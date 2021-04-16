---
title: Scanopties configureren voor Microsoft Defender AV
description: U kunt Microsoft Defender AV zo configureren dat e-mailopslagbestanden, back-up- of herstelpunten, netwerkbestanden en gearchiveerde bestanden (zoals ZIP-bestanden) worden gescand.
keywords: geavanceerde scans, scannen, e-mail, archief, zip, rar, archief, herparseren scannen
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 72d5024446e56cc7fa1d94a7b9402cbe898db2a8
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764853"
---
# <a name="configure-microsoft-defender-antivirus-scanning-options"></a><span data-ttu-id="e8ce7-104">Microsoft Defender Antivirus-scanopties configureren</span><span class="sxs-lookup"><span data-stu-id="e8ce7-104">Configure Microsoft Defender Antivirus scanning options</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="e8ce7-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="e8ce7-105">**Applies to:**</span></span>

- [<span data-ttu-id="e8ce7-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="e8ce7-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

## <a name="use-microsoft-intune-to-configure-scanning-options"></a><span data-ttu-id="e8ce7-107">Microsoft Intune gebruiken om scanopties te configureren</span><span class="sxs-lookup"><span data-stu-id="e8ce7-107">Use Microsoft Intune to configure scanning options</span></span>

<span data-ttu-id="e8ce7-108">Zie [Instellingen voor apparaatbeperkingen configureren in Microsoft Intune](/intune/device-restrictions-configure) en Microsoft Defender Antivirus apparaatbeperkingen voor [Windows 10 in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="e8ce7-108">See [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure) and [Microsoft Defender Antivirus device restriction settings for Windows 10 in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) for more details.</span></span>

## <a name="use-microsoft-endpoint-manager-to-configure-scanning-options"></a><span data-ttu-id="e8ce7-109">Microsoft Endpoint Manager gebruiken om scanopties te configureren</span><span class="sxs-lookup"><span data-stu-id="e8ce7-109">Use Microsoft Endpoint Manager to configure scanning options</span></span>

<span data-ttu-id="e8ce7-110">Zie [Antimalware-beleid](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scan-settings) maken en implementeren: Scaninstellingen voor meer informatie over het configureren van Microsoft Endpoint Manager (huidige vertakking).</span><span class="sxs-lookup"><span data-stu-id="e8ce7-110">See [How to create and deploy antimalware policies: Scan settings](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scan-settings) for details on configuring Microsoft Endpoint Manager (current branch).</span></span>

## <a name="use-group-policy-to-configure-scanning-options"></a><span data-ttu-id="e8ce7-111">Groepsbeleid gebruiken om scanopties te configureren</span><span class="sxs-lookup"><span data-stu-id="e8ce7-111">Use Group Policy to configure scanning options</span></span>

<span data-ttu-id="e8ce7-112">De instellingen voor groepsbeleid configureren die in de volgende tabel worden beschreven:</span><span class="sxs-lookup"><span data-stu-id="e8ce7-112">To configure the Group Policy settings described in the following table:</span></span>

1. <span data-ttu-id="e8ce7-113">Open op de computer groepsbeleidsbeheer de console Groepsbeleidsbeheer, [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en klik op **Bewerken.**</span><span class="sxs-lookup"><span data-stu-id="e8ce7-113">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="e8ce7-114">Ga in **groepsbeleidseditor** naar **Computerconfiguratie** en klik op **Beheersjablonen.**</span><span class="sxs-lookup"><span data-stu-id="e8ce7-114">In the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="e8ce7-115">Vouw de structuur uit **naar Windows-onderdelen > Microsoft Defender Antivirus** en vervolgens de locatie die is opgegeven in de onderstaande tabel. </span><span class="sxs-lookup"><span data-stu-id="e8ce7-115">Expand the tree to **Windows components > Microsoft Defender Antivirus** and then the **Location** specified in the table below.</span></span>

4. <span data-ttu-id="e8ce7-116">Dubbelklik op de **beleidsinstelling** zoals aangegeven in de onderstaande tabel en stel de optie in op de gewenste configuratie.</span><span class="sxs-lookup"><span data-stu-id="e8ce7-116">Double-click the policy **Setting** as specified in the table below, and set the option to your desired configuration.</span></span> <span data-ttu-id="e8ce7-117">Klik **op OK** en herhaal dit voor andere instellingen.</span><span class="sxs-lookup"><span data-stu-id="e8ce7-117">Click **OK**, and repeat for any other settings.</span></span>

<span data-ttu-id="e8ce7-118">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="e8ce7-118">Description</span></span> | <span data-ttu-id="e8ce7-119">Locatie en instelling</span><span class="sxs-lookup"><span data-stu-id="e8ce7-119">Location and setting</span></span> | <span data-ttu-id="e8ce7-120">Standaardinstelling (indien niet geconfigureerd)</span><span class="sxs-lookup"><span data-stu-id="e8ce7-120">Default setting (if not configured)</span></span> | <span data-ttu-id="e8ce7-121">`Set-MpPreference`PowerShell-parameter of WMI-eigenschap voor `MSFT_MpPreference` klas</span><span class="sxs-lookup"><span data-stu-id="e8ce7-121">PowerShell `Set-MpPreference` parameter or WMI property for `MSFT_MpPreference` class</span></span>
---|---|---|---
<span data-ttu-id="e8ce7-122">E-mail scannen Zie [Beperkingen voor het scannen van e-mail](#ref1)</span><span class="sxs-lookup"><span data-stu-id="e8ce7-122">Email scanning See [Email scanning limitations](#ref1)</span></span>| <span data-ttu-id="e8ce7-123">Scannen > e-mail scannen in-</span><span class="sxs-lookup"><span data-stu-id="e8ce7-123">Scan > Turn on e-mail scanning</span></span> | <span data-ttu-id="e8ce7-124">Uitgeschakeld</span><span class="sxs-lookup"><span data-stu-id="e8ce7-124">Disabled</span></span> | `-DisableEmailScanning`
<span data-ttu-id="e8ce7-125">[Reparse-punten scannen](/windows/win32/fileio/reparse-points)</span><span class="sxs-lookup"><span data-stu-id="e8ce7-125">Scan [reparse points](/windows/win32/fileio/reparse-points)</span></span> | <span data-ttu-id="e8ce7-126">Scannen > Het scannen van reparse-punten in-</span><span class="sxs-lookup"><span data-stu-id="e8ce7-126">Scan > Turn on reparse point scanning</span></span> | <span data-ttu-id="e8ce7-127">Uitgeschakeld</span><span class="sxs-lookup"><span data-stu-id="e8ce7-127">Disabled</span></span> | <span data-ttu-id="e8ce7-128">Niet beschikbaar</span><span class="sxs-lookup"><span data-stu-id="e8ce7-128">Not available</span></span>
<span data-ttu-id="e8ce7-129">Netwerkstations scannen</span><span class="sxs-lookup"><span data-stu-id="e8ce7-129">Scan mapped network drives</span></span> | <span data-ttu-id="e8ce7-130">Scannen > Volledige scan uitvoeren op netwerkstations met kaart</span><span class="sxs-lookup"><span data-stu-id="e8ce7-130">Scan > Run full scan on mapped network drives</span></span> | <span data-ttu-id="e8ce7-131">Uitgeschakeld</span><span class="sxs-lookup"><span data-stu-id="e8ce7-131">Disabled</span></span> | `-DisableScanningMappedNetworkDrivesForFullScan`
 <span data-ttu-id="e8ce7-132">Archiefbestanden scannen (zoals ZIP- of .rar-bestanden).</span><span class="sxs-lookup"><span data-stu-id="e8ce7-132">Scan archive files (such as .zip or .rar files).</span></span> <span data-ttu-id="e8ce7-133">De [uitsluitingslijst voor extensies](configure-extension-file-exclusions-microsoft-defender-antivirus.md) heeft voorrang op deze instelling.</span><span class="sxs-lookup"><span data-stu-id="e8ce7-133">The [extensions exclusion list](configure-extension-file-exclusions-microsoft-defender-antivirus.md) will take precedence over this setting.</span></span> | <span data-ttu-id="e8ce7-134">Archiefbestanden > scannen</span><span class="sxs-lookup"><span data-stu-id="e8ce7-134">Scan > Scan archive files</span></span> | <span data-ttu-id="e8ce7-135">Ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="e8ce7-135">Enabled</span></span> | `-DisableArchiveScanning`
<span data-ttu-id="e8ce7-136">Bestanden in het netwerk scannen</span><span class="sxs-lookup"><span data-stu-id="e8ce7-136">Scan files on the network</span></span> | <span data-ttu-id="e8ce7-137">Netwerkbestanden > scannen</span><span class="sxs-lookup"><span data-stu-id="e8ce7-137">Scan > Scan network files</span></span> | <span data-ttu-id="e8ce7-138">Uitgeschakeld</span><span class="sxs-lookup"><span data-stu-id="e8ce7-138">Disabled</span></span> | `-DisableScanningNetworkFiles`
<span data-ttu-id="e8ce7-139">Scanpakket uitvoerbare bestanden</span><span class="sxs-lookup"><span data-stu-id="e8ce7-139">Scan packed executables</span></span> | <span data-ttu-id="e8ce7-140">Scan > scanpakket uitvoerbare bestanden</span><span class="sxs-lookup"><span data-stu-id="e8ce7-140">Scan > Scan packed executables</span></span> | <span data-ttu-id="e8ce7-141">Ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="e8ce7-141">Enabled</span></span> | <span data-ttu-id="e8ce7-142">Niet beschikbaar</span><span class="sxs-lookup"><span data-stu-id="e8ce7-142">Not available</span></span>
<span data-ttu-id="e8ce7-143">Verwisselbare stations alleen scannen tijdens volledige scans</span><span class="sxs-lookup"><span data-stu-id="e8ce7-143">Scan removable drives during full scans only</span></span> | <span data-ttu-id="e8ce7-144">Scan > Verwisselbare stations scannen</span><span class="sxs-lookup"><span data-stu-id="e8ce7-144">Scan > Scan removable drives</span></span> | <span data-ttu-id="e8ce7-145">Uitgeschakeld</span><span class="sxs-lookup"><span data-stu-id="e8ce7-145">Disabled</span></span> | `-DisableRemovableDriveScanning`
<span data-ttu-id="e8ce7-146">Het niveau opgeven van submappen in een archiefmap om te scannen</span><span class="sxs-lookup"><span data-stu-id="e8ce7-146">Specify the level of subfolders within an archive folder to scan</span></span> | <span data-ttu-id="e8ce7-147">Scannen > De maximale diepte opgeven voor het scannen van archiefbestanden</span><span class="sxs-lookup"><span data-stu-id="e8ce7-147">Scan > Specify the maximum depth to scan archive files</span></span> | <span data-ttu-id="e8ce7-148">0</span><span class="sxs-lookup"><span data-stu-id="e8ce7-148">0</span></span> | <span data-ttu-id="e8ce7-149">Niet beschikbaar</span><span class="sxs-lookup"><span data-stu-id="e8ce7-149">Not available</span></span>
 <span data-ttu-id="e8ce7-150">Geef de maximale CPU-belasting (als percentage) op tijdens een scan.</span><span class="sxs-lookup"><span data-stu-id="e8ce7-150">Specify the maximum CPU load (as a percentage) during a scan.</span></span> <span data-ttu-id="e8ce7-151">Opmerking: Dit is geen harde limiet, maar een richtlijn voor de scan-engine om dit maximum gemiddeld niet te overschrijden.</span><span class="sxs-lookup"><span data-stu-id="e8ce7-151">Note: This is not a hard limit but rather a guidance for the scanning engine to not exceed this maximum on average.</span></span> | <span data-ttu-id="e8ce7-152">Scan > Het maximale percentage cpu-gebruik opgeven tijdens een scan</span><span class="sxs-lookup"><span data-stu-id="e8ce7-152">Scan > Specify the maximum percentage of CPU utilization during a scan</span></span> | <span data-ttu-id="e8ce7-153">50</span><span class="sxs-lookup"><span data-stu-id="e8ce7-153">50</span></span> |  `-ScanAvgCPULoadFactor`
 <span data-ttu-id="e8ce7-154">Geef de maximale grootte (in kilobytes) op van archiefbestanden die moeten worden gescand.</span><span class="sxs-lookup"><span data-stu-id="e8ce7-154">Specify the maximum size (in kilobytes) of archive files that should be scanned.</span></span> <span data-ttu-id="e8ce7-155">De **standaardwaarde, 0,** geldt geen limiet</span><span class="sxs-lookup"><span data-stu-id="e8ce7-155">The default, **0**, applies no limit</span></span> | <span data-ttu-id="e8ce7-156">Scannen > De maximale grootte opgeven van archiefbestanden die moeten worden gescand</span><span class="sxs-lookup"><span data-stu-id="e8ce7-156">Scan > Specify the maximum size of archive files to be scanned</span></span> | <span data-ttu-id="e8ce7-157">Geen limiet</span><span class="sxs-lookup"><span data-stu-id="e8ce7-157">No limit</span></span> | <span data-ttu-id="e8ce7-158">Niet beschikbaar</span><span class="sxs-lookup"><span data-stu-id="e8ce7-158">Not available</span></span>
 <span data-ttu-id="e8ce7-159">Lage CPU-prioriteit configureren voor geplande scans</span><span class="sxs-lookup"><span data-stu-id="e8ce7-159">Configure low CPU priority for scheduled scans</span></span> | <span data-ttu-id="e8ce7-160">Scan > Lage CPU-prioriteit configureren voor geplande scans</span><span class="sxs-lookup"><span data-stu-id="e8ce7-160">Scan > Configure low CPU priority for scheduled scans</span></span> | <span data-ttu-id="e8ce7-161">Uitgeschakeld</span><span class="sxs-lookup"><span data-stu-id="e8ce7-161">Disabled</span></span> | <span data-ttu-id="e8ce7-162">Niet beschikbaar</span><span class="sxs-lookup"><span data-stu-id="e8ce7-162">Not available</span></span>
 
> [!NOTE]
> <span data-ttu-id="e8ce7-163">Als realtimebeveiliging is ingeschakeld, worden bestanden gescand voordat ze worden toegankelijk en uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="e8ce7-163">If real-time protection is turned on, files are scanned before they are accessed and executed.</span></span> <span data-ttu-id="e8ce7-164">Het scanbereik bevat alle bestanden, inclusief bestanden op opgeslagen verwisselbare media, zoals USB-stations.</span><span class="sxs-lookup"><span data-stu-id="e8ce7-164">The scanning scope includes all files, including files on mounted removable media, such as USB drives.</span></span> <span data-ttu-id="e8ce7-165">Als het apparaat dat de scan voert realtimebeveiliging of on-access-beveiliging heeft ingeschakeld, bevat de scan ook netwerkaandelen.</span><span class="sxs-lookup"><span data-stu-id="e8ce7-165">If the device performing the scan has real-time protection or on-access protection turned on, the scan will also include network shares.</span></span>

## <a name="use-powershell-to-configure-scanning-options"></a><span data-ttu-id="e8ce7-166">PowerShell gebruiken om scanopties te configureren</span><span class="sxs-lookup"><span data-stu-id="e8ce7-166">Use PowerShell to configure scanning options</span></span>

<span data-ttu-id="e8ce7-167">Zie [Microsoft Defender Antivirus beheren met PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) en [Defender-cmdlets](/powershell/module/defender/) voor meer informatie over het gebruik van PowerShell met Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="e8ce7-167">See [Manage Microsoft Defender Antivirus with PowerShell cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

## <a name="use-wmi-to-configure-scanning-options"></a><span data-ttu-id="e8ce7-168">WMI gebruiken om scanopties te configureren</span><span class="sxs-lookup"><span data-stu-id="e8ce7-168">Use WMI to configure scanning options</span></span>

<span data-ttu-id="e8ce7-169">Zie Windows [Defender WMIv2 API's](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)voor het gebruik van WMI-klassen.</span><span class="sxs-lookup"><span data-stu-id="e8ce7-169">For using WMI classes, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

<a id="ref1"></a>

## <a name="email-scanning-limitations"></a><span data-ttu-id="e8ce7-170">Beperkingen voor het scannen van e-mail</span><span class="sxs-lookup"><span data-stu-id="e8ce7-170">Email scanning limitations</span></span>

<span data-ttu-id="e8ce7-171">Met e-mail scannen kunt u e-mailbestanden scannen die door Outlook en andere e-mail clients worden gebruikt tijdens scans op aanvraag en geplande scans.</span><span class="sxs-lookup"><span data-stu-id="e8ce7-171">Email scanning enables scanning of  email files used by Outlook and other mail clients during on-demand and scheduled scans.</span></span> <span data-ttu-id="e8ce7-172">Ingesloten objecten in een e-mailbestand (zoals bijlagen en gearchiveerde bestanden) worden ook gescand.</span><span class="sxs-lookup"><span data-stu-id="e8ce7-172">Embedded objects within an email file (such as attachments and archived files) are also scanned.</span></span> <span data-ttu-id="e8ce7-173">De volgende bestandsindelingstypen kunnen worden gescand en gesaneerd:</span><span class="sxs-lookup"><span data-stu-id="e8ce7-173">The following file format types can be scanned and remediated:</span></span>

- <span data-ttu-id="e8ce7-174">DBX</span><span class="sxs-lookup"><span data-stu-id="e8ce7-174">DBX</span></span>
- <span data-ttu-id="e8ce7-175">MBX</span><span class="sxs-lookup"><span data-stu-id="e8ce7-175">MBX</span></span>
- <span data-ttu-id="e8ce7-176">MIME</span><span class="sxs-lookup"><span data-stu-id="e8ce7-176">MIME</span></span>

<span data-ttu-id="e8ce7-177">PST-bestanden die worden gebruikt door Outlook 2003 of ouder (waarbij het archieftype is ingesteld op niet-unicode) worden ook gescand, maar Windows Defender kan geen bedreigingen herstellen die zijn gedetecteerd in PST-bestanden.</span><span class="sxs-lookup"><span data-stu-id="e8ce7-177">PST files used by Outlook 2003 or older (where the archive type is set to non-unicode) will also be scanned, but Windows Defender cannot remediate threats detected inside PST files.</span></span>

<span data-ttu-id="e8ce7-178">Als Microsoft Defender Antivirus een bedreiging in een e-mail detecteert, worden de volgende gegevens aan u gegeven om u te helpen bij het identificeren van de gecompromitteerde e-mail, zodat u de bedreiging handmatig kunt herstellen:</span><span class="sxs-lookup"><span data-stu-id="e8ce7-178">If Microsoft Defender Antivirus detects a threat inside an email, it will show you the following information to assist you in identifying the compromised email, so you can remediate the threat manually:</span></span>

- <span data-ttu-id="e8ce7-179">E-mail onderwerp</span><span class="sxs-lookup"><span data-stu-id="e8ce7-179">Email subject</span></span>
- <span data-ttu-id="e8ce7-180">Naam van bijlage</span><span class="sxs-lookup"><span data-stu-id="e8ce7-180">Attachment name</span></span>

## <a name="related-topics"></a><span data-ttu-id="e8ce7-181">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="e8ce7-181">Related topics</span></span>

- [<span data-ttu-id="e8ce7-182">De resultaten van Microsoft Defender Antivirus scans en herstel aanpassen, starten en controleren</span><span class="sxs-lookup"><span data-stu-id="e8ce7-182">Customize, initiate, and review the results of Microsoft Defender Antivirus scans and remediation</span></span>](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="e8ce7-183">Microsoft Defender Antivirus-scans op aanvraag configureren en uitvoeren</span><span class="sxs-lookup"><span data-stu-id="e8ce7-183">Configure and run on-demand Microsoft Defender Antivirus scans</span></span>](run-scan-microsoft-defender-antivirus.md)
- [<span data-ttu-id="e8ce7-184">Geplande Microsoft Defender Antivirus-scans configureren</span><span class="sxs-lookup"><span data-stu-id="e8ce7-184">Configure scheduled Microsoft Defender Antivirus scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="e8ce7-185">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="e8ce7-185">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)