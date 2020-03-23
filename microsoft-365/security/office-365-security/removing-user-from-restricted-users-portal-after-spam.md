---
title: Rimuovere utenti bloccati dal portale Utenti con restrizioni
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.exch.eac.ActionCenter.Restricted.Users.RestrictedUsers
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 712cfcc1-31e8-4e51-8561-b64258a8f1e5
ms.collection:
- M365-security-compliance
description: Gli amministratori possono scoprire come rimuovere gli utenti dal portale Utenti con restrizioni in Office 365. Gli utenti vengono aggiunti al portale Utenti con restrizioni se hanno inviato posta indesiderata in uscita, in genere in seguito a una compromissione dell'account.
ms.openlocfilehash: f1f869a81ef5b01733bf9060117cf3706094b961
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895204"
---
# <a name="remove-blocked-users-from-the-restricted-users-portal-in-office-365"></a><span data-ttu-id="f81fd-104">Rimuovere utenti bloccati dal portale Utenti con restrizioni in Office 365</span><span class="sxs-lookup"><span data-stu-id="f81fd-104">Remove blocked users from the Restricted Users portal in Office 365</span></span>

<span data-ttu-id="f81fd-105">Se un utente supera uno dei limiti di invio in uscita, come specificato nei [limiti di servizio](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) o nei [criteri di posta indesiderata in uscita](configure-the-outbound-spam-policy.md), l'utente non può inviare messaggi di posta elettronica, ma può continuare a riceverne.</span><span class="sxs-lookup"><span data-stu-id="f81fd-105">If a user exceeds one of the outbound sending limits as specified in [the service limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) or in [outbound spam policies](configure-the-outbound-spam-policy.md), the user is restricted from sending email, but they can still receive email.</span></span>

<span data-ttu-id="f81fd-106">L'utente viene aggiunto al portale Utenti con restrizioni nel Centro sicurezza e conformità di Office 365.</span><span class="sxs-lookup"><span data-stu-id="f81fd-106">The user is added to the Restricted Users portal in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="f81fd-107">Quando prova a inviare messaggi di posta elettronica, il messaggio viene restituito in un rapporto di mancato recapito, noto anche come NDR o notifica di mancato recapito, con il codice di errore [5.1.8](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/fix-error-code-5-1-8-in-exchange-online) e il testo seguente:</span><span class="sxs-lookup"><span data-stu-id="f81fd-107">When they try to send email, the message is returned in a non-delivery report (also known as an NDR or bounce messages) with the error code [5.1.8](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/fix-error-code-5-1-8-in-exchange-online) and the following text:</span></span>

> <span data-ttu-id="f81fd-108">"Non è stato possibile recapitare il messaggio perché l'utente non è stato riconosciuto come mittente valido.</span><span class="sxs-lookup"><span data-stu-id="f81fd-108">"Your message couldn't be delivered because you weren't recognized as a valid sender.</span></span> <span data-ttu-id="f81fd-109">La causa più comune di questo problema è che l'indirizzo di posta elettronica sia sospettato di inviare posta indesiderata e che non sia più autorizzato a inviare messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="f81fd-109">The most common reason for this is that your email address is suspected of sending spam and it's no longer allowed to send email.</span></span>  <span data-ttu-id="f81fd-110">Contattare l'amministratore della posta elettronica per ricevere assistenza.</span><span class="sxs-lookup"><span data-stu-id="f81fd-110">Contact  your email admin for assistance.</span></span> <span data-ttu-id="f81fd-111">Il server remoto ha restituito l'errore "550 5.1.8 Access denied, bad outbound sender."</span><span class="sxs-lookup"><span data-stu-id="f81fd-111">Remote Server returned '550 5.1.8 Access denied, bad outbound sender."</span></span>

<span data-ttu-id="f81fd-112">Gli amministratori possono rimuovere gli utenti dal portale Utenti con restrizioni nel Centro sicurezza e conformità o in PowerShell per Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="f81fd-112">Admins can remove users from the Restricted Senders portal in the Security & Compliance Center or in Exchange Online PowerShell.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f81fd-113">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="f81fd-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f81fd-114">Aprire il Centro sicurezza e conformità in<https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="f81fd-114">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="f81fd-115">Per passare direttamente alla pagina **Utenti con restrizioni**, usare <https://protection.office.com/restrictedusers>.</span><span class="sxs-lookup"><span data-stu-id="f81fd-115">To go directly to the **Restricted Users** page, use <https://protection.office.com/restrictedusers>.</span></span>

- <span data-ttu-id="f81fd-116">Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="f81fd-116">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="f81fd-117">È necessario disporre delle autorizzazioni prima di poter eseguire queste procedure.</span><span class="sxs-lookup"><span data-stu-id="f81fd-117">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="f81fd-118">Per rimuovere utenti dal portale Utenti con restrizioni è necessario essere membri dei gruppi di ruoli **Gestione organizzazione** o **Amministratore della sicurezza**.</span><span class="sxs-lookup"><span data-stu-id="f81fd-118">To remove users from the Restricted Users portal, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="f81fd-119">Per l'accesso in sola lettura al portale Utenti con restrizioni, è necessario essere un membro del gruppo di ruoli **Ruolo con autorizzazioni di lettura per la sicurezza**.</span><span class="sxs-lookup"><span data-stu-id="f81fd-119">For read-only access to the Restricted Users portal, you need to be a member of the **Security Reader** role group.</span></span> <span data-ttu-id="f81fd-120">Per altre informazioni sui gruppi di ruoli nel Centro sicurezza e conformità, vedere [Autorizzazioni nel Centro sicurezza e conformità di Office 365](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="f81fd-120">For more information about role groups in the Security & Compliance Center, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="f81fd-121">Un mittente che supera i limiti di posta elettronica in uscita è un indicatore di account compromesso.</span><span class="sxs-lookup"><span data-stu-id="f81fd-121">A sender exceeding the outbound email limits is an indicator of a compromised account.</span></span> <span data-ttu-id="f81fd-122">Prima di rimuovere l'utente dal portale Utenti con restrizioni, assicurarsi di seguire i passaggi necessari per riprendere il controllo dell'account.</span><span class="sxs-lookup"><span data-stu-id="f81fd-122">Before you remove the user from the Restricted Users portal, be sure to follow the required steps to regain control of their account.</span></span> <span data-ttu-id="f81fd-123">Per altre informazioni, vedere [Rispondere a un account di posta elettronica compromesso in Office 365](responding-to-a-compromised-email-account.md).</span><span class="sxs-lookup"><span data-stu-id="f81fd-123">For more information, see [Responding to a compromised email account in Office 365](responding-to-a-compromised-email-account.md).</span></span>

## <a name="use-the-security--compliance-center-to-remove-a-user-from-the-restricted-users-list"></a><span data-ttu-id="f81fd-124">Usare il Centro sicurezza e conformità per rimuovere un utente dall'elenco Utenti con restrizioni</span><span class="sxs-lookup"><span data-stu-id="f81fd-124">Use the Security & Compliance Center to remove a user from the Restricted Users list</span></span>

1. <span data-ttu-id="f81fd-125">Nel Centro sicurezza e conformità, passare a **Gestione delle minacce** \> **Rivedi** \> **Utenti con restrizioni**.</span><span class="sxs-lookup"><span data-stu-id="f81fd-125">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Restricted users**.</span></span>

2. <span data-ttu-id="f81fd-126">Individuare e selezionare l’utente che si desidera sbloccare.</span><span class="sxs-lookup"><span data-stu-id="f81fd-126">Find and select the user that you want to unblock.</span></span> <span data-ttu-id="f81fd-127">Nella colonna **Azioni** fare clic su **Sblocca**.</span><span class="sxs-lookup"><span data-stu-id="f81fd-127">In the **Actions** column, click **Unblock**.</span></span>

3. <span data-ttu-id="f81fd-128">I dettagli relativi all'account al quale è stato impedito l'invio di messaggi saranno visualizzati in un menu a comparsa.</span><span class="sxs-lookup"><span data-stu-id="f81fd-128">A fly-out will go into the details about the account whose sending is restricted.</span></span> <span data-ttu-id="f81fd-129">Si consiglia di consultare i suggerimenti per assicurarsi di eseguire le operazioni appropriate nel caso in cui l'account sia effettivamente compromesso.</span><span class="sxs-lookup"><span data-stu-id="f81fd-129">You should go through the recommendations to ensure you're taking the proper actions in case the account is actually compromised.</span></span> <span data-ttu-id="f81fd-130">Al termine, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f81fd-130">Click **Next** when done.</span></span>

4. <span data-ttu-id="f81fd-131">La schermata successiva include suggerimenti che consentono di evitare compromissioni future.</span><span class="sxs-lookup"><span data-stu-id="f81fd-131">The next screen has recommendations to help prevent future compromise.</span></span> <span data-ttu-id="f81fd-132">L'autenticazione a più fattori (MFA) e la modifica delle password sono buone soluzioni di difesa.</span><span class="sxs-lookup"><span data-stu-id="f81fd-132">Enabling multi-factor authentication (MFA) and changing the passwords are a good defense.</span></span> <span data-ttu-id="f81fd-133">Al termine, fare clic su **Sblocca utente**.</span><span class="sxs-lookup"><span data-stu-id="f81fd-133">Click **Unblock user** when done.</span></span>

5. <span data-ttu-id="f81fd-134">Fare clic su **Sì** per confermare la modifica.</span><span class="sxs-lookup"><span data-stu-id="f81fd-134">Click **Yes** to confirm the change.</span></span>

   > [!NOTE]
   > <span data-ttu-id="f81fd-135">La rimozione delle restrizioni potrebbe richiedere almeno 30 minuti.</span><span class="sxs-lookup"><span data-stu-id="f81fd-135">It may take 30 minutes or more before restrictions are removed.</span></span>

## <a name="verify-the-alert-settings-for-restricted-users"></a><span data-ttu-id="f81fd-136">Verificare le impostazioni di avviso per gli utenti con restrizioni</span><span class="sxs-lookup"><span data-stu-id="f81fd-136">Verify the alert settings for restricted users</span></span>

<span data-ttu-id="f81fd-137">Il criterio di avviso predefinito denominato **Utente al quale è stato impedito di inviare messaggi di posta elettronica** invierà automaticamente una notifica agli amministratori quando gli utenti sono bloccati dall'invio di posta in uscita.</span><span class="sxs-lookup"><span data-stu-id="f81fd-137">The default alert policy named **User restricted from sending email** will automatically notify admins when users are blocked from sending outbound mail.</span></span> <span data-ttu-id="f81fd-138">È possibile verificare queste impostazioni e aggiungere altri utenti a cui inviare una notifica.</span><span class="sxs-lookup"><span data-stu-id="f81fd-138">You can verify these settings and add additional users to notify.</span></span> <span data-ttu-id="f81fd-139">Per ulteriori informazioni sui criteri di avviso, vedere [Criteri di avviso nel Centro sicurezza e conformità](../../compliance/alert-policies.md).</span><span class="sxs-lookup"><span data-stu-id="f81fd-139">For more information about alert policies, see [Alert policies in the security and compliance center](../../compliance/alert-policies.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f81fd-140">Per il corretto funzionamento degli avvisi, la ricerca nel log di controllo deve essere attivata.</span><span class="sxs-lookup"><span data-stu-id="f81fd-140">For alerts to work, audit log search must to be turned on.</span></span> <span data-ttu-id="f81fd-141">Per altre informazioni, vedere [Attivare o disattivare la ricerca nel log di controllo in Office 365](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="f81fd-141">For more information, see [Turn Office 365 audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

1. <span data-ttu-id="f81fd-142">Nel Centro sicurezza e conformità, passare a **Avvisi** \> **Criteri di avviso**.</span><span class="sxs-lookup"><span data-stu-id="f81fd-142">In the Security & Compliance Center, go to **Alerts** \> **Alert policies**.</span></span>

2. <span data-ttu-id="f81fd-143">Individuare e selezionare l’avviso **relativo agli utenti ai quali è stato impedito di inviare posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="f81fd-143">Find an select the **User restricted from sending email** alert.</span></span>

3. <span data-ttu-id="f81fd-144">Nel riquadro a comparsa visualizzato verificare o configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f81fd-144">In the flyout that appears, verify or configure the following settings:</span></span>

   - <span data-ttu-id="f81fd-145">**Stato**: verificare che l'avviso sia attivato ![Attiva](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).</span><span class="sxs-lookup"><span data-stu-id="f81fd-145">**Status**: Verify the alert is turned on ![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).</span></span>

   - <span data-ttu-id="f81fd-146">**Destinatari di posta elettronica**: fare clic su **Modifica** e verificare o configurare le impostazioni seguenti nel riquadro a comparsa **Modifica destinatari** visualizzato:</span><span class="sxs-lookup"><span data-stu-id="f81fd-146">**Email recipients**: Click **Edit** and verify or configure the following settings in the **Edit recipients** flyout that appears:</span></span>

     - <span data-ttu-id="f81fd-147">**Invia notifiche tramite posta elettronica**: verificare che la casella di controllo sia selezionata (**Attivato**).</span><span class="sxs-lookup"><span data-stu-id="f81fd-147">**Send email notifications**: Verify the check box is selected (**On**).</span></span>

     - <span data-ttu-id="f81fd-148">**Destinatari di posta elettronica**: il valore predefinito è **TenantAdmins**, ossia i membri di **Amministratore globale**.</span><span class="sxs-lookup"><span data-stu-id="f81fd-148">**Email recipients**: The default value is **TenantAdmins** (meaning, **Global admin** members).</span></span> <span data-ttu-id="f81fd-149">Per aggiungere altri destinatari, fare clic in un'area vuota della casella.</span><span class="sxs-lookup"><span data-stu-id="f81fd-149">To add more recipients, click in a blank area of the box.</span></span> <span data-ttu-id="f81fd-150">Verrà visualizzato un elenco di destinatari e si può iniziare a digitare un nome per filtrare e selezionare un destinatario.</span><span class="sxs-lookup"><span data-stu-id="f81fd-150">A list of recipients will appear, and you can start typing a name to filter and select a recipient.</span></span> <span data-ttu-id="f81fd-151">È possibile rimuovere un destinatario esistente dalla casella facendo clic sull’![icona Rimuovi](../../media/scc-remove-icon.png) accanto al nome.</span><span class="sxs-lookup"><span data-stu-id="f81fd-151">You can remove an existing recipient from the box by clicking ![Remove icon](../../media/scc-remove-icon.png) next to their name.</span></span>

     - <span data-ttu-id="f81fd-152">**Limite giornaliero per le notifiche**: il valore predefinito è **Nessun limite**, ma è possibile selezionare un limite per il numero massimo di notifiche giornaliere.</span><span class="sxs-lookup"><span data-stu-id="f81fd-152">**Daily notification limit**: The default value is **No limit** but you can select a limit for the maximum number of notifications per day.</span></span>

     <span data-ttu-id="f81fd-153">Al termine, scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f81fd-153">When you're finished, click **Save**.</span></span>

4. <span data-ttu-id="f81fd-154">Nel riquadro a comparsa **relativo agli utenti ai quali è stato impedito di inviare posta elettronica** fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="f81fd-154">Back on the **User restricted from sending email** flyout, click **Close**.</span></span>

## <a name="use-exchange-online-powershell-to-view-and-remove-users-from-the-restricted-users-list"></a><span data-ttu-id="f81fd-155">Usare PowerShell per Exchange Online per visualizzare e rimuovere utenti dall'elenco Utenti con restrizioni</span><span class="sxs-lookup"><span data-stu-id="f81fd-155">Use Exchange Online PowerShell to view and remove users from the Restricted Users list</span></span>

<span data-ttu-id="f81fd-156">Per visualizzare l’elenco di utenti ai quali è stato impedito di inviare posta elettronica, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="f81fd-156">To view this list of users that are restricted from sending email, run the following command:</span></span>

```powershell
Get-BlockedSenderAddress
```

<span data-ttu-id="f81fd-157">Per visualizzare i dettagli di un utente specifico, sostituire \<emailaddress\> con l'indirizzo di posta elettronica corrispondente ed eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="f81fd-157">To view details about a specific user, replace \<emailaddress\> with their email address and run the following command:</span></span>

```powershell
Get-BlockedSenderAddress -SenderAddress <emailaddress>
```

<span data-ttu-id="f81fd-158">Per informazioni dettagliate su sintassi e parametri, vedere [Get-BlockedSenderAddress](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-blockedsenderaddress).</span><span class="sxs-lookup"><span data-stu-id="f81fd-158">For detailed syntax and parameter information, see [Get-BlockedSenderAddress](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-blockedsenderaddress).</span></span>

<span data-ttu-id="f81fd-159">Per rimuovere un utente dall’elenco Utenti con Restrizioni, sostituire \<emailaddress\> con l'indirizzo di posta elettronica corrispondente ed eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="f81fd-159">To remove a user from the Restricted Users list, replace \<emailaddress\> with their email address and run the following command:</span></span>

```powershell
Remove-BlockedSenderAddress -SenderAddress <emailaddress>
```

<span data-ttu-id="f81fd-160">Per informazioni dettagliate su sintassi e parametri, vedere [Remove-BlockedSenderAddress](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-blockedsenderaddress).</span><span class="sxs-lookup"><span data-stu-id="f81fd-160">For detailed syntax and parameter information, see [Remove-BlockedSenderAddress](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-blockedsenderaddress).</span></span>
