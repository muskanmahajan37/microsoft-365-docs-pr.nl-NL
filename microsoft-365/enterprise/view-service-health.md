---
title: De status van de Microsoft 365-service controleren
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365P_ServiceHealthModern
- O365M_ServiceHealthModern
- O365E_ViewStatusServices
- O365E_ServiceHealthModern
- seo-marvel-apr2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- BCS160
- IWA160
ms.assetid: 932ad3ad-533c-418a-b938-6e44e8bc33b0
description: Bekijk de status van Microsoft 365-services voordat u de ondersteuning belt om te zien of er een actieve serviceonderbreking is.
ms.openlocfilehash: e0ab4eaa1f7a96168839a4abef2f0f254a21d0ad
ms.sourcegitcommit: 437bdbf3f99610869811e80432a59b5f244f7a87
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/08/2021
ms.locfileid: "51644630"
---
# <a name="how-to-check-microsoft-365-service-health"></a>De status van de Microsoft 365-service controleren

[![Etiket om u te laten weten dat het beheercentrum wordt gewijzigd en meer informatie vindt u op aka.ms/aboutM365preview.](../media/O365-Admin-AdminCenterChanging.png)](/office365/admin/microsoft-365-admin-center-preview?preserve-view=true&view=o365-worldwide)

U kunt de status van uw Microsoft-services, waaronder Office op het web, Yammer, Microsoft Dynamics CRM en cloudservices voor mobiel apparaatbeheer, bekijken op de **pagina Service-status** in het [Microsoft 365-beheercentrum.](https://go.microsoft.com/fwlink/p/?linkid=2024339) Als u problemen ondervindt met een cloudservice, kunt u de service-status controleren om te bepalen of dit een bekend probleem is met een oplossing in uitvoering voordat u de ondersteuning belt of tijd besteedt aan het oplossen van problemen.

Als u zich niet kunt aanmelden bij het beheercentrum, kunt u de [pagina servicestatus](https://status.office365.com) gebruiken om te controleren op bekende problemen waardoor u zich niet kunt aanmelden bij uw tenant.  Meld u ook aan om ons te [volgen @MSFT365status](https://twitter.com/MSFT365Status) op Twitter om informatie over bepaalde gebeurtenissen te zien.

  
### <a name="how-to-check-service-health"></a>Servicestatus controleren

1. Ga naar het Microsoft 365-beheercentrum bij [https://admin.microsoft.com](https://go.microsoft.com/fwlink/p/?linkid=2024339) en meld u aan met een beheerdersaccount.

    > [!NOTE]
    > Personen aan wie de rol globale beheerder of serviceondersteuningsbeheerder is toegewezen, kunnen de servicetoestand bekijken. Beheerders van Exchange, SharePoint en Skype voor Bedrijven dient de rol servicebeheerder te zijn toegewezen om de servicestatus te kunnen bekijken. Zie Over beheerdersrollen voor meer informatie over rollen die de status van de service [kunnen weergeven.](../admin/add-users/about-admin-roles.md?preserve-view=true&view=o365-worldwide#commonly-used-microsoft-365-admin-center-roles)
  
2. Als u het nieuwe beheercentrum niet  gebruikt, selecteert u op de startpagina de schakelknop Het nieuwe **beheercentrum** uitproberen in de rechterbovenhoek.

3. Als u de servicetoestand wilt bekijken, gaat u in het beheercentrum naar **Health** Service Health of selecteert u de  >   **service-statuskaart** op het **dashboard Start.** De dashboardkaart geeft aan of er een actief serviceprobleem is en koppelingen naar de gedetailleerde **pagina Service-status.**
  
4. Op de **pagina Service-status** wordt de status van elke cloudservice weergegeven in een tabelindeling.

   ![View of current issues in service health](../media/service-health-all-services.png)

Op **het tabblad Alle services** (de standaardweergave) worden alle services en de huidige status weergegeven. Een pictogram en de **kolom Status** geven de status van elke service aan. 

Als u de weergave wilt filteren op services die momenteel een incident ondervinden, selecteert u het tabblad **Incidenten** boven aan de pagina. Als u **het tabblad Adviseurs** selecteert, worden alleen services weergegeven die momenteel een advies hebben gepost. 

Op **het** tabblad Geschiedenis ziet u de geschiedenis van incidenten en adviezen die zijn opgelost.

Als u een probleem ondervindt met een Microsoft 365-service en u deze niet ziet op de pagina **Service-status,** laat het ons dan weten door **Een** probleem melden te selecteren en het korte formulier in te vullen. We bekijken gerelateerde gegevens en rapporten van andere organisaties om te zien hoe wijdverspreid het probleem is en of het afkomstig is van onze service. Als dit het wel is gebeurd, voegen we het toe als een nieuw incident of advies op de **pagina Service-status,** waar u de resolutie kunt bijhouden. Als u deze niet binnen 30 minuten in de lijst ziet staan, kunt u contact opnemen met de ondersteuning om het probleem op te lossen.

Als u de weergave wilt aanpassen van welke services op het dashboard worden weergeven, selecteert u Aangepaste weergave Voorkeuren en schakelt u de selectievakjes uit voor de services die u wilt filteren uit de  >  dashboardweergave Service health. Controleer of het selectievakje is ingeschakeld voor elke service die u wilt controleren.    

Als u zich wilt registreren voor e-mailmeldingen van nieuwe incidenten die van invloed zijn op uw tenant en statuswijzigingen voor een actief incident, selecteert u Voorkeuren E-mail, klikt u op Meldingen over service heide verzenden per e-mail en geeft u het volgende  >  op: 

- Maximaal twee e-mailadressen.
- Of u nu meldingen voor incidenten of adviezen wilt
- De services waarvoor u een melding wilt ontvangen

> [!NOTE]
> Elke beheerder kan zijn voorkeuren instellen en de bovenstaande limiet van twee e-mailadressen is per beheerdersaccount.

> [!TIP]
> U kunt ook de [Microsoft 365 Admin-app](https://go.microsoft.com/fwlink/p/?linkid=627216) op uw mobiele apparaat gebruiken om service-status weer te geven. Dit is een uitstekende manier om op de hoogte te blijven van pushmeldingen. 
  
### <a name="view-details-of-posted-service-health"></a>Details bekijken van geposte servicestatus

Als u **in de weergave** Alle services de servicestatus selecteert, wordt een overzichtsweergave van adviezen of incidenten geopend.
  
[![Schermafbeelding van het serviceadvies ](../media/service-health-advisory.png)](../media/service-health-advisory.png#lightbox)

Het overzicht met het advies of incident bevat de volgende informatie:

- **Titel** - Een overzicht van het probleem.
- **Service:** de naam van de betreffende service.
- **ID** - Een numerieke id voor het probleem.
- **Status:** hoe dit probleem van invloed is op de service.
- **Begintijd:** de tijd waarop het probleem is begonnen.
- **Laatst bijgewerkt:** de laatste keer dat het bericht over de service-status is bijgewerkt. We plaatsen regelmatig berichten om u te laten weten wat de voortgang is bij het toepassen van een oplossing.

Selecteer de titel van het probleem om de pagina met probleemdetails weer te geven, met meer informatie over het probleem, inclusief de geschiedenis van alle berichten die zijn gepost terwijl we aan een oplossing werken. [](#history)

![Een schermafbeelding met probleemdetails](../media/service-health-advisory-detail.png)

### <a name="translate-service-health-details"></a>Details servicestatus vertalen

De beschrijvingen van de servicestatussen worden in realtime gepost, dus ze worden niet automatisch in uw eigen taal vertaald. De details van een servicegebeurtenis zijn alleen in het Engels. Ga als volgt te werk als u een beschrijving wilt vertalen:
  
1. Ga naar [Translator](https://www.bing.com/translator/).

2. Selecteer op de pagina **Servicestatus** een incident of advies. Kopieer onder **Details weergeven** de tekst over het probleem.

3. Plak de tekst in Translator en kies **Vertalen**.

### <a name="definitions"></a>Definities

Meestal worden services als gezond weergegeven zonder verdere informatie. Als er een probleem met een status is, wordt het als een advies of een incident geïdentificeerd en wordt de huidige status weergegeven.
  
> [!TIP]
> In de servicestatus wordt geen gepland onderhoud weergegeven. U kunt gepland onderhoud volgen via het **Berichtencentrum**. U kunt filteren op berichten in de categorie Wijzigingsplanning om erachter te komen wanneer de wijziging plaatsvindt, wat het effect is en hoe u zich erop moet voorbereiden. Zie [Berichtencentrum in Microsoft 365](https://support.office.com/article/38fb3333-bfcc-4340-a37b-deda509c2093) voor meer informatie.
  
### <a name="incidents-and-advisories"></a>Incidenten en adviezen

| Pictogram | Omschrijving |
|:-----|:-----|
|![Information icon for advisory](../media/a7f5fd21-c760-4948-9bc1-50f7c8070e28.png)|Als voor een service een advies wordt getoond, is er een probleem bekend waarvan een aantal gebruikers last heeft, maar de service is nog wel beschikbaar. Een advies biedt meestal een tijdelijke oplossing voor het probleem. Het probleem kan af en toe optreden of het bereik ervan of het aantal getroffen gebruikers is beperkt.  <br/> |
|![Exclamation point icon for incident](../media/a636db57-6083-44dc-bbd5-556850804f17.png)|Als voor een service een incident wordt getoond, gaat het om een kritiek probleem en is de service of een belangrijke functie ervan niet beschikbaar. Gebruikers kunnen bijvoorbeeld geen e-mail meer verzenden en ontvangen en kunnen zich niet aanmelden. Incidenten zijn van merkbare invloed op gebruikers. Wanneer er een incident wordt uitgevoerd, bieden we updates over het onderzoek, risicobeperking en bevestiging van de oplossing in het dashboard voor servicestatus.  <br/> |

### <a name="status-definitions"></a>Statusdefinities

| Status | Definitie |
|:-----|:-----|
|**Onderzoeken** | Wij zijn op de hoogte van een potentieel probleem en verzamelen meer informatie over wat er aan de hand is en wat de mogelijke gevolgen zijn. |
|**Verslechtering van service** | Wij hebben bevestigd dat er een probleem is dat van invloed kan zijn op een service of functie. U krijgt deze status te zien als bijvoorbeeld een service langzamer presteert dan normaal, er onregelmatige onderbrekingen zijn of als een functie niet werkt. |
|**Serviceonderbreking** | U krijgt deze status te zien als is vastgesteld dat gebruikers als gevolg van een probleem de service niet kunnen gebruiken. In dit geval is het probleem aanzienlijk en kan telkens worden gereproduceerd. |
|**Service wordt hersteld** | De oorzaak van het probleem is achterhaald; er is bekend welke herstelactie er moeten worden ondernomen en er wordt aan gewerkt om de service weer in orde te maken. |
|**Uitgebreid herstel** | Deze status geeft aan dat er een herstelactie gaande is om de service voor de meeste gebruikers weer toegankelijk te maken. Het kan enige tijd duren voordat alle getroffen systemen weer in orde zijn. Mogelijk ziet u deze status ook als we een tijdelijke oplossing hebben gemaakt om het effect te beperken totdat we klaar zijn om een permanente oplossing toe te passen. |
|**Onderzoek opgeschort** | Als uitgebreid onderzoek van een mogelijk probleem aanvullende informatie van klanten vereist voor nader onderzoek, krijgt u deze status te zien. Als wij u vragen actie te ondernemen, laten we u weten welke gegevens of logboeken we nodig hebben. |
|**Service hersteld** | Wij hebben bevestigd dat een herstelactie het onderliggende probleem heeft opgelost en dat de service geheel is hersteld. Bekijk de details van het probleem als u wilt weten wat er is misgegaan. |
|**Onwaar positief** | Na een uitgebreid onderzoek hebben we bevestigd dat de service gezond is en volgens de ontwerpstijl werkt. Er is geen invloed op de service waargenomen of de oorzaak van het incident is buiten de service ontstaan. |
|**Rapport na incident gepubliceerd** | We hebben een postincidentrapport gepubliceerd voor een specifiek probleem dat informatie over hoofdoorzaken bevat en de volgende stappen om ervoor te zorgen dat een soortgelijk probleem niet opnieuw wordt veroorzaakt. |

### <a name="history"></a>Geschiedenis

Met servicestatus kunt u de huidige status bekijken en de geschiedenis bekijken van serviceadviseurs en incidenten die uw tenant in de afgelopen 30 dagen hebben beïnvloed. Als u de status van alle services in het verleden wilt bekijken, **selecteert** u Geschiedenis weergeven op de pagina met probleemdetails.
  
![Show link to health history](../media/service-health-view-history.png)
  
Voor de geselecteerde periode wordt een lijst met alle servicestatusberichten weergegeven, zoals hieronder is te zien:
  
![View service health history](../media/service-health-history.png)
  
Vouw een rij uit om meer details over het probleem weer te geven.
  
Zie Transparante bewerkingen van [Microsoft 365](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity)voor meer informatie over onze inzet voor uptime.

## <a name="related-topics"></a>Verwante onderwerpen

[Activiteitenrapporten in het Microsoft 365-beheercentrum](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) 
 [Voorkeuren voor berichtencentrum](../admin/manage/message-center.md?preserve-view=true&view=o365-worldwide#preferences)<br/>
[Status van Windows-release controleren in het beheercentrum](https://docs.microsoft.com/windows/deployment/update/check-release-health)
