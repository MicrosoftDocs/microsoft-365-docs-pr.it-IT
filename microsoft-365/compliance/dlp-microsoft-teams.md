---
title: Prevenzione della perdita dei dati e Microsoft Teams
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Microsoft Teams chat e canali supporta i criteri di prevenzione della perdita dei dati (DLP).
ms.openlocfilehash: e55bfa34b2495465f573bcede3ebda2308dbbbbc
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2021
ms.locfileid: "52583389"
---
# <a name="data-loss-prevention-and-microsoft-teams"></a><span data-ttu-id="83b41-103">Prevenzione della perdita dei dati e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="83b41-103">Data loss prevention and Microsoft Teams</span></span>

<span data-ttu-id="83b41-104">Se l'organizzazione dispone di prevenzione della perdita dei dati (DLP), è possibile definire criteri che impediscono agli utenti di condividere informazioni riservate in un canale Microsoft Teams o una sessione di chat.</span><span class="sxs-lookup"><span data-stu-id="83b41-104">If your organization has data loss prevention (DLP), you can define policies that prevent people from sharing sensitive information in a Microsoft Teams channel or chat session.</span></span> <span data-ttu-id="83b41-105">Ecco alcuni esempi del funzionamento di questa protezione:</span><span class="sxs-lookup"><span data-stu-id="83b41-105">Here are some examples of how this protection works:</span></span>

- <span data-ttu-id="83b41-106">**Esempio 1: Protezione delle informazioni riservate nei messaggi**.</span><span class="sxs-lookup"><span data-stu-id="83b41-106">**Example 1: Protecting sensitive information in messages**.</span></span> <span data-ttu-id="83b41-107">Si supponga che un utente tenti di condividere informazioni riservate in Teams chat o canale con utenti guest (utenti esterni).</span><span class="sxs-lookup"><span data-stu-id="83b41-107">Suppose that someone attempts to share sensitive information in a Teams chat or channel with guests (external users).</span></span> <span data-ttu-id="83b41-108">Se si dispone di un criterio DLP definito per evitare questo problema, i messaggi con informazioni riservate inviate a utenti esterni vengono eliminati.</span><span class="sxs-lookup"><span data-stu-id="83b41-108">If you have a DLP policy defined to prevent this, messages with sensitive information that are sent to external users are deleted.</span></span> <span data-ttu-id="83b41-109">Ciò avviene automaticamente e in pochi secondi, in base alla configurazione del criterio DLP.</span><span class="sxs-lookup"><span data-stu-id="83b41-109">This happens automatically, and within seconds, according to how your DLP policy is configured.</span></span>

    > [!NOTE]
    > <span data-ttu-id="83b41-110">DLP per Microsoft Teams blocca il contenuto sensibile se condiviso con Microsoft Teams utenti che hanno:</span><span class="sxs-lookup"><span data-stu-id="83b41-110">DLP for Microsoft Teams blocks sensitive content when shared with Microsoft Teams users who have:</span></span><br/><span data-ttu-id="83b41-111">- [accesso guest](/MicrosoftTeams/guest-access) in team e canali; o</span><span class="sxs-lookup"><span data-stu-id="83b41-111">- [guest access](/MicrosoftTeams/guest-access) in teams and channels; or</span></span><br/><span data-ttu-id="83b41-112">- [accesso esterno](/MicrosoftTeams/manage-external-access) nelle riunioni e nelle sessioni di chat.</span><span class="sxs-lookup"><span data-stu-id="83b41-112">- [external access](/MicrosoftTeams/manage-external-access) in meetings and chat sessions.</span></span> <p><span data-ttu-id="83b41-113">DLP per le sessioni di chat esterne funzionerà solo se sia il mittente che il destinatario sono in modalità solo Teams e utilizzano Microsoft Teams [federazione nativa.](/microsoftteams/manage-external-access)</span><span class="sxs-lookup"><span data-stu-id="83b41-113">DLP for external chat sessions will only work if both the sender and the receiver are in Teams Only mode and using [Microsoft Teams native federation](/microsoftteams/manage-external-access).</span></span> <span data-ttu-id="83b41-114">DLP per Teams non blocca i messaggi in [interoperabilità](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business) con Skype for Business o con sessioni di chat federate non native.</span><span class="sxs-lookup"><span data-stu-id="83b41-114">DLP for Teams does not block messages in [interop](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business) with Skype for Business or non-native federated chat sessions.</span></span>

- <span data-ttu-id="83b41-115">**Esempio 2: protezione delle informazioni riservate nei documenti**.</span><span class="sxs-lookup"><span data-stu-id="83b41-115">**Example 2: Protecting sensitive information in documents**.</span></span> <span data-ttu-id="83b41-116">Si supponga che un utente tenti di condividere un documento con gli utenti guest in un canale Microsoft Teams o in una chat e che il documento contenga informazioni riservate.</span><span class="sxs-lookup"><span data-stu-id="83b41-116">Suppose that someone attempts to share a document with guests in a Microsoft Teams channel or chat, and the document contains sensitive information.</span></span> <span data-ttu-id="83b41-117">Se si dispone di un criterio DLP definito per evitare questo problema, il documento non verrà aperto per tali utenti.</span><span class="sxs-lookup"><span data-stu-id="83b41-117">If you have a DLP policy defined to prevent this, the document won't open for those users.</span></span> <span data-ttu-id="83b41-118">Il criterio di prevenzione della perdita dei dati deve includere SharePoint e OneDrive per far sì che la protezione sia in vigore.</span><span class="sxs-lookup"><span data-stu-id="83b41-118">Your DLP policy must include SharePoint and OneDrive in order for protection to be in place.</span></span> <span data-ttu-id="83b41-119">Si tratta di un esempio di DLP per SharePoint che viene visualizzato in Microsoft Teams e pertanto richiede che gli utenti siano concessi in licenza per Office 365 DLP (incluso in Office 365 E3), ma non richiedono agli utenti di essere concessi in licenza per Office 365 Advanced Compliance.</span><span class="sxs-lookup"><span data-stu-id="83b41-119">This is an example of DLP for SharePoint that shows up in Microsoft Teams, and therefore requires that users are licensed for Office 365 DLP (included in Office 365 E3), but does not require users to be licensed for Office 365 Advanced Compliance.)</span></span>

## <a name="dlp-licensing-for-microsoft-teams"></a><span data-ttu-id="83b41-120">Licenze DLP per Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="83b41-120">DLP Licensing for Microsoft Teams</span></span>

<span data-ttu-id="83b41-121">[Le funzionalità di prevenzione della](dlp-learn-about-dlp.md) perdita dei dati sono state estese Microsoft Teams messaggi di chat e canali, inclusi i messaggi del canale **privato** per:</span><span class="sxs-lookup"><span data-stu-id="83b41-121">[Data loss prevention](dlp-learn-about-dlp.md) capabilities were extended to include Microsoft Teams chat and channel messages, **including private channel messages** for:</span></span>

- <span data-ttu-id="83b41-122">Office 365 E5/A5</span><span class="sxs-lookup"><span data-stu-id="83b41-122">Office 365 E5/A5</span></span>
- <span data-ttu-id="83b41-123">Microsoft 365 E5/A5</span><span class="sxs-lookup"><span data-stu-id="83b41-123">Microsoft 365 E5/A5</span></span>
- <span data-ttu-id="83b41-124">Microsoft 365 Protezione e governance delle informazioni</span><span class="sxs-lookup"><span data-stu-id="83b41-124">Microsoft 365 Information Protection and Governance</span></span>
- <span data-ttu-id="83b41-125">Office 365 Advanced Compliance</span><span class="sxs-lookup"><span data-stu-id="83b41-125">Office 365 Advanced Compliance</span></span>

<span data-ttu-id="83b41-126">Office 365 e Microsoft 365 E3 includono la protezione DLP per SharePoint Online, OneDrive e Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="83b41-126">Office 365 and Microsoft 365 E3 include DLP protection for SharePoint Online, OneDrive, and Exchange Online.</span></span> <span data-ttu-id="83b41-127">Sono inclusi anche i file condivisi tramite Teams perché Teams utilizza SharePoint Online e OneDrive per condividere i file.</span><span class="sxs-lookup"><span data-stu-id="83b41-127">This also includes files that are shared through Teams because Teams uses SharePoint Online and OneDrive to share files.</span></span>

<span data-ttu-id="83b41-128">Il supporto per la protezione DLP in Teams Chat richiede E5.</span><span class="sxs-lookup"><span data-stu-id="83b41-128">Support for DLP protection in Teams Chat requires E5.</span></span>

<span data-ttu-id="83b41-129">Per altre informazioni sui requisiti di licenza, vedere [Linee guida per le licenze dei servizi a livello di tenant di Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span><span class="sxs-lookup"><span data-stu-id="83b41-129">To learn more about licensing requirements, see [Microsoft 365 Tenant-Level Services Licensing Guidance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="83b41-130">DLP si applica solo ai messaggi effettivi nel thread di chat o canale.</span><span class="sxs-lookup"><span data-stu-id="83b41-130">DLP applies only to the actual messages in the chat or channel thread.</span></span> <span data-ttu-id="83b41-131">Le notifiche di attività, che includono un'anteprima breve dei  messaggi e vengono visualizzate in base alle impostazioni di notifica di un utente, non sono incluse in Teams DLP.</span><span class="sxs-lookup"><span data-stu-id="83b41-131">Activity notifications -- which include a short message preview and appear based on a user's notification settings -- are **not** included in Teams DLP.</span></span> <span data-ttu-id="83b41-132">Tutte le informazioni riservate presenti nella parte del messaggio visualizzata nell'anteprima rimarranno visibili nella notifica anche dopo l'applicazione del criterio DLP e la rimozione delle informazioni riservate del messaggio stesso.</span><span class="sxs-lookup"><span data-stu-id="83b41-132">Any sensitive information present in the part of the message that appears in the preview will remain visible in the notification even after the DLP policy has been applied and removed sensitive information the message itself.</span></span>

## <a name="scope-of-dlp-protection"></a><span data-ttu-id="83b41-133">Ambito della protezione DLP</span><span class="sxs-lookup"><span data-stu-id="83b41-133">Scope of DLP protection</span></span>

<span data-ttu-id="83b41-134">La protezione DLP viene applicata in modo diverso Teams entità.</span><span class="sxs-lookup"><span data-stu-id="83b41-134">DLP protection are applied differently to Teams entities.</span></span>

|<span data-ttu-id="83b41-135">Account utente/Gruppi/Elenco</span><span class="sxs-lookup"><span data-stu-id="83b41-135">User Accounts/Groups/List</span></span>  |<span data-ttu-id="83b41-136">Teams Entità</span><span class="sxs-lookup"><span data-stu-id="83b41-136">Teams Entity</span></span> |<span data-ttu-id="83b41-137">Protezione DLP disponibile</span><span class="sxs-lookup"><span data-stu-id="83b41-137">DLP protection available</span></span>|
|---------|---------|---------|
|<span data-ttu-id="83b41-138">singoli account utente</span><span class="sxs-lookup"><span data-stu-id="83b41-138">individual user accounts</span></span>     |<span data-ttu-id="83b41-139">1:1/n chat</span><span class="sxs-lookup"><span data-stu-id="83b41-139">1:1/n chats</span></span>         |<span data-ttu-id="83b41-140">sì</span><span class="sxs-lookup"><span data-stu-id="83b41-140">yes</span></span>         |
|     |<span data-ttu-id="83b41-141">chat generali</span><span class="sxs-lookup"><span data-stu-id="83b41-141">general chats</span></span>         |<span data-ttu-id="83b41-142">no</span><span class="sxs-lookup"><span data-stu-id="83b41-142">no</span></span>         |
|     |<span data-ttu-id="83b41-143">canali condivisi</span><span class="sxs-lookup"><span data-stu-id="83b41-143">shared channels</span></span>         |<span data-ttu-id="83b41-144">no</span><span class="sxs-lookup"><span data-stu-id="83b41-144">no</span></span>         |
|     |<span data-ttu-id="83b41-145">canali privati</span><span class="sxs-lookup"><span data-stu-id="83b41-145">private channels</span></span>         |<span data-ttu-id="83b41-146">sì</span><span class="sxs-lookup"><span data-stu-id="83b41-146">yes</span></span>         |
|<span data-ttu-id="83b41-147">gruppi di sicurezza/liste di distribuzione</span><span class="sxs-lookup"><span data-stu-id="83b41-147">security groups/distribution lists</span></span>  | <span data-ttu-id="83b41-148">1:1/n chat</span><span class="sxs-lookup"><span data-stu-id="83b41-148">1:1/n chats</span></span>         |<span data-ttu-id="83b41-149">sì</span><span class="sxs-lookup"><span data-stu-id="83b41-149">yes</span></span>         |
|     |<span data-ttu-id="83b41-150">chat generali</span><span class="sxs-lookup"><span data-stu-id="83b41-150">general chats</span></span>         |<span data-ttu-id="83b41-151">no</span><span class="sxs-lookup"><span data-stu-id="83b41-151">no</span></span>         |
|     |<span data-ttu-id="83b41-152">canali condivisi</span><span class="sxs-lookup"><span data-stu-id="83b41-152">shared channels</span></span>         |<span data-ttu-id="83b41-153">no</span><span class="sxs-lookup"><span data-stu-id="83b41-153">no</span></span>      |
|     |<span data-ttu-id="83b41-154">canali privati</span><span class="sxs-lookup"><span data-stu-id="83b41-154">private channels</span></span>         |<span data-ttu-id="83b41-155">sì</span><span class="sxs-lookup"><span data-stu-id="83b41-155">yes</span></span>        |
|<span data-ttu-id="83b41-156">Microsoft 365 gruppo</span><span class="sxs-lookup"><span data-stu-id="83b41-156">Microsoft 365 group</span></span>    |<span data-ttu-id="83b41-157">1:1/n chat</span><span class="sxs-lookup"><span data-stu-id="83b41-157">1:1/n chats</span></span>          |<span data-ttu-id="83b41-158">no</span><span class="sxs-lookup"><span data-stu-id="83b41-158">no</span></span>         |
|     |<span data-ttu-id="83b41-159">chat generali</span><span class="sxs-lookup"><span data-stu-id="83b41-159">general chats</span></span>          |<span data-ttu-id="83b41-160">sì</span><span class="sxs-lookup"><span data-stu-id="83b41-160">yes</span></span>        |
|     |<span data-ttu-id="83b41-161">canali condivisi</span><span class="sxs-lookup"><span data-stu-id="83b41-161">shared channels</span></span>|<span data-ttu-id="83b41-162">sì</span><span class="sxs-lookup"><span data-stu-id="83b41-162">yes</span></span> |
|     |<span data-ttu-id="83b41-163">canali privati</span><span class="sxs-lookup"><span data-stu-id="83b41-163">private channels</span></span>|<span data-ttu-id="83b41-164">no</span><span class="sxs-lookup"><span data-stu-id="83b41-164">no</span></span>| 


## <a name="policy-tips-help-educate-users"></a><span data-ttu-id="83b41-165">I suggerimenti per i criteri aiutano a formare gli utenti</span><span class="sxs-lookup"><span data-stu-id="83b41-165">Policy tips help educate users</span></span>

<span data-ttu-id="83b41-166">Analogamente al funzionamento di DLP in [Exchange, Outlook, Outlook sul Web,](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web) [SharePoint Online, siti OneDrive for Business](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites)e client desktop [Office](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs), i suggerimenti per i criteri vengono visualizzati quando viene attivata un'azione con un criterio DLP.</span><span class="sxs-lookup"><span data-stu-id="83b41-166">Similar to how DLP works in [Exchange, Outlook, Outlook on the web](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web), [SharePoint Online, OneDrive for Business sites](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites), and [Office desktop clients](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs), policy tips appear when an action triggers with a DLP policy.</span></span> <span data-ttu-id="83b41-167">Ecco un esempio di suggerimento per i criteri:</span><span class="sxs-lookup"><span data-stu-id="83b41-167">Here's an example of a policy tip:</span></span>

![Notifica dei messaggi bloccati in Teams](../media/dlp-teams-blockedmessage-notification.png)

<span data-ttu-id="83b41-169">In questo caso, il mittente ha tentato di condividere un numero di previdenza sociale in Microsoft Teams canale.</span><span class="sxs-lookup"><span data-stu-id="83b41-169">Here, the sender attempted to share a social security number in a Microsoft Teams channel.</span></span> <span data-ttu-id="83b41-170">Il **collegamento What can I do?** apre una finestra di dialogo che consente al mittente di risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="83b41-170">The **What can I do?** link opens a dialog box that provides options for the sender to resolve the issue.</span></span> <span data-ttu-id="83b41-171">Si noti che il mittente può scegliere di ignorare il criterio o inviare una notifica a un amministratore per esaminarlo e risolverlo.</span><span class="sxs-lookup"><span data-stu-id="83b41-171">Notice that, the sender can opt to override the policy, or notify an admin to review and resolve it.</span></span>

![Opzioni per risolvere i messaggi bloccati](../media/dlp-teams-blockedmessage-possibleactions.png)

<span data-ttu-id="83b41-173">Nell'organizzazione, è possibile scegliere di consentire agli utenti di ignorare un criterio DLP.</span><span class="sxs-lookup"><span data-stu-id="83b41-173">In your organization, you can choose to allow users to override a DLP policy.</span></span> <span data-ttu-id="83b41-174">Quando si configurano i criteri DLP, è possibile utilizzare i suggerimenti per i criteri predefiniti o [personalizzare i suggerimenti per](#to-customize-policy-tips) i criteri per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="83b41-174">When you configure your DLP policies, you can use the default policy tips, or [customize policy tips](#to-customize-policy-tips) for your organization.</span></span>

<span data-ttu-id="83b41-175">Tornando all'esempio, in cui un mittente ha condiviso un numero di previdenza sociale in un canale Teams, ecco cosa ha visto il destinatario:</span><span class="sxs-lookup"><span data-stu-id="83b41-175">Returning to our example, where a sender shared a social security number in a Teams channel, here's what the recipient saw:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="83b41-176">![Messaggio bloccato](../media/dlp-teams-blockedmessage-notification-to-user.png)</span><span class="sxs-lookup"><span data-stu-id="83b41-176">![Message blocked](../media/dlp-teams-blockedmessage-notification-to-user.png)</span></span>

### <a name="to-customize-policy-tips"></a><span data-ttu-id="83b41-177">Personalizzare suggerimenti per i criteri</span><span class="sxs-lookup"><span data-stu-id="83b41-177">To customize policy tips</span></span>

<span data-ttu-id="83b41-178">Per eseguire questa attività, è necessario disporre di un ruolo con autorizzazioni per modificare i criteri di prevenzione della perdita di dati.</span><span class="sxs-lookup"><span data-stu-id="83b41-178">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="83b41-179">Per ulteriori informazioni, vedere [Autorizzazioni](data-loss-prevention-policies.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="83b41-179">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="83b41-180">Passare al Centro conformità ( [https://compliance.microsoft.com](https://compliance.microsoft.com) ) e accedere.</span><span class="sxs-lookup"><span data-stu-id="83b41-180">Go to the Compliance Center ([https://compliance.microsoft.com](https://compliance.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="83b41-181">Scegliere **Prevenzione della perdita dei dati** > **Criteri**.</span><span class="sxs-lookup"><span data-stu-id="83b41-181">Choose **Data loss prevention** > **Policy**.</span></span>

3. <span data-ttu-id="83b41-182">Selezionare un criterio e accanto a **Impostazioni criteri** scegliere **Modifica.**</span><span class="sxs-lookup"><span data-stu-id="83b41-182">Select a policy, and next to **Policy settings**, choose **Edit**.</span></span>

4. <span data-ttu-id="83b41-183">Creare una nuova regola o modificare una regola esistente per il criterio.</span><span class="sxs-lookup"><span data-stu-id="83b41-183">Either create a new rule, or edit an existing rule for the policy.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="83b41-184">![Modifica di una regola per un criterio](../media/dlp-teams-editrule.png)</span><span class="sxs-lookup"><span data-stu-id="83b41-184">![Editing a rule for a policy](../media/dlp-teams-editrule.png)</span></span>

5. <span data-ttu-id="83b41-185">Nella scheda **Notifiche utente** seleziona Personalizza il testo del messaggio **di posta** elettronica e/o Personalizza le opzioni del testo del **suggerimento per i** criteri.</span><span class="sxs-lookup"><span data-stu-id="83b41-185">On the **User notifications** tab, select **Customize the email text** and/or **Customize the policy tip text** options.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="83b41-186">![Personalizzare le notifiche utente e i suggerimenti per i criteri](../media/dlp-teams-editrule-usernotifications.png)</span><span class="sxs-lookup"><span data-stu-id="83b41-186">![Customize user notifications and policy tips](../media/dlp-teams-editrule-usernotifications.png)</span></span><br/>  

6. <span data-ttu-id="83b41-187">Specificare il testo che si desidera utilizzare per le notifiche di posta elettronica e/o i suggerimenti per i criteri, quindi scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="83b41-187">Specify the text you want to use for email notifications and/or policy tips, and then choose **Save**.</span></span>

7. <span data-ttu-id="83b41-188">Nella scheda **Impostazioni criteri** scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="83b41-188">On the **Policy settings** tab, choose **Save**.</span></span>

<span data-ttu-id="83b41-189">Consentire circa un'ora che le modifiche funzionino nel data center e si sincronizzano con gli account utente.</span><span class="sxs-lookup"><span data-stu-id="83b41-189">Allow approximately one hour for your changes to work their way through your data center and sync to user accounts.</span></span>
 <!-- why are these syncing to user accounts? -->

## <a name="add-microsoft-teams-as-a-location-to-existing-dlp-policies"></a><span data-ttu-id="83b41-190">Aggiungere Microsoft Teams come ubicazione per i criteri di prevenzione della perdita dei dati esistenti</span><span class="sxs-lookup"><span data-stu-id="83b41-190">Add Microsoft Teams as a location to existing DLP policies</span></span>

<span data-ttu-id="83b41-191">Per eseguire questa attività, è necessario disporre di un ruolo con autorizzazioni per modificare i criteri di prevenzione della perdita di dati.</span><span class="sxs-lookup"><span data-stu-id="83b41-191">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="83b41-192">Per ulteriori informazioni, vedere [Autorizzazioni](data-loss-prevention-policies.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="83b41-192">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="83b41-193">Passare al Centro conformità ( [https://compliance.microsoft.com](https://compliance.microsoft.com) ) e accedere.</span><span class="sxs-lookup"><span data-stu-id="83b41-193">Go to the Compliance Center ([https://compliance.microsoft.com](https://compliance.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="83b41-194">Scegliere **Prevenzione della perdita dei dati** > **Criteri**.</span><span class="sxs-lookup"><span data-stu-id="83b41-194">Choose **Data loss prevention** > **Policy**.</span></span>

3. <span data-ttu-id="83b41-195">Selezionare un criterio e osservare i valori in **Posizioni**.</span><span class="sxs-lookup"><span data-stu-id="83b41-195">Select a policy, and look at the values under **Locations**.</span></span> <span data-ttu-id="83b41-196">Se vengono visualizzati **Teams messaggi di chat e canali,** è tutto impostato.</span><span class="sxs-lookup"><span data-stu-id="83b41-196">If you see **Teams chat and channel messages**, you're all set.</span></span> <span data-ttu-id="83b41-197">In caso contrario, fare clic su **Modifica.**</span><span class="sxs-lookup"><span data-stu-id="83b41-197">If you don't, click **Edit**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="83b41-198">![Percorsi per i criteri esistenti](../media/dlp-teams-editexistingpolicy.png)</span><span class="sxs-lookup"><span data-stu-id="83b41-198">![Locations for existing policy](../media/dlp-teams-editexistingpolicy.png)</span></span>

4. <span data-ttu-id="83b41-199">Nella colonna **Stato** attivare il criterio per i messaggi di chat e canali **Teams messaggi di chat e canali.**</span><span class="sxs-lookup"><span data-stu-id="83b41-199">In the **Status** column, turn the policy on for **Teams chat and channel messages**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="83b41-200">![DLP per Teams chat e canali](../media/dlp-teams-addteamschatschannels.png)</span><span class="sxs-lookup"><span data-stu-id="83b41-200">![DLP for Teams chats and channels](../media/dlp-teams-addteamschatschannels.png)</span></span>

5. <span data-ttu-id="83b41-201">Nella scheda **Scegli posizioni** mantenere l'impostazione predefinita di tutti gli account oppure selezionare Consenti di scegliere **posizioni specifiche.**</span><span class="sxs-lookup"><span data-stu-id="83b41-201">On the **Choose locations** tab, keep the default setting of all accounts, or select **Let me choose specific locations**.</span></span> <span data-ttu-id="83b41-202">È possibile specificare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="83b41-202">You can specify:</span></span>

    1. <span data-ttu-id="83b41-203">fino a 1000 singoli account da includere o escludere</span><span class="sxs-lookup"><span data-stu-id="83b41-203">up to 1000 individual accounts to include or exclude</span></span>
    1. <span data-ttu-id="83b41-204">liste di distribuzione e gruppi di sicurezza da includere o escludere.</span><span class="sxs-lookup"><span data-stu-id="83b41-204">distribution lists and security groups to include or exclude.</span></span> 
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**--> 
    
6. <span data-ttu-id="83b41-205">Quindi scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="83b41-205">Then choose **Next**.</span></span>

7. <span data-ttu-id="83b41-206">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="83b41-206">Click **Save**.</span></span>

<span data-ttu-id="83b41-207">Consentire circa un'ora che le modifiche funzionino nel data center e si sincronizzano con gli account utente.</span><span class="sxs-lookup"><span data-stu-id="83b41-207">Allow approximately one hour for your changes to work their way through your data center and sync to user accounts.</span></span>
<!-- again, why user accounts? -->

## <a name="define-a-new-dlp-policy-for-microsoft-teams"></a><span data-ttu-id="83b41-208">Definire nuovi criteri di prevenzione della perdita dei dati per Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="83b41-208">Define a new DLP policy for Microsoft Teams</span></span>

<span data-ttu-id="83b41-209">Per eseguire questa attività, è necessario disporre di un ruolo con autorizzazioni per modificare i criteri di prevenzione della perdita di dati.</span><span class="sxs-lookup"><span data-stu-id="83b41-209">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="83b41-210">Per ulteriori informazioni, vedere [Autorizzazioni](data-loss-prevention-policies.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="83b41-210">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="83b41-211">Passare al Centro conformità ( [https://compliance.microsoft.com](https://compliance.microsoft.com) ) e accedere.</span><span class="sxs-lookup"><span data-stu-id="83b41-211">Go to the Compliance Center ([https://compliance.microsoft.com](https://compliance.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="83b41-212">Scegliere **Prevenzione della perdita dei dati** > **Criteri** > **+ Crea un criterio**.</span><span class="sxs-lookup"><span data-stu-id="83b41-212">Choose **Data loss prevention** > **Policy** > **+ Create a policy**.</span></span>

3. <span data-ttu-id="83b41-213">Scegliere un [modello](data-loss-prevention-policies.md#dlp-policy-templates)e quindi scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="83b41-213">Choose a [template](data-loss-prevention-policies.md#dlp-policy-templates), and then choose **Next**.</span></span>

    <span data-ttu-id="83b41-214">In questo esempio è stato scelto il modello Dati personali degli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="83b41-214">In our example, we chose the U.S. Personally Identifiable Information Data template.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="83b41-215">![Modello di privacy per i criteri DLP](../media/dlp-teams-createnewpolicy-template.png)</span><span class="sxs-lookup"><span data-stu-id="83b41-215">![Privacy template for DLP policy](../media/dlp-teams-createnewpolicy-template.png)</span></span><br/>

4. <span data-ttu-id="83b41-216">Nella scheda **Assegnare un nome al** criterio specificare un nome e una descrizione per il criterio e quindi scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="83b41-216">On the **Name your policy** tab, specify a name and description for the policy, and then choose **Next**.</span></span>

5. <span data-ttu-id="83b41-217">Nella scheda **Scegli posizioni** mantenere l'impostazione predefinita di tutti gli account oppure selezionare Consenti di scegliere **posizioni specifiche.**</span><span class="sxs-lookup"><span data-stu-id="83b41-217">On the **Choose locations** tab, keep the default setting of all accounts, or select **Let me choose specific locations**.</span></span> <span data-ttu-id="83b41-218">È possibile specificare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="83b41-218">You can specify:</span></span>

    1. <span data-ttu-id="83b41-219">fino a 1000 singoli account da includere o escludere</span><span class="sxs-lookup"><span data-stu-id="83b41-219">up to 1000 individual accounts to include or exclude</span></span>
    1. <span data-ttu-id="83b41-220">liste di distribuzione e gruppi di sicurezza da includere o escludere.</span><span class="sxs-lookup"><span data-stu-id="83b41-220">distribution lists and security groups to include or exclude.</span></span> <span data-ttu-id="83b41-221">**Si tratta di una funzionalità di anteprima pubblica.**</span><span class="sxs-lookup"><span data-stu-id="83b41-221">**This is a public preview feature.**</span></span>
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**-->  

    ![Percorsi dei criteri DLP](../media/dlp-teams-selectlocationsnewpolicy.png)

    > [!NOTE]
    > <span data-ttu-id="83b41-223">Se si desidera verificare che i documenti contenenti informazioni riservate non siano condivisi in modo inappropriato in Teams, verificare che i siti e gli account **OneDrive** di **SharePoint** siano attivati, insieme ai messaggi di chat e canali di **Teams**.</span><span class="sxs-lookup"><span data-stu-id="83b41-223">If you want to make sure documents that contain sensitive information are not shared inappropriately in Teams, make sure **SharePoint sites** and **OneDrive accounts** are turned on, along with **Teams chat and channel messages**.</span></span>

6. <span data-ttu-id="83b41-224">Nella scheda **Impostazioni criteri,** in **Personalizza** il tipo di contenuto che si desidera proteggere, mantenere le impostazioni semplici predefinite oppure scegliere **Usa impostazioni avanzate** e quindi **avanti.**</span><span class="sxs-lookup"><span data-stu-id="83b41-224">On the **Policy settings** tab, under **Customize the type of content you want to protect**, keep the default simple settings, or choose **Use advanced settings**, and then choose **Next**.</span></span> <span data-ttu-id="83b41-225">Se si scelgono impostazioni avanzate, è possibile creare o modificare le regole per i criteri.</span><span class="sxs-lookup"><span data-stu-id="83b41-225">If you choose advanced settings, you can create or edit rules for your policy.</span></span> <span data-ttu-id="83b41-226">Per informazioni su questo argomento, vedere [Impostazioni semplici e impostazioni avanzate.](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings)</span><span class="sxs-lookup"><span data-stu-id="83b41-226">To get help with this, see [Simple settings vs. advanced settings](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings).</span></span>

7.  <span data-ttu-id="83b41-227">Nella scheda **Impostazioni dei criteri,** in Cosa vuoi fare se rileviamo **informazioni riservate?** esamina le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="83b41-227">On the **Policy settings** tab, under **What do you want to do if we detect sensitive info?**, review the settings.</span></span> <span data-ttu-id="83b41-228">Ecco dove puoi scegliere se mantenere i suggerimenti e le notifiche di [posta](use-notifications-and-policy-tips.md)elettronica predefiniti o personalizzarli.</span><span class="sxs-lookup"><span data-stu-id="83b41-228">Here's where you can choose to keep default [policy tips and email notifications](use-notifications-and-policy-tips.md), or customize them.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="83b41-229">![Impostazioni dei criteri DLP con suggerimenti e notifiche](../media/dlp-teams-policysettings-tipsemails.png)</span><span class="sxs-lookup"><span data-stu-id="83b41-229">![DLP policy settings with tips and notifications](../media/dlp-teams-policysettings-tipsemails.png)</span></span>

    <span data-ttu-id="83b41-230">Al termine della revisione o della modifica delle impostazioni, scegliere **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="83b41-230">When you're finished reviewing or editing settings, choose **Next**.</span></span>

8. <span data-ttu-id="83b41-231">Nella  scheda Impostazioni criteri, in Si desidera attivare il criterio o testare prima gli **elementi?**, scegliere se attivare il [criterio,](dlp-overview-plan-for-dlp.md#policy-deployment)testarlo per primo o mantenerlo disattivato per il momento e quindi scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="83b41-231">On the **Policy settings** tab, under **Do you want to turn on the policy or test things out first?**, choose whether to turn the policy on, [test it first](dlp-overview-plan-for-dlp.md#policy-deployment), or keep it turned off for now, and then choose **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="83b41-232">![Specificare se attivare il criterio](../media/dlp-teams-policysettings-turnonnow.png)</span><span class="sxs-lookup"><span data-stu-id="83b41-232">![Specify whether to turn the policy on](../media/dlp-teams-policysettings-turnonnow.png)</span></span>

9. <span data-ttu-id="83b41-233">Nella scheda **Rivedere le impostazioni** esaminare le impostazioni per il nuovo criterio.</span><span class="sxs-lookup"><span data-stu-id="83b41-233">On the **Review your settings** tab, review the settings for your new policy.</span></span> <span data-ttu-id="83b41-234">Scegliere **Modifica** per apportare modifiche.</span><span class="sxs-lookup"><span data-stu-id="83b41-234">Choose **Edit** to make changes.</span></span> <span data-ttu-id="83b41-235">Al termine, scegliere **Crea**.</span><span class="sxs-lookup"><span data-stu-id="83b41-235">When you're finished, choose **Create**.</span></span>

<span data-ttu-id="83b41-236">Consentire circa un'ora per il funzionamento del nuovo criterio nel data center e la sincronizzazione con gli account utente.</span><span class="sxs-lookup"><span data-stu-id="83b41-236">Allow approximately one hour for your new policy to work its way through your data center and sync to user accounts.</span></span>

## <a name="prevent-external-access-to-sensitive-documents"></a><span data-ttu-id="83b41-237">Prevenire l'accesso esterno ai documenti sensibili</span><span class="sxs-lookup"><span data-stu-id="83b41-237">Prevent external access to sensitive documents</span></span>

<span data-ttu-id="83b41-238">Per assicurarsi che SharePoint documenti contenenti informazioni riservate non siano accessibili da utenti guest esterni da SharePoint o Teams per impostazione predefinita, selezionare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="83b41-238">To ensure that SharePoint documents that contain sensitive information cannot be accessed by external guests either from SharePoint or Teams by default, select the following:</span></span>

- <span data-ttu-id="83b41-239">È possibile assicurarsi che i documenti siano protetti fino all'analisi DLP e li contrassegni come sicuri da condividere contrassegnando i nuovi [file come sensibili per impostazione predefinita.](/sharepoint/sensitive-by-default)</span><span class="sxs-lookup"><span data-stu-id="83b41-239">You can ensure that documents are protected until DLP scans and marks them as safe to share by [marking new files as sensitive by default](/sharepoint/sensitive-by-default).</span></span>

- <span data-ttu-id="83b41-240">Struttura consigliata per il criterio DLP</span><span class="sxs-lookup"><span data-stu-id="83b41-240">Recommended DLP policy structure</span></span>

    - <span data-ttu-id="83b41-241">**Condizioni**</span><span class="sxs-lookup"><span data-stu-id="83b41-241">**Conditions**</span></span>
        - <span data-ttu-id="83b41-242">Il contenuto contiene uno di questi tipi di informazioni riservate: [Selezionare tutto ciò che si applica]</span><span class="sxs-lookup"><span data-stu-id="83b41-242">Content contains any of these sensitive information types: [Select all that apply]</span></span>
        
        - <span data-ttu-id="83b41-243">Il contenuto viene condiviso da Microsoft 365 persone esterne all'organizzazione</span><span class="sxs-lookup"><span data-stu-id="83b41-243">Content is shared from Microsoft 365 with people outside my organization</span></span>
        
          > [!div class="mx-imgBorder"]
          > <span data-ttu-id="83b41-244">![Condizioni DLP per rilevare la condivisione esterna di contenuto sensibile](../media/dlp-teams-external-sharing/external-condition.png)</span><span class="sxs-lookup"><span data-stu-id="83b41-244">![DLP conditions to detect external sharing of sensitive content](../media/dlp-teams-external-sharing/external-condition.png)</span></span>

    - <span data-ttu-id="83b41-245">**Azioni**</span><span class="sxs-lookup"><span data-stu-id="83b41-245">**Actions**</span></span>
        - <span data-ttu-id="83b41-246">Limitare l'accesso al contenuto per gli utenti esterni</span><span class="sxs-lookup"><span data-stu-id="83b41-246">Restrict access to the content for external users</span></span>
        
        - <span data-ttu-id="83b41-247">Inviare una notifica agli utenti tramite messaggio di posta elettronica e suggerimenti per i criteri</span><span class="sxs-lookup"><span data-stu-id="83b41-247">Notify users with email and policy tips</span></span>
        
        - <span data-ttu-id="83b41-248">Inviare i report degli incidenti all'amministratore</span><span class="sxs-lookup"><span data-stu-id="83b41-248">Send incident reports to the Administrator</span></span>
        
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="83b41-249">![Azione DLP per bloccare la condivisione esterna di contenuto sensibile](../media/dlp-teams-external-sharing/external-action.png)</span><span class="sxs-lookup"><span data-stu-id="83b41-249">![DLP action to block external sharing of sensitive content](../media/dlp-teams-external-sharing/external-action.png)</span></span>

<span data-ttu-id="83b41-250">Criteri DLP in azione quando si tenta di condividere un documento in SharePoint contenente informazioni riservate con un guest esterno:</span><span class="sxs-lookup"><span data-stu-id="83b41-250">DLP policy in action when attempting to share a document in SharePoint that contains sensitive information with an external guest:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="83b41-251">![Condivisione esterna bloccata](../media/dlp-teams-external-sharing/external-sharing-blocked.png)</span><span class="sxs-lookup"><span data-stu-id="83b41-251">![External sharing blocked](../media/dlp-teams-external-sharing/external-sharing-blocked.png)</span></span>


<span data-ttu-id="83b41-252">Criteri DLP in azione quando guest tenta di aprire un documento in Teams con blocco esterno:</span><span class="sxs-lookup"><span data-stu-id="83b41-252">DLP policy in action when guest attempts to open a document in Teams with block external:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="83b41-253">![Accesso esterno bloccato](../media/dlp-teams-external-sharing/external-access-blocked.png)</span><span class="sxs-lookup"><span data-stu-id="83b41-253">![External access blocked](../media/dlp-teams-external-sharing/external-access-blocked.png)</span></span>

## <a name="related-articles"></a><span data-ttu-id="83b41-254">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="83b41-254">Related articles</span></span>

- [<span data-ttu-id="83b41-255">Creare, testare e ottimizzare un criterio di prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="83b41-255">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="83b41-256">Inviare notifiche di posta elettronica e visualizzare i suggerimenti per i criteri di prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="83b41-256">Send email notifications and show policy tips for DLP policies</span></span>](use-notifications-and-policy-tips.md)
