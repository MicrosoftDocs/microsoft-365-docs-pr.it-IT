---
title: Tag utente in Microsoft Defender per Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Gli amministratori possono sapere come identificare gruppi specifici di utenti con tag utente in Microsoft Defender per Office 365 piano 2. Il filtro tag è disponibile tra gli avvisi, i report e le indagini in Microsoft Defender per Office 365 per identificare rapidamente gli utenti contrassegnati.
ms.openlocfilehash: 14ebcebeb8081a2de341fd06facabd9f7d55b119
ms.sourcegitcommit: 2d3e85173c65a9e0ce92624a80ed7a9839f5b8bd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/17/2020
ms.locfileid: "49123620"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a><span data-ttu-id="cd232-104">Tag utente in Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="cd232-104">User tags in Microsoft Defender for Office 365</span></span>

> [!NOTE]
> <span data-ttu-id="cd232-105">La funzionalità tag utente è in anteprima, non è disponibile per tutti, ed è soggetta a modifiche.</span><span class="sxs-lookup"><span data-stu-id="cd232-105">The user tags feature is in Preview, isn't available to everyone, and is subject to change.</span></span> <span data-ttu-id="cd232-106">Per informazioni sulla pianificazione dei rilasci, vedere la Guida di [orientamento di Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap).</span><span class="sxs-lookup"><span data-stu-id="cd232-106">For information about the release schedule, check out the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

<span data-ttu-id="cd232-107">I tag utente sono identificatori per gruppi di utenti specifici in [Microsoft Defender per Office 365](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="cd232-107">User tags are identifiers for specific groups of users in [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="cd232-108">Sono disponibili due tipi di tag utente:</span><span class="sxs-lookup"><span data-stu-id="cd232-108">There are two types of user tags:</span></span>

- <span data-ttu-id="cd232-109">**Tag di sistema**: attualmente, gli [account di priorità](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) sono l'unico tipo di tag di sistema.</span><span class="sxs-lookup"><span data-stu-id="cd232-109">**System tags**: Currently, [Priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) is the only type of system tag.</span></span>
- <span data-ttu-id="cd232-110">**Tag personalizzati**: creare personalmente questi tag utente.</span><span class="sxs-lookup"><span data-stu-id="cd232-110">**Custom tags**: You create these user tags yourself.</span></span>

<span data-ttu-id="cd232-111">Se l'organizzazione dispone di un difensore per Office 365 piano 2 (incluso nell'abbonamento o come componente aggiuntivo), è possibile creare tag utente personalizzati oltre a utilizzare il tag account prioritari.</span><span class="sxs-lookup"><span data-stu-id="cd232-111">If your organization has Defender for Office 365 Plan 2 (included in your subscription or as an add-on), you can create custom user tags in addition to using the priority accounts tag.</span></span>

<span data-ttu-id="cd232-112">Dopo aver applicato i tag di sistema o i tag personalizzati agli utenti, è possibile utilizzare tali tag come filtri in avvisi, rapporti ed indagini:</span><span class="sxs-lookup"><span data-stu-id="cd232-112">After you apply system tags or custom tags to users, you can use those tags as filters in alerts, reports, and investigations:</span></span>

- [<span data-ttu-id="cd232-113">Avvisi nel centro sicurezza & conformità</span><span class="sxs-lookup"><span data-stu-id="cd232-113">Alerts in the Security & Compliance Center</span></span>](alerts.md)
- [<span data-ttu-id="cd232-114">Esplora minacce e rilevamenti in tempo reale</span><span class="sxs-lookup"><span data-stu-id="cd232-114">Threat Explorer and real-time detections</span></span>](threat-explorer.md)
- [<span data-ttu-id="cd232-115">Report dello stato di protezione dalle minacce</span><span class="sxs-lookup"><span data-stu-id="cd232-115">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="cd232-116">Visualizzazioni campagna</span><span class="sxs-lookup"><span data-stu-id="cd232-116">Campaign Views</span></span>](campaigns.md)
- <span data-ttu-id="cd232-117">Per gli account prioritari, è possibile utilizzare i [problemi di posta elettronica per il rapporto account prioritari](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) nell'interfaccia di amministrazione di Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="cd232-117">For priority accounts, you can use the [Email issues for priority accounts report](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) in the Exchange admin center (EAC).</span></span>

<span data-ttu-id="cd232-118">In questo articolo viene illustrato come configurare i tag utente nel centro sicurezza & Compliance.</span><span class="sxs-lookup"><span data-stu-id="cd232-118">This article explains how to configure user tags in the Security & Compliance Center.</span></span> <span data-ttu-id="cd232-119">Non sono presenti cmdlet nel centro sicurezza & conformità per la gestione dei tag utente.</span><span class="sxs-lookup"><span data-stu-id="cd232-119">There are no cmdlets in Security & Compliance Center to manage user tags.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="cd232-120">Che cosa è necessario sapere prima di iniziare?</span><span class="sxs-lookup"><span data-stu-id="cd232-120">What do you need to know before you begin?</span></span>

- <span data-ttu-id="cd232-121">Aprire il Centro sicurezza e conformità in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="cd232-121">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="cd232-122">Per passare direttamente alla pagina **tag utente** , Apri <https://protection.office.com/userTags> .</span><span class="sxs-lookup"><span data-stu-id="cd232-122">To go directly to the **User tags** page, open <https://protection.office.com/userTags>.</span></span>

- <span data-ttu-id="cd232-123">Per creare, modificare o rimuovere **tag utente personalizzati**, è necessario essere membri dei gruppi di ruoli **Gestione organizzazione** o **amministratore sicurezza** nel centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="cd232-123">To create, modify, or remove **custom user tags**, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="cd232-124">Per altre informazioni, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="cd232-124">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="cd232-125">Per configurare gli account prioritari (tag di sistema), è necessario essere un [amministratore globale](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) o un [amministratore di Exchange](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator).</span><span class="sxs-lookup"><span data-stu-id="cd232-125">To configure priority accounts (system tags), you need to be a [Global Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) or an [Exchange Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator).</span></span>

  <span data-ttu-id="cd232-126">È inoltre possibile gestire e monitorare gli account prioritari nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cd232-126">You can also manage and monitor priority accounts in the Microsoft 365 admin center.</span></span> <span data-ttu-id="cd232-127">Per istruzioni, vedere [Manage and monitor Priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span><span class="sxs-lookup"><span data-stu-id="cd232-127">For instructions, see [Manage and monitor priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span></span>

## <a name="use-the-security-center-to-create-user-tags"></a><span data-ttu-id="cd232-128">Utilizzare il Centro sicurezza per creare tag utente</span><span class="sxs-lookup"><span data-stu-id="cd232-128">Use the Security Center to create user tags</span></span>

1. <span data-ttu-id="cd232-129">Nel centro sicurezza accedere a **Threat management** \> **tag utente** di gestione delle minacce.</span><span class="sxs-lookup"><span data-stu-id="cd232-129">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="cd232-130">Nella pagina **tag utente** visualizzata, fare clic su **Crea tag**.</span><span class="sxs-lookup"><span data-stu-id="cd232-130">On the **User tags** page that opens, click **Create tag**.</span></span>

3. <span data-ttu-id="cd232-131">La creazione guidata **tag** viene aperta in un nuovo volo. Nella pagina **Definisci Tag** configurare le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="cd232-131">The **Create tag** wizard opens in a new fly out. On the **Define tag** page, configure the following settings:</span></span>
   - <span data-ttu-id="cd232-132">**Nome**: immettere un nome descrittivo univoco per il tag.</span><span class="sxs-lookup"><span data-stu-id="cd232-132">**Name**: Enter a unique, descriptive name for the tag.</span></span> <span data-ttu-id="cd232-133">Questo è il valore che verrà visualizzato e utilizzato.</span><span class="sxs-lookup"><span data-stu-id="cd232-133">This is the value that you'll see and use.</span></span>
   - <span data-ttu-id="cd232-134">**Descrizione**: immettere una descrizione facoltativa per il tag.</span><span class="sxs-lookup"><span data-stu-id="cd232-134">**Description**: Enter an optional description for the tag.</span></span>

   <span data-ttu-id="cd232-135">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="cd232-135">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="cd232-136">Nella pagina **assegnare le cassette postali** , eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cd232-136">On the **Assign mailboxes** page, do either of the following steps:</span></span>

   - <span data-ttu-id="cd232-137">Fare clic su **Aggiungi cassette postali**.</span><span class="sxs-lookup"><span data-stu-id="cd232-137">Click **Add mailboxes**.</span></span> <span data-ttu-id="cd232-138">Nel volo che viene visualizzato, eseguire una delle operazioni seguenti per aggiungere singoli utenti o gruppi:</span><span class="sxs-lookup"><span data-stu-id="cd232-138">In the fly out that appears, do any of the following steps to add individual users or groups:</span></span>
     - <span data-ttu-id="cd232-139">Fare clic nella casella e scorrere l'elenco per selezionare un utente o un gruppo.</span><span class="sxs-lookup"><span data-stu-id="cd232-139">Click in the box and scroll through the list to select a user or group.</span></span>
     - <span data-ttu-id="cd232-140">Fare clic nella casella e iniziare a digitare per filtrare l'elenco e selezionare un utente o un gruppo.</span><span class="sxs-lookup"><span data-stu-id="cd232-140">Click in the box and start typing to filter the list and select a user or group.</span></span>
     - <span data-ttu-id="cd232-141">Per aggiungere ulteriori valori, fare clic in un'area vuota nella casella.</span><span class="sxs-lookup"><span data-stu-id="cd232-141">To add additional values, click in an empty area in the box.</span></span>
     - <span data-ttu-id="cd232-142">Per rimuovere singole voci dalla casella, fare clic su **Rimuovi** ![ icona Rimuovi ](../../media/scc-remove-icon.png) nell'utente o nel gruppo nella casella.</span><span class="sxs-lookup"><span data-stu-id="cd232-142">To remove individual entries from the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user or group in the box.</span></span>
     - <span data-ttu-id="cd232-143">Per rimuovere le voci esistenti dall'elenco sotto la casella, fare clic su **Rimuovi** ![ icona Rimuovi ](../../media/scc-remove-icon.png) la voce.</span><span class="sxs-lookup"><span data-stu-id="cd232-143">To remove existing entries from the list below the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) the entry.</span></span>

     <span data-ttu-id="cd232-144">Al termine, fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="cd232-144">When you're finished, click **Add**.</span></span>

   - <span data-ttu-id="cd232-145">Fare clic su **Importa** per selezionare un file di testo contenente gli indirizzi di posta elettronica degli utenti o dei gruppi.</span><span class="sxs-lookup"><span data-stu-id="cd232-145">Click **Import** to select a text file that contains the email addresses of the users or groups.</span></span> <span data-ttu-id="cd232-146">Verificare che il file di testo contenga una voce per riga.</span><span class="sxs-lookup"><span data-stu-id="cd232-146">Be sure the text file contains one entry per line.</span></span>

   <span data-ttu-id="cd232-147">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="cd232-147">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="cd232-148">Nella pagina **Revisione Tag** , esaminare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="cd232-148">On the **Review tag** page, review your settings.</span></span> <span data-ttu-id="cd232-149">Per apportare modifiche, è possibile fare clic su **modifica** nella sezione specifica.</span><span class="sxs-lookup"><span data-stu-id="cd232-149">You can click **Edit** in the specific section to make changes.</span></span>

   <span data-ttu-id="cd232-150">Al termine, fare clic su **Invia**.</span><span class="sxs-lookup"><span data-stu-id="cd232-150">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-view-user-tags"></a><span data-ttu-id="cd232-151">Utilizzare il Centro sicurezza per visualizzare i tag utente</span><span class="sxs-lookup"><span data-stu-id="cd232-151">Use the Security Center to view user tags</span></span>

1. <span data-ttu-id="cd232-152">Nel centro sicurezza accedere a **Threat management** \> **tag utente** di gestione delle minacce.</span><span class="sxs-lookup"><span data-stu-id="cd232-152">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="cd232-153">Nella pagina **tag utente** che viene visualizzata, selezionare il tag utente che si desidera visualizzare (non fare clic sulla casella di controllo).</span><span class="sxs-lookup"><span data-stu-id="cd232-153">On the **User tags** page that opens, select the user tag that you want to view (don't click on the checkbox).</span></span>

3. <span data-ttu-id="cd232-154">Nei dettagli di sola lettura che vengono visualizzati, esaminare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="cd232-154">In the read-only details fly out that appears, review the settings.</span></span>

   <span data-ttu-id="cd232-155">Al termine, fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="cd232-155">When you're finished, click **Close**.</span></span>

## <a name="use-the-security-center-to-modify-user-tags"></a><span data-ttu-id="cd232-156">Utilizzare il Centro sicurezza per modificare i tag utente</span><span class="sxs-lookup"><span data-stu-id="cd232-156">Use the Security Center to modify user tags</span></span>

1. <span data-ttu-id="cd232-157">Nel centro sicurezza accedere a **Threat management** \> **tag utente** di gestione delle minacce.</span><span class="sxs-lookup"><span data-stu-id="cd232-157">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="cd232-158">Nella pagina **tag utente** che viene visualizzata, selezionare il tag utente che si desidera visualizzare e quindi fare clic su **Modifica tag**.</span><span class="sxs-lookup"><span data-stu-id="cd232-158">On the **User tags** page that opens, select the user tag that you want to view, and then click **Edit tag**.</span></span>

3. <span data-ttu-id="cd232-159">Verrà visualizzata la procedura guidata dei criteri in un **Tag Edit** fly out. Fare clic su **Avanti** per rivedere e modificare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="cd232-159">The policy wizard opens in an **Edit tag** fly out. Click **Next** to review and modify the settings.</span></span>

   <span data-ttu-id="cd232-160">Al termine, fare clic su **Invia**.</span><span class="sxs-lookup"><span data-stu-id="cd232-160">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-remove-user-tags"></a><span data-ttu-id="cd232-161">Utilizzare il Centro sicurezza per rimuovere i tag utente</span><span class="sxs-lookup"><span data-stu-id="cd232-161">Use the Security Center to remove user tags</span></span>

<span data-ttu-id="cd232-162">**Nota**: non è possibile rimuovere il tag dell' **account prioritario** incorporato.</span><span class="sxs-lookup"><span data-stu-id="cd232-162">**Note**: You can't remove the built-in **Priority account** tag.</span></span>

1. <span data-ttu-id="cd232-163">Nel centro sicurezza accedere a **Threat management** \> **tag utente** di gestione delle minacce.</span><span class="sxs-lookup"><span data-stu-id="cd232-163">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="cd232-164">Nella pagina **tag utente** che viene visualizzata, selezionare il tag utente che si desidera rimuovere, fare clic su **Elimina tag**, quindi selezionare **Sì, Rimuovi** nell'avviso che viene visualizzato.</span><span class="sxs-lookup"><span data-stu-id="cd232-164">On the **User tags** page that opens, select the user tag that you want to remove, click **Delete tag**, and then select **Yes, remove** in the warning that appears.</span></span>
