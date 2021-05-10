---
title: Technische naslaginformatie over versleuteling
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
- Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: 862cbe93-4268-4ef9-ba79-277545ecf221
description: Meer informatie over de verschillende certificaten, technologieën en TLS-coderingssuites (Transport Layer Security) die worden gebruikt voor versleuteling in Office 365 en Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e7e50ea399cd694f512e0538de3f7e67c63ee0e3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52161961"
---
# <a name="technical-reference-details-about-encryption"></a><span data-ttu-id="128fe-103">Technische naslaginformatie over versleuteling</span><span class="sxs-lookup"><span data-stu-id="128fe-103">Technical reference details about encryption</span></span>

<span data-ttu-id="128fe-104">Raadpleeg dit artikel voor meer informatie over certificaten, technologieën en TLS-coderingssuites die worden gebruikt voor [versleuteling in Office 365.](encryption.md)</span><span class="sxs-lookup"><span data-stu-id="128fe-104">Refer to this article to learn about certificates, technologies, and TLS cipher suites used for [encryption in Office 365](encryption.md).</span></span> <span data-ttu-id="128fe-105">In dit artikel vindt u ook informatie over geplande afzettingen.</span><span class="sxs-lookup"><span data-stu-id="128fe-105">This article also provides details about planned deprecations.</span></span>
  
- <span data-ttu-id="128fe-106">Als u op zoek bent naar overzichtsgegevens, zie [Versleuteling in Office 365.](encryption.md)</span><span class="sxs-lookup"><span data-stu-id="128fe-106">If you're looking for overview information, see [Encryption in Office 365](encryption.md).</span></span>
- <span data-ttu-id="128fe-107">Zie Versleuteling instellen in Office 365 Enterprise als u op zoek [bent naar installatiegegevens.](set-up-encryption.md)</span><span class="sxs-lookup"><span data-stu-id="128fe-107">If you're looking for setup information, see [Set up encryption in Office 365 Enterprise](set-up-encryption.md).</span></span>
- <span data-ttu-id="128fe-108">Zie [Cipher Suites in TLS/SSL (Schannel SSP)](/windows/desktop/SecAuthN/cipher-suites-in-schannel)voor informatie over cipher suites die worden ondersteund door specifieke versies van Windows.</span><span class="sxs-lookup"><span data-stu-id="128fe-108">For information about cipher suites supported by specific versions of Windows, see [Cipher Suites in TLS/SSL (Schannel SSP)](/windows/desktop/SecAuthN/cipher-suites-in-schannel).</span></span>

## <a name="microsoft-office-365-certificate-ownership-and-management"></a><span data-ttu-id="128fe-109">Microsoft Office 365 certificaateigenschap en -beheer</span><span class="sxs-lookup"><span data-stu-id="128fe-109">Microsoft Office 365 certificate ownership and management</span></span>

<span data-ttu-id="128fe-110">U hoeft geen certificaten te kopen of te onderhouden voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="128fe-110">You don't need to purchase or maintain certificates for Office 365.</span></span> <span data-ttu-id="128fe-111">In plaats Office 365 eigen certificaten gebruikt.</span><span class="sxs-lookup"><span data-stu-id="128fe-111">Instead, Office 365 uses its own certificates.</span></span>
  
## <a name="current-encryption-standards-and-planned-deprecations"></a><span data-ttu-id="128fe-112">Huidige versleutelingsstandaarden en geplande afzettingen</span><span class="sxs-lookup"><span data-stu-id="128fe-112">Current encryption standards and planned deprecations</span></span>

<span data-ttu-id="128fe-113">Als u de beste versleuteling wilt bieden, Office 365 regelmatig ondersteunde versleutelingsstandaarden.</span><span class="sxs-lookup"><span data-stu-id="128fe-113">To provide best-in-class encryption, Office 365 regularly reviews supported encryption standards.</span></span> <span data-ttu-id="128fe-114">Soms worden oude standaarden afgeschaft als ze verouderd en minder veilig worden.</span><span class="sxs-lookup"><span data-stu-id="128fe-114">Sometimes, old standards are deprecated as they become out of date and less secure.</span></span> <span data-ttu-id="128fe-115">In dit artikel worden momenteel ondersteunde cijfersuites en andere standaarden en details over geplande afzettingen beschreven.</span><span class="sxs-lookup"><span data-stu-id="128fe-115">This article describes currently supported cipher suites and other standards and details about planned deprecations.</span></span>

## <a name="fips-compliance-for-office-365"></a><span data-ttu-id="128fe-116">FIPS-naleving voor Office 365</span><span class="sxs-lookup"><span data-stu-id="128fe-116">FIPS compliance for Office 365</span></span>

<span data-ttu-id="128fe-117">Alle cipher suites die worden ondersteund door Office 365 algoritmen gebruiken die acceptabel zijn onder FIPS 140-2.</span><span class="sxs-lookup"><span data-stu-id="128fe-117">All cipher suites supported by Office 365 use algorithms acceptable under FIPS 140-2.</span></span> <span data-ttu-id="128fe-118">Office 365 neemt FIPS-validaties over van Windows (via Schannel).</span><span class="sxs-lookup"><span data-stu-id="128fe-118">Office 365 inherits FIPS validations from Windows (through Schannel).</span></span> <span data-ttu-id="128fe-119">Zie [Cipher Suites in TLS/SSL (Schannel SSP) voor](/windows/desktop/SecAuthN/cipher-suites-in-schannel)meer informatie over Schannel.</span><span class="sxs-lookup"><span data-stu-id="128fe-119">For information about Schannel, see [Cipher Suites in TLS/SSL (Schannel SSP)](/windows/desktop/SecAuthN/cipher-suites-in-schannel).</span></span>
  
## <a name="versions-of-tls-supported-by-office-365"></a><span data-ttu-id="128fe-120">Versies van TLS die worden ondersteund door Office 365</span><span class="sxs-lookup"><span data-stu-id="128fe-120">Versions of TLS supported by Office 365</span></span>

<span data-ttu-id="128fe-121">TLS en SSL die vóór TLS zijn gebruikt, zijn cryptografische protocollen die communicatie via een netwerk beveiligen met behulp van beveiligingscertificaten om een verbinding tussen computers te versleutelen.</span><span class="sxs-lookup"><span data-stu-id="128fe-121">TLS, and SSL that came before TLS, are cryptographic protocols that secure communication over a network by using security certificates to encrypt a connection between computers.</span></span> <span data-ttu-id="128fe-122">Office 365 ondersteunt TLS versie 1.2 (TLS 1.2).</span><span class="sxs-lookup"><span data-stu-id="128fe-122">Office 365 supports TLS version 1.2 (TLS 1.2).</span></span>

<span data-ttu-id="128fe-123">TLS versie 1.3 (TLS 1.3) wordt momenteel niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="128fe-123">TLS version 1.3 (TLS 1.3) is currently not supported.</span></span>
  
## <a name="support-for-tls-10-and-11-deprecation"></a><span data-ttu-id="128fe-124">Ondersteuning voor de intrekking van TLS 1.0 en 1.1</span><span class="sxs-lookup"><span data-stu-id="128fe-124">Support for TLS 1.0 and 1.1 deprecation</span></span>

<span data-ttu-id="128fe-125">Office 365 ondersteuning van TLS 1.0 en 1.1 is gestopt op 31 oktober 2018.</span><span class="sxs-lookup"><span data-stu-id="128fe-125">Office 365 stopped supporting TLS 1.0 and 1.1 on October 31, 2018.</span></span> <span data-ttu-id="128fe-126">We hebben het uitschakelen van TLS 1.0 en 1.1 voltooid in GCC High- en DoD-omgevingen.</span><span class="sxs-lookup"><span data-stu-id="128fe-126">We have completed disabling TLS 1.0 and 1.1 in GCC High and DoD environments.</span></span> <span data-ttu-id="128fe-127">We zijn begonnen met het uitschakelen van TLS 1.0 en 1.1 voor Worldwide- en GCC-omgevingen vanaf 15 oktober 2020 en gaan de komende weken en maanden verder met de uitrol.</span><span class="sxs-lookup"><span data-stu-id="128fe-127">We began disabling TLS 1.0 and 1.1 for Worldwide and GCC environments beginning on October 15, 2020 and will continue with roll-out over the next weeks and months.</span></span>

<span data-ttu-id="128fe-128">Als u een veilige verbinding wilt Office 365 en Microsoft 365 services, gebruiken alle combinaties van clientservers en browserservers TLS 1.2 en moderne coderingssuites.</span><span class="sxs-lookup"><span data-stu-id="128fe-128">To maintain a secure connection to Office 365 and Microsoft 365 services, all client-server and browser-server combinations use TLS 1.2 and modern cipher suites.</span></span> <span data-ttu-id="128fe-129">Mogelijk moet u bepaalde combinaties van client-server en browserserver bijwerken.</span><span class="sxs-lookup"><span data-stu-id="128fe-129">You might have to update certain client-server and browser-server combinations.</span></span> <span data-ttu-id="128fe-130">Zie Voorbereiden op het verplichte gebruik van [TLS 1.2 in](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)Office 365.</span><span class="sxs-lookup"><span data-stu-id="128fe-130">For information about how this change impacts you, see [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>
  
## <a name="deprecating-support-for-3des"></a><span data-ttu-id="128fe-131">Ondersteuning voor 3DES afgeschaft</span><span class="sxs-lookup"><span data-stu-id="128fe-131">Deprecating support for 3DES</span></span>

<span data-ttu-id="128fe-132">Sinds 31 oktober 2018 ondersteunt Office 365 geen gebruik meer van 3DES-coderingssuites voor communicatie met Office 365.</span><span class="sxs-lookup"><span data-stu-id="128fe-132">Since October 31, 2018, Office 365 no longer supports the use of 3DES cipher suites for communication to Office 365.</span></span> <span data-ttu-id="128fe-133">Meer specifiek ondersteunt Office 365 niet langer de TLS_RSA_WITH_3DES_EDE_CBC_SHA codeersuite.</span><span class="sxs-lookup"><span data-stu-id="128fe-133">More specifically, Office 365 no longer supports the TLS_RSA_WITH_3DES_EDE_CBC_SHA cipher suite.</span></span> <span data-ttu-id="128fe-134">Sinds 28 februari 2019 is deze cijfersuite uitgeschakeld in Office 365.</span><span class="sxs-lookup"><span data-stu-id="128fe-134">Since February 28, 2019, this cipher suite has been disabled in Office 365.</span></span> <span data-ttu-id="128fe-135">Clients en servers die communiceren met Office 365 moeten een of meer van de ondersteunde cijfers ondersteunen.</span><span class="sxs-lookup"><span data-stu-id="128fe-135">Clients and servers that communicate with Office 365 must support one or more of the supported ciphers.</span></span> <span data-ttu-id="128fe-136">Zie [TLS-cijfersuites](#tls-cipher-suites-supported-by-office-365)die worden ondersteund door Office 365 voor een lijst met ondersteunde cijfers.</span><span class="sxs-lookup"><span data-stu-id="128fe-136">For a list of supported ciphers, see [TLS cipher suites supported by Office 365](#tls-cipher-suites-supported-by-office-365).</span></span>
  
## <a name="deprecating-sha-1-certificate-support-in-office-365"></a><span data-ttu-id="128fe-137">Ondersteuning voor SHA-1-certificaten in Office 365</span><span class="sxs-lookup"><span data-stu-id="128fe-137">Deprecating SHA-1 certificate support in Office 365</span></span>

<span data-ttu-id="128fe-138">Sinds juni 2016 Office 365 geen SHA-1-certificaat meer voor uitgaande of binnenkomende verbindingen.</span><span class="sxs-lookup"><span data-stu-id="128fe-138">Since June 2016, Office 365 no longer accepts an SHA-1 certificate for outbound or inbound connections.</span></span> <span data-ttu-id="128fe-139">Gebruik SHA-2 (Secure Hash Algorithm 2) of een sterker hashing-algoritme in de certificaatketen.</span><span class="sxs-lookup"><span data-stu-id="128fe-139">Use SHA-2 (Secure Hash Algorithm 2) or a stronger hashing algorithm in the certificate chain.</span></span>
  
## <a name="tls-cipher-suites-supported-by-office-365"></a><span data-ttu-id="128fe-140">TLS-coderingssuites die worden ondersteund door Office 365</span><span class="sxs-lookup"><span data-stu-id="128fe-140">TLS cipher suites supported by Office 365</span></span>

<span data-ttu-id="128fe-141">TLS gebruikt *coderingssuites*, verzamelingen versleutelingsalgoritmen, om veilige verbindingen tot stand te brengen.</span><span class="sxs-lookup"><span data-stu-id="128fe-141">TLS uses *cipher suites*, collections of encryption algorithms, to establish secure connections.</span></span> <span data-ttu-id="128fe-142">Office 365 ondersteunt de cijfersuites die in de volgende tabel worden vermeld.</span><span class="sxs-lookup"><span data-stu-id="128fe-142">Office 365 supports the cipher suites listed in the following table.</span></span> <span data-ttu-id="128fe-143">De tabel bevat de cijfersuites in volgorde van sterkte, met als eerste de sterkste cijfersuite.</span><span class="sxs-lookup"><span data-stu-id="128fe-143">The table lists the cipher suites in order of strength, with the strongest cipher suite listed first.</span></span>

<span data-ttu-id="128fe-144">Office 365 reageert op een verbindingsaanvraag door eerst verbinding te maken met de veiligste codeersuite.</span><span class="sxs-lookup"><span data-stu-id="128fe-144">Office 365 responds to a connection request by first attempting to connect using the most secure cipher suite.</span></span> <span data-ttu-id="128fe-145">Als de verbinding niet werkt, Office 365 de op een na veiligste coderingssuite in de lijst, en ga zo maar door.</span><span class="sxs-lookup"><span data-stu-id="128fe-145">If the connection doesn't work, Office 365 tries the second most secure cipher suite in the list, and so on.</span></span> <span data-ttu-id="128fe-146">De service blijft in de lijst staan totdat de verbinding wordt geaccepteerd.</span><span class="sxs-lookup"><span data-stu-id="128fe-146">The service continues down the list until the connection is accepted.</span></span> <span data-ttu-id="128fe-147">Wanneer u een verbinding Office 365, kiest de ontvangende service of TLS wordt gebruikt en welke codeersuite moet worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="128fe-147">Likewise, when Office 365 requests a connection, the receiving service chooses whether TLS will be used and which cipher suite to use.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="128fe-148">Let op: TLS-versies worden afgeschaft en dat afgeschafte  versies niet mogen worden gebruikt wanneer nieuwere versies beschikbaar zijn.</span><span class="sxs-lookup"><span data-stu-id="128fe-148">Be aware that TLS versions deprecate, and that deprecated versions *should not be used* where newer versions are available.</span></span> <span data-ttu-id="128fe-149">TLS 1.3 wordt momenteel niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="128fe-149">TLS 1.3 is currently not supported.</span></span> <span data-ttu-id="128fe-150">Als voor uw oudere services geen TLS 1.0 of 1.1 is vereist, moet u deze uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="128fe-150">If your legacy services do not require TLS 1.0 or 1.1 you should disable them.</span></span>

| <span data-ttu-id="128fe-151">Cipher-suite</span><span class="sxs-lookup"><span data-stu-id="128fe-151">Cipher suite</span></span> | <span data-ttu-id="128fe-152">Sleuteluitwisselingsalgoritme/sterkte</span><span class="sxs-lookup"><span data-stu-id="128fe-152">Key exchange algorithm/strength</span></span> | <span data-ttu-id="128fe-153">Geheimhouding doorsturen</span><span class="sxs-lookup"><span data-stu-id="128fe-153">Forward Secrecy</span></span> | <span data-ttu-id="128fe-154">Cijfer/sterkte</span><span class="sxs-lookup"><span data-stu-id="128fe-154">Cipher/strength</span></span> | <span data-ttu-id="128fe-155">Verificatiealgoritme</span><span class="sxs-lookup"><span data-stu-id="128fe-155">Authentication algorithm</span></span> |
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="128fe-156">TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384</span><span class="sxs-lookup"><span data-stu-id="128fe-156">TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384</span></span> <br/>     |<span data-ttu-id="128fe-157">ECDH/192</span><span class="sxs-lookup"><span data-stu-id="128fe-157">ECDH/192</span></span> <br/>|<span data-ttu-id="128fe-158">Ja</span><span class="sxs-lookup"><span data-stu-id="128fe-158">Yes</span></span> <br/>|<span data-ttu-id="128fe-159">AES/256</span><span class="sxs-lookup"><span data-stu-id="128fe-159">AES/256</span></span> <br/>|<span data-ttu-id="128fe-160">RSA/112</span><span class="sxs-lookup"><span data-stu-id="128fe-160">RSA/112</span></span> <br/> |
|<span data-ttu-id="128fe-161">TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256</span><span class="sxs-lookup"><span data-stu-id="128fe-161">TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256</span></span> <br/>     |<span data-ttu-id="128fe-162">ECDH/128</span><span class="sxs-lookup"><span data-stu-id="128fe-162">ECDH/128</span></span> <br/>|<span data-ttu-id="128fe-163">Ja</span><span class="sxs-lookup"><span data-stu-id="128fe-163">Yes</span></span> <br/>|<span data-ttu-id="128fe-164">AES/128</span><span class="sxs-lookup"><span data-stu-id="128fe-164">AES/128</span></span> <br/>|<span data-ttu-id="128fe-165">RSA/112</span><span class="sxs-lookup"><span data-stu-id="128fe-165">RSA/112</span></span> <br/> |
|<span data-ttu-id="128fe-166">TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384</span><span class="sxs-lookup"><span data-stu-id="128fe-166">TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384</span></span> <br/>     |<span data-ttu-id="128fe-167">ECDH/192</span><span class="sxs-lookup"><span data-stu-id="128fe-167">ECDH/192</span></span> <br/>|<span data-ttu-id="128fe-168">Ja</span><span class="sxs-lookup"><span data-stu-id="128fe-168">Yes</span></span> <br/>|<span data-ttu-id="128fe-169">AES/256</span><span class="sxs-lookup"><span data-stu-id="128fe-169">AES/256</span></span> <br/>|<span data-ttu-id="128fe-170">RSA/112</span><span class="sxs-lookup"><span data-stu-id="128fe-170">RSA/112</span></span> <br/> |
|<span data-ttu-id="128fe-171">TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256</span><span class="sxs-lookup"><span data-stu-id="128fe-171">TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256</span></span> <br/>     |<span data-ttu-id="128fe-172">ECDH/128</span><span class="sxs-lookup"><span data-stu-id="128fe-172">ECDH/128</span></span> <br/>|<span data-ttu-id="128fe-173">Ja</span><span class="sxs-lookup"><span data-stu-id="128fe-173">Yes</span></span> <br/>|<span data-ttu-id="128fe-174">AES/128</span><span class="sxs-lookup"><span data-stu-id="128fe-174">AES/128</span></span> <br/>|<span data-ttu-id="128fe-175">RSA/112</span><span class="sxs-lookup"><span data-stu-id="128fe-175">RSA/112</span></span> <br/> |
|<span data-ttu-id="128fe-176">TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA</span><span class="sxs-lookup"><span data-stu-id="128fe-176">TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA</span></span> <br/>        |<span data-ttu-id="128fe-177">ECDH/192</span><span class="sxs-lookup"><span data-stu-id="128fe-177">ECDH/192</span></span> <br/>|<span data-ttu-id="128fe-178">Ja</span><span class="sxs-lookup"><span data-stu-id="128fe-178">Yes</span></span> <br/>|<span data-ttu-id="128fe-179">AES/256</span><span class="sxs-lookup"><span data-stu-id="128fe-179">AES/256</span></span> <br/>|<span data-ttu-id="128fe-180">RSA/112</span><span class="sxs-lookup"><span data-stu-id="128fe-180">RSA/112</span></span> <br/> |
|<span data-ttu-id="128fe-181">TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA</span><span class="sxs-lookup"><span data-stu-id="128fe-181">TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA</span></span> <br/>        |<span data-ttu-id="128fe-182">ECDH/128</span><span class="sxs-lookup"><span data-stu-id="128fe-182">ECDH/128</span></span> <br/>|<span data-ttu-id="128fe-183">Ja</span><span class="sxs-lookup"><span data-stu-id="128fe-183">Yes</span></span> <br/>|<span data-ttu-id="128fe-184">AES/128</span><span class="sxs-lookup"><span data-stu-id="128fe-184">AES/128</span></span> <br/>|<span data-ttu-id="128fe-185">RSA/112</span><span class="sxs-lookup"><span data-stu-id="128fe-185">RSA/112</span></span> <br/> |
|<span data-ttu-id="128fe-186">TLS_RSA_WITH_AES_256_GCM_SHA384</span><span class="sxs-lookup"><span data-stu-id="128fe-186">TLS_RSA_WITH_AES_256_GCM_SHA384</span></span> <br/>           |<span data-ttu-id="128fe-187">RSA/112</span><span class="sxs-lookup"><span data-stu-id="128fe-187">RSA/112</span></span> <br/> |<span data-ttu-id="128fe-188">Nee</span><span class="sxs-lookup"><span data-stu-id="128fe-188">No</span></span> <br/> |<span data-ttu-id="128fe-189">AES/256</span><span class="sxs-lookup"><span data-stu-id="128fe-189">AES/256</span></span> <br/>|<span data-ttu-id="128fe-190">RSA/112</span><span class="sxs-lookup"><span data-stu-id="128fe-190">RSA/112</span></span> <br/> |
|<span data-ttu-id="128fe-191">TLS_RSA_WITH_AES_128_GCM_SHA256</span><span class="sxs-lookup"><span data-stu-id="128fe-191">TLS_RSA_WITH_AES_128_GCM_SHA256</span></span> <br/>           |<span data-ttu-id="128fe-192">RSA/112</span><span class="sxs-lookup"><span data-stu-id="128fe-192">RSA/112</span></span> <br/> |<span data-ttu-id="128fe-193">Nee</span><span class="sxs-lookup"><span data-stu-id="128fe-193">No</span></span> <br/> |<span data-ttu-id="128fe-194">AES/256</span><span class="sxs-lookup"><span data-stu-id="128fe-194">AES/256</span></span> <br/>|<span data-ttu-id="128fe-195">RSA/112</span><span class="sxs-lookup"><span data-stu-id="128fe-195">RSA/112</span></span> <br/> |

<span data-ttu-id="128fe-196">Deze coderingssuites ondersteunden TLS 1.0- en 1.1-protocollen tot de afzettingsdatum.</span><span class="sxs-lookup"><span data-stu-id="128fe-196">These cipher suites supported TLS 1.0 and 1.1 protocols until their deprecation date.</span></span> <span data-ttu-id="128fe-197">Voor GCC High- en DoD-omgevingen was die afzettingsdatum 15 januari 2020 en voor Worldwide en GCC-omgevingen die datum 15 oktober 2020 was.</span><span class="sxs-lookup"><span data-stu-id="128fe-197">For GCC High and DoD environments that deprecation date was January 15, 2020, and for Worldwide and GCC environments that date was October 15, 2020.</span></span>

| <span data-ttu-id="128fe-198">Protocollen</span><span class="sxs-lookup"><span data-stu-id="128fe-198">Protocols</span></span> | <span data-ttu-id="128fe-199">Naam van cipher-suite</span><span class="sxs-lookup"><span data-stu-id="128fe-199">Cipher suite name</span></span> | <span data-ttu-id="128fe-200">Sleuteluitwisselingsalgoritme/Sterkte</span><span class="sxs-lookup"><span data-stu-id="128fe-200">Key exchange algorithm/Strength</span></span> | <span data-ttu-id="128fe-201">Ondersteuning voor doorsturen van geheimhouding</span><span class="sxs-lookup"><span data-stu-id="128fe-201">Forward Secrecy support</span></span> | <span data-ttu-id="128fe-202">Verificatiealgoritme/Sterkte</span><span class="sxs-lookup"><span data-stu-id="128fe-202">Authentication algorithm/Strength</span></span> | <span data-ttu-id="128fe-203">Cijfer/sterkte</span><span class="sxs-lookup"><span data-stu-id="128fe-203">Cipher/Strength</span></span> |
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="128fe-204">TLS 1.0, 1.1, 1.2</span><span class="sxs-lookup"><span data-stu-id="128fe-204">TLS 1.0, 1.1, 1.2</span></span>  <br/> |<span data-ttu-id="128fe-205">TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA</span><span class="sxs-lookup"><span data-stu-id="128fe-205">TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA</span></span>  <br/> |<span data-ttu-id="128fe-206">ECDH/192</span><span class="sxs-lookup"><span data-stu-id="128fe-206">ECDH/192</span></span>  <br/> |<span data-ttu-id="128fe-207">Ja</span><span class="sxs-lookup"><span data-stu-id="128fe-207">Yes</span></span>  <br/> |<span data-ttu-id="128fe-208">RSA/112</span><span class="sxs-lookup"><span data-stu-id="128fe-208">RSA/112</span></span>  <br/> |<span data-ttu-id="128fe-209">AES/256</span><span class="sxs-lookup"><span data-stu-id="128fe-209">AES/256</span></span>  <br/> |
|<span data-ttu-id="128fe-210">TLS 1.0, 1.1, 1.2</span><span class="sxs-lookup"><span data-stu-id="128fe-210">TLS 1.0, 1.1, 1.2</span></span>  <br/> |<span data-ttu-id="128fe-211">TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA</span><span class="sxs-lookup"><span data-stu-id="128fe-211">TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA</span></span>  <br/> |<span data-ttu-id="128fe-212">ECDH/128</span><span class="sxs-lookup"><span data-stu-id="128fe-212">ECDH/128</span></span>  <br/> |<span data-ttu-id="128fe-213">Ja</span><span class="sxs-lookup"><span data-stu-id="128fe-213">Yes</span></span>  <br/> |<span data-ttu-id="128fe-214">RSA/112</span><span class="sxs-lookup"><span data-stu-id="128fe-214">RSA/112</span></span>  <br/> |<span data-ttu-id="128fe-215">AES/128</span><span class="sxs-lookup"><span data-stu-id="128fe-215">AES/128</span></span>  <br/> |
|<span data-ttu-id="128fe-216">TLS 1.0, 1.1, 1.2</span><span class="sxs-lookup"><span data-stu-id="128fe-216">TLS 1.0, 1.1, 1.2</span></span>  <br/> |<span data-ttu-id="128fe-217">TLS_RSA_WITH_AES_256_CBC_SHA</span><span class="sxs-lookup"><span data-stu-id="128fe-217">TLS_RSA_WITH_AES_256_CBC_SHA</span></span>        <br/> |<span data-ttu-id="128fe-218">RSA/112</span><span class="sxs-lookup"><span data-stu-id="128fe-218">RSA/112</span></span>  <br/>  |<span data-ttu-id="128fe-219">Nee</span><span class="sxs-lookup"><span data-stu-id="128fe-219">No</span></span>  <br/>  |<span data-ttu-id="128fe-220">RSA/112</span><span class="sxs-lookup"><span data-stu-id="128fe-220">RSA/112</span></span>  <br/> |<span data-ttu-id="128fe-221">AES/256</span><span class="sxs-lookup"><span data-stu-id="128fe-221">AES/256</span></span>  <br/> |
|<span data-ttu-id="128fe-222">TLS 1.0, 1.1, 1.2</span><span class="sxs-lookup"><span data-stu-id="128fe-222">TLS 1.0, 1.1, 1.2</span></span>  <br/> |<span data-ttu-id="128fe-223">TLS_RSA_WITH_AES_128_CBC_SHA</span><span class="sxs-lookup"><span data-stu-id="128fe-223">TLS_RSA_WITH_AES_128_CBC_SHA</span></span>        <br/> |<span data-ttu-id="128fe-224">RSA/112</span><span class="sxs-lookup"><span data-stu-id="128fe-224">RSA/112</span></span>  <br/>  |<span data-ttu-id="128fe-225">Nee</span><span class="sxs-lookup"><span data-stu-id="128fe-225">No</span></span>  <br/>  |<span data-ttu-id="128fe-226">RSA/112</span><span class="sxs-lookup"><span data-stu-id="128fe-226">RSA/112</span></span>  <br/> |<span data-ttu-id="128fe-227">AES/128</span><span class="sxs-lookup"><span data-stu-id="128fe-227">AES/128</span></span>  <br/> |
|<span data-ttu-id="128fe-228">TLS 1.0, 1.1, 1.2</span><span class="sxs-lookup"><span data-stu-id="128fe-228">TLS 1.0, 1.1, 1.2</span></span>  <br/> |<span data-ttu-id="128fe-229">TLS_RSA_WITH_AES_256_CBC_SHA256</span><span class="sxs-lookup"><span data-stu-id="128fe-229">TLS_RSA_WITH_AES_256_CBC_SHA256</span></span>     <br/> |<span data-ttu-id="128fe-230">RSA/112</span><span class="sxs-lookup"><span data-stu-id="128fe-230">RSA/112</span></span>  <br/>  |<span data-ttu-id="128fe-231">Nee</span><span class="sxs-lookup"><span data-stu-id="128fe-231">No</span></span>   <br/> |<span data-ttu-id="128fe-232">RSA/112</span><span class="sxs-lookup"><span data-stu-id="128fe-232">RSA/112</span></span>  <br/> |<span data-ttu-id="128fe-233">AES/256</span><span class="sxs-lookup"><span data-stu-id="128fe-233">AES/256</span></span>  <br/> |
|<span data-ttu-id="128fe-234">TLS 1.0, 1.1, 1.2</span><span class="sxs-lookup"><span data-stu-id="128fe-234">TLS 1.0, 1.1, 1.2</span></span>  <br/> |<span data-ttu-id="128fe-235">TLS_RSA_WITH_AES_128_CBC_SHA256</span><span class="sxs-lookup"><span data-stu-id="128fe-235">TLS_RSA_WITH_AES_128_CBC_SHA256</span></span>     <br/> |<span data-ttu-id="128fe-236">RSA/112</span><span class="sxs-lookup"><span data-stu-id="128fe-236">RSA/112</span></span>  <br/>  |<span data-ttu-id="128fe-237">Nee</span><span class="sxs-lookup"><span data-stu-id="128fe-237">No</span></span>   <br/> |<span data-ttu-id="128fe-238">RSA/112</span><span class="sxs-lookup"><span data-stu-id="128fe-238">RSA/112</span></span>  <br/> |<span data-ttu-id="128fe-239">AES/256</span><span class="sxs-lookup"><span data-stu-id="128fe-239">AES/256</span></span>  <br/> |

## <a name="related-articles"></a><span data-ttu-id="128fe-240">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="128fe-240">Related articles</span></span>

[<span data-ttu-id="128fe-241">TLS Cipher Suites in Windows 10 v1903</span><span class="sxs-lookup"><span data-stu-id="128fe-241">TLS Cipher Suites in Windows 10 v1903</span></span>](/windows/win32/secauthn/tls-cipher-suites-in-windows-10-v1903)

[<span data-ttu-id="128fe-242">Versleuteling in Office 365</span><span class="sxs-lookup"><span data-stu-id="128fe-242">Encryption in Office 365</span></span>](encryption.md)
  
[<span data-ttu-id="128fe-243">Versleuteling instellen in Office 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="128fe-243">Set up encryption in Office 365 Enterprise</span></span>](set-up-encryption.md)
  
[<span data-ttu-id="128fe-244">Schannel-implementatie van TLS 1.0 in Windows beveiligingsstatusupdate: 24 november 2015</span><span class="sxs-lookup"><span data-stu-id="128fe-244">Schannel implementation of TLS 1.0 in Windows security status update: November 24, 2015</span></span>](https://support.microsoft.com/kb/3117336)
  
<span data-ttu-id="128fe-245">[TLS/SSL Cryptographic Enhancements (Windows IT Center)](/previous-versions/windows/it-pro/windows-vista/cc766285(v=ws.10))</span><span class="sxs-lookup"><span data-stu-id="128fe-245">[TLS/SSL Cryptographic Enhancements (Windows IT Center)](/previous-versions/windows/it-pro/windows-vista/cc766285(v=ws.10))</span></span>
  
[<span data-ttu-id="128fe-246">Voorbereiden op TLS 1.2 in Office 365 en Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="128fe-246">Preparing for TLS 1.2 in Office 365 and Office 365 GCC</span></span>](/office365/troubleshoot/security/prepare-tls-1.2-in-office-365)