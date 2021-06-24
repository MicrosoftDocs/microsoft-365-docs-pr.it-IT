---
title: Archiviare i dati dalla piattaforma CellTrust SL2 a Microsoft 365
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
description: Informazioni su come configurare e usare un connettore dati CellTrust SL2 per importare e archiviare i dati delle comunicazioni mobili.
ms.openlocfilehash: 0929a92978f9b48d40153b3cc7328e5e05b54fd0
ms.sourcegitcommit: 778103d20a2b4c43e524aa436775764d8d8d4c33
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2021
ms.locfileid: "53097070"
---
# <a name="archive-data-from-celltrust-sl2-to-microsoft-365-preview"></a><span data-ttu-id="a3b31-103">Archiviare i dati da CellTrust SL2 a Microsoft 365 (anteprima)</span><span class="sxs-lookup"><span data-stu-id="a3b31-103">Archive data from CellTrust SL2 to Microsoft 365 (preview)</span></span>

<span data-ttu-id="a3b31-104">CellTrust SL2 acquisisce i dati delle comunicazioni mobili e si integra con le tecnologie di archiviazione leader per soddisfare i requisiti di individuazione elettronica per normative come FINRA, HIPAA, FOIA e TCPA.</span><span class="sxs-lookup"><span data-stu-id="a3b31-104">CellTrust SL2 captures mobile communications data and integrates with the leading archiving technologies to meet the electronic discovery requirements for regulations such as FINRA, HIPAA, FOIA, and TCPA.</span></span> <span data-ttu-id="a3b31-105">Il connettore dati SL2 importa gli elementi di comunicazione mobile Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a3b31-105">The SL2 Data Connector imports mobile communication items to Microsoft 365.</span></span> <span data-ttu-id="a3b31-106">In questo articolo viene descritto il processo di integrazione di SL2 con Microsoft 365 utilizzando cellTrust SL2 Data Connector per l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="a3b31-106">This article describes the process for integrating SL2 with Microsoft 365 by using the CellTrust SL2 Data Connector for archiving.</span></span> <span data-ttu-id="a3b31-107">Il completamento di questo processo presuppone che tu abbia sottoscritto il servizio CellTrust SL2 e abbia familiarità con l'architettura SL2.</span><span class="sxs-lookup"><span data-stu-id="a3b31-107">Completing this process assumes that you have subscribed to CellTrust SL2 service and are familiar with the SL2 architecture.</span></span> <span data-ttu-id="a3b31-108">Per informazioni su SL2, vedere <www.celltrust.com>.</span><span class="sxs-lookup"><span data-stu-id="a3b31-108">For information about SL2, see <www.celltrust.com>.</span></span>

<span data-ttu-id="a3b31-109">Dopo l'importazione dei dati nelle cassette postali degli utenti in Microsoft 365, è possibile applicare funzionalità di conformità Microsoft 365 quali conservazione per controversia legale, eDiscovery, criteri di conservazione Microsoft 365 e conformità delle comunicazioni.</span><span class="sxs-lookup"><span data-stu-id="a3b31-109">After data is imported to user mailboxes in Microsoft 365, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, Microsoft 365 retention policies, and communication compliance.</span></span> <span data-ttu-id="a3b31-110">L'utilizzo di CellTrust SL2 Data Connector per importare e archiviare i dati in Microsoft 365 può aiutare l'organizzazione a rimanere conforme ai criteri governativi e normativi.</span><span class="sxs-lookup"><span data-stu-id="a3b31-110">Using the CellTrust SL2 Data Connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-with-the-celltrust-sl2-data-connector"></a><span data-ttu-id="a3b31-111">Panoramica dell'archiviazione con cellTrust SL2 Data Connector</span><span class="sxs-lookup"><span data-stu-id="a3b31-111">Overview of archiving with the CellTrust SL2 Data Connector</span></span>

<span data-ttu-id="a3b31-112">La piattaforma SL2 di CellTrust acquisisce i dati di comunicazione da più origini.</span><span class="sxs-lookup"><span data-stu-id="a3b31-112">CellTrust's SL2 platform captures communication data from multiple sources.</span></span> <span data-ttu-id="a3b31-113">Le origini dati SL2 sono P2P (Person-to-Person) o Application-to-Person (A2P).</span><span class="sxs-lookup"><span data-stu-id="a3b31-113">SL2 data sources are either Person-to-Person (P2P) or Application-to-Person (A2P).</span></span> <span data-ttu-id="a3b31-114">Il processo descritto in questo articolo riguarda solo le origini dati P2P.</span><span class="sxs-lookup"><span data-stu-id="a3b31-114">The process described in this article pertains only to P2P data sources.</span></span> <span data-ttu-id="a3b31-115">Per tutte le origini dati P2P, almeno una parte della collaborazione è un utente SL2 sottoscritto al servizio SL2.</span><span class="sxs-lookup"><span data-stu-id="a3b31-115">For all P2P data sources, at least one party in the collaboration is an SL2 user who is subscribed to the SL2 service.</span></span> <span data-ttu-id="a3b31-116">Nella panoramica seguente viene illustrato il processo di utilizzo del connettore dati SL2 CellTrust in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a3b31-116">The following overview explains the process of using the CellTrust SL2 Data Connector in Microsoft 365.</span></span>

![Flusso di lavoro di archiviazione per il servizio CellTrust SL2](../media/CellTrustSL2ConnectorWorkflow.png)

1. <span data-ttu-id="a3b31-118">Gli utenti SL2 inviano e ricevono dati da e verso i servizi SL2 nel cloud Microsoft Azure cloud.</span><span class="sxs-lookup"><span data-stu-id="a3b31-118">SL2 users send and receive data to and from SL2 services in the Microsoft Azure cloud.</span></span>

2. <span data-ttu-id="a3b31-119">L'organizzazione ha un dominio SL2 nell'ambiente del servizio cloud SL2 di CellTrust.</span><span class="sxs-lookup"><span data-stu-id="a3b31-119">Your organization has an SL2 domain in CellTrust's SL2 Cloud Service environment.</span></span> <span data-ttu-id="a3b31-120">Il dominio può avere una o più unità organizzative.</span><span class="sxs-lookup"><span data-stu-id="a3b31-120">Your domain may have one or more organizational units (OUs).</span></span> <span data-ttu-id="a3b31-121">Il servizio cloud SL2 trasferisce i dati in un'area altamente sicura nella piattaforma Microsoft Azure, in modo che i dati non lascino mai l'Microsoft Azure ambiente.</span><span class="sxs-lookup"><span data-stu-id="a3b31-121">The SL2 Cloud Service transfers your data to a highly secure area in the Microsoft Azure platform, so that your data never leaves the Microsoft Azure environment.</span></span> <span data-ttu-id="a3b31-122">A seconda del piano SL2 (Enterprise, SMB o Government), il dominio è ospitato in Microsoft Azure Global o Microsoft Azure Government.</span><span class="sxs-lookup"><span data-stu-id="a3b31-122">Depending on your SL2 plan (Enterprise, SMB, or Government), your domain is either hosted on Microsoft Azure Global or Microsoft Azure Government.</span></span>

3. <span data-ttu-id="a3b31-123">Dopo aver creato il connettore dati SL2 CellTrust, il dominio e le unità organizzative (indipendentemente dal piano SL2), iniziare a inviare dati Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a3b31-123">After you create the CellTrust SL2 Data Connector, your domain and OUs (regardless of your SL2 plan), begin sending data to Microsoft 365.</span></span> <span data-ttu-id="a3b31-124">Il feed di dati è strutturato per supportare la creazione di report in base alle origini dati, alle unità organizzative o al dominio da solo.</span><span class="sxs-lookup"><span data-stu-id="a3b31-124">The data feed is structured to support reporting based on data sources, OUs, or the domain by itself.</span></span> <span data-ttu-id="a3b31-125">Di conseguenza, l'organizzazione ha bisogno di un solo connettore per alimentare tutte le origini dati Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a3b31-125">As a result, your organization needs only one connector to feed all your data sources to Microsoft 365.</span></span>

4. <span data-ttu-id="a3b31-126">Il connettore crea una cartella in ogni utente mappato con una licenza Office 365 appropriata intitolata **CellTrust SL2.**</span><span class="sxs-lookup"><span data-stu-id="a3b31-126">The connector creates a folder under each mapped user with an appropriate Office 365 license titled **CellTrust SL2**.</span></span> <span data-ttu-id="a3b31-127">Questo mapping connette un utente di CellTrust SL2 a una Office 365 cassetta postale utilizzando un indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="a3b31-127">This mapping connects a CellTrust SL2 user to an Office 365 mailbox by using an email address.</span></span> <span data-ttu-id="a3b31-128">Se un ID utente in CellTrust SL2 non ha alcuna corrispondenza in Office 365, i dati dell'utente non verranno archiviati.</span><span class="sxs-lookup"><span data-stu-id="a3b31-128">If a user ID in CellTrust SL2 has no match in Office 365, the user's data will not be archived.</span></span>

## <a name="before-you-set-up-a-connector"></a><span data-ttu-id="a3b31-129">Prima di configurare un connettore</span><span class="sxs-lookup"><span data-stu-id="a3b31-129">Before you set up a connector</span></span>

- <span data-ttu-id="a3b31-130">Verificare di disporre di un dominio nell'ambiente del servizio cloud CellTrust SL2.</span><span class="sxs-lookup"><span data-stu-id="a3b31-130">Verify that you have a domain in the CellTrust SL2 cloud service environment.</span></span> <span data-ttu-id="a3b31-131">Per ulteriori informazioni su come ottenere un dominio SL2 di produzione o di prova, [contattare CellTrust.](https://www.celltrust.com/contact-us/#form)</span><span class="sxs-lookup"><span data-stu-id="a3b31-131">For additional information on obtaining a production or trial SL2 domain, [Contact CellTrust](https://www.celltrust.com/contact-us/#form).</span></span>

- <span data-ttu-id="a3b31-132">Ottenere le credenziali per accedere all'account amministratore per il dominio SL2.</span><span class="sxs-lookup"><span data-stu-id="a3b31-132">Obtain the credentials to access the administrator account for your SL2 domain.</span></span>

- <span data-ttu-id="a3b31-133">L'utente che crea il connettore di dati CellTrust SL2 nel passaggio 1 (e lo completa nel passaggio 3) deve essere assegnato al ruolo Esportazione importazione cassette postali in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="a3b31-133">The user who creates the CellTrust SL2 data connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="a3b31-134">Questo ruolo è necessario per aggiungere connettori nella pagina **Connettori** dati nell'Centro conformità Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a3b31-134">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="a3b31-135">Per impostazione predefinita, questo ruolo non viene assegnato a un gruppo di ruoli in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="a3b31-135">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="a3b31-136">È possibile aggiungere il ruolo Esportazione importazione cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="a3b31-136">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="a3b31-137">In caso contrario, è possibile creare un gruppo di ruoli, assegnare il ruolo Importazione/Esportazione cassette postali e quindi aggiungere gli utenti appropriati come membri.</span><span class="sxs-lookup"><span data-stu-id="a3b31-137">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="a3b31-138">Per ulteriori informazioni, vedere le sezioni [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) o Modify role [groups](/Exchange/permissions-exo/role-groups#modify-role-groups) nell'articolo "Manage role groups in Exchange Online".</span><span class="sxs-lookup"><span data-stu-id="a3b31-138">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-create-a-celltrust-sl2-connector"></a><span data-ttu-id="a3b31-139">Passaggio 1: Creare un connettore SL2 CellTrust</span><span class="sxs-lookup"><span data-stu-id="a3b31-139">Step 1: Create a CellTrust SL2 connector</span></span>

<span data-ttu-id="a3b31-140">Il primo passaggio consiste nel creare un connettore dati nell'Centro conformità Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a3b31-140">The first step is to create a data connector in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="a3b31-141">Passare a <https://compliance.microsoft.com> e fare clic su **Connettori dati** nel riquadro di spostamento sinistro.</span><span class="sxs-lookup"><span data-stu-id="a3b31-141">Go to <https://compliance.microsoft.com> and click **Data connectors** on the left navigation pane.</span></span>

2. <span data-ttu-id="a3b31-142">Nella scheda **Panoramica** fare clic su **Filtro** e selezionare **Per CellTrust** e quindi applicare il filtro.</span><span class="sxs-lookup"><span data-stu-id="a3b31-142">On the **Overview** tab, click **Filter** and select **By CellTrust**, and then apply the filter.</span></span>

   ![Configurare il filtro per visualizzare i connettori CellTrust](../media/DataConnectorsFilter.png)

3. <span data-ttu-id="a3b31-144">Fare **clic su CellTrust SL2 (anteprima).**</span><span class="sxs-lookup"><span data-stu-id="a3b31-144">Click **CellTrust SL2 (preview**).</span></span>

4. <span data-ttu-id="a3b31-145">Nella pagina **Descrizione del prodotto CellTrust SL2 (anteprima)** fare clic **su Aggiungi connettore**.</span><span class="sxs-lookup"><span data-stu-id="a3b31-145">On the **CellTrust SL2 (preview**) product description page, click **Add connector**.</span></span>

5. <span data-ttu-id="a3b31-146">Nella pagina **Condizioni di servizio** fare clic su **Accetta.**</span><span class="sxs-lookup"><span data-stu-id="a3b31-146">On the **Terms of service** page, click **Accept**.</span></span>

6. <span data-ttu-id="a3b31-147">Immettere un nome univoco che identifichi il connettore e quindi fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="a3b31-147">Enter a unique name that identifies the connector and then click **Next**.</span></span> <span data-ttu-id="a3b31-148">Il nome immesso identificherà il connettore nella **pagina Connettori dati** dopo la creazione.</span><span class="sxs-lookup"><span data-stu-id="a3b31-148">The name you enter will identify the connector on the **Data connectors** page after you create it.</span></span>

7. <span data-ttu-id="a3b31-149">Nella pagina **Accedi al tuo account CellTrust** fai clic su Accedi a **CellTrust.**</span><span class="sxs-lookup"><span data-stu-id="a3b31-149">On the **Sign in to your CellTrust account** page, click **Sign into CellTrust**.</span></span> <span data-ttu-id="a3b31-150">Verrà reindirizzato al portale **CellTrust** per Microsoft 365 in una nuova finestra del browser.</span><span class="sxs-lookup"><span data-stu-id="a3b31-150">You'll be redirected to the **CellTrust Portal for Microsoft 365** in a new browser window.</span></span>

## <a name="step-2-select-the-domains-or-ous-to-archive"></a><span data-ttu-id="a3b31-151">Passaggio 2: Selezionare i domini o le unità organizzative da archiviare</span><span class="sxs-lookup"><span data-stu-id="a3b31-151">Step 2: Select the domains or OUs to archive</span></span>

<span data-ttu-id="a3b31-152">Il passaggio successivo consiste nell'accedere a un account amministratore per il dominio CellTrust SL2 e selezionare i domini e le unità organizzative da archiviare in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a3b31-152">The next step is to sign into an administrator account for your CellTrust SL2 domain and select the domains and OUs to archive in Microsoft 365.</span></span>

1. <span data-ttu-id="a3b31-153">Nella pagina CellTrust **Microsoft 365 Connector** selezionare l'ambiente nel servizio cloud SL2 per visualizzare una pagina di accesso.</span><span class="sxs-lookup"><span data-stu-id="a3b31-153">On the CellTrust **Microsoft 365 Connector** page, select your environment in the SL2 cloud service to display a sign-in page.</span></span>

   <span data-ttu-id="a3b31-154">In genere dovrebbe essere visualizzata un'opzione che rappresenta l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="a3b31-154">Typically, you should see one option representing your environment.</span></span> <span data-ttu-id="a3b31-155">Tuttavia, se si dispone di domini in più di un ambiente, saranno disponibili opzioni per ogni ambiente.</span><span class="sxs-lookup"><span data-stu-id="a3b31-155">However, if you have domains in more than one environment, you will see options for each environment.</span></span> <span data-ttu-id="a3b31-156">Dopo aver fatto una selezione, sarai reindirizzato alla pagina di accesso SL2.</span><span class="sxs-lookup"><span data-stu-id="a3b31-156">After you make a selection, you'll be redirected to the SL2 login page.</span></span>

2. <span data-ttu-id="a3b31-157">Accedere con le credenziali dell'account di amministratore di dominio o di unità organizzativa.</span><span class="sxs-lookup"><span data-stu-id="a3b31-157">Sign in with your Domain or OU Administrator account credentials.</span></span>

   <span data-ttu-id="a3b31-158">Se si accede come amministratore di dominio SL2, verranno visualizzati il nome del dominio e le unità organizzative in tale dominio.</span><span class="sxs-lookup"><span data-stu-id="a3b31-158">If you sign in as an SL2 domain administrator, you will see the name of your domain and the OUs in that domain.</span></span> <span data-ttu-id="a3b31-159">Se non si dispone di unità organizzative, viene visualizzato solo il nome del dominio.</span><span class="sxs-lookup"><span data-stu-id="a3b31-159">If you do not have OUs, you only see the name of your domain.</span></span> <span data-ttu-id="a3b31-160">Se si accede come amministratore dell'unità organizzativa, viene visualizzato solo il nome dell'unità organizzativa.</span><span class="sxs-lookup"><span data-stu-id="a3b31-160">If you log in as OU Administrator, you only see the name of your OU.</span></span>

3. <span data-ttu-id="a3b31-161">Abilitare le unità aziendali che si desidera archiviare.</span><span class="sxs-lookup"><span data-stu-id="a3b31-161">Enable the business units you wish to archive.</span></span> <span data-ttu-id="a3b31-162">La selezione del dominio non selezionerà automaticamente le unità organizzative.</span><span class="sxs-lookup"><span data-stu-id="a3b31-162">Selecting the domain will not automatically select the OUs.</span></span> <span data-ttu-id="a3b31-163">È necessario abilitare separatamente ogni unità organizzativa per archiviarla.</span><span class="sxs-lookup"><span data-stu-id="a3b31-163">You must enable each OU separately to archive it.</span></span>

   ![Abilitare le unità organizzative per l'archiviazione](../media/EnableCellTrustOUs.png)

4. <span data-ttu-id="a3b31-165">Al termine delle selezioni, chiudere la finestra del browser e tornare alla pagina della procedura guidata in Centro conformità Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a3b31-165">When you're finished with your selections, close the browser window and return to the wizard page in Microsoft 365 compliance center.</span></span> <span data-ttu-id="a3b31-166">Dopo alcuni secondi, la procedura guidata passa automaticamente al passaggio successivo del mapping degli utenti.</span><span class="sxs-lookup"><span data-stu-id="a3b31-166">After a few seconds, the wizard automatically advances to the next step of mapping users.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="a3b31-167">Passaggio 3: mappare gli utenti e completare la configurazione del connettore</span><span class="sxs-lookup"><span data-stu-id="a3b31-167">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="a3b31-168">L'ultimo passaggio consiste nel mappare gli utenti e completare la configurazione del connettore nella Centro conformità Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a3b31-168">The last step is to map users and complete the connector setup in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="a3b31-169">Nella pagina **Mapping utenti** selezionare **Abilita** mapping automatico utenti se l'indirizzo di posta elettronica per gli utenti è lo stesso sia in SL2 che Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a3b31-169">On the **User mapping** page, select **Enable automatic user mapping** if the email address for users is the same in both SL2 and  Microsoft 365.</span></span> <span data-ttu-id="a3b31-170">In caso contrario, è consigliabile caricare manualmente gli indirizzi di posta elettronica degli utenti caricando un file CSV che mappa l'indirizzo SL2 degli utenti al Microsoft 365 indirizzo.</span><span class="sxs-lookup"><span data-stu-id="a3b31-170">Otherwise, you should manually user email addresses by uploading a CSV file that maps users' SL2 address to their Microsoft 365 address.</span></span>

2. <span data-ttu-id="a3b31-171">Fare **clic su** Avanti, rivedere le impostazioni e quindi fare clic su **Fine** per creare il connettore.</span><span class="sxs-lookup"><span data-stu-id="a3b31-171">Click **Next**, review your settings, and then click **Finish** to create the connector.</span></span>

   <span data-ttu-id="a3b31-172">Il nuovo connettore viene aggiunto all'elenco nella **pagina Connettori dati.**</span><span class="sxs-lookup"><span data-stu-id="a3b31-172">The new connector is added to the list on the **Data connectors** page.</span></span>

## <a name="get-help-from-celltrust"></a><span data-ttu-id="a3b31-173">Ottenere assistenza da CellTrust</span><span class="sxs-lookup"><span data-stu-id="a3b31-173">Get help from CellTrust</span></span>

<span data-ttu-id="a3b31-174">Per informazioni dettagliate sulla configurazione di un connettore dati CellTrust SL2, vedere la pagina [CellTrust Customer Support.](https://www.celltrust.com/contact-us/#support)</span><span class="sxs-lookup"><span data-stu-id="a3b31-174">See the [CellTrust Customer Support page](https://www.celltrust.com/contact-us/#support) for details about contacting CellTrust for help with setting up a CellTrust SL2 data connector.</span></span>

## <a name="more-information"></a><span data-ttu-id="a3b31-175">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="a3b31-175">More information</span></span>

- <span data-ttu-id="a3b31-176">Un amministratore di dominio può configurare un connettore per il dominio o qualsiasi unità organizzativa in tale dominio.</span><span class="sxs-lookup"><span data-stu-id="a3b31-176">A domain administrator can set up a connector for the domain or any OUs in that domain.</span></span> <span data-ttu-id="a3b31-177">Se si utilizza l'account amministratore dell'unità organizzativa, è possibile configurare solo un connettore per tale unità organizzativa specifica.</span><span class="sxs-lookup"><span data-stu-id="a3b31-177">If you use the OU Administrator account, you can only set up a connector for that specific OU.</span></span>

- <span data-ttu-id="a3b31-178">Per completare correttamente i passaggi precedenti, devi disporre di una licenza Microsoft 365 E5 e disporre dei diritti di amministratore Microsoft Office appropriati.</span><span class="sxs-lookup"><span data-stu-id="a3b31-178">To successfully complete the steps above, you must be assigned a Microsoft 365 E5 license and have the proper Microsoft Office admin rights.</span></span>

- <span data-ttu-id="a3b31-179">Per testare il nuovo connettore, invia un SMS usando l'app per dispositivi mobili SL2 o dal portale SL2.</span><span class="sxs-lookup"><span data-stu-id="a3b31-179">To test the new connector, send a text message using your SL2 mobile app or from your SL2 portal.</span></span> <span data-ttu-id="a3b31-180">Passare alla cassetta Microsoft 365 e aprire la **cartella CellTrust SL2** nella cartella Posta in arrivo.</span><span class="sxs-lookup"><span data-stu-id="a3b31-180">Go to your Microsoft 365 mailbox and open the **CellTrust SL2** folder in your Inbox.</span></span> <span data-ttu-id="a3b31-181">La visualizzazione dei messaggi di testo nella cassetta postale potrebbe richiedere alcuni minuti.</span><span class="sxs-lookup"><span data-stu-id="a3b31-181">It may take a few minutes for the text messages to show up in your mailbox.</span></span>

- <span data-ttu-id="a3b31-182">Molte leggi e normative richiedono che la comunicazione elettronica sia conservata in modo tale che, quando richiesto, possa essere prodotto come prova.</span><span class="sxs-lookup"><span data-stu-id="a3b31-182">Many laws and regulations require electronic communication to be preserved in such a way that, when requested, it can be produced as evidence.</span></span> <span data-ttu-id="a3b31-183">Electronic Discovery (eDiscovery) viene utilizzato per conformarsi alla produzione di comunicazioni elettroniche.</span><span class="sxs-lookup"><span data-stu-id="a3b31-183">Electronic Discovery (eDiscovery) is used to comply with the production of electronic communication.</span></span> <span data-ttu-id="a3b31-184">Enterprise Le soluzioni di archiviazione delle informazioni sono progettate per eseguire eDiscovery e offrono funzionalità quali la gestione dei criteri di conservazione, la classificazione dei dati e la supervisione del contenuto.</span><span class="sxs-lookup"><span data-stu-id="a3b31-184">Enterprise Information Archiving (EIA) solutions are designed to perform eDiscovery, and provide features such as retention policy management, data classification, and content supervision.</span></span> <span data-ttu-id="a3b31-185">Microsoft 365 offre una soluzione di conservazione a lungo termine per la conformità alle normative e agli standard che influiscono sull'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a3b31-185">Microsoft 365 offers a long-term retention solution for compliance with the regulations and standards that affect your organization.</span></span>

- <span data-ttu-id="a3b31-186">Il termine *archiviazione* utilizzato in questo documento si riferisce all'archiviazione nel contesto di utilizzo all'interno di una soluzione Enterprise Information Archiving (EIA).</span><span class="sxs-lookup"><span data-stu-id="a3b31-186">The term *archiving* as used in this document refers to archiving in the context of use within an Enterprise Information Archiving (EIA) solution.</span></span> <span data-ttu-id="a3b31-187">Le soluzioni EIA dispongono di funzionalità di eDiscovery che producono documenti per procedimenti legali, controversie legali, controlli e indagini.</span><span class="sxs-lookup"><span data-stu-id="a3b31-187">EIA solutions have eDiscovery features that produce documents for legal proceedings, litigation, audits, and investigations.</span></span> <span data-ttu-id="a3b31-188">L'archiviazione nel contesto del backup e del ripristino utilizzato per il ripristino di emergenza e la continuità aziendale non è l'uso previsto del termine in questo documento.</span><span class="sxs-lookup"><span data-stu-id="a3b31-188">Archiving in the context of backup and restore used for disaster recovery and business continuity isn't the intended use of the term within this document.</span></span>