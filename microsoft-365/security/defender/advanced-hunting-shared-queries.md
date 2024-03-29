---
title: Gedeelde query's gebruiken in geavanceerde microsoft 365 Defender-zoekopdrachten
description: Begin onmiddellijk met het zoeken naar bedreigingen met vooraf gedefinieerde en gedeelde query's. Deel uw query's met het publiek of met uw organisatie.
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, custom detections, schema, kusto, github repo, my queries, shared queries
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
ms.openlocfilehash: 83c78f9df5560c75e40a171d770e994b86049204
ms.sourcegitcommit: 7cc2be0244fcc30049351e35c25369cacaaf4ca9
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/22/2021
ms.locfileid: "51952582"
---
# <a name="use-shared-queries-in-advanced-hunting"></a>Gedeelde query's gebruiken in geavanceerde zoekopdrachten

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender
- Microsoft Defender voor Eindpunt



[Geavanceerde](advanced-hunting-overview.md) zoekquery's kunnen worden gedeeld tussen gebruikers in dezelfde organisatie. U kunt ook query's vinden die openbaar zijn gedeeld op GitHub. Met deze query's kunt u snel specifieke scenario's voor het zoeken naar bedreigingen uitvoeren zonder dat u zelf query's moet schrijven.

![Afbeelding van gedeelde query's](../../media/advanced-hunting-shared-queries.png)

## <a name="save-modify-and-share-a-query"></a>Een query opslaan, wijzigen en delen
U kunt een nieuwe of bestaande query opslaan, zodat deze alleen toegankelijk is voor u of wordt gedeeld met andere gebruikers in uw organisatie. 

1. Een query maken of wijzigen. 

2. Klik op **de vervolgkeuzeknop** Query opslaan en selecteer **Opslaan als**.
    
3. Voer een naam in voor de query. 

   ![Afbeelding van het opslaan van een query](../../media/advanced-hunting-save-query.png)

4. Selecteer de map waarin u de query wilt opslaan.
    - **Gedeelde query's:** gedeeld met alle gebruikers van uw organisatie
    - **Mijn query's,** die alleen voor u toegankelijk zijn
    
5. Selecteer **Opslaan**. 

## <a name="delete-or-rename-a-query"></a>Een query verwijderen of de naam wijzigen
1. Klik met de rechtermuisknop op een query die u wilt wijzigen of verwijderen.

    ![Afbeelding van de verwijderquery](../../media/advanced_hunting_delete_rename.png)

2. Selecteer **Verwijderen** en bevestig verwijdering. Of selecteer **Naam wijzigen** en geef een nieuwe naam op voor de query.

## <a name="create-a-direct-link-to-a-query"></a>Een directe koppeling naar een query maken
Als u een koppeling wilt genereren die uw query rechtstreeks opent in de geavanceerde queryeditor, rondt u de query af en selecteert u **Koppeling delen.**

## <a name="access-queries-in-the-github-repository"></a>Access-query's in de GitHub-opslagplaats  
Microsoft-beveiligingsonderzoekers delen regelmatig geavanceerde zoekquery's in een aangewezen [openbare opslagplaats op GitHub.](https://aka.ms/hunting-queries) Deze opslagplaats staat open voor bijdragen. Als u wilt bijdragen, [kunt u gratis deelnemen aan GitHub.](https://github.com/)

>[!tip]
>Beveiligingsonderzoekers van Microsoft bieden ook geavanceerde zoekquery's die u kunt gebruiken om activiteiten en indicatoren te vinden die zijn gekoppeld aan nieuwe bedreigingen. Deze query's worden geleverd als onderdeel van de [bedreigingsanalyserapporten](/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) in het Microsoft Defender-beveiligingscentrum.

>[!NOTE]
>Sommige tabellen in dit artikel zijn mogelijk niet beschikbaar in Microsoft Defender voor Eindpunt. [Schakel Microsoft 365 Defender in om](m365d-enable.md) te zoeken naar bedreigingen met meer gegevensbronnen. U kunt uw geavanceerde zoekwerkstromen verplaatsen van Microsoft Defender voor Eindpunt naar Microsoft 365 Defender door de stappen te volgen in Geavanceerde zoekquery's migreren van [Microsoft Defender voor Eindpunt.](advanced-hunting-migrate-from-mde.md)

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Werken met queryresultaten](advanced-hunting-query-results.md)
- [Opsporen op apparaten en in e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)