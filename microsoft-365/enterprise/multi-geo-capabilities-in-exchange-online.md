---
title: Exchange Multi-Geo
ms.reviewer: adwood
ms.author: chrisda
author: chrisda
manager: serdars
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
localization_priority: Normal
description: Meer informatie over multi-geo-mogelijkheden in Exchange Online, zoals functiebeperkingen en postvakpositie.
ms.openlocfilehash: bf1c3c8f510c57f47cbfc7b2609d97f5932e05d3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923730"
---
# <a name="multi-geo-capabilities-in-exchange-online"></a>Multi-Geo-mogelijkheden in Exchange Online

In een multi-geo-omgeving kunt u per gebruiker de locatie van exchange Online-postvakinhoud (gegevens in rust) selecteren.

U kunt postvakken op satellietlocaties plaatsen op:

- Een nieuw Exchange Online-postvak rechtstreeks op een satellietlocatie maken.

- Een bestaand Exchange Online-postvak verplaatsen naar een satellietlocatie door de gewenste gegevenslocatie van de gebruiker te wijzigen.

- Een postvak van een on-premises Exchange-organisatie rechtstreeks in een satellietlocatie onboarden.

## <a name="mailbox-placement-and-moves"></a>Postvak plaatsen en verplaatst

Nadat Microsoft de vereiste stappen voor multi-geoconfiguratie heeft voltooid, wordt in Exchange Online het **kenmerk PreferredDataLocation** op gebruikersobjecten in Azure AD in ere gehouden.

Exchange Online synchroniseert de **eigenschap PreferredDataLocation** van Azure AD naar de **eigenschap MailboxRegion** in de Exchange Online-adreslijstservice. De waarde van **PostvakRegio bepaalt** de geografische locatie waar gebruikerspostvakken en bijbehorende archiefpostvakken worden geplaatst. Het is niet mogelijk om het primaire postvak en archiefpostvakken van een gebruiker zo te configureren dat deze zich op verschillende geografische locaties bevinden. Er kan slechts één geografische locatie worden geconfigureerd per gebruikersobject.

- Wanneer **PreferredDataLocation** is geconfigureerd op een gebruiker met een bestaand postvak, wordt het postvak in een relocatiewachtrij geplaatst en automatisch verplaatst naar de opgegeven geografische locatie.

- Wanneer **PreferredDataLocation** is geconfigureerd voor een gebruiker zonder een bestaand postvak, wordt het postvak ingesteld op de opgegeven geografische locatie.

- Wanneer **PreferredDataLocation** niet is opgegeven voor een gebruiker, wordt het postvak ingericht op de centrale geolocatie wanneer u het inrichten.

- Als de **PreferredDataLocation-code** onjuist is (bijvoorbeeld een type NAN in plaats van NAM), wordt het postvak ingericht op de centrale geolocatie.

**Opmerking:** Multi-geo-mogelijkheden en regionaal gehoste vergaderingen van Skype voor Bedrijven Online gebruiken beide de eigenschap **PreferredDataLocation** op gebruikersobjecten om services te zoeken. Als u **PreferredDataLocation-waarden** configureert op gebruikersobjecten voor regionaal gehoste vergaderingen, wordt het postvak voor deze gebruikers automatisch verplaatst naar de opgegeven geografische locatie nadat multi-geo is ingeschakeld op de Microsoft 365-tenant.

## <a name="feature-limitations-for-multi-geo-in-exchange-online"></a>Functiebeperkingen voor multi-geo in Exchange Online

- Beveiligings- en compliancefuncties (bijvoorbeeld auditing en eDiscovery) die beschikbaar zijn in het Exchange-beheercentrum (EAC) zijn niet beschikbaar in multi-geo-organisaties. In plaats daarvan moet u het [Microsoft 365-beveiligingscentrum & gebruiken](https://support.office.com/article/7e696a40-b86b-4a20-afcc-559218b7b1b8) om beveiligings- en compliancefuncties te configureren.

- Outlook voor Mac-gebruikers hebben mogelijk tijdelijk geen toegang meer tot de map Onlinearchief terwijl u hun postvak verplaatst naar een nieuwe geografische locatie. Deze voorwaarde treedt op wanneer de primaire postvakken en archiefpostvakken van de gebruiker zich op verschillende geografische locaties bevinden, omdat het cross-geopostvak op verschillende tijdstippen kan worden verplaatst.

- Gebruikers kunnen postvakmappen *niet* delen op geografische locaties in de webversie van Outlook (voorheen bekend als Outlook Web App of OWA). Een gebruiker in de Europese Unie kan bijvoorbeeld de webversie van Outlook niet gebruiken om een gedeelde map te openen in een postvak in de Verenigde Staten. Gebruikers van De webversie  van Outlook kunnen echter andere postvakken op verschillende geografische locaties openen met behulp van een afzonderlijk browservenster, zoals beschreven in Het postvak van een andere persoon openen in een afzonderlijk [browservenster in Outlook Web App.](https://support.office.com/article/A909AD30-E413-40B5-A487-0EA70B763081#__toc372210362)

  **Opmerking:** Het delen van mappen met verschillende geografische postvakken wordt ondersteund in Outlook voor Windows.

- Openbare mappen worden ondersteund in multi-geo-organisaties. De openbare mappen moeten echter op de centrale geografische locatie blijven staan. U kunt geen openbare mappen verplaatsen naar satellietlocatielocaties.

- In een multi-geo-omgeving wordt cross-geopostvakcontrole niet ondersteund. Als een gebruiker bijvoorbeeld machtigingen krijgt toegewezen voor toegang tot een gedeeld postvak op een andere geografische locatie, worden postvakacties die door die gebruiker worden uitgevoerd, niet aangemeld in het postvakauditlogboek van het gedeelde postvak. Zie Postvakcontrole beheren voor [meer informatie.](../compliance/enable-mailbox-auditing.md?view=o365-worldwide)