---
title: Fout-positieven of onwaar negatieven melden na automatisch onderzoek in Microsoft Defender voor Office 365
description: Is er iets gemist of ten onrechte gedetecteerd door AIR in Microsoft Defender voor Office 365? Meer informatie over het indienen van fout-positieven of onwaar negatieven bij Microsoft voor analyse.
keywords: geautomatiseerd, onderzoek, waarschuwing, trigger, actie, herstel, onwaar positief, onwaar negatief
search.appverid: met150
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
ms.prod: m365-security
ms.date: 01/29/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.topic: how-to
ms.custom:
- autoir
ms.technology: mdo
ms.openlocfilehash: 036ef1c97788f310c5b906ae5f80076ca2359cdb
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275082"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>Fout-positieven/negatieven rapporteren in geautomatiseerde onderzoeks- en antwoordmogelijkheden

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Als de mogelijkheden voor automatisch onderzoek en antwoord [(AIR) in](automated-investigation-response-office.md) Office 365 of iets verkeerd zijn gedetecteerd, zijn er stappen die uw team voor beveiligingsbewerkingen kan ondernemen om dit op te lossen. Dergelijke acties zijn onder andere:

- [Een onwaar positief/negatief melden bij Microsoft;](#report-a-false-positivenegative-to-microsoft-for-analysis)
- [Waarschuwingen aanpassen](#adjust-an-alert-to-prevent-false-positives-from-recurring) (indien nodig); en
- [Herstelacties ongedaan maken die zijn genomen.](#undo-a-remediation-action)

Gebruik dit artikel als handleiding.

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>Een onwaar positief/negatief melden bij Microsoft voor analyse

Als AIR in Microsoft Defender voor Office 365 een e-mailbericht, een e-mailbijlage, een URL in een e-mailbericht of een URL in een Office-bestand heeft gemist, kunt u verdachte [spam, phish, URL's](admin-submission.md)en bestanden indienen bij Microsoft voor Office 365 scannen.

U kunt ook [een bestand indienen bij Microsoft voor malwareanalyse.](https://www.microsoft.com/wdsi/filesubmission)

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>Een waarschuwing aanpassen om te voorkomen dat fout-positieven terugkeren

Als een waarschuwing wordt geactiveerd door legitiem gebruik of als de waarschuwing onjuist is, kunt u waarschuwingen beheren in de [Cloud App Security portal.](/cloud-app-security/managing-alerts)

Als uw organisatie naast Office 365 [Microsoft Defender](/windows/security/threat-protection) voor Eindpunt gebruikt en een bestand, IP-adres, URL of domein wordt beschouwd als malware op een apparaat, kunt u een aangepaste indicator maken met de actie Toestaan voor uw [apparaat.](/windows/security/threat-protection/microsoft-defender-atp/manage-indicators)

## <a name="undo-a-remediation-action"></a>Een herstelactie ongedaan maken

Als er in de meeste gevallen een herstelactie is uitgevoerd op een e-mailbericht, e-mailbijlage of URL en het item eigenlijk geen bedreiging is, kan uw beveiligingsteam de herstelactie ongedaan maken en stappen ondernemen om te voorkomen dat de fout-positieve zich opnieuw voordeed. U kunt Threat [Explorer of het](#undo-an-action-using-threat-explorer) tabblad Acties gebruiken voor een onderzoek [om](#undo-an-action-in-the-action-center) een actie ongedaan te maken.

> [!IMPORTANT]
> Zorg ervoor dat u de benodigde machtigingen hebt voordat u de volgende taken uitvoert.

### <a name="undo-an-action-using-threat-explorer"></a>Een actie ongedaan maken met Threat Explorer

Met Threat Explorer kan uw beveiligingsteam een e-mail vinden die is beïnvloed door een actie en de actie mogelijk ongedaan maken.

|Scenario|Opties voor ongedaan maken|Meer informatie|
|---|---|---|
|Een e-mailbericht is doorgeleid naar de map Ongewenste e-mail van een gebruiker|- Het bericht verplaatsen naar de map Verwijderde items van de gebruiker<br/>- Het bericht naar het Postvak IN van de gebruiker verplaatsen<br/>- Het bericht verwijderen|[Schadelijke e-mail zoeken en onderzoeken die is bezorgd in Office 365](investigate-malicious-email-that-was-delivered.md)|
|Een e-mailbericht of bestand is in quarantaine geplaatst|- Het e-mailbericht of bestand vrijgeven<br/>- Het e-mailbericht of bestand verwijderen|[Berichten in quarantaine beheren als beheerder](manage-quarantined-messages-and-files.md)|
|

### <a name="undo-an-action-in-the-action-center"></a>Een actie ongedaan maken in het actiecentrum

In het Actiecentrum kunt u herstelacties zien die zijn ondernomen en de actie mogelijk ongedaan kunnen maken.

1. Ga naar het Microsoft 365 beveiligingscentrum ( <https://security.microsoft.com> ).
2. Selecteer actiecentrum in het **navigatiedeelvenster.**
3. Selecteer het **tabblad Geschiedenis** om de lijst met voltooide acties te bekijken.
4. Selecteer een item. Het deelvenster Flyout wordt geopend.
5. Selecteer ongedaan maken in het deelvenster Flyout. (Alleen acties die ongedaan kunnen worden gemaakt, hebben een **knop Ongedaan** maken.)

## <a name="see-also"></a>Zie ook

- [Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Automatische onderzoeken in Microsoft Defender voor Office 365](office-365-air.md)
