---
title: Geautomatiseerde onderzoeks- en herstelmogelijkheden configureren
description: Uw geautomatiseerde onderzoeks- en herstelmogelijkheden instellen in Microsoft Defender voor Eindpunt.
keywords: configureren, instellen, geautomatiseerd, onderzoek, detectie, waarschuwingen, herstel, antwoord
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: JoeDavies-MSFT
ms.author: josephd
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: how-to
ms.date: 01/27/2021
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.openlocfilehash: 23d6c8c87a6cbcc7b8060440ba2c0cae6182767d
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274542"
---
# <a name="configure-automated-investigation-and-remediation-capabilities-in-microsoft-defender-for-endpoint"></a>Geautomatiseerde onderzoeks- en herstelmogelijkheden configureren in Microsoft Defender voor Eindpunt

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Als uw organisatie [Microsoft Defender voor Eindpunt](https://docs.microsoft.com/windows/security/threat-protection/) (Defender voor Eindpunt) gebruikt, kunnen geautomatiseerde onderzoeks- en herstelmogelijkheden uw beveiligingsbewerkingen tijd en moeite besparen. [](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/automated-investigations) Zoals in dit [blogbericht](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/enhance-your-soc-with-microsoft-defender-atp-automatic/ba-p/848946)wordt beschreven, bootsen deze mogelijkheden de ideale stappen na die een beveiligingsanalist neemt om bedreigingen te onderzoeken en te corrigeren. [Meer informatie over geautomatiseerd onderzoek en herstel](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/automated-investigations). 

Als u geautomatiseerd onderzoek en herstel wilt configureren,
1. [De functies in- en uit-](#turn-on-automated-investigation-and-remediation) en 
2. [Apparaatgroepen instellen.](#set-up-device-groups)

## <a name="turn-on-automated-investigation-and-remediation"></a>Automatisch onderzoek en herstel in- en uit-

1. Als globale beheerder of beveiligingsbeheerder gaat u naar het Microsoft Defender-beveiligingscentrum [https://securitycenter.windows.com](https://securitycenter.windows.com) () en meld u aan.
2. Kies instellingen in het **navigatiedeelvenster.**
3. Selecteer geavanceerde functies in **de** sectie **Algemeen.**
4. Schakel zowel Automatisch **onderzoek als** Waarschuwingen automatisch **oplossen in.**

## <a name="set-up-device-groups"></a>Apparaatgroepen instellen

1. Selecteer in het Microsoft Defender-beveiligingscentrum (), op de pagina [https://securitycenter.windows.com](https://securitycenter.windows.com) **Instellingen,** onder Machtigingen, de optie **Apparaatgroepen.** 
2. Selecteer **+ Apparaatgroep toevoegen.**
3. Maak ten minste één apparaatgroep als volgt:
   - Geef een naam en beschrijving op voor de apparaatgroep.
   - Selecteer in **de lijst Automatiseringsniveau** een niveau, zoals **Volledig, om bedreigingen automatisch te corrigeren.** Het automatiseringsniveau bepaalt of herstelacties automatisch worden ondernomen of alleen na goedkeuring. Zie Automatiseringsniveaus in geautomatiseerd onderzoek en herstel [voor meer informatie.](automation-levels.md)
   - Gebruik in **de sectie** Leden een of meer voorwaarden om apparaten te identificeren en op te nemen.
   - Selecteer op **het tabblad Gebruikerstoegang** de [Azure Active Directory-groepen](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-manage-groups?context=azure/active-directory/users-groups-roles/context/ugr-context) die toegang moeten hebben tot de apparaatgroep die u maakt.
4. Selecteer **Gereed** wanneer u klaar bent met het instellen van uw apparaatgroep.

## <a name="next-steps"></a>Volgende stappen

- [Ga naar het Actiecentrum om in behandeling zijnde en voltooide herstelacties te bekijken](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/auto-investigation-action-center#the-action-center)
- [Lopende acties controleren en goedkeuren](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-auto-investigation)

## <a name="see-also"></a>Zie ook

- [Actie ondernemen voor fout-positieven/-negatieven in Microsoft Defender voor Eindpunt](defender-endpoint-false-positives-negatives.md)
