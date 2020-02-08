---
title: Proteggere i file di SharePoint Online con le etichette di conservazione e la prevenzione della perdita dei dati
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/27/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- SPO_Content
ms.custom:
- Ent_Solutions
ms.assetid: c9f837af-8d71-4df1-a285-dedb1c5618b3
description: 'Sintesi: applicare etichette di conservazione e criteri di prevenzione della perdita dei dati ai siti del team di SharePoint Online con vari livelli di protezione delle informazioni.'
ms.openlocfilehash: ad333007b2efdcf577f1c31afc716c525a7abf7e
ms.sourcegitcommit: a53ec6ab7bf59983780ea7187cd5d56b8b1f4b33
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/07/2020
ms.locfileid: "41855375"
---
# <a name="protect-sharepoint-online-files-with-retention-labels-and-dlp"></a><span data-ttu-id="cff18-103">Proteggere i file di SharePoint Online con le etichette di conservazione e la prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="cff18-103">Protect SharePoint Online files with retention labels and DLP</span></span>

<span data-ttu-id="cff18-104">Usare i passaggi descritti in questo articolo per progettare e implementare le etichette di conservazione e i criteri di protezione della perdita dei dati (DLP) per i siti del team di SharePoint Online di base, riservati ed estremamente riservati.</span><span class="sxs-lookup"><span data-stu-id="cff18-104">Use the steps in this article to design and deploy retention labels and DLP policies for baseline, sensitive, and highly confidential SharePoint Online team sites.</span></span> <span data-ttu-id="cff18-105">Per altre informazioni su questi tre livelli di protezione, vedere [Proteggere siti e file di SharePoint Online](../security/office-365-security/secure-sharepoint-online-sites-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="cff18-105">For more information about these three tiers of protection, see [Secure SharePoint Online sites and files](../security/office-365-security/secure-sharepoint-online-sites-and-files.md).</span></span>
  
## <a name="how-this-works"></a><span data-ttu-id="cff18-106">Funzionamento</span><span class="sxs-lookup"><span data-stu-id="cff18-106">How this works</span></span>

1. <span data-ttu-id="cff18-107">Creare le etichette di conservazione desiderate e pubblicarle.</span><span class="sxs-lookup"><span data-stu-id="cff18-107">Create the desired retention labels and publish these.</span></span> <span data-ttu-id="cff18-108">La pubblicazione può richiedere fino a 12 ore.</span><span class="sxs-lookup"><span data-stu-id="cff18-108">It can take up to 12 hours for these to be published.</span></span>
2. <span data-ttu-id="cff18-109">Per i siti di SharePoint desiderati, modificare le impostazioni della raccolta documenti per applicare le etichette di conservazione desiderate agli elementi della raccolta.</span><span class="sxs-lookup"><span data-stu-id="cff18-109">For the desired SharePoint sites, edit the document library settings to apply the desired retention labels to items in the library.</span></span>
3. <span data-ttu-id="cff18-110">Creare criteri di prevenzione della perdita dei dati per intervenire in base alle etichette di conservazione.</span><span class="sxs-lookup"><span data-stu-id="cff18-110">Create DLP policies to take action based on the retention labels.</span></span>

<span data-ttu-id="cff18-111">Quando gli utenti aggiungono un documento alla raccolta, il documento riceve per impostazione predefinita l'etichetta di conservazione assegnata.</span><span class="sxs-lookup"><span data-stu-id="cff18-111">When users add a document to the library, the document will receive the assigned retention label by default.</span></span> <span data-ttu-id="cff18-112">È possibile modificare l'etichetta, se necessario.</span><span class="sxs-lookup"><span data-stu-id="cff18-112">Users can change the label, if needed.</span></span> <span data-ttu-id="cff18-113">Quando un utente condivide un documento all'esterno dell'organizzazione, i criteri di prevenzione della perdita dei dati verificano se è assegnata un'etichetta e intervengono in caso di corrispondenza all'etichetta.</span><span class="sxs-lookup"><span data-stu-id="cff18-113">When a user shares a document outside the organization, DLP will check to see if a label is assigned and take action if a DLP policy matches the label.</span></span> <span data-ttu-id="cff18-114">Quindi cercano la corrispondenza anche ad altri criteri, ad esempio la protezione dei file con i numeri di carta di credito, se questo tipo di criterio è configurato.</span><span class="sxs-lookup"><span data-stu-id="cff18-114">DLP will look for other policy matches as well, such as protecting files with credit card numbers if this type of policy is configured.</span></span> 

## <a name="retention-labels-for-your-sharepoint-online-sites"></a><span data-ttu-id="cff18-115">Etichette di conservazione per i siti di SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="cff18-115">Retention labels for your SharePoint Online sites</span></span>

<span data-ttu-id="cff18-116">La procedura per creare e poi assegnare etichette di conservazione ai siti del team di SharePoint Online prevede tre fasi.</span><span class="sxs-lookup"><span data-stu-id="cff18-116">There are three phases to creating and then assigning retention labels to SharePoint Online team sites.</span></span>
  
### <a name="phase-1-determine-the-retention-label-names"></a><span data-ttu-id="cff18-117">Fase 1: Definire i nomi delle etichette di conservazione</span><span class="sxs-lookup"><span data-stu-id="cff18-117">Phase 1: Determine the retention label names</span></span>

<span data-ttu-id="cff18-118">In questa fase si definiscono i nomi delle etichette di conservazione per i quattro livelli di protezione delle informazioni applicati ai siti del team di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="cff18-118">In this phase, you determine the names of your retention labels for the four levels of information protection applied to SharePoint Online team sites.</span></span> <span data-ttu-id="cff18-119">La tabella seguente elenca i nomi consigliati per ogni livello.</span><span class="sxs-lookup"><span data-stu-id="cff18-119">The following table lists the recommended names for each level.</span></span>
  
|<span data-ttu-id="cff18-120">**Livello di protezione del sito del team di SharePoint Online**</span><span class="sxs-lookup"><span data-stu-id="cff18-120">**SharePoint Online team site protection level**</span></span>|<span data-ttu-id="cff18-121">**Nome etichetta**</span><span class="sxs-lookup"><span data-stu-id="cff18-121">**Label name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="cff18-122">Pubblico di base</span><span class="sxs-lookup"><span data-stu-id="cff18-122">Baseline-Public</span></span>  <br/> |<span data-ttu-id="cff18-123">Pubblico interno</span><span class="sxs-lookup"><span data-stu-id="cff18-123">Internal public</span></span>  <br/> |
|<span data-ttu-id="cff18-124">Privato di base</span><span class="sxs-lookup"><span data-stu-id="cff18-124">Baseline-Private</span></span>  <br/> |<span data-ttu-id="cff18-125">Private</span><span class="sxs-lookup"><span data-stu-id="cff18-125">Private</span></span>  <br/> |
|<span data-ttu-id="cff18-126">Dati sensibili</span><span class="sxs-lookup"><span data-stu-id="cff18-126">Sensitive</span></span>  <br/> |<span data-ttu-id="cff18-127">Dati sensibili</span><span class="sxs-lookup"><span data-stu-id="cff18-127">Sensitive</span></span>  <br/> |
|<span data-ttu-id="cff18-128">Highly Confidential (Riservatezza elevata)</span><span class="sxs-lookup"><span data-stu-id="cff18-128">Highly Confidential</span></span>  <br/> |<span data-ttu-id="cff18-129">Highly Confidential (Riservatezza elevata)</span><span class="sxs-lookup"><span data-stu-id="cff18-129">Highly Confidential</span></span>  <br/> |
   
### <a name="phase-2-create-the-retention-labels"></a><span data-ttu-id="cff18-130">Fase 2: Creare le etichette di conservazione</span><span class="sxs-lookup"><span data-stu-id="cff18-130">Phase 2: Create the retention labels</span></span>

<span data-ttu-id="cff18-131">In questa fase si creano e poi pubblicano le etichette specificate per i diversi livelli di protezione delle informazioni.</span><span class="sxs-lookup"><span data-stu-id="cff18-131">In this phase, you create and then publish your determined labels for the different levels of information protection.</span></span>
  
1. <span data-ttu-id="cff18-132">Accedere al [portale Conformità Microsoft 365](https://compliance.microsoft.com) con un account che dispone del ruolo Amministratore della sicurezza oppure Amministratore della società.</span><span class="sxs-lookup"><span data-stu-id="cff18-132">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com) with an account that has the Security Administrator or Company Administrator role.</span></span>
    
2. <span data-ttu-id="cff18-133">Dalla scheda **Home: Conformità Microsoft 365** del browser fare clic su **Classificazioni > Etichette**.</span><span class="sxs-lookup"><span data-stu-id="cff18-133">From the **Home - Microsoft 365 compliance** tab of your browser, click **Classifications > Labels**.</span></span>
    
3. <span data-ttu-id="cff18-134">Fare clic su **Etichette di conservazione > Crea un'etichetta**.</span><span class="sxs-lookup"><span data-stu-id="cff18-134">Click **Retention labels > Create a label**.</span></span>
    
4. <span data-ttu-id="cff18-135">Nel riquadro **Assegnare un nome all'etichetta** digitare il nome dell’etichetta e una descrizione per amministratori e utenti, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="cff18-135">On the **Name your label** pane, type the name of the label and a description for admins and users, and then click **Next**.</span></span>

5. <span data-ttu-id="cff18-136">Nel riquadro **Descrittori del piano di archiviazione** compilare come necessario e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="cff18-136">On the **File plan descriptors** pane, fill in as needed, and then click **Next**.</span></span>
    
6. <span data-ttu-id="cff18-137">Nel riquadro **Impostazioni etichetta** impostare **Conservazione** su **Sì**, se necessario, e configurare le impostazioni di conservazione.</span><span class="sxs-lookup"><span data-stu-id="cff18-137">On the **Label settings** pane, if needed, set **Retention** to **On** and configure retention settings.</span></span> <span data-ttu-id="cff18-138">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="cff18-138">Click **Next**.</span></span>
    
7. <span data-ttu-id="cff18-139">Nel riquadro **Rivedere le impostazioni** fare clic su **Crea etichetta**.</span><span class="sxs-lookup"><span data-stu-id="cff18-139">On the **Review your settings** pane, click **Create the label**.</span></span>
    
8. <span data-ttu-id="cff18-140">Per etichette aggiuntive, fare clic su **Crea un'etichetta** e ripetere i passaggi da 3 a 7 in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="cff18-140">For your additional labels, click **Create a label**, and then repeat steps 3-7 as needed.</span></span>
    

### <a name="publish-your-new-labels"></a><span data-ttu-id="cff18-141">Pubblicare le nuove etichette</span><span class="sxs-lookup"><span data-stu-id="cff18-141">Publish your new labels</span></span>

<span data-ttu-id="cff18-142">Successivamente, seguire questa procedura per pubblicare le nuove etichette di conservazione.</span><span class="sxs-lookup"><span data-stu-id="cff18-142">Next, use these steps to publish the new retention labels.</span></span>
  
1. <span data-ttu-id="cff18-143">Nel riquadro **Etichette** fare clic sulla scheda **Etichette di conservazione** e quindi su **Pubblica etichette**.</span><span class="sxs-lookup"><span data-stu-id="cff18-143">From the **Labels** pane, click the **Retention labels** tab, and then click **Publish labels**.</span></span>
    
2. <span data-ttu-id="cff18-144">Nel riquadro **Scegliere le etichette da pubblicare** fare clic su **Scegliere le etichette da pubblicare**.</span><span class="sxs-lookup"><span data-stu-id="cff18-144">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
3. <span data-ttu-id="cff18-145">Nel riquadro **Scegli etichette** fare clic su **Aggiungi**, selezionare le quattro etichette e fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="cff18-145">On the **Choose labels** pane, click **Add**, select all four labels, click **Add**.</span></span>
    
4. <span data-ttu-id="cff18-146">Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="cff18-146">Click **Done**.</span></span>
    
5. <span data-ttu-id="cff18-147">Nel riquadro **Choose labels to publish** (Scegli etichette da pubblicare) fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="cff18-147">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
6. <span data-ttu-id="cff18-148">Nel riquadro **Choose locations** (Scegli posizioni) fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="cff18-148">On the **Choose locations** pane, click **Next**.</span></span>
    
7. <span data-ttu-id="cff18-149">Nel riquadro **Denomina il criterio**, digitare un nome per il set di etichette in **Nome**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="cff18-149">On the **Name your policy** pane, type a name for your set of labels in **Name**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="cff18-150">Nel riquadro **Verifica le impostazioni** fare clic su **Publish labels** (Pubblica etichette), quindi fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="cff18-150">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>

    
### <a name="phase-3-apply-the-retention-labels-to-your-sharepoint-online-sites"></a><span data-ttu-id="cff18-151">Fase 3: applicare le etichette di conservazione ai siti di SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="cff18-151">Phase 3: Apply the retention labels to your SharePoint Online sites</span></span>

<span data-ttu-id="cff18-152">Seguire questa procedura per applicare le etichette di conservazione alle cartelle di documenti dei siti del team di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="cff18-152">Use these steps to apply the retention labels to the documents folders of your SharePoint Online team sites.</span></span>
  
1. <span data-ttu-id="cff18-153">Accedere al [portale di Office 365](https://www.office.com) e fare clic sull'app **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="cff18-153">Sign in to the [Office 365 portal](https://www.office.com), click the **SharePoint** app.</span></span>
    
2. <span data-ttu-id="cff18-154">Nella nuova scheda **SharePoint** del browser selezionare un sito per cui è necessario assegnare un'etichetta di conservazione.</span><span class="sxs-lookup"><span data-stu-id="cff18-154">On the new **SharePoint** tab in your browser, click a site that needs a retention label assigned.</span></span>
    
3. <span data-ttu-id="cff18-155">Nella nuova scheda del sito di SharePoint del browser fare clic su **Documenti**.</span><span class="sxs-lookup"><span data-stu-id="cff18-155">In the new SharePoint site tab of your browser, click **Documents**.</span></span>
    
4. <span data-ttu-id="cff18-156">Fare clic sull'icona delle impostazioni e selezionare **Impostazioni libreria**.</span><span class="sxs-lookup"><span data-stu-id="cff18-156">Click the settings icon, and then click **Library settings**.</span></span>
    
5. <span data-ttu-id="cff18-157">In **Autorizzazioni e gestione** fare clic su **Apply label to items in this library** (Applica etichetta agli elementi in questa libreria).</span><span class="sxs-lookup"><span data-stu-id="cff18-157">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
6. <span data-ttu-id="cff18-158">In **Impostazioni - Applica etichetta**, selezionare l'etichetta di conservazione appropriata, quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="cff18-158">In **Settings-Apply Label**, select the appropriate retention label, and then click **Save**.</span></span>
    
7. <span data-ttu-id="cff18-159">Chiudere la scheda per il sito di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="cff18-159">Close the tab for the SharePoint Online site.</span></span>
    
8. <span data-ttu-id="cff18-160">Ripetere i passaggi da 2 a 8 per assegnare le etichette di conservazione a siti di SharePoint Online aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="cff18-160">Repeat steps 2-8 to assign retention labels to your additional SharePoint Online sites.</span></span>
    
<span data-ttu-id="cff18-161">Questa è la configurazione risultante.</span><span class="sxs-lookup"><span data-stu-id="cff18-161">Here is your resulting configuration.</span></span>
  
![Etichette di conservazione per i quattro tipi di siti del team di SharePoint Online.](media/e0a4fdd2-1c30-4d93-8af4-a6f0c6c29966.png)
  
## <a name="dlp-policies-for-your-sharepoint-online-sites"></a><span data-ttu-id="cff18-163">Criteri di prevenzione della perdita dei dati per siti di SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="cff18-163">DLP policies for your SharePoint Online sites</span></span>

<span data-ttu-id="cff18-164">Seguire questa procedura per configurare un criterio della prevenzione della perdita dei dati che notifica agli utenti la condivisione di un documento in un sito sensibile del team di SharePoint Online all'esterno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="cff18-164">Use these steps to configure a DLP policy that notifies users when they share a document on a SharePoint Online sensitive team site outside the organization.</span></span>

1. <span data-ttu-id="cff18-165">Accedere al [portale Conformità Microsoft 365](https://compliance.microsoft.com/) con un account che dispone del ruolo Amministratore della sicurezza oppure Amministratore della società.</span><span class="sxs-lookup"><span data-stu-id="cff18-165">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com/) with an account that has the Security Administrator or Company Administrator role.</span></span>
    
2. <span data-ttu-id="cff18-166">Nella nuova scheda **Sicurezza Microsoft 365** del browser fare clic su **Criteri > Prevenzione della perdita dei dati**.</span><span class="sxs-lookup"><span data-stu-id="cff18-166">On the new **Microsoft 365 compliance** tab in your browser, click **Policies > Data loss prevention**.</span></span>
    
3. <span data-ttu-id="cff18-167">Nel riquadro **Home > Prevenzione della perdita dei dati** fare clic su **Crea un criterio**.</span><span class="sxs-lookup"><span data-stu-id="cff18-167">In the **Home > Data loss prevention** pane, click **Create a policy**.</span></span>
    
4. <span data-ttu-id="cff18-168">Nel riquadro **Iniziare con un modello o creare un criterio personalizzato** fare clic su **Personalizza**, quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="cff18-168">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="cff18-169">Nel riquadro **Denomina il criterio**, digitare il nome per il criterio DLP di livello riservato in **Nome**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="cff18-169">In the **Name your policy** pane, type the name for the sensitive level DLP policy in **Name**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="cff18-170">Nel riquadro **Scegli posizioni** fare clic su **Consenti di scegliere posizioni specifiche** e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="cff18-170">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="cff18-171">Nell'elenco di località, disabilitare le località **Posta elettronica di Exchange**, **Account di OneDrive** e **Messaggi di chat e canali di Teams**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="cff18-171">In the list of locations, disable the **Exchange email**, **OneDrive accounts**, and **Teams chat and channel messages** locations, and then click **Next**.</span></span>
    
8. <span data-ttu-id="cff18-172">Nel riquadro **Personalizzare il tipo di contenuti da proteggere**, fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="cff18-172">In the **Customize the type of content you want to protect** pane, click **Edit**.</span></span>
    
9. <span data-ttu-id="cff18-173">Nel riquadro **Scegliere i tipi di contenuto da proteggere**,fare clic su **Aggiungi** nella casella di riepilogo a discesa, quindi fare clic su **Etichette di conservazione**.</span><span class="sxs-lookup"><span data-stu-id="cff18-173">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Retention labels**.</span></span>
    
10. <span data-ttu-id="cff18-174">Nel riquadro **Etichette di conservazione** fare clic su **Aggiungi**, selezionare l'etichetta **Riservato** fare clic su **Aggiungi**, quindi fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="cff18-174">In the **Retention labels** pane, click **Add**, select the **Sensitive** label, click **Add**, and then click **Done**.</span></span>
    
11. <span data-ttu-id="cff18-175">Nel riquadro **Choose the types of content to protect** (Scegli i tipi di contenuto da proteggere) fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="cff18-175">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="cff18-176">Nel riquadro **Personalizzare i tipi di informazioni da proteggere**, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="cff18-176">In the **Customize the type of content you want to protect** pane, click **Next**.</span></span>

13. <span data-ttu-id="cff18-177">Nel riquadro **What do you want to do if we detect sensitive info?** (Selezionare come procedere in caso di informazioni sensibili rilevate) fare clic su **Customize the tip and email** (Personalizza suggerimento e messaggio di posta elettronica).</span><span class="sxs-lookup"><span data-stu-id="cff18-177">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="cff18-178">Nel riquadro **Customize policy tips and email notifications** (Personalizza i suggerimenti per i criteri e le notifiche tramite posta elettronica) fare clic su **Customize the policy tip text** (Personalizza testo suggerimento per criterio).</span><span class="sxs-lookup"><span data-stu-id="cff18-178">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="cff18-179">Nella casella di testo digitare o incollare uno dei suggerimenti riportati di seguito, a seconda dell'uso facoltativo delle etichette di riservatezza per proteggere i file sensibili:</span><span class="sxs-lookup"><span data-stu-id="cff18-179">In the text box, type or paste in one of the following tips, depending on if you are optionallyusing sensitivity labels to protect sensitive files:</span></span>
    
  - <span data-ttu-id="cff18-p106">Per condividere con un utente esterno all'organizzazione, scaricare il file e quindi aprirlo. Fare clic su File, Proteggi documento, Crittografa con password, quindi specificare una password complessa. Inviare la password in un'e-mail separata o con altri mezzi di comunicazione.</span><span class="sxs-lookup"><span data-stu-id="cff18-p106">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>
  - <span data-ttu-id="cff18-p107">I file estremamente riservati sono protetti con crittografia. Solo gli utenti esterni che hanno ricevuto le autorizzazioni per questi file dal reparto IT possono leggerli.</span><span class="sxs-lookup"><span data-stu-id="cff18-p107">Highly confidential files are protected with encryption. Only external users who are granted permissions to these files by your IT department can read them.</span></span>
    
    <span data-ttu-id="cff18-185">In alternativa, digitare o incollare un suggerimento per i criteri che indica agli utenti come condividere un file all'esterno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="cff18-185">Alternately, type or paste in your own policy tip that instructs users on how to share a file outside your organization.</span></span>
    
16. <span data-ttu-id="cff18-186">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="cff18-186">Click **OK**.</span></span>
    
17. <span data-ttu-id="cff18-187">Nel riquadro **Quale operazione eseguire se vengono rilevate informazioni riservate?**, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="cff18-187">In the **What do you want to do if we detect sensitive info?** pane, click **Next**.</span></span>
    
18. <span data-ttu-id="cff18-188">Nel riquadro **Abilitare il criterio o eseguire prima un test?**, fare clic su **Sì, abilitarlo immediatamente**, quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="cff18-188">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="cff18-189">Nel riquadro **Verifica le impostazioni** fare clic su **Crea** e quindi su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="cff18-189">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
    
<span data-ttu-id="cff18-190">Di seguito è riportata la configurazione risultante per i siti sensibili del team di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="cff18-190">Here is your resulting configuration for sensitive SharePoint Online team sites.</span></span>
  
![Criteri di prevenzione della perdita dei dati per un sito del team di SharePoint Online isolato usando l'etichetta di conservazione Riservato](media/2ff4cc53-87a8-43e3-b637-3068d88409f3.png)
  
<span data-ttu-id="cff18-192">Seguire questa procedura per configurare un criterio della prevenzione della perdita dei dati che blocchi gli utenti in fase di condivisione di un documento in un sito con riservatezza elevata del team di SharePoint Online all'esterno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="cff18-192">Next, use these steps to configure a DLP policy that blocks users when they share a document on a SharePoint Online highly confidential team site outside the organization.</span></span>
  
1. <span data-ttu-id="cff18-193">Nella nuova scheda **Sicurezza Microsoft 365** del browser fare clic su **Criteri > Prevenzione della perdita dei dati**.</span><span class="sxs-lookup"><span data-stu-id="cff18-193">On the new **Microsoft 365 compliance** tab in your browser, click **Policies > Data loss prevention**.</span></span>
    
2. <span data-ttu-id="cff18-194">Nel riquadro **Prevenzione della perdita dei dati** fare clic su \*\* Crea un criterio\*\*.</span><span class="sxs-lookup"><span data-stu-id="cff18-194">In the **Data loss prevention** pane, click **Create a policy**.</span></span>
    
3. <span data-ttu-id="cff18-195">Nel riquadro **Inizia con un modello o crea un criterio personalizzato**, fare clic su **Personalizza**, quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="cff18-195">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
4. <span data-ttu-id="cff18-196">Nel riquadro **Denomina il criterio**, digitare il nome per il criterio DLP di livello estremamente riservato in **Nome**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="cff18-196">In the **Name your policy** pane, type the name for the highly sensitive level DLP policy in **Name**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="cff18-197">Nel riquadro **Choose locations** (Scegli posizioni) fare clic su **Let me choose specific locations** (Consenti di scegliere posizioni specifiche) e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="cff18-197">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="cff18-198">Nell'elenco di località, disabilitare le località **Posta elettronica di Exchange**, **Account di OneDrive** e **Messaggi di chat e canali di Teams**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="cff18-198">In the list of locations, disable the **Exchange email**, **OneDrive accounts**, and **Teams chat and channel messages** locations, and then click **Next**.</span></span>
    
7. <span data-ttu-id="cff18-199">Nel riquadro **Personalizzare i tipi di informazioni riservate da proteggere** fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="cff18-199">In the **Customize the types of sensitive info you want to protect** pane, click **Edit**.</span></span>
    
8. <span data-ttu-id="cff18-200">Nel riquadro **Scegliere i tipi di contenuto da proteggere**,fare clic su **Aggiungi** nella casella di riepilogo a discesa, quindi fare clic su **Etichette di conservazione**.</span><span class="sxs-lookup"><span data-stu-id="cff18-200">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Retention labels**.</span></span>
    
9. <span data-ttu-id="cff18-201">Nel riquadro **Etichette** fare clic su **Aggiungi**, selezionare l'etichetta **Estremamente riservato**, fare clic su **Aggiungi**, quindi fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="cff18-201">In the **Retention labels** pane, click **Add**, select the **Highly Confidential** label, click **Add**, and then click **Done**.</span></span>
    
10. <span data-ttu-id="cff18-202">Nel riquadro **Choose the types of content to protect** (Scegli i tipi di contenuto da proteggere) fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="cff18-202">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="cff18-203">Nel riquadro **Customize the types of sensitive info you want to protect** (Personalizza i tipi di informazioni sensibili da proteggere) fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="cff18-203">In the **Customize the types of sensitive info you want to protect** pane, click **Next**.</span></span>
    
13. <span data-ttu-id="cff18-204">Nel riquadro **What do you want to do if we detect sensitive info?** (Selezionare come procedere in caso di informazioni sensibili rilevate) fare clic su **Customize the tip and email** (Personalizza suggerimento e messaggio di posta elettronica).</span><span class="sxs-lookup"><span data-stu-id="cff18-204">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="cff18-205">Nel riquadro **Customize policy tips and email notifications** (Personalizza i suggerimenti per i criteri e le notifiche tramite posta elettronica) fare clic su **Customize the policy tip text** (Personalizza testo suggerimento per criterio).</span><span class="sxs-lookup"><span data-stu-id="cff18-205">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="cff18-206">Nella casella di testo digitare o incollare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="cff18-206">In the text box, type or paste in the following:</span></span>
    
  - <span data-ttu-id="cff18-p108">Per condividere con un utente esterno all'organizzazione, scaricare il file e quindi aprirlo. Fare clic su File, Proteggi documento, Crittografa con password, quindi specificare una password complessa. Inviare la password in un'e-mail separata o con altri mezzi di comunicazione.</span><span class="sxs-lookup"><span data-stu-id="cff18-p108">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>
    
    <span data-ttu-id="cff18-210">In alternativa, digitare o incollare un suggerimento per i criteri che indica agli utenti come condividere un file all'esterno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="cff18-210">Alternately, type or paste in your own policy tip that instructs users on how to share a file outside your organization.</span></span>
    
16. <span data-ttu-id="cff18-211">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="cff18-211">Click **OK**.</span></span>
    
17. <span data-ttu-id="cff18-212">Nel riquadro **Quale operazione eseguire se vengono rilevate informazioni riservate?** fare clic su **Limita l'accesso o crittografa i contenuti** in **Rileva se viene condivisa una specifica quantità di informazioni sensibili nello stesso momento** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="cff18-212">In the **What do you want to do if we detect sensitive info?** pane, under **Detect when a specific amount of sensitive info is being shared at one time**, click **Restrict access or encrypt the content**, and then click **Next**.</span></span>
    
18. <span data-ttu-id="cff18-213">Nel riquadro **Abilitare il criterio o eseguire prima un test?**, fare clic su **Sì, abilitarlo immediatamente**, quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="cff18-213">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="cff18-214">Nel riquadro **Verifica le impostazioni** fare clic su **Crea** e quindi su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="cff18-214">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
    
<span data-ttu-id="cff18-215">Di seguito è riportata la configurazione risultante per i siti con riservatezza elevata del team di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="cff18-215">Here is your resulting configuration for high confidentiality SharePoint Online team sites.</span></span>
  
![Criteri di prevenzione della perdita dei dati per un sito del team di SharePoint Online isolato usando l'etichetta di conservazione Riservatezza elevata](media/f705d3d0-23c9-4333-8b70-ad3b91f835ea.png)
  
## <a name="next-step"></a><span data-ttu-id="cff18-217">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="cff18-217">Next step</span></span>

[<span data-ttu-id="cff18-218">Proteggere i file di SharePoint Online con le etichette di riservatezza</span><span class="sxs-lookup"><span data-stu-id="cff18-218">Protect SharePoint Online files with sensitivity labels</span></span>](protect-sharepoint-online-files-with-sensitivity-label.md)
    
## <a name="see-also"></a><span data-ttu-id="cff18-219">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cff18-219">See Also</span></span>

[<span data-ttu-id="cff18-220">Guida sulla sicurezza Microsoft per organizzazioni che si occupano della campagna politica, no profit e altre organizzazioni agili</span><span class="sxs-lookup"><span data-stu-id="cff18-220">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](../security/office-365-security/microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
  
[<span data-ttu-id="cff18-221">Adozione del cloud e soluzioni ibride</span><span class="sxs-lookup"><span data-stu-id="cff18-221">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)


