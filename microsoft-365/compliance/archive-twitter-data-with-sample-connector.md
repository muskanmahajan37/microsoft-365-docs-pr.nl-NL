---
title: Een connector instellen voor het archiveren van Twitter-gegevens
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: seo-marvel-apr2020
description: Lees hoe beheerders een native connector kunnen instellen en gebruiken om Twitter-gegevens te importeren in Microsoft 365.
ms.openlocfilehash: 277af8ea7367936c4c9528a8ca50ccd678745bf6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162076"
---
# <a name="set-up-a-connector-to-archive-twitter-data-preview"></a><span data-ttu-id="27ebd-103">Een verbindingslijn instellen voor het archiveren van Twitter-gegevens (preview)</span><span class="sxs-lookup"><span data-stu-id="27ebd-103">Set up a connector to archive Twitter data (preview)</span></span>

<span data-ttu-id="27ebd-104">Gebruik een connector in het Microsoft 365 compliancecentrum om gegevens van Twitter te importeren en te archiveren Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="27ebd-104">Use a connector in the Microsoft 365 compliance center to import and archive data from Twitter to Microsoft 365.</span></span> <span data-ttu-id="27ebd-105">Nadat u de verbindingslijn hebt ingesteld en geconfigureerd, wordt er verbinding gemaakt met het Twitter-account van uw organisatie (op een geplande basis), wordt de inhoud van een item geconverformeerd naar een e-mailberichtindeling en worden deze items vervolgens geïmporteerd in een postvak in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="27ebd-105">After you set up and configure the connector, it connects to your organization's Twitter account (on a scheduled basis), converts the content of an item to an email message format, and then imports those items to a mailbox in Microsoft 365.</span></span>

<span data-ttu-id="27ebd-106">Nadat de Twitter-gegevens zijn geïmporteerd, kunt u Microsoft 365 compliancefuncties zoals Procesvoering, Inhoud zoeken, In-Place Archiveren, Auditing en Microsoft 365 bewaarbeleid toepassen op de Twitter-gegevens.</span><span class="sxs-lookup"><span data-stu-id="27ebd-106">After the Twitter data is imported, you can apply Microsoft 365 compliance features such as Litigation Hold, Content Search, In-Place Archiving, Auditing, and Microsoft 365 retention policies to the Twitter data.</span></span> <span data-ttu-id="27ebd-107">Als een postvak bijvoorbeeld in de bewaring van rechtszaken wordt geplaatst of is toegewezen aan een bewaarbeleid, blijven de Twitter-gegevens behouden.</span><span class="sxs-lookup"><span data-stu-id="27ebd-107">For example, when a mailbox is placed on Litigation Hold or assigned to a retention policy, the Twitter data is preserved.</span></span> <span data-ttu-id="27ebd-108">U kunt gegevens van derden doorzoeken met Inhoud zoeken of het postvak koppelen waarin de Twitter-gegevens zijn opgeslagen met een bewaarder in een Advanced eDiscovery geval.</span><span class="sxs-lookup"><span data-stu-id="27ebd-108">You can search third-party data using Content Search or associate the mailbox where the Twitter data is stored with a custodian in an Advanced eDiscovery case.</span></span> <span data-ttu-id="27ebd-109">Met een connector voor het importeren en archiveren van Twitter-gegevens in Microsoft 365 kan uw organisatie voldoen aan overheids- en regelgevingsbeleid.</span><span class="sxs-lookup"><span data-stu-id="27ebd-109">Using a connector to import and archive Twitter data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

<span data-ttu-id="27ebd-110">Nadat Twitter-gegevens zijn geïmporteerd, kunt u Microsoft 365 compliancefuncties zoals Procesvoering, Inhoud zoeken, In-Place Archiveren, Auditing, Communicatie compliance en Microsoft 365 bewaarbeleid toepassen op de gegevens die zijn opgeslagen in het postvak.</span><span class="sxs-lookup"><span data-stu-id="27ebd-110">After Twitter data is imported, you can apply Microsoft 365 compliance features such as Litigation Hold, Content Search, In-Place Archiving, Auditing, Communication compliance, and Microsoft 365 retention policies to the data stored in the mailbox.</span></span> <span data-ttu-id="27ebd-111">U kunt bijvoorbeeld zoeken in Twitter-gegevens met Inhoud zoeken of het postvak koppelen waarin de gegevens zijn opgeslagen aan een bewaarder in een Advanced eDiscovery geval.</span><span class="sxs-lookup"><span data-stu-id="27ebd-111">For example, you can search Twitter data using Content Search or associate the mailbox where the data is stored with a custodian in an Advanced eDiscovery case.</span></span> <span data-ttu-id="27ebd-112">Met een connector voor het importeren en archiveren van Twitter-gegevens in Microsoft 365 kan uw organisatie voldoen aan overheids- en regelgevingsbeleid.</span><span class="sxs-lookup"><span data-stu-id="27ebd-112">Using a connector to import and archive Twitter data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="before-you-set-up-a-connector"></a><span data-ttu-id="27ebd-113">Voordat u een verbindingslijn in stelt</span><span class="sxs-lookup"><span data-stu-id="27ebd-113">Before you set up a connector</span></span>

<span data-ttu-id="27ebd-114">Voltooi de volgende vereisten voordat u een connector kunt instellen en configureren in het Microsoft 365 compliancecentrum om gegevens te importeren en te archiveren vanuit het Twitter-account van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="27ebd-114">Complete the following prerequisites before you can set up and configure a connector in the Microsoft 365 compliance center to import and archive data from your organization's Twitter account.</span></span>

- <span data-ttu-id="27ebd-115">U hebt een Twitter-account voor uw organisatie nodig. u moet zich aanmelden bij dit account bij het instellen van de verbindingslijn.</span><span class="sxs-lookup"><span data-stu-id="27ebd-115">You need a Twitter account for your organization; you need to sign in to this account when setting up the connector.</span></span>

- <span data-ttu-id="27ebd-116">Uw organisatie moet een geldig Azure-abonnement hebben.</span><span class="sxs-lookup"><span data-stu-id="27ebd-116">Your organization must have a valid Azure subscription.</span></span> <span data-ttu-id="27ebd-117">Als u geen bestaand Azure-abonnement hebt, kunt u zich registreren voor een van de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="27ebd-117">If you don't have an existing Azure subscription, you can sign up for one of these options:</span></span>

    - [<span data-ttu-id="27ebd-118">Registreren voor een gratis Azure-abonnement van één jaar</span><span class="sxs-lookup"><span data-stu-id="27ebd-118">Sign up for a free one year Azure subscription</span></span>](https://azure.microsoft.com/free) 

    - [<span data-ttu-id="27ebd-119">Registreren voor een Pay-As-You-Go Azure-abonnement</span><span class="sxs-lookup"><span data-stu-id="27ebd-119">Sign up for a Pay-As-You-Go Azure subscription</span></span>](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > <span data-ttu-id="27ebd-120">Het [gratis Azure Active Directory](use-your-free-azure-ad-subscription-in-office-365.md) abonnement dat is inbegrepen bij uw Microsoft 365-abonnement biedt geen ondersteuning voor de connectors in het beveiligings- & compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="27ebd-120">The [free Azure Active Directory subscription](use-your-free-azure-ad-subscription-in-office-365.md) that's included with your Microsoft 365 subscription doesn't support the connectors in the Security & Compliance Center.</span></span>

- <span data-ttu-id="27ebd-121">De Twitter-connector kan in totaal 200.000 items in één dag importeren.</span><span class="sxs-lookup"><span data-stu-id="27ebd-121">The Twitter connector can import a total of 200,000 items in a single day.</span></span> <span data-ttu-id="27ebd-122">Als er meer dan 200.000 Twitter-items in een dag zijn, worden geen van deze items geïmporteerd in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="27ebd-122">If there are more than 200,000 Twitter items in a day, none of those items will be imported to Microsoft 365.</span></span>

- <span data-ttu-id="27ebd-123">De gebruiker die de Twitter-connector in het Microsoft 365 compliancecentrum (in stap 5) in stelt, moet de rol Postvak importeren exporteren in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="27ebd-123">The user who sets up the Twitter connector in the Microsoft 365 compliance center (in Step 5) must be assigned the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="27ebd-124">Deze rol is standaard niet toegewezen aan een rollengroep in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="27ebd-124">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="27ebd-125">U kunt de rol Postvak importeren exporteren toevoegen aan de rollengroep Organisatiebeheer in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="27ebd-125">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="27ebd-126">U kunt ook een rollengroep maken, de rol Postvak importeren exporteren toewijzen en vervolgens de juiste gebruikers toevoegen als leden.</span><span class="sxs-lookup"><span data-stu-id="27ebd-126">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="27ebd-127">Zie de secties [](/Exchange/permissions-exo/role-groups#create-role-groups) Rollengroepen [](/Exchange/permissions-exo/role-groups#modify-role-groups) maken of Rollengroepen wijzigen in het artikel 'Rollengroepen beheren in Exchange Online'.</span><span class="sxs-lookup"><span data-stu-id="27ebd-127">For more information, see the  [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-create-an-app-in-azure-active-directory"></a><span data-ttu-id="27ebd-128">Stap 1: Een app maken in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="27ebd-128">Step 1: Create an app in Azure Active Directory</span></span>

<span data-ttu-id="27ebd-129">De eerste stap is het registreren van een nieuwe app in Azure Active Directory (AAD).</span><span class="sxs-lookup"><span data-stu-id="27ebd-129">The first step is to register a new app in Azure Active Directory (AAD).</span></span> <span data-ttu-id="27ebd-130">Deze app komt overeen met de web-app-resource die u implementeert in stap 2 voor de Twitter-connector.</span><span class="sxs-lookup"><span data-stu-id="27ebd-130">This app corresponds to the web app resource that you implement in Step 2 for the Twitter connector.</span></span>

<span data-ttu-id="27ebd-131">Zie Een app maken in Azure Active Directory voor [stapsgewijse instructies.](deploy-twitter-connector.md#step-1-create-an-app-in-azure-active-directory)</span><span class="sxs-lookup"><span data-stu-id="27ebd-131">For step-by-step instructions, see [Create an app in Azure Active Directory](deploy-twitter-connector.md#step-1-create-an-app-in-azure-active-directory).</span></span>

<span data-ttu-id="27ebd-132">Tijdens het voltooien van deze stap (door de stapsgewijs instructies te volgen), worden de volgende gegevens opgeslagen in een tekstbestand.</span><span class="sxs-lookup"><span data-stu-id="27ebd-132">During the completion of this step (by following the step-by-step instructions), you'll save the following information to a text file.</span></span> <span data-ttu-id="27ebd-133">Deze waarden worden gebruikt in latere stappen in het implementatieproces.</span><span class="sxs-lookup"><span data-stu-id="27ebd-133">These values will be used in later steps in the deployment process.</span></span>

- <span data-ttu-id="27ebd-134">AAD-toepassings-id</span><span class="sxs-lookup"><span data-stu-id="27ebd-134">AAD application ID</span></span>

- <span data-ttu-id="27ebd-135">AAD-toepassingsgeheim</span><span class="sxs-lookup"><span data-stu-id="27ebd-135">AAD application secret</span></span>

- <span data-ttu-id="27ebd-136">Tenant-id</span><span class="sxs-lookup"><span data-stu-id="27ebd-136">Tenant Id</span></span>

## <a name="step-2-deploy-connector-web-service-from-github-repository-to-your-azure-account"></a><span data-ttu-id="27ebd-137">Stap 2: Connectorwebservice implementeren van GitHub repository naar uw Azure-account</span><span class="sxs-lookup"><span data-stu-id="27ebd-137">Step 2: Deploy connector web service from GitHub repository to your Azure account</span></span>

<span data-ttu-id="27ebd-138">De volgende stap is het implementeren van de broncode voor de Twitter-connector-app waarmee twitter-API wordt gebruikt om verbinding te maken met uw Twitter-account en gegevens op te halen, zodat u deze kunt importeren in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="27ebd-138">The next step is to deploy the source code for the Twitter connector app that will use Twitter API to connect to your Twitter account and extract data so you can import it to Microsoft 365.</span></span> <span data-ttu-id="27ebd-139">De Twitter-connector die u voor uw organisatie implementeert, uploadt de items van het Twitter-account van uw organisatie naar de Azure Storage locatie die in deze stap is gemaakt.</span><span class="sxs-lookup"><span data-stu-id="27ebd-139">The Twitter connector that you deploy for your organization will upload the items from your organization's Twitter account to the Azure Storage location that is created in this step.</span></span> <span data-ttu-id="27ebd-140">Nadat u een Twitter-connector hebt gemaakt in het Microsoft 365 compliancecentrum (in stap 5), kopieert de service Microsoft 365 Importeren de Twitter-gegevens van de Azure Storage-locatie naar een postvak in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="27ebd-140">After you create a Twitter connector in the Microsoft 365 compliance center (in Step 5), the Microsoft 365 Import service will copy the Twitter data from the Azure Storage location to a mailbox in Microsoft 365.</span></span> <span data-ttu-id="27ebd-141">Zoals eerder is uitgelegd in de sectie Voordat [u een](#before-you-set-up-a-connector) verbindingslijn in stelt, moet u een geldig Azure-abonnement hebben om een Azure Storage maken.</span><span class="sxs-lookup"><span data-stu-id="27ebd-141">As previous explained in the [Before you set up a connector](#before-you-set-up-a-connector) section, you must have a valid Azure subscription to create an Azure Storage account.</span></span>

<span data-ttu-id="27ebd-142">De broncode voor de Twitter-connector-app implementeren:</span><span class="sxs-lookup"><span data-stu-id="27ebd-142">To deploy the source code for the Twitter connector app:</span></span>

1. <span data-ttu-id="27ebd-143">Ga naar [deze GitHub site.](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet)</span><span class="sxs-lookup"><span data-stu-id="27ebd-143">Go to [this GitHub site](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet).</span></span>

2. <span data-ttu-id="27ebd-144">Klik **op Implementeren naar Azure.**</span><span class="sxs-lookup"><span data-stu-id="27ebd-144">Click **Deploy to Azure**.</span></span>

<span data-ttu-id="27ebd-145">Zie De connectorwebservice implementeren van GitHub azure-account voor [stapsgewijse instructies.](deploy-twitter-connector.md#step-2-deploy-the-connector-web-service-from-github-to-your-azure-account)</span><span class="sxs-lookup"><span data-stu-id="27ebd-145">For step-by-step instructions, see [Deploy the connector web service from GitHub to your Azure account](deploy-twitter-connector.md#step-2-deploy-the-connector-web-service-from-github-to-your-azure-account).</span></span>

<span data-ttu-id="27ebd-146">Terwijl u de stapsgewijse instructies volgt om deze stap te voltooien, geeft u de volgende informatie op</span><span class="sxs-lookup"><span data-stu-id="27ebd-146">While you follow the step-by-step instructions to complete this step, you provide the following information</span></span>

- <span data-ttu-id="27ebd-147">APISecretKey: u maakt dit geheim tijdens de voltooiing van deze stap.</span><span class="sxs-lookup"><span data-stu-id="27ebd-147">APISecretKey: You create this secret during the completion of this step.</span></span> <span data-ttu-id="27ebd-148">Deze wordt gebruikt in stap 5.</span><span class="sxs-lookup"><span data-stu-id="27ebd-148">It's used in Step 5.</span></span>

- <span data-ttu-id="27ebd-149">tenantId: De tenant-id van uw Microsoft 365 organisatie die u hebt gekopieerd na het maken van de Twitter-app in Azure Active Directory stap 1.</span><span class="sxs-lookup"><span data-stu-id="27ebd-149">tenantId: The tenant ID of your Microsoft 365 organization that you copied after creating the Twitter app in Azure Active Directory in Step 1.</span></span>

<span data-ttu-id="27ebd-150">Nadat u deze stap hebt doorlopen, moet u de app Service-URL kopiëren `https://twitterconnector.azurewebsites.net` (bijvoorbeeld).</span><span class="sxs-lookup"><span data-stu-id="27ebd-150">After completing this step, be sure to copy the app Service URL (for example, `https://twitterconnector.azurewebsites.net`).</span></span> <span data-ttu-id="27ebd-151">U moet deze URL gebruiken om stap 3, stap 4 en stap 5 te voltooien.</span><span class="sxs-lookup"><span data-stu-id="27ebd-151">You need to use this URL to complete Step 3, Step 4, and Step 5).</span></span>

## <a name="step-3-create-developer-app-on-twitter"></a><span data-ttu-id="27ebd-152">Stap 3: Ontwikkelaars-app maken op Twitter</span><span class="sxs-lookup"><span data-stu-id="27ebd-152">Step 3: Create developer app on Twitter</span></span>

<span data-ttu-id="27ebd-153">De volgende stap is het maken en configureren van een ontwikkelaars-app op Twitter.</span><span class="sxs-lookup"><span data-stu-id="27ebd-153">The next step is to create and configure a developer app on Twitter.</span></span> <span data-ttu-id="27ebd-154">De aangepaste connector die u in stap 7 maakt, gebruikt de Twitter-app om te communiceren met de Twitter-API om gegevens te verkrijgen uit het Twitter-account van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="27ebd-154">The custom connector that you create in Step 7 uses the Twitter app to interact with the Twitter API to obtain data from your organization's Twitter account.</span></span>

<span data-ttu-id="27ebd-155">Zie De [Twitter-app maken](deploy-twitter-connector.md#step-3-create-the-twitter-app)voor stapsgewijse instructies.</span><span class="sxs-lookup"><span data-stu-id="27ebd-155">For step-by-step instructions, see [Create the Twitter app](deploy-twitter-connector.md#step-3-create-the-twitter-app).</span></span>

<span data-ttu-id="27ebd-156">Tijdens het voltooien van deze stap (door de stapsgewijse instructies te volgen), kunt u de volgende gegevens opslaan in een tekstbestand.</span><span class="sxs-lookup"><span data-stu-id="27ebd-156">During the completion of this step (by following the step-by-step instructions), you save the following information to a text file.</span></span> <span data-ttu-id="27ebd-157">Deze waarden worden gebruikt om de Twitter-connector-app te configureren in stap 4.</span><span class="sxs-lookup"><span data-stu-id="27ebd-157">These values will be used to configure the Twitter connector app in Step 4.</span></span>

- <span data-ttu-id="27ebd-158">Twitter API-sleutel</span><span class="sxs-lookup"><span data-stu-id="27ebd-158">Twitter API Key</span></span>

- <span data-ttu-id="27ebd-159">Twitter API Secret Key</span><span class="sxs-lookup"><span data-stu-id="27ebd-159">Twitter API Secret Key</span></span>

- <span data-ttu-id="27ebd-160">Twitter Access-token</span><span class="sxs-lookup"><span data-stu-id="27ebd-160">Twitter Access Token</span></span>

- <span data-ttu-id="27ebd-161">Twitter Access Token Secret</span><span class="sxs-lookup"><span data-stu-id="27ebd-161">Twitter Access Token Secret</span></span>

## <a name="step-4-configure-the-twitter-connector-app"></a><span data-ttu-id="27ebd-162">Stap 4: De Twitter-connector-app configureren</span><span class="sxs-lookup"><span data-stu-id="27ebd-162">Step 4: Configure the Twitter connector app</span></span>

<span data-ttu-id="27ebd-163">De volgende stap is het toevoegen van configuratie-instellingen aan de Twitter-connector-app die u hebt geïmplementeerd in stap 2.</span><span class="sxs-lookup"><span data-stu-id="27ebd-163">The next step is to add configurations settings to the Twitter connector app that you deployed in Step 2.</span></span> <span data-ttu-id="27ebd-164">U doet dit door naar de startpagina van de connector-app te gaan en deze te configureren.</span><span class="sxs-lookup"><span data-stu-id="27ebd-164">You do this by going to the home page of your connector app and configuring it.</span></span>

<span data-ttu-id="27ebd-165">Zie De connectorweb-app [configureren](deploy-twitter-connector.md#step-4-configure-the-connector-web-app)voor stapsgewijse instructies.</span><span class="sxs-lookup"><span data-stu-id="27ebd-165">For step-by-step instructions, see [Configure the connector web app](deploy-twitter-connector.md#step-4-configure-the-connector-web-app).</span></span>

<span data-ttu-id="27ebd-166">Tijdens de voltooiing van deze stap (door de stapsgewijs instructies te volgen), geeft u de volgende informatie op (die u na het voltooien van de vorige stappen hebt gekopieerd naar een tekstbestand):</span><span class="sxs-lookup"><span data-stu-id="27ebd-166">During the completion of this step (by following the step-by-step instructions), you'll provide the following information (that you've copied to a text file after completing the previous steps):</span></span>

- <span data-ttu-id="27ebd-167">Twitter API-sleutel (verkregen in stap 3)</span><span class="sxs-lookup"><span data-stu-id="27ebd-167">Twitter API Key (obtained in Step 3)</span></span>

- <span data-ttu-id="27ebd-168">Twitter API Secret Key (verkregen in stap 3)</span><span class="sxs-lookup"><span data-stu-id="27ebd-168">Twitter API Secret Key (obtained in Step 3)</span></span>

- <span data-ttu-id="27ebd-169">Twitter Access-token (verkregen in stap 3)</span><span class="sxs-lookup"><span data-stu-id="27ebd-169">Twitter Access Token (obtained in Step 3)</span></span>

- <span data-ttu-id="27ebd-170">Twitter Access Token Secret (verkregen in stap 3)</span><span class="sxs-lookup"><span data-stu-id="27ebd-170">Twitter Access Token Secret (obtained in Step 3)</span></span>

- <span data-ttu-id="27ebd-171">Azure Active Directory toepassings-id (de AAD-toepassings-id die is verkregen in stap 1)</span><span class="sxs-lookup"><span data-stu-id="27ebd-171">Azure Active Directory application ID (the AAD application ID obtained in Step 1)</span></span>

- <span data-ttu-id="27ebd-172">Azure Active Directory toepassingsgeheim (het AAD-toepassingsgeheim dat is verkregen in stap 1)</span><span class="sxs-lookup"><span data-stu-id="27ebd-172">Azure Active Directory application secret (the AAD application secret obtained in Step 1)</span></span>

## <a name="step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="27ebd-173">Stap 5: Een Twitter-connector instellen in het Microsoft 365 compliancecentrum</span><span class="sxs-lookup"><span data-stu-id="27ebd-173">Step 5: Set up a Twitter connector in the Microsoft 365 compliance center</span></span>

<span data-ttu-id="27ebd-174">De laatste stap is het instellen van de Twitter-connector in het Microsoft 365 compliancecentrum dat gegevens uit het Twitter-account van uw organisatie importeert naar een opgegeven postvak in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="27ebd-174">The final step is to set up the Twitter connector in the Microsoft 365 compliance center that will import data from your organization's Twitter account to a specified mailbox in Microsoft 365.</span></span> <span data-ttu-id="27ebd-175">Nadat u deze stap hebt voltooid, Microsoft 365 de importservice gegevens uit het Twitter-account van uw organisatie importeren in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="27ebd-175">After you complete this step, the Microsoft 365 Import service will start importing data from your organization's Twitter account to Microsoft 365.</span></span>

<span data-ttu-id="27ebd-176">Zie Een Twitter-connector instellen in het Microsoft 365 [compliancecentrum voor stapsgewijse instructies.](deploy-twitter-connector.md#step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center)</span><span class="sxs-lookup"><span data-stu-id="27ebd-176">For step-by-step instructions, see [Set up a Twitter connector in the Microsoft 365 compliance center](deploy-twitter-connector.md#step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center).</span></span> 

<span data-ttu-id="27ebd-177">Tijdens het voltooien van deze stap (door de stapsgewijs instructies te volgen), geeft u de volgende informatie op (die u hebt gekopieerd naar een tekstbestand nadat u de stappen hebt voltooid).</span><span class="sxs-lookup"><span data-stu-id="27ebd-177">During the completion of this step (by following the step-by-step instructions), you'll provide the following information (that you've copied to a text file after completing the steps).</span></span>

- <span data-ttu-id="27ebd-178">Url van azure-appservice (verkregen in stap 2; `https://twitterconnector.azurewebsites.net` bijvoorbeeld)</span><span class="sxs-lookup"><span data-stu-id="27ebd-178">Azure app service URL (obtained in Step 2; for example, `https://twitterconnector.azurewebsites.net`)</span></span>

- <span data-ttu-id="27ebd-179">APISecretKey (die u hebt gemaakt in stap 2)</span><span class="sxs-lookup"><span data-stu-id="27ebd-179">APISecretKey (that you created in Step 2)</span></span>