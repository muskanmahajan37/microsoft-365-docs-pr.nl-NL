---
title: Een verbindingslijn instellen voor het archiveren van XSLT/XML-gegevens in Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: Beheerders kunnen een connector instellen voor het importeren en archiveren van XSLT/XML-gegevens van Veritas in Microsoft 365. Met deze verbindingslijn kunt u gegevens van externe gegevensbronnen archiveren in Microsoft 365, zodat u compliancefuncties zoals juridische bewaring, inhoud zoeken en bewaarbeleid kunt gebruiken om de gegevens van derden van uw organisatie te beheren.
ms.openlocfilehash: 51b05f83c51626bc60dc19b5ec9a63750903281c
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "52162302"
---
# <a name="set-up-a-connector-to-archive-xsltxml-data"></a><span data-ttu-id="592e7-104">Een connector instellen voor het archiveren van XSLT/XML-gegevens</span><span class="sxs-lookup"><span data-stu-id="592e7-104">Set up a connector to archive XSLT/XML data</span></span>

<span data-ttu-id="592e7-105">Gebruik een Veritas-connector in het Microsoft 365 compliancecentrum om gegevens uit de webpaginabron te importeren en te archiveren in gebruikerspostvakken in uw Microsoft 365 organisatie.</span><span class="sxs-lookup"><span data-stu-id="592e7-105">Use a Veritas connector in the Microsoft 365 compliance center to import and archive data from the Web page source to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="592e7-106">Veritas biedt u een [XSLT/XML-connector](https://globanet.com/xslt-xml) waarmee u snel bestanden kunt ontwikkelen die zijn gemaakt met behulp van XSLT (Extensible Style sheet Language Transformations) om XML-bestanden om te zetten in andere bestandsindelingen (zoals HTML of tekst) die kunnen worden geïmporteerd in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="592e7-106">Veritas provides you with an [XSLT/XML connector](https://globanet.com/xslt-xml) that allows the rapid development of files created by using XSLT (Extensible Style sheet Language Transformations) to transform XML files into other file formats (such as HTML or text) that can be imported to Microsoft 365.</span></span> <span data-ttu-id="592e7-107">De connector converteert de inhoud van een item uit de XSLT/XML-bron naar een e-mailberichtindeling en importeert vervolgens het geconverteerd item naar Microsoft 365 postvakken.</span><span class="sxs-lookup"><span data-stu-id="592e7-107">The connector converts the content of an item from the XSLT/XML source to an email message format and then imports the converted item to Microsoft 365 mailboxes.</span></span>

<span data-ttu-id="592e7-108">Nadat XSLT/XML-gegevens zijn opgeslagen in gebruikerspostvakken, kunt u Microsoft 365 compliancefuncties toepassen, zoals Litigation Hold, eDiscovery en bewaarbeleid en bewaarlabels.</span><span class="sxs-lookup"><span data-stu-id="592e7-108">After XSLT/XML data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, and retention policies and retention labels.</span></span> <span data-ttu-id="592e7-109">Met een XSLT/XML-connector voor het importeren en archiveren van gegevens in Microsoft 365 kan uw organisatie voldoen aan overheids- en regelgevingsbeleid.</span><span class="sxs-lookup"><span data-stu-id="592e7-109">Using an XSLT/XML connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-xsltxml-data"></a><span data-ttu-id="592e7-110">Overzicht van het archiveren van XSLT/XML-gegevens</span><span class="sxs-lookup"><span data-stu-id="592e7-110">Overview of archiving XSLT/XML data</span></span>

<span data-ttu-id="592e7-111">In het volgende overzicht wordt uitgelegd hoe het gebruik van een verbindingslijn voor het archiveren van XSLT/XML-brongegevens in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="592e7-111">The following overview explains the process of using a connector to archive XSLT/XML source data in Microsoft 365.</span></span>

![Archiveringswerkstroom voor XSLT/XML-gegevens](../media/XSLT-XMLConnectorWorkflow.png)

1. <span data-ttu-id="592e7-113">Uw organisatie werkt met de XSLT/XML-bron om een XSLT/XML-site in te stellen en te configureren.</span><span class="sxs-lookup"><span data-stu-id="592e7-113">Your organization works with the XSLT/XML source to set up and configure an XSLT/XML site.</span></span>

2. <span data-ttu-id="592e7-114">Eens in de 24 uur worden chatberichten uit de XSLT/XML-bron gekopieerd naar de Veritas Merge1-site.</span><span class="sxs-lookup"><span data-stu-id="592e7-114">Once every 24 hours, chat messages from the XSLT/XML source are copied to the Veritas Merge1 site.</span></span> <span data-ttu-id="592e7-115">De verbindingslijn converteert ook de inhoud naar een e-mailberichtindeling.</span><span class="sxs-lookup"><span data-stu-id="592e7-115">The connector also converts the content to an email message format.</span></span>

3. <span data-ttu-id="592e7-116">De XSLT/XML-connector die u maakt in het Microsoft 365-compliancecentrum, maakt elke dag verbinding met de Veritas Merge1-site en draagt de berichten over naar een veilige Azure Storage-locatie in de Microsoft-cloud.</span><span class="sxs-lookup"><span data-stu-id="592e7-116">The XSLT/XML connector that you create in the Microsoft 365 compliance center, connects to the Veritas Merge1 site every day and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="592e7-117">De connector importeert de geconverteerde berichtitems naar de postvakken van specifieke gebruikers met behulp van de waarde van de eigenschap *E-mail* van de automatische gebruikerstoewijzing, zoals beschreven in stap 3.</span><span class="sxs-lookup"><span data-stu-id="592e7-117">The connector imports the converted message items to the mailboxes of specific users using the value of the *Email* property of the automatic user mapping as described in Step 3.</span></span> <span data-ttu-id="592e7-118">Er wordt een nieuwe submap in de map Postvak IN met de naam **XSLT/XML** gemaakt in de postvakken van de gebruiker en de berichtitems worden geïmporteerd in die map.</span><span class="sxs-lookup"><span data-stu-id="592e7-118">A new subfolder in the Inbox folder named **XSLT/XML** is created in the user mailboxes, and the message items are imported to that folder.</span></span> <span data-ttu-id="592e7-119">De verbindingslijn doet dit met behulp van de waarde van de eigenschap *E-mail.*</span><span class="sxs-lookup"><span data-stu-id="592e7-119">The connector does this by using the value of the *Email* property.</span></span> <span data-ttu-id="592e7-120">Elk bericht bevat deze eigenschap, die wordt gevuld met het e-mailadres van elke deelnemer van het bericht.</span><span class="sxs-lookup"><span data-stu-id="592e7-120">Every message contains this property, which is populated with the email address of every participant of the message.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="592e7-121">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="592e7-121">Before you begin</span></span>

- <span data-ttu-id="592e7-122">Maak een Veritas Merge1-account voor Microsoft-connectors.</span><span class="sxs-lookup"><span data-stu-id="592e7-122">Create a Veritas Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="592e7-123">Neem contact op met [Veritas Customer Support](https://www.veritas.com/content/support/)om dit account te maken.</span><span class="sxs-lookup"><span data-stu-id="592e7-123">To create this account, contact [Veritas Customer Support](https://www.veritas.com/content/support/).</span></span> <span data-ttu-id="592e7-124">U meld u aan bij dit account wanneer u de verbindingslijn maakt in stap 1.</span><span class="sxs-lookup"><span data-stu-id="592e7-124">You will sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="592e7-125">De gebruiker die de XSLT/XML-connector maakt in stap 1 (en deze voltooit in stap 3), moet worden toegewezen aan de rol Postvak importeren exporteren in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="592e7-125">The user who creates the XSLT/XML connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="592e7-126">Deze rol is vereist om verbindingslijnen toe te voegen op de pagina **Gegevensconnectors** in het Microsoft 365 compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="592e7-126">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="592e7-127">Deze rol is standaard niet toegewezen aan een rollengroep in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="592e7-127">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="592e7-128">U kunt de rol Postvak importeren exporteren toevoegen aan de rollengroep Organisatiebeheer in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="592e7-128">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="592e7-129">U kunt ook een rollengroep maken, de rol Postvak importeren exporteren toewijzen en vervolgens de juiste gebruikers toevoegen als leden.</span><span class="sxs-lookup"><span data-stu-id="592e7-129">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="592e7-130">Zie de secties [](/Exchange/permissions-exo/role-groups#create-role-groups) Rollengroepen [](/Exchange/permissions-exo/role-groups#modify-role-groups) maken of Rollengroepen wijzigen in het artikel 'Rollengroepen beheren in Exchange Online'.</span><span class="sxs-lookup"><span data-stu-id="592e7-130">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-an-xsltxml-connector"></a><span data-ttu-id="592e7-131">Stap 1: Een XSLT/XML-connector instellen</span><span class="sxs-lookup"><span data-stu-id="592e7-131">Step 1: Set up an XSLT/XML connector</span></span>

<span data-ttu-id="592e7-132">De eerste stap is toegang tot de gegevensconnectors in het Microsoft 365 compliancecentrum en een **verbindingslijn** maken voor XSLT/XML-gegevens.</span><span class="sxs-lookup"><span data-stu-id="592e7-132">The first step is to access to the **Data Connectors** in the Microsoft 365 compliance center and create a connector for XSLT/XML data.</span></span>

1. <span data-ttu-id="592e7-133">Ga naar [https://compliance.microsoft.com](https://compliance.microsoft.com/) en klik vervolgens op **Gegevensconnectors**  >  **XSLT/XML.**</span><span class="sxs-lookup"><span data-stu-id="592e7-133">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **XSLT/XML**.</span></span>

2. <span data-ttu-id="592e7-134">Klik op **de pagina XSLT/XML-productbeschrijving** op **Nieuwe verbindingslijn toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="592e7-134">On the **XSLT/XML** product description page, click **Add new connector**.</span></span>

3. <span data-ttu-id="592e7-135">Klik op **de pagina Servicevoorwaarden** op **Accepteren.**</span><span class="sxs-lookup"><span data-stu-id="592e7-135">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="592e7-136">Voer een unieke naam in die de verbindingslijn identificeert en klik vervolgens op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="592e7-136">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="592e7-137">Meld u aan bij uw Merge1-account om de verbindingslijn te configureren.</span><span class="sxs-lookup"><span data-stu-id="592e7-137">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-an-xsltxml-connector"></a><span data-ttu-id="592e7-138">Stap 2: Een XSLT/XML-connector configureren</span><span class="sxs-lookup"><span data-stu-id="592e7-138">Step 2: Configure an XSLT/XML connector</span></span>

<span data-ttu-id="592e7-139">De tweede stap is het configureren van de XSLT/XML-connector op de merge1-site.</span><span class="sxs-lookup"><span data-stu-id="592e7-139">The second step is to configure the XSLT/XML connector on the Merge1 site.</span></span> <span data-ttu-id="592e7-140">Zie Handleiding [Connectors](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20XSLT-XML%20User%20Guide%20.pdf)van derden samenvoegen voor informatie over het configureren van de XSLT/XML-connector op de site Veritas Samenvoegen1.</span><span class="sxs-lookup"><span data-stu-id="592e7-140">For information about how to configure the XSLT/XML connector on the Veritas Merge1 site, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20XSLT-XML%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="592e7-141">Nadat u op **Opslaan &** Voltooien  hebt geklikt, wordt de pagina Gebruikerstoewijzing in de wizard verbindingslijn in het Microsoft 365 compliancecentrum weergegeven.</span><span class="sxs-lookup"><span data-stu-id="592e7-141">After you click **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="592e7-142">Stap 3: Gebruikers in kaart brengen en de configuratie van de connector voltooien</span><span class="sxs-lookup"><span data-stu-id="592e7-142">Step 3: Map users and complete the connector setup</span></span>

1. <span data-ttu-id="592e7-143">Als u gebruikers wilt in kaart brengen en de configuratie van de verbindingslijn wilt voltooien in het Microsoft 365 compliancecentrum, volgt u de onderstaande stappen:</span><span class="sxs-lookup"><span data-stu-id="592e7-143">To map users and complete the connector setup in the Microsoft 365 compliance center, follow the steps below:</span></span>

2. <span data-ttu-id="592e7-144">Schakel op **de pagina XSLT/XML-gebruikers** toewijzen Microsoft 365 gebruikers automatisch toewijzen in.</span><span class="sxs-lookup"><span data-stu-id="592e7-144">On the **Map XSLT/XML users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="592e7-145">De XSLT/XML-items bevatten een eigenschap *met* de naam E-mail, die e-mailadressen bevat voor gebruikers in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="592e7-145">The XSLT/XML items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="592e7-146">Als de verbindingslijn dit adres kan koppelen aan Microsoft 365 gebruiker, worden de items geïmporteerd in het postvak van die gebruiker.</span><span class="sxs-lookup"><span data-stu-id="592e7-146">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

3. <span data-ttu-id="592e7-147">Klik **op Volgende,** bekijk uw instellingen en ga naar de pagina Gegevensconnectors om de voortgang van het importproces voor de nieuwe **verbindingslijn** te bekijken.</span><span class="sxs-lookup"><span data-stu-id="592e7-147">Click **Next**, review your settings, and go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-xsltxml-connector"></a><span data-ttu-id="592e7-148">Stap 4: De XSLT/XML-connector controleren</span><span class="sxs-lookup"><span data-stu-id="592e7-148">Step 4: Monitor the XSLT/XML connector</span></span>

<span data-ttu-id="592e7-149">Nadat u de XSLT/XML-verbindingslijn hebt gebruikt, kunt u de verbindingslijnstatus weergeven in het Microsoft 365 compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="592e7-149">After you create the XSLT/XML connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="592e7-150">Ga naar [https://compliance.microsoft.com](https://compliance.microsoft.com) en klik op **Gegevensconnectoren** in het linkernavigatievenster.</span><span class="sxs-lookup"><span data-stu-id="592e7-150">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="592e7-151">Klik op **het tabblad Verbindingslijnen** en selecteer vervolgens de **XSLT/XML-connector** om de flyoutpagina weer te geven.</span><span class="sxs-lookup"><span data-stu-id="592e7-151">Click the **Connectors** tab and then select the **XSLT/XML** connector to display the flyout page.</span></span> <span data-ttu-id="592e7-152">Deze pagina bevat de eigenschappen en informatie over de verbindingslijn.</span><span class="sxs-lookup"><span data-stu-id="592e7-152">This page contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="592e7-153">Klik **onder Verbindingsstatus met bron** op de koppeling Logboek **downloaden** om het statuslogboek voor de verbindingslijn te openen (of op te slaan).</span><span class="sxs-lookup"><span data-stu-id="592e7-153">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="592e7-154">Dit logboek bevat gegevens die zijn geïmporteerd in de Microsoft-cloud.</span><span class="sxs-lookup"><span data-stu-id="592e7-154">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="592e7-155">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="592e7-155">Known issues</span></span>

- <span data-ttu-id="592e7-156">Op dit moment bieden we geen ondersteuning voor het importeren van bijlagen of items die groter zijn dan 10 MB.</span><span class="sxs-lookup"><span data-stu-id="592e7-156">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="592e7-157">Ondersteuning voor grotere items is op een later tijdstip beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="592e7-157">Support for larger items will be available at a later date.</span></span>