---
title: Uw organisatie beschermen tegen webbedreigingen
description: Meer informatie over webbeveiliging in Microsoft Defender ATP en hoe het uw organisatie kan beschermen.
keywords: webbeveiliging, bescherming tegen bedreigingen op het web, surfen op het web, beveiliging, phishing, malware, misbruik, websites, netwerkbeveiliging, Edge, Internet Explorer, Chrome, Firefox, webbrowser
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 7754fa586b24fdedaa9691b45f5da4654c882a5b
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185979"
---
# <a name="protect-your-organization-against-web-threats"></a>Uw organisatie beschermen tegen webbedreigingen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

Webbedreigingsbeveiliging maakt deel uit [van webbeveiliging](web-protection-overview.md) in Defender voor Eindpunt. Er wordt [netwerkbeveiliging gebruikt](network-protection.md) om uw apparaten te beveiligen tegen webbedreigingen. Door te integreren met Microsoft Edge en populaire browsers van derden, zoals Chrome en Firefox, worden webbedreigingen gestopt zonder een webproxy en kunnen apparaten worden beschermd terwijl ze niet of on-premises zijn. Beveiliging tegen webbedreigingen stopt de toegang tot phishingsites, malwarevectoren, misbruiksites, niet-vertrouwde of slechte reputatiesites, evenals sites die u hebt geblokkeerd in de lijst met aangepaste [indicatoren.](manage-indicators.md)

>[!Note]
>Het kan tot een uur duren voordat apparaten nieuwe klantindicatoren ontvangen.

## <a name="prerequisites"></a>Vereisten
Webbeveiliging maakt gebruik van netwerkbeveiliging om webbrowserbeveiliging te bieden in Microsoft Edge en webbrowsers van derden.

Netwerkbeveiliging op uw apparaten in- en uit te zetten:
- Bewerk de beveiligingslijn Defender voor Eindpunt onder **Web & Netwerkbeveiliging** om netwerkbeveiliging in te stellen voordat u deze implementeert of opnieuw implementeert. [Meer informatie over het controleren en toewijzen van de beveiligingslijn defender voor eindpunt](configure-machines-security-baseline.md#review-and-assign-the-microsoft-defender-for-endpoint-security-baseline)
- Schakel netwerkbeveiliging in met de configuratie van Intune-apparaten, SCCM, Groepsbeleid of uw MDM-oplossing. [Meer informatie over het inschakelen van netwerkbeveiliging](enable-network-protection.md)  

>[!Note]
>Als u netwerkbeveiliging in stelt op **Alleen controleren,** is blokkeren niet beschikbaar. U kunt ook pogingen om schadelijke en ongewenste websites alleen op Microsoft Edge te openen detecteren en aanmelden.

## <a name="related-topics"></a>Verwante onderwerpen

- [Overzicht van webbeveiliging](web-protection-overview.md)
- [Beveiliging tegen bedreigingen op het web](web-threat-protection.md)
- [Webbeveiliging controleren](web-protection-monitoring.md)
- [Reageren op webbedreigingen](web-protection-response.md)
- [Netwerkbeveiliging](network-protection.md)