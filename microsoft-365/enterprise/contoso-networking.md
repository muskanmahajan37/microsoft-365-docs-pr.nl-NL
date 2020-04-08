---
title: Netwerken voor de Contoso Corporation
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: De Contoso-netwerkinfrastructuur en hoe deze de SD-WAN-technologie gebruikt voor optimale netwerkprestaties bij Microsoft 365 Enterprise-cloudservices begrijpen.
ms.openlocfilehash: 20279ac0aed1b7ad86e1fc8e1d78a412230eba52
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42806076"
---
# <a name="networking-for-the-contoso-corporation"></a>Netwerken voor de Contoso Corporation

Om een cloud-inclusieve infrastructuur te implementeren, hebben de netwerkengineers van Contoso een fundamentele verschuiving gerealiseerd in de manier waarop netwerkverkeer naar cloudservices wordt geleid. In plaats van een intern hub-and-spoke-model waarin netwerkconnectiviteit en netwerkverkeer wordt gericht op het volgende niveau van de kantoorhiërarchie van Contoso, hebben ze gebruikerslocaties aan lokale internet-uitgangen en lokale verbindingen aan de dichtstbijzijnde Microsoft 365-netwerklocatie op het internet gekoppeld.

## <a name="contosos-networking-infrastructure"></a>Netwerkinfrastructuur van Contoso

De elementen van het netwerk van Contoso die hun kantoren op de hele wereld koppelen, zijn de volgende:

- Multiprotocol-Label Switching (MPLS) WAN-netwerk

  Een MPLS WAN-netwerk verbindt het hoofdkantoor in Parijs met regionale kantoren en regionale kantoren met satellietkantoren in een hub-and-spoke-configuratie. Zo hebben gebruikers toegang tot servers op locatie met Line of Business-toepassingen in het kantoor in Parijs. Het leidt ook al het algemene internetverkeer naar het kantoor in Parijs, waar netwerkbeveiligingsapparaten de verzoeken beoordelen. Binnen elke kantoor leiden routers het verkeer naar draadgebonden hosts of draadloze toegangspunten op subnetten, die gebruikmaken van de particuliere IP-adresruimte.

- Lokale rechtstreekse internettoegang voor Microsoft 365-verkeer

  Elk kantoor heeft een softwaregedefinieerd WAN-apparaat met een of meer lokale netwerkcircuits van de internetprovider en een eigen internetverbinding via een proxyserver. Dit wordt meestal geïmplementeerd als een WAN-koppeling naar een lokale internetprovider die ook openbare IP-adressen en een lokale DNS-server biedt.

- Internetaanwezigheid

  Contoso is de eigenaar van de openbare domeinnaam contoso.com. De openbare website van Contoso voor het bestellen van producten draait op een reeks servers in een op het internet aangesloten datacenter op de campus in Parijs. Contoso gebruikt een /24 openbaar IP-adresbereik op het internet.

Afbeelding 1 toont de netwerkinfrastructuur van Contoso en de bijbehorende verbindingen met het internet.

![Het netwerk van Contoso](../media/contoso-networking/contoso-networking-fig1.png)
 
**Afbeelding 1: Het netwerk van Contoso**

## <a name="use-of-sd-wan-for-optimal-network-connectivity-to-microsoft"></a>Gebruik van SD-WAN voor optimale netwerkconnectiviteit met Microsoft

Contoso heeft de [Beginselen voor Office 365-netwerkconnectiviteit](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles) gevolgd om:

1. Netwerkverkeer van Office 365 te identificeren en te onderscheiden
2. Lokale uitgangen van netwerkverbindingen te regelen
3. Netwerk-hairpins te vermijden
4. Dubbele netwerkbeveiligingsapparaten te omzeilen

Er zijn drie categorieën netwerkverkeer voor Office 365: Optimaliseren, toestaan en standaard. Verkeer in de categorieën Optimaliseren en Toestaan is betrouwbaar netwerkverkeer dat versleuteld en beveiligd is bij de eindpunten en is bestemd voor het Microsoft 365-netwerk.

Contoso heeft besloten om:

- Directe internetuitgangen te gebruiken voor verkeer uit de categorieën Optimaliseren en Toestaan en voor het doorsturen van al het verkeer in de categorie Standaard naar de centrale internetverbinding met Parijs.

- Op elk van hun kantoorlocaties SD-WAN-apparaten te implementeren om deze principes op een eenvoudige manier toe te passen en optimale netwerkprestaties te bereiken voor de cloudservices van Microsoft 365.

  De SD-WAN-apparaten hebben een LAN-poort voor het lokale kantoornetwerk en meerdere WAN-poorten. Een WAN-poort maakt verbinding met het MPLS-netwerk en een andere WAN-poort maakt verbinding met een lokaal ISP-circuit. Het SD-WAN-apparaat leidt netwerkverkeer uit de categorieën Optimaliseren en Toestaan via de ISP-koppeling.

## <a name="contosos-line-of-business-app-infrastructure"></a>De Line of Business-toepassingeninfrastructuur van Contoso

Contoso heeft haar Line of Business-toepassingen- en serverintranetinfrastructuur ingericht voor het volgende:

- Satellietkantoren gebruiken lokale cacheservers voor het opslaan van veelgebruikte documenten en interne websites.
- Regionale hubs gebruiken regionale toepassingsservers voor de regionale en satellietkantoren. Deze servers worden gesynchroniseerd met servers in het hoofdkantoor in Parijs.
- Op de campus in Parijs bevinden zich datacenters met gecentraliseerde toepassingsservers waar de hele organisatie gebruik van maakt.

Afbeelding 2 toont het percentage van netwerkverkeer bij het verkrijgen van toegang tot servers in het intranet van contoso.

![De infrastructuur van Contoso voor interne toepassingen](../media/contoso-networking/contoso-networking-fig2.png)
 
**Afbeelding 2: De infrastructuur van Contoso voor interne toepassingen**

Voor gebruikers op satelliet- of regionale hub-kantoren kan 60% van de resources die nodig zijn voor werknemers worden bediend door satelliet- en regionale kantoorservers. De extra 40% van de resourceaanvragen moet via de WAN-koppeling naar de campus in Parijs worden geleid.

## <a name="contosos-network-analysis-and-preparation-of-their-network-for-microsoft-365-enterprise"></a>Netwerkanalyse en -voorbereiding van Contoso voor Microsoft 365 Enterprise

Een succesvolle ingebruikname van Microsoft 365 Enterprise-services door de gebruikers van Contoso is afhankelijk van goed beschikbare en presterende verbinding met het internet of rechtstreekse verbinding met de cloudservices van Microsoft. Contoso nam de volgende stappen voor het plannen en implementeren van geoptimaliseerde connectiviteit met de cloudservices van Microsoft 365 Enterprise:

1. Een WAN-netwerkdiagram van het bedrijf gemaakt om te helpen bij de planning

   Contoso heeft de netwerkplanning gestart door een diagram te maken met de bijbehorende locaties, de bestaande netwerkconnectiviteit, de bestaande apparaten voor de netwerkperimeter en de klassen van de service die worden beheerd op het netwerk. Ze hebben deze diagram gebruikt voor elke daaropvolgende stap in de planning en tijdens de implementatie van netwerkconnectiviteit.

2. Een plan gemaakt voor de Microsoft 365 Enterprise-netwerkconnectiviteit

   Contoso heeft de [Basisprincipes voor Office 365-netwerkconnectiviteit](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles) en netwerkarchitecturen ter referentie geleverd om SD-WAN vast te leggen als gewenste topologie voor Office 365-connectiviteit.

3. Het verbruik van de internetverbinding en de MPLS WAN-bandbreedte op elke kantoor geanalyseerd en de bandbreedte indien nodig verhoogd

   Het huidige verbruik van elk kantoor is geanalyseerd en circuits zijn uitgebreid, zodat het verwachte verkeer in de Microsoft 365 Cloud zou worden uitgevoerd met een gemiddelde van 20% aan de niet-gebruikte capaciteit.

4. Optimale prestaties van Microsoft-netwerkservices

   Contoso heeft de set met Office 365-, Intune- en Azure-eindpunten vastgesteld en firewalls, beveiligingsapparaten en andere systemen in het internetpad geconfigureerd voor optimale prestaties. Eindpunten voor Office 365-verkeer in de categorieën Optimaliseren en Toestaan zijn in de SD-WAN-apparaten geconfigureerd voor routering via het ISP-circuit.

5. Interne DNS geconfigureerd

   DNS moet functioneel zijn en lokaal worden opgezocht voor Office 365-verkeer.

6. Gevalideerd netwerkeindpunt en poortconnectiviteit

   Contoso heeft testhulpprogramma's voor netwerkconnectiviteit van Microsoft gebruikt om de connectiviteit voor de cloudservices van Microsoft 365 Enterprise te valideren.

7. Computers van werknemers geoptimaliseerd voor netwerkconnectiviteit

   Afzonderlijke computers zijn gecontroleerd om te controleren of de meest recente updates voor het besturingssysteem geïnstalleerd waren en controle van de eindpuntbeveiliging bij alle clients actief was.

## <a name="next-step"></a>Volgende stap

[Lees hier meer](contoso-identity.md) over hoe Contoso op locatie Active Directory Domain Services (AD DS) in de Cloud gebruikt voor werknemers en federatieve verificatie voor klanten en zakenpartners.

## <a name="see-also"></a>Zie ook

[Netwerken voor Microsoft 365 Enterprise](networking-infrastructure.md)

[Implementatiehandleiding](deploy-microsoft-365-enterprise.md)

[Testlabrichtlijnen](m365-enterprise-test-lab-guides.md)