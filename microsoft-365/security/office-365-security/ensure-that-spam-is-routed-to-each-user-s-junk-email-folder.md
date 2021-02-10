---
title: Configurare EOP per la posta indesiderata in ambienti ibridi
f1.keywords:
- NOCSH
ms.author: chrisda
author: MSFTTracyP
manager: chrisda
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0cbaccf8-4afc-47e3-a36d-a84598a55fb8
ms.collection:
- M365-security-compliance
description: Gli amministratori possono imparare a instradare la posta indesiderata alle cartelle posta indesiderata dell'utente in un ambiente ibrido di Exchange Online Protection.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 926ac6dec33bf00fc8f0dcd292229e20ccc2b93f
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167120"
---
# <a name="configure-standalone-eop-to-deliver-spam-to-the-junk-email-folder-in-hybrid-environments"></a><span data-ttu-id="6c93c-103">Configurare EOP autonomo per recapitare la posta indesiderata nella cartella Posta indesiderata negli ambienti ibridi</span><span class="sxs-lookup"><span data-stu-id="6c93c-103">Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="6c93c-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="6c93c-104">**Applies to**</span></span>
-  [<span data-ttu-id="6c93c-105">Exchange Online Protection autonomo</span><span class="sxs-lookup"><span data-stu-id="6c93c-105">Exchange Online Protection standalone</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)

> [!IMPORTANT]
> <span data-ttu-id="6c93c-106">Questo argomento è disponibile solo per i clienti EOP autonomi in ambienti ibridi.</span><span class="sxs-lookup"><span data-stu-id="6c93c-106">This topic is only for standalone EOP customers in hybrid environments.</span></span> <span data-ttu-id="6c93c-107">Questo argomento non si applica ai clienti di Microsoft 365 con cassette postali di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="6c93c-107">This topic does not apply to Microsoft 365 customers with Exchange Online mailboxes.</span></span>

<span data-ttu-id="6c93c-108">Se si è un cliente autonomo di Exchange Online Protection (EOP) in un ambiente ibrido, è necessario configurare l'organizzazione di Exchange locale per riconoscere e tradurre i verdetti del filtro posta indesiderata di EOP, in modo che la regola di posta indesiderata nella cassetta postale locale possa spostare i messaggi nella cartella Posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="6c93c-108">If you're a standalone Exchange Online Protection (EOP) customer in a hybrid environment, you need to configure your on-premises Exchange organization to recognize and translate the spam filtering verdicts of EOP, so the junk email rule in the on-premises mailbox can move messages to the Junk Email folder.</span></span>

<span data-ttu-id="6c93c-109">In particolare, è necessario creare regole del flusso di posta (note anche come regole di trasporto) nell'organizzazione Exchange locale con condizioni che trovano i messaggi con una delle seguenti intestazioni e valori di protezione da posta indesiderata EOP e azioni che impostano il livello di probabilità di posta indesiderata (SCL) di tali messaggi su 6:</span><span class="sxs-lookup"><span data-stu-id="6c93c-109">Specifically, you need to create mail flow rules (also known as transport rules) in your on-premises Exchange organization with conditions that find messages with any of the following EOP anti-spam headers and values, and actions that set the spam confidence level (SCL) of those messages to 6:</span></span>

- <span data-ttu-id="6c93c-110">`X-Forefront-Antispam-Report: SFV:SPM` (messaggio contrassegnato come posta indesiderata dal filtro posta indesiderata)</span><span class="sxs-lookup"><span data-stu-id="6c93c-110">`X-Forefront-Antispam-Report: SFV:SPM` (message marked as spam by spam filtering)</span></span>

- <span data-ttu-id="6c93c-111">`X-Forefront-Antispam-Report: SFV:SKS` (messaggio contrassegnato come posta indesiderata dalle regole del flusso di posta in EOP prima del filtro posta indesiderata)</span><span class="sxs-lookup"><span data-stu-id="6c93c-111">`X-Forefront-Antispam-Report: SFV:SKS` (message marked as spam by mail flow rules in EOP before spam filtering)</span></span>

- <span data-ttu-id="6c93c-112">`X-Forefront-Antispam-Report: SFV:SKB` (messaggio contrassegnato come posta indesiderata dal filtro posta indesiderata a causa dell'indirizzo di posta elettronica del mittente o del dominio di posta elettronica presente nell'elenco dei mittenti bloccati o nell'elenco dei domini bloccati in EOP)</span><span class="sxs-lookup"><span data-stu-id="6c93c-112">`X-Forefront-Antispam-Report: SFV:SKB` (message marked as spam by spam filtering due to the sender's email address or email domain being in the blocked sender list or the blocked domain list in EOP)</span></span>

<span data-ttu-id="6c93c-113">Per ulteriori informazioni su questi valori di intestazione, vedere Intestazioni dei messaggi di [protezione da posta indesiderata.](anti-spam-message-headers.md)</span><span class="sxs-lookup"><span data-stu-id="6c93c-113">For more information about these header values, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>

<span data-ttu-id="6c93c-114">In questo argomento viene descritto come creare queste regole del flusso di posta nell'interfaccia di amministrazione di Exchange (EAC) e in Exchange Management Shell (Exchange PowerShell) nell'organizzazione exchange locale.</span><span class="sxs-lookup"><span data-stu-id="6c93c-114">This topic describes how to create these mail flow rules the Exchange admin center (EAC) and in the Exchange Management Shell (Exchange PowerShell) in the on-premises Exchange organization.</span></span>

> [!TIP]
> <span data-ttu-id="6c93c-115">Anziché recapitare i messaggi nella cartella Posta indesiderata dell'utente locale, è possibile configurare i criteri di protezione dalla posta indesiderata in EOP per mettere in quarantena i messaggi di posta indesiderata in EOP.</span><span class="sxs-lookup"><span data-stu-id="6c93c-115">Instead of delivering the messages to the on-premises user's Junk Email folder, you can configure anti-spam policies in EOP to quarantine spam messages in EOP.</span></span> <span data-ttu-id="6c93c-116">Per altre informazioni, vedere [Configurare i criteri di protezione dalla posta indesiderata in EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="6c93c-116">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="6c93c-117">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="6c93c-117">What do you need to know before you begin?</span></span>

- <span data-ttu-id="6c93c-118">Per eseguire queste procedure, è necessario disporre delle autorizzazioni nell'ambiente Exchange locale.</span><span class="sxs-lookup"><span data-stu-id="6c93c-118">You need to be assigned permissions in the on-premises Exchange environment before you can do these procedures.</span></span> <span data-ttu-id="6c93c-119">In particolare, è necessario  disporre del ruolo Regole di trasporto, assegnato ai ruoli **Gestione** **organizzazione,** Gestione conformità e **Gestione record** per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="6c93c-119">Specifically, you need to be assigned the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management**, and **Records Management** roles by default.</span></span> <span data-ttu-id="6c93c-120">Per ulteriori informazioni, vedere [Add members to a role group](https://docs.microsoft.com/Exchange/permissions/role-group-members#add-members-to-a-role-group).</span><span class="sxs-lookup"><span data-stu-id="6c93c-120">For more information, see [Add members to a role group](https://docs.microsoft.com/Exchange/permissions/role-group-members#add-members-to-a-role-group).</span></span>

- <span data-ttu-id="6c93c-121">Se e quando un messaggio viene recapitato nella cartella Posta indesiderata in un'organizzazione exchange locale è controllato da una combinazione delle seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="6c93c-121">If and when a message is delivered to the Junk Email folder in an on-premises Exchange organization is controlled by a combination of the following settings:</span></span>

  - <span data-ttu-id="6c93c-122">Il _valore del parametro SCLJunkThreshold_ nel cmdlet [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig) in Exchange Management Shell.</span><span class="sxs-lookup"><span data-stu-id="6c93c-122">The _SCLJunkThreshold_ parameter value on the [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig) cmdlet in the Exchange Management Shell.</span></span> <span data-ttu-id="6c93c-123">Il valore predefinito è 4, il che significa che un livello di probabilità di posta indesiderata pari o superiore a 5 deve recapitare il messaggio nella cartella Posta indesiderata dell'utente.</span><span class="sxs-lookup"><span data-stu-id="6c93c-123">The default value is 4, which means an SCL of 5 or higher should deliver the message to the user's Junk email folder.</span></span>

  - <span data-ttu-id="6c93c-124">Il _valore del parametro SCLJunkThreshold_ nel cmdlet [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/set-mailbox) in Exchange Management Shell.</span><span class="sxs-lookup"><span data-stu-id="6c93c-124">The _SCLJunkThreshold_ parameter value on the [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/set-mailbox) cmdlet in the Exchange Management Shell.</span></span> <span data-ttu-id="6c93c-125">Il valore predefinito è vuoto ($null), ovvero viene utilizzata l'impostazione dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="6c93c-125">The default value is blank ($null), which means the organization setting is used.</span></span>

  <span data-ttu-id="6c93c-126">Per informazioni dettagliate, vedere Soglie del livello di probabilità di posta indesiderata [(SCL) di Exchange.](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/scl)</span><span class="sxs-lookup"><span data-stu-id="6c93c-126">For details, see [Exchange spam confidence level (SCL) thresholds](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/scl).</span></span>

  - <span data-ttu-id="6c93c-127">Indica se la regola di posta indesiderata è abilitata nella cassetta postale (il valore del parametro _Enabled_ è $true sul cmdlet [Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration) in Exchange Management Shell).</span><span class="sxs-lookup"><span data-stu-id="6c93c-127">Whether the junk email rule is enabled on the mailbox (the _Enabled_ parameter value is $true on the [Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration) cmdlet in the Exchange Management Shell).</span></span> <span data-ttu-id="6c93c-128">È la regola di posta indesiderata che sposta effettivamente il messaggio nella cartella Posta indesiderata dopo il recapito.</span><span class="sxs-lookup"><span data-stu-id="6c93c-128">It's the junk email rule that actually moves the message to the Junk Email folder after delivery.</span></span> <span data-ttu-id="6c93c-129">Per impostazione predefinita, la regola di posta indesiderata è abilitata nelle cassette postali.</span><span class="sxs-lookup"><span data-stu-id="6c93c-129">By default, the junk email rule is enabled on mailboxes.</span></span> <span data-ttu-id="6c93c-130">Per ulteriori informazioni, vedere [Configure Exchange antispam settings on mailboxes](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings).</span><span class="sxs-lookup"><span data-stu-id="6c93c-130">For more information, see [Configure Exchange antispam settings on mailboxes](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings).</span></span>

- <span data-ttu-id="6c93c-131">Per aprire l'interfaccia di amministrazione di Exchange in Exchange Server, vedere l'interfaccia di amministrazione [di Exchange in Exchange Server](https://docs.microsoft.com/Exchange/architecture/client-access/exchange-admin-center).</span><span class="sxs-lookup"><span data-stu-id="6c93c-131">To open the EAC on an Exchange Server, see [Exchange admin center in Exchange Server](https://docs.microsoft.com/Exchange/architecture/client-access/exchange-admin-center).</span></span> <span data-ttu-id="6c93c-132">Per aprire Exchange Management Shell, vedere [Aprire Exchange Management Shell](https://docs.microsoft.com/powershell/exchange/open-the-exchange-management-shell).</span><span class="sxs-lookup"><span data-stu-id="6c93c-132">To open the Exchange Management Shell, see [Open the Exchange Management Shell](https://docs.microsoft.com/powershell/exchange/open-the-exchange-management-shell).</span></span>

- <span data-ttu-id="6c93c-133">Per ulteriori informazioni sulle regole del flusso di posta in Exchange locale, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="6c93c-133">For more information about mail flow rules in on-premises Exchange, see the following topics:</span></span>

  - [<span data-ttu-id="6c93c-134">Regole del flusso di posta Exchange Server</span><span class="sxs-lookup"><span data-stu-id="6c93c-134">Mail flow rules in Exchange Server</span></span>](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="6c93c-135">Condizioni ed eccezioni delle regole del flusso di posta (predicati) in Exchange Server</span><span class="sxs-lookup"><span data-stu-id="6c93c-135">Mail flow rule conditions and exceptions (predicates) in Exchange Server</span></span>](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="6c93c-136">Azioni delle regole del flusso di posta in Exchange Server</span><span class="sxs-lookup"><span data-stu-id="6c93c-136">Mail flow rule actions in Exchange Server</span></span>](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/actions)

## <a name="use-the-eac-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a><span data-ttu-id="6c93c-137">Utilizzo dell'interfaccia di amministrazione di Exchange per creare regole del flusso di posta che impostano il livello di probabilità di posta indesiderata dei messaggi di posta indesiderata di EOP</span><span class="sxs-lookup"><span data-stu-id="6c93c-137">Use the EAC to create mail flow rules that set the SCL of EOP spam messages</span></span>

1. <span data-ttu-id="6c93c-138">Nell'interfaccia di amministrazione di Exchange, andare a **Flusso di posta** \> **Regole**.</span><span class="sxs-lookup"><span data-stu-id="6c93c-138">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="6c93c-139">Fare **clic** sull'icona Aggiungi e selezionare Crea una nuova ![ regola ](../../media/ITPro-EAC-AddIcon.png) nell'elenco a discesa visualizzato. </span><span class="sxs-lookup"><span data-stu-id="6c93c-139">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and select **Create a new rule** in the drop-down that appears.</span></span>

3. <span data-ttu-id="6c93c-140">Nella pagina **Nuova regola** che si apre, configurare le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="6c93c-140">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="6c93c-141">**Nome**: immettere un nome descrittivo univoco per la regola.</span><span class="sxs-lookup"><span data-stu-id="6c93c-141">**Name**: Enter a unique, descriptive name for the rule.</span></span> <span data-ttu-id="6c93c-142">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="6c93c-142">For example:</span></span>

     - <span data-ttu-id="6c93c-143">EOP SFV:SPM a SCL 6</span><span class="sxs-lookup"><span data-stu-id="6c93c-143">EOP SFV:SPM to SCL 6</span></span>

     - <span data-ttu-id="6c93c-144">EOP SFV:SKS a SCL 6</span><span class="sxs-lookup"><span data-stu-id="6c93c-144">EOP SFV:SKS to SCL 6</span></span>

     - <span data-ttu-id="6c93c-145">EOP SFV:SKB a SCL 6</span><span class="sxs-lookup"><span data-stu-id="6c93c-145">EOP SFV:SKB to SCL 6</span></span>

   - <span data-ttu-id="6c93c-146">Fare **clic su Altre opzioni.**</span><span class="sxs-lookup"><span data-stu-id="6c93c-146">Click **More Options**.</span></span>

   - <span data-ttu-id="6c93c-147">**Applicare questa regola se**: Select **A message header** includes any of \> **these words.**</span><span class="sxs-lookup"><span data-stu-id="6c93c-147">**Apply this rule if**: Select **A message header** \> **includes any of these words**.</span></span>

     <span data-ttu-id="6c93c-148">Nell'intestazione Immettere il testo include la frase di **immissione** parole che viene visualizzata, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="6c93c-148">In the **Enter text header includes Enter words** sentence that appears, do the following steps:</span></span>

     - <span data-ttu-id="6c93c-149">Fare **clic su Immetti testo.**</span><span class="sxs-lookup"><span data-stu-id="6c93c-149">Click **Enter text**.</span></span> <span data-ttu-id="6c93c-150">Nella finestra **di dialogo Specifica** nome intestazione visualizzata, immettere **X-Forefront-Antispam-Report** e quindi fare clic su **OK.**</span><span class="sxs-lookup"><span data-stu-id="6c93c-150">In the **Specify header name** dialog that appears, enter **X-Forefront-Antispam-Report** and then click **OK**.</span></span>

     - <span data-ttu-id="6c93c-151">Fare **clic su Immetti parole.**</span><span class="sxs-lookup"><span data-stu-id="6c93c-151">Click  **Enter words**.</span></span> <span data-ttu-id="6c93c-152">Nella  finestra di dialogo Specifica parole o frasi visualizzata, immettere uno dei valori di intestazione della posta indesiderata EOP (  **SFV:SPM,** **SFV:SKS** o **SFV:SKB**), fare clic sull'icona Aggiungi e quindi su ![ ](../../media/ITPro-EAC-AddIcon.png) **OK.**</span><span class="sxs-lookup"><span data-stu-id="6c93c-152">In the **Specify words or phrases** dialog that appears, enter one of the EOP spam header values (**SFV:SPM**, **SFV:SKS**, or **SFV:SKB**), click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png), and then click **OK**.</span></span>

   - <span data-ttu-id="6c93c-153">**Eseguire le operazioni seguenti:** Selezionare **Modifica le proprietà del messaggio** Impostare il livello di probabilità di posta indesiderata \> **(SCL).**</span><span class="sxs-lookup"><span data-stu-id="6c93c-153">**Do the following**: Select **Modify the message properties** \> **Set the spam confidence level (SCL)**.</span></span>

     <span data-ttu-id="6c93c-154">Nella finestra **di dialogo Specifica SCL** visualizzata, selezionare **6** (il valore predefinito è **5).**</span><span class="sxs-lookup"><span data-stu-id="6c93c-154">In the **Specify SCL** dialog that appears, select **6** (the default value is **5**).</span></span>

   <span data-ttu-id="6c93c-155">Al termine, fare clic su **Salva**</span><span class="sxs-lookup"><span data-stu-id="6c93c-155">When you're finished, click **Save**</span></span>

<span data-ttu-id="6c93c-156">Ripetere questi passaggi per i rimanenti valori del verdetto di posta indesiderata EOP (**SFV:SPM,** **SFV:SKS** o **SFV:SKB**).</span><span class="sxs-lookup"><span data-stu-id="6c93c-156">Repeat these steps for the remaining EOP spam verdict values (**SFV:SPM**, **SFV:SKS**, or **SFV:SKB**).</span></span>

## <a name="use-the-exchange-management-shell-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a><span data-ttu-id="6c93c-157">Creazione di regole del flusso di posta che impostano il livello di probabilità di posta indesiderata dei messaggi di posta indesiderata di EOP tramite Exchange Management Shell</span><span class="sxs-lookup"><span data-stu-id="6c93c-157">Use the Exchange Management Shell to create mail flow rules that set the SCL of EOP spam messages</span></span>

<span data-ttu-id="6c93c-158">Utilizzare la sintassi seguente per creare le tre regole del flusso di posta:</span><span class="sxs-lookup"><span data-stu-id="6c93c-158">Use the following syntax to create the three mail flow rules:</span></span>

```Powershell
New-TransportRule -Name "<RuleName>" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "<EOPSpamFilteringVerdict>" -SetSCL 6
```

<span data-ttu-id="6c93c-159">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="6c93c-159">For example:</span></span>

```Powershell
New-TransportRule -Name "EOP SFV:SPM to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SPM" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKS to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKS" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKB to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKB" -SetSCL 6
```

<span data-ttu-id="6c93c-160">Per informazioni dettagliate su sintassi e parametri, vedere [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).</span><span class="sxs-lookup"><span data-stu-id="6c93c-160">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="6c93c-161">Come verificare se l'operazione ha avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="6c93c-161">How do you know this worked?</span></span>

<span data-ttu-id="6c93c-162">Per verificare la corretta configurazione di EOP autonomo per il recapito della posta indesiderata nella cartella Posta indesiderata nell'ambiente ibrido, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6c93c-162">To verify that you've successfully configured standalone EOP to deliver spam to the Junk Email folder in hybrid environment, do any of the following steps:</span></span>

- <span data-ttu-id="6c93c-163">Nell'interfaccia di amministrazione di Exchange, andare a Regole del **flusso** di posta, selezionare la regola, quindi fare clic sull'icona Modifica \> per verificare le  ![ ](../../media/ITPro-EAC-EditIcon.png) impostazioni.</span><span class="sxs-lookup"><span data-stu-id="6c93c-163">In the EAC, go to **Mail flow** \> **Rules**, select the rule, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png) to verify the settings.</span></span>

- <span data-ttu-id="6c93c-164">In Exchange Management Shell, sostituire con il nome della regola del flusso di posta e utilizzare il seguente comando \<RuleName\> per verificare le impostazioni:</span><span class="sxs-lookup"><span data-stu-id="6c93c-164">In the Exchange Management Shell, replace \<RuleName\> with the name of the mail flow rule, and rul the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "<RuleName>" | Format-List
  ```

- <span data-ttu-id="6c93c-165">In un sistema di posta elettronica esterno che non analizza i messaggi in uscita per la posta **indesiderata,** inviare un test generico per un messaggio GTUBE (Unsolicited Bulk Email) a un destinatario interessato e verificare che sia recapitato nella cartella Posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="6c93c-165">In an external email system **that doesn't scan outbound messages for spam**, send a Generic Test for Unsolicited Bulk Email (GTUBE) message to an affected recipient, and confirm that it's delivered to their Junk Email folder.</span></span> <span data-ttu-id="6c93c-166">Un messaggio GTUBE è simile al file di testo EICAR (European Institute for Computer Antivirus Research) per la verifica delle impostazioni antimalware.</span><span class="sxs-lookup"><span data-stu-id="6c93c-166">A GTUBE message is similar to the European Institute for Computer Antivirus Research (EICAR) text file for testing malware settings.</span></span>

  <span data-ttu-id="6c93c-167">Per inviare un messaggio GTUBE, includere il testo seguente nel corpo di un messaggio di posta elettronica su una singola riga, senza spazi o interruzioni di riga:</span><span class="sxs-lookup"><span data-stu-id="6c93c-167">To send a GTUBE message, include the following text in the body of an email message on a single line, without any spaces or line breaks:</span></span>

  ```text
  XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
  ```
