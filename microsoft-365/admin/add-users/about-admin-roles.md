---
title: Informatie over beheerdersrollen in het Microsoft 365-beheercentrum
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: da585eea-f576-4f55-a1e0-87090b6aaa9d
description: Beheerdersrollen zoals de Servicebeheerder worden toegewezen aan bedrijfsfuncties en geven machtigingen om specifieke taken uit te voeren in het beheercentrum.
ms.openlocfilehash: 3163b7a4037a923122d2da170ac5ea9e8c2d0185
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/24/2021
ms.locfileid: "52634194"
---
# <a name="about-admin-roles"></a>Informatie over beheerdersrollen

Het Microsoft 365- of Office 365-abonnement wordt geleverd met een set beheerdersrollen die u kunt toewijzen aan gebruikers in uw organisatie met behulp van het Microsoft 365-beheercentrum. Elke beheerdersrol wordt toegewezen aan algemene bedrijfsfuncties en machtigt personen in uw organisatie om specifieke taken in de beheercentra uit te voeren.

In het Microsoft 365-beheercentrum kunt u Azure AD- en Microsoft Intune-rollen beheren. Deze rollen vormen echter een subset van de rollen die beschikbaar zijn in de Azure-Portal en het Intune-beheercentrum.

## <a name="before-you-begin"></a>Voordat u begint

Zoekt u een volledige lijst met uitgebreide beschrijvingen van Azure AD-rollen die u kunt beheren in het Microsoft 365-Beheercentrum? Bekijk de machtigingen voor de beheerdersrol in Azure Active Directory. [Machtigingen voor de beheerdersrol in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles).

Zoekt u een volledige lijst met uitgebreide beschrijvingen van Intune-rollen die u kunt beheren in het Microsoft 365-Beheercentrum?  Bekijk [op rollen gebaseerd toegangsbeheer (RBAC) met Microsoft Intune](/mem/intune/fundamentals/role-based-access-control).

Zie [beheerdersrollen toewijzen](assign-admin-roles.md)voor meer informatie over het toewijzen van rollen in het Microsoft 365-beheercentrum.

## <a name="watch-what-is-an-admin"></a>Bekijk: Wat is een beheerder?

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1SRc0]

## <a name="security-guidelines-for-assigning-roles"></a>Beveiligingsrichtlijnen voor het toewijzen van rollen

Omdat beheerders toegang hebben tot gevoelige gegevens en bestanden, raden we u aan deze richtlijnen te volgen om de gegevens van uw organisatie veiliger te houden.

| Aanbeveling                  | Waarom is dit belangrijk?                 |
| :------------------- | :------------------- |
| Zet twee tot vier globale beheerders in  | Omdat alleen een andere globale beheerder het wachtwoord van een globale beheerder opnieuw kan instellen, raden wij u aan om ten minste twee globale beheerders in uw organisatie te hebben in geval van accountvergrendeling. Maar de globale beheerder heeft bijna onbeperkte toegang tot de instellingen van uw organisatie en de meeste gegevens. Wij raden u dan ook aan niet meer dan vier globale beheerders te hebben, omdat dit een beveiligingsrisico vormt. |
| De *minste strikte* functie toewijzen    | Het toewijzen van de *minste strikte* rol betekent dat beheerders alleen de toegang krijgen die ze nodig hebben om de taak uit te voeren. Als u bijvoorbeeld wilt dat iemand de wachtwoorden van werknemers opnieuw instelt, moet u geen onbeperkte globale beheerdersrol toewijzen, maar een beperkte beheerdersrol zoals Wachtwoordbeheerder of Helpdesk-beheerder. Dit helpt uw gegevens veilig te houden.                 |
| Meervoudige verificatie (MFA) voor beheerders vereisen                  |    Het is een goed idee om MFA te vereisen voor al uw gebruikers, maar beheerders moeten beslist verplicht worden om MFA te gebruiken om in te loggen. Met MFA doorlopen gebruikers een tweede identificatiemethode, om te verifiëren dat ze zijn wie ze zeggen dat ze zijn. Beheerders kunnen toegang hebben tot veel klant- en werknemersgegevens en als u MFA vereist, is het wachtwoord nutteloos zonder de tweede vorm van identificatie, zelfs als het wachtwoord van de beheerder wordt gecompromitteerd.  <br><br>Wanneer u MFA inschakelt, moet de gebruiker de volgende keer dat deze zich aanmeldt een alternatief e-mailadres en telefoonnummer opgeven voor accountherstel.  <br> [Meervoudige verificatie instellen](../security-and-compliance/set-up-multi-factor-authentication.md)          |

Als er een bericht wordt weergegeven in het Beheercentrum waarin wordt aangegeven dat u geen machtigingen hebt om een instelling of pagina te bewerken, komt dit omdat u een rol hebt toegewezen gekregen die deze machtiging niet omvat.

## <a name="commonly-used-microsoft-365-admin-center-roles"></a>Veelgebruikte rollen in het Microsoft 365-Beheercentrum

In het Microsoft 365-beheercentrum kunt u naar **Rollen** gaan en vervolgens een rol selecteren om het detailvenster te openen. Selecteer het tabblad **Machtigingen** om de gedetailleerde takenlijst weer te geven met wat de beheerders die aan die rol zijn toegewezen kunnen doen. Selecteer het tabblad **toegewezen** of **toegewezen beheerders** om gebruikers toe te voegen aan rollen.

Waarschijnlijk hoeft u alleen de volgende rollen in uw organisatie toe te wijzen. Standaard tonen we eerst de rollen die de meeste organisaties gebruiken. Als u een rol niet kunt vinden, gaat u naar het einde van de lijst en selecteert u **Alles weergeven per categorie**. (Zie [machtigingen voor beheerdersrol in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)voor meer informatie, waaronder de cmdlets die zijn gekoppeld aan een rol.)

|Beheerdersrol     |Aan wie moet deze rol worden toegewezen?  |
|---------|---------|
|Factureringsbeheerder     |   Wijs de beheerdersrol Facturering toe aan gebruikers die aankopen doen, abonnementen en serviceaanvragen beheren en de servicestatus controleren. <br><br> Factureringsbeheerders kunnen ook:<br> - Alle aspecten van facturering beheren <br> - Ondersteuningstickets maken en beheren in de Azure-portal <br>  |
|Exchange-beheerder     |   Wijs de Exchange-beheerdersrol toe aan gebruikers die de e-mailpostvakken, Microsoft 365-groepen en Exchange Online van uw gebruikers moeten kunnen bekijken en beheren. <br><br> Exchange-beheerders kunnen ook het volgende doen:<br> - Verwijderde items herstellen in het postvak van een gebruiker <br> Gedelegeerden instellen voor 'Verzenden als' en 'Verzenden namens'. <br>  |
|Algemene beheerder     |   Wijs de Globale beheerdersrol toe aan gebruikers die wereldwijde toegang nodig hebben tot de meeste beheerfuncties en -gegevens via Microsoft online services. <br><br> Te veel gebruikers globale toegang geven is een beveiligingsrisico, we raden u dan ook aan om 2 tot 4 globale beheerders te hebben. <br><br> Alleen globale beheerders kunnen het volgende doen:<br> - Wachtwoorden voor alle gebruikers opnieuw instellen <br> - Domeinen toevoegen en beheren <br> <br> **Opmerking:** de persoon die zich heeft geregistreerd voor Microsoft Online Services, wordt automatisch een globale beheerder. |
|Algemene lezer    |   Wijs de rol van globale lezer toe aan gebruikers die beheerdersfuncties en -instellingen moeten bekijken in beheercentra die de globale beheerder kan zien. De globale beheerder kan deze instellingen niet bewerken.   |
|Groepsbeheerder     |   Wijs de groepsbeheerdersrol toe aan gebruikers die alle groepsinstellingen in alle beheercentra moeten beheren, inclusief het Microsoft 365-Beheercentrum en de Azure Active Directory-Portal. <br><br> Groepsbeheerders kunnen het volgende doen:<br> - Microsoft 365-groepen maken, bewerken, verwijderen en herstellen <br> - Beleid voor het maken, verlopen en benoemen van groepen maken en bijwerken <br> - Azure Active Directory-beveiligingsgroepen maken, bewerken, verwijderen en herstellen| 
|Helpdesk-beheerder     |   Wijs de beheerdersrol Helpdesk toe aan gebruikers die de volgende taken moeten uitvoeren:<br> - Wachtwoorden opnieuw instellen <br> - Gebruikers dwingen zich af te melden <br> - Serviceaanvragen beheren <br> - De servicestatus bewaken <br> <br> **Opmerking**: de Helpdesk-beheerder kan alleen niet-beheerders helpen en gebruikers die deze rollen hebben toegewezen: Directory-lezer, Gast-invite, Helpdesk-beheerder, Berichtencentrum-lezer en Rapportlezer.      |
|Licentiebeheerder    |   Wijs de beheerdersrol Licenties toe aan gebruikers die licenties van gebruikers moeten toewijzen en verwijderen en hun gebruikslocatie moeten bewerken. <br/><br/> Licentiebeheerders kunnen ook: <br> - Licentietoewijzingen voor groepslicenties opnieuw verwerken <br> - Productlicenties toewijzen aan groepen voor groepslicenties  |
|Office-apps beheerder    |   Wijs de beheerdersrol Office Apps toe aan gebruikers die de volgende taken moeten uitvoeren: <br> - Gebruik de Office-cloudbeleidservice om cloudgebaseerd beleid voor Office te maken en te beheren <br> - Serviceaanvragen maken en beheren <br> - Inhoud over nieuwe functies beheren die gebruikers in hun Office-apps zien   <br> - De servicestatus bewaken  |
|Wachtwoordbeheerder  |   Wijs de beheerdersrol Wachtwoorden toe aan een gebruiker die wachtwoorden voor niet-beheerders en wachtwoordbeheerders opnieuw moet instellen.   |
|Service support-beheerder   |   Wijs de beheerdersrol Serviceondersteuning als een extra rol toe aan beheerders of gebruikers van die het volgende moeten doen als aanvulling op hun normale beheerdersrol: <br> - Serviceaanvragen openen en beheren <br> - Berichten in het berichtencentrum bekijken en delen <br> - De servicestatus bewaken   |
|SharePoint-beheerder    |   Wijs de SharePoint-beheerdersrol toe aan gebruikers die het SharePoint Online-beheercentrum moeten openen en beheren. <br><br>SharePoint-beheerders kunnen ook het volgende doen: <br> - Sites maken en verwijderen <br> - Siteverzamelingen en wereldwijde SharePoint-instellingen beheren   |
|Teams-servicebeheerder    |   Wijs de rol Teams-servicebeheerder toe aan gebruikers die het Teams-beheercentrum moeten openen en beheren. <br><br>Teams-servicebeheerders kunnen ook: <br> - Vergaderingen beheren <br> - Vergaderbruggen beheren <br> - Alle organisatiebrede instellingen beheren, inclusief federatie, Teams-upgrade en Teams-clientinstellingen   |
|Gebruikersbeheerder     |    Wijs de beheerdersrol Gebruikers toe aan gebruikers die de voor alle gebruikers de volgende taken moeten uitvoeren: <br> - Gebruikers en groepen toevoegen <br> - Licenties toewijzen <br> - De meeste gebruikerseigenschappen beheren <br> - Gebruikersweergaven maken en beheren <br> - Verloopbeleid voor wachtwoorden bijwerken <br> - Serviceaanvragen beheren <br> - De servicestatus bewaken <br><br>  De gebruikersbeheerder kan ook de volgende acties uitvoeren voor gebruikers die geen beheerders zijn en voor gebruikers die de volgende rollen hebben gekregen: adreslijst lezer, gast invite, helpdesk-beheerder, Message Center Reader, rapportlezer: <br> - Gebruikersnamen beheren<br> - Gebruikers verwijderen en herstellen<br> - Wachtwoorden opnieuw instellen <br> - Gebruikers dwingen zich af te melden <br> - Apparaatsleutels bijwerken (FIDO)   |

## <a name="delegated-administration-for-microsoft-partners"></a>Gedelegeerd beheer voor Microsoft-partners

Als u met een Microsoft-partner werkt, kunt u aan uw partner beheerdersrollen toewijzen. Deze kan op zijn beurt gebruikers in uw bedrijf, of zijn bedrijf, beheerdersrollen toewijzen. Soms wilt u dat uw partner dit doet, bijvoorbeeld als deze uw online organisatie voor u instelt en beheert.
  
Een partner kan deze rollen toewijzen: 
  
- **Admin Agent** Bevoegdheden vergelijkbaar met die van een globale beheerder, met uitzondering van het beheren van meervoudige verificatie via het Partnercentrum.

- **Helpdesk Agent** Bevoegdheden vergelijkbaar met die van een helpdesk-beheerder.

Voordat de partner deze rollen aan gebruikers kan toewijzen, moet u de partner als gedelegeerde beheerder aan uw account toevoegen. Dit proces wordt geïnitieerd door een geautoriseerde partner. De partner stuurt u een e-mailbericht waarin u wordt gevraagd of u de partner toestemming wilt geven om te fungeren als gedelegeerde beheerder. Zie [Partnerrelaties autoriseren of verwijderen](../misc/add-partner.md)voor instructies.
  
## <a name="related-content"></a>Verwante inhoud

[Beheerdersrollen toewijzen](assign-admin-roles.md) (artikel)\
[Informatie over Azure AD-rollen in het Microsoft 365-beheercentrum](azure-ad-roles-in-the-mac.md) (artikel)\
[Exchange Online-beheerdersrol](about-exchange-online-admin-role.md) (artikel)\ [Activiteitenoverzichten in het Microsoft 365-beheercentrum](../activity-reports/activity-reports.md) (artikel)
