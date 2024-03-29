---
title: Gereedheidsbeoordelingshulpmiddelen
description: Uitleg over de twee hulpmiddelen, de controles die worden uitgevoerd en de betekenis van de resultaten
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: caf9274284548a179e088131930ae832c098b521
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579396"
---
# <a name="readiness-assessment-tools"></a>Gereedheidsbeoordelingshulpmiddelen

Voor een zo soepel mogelijke ervaring wanneer u zich inschrijft voor Microsoft Managed Desktop, zijn er instellingen en andere parameters die u van tevoren moet instellen en bepaalde apparaat- en netwerkvereisten om te voldoen. Eén hulpprogramma, geopend via de Microsoft Managed Desktop Admin-portal, controleert beheergerelateerde instellingen. Een ander hulpprogramma, dat kan worden gedownload, controleert de vereisten van afzonderlijke apparaten en netwerkinstellingen. U kunt deze hulpprogramma's gebruiken om deze instellingen te controleren en gedetailleerde stappen te ontvangen voor het oplossen van fouten die niet juist zijn.

## <a name="downloadable-readiness-assessment-checker-for-devices-and-network"></a>Downloadbare gereedheidsbeoordelingscontrole voor apparaten en netwerk

Zie [Downloadable readiness assessment checker (Downloadable readiness assessment checker)](readiness-assessment-downloadable.md)voor meer informatie over het gebruik van de evaluatiecontrole voor downloadbare gereedheid.

## <a name="online-readiness-assessment-tool-for-management-settings"></a>Online gereedheidsbeoordelingshulpmiddel voor beheerinstellingen

Met [het onlinehulpprogramma](https://aka.ms/mmdart) worden instellingen gecontroleerd in Microsoft Endpoint Manager (met name Microsoft Intune), Azure Active Directory (Azure AD) en Microsoft 365 om ervoor te zorgen dat ze werken met Microsoft Managed Desktop. Microsoft Managed Desktop behoudt de gegevens die aan deze controles zijn gekoppeld, 12 maanden na de laatste keer dat u een check in uw Azure AD-organisatie (tenant) hebt uitgevoerd. Na 12 maanden bewaren we het in gedeïdentificeerde vorm. U kunt ervoor kiezen om de gegevens die we verzamelen te verwijderen.

Iedereen met ten minste de rol Globale lezer of Intune-beheerder kan dit hulpprogramma uitvoeren, maar twee van de controles[(Beleid](readiness-assessment-fix.md#conditional-access-policies) voor voorwaardelijke toegang en [Meervoudige](readiness-assessment-fix.md#multifactor-authentication) verificatie vereisen extra machtigingen.
 
Met het beoordelingshulpmiddel worden de volgende items gecontroleerd:

## <a name="microsoft-intune-settings"></a>Microsoft Intune-instellingen

|Cheque  |Omschrijving  |
|---------|---------|
|Autopilot-implementatieprofiel     | Controleert of de toewijzing van het Autopilot-implementatieprofiel niet  van toepassing is op alle apparaten (Het profiel mag niet worden toegewezen aan een Microsoft Managed Desktop-apparaat.)       |
|Connectors voor certificaten     | Controleert de status van certificaatconnectoren om ervoor te zorgen dat ze actief zijn   |
|Voorwaardelijke toegang     | Controleert of beleid voor voorwaardelijke toegang niet aan alle gebruikers is toegewezen (Beleid voor voorwaardelijke toegang *mag* niet worden toegewezen aan Microsoft Managed Desktop-serviceaccounts.)    |
|Beleid voor apparaat compliance     | Hiermee wordt gecontroleerd of intune-compliancebeleid niet aan  alle gebruikers is toegewezen (Het beleid mag niet worden toegewezen aan microsoft beheerde bureaubladapparaten.)    |
|Apparaatconfiguratieprofielen     | Bevestigt dat configuratieprofielen niet zijn toegewezen aan alle gebruikers  of alle apparaten (Configuratieprofielen mogen niet worden toegewezen aan microsoft beheerde bureaubladapparaten.)     |
|Beperkingen voor apparaattype     | Hiermee wordt gecontroleerd of Windows 10-apparaten in uw organisatie mogen worden ingeschreven bij Intune        |
|Pagina Inschrijvingsstatus     | Bevestigt dat de pagina Inschrijvingsstatus niet is ingeschakeld      |
|Inschrijving voor Intune     | Controleert of Windows 10-apparaten in uw Azure AD-organisatie automatisch zijn geregistreerd in Intune         |
|Microsoft Store voor Bedrijven     | Bevestigt dat Microsoft Store voor Bedrijven is ingeschakeld en gesynchroniseerd met Intune        |
|Meervoudige verificatie | Controleert of meervoudige verificatie niet wordt toegepast op serviceaccounts van Microsoft Managed Desktop.
|PowerShell-scripts     | Hiermee wordt gecontroleerd of Windows PowerShell-scripts *niet* zijn toegewezen op een manier die is gericht op Beheerde bureaubladapparaten van Microsoft    |
|Regio     | Controleert of uw regio wordt ondersteund door Microsoft Managed Desktop        |
|Beveiligingslijnlijnen     | Hiermee wordt gecontroleerd of het beveiligingslijnprofiel niet op alle  gebruikers of alle apparaten is gericht (Beleid voor basislijnbeveiliging mag niet zijn gericht op beheerde bureaubladapparaten van Microsoft.)       |
|Windows-apps     | Controleren welke apps u wilt toewijzen aan Microsoft Managed Desktop-apparaten      |
|Windows Hello voor Bedrijven     | Hiermee wordt gecontroleerd of Windows Hello voor Bedrijven is ingeschakeld        |
|Windows 10 update ring     | Hiermee wordt gecontroleerd of intune's updateringbeleid voor Windows 10 niet op  alle gebruikers of alle apparaten is gericht (Het beleid is niet gericht op alle beheerde bureaubladapparaten van Microsoft.)     |


## <a name="azure-active-directory-settings"></a>Azure Active Directory-instellingen

|Cheque  |Omschrijving  |
|---------|---------|
|'Ad hoc'-abonnementen voor Enterprise State Roaming     | Wordt geadviseerd hoe u een instelling controleert die (indien ingesteld op 'onwaar') kan voorkomen dat Enterprise State Roaming correct werkt  |
|Enterprise State Roaming     | Adviseert hoe u controleert of Enterprise State Roaming is ingeschakeld       |
|Licenties     | Controleert of u de benodigde [licenties hebt verkregen](prerequisites.md#more-about-licenses)         |
|Meervoudige verificatie     | Hiermee wordt gecontroleerd of meervoudige verificatie niet wordt toegepast op alle gebruikers (Meervoudige verificatie mag niet per ongeluk worden toegepast op Microsoft Managed Desktop-serviceaccounts.)|
|Namen van beveiligingsaccounts   | Hiermee wordt gecontroleerd of er geen gebruikersnamen conflicteren met de namen die door Microsoft Managed Desktop zijn voorbehouden voor eigen gebruik        |
|Beveiligingsbeheerdersrollen     | Bevestigt dat gebruikers met beveiligingslezer- of beveiligingsoperator- of globale lezerrollen zijn toegewezen aan deze rollen in Microsoft Defender voor Eindpunt         |
|Standaardinstellingen voor beveiliging | Hiermee wordt gecontroleerd of uw Azure AD-organisatie beveiligingsinstellingen heeft ingeschakeld in Azure Active Directory |
|Self-service voor wachtwoordherstel     | Bevestigt dat het opnieuw instellen van selfservicewachtwoord is ingeschakeld        |
|Standaardgebruikerrol     | Controleert of gebruikers standaardgebruikers zijn en geen lokale beheerdersrechten hebben         |


## <a name="microsoft-365-apps-for-enterprise-settings"></a>Microsoft 365 Apps voor bedrijfsinstellingen

|Cheque  |Omschrijving  |
|---------|---------|
|OneDrive voor Bedrijven     | Hiermee wordt gecontroleerd of OneDrive voor Bedrijven niet-ondersteunde instellingen gebruikt.        |


Voor elke controle rapporteert het hulpprogramma een van de vier mogelijke resultaten:


|Resultaat  |Betekenis  |
|---------|---------|
|Gereed     | Er is geen actie vereist voordat u de inschrijving voltooit.        |
|Advies    | Volg de stappen in het hulpprogramma voor de beste ervaring met registratie en voor gebruikers. U *kunt* de inschrijving voltooien, maar u moet deze problemen oplossen voordat u uw eerste apparaat implementeert.        |
|Nog niet klaar | *De inschrijving mislukt als* u deze problemen niet op kunt lossen. Volg de stappen in het hulpprogramma om deze op te lossen.        |
|Error | De Ad-rol (Azure Active Director) die u gebruikt, heeft niet voldoende machtigingen om deze controle uit te voeren. |

## <a name="after-enrollment"></a>Na inschrijving

Nadat u de inschrijving in Microsoft Managed Desktop hebt voltooid, vergeet niet om bepaalde Instellingen voor Intune en Azure AD aan te passen. Zie Instellingen aanpassen [na inschrijving voor meer informatie.](../get-started/conditional-access.md)

## <a name="steps-to-get-ready"></a>Stappen om u klaar te maken

1. Controleer [vereisten voor Microsoft Managed Desktop](prerequisites.md).
2. Gebruik [gereedheidsbeoordelingshulpmiddelen.](readiness-assessment-tool.md) (Dit artikel)
3. [Vereisten voor gast-accounts](guest-accounts.md)
4. [Netwerkconfiguratie voor Microsoft Managed Desktop](network.md)
5. [Certificaten en netwerkprofielen voorbereiden voor Microsoft Managed Desktop](certs-wifi-lan.md)
6. [Toegang voorbereiden tot on-premises bronnen voor Microsoft Managed Desktop](authentication.md)
7. [Apps in Microsoft Managed Desktop](apps.md)
8. [Toegewezen stations voorbereiden voor Microsoft Managed Desktop](mapped-drives.md)
9. [Printbronnen voorbereiden voor Microsoft Managed Desktop](printing.md)
