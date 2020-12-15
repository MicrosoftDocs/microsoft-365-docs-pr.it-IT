---
title: Tag di quarantena
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
ROBOTS: NOINDEX
description: Gli amministratori possono imparare a usare i tag di quarantena per controllare quali utenti sono in grado di eseguire nei messaggi in quarantena.
ms.openlocfilehash: 167f147d7c74b78b1a1661b5444625fbf1cf3d41
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/15/2020
ms.locfileid: "49683068"
---
# <a name="quarantine-tags"></a><span data-ttu-id="a9998-103">Tag di quarantena</span><span class="sxs-lookup"><span data-stu-id="a9998-103">Quarantine tags</span></span>

> [!NOTE]
> <span data-ttu-id="a9998-104">Le funzionalità descritte in questo articolo sono attualmente in anteprima, non sono disponibili per tutti gli utenti e sono soggette a modifiche.</span><span class="sxs-lookup"><span data-stu-id="a9998-104">The features that are described in this article are currently in Preview, aren't available to everyone, and are subject to change.</span></span>

<span data-ttu-id="a9998-105">I tag di quarantena in Exchange Online Protection (EOP) consentono agli amministratori di controllare quali utenti sono in grado di eseguire nei messaggi in quarantena in base al modo in cui il messaggio è arrivato in quarantena.</span><span class="sxs-lookup"><span data-stu-id="a9998-105">Quarantine tags in Exchange Online Protection (EOP) allow admins to control what users are able to do to their quarantined messages based on how the message arrived in quarantine.</span></span>

<span data-ttu-id="a9998-106">EOP ha tradizionalmente consentito o impedito alcuni livelli di interattività per i messaggi in [quarantena](find-and-release-quarantined-messages-as-a-user.md) e nelle [notifiche di posta indesiderata dell'utente finale](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span><span class="sxs-lookup"><span data-stu-id="a9998-106">EOP has traditionally allowed or prevented certain levels of interactivity for messages in [quarantine](find-and-release-quarantined-messages-as-a-user.md) and in [end-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span> <span data-ttu-id="a9998-107">Ad esempio, gli utenti finali possono visualizzare e rilasciare i messaggi che sono stati messi in quarantena dal filtro antispam come posta indesiderata o in blocco, ma non possono visualizzare o rilasciare messaggi che sono stati messi in quarantena come phishing ad alta sicurezza.</span><span class="sxs-lookup"><span data-stu-id="a9998-107">For example, end-users can view and release messages that were quarantined by anti-spam filtering as spam or bulk, but they can't view or release messages that were quarantined as high confidence phishing.</span></span>

<span data-ttu-id="a9998-108">Per le [funzionalità di protezione supportate](#step-2-assign-a-quarantine-tag-to-supported-features), i tag Quarantine specificano quali utenti sono autorizzati a eseguire nei messaggi di notifica di posta indesiderata dell'utente finale e nei messaggi in quarantena (messaggi in cui l'utente è destinatario).</span><span class="sxs-lookup"><span data-stu-id="a9998-108">For [supported protection features](#step-2-assign-a-quarantine-tag-to-supported-features), quarantine tags specify what users are allowed to do in end-user spam notification messages and in their quarantined messages in quarantine (messages where the user is a recipient).</span></span> <span data-ttu-id="a9998-109">I tag di quarantena predefiniti vengono assegnati automaticamente per applicare le funzionalità storiche per gli utenti finali nei messaggi in quarantena.</span><span class="sxs-lookup"><span data-stu-id="a9998-109">Default quarantine tags are automatically assigned to enforce the historical capabilities for end-users on quarantined messages.</span></span> <span data-ttu-id="a9998-110">In alternativa, è possibile creare e assegnare tag di quarantena personalizzati per consentire o impedire agli utenti finali di eseguire azioni specifiche sui messaggi in quarantena.</span><span class="sxs-lookup"><span data-stu-id="a9998-110">Or, you can create and assign custom quarantine tags to allow or prevent end-users from performing specific actions on quarantined messages.</span></span>

<span data-ttu-id="a9998-111">Le singole autorizzazioni vengono combinate nei seguenti gruppi di autorizzazioni preimpostati:</span><span class="sxs-lookup"><span data-stu-id="a9998-111">The individual permissions are combined into the following preset permission groups:</span></span>

- <span data-ttu-id="a9998-112">Nessun diritto di accesso</span><span class="sxs-lookup"><span data-stu-id="a9998-112">No access</span></span>
- <span data-ttu-id="a9998-113">Accesso limitato</span><span class="sxs-lookup"><span data-stu-id="a9998-113">Limited access</span></span>
- <span data-ttu-id="a9998-114">Accesso completo</span><span class="sxs-lookup"><span data-stu-id="a9998-114">Full access</span></span>

<span data-ttu-id="a9998-115">Nella tabella seguente sono descritte le autorizzazioni individuali disponibili e quelle incluse o non incluse nei gruppi di autorizzazioni preimpostati:</span><span class="sxs-lookup"><span data-stu-id="a9998-115">The available individual permissions and what's included or not included in the preset permission groups are described in the following table:</span></span>

|<span data-ttu-id="a9998-116">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="a9998-116">Permission</span></span>|<span data-ttu-id="a9998-117">Nessun diritto di accesso</span><span class="sxs-lookup"><span data-stu-id="a9998-117">No access</span></span>|<span data-ttu-id="a9998-118">Accesso limitato</span><span class="sxs-lookup"><span data-stu-id="a9998-118">Limited access</span></span>|<span data-ttu-id="a9998-119">Accesso completo</span><span class="sxs-lookup"><span data-stu-id="a9998-119">Full access</span></span>|
|---|:---:|:---:|:---:|
|<span data-ttu-id="a9998-120">**Consenti mittente** (_PermissionToAllowSender_)</span><span class="sxs-lookup"><span data-stu-id="a9998-120">**Allow sender** (_PermissionToAllowSender_)</span></span>|||![Segno di spunta](../../media/checkmark.png)|
|<span data-ttu-id="a9998-122">**Blocca mittente** (_PermissionToBlockSender_)</span><span class="sxs-lookup"><span data-stu-id="a9998-122">**Block sender** (_PermissionToBlockSender_)</span></span>||![Segno di spunta](../../media/checkmark.png)|![Segno di spunta](../../media/checkmark.png)|
|<span data-ttu-id="a9998-125">**Delete** (_PermissionToDelete_)</span><span class="sxs-lookup"><span data-stu-id="a9998-125">**Delete** (_PermissionToDelete_)</span></span>||![Segno di spunta](../../media/checkmark.png)|![Segno di spunta](../../media/checkmark.png)|
|<span data-ttu-id="a9998-128">**Anteprima** (_PermissionToPreview_)</span><span class="sxs-lookup"><span data-stu-id="a9998-128">**Preview** (_PermissionToPreview_)</span></span>||![Segno di spunta](../../media/checkmark.png)|![Segno di spunta](../../media/checkmark.png)|
|<span data-ttu-id="a9998-131">**Consenti ai destinatari di rilasciare un messaggio dalla quarantena** (_PermissionToRelease_)</span><span class="sxs-lookup"><span data-stu-id="a9998-131">**Allow recipients to release a message from quarantine** (_PermissionToRelease_)</span></span>|||![Segno di spunta](../../media/checkmark.png)|
|<span data-ttu-id="a9998-133">**Consenti ai destinatari di richiedere il rilascio di un messaggio dalla quarantena** (_PermissionToRequestRelease_)</span><span class="sxs-lookup"><span data-stu-id="a9998-133">**Allow recipients to request a message to be released from quarantine** (_PermissionToRequestRelease_)</span></span>||![Segno di spunta](../../media/checkmark.png)||
|

<span data-ttu-id="a9998-135">Se non si desiderano le autorizzazioni predefinite nei gruppi di autorizzazioni preimpostati, è possibile utilizzare le autorizzazioni personalizzate quando si creano o si modificano i tag di quarantena personalizzati.</span><span class="sxs-lookup"><span data-stu-id="a9998-135">If you don't like the default permissions in the preset permission groups, you can use custom permissions when you create or modify custom quarantine tags.</span></span> <span data-ttu-id="a9998-136">Per ulteriori informazioni sulle operazioni eseguite da ogni autorizzazione, vedere la sezione relativa alle autorizzazioni per i [tag di quarantena](#quarantine-tag-permission-details) più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="a9998-136">For more information about what each permission does, see the [Quarantine tag permission details](#quarantine-tag-permission-details) section later in this article.</span></span>

<span data-ttu-id="a9998-137">È possibile creare e assegnare tag di quarantena nel centro sicurezza & Compliance o in PowerShell (Exchange Online PowerShell per Microsoft 365 organizzazioni con cassette postali di Exchange Online; standalone EOP PowerShell nelle organizzazioni di EOP senza cassette postali di Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="a9998-137">You create and assign quarantine tags in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with Exchange Online Mailboxes; standalone EOP PowerShell in EOP organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a9998-138">Che cosa è necessario sapere prima di iniziare?</span><span class="sxs-lookup"><span data-stu-id="a9998-138">What do you need to know before you begin?</span></span>

- <span data-ttu-id="a9998-139">Aprire il Centro sicurezza e conformità in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="a9998-139">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="a9998-140">Per passare direttamente alla pagina dei **tag di quarantena** , Apri <https://protection.office.com/quarantineTags> .</span><span class="sxs-lookup"><span data-stu-id="a9998-140">To go directly to the **Quarantine tags** page, open <https://protection.office.com/quarantineTags>.</span></span>

- <span data-ttu-id="a9998-141">Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="a9998-141">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="a9998-142">Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="a9998-142">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="a9998-143">Per visualizzare, creare, modificare o rimuovere i tag di quarantena, è necessario essere membri dei ruoli **Gestione organizzazione** o **amministratore sicurezza** nel [Centro sicurezza & Compliance](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="a9998-143">To view, create, modify, or remove quarantine tags, you need to be a member of the **Organization Management** or **Security Administrator** roles in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="step-1-create-quarantine-tags-in-the-security--compliance-center"></a><span data-ttu-id="a9998-144">Passaggio 1: creare tag di quarantena nel centro sicurezza & Compliance</span><span class="sxs-lookup"><span data-stu-id="a9998-144">Step 1: Create quarantine tags in the Security & Compliance Center</span></span>

1. <span data-ttu-id="a9998-145">Nel centro sicurezza & conformità, accedere a criteri di **gestione delle minacce** \>  e quindi selezionare i **tag di quarantena**.</span><span class="sxs-lookup"><span data-stu-id="a9998-145">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

2. <span data-ttu-id="a9998-146">Nella pagina dei **tag di quarantena** , selezionare **Aggiungi tag personalizzato**.</span><span class="sxs-lookup"><span data-stu-id="a9998-146">On the **Quarantine tags** page, select **Add custom tag**.</span></span>

3. <span data-ttu-id="a9998-147">Verrà visualizzata la procedura guidata **nuovo tag** .</span><span class="sxs-lookup"><span data-stu-id="a9998-147">The **New tag** wizard opens.</span></span> <span data-ttu-id="a9998-148">Nella pagina **nome tag** immettere un nome breve ma univoco nel campo **nome tag** .</span><span class="sxs-lookup"><span data-stu-id="a9998-148">On the **Tag name** page, enter a brief but unique name in the **Tag name** field.</span></span> <span data-ttu-id="a9998-149">È necessario identificare e selezionare il tag per nome nei passaggi imminenti.</span><span class="sxs-lookup"><span data-stu-id="a9998-149">You'll need to identify and select the tag by name in upcoming steps.</span></span> <span data-ttu-id="a9998-150">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a9998-150">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="a9998-151">Nella pagina **accesso ai messaggi destinatario** selezionare uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="a9998-151">On the **Recipient message access** page, select one of the following values:</span></span>
   - <span data-ttu-id="a9998-152">**Nessun accesso**</span><span class="sxs-lookup"><span data-stu-id="a9998-152">**No access**</span></span>
   - <span data-ttu-id="a9998-153">**Accesso limitato**</span><span class="sxs-lookup"><span data-stu-id="a9998-153">**Limited access**</span></span>
   - <span data-ttu-id="a9998-154">**Accesso completo**</span><span class="sxs-lookup"><span data-stu-id="a9998-154">**Full access**</span></span>

   <span data-ttu-id="a9998-155">Le singole autorizzazioni incluse in questi gruppi di autorizzazioni sono descritte in precedenza in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="a9998-155">The individual permissions that are included in these permission groups are described earlier in this article.</span></span>

   <span data-ttu-id="a9998-156">Per specificare le autorizzazioni personalizzate, selezionare **Imposta accesso specifico (avanzato)** e configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a9998-156">To specify custom permissions, select **Set specific access (Advanced)** and configure the following settings:</span></span>

     - <span data-ttu-id="a9998-157">**Selezionare la preferenza azione di rilascio**: selezionare uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="a9998-157">**Select release action preference**: Select one of the following values:</span></span>
       - <span data-ttu-id="a9998-158">**Nessuna azione di rilascio**: questo è il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="a9998-158">**No release action**: This is the default value.</span></span>
       - <span data-ttu-id="a9998-159">**Consenti ai destinatari di rilasciare un messaggio dalla quarantena**</span><span class="sxs-lookup"><span data-stu-id="a9998-159">**Allow recipients to release a message from quarantine**</span></span>
       - <span data-ttu-id="a9998-160">**Consenti ai destinatari di richiedere il rilascio di un messaggio dalla quarantena**</span><span class="sxs-lookup"><span data-stu-id="a9998-160">**Allow recipients to request a message to be released from quarantine**</span></span>

     - <span data-ttu-id="a9998-161">**Selezionare ulteriori azioni che i destinatari possono intraprendere nei messaggi in quarantena**: selezionare alcuni, tutti o nessuno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="a9998-161">**Select additional actions recipients can take on quarantined messages**: Select some, all, or none of the following values:</span></span>
       - <span data-ttu-id="a9998-162">**Elimina**</span><span class="sxs-lookup"><span data-stu-id="a9998-162">**Delete**</span></span>
       - <span data-ttu-id="a9998-163">**Anteprima**</span><span class="sxs-lookup"><span data-stu-id="a9998-163">**Preview**</span></span>
       - <span data-ttu-id="a9998-164">**Consenti mittente**</span><span class="sxs-lookup"><span data-stu-id="a9998-164">**Allow sender**</span></span>
       - <span data-ttu-id="a9998-165">**Blocca mittente**</span><span class="sxs-lookup"><span data-stu-id="a9998-165">**Block sender**</span></span>

   <span data-ttu-id="a9998-166">Queste autorizzazioni e il loro effetto sui messaggi in quarantena e nelle notifiche di posta indesiderata dell'utente finale sono descritte nella sezione [informazioni sulle autorizzazioni dei tag di quarantena](#quarantine-tag-permission-details) più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="a9998-166">These permissions and their effect on quarantined messages and in end-user spam notifications are described in the [Quarantine tag permission details](#quarantine-tag-permission-details) section later in this article.</span></span>

   <span data-ttu-id="a9998-167">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a9998-167">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="a9998-168">Nella pagina **Riepilogo** visualizzata, esaminare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="a9998-168">On the **Summary** page that appears, review your settings.</span></span> <span data-ttu-id="a9998-169">È possibile fare clic su **modifica** su ogni impostazione per modificarla.</span><span class="sxs-lookup"><span data-stu-id="a9998-169">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="a9998-170">Al termine, fare clic su **Invia**.</span><span class="sxs-lookup"><span data-stu-id="a9998-170">When you're finished, click **Submit**.</span></span>

6. <span data-ttu-id="a9998-171">Fare clic su **fine** nella pagina di conferma che viene visualizzata.</span><span class="sxs-lookup"><span data-stu-id="a9998-171">Click **Done** on the confirmation page that appears.</span></span>

<span data-ttu-id="a9998-172">A questo punto si è pronti per assegnare il tag Quarantine a una funzionalità di quarantena, come descritto nella sezione [passaggio 2](#step-2-assign-a-quarantine-tag-to-supported-features) .</span><span class="sxs-lookup"><span data-stu-id="a9998-172">Now you are ready to assign the quarantine tag to a quarantine feature as described in the [Step 2](#step-2-assign-a-quarantine-tag-to-supported-features) section.</span></span>

### <a name="create-quarantine-tags-in-powershell"></a><span data-ttu-id="a9998-173">Creare tag di quarantena in PowerShell</span><span class="sxs-lookup"><span data-stu-id="a9998-173">Create quarantine tags in PowerShell</span></span>

<span data-ttu-id="a9998-174">Se si preferisce utilizzare PowerShell per creare tag di quarantena, connettersi a PowerShell di Exchange Online o Exchange Online Protection PowerShell e utilizzare il cmdlet **New-QuarantineTag** .</span><span class="sxs-lookup"><span data-stu-id="a9998-174">If you'd rather use PowerShell to create quarantine tags, connect to Exchange Online PowerShell or Exchange Online Protection PowerShell and use the **New-QuarantineTag** cmdlet.</span></span> <span data-ttu-id="a9998-175">Sono disponibili due metodi diversi tra cui scegliere:</span><span class="sxs-lookup"><span data-stu-id="a9998-175">You have two different methods to choose from:</span></span>

- <span data-ttu-id="a9998-176">Utilizzare il parametro _EndUserQuarantinePermissionsValue_ .</span><span class="sxs-lookup"><span data-stu-id="a9998-176">Use the _EndUserQuarantinePermissionsValue_ parameter.</span></span>
- <span data-ttu-id="a9998-177">Utilizzare il parametro _EndUserQuarantinePermissions_ .</span><span class="sxs-lookup"><span data-stu-id="a9998-177">Use the _EndUserQuarantinePermissions_ parameter.</span></span>

<span data-ttu-id="a9998-178">Questi metodi sono descritti nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="a9998-178">These methods are described in the following sections.</span></span>

#### <a name="use-the-enduserquarantinepermissionsvalue-parameter"></a><span data-ttu-id="a9998-179">Utilizzare il parametro EndUserQuarantinePermissionsValue</span><span class="sxs-lookup"><span data-stu-id="a9998-179">Use the EndUserQuarantinePermissionsValue parameter</span></span>

<span data-ttu-id="a9998-180">Per creare un tag di quarantena utilizzando il parametro _EndUserQuarantinePermissionsValue_ , utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="a9998-180">To create a quarantine tag using the _EndUserQuarantinePermissionsValue_ parameter, use the following syntax:</span></span>

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissionsValue <0 to 236>
```

<span data-ttu-id="a9998-181">Il parametro _EndUserQuarantinePermissionsValue_ utilizza un valore decimale convertito da un valore binario.</span><span class="sxs-lookup"><span data-stu-id="a9998-181">The _EndUserQuarantinePermissionsValue_ parameter uses a decimal value that's converted from a binary value.</span></span> <span data-ttu-id="a9998-182">Il valore binario corrisponde alle autorizzazioni di quarantena dell'utente finale disponibili in un ordine specifico.</span><span class="sxs-lookup"><span data-stu-id="a9998-182">The binary value corresponds to the available end-user quarantine permissions in a specific order.</span></span> <span data-ttu-id="a9998-183">Per ogni autorizzazione, il valore 1 è uguale a true e il valore 0 è uguale a false.</span><span class="sxs-lookup"><span data-stu-id="a9998-183">For each permission, the value 1 equals True and the value 0 equals False.</span></span>

<span data-ttu-id="a9998-184">Nella tabella seguente sono descritti l'ordine e i valori richiesti per ogni singola autorizzazione in gruppi di autorizzazioni preimpostati:</span><span class="sxs-lookup"><span data-stu-id="a9998-184">The required order and values for each individual permission in preset permission groups are described in the following table:</span></span>

****

|<span data-ttu-id="a9998-185">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="a9998-185">Permission</span></span>|<span data-ttu-id="a9998-186">Nessun diritto di accesso</span><span class="sxs-lookup"><span data-stu-id="a9998-186">No access</span></span>|<span data-ttu-id="a9998-187">Accesso limitato</span><span class="sxs-lookup"><span data-stu-id="a9998-187">Limited access</span></span>|<span data-ttu-id="a9998-188">Accesso completo</span><span class="sxs-lookup"><span data-stu-id="a9998-188">Full access</span></span>|
|---|:---:|:---:|:---:|
|<span data-ttu-id="a9998-189">PermissionToAllowSender</span><span class="sxs-lookup"><span data-stu-id="a9998-189">PermissionToAllowSender</span></span>|<span data-ttu-id="a9998-190">0</span><span class="sxs-lookup"><span data-stu-id="a9998-190">0</span></span>|<span data-ttu-id="a9998-191">0</span><span class="sxs-lookup"><span data-stu-id="a9998-191">0</span></span>|<span data-ttu-id="a9998-192">1 </span><span class="sxs-lookup"><span data-stu-id="a9998-192">1</span></span>|
|<span data-ttu-id="a9998-193">PermissionToBlockSender</span><span class="sxs-lookup"><span data-stu-id="a9998-193">PermissionToBlockSender</span></span>|<span data-ttu-id="a9998-194">0</span><span class="sxs-lookup"><span data-stu-id="a9998-194">0</span></span>|<span data-ttu-id="a9998-195">1 </span><span class="sxs-lookup"><span data-stu-id="a9998-195">1</span></span>|<span data-ttu-id="a9998-196">1 </span><span class="sxs-lookup"><span data-stu-id="a9998-196">1</span></span>|
|<span data-ttu-id="a9998-197">PermissionToDelete</span><span class="sxs-lookup"><span data-stu-id="a9998-197">PermissionToDelete</span></span>|<span data-ttu-id="a9998-198">0</span><span class="sxs-lookup"><span data-stu-id="a9998-198">0</span></span>|<span data-ttu-id="a9998-199">1 </span><span class="sxs-lookup"><span data-stu-id="a9998-199">1</span></span>|<span data-ttu-id="a9998-200">1 </span><span class="sxs-lookup"><span data-stu-id="a9998-200">1</span></span>|
|<span data-ttu-id="a9998-201">PermissionToDownload<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a9998-201">PermissionToDownload<sup>\*</sup></span></span>|<span data-ttu-id="a9998-202">0</span><span class="sxs-lookup"><span data-stu-id="a9998-202">0</span></span>|<span data-ttu-id="a9998-203">0</span><span class="sxs-lookup"><span data-stu-id="a9998-203">0</span></span>|<span data-ttu-id="a9998-204">0</span><span class="sxs-lookup"><span data-stu-id="a9998-204">0</span></span>|
|<span data-ttu-id="a9998-205">PermissionToPreview</span><span class="sxs-lookup"><span data-stu-id="a9998-205">PermissionToPreview</span></span>|<span data-ttu-id="a9998-206">0</span><span class="sxs-lookup"><span data-stu-id="a9998-206">0</span></span>|<span data-ttu-id="a9998-207">1 </span><span class="sxs-lookup"><span data-stu-id="a9998-207">1</span></span>|<span data-ttu-id="a9998-208">1 </span><span class="sxs-lookup"><span data-stu-id="a9998-208">1</span></span>|
|<span data-ttu-id="a9998-209">PermissionToRelease<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="a9998-209">PermissionToRelease<sup>\*\*</sup></span></span>|<span data-ttu-id="a9998-210">0</span><span class="sxs-lookup"><span data-stu-id="a9998-210">0</span></span>|<span data-ttu-id="a9998-211">0</span><span class="sxs-lookup"><span data-stu-id="a9998-211">0</span></span>|<span data-ttu-id="a9998-212">1 </span><span class="sxs-lookup"><span data-stu-id="a9998-212">1</span></span>|
|<span data-ttu-id="a9998-213">PermissionToRequestRelease<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="a9998-213">PermissionToRequestRelease<sup>\*\*</sup></span></span>|<span data-ttu-id="a9998-214">0</span><span class="sxs-lookup"><span data-stu-id="a9998-214">0</span></span>|<span data-ttu-id="a9998-215">1 </span><span class="sxs-lookup"><span data-stu-id="a9998-215">1</span></span>|<span data-ttu-id="a9998-216">0</span><span class="sxs-lookup"><span data-stu-id="a9998-216">0</span></span>|
|<span data-ttu-id="a9998-217">PermissionToViewHeader<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a9998-217">PermissionToViewHeader<sup>\*</sup></span></span>|<span data-ttu-id="a9998-218">0</span><span class="sxs-lookup"><span data-stu-id="a9998-218">0</span></span>|<span data-ttu-id="a9998-219">0</span><span class="sxs-lookup"><span data-stu-id="a9998-219">0</span></span>|<span data-ttu-id="a9998-220">0</span><span class="sxs-lookup"><span data-stu-id="a9998-220">0</span></span>|
|<span data-ttu-id="a9998-221">Valore binario</span><span class="sxs-lookup"><span data-stu-id="a9998-221">Binary value</span></span>|<span data-ttu-id="a9998-222">00000000</span><span class="sxs-lookup"><span data-stu-id="a9998-222">00000000</span></span>|<span data-ttu-id="a9998-223">01101010</span><span class="sxs-lookup"><span data-stu-id="a9998-223">01101010</span></span>|<span data-ttu-id="a9998-224">11101100</span><span class="sxs-lookup"><span data-stu-id="a9998-224">11101100</span></span>|
|<span data-ttu-id="a9998-225">Valore Decimal da utilizzare</span><span class="sxs-lookup"><span data-stu-id="a9998-225">Decimal value to use</span></span>|<span data-ttu-id="a9998-226">0</span><span class="sxs-lookup"><span data-stu-id="a9998-226">0</span></span>|<span data-ttu-id="a9998-227">106</span><span class="sxs-lookup"><span data-stu-id="a9998-227">106</span></span>|<span data-ttu-id="a9998-228">236</span><span class="sxs-lookup"><span data-stu-id="a9998-228">236</span></span>|

<span data-ttu-id="a9998-229"><sup>\*</sup> Attualmente, questo valore è sempre 0.</span><span class="sxs-lookup"><span data-stu-id="a9998-229"><sup>\*</sup> Currently, this value is always 0.</span></span> <span data-ttu-id="a9998-230">Per PermissionToViewHeader, il valore 0 non nasconde il pulsante **Visualizza intestazione del messaggio** nei dettagli del messaggio in quarantena (il pulsante è sempre disponibile).</span><span class="sxs-lookup"><span data-stu-id="a9998-230">For PermissionToViewHeader, the value 0 doesn't hide the **View message header** button in the details of the quarantined message (the button is always available).</span></span>

<span data-ttu-id="a9998-231"><sup>\*\*</sup> Non impostare entrambi i valori su 1.</span><span class="sxs-lookup"><span data-stu-id="a9998-231"><sup>\*\*</sup> Don't set both of these values to 1.</span></span> <span data-ttu-id="a9998-232">Impostare uno su 1 e l'altro su 0 o impostare entrambi su 0.</span><span class="sxs-lookup"><span data-stu-id="a9998-232">Set one to 1 and the other to 0, or set both to 0.</span></span>

<span data-ttu-id="a9998-233">In questo esempio viene creato un nuovo nome di tag di quarantena NoAccess che assegna le autorizzazioni No Access come descritto nella tabella precedente.</span><span class="sxs-lookup"><span data-stu-id="a9998-233">This example creates a new quarantine tag name NoAccess that assigns the No access permissions as described in the previous table.</span></span>

```powershell
New-QuarantineTag -Name NoAccess -EndUserQuarantinePermissionsValue 0
```

<span data-ttu-id="a9998-234">Per le autorizzazioni di accesso limitate, utilizzare il valore 106.</span><span class="sxs-lookup"><span data-stu-id="a9998-234">For Limited access permissions, use the value 106.</span></span> <span data-ttu-id="a9998-235">Per le autorizzazioni di accesso completo, utilizzare il valore 236.</span><span class="sxs-lookup"><span data-stu-id="a9998-235">For Full access permissions, use the value 236.</span></span>

<span data-ttu-id="a9998-236">Per le autorizzazioni personalizzate, utilizzare la tabella precedente per ottenere il valore binario corrispondente alle autorizzazioni desiderate.</span><span class="sxs-lookup"><span data-stu-id="a9998-236">For custom permissions, use the previous table to get the binary value that corresponds to the permissions you want.</span></span> <span data-ttu-id="a9998-237">Convertire il valore binario in un valore decimale e utilizzare il valore decimale per il parametro _EndUserQuarantinePermissionsValue_ .</span><span class="sxs-lookup"><span data-stu-id="a9998-237">Convert the binary value to a decimal value and use the decimal value for the _EndUserQuarantinePermissionsValue_ parameter.</span></span>

<span data-ttu-id="a9998-238">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [New-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag).</span><span class="sxs-lookup"><span data-stu-id="a9998-238">For detailed syntax and parameter information, see [New-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag).</span></span>

#### <a name="use-the-enduserquarantinepermissions-parameter"></a><span data-ttu-id="a9998-239">Utilizzare il parametro EndUserQuarantinePermissions</span><span class="sxs-lookup"><span data-stu-id="a9998-239">Use the EndUserQuarantinePermissions parameter</span></span>

<span data-ttu-id="a9998-240">Per creare un tag di quarantena utilizzando il parametro _EndUserQuarantinePermissionsValue_ , eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a9998-240">To create a quarantine tag using the _EndUserQuarantinePermissionsValue_ parameter, do the following steps:</span></span>

<span data-ttu-id="a9998-241">R.</span><span class="sxs-lookup"><span data-stu-id="a9998-241">A.</span></span> <span data-ttu-id="a9998-242">Archiviare un oggetto autorizzazioni per la quarantena in una variabile utilizzando il cmdlet **New-QuarantinePermissions** .</span><span class="sxs-lookup"><span data-stu-id="a9998-242">Store a quarantine permissions object in a variable using the **New-QuarantinePermissions** cmdlet.</span></span>

<p>

<span data-ttu-id="a9998-243">B.</span><span class="sxs-lookup"><span data-stu-id="a9998-243">B.</span></span> <span data-ttu-id="a9998-244">Utilizzare la variabile come valore _EndUserQuarantinePermissions_ nel comando **New-QuarantineTag** .</span><span class="sxs-lookup"><span data-stu-id="a9998-244">Use the variable as the _EndUserQuarantinePermissions_ value in the **New-QuarantineTag** command.</span></span>

##### <a name="step-a-store-a-quarantine-permissions-object-in-a-variable"></a><span data-ttu-id="a9998-245">Passaggio A: archiviare un oggetto autorizzazioni per la quarantena in una variabile</span><span class="sxs-lookup"><span data-stu-id="a9998-245">Step A: Store a quarantine permissions object in a variable</span></span>

<span data-ttu-id="a9998-246">Utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="a9998-246">Use the following syntax:</span></span>

```powershell
$<VariableName> = New-QuarantinePermissions [-PermissionToAllowSender <$true | $False>] [-PermissionToBlockSender <$true | $False>] [-PermissionToDelete <$true | $False>] [-PermissionToPreview <$true | $False>] [-PermissionToRelease <$true | $False>] [-PermissionToRequestRelease <$true | $False>]
```

<span data-ttu-id="a9998-247">Il valore predefinito per tutti i parametri inutilizzati è `$false` , quindi è necessario solo utilizzare i parametri in cui si desidera impostare il valore su `$true` .</span><span class="sxs-lookup"><span data-stu-id="a9998-247">The default value for any unused parameters is `$false`, so you only need to use the parameters where you want to set value to `$true`.</span></span>

<span data-ttu-id="a9998-248">Negli esempi seguenti viene illustrato come creare oggetti Permission che corrispondono ai gruppi di autorizzazioni preimpostati:</span><span class="sxs-lookup"><span data-stu-id="a9998-248">The following examples show how to create permission objects that correspond to the preset permissions groups:</span></span>

- <span data-ttu-id="a9998-249">**Nessun accesso**:</span><span class="sxs-lookup"><span data-stu-id="a9998-249">**No access**:</span></span>

  ```powershell
  $NoAccess = New-QuarantinePermissions
  ```

- <span data-ttu-id="a9998-250">**Accesso limitato**:</span><span class="sxs-lookup"><span data-stu-id="a9998-250">**Limited access**:</span></span>

  ```powershell
  $LimitedAccess = New-QuarantinePermissions -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRequestRelease $true
  ```

- <span data-ttu-id="a9998-251">**Accesso completo**:</span><span class="sxs-lookup"><span data-stu-id="a9998-251">**Full access**:</span></span>

  ```powershell
  $FullAccess = New-QuarantinePermissions -PermissionToAllowSender $true -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRelease $true
  ```

<span data-ttu-id="a9998-252">Per visualizzare i valori impostati, eseguire il nome della variabile come comando (ad esempio, eseguire il comando `$NoAccess` ).</span><span class="sxs-lookup"><span data-stu-id="a9998-252">To see the values that you've set, run the variable name as a command (for example, run the command `$NoAccess`).</span></span>

<span data-ttu-id="a9998-253">Per le autorizzazioni personalizzate, non impostare entrambi i parametri _PermissionToRelease_ e _PermissionToRequestRelease_ su `$true` .</span><span class="sxs-lookup"><span data-stu-id="a9998-253">For custom permissions, don't set both the _PermissionToRelease_ and _PermissionToRequestRelease_ parameters to `$true`.</span></span> <span data-ttu-id="a9998-254">Impostare uno su `$true` e lasciare l'altro come `$false` , o lasciare entrambi come `$false` .</span><span class="sxs-lookup"><span data-stu-id="a9998-254">Set one to `$true` and leave the other as `$false`, or leave both as `$false`.</span></span>

<span data-ttu-id="a9998-255">È inoltre possibile modificare una variabile dell'oggetto Permissions esistente dopo aver creato, ma prima di utilizzarla utilizzando il cmdlet **set-QuarantinePermissions** .</span><span class="sxs-lookup"><span data-stu-id="a9998-255">You can also modify an existing permissions object variable after you create but before you use it by using the **Set-QuarantinePermissions** cmdlet.</span></span>

<span data-ttu-id="a9998-256">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [New-QuarantinePermissions](https://docs.microsoft.com/powershell/module/exchange/new-quarantinepermissions) e [set-QuarantinePermissions](https://docs.microsoft.com/powershell/module/exchange/set-quarantinepermissions).</span><span class="sxs-lookup"><span data-stu-id="a9998-256">For detailed syntax and parameter information, see [New-QuarantinePermissions](https://docs.microsoft.com/powershell/module/exchange/new-quarantinepermissions) and [Set-QuarantinePermissions](https://docs.microsoft.com/powershell/module/exchange/set-quarantinepermissions).</span></span>

##### <a name="step-b-use-the-variable-in-the-new-quarantinetag-command"></a><span data-ttu-id="a9998-257">Passaggio B: utilizzare la variabile nel comando New-QuarantineTag</span><span class="sxs-lookup"><span data-stu-id="a9998-257">Step B: Use the variable in the New-QuarantineTag command</span></span>

<span data-ttu-id="a9998-258">Dopo aver creato e archiviato l'oggetto Permissions in una variabile, utilizzare la variabile per il valore del parametro _EndUserQuarantinePermission_ nel comando **New-QuarantineTag** seguente:</span><span class="sxs-lookup"><span data-stu-id="a9998-258">After you've created and stored the permissions object in a variable, use the variable for the _EndUserQuarantinePermission_ parameter value in the following **New-QuarantineTag** command:</span></span>

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissions $<VariableName>
```

<span data-ttu-id="a9998-259">In questo esempio viene creato un nuovo tag di quarantena denominato LimitedAccess utilizzando l' `$LimitedAccess` oggetto Permissions descritto e creato nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="a9998-259">This example creates a new quarantine tag named LimitedAccess using the `$LimitedAccess` permissions object that was described and created in the previous step.</span></span>

```powershell
New-QuarantineTag -Name LimitedAccess -EndUserQuarantinePermissions $LimitedAccess
```

<span data-ttu-id="a9998-260">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [New-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag).</span><span class="sxs-lookup"><span data-stu-id="a9998-260">For detailed syntax and parameter information, see [New-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag).</span></span>

## <a name="step-2-assign-a-quarantine-tag-to-supported-features"></a><span data-ttu-id="a9998-261">Passaggio 2: assegnare un tag di quarantena alle funzionalità supportate</span><span class="sxs-lookup"><span data-stu-id="a9998-261">Step 2: Assign a quarantine tag to supported features</span></span>

<span data-ttu-id="a9998-262">Nelle funzionalità di protezione _supportate_ che consentono di mettere in quarantena i messaggi o i file (azione automatica o configurabile), è possibile assegnare un tag di quarantena alle azioni di quarantena disponibili.</span><span class="sxs-lookup"><span data-stu-id="a9998-262">In _supported_ protection features that quarantine messages or files (automatically or as a configurable action), you can assign a quarantine tag to the available quarantine actions.</span></span> <span data-ttu-id="a9998-263">Nella tabella seguente sono descritte le funzionalità per la quarantena dei messaggi e la disponibilità di tag di quarantena:</span><span class="sxs-lookup"><span data-stu-id="a9998-263">Features that quarantine messages and the availability of quarantine tags are described in the following table:</span></span>

****

|<span data-ttu-id="a9998-264">Funzionalità</span><span class="sxs-lookup"><span data-stu-id="a9998-264">Feature</span></span>|<span data-ttu-id="a9998-265">I tag di quarantena sono supportati?</span><span class="sxs-lookup"><span data-stu-id="a9998-265">Quarantine tags supported?</span></span>|<span data-ttu-id="a9998-266">Tag di quarantena predefiniti utilizzati</span><span class="sxs-lookup"><span data-stu-id="a9998-266">Default quarantine tags used</span></span>|
|---|:---:|---|
|<span data-ttu-id="a9998-267">[Criteri di protezione da posta indesiderata](configure-your-spam-filter-policies.md):</span><span class="sxs-lookup"><span data-stu-id="a9998-267">[Anti-spam policies](configure-your-spam-filter-policies.md):</span></span> <ul><li><span data-ttu-id="a9998-268">**Posta indesiderata** (_SpamAction_)</span><span class="sxs-lookup"><span data-stu-id="a9998-268">**Spam** (_SpamAction_)</span></span></li><li><span data-ttu-id="a9998-269">**Posta indesiderata con elevata sicurezza** (_HighConfidenceSpamAction_)</span><span class="sxs-lookup"><span data-stu-id="a9998-269">**High confidence spam** (_HighConfidenceSpamAction_)</span></span></li><li><span data-ttu-id="a9998-270">**Messaggi di posta elettronica di phishing** (_PhishSpamAction_)</span><span class="sxs-lookup"><span data-stu-id="a9998-270">**Phishing email** (_PhishSpamAction_)</span></span></li><li><span data-ttu-id="a9998-271">**Posta elettronica di phishing con elevata sicurezza** (_HighConfidencePhishAction_)</span><span class="sxs-lookup"><span data-stu-id="a9998-271">**High confidence phishing email** (_HighConfidencePhishAction_)</span></span></li><li><span data-ttu-id="a9998-272">**Messaggi di posta elettronica in blocco** (_BulkSpamAction_)</span><span class="sxs-lookup"><span data-stu-id="a9998-272">**Bulk email** (_BulkSpamAction_)</span></span></li></ul>|<span data-ttu-id="a9998-273">Sì</span><span class="sxs-lookup"><span data-stu-id="a9998-273">Yes</span></span>|<ul><li><span data-ttu-id="a9998-274">DefaultSpamTag (accesso completo)</span><span class="sxs-lookup"><span data-stu-id="a9998-274">DefaultSpamTag (Full access)</span></span></li><li><span data-ttu-id="a9998-275">DefaultHighConfSpamTag (accesso completo)</span><span class="sxs-lookup"><span data-stu-id="a9998-275">DefaultHighConfSpamTag (Full access)</span></span></li><li><span data-ttu-id="a9998-276">DefaultPhishTag (accesso completo)</span><span class="sxs-lookup"><span data-stu-id="a9998-276">DefaultPhishTag (Full access)</span></span></li><li><span data-ttu-id="a9998-277">DefaultHighConfPhishTag (nessun accesso)</span><span class="sxs-lookup"><span data-stu-id="a9998-277">DefaultHighConfPhishTag (No access)</span></span></li><li><span data-ttu-id="a9998-278">DefaultBulkTag (accesso completo)</span><span class="sxs-lookup"><span data-stu-id="a9998-278">DefaultBulkTag (Full access)</span></span></li></ul>
|<span data-ttu-id="a9998-279">Criteri di anti-phishing:</span><span class="sxs-lookup"><span data-stu-id="a9998-279">Anti-phishing policies:</span></span> <ul><li><span data-ttu-id="a9998-280">[Protezione di intelligence spoof](set-up-anti-phishing-policies.md#spoof-settings) (_AuthenticationFailAction_)</span><span class="sxs-lookup"><span data-stu-id="a9998-280">[Spoof intelligence protection](set-up-anti-phishing-policies.md#spoof-settings) (_AuthenticationFailAction_)</span></span></li><li><span data-ttu-id="a9998-281">[Protezione della rappresentazione](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365):<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a9998-281">[Impersonation protection](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365):<sup>\*</sup></span></span> <ul><li><span data-ttu-id="a9998-282">**Se il messaggio di posta elettronica viene inviato da un utente rappresentato** (_TargetedUserProtectionAction_)</span><span class="sxs-lookup"><span data-stu-id="a9998-282">**If email is sent by an impersonated user** (_TargetedUserProtectionAction_)</span></span></li><li><span data-ttu-id="a9998-283">**Se il messaggio di posta elettronica viene inviato da un dominio rappresentato** (_TargetedDomainProtectionAction_)</span><span class="sxs-lookup"><span data-stu-id="a9998-283">**If email is sent by an impersonated domain** (_TargetedDomainProtectionAction_)</span></span></li><li><span data-ttu-id="a9998-284">Intelligence delle cassette **postali** \> **Se il messaggio di posta elettronica viene inviato da un utente rappresentato** (_MailboxIntelligenceProtectionAction_)</span><span class="sxs-lookup"><span data-stu-id="a9998-284">**Mailbox intelligence** \> **If email is sent by an impersonated user** (_MailboxIntelligenceProtectionAction_)</span></span></li></ul></li></ul></ul>|<span data-ttu-id="a9998-285">No</span><span class="sxs-lookup"><span data-stu-id="a9998-285">No</span></span>|<span data-ttu-id="a9998-286">n/d</span><span class="sxs-lookup"><span data-stu-id="a9998-286">n/a</span></span>|
|<span data-ttu-id="a9998-287">[Criteri anti-malware](configure-anti-malware-policies.md): tutti i messaggi rilevati vengono sempre messi in quarantena.</span><span class="sxs-lookup"><span data-stu-id="a9998-287">[Anti-malware policies](configure-anti-malware-policies.md): All detected messages are always quarantined.</span></span>|<span data-ttu-id="a9998-288">No</span><span class="sxs-lookup"><span data-stu-id="a9998-288">No</span></span>|<span data-ttu-id="a9998-289">n/d</span><span class="sxs-lookup"><span data-stu-id="a9998-289">n/a</span></span>|
|[<span data-ttu-id="a9998-290">ATP per SharePoint, OneDrive e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a9998-290">ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>](atp-for-spo-odb-and-teams.md)|<span data-ttu-id="a9998-291">No</span><span class="sxs-lookup"><span data-stu-id="a9998-291">No</span></span>|<span data-ttu-id="a9998-292">n/d</span><span class="sxs-lookup"><span data-stu-id="a9998-292">n/a</span></span>|
|<span data-ttu-id="a9998-293">[Regole del flusso di posta](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (note anche come regole di trasporto) con l'azione: **recapitare il messaggio alla quarantena ospitata** (_Quarantine_).</span><span class="sxs-lookup"><span data-stu-id="a9998-293">[Mail flow rules](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) with the action: **Deliver the message to the hosted quarantine** (_Quarantine_).</span></span>|<span data-ttu-id="a9998-294">No</span><span class="sxs-lookup"><span data-stu-id="a9998-294">No</span></span>|<span data-ttu-id="a9998-295">n/d</span><span class="sxs-lookup"><span data-stu-id="a9998-295">n/a</span></span>|
|

<span data-ttu-id="a9998-296"><sup>\*</sup> Le impostazioni di protezione della rappresentazione sono disponibili solo nei criteri anti-phishing in Microsoft Defender per Office 365.</span><span class="sxs-lookup"><span data-stu-id="a9998-296"><sup>\*</sup> Impersonation protection settings are available only in anti-phishing policies in Microsoft Defender for Office 365.</span></span>

<span data-ttu-id="a9998-297">Se si è soddisfatti delle autorizzazioni dell'utente finale fornite dai tag di quarantena predefiniti, non è necessario eseguire alcuna operazione.</span><span class="sxs-lookup"><span data-stu-id="a9998-297">If you're happy with the end-user permissions that are provided by the default quarantine tags, you don't need to do anything.</span></span> <span data-ttu-id="a9998-298">Se si desidera personalizzare le funzionalità degli utenti finali (pulsanti disponibili) nelle notifiche di posta indesiderata dell'utente finale o nei dettagli dei messaggi in quarantena, è possibile assegnare un tag di quarantena personalizzato.</span><span class="sxs-lookup"><span data-stu-id="a9998-298">If you want to customize the end-user capabilities (available buttons) in end-user spam notifications or in quarantined message details, you can assign a custom quarantine tag.</span></span>

### <a name="assign-quarantine-tags-in-anti-spam-policies-in-the-security--compliance-center"></a><span data-ttu-id="a9998-299">Assegnare i tag di quarantena nei criteri di protezione da posta indesiderata nel centro sicurezza & conformità</span><span class="sxs-lookup"><span data-stu-id="a9998-299">Assign quarantine tags in anti-spam policies in the Security & Compliance Center</span></span>

<span data-ttu-id="a9998-300">Le istruzioni complete per la creazione e la modifica dei criteri di protezione da posta indesiderata sono descritte in [Configure anti-spam Policies in EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="a9998-300">Full instructions for creating and modifying anti-spam policies are described in [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

1. <span data-ttu-id="a9998-301">Nel centro sicurezza & conformità, accedere a criteri di **gestione delle minacce** \>  \> e quindi selezionare **protezione da posta indesiderata**.</span><span class="sxs-lookup"><span data-stu-id="a9998-301">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> and then select **Anti-spam**.</span></span> <span data-ttu-id="a9998-302">In alternativa, aprire <https://protection.office.com/antispam> .</span><span class="sxs-lookup"><span data-stu-id="a9998-302">Or, open <https://protection.office.com/antispam>.</span></span>

2. <span data-ttu-id="a9998-303">Individuare e selezionare un criterio di protezione da posta indesiderata esistente da modificare o creare un nuovo criterio di protezione dalla posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="a9998-303">Find and select an existing anti-spam policy to edit, or create a new anti-spam policy.</span></span>

3. <span data-ttu-id="a9998-304">Nel riquadro a comparsa dettagli criteri espandere la sezione **posta indesiderata e azioni in blocco** .</span><span class="sxs-lookup"><span data-stu-id="a9998-304">In the policy details flyout, expand the **Spam and bulk actions** section.</span></span>

4. <span data-ttu-id="a9998-305">Se è stato selezionato **messaggio in quarantena** per l'azione di un verdetto di filtraggio della posta indesiderata, è disponibile la casella di **tag Applica criterio di quarantena** che consente di selezionare il tag di quarantena per tale verdetto.</span><span class="sxs-lookup"><span data-stu-id="a9998-305">If you've selected **Quarantine message** for the action of an available spam filtering verdict, the **Apply quarantine policy tag** box is available for you to select the quarantine tag for that verdict.</span></span>

   <span data-ttu-id="a9998-306">**Nota**: quando si crea un nuovo criterio, un valore del tag di quarantena vuoto per un verdetto del filtro della posta indesiderata indica che viene utilizzato il tag di quarantena predefinito per il verdetto.</span><span class="sxs-lookup"><span data-stu-id="a9998-306">**Note**: When you create a new policy, a blank quarantine tag value for a spam filtering verdict indicates the default quarantine tag for that verdict is used.</span></span> <span data-ttu-id="a9998-307">Quando si modifica il criterio in un secondo momento, i valori vuoti vengono sostituiti dai nomi dei tag di quarantena predefiniti effettivi come descritto nella tabella precedente.</span><span class="sxs-lookup"><span data-stu-id="a9998-307">When you later edit the policy, the blank values are replaced by the actual default quarantine tag names as described in the previous table.</span></span>

   ![Selezioni dei tag di quarantena in un criterio di protezione da posta indesiderata](../../media/quarantine-tags-in-anti-spam-policies.png)

5. <span data-ttu-id="a9998-309">Al termine, scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="a9998-309">When you're finished, click **Save**.</span></span>

#### <a name="assign-quarantine-tags-in-anti-spam-policies-in-powershell"></a><span data-ttu-id="a9998-310">Assegnare i tag di quarantena nei criteri di protezione da posta indesiderata in PowerShell</span><span class="sxs-lookup"><span data-stu-id="a9998-310">Assign quarantine tags in anti-spam policies in PowerShell</span></span>

<span data-ttu-id="a9998-311">Se si preferisce utilizzare PowerShell per assegnare i tag di quarantena nei criteri di protezione da posta indesiderata, connettersi a PowerShell di Exchange Online o Exchange Online Protection PowerShell e utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="a9998-311">If you'd rather use PowerShell to assign quarantine tags in anti-spam policies, connect to Exchange Online PowerShell or Exchange Online Protection PowerShell and use the following syntax:</span></span>

```powershell
<New-HostedContentFilterPolicy -Name "<Unique name>" | Set-HostedContentFilterPolicy -Identity "<Policy name>">  [-SpamAction Quarantine] [-SpamQuarantineTag <QuarantineTagName>] [-HighConfidenceSpamAction Quarantine] [-HighConfidenceSpamQuarantineTag <QuarantineTagName>] [-PhishSpamAction Quarantine] [-PhishQuarantineTag <QuarantineTagName>] [-HighConfidencePhishQuarantineTag <QuarantineTagName>] [-BulkSpamAction Quarantine] [-BulkQuarantineTag <QuarantineTagName>] ...
```

<span data-ttu-id="a9998-312">**Note**:</span><span class="sxs-lookup"><span data-stu-id="a9998-312">**Notes**:</span></span>

- <span data-ttu-id="a9998-313">Il valore predefinito per il parametro _HighConfidencePhishAction_ è Quarantine, quindi non è necessario impostare l'azione di quarantena per i rilevamenti di phishing ad alta confidenza nei nuovi criteri di protezione da posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="a9998-313">The default value for the _HighConfidencePhishAction_ parameter is Quarantine, so you don't need to set the Quarantine action for high confidence phishing detections in new anti-spam policies.</span></span> <span data-ttu-id="a9998-314">Per tutti gli altri verdetti di filtraggio della posta indesiderata nei criteri di protezione da posta indesiderata nuovi o esistenti, il tag Quarantine è efficace solo se il valore dell'azione è Quarantine.</span><span class="sxs-lookup"><span data-stu-id="a9998-314">For all other spam filtering verdicts in new or existing anti-spam policies, the quarantine tag is only effective if the action value is Quarantine.</span></span> <span data-ttu-id="a9998-315">Per visualizzare i valori di azione nei criteri di protezione da posta indesiderata esistenti, eseguire il seguente comando:</span><span class="sxs-lookup"><span data-stu-id="a9998-315">To see the action values in existing anti-spam policies, run the following command:</span></span>

  ```powershell
  Get-HostedContentFilterPolicy | Format-Table Name,*SpamAction,HighConfidencePhishAction
  ```

  <span data-ttu-id="a9998-316">Per informazioni sui valori di azione predefiniti e sui valori di azione consigliati per standard e Strict, vedere Impostazioni dei criteri di protezione da [posta indesiderata di EOP](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="a9998-316">For information about the default action values and the recommended action values for Standard and Strict, see [EOP anti-spam policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings).</span></span>

- <span data-ttu-id="a9998-317">Un verdetto di filtraggio della posta indesiderata senza un parametro di tag di quarantena corrispondente indica che viene utilizzato il [tag di quarantena predefinito](#step-2-assign-a-quarantine-tag-to-supported-features) .</span><span class="sxs-lookup"><span data-stu-id="a9998-317">A spam filtering verdict without a corresponding quarantine tag parameter means the [default quarantine tag](#step-2-assign-a-quarantine-tag-to-supported-features) for that verdict is used.</span></span>

  <span data-ttu-id="a9998-318">Se si desidera modificare le funzionalità predefinite degli utenti finali nei messaggi in quarantena, è necessario sostituire un tag di quarantena predefinito con un tag di quarantena personalizzato.</span><span class="sxs-lookup"><span data-stu-id="a9998-318">You only need to replace a default quarantine tag with a custom quarantine tag if you want to change the default end-user capabilities on quarantined messages.</span></span>

- <span data-ttu-id="a9998-319">Un nuovo criterio di protezione dalla posta indesiderata in PowerShell richiede un criterio di filtro della posta indesiderata (impostazioni) utilizzando il cmdlet **New-HostedContentFilterPolicy** e una nuova regola di filtro posta indesiderata (filtri destinatario) utilizzando il cmdlet **New-HostedContentFilterRule** .</span><span class="sxs-lookup"><span data-stu-id="a9998-319">A new anti-spam policy in PowerShell requires a spam filter policy (settings) using the **New-HostedContentFilterPolicy** cmdlet and a new spam filter rule (recipient filters) using the **New-HostedContentFilterRule** cmdlet.</span></span> <span data-ttu-id="a9998-320">Per istruzioni, vedere [utilizzare PowerShell per creare criteri di protezione dalla posta indesiderata](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies).</span><span class="sxs-lookup"><span data-stu-id="a9998-320">For instructions, see [Use PowerShell to create anti-spam policies](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies).</span></span>

<span data-ttu-id="a9998-321">In questo esempio viene creato un nuovo criterio di filtro posta indesiderata denominato Research Department con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="a9998-321">This example creates a new spam filter policy named Research Department with the following settings:</span></span>

- <span data-ttu-id="a9998-322">L'azione per tutti i verdetti del filtro della posta indesiderata è impostata su Quarantine.</span><span class="sxs-lookup"><span data-stu-id="a9998-322">The action for all spam filtering verdicts is set to Quarantine.</span></span>
- <span data-ttu-id="a9998-323">Il tag di quarantena personalizzato denominato NoAccess che non assegna autorizzazioni di **accesso** sostituisce tutti i tag di quarantena predefiniti che non assegnano le autorizzazioni di **accesso** per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="a9998-323">The custom quarantine tag named NoAccess that assigns **No access** permissions replaces any default quarantine tags that don't already assign **No access** permissions by default.</span></span>

```powershell
New-HostedContentFilterPolicy -Name Research Department -SpamAction Quarantine -SpamQuarantineTag NoAccess -HighConfidenceSpamAction Quarantine -HighConfidenceSpamQuarantineTag NoAction -PhishSpamAction Quarantine -PhishQuarantineTag NoAction -BulkSpamAction Quarantine -BulkQuarantineTag NoAccess
```

<span data-ttu-id="a9998-324">Per informazioni dettagliate su sintassi e parametri, vedere [New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="a9998-324">For detailed syntax and parameter information, see [New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy).</span></span>

<span data-ttu-id="a9998-325">In questo esempio viene modificato il criterio di filtro posta indesiderata esistente denominato risorse umane.</span><span class="sxs-lookup"><span data-stu-id="a9998-325">This example modifies the existing spam filter policy named Human Resources.</span></span> <span data-ttu-id="a9998-326">L'azione relativa al verdetto per la quarantena della posta indesiderata è impostata su Quarantine e viene assegnato il tag di quarantena personalizzato denominato NoAccess.</span><span class="sxs-lookup"><span data-stu-id="a9998-326">The action for the spam quarantine verdict is set to Quarantine, and the custom quarantine tag named NoAccess is assigned.</span></span>

```powershell
Set-HostedContentFilterPolicy -Identity "Human Resources" -SpamAction Quarantine -SpamQuarantineTag NoAccess
```

<span data-ttu-id="a9998-327">Per informazioni dettagliate su sintassi e parametri, vedere [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="a9998-327">For detailed syntax and parameter information, see [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy).</span></span>

## <a name="configure-global-quarantine-notification-settings-in-the-security--compliance-center"></a><span data-ttu-id="a9998-328">Configurare le impostazioni di notifica per la quarantena globale nel centro sicurezza & conformità</span><span class="sxs-lookup"><span data-stu-id="a9998-328">Configure global quarantine notification settings in the Security & Compliance Center</span></span>

<span data-ttu-id="a9998-329">Le impostazioni globali per i tag Quarantine consentono di personalizzare le notifiche di posta indesiderata dell'utente finale inviate ai destinatari dei messaggi in quarantena.</span><span class="sxs-lookup"><span data-stu-id="a9998-329">The global settings for quarantine tags allow you to customize the end-user spam notifications that are sent to recipients of messages that were quarantined.</span></span> <span data-ttu-id="a9998-330">Per ulteriori informazioni su queste notifiche, vedere [notifiche di posta indesiderata dell'utente finale](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span><span class="sxs-lookup"><span data-stu-id="a9998-330">For more information about these notifications, see [End-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

1. <span data-ttu-id="a9998-331">Nel centro sicurezza & conformità, accedere a criteri di **gestione delle minacce** \>  e quindi selezionare i **tag di quarantena**.</span><span class="sxs-lookup"><span data-stu-id="a9998-331">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

2. <span data-ttu-id="a9998-332">Nella pagina **tag di quarantena** selezionare **Impostazioni globali**.</span><span class="sxs-lookup"><span data-stu-id="a9998-332">On the **Quarantine tags** page, select **Global settings**.</span></span>

3. <span data-ttu-id="a9998-333">Nel riquadro a comparsa **delle impostazioni di notifica per la quarantena** che si apre, configurare alcune o tutte le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a9998-333">In the **Quarantine notification settings** flyout that opens, configure some or all of the following settings:</span></span>

   - <span data-ttu-id="a9998-334">**Utilizzare il logo della società**: selezionare questa opzione per sostituire il logo Microsoft predefinito che viene utilizzato all'inizio delle notifiche di posta indesiderata dell'utente finale.</span><span class="sxs-lookup"><span data-stu-id="a9998-334">**Use my company logo**: Select this option to replace the default Microsoft logo that's use at the top of end-user spam notifications.</span></span> <span data-ttu-id="a9998-335">Prima di eseguire questa operazione, è necessario seguire le istruzioni riportate in [Customize the Microsoft 365 Theme for Your Organization](https://docs.microsoft.com/microsoft-365/admin/setup/customize-your-organization-theme) to upload your Custom logo.</span><span class="sxs-lookup"><span data-stu-id="a9998-335">Before you do this, you need to follow the instructions in [Customize the Microsoft 365 theme for your organization](https://docs.microsoft.com/microsoft-365/admin/setup/customize-your-organization-theme) to upload your custom logo.</span></span>

     <span data-ttu-id="a9998-336">Nella schermata seguente viene mostrato un logo personalizzato in una notifica di posta indesiderata dell'utente finale:</span><span class="sxs-lookup"><span data-stu-id="a9998-336">The following screenshot shows a custom logo in an end-user spam notification:</span></span>

     ![Un logo personalizzato in una notifica di posta indesiderata dell'utente finale](../../media/quarantine-tags-esn-customization-logo.png)

   - <span data-ttu-id="a9998-338">**Scegliere la lingua**: le notifiche di posta indesiderata dell'utente finale sono già localizzate in base alle impostazioni della lingua del destinatario.</span><span class="sxs-lookup"><span data-stu-id="a9998-338">**Choose language**: End-user spam notifications are already localized based on the recipient's language settings.</span></span> <span data-ttu-id="a9998-339">È possibile specificare testo personalizzato in lingue diverse per il **nome visualizzato** e i valori di dichiarazione di non **responsabilità** .</span><span class="sxs-lookup"><span data-stu-id="a9998-339">You can specify customized text in different languages for the **Display name** and **Disclaimer** values.</span></span>

     <span data-ttu-id="a9998-340">Selezionare almeno una lingua nella prima casella della lingua e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="a9998-340">Select at least one language from the first language box and then click **Add**.</span></span> <span data-ttu-id="a9998-341">È possibile selezionare più lingue facendo clic su **Aggiungi** dopo ogni.</span><span class="sxs-lookup"><span data-stu-id="a9998-341">You can select multiple languages by clicking **Add** after each one.</span></span> <span data-ttu-id="a9998-342">Una casella della lingua della sezione Visualizza tutte le lingue selezionate:</span><span class="sxs-lookup"><span data-stu-id="a9998-342">A section language box shows all of the languages that you've selected:</span></span>

     ![Lingue selezionate nella seconda lingua nelle impostazioni di notifica della quarantena globale dei tag di quarantena](../../media/quarantine-tags-esn-customization-selected-languages.png)

   - <span data-ttu-id="a9998-344">**Nome visualizzato**: personalizzare il nome visualizzato del mittente utilizzato nelle notifiche di posta indesiderata dell'utente finale.</span><span class="sxs-lookup"><span data-stu-id="a9998-344">**Display name**: Customize the sender's display name that's used in end-user spam notifications.</span></span>

     <span data-ttu-id="a9998-345">Per ogni lingua aggiunta, selezionare la lingua nella seconda casella di lingua (non fare clic sulla X) e immettere il valore di testo desiderato nella casella **nome visualizzato** .</span><span class="sxs-lookup"><span data-stu-id="a9998-345">For each language that you've added, select the language in the second language box (don't click on the X) and enter the text value you want in the **Display name** box.</span></span>

     <span data-ttu-id="a9998-346">Nella schermata seguente viene mostrato il nome visualizzato personalizzato in una notifica di posta indesiderata dell'utente finale:</span><span class="sxs-lookup"><span data-stu-id="a9998-346">The following screenshot shows the customized display name in an end-user spam notification:</span></span>

     ![Un nome visualizzato del mittente personalizzato in una notifica di posta indesiderata dell'utente finale](../../media/quarantine-tags-esn-customization-display-name.png)

   - <span data-ttu-id="a9998-348">**Dichiarazione** di non responsabilità: aggiungere una dichiarazione di non responsabilità personalizzata alla fine delle notifiche di posta indesiderata dell'utente finale</span><span class="sxs-lookup"><span data-stu-id="a9998-348">**Disclaimer**: Add a custom disclaimer to the bottom of end-user spam notifications.</span></span> <span data-ttu-id="a9998-349">Il testo localizzato, **una dichiarazione di non responsabilità dell'organizzazione:** è sempre incluso per primo, seguito dal testo specificato.</span><span class="sxs-lookup"><span data-stu-id="a9998-349">The localized text, **A disclaimer from your organization:** is always included first, followed by the text you specify.</span></span>

     <span data-ttu-id="a9998-350">Per ogni lingua aggiunta, selezionare la lingua nella seconda casella di lingua (non fare clic sulla X) e immettere il valore del testo desiderato nella casella Dichiarazione di non **responsabilità** .</span><span class="sxs-lookup"><span data-stu-id="a9998-350">For each language that you've added, select the language in the second language box  (don't click the X) and enter the text value you want in the **Disclaimer** box.</span></span>

     <span data-ttu-id="a9998-351">Nella schermata seguente viene visualizzata la dichiarazione di non responsabilità personalizzata in una notifica di posta indesiderata dell'utente finale:</span><span class="sxs-lookup"><span data-stu-id="a9998-351">The following screenshot shows the customized disclaimer in an end-user spam notification:</span></span>

     ![Una dichiarazione di non responsabilità personalizzata nella parte inferiore di una notifica di posta indesiderata dell'utente finale](../../media/quarantine-tags-esn-customization-disclaimer.png)

## <a name="view-quarantine-tags-in-the-security--compliance-center"></a><span data-ttu-id="a9998-353">Visualizzare i tag per la quarantena nel centro sicurezza & Compliance</span><span class="sxs-lookup"><span data-stu-id="a9998-353">View quarantine tags in the Security & Compliance Center</span></span>

1. <span data-ttu-id="a9998-354">Nel centro sicurezza & conformità, accedere a criteri di **gestione delle minacce** \>  e quindi selezionare i **tag di quarantena**.</span><span class="sxs-lookup"><span data-stu-id="a9998-354">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

- <span data-ttu-id="a9998-355">Per visualizzare le impostazioni dei tag di quarantena incorporati o personalizzati, selezionare il tag Quarantine nell'elenco (non selezionare la casella di controllo).</span><span class="sxs-lookup"><span data-stu-id="a9998-355">To view the settings of built-in or custom quarantine tags, select the quarantine tag from the list (don't select the check box).</span></span>

- <span data-ttu-id="a9998-356">Per visualizzare le impostazioni globali, selezionare **Impostazioni globali**</span><span class="sxs-lookup"><span data-stu-id="a9998-356">To view the global settings, select **Global settings**</span></span>

### <a name="view-quarantine-tags-in-powershell"></a><span data-ttu-id="a9998-357">Visualizzare i tag di quarantena in PowerShell</span><span class="sxs-lookup"><span data-stu-id="a9998-357">View quarantine tags in PowerShell</span></span>

<span data-ttu-id="a9998-358">Se si preferisce utilizzare PowerShell per visualizzare i tag di quarantena, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a9998-358">If you'd rather use PowerShell to view quarantine tags, do any of the following steps:</span></span>

- <span data-ttu-id="a9998-359">Per visualizzare un elenco riepilogativo di tutti i tag incorporati o personalizzati, eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="a9998-359">To view a summary list of all built-in or custom tags, run the following command:</span></span>

  ```powershell
  Get-QuarantineTag | Format-Table Name
  ```

- <span data-ttu-id="a9998-360">Per visualizzare le impostazioni dei tag di quarantena incorporati o personalizzati, sostituire \<TagName\> con il nome del tag Quarantine ed eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="a9998-360">To view the settings of built-in or custom quarantine tags, replace \<TagName\> with the name of the quarantine tag, and run the following command:</span></span>

  ```powershell
  Get-QuarantineTag -Identity "<TagName>"
  ```

- <span data-ttu-id="a9998-361">Per visualizzare le impostazioni globali, eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="a9998-361">To view the global settings, run the following command:</span></span>

  ```powershell
  Get-QuarantineTag -QuarantineTagType GlobalQuarantineTag
  ```

<span data-ttu-id="a9998-362">Per informazioni dettagliate su sintassi e parametri, vedere [Get-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="a9998-362">For detailed syntax and parameter information, see [Get-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterpolicy).</span></span>

## <a name="remove-quarantine-tags-in-the-security--compliance-center"></a><span data-ttu-id="a9998-363">Rimuovere i tag di quarantena nel centro sicurezza & conformità</span><span class="sxs-lookup"><span data-stu-id="a9998-363">Remove quarantine tags in the Security & Compliance Center</span></span>

<span data-ttu-id="a9998-364">**Note**:</span><span class="sxs-lookup"><span data-stu-id="a9998-364">**Notes**:</span></span>

- <span data-ttu-id="a9998-365">Non è possibile rimuovere i tag di quarantena incorporati.</span><span class="sxs-lookup"><span data-stu-id="a9998-365">You can't remove built-in quarantine tags.</span></span>

- <span data-ttu-id="a9998-366">Prima di rimuovere un tag di quarantena personalizzato, verificare che non sia in uso.</span><span class="sxs-lookup"><span data-stu-id="a9998-366">Before you remove a custom quarantine tag, verify that it's not being used.</span></span> <span data-ttu-id="a9998-367">Ad esempio, eseguire il comando seguente in PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a9998-367">For example, run the following command in PowerShell:</span></span>

  ```powershell
  Get-HostedContentFilterPolicy | Format-List Name,*QuarantineTag
  ```

  <span data-ttu-id="a9998-368">Se viene utilizzato il tag Quarantine, [sostituire il tag di quarantena assegnato prima di](#step-2-assign-a-quarantine-tag-to-supported-features) rimuoverlo.</span><span class="sxs-lookup"><span data-stu-id="a9998-368">If the quarantine tag is being used, [replace the assigned quarantine tag](#step-2-assign-a-quarantine-tag-to-supported-features) before you remove it.</span></span>

1. <span data-ttu-id="a9998-369">Nel centro sicurezza & conformità, accedere a criteri di **gestione delle minacce** \>  e quindi selezionare i **tag di quarantena**.</span><span class="sxs-lookup"><span data-stu-id="a9998-369">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

2. <span data-ttu-id="a9998-370">Nella pagina dei **tag di quarantena** selezionare il tag di quarantena personalizzato che si desidera rimuovere e il tag fare clic su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="a9998-370">On the **Quarantine tags** page, select the custom quarantine tag that you want to remove, and the click **Delete tag**.</span></span>

3. <span data-ttu-id="a9998-371">Fare clic su **Rimuovi tag** nella finestra di dialogo di conferma che viene visualizzata.</span><span class="sxs-lookup"><span data-stu-id="a9998-371">Click **Remove tag** in the confirmation dialog that appears.</span></span>

### <a name="remove-quarantine-tags-in-powershell"></a><span data-ttu-id="a9998-372">Rimuovere i tag di quarantena in PowerShell</span><span class="sxs-lookup"><span data-stu-id="a9998-372">Remove quarantine tags in PowerShell</span></span>

<span data-ttu-id="a9998-373">Se si preferisce utilizzare PowerShell per rimuovere un tag di quarantena personalizzato, sostituire \<TagName\> con il nome del tag Quarantine ed eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="a9998-373">If you'd rather use PowerShell to remove a custom quarantine tag, replace \<TagName\> with the name of the quarantine tag, and run the following command:</span></span>

```powershell
Remove-QuarantineTag -Identity "<TagName>"
```

<span data-ttu-id="a9998-374">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Remove-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/remove-quarantinetag).</span><span class="sxs-lookup"><span data-stu-id="a9998-374">For detailed syntax and parameter information, see [Remove-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/remove-quarantinetag).</span></span>

## <a name="quarantine-tag-permission-details"></a><span data-ttu-id="a9998-375">Dettagli sull'autorizzazione dei tag per la quarantena</span><span class="sxs-lookup"><span data-stu-id="a9998-375">Quarantine tag permission details</span></span>

<span data-ttu-id="a9998-376">Nelle sezioni seguenti vengono descritti gli effetti dei gruppi di autorizzazioni preimpostati e delle autorizzazioni individuali nei dettagli dei messaggi in quarantena e nelle notifiche di posta indesiderata dell'utente finale.</span><span class="sxs-lookup"><span data-stu-id="a9998-376">The following sections describe the effects of preset permission groups and individual permissions in the details of quarantined messages and in end-user spam notifications.</span></span>

### <a name="preset-permissions-groups"></a><span data-ttu-id="a9998-377">Gruppi di autorizzazioni preimpostati</span><span class="sxs-lookup"><span data-stu-id="a9998-377">Preset permissions groups</span></span>

<span data-ttu-id="a9998-378">Nella tabella all'inizio di questo articolo vengono elencate le singole autorizzazioni incluse nei gruppi di autorizzazioni preimpostati.</span><span class="sxs-lookup"><span data-stu-id="a9998-378">The individual permissions that are included in preset permission groups are listed in the table at the beginning of this article.</span></span>

#### <a name="no-access"></a><span data-ttu-id="a9998-379">Nessun diritto di accesso</span><span class="sxs-lookup"><span data-stu-id="a9998-379">No access</span></span>

<span data-ttu-id="a9998-380">Se il tag Quarantine assegna le autorizzazioni di **accesso no** (nessuna autorizzazione), gli utenti possono ancora ottenere alcune funzionalità di base:</span><span class="sxs-lookup"><span data-stu-id="a9998-380">If the quarantine tag assigns the **No access** permissions (no permissions), users still get some baseline capabilities:</span></span>

- <span data-ttu-id="a9998-381">**Dettagli del messaggio in quarantena**: il pulsante **Visualizza intestazione del messaggio** è sempre disponibile.</span><span class="sxs-lookup"><span data-stu-id="a9998-381">**Quarantined message details**: The **View message header** button is always available.</span></span>

  ![Pulsanti disponibili nei dettagli del messaggio in quarantena se il tag Quarantine fornisce all'utente nessuna autorizzazione di accesso](../../media/quarantine-tags-quarantined-message-details-no-access.png)

- <span data-ttu-id="a9998-383">**Notifiche di posta indesiderata dell'utente finale**: il pulsante **Revisione** che porta l'utente al messaggio in quarantena è sempre disponibile.</span><span class="sxs-lookup"><span data-stu-id="a9998-383">**End-user spam notifications**: The **Review** button that takes the user to the message in quarantine is always available.</span></span>

  ![Pulsanti disponibili nella notifica di posta indesiderata dell'utente finale se il tag Quarantine fornisce all'utente nessuna autorizzazione di accesso](../../media/quarantine-tags-esn-no-access.png)

#### <a name="limited-access"></a><span data-ttu-id="a9998-385">Accesso limitato</span><span class="sxs-lookup"><span data-stu-id="a9998-385">Limited access</span></span>

<span data-ttu-id="a9998-386">Se il tag Quarantine assegna le autorizzazioni di **accesso limitate** , gli utenti riceveranno le seguenti funzionalità:</span><span class="sxs-lookup"><span data-stu-id="a9998-386">If the quarantine tag assigns the **Limited access** permissions, users get the following capabilities:</span></span>

- <span data-ttu-id="a9998-387">**Dettagli del messaggio in quarantena**: sono disponibili i seguenti pulsanti:</span><span class="sxs-lookup"><span data-stu-id="a9998-387">**Quarantined message details**: The following buttons are available:</span></span>
  - <span data-ttu-id="a9998-388">**Rilascio delle richieste**</span><span class="sxs-lookup"><span data-stu-id="a9998-388">**Request release**</span></span>
  - <span data-ttu-id="a9998-389">**Visualizzazione delle intestazioni del messaggio**</span><span class="sxs-lookup"><span data-stu-id="a9998-389">**View message header**</span></span>
  - <span data-ttu-id="a9998-390">**Messaggio di anteprima**</span><span class="sxs-lookup"><span data-stu-id="a9998-390">**Preview message**</span></span>
  - <span data-ttu-id="a9998-391">**Blocca mittente**</span><span class="sxs-lookup"><span data-stu-id="a9998-391">**Block sender**</span></span>
  - <span data-ttu-id="a9998-392">**Rimuovi dalla quarantena**</span><span class="sxs-lookup"><span data-stu-id="a9998-392">**Remove from quarantine**</span></span>

  ![Pulsanti disponibili nei dettagli del messaggio in quarantena se il tag Quarantine fornisce le autorizzazioni di accesso limitate all'utente](../../media/quarantine-tags-quarantined-message-details-limited-access.png)

- <span data-ttu-id="a9998-394">**Notifiche di posta indesiderata dell'utente finale**: sono disponibili i seguenti pulsanti:</span><span class="sxs-lookup"><span data-stu-id="a9998-394">**End-user spam notifications**: The following buttons are available:</span></span>
  - <span data-ttu-id="a9998-395">**Blocca mittente**</span><span class="sxs-lookup"><span data-stu-id="a9998-395">**Block sender**</span></span>
  - <span data-ttu-id="a9998-396">**Verifica**</span><span class="sxs-lookup"><span data-stu-id="a9998-396">**Review**</span></span>

  ![Pulsanti disponibili nella notifica di posta indesiderata dell'utente finale se il tag Quarantine fornisce le autorizzazioni di accesso limitate all'utente](../../media/quarantine-tags-esn-limited-access.png)

#### <a name="full-access"></a><span data-ttu-id="a9998-398">Accesso completo</span><span class="sxs-lookup"><span data-stu-id="a9998-398">Full access</span></span>

<span data-ttu-id="a9998-399">Se il tag Quarantine assegna le autorizzazioni di **accesso completo** (tutte le autorizzazioni disponibili), gli utenti ottengono le seguenti funzionalità:</span><span class="sxs-lookup"><span data-stu-id="a9998-399">If the quarantine tag assigns the **Full access** permissions (all available permissions), users get the following capabilities:</span></span>

- <span data-ttu-id="a9998-400">**Dettagli del messaggio in quarantena**: sono disponibili i seguenti pulsanti:</span><span class="sxs-lookup"><span data-stu-id="a9998-400">**Quarantined message details**: The following buttons are available:</span></span>
  - <span data-ttu-id="a9998-401">**Rilascia il messaggio**</span><span class="sxs-lookup"><span data-stu-id="a9998-401">**Release message**</span></span>
  - <span data-ttu-id="a9998-402">**Visualizzazione delle intestazioni del messaggio**</span><span class="sxs-lookup"><span data-stu-id="a9998-402">**View message header**</span></span>
  - <span data-ttu-id="a9998-403">**Messaggio di anteprima**</span><span class="sxs-lookup"><span data-stu-id="a9998-403">**Preview message**</span></span>
  - <span data-ttu-id="a9998-404">**Blocca mittente**</span><span class="sxs-lookup"><span data-stu-id="a9998-404">**Block sender**</span></span>
  - <span data-ttu-id="a9998-405">**Consenti mittente**</span><span class="sxs-lookup"><span data-stu-id="a9998-405">**Allow sender**</span></span>
  - <span data-ttu-id="a9998-406">**Rimuovi dalla quarantena**</span><span class="sxs-lookup"><span data-stu-id="a9998-406">**Remove from quarantine**</span></span>

  ![Pulsanti disponibili nei dettagli del messaggio in quarantena se il tag Quarantine fornisce all'utente le autorizzazioni di accesso completo](../../media/quarantine-tags-quarantined-message-details-full-access.png)

- <span data-ttu-id="a9998-408">**Notifiche di posta indesiderata dell'utente finale**: sono disponibili i seguenti pulsanti:</span><span class="sxs-lookup"><span data-stu-id="a9998-408">**End-user spam notifications**: The following buttons are available:</span></span>
  - <span data-ttu-id="a9998-409">**Blocca mittente**</span><span class="sxs-lookup"><span data-stu-id="a9998-409">**Block sender**</span></span>
  - <span data-ttu-id="a9998-410">**Rilascio**</span><span class="sxs-lookup"><span data-stu-id="a9998-410">**Release**</span></span>
  - <span data-ttu-id="a9998-411">**Verifica**</span><span class="sxs-lookup"><span data-stu-id="a9998-411">**Review**</span></span>

  ![Pulsanti disponibili nella notifica di posta indesiderata dell'utente finale se il tag Quarantine fornisce le autorizzazioni di accesso completo dell'utente](../../media/quarantine-tags-esn-full-access.png)

### <a name="individual-permissions"></a><span data-ttu-id="a9998-413">Autorizzazioni individuali</span><span class="sxs-lookup"><span data-stu-id="a9998-413">Individual permissions</span></span>

> [!NOTE]
> <span data-ttu-id="a9998-414">Tenere presente che gli utenti ottengono sempre i pulsanti descritti nella sezione [No Access](#no-access) .</span><span class="sxs-lookup"><span data-stu-id="a9998-414">Remember, users always get the buttons described in the [No access](#no-access) section.</span></span> <span data-ttu-id="a9998-415">Questi pulsanti non sono inclusi nelle singole descrizioni delle autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="a9998-415">These buttons are not included in the individual permission descriptions.</span></span>

#### <a name="allow-sender-permission"></a><span data-ttu-id="a9998-416">Consenti autorizzazione mittente</span><span class="sxs-lookup"><span data-stu-id="a9998-416">Allow sender permission</span></span>

<span data-ttu-id="a9998-417">L'autorizzazione **Consenti mittente** (_PermissionToAllowSender_) consente di controllare l'accesso al pulsante per consentire agli utenti di aggiungere comodamente il mittente del messaggio in quarantena all'elenco dei mittenti attendibili.</span><span class="sxs-lookup"><span data-stu-id="a9998-417">The **Allow sender** permission (_PermissionToAllowSender_) controls access to the button that allows users to conveniently add the quarantined message sender to their Safe Senders list.</span></span>

- <span data-ttu-id="a9998-418">**Dettagli del messaggio in quarantena**:</span><span class="sxs-lookup"><span data-stu-id="a9998-418">**Quarantined message details**:</span></span>
  - <span data-ttu-id="a9998-419">**Consenti autorizzazione mittente** attivata: il pulsante **Consenti mittente** è disponibile.</span><span class="sxs-lookup"><span data-stu-id="a9998-419">**Allow sender** permission enabled: The **Allow sender** button is available.</span></span>
  - <span data-ttu-id="a9998-420">**Consenti autorizzazioni mittente** disabilitate: il pulsante **Consenti mittente** non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="a9998-420">**Allow sender** permission disabled: The **Allow sender** button is not available.</span></span>

- <span data-ttu-id="a9998-421">**Notifiche di posta indesiderata dell'utente finale**: nessun effetto.</span><span class="sxs-lookup"><span data-stu-id="a9998-421">**End-user spam notifications**: No effect.</span></span>

<span data-ttu-id="a9998-422">Per ulteriori informazioni sull'elenco dei mittenti attendibili, vedere [Impedisci](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379666) l'esecuzione del blocco dei mittenti trusted e [utilizzo di PowerShell di Exchange Online per configurare la raccolta degli elenchi indirizzi attendibili in una cassetta postale](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span><span class="sxs-lookup"><span data-stu-id="a9998-422">For more information about the Safe Senders list, see [Prevent trusted senders from being blocked](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379666) and [Use Exchange Online PowerShell to configure the safelist collection on a mailbox](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span></span>

#### <a name="block-sender-permission"></a><span data-ttu-id="a9998-423">Autorizzazione Blocca mittente</span><span class="sxs-lookup"><span data-stu-id="a9998-423">Block sender permission</span></span>

<span data-ttu-id="a9998-424">L'autorizzazione **Blocca mittente** (_PermissionToBlockSender_) consente di controllare l'accesso al pulsante per consentire agli utenti di aggiungere comodamente il mittente del messaggio in quarantena all'elenco dei mittenti bloccati.</span><span class="sxs-lookup"><span data-stu-id="a9998-424">The **Block sender** permission (_PermissionToBlockSender_) controls access to the button that allows users to conveniently add the quarantined message sender to their Blocked Senders list.</span></span>

- <span data-ttu-id="a9998-425">**Dettagli del messaggio in quarantena**:</span><span class="sxs-lookup"><span data-stu-id="a9998-425">**Quarantined message details**:</span></span>
  - <span data-ttu-id="a9998-426">**Blocca autorizzazione mittente** attivata: il pulsante **Blocca mittente** è disponibile.</span><span class="sxs-lookup"><span data-stu-id="a9998-426">**Block sender** permission enabled: The **Block sender** button is available.</span></span>
  - <span data-ttu-id="a9998-427">**Blocca autorizzazioni mittente** disabilitate: il pulsante **Blocca mittente** non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="a9998-427">**Block sender** permission disabled: The **Block sender** button is not available.</span></span>

- <span data-ttu-id="a9998-428">**Notifiche di posta indesiderata dell'utente finale**:</span><span class="sxs-lookup"><span data-stu-id="a9998-428">**End-user spam notifications**:</span></span>
  - <span data-ttu-id="a9998-429">**Blocca autorizzazioni mittente** disabilitate: il pulsante **Blocca mittente** non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="a9998-429">**Block sender** permission disabled: The **Block sender** button is not available.</span></span>
  - <span data-ttu-id="a9998-430">**Blocca autorizzazione mittente** attivata: il pulsante **Blocca mittente** è disponibile.</span><span class="sxs-lookup"><span data-stu-id="a9998-430">**Block sender** permission enabled: The **Block sender** button is available.</span></span>

<span data-ttu-id="a9998-431">Per ulteriori informazioni sull'elenco dei mittenti bloccati, vedere [blocco dei messaggi da](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667) parte di [un utente e utilizzo di PowerShell di Exchange Online per configurare la raccolta degli elenchi indirizzi attendibili in una cassetta postale](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span><span class="sxs-lookup"><span data-stu-id="a9998-431">For more information about the Blocked Senders list, see [Block messages from someone](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667) and [Use Exchange Online PowerShell to configure the safelist collection on a mailbox](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span></span>

#### <a name="delete-permission"></a><span data-ttu-id="a9998-432">Autorizzazione di eliminazione</span><span class="sxs-lookup"><span data-stu-id="a9998-432">Delete permission</span></span>

<span data-ttu-id="a9998-433">L'autorizzazione di **eliminazione** (_PermissionToDelete_) consente di controllare la possibilità per gli utenti di eliminare i propri messaggi (messaggi in cui l'utente è destinatario) dalla quarantena.</span><span class="sxs-lookup"><span data-stu-id="a9998-433">The **Delete** permission (_PermissionToDelete_) controls the ability to of users to delete their messages (messages where the user is a recipient) from quarantine.</span></span>

- <span data-ttu-id="a9998-434">**Dettagli del messaggio in quarantena**:</span><span class="sxs-lookup"><span data-stu-id="a9998-434">**Quarantined message details**:</span></span>
  - <span data-ttu-id="a9998-435">Autorizzazioni di **eliminazione** abilitate: il pulsante **Rimuovi da Quarantine** è disponibile.</span><span class="sxs-lookup"><span data-stu-id="a9998-435">**Delete** permission enabled: The **Remove from quarantine** button is available.</span></span>
  - <span data-ttu-id="a9998-436">Autorizzazioni di **eliminazione** disabilitate: il pulsante **Rimuovi dalla quarantena** non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="a9998-436">**Delete** permission disabled: The **Remove from quarantine** button is not available.</span></span>

- <span data-ttu-id="a9998-437">**Notifiche di posta indesiderata dell'utente finale**: nessun effetto.</span><span class="sxs-lookup"><span data-stu-id="a9998-437">**End-user spam notifications**: No effect.</span></span>

#### <a name="preview-permission"></a><span data-ttu-id="a9998-438">Autorizzazione anteprima</span><span class="sxs-lookup"><span data-stu-id="a9998-438">Preview permission</span></span>

<span data-ttu-id="a9998-439">L'autorizzazione **Preview** (_PermissionToPreview_) consente di controllare la possibilità per gli utenti di visualizzare in anteprima i propri messaggi in quarantena.</span><span class="sxs-lookup"><span data-stu-id="a9998-439">The **Preview** permission (_PermissionToPreview_) controls the ability to of users to preview their messages in quarantine.</span></span>

- <span data-ttu-id="a9998-440">**Dettagli del messaggio in quarantena**:</span><span class="sxs-lookup"><span data-stu-id="a9998-440">**Quarantined message details**:</span></span>
  - <span data-ttu-id="a9998-441">Autorizzazioni di **Anteprima** abilitate: il pulsante **Anteprima messaggio** è disponibile.</span><span class="sxs-lookup"><span data-stu-id="a9998-441">**Preview** permission enabled: The **Preview message** button is available.</span></span>
  - <span data-ttu-id="a9998-442">Autorizzazioni di **Anteprima** disabilitate: il pulsante **Anteprima messaggio** non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="a9998-442">**Preview** permission disabled: The **Preview message** button is not available.</span></span>

- <span data-ttu-id="a9998-443">**Notifiche di posta indesiderata dell'utente finale**: nessun effetto.</span><span class="sxs-lookup"><span data-stu-id="a9998-443">**End-user spam notifications**: No effect.</span></span>

#### <a name="allow-recipients-to-release-a-message-from-quarantine-permission"></a><span data-ttu-id="a9998-444">Consenti ai destinatari di rilasciare un messaggio dall'autorizzazione per la quarantena</span><span class="sxs-lookup"><span data-stu-id="a9998-444">Allow recipients to release a message from quarantine permission</span></span>

<span data-ttu-id="a9998-445">L'autorizzazione **Consenti ai destinatari di rilasciare un messaggio dalla quarantena** (_PermissionToRelease_) consente di controllare la possibilità per gli utenti di rilasciare i messaggi in quarantena direttamente e senza l'approvazione di un amministratore.</span><span class="sxs-lookup"><span data-stu-id="a9998-445">The **Allow recipients to release a message from quarantine** permission (_PermissionToRelease_) controls the ability of users to release their quarantined messages directly and without the approval of an admin.</span></span>

- <span data-ttu-id="a9998-446">**Dettagli del messaggio in quarantena**:</span><span class="sxs-lookup"><span data-stu-id="a9998-446">**Quarantined message details**:</span></span>
  - <span data-ttu-id="a9998-447">Autorizzazione abilitata: il pulsante **rilascia messaggio** è disponibile.</span><span class="sxs-lookup"><span data-stu-id="a9998-447">Permission enabled: The **Release message** button is available.</span></span>
  - <span data-ttu-id="a9998-448">Autorizzazioni disabilitate: il pulsante **rilascia messaggio** non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="a9998-448">Permission disabled: The **Release message** button is not available.</span></span>

- <span data-ttu-id="a9998-449">**Notifiche di posta indesiderata dell'utente finale**:</span><span class="sxs-lookup"><span data-stu-id="a9998-449">**End-user spam notifications**:</span></span>
  - <span data-ttu-id="a9998-450">Autorizzazione abilitata: il pulsante **rilascia** è disponibile.</span><span class="sxs-lookup"><span data-stu-id="a9998-450">Permission enabled: The **Release** button is available.</span></span>
  - <span data-ttu-id="a9998-451">Autorizzazioni disabilitate: il pulsante **rilascia** non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="a9998-451">Permission disabled: The **Release** button is not available.</span></span>

#### <a name="allow-recipients-to-request-a-message-to-be-released-from-quarantine-permission"></a><span data-ttu-id="a9998-452">Consenti ai destinatari di richiedere il rilascio di un messaggio dall'autorizzazione per la quarantena</span><span class="sxs-lookup"><span data-stu-id="a9998-452">Allow recipients to request a message to be released from quarantine permission</span></span>

<span data-ttu-id="a9998-453">L'opzione **Consenti ai destinatari di richiedere un messaggio da rilasciare dall'autorizzazione di quarantena** (_PermissionToRequestRelease_) controlla la possibilità per gli utenti di _richiedere_ il rilascio dei messaggi in quarantena.</span><span class="sxs-lookup"><span data-stu-id="a9998-453">The **Allow recipients to request a message to be released from quarantine** permission (_PermissionToRequestRelease_) controls the ability of users to _request_ the release of their quarantined messages.</span></span> <span data-ttu-id="a9998-454">Il messaggio viene rilasciato solo dopo che un amministratore approva la richiesta.</span><span class="sxs-lookup"><span data-stu-id="a9998-454">The message is only released after an admin approves the request.</span></span>

- <span data-ttu-id="a9998-455">**Dettagli del messaggio in quarantena**:</span><span class="sxs-lookup"><span data-stu-id="a9998-455">**Quarantined message details**:</span></span>
  - <span data-ttu-id="a9998-456">Autorizzazione abilitata: il pulsante **rilascia richiesta** è disponibile.</span><span class="sxs-lookup"><span data-stu-id="a9998-456">Permission enabled: The **Request release** button is available.</span></span>
  - <span data-ttu-id="a9998-457">Autorizzazioni disabilitate: il pulsante **rilascia richiesta** non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="a9998-457">Permission disabled: The **Request release** button is not available.</span></span>

- <span data-ttu-id="a9998-458">**Notifiche di posta indesiderata dell'utente finale**: il pulsante **rilascia** non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="a9998-458">**End-user spam notifications**: The **Release** button is not available.</span></span>
