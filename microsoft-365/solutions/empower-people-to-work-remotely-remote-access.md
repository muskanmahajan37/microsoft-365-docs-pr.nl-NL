---
title: Stap 2. Externe toegang bieden tot on-premises apps en services
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 05/01/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
ms.custom:
- M365solutions
description: Zorg ervoor dat uw externe medewerkers toegang hebben tot on-premises informatiebronnen terwijl de toegang tot Microsoft 365-cloudservices wordt geoptimaliseerd.
ms.openlocfilehash: fb91451b52c55f2cad1e0efefe19a044ce1cc37b
ms.sourcegitcommit: 101084f9c81616342d78493232d8f13f5ffa4ddf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/01/2020
ms.locfileid: "44002646"
---
# <a name="step-2-provide-remote-access-to-on-premises-apps-and-services"></a><span data-ttu-id="1899c-104">Stap 2.</span><span class="sxs-lookup"><span data-stu-id="1899c-104">Step 2.</span></span> <span data-ttu-id="1899c-105">Externe toegang bieden tot on-premises apps en services</span><span class="sxs-lookup"><span data-stu-id="1899c-105">Provide remote access to on-premises apps and services</span></span>

<span data-ttu-id="1899c-106">Als uw organisatie een VPN-oplossing voor externe toegang gebruikt, meestal met VPN-servers aan de rand van uw netwerk en VPN-clients geïnstalleerd op de apparaten van uw gebruikers, kunnen uw gebruikers VPN-verbindingen voor externe toegang gebruiken voor toegang tot on-premises apps en servers.</span><span class="sxs-lookup"><span data-stu-id="1899c-106">If your organization uses a remote access VPN solution, typically with VPN servers on the edge of your network and VPN clients installed on your users' devices, your users can use remote access VPN connections to access on-premises apps and servers.</span></span> <span data-ttu-id="1899c-107">Het kan zijn dat u het verkeer naar de Microsoft 365-cloudservices moet optimaliseren.</span><span class="sxs-lookup"><span data-stu-id="1899c-107">But you may need to optimize traffic to Microsoft 365 cloud-based services.</span></span>

<span data-ttu-id="1899c-108">Als uw gebruikers geen VPN-oplossing gebruiken, kunt u Azure AD-toepassingsproxy (Active Directory) en Azure P2S-VPN (Point-to-Site) gebruiken om toegang te bieden, afhankelijk van het feit of al uw apps webversies zijn.</span><span class="sxs-lookup"><span data-stu-id="1899c-108">If your users do not use a VPN solution, you can use Azure Active Directory (Azure AD) Application Proxy and Azure Point-to-Site (P2S) VPN to provide access, depending on whether all your apps are web-based.</span></span>

<span data-ttu-id="1899c-109">Er zijn drie primaire configuraties:</span><span class="sxs-lookup"><span data-stu-id="1899c-109">There are three primary configurations:</span></span>

1. <span data-ttu-id="1899c-110">U gebruikt al een VPN-oplossing voor externe toegang.</span><span class="sxs-lookup"><span data-stu-id="1899c-110">You are already using a remote access VPN solution.</span></span>
2. <span data-ttu-id="1899c-111">U gebruikt geen VPN-oplossing voor externe toegang, u hebt een hybride identiteit en u hebt alleen externe toegang nodig tot on-premises web-apps.</span><span class="sxs-lookup"><span data-stu-id="1899c-111">You are not using a remote access VPN solution, you have hybrid identity, and you need remote access only to on-premises web-based apps.</span></span>
3. <span data-ttu-id="1899c-112">U gebruikt geen VPN-oplossing voor externe toegang en u hebt toegang nodig tot on-premises apps, waarvan sommige niet op internet zijn gebaseerd.</span><span class="sxs-lookup"><span data-stu-id="1899c-112">You are not using a remote access VPN solution and you need access to on-premises apps, some of which are not web-based.</span></span>

<span data-ttu-id="1899c-113">Met externe toegangsverbindingen kunt u ook [Extern bureaublad](https://support.microsoft.com/help/4028379/windows-10-how-to-use-remote-desktop) gebruiken om uw gebruikers verbinding te laten maken met een on-premises pc.</span><span class="sxs-lookup"><span data-stu-id="1899c-113">With remote access connections, you can also use [Remote Desktop](https://support.microsoft.com/help/4028379/windows-10-how-to-use-remote-desktop) to connect your users to an on-premises PC.</span></span> <span data-ttu-id="1899c-114">Een externe medewerker kan bijvoorbeeld Extern bureaublad gebruiken om verbinding te maken met de pc op zijn kantoor vanuit zijn Windows-, iOS- of Android-apparaat.</span><span class="sxs-lookup"><span data-stu-id="1899c-114">For example, a remote worker can use Remote Desktop to connect to the PC in their office from their Windows, iOS or Android device.</span></span> <span data-ttu-id="1899c-115">Zodra hij extern verbinding heeft gemaakt, kan hij deze gebruiken alsof hij erachter zit.</span><span class="sxs-lookup"><span data-stu-id="1899c-115">Once they are remotely connected, they can use it as if they were sitting in front of it.</span></span>

## <a name="optimize-performance-for-remote-access-vpn-clients-to-microsoft-365-cloud-services"></a><span data-ttu-id="1899c-116">Prestaties optimaliseren voor VPN-clients voor externe toegang tot Microsoft 365-cloudservices</span><span class="sxs-lookup"><span data-stu-id="1899c-116">Optimize performance for remote access VPN clients to Microsoft 365 cloud services</span></span>

<span data-ttu-id="1899c-117">Als uw externe medewerkers een traditionele VPN-client gebruiken om extern toegang te krijgen tot uw bedrijfsnetwerk, verifieer dan dat de VPN-client split tunneling ondersteunt.</span><span class="sxs-lookup"><span data-stu-id="1899c-117">If your remote workers are using a traditional VPN client to obtain remote access to your organization network, verify that the VPN client has split tunneling support.</span></span>

<span data-ttu-id="1899c-118">Zonder split tunneling wordt al uw externe werk verzonden via de VPN-verbinding, terwijl het moet worden doorgestuurd naar de edge-apparaten van uw bedrijf, worden verwerkt en dan verzonden op internet.</span><span class="sxs-lookup"><span data-stu-id="1899c-118">Without split tunneling, all of your remote work traffic gets sent across the VPN connection, where it must be forwarded to your organization’s edge devices, get processed, and then sent on the Internet.</span></span>

![Netwerkverkeer van VPN-clients zonder tunneling](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-before-tunneling.png)

<span data-ttu-id="1899c-120">Microsoft 365-verkeer moet een indirecte route gebruiken binnen uw organisatie dat dan kan worden doorgestuurd naar een Microsoft-netwerkingangspunt ver verwijderd van de fysieke locatie van de VPN-client.</span><span class="sxs-lookup"><span data-stu-id="1899c-120">Microsoft 365 traffic must take an indirect route through your organization, which could be the forwarded to a Microsoft network entry point far away from the VPN client’s physical location.</span></span> <span data-ttu-id="1899c-121">Met dit indirecte pad wordt een vertraging toegevoegd aan het netwerkverkeer en wordt de algehele prestatie negatief beïnvloed. </span><span class="sxs-lookup"><span data-stu-id="1899c-121">This indirect path adds latency to the network traffic and decreases overall performance.</span></span> 

<span data-ttu-id="1899c-122">Met split tunneling kunt u uw VPN-client zo configureren dat specifieke typen verkeer niet via de VPN-verbinding naar het bedrijfsnetwerk worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="1899c-122">With split tunneling, you can configure your VPN client to exclude specific types of traffic from being sent over the VPN connection to the organization network.</span></span>

<span data-ttu-id="1899c-123">Configureer uw split tunneling VPN-clients zodanig dat verkeer wordt uitgesloten naar de Microsoft 365-eindpuntcategorie **Optimaliseren** over de VPN-verbinding om toegang tot Microsoft 365-cloudresources te optimaliseren.</span><span class="sxs-lookup"><span data-stu-id="1899c-123">To optimize access to Microsoft 365 cloud resources, configure your split tunneling VPN clients to exclude traffic to the **Optimize** category Microsoft 365 endpoints over the VPN connection.</span></span> <span data-ttu-id="1899c-124">Zie [Office 365-eindpuntcategorieën](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#new-office-365-endpoint-categories) voor meer informatie. </span><span class="sxs-lookup"><span data-stu-id="1899c-124">For more information, see [Office 365 endpoint categories](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#new-office-365-endpoint-categories).</span></span> <span data-ttu-id="1899c-125">Bekijk [hier](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges) de lijst met eindpunten met categorie Optimaliseren.</span><span class="sxs-lookup"><span data-stu-id="1899c-125">See the list of Optimize category endpoints [here](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span></span>

![Netwerkverkeer van VPN-clients met tunneling](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-after-tunneling.png)

<span data-ttu-id="1899c-127">Hiermee kan de VPN-client cruciaal Microsoft 365-cloudserviceverkeer direct over internet verzenden en ontvangen en via het dichtstbijzijnde ingangspunt in het Microsoft-netwerk.</span><span class="sxs-lookup"><span data-stu-id="1899c-127">This allows the VPN client to send and receive crucial Microsoft 365 cloud service traffic directly over the Internet and to the nearest entry point into the Microsoft network.</span></span>

<span data-ttu-id="1899c-128">Bekijk [Office 365-connectiviteit optimaliseren voor externe gebruikers met VPN-split-tunneling](https://docs.microsoft.com/office365/enterprise/office-365-vpn-split-tunnel) voor meer informatie en richtlijnen.</span><span class="sxs-lookup"><span data-stu-id="1899c-128">For more information and guidance, see [Optimize Office 365 connectivity for remote users using VPN split tunneling](https://docs.microsoft.com/office365/enterprise/office-365-vpn-split-tunnel).</span></span>

## <a name="deploy-remote-access-when-all-your-apps-are-web-apps-and-you-have-hybrid-identity"></a><span data-ttu-id="1899c-129">Externe toegang implementeren wanneer al uw apps web-apps zijn en u een hybride identiteit hebt</span><span class="sxs-lookup"><span data-stu-id="1899c-129">Deploy remote access when all your apps are web apps and you have hybrid identity</span></span>

<span data-ttu-id="1899c-130">Als uw externe medewerkers geen traditionele VPN-client gebruiken en uw on-premises gebruikersaccounts en -groepen worden gesynchroniseerd met Azure AD, kunt u Azure AD-toepassingsproxy gebruiken om veilige externe toegang te bieden voor webtoepassingen die worden gehost op intranetservers.</span><span class="sxs-lookup"><span data-stu-id="1899c-130">If your remote workers are not using a traditional VPN client and your on-premises user accounts and groups are synchronized with Azure AD, you can use Azure AD Application Proxy to provide secure remote access for web-based applications hosted on intranet servers.</span></span> <span data-ttu-id="1899c-131">Webtoepassingen omvatten onder meer SharePoint-sites, Outlook-webtoegangsservers of andere bedrijfswebtoepassingen.</span><span class="sxs-lookup"><span data-stu-id="1899c-131">Web-based applications include SharePoint sites, Outlook Web Access servers, or any other web-based line of business applications.</span></span> 

<span data-ttu-id="1899c-132">Hier vindt u de onderdelen van Azure AD-toepassingsproxy.</span><span class="sxs-lookup"><span data-stu-id="1899c-132">Here are the components of Azure AD Application Proxy.</span></span>

![Onderdelen van Azure AD-toepassingsproxy](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-application-proxy.png)

<span data-ttu-id="1899c-134">Zie dit [overzicht van Azure AD-toepassingsproxy](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="1899c-134">For more information, see this [overview of Azure AD Application Proxy](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy).</span></span>

## <a name="deploy-remote-access-when-not-all-your-apps-are-web-apps"></a><span data-ttu-id="1899c-135">Externe toegang implementeren wanneer niet al uw apps web-apps zijn</span><span class="sxs-lookup"><span data-stu-id="1899c-135">Deploy remote access when not all your apps are web apps</span></span>

<span data-ttu-id="1899c-136">Als uw externe medewerkers geen traditionele VPN-client gebruiken en sommige van uw apps zijn geen web-apps, kunt u een Azure P2S-VPN (Point-to-Site) gebruiken.</span><span class="sxs-lookup"><span data-stu-id="1899c-136">If your remote workers are not using a traditional VPN client and any of your apps are not web-based, you can use an Azure Point-to-Site (P2S) VPN.</span></span>

<span data-ttu-id="1899c-137">Een P2S VPN-verbinding maakt een beveiligde verbinding met uw bedrijfsnetwerk vanaf het apparaat van de externe medewerker via een virtueel Azure-netwerk.</span><span class="sxs-lookup"><span data-stu-id="1899c-137">A P2S VPN connection creates a secure connection from a remote worker’s device to your organization network through an Azure virtual network.</span></span> 

![Onderdelen van Azure P2S VPN](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-p2s-vpn.png)

<span data-ttu-id="1899c-139">Zie dit [overzicht van P2S VPN](https://docs.microsoft.com/azure/vpn-gateway/point-to-site-about) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="1899c-139">For more information, see this [overview of P2S VPN](https://docs.microsoft.com/azure/vpn-gateway/point-to-site-about).</span></span>

## <a name="deploy-windows-virtual-desktop-to-provide-remote-access-for-remote-workers-using-personal-devices"></a><span data-ttu-id="1899c-140">Windows-virtueel bureaublad implementeren om externe toegang te bieden voor externe medewerkers met persoonlijke apparaten</span><span class="sxs-lookup"><span data-stu-id="1899c-140">Deploy Windows Virtual Desktop to provide remote access for remote workers using personal devices</span></span> 

<span data-ttu-id="1899c-141">Om externe medewerkers te ondersteunen die alleen hun persoonlijke en onbeheerde apparaten kunnen gebruiken, gebruikt u Windows-virtueel bureaublad in Azure om virtuele bureaubladen te maken en toe te wijzen aan uw gebruikers die thuiswerken.</span><span class="sxs-lookup"><span data-stu-id="1899c-141">To support remote workers who can only use their personal and unmanaged devices, use Windows Virtual Desktop in Azure to create and allocate virtual desktops for your users to use from home.</span></span>

<span data-ttu-id="1899c-142">Gevirtualiseerde pc's werken net als pc's die verbinding hebben met uw bedrijfsnetwerk.</span><span class="sxs-lookup"><span data-stu-id="1899c-142">Virtualized PCs can act just like PCs connected to your organization network.</span></span>

<span data-ttu-id="1899c-143">Voor meer informatie raadpleegt u dit [overzicht van Windows-virtueel bureaublad](https://docs.microsoft.com/azure/virtual-desktop/overview).</span><span class="sxs-lookup"><span data-stu-id="1899c-143">For more information, see [this overview of Windows Virtual Desktop](https://docs.microsoft.com/azure/virtual-desktop/overview).</span></span>

## <a name="admin-technical-resources-for-remote-access"></a><span data-ttu-id="1899c-144">Technische bronnen voor beheerders voor externe toegang</span><span class="sxs-lookup"><span data-stu-id="1899c-144">Admin technical resources for remote access</span></span>

- [<span data-ttu-id="1899c-145">Office 365-verkeer snel optimaliseren voor externe medewerkers en de belasting van uw infrastructuur verminderen</span><span class="sxs-lookup"><span data-stu-id="1899c-145">How to quickly optimize Office 365 traffic for remote staff & reduce the load on your infrastructure</span></span>](https://techcommunity.microsoft.com/t5/office-365-blog/how-to-quickly-optimize-office-365-traffic-for-remote-staff-amp/ba-p/1214571)
- [<span data-ttu-id="1899c-146">Office 365-connectiviteit optimaliseren voor externe gebruikers met VPN-split-tunneling</span><span class="sxs-lookup"><span data-stu-id="1899c-146">Optimize Office 365 connectivity for remote users using VPN split tunneling</span></span>](https://docs.microsoft.com/office365/enterprise/office-365-vpn-split-tunnel)

## <a name="results-of-step-2"></a><span data-ttu-id="1899c-147">Resultaten van stap 2</span><span class="sxs-lookup"><span data-stu-id="1899c-147">Results of Step 2</span></span>

<span data-ttu-id="1899c-148">Na de implementatie van een oplossing voor externe toegang voor uw externe medewerkers:</span><span class="sxs-lookup"><span data-stu-id="1899c-148">After deployment of a remote access solution for your remote workers:</span></span>

| <span data-ttu-id="1899c-149">Configuratie voor externe toegang</span><span class="sxs-lookup"><span data-stu-id="1899c-149">Remote access configuration</span></span> | <span data-ttu-id="1899c-150">Resultaten</span><span class="sxs-lookup"><span data-stu-id="1899c-150">Results</span></span> |
|:-------|:-----|
| <span data-ttu-id="1899c-151">Er is een VPN-oplossing voor externe toegang geïnstalleerd</span><span class="sxs-lookup"><span data-stu-id="1899c-151">A remote access VPN solution is in place</span></span> | <span data-ttu-id="1899c-152">U hebt uw VPN-client voor externe toegang voor split tunneling en de Microsoft 365-eindpuncategorie Optimaliseren geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="1899c-152">You have configured your remote access VPN client for split tunneling and for the Optimize category of Microsoft 365 endpoints.</span></span> |
| <span data-ttu-id="1899c-153">Geen VPN-oplossing voor externe toegang en u hebt alleen externe toegang nodig tot on-premises web-apps</span><span class="sxs-lookup"><span data-stu-id="1899c-153">No remote access VPN solution and you need remote access only to on-premises web-based apps</span></span> | <span data-ttu-id="1899c-154">U hebt Azure-toepassingsproxy geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="1899c-154">You have configured Azure Application Proxy.</span></span> |
| <span data-ttu-id="1899c-155">Geen VPN-oplossing voor externe toegang en u hebt externe toegang nodig tot on-premises apps, waarvan sommige niet op internet zijn gebaseerd</span><span class="sxs-lookup"><span data-stu-id="1899c-155">No remote access VPN solution and you need access to on-premises apps, some of which are not web-based</span></span> | <span data-ttu-id="1899c-156">U hebt Azure P2S VPN geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="1899c-156">You have configured Azure P2S VPN.</span></span> |
| <span data-ttu-id="1899c-157">Externe medewerkers gebruiken hun persoonlijke apparaten thuis</span><span class="sxs-lookup"><span data-stu-id="1899c-157">Remote workers are using their personal devices from home</span></span> | <span data-ttu-id="1899c-158">U hebt Windows-virtueel bureaublad geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="1899c-158">You have configured Windows Virtual Desktop.</span></span> |
|||

## <a name="next-step"></a><span data-ttu-id="1899c-159">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="1899c-159">Next step</span></span>

<span data-ttu-id="1899c-160">Ga door met [Stap 3](empower-people-to-work-remotely-manage-endpoints.md) om uw apparaten, pc's en andere eindpunten te beheren.</span><span class="sxs-lookup"><span data-stu-id="1899c-160">Continue with [Step 3](empower-people-to-work-remotely-manage-endpoints.md) to manage your devices, PCs, and other endpoints.</span></span>