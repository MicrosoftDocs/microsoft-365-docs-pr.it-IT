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
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Gli amministratori possono imparare a identificare gruppi specifici di utenti con tag utente in Microsoft Defender per Office 365 Piano 2. Il filtro dei tag è disponibile tra avvisi, report e indagini in Microsoft Defender per Office 365 per identificare rapidamente gli utenti con tag.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4c439dcb91831475bc10da4a01d0fa29e7aae359
ms.sourcegitcommit: 58fbcfd6437bfb08966b79954ca09556e636ff4a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2021
ms.locfileid: "51632203"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a><span data-ttu-id="6c5fa-104">Tag utente in Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="6c5fa-104">User tags in Microsoft Defender for Office 365</span></span>

> [!NOTE]
> <span data-ttu-id="6c5fa-105">La funzionalità tag utente è disponibile in Anteprima, non è disponibile per tutti gli utenti ed è soggetta a modifiche.</span><span class="sxs-lookup"><span data-stu-id="6c5fa-105">The user tags feature is in Preview, isn't available to everyone, and is subject to change.</span></span> <span data-ttu-id="6c5fa-106">Per informazioni sulla pianificazione dei rilasci, consultare la roadmap di [Microsoft 365.](https://www.microsoft.com/microsoft-365/roadmap)</span><span class="sxs-lookup"><span data-stu-id="6c5fa-106">For information about the release schedule, check out the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

<span data-ttu-id="6c5fa-107">I tag utente sono identificatori per gruppi specifici di utenti in [Microsoft Defender per Office 365.](defender-for-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="6c5fa-107">User tags are identifiers for specific groups of users in [Microsoft Defender for Office 365](defender-for-office-365.md).</span></span> <span data-ttu-id="6c5fa-108">Esistono due tipi di tag utente:</span><span class="sxs-lookup"><span data-stu-id="6c5fa-108">There are two types of user tags:</span></span>

- <span data-ttu-id="6c5fa-109">**Tag di** sistema: attualmente, [gli account Priority](../../admin/setup/priority-accounts.md) sono l'unico tipo di tag di sistema.</span><span class="sxs-lookup"><span data-stu-id="6c5fa-109">**System tags**: Currently, [Priority accounts](../../admin/setup/priority-accounts.md) is the only type of system tag.</span></span>
- <span data-ttu-id="6c5fa-110">**Tag personalizzati**: questi tag utente vengono creati manualmente.</span><span class="sxs-lookup"><span data-stu-id="6c5fa-110">**Custom tags**: You create these user tags yourself.</span></span>

<span data-ttu-id="6c5fa-111">Se l'organizzazione dispone di Defender per Office 365 Piano 2 (incluso nell'abbonamento o come componente aggiuntivo), è possibile creare tag utente personalizzati oltre a usare il tag degli account di priorità.</span><span class="sxs-lookup"><span data-stu-id="6c5fa-111">If your organization has Defender for Office 365 Plan 2 (included in your subscription or as an add-on), you can create custom user tags in addition to using the priority accounts tag.</span></span>

> [!NOTE]
> <span data-ttu-id="6c5fa-112">Attualmente, è possibile applicare i tag utente solo agli utenti delle cassette postali.</span><span class="sxs-lookup"><span data-stu-id="6c5fa-112">Currently, you can only apply user tags to mailbox users.</span></span>

<span data-ttu-id="6c5fa-113">Dopo aver applicato tag di sistema o tag personalizzati agli utenti, è possibile utilizzare tali tag come filtri in avvisi, report e indagini:</span><span class="sxs-lookup"><span data-stu-id="6c5fa-113">After you apply system tags or custom tags to users, you can use those tags as filters in alerts, reports, and investigations:</span></span>

- [<span data-ttu-id="6c5fa-114">Avvisi nel Centro sicurezza & conformità</span><span class="sxs-lookup"><span data-stu-id="6c5fa-114">Alerts in the Security & Compliance Center</span></span>](alerts.md)
- [<span data-ttu-id="6c5fa-115">Esplora minacce e rilevamenti in tempo reale</span><span class="sxs-lookup"><span data-stu-id="6c5fa-115">Threat Explorer and real-time detections</span></span>](threat-explorer.md)
- [<span data-ttu-id="6c5fa-116">Report dello stato di protezione dalle minacce</span><span class="sxs-lookup"><span data-stu-id="6c5fa-116">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="6c5fa-117">Visualizzazioni campagna</span><span class="sxs-lookup"><span data-stu-id="6c5fa-117">Campaign Views</span></span>](campaigns.md)
- <span data-ttu-id="6c5fa-118">Per gli account con priorità, è possibile utilizzare il [report Problemi di posta elettronica](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) per gli account con priorità nell'interfaccia di amministrazione di Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="6c5fa-118">For priority accounts, you can use the [Email issues for priority accounts report](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) in the Exchange admin center (EAC).</span></span>

<span data-ttu-id="6c5fa-119">In questo articolo viene illustrato come configurare i tag utente nel Centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="6c5fa-119">This article explains how to configure user tags in the Security & Compliance Center.</span></span> <span data-ttu-id="6c5fa-120">Non sono disponibili cmdlet nel Centro sicurezza & conformità per gestire i tag utente.</span><span class="sxs-lookup"><span data-stu-id="6c5fa-120">There are no cmdlets in Security & Compliance Center to manage user tags.</span></span>

<span data-ttu-id="6c5fa-121">Per informazioni su come i tag utente fanno parte della strategia per proteggere gli account utente ad alto impatto, vedere Consigli per la sicurezza per gli account con priorità [in Microsoft 365.](security-recommendations-for-priority-accounts.md)</span><span class="sxs-lookup"><span data-stu-id="6c5fa-121">To see how user tags are part of the strategy to help protect high-impact user accounts, see [Security recommendations for priority accounts in Microsoft 365](security-recommendations-for-priority-accounts.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="6c5fa-122">Che cosa è necessario sapere prima di iniziare?</span><span class="sxs-lookup"><span data-stu-id="6c5fa-122">What do you need to know before you begin?</span></span>

- <span data-ttu-id="6c5fa-123">Aprire il Centro sicurezza e conformità in<https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="6c5fa-123">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="6c5fa-124">Per passare direttamente alla **pagina Tag** utente, aprire <https://protection.office.com/userTags> .</span><span class="sxs-lookup"><span data-stu-id="6c5fa-124">To go directly to the **User tags** page, open <https://protection.office.com/userTags>.</span></span>

- <span data-ttu-id="6c5fa-125">Per poter eseguire le procedure contenute in questo articolo è necessario disporre delle autorizzazioni appropriate nel Centro sicurezza e conformità:</span><span class="sxs-lookup"><span data-stu-id="6c5fa-125">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="6c5fa-126">Per creare, modificare ed eliminare tag utente, è necessario essere membri dei gruppi **di** ruoli Gestione organizzazione o Amministratore **sicurezza.**</span><span class="sxs-lookup"><span data-stu-id="6c5fa-126">To create, modify, and delete user tags, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="6c5fa-127">Per aggiungere e rimuovere membri dai tag utente esistenti, è necessario essere membri dei gruppi di ruoli **Gestione** **organizzazione,** Amministratore sicurezza o **Operatore** sicurezza</span><span class="sxs-lookup"><span data-stu-id="6c5fa-127">To add and remove members from existing user tags, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Operator** role groups</span></span>
  - <span data-ttu-id="6c5fa-128">Per l'accesso in sola lettura ai tag utente, è necessario essere membri dei gruppi di ruoli **Lettore** globale o **Lettore** di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="6c5fa-128">For read-only access to user tags, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="6c5fa-129">Per altre informazioni, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="6c5fa-129">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="6c5fa-130">**Note**:</span><span class="sxs-lookup"><span data-stu-id="6c5fa-130">**Notes**:</span></span>

  - <span data-ttu-id="6c5fa-131">L'aggiunta di utenti al ruolo di Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft 365 fornisce agli utenti le autorizzazioni necessarie nel centro Sicurezza e conformità _e_ le autorizzazioni per altre funzionalità di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6c5fa-131">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="6c5fa-132">Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="6c5fa-132">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="6c5fa-133">La gestione dei tag utente è controllata dai **ruoli Lettore tag** **e Gestione** tag.</span><span class="sxs-lookup"><span data-stu-id="6c5fa-133">User tag management is controlled by the **Tag Reader** and **Tag Manager** roles.</span></span>

- <span data-ttu-id="6c5fa-134">È inoltre possibile gestire e monitorare gli account con priorità nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6c5fa-134">You can also manage and monitor priority accounts in the Microsoft 365 admin center.</span></span> <span data-ttu-id="6c5fa-135">Per istruzioni, vedere [Gestire e monitorare gli account con priorità.](../../admin/setup/priority-accounts.md)</span><span class="sxs-lookup"><span data-stu-id="6c5fa-135">For instructions, see [Manage and monitor priority accounts](../../admin/setup/priority-accounts.md).</span></span>

- <span data-ttu-id="6c5fa-136">Per informazioni sulla protezione degli _account con privilegi_ (account amministratore), vedere questo [argomento.](/azure/architecture/framework/security/critical-impact-accounts)</span><span class="sxs-lookup"><span data-stu-id="6c5fa-136">For information about securing _privileged accounts_ (admin accounts), see [this topic](/azure/architecture/framework/security/critical-impact-accounts).</span></span>

## <a name="use-the-security--compliance-center-to-create-user-tags"></a><span data-ttu-id="6c5fa-137">Usare il Centro sicurezza & conformità per creare tag utente</span><span class="sxs-lookup"><span data-stu-id="6c5fa-137">Use the Security & Compliance Center to create user tags</span></span>

1. <span data-ttu-id="6c5fa-138">Nel Centro sicurezza & conformità passare a **Gestione minacce** \> **Tag utente**.</span><span class="sxs-lookup"><span data-stu-id="6c5fa-138">In the Security & Compliance Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="6c5fa-139">Nella pagina **Tag utente** visualizzata fare clic su **Crea tag.**</span><span class="sxs-lookup"><span data-stu-id="6c5fa-139">On the **User tags** page that opens, click **Create tag**.</span></span>

3. <span data-ttu-id="6c5fa-140">La **procedura guidata Crea tag** si apre in un nuovo riquadro a comparsa. Nella pagina **Definisci tag** configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6c5fa-140">The **Create tag** wizard opens in a new fly out. On the **Define tag** page, configure the following settings:</span></span>
   - <span data-ttu-id="6c5fa-141">**Nome**: immettere un nome descrittivo univoco per il tag.</span><span class="sxs-lookup"><span data-stu-id="6c5fa-141">**Name**: Enter a unique, descriptive name for the tag.</span></span> <span data-ttu-id="6c5fa-142">Questo è il valore che vedrai e userai.</span><span class="sxs-lookup"><span data-stu-id="6c5fa-142">This is the value that you'll see and use.</span></span>
   - <span data-ttu-id="6c5fa-143">**Descrizione:** immettere una descrizione facoltativa per il tag.</span><span class="sxs-lookup"><span data-stu-id="6c5fa-143">**Description**: Enter an optional description for the tag.</span></span>

   <span data-ttu-id="6c5fa-144">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="6c5fa-144">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="6c5fa-145">Nella pagina **Assegna utenti** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6c5fa-145">On the **Assign users** page, do either of the following steps:</span></span>

   - <span data-ttu-id="6c5fa-146">Fare **clic su Aggiungi utenti**.</span><span class="sxs-lookup"><span data-stu-id="6c5fa-146">Click **Add users**.</span></span> <span data-ttu-id="6c5fa-147">Nel riquadro a comparsa visualizzato eseguire una delle operazioni seguenti per aggiungere singoli utenti o gruppi:</span><span class="sxs-lookup"><span data-stu-id="6c5fa-147">In the fly out that appears, do any of the following steps to add individual users or groups:</span></span>
     - <span data-ttu-id="6c5fa-148">Fare clic nella casella e scorrere l'elenco per selezionare un utente o un gruppo.</span><span class="sxs-lookup"><span data-stu-id="6c5fa-148">Click in the box and scroll through the list to select a user or group.</span></span>
     - <span data-ttu-id="6c5fa-149">Fare clic nella casella e iniziare a digitare per filtrare l'elenco e selezionare un utente o un gruppo.</span><span class="sxs-lookup"><span data-stu-id="6c5fa-149">Click in the box and start typing to filter the list and select a user or group.</span></span>
     - <span data-ttu-id="6c5fa-150">Per aggiungere altri valori, fare clic in un'area vuota della casella.</span><span class="sxs-lookup"><span data-stu-id="6c5fa-150">To add additional values, click in an empty area in the box.</span></span>
     - <span data-ttu-id="6c5fa-151">Per rimuovere singole voci dalla casella, fare clic **su** Rimuovi Icona ![ Rimuovi ](../../media/scc-remove-icon.png) nell'utente o nel gruppo nella casella.</span><span class="sxs-lookup"><span data-stu-id="6c5fa-151">To remove individual entries from the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user or group in the box.</span></span>
     - <span data-ttu-id="6c5fa-152">Per rimuovere le voci esistenti dall'elenco sotto la casella, fare clic **su Rimuovi** Rimuovi icona ![ la ](../../media/scc-remove-icon.png) voce.</span><span class="sxs-lookup"><span data-stu-id="6c5fa-152">To remove existing entries from the list below the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) the entry.</span></span>

     <span data-ttu-id="6c5fa-153">Al termine, fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="6c5fa-153">When you're finished, click **Add**.</span></span>

   - <span data-ttu-id="6c5fa-154">Fare **clic su** Importa per selezionare un file di testo contenente gli indirizzi di posta elettronica degli utenti o dei gruppi.</span><span class="sxs-lookup"><span data-stu-id="6c5fa-154">Click **Import** to select a text file that contains the email addresses of the users or groups.</span></span> <span data-ttu-id="6c5fa-155">Assicurarsi che il file di testo contenga una voce per riga.</span><span class="sxs-lookup"><span data-stu-id="6c5fa-155">Be sure the text file contains one entry per line.</span></span>

   <span data-ttu-id="6c5fa-156">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="6c5fa-156">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="6c5fa-157">Nella pagina **Rivedi tag** rivedere le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="6c5fa-157">On the **Review tag** page, review your settings.</span></span> <span data-ttu-id="6c5fa-158">È possibile fare **clic su** Modifica nella sezione specifica per apportare modifiche.</span><span class="sxs-lookup"><span data-stu-id="6c5fa-158">You can click **Edit** in the specific section to make changes.</span></span>

   <span data-ttu-id="6c5fa-159">Al termine, fare clic su **Invia.**</span><span class="sxs-lookup"><span data-stu-id="6c5fa-159">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security--compliance-center-to-view-user-tags"></a><span data-ttu-id="6c5fa-160">Usare il Centro sicurezza & conformità per visualizzare i tag utente</span><span class="sxs-lookup"><span data-stu-id="6c5fa-160">Use the Security & Compliance Center to view user tags</span></span>

1. <span data-ttu-id="6c5fa-161">Nel Centro sicurezza & conformità passare a **Gestione minacce** \> **Tag utente**.</span><span class="sxs-lookup"><span data-stu-id="6c5fa-161">In the Security & Compliance Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="6c5fa-162">Nella **pagina Tag utente** visualizzata selezionare il tag utente che si desidera visualizzare (non fare clic sulla casella di controllo).</span><span class="sxs-lookup"><span data-stu-id="6c5fa-162">On the **User tags** page that opens, select the user tag that you want to view (don't click on the checkbox).</span></span>

3. <span data-ttu-id="6c5fa-163">Nel riquadro a comparsa dei dettagli di sola lettura visualizzato, rivedere le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="6c5fa-163">In the read-only details fly out that appears, review the settings.</span></span>

   <span data-ttu-id="6c5fa-164">Al termine, fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="6c5fa-164">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-user-tags"></a><span data-ttu-id="6c5fa-165">Utilizzare il Centro sicurezza & conformità per modificare i tag utente</span><span class="sxs-lookup"><span data-stu-id="6c5fa-165">Use the Security & Compliance Center to modify user tags</span></span>

1. <span data-ttu-id="6c5fa-166">Nel Centro sicurezza & conformità passare a **Gestione minacce** \> **Tag utente**.</span><span class="sxs-lookup"><span data-stu-id="6c5fa-166">In the Security & Compliance Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="6c5fa-167">Nella **pagina Tag utente** visualizzata selezionare il tag utente che si desidera visualizzare e quindi fare clic su **Modifica tag.**</span><span class="sxs-lookup"><span data-stu-id="6c5fa-167">On the **User tags** page that opens, select the user tag that you want to view, and then click **Edit tag**.</span></span>

3. <span data-ttu-id="6c5fa-168">La procedura guidata dei criteri viene aperta in un **riquadro a comparsa** Modifica tag. Fare **clic su** Avanti per rivedere e modificare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="6c5fa-168">The policy wizard opens in an **Edit tag** fly out. Click **Next** to review and modify the settings.</span></span>

   <span data-ttu-id="6c5fa-169">Al termine, fare clic su **Invia.**</span><span class="sxs-lookup"><span data-stu-id="6c5fa-169">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-user-tags"></a><span data-ttu-id="6c5fa-170">Usare il Centro sicurezza & conformità per rimuovere i tag utente</span><span class="sxs-lookup"><span data-stu-id="6c5fa-170">Use the Security & Compliance Center to remove user tags</span></span>

<span data-ttu-id="6c5fa-171">**Nota:** non è possibile rimuovere il tag predefinito **dell'account Priority.**</span><span class="sxs-lookup"><span data-stu-id="6c5fa-171">**Note**: You can't remove the built-in **Priority account** tag.</span></span>

1. <span data-ttu-id="6c5fa-172">Nel Centro sicurezza & conformità passare a **Gestione minacce** \> **Tag utente**.</span><span class="sxs-lookup"><span data-stu-id="6c5fa-172">In the Security & Compliance Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="6c5fa-173">Nella **pagina Tag utente** visualizzata selezionare il tag utente che si desidera rimuovere, fare clic su Elimina **tag** e quindi selezionare **Sì,** rimuovi nell'avviso visualizzato.</span><span class="sxs-lookup"><span data-stu-id="6c5fa-173">On the **User tags** page that opens, select the user tag that you want to remove, click **Delete tag**, and then select **Yes, remove** in the warning that appears.</span></span>