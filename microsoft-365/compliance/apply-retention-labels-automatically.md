---
title: Applicare automaticamente un'etichetta di conservazione per conservare o eliminare il contenuto
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Creare e pubblicare automaticamente etichette di conservazione in modo da poter applicare automaticamente etichette per conservare ciò che serve ed eliminare ciò che non serve
ms.openlocfilehash: 7528fed52ae3df1a60303c40df35a42de6bc1f31
ms.sourcegitcommit: 19515d787246d38c4e0da579a767ce67b9dbc2bc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2020
ms.locfileid: "47315817"
---
# <a name="automatically-apply-a-retention-label-to-retain-or-delete-content"></a><span data-ttu-id="b7846-103">Applicare automaticamente un'etichetta di conservazione per conservare o eliminare il contenuto</span><span class="sxs-lookup"><span data-stu-id="b7846-103">Automatically apply a retention label to retain or delete content</span></span>

><span data-ttu-id="b7846-104">*[Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="b7846-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="b7846-105">Una delle funzionalità più efficaci delle [etichette di conservazione](retention.md) è la possibilità di applicarle automaticamente al contenuto che soddisfa condizioni specificate.</span><span class="sxs-lookup"><span data-stu-id="b7846-105">One of the most powerful features of [retention labels](retention.md) is the ability to apply them automatically to content that matches specified conditions.</span></span> <span data-ttu-id="b7846-106">In questo caso, gli utenti dell'organizzazione non dovranno applicare le etichette di conservazione.</span><span class="sxs-lookup"><span data-stu-id="b7846-106">In this case, people in your organization don't need to apply the retention labels.</span></span> <span data-ttu-id="b7846-107">Microsoft 365 lo farà automaticamente.</span><span class="sxs-lookup"><span data-stu-id="b7846-107">Microsoft 365 does the work for them.</span></span>
  
<span data-ttu-id="b7846-108">Le etichette di conservazione applicate automaticamente sono potenti perché:</span><span class="sxs-lookup"><span data-stu-id="b7846-108">Auto-applying retention labels are powerful because:</span></span>
  
- <span data-ttu-id="b7846-109">Non è necessario formare gli utenti su tutte le classificazioni.</span><span class="sxs-lookup"><span data-stu-id="b7846-109">You don't need to train your users on all of your classifications.</span></span>
    
- <span data-ttu-id="b7846-110">Non è necessario affidarsi solo agli utenti per la classificazione corretta di tutto il contenuto.</span><span class="sxs-lookup"><span data-stu-id="b7846-110">You don't need to rely on users to classify all content correctly.</span></span>
    
- <span data-ttu-id="b7846-111">Gli utenti non hanno più bisogno di conoscere i criteri di governance dai dati e possono concentrarsi sul loro lavoro.</span><span class="sxs-lookup"><span data-stu-id="b7846-111">Users no longer need to know about data governance policies - they can focus on their work.</span></span>
    
<span data-ttu-id="b7846-112">È possibile applicare automaticamente etichette di conservazione al contenuto quando questo include informazioni sensibili, parole chiave, proprietà disponibili per la ricerca o una corrispondenza per [classificatori sottoponibili a training](classifier-getting-started-with.md).</span><span class="sxs-lookup"><span data-stu-id="b7846-112">You can apply retention labels to content automatically when that content contains sensitive information, keywords or searchable properties, or a match for [trainable classifiers](classifier-getting-started-with.md).</span></span>

<span data-ttu-id="b7846-113">I processi per l'applicazione automatica di un'etichetta di conservazione si basano sulle condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b7846-113">The processes to automatically apply a retention label based on these conditions:</span></span>

![Diagramma di ruoli e attività per le etichette applicate automaticamente](../media/32f2f2fd-18a8-43fd-839d-72ad7a43e069.png)

<span data-ttu-id="b7846-115">Usare le istruzioni seguenti per i due passaggi per l'amministratore.</span><span class="sxs-lookup"><span data-stu-id="b7846-115">Use the following instructions for the two admin steps.</span></span>

> [!NOTE]
> <span data-ttu-id="b7846-116">I criteri di applicazione automatica usano l'etichettatura sul lato servizio con condizioni per applicare automaticamente etichette di conservazione.</span><span class="sxs-lookup"><span data-stu-id="b7846-116">Auto-policies use service-side labeling with conditions to automatically apply retention labels.</span></span> <span data-ttu-id="b7846-117">È anche possibile applicare automaticamente un'etichetta di conservazione con un criterio di etichetta eseguendo le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b7846-117">You can also automatically apply a retention label with a label policy when you do the following:</span></span> 
>
> - <span data-ttu-id="b7846-118">Applicare un'etichetta di conservazione predefinita a un set di documenti, una cartella o una raccolta di SharePoint in modo che il contenuto non etichettato presente nel contenitore venga etichettato automaticamente</span><span class="sxs-lookup"><span data-stu-id="b7846-118">Apply a default retention label to a SharePoint library, folder, or document set so that unlabeled content in that container is automatically labeled</span></span>
>- <span data-ttu-id="b7846-119">Applicazione automatica di un'etichetta di conservazione alla posta elettronica mediante regole</span><span class="sxs-lookup"><span data-stu-id="b7846-119">Automatically applying a retention label to email by using rules</span></span>
>
> <span data-ttu-id="b7846-120">Per questi scenari, vedere [Creare e applicare etichette di conservazione nelle app](create-apply-retention-labels.md).</span><span class="sxs-lookup"><span data-stu-id="b7846-120">For these scenarios, see [Create and apply retention labels in apps](create-apply-retention-labels.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="b7846-121">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="b7846-121">Before you begin</span></span>

<span data-ttu-id="b7846-122">L'amministratore globale dell'organizzazione dispone delle autorizzazioni complete per creare e modificare le etichette conservazione e i relativi criteri.</span><span class="sxs-lookup"><span data-stu-id="b7846-122">The global admin for your organization has full permissions to create and edit retention labels and their policies.</span></span> <span data-ttu-id="b7846-123">Se non si esegue l'accesso come amministratore globale, vedere le [autorizzazioni necessarie per creare e gestire criteri di conservazione ed etichette di conservazione](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels).</span><span class="sxs-lookup"><span data-stu-id="b7846-123">If you aren't signing in as a global admin, see [Permissions required to create and manage retention policies and retention labels](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels).</span></span>

## <a name="how-to-auto-apply-a-retention-label"></a><span data-ttu-id="b7846-124">Come applicare automaticamente un'etichetta di conservazione</span><span class="sxs-lookup"><span data-stu-id="b7846-124">How to auto-apply a retention label</span></span>

<span data-ttu-id="b7846-125">Creare prima di tutto l'etichetta di conservazione.</span><span class="sxs-lookup"><span data-stu-id="b7846-125">First, create your retention label.</span></span> <span data-ttu-id="b7846-126">Quindi, creare un criterio automatico per applicare l'etichetta.</span><span class="sxs-lookup"><span data-stu-id="b7846-126">Then create an auto-policy to apply that label.</span></span> <span data-ttu-id="b7846-127">Se è già stata creata l'etichetta di conservazione, passare a [Creare un criterio di applicazione automatica](#step-2-create-an-auto-apply-policy).</span><span class="sxs-lookup"><span data-stu-id="b7846-127">If you have already created your retention label, skip to [creating an auto-policy](#step-2-create-an-auto-apply-policy).</span></span>

<span data-ttu-id="b7846-128">Le istruzioni di spostamento variano a seconda che si usi o meno la [gestione dei record](records-management.md).</span><span class="sxs-lookup"><span data-stu-id="b7846-128">Navigation instructions depend on whether you're using [records management](records-management.md) or not.</span></span> <span data-ttu-id="b7846-129">Sono disponibili istruzioni per entrambi gli scenari.</span><span class="sxs-lookup"><span data-stu-id="b7846-129">Instructions are provided for both scenarios.</span></span>

### <a name="step-1-create-a-retention-label"></a><span data-ttu-id="b7846-130">Passaggio 1: Creare un'etichetta di conservazione</span><span class="sxs-lookup"><span data-stu-id="b7846-130">Step 1: Create a retention label</span></span>

1. <span data-ttu-id="b7846-131">Nel [Centro conformità Microsoft 365](https://compliance.microsoft.com/) passare a una delle posizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b7846-131">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="b7846-132">Se si usa la gestione dei record:</span><span class="sxs-lookup"><span data-stu-id="b7846-132">If you are using records management:</span></span>
        - <span data-ttu-id="b7846-133">**Soluzioni** > **Records management** > scheda **Piano di archiviazione** > **+ Crea un'etichetta** > **Etichetta di conservazione**</span><span class="sxs-lookup"><span data-stu-id="b7846-133">**Solutions** > **Records management** > **File plan** tab > **+ Create a label** > **Retention label**</span></span>
        
    - <span data-ttu-id="b7846-134">Se non si usa la gestione dei record:</span><span class="sxs-lookup"><span data-stu-id="b7846-134">If you are not using records management:</span></span>
       - <span data-ttu-id="b7846-135">**Soluzioni** > **Governance delle informazioni** > scheda **Etichette** > + **Crea un'etichetta**</span><span class="sxs-lookup"><span data-stu-id="b7846-135">**Solutions** > **Information governance** > **Labels** tab > + **Create a label**</span></span>
    
    <span data-ttu-id="b7846-136">L'opzione non è immediatamente visibile?</span><span class="sxs-lookup"><span data-stu-id="b7846-136">Don't immediately see your option?</span></span> <span data-ttu-id="b7846-137">Selezionare per prima cosa **Mostra tutto**.</span><span class="sxs-lookup"><span data-stu-id="b7846-137">First select **Show all**.</span></span> 

2. <span data-ttu-id="b7846-138">Seguire le istruzioni della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="b7846-138">Follow the prompts in the wizard.</span></span> <span data-ttu-id="b7846-139">Se si usa la gestione dei record:</span><span class="sxs-lookup"><span data-stu-id="b7846-139">If you are using records management:</span></span>
    
    - <span data-ttu-id="b7846-140">Per informazioni sui descrittori del piano di archiviazione, vedere [Usare il piano di archiviazione per gestire le etichette di conservazione](file-plan-manager.md).</span><span class="sxs-lookup"><span data-stu-id="b7846-140">For information about the file plan descriptors, see [Use file plan to manage retention labels](file-plan-manager.md)</span></span>
    
    - <span data-ttu-id="b7846-141">Per usare l'etichetta di conservazione per dichiarare il contenuto come record, attivare la casella di controllo **Usa l'etichetta per classificare il contenuto come "Record"**.</span><span class="sxs-lookup"><span data-stu-id="b7846-141">To use the retention label to declare content as a record, enable the checkbox **Use label to classify content as a "Record"**.</span></span>

<span data-ttu-id="b7846-142">Per modificare un'etichetta esistente, selezionarla e quindi selezionare **Modifica etichetta** per avviare la stessa procedura guidata che consente di modificare le descrizioni dell'etichetta e le [impostazioni idonee](#updating-retention-labels-and-their-policies) dal passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="b7846-142">To edit an existing label, select it, and then select **Edit label** to start the same wizard that lets you change the label descriptions and any [eligible settings](#updating-retention-labels-and-their-policies) from step 2.</span></span> <span data-ttu-id="b7846-143">In alternativa, selezionare una delle opzioni **Modifica** disponibili per passare direttamente alla pagina pertinente per eseguire l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="b7846-143">Alternatively, select any of the available **Edit** options to go directly to the relevant page to make your update.</span></span>


### <a name="step-2-create-an-auto-apply-policy"></a><span data-ttu-id="b7846-144">Passaggio 2: Creare un criterio di applicazione automatica</span><span class="sxs-lookup"><span data-stu-id="b7846-144">Step 2: Create an auto-apply policy</span></span>

<span data-ttu-id="b7846-145">Quando si crea un criterio di applicazione automatica, si seleziona un'etichetta di conservazione da applicare automaticamente al contenuto in base alle condizioni specificate.</span><span class="sxs-lookup"><span data-stu-id="b7846-145">When you create an auto-apply policy, you select a retention label to automatically apply to content, based on the conditions that you specify.</span></span>

1. <span data-ttu-id="b7846-146">Nel [Centro conformità Microsoft 365](https://compliance.microsoft.com/) passare a una delle posizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b7846-146">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="b7846-147">Se si usa la gestione dei record: **Governance delle informazioni**:</span><span class="sxs-lookup"><span data-stu-id="b7846-147">If you are using records management: **Information governance**:</span></span>
        - <span data-ttu-id="b7846-148">**Soluzioni** > **Gestione dei record** > scheda **Criteri delle etichette** > **Applica automaticamente le etichette**</span><span class="sxs-lookup"><span data-stu-id="b7846-148">**Solutions** > **Records management** > **Label policies** tab > **Auto-apply label**</span></span>
    
    - <span data-ttu-id="b7846-149">Se non si usa la gestione dei record:</span><span class="sxs-lookup"><span data-stu-id="b7846-149">If you are not using records management:</span></span>
        - <span data-ttu-id="b7846-150">**Soluzioni** > **Governance delle informazioni** > scheda **Criteri delle etichette** > **Applica automaticamente le etichette**</span><span class="sxs-lookup"><span data-stu-id="b7846-150">**Solutions** > **Information governance** > **Label policies** tab > **Auto-apply label**</span></span>
    
    <span data-ttu-id="b7846-151">L'opzione non è immediatamente visibile?</span><span class="sxs-lookup"><span data-stu-id="b7846-151">Don't immediately see your option?</span></span> <span data-ttu-id="b7846-152">Selezionare per prima cosa **Mostra tutto**.</span><span class="sxs-lookup"><span data-stu-id="b7846-152">First select **Show all**.</span></span> 

2. <span data-ttu-id="b7846-153">Seguire le istruzioni della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="b7846-153">Follow the prompts in the wizard.</span></span>
    
    <span data-ttu-id="b7846-154">Per informazioni su come configurare le condizioni per l'applicazione automatica dell'etichetta di conservazione, vedere la sezione [Configurare le condizioni per l'applicazione automatica delle etichette di conservazione](#configuring-conditions-for-auto-apply-retention-labels) in questa pagina.</span><span class="sxs-lookup"><span data-stu-id="b7846-154">For information about configuring the conditions that automatically apply the retention label, see the [Configuring conditions for auto-apply retention labels](#configuring-conditions-for-auto-apply-retention-labels) section on this page.</span></span>
    
    <span data-ttu-id="b7846-155">Per informazioni sulle posizioni supportate dalle etichette di conservazione, vedere la sezione [Etichette di conservazione e posizioni](retention.md#retention-label-policies-and-locations).</span><span class="sxs-lookup"><span data-stu-id="b7846-155">For information about the locations supported by retention labels, see the [Retention labels and locations](retention.md#retention-label-policies-and-locations) section.</span></span>

<span data-ttu-id="b7846-156">Per modificare un criterio di etichetta applicata automaticamente, selezionarlo e quindi selezionare **Modifica criteri** per avviare la stessa procedura guidata che consente di modificare la descrizione del criterio e le [impostazioni idonee](#updating-retention-labels-and-their-policies) dal passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="b7846-156">To edit an existing auto-apply label policy, select it, and then select **Edit policy** to start the same wizard that lets you change the policy description and any [eligible settings](#updating-retention-labels-and-their-policies) from step 2.</span></span> <span data-ttu-id="b7846-157">In alternativa, selezionare una delle opzioni **Modifica** disponibili per passare direttamente alla pagina pertinente per eseguire l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="b7846-157">Alternatively, select any of the available **Edit** options to go directly to the relevant page to make your update.</span></span>

### <a name="configuring-conditions-for-auto-apply-retention-labels"></a><span data-ttu-id="b7846-158">Configurare le condizioni per l'applicazione automatica delle etichette di conservazione</span><span class="sxs-lookup"><span data-stu-id="b7846-158">Configuring conditions for auto-apply retention labels</span></span>

<span data-ttu-id="b7846-159">È possibile applicare automaticamente etichette di conservazione al contenuto quando questo contiene:</span><span class="sxs-lookup"><span data-stu-id="b7846-159">You can apply retention labels to content automatically when that content contains:</span></span>

- [<span data-ttu-id="b7846-160">Tipi specifici di informazioni riservate.</span><span class="sxs-lookup"><span data-stu-id="b7846-160">Specific types of sensitive information</span></span>](#auto-apply-labels-to-content-with-specific-types-of-sensitive-information)

- [<span data-ttu-id="b7846-161">Parole chiave specifiche o proprietà disponibili per la ricerca che corrispondono a una query creata.</span><span class="sxs-lookup"><span data-stu-id="b7846-161">Specific keywords or searchable properties that match a query you create</span></span>](#auto-apply-labels-to-content-with-keywords-or-searchable-properties)

- [<span data-ttu-id="b7846-162">Una corrispondenza per classificatori sottoponibili a training</span><span class="sxs-lookup"><span data-stu-id="b7846-162">A match for trainable classifiers</span></span>](#auto-apply-labels-to-content-by-using-trainable-classifiers)

#### <a name="auto-apply-labels-to-content-with-specific-types-of-sensitive-information"></a><span data-ttu-id="b7846-163">Applicare automaticamente etichette al contenuto con tipi specifici di informazioni sensibili</span><span class="sxs-lookup"><span data-stu-id="b7846-163">Auto-apply labels to content with specific types of sensitive information</span></span>

<span data-ttu-id="b7846-164">Quando si creano etichette di conservazione ad applicazione automatica per le informazioni riservate, viene visualizzato lo stesso elenco di modelli di criteri mostrato quando si creano criteri di prevenzione della perdita dei dati (DLP).</span><span class="sxs-lookup"><span data-stu-id="b7846-164">When you create auto-apply retention labels for sensitive information, you see the same list of policy templates as when you create a data loss prevention (DLP) policy.</span></span> <span data-ttu-id="b7846-165">Ogni modello di criteri è preconfigurato in modo da cercare specifici tipi di informazioni riservate.</span><span class="sxs-lookup"><span data-stu-id="b7846-165">Each policy template is preconfigured to look for specific types of sensitive information.</span></span> <span data-ttu-id="b7846-166">Ad esempio, il modello illustrato di seguito cerca codici identificativi del singolo contribuente (ITIN), codici di previdenza sociale (SSN) e numeri di passaporto statunitensi.</span><span class="sxs-lookup"><span data-stu-id="b7846-166">For example, the template shown here looks for U.S. ITIN, SSN, and passport numbers.</span></span> <span data-ttu-id="b7846-167">Per altre informazioni sui criteri DLP, vedere [Panoramica dei criteri di prevenzione della perdita dei dati](data-loss-prevention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="b7846-167">To learn more about DLP, see [Overview of data loss prevention policies](data-loss-prevention-policies.md).</span></span>
  
![Modelli di criteri con le tipologie di informazioni sensibili](../media/dafd87d4-c7bb-439a-ac7b-193c018f98a5.png)
  
<span data-ttu-id="b7846-p112">Dopo aver selezionato un modello di criteri, è possibile aggiungere o rimuovere qualunque tipo di informazioni riservate e modificare il numero di istanze e l'accuratezza della corrispondenza. Nell'esempio mostrato di seguito, verrà applicata automaticamente un'etichetta di conservazione solo quando:</span><span class="sxs-lookup"><span data-stu-id="b7846-p112">After you select a policy template, you can add or remove any types of sensitive information, and you can change the instance count and match accuracy. In the example shown here, a retention label will be auto-applied only when:</span></span>
  
- <span data-ttu-id="b7846-p113">Il contenuto include tra 1 e 9 istanze di qualsiasi di tipo di informazioni riservate. È possibile eliminare il valore **max** in modo che diventi **qualsiasi**.</span><span class="sxs-lookup"><span data-stu-id="b7846-p113">The content contains between 1 and 9 instances of any of these three sensitive information types. You can delete the **max** value so that it changes to **any**.</span></span>
    
- <span data-ttu-id="b7846-173">Il tipo di informazioni sensibili rilevate ha un'accuratezza della corrispondenza (o livello di attendibilità) di almeno 75.</span><span class="sxs-lookup"><span data-stu-id="b7846-173">The type of sensitive information that's detected has a match accuracy (or confidence level) of at least 75.</span></span> <span data-ttu-id="b7846-174">Molti tipi di informazioni sensibili sono definiti con più criteri. I criteri con un livello di accuratezza della corrispondenza superiore richiedono l'individuazione di ulteriori elementi di prova (ad esempio parole chiave, date o indirizzi), mentre i criteri con un livello di accuratezza della corrispondenza inferiore richiedono meno elementi di prova.</span><span class="sxs-lookup"><span data-stu-id="b7846-174">Many sensitive information types are defined with multiple patterns, where a pattern with a higher match accuracy requires more evidence to be found (such as keywords, dates, or addresses), while a pattern with a lower match accuracy requires less evidence.</span></span> <span data-ttu-id="b7846-175">Più basso è il valore di accuratezza della corrispondenza **min**, più facile sarà che il contenuto soddisfi la condizione.</span><span class="sxs-lookup"><span data-stu-id="b7846-175">The lower the **min** match accuracy, the easier it is for content to match the condition.</span></span> 
    
<span data-ttu-id="b7846-176">Per altre informazioni su queste opzioni, vedere [Tuning rules to make them easier or harder to match](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match) (Ottimizzazione delle regole per rendere più facile o difficile la corrispondenza).</span><span class="sxs-lookup"><span data-stu-id="b7846-176">For more information on these options, see [Tuning rules to make them easier or harder to match](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span></span>
    
![Opzioni per l'identificazione dei tipi di informazioni riservate](../media/de255881-f596-4c8d-8359-e974e3a0819a.png)
  
#### <a name="auto-apply-labels-to-content-with-keywords-or-searchable-properties"></a><span data-ttu-id="b7846-178">Applicare automaticamente etichette al contenuto con parole chiave o con proprietà disponibili per le ricerche</span><span class="sxs-lookup"><span data-stu-id="b7846-178">Auto-apply labels to content with keywords or searchable properties</span></span>

<span data-ttu-id="b7846-p115">È possibile applicare automaticamente etichette al contenuto usando una query che include parole, frasi, valori o proprietà disponibili per le ricerche specifiche. È possibile perfezionare la query usando operatori di ricerca come AND, OR e NOT.</span><span class="sxs-lookup"><span data-stu-id="b7846-p115">You can auto-apply labels to content by using a query that contains specific words, phrases, or values of searchable properties. You can refine your query by using search operators such as AND, OR, and NOT.</span></span>

![Editor di query](../media/ac5b8e5e-7453-4ec7-905c-160df57298d3.png)

<span data-ttu-id="b7846-182">Per altre informazioni sulla sintassi della query che usa Keyword Query Language (KQL), vedere [Riferimenti alla sintassi KQL (Keyword Query Language)](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference).</span><span class="sxs-lookup"><span data-stu-id="b7846-182">For more information about the query syntax that uses Keyword Query Language (KQL), see [Keyword Query Language (KQL) syntax reference](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference).</span></span>

<span data-ttu-id="b7846-183">Le etichette basate su query usano l'indice di ricerca per identificare il contenuto.</span><span class="sxs-lookup"><span data-stu-id="b7846-183">Query-based labels use the search index to identify content.</span></span> <span data-ttu-id="b7846-184">Per ulteriori informazioni sulle proprietà disponibili per la ricerca, vedere:</span><span class="sxs-lookup"><span data-stu-id="b7846-184">For more information about the searchable properties that you can use, see:</span></span>

- [<span data-ttu-id="b7846-185">Query con parole chiave e condizioni di ricerca per la Ricerca contenuto</span><span class="sxs-lookup"><span data-stu-id="b7846-185">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
- [<span data-ttu-id="b7846-186">Panoramica delle proprietà gestite e sottoposte a ricerca per indicizzazione in SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="b7846-186">Overview of crawled and managed properties in SharePoint Server</span></span>](https://docs.microsoft.com/SharePoint/technical-reference/crawled-and-managed-properties-overview)

> [!NOTE]
> <span data-ttu-id="b7846-187">Sebbene le proprietà gestite da SharePoint supportino gli alias, non devono essere usate quando si configurano le etichette di conservazione.</span><span class="sxs-lookup"><span data-stu-id="b7846-187">Although SharePoint managed properties support aliases, don't use these when you configure your retention labels.</span></span> <span data-ttu-id="b7846-188">Specificare sempre il nome effettivo della proprietà gestita, ad esempio RefinableString01.</span><span class="sxs-lookup"><span data-stu-id="b7846-188">Always specify the actual name of the managed property, for example, "RefinableString01".</span></span>

<span data-ttu-id="b7846-189">Esempi di query:</span><span class="sxs-lookup"><span data-stu-id="b7846-189">Examples queries:</span></span>

| <span data-ttu-id="b7846-190">Carico di lavoro</span><span class="sxs-lookup"><span data-stu-id="b7846-190">Workload</span></span> | <span data-ttu-id="b7846-191">Esempio</span><span class="sxs-lookup"><span data-stu-id="b7846-191">Example</span></span> |
|:-----|:-----|
|<span data-ttu-id="b7846-192">Exchange</span><span class="sxs-lookup"><span data-stu-id="b7846-192">Exchange</span></span>   | `subject:"Quarterly Financials"` |
|<span data-ttu-id="b7846-193">Exchange</span><span class="sxs-lookup"><span data-stu-id="b7846-193">Exchange</span></span>   | `recipients:garthf@contoso.com` |
|<span data-ttu-id="b7846-194">SharePoint</span><span class="sxs-lookup"><span data-stu-id="b7846-194">SharePoint</span></span> | `contenttype:contract` |
|<span data-ttu-id="b7846-195">SharePoint</span><span class="sxs-lookup"><span data-stu-id="b7846-195">SharePoint</span></span> | `site:https://contoso.sharepoint.com/sites/teams/procurement AND contenttype:contract`|

#### <a name="auto-apply-labels-to-content-by-using-trainable-classifiers"></a><span data-ttu-id="b7846-196">Etichette applicate automaticamente al contenuto con classificatori sottoponibili a training</span><span class="sxs-lookup"><span data-stu-id="b7846-196">Auto-apply labels to content by using trainable classifiers</span></span>

<span data-ttu-id="b7846-197">Se si sceglie l'opzione del classificatore sottoponibile a training, è possibile selezionare un classificatore predefinito oppure personalizzato.</span><span class="sxs-lookup"><span data-stu-id="b7846-197">When you choose the option for a trainable classifier, you can select one of the built-in classifiers, or a custom classifier.</span></span> <span data-ttu-id="b7846-198">I classificatori predefiniti includono i **curriculum**, il **codice sorgente**, le **molestie mirate**, i **contenuti volgari** e le **minacce**:</span><span class="sxs-lookup"><span data-stu-id="b7846-198">The built-in classifiers include **Resumes**, **SourceCode**, **Targeted Harassment**, **Profanity**, and **Threat**:</span></span>

![Scegliere un classificatore sottoponibile a training](../media/retention-label-classifers.png)

> [!CAUTION]
> <span data-ttu-id="b7846-200">Il classificatore predefinito **Linguaggio offensivo** è stato deprecato perché generava un numero elevato di falsi positivi.</span><span class="sxs-lookup"><span data-stu-id="b7846-200">We are deprecating the **Offensive Language** built-in classifier because it has been producing a high number of false positives.</span></span> <span data-ttu-id="b7846-201">Non usare questo classificatore predefinito e, se è in uso, è consigliabile spostare i processi aziendali da esso.</span><span class="sxs-lookup"><span data-stu-id="b7846-201">Don't use this built-in classifier and if you are currently using it, you should move your business processes off it.</span></span> <span data-ttu-id="b7846-202">Usare invece i classificatori predefiniti per **molestie**, **volgarità** e **minacce**.</span><span class="sxs-lookup"><span data-stu-id="b7846-202">We recommend using the **Targeted Harassment**, **Profanity**, and **Threat** built-in classifiers instead.</span></span>

<span data-ttu-id="b7846-203">Per applicare automaticamente un'etichetta utilizzando questa opzione, i siti e le cassette postali di SharePoint Online devono avere almeno 10 MB di dati.</span><span class="sxs-lookup"><span data-stu-id="b7846-203">To automatically apply a label by using this option, SharePoint Online sites and mailboxes must have at least 10 MB of data.</span></span>

<span data-ttu-id="b7846-204">Per altre informazioni sui classificatori sottoponibili a training, vedere [Introduzione ai classificatori sottoponibili a training (anteprima)](classifier-getting-started-with.md).</span><span class="sxs-lookup"><span data-stu-id="b7846-204">For more information about trainable classifiers, see [Getting started with trainable classifiers (preview)](classifier-getting-started-with.md).</span></span>

<span data-ttu-id="b7846-205">Per avere un esempio di configurazione, vedere [Come preparare e usare un classificatore integrato](classifier-using-a-ready-to-use-classifier.md#how-to-verify-that-a-built-in-classifier-will-meet-your-needs).</span><span class="sxs-lookup"><span data-stu-id="b7846-205">For an example configuration, see [How to prepare for and use a built-in classifier](classifier-using-a-ready-to-use-classifier.md#how-to-verify-that-a-built-in-classifier-will-meet-your-needs).</span></span>

## <a name="how-long-it-takes-for-retention-labels-to-take-effect"></a><span data-ttu-id="b7846-206">Tempo necessario per l'applicazione delle etichette di conservazione</span><span class="sxs-lookup"><span data-stu-id="b7846-206">How long it takes for retention labels to take effect</span></span>

<span data-ttu-id="b7846-207">In caso di applicazione automatica di etichette di conservazione, possono essere necessari fino a sette giorni prima che le etichette vengano applicate a tutto il contenuto esistente che soddisfa le condizioni.</span><span class="sxs-lookup"><span data-stu-id="b7846-207">When you auto-apply retention labels, it can take up to seven days for the retention labels to be applied to all existing content that matches the conditions.</span></span>
  
![Diagramma di disponibilità delle etichette applicate automaticamente](../media/b8c00657-477a-4ade-b914-e643ef97a10d.png)
  
## <a name="updating-retention-labels-and-their-policies"></a><span data-ttu-id="b7846-209">Aggiornare le etichette di conservazione e i criteri</span><span class="sxs-lookup"><span data-stu-id="b7846-209">Updating retention labels and their policies</span></span>

<span data-ttu-id="b7846-210">Quando si modifica un'etichetta di conservazione o un criterio di applicazione automatica e l'etichetta di conservazione è già applicata al contenuto, le impostazioni aggiornate verranno applicate automaticamente a tale contenuto oltre che a quello identificato per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="b7846-210">When you edit a retention label or auto-apply policy, and the retention label is already applied to content, your updated settings will automatically be applied to this content in addition to content that's newly identified.</span></span>

<span data-ttu-id="b7846-211">Alcune impostazioni non possono essere modificate dopo aver creato e salvato l'etichetta o i criteri, tra cui:</span><span class="sxs-lookup"><span data-stu-id="b7846-211">Some settings can't be changed after the label or policy is created and saved, which include:</span></span>
- <span data-ttu-id="b7846-212">Le impostazioni di conservazione tranne il periodo di conservazione, a meno che l'etichetta non sia stata configurata per conservare o eliminare il contenuto in base alla data di creazione.</span><span class="sxs-lookup"><span data-stu-id="b7846-212">The retention settings except the retention period, unless you've configured the label to retain or delete the content based on when it was created.</span></span>
- <span data-ttu-id="b7846-213">L'opzione per classificare come record.</span><span class="sxs-lookup"><span data-stu-id="b7846-213">The option to classify as a record.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b7846-214">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="b7846-214">Next steps</span></span>

<span data-ttu-id="b7846-215">Vedere [Usare etichette di riservatezza per gestire il ciclo di vita dei documenti archiviati in SharePoint](auto-apply-retention-labels-scenario.md) per uno scenario di esempio in cui vengono usati un criterio di applicazione automatica con proprietà gestite in SharePoint conservazione e la conservazione basata su eventi per avviare il periodo di conservazione.</span><span class="sxs-lookup"><span data-stu-id="b7846-215">See [Use retention labels to manage the lifecycle of documents stored in SharePoint](auto-apply-retention-labels-scenario.md) for an example scenario that uses an auto-apply policy with managed properties in SharePoint, and event-based retention to start the retention period.</span></span>
