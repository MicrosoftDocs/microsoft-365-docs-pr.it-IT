---
title: Rimuovere utenti bloccati dal portale Utenti con restrizioni
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
f1_keywords:
- ms.exch.eac.ActionCenter.Restricted.Users.RestrictedUsers
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 712cfcc1-31e8-4e51-8561-b64258a8f1e5
ms.collection:
- M365-security-compliance
description: Gli amministratori possono scoprire come rimuovere gli utenti dalla pagina Utenti con restrizioni nel portale di Microsoft 365 Defender. Gli utenti vengono aggiunti al portale Utenti con restrizioni se hanno inviato posta indesiderata in uscita, in genere in seguito a una compromissione dell'account.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 924db948103a4d3b45c499f433961762a45931af
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2021
ms.locfileid: "53082853"
---
# <a name="remove-blocked-users-from-the-restricted-users-portal-in-microsoft-365"></a><span data-ttu-id="eb63b-104">Rimuovere utenti bloccati dal portale Utenti con restrizioni in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="eb63b-104">Remove blocked users from the Restricted users portal in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="eb63b-105">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="eb63b-105">**Applies to**</span></span>
- [<span data-ttu-id="eb63b-106">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="eb63b-106">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="eb63b-107">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="eb63b-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="eb63b-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="eb63b-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="eb63b-109">Se un utente supera uno dei limiti di invio in uscita, come specificato nei [limiti di servizio](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) o nei [criteri di posta indesiderata in uscita](configure-the-outbound-spam-policy.md), l'utente non può inviare messaggi di posta elettronica, ma può continuare a riceverne.</span><span class="sxs-lookup"><span data-stu-id="eb63b-109">If a user exceeds one of the outbound sending limits as specified in [the service limits](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) or in [outbound spam policies](configure-the-outbound-spam-policy.md), the user is restricted from sending email, but they can still receive email.</span></span>

<span data-ttu-id="eb63b-110">L'utente viene aggiunto alla pagina **Utenti con restrizioni** nel portale di Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="eb63b-110">The user is added to the **Restricted users** page in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="eb63b-111">Quando prova a inviare messaggi di posta elettronica, il messaggio viene restituito in un rapporto di mancato recapito, noto anche come NDR o notifica di mancato recapito, con il codice di errore [5.1.8](/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/fix-error-code-5-1-8-in-exchange-online) e il testo seguente:</span><span class="sxs-lookup"><span data-stu-id="eb63b-111">When they try to send email, the message is returned in a non-delivery report (also known as an NDR or bounce messages) with the error code [5.1.8](/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/fix-error-code-5-1-8-in-exchange-online) and the following text:</span></span>

> <span data-ttu-id="eb63b-112">"Non è stato possibile recapitare il messaggio perché l'utente non è stato riconosciuto come mittente valido.</span><span class="sxs-lookup"><span data-stu-id="eb63b-112">"Your message couldn't be delivered because you weren't recognized as a valid sender.</span></span> <span data-ttu-id="eb63b-113">La causa più comune di questo problema è che l'indirizzo di posta elettronica sia sospettato di inviare posta indesiderata e che non sia più autorizzato a inviare messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="eb63b-113">The most common reason for this is that your email address is suspected of sending spam and it's no longer allowed to send email.</span></span>  <span data-ttu-id="eb63b-114">Contattare l'amministratore della posta elettronica per ricevere assistenza.</span><span class="sxs-lookup"><span data-stu-id="eb63b-114">Contact  your email admin for assistance.</span></span> <span data-ttu-id="eb63b-115">Il server remoto ha restituito l'errore "550 5.1.8 Access denied, bad outbound sender."</span><span class="sxs-lookup"><span data-stu-id="eb63b-115">Remote Server returned '550 5.1.8 Access denied, bad outbound sender."</span></span>

<span data-ttu-id="eb63b-116">Gli amministratori possono rimuovere gli utenti dalla pagina Utenti con restrizioni in Microsoft 365 Defender o in PowerShell per Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="eb63b-116">Admins can remove users from the Restricted users page in the Microsoft 365 Defender or in Exchange Online PowerShell.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="eb63b-117">Che cosa è necessario sapere prima di iniziare?</span><span class="sxs-lookup"><span data-stu-id="eb63b-117">What do you need to know before you begin?</span></span>

- <span data-ttu-id="eb63b-118">Per aprire il portale di Microsoft 365 Defender, andare alla pagina <https://security.microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="eb63b-118">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="eb63b-119">Per passare direttamente alla pagina **Utenti con restrizioni**, usare <https://security.microsoft.com/restrictedusers>.</span><span class="sxs-lookup"><span data-stu-id="eb63b-119">Too go directly to the **Restricted users** page, use <https://security.microsoft.com/restrictedusers>.</span></span>

- <span data-ttu-id="eb63b-120">Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="eb63b-120">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="eb63b-121">Prima di eseguire le procedure descritte in questo articolo, occorre disporre delle autorizzazioni in **Exchange Online**:</span><span class="sxs-lookup"><span data-stu-id="eb63b-121">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="eb63b-122">Per rimuovere gli utenti dal portale Utenti con restrizioni è necessario essere membri dei gruppi di ruoli **Gestione organizzazione** o **Amministratore della sicurezza**.</span><span class="sxs-lookup"><span data-stu-id="eb63b-122">To remove users from the Restricted users portal, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="eb63b-123">Per l'accesso in sola lettura al portale Utenti con restrizioni, è necessario essere un membro del gruppo di ruoli **Amministratore con autorizzazioni di lettura globali** o **Amministratore che legge i dati di sicurezza**.</span><span class="sxs-lookup"><span data-stu-id="eb63b-123">For read-only access to the Restricted users portal, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="eb63b-124">Per altre informazioni, vedere [Autorizzazioni in Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="eb63b-124">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="eb63b-125">L'aggiunta di utenti al ruolo di Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft 365 fornisce agli utenti le autorizzazioni necessarie _e_ le autorizzazioni per altre funzionalità di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="eb63b-125">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="eb63b-126">Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="eb63b-126">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="eb63b-127">Anche il gruppo di ruoli di **Gestione organizzazione sola visualizzazione** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) offre inoltre l'accesso di sola lettura a tale funzionalità.</span><span class="sxs-lookup"><span data-stu-id="eb63b-127">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="eb63b-128">Un mittente che supera i limiti di posta elettronica in uscita è un indicatore di account compromesso.</span><span class="sxs-lookup"><span data-stu-id="eb63b-128">A sender exceeding the outbound email limits is an indicator of a compromised account.</span></span> <span data-ttu-id="eb63b-129">Prima di rimuovere l'utente dal portale Utenti con restrizioni, assicurarsi di seguire i passaggi necessari per riprendere il controllo dell'account.</span><span class="sxs-lookup"><span data-stu-id="eb63b-129">Before you remove the user from the Restricted users portal, be sure to follow the required steps to regain control of their account.</span></span> <span data-ttu-id="eb63b-130">Per altre informazioni, vedere [Rispondere a un account di posta elettronica compromesso in Office 365](responding-to-a-compromised-email-account.md).</span><span class="sxs-lookup"><span data-stu-id="eb63b-130">For more information, see [Responding to a compromised email account in Office 365](responding-to-a-compromised-email-account.md).</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-a-user-from-the-restricted-users-list"></a><span data-ttu-id="eb63b-131">Usare il portale di Microsoft 365 Defender per rimuovere un utente dall'elenco Utenti con restrizioni</span><span class="sxs-lookup"><span data-stu-id="eb63b-131">Use the Microsoft 365 Defender portal to remove a user from the Restricted users list</span></span>

1. <span data-ttu-id="eb63b-132">Nel portale di Microsoft 365 Defender, passare a **Posta elettronica e collaborazione**  >  **Rivedi** >  **Utenti con restrizioni**.</span><span class="sxs-lookup"><span data-stu-id="eb63b-132">In the Microsoft 365 Defender portal, go to **Email & collaboration** > **Review** > **Restricted users**.</span></span>

2. <span data-ttu-id="eb63b-133">Nella pagina **Utenti con restrizioni** individuare e selezionare l'utente che si desidera sbloccare facendo clic sull'utente.</span><span class="sxs-lookup"><span data-stu-id="eb63b-133">On the **Restricted users** page, find and select the user that you want to unblock by clicking on the user.</span></span>

3. <span data-ttu-id="eb63b-134">Fare clic sull'azione **Sblocca** che viene visualizzata.</span><span class="sxs-lookup"><span data-stu-id="eb63b-134">Click the **Unblock** action that appears.</span></span>

4. <span data-ttu-id="eb63b-135">Nel riquadro a comparsa **Sblocca utente** visualizzato leggere i dettagli sull'account con restrizioni.</span><span class="sxs-lookup"><span data-stu-id="eb63b-135">In the **Unblock user** flyout that appears, read the details about the restricted account.</span></span> <span data-ttu-id="eb63b-136">Si consiglia di consultare i suggerimenti per assicurarsi di eseguire le operazioni appropriate nel caso in cui l'account sia compromesso.</span><span class="sxs-lookup"><span data-stu-id="eb63b-136">You should go through the recommendations to ensure you're taking the proper actions in case the account is compromised.</span></span>

   <span data-ttu-id="eb63b-137">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="eb63b-137">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="eb63b-138">La schermata successiva include suggerimenti che consentono di evitare compromissioni future.</span><span class="sxs-lookup"><span data-stu-id="eb63b-138">The next screen has recommendations to help prevent future compromise.</span></span> <span data-ttu-id="eb63b-139">L'abilitazione dell'autenticazione a più fattori (MFA) e la reimpostazione della password sono buone soluzioni di difesa.</span><span class="sxs-lookup"><span data-stu-id="eb63b-139">Enabling multi-factor authentication (MFA) and resetting the password are a good defense.</span></span>

   <span data-ttu-id="eb63b-140">Al termine, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="eb63b-140">When you're finished, click **Submit**.</span></span>

6. <span data-ttu-id="eb63b-141">Fare clic su **Sì** per confermare la modifica.</span><span class="sxs-lookup"><span data-stu-id="eb63b-141">Click **Yes** to confirm the change.</span></span>

   > [!NOTE]
   > <span data-ttu-id="eb63b-142">La rimozione di tutte le restrizioni utente può richiedere fino a 24 ore.</span><span class="sxs-lookup"><span data-stu-id="eb63b-142">It might take up to 24 hours for all restrictions to be removed from the user.</span></span>

## <a name="verify-the-alert-settings-for-restricted-users"></a><span data-ttu-id="eb63b-143">Verificare le impostazioni di avviso per gli utenti con restrizioni</span><span class="sxs-lookup"><span data-stu-id="eb63b-143">Verify the alert settings for restricted users</span></span>

<span data-ttu-id="eb63b-144">Il criterio di avviso predefinito denominato **Utente al quale è stato impedito di inviare messaggi di posta elettronica** invierà automaticamente una notifica agli amministratori quando gli utenti sono bloccati dall'invio di posta in uscita.</span><span class="sxs-lookup"><span data-stu-id="eb63b-144">The default alert policy named **User restricted from sending email** will automatically notify admins when users are blocked from sending outbound mail.</span></span> <span data-ttu-id="eb63b-145">È possibile verificare queste impostazioni e aggiungere altri utenti a cui inviare una notifica.</span><span class="sxs-lookup"><span data-stu-id="eb63b-145">You can verify these settings and add additional users to notify.</span></span> <span data-ttu-id="eb63b-146">Per ulteriori informazioni sui criteri di avviso, vedere [Criteri di avviso in Microsoft 365](../../compliance/alert-policies.md).</span><span class="sxs-lookup"><span data-stu-id="eb63b-146">For more information about alert policies, see [Alert policies in Microsoft 365](../../compliance/alert-policies.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eb63b-147">Per il corretto funzionamento degli avvisi, la ricerca nel log di controllo deve essere attivata.</span><span class="sxs-lookup"><span data-stu-id="eb63b-147">For alerts to work, audit log search must to be turned on.</span></span> <span data-ttu-id="eb63b-148">Per altre informazioni, vedere [Attivare o disattivare la ricerca nel log di controllo](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="eb63b-148">For more information, see [Turn the audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

1. <span data-ttu-id="eb63b-149">Nel portale di Microsoft 365 Defender, passare a **Posta elettronica e collaborazione** \> **Rivedi**\> **Criterio di avviso**.</span><span class="sxs-lookup"><span data-stu-id="eb63b-149">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Policies & rules** \> **Alert policy**.</span></span>

2. <span data-ttu-id="eb63b-150">Nella pagina **Criteri di avviso**, trovare e selezionare l'avviso relativo agli **utenti ai quali è stato impedito di inviare posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="eb63b-150">On the **Alert policy** page, find and select the alert named **User restricted from sending email**.</span></span> <span data-ttu-id="eb63b-151">È possibile ordinare i criteri in base al nome o usare la **casella di ricerca** per trovare il criterio.</span><span class="sxs-lookup"><span data-stu-id="eb63b-151">You can sort the policies by name, or use the **Search box** to find the policy.</span></span>

3. <span data-ttu-id="eb63b-152">Nel riquadro a comparsa visualizzato relativo agli **utenti ai quali è stato impedito di inviare posta elettronica** verificare o configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="eb63b-152">In the **User restricted from sending email** flyout that appears, verify or configure the following settings:</span></span>
   - <span data-ttu-id="eb63b-153">**Stato**: verificare che l'avviso sia attivato ![Attiva](../../media/scc-toggle-on.png).</span><span class="sxs-lookup"><span data-stu-id="eb63b-153">**Status**: Verify the alert is turned on ![Toggle on](../../media/scc-toggle-on.png).</span></span>
   - <span data-ttu-id="eb63b-154">**Destinatari di posta elettronica**: fare clic su **Modifica** e verificare o configurare le impostazioni seguenti nel riquadro a comparsa **Modifica destinatari** visualizzato:</span><span class="sxs-lookup"><span data-stu-id="eb63b-154">**Email recipients**: Click **Edit** and verify or configure the following settings in the **Edit recipients** flyout that appears:</span></span>
     - <span data-ttu-id="eb63b-155">**Invia notifiche tramite posta elettronica**: verificare sia selezionato (**Attivato**).</span><span class="sxs-lookup"><span data-stu-id="eb63b-155">**Send email notifications**: Verify this is selected (**On**).</span></span>
     - <span data-ttu-id="eb63b-156">**Destinatari di posta elettronica**: il valore predefinito è **TenantAdmins**, ossia i membri di **Amministratore globale**.</span><span class="sxs-lookup"><span data-stu-id="eb63b-156">**Email recipients**: The default value is **TenantAdmins** (meaning, **Global admin** members).</span></span> <span data-ttu-id="eb63b-157">Per aggiungere altri destinatari, fare clic in un'area vuota della casella.</span><span class="sxs-lookup"><span data-stu-id="eb63b-157">To add more recipients, click in a blank area of the box.</span></span> <span data-ttu-id="eb63b-158">Verrà visualizzato un elenco di destinatari e si può iniziare a digitare un nome per filtrare e selezionare un destinatario.</span><span class="sxs-lookup"><span data-stu-id="eb63b-158">A list of recipients will appear, and you can start typing a name to filter and select a recipient.</span></span> <span data-ttu-id="eb63b-159">È possibile rimuovere un destinatario esistente dalla casella facendo clic sull’![icona Rimuovi](../../media/m365-cc-sc-remove-selection-icon.png) accanto al nome.</span><span class="sxs-lookup"><span data-stu-id="eb63b-159">You can remove an existing recipient from the box by clicking ![Remove icon](../../media/m365-cc-sc-remove-selection-icon.png) next to their name.</span></span>
     - <span data-ttu-id="eb63b-160">**Limite giornaliero per le notifiche**: il valore predefinito è **Nessun limite**, ma è possibile selezionare un limite per il numero massimo di notifiche giornaliere.</span><span class="sxs-lookup"><span data-stu-id="eb63b-160">**Daily notification limit**: The default value is **No limit** but you can select a limit for the maximum number of notifications per day.</span></span>

     <span data-ttu-id="eb63b-161">Al termine, scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="eb63b-161">When you're finished, click **Save**.</span></span>

4. <span data-ttu-id="eb63b-162">Nel riquadro a comparsa **relativo agli utenti ai quali è stato impedito di inviare posta elettronica** fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="eb63b-162">Back on the **User restricted from sending email** flyout, click **Close**.</span></span>

## <a name="use-exchange-online-powershell-to-view-and-remove-users-from-the-restricted-users-list"></a><span data-ttu-id="eb63b-163">Usare PowerShell per Exchange Online per visualizzare e rimuovere utenti dall'elenco Utenti con restrizioni</span><span class="sxs-lookup"><span data-stu-id="eb63b-163">Use Exchange Online PowerShell to view and remove users from the Restricted users list</span></span>

<span data-ttu-id="eb63b-164">Per visualizzare l’elenco di utenti ai quali è stato impedito di inviare posta elettronica, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="eb63b-164">To view this list of users that are restricted from sending email, run the following command:</span></span>

```powershell
Get-BlockedSenderAddress
```

<span data-ttu-id="eb63b-165">Per visualizzare i dettagli di un utente specifico, sostituire \<emailaddress\> con l'indirizzo di posta elettronica corrispondente ed eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="eb63b-165">To view details about a specific user, replace \<emailaddress\> with their email address and run the following command:</span></span>

```powershell
Get-BlockedSenderAddress -SenderAddress <emailaddress>
```

<span data-ttu-id="eb63b-166">Per informazioni dettagliate su sintassi e parametri, vedere [Get-BlockedSenderAddress](/powershell/module/exchange/get-blockedsenderaddress).</span><span class="sxs-lookup"><span data-stu-id="eb63b-166">For detailed syntax and parameter information, see [Get-BlockedSenderAddress](/powershell/module/exchange/get-blockedsenderaddress).</span></span>

<span data-ttu-id="eb63b-167">Per rimuovere un utente dall'elenco Utenti con Restrizioni, sostituire \<emailaddress\> con l'indirizzo di posta elettronica corrispondente ed eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="eb63b-167">To remove a user from the Restricted users list, replace \<emailaddress\> with their email address and run the following command:</span></span>

```powershell
Remove-BlockedSenderAddress -SenderAddress <emailaddress>
```

<span data-ttu-id="eb63b-168">Per informazioni dettagliate su sintassi e parametri, vedere [Remove-BlockedSenderAddress](/powershell/module/exchange/remove-blockedsenderaddress).</span><span class="sxs-lookup"><span data-stu-id="eb63b-168">For detailed syntax and parameter information, see [Remove-BlockedSenderAddress](/powershell/module/exchange/remove-blockedsenderaddress).</span></span>
