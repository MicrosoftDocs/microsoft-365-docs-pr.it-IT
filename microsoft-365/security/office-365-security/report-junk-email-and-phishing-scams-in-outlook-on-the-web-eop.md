---
title: Segnalare posta indesiderata e phishing in Outlook sul Web
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: Gli amministratori possono ottenere informazioni sulle opzioni predefinite per la segnalazione della posta indesiderata, non della posta indesiderata e del phishing in Outlook sul Web (Outlook Web App) in Exchange Online e su come disabilitare queste opzioni di segnalazione per gli utenti.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 933387dd32a6c1ca1e27ee11e4a9384615e8fdec
ms.sourcegitcommit: 0ff6edbf52562138a69c6675cb0274ec984986c3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/07/2021
ms.locfileid: "51615212"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-exchange-online"></a><span data-ttu-id="05591-103">Segnalare posta indesiderata e phishing in Outlook sul Web in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="05591-103">Report junk and phishing email in Outlook on the web in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="05591-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="05591-104">**Applies to**</span></span>
- [<span data-ttu-id="05591-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="05591-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="05591-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="05591-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="05591-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="05591-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="05591-108">Nelle organizzazioni di Microsoft 365 con cassette postali in Exchange Online o nelle cassette postali locali che utilizzano l'autenticazione moderna [ibrida,](../../enterprise/hybrid-modern-auth-overview.md)è possibile inviare falsi positivi (buona posta elettronica contrassegnata come posta indesiderata), falsi negativi (posta elettronica non consentita) e messaggi di phishing a Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="05591-108">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using [hybrid modern authentication](../../enterprise/hybrid-modern-auth-overview.md), you can submit false positives (good email marked as spam), false negatives (bad email allowed), and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="05591-109">Che cosa è necessario sapere prima di iniziare?</span><span class="sxs-lookup"><span data-stu-id="05591-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="05591-110">Per la migliore esperienza di invio degli utenti, ti consigliamo di usare i componenti aggiuntivi Segnala messaggio e Segnala phishing. Per ulteriori informazioni, vedere [Enable the Report Message add-in](./enable-the-report-message-add-in.md) e Enable the Report Phishing [add-in.](./enable-the-report-phish-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="05591-110">For the best user submission experience we recommend using the Report Message and the Report Phishing add-ins. See [Enable the Report Message add-in](./enable-the-report-message-add-in.md) and [Enable the Report Phishing add-in](./enable-the-report-phish-add-in.md) for more information.</span></span>

- <span data-ttu-id="05591-111">Se si è un amministratore di un'organizzazione con cassette postali di Exchange Online, è consigliabile utilizzare il portale invii nel Centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="05591-111">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="05591-112">Per ulteriori informazioni, vedere [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="05591-112">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="05591-113">Gli amministratori possono disabilitare o abilitare la possibilità per gli utenti di segnalare messaggi a Microsoft in Outlook sul Web.</span><span class="sxs-lookup"><span data-stu-id="05591-113">Admins can disable or enable the ability for users to report messages to Microsoft in Outlook on the web.</span></span> <span data-ttu-id="05591-114">Per informazioni dettagliate, vedere la [sezione Disabilitare o abilitare la segnalazione della](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) posta indesiderata in Outlook sul Web più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="05591-114">For details, see the [Disable or enable junk email reporting in Outlook on the web](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) section later in this article.</span></span>

- <span data-ttu-id="05591-115">È possibile configurare i messaggi segnalati da copiare o reindirizzare a una cassetta postale specificata.</span><span class="sxs-lookup"><span data-stu-id="05591-115">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="05591-116">Per ulteriori informazioni, vedere [Criteri di invio degli utenti.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="05591-116">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="05591-117">Per ulteriori informazioni sulla segnalazione dei messaggi a Microsoft, vedere [Segnalare messaggi e file a Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="05591-117">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="05591-118">Disabilitare o abilitare la segnalazione della posta indesiderata in Outlook sul Web</span><span class="sxs-lookup"><span data-stu-id="05591-118">Disable or enable junk email reporting in Outlook on the web</span></span>

<span data-ttu-id="05591-119">Per impostazione predefinita, gli utenti possono segnalare falsi positivi, falsi negativi e messaggi di phishing a Microsoft per l'analisi in Outlook sul Web.</span><span class="sxs-lookup"><span data-stu-id="05591-119">By default, users can report spam false positives, false negatives, and phishing messages to Microsoft for analysis in Outlook on the web.</span></span> <span data-ttu-id="05591-120">Gli amministratori possono configurare i criteri cassetta postale di Outlook sul Web in PowerShell di Exchange Online per impedire agli utenti di segnalare falsi positivi e falsi negativi di posta indesiderata a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="05591-120">Admins can configure Outlook on the web mailbox policies in Exchange Online PowerShell to prevent users from reporting spam false positives and spam false negatives to Microsoft.</span></span> <span data-ttu-id="05591-121">Non è possibile disabilitare la possibilità per gli utenti di segnalare messaggi di phishing a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="05591-121">You can't disable the ability for users to report phishing messages to Microsoft.</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="05591-122">Che cosa è necessario sapere prima di iniziare?</span><span class="sxs-lookup"><span data-stu-id="05591-122">What do you need to know before you begin?</span></span>

- <span data-ttu-id="05591-123">Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="05591-123">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="05591-124">Per eseguire le procedure descritte in questo articolo, è necessario disporre delle autorizzazioni in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="05591-124">You need to be assigned permissions in Exchange Online before you can do the procedures in this article.</span></span> <span data-ttu-id="05591-125">In particolare, sono necessari i **ruoli Criteri** **destinatario** o  Destinatari di posta, assegnati ai gruppi di ruoli Gestione organizzazione e Gestione destinatari per impostazione predefinita. </span><span class="sxs-lookup"><span data-stu-id="05591-125">Specifically you need the **Recipient Policies** or **Mail Recipients** roles, which are assigned to the **Organization Management** and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="05591-126">Per ulteriori informazioni sui gruppi di ruoli in Exchange Online, vedere [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo) e Modify role groups in Exchange [Online.](/Exchange/permissions-exo/role-groups#modify-role-groups)</span><span class="sxs-lookup"><span data-stu-id="05591-126">For more information about role groups in Exchange Online, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo) and [Modify role groups in Exchange Online](/Exchange/permissions-exo/role-groups#modify-role-groups).</span></span>

- <span data-ttu-id="05591-127">Ogni organizzazione dispone di un criterio predefinito denominato OwaMailboxPolicy-Default, ma è possibile creare criteri personalizzati.</span><span class="sxs-lookup"><span data-stu-id="05591-127">Every organization has a default policy named OwaMailboxPolicy-Default, but you can create custom policies.</span></span> <span data-ttu-id="05591-128">I criteri personalizzati vengono applicati agli utenti con ambito prima del criterio predefinito.</span><span class="sxs-lookup"><span data-stu-id="05591-128">Custom policies are applied to scoped users before the default policy.</span></span> <span data-ttu-id="05591-129">Per ulteriori informazioni sui criteri cassetta postale di Outlook sul Web, vedere Criteri cassetta postale [di Outlook sul Web in Exchange Online.](/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies)</span><span class="sxs-lookup"><span data-stu-id="05591-129">For more information about Outlook on the web mailbox policies, see [Outlook on the web mailbox policies in Exchange Online](/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).</span></span>

- <span data-ttu-id="05591-130">La disabilitazione della segnalazione della posta indesiderata non rimuove la possibilità di contrassegnare un messaggio come indesiderato o non indesiderato in Outlook sul Web.</span><span class="sxs-lookup"><span data-stu-id="05591-130">Disabling junk email reporting doesn't remove the ability to mark a message as junk or not junk in Outlook on the web.</span></span> <span data-ttu-id="05591-131">Se si seleziona un messaggio  nella cartella Posta indesiderata e si fa clic su Non posta indesiderata, il messaggio viene comunque spostato \>  di nuovo nella cartella Posta in arrivo.</span><span class="sxs-lookup"><span data-stu-id="05591-131">Selecting a message in the Junk email folder and clicking **Not junk** \> **Not junk** still moves the message back into the Inbox.</span></span> <span data-ttu-id="05591-132">Se si seleziona un messaggio  in qualsiasi altra cartella di posta elettronica e si fa clic su Posta indesiderata, il messaggio viene comunque \>  spostato nella cartella Posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="05591-132">Selecting a message in any other email folder and clicking **Junk** \> **Junk** still moves the message into the Junk Email folder.</span></span> <span data-ttu-id="05591-133">Ciò che non è più disponibile è l'opzione per segnalare il messaggio a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="05591-133">What's no longer available is the option to report the message to Microsoft.</span></span>

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="05591-134">Utilizzare PowerShell di Exchange Online per disabilitare o abilitare la segnalazione della posta indesiderata in Outlook sul Web</span><span class="sxs-lookup"><span data-stu-id="05591-134">Use Exchange Online PowerShell to disable or enable junk email reporting in Outlook on the web</span></span>

1. <span data-ttu-id="05591-135">Per trovare i criteri cassetta postale di Outlook sul Web esistenti e lo stato della segnalazione della posta indesiderata, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="05591-135">To find your existing Outlook on the web mailbox policies and the status of junk email reporting, run the following command:</span></span>

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. <span data-ttu-id="05591-136">Per disabilitare o abilitare la segnalazione della posta indesiderata in Outlook sul Web, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="05591-136">To disable or enable junk email reporting in Outlook on the web, use the following syntax:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   <span data-ttu-id="05591-137">In questo esempio viene disabilitata la segnalazione della posta indesiderata nel criterio predefinito.</span><span class="sxs-lookup"><span data-stu-id="05591-137">This example disables junk email reporting in the default policy.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   <span data-ttu-id="05591-138">In questo esempio viene abilitata la segnalazione della posta indesiderata nel criterio personalizzato denominato Contoso Managers.</span><span class="sxs-lookup"><span data-stu-id="05591-138">This example enables junk email reporting in the custom policy named Contoso Managers.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

<span data-ttu-id="05591-139">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-OwaMailboxPolicy](/powershell/module/exchange/get-owamailboxpolicy) e [Set-OwaMailboxPolicy.](/powershell/module/exchange/set-owamailboxpolicy)</span><span class="sxs-lookup"><span data-stu-id="05591-139">For detailed syntax and parameter information, see [Get-OwaMailboxPolicy](/powershell/module/exchange/get-owamailboxpolicy) and [Set-OwaMailboxPolicy](/powershell/module/exchange/set-owamailboxpolicy).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="05591-140">Come verificare se l'operazione ha avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="05591-140">How do you know this worked?</span></span>

<span data-ttu-id="05591-141">Per verificare che la segnalazione della posta indesiderata in Outlook sul Web sia stata abilitata o disabilitata correttamente, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="05591-141">To verify that you've successfully enabled or disabled junk email reporting in Outlook on the web, use any of the following steps:</span></span>

- <span data-ttu-id="05591-142">In PowerShell di Exchange Online, eseguire il comando seguente e verificare il valore della **proprietà ReportJunkEmailEnabled:**</span><span class="sxs-lookup"><span data-stu-id="05591-142">In Exchange Online PowerShell, run the following command and verify the **ReportJunkEmailEnabled** property value:</span></span>

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- <span data-ttu-id="05591-143">Aprire la cassetta postale di un utente interessato in Outlook sul  Web, selezionare un messaggio nella cartella Posta in arrivo, fare clic su Posta indesiderata e verificare che il messaggio venga visualizzato o \>  meno.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="05591-143">Open an affected user's mailbox in Outlook on the web, select a message in the Inbox, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

- <span data-ttu-id="05591-144">Aprire la cassetta postale di un utente interessato in Outlook sul Web, selezionare un messaggio nella cartella Posta indesiderata, fare clic su Posta indesiderata e verificare che la richiesta di segnalare il messaggio a Microsoft sia o non sia  \>  visualizzata.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="05591-144">Open an affected user's mailbox in Outlook on the web, select a message in the Junk Email folder, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

<span data-ttu-id="05591-145"><sup>\*</sup> Gli utenti possono nascondere la richiesta di segnalare il messaggio pur segnalando il messaggio.</span><span class="sxs-lookup"><span data-stu-id="05591-145"><sup>\*</sup> Users can hide the prompt to report the message while still reporting the message.</span></span> <span data-ttu-id="05591-146">Per verificare questa impostazione in Outlook sul Web:</span><span class="sxs-lookup"><span data-stu-id="05591-146">To check this setting in Outlook on the web:</span></span>

1. <span data-ttu-id="05591-147">Fare **clic su Impostazioni** Icona Impostazioni di Outlook sul Web Visualizza tutte le impostazioni di ![ ](../../media/owa-settings-icon.png) \> **Outlook** Posta \> **indesiderata.**</span><span class="sxs-lookup"><span data-stu-id="05591-147">Click **Settings** ![Outlook on the web settings icon](../../media/owa-settings-icon.png) \> **View all Outlook settings** \> **Junk email**.</span></span>
2. <span data-ttu-id="05591-148">Nella sezione **Report** verificare il valore: **Chiedi conferma prima di inviare un report.**</span><span class="sxs-lookup"><span data-stu-id="05591-148">In the **Reporting** section, verify the value: **Ask me before sending a report**.</span></span>

   ![Impostazioni per la segnalazione della posta indesiderata di Outlook sul Web](../../media/owa-junk-email-reporting-options.png)