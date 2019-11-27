---
title: Configurare il rilevamento dei privilegi avvocato-client in Advanced eDiscovery
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
ms.assetid: ''
ROBOTS: NOINDEX, NOFOLLOW
description: Opt-in e utilizzo del modello di rilevamento dei privilegi avvocato-client per utilizzare il rilevamento basato sull'apprendimento automatico del contenuto con privilegi quando si esaminano i contenuti in un caso avanzato di eDiscovery.
ms.openlocfilehash: a483941ba5d28527eb509f2e1bbd129434430244
ms.sourcegitcommit: 7f26840a4330b0fd29807ec091c6915d283b3dd2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2019
ms.locfileid: "39603780"
---
# <a name="set-up-attorney-client-privilege-detection-in-advanced-ediscovery"></a><span data-ttu-id="b5d0a-103">Configurare il rilevamento dei privilegi avvocato-client in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="b5d0a-103">Set up attorney-client privilege detection in Advanced eDiscovery</span></span>

<span data-ttu-id="b5d0a-104">Un aspetto importante e costoso della fase di revisione di un processo di eDiscovery consiste nell'esaminare i documenti per il contenuto con privilegi.</span><span class="sxs-lookup"><span data-stu-id="b5d0a-104">A major and costly aspect of the review phase of any eDiscovery process is reviewing documents for privileged content.</span></span> <span data-ttu-id="b5d0a-105">Advanced eDiscovery fornisce il rilevamento basato sull'apprendimento automatico del contenuto con privilegi per rendere più efficiente questo processo.</span><span class="sxs-lookup"><span data-stu-id="b5d0a-105">Advanced eDiscovery provides machine learning-based detection of privileged content to make this process more efficient.</span></span> <span data-ttu-id="b5d0a-106">Questa funzionalità è denominata *rilevamento dei privilegi di avvocato-client*.</span><span class="sxs-lookup"><span data-stu-id="b5d0a-106">This feature is called *attorney-client privilege detection*.</span></span>

> [!NOTE]
> <span data-ttu-id="b5d0a-107">Prima di poterlo utilizzare, è necessario optare per il modello di rilevamento dei privilegi avvocato-client.</span><span class="sxs-lookup"><span data-stu-id="b5d0a-107">You must opt in to the attorney-client privilege detection model before you can use it.</span></span> <span data-ttu-id="b5d0a-108">Vedere il [passaggio 1](#step-1-opt-in-to-attorney-client-privilege-detection) per le istruzioni.</span><span class="sxs-lookup"><span data-stu-id="b5d0a-108">See [Step 1](#step-1-opt-in-to-attorney-client-privilege-detection) for instructions.</span></span>

## <a name="how-does-it-work"></a><span data-ttu-id="b5d0a-109">Come funziona</span><span class="sxs-lookup"><span data-stu-id="b5d0a-109">How does it work?</span></span>

<span data-ttu-id="b5d0a-110">Quando è abilitato il rilevamento dei privilegi di avvocato-client, tutti i documenti in un set di revisione verranno elaborati dal modello di rilevamento del privilegio avvocato-client quando si [analizzano i dati](analyzing-data-in-review-set.md) nel set di revisione.</span><span class="sxs-lookup"><span data-stu-id="b5d0a-110">When attorney-client privilege detection is enabled, all documents in a review set will be processed by the attorney-client privilege detection model when you [analyze the data](analyzing-data-in-review-set.md) in the review set.</span></span> <span data-ttu-id="b5d0a-111">Il modello cerca due elementi:</span><span class="sxs-lookup"><span data-stu-id="b5d0a-111">The model looks for two things:</span></span>

- <span data-ttu-id="b5d0a-112">Contenuto con privilegi: il modello utilizza l'apprendimento automatico per determinare la probabilità che il documento contenga contenuti di natura legale.</span><span class="sxs-lookup"><span data-stu-id="b5d0a-112">Privileged content – The model uses machine learning to determine the likelihood that the document contains content that is legal in nature.</span></span>

- <span data-ttu-id="b5d0a-113">Partecipanti – nell'ambito della configurazione del rilevamento dei privilegi del procuratore-client, è necessario inviare un elenco di avvocati per la propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b5d0a-113">Participants – As part of setting up attorney-client privilege detection, you have to submit a list of attorneys for your organization.</span></span> <span data-ttu-id="b5d0a-114">Il modello confronta quindi i partecipanti del documento con l'elenco degli avvocati per determinare se un documento ha almeno un partecipante al procuratore.</span><span class="sxs-lookup"><span data-stu-id="b5d0a-114">The model then compares the participants of the document with the attorney list to determine if a document has at least one attorney participant.</span></span>

<span data-ttu-id="b5d0a-115">Il modello produce le tre proprietà seguenti per ogni documento:</span><span class="sxs-lookup"><span data-stu-id="b5d0a-115">The model produces the following three properties for every document:</span></span>

- <span data-ttu-id="b5d0a-116">**AttorneyClientPrivilegeScore** – la probabilità che il documento sia di natura legale; i valori per il punteggio sono compresi tra **0** e **1**.</span><span class="sxs-lookup"><span data-stu-id="b5d0a-116">**AttorneyClientPrivilegeScore** – The likelihood the document is legal in nature; the values for the score are between **0** and **1**.</span></span>

- <span data-ttu-id="b5d0a-117">**HasAttorney** : questa proprietà è impostata su **true** se uno dei partecipanti al documento è elencato nell'elenco di avvocati. in caso contrario, il valore è **false**.</span><span class="sxs-lookup"><span data-stu-id="b5d0a-117">**HasAttorney** – This property is set to **true** if one of the document participants is listed in the attorney list; otherwise the value is **false**.</span></span> <span data-ttu-id="b5d0a-118">Il valore viene impostato su **false** anche se l'organizzazione non ha caricato un elenco di avvocati.</span><span class="sxs-lookup"><span data-stu-id="b5d0a-118">The value is also set to **false** if your organization didn't upload an attorney list.</span></span>

- <span data-ttu-id="b5d0a-119">**Privilegio** : questa proprietà è impostata su **true** se il valore di **AttorneyClientPrivilegeScore** è al di sopra della soglia *o* se il documento ha un partecipante al procuratore; in caso contrario, il valore è impostato su **false**.</span><span class="sxs-lookup"><span data-stu-id="b5d0a-119">**IsPrivilege** – This property is set to **true** if the value for **AttorneyClientPrivilegeScore** is above the threshold *or* if the document has an attorney participant; otherwise the value is set to **false**.</span></span>

<span data-ttu-id="b5d0a-120">Queste proprietà e i relativi valori corrispondenti vengono aggiunte ai metadati del file dei documenti in un set di revisione, come illustrato nella schermata seguente:</span><span class="sxs-lookup"><span data-stu-id="b5d0a-120">These properties (and their corresponding values) are added to the file metadata of the documents in a review set, as shown in the following screenshot:</span></span>

![Proprietà del privilegio avvocato-client mostrate nei metadati dei file](media/AeDAttorneyClientPrivilegeMetadata.png)

<span data-ttu-id="b5d0a-122">Queste tre proprietà sono anche ricercabili all'interno di un set di revisione.</span><span class="sxs-lookup"><span data-stu-id="b5d0a-122">These three properties are also searchable within a review set.</span></span> <span data-ttu-id="b5d0a-123">Per ulteriori informazioni, vedere [eseguire una query sui dati in un set di revisione](review-set-search.md).</span><span class="sxs-lookup"><span data-stu-id="b5d0a-123">For more information, see [Query the data in a review set](review-set-search.md).</span></span>

## <a name="set-up-the-attorney-client-privilege-detection-model"></a><span data-ttu-id="b5d0a-124">Configurare il modello di rilevamento dei privilegi avvocato-client</span><span class="sxs-lookup"><span data-stu-id="b5d0a-124">Set up the attorney-client privilege detection model</span></span>

<span data-ttu-id="b5d0a-125">Per abilitare il modello di rilevamento dei privilegi avvocato-client, è necessario che l'organizzazione Opti e quindi carichi un elenco di avvocati.</span><span class="sxs-lookup"><span data-stu-id="b5d0a-125">To enable the attorney-client privilege detection model, your organization has to opt in and then upload an attorney list.</span></span>

### <a name="step-1-opt-in-to-attorney-client-privilege-detection"></a><span data-ttu-id="b5d0a-126">Passaggio 1: opt-in per il rilevamento dei privilegi avvocato-client</span><span class="sxs-lookup"><span data-stu-id="b5d0a-126">Step 1: Opt in to attorney-client privilege detection</span></span>

<span data-ttu-id="b5d0a-127">Come indicato in precedenza, il modello di rilevamento dei privilegi del procuratore-client è in anteprima.</span><span class="sxs-lookup"><span data-stu-id="b5d0a-127">As previously stated, the attorney-client privilege detection model is in Preview.</span></span> <span data-ttu-id="b5d0a-128">Pertanto, una persona all'interno dell'organizzazione eDiscovery Administrator (un membro del sottogruppo amministratore di eDiscovery nel gruppo di ruoli di eDiscovery Manager) deve scegliere di rendere disponibile il modello nei casi di eDiscovery avanzati.</span><span class="sxs-lookup"><span data-stu-id="b5d0a-128">Therefore a person in your organization eDiscovery Administrator (a member of the eDiscovery Administrator subgroup in the eDiscovery Manager role group) must opt in to make the model available in your Advanced eDiscovery cases.</span></span>

1. <span data-ttu-id="b5d0a-129">Nel centro sicurezza & conformità, accedere a **eDiscovery > Advanced eDiscovery**.</span><span class="sxs-lookup"><span data-stu-id="b5d0a-129">In the Security & Compliance Center, go to **eDiscovery > Advanced eDiscovery**.</span></span>

2. <span data-ttu-id="b5d0a-130">Nella Home page di **Advanced eDiscovery** fare clic su **Configura caratteristiche sperimentali**nel riquadro **Impostazioni** .</span><span class="sxs-lookup"><span data-stu-id="b5d0a-130">On the **Advanced eDiscovery** home page, in the **Settings** tile, select **Configure experimental features**.</span></span>

   ![Selezionare "Configura funzionalità sperimentali"](media/AeDExperimentalFeatures.png)

3. <span data-ttu-id="b5d0a-132">Nella scheda **caratteristiche sperimentali** selezionare **Gestisci impostazione di privilegio avvocato-client**.</span><span class="sxs-lookup"><span data-stu-id="b5d0a-132">On the **Experimental features** tab, select **Manage attorney-client privilege setting**.</span></span>

4. <span data-ttu-id="b5d0a-133">Nella pagina del riquadro a comparsa dei **privilegi avvocato-client** , utilizzare l'interruttore per attivare la funzionalità e quindi selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b5d0a-133">On the **Attorney-client privilege** flyout page, use the toggle to turn on the feature and then select **Save**.</span></span>

### <a name="step-2-upload-a-list-of-attorneys-optional"></a><span data-ttu-id="b5d0a-134">Passaggio 2: caricare un elenco di avvocati (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="b5d0a-134">Step 2: Upload a list of attorneys (optional)</span></span>

<span data-ttu-id="b5d0a-135">Per sfruttare al meglio il modello di rilevamento dei privilegi avvocato-client e utilizzare i risultati del **procuratore** o del rilevamento **potenzialmente privilegiato** descritto in precedenza, si consiglia di caricare un elenco di indirizzi di posta elettronica per gli avvocati e gli addetti legali che lavorano per la propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b5d0a-135">To take full advantage of the attorney-client privilege detection model and use the results of the **Has Attorney** or **Potentially Privileged** detection that was previously described, we recommend that you upload a list of email addresses for the lawyers and legal personnel who work for your organization.</span></span> 

<span data-ttu-id="b5d0a-136">Per caricare un elenco di avvocati per l'utilizzo da parte del modello di rilevamento dei privilegi avvocato-client:</span><span class="sxs-lookup"><span data-stu-id="b5d0a-136">To upload an attorney list for use by the attorney-client privilege detection model:</span></span>

1. <span data-ttu-id="b5d0a-137">Creare un file. csv (senza una riga di intestazione) e aggiungere l'indirizzo di posta elettronica per ogni persona appropriata su una riga distinta.</span><span class="sxs-lookup"><span data-stu-id="b5d0a-137">Create a .csv file (without a header row) and add the email address for each appropriate person on a separate line.</span></span> <span data-ttu-id="b5d0a-138">Salvare il file nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="b5d0a-138">Save this file to your local computer.</span></span>

2. <span data-ttu-id="b5d0a-139">Nella Home page di **Advanced eDiscovery** fare clic su **Configura caratteristiche sperimentali**nella sezione **Impostazioni** e quindi selezionare **Gestisci impostazione privilegio avvocato-client**.</span><span class="sxs-lookup"><span data-stu-id="b5d0a-139">On the **Advanced eDiscovery** home page, in the **Settings** tile, select **Configure experimental features**, and then select **Manage attorney-client privilege setting**.</span></span>

   <span data-ttu-id="b5d0a-140">Viene visualizzata la pagina **Privilege avvocato-client** e l'interruttore di **rilevamento dei privilegi del procuratore-client** è attivato.</span><span class="sxs-lookup"><span data-stu-id="b5d0a-140">The **Attorney-client privilege** page is displayed, and the **Attorney-client privilege detection** toggle is turned on.</span></span>

   ![Pagina del riquadro a comparsa dei privilegi avvocato-cliente](media/AeDUploadAttorneyList.png)

3. <span data-ttu-id="b5d0a-142">Selezionare **Sfoglia** e quindi individuare e selezionare il file. csv creato nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="b5d0a-142">Select **Browse** and then find and select the .csv file that you created in step 1.</span></span>

4. <span data-ttu-id="b5d0a-143">Selezionare **Salva** per caricare l'elenco degli avvocati.</span><span class="sxs-lookup"><span data-stu-id="b5d0a-143">Select **Save** to upload the attorney list.</span></span>

## <a name="use-the-attorney-client-privilege-detection-model"></a><span data-ttu-id="b5d0a-144">Utilizzare il modello di rilevamento dei privilegi avvocato-client</span><span class="sxs-lookup"><span data-stu-id="b5d0a-144">Use the attorney-client privilege detection model</span></span>

<span data-ttu-id="b5d0a-145">Seguire la procedura descritta in questa sezione per utilizzare il rilevamento dei privilegi di avvocato-client per i documenti in un set di revisione.</span><span class="sxs-lookup"><span data-stu-id="b5d0a-145">Follow the steps in this section to use attorney-client privilege detection for documents in a review set.</span></span>

### <a name="step-1-create-a-smart-tag-group-with-attorney-client-privilege-detection-model"></a><span data-ttu-id="b5d0a-146">Passaggio 1: creare un gruppo di smart tag con il modello di rilevamento dei privilegi avvocato-client</span><span class="sxs-lookup"><span data-stu-id="b5d0a-146">Step 1: Create a smart tag group with attorney-client privilege detection model</span></span>

<span data-ttu-id="b5d0a-147">Uno dei modi principali per visualizzare i risultati del rilevamento dei privilegi del procuratore-client nel processo di revisione consiste nell'utilizzare un gruppo di smart tag.</span><span class="sxs-lookup"><span data-stu-id="b5d0a-147">One of the primary ways to see the results of attorney-client privilege detection in your review process is by using a smart tag group.</span></span> <span data-ttu-id="b5d0a-148">Un gruppo di smart tag indica i risultati del rilevamento dei privilegi avvocato-client e Visualizza i risultati in linea accanto ai tag in un gruppo di smart tag.</span><span class="sxs-lookup"><span data-stu-id="b5d0a-148">A smart tag group indicates the results of the attorney-client privilege detection and shows the results in-line next to the tags in a smart tag group.</span></span> <span data-ttu-id="b5d0a-149">In questo modo è possibile identificare rapidamente i documenti potenzialmente privilegiati durante la revisione del documento.</span><span class="sxs-lookup"><span data-stu-id="b5d0a-149">This lets you quickly identify potentially privileged documents during document review.</span></span> <span data-ttu-id="b5d0a-150">Inoltre, è possibile utilizzare i tag del gruppo smart tag per contrassegnare i documenti come privilegiati o non privilegiati.</span><span class="sxs-lookup"><span data-stu-id="b5d0a-150">Additionally, you can also use the tags in the smart tag group to tag documents as privileged or non-privileged.</span></span> <span data-ttu-id="b5d0a-151">Per ulteriori informazioni sugli smart tag, vedere [configurare gli smart tag in Advanced eDiscovery](smart-tags.md).</span><span class="sxs-lookup"><span data-stu-id="b5d0a-151">For more information about smart tags, see [Set up smart tags in Advanced eDiscovery](smart-tags.md).</span></span>

1. <span data-ttu-id="b5d0a-152">Nel set di revisione che contiene i documenti analizzati nel passaggio 1, selezionare **Gestisci Revisione set** e quindi selezionare **Gestisci Tag**.</span><span class="sxs-lookup"><span data-stu-id="b5d0a-152">In the review set that contains the documents that you analyzed in Step 1, select **Manage review set** and then select **Manage tags**.</span></span>
 
2. <span data-ttu-id="b5d0a-153">In **tag**selezionare l'elenco a discesa accanto a **Aggiungi gruppo** e quindi fare clic su **Aggiungi gruppo smart tag**.</span><span class="sxs-lookup"><span data-stu-id="b5d0a-153">Under **Tags**, select the pull-down next to **Add group** and then select **Add smart tag group**.</span></span>

   ![Seleziona "Aggiungi gruppo smart tag"](media/AeDCreateSmartTag.png)

3. <span data-ttu-id="b5d0a-155">Nella pagina **scegliere un modello per la smart tag** scegliere **Seleziona** accanto a **privilegio avvocato-client**.</span><span class="sxs-lookup"><span data-stu-id="b5d0a-155">On the **Choose a model for your smart tag** page, choose **Select** next to **Attorney-client privilege**.</span></span>

   <span data-ttu-id="b5d0a-156">Viene visualizzato un gruppo di tag denominato **procuratore-Client Privilege** .</span><span class="sxs-lookup"><span data-stu-id="b5d0a-156">A tag group named **Attorney-client privilege** is displayed.</span></span> <span data-ttu-id="b5d0a-157">Contiene due tag figlio denominati **positivi** e **negativi**, che corrispondono ai possibili risultati prodotti dal modello.</span><span class="sxs-lookup"><span data-stu-id="b5d0a-157">It contains two child tags named **Positive** and **Negative**, which correspond to the possible results produced by the model.</span></span>

   ![Gruppo smart tag del privilegio avvocato-cliente](media/AeDAttorneyClientSmartTagGroup.png)

3. <span data-ttu-id="b5d0a-159">Rinominare il gruppo e i tag dei tag in base alle proprie esigenze per la revisione.</span><span class="sxs-lookup"><span data-stu-id="b5d0a-159">Rename the tag group and tags as appropriate for your review.</span></span> <span data-ttu-id="b5d0a-160">Ad esempio, è possibile rinominare **positivamente** con **privilegi** e **negativi** a **non privilegiati**.</span><span class="sxs-lookup"><span data-stu-id="b5d0a-160">For example, you can rename **Positive** to **Privileged** and **Negative** to **Not privileged**.</span></span>

### <a name="step-2-analyze-a-review-set"></a><span data-ttu-id="b5d0a-161">Passaggio 2: analizzare un set di Revisione</span><span class="sxs-lookup"><span data-stu-id="b5d0a-161">Step 2: Analyze a review set</span></span>

<span data-ttu-id="b5d0a-162">Quando si analizzano i documenti in un set di revisione, viene eseguito anche il modello di rilevamento dei privilegi di avvocato-client e le proprietà corrispondenti (descritte in [modalità di funzionamento?](#how-does-it-work) verranno aggiunte a tutti i documenti del set di revisione.</span><span class="sxs-lookup"><span data-stu-id="b5d0a-162">When you analyze the documents in a review set, the attorney-client privilege detection model will also run and the corresponding properties (described in [How does it work?](#how-does-it-work) will be added to every document in the review set.</span></span> <span data-ttu-id="b5d0a-163">Per ulteriori informazioni sull'analisi dei dati nel set di revisione, vedere [analyze data in a Review set in Advanced eDiscovery](analyzing-data-in-review-set.md).</span><span class="sxs-lookup"><span data-stu-id="b5d0a-163">For more information about analyzing data in review set, see [Analyze data in a review set in Advanced eDiscovery](analyzing-data-in-review-set.md).</span></span>

### <a name="step-3-use-the-smart-tag-group-for-review-of-privileged-content"></a><span data-ttu-id="b5d0a-164">Passaggio 3: utilizzare il gruppo smart tag per la revisione dei contenuti con privilegi</span><span class="sxs-lookup"><span data-stu-id="b5d0a-164">Step 3: Use the smart tag group for review of privileged content</span></span>

<span data-ttu-id="b5d0a-165">Dopo aver analizzato il set di revisione e aver configurato gli smart tag, il passaggio successivo consiste nel rivedere i documenti.</span><span class="sxs-lookup"><span data-stu-id="b5d0a-165">After analyzing the review set and setting up smart tags, the next step is to review the documents.</span></span> <span data-ttu-id="b5d0a-166">Se il modello ha determinato che il documento è potenzialmente privilegiato, lo smart tag corrispondente nel **Pannello di tagging** indicherà i risultati seguenti ottenuti dal rilevamento dei privilegi avvocato-client:</span><span class="sxs-lookup"><span data-stu-id="b5d0a-166">If the model has determined the document is potentially privileged, the corresponding smart tag in the **Tagging panel** will indicate the following results produced by the attorney-client privilege detection:</span></span>

- <span data-ttu-id="b5d0a-167">Se il documento contiene contenuto che potrebbe essere di natura legale, il **contenuto legale** dell'etichetta viene visualizzato accanto allo smart tag corrispondente, che in questo caso è il tag **positivo** predefinito.</span><span class="sxs-lookup"><span data-stu-id="b5d0a-167">If the document has content that may be legal in nature, the label **Legal content** is displayed next to the corresponding smart tag (which in this case is the default **Positive** tag).</span></span>

- <span data-ttu-id="b5d0a-168">Se il documento ha un partecipante che si trova nell'elenco di avvocati dell'organizzazione, viene visualizzato il **procuratore** di etichette accanto allo smart tag corrispondente (che in questo caso è anche il tag **positivo** predefinito).</span><span class="sxs-lookup"><span data-stu-id="b5d0a-168">If the document has a participant who is found in your organization's attorney list, the label **Attorney** is displayed next to the corresponding smart tag (which in this case is also the default **Positive** tag).</span></span>

- <span data-ttu-id="b5d0a-169">Se il documento contiene contenuto che potrebbe essere di natura legale *e* ha un partecipante trovato nell'elenco degli avvocati, vengono visualizzati sia il **contenuto legale** che le etichette del **procuratore** .</span><span class="sxs-lookup"><span data-stu-id="b5d0a-169">If the document has content that may be legal in nature *and* has a participant found in the attorney list, both the **Legal content**  and **Attorney** labels are displayed.</span></span> 

<span data-ttu-id="b5d0a-170">Se il modello determina che un documento non contiene contenuto di natura legale o che non contiene un partecipante all'elenco degli avvocati, non viene visualizzata alcuna etichetta nel pannello di tagging.</span><span class="sxs-lookup"><span data-stu-id="b5d0a-170">If the model determines that a document doesn't contain content that is legal in nature or doesn't contain a participant from the attorney list, then neither label is displayed in the tagging panel.</span></span>

<span data-ttu-id="b5d0a-171">Ad esempio, nelle schermate seguenti vengono visualizzati due documenti.</span><span class="sxs-lookup"><span data-stu-id="b5d0a-171">For example, the following screenshots show two documents.</span></span> <span data-ttu-id="b5d0a-172">Il primo contiene contenuto di natura legale e ha un partecipante trovato nell'elenco degli avvocati.</span><span class="sxs-lookup"><span data-stu-id="b5d0a-172">The first one contains content that is legal in nature and has a participant found in the list of attorneys.</span></span> <span data-ttu-id="b5d0a-173">La seconda non contiene né e pertanto non Visualizza etichette.</span><span class="sxs-lookup"><span data-stu-id="b5d0a-173">The second contains neither and therefore doesn't display any labels.</span></span>

![Documento con etichette legali e di contenuto legale](media/AeDTaggingPanelLegalContentAttorney.png)

![Documento senza etichette](media/AeDTaggingPanelNegative.png)

<span data-ttu-id="b5d0a-176">Dopo aver esaminato un documento per verificare se contiene contenuto con privilegi, è possibile contrassegnare il documento con il tag appropriato.</span><span class="sxs-lookup"><span data-stu-id="b5d0a-176">After you review a document to see if it contains privileged content, you can tag the document with the appropriate tag.</span></span>
