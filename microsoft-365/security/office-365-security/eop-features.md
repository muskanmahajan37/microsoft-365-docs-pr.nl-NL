---
title: EOP-functies
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: 599b8048-1056-457b-aae4-c063138fd319
description: De volgende tabel bevat een lijst met functies die beschikbaar zijn in Exchange Online Protection EOP-gehoste e-mailfilterservice.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: fa353b1e4e2560320b7e0fefae2dd302b35113b8
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624751"
---
# <a name="eop-features"></a>EOP-functies

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)

De volgende tabel bevat een lijst met functies die beschikbaar zijn in Exchange Online Protection EOP-e-mailfilterservice.

> [!TIP]
> De [Microsoft 365 roadmap voor bedrijven](https://www.microsoft.com/microsoft-365/roadmap?filters=O365) is een goede bron voor het vinden van informatie over toekomstige nieuwe functies. Zie voor een bredere weergave over welke functies beschikbaar zijn met de verschillende [EOP-abonnementsabonnementen Exchange Online Protection Servicebeschrijving.](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)

<br>

****

|Functie|Beschrijving|
|---|---|
|**Beveiliging tegen ongewenste e-mail**||
|Detectie van binnenkomende spam|Zie Bescherming tegen [spam in Microsoft 365.](anti-spam-protection.md) <p> In hybride omgevingen waarin EOP on-premises Exchange-postvakken beschermt, moet u regels voor e-mailstroom (ook wel transportregels genoemd) configureren in on-premises Exchange om de uitspraak voor EOP-spamfilters te vertalen, zodat de regel voor ongewenste e-mail het bericht naar de map Ongewenste e-mail kan verplaatsen. Zie [EOP configureren voor spam](/exchange/standalone-eop/configure-eop-spam-protection-hybrid)in de map Ongewenste e-mail in hybride omgevingen voor meer informatie.|
|Detectie van uitgaande spam|Uitgaande antispambeveiliging is altijd ingeschakeld als u de service gebruikt voor het verzenden van uitgaande e-mail. Zie Uitgaand spambeveiliging voor meer [informatie.](outbound-spam-controls.md)|
|Backscatterbeveiliging|Zie [Backscatter en EOP voor meer informatie.](backscatter-messages-and-eop.md)|
|Bulksgewijs filteren van e-mail|EOP gebruikt de bulkklachtsdrempel (BCL) om bulk-e-mailberichten als spam te markeren. Zie de volgende onderwerpen voor meer informatie: <p> [Wat is het verschil tussen ongewenste e-mail en bulkmail?](what-s-the-difference-between-junk-email-and-bulk-email.md) <p> [Bulkklachtsniveau (BCL) in EOP](bulk-complaint-level-values.md) <p> [Beleid tegen ongewenste e-mail configureren](configure-your-spam-filter-policies.md)|
|Lijsten met schadelijke URL-blokkeringen|EOP gebruikt verschillende URL-blokkeringslijsten om bekende schadelijke koppelingen in berichten te detecteren.|
|Bescherming tegen phishing|EOP bevat 750.000 domeinen van bekende spammers.|
|Beveiliging tegen adresvervalsing (spoofing)|Zie Bescherming tegen [spoofing voor meer informatie.](anti-spoofing-protection.md)|
|**Spambeheer**||
|Veilige afzenders en geblokkeerde afzenders configureren|Zie Lijsten met veilige [afzenders](create-safe-sender-lists-in-office-365.md) maken en Lijsten met geblokkeerde afzenders maken voor [meer informatie.](create-block-sender-lists-in-office-365.md)|
|Aangepaste antispambeleidsregels maken|Voor meer granulariteit kunt u aangepaste antispambeleidsregels maken en deze toepassen op opgegeven gebruikers, groepen of domeinen in uw organisatie. Aangepaste beleidsregels hebben altijd voorrang op het standaardbeleid, maar u kunt de prioriteit (dat wil zeggen de lopende volgorde) van uw aangepaste beleid wijzigen. Zie [Antispambeleid configureren](configure-your-spam-filter-policies.md) voor meer informatie.|
|De acties voor spam gefilterde berichten configureren|U kunt bijvoorbeeld berichten met inhoudsfilters verwijderen of verzenden naar de map Ongewenste e-mail of de quarantaine. Zie [Antispambeleid configureren](configure-your-spam-filter-policies.md) voor meer informatie.|
|Internationale spamfilters|U kunt antispamfiltering configureren om berichten te filteren die zijn geschreven in specifieke talen of verzonden uit specifieke landen of regio's. Zie [Antispambeleid configureren](configure-your-spam-filter-policies.md) voor meer informatie.|
|Spam beheren via Outlook of Outlook op internet (voorheen bekend als Outlook Web App)|Beheerders en eindgebruikers kunnen lijsten met veilige afzenders en geblokkeerde afzenderlijsten maken. Zie Instellingen voor ongewenste [e-mail in Outlook.](configure-junk-email-settings-on-exo-mailboxes.md#about-junk-email-settings-in-outlook) <p> Als u EOP gebruikt om on-premises postvakken te beveiligen, moet u adreslijstsynchronisatie gebruiken om ervoor te zorgen dat deze instellingen worden gesynchroniseerd met de service. Zie 'Adreslijstsynchronisatie gebruiken om e-mailgebruikers te beheren' in EOP-e-mailgebruikers beheren voor meer informatie over het instellen van [adreslijstsynchronisatie.](/exchange/standalone-eop/manage-mail-users-in-eop)|
|Rapporteer onwaar positieven en onwaar negatieven aan Microsoft.|Zie voor meer informatie [berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md).|
|Meldingen over spam door eindgebruikers|Zie Spammeldingen voor eindgebruikers [en](use-spam-notifications-to-release-and-report-quarantined-messages.md) [Spammeldingen](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)voor eindgebruikers configureren voor meer informatie.|
|Berichten weergeven, zoeken en beheren in de quarantaineportal.|Zie In quarantaine geplaatste berichten en bestanden beheren als beheerder [in EOP](manage-quarantined-messages-and-files.md) of Berichten in quarantaine zoeken en vrijgeven [als gebruiker voor meer informatie.](find-and-release-quarantined-messages-as-a-user.md)|
|Berichtenkoppen met spam in quarantaine weergeven|Nadat u de berichtkop in de quarantaine hebt weergegeven, kunt u de koptekst ook kopiëren en plakken in de berichtkopanalyse [om](https://mha.azurewebsites.net/) erachter te komen wat er met het bericht is gebeurd.|
|**Beveiliging tegen malware**||
|Beveiliging tegen malware met meerdere engines|Meerdere anti-malware-engines helpen onze klanten altijd automatisch te beschermen.|
|De mogelijkheid om malwarefilters uit te schakelen|U kunt malwarefiltering niet uitschakelen. We zijn van mening dat het helpen bij het bieden van een consistent en strikt beveiligingsniveau voor al onze klanten een essentieel onderdeel is van de uitgebreide strategie die nodig is om uw e-mailomgeving te beschermen. Hierdoor wordt malwarefilters automatisch ingeschakeld voor alle klanten.|
|Malware-inspectie van de bericht-body en bijlagen|De service controleert de actieve payload in de berichtbeslag en alle berichtbijlagen op malware.|
|Waarschuwingsmeldingen voor standaard- of aangepaste malware|U kunt een meldingsbericht verzenden naar afzenders of beheerders. Zie [Anti-malwarebeleid configureren](configure-anti-malware-policies.md)voor meer informatie.|
|Meldingen van geadresseerden|Plaats het bericht in quarantaine of plaats het bericht in quarantaine en lever het ook af met alle bijlagen die worden vervangen door één tekstbestand met standaard- of aangepaste tekst. Zie [Anti-malwarebeleid configureren](configure-anti-malware-policies.md)voor meer informatie.|
|Veelgebruikte bijlagefilters|U kunt een lijst met bestandstypen in- en aanpassen die altijd worden geacht malware te zijn. Zie Bescherming tegen [malware in EOP voor meer informatie.](anti-malware-protection.md)|
|Anti-spywarebeveiliging|Anti-malwarebeveiliging omvat bescherming tegen virussen en bescherming tegen spyware.|
|Aangepaste malwarefilterbeleidsregels maken|Voor meer granulariteit kunt u aangepaste malwarefilterbeleidsregels maken en toepassen op opgegeven gebruikers, groepen of domeinen in uw organisatie. Aangepaste beleidsregels hebben altijd voorrang op het standaardbeleid, maar u kunt de prioriteit (dat wil zeggen de lopende volgorde) van uw aangepaste beleid wijzigen. Zie [Anti-malwarebeleid configureren](configure-anti-malware-policies.md)voor meer informatie.|
|**E-mailroutering en verbindingslijnen**||
|Voorwaardelijke e-mailroutering|Zie voor meer informatie [scenario: voorwaardelijke routering voor e-mail in Exchange Online](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/conditional-mail-routing).|
|Opportunistisch of gedwongen TLS|Er is een opportunistische of gedwongen TLS beschikbaar met connectors. Als de TLS-verbinding mislukt, wordt een TLS-verbinding geprobeerd, maar wordt een SMTP-verbinding gebruikt. Force TLS dwingt TLS-verbindingen af, wat betekent dat het bericht wordt geweigerd als de TLS-verbinding mislukt. Zie Connectors instellen voor een veilige [e-mailstroom met een partnerorganisatie](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)voor meer informatie over TLS, beveiliging en connectors.|
|Regionale routering (de beperking van de e-mailstroom naar een bepaalde regio)|Zie de sectie 'EOP-datacenters' in Exchange Online Protection [overzicht voor meer informatie.](exchange-online-protection-overview.md)|
|Het hulpmiddel SMTP-connectiviteitscontrole|Zie E-mailstroom testen door uw verbindingslijnen te valideren voor Microsoft 365 meer informatie over het gebruik van dit hulpprogramma [om uw e-mailstroom te testen.](/exchange/mail-flow-best-practices/test-mail-flow)|
|Subdomeinen matchen|Zie E-mailstroom [in EOP](mail-flow-in-eop.md)voor meer informatie over het inschakelen van e-mailstroom van en naar subdomeinen van uw geaccepteerde domeinen.|
|**Regels voor e-mailstroom**||
|Filteren en acties op basis van beleid|Aangepaste beleidsregels zijn gebaseerd op Exchange regels voor e-mailstroom (ook wel transportregels genoemd). U kunt filteren op domein, trefwoord, bestandsnaam, bestandstype, onderwerpregel, berichttekst, afzender, geadresseerde, koptekst en IP-adres. Zie Regels voor [e-mailstroom (transportregels) in](mail-flow-rules-transport-rules-0.md)Exchange Online Protection.|
|Filteren op tekstpatronen|E-mailstroomregels kunnen een matrix of gewone expressies gebruiken om tekst aan te passen. U kunt ook één tekenreeks of een matrix met tekenreeksen gebruiken om veel berichteigenschappen aan te passen, zoals het adres, het onderwerp, de body of de namen van bijlagen. Zie Regels voor [e-mailstroom (transportregels) in](mail-flow-rules-transport-rules-0.md) Exchange Online Protection|
|Aangepaste woordenlijsten|E-mailstroomregels kunnen lange lijsten met tekst en trefwoorden bevatten, die dezelfde functionaliteit bieden als een aangepaste woordenlijst.|
|Beleidsregels per domein|Het bereik van een e-mailstroomregel kan worden aangepast aan de namen van afzenders of geadresseerden, IP-adresbereiken, adrestrefwoorden of patronen, groepslidmaatschap en andere voorwaarden.|
|Bijlage scannen|Er kunnen regels worden gemaakt om de bestandsnaam, extensie en inhoud van de bijlage te scannen.|
|Beleidsregelmeldingen verzenden naar de afzender|U kunt berichten weigeren en een rapport over niet-bezorging (ook wel een  NDR- of bouncebericht genoemd) naar de afzender verzenden via het bericht weigeren met de uitleg of Het bericht weigeren met de verbeterde **statuscodeactie.** Zie Acties voor [e-mailstroomregelacties in](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)Exchange Online.|
|Berichten omleiden of kopiëren|E-mailstroomregels kunnen omleiden, geadresseerden toevoegen via CC of BCC, alleen geadresseerden toevoegen en andere opties. Zie Acties voor [e-mailstroomregelacties in](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)Exchange Online.|
|Regelprioriteit voor meerdere regels aanpassen|Gebruik het Exchange beheercentrum om de volgorde te wijzigen waarin regels worden verwerkt.|
|Berichten filteren en vervolgens de routering of kenmerken van een bericht wijzigen|U kunt berichten filteren op basis van een groot aantal voorwaarden en vervolgens een reeks acties toepassen op elk bericht. Zie Regels voor [e-mailstroom (transportregels) in](mail-flow-rules-transport-rules-0.md)Exchange Online Protection.|
|Wijzig het betrouwbaarheidsniveau voor spam (SCL) van een bericht op regel.|U kunt een onderweg bericht controleren en er een betrouwbaarheidsniveau voor spam aan toewijzen op basis van de criteria die u kiest. Zie Regels voor e-mailstroom gebruiken om het betrouwbaarheidsniveau voor [spam (SCL)](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl)in berichten in te stellen voor meer informatie.|
|Berichtbijlagen controleren|U kunt de inhoud van een bijlage of de kenmerken van een bijgevoegd bestand bekijken en een actie definiëren die moet worden ondernomen op basis van wat er wordt gevonden. Zie E-mailstroomregels gebruiken om [berichtbijlagen in](/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments)Exchange Online.|
|**Beheer**||
|Webbeheer|De meeste functies worden beheerd in het [beveiligings- & compliancecentrum.](grant-access-to-the-security-and-compliance-center.md) <p> Voor andere functies is beheer vereist in Exchange beheercentrum (EAC). Zie het beheercentrum [Exchange beheercentrum in](/exchange/exchange-admin-center) Exchange Online of [Exchange beheercentrum in zelfstandige EOP](/exchange/standalone-eop/exchange-admin-center-eop)voor meer informatie.|
|Adreslijstsynchronisatie|Adreslijstsynchronisatie is beschikbaar via Azure Active Directory synchronisatiehulpmiddel. Zie de sectie Adreslijstsynchronisatie gebruiken om e-mailgebruikers te beheren in E-mailgebruikers [beheren in zelfstandige EOP](/exchange/standalone-eop/manage-mail-users-in-eop)voor meer informatie.|
|Directory Based Edge Blocking (DBEB)|Met de DBEB-functie kunt u berichten voor ongeldige geadresseerden bij de perimeter van het servicenetwerk weigeren. Met DBEB kunnen beheerders geadresseerden met e-mail toevoegen aan Microsoft 365 en alle berichten blokkeren die worden verzonden naar e-mailadressen die niet aanwezig zijn in Microsoft 365. Zie Directory Based Edge Blocking gebruiken om berichten te weigeren die naar ongeldige geadresseerden [zijn verzonden](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)voor meer informatie over het configureren van DBEB.|
|PowerShell|Volledige EOP-functionaliteit is beschikbaar in zelfstandige EOP PowerShell. Zie voor meer informatie [Exchange Online Protection PowerShell.](/powershell/exchange/exchange-online-protection-powershell)|
|**Rapportage en logboekregistratie**||
|Bericht traceren|Beheerders kunnen e-mailberichten volgen wanneer ze door de service lopen. U kunt bepalen of een gericht e-mailbericht is ontvangen, geweigerd, uitgesteld of bezorgd door de service. Op deze manier kunt u de vragen van uw gebruikers efficiënt beantwoorden, problemen met de e-mailstroom oplossen, beleidswijzigingen valideren en de noodzaak om contact op te nemen met de technische ondersteuning voor hulp, verminderen. Zie Bericht traceren in het Beveiligings- & [compliancecentrum voor meer informatie.](message-trace-scc.md)|
|Webrapporten|De e-mailbeveiligingsrapporten in het & compliancecentrum bieden berichtengegevens. U kunt bijvoorbeeld controleren hoeveel spam en malware wordt gedetecteerd of hoe vaak uw regels voor e-mailstromen worden afgestemd. Met deze interactieve rapporten kunt u snel een visueel rapport met overzichtsgegevens krijgen en inzoomen op details over afzonderlijke berichten, tot 90 dagen. Zie E-mailbeveiligingsrapporten gebruiken om [gegevens over malware, spam](/exchange/monitoring/use-mail-protection-reports)en regeldetecties weer te geven voor meer informatie.|
|Auditregistratie|Zie Controlerapporten [in](/exchange/security-and-compliance/exchange-auditing-reports/exchange-auditing-reports)Exchange Online.|
|**Service level agreements (SLA's) en ondersteuning**||
|Spameffectiviteit SLA|\> 99%|
|Fout-positieve ratio SLA|\< 1:250,000|
|Virusdetectie en het blokkeren van SLA|100% van bekende virussen|
|Maandelijkse uptime SLA|99.999%|
|Telefoon en web technische ondersteuning 24 uur per dag, zeven dagen per week|Zie Help en [ondersteuning voor EOP](help-and-support-for-eop.md)voor meer informatie over EOP-help- en ondersteuningsopties.|
|**Andere functies**||
|Een geo-redundant globaal netwerk van servers|EOP wordt uitgevoerd op een wereldwijd netwerk van datacenters die zijn ontworpen om de beste beschikbaarheid te bieden. Zie de sectie 'EOP-datacenters' in Exchange Online Protection [overzicht voor meer informatie.](exchange-online-protection-overview.md)|
|Bericht in de wachtrij wanneer de on-premises server geen e-mail kan accepteren|Berichten in uitstel blijven één dag in onze wachtrijen staan. Pogingen voor het opnieuw proberen van berichten zijn gebaseerd op de fout die we krijgen van het e-mailsysteem van de geadresseerde. Gemiddeld worden berichten elke 5 minuten opnieuw verzonden. Zie veelgestelde vragen [over EOP-berichten in de wachtrij, uitgestelde en niet-verzonden berichten voor meer informatie.](eop-queued-deferred-and-bounced-messages-faq.yml)|
|Office 365-berichtversleuteling beschikbaar als een invoegservice|Zie Versleuteling [in Office 365.](../../compliance/encryption.md)|
|
