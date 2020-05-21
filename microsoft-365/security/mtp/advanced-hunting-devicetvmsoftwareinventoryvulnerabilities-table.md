---
title: Tabel DeviceTvmSoftwareInventoryVulnerabilities in het geavanceerde jachtschema
description: Meer informatie over de inventaris van software in uw apparaten en hun kwetsbaarheden in de tabel DeviceTvmSoftwareInventoryVulnerabilities van het geavanceerde jachtschema.
keywords: geavanceerde jacht, dreigingjacht, cyberdreigingsjacht, bescherming tegen microsoft-dreigingen, microsoft 365, mtp, m365, zoekopdracht, query, telemetrie, schemareferentie, kusto, tabel, kolom, gegevenstype, beschrijving, bedreiging & kwetsbaarheidsbeheer, TVM, apparaatbeheer, software, inventaris, kwetsbaarheden, CVE ID, OS DeviceTvmSoftwareInventoryVulnerabilities
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 0a7ac5a68bcdb12b3cdcd94cac8012c7807a6e2b
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/20/2020
ms.locfileid: "44327946"
---
# <a name="devicetvmsoftwareinventoryvulnerabilities"></a><span data-ttu-id="1cfda-104">DeviceTvmSoftwareInventoryVulnerabilities</span><span class="sxs-lookup"><span data-stu-id="1cfda-104">DeviceTvmSoftwareInventoryVulnerabilities</span></span>

<span data-ttu-id="1cfda-105">**Geldt voor:**</span><span class="sxs-lookup"><span data-stu-id="1cfda-105">**Applies to:**</span></span>
- <span data-ttu-id="1cfda-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="1cfda-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="1cfda-107">De `DeviceTvmSoftwareInventoryVulnerabilities` tabel in het geavanceerde jachtschema bevat de threat & Vulnerability [Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) inventaris van software op uw apparaten en eventuele bekende kwetsbaarheden in deze softwareproducten.</span><span class="sxs-lookup"><span data-stu-id="1cfda-107">The `DeviceTvmSoftwareInventoryVulnerabilities` table in the advanced hunting schema contains the [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) inventory of software on your devices as well as any known vulnerabilities in these software products.</span></span> <span data-ttu-id="1cfda-108">Deze tabel bevat ook informatie over het besturingssysteem, CVE-id's en informatie over de ernst van kwetsbaarheden.</span><span class="sxs-lookup"><span data-stu-id="1cfda-108">This table also includes operating system information, CVE IDs, and vulnerability severity information.</span></span> <span data-ttu-id="1cfda-109">Gebruik deze verwijzing om query's te construeren die informatie uit de tabel retourneren.</span><span class="sxs-lookup"><span data-stu-id="1cfda-109">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="1cfda-110">Voor informatie over andere tabellen in de geavanceerde jacht schema, zie [de geavanceerde jacht referentie](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="1cfda-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="1cfda-111">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="1cfda-111">Column name</span></span> | <span data-ttu-id="1cfda-112">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="1cfda-112">Data type</span></span> | <span data-ttu-id="1cfda-113">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="1cfda-113">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="1cfda-114">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="1cfda-114">string</span></span> | <span data-ttu-id="1cfda-115">Unieke id voor de machine in de service</span><span class="sxs-lookup"><span data-stu-id="1cfda-115">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="1cfda-116">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="1cfda-116">string</span></span> | <span data-ttu-id="1cfda-117">Volledig gekwalificeerde domeinnaam (FQDN) van de machine</span><span class="sxs-lookup"><span data-stu-id="1cfda-117">Fully qualified domain name (FQDN) of the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="1cfda-118">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="1cfda-118">string</span></span> | <span data-ttu-id="1cfda-119">Platform van het besturingssysteem dat op de machine draait.</span><span class="sxs-lookup"><span data-stu-id="1cfda-119">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="1cfda-120">Dit geeft specifieke besturingssystemen aan, waaronder variaties binnen dezelfde familie, zoals Windows 10 en Windows 7.</span><span class="sxs-lookup"><span data-stu-id="1cfda-120">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="1cfda-121">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="1cfda-121">string</span></span> | <span data-ttu-id="1cfda-122">Versie van het besturingssysteem die op de machine draait</span><span class="sxs-lookup"><span data-stu-id="1cfda-122">Version of the operating system running on the machine</span></span> |
| `OSArchitecture` | <span data-ttu-id="1cfda-123">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="1cfda-123">string</span></span> | <span data-ttu-id="1cfda-124">Architectuur van het besturingssysteem dat op de machine draait</span><span class="sxs-lookup"><span data-stu-id="1cfda-124">Architecture of the operating system running on the machine</span></span> |
| `SoftwareVendor` | <span data-ttu-id="1cfda-125">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="1cfda-125">string</span></span> | <span data-ttu-id="1cfda-126">Naam van de softwareleverancier</span><span class="sxs-lookup"><span data-stu-id="1cfda-126">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="1cfda-127">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="1cfda-127">string</span></span> | <span data-ttu-id="1cfda-128">Naam van het softwareproduct</span><span class="sxs-lookup"><span data-stu-id="1cfda-128">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="1cfda-129">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="1cfda-129">string</span></span> | <span data-ttu-id="1cfda-130">Versienummer van het softwareproduct</span><span class="sxs-lookup"><span data-stu-id="1cfda-130">Version number of the software product</span></span> |
| `CveId` | <span data-ttu-id="1cfda-131">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="1cfda-131">string</span></span> | <span data-ttu-id="1cfda-132">Unieke id die is toegewezen aan het beveiligingslek onder het CVE-systeem (Common Vulnerabilities and Exposures)</span><span class="sxs-lookup"><span data-stu-id="1cfda-132">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="1cfda-133">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="1cfda-133">string</span></span> | <span data-ttu-id="1cfda-134">Ernstniveau toegewezen aan het beveiligingslek op basis van de CVSS-score en dynamische factoren die worden beïnvloed door het dreigingslandschap</span><span class="sxs-lookup"><span data-stu-id="1cfda-134">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |



## <a name="related-topics"></a><span data-ttu-id="1cfda-135">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="1cfda-135">Related topics</span></span>

- [<span data-ttu-id="1cfda-136">Proactief op zoek naar bedreigingen</span><span class="sxs-lookup"><span data-stu-id="1cfda-136">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="1cfda-137">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="1cfda-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="1cfda-138">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="1cfda-138">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="1cfda-139">Zoek naar bedreigingen op verschillende apparaten en e-mails</span><span class="sxs-lookup"><span data-stu-id="1cfda-139">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="1cfda-140">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="1cfda-140">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="1cfda-141">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="1cfda-141">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="1cfda-142">Overzicht van Threat & Vulnerability Management</span><span class="sxs-lookup"><span data-stu-id="1cfda-142">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)