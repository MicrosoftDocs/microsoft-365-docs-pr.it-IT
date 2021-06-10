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
description: Gli amministratori possono ottenere informazioni sulle opzioni predefinite per la segnalazione della posta indesiderata, non della posta indesiderata e di phishing in Outlook sul Web (Outlook Web App) in Exchange Online e su come disabilitare queste opzioni di segnalazione per gli utenti.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1139871f5929ff9fef29e980b7614e5bc7b92570
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2021
ms.locfileid: "52788308"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-exchange-online"></a><span data-ttu-id="b5ea2-103">Segnalare la posta indesiderata e il phishing Outlook sul Web in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="b5ea2-103">Report junk and phishing email in Outlook on the web in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="b5ea2-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="b5ea2-104">**Applies to**</span></span>
- [<span data-ttu-id="b5ea2-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="b5ea2-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="b5ea2-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="b5ea2-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="b5ea2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b5ea2-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="b5ea2-108">Nelle organizzazioni Microsoft 365 con cassette postali in Exchange Online o cassette postali locali che utilizzano l'autenticazione moderna [ibrida,](../../enterprise/hybrid-modern-auth-overview.md)è possibile inviare falsi positivi (buona posta elettronica contrassegnata come posta indesiderata), falsi negativi (posta elettronica non consentita) e messaggi di phishing a Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="b5ea2-108">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using [hybrid modern authentication](../../enterprise/hybrid-modern-auth-overview.md), you can submit false positives (good email marked as spam), false negatives (bad email allowed), and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b5ea2-109">Che cosa è necessario sapere prima di iniziare?</span><span class="sxs-lookup"><span data-stu-id="b5ea2-109">What do you need to know before you begin?</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b5ea2-110">È consigliabile il componente aggiuntivo Segnala messaggio o Segnala phishing per gli invii degli utenti.</span><span class="sxs-lookup"><span data-stu-id="b5ea2-110">We recommend the Report Message add-in or the Report Phishing add-in for user submissions.</span></span> <span data-ttu-id="b5ea2-111">Per ulteriori informazioni, vedere [Enable the Report Message or the Report Phishing add-ins.](./enable-the-report-message-add-in.md) Non è consigliabile l'esperienza di creazione di report incorporata in Outlook perché non può usare i criteri di invio [degli utenti.](./user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="b5ea2-111">For more information, see [Enable the Report Message or the Report Phishing add-ins](./enable-the-report-message-add-in.md). We don't recommend the built-in reporting experience in Outlook because it can't use the [user submission policy](./user-submission.md).</span></span>

- <span data-ttu-id="b5ea2-112">Se si è un amministratore di un'organizzazione con Exchange Online cassette postali, è consigliabile utilizzare il portale invii nel Centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="b5ea2-112">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="b5ea2-113">Per ulteriori informazioni, vedere [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="b5ea2-113">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="b5ea2-114">Gli amministratori possono disabilitare o abilitare la possibilità per gli utenti di segnalare messaggi a Microsoft in Outlook sul Web.</span><span class="sxs-lookup"><span data-stu-id="b5ea2-114">Admins can disable or enable the ability for users to report messages to Microsoft in Outlook on the web.</span></span> <span data-ttu-id="b5ea2-115">Per informazioni dettagliate, vedere la sezione [Disabilitare o](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) abilitare la segnalazione della posta indesiderata in Outlook sul Web più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="b5ea2-115">For details, see the [Disable or enable junk email reporting in Outlook on the web](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) section later in this article.</span></span>

- <span data-ttu-id="b5ea2-116">È possibile configurare i messaggi segnalati da copiare o reindirizzare a una cassetta postale specificata.</span><span class="sxs-lookup"><span data-stu-id="b5ea2-116">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="b5ea2-117">Per ulteriori informazioni, vedere [Criteri di invio degli utenti.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="b5ea2-117">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="b5ea2-118">Per ulteriori informazioni sulla segnalazione dei messaggi a Microsoft, vedere [Segnalare messaggi e file a Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="b5ea2-118">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="b5ea2-119">Disabilitare o abilitare la segnalazione della posta indesiderata Outlook sul Web</span><span class="sxs-lookup"><span data-stu-id="b5ea2-119">Disable or enable junk email reporting in Outlook on the web</span></span>

<span data-ttu-id="b5ea2-120">Per impostazione predefinita, gli utenti possono segnalare falsi positivi, falsi negativi e messaggi di phishing di posta indesiderata a Microsoft per l'analisi in Outlook sul Web.</span><span class="sxs-lookup"><span data-stu-id="b5ea2-120">By default, users can report spam false positives, false negatives, and phishing messages to Microsoft for analysis in Outlook on the web.</span></span> <span data-ttu-id="b5ea2-121">Gli amministratori possono configurare Outlook criteri cassetta postale sul Web in Exchange Online PowerShell per impedire agli utenti di segnalare falsi positivi e falsi negativi di posta indesiderata a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b5ea2-121">Admins can configure Outlook on the web mailbox policies in Exchange Online PowerShell to prevent users from reporting spam false positives and spam false negatives to Microsoft.</span></span> <span data-ttu-id="b5ea2-122">Non è possibile disabilitare la possibilità per gli utenti di segnalare messaggi di phishing a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b5ea2-122">You can't disable the ability for users to report phishing messages to Microsoft.</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b5ea2-123">Che cosa è necessario sapere prima di iniziare?</span><span class="sxs-lookup"><span data-stu-id="b5ea2-123">What do you need to know before you begin?</span></span>

- <span data-ttu-id="b5ea2-124">Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="b5ea2-124">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="b5ea2-125">Per eseguire le procedure descritte in questo articolo, è necessario disporre delle autorizzazioni Exchange Online in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="b5ea2-125">You need to be assigned permissions in Exchange Online before you can do the procedures in this article.</span></span> <span data-ttu-id="b5ea2-126">In particolare, sono necessari i **ruoli Criteri** **destinatario** o  Destinatari di posta, assegnati ai gruppi di ruoli Gestione organizzazione e Gestione destinatari per impostazione predefinita. </span><span class="sxs-lookup"><span data-stu-id="b5ea2-126">Specifically you need the **Recipient Policies** or **Mail Recipients** roles, which are assigned to the **Organization Management** and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="b5ea2-127">Per ulteriori informazioni sui gruppi di ruoli in Exchange Online, vedere [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo) e Modify role groups in [Exchange Online](/Exchange/permissions-exo/role-groups#modify-role-groups).</span><span class="sxs-lookup"><span data-stu-id="b5ea2-127">For more information about role groups in Exchange Online, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo) and [Modify role groups in Exchange Online](/Exchange/permissions-exo/role-groups#modify-role-groups).</span></span>

- <span data-ttu-id="b5ea2-128">Ogni organizzazione dispone di un criterio predefinito denominato OwaMailboxPolicy-Default, ma è possibile creare criteri personalizzati.</span><span class="sxs-lookup"><span data-stu-id="b5ea2-128">Every organization has a default policy named OwaMailboxPolicy-Default, but you can create custom policies.</span></span> <span data-ttu-id="b5ea2-129">I criteri personalizzati vengono applicati agli utenti con ambito prima del criterio predefinito.</span><span class="sxs-lookup"><span data-stu-id="b5ea2-129">Custom policies are applied to scoped users before the default policy.</span></span> <span data-ttu-id="b5ea2-130">Per ulteriori informazioni sulle Outlook sui criteri cassetta postale Web, vedere [Outlook sui criteri cassetta](/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies)postale web in Exchange Online .</span><span class="sxs-lookup"><span data-stu-id="b5ea2-130">For more information about Outlook on the web mailbox policies, see [Outlook on the web mailbox policies in Exchange Online](/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).</span></span>

- <span data-ttu-id="b5ea2-131">La disabilitazione della segnalazione della posta indesiderata non rimuove la possibilità di contrassegnare un messaggio come indesiderato o non indesiderato Outlook sul Web.</span><span class="sxs-lookup"><span data-stu-id="b5ea2-131">Disabling junk email reporting doesn't remove the ability to mark a message as junk or not junk in Outlook on the web.</span></span> <span data-ttu-id="b5ea2-132">Se si seleziona un messaggio  nella cartella Posta indesiderata e si fa clic su Non posta indesiderata, il messaggio viene comunque spostato \>  di nuovo nella cartella Posta in arrivo.</span><span class="sxs-lookup"><span data-stu-id="b5ea2-132">Selecting a message in the Junk email folder and clicking **Not junk** \> **Not junk** still moves the message back into the Inbox.</span></span> <span data-ttu-id="b5ea2-133">Se si seleziona un messaggio  in qualsiasi altra cartella di posta elettronica e si fa clic su Posta indesiderata, il messaggio viene comunque \>  spostato nella cartella Posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="b5ea2-133">Selecting a message in any other email folder and clicking **Junk** \> **Junk** still moves the message into the Junk Email folder.</span></span> <span data-ttu-id="b5ea2-134">Ciò che non è più disponibile è l'opzione per segnalare il messaggio a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b5ea2-134">What's no longer available is the option to report the message to Microsoft.</span></span>

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="b5ea2-135">Usare Exchange Online PowerShell per disabilitare o abilitare la segnalazione della posta indesiderata Outlook sul Web</span><span class="sxs-lookup"><span data-stu-id="b5ea2-135">Use Exchange Online PowerShell to disable or enable junk email reporting in Outlook on the web</span></span>

1. <span data-ttu-id="b5ea2-136">Per trovare i criteri delle cassette postali Outlook sul Web e lo stato della segnalazione della posta indesiderata, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="b5ea2-136">To find your existing Outlook on the web mailbox policies and the status of junk email reporting, run the following command:</span></span>

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. <span data-ttu-id="b5ea2-137">Per disabilitare o abilitare la segnalazione della posta indesiderata Outlook sul Web, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="b5ea2-137">To disable or enable junk email reporting in Outlook on the web, use the following syntax:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   <span data-ttu-id="b5ea2-138">In questo esempio viene disabilitata la segnalazione della posta indesiderata nel criterio predefinito.</span><span class="sxs-lookup"><span data-stu-id="b5ea2-138">This example disables junk email reporting in the default policy.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   <span data-ttu-id="b5ea2-139">In questo esempio viene abilitata la segnalazione della posta indesiderata nel criterio personalizzato denominato Contoso Managers.</span><span class="sxs-lookup"><span data-stu-id="b5ea2-139">This example enables junk email reporting in the custom policy named Contoso Managers.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

<span data-ttu-id="b5ea2-140">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-OwaMailboxPolicy](/powershell/module/exchange/get-owamailboxpolicy) e [Set-OwaMailboxPolicy.](/powershell/module/exchange/set-owamailboxpolicy)</span><span class="sxs-lookup"><span data-stu-id="b5ea2-140">For detailed syntax and parameter information, see [Get-OwaMailboxPolicy](/powershell/module/exchange/get-owamailboxpolicy) and [Set-OwaMailboxPolicy](/powershell/module/exchange/set-owamailboxpolicy).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="b5ea2-141">Come verificare se l'operazione ha avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="b5ea2-141">How do you know this worked?</span></span>

<span data-ttu-id="b5ea2-142">Per verificare che la segnalazione della posta indesiderata sia stata abilitata o disabilitata correttamente Outlook sul Web, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b5ea2-142">To verify that you've successfully enabled or disabled junk email reporting in Outlook on the web, use any of the following steps:</span></span>

- <span data-ttu-id="b5ea2-143">In Exchange Online PowerShell, eseguire il comando seguente e verificare il valore della proprietà **ReportJunkEmailEnabled:**</span><span class="sxs-lookup"><span data-stu-id="b5ea2-143">In Exchange Online PowerShell, run the following command and verify the **ReportJunkEmailEnabled** property value:</span></span>

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- <span data-ttu-id="b5ea2-144">Aprire la cassetta postale di un utente interessato in Outlook sul Web,  selezionare un messaggio nella posta in arrivo, fare clic su Posta indesiderata e verificare che la richiesta di segnalare il messaggio a Microsoft sia o non sia \>  visualizzata.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b5ea2-144">Open an affected user's mailbox in Outlook on the web, select a message in the Inbox, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

- <span data-ttu-id="b5ea2-145">Aprire la cassetta postale di un utente interessato in Outlook sul Web, selezionare  un messaggio nella cartella Posta indesiderata, fare clic su Posta indesiderata e verificare che la richiesta di segnalare il messaggio a Microsoft sia o non sia \>  visualizzata.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b5ea2-145">Open an affected user's mailbox in Outlook on the web, select a message in the Junk Email folder, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

<span data-ttu-id="b5ea2-146"><sup>\*</sup> Gli utenti possono nascondere la richiesta di segnalare il messaggio pur segnalando il messaggio.</span><span class="sxs-lookup"><span data-stu-id="b5ea2-146"><sup>\*</sup> Users can hide the prompt to report the message while still reporting the message.</span></span> <span data-ttu-id="b5ea2-147">Per verificare questa impostazione in Outlook sul Web:</span><span class="sxs-lookup"><span data-stu-id="b5ea2-147">To check this setting in Outlook on the web:</span></span>

1. <span data-ttu-id="b5ea2-148">Fare **clic Impostazioni** Outlook sull'icona Impostazioni Web Visualizza tutte Outlook impostazioni Posta indesiderata ![ ](../../media/owa-settings-icon.png) \>  \> .</span><span class="sxs-lookup"><span data-stu-id="b5ea2-148">Click **Settings** ![Outlook on the web settings icon](../../media/owa-settings-icon.png) \> **View all Outlook settings** \> **Junk email**.</span></span>
2. <span data-ttu-id="b5ea2-149">Nella sezione **Report** verificare il valore: **Chiedi conferma prima di inviare un report.**</span><span class="sxs-lookup"><span data-stu-id="b5ea2-149">In the **Reporting** section, verify the value: **Ask me before sending a report**.</span></span>

   ![Outlook sul Web per la segnalazione della posta indesiderata](../../media/owa-junk-email-reporting-options.png)
