---
title: Adreslijstsynchronisatie voor Microsoft 365 uitschakelen
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED150
ms.assetid: ee5f861e-bd48-4267-83d1-a4ead4b4a00d
description: In dit artikel vindt u informatie over het gebruik van PowerShell om adreslijstsynchronisatie voor Microsoft 365 uit te schakelen.
ms.openlocfilehash: 26f8729078ea06657ced565db780b57c7e537aa4
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445706"
---
# <a name="turn-off-directory-synchronization-for-microsoft-365"></a>Adreslijstsynchronisatie voor Microsoft 365 uitschakelen
U kunt PowerShell gebruiken om adreslijstsynchronisatie uit te schakelen en uw gesynchroniseerde gebruikers te converteren naar alleen-cloud. Het wordt echter afgeraden om adreslijstsynchronisatie uit te schakelen als een stap voor het oplossen van problemen. Zie het artikel Problemen oplossen met adreslijstsynchronisatie voor [Microsoft 365](fix-problems-with-directory-synchronization.md) als u hulp nodig hebt bij het oplossen van adreslijstsynchronisatie. 
  
[Neem indien nodig contact](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) op met de ondersteuning voor zakelijke producten.
  
## <a name="turn-off-directory-synchronization"></a>Adreslijstsynchronisatie uitschakelen  
Adreslijstsynchronisatie uitschakelen:
  
1. Installeer eerst de vereiste software en maak verbinding met uw Microsoft 365-abonnement. Zie Verbinding maken [met de Microsoft Azure Active Directory-module voor Windows PowerShell voor instructies.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)
    
2. [Set-MsolDirSyncEnabled gebruiken om](/previous-versions/azure/dn194097(v=azure.100)) adreslijstsynchronisatie uit te schakelen: 
    
  ```powershell
  Set-MsolDirSyncEnabled -EnableDirSync $false
  ```

>[!Note]
>Als u deze opdracht gebruikt, moet u 72 uur wachten voordat u adreslijstsynchronisatie weer kunt in- en uit- zetten.
>
