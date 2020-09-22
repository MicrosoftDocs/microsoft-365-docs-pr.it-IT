---
title: Tag utente
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
description: Gli amministratori possono imparare a identificare gruppi specifici di utenti con tag utente in Oiffce 365 ATP piano 2. Il filtro tag è disponibile tra gli avvisi, i report e le indagini di Office 365 ATP per identificare rapidamente gli utenti contrassegnati.
ms.openlocfilehash: d47c5c00e3cf0362c44aebc18d11db4bba68a149
ms.sourcegitcommit: e5ac81132cc5fd248350627a3cc7b3c640f53b6e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "48210027"
---
# <a name="user-tags-in-the-microsoft-security-center"></a><span data-ttu-id="48a5e-104">Tag utente nel centro protezione Microsoft</span><span class="sxs-lookup"><span data-stu-id="48a5e-104">User tags in the Microsoft Security Center</span></span>

<span data-ttu-id="48a5e-105">I tag utente sono identificatori di gruppi specifici di utenti in [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="48a5e-105">User tags are identifiers for specific groups of users in [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md).</span></span> <span data-ttu-id="48a5e-106">Gli [account di priorità](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) sono un tipo di tag utente.</span><span class="sxs-lookup"><span data-stu-id="48a5e-106">[Priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) are a type of user tag.</span></span> <span data-ttu-id="48a5e-107">Se l'organizzazione dispone di Office 365 ATP piano 2 (incluso nell'abbonamento o come componente aggiuntivo), è possibile creare tag utente personalizzati oltre a utilizzare il tag account prioritari.</span><span class="sxs-lookup"><span data-stu-id="48a5e-107">If your organization has Office 365 ATP Plan 2 (included in your subscription or as an add-on), you can create custom user tags in addition to using the priority accounts tag.</span></span>

<span data-ttu-id="48a5e-108">Dopo aver applicato i tag a utenti specifici, è possibile utilizzare tali tag come filtri in avvisi, rapporti ed indagini:</span><span class="sxs-lookup"><span data-stu-id="48a5e-108">After you apply tags to specific users, you can use those tags as filters in alerts, reports, and investigations:</span></span>

- [<span data-ttu-id="48a5e-109">Avvisi nel centro sicurezza & conformità</span><span class="sxs-lookup"><span data-stu-id="48a5e-109">Alerts in the Security & Compliance Center</span></span>](alerts.md)
- [<span data-ttu-id="48a5e-110">Esplora minacce e rilevamenti in tempo reale</span><span class="sxs-lookup"><span data-stu-id="48a5e-110">Threat Explorer and real-time detections</span></span>](threat-explorer.md)
- [<span data-ttu-id="48a5e-111">Report dello stato di protezione dalle minacce</span><span class="sxs-lookup"><span data-stu-id="48a5e-111">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="48a5e-112">Visualizzazioni campagna</span><span class="sxs-lookup"><span data-stu-id="48a5e-112">Campaign Views</span></span>](campaigns.md)

<span data-ttu-id="48a5e-113">In questo articolo viene illustrato come configurare i tag utente nel centro sicurezza.</span><span class="sxs-lookup"><span data-stu-id="48a5e-113">This article explains how to configure user tags in the Security Center.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="48a5e-114">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="48a5e-114">What do you need to know before you begin?</span></span>

- <span data-ttu-id="48a5e-115">Si apre il Centro sicurezza in <https://security.microsoft.com/> .</span><span class="sxs-lookup"><span data-stu-id="48a5e-115">You open the Security Center at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="48a5e-116">Per passare direttamente alla pagina **tag utente** , Apri <https://security.microsoft.com/securitysettings/userTags> .</span><span class="sxs-lookup"><span data-stu-id="48a5e-116">To go directly to the **User tags** page, open <https://security.microsoft.com/securitysettings/userTags>.</span></span>

- <span data-ttu-id="48a5e-117">Per creare, modificare o rimuovere tag utente, è necessario essere membri dei gruppi di ruoli **Gestione organizzazione** o **amministratore sicurezza** nel centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="48a5e-117">To create, modify, or remove user tags, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="48a5e-118">Per altre informazioni, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="48a5e-118">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="48a5e-119">È inoltre possibile gestire e monitorare gli account prioritari nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="48a5e-119">You can also manage and monitor priority accounts in the Microsoft 365 admin center.</span></span> <span data-ttu-id="48a5e-120">Per istruzioni, vedere [Manage and monitor Priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span><span class="sxs-lookup"><span data-stu-id="48a5e-120">For instructions, see [Manage and monitor priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span></span>

## <a name="use-the-security-center-to-create-user-tags"></a><span data-ttu-id="48a5e-121">Utilizzare il Centro sicurezza per creare tag utente</span><span class="sxs-lookup"><span data-stu-id="48a5e-121">Use the Security Center to create user tags</span></span>

1. <span data-ttu-id="48a5e-122">Nel centro sicurezza, andare a **Impostazioni** di \> **posta elettronica & di collaborazione** \> **tag utente**.</span><span class="sxs-lookup"><span data-stu-id="48a5e-122">In the Security Center, go to **Settings** \> **Email & collaboration** \> **User tags**.</span></span>

2. <span data-ttu-id="48a5e-123">Nella pagina **tag utente** visualizzata, fare clic su **Crea tag**.</span><span class="sxs-lookup"><span data-stu-id="48a5e-123">On the **User tags** page that opens, click **Create tag**.</span></span>

3. <span data-ttu-id="48a5e-124">La creazione guidata **tag** viene aperta in un nuovo volo. Nella pagina **Definisci Tag** configurare le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="48a5e-124">The **Create tag** wizard opens in a new fly out. On the **Define tag** page, configure the following settings:</span></span>

   - <span data-ttu-id="48a5e-125">**Nome**: immettere un nome descrittivo univoco per il tag.</span><span class="sxs-lookup"><span data-stu-id="48a5e-125">**Name**: Enter a unique, descriptive name for the tag.</span></span> <span data-ttu-id="48a5e-126">Questo è il valore che verrà visualizzato e utilizzato.</span><span class="sxs-lookup"><span data-stu-id="48a5e-126">This is the value that you'll see and use.</span></span>

   - <span data-ttu-id="48a5e-127">**Descrizione**: immettere una descrizione facoltativa per il tag.</span><span class="sxs-lookup"><span data-stu-id="48a5e-127">**Description**: Enter an optional description for the tag.</span></span>

   <span data-ttu-id="48a5e-128">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="48a5e-128">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="48a5e-129">Nella pagina **assegnare le cassette postali** , eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="48a5e-129">On the **Assign mailboxes** page, do either of the following steps:</span></span>

   - <span data-ttu-id="48a5e-130">Fare clic su **Aggiungi cassette postali**.</span><span class="sxs-lookup"><span data-stu-id="48a5e-130">Click **Add mailboxes**.</span></span> <span data-ttu-id="48a5e-131">Nel volo che viene visualizzato, eseguire una delle operazioni seguenti per aggiungere singoli utenti o gruppi:</span><span class="sxs-lookup"><span data-stu-id="48a5e-131">In the fly out that appears, do any of the following steps to add individual users or groups:</span></span>

     - <span data-ttu-id="48a5e-132">Fare clic nella casella e scorrere l'elenco per selezionare un utente o un gruppo.</span><span class="sxs-lookup"><span data-stu-id="48a5e-132">Click in the box and scroll through the list to select a user or group.</span></span>
     - <span data-ttu-id="48a5e-133">Fare clic nella casella e iniziare a digitare per filtrare l'elenco e selezionare un utente o un gruppo.</span><span class="sxs-lookup"><span data-stu-id="48a5e-133">Click in the box and start typing to filter the list and select a user or group.</span></span>
     - <span data-ttu-id="48a5e-134">Per aggiungere ulteriori valori, fare clic in un'area vuota nella casella.</span><span class="sxs-lookup"><span data-stu-id="48a5e-134">To add additional values, click in an empty area in the box.</span></span>
     - <span data-ttu-id="48a5e-135">Per rimuovere singole voci dalla casella, fare clic su **Rimuovi** ![ icona Rimuovi ](../../media/scc-remove-icon.png) nell'utente o nel gruppo nella casella.</span><span class="sxs-lookup"><span data-stu-id="48a5e-135">To remove individual entries from the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user or group in the box.</span></span>
     - <span data-ttu-id="48a5e-136">Per rimuovere le voci esistenti dall'elenco sotto la casella, fare clic su **Rimuovi** ![ icona Rimuovi ](../../media/scc-remove-icon.png) la voce.</span><span class="sxs-lookup"><span data-stu-id="48a5e-136">To remove existing entries from the list below the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) the entry.</span></span>

     <span data-ttu-id="48a5e-137">Al termine, fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="48a5e-137">When you're finished, click **Add**.</span></span>

   - <span data-ttu-id="48a5e-138">Fare clic su **Importa** per selezionare un file di testo contenente gli indirizzi di posta elettronica degli utenti o dei gruppi.</span><span class="sxs-lookup"><span data-stu-id="48a5e-138">Click **Import** to select a text file that contains the email addresses of the users or groups.</span></span> <span data-ttu-id="48a5e-139">Verificare che il file di testo contenga una voce per riga.</span><span class="sxs-lookup"><span data-stu-id="48a5e-139">Be sure the text file contains one entry per line.</span></span>

   <span data-ttu-id="48a5e-140">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="48a5e-140">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="48a5e-141">Nella pagina **Revisione Tag** , esaminare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="48a5e-141">On the **Review tag** page, review your settings.</span></span> <span data-ttu-id="48a5e-142">Per apportare modifiche, è possibile fare clic su **modifica** nella sezione specifica.</span><span class="sxs-lookup"><span data-stu-id="48a5e-142">You can click **Edit** in the specific section to make changes.</span></span>

   <span data-ttu-id="48a5e-143">Al termine, fare clic su **Invia**.</span><span class="sxs-lookup"><span data-stu-id="48a5e-143">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-view-user-tags"></a><span data-ttu-id="48a5e-144">Utilizzare il Centro sicurezza per visualizzare i tag utente</span><span class="sxs-lookup"><span data-stu-id="48a5e-144">Use the Security Center to view user tags</span></span>

1. <span data-ttu-id="48a5e-145">Nel centro sicurezza, andare a **Impostazioni** di \> **posta elettronica & di collaborazione** \> **tag utente**.</span><span class="sxs-lookup"><span data-stu-id="48a5e-145">In the Security Center, go to **Settings** \> **Email & collaboration** \> **User tags**.</span></span>

2. <span data-ttu-id="48a5e-146">Nella pagina **tag utente** che viene visualizzata, selezionare il tag utente che si desidera visualizzare (non fare clic sulla casella di controllo).</span><span class="sxs-lookup"><span data-stu-id="48a5e-146">On the **User tags** page that opens, select the user tag that you want to view (don't click on the checkbox).</span></span>

3. <span data-ttu-id="48a5e-147">Nei dettagli di sola lettura che vengono visualizzati, esaminare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="48a5e-147">In the read-only details fly out that appears, review the settings.</span></span>

   <span data-ttu-id="48a5e-148">Al termine, fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="48a5e-148">When you're finished, click **Close**.</span></span>

## <a name="use-the-security-center-to-modify-user-tags"></a><span data-ttu-id="48a5e-149">Utilizzare il Centro sicurezza per modificare i tag utente</span><span class="sxs-lookup"><span data-stu-id="48a5e-149">Use the Security Center to modify user tags</span></span>

1. <span data-ttu-id="48a5e-150">Nel centro sicurezza, andare a **Impostazioni** di \> **posta elettronica & di collaborazione** \> **tag utente**.</span><span class="sxs-lookup"><span data-stu-id="48a5e-150">In the Security Center, go to **Settings** \> **Email & collaboration** \> **User tags**.</span></span>

2. <span data-ttu-id="48a5e-151">Nella pagina **tag utente** che viene visualizzata, selezionare il tag utente che si desidera visualizzare e quindi fare clic su **Modifica tag**.</span><span class="sxs-lookup"><span data-stu-id="48a5e-151">On the **User tags** page that opens, select the user tag that you want to view, and then click **Edit tag**.</span></span>

3. <span data-ttu-id="48a5e-152">Verrà visualizzata la procedura guidata dei criteri in un **Tag Edit** fly out. Fare clic su **Avanti** per rivedere e modificare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="48a5e-152">The policy wizard opens in an **Edit tag** fly out. Click **Next** to review and modify the settings.</span></span>

   <span data-ttu-id="48a5e-153">Al termine, fare clic su **Invia**.</span><span class="sxs-lookup"><span data-stu-id="48a5e-153">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-remove-user-tags"></a><span data-ttu-id="48a5e-154">Utilizzare il Centro sicurezza per rimuovere i tag utente</span><span class="sxs-lookup"><span data-stu-id="48a5e-154">Use the Security Center to remove user tags</span></span>

<span data-ttu-id="48a5e-155">**Nota**: non è possibile rimuovere il tag dell' **account prioritario** incorporato.</span><span class="sxs-lookup"><span data-stu-id="48a5e-155">**Note**: You can't remove the built-in **Priority account** tag.</span></span>

1. <span data-ttu-id="48a5e-156">Nel centro sicurezza, andare a **Impostazioni** di \> **posta elettronica & di collaborazione** \> **tag utente**.</span><span class="sxs-lookup"><span data-stu-id="48a5e-156">In the Security Center, go to **Settings** \> **Email & collaboration** \> **User tags**.</span></span>

2. <span data-ttu-id="48a5e-157">Nella pagina **tag utente** che viene visualizzata, selezionare il tag utente che si desidera rimuovere, fare clic su **Elimina tag**, quindi selezionare **Sì, Rimuovi** nell'avviso che viene visualizzato.</span><span class="sxs-lookup"><span data-stu-id="48a5e-157">On the **User tags** page that opens, select the user tag that you want to remove, click **Delete tag**, and then select **Yes, remove** in the warning that appears.</span></span>
