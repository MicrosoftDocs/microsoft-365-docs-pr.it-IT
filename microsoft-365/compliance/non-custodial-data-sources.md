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
description: È possibile aggiungere origini dati non detentive a un caso di eDiscovery avanzato e inserire un'esenzione nell'origine dati. Le origini dati non detentive vengono reindicizzate, pertanto qualsiasi contenuto ritenuto parzialmente indicizzato viene rielaborato per renderlo completamente e rapidamente ricercabile.
ms.openlocfilehash: 2009a8cc82dc9407e9871409e85cdcd321ea9bb0
ms.sourcegitcommit: 51a9f34796535309b8ca8b52da92da0a3621327b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2020
ms.locfileid: "45024746"
---
# <a name="add-non-custodial-data-sources-to-an-advanced-ediscovery-case"></a><span data-ttu-id="5c539-104">Aggiungere origini dati non detentive a un caso avanzato di eDiscovery</span><span class="sxs-lookup"><span data-stu-id="5c539-104">Add non-custodial data sources to an Advanced eDiscovery case</span></span>

<span data-ttu-id="5c539-105">In Advanced eDiscovery casi, non sempre soddisfare le proprie esigenze per associare un'origine dati Microsoft 365 con un custode nel caso.</span><span class="sxs-lookup"><span data-stu-id="5c539-105">In Advanced eDiscovery cases, it doesn't always meet your needs to associate a Microsoft 365 data source with a custodian in the case.</span></span> <span data-ttu-id="5c539-106">Tuttavia, potrebbe essere necessario associare tali dati a un caso in modo che sia possibile cercarlo, aggiungerlo al set di revisione e rivederlo.</span><span class="sxs-lookup"><span data-stu-id="5c539-106">But you may still need to associate that data with a case so that you search it, add it to review set, and review it.</span></span> <span data-ttu-id="5c539-107">La nuova funzionalità denominata *origini dati non detentive* consente di aggiungere dati a un caso senza dover associare i dati a un custode.</span><span class="sxs-lookup"><span data-stu-id="5c539-107">The new feature called *non-custodial data sources* lets you add data to a case without having to associate the data to a custodian.</span></span> <span data-ttu-id="5c539-108">Applica inoltre la stessa funzionalità avanzata di eDiscovery ai dati non detentivi disponibili per i dati associati al custode.</span><span class="sxs-lookup"><span data-stu-id="5c539-108">It also applies the same Advanced eDiscovery functionality to non-custodial data that's available for data associated with custodian.</span></span> <span data-ttu-id="5c539-109">Due delle funzionalità più utili che è possibile applicare ai dati non detentivi sono l'inserimento e l'elaborazione in attesa tramite l' [indicizzazione avanzata](indexing-custodian-data.md).</span><span class="sxs-lookup"><span data-stu-id="5c539-109">Two of the most useful features that you can apply to non-custodial data is placing it on hold and processing it using [Advanced indexing](indexing-custodian-data.md).</span></span>

## <a name="add-a-non-custodial-data-source"></a><span data-ttu-id="5c539-110">Aggiunta di un'origine dati non priva di detenzione</span><span class="sxs-lookup"><span data-stu-id="5c539-110">Add a non-custodial data source</span></span>

<span data-ttu-id="5c539-111">Eseguire la procedura seguente per aggiungere e gestire origini dati non detentive in un caso di eDiscovery avanzato.</span><span class="sxs-lookup"><span data-stu-id="5c539-111">Follow these steps to add and manage non-custodial data sources in an Advanced eDiscovery case.</span></span>

1. <span data-ttu-id="5c539-112">Nella Home page di **Advanced eDiscovery** fare clic sul caso per il quale si desidera aggiungere i dati.</span><span class="sxs-lookup"><span data-stu-id="5c539-112">On the **Advanced eDiscovery** home page, click the case that you want to add the data to.</span></span>

2. <span data-ttu-id="5c539-113">Nella pagina **origini** fare clic sulla scheda **percorsi dati** e quindi fare clic su **Aggiungi percorso dati**.</span><span class="sxs-lookup"><span data-stu-id="5c539-113">On the **Sources** page, click the **Data locations** tab, and then click **Add data location**.</span></span>

3. <span data-ttu-id="5c539-114">Fare clic su **Aggiungi percorso dati** e scegliere le origini dati che si desidera aggiungere al caso.</span><span class="sxs-lookup"><span data-stu-id="5c539-114">Click **Add data location** and choose the data sources that you want to add to the case.</span></span> <span data-ttu-id="5c539-115">È possibile aggiungere più cassette postali e siti.</span><span class="sxs-lookup"><span data-stu-id="5c539-115">You can add multiple mailboxes and sites.</span></span>

4. <span data-ttu-id="5c539-116">Nella pagina **scegliere i percorsi** della procedura guidata, aggiungere le cassette postali o i siti (o entrambi) come origini dati non detentive al caso.</span><span class="sxs-lookup"><span data-stu-id="5c539-116">On the **Choose locations** page in the wizard, add mailboxes or sites (or both) as non-custodial data sources to the case.</span></span>

5. <span data-ttu-id="5c539-117">Dopo aver aggiunto le origini dati, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="5c539-117">After adding the data sources, click **Next**.</span></span>

6. <span data-ttu-id="5c539-118">Nella pagina **Place** holds scegliere le origini dati che si desidera inserire in attesa selezionando o deselezionando la casella di controllo associata.</span><span class="sxs-lookup"><span data-stu-id="5c539-118">On the **Place holds** page, choose which data sources you want to place on hold by selecting or unselecting the associated checkbox.</span></span>

7. <span data-ttu-id="5c539-119">Verificare le selezioni di blocco e quindi fare clic su **Invia**.</span><span class="sxs-lookup"><span data-stu-id="5c539-119">Verify the hold selections and then click **Submit**.</span></span>

   <span data-ttu-id="5c539-120">Ogni origine dati non priva di detenzione aggiunta è elencata nella pagina **origini dati** .</span><span class="sxs-lookup"><span data-stu-id="5c539-120">Each non-custodial data source that you added is listed on the **Data sources** page.</span></span>

   <span data-ttu-id="5c539-121">Inoltre, un processo denominato *reindicizzazione dei dati non detentivi* viene creato e visualizzato nella scheda **processi** del caso.</span><span class="sxs-lookup"><span data-stu-id="5c539-121">Also, a job named *Reindexing non-custodial data* is created and displayed on the **Jobs** tab of the case.</span></span> <span data-ttu-id="5c539-122">Una volta creato, il processo di indicizzazione avanzato è stato avviato e le origini dati vengono reindicizzate.</span><span class="sxs-lookup"><span data-stu-id="5c539-122">After the job is created, the Advanced indexing process in initiated and the data sources are reindexed.</span></span>

## <a name="managing-the-hold-on-non-custodial-data-sources"></a><span data-ttu-id="5c539-123">Gestione del blocco su origini dati non detentive</span><span class="sxs-lookup"><span data-stu-id="5c539-123">Managing the hold on non-custodial data sources</span></span>

<span data-ttu-id="5c539-124">Dopo aver posizionato un'esenzione su un'origine dati non di detenzione, viene creato automaticamente un criterio di conservazione che contiene tutte le origini dati non detentive del caso.</span><span class="sxs-lookup"><span data-stu-id="5c539-124">After you place a hold on a non-custodial data source, a hold policy that contains all non-custodial data sources for the case is automatically created.</span></span> <span data-ttu-id="5c539-125">Quando si impostano altre origini dati non detentive, queste vengono aggiunte ai criteri di blocco.</span><span class="sxs-lookup"><span data-stu-id="5c539-125">When you place additional non-custodial data sources on hold, they are added to this hold policy.</span></span>

1. <span data-ttu-id="5c539-126">Nella **Home** page del caso, fare clic sulla scheda **esenzioni** .</span><span class="sxs-lookup"><span data-stu-id="5c539-126">On the **Home** page of the case, click the **Holds** tab.</span></span>

2. <span data-ttu-id="5c539-127">Nella pagina **esenzioni** e fare clic su **NCDSHold \<GUID\> -**, in cui il valore GUID è univoco per il caso.</span><span class="sxs-lookup"><span data-stu-id="5c539-127">On the **Holds** page, and click **NCDSHold-\<GUID\>**, where the GUID value is unique to the case.</span></span>

3. <span data-ttu-id="5c539-128">Nella pagina a comparsa fare clic su **Modifica blocco** per visualizzare tutte le origini dati non detentive che sono state inserite in attesa.</span><span class="sxs-lookup"><span data-stu-id="5c539-128">On the flyout page, click **Edit hold** to view all the non-custodial data sources that are placed on hold.</span></span>

<span data-ttu-id="5c539-129">È possibile eseguire le seguenti attività di gestione su origini dati non detentive:</span><span class="sxs-lookup"><span data-stu-id="5c539-129">You can perform the following management task on non-custodial data sources:</span></span>

- <span data-ttu-id="5c539-130">È possibile modificare il blocco per creare un blocco basato su query applicato a tutte le origini dati non detentive nel caso.</span><span class="sxs-lookup"><span data-stu-id="5c539-130">You can edit the hold to create a query-based hold that is applied to all non-custodial data sources in the case.</span></span>

- <span data-ttu-id="5c539-131">È possibile rilasciare un'origine dati non detentiva dall'esenzione.</span><span class="sxs-lookup"><span data-stu-id="5c539-131">You can release a non-custodial data source from the hold.</span></span> <span data-ttu-id="5c539-132">Il rilascio di un'origine dati non rimuove l'origine dati non affidatario dal caso.</span><span class="sxs-lookup"><span data-stu-id="5c539-132">Releasing a data source doesn't remove the non-custodial data source from the case.</span></span> <span data-ttu-id="5c539-133">Rimuove solo il blocco che è stato inserito nell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="5c539-133">It only removes the hold that was placed on the data source.</span></span>
