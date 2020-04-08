---
title: DKIM gebruiken voor e-mail in uw aangepaste domein in Office 365, 2048-bit, 1024-bit, stappen, hoe het werkt, SPF, DMARC
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 10/8/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 56fee1c7-dc37-470e-9b09-33fff6d94617
ms.collection:
- M365-security-compliance
description: 'Samenvatting: In dit artikel wordt beschreven hoe u DKIM (DomainKeys Identified Mail) gebruikt in Office 365 om ervoor te zorgen dat de ontvangende e-mailsystemen berichten vertrouwen die worden verzonden vanuit uw aangepaste domein.'
ms.openlocfilehash: d76c31c6a3f0ce1550f0259ee40996189b60cb79
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42811641"
---
# <a name="use-dkim-to-validate-outbound-email-sent-from-your-custom-domain-in-office-365"></a>DKIM gebruiken om uitgaande e-mail te valideren die wordt verzonden vanuit uw aangepaste domein in Office 365

 **Samenvatting**: In dit artikel wordt beschreven hoe u DKIM (DomainKeys Identified Mail) gebruikt met Office 365 om ervoor te zorgen dat de ontvangende e-mailsystemen de uitgaande berichten vertrouwen die worden verzonden vanuit uw aangepaste domein.

U dient DKIM te gebruiken naast SPF en DMARC om te voorkomen dat spoofing-oplichters berichten verzenden die er uitzien alsof deze afkomstig zijn van uw domein. Met DKIM kunt u een digitale handtekening toevoegen aan uitgaande e-mailberichten in de berichtkop. Het klinkt misschien ingewikkeld, maar dat is echt niet. Wanneer u DKIM configureert, geeft u uw domein toestemming om de domeinnaam aan een e-mailbericht te koppelen met behulp van cryptografische verificatie. Een soort handtekening van uw domein, dus. E-mailsystemen die e-mail vanaf uw domein ontvangen, kunnen deze digitale handtekening gebruiken om te bepalen of de inkomende e-mail echt is.

Simpel gezegd gebruikt u een persoonlijke sleutel om de berichtkop in de uitgaande e-mail van uw domein te versleutelen. U publiceert een openbare sleutel naar de DNS-records van uw domein die vervolgens door ontvangende servers wordt gebruikt om de handtekening te decoderen. Ze gebruiken de openbare sleutel om te verifiëren dat de berichten werkelijk van u afkomstig zijn en niet afkomstig zijn van iemand die uw domein *spooft*.

In Office 365 wordt DKIM automatisch ingesteld voor de oorspronkelijke 'onmicrosoft.com'-domeinen. Dat betekent dat u niets hoeft te doen om DKIM in te stellen voor enige oorspronkelijke domeinnaam (bijvoorbeeld litware.onmicrosoft.com). Zie [Veelgestelde vragen over domeinen](https://docs.microsoft.com/office365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain) voor meer informatie over domeinen.

U kunt er ook voor kiezen om niets te doen met DKIM voor uw aangepaste domein. Als u geen DKIM voor uw aangepaste domein instelt, maakt Office 365 een persoonlijk en openbare sleutelpaar en wordt DKIM-ondertekening ingeschakeld. Vervolgens wordt het standaardbeleid van Office 365 voor uw aangepaste domein geconfigureerd. Hoewel dit voldoende is voor de meeste Office 365-klanten, moet u de DKIM voor uw aangepaste domein handmatig configureren in de volgende gevallen:

- U hebt meer dan één aangepast domein in Office 365

- U wilt ook DMARC instellen (aanbevolen)

- U wilt controle over uw persoonlijke sleutel

- U wilt de CNAME-records aanpassen

- U wilt DKIM-sleutels instellen voor e-mail die afkomstig is van een extern domein, bijvoorbeeld als u bulkmails via een derde verzendt.

In dit artikel:

- [Hoe DKIM beter werkt dan alleen SPF om schadelijke spoofing in Office 365 te voorkomen](use-dkim-to-validate-outbound-email.md#HowDKIMWorks)

- [Uw 1024-bits sleutels handmatig upgraden naar 2048-bits DKIM-versleutelingssleutels](use-dkim-to-validate-outbound-email.md#1024to2048DKIM)

- [Stappen die u moet uitvoeren om DKIM handmatig in te stellen in Office 365](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365)

- [DKIM configureren voor meer dan één aangepast domein in Office 365](use-dkim-to-validate-outbound-email.md#DKIMMultiDomain)

- [Het DKIM-handtekeningenbeleid uitschakelen voor een aangepast domein in Office 365](use-dkim-to-validate-outbound-email.md#DisableDKIMSigningPolicy)

- [Standaardgedrag voor DKIM en Office 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior)

- [DKIM instellen zodat een externe service namens uw aangepaste domein e-mails kan verzenden of spoofen](use-dkim-to-validate-outbound-email.md#SetUp3rdPartyspoof)

- [Volgende stappen: nadat u DKIM hebt ingesteld voor Office 365](use-dkim-to-validate-outbound-email.md#DKIMNextSteps)

## <a name="how-dkim-works-better-than-spf-alone-to-prevent-malicious-spoofing-in-office-365"></a>Hoe DKIM beter werkt dan alleen SPF om schadelijke spoofing in Office 365 te voorkomen
<a name="HowDKIMWorks"> </a>

Met SPF worden er gegevens aan een berichtenenvelop toegevoegd, maar met DKIM wordt een handtekening in de berichtkop daadwerkelijk versleuteld. Wanneer u een bericht doorstuurt, kunnen gedeelten van die berichtenenvelop door de doorsturende server worden verwijderd. Aangezien de digitale handtekening bij het e-mailbericht blijft, omdat deze namelijk deel uitmaakt van de e-mailberichtkop, werkt DKIM zelfs als een bericht is doorgestuurd, zoals weergegeven in het volgende voorbeeld.

![Diagram met een doorgestuurde bericht waarbij de DKIM-verificatie lukt terwijl de SPF-controle mislukt](../../media/28f93b4c-97e7-4309-acc4-fd0d2e0e3377.jpg)

Als u in dit voorbeeld slechts een TXT-record voor SPF had gepubliceerd voor uw domein kon de ontvangende e-mailserver uw e-mail als spam hebben gemarkeerd en een fout-positief resultaat hebben gegenereerd. Met het toevoegen van DKIM in dit scenario wordt het aantal fout-positieve spammeldingen beperkt. Omdat DKIM gebruikmaakt van de cryptografie van een openbare sleutel om te verifiëren en niet alleen van IP-adressen, wordt DKIM als een veel sterkere verificatievorm dan SPF beschouwd. Wij raden u aan om in uw implementatie SPF en DKIM te gebruiken, evenals DMARC.

Kortom: DKIM gebruikt een persoonlijke sleutel om een versleutelde handtekening in de berichtkoppen in te voegen. Het ondertekenende of uitgaande domein wordt in de kop ingevoegd als de waarde van het veld **d=**. Het verifiërende of ontvangende domein gebruikt vervolgens het veld **d=** om de openbare sleutel uit DNS te zoeken en het bericht te verifiëren. Als het bericht is geverifieerd, is de DKIM-controle gelukt.

## <a name="manually-upgrade-your-1024-bit-keys-to-2048-bit-dkim-encryption-keys"></a>Uw 1024-bits sleutels handmatig upgraden naar 2048-bits DKIM-versleutelingssleutels
<a name="1024to2048DKIM"> </a>

Aangezien zowel 1024- als 2048-bits voor DKIM-sleutels worden ondersteund, wordt in deze instructies uitgelegd hoe u de 1024-bits sleutel moet upgraden naar 2048-bits. De onderstaande stappen zijn voor twee gebruikscases: kies de optie die het geschiktst is voor uw configuratie.

1. Wanneer u **al DKIM hebt geconfigureerd**, wijzigt u de hoeveelheid bits als volgt:
    1. [Maak verbinding met de Office 365-workloads via PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window). (De cmdlet is afkomstig van Exchange Online.)
    1. En voer vervolgens de volgende cmdlet uit:

&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`Rotate-DkimSigningConfig -KeySize 2048 -Identity {Guid of the existing Signing Config}`

1. Of voor een **nieuwe implementatie van DKIM**:
    1. [Maak verbinding met de Office 365-workloads via PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window). (Dit is de cmdlet van Exchange Online.)
    1. Voer de volgende cmdlet uit:

&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; `New-DkimSigningConfig -DomainName {Domain for which config is to be created} -KeySize 2048 -Enabled $True`

Blijf verbonden met Office 365 om de configuratie te *verifiëren*.

2. Voer deze cmdlet uit:

&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; `Get-DkimSigningConfig | fl`

> [!TIP]
>Deze nieuwe 2048-bits sleutel wordt gebruikt vanaf RotateOnDate en verzendt in de tussentijd e-mails met de 1024-bits sleutel. Na vier dagen kunt u opnieuw testen met de 2048-bits sleutel (dat wil zeggen, wanneer de wijziging wordt toegepast op de tweede kiezer).

Als u de tweede kiezer wilt wijzigen, kunt u kiezen uit a) de Office 365-service de kiezer laten wijzigen en upgraden naar 2048-bits binnen de komende zes maanden of b) na 4 dagen en bevestigen dat 2048-bits wordt gebruikt, de tweede kiezer handmatig wijzigen met gebruik van de geschikte hierboven vermelde cmdlet.

## <a name="steps-you-need-to-do-to-manually-set-up-dkim-in-office-365"></a>Stappen die u moet uitvoeren om DKIM handmatig in te stellen in Office 365
<a name="SetUpDKIMO365"> </a>

Als u DKIM wilt configureren, voert u de volgende stappen uit:

- [Twee CNAME-records voor uw aangepaste domein in DNS publiceren](use-dkim-to-validate-outbound-email.md#Publish2CNAME)

- [DKIM-ondertekening voor uw aangepaste domein in Office 365 inschakelen](use-dkim-to-validate-outbound-email.md#EnableDKIMinO365)

### <a name="publish-two-cname-records-for-your-custom-domain-in-dns"></a>Twee CNAME-records voor uw aangepaste domein in DNS publiceren
<a name="Publish2CNAME"> </a>

U moet twee CNAME-records publiceren voor elk domein waarvoor u een DKIM-handtekening wilt toevoegen in DNS.

Voer de volgende opdrachten uit om de kiezer-records te maken:

```powershell
    New-DkimSigningConfig -DomainName <domain> -Enabled $false
    Get-DkimSigningConfig -Identity <domain> | fl Selector1CNAME, Selector2CNAME
```

Maak CNAME's waarnaar wordt verwezen in Get-DkimSigningConfig output

```powershell
    Set-DkimSigningConfig -Identity <domain> -Enabled $true
```

In Office 365 wordt de sleutelwijziging automatisch uitgevoerd op basis van de twee records die u instelt. Als u behalve het oorspronkelijke domein in Office 365 ook aangepaste domeinen hebt ingericht, moet u twee CNAME-records publiceren voor elk extra domein. Als u dus twee domeinen hebt, moet u twee extra CNAME-records publiceren, enzovoort.

Gebruik de volgende notatie voor de CNAME-records.

> [!IMPORTANT]
> Als u een van onze GCC High-klanten bent, wordt _domainGuid_ anders berekend! In plaats van de MX-record voor uw _initialDomain_ te zoeken, kunt u de _domainGuid_ berekenen. In plaats daarvan berekenen wij dit rechtstreeks vanuit het aangepaste domein. Als uw aangepaste domein bijvoorbeeld 'contoso.com' is, wordt de domainGuid 'contoso-com': alle punten worden vervangen door een streepje. Ongeacht de MX-record waarnaar uw initialDomain wijst, gebruikt u altijd de bovenstaande methode om de domainGuid te berekenen die u wilt gebruiken in de CNAME-records.

```text
Host name:          selector1._domainkey
Points to address or value: selector1-<domainGUID>._domainkey.<initialDomain>
TTL:                3600

Host name:          selector2._domainkey
Points to address or value: selector2-<domainGUID>._domainkey.<initialDomain>
TTL:                3600
```

Waarbij:

- Voor Office 365 de kiezers altijd 'kiezer1' of 'kiezer2' is.

- _domainGUID_ is dezelfde als de _domainGUID_ in de aangepaste MX-record voor uw aangepaste domein dat vóór mail.protection.outlook.com wordt weergegeven. In de volgende MX-record voor het domein contoso.com, is de _domainGUID_ bijvoorbeeld contoso-com:

    ```text
    contoso.com.  3600  IN  MX   5 contoso-com.mail.protection.outlook.com
    ```

- _initialDomain_ is het domein dat u hebt gebruikt toen u zich aanmeldde voor Office 365. Oorspronkelijke domeinen moeten altijd eindigen op onmicrosoft.com. Zie [Veelgestelde vragen over domeinen](https://docs.microsoft.com/office365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain)voor meer informatie over het bepalen van uw oorspronkelijke domein.

Als u bijvoorbeeld het oorspronkelijk domein cohovineyardandwinery.onmicrosoft.com hebt en twee aangepaste domeinen cohovineyard.com en cohowinery.com, moet u twee CNAME-records instellen voor elk extra domein: dus een totaal van vier CNAME-records.

```text
Host name:          selector1._domainkey
Points to address or value: selector1-cohovineyard-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:          selector2._domainkey
Points to address or value: selector2-cohovineyard-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:          selector1._domainkey
Points to address or value: selector1-cohowinery-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:          selector2._domainkey
Points to address or value: selector2-cohowinery-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600
```

> [!NOTE]
> Het is belangrijk om de tweede record te maken, maar mogelijk is slechts één van de kiezers beschikbaar op het moment dat het bestand wordt gemaakt. In wezen kan de tweede kiezer verwijzen naar een adres dat nog niet is gemaakt. We raden niettemin u aan om de tweede CNAME-record te maken, omdat de sleutelwijziging probleemloos zal verlopen en u hoeft zelf geen handmatige stappen te doorlopen.

### <a name="enable-dkim-signing-for-your-custom-domain-in-office-365"></a>DKIM-ondertekening voor uw aangepaste domein in Office 365 inschakelen
<a name="EnableDKIMinO365"> </a>

Als u de CNAME-records in DNS hebt gepubliceerd, kunt u DKIM-ondertekening inschakelen via Office 365. U kunt dit doen via het Microsoft 365-beheercentrum of met behulp van Windows PowerShell.

#### <a name="to-enable-dkim-signing-for-your-custom-domain-through-the-admin-center"></a>DKIM-ondertekening voor uw aangepaste domein inschakelen via het Beheercentrum

1. [Meld u aan bij Office 365](https://support.office.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4) met uw werk- of schoolaccount.

2. Selecteer het pictogram voor het startprogramma voor apps in de linkerbovenhoek en kies **Beheer**.

3. Vouw in het navigatievenster aan de linkerkant **Beheerder** uit en kies **Exchange**.

4. Ga naar **Bescherming** \> **dkim**.

5. Selecteer het domein waarvoor u DKIM wilt inschakelen en kies vervolgens **Inschakelen** voor **Berichten voor dit domein ondertekenen met DKIM-handtekeningen**. Herhaal deze stap voor elk aangepast domein.

#### <a name="to-enable-dkim-signing-for-your-custom-domain-by-using-powershell"></a>DKIM-ondertekening voor uw aangepaste domein inschakelen met behulp van Windows PowerShell

1. [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).

2. Voer de volgende opdracht uit:

    ```powershell
    Set-DkimSigningConfig -Identity <domain> -Enabled $true
    ```

   Waarbij _domein_ de naam van het aangepaste domein is waarvoor u DKIM-ondertekening wilt inschakelen.

   Voor bijvoorbeeld het domein contoso.com:

    ```powershell
    Set-DkimSigningConfig -Identity contoso.com -Enabled $true
    ```

#### <a name="to-confirm-dkim-signing-is-configured-properly-for-office-365"></a>Om te bevestigen dat DKIM-ondertekening correct is geconfigureerd voor Office 365

Wacht een paar minuten voordat u deze stappen uitvoert om te bevestigen dat u de DKIM correct hebt geconfigureerd. Dit zorgt ervoor dat de DKIM-informatie over het domein wordt verspreid in het hele netwerk.

- Verzend een bericht vanuit een account in uw Office 365-domein met ingeschakelde DKIM naar een ander e-mailaccount, zoals outlook.com of Hotmail.com.

- Gebruik geen aol.com-account voor testdoeleinden. AOL kan het DKIM-controle overslaan als de SPF-controle slaagt. De test wordt hierdoor zinloos.

- Open het bericht en bekijk de berichtkop. De instructies voor het bekijken van berichtkop tekst kan variëren afhankelijk van uw e-mailclient. Voor instructies over het bekijken van berichtkoppen in Outlook, raadpleegt u [E-mailberichtkoppen bekijken](https://support.office.com/article/CD039382-DC6E-4264-AC74-C048563D212C).

  Het DKIM-ondertekend bericht bevat de host- en domeinnaam die u hebt gedefinieerd toen u de CNAME-gegevens publiceerde. Het bericht ziet er nu ongeveer zo uit:

  ```text
    From: Example User <example@contoso.com>
    DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed;
        s=selector1; d=contoso.com; t=1429912795;
        h=From:To:Message-ID:Subject:MIME-Version:Content-Type;
        bh=<body hash>;
        b=<signed field>;
  ```

- Zoek naar de berichtkop Authentication-Results. Hoewel elke ontvangende service een iets andere notatie gebruikt om de binnenkomende e-mail te stempelen, moet het resultaat iets bevatten zoals **DKIM = Pass** of **DKIM = OK**.

## <a name="to-configure-dkim-for-more-than-one-custom-domain-in-office-365"></a>DKIM configureren voor meer dan één aangepast domein in Office 365
<a name="DKIMMultiDomain"> </a>

Als u in de toekomst besluit om een ander aangepast domein toe te voegen en u wilt DKIM inschakelen voor het nieuwe domein, moet u de stappen in dit artikel voor elk domein voltooien. Voer met name alle stappen uit in [Wat u moet doen om DKIM handmatig in te stellen in Office 365](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365).

## <a name="disabling-the-dkim-signing-policy-for-a-custom-domain-in-office-365"></a>Het DKIM-handtekeningenbeleid uitschakelen voor een aangepast domein in Office 365
<a name="DisableDKIMSigningPolicy"> </a>

Als u het handtekeningenbeleid uitschakelt, wordt DKIM niet volledig uitgeschakeld. Na een bepaalde tijd zal Office 365 automatisch het standaardbeleid van Office 365 toepassen op uw domein. Zie [Standaardgedrag voor DKIM en Office 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior) voor meer informatie.

### <a name="to-disable-the-dkim-signing-policy-by-using-windows-powershell"></a>Het DKIM-handtekeningenbeleid uitschakelen met behulp van Windows PowerShell

1. [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).

2. Voer een van de volgende opdrachten uit voor elk domein waarvoor u DKIM-ondertekening wilt uitschakelen.

    ```powershell
    $p = Get-DkimSigningConfig -Identity <domain>
    $p[0] | Set-DkimSigningConfig -Enabled $false
    ```

   Bijvoorbeeld:

    ```powershell
    $p = Get-DkimSigningConfig -Identity contoso.com
    $p[0] | Set-DkimSigningConfig -Enabled $false
    ```

   Of

    ```powershell
    Set-DkimSigningConfig -Identity $p[<number>].Identity -Enabled $false
    ```

    Hierbij is _nummer_ de index van het beleid. Bijvoorbeeld:

    ```powershell
    Set-DkimSigningConfig -Identity $p[0].Identity -Enabled $false
    ```

## <a name="default-behavior-for-dkim-and-office-365"></a>Standaardgedrag voor DKIM en Office 365
<a name="DefaultDKIMbehavior"> </a>

Als u DKIM niet inschakelt, maakt Office 365 automatisch een 1024-bits openbare sleutel voor uw standaarddomein en de bijbehorende persoonlijke sleutel die we intern opslaan in ons datacenter. In Office 365 wordt een standaardconfiguratie voor handtekeningen gebruikt voor domeinen die geen beleid hebben. Dit betekent dat als u DKIM niet zelf instelt, Office 365 gebruikmaakt van het standaardbeleid en de bijbehorende sleutels die daarvoor worden gemaakt, zodat DKIM voor uw domein wordt ingeschakeld.

Als u bovendien DKIM-ondertekening uitschakelt nadat u deze hebt ingeschakeld, wordt er in Office 365 na een bepaalde periode automatisch het standaardbeleid van Office 365 toegepast op uw domein.

Stel dat in het volgende voorbeeld DKIM voor fabrikam.com is ingeschakeld door Office 365 en niet door de beheerder van het domein. Dit betekent dat de vereiste CNAME's niet aanwezig zijn in DNS. DKIM-handtekeningen voor e-mail van dit domein zullen er ongeveer zo uitzien:

```text
From: Second Example <second.example@fabrikam.com>
DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed;
    s=selector1-fabrikam-com; d=contoso.onmicrosoft.com; t=1429912795;
    h=From:To:Message-ID:Subject:MIME-Version:Content-Type;
    bh=<body hash>;
    b=<signed field>;
```

In dit voorbeeld bevatten de hostnaam en het domein de waarden waarnaar de CNAME zou wijzen als DKIM-ondertekening voor fabrikam.com door de domeinbeheerder was ingeschakeld. Uiteindelijk wordt elk bericht dat wordt verzonden vanuit Office 365 DKIM-ondertekend. Als u DKIM zelf inschakelt, is het domein hetzelfde als het domein in het Van:-adres, in dit geval fabrikam.com. Als u dit niet doet, wordt het niet afgestemd en wordt in plaats daarvan het oorspronkelijke domein van uw organisatie gebruikt. Zie [Veelgestelde vragen over domeinen](https://docs.microsoft.com/office365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain)voor meer informatie over het bepalen van uw oorspronkelijke domein.

## <a name="set-up-dkim-so-that-a-third-party-service-can-send-or-spoof-email-on-behalf-of-your-custom-domain"></a>DKIM instellen zodat een externe service namens uw aangepaste domein e-mails kan verzenden of spoofen
<a name="SetUp3rdPartyspoof"> </a>

Bij sommige providers voor bulkmail, of providers van software-als-een-service, kunt u DKIM-sleutels instellen voor e-mail die afkomstig is van hun service. Hiervoor is coördinatie tussen uzelf en de derde partij nodig om de vereiste DNS-records in te stellen. Er zijn er geen twee organisaties die dit op precies dezelfde manier doen. In plaats daarvan hangt het proces volledig af van de organisatie.

Een voorbeeldbericht met een correct geconfigureerde DKIM voor contoso.com en bulkemailprovider.com kan er als volgt uitzien:

```text
Return-Path: <communication@bulkemailprovider.com>
 From: <sender@contoso.com>
 DKIM-Signature: s=s1024; d=contoso.com
 Subject: Here is a message from Bulk Email Provider's infrastructure, but with a DKIM signature authorized by contoso.com
```

In dit voorbeeld, om dit resultaat te bereiken, moet u het volgende doen:

1. De Provider voor bulkmail heeft Contoso een openbare DKIM-sleutel gegeven.

2. Contoso heeft de DKIM-sleutel gepubliceerd naar de bijbehorende DNS-record.

3. Bij het verzenden van e-mail ondertekent de provider voor bulkmail met de bijbehorende persoonlijke sleutel. Hiermee heeft de provider voor bulkmail de DKIM-handtekening toegevoegd aan de berichtkop.

4. Bij de ontvangende e-mailsystemen wordt een DKIM-controle uitgevoerd door de waarde d =\<domain\> van de DKIM-handtekening te verifiëren ten opzichte van het domein in het Van:-adres (5322.From) van het bericht. In dit voorbeeld komen de waarden overeen:

    sender@**contoso.com**

    d=**contoso.com**

## <a name="next-steps-after-you-set-up-dkim-for-office-365"></a>Volgende stappen: nadat u DKIM hebt ingesteld voor Office 365
<a name="DKIMNextSteps"> </a>

Hoewel DKIM is bedoeld om spoofing te voorkomen, werkt DKIM beter met SPF en DMARC. Als u DKIM hebt ingesteld, maar u hebt SPF nog niet ingesteld, moet u dat zeker doen. Zie voor een korte introductie van SPF en om het snel te configureren [SPF in Office 365 instellen om spoofing te voorkomen](set-up-spf-in-office-365-to-help-prevent-spoofing.md). Voor een beter begrip van hoe Office 365 gebruikmaakt van SPF of voor het oplossen van problemen of niet-standaardimplementaties zoals hybride implementaties, begint u met [Hoe Office 365 gebruikmaakt van SPF (Sender Policy Framework) om spoofing te voorkomen](how-office-365-uses-spf-to-prevent-spoofing.md). Zie vervolgens [DMARC gebruiken om e-mail in Office 365 te valideren](use-dmarc-to-validate-email.md). [Antispamberichtkoppen](anti-spam-message-headers.md) bevatten onder meer de syntaxis en koptekstvelden die door Office 365 worden gebruikt voor DKIM-controles.