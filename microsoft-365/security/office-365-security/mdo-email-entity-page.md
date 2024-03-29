---
title: De pagina E-mailentiteit van Microsoft Defender Office 365 (MDO)
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 01/21/2021
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Klanten van Microsoft Defender Office 365 E5 en P1 en P2 kunnen nu een 360-gradenweergave krijgen van elke e-mail met e-mailentiteitspagina.
ms.openlocfilehash: aa5d7effb66c4805f6983fa1afac19255bc996e4
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52539093"
---
# <a name="the-email-entity-page"></a>Entiteitspagina van e-mail

**In dit artikel:**
- [De pagina e-mailentiteit bereiken](#reach-the-email-entity-page)
- [De pagina e-mailentiteit lezen](#read-the-email-entity-page)
- [Paginatabbladen voor e-mailentiteit gebruiken](#use-email-entity-page-tabs)
- [Nieuw op de pagina e-mailentiteit](#new-to-the-email-entity-page)

Beheerders van Microsoft Defender voor Office 365 (of MDO) E5 en MDO P1 en P2 hebben een 360 graden-weergave van e-mail met behulp van de pagina **E-mailentiteit.** Deze go-to-e-mailpagina is gemaakt om informatie over de [fly-out 'e-mailgegevens'](threat-explorer-views.md)van Threat Explorer te verbeteren.

## <a name="reach-the-email-entity-page"></a>De pagina e-mailentiteit bereiken

In het bestaande beveiligings- & compliancecentrum (protection.office.com) of het nieuwe Microsoft 365-beveiligingscentrum (security.microsoft.com) kunt u de pagina e-mailentiteit bekijken en gebruiken..

|Centreer|URL|Navigatie|
|---|---|---|
|Beveiligings- & compliance |protection.office.com|Threat Management \> Explorer|
|Microsoft 365-beveiligingscentrum |security.microsoft.com|E-& \> Samenwerkingsverkenner|

Selecteer in Threat Explorer het onderwerp van een e-mailbericht dat u onderzoekt. Er wordt een gouden balk weergegeven boven aan de e-mail fly-out voor die e-mail. In deze uitnodiging voor de nieuwe pagina leest u 'Try out our new email entity page with enriched data...'. Selecteer om de nieuwe pagina weer te geven.

:::image type="content" source="../../media/email-entities-1-navigation-to-ee.png" alt-text="U ziet een gouden banner met de woorden *Probeer onze nieuwe e-mailentiteitspagina met verrijkte gegevens* uit om naar de nieuwe ervaring te gaan.":::

:::image type="content" source="../../media/email-entities-2-eep.png" alt-text="Deze afbeelding van de pagina e-mailentiteit richt zich op koppen die u ziet. Let op: de e-mailkoptekst wordt hier weergegeven.":::

> [!NOTE]
> De machtigingen die nodig zijn om deze pagina weer te geven en te gebruiken, zijn hetzelfde als voor het weergeven van Threat Explorer. De beheerder moet lid zijn van globale beheerder of globale lezer, of beveiligingsbeheerder of beveiligingslezer.

## <a name="read-the-email-entity-page"></a>De pagina e-mailentiteit lezen

De structuur is zo ontworpen dat u eenvoudig kunt lezen en in één oogopslag kunt navigeren. Met verschillende tabbladen boven aan de pagina kunt u meer details onderzoeken. De indeling werkt als volgende:

1. De meest vereiste velden staan aan de linkerkant van de fly-out. Deze details zijn 'plakkerig', wat betekent dat ze aan de linkerkant zijn verankerd, ongeacht het tabblad waar u naartoe navigeert in de rest van de fly-out.

    :::image type="content" source="../../media/email-entities-3-left-panel.png" alt-text="Afbeelding van de pagina e-mailentiteit met de linkerkant gemarkeerd. De titel en feiten over de bezorging van e-mail staan hier.":::

2. In de rechterbovenhoek vindt u de acties die u op een e-mail kunt uitvoeren. Alle acties die via Verkenner kunnen worden ondernomen, zijn ook beschikbaar via de pagina e-mailentiteit.

    :::image type="content" source="../../media/email-entities-5-preview.png" alt-text="Afbeelding van de pagina e-mailentiteit met de *rechterkant* gemarkeerd, deze keer. Acties zoals 'E-mailvoorbeeld' en 'Ga naar quarantaine' zijn hier.":::

3. U kunt een diepere analyse uitvoeren door de rest van de pagina te sorteren. Controleer de e-maildetectiedetails, de status van e-mailverificatie en de koptekst. Dit gebied moet per geval worden bekeken, maar de informatie in deze tabbladen is beschikbaar voor elk e-mailbericht.

    :::image type="content" source="../../media/email-entities-4-middle-panel.png" alt-text="Het hoofdvenster van deze pagina bevat de e-mailkoptekst en verificatiestatus.":::

### <a name="use-email-entity-page-tabs"></a>Paginatabbladen voor e-mailentiteit gebruiken

Met de tabbladen boven aan de entiteitspagina kunt u e-mail efficiënt onderzoeken.

1. **Tijdlijn:** De tijdlijnweergave voor een e-mailbericht (volgens de tijdlijn van Threat Explorer) toont de oorspronkelijke bezorging van gebeurtenissen na de bezorging die plaatsvinden in een e-mailbericht. Voor e-mailberichten die geen acties na de bezorging hebben, wordt in de weergave de oorspronkelijke bezorgingsrij weergegeven in de tijdlijnweergave. Gebeurtenissen zoals: Zero-hour Auto Purge (ZAP), Herstellen, URL-klikken, enzovoort, uit bronnen zoals: systeem, beheerder en gebruiker, worden hier weergegeven, in de volgorde waarin ze hebben plaatsgevonden.
2. **Analyse:** Analyse toont velden die beheerders helpen een e-mail grondig te analyseren. Voor gevallen waarin beheerders meer moeten weten over detectie, afzender/geadresseerde en e-mailverificatiegegevens, moeten ze het tabblad Analyse gebruiken. Koppelingen voor bijlagen en URL's vindt u ook op deze pagina, onder 'Gerelateerde entiteiten'. Zowel bijlagen als geïdentificeerde bedreigingen worden hier genummerd en als u klikt, gaat u rechtstreeks naar de pagina's Bijlagen en URL's. Dit tabblad heeft ook de optie Koptekst weergeven om *de e-mailkop weer te geven.* Beheerders kunnen elk detail van e-mailkoppen, naast elkaar met informatie in het hoofdvenster, voor de duidelijkheid vergelijken.
3. **Bijlagen:** Hiermee worden bijlagen in het e-mailbericht onderzocht, met andere details die zijn gevonden in bijlagen. Het aantal weergegeven bijlagen is momenteel beperkt tot 10. Let op: detonatiedetails voor bijlagen die schadelijk zijn gevonden, worden hier ook weergegeven.
4. **URL's:** Dit tabblad bevat URL's die in het e-mailbericht zijn gevonden, met andere details over de URL's. Het aantal URL's is op dit moment beperkt tot 10, maar deze 10 hebben prioriteit om eerst schadelijke *URL's weer te geven.* Prioriteitsprioriteit bespaart u tijd en gissen. De URL's die schadelijk en tot ontploffing zijn gebracht, worden hier ook weergegeven.
5. **Soortgelijke e-mailberichten:** Dit tabblad bevat alle e-mailberichten die lijken op de *netwerkbericht-id + de* combinatie van geadresseerden die specifiek zijn voor deze e-mail. Overeenkomsten zijn alleen gebaseerd op *de tekst van het* bericht. De vaststellingen die zijn gedaan op e-mails om ze te categoriseren als 'vergelijkbaar', bevatten geen overweging van *bijlagen.*

## <a name="new-to-the-email-entity-page"></a>Nieuw op de pagina e-mailentiteit

Deze pagina met e-mailentiteitentiteit biedt nieuwe mogelijkheden. Hier is de lijst.

### <a name="email-preview-for-cloud-mailboxes"></a>E-mailvoorbeeld voor cloudpostvakken

Beheerders kunnen een voorbeeld van e-mailberichten bekijken in cloudpostvakken, ***als*** de e-mailberichten nog steeds aanwezig zijn in de cloud. In het geval van een soft delete (door een beheerder of gebruiker) of ZAP (om in quarantaine te plaatsen), zijn e-mailberichten niet meer aanwezig in de cloudlocatie. In dat geval kunnen beheerders geen voorbeeld van deze specifieke e-mailberichten bekijken. E-mailberichten die zijn verwijderd of waar de bezorging is mislukt, zijn nooit in het postvak be komen. Hierdoor kunnen beheerders ook geen voorbeeld van deze e-mailberichten bekijken.

> [!WARNING]
> Als u een voorbeeld van e-mailberichten bekijkt, moet een speciale rol met de naam ***Voorbeeld** _ worden toegewezen aan beheerders. U kunt deze rol toevoegen door naar _ *Machtigingen & rollen** > **E-mail &** **samenwerkingsrollen** in *security.microsoft.com* of Machtigingen *in* protection.office.com. Voeg de ***voorbeeldrol*** toe aan een van de rollengroepen of een kopie van een rollengroep waarmee beheerders in uw organisatie kunnen werken in Threat Explorer.

### <a name="detonation-details"></a>Detonatiedetails

Deze details zijn specifiek voor e-mailbijlagen en URL's.

Gebruikers zien verrijkte detonatiedetails voor bekende schadelijke bijlagen of hyperlinks in hun postvakken, zoals Detonation Chain, Detonation Summary, Screenshot en Observed behavior details om klanten te helpen begrijpen waarom de bijlage of URL als schadelijk en tot stand is gebracht.

- *Detonatieketen:* één bestand of URL-detonatie kan meerdere detonaties veroorzaken. De detonatieketen houdt het pad van detonaties bij, inclusief het oorspronkelijke schadelijke bestand of de URL die de uitspraak heeft veroorzaakt, en alle andere bestanden of URL's die zijn veroorzaakt door de detonatie. Deze URL's of bijgevoegde bestanden zijn mogelijk niet rechtstreeks aanwezig in de e-mail, maar het is belangrijk om te bepalen waarom het bestand of de URL schadelijk is gevonden.
- *Samenvatting van de detonatie:* Dit geeft informatie over:
  - Detonatietijdbereik.
  - Uitspraak van het bijgevoegde bestand of DE URL.
  - Gerelateerde informatie (bestandsnummer, URL's, IPs of Domeinen), die andere entiteiten zijn die tijdens de detonatie worden onderzocht.
- *Schermafbeelding van detonatie:* hier ziet u schermafbeeldingen die zijn gemaakt tijdens het detonatieproces.
- *Detonatiedetails:* dit zijn de exacte gedragsdetails van elk proces dat plaatsvond tijdens de detonatie.

:::image type="content" source="../../media/email-entities-6-detonation-page.png" alt-text="Schermafbeelding van de samenvatting van de detonatie met de ketting, samenvatting, detonatiedetails en schermafbeelding onder de kop *Deep Analysis*.":::

### <a name="other-innovations"></a>Andere innovaties

*Tags:* dit zijn tags die zijn toegepast op gebruikers. Als de gebruiker een geadresseerde is, zien beheerders een *geadresseerdelabel.* Als de gebruiker een afzender is, wordt ook een *afzenderlabel* gebruikt. Dit wordt weergegeven aan de linkerkant van de pagina met e-mailentiteiten (in het gedeelte dat wordt beschreven als plakkerig en dus verankerd aan de pagina). 

*Meest recente* bezorgingslocatie: De meest recente bezorgingslocatie is de locatie waar een e-mailbericht is geland na systeemacties zoals ZAP of beheeracties zoals Verplaatsen naar verwijderde items, voltooien. De meest recente bezorgingslocatie is niet bedoeld om beheerders te informeren over de huidige locatie van *het* bericht. Als een gebruiker bijvoorbeeld een bericht verwijdert of naar het archief verplaatst, wordt de bezorgingslocatie niet bijgewerkt. Als er echter een systeemactie heeft plaatsgevonden en de locatie is bijgewerkt (zoals een ZAP waardoor een e-mailbericht naar Quarantaine wordt verplaatst), wordt de locatie voor de meest recente bezorging bijgewerkt naar Quarantaine.

*E-maildetails:* Details die nodig zijn voor een beter begrip van e-mail die beschikbaar is op *het tabblad* Analyse.

- *Exchange Transportregels (ETR's of Mailflow-regels)*: Deze regels worden toegepast op een bericht in de transportlaag en hebben voorrang op phish- en spam-vonnissen. Deze kunnen alleen worden gemaakt en gewijzigd in het Exchange-beheercentrum, maar als een ETR van toepassing is op een bericht, worden de ETR-naam en GUID hier weergegeven. Waardevolle informatie voor het bijhouden van doeleinden.

- *Systeem overschrijven:* Dit is een manier om uitzonderingen te maken op de bezorgingslocatie die is bedoeld voor een bericht door de bezorgingslocatie te overschrijven die door het systeem wordt gegeven (volgens de technologie voor bedreiging en detectie).

- *Regel ongewenste postvak:*'Ongewenste e-mail' is verborgen Regel voor Postvak IN die standaard is ingeschakeld in elk postvak.
  - Wanneer de regel Ongewenste e-mail is ingeschakeld in het postvak, Exchange Online Protection EOP (EOP) berichten volgens bepaalde criteria naar Ongewenste e-mail verplaatsen. De verhuizing kan zijn gebaseerd op actie voor spamfiltering *Bericht verplaatsen* naar de map Ongewenste e-mail of op de lijst Geblokkeerde afzenders in het postvak. Door de regel Ongewenste e-mail uit te sluiten, wordt voorkomen dat berichten worden bezorgd in de map Ongewenste e-mail op basis van de Safe *afzenders* in het postvak.
  - Wanneer de regel voor ongewenste e-mail *is* uitgeschakeld in het postvak, kan EOP geen berichten verplaatsen naar de map Ongewenste e-mail op basis van de actie Voor spamfiltering Bericht verplaatsen naar map Ongewenste e-mail of de veilige lijstverzameling in het postvak.

- *Bulksgewijs klachtenniveau (BCL)*: het bulkklachtsniveau (BCL) van het bericht. Een hogere BCL geeft aan dat een bulkbericht waarschijnlijk meer klachten kan genereren (het natuurlijke resultaat als de e-mail waarschijnlijk spam is).

- *Betrouwbaarheidsniveau voor spam (SCL)*: Het betrouwbaarheidsniveau voor spam (SCL) van het bericht. Hoe hoger de waarde, hoe groter de kans dat het bericht spam is.

- *Domeinnaam:* is de domeinnaam van de afzender.

- *Domeineigenaar:* geeft de eigenaar van het verzendende domein aan.

- *Domeinlocatie:* geeft de locatie van het verzendende domein aan.

- *Domein gemaakt datum:* geeft de datum van het maken van het verzendende domein aan. Een nieuw gemaakt domein is iets waar u voorzichtig mee kunt zijn als andere signalen wijzen op verdacht gedrag.

*E-mailverificatie:* E-mailverificatiemethoden die door Microsoft 365 worden gebruikt, zijn SPF, DKIM en DMARC.

- Sender Policy Framework **(SPF):** Beschrijft de resultaten voor SPF-controle voor het bericht. Mogelijke waarden kunnen zijn:
  - Pass (IP-adres): De SPF controleert of het bericht is doorgegeven en bevat het IP-adres van de afzender. De client wordt geautoriseerd e-mail te verzenden of door te sturen namens het domein van de afzender.
  - Fail (IP-adres): de SPF-controle voor het bericht is mislukt en bevat het IP-adres van de afzender. Dit wordt ook wel een hard fail genoemd.
  - Softfail (reden): De SPF-record heeft de host aangewezen als niet toegestaan om te verzenden, maar is in overgang.
  - Neutraal: In de SPF-record wordt expliciet vermeld dat niet wordt vermeld of het IP-adres is geautoriseerd om te verzenden.
  - Geen: Het domein heeft geen SPF-record of de SPF-record evalueert niet tot een resultaat.
  - Temperror: Er is een tijdelijke fout opgetreden. Bijvoorbeeld een DNS-fout. Dezelfde controle kan mogelijk later wel worden uitgevoerd.
  - Permerror: Er is een permanente fout opgetreden. Het domein heeft bijvoorbeeld een foutief ingedeeld SPF-record.

- DomainKeys Identified Mail **(DKIM):**
  - Pass: Geeft de DKIM-controle aan op het doorgegeven bericht.
  - Fail (reden): Hiermee geeft u aan dat de DKIM-controle voor het bericht is mislukt en waarom. Bijvoorbeeld als het bericht niet is ondertekend of als de handtekening niet is gecontroleerd.
  - Geen: Geeft aan dat het bericht niet is ondertekend. Dit kan al of niet betekenen dat het domein een DKIM-record heeft of dat het DKIM-record geen resultaat oplevert. Het betekent in elk geval dat dit bericht niet is ondertekend.

- Domain-based Message Authentication, Reporting and Conformance **(DMARC):**
  - Pass: Geeft de DMARC-controle aan op het doorgegeven bericht.
  - Mislukt: Geeft aan dat de DMARC-controle voor het bericht is mislukt.
  - Bestguesspass: Geeft aan dat er geen DMARC TXT-record voor het domein bestaat, maar als er een was geweest, zou de DMARC-controle voor het bericht zijn geslaagd.
  - Geen: Geeft aan dat er geen DMARC TXT-record bestaat voor het verzendende domein in DNS.

*Samengestelde* verificatie: dit is een waarde die door Microsoft 365 wordt gebruikt om e-mailverificatie zoals SPF, DKIM en DMARC te combineren, om te bepalen of het bericht authentiek is. Het domein *Van:* van de e-mail wordt gebruikt als basis voor evaluatie.
