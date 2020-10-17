---
title: Classificazione dei dati per l'ambiente di testing di Microsoft 365 per l'organizzazione
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Utilizzare questa guida del laboratorio di testing per creare e utilizzare etichette di conservazione nei documenti dell'ambiente di testing di Microsoft 365 per l'organizzazione.
ms.openlocfilehash: 5cc77167db866d99f0beea5f554a777ecf355046
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487733"
---
# <a name="data-classification-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="75e5c-103">Classificazione dei dati per l'ambiente di testing di Microsoft 365 per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="75e5c-103">Data classification for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="75e5c-104">*Questa guida del laboratorio di testing può essere utilizzata per ambienti di testing Microsoft 365 per Enterprise e Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="75e5c-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="75e5c-105">In questo articolo viene descritto come configurare la classificazione dei dati utilizzando le etichette di conservazione nell'ambiente di testing di Microsoft 365 per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="75e5c-105">This article describes how to configure data classification using retention labels in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="75e5c-106">La classificazione dei dati nell'ambiente di testing comporta tre fasi:</span><span class="sxs-lookup"><span data-stu-id="75e5c-106">Classifying data in your test environment involves three phases:</span></span>
- [<span data-ttu-id="75e5c-107">Fase 1: creare l'ambiente di testing di Microsoft 365 per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="75e5c-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="75e5c-108">Fase 2: creare etichette di conservazione</span><span class="sxs-lookup"><span data-stu-id="75e5c-108">Phase 2: Create retention labels</span></span>](#phase-2-create-retention-labels)
- [<span data-ttu-id="75e5c-109">Fase 3: applicare le etichette di conservazione ai documenti</span><span class="sxs-lookup"><span data-stu-id="75e5c-109">Phase 3: Apply retention labels to documents</span></span>](#phase-3-apply-retention-labels-to-documents)

![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="75e5c-111">Per una mappa visiva su tutti gli articoli della guida del laboratorio di testing di Microsoft 365 for Enterprise, accedere a [microsoft 365 per la guida dello stack del laboratorio di testing dell'organizzazione](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="75e5c-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="75e5c-112">Fase 1: creare l'ambiente di testing di Microsoft 365 per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="75e5c-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="75e5c-113">Se si desidera solo configurare le etichette di conservazione in modo semplice con i requisiti minimi, seguire le istruzioni in [Lightweight base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="75e5c-113">If you just want to configure retention labels in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="75e5c-114">Se si desidera configurare le etichette di conservazione in un'azienda simulata, seguire le istruzioni riportate nell' [autenticazione pass-through](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="75e5c-114">If you want to configure retention labels in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="75e5c-115">La verifica delle etichette di conservazione non richiede l'ambiente di testing dell'organizzazione simulata, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per una foresta di servizi di dominio Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="75e5c-115">Testing retention labels doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="75e5c-116">È disponibile come opzione in modo che sia possibile testare la licenza automatizzata e l'appartenenza ai gruppi e sperimentarla in un ambiente che rappresenta un'organizzazione tipica.</span><span class="sxs-lookup"><span data-stu-id="75e5c-116">It's provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-create-retention-labels"></a><span data-ttu-id="75e5c-117">Fase 2: creare etichette di conservazione</span><span class="sxs-lookup"><span data-stu-id="75e5c-117">Phase 2: Create retention labels</span></span>

<span data-ttu-id="75e5c-118">In questa fase, creare le etichette di conservazione per i diversi livelli di conservazione per le cartelle di documenti di SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="75e5c-118">In this phase, create the retention labels for the different levels of retention for SharePoint Online documents folders:</span></span>

1. <span data-ttu-id="75e5c-119">Accedere al [Centro sicurezza Microsoft 365](https://security.microsoft.com/homepage) con l'account di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="75e5c-119">Sign in to the [Microsoft 365 security center](https://security.microsoft.com/homepage) with your global admin account.</span></span>
1. <span data-ttu-id="75e5c-120">Dalla scheda **sicurezza Home-Microsoft 365** del browser selezionare etichette di conservazione per la **classificazione**  >  **Retention labels**.</span><span class="sxs-lookup"><span data-stu-id="75e5c-120">From the **Home - Microsoft 365 security** tab of your browser, select **Classification** > **Retention labels**.</span></span>
1. <span data-ttu-id="75e5c-121">Selezionare **Crea un'etichetta**.</span><span class="sxs-lookup"><span data-stu-id="75e5c-121">Select **Create a label**.</span></span>
1. <span data-ttu-id="75e5c-122">Nel riquadro **Name Your label** , immettere **public interno** in **nome dell'etichetta**, quindi selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="75e5c-122">In the **Name your label** pane, enter **Internal Public** in **Name your label**, and then select **Next**.</span></span>
1. <span data-ttu-id="75e5c-123">Nel riquadro dei **descrittori del piano file** , selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="75e5c-123">In the **File plan descriptors** pane, select **Next**.</span></span>
1. <span data-ttu-id="75e5c-124">Nel riquadro **Impostazioni etichetta** , se necessario, impostare **conservazione** **su**attivato, quindi selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="75e5c-124">In the **Label settings** pane, if needed, set **Retention** to **On**, and then select **Next**.</span></span>
1. <span data-ttu-id="75e5c-125">Nel riquadro **Verifica le impostazioni** fare clic su **crea l'etichetta**.</span><span class="sxs-lookup"><span data-stu-id="75e5c-125">In the **Review your settings** pane, select **Create the label**.</span></span>
1. <span data-ttu-id="75e5c-126">Ripetere i passaggi da 3 a 7 per altre etichette con i nomi seguenti:</span><span class="sxs-lookup"><span data-stu-id="75e5c-126">Repeat steps 3-7 for additional labels with these names:</span></span>
  - <span data-ttu-id="75e5c-127">Private</span><span class="sxs-lookup"><span data-stu-id="75e5c-127">Private</span></span>
  - <span data-ttu-id="75e5c-128">Dati sensibili</span><span class="sxs-lookup"><span data-stu-id="75e5c-128">Sensitive</span></span>
  - <span data-ttu-id="75e5c-129">Highly Confidential (Riservatezza elevata)</span><span class="sxs-lookup"><span data-stu-id="75e5c-129">Highly Confidential</span></span>
1. <span data-ttu-id="75e5c-130">Nel riquadro **etichette di conservazione** , selezionare **pubblica etichette**.</span><span class="sxs-lookup"><span data-stu-id="75e5c-130">In the **Retention labels** pane, select **Publish labels**.</span></span>
1. <span data-ttu-id="75e5c-131">Nel riquadro **Scegli etichette** da pubblicare, seleziona **Scegli etichette da pubblicare**.</span><span class="sxs-lookup"><span data-stu-id="75e5c-131">In the **Choose labels to publish** pane, select **Choose labels to publish**.</span></span>
1. <span data-ttu-id="75e5c-132">Nel riquadro **Scegli etichette** , selezionare **Aggiungi** e selezionare le quattro etichette.</span><span class="sxs-lookup"><span data-stu-id="75e5c-132">In the **Choose labels** pane, select **Add** and select all four labels.</span></span>
1. <span data-ttu-id="75e5c-133">Selezionare **Aggiungi**, quindi fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="75e5c-133">Select **Add**, and then select **Done**.</span></span>
1. <span data-ttu-id="75e5c-134">Nel riquadro **Scegli etichette da pubblicare** selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="75e5c-134">On the **Choose labels to publish** pane, select **Next**.</span></span>
1. <span data-ttu-id="75e5c-135">Nel riquadro **Scegli percorsi** scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="75e5c-135">On the **Choose locations** pane, select **Next**.</span></span>
1. <span data-ttu-id="75e5c-136">Nel riquadro **denomina il criterio** , immettere l' **organizzazione di esempio** in **nome**e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="75e5c-136">On the **Name your policy** pane, enter **Example organization** in **Name**, and then select **Next**.</span></span>
1. <span data-ttu-id="75e5c-137">Nel riquadro **Verifica le impostazioni** fare clic su **pubblica etichette**.</span><span class="sxs-lookup"><span data-stu-id="75e5c-137">On the **Review your settings** pane, select **Publish labels**.</span></span>
 
<span data-ttu-id="75e5c-138">Per la pubblicazione delle etichette di conservazione, potrebbero essere necessari alcuni minuti.</span><span class="sxs-lookup"><span data-stu-id="75e5c-138">It might take a few minutes for the retention labels to be published.</span></span>

## <a name="phase-3-apply-retention-labels-to-documents"></a><span data-ttu-id="75e5c-139">Fase 3: applicare le etichette di conservazione ai documenti</span><span class="sxs-lookup"><span data-stu-id="75e5c-139">Phase 3: Apply retention labels to documents</span></span>

<span data-ttu-id="75e5c-140">In questa fase, viene individuato il comportamento predefinito dell'etichetta di conservazione per i file nella cartella documenti di un sito di SharePoint Online e viene modificata manualmente l'etichetta di conservazione di un documento.</span><span class="sxs-lookup"><span data-stu-id="75e5c-140">In this phase, you discover the default retention label behavior for files in the Documents folder of a SharePoint Online site and manually change the retention label of a document.</span></span>

<span data-ttu-id="75e5c-141">Per prima cosa, creare un sito del team di SharePoint Online a livello di riserva:</span><span class="sxs-lookup"><span data-stu-id="75e5c-141">First, create a sensitive-level SharePoint Online team site:</span></span>
  
1. <span data-ttu-id="75e5c-142">Se si utilizza un'istanza privata del browser, accedere all'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com) utilizzando l'account di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="75e5c-142">Using a private instance of your browser, sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using your global admin account.</span></span>
1. <span data-ttu-id="75e5c-143">Nell'elenco dei riquadri selezionare **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="75e5c-143">In the list of tiles, select **SharePoint**.</span></span>
1. <span data-ttu-id="75e5c-144">Nella nuova scheda **SharePoint** del browser, selezionare **Crea sito**.</span><span class="sxs-lookup"><span data-stu-id="75e5c-144">On the new **SharePoint** tab in your browser, select **Create site**.</span></span>
1. <span data-ttu-id="75e5c-145">Nella pagina **Crea sito** fare clic su **sito del team**.</span><span class="sxs-lookup"><span data-stu-id="75e5c-145">On the **Create a site** page, select **Team site**.</span></span>
1. <span data-ttu-id="75e5c-146">Nella casella **nome sito del team** , immettere **SensitiveFiles**.</span><span class="sxs-lookup"><span data-stu-id="75e5c-146">In the **Team site name** box, enter **SensitiveFiles**.</span></span>
1. <span data-ttu-id="75e5c-147">Nella casella **Descrizione sito del team** , immettere il **sito di SharePoint per i file riservati**.</span><span class="sxs-lookup"><span data-stu-id="75e5c-147">In the **Team site description** box, enter **SharePoint site for sensitive files**.</span></span>
1. <span data-ttu-id="75e5c-148">In **impostazioni di privacy**, selezionare **membri solo privati possono accedere a questo sito**, quindi selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="75e5c-148">In **Privacy settings**, select **Private - only members can access this site**, and then select **Next**.</span></span>
1. <span data-ttu-id="75e5c-149">Nel riquadro **chi si desidera aggiungere?** , selezionare **fine**.</span><span class="sxs-lookup"><span data-stu-id="75e5c-149">In the **Who do you want to add?** pane, select **Finish**.</span></span>
    
<span data-ttu-id="75e5c-150">Successivamente, configurare la cartella dei documenti del sito del team di SensitiveFiles per l'etichetta di conservazione riservata.</span><span class="sxs-lookup"><span data-stu-id="75e5c-150">Next, configure the Documents folder of the SensitiveFiles team site for the Sensitive retention label.</span></span>
  
1. <span data-ttu-id="75e5c-151">Nella scheda **SensitiveFiles** del browser selezionare **documenti**.</span><span class="sxs-lookup"><span data-stu-id="75e5c-151">In the **SensitiveFiles** tab of your browser, select **Documents**.</span></span>
1. <span data-ttu-id="75e5c-152">Selezionare l'icona **Impostazioni** , quindi selezionare **Impostazioni raccolta**.</span><span class="sxs-lookup"><span data-stu-id="75e5c-152">Select the **Settings** icon, and then select **Library settings**.</span></span>
1. <span data-ttu-id="75e5c-153">In **autorizzazioni e gestione**selezionare **Applica etichetta agli elementi contenuti nell'elenco o nella raccolta**.</span><span class="sxs-lookup"><span data-stu-id="75e5c-153">Under **Permissions and Management**, select **Apply label to items in this list or library**.</span></span> <span data-ttu-id="75e5c-154">Se questa opzione non viene visualizzata, le etichette di conservazione non vengono ancora pubblicate.</span><span class="sxs-lookup"><span data-stu-id="75e5c-154">If this option doesn't appear, your retention labels aren't yet published.</span></span> <span data-ttu-id="75e5c-155">Provare questo passaggio in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="75e5c-155">Try this step at a later time.</span></span>
1. <span data-ttu-id="75e5c-156">In **impostazioni-Applica etichetta**, selezionare **sensibile** nell'elenco a discesa e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="75e5c-156">In **Settings-Apply Label**, select **Sensitive** in the drop-down box, and then select **Save**.</span></span>

<span data-ttu-id="75e5c-157">Successivamente, creare un nuovo documento nel sito di SensitiveFiles e modificarne l'etichetta di conservazione.</span><span class="sxs-lookup"><span data-stu-id="75e5c-157">Next, create a new document in the SensitiveFiles site and change its retention label.</span></span>
    
1. <span data-ttu-id="75e5c-158">Nella cartella documenti selezionare **nuovo**  >  **documento di Word**.</span><span class="sxs-lookup"><span data-stu-id="75e5c-158">In the documents folder, select **New** > **Word document**.</span></span>
1. <span data-ttu-id="75e5c-159">Immettere del testo nel documento vuoto.</span><span class="sxs-lookup"><span data-stu-id="75e5c-159">Enter some text in the blank document.</span></span> <span data-ttu-id="75e5c-160">Attendere che il testo venga salvato.</span><span class="sxs-lookup"><span data-stu-id="75e5c-160">Wait for the text to be saved.</span></span>
1. <span data-ttu-id="75e5c-161">Sulla barra dei menu, selezionare **documenti condivisi**.</span><span class="sxs-lookup"><span data-stu-id="75e5c-161">On the menu bar, select **Shared Documents**.</span></span>
1. <span data-ttu-id="75e5c-162">Accanto al nome del file **Document.docx** , selezionare i puntini di sospensione verticali e quindi fare clic su **Dettagli**.</span><span class="sxs-lookup"><span data-stu-id="75e5c-162">Next to the **Document.docx** file name, select the vertical ellipsis, and then select **Details**.</span></span>
1. <span data-ttu-id="75e5c-163">Nel riquadro a destra, nella sezione **Proprietà** , in **Apply Retention label**, tenere presente che il documento ha l'etichetta di conservazione **riservata** applicata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="75e5c-163">In the right pane, in the **Properties** section, under **Apply retention label**, note that the document has had the **Sensitive** retention label automatically applied.</span></span>
1. <span data-ttu-id="75e5c-164">Fare clic su **modifica tutto**.</span><span class="sxs-lookup"><span data-stu-id="75e5c-164">Click **Edit all**.</span></span>
1. <span data-ttu-id="75e5c-165">Nel riquadro **Document.docx** , in **Applica etichetta di conservazione**, selezionare l'etichetta **estremamente riservata** e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="75e5c-165">In the **Document.docx** pane, under **Apply retention label**, select the **Highly Confidential** label, and then select **Save**.</span></span>

## <a name="next-step"></a><span data-ttu-id="75e5c-166">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="75e5c-166">Next step</span></span>

<span data-ttu-id="75e5c-167">Esplorare le funzionalità e le funzionalità di [protezione delle informazioni](m365-enterprise-test-lab-guides.md#information-protection) aggiuntive nell'ambiente di testing.</span><span class="sxs-lookup"><span data-stu-id="75e5c-167">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="75e5c-168">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="75e5c-168">See also</span></span>

[<span data-ttu-id="75e5c-169">Guide ai lab di test di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="75e5c-169">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="75e5c-170">Panoramica di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="75e5c-170">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="75e5c-171">Microsoft 365 per la documentazione relativa all'organizzazione</span><span class="sxs-lookup"><span data-stu-id="75e5c-171">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
