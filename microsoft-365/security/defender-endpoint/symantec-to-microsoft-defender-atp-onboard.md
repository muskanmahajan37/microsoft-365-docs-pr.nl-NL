---
title: Symantec naar Microsoft Defender voor Eindpunt - Fase 3, Onboarding
description: Dit is Fase 3, Onboarding, van de migratie van Symantec naar Microsoft Defender voor Eindpunt
keywords: migratie, windows defender advanced threat protection, atp, edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-symantecmigrate
ms.topic: article
ms.date: 03/03/2021
ms.custom: migrationguides
ms.reviewer: depicker, yongrhee, chriggs
ms.openlocfilehash: 95b2e4bfc0eca58d6c71670b21ded81affcc219f
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185501"
---
# <a name="migrate-from-symantec---phase-3-onboard-to-microsoft-defender-for-endpoint"></a>Migreren van Symantec - Fase 3: Onboard to Microsoft Defender for Endpoint

**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

|[![Fase 1: Voorbereiden](images/phase-diagrams/prepare.png)](symantec-to-microsoft-defender-atp-prepare.md)<br/>[Fase 1: Voorbereiden](symantec-to-microsoft-defender-atp-prepare.md) |[![Fase 2: Instellen](images/phase-diagrams/setup.png)](symantec-to-microsoft-defender-atp-setup.md)<br/>[Fase 2: Instellen](symantec-to-microsoft-defender-atp-setup.md) |![Fase 3: Onboard](images/phase-diagrams/onboard.png)<br/>Fase 3: Onboard |
|--|--|--|
|| |*U bent er!* |


**Welkom bij fase 3 van [de migratie van Symantec naar Microsoft Defender voor Eindpunt.](symantec-to-microsoft-defender-atp-migration.md#the-migration-process)** Deze migratiefase bevat de volgende stappen:

1. [Onboard devices to Microsoft Defender for Endpoint](#onboard-devices-to-microsoft-defender-for-endpoint).
2. [Voer een detectietest uit.](#run-a-detection-test)
3. [Verwijder Symantec.](#uninstall-symantec)
4. [Zorg ervoor dat Microsoft Defender voor Eindpunt in de actieve modus staat.](#make-sure-microsoft-defender-for-endpoint-is-in-active-mode)

## <a name="onboard-devices-to-microsoft-defender-for-endpoint"></a>Onboard devices to Microsoft Defender for Endpoint

1. Ga naar het Microsoft Defender-beveiligingscentrum [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) () en meld u aan.
2. Kies **Instellingen**  >  **Apparaatbeheer**  >  **Onboarding**. 
3. Selecteer een besturingssysteem in de lijst Besturingssysteem selecteren om **het onboardingproces** te starten. 
4. Selecteer **onder Implementatiemethode** een optie. Volg de koppelingen en aanwijzingen om de apparaten van uw organisatie aan te nemen. Hulp nodig? Zie [Onboarding-methoden](#onboarding-methods) (in dit artikel).

### <a name="onboarding-methods"></a>Onboarding-methoden
 
Implementatiemethoden variëren, afhankelijk van het besturingssysteem dat is geselecteerd. Raadpleeg de bronnen in de onderstaande tabel voor hulp bij onboarding.

|Besturingssysteem  |Methode  |
|---------|---------|
|Windows 10     |- [Groepsbeleid](configure-endpoints-gp.md)<br/>- [Configuration Manager](configure-endpoints-sccm.md)<br/>- [Mobile Device Management (Intune)](configure-endpoints-mdm.md)<br/>- [Lokaal script](configure-endpoints-script.md) <br/><br/>**OPMERKING:** Een lokaal script is geschikt voor een conceptbewijs, maar mag niet worden gebruikt voor productie-implementatie. Voor een productie-implementatie wordt aangeraden groepsbeleid, Microsoft Endpoint Configuration Manager of Intune te gebruiken.         |
|- Windows 8.1 Enterprise <br/>- Windows 8.1 Pro <br/>- Windows 7 SP1 Enterprise <br/>- Windows 7 SP1 Pro     | [Microsoft Monitoring Agent](onboard-downlevel.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint)<br/><br/>**OPMERKING:** Microsoft Monitoring Agent is nu Azure Log Analytics-agent. Zie Logboekanalyse-agentoverzicht voor [meer informatie.](https://docs.microsoft.com/azure/azure-monitor/platform/log-analytics-agent)        |
|- Windows Server 2019 en hoger <br/>- Windows Server 2019 Core Edition <br/>- Windows Server versie 1803 en hoger |- [Lokaal script](configure-endpoints-script.md) <br/>- [Groepsbeleid](configure-endpoints-gp.md) <br/>- [Configuration Manager](/configure-endpoints-sccm.md) <br/>- [System Center Configuration Manager](configure-endpoints-sccm.md#onboard-devices-using-system-center-configuration-manager)<br/>- [VDI-onboarding-scripts voor niet-permanente apparaten](configure-endpoints-vdi.md) <br/><br/>**OPMERKING:** Een lokaal script is geschikt voor een conceptbewijs, maar mag niet worden gebruikt voor productie-implementatie. Voor een productie-implementatie wordt aangeraden groepsbeleid, Microsoft Endpoint Configuration Manager of Intune te gebruiken.    |
|- Windows Server 2016 <br/>- Windows Server 2012 R2 <br/>- Windows Server 2008 R2 SP1  |- [Microsoft Defender-beveiligingscentrum](configure-server-endpoints.md)<br/>- [Azure Security Center](https://docs.microsoft.com/azure/security-center/security-center-wdatp) |
|macOS<br/>- 10,15 (Catalina)<br/>- 10,14 (Mojave)<br/>- 10,13 (High Sierra)<br/><br/>iOS<br/><br/>Linux:<br/>- RHEL 7.2+<br/>- CentOS Linux 7.2+<br/>- Ubuntu 16 LTS of hoger LTS<br/>- SLES 12+<br/>- Debian 9+<br/>- Oracle Linux 7.2 |[Onboard niet-Windows-apparaten](configure-endpoints-non-windows.md)  |

## <a name="run-a-detection-test"></a>Een detectietest uitvoeren

Als u wilt controleren of uw onboarded-apparaten correct zijn verbonden met Microsoft Defender voor Eindpunt, kunt u een detectietest uitvoeren.

|Besturingssysteem  |Richtlijnen  |
|---------|---------|
|- Windows 10 <br/>- Windows Server 2019 <br/>- Windows Server, versie 1803 <br/>- Windows Server 2016 <br/>- Windows Server 2012 R2     |Zie [Een detectietest uitvoeren.](run-detection-test.md) <br/><br/>Ga naar de site met demoscenario's voor Microsoft Defender voor eindpunten () en [https://demo.wd.microsoft.com](https://demo.wd.microsoft.com) probeer een of meer van de scenario's. Probeer bijvoorbeeld het **door de cloud geleverde beveiligingsdemoscenario.**         |
|macOS<br/>- 10,15 (Catalina)<br/>- 10,14 (Mojave)<br/>- 10,13 (High Sierra)     |Download en gebruik de doe-het-zelf-app op [https://aka.ms/mdatpmacosdiy](https://aka.ms/mdatpmacosdiy) . <br/><br/>Zie Microsoft Defender voor Eindpunt voor Mac voor [meer informatie.](microsoft-defender-endpoint-mac.md)        |
|Linux:<br/>- RHEL 7.2+<br/>- CentOS Linux 7.2+<br/>- Ubuntu 16 LTS of hoger LTS<br/>- SLES 12+<br/>- Debian 9+<br/>- Oracle Linux 7.2 |1. Voer de volgende opdracht uit en zoek naar een resultaat van **1:** <br/>`mdatp health --field real_time_protection_enabled`. <br/><br/>2. Open een terminalvenster en voer de volgende opdracht uit: <br/>`curl -o ~/Downloads/eicar.com.txt https://www.eicar.org/download/eicar.com.txt`. <br/><br/>3. Voer de volgende opdracht uit om gedetecteerde bedreigingen op te geven: <br/>`mdatp threat list`. <br/><br/>Zie [Microsoft Defender voor Eindpunt voor Linux voor meer informatie.](microsoft-defender-endpoint-linux.md) |

## <a name="uninstall-symantec"></a>Verwijder Symantec

Nu u de apparaten van uw organisatie hebt ge onboarded bij Microsoft Defender voor Eindpunt, is de volgende stap het verwijderen van Symantec.

1. [TamperBeveiliging uitschakelen](https://knowledge.broadcom.com/external/article?legacyId=tech192023) in Symantec.
2. Verwijder het verwijderwachtwoord voor Symantec:<br/>
   1. Open registereditor op uw Windows-apparaten als beheerder.
   2. Ga naar `HKEY_LOCAL_MACHINE\SOFTWARE\Symantec\Symantec Endpoint Protection\SMC`.
   3. Zoek naar een item met de naam **SmcInstData**. 
   4. Klik met de rechtermuisknop op het item en kies **vervolgens Verwijderen.** 
3. Verwijder Symantec van uw apparaten. Zie de documentatie van Broadcom als u hier hulp bij nodig hebt. Hier zijn enkele Broadcom-bronnen: 
   - [Bescherming tegen eindpunten van Symantec verwijderen](https://knowledge.broadcom.com/external/article/156148/uninstall-symantec-endpoint-protection.html)
   - Windows-apparaten: [Endpoint Protection 14-clients](https://knowledge.broadcom.com/external/article?articleId=170040) handmatig verwijderen in Windows
   - macOS-computers: Software voor Mac verwijderen met [RemoveSymantecMacFiles](https://knowledge.broadcom.com/external/article?articleId=151387)
   - Linux-apparaten: [Veelgestelde vragen over Endpoint Protection voor Linux](https://knowledge.broadcom.com/external/article?articleId=162054)

## <a name="make-sure-microsoft-defender-for-endpoint-is-in-active-mode"></a>Zorg ervoor dat Microsoft Defender voor Eindpunt actief is

Nu u Symantec hebt verwijderd, moet u ervoor zorgen dat Microsoft Defender Antivirus en Microsoft Defender voor Eindpunt zijn ingeschakeld en in de actieve modus.

Ga hiervoor naar de site met demoscenario's voor Microsoft Defender for Endpoint [https://demo.wd.microsoft.com](https://demo.wd.microsoft.com) (). Probeer een of meer van de demoscenario's op die pagina, inclusief ten minste de volgende:
- Beveiliging in de cloud
- Potentieel ongewenste toepassingen (PUA)
- Netwerkbeveiliging (NP)

> [!IMPORTANT]
> Als u Windows Server 2016 gebruikt, moet u mogelijk Microsoft Defender Antivirus handmatig starten. U kunt dit doen met de PowerShell-cmdlet `mpcmdrun.exe -wdenable` op het apparaat.

## <a name="next-steps"></a>Volgende stappen

**Gefeliciteerd!** U hebt de migratie [van Symantec naar Microsoft Defender voor Eindpunt voltooid!](symantec-to-microsoft-defender-atp-migration.md#the-migration-process) 
- [Ga naar het dashboard voor beveiligingsbewerkingen](security-operations-dashboard.md) in het Microsoft Defender-beveiligingscentrum ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ). 
- [Beheer Microsoft Defender voor Eindpunt, na de migratie.](manage-atp-post-migration.md)