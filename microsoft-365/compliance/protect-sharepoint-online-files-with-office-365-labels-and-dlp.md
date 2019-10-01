---
title: Proteggere i file di SharePoint Online con le etichette di conservazione e la prevenzione della perdita dei dati
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 06/18/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
ms.assetid: c9f837af-8d71-4df1-a285-dedb1c5618b3
description: 'Sintesi: applicare etichette di conservazione e criteri di prevenzione della perdita dei dati ai siti del team di SharePoint Online con vari livelli di protezione delle informazioni.'
ms.openlocfilehash: 77da4ec44e31fae8db2c37ebc39233f76c5e4dd3
ms.sourcegitcommit: 8e5b799efd3ddd0eae9dd2835c3783103817fb4b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/30/2019
ms.locfileid: "37317608"
---
# <a name="protect-sharepoint-online-files-with-retention-labels-and-dlp"></a><span data-ttu-id="f8c22-103">Proteggere i file di SharePoint Online con le etichette di conservazione e la prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="f8c22-103">Protect SharePoint Online files with retention labels and DLP</span></span>

 <span data-ttu-id="f8c22-104">**Sintesi:** applicare etichette di conservazione e criteri di prevenzione della perdita dei dati ai siti del team di SharePoint Online con vari livelli di protezione delle informazioni.</span><span class="sxs-lookup"><span data-stu-id="f8c22-104">**Summary:** Apply retention labels and data loss prevention (DLP) policies for SharePoint Online team sites with various levels of information protection.</span></span>
  
<span data-ttu-id="f8c22-105">Usare i passaggi descritti in questo articolo per progettare e implementare le etichette di conservazione e i criteri di protezione della perdita dei dati (DLP) per i siti del team di SharePoint Online di base, riservati ed estremamente riservati.</span><span class="sxs-lookup"><span data-stu-id="f8c22-105">Use the steps in this article to design and deploy retention labels and DLP policies for baseline, sensitive, and highly confidential SharePoint Online team sites.</span></span> <span data-ttu-id="f8c22-106">Per altre informazioni su questi tre livelli di protezione, vedere [Proteggere siti e file di SharePoint Online](/security/office-365-security/secure-sharepoint-online-sites-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="f8c22-106">For more information about these three tiers of protection, see [Secure SharePoint Online sites and files](/security/office-365-security/secure-sharepoint-online-sites-and-files.md).</span></span>
  
## <a name="how-this-works"></a><span data-ttu-id="f8c22-107">Funzionamento</span><span class="sxs-lookup"><span data-stu-id="f8c22-107">How this works</span></span>

1. <span data-ttu-id="f8c22-108">Creare le etichette di conservazione desiderate e pubblicarle.</span><span class="sxs-lookup"><span data-stu-id="f8c22-108">Create the desired retention labels and publish these.</span></span> <span data-ttu-id="f8c22-109">La pubblicazione può richiedere fino a 12 ore.</span><span class="sxs-lookup"><span data-stu-id="f8c22-109">It can take up to 12 hours for these to be published.</span></span>
2. <span data-ttu-id="f8c22-110">Per i siti di SharePoint desiderati, modificare le impostazioni della raccolta documenti per applicare le etichette di conservazione desiderate agli elementi della raccolta.</span><span class="sxs-lookup"><span data-stu-id="f8c22-110">For the desired SharePoint sites, edit the document library settings to apply the desired retention labels to items in the library.</span></span>
3. <span data-ttu-id="f8c22-111">Creare criteri di prevenzione della perdita dei dati per intervenire in base alle etichette di conservazione.</span><span class="sxs-lookup"><span data-stu-id="f8c22-111">Create DLP policies to take action based on the retention labels.</span></span>

<span data-ttu-id="f8c22-112">Quando gli utenti aggiungono un documento alla raccolta, il documento riceve per impostazione predefinita l'etichetta di conservazione assegnata.</span><span class="sxs-lookup"><span data-stu-id="f8c22-112">When users add a document to the library, the document will receive the assigned retention label by default.</span></span> <span data-ttu-id="f8c22-113">È possibile modificare l'etichetta, se necessario.</span><span class="sxs-lookup"><span data-stu-id="f8c22-113">Users can change the label, if needed.</span></span> <span data-ttu-id="f8c22-114">Quando un utente condivide un documento all'esterno dell'organizzazione, i criteri di prevenzione della perdita dei dati verificano se è assegnata un'etichetta e intervengono in caso di corrispondenza all'etichetta.</span><span class="sxs-lookup"><span data-stu-id="f8c22-114">When a user shares a document outside the organization, DLP will check to see if a label is assigned and take action if a DLP policy matches the label.</span></span> <span data-ttu-id="f8c22-115">Quindi cercano la corrispondenza anche ad altri criteri, ad esempio la protezione dei file con i numeri di carta di credito, se questo tipo di criterio è configurato.</span><span class="sxs-lookup"><span data-stu-id="f8c22-115">DLP will look for other policy matches as well, such as protecting files with credit card numbers if this type of policy is configured.</span></span> 

## <a name="retention-labels-for-your-sharepoint-online-sites"></a><span data-ttu-id="f8c22-116">Etichette di conservazione per i siti di SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f8c22-116">Retention labels for your SharePoint Online sites</span></span>

<span data-ttu-id="f8c22-117">La procedura per creare e poi assegnare etichette di conservazione ai siti del team di SharePoint Online prevede tre fasi.</span><span class="sxs-lookup"><span data-stu-id="f8c22-117">There are three phases to creating and then assigning retention labels to SharePoint Online team sites.</span></span>
  
### <a name="phase-1-determine-the-retention-label-names"></a><span data-ttu-id="f8c22-118">Fase 1: Definire i nomi delle etichette di conservazione</span><span class="sxs-lookup"><span data-stu-id="f8c22-118">Phase 1: Determine the retention label names</span></span>

<span data-ttu-id="f8c22-119">In questa fase si definiscono i nomi delle etichette di conservazione per i quattro livelli di protezione delle informazioni applicati ai siti del team di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="f8c22-119">In this phase, you determine the names of your retention labels for the four levels of information protection applied to SharePoint Online team sites.</span></span> <span data-ttu-id="f8c22-120">La tabella seguente elenca i nomi consigliati per ogni livello.</span><span class="sxs-lookup"><span data-stu-id="f8c22-120">The following table lists the recommended names for each level.</span></span>
  
|<span data-ttu-id="f8c22-121">**Livello di protezione del sito del team di SharePoint Online**</span><span class="sxs-lookup"><span data-stu-id="f8c22-121">**SharePoint Online team site protection level**</span></span>|<span data-ttu-id="f8c22-122">**Nome etichetta**</span><span class="sxs-lookup"><span data-stu-id="f8c22-122">**Label name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f8c22-123">Pubblico di base</span><span class="sxs-lookup"><span data-stu-id="f8c22-123">Baseline-Public</span></span>  <br/> |<span data-ttu-id="f8c22-124">Pubblico interno</span><span class="sxs-lookup"><span data-stu-id="f8c22-124">Internal public</span></span>  <br/> |
|<span data-ttu-id="f8c22-125">Privato di base</span><span class="sxs-lookup"><span data-stu-id="f8c22-125">Baseline-Private</span></span>  <br/> |<span data-ttu-id="f8c22-126">Private</span><span class="sxs-lookup"><span data-stu-id="f8c22-126">Private</span></span>  <br/> |
|<span data-ttu-id="f8c22-127">Dati sensibili</span><span class="sxs-lookup"><span data-stu-id="f8c22-127">Sensitive</span></span>  <br/> |<span data-ttu-id="f8c22-128">Dati sensibili</span><span class="sxs-lookup"><span data-stu-id="f8c22-128">Sensitive</span></span>  <br/> |
|<span data-ttu-id="f8c22-129">Highly Confidential (Riservatezza elevata)</span><span class="sxs-lookup"><span data-stu-id="f8c22-129">Highly Confidential</span></span>  <br/> |<span data-ttu-id="f8c22-130">Highly Confidential (Riservatezza elevata)</span><span class="sxs-lookup"><span data-stu-id="f8c22-130">Highly Confidential</span></span>  <br/> |
   
### <a name="phase-2-create-the-retention-labels"></a><span data-ttu-id="f8c22-131">Fase 2: Creare le etichette di conservazione</span><span class="sxs-lookup"><span data-stu-id="f8c22-131">Phase 2: Create the retention labels</span></span>

<span data-ttu-id="f8c22-132">In questa fase si creano e poi pubblicano le etichette specificate per i diversi livelli di protezione delle informazioni.</span><span class="sxs-lookup"><span data-stu-id="f8c22-132">In this phase, you create and then publish your determined labels for the different levels of information protection.</span></span>
  
1. <span data-ttu-id="f8c22-133">Accedere al [portale Conformità Microsoft 365](https://compliance.microsoft.com) con un account che dispone del ruolo Amministratore della sicurezza oppure Amministratore della società.</span><span class="sxs-lookup"><span data-stu-id="f8c22-133">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com) with an account that has the Security Administrator or Company Administrator role.</span></span>
    
2. <span data-ttu-id="f8c22-134">Dalla scheda **Home: Conformità Microsoft 365** del browser fare clic su **Classificazioni > Etichette**.</span><span class="sxs-lookup"><span data-stu-id="f8c22-134">From the **Home - Microsoft 365 compliance** tab of your browser, click **Classifications > Labels**.</span></span>
    
3. <span data-ttu-id="f8c22-135">Fare clic su **Etichette di conservazione > Crea un'etichetta**.</span><span class="sxs-lookup"><span data-stu-id="f8c22-135">Click **Retention labels > Create a label**.</span></span>
    
4. <span data-ttu-id="f8c22-136">Nel riquadro **Assegnare un nome all'etichetta** digitare il nome dell’etichetta e una descrizione per amministratori e utenti, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f8c22-136">On the **Name your label** pane, type the name of the label and a description for admins and users, and then click **Next**.</span></span>

5. <span data-ttu-id="f8c22-137">Nel riquadro **Descrittori del piano di archiviazione** compilare come necessario e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f8c22-137">On the **File plan descriptors** pane, fill in as needed, and then click **Next**.</span></span>
    
6. <span data-ttu-id="f8c22-138">Nel riquadro **Impostazioni etichetta** impostare **Conservazione** su **Sì**, se necessario, e configurare le impostazioni di conservazione.</span><span class="sxs-lookup"><span data-stu-id="f8c22-138">On the **Label settings** pane, if needed, set **Retention** to **On** and configure retention settings.</span></span> <span data-ttu-id="f8c22-139">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f8c22-139">Click **Next**.</span></span>
    
7. <span data-ttu-id="f8c22-140">Nel riquadro **Rivedere le impostazioni** fare clic su **Crea etichetta**.</span><span class="sxs-lookup"><span data-stu-id="f8c22-140">On the **Review your settings** pane, click **Create the label**.</span></span>
    
8. <span data-ttu-id="f8c22-141">Per etichette aggiuntive, fare clic su **Crea un'etichetta** e ripetere i passaggi da 3 a 7 in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="f8c22-141">For your additional labels, click **Create a label**, and then repeat steps 3-7 as needed.</span></span>
    

### <a name="publish-your-new-labels"></a><span data-ttu-id="f8c22-142">Pubblicare le nuove etichette</span><span class="sxs-lookup"><span data-stu-id="f8c22-142">Publish your new labels</span></span>

<span data-ttu-id="f8c22-143">Successivamente, seguire questa procedura per pubblicare le nuove etichette di conservazione.</span><span class="sxs-lookup"><span data-stu-id="f8c22-143">Next, use these steps to publish the new retention labels.</span></span>
  
1. <span data-ttu-id="f8c22-144">Nel riquadro **Etichette** fare clic sulla scheda **Etichette di conservazione** e quindi su **Pubblica etichette**.</span><span class="sxs-lookup"><span data-stu-id="f8c22-144">From the **Labels** pane, click the **Retention labels** tab, and then click **Publish labels**.</span></span>
    
2. <span data-ttu-id="f8c22-145">Nel riquadro **Scegliere le etichette da pubblicare** fare clic su **Scegliere le etichette da pubblicare**.</span><span class="sxs-lookup"><span data-stu-id="f8c22-145">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
3. <span data-ttu-id="f8c22-146">Nel riquadro **Scegli etichette** fare clic su **Aggiungi**, selezionare le quattro etichette e fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="f8c22-146">On the **Choose labels** pane, click **Add**, select all four labels, click **Add**.</span></span>
    
4. <span data-ttu-id="f8c22-147">Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="f8c22-147">Click **Done**.</span></span>
    
5. <span data-ttu-id="f8c22-148">Nel riquadro **Choose labels to publish** (Scegli etichette da pubblicare) fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f8c22-148">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
6. <span data-ttu-id="f8c22-149">Nel riquadro **Choose locations** (Scegli posizioni) fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f8c22-149">On the **Choose locations** pane, click **Next**.</span></span>
    
7. <span data-ttu-id="f8c22-150">Nel riquadro **Denomina il criterio**, digitare un nome per il set di etichette in **Nome**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f8c22-150">On the **Name your policy** pane, type a name for your set of labels in **Name**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="f8c22-151">Nel riquadro **Verifica le impostazioni** fare clic su **Publish labels** (Pubblica etichette), quindi fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="f8c22-151">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>

    
### <a name="phase-3-apply-the-retention-labels-to-your-sharepoint-online-sites"></a><span data-ttu-id="f8c22-152">Fase 3: applicare le etichette di conservazione ai siti di SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f8c22-152">Phase 3: Apply the retention labels to your SharePoint Online sites</span></span>

<span data-ttu-id="f8c22-153">Seguire questa procedura per applicare le etichette di conservazione alle cartelle di documenti dei siti del team di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="f8c22-153">Use these steps to apply the retention labels to the documents folders of your SharePoint Online team sites.</span></span>
  
1. <span data-ttu-id="f8c22-154">Accedere al [portale di Office 365](https://www.office.com) e fare clic sull'app **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="f8c22-154">Sign in to the [Office 365 portal](https://www.office.com), click the **SharePoint** app.</span></span>
    
2. <span data-ttu-id="f8c22-155">Nella nuova scheda **SharePoint** del browser selezionare un sito per cui è necessario assegnare un'etichetta di conservazione.</span><span class="sxs-lookup"><span data-stu-id="f8c22-155">On the new **SharePoint** tab in your browser, click a site that needs a retention label assigned.</span></span>
    
3. <span data-ttu-id="f8c22-156">Nella nuova scheda del sito di SharePoint del browser fare clic su **Documenti**.</span><span class="sxs-lookup"><span data-stu-id="f8c22-156">In the new SharePoint site tab of your browser, click **Documents**.</span></span>
    
4. <span data-ttu-id="f8c22-157">Fare clic sull'icona delle impostazioni e selezionare **Impostazioni libreria**.</span><span class="sxs-lookup"><span data-stu-id="f8c22-157">Click the settings icon, and then click **Library settings**.</span></span>
    
5. <span data-ttu-id="f8c22-158">In **Autorizzazioni e gestione** fare clic su **Apply label to items in this library** (Applica etichetta agli elementi in questa libreria).</span><span class="sxs-lookup"><span data-stu-id="f8c22-158">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
6. <span data-ttu-id="f8c22-159">In **Impostazioni - Applica etichetta**, selezionare l'etichetta di conservazione appropriata, quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f8c22-159">In **Settings-Apply Label**, select the appropriate retention label, and then click **Save**.</span></span>
    
7. <span data-ttu-id="f8c22-160">Chiudere la scheda per il sito di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="f8c22-160">Close the tab for the SharePoint Online site.</span></span>
    
8. <span data-ttu-id="f8c22-161">Ripetere i passaggi da 2 a 8 per assegnare le etichette di conservazione a siti di SharePoint Online aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="f8c22-161">Repeat steps 2-8 to assign retention labels to your additional SharePoint Online sites.</span></span>
    
<span data-ttu-id="f8c22-162">Questa è la configurazione risultante.</span><span class="sxs-lookup"><span data-stu-id="f8c22-162">Here is your resulting configuration.</span></span>
  
![Etichette di conservazione per i quattro tipi di siti del team di SharePoint Online.](media/e0a4fdd2-1c30-4d93-8af4-a6f0c6c29966.png)
  
## <a name="dlp-policies-for-your-sharepoint-online-sites"></a><span data-ttu-id="f8c22-164">Criteri di prevenzione della perdita dei dati per siti di SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f8c22-164">DLP policies for your SharePoint Online sites</span></span>

<span data-ttu-id="f8c22-165">Seguire questa procedura per configurare un criterio della prevenzione della perdita dei dati che notifica agli utenti la condivisione di un documento in un sito sensibile del team di SharePoint Online all'esterno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f8c22-165">Use these steps to configure a DLP policy that notifies users when they share a document on a SharePoint Online sensitive team site outside the organization.</span></span>

1. <span data-ttu-id="f8c22-166">Accedere al [portale Conformità Microsoft 365](https://compliance.microsoft.com/) con un account che dispone del ruolo Amministratore della sicurezza oppure Amministratore della società.</span><span class="sxs-lookup"><span data-stu-id="f8c22-166">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com/) with an account that has the Security Administrator or Company Administrator role.</span></span>
    
2. <span data-ttu-id="f8c22-167">Nella nuova scheda **Sicurezza Microsoft 365** del browser fare clic su **Criteri > Prevenzione della perdita dei dati**.</span><span class="sxs-lookup"><span data-stu-id="f8c22-167">On the new **Microsoft 365 compliance** tab in your browser, click **Policies > Data loss prevention**.</span></span>
    
3. <span data-ttu-id="f8c22-168">Nel riquadro **Home > Prevenzione della perdita dei dati** fare clic su **Crea un criterio**.</span><span class="sxs-lookup"><span data-stu-id="f8c22-168">In the **Home > Data loss prevention** pane, click **Create a policy**.</span></span>
    
4. <span data-ttu-id="f8c22-169">Nel riquadro **Iniziare con un modello o creare un criterio personalizzato** fare clic su **Personalizza**, quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f8c22-169">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="f8c22-170">Nel riquadro **Denomina il criterio**, digitare il nome per il criterio DLP di livello riservato in **Nome**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f8c22-170">In the **Name your policy** pane, type the name for the sensitive level DLP policy in **Name**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="f8c22-171">Nel riquadro **Scegli posizioni** fare clic su **Consenti di scegliere posizioni specifiche** e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f8c22-171">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="f8c22-172">Nell'elenco di località, disabilitare le località **Posta elettronica di Exchange**, **Account di OneDrive** e **Messaggi di chat e canali di Teams**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f8c22-172">In the list of locations, disable the **Exchange email**, **OneDrive accounts**, and **Teams chat and channel messages** locations, and then click **Next**.</span></span>
    
8. <span data-ttu-id="f8c22-173">Nel riquadro **Personalizzare il tipo di contenuti da proteggere**, fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="f8c22-173">In the **Customize the type of content you want to protect** pane, click **Edit**.</span></span>
    
9. <span data-ttu-id="f8c22-174">Nel riquadro **Scegliere i tipi di contenuto da proteggere**,fare clic su **Aggiungi** nella casella di riepilogo a discesa, quindi fare clic su **Etichette di conservazione**.</span><span class="sxs-lookup"><span data-stu-id="f8c22-174">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Retention labels**.</span></span>
    
10. <span data-ttu-id="f8c22-175">Nel riquadro **Etichette di conservazione** fare clic su **Aggiungi**, selezionare l'etichetta **Riservato** fare clic su **Aggiungi**, quindi fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="f8c22-175">In the **Retention labels** pane, click **Add**, select the **Sensitive** label, click **Add**, and then click **Done**.</span></span>
    
11. <span data-ttu-id="f8c22-176">Nel riquadro **Choose the types of content to protect** (Scegli i tipi di contenuto da proteggere) fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f8c22-176">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="f8c22-177">Nel riquadro **Personalizzare i tipi di informazioni da proteggere**, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f8c22-177">In the **Customize the type of content you want to protect** pane, click **Next**.</span></span>

13. <span data-ttu-id="f8c22-178">Nel riquadro **What do you want to do if we detect sensitive info?** (Selezionare come procedere in caso di informazioni sensibili rilevate) fare clic su **Customize the tip and email** (Personalizza suggerimento e messaggio di posta elettronica).</span><span class="sxs-lookup"><span data-stu-id="f8c22-178">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="f8c22-179">Nel riquadro **Personalizza i suggerimenti per i criteri e le notifiche tramite posta elettronica** fare clic su **Personalizza il testo del suggerimento per i criteri**.</span><span class="sxs-lookup"><span data-stu-id="f8c22-179">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="f8c22-180">Nella casella di testo digitare o incollare uno dei suggerimenti riportati di seguito, a seconda se è stata implementato Azure Information Protection per proteggere i file estremamente riservati:</span><span class="sxs-lookup"><span data-stu-id="f8c22-180">In the text box, type or paste in one of the following tips, depending on if you implemented Azure Information Protection to protect highly confidential files:</span></span>
    
  - <span data-ttu-id="f8c22-p106">Per condividere con un utente esterno all'organizzazione, scaricare il file e quindi aprirlo. Fare clic su File, Proteggi documento, Crittografa con password, quindi specificare una password complessa. Inviare la password in un'e-mail separata o con altri mezzi di comunicazione.</span><span class="sxs-lookup"><span data-stu-id="f8c22-p106">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>
  - <span data-ttu-id="f8c22-p107">I file estremamente riservati sono protetti con crittografia. Solo gli utenti esterni che hanno ricevuto le autorizzazioni per questi file dal reparto IT possono leggerli.</span><span class="sxs-lookup"><span data-stu-id="f8c22-p107">Highly confidential files are protected with encryption. Only external users who are granted permissions to these files by your IT department can read them.</span></span>
    
    <span data-ttu-id="f8c22-186">In alternativa, digitare o incollare un suggerimento per i criteri che indica agli utenti come condividere un file all'esterno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f8c22-186">Alternately, type or paste in your own policy tip that instructs users on how to share a file outside your organization.</span></span>
    
16. <span data-ttu-id="f8c22-187">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="f8c22-187">Click **OK**.</span></span>
    
17. <span data-ttu-id="f8c22-188">Nel riquadro **Quale operazione eseguire se vengono rilevate informazioni riservate?**, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f8c22-188">In the **What do you want to do if we detect sensitive info?** pane, click **Next**.</span></span>
    
18. <span data-ttu-id="f8c22-189">Nel riquadro **Abilitare il criterio o eseguire prima un test?**, fare clic su **Sì, abilitarlo immediatamente**, quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f8c22-189">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="f8c22-190">Nel riquadro **Verifica le impostazioni** fare clic su **Crea** e quindi su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="f8c22-190">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
    
<span data-ttu-id="f8c22-191">Di seguito è riportata la configurazione risultante per i siti sensibili del team di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="f8c22-191">Here is your resulting configuration for sensitive SharePoint Online team sites.</span></span>
  
![Criteri di prevenzione della perdita dei dati per un sito del team di SharePoint Online isolato usando l'etichetta di conservazione Riservato](media/2ff4cc53-87a8-43e3-b637-3068d88409f3.png)
  
<span data-ttu-id="f8c22-193">Seguire questa procedura per configurare un criterio della prevenzione della perdita dei dati che blocchi gli utenti in fase di condivisione di un documento in un sito con riservatezza elevata del team di SharePoint Online all'esterno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f8c22-193">Next, use these steps to configure a DLP policy that blocks users when they share a document on a SharePoint Online highly confidential team site outside the organization.</span></span>
  
1. <span data-ttu-id="f8c22-194">Nella nuova scheda **Sicurezza Microsoft 365** del browser fare clic su **Criteri > Prevenzione della perdita dei dati**.</span><span class="sxs-lookup"><span data-stu-id="f8c22-194">On the new **Microsoft 365 compliance** tab in your browser, click **Policies > Data loss prevention**.</span></span>
    
2. <span data-ttu-id="f8c22-195">Nel riquadro **Prevenzione della perdita dei dati** fare clic su \*\* Crea un criterio\*\*.</span><span class="sxs-lookup"><span data-stu-id="f8c22-195">In the **Data loss prevention** pane, click **Create a policy**.</span></span>
    
3. <span data-ttu-id="f8c22-196">Nel riquadro **Inizia con un modello o crea un criterio personalizzato**, fare clic su **Personalizza**, quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f8c22-196">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
4. <span data-ttu-id="f8c22-197">Nel riquadro **Denomina il criterio**, digitare il nome per il criterio DLP di livello estremamente riservato in **Nome**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f8c22-197">In the **Name your policy** pane, type the name for the highly sensitive level DLP policy in **Name**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="f8c22-198">Nel riquadro **Choose locations** (Scegli posizioni) fare clic su **Let me choose specific locations** (Consenti di scegliere posizioni specifiche) e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f8c22-198">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="f8c22-199">Nell'elenco di località, disabilitare le località **Posta elettronica di Exchange**, **Account di OneDrive** e **Messaggi di chat e canali di Teams**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f8c22-199">In the list of locations, disable the **Exchange email**, **OneDrive accounts**, and **Teams chat and channel messages** locations, and then click **Next**.</span></span>
    
7. <span data-ttu-id="f8c22-200">Nel riquadro **Personalizzare i tipi di informazioni riservate da proteggere** fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="f8c22-200">In the **Customize the types of sensitive info you want to protect** pane, click **Edit**.</span></span>
    
8. <span data-ttu-id="f8c22-201">Nel riquadro **Scegliere i tipi di contenuto da proteggere**,fare clic su **Aggiungi** nella casella di riepilogo a discesa, quindi fare clic su **Etichette di conservazione**.</span><span class="sxs-lookup"><span data-stu-id="f8c22-201">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Retention labels**.</span></span>
    
9. <span data-ttu-id="f8c22-202">Nel riquadro **Etichette** fare clic su **Aggiungi**, selezionare l'etichetta **Estremamente riservato**, fare clic su **Aggiungi**, quindi fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="f8c22-202">In the **Retention labels** pane, click **Add**, select the **Highly Confidential** label, click **Add**, and then click **Done**.</span></span>
    
10. <span data-ttu-id="f8c22-203">Nel riquadro **Choose the types of content to protect** (Scegli i tipi di contenuto da proteggere) fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f8c22-203">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="f8c22-204">Nel riquadro **Customize the types of sensitive info you want to protect** (Personalizza i tipi di informazioni sensibili da proteggere) fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f8c22-204">In the **Customize the types of sensitive info you want to protect** pane, click **Next**.</span></span>
    
13. <span data-ttu-id="f8c22-205">Nel riquadro **What do you want to do if we detect sensitive info?** (Selezionare come procedere in caso di informazioni sensibili rilevate) fare clic su **Customize the tip and email** (Personalizza suggerimento e messaggio di posta elettronica).</span><span class="sxs-lookup"><span data-stu-id="f8c22-205">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="f8c22-206">Nel riquadro **Customize policy tips and email notifications** (Personalizza i suggerimenti per i criteri e le notifiche tramite posta elettronica) fare clic su **Customize the policy tip text** (Personalizza testo suggerimento per criterio).</span><span class="sxs-lookup"><span data-stu-id="f8c22-206">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="f8c22-207">Nella casella di testo digitare o incollare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="f8c22-207">In the text box, type or paste in the following:</span></span>
    
  - <span data-ttu-id="f8c22-p108">Per condividere con un utente esterno all'organizzazione, scaricare il file e quindi aprirlo. Fare clic su File, Proteggi documento, Crittografa con password, quindi specificare una password complessa. Inviare la password in un'e-mail separata o con altri mezzi di comunicazione.</span><span class="sxs-lookup"><span data-stu-id="f8c22-p108">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>
    
    <span data-ttu-id="f8c22-211">In alternativa, digitare o incollare un suggerimento per i criteri che indica agli utenti come condividere un file all'esterno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f8c22-211">Alternately, type or paste in your own policy tip that instructs users on how to share a file outside your organization.</span></span>
    
16. <span data-ttu-id="f8c22-212">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="f8c22-212">Click **OK**.</span></span>
    
17. <span data-ttu-id="f8c22-213">Nel riquadro **Quale operazione eseguire se vengono rilevate informazioni riservate?** fare clic su **Limita l'accesso o crittografa i contenuti** in **Rileva se viene condivisa una specifica quantità di informazioni sensibili nello stesso momento** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f8c22-213">In the **What do you want to do if we detect sensitive info?** pane, under **Detect when a specific amount of sensitive info is being shared at one time**, click **Restrict access or encrypt the content**, and then click **Next**.</span></span>
    
18. <span data-ttu-id="f8c22-214">Nel riquadro **Abilitare il criterio o eseguire prima un test?**, fare clic su **Sì, abilitarlo immediatamente**, quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f8c22-214">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="f8c22-215">Nel riquadro **Verifica le impostazioni** fare clic su **Crea** e quindi su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="f8c22-215">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
    
<span data-ttu-id="f8c22-216">Di seguito è riportata la configurazione risultante per i siti con riservatezza elevata del team di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="f8c22-216">Here is your resulting configuration for high confidentiality SharePoint Online team sites.</span></span>
  
![Criteri di prevenzione della perdita dei dati per un sito del team di SharePoint Online isolato usando l'etichetta di conservazione Riservatezza elevata](media/f705d3d0-23c9-4333-8b70-ad3b91f835ea.png)
  
## <a name="next-step"></a><span data-ttu-id="f8c22-218">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="f8c22-218">Next step</span></span>

[<span data-ttu-id="f8c22-219">Proteggere i file di SharePoint Online con Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="f8c22-219">Protect SharePoint Online files with Azure Information Protection</span></span>](protect-sharepoint-online-files-with-azure-information-protection.md)
    
## <a name="see-also"></a><span data-ttu-id="f8c22-220">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f8c22-220">See Also</span></span>

[<span data-ttu-id="f8c22-221">Protezione di file e siti di SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f8c22-221">Secure SharePoint Online sites and files</span></span>](../security/office-365-security/secure-sharepoint-online-sites-and-files.md)
  
[<span data-ttu-id="f8c22-222">Guida sulla sicurezza Microsoft per organizzazioni che si occupano della campagna politica, no profit e altre organizzazioni Agile</span><span class="sxs-lookup"><span data-stu-id="f8c22-222">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](../security/office-365-security/microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
  
[<span data-ttu-id="f8c22-223">Adozione del cloud e soluzioni ibride</span><span class="sxs-lookup"><span data-stu-id="f8c22-223">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)


