---
title: Netwerkbeveiliging inschakelen
description: Schakel netwerkbeveiliging in met Groepsbeleid, PowerShell of Mobile Device Management en Configuration Manager.
keywords: ANetwork-beveiliging, exploits, schadelijke website, ip, domein, domeinen, inschakelen, inschakelen
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: a2bc36f9d3a3e9179f07662da8d97f4c55e72a24
ms.sourcegitcommit: 58d74ff60303a879e35d112f10f79724ba41188f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/10/2021
ms.locfileid: "52302050"
---
# <a name="turn-on-network-protection"></a>Netwerkbeveiliging inschakelen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

[Netwerkbeveiliging](network-protection.md) helpt voorkomen dat werknemers elke toepassing gebruiken om toegang te krijgen tot gevaarlijke domeinen die phishingpraktijken, exploits en andere schadelijke inhoud op internet kunnen hosten. U kunt [netwerkbeveiliging](evaluate-network-protection.md) controleren in een testomgeving om te bekijken welke apps worden geblokkeerd voordat u deze inschakelen.

[Meer informatie over configuratieopties voor netwerkfilters](/mem/intune/protect/endpoint-protection-windows-10#network-filtering)

## <a name="check-if-network-protection-is-enabled"></a>Controleren of netwerkbeveiliging is ingeschakeld

Controleer of netwerkbeveiliging is ingeschakeld op een lokaal apparaat met behulp van registereditor.

1. Selecteer de **knop Start** op de taakbalk en typ **regedit om** registereditor te openen

2. Kies **HKEY_LOCAL_MACHINE** in het zijmenu

3. Navigeren door de geneste menu's naar  >  **SOFTWARE-beleid**  >  **van Microsoft**  >  **Windows Defender**  >  **Policy Manager** 

4. Selecteer **EnableNetworkProtection om** de huidige status van netwerkbeveiliging op het apparaat te bekijken

    * 0 of **Uit**
    * 1 of **Aan**
    * 2 of **auditmodus**
    
    ![netwerkprotectie](https://user-images.githubusercontent.com/3296790/95341270-b738b280-08d3-11eb-84a0-16abb140c9fd.PNG)

## <a name="enable-network-protection"></a>Netwerkbeveiliging inschakelen

Schakel netwerkbeveiliging in met behulp van een van deze methoden:

* [PowerShell](#powershell)
* [Mobile Device Management (MDM)](#mobile-device-management-mdm)
* [Microsoft Endpoint Manager / Intune](#microsoft-endpoint-manager-formerly-intune)
* [Groepsbeleid](#group-policy)

### <a name="powershell"></a>PowerShell

1. Typ **powershell** in het menu Start, klik met de **rechtermuisknop Windows PowerShell** en selecteer Uitvoeren als **beheerder**
2. Voer de volgende cmdlet in:

    ```PowerShell
    Set-MpPreference -EnableNetworkProtection Enabled
    ```

3. Optioneel: Schakel de functie in de auditmodus in met de volgende cmdlet:

    ```PowerShell
    Set-MpPreference -EnableNetworkProtection AuditMode
    ```

    Gebruik `Disabled` deze functie in plaats van of uit te `AuditMode` `Enabled` schakelen.

### <a name="mobile-device-management-mdm"></a>Mobile Device Management (MDM)

Gebruik de CSP -configuratieprovider [(./Vendor/MSFT/Policy/Config/Defender/EnableNetworkProtection)](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-enablenetworkprotection) om netwerkbeveiliging in of uit te schakelen of auditmodus in te schakelen.

### <a name="microsoft-endpoint-manager-formerly-intune"></a>Microsoft Endpoint Manager (voorheen Intune)

1. Meld u aan bij Microsoft Endpoint Manager beheercentrum (https://endpoint.microsoft.com)

2. Een configuratieprofiel voor [eindpuntbeveiliging maken of bewerken](/mem/intune/protect/endpoint-protection-configure)

3. Ga **onder Configuratie Instellingen** in de profielstroom naar **Microsoft Defender Exploit Guard**  >  **Netwerkfiltering** Netwerkbeveiliging  >    >  **inschakelen** of alleen **controleren**

### <a name="group-policy"></a>Groepsbeleid

Gebruik de volgende procedure om netwerkbeveiliging in te stellen op domeincomputers of op een zelfstandige computer.

1. Ga op een zelfstandige computer naar **Start** en typ en selecteer **Groepsbeleid bewerken.**

    *-Of-*

    Open op een domeingevoegde computer [](https://technet.microsoft.com/library/cc731212.aspx)voor groepsbeleidsbeheer de console Groepsbeleidsbeheer, klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en selecteer **Bewerken.**

2. Ga in de **Groepsbeleidsbeheereditor** naar **Computerconfiguratie** en selecteer **Beheersjablonen**.

3. Vouw de boom uit Windows **onderdelen**  >  **Microsoft Defender Antivirus**  >  **Windows Defender Exploit Guard Network**  >  **protection**.

> [!NOTE]
> In oudere versies van Windows kan het groepsbeleidspad 'Windows Defender Antivirus' zeggen in plaats van 'Microsoft Defender Antivirus'.

4. Dubbelklik op de **instelling Voorkomen dat gebruikers** en apps toegang krijgen tot gevaarlijke websites en stel de optie in op **Ingeschakeld.** In de sectie Opties moet u een van de volgende opties opgeven:
    * **Blokkeren:** gebruikers hebben geen toegang tot schadelijke IP-adressen en domeinen
    * **Uitschakelen (standaard)** - De functie Netwerkbeveiliging werkt niet. Gebruikers worden niet geblokkeerd voor toegang tot schadelijke domeinen
    * **Auditmodus:** als een gebruiker een schadelijk IP-adres of domein bezoekt, wordt er een gebeurtenis opgenomen in het Windows gebeurtenislogboek. De gebruiker wordt echter niet geblokkeerd voor het bezoeken van het adres.

> [!IMPORTANT]
> Als u netwerkbeveiliging volledig wilt inschakelen, moet u de optie Groepsbeleid instellen op **Ingeschakeld** en ook Blokkeren **selecteren** in de vervolgkeuzelijst Opties.

Bevestig dat netwerkbeveiliging is ingeschakeld op een lokale computer met behulp van registereditor:

1. Selecteer **Start** en typ **regedit om** registereditor te **openen.**

2. Navigeer naar **HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\Policy Manager\EnableNetworkProtection**

3. Selecteer **EnableNetworkProtection en** bevestig de waarde:
   * 0=Uit
   * 1=Aan
   * 2=Audit

## <a name="see-also"></a>Zie ook

* [Netwerkbeveiliging](network-protection.md)
* [Netwerkbeveiliging evalueren](evaluate-network-protection.md)
* [Problemen met netwerkbeveiliging oplossen](troubleshoot-np.md)
