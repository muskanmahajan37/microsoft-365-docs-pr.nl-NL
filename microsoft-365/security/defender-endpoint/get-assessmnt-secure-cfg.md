---
title: Veilige configuratiebeoordeling per apparaat exporteren
description: Retourneert een vermelding voor elke unieke combinatie van DeviceId, ConfigurationId.
keywords: api's, api's, exportbeoordeling, per apparaat, rapport over kwetsbaarheidsbeoordeling, beoordeling van kwetsbaarheid van apparaten, rapport over apparaatproblemen, beveiligingsprobleemrapport, secure configuration report, software vulnerabilities assessment, software vulnerability report, vulnerability report by machine,
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.custom: api
ms.openlocfilehash: f2e20415cb64903e8dfe2c82646c1970036b8f6b
ms.sourcegitcommit: 727a75b604d5ff5946a0854662ad5a8b049f2874
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/25/2021
ms.locfileid: "52653629"
---
# <a name="export-secure-configuration-assessment-per-device"></a><span data-ttu-id="2149e-104">Veilige configuratiebeoordeling per apparaat exporteren</span><span class="sxs-lookup"><span data-stu-id="2149e-104">Export secure configuration assessment per device</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2149e-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="2149e-105">**Applies to:**</span></span>

- [<span data-ttu-id="2149e-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="2149e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2149e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2149e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="2149e-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="2149e-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2149e-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="2149e-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]
>
>
<span data-ttu-id="2149e-110">Retourneert alle configuraties en hun status, per apparaat.</span><span class="sxs-lookup"><span data-stu-id="2149e-110">Returns all of the configurations and their status, on a per-device basis.</span></span>

<span data-ttu-id="2149e-111">Er zijn verschillende API-oproepen om verschillende typen gegevens op te halen.</span><span class="sxs-lookup"><span data-stu-id="2149e-111">There are different API calls to get different types of data.</span></span> <span data-ttu-id="2149e-112">Omdat de hoeveelheid gegevens erg groot kan zijn, kunnen deze op twee manieren worden opgehaald:</span><span class="sxs-lookup"><span data-stu-id="2149e-112">Because the amount of data can be very large, there are two ways it can be retrieved:</span></span>

- <span data-ttu-id="2149e-113">**OData**  De API haalt alle gegevens in uw organisatie op als Json-antwoorden, volgens het OData-protocol.</span><span class="sxs-lookup"><span data-stu-id="2149e-113">**OData**  The API pulls all data in your organization as Json responses, following the OData protocol.</span></span> <span data-ttu-id="2149e-114">Deze methode is het beste voor _kleine organisaties met minder dan 100.000 apparaten._</span><span class="sxs-lookup"><span data-stu-id="2149e-114">This method is best for _small organizations with less than 100K devices_.</span></span> <span data-ttu-id="2149e-115">Het antwoord is paginated, zodat u het veld odata.nextLink uit het antwoord kunt gebruiken \@ om de volgende resultaten op te halen.</span><span class="sxs-lookup"><span data-stu-id="2149e-115">The response is paginated, so you can use the \@odata.nextLink field from the response to fetch the next results.</span></span>

- <span data-ttu-id="2149e-116">**via bestanden** Met deze API-oplossing kunt u sneller en betrouwbaarder grotere hoeveelheden gegevens verzamelen.</span><span class="sxs-lookup"><span data-stu-id="2149e-116">**via files** This API solution enables pulling larger amounts of data faster and more reliably.</span></span> <span data-ttu-id="2149e-117">Daarom wordt het aanbevolen voor grote organisaties, met meer dan 100.000 apparaten.</span><span class="sxs-lookup"><span data-stu-id="2149e-117">Therefore, it is recommended for large organizations, with more than 100K devices.</span></span> <span data-ttu-id="2149e-118">Met deze API worden alle gegevens in uw organisatie als downloadbestanden opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="2149e-118">This API pulls all data in your organization as download files.</span></span> <span data-ttu-id="2149e-119">Het antwoord bevat URL's om alle gegevens uit de Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="2149e-119">The response contains URLs to download all the data from Azure Storage.</span></span> <span data-ttu-id="2149e-120">Met deze API kunt u al uw gegevens als volgt Azure Storage downloaden:</span><span class="sxs-lookup"><span data-stu-id="2149e-120">This API enables you to download all your data from Azure Storage as follows:</span></span>

  - <span data-ttu-id="2149e-121">Bel de API om een lijst met url's te downloaden met al uw organisatiegegevens.</span><span class="sxs-lookup"><span data-stu-id="2149e-121">Call the API to get a list of download URLs with all your organization data.</span></span>

  - <span data-ttu-id="2149e-122">Download alle bestanden met de download-URL's en verwerkt de gegevens naar eigen goed gebruik.</span><span class="sxs-lookup"><span data-stu-id="2149e-122">Download all the files using the download URLs and process the data as you like.</span></span>

<span data-ttu-id="2149e-123">De gegevens die worden verzameld (voor _OData_ of _via_ bestanden) zijn de huidige momentopname van de huidige status en bevatten geen historische gegevens.</span><span class="sxs-lookup"><span data-stu-id="2149e-123">The data that is collected (for either _OData_ or _via files_) is the current snapshot of the current state, and does not contain historic data.</span></span> <span data-ttu-id="2149e-124">Om historische gegevens te verzamelen, moeten klanten de gegevens opslaan in hun eigen gegevensopslag.</span><span class="sxs-lookup"><span data-stu-id="2149e-124">In order to collect historic data, customers must save the data in their own data storages.</span></span>

<span data-ttu-id="2149e-125">Tenzij anders aangegeven, zijn alle vermelde exportbeoordelingsmethoden volledig **_geëxporteerd_** en **_per apparaat_** (ook wel per **_apparaat genoemd)._**</span><span class="sxs-lookup"><span data-stu-id="2149e-125">Unless indicated otherwise, all export assessment methods listed are **_full export_** and **_by device_** (also referred to as **_per device_**).</span></span>

## <a name="1-export-secure-configuration-assessment-odata"></a><span data-ttu-id="2149e-126">1. Beveiligde configuratiebeoordeling exporteren (OData)</span><span class="sxs-lookup"><span data-stu-id="2149e-126">1. Export secure configuration assessment (OData)</span></span>

### <a name="11-api-method-description"></a><span data-ttu-id="2149e-127">Beschrijving van API-methode 1.1</span><span class="sxs-lookup"><span data-stu-id="2149e-127">1.1 API method description</span></span>

<span data-ttu-id="2149e-128">Deze API-reactie bevat de Secure Configuration Assessment op uw blootgestelde apparaten en retourneert een vermelding voor elke unieke combinatie van DeviceId, ConfigurationId.</span><span class="sxs-lookup"><span data-stu-id="2149e-128">This API response contains the Secure Configuration Assessment on your exposed devices, and returns an entry for every unique combination of DeviceId, ConfigurationId.</span></span>

#### <a name="111-limitations"></a><span data-ttu-id="2149e-129">1.1.1 Beperkingen</span><span class="sxs-lookup"><span data-stu-id="2149e-129">1.1.1 Limitations</span></span>

- <span data-ttu-id="2149e-130">De maximale paginagrootte is 200.000.</span><span class="sxs-lookup"><span data-stu-id="2149e-130">Maximum page size is 200,000.</span></span>

- <span data-ttu-id="2149e-131">Tariefbeperkingen voor deze API zijn 30 oproepen per minuut en 1000 oproepen per uur.</span><span class="sxs-lookup"><span data-stu-id="2149e-131">Rate limitations for this API are 30 calls per minute and 1000 calls per hour.</span></span>

### <a name="12-permissions"></a><span data-ttu-id="2149e-132">1.2 Machtigingen</span><span class="sxs-lookup"><span data-stu-id="2149e-132">1.2 Permissions</span></span>

<span data-ttu-id="2149e-133">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="2149e-133">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="2149e-134">Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.</span><span class="sxs-lookup"><span data-stu-id="2149e-134">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="2149e-135">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="2149e-135">Permission type</span></span> | <span data-ttu-id="2149e-136">Machtiging</span><span class="sxs-lookup"><span data-stu-id="2149e-136">Permission</span></span> | <span data-ttu-id="2149e-137">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="2149e-137">Permission display name</span></span>
---|---|---
<span data-ttu-id="2149e-138">Toepassing</span><span class="sxs-lookup"><span data-stu-id="2149e-138">Application</span></span> | <span data-ttu-id="2149e-139">Kwetsbaarheid.Read.All</span><span class="sxs-lookup"><span data-stu-id="2149e-139">Vulnerability.Read.All</span></span> | <span data-ttu-id="2149e-140">\'Informatie over kwetsbaarheidsbeheer en bedreigingsbeheer lezen\'</span><span class="sxs-lookup"><span data-stu-id="2149e-140">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="2149e-141">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="2149e-141">Delegated (work or school account)</span></span> | <span data-ttu-id="2149e-142">Kwetsbaarheid.Lezen</span><span class="sxs-lookup"><span data-stu-id="2149e-142">Vulnerability.Read</span></span> | <span data-ttu-id="2149e-143">\'Informatie over kwetsbaarheidsbeheer en bedreigingsbeheer lezen\'</span><span class="sxs-lookup"><span data-stu-id="2149e-143">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="13-url"></a><span data-ttu-id="2149e-144">1,3 URL</span><span class="sxs-lookup"><span data-stu-id="2149e-144">1.3 URL</span></span>

```http
GET /api/machines/SecureConfigurationsAssessmentByMachine
```

### <a name="14-parameters"></a><span data-ttu-id="2149e-145">1,4 Parameters</span><span class="sxs-lookup"><span data-stu-id="2149e-145">1.4 Parameters</span></span>

- <span data-ttu-id="2149e-146">pageSize \( default = 50.000 \) – aantal resultaten in antwoord</span><span class="sxs-lookup"><span data-stu-id="2149e-146">pageSize \(default = 50,000\) – number of results in response</span></span>

- <span data-ttu-id="2149e-147">\$boven: het aantal resultaten dat moet worden retourneren, geeft \( geen odata.nextLink als resultaat en haalt daarom niet alle \@ gegevens op\)</span><span class="sxs-lookup"><span data-stu-id="2149e-147">\$top – number of results to return \(doesn’t return \@odata.nextLink and therefore doesn’t pull all the data\)</span></span>

### <a name="15-properties"></a><span data-ttu-id="2149e-148">1,5 eigenschappen</span><span class="sxs-lookup"><span data-stu-id="2149e-148">1.5 Properties</span></span>

>[!Note]
>
>- <span data-ttu-id="2149e-149">De eigenschappen die in de volgende tabel zijn gedefinieerd, worden alfanumeriek weergegeven op eigenschap-id.</span><span class="sxs-lookup"><span data-stu-id="2149e-149">The properties defined in the following table are listed alphanumerically, by property ID.</span></span>  <span data-ttu-id="2149e-150">Bij het uitvoeren van deze API wordt de resulterende uitvoer niet noodzakelijkerwijs geretourneerd in dezelfde volgorde die in deze tabellen wordt vermeld.</span><span class="sxs-lookup"><span data-stu-id="2149e-150">When running this API, the resulting output will not necessarily be returned in the same order listed in these tables.</span></span>
>
>- <span data-ttu-id="2149e-151">Sommige extra kolommen kunnen worden geretourneerd in het antwoord.</span><span class="sxs-lookup"><span data-stu-id="2149e-151">Some additional columns might be returned in the response.</span></span> <span data-ttu-id="2149e-152">Deze kolommen zijn tijdelijk en kunnen worden verwijderd, gebruik alleen de gedocumenteerde kolommen.</span><span class="sxs-lookup"><span data-stu-id="2149e-152">These columns are temporary and might be removed, please use only the documented columns.</span></span>
>

<span data-ttu-id="2149e-153">Eigenschap (id)</span><span class="sxs-lookup"><span data-stu-id="2149e-153">Property (id)</span></span> | <span data-ttu-id="2149e-154">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="2149e-154">Data type</span></span> | <span data-ttu-id="2149e-155">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="2149e-155">Description</span></span> | <span data-ttu-id="2149e-156">Voorbeeld van een geretourneerde waarde</span><span class="sxs-lookup"><span data-stu-id="2149e-156">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="2149e-157">ConfigurationCategory</span><span class="sxs-lookup"><span data-stu-id="2149e-157">ConfigurationCategory</span></span> | <span data-ttu-id="2149e-158">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2149e-158">string</span></span> | <span data-ttu-id="2149e-159">Categorie of groepering waarvan de configuratie deel uitmaken: Toepassing, BE, Netwerk, Accounts, Beveiligingsbesturingselementen</span><span class="sxs-lookup"><span data-stu-id="2149e-159">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span> | <span data-ttu-id="2149e-160">Beveiligingsbesturingselementen</span><span class="sxs-lookup"><span data-stu-id="2149e-160">Security controls</span></span>
<span data-ttu-id="2149e-161">ConfigurationId</span><span class="sxs-lookup"><span data-stu-id="2149e-161">ConfigurationId</span></span> | <span data-ttu-id="2149e-162">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2149e-162">string</span></span> | <span data-ttu-id="2149e-163">Unieke id voor een specifieke configuratie</span><span class="sxs-lookup"><span data-stu-id="2149e-163">Unique identifier for a specific configuration</span></span> | <span data-ttu-id="2149e-164">scid-10000</span><span class="sxs-lookup"><span data-stu-id="2149e-164">scid-10000</span></span>
<span data-ttu-id="2149e-165">ConfigurationImpact</span><span class="sxs-lookup"><span data-stu-id="2149e-165">ConfigurationImpact</span></span> | <span data-ttu-id="2149e-166">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2149e-166">string</span></span> | <span data-ttu-id="2149e-167">Beoordeelde invloed van de configuratie op de algemene configuratiescore (1-10)</span><span class="sxs-lookup"><span data-stu-id="2149e-167">Rated impact of the configuration to the overall configuration score (1-10)</span></span> | <span data-ttu-id="2149e-168">9</span><span class="sxs-lookup"><span data-stu-id="2149e-168">9</span></span>
<span data-ttu-id="2149e-169">ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="2149e-169">ConfigurationName</span></span> | <span data-ttu-id="2149e-170">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2149e-170">string</span></span> | <span data-ttu-id="2149e-171">Weergavenaam van de configuratie</span><span class="sxs-lookup"><span data-stu-id="2149e-171">Display name of the configuration</span></span> | <span data-ttu-id="2149e-172">Onboarden apparaten naar Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="2149e-172">Onboard devices to Microsoft Defender for Endpoint</span></span>
<span data-ttu-id="2149e-173">ConfigurationSubcategory</span><span class="sxs-lookup"><span data-stu-id="2149e-173">ConfigurationSubcategory</span></span> | <span data-ttu-id="2149e-174">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2149e-174">string</span></span> | <span data-ttu-id="2149e-175">Subcategorie of subgroepering waarvan de configuratie deel uitmaken.</span><span class="sxs-lookup"><span data-stu-id="2149e-175">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="2149e-176">In veel gevallen worden hier specifieke mogelijkheden of functies beschreven.</span><span class="sxs-lookup"><span data-stu-id="2149e-176">In many cases, this describes specific capabilities or features.</span></span> | <span data-ttu-id="2149e-177">Onboard-apparaten</span><span class="sxs-lookup"><span data-stu-id="2149e-177">Onboard Devices</span></span>
<span data-ttu-id="2149e-178">DeviceId</span><span class="sxs-lookup"><span data-stu-id="2149e-178">DeviceId</span></span> | <span data-ttu-id="2149e-179">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2149e-179">string</span></span> | <span data-ttu-id="2149e-180">Unieke id voor het apparaat in de service.</span><span class="sxs-lookup"><span data-stu-id="2149e-180">Unique identifier for the device in the service.</span></span> | <span data-ttu-id="2149e-181">9eaf3a8b5962e0e6b1af9ec75664a9b823df2d1</span><span class="sxs-lookup"><span data-stu-id="2149e-181">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span></span>
<span data-ttu-id="2149e-182">Apparaatnaam</span><span class="sxs-lookup"><span data-stu-id="2149e-182">DeviceName</span></span> | <span data-ttu-id="2149e-183">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2149e-183">string</span></span> | <span data-ttu-id="2149e-184">Volledig gekwalificeerde domeinnaam (FQDN) van het apparaat.</span><span class="sxs-lookup"><span data-stu-id="2149e-184">Fully qualified domain name (FQDN) of the device.</span></span> | <span data-ttu-id="2149e-185">johnlaptop.europe.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2149e-185">johnlaptop.europe.contoso.com</span></span>
<span data-ttu-id="2149e-186">IsApplicable</span><span class="sxs-lookup"><span data-stu-id="2149e-186">IsApplicable</span></span> | <span data-ttu-id="2149e-187">bool</span><span class="sxs-lookup"><span data-stu-id="2149e-187">bool</span></span> | <span data-ttu-id="2149e-188">Geeft aan of de configuratie of het beleid van toepassing is</span><span class="sxs-lookup"><span data-stu-id="2149e-188">Indicates whether the configuration or policy is applicable</span></span> | <span data-ttu-id="2149e-189">waar</span><span class="sxs-lookup"><span data-stu-id="2149e-189">true</span></span>
<span data-ttu-id="2149e-190">IsCompliant</span><span class="sxs-lookup"><span data-stu-id="2149e-190">IsCompliant</span></span> | <span data-ttu-id="2149e-191">bool</span><span class="sxs-lookup"><span data-stu-id="2149e-191">bool</span></span> | <span data-ttu-id="2149e-192">Geeft aan of de configuratie of het beleid juist is geconfigureerd</span><span class="sxs-lookup"><span data-stu-id="2149e-192">Indicates whether the configuration or policy is properly configured</span></span> | <span data-ttu-id="2149e-193">onwaar</span><span class="sxs-lookup"><span data-stu-id="2149e-193">false</span></span>
<span data-ttu-id="2149e-194">IsExpectedUserImpact</span><span class="sxs-lookup"><span data-stu-id="2149e-194">IsExpectedUserImpact</span></span> | <span data-ttu-id="2149e-195">bool</span><span class="sxs-lookup"><span data-stu-id="2149e-195">bool</span></span> | <span data-ttu-id="2149e-196">Geeft aan of er gevolgen voor de gebruiker zijn als de configuratie wordt toegepast</span><span class="sxs-lookup"><span data-stu-id="2149e-196">Indicates whether there will be user impact if the configuration will be applied</span></span> | <span data-ttu-id="2149e-197">waar</span><span class="sxs-lookup"><span data-stu-id="2149e-197">true</span></span>
<span data-ttu-id="2149e-198">OSPlatform</span><span class="sxs-lookup"><span data-stu-id="2149e-198">OSPlatform</span></span> | <span data-ttu-id="2149e-199">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2149e-199">string</span></span> | <span data-ttu-id="2149e-200">Platform van het besturingssysteem dat op het apparaat wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="2149e-200">Platform of the operating system running on the device.</span></span> <span data-ttu-id="2149e-201">Dit geeft specifieke besturingssystemen aan, waaronder variaties binnen dezelfde familie, zoals Windows 10 en Windows 7.</span><span class="sxs-lookup"><span data-stu-id="2149e-201">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> <span data-ttu-id="2149e-202">Zie ondersteunde besturingssystemen en platforms van tvm voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="2149e-202">See tvm supported operating systems and platforms for details.</span></span> | <span data-ttu-id="2149e-203">Windows10</span><span class="sxs-lookup"><span data-stu-id="2149e-203">Windows10</span></span>
<span data-ttu-id="2149e-204">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="2149e-204">RbacGroupName</span></span> | <span data-ttu-id="2149e-205">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2149e-205">string</span></span> | <span data-ttu-id="2149e-206">De groep Toegangsbeheer (RBAC) op basis van rollen.</span><span class="sxs-lookup"><span data-stu-id="2149e-206">The role-based access control (RBAC) group.</span></span> <span data-ttu-id="2149e-207">Als dit apparaat niet is toegewezen aan een RBAC-groep, is de waarde 'Niet toegewezen'.</span><span class="sxs-lookup"><span data-stu-id="2149e-207">If this device is not assigned to any RBAC group, the value will be “Unassigned.”</span></span> <span data-ttu-id="2149e-208">Als de organisatie geen RBAC-groepen bevat, is de waarde 'Geen'.</span><span class="sxs-lookup"><span data-stu-id="2149e-208">If the organization doesn’t contain any RBAC groups, the value will be “None.”</span></span> | <span data-ttu-id="2149e-209">Servers</span><span class="sxs-lookup"><span data-stu-id="2149e-209">Servers</span></span>
<span data-ttu-id="2149e-210">RecommendationReference</span><span class="sxs-lookup"><span data-stu-id="2149e-210">RecommendationReference</span></span> | <span data-ttu-id="2149e-211">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2149e-211">string</span></span> | <span data-ttu-id="2149e-212">Een verwijzing naar de aanbevelings-id met betrekking tot deze software.</span><span class="sxs-lookup"><span data-stu-id="2149e-212">A reference to the recommendation ID related to this software.</span></span> | <span data-ttu-id="2149e-213">sca-_-scid-20000</span><span class="sxs-lookup"><span data-stu-id="2149e-213">sca-_-scid-20000</span></span>
<span data-ttu-id="2149e-214">Tijdstempel</span><span class="sxs-lookup"><span data-stu-id="2149e-214">Timestamp</span></span> | <span data-ttu-id="2149e-215">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2149e-215">string</span></span> | <span data-ttu-id="2149e-216">De laatste keer dat de configuratie op het apparaat is gezien</span><span class="sxs-lookup"><span data-stu-id="2149e-216">Last time the configuration was seen on the device</span></span> | <span data-ttu-id="2149e-217">2020-11-03 10:13:34.8476880</span><span class="sxs-lookup"><span data-stu-id="2149e-217">2020-11-03 10:13:34.8476880</span></span>

### <a name="16-examples"></a><span data-ttu-id="2149e-218">1.6 Voorbeelden</span><span class="sxs-lookup"><span data-stu-id="2149e-218">1.6 Examples</span></span>

#### <a name="161-request-example"></a><span data-ttu-id="2149e-219">1.6.1 Voorbeeld van aanvraag</span><span class="sxs-lookup"><span data-stu-id="2149e-219">1.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SecureConfigurationsAssessmentByMachine?pageSize=5 
```

#### <a name="162-response-example"></a><span data-ttu-id="2149e-220">1.6.2 Voorbeeld van antwoord</span><span class="sxs-lookup"><span data-stu-id="2149e-220">1.6.2 Response example</span></span>

```json
{
    "@odata.context": "api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.AssetConfiguration)",
    "value": [
        {
            "deviceId": "00013ee62c6b12345b10214e1801b217b50ab455c293d",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_5d96860d69c73fdd06fc8d1679e1eb73eceb8330",
            "osPlatform": "Windows10",
            "osVersion": "NT kernel 6.x",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-10000",
            "configurationCategory": "Network",
            "configurationSubcategory": "",
            "configurationImpact": 5,
            "isCompliant": true,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Disable insecure administration protocol – Telnet",
            "recommendationReference": "sca-_-scid-10000"
        },
        {
            "deviceId": "0002a1be533813b9a8c6de739785365bce7910",
            "rbacGroupName": "hhh",
            "deviceName": null,
            "osPlatform": "Windows10",
            "osVersion": "10.0",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-20000",
            "configurationCategory": "Security controls",
            "configurationSubcategory": "Onboard Devices",
            "configurationImpact": 9,
            "isCompliant": false,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Onboard devices to Microsoft Defender for Endpoint",
            "recommendationReference": "sca-_-scid-20000"
        },
        {
            "deviceId": "0002a1de123456a8c06de736785395d4ce7610",
            "rbacGroupName": "hhh",
            "deviceName": null,
            "osPlatform": "Windows10",
            "osVersion": "10.0",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-10000",
            "configurationCategory": "Network",
            "configurationSubcategory": "",
            "configurationImpact": 5,
            "isCompliant": true,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Disable insecure administration protocol – Telnet",
            "recommendationReference": "sca-_-scid-10000"
        },
        {
            "deviceId": "00044f912345bdaf756492dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663d45912eed224b2be2f5ea3142726e63f16a.DomainPII_21eeb80b086e76bdfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-39",
            "configurationCategory": "OS",
            "configurationSubcategory": "",
            "configurationImpact": 5,
            "isCompliant": true,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Enable 'Domain member: Digitally sign secure channel data (when possible)'",
            "recommendationReference": "sca-_-scid-39"
        },
        {
            "deviceId": "00044f912345daf759462bde6bd733d6a9c56ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45612eeb224d2de2f5ea3142726e63f16a.DomainPII_21eed80d086e76dbfa178eadfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-6093",
            "configurationCategory": "Security controls",
            "configurationSubcategory": "Antivirus",
            "configurationImpact": 5,
            "isCompliant": false,
            "isApplicable": false,
            "isExpectedUserImpact": false,
            "configurationName": "Enable Microsoft Defender Antivirus real-time behavior monitoring for Linux",
            "recommendationReference": "sca-_-scid-6093"
        }
    ],
    "@odata.nextLink": "https://api.securitycenter.microsoft.com/api/machines/SecureConfigurationsAssessmentByMachine?pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0xMS8xMTAxLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9"
}
```

## <a name="2-export-secure-configuration-assessment-via-files"></a><span data-ttu-id="2149e-221">2. Beveiligde configuratiebeoordeling exporteren (via bestanden)</span><span class="sxs-lookup"><span data-stu-id="2149e-221">2. Export secure configuration assessment (via files)</span></span>

### <a name="21-api-method-description"></a><span data-ttu-id="2149e-222">Beschrijving van API-methode 2.1</span><span class="sxs-lookup"><span data-stu-id="2149e-222">2.1 API method description</span></span>

<span data-ttu-id="2149e-223">Deze API-reactie bevat de Secure Configuration Assessment op uw blootgestelde apparaten en retourneert een vermelding voor elke unieke combinatie van DeviceId, ConfigurationId.</span><span class="sxs-lookup"><span data-stu-id="2149e-223">This API response contains the Secure Configuration Assessment on your exposed devices, and returns an entry for every unique combination of DeviceId, ConfigurationId.</span></span>

#### <a name="212-limitations"></a><span data-ttu-id="2149e-224">2.1.2 Beperkingen</span><span class="sxs-lookup"><span data-stu-id="2149e-224">2.1.2 Limitations</span></span>

<span data-ttu-id="2149e-225">Tariefbeperkingen voor deze API zijn 5 oproepen per minuut en 20 oproepen per uur.</span><span class="sxs-lookup"><span data-stu-id="2149e-225">Rate limitations for this API are 5 calls per minute and 20 calls per hour.</span></span>

### <a name="22-permissions"></a><span data-ttu-id="2149e-226">2.2 Machtigingen</span><span class="sxs-lookup"><span data-stu-id="2149e-226">2.2 Permissions</span></span>

<span data-ttu-id="2149e-227">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="2149e-227">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="2149e-228">Zie Microsoft Defender voor eindpunt-API's gebruiken voor meer informatie, inclusief het kiezen van [machtigingen.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="2149e-228">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="2149e-229">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="2149e-229">Permission type</span></span> | <span data-ttu-id="2149e-230">Machtiging</span><span class="sxs-lookup"><span data-stu-id="2149e-230">Permission</span></span> | <span data-ttu-id="2149e-231">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="2149e-231">Permission display name</span></span>
---|---|---
<span data-ttu-id="2149e-232">Toepassing</span><span class="sxs-lookup"><span data-stu-id="2149e-232">Application</span></span> | <span data-ttu-id="2149e-233">Kwetsbaarheid.Read.All</span><span class="sxs-lookup"><span data-stu-id="2149e-233">Vulnerability.Read.All</span></span> | <span data-ttu-id="2149e-234">\'Informatie over Threat and Vulnerability Management kwetsbaarheid lezen\'</span><span class="sxs-lookup"><span data-stu-id="2149e-234">\'Read "threat and vulnerability management" vulnerability information\'</span></span>
<span data-ttu-id="2149e-235">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="2149e-235">Delegated (work or school account)</span></span> | <span data-ttu-id="2149e-236">Kwetsbaarheid.Lezen</span><span class="sxs-lookup"><span data-stu-id="2149e-236">Vulnerability.Read</span></span> | <span data-ttu-id="2149e-237">\'Informatie over Threat and Vulnerability Management kwetsbaarheid lezen\'</span><span class="sxs-lookup"><span data-stu-id="2149e-237">\'Read "threat and vulnerability management" vulnerability information\'</span></span>

### <a name="23-url"></a><span data-ttu-id="2149e-238">2.3 URL</span><span class="sxs-lookup"><span data-stu-id="2149e-238">2.3 URL</span></span>

```http
GET /api/machines/SecureConfigurationsAssessmentExport
```

### <a name="parameters"></a><span data-ttu-id="2149e-239">Parameters</span><span class="sxs-lookup"><span data-stu-id="2149e-239">Parameters</span></span>

- <span data-ttu-id="2149e-240">sasValidHours: het aantal uren dat de download-URL's geldig zijn (maximaal 24 uur).</span><span class="sxs-lookup"><span data-stu-id="2149e-240">sasValidHours – The number of hours that the download URLs will be valid for (Maximum 24 hours).</span></span>

### <a name="25-properties"></a><span data-ttu-id="2149e-241">2,5 eigenschappen</span><span class="sxs-lookup"><span data-stu-id="2149e-241">2.5 Properties</span></span>

>[!Note]
>
>- <span data-ttu-id="2149e-242">De bestanden zijn gzip gecomprimeerde & in de Json-indeling met meerdere lijnen.</span><span class="sxs-lookup"><span data-stu-id="2149e-242">The files are gzip compressed & in multiline Json format.</span></span>
>
>- <span data-ttu-id="2149e-243">De DOWNLOAD-URL's zijn slechts 3 uur geldig. anders kunt u de parameter gebruiken.</span><span class="sxs-lookup"><span data-stu-id="2149e-243">The download URLs are only valid for 3 hours; otherwise you can use the parameter.</span></span>
>
>- <span data-ttu-id="2149e-244">Voor maximale downloadsnelheid van uw gegevens kunt u ervoor zorgen dat u downloadt vanuit dezelfde Azure-regio waarin uw gegevens zich bevinden.</span><span class="sxs-lookup"><span data-stu-id="2149e-244">For maximum download speed of your data, you can make sure you are downloading from the same Azure region in which your data resides.</span></span>
>
<span data-ttu-id="2149e-245">Eigenschap (id)</span><span class="sxs-lookup"><span data-stu-id="2149e-245">Property (id)</span></span> | <span data-ttu-id="2149e-246">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="2149e-246">Data type</span></span> | <span data-ttu-id="2149e-247">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="2149e-247">Description</span></span> | <span data-ttu-id="2149e-248">Voorbeeld van een geretourneerde waarde</span><span class="sxs-lookup"><span data-stu-id="2149e-248">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="2149e-249">Bestanden exporteren</span><span class="sxs-lookup"><span data-stu-id="2149e-249">Export files</span></span> | <span data-ttu-id="2149e-250">\[matrixreeks\]</span><span class="sxs-lookup"><span data-stu-id="2149e-250">array\[string\]</span></span> | <span data-ttu-id="2149e-251">Een lijst met DOWNLOAD-URL's voor bestanden met de huidige momentopname van de organisatie</span><span class="sxs-lookup"><span data-stu-id="2149e-251">A list of download URLs for files holding the current snapshot of the organization</span></span> | <span data-ttu-id="2149e-252">[  Https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2” ]</span><span class="sxs-lookup"><span data-stu-id="2149e-252">[  Https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2” ]</span></span>
<span data-ttu-id="2149e-253">GeneratedTime</span><span class="sxs-lookup"><span data-stu-id="2149e-253">GeneratedTime</span></span> | <span data-ttu-id="2149e-254">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2149e-254">string</span></span> | <span data-ttu-id="2149e-255">De tijd dat de export is gegenereerd.</span><span class="sxs-lookup"><span data-stu-id="2149e-255">The time that the export was generated.</span></span> | <span data-ttu-id="2149e-256">2021-05-20T08:00:00Z ]</span><span class="sxs-lookup"><span data-stu-id="2149e-256">2021-05-20T08:00:00Z  ]</span></span>

### <a name="26-examples"></a><span data-ttu-id="2149e-257">2.6 Voorbeelden</span><span class="sxs-lookup"><span data-stu-id="2149e-257">2.6 Examples</span></span>

#### <a name="261-request-example"></a><span data-ttu-id="2149e-258">2.6.1 Voorbeeld van aanvraag</span><span class="sxs-lookup"><span data-stu-id="2149e-258">2.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SecureConfigurationsAssessmentExport
```

#### <a name="262-response-example"></a><span data-ttu-id="2149e-259">2.6.2 Voorbeeld van antwoord</span><span class="sxs-lookup"><span data-stu-id="2149e-259">2.6.2 Response example</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#contoso.windowsDefenderATP.api.ExportFilesResponse",
    "exportFiles": [
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/ScaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/ScaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/ScaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c001.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=..."
    ],
    "generatedTime": "2021-01-11T11:01:00Z"
}
```

## <a name="see-also"></a><span data-ttu-id="2149e-260">Zie ook</span><span class="sxs-lookup"><span data-stu-id="2149e-260">See also</span></span>

- [<span data-ttu-id="2149e-261">Beoordelingsmethoden en -eigenschappen per apparaat exporteren</span><span class="sxs-lookup"><span data-stu-id="2149e-261">Export assessment methods and properties per device</span></span>](get-assessmnt-1methods-properties.md)

- [<span data-ttu-id="2149e-262">Beoordeling van de softwarevoorraad per apparaat exporteren</span><span class="sxs-lookup"><span data-stu-id="2149e-262">Export software inventory assessment per device</span></span>](get-assessmnt-software-inventory.md)

- [<span data-ttu-id="2149e-263">Beoordeling van beveiligingsproblemen met software per apparaat exporteren</span><span class="sxs-lookup"><span data-stu-id="2149e-263">Export software vulnerabilities assessment per device</span></span>](get-assessmnt-software-vulnerabilities.md)

<span data-ttu-id="2149e-264">Andere gerelateerde</span><span class="sxs-lookup"><span data-stu-id="2149e-264">Other related</span></span>

- [<span data-ttu-id="2149e-265">Risicogebaseerd & vulnerability management</span><span class="sxs-lookup"><span data-stu-id="2149e-265">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="2149e-266">Beveiligingslekken in uw organisatie</span><span class="sxs-lookup"><span data-stu-id="2149e-266">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)