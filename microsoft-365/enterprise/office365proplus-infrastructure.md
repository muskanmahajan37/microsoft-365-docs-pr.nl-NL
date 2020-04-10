---
title: 'Fase 4: Office 365 ProPlus'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: De stappen om de Office 365 ProPlus-infrastructuur voor Microsoft 365 Enterprise te implementeren.
ms.openlocfilehash: 2b3ac311863249720a2dc1fba00ead9ebf6ac8e5
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42808422"
---
# <a name="phase-4-office-365-proplus"></a>Fase 4: Office 365 ProPlus

![Fase 4: Office 365 ProPlus](../media/deploy-foundation-infrastructure/O365proplus_icon.png)

*Dit geldt voor zowel E3- als E5-versies van Microsoft 365 Enterprise en Microsoft 365 Education*

Microsoft 365 Enterprise omvat Office 365 ProPlus, de abonnementsversie van Office. Net als Office 2019 biedt Office 365 ProPlus alle Office-toepassingen en worden deze toepassingen rechtstreeks op uw clientapparaten geïnstalleerd. In tegenstelling tot Office 2019 wordt Office 365 ProPlus regelmatig bijgewerkt met nieuwe functies en heeft het een licentiemodel voor gebruikers waarmee personen Office kunnen installeren op meerdere apparaten. Zie [Informatie over Office 365 ProPlus in de onderneming](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise) voor meer informatie.

In deze fase implementeert u Office 365 ProPlus op clientapparaten als onderdeel van Microsoft 365 Enterprise. Naast deze richtlijnen wordt u aangeraden gebruik te maken van [Microsoft Fastrack](https://fasttrack.microsoft.com/office) voor hulp bij de implementatie. 

Als u Office 365 ProPlus al hebt geïmplementeerd, bekijkt u het [afsluitcriterium](office365proplus-exit-criteria.md) voor deze fase om er zeker van te zijn dat deze voldoet aan de vereiste voorwaarden voor Microsoft 365 Enterprise.

>[!Note]
>Als u zowel Windows 10 Enterprise als Office 365 ProPlus samen wilt implementeren, raadpleegt u het [Desktop Deployment Center](desktop-deployment-center-home.md).
>

## <a name="step-1-assess-your-environment"></a>Stap 1: Uw omgeving evalueren

Voordat u Office 365 ProPlus gaat implementeren, volgt u de richtlijnen in [Uw omgeving en vereisten voor het implementeren van Office 365 ProPlus evalueren](https://docs.microsoft.com/DeployOffice/assess-office-365-proplus). Deze evaluatie omvat de systeemvereisten, details van uw clientapparaten (zoals architecturen en vereiste talen), licentievereisten, netwerkfunctionaliteit en toepassingscompatibiliteit. Door de beoordeling te voltooien, kunt u belangrijke beslissingen nemen als onderdeel van de planning van uw implementatie.

## <a name="step-2-plan-your-deployment"></a>Stap 2: Uw implementatie plannen

Nadat u uw omgeving hebt beoordeeld, volgt u de richtlijnen in [Uw implementatie van Office 365 ProPlus plannen](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus) voor het maken van een implementatieplan. Dit plan omvat de volgende beslissingen: 

- Het implementeren van Office, met inbegrip van het programma dat u gaat gebruiken (zoals Microsoft Endpoint Configuration Manager of het Office Deployment Tool) en waar u Office vanuit kunt installeren
- Updates voor Office beheren
- Welke updatekanalen te gebruiken (updatekanalen voor Office bepalen hoe vaak uw gebruikers functie-updates ontvangen voor hun Office-toepassingen)
- De Office-installatiepakketten en -implementatiegroepen die u wilt gebruiken, met inbegrip van welke Office-toepassingen en -talen geïnstalleerd moeten worden voor welke gebruikers

Het [planningsartikel](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus) bevat aanbevolen procedures voor al deze opties, waaronder het beheren van de implementatie, het beheren van uw updates, het definiëren van installatiepakketten en het maken van implementatiegroepen. 

## <a name="step-3-deploy"></a>Stap 3: Implementeren

Kies op basis van uw implementatieplan hoe u wilt implementeren:

- **[Office 365 ProPlus implementeren met Configuration Manager](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-with-system-center-configuration-manager):** Beheer uw implementatie met Configuration Manager en download en implementeer Office vanaf distributiepunten op uw netwerk

- **[Office 365 ProPlus implementeren met de ODT uit de Cloud](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-from-the-cloud):** Beheer uw implementatie met de ODT en installeer Office rechtstreeks vanuit het Office CDN op clientapparaten
 
- **[Office 365 ProPlus zelf installeren vanuit het Office-portal](https://docs.microsoft.com/deployoffice/manage-software-download-settings-office-365):** Beheer uw implementatie vanuit de Office-portal en laat uw gebruikers Office rechtstreeks vanuit de portal installeren op hun clientapparaten

Veel organisaties gebruiken een combinatie van deze opties voor verschillende gebruikers. Een organisatie kan bijvoorbeeld voor de meeste gebruikers Configuration Manager gebruiken om Office te implementeren, maar een kleine groep werknemers die niet regelmatig met het interne netwerk verbonden zijn zelf laten installeren. 

Als uw organisatie Configuration Manager gebruikt, raden we u aan een upgrade uit te voeren naar de Huidige vertakking en een update uit te voeren naar de huidige versie. Zie [Welke vertakking van Configuration Manager moet ik gebruiken?](https://docs.microsoft.com/configmgr/core/understand/which-branch-should-i-use) voor meer informatie

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Hoe Microsoft omgaat met Microsoft 365 Enterprise

Lees hoe de experts van Microsoft [updates voor Office 365 ProPlus implementeren en beheren](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR7).

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Hoe Contoso Microsoft 365 Enterprise gebruikt

Bekijk hoe de Contoso Corporation, een fictieve maar representatieve multinational, [Office 365 ProPlus heeft geïmplementeerd](contoso-o365pp.md).

![Contoso Corporation](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>Volgende stap

[Afsluitcriterium voor Office 365 ProPlus-infrastructuur](office365proplus-exit-criteria.md)