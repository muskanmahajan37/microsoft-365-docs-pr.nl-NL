---
title: Versleuteling instellen in Office 365 Enterprise
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/2/2018
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e86fc991-0161-4f01-9c1c-d25e87733d06
description: Met Office 365 zijn sommige versleutelingsmogelijkheden standaard ingeschakeld. andere mogelijkheden kunnen worden geconfigureerd om te voldoen aan bepaalde nalevings- of wettelijke vereisten.
ms.openlocfilehash: 688d34d767a546cb97d940ab2141bb3edfabcda8
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/24/2021
ms.locfileid: "52625231"
---
# <a name="set-up-encryption-in-office-365-enterprise"></a>Versleuteling instellen in Office 365 Enterprise

Versleuteling kan voorkomen dat uw inhoud wordt gelezen door onbevoegde gebruikers. Omdat [versleuteling in Office 365](encryption.md) kan worden uitgevoerd met behulp van verschillende technologieën en methoden, is er niet één plek waar u versleuteling in- of in- of uit te stellen. In dit artikel vindt u informatie over verschillende manieren waarop u versleuteling kunt instellen of configureren als onderdeel van uw informatiebeveiligingsstrategie.

> [!TIP]
> Als u op zoek bent naar meer technische details over versleuteling, zie Technische informatie over [versleuteling in Office 365.](technical-reference-details-about-encryption.md)

Met Office 365 zijn er standaard verschillende versleutelingsmogelijkheden beschikbaar. Aanvullende versleutelingsmogelijkheden kunnen worden geconfigureerd om te voldoen aan bepaalde nalevings- of wettelijke vereisten. In de volgende tabel worden verschillende versleutelingsmethoden voor verschillende scenario's beschreven.

<br>

****

|Scenario|Versleutelingsmethoden|
|---|---|
|Bestanden worden opgeslagen op Windows computers|Versleuteling op computerniveau kan worden uitgevoerd met BitLocker op Windows apparaten. Als bedrijfsbeheerder of IT-Pro kunt u dit instellen met behulp van de Microsoft Deployment Toolkit (MDT). Zie [MDT instellen voor BitLocker.](/windows/deployment/deploy-windows-mdt/set-up-mdt-for-bitlocker)|
|Bestanden worden opgeslagen op mobiele apparaten|Sommige soorten mobiele apparaten versleutelen bestanden die standaard op die apparaten zijn opgeslagen. Met [de mogelijkheden van ingebouwde Mobile Device Management voor Office 365](https://support.microsoft.com/office/capabilities-of-built-in-mobile-device-management-for-microsoft-365-a1da44e5-7475-4992-be91-9ccec25905b0)kunt u beleidsregels instellen waarmee wordt bepaald of mobiele apparaten toegang mogen krijgen tot gegevens in Office 365. U kunt bijvoorbeeld een beleid instellen waarmee alleen apparaten die inhoud versleutelen toegang hebben tot Office 365 gegevens. Zie [Apparaatbeveiligingsbeleid maken en implementeren.](https://support.microsoft.com/office/create-and-deploy-device-security-policies-d310f556-8bfb-497b-9bd7-fe3c36ea2fd6) <p> Voor meer controle over hoe mobiele apparaten met Office 365 werken, kunt u overwegen om [Microsoft Intune.](/mem/intune/fundamentals/setup-steps)|
|U hebt controle nodig over de versleutelingssleutels die worden gebruikt om uw gegevens te versleutelen in de datacenters van Microsoft|Als Office 365 beheerder kunt u de versleutelingssleutels van uw organisatie controleren en vervolgens Office 365 configureren om deze te gebruiken om uw gegevens in de datacenters van Microsoft in rust te versleutelen. <p> [Serviceversleuteling met klantsleutel in Office 365](customer-key-overview.md)|
|Personen communiceren via e-mail (Exchange Online)|Als beheerder Exchange Online hebt u verschillende opties voor het configureren van e-mailversleuteling. Dit zijn onder andere: <ul><li>Het [Office 365 (OME)](set-up-new-message-encryption-capabilities.md) gebruiken met Azure Rights Management (Azure RMS) om personen in staat te stellen versleutelde berichten te verzenden binnen of buiten uw organisatie</li><li>[S/MIME](/exchange/security-and-compliance/smime-exo/smime-exo) gebruiken om e-mailberichten te versleutelen en digitaal te ondertekenen</li><li>TLS gebruiken om [verbindingslijnen in te stellen voor een veilige e-mailstroom met een andere organisatie](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)</li></ul> <p> Zie [E-mailversleuteling in Office 365.](./email-encryption.md)|
|Bestanden worden toegankelijk vanaf teamsites of documentbibliotheken (OneDrive voor Bedrijven of SharePoint Online)|Wanneer personen werken met bestanden die zijn opgeslagen OneDrive voor Bedrijven of SharePoint Online, worden TLS-verbindingen gebruikt. Dit is ingebouwd in Office 365 automatisch. Zie [Gegevensversleuteling in OneDrive voor Bedrijven en SharePoint Online.](./data-encryption-in-odb-and-spo.md)|
|Bestanden worden gedeeld in onlinevergaderingen en chatgesprekken (Skype voor Bedrijven Online)|Wanneer personen met bestanden werken met Skype voor Bedrijven Online, wordt TLS gebruikt voor de verbinding. Dit is ingebouwd in Office 365 automatisch. Zie [Beveiliging en archiveren (Skype voor Bedrijven Online)](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-features).|
|Bestanden worden gedeeld in onlinevergaderingen en chatgesprekken (Microsoft Teams)|Wanneer personen met bestanden werken met Microsoft Teams, wordt TLS gebruikt voor de verbinding. Dit is ingebouwd in Office 365 automatisch. Microsoft Teams biedt momenteel geen ondersteuning voor inlineweergave van versleutelde e-mail. Zie Veelgestelde vragen over berichtversleuteling om te voorkomen dat versleutelde e-Microsoft Teams als versleuteld [wordt weergegeven.](./ome-faq.yml?view=o365-worldwide&preserve-view=true#can-i-automatically-remove-encryption-on-incoming-and-outgoing-mail-)|
|

## <a name="additional-information"></a>Aanvullende informatie

Zie File Protection Solutions in Office 365 voor meer informatie over bestandsbeveiligingsoplossingen [met versleutelingsopties.](https://www.microsoft.com/download/details.aspx?id=55523)
