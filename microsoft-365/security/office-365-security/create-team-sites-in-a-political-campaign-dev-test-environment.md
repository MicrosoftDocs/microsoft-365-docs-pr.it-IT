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
localization_priority: Priority
search.appverid:
- MET150
ms.custom: seo-marvel-apr2020
ms.assetid: c2112ce8-1c4b-424f-b200-59e161db2d21
description: 'Sintesi: creare siti del team di SharePoint Online pubblici, privati, riservati ed estremamente riservati nel proprio ambiente di sviluppo/testinging per la campagna politica.'
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: fcba6e2f3939115d6dfbaae80d322246bdeadee9
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029898"
---
# <a name="create-team-sites-in-a-political-campaign-devtest-environment"></a><span data-ttu-id="4e5c5-103">Creare siti del team in un ambiente di sviluppo/testinging per la campagna politica</span><span class="sxs-lookup"><span data-stu-id="4e5c5-103">Create team sites in a political campaign dev/test environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="4e5c5-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="4e5c5-104">**Applies to**</span></span>

- [<span data-ttu-id="4e5c5-105">Microsoft Defender per Office 365 Piano 2</span><span class="sxs-lookup"><span data-stu-id="4e5c5-105">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)

 <span data-ttu-id="4e5c5-106">**Sintesi**: creare siti del team di SharePoint Online pubblici, privati, riservati ed estremamente riservati nel proprio ambiente di sviluppo/testinging per la campagna politica.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-106">**Summary:** Create public, private, sensitive, and highly confidential SharePoint Online team sites in your political campaign dev/test environment.</span></span>

<span data-ttu-id="4e5c5-p101">Attenersi alle istruzioni in questo articolo per creare un ambiente di sviluppo/testing che include i quattro tipi di siti del team di SharePoint Online per la soluzione [Guida sulla sicurezza Microsoft per organizzazioni che si occupano della campagna politica, no profit e altre organizzazioni Agile](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md). I siti sono descritti nel dettaglio nell'Argomento 10, **SharePoint e OneDrive for Business**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-p101">Use the instructions in this article to create a dev/test environment that includes the four different types of SharePoint Online team sites for the [Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md) solution. These sites are described in detail on Topic 10, titled **SharePoint and OneDrive for Business**.</span></span>

## <a name="phase-1-create-your-political-campaign-devtest-environment"></a><span data-ttu-id="4e5c5-109">Fase 1: creare l'ambiente di sviluppo/testing per la campagna politica</span><span class="sxs-lookup"><span data-stu-id="4e5c5-109">Phase 1: Create your political campaign dev/test environment</span></span>

<span data-ttu-id="4e5c5-110">Prima di tutto, seguire le istruzioni in [Configurazione di gruppi e utenti in un ambiente di sviluppo/testing per le campagne politiche](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md) per creare le sottoscrizioni, gli utenti e i gruppi.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-110">First, follow the instructions in [Configure groups and users for a political campaign dev/test environment](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md) to create your subscriptions, users, and groups.</span></span>

## <a name="phase-2-create-labels"></a><span data-ttu-id="4e5c5-111">Fase 2: creare etichette</span><span class="sxs-lookup"><span data-stu-id="4e5c5-111">Phase 2: Create labels</span></span>

<span data-ttu-id="4e5c5-112">In questa fase, vengono create le etichette per i diversi livelli di sicurezza per cartelle di documenti dei siti del team di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-112">In this phase, you create the labels for the different levels of security for SharePoint Online team site document folders.</span></span>

1. <span data-ttu-id="4e5c5-p102">Se necessario, accedere all'interfaccia di amministrazione di Microsoft 365 (<https://admin.microsoft.com>) con le credenziali dell'account amministratore globale dell'abbonamento di valutazione. Per informazioni, vedere [Dove accedere a Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="4e5c5-p102">If needed, sign in to the Microsoft 365 admin center (<https://admin.microsoft.com>) with the credentials of the global administrator account of your trial subscription. For help, see [Where to sign in to Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>

2. <span data-ttu-id="4e5c5-115">Nella pagina iniziale **Home** fare clic su **Mostra tutto**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-115">From the **Home** page where you start, click **Show all**.</span></span> <span data-ttu-id="4e5c5-116">Nella sezione **Interfacce di amministrazione** visualizzata fare clic su **Conformità**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-116">In the **Admin centers** section that appears, click **Compliance**.</span></span>

3. <span data-ttu-id="4e5c5-117">Nella pagina **Home** del Centro conformità Microsoft 365 passare alla sezione **Soluzioni** \> **Information Protection**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-117">From the **Home** page of the Microsoft 365 compliance center, go to the **Solutions** section \> **Information protection**.</span></span> <span data-ttu-id="4e5c5-118">Per passare direttamente alla pagina **Information Protection**, usare <https://compliance.microsoft.com//informationprotection>.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-118">To go directly to the **Information protection** page, use <https://compliance.microsoft.com//informationprotection>.</span></span>

4. <span data-ttu-id="4e5c5-119">Nella pagina **Information Protection** verificare che il tag **Etichetta** sia selezionato, quindi fare clic sull’icona ![Crea un'etichetta](../../media/m365-cc-sc-create-icon.png) **Crea un'etichetta**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-119">On the **Information protection** page, verify that the **Label** tag is selected, and then click  ![Create a label icon](../../media/m365-cc-sc-create-icon.png) **Create a label**.</span></span>

5. <span data-ttu-id="4e5c5-120">Verrà visualizzata la procedura guidata **Nuova etichetta di riservatezza**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-120">The **New sensitivity label** wizard opens.</span></span> <span data-ttu-id="4e5c5-121">Nel passaggio **Nome e descrizione** immettere i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="4e5c5-121">On the **Name & description** step, enter the following values:</span></span>
   - <span data-ttu-id="4e5c5-122">**Nome**: digitare **Interno**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-122">**Name**: Type **Internal**.</span></span>
   - <span data-ttu-id="4e5c5-123">**Nome visualizzato**</span><span class="sxs-lookup"><span data-stu-id="4e5c5-123">**Display name**</span></span>
   - <span data-ttu-id="4e5c5-124">**Descrizione per gli utenti**</span><span class="sxs-lookup"><span data-stu-id="4e5c5-124">**Description for users**</span></span>

   <span data-ttu-id="4e5c5-125">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-125">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="4e5c5-126">Nel riquadro **Label settings** (Importazioni etichetta) fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-126">On the **Label settings** pane, click **Next**.</span></span>

7. <span data-ttu-id="4e5c5-127">Nel riquadro **Verifica le impostazioni** fare clic su **Crea questa etichetta** e fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-127">On the **Review your settings** pane, click **Create this label**, and then click **Close**.</span></span>

8. <span data-ttu-id="4e5c5-128">Ripetere i passaggi 5-8 per queste etichette aggiuntive:</span><span class="sxs-lookup"><span data-stu-id="4e5c5-128">Repeat steps 5-8 for these additional labels:</span></span>

   - <span data-ttu-id="4e5c5-129">Private</span><span class="sxs-lookup"><span data-stu-id="4e5c5-129">Private</span></span>
   - <span data-ttu-id="4e5c5-130">Dati sensibili</span><span class="sxs-lookup"><span data-stu-id="4e5c5-130">Sensitive</span></span>
   - <span data-ttu-id="4e5c5-131">Highly Confidential (Riservatezza elevata)</span><span class="sxs-lookup"><span data-stu-id="4e5c5-131">Highly Confidential</span></span>

9. <span data-ttu-id="4e5c5-132">Dal riquadro **Home > Etichette** fare clic su **Publish labels** (Pubblica etichette).</span><span class="sxs-lookup"><span data-stu-id="4e5c5-132">From the **Home > Labels** pane, click **Publish labels**.</span></span>

10. <span data-ttu-id="4e5c5-133">Nel riquadro **Choose labels to publish** (Scegli etichette da pubblicare) fare clic su **Choose labels to publish** (Scegli etichette da pubblicare).</span><span class="sxs-lookup"><span data-stu-id="4e5c5-133">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>

11. <span data-ttu-id="4e5c5-134">Nel riquadro **Choose labels** (Scegli etichette) fare clic su **Aggiungi** e selezionare le quattro etichette.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-134">On the **Choose labels** pane, click **Add** and select all four labels.</span></span>

12. <span data-ttu-id="4e5c5-135">Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-135">Click **Done**.</span></span>

13. <span data-ttu-id="4e5c5-136">Nel riquadro **Choose labels to publish** (Scegli etichette da pubblicare) fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-136">On the **Choose labels to publish** pane, click **Next**.</span></span>

14. <span data-ttu-id="4e5c5-137">Nel riquadro **Choose locations** (Scegli posizioni) fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-137">On the **Choose locations** pane, click **Next**.</span></span>

15. <span data-ttu-id="4e5c5-138">Nel riquadro **Denomina il criterio**, digitare **Campagna** in **Nome**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-138">On the **Name your policy** pane, type **Campaign** in **Name**, and then click **Next**.</span></span>

16. <span data-ttu-id="4e5c5-139">Nel riquadro **Verifica le impostazioni**, fare clic su **Pubblica etichette** e fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-139">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>

## <a name="phase-3-create-your-sharepoint-online-team-sites"></a><span data-ttu-id="4e5c5-140">Fase 3: creare i siti del team di SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="4e5c5-140">Phase 3: Create your SharePoint Online team sites</span></span>

<span data-ttu-id="4e5c5-141">In questa fase, vengono creati e configurati i siti del team di SharePoint Online per la campagna politica corrispondente ai quattro tipi di siti del team di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-141">In this phase, you create and configure SharePoint Online team sites for your political campaign corresponding to the four types of SharePoint Online team sites.</span></span>

### <a name="campaign-wide-team-site"></a><span data-ttu-id="4e5c5-142">Sito del team per la campagna su vasta scala</span><span class="sxs-lookup"><span data-stu-id="4e5c5-142">Campaign wide team site</span></span>

<span data-ttu-id="4e5c5-143">Per creare un sito pubblico iniziale per il team di SharePoint Online, eseguire queste operazioni:</span><span class="sxs-lookup"><span data-stu-id="4e5c5-143">To create a baseline public SharePoint Online team site, do the following:</span></span>

1. <span data-ttu-id="4e5c5-144">Se necessario, usare un browser sul computer locale e accedere all'interfaccia di amministrazione (<https://admin.microsoft.com>) con l'account amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-144">If needed, use a browser on your local computer and sign in to the admin center (<https://admin.microsoft.com>) using your global administrator account.</span></span>

2. <span data-ttu-id="4e5c5-145">Nell'elenco dei riquadri fare clic su **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-145">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="4e5c5-146">Nella nuova scheda **SharePoint** del browser fare clic su + **Crea sito**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-146">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>

4. <span data-ttu-id="4e5c5-147">Nella pagina **Crea sito** fare clic su **Sito del team**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-147">On the **Create a site** page, click **Team site**.</span></span>

5. <span data-ttu-id="4e5c5-148">In **Nome sito**, digitare **Campagna su vasta scala**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-148">In **Site name**, type **Campaign wide**.</span></span>

6. <span data-ttu-id="4e5c5-149">In **Descrizione sito del team**, digitare **Sito di SharePoint per l'intera campagna**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-149">In **Team site description**, type **SharePoint site for the entire campaign**.</span></span>

7. <span data-ttu-id="4e5c5-150">In **Impostazioni privacy** selezionare **Public – anyone in the organization can access this site** (Pubblico: qualsiasi persona dell'organizzazione può accedere a questo sito) e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-150">In **Privacy settings**, select **Public - anyone in the organization can access this site**, and then click **Next**.</span></span>

8. <span data-ttu-id="4e5c5-151">Nel riquadro **Who do you want to add?** (Chi si desidera aggiungere?) fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-151">On the **Who do you want to add?** pane, click **Finish**.</span></span>

<span data-ttu-id="4e5c5-152">Successivamente, configurare la cartella dei documenti del sito del team Campagna su vasta scala per l'etichetta Interno.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-152">Next, configure the documents folder of the Campaign wide team site for the Internal label.</span></span>

1. <span data-ttu-id="4e5c5-153">Nella scheda **Campagna su vasta scala – Home** del browser, fare clic su **Documenti**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-153">In the **Campaign wide-Home** tab of your browser, click **Documents**.</span></span>

2. <span data-ttu-id="4e5c5-154">Fare clic sull'icona delle impostazioni e selezionare **Impostazioni libreria**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-154">Click the settings icon, and then click **Library settings**.</span></span>

3. <span data-ttu-id="4e5c5-155">In **Autorizzazioni e gestione** fare clic su **Apply label to items in this library** (Applica etichetta agli elementi in questa libreria).</span><span class="sxs-lookup"><span data-stu-id="4e5c5-155">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>

4. <span data-ttu-id="4e5c5-156">In **Impostazioni - Applica etichetta**, selezionare **Interno** e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-156">In **Settings-Apply Label**, select **Internal**, and then click **Save**.</span></span>

### <a name="campaign-project-1-team-site"></a><span data-ttu-id="4e5c5-157">Sito del team 1 del progetto della campagna</span><span class="sxs-lookup"><span data-stu-id="4e5c5-157">Campaign project 1 team site</span></span>

<span data-ttu-id="4e5c5-158">Per creare un sito del team di SharePoint Online privato di base per un progetto all'interno della campagna, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4e5c5-158">To create a baseline private SharePoint Online team site for a project within the campaign, do the following:</span></span>

1. <span data-ttu-id="4e5c5-159">Se necessario, usare un browser sul computer locale e accedere all'interfaccia di amministrazione (<https://admin.microsoft.com>) con l'account amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-159">If needed, use a browser on your local computer and sign in to the admin center (<https://admin.microsoft.com>) using your global administrator account.</span></span>

2. <span data-ttu-id="4e5c5-160">Nell'elenco dei riquadri fare clic su **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-160">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="4e5c5-161">Nella nuova scheda **SharePoint** del browser fare clic su + **Crea sito**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-161">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>

4. <span data-ttu-id="4e5c5-162">Nella pagina **Crea sito** fare clic su **Sito del team**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-162">On the **Create a site** page, click **Team site**.</span></span>

5. <span data-ttu-id="4e5c5-163">In **Nome sito**, digitare **Progetto della campagna 1**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-163">In **Site name**, type **Campaign project 1**.</span></span>

6. <span data-ttu-id="4e5c5-164">In **Descrizione sito del team**, digitare **Sito di SharePoint per il progetto della campagna 1**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-164">In **Team site description,** type **SharePoint site for Campaign project 1**.</span></span>

7. <span data-ttu-id="4e5c5-165">In **Impostazioni privacy** selezionare **Private - only members can access this site** (Privato: solo i membri possono accedere a questo sito) e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-165">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>

8. <span data-ttu-id="4e5c5-166">Nel riquadro **Who do you want to add?** (Chi si desidera aggiungere?) fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-166">On the **Who do you want to add?** pane, click **Finish**.</span></span>

<span data-ttu-id="4e5c5-167">Successivamente, configurare la cartella dei documenti del sito del team Progetto della campagna 1 per l'etichetta Privato.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-167">Next, configure the documents folder of the Campaign project 1 team site for the Private label.</span></span>

1. <span data-ttu-id="4e5c5-168">Nella scheda **Progetto della campagna 1 – Home** del browser, fare clic su **Documenti**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-168">In the **Campaign project 1-Home** tab of your browser, click **Documents**.</span></span>

2. <span data-ttu-id="4e5c5-169">Fare clic sull'icona delle impostazioni e selezionare **Impostazioni libreria**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-169">Click the settings icon, and then click **Library settings**.</span></span>

3. <span data-ttu-id="4e5c5-170">In **Autorizzazioni e gestione** fare clic su **Apply label to items in this library** (Applica etichetta agli elementi in questa libreria).</span><span class="sxs-lookup"><span data-stu-id="4e5c5-170">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>

4. <span data-ttu-id="4e5c5-171">In **Impostazioni - Applica etichetta**, selezionare **Privato** e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-171">In **Settings-Apply Label**, select **Private**, and then click **Save**.</span></span>

### <a name="campaign-marketing-team-site"></a><span data-ttu-id="4e5c5-172">Sito del team per il marketing della campagna</span><span class="sxs-lookup"><span data-stu-id="4e5c5-172">Campaign marketing team site</span></span>

<span data-ttu-id="4e5c5-173">Per creare un sito del team di SharePoint Online isolato riservato per le risorse marketing della campagna, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4e5c5-173">To create a sensitive-level isolated SharePoint Online team site for campaign marketing resources, do the following:</span></span>

1. <span data-ttu-id="4e5c5-174">Usando un browser nel computer locale, accedere all'interfaccia di amministrazione (<https://admin.microsoft.com>) con l'account amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-174">Using a browser on your local computer, sign in to the admin center (<https://admin.microsoft.com>) using your global administrator account.</span></span>

2. <span data-ttu-id="4e5c5-175">Nell'elenco dei riquadri fare clic su **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-175">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="4e5c5-176">Nella nuova scheda **SharePoint** del browser fare clic su + **Crea sito**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-176">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>

4. <span data-ttu-id="4e5c5-177">Nella pagina **Crea sito** fare clic su **Sito del team**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-177">On the **Create a site** page, click **Team site**.</span></span>

5. <span data-ttu-id="4e5c5-178">In **Nome sito del team**, digitare **Marketing della campagna**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-178">In **Team site name**, type **Campaign marketing**.</span></span>

6. <span data-ttu-id="4e5c5-179">In **Descrizione sito del team**, digitare **Sito di SharePoint per il marketing della campagna (riservato)**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-179">In **Team site description**, type **SharePoint site for campaign marketing (sensitive)**.</span></span>

7. <span data-ttu-id="4e5c5-180">In **Impostazioni privacy** selezionare **Private - only members can access this site** (Privato: solo i membri possono accedere a questo sito) e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-180">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>

8. <span data-ttu-id="4e5c5-181">Nel riquadro **Who do you want to add?** (Chi si desidera aggiungere?) fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-181">On the **Who do you want to add?** pane, click **Finish**.</span></span>

9. <span data-ttu-id="4e5c5-182">Nella nuova scheda **Marketing della campagna** visualizzata nel browser, nella barra degli strumenti fare clic sull'icona delle impostazioni, quindi su **Autorizzazioni sito**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-182">On the new **Campaign marketing** tab in your browser, in the tool bar, click the settings icon, and then click **Site permissions**.</span></span>

10. <span data-ttu-id="4e5c5-183">Nel riquadro **Autorizzazioni sito** fare clic su **Advanced permissions settings** (Impostazioni autorizzazioni avanzate).</span><span class="sxs-lookup"><span data-stu-id="4e5c5-183">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>

11. <span data-ttu-id="4e5c5-184">Nella nuova scheda **Autorizzazioni** del browser fare clic su **Impostazioni richieste di accesso**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-184">In the new **Permissions** tab in your browser, click **Access Request Settings**.</span></span>

12. <span data-ttu-id="4e5c5-185">Nella finestra di dialogo **Impostazioni richieste di accesso**, deselezionare le caselle di controllo **Consenti ai membri di condividere il sito e singoli file e cartelle** e **Consenti ai membri di invitare altre persone nel gruppo di membri del sito**, digitare **ITAdmin1@**\<your organization name\> **.onmicrosoft.com** in **Invia tutte le richieste di accesso**, poi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-185">In the **Access Request Settings** dialog box, clear the **Allow members to share the site and individual files and folders** and **Allow members to invite others to the site members group** check boxes, type **ITAdmin1@**\<your organization name\>**.onmicrosoft.com** in **Send all requests for access**, and then click **OK**.</span></span>

13. <span data-ttu-id="4e5c5-186">Fare clic su **Membri marketing della campagna** nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-186">Click **Campaign marketing Members** in the list.</span></span>

14. <span data-ttu-id="4e5c5-187">Nella pagina **Utenti e gruppi** fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-187">On the **People and Groups** page, click **New**.</span></span>

15. <span data-ttu-id="4e5c5-188">Nella finestra di dialogo **Condividi**, digitare **Staff senior e strategico**, selezionarlo e quindi fare clic su **Condividi**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-188">In the **Share** dialog box, type **Senior and strategic staff**, select it, and then click **Share**.</span></span>

16. <span data-ttu-id="4e5c5-189">Ripetere i passaggi 14 e 15 per il gruppo **Staff di analisi** e per l'account utente **Regolare1**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-189">Repeat steps 14 and 15 for the **Analytics staff** group and the **Regular1** user account.</span></span>

17. <span data-ttu-id="4e5c5-190">Fare clic sul pulsante Indietro del browser.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-190">Click the back button on your browser.</span></span>

18. <span data-ttu-id="4e5c5-191">Fare clic su **Proprietari marketing della campagna** nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-191">Click **Campaign marketing Owners** in the list.</span></span>

19. <span data-ttu-id="4e5c5-192">Nella pagina **Utenti e gruppi** fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-192">On the **People and Groups** page, click **New**.</span></span>

20. <span data-ttu-id="4e5c5-193">Nella finestra di dialogo **Condividi**, digitare **Staff IT**, selezionarlo e quindi fare clic su **Condividi**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-193">In the **Share** dialog box, type **IT staff**, select it, and then click **Share**.</span></span>

21. <span data-ttu-id="4e5c5-194">Fare clic sul pulsante Indietro del browser.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-194">Click the back button on your browser.</span></span>

22. <span data-ttu-id="4e5c5-195">Chiudere la scheda **Utenti e gruppi** visualizzata nel browser, fare clic sulla scheda **Marketing della campagna-Home**, quindi chiudere il riquadro **Autorizzazioni sito**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-195">Close the **People and Groups** tab in your browser, click the **Campaign marketing-Home** tab in your browser, and then close the **Site permissions** pane.</span></span>

<span data-ttu-id="4e5c5-196">Ecco i risultati della configurazione delle autorizzazioni:</span><span class="sxs-lookup"><span data-stu-id="4e5c5-196">Here are the results of configuring permissions:</span></span>

- <span data-ttu-id="4e5c5-197">Il gruppo **Marketing della campagna-Membri** di SharePoint contiene solo il gruppo **Staff senior e strategico** (che include gli account utente Candidato, Capodellostaff e Strategico1), il gruppo **Marketing della campagna** (che include l'account utente di amministratore globale),il gruppo **Staff di analisi** (che include l'account utente DataScientist1) e l'account utente **Regolare1**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-197">The **Campaign marketing-Members** SharePoint group contains only the **Senior and strategic staff** group (which contains the Candidate, ChiefOfStaff, and Strategic1 user accounts), the **Campaign marketing** group (which contains the global administrator user account), the **Analytics staff** group (which contains the DataScientist1 user account), and the **Regular1** user account.</span></span>

- <span data-ttu-id="4e5c5-198">Il gruppo **Marketing della campagna-Proprietari** di SharePoint contiene solo il gruppo **Staff IT** (che include solo gli account utente ITAdmin1 e ITAdmin2).</span><span class="sxs-lookup"><span data-stu-id="4e5c5-198">The **Campaign marketing-Owners** SharePoint group contains only the **IT staff** group (which contains only the ITAdmin1 and ITAdmin2 user accounts).</span></span>

- <span data-ttu-id="4e5c5-199">Il gruppo **Marketing della campagna-Visitatori** di SharePoint non contiene gruppi o account utente.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-199">The **Campaign marketing-Visitors** SharePoint group contains no groups or user accounts.</span></span>

- <span data-ttu-id="4e5c5-200">I membri non possono modificare le autorizzazioni a livello del sito (ciò può essere fatto solo dai membri del gruppo **Marketing della campagna-Proprietari**).</span><span class="sxs-lookup"><span data-stu-id="4e5c5-200">Members cannot modify site-level permissions (this can only be done by members of the **Campaign marketing-Owners** group).</span></span>

- <span data-ttu-id="4e5c5-201">Altri account utente non possono accedere al sito o alle sue risorse, ma possono richiedere l'accesso al sito, che invierà un'e-mail alla cassetta postale dell'account utente ITAdmin1.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-201">Other user accounts cannot access the site or its resources, but can request access to the site, which will send an email to the ITAdmin1 user account mailbox.</span></span>

<span data-ttu-id="4e5c5-202">Successivamente, configurare la cartella dei documenti del sito del team Marketing della campagna per l'etichetta Riservato.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-202">Next, configure the documents folder of the Campaign marketing team site for the Sensitive label.</span></span>

1. <span data-ttu-id="4e5c5-203">Nella scheda **Marketing della campagna–Home** del browser, fare clic su **Documenti**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-203">In the **Campaign marketing-Home** tab of your browser, click **Documents**.</span></span>

2. <span data-ttu-id="4e5c5-204">Fare clic sull'icona delle impostazioni e selezionare **Impostazioni libreria**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-204">Click the settings icon, and then click **Library settings**.</span></span>

3. <span data-ttu-id="4e5c5-205">In **Autorizzazioni e gestione** fare clic su **Apply label to items in this library** (Applica etichetta agli elementi in questa libreria).</span><span class="sxs-lookup"><span data-stu-id="4e5c5-205">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>

4. <span data-ttu-id="4e5c5-206">In **Impostazioni - Applica etichetta**, selezionare **Riservato** e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-206">In **Settings-Apply Label**, select **Sensitive**, and then click **Save**.</span></span>

<span data-ttu-id="4e5c5-p106">Configurare quindi un criterio di prevenzione della perdita di dati che informa gli utenti quando condividono un documento presente su un sito del team di SharePoint Online con etichetta Sensibile al di fuori dell'organizzazione. Questo criterio di prevenzione della perdita di dati verrà applicato alle risorse nel sito marketing della campagna.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-p106">Next, configure a data loss prevention (DLP) policy that notifies users when they share a document on a SharePoint Online team site with the Sensitive label outside the organization. This DLP policy will apply to resources in the Campaign marketing site.</span></span>

1. <span data-ttu-id="4e5c5-209">Dalla scheda **Microsoft Office Home** del browser, fare clic sul riquadro **Sicurezza e conformità**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-209">From the **Microsoft Office Home** tab in your browser, click the **Security & Compliance** tile.</span></span>

2. <span data-ttu-id="4e5c5-210">Nella nuova scheda **Sicurezza e conformità** del browser fare clic su **Prevenzione perdita dati > Criterio**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-210">On the new **Security & Compliance** tab in your browser, click **Data loss prevention > Policy**.</span></span>

3. <span data-ttu-id="4e5c5-211">Nel riquadro **Prevenzione della perdita di dati**, fare clic su **+ Crea un criterio**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-211">In the **Data loss prevention** pane, click **+ Create a policy**.</span></span>

4. <span data-ttu-id="4e5c5-212">Nel riquadro **Inizia con un modello o crea un criterio personalizzato**, fare clic su **Personalizza**, quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-212">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>

5. <span data-ttu-id="4e5c5-213">Nel riquadro **Denomina il criterio**, digitare **Siti del team di SharePoint Online con etichetta Riservato** in **Nome**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-213">In the **Name your policy** pane, type **Sensitive label SharePoint Online team sites** in **Name**, and then click **Next**.</span></span>

6. <span data-ttu-id="4e5c5-214">Nel riquadro **Choose locations** (Scegli posizioni) fare clic su **Let me choose specific locations** (Consenti di scegliere posizioni specifiche) e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-214">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>

7. <span data-ttu-id="4e5c5-215">Nell'elenco di località, disabilitare le località **Posta elettronica di Exchange** e **Account di OneDrive**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-215">In the list of locations, disable the **Exchange email** and **OneDrive accounts** locations, and then click **Next**.</span></span>

8. <span data-ttu-id="4e5c5-216">Nel riquadro **Customize the types of sensitive info you want to protect** (Personalizza i tipi di informazioni sensibili da proteggere) fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-216">In the **Customize the types of sensitive info you want to protect** pane, click **Edit**.</span></span>

9. <span data-ttu-id="4e5c5-217">Nel riquadro per **scegliere i tipi di contenuto da proteggere**, fare clic su **Aggiungi** nella casella di riepilogo a discesa, quindi fare clic su **Etichette**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-217">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Labels**.</span></span>

10. <span data-ttu-id="4e5c5-218">Nel riquadro **Etichette**, fare clic su **+ Aggiungi**, selezionare l’etichetta **Riservato** fare clic su **Aggiungi**, quindi fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-218">In the **Labels** pane, click **+ Add**, select the **Sensitive** label, click **Add**, and then click **Done**.</span></span>

11. <span data-ttu-id="4e5c5-219">Nel riquadro **Choose the types of content to protect** (Scegli i tipi di contenuto da proteggere) fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-219">In the **Choose the types of content to protect** pane, click **Save**.</span></span>

12. <span data-ttu-id="4e5c5-220">Nel riquadro **Customize the types of sensitive info you want to protect** (Personalizza i tipi di informazioni sensibili da proteggere) fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-220">In the **Customize the types of sensitive info you want to protect** pane, click **Next**.</span></span>

13. <span data-ttu-id="4e5c5-221">Nel riquadro **What do you want to do if we detect sensitive info?** (Selezionare come procedere in caso di informazioni sensibili rilevate) fare clic su **Customize the tip and email** (Personalizza suggerimento e messaggio di posta elettronica).</span><span class="sxs-lookup"><span data-stu-id="4e5c5-221">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>

14. <span data-ttu-id="4e5c5-222">Nel riquadro **Customize policy tips and email notifications** (Personalizza i suggerimenti per i criteri e le notifiche tramite posta elettronica) fare clic su **Customize the policy tip text** (Personalizza testo suggerimento per criterio).</span><span class="sxs-lookup"><span data-stu-id="4e5c5-222">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>

15. <span data-ttu-id="4e5c5-223">Nella casella di testo digitare o incollare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="4e5c5-223">In the text box, type or paste in the following:</span></span>

    - <span data-ttu-id="4e5c5-p107">Per condividere con un utente esterno all'organizzazione, scaricare il file e quindi aprirlo. Fare clic su File, Proteggi documento, Crittografa con password, quindi specificare una password complessa. Inviare la password in un'e-mail separata o con altri mezzi di comunicazione.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-p107">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>

16. <span data-ttu-id="4e5c5-227">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-227">Click **OK**.</span></span>

17. <span data-ttu-id="4e5c5-228">Nel riquadro **Quale operazione eseguire se vengono rilevate informazioni riservate?**, deselezionare la casella di testo per **bloccare la condivisione e limitare l'accesso al contenuto condiviso**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-228">In the **What do you want to do if we detect sensitive info?** pane, clear the **Block people from sharing, and restrict access to shared content** check box, and then click **Next**.</span></span>

18. <span data-ttu-id="4e5c5-229">Nel riquadro **Abilitare il criterio o eseguire prima un test?**, fare clic su **Sì, abilitarlo immediatamente**, quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-229">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>

19. <span data-ttu-id="4e5c5-230">Nel riquadro **Verifica le impostazioni** fare clic su **Crea** e quindi su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-230">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>

### <a name="campaign-strategy-team-site"></a><span data-ttu-id="4e5c5-231">Sito del team per la strategia della campagna</span><span class="sxs-lookup"><span data-stu-id="4e5c5-231">Campaign strategy team site</span></span>

<span data-ttu-id="4e5c5-232">Per creare un sito del team di SharePoint Online isolato al livello estremamente riservato per le risorse relative alla strategia della campagna, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4e5c5-232">To create an isolated SharePoint Online team site at the highly confidential level for campaign strategy resources, do the following:</span></span>

1. <span data-ttu-id="4e5c5-233">Se necessario, usare un browser sul computer locale e accedere all'interfaccia di amministrazione (<https://admin.microsoft.com>) con l'account amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-233">If needed, use a browser on your local computer and sign in to the admin center (<https://admin.microsoft.com>) using your global administrator account.</span></span>

2. <span data-ttu-id="4e5c5-234">Nell'elenco dei riquadri fare clic su **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-234">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="4e5c5-235">Nella nuova scheda **SharePoint** del browser fare clic su + **Crea sito**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-235">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>

4. <span data-ttu-id="4e5c5-236">Nella pagina **Crea sito** fare clic su **Sito del team**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-236">On the **Create a site** page, click **Team site**.</span></span>

5. <span data-ttu-id="4e5c5-237">In **Nome sito del team**, digitare **Strategia della campagna**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-237">In **Team site name**, type **Campaign strategy**.</span></span>

6. <span data-ttu-id="4e5c5-238">In **Descrizione sito del team**, digitare **Sito di SharePoint per la strategia della campagna (estremamente riservato)**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-238">In **Team site description**, type **SharePoint site for campaign strategy (highly confidential)**.</span></span>

7. <span data-ttu-id="4e5c5-239">In **Impostazioni privacy** selezionare **Private - only members can access this site** (Privato: solo i membri possono accedere a questo sito) e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-239">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>

8. <span data-ttu-id="4e5c5-240">Nel riquadro **Who do you want to add?** (Chi si desidera aggiungere?) fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-240">On the **Who do you want to add?** pane, click **Finish**.</span></span>

9. <span data-ttu-id="4e5c5-241">Nella nuova scheda **Strategia della campagna** visualizzata nel browser, nella barra degli strumenti fare clic sull'icona delle impostazioni, quindi su **Autorizzazioni sito**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-241">On the new **Campaign strategy** tab in your browser, in the tool bar, click the settings icon, and then click **Site permissions**.</span></span>

10. <span data-ttu-id="4e5c5-242">Nel riquadro **Autorizzazioni sito** fare clic su **Advanced permissions settings** (Impostazioni autorizzazioni avanzate).</span><span class="sxs-lookup"><span data-stu-id="4e5c5-242">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>

11. <span data-ttu-id="4e5c5-243">Nella nuova scheda **Autorizzazioni** del browser fare clic su **Impostazioni richieste di accesso**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-243">In the new **Permissions** tab in your browser, click **Access Request Settings**.</span></span>

12. <span data-ttu-id="4e5c5-244">Nella finestra di dialogo **Impostazioni richieste di accesso**, deselezionare **Consenti ai membri di condividere il sito e singoli file e cartelle** e **Consenti ai membri di invitare altre persone nel gruppo di membri del sito** (le tre caselle di controllo devono essere deselezionate), quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-244">In the **Access Request Settings** dialog box, clear **Allow members to share the site and individual files and folders** and **Allow members to invite others to the site members group** (so that all three check boxes are cleared), and then click **OK**.</span></span>

13. <span data-ttu-id="4e5c5-245">Fare clic su **Membri strategia della campagna** nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-245">Click **Campaign strategy Members** in the list.</span></span>

14. <span data-ttu-id="4e5c5-246">Nella pagina **Utenti e gruppi** fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-246">On the **People and Groups** page, click **New**.</span></span>

15. <span data-ttu-id="4e5c5-247">Nella finestra di dialogo **Condividi**, digitare **Staff senior e strategico**, selezionarlo e quindi fare clic su **Condividi**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-247">In the **Share** dialog box, type **Senior and strategic staff**, select it, and then click **Share**.</span></span>

16. <span data-ttu-id="4e5c5-248">Fare clic su **Proprietari strategia della campagna** nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-248">Click **Campaign strategy Owners** in the list.</span></span>

17. <span data-ttu-id="4e5c5-249">Nella pagina **Utenti e gruppi** fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-249">On the **People and Groups** page, click **New**.</span></span>

18. <span data-ttu-id="4e5c5-250">Nella finestra di dialogo **Condividi**, digitare **Staff IT**, selezionarlo e quindi fare clic su **Condividi**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-250">In the **Share** dialog box, type **IT staff**, select it, and then click **Share**.</span></span>

19. <span data-ttu-id="4e5c5-251">Fare clic sul pulsante Indietro del browser.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-251">Click the back button on your browser.</span></span>

20. <span data-ttu-id="4e5c5-252">Chiudere la scheda **Utenti e gruppi** visualizzata nel browser, fare clic sulla scheda **Strategia della campagna-Home**, quindi chiudere il riquadro **Autorizzazioni sito**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-252">Close the **People and Groups** tab in your browser, click the **Campaign strategy-Home** tab in your browser, and then close the **Site permissions** pane.</span></span>

<span data-ttu-id="4e5c5-253">Ecco i risultati della configurazione delle autorizzazioni:</span><span class="sxs-lookup"><span data-stu-id="4e5c5-253">Here are the results of configuring permissions:</span></span>

- <span data-ttu-id="4e5c5-254">Il gruppo **Strategia della campagna-Membri** di SharePoint contiene solo il gruppo **Staff senior e strategico** (che include solo gli account utente Candidato, Capodellostaff e Strategico1) e il gruppo **Strategia della campagna** (che include solo l'account utente di amministratore globale).
</span><span class="sxs-lookup"><span data-stu-id="4e5c5-254">The **Campaign strategy-Members** SharePoint group contains only the **Senior and strategic staff** group (which contains only the Candidate, ChiefOfStaff, and Strategic1 user accounts) and the **Campaign strategy** group (which contains only the global administrator user account).</span></span>

- <span data-ttu-id="4e5c5-255">Il gruppo **Strategia della campagna-Proprietari** di SharePoint contiene solo il gruppo **Staff IT** (che include solo gli account utente ITAdmin1 e ITAdmin2).</span><span class="sxs-lookup"><span data-stu-id="4e5c5-255">The **Campaign strategy-Owners** SharePoint group contains only the **IT staff** group (which contains only the ITAdmin1 and ITAdmin2 user accounts).</span></span>

- <span data-ttu-id="4e5c5-256">Il gruppo **Strategia della campagna-Visitatori** di SharePoint non contiene gruppi o account utente.	</span><span class="sxs-lookup"><span data-stu-id="4e5c5-256">The **Campaign strategy-Visitors** SharePoint group contains no groups or user accounts.</span></span>

- <span data-ttu-id="4e5c5-257">I membri non possono modificare le autorizzazioni a livello del sito (ciò può essere fatto solo dai membri del gruppo **Strategia della campagna-Proprietari**).</span><span class="sxs-lookup"><span data-stu-id="4e5c5-257">Members cannot modify site-level permissions (this can only be done by members of the **Campaign strategy-Owners** group).</span></span>

- <span data-ttu-id="4e5c5-p108">Altri account utente non possono accedere al sito e alle relative risorse o richiedere l'accesso al sito. Ulteriori autorizzazioni per il sito devono essere effettuate dall'amministratore globale o da un membro del gruppo **Strategia della campagna-Proprietari**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-p108">Other user accounts cannot access the site or its resources or request access to the site. Additional permissions to the site must be done by the global administrator or by a member of the **Campaign strategy-Owners** group.</span></span>

<span data-ttu-id="4e5c5-260">Successivamente, configurare la cartella dei documenti del sito del team Strategia della campagna per l'etichetta Estremamente riservato.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-260">Next, configure the documents folder of the Campaign strategy team site for the Highly Confidential label.</span></span>

1. <span data-ttu-id="4e5c5-261">Nella scheda **Strategia della campagna–Home** del browser, fare clic su **Documenti**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-261">In the **Campaign strategy-Home** tab of your browser, click **Documents**.</span></span>

2. <span data-ttu-id="4e5c5-262">Fare clic sull'icona delle impostazioni e selezionare **Impostazioni libreria**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-262">Click the settings icon, and then click **Library settings**.</span></span>

3. <span data-ttu-id="4e5c5-263">In **Autorizzazioni e gestione** fare clic su **Apply label to items in this library** (Applica etichetta agli elementi in questa libreria).</span><span class="sxs-lookup"><span data-stu-id="4e5c5-263">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>

4. <span data-ttu-id="4e5c5-264">In **Impostazioni - Applica etichetta**, selezionare **Estremamente riservato** e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-264">In **Settings-Apply Label**, select **Highly Confidential**, and then click **Save**.</span></span>

<span data-ttu-id="4e5c5-p109">Configurare quindi un criterio di prevenzione della perdita di dati che blocca gli utenti quando condividono un documento presente su un sito del team di SharePoint Online con etichetta Estremamente riservato al di fuori dell'organizzazione. Questo criterio di prevenzione della perdita di dati verrà applicato alle risorse nel sito della strategia della campagna.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-p109">Next, configure a DLP policy that blocks users when they share a document on a SharePoint Online team site with the Highly Confidential label outside the organization. This DLP policy will apply to resources in the Campaign strategy site.</span></span>

1. <span data-ttu-id="4e5c5-267">Se necessario, usare un browser nel computer locale e accedere all'interfaccia di amministrazione (<https://admin.microsoft.com>) con un account che dispone del ruolo Amministratore della sicurezza o Amministratore società.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-267">If needed, use a browser on your local computer and sign in to the admin center (<https://admin.microsoft.com>) with an account that has the Security Administrator or Company Administrator role.</span></span>

2. <span data-ttu-id="4e5c5-268">Dalla scheda **Microsoft Office Home** del browser, fare clic sul riquadro **Sicurezza e conformità**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-268">From the **Microsoft Office Home** tab in your browser, click the **Security & Compliance** tile.</span></span>

3. <span data-ttu-id="4e5c5-269">Nella nuova scheda **Sicurezza e conformità** del browser fare clic su **Prevenzione perdita dati > Criterio**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-269">On the new **Security & Compliance** tab in your browser, click **Data loss prevention > Policy**.</span></span>

4. <span data-ttu-id="4e5c5-270">Nel riquadro **Prevenzione della perdita di dati**, fare clic su **+ Crea un criterio**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-270">In the **Data loss prevention** pane, click **+ Create a policy**.</span></span>

5. <span data-ttu-id="4e5c5-271">Nel riquadro **Inizia con un modello o crea un criterio personalizzato**, fare clic su **Personalizza**, quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-271">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>

6. <span data-ttu-id="4e5c5-272">Nel riquadro **Denomina il criterio**, digitare **Siti del team di SharePoint Online con etichetta Estremamente riservato** in **Nome**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-272">In the **Name your policy** pane, type **Highly Confidential label SharePoint Online team sites** in **Name**, and then click **Next**.</span></span>

7. <span data-ttu-id="4e5c5-273">Nel riquadro **Choose locations** (Scegli posizioni) fare clic su **Let me choose specific locations** (Consenti di scegliere posizioni specifiche) e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-273">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>

8. <span data-ttu-id="4e5c5-274">Nell'elenco di località, disabilitare le località **Posta elettronica di Exchange** e **Account di OneDrive**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-274">In the list of locations, disable the **Exchange email** and **OneDrive accounts** locations, and then click **Next**.</span></span>

9. <span data-ttu-id="4e5c5-275">Nel riquadro **Customize the types of sensitive info you want to protect** (Personalizza i tipi di informazioni sensibili da proteggere) fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-275">In the **Customize the types of sensitive info you want to protect** pane, click **Edit**.</span></span>

10. <span data-ttu-id="4e5c5-276">Nel riquadro per **scegliere i tipi di contenuto da proteggere**, fare clic su **Aggiungi** nella casella di riepilogo a discesa, quindi fare clic su **Etichette**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-276">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Labels**.</span></span>

11. <span data-ttu-id="4e5c5-277">Nel riquadro **Etichette**, fare clic su **+ Aggiungi**, selezionare l’etichetta **Estremamente riservato**, fare clic su **Aggiungi**, quindi fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-277">In the **Labels** pane, click **+ Add**, select the **Highly Confidential** label, click **Add**, and then click **Done**.</span></span>

12. <span data-ttu-id="4e5c5-278">Nel riquadro **Choose the types of content to protect** (Scegli i tipi di contenuto da proteggere) fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-278">In the **Choose the types of content to protect** pane, click **Save**.</span></span>

13. <span data-ttu-id="4e5c5-279">Nel riquadro **Customize the types of sensitive info you want to protect** (Personalizza i tipi di informazioni sensibili da proteggere) fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-279">In the **Customize the types of sensitive info you want to protect** pane, click **Next**.</span></span>

14. <span data-ttu-id="4e5c5-280">Nel riquadro **What do you want to do if we detect sensitive info?** (Selezionare come procedere in caso di informazioni sensibili rilevate) fare clic su **Customize the tip and email** (Personalizza suggerimento e messaggio di posta elettronica).</span><span class="sxs-lookup"><span data-stu-id="4e5c5-280">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>

15. <span data-ttu-id="4e5c5-281">Nel riquadro **Customize policy tips and email notifications** (Personalizza i suggerimenti per i criteri e le notifiche tramite posta elettronica) fare clic su **Customize the policy tip text** (Personalizza testo suggerimento per criterio).</span><span class="sxs-lookup"><span data-stu-id="4e5c5-281">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>

16. <span data-ttu-id="4e5c5-282">Nella casella di testo digitare o incollare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="4e5c5-282">In the text box, type or paste in the following:</span></span>

    - <span data-ttu-id="4e5c5-p110">Per condividere con un utente esterno all'organizzazione, scaricare il file e quindi aprirlo. Fare clic su File, Proteggi documento, Crittografa con password, quindi specificare una password complessa. Inviare la password in un'e-mail separata o con altri mezzi di comunicazione.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-p110">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>

17. <span data-ttu-id="4e5c5-286">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-286">Click **OK**.</span></span>

18. <span data-ttu-id="4e5c5-287">Nel riquadro **Quale operazione eseguire se vengono rilevate informazioni riservate?**, selezionare l’opzione per **richiedere motivazioni aziendali per eseguire l'override**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-287">In the **What do you want to do if we detect sensitive info?** pane, select **Require a business justification to override**, and then click **Next**.</span></span>

19. <span data-ttu-id="4e5c5-288">Nel riquadro **Abilitare il criterio o eseguire prima un test?**, fare clic su **Sì, abilitarlo immediatamente**, quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-288">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>

20. <span data-ttu-id="4e5c5-289">Nel riquadro **Verifica le impostazioni** fare clic su **Crea** e quindi su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-289">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>

<span data-ttu-id="4e5c5-290">Seguire le istruzioni in [Attivare Azure RMS dall'interfaccia di amministrazione di Microsoft 365](/information-protection/deploy-use/activate-office365).</span><span class="sxs-lookup"><span data-stu-id="4e5c5-290">Use the instructions in [Activate Azure RMS with the Microsoft 365 admin center](/information-protection/deploy-use/activate-office365).</span></span>

<span data-ttu-id="4e5c5-291">Configurare quindi Azure Information Protection con un nuovo criterio con ambito e un'etichetta secondaria per la protezione e le autorizzazioni eseguendo le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4e5c5-291">Next, configure Azure Information Protection with a new scoped policy and sub-label for protection and permissions with the following steps:</span></span>

1. <span data-ttu-id="4e5c5-p111">Accedere all'interfaccia di amministrazione con un account che dispone del ruolo di amministratore della sicurezza oppure di amministratore aziendale. Per informazioni, vedere [Dove accedere a Office 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="4e5c5-p111">Sign in to the admin center with an account that has the Security Administrator or Company Administrator role. For help, see [Where to sign in to Office 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>

2. <span data-ttu-id="4e5c5-294">In un'altra scheda del browser, accedere al portale di Azure (<https://portal.azure.com>).</span><span class="sxs-lookup"><span data-stu-id="4e5c5-294">In a separate tab of your browser, go to the Azure portal (<https://portal.azure.com>).</span></span>

3. <span data-ttu-id="4e5c5-295">Nel riquadro di ricerca digitare **Informazioni** e quindi fare clic su **Azure Information Protection**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-295">In the search pane, type **information**, and then click **Azure Information Protection**.</span></span>

4. <span data-ttu-id="4e5c5-296">Fare clic su **Etichette**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-296">Click **Labels**.</span></span>

5. <span data-ttu-id="4e5c5-297">Fare clic con il pulsante destro del mouse sull'etichetta **Estremamente riservato**, quindi su **Aggiungi un'etichetta secondaria**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-297">Right-click the **Highly Confidential** label, and then click **Add a sub-label**.</span></span>

6. <span data-ttu-id="4e5c5-298">Digitare **CompanyStrategy** in **Nome** ed **Etichetta per i documenti nel sito del team di strategia aziendale** in **Descrizione**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-298">Type **CampaignStrategy** in **Name** and **Label for documents in the Campaign strategy team site** in **Description**.</span></span>

7. <span data-ttu-id="4e5c5-299">In **Configurare le autorizzazioni per documenti e messaggi di posta elettronica contenenti questa etichetta** fare clic su **Proteggi**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-299">In **Set permissions for documents and emails containing this label**, click **Protect**.</span></span>

8. <span data-ttu-id="4e5c5-300">Nella sezione **Protezione** fare clic su **Azure (chiave cloud)**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-300">In the **Protection** section, click **Azure (cloud key)**.</span></span>

9. <span data-ttu-id="4e5c5-301">Nel pannello **Protezione** fare clic su **+ Aggiungi autorizzazioni** in **Impostazioni di protezione**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-301">On the **Protection** blade, under **Protection settings**, click **+ Add permissions**.</span></span>

10. <span data-ttu-id="4e5c5-302">Nel pannello **Aggiungi autorizzazioni**, in **Specifica utenti e gruppi** fare clic su **+ Sfoglia la directory**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-302">On the **Add permissions** blade, under **Specify users and groups**, click **+ Browse directory**.</span></span>

11. <span data-ttu-id="4e5c5-303">Nel riquadro **Utenti e gruppi di AAD**, selezionare **Personale senior e strategico** e quindi fare clic su **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-303">On the **AAD Users and Groups** pane, select **Senior and strategic staff**, and then click **Select**.</span></span>

12. <span data-ttu-id="4e5c5-304">In **Scegliere le autorizzazioni dal set di impostazioni o imposta personalizzato** fare clic su **Personalizza**, quindi sulla casella **Visualizza diritti**, **Modifica contenuto**, **Salva**, **Rispondi** e **Rispondi a tutti**</span><span class="sxs-lookup"><span data-stu-id="4e5c5-304">Under **Choose permissions from the preset or set custom**, click **Custom**, and then click the **View Rights**, **Edit Content**, **Save**, **Reply**, and **Reply all** check boxes.</span></span>

13. <span data-ttu-id="4e5c5-305">Fare due volte clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-305">Click **OK** twice.</span></span>

14. <span data-ttu-id="4e5c5-306">Nel pannello **Etichetta secondaria** fare clic su **Salva**, quindi su **OK**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-306">On the **Sub-label** blade, click **Save**, and then click **OK**.</span></span>

15. <span data-ttu-id="4e5c5-307">Nel pannello **Azure Information Protection** fare clic su **Criteri > + Aggiungi un nuovo criterio**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-307">On the **Azure Information protection** blade, click **Policies > + Add a new policy**.</span></span>

16. <span data-ttu-id="4e5c5-308">Digitare **CompanyStrategy** in **Nome** e **Documenti nel sito del team di strategia aziendale** in **Descrizione**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-308">Type **CampaignStrategy** in **Name** and **Documents in the Campaign strategy team site** in **Description**.</span></span>

17. <span data-ttu-id="4e5c5-309">Fare clic su **Selezionare gli utenti o i gruppi a cui viene applicato il criterio > Utenti/Gruppi**, quindi selezionare **Personale senior e strategico**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-309">Click **Select which users or groups get this policy > User/Groups**, and then select **Senior and strategic staff**.</span></span>

18. <span data-ttu-id="4e5c5-310">Fare clic su **Seleziona \> OK**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-310">Click **Select \> OK**.</span></span>

19. <span data-ttu-id="4e5c5-p112">Fare clic su **Aggiungi o rimuovi etichette**. Nel riquadro **Criteri: Aggiungere o rimuovere etichette** fare clic su **CampaignStrategy**, quindi su **OK**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-p112">Click **Add or remove labels**. In the **Policy: Add or remove labels** pane, click **CampaignStrategy**, and then click **OK**.</span></span>

20. <span data-ttu-id="4e5c5-313">Fare clic su **Salva**, quindi su **OK**.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-313">Click **Save**, and then click **OK**.</span></span>

<span data-ttu-id="4e5c5-314">Ora è possibile iniziare a creare documenti in questi quattro siti e a testare l'accesso a tali siti con vari account utente.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-314">You are now ready to begin creating documents in these four sites and test access to them with various user accounts.</span></span>

<span data-ttu-id="4e5c5-315">Per proteggere un documento con Azure Information Protection e la nuova etichetta, è necessario [installare il client di Azure Information Protection](/information-protection/rms-client/install-client-app) in un computer di test, installare Office dall'interfaccia di amministrazione e quindi accedere da Microsoft Word con un account del gruppo **Personale senior e strategico** dell'abbonamento di valutazione.</span><span class="sxs-lookup"><span data-stu-id="4e5c5-315">To protect a document with Azure Information Protection and this new label, you must [install the Azure Information Protection client](/information-protection/rms-client/install-client-app) on a test machine, install Office from the admin center, and then sign in from Microsoft Word with an account in the **Senior and strategic staff** group of your trial subscription.</span></span>

## <a name="see-also"></a><span data-ttu-id="4e5c5-316">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4e5c5-316">See Also</span></span>

[<span data-ttu-id="4e5c5-317">Guida sulla sicurezza Microsoft per organizzazioni che si occupano della campagna politica, no profit e altre organizzazioni Agile</span><span class="sxs-lookup"><span data-stu-id="4e5c5-317">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)

[<span data-ttu-id="4e5c5-318">Configurare gruppi e utenti per un ambiente di sviluppo/testing per la campagna politica</span><span class="sxs-lookup"><span data-stu-id="4e5c5-318">Configure groups and users for a political campaign dev/test environment</span></span>](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md)

[<span data-ttu-id="4e5c5-319">Guida al lab test (TLG) per adozione del cloud</span><span class="sxs-lookup"><span data-stu-id="4e5c5-319">Cloud adoption Test Lab Guides (TLGs)</span></span>](../../enterprise/cloud-adoption-test-lab-guides-tlgs.md)

[<span data-ttu-id="4e5c5-320">Centro soluzioni e architetture di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4e5c5-320">Microsoft 365 solution and architecture center</span></span>](../../solutions/index.yml)