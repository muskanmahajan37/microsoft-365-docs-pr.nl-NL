---
title: De resultaten van AV-scans van Microsoft Defender bekijken
description: Bekijk de resultaten van scans met Microsoft Endpoint Configuration Manager, Microsoft Intune of de Windows Security-app
keywords: scanresultaten, herstel, volledige scan, snelle scan
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/28/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 3b8a299f41541be878a9e9023ab330ea973646fd
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764143"
---
# <a name="review-microsoft-defender-antivirus-scan-results"></a><span data-ttu-id="58944-104">Testresultaten van Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="58944-104">Review Microsoft Defender Antivirus scan results</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="58944-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="58944-105">**Applies to:**</span></span>

- [<span data-ttu-id="58944-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="58944-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="58944-107">Nadat een Microsoft Defender Antivirus-scan is voltooid, of dit nu een [on-demand](run-scan-microsoft-defender-antivirus.md) of geplande [scan](scheduled-catch-up-scans-microsoft-defender-antivirus.md)is, worden de resultaten opgenomen en kunt u de resultaten bekijken.</span><span class="sxs-lookup"><span data-stu-id="58944-107">After a Microsoft Defender Antivirus scan completes, whether it is an [on-demand](run-scan-microsoft-defender-antivirus.md) or [scheduled scan](scheduled-catch-up-scans-microsoft-defender-antivirus.md), the results are recorded and you can view the results.</span></span> 


## <a name="use-configuration-manager-to-review-scan-results"></a><span data-ttu-id="58944-108">Configuratiebeheer gebruiken om scanresultaten te bekijken</span><span class="sxs-lookup"><span data-stu-id="58944-108">Use Configuration Manager to review scan results</span></span>

<span data-ttu-id="58944-109">Zie [De status Endpoint Protection bewaken.](/configmgr/protect/deploy-use/monitor-endpoint-protection)</span><span class="sxs-lookup"><span data-stu-id="58944-109">See [How to monitor Endpoint Protection status](/configmgr/protect/deploy-use/monitor-endpoint-protection).</span></span>

## <a name="use-powershell-cmdlets-to-review-scan-results"></a><span data-ttu-id="58944-110">PowerShell-cmdlets gebruiken om scanresultaten te bekijken</span><span class="sxs-lookup"><span data-stu-id="58944-110">Use PowerShell cmdlets to review scan results</span></span>

<span data-ttu-id="58944-111">De volgende cmdlet retourneerd elke detectie op het eindpunt.</span><span class="sxs-lookup"><span data-stu-id="58944-111">The following cmdlet will return each detection on the endpoint.</span></span> <span data-ttu-id="58944-112">Als er meerdere detecties van dezelfde bedreiging zijn, wordt elke detectie afzonderlijk weergegeven op basis van het tijdstip van elke detectie:</span><span class="sxs-lookup"><span data-stu-id="58944-112">If there are multiple detections of the same threat, each detection will be listed separately, based on the time of each detection:</span></span>

```PowerShell
Get-MpThreatDetection
```

![schermafbeelding van PowerShell-cmdlets en -uitvoer](images/defender/wdav-get-mpthreatdetection.png)

<span data-ttu-id="58944-114">U kunt opgeven dat u de uitvoer wilt beperken om alleen de `-ThreatID` detecties voor een specifieke bedreiging weer te geven.</span><span class="sxs-lookup"><span data-stu-id="58944-114">You can specify `-ThreatID` to limit the output to only show the detections for a specific threat.</span></span>

<span data-ttu-id="58944-115">Als u bedreigingsdetecties wilt gebruiken, maar detecties van dezelfde bedreiging wilt combineren tot één item, kunt u de volgende cmdlet gebruiken:</span><span class="sxs-lookup"><span data-stu-id="58944-115">If you want to list threat detections, but combine detections of the same threat into a single item, you can use the following cmdlet:</span></span>

```PowerShell
Get-MpThreat
```

![schermafbeelding van PowerShell](images/defender/wdav-get-mpthreat.png)

<span data-ttu-id="58944-117">Zie [PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) gebruiken om Microsoft Defender Antivirus- en [Defender-cmdlets](/powershell/module/defender/) te configureren en uit te voeren voor meer informatie over het gebruik van PowerShell met Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="58944-117">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

## <a name="use-windows-management-instruction-wmi-to-review-scan-results"></a><span data-ttu-id="58944-118">Windows Management Instruction (WMI) gebruiken om scanresultaten te bekijken</span><span class="sxs-lookup"><span data-stu-id="58944-118">Use Windows Management Instruction (WMI) to review scan results</span></span>

<span data-ttu-id="58944-119">Gebruik de [ **methode Get** van de **MSFT_MpThreat** en **MSFT_MpThreatDetection**](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) klassen.</span><span class="sxs-lookup"><span data-stu-id="58944-119">Use the [**Get** method of the **MSFT_MpThreat** and **MSFT_MpThreatDetection**](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) classes.</span></span>


## <a name="related-articles"></a><span data-ttu-id="58944-120">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="58944-120">Related articles</span></span>

- [<span data-ttu-id="58944-121">De resultaten van Microsoft Defender Antivirus scans en herstel aanpassen, starten en controleren</span><span class="sxs-lookup"><span data-stu-id="58944-121">Customize, initiate, and review the results of Microsoft Defender Antivirus scans and remediation</span></span>](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="58944-122">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="58944-122">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)