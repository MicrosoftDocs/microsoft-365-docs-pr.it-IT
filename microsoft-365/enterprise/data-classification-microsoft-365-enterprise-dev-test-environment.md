---
title: Ambiente di testing di classificazione dei dati per la propria azienda 365 Microsoft
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/16/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Utilizzare questa guida dei laboratori di testing per creare e utilizzare le etichette di Office 365 su documenti nell'ambiente di test Microsoft 365 aziendale.
ms.openlocfilehash: 33ac1fa8e26c0037882e6c240cc04ec19e6a6a7b
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2019
ms.locfileid: "26868893"
---
# <a name="data-classification-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="9afb6-103">Ambiente di testing di classificazione dei dati per la propria azienda 365 Microsoft</span><span class="sxs-lookup"><span data-stu-id="9afb6-103">Data classification for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="9afb6-104">Con le istruzioni riportate in questo articolo, si configura la classificazione dei dati utilizzando le etichette di Office 365 conservazione nell'ambiente di test Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="9afb6-104">With the instructions in this article, you configure data classification using Office 365 retention labels in your Microsoft 365 Enterprise test environment.</span></span>

![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="9afb6-106">Fare clic [qui](https://aka.ms/m365etlgstack) per consultare una mappa di tutti gli articoli relativi alla guida al lab test di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="9afb6-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="9afb6-107">Fase 1: Preparare l'ambiente di testing Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="9afb6-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="9afb6-108">Se si desidera configurare le etichette di Office 365 in un modo semplice con i requisiti minimi, seguire le istruzioni di [configurazione di base semplificata](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="9afb6-108">If you just want to configure Office 365 labels in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="9afb6-109">Se si desidera configurare le etichette di Office 365 in un'azienda simulata, seguire le istruzioni [nell'autenticazione pass-through](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="9afb6-109">If you want to configure Office 365 labels in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="9afb6-p101">Testare le etichette di Office 365 non richiede l'ambiente di testing simulato enterprise, che include una rete intranet simulata connessione a Internet e la sincronizzazione delle directory per una foresta Windows Server Active Directory. Viene fornito qui come un'opzione in modo che sia possibile testare gestione automatica delle licenze e l'appartenenza al gruppo e sperimentare in un ambiente che rappresenta una tipica organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9afb6-p101">Testing Office 365 labels does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-create-office-365-labels"></a><span data-ttu-id="9afb6-112">Fase 2: creare etichette di Office 365</span><span class="sxs-lookup"><span data-stu-id="9afb6-112">Phase 2: Create Office 365 labels</span></span>

<span data-ttu-id="9afb6-113">In questa fase è creare etichette per i diversi livelli di conservazione per la cartella documenti di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="9afb6-113">In this phase, you create the labels for the different levels of retention for SharePoint Online documents folders.</span></span>
  
1. <span data-ttu-id="9afb6-p102">Se necessario, utilizzare un'istanza del browser Internet privata e accedere al portale di Office con l'account di amministratore globale. Per ulteriori informazioni, vedere [la posizione in cui eseguire l'accesso a Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="9afb6-p102">If needed, use a private instance of your Internet browser and sign in to the Office portal with your global administrator account. For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="9afb6-116">Nella scheda **Microsoft Office Home** fare clic sul riquadro **Amministratore**.</span><span class="sxs-lookup"><span data-stu-id="9afb6-116">From the **Microsoft Office Home** tab, click the **Admin** tile.</span></span>
    
3. <span data-ttu-id="9afb6-117">Nella nuova scheda **Interfaccia di amministrazione di Office** del browser fare clic su **Interfacce di amministrazione > Sicurezza e conformità**.</span><span class="sxs-lookup"><span data-stu-id="9afb6-117">From the new **Office Admin center** tab of your browser, click **Admin centers > Security &amp; Compliance**.</span></span>
    
4. <span data-ttu-id="9afb6-p103">Dalla nuova **Home - sicurezza &amp; conformità** scheda del browser, fare clic su **classificazioni > etichette**. Dal **Home > etichette** riquadro, fare clic sulla scheda **conservazione** .</span><span class="sxs-lookup"><span data-stu-id="9afb6-p103">From the new **Home - Security &amp; Compliance** tab of your browser, click **Classifications > Labels**. From the **Home > Labels** pane, click the **Retention** tab.</span></span>
    
5. <span data-ttu-id="9afb6-120">Fare clic su **Crea un'etichetta**.</span><span class="sxs-lookup"><span data-stu-id="9afb6-120">Click **Create a label**.</span></span>
    
6. <span data-ttu-id="9afb6-121">Nel riquadro **Name your label** (Denomina l'etichetta) digitare **Internal Public**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="9afb6-121">On the **Name your label** pane, type **Internal Public**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="9afb6-122">Nel riquadro **Label settings** (Importazioni etichetta) fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="9afb6-122">On the **Label settings** pane, click **Next**.</span></span>
    
8. <span data-ttu-id="9afb6-123">Nel riquadro **Verifica le impostazioni** fare clic su **Crea questa etichetta** e fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="9afb6-123">On the **Review your settings** pane, click **Create this label**, and then click **Close**.</span></span>
    
9. <span data-ttu-id="9afb6-124">Ripetere i passaggi 5-8 per queste etichette aggiuntive:</span><span class="sxs-lookup"><span data-stu-id="9afb6-124">Repeat steps 5-8 for these additional labels:</span></span>
    
  - <span data-ttu-id="9afb6-125">Private</span><span class="sxs-lookup"><span data-stu-id="9afb6-125">Private</span></span>
    
  - <span data-ttu-id="9afb6-126">Dati sensibili</span><span class="sxs-lookup"><span data-stu-id="9afb6-126">Sensitive</span></span>
    
  - <span data-ttu-id="9afb6-127">Highly Confidential (Riservatezza elevata)</span><span class="sxs-lookup"><span data-stu-id="9afb6-127">Highly Confidential</span></span>
    
10. <span data-ttu-id="9afb6-128">Dal riquadro **Home > Etichette** fare clic su **Publish labels** (Pubblica etichette).</span><span class="sxs-lookup"><span data-stu-id="9afb6-128">From the **Home > Labels** pane, click **Publish labels**.</span></span>
    
11. <span data-ttu-id="9afb6-129">Nel riquadro **Choose labels to publish** (Scegli etichette da pubblicare) fare clic su **Choose labels to publish** (Scegli etichette da pubblicare).</span><span class="sxs-lookup"><span data-stu-id="9afb6-129">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
12. <span data-ttu-id="9afb6-130">Nel riquadro **Choose labels** (Scegli etichette) fare clic su **Aggiungi** e selezionare le quattro etichette.</span><span class="sxs-lookup"><span data-stu-id="9afb6-130">On the **Choose labels** pane, click **Add** and select all four labels.</span></span>
    
13. <span data-ttu-id="9afb6-131">Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="9afb6-131">Click **Done**.</span></span>
    
14. <span data-ttu-id="9afb6-132">Nel riquadro **Choose labels to publish** (Scegli etichette da pubblicare) fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="9afb6-132">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
15. <span data-ttu-id="9afb6-133">Nel riquadro **Choose locations** (Scegli posizioni) fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="9afb6-133">On the **Choose locations** pane, click **Next**.</span></span>
    
16. <span data-ttu-id="9afb6-134">Nel riquadro **Denomina il criterio** digitare **Example organization** in **Nome**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="9afb6-134">On the **Name your policy** pane, type **Example organization** in **Name**, and then click **Next**.</span></span>
    
17. <span data-ttu-id="9afb6-135">Nel riquadro **Verifica le impostazioni** fare clic su **Publish labels** (Pubblica etichette), quindi fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="9afb6-135">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>

<span data-ttu-id="9afb6-136">Si noti che potrebbe richiedere alcuni minuti per le etichette per la pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="9afb6-136">Note that it might take a few minutes for the labels to be published.</span></span>

## <a name="phase-3-apply-office-365-retention-labels-to-documents"></a><span data-ttu-id="9afb6-137">Fase 3: Applicare etichette di conservazione di Office 365 ai documenti</span><span class="sxs-lookup"><span data-stu-id="9afb6-137">Phase 3: Apply Office 365 retention labels to documents</span></span>

<span data-ttu-id="9afb6-138">In questa fase, individuare il comportamento di etichetta predefinito per i file nella cartella documenti di un sito di SharePoint Online e modificare manualmente l'etichetta di un documento.</span><span class="sxs-lookup"><span data-stu-id="9afb6-138">In this phase, you discover the default label behavior for files in the Documents folder of a SharePoint Online site and manually change the label of a document.</span></span>

<span data-ttu-id="9afb6-139">Per prima cosa, creare un sito del team di SharePoint Online riservati livello:</span><span class="sxs-lookup"><span data-stu-id="9afb6-139">First, create a sensitive-level SharePoint Online team site:</span></span>
  
1. <span data-ttu-id="9afb6-p104">Utilizzando un browser nel computer locale, accedere al portale di Office utilizzando l'account amministratore globale. Per ulteriori informazioni, vedere [la posizione in cui eseguire l'accesso a Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="9afb6-p104">Using a browser on your local computer, sign in to the Office portal using your global administrator account. For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="9afb6-142">Nell'elenco dei riquadri fare clic su **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="9afb6-142">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="9afb6-143">Nella scheda **SharePoint** nuovo nel browser, fare clic su **Crea sito**.</span><span class="sxs-lookup"><span data-stu-id="9afb6-143">On the new **SharePoint** tab in your browser, click **Create site**.</span></span>
    
4. <span data-ttu-id="9afb6-144">Nella pagina **Crea sito** fare clic su **Sito del team**.</span><span class="sxs-lookup"><span data-stu-id="9afb6-144">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="9afb6-145">**Nome del sito del Team**, digitare **SensitiveFiles**.</span><span class="sxs-lookup"><span data-stu-id="9afb6-145">In **Team site name**, type **SensitiveFiles**.</span></span>
    
6. <span data-ttu-id="9afb6-146">Nella **descrizione del sito del Team**, digitare **sito di SharePoint per i file riservati**.</span><span class="sxs-lookup"><span data-stu-id="9afb6-146">In **Team site description**, type **SharePoint site for sensitive files**.</span></span>
    
7.  <span data-ttu-id="9afb6-147">In **Impostazioni privacy** selezionare **Private - only members can access this site** (Privato: solo i membri possono accedere a questo sito) e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="9afb6-147">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="9afb6-148">Nel riquadro **Who do you want to add?** (Chi si desidera aggiungere?) fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="9afb6-148">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
<span data-ttu-id="9afb6-149">Configurare quindi la cartella documenti del sito del team SensitiveFiles per l'etichetta riservato.</span><span class="sxs-lookup"><span data-stu-id="9afb6-149">Next, configure the Documents folder of the SensitiveFiles team site for the Sensitive label.</span></span>
  
1. <span data-ttu-id="9afb6-150">Nella scheda **SensitiveFiles** del browser fare clic su **documenti**.</span><span class="sxs-lookup"><span data-stu-id="9afb6-150">In the **SensitiveFiles** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="9afb6-151">Fare clic sull'icona delle impostazioni e selezionare **Impostazioni libreria**.</span><span class="sxs-lookup"><span data-stu-id="9afb6-151">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="9afb6-152">In **Autorizzazioni e gestione** fare clic su **Apply label to items in this library** (Applica etichetta agli elementi in questa libreria).</span><span class="sxs-lookup"><span data-stu-id="9afb6-152">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
4. <span data-ttu-id="9afb6-153">In **Impostazioni si applicano etichetta**, selezionare **riservati** nella casella di riepilogo a discesa e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="9afb6-153">In **Settings-Apply Label**, select **Sensitive** in the drop-down box, and then click **Save**.</span></span>

<span data-ttu-id="9afb6-154">Successivamente, creare un nuovo documento nel sito SensitiveFiles e modificare l'etichetta.</span><span class="sxs-lookup"><span data-stu-id="9afb6-154">Next, create a new document in the SensitiveFiles site and change its label.</span></span>
    
1. <span data-ttu-id="9afb6-155">Nella cartella documenti fare clic su **Nuovo > documento di Word**.</span><span class="sxs-lookup"><span data-stu-id="9afb6-155">In the documents folder, click **New > Word document**.</span></span>
    
2. <span data-ttu-id="9afb6-p105">Digitare un testo nel documento vuoto. Attendere il testo da salvare.</span><span class="sxs-lookup"><span data-stu-id="9afb6-p105">Type some text in the blank document. Wait for the text to be saved.</span></span>
    
3. <span data-ttu-id="9afb6-158">Nella barra dei menu fare clic su **Documenti condivisi**.</span><span class="sxs-lookup"><span data-stu-id="9afb6-158">In the menu bar, click **Shared Documents**.</span></span>
    
4. <span data-ttu-id="9afb6-159">Fare clic sull'icona Word accanto al nome del file **Document.docx** .</span><span class="sxs-lookup"><span data-stu-id="9afb6-159">Click the Word icon next to the **Document.docx** file name.</span></span>
    
5. <span data-ttu-id="9afb6-160">Nel riquadro di destra, nella sezione **proprietà** , in **Applica etichetta di conservazione**, tenere presente che il documento ha avuto l'etichetta **riservati** applicato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="9afb6-160">In the right-hand pane, in the **Properties** section, under **Apply retention label**, note that the document has had the **Sensitive** label automatically applied.</span></span>
    
6. <span data-ttu-id="9afb6-161">Fare clic su **Modifica tutte**.</span><span class="sxs-lookup"><span data-stu-id="9afb6-161">Click **Edit all**.</span></span>
    
7. <span data-ttu-id="9afb6-162">Nel riquadro **Document.docx** , in **Applica etichetta**, selezionare l'etichetta **Altamente riservati** e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="9afb6-162">In the **Document.docx** pane, under **Apply label**, select the **Highly Confidential** label, and then click **Save**.</span></span>

<span data-ttu-id="9afb6-163">Nella fase di **protezione delle informazioni** per informazioni e collegamenti a Office 365 le etichette di conservazione nell'ambiente di produzione, vedere la sezione [configurare classificazione per l'ambiente](infoprotect-configure-classification.md) .</span><span class="sxs-lookup"><span data-stu-id="9afb6-163">See the [Configure classification for your environment](infoprotect-configure-classification.md) step in the **Information protection** phase for information and links to Office 365 retention labels in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="9afb6-164">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="9afb6-164">Next step</span></span>

<span data-ttu-id="9afb6-165">Esplorare le funzionalità aggiuntive [la protezione delle informazioni](m365-enterprise-test-lab-guides.md#information-protection) e le funzionalità nell'ambiente di testing.</span><span class="sxs-lookup"><span data-stu-id="9afb6-165">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="9afb6-166">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9afb6-166">See also</span></span>

[<span data-ttu-id="9afb6-167">Guide al lab di test di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="9afb6-167">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="9afb6-168">Distribuzione di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="9afb6-168">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="9afb6-169">Documentazione di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="9afb6-169">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)

 