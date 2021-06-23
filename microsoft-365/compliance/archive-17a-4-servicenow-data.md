---
title: Configurare un connettore per archiviare i dati di ServiceNow in Microsoft 365
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
description: Informazioni su come configurare e usare un connettore ServiceNow DataParser 17a-4 per importare e archiviare i dati di ServiceNow in Microsoft 365.
ms.openlocfilehash: 9faa5fb1bf03bb7ab1e97b0bbd24aad4c38e91ae
ms.sourcegitcommit: 778103d20a2b4c43e524aa436775764d8d8d4c33
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2021
ms.locfileid: "53097032"
---
# <a name="set-up-a-connector-to-archive-servicenow-data-preview"></a><span data-ttu-id="ffebb-103">Configurare un connettore per archiviare i dati di ServiceNow (anteprima)</span><span class="sxs-lookup"><span data-stu-id="ffebb-103">Set up a connector to archive ServiceNow data (preview)</span></span>

<span data-ttu-id="ffebb-104">Utilizzare [ServiceNow DataParser](https://www.17a-4.com/dataparser/) da 17a-4 LLC per importare e archiviare i dati da ServiceNow alle cassette postali degli utenti nell'organizzazione Microsoft 365 locale.</span><span class="sxs-lookup"><span data-stu-id="ffebb-104">Use the [ServiceNow DataParser](https://www.17a-4.com/dataparser/) from 17a-4 LLC to import and archive data from ServiceNow to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="ffebb-105">DataParser include un connettore ServiceNow configurato per acquisire elementi da un'origine dati di terze parti e importare tali elementi in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ffebb-105">The DataParser includes a ServiceNow connector that's configured to capture items from a third-party data source and import those items to Microsoft 365.</span></span> <span data-ttu-id="ffebb-106">Il connettore ServiceNow DataParser converte i dati serviceNow in un formato di messaggio di posta elettronica e quindi importa tali elementi nelle cassette postali degli utenti in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ffebb-106">The ServiceNow DataParser connector converts ServiceNow data to an email message format and then imports those items to user mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="ffebb-107">Dopo aver archiviato i dati di ServiceNow nelle cassette postali degli utenti, è possibile applicare funzionalità di conformità Microsoft 365 quali conservazione per controversia legale, eDiscovery, criteri di conservazione ed etichette di conservazione e conformità delle comunicazioni.</span><span class="sxs-lookup"><span data-stu-id="ffebb-107">After ServiceNow data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="ffebb-108">L'utilizzo di un connettore ServiceNow per importare e archiviare i dati in Microsoft 365 può aiutare l'organizzazione a rimanere conforme ai criteri governativi e normativi.</span><span class="sxs-lookup"><span data-stu-id="ffebb-108">Using a ServiceNow connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-servicenow-data"></a><span data-ttu-id="ffebb-109">Panoramica dell'archiviazione dei dati serviceNow</span><span class="sxs-lookup"><span data-stu-id="ffebb-109">Overview of archiving ServiceNow data</span></span>

<span data-ttu-id="ffebb-110">Nella panoramica seguente viene illustrato il processo di utilizzo di un connettore dati per archiviare i dati serviceNow in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ffebb-110">The following overview explains the process of using a data connector to archive ServiceNow data in Microsoft 365.</span></span>

![Flusso di lavoro di archiviazione per i dati di ServiceNow da 17a a 4](../media/ServiceNowDataParserConnectorWorkflow.png)

1. <span data-ttu-id="ffebb-112">L'organizzazione collabora con 17a-4 per configurare ServiceNow DataParser.</span><span class="sxs-lookup"><span data-stu-id="ffebb-112">Your organization works with 17a-4 to set up and configure the ServiceNow DataParser.</span></span>

2. <span data-ttu-id="ffebb-113">A intervalli regolari, gli elementi ServiceNow vengono raccolti da DataParser.</span><span class="sxs-lookup"><span data-stu-id="ffebb-113">On a regular basis, ServiceNow items are collected by the DataParser.</span></span> <span data-ttu-id="ffebb-114">DataParser converte anche il contenuto di un messaggio in un formato di messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="ffebb-114">The DataParser also converts the content of a message to an email message format.</span></span>

3. <span data-ttu-id="ffebb-115">Il connettore ServiceNow DataParser creato nel Centro conformità Microsoft 365 si connette a DataParser e trasferisce i messaggi in una posizione Archiviazione di Azure sicura nel cloud Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ffebb-115">The ServiceNow DataParser connector that you create in the Microsoft 365 compliance center connects to DataParser and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="ffebb-116">Nelle cassette postali degli utenti viene creata una sottocartella nella cartella Posta in arrivo denominata **ServiceNow DataParser** e gli elementi ServiceNow vengono importati in tale cartella.</span><span class="sxs-lookup"><span data-stu-id="ffebb-116">A subfolder in the Inbox folder named **ServiceNow DataParser** is created in the user mailboxes, and the ServiceNow items are imported to that folder.</span></span> <span data-ttu-id="ffebb-117">Il connettore determina in quale cassetta postale importare gli elementi utilizzando il valore della *proprietà Email.*</span><span class="sxs-lookup"><span data-stu-id="ffebb-117">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="ffebb-118">Ogni elemento ServiceNow contiene questa proprietà, che viene popolata con l'indirizzo di posta elettronica di ogni partecipante.</span><span class="sxs-lookup"><span data-stu-id="ffebb-118">Every ServiceNow item contains this property, which is populated with the email address of every participant.</span></span>

## <a name="before-you-set-up-a-connector"></a><span data-ttu-id="ffebb-119">Prima di configurare un connettore</span><span class="sxs-lookup"><span data-stu-id="ffebb-119">Before you set up a connector</span></span>

- <span data-ttu-id="ffebb-120">Creare un account DataParser per i connettori Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ffebb-120">Create a DataParser account for Microsoft connectors.</span></span> <span data-ttu-id="ffebb-121">A tale scopo, contattare [17a-4 LLC](https://www.17a-4.com/contact/).</span><span class="sxs-lookup"><span data-stu-id="ffebb-121">To do this, contact [17a-4 LLC](https://www.17a-4.com/contact/).</span></span> <span data-ttu-id="ffebb-122">È necessario accedere a questo account quando si crea il connettore nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="ffebb-122">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="ffebb-123">L'utente che crea il connettore ServiceNow DataParser nel passaggio 1 (e lo completa nel passaggio 3) deve essere assegnato al ruolo Esportazione importazione cassette postali in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ffebb-123">The user who creates the ServiceNow DataParser connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="ffebb-124">Questo ruolo è necessario per aggiungere connettori nella pagina **Connettori** dati nell'Centro conformità Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ffebb-124">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="ffebb-125">Per impostazione predefinita, questo ruolo non viene assegnato a un gruppo di ruoli in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ffebb-125">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="ffebb-126">È possibile aggiungere il ruolo Esportazione importazione cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ffebb-126">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="ffebb-127">In caso contrario, è possibile creare un gruppo di ruoli, assegnare il ruolo Importazione/Esportazione cassette postali e quindi aggiungere gli utenti appropriati come membri.</span><span class="sxs-lookup"><span data-stu-id="ffebb-127">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="ffebb-128">Per ulteriori informazioni, vedere le sezioni [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) o Modify role [groups](/Exchange/permissions-exo/role-groups#modify-role-groups) nell'articolo "Manage role groups in Exchange Online".</span><span class="sxs-lookup"><span data-stu-id="ffebb-128">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-a-servicenow-dataparser-connector"></a><span data-ttu-id="ffebb-129">Passaggio 1: Configurare un connettore ServiceNow DataParser</span><span class="sxs-lookup"><span data-stu-id="ffebb-129">Step 1: Set up a ServiceNow DataParser connector</span></span>

<span data-ttu-id="ffebb-130">Il primo passaggio consiste nell'accedere alla pagina Connettori dati nell'Centro conformità Microsoft 365 e creare un connettore 17a-4 per i dati di ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="ffebb-130">The first step is to access to the Data connectors page in the Microsoft 365 compliance center and create a 17a-4 connector for ServiceNow data.</span></span>

1. <span data-ttu-id="ffebb-131">Passare a <https://compliance.microsoft.com> e quindi fare clic su **Connettori dati**  >  **ServiceNow DataParser**.</span><span class="sxs-lookup"><span data-stu-id="ffebb-131">Go to <https://compliance.microsoft.com> and then click **Data connectors** > **ServiceNow DataParser**.</span></span>

2. <span data-ttu-id="ffebb-132">Nella pagina **ServiceNow DataParser** product description fare clic **su Add connector**.</span><span class="sxs-lookup"><span data-stu-id="ffebb-132">On the **ServiceNow DataParser** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="ffebb-133">Nella pagina **Condizioni di servizio** fare clic su **Accetta.**</span><span class="sxs-lookup"><span data-stu-id="ffebb-133">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="ffebb-134">Immettere un nome univoco che identifichi il connettore e quindi fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="ffebb-134">Enter a unique name that identifies the connector and then click **Next**.</span></span>

5. <span data-ttu-id="ffebb-135">Accedi al tuo account 17a-4 e completa i passaggi della connessione guidata ServiceNow DataParser.</span><span class="sxs-lookup"><span data-stu-id="ffebb-135">Sign in to your 17a-4 account and complete the steps in the ServiceNow DataParser connection wizard.</span></span>

## <a name="step-2-configure-the-servicenow-dataparser-connector"></a><span data-ttu-id="ffebb-136">Passaggio 2: Configurare il connettore ServiceNow DataParser</span><span class="sxs-lookup"><span data-stu-id="ffebb-136">Step 2: Configure the ServiceNow DataParser connector</span></span>

<span data-ttu-id="ffebb-137">Utilizzare il supporto 17a-4 per configurare il connettore ServiceNow DataParser.</span><span class="sxs-lookup"><span data-stu-id="ffebb-137">Work with 17a-4 Support to configure the ServiceNow DataParser connector.</span></span>

## <a name="step-3-map-users"></a><span data-ttu-id="ffebb-138">Passaggio 3: mappare gli utenti</span><span class="sxs-lookup"><span data-stu-id="ffebb-138">Step 3: Map users</span></span>

<span data-ttu-id="ffebb-139">Il connettore ServiceNow DataParser mappa automaticamente gli utenti ai propri Microsoft 365 di posta elettronica prima di importare i dati Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ffebb-139">The ServiceNow DataParser connector will automatically map users to their Microsoft 365 email addresses before importing data to Microsoft 365.</span></span>

## <a name="step-4-monitor-the-servicenow-dataparser-connector"></a><span data-ttu-id="ffebb-140">Passaggio 4: Monitorare il connettore ServiceNow DataParser</span><span class="sxs-lookup"><span data-stu-id="ffebb-140">Step 4: Monitor the ServiceNow DataParser connector</span></span>

<span data-ttu-id="ffebb-141">Dopo aver creato un connettore ServiceNow DataParser, è possibile visualizzare lo stato del connettore nella Centro conformità Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ffebb-141">After you create a ServiceNow DataParser connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="ffebb-142">Vai a <https://compliance.microsoft.com> e fai clic su **Connettori dati** nel riquadro di spostamento sinistro.</span><span class="sxs-lookup"><span data-stu-id="ffebb-142">Go to <https://compliance.microsoft.com> and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="ffebb-143">Fare clic **sulla** scheda Connettori e quindi selezionare il connettore ServiceNow DataParser creato per visualizzare la pagina a comparsa, contenente le proprietà e le informazioni sul connettore.</span><span class="sxs-lookup"><span data-stu-id="ffebb-143">Click the **Connectors** tab and then select the ServiceNow DataParser connector that you created to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="ffebb-144">In **Stato connettore con origine** fare clic sul collegamento Scarica **registro** per aprire (o salvare) il registro di stato per il connettore.</span><span class="sxs-lookup"><span data-stu-id="ffebb-144">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="ffebb-145">Questo registro contiene i dati importati nel cloud Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ffebb-145">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="ffebb-146">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="ffebb-146">Known issues</span></span>

<span data-ttu-id="ffebb-147">Al momento non è possibile importare allegati o elementi di dimensioni superiori a 10 MB.</span><span class="sxs-lookup"><span data-stu-id="ffebb-147">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="ffebb-148">Il supporto per gli elementi più grandi sarà disponibile in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="ffebb-148">Support for larger items will be available at a later date.</span></span>
