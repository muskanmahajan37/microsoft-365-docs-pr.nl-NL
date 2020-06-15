---
title: Compliance Score en Compliance Manager gebruiken om verbeteracties te beheren
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- M365solutions
ms.custom: ''
description: Meer informatie over het gebruik van Complance Score en Compliance Manager om uw beschermingsniveau voor persoonsgegevens te verbeteren.
ms.openlocfilehash: 0d95c663030cf63fb83dfd40c7f3605c1c0b6f8f
ms.sourcegitcommit: b03a7ad0a80f8b839f40b8d396ab3a049491a12f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/10/2020
ms.locfileid: "44695171"
---
# <a name="use-compliance-score-and-compliance-manager-to-manage-improvement-actions"></a><span data-ttu-id="f65e1-103">Compliance Score en Compliance Manager gebruiken om verbeteracties te beheren</span><span class="sxs-lookup"><span data-stu-id="f65e1-103">Use Compliance Score and Compliance Manager to manage improvement actions</span></span>

<span data-ttu-id="f65e1-104">Microsoft Compliance Score en Compliance Manager kunnen samen worden gebruikt om verbeteringen in verband met de regelgeving inzake gegevensprivacy te beheren, zoals de [Algemene Verordening Gegevensbescherming (AVG) van](../compliance/gdpr.md)de Europese Unie, de California Consumer Protection Act [CCPA),](../compliance/ccpa-faq.md)HIPAA-HITECH (US Health Care Privacy Act) en de Brazil Data Protection Act (LGPD).</span><span class="sxs-lookup"><span data-stu-id="f65e1-104">Microsoft Compliance Score and Compliance Manager can be used together to manage improvements related to data privacy regulations such as the European Union [General Data Protection Regulation (GDPR)](../compliance/gdpr.md), [California Consumer Protection Act CCPA)](../compliance/ccpa-faq.md), HIPAA-HITECH (US health care privacy act), and the Brazil Data Protection Act (LGPD).</span></span> 

<span data-ttu-id="f65e1-105">In dit artikel vindt u richtlijnen voor het gebruik van deze hulpmiddelen voor gegevensprivacydoeleinden.</span><span class="sxs-lookup"><span data-stu-id="f65e1-105">This article provides guidance on the use of these tools for data privacy purposes.</span></span>

>[!Note]
><span data-ttu-id="f65e1-106">De klantacties in Compliance Manager zijn aanbevelingen.</span><span class="sxs-lookup"><span data-stu-id="f65e1-106">The customer actions provided in Compliance Manager are recommendations.</span></span> <span data-ttu-id="f65e1-107">Het is aan u om de effectiviteit van deze aanbevelingen in uw regelgevingsomgevingen te evalueren voordat deze worden geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="f65e1-107">It is up to you to evaluate the effectiveness of these recommendations in your regulatory environments prior to implementation.</span></span> <span data-ttu-id="f65e1-108">Aanbevelingen van compliancemanagers mogen niet worden geïnterpreteerd als een garantie voor naleving.</span><span class="sxs-lookup"><span data-stu-id="f65e1-108">Compliance Manager recommendations should not be interpreted as a guarantee of compliance.</span></span>
>

## <a name="planned-updates-for-compliance-score-and-compliance-manager"></a><span data-ttu-id="f65e1-109">Geplande updates voor Compliance Score en Compliance Manager</span><span class="sxs-lookup"><span data-stu-id="f65e1-109">Planned updates for Compliance Score and Compliance Manager</span></span>

<span data-ttu-id="f65e1-110">[Compliance Score](../compliance/compliance-score.md) (momenteel in preview) vereist het toevoegen van uw doelbeoordelingen voor een verordening (zoals GDPR) van de [Compliance Manager.](../compliance/compliance-manager-overview.md)</span><span class="sxs-lookup"><span data-stu-id="f65e1-110">[Compliance Score](../compliance/compliance-score.md) (currently in preview) requires adding your target assessments for a regulation (such as GDPR) from the [Compliance Manager](../compliance/compliance-manager-overview.md).</span></span> <span data-ttu-id="f65e1-111">In een toekomstige release wordt een groot deel van de functionaliteit in Compliance Manager samengevoegd tot een uniforme Compliance Score-ervaring, waardoor er minder behoefte is aan meerdere tools.</span><span class="sxs-lookup"><span data-stu-id="f65e1-111">In a future release, much of the functionality in Compliance Manager will be merged into a unified Compliance Score experience, reducing the need for multiple tools.</span></span>

<span data-ttu-id="f65e1-112">Dit zijn de tools voor uw abonnement, waarvoor u zich moet aanmelden:</span><span class="sxs-lookup"><span data-stu-id="f65e1-112">Here are the tools for your subscription, which require you to sign-in:</span></span>

- [<span data-ttu-id="f65e1-113">Compliance Score in het Microsoft Compliance-beheercentrum</span><span class="sxs-lookup"><span data-stu-id="f65e1-113">Compliance Score in the Microsoft Compliance admin center</span></span>](https://compliance.microsoft.com/compliancescore)
- [<span data-ttu-id="f65e1-114">Compliance Manager in de Microsoft Services Trust Portal</span><span class="sxs-lookup"><span data-stu-id="f65e1-114">Compliance Manager in the Microsoft Services Trust Portal</span></span>](https://servicetrust.microsoft.com/ComplianceManager/V3)

## <a name="getting-started-with-compliance-manager"></a><span data-ttu-id="f65e1-115">Aan de slag met Compliance Manager</span><span class="sxs-lookup"><span data-stu-id="f65e1-115">Getting started with Compliance Manager</span></span> 

<span data-ttu-id="f65e1-116">[Compliance Manager](../compliance/working-with-compliance-manager.md) (momenteel in preview) is een gratis workflowgebaseerde risicobeoordelingstool in de Microsoft Service Trust Portal voor het beheren van regelgevingsactiviteiten met betrekking tot Microsoft-cloudservices.</span><span class="sxs-lookup"><span data-stu-id="f65e1-116">[Compliance Manager](../compliance/working-with-compliance-manager.md) (currently in preview) is a free workflow-based risk assessment tool in the Microsoft Service Trust Portal for managing regulatory compliance activities related to Microsoft cloud services.</span></span> <span data-ttu-id="f65e1-117">Als onderdeel van uw Microsoft 365- of Azure Active Directory -abonnement (Azure AD) helpt Compliance Manager u bij het beheren van naleving van de regelgeving binnen het gedeelde verantwoordelijkheidsmodel voor Microsoft-cloudservices.</span><span class="sxs-lookup"><span data-stu-id="f65e1-117">As part of your Microsoft 365 or Azure Active Directory (Azure AD) subscription, Compliance Manager helps you manage regulatory compliance within the shared responsibility model for Microsoft cloud services.</span></span>

<span data-ttu-id="f65e1-118">Hoewel u uw algemene nalevingsscore bekijken en een aantal andere functies uitvoeren op de **compliancescorepagina** van het Compliance center, moet u Compliance Manager gebruiken via de Services Trust Portal om eerst beoordelingen voor uw regelgeving inzake gegevensprivacy te configureren.</span><span class="sxs-lookup"><span data-stu-id="f65e1-118">While you can view your overall compliance score and perform a number of other functions in the Compliance center's **Compliance Score** page, you need to use Compliance Manager through the Services Trust Portal to first configure assessments for your data privacy regulations.</span></span> <span data-ttu-id="f65e1-119">Gegevens uit deze beoordelingen worden vervolgens weergegeven in de nalevingsscore voor verder bekijken en filteren.</span><span class="sxs-lookup"><span data-stu-id="f65e1-119">Data from these assessments will then show up in Compliance Score for further viewing and filtering.</span></span> 

<span data-ttu-id="f65e1-120">Met behulp van de interface voor Compliance Manager u een of meer gegevensprivacygerelateerde regelgevingssjablonen selecteren en deze groeperen om vereiste verbeteringsacties in de set te beoordelen en bij te houden.</span><span class="sxs-lookup"><span data-stu-id="f65e1-120">Using the Compliance Manager interface, you can select one or more data privacy-related regulation templates and group them to assess and track required improvement actions across the set.</span></span> <span data-ttu-id="f65e1-121">U ook informatie bekijken over de besturingselementen die elke verordening vraagt om specifiek voor de doelservice, gescheiden door microsoft versus door de klant beheerde besturingselementen.</span><span class="sxs-lookup"><span data-stu-id="f65e1-121">You can also view information about the controls each regulation calls for specific to the target service, separated by Microsoft vs. customer-managed controls.</span></span>

<span data-ttu-id="f65e1-122">Beoordelingen en verbeteringsstatus die hier zijn geselecteerd, worden ook weergegeven in de compliancescore in het Microsoft Compliance Center, die het belang van uw eerste installatie in Compliance Manager benadrukken.</span><span class="sxs-lookup"><span data-stu-id="f65e1-122">Assessments and improvement status selected here also appear in Compliance Score in the Microsoft Compliance Center, which emphasize the importance of your initial setup in Compliance Manager.</span></span> <span data-ttu-id="f65e1-123">Deze relaties worden weergegeven in deze figuur.</span><span class="sxs-lookup"><span data-stu-id="f65e1-123">These relationships are shown in this figure.</span></span>
 
![Relaties van de compliancescore in het Microsoft Compliance Center](../media/information-protection-deploy-compliance/information-protection-deploy-compliance-ui.png)

<span data-ttu-id="f65e1-125">Hier volgen de belangrijkste stappen om u op weg te helpen.</span><span class="sxs-lookup"><span data-stu-id="f65e1-125">Here are the key steps to help you get started.</span></span>

### <a name="1-assessment-templates"></a><span data-ttu-id="f65e1-126">1. Beoordelingssjablonen</span><span class="sxs-lookup"><span data-stu-id="f65e1-126">1. Assessment templates</span></span>

<span data-ttu-id="f65e1-127">Vanuit de Compliance Manager is de eerste stap het toevoegen van beoordelingen die specifiek zijn voor de privacywetgeving van belang en deze op te nemen in een gedefinieerde groep "Gegevensprivacyverordeningen".</span><span class="sxs-lookup"><span data-stu-id="f65e1-127">From the Compliance Manager, the first step is to add assessments specific to the data privacy regulations of interest and include them in a defined "Data Privacy Regulations" group.</span></span>

<span data-ttu-id="f65e1-128">[Groepen](../compliance/working-with-compliance-manager.md#groups) zijn containers waarmee u beoordelingen organiseren en algemene informatie en werkstroomtaken delen tussen beoordelingen met dezelfde of gerelateerde door de klant beheerde besturingselementen.</span><span class="sxs-lookup"><span data-stu-id="f65e1-128">[Groups](../compliance/working-with-compliance-manager.md#groups) are containers that allow you to organize Assessments and share common information and workflow tasks between Assessments that have the same or related customer-managed controls.</span></span> <span data-ttu-id="f65e1-129">Wanneer twee verschillende beoordelingen in dezelfde groep door de klant beheerde controle delen, worden de voltooiing van implementatiegegevens, tests en status voor het besturingselement automatisch gesynchroniseerd met hetzelfde besturingselement in een andere beoordeling in de groep.</span><span class="sxs-lookup"><span data-stu-id="f65e1-129">When two different Assessments in the same group share customer-managed control, the completion of implementation details, testing, and status for the control automatically synchronize to the same control in any other Assessment in the Group.</span></span> <span data-ttu-id="f65e1-130">Dit verenigt de toegewezen actie-items voor elk besturingselement in de groep en vermindert dubbel werk.</span><span class="sxs-lookup"><span data-stu-id="f65e1-130">This unifies the assigned Action Items for each control across the group and reduces duplicating work.</span></span> 

<span data-ttu-id="f65e1-131">U er ook voor kiezen om groepen te gebruiken om te organiseren.</span><span class="sxs-lookup"><span data-stu-id="f65e1-131">You can also choose to use groups to organize.</span></span> <span data-ttu-id="f65e1-132">Beoordelingen per jaar, gebied, nalevingsnorm of andere groeperingen om uw nalevingswerk te organiseren.</span><span class="sxs-lookup"><span data-stu-id="f65e1-132">Assessments by year, area, compliance standard, or other groupings to help organize your compliance work.</span></span>


### <a name="2-action-items"></a><span data-ttu-id="f65e1-133">2. Actiepunten</span><span class="sxs-lookup"><span data-stu-id="f65e1-133">2. Action items</span></span>

<span data-ttu-id="f65e1-134">Zodra de beoordelingen zijn toegevoegd, u actiepunten bekijken die specifiek zijn voor elke groep of afzonderlijke verordening:</span><span class="sxs-lookup"><span data-stu-id="f65e1-134">Once the assessments have been added, you can view Action Items specific to each group or individual regulation:</span></span>

- <span data-ttu-id="f65e1-135">**Actielijst voor verbetering.**</span><span class="sxs-lookup"><span data-stu-id="f65e1-135">**Improvement action list.**</span></span> <span data-ttu-id="f65e1-136">Navigeer naar de lijst Actieitems en bekijk de verbeteringsacties die zijn gekoppeld aan de regelgeving die in de groep is opgenomen.</span><span class="sxs-lookup"><span data-stu-id="f65e1-136">Navigate to the Action Items list and view the improvement actions associated across the regulations included in the group.</span></span> <span data-ttu-id="f65e1-137">Veel acties omvatten regelgeving, zodat een enkele lijst item kan meerdere verordeningen vertegenwoordigen.</span><span class="sxs-lookup"><span data-stu-id="f65e1-137">Many actions span regulations so a single list item may represent multiple regulations.</span></span> 
 
- <span data-ttu-id="f65e1-138">**Verbetering actie filtering.**</span><span class="sxs-lookup"><span data-stu-id="f65e1-138">**Improvement action filtering.**</span></span> <span data-ttu-id="f65e1-139">Voor veel regelgeving voor gegevensprivacy en groepen regelgeving kan de lijst met verbeteracties vrij groot zijn, dus overweeg de lijst te filteren met behulp van de vervolgkeuzelijst filteren.</span><span class="sxs-lookup"><span data-stu-id="f65e1-139">For many data privacy regulations and groups of regulations, the list of improvement actions can be quite large, so consider filtering the list using the filter drop down.</span></span> <span data-ttu-id="f65e1-140">Als u bijvoorbeeld 'technische besturingselementen' selecteert, wordt de lijst teruggebracht tot alleen de taken met een technische implementatie in de organisatie, omdat veel van de acties gerelateerd zijn aan administratieve bewerkingen in verschillende aspecten van het bedrijf die ook zijn gedocumenteerd in Compliance Manager.</span><span class="sxs-lookup"><span data-stu-id="f65e1-140">For example, if you select "technical controls", the list will be reduced to just those which have a technical implementation in the organization, as many of the actions are related to administrative operations in various aspects of the business which are also documented in Compliance Manager.</span></span> <span data-ttu-id="f65e1-141">In dit artikel zullen we ons richten op technische controles, dus deze filteringsaanpak wordt aanbevolen.</span><span class="sxs-lookup"><span data-stu-id="f65e1-141">In this article, we will focus on technical controls, so this filtering approach is recommended.</span></span>
 
- <span data-ttu-id="f65e1-142">**Aanvullende informatie en beoordeling.**</span><span class="sxs-lookup"><span data-stu-id="f65e1-142">**Additional information and review.**</span></span> <span data-ttu-id="f65e1-143">Voor elke actie u op de link naar **Lees meer**klikken, die u meer vertelt over de aanbevolen activiteit of **Beoordeling**, waarmee u het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="f65e1-143">For each action, you can click on the link to **Read More**, which tells you more about the recommended activity, or **Review**, which opens a form allowing you to do the following:</span></span>
 
   - <span data-ttu-id="f65e1-144">De actie toewijzen aan iemand in uw organisatie om te beheren</span><span class="sxs-lookup"><span data-stu-id="f65e1-144">Assign the action to a someone in your organization to manage</span></span>
   - <span data-ttu-id="f65e1-145">Documenten beheren met betrekking tot het aanpakken van de actie</span><span class="sxs-lookup"><span data-stu-id="f65e1-145">Manage documents related to addressing the action</span></span>
   - <span data-ttu-id="f65e1-146">Status voor het item opgeven</span><span class="sxs-lookup"><span data-stu-id="f65e1-146">Specify status for the item</span></span>
   - <span data-ttu-id="f65e1-147">Uitvoerings- en testdatums opgeven</span><span class="sxs-lookup"><span data-stu-id="f65e1-147">Specify implementation and test dates</span></span>
   - <span data-ttu-id="f65e1-148">Aanvullende informatie, implementatienotities en testplannotities voor de onderwerpactie opnemen</span><span class="sxs-lookup"><span data-stu-id="f65e1-148">Record additional information, implementation notes, and test plan notes for the subject action</span></span>
  
- <span data-ttu-id="f65e1-149">**Niet-toepasselijke items als buiten het bereik.**</span><span class="sxs-lookup"><span data-stu-id="f65e1-149">**Non-applicable items as out-of-scope.**</span></span> <span data-ttu-id="f65e1-150">Sommige verbeteringsacties in de lijst Actieitems zijn mogelijk niet van toepassing op uw geplande implementatie.</span><span class="sxs-lookup"><span data-stu-id="f65e1-150">Some improvement actions included in the Action Items list might not apply to your planned implementation.</span></span> <span data-ttu-id="f65e1-151">U opgeven dat ze buiten het bereik van Compliance Manager vallen en de actie en het bewijs verwijderen uit de berekening van de waarde van de nalevingsscore.</span><span class="sxs-lookup"><span data-stu-id="f65e1-151">You can specify that they are out of scope in Compliance Manager and remove the action and its evidence from the calculation of the compliance score value.</span></span> 

<span data-ttu-id="f65e1-152">Als uw organisatie er bijvoorbeeld voor heeft gekozen om Microsoft Managed Key te gebruiken, is een aanbeveling voor Het gebruik van klantsleutel niet van toepassing op uw implementatie.</span><span class="sxs-lookup"><span data-stu-id="f65e1-152">For example, if your organization has elected to use Microsoft Managed Key", a recommendation to Use Customer Key is not applicable to your deployment.</span></span> <span data-ttu-id="f65e1-153">In dit geval markeert uw organisatie deze als **Niet in het bereik** in de **beheeracties** voor de toepasselijke regelgevingssjabloon.</span><span class="sxs-lookup"><span data-stu-id="f65e1-153">In this case, your organization would mark it as **Not in scope** in the **Control Actions** for the applicable regulatory template.</span></span>
 
### <a name="3-controls-info"></a><span data-ttu-id="f65e1-154">3. Controle info</span><span class="sxs-lookup"><span data-stu-id="f65e1-154">3. Controls info</span></span>

<span data-ttu-id="f65e1-155">Bekijk de controlegegevens voor elke beoordelingsgroep voor een [beoordelingsspecifieke](../compliance/compliance-manager-overview.md#controls) weergave.</span><span class="sxs-lookup"><span data-stu-id="f65e1-155">For an assessment-specific view, view the [Controls Info](../compliance/compliance-manager-overview.md#controls) for each assessment group.</span></span> <span data-ttu-id="f65e1-156">Dit biedt een beoordelingsspecifieke weergave, die verschil maakt dan de lijst met actie-items, die een technische controlespecifieke weergave biedt.</span><span class="sxs-lookup"><span data-stu-id="f65e1-156">This provides an assessment-specific view, which is difference than the Action Items list, which provides a technical control-specific view.</span></span>
 
![Relaties van beoordeling om items te controleren](../media/information-protection-deploy-compliance/information-protection-deploy-compliance-control.png)

<span data-ttu-id="f65e1-158">Navigeer naar de lijst **Met de controlegegevens** en bekijk de lijst met services in het bereik van de betreffende verordening.</span><span class="sxs-lookup"><span data-stu-id="f65e1-158">Navigate to the **Controls Info** list and view the list of in-scope services for the regulation in question.</span></span> 
 
<span data-ttu-id="f65e1-159">Regelgevingsspecifieke controlegroepen vermelden de acties die worden uitgevoerd door het controlegebied voor elk servicegebied.</span><span class="sxs-lookup"><span data-stu-id="f65e1-159">Regulation-specific control groupings list the actions provided by control area for each service area.</span></span> <span data-ttu-id="f65e1-160">Voor elke reeks acties biedt de Compliance Manager meer informatie over de actie en kan de organisatie beoordelingsopties voorstellen of bieden om de organisatie te helpen bij het kiezen van een controleaanpak.</span><span class="sxs-lookup"><span data-stu-id="f65e1-160">For each set of actions, the Compliance Manager provides more information on the action and may suggest or provide review options to assist the organization in choosing a control approach.</span></span>
 
<span data-ttu-id="f65e1-161">Houd er rekening mee dat deze interface de mogelijkheid biedt om details te bekijken die specifiek zijn voor de technische actie, samen met de status van acties met betrekking tot de controle en aanvullende context over de regelgeving waaraan de actie is gerelateerd.</span><span class="sxs-lookup"><span data-stu-id="f65e1-161">Note that this interface provides the capability to view details specific to the technical action, together with the status of actions related to the control, and supplemental context about the regulations to which the action is related.</span></span>

### <a name="4-template-download"></a><span data-ttu-id="f65e1-162">4. Sjabloon downloaden</span><span class="sxs-lookup"><span data-stu-id="f65e1-162">4. Template download</span></span>

<span data-ttu-id="f65e1-163">Voor degenen die meer vertrouwd zijn met spreadsheet-gebaseerde regelgevingsanalyse, een andere aanpak is het downloaden van de sjabloon voor elke respectieve beoordeling met behulp van de sjablonen vermelding.</span><span class="sxs-lookup"><span data-stu-id="f65e1-163">For those more familiar with spreadsheet-based regulatory analysis, another approach is to download the template for each respective assessment using the Templates listing.</span></span> <span data-ttu-id="f65e1-164">De gedownloade sjablonen bevatten zowel de wettelijke als technische controle-informatie voor elke sjabloon en kunnen voor bepaalde rollen gemakkelijker zijn om te navigeren/filteren en bedrijfsspecifieke weergaven te genereren.</span><span class="sxs-lookup"><span data-stu-id="f65e1-164">The downloaded templates list both the regulatory as well as technical control information for each template and may be easier for certain roles to navigate/filter and to generate business-specific views.</span></span>
 
<span data-ttu-id="f65e1-165">U ook een nieuwe sjabloon toevoegen die is aangepast voor uw organisatie op basis van een bestaande sjabloon, met **Sjabloon toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="f65e1-165">You can also add a new template customized for your organization based on an existing template, using **Add Template**.</span></span> <span data-ttu-id="f65e1-166">Dit vereist dat u een sjabloon naar keuze downloadt (zoals HIPAA/HITECH)), deze vervolgens voor uw doeleinden wijzigt en terug uploadt naar de Compliance Manager-tool, waar het nu beoordelingen en scores zal stimuleren die vergelijkbaar zijn met andere sjablonen en beoordelingen als onderdeel van de algemene compliancemanager en compliancescoretoolset.</span><span class="sxs-lookup"><span data-stu-id="f65e1-166">This requires that you download a template of choice (such as HIPAA/HITECH)), then modify it for your purposes and upload back into the Compliance Manager tool, where it will now drive assessments and scoring similar to other templates and assessments as part of the overall Compliance Manager and Compliance Score toolset.</span></span>
 
>[!Tip]
><span data-ttu-id="f65e1-167">Als u een groot aantal regelgeving of overlappende verbeteringsacties behandelt, u overwegen elke betreffende sjabloon te downloaden en de gegevenssets te combineren, verbeteringsacties of controletypen die niet van toepassing zijn op uw organisatie verwijderen en opnieuw uploaden.</span><span class="sxs-lookup"><span data-stu-id="f65e1-167">if dealing with a large number of regulations or overlapping improvement actions, consider downloading each respective template and combining the data sets, removing improvement actions or control types that do not apply to your organization, and re-uploading.</span></span> <span data-ttu-id="f65e1-168">Dit kan gemakkelijker zijn dan het navigeren in elke sectie controle-informatie en het markeren van elk als buiten het bereik.</span><span class="sxs-lookup"><span data-stu-id="f65e1-168">This may be easier than navigating every control info section and marking each as out of scope.</span></span>
>

## <a name="compliance-score"></a><span data-ttu-id="f65e1-169">Compliance Score</span><span class="sxs-lookup"><span data-stu-id="f65e1-169">Compliance Score</span></span>

<span data-ttu-id="f65e1-170">Zodra de beoordelingen en beoordelingsspecificaties zijn uitgevoerd in Compliance Manager, u nu naar de [compliancescore-tool](../compliance/working-with-compliance-score.md) gaan en de score bekijken en de gegevens verder snijden en de gegevens in blokjes snijden, inclusief het controlegebied.</span><span class="sxs-lookup"><span data-stu-id="f65e1-170">Once the assessments and review specifications are performed in Compliance Manager, you can now go to the [Compliance Score](../compliance/working-with-compliance-score.md) tool and review the score and slice and dice the data further, including by control area.</span></span>

<span data-ttu-id="f65e1-171">De Compliance Score-tool in het Microsoft 365 Compliance-beheercentrum biedt verschillende benaderingen voor het beoordelen en filteren van nalevingsgegevens die zijn verkregen van Compliance Manager en verschillende Microsoft 365-services.</span><span class="sxs-lookup"><span data-stu-id="f65e1-171">The Compliance Score tool in the Microsoft 365 Compliance admin center provides several approaches to review and filter compliance data obtained from Compliance Manager and various Microsoft 365 services.</span></span> <span data-ttu-id="f65e1-172">Deze tool wordt automatisch bijgewerkt wanneer verschillende configuratie-instellingen worden geïmplementeerd en deelt signalen met de Microsoft Secure Score, zodat veel verbeteringsacties in beide scores worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="f65e1-172">This tool is automatically updated when various configuration settings are implemented and shares signals with the Microsoft Secure Score so that many improvement actions will show up in both scores.</span></span> 
 
<span data-ttu-id="f65e1-173">De compliancescore biedt:</span><span class="sxs-lookup"><span data-stu-id="f65e1-173">The Compliance Score provides:</span></span>

- <span data-ttu-id="f65e1-174">Een verzamelde score, uitgesplitst door Microsoft en door klanten beheerde besturingselementen</span><span class="sxs-lookup"><span data-stu-id="f65e1-174">A collected score, broken down by Microsoft and customer-managed controls</span></span>
- <span data-ttu-id="f65e1-175">Een rollup van verbeteracties en voltooiingsstatus</span><span class="sxs-lookup"><span data-stu-id="f65e1-175">A rollup of improvement actions and completion status</span></span>
- <span data-ttu-id="f65e1-176">Een lijst van Microsoft 365-oplossingen die van invloed zijn op uw score</span><span class="sxs-lookup"><span data-stu-id="f65e1-176">A listing of Microsoft 365 solutions impacting your score</span></span>

### <a name="how-the-compliance-score-gets-calculated"></a><span data-ttu-id="f65e1-177">Hoe de nalevingsscore wordt berekend</span><span class="sxs-lookup"><span data-stu-id="f65e1-177">How the compliance score gets calculated</span></span>

<span data-ttu-id="f65e1-178">Kortom, de score wordt berekend op basis van een combinatie van Microsoft en door klanten beheerde controle-implementaties, zoals nader wordt uitgelegd in het [berekeningsartikel van](../compliance/compliance-score-methodology.md)de Microsoft Compliance Score .</span><span class="sxs-lookup"><span data-stu-id="f65e1-178">In short, the score is calculated based on a combination of Microsoft and customer-managed control implementations, as explained in more detail in the [Microsoft Compliance Score calculation article](../compliance/compliance-score-methodology.md).</span></span>

<span data-ttu-id="f65e1-179">Besturingselementen krijgen een scorewaarde toegewezen op basis van of ze verplicht of discretionair zijn en of ze preventief, detective of correctief zijn.</span><span class="sxs-lookup"><span data-stu-id="f65e1-179">Controls are assigned a score value based on whether they're mandatory or discretionary, and whether they're preventative, detective, or corrective.</span></span> <span data-ttu-id="f65e1-180">Deze vormen gezamenlijk het risico dat het niet ten opzichte van andere controles wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="f65e1-180">These collectively represent the risk of not implementing it relative to other controls.</span></span>

<span data-ttu-id="f65e1-181">Zoals gepresenteerd in het microsoft compliance score berekeningsartikel, krijgen preventieve controles een hogere score dan detective- en corrigerende controles en krijgen verplichte controles een hogere score dan discretionaire controles.</span><span class="sxs-lookup"><span data-stu-id="f65e1-181">As presented in the Microsoft Compliance Score calculation article, preventative controls get a higher score than detective and corrective ones, and mandatory controls get a higher score than discretionary ones.</span></span>
 
<span data-ttu-id="f65e1-182">Houd er rekening mee dat de gebruikersinterface van de beheerder van de nalevingsscore deze parameters niet vermeldt en ook niet de mogelijkheid biedt om erop te filteren.</span><span class="sxs-lookup"><span data-stu-id="f65e1-182">Note that the Compliance Score admin UI does not list these parameters, nor does it provide the ability to filter by them.</span></span> <span data-ttu-id="f65e1-183">Als u de bijbehorende sjabloon echter downloadt van het gereedschap Compliance Manager, worden deze parameters in de resulterende gegevensset wel vermeld voor de meeste regelgeving.</span><span class="sxs-lookup"><span data-stu-id="f65e1-183">However, if you download the associated template from the Compliance Manager tool, the resulting data set does list these parameters for most regulations.</span></span>

<span data-ttu-id="f65e1-184">Voor technische besturingselementen wordt de score voor verbeteringsactie automatisch bijgewerkt zodra de bijbehorende functie is geactiveerd.</span><span class="sxs-lookup"><span data-stu-id="f65e1-184">For technical controls, Compliance Score will automatically update the improvement action score once the related feature is activated.</span></span> <span data-ttu-id="f65e1-185">Andere, niet-technische &mdash; controleacties, zoals acties die operationeel zijn of gerelateerd zijn aan documentatie, moeten handmatig worden geregistreerd in de tool Compliance Manager op de Services Trust &mdash; Portal.</span><span class="sxs-lookup"><span data-stu-id="f65e1-185">Other, non-technical control actions&mdash;such as those that are operational or related to documentation&mdash;need to be recorded manually in the Compliance Manager tool on the Services Trust Portal.</span></span> 

<span data-ttu-id="f65e1-186">U veel ook de uitvoering van bepaalde verbetering acties voor andere doeleinden &mdash; voor bijvoorbeeld het gebruik van retentie labels om andere redenen dan de naleving van de regelgeving voor gegevensprivacy, zodat u krediet zou krijgen voor het gebruik van een dergelijke &mdash; functie, zelfs als het wordt gebruikt voor andere doeleinden, en geen deel uit van een opzettelijke naleving actie.</span><span class="sxs-lookup"><span data-stu-id="f65e1-186">You many also be implementing certain improvement actions for other purposes&mdash;for example using retention labels for reasons other than data privacy regulation compliance&mdash;so you would get credit for using such a feature even if it is being used for other purposes, and not part of a deliberate compliance action.</span></span>

<span data-ttu-id="f65e1-187">Uw compliancescore moet worden beschouwd als een relatieve maatregel om verbetering op grote schaal bij te houden.</span><span class="sxs-lookup"><span data-stu-id="f65e1-187">Your Compliance Score should be considered a relative measure to track improvement on a broad scale.</span></span> <span data-ttu-id="f65e1-188">Je moet niet streven naar een perfecte score.</span><span class="sxs-lookup"><span data-stu-id="f65e1-188">You should not pursue a perfect score.</span></span> 

### <a name="additional-guidance"></a><span data-ttu-id="f65e1-189">Aanvullende richtlijnen</span><span class="sxs-lookup"><span data-stu-id="f65e1-189">Additional guidance</span></span>

<span data-ttu-id="f65e1-190">Hier volgen enkele belangrijke tips voor het gebruik van Compliance Score en Compliance Manager voor u om naleving van de regelgeving voor gegevensprivacy te bereiken:</span><span class="sxs-lookup"><span data-stu-id="f65e1-190">Here are a few important tips for the use of Compliance Score and Compliance Manager for you to achieve data privacy regulation compliance:</span></span>

- <span data-ttu-id="f65e1-191">Elke verordening voor gegevensprivacy heeft een combinatie van technische controles, documentatiespecificaties en operationele, proces- en rapportagevereisten.</span><span class="sxs-lookup"><span data-stu-id="f65e1-191">Each data privacy regulation has a combination of technical controls, documentation specifications, and operational, process, and reporting requirements.</span></span> <span data-ttu-id="f65e1-192">Al deze verschijnen in de verbetering acties.</span><span class="sxs-lookup"><span data-stu-id="f65e1-192">All of these show up in the improvement actions.</span></span> 

- <span data-ttu-id="f65e1-193">Dit artikel richt zich op een subset van de technische besturingselementen die zijn opgegeven voor gegevensprivacy in Compliance Manager en Compliance Score.</span><span class="sxs-lookup"><span data-stu-id="f65e1-193">This article focuses on a subset of the technical controls specified for data privacy in Compliance Manager and Compliance Score.</span></span> <span data-ttu-id="f65e1-194">Raadpleeg de compliancemanager-tool en [documentatie](../compliance/working-with-compliance-score.md) voor meer informatie over niet-technische administratieve controles.</span><span class="sxs-lookup"><span data-stu-id="f65e1-194">Refer to the Compliance Manager tool and [documentation](../compliance/working-with-compliance-score.md) for more information on non-technical administrative controls.</span></span>

- <span data-ttu-id="f65e1-195">Als u de weergave van verbeteracties wilt richten op uw interessegebied, u filteren op actietype op het tabblad **Oplossingen** in de beheerder van de nalevingsscore.</span><span class="sxs-lookup"><span data-stu-id="f65e1-195">To focus the view of improvement actions to your area of interest, you can filter by action type in the **Solutions** tab in the Compliance Score admin.</span></span>

- <span data-ttu-id="f65e1-196">Het relatieve belang en de prioriteit van verbeteringsacties die zijn geïdentificeerd in de nalevingsscore, moet worden beschouwd als onderdeel van een bredere risicobeoordeling, samen met het risico op gegevensprivacy dat u hebt bepaald dat uw organisatie moet beheren.</span><span class="sxs-lookup"><span data-stu-id="f65e1-196">The relative importance and priority of improvement actions identified in Compliance Score should be considered as part of a broader risk review along with the data privacy risk you've determined your organization needs to manage.</span></span> 

- <span data-ttu-id="f65e1-197">Als u een wereldwijde organisatie bent en u meerdere sjablonen voor gegevensprivacyregelgeving toevoegt aan Compliance Manager als beoordelingen, combineert compliancescore elke toepasselijke sjabloon in een veldvermelding voor elke verbeteringsactie.</span><span class="sxs-lookup"><span data-stu-id="f65e1-197">If you are a global organization and you add multiple data privacy regulation templates into Compliance Manager as Assessments, Compliance Score will combine each applicable one in a field listing for each improvement action.</span></span>
 
- <span data-ttu-id="f65e1-198">Zelfs met verbeteringsactie aggregatie over meerdere wettelijke vereisten, als de regelgevingsbeoordelingssjablonen voor GDPR, LGPD, CCPA en HIPAA-HITECH worden geselecteerd, bijvoorbeeld, zullen bijna 400 verbeteringsacties worden geselecteerd in compliancescore.</span><span class="sxs-lookup"><span data-stu-id="f65e1-198">Even with improvement action aggregation across multiple regulatory requirements, if the regulation assessment templates for GDPR, LGPD, CCPA, and HIPAA-HITECH are selected, for example, almost 400 improvement actions will be listed in Compliance Score.</span></span> <span data-ttu-id="f65e1-199">Als u deze lange lijst beter wilt aanpakken, gebruikt u het filter voor verbeteringsactie om het resultaat te verlagen naar een meer beheersbare lijst.</span><span class="sxs-lookup"><span data-stu-id="f65e1-199">To better tackle this long list, use the improvement action filter to reduce the result set to a more manageable list.</span></span>

- <span data-ttu-id="f65e1-200">Het filter Categorieën biedt een middel om verbeteracties te filteren op logische groepering, waarop de artikelen Track, Prevent, Protect, Retain en Investigate in deze algemene oplossing zijn afgestemd.</span><span class="sxs-lookup"><span data-stu-id="f65e1-200">The Categories filter provides a means to filter improvement actions by logical grouping, which the Track, Prevent, Protect, Retain, and Investigate articles in this overall solution align to.</span></span> 

- <span data-ttu-id="f65e1-201">Sommige van de controles die in de verbeteringsacties worden vermeld kunnen meer direct worden gebonden aan een specifiek regelgevend artikel, terwijl andere controles indirect meer in verband met de geest van een verordening kunnen worden verbonden en vele tijden enkel dingen zijn u zou moeten nadenken doend hoe dan ook.</span><span class="sxs-lookup"><span data-stu-id="f65e1-201">Some of the controls listed in the improvement actions may be considered more directly tied to a specific regulatory article, while other controls may be more indirectly associated with the spirit of a regulation and are many times just things you should consider doing anyway.</span></span>
