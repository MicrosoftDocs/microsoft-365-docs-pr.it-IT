---
title: Tag di quarantena
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
ROBOTS: NOINDEX
description: Gli amministratori possono imparare a usare i tag di quarantena per controllare le attività che gli utenti possono eseguire sui messaggi in quarantena.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8024894cdb4a4718422c250eff87fa6da5443a84
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922413"
---
# <a name="quarantine-tags"></a><span data-ttu-id="ddb53-103">Tag di quarantena</span><span class="sxs-lookup"><span data-stu-id="ddb53-103">Quarantine tags</span></span>

> [!NOTE]
> <span data-ttu-id="ddb53-104">Le funzionalità descritte in questo articolo sono attualmente disponibili in Anteprima, non sono disponibili per tutti e sono soggette a modifiche.</span><span class="sxs-lookup"><span data-stu-id="ddb53-104">The features that are described in this article are currently in Preview, aren't available to everyone, and are subject to change.</span></span>

<span data-ttu-id="ddb53-105">I tag di quarantena in Exchange Online Protection (EOP) consentono agli amministratori di controllare le attività che gli utenti possono eseguire sui messaggi in quarantena in base al modo in cui il messaggio è arrivato in quarantena.</span><span class="sxs-lookup"><span data-stu-id="ddb53-105">Quarantine tags in Exchange Online Protection (EOP) allow admins to control what users are able to do to their quarantined messages based on how the message arrived in quarantine.</span></span>

<span data-ttu-id="ddb53-106">EOP ha tradizionalmente consentito o impedito determinati livelli di interattività per i messaggi in [quarantena](find-and-release-quarantined-messages-as-a-user.md) e nelle [notifiche di posta indesiderata dell'utente finale.](use-spam-notifications-to-release-and-report-quarantined-messages.md)</span><span class="sxs-lookup"><span data-stu-id="ddb53-106">EOP has traditionally allowed or prevented certain levels of interactivity for messages in [quarantine](find-and-release-quarantined-messages-as-a-user.md) and in [end-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span> <span data-ttu-id="ddb53-107">Ad esempio, gli utenti finali possono visualizzare e rilasciare i messaggi messi in quarantena dal filtro di protezione da posta indesiderata come posta indesiderata o in blocco, ma non possono visualizzare o rilasciare i messaggi messi in quarantena come phishing ad alta probabilità.</span><span class="sxs-lookup"><span data-stu-id="ddb53-107">For example, end-users can view and release messages that were quarantined by anti-spam filtering as spam or bulk, but they can't view or release messages that were quarantined as high confidence phishing.</span></span>

<span data-ttu-id="ddb53-108">Per [le funzionalità](#step-2-assign-a-quarantine-tag-to-supported-features)di protezione supportate, i tag di quarantena specificano le attività consentite agli utenti nei messaggi di notifica di posta indesiderata dell'utente finale e nei messaggi in quarantena (messaggi in cui l'utente è un destinatario).</span><span class="sxs-lookup"><span data-stu-id="ddb53-108">For [supported protection features](#step-2-assign-a-quarantine-tag-to-supported-features), quarantine tags specify what users are allowed to do in end-user spam notification messages and in their quarantined messages in quarantine (messages where the user is a recipient).</span></span> <span data-ttu-id="ddb53-109">I tag di quarantena predefiniti vengono assegnati automaticamente per applicare le funzionalità cronologiche per gli utenti finali ai messaggi in quarantena.</span><span class="sxs-lookup"><span data-stu-id="ddb53-109">Default quarantine tags are automatically assigned to enforce the historical capabilities for end-users on quarantined messages.</span></span> <span data-ttu-id="ddb53-110">In caso contrario, è possibile creare e assegnare tag di quarantena personalizzati per consentire o impedire agli utenti finali di eseguire azioni specifiche sui messaggi in quarantena.</span><span class="sxs-lookup"><span data-stu-id="ddb53-110">Or, you can create and assign custom quarantine tags to allow or prevent end-users from performing specific actions on quarantined messages.</span></span>

<span data-ttu-id="ddb53-111">Le singole autorizzazioni vengono combinate nei gruppi di autorizzazioni preimpostati seguenti:</span><span class="sxs-lookup"><span data-stu-id="ddb53-111">The individual permissions are combined into the following preset permission groups:</span></span>

- <span data-ttu-id="ddb53-112">Nessun diritto di accesso</span><span class="sxs-lookup"><span data-stu-id="ddb53-112">No access</span></span>
- <span data-ttu-id="ddb53-113">Accesso limitato</span><span class="sxs-lookup"><span data-stu-id="ddb53-113">Limited access</span></span>
- <span data-ttu-id="ddb53-114">Accesso completo</span><span class="sxs-lookup"><span data-stu-id="ddb53-114">Full access</span></span>

<span data-ttu-id="ddb53-115">Le singole autorizzazioni disponibili e ciò che è incluso o non incluso nei gruppi di autorizzazioni preimpostati sono descritti nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="ddb53-115">The available individual permissions and what's included or not included in the preset permission groups are described in the following table:</span></span>

|<span data-ttu-id="ddb53-116">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="ddb53-116">Permission</span></span>|<span data-ttu-id="ddb53-117">Nessun diritto di accesso</span><span class="sxs-lookup"><span data-stu-id="ddb53-117">No access</span></span>|<span data-ttu-id="ddb53-118">Accesso limitato</span><span class="sxs-lookup"><span data-stu-id="ddb53-118">Limited access</span></span>|<span data-ttu-id="ddb53-119">Accesso completo</span><span class="sxs-lookup"><span data-stu-id="ddb53-119">Full access</span></span>|
|---|:---:|:---:|:---:|
|<span data-ttu-id="ddb53-120">**Consenti mittente** (_PermissionToAllowSender_)</span><span class="sxs-lookup"><span data-stu-id="ddb53-120">**Allow sender** (_PermissionToAllowSender_)</span></span>|||![Segno di spunta](../../media/checkmark.png)|
|<span data-ttu-id="ddb53-122">**Blocca mittente** (_PermissionToBlockSender_)</span><span class="sxs-lookup"><span data-stu-id="ddb53-122">**Block sender** (_PermissionToBlockSender_)</span></span>||![Segno di spunta](../../media/checkmark.png)|![Segno di spunta](../../media/checkmark.png)|
|<span data-ttu-id="ddb53-125">**Delete** (_PermissionToDelete_)</span><span class="sxs-lookup"><span data-stu-id="ddb53-125">**Delete** (_PermissionToDelete_)</span></span>||![Segno di spunta](../../media/checkmark.png)|![Segno di spunta](../../media/checkmark.png)|
|<span data-ttu-id="ddb53-128">**Anteprima** (_PermissionToPreview_)</span><span class="sxs-lookup"><span data-stu-id="ddb53-128">**Preview** (_PermissionToPreview_)</span></span>||![Segno di spunta](../../media/checkmark.png)|![Segno di spunta](../../media/checkmark.png)|
|<span data-ttu-id="ddb53-131">**Consentire ai destinatari di rilasciare un messaggio dalla quarantena** (_PermissionToRelease_)</span><span class="sxs-lookup"><span data-stu-id="ddb53-131">**Allow recipients to release a message from quarantine** (_PermissionToRelease_)</span></span>|||![Segno di spunta](../../media/checkmark.png)|
|<span data-ttu-id="ddb53-133">**Consentire ai destinatari di richiedere il rilascio di un messaggio dalla quarantena** (_PermissionToRequestRelease_)</span><span class="sxs-lookup"><span data-stu-id="ddb53-133">**Allow recipients to request a message to be released from quarantine** (_PermissionToRequestRelease_)</span></span>||![Segno di spunta](../../media/checkmark.png)||
|

<span data-ttu-id="ddb53-135">Se non ti piace le autorizzazioni predefinite nei gruppi di autorizzazioni preimpostati, puoi usare autorizzazioni personalizzate quando crei o modifica tag di quarantena personalizzati.</span><span class="sxs-lookup"><span data-stu-id="ddb53-135">If you don't like the default permissions in the preset permission groups, you can use custom permissions when you create or modify custom quarantine tags.</span></span> <span data-ttu-id="ddb53-136">Per ulteriori informazioni sulle attività di ogni autorizzazione, vedere la sezione Dettagli sulle autorizzazioni [per i tag](#quarantine-tag-permission-details) di quarantena più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="ddb53-136">For more information about what each permission does, see the [Quarantine tag permission details](#quarantine-tag-permission-details) section later in this article.</span></span>

<span data-ttu-id="ddb53-137">È possibile creare e assegnare tag di quarantena nel Centro sicurezza & conformità o in PowerShell (PowerShell di Exchange Online per le organizzazioni di Microsoft 365 con cassette postali di Exchange Online; PowerShell EOP autonomo nelle organizzazioni EOP senza cassette postali di Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="ddb53-137">You create and assign quarantine tags in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with Exchange Online Mailboxes; standalone EOP PowerShell in EOP organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ddb53-138">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="ddb53-138">What do you need to know before you begin?</span></span>

- <span data-ttu-id="ddb53-139">Aprire il Centro sicurezza e conformità in<https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="ddb53-139">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="ddb53-140">Per passare direttamente alla pagina **Tag quarantena,** aprire <https://protection.office.com/quarantineTags> .</span><span class="sxs-lookup"><span data-stu-id="ddb53-140">To go directly to the **Quarantine tags** page, open <https://protection.office.com/quarantineTags>.</span></span>

- <span data-ttu-id="ddb53-141">Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="ddb53-141">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="ddb53-142">Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="ddb53-142">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="ddb53-143">Per visualizzare, creare, modificare o rimuovere tag di quarantena, è  necessario essere membri dei ruoli **Gestione** organizzazione o Amministratore sicurezza nel [Centro sicurezza & conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="ddb53-143">To view, create, modify, or remove quarantine tags, you need to be a member of the **Organization Management** or **Security Administrator** roles in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="step-1-create-quarantine-tags-in-the-security--compliance-center"></a><span data-ttu-id="ddb53-144">Passaggio 1: Creare tag di quarantena nel Centro sicurezza & conformità</span><span class="sxs-lookup"><span data-stu-id="ddb53-144">Step 1: Create quarantine tags in the Security & Compliance Center</span></span>

1. <span data-ttu-id="ddb53-145">Nel Centro sicurezza & conformità passare a Criteri di **gestione** delle minacce \>  e quindi selezionare Tag **quarantena.**</span><span class="sxs-lookup"><span data-stu-id="ddb53-145">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

2. <span data-ttu-id="ddb53-146">Nella pagina **Tag quarantena** selezionare Aggiungi **tag personalizzato.**</span><span class="sxs-lookup"><span data-stu-id="ddb53-146">On the **Quarantine tags** page, select **Add custom tag**.</span></span>

3. <span data-ttu-id="ddb53-147">Verrà **visualizzata la procedura guidata Nuovo** tag.</span><span class="sxs-lookup"><span data-stu-id="ddb53-147">The **New tag** wizard opens.</span></span> <span data-ttu-id="ddb53-148">Nella pagina **Nome tag** immettere un nome breve ma univoco nel **campo Nome** tag.</span><span class="sxs-lookup"><span data-stu-id="ddb53-148">On the **Tag name** page, enter a brief but unique name in the **Tag name** field.</span></span> <span data-ttu-id="ddb53-149">Dovrai identificare e selezionare il tag in base al nome nei passaggi successivi.</span><span class="sxs-lookup"><span data-stu-id="ddb53-149">You'll need to identify and select the tag by name in upcoming steps.</span></span> <span data-ttu-id="ddb53-150">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="ddb53-150">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="ddb53-151">Nella pagina **Accesso messaggio destinatario** selezionare uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="ddb53-151">On the **Recipient message access** page, select one of the following values:</span></span>
   - <span data-ttu-id="ddb53-152">**Nessun accesso**</span><span class="sxs-lookup"><span data-stu-id="ddb53-152">**No access**</span></span>
   - <span data-ttu-id="ddb53-153">**Accesso limitato**</span><span class="sxs-lookup"><span data-stu-id="ddb53-153">**Limited access**</span></span>
   - <span data-ttu-id="ddb53-154">**Accesso completo**</span><span class="sxs-lookup"><span data-stu-id="ddb53-154">**Full access**</span></span>

   <span data-ttu-id="ddb53-155">Le singole autorizzazioni incluse in questi gruppi di autorizzazioni sono descritte in precedenza in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="ddb53-155">The individual permissions that are included in these permission groups are described earlier in this article.</span></span>

   <span data-ttu-id="ddb53-156">Per specificare autorizzazioni personalizzate, selezionare **Imposta accesso specifico (avanzate)** e configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ddb53-156">To specify custom permissions, select **Set specific access (Advanced)** and configure the following settings:</span></span>

     - <span data-ttu-id="ddb53-157">**Selezionare la preferenza per l'azione di** rilascio : selezionare uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="ddb53-157">**Select release action preference**: Select one of the following values:</span></span>
       - <span data-ttu-id="ddb53-158">**Nessuna azione di rilascio:** questo è il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="ddb53-158">**No release action**: This is the default value.</span></span>
       - <span data-ttu-id="ddb53-159">**Consentire ai destinatari di rilasciare un messaggio dalla quarantena**</span><span class="sxs-lookup"><span data-stu-id="ddb53-159">**Allow recipients to release a message from quarantine**</span></span>
       - <span data-ttu-id="ddb53-160">**Consentire ai destinatari di richiedere il rilascio di un messaggio dalla quarantena**</span><span class="sxs-lookup"><span data-stu-id="ddb53-160">**Allow recipients to request a message to be released from quarantine**</span></span>

     - <span data-ttu-id="ddb53-161">**Selezionare altre azioni che i destinatari possono eseguire sui** messaggi in quarantena: selezionare alcuni, tutti o nessuno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="ddb53-161">**Select additional actions recipients can take on quarantined messages**: Select some, all, or none of the following values:</span></span>
       - <span data-ttu-id="ddb53-162">**Elimina**</span><span class="sxs-lookup"><span data-stu-id="ddb53-162">**Delete**</span></span>
       - <span data-ttu-id="ddb53-163">**Anteprima**</span><span class="sxs-lookup"><span data-stu-id="ddb53-163">**Preview**</span></span>
       - <span data-ttu-id="ddb53-164">**Consenti mittente**</span><span class="sxs-lookup"><span data-stu-id="ddb53-164">**Allow sender**</span></span>
       - <span data-ttu-id="ddb53-165">**Blocca mittente**</span><span class="sxs-lookup"><span data-stu-id="ddb53-165">**Block sender**</span></span>

   <span data-ttu-id="ddb53-166">Queste autorizzazioni e il relativo effetto sui messaggi in quarantena e sulle notifiche di posta indesiderata dell'utente finale sono descritti nella sezione [Dettagli](#quarantine-tag-permission-details) delle autorizzazioni tag quarantena più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="ddb53-166">These permissions and their effect on quarantined messages and in end-user spam notifications are described in the [Quarantine tag permission details](#quarantine-tag-permission-details) section later in this article.</span></span>

   <span data-ttu-id="ddb53-167">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="ddb53-167">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="ddb53-168">Nella pagina **Riepilogo** visualizzata esaminare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="ddb53-168">On the **Summary** page that appears, review your settings.</span></span> <span data-ttu-id="ddb53-169">È possibile fare **clic su** Modifica per ogni impostazione per modificarla.</span><span class="sxs-lookup"><span data-stu-id="ddb53-169">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="ddb53-170">Al termine, fare clic su **Invia.**</span><span class="sxs-lookup"><span data-stu-id="ddb53-170">When you're finished, click **Submit**.</span></span>

6. <span data-ttu-id="ddb53-171">Fare **clic su** Fine nella pagina di conferma visualizzata.</span><span class="sxs-lookup"><span data-stu-id="ddb53-171">Click **Done** on the confirmation page that appears.</span></span>

<span data-ttu-id="ddb53-172">Ora sei pronto per assegnare il tag di quarantena a una funzionalità di quarantena, come descritto nella [sezione Passaggio 2.](#step-2-assign-a-quarantine-tag-to-supported-features)</span><span class="sxs-lookup"><span data-stu-id="ddb53-172">Now you are ready to assign the quarantine tag to a quarantine feature as described in the [Step 2](#step-2-assign-a-quarantine-tag-to-supported-features) section.</span></span>

### <a name="create-quarantine-tags-in-powershell"></a><span data-ttu-id="ddb53-173">Creare tag di quarantena in PowerShell</span><span class="sxs-lookup"><span data-stu-id="ddb53-173">Create quarantine tags in PowerShell</span></span>

<span data-ttu-id="ddb53-174">Se si preferisce utilizzare PowerShell per creare tag di quarantena, connettersi a PowerShell di Exchange Online o PowerShell di Exchange Online Protection e utilizzare il cmdlet **New-QuarantineTag.**</span><span class="sxs-lookup"><span data-stu-id="ddb53-174">If you'd rather use PowerShell to create quarantine tags, connect to Exchange Online PowerShell or Exchange Online Protection PowerShell and use the **New-QuarantineTag** cmdlet.</span></span> <span data-ttu-id="ddb53-175">Sono disponibili due metodi diversi tra cui scegliere:</span><span class="sxs-lookup"><span data-stu-id="ddb53-175">You have two different methods to choose from:</span></span>

- <span data-ttu-id="ddb53-176">Utilizzare il _parametro EndUserQuarantinePermissionsValue._</span><span class="sxs-lookup"><span data-stu-id="ddb53-176">Use the _EndUserQuarantinePermissionsValue_ parameter.</span></span>
- <span data-ttu-id="ddb53-177">Utilizzare il _parametro EndUserQuarantinePermissions._</span><span class="sxs-lookup"><span data-stu-id="ddb53-177">Use the _EndUserQuarantinePermissions_ parameter.</span></span>

<span data-ttu-id="ddb53-178">Questi metodi sono descritti nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="ddb53-178">These methods are described in the following sections.</span></span>

#### <a name="use-the-enduserquarantinepermissionsvalue-parameter"></a><span data-ttu-id="ddb53-179">Utilizzare il parametro EndUserQuarantinePermissionsValue</span><span class="sxs-lookup"><span data-stu-id="ddb53-179">Use the EndUserQuarantinePermissionsValue parameter</span></span>

<span data-ttu-id="ddb53-180">Per creare un tag di quarantena utilizzando il _parametro EndUserQuarantinePermissionsValue,_ utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="ddb53-180">To create a quarantine tag using the _EndUserQuarantinePermissionsValue_ parameter, use the following syntax:</span></span>

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissionsValue <0 to 236>
```

<span data-ttu-id="ddb53-181">Il _parametro EndUserQuarantinePermissionsValue_ utilizza un valore decimale convertito da un valore binario.</span><span class="sxs-lookup"><span data-stu-id="ddb53-181">The _EndUserQuarantinePermissionsValue_ parameter uses a decimal value that's converted from a binary value.</span></span> <span data-ttu-id="ddb53-182">Il valore binario corrisponde alle autorizzazioni disponibili per la quarantena dell'utente finale in un ordine specifico.</span><span class="sxs-lookup"><span data-stu-id="ddb53-182">The binary value corresponds to the available end-user quarantine permissions in a specific order.</span></span> <span data-ttu-id="ddb53-183">Per ogni autorizzazione, il valore 1 è uguale a True e il valore 0 è uguale a False.</span><span class="sxs-lookup"><span data-stu-id="ddb53-183">For each permission, the value 1 equals True and the value 0 equals False.</span></span>

<span data-ttu-id="ddb53-184">L'ordine e i valori necessari per ogni singola autorizzazione nei gruppi di autorizzazioni preimpostati sono descritti nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="ddb53-184">The required order and values for each individual permission in preset permission groups are described in the following table:</span></span>

****

|<span data-ttu-id="ddb53-185">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="ddb53-185">Permission</span></span>|<span data-ttu-id="ddb53-186">Nessun diritto di accesso</span><span class="sxs-lookup"><span data-stu-id="ddb53-186">No access</span></span>|<span data-ttu-id="ddb53-187">Accesso limitato</span><span class="sxs-lookup"><span data-stu-id="ddb53-187">Limited access</span></span>|<span data-ttu-id="ddb53-188">Accesso completo</span><span class="sxs-lookup"><span data-stu-id="ddb53-188">Full access</span></span>|
|---|:---:|:---:|:---:|
|<span data-ttu-id="ddb53-189">PermissionToAllowSender</span><span class="sxs-lookup"><span data-stu-id="ddb53-189">PermissionToAllowSender</span></span>|<span data-ttu-id="ddb53-190">0</span><span class="sxs-lookup"><span data-stu-id="ddb53-190">0</span></span>|<span data-ttu-id="ddb53-191">0</span><span class="sxs-lookup"><span data-stu-id="ddb53-191">0</span></span>|<span data-ttu-id="ddb53-192">1</span><span class="sxs-lookup"><span data-stu-id="ddb53-192">1</span></span>|
|<span data-ttu-id="ddb53-193">PermissionToBlockSender</span><span class="sxs-lookup"><span data-stu-id="ddb53-193">PermissionToBlockSender</span></span>|<span data-ttu-id="ddb53-194">0</span><span class="sxs-lookup"><span data-stu-id="ddb53-194">0</span></span>|<span data-ttu-id="ddb53-195">1</span><span class="sxs-lookup"><span data-stu-id="ddb53-195">1</span></span>|<span data-ttu-id="ddb53-196">1</span><span class="sxs-lookup"><span data-stu-id="ddb53-196">1</span></span>|
|<span data-ttu-id="ddb53-197">PermissionToDelete</span><span class="sxs-lookup"><span data-stu-id="ddb53-197">PermissionToDelete</span></span>|<span data-ttu-id="ddb53-198">0</span><span class="sxs-lookup"><span data-stu-id="ddb53-198">0</span></span>|<span data-ttu-id="ddb53-199">1</span><span class="sxs-lookup"><span data-stu-id="ddb53-199">1</span></span>|<span data-ttu-id="ddb53-200">1</span><span class="sxs-lookup"><span data-stu-id="ddb53-200">1</span></span>|
|<span data-ttu-id="ddb53-201">PermissionToDownload<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ddb53-201">PermissionToDownload<sup>\*</sup></span></span>|<span data-ttu-id="ddb53-202">0</span><span class="sxs-lookup"><span data-stu-id="ddb53-202">0</span></span>|<span data-ttu-id="ddb53-203">0</span><span class="sxs-lookup"><span data-stu-id="ddb53-203">0</span></span>|<span data-ttu-id="ddb53-204">0</span><span class="sxs-lookup"><span data-stu-id="ddb53-204">0</span></span>|
|<span data-ttu-id="ddb53-205">PermissionToPreview</span><span class="sxs-lookup"><span data-stu-id="ddb53-205">PermissionToPreview</span></span>|<span data-ttu-id="ddb53-206">0</span><span class="sxs-lookup"><span data-stu-id="ddb53-206">0</span></span>|<span data-ttu-id="ddb53-207">1</span><span class="sxs-lookup"><span data-stu-id="ddb53-207">1</span></span>|<span data-ttu-id="ddb53-208">1</span><span class="sxs-lookup"><span data-stu-id="ddb53-208">1</span></span>|
|<span data-ttu-id="ddb53-209">PermissionToRelease<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="ddb53-209">PermissionToRelease<sup>\*\*</sup></span></span>|<span data-ttu-id="ddb53-210">0</span><span class="sxs-lookup"><span data-stu-id="ddb53-210">0</span></span>|<span data-ttu-id="ddb53-211">0</span><span class="sxs-lookup"><span data-stu-id="ddb53-211">0</span></span>|<span data-ttu-id="ddb53-212">1</span><span class="sxs-lookup"><span data-stu-id="ddb53-212">1</span></span>|
|<span data-ttu-id="ddb53-213">PermissionToRequestRelease<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="ddb53-213">PermissionToRequestRelease<sup>\*\*</sup></span></span>|<span data-ttu-id="ddb53-214">0</span><span class="sxs-lookup"><span data-stu-id="ddb53-214">0</span></span>|<span data-ttu-id="ddb53-215">1</span><span class="sxs-lookup"><span data-stu-id="ddb53-215">1</span></span>|<span data-ttu-id="ddb53-216">0</span><span class="sxs-lookup"><span data-stu-id="ddb53-216">0</span></span>|
|<span data-ttu-id="ddb53-217">PermissionToViewHeader<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ddb53-217">PermissionToViewHeader<sup>\*</sup></span></span>|<span data-ttu-id="ddb53-218">0</span><span class="sxs-lookup"><span data-stu-id="ddb53-218">0</span></span>|<span data-ttu-id="ddb53-219">0</span><span class="sxs-lookup"><span data-stu-id="ddb53-219">0</span></span>|<span data-ttu-id="ddb53-220">0</span><span class="sxs-lookup"><span data-stu-id="ddb53-220">0</span></span>|
|<span data-ttu-id="ddb53-221">Valore binario</span><span class="sxs-lookup"><span data-stu-id="ddb53-221">Binary value</span></span>|<span data-ttu-id="ddb53-222">00000000</span><span class="sxs-lookup"><span data-stu-id="ddb53-222">00000000</span></span>|<span data-ttu-id="ddb53-223">01101010</span><span class="sxs-lookup"><span data-stu-id="ddb53-223">01101010</span></span>|<span data-ttu-id="ddb53-224">11101100</span><span class="sxs-lookup"><span data-stu-id="ddb53-224">11101100</span></span>|
|<span data-ttu-id="ddb53-225">Valore decimale da utilizzare</span><span class="sxs-lookup"><span data-stu-id="ddb53-225">Decimal value to use</span></span>|<span data-ttu-id="ddb53-226">0</span><span class="sxs-lookup"><span data-stu-id="ddb53-226">0</span></span>|<span data-ttu-id="ddb53-227">106</span><span class="sxs-lookup"><span data-stu-id="ddb53-227">106</span></span>|<span data-ttu-id="ddb53-228">236</span><span class="sxs-lookup"><span data-stu-id="ddb53-228">236</span></span>|

<span data-ttu-id="ddb53-229"><sup>\*</sup> Attualmente, questo valore è sempre 0.</span><span class="sxs-lookup"><span data-stu-id="ddb53-229"><sup>\*</sup> Currently, this value is always 0.</span></span> <span data-ttu-id="ddb53-230">Per PermissionToViewHeader, il valore 0  non nasconde il pulsante Visualizza intestazione messaggio nei dettagli del messaggio in quarantena (il pulsante è sempre disponibile).</span><span class="sxs-lookup"><span data-stu-id="ddb53-230">For PermissionToViewHeader, the value 0 doesn't hide the **View message header** button in the details of the quarantined message (the button is always available).</span></span>

<span data-ttu-id="ddb53-231"><sup>\*\*</sup> Non impostare entrambi questi valori su 1.</span><span class="sxs-lookup"><span data-stu-id="ddb53-231"><sup>\*\*</sup> Don't set both of these values to 1.</span></span> <span data-ttu-id="ddb53-232">Impostare uno su 1 e l'altro su 0 oppure impostare entrambi su 0.</span><span class="sxs-lookup"><span data-stu-id="ddb53-232">Set one to 1 and the other to 0, or set both to 0.</span></span>

<span data-ttu-id="ddb53-233">In questo esempio viene creato un nuovo nome di tag di quarantena NoAccess che assegna le autorizzazioni No access come descritto nella tabella precedente.</span><span class="sxs-lookup"><span data-stu-id="ddb53-233">This example creates a new quarantine tag name NoAccess that assigns the No access permissions as described in the previous table.</span></span>

```powershell
New-QuarantineTag -Name NoAccess -EndUserQuarantinePermissionsValue 0
```

<span data-ttu-id="ddb53-234">Per Autorizzazioni di accesso limitato, utilizzare il valore 106.</span><span class="sxs-lookup"><span data-stu-id="ddb53-234">For Limited access permissions, use the value 106.</span></span> <span data-ttu-id="ddb53-235">Per autorizzazioni di accesso completo, utilizzare il valore 236.</span><span class="sxs-lookup"><span data-stu-id="ddb53-235">For Full access permissions, use the value 236.</span></span>

<span data-ttu-id="ddb53-236">Per le autorizzazioni personalizzate, utilizzare la tabella precedente per ottenere il valore binario corrispondente alle autorizzazioni desiderate.</span><span class="sxs-lookup"><span data-stu-id="ddb53-236">For custom permissions, use the previous table to get the binary value that corresponds to the permissions you want.</span></span> <span data-ttu-id="ddb53-237">Convertire il valore binario in un valore decimale e utilizzare il valore decimale per il _parametro EndUserQuarantinePermissionsValue._</span><span class="sxs-lookup"><span data-stu-id="ddb53-237">Convert the binary value to a decimal value and use the decimal value for the _EndUserQuarantinePermissionsValue_ parameter.</span></span>

<span data-ttu-id="ddb53-238">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere New-QuarantineTag](/powershell/module/exchange/new-quarantinetag).</span><span class="sxs-lookup"><span data-stu-id="ddb53-238">For detailed syntax and parameter information, see [New-QuarantineTag](/powershell/module/exchange/new-quarantinetag).</span></span>

#### <a name="use-the-enduserquarantinepermissions-parameter"></a><span data-ttu-id="ddb53-239">Utilizzare il parametro EndUserQuarantinePermissions</span><span class="sxs-lookup"><span data-stu-id="ddb53-239">Use the EndUserQuarantinePermissions parameter</span></span>

<span data-ttu-id="ddb53-240">Per creare un tag di quarantena utilizzando il _parametro EndUserQuarantinePermissionsValue,_ eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="ddb53-240">To create a quarantine tag using the _EndUserQuarantinePermissionsValue_ parameter, do the following steps:</span></span>

<span data-ttu-id="ddb53-241">R.</span><span class="sxs-lookup"><span data-stu-id="ddb53-241">A.</span></span> <span data-ttu-id="ddb53-242">Archiviare un oggetto autorizzazioni di quarantena in una variabile utilizzando il cmdlet **New-QuarantinePermissions.**</span><span class="sxs-lookup"><span data-stu-id="ddb53-242">Store a quarantine permissions object in a variable using the **New-QuarantinePermissions** cmdlet.</span></span>

<p>

<span data-ttu-id="ddb53-243">B.</span><span class="sxs-lookup"><span data-stu-id="ddb53-243">B.</span></span> <span data-ttu-id="ddb53-244">Utilizzare la variabile come _valore EndUserQuarantinePermissions_ nel **comando New-QuarantineTag.**</span><span class="sxs-lookup"><span data-stu-id="ddb53-244">Use the variable as the _EndUserQuarantinePermissions_ value in the **New-QuarantineTag** command.</span></span>

##### <a name="step-a-store-a-quarantine-permissions-object-in-a-variable"></a><span data-ttu-id="ddb53-245">Passaggio A: Archiviare un oggetto autorizzazioni di quarantena in una variabile</span><span class="sxs-lookup"><span data-stu-id="ddb53-245">Step A: Store a quarantine permissions object in a variable</span></span>

<span data-ttu-id="ddb53-246">Usare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="ddb53-246">Use the following syntax:</span></span>

```powershell
$<VariableName> = New-QuarantinePermissions [-PermissionToAllowSender <$true | $False>] [-PermissionToBlockSender <$true | $False>] [-PermissionToDelete <$true | $False>] [-PermissionToPreview <$true | $False>] [-PermissionToRelease <$true | $False>] [-PermissionToRequestRelease <$true | $False>]
```

<span data-ttu-id="ddb53-247">Il valore predefinito per tutti i parametri inutilizzati è , quindi è necessario utilizzare solo i parametri in cui si `$false` desidera impostare value su `$true` .</span><span class="sxs-lookup"><span data-stu-id="ddb53-247">The default value for any unused parameters is `$false`, so you only need to use the parameters where you want to set value to `$true`.</span></span>

<span data-ttu-id="ddb53-248">Negli esempi seguenti viene illustrato come creare oggetti autorizzazione che corrispondono ai gruppi di autorizzazioni preimpostati:</span><span class="sxs-lookup"><span data-stu-id="ddb53-248">The following examples show how to create permission objects that correspond to the preset permissions groups:</span></span>

- <span data-ttu-id="ddb53-249">**Nessun accesso**:</span><span class="sxs-lookup"><span data-stu-id="ddb53-249">**No access**:</span></span>

  ```powershell
  $NoAccess = New-QuarantinePermissions
  ```

- <span data-ttu-id="ddb53-250">**Accesso limitato**:</span><span class="sxs-lookup"><span data-stu-id="ddb53-250">**Limited access**:</span></span>

  ```powershell
  $LimitedAccess = New-QuarantinePermissions -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRequestRelease $true
  ```

- <span data-ttu-id="ddb53-251">**Accesso completo**:</span><span class="sxs-lookup"><span data-stu-id="ddb53-251">**Full access**:</span></span>

  ```powershell
  $FullAccess = New-QuarantinePermissions -PermissionToAllowSender $true -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRelease $true
  ```

<span data-ttu-id="ddb53-252">Per visualizzare i valori impostati, eseguire il nome della variabile come comando, ad esempio eseguire il comando `$NoAccess` .</span><span class="sxs-lookup"><span data-stu-id="ddb53-252">To see the values that you've set, run the variable name as a command (for example, run the command `$NoAccess`).</span></span>

<span data-ttu-id="ddb53-253">Per le autorizzazioni personalizzate, non impostare entrambi i _parametri PermissionToRelease_ _e PermissionToRequestRelease_ su `$true` .</span><span class="sxs-lookup"><span data-stu-id="ddb53-253">For custom permissions, don't set both the _PermissionToRelease_ and _PermissionToRequestRelease_ parameters to `$true`.</span></span> <span data-ttu-id="ddb53-254">Impostare uno su `$true` e lasciare l'altro come `$false` o lasciare entrambi come `$false` .</span><span class="sxs-lookup"><span data-stu-id="ddb53-254">Set one to `$true` and leave the other as `$false`, or leave both as `$false`.</span></span>

<span data-ttu-id="ddb53-255">È inoltre possibile modificare una variabile oggetto autorizzazioni esistente dopo la creazione, ma prima di utilizzarla utilizzando il cmdlet **Set-QuarantinePermissions.**</span><span class="sxs-lookup"><span data-stu-id="ddb53-255">You can also modify an existing permissions object variable after you create but before you use it by using the **Set-QuarantinePermissions** cmdlet.</span></span>

<span data-ttu-id="ddb53-256">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [New-QuarantinePermissions](/powershell/module/exchange/new-quarantinepermissions) e [Set-QuarantinePermissions](/powershell/module/exchange/set-quarantinepermissions).</span><span class="sxs-lookup"><span data-stu-id="ddb53-256">For detailed syntax and parameter information, see [New-QuarantinePermissions](/powershell/module/exchange/new-quarantinepermissions) and [Set-QuarantinePermissions](/powershell/module/exchange/set-quarantinepermissions).</span></span>

##### <a name="step-b-use-the-variable-in-the-new-quarantinetag-command"></a><span data-ttu-id="ddb53-257">Passaggio B: Utilizzare la variabile nel New-QuarantineTag comando</span><span class="sxs-lookup"><span data-stu-id="ddb53-257">Step B: Use the variable in the New-QuarantineTag command</span></span>

<span data-ttu-id="ddb53-258">Dopo aver creato e archiviato l'oggetto autorizzazioni in una variabile, utilizzare la variabile per il valore del parametro _EndUserQuarantinePermission_ nel comando **New-QuarantineTag** seguente:</span><span class="sxs-lookup"><span data-stu-id="ddb53-258">After you've created and stored the permissions object in a variable, use the variable for the _EndUserQuarantinePermission_ parameter value in the following **New-QuarantineTag** command:</span></span>

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissions $<VariableName>
```

<span data-ttu-id="ddb53-259">In questo esempio viene creato un nuovo tag di quarantena denominato LimitedAccess utilizzando l'oggetto autorizzazioni descritto `$LimitedAccess` e creato nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="ddb53-259">This example creates a new quarantine tag named LimitedAccess using the `$LimitedAccess` permissions object that was described and created in the previous step.</span></span>

```powershell
New-QuarantineTag -Name LimitedAccess -EndUserQuarantinePermissions $LimitedAccess
```

<span data-ttu-id="ddb53-260">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere New-QuarantineTag](/powershell/module/exchange/new-quarantinetag).</span><span class="sxs-lookup"><span data-stu-id="ddb53-260">For detailed syntax and parameter information, see [New-QuarantineTag](/powershell/module/exchange/new-quarantinetag).</span></span>

## <a name="step-2-assign-a-quarantine-tag-to-supported-features"></a><span data-ttu-id="ddb53-261">Passaggio 2: Assegnare un tag di quarantena alle funzionalità supportate</span><span class="sxs-lookup"><span data-stu-id="ddb53-261">Step 2: Assign a quarantine tag to supported features</span></span>

<span data-ttu-id="ddb53-262">Nelle _funzionalità_ di protezione supportate per mettere in quarantena i messaggi o i file (automaticamente o come azione configurabile), è possibile assegnare un tag di quarantena alle azioni di quarantena disponibili.</span><span class="sxs-lookup"><span data-stu-id="ddb53-262">In _supported_ protection features that quarantine messages or files (automatically or as a configurable action), you can assign a quarantine tag to the available quarantine actions.</span></span> <span data-ttu-id="ddb53-263">Le funzionalità che consentono di mettere in quarantena i messaggi e la disponibilità dei tag di quarantena sono descritte nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="ddb53-263">Features that quarantine messages and the availability of quarantine tags are described in the following table:</span></span>

****

|<span data-ttu-id="ddb53-264">Funzionalità</span><span class="sxs-lookup"><span data-stu-id="ddb53-264">Feature</span></span>|<span data-ttu-id="ddb53-265">Tag di quarantena supportati?</span><span class="sxs-lookup"><span data-stu-id="ddb53-265">Quarantine tags supported?</span></span>|<span data-ttu-id="ddb53-266">Tag di quarantena predefiniti utilizzati</span><span class="sxs-lookup"><span data-stu-id="ddb53-266">Default quarantine tags used</span></span>|
|---|:---:|---|
|<span data-ttu-id="ddb53-267">[Criteri di protezione da posta indesiderata](configure-your-spam-filter-policies.md):</span><span class="sxs-lookup"><span data-stu-id="ddb53-267">[Anti-spam policies](configure-your-spam-filter-policies.md):</span></span> <ul><li><span data-ttu-id="ddb53-268">**Posta** indesiderata (_SpamAction_)</span><span class="sxs-lookup"><span data-stu-id="ddb53-268">**Spam** (_SpamAction_)</span></span></li><li><span data-ttu-id="ddb53-269">**Posta indesiderata ad alta** probabilità (_HighConfidenceSpamAction_)</span><span class="sxs-lookup"><span data-stu-id="ddb53-269">**High confidence spam** (_HighConfidenceSpamAction_)</span></span></li><li><span data-ttu-id="ddb53-270">**Posta elettronica di phishing** (_PhishSpamAction_)</span><span class="sxs-lookup"><span data-stu-id="ddb53-270">**Phishing email** (_PhishSpamAction_)</span></span></li><li><span data-ttu-id="ddb53-271">**Posta elettronica di phishing** ad alta probabilità (_HighConfidencePhishAction_)</span><span class="sxs-lookup"><span data-stu-id="ddb53-271">**High confidence phishing email** (_HighConfidencePhishAction_)</span></span></li><li><span data-ttu-id="ddb53-272">**Posta elettronica in** blocco (_BulkSpamAction_)</span><span class="sxs-lookup"><span data-stu-id="ddb53-272">**Bulk email** (_BulkSpamAction_)</span></span></li></ul>|<span data-ttu-id="ddb53-273">Sì</span><span class="sxs-lookup"><span data-stu-id="ddb53-273">Yes</span></span>|<ul><li><span data-ttu-id="ddb53-274">DefaultSpamTag (accesso completo)</span><span class="sxs-lookup"><span data-stu-id="ddb53-274">DefaultSpamTag (Full access)</span></span></li><li><span data-ttu-id="ddb53-275">DefaultHighConfSpamTag (accesso completo)</span><span class="sxs-lookup"><span data-stu-id="ddb53-275">DefaultHighConfSpamTag (Full access)</span></span></li><li><span data-ttu-id="ddb53-276">DefaultPhishTag (accesso completo)</span><span class="sxs-lookup"><span data-stu-id="ddb53-276">DefaultPhishTag (Full access)</span></span></li><li><span data-ttu-id="ddb53-277">DefaultHighConfPhishTag (nessun accesso)</span><span class="sxs-lookup"><span data-stu-id="ddb53-277">DefaultHighConfPhishTag (No access)</span></span></li><li><span data-ttu-id="ddb53-278">DefaultBulkTag (accesso completo)</span><span class="sxs-lookup"><span data-stu-id="ddb53-278">DefaultBulkTag (Full access)</span></span></li></ul>
|<span data-ttu-id="ddb53-279">Criteri anti-phishing:</span><span class="sxs-lookup"><span data-stu-id="ddb53-279">Anti-phishing policies:</span></span> <ul><li><span data-ttu-id="ddb53-280">[Protezione di spoofing intelligence](set-up-anti-phishing-policies.md#spoof-settings) (_AuthenticationFailAction_)</span><span class="sxs-lookup"><span data-stu-id="ddb53-280">[Spoof intelligence protection](set-up-anti-phishing-policies.md#spoof-settings) (_AuthenticationFailAction_)</span></span></li><li><span data-ttu-id="ddb53-281">[Protezione della rappresentazione](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365):<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ddb53-281">[Impersonation protection](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365):<sup>\*</sup></span></span> <ul><li><span data-ttu-id="ddb53-282">**Se la posta elettronica viene inviata da un utente rappresentato** (_TargetedUserProtectionAction_)</span><span class="sxs-lookup"><span data-stu-id="ddb53-282">**If email is sent by an impersonated user** (_TargetedUserProtectionAction_)</span></span></li><li><span data-ttu-id="ddb53-283">**Se la posta elettronica viene inviata da un dominio rappresentato** (_TargetedDomainProtectionAction_)</span><span class="sxs-lookup"><span data-stu-id="ddb53-283">**If email is sent by an impersonated domain** (_TargetedDomainProtectionAction_)</span></span></li><li><span data-ttu-id="ddb53-284">**Intelligence delle cassette postali** \> **Se la posta elettronica viene inviata da un utente rappresentato** (_MailboxIntelligenceProtectionAction_)</span><span class="sxs-lookup"><span data-stu-id="ddb53-284">**Mailbox intelligence** \> **If email is sent by an impersonated user** (_MailboxIntelligenceProtectionAction_)</span></span></li></ul></li></ul></ul>|<span data-ttu-id="ddb53-285">No</span><span class="sxs-lookup"><span data-stu-id="ddb53-285">No</span></span>|<span data-ttu-id="ddb53-286">n/d</span><span class="sxs-lookup"><span data-stu-id="ddb53-286">n/a</span></span>|
|<span data-ttu-id="ddb53-287">[Criteri antimalware:](configure-anti-malware-policies.md)tutti i messaggi rilevati vengono sempre messi in quarantena.</span><span class="sxs-lookup"><span data-stu-id="ddb53-287">[Anti-malware policies](configure-anti-malware-policies.md): All detected messages are always quarantined.</span></span>|<span data-ttu-id="ddb53-288">No</span><span class="sxs-lookup"><span data-stu-id="ddb53-288">No</span></span>|<span data-ttu-id="ddb53-289">n/d</span><span class="sxs-lookup"><span data-stu-id="ddb53-289">n/a</span></span>|
|[<span data-ttu-id="ddb53-290">Allegati sicuri per SharePoint, OneDrive e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ddb53-290">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>](atp-for-spo-odb-and-teams.md)|<span data-ttu-id="ddb53-291">No</span><span class="sxs-lookup"><span data-stu-id="ddb53-291">No</span></span>|<span data-ttu-id="ddb53-292">n/d</span><span class="sxs-lookup"><span data-stu-id="ddb53-292">n/a</span></span>|
|<span data-ttu-id="ddb53-293">[Regole del flusso di](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) posta (note anche come regole di trasporto) con l'azione: **Recapita il** messaggio alla quarantena ospitata (_Quarantine_).</span><span class="sxs-lookup"><span data-stu-id="ddb53-293">[Mail flow rules](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) with the action: **Deliver the message to the hosted quarantine** (_Quarantine_).</span></span>|<span data-ttu-id="ddb53-294">No</span><span class="sxs-lookup"><span data-stu-id="ddb53-294">No</span></span>|<span data-ttu-id="ddb53-295">n/d</span><span class="sxs-lookup"><span data-stu-id="ddb53-295">n/a</span></span>|
|

<span data-ttu-id="ddb53-296"><sup>\*</sup> Le impostazioni di protezione della rappresentazione sono disponibili solo nei criteri anti-phishing in Microsoft Defender per Office 365.</span><span class="sxs-lookup"><span data-stu-id="ddb53-296"><sup>\*</sup> Impersonation protection settings are available only in anti-phishing policies in Microsoft Defender for Office 365.</span></span>

<span data-ttu-id="ddb53-297">Se si è soddisfatti delle autorizzazioni dell'utente finale fornite dai tag di quarantena predefiniti, non è necessario eseguire alcun'operazione.</span><span class="sxs-lookup"><span data-stu-id="ddb53-297">If you're happy with the end-user permissions that are provided by the default quarantine tags, you don't need to do anything.</span></span> <span data-ttu-id="ddb53-298">Se si desidera personalizzare le funzionalità dell'utente finale (pulsanti disponibili) nelle notifiche di posta indesiderata dell'utente finale o nei dettagli dei messaggi in quarantena, è possibile assegnare un tag di quarantena personalizzato.</span><span class="sxs-lookup"><span data-stu-id="ddb53-298">If you want to customize the end-user capabilities (available buttons) in end-user spam notifications or in quarantined message details, you can assign a custom quarantine tag.</span></span>

### <a name="assign-quarantine-tags-in-anti-spam-policies-in-the-security--compliance-center"></a><span data-ttu-id="ddb53-299">Assegnare tag di quarantena nei criteri di protezione da posta indesiderata nel Centro sicurezza & conformità</span><span class="sxs-lookup"><span data-stu-id="ddb53-299">Assign quarantine tags in anti-spam policies in the Security & Compliance Center</span></span>

<span data-ttu-id="ddb53-300">Le istruzioni complete per la creazione e la modifica dei criteri di protezione da posta indesiderata sono descritte in [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="ddb53-300">Full instructions for creating and modifying anti-spam policies are described in [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

1. <span data-ttu-id="ddb53-301">Nel Centro sicurezza & conformità passare a **Criteri** di gestione delle minacce \>  \> e quindi selezionare **Protezione da posta indesiderata.**</span><span class="sxs-lookup"><span data-stu-id="ddb53-301">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> and then select **Anti-spam**.</span></span> <span data-ttu-id="ddb53-302">In caso contrario, aprire <https://protection.office.com/antispam> .</span><span class="sxs-lookup"><span data-stu-id="ddb53-302">Or, open <https://protection.office.com/antispam>.</span></span>

2. <span data-ttu-id="ddb53-303">Trovare e selezionare un criterio di protezione da posta indesiderata esistente da modificare o creare un nuovo criterio di protezione da posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="ddb53-303">Find and select an existing anti-spam policy to edit, or create a new anti-spam policy.</span></span>

3. <span data-ttu-id="ddb53-304">Nel riquadro a comparsa dei dettagli del criterio espandi la **sezione Azioni di posta indesiderata e in blocco.**</span><span class="sxs-lookup"><span data-stu-id="ddb53-304">In the policy details flyout, expand the **Spam and bulk actions** section.</span></span>

4. <span data-ttu-id="ddb53-305">Se è stato  selezionato Messaggio in quarantena per l'azione di un verdetto di filtro della posta indesiderata disponibile, la casella Applica **tag** del criterio di quarantena è disponibile per selezionare il tag di quarantena per tale verdetto.</span><span class="sxs-lookup"><span data-stu-id="ddb53-305">If you've selected **Quarantine message** for the action of an available spam filtering verdict, the **Apply quarantine policy tag** box is available for you to select the quarantine tag for that verdict.</span></span>

   <span data-ttu-id="ddb53-306">**Nota:** quando si crea un nuovo criterio, viene utilizzato un valore di tag di quarantena vuoto per un verdetto di filtro della posta indesiderata che indica il tag di quarantena predefinito per tale verdetto.</span><span class="sxs-lookup"><span data-stu-id="ddb53-306">**Note**: When you create a new policy, a blank quarantine tag value for a spam filtering verdict indicates the default quarantine tag for that verdict is used.</span></span> <span data-ttu-id="ddb53-307">Quando successivamente si modifica il criterio, i valori vuoti vengono sostituiti dai nomi dei tag di quarantena predefiniti effettivi, come descritto nella tabella precedente.</span><span class="sxs-lookup"><span data-stu-id="ddb53-307">When you later edit the policy, the blank values are replaced by the actual default quarantine tag names as described in the previous table.</span></span>

   ![Selezioni di tag di quarantena in un criterio di protezione da posta indesiderata](../../media/quarantine-tags-in-anti-spam-policies.png)

5. <span data-ttu-id="ddb53-309">Al termine, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="ddb53-309">When you're finished, click **Save**.</span></span>

#### <a name="assign-quarantine-tags-in-anti-spam-policies-in-powershell"></a><span data-ttu-id="ddb53-310">Assegnare tag di quarantena nei criteri di protezione da posta indesiderata in PowerShell</span><span class="sxs-lookup"><span data-stu-id="ddb53-310">Assign quarantine tags in anti-spam policies in PowerShell</span></span>

<span data-ttu-id="ddb53-311">Se si preferisce utilizzare PowerShell per assegnare tag di quarantena nei criteri di protezione da posta indesiderata, connettersi a PowerShell di Exchange Online o PowerShell di Exchange Online Protection e utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="ddb53-311">If you'd rather use PowerShell to assign quarantine tags in anti-spam policies, connect to Exchange Online PowerShell or Exchange Online Protection PowerShell and use the following syntax:</span></span>

```powershell
<New-HostedContentFilterPolicy -Name "<Unique name>" | Set-HostedContentFilterPolicy -Identity "<Policy name>">  [-SpamAction Quarantine] [-SpamQuarantineTag <QuarantineTagName>] [-HighConfidenceSpamAction Quarantine] [-HighConfidenceSpamQuarantineTag <QuarantineTagName>] [-PhishSpamAction Quarantine] [-PhishQuarantineTag <QuarantineTagName>] [-HighConfidencePhishQuarantineTag <QuarantineTagName>] [-BulkSpamAction Quarantine] [-BulkQuarantineTag <QuarantineTagName>] ...
```

<span data-ttu-id="ddb53-312">**Note**:</span><span class="sxs-lookup"><span data-stu-id="ddb53-312">**Notes**:</span></span>

- <span data-ttu-id="ddb53-313">Il valore predefinito per il _parametro HighConfidencePhishAction_ è Quarantine, quindi non è necessario impostare l'azione Quarantine per i rilevamenti di phishing ad alta probabilità nei nuovi criteri di protezione da posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="ddb53-313">The default value for the _HighConfidencePhishAction_ parameter is Quarantine, so you don't need to set the Quarantine action for high confidence phishing detections in new anti-spam policies.</span></span> <span data-ttu-id="ddb53-314">Per tutti gli altri verdetti di filtro della posta indesiderata nei criteri di protezione da posta indesiderata nuovi o esistenti, il tag di quarantena è efficace solo se il valore dell'azione è Quarantine.</span><span class="sxs-lookup"><span data-stu-id="ddb53-314">For all other spam filtering verdicts in new or existing anti-spam policies, the quarantine tag is only effective if the action value is Quarantine.</span></span> <span data-ttu-id="ddb53-315">Per visualizzare i valori delle azioni nei criteri di protezione da posta indesiderata esistenti, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="ddb53-315">To see the action values in existing anti-spam policies, run the following command:</span></span>

  ```powershell
  Get-HostedContentFilterPolicy | Format-Table Name,*SpamAction,HighConfidencePhishAction
  ```

  <span data-ttu-id="ddb53-316">Per informazioni sui valori di azione predefiniti e sui valori di azione consigliati per Standard e Strict, vedere Impostazioni dei criteri di protezione da posta indesiderata di [EOP.](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="ddb53-316">For information about the default action values and the recommended action values for Standard and Strict, see [EOP anti-spam policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings).</span></span>

- <span data-ttu-id="ddb53-317">Un verdetto di filtro della posta indesiderata senza un parametro tag di quarantena corrispondente indica che viene utilizzato il [tag di quarantena](#step-2-assign-a-quarantine-tag-to-supported-features) predefinito per tale verdetto.</span><span class="sxs-lookup"><span data-stu-id="ddb53-317">A spam filtering verdict without a corresponding quarantine tag parameter means the [default quarantine tag](#step-2-assign-a-quarantine-tag-to-supported-features) for that verdict is used.</span></span>

  <span data-ttu-id="ddb53-318">È necessario sostituire un tag di quarantena predefinito con un tag di quarantena personalizzato solo se si desidera modificare le funzionalità predefinite dell'utente finale nei messaggi in quarantena.</span><span class="sxs-lookup"><span data-stu-id="ddb53-318">You only need to replace a default quarantine tag with a custom quarantine tag if you want to change the default end-user capabilities on quarantined messages.</span></span>

- <span data-ttu-id="ddb53-319">Un nuovo criterio di protezione da posta indesiderata in PowerShell richiede un criterio di filtro della posta indesiderata (impostazioni) utilizzando il cmdlet **New-HostedContentFilterPolicy** e una nuova regola di filtro della posta indesiderata (filtri destinatario) utilizzando il cmdlet **New-HostedContentFilterRule.**</span><span class="sxs-lookup"><span data-stu-id="ddb53-319">A new anti-spam policy in PowerShell requires a spam filter policy (settings) using the **New-HostedContentFilterPolicy** cmdlet and a new spam filter rule (recipient filters) using the **New-HostedContentFilterRule** cmdlet.</span></span> <span data-ttu-id="ddb53-320">Per istruzioni, vedere [Usare PowerShell per creare criteri di protezione da posta indesiderata.](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies)</span><span class="sxs-lookup"><span data-stu-id="ddb53-320">For instructions, see [Use PowerShell to create anti-spam policies](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies).</span></span>

<span data-ttu-id="ddb53-321">In questo esempio viene creato un nuovo criterio di filtro della posta indesiderata denominato Research Department con le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ddb53-321">This example creates a new spam filter policy named Research Department with the following settings:</span></span>

- <span data-ttu-id="ddb53-322">L'azione per tutti i verdetti del filtro posta indesiderata è impostata su Quarantena.</span><span class="sxs-lookup"><span data-stu-id="ddb53-322">The action for all spam filtering verdicts is set to Quarantine.</span></span>
- <span data-ttu-id="ddb53-323">Il tag di quarantena personalizzato  denominato NoAccess che assegna Nessuna autorizzazione di accesso sostituisce i tag di quarantena predefiniti che non assegnano già autorizzazioni **di** accesso no per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="ddb53-323">The custom quarantine tag named NoAccess that assigns **No access** permissions replaces any default quarantine tags that don't already assign **No access** permissions by default.</span></span>

```powershell
New-HostedContentFilterPolicy -Name Research Department -SpamAction Quarantine -SpamQuarantineTag NoAccess -HighConfidenceSpamAction Quarantine -HighConfidenceSpamQuarantineTag NoAction -PhishSpamAction Quarantine -PhishQuarantineTag NoAction -BulkSpamAction Quarantine -BulkQuarantineTag NoAccess
```

<span data-ttu-id="ddb53-324">Per informazioni dettagliate su sintassi e parametri, vedere [New-HostedContentFilterPolicy](/powershell/module/exchange/new-hostedcontentfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="ddb53-324">For detailed syntax and parameter information, see [New-HostedContentFilterPolicy](/powershell/module/exchange/new-hostedcontentfilterpolicy).</span></span>

<span data-ttu-id="ddb53-325">In questo esempio viene modificato il criterio di filtro della posta indesiderata esistente denominato Human Resources.</span><span class="sxs-lookup"><span data-stu-id="ddb53-325">This example modifies the existing spam filter policy named Human Resources.</span></span> <span data-ttu-id="ddb53-326">L'azione per il verdetto della quarantena della posta indesiderata è impostata su Quarantena e viene assegnato il tag di quarantena personalizzato denominato NoAccess.</span><span class="sxs-lookup"><span data-stu-id="ddb53-326">The action for the spam quarantine verdict is set to Quarantine, and the custom quarantine tag named NoAccess is assigned.</span></span>

```powershell
Set-HostedContentFilterPolicy -Identity "Human Resources" -SpamAction Quarantine -SpamQuarantineTag NoAccess
```

<span data-ttu-id="ddb53-327">Per informazioni dettagliate su sintassi e parametri, vedere [Set-HostedContentFilterPolicy](/powershell/module/exchange/set-hostedcontentfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="ddb53-327">For detailed syntax and parameter information, see [Set-HostedContentFilterPolicy](/powershell/module/exchange/set-hostedcontentfilterpolicy).</span></span>

## <a name="configure-global-quarantine-notification-settings-in-the-security--compliance-center"></a><span data-ttu-id="ddb53-328">Configurare le impostazioni di notifica di quarantena globali nel Centro sicurezza & conformità</span><span class="sxs-lookup"><span data-stu-id="ddb53-328">Configure global quarantine notification settings in the Security & Compliance Center</span></span>

<span data-ttu-id="ddb53-329">Le impostazioni globali per i tag di quarantena consentono di personalizzare le notifiche di posta indesiderata dell'utente finale inviate ai destinatari dei messaggi messi in quarantena.</span><span class="sxs-lookup"><span data-stu-id="ddb53-329">The global settings for quarantine tags allow you to customize the end-user spam notifications that are sent to recipients of messages that were quarantined.</span></span> <span data-ttu-id="ddb53-330">Per ulteriori informazioni su queste notifiche, vedere Notifiche di posta indesiderata [dell'utente finale.](use-spam-notifications-to-release-and-report-quarantined-messages.md)</span><span class="sxs-lookup"><span data-stu-id="ddb53-330">For more information about these notifications, see [End-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

1. <span data-ttu-id="ddb53-331">Nel Centro sicurezza & conformità passare a Criteri di **gestione** delle minacce \>  e quindi selezionare Tag **quarantena.**</span><span class="sxs-lookup"><span data-stu-id="ddb53-331">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

2. <span data-ttu-id="ddb53-332">Nella pagina **Tag quarantena** selezionare **Impostazioni globali.**</span><span class="sxs-lookup"><span data-stu-id="ddb53-332">On the **Quarantine tags** page, select **Global settings**.</span></span>

3. <span data-ttu-id="ddb53-333">Nel riquadro **a comparsa Impostazioni notifica** quarantena visualizzato configurare alcune o tutte le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ddb53-333">In the **Quarantine notification settings** flyout that opens, configure some or all of the following settings:</span></span>

   - <span data-ttu-id="ddb53-334">**Usa il logo dell'azienda:** selezionare questa opzione per sostituire il logo Microsoft predefinito utilizzato nella parte superiore delle notifiche di posta indesiderata dell'utente finale.</span><span class="sxs-lookup"><span data-stu-id="ddb53-334">**Use my company logo**: Select this option to replace the default Microsoft logo that's use at the top of end-user spam notifications.</span></span> <span data-ttu-id="ddb53-335">Prima di eseguire questa operazione, è necessario seguire le istruzioni in Personalizzare il tema [di Microsoft 365](../../admin/setup/customize-your-organization-theme.md) per l'organizzazione per caricare il logo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="ddb53-335">Before you do this, you need to follow the instructions in [Customize the Microsoft 365 theme for your organization](../../admin/setup/customize-your-organization-theme.md) to upload your custom logo.</span></span>

     <span data-ttu-id="ddb53-336">Lo screenshot seguente mostra un logo personalizzato in una notifica di posta indesiderata dell'utente finale:</span><span class="sxs-lookup"><span data-stu-id="ddb53-336">The following screenshot shows a custom logo in an end-user spam notification:</span></span>

     ![Logo personalizzato in una notifica di posta indesiderata dell'utente finale](../../media/quarantine-tags-esn-customization-logo.png)

   - <span data-ttu-id="ddb53-338">**Scegli lingua:** le notifiche di posta indesiderata dell'utente finale sono già localizzate in base alle impostazioni della lingua del destinatario.</span><span class="sxs-lookup"><span data-stu-id="ddb53-338">**Choose language**: End-user spam notifications are already localized based on the recipient's language settings.</span></span> <span data-ttu-id="ddb53-339">È possibile specificare testo personalizzato in lingue diverse per i **valori Nome visualizzato** e Dichiarazione di **non** responsabilità.</span><span class="sxs-lookup"><span data-stu-id="ddb53-339">You can specify customized text in different languages for the **Display name** and **Disclaimer** values.</span></span>

     <span data-ttu-id="ddb53-340">Selezionare almeno una lingua dalla prima casella della lingua e quindi fare clic su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="ddb53-340">Select at least one language from the first language box and then click **Add**.</span></span> <span data-ttu-id="ddb53-341">È possibile selezionare più lingue facendo clic **su Aggiungi** dopo ognuna di essi.</span><span class="sxs-lookup"><span data-stu-id="ddb53-341">You can select multiple languages by clicking **Add** after each one.</span></span> <span data-ttu-id="ddb53-342">Una casella della lingua di sezione mostra tutte le lingue selezionate:</span><span class="sxs-lookup"><span data-stu-id="ddb53-342">A section language box shows all of the languages that you've selected:</span></span>

     ![Lingue selezionate nella seconda casella della lingua nelle impostazioni globali di notifica quarantena dei tag di quarantena](../../media/quarantine-tags-esn-customization-selected-languages.png)

   - <span data-ttu-id="ddb53-344">**Nome visualizzato**: consente di personalizzare il nome visualizzato del mittente utilizzato nelle notifiche di posta indesiderata dell'utente finale.</span><span class="sxs-lookup"><span data-stu-id="ddb53-344">**Display name**: Customize the sender's display name that's used in end-user spam notifications.</span></span>

     <span data-ttu-id="ddb53-345">Per ogni lingua aggiunta, selezionare la lingua nella casella Seconda lingua (non fare clic sulla X) e immettere il valore di testo desiderato nella casella **Nome** visualizzato.</span><span class="sxs-lookup"><span data-stu-id="ddb53-345">For each language that you've added, select the language in the second language box (don't click on the X) and enter the text value you want in the **Display name** box.</span></span>

     <span data-ttu-id="ddb53-346">Lo screenshot seguente mostra il nome visualizzato personalizzato in una notifica di posta indesiderata dell'utente finale:</span><span class="sxs-lookup"><span data-stu-id="ddb53-346">The following screenshot shows the customized display name in an end-user spam notification:</span></span>

     ![Nome visualizzato del mittente personalizzato in una notifica di posta indesiderata dell'utente finale](../../media/quarantine-tags-esn-customization-display-name.png)

   - <span data-ttu-id="ddb53-348">**Dichiarazione di non responsabilità**: aggiungere una dichiarazione di non responsabilità personalizzata alla fine delle notifiche di posta indesiderata dell'utente finale.</span><span class="sxs-lookup"><span data-stu-id="ddb53-348">**Disclaimer**: Add a custom disclaimer to the bottom of end-user spam notifications.</span></span> <span data-ttu-id="ddb53-349">Il testo localizzato, **Una dichiarazione di** non responsabilità dell'organizzazione: viene sempre incluso per primo, seguito dal testo specificato.</span><span class="sxs-lookup"><span data-stu-id="ddb53-349">The localized text, **A disclaimer from your organization:** is always included first, followed by the text you specify.</span></span>

     <span data-ttu-id="ddb53-350">Per ogni lingua aggiunta, selezionare la lingua nella casella Seconda lingua (non fare clic sulla X) e immettere il valore di testo desiderato nella casella Dichiarazione di **non** responsabilità.</span><span class="sxs-lookup"><span data-stu-id="ddb53-350">For each language that you've added, select the language in the second language box  (don't click the X) and enter the text value you want in the **Disclaimer** box.</span></span>

     <span data-ttu-id="ddb53-351">Lo screenshot seguente mostra la dichiarazione di non responsabilità personalizzata in una notifica di posta indesiderata dell'utente finale:</span><span class="sxs-lookup"><span data-stu-id="ddb53-351">The following screenshot shows the customized disclaimer in an end-user spam notification:</span></span>

     ![Dichiarazione di non responsabilità personalizzata nella parte inferiore di una notifica di posta indesiderata dell'utente finale](../../media/quarantine-tags-esn-customization-disclaimer.png)

## <a name="view-quarantine-tags-in-the-security--compliance-center"></a><span data-ttu-id="ddb53-353">Visualizzare i tag di quarantena nel Centro sicurezza & conformità</span><span class="sxs-lookup"><span data-stu-id="ddb53-353">View quarantine tags in the Security & Compliance Center</span></span>

1. <span data-ttu-id="ddb53-354">Nel Centro sicurezza & conformità passare a Criteri di **gestione** delle minacce \>  e quindi selezionare Tag **quarantena.**</span><span class="sxs-lookup"><span data-stu-id="ddb53-354">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

- <span data-ttu-id="ddb53-355">Per visualizzare le impostazioni dei tag di quarantena incorporati o personalizzati, selezionare il tag di quarantena nell'elenco (non selezionare la casella di controllo).</span><span class="sxs-lookup"><span data-stu-id="ddb53-355">To view the settings of built-in or custom quarantine tags, select the quarantine tag from the list (don't select the check box).</span></span>

- <span data-ttu-id="ddb53-356">Per visualizzare le impostazioni globali, selezionare **Impostazioni globali**</span><span class="sxs-lookup"><span data-stu-id="ddb53-356">To view the global settings, select **Global settings**</span></span>

### <a name="view-quarantine-tags-in-powershell"></a><span data-ttu-id="ddb53-357">Visualizzare i tag di quarantena in PowerShell</span><span class="sxs-lookup"><span data-stu-id="ddb53-357">View quarantine tags in PowerShell</span></span>

<span data-ttu-id="ddb53-358">Se si preferisce usare PowerShell per visualizzare i tag di quarantena, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ddb53-358">If you'd rather use PowerShell to view quarantine tags, do any of the following steps:</span></span>

- <span data-ttu-id="ddb53-359">Per visualizzare un elenco riepilogativo di tutti i tag predefiniti o personalizzati, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="ddb53-359">To view a summary list of all built-in or custom tags, run the following command:</span></span>

  ```powershell
  Get-QuarantineTag | Format-Table Name
  ```

- <span data-ttu-id="ddb53-360">Per visualizzare le impostazioni dei tag di quarantena incorporati o personalizzati, sostituire con il nome del \<TagName\> tag di quarantena ed eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="ddb53-360">To view the settings of built-in or custom quarantine tags, replace \<TagName\> with the name of the quarantine tag, and run the following command:</span></span>

  ```powershell
  Get-QuarantineTag -Identity "<TagName>"
  ```

- <span data-ttu-id="ddb53-361">Per visualizzare le impostazioni globali, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="ddb53-361">To view the global settings, run the following command:</span></span>

  ```powershell
  Get-QuarantineTag -QuarantineTagType GlobalQuarantineTag
  ```

<span data-ttu-id="ddb53-362">Per informazioni dettagliate su sintassi e parametri, vedere [Get-HostedContentFilterPolicy](/powershell/module/exchange/get-hostedcontentfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="ddb53-362">For detailed syntax and parameter information, see [Get-HostedContentFilterPolicy](/powershell/module/exchange/get-hostedcontentfilterpolicy).</span></span>

## <a name="remove-quarantine-tags-in-the-security--compliance-center"></a><span data-ttu-id="ddb53-363">Rimuovere i tag di quarantena nel Centro sicurezza & conformità</span><span class="sxs-lookup"><span data-stu-id="ddb53-363">Remove quarantine tags in the Security & Compliance Center</span></span>

<span data-ttu-id="ddb53-364">**Note**:</span><span class="sxs-lookup"><span data-stu-id="ddb53-364">**Notes**:</span></span>

- <span data-ttu-id="ddb53-365">Non è possibile rimuovere i tag di quarantena incorporati.</span><span class="sxs-lookup"><span data-stu-id="ddb53-365">You can't remove built-in quarantine tags.</span></span>

- <span data-ttu-id="ddb53-366">Prima di rimuovere un tag di quarantena personalizzato, verificare che non sia in uso.</span><span class="sxs-lookup"><span data-stu-id="ddb53-366">Before you remove a custom quarantine tag, verify that it's not being used.</span></span> <span data-ttu-id="ddb53-367">Ad esempio, eseguire il comando seguente in PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ddb53-367">For example, run the following command in PowerShell:</span></span>

  ```powershell
  Get-HostedContentFilterPolicy | Format-List Name,*QuarantineTag
  ```

  <span data-ttu-id="ddb53-368">Se viene utilizzato il tag di quarantena, [sostituire il tag di quarantena assegnato](#step-2-assign-a-quarantine-tag-to-supported-features) prima di rimuoverlo.</span><span class="sxs-lookup"><span data-stu-id="ddb53-368">If the quarantine tag is being used, [replace the assigned quarantine tag](#step-2-assign-a-quarantine-tag-to-supported-features) before you remove it.</span></span>

1. <span data-ttu-id="ddb53-369">Nel Centro sicurezza & conformità passare a Criteri di **gestione** delle minacce \>  e quindi selezionare Tag **quarantena.**</span><span class="sxs-lookup"><span data-stu-id="ddb53-369">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

2. <span data-ttu-id="ddb53-370">Nella pagina **Tag quarantena** selezionare il tag di quarantena personalizzato che si desidera rimuovere e fare clic su **Elimina tag.**</span><span class="sxs-lookup"><span data-stu-id="ddb53-370">On the **Quarantine tags** page, select the custom quarantine tag that you want to remove, and the click **Delete tag**.</span></span>

3. <span data-ttu-id="ddb53-371">Fare **clic su Rimuovi tag** nella finestra di dialogo di conferma visualizzata.</span><span class="sxs-lookup"><span data-stu-id="ddb53-371">Click **Remove tag** in the confirmation dialog that appears.</span></span>

### <a name="remove-quarantine-tags-in-powershell"></a><span data-ttu-id="ddb53-372">Rimuovere i tag di quarantena in PowerShell</span><span class="sxs-lookup"><span data-stu-id="ddb53-372">Remove quarantine tags in PowerShell</span></span>

<span data-ttu-id="ddb53-373">Se si preferisce usare PowerShell per rimuovere un tag di quarantena personalizzato, sostituire con il nome del \<TagName\> tag di quarantena ed eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="ddb53-373">If you'd rather use PowerShell to remove a custom quarantine tag, replace \<TagName\> with the name of the quarantine tag, and run the following command:</span></span>

```powershell
Remove-QuarantineTag -Identity "<TagName>"
```

<span data-ttu-id="ddb53-374">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Remove-QuarantineTag.](/powershell/module/exchange/remove-quarantinetag)</span><span class="sxs-lookup"><span data-stu-id="ddb53-374">For detailed syntax and parameter information, see [Remove-QuarantineTag](/powershell/module/exchange/remove-quarantinetag).</span></span>

## <a name="quarantine-tag-permission-details"></a><span data-ttu-id="ddb53-375">Dettagli autorizzazione tag quarantena</span><span class="sxs-lookup"><span data-stu-id="ddb53-375">Quarantine tag permission details</span></span>

<span data-ttu-id="ddb53-376">Nelle sezioni seguenti vengono descritti gli effetti dei gruppi di autorizzazioni preimpostati e delle singole autorizzazioni nei dettagli dei messaggi in quarantena e nelle notifiche di posta indesiderata dell'utente finale.</span><span class="sxs-lookup"><span data-stu-id="ddb53-376">The following sections describe the effects of preset permission groups and individual permissions in the details of quarantined messages and in end-user spam notifications.</span></span>

### <a name="preset-permissions-groups"></a><span data-ttu-id="ddb53-377">Gruppi di autorizzazioni preimpostati</span><span class="sxs-lookup"><span data-stu-id="ddb53-377">Preset permissions groups</span></span>

<span data-ttu-id="ddb53-378">Le singole autorizzazioni incluse nei gruppi di autorizzazioni preimpostati sono elencate nella tabella all'inizio di questo articolo.</span><span class="sxs-lookup"><span data-stu-id="ddb53-378">The individual permissions that are included in preset permission groups are listed in the table at the beginning of this article.</span></span>

#### <a name="no-access"></a><span data-ttu-id="ddb53-379">Nessun diritto di accesso</span><span class="sxs-lookup"><span data-stu-id="ddb53-379">No access</span></span>

<span data-ttu-id="ddb53-380">Se il tag di quarantena assegna le **autorizzazioni Nessun accesso** (nessuna autorizzazione), gli utenti ottengono comunque alcune funzionalità di base:</span><span class="sxs-lookup"><span data-stu-id="ddb53-380">If the quarantine tag assigns the **No access** permissions (no permissions), users still get some baseline capabilities:</span></span>

- <span data-ttu-id="ddb53-381">**Dettagli messaggio in quarantena**: il **pulsante Visualizza intestazione messaggio** è sempre disponibile.</span><span class="sxs-lookup"><span data-stu-id="ddb53-381">**Quarantined message details**: The **View message header** button is always available.</span></span>

  ![Pulsanti disponibili nei dettagli del messaggio in quarantena se il tag di quarantena assegna all'utente autorizzazioni di accesso no](../../media/quarantine-tags-quarantined-message-details-no-access.png)

- <span data-ttu-id="ddb53-383">**Notifiche di posta indesiderata dell'utente** finale : il **pulsante** Revisione che porta l'utente al messaggio in quarantena è sempre disponibile.</span><span class="sxs-lookup"><span data-stu-id="ddb53-383">**End-user spam notifications**: The **Review** button that takes the user to the message in quarantine is always available.</span></span>

  ![Pulsanti disponibili nella notifica di posta indesiderata dell'utente finale se il tag di quarantena non concede all'utente autorizzazioni di accesso](../../media/quarantine-tags-esn-no-access.png)

#### <a name="limited-access"></a><span data-ttu-id="ddb53-385">Accesso limitato</span><span class="sxs-lookup"><span data-stu-id="ddb53-385">Limited access</span></span>

<span data-ttu-id="ddb53-386">Se il tag di quarantena assegna le **autorizzazioni accesso** limitato, gli utenti ottengono le funzionalità seguenti:</span><span class="sxs-lookup"><span data-stu-id="ddb53-386">If the quarantine tag assigns the **Limited access** permissions, users get the following capabilities:</span></span>

- <span data-ttu-id="ddb53-387">**Dettagli messaggio in quarantena**: Sono disponibili i pulsanti seguenti:</span><span class="sxs-lookup"><span data-stu-id="ddb53-387">**Quarantined message details**: The following buttons are available:</span></span>
  - <span data-ttu-id="ddb53-388">**Richiesta di rilascio**</span><span class="sxs-lookup"><span data-stu-id="ddb53-388">**Request release**</span></span>
  - <span data-ttu-id="ddb53-389">**Visualizzazione delle intestazioni del messaggio**</span><span class="sxs-lookup"><span data-stu-id="ddb53-389">**View message header**</span></span>
  - <span data-ttu-id="ddb53-390">**Messaggio di anteprima**</span><span class="sxs-lookup"><span data-stu-id="ddb53-390">**Preview message**</span></span>
  - <span data-ttu-id="ddb53-391">**Blocca mittente**</span><span class="sxs-lookup"><span data-stu-id="ddb53-391">**Block sender**</span></span>
  - <span data-ttu-id="ddb53-392">**Rimuovi dalla quarantena**</span><span class="sxs-lookup"><span data-stu-id="ddb53-392">**Remove from quarantine**</span></span>

  ![Pulsanti disponibili nei dettagli del messaggio in quarantena se il tag di quarantena assegna all'utente autorizzazioni di accesso limitato](../../media/quarantine-tags-quarantined-message-details-limited-access.png)

- <span data-ttu-id="ddb53-394">**Notifiche di posta indesiderata dell'utente finale**: sono disponibili i pulsanti seguenti:</span><span class="sxs-lookup"><span data-stu-id="ddb53-394">**End-user spam notifications**: The following buttons are available:</span></span>
  - <span data-ttu-id="ddb53-395">**Blocca mittente**</span><span class="sxs-lookup"><span data-stu-id="ddb53-395">**Block sender**</span></span>
  - <span data-ttu-id="ddb53-396">**Verifica**</span><span class="sxs-lookup"><span data-stu-id="ddb53-396">**Review**</span></span>

  ![Pulsanti disponibili nella notifica di posta indesiderata dell'utente finale se il tag di quarantena concede all'utente autorizzazioni di accesso limitato](../../media/quarantine-tags-esn-limited-access.png)

#### <a name="full-access"></a><span data-ttu-id="ddb53-398">Accesso completo</span><span class="sxs-lookup"><span data-stu-id="ddb53-398">Full access</span></span>

<span data-ttu-id="ddb53-399">Se il tag di quarantena assegna le **autorizzazioni di accesso** completo (tutte le autorizzazioni disponibili), gli utenti ottengono le funzionalità seguenti:</span><span class="sxs-lookup"><span data-stu-id="ddb53-399">If the quarantine tag assigns the **Full access** permissions (all available permissions), users get the following capabilities:</span></span>

- <span data-ttu-id="ddb53-400">**Dettagli messaggio in quarantena**: Sono disponibili i pulsanti seguenti:</span><span class="sxs-lookup"><span data-stu-id="ddb53-400">**Quarantined message details**: The following buttons are available:</span></span>
  - <span data-ttu-id="ddb53-401">**Messaggio di rilascio**</span><span class="sxs-lookup"><span data-stu-id="ddb53-401">**Release message**</span></span>
  - <span data-ttu-id="ddb53-402">**Visualizzazione delle intestazioni del messaggio**</span><span class="sxs-lookup"><span data-stu-id="ddb53-402">**View message header**</span></span>
  - <span data-ttu-id="ddb53-403">**Messaggio di anteprima**</span><span class="sxs-lookup"><span data-stu-id="ddb53-403">**Preview message**</span></span>
  - <span data-ttu-id="ddb53-404">**Blocca mittente**</span><span class="sxs-lookup"><span data-stu-id="ddb53-404">**Block sender**</span></span>
  - <span data-ttu-id="ddb53-405">**Consenti mittente**</span><span class="sxs-lookup"><span data-stu-id="ddb53-405">**Allow sender**</span></span>
  - <span data-ttu-id="ddb53-406">**Rimuovi dalla quarantena**</span><span class="sxs-lookup"><span data-stu-id="ddb53-406">**Remove from quarantine**</span></span>

  ![Pulsanti disponibili nei dettagli del messaggio in quarantena se il tag di quarantena assegna all'utente autorizzazioni di accesso completo](../../media/quarantine-tags-quarantined-message-details-full-access.png)

- <span data-ttu-id="ddb53-408">**Notifiche di posta indesiderata dell'utente finale**: sono disponibili i pulsanti seguenti:</span><span class="sxs-lookup"><span data-stu-id="ddb53-408">**End-user spam notifications**: The following buttons are available:</span></span>
  - <span data-ttu-id="ddb53-409">**Blocca mittente**</span><span class="sxs-lookup"><span data-stu-id="ddb53-409">**Block sender**</span></span>
  - <span data-ttu-id="ddb53-410">**Rilascio**</span><span class="sxs-lookup"><span data-stu-id="ddb53-410">**Release**</span></span>
  - <span data-ttu-id="ddb53-411">**Verifica**</span><span class="sxs-lookup"><span data-stu-id="ddb53-411">**Review**</span></span>

  ![Pulsanti disponibili nella notifica di posta indesiderata dell'utente finale se il tag di quarantena assegna all'utente autorizzazioni di accesso completo](../../media/quarantine-tags-esn-full-access.png)

### <a name="individual-permissions"></a><span data-ttu-id="ddb53-413">Autorizzazioni individuali</span><span class="sxs-lookup"><span data-stu-id="ddb53-413">Individual permissions</span></span>

> [!NOTE]
> <span data-ttu-id="ddb53-414">Tenere presente che gli utenti ottengono sempre i pulsanti descritti nella [sezione Nessun](#no-access) accesso.</span><span class="sxs-lookup"><span data-stu-id="ddb53-414">Remember, users always get the buttons described in the [No access](#no-access) section.</span></span> <span data-ttu-id="ddb53-415">Questi pulsanti non sono inclusi nelle descrizioni delle singole autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="ddb53-415">These buttons are not included in the individual permission descriptions.</span></span>

#### <a name="allow-sender-permission"></a><span data-ttu-id="ddb53-416">Consenti autorizzazione mittente</span><span class="sxs-lookup"><span data-stu-id="ddb53-416">Allow sender permission</span></span>

<span data-ttu-id="ddb53-417">**L'autorizzazione** Consenti mittente (_PermissionToAllowSender_) controlla l'accesso al pulsante che consente agli utenti di aggiungere comodamente il mittente del messaggio in quarantena all'elenco Mittenti attendibili.</span><span class="sxs-lookup"><span data-stu-id="ddb53-417">The **Allow sender** permission (_PermissionToAllowSender_) controls access to the button that allows users to conveniently add the quarantined message sender to their Safe Senders list.</span></span>

- <span data-ttu-id="ddb53-418">**Dettagli messaggio in quarantena**:</span><span class="sxs-lookup"><span data-stu-id="ddb53-418">**Quarantined message details**:</span></span>
  - <span data-ttu-id="ddb53-419">**Autorizzazione Consenti mittente** abilitata: il pulsante Consenti **mittente** è disponibile.</span><span class="sxs-lookup"><span data-stu-id="ddb53-419">**Allow sender** permission enabled: The **Allow sender** button is available.</span></span>
  - <span data-ttu-id="ddb53-420">**Consenti autorizzazione mittente** disabilitata: il **pulsante** Consenti mittente non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="ddb53-420">**Allow sender** permission disabled: The **Allow sender** button is not available.</span></span>

- <span data-ttu-id="ddb53-421">**Notifiche di posta indesiderata dell'utente finale**: Nessun effetto.</span><span class="sxs-lookup"><span data-stu-id="ddb53-421">**End-user spam notifications**: No effect.</span></span>

<span data-ttu-id="ddb53-422">Per ulteriori informazioni sull'elenco Mittenti attendibili, vedere [Prevent trusted senders from being blocked](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379666) e Use Exchange Online [PowerShell to configure the safelist collection on a mailbox.](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox)</span><span class="sxs-lookup"><span data-stu-id="ddb53-422">For more information about the Safe Senders list, see [Prevent trusted senders from being blocked](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379666) and [Use Exchange Online PowerShell to configure the safelist collection on a mailbox](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span></span>

#### <a name="block-sender-permission"></a><span data-ttu-id="ddb53-423">Blocca autorizzazione mittente</span><span class="sxs-lookup"><span data-stu-id="ddb53-423">Block sender permission</span></span>

<span data-ttu-id="ddb53-424">**L'autorizzazione** Blocca mittente (_PermissionToBlockSender_) controlla l'accesso al pulsante che consente agli utenti di aggiungere comodamente il mittente del messaggio in quarantena all'elenco Mittenti bloccati.</span><span class="sxs-lookup"><span data-stu-id="ddb53-424">The **Block sender** permission (_PermissionToBlockSender_) controls access to the button that allows users to conveniently add the quarantined message sender to their Blocked Senders list.</span></span>

- <span data-ttu-id="ddb53-425">**Dettagli messaggio in quarantena**:</span><span class="sxs-lookup"><span data-stu-id="ddb53-425">**Quarantined message details**:</span></span>
  - <span data-ttu-id="ddb53-426">**Autorizzazione Blocca mittente** abilitata: il pulsante Blocca **mittente** è disponibile.</span><span class="sxs-lookup"><span data-stu-id="ddb53-426">**Block sender** permission enabled: The **Block sender** button is available.</span></span>
  - <span data-ttu-id="ddb53-427">**Autorizzazione Blocca mittente** disabilitata: il **pulsante** Blocca mittente non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="ddb53-427">**Block sender** permission disabled: The **Block sender** button is not available.</span></span>

- <span data-ttu-id="ddb53-428">**Notifiche di posta indesiderata dell'utente finale**:</span><span class="sxs-lookup"><span data-stu-id="ddb53-428">**End-user spam notifications**:</span></span>
  - <span data-ttu-id="ddb53-429">**Autorizzazione Blocca mittente** disabilitata: il **pulsante** Blocca mittente non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="ddb53-429">**Block sender** permission disabled: The **Block sender** button is not available.</span></span>
  - <span data-ttu-id="ddb53-430">**Autorizzazione Blocca mittente** abilitata: il pulsante Blocca **mittente** è disponibile.</span><span class="sxs-lookup"><span data-stu-id="ddb53-430">**Block sender** permission enabled: The **Block sender** button is available.</span></span>

<span data-ttu-id="ddb53-431">Per ulteriori informazioni sull'elenco Mittenti bloccati, vedere [Block messages from someone](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667) e Use Exchange Online [PowerShell to configure the safelist collection on a mailbox.](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox)</span><span class="sxs-lookup"><span data-stu-id="ddb53-431">For more information about the Blocked Senders list, see [Block messages from someone](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667) and [Use Exchange Online PowerShell to configure the safelist collection on a mailbox](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span></span>

#### <a name="delete-permission"></a><span data-ttu-id="ddb53-432">Autorizzazione di eliminazione</span><span class="sxs-lookup"><span data-stu-id="ddb53-432">Delete permission</span></span>

<span data-ttu-id="ddb53-433">**L'autorizzazione** Delete (_PermissionToDelete_) controlla la possibilità per gli utenti di eliminare i propri messaggi (messaggi in cui l'utente è un destinatario) dalla quarantena.</span><span class="sxs-lookup"><span data-stu-id="ddb53-433">The **Delete** permission (_PermissionToDelete_) controls the ability to of users to delete their messages (messages where the user is a recipient) from quarantine.</span></span>

- <span data-ttu-id="ddb53-434">**Dettagli messaggio in quarantena**:</span><span class="sxs-lookup"><span data-stu-id="ddb53-434">**Quarantined message details**:</span></span>
  - <span data-ttu-id="ddb53-435">**Autorizzazione** di eliminazione abilitata: **il pulsante Rimuovi dalla** quarantena è disponibile.</span><span class="sxs-lookup"><span data-stu-id="ddb53-435">**Delete** permission enabled: The **Remove from quarantine** button is available.</span></span>
  - <span data-ttu-id="ddb53-436">**Autorizzazione** di eliminazione disabilitata: **il pulsante Rimuovi dalla** quarantena non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="ddb53-436">**Delete** permission disabled: The **Remove from quarantine** button is not available.</span></span>

- <span data-ttu-id="ddb53-437">**Notifiche di posta indesiderata dell'utente finale**: Nessun effetto.</span><span class="sxs-lookup"><span data-stu-id="ddb53-437">**End-user spam notifications**: No effect.</span></span>

#### <a name="preview-permission"></a><span data-ttu-id="ddb53-438">Autorizzazione anteprima</span><span class="sxs-lookup"><span data-stu-id="ddb53-438">Preview permission</span></span>

<span data-ttu-id="ddb53-439">**L'autorizzazione** Anteprima (_PermissionToPreview_) controlla la possibilità per gli utenti di visualizzare in anteprima i messaggi in quarantena.</span><span class="sxs-lookup"><span data-stu-id="ddb53-439">The **Preview** permission (_PermissionToPreview_) controls the ability to of users to preview their messages in quarantine.</span></span>

- <span data-ttu-id="ddb53-440">**Dettagli messaggio in quarantena**:</span><span class="sxs-lookup"><span data-stu-id="ddb53-440">**Quarantined message details**:</span></span>
  - <span data-ttu-id="ddb53-441">**Autorizzazione anteprima** abilitata: il **pulsante Anteprima** messaggio è disponibile.</span><span class="sxs-lookup"><span data-stu-id="ddb53-441">**Preview** permission enabled: The **Preview message** button is available.</span></span>
  - <span data-ttu-id="ddb53-442">**Autorizzazione anteprima** disabilitata: il **pulsante Anteprima** messaggio non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="ddb53-442">**Preview** permission disabled: The **Preview message** button is not available.</span></span>

- <span data-ttu-id="ddb53-443">**Notifiche di posta indesiderata dell'utente finale**: Nessun effetto.</span><span class="sxs-lookup"><span data-stu-id="ddb53-443">**End-user spam notifications**: No effect.</span></span>

#### <a name="allow-recipients-to-release-a-message-from-quarantine-permission"></a><span data-ttu-id="ddb53-444">Consentire ai destinatari di rilasciare un messaggio dall'autorizzazione di quarantena</span><span class="sxs-lookup"><span data-stu-id="ddb53-444">Allow recipients to release a message from quarantine permission</span></span>

<span data-ttu-id="ddb53-445">**L'autorizzazione** Consenti ai destinatari di rilasciare un messaggio dalla quarantena (_PermissionToRelease_) controlla la possibilità degli utenti di rilasciare i messaggi in quarantena direttamente e senza l'approvazione di un amministratore.</span><span class="sxs-lookup"><span data-stu-id="ddb53-445">The **Allow recipients to release a message from quarantine** permission (_PermissionToRelease_) controls the ability of users to release their quarantined messages directly and without the approval of an admin.</span></span>

- <span data-ttu-id="ddb53-446">**Dettagli messaggio in quarantena**:</span><span class="sxs-lookup"><span data-stu-id="ddb53-446">**Quarantined message details**:</span></span>
  - <span data-ttu-id="ddb53-447">Autorizzazione abilitata: il **pulsante Rilascia** messaggio è disponibile.</span><span class="sxs-lookup"><span data-stu-id="ddb53-447">Permission enabled: The **Release message** button is available.</span></span>
  - <span data-ttu-id="ddb53-448">Autorizzazione disabilitata: il **pulsante Rilascia** messaggio non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="ddb53-448">Permission disabled: The **Release message** button is not available.</span></span>

- <span data-ttu-id="ddb53-449">**Notifiche di posta indesiderata dell'utente finale**:</span><span class="sxs-lookup"><span data-stu-id="ddb53-449">**End-user spam notifications**:</span></span>
  - <span data-ttu-id="ddb53-450">Autorizzazione abilitata: il **pulsante Rilascia** è disponibile.</span><span class="sxs-lookup"><span data-stu-id="ddb53-450">Permission enabled: The **Release** button is available.</span></span>
  - <span data-ttu-id="ddb53-451">Autorizzazione disabilitata: **il pulsante** Rilascia non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="ddb53-451">Permission disabled: The **Release** button is not available.</span></span>

#### <a name="allow-recipients-to-request-a-message-to-be-released-from-quarantine-permission"></a><span data-ttu-id="ddb53-452">Consentire ai destinatari di richiedere il rilascio di un messaggio dall'autorizzazione di quarantena</span><span class="sxs-lookup"><span data-stu-id="ddb53-452">Allow recipients to request a message to be released from quarantine permission</span></span>

<span data-ttu-id="ddb53-453">**L'autorizzazione** Consenti ai destinatari di richiedere il rilascio di un messaggio dalla quarantena  (_PermissionToRequestRelease_) controlla la capacità degli utenti di richiedere il rilascio dei messaggi in quarantena.</span><span class="sxs-lookup"><span data-stu-id="ddb53-453">The **Allow recipients to request a message to be released from quarantine** permission (_PermissionToRequestRelease_) controls the ability of users to _request_ the release of their quarantined messages.</span></span> <span data-ttu-id="ddb53-454">Il messaggio viene rilasciato solo dopo che un amministratore approva la richiesta.</span><span class="sxs-lookup"><span data-stu-id="ddb53-454">The message is only released after an admin approves the request.</span></span>

- <span data-ttu-id="ddb53-455">**Dettagli messaggio in quarantena**:</span><span class="sxs-lookup"><span data-stu-id="ddb53-455">**Quarantined message details**:</span></span>
  - <span data-ttu-id="ddb53-456">Autorizzazione abilitata: **il pulsante Richiedi** rilascio è disponibile.</span><span class="sxs-lookup"><span data-stu-id="ddb53-456">Permission enabled: The **Request release** button is available.</span></span>
  - <span data-ttu-id="ddb53-457">Autorizzazione disabilitata: **il pulsante Richiedi** rilascio non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="ddb53-457">Permission disabled: The **Request release** button is not available.</span></span>

- <span data-ttu-id="ddb53-458">**Notifiche di posta indesiderata dell'utente finale**: **il pulsante** Rilascia non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="ddb53-458">**End-user spam notifications**: The **Release** button is not available.</span></span>