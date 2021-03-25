---
title: Migreren van Symantec naar Microsoft Defender voor Eindpunt
description: Een overzicht van hoe u overschakelt van Symantec naar Microsoft Defender voor Eindpunt
keywords: migratie, windows defender advanced threat protection, atp, edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-symantecmigrate
- m365solution-overview
ms.topic: article
ms.date: 03/03/2021
ms.custom: migrationguides
ms.reviewer: depicker, yongrhee, chriggs
ms.openlocfilehash: 6517359c805bb449d075e401283a79a791461630
ms.sourcegitcommit: 8685b0f7d53c99577fa65144ab60295dfa60f46f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51218784"
---
# <a name="migrate-from-symantec-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="b6771-104">Migreren van Symantec naar Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="b6771-104">Migrate from Symantec to Microsoft Defender for Endpoint</span></span>
<span data-ttu-id="b6771-105">Als u van plan bent om over te schakelen van De beveiliging van Het eindpunt van Symantec (Symantec) naar [Microsoft Defender voor](https://docs.microsoft.com/windows/security/threat-protection) Eindpunt (Microsoft Defender voor Eindpunt), bent u op de juiste plaats.</span><span class="sxs-lookup"><span data-stu-id="b6771-105">If you are planning to switch from Symantec Endpoint Protection (Symantec) to [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) (Microsoft Defender for Endpoint), you're in the right place.</span></span> <span data-ttu-id="b6771-106">Gebruik dit artikel als handleiding.</span><span class="sxs-lookup"><span data-stu-id="b6771-106">Use this article as a guide.</span></span>

<span data-ttu-id="b6771-107">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="b6771-107">**Applies to:**</span></span>
- [<span data-ttu-id="b6771-108">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="b6771-108">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b6771-109">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b6771-109">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

:::image type="content" source="images/symantec-mde-migration.png" alt-text="Overzicht van migreren van Symantec naar Defender voor Eindpunt":::

<span data-ttu-id="b6771-111">Wanneer u overschakelt van Symantec naar Defender voor Eindpunt, begint u met de Oplossing van Symantec in de actieve modus, configureert u Defender voor Eindpunt in passieve modus, gaat u aan boord naar Defender voor Eindpunt en stelt u Defender voor Endpoint in op de actieve modus en verwijdert u Symantec.</span><span class="sxs-lookup"><span data-stu-id="b6771-111">When you make the switch from Symantec to Defender for Endpoint, you begin with your Symantec solution in active mode, configure Defender for Endpoint in passive mode, onboard to Defender for Endpoint, and then set Defender for Endpoint to active mode and remove Symantec.</span></span>

## <a name="the-migration-process"></a><span data-ttu-id="b6771-112">Het migratieproces</span><span class="sxs-lookup"><span data-stu-id="b6771-112">The migration process</span></span>

<span data-ttu-id="b6771-113">Wanneer u overschakelt van Symantec naar Microsoft Defender voor Eindpunt, volgt u een proces dat kan worden onderverdeeld in drie fasen, zoals wordt beschreven in de volgende tabel:</span><span class="sxs-lookup"><span data-stu-id="b6771-113">When you switch from Symantec to Microsoft Defender for Endpoint, you follow a process that can be divided into three phases, as described in the following table:</span></span>

![Migratiefasen : voorbereiden, instellen, aan boord](images/phase-diagrams/migration-phases.png)

|<span data-ttu-id="b6771-115">Fase</span><span class="sxs-lookup"><span data-stu-id="b6771-115">Phase</span></span> |<span data-ttu-id="b6771-116">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="b6771-116">Description</span></span> |
|--|--|
|[<span data-ttu-id="b6771-117">Voorbereiden op uw migratie</span><span class="sxs-lookup"><span data-stu-id="b6771-117">Prepare for your migration</span></span>](symantec-to-microsoft-defender-atp-prepare.md) |<span data-ttu-id="b6771-118">Tijdens de **fase** Voorbereiden krijgt u Microsoft Defender voor Eindpunt, plant u uw rollen en machtigingen en verleent u toegang tot het Microsoft Defender-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="b6771-118">During the **Prepare** phase, you get Microsoft Defender for Endpoint, plan your roles and permissions, and grant access to the Microsoft Defender Security Center.</span></span> <span data-ttu-id="b6771-119">U configureert ook de apparaatproxy- en internetinstellingen om communicatie in te stellen tussen de apparaten van uw organisatie en Microsoft Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="b6771-119">You also configure your device proxy and internet settings to enable communication between your organization's devices and Microsoft Defender for Endpoint.</span></span> |
|[<span data-ttu-id="b6771-120">Microsoft Defender voor Eindpunt instellen</span><span class="sxs-lookup"><span data-stu-id="b6771-120">Set up Microsoft Defender for Endpoint</span></span>](symantec-to-microsoft-defender-atp-setup.md) |<span data-ttu-id="b6771-121">Tijdens de **installatiefase** configureert u instellingen en uitsluitingen voor Microsoft Defender Antivirus, Microsoft Defender voor Endpoint en Symantec Endpoint Protection.</span><span class="sxs-lookup"><span data-stu-id="b6771-121">During the **Setup** phase, you configure settings and exclusions for Microsoft Defender Antivirus, Microsoft Defender for Endpoint, and Symantec Endpoint Protection.</span></span> <span data-ttu-id="b6771-122">U maakt ook apparaatgroepen, verzamelingen en organisatie-eenheden.</span><span class="sxs-lookup"><span data-stu-id="b6771-122">You also create device groups, collections, and organizational units.</span></span> <span data-ttu-id="b6771-123">Ten slotte configureert u uw antimalwarebeleid en realtime beveiligingsinstellingen.</span><span class="sxs-lookup"><span data-stu-id="b6771-123">Finally, you configure your antimalware policies and real-time protection settings.</span></span>|
|[<span data-ttu-id="b6771-124">Onboard to Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="b6771-124">Onboard to Microsoft Defender for Endpoint</span></span>](symantec-to-microsoft-defender-atp-onboard.md) |<span data-ttu-id="b6771-125">Tijdens de **onboard-fase** kunt u uw apparaten aan boord van Microsoft Defender voor Eindpunten laten werken en controleren of deze apparaten communiceren met Microsoft Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="b6771-125">During the **Onboard** phase, you onboard your devices to Microsoft Defender for Endpoint and verify that those devices are communicating with Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="b6771-126">Als laatste verwijdert u Symantec en zorgt u ervoor dat de beveiliging via Microsoft Defender voor Eindpunt actief is.</span><span class="sxs-lookup"><span data-stu-id="b6771-126">Last, you uninstall Symantec and make sure protection through Microsoft Defender for Endpoint is in active mode.</span></span> |

## <a name="whats-included-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="b6771-127">Wat is inbegrepen in Microsoft Defender voor Eindpunt?</span><span class="sxs-lookup"><span data-stu-id="b6771-127">What's included in Microsoft Defender for Endpoint?</span></span>

<span data-ttu-id="b6771-128">In deze migratiehandleiding [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) richten we ons [](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) op de volgende generatie beveiligings- en eindpuntdetectie- en antwoordmogelijkheden als uitgangspunt voor de overstap naar Microsoft Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="b6771-128">In this migration guide, we focus on [next-generation protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) and [endpoint detection and response](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) capabilities as a starting point for moving to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="b6771-129">Microsoft Defender voor Eindpunt bevat echter veel meer dan antivirus- en eindpuntbeveiliging.</span><span class="sxs-lookup"><span data-stu-id="b6771-129">However, Microsoft Defender for Endpoint includes much more than antivirus and endpoint protection.</span></span> <span data-ttu-id="b6771-130">Microsoft Defender voor Eindpunt is een geïntegreerd platform voor preventieve beveiliging, detectie na inbreuken, geautomatiseerd onderzoek en antwoord.</span><span class="sxs-lookup"><span data-stu-id="b6771-130">Microsoft Defender for Endpoint is a unified platform for preventative protection, post-breach detection, automated investigation, and response.</span></span> <span data-ttu-id="b6771-131">In de volgende tabel worden functies en mogelijkheden in Microsoft Defender voor Eindpunt samengevat.</span><span class="sxs-lookup"><span data-stu-id="b6771-131">The following table summarizes features and capabilities in Microsoft Defender for Endpoint.</span></span> 

| <span data-ttu-id="b6771-132">Functie/mogelijkheid</span><span class="sxs-lookup"><span data-stu-id="b6771-132">Feature/Capability</span></span> | <span data-ttu-id="b6771-133">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="b6771-133">Description</span></span> |
|---|---|
| [<span data-ttu-id="b6771-134">Bedreigings- & kwetsbaarheidsbeheer</span><span class="sxs-lookup"><span data-stu-id="b6771-134">Threat & vulnerability management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) | <span data-ttu-id="b6771-135">Met & mogelijkheden voor beveiligingsprobleembeheer kunt u zwakke punten in uw eindpunten (zoals apparaten) identificeren, beoordelen en herstellen.</span><span class="sxs-lookup"><span data-stu-id="b6771-135">Threat & vulnerability management capabilities help identify, assess, and remediate weaknesses across your endpoints (such as devices).</span></span> |
| [<span data-ttu-id="b6771-136">Surface-beperking voor aanvallen</span><span class="sxs-lookup"><span data-stu-id="b6771-136">Attack surface reduction</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-attack-surface-reduction) | <span data-ttu-id="b6771-137">Regels voor het verminderen van aanvallen helpen de apparaten en toepassingen van uw organisatie te beschermen tegen cyberaanvallen en aanvallen.</span><span class="sxs-lookup"><span data-stu-id="b6771-137">Attack surface reduction rules help protect your organization's devices and applications from cyberthreats and attacks.</span></span> |
| [<span data-ttu-id="b6771-138">Beveiliging van de volgende generatie</span><span class="sxs-lookup"><span data-stu-id="b6771-138">Next-generation protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10) | <span data-ttu-id="b6771-139">Beveiliging van de volgende generatie omvat Microsoft Defender Antivirus om bedreigingen en malware te blokkeren.</span><span class="sxs-lookup"><span data-stu-id="b6771-139">Next-generation protection includes Microsoft Defender Antivirus to help block threats and malware.</span></span> |
| [<span data-ttu-id="b6771-140">Eindpuntdetectie en -antwoord</span><span class="sxs-lookup"><span data-stu-id="b6771-140">Endpoint detection and response</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) | <span data-ttu-id="b6771-141">Eindpuntdetectie- en antwoordmogelijkheden detecteren, onderzoeken en reageren op inbraakpogingen en actieve inbreuken.</span><span class="sxs-lookup"><span data-stu-id="b6771-141">Endpoint detection and response capabilities detect, investigate, and respond to intrusion attempts and active breaches.</span></span>  |
| [<span data-ttu-id="b6771-142">Geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="b6771-142">Advanced hunting</span></span>](advanced-hunting-overview.md) | <span data-ttu-id="b6771-143">Met geavanceerde zoekmogelijkheden kan uw beveiligingsteam indicatoren en entiteiten van bekende of potentiële bedreigingen vinden.</span><span class="sxs-lookup"><span data-stu-id="b6771-143">Advanced hunting capabilities enable your security operations team to locate indicators and entities of known or potential threats.</span></span> |
| [<span data-ttu-id="b6771-144">Gedrag blokkeren en insluiting</span><span class="sxs-lookup"><span data-stu-id="b6771-144">Behavioral blocking and containment</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) | <span data-ttu-id="b6771-145">Mogelijkheden voor het blokkeren en inperken van gedrag helpen bij het identificeren en stoppen van bedreigingen, op basis van hun gedrag en procesbomen, zelfs wanneer de bedreiging is gestart met de uitvoering.</span><span class="sxs-lookup"><span data-stu-id="b6771-145">Behavioral blocking and containment capabilities help identify and stop threats, based on their behaviors and process trees even when the threat has started execution.</span></span> |
| [<span data-ttu-id="b6771-146">Geautomatiseerd onderzoek en herstel</span><span class="sxs-lookup"><span data-stu-id="b6771-146">Automated investigation and remediation</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/automated-investigations) | <span data-ttu-id="b6771-147">Geautomatiseerde onderzoeks- en antwoordmogelijkheden onderzoeken waarschuwingen en nemen onmiddellijk herstelmaatregelen om inbreuken op te lossen.</span><span class="sxs-lookup"><span data-stu-id="b6771-147">Automated investigation and response capabilities examine alerts and take immediate remediation action to resolve breaches.</span></span> |
| <span data-ttu-id="b6771-148">[Threat hunting service](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-threat-experts) (Microsoft Threat Experts)</span><span class="sxs-lookup"><span data-stu-id="b6771-148">[Threat hunting service](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-threat-experts) (Microsoft Threat Experts)</span></span> | <span data-ttu-id="b6771-149">Bedreigingsjachtservices bieden beveiligingsteams controle en analyse op expertniveau, en om ervoor te zorgen dat kritieke bedreigingen niet worden gemist.</span><span class="sxs-lookup"><span data-stu-id="b6771-149">Threat hunting services provide security operations teams with expert level monitoring and analysis, and to help ensure that critical threats aren't missed.</span></span> |

<span data-ttu-id="b6771-150">**Wilt u meer informatie? Zie [Microsoft Defender voor Eindpunt](https://docs.microsoft.com/windows/security/threat-protection).**</span><span class="sxs-lookup"><span data-stu-id="b6771-150">**Want to learn more? See [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection).**</span></span>

## <a name="next-step"></a><span data-ttu-id="b6771-151">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="b6771-151">Next step</span></span>

- <span data-ttu-id="b6771-152">Ga verder [met Voorbereiden op uw migratie.](symantec-to-microsoft-defender-atp-prepare.md)</span><span class="sxs-lookup"><span data-stu-id="b6771-152">Proceed to [Prepare for your migration](symantec-to-microsoft-defender-atp-prepare.md).</span></span>