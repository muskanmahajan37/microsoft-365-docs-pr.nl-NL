---
title: API voor bestandsstatistieken downloaden
description: Lees hoe u de API Bestandsstatistieken ophalen kunt gebruiken om de statistieken voor het opgegeven bestand op te halen in Microsoft Defender voor Eindpunt.
keywords: api's, graph api, ondersteunde api's, get, bestand, statistieken
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ff43f6c46d89bc92cd1dc2a4fb0f329757b8f69e
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166700"
---
# <a name="get-file-statistics-api"></a>API voor bestandsstatistieken downloaden

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API-beschrijving
Hiermee worden de statistieken voor het opgegeven bestand opgehaald.


## <a name="limitations"></a>Beperkingen
1. Tariefbeperkingen voor deze API zijn 100 oproepen per minuut en 1500 oproepen per uur.


## <a name="permissions"></a>Machtigingen
Een van de volgende machtigingen is vereist om deze API te bellen. Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.

Machtigingstype |   Machtiging  |   Weergavenaam machtiging
:---|:---|:---
Toepassing |   File.Read.All | 'Bestandsprofielen lezen'
Gedelegeerd (werk- of schoolaccount) | File.Read.All | 'Bestandsprofielen lezen'

>[!Note]
> Bij het verkrijgen van een token met gebruikersreferenties:
>- De gebruiker moet ten minste de volgende rolmachtiging hebben: 'Gegevens weergeven' [(Zie](user-roles.md) Rollen maken en beheren voor meer informatie)

## <a name="http-request"></a>HTTP-aanvraag
```
GET /api/files/{id}/stats
```

## <a name="request-headers"></a>Kopteksten aanvragen

Naam | Type | Beschrijving
:---|:---|:---
Autorisatie | Tekenreeks | Bearer {token}. **Vereist**.

## <a name="request-uri-parameters"></a>URI-parameters aanvragen

Naam | Type | Beschrijving
:---|:---|:---
lookBackHours | Int32 | Definieert de uren die we terug zoeken om de statistieken te krijgen. Standaard is dit 30 dagen. **Optioneel**.

## <a name="request-body"></a>Body aanvragen
Leeg

## <a name="response"></a>Antwoord
Als dit is gelukt en het bestand bestaat- 200 OK met statistische gegevens in de body. Als bestand niet bestaat - 404 Niet gevonden.


## <a name="example"></a>Voorbeeld

**Aanvraag**

Hier is een voorbeeld van de aanvraag.

```http
GET https://api.securitycenter.microsoft.com/api/files/0991a395da64e1c5fbe8732ed11e6be064081d9f/stats?lookBackHours=48
```

**Antwoord**

Hier is een voorbeeld van het antwoord.


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.InOrgFileStats",
    "sha1": "0991a395da64e1c5fbe8732ed11e6be064081d9f",
    "orgPrevalence": "14850",
    "orgFirstSeen": "2019-12-07T13:44:16Z",
    "orgLastSeen": "2020-01-06T13:39:36Z",
    "globalPrevalence": "705012",
    "globalFirstObserved": "2015-03-19T12:20:07.3432441Z",
    "globalLastObserved": "2020-01-06T13:39:36Z",
    "topFileNames": [
        "MREC.exe"
    ]
}

```
