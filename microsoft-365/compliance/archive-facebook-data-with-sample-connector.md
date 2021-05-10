---
title: Een verbindingslijn instellen om Facebook-gegevens te archiveren
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
description: Meer informatie over het instellen van & verbindingslijn gebruiken in het Microsoft 365 compliancecentrum om & archiefgegevens van Facebook Business-pagina's te Microsoft 365.
ms.openlocfilehash: 616466a3af83c1558184526aa463f68c10ef9e70
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162068"
---
# <a name="set-up-a-connector-to-archive-facebook-data-preview"></a><span data-ttu-id="41845-103">Een verbindingslijn instellen om Facebook-gegevens te archiveren (voorbeeld)</span><span class="sxs-lookup"><span data-stu-id="41845-103">Set up a connector to archive Facebook data (preview)</span></span>

<span data-ttu-id="41845-104">Gebruik een verbindingslijn in het Microsoft 365 compliancecentrum om gegevens van Facebook Business-pagina's te importeren en te archiveren Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="41845-104">Use a connector in the Microsoft 365 compliance center to import and archive data from Facebook Business pages to Microsoft 365.</span></span> <span data-ttu-id="41845-105">Nadat u de verbindingslijn hebt ingesteld en geconfigureerd, wordt er verbinding gemaakt met de Facebook Business-pagina (op een geplande basis), wordt de inhoud van Facebook-items geconverformeerd naar een e-mailberichtindeling en worden deze items vervolgens geïmporteerd in een postvak in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="41845-105">After you set up and configure the connector, it connects to the Facebook Business page (on a scheduled basis), converts the content of Facebook items to an email message format, and then imports those items to a mailbox in Microsoft 365.</span></span>

<span data-ttu-id="41845-106">Nadat de Facebook-gegevens zijn geïmporteerd, kunt u Microsoft 365 compliancefuncties zoals Proces bewaring, Inhoud zoeken, In-Place Archiveren, Auditing, Communicatie compliance en Microsoft 365 bewaarbeleid toepassen op de Facebook-gegevens.</span><span class="sxs-lookup"><span data-stu-id="41845-106">After the Facebook data is imported, you can apply Microsoft 365 compliance features such as Litigation Hold, Content Search, In-Place Archiving, Auditing, Communication compliance, and Microsoft 365 retention policies to the Facebook data.</span></span> <span data-ttu-id="41845-107">Als een postvak bijvoorbeeld in de bewaring van rechtszaken wordt geplaatst of is toegewezen aan een bewaarbeleid, blijven de Facebook-gegevens behouden.</span><span class="sxs-lookup"><span data-stu-id="41845-107">For example, when a mailbox is placed on Litigation Hold or assigned to a retention policy, the Facebook data is preserved.</span></span> <span data-ttu-id="41845-108">U kunt gegevens van derden doorzoeken met Inhoud zoeken of het postvak koppelen waarin de Facebook-gegevens zijn opgeslagen met een bewaarder in een Advanced eDiscovery geval.</span><span class="sxs-lookup"><span data-stu-id="41845-108">You can search third-party data using Content Search or associate the mailbox where the Facebook data is stored with a custodian in an Advanced eDiscovery case.</span></span> <span data-ttu-id="41845-109">Met een connector voor het importeren en archiveren van Facebook-gegevens in Microsoft 365 kan uw organisatie voldoen aan overheids- en regelgevingsbeleid.</span><span class="sxs-lookup"><span data-stu-id="41845-109">Using a connector to import and archive Facebook data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="prerequisites-for-setting-up-a-connector-for-facebook-business-pages"></a><span data-ttu-id="41845-110">Vereisten voor het instellen van een connector voor Facebook Business-pagina's</span><span class="sxs-lookup"><span data-stu-id="41845-110">Prerequisites for setting up a connector for Facebook Business pages</span></span>

<span data-ttu-id="41845-111">Voltooi de volgende vereisten voordat u een verbindingslijn kunt instellen en configureren in het Microsoft 365 compliancecentrum om gegevens te importeren en te archiveren van de Facebook Business-pagina's van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="41845-111">Complete the following prerequisites before you can set up and configure a connector in the Microsoft 365 compliance center to import and archive data from your organization's Facebook Business pages.</span></span> 

- <span data-ttu-id="41845-112">U hebt een Facebook-account nodig voor de bedrijfspagina's van uw organisatie (u moet zich aanmelden bij dit account bij het instellen van de verbindingslijn).</span><span class="sxs-lookup"><span data-stu-id="41845-112">You need a Facebook account for your organization's business pages (you need to sign in to this account when setting up the connector).</span></span> <span data-ttu-id="41845-113">Op dit moment kunt u alleen gegevens archiveren van Facebook Business-pagina's. u kunt geen gegevens archiveren van afzonderlijke Facebook-profielen.</span><span class="sxs-lookup"><span data-stu-id="41845-113">Currently, you can only archive data from Facebook Business pages; you can't archive data from individual Facebook profiles.</span></span>

- <span data-ttu-id="41845-114">Uw organisatie moet een geldig Azure-abonnement hebben.</span><span class="sxs-lookup"><span data-stu-id="41845-114">Your organization must have a valid Azure subscription.</span></span> <span data-ttu-id="41845-115">Als u geen bestaand Azure-abonnement hebt, kunt u zich registreren voor een van de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="41845-115">If you don't have an existing Azure subscription, you can sign up for one of these options:</span></span>

    - [<span data-ttu-id="41845-116">Registreren voor een gratis Azure-abonnement van één jaar</span><span class="sxs-lookup"><span data-stu-id="41845-116">Sign up for a free one year Azure subscription</span></span>](https://azure.microsoft.com/free)

    - [<span data-ttu-id="41845-117">Registreren voor een Pay-As-You-Go Azure-abonnement</span><span class="sxs-lookup"><span data-stu-id="41845-117">Sign up for a Pay-As-You-Go Azure subscription</span></span>](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > <span data-ttu-id="41845-118">Het [gratis Azure Active Directory](use-your-free-azure-ad-subscription-in-office-365.md) abonnement dat is inbegrepen bij uw Microsoft 365-abonnement biedt geen ondersteuning voor de connectors in het beveiligings- & compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="41845-118">The [free Azure Active Directory subscription](use-your-free-azure-ad-subscription-in-office-365.md) that's included with your Microsoft 365 subscription doesn't support the connectors in the Security & Compliance Center.</span></span>

- <span data-ttu-id="41845-119">De connector voor Facebook Business-pagina's kan in totaal 200.000 items in één dag importeren.</span><span class="sxs-lookup"><span data-stu-id="41845-119">The connector for Facebook Business pages can import a total of 200,000 items in a single day.</span></span> <span data-ttu-id="41845-120">Als er meer dan 200.000 Facebook Business-items in een dag zijn, worden geen van deze items geïmporteerd in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="41845-120">If there are more than 200,000 Facebook Business items in a day, none of those items will be imported to Microsoft 365.</span></span>

- <span data-ttu-id="41845-121">De gebruiker die de aangepaste connector in het Microsoft 365 compliancecentrum (in stap 5) in stelt, moet de rol Postvak importeren exporteren in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="41845-121">The user who sets up the custom connector in the Microsoft 365 compliance center (in Step 5) must be assigned the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="41845-122">Deze rol is standaard niet toegewezen aan een rollengroep in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="41845-122">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="41845-123">U kunt de rol Postvak importeren exporteren toevoegen aan de rollengroep Organisatiebeheer in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="41845-123">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="41845-124">U kunt ook een rollengroep maken, de rol Postvak importeren exporteren toewijzen en vervolgens de juiste gebruikers toevoegen als leden.</span><span class="sxs-lookup"><span data-stu-id="41845-124">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="41845-125">Zie de secties [](/Exchange/permissions-exo/role-groups#create-role-groups) Rollengroepen [](/Exchange/permissions-exo/role-groups#modify-role-groups) maken of Rollengroepen wijzigen in het artikel 'Rollengroepen beheren in Exchange Online'.</span><span class="sxs-lookup"><span data-stu-id="41845-125">For more information, see the  [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-create-an-app-in-azure-active-directory"></a><span data-ttu-id="41845-126">Stap 1: Een app maken in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="41845-126">Step 1: Create an app in Azure Active Directory</span></span>

<span data-ttu-id="41845-127">De eerste stap is het registreren van een nieuwe app in Azure Active Directory (AAD).</span><span class="sxs-lookup"><span data-stu-id="41845-127">The first step is to register a new app in Azure Active Directory (AAD).</span></span> <span data-ttu-id="41845-128">Deze app komt overeen met de web-app-resource die u implementeert in stap 4 en stap 5 voor de Facebook-connector.</span><span class="sxs-lookup"><span data-stu-id="41845-128">This app corresponds to the web app resource that you implement in Step 4 and Step 5 for the Facebook connector.</span></span> 

<span data-ttu-id="41845-129">Zie Een app maken in Azure Active Directory voor [stapsgewijse instructies.](deploy-facebook-connector.md#step-1-create-an-app-in-azure-active-directory)</span><span class="sxs-lookup"><span data-stu-id="41845-129">For step-by-step instructions, see [Create an app in Azure Active Directory](deploy-facebook-connector.md#step-1-create-an-app-in-azure-active-directory).</span></span>

<span data-ttu-id="41845-130">Tijdens het voltooien van deze stap (met behulp van de vorige stapsgewijse instructies), wordt de volgende informatie opgeslagen in een tekstbestand.</span><span class="sxs-lookup"><span data-stu-id="41845-130">During the completion of this step (by using the previous step-by-step instructions), you'll save the following information to a text file.</span></span> <span data-ttu-id="41845-131">Deze waarden worden gebruikt in latere stappen in het implementatieproces.</span><span class="sxs-lookup"><span data-stu-id="41845-131">These values are used in later steps in the deployment process.</span></span>

- <span data-ttu-id="41845-132">AAD-toepassings-id</span><span class="sxs-lookup"><span data-stu-id="41845-132">AAD application ID</span></span>

- <span data-ttu-id="41845-133">AAD-toepassingsgeheim</span><span class="sxs-lookup"><span data-stu-id="41845-133">AAD application secret</span></span>

- <span data-ttu-id="41845-134">Tenant-id</span><span class="sxs-lookup"><span data-stu-id="41845-134">Tenant Id</span></span>

## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a><span data-ttu-id="41845-135">Stap 2: De connectorwebservice implementeren van GitHub naar uw Azure-account</span><span class="sxs-lookup"><span data-stu-id="41845-135">Step 2: Deploy the connector web service from GitHub to your Azure account</span></span>

<span data-ttu-id="41845-136">De volgende stap is het implementeren van de broncode voor de connector-app voor Facebook Business-pagina's waarmee de Facebook-API wordt gebruikt om verbinding te maken met uw Facebook-account en gegevens op te halen, zodat u deze kunt importeren in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="41845-136">The next step is to deploy the source code for the Facebook Business pages connector app that will use the Facebook API to connect to your Facebook account and extract data so you can import it to Microsoft 365.</span></span> <span data-ttu-id="41845-137">De Facebook-connector die u voor uw organisatie implementeert, uploadt de items van uw Facebook Business-pagina's naar de Azure Storage locatie die in deze stap is gemaakt.</span><span class="sxs-lookup"><span data-stu-id="41845-137">The Facebook connector that you deploy for your organization will upload the items from your Facebook Business pages to the Azure Storage location that is created in this step.</span></span> <span data-ttu-id="41845-138">Nadat u een Verbindingslijn voor Facebook-zakelijke pagina's hebt gemaakt in het Microsoft 365 compliancecentrum (in stap 5), kopieert de importservice de gegevens van de Facebook-bedrijfspagina's vanaf de Azure Storage-locatie naar een postvak in uw Microsoft 365 organisatie.</span><span class="sxs-lookup"><span data-stu-id="41845-138">After you create a Facebook business pages connector in the Microsoft 365 compliance center (in Step 5), the Import service will copy the Facebook business pages data from the Azure Storage location to a mailbox in your Microsoft 365 organization.</span></span> <span data-ttu-id="41845-139">Zoals u eerder hebt uitgelegd in [de](#prerequisites-for-setting-up-a-connector-for-facebook-business-pages) sectie Vereisten, moet u een geldig Azure-abonnement hebben om een Azure Storage maken.</span><span class="sxs-lookup"><span data-stu-id="41845-139">As previous explained in the [Prerequisites](#prerequisites-for-setting-up-a-connector-for-facebook-business-pages) section, you must have a valid Azure subscription to create an Azure Storage account.</span></span>

<span data-ttu-id="41845-140">Zie De connectorwebservice implementeren van GitHub azure-account voor [stapsgewijse instructies.](deploy-facebook-connector.md#step-2-deploy-the-connector-web-service-from-github-to-your-azure-account)</span><span class="sxs-lookup"><span data-stu-id="41845-140">For step-by-step instructions, see [Deploy the connector web service from GitHub to your Azure account](deploy-facebook-connector.md#step-2-deploy-the-connector-web-service-from-github-to-your-azure-account).</span></span>

<span data-ttu-id="41845-141">In de stapsgewijs instructies voor het voltooien van deze stap geeft u de volgende informatie:</span><span class="sxs-lookup"><span data-stu-id="41845-141">In the step-by-step instructions to complete this step, you'll provide the following information:</span></span>

- <span data-ttu-id="41845-142">APISecretKey: u maakt dit geheim tijdens de voltooiing van deze stap.</span><span class="sxs-lookup"><span data-stu-id="41845-142">APISecretKey: You create this secret during the completion of this step.</span></span> <span data-ttu-id="41845-143">Deze wordt gebruikt in stap 5.</span><span class="sxs-lookup"><span data-stu-id="41845-143">It's used in Step 5.</span></span>

- <span data-ttu-id="41845-144">TenantId: de tenant-id van uw Microsoft 365 organisatie die u hebt gekopieerd na het maken van de Facebook-connector-app in Azure Active Directory stap 1.</span><span class="sxs-lookup"><span data-stu-id="41845-144">TenantId: The tenant ID of your Microsoft 365 organization that you copied after creating the Facebook connector app in Azure Active Directory in Step 1.</span></span>

<span data-ttu-id="41845-145">Nadat u deze stap hebt uitgevoerd, moet u de URL van de Azure-app-service kopiëren https://fbconnector.azurewebsites.net) (bijvoorbeeld.</span><span class="sxs-lookup"><span data-stu-id="41845-145">After completing this step, be sure to copy the Azure app service URL (for example, https://fbconnector.azurewebsites.net).</span></span> <span data-ttu-id="41845-146">U moet deze URL gebruiken om stap 3, stap 4 en stap 5 te voltooien.</span><span class="sxs-lookup"><span data-stu-id="41845-146">You need to use this URL to complete Step 3, Step 4, and Step 5).</span></span>

## <a name="step-3-register-the-web-app-on-facebook"></a><span data-ttu-id="41845-147">Stap 3: De web-app registreren op Facebook</span><span class="sxs-lookup"><span data-stu-id="41845-147">Step 3: Register the web app on Facebook</span></span>

<span data-ttu-id="41845-148">De volgende stap is het maken en configureren van een nieuwe app op Facebook.</span><span class="sxs-lookup"><span data-stu-id="41845-148">The next step is to create and configure a new app on Facebook.</span></span> <span data-ttu-id="41845-149">De Facebook-verbindingslijn voor zakelijke pagina's die u in stap 5 maakt, gebruikt de Facebook-web-app om te communiceren met de Facebook-API om gegevens te verkrijgen van de Facebook Business-pagina's van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="41845-149">The Facebook business pages connector that you create in Step 5 uses the Facebook web app to interact with the Facebook API to obtain data from your organization's Facebook Business pages.</span></span>

<span data-ttu-id="41845-150">Zie De [Facebook-app registreren](deploy-facebook-connector.md#step-3-register-the-facebook-app)voor stapsgewijse instructies.</span><span class="sxs-lookup"><span data-stu-id="41845-150">For step-by-step instructions, see [Register the Facebook app](deploy-facebook-connector.md#step-3-register-the-facebook-app).</span></span>

<span data-ttu-id="41845-151">Tijdens het voltooien van deze stap (door de stapsgewijse instructies te volgen), kunt u de volgende gegevens opslaan in een tekstbestand.</span><span class="sxs-lookup"><span data-stu-id="41845-151">During the completion of this step (by following the step-by-step instructions), you save the following information to a text file.</span></span> <span data-ttu-id="41845-152">Deze waarden worden gebruikt om de Facebook-connector-app te configureren in stap 4.</span><span class="sxs-lookup"><span data-stu-id="41845-152">These values are used to configure the Facebook connector app in Step 4.</span></span>

- <span data-ttu-id="41845-153">Facebook-toepassing-id</span><span class="sxs-lookup"><span data-stu-id="41845-153">Facebook application ID</span></span>

- <span data-ttu-id="41845-154">Facebook-toepassingsgeheim</span><span class="sxs-lookup"><span data-stu-id="41845-154">Facebook application secret</span></span>

- <span data-ttu-id="41845-155">Facebook-webhooks verifiëren token</span><span class="sxs-lookup"><span data-stu-id="41845-155">Facebook webhooks verify token</span></span>

## <a name="step-4-configure-the-facebook-connector-app"></a><span data-ttu-id="41845-156">Stap 4: De Facebook-connector-app configureren</span><span class="sxs-lookup"><span data-stu-id="41845-156">Step 4: Configure the Facebook connector app</span></span>

<span data-ttu-id="41845-157">De volgende stap is het toevoegen van configuratie-instellingen aan de Facebook-connector-app die u hebt geüpload toen u de Azure Web App-resource maakte in stap 1.</span><span class="sxs-lookup"><span data-stu-id="41845-157">The next step is to add configuration settings to the Facebook connector app that you uploaded when you created the Azure web app resource in Step 1.</span></span> <span data-ttu-id="41845-158">U doet dit door naar de startpagina van de connector-app te gaan en deze te configureren.</span><span class="sxs-lookup"><span data-stu-id="41845-158">You do this by going to the home page of your connector app and configuring it.</span></span>

<span data-ttu-id="41845-159">Zie De [Facebook-connector-app configureren](archive-facebook-data-with-sample-connector.md#step-4-configure-the-facebook-connector-app)voor stapsgewijse instructies.</span><span class="sxs-lookup"><span data-stu-id="41845-159">For step-by-step instructions, see [Configure the Facebook connector app](archive-facebook-data-with-sample-connector.md#step-4-configure-the-facebook-connector-app).</span></span>

<span data-ttu-id="41845-160">Tijdens het voltooien van deze stap (door de stapsgewijs instructies te volgen), geeft u de volgende informatie op (die u na het voltooien van de vorige stappen hebt gekopieerd naar een tekstbestand):</span><span class="sxs-lookup"><span data-stu-id="41845-160">During the completion of this step (by following the step-by-step instructions), you provide the following information (that you've copied to a text file after completing the previous steps):</span></span>

- <span data-ttu-id="41845-161">Facebook-toepassing-id (verkregen in stap 3)</span><span class="sxs-lookup"><span data-stu-id="41845-161">Facebook application ID (obtained in Step 3)</span></span>

- <span data-ttu-id="41845-162">Facebook-toepassingsgeheim (verkregen in stap 3)</span><span class="sxs-lookup"><span data-stu-id="41845-162">Facebook application secret (obtained in Step 3)</span></span>

- <span data-ttu-id="41845-163">Facebook-webhaken verifiëren token (verkregen in stap 3)</span><span class="sxs-lookup"><span data-stu-id="41845-163">Facebook webhooks verify token (obtained in Step 3)</span></span>

- <span data-ttu-id="41845-164">Azure Active Directory toepassings-id (de AAD-toepassings-id die is verkregen in stap 1)</span><span class="sxs-lookup"><span data-stu-id="41845-164">Azure Active Directory application ID (the AAD application ID obtained in Step 1)</span></span>

- <span data-ttu-id="41845-165">Azure Active Directory toepassingsgeheim (het AAD-toepassingsgeheim dat is verkregen in stap 1)</span><span class="sxs-lookup"><span data-stu-id="41845-165">Azure Active Directory application secret (the AAD application secret obtained in Step 1)</span></span>

## <a name="step-5-set-up-a-facebook-business-pages-connector-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="41845-166">Stap 5: Een verbindingslijn voor Facebook Business-pagina's instellen in het Microsoft 365 compliancecentrum</span><span class="sxs-lookup"><span data-stu-id="41845-166">Step 5: Set up a Facebook Business pages connector in the Microsoft 365 compliance center</span></span>

<span data-ttu-id="41845-167">De laatste stap is het instellen van de verbindingslijn in het Microsoft 365 compliancecentrum dat gegevens van uw Facebook Business-pagina's importeert naar een opgegeven postvak in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="41845-167">The final step is to set up the connector in the Microsoft 365 compliance center that will import data from your Facebook Business pages to a specified mailbox in Microsoft 365.</span></span> <span data-ttu-id="41845-168">Nadat u deze stap hebt voltooid, wordt Microsoft 365 de importservice gegevens van uw Facebook Business-pagina's geïmporteerd naar Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="41845-168">After you complete this step, the Microsoft 365 Import service will start importing data from your Facebook Business pages to Microsoft 365.</span></span>

<span data-ttu-id="41845-169">Zie Stap 5: Een Facebook-connector instellen in het Microsoft 365 [compliancecentrum voor stapsgewijse instructies.](deploy-facebook-connector.md#step-5-set-up-a-facebook-connector-in-the-microsoft-365-compliance-center)</span><span class="sxs-lookup"><span data-stu-id="41845-169">For step-by-step instructions, see [Step 5: Set up a Facebook connector in the Microsoft 365 compliance center](deploy-facebook-connector.md#step-5-set-up-a-facebook-connector-in-the-microsoft-365-compliance-center).</span></span> 

<span data-ttu-id="41845-170">Tijdens het voltooien van deze stap (door de stapsgewijs instructies te volgen), geeft u de volgende informatie op (die u na het voltooien van de stappen hebt gekopieerd naar een tekstbestand).</span><span class="sxs-lookup"><span data-stu-id="41845-170">During the completion of this step (by following the step-by-step instructions), you provide the following information (that you've copied to a text file after completing the steps).</span></span>

- <span data-ttu-id="41845-171">AAD-toepassings-id (verkregen in stap 1)</span><span class="sxs-lookup"><span data-stu-id="41845-171">AAD application ID (obtained in Step 1)</span></span>

- <span data-ttu-id="41845-172">URL van azure-appservice (verkregen in stap 1; bijvoorbeeld: https://fbconnector.azurewebsites.net)</span><span class="sxs-lookup"><span data-stu-id="41845-172">Azure app service URL (obtained in Step 1; for example, https://fbconnector.azurewebsites.net)</span></span>

- <span data-ttu-id="41845-173">APISecretKey (die u hebt gemaakt in stap 2)</span><span class="sxs-lookup"><span data-stu-id="41845-173">APISecretKey (that you created in Step 2)</span></span>