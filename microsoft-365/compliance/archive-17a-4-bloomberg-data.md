---
title: Configurare un connettore per archiviare i dati di Bloomberg in Microsoft 365
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
description: Informazioni su come configurare e usare un connettore Bloomberg DataParser 17a-4 per importare e archiviare i dati di Bloomberg in Microsoft 365.
ms.openlocfilehash: 7fcc02384ce7bea6b9903fddef1256b97b8e340c
ms.sourcegitcommit: 778103d20a2b4c43e524aa436775764d8d8d4c33
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2021
ms.locfileid: "53096420"
---
# <a name="set-up-a-connector-to-archive-bloomberg-data-preview"></a><span data-ttu-id="c85b3-103">Configurare un connettore per archiviare i dati bloomberg (anteprima)</span><span class="sxs-lookup"><span data-stu-id="c85b3-103">Set up a connector to archive Bloomberg data (preview)</span></span>

<span data-ttu-id="c85b3-104">Utilizzare [Bloomberg DataParser](https://www.17a-4.com/Bloomberg-dataparser/) da 17a-4 LLC per importare e archiviare i dati da Bloomberg alle cassette postali degli utenti nell'organizzazione Microsoft 365 locale.</span><span class="sxs-lookup"><span data-stu-id="c85b3-104">Use the [Bloomberg DataParser](https://www.17a-4.com/Bloomberg-dataparser/) from 17a-4 LLC to import and archive data from Bloomberg to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="c85b3-105">DataParser include un connettore Bloomberg configurato per acquisire elementi da un'origine dati di terze parti e importare tali elementi in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c85b3-105">The DataParser includes a Bloomberg connector that's configured to capture items from a third-party data source and import those items to Microsoft 365.</span></span> <span data-ttu-id="c85b3-106">Il connettore Bloomberg DataParser converte i dati bloomberg in un formato di messaggio di posta elettronica e quindi importa tali elementi nelle cassette postali degli utenti in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c85b3-106">The Bloomberg DataParser connector converts Bloomberg data to an email message format and then imports those items to user mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="c85b3-107">Dopo aver archiviato i dati di Bloomberg nelle cassette postali degli utenti, è possibile applicare funzionalità di conformità Microsoft 365 quali conservazione per controversia legale, eDiscovery, criteri di conservazione ed etichette di conservazione e conformità delle comunicazioni.</span><span class="sxs-lookup"><span data-stu-id="c85b3-107">After Bloomberg data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="c85b3-108">L'utilizzo di un connettore Bloomberg per importare e archiviare i dati in Microsoft 365 può aiutare l'organizzazione a rimanere conforme ai criteri governativi e normativi.</span><span class="sxs-lookup"><span data-stu-id="c85b3-108">Using a Bloomberg connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-bloomberg-data"></a><span data-ttu-id="c85b3-109">Panoramica dell'archiviazione dei dati Bloomberg</span><span class="sxs-lookup"><span data-stu-id="c85b3-109">Overview of archiving Bloomberg data</span></span>

<span data-ttu-id="c85b3-110">Nella panoramica seguente viene illustrato il processo di utilizzo di un connettore dati per archiviare i dati bloomberg in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c85b3-110">The following overview explains the process of using a data connector to archive Bloomberg data in Microsoft 365.</span></span>

![Flusso di lavoro di archiviazione per i dati bloomberg dalla 17a alla 4](../media/BloombergDataParserConnectorWorkflow.png)

1. <span data-ttu-id="c85b3-112">L'organizzazione collabora con 17a-4 per configurare Bloomberg DataParser.</span><span class="sxs-lookup"><span data-stu-id="c85b3-112">Your organization works with 17a-4 to set up and configure the Bloomberg DataParser.</span></span>

2. <span data-ttu-id="c85b3-113">A intervalli regolari, gli elementi Bloomberg vengono raccolti da DataParser.</span><span class="sxs-lookup"><span data-stu-id="c85b3-113">On a regular basis, Bloomberg items are collected by the DataParser.</span></span> <span data-ttu-id="c85b3-114">DataParser converte anche il contenuto di un messaggio in un formato di messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="c85b3-114">The DataParser also converts the content of a message to an email message format.</span></span>

3. <span data-ttu-id="c85b3-115">Il connettore Bloomberg DataParser creato nel Centro conformità Microsoft 365 si connette a DataParser e trasferisce i messaggi in una posizione Archiviazione di Azure sicura nel cloud Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c85b3-115">The Bloomberg DataParser connector that you create in the Microsoft 365 compliance center connects to DataParser and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="c85b3-116">Nelle cassette postali degli utenti viene creata una sottocartella nella cartella Posta in arrivo denominata **Bloomberg DataParser** e gli elementi bloomberg vengono importati in tale cartella.</span><span class="sxs-lookup"><span data-stu-id="c85b3-116">A subfolder in the Inbox folder named **Bloomberg DataParser** is created in the user mailboxes, and the Bloomberg items are imported to that folder.</span></span> <span data-ttu-id="c85b3-117">Il connettore determina in quale cassetta postale importare gli elementi utilizzando il valore della *proprietà Email.*</span><span class="sxs-lookup"><span data-stu-id="c85b3-117">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="c85b3-118">Ogni elemento Bloomberg contiene questa proprietà, che viene popolata con l'indirizzo di posta elettronica di ogni partecipante.</span><span class="sxs-lookup"><span data-stu-id="c85b3-118">Every Bloomberg item contains this property, which is populated with the email address of every participant.</span></span>

## <a name="before-you-set-up-a-connector"></a><span data-ttu-id="c85b3-119">Prima di configurare un connettore</span><span class="sxs-lookup"><span data-stu-id="c85b3-119">Before you set up a connector</span></span>

- <span data-ttu-id="c85b3-120">Creare un account DataParser per i connettori Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c85b3-120">Create a DataParser account for Microsoft connectors.</span></span> <span data-ttu-id="c85b3-121">A tale scopo, contattare [17a-4 LLC](https://www.17a-4.com/contact/).</span><span class="sxs-lookup"><span data-stu-id="c85b3-121">To do this, contact [17a-4 LLC](https://www.17a-4.com/contact/).</span></span> <span data-ttu-id="c85b3-122">È necessario accedere a questo account quando si crea il connettore nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="c85b3-122">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="c85b3-123">L'utente che crea il connettore Bloomberg DataParser nel passaggio 1 (e lo completa nel passaggio 3) deve essere assegnato al ruolo Esportazione importazione cassette postali in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="c85b3-123">The user who creates the Bloomberg DataParser connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="c85b3-124">Questo ruolo è necessario per aggiungere connettori nella pagina **Connettori** dati nell'Centro conformità Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c85b3-124">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="c85b3-125">Per impostazione predefinita, questo ruolo non viene assegnato a un gruppo di ruoli in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="c85b3-125">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="c85b3-126">È possibile aggiungere il ruolo Esportazione importazione cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="c85b3-126">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="c85b3-127">In caso contrario, è possibile creare un gruppo di ruoli, assegnare il ruolo Importazione/Esportazione cassette postali e quindi aggiungere gli utenti appropriati come membri.</span><span class="sxs-lookup"><span data-stu-id="c85b3-127">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="c85b3-128">Per ulteriori informazioni, vedere le sezioni [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) o Modify role [groups](/Exchange/permissions-exo/role-groups#modify-role-groups) nell'articolo "Manage role groups in Exchange Online".</span><span class="sxs-lookup"><span data-stu-id="c85b3-128">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-a-bloomberg-dataparser-connector"></a><span data-ttu-id="c85b3-129">Passaggio 1: Configurare un connettore Bloomberg DataParser</span><span class="sxs-lookup"><span data-stu-id="c85b3-129">Step 1: Set up a Bloomberg DataParser connector</span></span>

<span data-ttu-id="c85b3-130">Il primo passaggio consiste nell'accedere alla pagina Connettori dati nell'Centro conformità Microsoft 365 e creare un connettore 17a-4 per i dati bloomberg.</span><span class="sxs-lookup"><span data-stu-id="c85b3-130">The first step is to access to the Data connectors page in the Microsoft 365 compliance center and create a 17a-4 connector for Bloomberg data.</span></span>

1. <span data-ttu-id="c85b3-131">Passare a <https://compliance.microsoft.com> e quindi fare clic su **Connettori dati**  >  **Bloomberg DataParser**.</span><span class="sxs-lookup"><span data-stu-id="c85b3-131">Go to <https://compliance.microsoft.com> and then click **Data connectors** > **Bloomberg DataParser**.</span></span>

2. <span data-ttu-id="c85b3-132">Nella pagina **Descrizione prodotto Bloomberg DataParser** fare clic su **Aggiungi connettore.**</span><span class="sxs-lookup"><span data-stu-id="c85b3-132">On the **Bloomberg DataParser** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="c85b3-133">Nella pagina **Condizioni di servizio** fare clic su **Accetta.**</span><span class="sxs-lookup"><span data-stu-id="c85b3-133">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="c85b3-134">Immettere un nome univoco che identifichi il connettore e quindi fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="c85b3-134">Enter a unique name that identifies the connector and then click **Next**.</span></span>

5. <span data-ttu-id="c85b3-135">Accedi al tuo account 17a-4 e completa i passaggi della connessione guidata Bloomberg DataParser.</span><span class="sxs-lookup"><span data-stu-id="c85b3-135">Sign in to your 17a-4 account and complete the steps in the Bloomberg DataParser connection wizard.</span></span>

## <a name="step-2-configure-the-bloomberg-dataparser-connector"></a><span data-ttu-id="c85b3-136">Passaggio 2: Configurare il connettore Bloomberg DataParser</span><span class="sxs-lookup"><span data-stu-id="c85b3-136">Step 2: Configure the Bloomberg DataParser connector</span></span>

<span data-ttu-id="c85b3-137">Utilizzare il supporto 17a-4 per configurare il connettore Bloomberg DataParser.</span><span class="sxs-lookup"><span data-stu-id="c85b3-137">Work with 17a-4 Support to configure the Bloomberg DataParser connector.</span></span>

## <a name="step-3-map-users"></a><span data-ttu-id="c85b3-138">Passaggio 3: mappare gli utenti</span><span class="sxs-lookup"><span data-stu-id="c85b3-138">Step 3: Map users</span></span>

<span data-ttu-id="c85b3-139">Il connettore Bloomberg DataParser mappa automaticamente gli utenti ai propri Microsoft 365 di posta elettronica prima di importare i dati in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c85b3-139">The Bloomberg DataParser connector will automatically map users to their Microsoft 365 email addresses before importing data to Microsoft 365.</span></span>

## <a name="step-4-monitor-the-bloomberg-dataparser-connector"></a><span data-ttu-id="c85b3-140">Passaggio 4: Monitorare il connettore Bloomberg DataParser</span><span class="sxs-lookup"><span data-stu-id="c85b3-140">Step 4: Monitor the Bloomberg DataParser connector</span></span>

<span data-ttu-id="c85b3-141">Dopo aver creato un connettore Bloomberg DataParser, è possibile visualizzare lo stato del connettore nel Centro conformità Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c85b3-141">After you create a Bloomberg DataParser connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="c85b3-142">Vai a <https://compliance.microsoft.com> e fai clic su **Connettori dati** nel riquadro di spostamento sinistro.</span><span class="sxs-lookup"><span data-stu-id="c85b3-142">Go to <https://compliance.microsoft.com> and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="c85b3-143">Fare clic **sulla scheda Connettori** e quindi selezionare il connettore Bloomberg DataParser creato per visualizzare la pagina a comparsa, contenente le proprietà e le informazioni sul connettore.</span><span class="sxs-lookup"><span data-stu-id="c85b3-143">Click the **Connectors** tab and then select the Bloomberg DataParser connector that you created to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="c85b3-144">In **Stato connettore con origine** fare clic sul collegamento Scarica **registro** per aprire (o salvare) il registro di stato per il connettore.</span><span class="sxs-lookup"><span data-stu-id="c85b3-144">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="c85b3-145">Questo registro contiene i dati importati nel cloud Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c85b3-145">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="c85b3-146">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="c85b3-146">Known issues</span></span>

<span data-ttu-id="c85b3-147">Al momento non è possibile importare allegati o elementi di dimensioni superiori a 10 MB.</span><span class="sxs-lookup"><span data-stu-id="c85b3-147">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="c85b3-148">Il supporto per gli elementi più grandi sarà disponibile in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="c85b3-148">Support for larger items will be available at a later date.</span></span>