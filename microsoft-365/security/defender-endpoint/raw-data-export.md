---
title: Microsoft Defender voor endpoint-gebeurtenis streamen
description: Meer informatie over het configureren van Microsoft Defender voor Eindpunt voor het streamen van Advanced Hunting-gebeurtenissen naar Event Hubs of Een Azure-opslagaccount
keywords: raw data export, streaming API, API, Event hubs, Azure storage, storage account, Advanced Hunting, raw data sharing
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.openlocfilehash: f6a45629d610ea3cc3ca7d517021a215b72b1439
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688751"
---
# <a name="raw-data-streaming-api"></a>Raw Data Streaming API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)

> Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a>Stream Advanced Hunting-gebeurtenissen naar Event Hubs en/of Azure-opslagaccount.

Defender for Endpoint ondersteunt het streamen van alle gebeurtenissen die beschikbaar zijn via [Advanced Hunting](advanced-hunting-overview.md) naar een [Event Hubs](https://docs.microsoft.com/azure/event-hubs/) en/of [Azure-opslagaccount.](https://docs.microsoft.com/azure/event-hubs/)

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r4ga]


## <a name="in-this-section"></a>In deze sectie

Onderwerp | Omschrijving
:---|:---
[Microsoft Defender voor eindpuntgebeurtenissen streamen naar Azure Event Hubs](raw-data-export-event-hub.md)| Meer informatie over het inschakelen van de streaming-API in uw tenant en het configureren van Defender voor Eindpunt om [Advanced Hunting te](advanced-hunting-overview.md) streamen naar Event Hubs.
[Stream Defender voor eindpuntgebeurtenissen naar uw Azure-opslagaccount](raw-data-export-storage.md)| Meer informatie over het inschakelen van de streaming-API in uw tenant en het configureren van Defender voor Eindpunt om [Advanced Hunting](advanced-hunting-overview.md) te streamen naar uw Azure-opslagaccount.


## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd jagen](advanced-hunting-overview.md)
- [Documentatie van Azure Event Hubs](https://docs.microsoft.com/azure/event-hubs/)
- [Documentatie over Azure Storage-account](https://docs.microsoft.com/azure/storage/common/storage-account-overview)
