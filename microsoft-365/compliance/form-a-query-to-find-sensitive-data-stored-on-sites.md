---
title: Een query maken om te zoeken naar gevoelige gegevens die zijn opgeslagen op sites
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
- SPO_Content
localization_priority: Normal
search.appverid:
- MOE150
- MET150
description: Gebruik DLP (Data Loss Prevention) in SharePoint Online om documenten te ontdekken die gevoelige gegevens in uw tenant bevatten.
ms.openlocfilehash: 9582974a26e0e112a6b3851494d057cad2010796
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52161866"
---
# <a name="form-a-query-to-find-sensitive-data-stored-on-sites"></a><span data-ttu-id="d12b0-103">Een query maken om te zoeken naar gevoelige gegevens die zijn opgeslagen op sites</span><span class="sxs-lookup"><span data-stu-id="d12b0-103">Form a query to find sensitive data stored on sites</span></span>

<span data-ttu-id="d12b0-104">Gebruikers slaan vaak gevoelige gegevens, zoals creditcardnummers, socialezekerheidsnummers of persoonlijke, op hun sites op, en na een tijd kan dit een organisatie blootstellen aan een aanzienlijk risico op gegevensverlies.</span><span class="sxs-lookup"><span data-stu-id="d12b0-104">Users often store sensitive data, such as credit card numbers, social security numbers, or personal, on their sites, and over time this can expose an organization to significant risk of data loss.</span></span> <span data-ttu-id="d12b0-105">Documenten die zijn opgeslagen op sites, OneDrive voor Bedrijven sites, kunnen worden gedeeld met personen buiten de organisatie die geen toegang hebben tot de informatie.</span><span class="sxs-lookup"><span data-stu-id="d12b0-105">Documents stored on sites—including OneDrive for Business sites—could be shared with people outside the organization who shouldn't have access to the information.</span></span> <span data-ttu-id="d12b0-106">Met DLP (Data Loss Prevention) in SharePoint Online kunt u documenten ontdekken die gevoelige gegevens bevatten in uw tenant.</span><span class="sxs-lookup"><span data-stu-id="d12b0-106">With data loss prevention (DLP) in SharePoint Online, you can discover documents that contain sensitive data throughout your tenant.</span></span> <span data-ttu-id="d12b0-107">Nadat u de documenten hebt ontdekt, kunt u samen met de documenteigenaren de gegevens beveiligen.</span><span class="sxs-lookup"><span data-stu-id="d12b0-107">After discovering the documents, you can work with the document owners to protect the data.</span></span> <span data-ttu-id="d12b0-108">Met dit onderwerp kunt u een query maken om te zoeken naar gevoelige gegevens.</span><span class="sxs-lookup"><span data-stu-id="d12b0-108">This topic can help you form a query to search for sensitive data.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d12b0-109">Elektronische detectie of eDiscovery en DLP zijn premiumfuncties waarvoor SharePoint [online abonnement 2.](https://go.microsoft.com/fwlink/?LinkId=510080)</span><span class="sxs-lookup"><span data-stu-id="d12b0-109">Electronic discovery, or eDiscovery, and DLP are premium features that require [SharePoint Online Plan 2](https://go.microsoft.com/fwlink/?LinkId=510080).</span></span> 
  
## <a name="forming-a-basic-dlp-query"></a><span data-ttu-id="d12b0-110">Een basis-DLP-query vormen</span><span class="sxs-lookup"><span data-stu-id="d12b0-110">Forming a basic DLP query</span></span>

<span data-ttu-id="d12b0-111">Er zijn drie onderdelen die een basis-DLP-query maken: SensitiveType, count range en betrouwbaarheidsbereik.</span><span class="sxs-lookup"><span data-stu-id="d12b0-111">There are three parts that make up a basic DLP query: SensitiveType, count range, and confidence range.</span></span> <span data-ttu-id="d12b0-112">Zoals in de volgende afbeelding wordt geïllustreerd, is **SensitiveType:" \<type\> vereist** en beide **|\<count range\>** en zijn ze **|\<confidence range\>** optioneel.</span><span class="sxs-lookup"><span data-stu-id="d12b0-112">As illustrated in the following graphic, **SensitiveType:"\<type\>"** is required, and both **|\<count range\>** and **|\<confidence range\>** are optional.</span></span> 
  
![Voorbeeldquery onderverdeeld in vereist en optioneel](../media/DLP-query-example-text.png)
  
### <a name="sensitive-type---required"></a><span data-ttu-id="d12b0-114">Gevoelig type - vereist</span><span class="sxs-lookup"><span data-stu-id="d12b0-114">Sensitive type - required</span></span>

<span data-ttu-id="d12b0-115">Wat is elk onderdeel?</span><span class="sxs-lookup"><span data-stu-id="d12b0-115">So what is each part?</span></span> <span data-ttu-id="d12b0-116">SharePoint DLP-query's beginnen meestal met de eigenschap en een naam van het informatietype uit de inventaris van gevoelige informatietypen `SensitiveType:"` en eindigen met een [](/Exchange/what-the-sensitive-information-types-in-exchange-look-for-exchange-2013-help) `"` .</span><span class="sxs-lookup"><span data-stu-id="d12b0-116">SharePoint DLP queries typically begin with the property  `SensitiveType:"` and an information type name from the [sensitive information types inventory](/Exchange/what-the-sensitive-information-types-in-exchange-look-for-exchange-2013-help), and end with a  `"`.</span></span> <span data-ttu-id="d12b0-117">U kunt ook de naam gebruiken van een aangepast type [gevoelige informatie](create-a-custom-sensitive-information-type.md) dat u voor uw organisatie hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="d12b0-117">You can also use the name of a [custom sensitive information type](create-a-custom-sensitive-information-type.md) that you created for your organization.</span></span> <span data-ttu-id="d12b0-118">U zoekt bijvoorbeeld documenten met creditcardnummers.</span><span class="sxs-lookup"><span data-stu-id="d12b0-118">For example, you might be looking for documents that contain credit card numbers.</span></span> <span data-ttu-id="d12b0-119">In een dergelijk geval gebruikt u de volgende indeling:  `SensitiveType:"Credit Card Number"` .</span><span class="sxs-lookup"><span data-stu-id="d12b0-119">In such an instance, you'd use the following format:  `SensitiveType:"Credit Card Number"`.</span></span> <span data-ttu-id="d12b0-120">Omdat u het bereik van het aantal of het betrouwbaarheidsbereik niet hebt meegetelde, retourneert de query elk document waarin een creditcardnummer is gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="d12b0-120">Because you didn't include count range or confidence range, the query returns every document in which a credit card number is detected.</span></span> <span data-ttu-id="d12b0-121">Dit is de eenvoudigste query die u kunt uitvoeren en geeft de meeste resultaten als resultaat.</span><span class="sxs-lookup"><span data-stu-id="d12b0-121">This is the simplest query that you can run, and it returns the most results.</span></span> <span data-ttu-id="d12b0-122">Houd er rekening mee dat de spelling en afstand van het gevoelige type belangrijk zijn.</span><span class="sxs-lookup"><span data-stu-id="d12b0-122">Keep in mind that the spelling and spacing of the sensitive type matters.</span></span> 
  
### <a name="ranges---optional"></a><span data-ttu-id="d12b0-123">Bereik - optioneel</span><span class="sxs-lookup"><span data-stu-id="d12b0-123">Ranges - optional</span></span>

<span data-ttu-id="d12b0-124">Beide volgende twee delen zijn bereikbereiken, dus laten we snel bekijken hoe een bereik eruitziet.</span><span class="sxs-lookup"><span data-stu-id="d12b0-124">Both of the next two parts are ranges, so let's quickly examine what a range looks like.</span></span> <span data-ttu-id="d12b0-125">In SharePoint DLP-query's wordt een basisbereik vertegenwoordigd door twee getallen die zijn gescheiden door twee perioden, wat er als volgende uitziet: `[number]..[number]` .</span><span class="sxs-lookup"><span data-stu-id="d12b0-125">In SharePoint DLP queries, a basic range is represented by two numbers separated by two periods, which looks like this:  `[number]..[number]`.</span></span> <span data-ttu-id="d12b0-126">Als dit bereik bijvoorbeeld wordt gebruikt, worden getallen van  `10..20` 10 tot en met 20 vast gemaakt.</span><span class="sxs-lookup"><span data-stu-id="d12b0-126">For instance, if  `10..20` is used, that range would capture numbers from 10 through 20.</span></span> <span data-ttu-id="d12b0-127">Er zijn veel verschillende bereikcombinaties en er worden er verschillende besproken in dit onderwerp.</span><span class="sxs-lookup"><span data-stu-id="d12b0-127">There are many different range combinations and several are covered in this topic.</span></span> 
  
<span data-ttu-id="d12b0-128">Laten we een aantalbereik toevoegen aan de query.</span><span class="sxs-lookup"><span data-stu-id="d12b0-128">Let's add a count range to the query.</span></span> <span data-ttu-id="d12b0-129">U kunt het aantalbereiken gebruiken om het aantal exemplaren te definiëren van gevoelige informatie die een document moet bevatten voordat het wordt opgenomen in de queryresultaten.</span><span class="sxs-lookup"><span data-stu-id="d12b0-129">You can use count range to define the number of occurrences of sensitive information a document needs to contain before it's included in the query results.</span></span> <span data-ttu-id="d12b0-130">Als u bijvoorbeeld wilt dat uw query alleen documenten retourneert die precies vijf creditcardnummers bevatten, gebruikt u dit:  `SensitiveType:"Credit Card Number|5"` .</span><span class="sxs-lookup"><span data-stu-id="d12b0-130">For example, if you want your query to return only documents that contain exactly five credit card numbers, use this:  `SensitiveType:"Credit Card Number|5"`.</span></span> <span data-ttu-id="d12b0-131">Het bereik aantal kan u ook helpen bij het identificeren van documenten met een hoog risico.</span><span class="sxs-lookup"><span data-stu-id="d12b0-131">Count range can also help you identify documents that pose high degrees of risk.</span></span> <span data-ttu-id="d12b0-132">Uw organisatie kan documenten met vijf of meer creditcardnummers bijvoorbeeld als een hoog risico beschouwen.</span><span class="sxs-lookup"><span data-stu-id="d12b0-132">For example, your organization might consider documents with five or more credit card numbers a high risk.</span></span> <span data-ttu-id="d12b0-133">Als u documenten wilt zoeken die aan dit criterium voldoen, gebruikt u deze query:  `SensitiveType:"Credit Card Number|5.."` .</span><span class="sxs-lookup"><span data-stu-id="d12b0-133">To find documents fitting this criterion, you would use this query:  `SensitiveType:"Credit Card Number|5.."`.</span></span> <span data-ttu-id="d12b0-134">U kunt ook documenten met vijf of minder creditcardnummers vinden met behulp van deze query:  `SensitiveType:"Credit Card Number|..5"` .</span><span class="sxs-lookup"><span data-stu-id="d12b0-134">Alternatively, you can find documents with five or fewer credit card numbers by using this query:  `SensitiveType:"Credit Card Number|..5"`.</span></span> 
  
#### <a name="confidence-range"></a><span data-ttu-id="d12b0-135">Betrouwbaarheidsbereik</span><span class="sxs-lookup"><span data-stu-id="d12b0-135">Confidence range</span></span>

<span data-ttu-id="d12b0-136">Ten slotte is het betrouwbaarheidsbereik het betrouwbaarheidsniveau dat het gedetecteerde gevoelige type daadwerkelijk een overeenkomst is.</span><span class="sxs-lookup"><span data-stu-id="d12b0-136">Finally, confidence range is the level of confidence that the detected sensitive type is actually a match.</span></span> <span data-ttu-id="d12b0-137">De waarden voor het betrouwbaarheidsbereik werken op dezelfde manier als het aantalbereiken.</span><span class="sxs-lookup"><span data-stu-id="d12b0-137">The values for confidence range work similarly to count range.</span></span> <span data-ttu-id="d12b0-138">U kunt een query maken zonder een aantalbereiken op te tellen.</span><span class="sxs-lookup"><span data-stu-id="d12b0-138">You can form a query without including a count range.</span></span> <span data-ttu-id="d12b0-139">Als u bijvoorbeeld wilt zoeken naar documenten met een groot aantal creditcardnummers , zolang het betrouwbaarheidsbereik 85 procent of hoger is, gebruikt u deze query:  `SensitiveType:"Credit Card Number|*|85.."` .</span><span class="sxs-lookup"><span data-stu-id="d12b0-139">For example, to search for documents with any number of credit card numbers—as long as the confidence range is 85 percent or higher—you would use this query:  `SensitiveType:"Credit Card Number|*|85.."`.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="d12b0-140">Het sterretje `*` () is een jokerteken dat betekent dat elke waarde werkt.</span><span class="sxs-lookup"><span data-stu-id="d12b0-140">The asterisk ( `*`) is a wildcard character that means any value works.</span></span> <span data-ttu-id="d12b0-141">U kunt het jokerteken () gebruiken in het aantalbereik of in het betrouwbaarheidsbereik, maar `*` niet in een gevoelig type.</span><span class="sxs-lookup"><span data-stu-id="d12b0-141">You can use the wildcard character ( `*`) either in the count range or in the confidence range, but not in a sensitive type.</span></span> 
  
### <a name="additional-query-properties-and-search-operators-available-in-the-ediscovery-center"></a><span data-ttu-id="d12b0-142">Extra query-eigenschappen en zoekoperatoren beschikbaar in het eDiscovery-centrum</span><span class="sxs-lookup"><span data-stu-id="d12b0-142">Additional query properties and search operators available in the eDiscovery Center</span></span>

<span data-ttu-id="d12b0-143">DLP in SharePoint introduceert ook de eigenschap LastSensitiveContentScan, waarmee u kunt zoeken naar bestanden die binnen een bepaalde periode zijn gescand.</span><span class="sxs-lookup"><span data-stu-id="d12b0-143">DLP in SharePoint also introduces the LastSensitiveContentScan property, which can help you search for files scanned within a specific timeframe.</span></span> <span data-ttu-id="d12b0-144">Zie Voorbeelden van complexe query's in de volgende sectie voor queryvoorbeelden `LastSensitiveContentScan` met de eigenschap. [](#examples-of-complex-queries)</span><span class="sxs-lookup"><span data-stu-id="d12b0-144">For query examples with the  `LastSensitiveContentScan` property, see the [Examples of complex queries](#examples-of-complex-queries) in the next section.</span></span> 
  
<span data-ttu-id="d12b0-145">U kunt niet alleen DLP-specifieke eigenschappen gebruiken om een query te maken, maar ook standaard SharePoint eDiscovery-zoekeigenschappen zoals `Author` of `FileExtension` .</span><span class="sxs-lookup"><span data-stu-id="d12b0-145">You can use not only DLP-specific properties to create a query, but also standard SharePoint eDiscovery search properties such as  `Author` or  `FileExtension`.</span></span> <span data-ttu-id="d12b0-146">U kunt operatoren gebruiken om complexe query's te maken.</span><span class="sxs-lookup"><span data-stu-id="d12b0-146">You can use operators to build complex queries.</span></span> <span data-ttu-id="d12b0-147">Zie het blogbericht Zoekeigenschappen en operatoren gebruiken met [eDiscovery](/archive/blogs/quentin/using-search-properties-and-operators-with-ediscovery) voor de lijst met beschikbare eigenschappen en operatoren.</span><span class="sxs-lookup"><span data-stu-id="d12b0-147">For the list of available properties and operators, see the [Using Search Properties and Operators with eDiscovery](/archive/blogs/quentin/using-search-properties-and-operators-with-ediscovery) blog post.</span></span> 
  
## <a name="examples-of-complex-queries"></a><span data-ttu-id="d12b0-148">Voorbeelden van complexe query's</span><span class="sxs-lookup"><span data-stu-id="d12b0-148">Examples of complex queries</span></span>

<span data-ttu-id="d12b0-149">In de volgende voorbeelden worden verschillende gevoelige typen, eigenschappen en operatoren gebruikt om te illustreren hoe u uw query's kunt verfijnen om precies te vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="d12b0-149">The following examples use different sensitive types, properties, and operators to illustrate how you can refine your queries to find exactly what you're looking for.</span></span>
  
|<span data-ttu-id="d12b0-150">**Query**</span><span class="sxs-lookup"><span data-stu-id="d12b0-150">**Query**</span></span>|<span data-ttu-id="d12b0-151">**Uitleg**</span><span class="sxs-lookup"><span data-stu-id="d12b0-151">**Explanation**</span></span>|
|:-----|:-----|
| `SensitiveType:"International Banking Account Number (IBAN)"` <br/> |<span data-ttu-id="d12b0-152">De naam lijkt misschien vreemd omdat deze zo lang is, maar het is de juiste naam voor dat gevoelige type.</span><span class="sxs-lookup"><span data-stu-id="d12b0-152">The name might seem strange because it's so long, but it's the correct name for that sensitive type.</span></span> <span data-ttu-id="d12b0-153">Zorg ervoor dat u exacte namen gebruikt uit de [inventaris van gevoelige informatietypen.](/Exchange/what-the-sensitive-information-types-in-exchange-look-for-exchange-2013-help)</span><span class="sxs-lookup"><span data-stu-id="d12b0-153">Make sure to use exact names from the [sensitive information types inventory](/Exchange/what-the-sensitive-information-types-in-exchange-look-for-exchange-2013-help).</span></span> <span data-ttu-id="d12b0-154">U kunt ook de naam gebruiken van een aangepast type [gevoelige informatie](create-a-custom-sensitive-information-type.md) dat u voor uw organisatie hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="d12b0-154">You can also use the name of a [custom sensitive information type](create-a-custom-sensitive-information-type.md) that you created for your organization.</span></span>  <br/> |
| `SensitiveType:"Credit Card Number|1..4294967295|1..100"` <br/> |<span data-ttu-id="d12b0-155">Hiermee retourneert u documenten met ten minste één overeenkomst met het gevoelige type 'Creditcardnummer'.</span><span class="sxs-lookup"><span data-stu-id="d12b0-155">This returns documents with at least one match to the sensitive type "Credit Card Number."</span></span> <span data-ttu-id="d12b0-156">De waarden voor elk bereik zijn de respectievelijke minimum- en maximumwaarden.</span><span class="sxs-lookup"><span data-stu-id="d12b0-156">The values for each range are the respective minimum and maximum values.</span></span> <span data-ttu-id="d12b0-157">Een eenvoudigere manier om deze query te schrijven is  `SensitiveType:"Credit Card Number"` , maar waar is het plezier in dat?</span><span class="sxs-lookup"><span data-stu-id="d12b0-157">A simpler way to write this query is  `SensitiveType:"Credit Card Number"`, but where's the fun in that?</span></span>  <br/> |
| `SensitiveType:"Credit Card Number| 5..25" AND LastSensitiveContentScan:"8/11/2018..8/13/2018"` <br/> |<span data-ttu-id="d12b0-158">Dit retourneert documenten met 5-25 creditcardnummers die zijn gescand van 11 augustus 2018 tot en met 13 augustus 2018.</span><span class="sxs-lookup"><span data-stu-id="d12b0-158">This returns documents with 5-25 credit card numbers that were scanned from August 11, 2018 through August 13, 2018.</span></span>  <br/> |
| `SensitiveType:"Credit Card Number| 5..25" AND LastSensitiveContentScan:"8/11/2018..8/13/2018" NOT FileExtension:XLSX` <br/> |<span data-ttu-id="d12b0-159">Dit retourneert documenten met 5-25 creditcardnummers die zijn gescand van 11 augustus 2018 tot en met 13 augustus 2018.</span><span class="sxs-lookup"><span data-stu-id="d12b0-159">This returns documents with 5-25 credit card numbers that were scanned from August 11, 2018 through August 13, 2018.</span></span> <span data-ttu-id="d12b0-160">Bestanden met een XLSX-extensie worden niet opgenomen in de queryresultaten.</span><span class="sxs-lookup"><span data-stu-id="d12b0-160">Files with an XLSX extension aren't included in the query results.</span></span>  <span data-ttu-id="d12b0-161">`FileExtension` is een van de vele eigenschappen die u in een query kunt opnemen.</span><span class="sxs-lookup"><span data-stu-id="d12b0-161">`FileExtension` is one of many properties that you can include in a query.</span></span> <span data-ttu-id="d12b0-162">Zie Zoekeigenschappen en operatoren gebruiken met [eDiscovery](/archive/blogs/quentin/using-search-properties-and-operators-with-ediscovery)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="d12b0-162">For more information, see [Using Search Properties and Operators with eDiscovery](/archive/blogs/quentin/using-search-properties-and-operators-with-ediscovery).</span></span>  <br/> |
| `SensitiveType:"Credit Card Number" OR SensitiveType:"U.S. Social Security Number (SSN)"` <br/> |<span data-ttu-id="d12b0-163">Hiermee retourneert u documenten die een creditcardnummer of een sociaal-zekerheidsnummer bevatten.</span><span class="sxs-lookup"><span data-stu-id="d12b0-163">This returns documents that contain either a credit card number or a social security number.</span></span>  <br/> |
   
## <a name="examples-of-queries-to-avoid"></a><span data-ttu-id="d12b0-164">Voorbeelden van query's om te voorkomen</span><span class="sxs-lookup"><span data-stu-id="d12b0-164">Examples of queries to avoid</span></span>

<span data-ttu-id="d12b0-165">Niet alle query's worden gelijk gemaakt.</span><span class="sxs-lookup"><span data-stu-id="d12b0-165">Not all queries are created equal.</span></span> <span data-ttu-id="d12b0-166">In de volgende tabel worden voorbeelden gegeven van query's die niet werken met DLP in SharePoint en wordt beschreven waarom.</span><span class="sxs-lookup"><span data-stu-id="d12b0-166">The following table gives examples of queries that don't work with DLP in SharePoint and describes why.</span></span>
  
|<span data-ttu-id="d12b0-167">**Niet-ondersteunde query**</span><span class="sxs-lookup"><span data-stu-id="d12b0-167">**Unsupported query**</span></span>|<span data-ttu-id="d12b0-168">**Reden**</span><span class="sxs-lookup"><span data-stu-id="d12b0-168">**Reason**</span></span>|
|:-----|:-----|
| `SensitiveType:"Credit Card Number|.."` <br/> |<span data-ttu-id="d12b0-169">U moet ten minste één getal toevoegen.</span><span class="sxs-lookup"><span data-stu-id="d12b0-169">You must add at least one number.</span></span>  <br/> |
| `SensitiveType:"NotARule"` <br/> |<span data-ttu-id="d12b0-170">NotARule is geen geldige gevoelige typenaam.</span><span class="sxs-lookup"><span data-stu-id="d12b0-170">"NotARule" isn't a valid sensitive type name.</span></span> <span data-ttu-id="d12b0-171">Alleen namen in de [inventaristypen voor gevoelige informatie werken](/Exchange/what-the-sensitive-information-types-in-exchange-look-for-exchange-2013-help) in DLP-query's.</span><span class="sxs-lookup"><span data-stu-id="d12b0-171">Only names in the [sensitive information types inventory](/Exchange/what-the-sensitive-information-types-in-exchange-look-for-exchange-2013-help) work in DLP queries.</span></span>  <br/> |
| `SensitiveType:"Credit Card Number|0"` <br/> |<span data-ttu-id="d12b0-172">Nul is niet geldig als de minimumwaarde of de maximumwaarde in een bereik.</span><span class="sxs-lookup"><span data-stu-id="d12b0-172">Zero isn't valid as either the minimum value or the maximum value in a range.</span></span>  <br/> |
| `SensitiveType:"Credit Card Number"` <br/> |<span data-ttu-id="d12b0-173">Het is misschien moeilijk te zien, maar er is extra witruimte tussen 'Tegoed' en 'Kaart' waardoor de query ongeldig is.</span><span class="sxs-lookup"><span data-stu-id="d12b0-173">It's might be difficult to see, but there's extra white space between "Credit" and "Card" that makes the query invalid.</span></span> <span data-ttu-id="d12b0-174">Gebruik exacte gevoelige typenamen uit de [inventaris van gevoelige informatietypen.](/Exchange/what-the-sensitive-information-types-in-exchange-look-for-exchange-2013-help)</span><span class="sxs-lookup"><span data-stu-id="d12b0-174">Use exact sensitive type names from the [sensitive information types inventory](/Exchange/what-the-sensitive-information-types-in-exchange-look-for-exchange-2013-help).</span></span>  <br/> |
| `SensitiveType:"Credit Card Number|1. .3"` <br/> |<span data-ttu-id="d12b0-175">Het gedeelte met twee perioden mag niet worden gescheiden door een spatie.</span><span class="sxs-lookup"><span data-stu-id="d12b0-175">The two-period portion shouldn't be separated by a space.</span></span>  <br/> |
| `SensitiveType:"Credit Card Number| |1..|80.."` <br/> |<span data-ttu-id="d12b0-176">Er zijn te veel scheidingstekens voor pijpen (</span><span class="sxs-lookup"><span data-stu-id="d12b0-176">There are too many pipe delimiters (</span></span>|<span data-ttu-id="d12b0-177">).</span><span class="sxs-lookup"><span data-stu-id="d12b0-177">).</span></span> <span data-ttu-id="d12b0-178">Volg in plaats daarvan deze indeling: `SensitiveType: "Credit Card Number|1..|80.."`</span><span class="sxs-lookup"><span data-stu-id="d12b0-178">Follow this format instead: `SensitiveType: "Credit Card Number|1..|80.."`</span></span> <br/> |
| `SensitiveType:"Credit Card Number|1..|80..101"` <br/> |<span data-ttu-id="d12b0-179">Omdat betrouwbaarheidswaarden een percentage vertegenwoordigen, kunnen ze niet groter zijn dan 100.</span><span class="sxs-lookup"><span data-stu-id="d12b0-179">Because confidence values represent a percentage, they can't exceed 100.</span></span> <span data-ttu-id="d12b0-180">Kies in plaats daarvan een getal van 1 tot en met 100.</span><span class="sxs-lookup"><span data-stu-id="d12b0-180">Choose a number from 1 through 100 instead.</span></span>  <br/> |
   
## <a name="for-more-information"></a><span data-ttu-id="d12b0-181">Voor meer informatie</span><span class="sxs-lookup"><span data-stu-id="d12b0-181">For more information</span></span>

- [<span data-ttu-id="d12b0-182">Definities van entiteiten van het type Gevoelige informatie</span><span class="sxs-lookup"><span data-stu-id="d12b0-182">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="d12b0-183">Een inhoudszoekactie uitvoeren</span><span class="sxs-lookup"><span data-stu-id="d12b0-183">Run a Content Search</span></span>](content-search.md)
- [<span data-ttu-id="d12b0-184">Trefwoordquery's en zoekvoorwaarden voor Zoeken naar inhoud</span><span class="sxs-lookup"><span data-stu-id="d12b0-184">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)