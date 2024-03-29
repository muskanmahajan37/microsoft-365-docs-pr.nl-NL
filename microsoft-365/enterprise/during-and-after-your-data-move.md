---
title: Tijdens en na het verplaatsen van uw gegevens
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-administration
ms.collection: SPO_Content
search.appverid:
- MET150
localization_priority: Normal
ms.assetid: f47e3e09-b1dc-4b80-b6ea-fd6e0933407f
f1.keywords:
- NOCSH
description: Gegevensvernieuwingen zijn back-endbewerkingen die plaatsvinden wanneer Microsoft services en bijbehorende gegevens voor uw tenant naar een nieuw datacentergeo verplaatst.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d3d44ffc1650989e5c39f5f79cb6a07065f9e9f1
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/24/2021
ms.locfileid: "52625255"
---
# <a name="during-and-after-your-data-move"></a>Tijdens en na het verplaatsen van uw gegevens

Gegevensverbewegingen zijn een back-endbewerking met minimale gevolgen voor eindgebruikers. Er is geen actie vereist terwijl Microsoft elke service en bijbehorende gegevens voor uw tenant naar een nieuw datacenter-geo verplaatst. Gegevensoverdracht en validatie vinden vooraf plaats op de achtergrond, met minimale gevolgen voor gebruikers.
  
> [!NOTE]
> Bewegingen vinden op verschillende tijdstippen voor elke service plaats. Hierdoor ziet u de beschreven beperkte functionaliteit voor elke service op een ander tijdstip. 
  
Bekijk het Microsoft 365 Berichtencentrum voor bevestiging wanneer de chatservice voor elk van Exchange Online, SharePoint Online en Teams chatservice is voltooid. Zoals wordt weergegeven in de onderstaande tabel, kan het tot 24 maanden na het einde van de inschrijvingsperiode duren voordat de belangrijkste klantgegevens in rust worden verplaatst naar het nieuwe datacenter.   

|**Klanten met een aanmeldingsland in**|**Alle bewegingen voltooid door**|
|:-----|:-----|
|Australië, Nieuw-Zeeland, Fiji  <br/> |1 juli 2022  <br/> |
|Japan   <br/> |1 juli 2022  <br/> |
|India  <br/> |1 juli 2022  <br/> |
|Canada  <br/> |1 juli 2022  <br/> |
|Zuid-Korea  <br/> |1 juli 2022  <br/> |
|Verenigd Koninkrijk  <br/> |1 juli 2022  <br/> |
|Frankrijk  <br/> |1 juli 2022  <br/> |
|Verenigde Arabische Emiraten  <br/> |1 juli 2022  <br/> |
|Zuid-Afrika  <br/> |1 juli 2022  <br/> |
|Zwitserland, Liechtenstein  <br/> |1 juli 2022  <br/> |
|Noorwegen  <br/> |1 november 2022  <br/> |
|Duitsland  <br/> |1 mei 2023  <br/> |
|Brazilië  <br/> |1 juni 2023  <br/> |

## <a name="exchange-online"></a>Exchange Online

Omdat het tijd kost om elke gebruiker voor één tenant naar het nieuwe datacenter te verplaatsen, bevinden sommige gebruikers zich nog steeds in de oude datacenter-geo tijdens de verhuizing, terwijl andere gebruikers zich in de nieuwe datacenter-geo bevinden. Dit betekent dat sommige functies die betrekking hebben op het openen van meerdere postvakken, mogelijk niet volledig werken tijdens een periode van het verhuisproces, wat weken kan duren. Deze functies worden in de volgende secties beschreven.
  
### <a name="open-shared-folder-in-outlook-web-access"></a>'Gedeelde map' openen in Outlook Web Access

Sommige gebruikers openen een gedeelde e-mailmap vanuit een ander postvak (waar de gebruiker lees- of schrijfmachtigingen voor heeft) in Outlook Web Access met behulp van de functie Gedeelde map. In de volgende tabel wordt beschreven hoe toegang tot gedeelde mappen werkt tijdens een postvak verplaatsen. Gebruikers met volledige machtigingen voor een gedeeld postvak kunnen het postvak openen met Outlook Web Access tijdens de verhuizing. 
  
|**Configuratie**|**Beschrijving**|
|:-----|:-----|
|Gebruiker heeft de machtiging postvakmap voor een ander postvak  <br/> |Mogelijk beperkt.  <br/> Als gebruiker A en postvak B zich niet in hetzelfde geo tijdens de tenant verplaatsen, kan gebruiker A de map postvak B niet openen in Outlook Web Access als gebruiker A alleen machtigingen heeft voor een specifieke map in Postvak B.  <br/> Als u een gedeelde map wilt toevoegen, klikt u met de rechtermuisknop op de gebruikersnaam in het linkernavigatievenster en selecteert u **Gedeelde map toevoegen.**  <br/> |
|Gebruiker met volledige postvakmachtiging voor een ander postvak  <br/> |Volledig ondersteund.  <br/> Als gebruiker A de machtiging Volledige toegang heeft voor Postvak B, kan gebruiker A op de gedeelde map in het linkernavigatievenster in Outlook Web Access klikken om een venster met Postvak B te openen.  Een gebruiker kan een gedeeld postvak openen met Outlook Web Access tijdens het verplaatsen zonder nadelige gevolgen. De beperking geldt alleen voor delen op mapniveau in een postvak.           |
  
## <a name="sharepoint-online"></a>SharePoint Online

Wanneer SharePoint Online wordt verplaatst, worden gegevens voor de volgende services ook verplaatst:
  
- One Drive for Business
    
- Microsoft 365 Videoservices
    
- Office in een browser
    
- Microsoft 365-apps voor ondernemingen
    
- Visio Pro voor Microsoft 365
    
Nadat we het verplaatsen van uw onlinegegevens SharePoint voltooid, ziet u mogelijk de volgende effecten.
  
### <a name="microsoft-365-video-services"></a>Microsoft 365 Videoservices

- De gegevens verplaatsen voor video duurt langer dan de bewegingen voor de rest van uw inhoud in SharePoint Online.
    
- Nadat de SharePoint Online-inhoud is verplaatst, is er een periode waarin video's niet kunnen worden afgespeeld.
    
- We verwijderen de getranscodeerd exemplaren uit het vorige datacenter en transcoderen ze opnieuw in het nieuwe datacenter.
    
### <a name="search"></a>Zoeken

Tijdens het verplaatsen van uw SharePoint Online-gegevens migreren we uw zoekindex en zoekinstellingen naar een nieuwe locatie. Totdat we  de overplaatsing van uw gegevens SharePoint Online hebben voltooid, blijven we uw gebruikers van de index op de oorspronkelijke locatie bedienen. Op de nieuwe locatie wordt automatisch gezocht naar uw inhoud nadat we het verplaatsen van uw onlinegegevens SharePoint voltooid. Vanaf dit punt en verder bedienen we uw gebruikers vanaf de gemigreerde index. Wijzigingen in de inhoud die is opgetreden na de migratie, worden pas opgenomen in de gemigreerde index als ze worden opgehaald door het crawlen. De meeste klanten merken niet dat de resultaten minder fris zijn direct nadat we hun SharePoint Online-gegevens hebben verplaatst, maar sommige klanten kunnen in de eerste 24-48 uur een verminderde versheid ervaren 
  
De volgende zoekfuncties zijn van invloed:
  
- Zoekresultaten en zoekresultaten Webonderdelen: resultaten bevatten geen wijzigingen die zijn opgetreden na de migratie totdat ze worden opgehaald door het crawlen. 
    
- Delve: Delve bevat geen wijzigingen die zijn opgetreden na de migratie totdat ze worden opgehaald door het crawlen.
    
- Populariteits- en zoekrapporten voor de site: telt voor Excel-rapporten op de nieuwe locatie alleen gemigreerde tellingen en tellingen uit gebruiksrapporten die zijn uitgevoerd nadat we het verplaatsen van uw SharePoint Online-gegevens hebben voltooid. Alle tellingen uit de tussentijdse periode gaan verloren en kunnen niet worden hersteld. Deze periode is meestal een paar dagen. Sommige klanten kunnen kortere of langere verliezen ervaren.
    
- Videoportal: Het aantal weergaven en statistieken voor de videoportal zijn afhankelijk van de statistieken voor Excel-rapporten, dus het aantal weergaven en statistieken voor de videoportal gaan verloren voor dezelfde periode als voor de Excel rapporten.
    
- eDiscovery: Items die tijdens de migratie zijn gewijzigd, worden pas weergegeven als de wijzigingen worden opgehaald door het crawlen.
    
- Gegevensverliesbeveiliging (DLP): Beleidsregels worden niet afgedwongen voor items die veranderen totdat de wijzigingen worden opgehaald door het crawlen.

Als onderdeel van de migratie wordt het standaardgebied gewijzigd en worden alle nieuwe inhoud in rust opgeslagen in het nieuwe standaardgebied. Bestaande inhoud wordt tot 90 dagen na de eerste wijziging in de SharePoint Online-gegevenslocatie in het beheercentrum zonder gevolgen voor u verplaatst.

## <a name="microsoft-teams"></a>Microsoft Teams

Naast Exchange Online, SharePoint Online en OneDrive voor Bedrijven, migreert Microsoft Teams chatservicegegevens naar het lokale datacenter.

- Teams chatberichten, waaronder privéberichten en kanaalberichten.
- Teams afbeeldingen die worden gebruikt in chats.

Teams bestanden worden opgeslagen in SharePoint Online en Teams chatbestanden worden opgeslagen in OneDrive voor Bedrijven. Voicemail, agenda, chatgeschiedenis en contactpersonen worden opgeslagen in Exchange Online. In veel gevallen worden Exchange Online, SharePoint Online en OneDrive voor Bedrijven al gebruikt door de klant in de geo van het lokale datacenter en maken ze ook deel uit van het Microsoft 365-migratieprogramma voor in aanmerking komende klantlanden.

## <a name="skype-for-business"></a>Skype voor Bedrijven

Skype voor Bedrijven zijn niet meer beschikbaar.  [Skype voor Bedrijven Online wordt op](/lifecycle/announcements/skype-for-business-online-retirement) 31 juli 2021 met pensioen. Na die tijd is de service niet meer toegankelijk. 
  
## <a name="related-topics"></a>Verwante onderwerpen 
 
[De verplaatsing van uw gegevens aanvragen](request-your-data-move.md)
    
[Algemene veelgestelde vragen over het verplaatsen van gegevens](data-move-faq.md)
  
[Nieuwe datacenter-geo's voor Microsoft Dynamics CRM Online](/power-platform/admin/new-datacenter-regions)
  
[Azure-services per regio](https://azure.microsoft.com/regions/)
