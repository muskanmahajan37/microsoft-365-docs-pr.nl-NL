---
title: Aanbevelingsmethoden en -eigenschappen
description: Hiermee worden de meest recente waarschuwingen opgehaald.
keywords: api's, graph api, ondersteunde api's, get, waarschuwingen, recent
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6ab4d4e1acab0e4b837195f64c369057d7ceb417
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198231"
---
# <a name="recommendation-resource-type"></a>Type aanbevelingsresource

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:** [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)

> Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a>Methoden
Methode |Retourtype |Beschrijving
:---|:---|:---
[Alle aanbevelingen op een lijst zetten](get-all-recommendations.md) | Aanbevelingsverzameling | Hiermee wordt een lijst opgehaald met alle beveiligingsaanbevelingen die van invloed zijn op de organisatie
[Aanbeveling per id krijgen](get-recommendation-by-id.md) | Aanbeveling | Haalt een beveiligingsaanbeveling op met de id
[Aanbevelingssoftware downloaden](get-recommendation-software.md)| [Software](software.md) | Haalt een beveiligingsaanbeveling op die betrekking heeft op een specifieke software
[Aanbevelingsapparaten krijgen](get-recommendation-machines.md)|MachineRef-verzameling | Hiermee wordt een lijst opgehaald met apparaten die zijn gekoppeld aan de beveiligingsaanbeveling
[Beveiligingsproblemen met aanbevelingen krijgen](get-recommendation-vulnerabilities.md) | [Kwetsbaarheidsverzameling](vulnerability.md) | Hiermee wordt een lijst met beveiligingsproblemen opgehaald die zijn gekoppeld aan de beveiligingsaanbeveling


## <a name="properties"></a>Eigenschappen
Eigenschap |   Type   |   Beschrijving
:---|:---|:---
id | Tekenreeks | Aanbevelings-id
productNaam | Tekenreeks | Gerelateerde softwarenaam  
recommendationName | Tekenreeks | Naam van aanbeveling
Zwakke punten | Lang | Aantal gevonden beveiligingslekken
Leverancier | Tekenreeks | Naam van gerelateerde leverancier
aanbevolenVersie | Tekenreeks | Aanbevolen versie
aanbevelingCategory | Tekenreeks | Aanbevelingscategorie. Mogelijke waarden zijn: 'Accounts', 'Toepassing', 'Netwerk', 'OS', 'SecurityStack'
subCategorie | Tekenreeks | Subcategorie Aanbeveling
ernstScore | Dubbel | Mogelijke gevolgen van de configuratie voor de Microsoft Secure Score voor apparaten van de organisatie (1-10)
publicExploit | Booleaanse waarde | Openbare exploit is beschikbaar 
activeAlert | Booleaanse waarde | Actieve waarschuwing is gekoppeld aan deze aanbeveling
associatedThreats | Tekenreeksverzameling | Bedreigingsanalyserapport is gekoppeld aan deze aanbeveling
hersteltype | Tekenreeks | Hersteltype. Mogelijke waarden zijn: "ConfigurationChange","Update","Upgrade","Uninstall"
Status | Enum | Uitzonderingsstatus van aanbeveling. Mogelijke waarden zijn: 'Actief' en 'Uitzondering'
configScoreImpact | Dubbel | Microsoft Secure Score for Devices impact
exposureImpacte | Dubbel | Impact van blootstellingsscore
totalMachineCount | Lang | Aantal geïnstalleerde apparaten
exposedMachinesCount | Lang | Aantal geïnstalleerde apparaten dat wordt blootgesteld aan beveiligingslekken
nonProductivityImpactedAssets | Lang | Aantal apparaten dat niet wordt beïnvloed  
relatedComponent | Tekenreeks |  Gerelateerde softwarecomponent
