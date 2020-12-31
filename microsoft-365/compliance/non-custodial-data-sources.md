---
title: Aggiungere origini dati non detentive a un caso avanzato di eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: È possibile aggiungere origini dati non detentive a un caso di eDiscovery avanzato e inserire un'esenzione nell'origine dati. Le origini dati non detentive vengono reindicizzate, in modo che tutti i contenuti contrassegnati come parzialmente indicizzati vengano rielaborati per renderli completamente e rapidamente disponibili per la ricerca.
ms.openlocfilehash: 467f0e1167bfebe21bd3f2bbd52acd81529b8685
ms.sourcegitcommit: 36d12e02f6fda199ae7f2fb72fe52d7e2b5b4efd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/31/2020
ms.locfileid: "49740353"
---
# <a name="add-non-custodial-data-sources-to-an-advanced-ediscovery-case"></a><span data-ttu-id="5a23e-104">Aggiungere origini dati non detentive a un caso avanzato di eDiscovery</span><span class="sxs-lookup"><span data-stu-id="5a23e-104">Add non-custodial data sources to an Advanced eDiscovery case</span></span>

<span data-ttu-id="5a23e-105">In Advanced eDiscovery casi, non sempre soddisfare le proprie esigenze per associare un'origine dati Microsoft 365 con un custode nel caso.</span><span class="sxs-lookup"><span data-stu-id="5a23e-105">In Advanced eDiscovery cases, it doesn't always meet your needs to associate a Microsoft 365 data source with a custodian in the case.</span></span> <span data-ttu-id="5a23e-106">Tuttavia, potrebbe essere comunque necessario associare tali dati a un caso in modo che sia possibile cercarlo, aggiungerlo a un set di revisione e analizzarlo e rivederlo.</span><span class="sxs-lookup"><span data-stu-id="5a23e-106">But you may still need to associate that data with a case so that you can search it, add it to a review set, and analyze and review it.</span></span> <span data-ttu-id="5a23e-107">La caratteristica in Advanced eDiscovery è denominata *origini dati non detentive* e consente di aggiungere dati a un caso senza che sia necessario associarlo a un custode.</span><span class="sxs-lookup"><span data-stu-id="5a23e-107">The feature in Advanced eDiscovery is called *non-custodial data sources* and lets you add data to a case without having to associate it to a custodian.</span></span> <span data-ttu-id="5a23e-108">Applica inoltre la stessa funzionalità avanzata di eDiscovery ai dati non detentivi disponibili per i dati associati al custode.</span><span class="sxs-lookup"><span data-stu-id="5a23e-108">It also applies the same Advanced eDiscovery functionality to non-custodial data that's available for data associated with custodian.</span></span> <span data-ttu-id="5a23e-109">Due delle cose più utili che è possibile applicare ai dati non detentivi sono l'inserimento e l'elaborazione in attesa tramite l' [indicizzazione avanzata](indexing-custodian-data.md).</span><span class="sxs-lookup"><span data-stu-id="5a23e-109">Two of the most useful things that you can apply to non-custodial data is placing it on hold and processing it using [Advanced indexing](indexing-custodian-data.md).</span></span>

## <a name="add-a-non-custodial-data-source"></a><span data-ttu-id="5a23e-110">Aggiunta di un'origine dati non priva di detenzione</span><span class="sxs-lookup"><span data-stu-id="5a23e-110">Add a non-custodial data source</span></span>

<span data-ttu-id="5a23e-111">Eseguire la procedura seguente per aggiungere e gestire origini dati non detentive in un caso di eDiscovery avanzato.</span><span class="sxs-lookup"><span data-stu-id="5a23e-111">Follow these steps to add and manage non-custodial data sources in an Advanced eDiscovery case.</span></span>

1. <span data-ttu-id="5a23e-112">Nella Home page di **Advanced eDiscovery** fare clic sul caso per il quale si desidera aggiungere i dati.</span><span class="sxs-lookup"><span data-stu-id="5a23e-112">On the **Advanced eDiscovery** home page, click the case that you want to add the data to.</span></span>

2. <span data-ttu-id="5a23e-113">Fare clic sulla scheda **origini dati** , quindi fare clic su **Aggiungi**  >  **percorsi** dati.</span><span class="sxs-lookup"><span data-stu-id="5a23e-113">Click the **Data sources** tab and then click **Add data source** > **Add data locations**.</span></span>

3. <span data-ttu-id="5a23e-114">Nella pagina nuovo riquadro a comparsa **posizioni non detentive** scegliere le origini dati che si desidera aggiungere al caso.</span><span class="sxs-lookup"><span data-stu-id="5a23e-114">On the **New non-custodial data locations** flyout page, choose the data sources that you want to add to the case.</span></span> <span data-ttu-id="5a23e-115">È possibile aggiungere più cassette postali e siti espandendo le sezioni di **SharePoint** o di **Exchange** e quindi facendo clic su **modifica**.</span><span class="sxs-lookup"><span data-stu-id="5a23e-115">You can add multiple mailboxes and sites by expanding the **SharePoint** or **Exchange** sections and then clicking **Edit**.</span></span>

   ![Aggiungere i siti di SharePoint e le cassette postali di Exchange come origini dati non detentive](../media/NonCustodialDataSources1.png)

   - <span data-ttu-id="5a23e-117">**SharePoint** -fare clic su **modifica** per aggiungere siti.</span><span class="sxs-lookup"><span data-stu-id="5a23e-117">**SharePoint** - Click **Edit** to add sites.</span></span> <span data-ttu-id="5a23e-118">Selezionare un sito nell'elenco oppure è possibile cercare un sito digitando l'URL del sito nella barra di ricerca.</span><span class="sxs-lookup"><span data-stu-id="5a23e-118">Select a site in the list or you can search for a site by typing the URL of the site in the search bar.</span></span> <span data-ttu-id="5a23e-119">Selezionare i siti che si desidera aggiungere come origini dati non depositarie e fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="5a23e-119">Select the sites that you want to add as non-custodian data sources and click **Add**.</span></span>

   - <span data-ttu-id="5a23e-120">**Exchange** -fare clic su **modifica** per aggiungere le cassette postali.</span><span class="sxs-lookup"><span data-stu-id="5a23e-120">**Exchange** - Click **Edit** to add mailboxes.</span></span> <span data-ttu-id="5a23e-121">Digitare un nome o un alias (almeno tre caratteri) nella casella di ricerca per cassette postali o gruppi di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="5a23e-121">Type a name or alias (a minimum of three characters) in the search box for mailboxes or distribution groups.</span></span> <span data-ttu-id="5a23e-122">Selezionare le cassette postali che si desidera aggiungere come origini dati non depositarie e fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="5a23e-122">Select the mailboxes that you want to add as non-custodian data sources and click **Add**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="5a23e-123">È possibile utilizzare le sezioni di **SharePoint** ed **Exchange** per aggiungere siti e cassette postali associati a un gruppo di team o Yammer come origini dati non detentive.</span><span class="sxs-lookup"><span data-stu-id="5a23e-123">You can use the **SharePoint** and **Exchange** sections to add sites and mailboxes associated with a Team or Yammer group as non-custodial data sources.</span></span> <span data-ttu-id="5a23e-124">È necessario aggiungere separatamente la cassetta postale e il sito associati a un gruppo di team o Yammer.</span><span class="sxs-lookup"><span data-stu-id="5a23e-124">You have to separately add the mailbox and site associated with a Team or Yammer group.</span></span>

4. <span data-ttu-id="5a23e-125">Dopo aver aggiunto origini dati non detentive, è possibile disporre di tali posizioni in attesa o meno.</span><span class="sxs-lookup"><span data-stu-id="5a23e-125">After you add non-custodial data sources, you have the option to place those locations on hold or not.</span></span> <span data-ttu-id="5a23e-126">Selezionare o deselezionare la casella di controllo **blocca** accanto all'origine dati per metterla in attesa.</span><span class="sxs-lookup"><span data-stu-id="5a23e-126">Select or unselect the **Hold** checkbox next to the data source to place it on hold.</span></span>

5. <span data-ttu-id="5a23e-127">Fare clic su **Aggiungi** nella parte inferiore della pagina nuovo riquadro a comparsa **posizioni dati non detentive** per aggiungere le origini dati al caso.</span><span class="sxs-lookup"><span data-stu-id="5a23e-127">Click **Add** at the bottom of the **New non-custodial data locations** flyout page to add the data sources to the case.</span></span>

   <span data-ttu-id="5a23e-128">Ogni origine dati non priva di detenzione aggiunta è elencata nella pagina **origini dati** .</span><span class="sxs-lookup"><span data-stu-id="5a23e-128">Each non-custodial data source that you added is listed on the **Data sources** page.</span></span> <span data-ttu-id="5a23e-129">Le origini dati non detentive sono identificate dal valore **percorso dati** nella colonna **tipo di origine** .</span><span class="sxs-lookup"><span data-stu-id="5a23e-129">Non-custodial data sources are identified by the **Data location** value in the **Source type** column.</span></span>

   ![Origini dati non detentive nella scheda origini dati](../media/NonCustodialDataSources2.png)

<span data-ttu-id="5a23e-131">Dopo aver aggiunto le origini dati non detentive al caso, viene creato e visualizzato nella scheda **processi** del caso un processo denominato *reindicizzazione dei dati non detentivi* .</span><span class="sxs-lookup"><span data-stu-id="5a23e-131">After you add non-custodial data sources to the case, a job named *Reindexing non-custodial data* is created and displayed on the **Jobs** tab of the case.</span></span> <span data-ttu-id="5a23e-132">Una volta creato, il processo di indicizzazione avanzato è stato avviato e le origini dati vengono reindicizzate.</span><span class="sxs-lookup"><span data-stu-id="5a23e-132">After the job is created, the Advanced indexing process in initiated and the data sources are reindexed.</span></span>

## <a name="manage-the-hold-for-non-custodial-data-sources"></a><span data-ttu-id="5a23e-133">Gestire il blocco per le origini dati non detentive</span><span class="sxs-lookup"><span data-stu-id="5a23e-133">Manage the hold for non-custodial data sources</span></span>

<span data-ttu-id="5a23e-134">Dopo aver posizionato un'esenzione su un'origine dati non di detenzione, viene creato automaticamente un criterio di conservazione contenente le origini dati non detentive del caso.</span><span class="sxs-lookup"><span data-stu-id="5a23e-134">After you place a hold on a non-custodial data source, a hold policy that contains the non-custodial data sources for the case is automatically created.</span></span> <span data-ttu-id="5a23e-135">Quando si impostano altre origini dati non detentive, queste vengono aggiunte ai criteri di blocco.</span><span class="sxs-lookup"><span data-stu-id="5a23e-135">When you place other non-custodial data sources on hold, they are added to this hold policy.</span></span>

1. <span data-ttu-id="5a23e-136">Aprire il caso Advanced eDiscovery e selezionare la scheda **blocca** .</span><span class="sxs-lookup"><span data-stu-id="5a23e-136">Open the Advanced eDiscovery case and select the **Hold** tab.</span></span>

2. <span data-ttu-id="5a23e-137">Fare clic su **NCDSHold- \<GUID\>**, in cui il valore GUID è univoco per il caso.</span><span class="sxs-lookup"><span data-stu-id="5a23e-137">Click **NCDSHold-\<GUID\>**, where the GUID value is unique to the case.</span></span>

   <span data-ttu-id="5a23e-138">La pagina del riquadro a comparsa Visualizza informazioni e statistiche sulle origini dati non detentive in attesa.</span><span class="sxs-lookup"><span data-stu-id="5a23e-138">The flyout page display information and statistics about the non-custodial data sources on hold.</span></span>

   ![La pagina del riquadro a comparsa per le origini dati non detentive contiene le statistiche di visualizzazione](../media/NonCustodialDataSourcesHoldFlyout.png)

3. <span data-ttu-id="5a23e-140">Fare clic su **Modifica blocco** per visualizzare le origini dati non detentive inserite in attesa ed eseguire le attività di gestione seguenti:</span><span class="sxs-lookup"><span data-stu-id="5a23e-140">Click **Edit hold** to view the non-custodial data sources placed on hold and perform the following management tasks:</span></span>

   - <span data-ttu-id="5a23e-141">Nella pagina **percorsi** è possibile rilasciare un'origine dati non priva di detenzione rimuoverla dall'esenzione.</span><span class="sxs-lookup"><span data-stu-id="5a23e-141">On the **Locations** page, you can release a non-custodial data source by removing it from the hold.</span></span> <span data-ttu-id="5a23e-142">Il rilascio di un'origine dati non rimuove l'origine dati non affidatario dal caso.</span><span class="sxs-lookup"><span data-stu-id="5a23e-142">Releasing a data source doesn't remove the non-custodial data source from the case.</span></span> <span data-ttu-id="5a23e-143">Rimuove solo il blocco che è stato inserito nell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="5a23e-143">It only removes the hold that was placed on the data source.</span></span>

   - <span data-ttu-id="5a23e-144">Nella pagina **query** è possibile modificare il blocco per creare un blocco basato su query applicato a tutte le origini dati non detentive del caso.</span><span class="sxs-lookup"><span data-stu-id="5a23e-144">On the **Query** page, you can edit the hold to create a query-based hold that is applied to all tha non-custodial data sources in the case.</span></span>
