---
title: Configurare Advanced eDiscovery in Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-ediscovery
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: In questo articolo viene descritto come configurare Advanced eDiscovery per iniziare a creare e gestire i casi. Vengono inoltre descritte le sottoscrizioni e le licenze Microsoft necessarie. Dopo aver completato alcuni passaggi rapidi, lo strumento Advanced eDiscovery è pronto per l'uso.
ms.openlocfilehash: 29a220f36a55a04d1c1a24add03b2e013a5c60ba
ms.sourcegitcommit: 3d48e198e706f22ac903b346cadda06b2368dd1e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/11/2021
ms.locfileid: "50727411"
---
# <a name="set-up-microsoft-365-advanced-ediscovery"></a><span data-ttu-id="aa0dc-105">Configurare Microsoft 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="aa0dc-105">Set up Microsoft 365 Advanced eDiscovery</span></span>

<span data-ttu-id="aa0dc-106">Advanced eDiscovery in Microsoft 365 offre un flusso di lavoro [end-to-end](overview-ediscovery-20.md#advanced-ediscovery-workflow) per conservare, raccogliere, esaminare, analizzare ed esportare i dati in grado di rispondere alle indagini interne ed esterne dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="aa0dc-106">Advanced eDiscovery in Microsoft 365 provides an [end-to-end workflow](overview-ediscovery-20.md#advanced-ediscovery-workflow) to preserve, collect, review, analyze, and export data that's responsive to your organization's internal and external investigations.</span></span> <span data-ttu-id="aa0dc-107">Non è necessario distribuire Advanced eDiscovery, ma esistono alcune attività preliminari che un amministratore IT e un manager di eDiscovery devono completare prima che l'organizzazione possa iniziare a creare e utilizzare casi di eDiscovery avanzati per gestire le indagini.</span><span class="sxs-lookup"><span data-stu-id="aa0dc-107">Nothing is needed to deploy Advanced eDiscovery, but there are some prerequisite tasks that an IT admin and eDiscovery manager have to complete before your organization can start to create and use Advanced eDiscovery cases to manage your investigations.</span></span>

<span data-ttu-id="aa0dc-108">In questo articolo vengono illustrati i passaggi necessari per configurare Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="aa0dc-108">This article discusses the steps necessary to set up Advanced eDiscovery.</span></span> <span data-ttu-id="aa0dc-109">Ciò include la garanzia delle licenze appropriate necessarie per accedere a Advanced eDiscovery e aggiungere i custodi ai casi e l'assegnazione delle autorizzazioni al team legale e di indagine in modo che possano accedere e gestire i casi.</span><span class="sxs-lookup"><span data-stu-id="aa0dc-109">This includes ensuring the proper licensing required to access Advanced eDiscovery and add custodians to cases, and assigning permissions to your legal and investigation team so they can access and manage cases.</span></span>

## <a name="step-1-verify-and-assign-appropriate-licenses"></a><span data-ttu-id="aa0dc-110">Passaggio 1: Verificare e assegnare licenze appropriate</span><span class="sxs-lookup"><span data-stu-id="aa0dc-110">Step 1: Verify and assign appropriate licenses</span></span>

<span data-ttu-id="aa0dc-111">Le licenze per Advanced eDiscovery richiedono l'abbonamento all'organizzazione appropriato e le licenze per utente.</span><span class="sxs-lookup"><span data-stu-id="aa0dc-111">Licensing for Advanced eDiscovery requires the appropriate organization subscription and per-user licensing.</span></span>

- <span data-ttu-id="aa0dc-112">**Sottoscrizione organizzazione:** Per accedere a Advanced eDiscovery nel Centro conformità Microsoft 365 o nel Centro sicurezza e conformità &, l'organizzazione deve disporre di uno degli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="aa0dc-112">**Organization subscription:** To access Advanced eDiscovery in the Microsoft 365 compliance center or the Security & Compliance Center, your organization must have one of the following:</span></span>

  - <span data-ttu-id="aa0dc-113">Abbonamento a Microsoft 365 E5 o a Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="aa0dc-113">Microsoft 365 E5 or Office 365 E5 subscription</span></span>
  
  - <span data-ttu-id="aa0dc-114">Abbonamento a Microsoft 365 E3 con il componente aggiuntivo E5 Compliance</span><span class="sxs-lookup"><span data-stu-id="aa0dc-114">Microsoft 365 E3 subscription with E5 Compliance add-on</span></span>

  - <span data-ttu-id="aa0dc-115">Abbonamento a Microsoft 365 E3 con il componente aggiuntivo eDiscovery e controllo di E5</span><span class="sxs-lookup"><span data-stu-id="aa0dc-115">Microsoft 365 E3 subscription with E5 eDiscovery and Audit add-on</span></span>

  <span data-ttu-id="aa0dc-116">Se non si dispone di un piano Microsoft 365 E5 esistente e si desidera provare Advanced eDiscovery, è possibile aggiungere [Microsoft 365](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) all'abbonamento esistente o iscriversi [per](https://www.microsoft.com/microsoft-365/enterprise) una versione di valutazione di Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="aa0dc-116">If you don't have an existing Microsoft 365 E5 plan and want to try Advanced eDiscovery, you can [add Microsoft 365](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) to your existing subscription or [sign up for a trial](https://www.microsoft.com/microsoft-365/enterprise) of Microsoft 365 E5.</span></span>

- <span data-ttu-id="aa0dc-117">**Licenze per utente:** Per aggiungere un utente come responsabile in un caso di Advance eDiscovery, a tale utente deve essere assegnata una delle licenze seguenti, a seconda dell'abbonamento all'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="aa0dc-117">**Per-user licensing:** To add a user as a custodian in an Advance eDiscovery case, that user must be assigned one of the following licenses, depending on your organization subscription:</span></span>

  - <span data-ttu-id="aa0dc-118">Microsoft 365: agli utenti deve essere assegnata una licenza di Microsoft 365 E5, una licenza del componente aggiuntivo Conformità E5 o una licenza del componente aggiuntivo E5 eDiscovery e controllo.</span><span class="sxs-lookup"><span data-stu-id="aa0dc-118">Microsoft 365: Users must be assigned a Microsoft 365 E5 license, an E5 Compliance add-on license, or an E5 eDiscovery and Audit add-on license.</span></span>

  - <span data-ttu-id="aa0dc-119">Office 365: agli utenti deve essere assegnata una licenza di Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="aa0dc-119">Office 365: Users must be assigned an Office 365 E5 license.</span></span>

   <span data-ttu-id="aa0dc-120">Per informazioni su come assegnare licenze, vedere [Assegnare licenze agli utenti.](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)</span><span class="sxs-lookup"><span data-stu-id="aa0dc-120">For information about how to assign licenses, see [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

> [!NOTE]
> <span data-ttu-id="aa0dc-121">Gli utenti necessitano solo di una licenza E5 (o della licenza del componente aggiuntivo appropriata) da aggiungere come custodi a un caso advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="aa0dc-121">Users only need an E5 license (or the appropriate add-on license) to be added as custodians to an Advanced eDiscovery case.</span></span> <span data-ttu-id="aa0dc-122">Gli amministratori IT, i responsabili di eDiscovery, gli avvocati, i paralegali o gli investigatori che utilizzano Advanced eDiscovery per gestire i casi e rivedere i dati dei casi non necessitano di una licenza E5 o di un componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="aa0dc-122">IT admins, eDiscovery managers, lawyers, paralegals, or investigators who use Advanced eDiscovery to manage cases and review case data don't need an E5 or add-on license.</span></span>

## <a name="step-2-assign-ediscovery-permissions"></a><span data-ttu-id="aa0dc-123">Passaggio 2: Assegnare le autorizzazioni di eDiscovery</span><span class="sxs-lookup"><span data-stu-id="aa0dc-123">Step 2: Assign eDiscovery permissions</span></span>

<span data-ttu-id="aa0dc-124">Per accedere a Advanced eDiscovery o essere stato aggiunto come membro di un caso advanced eDiscovery, a un utente devono essere assegnate le autorizzazioni appropriate.</span><span class="sxs-lookup"><span data-stu-id="aa0dc-124">To access Advanced eDiscovery or added as a member of an Advanced eDiscovery case, a user must be assigned the appropriate permissions.</span></span> <span data-ttu-id="aa0dc-125">In particolare, un utente deve essere aggiunto come membro del gruppo di ruoli Manager eDiscovery nel Centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="aa0dc-125">Specifically, a user must be added as a member of the eDiscovery Manager role group in the Security & Compliance Center.</span></span> <span data-ttu-id="aa0dc-126">I membri di questo gruppo di ruoli possono creare e gestire i casi di Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="aa0dc-126">Members of this role group can create and manage Advanced eDiscovery cases.</span></span> <span data-ttu-id="aa0dc-127">Possono aggiungere e rimuovere membri, mettere in attesa i custodi e i percorsi di contenuto, gestire le notifiche di blocco legale, creare e modificare le ricerche associate in un caso, aggiungere risultati di ricerca a un set di recensioni, analizzare i dati in un set di recensioni ed esportare e scaricare da un caso advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="aa0dc-127">They can add and remove members, place custodians and content locations on hold, manage legal hold notifications, create and edit searches associated in a case, add search results to a review set, analyze data in a review set, and export and download from an Advanced eDiscovery case.</span></span>

<span data-ttu-id="aa0dc-128">Completare la procedura seguente per aggiungere utenti al gruppo di ruoli Manager eDiscovery:</span><span class="sxs-lookup"><span data-stu-id="aa0dc-128">Complete the following steps to add users to the eDiscovery Manager role group:</span></span>

1. <span data-ttu-id="aa0dc-129">Accedere a e accedere utilizzando le credenziali per [https://protection.office.com/permissions](https://protection.office.com/permissions) un account amministratore nell'organizzazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="aa0dc-129">Go to [https://protection.office.com/permissions](https://protection.office.com/permissions) and sign in using the credentials for an admin account in your Microsoft 365 organization.</span></span>

2. <span data-ttu-id="aa0dc-130">Nella pagina **Autorizzazioni** selezionare il gruppo di ruoli **Manager eDiscovery.**</span><span class="sxs-lookup"><span data-stu-id="aa0dc-130">On the **Permissions** page, select the **eDiscovery Manager** role group.</span></span>

3. <span data-ttu-id="aa0dc-131">Nella pagina a comparsa Gestione eDiscovery fare clic su **Modifica** accanto alla sezione **Gestione eDiscovery.**</span><span class="sxs-lookup"><span data-stu-id="aa0dc-131">On the eDiscovery Manager flyout page, click **Edit** next to the **eDiscovery Manager** section.</span></span>

4. <span data-ttu-id="aa0dc-132">Nella pagina **Choose eDiscovery Manager** della procedura guidata edit role group fare clic **su Choose eDiscovery Manager.**</span><span class="sxs-lookup"><span data-stu-id="aa0dc-132">On the **Choose eDiscovery Manager** page in the edit role group wizard, click **Choose eDiscovery Manager**.</span></span>

5. <span data-ttu-id="aa0dc-133">Fare **clic su** Aggiungi, quindi selezionare la casella di controllo per tutti gli utenti che si desidera aggiungere al gruppo di ruoli.</span><span class="sxs-lookup"><span data-stu-id="aa0dc-133">Click **Add** then select the checkbox for all users you want to add to the role group.</span></span>

6. <span data-ttu-id="aa0dc-134">Fare **clic su** Aggiungi per aggiungere gli utenti selezionati e quindi fare clic su **Fine.**</span><span class="sxs-lookup"><span data-stu-id="aa0dc-134">Click **Add** to add the selected users, and then click **Done**.</span></span>

7. <span data-ttu-id="aa0dc-135">Fare **clic** su Salva per aggiungere gli utenti al gruppo di ruoli, quindi fare clic su **Chiudi** per completare il passaggio.</span><span class="sxs-lookup"><span data-stu-id="aa0dc-135">Click **Save** to add the users to the role group, and then click **Close** to complete the step.</span></span>

### <a name="more-information-about-the-ediscovery-manager-role-group"></a><span data-ttu-id="aa0dc-136">Ulteriori informazioni sul gruppo di ruoli Manager eDiscovery</span><span class="sxs-lookup"><span data-stu-id="aa0dc-136">More information about the eDiscovery Manager role group</span></span>

<span data-ttu-id="aa0dc-137">Esistono due sottogruppi nel gruppo di ruoli Manager eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="aa0dc-137">There are two subgroups in the eDiscovery Manager role group.</span></span> <span data-ttu-id="aa0dc-138">La differenza tra questi sottogruppi dipende dall'ambito.</span><span class="sxs-lookup"><span data-stu-id="aa0dc-138">The difference between these subgroups is based on scope.</span></span>

- <span data-ttu-id="aa0dc-139">**eDiscovery Manager:** Può visualizzare e gestire i casi di Advanced eDiscovery creati o di cui sono membri.</span><span class="sxs-lookup"><span data-stu-id="aa0dc-139">**eDiscovery Manager:** Can view and manage the Advanced eDiscovery cases they create or are a member of.</span></span> <span data-ttu-id="aa0dc-140">Se un altro responsabile di eDiscovery crea un caso ma non aggiunge un secondo responsabile di eDiscovery come membro di tale caso, il secondo gestore di eDiscovery non sarà in grado di visualizzare o aprire il caso nella pagina Advanced eDiscovery nel Centro conformità.</span><span class="sxs-lookup"><span data-stu-id="aa0dc-140">If another eDiscovery Manager creates a case but doesn't add a second eDiscovery Manager as a member of that case, the second eDiscovery Manager won't be able to view or open the case on the Advanced eDiscovery page in the compliance center.</span></span> <span data-ttu-id="aa0dc-141">In generale, la maggior parte degli utenti dell'organizzazione può essere aggiunta al sottogruppo Manager di eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="aa0dc-141">In general, most people in your organization can be added to the eDiscovery Manager subgroup.</span></span>

- <span data-ttu-id="aa0dc-142">**Amministratore di eDiscovery:** Può eseguire tutte le attività di gestione dei casi che possono essere eseguite da un responsabile di eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="aa0dc-142">**eDiscovery Administrator:** Can perform all case management tasks that an eDiscovery Manager can do.</span></span> <span data-ttu-id="aa0dc-143">Inoltre, un amministratore di eDiscovery è in grado di:</span><span class="sxs-lookup"><span data-stu-id="aa0dc-143">Additionally, an eDiscovery Administrator can:</span></span>

  - <span data-ttu-id="aa0dc-144">Visualizzare tutti i casi elencati nella pagina Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="aa0dc-144">View all cases that are listed on the Advanced eDiscovery page.</span></span>
  
  - <span data-ttu-id="aa0dc-145">Gestire qualsiasi caso nell'organizzazione dopo essersi aggiunti come membri del caso.</span><span class="sxs-lookup"><span data-stu-id="aa0dc-145">Manage any case in the organization after they add themselves as a member of the case.</span></span>

  - <span data-ttu-id="aa0dc-146">Accedere ed esportare i dati del caso per qualsiasi caso nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="aa0dc-146">Access and export case data for any case in the organization.</span></span>

  <span data-ttu-id="aa0dc-147">A causa dell'ampio ambito di accesso, un'organizzazione deve avere solo pochi amministratori membri del sottogruppo Amministratori di eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="aa0dc-147">Because of the broad scope of access, an organization should have only a few admins who are members of the eDiscovery Administrators subgroup.</span></span>

<span data-ttu-id="aa0dc-148">Per ulteriori informazioni sulle autorizzazioni di eDiscovery e una descrizione di ogni ruolo assegnato al gruppo di ruoli Manager eDiscovery, vedere [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="aa0dc-148">For more information about eDiscovery permissions and a description of each role that's assigned to the eDiscovery Manager role group, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>

## <a name="step-3-configure-global-settings-for-advanced-ediscovery"></a><span data-ttu-id="aa0dc-149">Passaggio 3: Configurare le impostazioni globali per Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="aa0dc-149">Step 3: Configure global settings for Advanced eDiscovery</span></span>

<span data-ttu-id="aa0dc-150">L'ultimo passaggio da completare prima che gli utenti dell'organizzazione inizino a creare e utilizzare i casi consiste nel configurare le impostazioni globali applicabili a tutti i casi dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="aa0dc-150">The last step to complete before people in your organization start to create and use cases is to configure global settings that apply to all cases in your organization.</span></span> <span data-ttu-id="aa0dc-151">In questo momento, l'unica impostazione globale è il rilevamento dei privilegi *avvocato-client* (altre impostazioni globali saranno disponibili in futuro).</span><span class="sxs-lookup"><span data-stu-id="aa0dc-151">At this time, the only global setting is *attorney-client privilege detection* (more global settings will be available in the future).</span></span> <span data-ttu-id="aa0dc-152">Questa impostazione consente l'esecuzione del modello di privilegio avvocato-client quando si analizzano i dati in un set di revisione.</span><span class="sxs-lookup"><span data-stu-id="aa0dc-152">This setting enables the attorney-client privilege model to run when you analyze data in a review set.</span></span> <span data-ttu-id="aa0dc-153">Il modello usa l'apprendimento automatico per determinare la probabilità che un documento contenga contenuto di natura legale.</span><span class="sxs-lookup"><span data-stu-id="aa0dc-153">The model uses machine learning to determine the likelihood that a document contains content that is legal in nature.</span></span> <span data-ttu-id="aa0dc-154">Confronta inoltre i partecipanti ai documenti con un elenco di avvocati (inviato durante la configurazione del modello) per determinare se un documento ha almeno un partecipante che è un avvocato.</span><span class="sxs-lookup"><span data-stu-id="aa0dc-154">It also compares the participants of documents with an attorney list (that you submit when setting up the model) to determine if a document has at least one participant who is an attorney.</span></span>

<span data-ttu-id="aa0dc-155">Per ulteriori informazioni sulla configurazione e sull'utilizzo del modello di rilevamento dei privilegi [avvocato-client, vedere Set up attorney-client privilege detection in Advanced eDiscovery.](attorney-privilege-detection.md)</span><span class="sxs-lookup"><span data-stu-id="aa0dc-155">For more information about setting up and using the attorney-client privilege detection model, see [Set up attorney-client privilege detection in Advanced eDiscovery](attorney-privilege-detection.md).</span></span>

> [!NOTE]
> <span data-ttu-id="aa0dc-156">Si tratta di un passaggio facoltativo che è possibile eseguire in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="aa0dc-156">This is an optional step that you can perform anytime.</span></span> <span data-ttu-id="aa0dc-157">La non implementazione del modello di rilevamento dei privilegi avvocato-client non impedisce la creazione e l'utilizzo di casi di Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="aa0dc-157">Not implementing the attorney-client privilege detection model doesn't prevent you from creating and using Advanced eDiscovery cases.</span></span>

## <a name="next-steps"></a><span data-ttu-id="aa0dc-158">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="aa0dc-158">Next steps</span></span>

<span data-ttu-id="aa0dc-159">Dopo aver configurato Advanced eDiscovery, è possibile [creare un caso.](create-and-manage-advanced-ediscoveryv2-case.md)</span><span class="sxs-lookup"><span data-stu-id="aa0dc-159">After you set up Advanced eDiscovery, you're ready to [create a case](create-and-manage-advanced-ediscoveryv2-case.md).</span></span>
