---
title: Eventuele zero-day-beveiligingslekken beperken - Threat and Vulnerability Management
description: Meer informatie over het vinden en beperken van zero-day-beveiligingslekken in uw omgeving via Threat and Vulnerability Management.
keywords: Microsoft Defender for Endpoint tvm zero day vulnerabilities, tvm, threat & vulnerability management, zero day, 0-day, mitigate 0 day vulnerabilities, vulnerable CVE
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
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 2c746a74899a34827e089f4c9c2f6ecc396bb69c
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538769"
---
# <a name="mitigate-zero-day-vulnerabilities---threat-and-vulnerability-management"></a>Eventuele zero-day-beveiligingslekken beperken - Threat and Vulnerability Management

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Bedreiging en vulnerability management](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

Een zero-day-kwetsbaarheid is een openbaar openbaar gemaakt beveiligingsprobleem waarvoor geen officiële patches of beveiligingsupdates zijn uitgebracht. Zero-day-beveiligingslekken hebben vaak hoge ernstniveaus en worden actief benut.

Bedreigingen vulnerability management worden alleen zero-day-beveiligingslekken weergegeven die informatie bevatten.

## <a name="find-information-about-zero-day-vulnerabilities"></a>Informatie over zero-day-beveiligingslekken zoeken

Wanneer een zero-day-kwetsbaarheid is gevonden, wordt informatie over het probleem overgebracht via de volgende ervaringen in de Microsoft Defender-beveiligingscentrum.

>[!NOTE]
> 0-daagse mogelijkheden zijn momenteel niet beschikbaar voor niet-Windows producten (Mac, Linux); deze wordt echter in de toekomst toegevoegd.

### <a name="threat-and-vulnerability-management-dashboard"></a>Bedreiging en vulnerability management dashboard

Zoek naar aanbevelingen met een zero-day tag in de kaart 'Top security recommendations'.

![Topaanbevelingen met een zero-day-tag.](images/tvm-zero-day-top-security-recommendations.png)

Zoek de beste software met de zero-day tag in de kaart 'Top vulnerable software'.

![Top kwetsbaar software met een zero-day tag.](images/tvm-zero-day-top-software.png)

### <a name="weaknesses-page"></a>Pagina Zwakke punten

Zoek naar het benoemde zero-day-beveiligingsprobleem, samen met een beschrijving en details.

- Als aan dit beveiligingsprobleem een CVE-ID is toegewezen, ziet u het zero-day label naast de CVE-naam.

- Als aan dit beveiligingsprobleem geen CVE-ID is toegewezen, vindt u deze onder een interne, tijdelijke naam die eruitziet als 'TVM-XXXX-XXXX'. De naam wordt bijgewerkt zodra een officiële CVE-ID is toegewezen, maar de vorige interne naam kan nog steeds worden doorzocht en in het zijpaneel worden gevonden.

![Zero day example for CVE-2020-17087 in weaknesses page.](images/tvm-zero-day-weakness-name.png)

### <a name="software-inventory-page"></a>Pagina Softwarevoorraad

Zoek naar software met de zero-day tag. Filter op de tag 'zero day' om alleen software te zien met zero-day-beveiligingslekken.

![Voorbeeld van nul dagen van Windows Server 2016 op de pagina softwarevoorraad.](images/tvm-zero-day-software-inventory.png)

### <a name="software-page"></a>Softwarepagina

Zoek naar een zero-day-tag voor elke software die is beïnvloed door het zero-day-beveiligingsprobleem.

![Voorbeeld van nul dagen voor Windows Server 2016 softwarepagina.](images/tvm-zero-day-software-page.png)

### <a name="security-recommendations-page"></a>Pagina Met beveiligingsaanbevelingen

Bekijk duidelijke suggesties over herstel- en mitigatieopties, inclusief tijdelijke oplossingen als deze bestaan. Filter op de tag 'zero day' om alleen beveiligingsaanbevelingen te zien voor het oplossen van zero-day-beveiligingsproblemen.

Als er software is met een zero-day-kwetsbaarheid en extra beveiligingslekken, krijgt u één aanbeveling over alle beveiligingslekken.

![Voorbeeld van nul dagen Windows Server 2016 op de pagina met beveiligingsaanbevelingen.](images/tvm-zero-day-security-recommendation.png)

## <a name="addressing-zero-day-vulnerabilities"></a>Zero-day-beveiligingslekken oplossen

Ga naar de pagina met beveiligingsaanbevelingen en selecteer een aanbeveling met een nuldag. Er wordt een flyout geopend met informatie over de zero-day en andere beveiligingslekken voor die software.

Er wordt een koppeling gemaakt naar opties voor beperking en tijdelijke oplossingen als deze beschikbaar zijn. Tijdelijke oplossingen kunnen het risico van dit zero-day-beveiligingsprobleem beperken totdat een patch of beveiligingsupdate kan worden geïmplementeerd.

Open herstelopties en kies het type aandacht. Een 'aandacht vereist' hersteloptie wordt aanbevolen voor de zero-day-beveiligingslekken, omdat er nog geen update is uitgebracht. U kunt geen einddatum selecteren, omdat er geen specifieke actie moet worden ondernomen. Als er oudere beveiligingsproblemen zijn voor deze software die u wilt herstellen, kunt u de hersteloptie 'aandacht vereist' overschrijven en 'bijwerken' kiezen.

![Zero day flyout example of Windows Server 2016 in the security recommendations page.](images/tvm-zero-day-recommendation-flyout400.png)

## <a name="track-zero-day-remediation-activities"></a>Herstelactiviteiten van nul dagen bijhouden

Ga naar de Threat and Vulnerability Management [herstelpagina](tvm-remediation.md) om het item herstelactiviteit weer te geven. Als u de optie 'aandacht vereist' kiest, is er geen voortgangsbalk, ticketstatus of einddatum omdat er geen werkelijke actie is die we kunnen controleren. U kunt filteren op hersteltype, zoals 'software-update' of 'aandacht vereist', om alle activiteitenitems in dezelfde categorie weer te geven.

## <a name="patching-zero-day-vulnerabilities"></a>Beveiligingslekken van nul dagen verhelpen

Wanneer er een patch wordt uitgebracht voor de zero-day, wordt de aanbeveling gewijzigd in 'Update' en een blauw label er naast met de naam 'Nieuwe beveiligingsupdate voor nuldag'. Het wordt niet langer gezien als een zero-day-tag, de zero-day tag wordt van alle pagina's verwijderd.

![Aanbeveling voor 'Update Microsoft Windows 10' met een nieuw patchlabel.](images/tvm-zero-day-patch.jpg)

## <a name="related-articles"></a>Verwante artikelen

- [Overzicht van bedreigingen en vulnerability management](next-gen-threat-and-vuln-mgt.md)
- [Dashboard](tvm-dashboard-insights.md)
- [Beveiligingsaanbevelingen](tvm-security-recommendation.md)
- [Software-inventaris](tvm-software-inventory.md)
- [Beveiligingsproblemen in mijn organisatie](tvm-weaknesses.md)
