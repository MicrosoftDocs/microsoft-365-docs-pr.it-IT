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
description: È ora possibile applicare i criteri DLP alle chat e ai canali di Microsoft Teams. Leggi questo articolo per altre informazioni su come funziona.
ms.openlocfilehash: 40c55ed486efc75619b514a60b707ac75554953b
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445664"
---
# <a name="data-loss-prevention-and-microsoft-teams"></a><span data-ttu-id="f7867-104">Prevenzione della perdita dei dati e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f7867-104">Data loss prevention and Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="f7867-105">Le funzionalità di prevenzione della perdita dei dati sono state aggiunte di recente ai messaggi di chat e canali di Microsoft Teams per gli utenti con licenza per Office 365 E5/A5, Microsoft 365 E5/A5, Microsoft 365 Information Protection and Governance o Office 365 Advanced Compliance.</span><span class="sxs-lookup"><span data-stu-id="f7867-105">Data loss prevention capabilities were recently added to Microsoft Teams chat and channel messages for users licensed for Office 365 E5/A5, Microsoft 365 E5/A5, Microsoft 365 Information Protection and Governance or Office 365 Advanced Compliance.</span></span> <span data-ttu-id="f7867-106">Office 365 e Microsoft 365 E3 includono la protezione DLP per SharePoint Online, OneDrive ed Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="f7867-106">Office 365 and Microsoft 365 E3 include DLP protection for SharePoint Online, OneDrive, and Exchange Online.</span></span> <span data-ttu-id="f7867-107">Sono inclusi anche i file condivisi tramite Teams perché Teams usa SharePoint Online e OneDrive per condividere i file.</span><span class="sxs-lookup"><span data-stu-id="f7867-107">This also includes files that are shared through Teams because Teams uses SharePoint Online and OneDrive to share files.</span></span>
<span data-ttu-id="f7867-108">Il supporto per la protezione DLP in Teams Chat richiede E5.</span><span class="sxs-lookup"><span data-stu-id="f7867-108">Support for DLP protection in Teams Chat requires E5.</span></span>
<span data-ttu-id="f7867-109">Per altre informazioni sui requisiti di licenza, vedere [Linee guida per le licenze dei servizi a livello di tenant di Microsoft 365](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance).</span><span class="sxs-lookup"><span data-stu-id="f7867-109">To learn more about licensing requirements, see [Microsoft 365 Tenant-Level Services Licensing Guidance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance).</span></span>

## <a name="overview-of-dlp-for-microsoft-teams"></a><span data-ttu-id="f7867-110">Panoramica della prevenzione della perdita dei dati per Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f7867-110">Overview of DLP for Microsoft Teams</span></span>

<span data-ttu-id="f7867-111">Recentemente, [le funzionalità di prevenzione della](data-loss-prevention-policies.md) perdita dei dati (DLP) sono state estese per includere i messaggi di chat e canali di Microsoft Teams, inclusi i messaggi del canale **privato.**</span><span class="sxs-lookup"><span data-stu-id="f7867-111">Recently, [data loss prevention](data-loss-prevention-policies.md) (DLP) capabilities were extended to include Microsoft Teams chat and channel messages, **including private channel messages**.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="f7867-112">Dlp attualmente si applica solo ai messaggi effettivi nel thread di chat o canale.</span><span class="sxs-lookup"><span data-stu-id="f7867-112">DLP currently applies only to the actual messages in the chat or channel thread.</span></span> <span data-ttu-id="f7867-113">Le notifiche di attività, che includono un'anteprima breve dei  messaggi e vengono visualizzate in base alle impostazioni di notifica di un utente, non sono incluse in Dlp di Teams in questo momento.</span><span class="sxs-lookup"><span data-stu-id="f7867-113">Activity notifications -- which include a short message preview and appear based on a user's notification settings -- are **not** included in Teams DLP at this time.</span></span> <span data-ttu-id="f7867-114">Tutte le informazioni riservate presenti nella parte del messaggio visualizzata nell'anteprima rimarranno visibili nella notifica anche dopo l'applicazione del criterio DLP e la rimozione dell'inforamzione sensibile del messaggio stesso.</span><span class="sxs-lookup"><span data-stu-id="f7867-114">Any sensitive information present in the part of the message that appears in the preview will remain visible in the notification even after the DLP policy has been applied and removed sensitive inforamtion the message itself.</span></span>

<span data-ttu-id="f7867-115">Se l'organizzazione dispone di DLP, è ora possibile definire criteri che impediscono agli utenti di condividere informazioni riservate in un canale di Microsoft Teams o in una sessione di chat.</span><span class="sxs-lookup"><span data-stu-id="f7867-115">If your organization has DLP, you can now define policies that prevent people from sharing sensitive information in a Microsoft Teams channel or chat session.</span></span> <span data-ttu-id="f7867-116">Ecco alcuni esempi del funzionamento di questa protezione:</span><span class="sxs-lookup"><span data-stu-id="f7867-116">Here are some examples of how this protection works:</span></span>

- <span data-ttu-id="f7867-117">**Esempio 1: Protezione delle informazioni riservate nei messaggi**.</span><span class="sxs-lookup"><span data-stu-id="f7867-117">**Example 1: Protecting sensitive information in messages**.</span></span> <span data-ttu-id="f7867-118">Si supponga che qualcuno tenti di condividere informazioni riservate in una chat o in un canale di Teams con utenti guest (utenti esterni).</span><span class="sxs-lookup"><span data-stu-id="f7867-118">Suppose that someone attempts to share sensitive information in a Teams chat or channel with guests (external users).</span></span> <span data-ttu-id="f7867-119">Se si dispone di un criterio DLP definito per evitare questo problema, i messaggi con informazioni riservate inviate a utenti esterni vengono eliminati.</span><span class="sxs-lookup"><span data-stu-id="f7867-119">If you have a DLP policy defined to prevent this, messages with sensitive information that are sent to external users are deleted.</span></span> <span data-ttu-id="f7867-120">Ciò avviene automaticamente e in pochi secondi, in base alla configurazione del criterio DLP.</span><span class="sxs-lookup"><span data-stu-id="f7867-120">This happens automatically, and within seconds, according to how your DLP policy is configured.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f7867-121">DLP per Microsoft Teams blocca i contenuti sensibili quando vengono condivisi con utenti di Microsoft Teams che hanno:</span><span class="sxs-lookup"><span data-stu-id="f7867-121">DLP for Microsoft Teams blocks sensitive content when shared with Microsoft Teams users who have:</span></span><br/><span data-ttu-id="f7867-122">- [accesso guest](/MicrosoftTeams/guest-access) in team e canali; o</span><span class="sxs-lookup"><span data-stu-id="f7867-122">- [guest access](/MicrosoftTeams/guest-access) in teams and channels; or</span></span><br/><span data-ttu-id="f7867-123">- [accesso esterno](/MicrosoftTeams/manage-external-access) nelle riunioni e nelle sessioni di chat.</span><span class="sxs-lookup"><span data-stu-id="f7867-123">- [external access](/MicrosoftTeams/manage-external-access) in meetings and chat sessions.</span></span> <p><span data-ttu-id="f7867-124">DLP per le sessioni di chat esterne funzionerà solo se il mittente e il destinatario sono in modalità Solo Teams e utilizzano [la federazione nativa di Microsoft Teams.](/microsoftteams/manage-external-access)</span><span class="sxs-lookup"><span data-stu-id="f7867-124">DLP for external chat sessions will only work if both the sender and the receiver are in Teams Only mode and using [Microsoft Teams native federation](/microsoftteams/manage-external-access).</span></span> <span data-ttu-id="f7867-125">DLP per Teams non blocca i messaggi in [interoperabilità](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business) con Skype for Business o le sessioni di chat federate non native.</span><span class="sxs-lookup"><span data-stu-id="f7867-125">DLP for Teams does not block messages in [interop](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business) with Skype for Business or non-native federated chat sessions.</span></span>

- <span data-ttu-id="f7867-126">**Esempio 2: protezione delle informazioni riservate nei documenti**.</span><span class="sxs-lookup"><span data-stu-id="f7867-126">**Example 2: Protecting sensitive information in documents**.</span></span> <span data-ttu-id="f7867-127">Si supponga che un utente tenti di condividere un documento con utenti guest in un canale o in una chat di Microsoft Teams e che il documento contenga informazioni riservate.</span><span class="sxs-lookup"><span data-stu-id="f7867-127">Suppose that someone attempts to share a document with guests in a Microsoft Teams channel or chat, and the document contains sensitive information.</span></span> <span data-ttu-id="f7867-128">Se si dispone di un criterio DLP definito per evitare questo problema, il documento non verrà aperto per tali utenti.</span><span class="sxs-lookup"><span data-stu-id="f7867-128">If you have a DLP policy defined to prevent this, the document won't open for those users.</span></span> <span data-ttu-id="f7867-129">Tenere presente che, in questo caso, i criteri DLP devono includere SharePoint e OneDrive per garantire la protezione.</span><span class="sxs-lookup"><span data-stu-id="f7867-129">Note that in this case, your DLP policy must include SharePoint and OneDrive in order for protection to be in place.</span></span> <span data-ttu-id="f7867-130">Si tratta di un esempio di DLP per SharePoint che viene visualizzato in Microsoft Teams e pertanto richiede che gli utenti siano concessi in licenza per Office 365 DLP (incluso in Office 365 E3), ma non richiede che gli utenti siano concessi in licenza per La conformità avanzata di Office 365.</span><span class="sxs-lookup"><span data-stu-id="f7867-130">(This is an example of DLP for SharePoint that shows up in Microsoft Teams, and therefore requires that users are licensed for Office 365 DLP (included in Office 365 E3), but does not require users to be licensed for Office 365 Advanced Compliance.)</span></span>

## <a name="policy-tips-help-educate-users"></a><span data-ttu-id="f7867-131">I suggerimenti per i criteri aiutano a formare gli utenti</span><span class="sxs-lookup"><span data-stu-id="f7867-131">Policy tips help educate users</span></span>

<span data-ttu-id="f7867-132">Analogamente al funzionamento della prevenzione della perdita dei dati in [Exchange, Outlook, Outlook sul Web,](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web) [SharePoint Online,](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites)siti di OneDrive for Business e client desktop di [Office,](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs)i suggerimenti per i criteri vengono visualizzati quando un'azione è in conflitto con un criterio DLP.</span><span class="sxs-lookup"><span data-stu-id="f7867-132">Similar to how DLP works in [Exchange, Outlook, Outlook on the web](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web), [SharePoint Online, OneDrive for Business sites](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites), and [Office desktop clients](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs), policy tips appear when an action conflicts with a DLP policy.</span></span> <span data-ttu-id="f7867-133">Ecco un esempio di suggerimento per i criteri:</span><span class="sxs-lookup"><span data-stu-id="f7867-133">Here's an example of a policy tip:</span></span>

![Notifica dei messaggi bloccati in Teams](../media/dlp-teams-blockedmessage-notification.png)

<span data-ttu-id="f7867-135">In questo caso, il mittente ha tentato di condividere un numero di previdenza sociale in un canale di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f7867-135">In this case, the sender attempted to share a social security number in a Microsoft Teams channel.</span></span> <span data-ttu-id="f7867-136">Il **collegamento What can I do?** apre una finestra di dialogo che consente al mittente di risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="f7867-136">The **What can I do?** link opens a dialog box that provides options for the sender to resolve the issue.</span></span> <span data-ttu-id="f7867-137">Si noti che in questo caso, il mittente può scegliere di ignorare il criterio o informare un amministratore di esaminarlo e risolverlo.</span><span class="sxs-lookup"><span data-stu-id="f7867-137">Notice that in this case, the sender can opt to override the policy, or notify an admin to review and resolve it.</span></span>

![Opzioni per risolvere i messaggi bloccati](../media/dlp-teams-blockedmessage-possibleactions.png)

<span data-ttu-id="f7867-139">Nell'organizzazione, è possibile scegliere di consentire agli utenti di ignorare un criterio DLP.</span><span class="sxs-lookup"><span data-stu-id="f7867-139">In your organization, you can choose to allow users to override a DLP policy.</span></span> <span data-ttu-id="f7867-140">Inoltre, quando si configurano i criteri DLP, è possibile utilizzare i suggerimenti per i criteri predefiniti o [personalizzare i suggerimenti per](#to-customize-policy-tips) i criteri per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f7867-140">And, when you configure your DLP policies, you can use the default policy tips, or [customize policy tips](#to-customize-policy-tips) for your organization.</span></span>

<span data-ttu-id="f7867-141">Tornando all'esempio, in cui un mittente ha condiviso un numero di previdenza sociale in un canale di Teams, ecco cosa ha visto il destinatario:</span><span class="sxs-lookup"><span data-stu-id="f7867-141">Returning to our example, where a sender shared a social security number in a Teams channel, here's what the recipient saw:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f7867-142">![Messaggio bloccato](../media/dlp-teams-blockedmessage-notification-to-user.png)</span><span class="sxs-lookup"><span data-stu-id="f7867-142">![Message blocked](../media/dlp-teams-blockedmessage-notification-to-user.png)</span></span>

<span data-ttu-id="f7867-143">Il **collegamento What's this?** apre [un](data-loss-prevention-policies.md) articolo sui criteri DLP, che spiega perché il messaggio è stato bloccato.</span><span class="sxs-lookup"><span data-stu-id="f7867-143">The **What's this?** link opens an [article](data-loss-prevention-policies.md) about DLP policies, which helps explain why the message was blocked.</span></span>

### <a name="to-customize-policy-tips"></a><span data-ttu-id="f7867-144">Per personalizzare i suggerimenti per i criteri</span><span class="sxs-lookup"><span data-stu-id="f7867-144">To customize policy tips</span></span>

<span data-ttu-id="f7867-145">Per eseguire questa attività, è necessario disporre di un ruolo che dispone delle autorizzazioni per modificare i criteri DLP.</span><span class="sxs-lookup"><span data-stu-id="f7867-145">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="f7867-146">Per ulteriori informazioni, vedere [Autorizzazioni](data-loss-prevention-policies.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="f7867-146">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="f7867-147">Passare al Centro sicurezza & conformità ( [https://protection.office.com](https://protection.office.com) ) ed eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="f7867-147">Go to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="f7867-148">Scegliere **Criteri di prevenzione della perdita di**  >  **dati**.</span><span class="sxs-lookup"><span data-stu-id="f7867-148">Choose **Data loss prevention** > **Policy**.</span></span>

3. <span data-ttu-id="f7867-149">Selezionare un criterio e accanto a **Impostazioni criteri** scegliere **Modifica.**</span><span class="sxs-lookup"><span data-stu-id="f7867-149">Select a policy, and next to **Policy settings**, choose **Edit**.</span></span>

4. <span data-ttu-id="f7867-150">Creare una nuova regola o modificare una regola esistente per il criterio.</span><span class="sxs-lookup"><span data-stu-id="f7867-150">Either create a new rule, or edit an existing rule for the policy.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f7867-151">![Modifica di una regola per un criterio](../media/dlp-teams-editrule.png)</span><span class="sxs-lookup"><span data-stu-id="f7867-151">![Editing a rule for a policy](../media/dlp-teams-editrule.png)</span></span>

5. <span data-ttu-id="f7867-152">Nella scheda **Notifiche utente** seleziona Personalizza il testo del messaggio **di posta** elettronica e/o Personalizza le opzioni del testo del **suggerimento per i** criteri.</span><span class="sxs-lookup"><span data-stu-id="f7867-152">On the **User notifications** tab, select **Customize the email text** and/or **Customize the policy tip text** options.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f7867-153">![Personalizzare le notifiche utente e i suggerimenti per i criteri](../media/dlp-teams-editrule-usernotifications.png)</span><span class="sxs-lookup"><span data-stu-id="f7867-153">![Customize user notifications and policy tips](../media/dlp-teams-editrule-usernotifications.png)</span></span><br/>  

6. <span data-ttu-id="f7867-154">Specificare il testo che si desidera utilizzare per le notifiche di posta elettronica e/o i suggerimenti per i criteri, quindi scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f7867-154">Specify the text you want to use for email notifications and/or policy tips, and then choose **Save**.</span></span>

7. <span data-ttu-id="f7867-155">Nella scheda **Impostazioni criteri** scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f7867-155">On the **Policy settings** tab, choose **Save**.</span></span>

<span data-ttu-id="f7867-156">Consentire circa un'ora che le modifiche funzionino nel data center e si sincronizzano con gli account utente.</span><span class="sxs-lookup"><span data-stu-id="f7867-156">Allow approximately one hour for your changes to work their way through your data center and sync to user accounts.</span></span>
 <!-- why are these syncing to user accounts? -->

## <a name="add-microsoft-teams-as-a-location-to-existing-dlp-policies"></a><span data-ttu-id="f7867-157">Aggiungere Microsoft Teams come percorso ai criteri DLP esistenti</span><span class="sxs-lookup"><span data-stu-id="f7867-157">Add Microsoft Teams as a location to existing DLP policies</span></span>

<span data-ttu-id="f7867-158">Per eseguire questa attività, è necessario disporre di un ruolo che dispone delle autorizzazioni per modificare i criteri DLP.</span><span class="sxs-lookup"><span data-stu-id="f7867-158">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="f7867-159">Per ulteriori informazioni, vedere [Autorizzazioni](data-loss-prevention-policies.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="f7867-159">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="f7867-160">Passare al Centro sicurezza & conformità ( [https://protection.office.com](https://protection.office.com) ) ed eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="f7867-160">Go to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="f7867-161">Scegliere **Criteri di prevenzione della perdita di**  >  **dati**.</span><span class="sxs-lookup"><span data-stu-id="f7867-161">Choose **Data loss prevention** > **Policy**.</span></span>

3. <span data-ttu-id="f7867-162">Selezionare un criterio e osservare i valori in **Posizioni**.</span><span class="sxs-lookup"><span data-stu-id="f7867-162">Select a policy, and look at the values under **Locations**.</span></span> <span data-ttu-id="f7867-163">Se vengono visualizzati **messaggi di chat e canali di Teams,** è tutto impostato.</span><span class="sxs-lookup"><span data-stu-id="f7867-163">If you see **Teams chat and channel messages**, you're all set.</span></span> <span data-ttu-id="f7867-164">In caso contrario, fare clic su **Modifica.**</span><span class="sxs-lookup"><span data-stu-id="f7867-164">If you don't, click **Edit**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f7867-165">![Percorsi per i criteri esistenti](../media/dlp-teams-editexistingpolicy.png)</span><span class="sxs-lookup"><span data-stu-id="f7867-165">![Locations for existing policy](../media/dlp-teams-editexistingpolicy.png)</span></span>

4. <span data-ttu-id="f7867-166">Nella colonna **Stato** attivare il criterio per i messaggi di chat e **canali di Teams.**</span><span class="sxs-lookup"><span data-stu-id="f7867-166">In the **Status** column, turn the policy on for **Teams chat and channel messages**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f7867-167">![DLP per chat e canali di Teams](../media/dlp-teams-addteamschatschannels.png)</span><span class="sxs-lookup"><span data-stu-id="f7867-167">![DLP for Teams chats and channels](../media/dlp-teams-addteamschatschannels.png)</span></span>

5. <span data-ttu-id="f7867-168">Nella scheda **Scegli posizioni** mantenere l'impostazione predefinita di tutti gli account oppure selezionare Consenti di scegliere **posizioni specifiche.**</span><span class="sxs-lookup"><span data-stu-id="f7867-168">On the **Choose locations** tab, keep the default setting of all accounts, or select **Let me choose specific locations**.</span></span> <span data-ttu-id="f7867-169">È possibile specificare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="f7867-169">You can specify:</span></span>

    1. <span data-ttu-id="f7867-170">fino a 1000 singoli account da includere o escludere</span><span class="sxs-lookup"><span data-stu-id="f7867-170">up to 1000 individual accounts to include or exclude</span></span>
    1. <span data-ttu-id="f7867-171">liste di distribuzione e gruppi di sicurezza da includere o escludere.</span><span class="sxs-lookup"><span data-stu-id="f7867-171">distribution lists and security groups to include or exclude.</span></span> <span data-ttu-id="f7867-172">**Si tratta di una funzionalità di anteprima pubblica.**</span><span class="sxs-lookup"><span data-stu-id="f7867-172">**This is a public preview feature.**</span></span>
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**--> 
    
6. <span data-ttu-id="f7867-173">Quindi scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f7867-173">Then choose **Next**.</span></span>

7. <span data-ttu-id="f7867-174">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f7867-174">Click **Save**.</span></span>

<span data-ttu-id="f7867-175">Consentire circa un'ora che le modifiche funzionino nel data center e si sincronizzano con gli account utente.</span><span class="sxs-lookup"><span data-stu-id="f7867-175">Allow approximately one hour for your changes to work their way through your data center and sync to user accounts.</span></span>
<!-- again, why user accounts? -->

## <a name="define-a-new-dlp-policy-for-microsoft-teams"></a><span data-ttu-id="f7867-176">Definire un nuovo criterio DLP per Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f7867-176">Define a new DLP policy for Microsoft Teams</span></span>

<span data-ttu-id="f7867-177">Per eseguire questa attività, è necessario disporre di un ruolo che dispone delle autorizzazioni per modificare i criteri DLP.</span><span class="sxs-lookup"><span data-stu-id="f7867-177">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="f7867-178">Per ulteriori informazioni, vedere [Autorizzazioni](data-loss-prevention-policies.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="f7867-178">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="f7867-179">Passare al Centro sicurezza & conformità ( [https://protection.office.com](https://protection.office.com) ) ed eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="f7867-179">Go to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="f7867-180">Scegliere **Criteri di prevenzione della perdita** dei  >  **dati**+ Crea un  >  **criterio.**</span><span class="sxs-lookup"><span data-stu-id="f7867-180">Choose **Data loss prevention** > **Policy** > **+ Create a policy**.</span></span>

3. <span data-ttu-id="f7867-181">Scegliere un [modello](data-loss-prevention-policies.md#dlp-policy-templates)e quindi scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f7867-181">Choose a [template](data-loss-prevention-policies.md#dlp-policy-templates), and then choose **Next**.</span></span>

    <span data-ttu-id="f7867-182">In questo esempio è stato scelto il modello Dati personali degli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="f7867-182">In our example, we chose the U.S. Personally Identifiable Information Data template.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f7867-183">![Modello di privacy per i criteri DLP](../media/dlp-teams-createnewpolicy-template.png)</span><span class="sxs-lookup"><span data-stu-id="f7867-183">![Privacy template for DLP policy](../media/dlp-teams-createnewpolicy-template.png)</span></span><br/>

4. <span data-ttu-id="f7867-184">Nella scheda **Assegnare un nome al** criterio specificare un nome e una descrizione per il criterio e quindi scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f7867-184">On the **Name your policy** tab, specify a name and description for the policy, and then choose **Next**.</span></span>

5. <span data-ttu-id="f7867-185">Nella scheda **Scegli posizioni** mantenere l'impostazione predefinita di tutti gli account oppure selezionare Consenti di scegliere **posizioni specifiche.**</span><span class="sxs-lookup"><span data-stu-id="f7867-185">On the **Choose locations** tab, keep the default setting of all accounts, or select **Let me choose specific locations**.</span></span> <span data-ttu-id="f7867-186">È possibile specificare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="f7867-186">You can specify:</span></span>

    1. <span data-ttu-id="f7867-187">fino a 1000 singoli account da includere o escludere</span><span class="sxs-lookup"><span data-stu-id="f7867-187">up to 1000 individual accounts to include or exclude</span></span>
    1. <span data-ttu-id="f7867-188">liste di distribuzione e gruppi di sicurezza da includere o escludere.</span><span class="sxs-lookup"><span data-stu-id="f7867-188">distribution lists and security groups to include or exclude.</span></span> <span data-ttu-id="f7867-189">**Si tratta di una funzionalità di anteprima pubblica.**</span><span class="sxs-lookup"><span data-stu-id="f7867-189">**This is a public preview feature.**</span></span>
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**-->  

    ![Percorsi dei criteri DLP](../media/dlp-teams-selectlocationsnewpolicy.png)

    > [!NOTE]
    > <span data-ttu-id="f7867-191">Se si desidera verificare che i documenti contenenti informazioni riservate non siano condivisi in modo inappropriato in Teams, verificare che i siti di **SharePoint** e gli account **di OneDrive** siano attivati, insieme ai messaggi di chat e canali di **Teams.**</span><span class="sxs-lookup"><span data-stu-id="f7867-191">If you want to make sure documents that contain sensitive information are not shared inappropriately in Teams, make sure **SharePoint sites** and **OneDrive accounts** are turned on, along with **Teams chat and channel messages**.</span></span>

6. <span data-ttu-id="f7867-192">Nella scheda **Impostazioni criteri,** in **Personalizza** il tipo di contenuto che si desidera proteggere, mantenere le impostazioni semplici predefinite oppure scegliere **Usa impostazioni avanzate** e quindi **avanti.**</span><span class="sxs-lookup"><span data-stu-id="f7867-192">On the **Policy settings** tab, under **Customize the type of content you want to protect**, keep the default simple settings, or choose **Use advanced settings**, and then choose **Next**.</span></span> <span data-ttu-id="f7867-193">Se si scelgono impostazioni avanzate, è possibile creare o modificare le regole per i criteri.</span><span class="sxs-lookup"><span data-stu-id="f7867-193">If you choose advanced settings, you can create or edit rules for your policy.</span></span> <span data-ttu-id="f7867-194">Per informazioni su questo argomento, vedere [Impostazioni semplici e impostazioni avanzate.](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings)</span><span class="sxs-lookup"><span data-stu-id="f7867-194">(To get help with this, see [Simple settings vs. advanced settings](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings).)</span></span>

7.  <span data-ttu-id="f7867-195">Nella scheda **Impostazioni dei criteri,** in Cosa vuoi fare se rileviamo **informazioni riservate?** esamina le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="f7867-195">On the **Policy settings** tab, under **What do you want to do if we detect sensitive info?**, review the settings.</span></span> <span data-ttu-id="f7867-196">Ecco dove puoi scegliere se mantenere i suggerimenti per i criteri predefiniti e le [notifiche tramite posta elettronica](use-notifications-and-policy-tips.md)o personalizzarli.</span><span class="sxs-lookup"><span data-stu-id="f7867-196">(Here's where you can choose to keep default [policy tips and email notifications](use-notifications-and-policy-tips.md), or customize them.)</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f7867-197">![Impostazioni dei criteri DLP con suggerimenti e notifiche](../media/dlp-teams-policysettings-tipsemails.png)</span><span class="sxs-lookup"><span data-stu-id="f7867-197">![DLP policy settings with tips and notifications](../media/dlp-teams-policysettings-tipsemails.png)</span></span>

    <span data-ttu-id="f7867-198">Al termine della revisione o della modifica delle impostazioni, scegliere **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="f7867-198">When you're finished reviewing or editing settings, choose **Next**.</span></span>

8. <span data-ttu-id="f7867-199">Nella  scheda Impostazioni criteri, in Si desidera attivare il criterio o testare prima gli **elementi?**, scegliere se attivare il [criterio,](data-loss-prevention-policies.md#roll-out-dlp-policies-gradually-with-test-mode)testarlo per primo o mantenerlo disattivato per il momento e quindi scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f7867-199">On the **Policy settings** tab, under **Do you want to turn on the policy or test things out first?**, choose whether to turn the policy on, [test it first](data-loss-prevention-policies.md#roll-out-dlp-policies-gradually-with-test-mode), or keep it turned off for now, and then choose **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f7867-200">![Specificare se attivare il criterio](../media/dlp-teams-policysettings-turnonnow.png)</span><span class="sxs-lookup"><span data-stu-id="f7867-200">![Specify whether to turn the policy on](../media/dlp-teams-policysettings-turnonnow.png)</span></span>

9. <span data-ttu-id="f7867-201">Nella scheda **Rivedere le impostazioni** esaminare le impostazioni per il nuovo criterio.</span><span class="sxs-lookup"><span data-stu-id="f7867-201">On the **Review your settings** tab, review the settings for your new policy.</span></span> <span data-ttu-id="f7867-202">Scegliere **Modifica** per apportare modifiche.</span><span class="sxs-lookup"><span data-stu-id="f7867-202">Choose **Edit** to make changes.</span></span> <span data-ttu-id="f7867-203">Al termine, scegliere **Crea**.</span><span class="sxs-lookup"><span data-stu-id="f7867-203">When you're finished, choose **Create**.</span></span>

<span data-ttu-id="f7867-204">Consentire circa un'ora per il funzionamento del nuovo criterio nel data center e la sincronizzazione con gli account utente.</span><span class="sxs-lookup"><span data-stu-id="f7867-204">Allow approximately one hour for your new policy to work its way through your data center and sync to user accounts.</span></span>

## <a name="prevent-external-access-to-sensitive-documents"></a><span data-ttu-id="f7867-205">Impedire l'accesso esterno ai documenti riservati</span><span class="sxs-lookup"><span data-stu-id="f7867-205">Prevent external access to sensitive documents</span></span>

<span data-ttu-id="f7867-206">Per assicurarsi che i documenti di SharePoint contenenti informazioni riservate non siano accessibili da utenti guest esterni da SharePoint o Teams per impostazione predefinita, selezionare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="f7867-206">To ensure that SharePoint documents that contain sensitive information cannot be accessed by external guests either from SharePoint or Teams by default, select the following:</span></span>

- <span data-ttu-id="f7867-207">È possibile assicurarsi che i documenti siano protetti fino all'analisi DLP e li contrassegni come sicuri da condividere contrassegnando i nuovi [file come sensibili per impostazione predefinita.](/sharepoint/sensitive-by-default)</span><span class="sxs-lookup"><span data-stu-id="f7867-207">You can ensure that documents are protected until DLP scans and marks them as safe to share by [marking new files as sensitive by default](/sharepoint/sensitive-by-default).</span></span>

- <span data-ttu-id="f7867-208">Struttura consigliata dei criteri DLP</span><span class="sxs-lookup"><span data-stu-id="f7867-208">Recommended DLP policy structure</span></span>

    - <span data-ttu-id="f7867-209">**Condizioni**</span><span class="sxs-lookup"><span data-stu-id="f7867-209">**Conditions**</span></span>
        - <span data-ttu-id="f7867-210">Il contenuto contiene uno di questi tipi di informazioni riservate: [Selezionare tutto ciò che si applica]</span><span class="sxs-lookup"><span data-stu-id="f7867-210">Content contains any of these sensitive information types: [Select all that applies]</span></span>
        
        - <span data-ttu-id="f7867-211">Il contenuto viene condiviso da Microsoft 365 con persone esterne all'organizzazione</span><span class="sxs-lookup"><span data-stu-id="f7867-211">Content is shared from Microsoft 365 with people outside my organization</span></span>
        
          > [!div class="mx-imgBorder"]
          > <span data-ttu-id="f7867-212">![Condizioni DLP per rilevare la condivisione esterna di contenuto sensibile](../media/dlp-teams-external-sharing/external-condition.png)</span><span class="sxs-lookup"><span data-stu-id="f7867-212">![DLP conditions to detect external sharing of sensitive content](../media/dlp-teams-external-sharing/external-condition.png)</span></span>

    - <span data-ttu-id="f7867-213">**Azioni**</span><span class="sxs-lookup"><span data-stu-id="f7867-213">**Actions**</span></span>
        - <span data-ttu-id="f7867-214">Limitare l'accesso al contenuto per gli utenti esterni</span><span class="sxs-lookup"><span data-stu-id="f7867-214">Restrict access to the content for external users</span></span>
        
        - <span data-ttu-id="f7867-215">Inviare notifiche agli utenti tramite posta elettronica e suggerimenti per i criteri</span><span class="sxs-lookup"><span data-stu-id="f7867-215">Notify users with email and policy tips</span></span>
        
        - <span data-ttu-id="f7867-216">Inviare rapporti operazioni non consentite all'amministratore</span><span class="sxs-lookup"><span data-stu-id="f7867-216">Send incident reports to the Administrator</span></span>
        
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="f7867-217">![Azione DLP per bloccare la condivisione esterna di contenuto sensibile](../media/dlp-teams-external-sharing/external-action.png)</span><span class="sxs-lookup"><span data-stu-id="f7867-217">![DLP action to block external sharing of sensitive content](../media/dlp-teams-external-sharing/external-action.png)</span></span>

<span data-ttu-id="f7867-218">Criteri DLP in azione quando si tenta di condividere un documento in SharePoint contenente informazioni riservate con un guest esterno:</span><span class="sxs-lookup"><span data-stu-id="f7867-218">DLP policy in action when attempting to share a document in SharePoint that contains sensitive information with an external guest:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f7867-219">![Condivisione esterna bloccata](../media/dlp-teams-external-sharing/external-sharing-blocked.png)</span><span class="sxs-lookup"><span data-stu-id="f7867-219">![External sharing blocked](../media/dlp-teams-external-sharing/external-sharing-blocked.png)</span></span>


<span data-ttu-id="f7867-220">Criteri DLP in azione quando guest tenta di aprire un documento in Teams con blocco esterno:</span><span class="sxs-lookup"><span data-stu-id="f7867-220">DLP policy in action when guest attempts to open a document in Teams with block external:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f7867-221">![Accesso esterno bloccato](../media/dlp-teams-external-sharing/external-access-blocked.png)</span><span class="sxs-lookup"><span data-stu-id="f7867-221">![External access blocked](../media/dlp-teams-external-sharing/external-access-blocked.png)</span></span>

## <a name="related-articles"></a><span data-ttu-id="f7867-222">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="f7867-222">Related articles</span></span>

[<span data-ttu-id="f7867-223">Creare, testare e ottimizzare un criterio di prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="f7867-223">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)

[<span data-ttu-id="f7867-224">Inviare notifiche di posta elettronica e visualizzare i suggerimenti per i criteri di prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="f7867-224">Send email notifications and show policy tips for DLP policies</span></span>](use-notifications-and-policy-tips.md)
