---
title: Uw infrastructuur instellen voor extern werk met Microsoft 365
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- m365solution-remotework
- m365solution-overview
- M365initiative-coredeploy
ms.custom: seo-marvel-jun2020
keywords: thuisweken, telewerken, hybride, externe werknemer, hybride werken, externe medewerkers, hybride connectiviteit, externe toegang, extern werk, telewerk, mobiel werken, werken op afstand, overal werken, flexibele werkplek
description: Ga stapsgewijs door de lagen van uw infrastructuur om uw externe werknemers veilig toegang te geven tot on-premises en Microsoft 365-resources.
ms.openlocfilehash: 1a8cf471cf92e1301c231f395ed0238bb35359cb
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/06/2021
ms.locfileid: "52246318"
---
# <a name="set-up-your-infrastructure-for-remote-work-with-microsoft-365"></a>Uw infrastructuur instellen voor extern werk met Microsoft 365

U moet uw IT- en cloudinfrastructuur configureren om extern werk mogelijk te maken en toegang bieden tot de on-premises informatie, hulpmiddelen en resources om de productiviteit van uw externe werknemers te beveiligen en te optimaliseren. Met deze oplossing wordt u stap voor stap door de implementatie van de belangrijkste lagen van de infrastructuur geleid die ervoor zorgen dat uw medewerkers goed werk leveren, waar ze zich ook bevinden.

Door werknemers op afstand te laten werken, kunnen veel organisaties:

- Besparen op kantoorruimte.
- Werknemers aannemen en behouden die niet bereid zijn te verhuizen.
- De reistijd van werknemers verminderen, waardoor er meer tijd overblijft om productief te zijn en stress verlagende activiteiten uit te voeren buiten werktijd.

Microsoft 365 biedt de mogelijkheden om uw werknemers in staat te stellen om op afstand te werken.

![Uw externe werknemers mogelijkheden bieden met Microsoft 365](../media/empower-people-to-work-remotely/2-m365-remoteworker-solution-businessoverview.png)

>[!Note]
>Raadpleeg [deze informatiebronnen](https://www.microsoft.com/microsoft-365) als Microsoft 365 nieuw voor u is.
>

Bekijk deze video voor een overzicht van het implementatieproces.
<br>
<br>
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4F1af]

Voor IT-professionals die de onsite- en cloudinfrastructuur beheren om de productiviteit van werknemers te verbeteren, biedt deze oplossing de volgende belangrijke mogelijkheden:

- Verbonden

  Externe werknemers hebben overal ter wereld en op elk gewenst moment toegang tot: 

  - Op de cloud gebaseerde services en gegevens in uw Microsoft 365-abonnement. 

  - Resources van de organisatie, zoals de resources van on-premises toepassingsdatacenters.

- Beveiligd

  Aanmeldingen worden beveiligd met meervoudige verificatie (MFA) en ingebouwde beveiligingsfuncties van Microsoft 365 en Windows 10 beveiligen tegen malware, kwaadwillige aanvallen en gegevensverlies.

- Beheerd

  De apparaten van uw externe werknemers kunnen worden beheerd vanuit de cloud met beveiligingsinstellingen, toegestane apps en door naleving van de systeemstatus te vereisen.

- Samenwerking en productiviteit

  Uw externe werknemers kunnen net zo productief zijn als op kantoor in een omgeving waar samenwerking eenvoudig is met:

  - Online vergaderingen en chatsessies met Teams. 

  - Gedeelde werkruimten voor cloudopslag met wereldwijde toegankelijkheid en realtime samenwerking met SharePoint en OneDrive.

  - Gedeelde taken en werkstromen om het werk te verdelen en taken uit te voeren. 

Voor een naadloze aanmelding moeten de on-premise gebruikersaccounts van Active Directory Domain Services (AD DS) worden gesynchroniseerd met Azure Active Directory (Azure AD). Als u uw Windows 10-apparaten wilt beveiligen, moeten ze worden ingeschreven in Intune. Dit is een algemeen overzicht van de infrastructuur.

![De basisinfrastructuur voor externe werknemers met Microsoft 365](../media/empower-people-to-work-remotely/remote-workers-basic-infrastructure.png)

Als je de mogelijkheden van Microsoft 365 wilt inschakelen voor uw externe werknemers, kun je gebruikmaken van de volgende functies van Microsoft 365.

| Functie | Beschrijving | Licenties |
|:-------|:-----|:-------|
| Afgedwongen door MFA en met standaardbeveiligingsinstellingen   | Voorkom gecompromitteerde identiteiten en apparaten met een tweede vorm van verificatie voor aanmeldingen. Als standaardinstelling voor de beveiliging is MFA vereist voor alle gebruikersaccounts.   | Microsoft 365 E3 of E5 |
| Afgedwongen door MFA en met voorwaardelijke toegang| Gebruik beleid voor voorwaardelijke toegang om MFA te vereisen op basis van de eigenschappen van de aanmelding.    | Microsoft 365 E3 of E5 | 
| Afgedwongen door MFA en met voorwaardelijke toegang op basis van risico   | Vereis MFA op basis van het risico van de gebruikersaanmelding met Microsoft Defender for Identity. | Microsoft 365 E5 of E3 met Azure AD Premium P2-licenties | 
| Selfservice voor wachtwoordherstel (SSPR)    | Sta toe dat gebruikers hun wachtwoorden of accounts opnieuw kunnen instellen of ontgrendelen.  | Microsoft 365 E3 of E5 |
| Azure AD-toepassingsproxy    | Bied beveiligde externe toegang bieden voor webtoepassingen die worden gehost op intranetservers.   | Hiervoor is een afzonderlijk betaald Azure-abonnement vereist |
| Azure-punt-naar-site-VPN   | Maak een veilige verbinding tussen het apparaat van een externe werknemer en uw intranet via een virtueel Azure-netwerk.   | Hiervoor is een afzonderlijk betaald Azure-abonnement vereist |
| Windows Virtual Desktop   | Bied ondersteuning voor externe werknemers die alleen hun persoonlijke en niet-beheerde apparaten kunnen gebruiken met virtuele bureaubladen die worden uitgevoerd in Azure. | Hiervoor is een afzonderlijk betaald Azure-abonnement vereist |
| Extern bureaublad-services (RDS) | Geef werknemers toestemming om verbinding te maken met Windows-computers op uw intranet. | Microsoft 365 E3 of E5 | 
| Gateway voor extern bureaublad-services   | Versleutel de communicatie en voorkom dat de RDS-hosts rechtstreeks worden weergegeven op internet. | Hiervoor zijn afzonderlijke Windows Server-licenties vereist |
| Microsoft Intune | Beheer apparaten en toepassingen.   | Microsoft 365 E3 of E5 | 
| Configuration Manager | Software-installaties, updates en instellingen op uw apparaten beheren | Hiervoor zijn afzonderlijke Configuration Manager-licenties vereist |
| Desktop Analytics | Bepaal de updategereedheid van uw Windows-clients.   | Hiervoor zijn afzonderlijke Configuration Manager-licenties vereist |
| Windows Autopilot | Configureer de nieuwe Windows 10-apparaten vooraf voor productief gebruik.   | Microsoft 365 E3 of E5 |
| Microsoft Teams, Exchange Online, SharePoint Online en OneDrive, Microsoft 365-apps, Microsoft Power Platform en Yammer | Maak, communiceer en werk samen. | Microsoft 365 E3 of E5 |
||||

Raadpleeg [Beveiliging en compliance implementeren voor beveiligings- en compliancecriteria voor externe werknemers](empower-people-to-work-remotely-security-compliance.md).

<a name="poster"></a> Zie de [Poster Externe werknemers mogelijkheden bieden](../downloads/empower-remote-workers.pdf) voor een overzicht van twee pagina's van deze oplossing.

[![Poster Externe werknemers mogelijkheden bieden](../media/empower-people-to-work-remotely/empower-remote-workers-poster.png)](../downloads/empower-remote-workers.pdf)

Je kunt deze poster ook downloaden in [PDF-](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/empower-remote-workers.pdf) of [PowerPoint-](https://download.microsoft.com/download/5/1/1/511b77a9-a34c-4ea7-af2a-32b07f20b780/empower-remote-workers.pptx)indeling en afdrukken op papier met formaat Letter, Legal of Tabloid (27,9 x 43,2 cm).

## <a name="provide-remote-working-for-all-of-your-workers"></a>Thuiswerken aanbieden voor alle werknemers

U kunt ervoor zorgen dat alle werknemers overal productief kunnen blijven met deze apparaten:

- Een modern apparaat, zoals een Surface-laptop en Windows 10, met functies, beveiliging en prestaties voor toegang tot de cloud-apps en -services van Microsoft 365 rechtstreeks via het web.

- Elk apparaat, met inbegrip van oude laptops of desktops die worden gebruikt vanaf thuis, dat indirect toegang biedt tot Microsoft 365-cloud-apps en-services middels een snel geïmplementeerd [Windows 10 virtueel bureaublad](empower-people-to-work-remotely-remote-access.md#deploy-windows-virtual-desktop-to-provide-remote-access-for-remote-workers-using-personal-devices). Deze optie biedt hoge prestaties, krachtige beveiliging en vereenvoudigd IT-beheer.

## <a name="next-steps"></a>Volgende stappen

Gebruik de volgende stappen om de toegang tot de servers en cloudservices van je organisatie te beveiligen en optimaliseren, en je externe werknemers maximaal productief te laten zijn.

1. [Beveiliging van aanmelden verbeteren met MFA](empower-people-to-work-remotely-secure-sign-in.md)
2. [Externe toegang tot on-premises apps en services bieden](empower-people-to-work-remotely-remote-access.md)
3. [Beveiligings- en complianceservices implementeren](empower-people-to-work-remotely-security-compliance.md)
4. [Eindpuntbeheer voor uw apparaten, pc's en andere eindpunten implementeren](empower-people-to-work-remotely-manage-endpoints.md)
5. [Productiviteitsapps en -services voor externe medewerkers implementeren](empower-people-to-work-remotely-teams-productivity-apps.md)
6. [Externe werknemers trainen en voor feedback over gebruik zorgen](empower-people-to-work-remotely-train-monitor-usage.md)

[![De stappen voor het instellen van uw infrastructuur voor extern werk met Microsoft 365](../media/empower-people-to-work-remotely/remote-workers-step-grid.png)](empower-people-to-work-remotely-secure-sign-in.md)

Lees [De COVID-19-aanpak en de infrastructuur voor extern en onsite werken van Contoso](contoso-remote-onsite-work.md) als u wilt zien hoe een fictieve, maar representatieve multinational zijn infrastructuur heeft ingesteld voor extern werk.
