---
title: Tag utente in Microsoft Defender per Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 04/21/2021
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
ms.openlocfilehash: 3ac53891e0eb106ab3681251cc4cb8c969b51f8a
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083117"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a><span data-ttu-id="de282-104">Tag utente in Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="de282-104">User tags in Microsoft Defender for Office 365</span></span>

> [!NOTE]
> <span data-ttu-id="de282-105">La funzionalità tag utente è disponibile in Anteprima, non è disponibile per tutti gli utenti ed è soggetta a modifiche.</span><span class="sxs-lookup"><span data-stu-id="de282-105">The user tags feature is in Preview, isn't available to everyone, and is subject to change.</span></span> <span data-ttu-id="de282-106">Per informazioni sulla pianificazione dei rilasci, vedere la roadmap [Microsoft 365.](https://www.microsoft.com/microsoft-365/roadmap)</span><span class="sxs-lookup"><span data-stu-id="de282-106">For information about the release schedule, check out the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

<span data-ttu-id="de282-107">I tag utente sono identificatori per gruppi specifici di utenti in [Microsoft Defender per Office 365](defender-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="de282-107">User tags are identifiers for specific groups of users in [Microsoft Defender for Office 365](defender-for-office-365.md).</span></span> <span data-ttu-id="de282-108">Esistono due tipi di tag utente:</span><span class="sxs-lookup"><span data-stu-id="de282-108">There are two types of user tags:</span></span>

- <span data-ttu-id="de282-109">**Tag di** sistema: attualmente, [gli account Priority](../../admin/setup/priority-accounts.md) sono l'unico tipo di tag di sistema.</span><span class="sxs-lookup"><span data-stu-id="de282-109">**System tags**: Currently, [Priority accounts](../../admin/setup/priority-accounts.md) is the only type of system tag.</span></span>
- <span data-ttu-id="de282-110">**Tag personalizzati**: questi tag utente vengono creati manualmente.</span><span class="sxs-lookup"><span data-stu-id="de282-110">**Custom tags**: You create these user tags yourself.</span></span>

<span data-ttu-id="de282-111">Se l'organizzazione ha Defender per Office 365 Piano 2 (incluso nell'abbonamento o come componente aggiuntivo), puoi creare tag utente personalizzati oltre a usare il tag degli account di priorità.</span><span class="sxs-lookup"><span data-stu-id="de282-111">If your organization has Defender for Office 365 Plan 2 (included in your subscription or as an add-on), you can create custom user tags in addition to using the priority accounts tag.</span></span>

> [!NOTE]
> <span data-ttu-id="de282-112">Attualmente, è possibile applicare i tag utente solo agli utenti delle cassette postali.</span><span class="sxs-lookup"><span data-stu-id="de282-112">Currently, you can only apply user tags to mailbox users.</span></span>

<span data-ttu-id="de282-113">Dopo aver applicato tag di sistema o tag personalizzati agli utenti, è possibile utilizzare tali tag come filtri in avvisi, report e indagini:</span><span class="sxs-lookup"><span data-stu-id="de282-113">After you apply system tags or custom tags to users, you can use those tags as filters in alerts, reports, and investigations:</span></span>

- [<span data-ttu-id="de282-114">Avvisi</span><span class="sxs-lookup"><span data-stu-id="de282-114">Alerts</span></span>](alerts.md)
- [<span data-ttu-id="de282-115">Criteri di avviso personalizzati</span><span class="sxs-lookup"><span data-stu-id="de282-115">Custom alert policies</span></span>](../../compliance/alert-policies.md#viewing-alerts)
- [<span data-ttu-id="de282-116">Esplora minacce e rilevamenti in tempo reale</span><span class="sxs-lookup"><span data-stu-id="de282-116">Threat Explorer and real-time detections</span></span>](threat-explorer.md)
- [<span data-ttu-id="de282-117">Pagina Entità posta elettronica</span><span class="sxs-lookup"><span data-stu-id="de282-117">Email entity page</span></span>](mdo-email-entity-page.md#other-innovations)
- [<span data-ttu-id="de282-118">Report dello stato di protezione dalle minacce</span><span class="sxs-lookup"><span data-stu-id="de282-118">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="de282-119">Visualizzazioni campagna</span><span class="sxs-lookup"><span data-stu-id="de282-119">Campaign Views</span></span>](campaigns.md)
- <span data-ttu-id="de282-120">Per gli account con priorità, è possibile utilizzare il [report Problemi](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) di posta elettronica per gli account di priorità nell'interfaccia di amministrazione di Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="de282-120">For priority accounts, you can use the [Email issues for priority accounts report](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) in the Exchange admin center (EAC).</span></span>

<span data-ttu-id="de282-121">In questo articolo viene illustrato come configurare i tag utente nel portale Microsoft 365 Defender utente.</span><span class="sxs-lookup"><span data-stu-id="de282-121">This article explains how to configure user tags in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="de282-122">Non esistono cmdlet nel portale Microsoft 365 Defender per gestire i tag utente.</span><span class="sxs-lookup"><span data-stu-id="de282-122">There are no cmdlets in Microsoft 365 Defender portal to manage user tags.</span></span>

<span data-ttu-id="de282-123">Per informazioni su come i tag utente fanno parte della strategia per proteggere gli account utente ad alto [impatto,](security-recommendations-for-priority-accounts.md)vedere Suggerimenti per la sicurezza per gli account con priorità in Microsoft 365 .</span><span class="sxs-lookup"><span data-stu-id="de282-123">To see how user tags are part of the strategy to help protect high-impact user accounts, see [Security recommendations for priority accounts in Microsoft 365](security-recommendations-for-priority-accounts.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="de282-124">Che cosa è necessario sapere prima di iniziare?</span><span class="sxs-lookup"><span data-stu-id="de282-124">What do you need to know before you begin?</span></span>

- <span data-ttu-id="de282-125">Per aprire il portale di Microsoft 365 Defender, andare alla pagina <https://security.microsoft.com/>.</span><span class="sxs-lookup"><span data-stu-id="de282-125">You open the Microsoft 365 Defender portal at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="de282-126">Per passare direttamente alla **pagina Tag** utente, aprire <https://security.microsoft.com/securitysettings/userTags> .</span><span class="sxs-lookup"><span data-stu-id="de282-126">To go directly to the **User tags** page, open <https://security.microsoft.com/securitysettings/userTags>.</span></span>

- <span data-ttu-id="de282-127">È necessario disporre delle autorizzazioni nel portale Microsoft 365 Defender per poter eseguire le procedure descritte in questo articolo:</span><span class="sxs-lookup"><span data-stu-id="de282-127">You need to be assigned permissions in the Microsoft 365 Defender portal before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="de282-128">Per creare, modificare ed eliminare tag utente, è necessario essere membri dei gruppi **di** ruoli Gestione organizzazione o Amministratore **sicurezza.**</span><span class="sxs-lookup"><span data-stu-id="de282-128">To create, modify, and delete user tags, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="de282-129">Per aggiungere e rimuovere membri dai tag utente esistenti, è necessario essere membri dei gruppi di ruoli **Gestione** **organizzazione,** Amministratore sicurezza o **Operatore** sicurezza</span><span class="sxs-lookup"><span data-stu-id="de282-129">To add and remove members from existing user tags, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Operator** role groups</span></span>
  - <span data-ttu-id="de282-130">Per l'accesso in sola lettura ai tag utente, è necessario essere membri dei gruppi di ruoli **Lettore** globale o **Lettore** di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="de282-130">For read-only access to user tags, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="de282-131">Per altre informazioni, vedere [Autorizzazioni nel portale di Microsoft 365 Defender](permissions-microsoft-365-security-center.md).</span><span class="sxs-lookup"><span data-stu-id="de282-131">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="de282-132">L'aggiunta di utenti al ruolo Azure Active Directory corrispondente nel interfaccia di amministrazione di Microsoft 365 offre agli utenti le  autorizzazioni necessarie nel portale di Microsoft 365 Defender e le autorizzazioni per altre funzionalità di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="de282-132">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="de282-133">Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="de282-133">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="de282-134">La gestione dei tag utente è controllata dai **ruoli Lettore tag** **e Gestione** tag.</span><span class="sxs-lookup"><span data-stu-id="de282-134">User tag management is controlled by the **Tag Reader** and **Tag Manager** roles.</span></span>

- <span data-ttu-id="de282-135">È inoltre possibile gestire e monitorare gli account di priorità nella interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="de282-135">You can also manage and monitor priority accounts in the Microsoft 365 admin center.</span></span> <span data-ttu-id="de282-136">Per istruzioni, vedere [Gestire e monitorare gli account con priorità.](../../admin/setup/priority-accounts.md)</span><span class="sxs-lookup"><span data-stu-id="de282-136">For instructions, see [Manage and monitor priority accounts](../../admin/setup/priority-accounts.md).</span></span>

- <span data-ttu-id="de282-137">Per informazioni sulla protezione degli _account con privilegi_ (account amministratore), vedere questo [argomento.](/azure/architecture/framework/security/critical-impact-accounts)</span><span class="sxs-lookup"><span data-stu-id="de282-137">For information about securing _privileged accounts_ (admin accounts), see [this topic](/azure/architecture/framework/security/critical-impact-accounts).</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-user-tags"></a><span data-ttu-id="de282-138">Usare il portale Microsoft 365 Defender per creare tag utente</span><span class="sxs-lookup"><span data-stu-id="de282-138">Use the Microsoft 365 Defender portal to create user tags</span></span>

1. <span data-ttu-id="de282-139">Nel portale Microsoft 365 Defender, passare **a** Impostazioni \> **e-mail & collaborazione** Tag \> **utente**.</span><span class="sxs-lookup"><span data-stu-id="de282-139">In the Microsoft 365 Defender portal, go to **Settings** \> **Email & collaboration** \> **User tags**.</span></span>

2. <span data-ttu-id="de282-140">Nella pagina **Tag utente** fare clic su Crea icona tag ![ Crea ](../../media/m365-cc-sc-create-icon.png) **tag**.</span><span class="sxs-lookup"><span data-stu-id="de282-140">On the **User tags** page, click ![Create tag icon](../../media/m365-cc-sc-create-icon.png) **Create tag**.</span></span>

3. <span data-ttu-id="de282-141">La **procedura guidata Crea tag** si apre in un nuovo riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="de282-141">The **Create tag** wizard opens in a new flyout.</span></span> <span data-ttu-id="de282-142">Nella pagina **Definisci tag** configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="de282-142">On the **Define tag** page, configure the following settings:</span></span>
   - <span data-ttu-id="de282-143">**Nome**: immettere un nome descrittivo univoco per il tag.</span><span class="sxs-lookup"><span data-stu-id="de282-143">**Name**: Enter a unique, descriptive name for the tag.</span></span> <span data-ttu-id="de282-144">Questo è il valore che vedrai e userai.</span><span class="sxs-lookup"><span data-stu-id="de282-144">This is the value that you'll see and use.</span></span> <span data-ttu-id="de282-145">Tieni presente che non puoi rinominare un tag dopo averlo creato.</span><span class="sxs-lookup"><span data-stu-id="de282-145">Note that you can't rename a tag after you create it.</span></span>
   - <span data-ttu-id="de282-146">**Descrizione:** immettere una descrizione facoltativa per il tag.</span><span class="sxs-lookup"><span data-stu-id="de282-146">**Description**: Enter an optional description for the tag.</span></span>

   <span data-ttu-id="de282-147">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="de282-147">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="de282-148">Nella pagina **Assegna membri** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="de282-148">On the **Assign members** page, do either of the following steps:</span></span>
   - <span data-ttu-id="de282-149">Fare ![ clic su Aggiungi membri icona Aggiungi ](../../media/m365-cc-sc-create-icon.png) **membri**.</span><span class="sxs-lookup"><span data-stu-id="de282-149">Click ![Add members icon](../../media/m365-cc-sc-create-icon.png) **Add members**.</span></span> <span data-ttu-id="de282-150">Nel riquadro a comparsa visualizzato eseguire una delle operazioni seguenti per aggiungere singoli utenti o gruppi:</span><span class="sxs-lookup"><span data-stu-id="de282-150">In the fly out that appears, do any of the following steps to add individual users or groups:</span></span>
     - <span data-ttu-id="de282-151">Fare clic nella casella e scorrere l'elenco per selezionare un utente o un gruppo.</span><span class="sxs-lookup"><span data-stu-id="de282-151">Click in the box and scroll through the list to select a user or group.</span></span>
     - <span data-ttu-id="de282-152">Fare clic nella casella e iniziare a digitare per filtrare l'elenco e selezionare un utente o un gruppo.</span><span class="sxs-lookup"><span data-stu-id="de282-152">Click in the box and start typing to filter the list and select a user or group.</span></span>
     - <span data-ttu-id="de282-153">Per aggiungere altri valori, fare clic in un'area vuota della casella.</span><span class="sxs-lookup"><span data-stu-id="de282-153">To add additional values, click in an empty area in the box.</span></span>
     - <span data-ttu-id="de282-154">Per rimuovere singole voci, fare clic su</span><span class="sxs-lookup"><span data-stu-id="de282-154">To remove individual entries, click</span></span> ![Icona Rimuovi voce](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="de282-156">accanto alla voce nella casella.</span><span class="sxs-lookup"><span data-stu-id="de282-156">next to the entry in the box.</span></span>
     - <span data-ttu-id="de282-157">Per rimuovere tutte le voci, fare clic sull'icona Rimuovi voce ![ nell'elemento Utenti e gruppi ](../../media/m365-cc-sc-remove-selection-icon.png) **nn** selezionati sotto la casella.</span><span class="sxs-lookup"><span data-stu-id="de282-157">To remove all entries, click ![Remove entry icon](../../media/m365-cc-sc-remove-selection-icon.png) on the **Selected nn users and nn groups** item below the box.</span></span>

     <span data-ttu-id="de282-158">Al termine, fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="de282-158">When you're finished, click **Add**.</span></span>

     <span data-ttu-id="de282-159">Nella pagina **Assegna membri** è inoltre possibile rimuovere le voci facendo clic sull'icona Elimina accanto alla ![ ](../../media/m365-cc-sc-delete-icon.png) voce.</span><span class="sxs-lookup"><span data-stu-id="de282-159">Back on the **Assign members** page, you can also remove entries by clicking ![Delete icon](../../media/m365-cc-sc-delete-icon.png) next to the entry.</span></span>

   - <span data-ttu-id="de282-160">Fare **clic su** Importa per selezionare un file di testo contenente gli indirizzi di posta elettronica degli utenti o dei gruppi.</span><span class="sxs-lookup"><span data-stu-id="de282-160">Click **Import** to select a text file that contains the email addresses of the users or groups.</span></span> <span data-ttu-id="de282-161">Assicurarsi che il file di testo contenga una voce per riga.</span><span class="sxs-lookup"><span data-stu-id="de282-161">Be sure the text file contains one entry per line.</span></span>

   <span data-ttu-id="de282-162">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="de282-162">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="de282-163">Nella pagina **Rivedi tag** visualizzata rivedere le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="de282-163">On the **Review tag** page that appears, review your settings.</span></span> <span data-ttu-id="de282-164">È possibile selezionare **Modifica** in ogni sezione per modificare le impostazioni all'interno della sezione.</span><span class="sxs-lookup"><span data-stu-id="de282-164">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="de282-165">Oppure è possibile fare clic su **Indietro** o selezionare la pagina specifica della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="de282-165">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="de282-166">Al termine, fare clic su **Invia** e quindi su **Fine.**</span><span class="sxs-lookup"><span data-stu-id="de282-166">When you're finished, click **Submit**, and then click **Done**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-view-user-tags"></a><span data-ttu-id="de282-167">Usare il portale Microsoft 365 Defender per visualizzare i tag utente</span><span class="sxs-lookup"><span data-stu-id="de282-167">Use the Microsoft 365 Defender portal to view user tags</span></span>

1. <span data-ttu-id="de282-168">Nel portale Microsoft 365 Defender, passare **a** Impostazioni \> **e-mail & collaborazione** Tag \> **utente**.</span><span class="sxs-lookup"><span data-stu-id="de282-168">In the Microsoft 365 Defender portal, go to **Settings** \> **Email & collaboration** \> **User tags**.</span></span>

2. <span data-ttu-id="de282-169">Nella **pagina Tag utente** vengono visualizzate le proprietà seguenti nell'elenco dei tag utente:</span><span class="sxs-lookup"><span data-stu-id="de282-169">On the **User tags** page, the following properties are displayed in the list of user tags:</span></span>

   - <span data-ttu-id="de282-170">**Tag**: nome del tag utente.</span><span class="sxs-lookup"><span data-stu-id="de282-170">**Tag**: The name of the user tag.</span></span> <span data-ttu-id="de282-171">Tieni presente che questo include il tag di **sistema dell'account Priority** incorporato.</span><span class="sxs-lookup"><span data-stu-id="de282-171">Note that this includes the built-in **Priority account** system tag.</span></span>
   - <span data-ttu-id="de282-172">**Applicato a**: Numero di membri</span><span class="sxs-lookup"><span data-stu-id="de282-172">**Applied to**: The number of members</span></span>
   - <span data-ttu-id="de282-173">**Data ultima modifica**</span><span class="sxs-lookup"><span data-stu-id="de282-173">**Last modified**</span></span>
   - <span data-ttu-id="de282-174">**Data di creazione**</span><span class="sxs-lookup"><span data-stu-id="de282-174">**Created on**</span></span>

3. <span data-ttu-id="de282-175">Quando si seleziona un tag utente facendo clic sul nome, i dettagli vengono visualizzati in un riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="de282-175">When you select a user tag by clicking on the name, the details are displayed in a flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-modify-user-tags"></a><span data-ttu-id="de282-176">Utilizzare il portale Microsoft 365 Defender per modificare i tag utente</span><span class="sxs-lookup"><span data-stu-id="de282-176">Use the Microsoft 365 Defender portal to modify user tags</span></span>

1. <span data-ttu-id="de282-177">Nel portale Microsoft 365 Defender, passare **a** Impostazioni \> **e-mail & collaborazione** Tag \> **utente**.</span><span class="sxs-lookup"><span data-stu-id="de282-177">In the Microsoft 365 Defender portal, go to **Settings** \> **Email & collaboration** \> **User tags**.</span></span>

2. <span data-ttu-id="de282-178">Nella pagina **Tag utente** selezionare il tag utente nell'elenco e quindi fare clic su Modifica icona tag ![ Modifica ](../../media/m365-cc-sc-edit-icon.png) **tag**.</span><span class="sxs-lookup"><span data-stu-id="de282-178">On the **User tags** page, select the user tag from the list, and then click ![Edit tag icon](../../media/m365-cc-sc-edit-icon.png) **Edit tag**.</span></span>

3. <span data-ttu-id="de282-179">Nel riquadro a comparsa dei dettagli visualizzato, la stessa procedura guidata e le stesse impostazioni sono disponibili come descritto nella sezione Usare il portale di [Microsoft 365 Defender](#use-the-microsoft-365-defender-portal-to-create-user-tags) per creare tag utente più indietro in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="de282-179">In the details flyout that appears, the same wizard and settings are available as described in the [Use the Microsoft 365 Defender portal to create user tags](#use-the-microsoft-365-defender-portal-to-create-user-tags) section earlier in this article.</span></span>

   <span data-ttu-id="de282-180">**Note**:</span><span class="sxs-lookup"><span data-stu-id="de282-180">**Notes**:</span></span>

   - <span data-ttu-id="de282-181">La **pagina Definisci tag** non è disponibile per il tag di sistema dell'account **Priority** predefinito, quindi non puoi rinominare questo tag o modificare la descrizione.</span><span class="sxs-lookup"><span data-stu-id="de282-181">The **Define tag** page is not available for the built-in **Priority account** system tag, so you can't rename this tag or change the description.</span></span>
   - <span data-ttu-id="de282-182">Non è possibile rinominare un tag personalizzato, ma è possibile modificare la descrizione.</span><span class="sxs-lookup"><span data-stu-id="de282-182">You can't rename a custom tag, but you can change the description.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-user-tags"></a><span data-ttu-id="de282-183">Usare il portale Microsoft 365 Defender per rimuovere i tag utente</span><span class="sxs-lookup"><span data-stu-id="de282-183">Use the Microsoft 365 Defender portal to remove user tags</span></span>

> [!NOTE]
> <span data-ttu-id="de282-184">Non è possibile rimuovere il tag di sistema **dell'account Priority** predefinito.</span><span class="sxs-lookup"><span data-stu-id="de282-184">You can't remove the built-in **Priority account** system tag.</span></span>

1. <span data-ttu-id="de282-185">Nel portale Microsoft 365 Defender, passare **a** Impostazioni \> **e-mail & collaborazione** Tag \> **utente**.</span><span class="sxs-lookup"><span data-stu-id="de282-185">In the Microsoft 365 Defender portal, go to **Settings** \> **Email & collaboration** \> **User tags**.</span></span>

2. <span data-ttu-id="de282-186">Nella pagina **Tag utente** selezionare il tag utente nell'elenco e quindi fare clic su Elimina tag icona ![ Elimina ](../../media/m365-cc-sc-delete-icon.png) **tag**.</span><span class="sxs-lookup"><span data-stu-id="de282-186">On the **User tags** page, select the user tag from the list, and then click ![Delete tag icon](../../media/m365-cc-sc-delete-icon.png) **Delete tag**.</span></span>

3. <span data-ttu-id="de282-187">Leggere l'avviso nella finestra di dialogo di conferma visualizzata e quindi fare clic su **Sì, rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="de282-187">Read the warning in the confirmation dialog that appears, and then click **Yes, remove**.</span></span>
