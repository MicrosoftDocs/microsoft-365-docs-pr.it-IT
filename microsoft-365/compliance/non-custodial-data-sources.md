---
title: Aggiungere origini dati non di custodia a un Advanced eDiscovery caso
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
description: È possibile aggiungere origini dati non di custodia a un caso Advanced eDiscovery e mantenere l'origine dati. Le origini dati non di custodia vengono reindicizzate, quindi qualsiasi contenuto contrassegnato come parzialmente indicizzato viene rielaborato per renderlo ricercabile in modo completo e rapido.
ms.openlocfilehash: 467f0e1167bfebe21bd3f2bbd52acd81529b8685
ms.sourcegitcommit: 36d12e02f6fda199ae7f2fb72fe52d7e2b5b4efd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/31/2020
ms.locfileid: "49740353"
---
# <a name="add-non-custodial-data-sources-to-an-advanced-ediscovery-case"></a><span data-ttu-id="ea91c-104">Aggiungere origini dati non di custodia a un Advanced eDiscovery caso</span><span class="sxs-lookup"><span data-stu-id="ea91c-104">Add non-custodial data sources to an Advanced eDiscovery case</span></span>

<span data-ttu-id="ea91c-105">In Advanced eDiscovery casi, non sempre soddisfa le esigenze di associare un'origine dati Microsoft 365 a un responsabile nel caso.</span><span class="sxs-lookup"><span data-stu-id="ea91c-105">In Advanced eDiscovery cases, it doesn't always meet your needs to associate a Microsoft 365 data source with a custodian in the case.</span></span> <span data-ttu-id="ea91c-106">Tuttavia, potrebbe essere comunque necessario associare i dati a un caso in modo da poterli cercare, aggiungerli a un set di recensioni e analizzarli e esaminarli.</span><span class="sxs-lookup"><span data-stu-id="ea91c-106">But you may still need to associate that data with a case so that you can search it, add it to a review set, and analyze and review it.</span></span> <span data-ttu-id="ea91c-107">La funzionalità in Advanced eDiscovery è denominata origine dati *non* depositale e consente di aggiungere dati a un caso senza doverlo associare a un responsabile.</span><span class="sxs-lookup"><span data-stu-id="ea91c-107">The feature in Advanced eDiscovery is called *non-custodial data sources* and lets you add data to a case without having to associate it to a custodian.</span></span> <span data-ttu-id="ea91c-108">Applica inoltre la stessa Advanced eDiscovery ai dati non depositario disponibili per i dati associati al responsabile.</span><span class="sxs-lookup"><span data-stu-id="ea91c-108">It also applies the same Advanced eDiscovery functionality to non-custodial data that's available for data associated with custodian.</span></span> <span data-ttu-id="ea91c-109">Due delle operazioni più utili che è possibile applicare ai dati non depositario sono la conservazione e l'elaborazione tramite [l'indicizzazione avanzata.](indexing-custodian-data.md)</span><span class="sxs-lookup"><span data-stu-id="ea91c-109">Two of the most useful things that you can apply to non-custodial data is placing it on hold and processing it using [Advanced indexing](indexing-custodian-data.md).</span></span>

## <a name="add-a-non-custodial-data-source"></a><span data-ttu-id="ea91c-110">Aggiungere un'origine dati non depositale</span><span class="sxs-lookup"><span data-stu-id="ea91c-110">Add a non-custodial data source</span></span>

<span data-ttu-id="ea91c-111">Seguire questa procedura per aggiungere e gestire origini dati non di Advanced eDiscovery caso.</span><span class="sxs-lookup"><span data-stu-id="ea91c-111">Follow these steps to add and manage non-custodial data sources in an Advanced eDiscovery case.</span></span>

1. <span data-ttu-id="ea91c-112">Nella home **Advanced eDiscovery** fare clic sul caso a cui si desidera aggiungere i dati.</span><span class="sxs-lookup"><span data-stu-id="ea91c-112">On the **Advanced eDiscovery** home page, click the case that you want to add the data to.</span></span>

2. <span data-ttu-id="ea91c-113">Fare clic **sulla scheda Origini** dati e quindi su Aggiungi origine **dati** Aggiungi  >  **percorsi dati**.</span><span class="sxs-lookup"><span data-stu-id="ea91c-113">Click the **Data sources** tab and then click **Add data source** > **Add data locations**.</span></span>

3. <span data-ttu-id="ea91c-114">Nella pagina a comparsa **New non-custodial data locations** scegliere le origini dati che si desidera aggiungere al caso.</span><span class="sxs-lookup"><span data-stu-id="ea91c-114">On the **New non-custodial data locations** flyout page, choose the data sources that you want to add to the case.</span></span> <span data-ttu-id="ea91c-115">È possibile aggiungere più cassette postali e siti espandendo le sezioni SharePoint **o** **Exchange** e quindi facendo clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="ea91c-115">You can add multiple mailboxes and sites by expanding the **SharePoint** or **Exchange** sections and then clicking **Edit**.</span></span>

   ![Aggiungere SharePoint siti e Exchange cassette postali come origini dati non di tipo depositario](../media/NonCustodialDataSources1.png)

   - <span data-ttu-id="ea91c-117">**SharePoint** - Fare clic **su Modifica** per aggiungere siti.</span><span class="sxs-lookup"><span data-stu-id="ea91c-117">**SharePoint** - Click **Edit** to add sites.</span></span> <span data-ttu-id="ea91c-118">Selezionare un sito nell'elenco oppure è possibile cercare un sito digitando l'URL del sito nella barra di ricerca.</span><span class="sxs-lookup"><span data-stu-id="ea91c-118">Select a site in the list or you can search for a site by typing the URL of the site in the search bar.</span></span> <span data-ttu-id="ea91c-119">Selezionare i siti che si desidera aggiungere come origini dati non di proprietà e fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="ea91c-119">Select the sites that you want to add as non-custodian data sources and click **Add**.</span></span>

   - <span data-ttu-id="ea91c-120">**Exchange** - Fare clic **su Modifica** per aggiungere cassette postali.</span><span class="sxs-lookup"><span data-stu-id="ea91c-120">**Exchange** - Click **Edit** to add mailboxes.</span></span> <span data-ttu-id="ea91c-121">Digitare un nome o un alias (un minimo di tre caratteri) nella casella di ricerca per le cassette postali o i gruppi di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="ea91c-121">Type a name or alias (a minimum of three characters) in the search box for mailboxes or distribution groups.</span></span> <span data-ttu-id="ea91c-122">Selezionare le cassette postali che si desidera aggiungere come origini dati non di archiviazione e fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="ea91c-122">Select the mailboxes that you want to add as non-custodian data sources and click **Add**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="ea91c-123">È possibile utilizzare le **sezioni SharePoint** e **Exchange** per aggiungere siti e cassette postali associati a un team o a un gruppo di Yammer come origini dati non di tipo depositario.</span><span class="sxs-lookup"><span data-stu-id="ea91c-123">You can use the **SharePoint** and **Exchange** sections to add sites and mailboxes associated with a Team or Yammer group as non-custodial data sources.</span></span> <span data-ttu-id="ea91c-124">È necessario aggiungere separatamente la cassetta postale e il sito associati a un team o Yammer gruppo.</span><span class="sxs-lookup"><span data-stu-id="ea91c-124">You have to separately add the mailbox and site associated with a Team or Yammer group.</span></span>

4. <span data-ttu-id="ea91c-125">Dopo aver aggiunto origini dati non di tipo depositario, è possibile mettere tali posizioni in attesa o meno.</span><span class="sxs-lookup"><span data-stu-id="ea91c-125">After you add non-custodial data sources, you have the option to place those locations on hold or not.</span></span> <span data-ttu-id="ea91c-126">Selezionare o deselezionare la casella **di controllo** Esenzione accanto all'origine dati per metterla in attesa.</span><span class="sxs-lookup"><span data-stu-id="ea91c-126">Select or unselect the **Hold** checkbox next to the data source to place it on hold.</span></span>

5. <span data-ttu-id="ea91c-127">Fare **clic** su Aggiungi nella parte inferiore della pagina a comparsa Nuove posizioni **dati non** di custodia per aggiungere le origini dati al caso.</span><span class="sxs-lookup"><span data-stu-id="ea91c-127">Click **Add** at the bottom of the **New non-custodial data locations** flyout page to add the data sources to the case.</span></span>

   <span data-ttu-id="ea91c-128">Ogni origine dati non depositale aggiunta viene elencata nella **pagina Origini** dati.</span><span class="sxs-lookup"><span data-stu-id="ea91c-128">Each non-custodial data source that you added is listed on the **Data sources** page.</span></span> <span data-ttu-id="ea91c-129">Le origini dati non di tipo depositario sono identificate dal **valore Percorso** dati nella colonna **Tipo di** origine.</span><span class="sxs-lookup"><span data-stu-id="ea91c-129">Non-custodial data sources are identified by the **Data location** value in the **Source type** column.</span></span>

   ![Origini dati non di tipo depositario nella scheda Origini dati](../media/NonCustodialDataSources2.png)

<span data-ttu-id="ea91c-131">Dopo aver aggiunto origini dati non di custodia al caso, viene creato e visualizzato nella  scheda Processi del caso un processo denominato Reindicizzazione dei dati *non* di custodia.</span><span class="sxs-lookup"><span data-stu-id="ea91c-131">After you add non-custodial data sources to the case, a job named *Reindexing non-custodial data* is created and displayed on the **Jobs** tab of the case.</span></span> <span data-ttu-id="ea91c-132">Dopo la creazione del processo, il processo di indicizzazione avanzato viene avviato e le origini dati vengono reindicizzare.</span><span class="sxs-lookup"><span data-stu-id="ea91c-132">After the job is created, the Advanced indexing process in initiated and the data sources are reindexed.</span></span>

## <a name="manage-the-hold-for-non-custodial-data-sources"></a><span data-ttu-id="ea91c-133">Gestire il blocco per le origini dati non di custodia</span><span class="sxs-lookup"><span data-stu-id="ea91c-133">Manage the hold for non-custodial data sources</span></span>

<span data-ttu-id="ea91c-134">Dopo aver posto un'esenzione su un'origine dati non depositale, viene creato automaticamente un criterio di conservazione contenente le origini dati non di custodia per il caso.</span><span class="sxs-lookup"><span data-stu-id="ea91c-134">After you place a hold on a non-custodial data source, a hold policy that contains the non-custodial data sources for the case is automatically created.</span></span> <span data-ttu-id="ea91c-135">Quando si posizionano in attesa altre origini dati non di custodia, queste vengono aggiunte a questo criterio di conservazione.</span><span class="sxs-lookup"><span data-stu-id="ea91c-135">When you place other non-custodial data sources on hold, they are added to this hold policy.</span></span>

1. <span data-ttu-id="ea91c-136">Aprire il Advanced eDiscovery e selezionare la **scheda Esenzione.**</span><span class="sxs-lookup"><span data-stu-id="ea91c-136">Open the Advanced eDiscovery case and select the **Hold** tab.</span></span>

2. <span data-ttu-id="ea91c-137">Fare **clic su \<GUID\> NCDSHold-**, dove il valore GUID è univoco per il caso.</span><span class="sxs-lookup"><span data-stu-id="ea91c-137">Click **NCDSHold-\<GUID\>**, where the GUID value is unique to the case.</span></span>

   <span data-ttu-id="ea91c-138">Nella pagina a comparsa vengono visualizzate informazioni e statistiche sulle origini dati non riservate in attesa.</span><span class="sxs-lookup"><span data-stu-id="ea91c-138">The flyout page display information and statistics about the non-custodial data sources on hold.</span></span>

   ![La pagina a comparsa per il blocco di origini dati non di tipo depositario visualizza le statistiche](../media/NonCustodialDataSourcesHoldFlyout.png)

3. <span data-ttu-id="ea91c-140">Fare **clic su Modifica** esenzione per visualizzare le origini dati non di custodia poste in attesa ed eseguire le attività di gestione seguenti:</span><span class="sxs-lookup"><span data-stu-id="ea91c-140">Click **Edit hold** to view the non-custodial data sources placed on hold and perform the following management tasks:</span></span>

   - <span data-ttu-id="ea91c-141">Nella pagina **Posizioni** è possibile rilasciare un'origine dati non depositale rimuovendo l'origine dall'esenzione.</span><span class="sxs-lookup"><span data-stu-id="ea91c-141">On the **Locations** page, you can release a non-custodial data source by removing it from the hold.</span></span> <span data-ttu-id="ea91c-142">Il rilascio di un'origine dati non rimuove l'origine dati non depositale dal caso.</span><span class="sxs-lookup"><span data-stu-id="ea91c-142">Releasing a data source doesn't remove the non-custodial data source from the case.</span></span> <span data-ttu-id="ea91c-143">Rimuove solo l'esenzione che è stata inserita nell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="ea91c-143">It only removes the hold that was placed on the data source.</span></span>

   - <span data-ttu-id="ea91c-144">Nella pagina **Query** è possibile modificare l'esenzione per creare un'esenzione basata su query applicata a tutte le origini dati non di tipo non depositario nel caso.</span><span class="sxs-lookup"><span data-stu-id="ea91c-144">On the **Query** page, you can edit the hold to create a query-based hold that is applied to all tha non-custodial data sources in the case.</span></span>
