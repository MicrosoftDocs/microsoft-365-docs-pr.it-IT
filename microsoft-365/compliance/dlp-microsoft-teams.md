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
description: Ora puoi applicare i criteri DLP Microsoft Teams chat e canali. Leggi questo articolo per saperne di più su come funziona.
ms.openlocfilehash: 9fdce86473dcfbb7ec75b9d371b8782d4141ef57
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572466"
---
# <a name="data-loss-prevention-and-microsoft-teams"></a><span data-ttu-id="afc65-104">Prevenzione della perdita dei dati e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="afc65-104">Data loss prevention and Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="afc65-105">Le funzionalità di prevenzione della perdita di dati sono state recentemente aggiunte ai messaggi di chat e canale Microsoft Teams per gli utenti con licenza Office 365 E5/A5, Microsoft 365 E5/A5, Microsoft 365 Information Protection and Governance o Office 365 Advanced Compliance.</span><span class="sxs-lookup"><span data-stu-id="afc65-105">Data loss prevention capabilities were recently added to Microsoft Teams chat and channel messages for users licensed for Office 365 E5/A5, Microsoft 365 E5/A5, Microsoft 365 Information Protection and Governance or Office 365 Advanced Compliance.</span></span> <span data-ttu-id="afc65-106">Office 365 e Microsoft 365 E3 includono la protezione DLP per SharePoint online, OneDrive e Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="afc65-106">Office 365 and Microsoft 365 E3 include DLP protection for SharePoint Online, OneDrive, and Exchange Online.</span></span> <span data-ttu-id="afc65-107">Ciò include anche i file condivisi tramite Teams perché Teams utilizza SharePoint Online e OneDrive per condividere file.</span><span class="sxs-lookup"><span data-stu-id="afc65-107">This also includes files that are shared through Teams because Teams uses SharePoint Online and OneDrive to share files.</span></span>
<span data-ttu-id="afc65-108">Il supporto per la protezione DLP Teams Chat richiede E5.</span><span class="sxs-lookup"><span data-stu-id="afc65-108">Support for DLP protection in Teams Chat requires E5.</span></span>
<span data-ttu-id="afc65-109">Per altre informazioni sui requisiti di licenza, vedere [Linee guida per le licenze dei servizi a livello di tenant di Microsoft 365](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance).</span><span class="sxs-lookup"><span data-stu-id="afc65-109">To learn more about licensing requirements, see [Microsoft 365 Tenant-Level Services Licensing Guidance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance).</span></span>

## <a name="overview-of-dlp-for-microsoft-teams"></a><span data-ttu-id="afc65-110">Panoramica di DLP e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="afc65-110">Overview of DLP for Microsoft Teams</span></span>

<span data-ttu-id="afc65-111">Di recente, [le funzionalità di prevenzione](dlp-learn-about-dlp.md) della perdita di dati sono state estese per includere Microsoft Teams di chat e canali, inclusi i messaggi di canale **privati**.</span><span class="sxs-lookup"><span data-stu-id="afc65-111">Recently, [data loss prevention](dlp-learn-about-dlp.md) capabilities were extended to include Microsoft Teams chat and channel messages, **including private channel messages**.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="afc65-112">DLP attualmente si applica solo ai messaggi effettivi nel thread di chat o canale.</span><span class="sxs-lookup"><span data-stu-id="afc65-112">DLP currently applies only to the actual messages in the chat or channel thread.</span></span> <span data-ttu-id="afc65-113">Le notifiche di attività, che includono una breve anteprima del  messaggio e vengono visualizzate in base alle impostazioni di notifica di un utente, non sono Teams DLP in questo momento.</span><span class="sxs-lookup"><span data-stu-id="afc65-113">Activity notifications -- which include a short message preview and appear based on a user's notification settings -- are **not** included in Teams DLP at this time.</span></span> <span data-ttu-id="afc65-114">Tutte le informazioni riservate presenti nella parte del messaggio visualizzata nell'anteprima rimarranno visibili nella notifica anche dopo l'applicazione del criterio DLP e la rimozione delle informazioni riservate del messaggio stesso.</span><span class="sxs-lookup"><span data-stu-id="afc65-114">Any sensitive information present in the part of the message that appears in the preview will remain visible in the notification even after the DLP policy has been applied and removed sensitive information the message itself.</span></span>

<span data-ttu-id="afc65-115">Se l'organizzazione dispone di DLP, è ora possibile definire criteri che impediscano agli utenti di condividere informazioni riservate in un canale Microsoft Teams o in una sessione di chat.</span><span class="sxs-lookup"><span data-stu-id="afc65-115">If your organization has DLP, you can now define policies that prevent people from sharing sensitive information in a Microsoft Teams channel or chat session.</span></span> <span data-ttu-id="afc65-116">Ecco alcuni esempi di come funziona questa protezione:</span><span class="sxs-lookup"><span data-stu-id="afc65-116">Here are some examples of how this protection works:</span></span>

- <span data-ttu-id="afc65-117">**Esempio 1: protezione delle informazioni riservate nei messaggi**.</span><span class="sxs-lookup"><span data-stu-id="afc65-117">**Example 1: Protecting sensitive information in messages**.</span></span> <span data-ttu-id="afc65-118">Si supponga che qualcuno tenti di condividere informazioni riservate in Teams chat o canale con ospiti (utenti esterni).</span><span class="sxs-lookup"><span data-stu-id="afc65-118">Suppose that someone attempts to share sensitive information in a Teams chat or channel with guests (external users).</span></span> <span data-ttu-id="afc65-119">Se per evitare questo problema è stato definito un criterio DLP, i messaggi con informazioni riservate inviati a utenti esterni vengono eliminati.</span><span class="sxs-lookup"><span data-stu-id="afc65-119">If you have a DLP policy defined to prevent this, messages with sensitive information that are sent to external users are deleted.</span></span> <span data-ttu-id="afc65-120">Ciò avviene automaticamente e in pochi secondi, in base alla configurazione dei criteri DLP.</span><span class="sxs-lookup"><span data-stu-id="afc65-120">This happens automatically, and within seconds, according to how your DLP policy is configured.</span></span>

    > [!NOTE]
    > <span data-ttu-id="afc65-121">DLP per Microsoft Teams blocca il contenuto sensibile quando condiviso con Microsoft Teams utenti che hanno:</span><span class="sxs-lookup"><span data-stu-id="afc65-121">DLP for Microsoft Teams blocks sensitive content when shared with Microsoft Teams users who have:</span></span><br/><span data-ttu-id="afc65-122">- [accesso degli ospiti](/MicrosoftTeams/guest-access) in team e canali; o</span><span class="sxs-lookup"><span data-stu-id="afc65-122">- [guest access](/MicrosoftTeams/guest-access) in teams and channels; or</span></span><br/><span data-ttu-id="afc65-123">- [accesso esterno nelle](/MicrosoftTeams/manage-external-access) riunioni e nelle sessioni di chat.</span><span class="sxs-lookup"><span data-stu-id="afc65-123">- [external access](/MicrosoftTeams/manage-external-access) in meetings and chat sessions.</span></span> <p><span data-ttu-id="afc65-124">DLP per le sessioni di chat esterne funzionerà solo se sia il mittente che il destinatario sono in modalità Teams solo [e utilizzano Microsoft Teams federazione nativa](/microsoftteams/manage-external-access).</span><span class="sxs-lookup"><span data-stu-id="afc65-124">DLP for external chat sessions will only work if both the sender and the receiver are in Teams Only mode and using [Microsoft Teams native federation](/microsoftteams/manage-external-access).</span></span> <span data-ttu-id="afc65-125">DLP per Teams non blocca i messaggi in [interoperabilità](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business) con Skype for Business o sessioni di chat federate non native.</span><span class="sxs-lookup"><span data-stu-id="afc65-125">DLP for Teams does not block messages in [interop](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business) with Skype for Business or non-native federated chat sessions.</span></span>

- <span data-ttu-id="afc65-126">**Esempio 2: Protezione delle informazioni riservate nei documenti**.</span><span class="sxs-lookup"><span data-stu-id="afc65-126">**Example 2: Protecting sensitive information in documents**.</span></span> <span data-ttu-id="afc65-127">Si supponga che qualcuno tenti di condividere un documento con gli ospiti in un canale Microsoft Teams o in una chat e che il documento contenga informazioni riservate.</span><span class="sxs-lookup"><span data-stu-id="afc65-127">Suppose that someone attempts to share a document with guests in a Microsoft Teams channel or chat, and the document contains sensitive information.</span></span> <span data-ttu-id="afc65-128">Se per evitare questo problema è stato definito un criterio DLP, il documento non si aprirà per tali utenti.</span><span class="sxs-lookup"><span data-stu-id="afc65-128">If you have a DLP policy defined to prevent this, the document won't open for those users.</span></span> <span data-ttu-id="afc65-129">Si noti che in questo caso, i criteri DLP devono includere SharePoint e OneDrive per consentire l'allora in vigore della protezione.</span><span class="sxs-lookup"><span data-stu-id="afc65-129">Note that in this case, your DLP policy must include SharePoint and OneDrive in order for protection to be in place.</span></span> <span data-ttu-id="afc65-130">Si tratta di un esempio di DLP per SharePoint visualizzato in Microsoft Teams e richiede pertanto che gli utenti siano concessi in licenza Office 365 per un DLP (incluso in Office 365 E3), ma non richiedano che gli utenti siano concessi in licenza per Office 365 Advanced Compliance.</span><span class="sxs-lookup"><span data-stu-id="afc65-130">(This is an example of DLP for SharePoint that shows up in Microsoft Teams, and therefore requires that users are licensed for Office 365 DLP (included in Office 365 E3), but does not require users to be licensed for Office 365 Advanced Compliance.)</span></span>

## <a name="policy-tips-help-educate-users"></a><span data-ttu-id="afc65-131">I suggerimenti per i criteri aiutano a educare gli utenti</span><span class="sxs-lookup"><span data-stu-id="afc65-131">Policy tips help educate users</span></span>

<span data-ttu-id="afc65-132">Analogamente al funzionamento di DLP nei client desktop [Exchange, Outlook, Outlook sul Web](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web), [SharePoint Online, OneDrive for Business e](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites)nei client desktop [Office](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs), i suggerimenti per i criteri vengono visualizzati quando un'azione è in conflitto con un criterio DLP.</span><span class="sxs-lookup"><span data-stu-id="afc65-132">Similar to how DLP works in [Exchange, Outlook, Outlook on the web](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web), [SharePoint Online, OneDrive for Business sites](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites), and [Office desktop clients](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs), policy tips appear when an action conflicts with a DLP policy.</span></span> <span data-ttu-id="afc65-133">Ecco un esempio di suggerimento per i criteri:</span><span class="sxs-lookup"><span data-stu-id="afc65-133">Here's an example of a policy tip:</span></span>

![Notifica messaggi bloccata in Teams](../media/dlp-teams-blockedmessage-notification.png)

<span data-ttu-id="afc65-135">In questo caso, il mittente ha tentato di condividere un numero di previdenza sociale in un Microsoft Teams canale.</span><span class="sxs-lookup"><span data-stu-id="afc65-135">In this case, the sender attempted to share a social security number in a Microsoft Teams channel.</span></span> <span data-ttu-id="afc65-136">Il **collegamento Cosa posso fare?** apre una finestra di dialogo che fornisce al mittente le opzioni per risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="afc65-136">The **What can I do?** link opens a dialog box that provides options for the sender to resolve the issue.</span></span> <span data-ttu-id="afc65-137">Si noti che in questo caso, il mittente può scegliere di ignorare il criterio o notificare a un amministratore di esaminarlo e risolverlo.</span><span class="sxs-lookup"><span data-stu-id="afc65-137">Notice that in this case, the sender can opt to override the policy, or notify an admin to review and resolve it.</span></span>

![Opzioni per risolvere il messaggio bloccato](../media/dlp-teams-blockedmessage-possibleactions.png)

<span data-ttu-id="afc65-139">Nell'organizzazione è possibile scegliere di consentire agli utenti di ignorare un criterio DLP.</span><span class="sxs-lookup"><span data-stu-id="afc65-139">In your organization, you can choose to allow users to override a DLP policy.</span></span> <span data-ttu-id="afc65-140">Inoltre, quando si configurano i criteri DLP, è possibile utilizzare i suggerimenti per i criteri predefiniti o personalizzare [i suggerimenti per i criteri](#to-customize-policy-tips) per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="afc65-140">And, when you configure your DLP policies, you can use the default policy tips, or [customize policy tips](#to-customize-policy-tips) for your organization.</span></span>

<span data-ttu-id="afc65-141">Tornando al nostro esempio, in cui un mittente ha condiviso un numero di previdenza sociale in un Teams, ecco cosa ha visto il destinatario:</span><span class="sxs-lookup"><span data-stu-id="afc65-141">Returning to our example, where a sender shared a social security number in a Teams channel, here's what the recipient saw:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="afc65-142">![Messaggio bloccato](../media/dlp-teams-blockedmessage-notification-to-user.png)</span><span class="sxs-lookup"><span data-stu-id="afc65-142">![Message blocked](../media/dlp-teams-blockedmessage-notification-to-user.png)</span></span>

### <a name="to-customize-policy-tips"></a><span data-ttu-id="afc65-143">Personalizzare suggerimenti per i criteri</span><span class="sxs-lookup"><span data-stu-id="afc65-143">To customize policy tips</span></span>

<span data-ttu-id="afc65-144">Per eseguire questa attività, è necessario disporre di un ruolo con autorizzazioni per modificare i criteri di prevenzione della perdita di dati.</span><span class="sxs-lookup"><span data-stu-id="afc65-144">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="afc65-145">Per ulteriori informazioni, vedere [Autorizzazioni](data-loss-prevention-policies.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="afc65-145">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="afc65-146">Passare al Centro conformità & sicurezza ( [https://protection.office.com](https://protection.office.com) ) e accedere.</span><span class="sxs-lookup"><span data-stu-id="afc65-146">Go to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="afc65-147">Scegliere **Prevenzione della perdita dei dati** > **Criteri**.</span><span class="sxs-lookup"><span data-stu-id="afc65-147">Choose **Data loss prevention** > **Policy**.</span></span>

3. <span data-ttu-id="afc65-148">Selezionare un criterio e accanto a **Impostazioni criterio** scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="afc65-148">Select a policy, and next to **Policy settings**, choose **Edit**.</span></span>

4. <span data-ttu-id="afc65-149">Creare una nuova regola o modificare una regola esistente per il criterio.</span><span class="sxs-lookup"><span data-stu-id="afc65-149">Either create a new rule, or edit an existing rule for the policy.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="afc65-150">![Modifica di una regola per un criterio](../media/dlp-teams-editrule.png)</span><span class="sxs-lookup"><span data-stu-id="afc65-150">![Editing a rule for a policy](../media/dlp-teams-editrule.png)</span></span>

5. <span data-ttu-id="afc65-151">Nella scheda **Notifiche utente selezionare** Personalizza il testo della posta elettronica **e/o** Personalizza le opzioni di testo **del suggerimento per i** criteri.</span><span class="sxs-lookup"><span data-stu-id="afc65-151">On the **User notifications** tab, select **Customize the email text** and/or **Customize the policy tip text** options.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="afc65-152">![Personalizzare le notifiche degli utenti e i suggerimenti per i criteri](../media/dlp-teams-editrule-usernotifications.png)</span><span class="sxs-lookup"><span data-stu-id="afc65-152">![Customize user notifications and policy tips](../media/dlp-teams-editrule-usernotifications.png)</span></span><br/>  

6. <span data-ttu-id="afc65-153">Specificare il testo da utilizzare per le notifiche tramite posta elettronica e/o i suggerimenti per i criteri e quindi scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="afc65-153">Specify the text you want to use for email notifications and/or policy tips, and then choose **Save**.</span></span>

7. <span data-ttu-id="afc65-154">Nella scheda **Impostazioni criteri** scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="afc65-154">On the **Policy settings** tab, choose **Save**.</span></span>

<span data-ttu-id="afc65-155">Consentire a circa un'ora che le modifiche si disercino nel data center e si sincronizzino con gli account utente.</span><span class="sxs-lookup"><span data-stu-id="afc65-155">Allow approximately one hour for your changes to work their way through your data center and sync to user accounts.</span></span>
 <!-- why are these syncing to user accounts? -->

## <a name="add-microsoft-teams-as-a-location-to-existing-dlp-policies"></a><span data-ttu-id="afc65-156">Aggiungere Microsoft Teams come ubicazione per i criteri di prevenzione della perdita dei dati esistenti</span><span class="sxs-lookup"><span data-stu-id="afc65-156">Add Microsoft Teams as a location to existing DLP policies</span></span>

<span data-ttu-id="afc65-157">Per eseguire questa attività, è necessario disporre di un ruolo con autorizzazioni per modificare i criteri di prevenzione della perdita di dati.</span><span class="sxs-lookup"><span data-stu-id="afc65-157">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="afc65-158">Per ulteriori informazioni, vedere [Autorizzazioni](data-loss-prevention-policies.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="afc65-158">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="afc65-159">Passare al Centro conformità & sicurezza ( [https://protection.office.com](https://protection.office.com) ) e accedere.</span><span class="sxs-lookup"><span data-stu-id="afc65-159">Go to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="afc65-160">Scegliere **Prevenzione della perdita dei dati** > **Criteri**.</span><span class="sxs-lookup"><span data-stu-id="afc65-160">Choose **Data loss prevention** > **Policy**.</span></span>

3. <span data-ttu-id="afc65-161">Selezionare un criterio e esaminare i valori in **Percorsi**.</span><span class="sxs-lookup"><span data-stu-id="afc65-161">Select a policy, and look at the values under **Locations**.</span></span> <span data-ttu-id="afc65-162">Se vedi Teams **messaggi di chat e** canale , sei pronto.</span><span class="sxs-lookup"><span data-stu-id="afc65-162">If you see **Teams chat and channel messages**, you're all set.</span></span> <span data-ttu-id="afc65-163">In caso di pertanto, fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="afc65-163">If you don't, click **Edit**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="afc65-164">![Percorsi per i criteri esistenti](../media/dlp-teams-editexistingpolicy.png)</span><span class="sxs-lookup"><span data-stu-id="afc65-164">![Locations for existing policy](../media/dlp-teams-editexistingpolicy.png)</span></span>

4. <span data-ttu-id="afc65-165">Nella colonna **Stato** attivare i criteri per i messaggi **di Teams chat e canale**.</span><span class="sxs-lookup"><span data-stu-id="afc65-165">In the **Status** column, turn the policy on for **Teams chat and channel messages**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="afc65-166">![DLP per Teams chat e canali](../media/dlp-teams-addteamschatschannels.png)</span><span class="sxs-lookup"><span data-stu-id="afc65-166">![DLP for Teams chats and channels](../media/dlp-teams-addteamschatschannels.png)</span></span>

5. <span data-ttu-id="afc65-167">Nella scheda **Scegli percorsi** mantenere l'impostazione predefinita di tutti gli account oppure selezionare Lascia **che scelga percorsi specifici**.</span><span class="sxs-lookup"><span data-stu-id="afc65-167">On the **Choose locations** tab, keep the default setting of all accounts, or select **Let me choose specific locations**.</span></span> <span data-ttu-id="afc65-168">È possibile specificare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="afc65-168">You can specify:</span></span>

    1. <span data-ttu-id="afc65-169">fino a 1000 singoli account da includere o escludere</span><span class="sxs-lookup"><span data-stu-id="afc65-169">up to 1000 individual accounts to include or exclude</span></span>
    1. <span data-ttu-id="afc65-170">liste di distribuzione e gruppi di sicurezza da includere o escludere.</span><span class="sxs-lookup"><span data-stu-id="afc65-170">distribution lists and security groups to include or exclude.</span></span> 
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**--> 
    
6. <span data-ttu-id="afc65-171">Quindi scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="afc65-171">Then choose **Next**.</span></span>

7. <span data-ttu-id="afc65-172">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="afc65-172">Click **Save**.</span></span>

<span data-ttu-id="afc65-173">Consentire a circa un'ora che le modifiche si disercino nel data center e si sincronizzino con gli account utente.</span><span class="sxs-lookup"><span data-stu-id="afc65-173">Allow approximately one hour for your changes to work their way through your data center and sync to user accounts.</span></span>
<!-- again, why user accounts? -->

## <a name="define-a-new-dlp-policy-for-microsoft-teams"></a><span data-ttu-id="afc65-174">Definire nuovi criteri di prevenzione della perdita dei dati per Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="afc65-174">Define a new DLP policy for Microsoft Teams</span></span>

<span data-ttu-id="afc65-175">Per eseguire questa attività, è necessario disporre di un ruolo con autorizzazioni per modificare i criteri di prevenzione della perdita di dati.</span><span class="sxs-lookup"><span data-stu-id="afc65-175">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="afc65-176">Per ulteriori informazioni, vedere [Autorizzazioni](data-loss-prevention-policies.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="afc65-176">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="afc65-177">Passare al Centro conformità & sicurezza ( [https://protection.office.com](https://protection.office.com) ) e accedere.</span><span class="sxs-lookup"><span data-stu-id="afc65-177">Go to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="afc65-178">Scegliere **Prevenzione della perdita dei dati** > **Criteri** > **+ Crea un criterio**.</span><span class="sxs-lookup"><span data-stu-id="afc65-178">Choose **Data loss prevention** > **Policy** > **+ Create a policy**.</span></span>

3. <span data-ttu-id="afc65-179">Scegliere un [modello](data-loss-prevention-policies.md#dlp-policy-templates)e quindi **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="afc65-179">Choose a [template](data-loss-prevention-policies.md#dlp-policy-templates), and then choose **Next**.</span></span>

    <span data-ttu-id="afc65-180">Nel nostro esempio, abbiamo scelto il modello dati di informazioni di identificazione personale degli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="afc65-180">In our example, we chose the U.S. Personally Identifiable Information Data template.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="afc65-181">![Modello di privacy per i criteri DLP](../media/dlp-teams-createnewpolicy-template.png)</span><span class="sxs-lookup"><span data-stu-id="afc65-181">![Privacy template for DLP policy](../media/dlp-teams-createnewpolicy-template.png)</span></span><br/>

4. <span data-ttu-id="afc65-182">Nella scheda **Nome criterio** specificare un nome e una descrizione per il criterio e quindi scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="afc65-182">On the **Name your policy** tab, specify a name and description for the policy, and then choose **Next**.</span></span>

5. <span data-ttu-id="afc65-183">Nella scheda **Scegli percorsi** mantenere l'impostazione predefinita di tutti gli account oppure selezionare Lascia **che scelga percorsi specifici**.</span><span class="sxs-lookup"><span data-stu-id="afc65-183">On the **Choose locations** tab, keep the default setting of all accounts, or select **Let me choose specific locations**.</span></span> <span data-ttu-id="afc65-184">È possibile specificare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="afc65-184">You can specify:</span></span>

    1. <span data-ttu-id="afc65-185">fino a 1000 singoli account da includere o escludere</span><span class="sxs-lookup"><span data-stu-id="afc65-185">up to 1000 individual accounts to include or exclude</span></span>
    1. <span data-ttu-id="afc65-186">liste di distribuzione e gruppi di sicurezza da includere o escludere.</span><span class="sxs-lookup"><span data-stu-id="afc65-186">distribution lists and security groups to include or exclude.</span></span> <span data-ttu-id="afc65-187">**Questa è una funzione di anteprima pubblica.**</span><span class="sxs-lookup"><span data-stu-id="afc65-187">**This is a public preview feature.**</span></span>
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**-->  

    ![Percorsi dei criteri DLP](../media/dlp-teams-selectlocationsnewpolicy.png)

    > [!NOTE]
    > <span data-ttu-id="afc65-189">Se si desidera assicurarsi che i documenti che contengono informazioni riservate non siano condivisi in modo inappropriato nel Teams, assicurarsi **che i siti SharePoint** e gli account **OneDrive** siano attivati, insieme Teams messaggi di chat **e canale**.</span><span class="sxs-lookup"><span data-stu-id="afc65-189">If you want to make sure documents that contain sensitive information are not shared inappropriately in Teams, make sure **SharePoint sites** and **OneDrive accounts** are turned on, along with **Teams chat and channel messages**.</span></span>

6. <span data-ttu-id="afc65-190">Nella scheda **Impostazioni criteri,** in **Personalizza il tipo di contenuto che si desidera proteggere**, mantenere le impostazioni semplici predefinite oppure scegliere Usa impostazioni **avanzate** e quindi **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="afc65-190">On the **Policy settings** tab, under **Customize the type of content you want to protect**, keep the default simple settings, or choose **Use advanced settings**, and then choose **Next**.</span></span> <span data-ttu-id="afc65-191">Se si scelgono impostazioni avanzate, è possibile creare o modificare regole per i criteri.</span><span class="sxs-lookup"><span data-stu-id="afc65-191">If you choose advanced settings, you can create or edit rules for your policy.</span></span> <span data-ttu-id="afc65-192">Per ottenere assistenza in questo senso, [vedere Impostazioni semplici e impostazioni](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings)avanzate.</span><span class="sxs-lookup"><span data-stu-id="afc65-192">(To get help with this, see [Simple settings vs. advanced settings](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings).)</span></span>

7.  <span data-ttu-id="afc65-193">Nella scheda **Impostazioni criteri,** in **Cosa si vuole fare se si rilevano informazioni riservate?**, esaminare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="afc65-193">On the **Policy settings** tab, under **What do you want to do if we detect sensitive info?**, review the settings.</span></span> <span data-ttu-id="afc65-194">È qui che è possibile scegliere di mantenere i suggerimenti per i [criteri predefiniti e le notifiche tramite posta](use-notifications-and-policy-tips.md)elettronica o personalizzarli.</span><span class="sxs-lookup"><span data-stu-id="afc65-194">(Here's where you can choose to keep default [policy tips and email notifications](use-notifications-and-policy-tips.md), or customize them.)</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="afc65-195">![Impostazioni dei criteri DLP con suggerimenti e notifiche](../media/dlp-teams-policysettings-tipsemails.png)</span><span class="sxs-lookup"><span data-stu-id="afc65-195">![DLP policy settings with tips and notifications](../media/dlp-teams-policysettings-tipsemails.png)</span></span>

    <span data-ttu-id="afc65-196">Al termine della revisione o della modifica delle impostazioni, scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="afc65-196">When you're finished reviewing or editing settings, choose **Next**.</span></span>

8. <span data-ttu-id="afc65-197">Nella **scheda Impostazioni criteri,** in Attivare o **testare prima i criteri?**, scegliere se attivare il criterio, [testarlo prima](dlp-overview-plan-for-dlp.md#policy-deployment)o tenerlo disattivato per il momento e quindi scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="afc65-197">On the **Policy settings** tab, under **Do you want to turn on the policy or test things out first?**, choose whether to turn the policy on, [test it first](dlp-overview-plan-for-dlp.md#policy-deployment), or keep it turned off for now, and then choose **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="afc65-198">![Specificare se attivare il criterio](../media/dlp-teams-policysettings-turnonnow.png)</span><span class="sxs-lookup"><span data-stu-id="afc65-198">![Specify whether to turn the policy on](../media/dlp-teams-policysettings-turnonnow.png)</span></span>

9. <span data-ttu-id="afc65-199">Nella scheda **Rivedi impostazioni** esaminare le impostazioni per il nuovo criterio.</span><span class="sxs-lookup"><span data-stu-id="afc65-199">On the **Review your settings** tab, review the settings for your new policy.</span></span> <span data-ttu-id="afc65-200">Scegliere **Modifica** per apportare modifiche.</span><span class="sxs-lookup"><span data-stu-id="afc65-200">Choose **Edit** to make changes.</span></span> <span data-ttu-id="afc65-201">Al termine, scegliere **Crea**.</span><span class="sxs-lookup"><span data-stu-id="afc65-201">When you're finished, choose **Create**.</span></span>

<span data-ttu-id="afc65-202">Consentire a circa un'ora che i nuovi criteri si disercino nel data center e si sincronizzino con gli account utente.</span><span class="sxs-lookup"><span data-stu-id="afc65-202">Allow approximately one hour for your new policy to work its way through your data center and sync to user accounts.</span></span>

## <a name="prevent-external-access-to-sensitive-documents"></a><span data-ttu-id="afc65-203">Prevenire l'accesso esterno ai documenti sensibili</span><span class="sxs-lookup"><span data-stu-id="afc65-203">Prevent external access to sensitive documents</span></span>

<span data-ttu-id="afc65-204">Per assicurarsi che SharePoint documenti contenenti informazioni riservate non possano essere accessibili da ospiti esterni da SharePoint o Teams per impostazione predefinita, selezionare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="afc65-204">To ensure that SharePoint documents that contain sensitive information cannot be accessed by external guests either from SharePoint or Teams by default, select the following:</span></span>

- <span data-ttu-id="afc65-205">È possibile assicurarsi che i documenti siano protetti fino a quando DLP non esegue l'analisi e li contrassegna come sicuri da condividere [contrassegnando i nuovi file come sensibili per impostazione predefinita](/sharepoint/sensitive-by-default).</span><span class="sxs-lookup"><span data-stu-id="afc65-205">You can ensure that documents are protected until DLP scans and marks them as safe to share by [marking new files as sensitive by default](/sharepoint/sensitive-by-default).</span></span>

- <span data-ttu-id="afc65-206">Struttura consigliata per il criterio DLP</span><span class="sxs-lookup"><span data-stu-id="afc65-206">Recommended DLP policy structure</span></span>

    - <span data-ttu-id="afc65-207">**Condizioni**</span><span class="sxs-lookup"><span data-stu-id="afc65-207">**Conditions**</span></span>
        - <span data-ttu-id="afc65-208">Il contenuto contiene uno di questi tipi di informazioni riservate: [Selezionare tutto ciò che si applica]</span><span class="sxs-lookup"><span data-stu-id="afc65-208">Content contains any of these sensitive information types: [Select all that applies]</span></span>
        
        - <span data-ttu-id="afc65-209">Il contenuto viene condiviso da Microsoft 365 persone esterne all'organizzazione</span><span class="sxs-lookup"><span data-stu-id="afc65-209">Content is shared from Microsoft 365 with people outside my organization</span></span>
        
          > [!div class="mx-imgBorder"]
          > <span data-ttu-id="afc65-210">![Condizioni DLP per rilevare la condivisione esterna di contenuto sensibile](../media/dlp-teams-external-sharing/external-condition.png)</span><span class="sxs-lookup"><span data-stu-id="afc65-210">![DLP conditions to detect external sharing of sensitive content](../media/dlp-teams-external-sharing/external-condition.png)</span></span>

    - <span data-ttu-id="afc65-211">**Azioni**</span><span class="sxs-lookup"><span data-stu-id="afc65-211">**Actions**</span></span>
        - <span data-ttu-id="afc65-212">Limitare l'accesso al contenuto per gli utenti esterni</span><span class="sxs-lookup"><span data-stu-id="afc65-212">Restrict access to the content for external users</span></span>
        
        - <span data-ttu-id="afc65-213">Inviare una notifica agli utenti tramite messaggio di posta elettronica e suggerimenti per i criteri</span><span class="sxs-lookup"><span data-stu-id="afc65-213">Notify users with email and policy tips</span></span>
        
        - <span data-ttu-id="afc65-214">Inviare i report degli incidenti all'amministratore</span><span class="sxs-lookup"><span data-stu-id="afc65-214">Send incident reports to the Administrator</span></span>
        
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="afc65-215">![Azione DLP per bloccare la condivisione esterna di contenuto sensibile](../media/dlp-teams-external-sharing/external-action.png)</span><span class="sxs-lookup"><span data-stu-id="afc65-215">![DLP action to block external sharing of sensitive content](../media/dlp-teams-external-sharing/external-action.png)</span></span>

<span data-ttu-id="afc65-216">Criteri DLP in azione quando si tenta di condividere un documento in SharePoint contenente informazioni riservate con un ospite esterno:</span><span class="sxs-lookup"><span data-stu-id="afc65-216">DLP policy in action when attempting to share a document in SharePoint that contains sensitive information with an external guest:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="afc65-217">![Condivisione esterna bloccata](../media/dlp-teams-external-sharing/external-sharing-blocked.png)</span><span class="sxs-lookup"><span data-stu-id="afc65-217">![External sharing blocked](../media/dlp-teams-external-sharing/external-sharing-blocked.png)</span></span>


<span data-ttu-id="afc65-218">Criteri DLP in azione quando l'ospite tenta di aprire un documento in Teams con blocco esterno:</span><span class="sxs-lookup"><span data-stu-id="afc65-218">DLP policy in action when guest attempts to open a document in Teams with block external:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="afc65-219">![Accesso esterno bloccato](../media/dlp-teams-external-sharing/external-access-blocked.png)</span><span class="sxs-lookup"><span data-stu-id="afc65-219">![External access blocked](../media/dlp-teams-external-sharing/external-access-blocked.png)</span></span>

## <a name="related-articles"></a><span data-ttu-id="afc65-220">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="afc65-220">Related articles</span></span>

[<span data-ttu-id="afc65-221">Creare, testare e ottimizzare un criterio di prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="afc65-221">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)

[<span data-ttu-id="afc65-222">Inviare notifiche di posta elettronica e visualizzare i suggerimenti per i criteri di prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="afc65-222">Send email notifications and show policy tips for DLP policies</span></span>](use-notifications-and-policy-tips.md)
