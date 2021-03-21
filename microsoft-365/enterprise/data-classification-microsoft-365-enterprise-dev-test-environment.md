---
title: Classificazione dei dati per l'ambiente di testing di Microsoft 365 per le aziende
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
description: Usare questa guida al laboratorio di testing per creare e usare etichette di conservazione nei documenti nell'ambiente di testing di Microsoft 365 per le aziende.
ms.openlocfilehash: 613aa3713b4d72eed1bc0b2d88f70a817d0e7cff
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919189"
---
# <a name="data-classification-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="9ae06-103">Classificazione dei dati per l'ambiente di testing di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="9ae06-103">Data classification for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="9ae06-104">*Questa guida al laboratorio di testing può essere usata sia per gli ambienti di testing di Microsoft 365 per le aziende che per gli ambienti di testing di Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="9ae06-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="9ae06-105">In questo articolo viene descritto come configurare la classificazione dei dati utilizzando le etichette di conservazione nell'ambiente di testing di Microsoft 365 per le aziende.</span><span class="sxs-lookup"><span data-stu-id="9ae06-105">This article describes how to configure data classification using retention labels in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="9ae06-106">La classificazione dei dati nell'ambiente di testing prevede tre fasi:</span><span class="sxs-lookup"><span data-stu-id="9ae06-106">Classifying data in your test environment involves three phases:</span></span>
- [<span data-ttu-id="9ae06-107">Fase 1: creare l'ambiente di testing di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="9ae06-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="9ae06-108">Fase 2: creare etichette di conservazione</span><span class="sxs-lookup"><span data-stu-id="9ae06-108">Phase 2: Create retention labels</span></span>](#phase-2-create-retention-labels)
- [<span data-ttu-id="9ae06-109">Fase 3: applicare etichette di conservazione ai documenti</span><span class="sxs-lookup"><span data-stu-id="9ae06-109">Phase 3: Apply retention labels to documents</span></span>](#phase-3-apply-retention-labels-to-documents)

![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="9ae06-111">Per una mappa visiva a tutti gli articoli nello stack guida del laboratorio di testing di Microsoft 365 per le aziende, passare a [Microsoft 365 per enterprise Test Lab Guide Stack.](../downloads/Microsoft365EnterpriseTLGStack.pdf)</span><span class="sxs-lookup"><span data-stu-id="9ae06-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="9ae06-112">Fase 1: creare l'ambiente di testing di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="9ae06-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="9ae06-113">Se si desidera solo configurare le etichette di conservazione in modo leggero con i requisiti minimi, seguire le istruzioni in [Configurazione di base lightweight](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="9ae06-113">If you just want to configure retention labels in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="9ae06-114">Se si desidera configurare le etichette di conservazione in un'organizzazione simulata, seguire le istruzioni in [Autenticazione pass-through.](pass-through-auth-m365-ent-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="9ae06-114">If you want to configure retention labels in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="9ae06-115">Il test delle etichette di conservazione non richiede l'ambiente di testing aziendale simulato, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per una foresta di Servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="9ae06-115">Testing retention labels doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="9ae06-116">Viene fornito qui come opzione in modo da poter testare le licenze automatizzate e l'appartenenza ai gruppi e sperimentarla in un ambiente che rappresenta un'organizzazione tipica.</span><span class="sxs-lookup"><span data-stu-id="9ae06-116">It's provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-create-retention-labels"></a><span data-ttu-id="9ae06-117">Fase 2: creare etichette di conservazione</span><span class="sxs-lookup"><span data-stu-id="9ae06-117">Phase 2: Create retention labels</span></span>

<span data-ttu-id="9ae06-118">In questa fase, creare le etichette di conservazione per i diversi livelli di conservazione per le cartelle di documenti di SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="9ae06-118">In this phase, create the retention labels for the different levels of retention for SharePoint Online documents folders:</span></span>

1. <span data-ttu-id="9ae06-119">Accedere al Centro sicurezza [Microsoft 365](https://security.microsoft.com/homepage) con l'account di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="9ae06-119">Sign in to the [Microsoft 365 security center](https://security.microsoft.com/homepage) with your global admin account.</span></span>
1. <span data-ttu-id="9ae06-120">Nella scheda **Home - Sicurezza di Microsoft 365** del browser selezionare Etichette **di**  >  **conservazione classificazione.**</span><span class="sxs-lookup"><span data-stu-id="9ae06-120">From the **Home - Microsoft 365 security** tab of your browser, select **Classification** > **Retention labels**.</span></span>
1. <span data-ttu-id="9ae06-121">Selezionare **Crea un'etichetta**.</span><span class="sxs-lookup"><span data-stu-id="9ae06-121">Select **Create a label**.</span></span>
1. <span data-ttu-id="9ae06-122">Nel riquadro **Assegnare un nome** all'etichetta immettere **Internal Public** in Name **your label** e quindi selezionare **Next.**</span><span class="sxs-lookup"><span data-stu-id="9ae06-122">In the **Name your label** pane, enter **Internal Public** in **Name your label**, and then select **Next**.</span></span>
1. <span data-ttu-id="9ae06-123">Nel riquadro **Descrittori piano file** selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="9ae06-123">In the **File plan descriptors** pane, select **Next**.</span></span>
1. <span data-ttu-id="9ae06-124">Nel riquadro **Impostazioni etichetta,** se necessario, impostare **Conservazione** su **Su** e quindi selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="9ae06-124">In the **Label settings** pane, if needed, set **Retention** to **On**, and then select **Next**.</span></span>
1. <span data-ttu-id="9ae06-125">Nel riquadro **Rivedi le impostazioni** seleziona **Crea l'etichetta.**</span><span class="sxs-lookup"><span data-stu-id="9ae06-125">In the **Review your settings** pane, select **Create the label**.</span></span>
1. <span data-ttu-id="9ae06-126">Ripetere i passaggi da 3 a 7 per altre etichette con i nomi seguenti:</span><span class="sxs-lookup"><span data-stu-id="9ae06-126">Repeat steps 3-7 for additional labels with these names:</span></span>
  - <span data-ttu-id="9ae06-127">Private</span><span class="sxs-lookup"><span data-stu-id="9ae06-127">Private</span></span>
  - <span data-ttu-id="9ae06-128">Dati sensibili</span><span class="sxs-lookup"><span data-stu-id="9ae06-128">Sensitive</span></span>
  - <span data-ttu-id="9ae06-129">Highly Confidential (Riservatezza elevata)</span><span class="sxs-lookup"><span data-stu-id="9ae06-129">Highly Confidential</span></span>
1. <span data-ttu-id="9ae06-130">Nel riquadro **Etichette di conservazione** selezionare Pubblica **etichette.**</span><span class="sxs-lookup"><span data-stu-id="9ae06-130">In the **Retention labels** pane, select **Publish labels**.</span></span>
1. <span data-ttu-id="9ae06-131">Nel riquadro **Scegliere le etichette da pubblicare** selezionare Scegliere le etichette da **pubblicare.**</span><span class="sxs-lookup"><span data-stu-id="9ae06-131">In the **Choose labels to publish** pane, select **Choose labels to publish**.</span></span>
1. <span data-ttu-id="9ae06-132">Nel riquadro **Scegli etichette** selezionare **Aggiungi e** selezionare tutte e quattro le etichette.</span><span class="sxs-lookup"><span data-stu-id="9ae06-132">In the **Choose labels** pane, select **Add** and select all four labels.</span></span>
1. <span data-ttu-id="9ae06-133">Selezionare **Aggiungi** e quindi Fare **clic su Fine.**</span><span class="sxs-lookup"><span data-stu-id="9ae06-133">Select **Add**, and then select **Done**.</span></span>
1. <span data-ttu-id="9ae06-134">Nel riquadro **Scegliere le etichette da pubblicare** selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="9ae06-134">On the **Choose labels to publish** pane, select **Next**.</span></span>
1. <span data-ttu-id="9ae06-135">Nel riquadro **Scegli posizioni** selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="9ae06-135">On the **Choose locations** pane, select **Next**.</span></span>
1. <span data-ttu-id="9ae06-136">Nel riquadro **Assegnare un nome al** criterio immettere **Organizzazione di esempio** in **Nome** e quindi selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="9ae06-136">On the **Name your policy** pane, enter **Example organization** in **Name**, and then select **Next**.</span></span>
1. <span data-ttu-id="9ae06-137">Nel riquadro **Rivedere le impostazioni** selezionare Pubblica **etichette.**</span><span class="sxs-lookup"><span data-stu-id="9ae06-137">On the **Review your settings** pane, select **Publish labels**.</span></span>
 
<span data-ttu-id="9ae06-138">La pubblicazione delle etichette di conservazione potrebbe richiedere alcuni minuti.</span><span class="sxs-lookup"><span data-stu-id="9ae06-138">It might take a few minutes for the retention labels to be published.</span></span>

## <a name="phase-3-apply-retention-labels-to-documents"></a><span data-ttu-id="9ae06-139">Fase 3: applicare etichette di conservazione ai documenti</span><span class="sxs-lookup"><span data-stu-id="9ae06-139">Phase 3: Apply retention labels to documents</span></span>

<span data-ttu-id="9ae06-140">In questa fase si individua il comportamento predefinito delle etichette di conservazione per i file nella cartella Documenti di un sito di SharePoint Online e si modifica manualmente l'etichetta di conservazione di un documento.</span><span class="sxs-lookup"><span data-stu-id="9ae06-140">In this phase, you discover the default retention label behavior for files in the Documents folder of a SharePoint Online site and manually change the retention label of a document.</span></span>

<span data-ttu-id="9ae06-141">Creare innanzitutto un sito del team di SharePoint Online a livello sensibile:</span><span class="sxs-lookup"><span data-stu-id="9ae06-141">First, create a sensitive-level SharePoint Online team site:</span></span>
  
1. <span data-ttu-id="9ae06-142">Usando un'istanza privata del browser, accedere all'interfaccia di amministrazione di [Microsoft 365](https://admin.microsoft.com) usando l'account di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="9ae06-142">Using a private instance of your browser, sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using your global admin account.</span></span>
1. <span data-ttu-id="9ae06-143">Nell'elenco dei riquadri selezionare **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="9ae06-143">In the list of tiles, select **SharePoint**.</span></span>
1. <span data-ttu-id="9ae06-144">Nella nuova **scheda Di SharePoint** nel browser selezionare **Crea sito.**</span><span class="sxs-lookup"><span data-stu-id="9ae06-144">On the new **SharePoint** tab in your browser, select **Create site**.</span></span>
1. <span data-ttu-id="9ae06-145">Nella pagina **Crea sito** selezionare Sito **del team**.</span><span class="sxs-lookup"><span data-stu-id="9ae06-145">On the **Create a site** page, select **Team site**.</span></span>
1. <span data-ttu-id="9ae06-146">Nella casella **Nome sito del** team immettere **SensitiveFiles**.</span><span class="sxs-lookup"><span data-stu-id="9ae06-146">In the **Team site name** box, enter **SensitiveFiles**.</span></span>
1. <span data-ttu-id="9ae06-147">Nella casella **Descrizione sito del** team immettere Sito **di SharePoint per i file riservati.**</span><span class="sxs-lookup"><span data-stu-id="9ae06-147">In the **Team site description** box, enter **SharePoint site for sensitive files**.</span></span>
1. <span data-ttu-id="9ae06-148">In **Impostazioni privacy** selezionare Privato : solo i membri possono accedere al **sito** e quindi selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="9ae06-148">In **Privacy settings**, select **Private - only members can access this site**, and then select **Next**.</span></span>
1. <span data-ttu-id="9ae06-149">Nel riquadro **Chi si desidera aggiungere?** selezionare **Fine.**</span><span class="sxs-lookup"><span data-stu-id="9ae06-149">In the **Who do you want to add?** pane, select **Finish**.</span></span>
    
<span data-ttu-id="9ae06-150">Configurare quindi la cartella Documenti del sito del team SensitiveFiles per l'etichetta di conservazione Sensitive.</span><span class="sxs-lookup"><span data-stu-id="9ae06-150">Next, configure the Documents folder of the SensitiveFiles team site for the Sensitive retention label.</span></span>
  
1. <span data-ttu-id="9ae06-151">Nella scheda **SensitiveFiles** del browser selezionare **Documenti**.</span><span class="sxs-lookup"><span data-stu-id="9ae06-151">In the **SensitiveFiles** tab of your browser, select **Documents**.</span></span>
1. <span data-ttu-id="9ae06-152">Seleziona **l'icona** Impostazioni e quindi seleziona **Impostazioni raccolta.**</span><span class="sxs-lookup"><span data-stu-id="9ae06-152">Select the **Settings** icon, and then select **Library settings**.</span></span>
1. <span data-ttu-id="9ae06-153">In **Autorizzazioni e gestione** selezionare Applica etichetta agli elementi **dell'elenco o della raccolta.**</span><span class="sxs-lookup"><span data-stu-id="9ae06-153">Under **Permissions and Management**, select **Apply label to items in this list or library**.</span></span> <span data-ttu-id="9ae06-154">Se questa opzione non viene visualizzata, le etichette di conservazione non sono ancora state pubblicate.</span><span class="sxs-lookup"><span data-stu-id="9ae06-154">If this option doesn't appear, your retention labels aren't yet published.</span></span> <span data-ttu-id="9ae06-155">Provare questo passaggio in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="9ae06-155">Try this step at a later time.</span></span>
1. <span data-ttu-id="9ae06-156">In **Impostazioni-Applica etichetta** selezionare **Sensibile** nella casella di riepilogo a discesa e quindi selezionare **Salva.**</span><span class="sxs-lookup"><span data-stu-id="9ae06-156">In **Settings-Apply Label**, select **Sensitive** in the drop-down box, and then select **Save**.</span></span>

<span data-ttu-id="9ae06-157">Successivamente, creare un nuovo documento nel sito SensitiveFiles e modificarne l'etichetta di conservazione.</span><span class="sxs-lookup"><span data-stu-id="9ae06-157">Next, create a new document in the SensitiveFiles site and change its retention label.</span></span>
    
1. <span data-ttu-id="9ae06-158">Nella cartella documenti selezionare **Nuovo documento**  >  **di Word.**</span><span class="sxs-lookup"><span data-stu-id="9ae06-158">In the documents folder, select **New** > **Word document**.</span></span>
1. <span data-ttu-id="9ae06-159">Immettere del testo nel documento vuoto.</span><span class="sxs-lookup"><span data-stu-id="9ae06-159">Enter some text in the blank document.</span></span> <span data-ttu-id="9ae06-160">Attendere il salvataggio del testo.</span><span class="sxs-lookup"><span data-stu-id="9ae06-160">Wait for the text to be saved.</span></span>
1. <span data-ttu-id="9ae06-161">Sulla barra dei menu selezionare **Documenti condivisi**.</span><span class="sxs-lookup"><span data-stu-id="9ae06-161">On the menu bar, select **Shared Documents**.</span></span>
1. <span data-ttu-id="9ae06-162">Accanto al nome **Document.docx** file, selezionare i puntini di sospensione verticali e quindi selezionare **Dettagli**.</span><span class="sxs-lookup"><span data-stu-id="9ae06-162">Next to the **Document.docx** file name, select the vertical ellipsis, and then select **Details**.</span></span>
1. <span data-ttu-id="9ae06-163">Nella sezione Proprietà del  riquadro destro, in Applica etichetta di **conservazione,** si noti che al documento è stata applicata automaticamente l'etichetta di conservazione Sensibile. </span><span class="sxs-lookup"><span data-stu-id="9ae06-163">In the right pane, in the **Properties** section, under **Apply retention label**, note that the document has had the **Sensitive** retention label automatically applied.</span></span>
1. <span data-ttu-id="9ae06-164">Fare **clic su Modifica tutto.**</span><span class="sxs-lookup"><span data-stu-id="9ae06-164">Click **Edit all**.</span></span>
1. <span data-ttu-id="9ae06-165">Nel riquadro **Document.docx,** in Applica etichetta **di conservazione,** selezionare l'etichetta **Estremamente riservato** e quindi selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="9ae06-165">In the **Document.docx** pane, under **Apply retention label**, select the **Highly Confidential** label, and then select **Save**.</span></span>

## <a name="next-step"></a><span data-ttu-id="9ae06-166">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="9ae06-166">Next step</span></span>

<span data-ttu-id="9ae06-167">Esplorare ulteriori [funzionalità e funzionalità di](m365-enterprise-test-lab-guides.md#information-protection) protezione delle informazioni nell'ambiente di testing.</span><span class="sxs-lookup"><span data-stu-id="9ae06-167">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="9ae06-168">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9ae06-168">See also</span></span>

[<span data-ttu-id="9ae06-169">Guide ai lab di test di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="9ae06-169">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="9ae06-170">Panoramica di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="9ae06-170">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="9ae06-171">Documentazione di Microsoft 365 for enterprise</span><span class="sxs-lookup"><span data-stu-id="9ae06-171">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)