---
title: Passaggio 2. Usare Microsoft Teams per creare il canale di gestione dei contratti
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.date: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: ''
description: Informazioni su come usare Microsoft Teams per creare il canale di gestione dei contratti usando una Microsoft 365 soluzione.
ms.openlocfilehash: 073ef1651ea5470594bfce0ffce65e849f9e063a
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841175"
---
# <a name="step-2-use-microsoft-teams-to-create-your-contract-management-channel"></a><span data-ttu-id="da8c8-104">Passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="da8c8-104">Step 2.</span></span> <span data-ttu-id="da8c8-105">Usare Microsoft Teams per creare il canale di gestione dei contratti</span><span class="sxs-lookup"><span data-stu-id="da8c8-105">Use Microsoft Teams to create your contract management channel</span></span>

<span data-ttu-id="da8c8-106">Quando l'organizzazione configura una soluzione di gestione dei contratti, è necessaria una posizione centrale in cui le parti interessate possano esaminare e gestire i contratti.</span><span class="sxs-lookup"><span data-stu-id="da8c8-106">When your organization sets up a contracts management solution, you need a central location in which stakeholders can review and manage contracts.</span></span> <span data-ttu-id="da8c8-107">A questo scopo, è possibile [usare](/microsoftteams/) Microsoft Teams per configurare un canale Teams e usare le funzionalità di Teams per:</span><span class="sxs-lookup"><span data-stu-id="da8c8-107">For this purpose, you can use [Microsoft Teams](/microsoftteams/) to set up a Teams channel and use the features in Teams to:</span></span>

- <span data-ttu-id="da8c8-108">**Creare un percorso per le parti interessate per visualizzare facilmente tutti i contratti che richiedono un'azione.**</span><span class="sxs-lookup"><span data-stu-id="da8c8-108">**Create a location for stakeholders to easily see all contracts that require action.**</span></span> <span data-ttu-id="da8c8-109">Ad esempio, in Teams puoi creare  una scheda Contratti nel canale Gestione contratti in cui i membri possono visualizzare una visualizzazione riquadro utile di tutti i contratti che necessitano di approvazione.</span><span class="sxs-lookup"><span data-stu-id="da8c8-109">For example, in Teams you can create a **Contracts** tab in the Contract Management channel in which members can see a useful tile view of all contracts that need approval.</span></span> <span data-ttu-id="da8c8-110">È inoltre possibile configurare la visualizzazione in modo che ogni "carta" elenchi i dati importanti di cui si è a cuore (ad esempio *Cliente,* Appaltatore e *Importo commissione).*</span><span class="sxs-lookup"><span data-stu-id="da8c8-110">You can also configure the view so that each "card" lists the important data you care about (such as *Client*, *Contractor*, and *Fee amount*).</span></span>

     ![Scheda Contratti.](../media/content-understanding/tile-view.png)

- <span data-ttu-id="da8c8-112">**Avere una posizione in cui i membri possono interagire tra loro e visualizzare eventi importanti.**</span><span class="sxs-lookup"><span data-stu-id="da8c8-112">**Have a location for members to interact with each other and see important events.**</span></span> <span data-ttu-id="da8c8-113">Ad esempio, in Teams, la scheda **Post** può essere usata per avere conversazioni, ottenere aggiornamenti e visualizzare azioni (ad esempio, un membro che rifiuta un contratto).</span><span class="sxs-lookup"><span data-stu-id="da8c8-113">For example, in Teams, the **Posts** tab can be used to have conversations, get updates, and see actions (such as a member rejecting a contract).</span></span> <span data-ttu-id="da8c8-114">Quando si è verificato un problema, ad esempio un nuovo contratto inviato per l'approvazione, la scheda **Post** può essere utilizzata non solo per annunciarlo, ma anche per conservare un record.</span><span class="sxs-lookup"><span data-stu-id="da8c8-114">When something has happened (such as a new contract submitted for approval), the **Posts** tab can be used not only to announce it, but also to keep a record of it.</span></span> <span data-ttu-id="da8c8-115">Se i membri sottoscrivano le notifiche, verranno avvisati ogni volta che è disponibile un aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="da8c8-115">And if members subscribe to notifications, they'll get notified whenever there's an update.</span></span>

     ![Scheda Post.](../media/content-understanding/posts.png)

- <span data-ttu-id="da8c8-117">**Avere una posizione in cui i membri possano visualizzare i contratti approvati per sapere quando possono essere inviati per il pagamento.**</span><span class="sxs-lookup"><span data-stu-id="da8c8-117">**Have a location for members to see approved contracts to know when they can be submitted for payment.**</span></span> <span data-ttu-id="da8c8-118">In Teams, è possibile creare un canale **Per** pagamento che elenca tutti i contratti che dovranno essere inviati al pagamento.</span><span class="sxs-lookup"><span data-stu-id="da8c8-118">In Teams, you can create a **For Payment** channel that will list all contracts that will need to be submitted to payment.</span></span> <span data-ttu-id="da8c8-119">È possibile estendere facilmente questa soluzione per scrivere queste informazioni direttamente in un'applicazione finanziaria di terze parti, ad esempio Dynamics CRM.</span><span class="sxs-lookup"><span data-stu-id="da8c8-119">You can easily extend this solution to instead write this information directly to a third-party financial application (for example, Dynamics CRM).</span></span>

## <a name="attach-your-sharepoint-document-library-to-the-contracts-tab"></a><span data-ttu-id="da8c8-120">Allegare SharePoint raccolta documenti alla scheda Contratti</span><span class="sxs-lookup"><span data-stu-id="da8c8-120">Attach your SharePoint document library to the Contracts tab</span></span>

<span data-ttu-id="da8c8-121">Dopo aver creato una **scheda** Contratti nel canale Gestione contratti, è necessario allegarvi SharePoint raccolta [documenti.](https://support.microsoft.com/office/add-a-sharepoint-page-list-or-document-library-as-a-tab-in-teams-131edef1-455f-4c67-a8ce-efa2ebf25f0b)</span><span class="sxs-lookup"><span data-stu-id="da8c8-121">After you create a **Contracts** tab in your Contracts Management channel, you need to [attach your SharePoint document library to it](https://support.microsoft.com/office/add-a-sharepoint-page-list-or-document-library-as-a-tab-in-teams-131edef1-455f-4c67-a8ce-efa2ebf25f0b).</span></span> <span data-ttu-id="da8c8-122">La SharePoint documento che si desidera allegare è quella a cui è stato applicato il modello di SharePoint syntex nella sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="da8c8-122">The SharePoint document library you want to attach is the one in which you applied your SharePoint Syntex document understanding model to in the previous section.</span></span>

<span data-ttu-id="da8c8-123">Dopo aver collegato SharePoint raccolta documenti, sarà possibile visualizzare eventuali contratti classificati tramite una visualizzazione elenco predefinita.</span><span class="sxs-lookup"><span data-stu-id="da8c8-123">After you attach the SharePoint document library, you'll be able to view any classified contracts through a default list view.</span></span>

   ![Visualizzazione elenco.](../media/content-understanding/list-view.png)

## <a name="customize-your-contracts-tab-tile-view"></a><span data-ttu-id="da8c8-125">Personalizzare la visualizzazione del riquadro della scheda Contratti</span><span class="sxs-lookup"><span data-stu-id="da8c8-125">Customize your Contracts tab tile view</span></span>

> [!NOTE]
> <span data-ttu-id="da8c8-126">Questa sezione fa riferimento ad esempi di codice contenuti nel file [ContractTileFormatting.jsincluso](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) nell'archivio [Contracts Management Solution Assets.](https://github.com/pnp/syntex-samples/tree/main/scenario%20assets/Contracts%20Management)</span><span class="sxs-lookup"><span data-stu-id="da8c8-126">This section references code examples that are contained in the [ContractTileFormatting.json](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) file that is included in the [Contracts Management Solution Assets repository](https://github.com/pnp/syntex-samples/tree/main/scenario%20assets/Contracts%20Management).</span></span>

<span data-ttu-id="da8c8-127">Anche Teams consente di visualizzare i contratti in una visualizzazione riquadro, è consigliabile personalizzarlo per visualizzare i dati del contratto che si desidera rendere visibili nella scheda contratto.</span><span class="sxs-lookup"><span data-stu-id="da8c8-127">While Teams lets you view your contracts in a tile view, you might want to customize it to view the contract data you want to make visible in the contract card.</span></span> <span data-ttu-id="da8c8-128">Ad esempio, per la **scheda Contratti,** è importante che i membri vedano il cliente, l'appaltatore e l'importo della commissione nella scheda del contratto.</span><span class="sxs-lookup"><span data-stu-id="da8c8-128">For example, for the **Contracts** tab, it is important for members to see the client, contractor, and fee amount on the contract card.</span></span> <span data-ttu-id="da8c8-129">Tutti questi campi sono stati estratti da ogni contratto tramite il SharePoint Syntex applicato alla raccolta documenti.</span><span class="sxs-lookup"><span data-stu-id="da8c8-129">All of these fields were extracted from each contract through your SharePoint Syntex model that was applied to your document library.</span></span> <span data-ttu-id="da8c8-130">Vuoi anche essere in grado di modificare la barra di intestazione del riquadro con colori diversi per ogni stato in modo che i membri possano facilmente vedere dove si trova il contratto nel processo di approvazione.</span><span class="sxs-lookup"><span data-stu-id="da8c8-130">You also want to be able to change the tile header bar to different colors for each status so that members can easily see where the contract is in the approval process.</span></span> <span data-ttu-id="da8c8-131">Ad esempio, tutti i contratti approvati avranno una barra di intestazione blu.</span><span class="sxs-lookup"><span data-stu-id="da8c8-131">For example, all approved contracts will have a blue header bar.</span></span>

   ![Visualizzazione elenco.](../media/content-understanding/tile.png)

<span data-ttu-id="da8c8-133">La visualizzazione riquadro personalizzata usata richiede di apportare modifiche al file JSON usato per formattare la visualizzazione riquadro corrente.</span><span class="sxs-lookup"><span data-stu-id="da8c8-133">The custom tile view you use requires you to make changes to the JSON file used to format the current tile view.</span></span> <span data-ttu-id="da8c8-134">Puoi fare riferimento al file JSON usato per creare la visualizzazione scheda esaminando il file [ContractTileFormatting.jssu.](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json)</span><span class="sxs-lookup"><span data-stu-id="da8c8-134">You can reference the JSON file used to create the card view by looking at the [ContractTileFormatting.json](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) file.</span></span> <span data-ttu-id="da8c8-135">Nelle sezioni seguenti vedrai sezioni specifiche del codice per le funzionalità presenti nelle schede del contratto.</span><span class="sxs-lookup"><span data-stu-id="da8c8-135">In the following sections, you'll see specific sections of the code for features that are in the contract cards.</span></span>

<span data-ttu-id="da8c8-136">Se vuoi visualizzare o apportare modifiche al codice JSON per la visualizzazione nel canale Teams, nel canale Teams seleziona il menu a discesa della visualizzazione e quindi seleziona **Formatta visualizzazione corrente.**</span><span class="sxs-lookup"><span data-stu-id="da8c8-136">If you want to see or make changes to the JSON code for your view in your Teams channel, in the Teams channel, select the view drop-down menu, and then select **Format current view**.</span></span>

   ![formato json.](../media/content-understanding/jason-format.png)

## <a name="card-size-and-shape"></a><span data-ttu-id="da8c8-138">Dimensioni e forma della scheda</span><span class="sxs-lookup"><span data-stu-id="da8c8-138">Card size and shape</span></span>

<span data-ttu-id="da8c8-139">Nel file [ContractTileFormatting.js,](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) esaminare la sezione seguente per visualizzare il codice per la formattazione delle dimensioni e della forma della scheda.</span><span class="sxs-lookup"><span data-stu-id="da8c8-139">In the [ContractTileFormatting.json](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) file, look at the following section to see the code for how the size and shape of the card is formatted.</span></span>

```JSON
                  {
                    "elmType": "div",
                    "style": {
                      "background-color": "#f5f5f5",
                      "padding": "5px",
                      "width": "180px"
                    },
                    "children": [
                      {
                        "elmType": "img",
                        "attributes": {
                          "src": "@thumbnail.large"
                        },
                        "style": {
                          "width": "185px",
                          "height": "248px"
                        }
                      }
```

## <a name="contract-status"></a><span data-ttu-id="da8c8-140">Stato contratto</span><span class="sxs-lookup"><span data-stu-id="da8c8-140">Contract status</span></span>

<span data-ttu-id="da8c8-141">Il codice seguente consente di definire lo stato di ogni scheda titolo.</span><span class="sxs-lookup"><span data-stu-id="da8c8-141">The following code lets you define the status of each title card.</span></span> <span data-ttu-id="da8c8-142">Si noti che ogni valore di stato (*New*, *In review*, *Approved* e *Rejected*) visualizza un codice di colore diverso per ognuno.</span><span class="sxs-lookup"><span data-stu-id="da8c8-142">Note that each status value (*New*, *In review*, *Approved*, and *Rejected*) will display a different color code for each.</span></span> <span data-ttu-id="da8c8-143">Nel file [ContractTileFormatting.js,](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) esaminare la sezione che definisce lo stato.</span><span class="sxs-lookup"><span data-stu-id="da8c8-143">In the [ContractTileFormatting.json](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) file, look at the section that defines the status.</span></span>

```JSON
          {
            "elmType": "div",
            "children": [
              {
                "elmType": "div",
                "style": {
                  "color": "white",
                  "background-color": "=if([$Status] == 'New', '#00b7c3', if([$Status] == 'In review', '#ffaa44', if([$Status] == 'Approved', '#0078d4', if([$Status] == 'Rejected', '#d13438', '#8378de'))))",
                  "padding": "5px 15px",
                  "height": "auto",
                  "text-transform": "uppercase",
                  "font-size": "12.5px"
                },
                "txtContent": "[$Status]"
              }
```

## <a name="extracted-fields"></a><span data-ttu-id="da8c8-144">Campi estratti</span><span class="sxs-lookup"><span data-stu-id="da8c8-144">Extracted fields</span></span>

<span data-ttu-id="da8c8-145">In ogni scheda contratto verranno visualizzati tre campi estratti per ogni contratto (*Cliente,* Appaltatore e Importo *commissione*).</span><span class="sxs-lookup"><span data-stu-id="da8c8-145">Each contract card will display three fields that were extracted for each contract (*Client*, *Contractor*, and *Fee Amount*).</span></span> <span data-ttu-id="da8c8-146">Inoltre, vuoi anche visualizzare l'ora/data in cui il file è stato classificato dal modello syntex SharePoint usato per identificarlo.</span><span class="sxs-lookup"><span data-stu-id="da8c8-146">Additionally, you also want to display the time/date that the file was classified by the SharePoint Syntex model used to identify it.</span></span>

<span data-ttu-id="da8c8-147">Nel file [ContractTileFormatting.js,](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) le sezioni seguenti definiscono ognuna di queste.</span><span class="sxs-lookup"><span data-stu-id="da8c8-147">In the [ContractTileFormatting.json](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) file, the following sections define each of these.</span></span>

### <a name="client"></a><span data-ttu-id="da8c8-148">Client</span><span class="sxs-lookup"><span data-stu-id="da8c8-148">Client</span></span>

<span data-ttu-id="da8c8-149">Questa sezione definisce il modo in cui "Client" verrà visualizzato sulla scheda e usa il valore per il contratto specifico.</span><span class="sxs-lookup"><span data-stu-id="da8c8-149">This section defines how "Client" will display on the card, and uses the value for the specific contract.</span></span>

```JSON
                      {
                        "elmType": "div",
                        "style": {
                          "color": "#767676",
                          "font-size": "12px"
                        },
                        "txtContent": "Client"
                      },
                      {
                        "elmType": "div",
                        "style": {
                          "margin-bottom": "12px",
                          "font-size": "16px",
                          "font-weight": "600"
                        },
                        "txtContent": "[$Client]"
                      },
```

### <a name="contractor"></a><span data-ttu-id="da8c8-150">Contractor</span><span class="sxs-lookup"><span data-stu-id="da8c8-150">Contractor</span></span>

<span data-ttu-id="da8c8-151">Questa sezione definisce la modalità di visualizzazione del "Terzista" sulla scheda e utilizza il valore per il contratto specifico.</span><span class="sxs-lookup"><span data-stu-id="da8c8-151">This section defines how the "Contractor" will display on the card, and uses the value for the specific contract.</span></span>

```JSON
                      {
                        "elmType": "div",
                        "style": {
                          "color": "#767676",
                          "font-size": "12px"
                        },
                        "txtContent": "Client"
                      },
                      {
                        "elmType": "div",
                        "style": {
                          "margin-bottom": "12px",
                          "font-size": "16px",
                          "font-weight": "600"
                        },
                        "txtContent": "[$Client]"
},
```

### <a name="fee-amount"></a><span data-ttu-id="da8c8-152">Importo commissione</span><span class="sxs-lookup"><span data-stu-id="da8c8-152">Fee Amount</span></span>

<span data-ttu-id="da8c8-153">Questa sezione definisce la modalità di visualizzazione dell'"Importo commissione" sulla scheda e utilizza il valore per il contratto specifico.</span><span class="sxs-lookup"><span data-stu-id="da8c8-153">This section defines how the "Fee Amount" will display on the card, and uses the value for the specific contract.</span></span>

```JSON
                      {
                        "elmType": "div",
                        "txtContent": "Fee amount",
                        "style": {
                          "color": "#767676",
                          "font-size": "12px",
                          "margin-bottom": "2px"
                        }
                      },
                      {
                        "elmType": "div",
                        "style": {
                          "margin-bottom": "12px",
                          "font-size": "14px"
                        },
                        "txtContent": "[$FeeAmount]"
                      },
```

### <a name="classification-date"></a><span data-ttu-id="da8c8-154">Data classificazione</span><span class="sxs-lookup"><span data-stu-id="da8c8-154">Classification date</span></span>

<span data-ttu-id="da8c8-155">In questa sezione viene definita la modalità di visualizzazione della "classificazione" nella scheda e viene utilizzato il valore per il contratto specifico.</span><span class="sxs-lookup"><span data-stu-id="da8c8-155">This section defines how "Classification" will display on the card, and uses the value for the specific contract.</span></span>

```JSON
                      {
                        "elmType": "div",
                        "txtContent": "Classified",
                        "style": {
                          "color": "#767676",
                          "font-size": "12px",
                          "margin-bottom": "2px"
                        }
                      },
                      {
                        "elmType": "div",
                        "style": {
                          "margin-bottom": "12px",
                          "font-size": "14px"
                        },
                        "txtContent": "[$PrimeLastClassified]"
                      }
```

## <a name="next-step"></a><span data-ttu-id="da8c8-156">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="da8c8-156">Next step</span></span>

[<span data-ttu-id="da8c8-157">Passaggio 3. Usare Power Automate per creare il flusso per elaborare i contratti</span><span class="sxs-lookup"><span data-stu-id="da8c8-157">Step 3. Use Power Automate to create your flow to process your contracts</span></span>](solution-manage-contracts-step3.md)
