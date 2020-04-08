---
title: Reageren op een gehackt e-mailaccount in Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- M365-security-compliance
ms.custom: TopSMBIssues
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: Lees hoe u een gehackt e-mailaccount in Office 365 kunt herkennen en hierop kunt reageren
ms.openlocfilehash: b19d48046834e3f1387490774babb40dcbd92acc
ms.sourcegitcommit: 9224a7a5886c0c5fa0bc12bd9f7234a0eba90023
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/02/2020
ms.locfileid: "42811331"
---
# <a name="responding-to-a-compromised-email-account-in-office-365"></a>Reageren op een gehackt e-mailaccount in Office 365

**Overzicht** Lees hoe u een gehackt e-mailaccount in Office 365 kunt herkennen en hierop kunt reageren.

## <a name="what-is-a-compromised-email-account-in-office-365"></a>Wat is een gehackt e-mailaccount in Office 365?

Toegang tot Office 365-postvakken, -gegevens en andere services wordt geregeld door het gebruik van referenties, zoals een gebruikersnaam en wachtwoord of pincode. Als iemand anders dan de bedoelde gebruiker die referenties steelt, worden de gestolen referenties geacht te zijn gehackt. Hiermee kan de hacker zich aanmelden als de oorspronkelijke gebruiker en illegale acties uitvoeren.
Met de gestolen referenties kan de hacker toegang krijgen tot het Office 365-postvak, SharePoint-mappen of bestanden in de OneDrive van de gebruiker. Een actie die vaak wordt gezien, is dat de hacker e-mails verzendt als de oorspronkelijke gebruiker naar geadresseerden binnen en buiten de organisatie. Wanneer de hacker gegevens naar externe geadresseerden stuurt, wordt dit gegevensexfiltratie genoemd.

## <a name="symptoms-of-a-compromised-office-365-email-account"></a>Symptomen van een gehackt Office 365-e-mailaccount

Gebruikers kunnen ongebruikelijke activiteiten in hun Office 365-postvakken opmerken en melden. Hier volgen enkele veelvoorkomende symptomen:

- Verdachte activiteiten, zoals ontbrekende of verwijderde e-mails.

- Het is mogelijk dat andere gebruikers e-mails ontvangen van het gehackte account, zonder dat de desbetreffende e-mail aanwezig is in de map met **Verzonden items** van de afzender.

- De aanwezigheid van regels voor Postvak IN die niet zijn aangemaakt door de bedoelde gebruiker of door de beheerder. Met deze regels kunnen e-mails automatisch worden doorgestuurd naar onbekende adressen of worden deze verplaatst naar de mappen met **Notities**, **Ongewenste e-mail** of **RSS-abonnementen**.

- De weergavenaam van de gebruiker kan worden gewijzigd in de algemene adreslijst.

- Het postvak van de gebruiker is geblokkeerd voor het verzenden van e-mails.

- De mappen met Verzonden of Verwijderde items in Microsoft Outlook of de webversie van Outlook (voorheen bekend als Outlook Web App) bevatten berichten die vaak worden gestuurd door gehackte accounts, zoals "Ik zit vast in Londen, stuur geld".

- Ongebruikelijke profielwijzigingen, zoals de naam, het telefoonnummer of de postcode zijn bijgewerkt.

- Ongebruikelijke referentiewijzigingen, zoals meerdere wachtwoordwijzigingen.

- Het doorsturen van e-mail is onlangs toegevoegd.

- Er is onlangs een ongebruikelijke handtekening toegevoegd, zoals een valse bankhandtekening of een handtekening voor voorgeschreven medicijnen.

Als een gebruiker een van de bovenstaande problemen meldt, moet u nader onderzoek doen. Het Microsoft 365-beveiligings- en compliancecentrum en de Azure-portal bieden hulpmiddelen voor het onderzoeken van de activiteiten van een gebruikersaccount waarvan u vermoedt dat het niet meer betrouwbaar is.

- **Geïntegreerde Office 365-auditlogboeken in het Beveiligings- en compliancecentrum**: Bekijk alle activiteiten van het verdachte account door de resultaten te filteren op het datumbereik van vlak voordat de verdachte activiteiten zich voordeden tot nu. Filter niet op de activiteiten tijdens het zoeken.

- **Auditlogboeken voor Office 365-beheerder in het Exchange-beheercentrum (EAC)**: In Exchange Online kunt u het Exchange-beheercentrum gebruiken om vermeldingen te zoeken en weer te geven in het auditlogboek van de beheerder. In het auditlogboek van de beheerder worden specifieke acties vastgelegd, gebaseerd op Exchange Online PowerShell-cmdlets, die worden uitgevoerd door beheerders en gebruikers aan wie beheerdersbevoegdheden zijn toegewezen. Vermeldingen in het auditlogboek van de beheerder bieden informatie over welke cmdlet is uitgevoerd, welke parameters zijn gebruikt, wie de cmdlet heeft uitgevoerd en welke objecten zijn beïnvloed.

- **Azure AD-aanmeldingslogboeken en andere risicorapporten in de Azure AD-portal**: Bekijk de waarden in deze kolommen:

  - Controleer het IP-adres

  - aanmeldingslocaties

  - aanmeldingstijden

  - geslaagde of misluke aanmeldingen

## <a name="how-to-secure-and-restore-email-function-to-a-suspected-compromised-office-365-account-and-mailbox"></a>E-mailfunctionaliteit van een vermoedelijk gehackt Office 365-account en -postvak beveiligen en herstellen

> [!VIDEO https://videoplayercdn.osi.office.net/hub/?csid=ux-cms-en-us-msoffice&uuid=RE2jvOb&AutoPlayVideo=false]

Zelfs nadat u opnieuw toegang heeft gekregen tot uw account, is het mogelijk dat de hacker verborgen toegangsmogelijkheden heeft aangemaakt waardoor de hacker beheer van het account kan hervatten.

U moet de volgende stappen uitvoeren om weer toegang te krijgen tot uw account. Het is verstandig dit zo snel mogelijk te doen, zodat de hacker niet opnieuw controle over uw account kan krijgen. Met deze stappen verwijdert u alle verborgen toegangsmogelijkheden die de hacker mogelijk aan uw account heeft toegevoegd. Nadat u deze stappen hebt uitgevoerd, raden we u aan een virusscan uit te voeren om er zeker van te zijn dat uw computer niet gehackt is.

### <a name="step-1-reset-the-users-password"></a>Stap 1 Stel het gebruikerswachtwoord opnieuw in

> [!WARNING]
> Stuur het nieuwe wachtwoord niet via e-mail naar de bedoelde gebruiker, aangezien de hacker op dit moment nog steeds toegang tot het postvak heeft.

1. Volg de procedures voor het opnieuw instellen van een zakelijk Office 365-wachtwoord van iemand anders in [Zakelijk Office 365-wachtwoorden opnieuw instellen](https://docs.microsoft.com/office365/admin/add-users/reset-passwords)

**Opmerkingen**:

- Zorg ervoor dat het wachtwoord sterk is en dat het hoofdletters en kleine letters, tenminste één cijfer en tenminste één speciaal teken bevat.

- Gebruik uw laatste vijf wachtwoorden niet opnieuw. Hoewel u volgens de vereisten voor wachtwoordgeschiedenis een recenter wachtwoord opnieuw kunt gebruiken, is het verstandig om iets te selecteren dat de hacker niet kan raden.

- Als uw identiteit op locatie federatief is met Office 365, moet u uw wachtwoord op locatie wijzigen en uw beheerder op de hoogte stellen van de aanval.

> [!TIP]
> We raden u ten zeerste aan om meervoudige verificatie in te schakelen om een inbreuk te voorkomen, met name voor accounts met beheerdersbevoegdheden.  [Hier](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication) vindt u meer informatie over meervoudige verificatie.

### <a name="step-2-remove-suspicious-email-forwarding-addresses"></a>Stap 2 E-mailadressen verwijderen die verdachte mails doorsturen

1. Open het **Microsoft 365-beheercentrum > Actieve gebruikers**.

2. Zoek het gebruikersaccount in kwestie en vouw **E-mail instellingen** uit.

3. Kies **Bewerken** bij **E-mail doorsturen**.

4. Verwijder alle verdachte doorstuuradressen.

### <a name="step-3-disable-any-suspicious-inbox-rules"></a>Stap 3 Alle verdachte regels voor Postvak IN uitschakelen

1. Meld u aan bij het postvak van de gebruiker met de webversie van Outlook.

2. Klik op het tandwielpictogram en klik op **Mail**.

3. Klik op **Regels voor postvak in en opruimen** en controleer de regels.

4. Blokkeer of verwijder alle verdachte regels.

### <a name="step-4-unblock-the-user-from-sending-mail"></a>Stap 4 De gebruiker opnieuw toestemming geven om mail te verzenden

Als het vermoedelijk gehackte postvak op illegale wijze is gebruikt voor het verzenden van ongewenste e-mail, is de kans groot dat het verzenden van mails vanuit dit postvak is geblokkeerd.

Om ervoor te zorgen dat er weer mails kunnen worden verzonden vanuit dit postvak, volgt u de procedures in [Een gebruiker verwijderen uit de portal voor gebruikers met beperkte rechten na het verzenden van ongewenste e-mail](removing-user-from-restricted-users-portal-after-spam.md).

### <a name="step-5-optional-block-the-user-account-from-signing-in"></a>Stap 5 Optioneel: Aanmelden bij het gebruikersaccount blokkeren

> [!IMPORTANT]
> U kunt ervoor zorgen dat er niet meer ingelogd kan worden bij het vermoedelijk gehackte account tot u ervan overtuigd bent dat het veilig is om de blokkering op te heffen.

1. Ga naar het Microsoft 365-beheercentrum.

2. Selecteer **Gebruikers** in het Microsoft 365-beheercentrum.

3. Selecteer de werknemer die u wilt blokkeren en kies **Bewerken** naast **Aanmeldstatus** in het gebruikersdeelvenster.

4. Kies in het deelvenster **Aanmeldstatus** de optie **Aanmelding geblokkeerd** en klik vervolgens op **Opslaan**.

5. Vouw in het Beheercentrum, in het navigatievenster linksonder, **Beheercentra** uit en selecteer **Exchange**.

6. Ga in het Exchange-beheercentrum naar **Ontvangers > Postvakken**.

7. Selecteer de gebruiker en klik op de pagina met gebruikerseigenschappen onder **Mobiele apparaten** op **Exchange ActiveSync uitschakelen** en **OWA voor apparaten uitschakelen** en klik bij beide items op **Ja**.

8. Klik onder **E-mailconnectiviteit** op **Uitschakelen** en klik op **Ja**.

### <a name="step-6-optional-remove-the-suspected-compromised-account-from-all-administrative-role-groups"></a>Stap 6 Optioneel: Verwijder het vermoedelijk gehackte account uit alle beheerdersrollen.

> [!NOTE]
> Het lidmaatschap van de administratieve rolgroep kan worden hersteld nadat het account is beveiligd.

1. Meld u met een algemeen beheerdersaccount aan bij het Microsoft 365-beheercentrum en open **Actieve gebruikers**.

2. Zoek het vermoedelijk gehackte account en controleer handmatig of er beheerdersrollen aan het account zijn toegewezen.

3. Open het **Beveiligings- en compliancecentrum**.

4. Klik op **Machtigingen**.

5. Bekijk de rolgroepen handmatig om te zien of het vermoedelijk gehackte account lid is van een van deze groepen.  Zo ja:

   a. Klik op de rolgroep en klik op **Rolgroep bewerken**.

   b. Klik op **Leden kiezen** en **Bewerken** om de gebruiker uit de rolgroep te verwijderen.

6. Open het **Exchange-beheercentrum**.

7. Klik op **Machtigingen**.

8. Bekijk de rolgroepen handmatig om te zien of het vermoedelijk gehackte account lid is van een van deze groepen. Zo ja:

   a. Klik op de rolgroep en klik op **Bewerken**.

   b. Gebruik de **leden**-sectie om de gebruiker uit de rolgroep te verwijderen.

### <a name="step-7-optional-additional-precautionary-steps"></a>Stap 7 Optioneel: Extra voorzorgsmaatregelen

1. Zorg ervoor dat u uw verzonden items controleert. Het is verstandig om de personen in uw contactenlijst op de hoogte te stellen van het feit dat uw account is gehackt. De hacker heeft hen mogelijk om geld gevraagd, spoofing, bijvoorbeeld dat u zich in een ander land bevindt en geld nodig heeft, of het kan zijn dat de hacker een virus heeft verstuurd om ook hun computers te overnemen.

2. Een andere service die gebruik heeft gemaakt van dit Exchange-account als alternatief e-mailaccount kan ook gehackt zijn. Voer deze stappen eerst uit voor uw Office 365-abonnement en voer ze vervolgens uit voor uw andere accounts.

3. Zorg ervoor dat uw contactgegevens, zoals telefoonnummers en adressen, correct zijn.

## <a name="secure-office-365-like-a-cybersecurity-pro"></a>Office 365 beveiligen als een cybersecurity pro

Uw Office 365-abonnement heeft een krachtige reeks aan beveiligingsmogelijkheden die u kunt gebruiken om uw gegevens en gebruikers te beschermen.  Gebruik de [Office 365-roadmap voor beveiliging - Topprioriteiten voor de eerste 30 dagen, 90 dagen en verder](security-roadmap.md) om door Microsoft aanbevolen procedures voor het beveiligen van uw Office 365-tenant te implementeren.

- Taken die in de eerste 30 dagen moeten worden uitgevoerd.  Deze hebben direct effect en weinig invloed op uw gebruikers.

- Taken die binnen 90 dagen moeten worden uitgevoerd. Deze nemen qua planning en implementatie iets meer tijd in beslag, maar zorgen voor aanzienlijke verbeteringen in uw beveiligingspostuur.

- Na 90 dagen. Deze verbeteringen zijn gebaseerd op de eerste 90 dagen.

## <a name="see-also"></a>Zie ook

- [Het opsporen en herstellen van Outlook-regels en aangepaste formulieren in Office 365](detect-and-remediate-outlook-rules-forms-attack.md)

- [Internet Crime Complaint Center](https://www.ic3.gov/preventiontips.aspx)

- [Securities and Exchange Commission - "Phishing" fraude](https://www.sec.gov/investor/pubs/phishing.htm)

- Om ongewenste e-mailberichten rechtstreeks bij Microsoft en uw beheerder te melden, kunt u [De invoegtoepassing rapporteer bericht gebruiken](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)