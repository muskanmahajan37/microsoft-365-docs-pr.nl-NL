---
title: Serviceversleuteling met klantsleutel
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 02/05/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
ms.custom: seo-marvel-apr2020
description: In dit artikel leert u hoe serviceversleuteling werkt met de klantsleutel in Microsoft 365.
ms.openlocfilehash: 21291dc45cd634cd5b6a88c4e58972c17486724f
ms.sourcegitcommit: 94fa3e57fa6505551d84ae7b458150dceff30db7
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/26/2021
ms.locfileid: "52162483"
---
# <a name="service-encryption-with-customer-key"></a><span data-ttu-id="22b34-103">Serviceversleuteling met klantsleutel</span><span class="sxs-lookup"><span data-stu-id="22b34-103">Service encryption with Customer Key</span></span>

<span data-ttu-id="22b34-104">Microsoft 365 biedt basislijnversleuteling, volumeversleuteling die is ingeschakeld via BitLocker en Distributed Key Manager (DKM).</span><span class="sxs-lookup"><span data-stu-id="22b34-104">Microsoft 365 provides baseline, volume-level encryption enabled through BitLocker and Distributed Key Manager (DKM).</span></span> <span data-ttu-id="22b34-105">Microsoft 365 biedt een extra versleutelingslaag op de toepassingslaag voor uw inhoud.</span><span class="sxs-lookup"><span data-stu-id="22b34-105">Microsoft 365 offers an added layer of encryption at the application layer for your content.</span></span> <span data-ttu-id="22b34-106">Deze inhoud bevat gegevens uit Exchange Online, Skype voor Bedrijven, SharePoint Online, OneDrive voor Bedrijven en Teams bestanden.</span><span class="sxs-lookup"><span data-stu-id="22b34-106">This content includes data from Exchange Online, Skype for Business, SharePoint Online, OneDrive for Business, and Teams files.</span></span> <span data-ttu-id="22b34-107">Deze toegevoegde versleutelingslaag wordt serviceversleuteling genoemd.</span><span class="sxs-lookup"><span data-stu-id="22b34-107">This added layer of encryption is called service encryption.</span></span>

## <a name="how-service-encryption-bitlocker-and-customer-key-work-together"></a><span data-ttu-id="22b34-108">Hoe serviceversleuteling, BitLocker en Klantsleutel samenwerken</span><span class="sxs-lookup"><span data-stu-id="22b34-108">How service encryption, BitLocker, and Customer Key work together</span></span>

<span data-ttu-id="22b34-109">Serviceversleuteling zorgt ervoor dat inhoud in rust wordt versleuteld op de servicelaag.</span><span class="sxs-lookup"><span data-stu-id="22b34-109">Service encryption ensures that content at rest is encrypted at the service layer.</span></span> <span data-ttu-id="22b34-110">Uw gegevens worden altijd in rust versleuteld in de Microsoft 365 **service met BitLocker en DKM.**</span><span class="sxs-lookup"><span data-stu-id="22b34-110">**Your data is always encrypted at rest in the Microsoft 365 service with BitLocker and DKM**.</span></span> <span data-ttu-id="22b34-111">Zie de 'Beveiligings-, privacy- en compliancegegevens' en Hoe Exchange Online uw e-mailgeheimen [beveiligt](exchange-online-secures-email-secrets.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="22b34-111">For more information, see the "Security, Privacy, and Compliance Information", and [How Exchange Online secures your email secrets](exchange-online-secures-email-secrets.md).</span></span> <span data-ttu-id="22b34-112">Klantsleutel biedt extra bescherming tegen het weergeven van gegevens door onbevoegde systemen of personeel en vormt een aanvulling op de BitLocker schijfversleuteling in Microsoft-datacenters.</span><span class="sxs-lookup"><span data-stu-id="22b34-112">Customer Key provides additional protection against viewing of data by unauthorized systems or personnel, and complements BitLocker disk encryption in Microsoft datacenters.</span></span> <span data-ttu-id="22b34-113">Serviceversleuteling is niet bedoeld om te voorkomen dat microsoft-personeel toegang heeft tot klantgegevens.</span><span class="sxs-lookup"><span data-stu-id="22b34-113">Service encryption is not meant to prevent Microsoft personnel from accessing customer data.</span></span> <span data-ttu-id="22b34-114">Het primaire doel is klanten te helpen bij het voldoen aan wettelijke of nalevingsverplichtingen voor het beheren van hoofdsleutels.</span><span class="sxs-lookup"><span data-stu-id="22b34-114">The primary purpose is to assist customers in meeting regulatory or compliance obligations for controlling root keys.</span></span> <span data-ttu-id="22b34-115">Klanten machtigen O365-services expliciet om hun versleutelingssleutels te gebruiken om cloudservices met toegevoegde waarde te leveren, zoals eDiscovery, anti-malware, antispam, zoekindexering, enzovoort.</span><span class="sxs-lookup"><span data-stu-id="22b34-115">Customers explicitly authorize O365 services to use their encryption keys to provide value added cloud services, such as eDiscovery, anti-malware, anti-spam, search indexing, etc.</span></span>

<span data-ttu-id="22b34-116">Klantsleutel is gebaseerd op serviceversleuteling en u kunt versleutelingssleutels leveren en bedienen.</span><span class="sxs-lookup"><span data-stu-id="22b34-116">Customer Key is built on service encryption and lets you provide and control encryption keys.</span></span> <span data-ttu-id="22b34-117">Microsoft 365 gebruikt deze sleutels om uw gegevens in rust te versleutelen, zoals beschreven in de [Voorwaarden voor Online Services (OST).](https://www.microsoft.com/licensing/product-licensing/products.aspx)</span><span class="sxs-lookup"><span data-stu-id="22b34-117">Microsoft 365 then uses these keys to encrypt your data at rest as described in the [Online Services Terms (OST)](https://www.microsoft.com/licensing/product-licensing/products.aspx).</span></span> <span data-ttu-id="22b34-118">Met De klantsleutel kunt u voldoen aan nalevingsverplichtingen omdat u de versleutelingssleutels controleert die Microsoft 365 gegevens versleutelen en ontsleutelen.</span><span class="sxs-lookup"><span data-stu-id="22b34-118">Customer Key helps you meet compliance obligations because you control the encryption keys that Microsoft 365 uses to encrypt and decrypt data.</span></span>
  
<span data-ttu-id="22b34-119">Klantsleutel verbetert de mogelijkheid van uw organisatie om te voldoen aan de vereisten voor naleving die belangrijke afspraken met de cloudserviceprovider specificeren.</span><span class="sxs-lookup"><span data-stu-id="22b34-119">Customer Key enhances the ability of your organization to meet the demands of compliance requirements that specify key arrangements with the cloud service provider.</span></span> <span data-ttu-id="22b34-120">Met De klantsleutel geeft u de hoofdversleutelingssleutels voor uw Microsoft 365 op het toepassingsniveau.</span><span class="sxs-lookup"><span data-stu-id="22b34-120">With Customer Key, you provide and control the root encryption keys for your Microsoft 365 data at-rest at the application level.</span></span> <span data-ttu-id="22b34-121">Hierdoor oefent u de controle over de sleutels van uw organisatie uit.</span><span class="sxs-lookup"><span data-stu-id="22b34-121">As a result, you exercise control over your organization's keys.</span></span> <span data-ttu-id="22b34-122">Als u besluit de service te verlaten, trekt u de toegang tot de hoofdsleutels van uw organisatie in.</span><span class="sxs-lookup"><span data-stu-id="22b34-122">If you decide to exit the service, you revoke access to your organization's root keys.</span></span> <span data-ttu-id="22b34-123">Voor alle Microsoft 365 services is het inroepen van toegang tot de sleutels de eerste stap op het pad naar gegevensverhaling.</span><span class="sxs-lookup"><span data-stu-id="22b34-123">For all Microsoft 365 services, revoking access to the keys is the first step on the path towards data deletion.</span></span> <span data-ttu-id="22b34-124">Als u de toegang tot de sleutels inroept, zijn de gegevens onleesbaar voor de service.</span><span class="sxs-lookup"><span data-stu-id="22b34-124">By revoking access to the keys, the data is unreadable to the service.</span></span>

## <a name="customer-key-encrypts-data-at-rest-in-office-365"></a><span data-ttu-id="22b34-125">Klantsleutel versleutelt gegevens in rust in Office 365</span><span class="sxs-lookup"><span data-stu-id="22b34-125">Customer Key encrypts data at rest in Office 365</span></span>

<span data-ttu-id="22b34-126">Met behulp van de door u op te geven sleutels versleutelt Klantsleutel op toepassingsniveau:</span><span class="sxs-lookup"><span data-stu-id="22b34-126">Using keys you provide, Customer Key at the application level encrypts:</span></span>

- <span data-ttu-id="22b34-127">SharePoint Online, OneDrive voor Bedrijven en Teams bestanden.</span><span class="sxs-lookup"><span data-stu-id="22b34-127">SharePoint Online, OneDrive for Business, and Teams files.</span></span>
- <span data-ttu-id="22b34-128">Bestanden die zijn geüpload naar OneDrive voor Bedrijven.</span><span class="sxs-lookup"><span data-stu-id="22b34-128">Files uploaded to OneDrive for Business.</span></span>
- <span data-ttu-id="22b34-129">Exchange Online inhoud van het postvak, inclusief inhoud van e-mail, agenda-items en de inhoud in e-mailbijlagen.</span><span class="sxs-lookup"><span data-stu-id="22b34-129">Exchange Online mailbox content including e-mail body content, calendar entries, and the content within email attachments.</span></span>
- <span data-ttu-id="22b34-130">Tekstgesprekken uit Skype voor Bedrijven.</span><span class="sxs-lookup"><span data-stu-id="22b34-130">Text conversations from Skype for Business.</span></span>

<span data-ttu-id="22b34-131">We bieden momenteel geen klantcontrole over de versleutelingssleutels voor Skype-vergadering Broadcast en Skype-vergadering inhoud uploaden.</span><span class="sxs-lookup"><span data-stu-id="22b34-131">We don't currently offer customer control of the encryption keys for Skype Meeting Broadcast and Skype Meeting content uploads.</span></span> <span data-ttu-id="22b34-132">In plaats daarvan wordt deze inhoud versleuteld samen met alle andere inhoud in Office 365.</span><span class="sxs-lookup"><span data-stu-id="22b34-132">Instead, this content is encrypted along with all other content in Office 365.</span></span>

### <a name="customer-key-with-hybrid-deployments"></a><span data-ttu-id="22b34-133">Klantcode met hybride implementaties</span><span class="sxs-lookup"><span data-stu-id="22b34-133">Customer Key with hybrid deployments</span></span>

<span data-ttu-id="22b34-134">Klantsleutel versleutelt alleen gegevens in rust in de cloud.</span><span class="sxs-lookup"><span data-stu-id="22b34-134">Customer Key only encrypts data at rest in the cloud.</span></span> <span data-ttu-id="22b34-135">Klantcode werkt niet om uw on-premises postvakken en bestanden te beveiligen.</span><span class="sxs-lookup"><span data-stu-id="22b34-135">Customer Key does not work to protect your on-premises mailboxes and files.</span></span> <span data-ttu-id="22b34-136">U kunt uw on-premises gegevens versleutelen met een andere methode, zoals BitLocker.</span><span class="sxs-lookup"><span data-stu-id="22b34-136">You can encrypt your on-premises data using another method, such as BitLocker.</span></span>

## <a name="about-the-data-encryption-policy-dep"></a><span data-ttu-id="22b34-137">Informatie over het beleid voor gegevensversleuteling (DEP)</span><span class="sxs-lookup"><span data-stu-id="22b34-137">About the data encryption policy (DEP)</span></span>

<span data-ttu-id="22b34-138">Een gegevensversleutelingsbeleid definieert de versleutelingshiërarchie om gegevens te versleutelen met behulp van elk van de sleutels die u verstrekt, evenals de beschikbaarheidssleutel die door Microsoft is beveiligd.</span><span class="sxs-lookup"><span data-stu-id="22b34-138">A data encryption policy defines the encryption hierarchy to encrypt data using each of the keys you provide as well as the availability key protected by Microsoft.</span></span> <span data-ttu-id="22b34-139">U maakt DEP's met PowerShell-cmdlets, die voor elke service verschillen, en wijst deze DEP's toe om toepassingsgegevens te versleutelen.</span><span class="sxs-lookup"><span data-stu-id="22b34-139">You create DEPs using PowerShell cmdlets, which are different for each service, and assign those DEPs to encrypt application data.</span></span> <span data-ttu-id="22b34-140">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="22b34-140">For example:</span></span>

<span data-ttu-id="22b34-141">**Exchange Online en Skype voor Bedrijven** U kunt maximaal 50 DEP's per tenant maken.</span><span class="sxs-lookup"><span data-stu-id="22b34-141">**Exchange Online and Skype for Business** You can create up to 50 DEPs per tenant.</span></span> <span data-ttu-id="22b34-142">U koppelt DEP's aan uw klantsleutels in Azure Key Vault en wijst vervolgens DEP's toe aan afzonderlijke postvakken.</span><span class="sxs-lookup"><span data-stu-id="22b34-142">You associate DEPs to your Customer Keys in Azure Key Vault and then assign DEPs to individual mailboxes.</span></span> <span data-ttu-id="22b34-143">Wanneer u een DEP aan een postvak toewijst:</span><span class="sxs-lookup"><span data-stu-id="22b34-143">When you assign a DEP to a mailbox:</span></span>

- <span data-ttu-id="22b34-144">het postvak is gemarkeerd voor een postvak verplaatsen.</span><span class="sxs-lookup"><span data-stu-id="22b34-144">the mailbox is marked for a mailbox move.</span></span> <span data-ttu-id="22b34-145">Op basis van prioriteiten in Microsoft 365 zoals hier wordt [beschreven, verplaatst u aanvragen in de Microsoft 365 service.](/exchange/mailbox-migration/office-365-migration-best-practices#move-requests-in-the-office-365-service)</span><span class="sxs-lookup"><span data-stu-id="22b34-145">Based on priorities in Microsoft 365 as described here [Move requests in the Microsoft 365 service](/exchange/mailbox-migration/office-365-migration-best-practices#move-requests-in-the-office-365-service).</span></span>

- <span data-ttu-id="22b34-146">De versleuteling vindt plaats terwijl het postvak wordt verplaatst.</span><span class="sxs-lookup"><span data-stu-id="22b34-146">The encryption takes place while the mailbox is moved.</span></span> <span data-ttu-id="22b34-147">Sta 72 uur toe dat het postvak wordt versleuteld met de nieuwe DEP.</span><span class="sxs-lookup"><span data-stu-id="22b34-147">Allow 72 hours for the mailbox to become encrypted with the new DEP.</span></span> <span data-ttu-id="22b34-148">Als de postvakken niet zijn versleuteld na 72 uur te hebben gewacht vanaf het moment dat u de DEP hebt toegewezen, neem dan contact op met Microsoft.</span><span class="sxs-lookup"><span data-stu-id="22b34-148">If the mailboxes aren't encrypted after waiting 72 hours from the time you assigned the DEP, contact Microsoft.</span></span>

<span data-ttu-id="22b34-149">Later kunt u het DEP vernieuwen of een ander DEP toewijzen aan het postvak, zoals beschreven in Klantsleutel beheren [voor Office 365.](customer-key-manage.md)</span><span class="sxs-lookup"><span data-stu-id="22b34-149">Later, you can either refresh the DEP or assign a different DEP to the mailbox as described in [Manage Customer Key for Office 365](customer-key-manage.md).</span></span> <span data-ttu-id="22b34-150">Elk postvak moet over de juiste licenties zijn om een DEP toe te wijzen.</span><span class="sxs-lookup"><span data-stu-id="22b34-150">Each mailbox must have appropriate licenses in order to assign a DEP.</span></span> <span data-ttu-id="22b34-151">Zie Voordat u Klantcode in stelt voor meer informatie over [licenties.](customer-key-set-up.md#before-you-set-up-customer-key)</span><span class="sxs-lookup"><span data-stu-id="22b34-151">For more information about licensing, see [Before you set up Customer Key](customer-key-set-up.md#before-you-set-up-customer-key).</span></span>

> [!NOTE]
> <span data-ttu-id="22b34-152">De DEP kan worden toegepast op een gedeeld postvak, een postvak in een openbare map en een Microsoft 365-groepspostvak voor tenants die voldoen aan de licentievereiste voor gebruikerspostvakken, hoewel sommige van deze postvakken geen toegewezen licentie kunnen zijn (postvak voor openbare mappen en Microsoft 365 groepspostvak) of een licentie nodig hebben voor het vergroten van de opslag (gedeeld postvak).</span><span class="sxs-lookup"><span data-stu-id="22b34-152">The DEP can be applied to a shared mailbox, public folder mailbox, and Microsoft 365 group mailbox for tenants that meet the licensing requirement for user mailboxes, even though some of these mailbox types cannot be an assigned license (public folder mailbox and Microsoft 365 group mailbox) or need a license for increasing storage (shared mailbox).</span></span>

<span data-ttu-id="22b34-153">**SharePoint Online, OneDrive voor Bedrijven en Teams bestanden** Als u de functie multi-geo gebruikt, kunt u maximaal één DEP per geo maken voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="22b34-153">**SharePoint Online, OneDrive for Business, and Teams files** If you're using the multi-geo feature, you can create up to one DEP per geo for your organization.</span></span> <span data-ttu-id="22b34-154">U kunt verschillende klantsleutels voor elke geo gebruiken.</span><span class="sxs-lookup"><span data-stu-id="22b34-154">You can use different Customer Keys for each geo.</span></span> <span data-ttu-id="22b34-155">Als u de functie multi-geo niet gebruikt, kunt u slechts één DEP per tenant maken.</span><span class="sxs-lookup"><span data-stu-id="22b34-155">If you're not using the multi-geo feature, you can only create one DEP per tenant.</span></span> <span data-ttu-id="22b34-156">Wanneer u de DEP toewijst, wordt de versleuteling automatisch gestart, maar kan het enige tijd duren om de versleuteling te voltooien.</span><span class="sxs-lookup"><span data-stu-id="22b34-156">When you assign the DEP, encryption begins automatically but can take some time to complete.</span></span> <span data-ttu-id="22b34-157">Raadpleeg de details in [Klantsleutel instellen.](customer-key-set-up.md)</span><span class="sxs-lookup"><span data-stu-id="22b34-157">Refer to the details in [Set up Customer Key](customer-key-set-up.md).</span></span>

## <a name="leaving-the-service"></a><span data-ttu-id="22b34-158">De service verlaten</span><span class="sxs-lookup"><span data-stu-id="22b34-158">Leaving the service</span></span>

<span data-ttu-id="22b34-159">Klantsleutel helpt u bij het voldoen aan nalevingsverplichtingen doordat u uw sleutels kunt intrekken wanneer u de service Microsoft 365 verlaten.</span><span class="sxs-lookup"><span data-stu-id="22b34-159">Customer Key assists you in meeting compliance obligations by allowing you to revoke your keys when you leave the Microsoft 365 service.</span></span> <span data-ttu-id="22b34-160">Wanneer u uw sleutels int als onderdeel van het verlaten van de service, wordt de beschikbaarheidssleutel verwijderd, wat resulteert in cryptografische verwijdering van uw gegevens.</span><span class="sxs-lookup"><span data-stu-id="22b34-160">When you revoke your keys as part of leaving the service, the availability key is deleted resulting in cryptographic deletion of your data.</span></span> <span data-ttu-id="22b34-161">Cryptografische verwijdering verkleint het risico op gegevensmanie, wat belangrijk is voor het voldoen aan zowel beveiligings- als nalevingsverplichtingen.</span><span class="sxs-lookup"><span data-stu-id="22b34-161">Cryptographic deletion mitigates the risk of data remanence which is important for meeting both security and compliance obligations.</span></span> <span data-ttu-id="22b34-162">Zie Uw sleutels intrekken en het proces voor het verwijderen van gegevens starten voor informatie over het proces voor het verwijderen van gegevens en het intrekken van [sleutels.](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process)</span><span class="sxs-lookup"><span data-stu-id="22b34-162">For information about the data purge process and key revocation, see [Revoke your keys and start the data purge path process](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process).</span></span>

### <a name="encryption-ciphers-used-by-customer-key"></a><span data-ttu-id="22b34-163">Versleutelingscodes die door klantsleutel worden gebruikt</span><span class="sxs-lookup"><span data-stu-id="22b34-163">Encryption ciphers used by Customer Key</span></span>

<span data-ttu-id="22b34-164">Klantsleutel gebruikt diverse versleutelingscodes om sleutels te versleutelen, zoals wordt weergegeven in de volgende cijfers.</span><span class="sxs-lookup"><span data-stu-id="22b34-164">Customer Key uses a variety of encryption ciphers to encrypt keys as shown in the following figures.</span></span>

#### <a name="encryption-ciphers-used-to-encrypt-keys-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="22b34-165">Versleutelingssleutels die worden gebruikt om sleutels voor Exchange Online en Skype voor Bedrijven</span><span class="sxs-lookup"><span data-stu-id="22b34-165">Encryption ciphers used to encrypt keys for Exchange Online and Skype for Business</span></span>

![Versleutelingscodes voor Exchange Online klantsleutel](../media/customerkeyencryptionhierarchiesexchangeskype.png)

#### <a name="encryption-ciphers-used-to-encrypt-keys-for-sharepoint-online-onedrive-for-business-and-teams-files"></a><span data-ttu-id="22b34-167">Versleutelingscodes die worden gebruikt om sleutels te versleutelen voor SharePoint Online OneDrive voor Bedrijven en Teams bestanden</span><span class="sxs-lookup"><span data-stu-id="22b34-167">Encryption ciphers used to encrypt keys for SharePoint Online, OneDrive for Business, and Teams files</span></span>

![Versleutelingscodes voor SharePoint Online Customer Key](../media/customerkeyencryptionhierarchiessharepointonedriveteamsfiles.png)

## <a name="related-articles"></a><span data-ttu-id="22b34-169">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="22b34-169">Related articles</span></span>

- [<span data-ttu-id="22b34-170">Klantsleutel instellen</span><span class="sxs-lookup"><span data-stu-id="22b34-170">Set up Customer Key</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="22b34-171">Klantcode beheren</span><span class="sxs-lookup"><span data-stu-id="22b34-171">Manage Customer Key</span></span>](customer-key-manage.md)

- [<span data-ttu-id="22b34-172">Een klantsleutel of een beschikbaarheidssleutel rollen of draaien</span><span class="sxs-lookup"><span data-stu-id="22b34-172">Roll or rotate a Customer Key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="22b34-173">Meer informatie over de beschikbaarheidssleutel</span><span class="sxs-lookup"><span data-stu-id="22b34-173">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)

- [<span data-ttu-id="22b34-174">Klanten-lockbox</span><span class="sxs-lookup"><span data-stu-id="22b34-174">Customer Lockbox</span></span>](customer-lockbox-requests.md)

- [<span data-ttu-id="22b34-175">Serviceversleuteling</span><span class="sxs-lookup"><span data-stu-id="22b34-175">Service Encryption</span></span>](office-365-service-encryption.md)