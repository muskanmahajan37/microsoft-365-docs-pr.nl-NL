---
title: Een QR-code gebruiken om u aan te melden bij de Outlook mobiele apps
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
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
description: Meer informatie over het gebruik van een QR-code om uw mobiele Outlook te verifiëren en te downloaden.
ms.openlocfilehash: 2c1853a6ea1dd1a5d2ad30b975d1dbd23b942040
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635996"
---
# <a name="use-a-qr-code-to-sign-in-to-the-outlook-mobile-apps"></a>Een QR-code gebruiken om u aan te melden bij de Outlook mobiele apps

> [!IMPORTANT]
> Deze functie is alleen beschikbaar voor organisaties die Targeted Release hebben ingeschakeld in het Microsoft 365 beheercentrum. Zie De opties Standaard of Targeted release instellen voor meer informatie over hoe deze [werkt.](release-options-in-office-365.md) We breiden de komende weken uit naar meer organisaties via een openbare preview. Openbare preview biedt vroegtijdige toegang tot Microsoft 365 functies.

Als Microsoft 365-beheerder kunt u uw gebruikers inschakelen om zich aan te melden bij Outlook voor Android- of iOS-app op hun mobiele apparaten zonder hun gebruikersnaam en wachtwoord in te voeren. Door een QR-code te scannen, kunnen gebruikers zich veilig verifiëren en zich aanmelden bij Outlook mobiel.

In Outlook op het web of andere bureaubladtoepassingen Outlook kunnen gebruikers meldingen zien waarin wordt hen ervan op de hoogte worden gemaakt dat ze Outlook kunnen gebruiken op hun mobiele apparaat. Deze meldingen kunnen worden beheerd door de beheerder met Exchange PowerShell. Als gebruikers ervoor kiezen om zichzelf een Sms te sturen om de app te downloaden op hun mobiele apparaat, wordt er een QR-code weergegeven op hun computer. Ze kunnen de QR-code scannen om zich aan te melden Outlook hun telefoon of tablet. Deze QR-code is een teken van korte duur dat slechts één keer kan worden ingewisseld.

> [!NOTE]
> In sommige gevallen moeten uw gebruikers zich opnieuw verifiëren op hun computer om de QR-code te genereren.

## <a name="use-exchange-powershell"></a>PowerShell Exchange gebruiken

Deze functie is standaard ingeschakeld. Als u deze functie wilt uitschakelen, volgt u de onderstaande stappen.

1. [Verbinding maken powershell Exchange gebruiken.](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps)
2. Met PowerShell kunt u de meldingen uitschakelen die uw gebruikers informeren over de Outlook mobiele apps. Hierdoor wordt ook voorkomen dat de aanmeldingsstroom voor QR-code wordt weergegeven.

```powershell
Set-OrganizationConfig -MobileAppEducationEnabled <Boolean>
```

## <a name="related-content"></a>Verwante onderwerpen

[De opties Standaard of Targeted Release](release-options-in-office-365.md) (artikel)\ instellen
[Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig?view=exchange-ps) (artikel)