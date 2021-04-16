---
title: Implementatiehandleiding voor Microsoft Defender Antivirus Virtual Desktop Infrastructure
description: Lees hoe u Microsoft Defender Antivirus implementeert in een virtuele bureaubladomgeving voor de beste balans tussen beveiliging en prestaties.
keywords: vdi, hyper-v, vm, virtual machine, windows defender, antivirus, av, virtual desktop, rds, remote desktop
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 12/28/2020
ms.reviewer: jesquive
manager: dansimp
ms.technology: mde
ms.openlocfilehash: fed66586dc0607989e407ecd790d2af8c40e2939
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765729"
---
# <a name="deployment-guide-for-microsoft-defender-antivirus-in-a-virtual-desktop-infrastructure-vdi-environment"></a><span data-ttu-id="71633-104">Implementatiehandleiding voor Microsoft Defender Antivirus in een VDI-omgeving (Virtual Desktop Infrastructure)</span><span class="sxs-lookup"><span data-stu-id="71633-104">Deployment guide for Microsoft Defender Antivirus in a virtual desktop infrastructure (VDI) environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="71633-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="71633-105">**Applies to:**</span></span>

- [<span data-ttu-id="71633-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="71633-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="71633-107">Naast standaard on-premises of hardwareconfiguraties kunt u ook Microsoft Defender Antivirus gebruiken in een extern bureaublad (RDS) of VDI-omgeving (Virtual Desktop Infrastructure).</span><span class="sxs-lookup"><span data-stu-id="71633-107">In addition to standard on-premises or hardware configurations, you can also use Microsoft Defender Antivirus in a remote desktop (RDS) or virtual desktop infrastructure (VDI) environment.</span></span>

<span data-ttu-id="71633-108">Zie [Documentatie over Windows Virtual Desktop voor](/azure/virtual-desktop) meer informatie over Microsoft Remote Desktop Services en VDI-ondersteuning.</span><span class="sxs-lookup"><span data-stu-id="71633-108">See [Windows Virtual Desktop Documentation](/azure/virtual-desktop) for more details on Microsoft Remote Desktop Services and VDI support.</span></span>

<span data-ttu-id="71633-109">Zie [Endpoint Protection](/azure/security-center/security-center-install-endpoint-protection)installeren in Azure Defender voor virtuele azure-machines.</span><span class="sxs-lookup"><span data-stu-id="71633-109">For Azure-based virtual machines, see [Install Endpoint Protection in Azure Defender](/azure/security-center/security-center-install-endpoint-protection).</span></span>

<span data-ttu-id="71633-110">Met de mogelijkheid om eenvoudig updates te implementeren voor VM's die worden uitgevoerd in VDI's, hebben we deze handleiding ingekort om ons te concentreren op hoe u snel en eenvoudig updates op uw machines kunt krijgen.</span><span class="sxs-lookup"><span data-stu-id="71633-110">With the ability to easily deploy updates to VMs running in VDIs, we've shortened this guide to focus on how you can get updates on your machines quickly and easily.</span></span> <span data-ttu-id="71633-111">U hoeft geen gouden afbeeldingen meer periodiek te maken en te verzegelen, aangezien updates worden uitgebreid naar de onderdelen op de hostserver en vervolgens rechtstreeks naar de VM worden gedownload wanneer deze is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="71633-111">You no longer need to create and seal golden images on a periodic basis, as updates are expanded into their component bits on the host server and then downloaded directly to the VM when it's turned on.</span></span>

<span data-ttu-id="71633-112">In deze handleiding wordt beschreven hoe u uw VM's kunt configureren voor optimale beveiliging en prestaties, inclusief het volgende:</span><span class="sxs-lookup"><span data-stu-id="71633-112">This guide describes how to configure your VMs for optimal protection and performance, including how to:</span></span>

- [<span data-ttu-id="71633-113">Een speciale VDI-bestands delen instellen voor beveiligingsinformatieupdates</span><span class="sxs-lookup"><span data-stu-id="71633-113">Set up a dedicated VDI file share for security intelligence updates</span></span>](#set-up-a-dedicated-vdi-file-share)
- [<span data-ttu-id="71633-114">Geplande scans willekeurig maken</span><span class="sxs-lookup"><span data-stu-id="71633-114">Randomize scheduled scans</span></span>](#randomize-scheduled-scans)
- [<span data-ttu-id="71633-115">Snelle scans gebruiken</span><span class="sxs-lookup"><span data-stu-id="71633-115">Use quick scans</span></span>](#use-quick-scans)
- [<span data-ttu-id="71633-116">Meldingen voorkomen</span><span class="sxs-lookup"><span data-stu-id="71633-116">Prevent notifications</span></span>](#prevent-notifications)
- [<span data-ttu-id="71633-117">Scans uitschakelen na elke update</span><span class="sxs-lookup"><span data-stu-id="71633-117">Disable scans from occurring after every update</span></span>](#disable-scans-after-an-update)
- [<span data-ttu-id="71633-118">Verouderd machines of machines scannen die al een tijdje offline zijn</span><span class="sxs-lookup"><span data-stu-id="71633-118">Scan out-of-date machines or machines that have been offline for a while</span></span>](#scan-vms-that-have-been-offline)
- [<span data-ttu-id="71633-119">Uitsluitingen toepassen</span><span class="sxs-lookup"><span data-stu-id="71633-119">Apply exclusions</span></span>](#exclusions)

<span data-ttu-id="71633-120">U kunt ook het whitepaper [Microsoft Defender Antivirus](https://demo.wd.microsoft.com/Content/wdav-testing-vdi-ssu.pdf)downloaden op virtual desktop-infrastructuur, waarin wordt ge kijkt naar de nieuwe functie voor het bijwerken van gedeelde beveiligingsinformatie, naast prestatietests en richtlijnen voor het testen van antivirusprestaties op uw eigen VDI.</span><span class="sxs-lookup"><span data-stu-id="71633-120">You can also download the whitepaper [Microsoft Defender Antivirus on Virtual Desktop Infrastructure](https://demo.wd.microsoft.com/Content/wdav-testing-vdi-ssu.pdf), which looks at the new shared security intelligence update feature, alongside performance testing and guidance on how you can test antivirus performance on your own VDI.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="71633-121">Hoewel VDI kan worden gehost op Windows Server 2012 of Windows Server 2016, moeten op de virtuele machines (VM's) minimaal Windows 10, 1607 worden uitgevoerd vanwege verbeterde beveiligingstechnologieën en -functies die niet beschikbaar zijn in eerdere versies van Windows.</span><span class="sxs-lookup"><span data-stu-id="71633-121">Although the VDI can be hosted on Windows Server 2012 or Windows Server 2016, the virtual machines (VMs) should be running Windows 10, 1607 at a minimum, due to increased protection technologies and features that are unavailable in earlier versions of Windows.</span></span><br/><span data-ttu-id="71633-122">Er zijn prestatie- en functieverbeteringen in de manier waarop Microsoft Defender AV werkt op virtuele machines in Windows 10 Insider Preview, build 18323 (en hoger).</span><span class="sxs-lookup"><span data-stu-id="71633-122">There are performance and feature improvements to the way in which Microsoft Defender AV operates on virtual machines in Windows 10 Insider Preview, build 18323 (and later).</span></span> <span data-ttu-id="71633-123">We identificeren in deze handleiding of u een Insider Preview-build wilt gebruiken. als dit niet is opgegeven, is Windows 10 1607 de minimaal vereiste versie voor de beste beveiliging en prestaties.</span><span class="sxs-lookup"><span data-stu-id="71633-123">We'll identify in this guide if you need to be using an Insider Preview build; if it isn't specified, then the minimum required version for the best protection and performance is Windows 10 1607.</span></span>

## <a name="set-up-a-dedicated-vdi-file-share"></a><span data-ttu-id="71633-124">Een speciale VDI-bestands delen instellen</span><span class="sxs-lookup"><span data-stu-id="71633-124">Set up a dedicated VDI file share</span></span>

<span data-ttu-id="71633-125">In Windows 10, versie 1903, hebben we de functie voor gedeelde beveiligingsinformatie geïntroduceerd, waarmee het uitpakken van gedownloade beveiligingsintelligentie-updates wordt uitgeschakeld op een hostmachine, waardoor eerdere CPU-, schijf- en geheugenresources op afzonderlijke machines worden opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="71633-125">In Windows 10, version 1903, we introduced the shared security intelligence feature, which offloads the unpackaging of downloaded security intelligence updates onto a host machine—thus saving previous CPU, disk, and memory resources on individual machines.</span></span> <span data-ttu-id="71633-126">Deze functie is backported en werkt nu in Windows 10 versie 1703 en hoger.</span><span class="sxs-lookup"><span data-stu-id="71633-126">This feature has been backported and now works in Windows 10 version 1703 and above.</span></span> <span data-ttu-id="71633-127">U kunt deze functie instellen met een groepsbeleid of PowerShell.</span><span class="sxs-lookup"><span data-stu-id="71633-127">You can set this feature with a Group Policy, or PowerShell.</span></span>

### <a name="use-group-policy-to-enable-the-shared-security-intelligence-feature"></a><span data-ttu-id="71633-128">Groepsbeleid gebruiken om de functie voor gedeelde beveiligingsinformatie in te stellen:</span><span class="sxs-lookup"><span data-stu-id="71633-128">Use Group Policy to enable the shared security intelligence feature:</span></span>

1. <span data-ttu-id="71633-129">Open op de computer groepsbeleidsbeheer de console Groepsbeleidsbeheer, klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en klik vervolgens op **Bewerken.**</span><span class="sxs-lookup"><span data-stu-id="71633-129">On your Group Policy management computer, open the Group Policy Management Console, right-click the Group Policy Object you want to configure, and then click **Edit**.</span></span>

2. <span data-ttu-id="71633-130">Ga in **de Editor voor groepsbeleidsbeheer** naar **Computerconfiguratie.**</span><span class="sxs-lookup"><span data-stu-id="71633-130">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="71633-131">Klik **op Beheersjablonen.**</span><span class="sxs-lookup"><span data-stu-id="71633-131">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="71633-132">Vouw de structuur uit naar **Windows-onderdelen**  >  **Microsoft Defender Antivirus** Security Intelligence  >  **Updates**.</span><span class="sxs-lookup"><span data-stu-id="71633-132">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Security Intelligence Updates**.</span></span>

5. <span data-ttu-id="71633-133">Dubbelklik op **Locatie voor beveiligingsinformatie definiëren voor VDI-clients** en stel de optie in op **Ingeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="71633-133">Double-click **Define security intelligence location for VDI clients**, and then set the option to **Enabled**.</span></span> <span data-ttu-id="71633-134">Er wordt automatisch een veld weergegeven.</span><span class="sxs-lookup"><span data-stu-id="71633-134">A field automatically appears.</span></span>

6. <span data-ttu-id="71633-135">Enter (zie Downloaden en uitpakken voor hulp bij `\\<sharedlocation\>\wdav-update` [deze waarde).](#download-and-unpackage-the-latest-updates)</span><span class="sxs-lookup"><span data-stu-id="71633-135">Enter `\\<sharedlocation\>\wdav-update` (for help with this value, see [Download and unpackage](#download-and-unpackage-the-latest-updates)).</span></span>

7. <span data-ttu-id="71633-136">Klik op **OK**.</span><span class="sxs-lookup"><span data-stu-id="71633-136">Click **OK**.</span></span>

8. <span data-ttu-id="71633-137">Implementeer het GPO naar de VM's die u wilt testen.</span><span class="sxs-lookup"><span data-stu-id="71633-137">Deploy the GPO to the VMs you want to test.</span></span>

### <a name="use-powershell-to-enable-the-shared-security-intelligence-feature"></a><span data-ttu-id="71633-138">PowerShell gebruiken om de functie voor gedeelde beveiligingsinformatie in te stellen</span><span class="sxs-lookup"><span data-stu-id="71633-138">Use PowerShell to enable the shared security intelligence feature</span></span>

<span data-ttu-id="71633-139">Gebruik de volgende cmdlet om de functie in te stellen.</span><span class="sxs-lookup"><span data-stu-id="71633-139">Use the following cmdlet to enable the feature.</span></span> <span data-ttu-id="71633-140">U moet dit vervolgens pushen omdat u normaal gesproken configuratiebeleid op basis van PowerShell naar de VM's zou pushen:</span><span class="sxs-lookup"><span data-stu-id="71633-140">You’ll need to then push this as you normally would push PowerShell-based configuration policies onto the VMs:</span></span>

```PowerShell
Set-MpPreference -SharedSignaturesPath \\<shared location>\wdav-update
```

<span data-ttu-id="71633-141">Zie de [sectie Downloaden en uitpakken](#download-and-unpackage-the-latest-updates) voor wat \<shared location\> het wordt.</span><span class="sxs-lookup"><span data-stu-id="71633-141">See the [Download and unpackage](#download-and-unpackage-the-latest-updates) section for what the \<shared location\> will be.</span></span>

## <a name="download-and-unpackage-the-latest-updates"></a><span data-ttu-id="71633-142">De nieuwste updates downloaden en uitpakken</span><span class="sxs-lookup"><span data-stu-id="71633-142">Download and unpackage the latest updates</span></span>

<span data-ttu-id="71633-143">Nu kunt u aan de slag met het downloaden en installeren van nieuwe updates.</span><span class="sxs-lookup"><span data-stu-id="71633-143">Now you can get started on downloading and installing new updates.</span></span> <span data-ttu-id="71633-144">Hieronder hebben we een voorbeeldscript voor PowerShell voor u gemaakt.</span><span class="sxs-lookup"><span data-stu-id="71633-144">We’ve created a sample PowerShell script for you below.</span></span> <span data-ttu-id="71633-145">Dit script is de eenvoudigste manier om nieuwe updates te downloaden en ze klaar te maken voor uw VM's.</span><span class="sxs-lookup"><span data-stu-id="71633-145">This script is the easiest way to download new updates and get them ready for your VMs.</span></span> <span data-ttu-id="71633-146">Vervolgens moet u instellen dat het script op een bepaald moment op de beheermachine wordt uitgevoerd met behulp van een geplande taak (of, als u bekend bent met het gebruik van PowerShell-scripts in Azure, Intune of SCCM, kunt u deze scripts ook gebruiken).</span><span class="sxs-lookup"><span data-stu-id="71633-146">You should then set the script to run at a certain time on the management machine by using a scheduled task (or, if you’re familiar with using PowerShell scripts in Azure, Intune, or SCCM, you could also use those scripts).</span></span>

```PowerShell
$vdmpathbase = "$env:systemdrive\wdav-update\{00000000-0000-0000-0000-"
$vdmpathtime = Get-Date -format "yMMddHHmmss"
$vdmpath = $vdmpathbase + $vdmpathtime + '}'
$vdmpackage = $vdmpath + '\mpam-fe.exe'

New-Item -ItemType Directory -Force -Path $vdmpath | Out-Null

Invoke-WebRequest -Uri 'https://go.microsoft.com/fwlink/?LinkID=121721&arch=x64' -OutFile $vdmpackage

cmd /c "cd $vdmpath & c: & mpam-fe.exe /x"
```

<span data-ttu-id="71633-147">U kunt instellen dat een geplande taak eenmaal per dag wordt uitgevoerd, zodat wanneer het pakket wordt gedownload en uitgepakt, de VM's de nieuwe update ontvangen.</span><span class="sxs-lookup"><span data-stu-id="71633-147">You can set a scheduled task to run once a day so that whenever the package is downloaded and unpacked then the VMs will receive the new update.</span></span> <span data-ttu-id="71633-148">We raden u aan om één keer per dag te beginnen, maar u moet experimenteren met het verhogen of verlagen van de frequentie om de impact te begrijpen.</span><span class="sxs-lookup"><span data-stu-id="71633-148">We suggest starting with once a day—but you should experiment with increasing or decreasing the frequency to understand the impact.</span></span> 

<span data-ttu-id="71633-149">Beveiligingsinformatiepakketten worden meestal eenmaal per drie tot vier uur gepubliceerd.</span><span class="sxs-lookup"><span data-stu-id="71633-149">Security intelligence packages are typically published once every three to four hours.</span></span> <span data-ttu-id="71633-150">Het is niet raadzaam een frequentie in te stellen die korter is dan vier uur, omdat hierdoor de overhead van het netwerk op uw beheerapparaat zonder voordeel wordt vergroot.</span><span class="sxs-lookup"><span data-stu-id="71633-150">Setting a frequency shorter than four hours isn’t advised because it will increase the network overhead on your management machine for no benefit.</span></span>

### <a name="set-a-scheduled-task-to-run-the-powershell-script"></a><span data-ttu-id="71633-151">Een geplande taak instellen om het PowerShell-script uit te voeren</span><span class="sxs-lookup"><span data-stu-id="71633-151">Set a scheduled task to run the PowerShell script</span></span>

1. <span data-ttu-id="71633-152">Open op de beheermachine het menu Start en typ **Taakplanning.**</span><span class="sxs-lookup"><span data-stu-id="71633-152">On the management machine, open the Start menu and type **Task Scheduler**.</span></span> <span data-ttu-id="71633-153">Open deze en selecteer **Taak maken...**</span><span class="sxs-lookup"><span data-stu-id="71633-153">Open it and select **Create task…**</span></span> <span data-ttu-id="71633-154">op het zijpaneel.</span><span class="sxs-lookup"><span data-stu-id="71633-154">on the side panel.</span></span>

2. <span data-ttu-id="71633-155">Voer de naam in als **Beveiligingsinformatie-uitpakken.**</span><span class="sxs-lookup"><span data-stu-id="71633-155">Enter the name as **Security intelligence unpacker**.</span></span> <span data-ttu-id="71633-156">Ga naar het **tabblad Trigger.** Selecteer **Nieuw...**</span><span class="sxs-lookup"><span data-stu-id="71633-156">Go to the **Trigger** tab. Select **New…**</span></span><span data-ttu-id="71633-157"> > **Dagelijks** en selecteer **OK.**</span><span class="sxs-lookup"><span data-stu-id="71633-157"> > **Daily**, and select **OK**.</span></span>

3. <span data-ttu-id="71633-158">Ga naar het **tabblad** Acties. Selecteer **Nieuw...**</span><span class="sxs-lookup"><span data-stu-id="71633-158">Go to the **Actions** tab. Select **New…**</span></span> <span data-ttu-id="71633-159">Voer **PowerShell** in het **veld Programma/script** in.</span><span class="sxs-lookup"><span data-stu-id="71633-159">Enter **PowerShell** in the **Program/Script** field.</span></span> <span data-ttu-id="71633-160">Voer `-ExecutionPolicy Bypass c:\wdav-update\vdmdlunpack.ps1` in het veld Argumenten **toevoegen** in.</span><span class="sxs-lookup"><span data-stu-id="71633-160">Enter `-ExecutionPolicy Bypass c:\wdav-update\vdmdlunpack.ps1` in the **Add arguments** field.</span></span> <span data-ttu-id="71633-161">Kies **OK**.</span><span class="sxs-lookup"><span data-stu-id="71633-161">Select **OK**.</span></span>

4. <span data-ttu-id="71633-162">U kunt er indien nodig voor kiezen om extra instellingen te configureren.</span><span class="sxs-lookup"><span data-stu-id="71633-162">You can choose to configure additional settings if you wish.</span></span>

5. <span data-ttu-id="71633-163">Selecteer **OK** om de geplande taak op te slaan.</span><span class="sxs-lookup"><span data-stu-id="71633-163">Select **OK** to save the scheduled task.</span></span>
 
<span data-ttu-id="71633-164">U kunt de update handmatig starten door met de rechtermuisknop op de taak te klikken en op **Uitvoeren te klikken.**</span><span class="sxs-lookup"><span data-stu-id="71633-164">You can initiate the update manually by right-clicking on the task and clicking **Run**.</span></span>

### <a name="download-and-unpackage-manually"></a><span data-ttu-id="71633-165">Handmatig downloaden en uitpakken</span><span class="sxs-lookup"><span data-stu-id="71633-165">Download and unpackage manually</span></span>

<span data-ttu-id="71633-166">Als u alles liever handmatig wilt doen, gaat u als volgende te werk om het gedrag van het script te repliceren:</span><span class="sxs-lookup"><span data-stu-id="71633-166">If you would prefer to do everything manually, here's what to do to replicate the script’s behavior:</span></span>

1. <span data-ttu-id="71633-167">Maak een nieuwe map in de systeemwortel die wordt genoemd om intelligence-updates op te `wdav_update` slaan, bijvoorbeeld om de map te `c:\wdav_update` maken.</span><span class="sxs-lookup"><span data-stu-id="71633-167">Create a new folder on the system root called `wdav_update` to store intelligence updates, for example, create the folder `c:\wdav_update`.</span></span>

2. <span data-ttu-id="71633-168">Een submap maken onder *wdav_update* met een GUID-naam, zoals `{00000000-0000-0000-0000-000000000000}`</span><span class="sxs-lookup"><span data-stu-id="71633-168">Create a subfolder under *wdav_update* with a GUID name, such as `{00000000-0000-0000-0000-000000000000}`</span></span>

<span data-ttu-id="71633-169">Hier is een voorbeeld: `c:\wdav_update\{00000000-0000-0000-0000-000000000000}`</span><span class="sxs-lookup"><span data-stu-id="71633-169">Here's an example: `c:\wdav_update\{00000000-0000-0000-0000-000000000000}`</span></span>

   > [!NOTE]
   > <span data-ttu-id="71633-170">In het script hebben we het zo ingesteld dat de laatste 12 cijfers van de GUID het jaar, de maand, de dag en de tijd zijn waarop het bestand is gedownload, zodat er telkens een nieuwe map wordt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="71633-170">In the script we set it so the last 12 digits of the GUID are the year, month, day, and time when the file was downloaded so that a new folder is created each time.</span></span> <span data-ttu-id="71633-171">U kunt dit wijzigen zodat het bestand telkens naar dezelfde map wordt gedownload.</span><span class="sxs-lookup"><span data-stu-id="71633-171">You can change this so that the file is downloaded to the same folder each time.</span></span>

3. <span data-ttu-id="71633-172">Download een beveiligingsinformatiepakket [https://www.microsoft.com/wdsi/definitions](https://www.microsoft.com/wdsi/definitions)  in de map GUID.</span><span class="sxs-lookup"><span data-stu-id="71633-172">Download a security intelligence package from [https://www.microsoft.com/wdsi/definitions](https://www.microsoft.com/wdsi/definitions)  into the GUID folder.</span></span> <span data-ttu-id="71633-173">Het bestand moet een naam `mpam-fe.exe` hebben.</span><span class="sxs-lookup"><span data-stu-id="71633-173">The file should be named `mpam-fe.exe`.</span></span>

4. <span data-ttu-id="71633-174">Open een cmd-promptvenster en ga naar de MAP GUID die u hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="71633-174">Open a cmd prompt window and navigate to the GUID folder you created.</span></span> <span data-ttu-id="71633-175">Gebruik bijvoorbeeld **de opdracht /X-extractie** om de bestanden op te `mpam-fe.exe /X` halen.</span><span class="sxs-lookup"><span data-stu-id="71633-175">Use the **/X** extraction command to extract the files, for example `mpam-fe.exe /X`.</span></span>

   > [!NOTE]
   > <span data-ttu-id="71633-176">De VM's nemen het bijgewerkte pakket op wanneer een nieuwe GUID-map wordt gemaakt met een uitgepakt updatepakket of wanneer een bestaande map wordt bijgewerkt met een nieuw uitgepakt pakket.</span><span class="sxs-lookup"><span data-stu-id="71633-176">The VMs will pick up the updated package whenever a new GUID folder is created with an extracted update package or whenever an existing folder is updated with a new extracted package.</span></span>

## <a name="randomize-scheduled-scans"></a><span data-ttu-id="71633-177">Geplande scans willekeurig maken</span><span class="sxs-lookup"><span data-stu-id="71633-177">Randomize scheduled scans</span></span>

<span data-ttu-id="71633-178">Geplande scans worden uitgevoerd naast [realtime beveiliging en scannen.](configure-real-time-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="71633-178">Scheduled scans run in addition to [real-time protection and scanning](configure-real-time-protection-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="71633-179">De begintijd van de scan zelf is nog steeds gebaseerd op het geplande scanbeleid **(ScheduleDay,** **ScheduleTime** en **ScheduleQuickScanTime).**</span><span class="sxs-lookup"><span data-stu-id="71633-179">The start time of the scan itself is still based on the scheduled scan policy (**ScheduleDay**, **ScheduleTime**, and **ScheduleQuickScanTime**).</span></span> <span data-ttu-id="71633-180">Randomization will cause Microsoft Defender Antivirus to start a scan on each machine within a 4 hour window from the time set for the scheduled scan.</span><span class="sxs-lookup"><span data-stu-id="71633-180">Randomization will cause Microsoft Defender Antivirus to start a scan on each machine within a 4-hour window from the time set for the scheduled scan.</span></span>

<span data-ttu-id="71633-181">Zie [Scans plannen](scheduled-catch-up-scans-microsoft-defender-antivirus.md) voor andere configuratieopties die beschikbaar zijn voor geplande scans.</span><span class="sxs-lookup"><span data-stu-id="71633-181">See [Schedule scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md) for other configuration options available for scheduled scans.</span></span>

## <a name="use-quick-scans"></a><span data-ttu-id="71633-182">Snelle scans gebruiken</span><span class="sxs-lookup"><span data-stu-id="71633-182">Use quick scans</span></span>

<span data-ttu-id="71633-183">U kunt het type scan opgeven dat moet worden uitgevoerd tijdens een geplande scan.</span><span class="sxs-lookup"><span data-stu-id="71633-183">You can specify the type of scan that should be performed during a scheduled scan.</span></span> <span data-ttu-id="71633-184">Snelle scans zijn de voorkeursbenadering omdat ze zijn ontworpen om te zoeken op alle plaatsen waar malware moet staan om actief te zijn.</span><span class="sxs-lookup"><span data-stu-id="71633-184">Quick scans are the preferred approach as they are designed to look in all places where malware needs to reside to be active.</span></span> <span data-ttu-id="71633-185">In de volgende procedure wordt beschreven hoe u snelle scans kunt instellen met groepsbeleid.</span><span class="sxs-lookup"><span data-stu-id="71633-185">The following procedure describes how to set up quick scans using Group Policy.</span></span>

1. <span data-ttu-id="71633-186">Ga in de Groepsbeleidseditor naar **Beheersjablonen**  >  **Windows-onderdelen**  >  **Microsoft Defender Antivirus**  >  **Scan.**</span><span class="sxs-lookup"><span data-stu-id="71633-186">In your Group Policy Editor, go to **Administrative templates** > **Windows components** > **Microsoft Defender Antivirus** > **Scan**.</span></span>

2. <span data-ttu-id="71633-187">Selecteer **Geef het scantype op dat u wilt gebruiken** voor een geplande scan en bewerk vervolgens de beleidsinstelling.</span><span class="sxs-lookup"><span data-stu-id="71633-187">Select **Specify the scan type to use for a scheduled scan** and then edit the policy setting.</span></span>

3. <span data-ttu-id="71633-188">Stel het beleid in **op Ingeschakeld** en selecteer onder **Opties** de optie **Snel scannen.**</span><span class="sxs-lookup"><span data-stu-id="71633-188">Set the policy to **Enabled**, and then under **Options**, select  **Quick scan**.</span></span>

4. <span data-ttu-id="71633-189">Kies **OK**.</span><span class="sxs-lookup"><span data-stu-id="71633-189">Select **OK**.</span></span> 

5. <span data-ttu-id="71633-190">Implementeer het groepsbeleidsobject zoals u gewoonlijk doet.</span><span class="sxs-lookup"><span data-stu-id="71633-190">Deploy your Group Policy object as you usually do.</span></span>

## <a name="prevent-notifications"></a><span data-ttu-id="71633-191">Meldingen voorkomen</span><span class="sxs-lookup"><span data-stu-id="71633-191">Prevent notifications</span></span>

<span data-ttu-id="71633-192">Soms kunnen Microsoft Defender Antivirusmeldingen worden verzonden naar of blijven bestaan in meerdere sessies.</span><span class="sxs-lookup"><span data-stu-id="71633-192">Sometimes, Microsoft Defender Antivirus notifications may be sent to or persist across multiple sessions.</span></span> <span data-ttu-id="71633-193">Als u dit probleem wilt minimaliseren, kunt u de gebruikersinterface van Microsoft Defender Antivirus vergrendelen.</span><span class="sxs-lookup"><span data-stu-id="71633-193">In order to minimize this problem, you can lock down the Microsoft Defender Antivirus user interface.</span></span> <span data-ttu-id="71633-194">In de volgende procedure wordt beschreven hoe u meldingen met groepsbeleid kunt onderdrukken.</span><span class="sxs-lookup"><span data-stu-id="71633-194">The following procedure describes how to suppress notifications with Group Policy.</span></span>

1. <span data-ttu-id="71633-195">Ga in de Groepsbeleidseditor naar **Windows-onderdelen**  >  **Microsoft Defender Antivirus** Client  >  **Interface.**</span><span class="sxs-lookup"><span data-stu-id="71633-195">In your Group Policy Editor, go to **Windows components** > **Microsoft Defender Antivirus** > **Client Interface**.</span></span>

2. <span data-ttu-id="71633-196">Selecteer **Alle meldingen onderdrukken en** bewerk vervolgens de beleidsinstellingen.</span><span class="sxs-lookup"><span data-stu-id="71633-196">Select **Suppress all notifications** and then edit the policy settings.</span></span> 

3. <span data-ttu-id="71633-197">Stel het beleid in **op Ingeschakeld** en selecteer **OK.**</span><span class="sxs-lookup"><span data-stu-id="71633-197">Set the policy to **Enabled**, and then select **OK**.</span></span>

4. <span data-ttu-id="71633-198">Implementeer het groepsbeleidsobject zoals u gewoonlijk doet.</span><span class="sxs-lookup"><span data-stu-id="71633-198">Deploy your Group Policy object as you usually do.</span></span>

<span data-ttu-id="71633-199">Als u meldingen onderdrukt, worden meldingen van Microsoft Defender Antivirus niet weergegeven in het Actiecentrum in Windows 10 wanneer scans worden uitgevoerd of herstelacties worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="71633-199">Suppressing notifications prevents notifications from Microsoft Defender Antivirus from showing up in the Action Center on Windows 10 when scans are done or remediation actions are taken.</span></span> <span data-ttu-id="71633-200">Het beveiligingsteam ziet echter de resultaten van de scan in het Microsoft Defender-beveiligingscentrum [https://securitycenter.windows.com](https://securitycenter.windows.com) ().</span><span class="sxs-lookup"><span data-stu-id="71633-200">However, your security operations team will see the results of the scan in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

> [!TIP]
> <span data-ttu-id="71633-201">Als u het Actiecentrum in Windows 10 wilt openen, gaat u als volgt te werk:</span><span class="sxs-lookup"><span data-stu-id="71633-201">To open the Action Center on Windows 10, take one of the following steps:</span></span>
> - <span data-ttu-id="71633-202">Selecteer het pictogram Actiecentrum aan de rechterkant van de taakbalk.</span><span class="sxs-lookup"><span data-stu-id="71633-202">On the right end of the taskbar, select the Action Center icon.</span></span>
> - <span data-ttu-id="71633-203">Druk op de knop Windows-logotoets + A.</span><span class="sxs-lookup"><span data-stu-id="71633-203">Press the Windows logo key button + A.</span></span>
> - <span data-ttu-id="71633-204">Swipe op een touchscreen vanaf de rechterrand van het scherm.</span><span class="sxs-lookup"><span data-stu-id="71633-204">On a touchscreen device, swipe in from the right edge of the screen.</span></span>

## <a name="disable-scans-after-an-update"></a><span data-ttu-id="71633-205">Scans uitschakelen na een update</span><span class="sxs-lookup"><span data-stu-id="71633-205">Disable scans after an update</span></span>

<span data-ttu-id="71633-206">Als u een scan na een update uit kunt uitschakelen, wordt voorkomen dat er een scan wordt uitgevoerd na ontvangst van een update.</span><span class="sxs-lookup"><span data-stu-id="71633-206">Disabling a scan after an update will prevent a scan from occurring after receiving an update.</span></span> <span data-ttu-id="71633-207">U kunt deze instelling toepassen bij het maken van de basisafbeelding als u ook een snelle scan hebt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="71633-207">You can apply this setting when creating the base image if you have also run a quick scan.</span></span> <span data-ttu-id="71633-208">Op deze manier kunt u voorkomen dat de onlangs bijgewerkte VM opnieuw een scan kan uitvoeren (zoals u al hebt gescand toen u de basisafbeelding maakte).</span><span class="sxs-lookup"><span data-stu-id="71633-208">This way, you can prevent the newly updated VM from performing a scan again (as you've already scanned it when you created the base image).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="71633-209">Met scans na een update kunt u ervoor zorgen dat uw VM's worden beveiligd met de meest recente beveiligingsinformatie-updates.</span><span class="sxs-lookup"><span data-stu-id="71633-209">Running scans after an update will help ensure your VMs are protected with the latest Security intelligence updates.</span></span> <span data-ttu-id="71633-210">Als u deze optie uitkeert, wordt het beveiligingsniveau van uw VM's beperkt en mag deze alleen worden gebruikt wanneer u eerst de basisafbeelding maakt of implementeert.</span><span class="sxs-lookup"><span data-stu-id="71633-210">Disabling this option will reduce the protection level of your VMs and should only be used when first creating or deploying the base image.</span></span>

1. <span data-ttu-id="71633-211">Ga in de Groepsbeleidseditor naar **Windows-onderdelen**  >  **Microsoft Defender Antivirus** Security Intelligence  >  **Updates.**</span><span class="sxs-lookup"><span data-stu-id="71633-211">In your Group Policy Editor, go to **Windows components** > **Microsoft Defender Antivirus** > **Security Intelligence Updates**.</span></span>

2. <span data-ttu-id="71633-212">Selecteer **Scannen in-/uit-/uit-2014** en bewerk vervolgens de beleidsinstelling.</span><span class="sxs-lookup"><span data-stu-id="71633-212">Select **Turn on scan after security intelligence update** and then edit the policy setting.</span></span>

3. <span data-ttu-id="71633-213">Stel het beleid in op **Uitgeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="71633-213">Set the policy to **Disabled**.</span></span>

4. <span data-ttu-id="71633-214">Kies **OK**.</span><span class="sxs-lookup"><span data-stu-id="71633-214">Select **OK**.</span></span>

5. <span data-ttu-id="71633-215">Implementeer het groepsbeleidsobject zoals u gewoonlijk doet.</span><span class="sxs-lookup"><span data-stu-id="71633-215">Deploy your Group Policy object as you usually do.</span></span>

<span data-ttu-id="71633-216">Met dit beleid wordt voorkomen dat een scan direct na een update wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="71633-216">This policy prevents a scan from running immediately after an update.</span></span>

## <a name="scan-vms-that-have-been-offline"></a><span data-ttu-id="71633-217">VM's scannen die offline zijn</span><span class="sxs-lookup"><span data-stu-id="71633-217">Scan VMs that have been offline</span></span>

1. <span data-ttu-id="71633-218">Ga in de Groepsbeleidseditor naar **Windows-onderdelen**  >  **Microsoft Defender Antivirus**  >  **Scan.**</span><span class="sxs-lookup"><span data-stu-id="71633-218">In your Group Policy Editor, go to to **Windows components** > **Microsoft Defender Antivirus** > **Scan**.</span></span>

2. <span data-ttu-id="71633-219">Selecteer **Inhaal quick scan in- en uithalen** en bewerk vervolgens de beleidsinstelling.</span><span class="sxs-lookup"><span data-stu-id="71633-219">Select **Turn on catch-up quick scan** and then edit the policy setting.</span></span>

3. <span data-ttu-id="71633-220">Stel het beleid in op **Ingeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="71633-220">Set the policy to **Enabled**.</span></span>

4. <span data-ttu-id="71633-221">Kies **OK**.</span><span class="sxs-lookup"><span data-stu-id="71633-221">Select **OK**.</span></span>

5. <span data-ttu-id="71633-222">Implementeer het groepsbeleidsobject zoals u gewoonlijk doet.</span><span class="sxs-lookup"><span data-stu-id="71633-222">Deploy your Group Policy Object as you usually do.</span></span>

<span data-ttu-id="71633-223">Dit beleid dwingt een scan af als de VM twee of meer opeenvolgende geplande scans heeft gemist.</span><span class="sxs-lookup"><span data-stu-id="71633-223">This policy forces a scan if the VM has missed two or more consecutive scheduled scans.</span></span>

## <a name="enable-headless-ui-mode"></a><span data-ttu-id="71633-224">Gebruikersinterface zonder hoofd inschakelen</span><span class="sxs-lookup"><span data-stu-id="71633-224">Enable headless UI mode</span></span>

1. <span data-ttu-id="71633-225">Ga in de Groepsbeleidseditor naar **Windows-onderdelen**  >  **Microsoft Defender Antivirus** Client  >  **Interface.**</span><span class="sxs-lookup"><span data-stu-id="71633-225">In your Group Policy Editor, go to **Windows components** > **Microsoft Defender Antivirus** > **Client Interface**.</span></span>

2. <span data-ttu-id="71633-226">Selecteer **De gebruikersinterfacemodus zonder hoofd inschakelen** en bewerk het beleid.</span><span class="sxs-lookup"><span data-stu-id="71633-226">Select **Enable headless UI mode** and edit the policy.</span></span>

3. <span data-ttu-id="71633-227">Stel het beleid in op **Ingeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="71633-227">Set the policy to **Enabled**.</span></span>

4. <span data-ttu-id="71633-228">Klik op **OK**.</span><span class="sxs-lookup"><span data-stu-id="71633-228">Click **OK**.</span></span>

5. <span data-ttu-id="71633-229">Implementeer het groepsbeleidsobject zoals u gewoonlijk doet.</span><span class="sxs-lookup"><span data-stu-id="71633-229">Deploy your Group Policy Object as you usually do.</span></span>
 
<span data-ttu-id="71633-230">Met dit beleid wordt de volledige gebruikersinterface van Microsoft Defender Antivirus verborgen voor eindgebruikers in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="71633-230">This policy hides the entire Microsoft Defender Antivirus user interface from end users in your organization.</span></span>

## <a name="exclusions"></a><span data-ttu-id="71633-231">Uitsluitingen</span><span class="sxs-lookup"><span data-stu-id="71633-231">Exclusions</span></span>

<span data-ttu-id="71633-232">Uitsluitingen kunnen worden toegevoegd, verwijderd of aangepast aan uw behoeften.</span><span class="sxs-lookup"><span data-stu-id="71633-232">Exclusions can be added, removed, or customized to suit your needs.</span></span>

<span data-ttu-id="71633-233">Zie Microsoft [Defender Antivirus exclusions configureren op Windows Server voor meer informatie.](configure-exclusions-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="71633-233">For more information, see [Configure Microsoft Defender Antivirus exclusions on Windows Server](configure-exclusions-microsoft-defender-antivirus.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="71633-234">Aanvullende bronnen</span><span class="sxs-lookup"><span data-stu-id="71633-234">Additional resources</span></span>

- [<span data-ttu-id="71633-235">Tech Community Blog: Microsoft Defender Antivirus configureren voor niet-permanente VDI-machines</span><span class="sxs-lookup"><span data-stu-id="71633-235">Tech Community Blog: Configuring Microsoft Defender Antivirus for non-persistent VDI machines</span></span>](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/configuring-microsoft-defender-antivirus-for-non-persistent-vdi/ba-p/1489633)
- [<span data-ttu-id="71633-236">TechNet-forums op Remote Desktop Services en VDI</span><span class="sxs-lookup"><span data-stu-id="71633-236">TechNet forums on Remote Desktop Services and VDI</span></span>](https://social.technet.microsoft.com/Forums/windowsserver/en-US/home?forum=winserverTS)
- [<span data-ttu-id="71633-237">SignatureDownloadCustomTask PowerShell-script</span><span class="sxs-lookup"><span data-stu-id="71633-237">SignatureDownloadCustomTask PowerShell script</span></span>](https://www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4)