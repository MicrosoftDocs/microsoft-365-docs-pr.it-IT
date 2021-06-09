---
title: Configurare il rilevamento dei privilegi avvocato-client in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Usa il modello di rilevamento dei privilegi avvocato-client per usare il rilevamento basato su machine learning del contenuto con privilegi durante la revisione del contenuto in un Advanced eDiscovery caso.
ms.openlocfilehash: 73a0efeece7bc331045e9bbe1a1da56f9fd24700
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358042"
---
# <a name="set-up-attorney-client-privilege-detection-in-advanced-ediscovery"></a><span data-ttu-id="21043-103">Configurare il rilevamento dei privilegi avvocato-client in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="21043-103">Set up attorney-client privilege detection in Advanced eDiscovery</span></span>

<span data-ttu-id="21043-104">Un aspetto importante e dissario della fase di revisione di qualsiasi processo di eDiscovery è la revisione dei documenti per il contenuto con privilegi.</span><span class="sxs-lookup"><span data-stu-id="21043-104">A major and costly aspect of the review phase of any eDiscovery process is reviewing documents for privileged content.</span></span> <span data-ttu-id="21043-105">Advanced eDiscovery consente di rilevare il contenuto con privilegi basato sull'apprendimento automatico per rendere più efficiente questo processo.</span><span class="sxs-lookup"><span data-stu-id="21043-105">Advanced eDiscovery provides machine learning-based detection of privileged content to make this process more efficient.</span></span> <span data-ttu-id="21043-106">Questa funzionalità è denominata *rilevamento privilegi avvocato-client.*</span><span class="sxs-lookup"><span data-stu-id="21043-106">This feature is called *attorney-client privilege detection*.</span></span>

## <a name="how-does-it-work"></a><span data-ttu-id="21043-107">Come funziona?</span><span class="sxs-lookup"><span data-stu-id="21043-107">How does it work?</span></span>

<span data-ttu-id="21043-108">Quando il rilevamento dei privilegi avvocato-client è abilitato, tutti i documenti [in](analyzing-data-in-review-set.md) un set di revisione verranno elaborati dal modello di rilevamento dei privilegi avvocato-client quando si analizzano i dati nel set di revisione.</span><span class="sxs-lookup"><span data-stu-id="21043-108">When attorney-client privilege detection is enabled, all documents in a review set will be processed by the attorney-client privilege detection model when you [analyze the data](analyzing-data-in-review-set.md) in the review set.</span></span> <span data-ttu-id="21043-109">Il modello cerca due elementi:</span><span class="sxs-lookup"><span data-stu-id="21043-109">The model looks for two things:</span></span>

- <span data-ttu-id="21043-110">Contenuto con privilegi: il modello utilizza l'apprendimento automatico per determinare la probabilità che il documento contenga contenuto di natura legale.</span><span class="sxs-lookup"><span data-stu-id="21043-110">Privileged content – The model uses machine learning to determine the likelihood that the document contains content that is legal in nature.</span></span>

- <span data-ttu-id="21043-111">Partecipanti: nell'ambito della configurazione del rilevamento dei privilegi avvocato-client, è necessario inviare un elenco di avvocati per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="21043-111">Participants – As part of setting up attorney-client privilege detection, you have to submit a list of attorneys for your organization.</span></span> <span data-ttu-id="21043-112">Il modello confronta quindi i partecipanti al documento con l'elenco degli avvocati per determinare se un documento ha almeno un partecipante avvocato.</span><span class="sxs-lookup"><span data-stu-id="21043-112">The model then compares the participants of the document with the attorney list to determine if a document has at least one attorney participant.</span></span>

<span data-ttu-id="21043-113">Il modello produce le tre proprietà seguenti per ogni documento:</span><span class="sxs-lookup"><span data-stu-id="21043-113">The model produces the following three properties for every document:</span></span>

- <span data-ttu-id="21043-114">**AttorneyClientPrivilegeScore:** Probabilità che il documento sia di natura legale. i valori per il punteggio sono compresi tra **0** e **1**.</span><span class="sxs-lookup"><span data-stu-id="21043-114">**AttorneyClientPrivilegeScore:** The likelihood the document is legal in nature; the values for the score are between **0** and **1**.</span></span>

- <span data-ttu-id="21043-115">**HasAttorney:** Questa proprietà è impostata su **true** se uno dei partecipanti al documento è elencato nell'elenco degli avvocati. in caso contrario, il valore è **false**.</span><span class="sxs-lookup"><span data-stu-id="21043-115">**HasAttorney:** This property is set to **true** if one of the document participants is listed in the attorney list; otherwise the value is **false**.</span></span> <span data-ttu-id="21043-116">Il valore viene impostato su **false** anche se l'organizzazione non ha caricato un elenco di avvocati.</span><span class="sxs-lookup"><span data-stu-id="21043-116">The value is also set to **false** if your organization didn't upload an attorney list.</span></span>

- <span data-ttu-id="21043-117">**IsPrivilege:** Questa proprietà è impostata su **true** se il valore di **AttorneyClientPrivilegeScore** è superiore alla soglia o se il documento ha un partecipante avvocato;  in caso contrario, il valore è impostato su **false**.</span><span class="sxs-lookup"><span data-stu-id="21043-117">**IsPrivilege:** This property is set to **true** if the value for **AttorneyClientPrivilegeScore** is above the threshold *or* if the document has an attorney participant; otherwise the value is set to **false**.</span></span>

<span data-ttu-id="21043-118">Queste proprietà (e i valori corrispondenti) vengono aggiunte ai metadati dei file dei documenti in un set di revisioni, come illustrato nello screenshot seguente:</span><span class="sxs-lookup"><span data-stu-id="21043-118">These properties (and their corresponding values) are added to the file metadata of the documents in a review set, as shown in the following screenshot:</span></span>

![Proprietà dei privilegi attorney-client visualizzate nei metadati dei file](../media/AeDAttorneyClientPrivilegeMetadata.png)

<span data-ttu-id="21043-120">Queste tre proprietà sono disponibili anche per la ricerca all'interno di un set di recensioni.</span><span class="sxs-lookup"><span data-stu-id="21043-120">These three properties are also searchable within a review set.</span></span> <span data-ttu-id="21043-121">Per ulteriori informazioni, vedere [Query the data in a review set](review-set-search.md).</span><span class="sxs-lookup"><span data-stu-id="21043-121">For more information, see [Query the data in a review set](review-set-search.md).</span></span>

## <a name="set-up-the-attorney-client-privilege-detection-model"></a><span data-ttu-id="21043-122">Configurare il modello di rilevamento dei privilegi avvocato-client</span><span class="sxs-lookup"><span data-stu-id="21043-122">Set up the attorney-client privilege detection model</span></span>

<span data-ttu-id="21043-123">Per abilitare il modello di rilevamento dei privilegi avvocato-client, l'organizzazione deve attivarlo e quindi caricare un elenco di avvocati.</span><span class="sxs-lookup"><span data-stu-id="21043-123">To enable the attorney-client privilege detection model, your organization has to turn it on and then upload an attorney list.</span></span>

### <a name="step-1-turn-on-attorney-client-privilege-detection"></a><span data-ttu-id="21043-124">Passaggio 1: attivare il rilevamento dei privilegi avvocato-client</span><span class="sxs-lookup"><span data-stu-id="21043-124">Step 1: Turn on attorney-client privilege detection</span></span>

<span data-ttu-id="21043-125">Una persona che è un amministratore di eDiscovery nell'organizzazione (membro del sottogruppo Amministratore di eDiscovery nel gruppo di ruoli Manager eDiscovery) deve rendere il modello disponibile nei casi Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="21043-125">A person who is an eDiscovery Administrator in your organization (a member of the eDiscovery Administrator subgroup in the eDiscovery Manager role group) must make the model available in your Advanced eDiscovery cases.</span></span>

1. <span data-ttu-id="21043-126">Nel Centro sicurezza & conformità passare a **eDiscovery > Advanced eDiscovery**.</span><span class="sxs-lookup"><span data-stu-id="21043-126">In the Security & Compliance Center, go to **eDiscovery > Advanced eDiscovery**.</span></span>

2. <span data-ttu-id="21043-127">Nella home **page Advanced eDiscovery,** nel **riquadro** Impostazioni, fare clic **su Configura impostazioni di analisi globali.**</span><span class="sxs-lookup"><span data-stu-id="21043-127">On the **Advanced eDiscovery** home page, in the **Settings** tile, click **Configure global analytics settings**.</span></span>

   ![Selezionare "Configura funzionalità sperimentali"](../media/AeDExperimentalFeatures.png)

3. <span data-ttu-id="21043-129">Nella scheda **Impostazioni analisi** selezionare Gestisci **impostazione privilegio avvocato-client.**</span><span class="sxs-lookup"><span data-stu-id="21043-129">On the **Analytics settings** tab, select **Manage attorney-client privilege setting**.</span></span>

4. <span data-ttu-id="21043-130">Nella pagina a comparsa **Privilegio avvocato-cliente**, usare l'interruttore per attivare la funzionalità, quindi selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="21043-130">On the **Attorney-client privilege** flyout page, use the toggle to turn on the feature and then select **Save**.</span></span>

### <a name="step-2-upload-a-list-of-attorneys-optional"></a><span data-ttu-id="21043-131">Passaggio 2: Upload un elenco di avvocati (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="21043-131">Step 2: Upload a list of attorneys (optional)</span></span>

<span data-ttu-id="21043-132">Per sfruttare al meglio il modello di rilevamento dei privilegi avvocato-client e utilizzare i risultati del rilevamento Has **Attorney** o **Potentially Privileged** descritto in precedenza, è consigliabile caricare un elenco di indirizzi di posta elettronica per gli avvocati e il personale legale che lavorano per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="21043-132">To take full advantage of the attorney-client privilege detection model and use the results of the **Has Attorney** or **Potentially Privileged** detection that was previously described, we recommend that you upload a list of email addresses for the lawyers and legal personnel who work for your organization.</span></span> 

<span data-ttu-id="21043-133">Per caricare un elenco di avvocati per l'utilizzo da parte del modello di rilevamento dei privilegi avvocato-client:</span><span class="sxs-lookup"><span data-stu-id="21043-133">To upload an attorney list for use by the attorney-client privilege detection model:</span></span>

1. <span data-ttu-id="21043-p106">Creare un file CSV (senza una riga di intestazione) e aggiungere l'indirizzo di posta elettronica di ogni persona pertinente in una riga separata. Salvare il file nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="21043-p106">Create a .csv file (without a header row) and add the email address for each appropriate person on a separate line. Save this file to your local computer.</span></span>

2. <span data-ttu-id="21043-136">Nella **home page Advanced eDiscovery,** nel riquadro **Impostazioni,** selezionare **Configura** funzionalità sperimentali e quindi selezionare **Gestisci impostazione privilegio avvocato-client.**</span><span class="sxs-lookup"><span data-stu-id="21043-136">On the **Advanced eDiscovery** home page, in the **Settings** tile, select **Configure experimental features**, and then select **Manage attorney-client privilege setting**.</span></span>

   <span data-ttu-id="21043-137">Viene **visualizzata la pagina Privilegi avvocato-client** e l'interruttore rilevamento privilegi **avvocato-client** è attivato.</span><span class="sxs-lookup"><span data-stu-id="21043-137">The **Attorney-client privilege** page is displayed, and the **Attorney-client privilege detection** toggle is turned on.</span></span>

   ![Pagina a comparsa privilegi avvocato-client](../media/AeDUploadAttorneyList.png)

3. <span data-ttu-id="21043-139">Selezionare **Sfoglia** e quindi individuare e selezionare il file .csv creato nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="21043-139">Select **Browse** and then find and select the .csv file that you created in step 1.</span></span>

4. <span data-ttu-id="21043-140">Seleziona **Salva** per caricare l'elenco degli avvocati.</span><span class="sxs-lookup"><span data-stu-id="21043-140">Select **Save** to upload the attorney list.</span></span>

## <a name="use-the-attorney-client-privilege-detection-model"></a><span data-ttu-id="21043-141">Usare il modello di rilevamento dei privilegi avvocato-client</span><span class="sxs-lookup"><span data-stu-id="21043-141">Use the attorney-client privilege detection model</span></span>

<span data-ttu-id="21043-142">Seguire i passaggi descritti in questa sezione per usare il rilevamento dei privilegi avvocato-client per i documenti in un set di revisione.</span><span class="sxs-lookup"><span data-stu-id="21043-142">Follow the steps in this section to use attorney-client privilege detection for documents in a review set.</span></span>

### <a name="step-1-create-a-smart-tag-group-with-attorney-client-privilege-detection-model"></a><span data-ttu-id="21043-143">Passaggio 1: Creare un gruppo di smart tag con il modello di rilevamento dei privilegi avvocato-client</span><span class="sxs-lookup"><span data-stu-id="21043-143">Step 1: Create a smart tag group with attorney-client privilege detection model</span></span>

<span data-ttu-id="21043-144">Uno dei modi principali per visualizzare i risultati del rilevamento del privilegio avvocato-cliente nel processo di revisione consiste nell'utilizzare un gruppo di smart tag.</span><span class="sxs-lookup"><span data-stu-id="21043-144">One of the primary ways to see the results of attorney-client privilege detection in your review process is by using a smart tag group.</span></span> <span data-ttu-id="21043-145">Un gruppo di smart tag indica i risultati del rilevamento del privilegio avvocato-cliente e mostra i risultati in linea accanto ai tag nel gruppo di smart tag.</span><span class="sxs-lookup"><span data-stu-id="21043-145">A smart tag group indicates the results of the attorney-client privilege detection and shows the results in-line next to the tags in a smart tag group.</span></span> <span data-ttu-id="21043-146">Ciò consente di identificare rapidamente i documenti potenzialmente privilegiati durante la revisione dei documenti.</span><span class="sxs-lookup"><span data-stu-id="21043-146">This lets you quickly identify potentially privileged documents during document review.</span></span> <span data-ttu-id="21043-147">Inoltre, è anche possibile usare i tag nel gruppo di smart tag per contrassegnare i documenti come con privilegi o senza privilegi.</span><span class="sxs-lookup"><span data-stu-id="21043-147">Additionally, you can also use the tags in the smart tag group to tag documents as privileged or non-privileged.</span></span> <span data-ttu-id="21043-148">Per ulteriori informazioni sugli smart tag, vedere [Set up smart tags in Advanced eDiscovery](smart-tags.md).</span><span class="sxs-lookup"><span data-stu-id="21043-148">For more information about smart tags, see [Set up smart tags in Advanced eDiscovery](smart-tags.md).</span></span>

1. <span data-ttu-id="21043-149">Nel set di revisioni contenente i documenti analizzati nel passaggio 1, selezionare **Gestisci** set di revisioni e quindi **Selezionare Gestisci tag.**</span><span class="sxs-lookup"><span data-stu-id="21043-149">In the review set that contains the documents that you analyzed in Step 1, select **Manage review set** and then select **Manage tags**.</span></span>
 
2. <span data-ttu-id="21043-150">In **Tag** selezionare l'elenco a discesa accanto a **Aggiungi gruppo** e quindi selezionare Aggiungi gruppo di smart **tag.**</span><span class="sxs-lookup"><span data-stu-id="21043-150">Under **Tags**, select the pull-down next to **Add group** and then select **Add smart tag group**.</span></span>

   ![Selezionare "Aggiungi gruppo di smart tag"](../media/AeDCreateSmartTag.png)

3. <span data-ttu-id="21043-152">Nella pagina **Scegliere un modello per lo smart tag** scegliere **Seleziona** accanto a **Privilegio avvocato-client.**</span><span class="sxs-lookup"><span data-stu-id="21043-152">On the **Choose a model for your smart tag** page, choose **Select** next to **Attorney-client privilege**.</span></span>

   <span data-ttu-id="21043-153">Viene visualizzato un gruppo **di tag denominato Attorney-client privilege.**</span><span class="sxs-lookup"><span data-stu-id="21043-153">A tag group named **Attorney-client privilege** is displayed.</span></span> <span data-ttu-id="21043-154">Contiene due tag figlio denominati **Positive** e **Negative**, che corrispondono ai possibili risultati prodotti dal modello.</span><span class="sxs-lookup"><span data-stu-id="21043-154">It contains two child tags named **Positive** and **Negative**, which correspond to the possible results produced by the model.</span></span>

   ![Gruppo di smart tag privilegi avvocato-client](../media/AeDAttorneyClientSmartTagGroup.png)

3. <span data-ttu-id="21043-156">Rinominare il gruppo di tag e i tag in base alle esigenze della revisione.</span><span class="sxs-lookup"><span data-stu-id="21043-156">Rename the tag group and tags as appropriate for your review.</span></span> <span data-ttu-id="21043-157">Ad esempio, è possibile rinominare **Positivo** in **Privilegiato** e **Negativo** in **Non privilegiato**.</span><span class="sxs-lookup"><span data-stu-id="21043-157">For example, you can rename **Positive** to **Privileged** and **Negative** to **Not privileged**.</span></span>

### <a name="step-2-analyze-a-review-set"></a><span data-ttu-id="21043-158">Passaggio 2: analizzare un set di recensioni</span><span class="sxs-lookup"><span data-stu-id="21043-158">Step 2: Analyze a review set</span></span>

<span data-ttu-id="21043-159">Quando si analizzano i documenti in un set di revisione, verrà eseguito anche il modello di rilevamento dei privilegi avvocato-client e le proprietà corrispondenti (descritte in [Come funziona?](#how-does-it-work) verranno aggiunte a ogni documento nel set di revisioni.</span><span class="sxs-lookup"><span data-stu-id="21043-159">When you analyze the documents in a review set, the attorney-client privilege detection model will also run and the corresponding properties (described in [How does it work?](#how-does-it-work) will be added to every document in the review set.</span></span> <span data-ttu-id="21043-160">Per ulteriori informazioni sull'analisi dei dati nel set di revisioni, vedere [Analyze data in a review set in Advanced eDiscovery](analyzing-data-in-review-set.md).</span><span class="sxs-lookup"><span data-stu-id="21043-160">For more information about analyzing data in review set, see [Analyze data in a review set in Advanced eDiscovery](analyzing-data-in-review-set.md).</span></span>

### <a name="step-3-use-the-smart-tag-group-for-review-of-privileged-content"></a><span data-ttu-id="21043-161">Passaggio 3: Utilizzare il gruppo di smart tag per la revisione del contenuto con privilegi</span><span class="sxs-lookup"><span data-stu-id="21043-161">Step 3: Use the smart tag group for review of privileged content</span></span>

<span data-ttu-id="21043-162">Dopo aver analizzato il set di revisione e aver configurato gli smart tag, il passaggio successivo consiste nel rivedere i documenti.</span><span class="sxs-lookup"><span data-stu-id="21043-162">After analyzing the review set and setting up smart tags, the next step is to review the documents.</span></span> <span data-ttu-id="21043-163">Se il modello ha determinato che il documento è potenzialmente privilegiato, lo smart tag corrispondente nel pannello **Tagging** indicherà i risultati seguenti prodotti dal rilevamento dei privilegi avvocato-client:</span><span class="sxs-lookup"><span data-stu-id="21043-163">If the model has determined the document is potentially privileged, the corresponding smart tag in the **Tagging panel** will indicate the following results produced by the attorney-client privilege detection:</span></span>

- <span data-ttu-id="21043-164">Se il documento ha contenuto che può  essere di natura legale, l'etichetta Contenuto legale viene visualizzata accanto al corrispondente smart tag (che in questo caso è il tag **Positivo** predefinito).</span><span class="sxs-lookup"><span data-stu-id="21043-164">If the document has content that may be legal in nature, the label **Legal content** is displayed next to the corresponding smart tag (which in this case is the default **Positive** tag).</span></span>

- <span data-ttu-id="21043-165">Se il documento include un partecipante che si trova  nell'elenco degli avvocati dell'organizzazione, l'etichetta Avvocato viene visualizzata accanto allo smart tag corrispondente (che in questo caso è anche il tag **Positivo** predefinito).</span><span class="sxs-lookup"><span data-stu-id="21043-165">If the document has a participant who is found in your organization's attorney list, the label **Attorney** is displayed next to the corresponding smart tag (which in this case is also the default **Positive** tag).</span></span>

- <span data-ttu-id="21043-166">Se il documento contiene contenuto che può essere di natura legale e  che  un partecipante è presente nell'elenco degli avvocati, vengono visualizzati sia il contenuto legale che le etichette dell'avvocato. </span><span class="sxs-lookup"><span data-stu-id="21043-166">If the document has content that may be legal in nature *and* has a participant found in the attorney list, both the **Legal content**  and **Attorney** labels are displayed.</span></span> 

<span data-ttu-id="21043-167">Se il modello determina che un documento non contiene contenuto di natura legale o che non contiene un partecipante nell'elenco degli avvocati, nel riquadro di tagging non viene visualizzata alcuna etichetta.</span><span class="sxs-lookup"><span data-stu-id="21043-167">If the model determines that a document doesn't contain content that is legal in nature or doesn't contain a participant from the attorney list, then neither label is displayed in the tagging panel.</span></span>

<span data-ttu-id="21043-168">Ad esempio, le schermate seguenti mostrano due documenti.</span><span class="sxs-lookup"><span data-stu-id="21043-168">For example, the following screenshots show two documents.</span></span> <span data-ttu-id="21043-169">Il primo contiene contenuti di natura legale e con un partecipante presente nell'elenco degli avvocati.</span><span class="sxs-lookup"><span data-stu-id="21043-169">The first one contains content that is legal in nature and has a participant found in the list of attorneys.</span></span> <span data-ttu-id="21043-170">Il secondo non contiene nessuno dei due e pertanto non visualizza alcuna etichetta.</span><span class="sxs-lookup"><span data-stu-id="21043-170">The second contains neither and therefore doesn't display any labels.</span></span>

![Documento con etichette di contenuto legale e legale](../media/AeDTaggingPanelLegalContentAttorney.png)

![Documento senza etichette](../media/AeDTaggingPanelNegative.png)

<span data-ttu-id="21043-173">Dopo aver esaminato un documento per verificare se contiene contenuto con privilegi, è possibile contrassegnarlo con il tag appropriato.</span><span class="sxs-lookup"><span data-stu-id="21043-173">After you review a document to see if it contains privileged content, you can tag the document with the appropriate tag.</span></span>
