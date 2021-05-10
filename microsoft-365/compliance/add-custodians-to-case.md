---
title: Beheerders toevoegen aan een Advanced eDiscovery zaak
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Meer informatie over het gebruik van het ingebouwde beheerprogramma voor beheerders in Advanced eDiscovery om uw werkstromen te coördineren en relevante gegevensbronnen in een zaak te identificeren.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9468fb889e9115b3652d1dba8a6c6632bb367fe3
ms.sourcegitcommit: 36d12e02f6fda199ae7f2fb72fe52d7e2b5b4efd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/31/2020
ms.locfileid: "52161646"
---
# <a name="add-custodians-to-an-advanced-ediscovery-case"></a><span data-ttu-id="6b1f8-103">Beheerders toevoegen aan een Advanced eDiscovery zaak</span><span class="sxs-lookup"><span data-stu-id="6b1f8-103">Add custodians to an Advanced eDiscovery case</span></span>

<span data-ttu-id="6b1f8-104">Gebruik het ingebouwde beheerprogramma voor beheerders in Advanced eDiscovery om uw werkstromen rond het beheren van beheerders te coördineren en relevante, bewaardergegevensbronnen te identificeren die aan een zaak zijn gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="6b1f8-104">Use the built-in custodian management tool in Advanced eDiscovery to coordinate your workflows around managing custodians and identifying relevant, custodial data sources associated with a case.</span></span> <span data-ttu-id="6b1f8-105">Wanneer u een bewaarder toevoegt, kan het systeem automatisch het postvak en het Exchange in OneDrive voor Bedrijven houden.</span><span class="sxs-lookup"><span data-stu-id="6b1f8-105">When you add a custodian, the system can automatically identify and place a hold on their Exchange mailbox and OneDrive for Business account.</span></span> <span data-ttu-id="6b1f8-106">Tijdens het detectieproces van uw onderzoek kunt u ook andere gegevensbronnen identificeren (zoals postvakken, sites of Teams) die een bewaarder heeft geopend of heeft bijgedragen aan.</span><span class="sxs-lookup"><span data-stu-id="6b1f8-106">During the discovery process of your investigation, you might also identify other data sources (such as mailboxes, sites, or Teams) that a custodian accessed or contributed to.</span></span> <span data-ttu-id="6b1f8-107">In deze situatie kunt u het hulpprogramma voor beheer van beheerders gebruiken om deze gegevensbronnen te koppelen aan een specifieke bewaarder.</span><span class="sxs-lookup"><span data-stu-id="6b1f8-107">In this situation, you can use the custodian management tool to associate those data sources will a specific custodian.</span></span> <span data-ttu-id="6b1f8-108">Nadat u bewaarders aan een zaak hebt toevoegen en andere gegevensbron hieraan hebt koppelen, kunt u snel gegevens bewaren en de bewaargegevens doorzoeken.</span><span class="sxs-lookup"><span data-stu-id="6b1f8-108">After you add custodians to a case and associate other data source with them, you can quickly preserve data and search the custodial data.</span></span>

<span data-ttu-id="6b1f8-109">In vier stappen kunt u beheerders in Advanced eDiscovery toevoegen en beheren:</span><span class="sxs-lookup"><span data-stu-id="6b1f8-109">You can add and manage custodians in Advanced eDiscovery cases in four steps:</span></span>

1. <span data-ttu-id="6b1f8-110">Identificeer de bewaarders.</span><span class="sxs-lookup"><span data-stu-id="6b1f8-110">Identify the custodians.</span></span>

2. <span data-ttu-id="6b1f8-111">Kies bewaarlocaties voor gegevens.</span><span class="sxs-lookup"><span data-stu-id="6b1f8-111">Choose custodian data locations.</span></span>

3. <span data-ttu-id="6b1f8-112">Instellingen voor wacht houden configureren.</span><span class="sxs-lookup"><span data-stu-id="6b1f8-112">Configure hold settings.</span></span>

4. <span data-ttu-id="6b1f8-113">Controleer de bewaarders en voltooi het proces.</span><span class="sxs-lookup"><span data-stu-id="6b1f8-113">Review the custodians and complete the process.</span></span>

   <span data-ttu-id="6b1f8-114">[![Tabblad Bronnen in Advanced eDiscovery geval ](../media/AeD-Sources-Tab.png)](../media/AeD-Sources-Tab.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="6b1f8-114">[ ![Sources tab in Advanced eDiscovery case](../media/AeD-Sources-Tab.png) ](../media/AeD-Sources-Tab.png#lightbox)</span></span>

## <a name="make-sure-you-have-the-necessary-permissions"></a><span data-ttu-id="6b1f8-115">Zorg ervoor dat u de benodigde machtigingen hebt</span><span class="sxs-lookup"><span data-stu-id="6b1f8-115">Make sure you have the necessary permissions</span></span>

<span data-ttu-id="6b1f8-116">Als u beheerders aan een zaak wilt toevoegen, moet u lid zijn van de rollengroep eDiscovery Manager.</span><span class="sxs-lookup"><span data-stu-id="6b1f8-116">To add custodians to a case, you must be a member of the eDiscovery Manager role group.</span></span> <span data-ttu-id="6b1f8-117">Hiermee beschikt u over de benodigde machtigingen om beheerders toe te voegen aan een zaak en de bewaargegevensbronnen in de wacht te zetten.</span><span class="sxs-lookup"><span data-stu-id="6b1f8-117">This provides you with the necessary permissions to add custodians to a case and place a hold on the custodial data sources.</span></span> <span data-ttu-id="6b1f8-118">Zie [eDiscovery-machtigingen](get-started-with-advanced-ediscovery.md#step-2-assign-ediscovery-permissions)toewijzen voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="6b1f8-118">For more information, see [Assign eDiscovery permissions](get-started-with-advanced-ediscovery.md#step-2-assign-ediscovery-permissions).</span></span>

## <a name="step-1-identify-custodians"></a><span data-ttu-id="6b1f8-119">Stap 1: beheerders identificeren</span><span class="sxs-lookup"><span data-stu-id="6b1f8-119">Step 1: Identify custodians</span></span>

1. <span data-ttu-id="6b1f8-120">Ga naar en meld u aan met een gebruikersaccount dat is toegewezen aan de juiste [https://compliance.microsoft.com](https://compliance.microsoft.com) eDiscovery-machtigingen.</span><span class="sxs-lookup"><span data-stu-id="6b1f8-120">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and sign in with a user account that has been assigned the appropriate eDiscovery permissions.</span></span>

2. <span data-ttu-id="6b1f8-121">Klik in het linkernavigatiedeelvenster van het Microsoft 365 compliancecentrum op **Alles weergeven** en klik vervolgens op **eDiscovery > Geavanceerd.**</span><span class="sxs-lookup"><span data-stu-id="6b1f8-121">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **eDiscovery > Advanced**.</span></span>

3. <span data-ttu-id="6b1f8-122">Klik op **Advanced eDiscovery** pagina op **het** tabblad Gevallen en selecteer vervolgens de zaak aan wie u bewaarders wilt toevoegen.</span><span class="sxs-lookup"><span data-stu-id="6b1f8-122">On the **Advanced eDiscovery** page, click the **Cases** tab, and then select the case that you want to add custodians to.</span></span>

4. <span data-ttu-id="6b1f8-123">Klik op **het tabblad Gegevensbronnen** en klik vervolgens **op Gegevensbron toevoegen** Nieuwe beheerders  >  **toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="6b1f8-123">Click the **Data sources** tab and then click **Add data source** > **Add new custodians**.</span></span>

5. <span data-ttu-id="6b1f8-124">Voeg een of meer gebruikers in uw organisatie als voogd toe aan de zaak door het eerste deel van de naam of alias van een persoon te typen.</span><span class="sxs-lookup"><span data-stu-id="6b1f8-124">Add one or more users in your organization as custodians to the case by typing the first part of a person's name or alias.</span></span> <span data-ttu-id="6b1f8-125">Nadat u de juiste persoon hebt gevonden, selecteert u de naam om deze toe te voegen aan de lijst.</span><span class="sxs-lookup"><span data-stu-id="6b1f8-125">After you find the correct person, select their name to add them to the list.</span></span>

## <a name="step-2-choose-custodian-data-locations"></a><span data-ttu-id="6b1f8-126">Stap 2: Locaties voor bewaargegevens kiezen</span><span class="sxs-lookup"><span data-stu-id="6b1f8-126">Step 2: Choose custodian data locations</span></span>

<span data-ttu-id="6b1f8-127">Nadat u beheerders hebt geselecteerd, probeert het systeem deze gebruikers en hun gegevensbronnen automatisch te identificeren en te verifiëren.</span><span class="sxs-lookup"><span data-stu-id="6b1f8-127">After you select custodians, the system automatically attempts to identify and verify these users and their data sources.</span></span> <span data-ttu-id="6b1f8-128">Nadat u beheerders aan de lijst hebt toegevoegd, bevat het hulpprogramma automatisch het primaire postvak en OneDrive account voor elke bewaarder.</span><span class="sxs-lookup"><span data-stu-id="6b1f8-128">After adding custodians to the list, the tool automatically includes the primary mailbox and OneDrive account for each custodian.</span></span> <span data-ttu-id="6b1f8-129">U kunt ervoor kiezen deze gegevensbronnen niet op te nemen wanneer u beheerders toevoegt aan de zaak.</span><span class="sxs-lookup"><span data-stu-id="6b1f8-129">You can choose not to include these data sources when adding custodians to the case.</span></span>

<span data-ttu-id="6b1f8-130">Naast het postvak en OneDrive-account van een bewaarder kunt u ook andere gegevenslocaties koppelen aan een bewaarder, zoals een SharePoint-site of een Microsoft-team waar de bewaarder lid van is.</span><span class="sxs-lookup"><span data-stu-id="6b1f8-130">In addition to a custodian's mailbox and OneDrive account, you can also associate other data locations to a custodian, such as SharePoint site or a Microsoft Team the custodian is a member of.</span></span> <span data-ttu-id="6b1f8-131">Op deze manier kunt u inhoud bewaren, verzamelen, analyseren en controleren in andere gegevensbronnen die zijn gekoppeld aan de bewaarders van de zaak.</span><span class="sxs-lookup"><span data-stu-id="6b1f8-131">This allows you to preserve, collect, analyze, and review content in other data sources associated with the custodians of the case.</span></span>

<span data-ttu-id="6b1f8-132">Deselecteer het primaire postvak en OneDrive account voor een bewaarder:</span><span class="sxs-lookup"><span data-stu-id="6b1f8-132">To deselect the primary mailbox and OneDrive account for a custodian:</span></span>

1. <span data-ttu-id="6b1f8-133">Vouw de bewaarder uit om de primaire gegevenslocaties weer te geven die automatisch aan elke bewaarder zijn gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="6b1f8-133">Expand the custodian to view the primary data locations that have been automatically associated to each custodian.</span></span>

2. <span data-ttu-id="6b1f8-134">Selecteer **Verwijderen** naast **Postvak** of **OneDrive** om te verwijderen dat het postvak of OneDrive account van een beheerder is gekoppeld aan een gegevenslocatie voor deze bewaarder.</span><span class="sxs-lookup"><span data-stu-id="6b1f8-134">Select **Clear** next to **Mailbox** or **OneDrive** to remove a custodian's mailbox or OneDrive account from being associated as a data location for this custodian.</span></span>

   ![Locaties configureren om te koppelen aan een bewaarder](../media/ConfigureCustodianLocations.png)

<span data-ttu-id="6b1f8-136">Als u andere postvakken, sites, Teams of Yammer wilt koppelen aan een specifieke bewaarder:</span><span class="sxs-lookup"><span data-stu-id="6b1f8-136">To associate other mailboxes, sites, Teams, or Yammer groups to a specific custodian:</span></span>

1. <span data-ttu-id="6b1f8-137">Vouw een bewaarder uit om de volgende services weer te geven om gegevenslocaties te koppelen aan de bewaarder.</span><span class="sxs-lookup"><span data-stu-id="6b1f8-137">Expand a custodian to display the following services to associate data locations with the custodian.</span></span> <span data-ttu-id="6b1f8-138">Klik **op Bewerken** naast een service om een gegevenslocatie toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="6b1f8-138">Click **Edit** next to a service to add a data location.</span></span>

   - <span data-ttu-id="6b1f8-139">**Exchange:** Gebruik dit om andere postvakken aan de beheerder te koppelen.</span><span class="sxs-lookup"><span data-stu-id="6b1f8-139">**Exchange**: Use to associate other mailboxes to the custodian.</span></span> <span data-ttu-id="6b1f8-140">Typ in het zoekvak de naam of alias (minimaal drie tekens) van gebruikerspostvakken of distributiegroepen.</span><span class="sxs-lookup"><span data-stu-id="6b1f8-140">Type into the search box the name or alias (a minimum of three characters) of user mailboxes or distribution groups.</span></span> <span data-ttu-id="6b1f8-141">Selecteer de postvakken die u wilt toewijzen aan de beheerder en klik vervolgens op **Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="6b1f8-141">Select the mailboxes to assign to the custodian and then click **Add**.</span></span>

   - <span data-ttu-id="6b1f8-142">**SharePoint**: Gebruik deze SharePoint sites aan de beheerder.</span><span class="sxs-lookup"><span data-stu-id="6b1f8-142">**SharePoint**: Use to associate SharePoint sites to the custodian.</span></span> <span data-ttu-id="6b1f8-143">Selecteer een site in de lijst of zoek naar een site door een URL in het zoekvak te typen.</span><span class="sxs-lookup"><span data-stu-id="6b1f8-143">Select a site in the list or search for a site by typing a URL in the search box.</span></span> <span data-ttu-id="6b1f8-144">Selecteer de sites die u wilt toewijzen aan de beheerder en klik vervolgens op **Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="6b1f8-144">Select the sites to assign to the custodian and then click **Add**.</span></span>

   - <span data-ttu-id="6b1f8-145">**Teams**: Gebruik dit om de Microsoft Teams toe te wijzen waar de bewaarder momenteel lid van is.</span><span class="sxs-lookup"><span data-stu-id="6b1f8-145">**Teams**: Use to assign the Microsoft Teams the custodian is currently a member of.</span></span> <span data-ttu-id="6b1f8-146">Selecteer de teams die u wilt toewijzen aan de bewaarder en klik vervolgens op **Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="6b1f8-146">Select the teams to assign to the custodian and then click **Add**.</span></span> <span data-ttu-id="6b1f8-147">Nadat u een team hebt toevoegen, identificeert en zoekt het systeem automatisch de SharePoint site en het groepspostvak die aan dat team zijn gekoppeld en wijst het deze toe aan de beheerder.</span><span class="sxs-lookup"><span data-stu-id="6b1f8-147">After you add a team, the system automatically identifies and locates the SharePoint site and group mailbox associated to that team and assigns them to the custodian.</span></span>

   - <span data-ttu-id="6b1f8-148">**Yammer**: Gebruik deze Yammer groepen waar de bewaarder momenteel lid van is.</span><span class="sxs-lookup"><span data-stu-id="6b1f8-148">**Yammer**:  Use to assign the Yammer groups the custodian is currently a member of.</span></span> <span data-ttu-id="6b1f8-149">Selecteer de groepen die u wilt toewijzen aan de beheerder en klik vervolgens op **Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="6b1f8-149">Select the groups to assign to the custodian and then click **Add**.</span></span> <span data-ttu-id="6b1f8-150">Nadat u een team hebt toevoegen, identificeert en zoekt het systeem automatisch de SharePoint site en het groepspostvak dat aan die groep is gekoppeld en wijst het deze toe aan de beheerder.</span><span class="sxs-lookup"><span data-stu-id="6b1f8-150">After you add a team, the system automatically identifies and locates the SharePoint site and group mailbox associated to that group and assigns them to the custodian.</span></span>

   > [!NOTE]
   > <span data-ttu-id="6b1f8-151">U kunt de **Exchange** en **SharePoint** locatie pickers gebruiken om andere teams of Yammer groepen (waar een bewaarder geen lid van is) aan een bewaarder te koppelen.</span><span class="sxs-lookup"><span data-stu-id="6b1f8-151">You can use the **Exchange** and **SharePoint** location pickers to associate other teams or Yammer groups (that a custodian is not a member of) to a custodian.</span></span> <span data-ttu-id="6b1f8-152">Hiervoor moet u zowel het postvak als de site toevoegen die aan elk team of elke groep Yammer gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="6b1f8-152">To do this, you have to add both the mailbox and site associated with each team or Yammer group.</span></span>

2. <span data-ttu-id="6b1f8-153">U kunt het totale aantal postvakken, sites, Teams en Yammer groepen weergeven dat aan elke bewaarder is toegewezen door elke bewaarder in de tabel uit te breiden.</span><span class="sxs-lookup"><span data-stu-id="6b1f8-153">You can view the total number of mailboxes, sites, Teams, and Yammer groups assigned to each custodian by expanding each custodian in the table.</span></span> <span data-ttu-id="6b1f8-154">Wanneer u de toegewezen gegevenslocaties voor elke bewaarder hebt afgerond, worden deze associaties bijgehouden en gebruikt tijdens het verzamelen, verwerken en controleren van stadia in de Advanced eDiscovery werkstroom.</span><span class="sxs-lookup"><span data-stu-id="6b1f8-154">When you've finalized the assigned data locations for each custodian, these associations will be maintained and used during the collection, processing, and review stages in the Advanced eDiscovery workflow.</span></span>

3. <span data-ttu-id="6b1f8-155">Nadat u beheerders hebt toegevoegd en hun gegevenslocaties hebt geconfigureerd, klikt u op **Volgende** om naar de pagina Instellingen voor wacht **houden te** gaan.</span><span class="sxs-lookup"><span data-stu-id="6b1f8-155">After adding custodians and configuring their data locations, click **Next** to go to the **Hold settings** page.</span></span>  

## <a name="step-3-configure-hold-settings"></a><span data-ttu-id="6b1f8-156">Stap 3: Instellingen voor wacht houden configureren</span><span class="sxs-lookup"><span data-stu-id="6b1f8-156">Step 3: Configure hold settings</span></span>

 <span data-ttu-id="6b1f8-157">Nadat u de bewaarders en hun gegevenslocaties hebt afgerond, kunt u sommige of alle bewaarders in de wachtstand plaatsen.</span><span class="sxs-lookup"><span data-stu-id="6b1f8-157">After you've finalized the custodians and their data locations, you can place some or all of the custodians on hold.</span></span> <span data-ttu-id="6b1f8-158">Wanneer u een bewaarder in de wacht zet, blijft alle inhoud op alle inhoudslocaties die aan de bewaarder zijn gekoppeld, bewaard totdat u de bewaarplaats verwijdert of de bewaarder uit de wacht houdt.</span><span class="sxs-lookup"><span data-stu-id="6b1f8-158">When you place a custodian on hold, all content in all content locations that are associated with the custodian is preserved until you remove the hold or release the custodian from the hold.</span></span> <span data-ttu-id="6b1f8-159">In sommige gevallen wilt u mogelijk beheerders toevoegen aan een zaak zonder ze in de wacht te zetten.</span><span class="sxs-lookup"><span data-stu-id="6b1f8-159">In some cases, you may want to add custodians to a case without placing them on hold.</span></span>

<span data-ttu-id="6b1f8-160">De bewaarders en gegevensbronnen in de wacht zetten:</span><span class="sxs-lookup"><span data-stu-id="6b1f8-160">To place the custodians and data sources on hold:</span></span>

1. <span data-ttu-id="6b1f8-161">Op de **pagina Instellingen in** wacht houden kunt u een hold toepassen op afzonderlijke beheerders door het selectievakje onder de kolom Wacht houden in **te** selecteren.</span><span class="sxs-lookup"><span data-stu-id="6b1f8-161">On the **Hold settings** page, you can apply a hold to individual custodians by selecting the checkbox under the **Hold** column.</span></span>

   <span data-ttu-id="6b1f8-162">U kunt ook alle bewaarders in de wacht zetten door het **selectievakje** Wacht houden boven aan de kolom in te selecteren.</span><span class="sxs-lookup"><span data-stu-id="6b1f8-162">Alternatively, you can place all custodians on hold by selecting the **Hold** checkbox at the top of the column.</span></span>

2. <span data-ttu-id="6b1f8-163">Controleer de bewaarselecties en klik vervolgens op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="6b1f8-163">Verify the custodian hold selections and then click **Next**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="6b1f8-164">Als u een bewaarder niet in de wacht houdt, worden de bewaarder en de bijbehorende gegevensbronnen aan de zaak toegevoegd, maar blijft de inhoud in deze gegevensbronnen niet behouden door de bewaarplaats die aan de zaak is gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="6b1f8-164">If you don't place a hold on a custodian, the custodian and their associated data sources will be added to the case but the content in those data sources won't preserved by the hold that associated with the case.</span></span>

## <a name="step-4-review-the-custodians-and-complete-the-process"></a><span data-ttu-id="6b1f8-165">Stap 4: De beheerders controleren en het proces voltooien</span><span class="sxs-lookup"><span data-stu-id="6b1f8-165">Step 4: Review the custodians and complete the process</span></span>

<span data-ttu-id="6b1f8-166">Voordat u de bewaarders daadwerkelijk aan de zaak toevoegt, kunt u de lijst met bewaarders, de gegevenslocaties die aan hen zijn toegewezen en de bewaarinstellingen bekijken.</span><span class="sxs-lookup"><span data-stu-id="6b1f8-166">Before you actually add the custodians to the case, you can review the list of custodians, the data locations assigned to them, and the hold settings.</span></span>

1. <span data-ttu-id="6b1f8-167">Controleer en controleer het aantal gegevensbronnen en de bewaarinstelling die is gekoppeld aan elke bewaarder in de tabel.</span><span class="sxs-lookup"><span data-stu-id="6b1f8-167">Verify and review all the data sources count and the hold setting associated with each custodian in the table.</span></span> <span data-ttu-id="6b1f8-168">Ga zo nodig terug naar de  **pagina's Instellingen** identificeren of Bewaren om wijzigingen aan te brengen.</span><span class="sxs-lookup"><span data-stu-id="6b1f8-168">If necessary, go back to the **Identify custodian** or **Hold settings** pages to make any changes.</span></span>

2. <span data-ttu-id="6b1f8-169">Klik **op Verzenden** om bewaarders en hun gegevenslocaties aan de zaak toe te voegen en alle instellingen voor bewaarzorg toe te passen.</span><span class="sxs-lookup"><span data-stu-id="6b1f8-169">Click **Submit** to add custodians and their data locations to the case and apply all custodial hold settings.</span></span>

   <span data-ttu-id="6b1f8-170">De nieuwe bewaarders worden toegevoegd aan de zaak en worden weergegeven op het **tabblad Gegevensbronnen.**</span><span class="sxs-lookup"><span data-stu-id="6b1f8-170">The new custodians are added to the case and displayed on the **Data sources** tab.</span></span>

   <span data-ttu-id="6b1f8-171">[![Bewaarders die worden vermeld op het tabblad Gegevensbronnen ](../media/DataSourcesTab.png)](../media/DataSourcesTab.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="6b1f8-171">[ ![Custodians listed on the Data sources tab](../media/DataSourcesTab.png) ](../media/DataSourcesTab.png#lightbox)</span></span>