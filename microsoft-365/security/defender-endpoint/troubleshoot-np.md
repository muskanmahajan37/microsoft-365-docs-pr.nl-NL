---
title: Problemen met netwerkbeveiliging oplossen
description: Resources en voorbeeldcode om problemen met netwerkbeveiliging in Microsoft Defender voor Eindpunt op te lossen.
keywords: probleemoplossing, fout, fix, windows defender bijvoorbeeld, asr, regels, hips, troubleshoot, audit, exclusion, false positive, broken, blocking, Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: oogunrinde
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: f77ce94fda63a9e7e8a9484a67a22eeec136d619
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935879"
---
# <a name="troubleshoot-network-protection"></a>Problemen met netwerkbeveiliging oplossen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


Wanneer u [netwerkbeveiliging gebruikt,](network-protection.md) kunnen er problemen zijn, zoals:

- Netwerkbeveiliging blokkeert een veilige website (onwaar positief)
- Netwerkbeveiliging blokkeert een verdachte of bekende schadelijke website (onwaar negatief)

Er zijn vier stappen om deze problemen op te lossen:

1. Vereisten bevestigen
2. Controlemodus gebruiken om de regel te testen
3. Uitsluitingen toevoegen voor de opgegeven regel (voor onwaar-positieven)
4. Ondersteuningslogboeken verzenden

## <a name="confirm-prerequisites"></a>Vereisten bevestigen

Netwerkbeveiliging werkt alleen op apparaten met de volgende voorwaarden:

>[!div class="checklist"]
> - Eindpunten worden uitgevoerd met Windows 10 Pro- of Enterprise-versie, versie 1709 of hoger.
> - Eindpunten gebruiken Microsoft Defender Antivirus als de enige antivirusbeveiligings-app. [Bekijk wat er gebeurt wanneer u een niet-Microsoft-antivirusoplossing gebruikt.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)
> - [Realtime beveiliging](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) is ingeschakeld.
> - [Beveiliging in de cloud](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) is ingeschakeld.
> - De controlemodus is niet ingeschakeld. Gebruik [Groepsbeleid om](enable-network-protection.md#group-policy) de regel in te stellen **op Uitgeschakeld** (waarde: **0**).

## <a name="use-audit-mode"></a>Controlemodus gebruiken

U kunt netwerkbeveiliging inschakelen in de auditmodus en vervolgens naar een website gaan die we hebben gemaakt om de functie te demo's. Alle websiteverbindingen worden toegestaan door netwerkbeveiliging, maar een gebeurtenis wordt geregistreerd om een verbinding aan te geven die zou zijn geblokkeerd als netwerkbeveiliging was ingeschakeld.

1. Netwerkbeveiliging instellen op **auditmodus.**

   ```PowerShell
   Set-MpPreference -EnableNetworkProtection AuditMode
   ```

2. Voer de verbindingsactiviteit uit die een probleem veroorzaakt (bijvoorbeeld proberen de site te bezoeken of verbinding te maken met het IP-adres dat u wel of niet wilt blokkeren).

3. [Bekijk de logboeken voor netwerkbeveiliging om](network-protection.md#review-network-protection-events-in-windows-event-viewer) te zien of de verbinding door de functie is geblokkeerd als deze is ingesteld op **Ingeschakeld.**
   
   Als netwerkbeveiliging een verbinding die u verwacht niet blokkeert, blokkeert, kunt u de functie inschakelen.

   ```PowerShell
   Set-MpPreference -EnableNetworkProtection Enabled
   ```

## <a name="report-a-false-positive-or-false-negative"></a>Een onwaar positief of onwaar negatief rapporteren

Als u de functie hebt getest met de demosite en met de auditmodus en netwerkbeveiliging werkt aan vooraf geconfigureerde scenario's, maar niet werkt zoals verwacht voor een specifieke verbinding, gebruikt u het webinzendingsformulier van [Windows Defender Security Intelligence](https://www.microsoft.com/wdsi/filesubmission) om een onwaar negatief of onwaar positief voor netwerkbeveiliging te melden. Met een E5-abonnement kunt u ook een koppeling naar [een bijbehorende waarschuwing geven.](alerts-queue.md)

Zie [Fout-positieve/negatieven adresseert in Microsoft Defender voor Eindpunt.](defender-endpoint-false-positives-negatives.md)

## <a name="exclude-website-from-network-protection-scope"></a>Website uitsluiten van netwerkbeveiligingsbereik

Als u de geblokkeerde website wilt toestaan (onwaar positief), voegt u de URL toe aan de [lijst met vertrouwde sites.](https://blogs.msdn.microsoft.com/asiatech/2014/08/19/how-to-add-web-sites-to-trusted-sites-via-gpo-from-dc-installed-ie10-or-higher-ie-version/) Webbronnen uit deze lijst omzeilen de netwerkbeveiligingscontrole.

## <a name="collect-diagnostic-data-for-file-submissions"></a>Diagnostische gegevens verzamelen voor bestandsinzendingen

Wanneer u een probleem met netwerkbeveiliging rapporteert, wordt u gevraagd diagnostische gegevens te verzamelen en te verzenden die kunnen worden gebruikt door microsoft-ondersteunings- en technische teams om problemen op te lossen.

1. Open een opdrachtprompt met verhoogde opdracht en wijzig in de Windows Defender-adreslijst:

   ```console
   cd c:\program files\windows defender
   ```

2. Voer deze opdracht uit om de diagnostische logboeken te genereren:

   ```console
   mpcmdrun -getfiles
   ```

3. Voeg het bestand toe aan het inzendingsformulier. Diagnostische logboeken worden standaard opgeslagen op `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab` . 

## <a name="resolve-connectivity-issues-with-network-protection-for-e5-customers"></a>Verbindingsproblemen met netwerkbeveiliging oplossen (voor E5-klanten)

Vanwege de omgeving waarin netwerkbeveiliging wordt uitgevoerd, kan Microsoft de proxy-instellingen van het besturingssysteem niet zien. In sommige gevallen kunnen netwerkbeveiligings clients de cloudservice niet bereiken. Als u verbindingsproblemen met netwerkbeveiliging wilt oplossen, configureert u een van de volgende registersleutels, zodat netwerkbeveiliging op de hoogte wordt van de proxyconfiguratie:

```powershell
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyServer /d "<proxy IP address: Port>" /f
```

---OR---


```powershell
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyPacUrl /d "<Proxy PAC url>" /f
```

U kunt de registersleutel configureren met PowerShell, Microsoft Endpoint Manager of Groepsbeleid. Hier zijn enkele bronnen die u kunt helpen:
- [Werken met registersleutels](/powershell/scripting/samples/working-with-registry-keys)
- [Aangepaste clientinstellingen configureren voor Endpoint Protection](/mem/configmgr/protect/deploy-use/endpoint-protection-configure-client)
- [Groepsbeleidsinstellingen gebruiken om endpointbeveiliging te beheren](/mem/configmgr/protect/deploy-use/endpoint-protection-group-policies)

## <a name="see-also"></a>Zie ook

- [Netwerkbeveiliging](network-protection.md)
- [Netwerkbeveiliging evalueren](evaluate-network-protection.md)
- [Netwerkbeveiliging inschakelen](enable-network-protection.md)
- [False positives/negatives in Defender for Endpoint adresseert](defender-endpoint-false-positives-negatives.md)
