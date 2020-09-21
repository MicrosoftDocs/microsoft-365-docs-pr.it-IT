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
ms.openlocfilehash: b792a03bda6785a8b45472d2eb997bfb00574218
ms.sourcegitcommit: fdb5f9d865037c0ae23aae34a5c0f06b625b2f69
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/18/2020
ms.locfileid: "48131794"
---
# <a name="automatically-apply-a-retention-label-to-retain-or-delete-content"></a><span data-ttu-id="fae75-103">Applicare automaticamente un'etichetta di conservazione per conservare o eliminare il contenuto</span><span class="sxs-lookup"><span data-stu-id="fae75-103">Automatically apply a retention label to retain or delete content</span></span>

><span data-ttu-id="fae75-104">*[Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="fae75-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="fae75-105">Una delle funzionalità più efficaci delle [etichette di conservazione](retention.md) è la possibilità di applicarle automaticamente al contenuto che soddisfa condizioni specificate.</span><span class="sxs-lookup"><span data-stu-id="fae75-105">One of the most powerful features of [retention labels](retention.md) is the ability to apply them automatically to content that matches specified conditions.</span></span> <span data-ttu-id="fae75-106">In questo caso, gli utenti dell'organizzazione non dovranno applicare le etichette di conservazione.</span><span class="sxs-lookup"><span data-stu-id="fae75-106">In this case, people in your organization don't need to apply the retention labels.</span></span> <span data-ttu-id="fae75-107">Microsoft 365 lo farà automaticamente.</span><span class="sxs-lookup"><span data-stu-id="fae75-107">Microsoft 365 does the work for them.</span></span>
  
<span data-ttu-id="fae75-108">Le etichette di conservazione applicate automaticamente sono potenti perché:</span><span class="sxs-lookup"><span data-stu-id="fae75-108">Auto-applying retention labels are powerful because:</span></span>
  
- <span data-ttu-id="fae75-109">Non è necessario formare gli utenti su tutte le classificazioni.</span><span class="sxs-lookup"><span data-stu-id="fae75-109">You don't need to train your users on all of your classifications.</span></span>
    
- <span data-ttu-id="fae75-110">Non è necessario affidarsi solo agli utenti per la classificazione corretta di tutto il contenuto.</span><span class="sxs-lookup"><span data-stu-id="fae75-110">You don't need to rely on users to classify all content correctly.</span></span>
    
- <span data-ttu-id="fae75-111">Gli utenti non hanno più bisogno di conoscere i criteri di governance dai dati e possono concentrarsi sul loro lavoro.</span><span class="sxs-lookup"><span data-stu-id="fae75-111">Users no longer need to know about data governance policies - they can focus on their work.</span></span>
    
<span data-ttu-id="fae75-112">È possibile applicare automaticamente etichette di conservazione al contenuto quando questo include informazioni sensibili, parole chiave, proprietà disponibili per la ricerca o una corrispondenza per [classificatori sottoponibili a training](classifier-get-started-with.md).</span><span class="sxs-lookup"><span data-stu-id="fae75-112">You can apply retention labels to content automatically when that content contains sensitive information, keywords or searchable properties, or a match for [trainable classifiers](classifier-get-started-with.md).</span></span>

<span data-ttu-id="fae75-113">I processi per l'applicazione automatica di un'etichetta di conservazione si basano sulle condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="fae75-113">The processes to automatically apply a retention label based on these conditions:</span></span>

![Diagramma di ruoli e attività per le etichette applicate automaticamente](../media/32f2f2fd-18a8-43fd-839d-72ad7a43e069.png)

<span data-ttu-id="fae75-115">Usare le istruzioni seguenti per i due passaggi per l'amministratore.</span><span class="sxs-lookup"><span data-stu-id="fae75-115">Use the following instructions for the two admin steps.</span></span>

> [!NOTE]
> <span data-ttu-id="fae75-116">I criteri di applicazione automatica usano l'etichettatura sul lato servizio con condizioni per applicare automaticamente etichette di conservazione.</span><span class="sxs-lookup"><span data-stu-id="fae75-116">Auto-policies use service-side labeling with conditions to automatically apply retention labels.</span></span> <span data-ttu-id="fae75-117">È anche possibile applicare automaticamente un'etichetta di conservazione con un criterio di etichetta eseguendo le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="fae75-117">You can also automatically apply a retention label with a label policy when you do the following:</span></span> 
>
> - <span data-ttu-id="fae75-118">Applicare un'etichetta di conservazione predefinita a un set di documenti, una cartella o una raccolta di SharePoint in modo che il contenuto non etichettato presente nel contenitore venga etichettato automaticamente</span><span class="sxs-lookup"><span data-stu-id="fae75-118">Apply a default retention label to a SharePoint library, folder, or document set so that unlabeled content in that container is automatically labeled</span></span>
>- <span data-ttu-id="fae75-119">Applicazione automatica di un'etichetta di conservazione alla posta elettronica mediante regole</span><span class="sxs-lookup"><span data-stu-id="fae75-119">Automatically applying a retention label to email by using rules</span></span>
>
> <span data-ttu-id="fae75-120">Per questi scenari, vedere [Creare e applicare etichette di conservazione nelle app](create-apply-retention-labels.md).</span><span class="sxs-lookup"><span data-stu-id="fae75-120">For these scenarios, see [Create and apply retention labels in apps](create-apply-retention-labels.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="fae75-121">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="fae75-121">Before you begin</span></span>

<span data-ttu-id="fae75-122">L'amministratore globale dell'organizzazione dispone delle autorizzazioni complete per creare e modificare le etichette conservazione e i relativi criteri.</span><span class="sxs-lookup"><span data-stu-id="fae75-122">The global admin for your organization has full permissions to create and edit retention labels and their policies.</span></span> <span data-ttu-id="fae75-123">Se non si esegue l'accesso come amministratore globale, vedere le [autorizzazioni necessarie per creare e gestire criteri di conservazione ed etichette di conservazione](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels).</span><span class="sxs-lookup"><span data-stu-id="fae75-123">If you aren't signing in as a global admin, see [Permissions required to create and manage retention policies and retention labels](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels).</span></span>

## <a name="how-to-auto-apply-a-retention-label"></a><span data-ttu-id="fae75-124">Come applicare automaticamente un'etichetta di conservazione</span><span class="sxs-lookup"><span data-stu-id="fae75-124">How to auto-apply a retention label</span></span>

<span data-ttu-id="fae75-125">Creare prima di tutto l'etichetta di conservazione.</span><span class="sxs-lookup"><span data-stu-id="fae75-125">First, create your retention label.</span></span> <span data-ttu-id="fae75-126">Quindi, creare un criterio automatico per applicare l'etichetta.</span><span class="sxs-lookup"><span data-stu-id="fae75-126">Then create an auto-policy to apply that label.</span></span> <span data-ttu-id="fae75-127">Se è già stata creata l'etichetta di conservazione, passare a [Creare un criterio di applicazione automatica](#step-2-create-an-auto-apply-policy).</span><span class="sxs-lookup"><span data-stu-id="fae75-127">If you have already created your retention label, skip to [creating an auto-policy](#step-2-create-an-auto-apply-policy).</span></span>

<span data-ttu-id="fae75-128">Le istruzioni di spostamento variano a seconda che si usi o meno la [gestione dei record](records-management.md).</span><span class="sxs-lookup"><span data-stu-id="fae75-128">Navigation instructions depend on whether you're using [records management](records-management.md) or not.</span></span> <span data-ttu-id="fae75-129">Sono disponibili istruzioni per entrambi gli scenari.</span><span class="sxs-lookup"><span data-stu-id="fae75-129">Instructions are provided for both scenarios.</span></span>

### <a name="step-1-create-a-retention-label"></a><span data-ttu-id="fae75-130">Passaggio 1: Creare un'etichetta di conservazione</span><span class="sxs-lookup"><span data-stu-id="fae75-130">Step 1: Create a retention label</span></span>

1. <span data-ttu-id="fae75-131">Nel [Centro conformità Microsoft 365](https://compliance.microsoft.com/) passare a una delle posizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="fae75-131">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="fae75-132">Se si usa la gestione dei record:</span><span class="sxs-lookup"><span data-stu-id="fae75-132">If you are using records management:</span></span>
        - <span data-ttu-id="fae75-133">**Soluzioni** > **Records management** > scheda **Piano di archiviazione** > **+ Crea un'etichetta** > **Etichetta di conservazione**</span><span class="sxs-lookup"><span data-stu-id="fae75-133">**Solutions** > **Records management** > **File plan** tab > **+ Create a label** > **Retention label**</span></span>
        
    - <span data-ttu-id="fae75-134">Se non si usa la gestione dei record:</span><span class="sxs-lookup"><span data-stu-id="fae75-134">If you are not using records management:</span></span>
       - <span data-ttu-id="fae75-135">**Soluzioni** > **Governance delle informazioni** > scheda **Etichette** > + **Crea un'etichetta**</span><span class="sxs-lookup"><span data-stu-id="fae75-135">**Solutions** > **Information governance** > **Labels** tab > + **Create a label**</span></span>
    
    <span data-ttu-id="fae75-136">L'opzione non è immediatamente visibile?</span><span class="sxs-lookup"><span data-stu-id="fae75-136">Don't immediately see your option?</span></span> <span data-ttu-id="fae75-137">Selezionare per prima cosa **Mostra tutto**.</span><span class="sxs-lookup"><span data-stu-id="fae75-137">First select **Show all**.</span></span> 

2. <span data-ttu-id="fae75-138">Seguire le istruzioni della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="fae75-138">Follow the prompts in the wizard.</span></span> <span data-ttu-id="fae75-139">Se si usa la gestione dei record:</span><span class="sxs-lookup"><span data-stu-id="fae75-139">If you are using records management:</span></span>
    
    - <span data-ttu-id="fae75-140">Per informazioni sui descrittori del piano di archiviazione, vedere [Usare il piano di archiviazione per gestire le etichette di conservazione](file-plan-manager.md).</span><span class="sxs-lookup"><span data-stu-id="fae75-140">For information about the file plan descriptors, see [Use file plan to manage retention labels](file-plan-manager.md)</span></span>
    
    - <span data-ttu-id="fae75-141">Per usare l'etichetta di conservazione per dichiarare un [record](records-management.md#records), abilitare l'opzione **Contrassegna elementi come record**.</span><span class="sxs-lookup"><span data-stu-id="fae75-141">To use the retention label to declare a [record](records-management.md#records), enable the option **Mark items as a record**.</span></span>

3. <span data-ttu-id="fae75-142">Una volta creata l'etichetta e dopo la comparsa dell'opzione per pubblicarla, applicare automaticamente l'etichetta o semplicemente salvarla: selezionare **Applica automaticamente questa etichetta a un tipo specifico di contenuto**, quindi selezionare **Fatto** per avviare la procedura guidata di creazione automatica delle etichette e procedere direttamente al passaggio 2 della procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="fae75-142">After you have created the label and you see the options to publish the label, auto-apply the label, or just save the label: Select **Auto-apply this label to a specific type of content**, and then select **Done** to start the Create auto-labeling wizard that takes you directly to step 2 in the following procedure.</span></span>

<span data-ttu-id="fae75-143">Per modificare un'etichetta esistente, selezionarla e quindi selezionare l'opzione **Modifica etichetta** per avviare la procedura guidata di modifica che consente di modificare le descrizioni dell'etichetta e qualsiasi [impostazione idonea](#updating-retention-labels-and-their-policies) del passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="fae75-143">To edit an existing label, select it, and then select the **Edit label** option to start the Edit retention wizard that lets you change the label descriptions and any [eligible settings](#updating-retention-labels-and-their-policies) from step 2.</span></span>


### <a name="step-2-create-an-auto-apply-policy"></a><span data-ttu-id="fae75-144">Passaggio 2: Creare un criterio di applicazione automatica</span><span class="sxs-lookup"><span data-stu-id="fae75-144">Step 2: Create an auto-apply policy</span></span>

<span data-ttu-id="fae75-145">Quando si crea un criterio di applicazione automatica, si seleziona un'etichetta di conservazione da applicare automaticamente al contenuto in base alle condizioni specificate.</span><span class="sxs-lookup"><span data-stu-id="fae75-145">When you create an auto-apply policy, you select a retention label to automatically apply to content, based on the conditions that you specify.</span></span>

1. <span data-ttu-id="fae75-146">Nel [Centro conformità Microsoft 365](https://compliance.microsoft.com/) passare a una delle posizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="fae75-146">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="fae75-147">Se si usa la gestione dei record: **Governance delle informazioni**:</span><span class="sxs-lookup"><span data-stu-id="fae75-147">If you are using records management: **Information governance**:</span></span>
        - <span data-ttu-id="fae75-148">**Soluzioni** > **Gestione dei record** > scheda **Criteri delle etichette** > **Applica automaticamente etichetta**</span><span class="sxs-lookup"><span data-stu-id="fae75-148">**Solutions** > **Records management** > **Label policies** tab > **Auto-apply a label**</span></span>
    
    - <span data-ttu-id="fae75-149">Se non si usa la gestione dei record:</span><span class="sxs-lookup"><span data-stu-id="fae75-149">If you are not using records management:</span></span>
        - <span data-ttu-id="fae75-150">**Soluzioni** > **Governance delle informazioni** > scheda **Criteri delle etichette** > **Applica automaticamente etichetta**</span><span class="sxs-lookup"><span data-stu-id="fae75-150">**Solutions** > **Information governance** > **Label policies** tab > **Auto-apply a label**</span></span>
    
    <span data-ttu-id="fae75-151">L'opzione non è immediatamente visibile?</span><span class="sxs-lookup"><span data-stu-id="fae75-151">Don't immediately see your option?</span></span> <span data-ttu-id="fae75-152">Selezionare per prima cosa **Mostra tutto**.</span><span class="sxs-lookup"><span data-stu-id="fae75-152">First select **Show all**.</span></span> 

2. <span data-ttu-id="fae75-153">Seguire le istruzioni della procedura guidata per la creazione automatica di etichette.</span><span class="sxs-lookup"><span data-stu-id="fae75-153">Follow the prompts in the Create auto-labeling wizard.</span></span>
    
    <span data-ttu-id="fae75-154">Per informazioni su come configurare le condizioni per l'applicazione automatica dell'etichetta di conservazione, vedere la sezione [Configurare le condizioni per l'applicazione automatica delle etichette di conservazione](#configuring-conditions-for-auto-apply-retention-labels) in questa pagina.</span><span class="sxs-lookup"><span data-stu-id="fae75-154">For information about configuring the conditions that automatically apply the retention label, see the [Configuring conditions for auto-apply retention labels](#configuring-conditions-for-auto-apply-retention-labels) section on this page.</span></span>
    
    <span data-ttu-id="fae75-155">Per informazioni sulle posizioni supportate dalle etichette di conservazione, vedere la sezione [Etichette di conservazione e posizioni](retention.md#retention-label-policies-and-locations).</span><span class="sxs-lookup"><span data-stu-id="fae75-155">For information about the locations supported by retention labels, see the [Retention labels and locations](retention.md#retention-label-policies-and-locations) section.</span></span>

<span data-ttu-id="fae75-156">Per modificare un criterio di applicazione automatica esistente, selezionarlo per avviare la procedura guidata di modifica del criteri di conservazione, che consente di modificare l'etichetta selezionata e qualsiasi [impostazione idonea](#updating-retention-labels-and-their-policies) del passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="fae75-156">To edit an existing auto-apply policy, select it to start the Edit retention policy wizard that lets you change the selected retention label and any [eligible settings](#updating-retention-labels-and-their-policies) from step 2.</span></span>


### <a name="configuring-conditions-for-auto-apply-retention-labels"></a><span data-ttu-id="fae75-157">Configurare le condizioni per l'applicazione automatica delle etichette di conservazione</span><span class="sxs-lookup"><span data-stu-id="fae75-157">Configuring conditions for auto-apply retention labels</span></span>

<span data-ttu-id="fae75-158">È possibile applicare automaticamente etichette di conservazione al contenuto quando questo contiene:</span><span class="sxs-lookup"><span data-stu-id="fae75-158">You can apply retention labels to content automatically when that content contains:</span></span>

- [<span data-ttu-id="fae75-159">Tipi specifici di informazioni riservate.</span><span class="sxs-lookup"><span data-stu-id="fae75-159">Specific types of sensitive information</span></span>](#auto-apply-labels-to-content-with-specific-types-of-sensitive-information)

- [<span data-ttu-id="fae75-160">Parole chiave specifiche o proprietà disponibili per la ricerca che corrispondono a una query creata.</span><span class="sxs-lookup"><span data-stu-id="fae75-160">Specific keywords or searchable properties that match a query you create</span></span>](#auto-apply-labels-to-content-with-keywords-or-searchable-properties)

- [<span data-ttu-id="fae75-161">Una corrispondenza per classificatori sottoponibili a training</span><span class="sxs-lookup"><span data-stu-id="fae75-161">A match for trainable classifiers</span></span>](#auto-apply-labels-to-content-by-using-trainable-classifiers)

#### <a name="auto-apply-labels-to-content-with-specific-types-of-sensitive-information"></a><span data-ttu-id="fae75-162">Applicare automaticamente etichette al contenuto con tipi specifici di informazioni sensibili</span><span class="sxs-lookup"><span data-stu-id="fae75-162">Auto-apply labels to content with specific types of sensitive information</span></span>

<span data-ttu-id="fae75-163">Quando si creano etichette di conservazione ad applicazione automatica per le informazioni riservate, viene visualizzato lo stesso elenco di modelli di criteri mostrato quando si creano criteri di prevenzione della perdita dei dati (DLP).</span><span class="sxs-lookup"><span data-stu-id="fae75-163">When you create auto-apply retention labels for sensitive information, you see the same list of policy templates as when you create a data loss prevention (DLP) policy.</span></span> <span data-ttu-id="fae75-164">Ogni modello è preconfigurato in modo da cercare specifici tipi di informazioni riservate.</span><span class="sxs-lookup"><span data-stu-id="fae75-164">Each template is preconfigured to look for specific types of sensitive information.</span></span> <span data-ttu-id="fae75-165">Ad esempio, il modello mostrato qui cerca i numeri ITIN, SSN e di passaporto nella categoria **Privacy**, e nel **Modello dati personali (PII) Stati Uniti**:</span><span class="sxs-lookup"><span data-stu-id="fae75-165">For example, the template shown here looks for U.S. ITIN, SSN, and passport numbers from the **Privacy** category, and **U.S Personally Identifiable Information (PII) Data template**:</span></span>

![Modelli di criteri con le tipologie di informazioni sensibili](../media/dafd87d4-c7bb-439a-ac7b-193c018f98a5.png)

<span data-ttu-id="fae75-167">Per altre informazioni sui tipi di informazioni sensibili, vedere [Definizioni delle entità tipo di informazione sensibile](sensitive-information-type-entity-definitions.md).</span><span class="sxs-lookup"><span data-stu-id="fae75-167">To learn more about the sensitivity information types, see [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md).</span></span>

<span data-ttu-id="fae75-168">Dopo aver selezionato un modello di criteri, è possibile aggiungere o rimuovere qualunque tipo di informazione riservata e modificare il numero di istanze e l'accuratezza della corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="fae75-168">After you select a policy template, you can add or remove any types of sensitive information, and you can change the instance count and match accuracy.</span></span> <span data-ttu-id="fae75-169">Nella schermata di esempio seguente, un'etichetta di conservazione sarà applicata automaticamente solo quando:</span><span class="sxs-lookup"><span data-stu-id="fae75-169">In the example screenshot shown next, a retention label will be auto-applied only when:</span></span>
  
- <span data-ttu-id="fae75-170">Il tipo di informazioni sensibili rilevate ha un'accuratezza della corrispondenza (o livello di attendibilità) di almeno 75.</span><span class="sxs-lookup"><span data-stu-id="fae75-170">The type of sensitive information that's detected has a match accuracy (or confidence level) of at least 75.</span></span> <span data-ttu-id="fae75-171">Molti tipi di informazioni sensibili sono definiti con più criteri. I criteri con un livello di accuratezza della corrispondenza superiore richiedono l'individuazione di ulteriori elementi di prova (ad esempio parole chiave, date o indirizzi), mentre i criteri con un livello di accuratezza della corrispondenza inferiore richiedono meno elementi di prova.</span><span class="sxs-lookup"><span data-stu-id="fae75-171">Many sensitive information types are defined with multiple patterns, where a pattern with a higher match accuracy requires more evidence to be found (such as keywords, dates, or addresses), while a pattern with a lower match accuracy requires less evidence.</span></span> <span data-ttu-id="fae75-172">Più basso è il valore di accuratezza della corrispondenza **min**, più facile sarà che il contenuto soddisfi la condizione.</span><span class="sxs-lookup"><span data-stu-id="fae75-172">The lower the **min** match accuracy, the easier it is for content to match the condition.</span></span>

- <span data-ttu-id="fae75-173">Il contenuto include tra 1 e 9 istanze di qualsiasi di questi tre tipi di informazioni riservate.</span><span class="sxs-lookup"><span data-stu-id="fae75-173">The content contains between 1 and 9 instances of any of these three sensitive information types.</span></span> <span data-ttu-id="fae75-174">È possibile eliminare il valore **a** in modo che diventi **Qualsiasi**.</span><span class="sxs-lookup"><span data-stu-id="fae75-174">You can delete the **to** value so that it changes to **Any**.</span></span>

<span data-ttu-id="fae75-175">Per altre informazioni su queste opzioni, vedere le indicazioni seguenti della documentazione sulla prevenzione della perdita dei dati [Modificare le regole per rendere più facili o difficili le corrispondenze](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span><span class="sxs-lookup"><span data-stu-id="fae75-175">For more information about these options, see the following guidance from the DLP documentation [Tuning rules to make them easier or harder to match](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span></span>
    
![Opzioni per l'identificazione dei tipi di informazioni riservate](../media/de255881-f596-4c8d-8359-e974e3a0819a.png)
  
#### <a name="auto-apply-labels-to-content-with-keywords-or-searchable-properties"></a><span data-ttu-id="fae75-177">Applicare automaticamente etichette al contenuto con parole chiave o con proprietà disponibili per le ricerche</span><span class="sxs-lookup"><span data-stu-id="fae75-177">Auto-apply labels to content with keywords or searchable properties</span></span>

<span data-ttu-id="fae75-p113">È possibile applicare automaticamente etichette al contenuto usando una query che include parole, frasi, valori o proprietà disponibili per le ricerche specifiche. È possibile perfezionare la query usando operatori di ricerca come AND, OR e NOT.</span><span class="sxs-lookup"><span data-stu-id="fae75-p113">You can auto-apply labels to content by using a query that contains specific words, phrases, or values of searchable properties. You can refine your query by using search operators such as AND, OR, and NOT.</span></span>

![Editor di query](../media/new-retention-query-editor.png)

<span data-ttu-id="fae75-181">Per altre informazioni sulla sintassi della query che usa Keyword Query Language (KQL), vedere [Riferimenti alla sintassi KQL (Keyword Query Language)](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference).</span><span class="sxs-lookup"><span data-stu-id="fae75-181">For more information about the query syntax that uses Keyword Query Language (KQL), see [Keyword Query Language (KQL) syntax reference](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference).</span></span>

<span data-ttu-id="fae75-182">Le etichette basate su query usano l'indice di ricerca per identificare il contenuto.</span><span class="sxs-lookup"><span data-stu-id="fae75-182">Query-based labels use the search index to identify content.</span></span> <span data-ttu-id="fae75-183">Per ulteriori informazioni sulle proprietà disponibili per la ricerca, vedere:</span><span class="sxs-lookup"><span data-stu-id="fae75-183">For more information about the searchable properties that you can use, see:</span></span>

- [<span data-ttu-id="fae75-184">Query con parole chiave e condizioni di ricerca per la Ricerca contenuto</span><span class="sxs-lookup"><span data-stu-id="fae75-184">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
- [<span data-ttu-id="fae75-185">Panoramica delle proprietà gestite e sottoposte a ricerca per indicizzazione in SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="fae75-185">Overview of crawled and managed properties in SharePoint Server</span></span>](https://docs.microsoft.com/SharePoint/technical-reference/crawled-and-managed-properties-overview)

> [!NOTE]
> <span data-ttu-id="fae75-186">Sebbene le proprietà gestite da SharePoint supportino gli alias, non devono essere usate quando si configurano le etichette di conservazione.</span><span class="sxs-lookup"><span data-stu-id="fae75-186">Although SharePoint managed properties support aliases, don't use these when you configure your retention labels.</span></span> <span data-ttu-id="fae75-187">Specificare sempre il nome effettivo della proprietà gestita, ad esempio RefinableString01.</span><span class="sxs-lookup"><span data-stu-id="fae75-187">Always specify the actual name of the managed property, for example, "RefinableString01".</span></span>

<span data-ttu-id="fae75-188">Esempi di query:</span><span class="sxs-lookup"><span data-stu-id="fae75-188">Examples queries:</span></span>

| <span data-ttu-id="fae75-189">Carico di lavoro</span><span class="sxs-lookup"><span data-stu-id="fae75-189">Workload</span></span> | <span data-ttu-id="fae75-190">Esempio</span><span class="sxs-lookup"><span data-stu-id="fae75-190">Example</span></span> |
|:-----|:-----|
|<span data-ttu-id="fae75-191">Exchange</span><span class="sxs-lookup"><span data-stu-id="fae75-191">Exchange</span></span>   | `subject:"Quarterly Financials"` |
|<span data-ttu-id="fae75-192">Exchange</span><span class="sxs-lookup"><span data-stu-id="fae75-192">Exchange</span></span>   | `recipients:garthf@contoso.com` |
|<span data-ttu-id="fae75-193">SharePoint</span><span class="sxs-lookup"><span data-stu-id="fae75-193">SharePoint</span></span> | `contenttype:contract` |
|<span data-ttu-id="fae75-194">SharePoint</span><span class="sxs-lookup"><span data-stu-id="fae75-194">SharePoint</span></span> | `site:https://contoso.sharepoint.com/sites/teams/procurement AND contenttype:contract`|

#### <a name="auto-apply-labels-to-content-by-using-trainable-classifiers"></a><span data-ttu-id="fae75-195">Etichette applicate automaticamente al contenuto con classificatori sottoponibili a training</span><span class="sxs-lookup"><span data-stu-id="fae75-195">Auto-apply labels to content by using trainable classifiers</span></span>

<span data-ttu-id="fae75-196">Se si sceglie l'opzione del classificatore sottoponibile a training, è possibile selezionare un classificatore predefinito oppure personalizzato.</span><span class="sxs-lookup"><span data-stu-id="fae75-196">When you choose the option for a trainable classifier, you can select one of the built-in classifiers, or a custom classifier.</span></span> <span data-ttu-id="fae75-197">I classificatori predefiniti includono i **curriculum**, il **codice sorgente**, le **molestie mirate**, i **contenuti volgari** e le **minacce**:</span><span class="sxs-lookup"><span data-stu-id="fae75-197">The built-in classifiers include **Resumes**, **SourceCode**, **Targeted Harassment**, **Profanity**, and **Threat**:</span></span>

![Scegliere un classificatore sottoponibile a training](../media/retention-label-classifers.png)

> [!CAUTION]
> <span data-ttu-id="fae75-199">Il classificatore predefinito **Linguaggio offensivo** è stato deprecato perché generava un numero elevato di falsi positivi.</span><span class="sxs-lookup"><span data-stu-id="fae75-199">We are deprecating the **Offensive Language** built-in classifier because it has been producing a high number of false positives.</span></span> <span data-ttu-id="fae75-200">Non usare questo classificatore predefinito e, se è in uso, è consigliabile spostare i processi aziendali da esso.</span><span class="sxs-lookup"><span data-stu-id="fae75-200">Don't use this built-in classifier and if you are currently using it, you should move your business processes off it.</span></span> <span data-ttu-id="fae75-201">Usare invece i classificatori predefiniti per **molestie**, **volgarità** e **minacce**.</span><span class="sxs-lookup"><span data-stu-id="fae75-201">We recommend using the **Targeted Harassment**, **Profanity**, and **Threat** built-in classifiers instead.</span></span>

<span data-ttu-id="fae75-202">Per applicare automaticamente un'etichetta utilizzando questa opzione, i siti e le cassette postali di SharePoint devono avere almeno 10 MB di dati.</span><span class="sxs-lookup"><span data-stu-id="fae75-202">To automatically apply a label by using this option, SharePoint sites and mailboxes must have at least 10 MB of data.</span></span>

<span data-ttu-id="fae75-203">Per altre informazioni sui classificatori sottoponibili a training, vedere [Informazioni sui classificatori sottoponibili a training (anteprima)](classifier-learn-about.md).</span><span class="sxs-lookup"><span data-stu-id="fae75-203">For more information about trainable classifiers, see [Learn about trainable classifiers (preview)](classifier-learn-about.md).</span></span>


## <a name="how-long-it-takes-for-retention-labels-to-take-effect"></a><span data-ttu-id="fae75-204">Tempo necessario per l'applicazione delle etichette di conservazione</span><span class="sxs-lookup"><span data-stu-id="fae75-204">How long it takes for retention labels to take effect</span></span>

<span data-ttu-id="fae75-205">In caso di applicazione automatica di etichette di conservazione, possono essere necessari fino a sette giorni prima che le etichette vengano applicate a tutto il contenuto esistente che soddisfa le condizioni.</span><span class="sxs-lookup"><span data-stu-id="fae75-205">When you auto-apply retention labels, it can take up to seven days for the retention labels to be applied to all existing content that matches the conditions.</span></span>
  
![Diagramma di disponibilità delle etichette applicate automaticamente](../media/b8c00657-477a-4ade-b914-e643ef97a10d.png)
  
## <a name="updating-retention-labels-and-their-policies"></a><span data-ttu-id="fae75-207">Aggiornare le etichette di conservazione e i criteri</span><span class="sxs-lookup"><span data-stu-id="fae75-207">Updating retention labels and their policies</span></span>

<span data-ttu-id="fae75-208">Quando si modifica un'etichetta di conservazione o un criterio di applicazione automatica e l'etichetta di conservazione è già applicata al contenuto, le impostazioni aggiornate verranno applicate automaticamente a tale contenuto oltre che a quello identificato per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="fae75-208">When you edit a retention label or auto-apply policy, and the retention label is already applied to content, your updated settings will automatically be applied to this content in addition to content that's newly identified.</span></span>

<span data-ttu-id="fae75-209">Alcune impostazioni non possono essere modificate dopo aver creato e salvato l'etichetta o i criteri, tra cui:</span><span class="sxs-lookup"><span data-stu-id="fae75-209">Some settings can't be changed after the label or policy is created and saved, which include:</span></span>
- <span data-ttu-id="fae75-210">Le impostazioni di conservazione tranne il periodo di conservazione, a meno che l'etichetta non sia stata configurata per conservare o eliminare il contenuto in base alla data di creazione.</span><span class="sxs-lookup"><span data-stu-id="fae75-210">The retention settings except the retention period, unless you've configured the label to retain or delete the content based on when it was created.</span></span>
- <span data-ttu-id="fae75-211">Opzione per contrassegnare gli elementi come record.</span><span class="sxs-lookup"><span data-stu-id="fae75-211">The option to mark items as a record.</span></span>

## <a name="next-steps"></a><span data-ttu-id="fae75-212">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="fae75-212">Next steps</span></span>

<span data-ttu-id="fae75-213">Vedere [Usare etichette di riservatezza per gestire il ciclo di vita dei documenti archiviati in SharePoint](auto-apply-retention-labels-scenario.md) per uno scenario di esempio in cui vengono usati un criterio di applicazione automatica con proprietà gestite in SharePoint conservazione e la conservazione basata su eventi per avviare il periodo di conservazione.</span><span class="sxs-lookup"><span data-stu-id="fae75-213">See [Use retention labels to manage the lifecycle of documents stored in SharePoint](auto-apply-retention-labels-scenario.md) for an example scenario that uses an auto-apply policy with managed properties in SharePoint, and event-based retention to start the retention period.</span></span>
