---
title: Beoordelingsmethoden en -eigenschappen per apparaat exporteren
description: Hier vindt u informatie over de API's die 'Threat and Vulnerability Management' halen. Er zijn verschillende API-oproepen om verschillende typen gegevens op te halen. Over het algemeen bevat elke API-oproep de vereiste gegevens voor apparaten in uw organisatie. Aangezien de hoeveelheid gegevens erg groot kan zijn, kunnen deze op twee manieren worden opgehaald
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
ms.openlocfilehash: 851c792265375e5905c0c427bfc77a2366bc962d
ms.sourcegitcommit: 727a75b604d5ff5946a0854662ad5a8b049f2874
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/25/2021
ms.locfileid: "52653634"
---
# <a name="export-assessment-methods-and-properties-per-device"></a>Beoordelingsmethoden en -eigenschappen per apparaat exporteren

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="api-description"></a>API-beschrijving

Hier vindt u methoden en eigenschapsgegevens over de API's die Threat and Vulnerability Management per apparaat verzamelen. Er zijn verschillende API-oproepen om verschillende typen gegevens op te halen. Over het algemeen bevat elke API-oproep de vereiste gegevens voor apparaten in uw organisatie.

> [!Note]
>
> Tenzij anders aangegeven, zijn alle vermelde exportbeoordelingsmethoden volledig **_geëxporteerd_** en **_per apparaat_** (ook wel per **_apparaat genoemd)._**

Er zijn verschillende API-oproepen om verschillende typen gegevens op te halen. Omdat de hoeveelheid gegevens groot kan zijn, kunnen deze op twee manieren worden opgehaald:

- **OData**  De API haalt alle gegevens in uw organisatie op als Json-antwoorden, volgens het OData-protocol. Deze methode is het beste voor _kleine organisaties met minder dan 100.000 apparaten._ Het antwoord is paginated, zodat u het veld odata.nextLink uit het antwoord kunt gebruiken \@ om de volgende resultaten op te halen.

- **via bestanden** Met deze API-oplossing kunt u sneller en betrouwbaarder grotere hoeveelheden gegevens verzamelen. Daarom wordt het aanbevolen voor grote organisaties, met meer dan 100.000 apparaten. Met deze API worden alle gegevens in uw organisatie als downloadbestanden opgeslagen. Het antwoord bevat URL's om alle gegevens uit de Azure Storage. Met deze API kunt u al uw gegevens als volgt Azure Storage downloaden:

  - Bel de API om een lijst met url's te downloaden met al uw organisatiegegevens.

  - Download alle bestanden met de download-URL's en verwerkt de gegevens naar eigen goed gebruik.

De gegevens die worden verzameld (voor _OData_ of _via_ bestanden) zijn de huidige momentopname van de huidige status en bevatten geen historische gegevens. Om historische gegevens te verzamelen, moeten klanten de gegevens opslaan in hun eigen gegevensopslag.

Tenzij anders aangegeven, zijn alle vermelde exportbeoordelingsmethoden volledig **_geëxporteerd_** en **_per apparaat_** (ook wel per **_apparaat genoemd)._**

## <a name="1-export-secure-configurations-assessment"></a>1. Secure configurations assessment exporteren

Retourneert alle configuraties en hun status, per apparaat.

### <a name="11-methods"></a>1.1 Methoden

Methode | Gegevenstype | Omschrijving
:---|:---|:---
[Veilige configuratiebeoordeling exporteren (OData)](get-assessmnt-secure-cfg.md#1-export-secure-configuration-assessment-odata) | Veilige configuratie per apparaatverzameling. Zie: [1,2 eigenschappen (OData)](#12-properties-odata) | Retourneert een tabel met een vermelding voor elke unieke combinatie van DeviceId, ConfigurationId. De gegevens die worden verzameld (voor _OData_ of _via_ bestanden) zijn de huidige momentopname van de huidige status en bevatten geen historische gegevens. Om historische gegevens te verzamelen, moeten klanten de gegevens opslaan in hun eigen gegevensopslag.
[Beveiligde configuratiebeoordeling exporteren (via bestanden)](get-assessmnt-secure-cfg.md#2-export-secure-configuration-assessment-via-files) | veilige configuratie per apparaatbestanden. Zie: [1.3 Eigenschappen (via bestanden)](#13-properties-via-files) | Retourneert een tabel met een vermelding voor elke unieke combinatie van DeviceId, ConfigurationId. Met deze API-oplossing kunt u sneller en betrouwbaarder grotere hoeveelheden gegevens verzamelen. Daarom wordt het aanbevolen voor grote organisaties, met meer dan 100.000 apparaten. Met deze API worden alle gegevens in uw organisatie als downloadbestanden opgeslagen. Het antwoord bevat URL's om alle gegevens uit de Azure Storage. Met deze API kunt u al uw gegevens als volgt Azure Storage downloaden: 1.  Bel de API om een lijst met url's te downloaden met al uw organisatiegegevens. 2.  Download alle bestanden met de download-URL's en verwerkt de gegevens naar eigen goed gebruik.

### <a name="12-properties-odata"></a>1.2 Eigenschappen (OData)

Eigenschap (id) | Gegevenstype | Omschrijving
:---|:---|:---
ConfigurationCategory | tekenreeks | Categorie of groepering waarvan de configuratie deel uitmaken: Toepassing, BE, Netwerk, Accounts, Beveiligingsbesturingselementen
ConfigurationId | tekenreeks | Unieke id voor een specifieke configuratie
ConfigurationImpact | tekenreeks | Beoordeelde invloed van de configuratie op de algemene configuratiescore (1-10)
ConfigurationName | tekenreeks | Weergavenaam van de configuratie
ConfigurationSubcategory | tekenreeks | Subcategorie of subgroepering waarvan de configuratie deel uitmaken. In veel gevallen worden hier specifieke mogelijkheden of functies beschreven.
DeviceId | tekenreeks | Unieke id voor het apparaat in de service.
Apparaatnaam | tekenreeks | Volledig gekwalificeerde domeinnaam (FQDN) van het apparaat.
IsApplicable | bool | Geeft aan of de configuratie of het beleid van toepassing is
IsCompliant | bool | Geeft aan of de configuratie of het beleid juist is geconfigureerd
IsExpectedUserImpact | bool | Geeft aan of er gevolgen voor de gebruiker zijn als de configuratie wordt toegepast
OSPlatform | tekenreeks | Platform van het besturingssysteem dat op het apparaat wordt uitgevoerd. Dit geeft specifieke besturingssystemen aan, waaronder variaties binnen dezelfde familie, zoals Windows 10 en Windows 7. Zie ondersteunde besturingssystemen en platforms van tvm voor meer informatie.
RbacGroupName | tekenreeks | De groep Toegangsbeheer (RBAC) op basis van rollen. Als dit apparaat niet is toegewezen aan een RBAC-groep, is de waarde 'Niet toegewezen'. Als de organisatie geen RBAC-groepen bevat, is de waarde 'Geen'.
RecommendationReference | tekenreeks | Een verwijzing naar de aanbevelings-id met betrekking tot deze software.
Tijdstempel | tekenreeks | De laatste keer dat de configuratie op het apparaat is gezien

### <a name="13-properties-via-files"></a>1.3 Eigenschappen (via bestanden)

Eigenschap (id) | Gegevenstype | Omschrijving
:---|:---|:---
Bestanden exporteren | \[matrixreeks\] | Een lijst met download-URL's voor bestanden met de huidige momentopname van de organisatie.
GeneratedTime | tekenreeks | De tijd dat de export is gegenereerd.

## <a name="2-export-software-inventory-assessment"></a>2. Evaluatie van de softwarevoorraad exporteren

Retourneert alle geïnstalleerde software en de gegevens op elk apparaat.

### <a name="21-methods"></a>2.1 Methoden

Methode | Gegevenstype | Omschrijving
:---|:---|:---
[Beoordeling van de softwarevoorraad exporteren (OData)](get-assessmnt-software-inventory.md#1-export-software-inventory-assessment-odata) | Softwarevoorraad per apparaatverzameling. Zie: [2.2 Eigenschappen (OData)](#22-properties-odata) | Retourneert een tabel met een vermelding voor elke unieke combinatie van DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion. De gegevens die worden verzameld (voor _OData_ of _via_ bestanden) zijn de huidige momentopname van de huidige status en bevatten geen historische gegevens. Om historische gegevens te verzamelen, moeten klanten de gegevens opslaan in hun eigen gegevensopslag.
[Beoordeling van softwarevoorraad exporteren (via bestanden)](get-assessmnt-software-inventory.md#2-export-software-inventory-assessment-via-files) | Softwarevoorraad per apparaatbestanden. Zie: [2.3 Eigenschappen (via bestanden)](#23-properties-via-files) | Retourneert een tabel met een vermelding voor elke unieke combinatie van DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion. Met deze API-oplossing kunt u sneller en betrouwbaarder grotere hoeveelheden gegevens verzamelen. Daarom wordt het aanbevolen voor grote organisaties, met meer dan 100.000 apparaten. Met deze API worden alle gegevens in uw organisatie als downloadbestanden opgeslagen. Het antwoord bevat URL's om alle gegevens uit de Azure Storage. Met deze API kunt u al uw gegevens als volgt Azure Storage downloaden: 1.  Bel de API om een lijst met url's te downloaden met al uw organisatiegegevens. 2.  Download alle bestanden met de download-URL's en verwerkt de gegevens naar eigen goed gebruik.

### <a name="22-properties-odata"></a>2.2 Eigenschappen (OData)

Eigenschap (id) | Gegevenstype | Omschrijving
:---|:---|:---
DeviceId | tekenreeks | Unieke id voor het apparaat in de service.
Apparaatnaam | tekenreeks | Volledig gekwalificeerde domeinnaam (FQDN) van het apparaat.
DiskPaths | Matrix[tekenreeks]  | Schijf bewijs dat het product is geïnstalleerd op het apparaat.
EndOfSupportDate | tekenreeks | De datum waarop de ondersteuning voor deze software is of eindigt.
EndOfSupportStatus | tekenreeks | Einde van de ondersteuningsstatus. Kan deze mogelijke waarden bevatten: Geen, EOS-versie, aankomende EOS-versie, EOS-software, aankomende EOS-software.
Id | tekenreeks | Unieke id voor de record.
NumberOfWeaknesses | int|Aantal zwakke punten in deze software op dit apparaat
OSPlatform | tekenreeks | Platform van het besturingssysteem dat op het apparaat wordt uitgevoerd. Dit geeft specifieke besturingssystemen aan, waaronder variaties binnen dezelfde familie, zoals Windows 10 en Windows 7. Zie ondersteunde besturingssystemen en platforms van tvm voor meer informatie.
RbacGroupName | tekenreeks | De groep Toegangsbeheer (RBAC) op basis van rollen. Als dit apparaat niet is toegewezen aan een RBAC-groep, is de waarde 'Niet toegewezen'. Als de organisatie geen RBAC-groepen bevat, is de waarde 'Geen'.
RegistryPaths | Matrix[tekenreeks] | Registergegevens dat het product op het apparaat is geïnstalleerd.
SoftwareFirstSeenTimestamp | tekenreeks | De eerste keer dat deze software op het apparaat werd gezien.
SoftwareName | tekenreeks | Naam van het softwareproduct.
SoftwareVendor | tekenreeks | Naam van de softwareleverancier.
SoftwareVersion | tekenreeks | Versienummer van het softwareproduct.

### <a name="23-properties-via-files"></a>2.3 Eigenschappen (via bestanden)

Eigenschap (id) | Gegevenstype | Omschrijving
:---|:---|:---
Bestanden exporteren | \[matrixreeks\] | Een lijst met download-URL's voor bestanden met de huidige momentopname van de organisatie.
GeneratedTime | tekenreeks | De tijd dat de export is gegenereerd.

## <a name="3-export-software-vulnerabilities-assessment-per-device"></a>3. Evaluatie van beveiligingsproblemen met software per apparaat exporteren

Retourneert alle bekende beveiligingslekken op een apparaat en de details, voor alle apparaten.

### <a name="31-methods"></a>3.1 Methoden

Methode | Gegevenstype | Omschrijving
:---|:---|:---
[Beoordeling van beveiligingsproblemen met software exporteren (OData)](get-assessmnt-software-vulnerabilities.md#1-export-software-vulnerabilities-assessment-odata) | Onderzoeksverzameling Zie: [3.2 Eigenschappen (OData)](#32-properties-odata) | Retourneert een tabel met een vermelding voor elke unieke combinatie van DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId. De gegevens die worden verzameld (voor _OData_ of _via_ bestanden) zijn de huidige momentopname van de huidige status en bevatten geen historische gegevens. Om historische gegevens te verzamelen, moeten klanten de gegevens opslaan in hun eigen gegevensopslag.
[Beoordeling van beveiligingsproblemen met software exporteren (via bestanden)](get-assessmnt-software-vulnerabilities.md#2-export-software-vulnerabilities-assessment-via-files) | Onderzoeksentiteit Zie: [3.3 Eigenschappen (via bestanden)](#33-properties-via-files) | Retourneert een tabel met een vermelding voor elke unieke combinatie van DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId. Met deze API-oplossing kunt u sneller en betrouwbaarder grotere hoeveelheden gegevens verzamelen. Daarom wordt het aanbevolen voor grote organisaties, met meer dan 100.000 apparaten. Met deze API worden alle gegevens in uw organisatie als downloadbestanden opgeslagen. Het antwoord bevat URL's om alle gegevens uit de Azure Storage. Met deze API kunt u al uw gegevens als volgt Azure Storage downloaden: 1.  Bel de API om een lijst met url's te downloaden met al uw organisatiegegevens. 2.  Download alle bestanden met de download-URL's en verwerkt de gegevens naar eigen goed gebruik.

### <a name="32-properties-odata"></a>3.2 Eigenschappen (OData)

Eigenschap (id) | Gegevenstype | Omschrijving
:---|:---|:---
CveId | tekenreeks | Unieke id die is toegewezen aan het beveiligingsprobleem onder het CVE-systeem (Common Vulnerabilities and Exposures).
CvssScore | tekenreeks | De CVSS-score van de CVE.
DeviceId | tekenreeks | Unieke id voor het apparaat in de service.
Apparaatnaam | tekenreeks | Volledig gekwalificeerde domeinnaam (FQDN) van het apparaat.
DiskPaths | \[Matrixreeks\] | Schijf bewijs dat het product is geïnstalleerd op het apparaat.
ExploitabilityLevel | tekenreeks | Het gebruiksniveau van dit beveiligingsprobleem (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)
FirstSeenTimestamp | tekenreeks | De eerste keer dat de CVE van dit product op het apparaat werd gezien.
Id | tekenreeks | Unieke id voor de record.
LastSeenTimestamp | tekenreeks | De laatste keer dat de CVE werd gezien op het apparaat.
OSPlatform | tekenreeks | Platform van het besturingssysteem dat op het apparaat wordt uitgevoerd. Dit geeft specifieke besturingssystemen aan, waaronder variaties binnen dezelfde familie, zoals Windows 10 en Windows 7. Zie ondersteunde besturingssystemen en platforms van tvm voor meer informatie.
RbacGroupName | tekenreeks | De groep Toegangsbeheer (RBAC) op basis van rollen. Als dit apparaat niet is toegewezen aan een RBAC-groep, is de waarde 'Niet toegewezen'. Als de organisatie geen RBAC-groepen bevat, is de waarde 'Geen'.
RecommendationReference | tekenreeks | Een verwijzing naar de aanbevelings-id met betrekking tot deze software.
AanbevolenSecurityUpdate | tekenreeks | Naam of beschrijving van de beveiligingsupdate die door de softwareleverancier wordt geleverd om het beveiligingsprobleem aan te pakken.
AanbevolenSecurityUpdateId | tekenreeks | Id van de toepasselijke beveiligingsupdates of -id voor de bijbehorende richtlijnen of KB-artikelen (Knowledge Base)
Matrixreeks \[ registerpaden\] | Registergegevens dat het product op het apparaat is geïnstalleerd.
SoftwareName | tekenreeks | Naam van het softwareproduct.
SoftwareVendor | tekenreeks | Naam van de softwareleverancier.
SoftwareVersion | tekenreeks | Versienummer van het softwareproduct.
VulnerabilitySeverityLevel | tekenreeks | Ernstniveau dat is toegewezen aan het beveiligingsprobleem op basis van de CVSS-score en dynamische factoren die worden beïnvloed door het bedreigingslandschap.

### <a name="33-properties-via-files"></a>3.3 Eigenschappen (via bestanden)

Eigenschap (id) | Gegevenstype | Omschrijving
:---|:---|:---
Bestanden exporteren | \[matrixreeks\]  | Een lijst met download-URL's voor bestanden met de huidige momentopname van de organisatie.
GeneratedTime | tekenreeks | De tijd dat de export is gegenereerd.

## <a name="see-also"></a>Zie ook

- [Veilige configuratiebeoordeling per apparaat exporteren](get-assessmnt-secure-cfg.md)

- [Beoordeling van de softwarevoorraad per apparaat exporteren](get-assessmnt-software-inventory.md)

- [Beoordeling van beveiligingsproblemen met software per apparaat exporteren](get-assessmnt-software-vulnerabilities.md)

Andere gerelateerde

- [Risicogebaseerd & vulnerability management](next-gen-threat-and-vuln-mgt.md)

- [Beveiligingslekken in uw organisatie](tvm-weaknesses.md)
