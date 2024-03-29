---
title: Microsoft Search gebruiken om onderwerpen te zoeken in Microsoft Viva-onderwerpen
ms.author: efrene
author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
localization_priority: None
description: Meer informatie over hoe u kunt zoeken naar onderwerpen in Microsoft Viva.
ms.openlocfilehash: 54a143ea0960bf56a0d1c5224658bea404c7621e
ms.sourcegitcommit: 58d74ff60303a879e35d112f10f79724ba41188f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/10/2021
ms.locfileid: "52301714"
---
# <a name="use-microsoft-search-to-find-topics-in-microsoft-viva-topics"></a>Microsoft Search gebruiken om onderwerpen te zoeken in Microsoft Viva-onderwerpen

Hoewel Gebruikers van Viva-onderwerpen onderwerpen kunnen vinden via onderwerp highlights in hun SharePoint sites, kunnen ze ze ook vinden via Microsoft Search. 

## <a name="topic-answer"></a>Antwoord op onderwerp

Wanneer u zoekt naar een specifiek onderwerp in Microsoft Search (bijvoorbeeld 'Saturnus'), als er een onderwerp bestaat en wordt gevonden, wordt het resultaat weergegeven in de suggestienotatie Antwoorden.

Het antwoord op het onderwerp wordt weergegeven:
- Onderwerpnaam
- Alternatieve namen: Alternatieve namen of acroniems voor het onderwerp.
- Definitie: Beschrijving van het onderwerp dat door AI wordt geleverd of handmatig door een persoon is toegevoegd.
- Voorgestelde of vastgemaakte personen: personen die door AI worden voorgesteld of vastgemaakt aan het onderwerp door een persoon
- Voorgestelde of vastgemaakte resources: Bestanden, pagina's of sites, voorgesteld door AI of vastgemaakt aan het onderwerp door een persoon. 

   ![Onderwerp in zoeken](../media/knowledge-management/search-topic-answer.png) 

De onderwerppagina kan worden weergegeven in de zoekresultaten, zelfs als de antwoordkaart voor het onderwerp niet wordt weergegeven.

In de zoekresultaten in Word, PowerPoint, Outlook en Excel wordt ook het antwoord op het onderwerp als er een wordt gevonden.


## <a name="acronyms"></a>Acroniems

In Viva-onderwerpen kunt u handmatig een onderwerp bewerken om er een acroniem voor op te nemen als <b>alternatieve naam.</b> Hierdoor kan een gebruiker die alleen zoekt op het acroniem van het onderwerp, het antwoord op het onderwerp vinden via Microsoft Search.

[Acronym Answers](/microsoftsearch/manage-acronyms) is een functie die beschikbaar is via Microsoft Search en wordt afzonderlijk beheerd van Viva-onderwerpen.

## <a name="bookmarks-and-topics"></a>Bladwijzers en onderwerpen

[Bladwijzers](/microsoftsearch/manage-bookmarks) zijn een Microsoft Search-functie waarmee personen snel belangrijke sites en hulpprogramma's kunnen vinden met alleen een zoekopdracht (bijvoorbeeld een reisboekingshulpmiddel op een externe site buiten hun Microsoft 365 tenant). Ze worden gemaakt door zoekbeheerders in het Microsoft 365 beheercentrum. 

Voor gebruikers die op zoek zijn naar informatie over het boeken van een reis voor werk:

- Als sommige gebruikers de naam van het reishulpmiddel kennen (bijvoorbeeld 'Concur'), kunt u gemakkelijker een bladwijzer maken om rechtstreeks naar de externe site te gaan.
- Voor gebruikers die in het algemeen zoeken naar 'reizen', maakt u een onderwerp over 'Reizen' met de informatie die ze verwachten te zien. U kunt een koppeling toevoegen aan de externe site Concur in de beschrijving van het onderwerp. Als de koppeling is gekoppeld aan een interne boekingssite voor reizen die wordt gehost op de Microsoft 365 tenant, kunt u deze toevoegen aan de 'Vastgemaakte resources'.
 
### <a name="search-results-priority"></a>Prioriteit voor zoekresultaten 
 
In de zoekervaring van gebruikers worden zoekresultaten weergegeven in de volgende prioriteit in Microsoft Search wanneer een gebruiker zoekt naar een term zoals 'reizen'.
1. Gepubliceerde of bevestigde onderwerpen 
2. Bladwijzers
3. Voorgestelde onderwerpen
