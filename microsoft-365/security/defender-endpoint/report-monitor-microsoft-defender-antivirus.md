---
title: Microsoft Defender Antivirusbeveiliging controleren en rapporteren
description: Gebruik Configuratiebeheer of hulpprogramma's voor beveiligingsgegevens en gebeurtenisbeheer (SIEM) om rapporten te gebruiken en Microsoft Defender AV te controleren met PowerShell en WMI.
keywords: siem, monitor, rapport, Microsoft Defender AV
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 12/07/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: a31dfa7e5eba36937f4ab50205df938614e80b76
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765765"
---
# <a name="report-on-microsoft-defender-antivirus"></a><span data-ttu-id="b8c56-104">Rapporteren in Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="b8c56-104">Report on Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="b8c56-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="b8c56-105">**Applies to:**</span></span>

- [<span data-ttu-id="b8c56-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="b8c56-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="b8c56-107">Microsoft Defender Antivirus is ingebouwd in Windows 10, Windows Server 2019 en Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="b8c56-107">Microsoft Defender Antivirus is built into Windows 10, Windows Server 2019, and Windows Server 2016.</span></span> <span data-ttu-id="b8c56-108">Microsoft Defender Antivirus is van uw volgende generatie bescherming in Microsoft Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="b8c56-108">Microsoft Defender Antivirus is of your next-generation protection in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="b8c56-109">Beveiliging van de volgende generatie helpt uw apparaten te beschermen tegen softwaredreigingen zoals virussen, malware en spyware in e-mail, apps, de cloud en het web.</span><span class="sxs-lookup"><span data-stu-id="b8c56-109">Next-generation protection helps protect your devices from software threats like viruses, malware, and spyware across email, apps, the cloud, and the web.</span></span>

<span data-ttu-id="b8c56-110">Met Microsoft Defender Antivirus hebt u verschillende opties voor het controleren van de beveiligingsstatus en waarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="b8c56-110">With Microsoft Defender Antivirus, you have several options for reviewing protection status and alerts.</span></span> <span data-ttu-id="b8c56-111">U kunt Microsoft Endpoint Manager gebruiken om [Microsoft Defender Antivirus te](/configmgr/protect/deploy-use/monitor-endpoint-protection) controleren of [e-mailwaarschuwingen te maken.](/configmgr/protect/deploy-use/endpoint-configure-alerts)</span><span class="sxs-lookup"><span data-stu-id="b8c56-111">You can use Microsoft Endpoint Manager to [monitor Microsoft Defender Antivirus](/configmgr/protect/deploy-use/monitor-endpoint-protection) or [create email alerts](/configmgr/protect/deploy-use/endpoint-configure-alerts).</span></span> <span data-ttu-id="b8c56-112">U kunt ook de beveiliging bewaken met [Microsoft Intune.](/intune/introduction-intune)</span><span class="sxs-lookup"><span data-stu-id="b8c56-112">Or, you can monitor protection using [Microsoft Intune](/intune/introduction-intune).</span></span>  

<span data-ttu-id="b8c56-113">Microsoft Operations Management Suite heeft een [update compliance-invoeging](/windows/deployment/update/update-compliance-get-started) die rapporteert over belangrijke Microsoft Defender Antivirus-problemen, waaronder beveiligingsupdates en realtime beveiligingsinstellingen.</span><span class="sxs-lookup"><span data-stu-id="b8c56-113">Microsoft Operations Management Suite has an [Update Compliance add-in](/windows/deployment/update/update-compliance-get-started) that reports on key Microsoft Defender Antivirus issues, including protection updates and real-time protection settings.</span></span>

<span data-ttu-id="b8c56-114">Als u een SIEM-server (Security Information and Event Management) van derden hebt, kunt u ook [Windows Defender-clientgebeurtenissen gebruiken.](/windows/win32/events/windows-events)</span><span class="sxs-lookup"><span data-stu-id="b8c56-114">If you have a third-party security information and event management (SIEM) server, you can also consume [Windows Defender client events](/windows/win32/events/windows-events).</span></span> 

<span data-ttu-id="b8c56-115">Windows-gebeurtenissen bestaan uit verschillende bronnen voor beveiligingsgebeurtenissen, waaronder SAM-gebeurtenissen (verbeterd voor[Windows 10](/windows/whats-new/whats-new-windows-10-version-1507-and-1511), zie ook het onderwerp Beveiligingsaudit) en [Windows Defender-gebeurtenissen.](troubleshoot-microsoft-defender-antivirus.md) [](/windows/device-security/auditing/security-auditing-overview)</span><span class="sxs-lookup"><span data-stu-id="b8c56-115">Windows events comprise several security event sources, including Security Account Manager (SAM) events ([enhanced for Windows 10](/windows/whats-new/whats-new-windows-10-version-1507-and-1511), also see the [Security auditing](/windows/device-security/auditing/security-auditing-overview) topic) and  [Windows Defender events](troubleshoot-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="b8c56-116">Deze gebeurtenissen kunnen centraal worden samengevoegd met behulp van de [Windows-gebeurtenisverzamelaar.](/windows/win32/wec/windows-event-collector)</span><span class="sxs-lookup"><span data-stu-id="b8c56-116">These events can be centrally aggregated using the [Windows event collector](/windows/win32/wec/windows-event-collector).</span></span> <span data-ttu-id="b8c56-117">SiEM-servers hebben vaak verbindingslijnen voor Windows-gebeurtenissen, zodat u alle beveiligingsgebeurtenissen in uw SIEM-server kunt correleren.</span><span class="sxs-lookup"><span data-stu-id="b8c56-117">Often, SIEM servers have connectors for Windows events, allowing you to correlate all security events in your SIEM server.</span></span> 

<span data-ttu-id="b8c56-118">U kunt ook [malwaregebeurtenissen controleren met behulp van de malwarebeoordelingsoplossing in Log Analytics.](/azure/log-analytics/log-analytics-malware)</span><span class="sxs-lookup"><span data-stu-id="b8c56-118">You can also [monitor malware events using the Malware Assessment solution in Log Analytics](/azure/log-analytics/log-analytics-malware).</span></span>

<span data-ttu-id="b8c56-119">Zie de tabel [(Implementatie, beheer](deploy-manage-report-microsoft-defender-antivirus.md#ref2)en rapportageopties) voor het bewaken of bepalen van de status met PowerShell, WMI of Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="b8c56-119">For monitoring or determining status with PowerShell, WMI, or Microsoft Azure, see the [(Deployment, management, and reporting options table)](deploy-manage-report-microsoft-defender-antivirus.md#ref2).</span></span>

## <a name="related-articles"></a><span data-ttu-id="b8c56-120">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="b8c56-120">Related articles</span></span>

- [<span data-ttu-id="b8c56-121">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="b8c56-121">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="b8c56-122">Microsoft Defender Antivirus op Windows Server 2016 en 2019</span><span class="sxs-lookup"><span data-stu-id="b8c56-122">Microsoft Defender Antivirus on Windows Server 2016 and 2019</span></span>](microsoft-defender-antivirus-on-windows-server.md)
- [<span data-ttu-id="b8c56-123">Microsoft Defender Antivirus implementeren</span><span class="sxs-lookup"><span data-stu-id="b8c56-123">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)