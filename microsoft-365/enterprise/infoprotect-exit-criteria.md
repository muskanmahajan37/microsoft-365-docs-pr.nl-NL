---
title: Uitgangscriteria voor de infrastructuur voor gegevensbeveiliging
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Bekijk de criteria voor op gegevensbeveiliging gebaseerde services en infrastructuur om ervoor te zorgen dat uw configuratie voldoet aan de vereisten van Microsoft 365 Enterprise.
ms.openlocfilehash: 28eff02ea870dcfca7e2e32580ed6a3a9e8a9484
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/13/2020
ms.locfileid: "42806618"
---
# <a name="information-protection-infrastructure-exit-criteria"></a><span data-ttu-id="74211-103">Uitgangscriteria voor de infrastructuur voor gegevensbeveiliging</span><span class="sxs-lookup"><span data-stu-id="74211-103">Information protection infrastructure exit criteria</span></span>

![Fase 6: gegevensbescherming](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="74211-105">Zorg ervoor dat de op gegevensbeveiliging gebaseerde infrastructuur aan de volgende vereiste criteria voldoet en dat u de optionele criteria hebt overwogen.</span><span class="sxs-lookup"><span data-stu-id="74211-105">Make sure your information protection infrastructure meets the following required criteria and that you've considered those that are optional.</span></span>

<a name="crit-infoprotect-step1"></a>
## <a name="required-security-and-information-protection-levels-for-your-organization-are-defined"></a><span data-ttu-id="74211-106">Vereist: de beveiligings- en gegevensbeschermingsniveaus voor uw organisatie zijn gedefinieerd</span><span class="sxs-lookup"><span data-stu-id="74211-106">Required: Security and information protection levels for your organization are defined</span></span>

<span data-ttu-id="74211-107">U hebt de beveiligingsniveaus die uw organisatie nodig heeft gepland en vastgesteld.</span><span class="sxs-lookup"><span data-stu-id="74211-107">You've planned for and determined the security levels that your organization needs.</span></span> <span data-ttu-id="74211-108">Deze niveaus bepalen een minimaal beveiligingsniveau en aanvullende niveaus voor steeds gevoeliger wordende gegevens en de bijbehorende gegevensbeveiliging.</span><span class="sxs-lookup"><span data-stu-id="74211-108">These levels define a minimum level of security and additional levels for increasingly sensitive information and their required data security.</span></span>

<span data-ttu-id="74211-109">U gebruikt minimaal drie beveiligingsniveaus:</span><span class="sxs-lookup"><span data-stu-id="74211-109">At a minimum, you are using three security levels:</span></span>

- <span data-ttu-id="74211-110">Basislijn</span><span class="sxs-lookup"><span data-stu-id="74211-110">Baseline</span></span>
- <span data-ttu-id="74211-111">Gevoelig</span><span class="sxs-lookup"><span data-stu-id="74211-111">Sensitive</span></span>
- <span data-ttu-id="74211-112">Sterk gereglementeerd</span><span class="sxs-lookup"><span data-stu-id="74211-112">Highly regulated</span></span>

<span data-ttu-id="74211-113">Via [Stap 1](infoprotect-define-sec-infoprotect-levels.md) kunt u zo nodig aan deze vereisten voldoen.</span><span class="sxs-lookup"><span data-stu-id="74211-113">If needed, [Step 1](infoprotect-define-sec-infoprotect-levels.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step3"></a>
## <a name="required-increased-security-for-microsoft-365-is-configured"></a><span data-ttu-id="74211-114">Vereist: verbeterde beveiliging voor Microsoft 365 is geconfigureerd</span><span class="sxs-lookup"><span data-stu-id="74211-114">Required: Increased security for Microsoft 365 is configured</span></span>

<span data-ttu-id="74211-115">U hebt de volgende instellingen voor [Office 365 verhoogde beveiliging](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security) geconfigureerd:</span><span class="sxs-lookup"><span data-stu-id="74211-115">You've configured the following settings for [Office 365 increased security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security):</span></span>

- <span data-ttu-id="74211-116">Beleid voor bedreigingsbeheer in het Microsoft 365-beveiligingscentrum</span><span class="sxs-lookup"><span data-stu-id="74211-116">Threat management policies in the Microsoft 365 security Center</span></span>
- <span data-ttu-id="74211-117">Aanvullende, tenant-brede Exchange Online-instellingen</span><span class="sxs-lookup"><span data-stu-id="74211-117">Additional Exchange Online tenant-wide settings</span></span>
- <span data-ttu-id="74211-118">Tenant-breed deelbeleid in SharePoint Online-beheercentrum</span><span class="sxs-lookup"><span data-stu-id="74211-118">Tenant-wide sharing policies in SharePoint Online admin center</span></span>
- <span data-ttu-id="74211-119">Instellingen in Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="74211-119">Settings in Azure Active Directory (Azure AD)</span></span>

<span data-ttu-id="74211-120">U hebt ook [Office 365 Advanced Threat Protection (ATP) voor bestanden in SharePoint, OneDrive en Microsoft Teams ingeschakeld](https://docs.microsoft.com/office365/securitycompliance/turn-on-atp-for-spo-odb-and-teams).</span><span class="sxs-lookup"><span data-stu-id="74211-120">You've also [enabled Office 365 Advanced Threat Protection (ATP) for SharePoint, OneDrive, and Microsoft Teams](https://docs.microsoft.com/office365/securitycompliance/turn-on-atp-for-spo-odb-and-teams).</span></span>

<span data-ttu-id="74211-121">Via [Stap 3](infoprotect-configure-increased-security-office-365.md) kunt u zo nodig aan deze vereisten voldoen.</span><span class="sxs-lookup"><span data-stu-id="74211-121">If needed, [Step 3](infoprotect-configure-increased-security-office-365.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step2"></a>
## <a name="optional-classification-is-configured-across-your-environment"></a><span data-ttu-id="74211-122">Optioneel: classificatie wordt in uw gehele omgeving geconfigureerd</span><span class="sxs-lookup"><span data-stu-id="74211-122">Optional: Classification is configured across your environment</span></span>

<span data-ttu-id="74211-123">U hebt samen met uw juridische en compliance-teams een geschikt classificatie- en labelsysteem ontwikkeld voor het beheer van gegevens en het beveiligingsbeleid van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="74211-123">You've worked with your legal and compliance teams to develop an appropriate classification and labeling scheme for your organization’s data governance and security policies.</span></span> 

<span data-ttu-id="74211-124">Dit beleid komt overeen met de configuratie en implementatie van:</span><span class="sxs-lookup"><span data-stu-id="74211-124">Those policies correspond to the configuration and deployment of:</span></span>

- <span data-ttu-id="74211-125">Gevoelige gegevenstypen</span><span class="sxs-lookup"><span data-stu-id="74211-125">Sensitive data types</span></span>
- <span data-ttu-id="74211-126">Retentielabels</span><span class="sxs-lookup"><span data-stu-id="74211-126">Retention labels</span></span>
- <span data-ttu-id="74211-127">Gevoeligheidslabels</span><span class="sxs-lookup"><span data-stu-id="74211-127">Sensitivity labels</span></span>
- <span data-ttu-id="74211-128">Azure Information Protection-labels</span><span class="sxs-lookup"><span data-stu-id="74211-128">Azure Information Protection labels</span></span>

<span data-ttu-id="74211-129">Via [Stap 2](infoprotect-configure-classification.md) kunt u zo nodig aan deze vereisten voldoen.</span><span class="sxs-lookup"><span data-stu-id="74211-129">If needed, [Step 2](infoprotect-configure-classification.md) can help you meet this requirement.</span></span> 


<a name="crit-infoprotect-step4"></a>
## <a name="optional-windows-information-protection-is-deployed-across-your-environment"></a><span data-ttu-id="74211-130">Optioneel: Windows-gegevensbescherming wordt in uw volledige omgeving geïmplementeerd</span><span class="sxs-lookup"><span data-stu-id="74211-130">Optional: Windows Information Protection is deployed across your environment</span></span>

<span data-ttu-id="74211-131">Uw Windows 10 Enterprise-apparaten hebben een Intune-beleid geïmplementeerd en toegepast dat bepaalt:</span><span class="sxs-lookup"><span data-stu-id="74211-131">Your enrolled Windows 10 Enterprise devices have an Intune policy deployed and applied that defines:</span></span>

- <span data-ttu-id="74211-132">Welke apps moeten worden beveiligd.</span><span class="sxs-lookup"><span data-stu-id="74211-132">Which apps to protect.</span></span>
- <span data-ttu-id="74211-133">Het niveau van de beveiliging.</span><span class="sxs-lookup"><span data-stu-id="74211-133">The level of protection.</span></span>
- <span data-ttu-id="74211-134">Waar de beveiliging wordt uitgebreid.</span><span class="sxs-lookup"><span data-stu-id="74211-134">Where the protection extends.</span></span>

<span data-ttu-id="74211-135">Via [Stap 4](infoprotect-deploy-windows-information-protection.md) kunt u zo nodig aan deze vereisten voldoen.</span><span class="sxs-lookup"><span data-stu-id="74211-135">If needed, [Step 4](infoprotect-deploy-windows-information-protection.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step5"></a>
## <a name="optional-office-365-data-loss-prevention-dlp-is-deployed"></a><span data-ttu-id="74211-136">Optioneel: Office 365-preventie van gegevensverlies (DLP) wordt geïmplementeerd</span><span class="sxs-lookup"><span data-stu-id="74211-136">Optional: Office 365 Data Loss Prevention (DLP) is deployed</span></span>

<span data-ttu-id="74211-137">U hebt de set DLP-beleidsregels, met locaties en regels met voorwaarden en acties, die uw organisatie nodig heeft om klant- en andere soorten privégegevens te beschermen en te voldoen aan branche- en regionale voorschriften en vereisten, geanalyseerd, getest en vervolgens uitgerold.</span><span class="sxs-lookup"><span data-stu-id="74211-137">You have analyzed, tested, and then rolled out the set of DLP policies—with locations and rules with conditions and actions—that your organization requires to protect customer and other types of private data and to adhere to industry and regional regulations and requirements.</span></span>

<span data-ttu-id="74211-138">Uw medewerkers voor compliance en beveiliging van gegevens gebruiken het Office 365-beveiligings- en compliance-dashboard om DLP-incidenten te bewaken.</span><span class="sxs-lookup"><span data-stu-id="74211-138">Your data compliance and security staff are using the Office 365 Security & Compliance dashboard to monitor DLP incidents.</span></span>

<span data-ttu-id="74211-139">Via [Stap 5](infoprotect-data-loss-prevention.md) kunt u zo nodig aan deze vereisten voldoen.</span><span class="sxs-lookup"><span data-stu-id="74211-139">If needed, [Step 5](infoprotect-data-loss-prevention.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step6"></a>
## <a name="optional-email-encryption-is-configured"></a><span data-ttu-id="74211-140">Optioneel: e-mailversleuteling wordt geconfigureerd</span><span class="sxs-lookup"><span data-stu-id="74211-140">Optional: Email encryption is configured</span></span>

<span data-ttu-id="74211-141">U hebt voor uw organisatie de volgende e-mailversleuteling geconfigureerd:</span><span class="sxs-lookup"><span data-stu-id="74211-141">You've configured the following email encryption as needed for your organization:</span></span>

|||
|:-------|:-----|
| <span data-ttu-id="74211-142">**Versleutelingsmethode**</span><span class="sxs-lookup"><span data-stu-id="74211-142">**Encryption method**</span></span> | <span data-ttu-id="74211-143">**Voor verzonden e-mail**</span><span class="sxs-lookup"><span data-stu-id="74211-143">**For email sent**</span></span> |
| [<span data-ttu-id="74211-144">Office 365-berichtversleuteling (OME)</span><span class="sxs-lookup"><span data-stu-id="74211-144">Office 365 Message Encryption (OME)</span></span>](https://docs.microsoft.com/Office365/SecurityCompliance/ome)  | <span data-ttu-id="74211-145">Buiten uw organisatie met versleuteling</span><span class="sxs-lookup"><span data-stu-id="74211-145">Outside your organization with encryption</span></span> |
| [<span data-ttu-id="74211-146">IRM (Information Rights Management)</span><span class="sxs-lookup"><span data-stu-id="74211-146">Information Rights Management (IRM)</span></span>](https://docs.microsoft.com/office365/SecurityCompliance/information-rights-management-in-exchange-online) | <span data-ttu-id="74211-147">Met zowel versleuteling als machtigingen</span><span class="sxs-lookup"><span data-stu-id="74211-147">With both encryption and permissions</span></span> |
| [<span data-ttu-id="74211-148">S/MIME (Secure/Multipurpose Internet Mail Extensions)</span><span class="sxs-lookup"><span data-stu-id="74211-148">Secure/Multipurpose Internet Mail Extensions (S/MIME)</span></span>](https://docs.microsoft.com/Exchange/policy-and-compliance/smime) | <span data-ttu-id="74211-149">Waarbij zowel versleuteling als digitale handtekeningen openbare sleutelcryptografie gebruiken</span><span class="sxs-lookup"><span data-stu-id="74211-149">With both encryption and digital signatures using public key cryptography</span></span> |
|||

<span data-ttu-id="74211-150">Via [Stap 6](infoprotect-email-encryption.md) kunt u zo nodig aan deze vereisten voldoen.</span><span class="sxs-lookup"><span data-stu-id="74211-150">If needed, [Step 6](infoprotect-email-encryption.md) can help you meet this requirement.</span></span>

<a name="crit-infoprotect-step7"></a>
## <a name="optional-configure-privileged-access-management-in-office-365"></a><span data-ttu-id="74211-151">Optioneel: configureer bevoegd toegangsbeheer in Office 365</span><span class="sxs-lookup"><span data-stu-id="74211-151">Optional: Configure privileged access management in Office 365</span></span>

<span data-ttu-id="74211-152">U hebt de informatie in [Privileged Access Management (bevoegd toegangsbeheer) configureren in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) gebruikt om Privileged Access Management in te schakelen en een of meer beleidsregels voor geprivilegieerde toegang in uw organisatie te maken.</span><span class="sxs-lookup"><span data-stu-id="74211-152">You've used the information in the [Configure privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic to enable privileged access and create one or more privileged access policies in your organization.</span></span> <span data-ttu-id="74211-153">U hebt deze beleidsregels geconfigureerd en just-in-time-toegang is ingeschakeld voor toegang tot gevoelige gegevens of kritieke configuratie-instellingen.</span><span class="sxs-lookup"><span data-stu-id="74211-153">You've configured these policies and just-in-time access is enabled for access to sensitive data or access to critical configuration settings.</span></span>

<span data-ttu-id="74211-154">Via [Stap 7](infoprotect-configure-privileged-access-management.md) kunt u zo nodig aan deze vereisten voldoen.</span><span class="sxs-lookup"><span data-stu-id="74211-154">If needed, [Step 7](infoprotect-configure-privileged-access-management.md) can help you meet this requirement.</span></span> 

## <a name="results-and-next-steps"></a><span data-ttu-id="74211-155">Resultaten en volgende stappen</span><span class="sxs-lookup"><span data-stu-id="74211-155">Results and next steps</span></span>

<span data-ttu-id="74211-156">De infrastructuur voor informatiebescherming voor Microsoft 365 Enterprise gebruikt gedefinieerde beveiligingsniveaus, verhoogde beveiliging voor Office 365, classificatie met gevoelige gegevenstypen en labels, Windows-gegevensbescherming, preventie van gegevensverlies, e-mail versleuteling en beleid voor geprivilegieerde toegang.</span><span class="sxs-lookup"><span data-stu-id="74211-156">Your information protection infrastructure for Microsoft 365 Enterprise uses defined security levels, increased security for Office 365, classification using sensitive data types and labels, Windows Information Protection, Data Loss Prevention, email encryption, and privileged access management.</span></span>

<span data-ttu-id="74211-157">Als u de volledige implementatie van Microsoft 365 Enterprise hebt gevolgd, bent u nu klaar om uw [workloads en scenario's](deploy-workloads.md) te laten profiteren van alle functies en configuraties van uw basisinfrastructuur.</span><span class="sxs-lookup"><span data-stu-id="74211-157">If you're following the end-to-end deployment of Microsoft 365 Enterprise, you're now ready to have your [workloads and scenarios](deploy-workloads.md) take advantage of all the features and configuration of your foundation infrastructure.</span></span>