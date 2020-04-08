---
title: Opnieuw instellen van het wachtwoord voor uw Microsoft 365-testomgeving
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/13/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: 'Samenvatting: configureer en test het opnieuw instellen van het wachtwoord voor uw Microsoft 365-testomgeving.'
ms.openlocfilehash: c8d5ed0c7feac98afd3230a305f4ab1f850ca7f8
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/13/2020
ms.locfileid: "42805679"
---
# <a name="password-reset-for-your-microsoft-365-test-environment"></a>Opnieuw instellen van het wachtwoord voor uw Microsoft 365-testomgeving

*Deze testlabrichtlijn kan alleen worden gebruikt voor Microsoft 365 Enterprise-testomgevingen.*

Met de Azure Active Directory (Azure AD) selfservice voor het opnieuw instellen van wachtwoorden (SSPR) kunnen gebruikers hun wachtwoorden of accounts opnieuw instellen of ontgrendelen. 

In dit artikel wordt beschreven hoe u wachtwoordinstellingen in uw Microsoft 365-testomgeving in drie fasen kunt configureren en testen:

1.  Maak de Microsoft 365 Enterprise-testomgeving.
2.  Wachtwoord terugschrijven inschakelen.
3.  Configureer en test het opnieuw instellen van het wachtwoord voor het gebruikersaccount 3.
    
![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Klik [hier](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) voor een visuele kaart met alle artikelen over de Microsoft 365 Enterprise-testlabrichtlijnen.

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Fase 1: configureer wachtwoord-hash-synchronisatie voor uw Microsoft 365-testomgeving

Volg eerst de instructies in [wachtwoord-hash-synchronisatie](password-hash-sync-m365-ent-test-environment.md). Dit is de resulterende configuratie.
  
![De gesimuleerde onderneming in een testomgeving met wachtwoord-hash-synchronisatie](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
Deze configuratie bestaat uit: 
  
- Een betaald of proefabonnement op Microsoft 365 E5 of Office 365 E5.
- Een vereenvoudigde organisatie die via intranet is verbonden met internet, bestaande uit de virtuele machines DC1, APP1 en CLIENT1 op een subnet van een virtueel Azure-netwerk. 
- Azure AD Connect wordt uitgevoerd op APP1 om het AD DS-domein TESTLAB periodiek te synchroniseren met de Azure AD-tenant van uw Microsoft 365- of Office 365-abonnement.

## <a name="phase-2-enable-password-writeback"></a>Fase 2: wachtwoord terugschrijven inschakelen.

Volg de instructies in [Fase 2 van testlabrichtlijn Wachtwoord terugschrijven](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).

Voor het gebruik van wachtwoordherstel moet u een wachtwoord voor terugschrijven inschakelen.
  
## <a name="phase-3-configure-and-test-password-reset"></a>Fase 3: opnieuw instellen van wachtwoorden configureren en testen

In deze fase configureert u het opnieuw instellen van wachtwoorden in de Azure AD-Tenant via groepslidmaatschap. Controleer vervolgens of dit werkt.

Schakel eerst het opnieuw instellen van het wachtwoord in voor de accounts in een specifieke groep van Azure AD.

1. Open [https://portal.azure.com](https://portal.azure.com)in een privévenster van uw browser en meld u aan met de referenties van uw globale beheerdersaccount.
2. Klik in de Azure-portal op **Azure Active Directory > Nieuwe groep**.
3. Stel het **groepstype** in op **beveiliging**, **groepsnaam** op **PWReset** en het **lidmaatschapstype** op **toegewezen**. 
4. Klik op **leden**, zoek en selecteer **gebruiker 3**, klik op **selecteren**en klik vervolgens op **maken**.
5. Sluit het **deelvenster** groepen.
6. Klik in het deelvenster Azure Active Directory op **opnieuw instellen van wachtwoorden** in de linkernavigatiebalk.
7. Kies in het deelvenster **wachtwoordherstel-eigenschappen** onder de optie **selfservice wachtwoord opnieuw instellen ingeschakeld****geselecteerd**.
8. Klik op **groep selecteren**, selecteer de groep **PWReset** en klik vervolgens op **selecteren > opslaan**.
9. Sluit het privévenster in uw browser.

Configureer en test vervolgens het opnieuw instellen van het wachtwoord voor het gebruikersaccount 3.

1. Open een nieuwe privévenster in uw browser en blader naar [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).
2. Meld u aan met de referenties van het account gebruikers 3.
3. Klik in **meer informatie vereist**op **volgende**. 
5. Stel bij **Verlies geen toegang tot uw account**, uw mobiele telefoonnummer in als verificatienummer en uw werk- of persoonlijke e-mailaccount als verificatie-e-mailadres.
7. Nadat beide zijn geverifieerd, klikt u op **Ziet er goed uit** en sluit u de privévenster van de browser.
8. Open een nieuw privévenster en blader naar [https://aka.ms/sspr](https://aka.ms/sspr).
9. Typ de accountnaam van gebruiker 3, typ de tekens uit de CAPTCHA en klik vervolgens op **volgende**.
10. Klik voor **verificatiestap 1** op **Naar mijn alternatieve e-mail e-mailen** en klik vervolgens **op E-mail**. Wanneer u het e-mailbericht ontvangt, typt u de verificatiecode en klikt u op **volgende**.
11. Typ in **Ga terug naar uw account** een nieuw wachtwoord voor het account van Gebruiker 3 en klik vervolgens op **voltooien**. Noteer het gewijzigde wachtwoord van het account van gebruiker 3 en bewaar het op een veilige locatie.
12. Ga op een afzonderlijk tabblad van dezelfde browser naar [https://portal.office.com](https://portal.office.com), en meld u vervolgens aan met de naam van het account voor gebruikers 3 en het nieuwe wachtwoord. U zou de pagina van **Microsoft Office voor Thuisgebruik** moeten zien.

Zie de stap [Vereenvoudig het opnieuw instellen van wachtwoorden](identity-secure-your-passwords.md#identity-pw-reset) in de Identiteitsfase voor informatie en koppelingen om het opnieuw instellen van wachtwoorden in productie te configureren.

## <a name="next-step"></a>Volgende stap

Verken aanvullende [identiteits](m365-enterprise-test-lab-guides.md#identity)functies en -mogelijkheden in uw testomgeving.

## <a name="see-also"></a>Zie ook

[Microsoft 365 Enterprise-testlabrichtlijnen](m365-enterprise-test-lab-guides.md)

[Microsoft 365 Enterprise implementeren](deploy-microsoft-365-enterprise.md)

[Microsoft 365 Enterprise-documentatie](https://docs.microsoft.com/microsoft-365-enterprise/)