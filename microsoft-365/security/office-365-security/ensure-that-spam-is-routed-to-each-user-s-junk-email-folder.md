---
title: Configurare EOP per la posta indesiderata in ambienti ibridi
f1.keywords:
- NOCSH
ms.author: chrisda
author: MSFTTracyP
manager: chrisda
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0cbaccf8-4afc-47e3-a36d-a84598a55fb8
ms.collection:
- M365-security-compliance
description: Gli amministratori possono imparare a instradare la posta indesiderata alle cartelle posta indesiderata degli utenti in un ambiente ibrido di Exchange Online Protection.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1d5d83f8cfb994499be98eccf77b36d83e1f3d7c
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/23/2020
ms.locfileid: "44351964"
---
# <a name="configure-standalone-eop-to-deliver-spam-to-the-junk-email-folder-in-hybrid-environments"></a><span data-ttu-id="e7af2-103">Configurare EOP autonomo per recapitare la posta indesiderata nella cartella posta indesiderata in ambienti ibridi</span><span class="sxs-lookup"><span data-stu-id="e7af2-103">Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e7af2-104">Questo argomento è solo per i clienti di EOP autonomi in ambienti ibridi.</span><span class="sxs-lookup"><span data-stu-id="e7af2-104">This topic is only for standalone EOP customers in hybrid environments.</span></span> <span data-ttu-id="e7af2-105">Questo argomento non si applica ai clienti Microsoft 365 con cassette postali di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e7af2-105">This topic does not apply to Microsoft 365 customers with Exchange Online mailboxes.</span></span>

<span data-ttu-id="e7af2-106">Se si è un cliente autonomo di Exchange Online Protection (EOP) in un ambiente ibrido, è necessario configurare l'organizzazione di Exchange locale per riconoscere e tradurre i verdetti del filtro della posta indesiderata di EOP, in modo che la regola di posta indesiderata nella cassetta postale locale possa spostare i messaggi nella cartella posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="e7af2-106">If you're a standalone Exchange Online Protection (EOP) customer in a hybrid environment, you need to configure your on-premises Exchange organization to recognize and translate the spam filtering verdicts of EOP, so the junk email rule in the on-premises mailbox can move messages to the Junk Email folder.</span></span>

<span data-ttu-id="e7af2-107">In particolare, è necessario creare regole del flusso di posta (note anche come regole di trasporto) nell'organizzazione di Exchange locale con condizioni che consentono di trovare messaggi con uno dei seguenti valori e intestazioni di protezione da posta indesiderata di EOP e le azioni che configurano il livello di probabilità di posta indesiderata (SCL) di tali messaggi su 6:</span><span class="sxs-lookup"><span data-stu-id="e7af2-107">Specifically, you need to create mail flow rules (also known as transport rules) in your on-premises Exchange organization with conditions that find messages with any of the following EOP anti-spam headers and values, and actions that set the spam confidence level (SCL) of those messages to 6:</span></span>

- <span data-ttu-id="e7af2-108">`X-Forefront-Antispam-Report: SFV:SPM`(messaggio contrassegnato come posta indesiderata dal filtro posta indesiderata)</span><span class="sxs-lookup"><span data-stu-id="e7af2-108">`X-Forefront-Antispam-Report: SFV:SPM` (message marked as spam by spam filtering)</span></span>

- <span data-ttu-id="e7af2-109">`X-Forefront-Antispam-Report: SFV:SKS`messaggio contrassegnato come posta indesiderata dalle regole del flusso di posta in EOP prima del filtro posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="e7af2-109">`X-Forefront-Antispam-Report: SFV:SKS` (message marked as spam by mail flow rules in EOP before spam filtering)</span></span>

- <span data-ttu-id="e7af2-110">`X-Forefront-Antispam-Report: SFV:SKB`(messaggio contrassegnato come posta indesiderata dal filtro posta indesiderata a causa dell'indirizzo di posta elettronica o del dominio di posta elettronica del mittente nell'elenco dei mittenti bloccati o nell'elenco dei domini bloccati in EOP)</span><span class="sxs-lookup"><span data-stu-id="e7af2-110">`X-Forefront-Antispam-Report: SFV:SKB` (message marked as spam by spam filtering due to the sender's email address or email domain being in the blocked sender list or the blocked domain list in EOP)</span></span>

<span data-ttu-id="e7af2-111">Per ulteriori informazioni su questi valori di intestazione, vedere intestazioni dei messaggi di protezione da [posta indesiderata](anti-spam-message-headers.md).</span><span class="sxs-lookup"><span data-stu-id="e7af2-111">For more information about these header values, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>

<span data-ttu-id="e7af2-112">In questo argomento viene descritto come creare queste regole del flusso di posta dell'interfaccia di amministrazione di Exchange (EAC) e in Exchange Management Shell (Exchange PowerShell) nell'organizzazione di Exchange locale.</span><span class="sxs-lookup"><span data-stu-id="e7af2-112">This topic describes how to create these mail flow rules the Exchange admin center (EAC) and in the Exchange Management Shell (Exchange PowerShell) in the on-premises Exchange organization.</span></span>

> [!TIP]
> <span data-ttu-id="e7af2-113">Invece di inviare i messaggi alla cartella posta indesiderata dell'utente locale, è possibile configurare i criteri di protezione dalla posta indesiderata in EOP per la quarantena dei messaggi di posta indesiderata in EOP.</span><span class="sxs-lookup"><span data-stu-id="e7af2-113">Instead of delivering the messages to the on-premises user's Junk Email folder, you can configure anti-spam policies in EOP to quarantine spam messages in EOP.</span></span> <span data-ttu-id="e7af2-114">Per altre informazioni, vedere [Configurare i criteri di protezione dalla posta indesiderata in EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="e7af2-114">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e7af2-115">Che cosa è necessario sapere prima di iniziare?</span><span class="sxs-lookup"><span data-stu-id="e7af2-115">What do you need to know before you begin?</span></span>

- <span data-ttu-id="e7af2-116">Prima di poter eseguire queste procedure, è necessario disporre delle autorizzazioni nell'ambiente di Exchange locale.</span><span class="sxs-lookup"><span data-stu-id="e7af2-116">You need to be assigned permissions in the on-premises Exchange environment before you can do these procedures.</span></span> <span data-ttu-id="e7af2-117">In particolare, è necessario che venga assegnato il ruolo **regole di trasporto** , assegnato ai ruoli Gestione **organizzazione**, **Gestione conformità**e **record** per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="e7af2-117">Specifically, you need to be assigned the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management**, and **Records Management** roles by default.</span></span> <span data-ttu-id="e7af2-118">Per ulteriori informazioni, vedere [Add members to a role group](https://docs.microsoft.com/Exchange/permissions/role-group-members?view=exchserver-2019#add-members-to-a-role-group).</span><span class="sxs-lookup"><span data-stu-id="e7af2-118">For more information, see [Add members to a role group](https://docs.microsoft.com/Exchange/permissions/role-group-members?view=exchserver-2019#add-members-to-a-role-group).</span></span>

- <span data-ttu-id="e7af2-119">Se e quando un messaggio viene recapitato nella cartella posta indesiderata in un'organizzazione di Exchange locale, è controllato da una combinazione delle seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="e7af2-119">If and when a message is delivered to the Junk Email folder in an on-premises Exchange organization is controlled by a combination of the following settings:</span></span>

  - <span data-ttu-id="e7af2-120">Il valore del parametro _SCLJunkThreshold_ nel cmdlet [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig) in Exchange Management Shell.</span><span class="sxs-lookup"><span data-stu-id="e7af2-120">The _SCLJunkThreshold_ parameter value on the [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig) cmdlet in the Exchange Management Shell.</span></span> <span data-ttu-id="e7af2-121">Il valore predefinito è 4, il che significa che un SCL di 5 o superiore deve recapitare il messaggio alla cartella posta indesiderata dell'utente.</span><span class="sxs-lookup"><span data-stu-id="e7af2-121">The default value is 4, which means an SCL of 5 or higher should deliver the message to the user's Junk email folder.</span></span>

  - <span data-ttu-id="e7af2-122">Il valore del parametro _SCLJunkThreshold_ nel cmdlet [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/set-mailbox) in Exchange Management Shell.</span><span class="sxs-lookup"><span data-stu-id="e7af2-122">The _SCLJunkThreshold_ parameter value on the [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/set-mailbox) cmdlet in the Exchange Management Shell.</span></span> <span data-ttu-id="e7af2-123">Il valore predefinito è vuoto ($null), che indica che viene utilizzata l'impostazione dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e7af2-123">The default value is blank ($null), which means the organization setting is used.</span></span>

  <span data-ttu-id="e7af2-124">Per ulteriori informazioni, vedere [soglie del livello di probabilità di posta indesiderata (SCL) di Exchange](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/scl).</span><span class="sxs-lookup"><span data-stu-id="e7af2-124">For details, see [Exchange spam confidence level (SCL) thresholds](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/scl).</span></span>

  - <span data-ttu-id="e7af2-125">Se la regola di posta indesiderata è abilitata per la cassetta postale (il valore del parametro _Enabled_ è $true sul cmdlet [Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration) in Exchange Management Shell).</span><span class="sxs-lookup"><span data-stu-id="e7af2-125">Whether the junk email rule is enabled on the mailbox (the _Enabled_ parameter value is $true on the [Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration) cmdlet in the Exchange Management Shell).</span></span> <span data-ttu-id="e7af2-126">È la regola di posta indesiderata che in realtà sposta il messaggio nella cartella posta indesiderata dopo il recapito.</span><span class="sxs-lookup"><span data-stu-id="e7af2-126">It's the junk email rule that actually moves the message to the Junk Email folder after delivery.</span></span> <span data-ttu-id="e7af2-127">Per impostazione predefinita, la regola di posta indesiderata è abilitata sulle cassette postali.</span><span class="sxs-lookup"><span data-stu-id="e7af2-127">By default, the junk email rule is enabled on mailboxes.</span></span> <span data-ttu-id="e7af2-128">Per ulteriori informazioni, vedere [Configure Exchange antispam settings on mailboxes](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings).</span><span class="sxs-lookup"><span data-stu-id="e7af2-128">For more information, see [Configure Exchange antispam settings on mailboxes](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings).</span></span>
  
- <span data-ttu-id="e7af2-129">Per aprire EAC su un server Exchange, vedere interfaccia [di amministrazione di Exchange in Exchange Server](https://docs.microsoft.com/Exchange/architecture/client-access/exchange-admin-center).</span><span class="sxs-lookup"><span data-stu-id="e7af2-129">To open the EAC on an Exchange Server, see [Exchange admin center in Exchange Server](https://docs.microsoft.com/Exchange/architecture/client-access/exchange-admin-center).</span></span> <span data-ttu-id="e7af2-130">Per aprire Exchange Management Shell, vedere [https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell) .</span><span class="sxs-lookup"><span data-stu-id="e7af2-130">To open the Exchange Management Shell, see [https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell).</span></span>

- <span data-ttu-id="e7af2-131">Per ulteriori informazioni sulle regole del flusso di posta in Exchange locale, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="e7af2-131">For more information about mail flow rules in on-premises Exchange, see the following topics:</span></span>

  - [<span data-ttu-id="e7af2-132">Regole del flusso di posta in Exchange Server</span><span class="sxs-lookup"><span data-stu-id="e7af2-132">Mail flow rules in Exchange Server</span></span>](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="e7af2-133">Condizioni ed eccezioni della regola del flusso di posta (predicati) in Exchange Server</span><span class="sxs-lookup"><span data-stu-id="e7af2-133">Mail flow rule conditions and exceptions (predicates) in Exchange Server</span></span>](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="e7af2-134">Azioni delle regole del flusso di posta in Exchange Server</span><span class="sxs-lookup"><span data-stu-id="e7af2-134">Mail flow rule actions in Exchange Server</span></span>](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/actions)

## <a name="use-the-eac-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a><span data-ttu-id="e7af2-135">Utilizzare EAC per creare regole del flusso di posta che configurano il SCL dei messaggi di posta indesiderata di EOP</span><span class="sxs-lookup"><span data-stu-id="e7af2-135">Use the EAC to create mail flow rules that set the SCL of EOP spam messages</span></span>

1. <span data-ttu-id="e7af2-136">Nell'interfaccia di amministrazione di Exchange, andare a **Flusso di posta** \> **Regole**.</span><span class="sxs-lookup"><span data-stu-id="e7af2-136">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="e7af2-137">Fare clic su **Aggiungi** ![ icona ](../../media/ITPro-EAC-AddIcon.png) e selezionare **Crea una nuova regola** nell'elenco a discesa che viene visualizzato.</span><span class="sxs-lookup"><span data-stu-id="e7af2-137">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and select **Create a new rule** in the drop-down that appears.</span></span>

3. <span data-ttu-id="e7af2-138">Nella pagina **Nuova regola** che si apre, configurare le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="e7af2-138">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="e7af2-139">**Nome**: immettere un nome univoco descrittivo per la regola.</span><span class="sxs-lookup"><span data-stu-id="e7af2-139">**Name**: Enter a unique, descriptive name for the rule.</span></span> <span data-ttu-id="e7af2-140">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e7af2-140">For example:</span></span>

     - <span data-ttu-id="e7af2-141">EOP SFV: SPM a SCL 6</span><span class="sxs-lookup"><span data-stu-id="e7af2-141">EOP SFV:SPM to SCL 6</span></span>

     - <span data-ttu-id="e7af2-142">EOP SFV: SKS to SCL 6</span><span class="sxs-lookup"><span data-stu-id="e7af2-142">EOP SFV:SKS to SCL 6</span></span>

     - <span data-ttu-id="e7af2-143">EOP SFV: SKB to SCL 6</span><span class="sxs-lookup"><span data-stu-id="e7af2-143">EOP SFV:SKB to SCL 6</span></span>

   - <span data-ttu-id="e7af2-144">Fare clic su **altre opzioni**.</span><span class="sxs-lookup"><span data-stu-id="e7af2-144">Click **More Options**.</span></span>

   - <span data-ttu-id="e7af2-145">**Applica questa regola se**: selezionare **un'intestazione** \> **del messaggio include una di queste parole**.</span><span class="sxs-lookup"><span data-stu-id="e7af2-145">**Apply this rule if**: Select **A message header** \> **includes any of these words**.</span></span>

     <span data-ttu-id="e7af2-146">Nell' **intestazione Enter Text è inclusa l'indicazione Enter Words** , che viene visualizzata, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e7af2-146">In the **Enter text header includes Enter words** sentence that appears, do the following steps:</span></span>

     - <span data-ttu-id="e7af2-147">Fare clic su **Immetti testo**.</span><span class="sxs-lookup"><span data-stu-id="e7af2-147">Click **Enter text**.</span></span> <span data-ttu-id="e7af2-148">Nella finestra di dialogo **Specifica nome intestazione** che viene visualizzata, immettere **X-Forefront-antispam-report** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="e7af2-148">In the **Specify header name** dialog that appears, enter **X-Forefront-Antispam-Report** and then click **OK**.</span></span>

     - <span data-ttu-id="e7af2-149">Fare clic su **Immetti parole**.</span><span class="sxs-lookup"><span data-stu-id="e7af2-149">Click  **Enter words**.</span></span> <span data-ttu-id="e7af2-150">Nella finestra di dialogo **specifica parole o frasi** visualizzata, immettere uno dei valori delle intestazioni di posta indesiderata di EOP (**SFV: SPM**, **SFV: SKS**o **SFV: SKB**), fare clic su **Aggiungi** ![ icona ](../../media/ITPro-EAC-AddIcon.png) e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="e7af2-150">In the **Specify words or phrases** dialog that appears, enter one of the EOP spam header values (**SFV:SPM**, **SFV:SKS**, or **SFV:SKB**), click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png), and then click **OK**.</span></span>

   - <span data-ttu-id="e7af2-151">**Eseguire le operazioni seguenti**: selezionare **modifica le proprietà del messaggio** \> **impostare il livello di probabilità di posta indesiderata (SCL)**.</span><span class="sxs-lookup"><span data-stu-id="e7af2-151">**Do the following**: Select **Modify the message properties** \> **Set the spam confidence level (SCL)**.</span></span>

     <span data-ttu-id="e7af2-152">Nella finestra di dialogo **specifica SCL** visualizzata, selezionare **6** (il valore predefinito è **5**).</span><span class="sxs-lookup"><span data-stu-id="e7af2-152">In the **Specify SCL** dialog that appears, select **6** (the default value is **5**).</span></span>

   <span data-ttu-id="e7af2-153">Al termine, fare clic su **Salva**</span><span class="sxs-lookup"><span data-stu-id="e7af2-153">When you're finished, click **Save**</span></span>

<span data-ttu-id="e7af2-154">Ripetere questi passaggi per i valori del verdetto di posta indesiderata EOP rimanenti (**SFV: SPM**, **SFV: SKS**o **SFV: SKB**).</span><span class="sxs-lookup"><span data-stu-id="e7af2-154">Repeat these steps for the remaining EOP spam verdict values (**SFV:SPM**, **SFV:SKS**, or **SFV:SKB**).</span></span>

## <a name="use-the-exchange-management-shell-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a><span data-ttu-id="e7af2-155">Utilizzare Exchange Management Shell per creare regole del flusso di posta che configurano il livello SCL dei messaggi di posta indesiderata di EOP</span><span class="sxs-lookup"><span data-stu-id="e7af2-155">Use the Exchange Management Shell to create mail flow rules that set the SCL of EOP spam messages</span></span>

<span data-ttu-id="e7af2-156">Per creare le tre regole del flusso di posta, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="e7af2-156">Use the following syntax to create the three mail flow rules:</span></span>

```Powershell
New-TransportRule -Name "<RuleName>" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "<EOPSpamFilteringVerdict>" -SetSCL 6
```

<span data-ttu-id="e7af2-157">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e7af2-157">For example:</span></span>

```Powershell
New-TransportRule -Name "EOP SFV:SPM to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SPM" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKS to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKS" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKB to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKB" -SetSCL 6
```

<span data-ttu-id="e7af2-158">Per informazioni dettagliate su sintassi e parametri, vedere [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).</span><span class="sxs-lookup"><span data-stu-id="e7af2-158">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="e7af2-159">Come verificare se l'operazione ha avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="e7af2-159">How do you know this worked?</span></span>

<span data-ttu-id="e7af2-160">Per verificare la corretta configurazione di EOP autonomo per recapitare la posta indesiderata alla cartella posta indesiderata in ambiente ibrido, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e7af2-160">To verify that you've successfully configured standalone EOP to deliver spam to the Junk Email folder in hybrid environment, do any of the following steps:</span></span>

- <span data-ttu-id="e7af2-161">Nell'interfaccia di amministrazione di Exchange, andare a regole del **flusso di posta** \> **Rules**, selezionare la regola, quindi fare clic su **modifica** ![ icona modifica ](../../media/ITPro-EAC-EditIcon.png) per verificare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="e7af2-161">In the EAC, go to **Mail flow** \> **Rules**, select the rule, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png) to verify the settings.</span></span>

- <span data-ttu-id="e7af2-162">In Exchange Management Shell, sostituire \< RuleName \> con il nome della regola del flusso di posta e RUL il comando seguente per verificare le impostazioni:</span><span class="sxs-lookup"><span data-stu-id="e7af2-162">In the Exchange Management Shell, replace \<RuleName\> with the name of the mail flow rule, and rul the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "<RuleName>" | Format-List
  ```

- <span data-ttu-id="e7af2-163">In un sistema di posta elettronica esterno **che non esegue l'analisi dei messaggi in uscita per la posta indesiderata**, inviare un test generico per il messaggio di posta elettronica indesiderata (GTUBE) a un destinatario coinvolto e verificare che sia recapitato nella cartella posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="e7af2-163">In an external email system **that doesn't scan outbound messages for spam**, send a Generic Test for Unsolicited Bulk Email (GTUBE) message to an affected recipient, and confirm that it's delivered to their Junk Email folder.</span></span> <span data-ttu-id="e7af2-164">Un messaggio GTUBE è simile al file di testo EICAR (European Institute for Computer Antivirus Research) per la verifica delle impostazioni antimalware.</span><span class="sxs-lookup"><span data-stu-id="e7af2-164">A GTUBE message is similar to the European Institute for Computer Antivirus Research (EICAR) text file for testing malware settings.</span></span>

  <span data-ttu-id="e7af2-165">Per inviare un messaggio di GTUBE, includere il testo seguente nel corpo di un messaggio di posta elettronica su una singola riga, senza spazi o interruzioni di riga:</span><span class="sxs-lookup"><span data-stu-id="e7af2-165">To send a GTUBE message, include the following text in the body of an email message on a single line, without any spaces or line breaks:</span></span>

  ```text
  XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
  ```
