---
title: Stap 2. Externe toegang bieden tot on-premises apps en services
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
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
- m365solution-scenario
ms.custom: ''
description: Zorg ervoor dat uw externe medewerkers toegang hebben tot on-premises informatiebronnen terwijl de toegang tot Microsoft 365-cloudservices wordt geoptimaliseerd.
ms.openlocfilehash: 9fea86bb9c564a37a519d2c7e0ef2e2fd0a59470
ms.sourcegitcommit: e02cf5702af178ddd2968877a808874ecb49ed2c
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/26/2021
ms.locfileid: "52029132"
---
# <a name="step-2-provide-remote-access-to-on-premises-apps-and-services"></a>Stap 2. Externe toegang bieden tot on-premises apps en services

Als uw organisatie een VPN-oplossing voor externe toegang gebruikt, meestal met VPN-servers aan de rand van uw netwerk en VPN-clients geïnstalleerd op de apparaten van uw gebruikers, kunnen uw gebruikers VPN-verbindingen voor externe toegang gebruiken voor toegang tot on-premises apps en servers. Het kan zijn dat u het verkeer naar de Microsoft 365-cloudservices moet optimaliseren.

Als uw gebruikers geen VPN-oplossing gebruiken, kunt u Azure AD-toepassingsproxy (Active Directory) en Azure P2S-VPN (Point-to-Site) gebruiken om toegang te bieden, afhankelijk van het feit of al uw apps webversies zijn.

Dit zijn de belangrijkste configuraties voor externe toegang:

- U gebruikt al een VPN-oplossing voor externe toegang.
- U gebruikt geen VPN-oplossing voor externe toegang en u wilt dat uw externe werknemers hun persoonlijke computers kunnen gebruiken.
- U gebruikt geen VPN-oplossing voor externe toegang, u hebt een hybride identiteit en u hebt alleen externe toegang nodig tot on-premises web-apps.
- U gebruikt geen VPN-oplossing voor externe toegang en u hebt toegang nodig tot on-premises apps, waarvan sommige niet op internet zijn gebaseerd.

Bekijk deze stroomdiagram voor de configuratieopties voor externe toegang die in dit artikel worden beschreven.

![Stroomdiagram van configuratie voor externe toegang](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-flowchart.png)

Met externe toegangsverbindingen kunt u ook [Extern bureaublad](https://support.microsoft.com/help/4028379/windows-10-how-to-use-remote-desktop) gebruiken om uw gebruikers verbinding te laten maken met een on-premises pc. Een externe medewerker kan bijvoorbeeld Extern bureaublad gebruiken om verbinding te maken met de pc op zijn kantoor vanuit zijn Windows-, iOS- of Android-apparaat. Zodra hij extern verbinding heeft gemaakt, kan hij deze gebruiken alsof hij erachter zit.

## <a name="optimize-performance-for-remote-access-vpn-clients-to-microsoft-365-cloud-services"></a>Prestaties optimaliseren voor VPN-clients voor externe toegang tot Microsoft 365-cloudservices

Als uw externe medewerkers een traditionele VPN-client gebruiken om extern toegang te krijgen tot uw bedrijfsnetwerk, verifieer dan dat de VPN-client split tunneling ondersteunt.

Zonder split tunneling wordt al uw externe werk verzonden via de VPN-verbinding, terwijl het moet worden doorgestuurd naar de edge-apparaten van uw bedrijf, worden verwerkt en dan verzonden op internet.

![Netwerkverkeer van VPN-clients zonder tunneling](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-before-tunneling.png)

Microsoft 365-verkeer moet een indirecte route gebruiken binnen jouw organisatie en kan worden doorgestuurd naar een Microsoft-netwerkingangspunt ver van de fysieke locatie van de VPN-client vandaan. Met dit indirecte pad wordt een vertraging toegevoegd aan het netwerkverkeer en wordt de algehele prestatie negatief beïnvloed.  

Met split tunneling kunt u uw VPN-client zo configureren dat specifieke typen verkeer niet via de VPN-verbinding naar het bedrijfsnetwerk worden verzonden.

Configureer uw split tunneling VPN-clients zodanig dat verkeer wordt uitgesloten naar de Microsoft 365-eindpuntcategorie **Optimaliseren** over de VPN-verbinding om toegang tot Microsoft 365-cloudresources te optimaliseren. Zie [Office 365-eindpuntcategorieën](../enterprise/microsoft-365-network-connectivity-principles.md#new-office-365-endpoint-categories) voor meer informatie.  Bekijk [de lijst](../enterprise/urls-and-ip-address-ranges.md) met eindpunten met categorie Optimaliseren.

Hier vindt u de stroom die het resultaat is van de gegevensoverdracht, waarin de meeste verkeer naar Cloud-apps voor Microsoft 365 de VPN-verbinding omzeilen.

![Netwerkverkeer van VPN-clients met tunneling](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-after-tunneling.png)

Hiermee kan de VPN-client cruciaal Microsoft 365-cloudserviceverkeer direct over internet verzenden en ontvangen en via het dichtstbijzijnde ingangspunt in het Microsoft-netwerk.

Bekijk [Office 365-connectiviteit optimaliseren voor externe gebruikers met VPN-split-tunneling](../enterprise/microsoft-365-vpn-split-tunnel.md) voor meer informatie en richtlijnen.

## <a name="deploy-remote-access-when-all-your-apps-are-web-apps-and-you-have-hybrid-identity"></a>Externe toegang implementeren wanneer al uw apps web-apps zijn en u een hybride identiteit hebt

Als uw externe medewerkers geen traditionele VPN-client gebruiken en uw on-premises gebruikersaccounts en -groepen worden gesynchroniseerd met Azure AD, kunt u Azure AD-toepassingsproxy gebruiken om veilige externe toegang te bieden voor webtoepassingen die worden gehost op lokale servers. Webtoepassingen omvatten onder meer SharePoint Server-sites, Outlook-webtoegangsservers of andere bedrijfswebtoepassingen. 

Hier vindt u de onderdelen van Azure AD-toepassingsproxy.

![Onderdelen van Azure AD-toepassingsproxy](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-application-proxy.png)

Zie dit [overzicht van Azure AD-toepassingsproxy](/azure/active-directory/manage-apps/application-proxy)voor meer informatie.

>[!Note]
>Azure AD-toepassingsproxy maakt geen deel uit van een Microsoft 365-abonnement. U moet betalen voor het gebruik met een afzonderlijk Azure-abonnement.
>

## <a name="deploy-remote-access-when-not-all-your-apps-are-web-apps"></a>Externe toegang implementeren wanneer niet al uw apps web-apps zijn

Als uw externe medewerkers geen traditionele VPN-client gebruiken en sommige van uw apps zijn geen web-apps, kunt u een Azure P2S-VPN (Point-to-Site) gebruiken.

Een P2S VPN-verbinding maakt een beveiligde verbinding met uw bedrijfsnetwerk vanaf het apparaat van de externe medewerker via een virtueel Azure-netwerk. 

![Onderdelen van Azure P2S VPN](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-p2s-vpn.png)

Zie dit [overzicht van P2S VPN](/azure/vpn-gateway/point-to-site-about) voor meer informatie.

>[!Note]
>Azure P2S VPN maakt geen deel uit van een Microsoft 365-abonnement. U moet betalen voor het gebruik met een afzonderlijk Azure-abonnement.
>

## <a name="deploy-windows-virtual-desktop-to-provide-remote-access-for-remote-workers-using-personal-devices"></a>Windows-virtueel bureaublad implementeren om externe toegang te bieden voor externe medewerkers met persoonlijke apparaten 

Om externe medewerkers te ondersteunen die alleen hun persoonlijke en onbeheerde apparaten kunnen gebruiken, gebruikt u Windows-virtueel bureaublad in Azure om virtuele bureaubladen te maken en toe te wijzen aan uw gebruikers die thuiswerken. Gevirtualiseerde pc's werken net als pc's die verbinding hebben met uw bedrijfsnetwerk.

![Onderdelen van Azure Windows Virtual Desktop](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-windows-virtual-desktop.png)

Voor meer informatie raadpleegt u dit [overzicht van Windows-virtueel bureaublad](/azure/virtual-desktop/overview). 

>[!Note]
>Windows Virtual Desktop maakt geen deel uit van een Microsoft 365-abonnement. U moet betalen voor het gebruik met een afzonderlijk Azure-abonnement.
>

## <a name="protect-your-remote-desktop-services-connections-with-the-remote-desktop-services-gateway"></a>Verbindingen voor Extern bureaublad-services beveiligen met de Extern bureaublad-servicesgateway

Als u Extern bureaublad-services (RDS) gebruikt om medewerkers verbinding te laten maken met Windows-computers in het on-premises-netwerk, moet u een Extern bureaublad-servicesgateway van Microsoft in het edgenetwerk gebruiken. De gateway maakt gebruik van Transport Layer Security (TLS) om verkeer te versleutelen en voorkomt dat de lokale computer die als host fungeert voor RDS een onveilige verbinding heeft met internet.

![Verbindingen voor Extern bureaublad-services met de Extern bureaublad-servicesgateway](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-remote-desktop.png)

Zie [dit artikel](https://www.microsoft.com/security/blog/2020/04/16/security-guidance-remote-desktop-adoption/) voor meer informatie.

## <a name="admin-technical-resources-for-remote-access"></a>Technische bronnen voor beheerders voor externe toegang

- [Office 365-verkeer snel optimaliseren voor externe medewerkers en de belasting van uw infrastructuur verminderen](https://techcommunity.microsoft.com/t5/office-365-blog/how-to-quickly-optimize-office-365-traffic-for-remote-staff-amp/ba-p/1214571)
- [Office 365-connectiviteit optimaliseren voor externe gebruikers met VPN-split-tunneling](../enterprise/microsoft-365-vpn-split-tunnel.md)

## <a name="results-of-step-2"></a>Resultaten van stap 2

Na de implementatie van een oplossing voor externe toegang voor uw externe medewerkers:

| Configuratie voor externe toegang | Resultaten |
|:-------|:-----|
| Er is een VPN-oplossing voor externe toegang geïnstalleerd | U hebt uw VPN-client voor externe toegang voor split tunneling en de Microsoft 365-eindpuncategorie Optimaliseren geconfigureerd. |
| Geen VPN-oplossing voor externe toegang en u hebt alleen externe toegang nodig tot on-premises web-apps | U hebt Azure-toepassingsproxy geconfigureerd. |
| Geen VPN-oplossing voor externe toegang en u hebt externe toegang nodig tot on-premises apps, waarvan sommige niet op internet zijn gebaseerd | U hebt Azure P2S VPN geconfigureerd. |
| Externe medewerkers gebruiken hun persoonlijke apparaten thuis | U hebt Windows-virtueel bureaublad geconfigureerd. |
| Externe werknemers gebruiken RDS om verbinding te maken met on-premises-systemen | U hebt een Extern bureaublad-servicesgateway in het edgenetwerk geïmplementeerd. |
|||

## <a name="next-step"></a>Volgende stap

[![Stap 3: Beveiligings- en complianceservices van Microsoft 365 implementeren](../media/empower-people-to-work-remotely/remote-workers-step-grid-3.png)](empower-people-to-work-remotely-security-compliance.md)

Ga verder met [stap 3](empower-people-to-work-remotely-security-compliance.md) om beveiligings- en complianceservices van Microsoft 365 te implementeren om uw apps, gegevens en apparaten te beveiligen.