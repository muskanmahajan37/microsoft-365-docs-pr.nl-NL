---
title: Aan de slag met intern risicobeheer
description: Configureer insider risk management in uw organisatie.
keywords: Microsoft 365, insider risk management, risk management, compliance
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
ms.openlocfilehash: 9e1b7a18bea09d10cb133ce9106df45533a72172
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/30/2021
ms.locfileid: "52162494"
---
# <a name="get-started-with-insider-risk-management"></a>Aan de slag met intern risicobeheer

Gebruik beleid voor insiderrisicobeheer om risicovolle activiteiten en beheerhulpmiddelen te identificeren om risicowaarschuwingen in uw organisatie op te nemen. Volg de volgende stappen om vereisten in te stellen en een beleid voor insiderrisicobeheer te configureren.

>[!IMPORTANT]
>De Microsoft 365 insider risk management-oplossing biedt een optie op tenantniveau om klanten te helpen interne governance op gebruikersniveau te vergemakkelijken. Beheerders op tenantniveau kunnen machtigingen instellen voor toegang tot deze oplossing voor leden van uw organisatie en gegevensconnectoren instellen in het Microsoft 365 compliancecentrum om relevante gegevens te importeren ter ondersteuning van de identificatie op gebruikersniveau van potentieel riskante activiteiten. Klanten erkennen inzichten met betrekking tot het gedrag, het karakter of de prestaties van de afzonderlijke gebruiker die materiaal gerelateerd zijn aan werk, kunnen door de beheerder worden berekend en beschikbaar worden gesteld aan anderen in de organisatie. Daarnaast erkennen klanten dat ze hun eigen volledige onderzoek moeten uitvoeren met betrekking tot het gedrag, karakter of prestaties van de afzonderlijke gebruiker die materiaal gerelateerd is aan werk en niet alleen afhankelijk zijn van inzichten van de insider-service voor risicobeheer. Klanten zijn uitsluitend verantwoordelijk voor het gebruik van de Microsoft 365 insider risk management-service en alle bijbehorende functies of service in overeenstemming met alle toepasselijke wetten, met inbegrip van wetten met betrekking tot individuele gebruikersidentificatie en eventuele herstelacties.

Zie Insider risk management in Microsoft 365 voor meer informatie over hoe insiderrisicobeleid u kan helpen bij het beheren van [risico's in uw organisatie.](insider-risk-management.md)

## <a name="subscriptions-and-licensing"></a>Abonnementen en licenties

Voordat u aan de slag gaat met insider risk management, moet u uw Microsoft 365 [en](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) eventuele invoegtoepassingen bevestigen. Als u insider risk management wilt openen en gebruiken, moet uw organisatie een van de volgende abonnementen of invoegtoepassingen hebben:

- Microsoft 365 E5 (betaalde of proefversie)
- Microsoft 365 E3 +de Microsoft 365 E5 Compliance-invoegvoegvoeging
- Microsoft 365 E3 abonnement + de Microsoft 365 E5 Insider Risk Management-invoegvoegvoeging
- Microsoft 365 A5-abonnement (betaalde versie of proefversie)
- Microsoft 365 A3-abonnement + de Microsoft 365 A5 Compliance-invoegvoegvoeging
- Microsoft 365 A3-abonnement + de Microsoft 365 A5 Insider Risk Management-invoegvoegvoeging
- Microsoft 365 G5-abonnement (betaalde versie of proefversie)
- Microsoft 365 G3 +de Microsoft 365 G5 Compliance-invoegvoegvoeging
- Microsoft 365 G3 +de Microsoft 365 G5 Insider Risk Management add-on
- Office 365 E3-abonnement + Enterprise Mobility and Security E3 + Microsoft 365 E5 Compliance add-on

Gebruikers die zijn opgenomen in beleidsregels voor insiderrisicobeheer, moeten een van de bovenstaande licenties krijgen toegewezen.

Als u geen bestaand Microsoft 365 Enterprise E5-abonnement hebt en insider risk management wilt proberen, kunt u [Microsoft 365](/office365/admin/try-or-buy-microsoft-365) toevoegen aan uw bestaande abonnement [of](https://www.microsoft.com/microsoft-365/enterprise) u registreren voor een proefabonnement op Microsoft 365 Enterprise E5.

## <a name="step-1-enable-permissions-for-insider-risk-management"></a>Stap 1: Machtigingen inschakelen voor insiderrisicobeheer

>[!Important]
>Nadat u de rollengroepen hebt geconfigureerd, kan het tot 30 minuten duren voordat de machtigingen voor rollengroepen van toepassing zijn op toegewezen gebruikers in uw organisatie.

Er zijn vier rollengroepen die worden gebruikt om machtigingen te configureren voor het beheren van functies voor insiderrisicobeheer. Als u deze configuratiestappen wilt voortzetten, moeten uw tenantbeheerders u eerst toewijzen aan de rollengroep **Insider Risk Management** of Insider Risk Management **Admin.** Als u functies voor insiderrisicobeheer na de eerste configuratie wilt openen en beheren, moeten gebruikers lid zijn van ten minste één rollengroep voor insiderrisicobeheer.

Afhankelijk van de structuur van uw compliancebeheerteam hebt u opties om gebruikers toe te wijzen aan specifieke rollengroepen om verschillende sets functies voor insiderrisicobeheer te beheren. Als u  het tabblad Machtigingen wilt weergeven in het Office 365 Beveiligings- & Compliancecentrum en rollengroepen wilt beheren, moet u zijn toegewezen aan de rollengroep Organisatiebeheer of moet u de rol Rollenbeheer *toegewezen* krijgen.  Kies uit deze opties voor rollengroep bij het configureren van insiderrisicobeheer:

| **Rollengroep** | **Rolmachtigingen** |
| :------------- | :------------------- |
| **Insider Risk Management** | Gebruik deze rollengroep om insiderrisicobeheer voor uw organisatie in één groep te beheren. Door alle gebruikersaccounts toe te voegen voor aangewezen beheerders, analisten, onderzoekers en auditors, kunt u machtigingen voor insiderrisicobeheer configureren in één groep. Deze rollengroep bevat alle machtigingen voor insiderrisicobeheer en bijbehorende machtigingen. Deze configuratie is de eenvoudigste manier om snel aan de slag te gaan met insider risk management en is geschikt voor organisaties die geen afzonderlijke machtigingen nodig hebben die zijn gedefinieerd voor afzonderlijke groepen gebruikers. |
| **Insider Risk Management Admin** | Gebruik deze rollengroep om in eerste instantie insiderrisicobeheer te configureren en later om beheerders van insiderrisico's te scheiden in een gedefinieerde groep. Gebruikers in deze rollengroep kunnen analyseinzichten in- en weergeven en insiderrisicobeheerbeleid, globale instellingen en rolgroeptoewijzingen maken, lezen, bijwerken en verwijderen. |
| **Analist intern risicobeheer** | Gebruik deze groep om machtigingen toe te wijzen aan gebruikers die fungeren als insiderrisicocaseanalisten. Gebruikers in deze rollengroep hebben toegang tot alle insiderrisicobeheerwaarschuwingen, cases, analyseinzichten en kennisgevingssjablonen. Ze hebben geen toegang tot het insiderrisico Inhoudsverkenner. |
| **Onderzoeker intern risicobeheer** | Gebruik deze groep om machtigingen toe te wijzen aan gebruikers die fungeren als insider-risicogegevensonderzoekers. Gebruikers in deze rollengroep hebben toegang tot alle waarschuwingen voor insiderrisicobeheer, cases, kennisgevingssjablonen en de Inhoudsverkenner voor alle gevallen. |
| **Insider Risk Management Auditors** | Gebruik deze groep om machtigingen toe te wijzen aan gebruikers die activiteiten voor insiderrisicobeheer controleren. Gebruikers in deze rollengroep hebben toegang tot het auditlogboek voor insiderrisico's. |

> [!NOTE]
> Deze rollengroepen worden momenteel niet ondersteund op Privileged Identity Management (PIM). Zie Azure AD-rollen toewijzen in Privileged Identity Management voor meer [Privileged Identity Management.](/azure/active-directory/privileged-identity-management/pim-how-to-add-role-to-user)

### <a name="add-users-to-an-insider-risk-management-role-group"></a>Gebruikers toevoegen aan een rollengroep voor insiderrisicobeheer

Volg de volgende stappen om gebruikers toe te voegen aan een rollengroep voor insiderrisicobeheer:

1. Meld u [https://protection.office.com/permissions](https://protection.office.com/permissions) aan bij het gebruik van referenties voor een beheerdersaccount in uw Microsoft 365 organisatie.

2. Ga in het &amp; Beveiligings compliancecentrum naar **Machtigingen.** Selecteer de koppeling voor het weergeven en beheren van rollen in Office 365.

3. Selecteer de rollengroep voor insiderrisicobeheer aan wie u gebruikers wilt toevoegen en selecteer **vervolgens Rollengroep bewerken.**

4. Selecteer **Leden kiezen** in het linkernavigatiedeelvenster en selecteer vervolgens **Bewerken.**

5. Selecteer **Toevoegen** en schakel het selectievakje in voor alle gebruikers die u wilt toevoegen aan de rollengroep.

6. Selecteer **Toevoegen** en selecteer vervolgens **Klaar.**

7. Selecteer **Opslaan om** de gebruikers toe te voegen aan de rollengroep. Selecteer **Sluiten om** de stappen uit te voeren.

## <a name="step-2-enable-the-microsoft-365-audit-log"></a>Stap 2: Het auditlogboek Microsoft 365 inschakelen

Insider risk management gebruikt Microsoft 365 auditlogboeken voor gebruikersinzichten en activiteiten die zijn geïdentificeerd in beleidsregels en analyseinzichten. De Microsoft 365 auditlogboeken zijn een overzicht van alle activiteiten binnen uw organisatie en insiderrisicobeheerbeleid kan deze activiteiten gebruiken om beleidsinzichten te genereren.

Zie Zoeken in auditlogboek in- of uitschakelen voor stapsgewijs instructies voor het in- of [uitschakelen van controlelogboek.](turn-audit-log-search-on-or-off.md) Nadat u de controle hebt in- of uitgevoerd, wordt een bericht weergegeven met de melding dat het auditlogboek wordt voorbereid en dat u een zoekopdracht kunt uitvoeren binnen een paar uur nadat de voorbereiding is voltooid. U hoeft deze actie maar één keer uit te voeren. Zie Het auditlogboek doorzoeken Microsoft 365 voor meer informatie over het gebruik van het [auditlogboek.](search-the-audit-log-in-security-and-compliance.md)

## <a name="step-3-enable-and-view-insider-risk-analytics-insights-optional"></a>Stap 3: Inzichten in insider risk analytics in- en weergeven (optioneel)

Met insider risk management analytics kunt u een evaluatie uitvoeren van potentiële insiderrisico's in uw organisatie zonder dat u beleidsregels voor insiderrisico's configureert. Deze evaluatie kan uw organisatie helpen bij het identificeren van mogelijke gebieden met een hoger gebruikersrisico en het bepalen van het type en het bereik van beleidsregels voor insiderrisicobeheer dat u mogelijk wilt configureren. Deze evaluatie kan u ook helpen bij het bepalen van de behoeften voor aanvullende licenties of toekomstige optimalisatie van bestaande beleidsregels. Het kan tot 48 uur duren voordat inzichten beschikbaar zijn als rapporten om te worden beoordeeld. Zie Insider-instellingen voor risicobeheer voor meer informatie over analyseinzichten: Analytics [(preview)](insider-risk-management-settings.md#analytics-preview) en bekijk de [video Insider Risk Management Analytics](https://www.youtube.com/watch?v=5c0P5MCXNXk) om te begrijpen hoe analyses de identificatie van potentiële insiderrisico's kunnen versnellen en u kunnen helpen om snel actie te ondernemen.

Als u insider risk Analytics wilt inschakelen, moet u lid zijn van de rollengroep *Insider Risk Management,* *Insider Risk Management* of Microsoft 365 Global *Admin.*

Volg de volgende stappen om insider risk analytics in teschakelen:

1. Ga in [Microsoft 365 compliancecentrum](https://compliance.microsoft.com)naar **Insider-risicobeheer.**
2. Selecteer **Scan uitvoeren** op de scan voor **insiderrisico's in uw organisatiekaart** op het tabblad Overzicht van insiderrisicobeheer.  Met deze actie schakelt u het scannen van analyses voor uw organisatie in. U kunt scannen in uw organisatie ook inschakelen door te navigeren naar Insider-risico-instellingen Analytics (preview) en de gebruikersactiviteit van uw tenant scannen in te stellen om mogelijke  >   **insiderrisico's te identificeren.**
3. Selecteer in **het deelvenster Details van Analyse** de optie Scan uitvoeren om de scan voor uw organisatie te **starten.** Het kan tot 24 uur duren voordat inzichten beschikbaar zijn als rapporten om te worden beoordeeld.

Nadat u de analyseinzichten hebt beoordeeld, kiest u het beleid voor insiderrisico's en configureert u de bijbehorende vereisten die het best voldoen aan de risicobeperkingsstrategie voor insiders van uw organisatie.

## <a name="step-4-configure-prerequisites-for-policies"></a>Stap 4: Vereisten voor beleid configureren

De meeste beleidsregels voor insiderrisicobeheer hebben vereisten die moeten worden geconfigureerd voor beleidsindicatoren om relevante activiteitswaarschuwingen te genereren. Configureer de juiste vereisten, afhankelijk van het beleid dat u voor uw organisatie wilt configureren.

### <a name="configure-microsoft-365-hr-connector"></a>Een MICROSOFT 365-connector configureren

Insider-risicobeheer ondersteunt het importeren van gebruikers- en logboekgegevens die zijn geïmporteerd uit platformen voor risicobeheer en personeelszaken van derden. Met Microsoft 365 Hr-gegevensconnector (Human Resources) kunt u hr-gegevens uit CSV-bestanden halen, waaronder einddatums van gebruikers, laatste dienstverbanddatums, meldingen over prestatieverbeteringsplan, acties voor prestatiebeoordeling en status van functieniveau wijzigen. Deze gegevens helpen waarschuwingsindicatoren in beleidsregels voor insiderrisicobeheer te verbeteren en vormen een belangrijk onderdeel van het configureren van volledige risicobeheerdekking in uw organisatie. Als u meer dan één HR-connector configureert voor uw organisatie, haalt insider risk management automatisch indicatoren uit alle HR-connectors.

De Microsoft 365 HR-connector is vereist wanneer u de volgende beleidssjablonen gebruikt:

- Gegevensdiefstal van vertrekkende gebruikers
- Schendingen van het beveiligingsbeleid door vertrekkende gebruikers
- Schendingen van beveiligingsbeleid door ontevreden gebruikers
- Gegevenslekken door ontevreden gebruikers

Zie het artikel Een [verbindingslijn instellen](import-hr-data.md) voor het importeren van HR-gegevens voor stapsgewijs richtlijnen voor het configureren van de Microsoft 365 HR-connector voor uw organisatie. Nadat u de HR-connector hebt geconfigureerd, gaat u terug naar deze configuratiestappen.

### <a name="configure-data-loss-prevention-dlp-policies"></a>DLP-beleid (Data Loss Prevention) configureren

Insider risk management ondersteunt het gebruik van DLP-beleid om de opzettelijke of onbedoelde blootstelling van gevoelige informatie aan ongewenste partijen te identificeren voor DLP-waarschuwingen met hoge ernst. Wanneer u een insiderrisicobeheerbeleid configureert met een van de **gegevenslekkensjablonen,** moet u een specifiek DLP-beleid aan het beleid toewijzen.

DLP-beleid helpt gebruikers bij het activeren van risicoscores in insider risk management voor DLP-waarschuwingen met hoge ernst voor gevoelige informatie en vormen een belangrijk onderdeel van het configureren van volledige risicobeheerdekking in uw organisatie. Zie Insider-beleid voor risicobeheer voor meer informatie over [insiderrisicobeheer](insider-risk-management-policies.md#general-data-leaks)en DLP-beleidsintegratie en -planning.

>[!IMPORTANT]
>Zorg ervoor dat u het volgende hebt voltooid:
>
>- U begrijpt en configureert de gebruikers binnen het bereik in zowel het DLP- als insiderrisicobeheerbeleid om de beleidsdekking te leveren die u verwacht.
>- Zorg ervoor dat de **instelling incidentrapporten** in het DLP-beleid voor  insiderrisicobeheer dat met deze sjablonen wordt gebruikt, is geconfigureerd voor waarschuwingen op hoog ernstniveau. Waarschuwingen voor insiderrisicobeheer worden niet gegenereerd op basis van DLP-beleid met het **veld Incidentrapporten** ingesteld op *Laag* of *Gemiddeld.*

Een DLP-beleid is vereist bij het gebruik van de volgende beleidssjablonen:

- Algemene gegevenslekken
- Gegevenslekken door prioriteitsgebruikers

Zie het [artikel DLP-beleid maken,](create-test-tune-dlp-policy.md) testen en afstemmen voor stapsgewijs richtlijnen voor het configureren van DLP-beleid voor uw organisatie. Nadat u een DLP-beleid hebt geconfigureerd, gaat u terug naar deze configuratiestappen.

### <a name="configure-priority-user-groups"></a>Gebruikersgroepen met prioriteit configureren

Insider-risicobeheer omvat ondersteuning voor het toewijzen van prioriteitsgebruikersgroepen aan beleidsregels om unieke risicoactiviteiten voor gebruikers met kritieke posities, hoge niveaus van gegevens en netwerktoegang of een geschiedenis van risicogedrag te helpen. Het maken van een gebruikersgroep met prioriteit en het toewijzen van gebruikers aan het groepshulpbereikbeleid aan de unieke omstandigheden die door deze gebruikers worden gepresenteerd.

Een gebruikersgroep met prioriteit is vereist wanneer u de volgende beleidssjablonen gebruikt:

- Schendingen van beveiligingsbeleid door gebruikers met prioriteit
- Gegevenslekken door prioriteitsgebruikers

Zie het [artikel Aan de slag met insider-instellingen](insider-risk-management-settings.md#priority-user-groups-preview) voor risicobeheer voor stapsgewijs richtlijnen om een gebruikersgroep met prioriteit te maken. Nadat u een gebruikersgroep met prioriteit hebt geconfigureerd, gaat u terug naar deze configuratiestappen.

### <a name="configure-physical-badging-connector-optional"></a>Fysieke verbindingslijn configureren (optioneel)

Insider risk management ondersteunt het importeren van gebruikers- en logboekgegevens van fysieke besturings- en toegangsplatforms. Met de verbindingslijn Fysieke fout kunt u toegangsgegevens binnen halen uit JSON-bestanden, zoals gebruikers-ID's, toegangspunt-ID's, toegangstijd en -datums en toegangsstatus. Deze gegevens helpen waarschuwingsindicatoren in beleidsregels voor insiderrisicobeheer te verbeteren en vormen een belangrijk onderdeel van het configureren van volledige risicobeheerdekking in uw organisatie. Als u meer dan één fysieke verbindingslijn configureert voor uw organisatie, haalt insider risk management automatisch indicatoren uit alle connectors voor fysieke fout. Informatie van de physical badging connector vormt een aanvulling op andere insiderrisicosignalen bij het gebruik van alle sjablonen voor insiderrisicobeleid.

>[!IMPORTANT]
>Voor beleidsregels voor insiderrisicobeheer om signaalgegevens met betrekking tot vertrekkende en beëindigde gebruikers te gebruiken en te correleren met gebeurtenisgegevens van uw fysieke beheer- en toegangsplatformen, moet u ook de Microsoft 365 HR-connector configureren. Als u de connector Voor fysieke problemen inschakelen zonder de Microsoft 365 HR-connector in te stellen, worden met beleidsregels voor insiderrisicobeheer alleen gebeurtenissen verwerkt voor niet-geautoriseerde fysieke toegang voor gebruikers in uw organisatie.

Zie het [artikel Een verbindingslijn instellen](import-physical-badging-data.md) voor het importeren van fysieke foutgegevens voor stapsgewijs richtlijnen voor het configureren van de connector Voor fysieke problemen voor uw organisatie. Nadat u de verbindingslijn hebt geconfigureerd, gaat u terug naar deze configuratiestappen.

### <a name="configure-microsoft-defender-for-endpoint-optional"></a>Microsoft Defender voor eindpunt configureren (optioneel)

[Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) is een beveiligingsplatform voor zakelijke eindpunten dat is ontworpen om bedrijfsnetwerken te helpen geavanceerde bedreigingen te voorkomen, te detecteren, te onderzoeken en erop te reageren. Als u een betere zichtbaarheid van beveiligingsovertredingen in uw organisatie wilt hebben, kunt u Defender voor eindpuntwaarschuwingen importeren en filteren voor activiteiten die worden gebruikt in beleidsregels die zijn gemaakt op basis van beleidsregels voor beveiligingsovertredingssjablonen voor insiderrisicobeheer.

Als u beleidsregels voor beveiligingsovertreding maakt, moet Microsoft Defender voor Eindpunt zijn geconfigureerd in uw organisatie en Defender voor Eindpunt inschakelen voor integratie van insiderrisicobeheer in het Defender-beveiligingscentrum om waarschuwingen voor beveiligingsovertreding te importeren. Zie het artikel Minimumvereisten voor [Microsoft Defender voor eindpunten](/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements) voor meer informatie over vereisten.

Zie het [artikel Geavanceerde functies configureren in Het](/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center) artikel Van Defender voor Eindpunt voor stapsgewijs richtlijnen voor het configureren van Defender voor Eindpunt voor integratie van insiderrisicobeheer. Nadat u het Microsoft Defender voor eindpunt hebt geconfigureerd, gaat u terug naar deze configuratiestappen.

## <a name="step-5-configure-insider-risk-settings"></a>Stap 5: Instellingen voor insiderrisico's configureren

[Insider-risico-instellingen](insider-risk-management-settings.md) zijn van toepassing op alle beleidsregels voor insiderrisicobeheer, ongeacht de sjabloon die u hebt gekozen bij het maken van een beleid. Instellingen zijn geconfigureerd met behulp  van het insiderrisico-instellingenbesturingselement boven aan alle tabbladen voor insiderrisicobeheer. Deze instellingen bepalen de privacy, indicatoren, vensters bewaken en intelligente detecties.

Voordat u een beleid configureert, definieert u de volgende instellingen voor insiderrisico's:

1. Ga in [Microsoft 365 compliancecentrum](https://compliance.microsoft.com)naar **Insider-risicobeheer** en selecteer Insider-risico-instellingen in de rechterbovenhoek van een pagina. 
2. Selecteer op **de pagina Privacy** een privacyinstelling voor het weergeven van gebruikersnamen voor beleidswaarschuwingen.
3. Selecteer op **de** pagina Indicatoren de waarschuwingsindicatoren die u wilt toepassen op alle beleidsregels voor insiderrisico's.

    >[!IMPORTANT]
    >Als u waarschuwingen wilt ontvangen voor risicovolle activiteiten die zijn gedefinieerd in uw beleid, moet u een of meer indicatoren selecteren. Als indicatoren niet zijn geconfigureerd in Instellingen, kunnen de indicatoren niet worden geselecteerd in beleidsregels voor insiderrisico's.

4. Selecteer op **de pagina** Beleidstijdframes de beleidstermijnen die van kracht moeten worden voor een gebruiker wanneer deze een overeenkomst voor een insiderrisicobeleid activeert. [](insider-risk-management-settings.md#policy-timeframes)
5. Configureer op de pagina Intelligente **detecties** de volgende instellingen voor insiderrisicobeleid:
    - [Uitsluitingen van bestandstype](insider-risk-management-settings.md#file-type-exclusions)
    - [Drempelwaarden voor ongebruikelijke bestandsactiviteit](insider-risk-management-settings.md#threshold-for-unusual-file-activity)
    - [Alarmvolumeniveau](insider-risk-management-settings.md#alert-volume)
    - [Waarschuwingsstatus van Microsoft Defender voor eindpunt](insider-risk-management-settings.md#microsoft-defender-for-endpoint-preview)
    - [Domeininstellingen](insider-risk-management-settings.md#domains-preview)
6. Schakel op **de pagina Waarschuwingen exporteren** de export van informatie over insiderrisicowaarschuwingen in met de Office 365 management-API's indien nodig.
7. Maak op **de pagina Gebruikersgroepen** prioriteit een gebruikersgroep met prioriteit en voeg gebruikers toe als deze niet zijn gemaakt in **stap 3.**
8. Configureer op **Power Automate pagina met stroomstromen** een stroom van insider-risicostroomsjablonen of maak een nieuwe stroom. Zie het [artikel Aan de slag met insider-instellingen](insider-risk-management-settings.md#power-automate-flows-preview) voor risicobeheer voor stapsgewijs richtlijnen.
9. Configureer **op de pagina Prioriteitactiva** de prioriteitsactiva om gegevens te gebruiken van uw fysieke beheer- en toegangsplatform die zijn geïmporteerd door de connector Fysieke fout. Zie het [artikel Aan de slag met insider-instellingen](insider-risk-management-settings.md#priority-physical-assets-preview) voor risicobeheer voor stapsgewijs richtlijnen.
10. Schakel op **Microsoft Teams** pagina de integratie Microsoft Teams insiderrisicobeheer in om automatisch een team te maken voor case- of gebruikerssamenwerking. Zie het [artikel Aan de slag met insider-instellingen](insider-risk-management-settings.md#microsoft-teams-preview) voor risicobeheer voor stapsgewijs richtlijnen.
11. Selecteer **Opslaan om** deze instellingen in te stellen voor uw insiderrisicobeleid.

## <a name="step-6-create-an-insider-risk-management-policy"></a>Stap 6: Een beleid voor insider-risicobeheer maken

Insider-beleid voor risicobeheer omvat toegewezen gebruikers en definieer welke typen risico-indicatoren zijn geconfigureerd voor waarschuwingen. Voordat activiteiten waarschuwingen kunnen activeren, moet een beleid zijn geconfigureerd. Gebruik de beleidswizard om nieuw beleid voor insiderrisicobeheer te maken.

1. Ga in [Microsoft 365 compliancecentrum](https://compliance.microsoft.com)naar **Insider-risicobeheer** en selecteer het **tabblad** Beleid.
2. Selecteer **Beleid maken om** de beleidswizard te openen.
3. Kies op **de pagina** Beleidssjabloon een beleidscategorie en selecteer vervolgens de sjabloon voor het nieuwe beleid. Deze sjablonen zijn gemaakt van voorwaarden en indicatoren die de risicoactiviteiten definiëren die u wilt detecteren en onderzoeken. Controleer de vereisten voor de sjabloon, triggeringsgebeurtenissen en gedetecteerde activiteiten om te bevestigen dat deze beleidssjabloon aan uw behoeften voldoet.

    >[!IMPORTANT]
    >Sommige beleidssjablonen hebben vereisten die moeten worden geconfigureerd voor het beleid om relevante waarschuwingen te genereren. Zie Stap **4 hierboven** als u de toepasselijke beleidsvoorwaarde niet hebt geconfigureerd.

4. Selecteer **Volgende om** door te gaan.
5. Vul op **de pagina Naam** en beschrijving de volgende velden in:
    - **Naam (vereist)**: Voer een vriendelijke naam in voor het beleid. Deze naam kan niet worden gewijzigd nadat het beleid is gemaakt.
    - **Beschrijving (optioneel)**: Voer een beschrijving in voor het beleid.

6. Selecteer **Volgende om** door te gaan.
7. Selecteer op de pagina  Gebruikers en groepen  de optie Alle gebruikers en groepen opnemen of Specifieke gebruikers en groepen opnemen om te definiëren welke gebruikers of groepen zijn opgenomen in het beleid of als u een sjabloon met prioriteitsgebruikers hebt gekozen.  selecteer **Gebruikersgroepen met prioriteit toevoegen of bewerken.** Als **u Alle gebruikers en groepen opnemen** selecteert, wordt er naar triggeringgebeurtenissen voor alle gebruikers en groepen in uw organisatie op zoek om risicoscores voor het beleid toe te wijzen. Als **u Specifieke gebruikers en groepen opnemen selecteert,** kunt u definiëren welke gebruikers en groepen u wilt toewijzen aan het beleid.
8. Selecteer **Volgende om** door te gaan.
9. Op de **pagina** Inhoud om prioriteit te geven, kunt u (indien nodig) de bronnen toewijzen aan prioriteit, waardoor de kans op het genereren van een waarschuwing met hoge ernst voor deze bronnen groter wordt. Selecteer een van de volgende opties:

    - **Ik wil de SharePoint, gevoeligheidslabels en/of gevoelige informatietypen opgeven als prioriteitsinhoud.** Als u deze optie selecteert, kunnen detailpagina's in de wizard deze kanalen configureren.
    - **Ik wil nu geen prioriteitsinhoud** opgeven (u kunt dit doen nadat het beleid is gemaakt) . Als u deze optie selecteert, worden de pagina's met kanaaldetails in de wizard overgeslagen.

10. Selecteer **Volgende om** door te gaan.

11. Als u in de vorige stap ik SharePoint sites, gevoeligheidslabels **en/of** gevoelige informatietypen als prioriteitsinhoud hebt geselecteerd, ziet u de detailpagina's voor *SharePoint-sites,* gevoelige *infotypen* en gevoeligheidslabels.  Gebruik deze detailpagina's om de SharePoint, gevoelige infotypen en gevoeligheidslabels te definiëren om prioriteit te geven aan het beleid.

    - **SharePoint sites:** Selecteer **Toevoegen SharePoint site** en selecteer de SharePoint sites die u hebt en die u prioriteit wilt geven. Bijvoorbeeld *'group1@contoso.sharepoint.com/sites/group1'*.
    - **Type gevoelige informatie:** Selecteer **Gevoelige informatietype toevoegen** en selecteer de gevoeligheidstypen die u wilt prioriteren. Bijvoorbeeld *'Amerikaans bankrekeningnummer'* en *'Creditcardnummer'.*
    - **Gevoeligheidslabels:** Selecteer **Gevoeligheidslabel toevoegen** en selecteer de etiketten die u wilt prioriteren. Bijvoorbeeld *'Vertrouwelijk'* en *'Geheim'.*

12. Selecteer **Volgende om** door te gaan.
13. Op de **pagina Indicatoren en triggeringgebeurtenissen** ziet u de indicatoren die u hebt gedefinieerd als beschikbaar op de pagina Indicatoren voor [](insider-risk-management-settings.md#indicators)   >   insiderrisico-instellingen. Als u aan het begin van de wizard een sjabloon Gegevenslekken hebt geselecteerd, moet u een DLP-beleid selecteren in de vervolgkeuzelijst **DLP-beleid** om *triggeringindicatoren* voor het beleid in te stellen of de ingebouwde triggeringgebeurtenis te selecteren.

    >[!IMPORTANT]
    >Als indicatoren op deze pagina niet kunnen worden geselecteerd, moet u de indicatoren selecteren die u wilt inschakelen voor alle beleidsregels. U kunt de knop **Indicatoren in de** wizard in-/uit- of indicatoren selecteren op de pagina **Insider-risicobeheer**  >  **Instellingen**  >  **beleidsindicatoren.**

    Selecteer de indicatoren die u wilt toepassen op het beleid. Als u liever geen gebruik wilt maken van de standaardinstellingen voor drempelwaarden voor deze indicatoren, schakelt u de door Microsoft aanbevolen **standaarddrempels** gebruiken uit en voert u de drempelwaarden voor elke geselecteerde indicator in.

    - Als u ten minste  één Office of *apparaatindicator* hebt geselecteerd, selecteert u de **risicoscore-verhogingen.** Risicoscore-verhogingen zijn alleen van toepassing op geselecteerde indicatoren.
    - Als u een beleidssjabloon *Gegevensdiefstal* of Gegevenslekken hebt geselecteerd, selecteert u een of meer detectiemethoden voor reeksen en een methode voor cumulatieve **exfiltratie** die u wilt toepassen op het beleid.  

14. Selecteer **Volgende om** door te gaan.
15. Selecteer op **de pagina Indicatordrempels** de optie voor het gebruik van standaardindicatordrempels of om aangepaste drempelwaarden voor afzonderlijke indicatoren op te geven. Kies voor elke indicator het juiste niveau om het gewenste niveau van activiteitswaarschuwingen te genereren.
16. Selecteer **Volgende om** door te gaan.
17. Bekijk op **de** pagina Controleren de instellingen die u hebt gekozen voor het beleid en eventuele suggesties of waarschuwingen voor uw selecties. Selecteer **Bewerken om** een van de beleidswaarden te wijzigen of selecteer **Verzenden** om het beleid te maken en te activeren.

## <a name="next-steps"></a>Volgende stappen

Nadat u deze stappen hebt voltooid om uw eerste beleid voor insiderrisicobeheer te maken, ontvangt u na ongeveer 24 uur waarschuwingen van activiteitsindicatoren. Configureer zo nodig extra beleid met behulp van de richtlijnen in stap 4 van dit artikel of de stappen in [Een nieuw insiderrisicobeleid maken.](insider-risk-management-policies.md#create-a-new-policy)

Zie Insider risk management alerts (Insider [risk management alerts)](insider-risk-management-alerts.md)voor meer informatie over het onderzoeken van waarschuwingen voor insiderrisico's en het **dashboard** Waarschuwingen.
