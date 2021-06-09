---
title: Gestire l'individuazione degli argomenti in Microsoft Viva Topics
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: Informazioni su come amministrare l'individuazione degli argomenti in Microsoft Viva Topics.
ms.openlocfilehash: 53e304dc69ccf2ca6fe01d29f0997c539406b0fe
ms.sourcegitcommit: 4acf613587128cae27e0fd470d1216b509775529
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/15/2021
ms.locfileid: "51768975"
---
# <a name="manage-topic-discovery-in-microsoft-viva-topics"></a><span data-ttu-id="fa107-103">Gestire l'individuazione degli argomenti in Microsoft Viva Topics</span><span class="sxs-lookup"><span data-stu-id="fa107-103">Manage topic discovery in Microsoft Viva Topics</span></span>

<span data-ttu-id="fa107-104">È possibile gestire le impostazioni di individuazione degli argomenti [nell'Microsoft 365 di amministrazione.](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="fa107-104">You can manage topic discovery settings in the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span> <span data-ttu-id="fa107-105">Per eseguire queste attività, è SharePoint amministratore globale o amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="fa107-105">You must be a global administrator or SharePoint administrator to perform these tasks.</span></span>

## <a name="to-access-topics-management-settings"></a><span data-ttu-id="fa107-106">Per accedere alle impostazioni di gestione degli argomenti:</span><span class="sxs-lookup"><span data-stu-id="fa107-106">To access topics management settings:</span></span>

1. <span data-ttu-id="fa107-107">Nell'Microsoft 365 di amministrazione fare clic su **Impostazioni** e quindi **su Impostazioni organizzazione.**</span><span class="sxs-lookup"><span data-stu-id="fa107-107">In the Microsoft 365 admin center, click **Settings**, then **Org settings**.</span></span>
2. <span data-ttu-id="fa107-108">Nella scheda **Servizi** fare clic su **Esperienze argomento.**</span><span class="sxs-lookup"><span data-stu-id="fa107-108">On the **Services** tab, click **Topic experiences**.</span></span>

    ![Connessione persone alla conoscenza](../media/admin-org-knowledge-options-completed.png) 

3. <span data-ttu-id="fa107-110">Selezionare la **scheda Individuazione** argomenti. Per informazioni su ogni impostazione, vedere le sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="fa107-110">Select the **Topic discovery** tab. See the following sections for information about each setting.</span></span>

    ![knowledge-network-settings](../media/knowledge-network-settings-topic-discovery.png) 

## <a name="select-sharepoint-topic-sources"></a><span data-ttu-id="fa107-112">Selezionare SharePoint'argomento</span><span class="sxs-lookup"><span data-stu-id="fa107-112">Select SharePoint topic sources</span></span>

<span data-ttu-id="fa107-113">È possibile modificare i siti SharePoint dell'organizzazione che verranno sottoposti a ricerca per indicizzazione per gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="fa107-113">You can change the SharePoint sites in your organization that will be crawled for topics.</span></span>

<span data-ttu-id="fa107-114">Se si desidera includere o escludere un elenco specifico di siti, è possibile utilizzare il modello di .csv seguente:</span><span class="sxs-lookup"><span data-stu-id="fa107-114">If you want to include or exclude a specific list of sites, you can use the following .csv template:</span></span>

``` csv
Site name,URL
```

<span data-ttu-id="fa107-115">Se si aggiungono siti con Selezione sito, questi vengono aggiunti all’elenco di siti esistenti da includere o escludere.</span><span class="sxs-lookup"><span data-stu-id="fa107-115">If you add sites using the site picker, they are added to the existing list of sites to include or exclude.</span></span> <span data-ttu-id="fa107-116">Se si carica un file .csv, viene sovrascritto qualsiasi elenco esistente.</span><span class="sxs-lookup"><span data-stu-id="fa107-116">If you upload a .csv file, it overwrites any existing list.</span></span> <span data-ttu-id="fa107-117">Se in precedenza sono stati inclusi o esclusi siti specifici, è possibile scaricare l'elenco come file .csv, apportare modifiche e caricare il nuovo elenco.</span><span class="sxs-lookup"><span data-stu-id="fa107-117">If you have previously included or excluded specific sites, you and download the list as a .csv file, make changes, and upload the new list.</span></span>

<span data-ttu-id="fa107-118">Per scegliere i siti per l'individuazione degli argomenti</span><span class="sxs-lookup"><span data-stu-id="fa107-118">To choose sites for topic discovery</span></span>

1. <span data-ttu-id="fa107-119">Nella scheda **Individuazione argomenti**, in **Selezionare origini argomenti di SharePoint**, selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="fa107-119">On the **Topic discovery** tab, under **Select SharePoint topic sources**, select **Edit**.</span></span>
2. <span data-ttu-id="fa107-120">Nella pagina **Seleziona SharePoint di** argomenti selezionare quali siti SharePoint verranno sottoposti a ricerca per indicizzazione come origini per gli argomenti durante l'individuazione.</span><span class="sxs-lookup"><span data-stu-id="fa107-120">On the **Select SharePoint topic sources** page, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="fa107-121">Tra questi vi sono anche:</span><span class="sxs-lookup"><span data-stu-id="fa107-121">This includes:</span></span>
    - <span data-ttu-id="fa107-122">**Tutti i siti**: tutti SharePoint siti nel tenant.</span><span class="sxs-lookup"><span data-stu-id="fa107-122">**All sites**: All SharePoint sites in your tenant.</span></span> <span data-ttu-id="fa107-123">In questo modo vengono catturati i siti correnti e futuri.</span><span class="sxs-lookup"><span data-stu-id="fa107-123">This captures current and future sites.</span></span>
    - <span data-ttu-id="fa107-124">**Tutti, ad eccezione dei siti** selezionati: digitare i nomi dei siti che si desidera escludere.</span><span class="sxs-lookup"><span data-stu-id="fa107-124">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="fa107-125">È inoltre possibile caricare un elenco di siti che si desidera rifiutare esplicitamente dall'individuazione.</span><span class="sxs-lookup"><span data-stu-id="fa107-125">You can also upload a list of sites you want to opt out from discovery.</span></span> <span data-ttu-id="fa107-126">I siti creati in futuro verranno inclusi come origini per l’individuazione di argomenti.</span><span class="sxs-lookup"><span data-stu-id="fa107-126">Sites created in the future will be included as sources for topic discovery.</span></span> 
    - <span data-ttu-id="fa107-127">**Solo siti selezionati:** digitare i nomi dei siti che si desidera includere.</span><span class="sxs-lookup"><span data-stu-id="fa107-127">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="fa107-128">È inoltre possibile caricare un elenco di siti.</span><span class="sxs-lookup"><span data-stu-id="fa107-128">You can also upload a list of sites.</span></span> <span data-ttu-id="fa107-129">I siti creati in futuro non verranno inclusi come origini per l’individuazione di argomenti.</span><span class="sxs-lookup"><span data-stu-id="fa107-129">Sites created in the future will not be included as sources for topic discovery.</span></span>
    - <span data-ttu-id="fa107-130">**Nessun sito:** gli argomenti non verranno generati o aggiornati automaticamente con SharePoint contenuto.</span><span class="sxs-lookup"><span data-stu-id="fa107-130">**No sites**: Topics won't be automatically generated or updated with SharePoint content.</span></span> <span data-ttu-id="fa107-131">Gli argomenti esistenti rimangono nel Centro argomenti.</span><span class="sxs-lookup"><span data-stu-id="fa107-131">Existing topics remain in the topic center.</span></span>

    ![Screenshot dell'interfaccia SharePoint'interfaccia utente delle origini degli argomenti](../media/k-manage-select-topic-source.png)
   
3. <span data-ttu-id="fa107-133">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="fa107-133">Click **Save**.</span></span>

## <a name="exclude-topics-by-name"></a><span data-ttu-id="fa107-134">Escludere gli argomenti per nome</span><span class="sxs-lookup"><span data-stu-id="fa107-134">Exclude topics by name</span></span>

<span data-ttu-id="fa107-135">È possibile escludere gli argomenti dall’individuazione caricando un elenco usando un file .csv.</span><span class="sxs-lookup"><span data-stu-id="fa107-135">You can exclude topics from discovery by uploading a list using a .csv file.</span></span> <span data-ttu-id="fa107-136">Se in precedenza sono stati esclusi alcuni argomenti, è possibile scaricare il file .csv, apportare modifiche e caricarlo di nuovo.</span><span class="sxs-lookup"><span data-stu-id="fa107-136">If you've previously excluded topics, you can download the .csv, make changes, and upload it again.</span></span>

1. <span data-ttu-id="fa107-137">Nella scheda **Individuazione argomenti**, in **Escludi**, selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="fa107-137">On the **Topic discovery** tab, under **Exclude topics**, select **Edit**.</span></span>
2. <span data-ttu-id="fa107-138">Fare **clic su Escludi argomenti per nome.**</span><span class="sxs-lookup"><span data-stu-id="fa107-138">Click **Exclude topics by name**.</span></span>
3. <span data-ttu-id="fa107-139">Se è necessario creare un elenco, scaricare il modello di .csv e aggiungere gli argomenti che si desidera escludere (vedere Utilizzo del modello di .csv *seguente).*</span><span class="sxs-lookup"><span data-stu-id="fa107-139">If you need to create a list, download the .csv template and add the topics that you want to exclude (see *Working with the .csv template* below).</span></span> <span data-ttu-id="fa107-140">Quando il file è pronto, fare clic **su Sfoglia** e caricare il file.</span><span class="sxs-lookup"><span data-stu-id="fa107-140">When the file is ready, click **Browse** and upload the file.</span></span> <span data-ttu-id="fa107-141">Se è presente un elenco esistente, è possibile scaricare il .csv contenente l'elenco.</span><span class="sxs-lookup"><span data-stu-id="fa107-141">If there's an existing list, you can download the .csv containing the list.</span></span>
4. <span data-ttu-id="fa107-142">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="fa107-142">Click **Save**.</span></span>

    ![Screenshot dell'interfaccia utente degli argomenti di esclusione](../media/km-manage-exclude-topics.png)

### <a name="working-with-the-csv-template"></a><span data-ttu-id="fa107-144">Utilizzo del modello .csv</span><span class="sxs-lookup"><span data-stu-id="fa107-144">Working with the .csv template</span></span>

<span data-ttu-id="fa107-145">È possibile copiare il modello csv seguente:</span><span class="sxs-lookup"><span data-stu-id="fa107-145">You can copy the csv template below:</span></span>

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

<span data-ttu-id="fa107-146">Nel modello CSV immettere le informazioni seguenti sugli argomenti da escludere:</span><span class="sxs-lookup"><span data-stu-id="fa107-146">In the CSV template, enter the following information about the topics you want to exclude:</span></span>

- <span data-ttu-id="fa107-147">**Nome**: digitare il nome dell’argomento da escludere.</span><span class="sxs-lookup"><span data-stu-id="fa107-147">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="fa107-148">È possibile eseguire questa operazione in due modi:</span><span class="sxs-lookup"><span data-stu-id="fa107-148">There are two ways to do this:</span></span>
    - <span data-ttu-id="fa107-149">Corrispondenza esatta: è possibile escludere il nome esatto o l'acronimo (ad esempio, *Contoso* o *ATL).*</span><span class="sxs-lookup"><span data-stu-id="fa107-149">Exact match: You can exclude the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
    - <span data-ttu-id="fa107-150">Corrispondenza parziale: è possibile escludere tutti gli argomenti che includono una parola specifica.</span><span class="sxs-lookup"><span data-stu-id="fa107-150">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="fa107-151">Ad esempio, *arco* escluderà tutti gli argomenti con la parola arco *al* suo interno, ad esempio Cerchio *arco,* *Saldatura* arco di plasma o *Arco di formazione.* Si noti che non verranno esclusi gli argomenti in cui il testo è incluso come parte di una parola, ad esempio *Architettura*.</span><span class="sxs-lookup"><span data-stu-id="fa107-151">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
- <span data-ttu-id="fa107-152">**Sta per (facoltativo):** se si desidera escludere un acronimo, digitare le parole che l'acronimo sta per.</span><span class="sxs-lookup"><span data-stu-id="fa107-152">**Stands for (optional)**: If you want to exclude an acronym, type the words the acronym stands for.</span></span>
- <span data-ttu-id="fa107-153">**MatchType-Exact/Partial**: Digitare se il nome immesso è un *tipo* di corrispondenza esatto *o* parziale.</span><span class="sxs-lookup"><span data-stu-id="fa107-153">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>

    ![Escludere gli argomenti nel modello CSV](../media/exclude-topics-csv.png) 

## <a name="see-also"></a><span data-ttu-id="fa107-155">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fa107-155">See also</span></span>

[<span data-ttu-id="fa107-156">Gestire la visibilità degli argomenti in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fa107-156">Manage topic visibility in Microsoft 365</span></span>](topic-experiences-knowledge-rules.md)

[<span data-ttu-id="fa107-157">Gestire le autorizzazioni per gli argomenti in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fa107-157">Manage topic permissions in Microsoft 365</span></span>](topic-experiences-user-permissions.md)

[<span data-ttu-id="fa107-158">Modificare il nome del centro argomenti in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fa107-158">Change the name of the topic center in Microsoft 365</span></span>](topic-experiences-administration.md)
