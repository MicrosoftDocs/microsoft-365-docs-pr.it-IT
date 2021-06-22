---
title: Criteri di quarantena
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
description: Gli amministratori possono imparare a usare i criteri di quarantena per controllare le attività che gli utenti possono eseguire sui messaggi in quarantena.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 96dc1e2158787457884ca6a3c6f27bf76e83a369
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/22/2021
ms.locfileid: "53055183"
---
# <a name="quarantine-policies"></a><span data-ttu-id="c31c1-103">Criteri di quarantena</span><span class="sxs-lookup"><span data-stu-id="c31c1-103">Quarantine policies</span></span>

> [!NOTE]
> <span data-ttu-id="c31c1-104">Le funzionalità descritte in questo articolo sono attualmente disponibili in Anteprima, non sono disponibili per tutti e sono soggette a modifiche.</span><span class="sxs-lookup"><span data-stu-id="c31c1-104">The features that are described in this article are currently in Preview, aren't available to everyone, and are subject to change.</span></span>

<span data-ttu-id="c31c1-105">I criteri di quarantena (in precedenza noti come tag di quarantena) in Exchange Online Protection (EOP) consentono agli amministratori di controllare le attività che gli utenti possono eseguire sui messaggi in quarantena in base al modo in cui il messaggio è arrivato in quarantena.</span><span class="sxs-lookup"><span data-stu-id="c31c1-105">Quarantine policies (formerly known as quarantine tags) in Exchange Online Protection (EOP) allow admins to control what users are able to do to their quarantined messages based on how the message arrived in quarantine.</span></span>

<span data-ttu-id="c31c1-106">EOP ha tradizionalmente consentito o impedito determinati livelli di interattività per i messaggi in [quarantena](find-and-release-quarantined-messages-as-a-user.md) e nelle [notifiche di posta indesiderata dell'utente finale.](use-spam-notifications-to-release-and-report-quarantined-messages.md)</span><span class="sxs-lookup"><span data-stu-id="c31c1-106">EOP has traditionally allowed or prevented certain levels of interactivity for messages in [quarantine](find-and-release-quarantined-messages-as-a-user.md) and in [end-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span> <span data-ttu-id="c31c1-107">Ad esempio, gli utenti possono visualizzare e rilasciare i messaggi messi in quarantena dal filtro di protezione da posta indesiderata come posta indesiderata o in blocco, ma non possono visualizzare o rilasciare i messaggi messi in quarantena come phishing ad alta probabilità (solo gli amministratori possono farlo).</span><span class="sxs-lookup"><span data-stu-id="c31c1-107">For example, users can view and release messages that were quarantined by anti-spam filtering as spam or bulk, but they can't view or release messages that were quarantined as high confidence phishing (only admins can do that).</span></span>

<span data-ttu-id="c31c1-108">Per [le funzionalità](#step-2-assign-a-quarantine-policy-to-supported-features)di protezione supportate, i criteri di quarantena specificano le attività consentite agli utenti nei messaggi di notifica di posta indesiderata dell'utente finale e nei messaggi in quarantena (messaggi in cui l'utente è un destinatario).</span><span class="sxs-lookup"><span data-stu-id="c31c1-108">For [supported protection features](#step-2-assign-a-quarantine-policy-to-supported-features), quarantine policies specify what users are allowed to do in end-user spam notification messages and in their quarantined messages in quarantine (messages where the user is a recipient).</span></span> <span data-ttu-id="c31c1-109">I criteri di quarantena predefiniti vengono assegnati automaticamente per applicare le funzionalità cronologiche agli utenti nei messaggi in quarantena.</span><span class="sxs-lookup"><span data-stu-id="c31c1-109">Default quarantine policies are automatically assigned to enforce the historical capabilities for users on quarantined messages.</span></span> <span data-ttu-id="c31c1-110">In caso contrario, è possibile creare e assegnare criteri di quarantena personalizzati per consentire o impedire agli utenti finali di eseguire azioni specifiche sui messaggi in quarantena.</span><span class="sxs-lookup"><span data-stu-id="c31c1-110">Or, you can create and assign custom quarantine policies to allow or prevent end users from performing specific actions on quarantined messages.</span></span>

<span data-ttu-id="c31c1-111">Le singole autorizzazioni vengono combinate nei gruppi di autorizzazioni preimpostati seguenti:</span><span class="sxs-lookup"><span data-stu-id="c31c1-111">The individual permissions are combined into the following preset permission groups:</span></span>

- <span data-ttu-id="c31c1-112">Nessun diritto di accesso</span><span class="sxs-lookup"><span data-stu-id="c31c1-112">No access</span></span>
- <span data-ttu-id="c31c1-113">Accesso limitato</span><span class="sxs-lookup"><span data-stu-id="c31c1-113">Limited access</span></span>
- <span data-ttu-id="c31c1-114">Accesso completo</span><span class="sxs-lookup"><span data-stu-id="c31c1-114">Full access</span></span>

<span data-ttu-id="c31c1-115">Le singole autorizzazioni disponibili e ciò che è incluso o non incluso nei gruppi di autorizzazioni preimpostati sono descritti nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="c31c1-115">The available individual permissions and what's included or not included in the preset permission groups are described in the following table:</span></span>

<br>

****

|<span data-ttu-id="c31c1-116">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="c31c1-116">Permission</span></span>|<span data-ttu-id="c31c1-117">Nessun diritto di accesso</span><span class="sxs-lookup"><span data-stu-id="c31c1-117">No access</span></span>|<span data-ttu-id="c31c1-118">Accesso limitato</span><span class="sxs-lookup"><span data-stu-id="c31c1-118">Limited access</span></span>|<span data-ttu-id="c31c1-119">Accesso completo</span><span class="sxs-lookup"><span data-stu-id="c31c1-119">Full access</span></span>|
|---|:---:|:---:|:---:|
|<span data-ttu-id="c31c1-120">**Consenti mittente** (_PermissionToAllowSender_)</span><span class="sxs-lookup"><span data-stu-id="c31c1-120">**Allow sender** (_PermissionToAllowSender_)</span></span>|||![Segno di spunta](../../media/checkmark.png)|
|<span data-ttu-id="c31c1-122">**Blocca mittente** (_PermissionToBlockSender_)</span><span class="sxs-lookup"><span data-stu-id="c31c1-122">**Block sender** (_PermissionToBlockSender_)</span></span>||![Segno di spunta](../../media/checkmark.png)|![Segno di spunta](../../media/checkmark.png)|
|<span data-ttu-id="c31c1-125">**Delete** (_PermissionToDelete_)</span><span class="sxs-lookup"><span data-stu-id="c31c1-125">**Delete** (_PermissionToDelete_)</span></span>||![Segno di spunta](../../media/checkmark.png)|![Segno di spunta](../../media/checkmark.png)|
|<span data-ttu-id="c31c1-128">**Anteprima** (_PermissionToPreview_)</span><span class="sxs-lookup"><span data-stu-id="c31c1-128">**Preview** (_PermissionToPreview_)</span></span>||![Segno di spunta](../../media/checkmark.png)|![Segno di spunta](../../media/checkmark.png)|
|<span data-ttu-id="c31c1-131">**Consentire ai destinatari di rilasciare un messaggio dalla quarantena** (_PermissionToRelease_)</span><span class="sxs-lookup"><span data-stu-id="c31c1-131">**Allow recipients to release a message from quarantine** (_PermissionToRelease_)</span></span>|||![Segno di spunta](../../media/checkmark.png)|
|<span data-ttu-id="c31c1-133">**Consentire ai destinatari di richiedere il rilascio di un messaggio dalla quarantena** (_PermissionToRequestRelease_)</span><span class="sxs-lookup"><span data-stu-id="c31c1-133">**Allow recipients to request a message to be released from quarantine** (_PermissionToRequestRelease_)</span></span>||![Segno di spunta](../../media/checkmark.png)||
|

<span data-ttu-id="c31c1-135">Se non si desidera utilizzare le autorizzazioni predefinite nei gruppi di autorizzazioni preimpostati, è possibile utilizzare le autorizzazioni personalizzate quando si creano o si modificano criteri di quarantena personalizzati.</span><span class="sxs-lookup"><span data-stu-id="c31c1-135">If you don't like the default permissions in the preset permission groups, you can use custom permissions when you create or modify custom quarantine policies.</span></span> <span data-ttu-id="c31c1-136">Per ulteriori informazioni sulle attività di ogni autorizzazione, vedere la sezione [Dettagli](#quarantine-policy-permission-details) sulle autorizzazioni dei criteri di quarantena più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="c31c1-136">For more information about what each permission does, see the [Quarantine policy permission details](#quarantine-policy-permission-details) section later in this article.</span></span>

<span data-ttu-id="c31c1-137">È possibile creare e assegnare criteri di quarantena nel portale di Microsoft 365 Defender o in PowerShell (Exchange Online PowerShell per le organizzazioni Microsoft 365 con cassette postali di Exchange Online; PowerShell EOP autonomo nelle organizzazioni EOP senza cassette postali Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="c31c1-137">You create and assign quarantine policies in the Microsoft 365 Defender portal or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with Exchange Online Mailboxes; standalone EOP PowerShell in EOP organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c31c1-138">Che cosa è necessario sapere prima di iniziare?</span><span class="sxs-lookup"><span data-stu-id="c31c1-138">What do you need to know before you begin?</span></span>

- <span data-ttu-id="c31c1-139">Per aprire il portale di Microsoft 365 Defender, andare alla pagina <https://security.microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="c31c1-139">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="c31c1-140">Oppure per passare direttamente alla pagina **Criteri di** quarantena, aprire <https://security.microsoft.com/quarantineTags> .</span><span class="sxs-lookup"><span data-stu-id="c31c1-140">Or to go directly to the **Quarantine policies** page, open <https://security.microsoft.com/quarantineTags>.</span></span>

- <span data-ttu-id="c31c1-141">Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="c31c1-141">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="c31c1-142">Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="c31c1-142">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="c31c1-143">Per visualizzare, creare, modificare o rimuovere i criteri di quarantena,  è necessario essere membri dei ruoli **Gestione** organizzazione o Amministratore sicurezza nel portale Microsoft 365 Defender sicurezza.</span><span class="sxs-lookup"><span data-stu-id="c31c1-143">To view, create, modify, or remove quarantine policies, you need to be a member of the **Organization Management** or **Security Administrator** roles in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="c31c1-144">Per altre informazioni, vedere [Autorizzazioni nel portale di Microsoft 365 Defender](permissions-microsoft-365-security-center.md).</span><span class="sxs-lookup"><span data-stu-id="c31c1-144">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>

## <a name="step-1-create-quarantine-policies-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="c31c1-145">Passaggio 1: Creare criteri di quarantena nel portale Microsoft 365 Defender di quarantena</span><span class="sxs-lookup"><span data-stu-id="c31c1-145">Step 1: Create quarantine policies in the Microsoft 365 Defender portal</span></span>

1. <span data-ttu-id="c31c1-146">Nel portale Microsoft 365 Defender, passare a Posta **elettronica &** criteri di minaccia di collaborazione Sezione Criteri di quarantena e \>  \>  quindi \>  selezionare Criteri **di quarantena.**</span><span class="sxs-lookup"><span data-stu-id="c31c1-146">In the Microsoft 365 Defender portal, go to **Email & collaboration** \>**Threat policies** \> **Rules** section \> **Quarantine policies** and then select **Quarantine policies**.</span></span>

2. <span data-ttu-id="c31c1-147">Nella pagina **Criterio quarantena** fare clic su Aggiungi icona criterio personalizzato Aggiungi ![ criterio ](../../media/m365-cc-sc-create-icon.png) **personalizzato.**</span><span class="sxs-lookup"><span data-stu-id="c31c1-147">On the **Quarantine policy** page, click ![Add custom policy icon](../../media/m365-cc-sc-create-icon.png) **Add custom policy**.</span></span>

3. <span data-ttu-id="c31c1-148">Verrà **visualizzata la procedura guidata** Nuovo criterio.</span><span class="sxs-lookup"><span data-stu-id="c31c1-148">The **New policy** wizard opens.</span></span> <span data-ttu-id="c31c1-149">Nella pagina **Nome criterio** immettere un nome breve ma univoco nella **casella Nome** criterio.</span><span class="sxs-lookup"><span data-stu-id="c31c1-149">On the **Policy name** page, enter a brief but unique name in the **Policy name** box.</span></span> <span data-ttu-id="c31c1-150">Dovrai identificare e selezionare il criterio di quarantena in base al nome nei passaggi successivi.</span><span class="sxs-lookup"><span data-stu-id="c31c1-150">You'll need to identify and select the quarantine policy by name in upcoming steps.</span></span> <span data-ttu-id="c31c1-151">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="c31c1-151">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="c31c1-152">Nella pagina **Accesso messaggio destinatario** selezionare uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="c31c1-152">On the **Recipient message access** page, select one of the following values:</span></span>
   - <span data-ttu-id="c31c1-153">**Nessun accesso**</span><span class="sxs-lookup"><span data-stu-id="c31c1-153">**No access**</span></span>
   - <span data-ttu-id="c31c1-154">**Accesso limitato**</span><span class="sxs-lookup"><span data-stu-id="c31c1-154">**Limited access**</span></span>
   - <span data-ttu-id="c31c1-155">**Accesso completo**</span><span class="sxs-lookup"><span data-stu-id="c31c1-155">**Full access**</span></span>

   <span data-ttu-id="c31c1-156">Le singole autorizzazioni incluse in questi gruppi di autorizzazioni sono descritte in precedenza in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="c31c1-156">The individual permissions that are included in these permission groups are described earlier in this article.</span></span>

   <span data-ttu-id="c31c1-157">Per specificare autorizzazioni personalizzate, selezionare **Imposta accesso specifico (avanzate)** e configurare le impostazioni seguenti visualizzate:</span><span class="sxs-lookup"><span data-stu-id="c31c1-157">To specify custom permissions, select **Set specific access (Advanced)** and the configure the following settings that appear:</span></span>

     - <span data-ttu-id="c31c1-158">**Selezionare la preferenza per l'azione di** rilascio : selezionare uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="c31c1-158">**Select release action preference**: Select one of the following values:</span></span>
       - <span data-ttu-id="c31c1-159">**Nessuna azione di rilascio:** questo è il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="c31c1-159">**No release action**: This is the default value.</span></span>
       - <span data-ttu-id="c31c1-160">**Consentire ai destinatari di rilasciare un messaggio dalla quarantena**</span><span class="sxs-lookup"><span data-stu-id="c31c1-160">**Allow recipients to release a message from quarantine**</span></span>
       - <span data-ttu-id="c31c1-161">**Consentire ai destinatari di richiedere il rilascio di un messaggio dalla quarantena**</span><span class="sxs-lookup"><span data-stu-id="c31c1-161">**Allow recipients to request a message to be released from quarantine**</span></span>
     - <span data-ttu-id="c31c1-162">**Selezionare altre azioni che i destinatari possono eseguire sui** messaggi in quarantena: selezionare alcuni, tutti o nessuno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="c31c1-162">**Select additional actions recipients can take on quarantined messages**: Select some, all, or none of the following values:</span></span>
       - <span data-ttu-id="c31c1-163">**Elimina**</span><span class="sxs-lookup"><span data-stu-id="c31c1-163">**Delete**</span></span>
       - <span data-ttu-id="c31c1-164">**Anteprima**</span><span class="sxs-lookup"><span data-stu-id="c31c1-164">**Preview**</span></span>
       - <span data-ttu-id="c31c1-165">**Blocca mittente**</span><span class="sxs-lookup"><span data-stu-id="c31c1-165">**Block sender**</span></span>

   <span data-ttu-id="c31c1-166">Queste autorizzazioni e il relativo effetto sui messaggi in quarantena e sulle notifiche di posta indesiderata dell'utente finale sono descritti nella sezione [Dettagli](#quarantine-policy-permission-details) sulle autorizzazioni dei criteri di quarantena più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="c31c1-166">These permissions and their effect on quarantined messages and in end-user spam notifications are described in the [Quarantine policy permission details](#quarantine-policy-permission-details) section later in this article.</span></span>

   <span data-ttu-id="c31c1-167">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="c31c1-167">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="c31c1-168">Nella pagina **Rivedere i** criteri visualizzata esaminare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="c31c1-168">On the **Review policy** page that appears, review your settings.</span></span> <span data-ttu-id="c31c1-169">È possibile selezionare **Modifica** in ogni sezione per modificare le impostazioni all'interno della sezione.</span><span class="sxs-lookup"><span data-stu-id="c31c1-169">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="c31c1-170">Oppure è possibile fare clic su **Indietro** o selezionare la pagina specifica della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="c31c1-170">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="c31c1-171">Al termine, fare clic su **Invia.**</span><span class="sxs-lookup"><span data-stu-id="c31c1-171">When you're finished, click **Submit**.</span></span>

6. <span data-ttu-id="c31c1-172">Nel messaggio di conferma visualizzato fare clic su **Fatto**.</span><span class="sxs-lookup"><span data-stu-id="c31c1-172">On the confirmation page that appears, click **Done**.</span></span>

<span data-ttu-id="c31c1-173">Ora sei pronto per assegnare il criterio di quarantena a una funzionalità di quarantena, come descritto nella [sezione Passaggio 2.](#step-2-assign-a-quarantine-policy-to-supported-features)</span><span class="sxs-lookup"><span data-stu-id="c31c1-173">Now you're ready to assign the quarantine policy to a quarantine feature as described in the [Step 2](#step-2-assign-a-quarantine-policy-to-supported-features) section.</span></span>

### <a name="create-quarantine-policies-in-powershell"></a><span data-ttu-id="c31c1-174">Creare criteri di quarantena in PowerShell</span><span class="sxs-lookup"><span data-stu-id="c31c1-174">Create quarantine policies in PowerShell</span></span>

<span data-ttu-id="c31c1-175">Se si preferisce usare PowerShell per creare criteri di quarantena, connettersi Exchange Online PowerShell o Exchange Online Protection PowerShell e utilizzare il cmdlet **New-QuarantineTag.**</span><span class="sxs-lookup"><span data-stu-id="c31c1-175">If you'd rather use PowerShell to create quarantine policies, connect to Exchange Online PowerShell or Exchange Online Protection PowerShell and use the **New-QuarantineTag** cmdlet.</span></span> <span data-ttu-id="c31c1-176">Sono disponibili due metodi diversi tra cui scegliere:</span><span class="sxs-lookup"><span data-stu-id="c31c1-176">You have two different methods to choose from:</span></span>

- <span data-ttu-id="c31c1-177">Utilizzare il _parametro EndUserQuarantinePermissionsValue._</span><span class="sxs-lookup"><span data-stu-id="c31c1-177">Use the _EndUserQuarantinePermissionsValue_ parameter.</span></span>
- <span data-ttu-id="c31c1-178">Utilizzare il _parametro EndUserQuarantinePermissions._</span><span class="sxs-lookup"><span data-stu-id="c31c1-178">Use the _EndUserQuarantinePermissions_ parameter.</span></span>

<span data-ttu-id="c31c1-179">Questi metodi sono descritti nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="c31c1-179">These methods are described in the following sections.</span></span>

#### <a name="use-the-enduserquarantinepermissionsvalue-parameter"></a><span data-ttu-id="c31c1-180">Utilizzare il parametro EndUserQuarantinePermissionsValue</span><span class="sxs-lookup"><span data-stu-id="c31c1-180">Use the EndUserQuarantinePermissionsValue parameter</span></span>

<span data-ttu-id="c31c1-181">Per creare un criterio di quarantena utilizzando il _parametro EndUserQuarantinePermissionsValue,_ utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="c31c1-181">To create a quarantine policy using the _EndUserQuarantinePermissionsValue_ parameter, use the following syntax:</span></span>

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissionsValue <0 to 236>
```

<span data-ttu-id="c31c1-182">Il _parametro EndUserQuarantinePermissionsValue_ utilizza un valore decimale convertito da un valore binario.</span><span class="sxs-lookup"><span data-stu-id="c31c1-182">The _EndUserQuarantinePermissionsValue_ parameter uses a decimal value that's converted from a binary value.</span></span> <span data-ttu-id="c31c1-183">Il valore binario corrisponde alle autorizzazioni disponibili per la quarantena dell'utente finale in un ordine specifico.</span><span class="sxs-lookup"><span data-stu-id="c31c1-183">The binary value corresponds to the available end-user quarantine permissions in a specific order.</span></span> <span data-ttu-id="c31c1-184">Per ogni autorizzazione, il valore 1 è uguale a True e il valore 0 è uguale a False.</span><span class="sxs-lookup"><span data-stu-id="c31c1-184">For each permission, the value 1 equals True and the value 0 equals False.</span></span>

<span data-ttu-id="c31c1-185">L'ordine e i valori necessari per ogni singola autorizzazione nei gruppi di autorizzazioni preimpostati sono descritti nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="c31c1-185">The required order and values for each individual permission in preset permission groups are described in the following table:</span></span>

<br>

****

|<span data-ttu-id="c31c1-186">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="c31c1-186">Permission</span></span>|<span data-ttu-id="c31c1-187">Nessun diritto di accesso</span><span class="sxs-lookup"><span data-stu-id="c31c1-187">No access</span></span>|<span data-ttu-id="c31c1-188">Accesso limitato</span><span class="sxs-lookup"><span data-stu-id="c31c1-188">Limited access</span></span>|<span data-ttu-id="c31c1-189">Accesso completo</span><span class="sxs-lookup"><span data-stu-id="c31c1-189">Full access</span></span>|
|---|:---:|:---:|:---:|
|<span data-ttu-id="c31c1-190">PermissionToAllowSender</span><span class="sxs-lookup"><span data-stu-id="c31c1-190">PermissionToAllowSender</span></span>|<span data-ttu-id="c31c1-191">0</span><span class="sxs-lookup"><span data-stu-id="c31c1-191">0</span></span>|<span data-ttu-id="c31c1-192">0</span><span class="sxs-lookup"><span data-stu-id="c31c1-192">0</span></span>|<span data-ttu-id="c31c1-193">1</span><span class="sxs-lookup"><span data-stu-id="c31c1-193">1</span></span>|
|<span data-ttu-id="c31c1-194">PermissionToBlockSender</span><span class="sxs-lookup"><span data-stu-id="c31c1-194">PermissionToBlockSender</span></span>|<span data-ttu-id="c31c1-195">0</span><span class="sxs-lookup"><span data-stu-id="c31c1-195">0</span></span>|<span data-ttu-id="c31c1-196">1</span><span class="sxs-lookup"><span data-stu-id="c31c1-196">1</span></span>|<span data-ttu-id="c31c1-197">1</span><span class="sxs-lookup"><span data-stu-id="c31c1-197">1</span></span>|
|<span data-ttu-id="c31c1-198">PermissionToDelete</span><span class="sxs-lookup"><span data-stu-id="c31c1-198">PermissionToDelete</span></span>|<span data-ttu-id="c31c1-199">0</span><span class="sxs-lookup"><span data-stu-id="c31c1-199">0</span></span>|<span data-ttu-id="c31c1-200">1</span><span class="sxs-lookup"><span data-stu-id="c31c1-200">1</span></span>|<span data-ttu-id="c31c1-201">1</span><span class="sxs-lookup"><span data-stu-id="c31c1-201">1</span></span>|
|<span data-ttu-id="c31c1-202">PermissionToDownload<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c31c1-202">PermissionToDownload<sup>\*</sup></span></span>|<span data-ttu-id="c31c1-203">0</span><span class="sxs-lookup"><span data-stu-id="c31c1-203">0</span></span>|<span data-ttu-id="c31c1-204">0</span><span class="sxs-lookup"><span data-stu-id="c31c1-204">0</span></span>|<span data-ttu-id="c31c1-205">0</span><span class="sxs-lookup"><span data-stu-id="c31c1-205">0</span></span>|
|<span data-ttu-id="c31c1-206">PermissionToPreview</span><span class="sxs-lookup"><span data-stu-id="c31c1-206">PermissionToPreview</span></span>|<span data-ttu-id="c31c1-207">0</span><span class="sxs-lookup"><span data-stu-id="c31c1-207">0</span></span>|<span data-ttu-id="c31c1-208">1</span><span class="sxs-lookup"><span data-stu-id="c31c1-208">1</span></span>|<span data-ttu-id="c31c1-209">1</span><span class="sxs-lookup"><span data-stu-id="c31c1-209">1</span></span>|
|<span data-ttu-id="c31c1-210">PermissionToRelease<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="c31c1-210">PermissionToRelease<sup>\*\*</sup></span></span>|<span data-ttu-id="c31c1-211">0</span><span class="sxs-lookup"><span data-stu-id="c31c1-211">0</span></span>|<span data-ttu-id="c31c1-212">0</span><span class="sxs-lookup"><span data-stu-id="c31c1-212">0</span></span>|<span data-ttu-id="c31c1-213">1</span><span class="sxs-lookup"><span data-stu-id="c31c1-213">1</span></span>|
|<span data-ttu-id="c31c1-214">PermissionToRequestRelease<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="c31c1-214">PermissionToRequestRelease<sup>\*\*</sup></span></span>|<span data-ttu-id="c31c1-215">0</span><span class="sxs-lookup"><span data-stu-id="c31c1-215">0</span></span>|<span data-ttu-id="c31c1-216">1</span><span class="sxs-lookup"><span data-stu-id="c31c1-216">1</span></span>|<span data-ttu-id="c31c1-217">0</span><span class="sxs-lookup"><span data-stu-id="c31c1-217">0</span></span>|
|<span data-ttu-id="c31c1-218">PermissionToViewHeader<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c31c1-218">PermissionToViewHeader<sup>\*</sup></span></span>|<span data-ttu-id="c31c1-219">0</span><span class="sxs-lookup"><span data-stu-id="c31c1-219">0</span></span>|<span data-ttu-id="c31c1-220">0</span><span class="sxs-lookup"><span data-stu-id="c31c1-220">0</span></span>|<span data-ttu-id="c31c1-221">0</span><span class="sxs-lookup"><span data-stu-id="c31c1-221">0</span></span>|
|<span data-ttu-id="c31c1-222">Valore binario</span><span class="sxs-lookup"><span data-stu-id="c31c1-222">Binary value</span></span>|<span data-ttu-id="c31c1-223">00000000</span><span class="sxs-lookup"><span data-stu-id="c31c1-223">00000000</span></span>|<span data-ttu-id="c31c1-224">01101010</span><span class="sxs-lookup"><span data-stu-id="c31c1-224">01101010</span></span>|<span data-ttu-id="c31c1-225">11101100</span><span class="sxs-lookup"><span data-stu-id="c31c1-225">11101100</span></span>|
|<span data-ttu-id="c31c1-226">Valore decimale da utilizzare</span><span class="sxs-lookup"><span data-stu-id="c31c1-226">Decimal value to use</span></span>|<span data-ttu-id="c31c1-227">0</span><span class="sxs-lookup"><span data-stu-id="c31c1-227">0</span></span>|<span data-ttu-id="c31c1-228">106</span><span class="sxs-lookup"><span data-stu-id="c31c1-228">106</span></span>|<span data-ttu-id="c31c1-229">236</span><span class="sxs-lookup"><span data-stu-id="c31c1-229">236</span></span>|
|

<span data-ttu-id="c31c1-230"><sup>\*</sup> Attualmente, questo valore è sempre 0.</span><span class="sxs-lookup"><span data-stu-id="c31c1-230"><sup>\*</sup> Currently, this value is always 0.</span></span> <span data-ttu-id="c31c1-231">Per PermissionToViewHeader, il valore 0  non nasconde il pulsante Visualizza intestazione messaggio nei dettagli del messaggio in quarantena (il pulsante è sempre disponibile).</span><span class="sxs-lookup"><span data-stu-id="c31c1-231">For PermissionToViewHeader, the value 0 doesn't hide the **View message header** button in the details of the quarantined message (the button is always available).</span></span>

<span data-ttu-id="c31c1-232"><sup>\*\*</sup> Non impostare entrambi questi valori su 1.</span><span class="sxs-lookup"><span data-stu-id="c31c1-232"><sup>\*\*</sup> Don't set both of these values to 1.</span></span> <span data-ttu-id="c31c1-233">Impostare uno su 1 e l'altro su 0 oppure impostare entrambi su 0.</span><span class="sxs-lookup"><span data-stu-id="c31c1-233">Set one to 1 and the other to 0, or set both to 0.</span></span>

<span data-ttu-id="c31c1-234">In questo esempio viene creato un nuovo nome di criterio di quarantena NoAccess che assegna le autorizzazioni No access come descritto nella tabella precedente.</span><span class="sxs-lookup"><span data-stu-id="c31c1-234">This example creates a new quarantine policy name NoAccess that assigns the No access permissions as described in the previous table.</span></span>

```powershell
New-QuarantineTag -Name NoAccess -EndUserQuarantinePermissionsValue 0
```

<span data-ttu-id="c31c1-235">Per Autorizzazioni di accesso limitato, utilizzare il valore 106.</span><span class="sxs-lookup"><span data-stu-id="c31c1-235">For Limited access permissions, use the value 106.</span></span> <span data-ttu-id="c31c1-236">Per autorizzazioni di accesso completo, utilizzare il valore 236.</span><span class="sxs-lookup"><span data-stu-id="c31c1-236">For Full access permissions, use the value 236.</span></span>

<span data-ttu-id="c31c1-237">Per le autorizzazioni personalizzate, utilizzare la tabella precedente per ottenere il valore binario corrispondente alle autorizzazioni desiderate.</span><span class="sxs-lookup"><span data-stu-id="c31c1-237">For custom permissions, use the previous table to get the binary value that corresponds to the permissions you want.</span></span> <span data-ttu-id="c31c1-238">Convertire il valore binario in un valore decimale e utilizzare il valore decimale per il _parametro EndUserQuarantinePermissionsValue._</span><span class="sxs-lookup"><span data-stu-id="c31c1-238">Convert the binary value to a decimal value and use the decimal value for the _EndUserQuarantinePermissionsValue_ parameter.</span></span>

<span data-ttu-id="c31c1-239">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere New-QuarantineTag](/powershell/module/exchange/new-quarantinetag).</span><span class="sxs-lookup"><span data-stu-id="c31c1-239">For detailed syntax and parameter information, see [New-QuarantineTag](/powershell/module/exchange/new-quarantinetag).</span></span>

#### <a name="use-the-enduserquarantinepermissions-parameter"></a><span data-ttu-id="c31c1-240">Utilizzare il parametro EndUserQuarantinePermissions</span><span class="sxs-lookup"><span data-stu-id="c31c1-240">Use the EndUserQuarantinePermissions parameter</span></span>

<span data-ttu-id="c31c1-241">Per creare un criterio di quarantena utilizzando il _parametro EndUserQuarantinePermissionsValue,_ eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="c31c1-241">To create a quarantine policy using the _EndUserQuarantinePermissionsValue_ parameter, do the following steps:</span></span>

<span data-ttu-id="c31c1-242">R.</span><span class="sxs-lookup"><span data-stu-id="c31c1-242">A.</span></span> <span data-ttu-id="c31c1-243">Archiviare un oggetto autorizzazioni di quarantena in una variabile utilizzando il cmdlet **New-QuarantinePermissions.**</span><span class="sxs-lookup"><span data-stu-id="c31c1-243">Store a quarantine permissions object in a variable using the **New-QuarantinePermissions** cmdlet.</span></span>

<p>

<span data-ttu-id="c31c1-244">B.</span><span class="sxs-lookup"><span data-stu-id="c31c1-244">B.</span></span> <span data-ttu-id="c31c1-245">Utilizzare la variabile come _valore EndUserQuarantinePermissions_ nel **comando New-QuarantineTag.**</span><span class="sxs-lookup"><span data-stu-id="c31c1-245">Use the variable as the _EndUserQuarantinePermissions_ value in the **New-QuarantineTag** command.</span></span>

##### <a name="step-a-store-a-quarantine-permissions-object-in-a-variable"></a><span data-ttu-id="c31c1-246">Passaggio A: Archiviare un oggetto autorizzazioni di quarantena in una variabile</span><span class="sxs-lookup"><span data-stu-id="c31c1-246">Step A: Store a quarantine permissions object in a variable</span></span>

<span data-ttu-id="c31c1-247">Usare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="c31c1-247">Use the following syntax:</span></span>

```powershell
$<VariableName> = New-QuarantinePermissions [-PermissionToAllowSender <$true | $False>] [-PermissionToBlockSender <$true | $False>] [-PermissionToDelete <$true | $False>] [-PermissionToPreview <$true | $False>] [-PermissionToRelease <$true | $False>] [-PermissionToRequestRelease <$true | $False>]
```

<span data-ttu-id="c31c1-248">Il valore predefinito per tutti i parametri inutilizzati è , quindi è necessario utilizzare solo i parametri in cui si `$false` desidera impostare value su `$true` .</span><span class="sxs-lookup"><span data-stu-id="c31c1-248">The default value for any unused parameters is `$false`, so you only need to use the parameters where you want to set value to `$true`.</span></span>

<span data-ttu-id="c31c1-249">Negli esempi seguenti viene illustrato come creare oggetti autorizzazione che corrispondono ai gruppi di autorizzazioni preimpostati:</span><span class="sxs-lookup"><span data-stu-id="c31c1-249">The following examples show how to create permission objects that correspond to the preset permissions groups:</span></span>

- <span data-ttu-id="c31c1-250">**Nessun accesso**:</span><span class="sxs-lookup"><span data-stu-id="c31c1-250">**No access**:</span></span>

  ```powershell
  $NoAccess = New-QuarantinePermissions
  ```

- <span data-ttu-id="c31c1-251">**Accesso limitato**:</span><span class="sxs-lookup"><span data-stu-id="c31c1-251">**Limited access**:</span></span>

  ```powershell
  $LimitedAccess = New-QuarantinePermissions -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRequestRelease $true
  ```

- <span data-ttu-id="c31c1-252">**Accesso completo**:</span><span class="sxs-lookup"><span data-stu-id="c31c1-252">**Full access**:</span></span>

  ```powershell
  $FullAccess = New-QuarantinePermissions -PermissionToAllowSender $true -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRelease $true
  ```

<span data-ttu-id="c31c1-253">Per visualizzare i valori impostati, eseguire il nome della variabile come comando, ad esempio eseguire il comando `$NoAccess` .</span><span class="sxs-lookup"><span data-stu-id="c31c1-253">To see the values that you've set, run the variable name as a command (for example, run the command `$NoAccess`).</span></span>

<span data-ttu-id="c31c1-254">Per le autorizzazioni personalizzate, non impostare entrambi i _parametri PermissionToRelease_ _e PermissionToRequestRelease_ su `$true` .</span><span class="sxs-lookup"><span data-stu-id="c31c1-254">For custom permissions, don't set both the _PermissionToRelease_ and _PermissionToRequestRelease_ parameters to `$true`.</span></span> <span data-ttu-id="c31c1-255">Impostare uno su `$true` e lasciare l'altro come `$false` o lasciare entrambi come `$false` .</span><span class="sxs-lookup"><span data-stu-id="c31c1-255">Set one to `$true` and leave the other as `$false`, or leave both as `$false`.</span></span>

<span data-ttu-id="c31c1-256">È inoltre possibile modificare una variabile oggetto autorizzazioni esistente dopo la creazione, ma prima di utilizzarla utilizzando il cmdlet **Set-QuarantinePermissions.**</span><span class="sxs-lookup"><span data-stu-id="c31c1-256">You can also modify an existing permissions object variable after you create but before you use it by using the **Set-QuarantinePermissions** cmdlet.</span></span>

<span data-ttu-id="c31c1-257">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [New-QuarantinePermissions](/powershell/module/exchange/new-quarantinepermissions) e [Set-QuarantinePermissions](/powershell/module/exchange/set-quarantinepermissions).</span><span class="sxs-lookup"><span data-stu-id="c31c1-257">For detailed syntax and parameter information, see [New-QuarantinePermissions](/powershell/module/exchange/new-quarantinepermissions) and [Set-QuarantinePermissions](/powershell/module/exchange/set-quarantinepermissions).</span></span>

##### <a name="step-b-use-the-variable-in-the-new-quarantinetag-command"></a><span data-ttu-id="c31c1-258">Passaggio B: Utilizzare la variabile nel New-QuarantineTag comando</span><span class="sxs-lookup"><span data-stu-id="c31c1-258">Step B: Use the variable in the New-QuarantineTag command</span></span>

<span data-ttu-id="c31c1-259">Dopo aver creato e archiviato l'oggetto autorizzazioni in una variabile, utilizzare la variabile per il valore del parametro _EndUserQuarantinePermission_ nel comando **New-QuarantineTag** seguente:</span><span class="sxs-lookup"><span data-stu-id="c31c1-259">After you've created and stored the permissions object in a variable, use the variable for the _EndUserQuarantinePermission_ parameter value in the following **New-QuarantineTag** command:</span></span>

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissions $<VariableName>
```

<span data-ttu-id="c31c1-260">In questo esempio viene creato un nuovo criterio di quarantena denominato LimitedAccess utilizzando l'oggetto autorizzazioni descritto `$LimitedAccess` e creato nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="c31c1-260">This example creates a new quarantine policy named LimitedAccess using the `$LimitedAccess` permissions object that was described and created in the previous step.</span></span>

```powershell
New-QuarantineTag -Name LimitedAccess -EndUserQuarantinePermissions $LimitedAccess
```

<span data-ttu-id="c31c1-261">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere New-QuarantineTag](/powershell/module/exchange/new-quarantinetag).</span><span class="sxs-lookup"><span data-stu-id="c31c1-261">For detailed syntax and parameter information, see [New-QuarantineTag](/powershell/module/exchange/new-quarantinetag).</span></span>

## <a name="step-2-assign-a-quarantine-policy-to-supported-features"></a><span data-ttu-id="c31c1-262">Passaggio 2: Assegnare un criterio di quarantena alle funzionalità supportate</span><span class="sxs-lookup"><span data-stu-id="c31c1-262">Step 2: Assign a quarantine policy to supported features</span></span>

<span data-ttu-id="c31c1-263">Nelle _funzionalità_ di protezione supportate per mettere in quarantena i messaggi o i file (automaticamente o come azione configurabile), è possibile assegnare un criterio di quarantena alle azioni di quarantena disponibili.</span><span class="sxs-lookup"><span data-stu-id="c31c1-263">In _supported_ protection features that quarantine messages or files (automatically or as a configurable action), you can assign a quarantine policy to the available quarantine actions.</span></span> <span data-ttu-id="c31c1-264">Le funzionalità che consentono di mettere in quarantena i messaggi e la disponibilità dei criteri di quarantena sono descritte nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="c31c1-264">Features that quarantine messages and the availability of quarantine policies are described in the following table:</span></span>

<br>

****

|<span data-ttu-id="c31c1-265">Funzionalità</span><span class="sxs-lookup"><span data-stu-id="c31c1-265">Feature</span></span>|<span data-ttu-id="c31c1-266">Criteri di quarantena supportati?</span><span class="sxs-lookup"><span data-stu-id="c31c1-266">Quarantine policies supported?</span></span>|<span data-ttu-id="c31c1-267">Criteri di quarantena predefiniti utilizzati</span><span class="sxs-lookup"><span data-stu-id="c31c1-267">Default quarantine policies used</span></span>|
|---|:---:|---|
|<span data-ttu-id="c31c1-268">[Criteri di protezione da posta indesiderata](configure-your-spam-filter-policies.md):</span><span class="sxs-lookup"><span data-stu-id="c31c1-268">[Anti-spam policies](configure-your-spam-filter-policies.md):</span></span> <ul><li><span data-ttu-id="c31c1-269">**Posta** indesiderata (_SpamAction_)</span><span class="sxs-lookup"><span data-stu-id="c31c1-269">**Spam** (_SpamAction_)</span></span></li><li><span data-ttu-id="c31c1-270">**Posta indesiderata ad alta** probabilità (_HighConfidenceSpamAction_)</span><span class="sxs-lookup"><span data-stu-id="c31c1-270">**High confidence spam** (_HighConfidenceSpamAction_)</span></span></li><li><span data-ttu-id="c31c1-271">**Phishing** (_PhishSpamAction_)</span><span class="sxs-lookup"><span data-stu-id="c31c1-271">**Phishing** (_PhishSpamAction_)</span></span></li><li><span data-ttu-id="c31c1-272">**Phishing ad alta probabilità** (_HighConfidencePhishAction_)</span><span class="sxs-lookup"><span data-stu-id="c31c1-272">**High confidence phishing** (_HighConfidencePhishAction_)</span></span></li><li><span data-ttu-id="c31c1-273">**Bulk** (_BulkSpamAction_)</span><span class="sxs-lookup"><span data-stu-id="c31c1-273">**Bulk** (_BulkSpamAction_)</span></span></li></ul>|<span data-ttu-id="c31c1-274">Sì</span><span class="sxs-lookup"><span data-stu-id="c31c1-274">Yes</span></span>|<ul><li><span data-ttu-id="c31c1-275">DefaultSpamTag (accesso completo)</span><span class="sxs-lookup"><span data-stu-id="c31c1-275">DefaultSpamTag (Full access)</span></span></li><li><span data-ttu-id="c31c1-276">DefaultHighConfSpamTag (accesso completo)</span><span class="sxs-lookup"><span data-stu-id="c31c1-276">DefaultHighConfSpamTag (Full access)</span></span></li><li><span data-ttu-id="c31c1-277">DefaultPhishTag (accesso completo)</span><span class="sxs-lookup"><span data-stu-id="c31c1-277">DefaultPhishTag (Full access)</span></span></li><li><span data-ttu-id="c31c1-278">DefaultHighConfPhishTag (nessun accesso)</span><span class="sxs-lookup"><span data-stu-id="c31c1-278">DefaultHighConfPhishTag (No access)</span></span></li><li><span data-ttu-id="c31c1-279">DefaultBulkTag (accesso completo)</span><span class="sxs-lookup"><span data-stu-id="c31c1-279">DefaultBulkTag (Full access)</span></span></li></ul>
|<span data-ttu-id="c31c1-280">Criteri anti-phishing:</span><span class="sxs-lookup"><span data-stu-id="c31c1-280">Anti-phishing policies:</span></span> <ul><li><span data-ttu-id="c31c1-281">[Protezione di spoofing intelligence](set-up-anti-phishing-policies.md#spoof-settings) (_AuthenticationFailAction_)</span><span class="sxs-lookup"><span data-stu-id="c31c1-281">[Spoof intelligence protection](set-up-anti-phishing-policies.md#spoof-settings) (_AuthenticationFailAction_)</span></span></li><li><span data-ttu-id="c31c1-282">[Protezione della rappresentazione](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365):<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c31c1-282">[Impersonation protection](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365):<sup>\*</sup></span></span> <ul><li><span data-ttu-id="c31c1-283">**Se il messaggio viene rilevato come utente rappresentato** (_TargetedUserProtectionAction_)</span><span class="sxs-lookup"><span data-stu-id="c31c1-283">**If message is detected as an impersonated user** (_TargetedUserProtectionAction_)</span></span></li><li><span data-ttu-id="c31c1-284">**Se il messaggio viene rilevato come dominio rappresentato** (_TargetedDomainProtectionAction_)</span><span class="sxs-lookup"><span data-stu-id="c31c1-284">**If message is detected as an impersonated domain** (_TargetedDomainProtectionAction_)</span></span></li><li><span data-ttu-id="c31c1-285">**Se l'intelligence delle cassette postali rileva e rappresenta l'utente** (_MailboxIntelligenceProtectionAction_)</span><span class="sxs-lookup"><span data-stu-id="c31c1-285">**If mailbox intelligence detects and impersonated user** (_MailboxIntelligenceProtectionAction_)</span></span></li></ul></li></ul></ul>|<span data-ttu-id="c31c1-286">No</span><span class="sxs-lookup"><span data-stu-id="c31c1-286">No</span></span>|<span data-ttu-id="c31c1-287">n/d</span><span class="sxs-lookup"><span data-stu-id="c31c1-287">n/a</span></span>|
|<span data-ttu-id="c31c1-288">[Criteri antimalware:](configure-anti-malware-policies.md)tutti i messaggi rilevati vengono sempre messi in quarantena.</span><span class="sxs-lookup"><span data-stu-id="c31c1-288">[Anti-malware policies](configure-anti-malware-policies.md): All detected messages are always quarantined.</span></span>|<span data-ttu-id="c31c1-289">No</span><span class="sxs-lookup"><span data-stu-id="c31c1-289">No</span></span>|<span data-ttu-id="c31c1-290">n/d</span><span class="sxs-lookup"><span data-stu-id="c31c1-290">n/a</span></span>|
|[<span data-ttu-id="c31c1-291">Allegati sicuri per SharePoint, OneDrive e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c31c1-291">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>](mdo-for-spo-odb-and-teams.md)|<span data-ttu-id="c31c1-292">No</span><span class="sxs-lookup"><span data-stu-id="c31c1-292">No</span></span>|<span data-ttu-id="c31c1-293">n/d</span><span class="sxs-lookup"><span data-stu-id="c31c1-293">n/a</span></span>|
|<span data-ttu-id="c31c1-294">[Regole del flusso di](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) posta (note anche come regole di trasporto) con l'azione: **Recapita il** messaggio alla quarantena ospitata (_Quarantine_).</span><span class="sxs-lookup"><span data-stu-id="c31c1-294">[Mail flow rules](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) with the action: **Deliver the message to the hosted quarantine** (_Quarantine_).</span></span>|<span data-ttu-id="c31c1-295">No</span><span class="sxs-lookup"><span data-stu-id="c31c1-295">No</span></span>|<span data-ttu-id="c31c1-296">n/d</span><span class="sxs-lookup"><span data-stu-id="c31c1-296">n/a</span></span>|
|

<span data-ttu-id="c31c1-297"><sup>\*</sup>Le impostazioni di protezione della rappresentazione sono disponibili solo nei criteri anti-phishing in Microsoft Defender per Office 365.</span><span class="sxs-lookup"><span data-stu-id="c31c1-297"><sup>\*</sup> Impersonation protection settings are available only in anti-phishing policies in Microsoft Defender for Office 365.</span></span>

<span data-ttu-id="c31c1-298">Se si è soddisfatti delle autorizzazioni dell'utente finale fornite dai criteri di quarantena predefiniti, non è necessario eseguire alcun'operazione.</span><span class="sxs-lookup"><span data-stu-id="c31c1-298">If you're happy with the end-user permissions that are provided by the default quarantine policies, you don't need to do anything.</span></span> <span data-ttu-id="c31c1-299">Se si desidera personalizzare le funzionalità dell'utente finale (pulsanti disponibili) nelle notifiche di posta indesiderata dell'utente finale o nei dettagli dei messaggi in quarantena, è possibile assegnare un criterio di quarantena personalizzato.</span><span class="sxs-lookup"><span data-stu-id="c31c1-299">If you want to customize the end-user capabilities (available buttons) in end-user spam notifications or in quarantined message details, you can assign a custom quarantine policy.</span></span>

### <a name="assign-quarantine-policies-in-anti-spam-policies-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="c31c1-300">Assegnare criteri di quarantena nei criteri di protezione da posta indesiderata nel portale Microsoft 365 Defender posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="c31c1-300">Assign quarantine policies in anti-spam policies in the Microsoft 365 Defender portal</span></span>

<span data-ttu-id="c31c1-301">Le istruzioni complete per la creazione e la modifica dei criteri di protezione da posta indesiderata sono descritte in [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="c31c1-301">Full instructions for creating and modifying anti-spam policies are described in [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

1. <span data-ttu-id="c31c1-302">Nel portale Microsoft 365 Defender, andare a **Posta elettronica & criteri di collaborazione** \> **&** \> **criteri di** protezione \> **da posta indesiderata**.</span><span class="sxs-lookup"><span data-stu-id="c31c1-302">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Policies & rules** \> **Policies** section \> **Anti-spam**.</span></span> <span data-ttu-id="c31c1-303">In caso contrario, aprire <https://security.microsoft.com/antispam> .</span><span class="sxs-lookup"><span data-stu-id="c31c1-303">Or, open <https://security.microsoft.com/antispam>.</span></span>

2. <span data-ttu-id="c31c1-304">Nella pagina **Criteri di protezione da** posta indesiderata eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c31c1-304">On the **Anti-spam policies** page, do one of the following steps:</span></span>
   - <span data-ttu-id="c31c1-305">Trovare e selezionare un criterio di protezione da posta **indesiderata in** ingresso esistente.</span><span class="sxs-lookup"><span data-stu-id="c31c1-305">Find and select an existing **inbound** anti-spam policy.</span></span>
   - <span data-ttu-id="c31c1-306">Creare un nuovo **criterio di** protezione da posta indesiderata in ingresso.</span><span class="sxs-lookup"><span data-stu-id="c31c1-306">Create a new **inbound** anti-spam policy.</span></span>

3. <span data-ttu-id="c31c1-307">Esegui uno dei seguenti passaggi:</span><span class="sxs-lookup"><span data-stu-id="c31c1-307">Do one of the following steps:</span></span>
   - <span data-ttu-id="c31c1-308">**Modificare i criteri di protezione da posta indesiderata** esistenti : nel riquadro a comparsa dei dettagli del criterio passare alla sezione **Azioni** e quindi fare clic su **Modifica azioni.**</span><span class="sxs-lookup"><span data-stu-id="c31c1-308">**Edit existing anti-spam policy**: In the policy details flyout, go to the **Actions** section and then click **Edit actions**.</span></span>
   - <span data-ttu-id="c31c1-309">**Creare nuovi criteri di protezione da** posta indesiderata: nella procedura guidata nuovo criterio passare alla **pagina** Azioni.</span><span class="sxs-lookup"><span data-stu-id="c31c1-309">**Create new anti-spam policy**: In the new policy wizard, go to the **Actions** page.</span></span>

4. <span data-ttu-id="c31c1-310">Nella **pagina** Azioni.</span><span class="sxs-lookup"><span data-stu-id="c31c1-310">On the **Actions** page.</span></span> <span data-ttu-id="c31c1-311">Ogni verdetto con l'azione **Messaggio**  in quarantena avrà anche la casella Seleziona criterio quarantena per selezionare un criterio di quarantena corrispondente.</span><span class="sxs-lookup"><span data-stu-id="c31c1-311">every verdict that has the **Quarantine message** action will also have the **Select quarantine policy** box for you to select a corresponding quarantine policy.</span></span>

   <span data-ttu-id="c31c1-312">**Nota:** quando si crea un  nuovo criterio, viene utilizzato un valore vuoto Seleziona criterio quarantena che indica il criterio di quarantena predefinito per tale verdetto.</span><span class="sxs-lookup"><span data-stu-id="c31c1-312">**Note**: When you create a new policy, a blank **Select quarantine policy** value indicates the default quarantine policy for that verdict is used.</span></span> <span data-ttu-id="c31c1-313">Quando successivamente si modifica il criterio, i valori vuoti vengono sostituiti dai nomi dei criteri di quarantena predefiniti effettivi, come descritto nella tabella precedente.</span><span class="sxs-lookup"><span data-stu-id="c31c1-313">When you later edit the policy, the blank values are replaced by the actual default quarantine policy names as described in the previous table.</span></span>

   ![Selezioni dei criteri di quarantena in un criterio di protezione da posta indesiderata](../../media/quarantine-tags-in-anti-spam-policies.png)

5. <span data-ttu-id="c31c1-315">Al termine, seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="c31c1-315">When you're finished, click **Save**.</span></span>

#### <a name="assign-quarantine-policies-in-anti-spam-policies-in-powershell"></a><span data-ttu-id="c31c1-316">Assegnare criteri di quarantena nei criteri di protezione da posta indesiderata in PowerShell</span><span class="sxs-lookup"><span data-stu-id="c31c1-316">Assign quarantine policies in anti-spam policies in PowerShell</span></span>

<span data-ttu-id="c31c1-317">Se si preferisce utilizzare PowerShell per assegnare criteri di quarantena nei criteri di protezione da posta indesiderata, connettersi Exchange Online PowerShell o Exchange Online Protection PowerShell e utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="c31c1-317">If you'd rather use PowerShell to assign quarantine policies in anti-spam policies, connect to Exchange Online PowerShell or Exchange Online Protection PowerShell and use the following syntax:</span></span>

```powershell
<New-HostedContentFilterPolicy -Name "<Unique name>" | Set-HostedContentFilterPolicy -Identity "<Policy name>">  [-SpamAction Quarantine] [-SpamQuarantineTag <QuarantineTagName>] [-HighConfidenceSpamAction Quarantine] [-HighConfidenceSpamQuarantineTag <QuarantineTagName>] [-PhishSpamAction Quarantine] [-PhishQuarantineTag <QuarantineTagName>] [-HighConfidencePhishQuarantineTag <QuarantineTagName>] [-BulkSpamAction Quarantine] [-BulkQuarantineTag <QuarantineTagName>] ...
```

<span data-ttu-id="c31c1-318">**Note**:</span><span class="sxs-lookup"><span data-stu-id="c31c1-318">**Notes**:</span></span>

- <span data-ttu-id="c31c1-319">Il valore predefinito per il _parametro HighConfidencePhishAction_ è Quarantine, quindi non è necessario impostare l'azione Quarantine per i rilevamenti di phishing ad alta probabilità nei nuovi criteri di protezione da posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="c31c1-319">The default value for the _HighConfidencePhishAction_ parameter is Quarantine, so you don't need to set the Quarantine action for high confidence phishing detections in new anti-spam policies.</span></span> <span data-ttu-id="c31c1-320">Per tutti gli altri verdetti di filtro della posta indesiderata nei criteri di protezione da posta indesiderata nuovi o esistenti, il criterio di quarantena è efficace solo se il valore dell'azione è Quarantine.</span><span class="sxs-lookup"><span data-stu-id="c31c1-320">For all other spam filtering verdicts in new or existing anti-spam policies, the quarantine policy is only effective if the action value is Quarantine.</span></span> <span data-ttu-id="c31c1-321">Per visualizzare i valori delle azioni nei criteri di protezione da posta indesiderata esistenti, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="c31c1-321">To see the action values in existing anti-spam policies, run the following command:</span></span>

  ```powershell
  Get-HostedContentFilterPolicy | Format-Table Name,*SpamAction,HighConfidencePhishAction
  ```

  <span data-ttu-id="c31c1-322">Per informazioni sui valori di azione predefiniti e sui valori di azione consigliati per Standard e Strict, vedere Impostazioni dei criteri di protezione da posta indesiderata di [EOP.](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="c31c1-322">For information about the default action values and the recommended action values for Standard and Strict, see [EOP anti-spam policy settings](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings).</span></span>

- <span data-ttu-id="c31c1-323">Un verdetto di filtro della posta indesiderata senza un parametro del criterio di quarantena corrispondente indica [che](#step-2-assign-a-quarantine-policy-to-supported-features) viene utilizzato il criterio di quarantena predefinito per tale verdetto.</span><span class="sxs-lookup"><span data-stu-id="c31c1-323">A spam filtering verdict without a corresponding quarantine policy parameter means the [default quarantine policy](#step-2-assign-a-quarantine-policy-to-supported-features) for that verdict is used.</span></span>

  <span data-ttu-id="c31c1-324">È necessario sostituire un criterio di quarantena predefinito con un criterio di quarantena personalizzato solo se si desidera modificare le funzionalità predefinite dell'utente finale nei messaggi in quarantena.</span><span class="sxs-lookup"><span data-stu-id="c31c1-324">You only need to replace a default quarantine policy with a custom quarantine policy if you want to change the default end-user capabilities on quarantined messages.</span></span>

- <span data-ttu-id="c31c1-325">Un nuovo criterio di protezione da posta indesiderata in PowerShell richiede un criterio di filtro della posta indesiderata (impostazioni) utilizzando il cmdlet **New-HostedContentFilterPolicy** e una nuova regola di filtro della posta indesiderata (filtri destinatario) utilizzando il cmdlet **New-HostedContentFilterRule.**</span><span class="sxs-lookup"><span data-stu-id="c31c1-325">A new anti-spam policy in PowerShell requires a spam filter policy (settings) using the **New-HostedContentFilterPolicy** cmdlet and a new spam filter rule (recipient filters) using the **New-HostedContentFilterRule** cmdlet.</span></span> <span data-ttu-id="c31c1-326">Per istruzioni, vedere [Usare PowerShell per creare criteri di protezione da posta indesiderata.](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies)</span><span class="sxs-lookup"><span data-stu-id="c31c1-326">For instructions, see [Use PowerShell to create anti-spam policies](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies).</span></span>

<span data-ttu-id="c31c1-327">In questo esempio viene creato un nuovo criterio di filtro della posta indesiderata denominato Research Department con le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c31c1-327">This example creates a new spam filter policy named Research Department with the following settings:</span></span>

- <span data-ttu-id="c31c1-328">L'azione per tutti i verdetti del filtro posta indesiderata è impostata su Quarantena.</span><span class="sxs-lookup"><span data-stu-id="c31c1-328">The action for all spam filtering verdicts is set to Quarantine.</span></span>
- <span data-ttu-id="c31c1-329">Il criterio di quarantena personalizzato  denominato NoAccess che assegna Nessuna autorizzazione di  accesso sostituisce tutti i criteri di quarantena predefiniti che non assegnano già Autorizzazioni di accesso no per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="c31c1-329">The custom quarantine policy named NoAccess that assigns **No access** permissions replaces any default quarantine policies that don't already assign **No access** permissions by default.</span></span>

```powershell
New-HostedContentFilterPolicy -Name Research Department -SpamAction Quarantine -SpamQuarantineTag NoAccess -HighConfidenceSpamAction Quarantine -HighConfidenceSpamQuarantineTag NoAction -PhishSpamAction Quarantine -PhishQuarantineTag NoAction -BulkSpamAction Quarantine -BulkQuarantineTag NoAccess
```

<span data-ttu-id="c31c1-330">Per informazioni dettagliate su sintassi e parametri, vedere [New-HostedContentFilterPolicy](/powershell/module/exchange/new-hostedcontentfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="c31c1-330">For detailed syntax and parameter information, see [New-HostedContentFilterPolicy](/powershell/module/exchange/new-hostedcontentfilterpolicy).</span></span>

<span data-ttu-id="c31c1-331">In questo esempio viene modificato il criterio di filtro della posta indesiderata esistente denominato Human Resources.</span><span class="sxs-lookup"><span data-stu-id="c31c1-331">This example modifies the existing spam filter policy named Human Resources.</span></span> <span data-ttu-id="c31c1-332">L'azione per il verdetto della quarantena della posta indesiderata è impostata su Quarantena e viene assegnato il criterio di quarantena personalizzato denominato NoAccess.</span><span class="sxs-lookup"><span data-stu-id="c31c1-332">The action for the spam quarantine verdict is set to Quarantine, and the custom quarantine policy named NoAccess is assigned.</span></span>

```powershell
Set-HostedContentFilterPolicy -Identity "Human Resources" -SpamAction Quarantine -SpamQuarantineTag NoAccess
```

<span data-ttu-id="c31c1-333">Per informazioni dettagliate su sintassi e parametri, vedere [Set-HostedContentFilterPolicy](/powershell/module/exchange/set-hostedcontentfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="c31c1-333">For detailed syntax and parameter information, see [Set-HostedContentFilterPolicy](/powershell/module/exchange/set-hostedcontentfilterpolicy).</span></span>

## <a name="configure-global-quarantine-notification-settings-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="c31c1-334">Configurare le impostazioni globali delle notifiche di quarantena nel portale Microsoft 365 Defender globale</span><span class="sxs-lookup"><span data-stu-id="c31c1-334">Configure global quarantine notification settings in the Microsoft 365 Defender portal</span></span>

<span data-ttu-id="c31c1-335">Le impostazioni globali per i criteri di quarantena consentono di personalizzare le notifiche di posta indesiderata dell'utente finale inviate ai destinatari dei messaggi messi in quarantena.</span><span class="sxs-lookup"><span data-stu-id="c31c1-335">The global settings for quarantine policies allow you to customize the end-user spam notifications that are sent to recipients of messages that were quarantined.</span></span> <span data-ttu-id="c31c1-336">Per ulteriori informazioni su queste notifiche, vedere Notifiche di posta indesiderata [dell'utente finale.](use-spam-notifications-to-release-and-report-quarantined-messages.md)</span><span class="sxs-lookup"><span data-stu-id="c31c1-336">For more information about these notifications, see [End-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

1. <span data-ttu-id="c31c1-337">Nel portale Microsoft 365 Defender, passare a Posta **elettronica &** criteri di minaccia di collaborazione Sezione Criteri di quarantena e \>  \>  quindi \>  selezionare Criteri **di quarantena.**</span><span class="sxs-lookup"><span data-stu-id="c31c1-337">In the Microsoft 365 Defender portal, go to **Email & collaboration** \>**Threat policies** \> **Rules** section \> **Quarantine policies** and then select **Quarantine policies**.</span></span>

2. <span data-ttu-id="c31c1-338">Nella pagina **Criterio quarantena** selezionare **Impostazioni globali.**</span><span class="sxs-lookup"><span data-stu-id="c31c1-338">On the **Quarantine policy** page, select **Global settings**.</span></span>

3. <span data-ttu-id="c31c1-339">Nel riquadro **a comparsa Impostazioni notifica** quarantena visualizzato configurare alcune o tutte le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c31c1-339">In the **Quarantine notification settings** flyout that opens, configure some or all of the following settings:</span></span>

   - <span data-ttu-id="c31c1-340">**Nome visualizzato**: consente di personalizzare il nome visualizzato del mittente utilizzato nelle notifiche di posta indesiderata dell'utente finale.</span><span class="sxs-lookup"><span data-stu-id="c31c1-340">**Display name**: Customize the sender's display name that's used in end-user spam notifications.</span></span>

     <span data-ttu-id="c31c1-341">Per ogni lingua aggiunta, selezionare la lingua nella casella Seconda lingua (non fare clic sulla X) e immettere il valore di testo desiderato nella casella **Nome** visualizzato.</span><span class="sxs-lookup"><span data-stu-id="c31c1-341">For each language that you've added, select the language in the second language box (don't click on the X) and enter the text value you want in the **Display name** box.</span></span>

     <span data-ttu-id="c31c1-342">Lo screenshot seguente mostra il nome visualizzato personalizzato in una notifica di posta indesiderata dell'utente finale:</span><span class="sxs-lookup"><span data-stu-id="c31c1-342">The following screenshot shows the customized display name in an end-user spam notification:</span></span>

     ![Nome visualizzato del mittente personalizzato in una notifica di posta indesiderata dell'utente finale](../../media/quarantine-tags-esn-customization-display-name.png)

   - <span data-ttu-id="c31c1-344">**Dichiarazione di non responsabilità**: aggiungere una dichiarazione di non responsabilità personalizzata alla fine delle notifiche di posta indesiderata dell'utente finale.</span><span class="sxs-lookup"><span data-stu-id="c31c1-344">**Disclaimer**: Add a custom disclaimer to the bottom of end-user spam notifications.</span></span> <span data-ttu-id="c31c1-345">Il testo localizzato, **Una dichiarazione di** non responsabilità dell'organizzazione: viene sempre incluso per primo, seguito dal testo specificato.</span><span class="sxs-lookup"><span data-stu-id="c31c1-345">The localized text, **A disclaimer from your organization:** is always included first, followed by the text you specify.</span></span>

     <span data-ttu-id="c31c1-346">Per ogni lingua aggiunta, selezionare la lingua nella casella Seconda lingua (non fare clic sulla X) e immettere il valore di testo desiderato nella casella Dichiarazione di **non** responsabilità.</span><span class="sxs-lookup"><span data-stu-id="c31c1-346">For each language that you've added, select the language in the second language box  (don't click the X) and enter the text value you want in the **Disclaimer** box.</span></span>

     <span data-ttu-id="c31c1-347">Lo screenshot seguente mostra la dichiarazione di non responsabilità personalizzata in una notifica di posta indesiderata dell'utente finale:</span><span class="sxs-lookup"><span data-stu-id="c31c1-347">The following screenshot shows the customized disclaimer in an end-user spam notification:</span></span>

     ![Dichiarazione di non responsabilità personalizzata nella parte inferiore di una notifica di posta indesiderata dell'utente finale](../../media/quarantine-tags-esn-customization-disclaimer.png)

   - <span data-ttu-id="c31c1-349">**Scegli lingua:** le notifiche di posta indesiderata dell'utente finale sono già localizzate in base alle impostazioni della lingua del destinatario.</span><span class="sxs-lookup"><span data-stu-id="c31c1-349">**Choose language**: End-user spam notifications are already localized based on the recipient's language settings.</span></span> <span data-ttu-id="c31c1-350">È possibile specificare testo personalizzato in lingue diverse per i **valori Nome visualizzato** e Dichiarazione di **non** responsabilità.</span><span class="sxs-lookup"><span data-stu-id="c31c1-350">You can specify customized text in different languages for the **Display name** and **Disclaimer** values.</span></span>

     <span data-ttu-id="c31c1-351">Selezionare almeno una lingua dalla prima casella della lingua e quindi fare clic su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="c31c1-351">Select at least one language from the first language box and then click **Add**.</span></span> <span data-ttu-id="c31c1-352">È possibile selezionare più lingue facendo clic **su Aggiungi** dopo ognuna di essi.</span><span class="sxs-lookup"><span data-stu-id="c31c1-352">You can select multiple languages by clicking **Add** after each one.</span></span> <span data-ttu-id="c31c1-353">Una casella della lingua di sezione mostra tutte le lingue selezionate:</span><span class="sxs-lookup"><span data-stu-id="c31c1-353">A section language box shows all of the languages that you've selected:</span></span>

     ![Lingue selezionate nella seconda lingua nelle impostazioni globali di notifica quarantena dei criteri di quarantena](../../media/quarantine-tags-esn-customization-selected-languages.png)

   - <span data-ttu-id="c31c1-355">**Usa il logo dell'azienda:** selezionare questa opzione per sostituire il logo Microsoft predefinito utilizzato nella parte superiore delle notifiche di posta indesiderata dell'utente finale.</span><span class="sxs-lookup"><span data-stu-id="c31c1-355">**Use my company logo**: Select this option to replace the default Microsoft logo that's use at the top of end-user spam notifications.</span></span> <span data-ttu-id="c31c1-356">Prima di eseguire questa operazione, è necessario seguire le istruzioni in Personalizzare il tema Microsoft 365 [per](../../admin/setup/customize-your-organization-theme.md) l'organizzazione per caricare il logo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="c31c1-356">Before you do this, you need to follow the instructions in [Customize the Microsoft 365 theme for your organization](../../admin/setup/customize-your-organization-theme.md) to upload your custom logo.</span></span>

     <span data-ttu-id="c31c1-357">Lo screenshot seguente mostra un logo personalizzato in una notifica di posta indesiderata dell'utente finale:</span><span class="sxs-lookup"><span data-stu-id="c31c1-357">The following screenshot shows a custom logo in an end-user spam notification:</span></span>

     ![Logo personalizzato in una notifica di posta indesiderata dell'utente finale](../../media/quarantine-tags-esn-customization-logo.png)

## <a name="view-quarantine-policies-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="c31c1-359">Visualizzare i criteri di quarantena nel portale Microsoft 365 Defender di quarantena</span><span class="sxs-lookup"><span data-stu-id="c31c1-359">View quarantine policies in the Microsoft 365 Defender portal</span></span>

1. <span data-ttu-id="c31c1-360">Nel portale Microsoft 365 Defender, passare a Posta **elettronica &** criteri di minaccia di collaborazione Sezione Criteri di quarantena e \>  \>  quindi \>  selezionare Criteri **di quarantena.**</span><span class="sxs-lookup"><span data-stu-id="c31c1-360">In the Microsoft 365 Defender portal, go to **Email & collaboration** \>**Threat policies** \> **Rules** section \> **Quarantine policies** and then select **Quarantine policies**.</span></span>

2. <span data-ttu-id="c31c1-361">Nella **pagina Criteri di** quarantena viene visualizzato l'elenco dei criteri in base a **Nome** e Data **ultimo** aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="c31c1-361">The **Quarantine policy** page shows the list of policies by **Name** and **Last updated** date.</span></span>

3. <span data-ttu-id="c31c1-362">Per visualizzare le impostazioni dei criteri di quarantena predefiniti o personalizzati, selezionare il criterio di quarantena nell'elenco facendo clic sul nome.</span><span class="sxs-lookup"><span data-stu-id="c31c1-362">To view the settings of built-in or custom quarantine policies, select the quarantine policy from the list by clicking on the name.</span></span>

4. <span data-ttu-id="c31c1-363">Per visualizzare le impostazioni globali, fare clic su **Impostazioni globali**</span><span class="sxs-lookup"><span data-stu-id="c31c1-363">To view the global settings, click **Global settings**</span></span>

### <a name="view-quarantine-policies-in-powershell"></a><span data-ttu-id="c31c1-364">Visualizzare i criteri di quarantena in PowerShell</span><span class="sxs-lookup"><span data-stu-id="c31c1-364">View quarantine policies in PowerShell</span></span>

<span data-ttu-id="c31c1-365">Se si preferisce usare PowerShell per visualizzare i criteri di quarantena, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c31c1-365">If you'd rather use PowerShell to view quarantine policies, do any of the following steps:</span></span>

- <span data-ttu-id="c31c1-366">Per visualizzare un elenco riepilogativo di tutti i criteri predefiniti o personalizzati, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="c31c1-366">To view a summary list of all built-in or custom policies, run the following command:</span></span>

  ```powershell
  Get-QuarantineTag | Format-Table Name
  ```

- <span data-ttu-id="c31c1-367">Per visualizzare le impostazioni dei criteri di quarantena predefiniti o personalizzati, sostituire con il nome del criterio di quarantena \<QuarantinePolicyName\> ed eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="c31c1-367">To view the settings of built-in or custom quarantine policies, replace \<QuarantinePolicyName\> with the name of the quarantine policy, and run the following command:</span></span>

  ```powershell
  Get-QuarantineTag -Identity "<QuarantinePolicyName>"
  ```

- <span data-ttu-id="c31c1-368">Per visualizzare le impostazioni globali, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="c31c1-368">To view the global settings, run the following command:</span></span>

  ```powershell
  Get-QuarantineTag -QuarantineTagType GlobalQuarantineTag
  ```

<span data-ttu-id="c31c1-369">Per informazioni dettagliate su sintassi e parametri, vedere [Get-HostedContentFilterPolicy](/powershell/module/exchange/get-hostedcontentfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="c31c1-369">For detailed syntax and parameter information, see [Get-HostedContentFilterPolicy](/powershell/module/exchange/get-hostedcontentfilterpolicy).</span></span>

## <a name="modify-quarantine-policies-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="c31c1-370">Modificare i criteri di quarantena nel portale Microsoft 365 Defender di quarantena</span><span class="sxs-lookup"><span data-stu-id="c31c1-370">Modify quarantine policies in the Microsoft 365 Defender portal</span></span>

1. <span data-ttu-id="c31c1-371">Nel portale Microsoft 365 Defender, passare a Posta **elettronica &** criteri di minaccia di collaborazione Sezione Criteri di quarantena e \>  \>  quindi \>  selezionare Criteri **di quarantena.**</span><span class="sxs-lookup"><span data-stu-id="c31c1-371">In the Microsoft 365 Defender portal, go to **Email & collaboration** \>**Threat policies** \> **Rules** section \> **Quarantine policies** and then select **Quarantine policies**.</span></span>

2. <span data-ttu-id="c31c1-372">Nella pagina **Criteri di quarantena** selezionare il criterio facendo clic sul nome.</span><span class="sxs-lookup"><span data-stu-id="c31c1-372">On the **Quarantine policies** page, select the policy by clicking on the name.</span></span>

3. <span data-ttu-id="c31c1-373">Dopo aver selezionato il criterio, fare clic ![ sull'icona Modifica criterio ](../../media/m365-cc-sc-edit-icon.png) **Modifica** criterio visualizzata.</span><span class="sxs-lookup"><span data-stu-id="c31c1-373">After you select the policy, click the ![Edit policy icon](../../media/m365-cc-sc-edit-icon.png) **Edit policy** icon that appears.</span></span>

4. <span data-ttu-id="c31c1-374">La **procedura guidata** Modifica criteri visualizzata  è praticamente identica alla procedura guidata Nuovo criterio, come descritto nella sezione Creare criteri di quarantena nel portale di [Microsoft 365 Defender](#step-1-create-quarantine-policies-in-the-microsoft-365-defender-portal) in precedenza in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="c31c1-374">The **Edit policy** wizard that opens is virtually identical to the **New policy** wizard as described in the [Create quarantine policies in the Microsoft 365 Defender portal](#step-1-create-quarantine-policies-in-the-microsoft-365-defender-portal) section earlier in this article.</span></span>

   <span data-ttu-id="c31c1-375">La differenza principale è che non è possibile rinominare un criterio esistente.</span><span class="sxs-lookup"><span data-stu-id="c31c1-375">The main difference is: you can't rename an existing policy.</span></span>

5. <span data-ttu-id="c31c1-376">Dopo aver modificato il criterio, passare alla pagina **Riepilogo** e fare clic su **Invia.**</span><span class="sxs-lookup"><span data-stu-id="c31c1-376">When you're finished modifying the policy, go to the **Summary** page and click **Submit**.</span></span>

### <a name="modify-quarantine-policies-in-powershell"></a><span data-ttu-id="c31c1-377">Modificare i criteri di quarantena in PowerShell</span><span class="sxs-lookup"><span data-stu-id="c31c1-377">Modify quarantine policies in PowerShell</span></span>

<span data-ttu-id="c31c1-378">Se si preferisce utilizzare PowerShell per modificare un criterio di quarantena personalizzato, sostituire con il nome del criterio di quarantena e utilizzare \<QuarantinePolicyName\> la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="c31c1-378">If you'd rather use PowerShell to modify a custom quarantine policy, replace \<QuarantinePolicyName\> with the name of the quarantine policy, and use the following syntax:</span></span>

```powershell
Set-QuarantineTag -Identity "<QuarantinePolicyName>" [Settings]
```

<span data-ttu-id="c31c1-379">Le impostazioni disponibili sono le stesse descritte in precedenza per la creazione dei criteri di quarantena in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="c31c1-379">The available settings are the same as described for creating quarantine policies earlier in this article.</span></span>

<span data-ttu-id="c31c1-380">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-QuarantineTag.](/powershell/module/exchange/set-quarantinetag)</span><span class="sxs-lookup"><span data-stu-id="c31c1-380">For detailed syntax and parameter information, see [Set-QuarantineTag](/powershell/module/exchange/set-quarantinetag).</span></span>

## <a name="remove-quarantine-policies-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="c31c1-381">Rimuovere i criteri di quarantena nel portale Microsoft 365 Defender di quarantena</span><span class="sxs-lookup"><span data-stu-id="c31c1-381">Remove quarantine policies in the Microsoft 365 Defender portal</span></span>

<span data-ttu-id="c31c1-382">**Note**:</span><span class="sxs-lookup"><span data-stu-id="c31c1-382">**Notes**:</span></span>

- <span data-ttu-id="c31c1-383">Non è possibile rimuovere i criteri di quarantena predefiniti.</span><span class="sxs-lookup"><span data-stu-id="c31c1-383">You can't remove built-in quarantine policies.</span></span>
- <span data-ttu-id="c31c1-384">Prima di rimuovere un criterio di quarantena personalizzato, verificare che non sia in uso.</span><span class="sxs-lookup"><span data-stu-id="c31c1-384">Before you remove a custom quarantine policy, verify that it's not being used.</span></span> <span data-ttu-id="c31c1-385">Ad esempio, eseguire il comando seguente in PowerShell:</span><span class="sxs-lookup"><span data-stu-id="c31c1-385">For example, run the following command in PowerShell:</span></span>

  ```powershell
  Get-HostedContentFilterPolicy | Format-List Name,*QuarantineTag
  ```

  <span data-ttu-id="c31c1-386">Se viene utilizzato il criterio di quarantena, [sostituire il criterio di quarantena assegnato](#step-2-assign-a-quarantine-policy-to-supported-features) prima di rimuoverlo.</span><span class="sxs-lookup"><span data-stu-id="c31c1-386">If the quarantine policy is being used, [replace the assigned quarantine policy](#step-2-assign-a-quarantine-policy-to-supported-features) before you remove it.</span></span>

1. <span data-ttu-id="c31c1-387">Nel portale Microsoft 365 Defender, passare a Posta **elettronica &** criteri di minaccia di collaborazione Sezione Criteri di quarantena e \>  \>  quindi \>  selezionare Criteri **di quarantena.**</span><span class="sxs-lookup"><span data-stu-id="c31c1-387">In the Microsoft 365 Defender portal, go to **Email & collaboration** \>**Threat policies** \> **Rules** section \> **Quarantine policies** and then select **Quarantine policies**.</span></span>

2. <span data-ttu-id="c31c1-388">Nella pagina **Criterio quarantena** selezionare il criterio di quarantena personalizzato che si desidera rimuovere facendo clic sul nome.</span><span class="sxs-lookup"><span data-stu-id="c31c1-388">On the **Quarantine policy** page, select the custom quarantine policy that you want to remove by clicking on the name.</span></span>

3. <span data-ttu-id="c31c1-389">Dopo aver selezionato il criterio, fare clic sull'icona Elimina criterio ![ ](../../media/m365-cc-sc-delete-icon.png) **Icona** Elimina criterio visualizzata.</span><span class="sxs-lookup"><span data-stu-id="c31c1-389">After you select the policy, click the ![Delete policy icon](../../media/m365-cc-sc-delete-icon.png) **Delete policy** icon that appears.</span></span>

4. <span data-ttu-id="c31c1-390">Fare **clic su Rimuovi** criterio nella finestra di dialogo di conferma visualizzata.</span><span class="sxs-lookup"><span data-stu-id="c31c1-390">Click **Remove policy** in the confirmation dialog that appears.</span></span>

### <a name="remove-quarantine-policies-in-powershell"></a><span data-ttu-id="c31c1-391">Rimuovere i criteri di quarantena in PowerShell</span><span class="sxs-lookup"><span data-stu-id="c31c1-391">Remove quarantine policies in PowerShell</span></span>

<span data-ttu-id="c31c1-392">Se si preferisce utilizzare PowerShell per rimuovere un criterio di quarantena personalizzato, sostituire con il nome del criterio di quarantena \<QuarantinePolicyName\> ed eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="c31c1-392">If you'd rather use PowerShell to remove a custom quarantine policy, replace \<QuarantinePolicyName\> with the name of the quarantine policy, and run the following command:</span></span>

```powershell
Remove-QuarantineTag -Identity "<QuarantinePolicyName>"
```

<span data-ttu-id="c31c1-393">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Remove-QuarantineTag.](/powershell/module/exchange/remove-quarantinetag)</span><span class="sxs-lookup"><span data-stu-id="c31c1-393">For detailed syntax and parameter information, see [Remove-QuarantineTag](/powershell/module/exchange/remove-quarantinetag).</span></span>

## <a name="quarantine-policy-permission-details"></a><span data-ttu-id="c31c1-394">Dettagli sulle autorizzazioni dei criteri di quarantena</span><span class="sxs-lookup"><span data-stu-id="c31c1-394">Quarantine policy permission details</span></span>

<span data-ttu-id="c31c1-395">Nelle sezioni seguenti vengono descritti gli effetti dei gruppi di autorizzazioni preimpostati e delle singole autorizzazioni nei dettagli dei messaggi in quarantena e nelle notifiche di posta indesiderata dell'utente finale.</span><span class="sxs-lookup"><span data-stu-id="c31c1-395">The following sections describe the effects of preset permission groups and individual permissions in the details of quarantined messages and in end-user spam notifications.</span></span>

### <a name="preset-permissions-groups"></a><span data-ttu-id="c31c1-396">Gruppi di autorizzazioni preimpostati</span><span class="sxs-lookup"><span data-stu-id="c31c1-396">Preset permissions groups</span></span>

<span data-ttu-id="c31c1-397">Le singole autorizzazioni incluse nei gruppi di autorizzazioni preimpostati sono elencate nella tabella all'inizio di questo articolo.</span><span class="sxs-lookup"><span data-stu-id="c31c1-397">The individual permissions that are included in preset permission groups are listed in the table at the beginning of this article.</span></span>

#### <a name="no-access"></a><span data-ttu-id="c31c1-398">Nessun diritto di accesso</span><span class="sxs-lookup"><span data-stu-id="c31c1-398">No access</span></span>

<span data-ttu-id="c31c1-399">Se il criterio di quarantena assegna le **autorizzazioni Nessun accesso** (nessuna autorizzazione), gli utenti ottengono comunque alcune funzionalità di base:</span><span class="sxs-lookup"><span data-stu-id="c31c1-399">If the quarantine policy assigns the **No access** permissions (no permissions), users still get some baseline capabilities:</span></span>

- <span data-ttu-id="c31c1-400">**Dettagli messaggio in quarantena**: il **pulsante Visualizza intestazione messaggio** è sempre disponibile.</span><span class="sxs-lookup"><span data-stu-id="c31c1-400">**Quarantined message details**: The **View message header** button is always available.</span></span>

  ![Pulsanti disponibili nei dettagli del messaggio in quarantena se il criterio di quarantena concede all'utente autorizzazioni di accesso no](../../media/quarantine-tags-quarantined-message-details-no-access.png)

- <span data-ttu-id="c31c1-402">**Notifiche di posta indesiderata dell'utente** finale : il **pulsante** Revisione che porta l'utente al messaggio in quarantena è sempre disponibile.</span><span class="sxs-lookup"><span data-stu-id="c31c1-402">**End-user spam notifications**: The **Review** button that takes the user to the message in quarantine is always available.</span></span>

  ![Pulsanti disponibili nella notifica di posta indesiderata dell'utente finale se il criterio di quarantena concede all'utente autorizzazioni di accesso no](../../media/quarantine-tags-esn-no-access.png)

#### <a name="limited-access"></a><span data-ttu-id="c31c1-404">Accesso limitato</span><span class="sxs-lookup"><span data-stu-id="c31c1-404">Limited access</span></span>

<span data-ttu-id="c31c1-405">Se il criterio di quarantena assegna le **autorizzazioni accesso** limitato, gli utenti ottengono le funzionalità seguenti:</span><span class="sxs-lookup"><span data-stu-id="c31c1-405">If the quarantine policy assigns the **Limited access** permissions, users get the following capabilities:</span></span>

- <span data-ttu-id="c31c1-406">**Dettagli messaggio in quarantena**: Sono disponibili i pulsanti seguenti:</span><span class="sxs-lookup"><span data-stu-id="c31c1-406">**Quarantined message details**: The following buttons are available:</span></span>
  - <span data-ttu-id="c31c1-407">**Richiesta di rilascio**</span><span class="sxs-lookup"><span data-stu-id="c31c1-407">**Request release**</span></span>
  - <span data-ttu-id="c31c1-408">**Visualizzazione delle intestazioni del messaggio**</span><span class="sxs-lookup"><span data-stu-id="c31c1-408">**View message header**</span></span>
  - <span data-ttu-id="c31c1-409">**Messaggio di anteprima**</span><span class="sxs-lookup"><span data-stu-id="c31c1-409">**Preview message**</span></span>
  - <span data-ttu-id="c31c1-410">**Blocca mittente**</span><span class="sxs-lookup"><span data-stu-id="c31c1-410">**Block sender**</span></span>
  - <span data-ttu-id="c31c1-411">**Rimuovi dalla quarantena**</span><span class="sxs-lookup"><span data-stu-id="c31c1-411">**Remove from quarantine**</span></span>

  ![Pulsanti disponibili nei dettagli del messaggio in quarantena se il criterio di quarantena concede all'utente autorizzazioni di accesso limitato](../../media/quarantine-tags-quarantined-message-details-limited-access.png)

- <span data-ttu-id="c31c1-413">**Notifiche di posta indesiderata dell'utente finale**: sono disponibili i pulsanti seguenti:</span><span class="sxs-lookup"><span data-stu-id="c31c1-413">**End-user spam notifications**: The following buttons are available:</span></span>
  - <span data-ttu-id="c31c1-414">**Blocca mittente**</span><span class="sxs-lookup"><span data-stu-id="c31c1-414">**Block sender**</span></span>
  - <span data-ttu-id="c31c1-415">**Verifica**</span><span class="sxs-lookup"><span data-stu-id="c31c1-415">**Review**</span></span>

  ![Pulsanti disponibili nella notifica di posta indesiderata dell'utente finale se il criterio di quarantena concede all'utente autorizzazioni di accesso limitato](../../media/quarantine-tags-esn-limited-access.png)

#### <a name="full-access"></a><span data-ttu-id="c31c1-417">Accesso completo</span><span class="sxs-lookup"><span data-stu-id="c31c1-417">Full access</span></span>

<span data-ttu-id="c31c1-418">Se il criterio di quarantena assegna le **autorizzazioni di accesso** completo (tutte le autorizzazioni disponibili), gli utenti ottengono le funzionalità seguenti:</span><span class="sxs-lookup"><span data-stu-id="c31c1-418">If the quarantine policy assigns the **Full access** permissions (all available permissions), users get the following capabilities:</span></span>

- <span data-ttu-id="c31c1-419">**Dettagli messaggio in quarantena**: Sono disponibili i pulsanti seguenti:</span><span class="sxs-lookup"><span data-stu-id="c31c1-419">**Quarantined message details**: The following buttons are available:</span></span>
  - <span data-ttu-id="c31c1-420">**Messaggio di rilascio**</span><span class="sxs-lookup"><span data-stu-id="c31c1-420">**Release message**</span></span>
  - <span data-ttu-id="c31c1-421">**Visualizzazione delle intestazioni del messaggio**</span><span class="sxs-lookup"><span data-stu-id="c31c1-421">**View message header**</span></span>
  - <span data-ttu-id="c31c1-422">**Messaggio di anteprima**</span><span class="sxs-lookup"><span data-stu-id="c31c1-422">**Preview message**</span></span>
  - <span data-ttu-id="c31c1-423">**Blocca mittente**</span><span class="sxs-lookup"><span data-stu-id="c31c1-423">**Block sender**</span></span>
  - <span data-ttu-id="c31c1-424">**Consenti mittente**</span><span class="sxs-lookup"><span data-stu-id="c31c1-424">**Allow sender**</span></span>
  - <span data-ttu-id="c31c1-425">**Rimuovi dalla quarantena**</span><span class="sxs-lookup"><span data-stu-id="c31c1-425">**Remove from quarantine**</span></span>

  ![Pulsanti disponibili nei dettagli del messaggio in quarantena se il criterio di quarantena concede all'utente autorizzazioni di accesso completo](../../media/quarantine-tags-quarantined-message-details-full-access.png)

- <span data-ttu-id="c31c1-427">**Notifiche di posta indesiderata dell'utente finale**: sono disponibili i pulsanti seguenti:</span><span class="sxs-lookup"><span data-stu-id="c31c1-427">**End-user spam notifications**: The following buttons are available:</span></span>
  - <span data-ttu-id="c31c1-428">**Blocca mittente**</span><span class="sxs-lookup"><span data-stu-id="c31c1-428">**Block sender**</span></span>
  - <span data-ttu-id="c31c1-429">**Rilascia**</span><span class="sxs-lookup"><span data-stu-id="c31c1-429">**Release**</span></span>
  - <span data-ttu-id="c31c1-430">**Verifica**</span><span class="sxs-lookup"><span data-stu-id="c31c1-430">**Review**</span></span>

  ![Pulsanti disponibili nella notifica di posta indesiderata dell'utente finale se il criterio di quarantena concede all'utente autorizzazioni di accesso completo](../../media/quarantine-tags-esn-full-access.png)

### <a name="individual-permissions"></a><span data-ttu-id="c31c1-432">Autorizzazioni individuali</span><span class="sxs-lookup"><span data-stu-id="c31c1-432">Individual permissions</span></span>

> [!NOTE]
> <span data-ttu-id="c31c1-433">Tenere presente che gli utenti ottengono sempre i pulsanti descritti nella [sezione Nessun](#no-access) accesso.</span><span class="sxs-lookup"><span data-stu-id="c31c1-433">Remember, users always get the buttons described in the [No access](#no-access) section.</span></span> <span data-ttu-id="c31c1-434">Questi pulsanti non sono inclusi nelle descrizioni delle singole autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="c31c1-434">These buttons are not included in the individual permission descriptions.</span></span>

#### <a name="allow-sender-permission"></a><span data-ttu-id="c31c1-435">Consenti autorizzazione mittente</span><span class="sxs-lookup"><span data-stu-id="c31c1-435">Allow sender permission</span></span>

<span data-ttu-id="c31c1-436">**L'autorizzazione** Consenti mittente (_PermissionToAllowSender_) controlla l'accesso al pulsante che consente agli utenti di aggiungere comodamente il mittente del messaggio in quarantena al Cassaforte Mittenti.</span><span class="sxs-lookup"><span data-stu-id="c31c1-436">The **Allow sender** permission (_PermissionToAllowSender_) controls access to the button that allows users to conveniently add the quarantined message sender to their Safe Senders list.</span></span>

- <span data-ttu-id="c31c1-437">**Dettagli messaggio in quarantena**:</span><span class="sxs-lookup"><span data-stu-id="c31c1-437">**Quarantined message details**:</span></span>
  - <span data-ttu-id="c31c1-438">**Autorizzazione Consenti mittente** abilitata: il pulsante Consenti **mittente** è disponibile.</span><span class="sxs-lookup"><span data-stu-id="c31c1-438">**Allow sender** permission enabled: The **Allow sender** button is available.</span></span>
  - <span data-ttu-id="c31c1-439">**Consenti autorizzazione mittente** disabilitata: il **pulsante** Consenti mittente non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="c31c1-439">**Allow sender** permission disabled: The **Allow sender** button is not available.</span></span>

- <span data-ttu-id="c31c1-440">**Notifiche di posta indesiderata dell'utente finale**: Nessun effetto.</span><span class="sxs-lookup"><span data-stu-id="c31c1-440">**End-user spam notifications**: No effect.</span></span>

<span data-ttu-id="c31c1-441">Per ulteriori informazioni sull'elenco dei mittenti Cassaforte, vedere [Prevent trusted senders from being blocked](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379666) e Use Exchange Online [PowerShell to configure the safelist collection on a mailbox.](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox)</span><span class="sxs-lookup"><span data-stu-id="c31c1-441">For more information about the Safe Senders list, see [Prevent trusted senders from being blocked](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379666) and [Use Exchange Online PowerShell to configure the safelist collection on a mailbox](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span></span>

#### <a name="block-sender-permission"></a><span data-ttu-id="c31c1-442">Blocca autorizzazione mittente</span><span class="sxs-lookup"><span data-stu-id="c31c1-442">Block sender permission</span></span>

<span data-ttu-id="c31c1-443">**L'autorizzazione** Blocca mittente (_PermissionToBlockSender_) controlla l'accesso al pulsante che consente agli utenti di aggiungere comodamente il mittente del messaggio in quarantena all'elenco Mittenti bloccati.</span><span class="sxs-lookup"><span data-stu-id="c31c1-443">The **Block sender** permission (_PermissionToBlockSender_) controls access to the button that allows users to conveniently add the quarantined message sender to their Blocked Senders list.</span></span>

- <span data-ttu-id="c31c1-444">**Dettagli messaggio in quarantena**:</span><span class="sxs-lookup"><span data-stu-id="c31c1-444">**Quarantined message details**:</span></span>
  - <span data-ttu-id="c31c1-445">**Autorizzazione Blocca mittente** abilitata: il pulsante Blocca **mittente** è disponibile.</span><span class="sxs-lookup"><span data-stu-id="c31c1-445">**Block sender** permission enabled: The **Block sender** button is available.</span></span>
  - <span data-ttu-id="c31c1-446">**Autorizzazione Blocca mittente** disabilitata: il **pulsante** Blocca mittente non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="c31c1-446">**Block sender** permission disabled: The **Block sender** button is not available.</span></span>

- <span data-ttu-id="c31c1-447">**Notifiche di posta indesiderata dell'utente finale**:</span><span class="sxs-lookup"><span data-stu-id="c31c1-447">**End-user spam notifications**:</span></span>
  - <span data-ttu-id="c31c1-448">**Autorizzazione Blocca mittente** disabilitata: il **pulsante** Blocca mittente non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="c31c1-448">**Block sender** permission disabled: The **Block sender** button is not available.</span></span>
  - <span data-ttu-id="c31c1-449">**Autorizzazione Blocca mittente** abilitata: il pulsante Blocca **mittente** è disponibile.</span><span class="sxs-lookup"><span data-stu-id="c31c1-449">**Block sender** permission enabled: The **Block sender** button is available.</span></span>

<span data-ttu-id="c31c1-450">Per ulteriori informazioni sull'elenco Mittenti bloccati, vedere [Block messages from someone](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667) e Use Exchange Online [PowerShell to configure the safelist collection on a mailbox.](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox)</span><span class="sxs-lookup"><span data-stu-id="c31c1-450">For more information about the Blocked Senders list, see [Block messages from someone](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667) and [Use Exchange Online PowerShell to configure the safelist collection on a mailbox](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span></span>

#### <a name="delete-permission"></a><span data-ttu-id="c31c1-451">Autorizzazione di eliminazione</span><span class="sxs-lookup"><span data-stu-id="c31c1-451">Delete permission</span></span>

<span data-ttu-id="c31c1-452">**L'autorizzazione** Delete (_PermissionToDelete_) controlla la possibilità per gli utenti di eliminare i propri messaggi (messaggi in cui l'utente è un destinatario) dalla quarantena.</span><span class="sxs-lookup"><span data-stu-id="c31c1-452">The **Delete** permission (_PermissionToDelete_) controls the ability to of users to delete their messages (messages where the user is a recipient) from quarantine.</span></span>

- <span data-ttu-id="c31c1-453">**Dettagli messaggio in quarantena**:</span><span class="sxs-lookup"><span data-stu-id="c31c1-453">**Quarantined message details**:</span></span>
  - <span data-ttu-id="c31c1-454">**Autorizzazione** di eliminazione abilitata: **il pulsante Rimuovi dalla** quarantena è disponibile.</span><span class="sxs-lookup"><span data-stu-id="c31c1-454">**Delete** permission enabled: The **Remove from quarantine** button is available.</span></span>
  - <span data-ttu-id="c31c1-455">**Autorizzazione** di eliminazione disabilitata: **il pulsante Rimuovi dalla** quarantena non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="c31c1-455">**Delete** permission disabled: The **Remove from quarantine** button is not available.</span></span>

- <span data-ttu-id="c31c1-456">**Notifiche di posta indesiderata dell'utente finale**: Nessun effetto.</span><span class="sxs-lookup"><span data-stu-id="c31c1-456">**End-user spam notifications**: No effect.</span></span>

#### <a name="preview-permission"></a><span data-ttu-id="c31c1-457">Autorizzazione anteprima</span><span class="sxs-lookup"><span data-stu-id="c31c1-457">Preview permission</span></span>

<span data-ttu-id="c31c1-458">**L'autorizzazione** Anteprima (_PermissionToPreview_) controlla la possibilità per gli utenti di visualizzare in anteprima i messaggi in quarantena.</span><span class="sxs-lookup"><span data-stu-id="c31c1-458">The **Preview** permission (_PermissionToPreview_) controls the ability to of users to preview their messages in quarantine.</span></span>

- <span data-ttu-id="c31c1-459">**Dettagli messaggio in quarantena**:</span><span class="sxs-lookup"><span data-stu-id="c31c1-459">**Quarantined message details**:</span></span>
  - <span data-ttu-id="c31c1-460">**Autorizzazione anteprima** abilitata: il **pulsante Anteprima** messaggio è disponibile.</span><span class="sxs-lookup"><span data-stu-id="c31c1-460">**Preview** permission enabled: The **Preview message** button is available.</span></span>
  - <span data-ttu-id="c31c1-461">**Autorizzazione anteprima** disabilitata: il **pulsante Anteprima** messaggio non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="c31c1-461">**Preview** permission disabled: The **Preview message** button is not available.</span></span>

- <span data-ttu-id="c31c1-462">**Notifiche di posta indesiderata dell'utente finale**: Nessun effetto.</span><span class="sxs-lookup"><span data-stu-id="c31c1-462">**End-user spam notifications**: No effect.</span></span>

#### <a name="allow-recipients-to-release-a-message-from-quarantine-permission"></a><span data-ttu-id="c31c1-463">Consentire ai destinatari di rilasciare un messaggio dall'autorizzazione di quarantena</span><span class="sxs-lookup"><span data-stu-id="c31c1-463">Allow recipients to release a message from quarantine permission</span></span>

<span data-ttu-id="c31c1-464">**L'autorizzazione** Consenti ai destinatari di rilasciare un messaggio dalla quarantena (_PermissionToRelease_) controlla la possibilità degli utenti di rilasciare i messaggi in quarantena direttamente e senza l'approvazione di un amministratore.</span><span class="sxs-lookup"><span data-stu-id="c31c1-464">The **Allow recipients to release a message from quarantine** permission (_PermissionToRelease_) controls the ability of users to release their quarantined messages directly and without the approval of an admin.</span></span>

- <span data-ttu-id="c31c1-465">**Dettagli messaggio in quarantena**:</span><span class="sxs-lookup"><span data-stu-id="c31c1-465">**Quarantined message details**:</span></span>
  - <span data-ttu-id="c31c1-466">Autorizzazione abilitata: il **pulsante Rilascia** messaggio è disponibile.</span><span class="sxs-lookup"><span data-stu-id="c31c1-466">Permission enabled: The **Release message** button is available.</span></span>
  - <span data-ttu-id="c31c1-467">Autorizzazione disabilitata: il **pulsante Rilascia** messaggio non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="c31c1-467">Permission disabled: The **Release message** button is not available.</span></span>

- <span data-ttu-id="c31c1-468">**Notifiche di posta indesiderata dell'utente finale**:</span><span class="sxs-lookup"><span data-stu-id="c31c1-468">**End-user spam notifications**:</span></span>
  - <span data-ttu-id="c31c1-469">Autorizzazione abilitata: il **pulsante Rilascia** è disponibile.</span><span class="sxs-lookup"><span data-stu-id="c31c1-469">Permission enabled: The **Release** button is available.</span></span>
  - <span data-ttu-id="c31c1-470">Autorizzazione disabilitata: **il pulsante** Rilascia non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="c31c1-470">Permission disabled: The **Release** button is not available.</span></span>

#### <a name="allow-recipients-to-request-a-message-to-be-released-from-quarantine-permission"></a><span data-ttu-id="c31c1-471">Consentire ai destinatari di richiedere il rilascio di un messaggio dall'autorizzazione di quarantena</span><span class="sxs-lookup"><span data-stu-id="c31c1-471">Allow recipients to request a message to be released from quarantine permission</span></span>

<span data-ttu-id="c31c1-472">**L'autorizzazione** Consenti ai destinatari di richiedere il rilascio di un messaggio dalla quarantena  (_PermissionToRequestRelease_) controlla la capacità degli utenti di richiedere il rilascio dei messaggi in quarantena.</span><span class="sxs-lookup"><span data-stu-id="c31c1-472">The **Allow recipients to request a message to be released from quarantine** permission (_PermissionToRequestRelease_) controls the ability of users to _request_ the release of their quarantined messages.</span></span> <span data-ttu-id="c31c1-473">Il messaggio viene rilasciato solo dopo che un amministratore approva la richiesta.</span><span class="sxs-lookup"><span data-stu-id="c31c1-473">The message is only released after an admin approves the request.</span></span>

- <span data-ttu-id="c31c1-474">**Dettagli messaggio in quarantena**:</span><span class="sxs-lookup"><span data-stu-id="c31c1-474">**Quarantined message details**:</span></span>
  - <span data-ttu-id="c31c1-475">Autorizzazione abilitata: **il pulsante Richiedi** rilascio è disponibile.</span><span class="sxs-lookup"><span data-stu-id="c31c1-475">Permission enabled: The **Request release** button is available.</span></span>
  - <span data-ttu-id="c31c1-476">Autorizzazione disabilitata: **il pulsante Richiedi** rilascio non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="c31c1-476">Permission disabled: The **Request release** button is not available.</span></span>

- <span data-ttu-id="c31c1-477">**Notifiche di posta indesiderata dell'utente finale**: **il pulsante** Rilascia non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="c31c1-477">**End-user spam notifications**: The **Release** button is not available.</span></span>
