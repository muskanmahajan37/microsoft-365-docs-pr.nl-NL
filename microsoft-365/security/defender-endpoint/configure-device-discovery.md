---
title: Apparaatdetectie configureren
description: Informatie over het configureren van apparaatdetectie in Microsoft 365 Defender met basis- of standaarddetectie
keywords: basis, standaard, eindpuntdetectie configureren, apparaatdetectie
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 0d722b4f4bef5b4d178edc5f2142c887690d4c63
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765249"
---
# <a name="configure-device-discovery"></a>Apparaatdetectie configureren

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


[!include[Prerelease information](../../includes/prerelease.md)]

Detectie kan worden geconfigureerd in de standaard- of basismodus. Gebruik de standaardoptie om apparaten in uw netwerk actief te zoeken, waardoor de detectie van eindpunten beter wordt gegarandeerd en de apparaatclassificatie uitgebreider is. 

U kunt de lijst met apparaten aanpassen die worden gebruikt om standaarddetectie uit te voeren. U kunt standaarddetectie inschakelen op alle onboarded-apparaten die deze mogelijkheid ondersteunen (momenteel alleen Windows 10-apparaten) of een subset of subset van uw apparaten selecteren door hun apparaatlabels op te geven. 


> [!IMPORTANT]
> Voor een voorbeeld moet u eerst de preview-functies in het Microsoft Defender-beveiligingscentrum in te zetten.
> Vervolgens hebt u toegang tot de configuratie voor apparaatdetectie in het Microsoft 365-beveiligingscentrum. De lijst met niet-beheerde apparaten en beveiligingsaanbevelingen is beschikbaar in zowel het Microsoft Defender-beveiligingscentrum als het Microsoft 365-beveiligingscentrum, terwijl de dashboardtegels alleen beschikbaar zijn in het Microsoft 365-beveiligingscentrum.


Volg de volgende configuratiestappen in het Microsoft 365-beveiligingscentrum:

1.  Ga naar **Instellingen > apparaatdetectie**.
2.  Selecteer de detectiemodus die u wilt gebruiken op uw onboarded-apparaten. 
3.  Als u hebt geselecteerd om standaarddetectie te gebruiken, selecteert u welke apparaten u wilt gebruiken voor actieve detectie: alle apparaten of op een subset door de apparaatlabels op te geven.
4. Klik op **Opslaan**.


## <a name="exclude-devices-from-being-actively-probed-in-standard-discovery"></a>Apparaten uitsluiten van actief worden onderzocht in standaarddetectie
Als er apparaten in uw netwerk zijn die niet actief moeten worden gescand (bijvoorbeeld apparaten die worden gebruikt als honeypots voor een ander beveiligingsprogramma), kunt u ook een lijst met uitsluitingen definiëren om te voorkomen dat ze worden gescand. Houd er rekening mee dat apparaten nog steeds kunnen worden gevonden met de basisdetectiemodus. Deze apparaten worden passief ontdekt, maar worden niet actief onderzocht. 

## <a name="select-networks-to-monitor"></a>Netwerken selecteren die u wilt controleren
 Microsoft Defender voor Eindpunt analyseert een netwerk en bepaalt of het een bedrijfsnetwerk is dat moet worden gecontroleerd of een niet-bedrijfsnetwerk dat kan worden genegeerd. Bedrijfsnetwerken worden meestal gekozen om te worden gecontroleerd. U kunt deze beslissing echter overschrijven door ervoor te kiezen niet-bedrijfsnetwerken te controleren waar onboarded-apparaten worden gevonden. 

U kunt configureren waar apparaatdetectie kan worden uitgevoerd door op te geven welke netwerken moeten worden gecontroleerd. Wanneer een netwerk wordt gecontroleerd, kan apparaatdetectie op het netwerk worden uitgevoerd. 

Een lijst met netwerken waarop apparaatdetectie kan worden uitgevoerd, wordt weergegeven op de pagina **Bewaakte netwerken.** 


>[!NOTE]
> Alleen top 50-netwerken (afhankelijk van het aantal gekoppelde apparaten) zijn beschikbaar in de netwerklijst. 


De lijst met bewaakte netwerken wordt gesorteerd op basis van het totale aantal apparaten dat in de afgelopen 7 dagen op het netwerk is gezien.


U kunt een filter toepassen om een van de volgende detectie-staten van het netwerk te bekijken:

- **Bewaakte netwerken:** netwerken waar apparaatdetectie wordt uitgevoerd.
- **Genegeerde netwerken:** dit netwerk wordt genegeerd en apparaatdetectie wordt niet uitgevoerd op het netwerk.
- **Alles:** zowel bewaakte als genegeerde netwerken worden weergegeven. 


### <a name="configure-the-network-monitor-state"></a>De status van de netwerkmonitor configureren
U kunt bepalen waar apparaatdetectie plaatsvindt. Bewaakte netwerken is de plaats waar apparaatdetectie wordt uitgevoerd en meestal bedrijfsnetwerken zijn. U kunt er ook voor kiezen om netwerken te negeren of de eerste detectieclassificatie te selecteren nadat u een status hebt gewijzigd. 

Als u de eerste detectieclassificatie kiest, wordt de standaardinstelling voor netwerkmonitoren van het systeem toegepast. Als u de standaardtoestand voor netwerkmonitoren van het systeem selecteert, worden netwerken die zijn geïdentificeerd als zakelijk, gecontroleerd en die zijn geïdentificeerd als niet-bedrijfsnetwerken, automatisch genegeerd.
 
1. Selecteer **Instellingen > apparaatdetectie**.
2. Selecteer **Bewaakte netwerken.** 
3. Bekijk de lijst met netwerken. 
4. Selecteer de drie puntjes naast de netwerknaam. 
5. Kies of u de oorspronkelijke detectieclassificatie wilt controleren, negeren of gebruiken. 
    
    > [!WARNING]
    >- Als u ervoor kiest om een netwerk te controleren dat niet is geïdentificeerd door Microsoft Defender voor Eindpunt als een bedrijfsnetwerk, kan apparaatdetectie buiten uw bedrijfsnetwerk worden veroorzaakt en kunnen daarom thuis- of andere niet-zakelijke apparaten worden gedetecteerd. 
    > - Als u ervoor kiest om een netwerk te negeren, wordt het controleren en ontdekken van apparaten in dat netwerk gestopt. Apparaten die al zijn gevonden, worden niet uit de voorraad verwijderd, maar worden niet meer bijgewerkt en details worden bewaard totdat de bewaarperiode voor gegevens van het Defender for Endpoint verloopt.
    > - Voordat u ervoor kiest om netwerken van niet-zakelijke ondernemingen te controleren, moet u ervoor zorgen dat u daarvoor toestemming hebt. <br>


6. Bevestig dat u de wijziging wilt maken. 




## <a name="see-also"></a>Zie ook
- [Overzicht van apparaatdetectie](device-discovery.md)
- [Veelgestelde vragen over apparaatdetectie](device-discovery-faq.md)