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
ms.openlocfilehash: ad06bf90f1ecb93d671bfcad6fad0b4f2a952cb2
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663608"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a><span data-ttu-id="82536-104">Tag utente in Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="82536-104">User tags in Microsoft Defender for Office 365</span></span>

> [!NOTE]
> <span data-ttu-id="82536-105">La funzionalità tag utente è in anteprima, non è disponibile per tutti, ed è soggetta a modifiche.</span><span class="sxs-lookup"><span data-stu-id="82536-105">The user tags feature is in Preview, isn't available to everyone, and is subject to change.</span></span> <span data-ttu-id="82536-106">Per informazioni sulla pianificazione dei rilasci, vedere la Guida di [orientamento di Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap).</span><span class="sxs-lookup"><span data-stu-id="82536-106">For information about the release schedule, check out the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

<span data-ttu-id="82536-107">I tag utente sono identificatori per gruppi di utenti specifici in [Microsoft Defender per Office 365](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="82536-107">User tags are identifiers for specific groups of users in [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="82536-108">Sono disponibili due tipi di tag utente:</span><span class="sxs-lookup"><span data-stu-id="82536-108">There are two types of user tags:</span></span>

- <span data-ttu-id="82536-109">**Tag di sistema**: attualmente, gli [account di priorità](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) sono l'unico tipo di tag di sistema.</span><span class="sxs-lookup"><span data-stu-id="82536-109">**System tags**: Currently, [Priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) is the only type of system tag.</span></span>
- <span data-ttu-id="82536-110">**Tag personalizzati**: creare personalmente questi tag utente.</span><span class="sxs-lookup"><span data-stu-id="82536-110">**Custom tags**: You create these user tags yourself.</span></span>

<span data-ttu-id="82536-111">Se l'organizzazione dispone di un difensore per Office 365 piano 2 (incluso nell'abbonamento o come componente aggiuntivo), è possibile creare tag utente personalizzati oltre a utilizzare il tag account prioritari.</span><span class="sxs-lookup"><span data-stu-id="82536-111">If your organization has Defender for Office 365 Plan 2 (included in your subscription or as an add-on), you can create custom user tags in addition to using the priority accounts tag.</span></span>

<span data-ttu-id="82536-112">Dopo aver applicato i tag di sistema o i tag personalizzati agli utenti, è possibile utilizzare tali tag come filtri in avvisi, rapporti ed indagini:</span><span class="sxs-lookup"><span data-stu-id="82536-112">After you apply system tags or custom tags to users, you can use those tags as filters in alerts, reports, and investigations:</span></span>

- [<span data-ttu-id="82536-113">Avvisi nel centro sicurezza & conformità</span><span class="sxs-lookup"><span data-stu-id="82536-113">Alerts in the Security & Compliance Center</span></span>](alerts.md)
- [<span data-ttu-id="82536-114">Esplora minacce e rilevamenti in tempo reale</span><span class="sxs-lookup"><span data-stu-id="82536-114">Threat Explorer and real-time detections</span></span>](threat-explorer.md)
- [<span data-ttu-id="82536-115">Report dello stato di protezione dalle minacce</span><span class="sxs-lookup"><span data-stu-id="82536-115">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="82536-116">Visualizzazioni campagna</span><span class="sxs-lookup"><span data-stu-id="82536-116">Campaign Views</span></span>](campaigns.md)
- <span data-ttu-id="82536-117">Per gli account prioritari, è possibile utilizzare i [problemi di posta elettronica per il rapporto account prioritari](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) nell'interfaccia di amministrazione di Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="82536-117">For priority accounts, you can use the [Email issues for priority accounts report](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) in the Exchange admin center (EAC).</span></span>

<span data-ttu-id="82536-118">In questo articolo viene illustrato come configurare i tag utente nel centro sicurezza & Compliance.</span><span class="sxs-lookup"><span data-stu-id="82536-118">This article explains how to configure user tags in the Security & Compliance Center.</span></span> <span data-ttu-id="82536-119">Non sono presenti cmdlet nel centro sicurezza & conformità per la gestione dei tag utente.</span><span class="sxs-lookup"><span data-stu-id="82536-119">There are no cmdlets in Security & Compliance Center to manage user tags.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="82536-120">Che cosa è necessario sapere prima di iniziare?</span><span class="sxs-lookup"><span data-stu-id="82536-120">What do you need to know before you begin?</span></span>

- <span data-ttu-id="82536-121">Aprire il Centro sicurezza e conformità in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="82536-121">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="82536-122">Per passare direttamente alla pagina **tag utente** , Apri <https://protection.office.com/userTags> .</span><span class="sxs-lookup"><span data-stu-id="82536-122">To go directly to the **User tags** page, open <https://protection.office.com/userTags>.</span></span>

- <span data-ttu-id="82536-123">Per poter eseguire le procedure contenute in questo articolo è necessario disporre delle autorizzazioni appropriate nel Centro sicurezza e conformità:</span><span class="sxs-lookup"><span data-stu-id="82536-123">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="82536-124">Per creare, modificare ed eliminare i tag utente, è necessario essere membri dei gruppi di ruoli **Gestione organizzazione** o **amministratore sicurezza** .</span><span class="sxs-lookup"><span data-stu-id="82536-124">To create, modify, and delete user tags, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="82536-125">Per aggiungere e rimuovere membri dai tag utente esistenti, è necessario essere membri dei gruppi di ruoli **Gestione organizzazione**, **amministratore sicurezza** o **operatore di sicurezza** .</span><span class="sxs-lookup"><span data-stu-id="82536-125">To add and remove members from existing user tags, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Operator** role groups</span></span>
  - <span data-ttu-id="82536-126">Per l'accesso in sola lettura ai tag degli utenti, è necessario essere membri dei gruppi di ruoli **lettore globale** o lettore di **sicurezza** .</span><span class="sxs-lookup"><span data-stu-id="82536-126">For read-only access to user tags, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="82536-127">Per altre informazioni, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="82536-127">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="82536-128">**Note**:</span><span class="sxs-lookup"><span data-stu-id="82536-128">**Notes**:</span></span>

  - <span data-ttu-id="82536-129">L'aggiunta di utenti al ruolo di Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft 365 fornisce agli utenti le autorizzazioni necessarie nel centro Sicurezza e conformità _e_ le autorizzazioni per altre funzionalità di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="82536-129">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="82536-130">Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="82536-130">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="82536-131">La gestione dei tag utente è controllata dai ruoli **lettore** tag, **collaboratore Tag** e **Gestione tag** .</span><span class="sxs-lookup"><span data-stu-id="82536-131">User tag management is controlled by the **Tag Reader**, **Tag Contributor**, and **Tag Manager** roles.</span></span>

- <span data-ttu-id="82536-132">È inoltre possibile gestire e monitorare gli account prioritari nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="82536-132">You can also manage and monitor priority accounts in the Microsoft 365 admin center.</span></span> <span data-ttu-id="82536-133">Per istruzioni, vedere [Manage and monitor Priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span><span class="sxs-lookup"><span data-stu-id="82536-133">For instructions, see [Manage and monitor priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span></span>

## <a name="use-the-security-center-to-create-user-tags"></a><span data-ttu-id="82536-134">Utilizzare il Centro sicurezza per creare tag utente</span><span class="sxs-lookup"><span data-stu-id="82536-134">Use the Security Center to create user tags</span></span>

1. <span data-ttu-id="82536-135">Nel centro sicurezza accedere a  \> **tag utente** di gestione delle minacce.</span><span class="sxs-lookup"><span data-stu-id="82536-135">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="82536-136">Nella pagina **tag utente** visualizzata, fare clic su **Crea tag**.</span><span class="sxs-lookup"><span data-stu-id="82536-136">On the **User tags** page that opens, click **Create tag**.</span></span>

3. <span data-ttu-id="82536-137">La creazione guidata **tag** viene aperta in un nuovo volo. Nella pagina **Definisci Tag** configurare le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="82536-137">The **Create tag** wizard opens in a new fly out. On the **Define tag** page, configure the following settings:</span></span>
   - <span data-ttu-id="82536-138">**Nome**: immettere un nome descrittivo univoco per il tag.</span><span class="sxs-lookup"><span data-stu-id="82536-138">**Name**: Enter a unique, descriptive name for the tag.</span></span> <span data-ttu-id="82536-139">Questo è il valore che verrà visualizzato e utilizzato.</span><span class="sxs-lookup"><span data-stu-id="82536-139">This is the value that you'll see and use.</span></span>
   - <span data-ttu-id="82536-140">**Descrizione**: immettere una descrizione facoltativa per il tag.</span><span class="sxs-lookup"><span data-stu-id="82536-140">**Description**: Enter an optional description for the tag.</span></span>

   <span data-ttu-id="82536-141">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="82536-141">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="82536-142">Nella pagina **Assegna utenti** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="82536-142">On the **Assign users** page, do either of the following steps:</span></span>

   - <span data-ttu-id="82536-143">Fare clic su **Aggiungi utenti**.</span><span class="sxs-lookup"><span data-stu-id="82536-143">Click **Add users**.</span></span> <span data-ttu-id="82536-144">Nel volo che viene visualizzato, eseguire una delle operazioni seguenti per aggiungere singoli utenti o gruppi:</span><span class="sxs-lookup"><span data-stu-id="82536-144">In the fly out that appears, do any of the following steps to add individual users or groups:</span></span>
     - <span data-ttu-id="82536-145">Fare clic nella casella e scorrere l'elenco per selezionare un utente o un gruppo.</span><span class="sxs-lookup"><span data-stu-id="82536-145">Click in the box and scroll through the list to select a user or group.</span></span>
     - <span data-ttu-id="82536-146">Fare clic nella casella e iniziare a digitare per filtrare l'elenco e selezionare un utente o un gruppo.</span><span class="sxs-lookup"><span data-stu-id="82536-146">Click in the box and start typing to filter the list and select a user or group.</span></span>
     - <span data-ttu-id="82536-147">Per aggiungere ulteriori valori, fare clic in un'area vuota nella casella.</span><span class="sxs-lookup"><span data-stu-id="82536-147">To add additional values, click in an empty area in the box.</span></span>
     - <span data-ttu-id="82536-148">Per rimuovere singole voci dalla casella, fare clic su **Rimuovi** ![ icona Rimuovi ](../../media/scc-remove-icon.png) nell'utente o nel gruppo nella casella.</span><span class="sxs-lookup"><span data-stu-id="82536-148">To remove individual entries from the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user or group in the box.</span></span>
     - <span data-ttu-id="82536-149">Per rimuovere le voci esistenti dall'elenco sotto la casella, fare clic su **Rimuovi** ![ icona Rimuovi ](../../media/scc-remove-icon.png) la voce.</span><span class="sxs-lookup"><span data-stu-id="82536-149">To remove existing entries from the list below the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) the entry.</span></span>

     <span data-ttu-id="82536-150">Al termine, fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="82536-150">When you're finished, click **Add**.</span></span>

   - <span data-ttu-id="82536-151">Fare clic su **Importa** per selezionare un file di testo contenente gli indirizzi di posta elettronica degli utenti o dei gruppi.</span><span class="sxs-lookup"><span data-stu-id="82536-151">Click **Import** to select a text file that contains the email addresses of the users or groups.</span></span> <span data-ttu-id="82536-152">Verificare che il file di testo contenga una voce per riga.</span><span class="sxs-lookup"><span data-stu-id="82536-152">Be sure the text file contains one entry per line.</span></span>

   <span data-ttu-id="82536-153">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="82536-153">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="82536-154">Nella pagina **Revisione Tag** , esaminare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="82536-154">On the **Review tag** page, review your settings.</span></span> <span data-ttu-id="82536-155">Per apportare modifiche, è possibile fare clic su **modifica** nella sezione specifica.</span><span class="sxs-lookup"><span data-stu-id="82536-155">You can click **Edit** in the specific section to make changes.</span></span>

   <span data-ttu-id="82536-156">Al termine, fare clic su **Invia**.</span><span class="sxs-lookup"><span data-stu-id="82536-156">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-view-user-tags"></a><span data-ttu-id="82536-157">Utilizzare il Centro sicurezza per visualizzare i tag utente</span><span class="sxs-lookup"><span data-stu-id="82536-157">Use the Security Center to view user tags</span></span>

1. <span data-ttu-id="82536-158">Nel centro sicurezza accedere a  \> **tag utente** di gestione delle minacce.</span><span class="sxs-lookup"><span data-stu-id="82536-158">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="82536-159">Nella pagina **tag utente** che viene visualizzata, selezionare il tag utente che si desidera visualizzare (non fare clic sulla casella di controllo).</span><span class="sxs-lookup"><span data-stu-id="82536-159">On the **User tags** page that opens, select the user tag that you want to view (don't click on the checkbox).</span></span>

3. <span data-ttu-id="82536-160">Nei dettagli di sola lettura che vengono visualizzati, esaminare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="82536-160">In the read-only details fly out that appears, review the settings.</span></span>

   <span data-ttu-id="82536-161">Al termine, fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="82536-161">When you're finished, click **Close**.</span></span>

## <a name="use-the-security-center-to-modify-user-tags"></a><span data-ttu-id="82536-162">Utilizzare il Centro sicurezza per modificare i tag utente</span><span class="sxs-lookup"><span data-stu-id="82536-162">Use the Security Center to modify user tags</span></span>

1. <span data-ttu-id="82536-163">Nel centro sicurezza accedere a  \> **tag utente** di gestione delle minacce.</span><span class="sxs-lookup"><span data-stu-id="82536-163">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="82536-164">Nella pagina **tag utente** che viene visualizzata, selezionare il tag utente che si desidera visualizzare e quindi fare clic su **Modifica tag**.</span><span class="sxs-lookup"><span data-stu-id="82536-164">On the **User tags** page that opens, select the user tag that you want to view, and then click **Edit tag**.</span></span>

3. <span data-ttu-id="82536-165">Verrà visualizzata la procedura guidata dei criteri in un **Tag Edit** fly out. Fare clic su **Avanti** per rivedere e modificare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="82536-165">The policy wizard opens in an **Edit tag** fly out. Click **Next** to review and modify the settings.</span></span>

   <span data-ttu-id="82536-166">Al termine, fare clic su **Invia**.</span><span class="sxs-lookup"><span data-stu-id="82536-166">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-remove-user-tags"></a><span data-ttu-id="82536-167">Utilizzare il Centro sicurezza per rimuovere i tag utente</span><span class="sxs-lookup"><span data-stu-id="82536-167">Use the Security Center to remove user tags</span></span>

<span data-ttu-id="82536-168">**Nota**: non è possibile rimuovere il tag dell' **account prioritario** incorporato.</span><span class="sxs-lookup"><span data-stu-id="82536-168">**Note**: You can't remove the built-in **Priority account** tag.</span></span>

1. <span data-ttu-id="82536-169">Nel centro sicurezza accedere a  \> **tag utente** di gestione delle minacce.</span><span class="sxs-lookup"><span data-stu-id="82536-169">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="82536-170">Nella pagina **tag utente** che viene visualizzata, selezionare il tag utente che si desidera rimuovere, fare clic su **Elimina tag**, quindi selezionare **Sì, Rimuovi** nell'avviso che viene visualizzato.</span><span class="sxs-lookup"><span data-stu-id="82536-170">On the **User tags** page that opens, select the user tag that you want to remove, click **Delete tag**, and then select **Yes, remove** in the warning that appears.</span></span>
