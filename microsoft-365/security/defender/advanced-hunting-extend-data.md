---
title: Geavanceerde dekking voor jagen uitbreiden met de juiste instellingen
description: Controleer de controle-instellingen op Windows-apparaten en andere instellingen om ervoor te zorgen dat u de meest uitgebreide gegevens krijgt in geavanceerde jacht
keywords: advanced hunting, incident, pivot, entity, audit settings, user account management, security group management, threat hunting, cyber threat hunting, search, query, telemetry, Microsoft 365, Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: f4b1399b77583e95b109575a9577d8b1af89e6ad
ms.sourcegitcommit: 7cc2be0244fcc30049351e35c25369cacaaf4ca9
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/22/2021
ms.locfileid: "51952666"
---
# <a name="extend-advanced-hunting-coverage-with-the-right-settings"></a>Geavanceerde dekking voor jagen uitbreiden met de juiste instellingen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender
- Microsoft Defender voor Eindpunt

[Geavanceerd zoeken](advanced-hunting-overview.md) is afhankelijk van gegevens uit verschillende bronnen, waaronder uw apparaten, uw Office 365-werkruimten, Azure AD en Microsoft Defender voor identiteit. Als u de meest uitgebreide gegevens wilt krijgen, moet u ervoor zorgen dat u de juiste instellingen hebt in de bijbehorende gegevensbronnen.

## <a name="advanced-security-auditing-on-windows-devices"></a>Geavanceerde beveiligingsaudits op Windows-apparaten
Schakel deze geavanceerde controle-instellingen in om ervoor te zorgen dat u gegevens krijgt over activiteiten op uw apparaten, zoals lokaal accountbeheer, lokaal beveiligingsgroepbeheer en het maken van service.

| Data | Beschrijving | Schematabel | Configureren |
| --- | --- | --- | --- |
| Accountbeheer | Gebeurtenissen die zijn vastgelegd als verschillende waarden die het maken, verwijderen en `ActionType` andere accountgerelateerde activiteiten aangeven | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - Een geavanceerd beveiligingsauditbeleid implementeren: [Gebruikersaccountbeheer controleren](/windows/security/threat-protection/auditing/audit-user-account-management)<br> - [Meer informatie over geavanceerd beveiligingsauditbeleid](/windows/security/threat-protection/auditing/advanced-security-auditing) |
| Beveiligingsgroepsbeheer | Gebeurtenissen die zijn vastgelegd als verschillende waarden die het maken van `ActionType` lokale beveiligingsgroepen en andere lokale activiteiten voor groepsbeheer aangeven | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - Een geavanceerd beveiligingsauditbeleid implementeren: [Beveiligingsgroepsbeheer controleren](/windows/security/threat-protection/auditing/audit-security-group-management)<br> - [Meer informatie over geavanceerd beveiligingsauditbeleid](/windows/security/threat-protection/auditing/advanced-security-auditing) |
| Service-installatie | Gebeurtenissen die zijn vastgelegd met de waarde, waarmee wordt `ActionType` aangegeven dat er een service is `ServiceInstalled` gemaakt | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - Een geavanceerd beveiligingsauditbeleid implementeren: [Systeemextensie voor auditbeveiliging](/windows/security/threat-protection/auditing/audit-security-system-extension)<br> - [Meer informatie over geavanceerd beveiligingsauditbeleid](/windows/security/threat-protection/auditing/advanced-security-auditing) |

## <a name="microsoft-defender-for-identity-sensor-on-the-domain-controller"></a>Microsoft Defender voor identiteits sensor op de domeincontroller
Als u Active Directory on-premises gebruikt, moet u de Microsoft Defender for Identity-sensor installeren op de domeincontroller om gegevens voor Microsoft Defender voor identiteit op te halen. Wanneer deze gegevens zijn geïnstalleerd en correct zijn geconfigureerd, worden deze gegevens ook gebruikt voor geavanceerde jacht via Microsoft Defender voor identiteit en krijgt u een meer holistisch beeld van identiteitsgegevens en gebeurtenissen in uw netwerk. Deze gegevens verbeteren ook de mogelijkheid van Microsoft Defender voor identiteit om relevante waarschuwingen te genereren die ook worden gedekt door geavanceerde jacht. 

| Data | Beschrijving | Schematabel | Configureren |
| --- | --- | --- | --- |
| Domeincontroller | Gegevens van on-premises Active Directory die zijn verzonden naar Microsoft Defender voor identiteit, wat identiteitsgerelateerde informatie verrijkt, zoals accountgegevens, aanmeldingsactiviteit en Active Directory-query's | Meerdere tabellen, waaronder [IdentityInfo,](advanced-hunting-identityinfo-table.md) [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)en [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)  | - [De Microsoft Defender for Identity-sensor installeren](/azure-advanced-threat-protection/install-atp-step4)<br>- [Relevante Windows-gebeurtenissen in- en uit-](/azure-advanced-threat-protection/configure-event-collection) |

>[!NOTE]
>Sommige tabellen in dit artikel zijn mogelijk niet beschikbaar in Microsoft Defender voor Eindpunt. [Schakel Microsoft 365 Defender in om](m365d-enable.md) te zoeken naar bedreigingen met meer gegevensbronnen. U kunt uw geavanceerde zoekwerkstromen verplaatsen van Microsoft Defender voor Eindpunt naar Microsoft 365 Defender door de stappen te volgen in Geavanceerde zoekquery's migreren van [Microsoft Defender voor Eindpunt.](advanced-hunting-migrate-from-mde.md)

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)