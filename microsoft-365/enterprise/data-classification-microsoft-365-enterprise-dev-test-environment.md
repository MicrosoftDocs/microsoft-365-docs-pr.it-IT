---
title: Classificazione dei dati per l'ambiente di testing Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Utilizzare questa guida del laboratorio di testing per creare e utilizzare le etichette di conservazione di Office 365 nei documenti nell'ambiente di testing di Microsoft 365 Enterprise.
ms.openlocfilehash: e0186bcfc786356b34aff45b1b1e67f54dd40001
ms.sourcegitcommit: 9ee873c6a2f738a0c99921e036894b646742e706
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/15/2019
ms.locfileid: "38672662"
---
# <a name="data-classification-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="7e39f-103">Classificazione dei dati per l'ambiente di testing Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="7e39f-103">Data classification for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="7e39f-104">*Questa guida del laboratorio di testing può essere utilizzata per ambienti di testing Microsoft 365 Enterprise e Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="7e39f-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="7e39f-105">Con le istruzioni riportate in questo articolo, è possibile configurare la classificazione dei dati utilizzando le etichette di conservazione di Office 365 nell'ambiente di testing di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="7e39f-105">With the instructions in this article, you configure data classification using Office 365 retention labels in your Microsoft 365 Enterprise test environment.</span></span>

![Guide del laboratorio di testing per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="7e39f-107">Fare clic [qui](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) per consultare una mappa di tutti gli articoli relativi alla guida al lab test di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="7e39f-107">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="7e39f-108">Fase 1: Creare l'ambiente di testing di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="7e39f-108">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="7e39f-109">Se si desidera solo configurare le etichette di conservazione di Office 365 in modo semplice con i requisiti minimi, seguire le istruzioni contenute in [Lightweight base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="7e39f-109">If you just want to configure Office 365 retention labels in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="7e39f-110">Se si desidera configurare le etichette di conservazione di Office 365 in un'azienda simulata, seguire le istruzioni riportate nell' [autenticazione pass-through](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="7e39f-110">If you want to configure Office 365 retention labels in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="7e39f-111">Testing Office 365 le etichette di conservazione non richiedono l'ambiente di testing dell'organizzazione simulata, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per una foresta di servizi di dominio Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="7e39f-111">Testing Office 365 retention labels does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="7e39f-112">Viene fornito come opzione in modo che sia possibile testare la licenza automatizzata e l'appartenenza ai gruppi e sperimentarla in un ambiente che rappresenta un'organizzazione tipica.</span><span class="sxs-lookup"><span data-stu-id="7e39f-112">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-create-office-365-retention-labels"></a><span data-ttu-id="7e39f-113">Fase 2: creare etichette di conservazione di Office 365</span><span class="sxs-lookup"><span data-stu-id="7e39f-113">Phase 2: Create Office 365 retention labels</span></span>

<span data-ttu-id="7e39f-114">In questa fase, vengono create le etichette di conservazione per i diversi livelli di conservazione per le cartelle di documenti di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="7e39f-114">In this phase, you create the retention labels for the different levels of retention for SharePoint Online documents folders.</span></span>

1. <span data-ttu-id="7e39f-115">Accedere al [portale Conformità Microsoft 365](https://compliance.microsoft.com) con l'account di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="7e39f-115">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com) with your global admin account.</span></span>
    
2. <span data-ttu-id="7e39f-116">Dalla scheda **Home: Conformità Microsoft 365** del browser fare clic su **Classificazioni > Etichette**.</span><span class="sxs-lookup"><span data-stu-id="7e39f-116">From the **Home - Microsoft 365 compliance** tab of your browser, click **Classifications > Labels**.</span></span>
    
3. <span data-ttu-id="7e39f-117">Fare clic su **Etichette di conservazione > Crea un'etichetta**.</span><span class="sxs-lookup"><span data-stu-id="7e39f-117">Click **Retention labels > Create a label**.</span></span>
    
4. <span data-ttu-id="7e39f-118">Nel riquadro **Assegnare un nome all'etichetta** digitare \*\*Internal Public\*\*\*\*\*\* e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="7e39f-118">On the **Name your label** pane, type **Internal Public** in **Name your label**, and then click **Next**.</span></span>

5. <span data-ttu-id="7e39f-119">Nel riquadro **Descrittori del piano di archiviazione** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="7e39f-119">On the **File plan descriptors** pane, click **Next**.</span></span>
    
6. <span data-ttu-id="7e39f-120">Nel riquadro **Impostazioni etichetta** impostare **Conservazione** su **Sì**, se necessario, e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="7e39f-120">On the **Label settings** pane, if needed, set **Retention** to **On**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="7e39f-121">Nel riquadro **Rivedere le impostazioni** fare clic su **Crea etichetta**.</span><span class="sxs-lookup"><span data-stu-id="7e39f-121">On the **Review your settings** pane, click **Create the label**.</span></span>
    
8. <span data-ttu-id="7e39f-122">Ripetere i passaggi da 3 a 7 per altre etichette con i nomi seguenti:</span><span class="sxs-lookup"><span data-stu-id="7e39f-122">Repeat steps 3-7 for additional labels with these names:</span></span>
    
  - <span data-ttu-id="7e39f-123">Private</span><span class="sxs-lookup"><span data-stu-id="7e39f-123">Private</span></span>
    
  - <span data-ttu-id="7e39f-124">Dati sensibili</span><span class="sxs-lookup"><span data-stu-id="7e39f-124">Sensitive</span></span>
    
  - <span data-ttu-id="7e39f-125">Highly Confidential (Riservatezza elevata)</span><span class="sxs-lookup"><span data-stu-id="7e39f-125">Highly Confidential</span></span>
  
9. <span data-ttu-id="7e39f-126">Dal riquadro **Home > Etichette** fare clic su **Publish labels** (Pubblica etichette).</span><span class="sxs-lookup"><span data-stu-id="7e39f-126">From the **Home > Labels** pane, click **Publish labels**.</span></span>
    
10. <span data-ttu-id="7e39f-127">Nel riquadro **Choose labels to publish** (Scegli etichette da pubblicare) fare clic su **Choose labels to publish** (Scegli etichette da pubblicare).</span><span class="sxs-lookup"><span data-stu-id="7e39f-127">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
11. <span data-ttu-id="7e39f-128">Nel riquadro **Choose labels** (Scegli etichette) fare clic su **Aggiungi** e selezionare le quattro etichette.</span><span class="sxs-lookup"><span data-stu-id="7e39f-128">On the **Choose labels** pane, click **Add** and select all four labels.</span></span>
    
12. <span data-ttu-id="7e39f-129">Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="7e39f-129">Click **Done**.</span></span>
    
13. <span data-ttu-id="7e39f-130">Nel riquadro **Choose labels to publish** (Scegli etichette da pubblicare) fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="7e39f-130">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
14. <span data-ttu-id="7e39f-131">Nel riquadro **Choose locations** (Scegli posizioni) fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="7e39f-131">On the **Choose locations** pane, click **Next**.</span></span>
    
15. <span data-ttu-id="7e39f-132">Nel riquadro **Denomina il criterio** digitare **Example organization** in **Nome**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="7e39f-132">On the **Name your policy** pane, type **Example organization** in **Name**, and then click **Next**.</span></span>
    
16. <span data-ttu-id="7e39f-133">Nel riquadro **Verifica le impostazioni** fare clic su **Publish labels** (Pubblica etichette), quindi fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="7e39f-133">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>
 
<span data-ttu-id="7e39f-134">Tenere presente che potrebbero essere necessari alcuni minuti per la pubblicazione delle etichette di conservazione.</span><span class="sxs-lookup"><span data-stu-id="7e39f-134">Note that it might take a few minutes for the retention labels to be published.</span></span>

## <a name="phase-3-apply-office-365-retention-labels-to-documents"></a><span data-ttu-id="7e39f-135">Fase 3: applicare le etichette di conservazione di Office 365 ai documenti</span><span class="sxs-lookup"><span data-stu-id="7e39f-135">Phase 3: Apply Office 365 retention labels to documents</span></span>

<span data-ttu-id="7e39f-136">In questa fase, viene individuato il comportamento predefinito dell'etichetta di conservazione per i file nella cartella documenti di un sito di SharePoint Online e viene modificata manualmente l'etichetta di conservazione di un documento.</span><span class="sxs-lookup"><span data-stu-id="7e39f-136">In this phase, you discover the default retention label behavior for files in the Documents folder of a SharePoint Online site and manually change the retention label of a document.</span></span>

<span data-ttu-id="7e39f-137">Per prima cosa, creare un sito del team di SharePoint Online a livello di riserva:</span><span class="sxs-lookup"><span data-stu-id="7e39f-137">First, create a sensitive-level SharePoint Online team site:</span></span>
  
1. <span data-ttu-id="7e39f-138">Usando un browser sul computer locale, accedere al [portale di Office 365](https://portal.office.com) con il proprio account amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="7e39f-138">Using a browser on your local computer, sign in to the [Office 365 portal](https://portal.office.com) using your global administrator account.</span></span>
    
2. <span data-ttu-id="7e39f-139">Nell'elenco dei riquadri fare clic su **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="7e39f-139">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="7e39f-140">Nella nuova scheda **SharePoint** del browser fare clic su **Crea sito**.</span><span class="sxs-lookup"><span data-stu-id="7e39f-140">On the new **SharePoint** tab in your browser, click **Create site**.</span></span>
    
4. <span data-ttu-id="7e39f-141">Nella pagina **Crea sito** fare clic su **Sito del team**.</span><span class="sxs-lookup"><span data-stu-id="7e39f-141">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="7e39f-142">In **nome sito del team**digitare **SensitiveFiles**.</span><span class="sxs-lookup"><span data-stu-id="7e39f-142">In **Team site name**, type **SensitiveFiles**.</span></span>
    
6. <span data-ttu-id="7e39f-143">In **Descrizione sito del team**, digitare **sito di SharePoint per i file riservati**.</span><span class="sxs-lookup"><span data-stu-id="7e39f-143">In **Team site description**, type **SharePoint site for sensitive files**.</span></span>
    
7.  <span data-ttu-id="7e39f-144">In **Impostazioni privacy** selezionare **Private - only members can access this site** (Privato: solo i membri possono accedere a questo sito) e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="7e39f-144">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="7e39f-145">Nel riquadro **Who do you want to add?** (Chi si desidera aggiungere?) fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="7e39f-145">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
<span data-ttu-id="7e39f-146">Successivamente, configurare la cartella dei documenti del sito del team di SensitiveFiles per l'etichetta di conservazione riservata.</span><span class="sxs-lookup"><span data-stu-id="7e39f-146">Next, configure the Documents folder of the SensitiveFiles team site for the Sensitive retention label.</span></span>
  
1. <span data-ttu-id="7e39f-147">Nella scheda **SensitiveFiles** del browser fare clic su **documenti**.</span><span class="sxs-lookup"><span data-stu-id="7e39f-147">In the **SensitiveFiles** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="7e39f-148">Fare clic sull'icona delle impostazioni e selezionare **Impostazioni raccolta**.</span><span class="sxs-lookup"><span data-stu-id="7e39f-148">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="7e39f-149">In **Autorizzazioni e gestione** fare clic su **Apply label to items in this library** (Applica etichetta agli elementi in questa libreria).</span><span class="sxs-lookup"><span data-stu-id="7e39f-149">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
4. <span data-ttu-id="7e39f-150">In **impostazioni-Applica etichetta**, selezionare **sensibile** nell'elenco a discesa e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="7e39f-150">In **Settings-Apply Label**, select **Sensitive** in the drop-down box, and then click **Save**.</span></span>

<span data-ttu-id="7e39f-151">Successivamente, creare un nuovo documento nel sito di SensitiveFiles e modificarne l'etichetta di conservazione.</span><span class="sxs-lookup"><span data-stu-id="7e39f-151">Next, create a new document in the SensitiveFiles site and change its retention label.</span></span>
    
1. <span data-ttu-id="7e39f-152">Nella cartella documenti fare clic su **nuovo > documento di Word**.</span><span class="sxs-lookup"><span data-stu-id="7e39f-152">In the documents folder, click **New > Word document**.</span></span>
    
2. <span data-ttu-id="7e39f-153">Digitare del testo nel documento vuoto.</span><span class="sxs-lookup"><span data-stu-id="7e39f-153">Type some text in the blank document.</span></span> <span data-ttu-id="7e39f-154">Attendere che il testo venga salvato.</span><span class="sxs-lookup"><span data-stu-id="7e39f-154">Wait for the text to be saved.</span></span>
    
3. <span data-ttu-id="7e39f-155">Nella barra dei menu fare clic su **documenti condivisi**.</span><span class="sxs-lookup"><span data-stu-id="7e39f-155">In the menu bar, click **Shared Documents**.</span></span>
    
4. <span data-ttu-id="7e39f-156">Fare clic sull'icona di Word accanto al nome del file **Document. docx** .</span><span class="sxs-lookup"><span data-stu-id="7e39f-156">Click the Word icon next to the **Document.docx** file name.</span></span>
    
5. <span data-ttu-id="7e39f-157">Nel riquadro di destra, nella sezione **Proprietà** , in **Applica etichetta di conservazione**, tenere presente che il documento ha l'etichetta **riservata** applicata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="7e39f-157">In the right-hand pane, in the **Properties** section, under **Apply retention label**, note that the document has had the **Sensitive** label automatically applied.</span></span>
    
6. <span data-ttu-id="7e39f-158">Fare clic su **modifica tutto**.</span><span class="sxs-lookup"><span data-stu-id="7e39f-158">Click **Edit all**.</span></span>
    
7. <span data-ttu-id="7e39f-159">Nel riquadro **Document. docx** , in **Applica etichetta**, selezionare l'etichetta **estremamente riservata** , quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="7e39f-159">In the **Document.docx** pane, under **Apply label**, select the **Highly Confidential** label, and then click **Save**.</span></span>

<span data-ttu-id="7e39f-160">Per informazioni e collegamenti su come distribuire le etichette di conservazione di Office 365 in produzione, vedere la pagina [Configura classificazione per il](infoprotect-configure-classification.md) passaggio dell'ambiente nella fase di **protezione delle informazioni** .</span><span class="sxs-lookup"><span data-stu-id="7e39f-160">See the [Configure classification for your environment](infoprotect-configure-classification.md) step in the **Information protection** phase for information and links to how to deploy Office 365 retention labels in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="7e39f-161">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="7e39f-161">Next step</span></span>

<span data-ttu-id="7e39f-162">Esplorare le funzionalità e le funzionalità di [protezione delle informazioni](m365-enterprise-test-lab-guides.md#information-protection) aggiuntive nell'ambiente di testing.</span><span class="sxs-lookup"><span data-stu-id="7e39f-162">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="7e39f-163">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7e39f-163">See also</span></span>

[<span data-ttu-id="7e39f-164">Guide al lab di test di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="7e39f-164">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="7e39f-165">Distribuzione di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="7e39f-165">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="7e39f-166">Documentazione di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="7e39f-166">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)

 