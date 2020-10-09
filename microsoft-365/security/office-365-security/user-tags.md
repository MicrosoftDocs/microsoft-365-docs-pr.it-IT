---
title: Tag utente in Office 365 ATP
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
description: Gli amministratori possono imparare a identificare gruppi specifici di utenti con tag utente in Office 365 ATP piano 2. Il filtro tag è disponibile tra gli avvisi, i report e le indagini di Office 365 ATP per identificare rapidamente gli utenti contrassegnati.
ms.openlocfilehash: 16e756b95e16e40f4df738e825e842681c67e22c
ms.sourcegitcommit: cd17328baa58448214487e3e68c37590ab9fd08d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/09/2020
ms.locfileid: "48399386"
---
# <a name="user-tags-in-office-365-atp"></a><span data-ttu-id="47378-104">Tag utente in Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="47378-104">User tags in Office 365 ATP</span></span>

<span data-ttu-id="47378-105">I tag utente sono identificatori di gruppi specifici di utenti in [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="47378-105">User tags are identifiers for specific groups of users in [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md).</span></span> <span data-ttu-id="47378-106">Sono disponibili due tipi di tag utente:</span><span class="sxs-lookup"><span data-stu-id="47378-106">There are two types of user tags:</span></span>

- <span data-ttu-id="47378-107">**Tag di sistema**: attualmente, gli [account di priorità](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) sono l'unico tipo di tag di sistema.</span><span class="sxs-lookup"><span data-stu-id="47378-107">**System tags**: Currently, [Priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) is the only type of system tag.</span></span>
- <span data-ttu-id="47378-108">**Tag personalizzati**: creare personalmente questi tag utente.</span><span class="sxs-lookup"><span data-stu-id="47378-108">**Custom tags**: You create these user tags yourself.</span></span>

<span data-ttu-id="47378-109">Se l'organizzazione dispone di Office 365 ATP piano 2 (incluso nell'abbonamento o come componente aggiuntivo), è possibile creare tag utente personalizzati oltre a utilizzare il tag account prioritari.</span><span class="sxs-lookup"><span data-stu-id="47378-109">If your organization has Office 365 ATP Plan 2 (included in your subscription or as an add-on), you can create custom user tags in addition to using the priority accounts tag.</span></span>

<span data-ttu-id="47378-110">Dopo aver applicato i tag di sistema o i tag personalizzati agli utenti, è possibile utilizzare tali tag come filtri in avvisi, rapporti ed indagini:</span><span class="sxs-lookup"><span data-stu-id="47378-110">After you apply system tags or custom tags to users, you can use those tags as filters in alerts, reports, and investigations:</span></span>

- [<span data-ttu-id="47378-111">Avvisi nel centro sicurezza & conformità</span><span class="sxs-lookup"><span data-stu-id="47378-111">Alerts in the Security & Compliance Center</span></span>](alerts.md)
- [<span data-ttu-id="47378-112">Esplora minacce e rilevamenti in tempo reale</span><span class="sxs-lookup"><span data-stu-id="47378-112">Threat Explorer and real-time detections</span></span>](threat-explorer.md)
- [<span data-ttu-id="47378-113">Report dello stato di protezione dalle minacce</span><span class="sxs-lookup"><span data-stu-id="47378-113">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="47378-114">Visualizzazioni campagna</span><span class="sxs-lookup"><span data-stu-id="47378-114">Campaign Views</span></span>](campaigns.md)

<span data-ttu-id="47378-115">In questo articolo viene illustrato come configurare i tag utente nel centro sicurezza & Compliance.</span><span class="sxs-lookup"><span data-stu-id="47378-115">This article explains how to configure user tags in the Security & Compliance Center.</span></span> <span data-ttu-id="47378-116">Non sono presenti cmdlet nel centro sicurezza & conformità per la gestione dei tag utente.</span><span class="sxs-lookup"><span data-stu-id="47378-116">There are no cmdlets in Security & Compliance Center to manage user tags.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="47378-117">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="47378-117">What do you need to know before you begin?</span></span>

- <span data-ttu-id="47378-118">Aprire il Centro sicurezza e conformità in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="47378-118">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="47378-119">Per passare direttamente alla pagina **tag utente** , Apri <https://protection.office.com/userTags> .</span><span class="sxs-lookup"><span data-stu-id="47378-119">To go directly to the **User tags** page, open <https://protection.office.com/userTags>.</span></span>

- <span data-ttu-id="47378-120">Per creare, modificare o rimuovere **tag utente personalizzati**, è necessario essere membri dei gruppi di ruoli **Gestione organizzazione** o **amministratore sicurezza** nel centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="47378-120">To create, modify, or remove **custom user tags**, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="47378-121">Per altre informazioni, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="47378-121">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="47378-122">Per configurare gli account prioritari (tag di sistema), è necessario essere un [amministratore globale](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) o un [amministratore di Exchange](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator).</span><span class="sxs-lookup"><span data-stu-id="47378-122">To configure priority accounts (system tags), you need to be a [Global Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) or an [Exchange Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator).</span></span>

  <span data-ttu-id="47378-123">È inoltre possibile gestire e monitorare gli account prioritari nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="47378-123">You can also manage and monitor priority accounts in the Microsoft 365 admin center.</span></span> <span data-ttu-id="47378-124">Per istruzioni, vedere [Manage and monitor Priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span><span class="sxs-lookup"><span data-stu-id="47378-124">For instructions, see [Manage and monitor priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span></span>

## <a name="use-the-security-center-to-create-user-tags"></a><span data-ttu-id="47378-125">Utilizzare il Centro sicurezza per creare tag utente</span><span class="sxs-lookup"><span data-stu-id="47378-125">Use the Security Center to create user tags</span></span>

1. <span data-ttu-id="47378-126">Nel centro sicurezza accedere a **Threat management** \> **tag utente**di gestione delle minacce.</span><span class="sxs-lookup"><span data-stu-id="47378-126">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="47378-127">Nella pagina **tag utente** visualizzata, fare clic su **Crea tag**.</span><span class="sxs-lookup"><span data-stu-id="47378-127">On the **User tags** page that opens, click **Create tag**.</span></span>

3. <span data-ttu-id="47378-128">La creazione guidata **tag** viene aperta in un nuovo volo. Nella pagina **Definisci Tag** configurare le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="47378-128">The **Create tag** wizard opens in a new fly out. On the **Define tag** page, configure the following settings:</span></span>

   - <span data-ttu-id="47378-129">**Nome**: immettere un nome descrittivo univoco per il tag.</span><span class="sxs-lookup"><span data-stu-id="47378-129">**Name**: Enter a unique, descriptive name for the tag.</span></span> <span data-ttu-id="47378-130">Questo è il valore che verrà visualizzato e utilizzato.</span><span class="sxs-lookup"><span data-stu-id="47378-130">This is the value that you'll see and use.</span></span>

   - <span data-ttu-id="47378-131">**Descrizione**: immettere una descrizione facoltativa per il tag.</span><span class="sxs-lookup"><span data-stu-id="47378-131">**Description**: Enter an optional description for the tag.</span></span>

   <span data-ttu-id="47378-132">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="47378-132">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="47378-133">Nella pagina **assegnare le cassette postali** , eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="47378-133">On the **Assign mailboxes** page, do either of the following steps:</span></span>

   - <span data-ttu-id="47378-134">Fare clic su **Aggiungi cassette postali**.</span><span class="sxs-lookup"><span data-stu-id="47378-134">Click **Add mailboxes**.</span></span> <span data-ttu-id="47378-135">Nel volo che viene visualizzato, eseguire una delle operazioni seguenti per aggiungere singoli utenti o gruppi:</span><span class="sxs-lookup"><span data-stu-id="47378-135">In the fly out that appears, do any of the following steps to add individual users or groups:</span></span>

     - <span data-ttu-id="47378-136">Fare clic nella casella e scorrere l'elenco per selezionare un utente o un gruppo.</span><span class="sxs-lookup"><span data-stu-id="47378-136">Click in the box and scroll through the list to select a user or group.</span></span>
     - <span data-ttu-id="47378-137">Fare clic nella casella e iniziare a digitare per filtrare l'elenco e selezionare un utente o un gruppo.</span><span class="sxs-lookup"><span data-stu-id="47378-137">Click in the box and start typing to filter the list and select a user or group.</span></span>
     - <span data-ttu-id="47378-138">Per aggiungere ulteriori valori, fare clic in un'area vuota nella casella.</span><span class="sxs-lookup"><span data-stu-id="47378-138">To add additional values, click in an empty area in the box.</span></span>
     - <span data-ttu-id="47378-139">Per rimuovere singole voci dalla casella, fare clic su **Rimuovi** ![ icona Rimuovi ](../../media/scc-remove-icon.png) nell'utente o nel gruppo nella casella.</span><span class="sxs-lookup"><span data-stu-id="47378-139">To remove individual entries from the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user or group in the box.</span></span>
     - <span data-ttu-id="47378-140">Per rimuovere le voci esistenti dall'elenco sotto la casella, fare clic su **Rimuovi** ![ icona Rimuovi ](../../media/scc-remove-icon.png) la voce.</span><span class="sxs-lookup"><span data-stu-id="47378-140">To remove existing entries from the list below the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) the entry.</span></span>

     <span data-ttu-id="47378-141">Al termine, fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="47378-141">When you're finished, click **Add**.</span></span>

   - <span data-ttu-id="47378-142">Fare clic su **Importa** per selezionare un file di testo contenente gli indirizzi di posta elettronica degli utenti o dei gruppi.</span><span class="sxs-lookup"><span data-stu-id="47378-142">Click **Import** to select a text file that contains the email addresses of the users or groups.</span></span> <span data-ttu-id="47378-143">Verificare che il file di testo contenga una voce per riga.</span><span class="sxs-lookup"><span data-stu-id="47378-143">Be sure the text file contains one entry per line.</span></span>

   <span data-ttu-id="47378-144">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="47378-144">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="47378-145">Nella pagina **Revisione Tag** , esaminare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="47378-145">On the **Review tag** page, review your settings.</span></span> <span data-ttu-id="47378-146">Per apportare modifiche, è possibile fare clic su **modifica** nella sezione specifica.</span><span class="sxs-lookup"><span data-stu-id="47378-146">You can click **Edit** in the specific section to make changes.</span></span>

   <span data-ttu-id="47378-147">Al termine, fare clic su **Invia**.</span><span class="sxs-lookup"><span data-stu-id="47378-147">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-view-user-tags"></a><span data-ttu-id="47378-148">Utilizzare il Centro sicurezza per visualizzare i tag utente</span><span class="sxs-lookup"><span data-stu-id="47378-148">Use the Security Center to view user tags</span></span>

1. <span data-ttu-id="47378-149">Nel centro sicurezza accedere a **Threat management** \> **tag utente**di gestione delle minacce.</span><span class="sxs-lookup"><span data-stu-id="47378-149">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="47378-150">Nella pagina **tag utente** che viene visualizzata, selezionare il tag utente che si desidera visualizzare (non fare clic sulla casella di controllo).</span><span class="sxs-lookup"><span data-stu-id="47378-150">On the **User tags** page that opens, select the user tag that you want to view (don't click on the checkbox).</span></span>

3. <span data-ttu-id="47378-151">Nei dettagli di sola lettura che vengono visualizzati, esaminare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="47378-151">In the read-only details fly out that appears, review the settings.</span></span>

   <span data-ttu-id="47378-152">Al termine, fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="47378-152">When you're finished, click **Close**.</span></span>

## <a name="use-the-security-center-to-modify-user-tags"></a><span data-ttu-id="47378-153">Utilizzare il Centro sicurezza per modificare i tag utente</span><span class="sxs-lookup"><span data-stu-id="47378-153">Use the Security Center to modify user tags</span></span>

1. <span data-ttu-id="47378-154">Nel centro sicurezza accedere a **Threat management** \> **tag utente**di gestione delle minacce.</span><span class="sxs-lookup"><span data-stu-id="47378-154">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="47378-155">Nella pagina **tag utente** che viene visualizzata, selezionare il tag utente che si desidera visualizzare e quindi fare clic su **Modifica tag**.</span><span class="sxs-lookup"><span data-stu-id="47378-155">On the **User tags** page that opens, select the user tag that you want to view, and then click **Edit tag**.</span></span>

3. <span data-ttu-id="47378-156">Verrà visualizzata la procedura guidata dei criteri in un **Tag Edit** fly out. Fare clic su **Avanti** per rivedere e modificare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="47378-156">The policy wizard opens in an **Edit tag** fly out. Click **Next** to review and modify the settings.</span></span>

   <span data-ttu-id="47378-157">Al termine, fare clic su **Invia**.</span><span class="sxs-lookup"><span data-stu-id="47378-157">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-remove-user-tags"></a><span data-ttu-id="47378-158">Utilizzare il Centro sicurezza per rimuovere i tag utente</span><span class="sxs-lookup"><span data-stu-id="47378-158">Use the Security Center to remove user tags</span></span>

<span data-ttu-id="47378-159">**Nota**: non è possibile rimuovere il tag dell' **account prioritario** incorporato.</span><span class="sxs-lookup"><span data-stu-id="47378-159">**Note**: You can't remove the built-in **Priority account** tag.</span></span>

1. <span data-ttu-id="47378-160">Nel centro sicurezza accedere a **Threat management** \> **tag utente**di gestione delle minacce.</span><span class="sxs-lookup"><span data-stu-id="47378-160">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="47378-161">Nella pagina **tag utente** che viene visualizzata, selezionare il tag utente che si desidera rimuovere, fare clic su **Elimina tag**, quindi selezionare **Sì, Rimuovi** nell'avviso che viene visualizzato.</span><span class="sxs-lookup"><span data-stu-id="47378-161">On the **User tags** page that opens, select the user tag that you want to remove, click **Delete tag**, and then select **Yes, remove** in the warning that appears.</span></span>
