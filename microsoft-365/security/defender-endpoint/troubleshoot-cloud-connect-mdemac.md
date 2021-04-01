---
title: Problemen met cloudconnectiviteit oplossen voor Microsoft Defender voor Eindpunt voor Mac
description: In dit onderwerp wordt beschreven hoe u problemen met cloudconnectiviteit voor Microsoft Defender voor Eindpunt voor Mac kunt oplossen
keywords: microsoft, defender, atp, mac, installatie, implementeren, verwijderen, intune, jamf, macos, catalina, mojave, high sierra
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-lsaldanha
author: lovina-saldanha
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: e522495fa86b5a71faa9f25cc863c29cc5d124c0
ms.sourcegitcommit: 7b8104015a76e02bc215e1cf08069979c70650ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/31/2021
ms.locfileid: "51476665"
---
# <a name="troubleshoot-cloud-connectivity-issues-for-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="5c87e-104">Problemen met cloudconnectiviteit oplossen voor Microsoft Defender voor Eindpunt voor Mac</span><span class="sxs-lookup"><span data-stu-id="5c87e-104">Troubleshoot cloud connectivity issues for Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5c87e-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="5c87e-105">**Applies to:**</span></span>
- [<span data-ttu-id="5c87e-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="5c87e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5c87e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5c87e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="5c87e-108">**Platform** macOS</span><span class="sxs-lookup"><span data-stu-id="5c87e-108">**Platform** macOS</span></span>

<span data-ttu-id="5c87e-109">In dit onderwerp wordt beschreven hoe u problemen met cloudconnectiviteit voor Microsoft Defender voor Eindpunt voor Mac kunt oplossen.</span><span class="sxs-lookup"><span data-stu-id="5c87e-109">This topic describes how to Troubleshoot cloud connectivity issues for Microsoft Defender for Endpoint for Mac.</span></span>

## <a name="run-the-connectivity-test"></a><span data-ttu-id="5c87e-110">De connectiviteitstest uitvoeren</span><span class="sxs-lookup"><span data-stu-id="5c87e-110">Run the connectivity test</span></span>
<span data-ttu-id="5c87e-111">Als u wilt testen of Defender voor Eindpunt voor Mac met de huidige netwerkinstellingen met de cloud kan communiceren, moet u een connectiviteitstest uitvoeren vanaf de opdrachtregel:</span><span class="sxs-lookup"><span data-stu-id="5c87e-111">To test if Defender for Endpoint for Mac can communicate to the cloud with the current network settings, run a connectivity test from the command line:</span></span>

```Bash
mdatp connectivity test
```

<span data-ttu-id="5c87e-112">verwachte uitvoer:</span><span class="sxs-lookup"><span data-stu-id="5c87e-112">expected output:</span></span>
```Bash
Testing connection with https://cdn.x.cp.wd.microsoft.com/ping ... [OK]
Testing connection with https://eu-cdn.x.cp.wd.microsoft.com/ping ... [OK]
Testing connection with https://wu-cdn.x.cp.wd.microsoft.com/ping ... [OK]
Testing connection with https://x.cp.wd.microsoft.com/api/report ... [OK]
Testing connection with https://winatp-gw-cus.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-eus.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-weu.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-neu.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-ukw.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-uks.microsoft.com/test ... [OK]
Testing connection with https://eu-v20.events.data.microsoft.com/ping ... [OK]
Testing connection with https://us-v20.events.data.microsoft.com/ping ... [OK]
Testing connection with https://uk-v20.events.data.microsoft.com/ping ... [OK]
Testing connection with https://v20.events.data.microsoft.com/ping ... [OK]
```

<span data-ttu-id="5c87e-113">Als de [verbindingstest](microsoft-defender-endpoint-mac.md#network-connections) mislukt, controleert u of het apparaat internetverbinding heeft en of een van de eindpunten die vereist zijn voor het product, wordt geblokkeerd door een proxy of firewall.</span><span class="sxs-lookup"><span data-stu-id="5c87e-113">If the connectivity test fails, check if the device has Internet access and if [any of the endpoints required by the product](microsoft-defender-endpoint-mac.md#network-connections) are blocked by a proxy or firewall.</span></span>

<span data-ttu-id="5c87e-114">Fouten met krulfout 35 of 60 wijzen op afwijzing van certificaatpinning, wat een mogelijk probleem met SSL- of HTTPS-inspectie aangeeft.</span><span class="sxs-lookup"><span data-stu-id="5c87e-114">Failures with curl error 35 or 60 indicate certificate pinning rejection, which indicates a potential issue with SSL or HTTPS inspection.</span></span> <span data-ttu-id="5c87e-115">Zie onderstaande instructies over de configuratie van SSL-inspectie.</span><span class="sxs-lookup"><span data-stu-id="5c87e-115">See instructions below regarding SSL inspection configuration.</span></span>

## <a name="troubleshooting-steps-for-environments-without-proxy-or-with-proxy-autoconfig-pac-or-with-web-proxy-autodiscovery-protocol-wpad"></a><span data-ttu-id="5c87e-116">Stappen voor probleemoplossing voor omgevingen zonder proxy of met Proxy autoconfig (PAC) of met WPAD (Web Proxy AutoDiscovery Protocol)</span><span class="sxs-lookup"><span data-stu-id="5c87e-116">Troubleshooting steps for environments without proxy or with Proxy autoconfig (PAC) or with Web Proxy Autodiscovery Protocol (WPAD)</span></span>
<span data-ttu-id="5c87e-117">Gebruik de volgende procedure om te testen of een verbinding niet is geblokkeerd in een omgeving zonder een proxy of met Proxy autoconfig (PAC) of met WPAD (Web Proxy AutoDiscovery Protocol).</span><span class="sxs-lookup"><span data-stu-id="5c87e-117">Use the following procedure to test that a connection is not blocked in an environment without a proxy or with Proxy autoconfig (PAC) or with Web Proxy Autodiscovery Protocol (WPAD).</span></span>

<span data-ttu-id="5c87e-118">Als een proxy of firewall anoniem verkeer blokkeert, moet u ervoor zorgen dat anoniem verkeer is toegestaan in de eerder genoemde URL's.</span><span class="sxs-lookup"><span data-stu-id="5c87e-118">If a proxy or firewall is blocking anonymous traffic, make sure that anonymous traffic is permitted in the previously listed URLs.</span></span>

> [!WARNING]
> <span data-ttu-id="5c87e-119">Geverifieerde proxies worden niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="5c87e-119">Authenticated proxies are not supported.</span></span> <span data-ttu-id="5c87e-120">Zorg ervoor dat alleen PAC, WPAD of een statische proxy wordt gebruikt.</span><span class="sxs-lookup"><span data-stu-id="5c87e-120">Ensure that only PAC, WPAD, or a static proxy is being used.</span></span> <span data-ttu-id="5c87e-121">SSL-inspectie en het onderscheppen van proxies worden ook niet ondersteund om beveiligingsredenen.</span><span class="sxs-lookup"><span data-stu-id="5c87e-121">SSL inspection and intercepting proxies are also not supported for security reasons.</span></span> <span data-ttu-id="5c87e-122">Configureer een uitzondering voor SSL-inspectie en uw proxyserver om gegevens van Microsoft Defender voor Eindpunt voor Mac rechtstreeks door te geven aan de relevante URL's zonder interceptie.</span><span class="sxs-lookup"><span data-stu-id="5c87e-122">Configure an exception for SSL inspection and your proxy server to directly pass through data from Microsoft Defender for Endpoint for Mac to the relevant URLs without interception.</span></span> <span data-ttu-id="5c87e-123">Als u uw interceptiecertificaat toevoegt aan de algemene winkel, is onderschepping niet toegestaan.</span><span class="sxs-lookup"><span data-stu-id="5c87e-123">Adding your interception certificate to the global store will not allow for interception.</span></span>
<span data-ttu-id="5c87e-124">Om te testen of een verbinding niet is geblokkeerd: In een browser zoals Microsoft Edge voor Mac of Safari openen https://x.cp.wd.microsoft.com/api/report en https://cdn.x.cp.wd.microsoft.com/ping .</span><span class="sxs-lookup"><span data-stu-id="5c87e-124">To test that a connection is not blocked: In a browser such as Microsoft Edge for Mac or Safari open https://x.cp.wd.microsoft.com/api/report and https://cdn.x.cp.wd.microsoft.com/ping.</span></span>

<span data-ttu-id="5c87e-125">Voer desgewenst in Terminal de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="5c87e-125">Optionally, in Terminal, run the following command:</span></span>

```Bash
curl -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping' 
```

<span data-ttu-id="5c87e-126">De uitvoer van deze opdracht moet vergelijkbaar zijn met:</span><span class="sxs-lookup"><span data-stu-id="5c87e-126">The output from this command should be similar to:</span></span>
```bash
OK https://x.cp.wd.microsoft.com/api/report
OK https://cdn.x.cp.wd.microsoft.com/ping
```