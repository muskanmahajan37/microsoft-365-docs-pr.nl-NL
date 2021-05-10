---
title: IRM (Information Rights Management) toepassen op een lijst of bibliotheek
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 7/2/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- OSU150
- OSU160
- MET150
ms.assetid: 3bdb5c4e-94fc-4741-b02f-4e7cc3c54aa1
ms.collection:
- M365-security-compliance
- SPO_Content
description: U kunt IRM (Information Rights Management) gebruiken om bestanden te beheren en te beveiligen die worden gedownload uit lijsten of bibliotheken.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0648d511ee882765f1905e83ebdea673f306c186
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/12/2021
ms.locfileid: "52161691"
---
# <a name="apply-information-rights-management-irm-to-a-list-or-library"></a><span data-ttu-id="64646-103">IRM (Information Rights Management) toepassen op een lijst of bibliotheek</span><span class="sxs-lookup"><span data-stu-id="64646-103">Apply Information Rights Management (IRM) to a list or library</span></span>

<span data-ttu-id="64646-104">U kunt IRM (Information Rights Management) gebruiken om bestanden te beheren en te beveiligen die worden gedownload uit lijsten of bibliotheken.</span><span class="sxs-lookup"><span data-stu-id="64646-104">You can use Information Rights Management (IRM) to help control and protect files that are downloaded from lists or libraries.</span></span> <span data-ttu-id="64646-105">Deze functie wordt alleen ondersteund in de globale microsoft-cloud.</span><span class="sxs-lookup"><span data-stu-id="64646-105">This feature is only supported in the Microsoft global cloud.</span></span> <span data-ttu-id="64646-106">IRM wordt niet ondersteund voor SharePoint lijsten en bibliotheken in nationale cloudimplementaties.</span><span class="sxs-lookup"><span data-stu-id="64646-106">IRM is not supported for SharePoint lists and libraries in national cloud deployments.</span></span>
  
## <a name="administrator-preparations-before-applying-irm"></a><span data-ttu-id="64646-107">Voorbereidingen voor beheerders voordat u IRM toe te passen</span><span class="sxs-lookup"><span data-stu-id="64646-107">Administrator preparations before applying IRM</span></span>

- <span data-ttu-id="64646-108">De Azure Rights Management service (Azure RMS) van Azure Information Protection en het on-premises equivalent, Active Directory Rights Management Services (AD RMS), ondersteunen Information Rights Management voor sites.</span><span class="sxs-lookup"><span data-stu-id="64646-108">The Azure Rights Management service (Azure RMS) from Azure Information Protection, and the on-premises equivalent, Active Directory Rights Management Services (AD RMS), support Information Rights Management for sites.</span></span> <span data-ttu-id="64646-109">Er zijn geen afzonderlijke of extra installaties vereist.</span><span class="sxs-lookup"><span data-stu-id="64646-109">No separate or additional installations are required.</span></span>

- <span data-ttu-id="64646-110">Voordat u IRM op een lijst of bibliotheek gaat toepassen, moet u IRM voor uw site inschakelen.</span><span class="sxs-lookup"><span data-stu-id="64646-110">Before you apply IRM to a list or library, you need to enable IRM for your site.</span></span> <span data-ttu-id="64646-111">U hebt beheerdersmachtigingen nodig om IRM in te stellen.</span><span class="sxs-lookup"><span data-stu-id="64646-111">You'll need administrator permissions to enable IRM.</span></span>

- <span data-ttu-id="64646-112">Als u IRM wilt toepassen op een lijst of bibliotheek, moet u beheerdersmachtigingen hebben voor die lijst of bibliotheek.</span><span class="sxs-lookup"><span data-stu-id="64646-112">To apply IRM to a list or library, you must have administrator permissions for that list or library.</span></span>

- <span data-ttu-id="64646-113">Als u gebruik maakt van SharePoint Online, kunnen uw gebruikers time-outs ervaren bij het downloaden van grotere met IRM beveiligde bestanden.</span><span class="sxs-lookup"><span data-stu-id="64646-113">If you're using SharePoint Online, your users might experience timeouts when downloading larger IRM-protected files.</span></span> <span data-ttu-id="64646-114">Als u time-outs wilt voorkomen, gebruikt u uw Office programma's om IRM-beveiliging toe te passen en grotere bestanden op te slaan in een SharePoint bibliotheek die geen IRM gebruikt.</span><span class="sxs-lookup"><span data-stu-id="64646-114">To avoid timeouts, use your Office programs to apply IRM protection, and store larger files in a SharePoint library that doesn't use IRM.</span></span>

> [!NOTE]
> <span data-ttu-id="64646-115">Als u SharePoint Server 2013 gebruikt, moet een serverbeheerder beschermers installeren op alle front-endwebservers voor elk bestandstype dat de personen in uw organisatie willen beveiligen met behulp van IRM.</span><span class="sxs-lookup"><span data-stu-id="64646-115">If you're using SharePoint Server 2013, a server administrator must install protectors on all front-end Web servers for every file type that the people in your organization want to protect by using IRM.</span></span>
  
## <a name="apply-irm-to-a-list-or-library"></a><span data-ttu-id="64646-116">IRM toepassen op een lijst of bibliotheek</span><span class="sxs-lookup"><span data-stu-id="64646-116">Apply IRM to a list or library</span></span>
<span data-ttu-id="64646-117"><a name="__toc256598179"> </a></span><span class="sxs-lookup"><span data-stu-id="64646-117"><a name="__toc256598179"> </a></span></span>

![Information Rights Management Instellingen](../media/1b708102-9c90-42b0-b255-ef0e72d0be88.png)
  
1. <span data-ttu-id="64646-119">Ga naar de lijst of bibliotheek waarvoor u IRM wilt configureren.</span><span class="sxs-lookup"><span data-stu-id="64646-119">Go to the list or library for which you want to configure IRM.</span></span>

2. <span data-ttu-id="64646-120">Selecteer op het lint het tabblad **Bibliotheek** en selecteer vervolgens **Bibliotheek Instellingen.**</span><span class="sxs-lookup"><span data-stu-id="64646-120">On the ribbon, select the **Library** tab, and then select **Library Settings**.</span></span> <span data-ttu-id="64646-121">(Als u in een lijst werkt, selecteert u **het** tabblad Lijst en selecteert u **vervolgens Lijst Instellingen).**</span><span class="sxs-lookup"><span data-stu-id="64646-121">(If you're working in a list, select the **List** tab, and then select **List Settings**).</span></span>
    
    ![SharePoint Bibliotheekknoppen Instellingen op het lint](../media/cdf718fa-d792-40fc-8026-00c3b80b9e05.png)
  
3. <span data-ttu-id="64646-123">Selecteer **onder Machtigingen en beheer** de optie Information Rights **Management**.</span><span class="sxs-lookup"><span data-stu-id="64646-123">Under **Permissions and Management**, select **Information Rights Management**.</span></span> <span data-ttu-id="64646-124">Als de koppeling Information Rights Management niet wordt weergegeven, is IRM mogelijk niet ingeschakeld voor uw site.</span><span class="sxs-lookup"><span data-stu-id="64646-124">If the Information Rights Management link doesn't appear, IRM might not be enabled for your site.</span></span> <span data-ttu-id="64646-125">Neem contact op met de serverbeheerder om te kijken of u IRM voor uw site kunt inschakelen.</span><span class="sxs-lookup"><span data-stu-id="64646-125">Contact your server administrator to see if you can enable IRM for your site.</span></span> <span data-ttu-id="64646-126">De **koppeling Information Rights Management** wordt niet weergegeven voor afbeeldingsbibliotheken.</span><span class="sxs-lookup"><span data-stu-id="64646-126">The **Information Rights Management** link doesn't appear for picture libraries.</span></span>

4. <span data-ttu-id="64646-127">Schakel op **de pagina Information Rights Management Instellingen** het selectievakje Machtiging beperken voor documenten in deze bibliotheek bij **downloaden** in om beperkte machtigingen toe te passen op documenten die gebruikers uit deze lijst of bibliotheek downloaden.</span><span class="sxs-lookup"><span data-stu-id="64646-127">On the **Information Rights Management Settings** page, select the **Restrict permission to documents in this library on download** check box to apply restricted permission to documents users download from this list or library.</span></span>

5. <span data-ttu-id="64646-128">Voer in **het vak Titel van** machtigingsbeleid maken een beschrijvende naam voor het beleid in.</span><span class="sxs-lookup"><span data-stu-id="64646-128">In the **Create a permission policy title** box, enter a descriptive name for the policy.</span></span> <span data-ttu-id="64646-129">Gebruik een naam waarmee u dit beleid kunt identificeren op basis van andere beleidsregels.</span><span class="sxs-lookup"><span data-stu-id="64646-129">Use a name that helps you identify this policy from other policies.</span></span> <span data-ttu-id="64646-130">Gebruik bijvoorbeeld Bedrijfs **vertrouwelijk om** beperkte machtigingen toe te passen op een lijst of bibliotheek met vertrouwelijke bedrijfsdocumenten.</span><span class="sxs-lookup"><span data-stu-id="64646-130">For example, use **Company Confidential** to apply restricted permissions to a list or library that contains confidential company documents.</span></span>

6. <span data-ttu-id="64646-131">Typ in **het** vak Beschrijving van machtigingsbeleid toevoegen een beschrijving die wordt weergegeven voor personen die deze lijst of bibliotheek gebruiken, waarin wordt uitgelegd hoe ze de documenten in deze lijst of bibliotheek moeten verwerken.</span><span class="sxs-lookup"><span data-stu-id="64646-131">In the **Add a permission policy description** box, type a description that will appear to people who use this list or library that explains how they should handle the documents in this list or library.</span></span> <span data-ttu-id="64646-132">U kunt bijvoorbeeld alleen de inhoud van dit document bespreken typen **met** andere werknemers als u de toegang tot de informatie in deze documenten wilt beperken tot interne werknemers.</span><span class="sxs-lookup"><span data-stu-id="64646-132">For example, you can type **Discuss the contents of this document only with other employees** if you want to restrict access to the information in these documents to internal employees.</span></span> 

7. <span data-ttu-id="64646-133">Als u extra beperkingen wilt toepassen op de documenten in deze lijst of bibliotheek, **selecteert** u Opties tonen en doet u een van de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="64646-133">To apply additional restrictions to the documents in this list or library, select **Show Options**, and do any of the following:</span></span>

|<span data-ttu-id="64646-134">**Ga als volgende te werk:**</span><span class="sxs-lookup"><span data-stu-id="64646-134">**To do this:**</span></span>|<span data-ttu-id="64646-135">**Ga als volgende te werk:**</span><span class="sxs-lookup"><span data-stu-id="64646-135">**Do this:**</span></span>|
|:-----|:-----|
|<span data-ttu-id="64646-136">Personen toestaan documenten uit deze lijst of bibliotheek af te drukken</span><span class="sxs-lookup"><span data-stu-id="64646-136">Allow people to print documents from this list or library</span></span>|<span data-ttu-id="64646-137">Schakel het **selectievakje Toestaan dat gebruikers kunnen afdrukken** in.</span><span class="sxs-lookup"><span data-stu-id="64646-137">Select the **Allow viewers to print** check box.</span></span>|
|<span data-ttu-id="64646-138">Sta personen met ten minste de machtiging Items weergeven toe om ingesloten code of macro's in een document uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="64646-138">Allow people with at least the View Items permission to run embedded code or macros on a document.</span></span>|<span data-ttu-id="64646-139">Schakel het **selectievakje Toestaan dat gebruikers script en schermlezer** kunnen uitvoeren in voor gedownloade documenten in. Als u deze optie selecteert, kunnen gebruikers code uitvoeren om de inhoud van een document op te halen.</span><span class="sxs-lookup"><span data-stu-id="64646-139">Select the **Allow viewers to run script and screen reader to function on downloaded documents** check box.If you select this option, users could run code to extract the contents of a document.</span></span>           |
|<span data-ttu-id="64646-140">Selecteer deze optie als u de toegang tot inhoud tot een bepaalde periode wilt beperken.</span><span class="sxs-lookup"><span data-stu-id="64646-140">Select this option if you want to restrict access to content to a specified period of time.</span></span> <span data-ttu-id="64646-141">Als u deze optie selecteert, verlopen de uitgiftelicenties van personen voor toegang tot de inhoud na het opgegeven aantal dagen en moeten personen terugkeren naar de server om hun referenties te verifiëren en een nieuw exemplaar te downloaden.</span><span class="sxs-lookup"><span data-stu-id="64646-141">If you select this option, people's issuance licenses to access the content will expire after the specified number of days, and people will be required to return to the server to verify their credentials and download a new copy.</span></span>|<span data-ttu-id="64646-142">Schakel het selectievakje Na het downloaden de rechten voor documenttoegang na dit aantal dagen **(1-365)** in en geef vervolgens het aantal dagen op waarvoor u wilt dat het document kan worden bekeken.</span><span class="sxs-lookup"><span data-stu-id="64646-142">Select the **After download, document access rights will expire after these number of days (1-365)** check box, and then specify the number of days for which you want the document to be viewable.</span></span>|
| <span data-ttu-id="64646-143">Voorkomen dat personen documenten uploaden die geen ondersteuning bieden voor IRM naar deze lijst of bibliotheek.</span><span class="sxs-lookup"><span data-stu-id="64646-143">Prevent people from uploading documents that do not support IRM to this list or library.</span></span> <span data-ttu-id="64646-144">Als u deze optie selecteert, kunnen personen geen van de volgende bestandstypen uploaden: Bestandstypen waarop geen bijbehorende IRM-beschermers zijn geïnstalleerd op alle front-endwebservers.</span><span class="sxs-lookup"><span data-stu-id="64646-144">If you select this option, people will not be able to upload any of the following file types: File types that do not have corresponding IRM protectors installed on all of the front-end web servers.</span></span> <span data-ttu-id="64646-145">Bestandstypen die SharePoint Server 2010 kunnen niet worden ontsleuteld.</span><span class="sxs-lookup"><span data-stu-id="64646-145">File types that SharePoint Server 2010 cannot decrypt.</span></span> <span data-ttu-id="64646-146">Bestandstypen die IRM-beveiligd zijn in een ander programma.</span><span class="sxs-lookup"><span data-stu-id="64646-146">File types that are IRM protected in another program.</span></span>|<span data-ttu-id="64646-147">Schakel het selectievakje Geen gebruikers toestaan om documenten te uploaden die geen **ondersteuning bieden voor IRM** in.</span><span class="sxs-lookup"><span data-stu-id="64646-147">Select the **Do not allow users to upload documents that do not support IRM** check box.</span></span>|
|<span data-ttu-id="64646-148">Verwijder beperkte machtigingen uit deze lijst of bibliotheek op een bepaalde datum.</span><span class="sxs-lookup"><span data-stu-id="64646-148">Remove restricted permissions from this list or library on a specific date.</span></span>|<span data-ttu-id="64646-149">Schakel het **selectievakje Toegang beperken tot de bibliotheek** stoppen bij in en selecteer vervolgens de juiste datum.</span><span class="sxs-lookup"><span data-stu-id="64646-149">Select the **Stop restricting access to the library at** check box, and then select the date that you want.</span></span>|
|<span data-ttu-id="64646-150">Besturingselement het interval dat referenties in de cache worden opgeslagen voor het programma dat is gelicentieerd om het document te openen.</span><span class="sxs-lookup"><span data-stu-id="64646-150">Control the interval that credentials are cached for the program that is licensed to open the document.</span></span>|<span data-ttu-id="64646-151">Schakel het selectievakje Gebruikers moeten hun referenties verifiëren met behulp van dit **interval (dagen)** in en voer vervolgens het interval in voor cachingreferenties in het aantal dagen.</span><span class="sxs-lookup"><span data-stu-id="64646-151">Select the **Users must verify their credentials using this interval (days)** check box, then enter the interval for caching credentials in number of days.</span></span>|
|<span data-ttu-id="64646-152">Groepsbeveiliging toestaan, zodat gebruikers kunnen delen met leden van dezelfde groep.</span><span class="sxs-lookup"><span data-stu-id="64646-152">Allow group protection so that users can share with members of the same group.</span></span>|<span data-ttu-id="64646-153">Selecteer **Groepsbeveiliging toestaan** en voer de naam van de groep in voor delen.</span><span class="sxs-lookup"><span data-stu-id="64646-153">Select **Allow group protection**, and enter the group's name for sharing.</span></span>|

8. <span data-ttu-id="64646-154">Nadat u klaar bent met het selecteren van de opties die u wilt selecteren, selecteert u **OK.**</span><span class="sxs-lookup"><span data-stu-id="64646-154">After you finish selecting the options you want, select **OK**.</span></span>
  
## <a name="what-is-information-rights-management"></a><span data-ttu-id="64646-155">Wat is Information Rights Management?</span><span class="sxs-lookup"><span data-stu-id="64646-155">What is Information Rights Management?</span></span>
<span data-ttu-id="64646-156"><a name="__toc256598175"> </a></span><span class="sxs-lookup"><span data-stu-id="64646-156"><a name="__toc256598175"> </a></span></span>

<span data-ttu-id="64646-157">Met IRM (Information Rights Management) kunt u de acties beperken die gebruikers kunnen uitvoeren op bestanden die zijn gedownload uit lijsten of bibliotheken.</span><span class="sxs-lookup"><span data-stu-id="64646-157">Information Rights Management (IRM) enables you to limit the actions that users can take on files that have been downloaded from lists or libraries.</span></span> <span data-ttu-id="64646-158">IRM versleutelt de gedownloade bestanden en beperkt de set gebruikers en programma's die deze bestanden mogen ontsleutelen.</span><span class="sxs-lookup"><span data-stu-id="64646-158">IRM encrypts the downloaded files and limits the set of users and programs that are allowed to decrypt these files.</span></span> <span data-ttu-id="64646-159">IRM kan ook de rechten beperken van de gebruikers die bestanden mogen lezen, zodat ze geen acties kunnen uitvoeren, zoals kopieën van de bestanden afdrukken of tekst ervan kopiëren.</span><span class="sxs-lookup"><span data-stu-id="64646-159">IRM can also limit the rights of the users who are allowed to read files, so that they cannot take actions such as print copies of the files or copy text from them.</span></span>
  
<span data-ttu-id="64646-160">U kunt IRM in lijsten of bibliotheken gebruiken om de verspreiding van gevoelige inhoud te beperken.</span><span class="sxs-lookup"><span data-stu-id="64646-160">You can use IRM on lists or libraries to limit the dissemination of sensitive content.</span></span> <span data-ttu-id="64646-161">Als u bijvoorbeeld een documentbibliotheek maakt om informatie over toekomstige producten te delen met geselecteerde marketingvertegenwoordigers, kunt u IRM gebruiken om te voorkomen dat deze personen deze inhoud delen met andere werknemers in het bedrijf.</span><span class="sxs-lookup"><span data-stu-id="64646-161">For example, if you are creating a document library to share information about upcoming products with selected marketing representatives, you can use IRM to prevent these individuals from sharing this content with other employees in the company.</span></span>
  
<span data-ttu-id="64646-162">Op een site kunt u IRM toepassen op een hele lijst of bibliotheek, in plaats van op afzonderlijke bestanden.</span><span class="sxs-lookup"><span data-stu-id="64646-162">On a site, you apply IRM to an entire list or library, rather than to individual files.</span></span> <span data-ttu-id="64646-163">Hierdoor kunt u eenvoudiger een consistent beveiligingsniveau voor een hele set documenten of bestanden garanderen.</span><span class="sxs-lookup"><span data-stu-id="64646-163">This makes it easier to ensure a consistent level of protection for an entire set of documents or files.</span></span> <span data-ttu-id="64646-164">IRM kan uw organisatie helpen bij het afdwingen van bedrijfsbeleid dat van toepassing is op het gebruik en de verspreiding van vertrouwelijke of bedrijfseigen informatie.</span><span class="sxs-lookup"><span data-stu-id="64646-164">IRM can thus help your organization to enforce corporate policies that govern the use and dissemination of confidential or proprietary information.</span></span>
  
> [!NOTE]
> <span data-ttu-id="64646-165">De informatie op deze pagina met betrekking tot Information Rights Management komt boven alle voorwaarden die verwijzen naar 'Information Rights Management' in een licentieovereenkomst van Microsoft SharePoint Server 2013 en SharePoint Server 2016.</span><span class="sxs-lookup"><span data-stu-id="64646-165">The information on this page regarding Information Rights Management supersedes any terms that reference 'Information Rights Management' in any Microsoft SharePoint Server 2013 and SharePoint Server 2016 license term agreements.</span></span> 
  
### <a name="how-irm-can-help-protect-content"></a><span data-ttu-id="64646-166">Hoe IRM inhoud kan beschermen</span><span class="sxs-lookup"><span data-stu-id="64646-166">How IRM can help protect content</span></span>
<span data-ttu-id="64646-167"><a name="__toc256598176"> </a></span><span class="sxs-lookup"><span data-stu-id="64646-167"><a name="__toc256598176"> </a></span></span>

<span data-ttu-id="64646-168">IRM helpt om beperkte inhoud op de volgende manieren te beveiligen:</span><span class="sxs-lookup"><span data-stu-id="64646-168">IRM helps to protect restricted content in the following ways:</span></span>
  
- <span data-ttu-id="64646-169">Hiermee voorkomt u dat een geautoriseerde viewer de inhoud kopieert, wijzigt, afdrukt, faxt of kopieert en kopieert voor niet-geautoriseerd gebruik</span><span class="sxs-lookup"><span data-stu-id="64646-169">Helps to prevent an authorized viewer from copying, modifying, printing, faxing, or copying and pasting the content for unauthorized use</span></span>
    
- <span data-ttu-id="64646-170">Hiermee voorkomt u dat een geautoriseerde viewer de inhoud kopieert met de functie Scherm afdrukken in Microsoft Windows</span><span class="sxs-lookup"><span data-stu-id="64646-170">Helps to prevent an authorized viewer from copying the content by using the Print Screen feature in Microsoft Windows</span></span>
    
- <span data-ttu-id="64646-171">Hiermee voorkomt u dat een niet-geautoriseerde viewer de inhoud kan bekijken als deze per e-mail wordt verzonden nadat deze van de server is gedownload</span><span class="sxs-lookup"><span data-stu-id="64646-171">Helps to prevent an unauthorized viewer from viewing the content if it is sent in e-mail after it is downloaded from the server</span></span>
    
- <span data-ttu-id="64646-172">Beperkt de toegang tot inhoud tot een bepaalde periode, waarna gebruikers hun referenties moeten bevestigen en de inhoud opnieuw moeten downloaden</span><span class="sxs-lookup"><span data-stu-id="64646-172">Restricts access to content to a specified period of time, after which users must confirm their credentials and download the content again</span></span>
    
- <span data-ttu-id="64646-173">Helpt bij het afdwingen van bedrijfsbeleid dat van toepassing is op het gebruik en de verspreiding van inhoud binnen uw organisatie</span><span class="sxs-lookup"><span data-stu-id="64646-173">Helps to enforce corporate policies that govern the use and dissemination of content within your organization</span></span>
    
### <a name="how-irm-cannot-help-protect-content"></a><span data-ttu-id="64646-174">Hoe IRM inhoud niet kan beschermen</span><span class="sxs-lookup"><span data-stu-id="64646-174">How IRM cannot help protect content</span></span>
<span data-ttu-id="64646-175"><a name="__toc256598177"> </a></span><span class="sxs-lookup"><span data-stu-id="64646-175"><a name="__toc256598177"> </a></span></span>

<span data-ttu-id="64646-176">IRM kan beperkte inhoud niet als volgt beveiligen:</span><span class="sxs-lookup"><span data-stu-id="64646-176">IRM cannot protect restricted content from the following:</span></span>
  
- <span data-ttu-id="64646-177">Wissen, diefstal, vastleggen of verzenden door schadelijke programma's zoals Trojaanse paarden, toetsaanslagloggers en bepaalde typen spyware</span><span class="sxs-lookup"><span data-stu-id="64646-177">Erasure, theft, capture, or transmission by malicious programs such as Trojan horses, keystroke loggers, and certain types of spyware</span></span>
    
- <span data-ttu-id="64646-178">Verlies of beschadiging vanwege de acties van computervirussen</span><span class="sxs-lookup"><span data-stu-id="64646-178">Loss or corruption because of the actions of computer viruses</span></span>
    
- <span data-ttu-id="64646-179">Handmatig kopiëren of opnieuwtyping van inhoud vanuit de weergave op een scherm</span><span class="sxs-lookup"><span data-stu-id="64646-179">Manual copying or retyping of content from the display on a screen</span></span>
    
- <span data-ttu-id="64646-180">Digitale of filmfoto's van inhoud die wordt weergegeven op een scherm</span><span class="sxs-lookup"><span data-stu-id="64646-180">Digital or film photography of content that is displayed on a screen</span></span>
    
- <span data-ttu-id="64646-181">Kopiëren via het gebruik van schermopnameprogramma's van derden</span><span class="sxs-lookup"><span data-stu-id="64646-181">Copying through the use of third-party screen-capture programs</span></span>
    
- <span data-ttu-id="64646-182">Kopiëren van metagegevens van inhoud (kolomwaarden) via het gebruik van programma's voor schermopname van derden of kopieer- en plakactie</span><span class="sxs-lookup"><span data-stu-id="64646-182">Copying of content metadata (column values) through the use of third-party screen-capture programs or copy-and-paste action</span></span>
  
## <a name="how-irm-works-for-lists-and-libraries"></a><span data-ttu-id="64646-183">Hoe IRM werkt voor lijsten en bibliotheken</span><span class="sxs-lookup"><span data-stu-id="64646-183">How IRM works for lists and libraries</span></span>
<span data-ttu-id="64646-184"><a name="__toc256598178"> </a></span><span class="sxs-lookup"><span data-stu-id="64646-184"><a name="__toc256598178"> </a></span></span>

<span data-ttu-id="64646-185">IRM-beveiliging wordt toegepast op bestanden op lijst- of bibliotheekniveau.</span><span class="sxs-lookup"><span data-stu-id="64646-185">IRM protection is applied to files at the list or library level.</span></span> <span data-ttu-id="64646-186">Wanneer IRM is ingeschakeld voor een bibliotheek, is rechtenbeheer van toepassing op alle bestanden in die bibliotheek.</span><span class="sxs-lookup"><span data-stu-id="64646-186">When IRM is enabled for a library, rights management applies to all of the files in that library.</span></span> <span data-ttu-id="64646-187">Wanneer IRM is ingeschakeld voor een lijst, is rechtenbeheer alleen van toepassing op bestanden die zijn gekoppeld aan lijstitems, niet de werkelijke lijstitems.</span><span class="sxs-lookup"><span data-stu-id="64646-187">When IRM is enabled for a list, rights management applies only to files that are attached to list items, not the actual list items.</span></span>
  
<span data-ttu-id="64646-188">Wanneer personen bestanden downloaden in een lijst of bibliotheek met IRM-functie, worden de bestanden versleuteld, zodat alleen geautoriseerde personen ze kunnen bekijken.</span><span class="sxs-lookup"><span data-stu-id="64646-188">When people download files in an IRM-enabled list or library, the files are encrypted so that only authorized people can view them.</span></span> <span data-ttu-id="64646-189">Elk door rechten beheerd bestand bevat ook een uitgiftelicentie die beperkingen oplegt aan de personen die het bestand bekijken.</span><span class="sxs-lookup"><span data-stu-id="64646-189">Each rights-managed file also contains an issuance license that imposes restrictions on the people who view the file.</span></span> <span data-ttu-id="64646-190">Typische beperkingen zijn het maken van een bestand alleen-lezen, het uitschakelen van het kopiëren van tekst, het voorkomen dat personen een lokale kopie opslaan en voorkomen dat personen het bestand afdrukken.</span><span class="sxs-lookup"><span data-stu-id="64646-190">Typical restrictions include making a file read-only, disabling the copying of text, preventing people from saving a local copy, and preventing people from printing the file.</span></span> <span data-ttu-id="64646-191">Clientprogramma's die door IRM ondersteunde bestandstypen kunnen lezen, gebruiken de uitgiftelicentie in het door rechten beheerde bestand om deze beperkingen af te dwingen.</span><span class="sxs-lookup"><span data-stu-id="64646-191">Client programs that can read IRM-supported file types use the issuance license within the rights-managed file to enforce these restrictions.</span></span> <span data-ttu-id="64646-192">Op deze manier behoudt een door rechten beheerd bestand de beveiliging ervan, zelfs nadat het van de server is gedownload.</span><span class="sxs-lookup"><span data-stu-id="64646-192">This is how a rights-managed file retains its protection even after it is downloaded from the server.</span></span>
  
<span data-ttu-id="64646-193">De typen beperkingen die worden toegepast op een bestand wanneer het wordt gedownload uit een lijst of bibliotheek, zijn gebaseerd op de machtigingen van de afzonderlijke gebruiker op de site die het bestand bevat.</span><span class="sxs-lookup"><span data-stu-id="64646-193">The types of restrictions that are applied to a file when it is downloaded from a list or library are based on the individual user's permissions on the site that contains the file.</span></span> <span data-ttu-id="64646-194">In de volgende tabel wordt uitgelegd hoe de machtigingen op sites overeenkomen met IRM-machtigingen.</span><span class="sxs-lookup"><span data-stu-id="64646-194">The following table explains how the permissions on sites correspond to IRM permissions.</span></span>
  
|<span data-ttu-id="64646-195">**Machtigingen**</span><span class="sxs-lookup"><span data-stu-id="64646-195">**Permissions**</span></span>|<span data-ttu-id="64646-196">**IRM-machtigingen**</span><span class="sxs-lookup"><span data-stu-id="64646-196">**IRM Permissions**</span></span>|
|:-----|:-----|
|<span data-ttu-id="64646-197">Machtigingen beheren, website beheren</span><span class="sxs-lookup"><span data-stu-id="64646-197">Manage Permissions, Manage Web Site</span></span>|<span data-ttu-id="64646-198">**Volledig beheer** (zoals gedefinieerd door het clientprogramma): Met deze machtiging kan een gebruiker over het algemeen machtigingen voor door rechten beheerde inhoud lezen, bewerken, kopiëren, opslaan en wijzigen.</span><span class="sxs-lookup"><span data-stu-id="64646-198">**Full control** (as defined by the client program): This permission generally allows a user to read, edit, copy, save, and modify permissions of rights-managed content.</span></span>|
|<span data-ttu-id="64646-199">Items bewerken, Lijsten beheren, Pagina's toevoegen en aanpassen</span><span class="sxs-lookup"><span data-stu-id="64646-199">Edit Items, Manage Lists, Add and Customize Pages</span></span>|<span data-ttu-id="64646-200">**Bewerken,** **kopiëren** en **opslaan:** een gebruiker kan  een bestand alleen afdrukken als het selectievakje Gebruikers toestaan documenten af te drukken is ingeschakeld op de pagina Information Rights Management Instellingen voor de lijst of bibliotheek.</span><span class="sxs-lookup"><span data-stu-id="64646-200">**Edit**, **Copy**, and **Save**: A user can print a file only if the **Allow users to print documents** check box is selected on the Information Rights Management Settings page for the list or library.</span></span>|
|<span data-ttu-id="64646-201">Items weergeven</span><span class="sxs-lookup"><span data-stu-id="64646-201">View Items</span></span>|<span data-ttu-id="64646-202">**Lezen:** Een gebruiker kan het document lezen, maar kan de inhoud ervan niet kopiëren of wijzigen.</span><span class="sxs-lookup"><span data-stu-id="64646-202">**Read**: A user can read the document, but cannot copy or modify its content.</span></span> <span data-ttu-id="64646-203">Een gebruiker kan alleen afdrukken als het selectievakje **Gebruikers toestaan** documenten af te drukken is ingeschakeld op de pagina Information Rights Management Instellingen voor de lijst of bibliotheek.</span><span class="sxs-lookup"><span data-stu-id="64646-203">A user can print only if the **Allow users to print documents** check box is selected on the Information Rights Management Settings page for the list or library.</span></span>|
|<span data-ttu-id="64646-204">Overige</span><span class="sxs-lookup"><span data-stu-id="64646-204">Other</span></span>|<span data-ttu-id="64646-205">Geen andere machtigingen komen rechtstreeks overeen met IRM-machtigingen.</span><span class="sxs-lookup"><span data-stu-id="64646-205">No other permissions correspond directly to IRM permissions.</span></span>|
   
<span data-ttu-id="64646-206">Wanneer u IRM inschakelen voor een lijst of bibliotheek in SharePoint Server 2013, kunt u alleen bestandstypen in die lijst of bibliotheek beveiligen waarvoor een protector is geïnstalleerd op alle front-endwebservers.</span><span class="sxs-lookup"><span data-stu-id="64646-206">When you enable IRM for a list or library in SharePoint Server 2013, you can only protect file types in that list or library for which a protector is installed on all front-end web servers.</span></span> <span data-ttu-id="64646-207">Een protector is een programma dat de versleuteling en ontsleuteling van door rechten beheerde bestanden van een specifieke bestandsindeling regelt.</span><span class="sxs-lookup"><span data-stu-id="64646-207">A protector is a program that controls the encryption and decryption of rights-managed files of a specific file format.</span></span> <span data-ttu-id="64646-208">SharePoint bevat beschermers voor de volgende bestandstypen:</span><span class="sxs-lookup"><span data-stu-id="64646-208">SharePoint includes protectors for the following file types:</span></span>
  
- <span data-ttu-id="64646-209">Microsoft Office InfoPath-formulieren</span><span class="sxs-lookup"><span data-stu-id="64646-209">Microsoft Office InfoPath forms</span></span>
    
- <span data-ttu-id="64646-210">De bestandsindelingen 97-2003 voor de volgende Microsoft Office: Word, Excel en PowerPoint</span><span class="sxs-lookup"><span data-stu-id="64646-210">The 97-2003 file formats for the following Microsoft Office programs: Word, Excel, and PowerPoint</span></span>
    
- <span data-ttu-id="64646-211">De Office XML-indelingen openen voor de volgende Microsoft Office: Word, Excel en PowerPoint</span><span class="sxs-lookup"><span data-stu-id="64646-211">The Office Open XML Formats for the following Microsoft Office programs: Word, Excel, and PowerPoint</span></span>
    
- <span data-ttu-id="64646-212">De XPS-indeling (XML Paper Specification)</span><span class="sxs-lookup"><span data-stu-id="64646-212">The XML Paper Specification (XPS) format</span></span>
    
<span data-ttu-id="64646-213">Als uw organisatie van plan is IRM te gebruiken om andere bestandstypen te beveiligen, moet uw serverbeheerder beschermers installeren voor deze extra bestandsindelingen.</span><span class="sxs-lookup"><span data-stu-id="64646-213">If your organization plans to use IRM to protect any other file types in addition to those listed above, your server administrator must install protectors for these additional file formats.</span></span>
  
