---
title: Beveiligingsupdates Microsoft Defender Antivirus plannen
description: Plan de dag, tijd en interval voor wanneer beveiligingsupdates moeten worden gedownload
keywords: updates, beveiligingslijnlijnen, planningsupdates
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
search.appverid: met150
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 26b88b8677c27a5d6615776a371326e37034afd4
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275034"
---
# <a name="manage-the-schedule-for-when-protection-updates-should-be-downloaded-and-applied"></a>Het schema beheren voor wanneer beveiligingsupdates moeten worden gedownload en toegepast

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/)

Microsoft Defender Antivirus kunt u bepalen wanneer het moet zoeken naar en updates downloaden.

U kunt updates voor uw eindpunten plannen door: 

- De dag van de week opgeven om te controleren op beveiligingsupdates 
- Het interval opgeven om te controleren op beveiligingsupdates
- De tijd opgeven om te controleren op beveiligingsupdates

U kunt ook willekeurig de tijden kiezen waarop elk eindpunt beveiligingsupdates controleert en downloadt. Zie het [onderwerp Planning scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md) voor meer informatie.

## <a name="use-configuration-manager-to-schedule-protection-updates"></a>Configuration Manager gebruiken om beveiligingsupdates te plannen

1.  Open op Microsoft Endpoint Manager console het antimalwarebeleid dat u wilt wijzigen (klik **op** Activa en naleving in het navigatiedeelvenster aan de linkerkant en vouw de structuur uit naar Overzicht  >  **Endpoint Protection**  >  **Antimalware-beleid**)

2.  Ga naar de **sectie Beveiligingsinformatie-updates.**

3. Updates op een bepaald moment controleren en downloaden:
      1. Stel **Controleren op Endpoint Protection beveiligingsintelligentieupdates in met een bepaald interval...** op **0**.
      2. Stel **Controleren op Endpoint Protection beveiligingsinformatieupdates dagelijks op...** in op het moment waarop updates moeten worden gecontroleerd.
      3
4. Als u updates met een doorlopend interval wilt controleren en downloaden, stelt u Controleren op Endpoint Protection beveiligingsintelligentieupdates met een specifiek **interval in...** in op het aantal uren dat moet plaatsvinden tussen updates.

5.  [Implementeer het bijgewerkte beleid zoals gewoonlijk.](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)

## <a name="use-group-policy-to-schedule-protection-updates"></a>Groepsbeleid gebruiken om beveiligingsupdates te plannen

> [!IMPORTANT]
> Standaard wordt Microsoft Defender Antivirus 15 minuten vóór het tijdstip van geplande scans op een update. Als u deze instellingen inschakelen, wordt deze standaard overgenomen.

1.  Open op uw groepsbeleidsbeheercomputer de [console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))Groepsbeleidsbeheer, klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en klik op **Bewerken.**

3.  Ga in **de Editor voor groepsbeleidsbeheer** naar **Computerconfiguratie.**

4.  Klik **op Beleid** en vervolgens op **Beheersjablonen.**

5.  Vouw de structuur uit Windows **onderdelen**  >  **Microsoft Defender Antivirus**  >  **Signature Intelligence Updates** en configureer de volgende instellingen:

    1. Dubbelklik op de instelling Geef de dag van de week op om te controleren **of beveiligingsinformatieupdates** zijn ingesteld en stel de optie in op **Ingeschakeld.** Voer de dag van de week in om te controleren op updates. Klik op **OK**.
    2. Dubbelklik op de instelling Geef het interval op om te controleren op de instelling **beveiligingsinformatieupdates** en stel de optie in op **Ingeschakeld.** Voer het aantal uren tussen updates in. Klik op **OK**.
    3. Dubbelklik op **de instelling Tijd opgeven om te controleren op beveiligingsinformatie-updates** en stel de optie in op **Ingeschakeld.** Voer de tijd in waarop updates moeten worden gecontroleerd. De tijd is gebaseerd op de lokale tijd van het eindpunt. Klik op **OK**.


## <a name="use-powershell-cmdlets-to-schedule-protection-updates"></a>PowerShell-cmdlets gebruiken om beveiligingsupdates te plannen

Gebruik de volgende cmdlets:

```PowerShell
Set-MpPreference -SignatureScheduleDay
Set-MpPreference -SignatureScheduleTime
Set-MpPreference -SignatureUpdateInterval
```

Zie [PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) gebruiken om Microsoft Defender Antivirus en [Defender-cmdlets](/powershell/module/defender/) te configureren en uit te voeren voor meer informatie over het gebruik van PowerShell met Microsoft Defender Antivirus.

## <a name="use-windows-management-instruction-wmi-to-schedule-protection-updates"></a>Gebruik Windows Management Instruction (WMI) om beveiligingsupdates te plannen

Gebruik de [ **methode Set** of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class voor de volgende eigenschappen:

```WMI
SignatureScheduleDay
SignatureScheduleTime
SignatureUpdateInterval
```

Zie het volgende voor meer informatie en toegestane parameters:
- [Windows Defender WMIv2-API's](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="related-articles"></a>Verwante artikelen

- [Implementatie van Microsoft Defender Antivirus](deploy-manage-report-microsoft-defender-antivirus.md)
- [Updates Microsoft Defender Antivirus en basislijnen toepassen](manage-updates-baselines-microsoft-defender-antivirus.md)
- [Updates beheren voor eindpunten die verouderd zijn](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [Op basis van gebeurtenissen afgedwongen updates beheren](manage-event-based-updates-microsoft-defender-antivirus.md)
- [Updates beheren voor mobiele apparaten en virtuele machines (VM's)](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)