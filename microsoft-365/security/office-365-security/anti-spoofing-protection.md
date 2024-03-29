---
title: Beveiliging tegen adresvervalsing
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
search.appverid:
- MET150
ms.assetid: d24bb387-c65d-486e-93e7-06a4f1a436c0
ms.collection:
- M365-security-compliance
- Strat_O365_IP
- m365initiative-defender-office365
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
localization_priority: Priority
description: Beheerders kunnen meer informatie krijgen over de functies tegen adresvervalsing die beschikbaar zijn in EOP (Exchange Online Protection) die kunnen beschermen tegen phishing-aanvallen van vervalste afzenders en domeinen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7680c2f4eae54aa53eba72b328baf1bf92fbcf98
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537965"
---
# <a name="anti-spoofing-protection-in-eop"></a>Beveiliging tegen adresvervalsing in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

In Microsoft 365-bedrijven met postvakken in Exchange Online of EOP-bedrijven (standalone Exchange Online Protection) zonder Exchange Online-postvakken bevat EOP functies om uw organisatie te beschermen tegen gespoofte (vervalste) afzenders.

Wanneer het gaat om het beschermen van haar gebruikers, neemt Microsoft de dreiging van phishing zeer serieus. Spoofing is een gangbare techniek die door hackers wordt gebruikt. **Vervalste berichten lijken afkomstig te zijn van iemand of ergens anders dan de daadwerkelijke bron.** Deze techniek wordt vaak gebruikt in phishing-campagnes die zijn ontworpen om gebruikersgegevens te verkrijgen. De anti-spoofing-technologie in EOP onderzoekt specifiek vervalsing van de Van-header in de berichttekst (gebruikt om de afzender van het bericht weer te geven in e-mailclients). Wanneer EOP een hoge mate van vertrouwen heeft dat de Van-header is vervalst, wordt het bericht geïdentificeerd als vervalst.

De volgende anti-spoofing-technologieën zijn beschikbaar in EOP:

- **E-mailverificatie**: een integraal onderdeel van elke poging tot spoofing is het gebruik van e-mailverificatie (ook bekend als e-mailvalidatie) door SPF-, DKIM- en DMARC-records in DNS. U kunt deze records configureren voor uw domeinen, zodat doel-e-mailsystemen de geldigheid kunnen controleren van berichten die beweren afkomstig te zijn van afzenders in uw domeinen. Voor inkomende berichten vereist Microsoft 365 e-mailverificatie voor de domeinen van de afzender. Zie [E-mailverificatie in Microsoft 365](email-validation-and-authentication.md) voor meer informatie.

  EOP analyseert en blokkeert berichten die niet kunnen worden geverifieerd door de combinatie van standaardmethoden voor e-mailverificatie en reputatietechnieken van de afzender.

  ![EOP anti-spoofing-technieken](../../media/eop-anti-spoofing-protection.png)

- **Inzicht in adresvervalsingsanalyse**: Vervalste berichten van afzenders beoordelen in interne en externe domeinen tijdens de laatste 7 dagen, en deze verzenders toestaan of blokkeren. Zie [Inzicht in adresvervalsingsanalyse in EOP](learn-about-spoof-intelligence.md) voor meer informatie.

- **Vervalste afzenders toestaan of blokkeren in de lijst Tenant toestaan/blokkeren**: wanneer u het oordeel in inzicht in adresvervalsingsanalyse overschrijft, wordt de vervalste afzender een handmatige vermelding voor toestaan of blokkeren die alleen wordt weergegeven op het tabblad **Adresvervalsing gebruiken** in de lijst Tenant toestaan/blokkeren. U kunt ook handmatig vermeldingen maken voor toestaan of blokkeren voor vervalste afzenders voordat deze worden gedetecteerd door adresvervalsingsanalyse. Zie voor meer informatie [Lijst Tenant toestaan/blokkeren beheren in EOP](tenant-allow-block-list.md).

- **Anti-phishingbeleid**: in EOP bevat anti-phishingbeleid de volgende instellingen voor anti-adresvervalsing (spoofing):
  - Adresvervalsingsanalyse in- of uitschakelen.
  - Schakel identificatie met niet-geverifieerde afzender in Outlook in of uit.
  - Geef de actie op voor geblokkeerde vervalste afzenders.

  Zie [Instellingen voor adresvervalsing in anti-phishingbeleid](set-up-anti-phishing-policies.md#spoof-settings) voor meer informatie.

  **Opmerking**: Anti-phishingbeleid in Microsoft Defender voor Office 365 bevatten extra beveiligingen, waaronder **imitatie** beveiliging. Zie voor meer informatie [Exclusieve instellingen in anti-phishingbeleid in Microsoft Defender voor Office 365](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).

- **Rapport met detectie van adresvervalsing**: Voor meer informatie, zie [Rapport voor adresvervalsing](view-email-security-reports.md#spoof-detections-report).

  **Opmerking**: Defender voor Office 365-organisaties kunnen ook realtimedetecties (Abonnement 1) of Bedreigingsverkenner (Abonnement 2) gebruiken om informatie over phishingpogingen te bekijken. Zie voor meer informatie [Dreigingsonderzoek en -reactie in Microsoft 365](office-365-ti.md).

## <a name="how-spoofing-is-used-in-phishing-attacks"></a>Hoe spoofing wordt gebruikt in phishing-aanvallen

Spoofberichten hebben de volgende negatieve gevolgen voor gebruikers:

- **Vervalste berichten misleiden gebruikers**: een vervalst bericht kan de ontvanger misleiden tot het klikken op een link en het opgeven van hun inloggegevens, het downloaden van malware of het beantwoorden van een bericht met gevoelige inhoud (bekend als een zakelijk e-mail compromis of BEC).

  In het volgende voorbeeld ziet u een phishingbericht met een vervalste afzender msoutlook94@service.outlook.com:

  ![Phishingbericht dat zich voordoet als service.outlook.com](../../media/1a441f21-8ef7-41c7-90c0-847272dc5350.jpg)

  Dit bericht is niet afkomstig van service.outlook.com, maar de aanvaller heeft het **Van**-veld in de header vervalst om het er zo uit te laten zien. Dit was een poging om de ontvanger te misleiden om op de link voor het **wijzigen van uw wachtwoord** te klikken en hun inloggegevens op te geven.

  Hieronder ziet u een voorbeeld van BEC waarin het vervalste e-mail domein contoso.com wordt gebruikt:

  ![Phishingboodschap: inbreuk op zakelijke e-mail](../../media/da15adaa-708b-4e73-8165-482fc9182090.jpg)

  Het bericht ziet er legitiem uit, maar de afzender is vervalst.

- **Gebruikers verwarren echte berichten met nepberichten**: zelfs gebruikers die op de hoogte zijn van phishing kunnen moeite hebben om de verschillen tussen echte berichten en vervalste berichten te zien.

  Het volgende bericht is een voorbeeld van een echt wachtwoordherstelbericht van het Microsoft Beveiliging-account:

  ![Legitiem Microsoft-wachtwoordherstelbericht](../../media/58a3154f-e83d-4f86-bcfe-ae9e8c87bd37.jpg)

  Het bericht was echt van Microsoft afkomstig, maar gebruikers hebben geleerd om achterdochtig te zijn. Omdat het moeilijk is om het verschil te zien tussen een echt wachtwoordherstelbericht en een nepbericht, kunnen gebruikers het bericht negeren, als spam rapporteren of het bericht onnodig aan Microsoft als phishing melden.

## <a name="different-types-of-spoofing"></a>Verschillende typen spoofing

Microsoft maakt onderscheid tussen twee verschillende typen adresvervalsingberichten:

- **Intra-org-spoofing**: ook bekend als _Self-to-self_-spoofing. Bijvoorbeeld:

  - De afzender en ontvanger bevinden zich in hetzelfde domein:
    > Van: chris@contoso.com <br> Aan: michelle@contoso.com

  - De afzender en de ontvanger bevinden zich in de subdomeinen van hetzelfde domein:
    > Van: laura@marketing.fabrikam.com <br> Aan: julia@engineering.fabrikam.com

  - De afzender en de ontvanger bevinden zich in verschillende domeinen van dezelfde organisatie (dat wil zeggen: beide domeinen zijn geconfigureerd als [geaccepteerde domeinen](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in dezelfde organisatie):
    > Van: sender @ microsoft.com <br> Aan: geadresseerde @ bing.com

    In de e-mailadressen worden spaties gebruikt om kopiëren door spambots te voorkomen.

  Berichten waarvoor [samengestelde authenticatie](email-validation-and-authentication.md#composite-authentication) is mislukt vanwege adresvervalsing tussen domeinen bevatten de volgende waarden in de koppen:

  `Authentication-Results: ... compauth=fail reason=6xx`

  `X-Forefront-Antispam-Report: ...CAT:SPOOF;...SFTY:9.11`

  - `reason=6xx` geeft adresvervalsing binnen de organisatie aan.

  - SFTY geeft het beveiligingsniveau van het bericht. 9 geeft phishing aan, .11 geeft aan dat er sprake is van intra-org-spoofing.

- **spoofing tussen domeinen**: de afzender- en ontvangerdomeinen zijn verschillend en hebben geen relatie met elkaar (ook wel externe domeinen genoemd). Bijvoorbeeld:
    > Van: chris@contoso.com <br> Aan: michelle@tailspintoys.com

  Berichten waarvoor de [samengestelde verificatie](email-validation-and-authentication.md#composite-authentication) is mislukt vanwege adresvervalsing tussen domeinen bevatten de volgende waarden in de koppen:

  `Authentication-Results: ... compauth=fail reason=000/001`

  `X-Forefront-Antispam-Report: ...CAT:SPOOF;...SFTY:9.22`

  - `reason=000` betekent dat het bericht niet is geslaagd voor expliciete e-mailverificatie. `reason=001` betekent dat het bericht niet is geslaagd voor impliciete e-mailverificatie.

  - `SFTY` is het beveiligingsniveau van het bericht. 9 geeft phishing aan, .22 geeft aan dat er sprake is van spoofing tussen domeinen.

> [!NOTE]
> Als u een bericht hebt gekregen zoals ***compauth=fail reason=###** _ en u informatie wilt over samengestelde verificatie (compauth) en de waarden met betrekking tot spoofing, gaat u naar [_Anti-spamberichtkoppen in Microsoft 365*](anti-spam-message-headers.md). Of ga rechtstreeks naar de [*reden*](anti-spam-message-headers.md) codes.

Zie voor informatie over DMARC [DMARC gebruiken om e-mail in Microsoft 365 te valideren](use-dmarc-to-validate-email.md).

## <a name="problems-with-anti-spoofing-protection"></a>Problemen met bescherming tegen spoofing

Mailinglijsten (ook wel discussielijsten genoemd) staan erom bekend dat ze problemen ondervinden met antispoofing vanwege de manier waarop ze berichten doorsturen en wijzigen.

Stel dat Gabriela Laureano (glaureano@contoso.com) geïnteresseerd is in vogels spotten en lid wordt van de mailinglijst vogelspotters@fabrikam.com. Ze stuurt het volgende bericht naar de lijst:

> **Van:** 'Gabriela Laureano' \<glaureano@contoso.com\> <br> **Aan:** Vogelaars discussielijst \<birdwatchers@fabrikam.com\> <br> **Betreft:** Geweldig treffen van blauwe gaaien op de top van de Wageningse Berg deze week <p> Wil iemand deze week het uitzicht vanop Mount Rainier bekijken?

De mailinglijstserver ontvangt het bericht, wijzigt de inhoud ervan en speelt het opnieuw af voor de leden van de lijst. Het opnieuw afgespeelde bericht heeft hetzelfde Van-adres (glaureano@contoso.com), maar er wordt een label aan de onderwerpregel toegevoegd en er wordt een voettekst onder aan het bericht toegevoegd. Dit type wijziging komt veel voor in mailinglijsten en kan leiden tot fout-positieven voor spoofing.

> **Van:** 'Gabriela Laureano' \<glaureano@contoso.com\> <br> **Aan:** Vogelaars discussielijst \<birdwatchers@fabrikam.com\> <br> **Betreft:** [VOGELSPOTTERS] Geweldig treffen van blauwe gaaien op de top van de Wageningse Berg deze week <p> Wil iemand deze week het uitzicht vanop Mount Rainier bekijken? <p> Dit bericht is verzonden naar de Vogelspotters-discussielijst. U kunt zich op elk moment weer afmelden.

Voer de volgende stappen uit, afhankelijk van of u de mailinglijst beheert, om ervoor te zorgen dat mailinglijstberichten anti-spoofingcontroles doorstaan:

- Uw organisatie is eigenaar van de mailinglijst:

  - Bekijk de veelgestelde vragen op DMARC.org: [Ik heb een adressenlijst en ik wil samenwerken met DMARC, wat moet ik doen?](https://dmarc.org/wiki/FAQ#I_operate_a_mailing_list_and_I_want_to_interoperate_with_DMARC.2C_what_should_I_do.3F)

  - Lees de instructies in dit blogbericht: [Een tip voor adressenlijstbeheerders om samen te werken met DMARC om fouten te voorkomen](/archive/blogs/tzink/a-tip-for-mailing-list-operators-to-interoperate-with-dmarc-to-avoid-failures).

  - Als u updates op de adressenlijstserver wilt installeren om ARC te ondersteunen, raadpleegt u <http://arc-spec.org>.

- Uw organisatie is niet de eigenaar van de mailinglijst:

  - Vraag de beheerder van de mailinglijst om e-mailverificatie te configureren voor het domein waar vandaan de mailinglijst doorstuurt.

    Wanneer voldoende afzenders aan domeineigenaren antwoorden dat ze e-mailverificatierecords moeten instellen, zet dit hen aan tot actie. Hoewel Microsoft ook met domeineigenaren samenwerkt om de vereiste records te publiceren, is het nog beter wanneer afzonderlijke gebruikers erom vragen.

  - Maak regels voor postvak IN in uw e-mailclient om berichten te verplaatsen naar het postvak IN. U kunt ook uw beheerders vragen overschrijvingen te configureren zoals is beschreven in [Inzicht in adresvervalsingsanalyse in EOP](learn-about-spoof-intelligence.md) en [Lijst Tenant toestaan/blokkeren beheren](tenant-allow-block-list.md).

  - U kunt met Microsoft 365 een ondersteuningsticket maken om een override voor de adressenlijst te maken om deze als legitiem te beschouwen. Raadpleeg voor meer informatie [Contact opnemen met ondersteuning voor zakelijke producten - Hulp voor beheerders](../../business-video/get-help-support.md).

Als al het andere niet lukt, kunt u het bericht als fout-positief melden aan Microsoft. Zie voor meer informatie [berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md).

U kunt ook contact opnemen met uw beheerder die een ondersteuningsticket kan genereren bij Microsoft. Het technische team van Microsoft zal onderzoeken waarom het bericht als spoof is gemarkeerd.

## <a name="considerations-for-anti-spoofing-protection"></a>Overwegingen bij de bescherming tegen spoofing

Als u een beheerder bent die momenteel berichten naar Microsoft 365 stuurt, moet u ervoor zorgen dat uw e-mail correct is geverifieerd. Anders kan het als spam of phishing worden gemarkeerd. Zie voor meer informatie [oplossingen voor legitieme afzenders die niet-geverifieerde e-mail verzenden](email-validation-and-authentication.md#solutions-for-legitimate-senders-who-are-sending-unauthenticated-email).

Afzenders in de lijst met veilige afzenders van een afzonderlijke gebruiker (of beheerder) slaan onderdelen van de filterstack over, met inbegrip van de beveiliging van spoofberichten. Zie [Outlook-lijsten met veilige afzenders](create-safe-sender-lists-in-office-365.md#use-outlook-safe-senders) voor meer informatie.

Beheerders moeten (indien mogelijk) voorkomen dat toegestane afzenders of toegestane domeinlijsten gebruikt worden. Met deze afzenders worden alle spam, spoofing en phishing-bescherming en de verificatie van de afzender (SPF, DKIM, DMARC) overgeslagen. Zie [lijst met toegestane afzenders of toegestane domein lijsten gebruiken](create-safe-sender-lists-in-office-365.md#use-allowed-sender-lists-or-allowed-domain-lists)voor meer informatie.
