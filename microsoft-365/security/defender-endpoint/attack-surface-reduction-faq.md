---
title: Veelgestelde vragen over surface reduction attack
description: Hier vindt u antwoorden op veelgestelde vragen over de attack surface reduction-regels van Microsoft Defender ATP.
keywords: Attack surface reduction rules, asr, hips, host intrusion prevention system, protection rules, anti-exploit, anti-exploit, exploit, infection prevention, microsoft defender for endpoint
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: martyav
ms.author: v-maave
ms.reviewer: ''
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.openlocfilehash: 7685bd70d85ecebe759ade762b78ee2c3639cea8
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51057161"
---
# <a name="attack-surface-reduction-frequently-asked-questions-faq"></a>Veelgestelde vragen over surface reduction attack

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


## <a name="is-attack-surface-reduction-asr-part-of-windows"></a>Maakt attack surface reduction (ASR) deel uit van Windows?

ASR was oorspronkelijk een functie van de suite met exploit guard-functies die werden geïntroduceerd als een belangrijke update voor Microsoft Defender Antivirus, in Windows 10, versie 1709. Microsoft Defender Antivirus is het oorspronkelijke antimalwareonderdeel van Windows. De volledige ASR-functieset is echter alleen beschikbaar met een Windows Enterprise-licentie. Houd er ook rekening mee dat uitsluitingen van ASR-regels afzonderlijk worden beheerd van Microsoft Defender Antivirus-uitsluitingen.

## <a name="do-i-need-to-have-an-enterprise-license-to-run-asr-rules"></a>Moet ik een ondernemingslicentie hebben om ASR-regels uit te voeren?

De volledige set ASR-regels en -functies wordt alleen ondersteund als u een ondernemingslicentie voor Windows 10 hebt. Een beperkt aantal regels kan werken zonder een ondernemingslicentie. Als u Microsoft 365 Business hebt, stelt u Microsoft Defender Antivirus in als uw primaire beveiligingsoplossing en schakel u de regels in via PowerShell. Asr-gebruik zonder ondernemingslicentie wordt echter niet officieel ondersteund en de volledige mogelijkheden van ASR zijn niet beschikbaar.

Zie Windows [10 Licensing](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) voor meer informatie over Windows-licenties en de [handleiding Volumelicenties voor Windows 10.](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf)

## <a name="is-asr-supported-if-i-have-an-e3-license"></a>Wordt ASR ondersteund als ik een E3-licentie heb?

Ja. ASR wordt ondersteund voor Windows Enterprise E3 en hoger. 

## <a name="which-features-are-supported-with-an-e5-license"></a>Welke functies worden ondersteund met een E5-licentie?

Alle regels die met E3 worden ondersteund, worden ook ondersteund met E5.

E5 heeft ook een grotere integratie met Defender voor Eindpunt toegevoegd. Met E5 kunt u [Defender](https://docs.microsoft.com/microsoft-365/security/defender/monitor-devices?view=o365-worldwide&preserve-view=true#monitor-and-manage-asr-rule-deployment-and-detections) voor Eindpunt gebruiken om analyses van waarschuwingen in realtime te controleren en te controleren, regeluitsluitingen aan te passen, ASR-regels te configureren en lijsten met gebeurtenisrapporten weer te geven.

## <a name="what-are-the-currently-supported-asr-rules"></a>Wat zijn de momenteel ondersteunde ASR-regels?

ASR ondersteunt momenteel alle onderstaande regels:

* [Uitvoerbare inhoud van e-mailclient en webmail blokkeren](attack-surface-reduction.md#block-executable-content-from-email-client-and-webmail)
* [Alle Office-toepassingen blokkeren om onderliggende processen te maken](attack-surface-reduction.md#block-all-office-applications-from-creating-child-processes)
* [Voorkomen dat Office-toepassingen uitvoerbare inhoud maken](attack-surface-reduction.md#block-office-applications-from-creating-executable-content)
* [Office-toepassingen blokkeren om code in andere processen te injecteren](attack-surface-reduction.md#block-office-applications-from-injecting-code-into-other-processes)
* [JavaScript of VBScript blokkeren om gedownloade uitvoerbare inhoud te starten](attack-surface-reduction.md#block-javascript-or-vbscript-from-launching-downloaded-executable-content)
* [De uitvoering van mogelijk obfuscated scripts blokkeren](attack-surface-reduction.md#block-execution-of-potentially-obfuscated-scripts)
* [Win32 API-oproepen blokkeren vanuit Office-macro](attack-surface-reduction.md#block-win32-api-calls-from-office-macros)
* [Geavanceerde beveiliging tegen ransomware gebruiken](attack-surface-reduction.md#use-advanced-protection-against-ransomware)
* [Het stelen van referenties blokkeren van het subsysteem](attack-surface-reduction.md#block-credential-stealing-from-the-windows-local-security-authority-subsystem) van de lokale beveiligingsinstantie van Windows (lsass.exe)
* [Procescreaties blokkeren die afkomstig zijn van PSExec- en WMI-opdrachten](attack-surface-reduction.md#block-process-creations-originating-from-psexec-and-wmi-commands)
* [Niet-vertrouwde en niet-ondertekende processen blokkeren die worden uitgevoerd via USB](attack-surface-reduction.md#block-untrusted-and-unsigned-processes-that-run-from-usb)
* [Het uitvoeren van uitvoerbare bestanden blokkeren, tenzij ze voldoen aan een criteria voor gebruik, leeftijd of vertrouwde lijst](attack-surface-reduction.md#block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion)
* [Office-communicatietoepassingen blokkeren om onderliggende processen te maken](attack-surface-reduction.md#block-office-communication-application-from-creating-child-processes)
* [Adobe Reader blokkeren om onderliggende processen te maken](attack-surface-reduction.md#block-adobe-reader-from-creating-child-processes)
* [Persistentie blokkeren via WMI-gebeurtenisabonnement](attack-surface-reduction.md#block-persistence-through-wmi-event-subscription)

## <a name="what-are-some-good-recommendations-for-getting-started-with-asr"></a>Wat zijn enkele goede aanbevelingen om aan de slag te gaan met ASR?

Test hoe ASR-regels van invloed zijn op uw organisatie voordat u deze inschakelen door ASR-regels voor een korte periode in de auditmodus uit te voeren. Terwijl u de regels in de auditmodus gebruikt, kunt u alle zakelijke toepassingen identificeren die mogelijk ten onrechte worden geblokkeerd en deze uitsluiten van ASR.

Grotere organisaties moeten overwegen ASR-regels in 'ringen' uit te rollen door regels in steeds bredere subsets van apparaten te controleren en in te stellen. U kunt de apparaten van uw organisatie rangschikt in ringen met Behulp van Intune of een hulpprogramma voor groepsbeleidsbeheer.

## <a name="how-long-should-i-test-an-asr-rule-in-audit-mode-before-enabling-it"></a>Hoe lang moet ik een ASR-regel testen in de auditmodus voordat ik deze inschakelen?

Houd de regel ongeveer 30 dagen in de auditmodus om een goede basislijn te krijgen voor de werking van de regel zodra deze in de hele organisatie wordt uitgevoerd. Tijdens de controleperiode kunt u alle zakelijke toepassingen identificeren die mogelijk door de regel worden geblokkeerd en kunt u de regel zo configureren dat deze worden uitgesloten.

## <a name="im-making-the-switch-from-a-third-party-security-solution-to-defender-for-endpoint-is-there-an-easy-way-to-export-rules-from-another-security-solution-to-asr"></a>Ik maak de overstap van een beveiligingsoplossing van derden naar Defender voor Eindpunt. Is er een 'eenvoudige' manier om regels van een andere beveiligingsoplossing naar ASR te exporteren?

In de meeste gevallen is het gemakkelijker en beter om te beginnen met de basislijnaanbevelingen die [door Defender](https://docs.microsoft.com/windows/security/threat-protection) voor Eindpunt worden voorgesteld, dan om te proberen regels te importeren uit een andere beveiligingsoplossing. Gebruik vervolgens hulpprogramma's zoals auditmodus, monitoring en analyse om uw nieuwe oplossing te configureren die aan uw unieke behoeften is aangepast. 

De standaardconfiguratie voor de meeste ASR-regels, gecombineerd met de real-time beveiliging van Defender voor Endpoint, beschermt tegen een groot aantal exploits en beveiligingslekken.

Vanuit Defender voor Eindpunt kunt u uw verdediging bijwerken met aangepaste indicatoren om bepaalde softwaregedrag toe te staan en te blokkeren. ASR maakt het ook mogelijk regels aan te passen, in de vorm van bestands- en mapuitsluitingen. Over het algemeen is het het beste om een regel een bepaalde periode te controleren en uitsluitingen te configureren voor alle bedrijfstoepassingen die mogelijk worden geblokkeerd.

## <a name="does-asr-support-file-or-folder-exclusions-that-include-system-variables-and-wildcards-in-the-path"></a>Ondersteunt ASR bestands- of mapuitsluitingen die systeemvariabelen en jokertekens in het pad bevatten?

Ja. Zie Bestanden en mappen uitsluiten van [ASR-regels](enable-attack-surface-reduction.md#exclude-files-and-folders-from-asr-rules) voor meer informatie over het uitsluiten van bestanden of mappen van ASR-regels en Het configureren en valideren van uitsluitingen op basis van bestandsextensie en maplocatie voor meer informatie over het gebruik van systeemvariabelen en jokertekens in uitgesloten [bestandspaden.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)

## <a name="do-asr-rules-cover-all-applications-by-default"></a>Gelden ASR-regels standaard voor alle toepassingen?

Dit hangt af van de regel. De meeste ASR-regels hebben betrekking op het gedrag van Microsoft Office-producten en -services, zoals Word, Excel, PowerPoint en OneNote of Outlook. Bepaalde ASR-regels, zoals Blokuitvoering van mogelijk *obfuscated scripts,* zijn algemener van omvang.

## <a name="does-asr-support-third-party-security-solutions"></a>Ondersteunt ASR beveiligingsoplossingen van derden?

ASR gebruikt Microsoft Defender Antivirus om toepassingen te blokkeren. Het is niet mogelijk om ASR te configureren voor het gebruik van een andere beveiligingsoplossing voor blokkeren op dit moment.

## <a name="i-have-an-e5-license-and-enabled-some-asr-rules-in-conjunction-with-defender-for-endpoint-is-it-possible-for-an-asr-event-to-not-show-up-at-all-in-defender-for-endpoints-event-timeline"></a>Ik heb een E5-licentie en heb enkele ASR-regels ingeschakeld in combinatie met Defender voor Eindpunt. Is het mogelijk dat een ASR-gebeurtenis helemaal niet wordt weergegeven in de tijdlijn van de gebeurtenis van Defender voor Eindpunt?

Wanneer een melding lokaal wordt geactiveerd door een ASR-regel, wordt er ook een rapport over de gebeurtenis verzonden naar de Defender for Endpoint-portal. Als u problemen hebt met het vinden van de gebeurtenis, kunt u de tijdlijn voor gebeurtenissen filteren met behulp van het zoekvak. U kunt ASR-gebeurtenissen ook bekijken door naar Ga naar **surfacebeheer** aanvallen te gaan, vanuit het pictogram **Configuratiebeheer** op de taakbalk van het beveiligingscentrum. De pagina Aanvalsoppervlakbeheer bevat een tabblad voor rapportdetecties, met een volledige lijst met ASR-regelgebeurtenissen die zijn gerapporteerd aan Defender voor Eindpunt.

## <a name="i-applied-a-rule-using-gpo-now-when-i-try-to-check-the-indexing-options-for-the-rule-in-microsoft-outlook-i-get-a-message-stating-access-denied"></a>Ik heb een regel toegepast met GPO. Als ik nu de indexeringsopties voor de regel in Microsoft Outlook probeer te controleren, krijg ik een bericht met de tekst 'Toegang geweigerd'.

Open de indexeringsopties rechtstreeks vanuit Windows 10.

1. Selecteer het **pictogram Zoeken** op de Windows-taakbalk.

1. Voer **indexeringsopties** in het zoekvak in.

## <a name="are-the-criteria-used-by-the-rule-block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion-configurable-by-an-admin"></a>Zijn de criteria die worden gebruikt door de regel 'Blokkeer uitvoerbare bestanden uit te voeren, tenzij ze voldoen aan een criterium voor de prevalentie, leeftijd of vertrouwde lijst', configureerbaar door een beheerder?

Nee. De criteria die door deze regel worden gebruikt, worden door Microsoft cloudbeveiliging gehandhaafd, om de vertrouwde lijst voortdurend up-to-date te houden met gegevens die van over de hele wereld zijn verzameld. Lokale beheerders hebben geen schrijftoegang om deze gegevens te wijzigen. Als u deze regel wilt configureren om deze aan te passen aan uw bedrijf, kunt u bepaalde toepassingen toevoegen aan de lijst met uitsluitingen om te voorkomen dat de regel wordt geactiveerd.

## <a name="i-enabled-the-asr-rule-block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion-after-some-time-i-updated-a-piece-of-software-and-the-rule-is-now-blocking-it-even-though-it-didnt-before-did-something-go-wrong"></a>Ik heb de ASR-regel ingeschakeld om uitvoerbare bestanden niet uit te voeren, tenzij ze voldoen aan een criterium voor *prevalentie, leeftijd of vertrouwde lijst.* Na enige tijd heb ik een stukje software bijgewerkt en de regel blokkeert deze nu, ook al is dit niet eerder gebeurd. Is er iets misgegaan?

Deze regel is afhankelijk van elke toepassing met een bekende reputatie, zoals gemeten op basis van de prevalentie, leeftijd of opname in een lijst met vertrouwde apps. Het besluit van de regel om een toepassing te blokkeren of toe te staan, wordt uiteindelijk bepaald door de beoordeling van deze criteria door Microsoft Cloud Protection.

Meestal kan cloudbeveiliging bepalen dat een nieuwe versie van een toepassing vergelijkbaar is met eerdere versies, zodat deze niet uitgebreid opnieuw hoeft te worden beoordeeld. Het kan echter enige tijd duren voor de app een reputatie heeft opgebouwd nadat u van versie hebt gewisseld, met name na een grote update. In de tussentijd kunt u de toepassing toevoegen aan de lijst met uitsluitingen, om te voorkomen dat deze regel belangrijke toepassingen blokkeert. Als u regelmatig werkt met nieuwe versies van toepassingen, kunt u ervoor kiezen om deze regel uit te voeren in de auditmodus.

## <a name="i-recently-enabled-the-asr-rule-block-credential-stealing-from-the-windows-local-security-authority-subsystem-lsassexe-and-i-am-getting-a-large-number-of-notifications-what-is-going-on"></a>Ik heb onlangs de ASR-regel, Het stelen van referenties blokkeren van het subsysteem van de lokale beveiligingsinstantie *van Windows (lsass.exe)* ingeschakeld en ik krijg een groot aantal meldingen. Wat gebeurt er?

Een melding die door deze regel wordt gegenereerd, geeft niet noodzakelijkerwijs schadelijke activiteiten aan. Deze regel is echter nog steeds handig voor het blokkeren van schadelijke activiteiten, omdat malware vaak is gericht op lsass.exe toegang tot accounts te verkrijgen. In lsass.exe proces worden gebruikersreferenties opgeslagen in het geheugen nadat een gebruiker zich heeft aangemeld. Windows gebruikt deze referenties om gebruikers te valideren en lokaal beveiligingsbeleid toe te passen.

Omdat veel legitieme processen gedurende een normale dag een beroep doen op lsass.exe referenties, kan deze regel vooral luidruchtig zijn. Als een bekende legitieme toepassing ervoor zorgt dat deze regel een te groot aantal meldingen genereert, kunt u deze toevoegen aan de uitsluitingslijst. De meeste andere ASR-regels genereren een relatief kleiner aantal meldingen, in vergelijking met deze, omdat het inroepen van lsass.exe typt voor de normale werking van veel toepassingen.

## <a name="is-it-a-good-idea-to-enable-the-rule-block-credential-stealing-from-the-windows-local-security-authority-subsystem-lsassexe-alongside-lsa-protection"></a>Is het een goed idee om de regel, Het stelen van referenties van het *windows local security authority subsysteem (lsass.exe)* in teschakelen, naast LSA-beveiliging?

Het inschakelen van deze regel biedt geen extra beveiliging als [U ook LSA-beveiliging](https://docs.microsoft.com/windows-server/security/credentials-protection-and-management/configuring-additional-lsa-protection#BKMK_HowToConfigure) hebt ingeschakeld. Zowel de regel als de LSA-beveiliging werken op vrijwel dezelfde manier, dus beide tegelijk uitvoeren is overbodig. Soms kunt u echter geen LSA-beveiliging inschakelen. In die gevallen kunt u deze regel inschakelen om vergelijkbare bescherming te bieden tegen malware die lsass.exe.

## <a name="see-also"></a>Zie ook

* [Overzicht van de surface reduction van attack](attack-surface-reduction.md)
* [Regels voor het verlagen van het oppervlak van de aanval evalueren](evaluate-attack-surface-reduction.md)
* [Surface Reduction-regels voor aanvallen aanpassen](customize-attack-surface-reduction.md)
* [Regels voor het verlagen van de surface voor aanvallen inschakelen](enable-attack-surface-reduction.md)
* [Compatibiliteit van Microsoft Defender met andere antivirus-/antimalware](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)