---
title: Toegang tot de API's voor Microsoft Defender voor Eindpunt
ms.reviewer: ''
description: Meer informatie over hoe u API's kunt gebruiken om werkstromen te automatiseren en te innoveren op basis van de mogelijkheden van Microsoft Defender voor eindpunten
keywords: api's, api, wdatp, open api, microsoft defender voor endpoint api, microsoft defender atp, openbare api, ondersteunde api's, waarschuwingen, apparaat, gebruiker, domein, ip, bestand, geavanceerd zoeken, query
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: a91a401d5d57c7757bc043178c95dc42e7733b41
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571827"
---
# <a name="access-the-microsoft-defender-for-endpoint-apis"></a>Toegang tot de API's voor Microsoft Defender voor Eindpunt 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


**Van toepassing op:** 
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)

> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 



In Defender voor Eindpunt worden veel van de gegevens en acties via een set programmatische API's beschikbaar. Met deze API's kunt u werkstromen automatiseren en innoveren op basis van De mogelijkheden van Defender voor eindpunten. Voor de API-toegang is OAuth2.0-verificatie vereist. Zie [OAuth 2.0 Autorisatiecode](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)voor Flow.

Bekijk deze video voor een kort overzicht van de API's van Defender voor Eindpunt. 
>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4d73M]

Over het algemeen moet u de volgende stappen nemen om de API's te gebruiken:
- Een [AAD-toepassing maken](/microsoft-365/security/defender-endpoint/exposed-apis-create-app-nativeapp)
- Een toegangs token krijgen met deze toepassing
- Het token gebruiken om toegang te krijgen tot Defender for Endpoint API


U hebt toegang tot Defender for Endpoint API met **Toepassingscontext** **of Gebruikerscontext.**

- **Toepassingscontext: (Aanbevolen)** <br>
    Gebruikt door apps die worden uitgevoerd zonder dat een aangemelde gebruiker aanwezig is. bijvoorbeeld apps die als achtergrondservices of daemons worden uitgevoerd.

    Stappen die moeten worden genomen om toegang te krijgen tot Defender voor Endpoint API met toepassingscontext:

  1. Maak een AAD-webtoepassing.
  2. Wijs de gewenste machtiging toe aan de toepassing, bijvoorbeeld 'Leeswaarschuwingen', 'Machines isoleren'. 
  3. Maak een sleutel voor deze toepassing.
  4. Get token using the application with its key.
  5. Het token gebruiken om toegang te krijgen tot de Microsoft Defender for Endpoint API

     Zie Toegang krijgen met [toepassingscontext voor meer informatie.](exposed-apis-create-app-webapp.md)


- **Gebruikerscontext:** <br>
    Wordt gebruikt om acties uit te voeren in de API namens een gebruiker.

    Stappen die u moet ondernemen om toegang te krijgen tot Defender voor Endpoint API met toepassingscontext:

  1. Maak AAD Native-Application.
  2. Wijs de gewenste machtiging toe aan de toepassing, zoals 'Leeswaarschuwingen', 'Isolate Machines' enzovoort. 
  3. Get token using the application with user credentials.
  4. Het token gebruiken om toegang te krijgen tot de Microsoft Defender for Endpoint API

     Zie Toegang krijgen met [gebruikerscontext voor meer informatie.](exposed-apis-create-app-nativeapp.md)


## <a name="related-topics"></a>Verwante onderwerpen
- [Microsoft Defender voor eindpunt-API's](exposed-apis-list.md)
- [Toegang tot Microsoft Defender voor eindpunt met toepassingscontext](exposed-apis-create-app-webapp.md)
- [Toegang tot Microsoft Defender voor Eindpunt met gebruikerscontext](exposed-apis-create-app-nativeapp.md)
