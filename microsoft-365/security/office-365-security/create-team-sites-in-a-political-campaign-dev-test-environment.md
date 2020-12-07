---
title: Creare siti del team - Ambiente di sviluppo per la campagna politica
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/21/2018
audience: ITPro
ms.topic: article
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.custom: seo-marvel-apr2020
ms.assetid: c2112ce8-1c4b-424f-b200-59e161db2d21
description: 'Sintesi: creare siti del team di SharePoint Online pubblici, privati, riservati ed estremamente riservati nel proprio ambiente di sviluppo/testinging per la campagna politica.'
ms.openlocfilehash: d6fe2067e51e47fed4bd90e1a1fa6c898034a6d7
ms.sourcegitcommit: 4debeb8f0fce67f361676340fc390f1b283a3069
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/03/2020
ms.locfileid: "49561202"
---
# <a name="create-team-sites-in-a-political-campaign-devtest-environment"></a><span data-ttu-id="a019a-103">Creare siti del team in un ambiente di sviluppo/testinging per la campagna politica</span><span class="sxs-lookup"><span data-stu-id="a019a-103">Create team sites in a political campaign dev/test environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


 <span data-ttu-id="a019a-104">**Sintesi**: creare siti del team di SharePoint Online pubblici, privati, riservati ed estremamente riservati nel proprio ambiente di sviluppo/testinging per la campagna politica.</span><span class="sxs-lookup"><span data-stu-id="a019a-104">**Summary:** Create public, private, sensitive, and highly confidential SharePoint Online team sites in your political campaign dev/test environment.</span></span> 
  
<span data-ttu-id="a019a-p101">Attenersi alle istruzioni in questo articolo per creare un ambiente di sviluppo/testing che include i quattro tipi di siti del team di SharePoint Online per la soluzione [Guida sulla sicurezza Microsoft per organizzazioni che si occupano della campagna politica, no profit e altre organizzazioni Agile](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md). I siti sono descritti nel dettaglio nell'Argomento 10, **SharePoint e OneDrive for Business**.</span><span class="sxs-lookup"><span data-stu-id="a019a-p101">Use the instructions in this article to create a dev/test environment that includes the four different types of SharePoint Online team sites for the [Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md) solution. These sites are described in detail on Topic 10, titled **SharePoint and OneDrive for Business**.</span></span>
  
## <a name="phase-1-create-your-political-campaign-devtest-environment"></a><span data-ttu-id="a019a-107">Fase 1: creare l'ambiente di sviluppo/testing per la campagna politica</span><span class="sxs-lookup"><span data-stu-id="a019a-107">Phase 1: Create your political campaign dev/test environment</span></span>

<span data-ttu-id="a019a-108">Prima di tutto, seguire le istruzioni in [Configurazione di gruppi e utenti in un ambiente di sviluppo/testing per le campagne politiche](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md) per creare le sottoscrizioni, gli utenti e i gruppi.</span><span class="sxs-lookup"><span data-stu-id="a019a-108">First, follow the instructions in [Configure groups and users for a political campaign dev/test environment](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md) to create your subscriptions, users, and groups.</span></span>
  
## <a name="phase-2-create-labels"></a><span data-ttu-id="a019a-109">Fase 2: creare etichette</span><span class="sxs-lookup"><span data-stu-id="a019a-109">Phase 2: Create labels</span></span>

<span data-ttu-id="a019a-110">In questa fase, vengono create le etichette per i diversi livelli di sicurezza per cartelle di documenti dei siti del team di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="a019a-110">In this phase, you create the labels for the different levels of security for SharePoint Online team site document folders.</span></span>
  
1. <span data-ttu-id="a019a-111">Se necessario, accedere all'interfaccia di amministrazione con le credenziali dell'account amministratore globale della sottoscrizione di valutazione.</span><span class="sxs-lookup"><span data-stu-id="a019a-111">If needed, sign in to the admin center with the credentials of the global administrator account of your trial subscription.</span></span> <span data-ttu-id="a019a-112">Per informazioni, vedere [Dove accedere a Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="a019a-112">For help, see [Where to sign in to Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="a019a-113">Dalla scheda **Microsoft Office Home** fare clic sul riquadro **Amministratore**.</span><span class="sxs-lookup"><span data-stu-id="a019a-113">From the **Microsoft Office Home** tab, click the **Admin** tile.</span></span>
    
3. <span data-ttu-id="a019a-114">Dalla nuova scheda **Interfaccia di amministrazione di Microsoft 365** del browser fare clic su **Interfacce di amministrazione > Sicurezza e conformità**.</span><span class="sxs-lookup"><span data-stu-id="a019a-114">From the new **Microsoft 365 admin center** tab of your browser, click **Admin centers > Security & Compliance**.</span></span>
    
4. <span data-ttu-id="a019a-115">Dalla nuova scheda **Home: Sicurezza e conformità** del browser, fare clic su **Classificazioni > Etichette**.</span><span class="sxs-lookup"><span data-stu-id="a019a-115">From the new **Home - Security & Compliance** tab of your browser, click **Classifications > Labels**.</span></span>
    
5. <span data-ttu-id="a019a-116">Dal riquadro **Home > Etichette**, fare clic su **Crea un’etichetta**.</span><span class="sxs-lookup"><span data-stu-id="a019a-116">From the **Home > Labels** pane, click **Create a label**.</span></span>
    
6. <span data-ttu-id="a019a-117">Nel riquadro **Denomina l'etichetta**, digitare **Interno** e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a019a-117">On the **Name your label** pane, type **Internal**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="a019a-118">Nel riquadro **Label settings** (Importazioni etichetta) fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a019a-118">On the **Label settings** pane, click **Next**.</span></span>
    
8. <span data-ttu-id="a019a-119">Nel riquadro **Verifica le impostazioni** fare clic su **Crea questa etichetta** e fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="a019a-119">On the **Review your settings** pane, click **Create this label**, and then click **Close**.</span></span>
    
9. <span data-ttu-id="a019a-120">Ripetere i passaggi 5-8 per queste etichette aggiuntive:</span><span class="sxs-lookup"><span data-stu-id="a019a-120">Repeat steps 5-8 for these additional labels:</span></span>
    
  - <span data-ttu-id="a019a-121">Private</span><span class="sxs-lookup"><span data-stu-id="a019a-121">Private</span></span>
    
  - <span data-ttu-id="a019a-122">Dati sensibili</span><span class="sxs-lookup"><span data-stu-id="a019a-122">Sensitive</span></span>
    
  - <span data-ttu-id="a019a-123">Highly Confidential (Riservatezza elevata)</span><span class="sxs-lookup"><span data-stu-id="a019a-123">Highly Confidential</span></span>
    
10. <span data-ttu-id="a019a-124">Dal riquadro **Home > Etichette** fare clic su **Publish labels** (Pubblica etichette).</span><span class="sxs-lookup"><span data-stu-id="a019a-124">From the **Home > Labels** pane, click **Publish labels**.</span></span>
    
11. <span data-ttu-id="a019a-125">Nel riquadro **Choose labels to publish** (Scegli etichette da pubblicare) fare clic su **Choose labels to publish** (Scegli etichette da pubblicare).</span><span class="sxs-lookup"><span data-stu-id="a019a-125">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
12. <span data-ttu-id="a019a-126">Nel riquadro **Choose labels** (Scegli etichette) fare clic su **Aggiungi** e selezionare le quattro etichette.</span><span class="sxs-lookup"><span data-stu-id="a019a-126">On the **Choose labels** pane, click **Add** and select all four labels.</span></span>
    
13. <span data-ttu-id="a019a-127">Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="a019a-127">Click **Done**.</span></span>
    
14. <span data-ttu-id="a019a-128">Nel riquadro **Choose labels to publish** (Scegli etichette da pubblicare) fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a019a-128">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
15. <span data-ttu-id="a019a-129">Nel riquadro **Choose locations** (Scegli posizioni) fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a019a-129">On the **Choose locations** pane, click **Next**.</span></span>
    
16. <span data-ttu-id="a019a-130">Nel riquadro **Denomina il criterio**, digitare **Campagna** in **Nome**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a019a-130">On the **Name your policy** pane, type **Campaign** in **Name**, and then click **Next**.</span></span>
    
17. <span data-ttu-id="a019a-131">Nel riquadro **Verifica le impostazioni**, fare clic su **Pubblica etichette** e fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="a019a-131">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>
    
## <a name="phase-3-create-your-sharepoint-online-team-sites"></a><span data-ttu-id="a019a-132">Fase 3: creare i siti del team di SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="a019a-132">Phase 3: Create your SharePoint Online team sites</span></span>

<span data-ttu-id="a019a-133">In questa fase, vengono creati e configurati i siti del team di SharePoint Online per la campagna politica corrispondente ai quattro tipi di siti del team di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="a019a-133">In this phase, you create and configure SharePoint Online team sites for your political campaign corresponding to the four types of SharePoint Online team sites.</span></span>
  
### <a name="campaign-wide-team-site"></a><span data-ttu-id="a019a-134">Sito del team per la campagna su vasta scala</span><span class="sxs-lookup"><span data-stu-id="a019a-134">Campaign wide team site</span></span>

<span data-ttu-id="a019a-135">Per creare un sito pubblico iniziale per il team di SharePoint Online, eseguire queste operazioni:</span><span class="sxs-lookup"><span data-stu-id="a019a-135">To create a baseline public SharePoint Online team site, do the following:</span></span>
  
1. <span data-ttu-id="a019a-136">Se necessario, usare un browser sul computer locale e accedere all'interfaccia di amministrazione ([https://admin.microsoft.com](https://admin.microsoft.com)) con l'account amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="a019a-136">If needed, use a browser on your local computer and sign in to the admin center ([https://admin.microsoft.com](https://admin.microsoft.com)) using your global administrator account.</span></span>
    
2. <span data-ttu-id="a019a-137">Nell'elenco dei riquadri fare clic su **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="a019a-137">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="a019a-138">Nella nuova scheda **SharePoint** del browser fare clic su + **Crea sito**.</span><span class="sxs-lookup"><span data-stu-id="a019a-138">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>
    
4. <span data-ttu-id="a019a-139">Nella pagina **Crea sito** fare clic su **Sito del team**.</span><span class="sxs-lookup"><span data-stu-id="a019a-139">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="a019a-140">In **Nome sito**, digitare **Campagna su vasta scala**.</span><span class="sxs-lookup"><span data-stu-id="a019a-140">In **Site name**, type **Campaign wide**.</span></span> 
    
6. <span data-ttu-id="a019a-141">In **Descrizione sito del team**, digitare **Sito di SharePoint per l'intera campagna**.</span><span class="sxs-lookup"><span data-stu-id="a019a-141">In **Team site description**, type **SharePoint site for the entire campaign**.</span></span>
    
7. <span data-ttu-id="a019a-142">In **Impostazioni privacy** selezionare **Public – anyone in the organization can access this site** (Pubblico: qualsiasi persona dell'organizzazione può accedere a questo sito) e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a019a-142">In **Privacy settings**, select **Public - anyone in the organization can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="a019a-143">Nel riquadro **Who do you want to add?** (Chi si desidera aggiungere?) fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="a019a-143">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
<span data-ttu-id="a019a-144">Successivamente, configurare la cartella dei documenti del sito del team Campagna su vasta scala per l'etichetta Interno.</span><span class="sxs-lookup"><span data-stu-id="a019a-144">Next, configure the documents folder of the Campaign wide team site for the Internal label.</span></span>
  
1. <span data-ttu-id="a019a-145">Nella scheda **Campagna su vasta scala – Home** del browser, fare clic su **Documenti**.</span><span class="sxs-lookup"><span data-stu-id="a019a-145">In the **Campaign wide-Home** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="a019a-146">Fare clic sull'icona delle impostazioni e selezionare **Impostazioni libreria**.</span><span class="sxs-lookup"><span data-stu-id="a019a-146">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="a019a-147">In **Autorizzazioni e gestione** fare clic su **Apply label to items in this library** (Applica etichetta agli elementi in questa libreria).</span><span class="sxs-lookup"><span data-stu-id="a019a-147">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
4. <span data-ttu-id="a019a-148">In **Impostazioni - Applica etichetta**, selezionare **Interno** e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="a019a-148">In **Settings-Apply Label**, select **Internal**, and then click **Save**.</span></span>
    
### <a name="campaign-project-1-team-site"></a><span data-ttu-id="a019a-149">Sito del team 1 del progetto della campagna</span><span class="sxs-lookup"><span data-stu-id="a019a-149">Campaign project 1 team site</span></span>

<span data-ttu-id="a019a-150">Per creare un sito del team di SharePoint Online privato di base per un progetto all'interno della campagna, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a019a-150">To create a baseline private SharePoint Online team site for a project within the campaign, do the following:</span></span>
  
1. <span data-ttu-id="a019a-151">Se necessario, usare un browser sul computer locale e accedere all'interfaccia di amministrazione ([https://admin.microsoft.com](https://admin.microsoft.com)) con l'account amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="a019a-151">If needed, use a browser on your local computer and sign in to the admin center ([https://admin.microsoft.com](https://admin.microsoft.com)) using your global administrator account.</span></span>
    
2. <span data-ttu-id="a019a-152">Nell'elenco dei riquadri fare clic su **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="a019a-152">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="a019a-153">Nella nuova scheda **SharePoint** del browser fare clic su + **Crea sito**.</span><span class="sxs-lookup"><span data-stu-id="a019a-153">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>
    
4. <span data-ttu-id="a019a-154">Nella pagina **Crea sito** fare clic su **Sito del team**.</span><span class="sxs-lookup"><span data-stu-id="a019a-154">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="a019a-155">In **Nome sito**, digitare **Progetto della campagna 1**.</span><span class="sxs-lookup"><span data-stu-id="a019a-155">In **Site name**, type **Campaign project 1**.</span></span> 
    
6. <span data-ttu-id="a019a-156">In **Descrizione sito del team**, digitare **Sito di SharePoint per il progetto della campagna 1**.</span><span class="sxs-lookup"><span data-stu-id="a019a-156">In **Team site description,** type **SharePoint site for Campaign project 1**.</span></span>
    
7. <span data-ttu-id="a019a-157">In **Impostazioni privacy** selezionare **Private - only members can access this site** (Privato: solo i membri possono accedere a questo sito) e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a019a-157">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="a019a-158">Nel riquadro **Who do you want to add?** (Chi si desidera aggiungere?) fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="a019a-158">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
<span data-ttu-id="a019a-159">Successivamente, configurare la cartella dei documenti del sito del team Progetto della campagna 1 per l'etichetta Privato.</span><span class="sxs-lookup"><span data-stu-id="a019a-159">Next, configure the documents folder of the Campaign project 1 team site for the Private label.</span></span>
  
1. <span data-ttu-id="a019a-160">Nella scheda **Progetto della campagna 1 – Home** del browser, fare clic su **Documenti**.</span><span class="sxs-lookup"><span data-stu-id="a019a-160">In the **Campaign project 1-Home** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="a019a-161">Fare clic sull'icona delle impostazioni e selezionare **Impostazioni libreria**.</span><span class="sxs-lookup"><span data-stu-id="a019a-161">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="a019a-162">In **Autorizzazioni e gestione** fare clic su **Apply label to items in this library** (Applica etichetta agli elementi in questa libreria).</span><span class="sxs-lookup"><span data-stu-id="a019a-162">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
4. <span data-ttu-id="a019a-163">In **Impostazioni - Applica etichetta**, selezionare **Privato** e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="a019a-163">In **Settings-Apply Label**, select **Private**, and then click **Save**.</span></span>
    
### <a name="campaign-marketing-team-site"></a><span data-ttu-id="a019a-164">Sito del team per il marketing della campagna</span><span class="sxs-lookup"><span data-stu-id="a019a-164">Campaign marketing team site</span></span>

<span data-ttu-id="a019a-165">Per creare un sito del team di SharePoint Online isolato riservato per le risorse marketing della campagna, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a019a-165">To create a sensitive-level isolated SharePoint Online team site for campaign marketing resources, do the following:</span></span>
  
1. <span data-ttu-id="a019a-166">Usando un browser nel computer locale, accedere all'interfaccia di amministrazione ([https://admin.microsoft.com](https://admin.microsoft.com)) con l'account amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="a019a-166">Using a browser on your local computer, sign in to the admin center ([https://admin.microsoft.com](https://admin.microsoft.com)) using your global administrator account.</span></span>
    
2. <span data-ttu-id="a019a-167">Nell'elenco dei riquadri fare clic su **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="a019a-167">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="a019a-168">Nella nuova scheda **SharePoint** del browser fare clic su + **Crea sito**.</span><span class="sxs-lookup"><span data-stu-id="a019a-168">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>
    
4. <span data-ttu-id="a019a-169">Nella pagina **Crea sito** fare clic su **Sito del team**.</span><span class="sxs-lookup"><span data-stu-id="a019a-169">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="a019a-170">In **Nome sito del team**, digitare **Marketing della campagna**.</span><span class="sxs-lookup"><span data-stu-id="a019a-170">In **Team site name**, type **Campaign marketing**.</span></span>
    
6. <span data-ttu-id="a019a-171">In **Descrizione sito del team**, digitare **Sito di SharePoint per il marketing della campagna (riservato)**.</span><span class="sxs-lookup"><span data-stu-id="a019a-171">In **Team site description**, type **SharePoint site for campaign marketing (sensitive)**.</span></span>
    
7.  <span data-ttu-id="a019a-172">In **Impostazioni privacy** selezionare **Private - only members can access this site** (Privato: solo i membri possono accedere a questo sito) e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a019a-172">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="a019a-173">Nel riquadro **Who do you want to add?** (Chi si desidera aggiungere?) fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="a019a-173">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
9. <span data-ttu-id="a019a-174">Nella nuova scheda **Marketing della campagna** visualizzata nel browser, nella barra degli strumenti fare clic sull'icona delle impostazioni, quindi su **Autorizzazioni sito**.</span><span class="sxs-lookup"><span data-stu-id="a019a-174">On the new **Campaign marketing** tab in your browser, in the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
    
10. <span data-ttu-id="a019a-175">Nel riquadro **Autorizzazioni sito** fare clic su **Advanced permissions settings** (Impostazioni autorizzazioni avanzate).</span><span class="sxs-lookup"><span data-stu-id="a019a-175">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>
    
11. <span data-ttu-id="a019a-176">Nella nuova scheda **Autorizzazioni** del browser fare clic su **Impostazioni richieste di accesso**.</span><span class="sxs-lookup"><span data-stu-id="a019a-176">In the new **Permissions** tab in your browser, click **Access Request Settings**.</span></span>
    
12. <span data-ttu-id="a019a-177">Nella finestra di dialogo **Impostazioni richieste di accesso**, deselezionare le caselle di controllo **Consenti ai membri di condividere il sito e singoli file e cartelle** e **Consenti ai membri di invitare altre persone nel gruppo di membri del sito**, digitare **ITAdmin1@**<your organization name> **.onmicrosoft.com** in **Invia tutte le richieste di accesso**, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a019a-177">In the **Access Request Settings** dialog box, clear the **Allow members to share the site and individual files and folders** and **Allow members to invite others to the site members group** check boxes, type **ITAdmin1@**<your organization name> **.onmicrosoft.com** in **Send all requests for access**, and then click **OK**.</span></span>
    
13. <span data-ttu-id="a019a-178">Fare clic su **Membri marketing della campagna** nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="a019a-178">Click **Campaign marketing Members** in the list.</span></span>
    
14. <span data-ttu-id="a019a-179">Nella pagina **Utenti e gruppi** fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="a019a-179">On the **People and Groups** page, click **New**.</span></span>
    
15. <span data-ttu-id="a019a-180">Nella finestra di dialogo **Condividi**, digitare **Staff senior e strategico**, selezionarlo e quindi fare clic su **Condividi**.</span><span class="sxs-lookup"><span data-stu-id="a019a-180">In the **Share** dialog box, type **Senior and strategic staff**, select it, and then click **Share**.</span></span>
    
16. <span data-ttu-id="a019a-181">Ripetere i passaggi 14 e 15 per il gruppo **Staff di analisi** e per l'account utente **Regolare1**.</span><span class="sxs-lookup"><span data-stu-id="a019a-181">Repeat steps 14 and 15 for the **Analytics staff** group and the **Regular1** user account.</span></span>
    
17. <span data-ttu-id="a019a-182">Fare clic sul pulsante Indietro del browser.</span><span class="sxs-lookup"><span data-stu-id="a019a-182">Click the back button on your browser.</span></span>
    
18. <span data-ttu-id="a019a-183">Fare clic su **Proprietari marketing della campagna** nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="a019a-183">Click **Campaign marketing Owners** in the list.</span></span>
    
19. <span data-ttu-id="a019a-184">Nella pagina **Utenti e gruppi** fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="a019a-184">On the **People and Groups** page, click **New**.</span></span>
    
20. <span data-ttu-id="a019a-185">Nella finestra di dialogo **Condividi**, digitare **Staff IT**, selezionarlo e quindi fare clic su **Condividi**.</span><span class="sxs-lookup"><span data-stu-id="a019a-185">In the **Share** dialog box, type **IT staff**, select it, and then click **Share**.</span></span>
    
21. <span data-ttu-id="a019a-186">Fare clic sul pulsante Indietro del browser.</span><span class="sxs-lookup"><span data-stu-id="a019a-186">Click the back button on your browser.</span></span>
    
22. <span data-ttu-id="a019a-187">Chiudere la scheda **Utenti e gruppi** visualizzata nel browser, fare clic sulla scheda **Marketing della campagna-Home**, quindi chiudere il riquadro **Autorizzazioni sito**.</span><span class="sxs-lookup"><span data-stu-id="a019a-187">Close the **People and Groups** tab in your browser, click the **Campaign marketing-Home** tab in your browser, and then close the **Site permissions** pane.</span></span>
    
<span data-ttu-id="a019a-188">Ecco i risultati della configurazione delle autorizzazioni:</span><span class="sxs-lookup"><span data-stu-id="a019a-188">Here are the results of configuring permissions:</span></span>
  
- <span data-ttu-id="a019a-189">Il gruppo **Marketing della campagna-Membri** di SharePoint contiene solo il gruppo **Staff senior e strategico** (che include gli account utente Candidato, Capodellostaff e Strategico1), il gruppo **Marketing della campagna** (che include l'account utente di amministratore globale),il gruppo **Staff di analisi** (che include l'account utente DataScientist1) e l'account utente **Regolare1**.</span><span class="sxs-lookup"><span data-stu-id="a019a-189">The **Campaign marketing-Members** SharePoint group contains only the **Senior and strategic staff** group (which contains the Candidate, ChiefOfStaff, and Strategic1 user accounts), the **Campaign marketing** group (which contains the global administrator user account), the **Analytics staff** group (which contains the DataScientist1 user account), and the **Regular1** user account.</span></span>
    
- <span data-ttu-id="a019a-190">Il gruppo **Marketing della campagna-Proprietari** di SharePoint contiene solo il gruppo **Staff IT** (che include solo gli account utente ITAdmin1 e ITAdmin2).</span><span class="sxs-lookup"><span data-stu-id="a019a-190">The **Campaign marketing-Owners** SharePoint group contains only the **IT staff** group (which contains only the ITAdmin1 and ITAdmin2 user accounts).</span></span>
    
- <span data-ttu-id="a019a-191">Il gruppo **Marketing della campagna-Visitatori** di SharePoint non contiene gruppi o account utente.</span><span class="sxs-lookup"><span data-stu-id="a019a-191">The **Campaign marketing-Visitors** SharePoint group contains no groups or user accounts.</span></span>
    
- <span data-ttu-id="a019a-192">I membri non possono modificare le autorizzazioni a livello del sito (ciò può essere fatto solo dai membri del gruppo **Marketing della campagna-Proprietari**).</span><span class="sxs-lookup"><span data-stu-id="a019a-192">Members cannot modify site-level permissions (this can only be done by members of the **Campaign marketing-Owners** group).</span></span>
    
- <span data-ttu-id="a019a-193">Altri account utente non possono accedere al sito o alle sue risorse, ma possono richiedere l'accesso al sito, che invierà un'e-mail alla cassetta postale dell'account utente ITAdmin1.</span><span class="sxs-lookup"><span data-stu-id="a019a-193">Other user accounts cannot access the site or its resources, but can request access to the site, which will send an email to the ITAdmin1 user account mailbox.</span></span>
    
<span data-ttu-id="a019a-194">Successivamente, configurare la cartella dei documenti del sito del team Marketing della campagna per l'etichetta Riservato.</span><span class="sxs-lookup"><span data-stu-id="a019a-194">Next, configure the documents folder of the Campaign marketing team site for the Sensitive label.</span></span>
  
1. <span data-ttu-id="a019a-195">Nella scheda **Marketing della campagna–Home** del browser, fare clic su **Documenti**.</span><span class="sxs-lookup"><span data-stu-id="a019a-195">In the **Campaign marketing-Home** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="a019a-196">Fare clic sull'icona delle impostazioni e selezionare **Impostazioni libreria**.</span><span class="sxs-lookup"><span data-stu-id="a019a-196">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="a019a-197">In **Autorizzazioni e gestione** fare clic su **Apply label to items in this library** (Applica etichetta agli elementi in questa libreria).</span><span class="sxs-lookup"><span data-stu-id="a019a-197">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
4. <span data-ttu-id="a019a-198">In **Impostazioni - Applica etichetta**, selezionare **Riservato** e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="a019a-198">In **Settings-Apply Label**, select **Sensitive**, and then click **Save**.</span></span>
    
<span data-ttu-id="a019a-p103">Configurare quindi un criterio di prevenzione della perdita di dati che informa gli utenti quando condividono un documento presente su un sito del team di SharePoint Online con etichetta Sensibile al di fuori dell'organizzazione. Questo criterio di prevenzione della perdita di dati verrà applicato alle risorse nel sito marketing della campagna.</span><span class="sxs-lookup"><span data-stu-id="a019a-p103">Next, configure a data loss prevention (DLP) policy that notifies users when they share a document on a SharePoint Online team site with the Sensitive label outside the organization. This DLP policy will apply to resources in the Campaign marketing site.</span></span>
  
1. <span data-ttu-id="a019a-201">Dalla scheda **Microsoft Office Home** del browser, fare clic sul riquadro **Sicurezza e conformità**.</span><span class="sxs-lookup"><span data-stu-id="a019a-201">From the **Microsoft Office Home** tab in your browser, click the **Security & Compliance** tile.</span></span>
    
2. <span data-ttu-id="a019a-202">Nella nuova scheda **Sicurezza e conformità** del browser fare clic su **Prevenzione perdita dati > Criterio**.</span><span class="sxs-lookup"><span data-stu-id="a019a-202">On the new **Security & Compliance** tab in your browser, click **Data loss prevention > Policy**.</span></span>
    
3. <span data-ttu-id="a019a-203">Nel riquadro **Prevenzione della perdita di dati**, fare clic su **+ Crea un criterio**.</span><span class="sxs-lookup"><span data-stu-id="a019a-203">In the **Data loss prevention** pane, click **+ Create a policy**.</span></span>
    
4. <span data-ttu-id="a019a-204">Nel riquadro **Inizia con un modello o crea un criterio personalizzato**, fare clic su **Personalizza**, quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a019a-204">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="a019a-205">Nel riquadro **Denomina il criterio**, digitare **Siti del team di SharePoint Online con etichetta Riservato** in **Nome**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a019a-205">In the **Name your policy** pane, type **Sensitive label SharePoint Online team sites** in **Name**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="a019a-206">Nel riquadro **Choose locations** (Scegli posizioni) fare clic su **Let me choose specific locations** (Consenti di scegliere posizioni specifiche) e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a019a-206">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="a019a-207">Nell'elenco di località, disabilitare le località **Posta elettronica di Exchange** e **Account di OneDrive**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a019a-207">In the list of locations, disable the **Exchange email** and **OneDrive accounts** locations, and then click **Next**.</span></span>
    
8. <span data-ttu-id="a019a-208">Nel riquadro **Customize the types of sensitive info you want to protect** (Personalizza i tipi di informazioni sensibili da proteggere) fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="a019a-208">In the **Customize the types of sensitive info you want to protect** pane, click **Edit**.</span></span>
    
9. <span data-ttu-id="a019a-209">Nel riquadro per **scegliere i tipi di contenuto da proteggere**, fare clic su **Aggiungi** nella casella di riepilogo a discesa, quindi fare clic su **Etichette**.</span><span class="sxs-lookup"><span data-stu-id="a019a-209">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Labels**.</span></span>
    
10. <span data-ttu-id="a019a-210">Nel riquadro **Etichette**, fare clic su **+ Aggiungi**, selezionare l’etichetta **Riservato** fare clic su **Aggiungi**, quindi fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="a019a-210">In the **Labels** pane, click **+ Add**, select the **Sensitive** label, click **Add**, and then click **Done**.</span></span>
    
11. <span data-ttu-id="a019a-211">Nel riquadro **Choose the types of content to protect** (Scegli i tipi di contenuto da proteggere) fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="a019a-211">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="a019a-212">Nel riquadro **Customize the types of sensitive info you want to protect** (Personalizza i tipi di informazioni sensibili da proteggere) fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a019a-212">In the **Customize the types of sensitive info you want to protect** pane, click **Next**.</span></span>
    
13. <span data-ttu-id="a019a-213">Nel riquadro **What do you want to do if we detect sensitive info?** (Selezionare come procedere in caso di informazioni sensibili rilevate) fare clic su **Customize the tip and email** (Personalizza suggerimento e messaggio di posta elettronica).</span><span class="sxs-lookup"><span data-stu-id="a019a-213">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="a019a-214">Nel riquadro **Customize policy tips and email notifications** (Personalizza i suggerimenti per i criteri e le notifiche tramite posta elettronica) fare clic su **Customize the policy tip text** (Personalizza testo suggerimento per criterio).</span><span class="sxs-lookup"><span data-stu-id="a019a-214">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="a019a-215">Nella casella di testo digitare o incollare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="a019a-215">In the text box, type or paste in the following:</span></span>
    
  - <span data-ttu-id="a019a-p104">Per condividere con un utente esterno all'organizzazione, scaricare il file e quindi aprirlo. Fare clic su File, Proteggi documento, Crittografa con password, quindi specificare una password complessa. Inviare la password in un'e-mail separata o con altri mezzi di comunicazione.</span><span class="sxs-lookup"><span data-stu-id="a019a-p104">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>
    
16. <span data-ttu-id="a019a-219">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a019a-219">Click **OK**.</span></span>
    
17. <span data-ttu-id="a019a-220">Nel riquadro **Quale operazione eseguire se vengono rilevate informazioni riservate?**, deselezionare la casella di testo per **bloccare la condivisione e limitare l'accesso al contenuto condiviso**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a019a-220">In the **What do you want to do if we detect sensitive info?** pane, clear the **Block people from sharing, and restrict access to shared content** check box, and then click **Next**.</span></span>
    
18. <span data-ttu-id="a019a-221">Nel riquadro **Abilitare il criterio o eseguire prima un test?**, fare clic su **Sì, abilitarlo immediatamente**, quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a019a-221">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="a019a-222">Nel riquadro **Verifica le impostazioni** fare clic su **Crea** e quindi su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="a019a-222">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
    
### <a name="campaign-strategy-team-site"></a><span data-ttu-id="a019a-223">Sito del team per la strategia della campagna</span><span class="sxs-lookup"><span data-stu-id="a019a-223">Campaign strategy team site</span></span>

<span data-ttu-id="a019a-224">Per creare un sito del team di SharePoint Online isolato al livello estremamente riservato per le risorse relative alla strategia della campagna, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a019a-224">To create an isolated SharePoint Online team site at the highly confidential level for campaign strategy resources, do the following:</span></span>
  
1. <span data-ttu-id="a019a-225">Se necessario, usare un browser sul computer locale e accedere all'interfaccia di amministrazione ([https://admin.microsoft.com](https://admin.microsoft.com)) con l'account amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="a019a-225">If needed, use a browser on your local computer and sign in to the admin center ([https://admin.microsoft.com](https://admin.microsoft.com)) using your global administrator account.</span></span>
    
2. <span data-ttu-id="a019a-226">Nell'elenco dei riquadri fare clic su **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="a019a-226">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="a019a-227">Nella nuova scheda **SharePoint** del browser fare clic su + **Crea sito**.</span><span class="sxs-lookup"><span data-stu-id="a019a-227">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>
    
4. <span data-ttu-id="a019a-228">Nella pagina **Crea sito** fare clic su **Sito del team**.</span><span class="sxs-lookup"><span data-stu-id="a019a-228">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="a019a-229">In **Nome sito del team**, digitare **Strategia della campagna**.</span><span class="sxs-lookup"><span data-stu-id="a019a-229">In **Team site name**, type **Campaign strategy**.</span></span>
    
6. <span data-ttu-id="a019a-230">In **Descrizione sito del team**, digitare **Sito di SharePoint per la strategia della campagna (estremamente riservato)**.</span><span class="sxs-lookup"><span data-stu-id="a019a-230">In **Team site description**, type **SharePoint site for campaign strategy (highly confidential)**.</span></span>
    
7.  <span data-ttu-id="a019a-231">In **Impostazioni privacy** selezionare **Private - only members can access this site** (Privato: solo i membri possono accedere a questo sito) e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a019a-231">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="a019a-232">Nel riquadro **Who do you want to add?** (Chi si desidera aggiungere?) fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="a019a-232">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
9. <span data-ttu-id="a019a-233">Nella nuova scheda **Strategia della campagna** visualizzata nel browser, nella barra degli strumenti fare clic sull'icona delle impostazioni, quindi su **Autorizzazioni sito**.</span><span class="sxs-lookup"><span data-stu-id="a019a-233">On the new **Campaign strategy** tab in your browser, in the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
    
10. <span data-ttu-id="a019a-234">Nel riquadro **Autorizzazioni sito** fare clic su **Advanced permissions settings** (Impostazioni autorizzazioni avanzate).</span><span class="sxs-lookup"><span data-stu-id="a019a-234">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>
    
11. <span data-ttu-id="a019a-235">Nella nuova scheda **Autorizzazioni** del browser fare clic su **Impostazioni richieste di accesso**.</span><span class="sxs-lookup"><span data-stu-id="a019a-235">In the new **Permissions** tab in your browser, click **Access Request Settings**.</span></span>
    
12. <span data-ttu-id="a019a-236">Nella finestra di dialogo **Impostazioni richieste di accesso**, deselezionare **Consenti ai membri di condividere il sito e singoli file e cartelle** e **Consenti ai membri di invitare altre persone nel gruppo di membri del sito** (le tre caselle di controllo devono essere deselezionate), quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a019a-236">In the **Access Request Settings** dialog box, clear **Allow members to share the site and individual files and folders** and **Allow members to invite others to the site members group** (so that all three check boxes are cleared), and then click **OK**.</span></span>
    
13. <span data-ttu-id="a019a-237">Fare clic su **Membri strategia della campagna** nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="a019a-237">Click **Campaign strategy Members** in the list.</span></span>
    
14. <span data-ttu-id="a019a-238">Nella pagina **Utenti e gruppi** fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="a019a-238">On the **People and Groups** page, click **New**.</span></span>
    
15. <span data-ttu-id="a019a-239">Nella finestra di dialogo **Condividi**, digitare **Staff senior e strategico**, selezionarlo e quindi fare clic su **Condividi**.</span><span class="sxs-lookup"><span data-stu-id="a019a-239">In the **Share** dialog box, type **Senior and strategic staff**, select it, and then click **Share**.</span></span>
    
16. <span data-ttu-id="a019a-240">Fare clic su **Proprietari strategia della campagna** nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="a019a-240">Click **Campaign strategy Owners** in the list.</span></span>
    
17. <span data-ttu-id="a019a-241">Nella pagina **Utenti e gruppi** fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="a019a-241">On the **People and Groups** page, click **New**.</span></span>
    
18. <span data-ttu-id="a019a-242">Nella finestra di dialogo **Condividi**, digitare **Staff IT**, selezionarlo e quindi fare clic su **Condividi**.</span><span class="sxs-lookup"><span data-stu-id="a019a-242">In the **Share** dialog box, type **IT staff**, select it, and then click **Share**.</span></span>
    
19. <span data-ttu-id="a019a-243">Fare clic sul pulsante Indietro del browser.</span><span class="sxs-lookup"><span data-stu-id="a019a-243">Click the back button on your browser.</span></span>
    
20. <span data-ttu-id="a019a-244">Chiudere la scheda **Utenti e gruppi** visualizzata nel browser, fare clic sulla scheda **Strategia della campagna-Home**, quindi chiudere il riquadro **Autorizzazioni sito**.</span><span class="sxs-lookup"><span data-stu-id="a019a-244">Close the **People and Groups** tab in your browser, click the **Campaign strategy-Home** tab in your browser, and then close the **Site permissions** pane.</span></span>
    
<span data-ttu-id="a019a-245">Ecco i risultati della configurazione delle autorizzazioni:</span><span class="sxs-lookup"><span data-stu-id="a019a-245">Here are the results of configuring permissions:</span></span>
  
- <span data-ttu-id="a019a-246">Il gruppo **Strategia della campagna-Membri** di SharePoint contiene solo il gruppo **Staff senior e strategico** (che include solo gli account utente Candidato, Capodellostaff e Strategico1) e il gruppo **Strategia della campagna** (che include solo l'account utente di amministratore globale).
</span><span class="sxs-lookup"><span data-stu-id="a019a-246">The **Campaign strategy-Members** SharePoint group contains only the **Senior and strategic staff** group (which contains only the Candidate, ChiefOfStaff, and Strategic1 user accounts) and the **Campaign strategy** group (which contains only the global administrator user account).</span></span>
    
- <span data-ttu-id="a019a-247">Il gruppo **Strategia della campagna-Proprietari** di SharePoint contiene solo il gruppo **Staff IT** (che include solo gli account utente ITAdmin1 e ITAdmin2).</span><span class="sxs-lookup"><span data-stu-id="a019a-247">The **Campaign strategy-Owners** SharePoint group contains only the **IT staff** group (which contains only the ITAdmin1 and ITAdmin2 user accounts).</span></span>
    
- <span data-ttu-id="a019a-248">Il gruppo **Strategia della campagna-Visitatori** di SharePoint non contiene gruppi o account utente.	</span><span class="sxs-lookup"><span data-stu-id="a019a-248">The **Campaign strategy-Visitors** SharePoint group contains no groups or user accounts.</span></span>
    
- <span data-ttu-id="a019a-249">I membri non possono modificare le autorizzazioni a livello del sito (ciò può essere fatto solo dai membri del gruppo **Strategia della campagna-Proprietari**).</span><span class="sxs-lookup"><span data-stu-id="a019a-249">Members cannot modify site-level permissions (this can only be done by members of the **Campaign strategy-Owners** group).</span></span>
    
- <span data-ttu-id="a019a-p105">Altri account utente non possono accedere al sito e alle relative risorse o richiedere l'accesso al sito. Ulteriori autorizzazioni per il sito devono essere effettuate dall'amministratore globale o da un membro del gruppo **Strategia della campagna-Proprietari**.</span><span class="sxs-lookup"><span data-stu-id="a019a-p105">Other user accounts cannot access the site or its resources or request access to the site. Additional permissions to the site must be done by the global administrator or by a member of the **Campaign strategy-Owners** group.</span></span>
    
<span data-ttu-id="a019a-252">Successivamente, configurare la cartella dei documenti del sito del team Strategia della campagna per l'etichetta Estremamente riservato.</span><span class="sxs-lookup"><span data-stu-id="a019a-252">Next, configure the documents folder of the Campaign strategy team site for the Highly Confidential label.</span></span>
  
1. <span data-ttu-id="a019a-253">Nella scheda **Strategia della campagna–Home** del browser, fare clic su **Documenti**.</span><span class="sxs-lookup"><span data-stu-id="a019a-253">In the **Campaign strategy-Home** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="a019a-254">Fare clic sull'icona delle impostazioni e selezionare **Impostazioni libreria**.</span><span class="sxs-lookup"><span data-stu-id="a019a-254">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="a019a-255">In **Autorizzazioni e gestione** fare clic su **Apply label to items in this library** (Applica etichetta agli elementi in questa libreria).</span><span class="sxs-lookup"><span data-stu-id="a019a-255">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
4. <span data-ttu-id="a019a-256">In **Impostazioni - Applica etichetta**, selezionare **Estremamente riservato** e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="a019a-256">In **Settings-Apply Label**, select **Highly Confidential**, and then click **Save**.</span></span>
    
<span data-ttu-id="a019a-p106">Configurare quindi un criterio di prevenzione della perdita di dati che blocca gli utenti quando condividono un documento presente su un sito del team di SharePoint Online con etichetta Estremamente riservato al di fuori dell'organizzazione. Questo criterio di prevenzione della perdita di dati verrà applicato alle risorse nel sito della strategia della campagna.</span><span class="sxs-lookup"><span data-stu-id="a019a-p106">Next, configure a DLP policy that blocks users when they share a document on a SharePoint Online team site with the Highly Confidential label outside the organization. This DLP policy will apply to resources in the Campaign strategy site.</span></span>
  
1. <span data-ttu-id="a019a-259">Se necessario, usare un browser nel computer locale e accedere all'interfaccia di amministrazione ([https://admin.microsoft.com](https://admin.microsoft.com)) con un account che dispone del ruolo Amministratore della sicurezza o Amministratore società.</span><span class="sxs-lookup"><span data-stu-id="a019a-259">If needed, use a browser on your local computer and sign in to the admin center ([https://admin.microsoft.com](https://admin.microsoft.com)) with an account that has the Security Administrator or Company Administrator role.</span></span>
    
2. <span data-ttu-id="a019a-260">Dalla scheda **Microsoft Office Home** del browser, fare clic sul riquadro **Sicurezza e conformità**.</span><span class="sxs-lookup"><span data-stu-id="a019a-260">From the **Microsoft Office Home** tab in your browser, click the **Security & Compliance** tile.</span></span>
    
3. <span data-ttu-id="a019a-261">Nella nuova scheda **Sicurezza e conformità** del browser fare clic su **Prevenzione perdita dati > Criterio**.</span><span class="sxs-lookup"><span data-stu-id="a019a-261">On the new **Security & Compliance** tab in your browser, click **Data loss prevention > Policy**.</span></span>
    
4. <span data-ttu-id="a019a-262">Nel riquadro **Prevenzione della perdita di dati**, fare clic su **+ Crea un criterio**.</span><span class="sxs-lookup"><span data-stu-id="a019a-262">In the **Data loss prevention** pane, click **+ Create a policy**.</span></span>
    
5. <span data-ttu-id="a019a-263">Nel riquadro **Inizia con un modello o crea un criterio personalizzato**, fare clic su **Personalizza**, quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a019a-263">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="a019a-264">Nel riquadro **Denomina il criterio**, digitare **Siti del team di SharePoint Online con etichetta Estremamente riservato** in **Nome**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a019a-264">In the **Name your policy** pane, type **Highly Confidential label SharePoint Online team sites** in **Name**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="a019a-265">Nel riquadro **Choose locations** (Scegli posizioni) fare clic su **Let me choose specific locations** (Consenti di scegliere posizioni specifiche) e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a019a-265">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="a019a-266">Nell'elenco di località, disabilitare le località **Posta elettronica di Exchange** e **Account di OneDrive**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a019a-266">In the list of locations, disable the **Exchange email** and **OneDrive accounts** locations, and then click **Next**.</span></span>
    
9. <span data-ttu-id="a019a-267">Nel riquadro **Customize the types of sensitive info you want to protect** (Personalizza i tipi di informazioni sensibili da proteggere) fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="a019a-267">In the **Customize the types of sensitive info you want to protect** pane, click **Edit**.</span></span>
    
10. <span data-ttu-id="a019a-268">Nel riquadro per **scegliere i tipi di contenuto da proteggere**, fare clic su **Aggiungi** nella casella di riepilogo a discesa, quindi fare clic su **Etichette**.</span><span class="sxs-lookup"><span data-stu-id="a019a-268">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Labels**.</span></span>
    
11. <span data-ttu-id="a019a-269">Nel riquadro **Etichette**, fare clic su **+ Aggiungi**, selezionare l’etichetta **Estremamente riservato**, fare clic su **Aggiungi**, quindi fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="a019a-269">In the **Labels** pane, click **+ Add**, select the **Highly Confidential** label, click **Add**, and then click **Done**.</span></span>
    
12. <span data-ttu-id="a019a-270">Nel riquadro **Choose the types of content to protect** (Scegli i tipi di contenuto da proteggere) fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="a019a-270">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
13. <span data-ttu-id="a019a-271">Nel riquadro **Customize the types of sensitive info you want to protect** (Personalizza i tipi di informazioni sensibili da proteggere) fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a019a-271">In the **Customize the types of sensitive info you want to protect** pane, click **Next**.</span></span>
    
14. <span data-ttu-id="a019a-272">Nel riquadro **What do you want to do if we detect sensitive info?** (Selezionare come procedere in caso di informazioni sensibili rilevate) fare clic su **Customize the tip and email** (Personalizza suggerimento e messaggio di posta elettronica).</span><span class="sxs-lookup"><span data-stu-id="a019a-272">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
15. <span data-ttu-id="a019a-273">Nel riquadro **Customize policy tips and email notifications** (Personalizza i suggerimenti per i criteri e le notifiche tramite posta elettronica) fare clic su **Customize the policy tip text** (Personalizza testo suggerimento per criterio).</span><span class="sxs-lookup"><span data-stu-id="a019a-273">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
16. <span data-ttu-id="a019a-274">Nella casella di testo digitare o incollare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="a019a-274">In the text box, type or paste in the following:</span></span>
    
  - <span data-ttu-id="a019a-p107">Per condividere con un utente esterno all'organizzazione, scaricare il file e quindi aprirlo. Fare clic su File, Proteggi documento, Crittografa con password, quindi specificare una password complessa. Inviare la password in un'e-mail separata o con altri mezzi di comunicazione.</span><span class="sxs-lookup"><span data-stu-id="a019a-p107">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>
    
17. <span data-ttu-id="a019a-278">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a019a-278">Click **OK**.</span></span>
    
18. <span data-ttu-id="a019a-279">Nel riquadro **Quale operazione eseguire se vengono rilevate informazioni riservate?**, selezionare l’opzione per **richiedere motivazioni aziendali per eseguire l'override**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a019a-279">In the **What do you want to do if we detect sensitive info?** pane, select **Require a business justification to override**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="a019a-280">Nel riquadro **Abilitare il criterio o eseguire prima un test?**, fare clic su **Sì, abilitarlo immediatamente**, quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a019a-280">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
20. <span data-ttu-id="a019a-281">Nel riquadro **Verifica le impostazioni** fare clic su **Crea** e quindi su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="a019a-281">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
    
<span data-ttu-id="a019a-282">Seguire le istruzioni in [Attivare Azure RMS dall'interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/information-protection/deploy-use/activate-office365).</span><span class="sxs-lookup"><span data-stu-id="a019a-282">Use the instructions in [Activate Azure RMS with the Microsoft 365 admin center](https://docs.microsoft.com/information-protection/deploy-use/activate-office365).</span></span>
  
<span data-ttu-id="a019a-283">Configurare quindi Azure Information Protection con un nuovo criterio con ambito e un'etichetta secondaria per la protezione e le autorizzazioni eseguendo le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a019a-283">Next, configure Azure Information Protection with a new scoped policy and sub-label for protection and permissions with the following steps:</span></span>
  
1. <span data-ttu-id="a019a-284">Accedere all'interfaccia di amministrazione con un account che dispone del ruolo Amministratore della sicurezza o Amministratore della società.</span><span class="sxs-lookup"><span data-stu-id="a019a-284">Sign in to the admin center with an account that has the Security Administrator or Company Administrator role.</span></span> <span data-ttu-id="a019a-285">Per informazioni, vedere [Dove accedere a Office 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="a019a-285">For help, see [Where to sign in to Office 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="a019a-286">In un'altra scheda del browser, accedere al portale di Azure ([https://portal.azure.com](https://portal.azure.com)).</span><span class="sxs-lookup"><span data-stu-id="a019a-286">In a separate tab of your browser, go to the Azure portal ([https://portal.azure.com](https://portal.azure.com)).</span></span>
    
4. <span data-ttu-id="a019a-287">Nel riquadro di ricerca digitare **Informazioni** e quindi fare clic su **Azure Information Protection**.</span><span class="sxs-lookup"><span data-stu-id="a019a-287">In the search pane, type **information**, and then click **Azure Information Protection**.</span></span>

5. <span data-ttu-id="a019a-288">Fare clic su **Etichette**.</span><span class="sxs-lookup"><span data-stu-id="a019a-288">Click **Labels**.</span></span>
    
6. <span data-ttu-id="a019a-289">Fare clic con il pulsante destro del mouse sull'etichetta **Estremamente riservato**, quindi su **Aggiungi un'etichetta secondaria**.</span><span class="sxs-lookup"><span data-stu-id="a019a-289">Right-click the **Highly Confidential** label, and then click **Add a sub-label**.</span></span>
    
7. <span data-ttu-id="a019a-290">Digitare **CompanyStrategy** in **Nome** ed **Etichetta per i documenti nel sito del team di strategia aziendale** in **Descrizione**.</span><span class="sxs-lookup"><span data-stu-id="a019a-290">Type **CampaignStrategy** in **Name** and **Label for documents in the Campaign strategy team site** in **Description**.</span></span>
    
8. <span data-ttu-id="a019a-291">In **Configurare le autorizzazioni per documenti e messaggi di posta elettronica contenenti questa etichetta** fare clic su **Proteggi**.</span><span class="sxs-lookup"><span data-stu-id="a019a-291">In **Set permissions for documents and emails containing this label**, click **Protect**.</span></span>
    
9. <span data-ttu-id="a019a-292">Nella sezione **Protezione** fare clic su **Azure (chiave cloud)**.</span><span class="sxs-lookup"><span data-stu-id="a019a-292">In the **Protection** section, click **Azure (cloud key)**.</span></span>
    
10. <span data-ttu-id="a019a-293">Nel pannello **Protezione** fare clic su **+ Aggiungi autorizzazioni** in **Impostazioni di protezione**.</span><span class="sxs-lookup"><span data-stu-id="a019a-293">On the **Protection** blade, under **Protection settings**, click **+ Add permissions**.</span></span>
    
11. <span data-ttu-id="a019a-294">Nel pannello **Aggiungi autorizzazioni**, in **Specifica utenti e gruppi** fare clic su **+ Sfoglia la directory**.</span><span class="sxs-lookup"><span data-stu-id="a019a-294">On the **Add permissions** blade, under **Specify users and groups**, click **+ Browse directory**.</span></span>
    
12. <span data-ttu-id="a019a-295">Nel riquadro **Utenti e gruppi di AAD**, selezionare **Personale senior e strategico** e quindi fare clic su **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="a019a-295">On the **AAD Users and Groups** pane, select **Senior and strategic staff**, and then click **Select**.</span></span>
    
13. <span data-ttu-id="a019a-296">In **Scegliere le autorizzazioni dal set di impostazioni o imposta personalizzato** fare clic su **Personalizza**, quindi sulla casella **Visualizza diritti**, **Modifica contenuto**, **Salva**, **Rispondi** e **Rispondi a tutti**</span><span class="sxs-lookup"><span data-stu-id="a019a-296">Under **Choose permissions from the preset or set custom**, click **Custom**, and then click the **View Rights**, **Edit Content**, **Save**, **Reply**, and **Reply all** check boxes.</span></span>
    
14. <span data-ttu-id="a019a-297">Fare due volte clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a019a-297">Click **OK** twice.</span></span>
    
15. <span data-ttu-id="a019a-298">Nel pannello **Etichetta secondaria** fare clic su **Salva**, quindi su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a019a-298">On the **Sub-label** blade, click **Save**, and then click **OK**.</span></span>

16. <span data-ttu-id="a019a-299">Nel pannello **Azure Information Protection** fare clic su **Criteri > + Aggiungi un nuovo criterio**.</span><span class="sxs-lookup"><span data-stu-id="a019a-299">On the **Azure Information protection** blade, click **Policies > + Add a new policy**.</span></span>
    
17. <span data-ttu-id="a019a-300">Digitare **CompanyStrategy** in **Nome** e **Documenti nel sito del team di strategia aziendale** in **Descrizione**.</span><span class="sxs-lookup"><span data-stu-id="a019a-300">Type **CampaignStrategy** in **Name** and **Documents in the Campaign strategy team site** in **Description**.</span></span>
    
18. <span data-ttu-id="a019a-301">Fare clic su **Selezionare gli utenti o i gruppi a cui viene applicato il criterio > Utenti/Gruppi**, quindi selezionare **Personale senior e strategico**.</span><span class="sxs-lookup"><span data-stu-id="a019a-301">Click **Select which users or groups get this policy > User/Groups**, and then select **Senior and strategic staff**.</span></span>
    
19. <span data-ttu-id="a019a-302">Fare clic su **Seleziona > OK**.</span><span class="sxs-lookup"><span data-stu-id="a019a-302">Click **Select > OK**.</span></span>

20. <span data-ttu-id="a019a-p109">Fare clic su **Aggiungi o rimuovi etichette**. Nel riquadro **Criteri: Aggiungere o rimuovere etichette** fare clic su **CampaignStrategy**, quindi su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a019a-p109">Click **Add or remove labels**. In the **Policy: Add or remove labels** pane, click **CampaignStrategy**, and then click **OK**.</span></span>   

21. <span data-ttu-id="a019a-305">Fare clic su **Salva**, quindi su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a019a-305">Click **Save**, and then click **OK**.</span></span>
  
<span data-ttu-id="a019a-306">Ora è possibile iniziare a creare documenti in questi quattro siti e a testare l'accesso a tali siti con vari account utente.</span><span class="sxs-lookup"><span data-stu-id="a019a-306">You are now ready to begin creating documents in these four sites and test access to them with various user accounts.</span></span> 
  
<span data-ttu-id="a019a-307">Per proteggere un documento con Azure Information Protection e la nuova etichetta, è necessario [installare il client di Azure Information Protection](https://docs.microsoft.com/information-protection/rms-client/install-client-app) in un computer di test, installare Office dall'interfaccia di amministrazione e quindi accedere da Microsoft Word con un account del gruppo **Personale senior e strategico** dell'abbonamento di valutazione.</span><span class="sxs-lookup"><span data-stu-id="a019a-307">To protect a document with Azure Information Protection and this new label, you must [install the Azure Information Protection client](https://docs.microsoft.com/information-protection/rms-client/install-client-app) on a test machine, install Office from the admin center, and then sign in from Microsoft Word with an account in the **Senior and strategic staff** group of your trial subscription.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a019a-308">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a019a-308">See Also</span></span>

[<span data-ttu-id="a019a-309">Guida sulla sicurezza Microsoft per organizzazioni che si occupano della campagna politica, no profit e altre organizzazioni Agile</span><span class="sxs-lookup"><span data-stu-id="a019a-309">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
  
[<span data-ttu-id="a019a-310">Configurare gruppi e utenti per un ambiente di sviluppo/testing per la campagna politica</span><span class="sxs-lookup"><span data-stu-id="a019a-310">Configure groups and users for a political campaign dev/test environment</span></span>](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md)
  
[<span data-ttu-id="a019a-311">Guida al lab test (TLG) per adozione del cloud</span><span class="sxs-lookup"><span data-stu-id="a019a-311">Cloud adoption Test Lab Guides (TLGs)</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/cloud-adoption-test-lab-guides-tlgs)
  
[<span data-ttu-id="a019a-312">Adozione del cloud e soluzioni ibride</span><span class="sxs-lookup"><span data-stu-id="a019a-312">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)




