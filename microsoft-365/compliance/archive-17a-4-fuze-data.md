---
title: Configurare un connettore per archiviare i dati fuze in Microsoft 365
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
description: Informazioni su come configurare e usare un connettore Fuze DataParser 17a-4 per importare e archiviare i dati fuze in Microsoft 365.
ms.openlocfilehash: 9f3c7590a033c2c19d9b588167d67c24f917ec5f
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454506"
---
# <a name="set-up-a-connector-to-archive-fuze-data"></a><span data-ttu-id="c45f8-103">Configurare un connettore per archiviare i dati fuze</span><span class="sxs-lookup"><span data-stu-id="c45f8-103">Set up a connector to archive Fuze data</span></span>

<span data-ttu-id="c45f8-104">Utilizzare [Fuze DataParser](https://www.17a-4.com/fuze-dataparser/) da 17a-4 LLC per importare e archiviare i dati da Fuze alle cassette postali degli utenti nell'organizzazione Microsoft 365 locale.</span><span class="sxs-lookup"><span data-stu-id="c45f8-104">Use the [Fuze DataParser](https://www.17a-4.com/fuze-dataparser/) from 17a-4 LLC to import and archive data from Fuze to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="c45f8-105">DataParser include un connettore Fuze configurato per acquisire elementi da un'origine dati di terze parti e importare tali elementi in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c45f8-105">The DataParser includes a Fuze connector that's configured to capture items from a third-party data source and import those items to Microsoft 365.</span></span> <span data-ttu-id="c45f8-106">Il connettore Fuze DataParser converte i dati fuze in un formato di messaggio di posta elettronica e quindi importa tali elementi nelle cassette postali degli utenti in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c45f8-106">The Fuze DataParser connector converts Fuze data to an email message format and then imports those items to user mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="c45f8-107">Dopo aver archiviato i dati di Fuze nelle cassette postali degli utenti, è possibile applicare funzionalità di conformità Microsoft 365 quali conservazione per controversia legale, eDiscovery, criteri di conservazione ed etichette di conservazione e conformità delle comunicazioni.</span><span class="sxs-lookup"><span data-stu-id="c45f8-107">After Fuze data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="c45f8-108">L'utilizzo di un connettore Fuze per importare e archiviare i dati in Microsoft 365 può aiutare l'organizzazione a rimanere conforme ai criteri governativi e normativi.</span><span class="sxs-lookup"><span data-stu-id="c45f8-108">Using a Fuze connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-fuze-data"></a><span data-ttu-id="c45f8-109">Panoramica dell'archiviazione dei dati fuze</span><span class="sxs-lookup"><span data-stu-id="c45f8-109">Overview of archiving Fuze data</span></span>

<span data-ttu-id="c45f8-110">Nella panoramica seguente viene illustrato il processo di utilizzo di un connettore dati per archiviare i dati di Fuze in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c45f8-110">The following overview explains the process of using a data connector to archive Fuze data in Microsoft 365.</span></span>

![Flusso di lavoro di archiviazione per i dati fuze dalla 17a alla 4](../media/FuzeDataParserConnectorWorkflow.png)

1. <span data-ttu-id="c45f8-112">L'organizzazione collabora con 17a-4 per configurare Fuze DataParser.</span><span class="sxs-lookup"><span data-stu-id="c45f8-112">Your organization works with 17a-4 to set up and configure the Fuze DataParser.</span></span>

2. <span data-ttu-id="c45f8-113">A intervalli regolari, gli elementi Fuze vengono raccolti da DataParser.</span><span class="sxs-lookup"><span data-stu-id="c45f8-113">On a regular basis, Fuze items are collected by the DataParser.</span></span> <span data-ttu-id="c45f8-114">DataParser converte anche il contenuto di un messaggio in un formato di messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="c45f8-114">The DataParser also converts the content of a message to an email message format.</span></span>

3. <span data-ttu-id="c45f8-115">Il connettore Fuze DataParser creato nel Centro conformità Microsoft 365 si connette a DataParser e trasferisce i messaggi in una posizione Archiviazione di Azure sicura nel cloud Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c45f8-115">The Fuze DataParser connector that you create in the Microsoft 365 compliance center connects to DataParser and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="c45f8-116">Nelle cassette postali degli utenti viene creata una sottocartella nella cartella Posta in arrivo denominata **Fuze DataParser** e gli elementi Fuze vengono importati in tale cartella.</span><span class="sxs-lookup"><span data-stu-id="c45f8-116">A subfolder in the Inbox folder named **Fuze DataParser** is created in the user mailboxes, and the Fuze items are imported to that folder.</span></span> <span data-ttu-id="c45f8-117">Il connettore determina in quale cassetta postale importare gli elementi utilizzando il valore della *proprietà Email.*</span><span class="sxs-lookup"><span data-stu-id="c45f8-117">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="c45f8-118">Ogni elemento Fuze contiene questa proprietà, che viene popolata con l'indirizzo di posta elettronica di ogni partecipante.</span><span class="sxs-lookup"><span data-stu-id="c45f8-118">Every Fuze item contains this property, which is populated with the email address of every participant.</span></span>

## <a name="before-you-set-up-a-connector"></a><span data-ttu-id="c45f8-119">Prima di configurare un connettore</span><span class="sxs-lookup"><span data-stu-id="c45f8-119">Before you set up a connector</span></span>

- <span data-ttu-id="c45f8-120">Creare un account DataParser per i connettori Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c45f8-120">Create a DataParser account for Microsoft connectors.</span></span> <span data-ttu-id="c45f8-121">A tale scopo, contattare [17a-4 LLC](https://www.17a-4.com/contact/).</span><span class="sxs-lookup"><span data-stu-id="c45f8-121">To do this, contact [17a-4 LLC](https://www.17a-4.com/contact/).</span></span> <span data-ttu-id="c45f8-122">È necessario accedere a questo account quando si crea il connettore nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="c45f8-122">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="c45f8-123">L'utente che crea il connettore Fuze DataParser nel passaggio 1 (e lo completa nel passaggio 3) deve essere assegnato al ruolo Esportazione importazione cassette postali in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="c45f8-123">The user who creates the Fuze DataParser connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="c45f8-124">Questo ruolo è necessario per aggiungere connettori nella pagina **Connettori** dati nell'Centro conformità Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c45f8-124">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="c45f8-125">Per impostazione predefinita, questo ruolo non viene assegnato a un gruppo di ruoli in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="c45f8-125">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="c45f8-126">È possibile aggiungere il ruolo Esportazione importazione cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="c45f8-126">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="c45f8-127">In caso contrario, è possibile creare un gruppo di ruoli, assegnare il ruolo Importazione/Esportazione cassette postali e quindi aggiungere gli utenti appropriati come membri.</span><span class="sxs-lookup"><span data-stu-id="c45f8-127">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="c45f8-128">Per ulteriori informazioni, vedere le sezioni [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) o Modify role [groups](/Exchange/permissions-exo/role-groups#modify-role-groups) nell'articolo "Manage role groups in Exchange Online".</span><span class="sxs-lookup"><span data-stu-id="c45f8-128">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-a-fuze-dataparser-connector"></a><span data-ttu-id="c45f8-129">Passaggio 1: Configurare un connettore Fuze DataParser</span><span class="sxs-lookup"><span data-stu-id="c45f8-129">Step 1: Set up a Fuze DataParser connector</span></span>

<span data-ttu-id="c45f8-130">Il primo passaggio consiste nell'accedere alla pagina Connettori dati nel Centro conformità Microsoft 365 e creare un connettore 17a-4 per i dati fuze.</span><span class="sxs-lookup"><span data-stu-id="c45f8-130">The first step is to access to the Data connectors page in the Microsoft 365 compliance center and create a 17a-4 connector for Fuze data.</span></span>

1. <span data-ttu-id="c45f8-131">Passare a <https://compliance.microsoft.com> e quindi fare clic su **Connettori dati**  >  **Fuze DataParser**.</span><span class="sxs-lookup"><span data-stu-id="c45f8-131">Go to <https://compliance.microsoft.com> and then click **Data connectors** > **Fuze DataParser**.</span></span>

2. <span data-ttu-id="c45f8-132">Nella pagina **Descrizione prodotto Fuze DataParser** fare clic su **Aggiungi connettore.**</span><span class="sxs-lookup"><span data-stu-id="c45f8-132">On the **Fuze DataParser** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="c45f8-133">Nella pagina **Condizioni di servizio** fare clic su **Accetta.**</span><span class="sxs-lookup"><span data-stu-id="c45f8-133">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="c45f8-134">Immettere un nome univoco che identifichi il connettore e quindi fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="c45f8-134">Enter a unique name that identifies the connector and then click **Next**.</span></span>

5. <span data-ttu-id="c45f8-135">Accedi al tuo account 17a-4 e completa i passaggi della connessione guidata Fuze DataParser.</span><span class="sxs-lookup"><span data-stu-id="c45f8-135">Sign in to your 17a-4 account and complete the steps in the Fuze DataParser connection wizard.</span></span>

## <a name="step-2-configure-the-fuze-dataparser-connector"></a><span data-ttu-id="c45f8-136">Passaggio 2: Configurare il connettore Fuze DataParser</span><span class="sxs-lookup"><span data-stu-id="c45f8-136">Step 2: Configure the Fuze DataParser connector</span></span>

<span data-ttu-id="c45f8-137">Utilizzare il supporto 17a-4 per configurare il connettore Fuze DataParser.</span><span class="sxs-lookup"><span data-stu-id="c45f8-137">Work with 17a-4 Support to configure the Fuze DataParser connector.</span></span>

## <a name="step-3-map-users"></a><span data-ttu-id="c45f8-138">Passaggio 3: mappare gli utenti</span><span class="sxs-lookup"><span data-stu-id="c45f8-138">Step 3: Map users</span></span>

<span data-ttu-id="c45f8-139">Il connettore Fuze DataParser mappa automaticamente gli utenti ai propri Microsoft 365 di posta elettronica prima di importare i dati Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c45f8-139">The Fuze DataParser connector will automatically map users to their Microsoft 365 email addresses before importing data to Microsoft 365.</span></span>

## <a name="step-4-monitor-the-fuze-dataparser-connector"></a><span data-ttu-id="c45f8-140">Passaggio 4: Monitorare il connettore Fuze DataParser</span><span class="sxs-lookup"><span data-stu-id="c45f8-140">Step 4: Monitor the Fuze DataParser connector</span></span>

<span data-ttu-id="c45f8-141">Dopo aver creato un connettore Fuze DataParser, è possibile visualizzare lo stato del connettore nella Centro conformità Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c45f8-141">After you create a Fuze DataParser connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="c45f8-142">Vai a <https://compliance.microsoft.com> e fai clic su **Connettori dati** nel riquadro di spostamento sinistro.</span><span class="sxs-lookup"><span data-stu-id="c45f8-142">Go to <https://compliance.microsoft.com> and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="c45f8-143">Fare clic **sulla scheda** Connettori e quindi selezionare il connettore Fuze DataParser creato per visualizzare la pagina a comparsa, contenente le proprietà e le informazioni sul connettore.</span><span class="sxs-lookup"><span data-stu-id="c45f8-143">Click the **Connectors** tab and then select the Fuze DataParser connector that you created to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="c45f8-144">In **Stato connettore con origine** fare clic sul collegamento Scarica **registro** per aprire (o salvare) il registro di stato per il connettore.</span><span class="sxs-lookup"><span data-stu-id="c45f8-144">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="c45f8-145">Questo registro contiene i dati importati nel cloud Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c45f8-145">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="c45f8-146">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="c45f8-146">Known issues</span></span>

<span data-ttu-id="c45f8-147">Al momento non è possibile importare allegati o elementi di dimensioni superiori a 10 MB.</span><span class="sxs-lookup"><span data-stu-id="c45f8-147">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="c45f8-148">Il supporto per gli elementi più grandi sarà disponibile in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="c45f8-148">Support for larger items will be available at a later date.</span></span>
