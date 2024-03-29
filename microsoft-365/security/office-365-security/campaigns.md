---
title: Campagneweergaven in Microsoft Defender voor Office 365-abonnement
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: mcostea
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Meer informatie over campagneweergaven in Microsoft Defender voor Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e3c84b9e6253dd813ff930314fc2c1d0a947e94e
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204009"
---
# <a name="campaign-views-in-microsoft-defender-for-office-365"></a>Campagneweergaven in Microsoft Defender voor Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)

Campagneweergaven is een functie in Microsoft Defender voor Office 365 Plan 2 (bijvoorbeeld Microsoft 365 E5 of organisaties met een Defender voor Office 365-abonnement 2-invoegactie). Campagneweergaven in het Beveiligings- & compliancecentrum identificeert en categoriseert phishingaanvallen in de service. Campagneweergaven kunnen u helpen:

- Efficiënt onderzoeken en reageren op phishing-aanvallen.
- Beter inzicht in het bereik van de aanval.
- Toon waarde aan besluitvormers.

Met Campagneweergaven kunt u het grote beeld van een aanval sneller en completer zien dan een ander mens.

## <a name="what-is-a-campaign"></a>Wat is een campagne?

Een campagne is een gecoördineerde e-mail aanval op een of meer organisaties. E-mailaanvallen die referenties en bedrijfsgegevens stelen, zijn een grote en lucratieve industrie. Naarmate technologieën steeds meer moeite doen om aanvallen te stoppen, wijzigen aanvallers hun methoden in een poging om het succes te waarborgen.

Microsoft maakt gebruik van de enorme hoeveelheden anti-phishing-, antispam- en anti-malwaregegevens in de hele service om campagnes te identificeren. We analyseren en classificeren de aanvalsgegevens op basis van verschillende factoren. Bijvoorbeeld:

- **Aanvalsbron:** de bron-IP-adressen en e-maildomeinen van afzenders.
- **Berichteigenschappen:** De inhoud, stijl en toon van de berichten.
- **Geadresseerden van berichten:** hoe geadresseerden zijn gerelateerd. Bijvoorbeeld: geadresseerdedomeinen, functie voor geadresseerden (beheerders, leidinggevenden, enzovoort), bedrijfstypen (groot, klein, openbaar, privé, enzovoort) en bedrijfstakken.
- **Aanvalslading:** schadelijke koppelingen, bijlagen of andere payloads in de berichten.

Een campagne kan van korte duur zijn of meerdere dagen, weken of maanden duren met actieve en inactieve perioden. Er kan een campagne worden gestart tegen uw specifieke organisatie of uw organisatie maakt mogelijk deel uit van een grotere campagne voor meerdere bedrijven.

## <a name="campaign-views-in-the-security--compliance-center"></a>Campagneweergaven in het beveiligings- & compliancecentrum

Campagneweergaven zijn beschikbaar in het [Beveiligings- & compliancecentrum](https://protection.office.com) bij **Threat Management** \> **Campaigns** of rechtstreeks op <https://protection.office.com/campaigns> .

![Overzicht van campagnes in het beveiligings- & compliancecentrum](../../media/campaigns-overview.png)

U kunt ook naar Campagneweergaven gaan via:

- **Bedreigingsbeheer** \> **Explorer** \> **Weergave** \> **Campagnes**
- **Bedreigingsbeheer** \> **Explorer** \> **Weergave** \> **Alle e-mail** \> **Tabblad Campagne**
- **Bedreigingsbeheer** \> **Explorer** \> **Weergave** \> **Phish** \> **Tabblad Campagne**
- **Bedreigingsbeheer** \> **Explorer** \> **Weergave** \> **Malware** \> **Tabblad Campagne**

Als u toegang wilt tot campagneweergaven, moet u lid  zijn van de rollengroepen Organisatiebeheer, Beveiligingsbeheerder of Beveiligingslezer in het beveiligings- & Compliancecentrum. Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.

## <a name="campaigns-overview"></a>Overzicht van campagnes

Op de overzichtspagina ziet u informatie over alle campagnes.

Op het **standaardtabblad** Campagne wordt in **het gebied Campagnetype** een staafdiagram weergegeven met het aantal geadresseerden per dag. Standaard worden in de grafiek zowel **Phish-** als **Malware-gegevens** weergegeven.

> [!TIP]
> Als u geen campagnegegevens ziet, kunt u het datumbereik of de [filters wijzigen.](#filters-and-settings)

Op de rest van de overzichtspagina ziet u de volgende informatie op het **tabblad** Campagne:

- **Naam**

- **Voorbeeldonderwerp:** De onderwerpregel van een van de berichten in de campagne. Houd er rekening mee dat alle berichten in de campagne niet per se hetzelfde onderwerp hebben.

- **Targeted:** Het percentage zoals berekend door: (het aantal geadresseerden van de campagne in uw organisatie) / (het totale aantal geadresseerden in de campagne in alle organisaties in de service). Deze waarde geeft aan in welke mate de campagne alleen is gericht op uw organisatie (een hogere waarde) ten opzichte van andere organisaties in de service (een lagere waarde).

- **Type:** Deze waarde is **Phish** of **Malware.**

- **Subtype:** Deze waarde bevat meer informatie over de campagne. Bijvoorbeeld:
  - **Phish:** Waar beschikbaar, het merk dat wordt gepromoveerd door deze campagne. Bijvoorbeeld, `Microsoft` `365` , `Unknown` , , `Outlook` of `DocuSign` .
  - **Malware:** Bijvoorbeeld, `HTML/PHISH` of `HTML/<MalwareFamilyName>` .

  Waar beschikbaar, het merk dat wordt gepromoveerd door deze campagne. Wanneer de detectie wordt aangedreven door Defender voor Office 365-technologie, wordt het voorvoegsel **ATP toegevoegd** aan de subtypewaarde.

- **Geadresseerden:** het aantal gebruikers dat het doel van deze campagne is.

- **Postvak IN:** Het aantal gebruikers dat berichten van deze campagne heeft ontvangen in hun Postvak IN (niet bezorgd in de map Ongewenste e-mail).

- **Geklikt**: Het aantal gebruikers dat op de URL heeft geklikt of de bijlage in het phishingbericht heeft geopend.

- **Klikpercentage:** Het percentage zoals berekend met "**Klik op**  /  **Postvak IN**". Deze waarde is een indicator voor de effectiviteit van de campagne. Met andere woorden, als de geadresseerden het bericht konden identificeren als phishing en als ze niet op de payload-URL hebben geklikt.

  Klikpercentage **wordt** niet gebruikt in malwarecampagnes.

- **Bezocht:** Hoeveel gebruikers zijn daadwerkelijk door de payload-website. Als er **geklikte waarden** zijn, maar veilige koppelingen de toegang tot de website hebben geblokkeerd, is deze waarde nul.

Het **tabblad Campagne origin** toont de berichtbronnen op een kaart van de wereld.

### <a name="filters-and-settings"></a>Filters en instellingen

Boven aan de pagina Campagneweergaven vindt u verschillende filter- en query-instellingen om specifieke campagnes te vinden en te isoleren.

![Campagnefilters](../../media/campaign-filters-and-settings.png)

De meest eenvoudige filtering die u kunt doen, is de begindatum/tijd en de einddatum/tijd.

Als u de weergave verder wilt filteren, kunt u één eigenschap met meerdere waarden filteren door op de knop **Campagnetype** te klikken, uw selectie te maken en vervolgens op **Vernieuwen te klikken.**

De filterbare campagneeigenschappen die beschikbaar zijn in de knop **Campagnetype** worden in de volgende lijst beschreven:

- **Basis**:
  - **Campagnetype:** Selecteer **Malware** of **Phish.** Het wissen van de selecties heeft hetzelfde resultaat als het selecteren van beide.
  - **Campagnenaam**
  - **Subtype Campagne**
  - **Afzender**
  - **Geadresseerden**
  - **Afzenderdomein**
  - **Onderwerp**
  - **Bestandsnaam bijlage**
  - **Malwarefamilie**
  - **Tags:** Gebruikers of groepen waarvan de opgegeven gebruikerstag is toegepast (inclusief prioriteitsaccounts). Zie Gebruikerslabels voor meer [informatie over gebruikerslabels.](user-tags.md)
  - **Systeem overschrijven**
  - **Bezorgingsactie**
  - **Aanvullende actie**
  - **Richtingsrichting**
  - **Detectietechnologie**
  - **Oorspronkelijke bezorgingslocatie**
  - **Meest recente bezorgingslocatie**
  - **Systeem overschrijven**

- **Geavanceerd:**
  - **Internetbericht-id:** Beschikbaar in het **veld Bericht-id** in de berichtkoptekst. Een voorbeeldwaarde is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (let op de hoekhaken).
  - **Netwerkbericht-id:** een GUID-waarde die beschikbaar is in het veld **X-MS-Exchange-Organization-Network-Message-Id** in de berichtkoptekst.
  - **Ip-afzender**
  - **Bijlage SHA256:** Als u de hashwaarde SHA256 van een bestand in Windows wilt zoeken, voer u de volgende opdracht uit in een opdrachtprompt: `certutil.exe -hashfile "<Path>\<Filename>" SHA256` .
  - **Cluster-id**
  - **Waarschuwingsbeleids-id**
  - **ZAP URL-signaal**

- **URL's**:
  - **URL-domein**
  - **URL-domein en -pad**
  - **URL**
  - **URL-pad**
  - **Klik op vonnis**

Voor geavanceerdere filtering, inclusief filteren op meerdere eigenschappen, kunt u op de knop Geavanceerd **filter** klikken om een query te maken. Dezelfde campagne-eigenschappen zijn beschikbaar, maar met de volgende verbeteringen:

- U kunt op **Een voorwaarde toevoegen klikken om** meerdere voorwaarden te selecteren.
- U kunt de operator **En** of **Of** kiezen tussen voorwaarden.
- U kunt het **groepsitem Voorwaarde** onder aan de lijst met voorwaarden selecteren om complexe samengestelde voorwaarden te vormen.

Wanneer u klaar bent, klikt u op de **knop** Query.

Nadat u een eenvoudig of geavanceerd filter hebt gemaakt, kunt u het opslaan met behulp van **Query opslaan** of Query **opslaan als**. Wanneer u later terugkeert naar Campagneweergaven, kunt u een opgeslagen filter laden door op **Opgeslagen query-instellingen te klikken.**

Als u de grafiek of de lijst met campagnes wilt exporteren, klikt u op **Exporteren** en selecteert u **Grafiekgegevens exporteren** of **Campagnelijst exporteren.**

Als u een Abonnement op Microsoft Defender voor Eindpunt hebt, kunt u op **MDE-instellingen** klikken om de campagnesgegevens te verbinden of los te koppelen met Microsoft Defender voor Eindpunt. Zie Microsoft Defender voor [Office 365](integrate-office-365-ti-with-mde.md)integreren met Microsoft Defender voor Eindpunt voor meer informatie.

## <a name="campaign-details"></a>Campagnedetails

Wanneer u op de naam van een campagne klikt, worden de campagnedetails weergegeven in een flyout.

### <a name="campaign-information"></a>Campagnegegevens

Boven aan de weergave met campagnedetails zijn de volgende campagnegegevens beschikbaar:

- **ID:** de unieke campagne-id.

- **Gestart** **en beëindigd:** de begin- en einddatum van de campagne. Houd er rekening mee dat deze datums verder kunnen gaan dan de filterdatums die u hebt geselecteerd op de overzichtspagina.

- **Effect:** deze sectie bevat de volgende gegevens voor het datumbereikfilter dat u hebt geselecteerd (of die u selecteert in de tijdlijn):
  - Het totale aantal geadresseerden.
  - Het aantal berichten dat 'Postvak IN' was (dat wil zeggen, bezorgd in het Postvak IN, niet in de map Ongewenste e-mail).
  - Hoeveel gebruikers hebben in het phishingbericht op de URL-payload geklikt.
  - Hoeveel gebruikers hebben de URL bezocht.

- **Targeted:** Het percentage zoals berekend door: (het aantal geadresseerden van de campagne in uw organisatie) / (het totale aantal geadresseerden in de campagne in alle organisaties in de service). Deze waarde wordt berekend over de hele levensduur van de campagne en wordt niet gewijzigd op basis van datumfilters.

- Een interactieve tijdlijn van campagneactiviteit: de tijdlijn toont activiteiten gedurende de hele levensduur van de campagne. Standaard bevat het gearceerde gebied het datumbereikfilter dat u hebt geselecteerd in het overzicht. U kunt klikken en slepen om een specifiek begin- en eindpunt te selecteren, waarmee de gegevens worden gewijzigd die worden weergegeven in het gebied Impact en op de rest van de pagina, zoals beschreven in de volgende <u>secties.  </u>

Klik op de titelbalk op de knop Campagneopschrijven downloaden Om de campagnedetails te downloaden naar een **Word-document** (standaard met de naam ![ ](../../media/download-campaign-write-up-button.png) CampaignReport.docx). Houd er rekening mee dat de download details bevat over de hele levensduur van de campagne (niet alleen de filterdatums die u hebt geselecteerd).

![Campagnegegevens](../../media/campaign-details-campaign-info.png)

### <a name="campaign-flow"></a>Campagnestroom

In het midden van de weergave met campagnedetails worden belangrijke details over de campagne weergegeven in de sectie **Stroom** in een horizontaal stroomdiagram (bekend als een _Sankey-diagram)._ Met deze details krijgt u inzicht in de elementen van de campagne en de mogelijke impact in uw organisatie.

> [!TIP]
> De informatie die wordt weergegeven in het **stroomdiagram,** wordt bepaald door het gearceerde datumbereik in de tijdlijn, zoals beschreven in de vorige sectie.

![Campagnedetails die geen url-klikken van gebruikers bevatten](../../media/campaign-details-no-recipient-actions.png)

Als u de muisaanwijzer op een horizontale band in het diagram houdt, ziet u het aantal gerelateerde berichten (bijvoorbeeld berichten uit een bepaalde bron-IP, berichten uit het bron-IP-adres met het opgegeven afzenderdomein, enzovoort).

Het diagram bevat de volgende informatie:

- **Afzender-IPs**
- **Afzenderdomeinen**
- **Filter vonnissen:** Vonniswaarden zijn gerelateerd aan de beschikbare phishing- en spamfilters zoals beschreven in kopteksten van [antispamberichten.](anti-spam-message-headers.md) De beschikbare waarden worden in de volgende tabel beschreven:

  ****

  |Waarde|Uitspraak over spamfilter|Beschrijving|
  |---|---|---|
  |**Toegestaan**|`SFV:SKN` <p> `SFV:SKI`|Het bericht is gemarkeerd als geen spam en/of is niet gefilterd voordat het door spamfilters wordt geëvalueerd. Het bericht is bijvoorbeeld gemarkeerd als geen spam door een regel voor de e-mailstroom (ook wel een transportregel genoemd). <p> Het bericht heeft spamfilters om andere redenen overgeslagen. De afzender en geadresseerde lijken zich bijvoorbeeld in dezelfde organisatie te hebben.|
  |**Geblokkeerd**|`SFV:SKS`|Het bericht is gemarkeerd als spam voordat het werd geëvalueerd door spamfilters. Bijvoorbeeld door een regel voor de e-mailstroom.|
  |**Gedetecteerd**|`SFV:SPM`|Het bericht is gemarkeerd als spam door het spamfilter.|
  |**Niet gedetecteerd**|`SFV:NSPM`|Het bericht is gemarkeerd als geen spam door spamfilters.|
  |**Uitgebracht**|`SFV:SKQ`|Het bericht heeft spamfilters overgeslagen omdat het is vrijgegeven uit quarantaine.|
  |**Tenant toestaan**<sup>\*</sup>|`SFV:SKA`|Het bericht heeft spamfilters overgeslagen vanwege de instellingen in een antispambeleid. De afzender stond bijvoorbeeld in de lijst met toegestane afzenders of de lijst met toegestane domeinen.|
  |**Tenantblok**<sup>\*\*</sup>|`SFV:SKA`|Het bericht is geblokkeerd door spamfilters vanwege de instellingen in een antispambeleid. De afzender stond bijvoorbeeld in de lijst met toegestane afzenders of de lijst met toegestane domeinen.|
  |**Toestaan door gebruiker**<sup>\*</sup>|`SFV:SFE`|Het bericht heeft spamfilters overgeslagen omdat de afzender zich in de lijst Met veilige afzenders van een gebruiker had geplaatst.|
  |**Gebruikersblok**<sup>\*\*</sup>|`SFV:BLK`|Het bericht is geblokkeerd door spamfilters omdat de afzender zich in de lijst Geblokkeerde afzenders van een gebruiker heeft geplaatst.|
  |**ZAP**|n/a|Het bezorgde bericht is verplaatst naar de map Ongewenste [e-mail of quarantaine.](zero-hour-auto-purge.md) U configureert de actie in uw antispambeleid.|
  |

  <sup>\*</sup> Controleer uw antispambeleid, omdat het toegestane bericht waarschijnlijk is geblokkeerd door de service.

  <sup>\*\*</sup> Controleer uw antispambeleid, omdat deze berichten in quarantaine moeten worden geplaatst en niet moeten worden bezorgd.

- Bezorgingslocaties: U wilt waarschijnlijk berichten onderzoeken die zijn bezorgd bij geadresseerden (in het Postvak IN of in de map Ongewenste e-mail), zelfs als gebruikers niet op de payload-URL in het bericht hebben geklikt. U kunt ook de in quarantaine geplaatste berichten uit quarantaine verwijderen. Zie In quarantaine geplaatste [e-mailberichten in EOP](quarantine-email-messages.md)voor meer informatie.
  - **Verwijderde map**
  - **Laten vallen**
  - **Extern:** De ontvanger bevindt zich in uw on-premises e-mailorganisatie in hybride omgevingen.
  - **Mislukt**
  - **Doorgestuurd**
  - **Postvak IN**
  - **Map Ongewenste e-mail**
  - **Quarantaine**
  - **Unknown**

- **URL-klikken:** deze waarden worden beschreven in de volgende sectie.

> [!NOTE]
> In alle lagen die meer dan 10 items bevatten, worden de tien bovenste items weergegeven, terwijl de rest wordt gebundeld in **Andere** lagen.

#### <a name="url-clicks"></a>URL-klikken

Wanneer een phishingbericht wordt bezorgd in het Postvak IN of ongewenste e-mail van een geadresseerde, is er altijd een kans dat de gebruiker op de payload-URL klikt. Het niet klikken op de URL is een kleine maat voor het succes, maar u moet wel bepalen waarom het phishingbericht zelfs in het postvak is bezorgd.

Als een gebruiker in het phishingbericht op de payload-URL heeft geklikt, worden de acties weergegeven in het **gebied URL-klikken** van het diagram in de weergave campagnedetails.

- **Toegestaan**
- **BlockPage:** De ontvanger heeft op de payload-URL geklikt, maar [](safe-links.md) de toegang tot de schadelijke website is geblokkeerd door een beleid voor veilige koppelingen in uw organisatie.
- **BlockPageOverride:** De geadresseerde klikte op de payload-URL in het bericht, Veilige koppelingen probeerden deze te stoppen, maar ze mochten het blok overschrijven. Controleer uw [beleid voor veilige koppelingen](set-up-safe-links-policies.md) om te zien waarom gebruikers de uitspraak veilige koppelingen mogen overschrijven en door mogen gaan naar de schadelijke website.
- **PendingDetonationPage:** Veilige bijlagen in Microsoft Defender voor Office 365 is bezig met het openen en onderzoeken van de payload-URL in een virtuele computeromgeving.
- **PendingDetonationPageOverride:** De geadresseerde mocht de ontsteker van de payload overschrijven en de URL openen zonder te wachten op de resultaten.

### <a name="tabs"></a>Tabbladen

Met de tabbladen in de weergave campagnedetails kunt u de campagne verder onderzoeken.

> [!TIP]
> De informatie die op de tabbladen wordt weergegeven, wordt bepaald door het gearceerde datumbereik in de tijdlijn, zoals beschreven in de sectie [Campagnegegevens.](#campaign-information)

- **URL-klikken**: Als gebruikers niet op de payload-URL in het bericht hebben geklikt, is deze sectie leeg. Als een gebruiker op de URL kan klikken, worden de volgende waarden ingevuld:
  - **Gebruiker**<sup>\*</sup>
  - **URL**<sup>\*</sup>
  - **Klik op tijd**
  - **Klik op vonnis**

- **Afzender-IPs**
  - **Ip-afzender**<sup>\*</sup>
  - **Totaal aantal**
  - **Postvak IN**
  - **Niet postvak IN**
  - **SPF doorgegeven:** de afzender is geverifieerd door [het Sender Policy Framework (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md). Een afzender die niet door SPF-validatie komt, geeft een niet-genauteerde afzender aan of het bericht vervalst een legitieme afzender.

- **Afzenders**
  - **Afzender:** dit is het werkelijke afzenderadres in de opdracht SMTP MAIL FROM, wat niet noodzakelijkerwijs het E-mailadres Van: is dat gebruikers zien in hun e-mail clients.
  - **Totaal aantal**
  - **Postvak IN**
  - **Niet postvak IN**
  - **DKIM doorgegeven:** De afzender is geverifieerd door [Domain Keys Identified Mail (DKIM)](support-for-validation-of-dkim-signed-messages.md). Een afzender die niet door DKIM-validatie komt, geeft een niet-genauteerde afzender aan of het bericht vervalst een legitieme afzender.
  - **DMARC doorgegeven:** De afzender is geverifieerd door [DMARC (Domain-based Message Authentication, Reporting, and Conformance).](use-dmarc-to-validate-email.md) Een afzender die niet door DMARC-validatie komt, geeft een niet-genauteerde afzender aan of het bericht vervalst een legitieme afzender.

- **Bijlagen**
  - **Bestandsnaam**
  - **SHA256**
  - **Malwarefamilie**
  - **Totaal aantal**

- **URL**
  - **URL**<sup>\*</sup>
  - **Totaal aantal**

<sup>\*</sup> Als u op deze waarde klikt, wordt er een nieuw flyout geopend met meer informatie over het opgegeven item (gebruiker, URL, enzovoort) boven aan de weergave met campagnedetails. Als u wilt terugkeren naar de weergave met campagnedetails, klikt u op **Klaar** in de nieuwe flyout.

### <a name="buttons"></a>Knoppen

Met de knoppen in de weergave campagnedetails kunt u de kracht van Threat Explorer gebruiken om de campagne verder te onderzoeken.

- **Campagne verkennen:** hiermee opent u een nieuw zoektabblad Threat Explorer met de **waarde Campagne-id** als zoekfilter.
- **Berichten met Postvak IN verkennen:** hiermee opent u een nieuw zoektabblad Threat Explorer met de locatie **Campagne-id** en **Bezorging: Postvak IN** als zoekfilter.
