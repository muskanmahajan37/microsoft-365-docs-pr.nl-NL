---
title: Uitsluitingen configureren en valideren voor Microsoft Defender voor Eindpunt op Linux
description: Uitsluitingen voor Microsoft Defender voor Eindpunt op Linux verstrekken en valideren. Uitsluitingen kunnen worden ingesteld voor bestanden, mappen en processen.
keywords: microsoft, defender, Microsoft Defender for Endpoint, linux, exclusions, scans, antivirus
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: bd506caa041af2585778fb3ecd7a40562463b17e
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/12/2021
ms.locfileid: "52346412"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-for-endpoint-on-linux"></a>Uitsluitingen configureren en valideren voor Microsoft Defender voor Eindpunt op Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

In dit artikel vindt u informatie over het definiëren van uitsluitingen die van toepassing zijn op scans op aanvraag, en realtime beveiliging en monitoring.

> [!IMPORTANT]
> De uitsluitingen die in dit artikel worden beschreven, zijn niet van toepassing op andere Defender voor Eindpunt op Linux-mogelijkheden, waaronder eindpuntdetectie en -respons (EDR). Bestanden die u uitsluit met de methoden die in dit artikel worden beschreven, kunnen nog steeds EDR waarschuwingen en andere detecties activeren.

U kunt bepaalde bestanden, mappen, processen en proces geopende bestanden uitsluiten van Defender voor Eindpunt op Linux-scans.

Uitsluitingen kunnen handig zijn om onjuiste detecties te voorkomen van bestanden of software die uniek of aangepast zijn aan uw organisatie. Ze kunnen ook handig zijn voor het verminderen van prestatieproblemen die worden veroorzaakt door Defender voor Eindpunt op Linux.

> [!WARNING]
> Als u uitsluitingen definieert, wordt de beveiliging die door Defender voor Eindpunt op Linux wordt geboden, verlaagd. U moet altijd de risico's evalueren die zijn gekoppeld aan het implementeren van uitsluitingen en u moet alleen bestanden uitsluiten die u zeker weet dat ze niet schadelijk zijn.

## <a name="supported-exclusion-types"></a>Ondersteunde uitsluitingstypen

In de volgende tabel ziet u de uitsluitingstypen die worden ondersteund door Defender voor Eindpunt op Linux.

Uitsluiting | Definitie | Voorbeelden
---|---|---
Bestandsextensie | Alle bestanden met de extensie, overal op het apparaat | `.test`
Bestand | Een specifiek bestand dat is geïdentificeerd door het volledige pad | `/var/log/test.log`<br/>`/var/log/*.log`<br/>`/var/log/install.?.log`
Map | Alle bestanden onder de opgegeven map (recursief) | `/var/log/`<br/>`/var/*/`
Proces | Een specifiek proces (opgegeven door het volledige pad of de bestandsnaam) en alle bestanden die hiermee worden geopend | `/bin/cat`<br/>`cat`<br/>`c?t`

> [!IMPORTANT]
> De bovenstaande paden moeten harde koppelingen zijn, geen symbolische koppelingen, om te kunnen worden uitgesloten. U kunt controleren of een pad een symbolische koppeling is door te `file <path-name>` lopen.

Bestands-, map- en procesuitsluitingen ondersteunen de volgende jokertekens:

Jokerteken | Omschrijving | Voorbeeld | Overeenkomsten | Komt niet overeen met
---|---|---|---|---
\* |    Komt overeen met een aantal tekens, inclusief geen tekens (houd er rekening mee dat wanneer dit jokerteken binnen een pad wordt gebruikt, dit slechts één map vervangt) | `/var/\*/\*.log` | `/var/log/system.log` | `/var/log/nested/system.log`
? | Komt overeen met een enkel teken | `file?.log` | `file1.log`<br/>`file2.log` | `file123.log`

## <a name="how-to-configure-the-list-of-exclusions"></a>De lijst met uitsluitingen configureren

### <a name="from-the-management-console"></a>Vanuit de beheerconsole

Zie Voorkeuren instellen voor Defender voor Eindpunt op Linux voor meer informatie over het configureren van uitsluitingen van Poppen, Ansible of een andere [beheerconsole.](linux-preferences.md)

### <a name="from-the-command-line"></a>Vanuit de opdrachtregel

Voer de volgende opdracht uit om de beschikbare schakelopties voor het beheren van uitsluitingen te bekijken:

```bash
mdatp exclusion
```

> [!TIP]
> Wanneer u uitsluitingen configureert met jokertekens, sluit u de parameter tussen dubbele aanhalingstekens om gglobbing te voorkomen.

Voorbeelden:

- Een uitsluiting voor een bestandsextensie toevoegen:

    ```bash
    mdatp exclusion extension add --name .txt
    ```
    ```Output
    Extension exclusion configured successfully
    ```

- Een uitsluiting voor een bestand toevoegen:

    ```bash
    mdatp exclusion file add --path /var/log/dummy.log
    ```
    ```Output
    File exclusion configured successfully
    ```

- Een uitsluiting voor een map toevoegen:

    ```bash
    mdatp exclusion folder add --path /var/log/
    ```
    ```Output
    Folder exclusion configured successfully
    ```

- Een uitsluiting voor een map met een jokerteken toevoegen:

    ```bash
    mdatp exclusion folder add --path "/var/*/"
    ```

    > [!NOTE]
    > Hiermee worden paden slechts één niveau lager *dan /var/* uitgesloten, maar geen mappen die dieper zijn geneste; bijvoorbeeld */var/this-subfolder/but-not-this-subfolder*.
    
    ```bash
    mdatp exclusion folder add --path "/var/"
    ```
    > [!NOTE]
    > Hiermee worden alle paden uitgesloten waarvan de bovenliggende paden */var/ zijn;* bijvoorbeeld */var/this-subfolder/and-this-subfolder-as-well*.

    ```Output
    Folder exclusion configured successfully
    ```

- Een uitsluiting voor een proces toevoegen:

    ```bash
    mdatp exclusion process add --name cat
    ```
    ```Output    
    Process exclusion configured successfully
    ```

## <a name="validate-exclusions-lists-with-the-eicar-test-file"></a>Lijsten met uitsluitingen valideren met het EICAR-testbestand

U kunt valideren dat uw uitsluitingslijsten werken met behulp `curl` van het downloaden van een testbestand.

Vervang in het volgende Bash-fragment `test.txt` door een bestand dat voldoet aan de uitsluitingsregels. Als u bijvoorbeeld de extensie hebt uitgesloten, vervangt `.testing` u `test.txt` door `test.testing` . Als u een pad test, controleert u of u de opdracht binnen dat pad hebt uitgevoerd.

```bash
curl -o test.txt https://www.eicar.org/download/eicar.com.txt
```

Als Defender voor Eindpunt op Linux malware rapporteert, werkt de regel niet. Als er geen malwarerapport is en het gedownloade bestand bestaat, werkt de uitsluiting. U kunt het bestand openen om te bevestigen dat de inhoud hetzelfde is als wat wordt beschreven op de website van het [EICAR-testbestand.](http://2016.eicar.org/86-0-Intended-use.html)

Als u geen internetverbinding hebt, kunt u uw eigen EICAR-testbestand maken. Schrijf de EICAR-tekenreeks naar een nieuw tekstbestand met de volgende opdracht Bash:

```bash
echo 'X5O!P%@AP[4\PZX54(P^)7CC)7}$EICAR-STANDARD-ANTIVIRUS-TEST-FILE!$H+H*' > test.txt
```

U kunt de tekenreeks ook kopiëren naar een leeg tekstbestand en proberen deze op te slaan met de bestandsnaam of in de map die u probeert uit te sluiten.

## <a name="allow-threats"></a>Bedreigingen toestaan

Naast het uitsluiten van het scannen van bepaalde inhoud, kunt u het product ook zo configureren dat bepaalde categorieën bedreigingen niet worden gedetecteerd (geïdentificeerd met de naam van de bedreiging). U moet voorzichtig zijn bij het gebruik van deze functionaliteit, omdat uw apparaat hierdoor niet wordt beveiligd.

Als u een bedreigingsnaam wilt toevoegen aan de toegestane lijst, voert u de volgende opdracht uit:

```bash
mdatp threat allowed add --name [threat-name]
```

De bedreigingsnaam die is gekoppeld aan een detectie op uw apparaat, kunt u verkrijgen met de volgende opdracht:

```bash
mdatp threat list
```

Als u bijvoorbeeld (de bedreigingsnaam die is gekoppeld aan de EICAR-detectie) wilt toevoegen aan de toegestane lijst, voert u `EICAR-Test-File (not a virus)` de volgende opdracht uit:

```bash
mdatp threat allowed add --name "EICAR-Test-File (not a virus)"
```
