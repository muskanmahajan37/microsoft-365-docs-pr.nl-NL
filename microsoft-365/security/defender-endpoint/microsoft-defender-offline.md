---
title: Microsoft Defender Offline in Windows 10
description: U kunt Microsoft Defender Offline rechtstreeks vanuit de Windows Defender Antivirus-app gebruiken. U kunt ook beheren hoe deze wordt geïmplementeerd in uw netwerk.
keywords: scannen, defender, offline
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 3b1e7e70c6ca217d3ad8859c1493598d71054f84
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765333"
---
# <a name="run-and-review-the-results-of-a-microsoft-defender-offline-scan"></a><span data-ttu-id="4b4ab-105">De resultaten van een Microsoft Defender Offline-scan uitvoeren en bekijken</span><span class="sxs-lookup"><span data-stu-id="4b4ab-105">Run and review the results of a Microsoft Defender Offline scan</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="4b4ab-106">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="4b4ab-106">**Applies to:**</span></span>

- [<span data-ttu-id="4b4ab-107">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="4b4ab-107">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="4b4ab-108">Microsoft Defender Offline is een antimalware scanprogramma waarmee u een scan kunt starten en uitvoeren vanuit een vertrouwde omgeving.</span><span class="sxs-lookup"><span data-stu-id="4b4ab-108">Microsoft Defender Offline is an antimalware scanning tool that lets you boot and run a scan from a trusted environment.</span></span> <span data-ttu-id="4b4ab-109">De scan wordt uitgevoerd van buiten de normale Windows-kernel, zodat deze zich kan richten op malware die probeert de Windows-shell te omzeilen, zoals virussen en rootkits die de master boot record (MBR) infecteren of overschrijven.</span><span class="sxs-lookup"><span data-stu-id="4b4ab-109">The scan runs from outside the normal Windows kernel so it can target malware that attempts to bypass the Windows shell, such as viruses and rootkits that infect or overwrite the master boot record (MBR).</span></span>

<span data-ttu-id="4b4ab-110">U kunt Microsoft Defender Offline gebruiken als u vermoedt dat er een malware-infectie is, of als u wilt bevestigen dat het eindpunt grondig is opschoond na een malware-uitbraak.</span><span class="sxs-lookup"><span data-stu-id="4b4ab-110">You can use Microsoft Defender Offline if you suspect a malware infection, or you want to confirm a thorough clean of the endpoint after a malware outbreak.</span></span>

<span data-ttu-id="4b4ab-111">In Windows 10 kan Microsoft Defender Offline met één klik rechtstreeks vanuit de [Windows Security-app worden uitgevoerd.](microsoft-defender-security-center-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="4b4ab-111">In Windows 10, Microsoft Defender Offline can be run with one click directly from the [Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span> <span data-ttu-id="4b4ab-112">In eerdere versies van Windows moest een gebruiker Microsoft Defender Offline installeren om opstartbare media te installeren, het eindpunt opnieuw op te starten en de opstartbare media te laden.</span><span class="sxs-lookup"><span data-stu-id="4b4ab-112">In previous versions of Windows, a user had to install Microsoft Defender Offline to bootable media, restart the endpoint, and load the bootable media.</span></span>

## <a name="prerequisites-and-requirements"></a><span data-ttu-id="4b4ab-113">vereisten en vereisten</span><span class="sxs-lookup"><span data-stu-id="4b4ab-113">prerequisites and requirements</span></span>

<span data-ttu-id="4b4ab-114">Microsoft Defender Offline in Windows 10 heeft dezelfde hardwarevereisten als Windows 10.</span><span class="sxs-lookup"><span data-stu-id="4b4ab-114">Microsoft Defender Offline in Windows 10 has the same hardware requirements as Windows 10.</span></span> 

<span data-ttu-id="4b4ab-115">Zie de volgende onderwerpen voor meer informatie over windows 10-vereisten:</span><span class="sxs-lookup"><span data-stu-id="4b4ab-115">For more information about Windows 10 requirements, see the following topics:</span></span>

- [<span data-ttu-id="4b4ab-116">Minimale hardwarevereisten</span><span class="sxs-lookup"><span data-stu-id="4b4ab-116">Minimum hardware requirements</span></span>](/windows-hardware/design/minimum/minimum-hardware-requirements-overview)

- [<span data-ttu-id="4b4ab-117">Richtlijnen voor hardwarecomponenten</span><span class="sxs-lookup"><span data-stu-id="4b4ab-117">Hardware component guidelines</span></span>](/windows-hardware/design/component-guidelines/components)

> [!NOTE]
> <span data-ttu-id="4b4ab-118">Microsoft Defender Offline wordt niet ondersteund op machines ARM processors of op Windows Server Stock Keeping Units.</span><span class="sxs-lookup"><span data-stu-id="4b4ab-118">Microsoft Defender Offline is not supported on machines with ARM processors, or on Windows Server Stock Keeping Units.</span></span>

<span data-ttu-id="4b4ab-119">Als u Microsoft Defender Offline wilt uitvoeren vanaf het eindpunt, moet de gebruiker zijn aangemeld met beheerdersbevoegdheden.</span><span class="sxs-lookup"><span data-stu-id="4b4ab-119">To run Microsoft Defender Offline from the endpoint, the user must be logged in with administrator privileges.</span></span>
 
## <a name="microsoft-defender-offline-updates"></a><span data-ttu-id="4b4ab-120">Offlineupdates van Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="4b4ab-120">Microsoft Defender Offline updates</span></span>

<span data-ttu-id="4b4ab-121">Microsoft Defender Offline gebruikt de meest recente beveiligingsupdates die beschikbaar zijn op het eindpunt. deze wordt bijgewerkt wanneer Windows Defender Antivirus wordt bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="4b4ab-121">Microsoft Defender Offline uses the most recent protection updates available on the endpoint; it's updated whenever Windows Defender Antivirus is updated.</span></span> 

> [!NOTE]
> <span data-ttu-id="4b4ab-122">Voordat u een offlinescan uitwerkt, moet u proberen microsoft Defender AV-beveiliging bij te werken.</span><span class="sxs-lookup"><span data-stu-id="4b4ab-122">Before running an offline scan, you should attempt to update Microsoft Defender AV protection.</span></span> <span data-ttu-id="4b4ab-123">U kunt een update met groepsbeleid forcen of updates naar eindpunten implementeren, of u kunt handmatig de meest recente beveiligingsupdates downloaden en installeren vanuit het [Microsoft Malware Protection Center.](https://www.microsoft.com/security/portal/definitions/adl.aspx)</span><span class="sxs-lookup"><span data-stu-id="4b4ab-123">You can either force an update with Group Policy or however you normally deploy updates to endpoints, or you can manually download and install the latest protection updates from the [Microsoft Malware Protection Center](https://www.microsoft.com/security/portal/definitions/adl.aspx).</span></span>

<span data-ttu-id="4b4ab-124">Zie het [onderwerp Updates van Microsoft Defender Antivirus Security Intelligence beheren](manage-protection-updates-microsoft-defender-antivirus.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="4b4ab-124">See the [Manage Microsoft Defender Antivirus Security intelligence  updates](manage-protection-updates-microsoft-defender-antivirus.md) topic for more information.</span></span>

## <a name="usage-scenarios"></a><span data-ttu-id="4b4ab-125">Gebruiksscenario's</span><span class="sxs-lookup"><span data-stu-id="4b4ab-125">Usage scenarios</span></span>

<span data-ttu-id="4b4ab-126">In Windows 10, versie 1607, kunt u handmatig een offlinescan forcen.</span><span class="sxs-lookup"><span data-stu-id="4b4ab-126">In Windows 10, version 1607, you can manually force an offline scan.</span></span> <span data-ttu-id="4b4ab-127">Als Windows Defender bepaalt dat Microsoft Defender Offline moet worden uitgevoerd, wordt de gebruiker op het eindpunt gevraagd.</span><span class="sxs-lookup"><span data-stu-id="4b4ab-127">Alternatively, if Windows Defender determines that Microsoft Defender Offline needs to run, it will prompt the user on the endpoint.</span></span> 

<span data-ttu-id="4b4ab-128">De noodzaak om een offlinescan uit te voeren, wordt ook in Microsoft Endpoint Manager onthuld als u deze gebruikt om uw eindpunten te beheren.</span><span class="sxs-lookup"><span data-stu-id="4b4ab-128">The need to perform an offline scan will also be revealed in Microsoft Endpoint Manager if you're using it to manage your endpoints.</span></span>

<span data-ttu-id="4b4ab-129">De prompt kan optreden via een melding, vergelijkbaar met de volgende:</span><span class="sxs-lookup"><span data-stu-id="4b4ab-129">The prompt can occur via a notification, similar to the following:</span></span>

![Windows-melding met de vereiste om Microsoft Defender Offline uit te voeren](images/defender/notification.png)

<span data-ttu-id="4b4ab-131">De gebruiker krijgt ook een melding binnen de Windows Defender-client.</span><span class="sxs-lookup"><span data-stu-id="4b4ab-131">The user will also be notified within the Windows Defender client.</span></span>

<span data-ttu-id="4b4ab-132">In Configuration Manager kunt u de status van eindpunten identificeren door te navigeren naar Monitoring **> Overview > Security > Endpoint Protection Status > System Center Endpoint Protection Status**.</span><span class="sxs-lookup"><span data-stu-id="4b4ab-132">In Configuration Manager, you can identify the status of endpoints by navigating to **Monitoring > Overview > Security > Endpoint Protection Status > System Center Endpoint Protection Status**.</span></span> 

<span data-ttu-id="4b4ab-133">Microsoft Defender Offline scans worden aangegeven onder **Malware herstelstatus** als **Offline scannen vereist**.</span><span class="sxs-lookup"><span data-stu-id="4b4ab-133">Microsoft Defender Offline scans are indicated under **Malware remediation status** as **Offline scan required**.</span></span>

![Microsoft Endpoint Manager die aangeeft dat een Microsoft Defender Offline-scan is vereist](images/defender/sccm-wdo.png)

## <a name="configure-notifications"></a><span data-ttu-id="4b4ab-135">Meldingen configureren</span><span class="sxs-lookup"><span data-stu-id="4b4ab-135">Configure notifications</span></span>

<span data-ttu-id="4b4ab-136">Microsoft Defender Offline-meldingen zijn geconfigureerd in dezelfde beleidsinstelling als andere AV-meldingen van Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="4b4ab-136">Microsoft Defender Offline notifications are configured in the same policy setting as other Microsoft Defender AV notifications.</span></span>

<span data-ttu-id="4b4ab-137">Zie de meldingen configureren die worden weergegeven in het onderwerp Eindpunten voor meer [informatie](configure-notifications-microsoft-defender-antivirus.md) over meldingen in Windows Defender.</span><span class="sxs-lookup"><span data-stu-id="4b4ab-137">For more information about notifications in Windows Defender, see the [Configure the notifications that appear on endpoints](configure-notifications-microsoft-defender-antivirus.md) topic.</span></span>

## <a name="run-a-scan"></a><span data-ttu-id="4b4ab-138">Een scan uitvoeren</span><span class="sxs-lookup"><span data-stu-id="4b4ab-138">Run a scan</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="4b4ab-139">Voordat u Microsoft Defender Offline gebruikt, moet u bestanden opslaan en lopende programma's afsluiten.</span><span class="sxs-lookup"><span data-stu-id="4b4ab-139">Before you use Microsoft Defender Offline, make sure you save any files and shut down running programs.</span></span> <span data-ttu-id="4b4ab-140">De offlinescan van Microsoft Defender duurt ongeveer 15 minuten.</span><span class="sxs-lookup"><span data-stu-id="4b4ab-140">The Microsoft Defender Offline scan takes about 15 minutes to run.</span></span> <span data-ttu-id="4b4ab-141">Het eindpunt wordt opnieuw gestart wanneer de scan is voltooid.</span><span class="sxs-lookup"><span data-stu-id="4b4ab-141">It will restart the endpoint when the scan is complete.</span></span> <span data-ttu-id="4b4ab-142">De scan wordt uitgevoerd buiten de gebruikelijke Windows-besturingssysteemomgeving.</span><span class="sxs-lookup"><span data-stu-id="4b4ab-142">The scan is performed outside of the usual Windows operating environment.</span></span> <span data-ttu-id="4b4ab-143">De gebruikersinterface wordt anders weergegeven dan een normale scan die wordt uitgevoerd door Windows Defender.</span><span class="sxs-lookup"><span data-stu-id="4b4ab-143">The user interface will appear different to a normal scan performed by Windows Defender.</span></span> <span data-ttu-id="4b4ab-144">Nadat de scan is voltooid, wordt het eindpunt opnieuw gestart en wordt Windows normaal geladen.</span><span class="sxs-lookup"><span data-stu-id="4b4ab-144">After the scan is completed, the endpoint will be restarted and Windows will load normally.</span></span>

<span data-ttu-id="4b4ab-145">U kunt een Microsoft Defender Offline-scan uitvoeren met de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="4b4ab-145">You can run a Microsoft Defender Offline scan with the following:</span></span>

- <span data-ttu-id="4b4ab-146">PowerShell</span><span class="sxs-lookup"><span data-stu-id="4b4ab-146">PowerShell</span></span>
- <span data-ttu-id="4b4ab-147">Windows Management Instrumentation (WMI)</span><span class="sxs-lookup"><span data-stu-id="4b4ab-147">Windows Management Instrumentation (WMI)</span></span>
- <span data-ttu-id="4b4ab-148">De Windows Security-app</span><span class="sxs-lookup"><span data-stu-id="4b4ab-148">The Windows Security app</span></span>



### <a name="use-powershell-cmdlets-to-run-an-offline-scan"></a><span data-ttu-id="4b4ab-149">PowerShell-cmdlets gebruiken om een offlinescan uit te voeren</span><span class="sxs-lookup"><span data-stu-id="4b4ab-149">Use PowerShell cmdlets to run an offline scan</span></span>

<span data-ttu-id="4b4ab-150">Gebruik de volgende cmdlets:</span><span class="sxs-lookup"><span data-stu-id="4b4ab-150">Use the following cmdlets:</span></span>

```PowerShell
Start-MpWDOScan
```

<span data-ttu-id="4b4ab-151">Zie [PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) gebruiken om Microsoft Defender Antivirus- en [Defender-cmdlets](/powershell/module/defender/) te configureren en uit te voeren voor meer informatie over het gebruik van PowerShell met Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="4b4ab-151">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-run-an-offline-scan"></a><span data-ttu-id="4b4ab-152">Windows Management Instruction (WMI) gebruiken om een offlinescan uit te voeren</span><span class="sxs-lookup"><span data-stu-id="4b4ab-152">Use Windows Management Instruction (WMI) to run an offline scan</span></span>

<span data-ttu-id="4b4ab-153">Gebruik de [**MSFT_MpWDOScan**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) om een offlinescan uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="4b4ab-153">Use the [**MSFT_MpWDOScan**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class to run an offline scan.</span></span>

<span data-ttu-id="4b4ab-154">In het volgende WMI-scriptfragment wordt onmiddellijk een Microsoft Defender Offline-scan uitgevoerd, waardoor het eindpunt opnieuw wordt gestart, de offlinescan wordt uitgevoerd en vervolgens opnieuw wordt gestart en opgestart in Windows.</span><span class="sxs-lookup"><span data-stu-id="4b4ab-154">The following WMI script snippet will immediately run a Microsoft Defender Offline scan, which will cause the endpoint to restart, run the offline scan, and then restart and boot into Windows.</span></span>

```console
wmic /namespace:\\root\Microsoft\Windows\Defender path MSFT_MpWDOScan call Start 
```

<span data-ttu-id="4b4ab-155">Zie het volgende voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="4b4ab-155">See the following for more information:</span></span>
- [<span data-ttu-id="4b4ab-156">Windows Defender WMIv2-API's</span><span class="sxs-lookup"><span data-stu-id="4b4ab-156">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


### <a name="use-the-windows-defender-security-app-to-run-an-offline-scan"></a><span data-ttu-id="4b4ab-157">De Windows Defender-beveiligingsapp gebruiken om een offlinescan uit te voeren</span><span class="sxs-lookup"><span data-stu-id="4b4ab-157">Use the Windows Defender Security app to run an offline scan</span></span>

1. <span data-ttu-id="4b4ab-158">Open de Windows Security-app door op het schildpictogram op de taakbalk te klikken of door te zoeken in het startmenu voor **Defender.**</span><span class="sxs-lookup"><span data-stu-id="4b4ab-158">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Defender**.</span></span>

2. <span data-ttu-id="4b4ab-159">Klik op **de tegel & virusbeveiliging** (of het schildpictogram op de linkermenubalk) en klik vervolgens op **het** label Geavanceerd scannen:</span><span class="sxs-lookup"><span data-stu-id="4b4ab-159">Click the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then the **Advanced scan** label:</span></span>
    
3. <span data-ttu-id="4b4ab-160">Selecteer **Microsoft Defender Offline scannen** en klik op Nu **scannen.**</span><span class="sxs-lookup"><span data-stu-id="4b4ab-160">Select **Microsoft Defender Offline scan** and click **Scan now**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4b4ab-161">In Windows 10, versie 1607, kan de offlinescan worden uitgevoerd onder **Windows Settings** Update & security Windows Defender of vanuit de  >    >   Windows Defender-client.</span><span class="sxs-lookup"><span data-stu-id="4b4ab-161">In Windows 10, version 1607, the offline scan could be run from under **Windows Settings** > **Update & security** > **Windows Defender** or from the Windows Defender client.</span></span>


## <a name="review-scan-results"></a><span data-ttu-id="4b4ab-162">Scanresultaten controleren</span><span class="sxs-lookup"><span data-stu-id="4b4ab-162">Review scan results</span></span>

<span data-ttu-id="4b4ab-163">Microsoft Defender Offline scanresultaten worden weergegeven in de [sectie Scangeschiedenis van de Windows Security-app.](microsoft-defender-security-center-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="4b4ab-163">Microsoft Defender Offline scan results will be listed in the [Scan history section of the Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span> 


## <a name="related-articles"></a><span data-ttu-id="4b4ab-164">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="4b4ab-164">Related articles</span></span>

- [<span data-ttu-id="4b4ab-165">De resultaten van scans en herstel aanpassen, starten en controleren</span><span class="sxs-lookup"><span data-stu-id="4b4ab-165">Customize, initiate, and review the results of scans and remediation</span></span>](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="4b4ab-166">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="4b4ab-166">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)