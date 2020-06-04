---
title: Creare, pubblicare e applicare automaticamente etichette di conservazione
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
description: Istruzioni per creare, pubblicare e applicare automaticamente etichette di conservazione per conservare il contenuto necessario, eliminare quello che non è necessario e dichiarare un elemento come record nell'ambiente di Office 365.
ms.openlocfilehash: a3ba321c9eae91bf701646a45271d3edcbc8dccc
ms.sourcegitcommit: c696852da06d057dba4f5147bbf46521910de3ab
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2020
ms.locfileid: "44545958"
---
# <a name="create-publish-and-auto-apply-retention-labels"></a><span data-ttu-id="a350c-103">Creare, pubblicare e applicare automaticamente etichette di conservazione</span><span class="sxs-lookup"><span data-stu-id="a350c-103">Create, publish, and auto-apply retention labels</span></span>

><span data-ttu-id="a350c-104">*[Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="a350c-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="a350c-105">Usare le informazioni seguenti per creare [etichette di conservazione](labels.md) e quindi applicarle automaticamente a documenti e messaggi di posta elettronica, oppure pubblicarle in modo che gli utenti possano applicarle manualmente.</span><span class="sxs-lookup"><span data-stu-id="a350c-105">Use the following information to help you create [retention labels](labels.md), and then automatically apply them to documents and emails, or publish them so that users can manually apply them.</span></span>

<span data-ttu-id="a350c-106">Le etichette di conservazione aiutano a conservare tutto ciò che serve ed eliminare ciò che non serve.</span><span class="sxs-lookup"><span data-stu-id="a350c-106">Retention labels help you retain what you need and delete what you don't.</span></span> <span data-ttu-id="a350c-107">Vengono anche usate anche per dichiarare un elemento come record nell'ambito di una soluzione di [gestione dei record](records-management.md) per i dati di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a350c-107">They are also used to declare an item as a record as part of a [records management](records-management.md) solution for your Microsoft 365 data.</span></span>

<span data-ttu-id="a350c-108">La posizione in cui si creano e si configurano le etichette di conservazione varia a seconda che si usi o meno la gestione dei record.</span><span class="sxs-lookup"><span data-stu-id="a350c-108">Where you create and configure your retention labels depend on whether you're using records management or not.</span></span> <span data-ttu-id="a350c-109">Sono disponibili istruzioni per entrambi gli scenari.</span><span class="sxs-lookup"><span data-stu-id="a350c-109">Instructions are provided for both scenarios.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="a350c-110">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="a350c-110">Before you begin</span></span>

<span data-ttu-id="a350c-111">Ai membri del team di conformità che creeranno etichette di conservazione è necessario assegnare autorizzazioni per il Centro sicurezza &amp; conformità.</span><span class="sxs-lookup"><span data-stu-id="a350c-111">Members of your compliance team who will create retention labels need permissions to the Security &amp; Compliance Center.</span></span> <span data-ttu-id="a350c-112">Per impostazione predefinita, l'amministratore del tenant ha accesso a questa posizione e può fornire ai responsabili della conformità e ad altre persone l'accesso al Centro sicurezza &amp; conformità, senza concedere tutte le autorizzazioni di un amministratore del tenant. A questo scopo, è consigliabile accedere alla pagina **Autorizzazioni** del Centro sicurezza &amp; conformità, modificare il gruppo di ruoli **Amministratore conformità** e aggiungere membri a tale gruppo di ruoli.</span><span class="sxs-lookup"><span data-stu-id="a350c-112">By default, your tenant admin has access to this location and can give compliance officers and other people access to the Security &amp; Compliance Center, without giving them all of the permissions of a tenant admin. To do this, we recommend that you go to the **Permissions** page of the Security &amp; Compliance Center, edit the **Compliance Administrator** role group, and add members to that role group.</span></span> 
  
<span data-ttu-id="a350c-113">Per ulteriori informazioni, vedere [Concedere agli utenti l'accesso al Centro sicurezza e conformità di Office 365](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="a350c-113">For more information, see [Give users access to the Office 365 Security &amp; Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span></span>
  
<span data-ttu-id="a350c-p104">Queste autorizzazioni sono necessarie solo per creare e applicare etichette di conservazione e criteri di etichetta. L'applicazione dei criteri non richiede l'accesso al contenuto.</span><span class="sxs-lookup"><span data-stu-id="a350c-p104">These permissions are required only to create and apply retention labels and a label policy. Policy enforcement does not require access to the content.</span></span>

## <a name="create-and-configure-retention-labels"></a><span data-ttu-id="a350c-116">Creare e configurare etichette di conservazione</span><span class="sxs-lookup"><span data-stu-id="a350c-116">Create and configure retention labels</span></span>

1. <span data-ttu-id="a350c-117">Nel [Centro conformità Microsoft 365](https://compliance.microsoft.com/) passare a una delle posizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a350c-117">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="a350c-118">Se si usa la gestione dei record:</span><span class="sxs-lookup"><span data-stu-id="a350c-118">If you are using records management:</span></span>
        - <span data-ttu-id="a350c-119">**Soluzioni** > **Records management** > scheda **Piano di archiviazione** > **+ Crea un'etichetta** > **Etichetta di conservazione**</span><span class="sxs-lookup"><span data-stu-id="a350c-119">**Solutions** > **Records management** > **File plan** tab > **+ Create a label** > **Retention label**</span></span>
        
    - <span data-ttu-id="a350c-120">Se non si usa la gestione dei record:</span><span class="sxs-lookup"><span data-stu-id="a350c-120">If you are not using records management:</span></span>
       - <span data-ttu-id="a350c-121">**Soluzioni** > **Governance delle informazioni** > scheda **Etichette** > + **Crea un'etichetta**</span><span class="sxs-lookup"><span data-stu-id="a350c-121">**Solutions** > **Information governance** > **Labels** tab > + **Create a label**</span></span>
    
    <span data-ttu-id="a350c-122">L'opzione non è immediatamente visibile?</span><span class="sxs-lookup"><span data-stu-id="a350c-122">Don't immediately see your option?</span></span> <span data-ttu-id="a350c-123">Selezionare per prima cosa **Mostra tutto**.</span><span class="sxs-lookup"><span data-stu-id="a350c-123">First select **Show all**.</span></span> 

2. <span data-ttu-id="a350c-124">Seguire le istruzioni della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="a350c-124">Follow the prompts in the wizard.</span></span> <span data-ttu-id="a350c-125">Se si usa la gestione dei record:</span><span class="sxs-lookup"><span data-stu-id="a350c-125">If you are using records management:</span></span>
    
    - <span data-ttu-id="a350c-126">Per informazioni sui descrittori del piano di archiviazione, vedere [Usare il piano di archiviazione per gestire le etichette di conservazione](file-plan-manager.md).</span><span class="sxs-lookup"><span data-stu-id="a350c-126">For information about the file plan descriptors, see [Use file plan to manage retention labels](file-plan-manager.md)</span></span>
    
    - <span data-ttu-id="a350c-127">Per usare l'etichetta di conservazione per dichiarare il contenuto come record, attivare la casella di controllo **Usa l'etichetta per classificare il contenuto come "Record"**.</span><span class="sxs-lookup"><span data-stu-id="a350c-127">To use the retention label to declare content as a record, enable the checkbox **Use label to classify content as a "Record"**.</span></span>

3. <span data-ttu-id="a350c-128">Ripetere questi passaggi per creare altre etichette.</span><span class="sxs-lookup"><span data-stu-id="a350c-128">Repeat these steps to create more labels.</span></span>

<span data-ttu-id="a350c-129">Per modificare un'etichetta esistente, selezionarla e quindi selezionare **Modifica etichetta** per avviare la stessa procedura guidata che consente di modificare le descrizioni dell'etichetta e le [impostazioni idonee](#updating-retention-labels-and-their-policies) dal passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="a350c-129">To edit an existing label, select it, and then select **Edit label** to start the same wizard that lets you change the label descriptions and any [eligible settings](#updating-retention-labels-and-their-policies) from step 2.</span></span> <span data-ttu-id="a350c-130">In alternativa, selezionare una delle opzioni **Modifica** disponibili per passare direttamente alla pagina pertinente per eseguire l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="a350c-130">Alternatively, select any of the available **Edit** options to go directly to the relevant page to make your update.</span></span>

## <a name="publish-retention-labels-by-creating-a-retention-label-policy"></a><span data-ttu-id="a350c-131">Pubblicare etichette di conservazione creando un criterio di etichetta di conservazione</span><span class="sxs-lookup"><span data-stu-id="a350c-131">Publish retention labels by creating a retention label policy</span></span>

<span data-ttu-id="a350c-132">Pubblicare le etichette di conservazione in modo che possano essere applicate manualmente dagli utenti.</span><span class="sxs-lookup"><span data-stu-id="a350c-132">Publish retention labels so that they can be manually applied by users.</span></span>

1. <span data-ttu-id="a350c-133">Nel [Centro conformità Microsoft 365](https://compliance.microsoft.com/) passare a una delle posizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a350c-133">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="a350c-134">Se si usa la gestione dei record:</span><span class="sxs-lookup"><span data-stu-id="a350c-134">If you are using records management:</span></span>
        - <span data-ttu-id="a350c-135">**Soluzioni** > **Gestione dei record** scheda > **Criteri delle etichette** > **Pubblica etichette**</span><span class="sxs-lookup"><span data-stu-id="a350c-135">**Solutions** > **Records management** > > **Label policies** tab > **Publish labels**</span></span>
    
    - <span data-ttu-id="a350c-136">Se non si usa la gestione dei record:</span><span class="sxs-lookup"><span data-stu-id="a350c-136">If you are not using records management:</span></span>
        - <span data-ttu-id="a350c-137">**Soluzioni** > **Governance delle informazioni** > scheda **Criteri delle etichette** > **Pubblica etichette**</span><span class="sxs-lookup"><span data-stu-id="a350c-137">**Solutions** > **Information governance** > **Label policies** tab > **Publish labels**</span></span>
    
    <span data-ttu-id="a350c-138">L'opzione non è immediatamente visibile?</span><span class="sxs-lookup"><span data-stu-id="a350c-138">Don't immediately see your option?</span></span> <span data-ttu-id="a350c-139">Selezionare per prima cosa **Mostra tutto**.</span><span class="sxs-lookup"><span data-stu-id="a350c-139">First select **Show all**.</span></span> 

2. <span data-ttu-id="a350c-140">Seguire le istruzioni della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="a350c-140">Follow the prompts in the wizard.</span></span>
    
    <span data-ttu-id="a350c-141">Per informazioni sulle posizioni supportate dalle etichette di conservazione, vedere la sezione [Etichette di conservazione e posizioni](labels.md#retention-label-policies-and-locations).</span><span class="sxs-lookup"><span data-stu-id="a350c-141">For information about the locations supported by retention labels, see the [Retention labels and locations](labels.md#retention-label-policies-and-locations) section.</span></span> 

<span data-ttu-id="a350c-142">Per modificare un criterio di etichetta di conservazione esistente, selezionarlo e quindi selezionare **Modifica criteri** per avviare la stessa procedura guidata che consente di modificare la descrizione del criterio e le [impostazioni idonee](#updating-retention-labels-and-their-policies) dal passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="a350c-142">To edit an existing retention label policy, select it, and then select **Edit policy** to start the same wizard that lets you change the policy description and any [eligible settings](#updating-retention-labels-and-their-policies) from step 2.</span></span> <span data-ttu-id="a350c-143">In alternativa, selezionare una delle opzioni **Modifica** disponibili per passare direttamente alla pagina pertinente per eseguire l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="a350c-143">Alternatively, select any of the available **Edit** options to go directly to the relevant page to make your update.</span></span>

## <a name="auto-apply-a-retention-label"></a><span data-ttu-id="a350c-144">Applicare automaticamente un'etichetta di conservazione</span><span class="sxs-lookup"><span data-stu-id="a350c-144">Auto-apply a retention label</span></span>

<span data-ttu-id="a350c-145">Applicare automaticamente un'etichetta di conservazione in base alle condizioni specificate.</span><span class="sxs-lookup"><span data-stu-id="a350c-145">Auto-apply a retention label, based on the conditions that you specify.</span></span>

1. <span data-ttu-id="a350c-146">Nel [Centro conformità Microsoft 365](https://compliance.microsoft.com/) passare a una delle posizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a350c-146">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="a350c-147">Se si usa la gestione dei record: **Governance delle informazioni**:</span><span class="sxs-lookup"><span data-stu-id="a350c-147">If you are using records management: **Information governance**:</span></span>
        - <span data-ttu-id="a350c-148">**Soluzioni** > **Gestione dei record** > scheda **Criteri delle etichette** > **Applica automaticamente le etichette**</span><span class="sxs-lookup"><span data-stu-id="a350c-148">**Solutions** > **Records management** > **Label policies** tab > **Auto-apply label**</span></span>
    
    - <span data-ttu-id="a350c-149">Se non si usa la gestione dei record:</span><span class="sxs-lookup"><span data-stu-id="a350c-149">If you are not using records management:</span></span>
        - <span data-ttu-id="a350c-150">**Soluzioni** > **Governance delle informazioni** > scheda **Criteri delle etichette** > **Applica automaticamente le etichette**</span><span class="sxs-lookup"><span data-stu-id="a350c-150">**Solutions** > **Information governance** > **Label policies** tab > **Auto-apply label**</span></span>
    
    <span data-ttu-id="a350c-151">L'opzione non è immediatamente visibile?</span><span class="sxs-lookup"><span data-stu-id="a350c-151">Don't immediately see your option?</span></span> <span data-ttu-id="a350c-152">Selezionare per prima cosa **Mostra tutto**.</span><span class="sxs-lookup"><span data-stu-id="a350c-152">First select **Show all**.</span></span> 

2. <span data-ttu-id="a350c-153">Seguire le istruzioni della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="a350c-153">Follow the prompts in the wizard.</span></span>
    
    <span data-ttu-id="a350c-154">Per informazioni su come configurare le condizioni per l'applicazione automatica dell'etichetta di conservazione, vedere la sezione [Configurare le condizioni per l'applicazione automatica delle etichette di conservazione](#configuring-conditions-for-auto-apply-retention-labels) in questa pagina.</span><span class="sxs-lookup"><span data-stu-id="a350c-154">For information about configuring the conditions that automatically apply the retention label, see the [Configuring conditions for auto-apply retention labels](#configuring-conditions-for-auto-apply-retention-labels) section on this page.</span></span>
    
    <span data-ttu-id="a350c-155">Per informazioni sulle posizioni supportate dalle etichette di conservazione, vedere la sezione [Etichette di conservazione e posizioni](labels.md#retention-label-policies-and-locations).</span><span class="sxs-lookup"><span data-stu-id="a350c-155">For information about the locations supported by retention labels, see the [Retention labels and locations](labels.md#retention-label-policies-and-locations) section.</span></span>

<span data-ttu-id="a350c-156">Per modificare un criterio di etichetta applicata automaticamente, selezionarlo e quindi selezionare **Modifica criteri** per avviare la stessa procedura guidata che consente di modificare la descrizione del criterio e le [impostazioni idonee](#updating-retention-labels-and-their-policies) dal passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="a350c-156">To edit an existing auto-apply label policy, select it, and then select **Edit policy** to start the same wizard that lets you change the policy description and any [eligible settings](#updating-retention-labels-and-their-policies) from step 2.</span></span> <span data-ttu-id="a350c-157">In alternativa, selezionare una delle opzioni **Modifica** disponibili per passare direttamente alla pagina pertinente per eseguire l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="a350c-157">Alternatively, select any of the available **Edit** options to go directly to the relevant page to make your update.</span></span>


## <a name="configuring-conditions-for-auto-apply-retention-labels"></a><span data-ttu-id="a350c-158">Configurare le condizioni per l'applicazione automatica delle etichette di conservazione</span><span class="sxs-lookup"><span data-stu-id="a350c-158">Configuring conditions for auto-apply retention labels</span></span>

<span data-ttu-id="a350c-159">È possibile applicare automaticamente etichette di conservazione al contenuto quando questo contiene:</span><span class="sxs-lookup"><span data-stu-id="a350c-159">You can apply retention labels to content automatically when that content contains:</span></span>
  
- [<span data-ttu-id="a350c-160">Tipi specifici di informazioni riservate.</span><span class="sxs-lookup"><span data-stu-id="a350c-160">Specific types of sensitive information</span></span>](#auto-apply-labels-to-content-with-specific-types-of-sensitive-information)
    
- [<span data-ttu-id="a350c-161">Parole chiave specifiche che corrispondono a una query creata.</span><span class="sxs-lookup"><span data-stu-id="a350c-161">Specific keywords that match a query you create</span></span>](#auto-apply-labels-to-content-with-keywords-or-searchable-properties)

- [<span data-ttu-id="a350c-162">Una corrispondenza per classificatori sottoponibili a training</span><span class="sxs-lookup"><span data-stu-id="a350c-162">A match for trainable classifiers</span></span>](#auto-apply-labels-to-content-by-using-trainable-classifiers)
    
![Pagina per scegliere la condizione dell’etichetta applicata automaticamente](../media/classifier-pre-trained-apply-label-match-trainable-classifier.png)

<span data-ttu-id="a350c-164">Possono essere necessari fino a sette giorni per applicare le etichette di conservazione ad applicazione automatica a tutto il contenuto che soddisfa le condizioni configurate.</span><span class="sxs-lookup"><span data-stu-id="a350c-164">It can take up to seven days for auto-apply retention labels to be applied to all content that matches the conditions you've configured.</span></span>

### <a name="auto-apply-labels-to-content-with-specific-types-of-sensitive-information"></a><span data-ttu-id="a350c-165">Applicare automaticamente etichette al contenuto con tipi specifici di informazioni sensibili</span><span class="sxs-lookup"><span data-stu-id="a350c-165">Auto-apply labels to content with specific types of sensitive information</span></span>

<span data-ttu-id="a350c-166">Quando si creano etichette di conservazione ad applicazione automatica per le informazioni riservate, viene visualizzato lo stesso elenco di modelli di criteri mostrato quando si creano criteri di prevenzione della perdita dei dati (DLP).</span><span class="sxs-lookup"><span data-stu-id="a350c-166">When you create auto-apply retention labels for sensitive information, you see the same list of policy templates as when you create a data loss prevention (DLP) policy.</span></span> <span data-ttu-id="a350c-167">Ogni modello di criteri è preconfigurato in modo da cercare specifici tipi di informazioni riservate.</span><span class="sxs-lookup"><span data-stu-id="a350c-167">Each policy template is preconfigured to look for specific types of sensitive information.</span></span> <span data-ttu-id="a350c-168">Ad esempio, il modello illustrato di seguito cerca codici identificativi del singolo contribuente (ITIN), codici di previdenza sociale (SSN) e numeri di passaporto statunitensi.</span><span class="sxs-lookup"><span data-stu-id="a350c-168">For example, the template shown here looks for U.S. ITIN, SSN, and passport numbers.</span></span> <span data-ttu-id="a350c-169">Per altre informazioni sui criteri DLP, vedere [Panoramica dei criteri di prevenzione della perdita dei dati](data-loss-prevention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="a350c-169">To learn more about DLP, see [Overview of data loss prevention policies](data-loss-prevention-policies.md).</span></span>
  
![Modelli di criteri con le tipologie di informazioni sensibili](../media/dafd87d4-c7bb-439a-ac7b-193c018f98a5.png)
  
<span data-ttu-id="a350c-p113">Dopo aver selezionato un modello di criteri, è possibile aggiungere o rimuovere qualunque tipo di informazioni riservate e modificare il numero di istanze e l'accuratezza della corrispondenza. Nell'esempio mostrato di seguito, verrà applicata automaticamente un'etichetta di conservazione solo quando:</span><span class="sxs-lookup"><span data-stu-id="a350c-p113">After you select a policy template, you can add or remove any types of sensitive information, and you can change the instance count and match accuracy. In the example shown here, a retention label will be auto-applied only when:</span></span>
  
- <span data-ttu-id="a350c-p114">Il contenuto include tra 1 e 9 istanze di qualsiasi di tipo di informazioni riservate. È possibile eliminare il valore **max** in modo che diventi **qualsiasi**.</span><span class="sxs-lookup"><span data-stu-id="a350c-p114">The content contains between 1 and 9 instances of any of these three sensitive information types. You can delete the **max** value so that it changes to **any**.</span></span>
    
- <span data-ttu-id="a350c-p115">Il tipo di informazioni riservate rilevate ha un'accuratezza della corrispondenza (o livello di attendibilità) di almeno 75. Molti tipi di informazioni riservate sono definiti con più criteri. I criteri con un livello di accuratezza della corrispondenza superiore richiedono l'individuazione di ulteriori elementi di prova (ad esempio parole chiave, date o indirizzi), mentre i criteri con un livello di accuratezza della corrispondenza inferiore richiedono meno elementi di prova. In parole povere, più basso è il valore di accuratezza della corrispondenza **min**, più facile sarà che il contenuto soddisfi la condizione.</span><span class="sxs-lookup"><span data-stu-id="a350c-p115">The type of sensitive information that's detected has a match accuracy (or confidence level) of at least 75. Many sensitive information types are defined with multiple patterns, where a pattern with a higher match accuracy requires more evidence to be found (such as keywords, dates, or addresses), while a pattern with a lower match accuracy requires less evidence. Simply put, the lower the **min** match accuracy, the easier it is for content to match the condition.</span></span> 
    
<span data-ttu-id="a350c-178">Per altre informazioni su queste opzioni, vedere [Tuning rules to make them easier or harder to match](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match) (Ottimizzazione delle regole per rendere più facile o difficile la corrispondenza).</span><span class="sxs-lookup"><span data-stu-id="a350c-178">For more information on these options, see [Tuning rules to make them easier or harder to match](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span></span>
    
![Opzioni per l'identificazione dei tipi di informazioni riservate](../media/de255881-f596-4c8d-8359-e974e3a0819a.png)
  
### <a name="auto-apply-labels-to-content-with-keywords-or-searchable-properties"></a><span data-ttu-id="a350c-180">Applicare automaticamente etichette al contenuto con parole chiave o con proprietà disponibili per le ricerche</span><span class="sxs-lookup"><span data-stu-id="a350c-180">Auto-apply labels to content with keywords or searchable properties</span></span>

<span data-ttu-id="a350c-p116">È possibile applicare automaticamente etichette al contenuto che soddisfa determinate condizioni. Le condizioni disponibili ora supportano l'applicazione di un'etichetta al contenuto che include parole, frasi, valori o proprietà disponibili per le ricerche specifiche. È possibile perfezionare la query usando operatori di ricerca come AND, OR e NOT.</span><span class="sxs-lookup"><span data-stu-id="a350c-p116">You can auto-apply labels to content that satisfies certain conditions. The conditions now available support applying a label to content that contains specific words, phrases, or values of searchable properties. You can refine your query by using search operators like AND, OR, and NOT.</span></span>

<span data-ttu-id="a350c-184">Per altre informazioni sulla sintassi della query, vedere:</span><span class="sxs-lookup"><span data-stu-id="a350c-184">For more information on query syntax, see:</span></span>

- [<span data-ttu-id="a350c-185">Riferimenti per la sintassi di Keyword Query Language (KQL)</span><span class="sxs-lookup"><span data-stu-id="a350c-185">Keyword Query Language (KQL) syntax reference</span></span>](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)

<span data-ttu-id="a350c-p117">Le etichette basate su query usano l’indice di ricerca per identificare il contenuto. Per altre informazioni sulle proprietà disponibili per la ricerca valide, vedere:</span><span class="sxs-lookup"><span data-stu-id="a350c-p117">Query-based labels use the search index to identify content. For more information on valid searchable properties, see:</span></span>

- [<span data-ttu-id="a350c-188">Query con parole chiave e condizioni di ricerca per la Ricerca contenuto</span><span class="sxs-lookup"><span data-stu-id="a350c-188">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
- [<span data-ttu-id="a350c-189">Panoramica delle proprietà gestite e sottoposte a ricerca per indicizzazione in SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="a350c-189">Overview of crawled and managed properties in SharePoint Server</span></span>](https://docs.microsoft.com/SharePoint/technical-reference/crawled-and-managed-properties-overview)

<span data-ttu-id="a350c-190">Esempi di query:</span><span class="sxs-lookup"><span data-stu-id="a350c-190">Examples queries:</span></span>

- <span data-ttu-id="a350c-191">Exchange</span><span class="sxs-lookup"><span data-stu-id="a350c-191">Exchange</span></span>
    - <span data-ttu-id="a350c-192">subject:"Quarterly Financials"</span><span class="sxs-lookup"><span data-stu-id="a350c-192">subject:"Quarterly Financials"</span></span>
    - <span data-ttu-id="a350c-193">recipients:garthf</span><span class="sxs-lookup"><span data-stu-id="a350c-193">recipients:garthf</span></span><!--nolink--><span data-ttu-id="a350c-194">@contoso.com</span><span class="sxs-lookup"><span data-stu-id="a350c-194">@contoso.com</span></span>
- <span data-ttu-id="a350c-195">SharePoint e OneDrive</span><span class="sxs-lookup"><span data-stu-id="a350c-195">SharePoint and OneDrive</span></span>
    - <span data-ttu-id="a350c-196">contenttype:contract</span><span class="sxs-lookup"><span data-stu-id="a350c-196">contenttype:contract</span></span>
    - <span data-ttu-id="a350c-197">site:https</span><span class="sxs-lookup"><span data-stu-id="a350c-197">site:https</span></span><!--nolink--><span data-ttu-id="a350c-198">://contoso.sharepoint.com/sites/teams/procurement AND contenttype:contract</span><span class="sxs-lookup"><span data-stu-id="a350c-198">://contoso.sharepoint.com/sites/teams/procurement AND contenttype:contract</span></span>

![Editor di query](../media/ac5b8e5e-7453-4ec7-905c-160df57298d3.png)


### <a name="auto-apply-labels-to-content-by-using-trainable-classifiers"></a><span data-ttu-id="a350c-200">Etichette applicate automaticamente al contenuto con classificatori sottoponibili a training</span><span class="sxs-lookup"><span data-stu-id="a350c-200">Auto-apply labels to content by using trainable classifiers</span></span>

<span data-ttu-id="a350c-201">Se si sceglie l'opzione del classificatore sottoponibile a training, è possibile selezionare un classificatore predefinito oppure personalizzato.</span><span class="sxs-lookup"><span data-stu-id="a350c-201">When you choose the option for a trainable classifier, you can select one of the built-in classifiers, or a custom classifier.</span></span> <span data-ttu-id="a350c-202">I classificatori predefiniti includono i **curriculum**, il **codice sorgente**, le **molestie mirate**, i **contenuti volgari** e le **minacce**:</span><span class="sxs-lookup"><span data-stu-id="a350c-202">The built-in classifiers include **Resumes**, **SourceCode**, **Targeted Harassment**, **Profanity**, and **Threat**:</span></span>

![Scegliere un classificatore sottoponibile a training](../media/retention-label-classifers.png)

<span data-ttu-id="a350c-204">Per applicare automaticamente un'etichetta utilizzando questa opzione, i siti e le cassette postali di SharePoint Online devono avere almeno 10 MB di dati.</span><span class="sxs-lookup"><span data-stu-id="a350c-204">To automatically apply a label by using this option, SharePoint Online sites and mailboxes must have at least 10 MB of data.</span></span>

<span data-ttu-id="a350c-205">Per altre informazioni sui classificatori sottoponibili a training, vedere [Introduzione ai classificatori sottoponibili a training (anteprima)](classifier-getting-started-with.md).</span><span class="sxs-lookup"><span data-stu-id="a350c-205">For more information about trainable classifiers, see [Getting started with trainable classifiers (preview)](classifier-getting-started-with.md).</span></span>

<span data-ttu-id="a350c-206">Per avere un esempio di configurazione, vedere [Come preparare e usare un classificatore integrato](classifier-using-a-ready-to-use-classifier.md#how-to-verify-that-a-built-in-classifier-will-meet-your-needs).</span><span class="sxs-lookup"><span data-stu-id="a350c-206">For an example configuration, see [How to prepare for and use a built-in classifier](classifier-using-a-ready-to-use-classifier.md#how-to-verify-that-a-built-in-classifier-will-meet-your-needs).</span></span>

## <a name="how-long-it-takes-for-retention-labels-to-take-effect"></a><span data-ttu-id="a350c-207">Tempo necessario per l'applicazione delle etichette di conservazione</span><span class="sxs-lookup"><span data-stu-id="a350c-207">How long it takes for retention labels to take effect</span></span>

<span data-ttu-id="a350c-208">Quando si pubblicano o si applicano automaticamente le etichette di conservazione, queste non hanno effetto immediato:</span><span class="sxs-lookup"><span data-stu-id="a350c-208">When you publish or auto-apply retention labels, they don't take effect immediately:</span></span>
  
1. <span data-ttu-id="a350c-209">Per prima cosa i criteri di etichetta devono essere sincronizzati dall'interfaccia di amministrazione alle posizioni indicate nei criteri.</span><span class="sxs-lookup"><span data-stu-id="a350c-209">First the label policy needs to be synced from the admin center to the locations in the policy.</span></span>
    
2. <span data-ttu-id="a350c-210">Quindi, la posizione potrebbe richiedere del tempo per rendere disponibili le etichette di conservazione pubblicate agli utenti finali o per applicare automaticamente etichette al contenuto.</span><span class="sxs-lookup"><span data-stu-id="a350c-210">Then the location might require time to make published retention labels available to end users or time to auto-apply labels to content.</span></span> <span data-ttu-id="a350c-211">Il tempo necessario dipende dalla posizione e dal tipo di etichetta di conservazione.</span><span class="sxs-lookup"><span data-stu-id="a350c-211">How long this takes depends on the location and type of retention label.</span></span>
    
### <a name="published-retention-labels"></a><span data-ttu-id="a350c-212">Etichette di conservazione pubblicate</span><span class="sxs-lookup"><span data-stu-id="a350c-212">Published retention labels</span></span>

<span data-ttu-id="a350c-p120">Se si pubblicano etichette di conservazione in SharePoint o OneDrive, può essere necessario un giorno perché le etichette di conservazione siano visibili agli utenti finali. Se si pubblicano etichette di conservazione in Exchange, possono essere necessari 7 giorni perché le etichette di conservazione siano visibili agli utenti finali, inoltre la cassetta postale deve contenere almeno 10 MB di dati.</span><span class="sxs-lookup"><span data-stu-id="a350c-p120">If you publish retention labels to SharePoint or OneDrive, it can take one day for those retention labels to appear for end users. In addition, if you publish retention labels to Exchange, it can take 7 days for those retention labels to appear for end users, and the mailbox needs to contain at least 10 MB of data.</span></span>
  
![Diagramma del momento in cui le etichette manuali hanno effetto](../media/b19f3a10-f625-45bf-9a53-dd14df02ae7c.png)
  
### <a name="auto-apply-retention-labels"></a><span data-ttu-id="a350c-216">Applicare automaticamente etichette di conservazione</span><span class="sxs-lookup"><span data-stu-id="a350c-216">Auto-apply retention labels</span></span>

<span data-ttu-id="a350c-217">In caso di applicazione automatica di etichette di conservazione ai contenuti che soddisfano condizioni specifiche, possono essere necessari 7 giorni prima che le etichette di conservazione vengano applicate a tutto il contenuto esistente che soddisfa le condizioni.</span><span class="sxs-lookup"><span data-stu-id="a350c-217">If you auto-apply retention labels to content matching specific conditions, it can take seven days for the retention labels to be applied to all existing content that matches the conditions.</span></span>
  
![Diagramma di disponibilità delle etichette applicate automaticamente](../media/b8c00657-477a-4ade-b914-e643ef97a10d.png)
  
### <a name="how-to-check-on-the-status-of-retention-labels-published-to-exchange"></a><span data-ttu-id="a350c-219">Come verificare lo stato delle etichette di conservazione pubblicate in Exchange</span><span class="sxs-lookup"><span data-stu-id="a350c-219">How to check on the status of retention labels published to Exchange</span></span>

<span data-ttu-id="a350c-220">In Exchange Online le etichette di conservazione vengono rese disponibili agli utenti finali mediante un processo eseguito ogni sette giorni.</span><span class="sxs-lookup"><span data-stu-id="a350c-220">In Exchange Online, retention labels are made available to end users by a process that runs every seven days.</span></span> <span data-ttu-id="a350c-221">Usando Powershell è possibile vedere quando è stato eseguito per l'ultima volta questo processo e quindi identificare quando verrà eseguito nuovamente.</span><span class="sxs-lookup"><span data-stu-id="a350c-221">By using Powershell, you can see when this process last ran and therefore identify when it will run again.</span></span>
  
1. <span data-ttu-id="a350c-222">[Connettersi a Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=799773).</span><span class="sxs-lookup"><span data-stu-id="a350c-222">[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=799773).</span></span>
    
2. <span data-ttu-id="a350c-223">Eseguire questi comandi.</span><span class="sxs-lookup"><span data-stu-id="a350c-223">Run these commands.</span></span>
    
   ```powershell
   $logProps = Export-MailboxDiagnosticLogs <user> -ExtendedProperties
   ```

   ```powershell
   $xmlprops = [xml]($logProps.MailboxLog)
   ```

   ```powershell
   $xmlprops.Properties.MailboxTable.Property | ? {$_.Name -like "ELC*"}
   ```

<span data-ttu-id="a350c-224">Nei risultati, la proprietà `ELCLastSuccessTimeStamp` (UTC) mostra quando il sistema ha elaborato la casetta postale per l'ultima volta.</span><span class="sxs-lookup"><span data-stu-id="a350c-224">In the results, the `ELCLastSuccessTimeStamp` (UTC) property shows when the system last processed your mailbox.</span></span> <span data-ttu-id="a350c-225">Se questa operazione non è stata eseguita da quando è stato creato il criterio, le etichette non verranno visualizzate.</span><span class="sxs-lookup"><span data-stu-id="a350c-225">If it has not happened since the time you created the policy, the labels are not going to appear.</span></span> <span data-ttu-id="a350c-226">Per forzare l'elaborazione, eseguire `Start-ManagedFolderAssistant -Identity <user>`.</span><span class="sxs-lookup"><span data-stu-id="a350c-226">To force processing, run  `Start-ManagedFolderAssistant -Identity <user>`.</span></span>
    
<span data-ttu-id="a350c-227">Se le etichette non compaiono in Outlook sul web e si ritiene che invece debbano comparire, svuotare la cache del browser (CTRL+F5).</span><span class="sxs-lookup"><span data-stu-id="a350c-227">If labels aren't appearing in Outlook on the web and you think they should be, make sure to clear the cache in your browser (CTRL+F5).</span></span>
    

## <a name="updating-retention-labels-and-their-policies"></a><span data-ttu-id="a350c-228">Aggiornare le etichette di conservazione e i criteri</span><span class="sxs-lookup"><span data-stu-id="a350c-228">Updating retention labels and their policies</span></span>

<span data-ttu-id="a350c-229">Quando si modifica un'etichetta di conservazione, un criterio di etichetta di conservazione o un criterio di applicazione automatica e l'etichetta di conservazione o il criterio è già applicato al contenuto, le impostazioni aggiornate verranno applicate automaticamente a tale contenuto oltre che a quello identificato per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="a350c-229">When you edit a retention label, retention label policy, or auto-apply policy, and the retention label or policy is already applied to content, your updated settings will automatically be applied to this content in addition to content that's newly identified.</span></span>

<span data-ttu-id="a350c-230">Alcune impostazioni non possono essere modificate dopo aver creato e salvato l'etichetta o i criteri, tra cui:</span><span class="sxs-lookup"><span data-stu-id="a350c-230">Some settings can't be changed after the label or policy is created and saved, which include:</span></span>
- <span data-ttu-id="a350c-231">Le impostazioni di conservazione tranne il periodo di conservazione, a meno che l'etichetta non sia stata configurata per conservare o eliminare il contenuto in base alla data di creazione.</span><span class="sxs-lookup"><span data-stu-id="a350c-231">The retention settings except the retention period, unless you've configured the label to retain or delete the content based on when it was created.</span></span>
- <span data-ttu-id="a350c-232">L'opzione per classificare come record.</span><span class="sxs-lookup"><span data-stu-id="a350c-232">The option to classify as a record.</span></span>

## <a name="find-the-powershell-cmdlets-for-retention-labels"></a><span data-ttu-id="a350c-233">Trovare i cmdlet di PowerShell per le etichette di conservazione</span><span class="sxs-lookup"><span data-stu-id="a350c-233">Find the PowerShell cmdlets for retention labels</span></span>

<span data-ttu-id="a350c-234">Per usare i cmdlet per le etichette di conservazione:</span><span class="sxs-lookup"><span data-stu-id="a350c-234">To use the retention label cmdlets:</span></span>
  
1. [<span data-ttu-id="a350c-235">Connettersi a PowerShell in Centro sicurezza e conformità di Office 365</span><span class="sxs-lookup"><span data-stu-id="a350c-235">Connect to the Office 365 Security & Compliance Center Powershell</span></span>](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)
    
2. <span data-ttu-id="a350c-236">Usare questi cmdlet del Centro sicurezza e conformità di Office 365:</span><span class="sxs-lookup"><span data-stu-id="a350c-236">Use these Office 365 Security & Compliance Center cmdlets:</span></span>
    
    - [<span data-ttu-id="a350c-237">Get-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="a350c-237">Get-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancetag)
    
    - [<span data-ttu-id="a350c-238">New-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="a350c-238">New-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-compliancetag)
    
    - [<span data-ttu-id="a350c-239">Remove-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="a350c-239">Remove-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/remove-compliancetag)
    
    - [<span data-ttu-id="a350c-240">Set-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="a350c-240">Set-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-compliancetag)
    
    - [<span data-ttu-id="a350c-241">Enable-ComplianceTagStorage</span><span class="sxs-lookup"><span data-stu-id="a350c-241">Enable-ComplianceTagStorage</span></span>](https://docs.microsoft.com/powershell/module/exchange/enable-compliancetagstorage)
    
    - [<span data-ttu-id="a350c-242">Get-ComplianceTagStorage</span><span class="sxs-lookup"><span data-stu-id="a350c-242">Get-ComplianceTagStorage</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancetagstorage)
    
    - [<span data-ttu-id="a350c-243">Get-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="a350c-243">Get-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancepolicy)
    
    - [<span data-ttu-id="a350c-244">New-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="a350c-244">New-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancepolicy)
    
    - [<span data-ttu-id="a350c-245">Remove-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="a350c-245">Remove-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/remove-retentioncompliancepolicy)
    
    - [<span data-ttu-id="a350c-246">Set-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="a350c-246">Set-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy)
    
    - [<span data-ttu-id="a350c-247">Get-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="a350c-247">Get-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancerule)
    
    - [<span data-ttu-id="a350c-248">New-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="a350c-248">New-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancerule)
    
    - [<span data-ttu-id="a350c-249">Remove-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="a350c-249">Remove-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/remove-retentioncompliancerule)
    
    - [<span data-ttu-id="a350c-250">Set-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="a350c-250">Set-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancerule)
