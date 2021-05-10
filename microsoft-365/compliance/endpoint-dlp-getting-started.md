---
title: Aan de slag met Microsoft 365 Preventie van gegevensverlies voor eindpunten
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Stel Microsoft 365 Preventie van gegevensverlies voor eindpunten in om bestandsactiviteiten te controleren en beschermende maatregelen voor deze bestanden naar eindpunten te implementeren.
ms.openlocfilehash: 118c2f3f87df5ac9930bebd1338157d323b1e5e1
ms.sourcegitcommit: 5a1cb7d95070eef47d401a4693cc137a90550a5e
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/06/2021
ms.locfileid: "52259497"
---
# <a name="get-started-with-endpoint-data-loss-prevention"></a><span data-ttu-id="483a5-103">Aan de slag met Preventie van gegevensverlies voor eindpunten</span><span class="sxs-lookup"><span data-stu-id="483a5-103">Get started with Endpoint data loss prevention</span></span>

<span data-ttu-id="483a5-104">Microsoft Preventie van gegevensverlies voor eindpunten (DLP voor eindpunten) maakt deel uit van het Microsoft 365-programmapakket voor preventie van gegevensverlies (DLP) met functies die u kunt gebruiken voor het zoeken en beveiligen van gevoelige items in Microsoft 365-services.</span><span class="sxs-lookup"><span data-stu-id="483a5-104">Microsoft Endpoint data loss prevention (Endpoint DLP) is part of the Microsoft 365 data loss prevention (DLP) suite of features you can use to discover and protect sensitive items across Microsoft 365 services.</span></span> <span data-ttu-id="483a5-105">Zie voor meer informatie over alle DLP-aanbiedingen van Microsoft [Meer informatie over preventie van gegevensverlies](dlp-learn-about-dlp.md).</span><span class="sxs-lookup"><span data-stu-id="483a5-105">For more information about all of Microsoft’s DLP offerings, see [Learn about data loss prevention](dlp-learn-about-dlp.md).</span></span> <span data-ttu-id="483a5-106">Zie voor meer informatie over DLP voor eindpunten [Meer informatie over preventie van gegevensverlies voor eindpunten](endpoint-dlp-learn-about.md)</span><span class="sxs-lookup"><span data-stu-id="483a5-106">To learn more about Endpoint DLP, see [Learn about Endpoint data loss prevention](endpoint-dlp-learn-about.md)</span></span>

<span data-ttu-id="483a5-107">Met Microsoft DLP voor eindpunten kunt u Windows 10-apparaten controleren en detecteren wanneer gevoelige items worden gebruikt en gedeeld.</span><span class="sxs-lookup"><span data-stu-id="483a5-107">Microsoft Endpoint DLP allows you to monitor Windows 10 devices and detect when sensitive items are used and shared.</span></span> <span data-ttu-id="483a5-108">Dit geeft u de zichtbaarheid en controle die u nodig hebt om ervoor te zorgen dat ze goed worden gebruikt en beveiligd, en om risicogedrag te voorkomen dat dergelijke gevoelige items in gevaar kan brengen.</span><span class="sxs-lookup"><span data-stu-id="483a5-108">This gives you the visibility and control you need to ensure that they are used and protected properly, and to help prevent risky behavior that might compromise them.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="483a5-109">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="483a5-109">Before you begin</span></span>

### <a name="skusubscriptions-licensing"></a><span data-ttu-id="483a5-110">SKU/abonnementenlicenties</span><span class="sxs-lookup"><span data-stu-id="483a5-110">SKU/subscriptions licensing</span></span>

<span data-ttu-id="483a5-111">Voordat u aan de slag gaat met DLP voor eindpunten, moet u uw [abonnement op Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) en eventuele invoegtoepassingen bevestigen.</span><span class="sxs-lookup"><span data-stu-id="483a5-111">Before you get started with Endpoint DLP, you should confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) and any add-ons.</span></span> <span data-ttu-id="483a5-112">Als u DLP-functionaliteit voor eindpunten wilt openen en gebruiken, moet u een van deze abonnementen of invoegtoepassingen hebben.</span><span class="sxs-lookup"><span data-stu-id="483a5-112">To access and use Endpoint DLP functionality, you must have one of these subscriptions or add-ons.</span></span>

- <span data-ttu-id="483a5-113">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="483a5-113">Microsoft 365 E5</span></span>
- <span data-ttu-id="483a5-114">Microsoft 365 A5 (EDU)</span><span class="sxs-lookup"><span data-stu-id="483a5-114">Microsoft 365 A5 (EDU)</span></span>
- <span data-ttu-id="483a5-115">Microsoft 365 E5 compliance</span><span class="sxs-lookup"><span data-stu-id="483a5-115">Microsoft 365 E5 compliance</span></span>
- <span data-ttu-id="483a5-116">Microsoft 365 A5 compliance</span><span class="sxs-lookup"><span data-stu-id="483a5-116">Microsoft 365 A5 compliance</span></span>
- <span data-ttu-id="483a5-117">Microsoft 365 E5 Information Protection en governance</span><span class="sxs-lookup"><span data-stu-id="483a5-117">Microsoft 365 E5 information protection and governance</span></span>
- <span data-ttu-id="483a5-118">Microsoft 365 A5 Information Protection en governance</span><span class="sxs-lookup"><span data-stu-id="483a5-118">Microsoft 365 A5 information protection and governance</span></span>


### <a name="permissions"></a><span data-ttu-id="483a5-119">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="483a5-119">Permissions</span></span>

<span data-ttu-id="483a5-120">Als u apparaatbeheer wilt inschakelen, moet het account dat u gebruikt lid zijn van een van deze rollen:</span><span class="sxs-lookup"><span data-stu-id="483a5-120">To enable device management, the account you use must be a member of any one of these roles:</span></span>

- <span data-ttu-id="483a5-121">Bedrijfsbeheerder</span><span class="sxs-lookup"><span data-stu-id="483a5-121">Global admin</span></span>
- <span data-ttu-id="483a5-122">Beveiligingsbeheerder</span><span class="sxs-lookup"><span data-stu-id="483a5-122">Security admin</span></span>
- <span data-ttu-id="483a5-123">Compliancebeheerder</span><span class="sxs-lookup"><span data-stu-id="483a5-123">Compliance admin</span></span>

<span data-ttu-id="483a5-124">Als u een aangepast account wilt gebruiken om de instellingen voor apparaatbeheer te bekijken, moet dit een van deze rollen hebben:</span><span class="sxs-lookup"><span data-stu-id="483a5-124">If you want to use a custom account to view the device management settings, it must be in one of these roles:</span></span>

- <span data-ttu-id="483a5-125">Bedrijfsbeheerder</span><span class="sxs-lookup"><span data-stu-id="483a5-125">Global admin</span></span>
- <span data-ttu-id="483a5-126">Compliancebeheerder</span><span class="sxs-lookup"><span data-stu-id="483a5-126">Compliance admin</span></span>
- <span data-ttu-id="483a5-127">Beheerder van compliancegegevens</span><span class="sxs-lookup"><span data-stu-id="483a5-127">Compliance data admin</span></span>
- <span data-ttu-id="483a5-128">Globale lezer</span><span class="sxs-lookup"><span data-stu-id="483a5-128">Global reader</span></span>

<span data-ttu-id="483a5-129">Als u een aangepast account wilt gebruiken voor toegang tot de onboarding-/offboarding-pagina, moet dit een van deze rollen hebben:</span><span class="sxs-lookup"><span data-stu-id="483a5-129">If you want to use a custom account to access the onboarding/offboarding page, it must be in one of these roles:</span></span>

- <span data-ttu-id="483a5-130">Bedrijfsbeheerder</span><span class="sxs-lookup"><span data-stu-id="483a5-130">Global admin</span></span>
- <span data-ttu-id="483a5-131">Compliancebeheerder</span><span class="sxs-lookup"><span data-stu-id="483a5-131">Compliance admin</span></span>

<span data-ttu-id="483a5-132">Als u een aangepast account wilt gebruiken om Apparaatcontrole in te schakelen of uit te schakelen, moet dit een van deze rollen hebben:</span><span class="sxs-lookup"><span data-stu-id="483a5-132">If you want to use a custom account to turn on/off device monitoring, it must be in one of these roles:</span></span>

- <span data-ttu-id="483a5-133">Bedrijfsbeheerder</span><span class="sxs-lookup"><span data-stu-id="483a5-133">Global admin</span></span>
- <span data-ttu-id="483a5-134">Compliancebeheerder</span><span class="sxs-lookup"><span data-stu-id="483a5-134">Compliance admin</span></span>

<span data-ttu-id="483a5-135">Gegevens uit DLP voor eindpunten kunnen worden weergegeven in [Activiteitenverkenner](data-classification-activity-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="483a5-135">Data from Endpoint DLP can be viewed in [Activity explorer](data-classification-activity-explorer.md).</span></span> <span data-ttu-id="483a5-136">Er zijn vier rollen die machtigingen verlenen aan Activiteitenverkenner. Het account dat u gebruikt voor het openen van de gegevens, moet lid zijn van een van deze rollen.</span><span class="sxs-lookup"><span data-stu-id="483a5-136">There are four roles that grant permission to activity explorer, the account you use for accessing the data must be a member of any one of them.</span></span>

- <span data-ttu-id="483a5-137">Bedrijfsbeheerder</span><span class="sxs-lookup"><span data-stu-id="483a5-137">Global admin</span></span>
- <span data-ttu-id="483a5-138">Compliancebeheerder</span><span class="sxs-lookup"><span data-stu-id="483a5-138">Compliance admin</span></span>
- <span data-ttu-id="483a5-139">Beveiligingsbeheerder</span><span class="sxs-lookup"><span data-stu-id="483a5-139">Security admin</span></span>
- <span data-ttu-id="483a5-140">Beheerder van compliancegegevens</span><span class="sxs-lookup"><span data-stu-id="483a5-140">Compliance data admin</span></span>
- <span data-ttu-id="483a5-141">Globale lezer</span><span class="sxs-lookup"><span data-stu-id="483a5-141">Global reader</span></span>
- <span data-ttu-id="483a5-142">Beveiligingslezer</span><span class="sxs-lookup"><span data-stu-id="483a5-142">Security reader</span></span>
- <span data-ttu-id="483a5-143">Rapportenlezer</span><span class="sxs-lookup"><span data-stu-id="483a5-143">Reports reader</span></span>

### <a name="prepare-your-endpoints"></a><span data-ttu-id="483a5-144">Uw eindpunten voorbereiden</span><span class="sxs-lookup"><span data-stu-id="483a5-144">Prepare your endpoints</span></span>

<span data-ttu-id="483a5-145">Zorg ervoor dat de Windows 10-apparaten die u van plan bent in DLP voor eindpunten te implementeren aan deze vereisten voldoen.</span><span class="sxs-lookup"><span data-stu-id="483a5-145">Make sure that the Windows 10 devices that you plan on deploying Endpoint DLP to meet these requirements.</span></span>

1. <span data-ttu-id="483a5-146">Moet Windows 10 x64 build 1809 of hoger hebben.</span><span class="sxs-lookup"><span data-stu-id="483a5-146">Must be running Windows 10 x64 build 1809 or later.</span></span>

2. <span data-ttu-id="483a5-147">Antimalware-clientversie is 4.18.2009.7 of hoger.</span><span class="sxs-lookup"><span data-stu-id="483a5-147">Antimalware Client Version is 4.18.2009.7 or newer.</span></span> <span data-ttu-id="483a5-148">Controleer uw huidige versie door de Windows-beveiligingsapp te openen, selecteer het pictogram Instellingen en selecteer vervolgens Info.</span><span class="sxs-lookup"><span data-stu-id="483a5-148">Check your current version by opening Windows Security app, select the Settings icon, and then select About.</span></span> <span data-ttu-id="483a5-149">Het versienummer wordt weergegeven onder Antimalware-clientversie.</span><span class="sxs-lookup"><span data-stu-id="483a5-149">The version number is listed under Antimalware Client Version.</span></span> <span data-ttu-id="483a5-150">Werk bij naar de nieuwste Antimalware-clientversie door Windows Update KB4052623 te installeren.</span><span class="sxs-lookup"><span data-stu-id="483a5-150">Update to the latest Antimalware Client Version by installing Windows Update KB4052623.</span></span> 

   > [!NOTE]
   > <span data-ttu-id="483a5-151">Geen van de Windows-beveiligingsonderdelen hoeft actief te zijn, u kunt DLP voor eindpunten uitvoeren onafhankelijk van de Windows-beveiligingsstatus, maar de [Realtime-beveiliging- en gedragscontrole](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus)) moet zijn ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="483a5-151">None of Windows Security components need to be active, you can run Endpoint DLP independent of Windows Security status, but the [Real-time protection and Behavior monitor](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus)) must be enabled.</span></span>
 
3. <span data-ttu-id="483a5-152">De volgende Windows-updates zijn geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="483a5-152">The following Windows Updates are installed.</span></span> 
 
   > [!NOTE]
   > <span data-ttu-id="483a5-153">Deze updates zijn niet vereist voor het onboarden van een apparaat naar DLP voor eindpunten, maar bevatten oplossingen voor belangrijke problemen die dus moeten worden geïnstalleerd voordat u het product gebruikt.</span><span class="sxs-lookup"><span data-stu-id="483a5-153">These updates are not a pre-requisite to onboard a device to Endpoint DLP, but contain fixes for important issues thus must be installed before using the product.</span></span>

    - <span data-ttu-id="483a5-154">Voor Windows 10 1809 - KB4559003, KB4577069, KB4580390</span><span class="sxs-lookup"><span data-stu-id="483a5-154">For Windows 10 1809 - KB4559003, KB4577069, KB4580390</span></span>
    - <span data-ttu-id="483a5-155">Voor Windows 10 1903 or 1909 - KB4559004, KB4577062, KB4580386</span><span class="sxs-lookup"><span data-stu-id="483a5-155">For Windows 10 1903 or 1909 - KB4559004, KB4577062, KB4580386</span></span>
    - <span data-ttu-id="483a5-156">Voor Windows 10 2004 - KB4568831, KB4577063</span><span class="sxs-lookup"><span data-stu-id="483a5-156">For Windows 10 2004 - KB4568831, KB4577063</span></span>
    - <span data-ttu-id="483a5-157">Voor apparaten met Office 2016 (en geen andere Office-versie) - KB4577063</span><span class="sxs-lookup"><span data-stu-id="483a5-157">For devices running Office 2016 (and not any other Office version) - KB4577063</span></span> 

4. <span data-ttu-id="483a5-158">Alle apparaten moeten [Azure Active Directory-gekoppeld zijn (Azure AD)](/azure/active-directory/devices/concept-azure-ad-join), AD-gekoppeld, Hybride Azure AD-gekoppeld of AAD-geregistreerd zijn.</span><span class="sxs-lookup"><span data-stu-id="483a5-158">All devices must be [Azure Active Directory (Azure AD) joined](/azure/active-directory/devices/concept-azure-ad-join), AD joined, Hybrid Azure AD joined, or AAD registered.</span></span>

5. <span data-ttu-id="483a5-159">Installeer de browser Microsoft Chromium Edge op het eindpuntapparaat om beleidsacties af te dwingen voor het uploaden naar cloudactiviteit.</span><span class="sxs-lookup"><span data-stu-id="483a5-159">Install Microsoft Chromium Edge browser on the endpoint device to enforce policy actions for the upload to cloud activity.</span></span> <span data-ttu-id="483a5-160">Zie [Nieuwe Microsoft Edge op basis van Chromium downloaden](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium).</span><span class="sxs-lookup"><span data-stu-id="483a5-160">See, [Download the new Microsoft Edge based on Chromium](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium).</span></span>

6. <span data-ttu-id="483a5-161">Als u werkt met het Maandelijks ondernemingskanaal van Microsoft 365-apps (versie 2004-2008) is er een bekend probleem met de DLP-classificatie van Office-inhoud voor eindpunten en moet u bijwerken naar versie 2009 of hoger.</span><span class="sxs-lookup"><span data-stu-id="483a5-161">If you are on Monthly Enterprise Channel of Microsoft 365 Apps versions 2004-2008, there is a known issue with Endpoint DLP classifying Office content and you need to update to version 2009 or later.</span></span> <span data-ttu-id="483a5-162">Zie [Geschiedenis van updates voor Microsoft 365-apps (weergegeven op datum)](/officeupdates/update-history-microsoft365-apps-by-date)voor huidige versies.</span><span class="sxs-lookup"><span data-stu-id="483a5-162">See [Update history for Microsoft 365 Apps (listed by date)](/officeupdates/update-history-microsoft365-apps-by-date) for current versions.</span></span> <span data-ttu-id="483a5-163">Voor meer informatie over dit probleem, zie de sectie van het Office-programmapakket [Releaseopmerkingen voor huidige kanaalreleases in 2020](/officeupdates/current-channel#version-2010-october-27).</span><span class="sxs-lookup"><span data-stu-id="483a5-163">To learn more about this issue, see the Office Suite section of [Release notes for Current Channel releases in 2020](/officeupdates/current-channel#version-2010-october-27).</span></span>

7. <span data-ttu-id="483a5-164">Als u eindpunten hebt die een apparaatproxy gebruiken om verbinding te maken met internet, volgt u de procedures in [Apparaatproxy- en internetverbindingsinstellingen configureren voor DLP voor eindpunten](endpoint-dlp-configure-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="483a5-164">If you have endpoints that use a device proxy to connect to the internet, follow the procedures in [Configure device proxy and internet connection settings for Endpoint DLP](endpoint-dlp-configure-proxy.md).</span></span>

## <a name="onboarding-devices-into-device-management"></a><span data-ttu-id="483a5-165">Zie Onboarding van apparaten in apparaatbeheer</span><span class="sxs-lookup"><span data-stu-id="483a5-165">Onboarding devices into device management</span></span>

<span data-ttu-id="483a5-166">U moet apparaatcontrole en onboarding van uw eindpunten inschakelen voordat u gevoelige items op een apparaat kunt controleren en beveiligen.</span><span class="sxs-lookup"><span data-stu-id="483a5-166">You must enable device monitoring and onboard your endpoints before you can monitor and protect sensitive items on a device.</span></span> <span data-ttu-id="483a5-167">Beide acties worden uitgevoerd in het Complianceportal van Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="483a5-167">Both of these actions are done in the Microsoft 365 Compliance portal.</span></span>

<span data-ttu-id="483a5-168">Wanneer u apparaten wilt gebruiken die nog niet zijn onboarded, downloadt u het juiste script en implementeert u het op die apparaten.</span><span class="sxs-lookup"><span data-stu-id="483a5-168">When you want to onboard devices that haven't been onboarded yet, you'll download the appropriate script and deploy it to those devices.</span></span> <span data-ttu-id="483a5-169">Volg de [Procedure voor de onboarding van apparaten](endpoint-dlp-getting-started.md#onboarding-devices).</span><span class="sxs-lookup"><span data-stu-id="483a5-169">Follow the [Onboarding devices procedure](endpoint-dlp-getting-started.md#onboarding-devices).</span></span>

<span data-ttu-id="483a5-170">Als u al apparaten hebt die zijn toegevoegd aan [Microsoft Defender voor Eindpunt](/windows/security/threat-protection/), worden deze al weergegeven in de lijst met beheerde apparaten.</span><span class="sxs-lookup"><span data-stu-id="483a5-170">If you already have devices onboarded into [Microsoft Defender for Endpoint](/windows/security/threat-protection/), they will already appear in the managed devices list.</span></span> <span data-ttu-id="483a5-171">Volg de [procedure Met apparaten die onboarded zijn in Microsoft Defender voor Eindpunt](?source=docs&view=o365-worldwide#with-devices-onboarded-into-microsoft-defender-for-endpoint).</span><span class="sxs-lookup"><span data-stu-id="483a5-171">Follow the [With devices onboarded into Microsoft Defender for Endpoint procedure](?source=docs&view=o365-worldwide#with-devices-onboarded-into-microsoft-defender-for-endpoint).</span></span>

### <a name="onboarding-devices"></a><span data-ttu-id="483a5-172">Onboarding van apparaten</span><span class="sxs-lookup"><span data-stu-id="483a5-172">Onboarding devices</span></span>

<span data-ttu-id="483a5-173">In dit implementatiescenario onboardt u apparaten die nog niet zijn onboarded en wilt u alleen gevoelige items controleren en beveiligen tegen onbedoeld delen op Windows 10-apparaten.</span><span class="sxs-lookup"><span data-stu-id="483a5-173">In this deployment scenario, you'll onboard devices that have not been onboarded yet, and you just want to monitor and protect sensitive items from unintentional sharing on Windows 10 devices.</span></span>

1. <span data-ttu-id="483a5-174">Open het [Microsoft-compliancecentrum](https://compliance.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="483a5-174">Open the [Microsoft compliance center](https://compliance.microsoft.com).</span></span>

2. <span data-ttu-id="483a5-175">Open de instellingenpagina voor het Compliancecentrum en kies **Apparaten onboarden**.</span><span class="sxs-lookup"><span data-stu-id="483a5-175">Open the Compliance Center settings page and choose **Onboard devices**.</span></span> 

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="483a5-176">![apparaatbeheer inschakelen](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="483a5-176">![enable device management](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span></span>

   > [!NOTE]
   > <span data-ttu-id="483a5-177">Het duurt gewoonlijk ongeveer 60 seconden voordat onboarding voor apparaten is ingeschakeld. Wacht 30 minuten voordat u contact opneemt met Microsoft-ondersteuning.</span><span class="sxs-lookup"><span data-stu-id="483a5-177">While it usually takes about 60 seconds for device onboarding to be enabled, please allow up to 30 minutes before engaging with Microsoft support.</span></span>

3. <span data-ttu-id="483a5-178">Kies **Apparaatbeheer** om de lijst **Apparaten** te openen.</span><span class="sxs-lookup"><span data-stu-id="483a5-178">Choose **Device management** to open the **Devices** list.</span></span> <span data-ttu-id="483a5-179">De lijst is leeg totdat u apparaten onboardt.</span><span class="sxs-lookup"><span data-stu-id="483a5-179">The list will be empty until you onboard devices.</span></span>

4. <span data-ttu-id="483a5-180">Kies **Onboarding** om het onboardingproces te starten.</span><span class="sxs-lookup"><span data-stu-id="483a5-180">Choose **Onboarding** to begin the onboarding process.</span></span>

5. <span data-ttu-id="483a5-181">Kies de manier waarop u wilt implementeren op deze andere apparaten in de lijst **implementatiemethode** en vervolgens **pakket downloaden**.</span><span class="sxs-lookup"><span data-stu-id="483a5-181">Choose the way you want to deploy to these additional devices from the **Deployment method** list and then **download package**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="483a5-182">![Implementatiemethode](../media/endpoint-dlp-getting-started-3-deployment-method.png)</span><span class="sxs-lookup"><span data-stu-id="483a5-182">![deployment method](../media/endpoint-dlp-getting-started-3-deployment-method.png)</span></span>
   
6. <span data-ttu-id="483a5-183">Volg de juiste procedures in [Onboarding-hulpprogramma's en -methoden voor Windows 10-computers](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span><span class="sxs-lookup"><span data-stu-id="483a5-183">Follow the appropriate procedures in [Onboarding tools and methods for Windows 10 machines](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span> <span data-ttu-id="483a5-184">Via deze koppeling gaat u naar een landingspagina waar u toegang hebt tot procedures voor Microsoft Defender voor Eindpunt die overeenkomen met het installatiepakket dat u in stap 5 hebt geselecteerd:</span><span class="sxs-lookup"><span data-stu-id="483a5-184">This link takes you to a landing page where you can access Microsoft Defender for Endpoint procedures that match the deployment package you selected in step 5:</span></span>

    - <span data-ttu-id="483a5-185">Windows 10-computers onboarden met groepsbeleid</span><span class="sxs-lookup"><span data-stu-id="483a5-185">Onboard Windows 10 machines using Group Policy</span></span>
    - <span data-ttu-id="483a5-186">Windows-apparaten onboarden met behulp van Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="483a5-186">Onboard Windows machines using Microsoft Endpoint Configuration Manager</span></span>
    - <span data-ttu-id="483a5-187">Windows 10-apparaten onboarden met hulpmiddelen voor Mobiel Apparaatbeheer</span><span class="sxs-lookup"><span data-stu-id="483a5-187">Onboard Windows 10 machines using Mobile Device Management tools</span></span>
    - <span data-ttu-id="483a5-188">Windows 10-apparaten onboarden met een lokaal script</span><span class="sxs-lookup"><span data-stu-id="483a5-188">Onboard Windows 10 machines using a local script</span></span>
    - <span data-ttu-id="483a5-189">Niet-permanente virtuele desktopinfrastructuur (VDI)-apparaten onboarden.</span><span class="sxs-lookup"><span data-stu-id="483a5-189">Onboard non-persistent virtual desktop infrastructure (VDI) machines.</span></span>

<span data-ttu-id="483a5-190">Wanneer dit is gedaan en het eindpunt is onboarded, moet dit zichtbaar zijn in de lijst met apparaten en moet u ook auditactiviteitslogboeken rapporteren aan Activiteitenverkenner.</span><span class="sxs-lookup"><span data-stu-id="483a5-190">Once done and endpoint is onboarded, it should be visible in the devices list and also start reporting audit activity logs to Activity explorer.</span></span>

> [!NOTE]
> <span data-ttu-id="483a5-191">Deze ervaring valt onder het afdwingen van licenties.</span><span class="sxs-lookup"><span data-stu-id="483a5-191">This experience is under license enforcement.</span></span> <span data-ttu-id="483a5-192">Zonder de vereiste licentie zijn de gegevens niet zichtbaar of toegankelijk.</span><span class="sxs-lookup"><span data-stu-id="483a5-192">Without the required license, data will not be visible or accessible.</span></span>

### <a name="with-devices-onboarded-into-microsoft-defender-for-endpoint"></a><span data-ttu-id="483a5-193">Met apparaten die onboarded zijn in Microsoft Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="483a5-193">With devices onboarded into Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="483a5-194">In dit scenario is Microsoft Defender voor Eindpunt al geïmplementeerd en zijn er rapportage-eindpunten.</span><span class="sxs-lookup"><span data-stu-id="483a5-194">In this scenario, Microsoft Defender for Endpoint is already deployed and there are endpoints reporting in.</span></span> <span data-ttu-id="483a5-195">Al deze eindpunten worden weergegeven in de lijst met beheerde apparaten.</span><span class="sxs-lookup"><span data-stu-id="483a5-195">All these endpoints will appear in the managed devices list.</span></span> <span data-ttu-id="483a5-196">U kunt nieuwe apparaten blijven gebruiken voor DLP voor eindpunten om de dekking uit te breiden met behulp van de [procedure voor het onboarden van apparaten](endpoint-dlp-getting-started.md#onboarding-devices).</span><span class="sxs-lookup"><span data-stu-id="483a5-196">You can continue to onboard new devices into Endpoint DLP to expand coverage by using the [Onboarding devices procedure](endpoint-dlp-getting-started.md#onboarding-devices).</span></span>

1. <span data-ttu-id="483a5-197">Open het [Microsoft-compliancecentrum](https://compliance.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="483a5-197">Open the [Microsoft compliance center](https://compliance.microsoft.com).</span></span>

2. <span data-ttu-id="483a5-198">Open de instellingenpagina voor het Compliancecentrum en kies **Apparaatcontrole inschakelen**.</span><span class="sxs-lookup"><span data-stu-id="483a5-198">Open the Compliance Center settings page and choose **Enable device monitoring**.</span></span>

3. <span data-ttu-id="483a5-199">Kies **Apparaatbeheer** om de lijst **Apparaten** te openen.</span><span class="sxs-lookup"><span data-stu-id="483a5-199">Choose **Device management** to open the **Devices** list.</span></span> <span data-ttu-id="483a5-200">U ziet nu de lijst met apparaten die al zijn opgenomen in Microsoft Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="483a5-200">You should see the list of devices that are already reporting in to Microsoft Defender for Endpoint.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="483a5-201">![apparaatbeheer](../media/endpoint-dlp-getting-started-2-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="483a5-201">![device management](../media/endpoint-dlp-getting-started-2-device-management.png)</span></span>
   
4. <span data-ttu-id="483a5-202">Kies **Onboarding** als u extra apparaten wilt onboarden.</span><span class="sxs-lookup"><span data-stu-id="483a5-202">Choose **Onboarding** if you need to onboard additional devices.</span></span>

5. <span data-ttu-id="483a5-203">Kies de manier waarop u wilt implementeren op deze extra apparaten in de lijst **Implementatiemethode** en vervolgens **Pakket downloaden**.</span><span class="sxs-lookup"><span data-stu-id="483a5-203">Choose the way you want to deploy to these additional devices from the **Deployment method** list and then **Download package**.</span></span>

6. <span data-ttu-id="483a5-204">Volg de juiste procedures in [Onboarding-hulpprogramma's en -methoden voor Windows 10-computers](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span><span class="sxs-lookup"><span data-stu-id="483a5-204">Follow the appropriate procedures in [Onboarding tools and methods for Windows 10 machines](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span> <span data-ttu-id="483a5-205">Via deze koppeling gaat u naar een landingspagina waar u toegang hebt tot procedures voor Microsoft Defender voor Eindpunt die overeenkomen met het installatiepakket dat u in stap 5 hebt geselecteerd:</span><span class="sxs-lookup"><span data-stu-id="483a5-205">This link takes you to a landing page where you can access Microsoft Defender for Endpoint procedures that match the deployment package you selected in step 5:</span></span>

    - <span data-ttu-id="483a5-206">Windows 10-computers onboarden met groepsbeleid</span><span class="sxs-lookup"><span data-stu-id="483a5-206">Onboard Windows 10 machines using Group Policy</span></span>
    - <span data-ttu-id="483a5-207">Windows-apparaten onboarden met behulp van Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="483a5-207">Onboard Windows machines using Microsoft Endpoint Configuration Manager</span></span>
    - <span data-ttu-id="483a5-208">Windows 10-apparaten onboarden met hulpmiddelen voor Mobiel Apparaatbeheer</span><span class="sxs-lookup"><span data-stu-id="483a5-208">Onboard Windows 10 machines using Mobile Device Management tools</span></span>
    - <span data-ttu-id="483a5-209">Windows 10-apparaten onboarden met een lokaal script</span><span class="sxs-lookup"><span data-stu-id="483a5-209">Onboard Windows 10 machines using a local script</span></span>
    - <span data-ttu-id="483a5-210">Niet-permanente virtuele desktopinfrastructuur (VDI)-apparaten onboarden.</span><span class="sxs-lookup"><span data-stu-id="483a5-210">Onboard non-persistent virtual desktop infrastructure (VDI) machines.</span></span>

<span data-ttu-id="483a5-211">Wanneer dit is gedaan en het eindpunt is onboarded, moet dit zichtbaar zijn in de tabel **Apparaten** en moet u ook auditactiviteitslogboeken rapporteren aan **Activiteitenverkenner**.</span><span class="sxs-lookup"><span data-stu-id="483a5-211">Once done and endpoint is onboarded, it should be visible under the **Devices** table and also start reporting audit logs to the **Activity Explorer**.</span></span>

> [!NOTE]
><span data-ttu-id="483a5-212">Deze ervaring valt onder het afdwingen van licenties.</span><span class="sxs-lookup"><span data-stu-id="483a5-212">This experience is under license enforcement.</span></span> <span data-ttu-id="483a5-213">Zonder de vereiste licentie zijn de gegevens niet zichtbaar of toegankelijk.</span><span class="sxs-lookup"><span data-stu-id="483a5-213">Without the required license, data will not be visible or accessible.</span></span>

### <a name="viewing-endpoint-dlp-alerts-in-dlp-alerts-management-dashboard"></a><span data-ttu-id="483a5-214">DLP-waarschuwingen voor eindpunten weergeven in het dashboard DLP-waarschuwingenbeheer</span><span class="sxs-lookup"><span data-stu-id="483a5-214">Viewing Endpoint DLP alerts in DLP Alerts Management dashboard</span></span>

1. <span data-ttu-id="483a5-215">Ga in het Microsoft 365-compliancecentrum naar de pagina Preventie van gegevensverlies en kies Waarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="483a5-215">Open the Data loss prevention page in the Microsoft 365 Compliance center and choose Alerts.</span></span>

2. <span data-ttu-id="483a5-216">Raadpleeg de procedures in [Informatie over het configureren en weergeven van waarschuwingen voor uw DLP-beleid](dlp-configure-view-alerts-policies.md) om waarschuwingen voor uw DLP-beleid voor eindpunten weer te geven.</span><span class="sxs-lookup"><span data-stu-id="483a5-216">Refer to the procedures in [How to configure and view alerts for your DLP policies](dlp-configure-view-alerts-policies.md) to view alerts for your Endpoint DLP policies.</span></span>


### <a name="viewing-endpoint-dlp-data-in-activity-explorer"></a><span data-ttu-id="483a5-217">DLP-gegevens van eindpunten weergeven in Activiteitenverkenner</span><span class="sxs-lookup"><span data-stu-id="483a5-217">Viewing Endpoint DLP data in activity explorer</span></span>

1. <span data-ttu-id="483a5-218">Open de [pagina Gegevensclassificatie voor](https://compliance.microsoft.com/dataclassification?viewid=overview) uw domein in het Microsoft 365-compliancecentrum en kies Activiteitenverkenner.</span><span class="sxs-lookup"><span data-stu-id="483a5-218">Open the [Data classification page](https://compliance.microsoft.com/dataclassification?viewid=overview) for your domain in the Microsoft 365 Compliance center and choose Activity explorer.</span></span>

2. <span data-ttu-id="483a5-219">Raadpleeg de procedures in [Aan de slag met Activiteitenverkenner](data-classification-activity-explorer.md) om alle gegevens voor uw eindpuntapparaten weer te geven en te filteren.</span><span class="sxs-lookup"><span data-stu-id="483a5-219">Refer to the procedures in [Get started with Activity explorer](data-classification-activity-explorer.md) to access and filter all the data for your Endpoint devices.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="483a5-220">![Activiteitenverkenner-filter voor eindpuntapparaten](../media/endpoint-dlp-4-getting-started-activity-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="483a5-220">![activity explorer filter for endpoint devices](../media/endpoint-dlp-4-getting-started-activity-explorer.png)</span></span>

## <a name="next-steps"></a><span data-ttu-id="483a5-221">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="483a5-221">Next steps</span></span>
<span data-ttu-id="483a5-222">Nu u onboarded-apparaten hebt en de activiteitsgegevens kunt bekijken in Activiteitenverkenner, kunt u verder gaan met de volgende stap, waarin u DLP-beleid maakt voor het beveiligen van uw gevoelige items.</span><span class="sxs-lookup"><span data-stu-id="483a5-222">Now that you have onboarded devices and can view the activity data in Activity explorer, you are ready to move on to your next step where you create DLP policies that protect your sensitive items.</span></span>

- [<span data-ttu-id="483a5-223">Preventie van gegevensverlies voor eindpunten gebruiken</span><span class="sxs-lookup"><span data-stu-id="483a5-223">Using Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="483a5-224">Zie ook</span><span class="sxs-lookup"><span data-stu-id="483a5-224">See also</span></span>

- [<span data-ttu-id="483a5-225">Meer informatie over Preventie van gegevensverlies voor eindpunten</span><span class="sxs-lookup"><span data-stu-id="483a5-225">Learn about Endpoint data loss prevention </span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="483a5-226">Preventie van gegevensverlies voor eindpunten gebruiken</span><span class="sxs-lookup"><span data-stu-id="483a5-226">Using Endpoint data loss prevention </span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="483a5-227">Meer informatie over preventie van gegevensverlies</span><span class="sxs-lookup"><span data-stu-id="483a5-227">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="483a5-228">Een DLP-beleid maken, testen en afstemmen</span><span class="sxs-lookup"><span data-stu-id="483a5-228">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="483a5-229">Aan de slag met de activiteitenverkenner</span><span class="sxs-lookup"><span data-stu-id="483a5-229">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="483a5-230">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="483a5-230">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/)
- [<span data-ttu-id="483a5-231">Hulpmiddelen en methoden onboarden voor Windows 10-apparaten</span><span class="sxs-lookup"><span data-stu-id="483a5-231">Onboarding tools and methods for Windows 10 machines</span></span>](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [<span data-ttu-id="483a5-232">Microsoft 365-abonnement</span><span class="sxs-lookup"><span data-stu-id="483a5-232">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [<span data-ttu-id="483a5-233">Azure AD-gekoppelde apparaten</span><span class="sxs-lookup"><span data-stu-id="483a5-233">Azure AD joined devices</span></span>](/azure/active-directory/devices/concept-azure-ad-join)
- [<span data-ttu-id="483a5-234">De nieuwe Microsoft Edge op basis van Chromium downloaden</span><span class="sxs-lookup"><span data-stu-id="483a5-234">Download the new Microsoft Edge based on Chromium</span></span>](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)