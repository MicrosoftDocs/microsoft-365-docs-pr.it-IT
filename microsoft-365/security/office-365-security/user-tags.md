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
description: Gli amministratori possono imparare a identificare gruppi specifici di utenti con tag utente in Microsoft Defender per Office 365 Piano 2. Il filtro tag è disponibile per avvisi, report e indagini in Microsoft Defender per Office 365 per identificare rapidamente gli utenti contrassegnati.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ed91492e652773b3a48373df49b20d97887df6ee
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931435"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a><span data-ttu-id="90cba-104">Tag utente in Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="90cba-104">User tags in Microsoft Defender for Office 365</span></span>

> [!NOTE]
> <span data-ttu-id="90cba-105">La funzionalità tag utente è disponibile in Anteprima, non è disponibile per tutti gli utenti ed è soggetta a modifiche.</span><span class="sxs-lookup"><span data-stu-id="90cba-105">The user tags feature is in Preview, isn't available to everyone, and is subject to change.</span></span> <span data-ttu-id="90cba-106">Per informazioni sulla pianificazione dei rilasci, consultare la roadmap di [Microsoft 365.](https://www.microsoft.com/microsoft-365/roadmap)</span><span class="sxs-lookup"><span data-stu-id="90cba-106">For information about the release schedule, check out the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

<span data-ttu-id="90cba-107">I tag utente sono identificatori per gruppi specifici di utenti in [Microsoft Defender per Office 365.](office-365-atp.md)</span><span class="sxs-lookup"><span data-stu-id="90cba-107">User tags are identifiers for specific groups of users in [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="90cba-108">Esistono due tipi di tag utente:</span><span class="sxs-lookup"><span data-stu-id="90cba-108">There are two types of user tags:</span></span>

- <span data-ttu-id="90cba-109">**Tag di** sistema: attualmente, [gli account Priority](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) sono l'unico tipo di tag di sistema.</span><span class="sxs-lookup"><span data-stu-id="90cba-109">**System tags**: Currently, [Priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) is the only type of system tag.</span></span>
- <span data-ttu-id="90cba-110">**Tag personalizzati:** questi tag utente vengono creati manualmente.</span><span class="sxs-lookup"><span data-stu-id="90cba-110">**Custom tags**: You create these user tags yourself.</span></span>

<span data-ttu-id="90cba-111">Se l'organizzazione dispone di Defender per Office 365 Piano 2 (incluso nell'abbonamento o come componente aggiuntivo), è possibile creare tag utente personalizzati oltre a usare il tag degli account con priorità.</span><span class="sxs-lookup"><span data-stu-id="90cba-111">If your organization has Defender for Office 365 Plan 2 (included in your subscription or as an add-on), you can create custom user tags in addition to using the priority accounts tag.</span></span>

<span data-ttu-id="90cba-112">Dopo aver applicato tag di sistema o tag personalizzati agli utenti, è possibile utilizzare tali tag come filtri in avvisi, report e indagini:</span><span class="sxs-lookup"><span data-stu-id="90cba-112">After you apply system tags or custom tags to users, you can use those tags as filters in alerts, reports, and investigations:</span></span>

- [<span data-ttu-id="90cba-113">Avvisi nel Centro sicurezza & conformità</span><span class="sxs-lookup"><span data-stu-id="90cba-113">Alerts in the Security & Compliance Center</span></span>](alerts.md)
- [<span data-ttu-id="90cba-114">Esplora minacce e rilevamenti in tempo reale</span><span class="sxs-lookup"><span data-stu-id="90cba-114">Threat Explorer and real-time detections</span></span>](threat-explorer.md)
- [<span data-ttu-id="90cba-115">Report dello stato di protezione dalle minacce</span><span class="sxs-lookup"><span data-stu-id="90cba-115">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="90cba-116">Visualizzazioni campagna</span><span class="sxs-lookup"><span data-stu-id="90cba-116">Campaign Views</span></span>](campaigns.md)
- <span data-ttu-id="90cba-117">Per gli account con priorità, è possibile utilizzare il report Problemi di posta elettronica per gli [account con priorità](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) nell'interfaccia di amministrazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="90cba-117">For priority accounts, you can use the [Email issues for priority accounts report](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) in the Exchange admin center (EAC).</span></span>

<span data-ttu-id="90cba-118">Questo articolo spiega come configurare i tag utente nel Centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="90cba-118">This article explains how to configure user tags in the Security & Compliance Center.</span></span> <span data-ttu-id="90cba-119">Non sono disponibili cmdlet nel Centro sicurezza & conformità per gestire i tag utente.</span><span class="sxs-lookup"><span data-stu-id="90cba-119">There are no cmdlets in Security & Compliance Center to manage user tags.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="90cba-120">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="90cba-120">What do you need to know before you begin?</span></span>

- <span data-ttu-id="90cba-121">Aprire il Centro sicurezza e conformità in<https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="90cba-121">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="90cba-122">Per passare direttamente alla **pagina Tag** utente, aprire <https://protection.office.com/userTags> .</span><span class="sxs-lookup"><span data-stu-id="90cba-122">To go directly to the **User tags** page, open <https://protection.office.com/userTags>.</span></span>

- <span data-ttu-id="90cba-123">È necessario disporre delle autorizzazioni nel Centro sicurezza e conformità per poter eseguire le procedure contenute in questo articolo:</span><span class="sxs-lookup"><span data-stu-id="90cba-123">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="90cba-124">Per creare, modificare ed eliminare tag utente, è necessario essere membri dei gruppi **di** ruoli Gestione organizzazione o Amministratore **sicurezza.**</span><span class="sxs-lookup"><span data-stu-id="90cba-124">To create, modify, and delete user tags, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="90cba-125">Per aggiungere e rimuovere membri dai tag utente esistenti, è necessario essere membri dei gruppi di ruoli **Gestione** **organizzazione,** Amministratore sicurezza **o Operatore** sicurezza</span><span class="sxs-lookup"><span data-stu-id="90cba-125">To add and remove members from existing user tags, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Operator** role groups</span></span>
  - <span data-ttu-id="90cba-126">Per l'accesso in sola lettura ai tag utente, è necessario essere membri dei **gruppi** di ruoli Lettore globale o **Lettore** di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="90cba-126">For read-only access to user tags, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="90cba-127">Per altre informazioni, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="90cba-127">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="90cba-128">**Note**:</span><span class="sxs-lookup"><span data-stu-id="90cba-128">**Notes**:</span></span>

  - <span data-ttu-id="90cba-129">L'aggiunta di utenti al ruolo di Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft 365 fornisce agli utenti le autorizzazioni necessarie nel centro Sicurezza e conformità _e_ le autorizzazioni per altre funzionalità di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="90cba-129">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="90cba-130">Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="90cba-130">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="90cba-131">La gestione dei tag utente è controllata dai **ruoli Lettore tag,** **Collaboratore** tag **e Gestione** tag.</span><span class="sxs-lookup"><span data-stu-id="90cba-131">User tag management is controlled by the **Tag Reader**, **Tag Contributor**, and **Tag Manager** roles.</span></span>

- <span data-ttu-id="90cba-132">È inoltre possibile gestire e monitorare gli account con priorità nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="90cba-132">You can also manage and monitor priority accounts in the Microsoft 365 admin center.</span></span> <span data-ttu-id="90cba-133">Per istruzioni, vedere [Gestire e monitorare gli account con priorità.](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts)</span><span class="sxs-lookup"><span data-stu-id="90cba-133">For instructions, see [Manage and monitor priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span></span>

## <a name="use-the-security-center-to-create-user-tags"></a><span data-ttu-id="90cba-134">Utilizzare il Centro sicurezza per creare tag utente</span><span class="sxs-lookup"><span data-stu-id="90cba-134">Use the Security Center to create user tags</span></span>

1. <span data-ttu-id="90cba-135">Nel Centro sicurezza passare a **Tag utente per la gestione** delle \> **minacce.**</span><span class="sxs-lookup"><span data-stu-id="90cba-135">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="90cba-136">Nella pagina **Tag utente** visualizzata fare clic su **Crea tag.**</span><span class="sxs-lookup"><span data-stu-id="90cba-136">On the **User tags** page that opens, click **Create tag**.</span></span>

3. <span data-ttu-id="90cba-137">La **creazione guidata tag** si apre in un nuovo riquadro a comparsa. Nella pagina **Definisci tag** configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="90cba-137">The **Create tag** wizard opens in a new fly out. On the **Define tag** page, configure the following settings:</span></span>
   - <span data-ttu-id="90cba-138">**Nome**: immettere un nome descrittivo univoco per il tag.</span><span class="sxs-lookup"><span data-stu-id="90cba-138">**Name**: Enter a unique, descriptive name for the tag.</span></span> <span data-ttu-id="90cba-139">Questo è il valore che verrà visualizzato e utilizzato.</span><span class="sxs-lookup"><span data-stu-id="90cba-139">This is the value that you'll see and use.</span></span>
   - <span data-ttu-id="90cba-140">**Descrizione:** immettere una descrizione facoltativa per il tag.</span><span class="sxs-lookup"><span data-stu-id="90cba-140">**Description**: Enter an optional description for the tag.</span></span>

   <span data-ttu-id="90cba-141">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="90cba-141">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="90cba-142">Nella pagina **Assegna utenti** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="90cba-142">On the **Assign users** page, do either of the following steps:</span></span>

   - <span data-ttu-id="90cba-143">Fare **clic su Aggiungi utenti.**</span><span class="sxs-lookup"><span data-stu-id="90cba-143">Click **Add users**.</span></span> <span data-ttu-id="90cba-144">Nel riquadro a comparsa visualizzato, eseguire una delle operazioni seguenti per aggiungere singoli utenti o gruppi:</span><span class="sxs-lookup"><span data-stu-id="90cba-144">In the fly out that appears, do any of the following steps to add individual users or groups:</span></span>
     - <span data-ttu-id="90cba-145">Fare clic nella casella e scorrere l'elenco per selezionare un utente o un gruppo.</span><span class="sxs-lookup"><span data-stu-id="90cba-145">Click in the box and scroll through the list to select a user or group.</span></span>
     - <span data-ttu-id="90cba-146">Fare clic nella casella e iniziare a digitare per filtrare l'elenco e selezionare un utente o un gruppo.</span><span class="sxs-lookup"><span data-stu-id="90cba-146">Click in the box and start typing to filter the list and select a user or group.</span></span>
     - <span data-ttu-id="90cba-147">Per aggiungere ulteriori valori, fare clic in un'area vuota della casella.</span><span class="sxs-lookup"><span data-stu-id="90cba-147">To add additional values, click in an empty area in the box.</span></span>
     - <span data-ttu-id="90cba-148">Per rimuovere singole voci dalla casella, fare **clic** sull'icona Rimuovi ![ ](../../media/scc-remove-icon.png) dell'utente o del gruppo nella casella.</span><span class="sxs-lookup"><span data-stu-id="90cba-148">To remove individual entries from the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user or group in the box.</span></span>
     - <span data-ttu-id="90cba-149">Per rimuovere voci esistenti dall'elenco sotto la casella, fare clic  ![ sull'icona ](../../media/scc-remove-icon.png) Rimuovi.</span><span class="sxs-lookup"><span data-stu-id="90cba-149">To remove existing entries from the list below the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) the entry.</span></span>

     <span data-ttu-id="90cba-150">Al termine, fare clic su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="90cba-150">When you're finished, click **Add**.</span></span>

   - <span data-ttu-id="90cba-151">Fare **clic su** Importa per selezionare un file di testo contenente gli indirizzi di posta elettronica degli utenti o dei gruppi.</span><span class="sxs-lookup"><span data-stu-id="90cba-151">Click **Import** to select a text file that contains the email addresses of the users or groups.</span></span> <span data-ttu-id="90cba-152">Assicurarsi che il file di testo contenga una voce per riga.</span><span class="sxs-lookup"><span data-stu-id="90cba-152">Be sure the text file contains one entry per line.</span></span>

   <span data-ttu-id="90cba-153">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="90cba-153">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="90cba-154">Nella pagina **Rivedi tag** esaminare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="90cba-154">On the **Review tag** page, review your settings.</span></span> <span data-ttu-id="90cba-155">È possibile fare **clic su** Modifica nella sezione specifica per apportare modifiche.</span><span class="sxs-lookup"><span data-stu-id="90cba-155">You can click **Edit** in the specific section to make changes.</span></span>

   <span data-ttu-id="90cba-156">Al termine, fare clic su **Invia.**</span><span class="sxs-lookup"><span data-stu-id="90cba-156">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-view-user-tags"></a><span data-ttu-id="90cba-157">Utilizzare il Centro sicurezza per visualizzare i tag utente</span><span class="sxs-lookup"><span data-stu-id="90cba-157">Use the Security Center to view user tags</span></span>

1. <span data-ttu-id="90cba-158">Nel Centro sicurezza passare a **Tag utente per la gestione** delle \> **minacce.**</span><span class="sxs-lookup"><span data-stu-id="90cba-158">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="90cba-159">Nella **pagina Tag utente** visualizzata, selezionare il tag utente che si desidera visualizzare (non fare clic sulla casella di controllo).</span><span class="sxs-lookup"><span data-stu-id="90cba-159">On the **User tags** page that opens, select the user tag that you want to view (don't click on the checkbox).</span></span>

3. <span data-ttu-id="90cba-160">Nel riquadro a comparsa dei dettagli di sola lettura visualizzato, rivedere le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="90cba-160">In the read-only details fly out that appears, review the settings.</span></span>

   <span data-ttu-id="90cba-161">Al termine, fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="90cba-161">When you're finished, click **Close**.</span></span>

## <a name="use-the-security-center-to-modify-user-tags"></a><span data-ttu-id="90cba-162">Utilizzare il Centro sicurezza per modificare i tag utente</span><span class="sxs-lookup"><span data-stu-id="90cba-162">Use the Security Center to modify user tags</span></span>

1. <span data-ttu-id="90cba-163">Nel Centro sicurezza passare a **Tag utente per la gestione** delle \> **minacce.**</span><span class="sxs-lookup"><span data-stu-id="90cba-163">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="90cba-164">Nella **pagina Tag utente** visualizzata selezionare il tag utente che si desidera visualizzare e quindi fare clic su **Modifica tag.**</span><span class="sxs-lookup"><span data-stu-id="90cba-164">On the **User tags** page that opens, select the user tag that you want to view, and then click **Edit tag**.</span></span>

3. <span data-ttu-id="90cba-165">La procedura guidata per i criteri si apre in **un riquadro a comparsa** Modifica tag. Fare **clic su** Avanti per rivedere e modificare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="90cba-165">The policy wizard opens in an **Edit tag** fly out. Click **Next** to review and modify the settings.</span></span>

   <span data-ttu-id="90cba-166">Al termine, fare clic su **Invia.**</span><span class="sxs-lookup"><span data-stu-id="90cba-166">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-remove-user-tags"></a><span data-ttu-id="90cba-167">Utilizzare il Centro sicurezza per rimuovere i tag utente</span><span class="sxs-lookup"><span data-stu-id="90cba-167">Use the Security Center to remove user tags</span></span>

<span data-ttu-id="90cba-168">**Nota:** non è possibile rimuovere il tag predefinito **dell'account Priority.**</span><span class="sxs-lookup"><span data-stu-id="90cba-168">**Note**: You can't remove the built-in **Priority account** tag.</span></span>

1. <span data-ttu-id="90cba-169">Nel Centro sicurezza passare a **Tag utente per la gestione** delle \> **minacce.**</span><span class="sxs-lookup"><span data-stu-id="90cba-169">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="90cba-170">Nella **pagina Tag utente** visualizzata selezionare il tag utente che si desidera rimuovere, fare clic su Elimina **tag** e quindi selezionare **Sì,** rimuovi nell'avviso visualizzato.</span><span class="sxs-lookup"><span data-stu-id="90cba-170">On the **User tags** page that opens, select the user tag that you want to remove, click **Delete tag**, and then select **Yes, remove** in the warning that appears.</span></span>
