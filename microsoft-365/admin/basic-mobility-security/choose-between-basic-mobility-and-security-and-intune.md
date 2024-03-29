---
title: Kies tussen Basismobiliteit en Beveiliging en Intune
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: Basismobiliteit en beveiliging maken deel uit van de Microsoft 365-abonnementen.
ms.openlocfilehash: b7b1d229e87a313a9567daed87f03452b1925a65
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904262"
---
# <a name="choose-between-basic-mobility-and-security-or-intune"></a>Kiezen tussen Basismobiliteit en Beveiliging of Intune

[Microsoft Intune](/mem/intune/) is een zelfstandig product dat is opgenomen in bepaalde Microsoft 365-abonnementen, terwijl Basismobiliteit en beveiliging deel uitmaakt van de Microsoft 365-abonnementen.

 ## <a name="availability-of-basic-mobility-and-security-and-intune"></a>Beschikbaarheid van basismobiliteit en beveiliging en Intune

Zowel Basismobiliteit als Beveiliging en Intune zijn opgenomen in verschillende abonnementen, die in de volgende tabel worden beschreven.

| Plannen | Basic Mobility en Security | Microsoft Intune |
|:-----|:-----|:-----|
|Microsoft 365-apps|Ja|Nee|
|Microsoft 365 Business Basic|Ja|Nee|
|Microsoft 365 Business Standard|Ja|Nee|
|Office 365 E1 |Ja|Nee|
|Office 365 E3 |Ja|Nee|
|Office 365 E5 |Ja|Nee|
|Microsoft 365 Business Premium |Ja|Ja|
|Microsoft 365 Firstline 3 |Ja|Ja|
|Microsoft 365 Enterprise E3 |Ja|Ja|
|Microsoft 365 Enterprise E5 |Ja|Ja|
|Microsoft 365 Education A1 |Ja|Ja|
|Microsoft 365 Education A3 |Ja|Ja|
|Microsoft 365 Education A5 |Ja|Ja|
|Microsoft Intune |Nee|Ja|
|Enterprise Mobility & Security E3 |Nee|Ja|
|Enterprise Mobility & Security E5 |Nee|Ja|

>[!NOTE]
>U kunt niet beginnen met basismobiliteit en beveiliging als u al Microsoft Intune gebruikt.

 Zie servicebeschrijvingen [voor Microsoft 365- en Office 365-platform voor meer informatie.](/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description) 

## <a name="differences-in-capabilities"></a>Verschillen in mogelijkheden

Microsoft Intune en de ingebouwde basismobiliteit en beveiliging bieden u beide de mogelijkheid om mobiele apparaten in uw organisatie te beheren, maar er zijn belangrijke verschillen in mogelijkheden, beschreven in de volgende tabel.

>[!NOTE]
>U kunt gebruikers en hun mobiele apparaten beheren met intune en basismobiliteit en beveiliging in dezelfde Microsoft 365 Business Standard-organisatie door eerst Basismobiliteit en beveiliging in te stellen en vervolgens *Microsoft Intune* toe te voegen. Op deze manier kunt u basismobiliteit en beveiliging of de meer functierijke Intune-oplossing kiezen. Wijs een Intune-licentie toe om de Intune-functies in te stellen.

| Functiegebied | Highlights van functies | Basic Mobility en Security | Microsoft Intune |
|:-----|:-----|:-----|:-----|
|Apparaattypen|Verschillende besturingssystemen en hoofdbeheermodusvarianten beheren. |Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>|Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>mac OS, iPad OS|
|Apparaat compliance|Beveiligingsbeleid instellen en beheren, zoals pincodevergrendeling op apparaatniveau en jailbreakdetectie. |Beperkingen op Android 9- en latere apparaten. Zie [details.](capabilities.md) |Ja|
|Voorwaardelijke toegang op basis van apparaat compliance |Voorkomen dat niet-compatibele apparaten toegang krijgen tot zakelijke e-mail en gegevens vanuit de cloud. |Wordt niet ondersteund in Windows 10.<br/>Beperkt tot het beheren van toegang tot Exchange Online, SharePoint Online en Outlook. |Ja |
|Apparaatconfiguratie  |Apparaatinstellingen configureren (bijvoorbeeld de camera uitschakelen)|Beperkte set instellingen.|Ja|
|Apparaat compliance  |Beveiligingsbeleid instellen en beheren, zoals pincodevergrendeling op apparaatniveau en jailbreakdetectie. |Beperkingen op Android 9- en latere apparaten. Zie [details.](capabilities.md) |Ja|
|E-mailprofielen  |Een eigen e-mailprofiel inrichten op het apparaat. |Ja|Ja|
|WiFi-profielen |Een native WiFi-profiel inrichten op het apparaat. |Nee|Ja|
|VPN-profielen |Een native VPN-profiel inrichten op het apparaat. |Nee|Ja|
|Mobiel toepassingsbeheer  |Implementeer uw interne line-of-business-apps en van appsstores naar gebruikers. |Nee|Ja|
|Beveiliging van mobiele toepassingen  |Uw gebruikers in staat stellen om veilig toegang te krijgen tot bedrijfsgegevens met behulp van de mobiele Office-apps en line-of-business-apps die ze kennen, en tegelijkertijd de beveiliging van gegevens te waarborgen door acties zoals kopiëren, knippen, plakken en opslaan als te beperken tot alleen de apps die zijn goedgekeurd voor bedrijfsgegevens. Werkt zelfs als de apparaten niet zijn geregistreerd voor Basismobiliteit en Beveiliging. Zie App-gegevens beveiligen met MAM-beleid. |Nee|Ja|
|Beheerde browser  |Schakel veiliger surfen op het web in met de Edge-app. |Nee|Ja|
|Programma's voor registratie zonder aanraking (AutoPilot) |Schrijf grote aantallen apparaten van het bedrijf in en vereenvoudig de installatie van gebruikers. |Nee|Ja|
|||

Naast functies die in de vorige tabel worden vermeld, bevatten Basismobiliteit en Beveiliging en Intune beide een reeks externe acties die opdrachten verzenden naar apparaten via internet. U kunt bijvoorbeeld Office-gegevens van het apparaat van een werknemer verwijderen terwijl u persoonlijke gegevens op zijn plaats laat (met pensioen gaan), Office-apps van het apparaat van een werknemer verwijderen (wissen) of een apparaat opnieuw instellen op de fabrieksinstellingen (volledig wissen). 

Basisacties voor mobiliteit en beveiliging op afstand zijn terugtrekken, wissen en volledig wissen. Zie mogelijkheden van Basismobiliteit en Beveiliging voor meer informatie over basismobiliteits- [en beveiligingsacties.](capabilities.md)

Met Intune hebt u de volgende reeks acties:

-   Autopilot resetten (alleen Windows
-  [Bitlocker-toets draaien](/mem/intune/protect/encrypt-devices#rotate-bitlocker-recovery-keys)   (Alleen Windows)
-  [Het apparaat wissen, met pensioen gaan of handmatig uitrollen gebruiken](/mem/intune/remote-actions/devices-wipe#delete-devices-from-the-intune-portal)
-  [Activeringslocatie uitschakelen](/mem/intune/remote-actions/device-activation-lock-disable)   (alleen iOS)
-  [Nieuwe start](/mem/intune/remote-actions/device-fresh-start)   (Alleen Windows)
- [Volledige scan](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)   (Alleen Windows 10)
- [Apparaat zoeken](/mem/intune/remote-actions/device-locate)   (alleen iOS)
- [Modus Verloren](/mem/intune/remote-actions/device-lost-mode)   (alleen iOS)- [Snelle scan](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)(alleen windows 10)
- [Afstandsbediening voor Android](/mem/intune/remote-actions/teamviewer-support)
- [Vergrendeling op afstand](/mem/intune/remote-actions/device-remote-lock)
- [Naam van apparaat wijzigen](/mem/intune/remote-actions/device-rename)
-  [Wachtwoordcode opnieuw instellen](/mem/intune/remote-actions/device-passcode-reset) [Opnieuw](/mem/intune/remote-actions/device-restart)   starten (alleen windows)
-  Windows Defender-beveiligingsinformatie bijwerken (alleen windows)
-  Windows 10-pincode opnieuw instellen (alleen Windows)
-  [Aangepaste meldingen verzenden](/mem/intune/remote-actions/custom-notifications#send-a-custom-notification-to-a-single-device)   (Android, iOS, iPad OS)
-  [Apparaat synchroniseren](/mem/intune/remote-actions/device-sync)

Zie Microsoft Intune-documentatie voor meer informatie over [Intune-acties.](/mem/intune/)