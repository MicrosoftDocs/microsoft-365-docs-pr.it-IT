---
title: Classificazione dei dati per l'ambiente di testing Microsoft 365 Enterprise
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
description: Utilizzare questa guida del laboratorio di testing per creare e utilizzare etichette di conservazione nei documenti dell'ambiente di testing di Microsoft 365 Enterprise.
ms.openlocfilehash: 41873eba8f2d6168d68d771c6feb17a44c775f6a
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636093"
---
# <a name="data-classification-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="f1852-103">Classificazione dei dati per l'ambiente di testing Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f1852-103">Data classification for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="f1852-104">*Questa guida al lab di test può essere usata sia per ambienti di testing di Microsoft 365 Enterprise che Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="f1852-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="f1852-105">Con le istruzioni riportate in questo articolo, è possibile configurare la classificazione dei dati utilizzando le etichette di conservazione nell'ambiente di testing Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="f1852-105">With the instructions in this article, you configure data classification using retention labels in your Microsoft 365 Enterprise test environment.</span></span>

![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="f1852-107">Fare clic [qui](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) per consultare una mappa di tutti gli articoli relativi alla guida al lab test di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="f1852-107">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="f1852-108">Fase 1: Creare l'ambiente di testing di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f1852-108">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="f1852-109">Se si desidera solo configurare le etichette di conservazione in modo semplice con i requisiti minimi, seguire le istruzioni in [Lightweight base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="f1852-109">If you just want to configure retention labels in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="f1852-110">Se si desidera configurare le etichette di conservazione in un'azienda simulata, seguire le istruzioni riportate nell' [autenticazione pass-through](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="f1852-110">If you want to configure retention labels in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="f1852-111">La verifica delle etichette di conservazione non richiede l'ambiente di testing dell'organizzazione simulata, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per una foresta di servizi di dominio Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="f1852-111">Testing retention labels does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="f1852-112">Viene fornito come opzione in modo che sia possibile testare la licenza automatizzata e l'appartenenza ai gruppi e sperimentarla in un ambiente che rappresenta un'organizzazione tipica.</span><span class="sxs-lookup"><span data-stu-id="f1852-112">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-create-retention-labels"></a><span data-ttu-id="f1852-113">Fase 2: creare etichette di conservazione</span><span class="sxs-lookup"><span data-stu-id="f1852-113">Phase 2: Create retention labels</span></span>

<span data-ttu-id="f1852-114">In questa fase, vengono create le etichette di conservazione per i diversi livelli di conservazione per le cartelle di documenti di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="f1852-114">In this phase, you create the retention labels for the different levels of retention for SharePoint Online documents folders.</span></span>

1. <span data-ttu-id="f1852-115">Accedere al [Centro sicurezza Microsoft 365](https://security.microsoft.com/homepage) con l'account di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="f1852-115">Sign in to the [Microsoft 365 security center](https://security.microsoft.com/homepage) with your global admin account.</span></span>
    
2. <span data-ttu-id="f1852-116">Dalla scheda **sicurezza Home-Microsoft 365** del browser, fare clic su **classificazione > etichette di conservazione**.</span><span class="sxs-lookup"><span data-stu-id="f1852-116">From the **Home - Microsoft 365 security** tab of your browser, click **Classification > Retention labels**.</span></span>
    
3. <span data-ttu-id="f1852-117">Fare clic su **Crea un'etichetta**.</span><span class="sxs-lookup"><span data-stu-id="f1852-117">Click **Create a label**.</span></span>
    
4. <span data-ttu-id="f1852-118">Nel riquadro **Name Your label** , digitare **Public Internal** in **Name Your label**, quindi fare clic su **Next**.</span><span class="sxs-lookup"><span data-stu-id="f1852-118">In the **Name your label** pane, type **Internal Public** in **Name your label**, and then click **Next**.</span></span>

5. <span data-ttu-id="f1852-119">Nel riquadro dei **descrittori del piano file** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f1852-119">In the **File plan descriptors** pane, click **Next**.</span></span>
    
6. <span data-ttu-id="f1852-120">Nel riquadro **Impostazioni etichetta** , se necessario, impostare la **conservazione** **su**attivato e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f1852-120">In the **Label settings** pane, if needed, set **Retention** to **On**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="f1852-121">Nel riquadro **Verifica le impostazioni** fare clic su **crea l'etichetta**.</span><span class="sxs-lookup"><span data-stu-id="f1852-121">In the **Review your settings** pane, click **Create the label**.</span></span>
    
8. <span data-ttu-id="f1852-122">Ripetere i passaggi da 3 a 7 per altre etichette con i nomi seguenti:</span><span class="sxs-lookup"><span data-stu-id="f1852-122">Repeat steps 3-7 for additional labels with these names:</span></span>
    
  - <span data-ttu-id="f1852-123">Private</span><span class="sxs-lookup"><span data-stu-id="f1852-123">Private</span></span>
    
  - <span data-ttu-id="f1852-124">Dati sensibili</span><span class="sxs-lookup"><span data-stu-id="f1852-124">Sensitive</span></span>
    
  - <span data-ttu-id="f1852-125">Highly Confidential (Riservatezza elevata)</span><span class="sxs-lookup"><span data-stu-id="f1852-125">Highly Confidential</span></span>
  
9. <span data-ttu-id="f1852-126">Nel riquadro **etichette di conservazione** fare clic su **pubblica etichette**.</span><span class="sxs-lookup"><span data-stu-id="f1852-126">In the **Retention labels** pane, click **Publish labels**.</span></span>
    
10. <span data-ttu-id="f1852-127">Nel riquadro **Scegli etichette** da pubblicare, fare clic su **Scegli etichette da pubblicare**.</span><span class="sxs-lookup"><span data-stu-id="f1852-127">In the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
11. <span data-ttu-id="f1852-128">Nel riquadro **Scegli etichette** , fare clic su **Aggiungi** e selezionare le quattro etichette.</span><span class="sxs-lookup"><span data-stu-id="f1852-128">In the **Choose labels** pane, click **Add** and select all four labels.</span></span>
    
12. <span data-ttu-id="f1852-129">Fare clic su **Aggiungi**e quindi su **fine**.</span><span class="sxs-lookup"><span data-stu-id="f1852-129">Click **Add**, and then click **Done**.</span></span>
    
13. <span data-ttu-id="f1852-130">Nel riquadro **Choose labels to publish** (Scegli etichette da pubblicare) fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f1852-130">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
14. <span data-ttu-id="f1852-131">Nel riquadro **Choose locations** (Scegli posizioni) fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f1852-131">On the **Choose locations** pane, click **Next**.</span></span>
    
15. <span data-ttu-id="f1852-132">Nel riquadro **Denomina il criterio** digitare **Example organization** in **Nome**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f1852-132">On the **Name your policy** pane, type **Example organization** in **Name**, and then click **Next**.</span></span>
    
16. <span data-ttu-id="f1852-133">Nel riquadro **Verifica le impostazioni** fare clic su **pubblica etichette**.</span><span class="sxs-lookup"><span data-stu-id="f1852-133">On the **Review your settings** pane, click **Publish labels**.</span></span>
 
<span data-ttu-id="f1852-134">Tenere presente che potrebbero essere necessari alcuni minuti per la pubblicazione delle etichette di conservazione.</span><span class="sxs-lookup"><span data-stu-id="f1852-134">Note that it might take a few minutes for the retention labels to be published.</span></span>

## <a name="phase-3-apply-retention-labels-to-documents"></a><span data-ttu-id="f1852-135">Fase 3: applicare le etichette di conservazione ai documenti</span><span class="sxs-lookup"><span data-stu-id="f1852-135">Phase 3: Apply retention labels to documents</span></span>

<span data-ttu-id="f1852-136">In questa fase, viene individuato il comportamento predefinito dell'etichetta di conservazione per i file nella cartella documenti di un sito di SharePoint Online e viene modificata manualmente l'etichetta di conservazione di un documento.</span><span class="sxs-lookup"><span data-stu-id="f1852-136">In this phase, you discover the default retention label behavior for files in the Documents folder of a SharePoint Online site and manually change the retention label of a document.</span></span>

<span data-ttu-id="f1852-137">Per prima cosa, creare un sito del team di SharePoint Online a livello di riserva:</span><span class="sxs-lookup"><span data-stu-id="f1852-137">First, create a sensitive-level SharePoint Online team site:</span></span>
  
1. <span data-ttu-id="f1852-138">Se si utilizza un'istanza privata del browser, accedere al [portale di Office 365](https://portal.office.com) utilizzando l'account di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="f1852-138">Using a private instance of your browser, sign in to the [Office 365 portal](https://portal.office.com) using your global admin account.</span></span>
    
2. <span data-ttu-id="f1852-139">Nell'elenco dei riquadri fare clic su **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="f1852-139">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="f1852-140">Nella nuova scheda **SharePoint** del browser fare clic su **Crea sito**.</span><span class="sxs-lookup"><span data-stu-id="f1852-140">On the new **SharePoint** tab in your browser, click **Create site**.</span></span>
    
4. <span data-ttu-id="f1852-141">Nella pagina **Crea sito** fare clic su **Sito del team**.</span><span class="sxs-lookup"><span data-stu-id="f1852-141">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="f1852-142">In **nome sito del team**digitare **SensitiveFiles**.</span><span class="sxs-lookup"><span data-stu-id="f1852-142">In **Team site name**, type **SensitiveFiles**.</span></span>
    
6. <span data-ttu-id="f1852-143">In **Descrizione sito del team**, digitare **sito di SharePoint per i file riservati**.</span><span class="sxs-lookup"><span data-stu-id="f1852-143">In **Team site description**, type **SharePoint site for sensitive files**.</span></span>
    
7.  <span data-ttu-id="f1852-144">In **Impostazioni privacy** selezionare **Private - only members can access this site** (Privato: solo i membri possono accedere a questo sito) e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f1852-144">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="f1852-145">Nel riquadro **chi si desidera aggiungere?** , fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="f1852-145">In the **Who do you want to add?** pane, click **Finish**.</span></span>
    
<span data-ttu-id="f1852-146">Successivamente, configurare la cartella dei documenti del sito del team di SensitiveFiles per l'etichetta di conservazione riservata.</span><span class="sxs-lookup"><span data-stu-id="f1852-146">Next, configure the Documents folder of the SensitiveFiles team site for the Sensitive retention label.</span></span>
  
1. <span data-ttu-id="f1852-147">Nella scheda **SensitiveFiles** del browser fare clic su **documenti**.</span><span class="sxs-lookup"><span data-stu-id="f1852-147">In the **SensitiveFiles** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="f1852-148">Fare clic sull'icona delle impostazioni e selezionare **Impostazioni libreria**.</span><span class="sxs-lookup"><span data-stu-id="f1852-148">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="f1852-149">In **autorizzazioni e gestione**fare clic su **Applica etichetta agli elementi contenuti nell'elenco o nella raccolta**.</span><span class="sxs-lookup"><span data-stu-id="f1852-149">Under **Permissions and Management**, click **Apply label to items in this list or library**.</span></span> <span data-ttu-id="f1852-150">Se questa opzione non viene visualizzata, le etichette di conservazione non vengono ancora pubblicate.</span><span class="sxs-lookup"><span data-stu-id="f1852-150">If this option does not appear, your retention labels are not yet published.</span></span> <span data-ttu-id="f1852-151">Provare questo passaggio in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="f1852-151">Try this step at a later time.</span></span>
    
4. <span data-ttu-id="f1852-152">In **impostazioni-Applica etichetta**, selezionare **sensibile** nell'elenco a discesa e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f1852-152">In **Settings-Apply Label**, select **Sensitive** in the drop-down box, and then click **Save**.</span></span>

<span data-ttu-id="f1852-153">Successivamente, creare un nuovo documento nel sito di SensitiveFiles e modificarne l'etichetta di conservazione.</span><span class="sxs-lookup"><span data-stu-id="f1852-153">Next, create a new document in the SensitiveFiles site and change its retention label.</span></span>
    
1. <span data-ttu-id="f1852-154">Nella cartella documenti fare clic su **nuovo > documento di Word**.</span><span class="sxs-lookup"><span data-stu-id="f1852-154">In the documents folder, click **New > Word document**.</span></span>
    
2. <span data-ttu-id="f1852-155">Digitare del testo nel documento vuoto.</span><span class="sxs-lookup"><span data-stu-id="f1852-155">Type some text in the blank document.</span></span> <span data-ttu-id="f1852-156">Attendere che il testo venga salvato.</span><span class="sxs-lookup"><span data-stu-id="f1852-156">Wait for the text to be saved.</span></span>
    
3. <span data-ttu-id="f1852-157">Nella barra dei menu fare clic su **documenti condivisi**.</span><span class="sxs-lookup"><span data-stu-id="f1852-157">In the menu bar, click **Shared Documents**.</span></span>
    
4. <span data-ttu-id="f1852-158">Fare clic sul pulsante con i puntini di sospensione verticali accanto al nome del file **Document. docx** e quindi fare clic su **Dettagli**.</span><span class="sxs-lookup"><span data-stu-id="f1852-158">Click the vertical ellipsis next to the **Document.docx** file name, and then click **Details**.</span></span>
    
5. <span data-ttu-id="f1852-159">Nel riquadro di destra, nella sezione **Proprietà** , in **Apply Retention label**, tenere presente che il documento ha l'etichetta di conservazione **riservata** applicata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="f1852-159">In the right-hand pane, in the **Properties** section, under **Apply retention label**, note that the document has had the **Sensitive** retention label automatically applied.</span></span>
    
6. <span data-ttu-id="f1852-160">Fare clic su **modifica tutto**.</span><span class="sxs-lookup"><span data-stu-id="f1852-160">Click **Edit all**.</span></span>
    
7. <span data-ttu-id="f1852-161">Nel riquadro **Document. docx** , in **Apply Retention label**, selezionare l'etichetta **estremamente riservata** , quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f1852-161">In the **Document.docx** pane, under **Apply retention label**, select the **Highly Confidential** label, and then click **Save**.</span></span>

<span data-ttu-id="f1852-162">Per informazioni e collegamenti su come distribuire le etichette di conservazione in produzione, vedere la pagina [Configura classificazione per il](infoprotect-configure-classification.md) passaggio dell'ambiente nella fase di **protezione delle informazioni** .</span><span class="sxs-lookup"><span data-stu-id="f1852-162">See the [Configure classification for your environment](infoprotect-configure-classification.md) step in the **Information protection** phase for information and links to how to deploy retention labels in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="f1852-163">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="f1852-163">Next step</span></span>

<span data-ttu-id="f1852-164">Esplorare le funzionalità e le funzionalità di [protezione delle informazioni](m365-enterprise-test-lab-guides.md#information-protection) aggiuntive nell'ambiente di testing.</span><span class="sxs-lookup"><span data-stu-id="f1852-164">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="f1852-165">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f1852-165">See also</span></span>

[<span data-ttu-id="f1852-166">Guide al lab di test di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f1852-166">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="f1852-167">Distribuzione di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f1852-167">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="f1852-168">Documentazione di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f1852-168">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)

 
