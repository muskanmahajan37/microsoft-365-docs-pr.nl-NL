---
title: Ga naar het Actiecentrum om uw geautomatiseerde onderzoeks- en hersteltaken weer te geven en goed te keuren
description: Het Actiecentrum gebruiken om details over geautomatiseerd onderzoek weer te geven en acties in behandeling goed te keuren
keywords: Actiecentrum, bedreigingsbeveiliging, onderzoek, waarschuwing, in behandeling, geautomatiseerd, detectie
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: how-to
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.openlocfilehash: 7bea9a1632e7a9ed9d394c2c411123d0601a9397
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274578"
---
# <a name="the-action-center"></a>Het Actiecentrum

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

Het actiecentrum biedt een 'enkel deelvenster met glas' voor incident- en waarschuwingstaken, zoals:

- Goedkeuring van herstelacties in behandeling.
- Een auditlogboek weergeven van al goedgekeurde herstelacties.
- Voltooide herstelacties controleren.

Omdat het Actiecentrum een uitgebreide weergave biedt van Microsoft 365 Defender op het werk, kan uw beveiligingsteam effectiever en efficiënter werken.

## <a name="the-unified-action-center"></a>Het geïntegreerde actiecentrum

Het geïntegreerde Actiecentrum () bevat lopende en voltooide herstelacties voor uw apparaten, e-mail & [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) samenwerkingsinhoud en identiteiten op één locatie.

:::image type="content" source="../../media/m3d-action-center-unified.png" alt-text="Unified Action center in Microsoft 365 Defender":::

Bijvoorbeeld: 

- Als u eerder het Office 365 Security & Compliance Center () hebt gebruikt, probeert u het geïntegreerde Actiecentrum in het [https://protection.office.com](https://protection.office.com) Microsoft 365-beveiligingscentrum ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ).
- Als u het Actiecentrum in het Microsoft Defender-beveiligingscentrum () gebruikt, probeert u het geïntegreerde Actiecentrum in het [https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center) Microsoft 365-beveiligingscentrum ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ).
- Als u al gebruik hebt gemaakt van het Microsoft 365-beveiligingscentrum ( ), ziet u verschillende [https://security.microsoft.com](https://security.microsoft.com) verbeteringen in het Actiecentrum ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ).

Het geïntegreerde actiecentrum brengt herstelacties samen in Defender voor Eindpunt en Defender voor Office 365. Het definieert een gemeenschappelijke taal voor alle herstelacties en biedt een geïntegreerde onderzoekservaring. Uw beveiligingsbewerkingsteam heeft een 'enkel deelvenster met glas' om herstelacties weer te geven en te beheren.  

U kunt het geïntegreerde actiecentrum gebruiken als u de juiste machtigingen en een of meer van de volgende abonnementen hebt:

- [Defender voor Eindpunt](../defender-endpoint/microsoft-defender-endpoint.md)
- [Defender voor Office 365](/microsoft-365/security/office-365-security/defender-for-office-365)
- [Microsoft 365 Defender](microsoft-365-defender.md)

> [!TIP]
> Zie Vereisten voor meer [informatie.](./prerequisites.md)

## <a name="using-the-action-center"></a>Het actiecentrum gebruiken

1. Ga naar [https://security.microsoft.com](https://security.microsoft.com) en meld u aan. 
2. Kies actiecentrum in het **navigatiedeelvenster.** 

Wanneer u het Actiecentrum bezoekt, ziet u twee tabbladen: **Acties in behandeling** en **Geschiedenis.** De volgende tabel bevat een overzicht van wat u op elk tabblad ziet:

|Tab  |Omschrijving  |
|---------|---------|
|**In behandeling**     | Hiermee wordt een lijst weergegeven met acties die aandacht vereisen. U kunt acties één voor één goedkeuren of weigeren of meerdere acties selecteren als ze hetzelfde type actie hebben (zoals Quarantainebestand). <p>**TIP:** Controleer en keur in behandeling zijnde acties zo snel mogelijk goed (of weiger) zodat uw geautomatiseerde onderzoeken tijdig kunnen worden voltooid.       |
|**Geschiedenis**     | Fungeert als een auditlogboek voor acties die zijn uitgevoerd, zoals: <br/>- Herstelacties die zijn ondernomen als gevolg van geautomatiseerde onderzoeken <br/>- Herstelacties die zijn ondernomen op verdachte of schadelijke e-mailberichten, bestanden of URL's<br/>- Herstelacties die zijn goedgekeurd door uw beveiligingsteam <br/>- Opdrachten die zijn uitgevoerd en herstelacties die zijn toegepast tijdens livereactiesessies<br/>- Herstelacties die zijn ondernomen door uw antivirusbeveiliging <p>Biedt een manier om bepaalde acties ongedaan te maken (zie [Voltooide acties ongedaan maken).](m365d-autoir-actions.md#undo-completed-actions)        |

U kunt gegevens aanpassen, sorteren, filteren en exporteren in het Actiecentrum.

:::image type="content" source="../../media/m3d-action-center-columnsfilters.png" alt-text="Met het Actiecentrum kunt u uw lijst met acties sorteren, filteren en aanpassen":::

- Selecteer een kolomkoppen om items in oplopende of aflopende volgorde te sorteren.
- Gebruik het tijdsperiodefilter om gegevens voor de afgelopen dag, week, 30 dagen of 6 maanden weer te geven.
- Kies de kolommen die u wilt weergeven.
- Geef op hoeveel items u wilt opnemen op elke pagina met gegevens.
- Gebruik filters om alleen de items te bekijken die u wilt zien.
- Selecteer **Exporteren** om resultaten te exporteren naar een .csv bestand.

## <a name="actions-tracked-in-the-action-center"></a>Bij te houden acties in het actiecentrum

Alle acties, ongeacht of ze in behandeling zijn of al zijn genomen, worden bijgespoord in het Actiecentrum. Beschikbare acties zijn onder andere:

- Onderzoekspakket verzamelen 
- Apparaat isoleren (deze actie kan ongedaan worden gemaakt) 
- Computer offboarden 
- Uitvoering van releasecode 
- Release uit quarantaine 
- Voorbeeld aanvragen 
- Codeuitvoering beperken (deze actie kan ongedaan worden gemaakt) 
- Antivirusscan uitvoeren 
- Stoppen en in quarantaine plaatsen 

Naast herstelacties die automatisch worden ondernomen als gevolg van geautomatiseerde onderzoeken, houdt het Actiecentrum ook acties bij die uw beveiligingsteam heeft ondernomen om gedetecteerde bedreigingen aan te pakken en acties die zijn ondernomen als gevolg van functies voor [bedreigingsbeveiliging](m365d-autoir.md)in Microsoft 365 Defender. Zie Herstelacties voor meer informatie over automatische en handmatige [herstelacties.](m365d-remediation-actions.md)

## <a name="viewing-action-source-details"></a>Details van actiebron weergeven

(**NIEUW!**) Het verbeterde Actiecentrum bevat nu een **kolom Actiebron** waarin wordt be informatie over waar elke actie vandaan komt. In de volgende tabel worden mogelijke **actiebronwaarden** beschreven:

| Actiebronwaarde | Omschrijving |
|:-----|:---|
| **Handmatige apparaatactie** | Een handmatige actie op een apparaat. Voorbeelden hiervan [zijn apparaatisolatie](../defender-endpoint/respond-machine-alerts.md#isolate-devices-from-the-network) [of bestands quarantaine.](../defender-endpoint/respond-file-alerts.md#stop-and-quarantine-files) |
| **Handmatige e-mailactie** | Een handmatige actie voor e-mail. Een voorbeeld hiervan is het verwijderen van e-mailberichten of [het herstellen van een e-mailbericht.](../office-365-security/remediate-malicious-email-delivered-office-365.md) |
| **Geautomatiseerde apparaatactie** | Een geautomatiseerde actie die wordt ondernomen op een entiteit, zoals een bestand of proces. Voorbeelden van geautomatiseerde acties zijn het verzenden van een bestand naar quarantaine, het stoppen van een proces en het verwijderen van een registersleutel. (Zie [Herstelacties in Microsoft Defender voor Eindpunt](../defender-endpoint/manage-auto-investigation.md#remediation-actions).) |
| **Geautomatiseerde e-mailactie** | Een geautomatiseerde actie voor e-mailinhoud, zoals een e-mailbericht, bijlage of URL. Voorbeelden van geautomatiseerde acties zijn het zacht verwijderen van e-mailberichten, het blokkeren van URL's en het uitschakelen van externe e-mail doorsturen. (Zie [Herstelacties in Microsoft Defender voor Office 365](../office-365-security/air-remediation-actions.md).) |
| **Geavanceerde actie voor de jacht** | Acties die zijn ondernomen op apparaten of e-mail [met geavanceerde zoekacties.](./advanced-hunting-overview.md) |
| **Explorer-actie** | Acties voor e-mailinhoud met [Explorer](../office-365-security/threat-explorer.md). |
| **Handmatige livereactieactie** | Acties die zijn ondernomen op een apparaat met [livereactie.](../defender-endpoint/live-response.md) Voorbeelden hiervan zijn het verwijderen van een bestand, het stoppen van een proces en het verwijderen van een geplande taak. |
| **Livereactieactie** | Acties die zijn ondernomen op een apparaat [met Microsoft Defender voor eindpunt-API's.](../defender-endpoint/management-apis.md#microsoft-defender-for-endpoint-apis) Voorbeelden van acties zijn het isoleren van een apparaat, het uitvoeren van een antivirusscan en het verkrijgen van informatie over een bestand. |

## <a name="required-permissions-for-action-center-tasks"></a>Vereiste machtigingen voor actiecentrumtaken

Als u taken wilt uitvoeren, zoals het goedkeuren of weigeren van acties in behandeling in het actiecentrum, moet u machtigingen hebben toegewezen zoals vermeld in de volgende tabel:

|Herstelactie |Vereiste rollen en machtigingen |
|--|----|
|Microsoft Defender voor herstel van eindpunten (apparaten) |**Beveiligingsbeheerderrol** toegewezen in Azure Active Directory (Azure AD) ( ) of [https://portal.azure.com](https://portal.azure.com) het Microsoft 365-beheercentrum ( [https://admin.microsoft.com](https://admin.microsoft.com) )<br/>--- of ---<br/>**Rol actieve herstelacties** toegewezen in Microsoft Defender voor eindpunt <br/> <br/> Zie de volgende bronnen voor meer informatie: <br/>- [Beheerdersrolmachtigingen in Azure AD](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br/>- [Rollen maken en beheren voor op rollen gebaseerde toegangsbeheer (Microsoft Defender voor Eindpunt)](../defender-endpoint/user-roles.md)  |
|Herstel van Microsoft Defender voor Office 365 (Office-inhoud en e-mail)  |**Beveiligingsbeheerder-rol** toegewezen in Azure AD ( [https://portal.azure.com](https://portal.azure.com) ) of het Microsoft 365-beheercentrum ( [https://admin.microsoft.com](https://admin.microsoft.com) )<br/>--- en --- <br/>**Zoek- en purge-rol** toegewezen in het beveiligings- & Compliancecentrum ( [https://protection.office.com](https://protection.office.com) ) <br/><br/>**BELANGRIJK:** Als de  rol beveiligingsbeheerder alleen is toegewezen in het Office 365-beveiligings- & compliancecentrum ( ), hebt u geen toegang tot de mogelijkheden van het Actiecentrum of [https://protection.office.com](https://protection.office.com) Microsoft 365 Defender. U moet de rol **Beveiligingsbeheerder** hebben toegewezen in Azure AD of het Microsoft 365-beheercentrum. <br/><br/>Zie de volgende bronnen voor meer informatie: <br/>- [Beheerdersrolmachtigingen in Azure AD](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br/>- [Machtigingen in het beveiligings- & compliancecentrum](/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center) |

> [!TIP]
> Gebruikers die de rol **Globale beheerder** hebben toegewezen in Azure AD, kunnen acties in behandeling in het Actiecentrum goedkeuren of weigeren. Als beste gewoonte moet uw organisatie echter het aantal personen beperken dat de rol Globale beheerder **heeft** toegewezen. We raden u **aan** de beveiligingsbeheerder,  **actieve herstelacties** en rollen zoeken en zuiveren te gebruiken die in de vorige tabel voor machtigingen van het Actiecentrum worden vermeld.

## <a name="next-step"></a>Volgende stap 

- [Herstelacties weergeven en beheren](m365d-autoir-actions.md)
