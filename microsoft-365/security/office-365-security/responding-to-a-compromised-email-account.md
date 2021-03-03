---
title: Rispondere a un account di posta elettronica compromesso
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.collection:
- o365_security_incident_response
- M365-security-compliance
- m365solution-smb
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
localization_priority: Priority
search.appverid:
- MET150
description: Informazioni su come riconoscere e rispondere a un account di posta elettronica compromesso usando gli strumenti disponibili in Microsoft 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5dfb40c195cb9df9c8f2ac5d1cfbacdda022d416
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406725"
---
# <a name="responding-to-a-compromised-email-account"></a><span data-ttu-id="a2069-103">Rispondere a un account di posta elettronica compromesso</span><span class="sxs-lookup"><span data-stu-id="a2069-103">Responding to a Compromised Email Account</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="a2069-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="a2069-104">**Applies to**</span></span>
- [<span data-ttu-id="a2069-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="a2069-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="a2069-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="a2069-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="a2069-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a2069-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="a2069-108">**Riepilogo** Informazioni su come riconoscere e rispondere a un account di posta elettronica compromesso in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a2069-108">**Summary** Learn how to recognize and respond to a compromised email account in Microsoft 365.</span></span>

## <a name="what-is-a-compromised-email-account-in-microsoft-365"></a><span data-ttu-id="a2069-109">Che cos'è un account di posta elettronica compromesso in Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="a2069-109">What is a Compromised Email Account in Microsoft 365?</span></span>

<span data-ttu-id="a2069-110">L’accesso alle cassette postali, dati e altri servizi di Microsoft 365 viene controllato tramite l’uso di credenziali, ad esempio un nome utente e la password o il PIN.</span><span class="sxs-lookup"><span data-stu-id="a2069-110">Access to Microsoft 365 mailboxes, data and other services, is controlled through the use of credentials, for example a user name and password or PIN.</span></span> <span data-ttu-id="a2069-111">Quando un utente diverso da quello previsto sottrae queste credenziali, queste sono considerate compromesse.</span><span class="sxs-lookup"><span data-stu-id="a2069-111">When someone other than the intended user steals those credentials, the stolen credentials are considered to be compromised.</span></span> <span data-ttu-id="a2069-112">Con queste l'utente malintenzionato può accedere come utente originale ed effettuare operazioni illegali.</span><span class="sxs-lookup"><span data-stu-id="a2069-112">With them the attacker can sign in as the original user and perform illicit actions.</span></span>
<span data-ttu-id="a2069-113">Usando le credenziali rubate, l'autore dell'attacco può accedere alla cassetta postale di Microsoft 365, alle cartelle di SharePoint o ai file in OneDrive dell'utente.</span><span class="sxs-lookup"><span data-stu-id="a2069-113">Using the stolen credentials, the attacker can access the user's Microsoft 365 mailbox, SharePoint folders, or files in the user's OneDrive.</span></span> <span data-ttu-id="a2069-114">Un’operazione vista comunemente è l’invio da parte del pirata informatico di messaggi di posta elettronica a destinatari sia interni che esterni all'organizzazione dell'utente originale.</span><span class="sxs-lookup"><span data-stu-id="a2069-114">One action commonly seen is the attacker sending emails as the original user to recipients both inside and outside of the organization.</span></span> <span data-ttu-id="a2069-115">Quando un utente malintenzionato invia dei dati tramite messaggi di posta elettronica a destinatari esterni, si chiama esfiltrazione di dati.</span><span class="sxs-lookup"><span data-stu-id="a2069-115">When the attacker emails data to external recipients, this is called data exfiltration.</span></span>

## <a name="symptoms-of-a-compromised-microsoft-email-account"></a><span data-ttu-id="a2069-116">Sintomi di un account di posta elettronica Microsoft compromesso</span><span class="sxs-lookup"><span data-stu-id="a2069-116">Symptoms of a Compromised Microsoft Email Account</span></span>

<span data-ttu-id="a2069-117">Gli utenti potrebbero notare e segnalare attività insolite nelle proprie cassette postali di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a2069-117">Users might notice and report unusual activity in their Microsoft 365 mailboxes.</span></span> <span data-ttu-id="a2069-118">Ecco i sintomi più comuni:</span><span class="sxs-lookup"><span data-stu-id="a2069-118">Here are some common symptoms:</span></span>

- <span data-ttu-id="a2069-119">Attività sospette, ad esempio messaggi di posta elettronica mancanti o eliminati.</span><span class="sxs-lookup"><span data-stu-id="a2069-119">Suspicious activity, such as missing or deleted emails.</span></span>

- <span data-ttu-id="a2069-120">Altri utenti potrebbero ricevere messaggi di posta elettronica dall'account compromesso senza che sia presente il messaggio di posta elettronica corrispondente nella cartella **Posta inviata** del mittente.</span><span class="sxs-lookup"><span data-stu-id="a2069-120">Other users might receive emails from the compromised account without the corresponding email existing in the **Sent Items** folder of the sender.</span></span>

- <span data-ttu-id="a2069-121">La presenza di regole posta in arrivo che non sono state create dal proprietario o dall'amministratore.</span><span class="sxs-lookup"><span data-stu-id="a2069-121">The presence of inbox rules that weren't created by the intended user or the administrator.</span></span> <span data-ttu-id="a2069-122">Queste regole possono inoltrare messaggi di posta elettronica a indirizzi sconosciuti o spostarli automaticamente nelle cartelle di **Note**, **Posta indesiderata**, o **Sottoscrizioni RSS**.</span><span class="sxs-lookup"><span data-stu-id="a2069-122">These rules may automatically forward emails to unknown addresses or move them to the **Notes**, **Junk Email**, or **RSS Subscriptions** folders.</span></span>

- <span data-ttu-id="a2069-123">Il nome visualizzato dell'utente può essere modificato nell'elenco indirizzi globale.</span><span class="sxs-lookup"><span data-stu-id="a2069-123">The user's display name might be changed in the Global Address List.</span></span>

- <span data-ttu-id="a2069-124">Non è possibile inviare messaggi di posta elettronica dalla cassetta postale dell'utente.</span><span class="sxs-lookup"><span data-stu-id="a2069-124">The user's mailbox is blocked from sending email.</span></span>

- <span data-ttu-id="a2069-125">Le cartelle Posta inviata o Posta eliminata in Microsoft Outlook o Outlook sul web (precedentemente noto come Outlook Web App) contengono messaggi presenti comunemente in un account oggetto di un attacco, ad esempio "Mi sono bloccato a Milano, invia denaro."</span><span class="sxs-lookup"><span data-stu-id="a2069-125">The Sent or Deleted Items folders in Microsoft Outlook or Outlook on the web (formerly known as Outlook Web App) contain common hacked-account messages, such as "I'm stuck in London, send money."</span></span>

- <span data-ttu-id="a2069-126">Modifiche al profilo insolite, ad esempio un aggiornamento del nome, numero di telefono o codice postale.</span><span class="sxs-lookup"><span data-stu-id="a2069-126">Unusual profile changes, such as the name, the telephone number, or the postal code were updated.</span></span>

- <span data-ttu-id="a2069-127">Modifiche insolite alle credenziali, ad esempio, sono richiesti varie modifiche alla password.</span><span class="sxs-lookup"><span data-stu-id="a2069-127">Unusual credential changes, such as multiple password changes are required.</span></span>

- <span data-ttu-id="a2069-128">È stato aggiunto di recente un inoltro della posta di Outlook.</span><span class="sxs-lookup"><span data-stu-id="a2069-128">Mail forwarding was recently added.</span></span>

- <span data-ttu-id="a2069-129">È stata aggiunta una firma insolita, ad esempio una firma bancaria falsa o la fima per una ricetta medica.</span><span class="sxs-lookup"><span data-stu-id="a2069-129">An unusual signature was recently added, such as a fake banking signature or a prescription drug signature.</span></span>

<span data-ttu-id="a2069-130">Se un utente segnala qualsiasi dei sintomi precedenti, è necessario eseguire ulteriori analisi.</span><span class="sxs-lookup"><span data-stu-id="a2069-130">If a user reports any of the above symptoms, you should perform further investigation.</span></span> <span data-ttu-id="a2069-131">Il Centro sicurezza e conformità di Microsoft 365 e il portale di Azure offfrono strumenti che consentono di analizzare le attività di un account utente che si sospetta potrebbe essere compromesso.</span><span class="sxs-lookup"><span data-stu-id="a2069-131">The Microsoft 365 Security & Compliance Center and the Azure Portal offer tools to help you investigate the activity of a user account that you suspect may be compromised.</span></span>

- <span data-ttu-id="a2069-132">**Log di controllo unificati nel Centro sicurezza e conformità**: esaminare tutte le attività nell'account sospetto filtrando i risultati per l'intervallo di date che si estendono da immediatamente prima delle attività sospette alla data attuale.</span><span class="sxs-lookup"><span data-stu-id="a2069-132">**Unified Audit Logs in the Security & Compliance Center**: Review all the activities for the suspected account by filtering the results for the date range spanning from immediately before the suspicious activity occurred to the current date.</span></span> <span data-ttu-id="a2069-133">Non filtrare le attività durante la ricerca.</span><span class="sxs-lookup"><span data-stu-id="a2069-133">Do not filter on the activities during the search.</span></span>

- <span data-ttu-id="a2069-134">**Log di controllo dell'amministratore nell'interfaccia di amministrazione di Exchange**: in Exchange Online è possibile usare l'interfaccia di amministrazione di Exchange per cercare e visualizzare voci nel log di controllo dell'amministratore.</span><span class="sxs-lookup"><span data-stu-id="a2069-134">**Admin Audit logs in the EAC**: In Exchange Online, you can use the Exchange admin center (EAC) to search for and view entries in the administrator audit log.</span></span> <span data-ttu-id="a2069-135">Il log di controllo dell'amministratore registra operazioni specifiche, basate su cmdlet di PowerShell per Exchange Online, eseguite dagli amministratori e dagli utenti che dispongono di privilegi amministrativi.</span><span class="sxs-lookup"><span data-stu-id="a2069-135">The administrator audit log records specific actions, based on Exchange Online PowerShell cmdlets, performed by administrators and users who have been assigned administrative privileges.</span></span> <span data-ttu-id="a2069-136">Le voci nel registro di controllo dell'amministratore forniscono informazioni sul cmdlet eseguito, sui parametri utilizzati, sull'utente che ha eseguito il cmdlet e sugli oggetti coinvolti.</span><span class="sxs-lookup"><span data-stu-id="a2069-136">Entries in the administrator audit log provide you with information about what cmdlet was run, which parameters were used, who ran the cmdlet, and what objects were affected.</span></span>

- <span data-ttu-id="a2069-137">**Log di accesso di Azure AD e altri report sui rischi disponibili nel portale di Azure AD**: esaminare i valori nelle colonne seguenti:</span><span class="sxs-lookup"><span data-stu-id="a2069-137">**Azure AD Sign-in logs and other risk reports in the Azure AD portal**: Examine the values in these columns:</span></span>

  - <span data-ttu-id="a2069-138">Esaminare l'indirizzo IP</span><span class="sxs-lookup"><span data-stu-id="a2069-138">Review IP address</span></span>
  - <span data-ttu-id="a2069-139">Posizioni di accesso</span><span class="sxs-lookup"><span data-stu-id="a2069-139">sign-in locations</span></span>
  - <span data-ttu-id="a2069-140">Orari di accesso</span><span class="sxs-lookup"><span data-stu-id="a2069-140">sign-in times</span></span>
  - <span data-ttu-id="a2069-141">Esito dell’accesso</span><span class="sxs-lookup"><span data-stu-id="a2069-141">sign-in success or failure</span></span>

## <a name="how-to-secure-and-restore-email-function-to-a-suspected-compromised-microsoft-365-account-and-mailbox"></a><span data-ttu-id="a2069-142">Come proteggere e ripristinare la funzione di posta elettronica in un potenziale account e cassetta postale di Microsoft 365 compromessi.</span><span class="sxs-lookup"><span data-stu-id="a2069-142">How to secure and restore email function to a suspected compromised Microsoft 365 account and mailbox</span></span>

> [!VIDEO https://videoplayercdn.osi.office.net/hub/?csid=ux-cms-en-us-msoffice&uuid=RE2jvOb&AutoPlayVideo=false]

<span data-ttu-id="a2069-143">Anche l’accesso all’account è stato riacquisito rapidamente, un utente malintenzionato potrebbe aver aggiunto voci “back-door” che gli permettono di riprendere il controllo dell'account.</span><span class="sxs-lookup"><span data-stu-id="a2069-143">Even after you've regained access to your account, the attacker may have added back-door entries that enable the attacker to resume control of the account.</span></span>

<span data-ttu-id="a2069-144">È necessario eseguire la procedura seguente per accedere all'account il prima possibile per assicurarsi che l’autore dell’attacco non riprenda il controllo dell’account.</span><span class="sxs-lookup"><span data-stu-id="a2069-144">You must do all the following steps to regain access to your account the sooner the better to make sure that the hijacker doesn't resume control your account.</span></span> <span data-ttu-id="a2069-145">Questa procedura consente di rimuovere le voci “back-door” che l’autore dell’attacco potrebbe aver aggiunto all’account.</span><span class="sxs-lookup"><span data-stu-id="a2069-145">These steps help you remove any back-door entries that the hijacker may have added to your account.</span></span> <span data-ttu-id="a2069-146">Dopo avere eseguito questi passaggi, è consigliabile eseguire una scansione con un programma antivirus per verificare che il computer non sia compromesso.</span><span class="sxs-lookup"><span data-stu-id="a2069-146">After you do these steps, we recommend that you run a virus scan to make sure that your computer isn't compromised.</span></span>

### <a name="step-1-reset-the-users-password"></a><span data-ttu-id="a2069-147">Passaggio 1: Reimpostare la password dell’utente.</span><span class="sxs-lookup"><span data-stu-id="a2069-147">Step 1 Reset the user's password</span></span>

<span data-ttu-id="a2069-148">Seguire le procedure in [reimpostare la password per un utente ](../../admin/add-users/reset-passwords.md#reset-my-admin-password).</span><span class="sxs-lookup"><span data-stu-id="a2069-148">Follow the procedures in [Reset a business password for someone](../../admin/add-users/reset-passwords.md#reset-my-admin-password).</span></span>

> [!IMPORTANT]
>
> - <span data-ttu-id="a2069-149">Non inviare la nuova password per l'utente desiderato tramite posta elettronica, poiché l’utente malintenzionato potrebbe ancora avere accesso alla cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="a2069-149">Do not send the new password to the intended user through email as the attacker still has access to the mailbox at this point.</span></span>
>
> - <span data-ttu-id="a2069-150">Assicurarsi che la password sia complessa e che contenga lettere maiuscole e minuscole, almeno un numero e almeno un carattere speciale.</span><span class="sxs-lookup"><span data-stu-id="a2069-150">Make sure that the password is strong and that it contains upper and lowercase letters, at least one number, and at least one special character.</span></span>
>
> - <span data-ttu-id="a2069-151">Non riutilizzare le cinque password più recenti.</span><span class="sxs-lookup"><span data-stu-id="a2069-151">Don't reuse any of your last five passwords.</span></span> <span data-ttu-id="a2069-152">Anche se il requisito di cronologia delle password consente di riutilizzare una password più recente, è necessario sceglierla in modo che un utente malintenzionato non possa indovinarla.</span><span class="sxs-lookup"><span data-stu-id="a2069-152">Even though the password history requirement lets you reuse a more recent password, you should select something that the attacker can't guess.</span></span>
>
> - <span data-ttu-id="a2069-153">Se l'identità dell'utente locale è federata con Microsoft 365, è necessario cambiare la password locale e quindi informare l'amministratore della violazione.</span><span class="sxs-lookup"><span data-stu-id="a2069-153">If your on-premises identity is federated with Microsoft 365, you must change your password on-premises, and then you must notify your administrator of the compromise.</span></span>
>
> - <span data-ttu-id="a2069-154">Assicurati di aggiornare le password dell'app.</span><span class="sxs-lookup"><span data-stu-id="a2069-154">Be sure to update app passwords.</span></span> <span data-ttu-id="a2069-155">Le password dell'app non vengono automaticamente revocate quando si reimposta la password di un account utente.</span><span class="sxs-lookup"><span data-stu-id="a2069-155">App passwords aren't automatically revoked when a user account password reset.</span></span> <span data-ttu-id="a2069-156">L'utente deve eliminare le password dell'app esistenti e crearne nuove.</span><span class="sxs-lookup"><span data-stu-id="a2069-156">The user should delete existing app passwords and create new ones.</span></span> <span data-ttu-id="a2069-157">Per istruzioni, vedere [creare ed eliminare password per le app dalla pagina Verifica di sicurezza aggiuntiva](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-app-passwords#create-and-delete-app-passwords-from-the-additional-security-verification-page).</span><span class="sxs-lookup"><span data-stu-id="a2069-157">For instructions, see [Create and delete app passwords from the Additional security verification page](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-app-passwords#create-and-delete-app-passwords-from-the-additional-security-verification-page).</span></span>
>
> - <span data-ttu-id="a2069-158">È altamente consigliabile abilitare l'autenticazione a più fattori (MFA) per evitare violazioni, soprattutto per gli account con privilegi amministrativi.</span><span class="sxs-lookup"><span data-stu-id="a2069-158">We highly recommended that you enable Multi-Factor Authentication (MFA) in order to prevent compromise, especially for accounts with administrative privileges.</span></span> <span data-ttu-id="a2069-159">Per maggiori dettagli sull’autenticazione a più fattori, visitare [Configurare l’autenticazione a più fattori](../../admin/security-and-compliance/set-up-multi-factor-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="a2069-159">To learn more about MFA, go to [Set up multi-factor authentication](../../admin/security-and-compliance/set-up-multi-factor-authentication.md).</span></span>

### <a name="step-2-remove-suspicious-email-forwarding-addresses"></a><span data-ttu-id="a2069-160">Passaggio 2: Rimuovere indirizzi di inoltro della posta elettronica</span><span class="sxs-lookup"><span data-stu-id="a2069-160">Step 2 Remove suspicious email forwarding addresses</span></span>

1. <span data-ttu-id="a2069-161">Apri l’interfaccia di amministrazione di Microsoft 365 in <https://admin.microsoft.com></span><span class="sxs-lookup"><span data-stu-id="a2069-161">Open the Microsoft 365 admin center at <https://admin.microsoft.com></span></span>

2. <span data-ttu-id="a2069-162">Passa a **Utenti** \> **Utenti attivi**.</span><span class="sxs-lookup"><span data-stu-id="a2069-162">Go to **Users** \> **Active users**.</span></span> <span data-ttu-id="a2069-163">Trova l'account utente in questione e seleziona l'utente (riga) senza selezionare la casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="a2069-163">Find the user account in question, and select the user (row) without selecting the checkbox.</span></span>

3. <span data-ttu-id="a2069-164">Nel riquadro a comparsa dei dettagli visualizzato, seleziona la scheda **Posta**.</span><span class="sxs-lookup"><span data-stu-id="a2069-164">In the details flyout that appears, select the **Mail** tab.</span></span>

4. <span data-ttu-id="a2069-165">Se il valore nella sezione **Inoltro e-mail** è **Applicato**, fai clic su **Gestisci inoltro e-mail**.</span><span class="sxs-lookup"><span data-stu-id="a2069-165">If the value in the **Email forwarding** section is **Applied**, click **Manage email forwarding**.</span></span> <span data-ttu-id="a2069-166">Nel riquadro a comparsa **Gestisci inoltro e-mail** visualizzato, deseleziona **Inoltra tutte le e-mail inviate a questa cassetta postale**, e fai clic su **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="a2069-166">In the **Manage email forwarding** flyout that appears, clear **Forward all email sent to this mailbox**, and then click **Save changes**.</span></span>

### <a name="step-3-disable-any-suspicious-inbox-rules"></a><span data-ttu-id="a2069-167">Passaggio 3 disabilitare tutte le regole di posta in arrivo sospette</span><span class="sxs-lookup"><span data-stu-id="a2069-167">Step 3 Disable any suspicious inbox rules</span></span>

1. <span data-ttu-id="a2069-168">Aprire la cassetta postale dell’utente con Outlook sul web.</span><span class="sxs-lookup"><span data-stu-id="a2069-168">Sign in to the user's mailbox using Outlook on the web.</span></span>

2. <span data-ttu-id="a2069-169">Fare clic sull'icona con l’ingranaggio e fare clic su **Posta**.</span><span class="sxs-lookup"><span data-stu-id="a2069-169">Click on the gear icon and click **Mail**.</span></span>

3. <span data-ttu-id="a2069-170">Fare clic su **Regole posta in arrivo e organizzazione** ed esaminare le regole.</span><span class="sxs-lookup"><span data-stu-id="a2069-170">Click **Inbox and sweep rules** and review the rules.</span></span>

4. <span data-ttu-id="a2069-171">Disattivare o eliminare le regole sospette.</span><span class="sxs-lookup"><span data-stu-id="a2069-171">Disable or delete suspicious rules.</span></span>

### <a name="step-4-unblock-the-user-from-sending-mail"></a><span data-ttu-id="a2069-172">Passaggio 4 Disattivare il blocco dell’invio di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="a2069-172">Step 4 Unblock the user from sending mail</span></span>

<span data-ttu-id="a2069-173">Se la cassetta postale compromessa è stata usata illecitamente per inviare posta indesiderata, è probabile che la l'invio di posta elettronica sia stato bloccato.</span><span class="sxs-lookup"><span data-stu-id="a2069-173">If the suspected compromised mailbox was used illicitly to send spam email, it is likely that the mailbox has been blocked from sending mail.</span></span>

<span data-ttu-id="a2069-174">Per sbloccare l’invio di posta elettronica da una cassetta postale, seguire le procedure descritte in [Rimozione di un utente dal portale Utenti con restrizioni dopo l'invio di posta elettronica indesiderata](removing-user-from-restricted-users-portal-after-spam.md).</span><span class="sxs-lookup"><span data-stu-id="a2069-174">To unblock a mailbox from sending mail, follow the procedures in [Removing a user from the Restricted Users portal after sending spam email](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

### <a name="step-5-optional-block-the-user-account-from-signing-in"></a><span data-ttu-id="a2069-175">Passaggio 5 facoltativo: Bloccare l’accesso all’account dell’utente</span><span class="sxs-lookup"><span data-stu-id="a2069-175">Step 5 Optional: Block the user account from signing-in</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a2069-176">È possibile bloccare l’accesso all’account compromesso fino a quando non si ritiene che sia sicuro abilitare di nuovo l'accesso.</span><span class="sxs-lookup"><span data-stu-id="a2069-176">You can block the suspected compromised account from signing-in until you believe it is safe to re-enable access.</span></span>

1. <span data-ttu-id="a2069-177">Apri l'interfaccia di amministrazione di Microsoft 365 e vai a **utenti** \> **utenti attivi**.</span><span class="sxs-lookup"><span data-stu-id="a2069-177">Open the Microsoft 365 admin center and go to **Users** \> **Active users**.</span></span>

2. <span data-ttu-id="a2069-178">Trova e seleziona l'account utente, fai clic sull'![icona Altro](../../media/ITPro-EAC-MoreOptionsIcon.png) e seleziona **Modifica stato di accesso**.</span><span class="sxs-lookup"><span data-stu-id="a2069-178">Find and select the user account, click ![More icon](../../media/ITPro-EAC-MoreOptionsIcon.png), and then select **Edit sign-in status**.</span></span>

3. <span data-ttu-id="a2069-179">Nel riquadro **Blocca accesso** visualizzato, seleziona **Impedisci a questo utente di accedere**, e fai clic su **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="a2069-179">On the **Block sign-in** pane that appears, select **Block this user from signing in**, and then click **Save changes**.</span></span>

4. <span data-ttu-id="a2069-180">Apri l'interfaccia di amministrazione di Exchange (EAC) su <admin.protection.outlook.com/ecp/> e vai a **Destinatari> Cassette postali**.</span><span class="sxs-lookup"><span data-stu-id="a2069-180">Open the Exchange admin center (EAC) at <admin.protection.outlook.com/ecp/>, and go to **Recipients > Mailboxes**.</span></span>

5. <span data-ttu-id="a2069-181">Individua e seleziona l'utente.</span><span class="sxs-lookup"><span data-stu-id="a2069-181">Find and select the select the user.</span></span> <span data-ttu-id="a2069-182">Nel riquadro dei dettagli eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a2069-182">In the details pane, do the following steps:</span></span>

   - <span data-ttu-id="a2069-183">Nella sezione **Funzionalità telefoniche e vocali**, effettua le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="a2069-183">In the **Phone and voice features** section, do the following steps:</span></span>

     - <span data-ttu-id="a2069-184">Seleziona **Disabilita Exchange ActiveSync**, fai clic su **Sì** nell'avviso visualizzato.</span><span class="sxs-lookup"><span data-stu-id="a2069-184">Select **Disable Exchange ActiveSync** and then click **Yes** in the warning that appears.</span></span>
     - <span data-ttu-id="a2069-185">Seleziona **OWA per dispositivi**, fai clic su **Sì** nell'avviso visualizzato.</span><span class="sxs-lookup"><span data-stu-id="a2069-185">Select **Disable OWA for Devices** and then click **Yes** in the warning that appears.</span></span>

   - <span data-ttu-id="a2069-186">Nella sezione **Connettività e-mail** per Outlook sul web, fai clic su **Disabilita** e poi su **Sì** nell'avviso visualizzato.</span><span class="sxs-lookup"><span data-stu-id="a2069-186">In the **Email Connectivity** section for Outlook on the web, click **Disable** and then click **Yes** in the warning that appears.</span></span>

### <a name="step-6-optional-remove-the-suspected-compromised-account-from-all-administrative-role-groups"></a><span data-ttu-id="a2069-187">Passaggio 6 Facoltativo: Rimuovere l'account potenzialmente compromesso da tutti i gruppi di ruoli amministrativi</span><span class="sxs-lookup"><span data-stu-id="a2069-187">Step 6 Optional: Remove the suspected compromised account from all administrative role groups</span></span>

> [!NOTE]
> <span data-ttu-id="a2069-188">Dopo aver protetto l'account, è possibile ripristinare l'appartenenza ai gruppi di ruoli amministrativi.</span><span class="sxs-lookup"><span data-stu-id="a2069-188">Administrative role group membership can be restored after the account has been secured.</span></span>

1. <span data-ttu-id="a2069-189">Accedere con il proprio account di amministratore globale:</span><span class="sxs-lookup"><span data-stu-id="a2069-189">Sign in with a global administrator account:</span></span>

2. <span data-ttu-id="a2069-190">Nell'interfaccia di amministrazione di Microsoft 365 esegui le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="a2069-190">In the Microsoft 365 admin center, do the following steps:</span></span>

   1. <span data-ttu-id="a2069-191">Passa a **Utenti** \> **Utenti attivi**.</span><span class="sxs-lookup"><span data-stu-id="a2069-191">Go to **Users** \> **Active users**.</span></span>
   2. <span data-ttu-id="a2069-192">Trova e seleziona l'account utente, fai clic sull'![icona Altro](../../media/ITPro-EAC-MoreOptionsIcon.png) e seleziona **Gestisci ruoli**.</span><span class="sxs-lookup"><span data-stu-id="a2069-192">Find and select the user account, click ![More icon](../../media/ITPro-EAC-MoreOptionsIcon.png), and then select **Manage roles**.</span></span>
   3. <span data-ttu-id="a2069-193">Rimuovi gli eventuali ruoli da amministratore assegnati all'account.</span><span class="sxs-lookup"><span data-stu-id="a2069-193">Remove any administrative roles that are assigned to the account.</span></span> <span data-ttu-id="a2069-194">Al termine, fai clic su **salvare le modifiche**.</span><span class="sxs-lookup"><span data-stu-id="a2069-194">When you're finished, click **Save changes**.</span></span>

3. <span data-ttu-id="a2069-195">Nel centro sicurezza e conformità in <https://protection.office.com>esegui le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="a2069-195">In the Security & Compliance Center at <https://protection.office.com>, do the following steps:</span></span>

   <span data-ttu-id="a2069-196">Seleziona **autorizzazioni**, seleziona ogni gruppo di ruoli nell'elenco e cerca l'account utente nella sezione **membri** nel riquadro a comparsa dettagli visualizzato.</span><span class="sxs-lookup"><span data-stu-id="a2069-196">Select **Permissions**, select each role group in the list and look for the user account in the **Members** section of the details flyout that appears.</span></span> <span data-ttu-id="a2069-197">Se il gruppo di ruoli contiene l'account utente, esegui le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a2069-197">If the role group contains the user account, do the following steps:</span></span>

   <span data-ttu-id="a2069-198">a.</span><span class="sxs-lookup"><span data-stu-id="a2069-198">a.</span></span> <span data-ttu-id="a2069-199">Fai clic su **modifica** accanto a **membri**.</span><span class="sxs-lookup"><span data-stu-id="a2069-199">Click **Edit** next to **Members**.</span></span>
   <span data-ttu-id="a2069-200">b.</span><span class="sxs-lookup"><span data-stu-id="a2069-200">b.</span></span> <span data-ttu-id="a2069-201">Nel riquadro a comparsa **modifica selezionare membri** visualizzato e fai clic su **modifica**.</span><span class="sxs-lookup"><span data-stu-id="a2069-201">On the **Editing Choose members** flyout that appears, click **Edit**.</span></span>
   <span data-ttu-id="a2069-202">c.</span><span class="sxs-lookup"><span data-stu-id="a2069-202">c.</span></span> <span data-ttu-id="a2069-203">Nel riquadro a comparsa visualizzato **Scegli membri**, seleziona l'account utente, e fai clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="a2069-203">In the **Choose members** flyout that appears, select the user account, and then click **Remove**.</span></span> <span data-ttu-id="a2069-204">Al termine, faI clic su **Completato**, **Salva** e **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="a2069-204">When you're finished, click **Done**, **Save**, and then **Close**.</span></span>

4. <span data-ttu-id="a2069-205">Nell’interfaccia di amministrazione di Exchange in <admin.protection.outlook.com/ecp/>, esegui i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="a2069-205">In the EAC at <admin.protection.outlook.com/ecp/>, do the following steps:</span></span>

   <span data-ttu-id="a2069-206">Seleziona **Autorizzazioni**, seleziona manualmente ogni gruppo di ruoli e nel riquadro dei dettagli verifica gli account utente nella sezione **Membri**.</span><span class="sxs-lookup"><span data-stu-id="a2069-206">Select **Permissions**, manually select each role group, and in the details pane, verify the user accounts in the **Members** section.</span></span>  <span data-ttu-id="a2069-207">Se il gruppo di ruoli contiene l'account utente, esegui le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a2069-207">If the role group contains the user account, do the following steps:</span></span>

   <span data-ttu-id="a2069-208">a.</span><span class="sxs-lookup"><span data-stu-id="a2069-208">a.</span></span> <span data-ttu-id="a2069-209">Seleziona il gruppo di ruoli, fai clic su **Modifica** ![Modifica icona](../../media/ITPro-EAC-EditIcon.png).</span><span class="sxs-lookup"><span data-stu-id="a2069-209">Select the role group, click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>
   <span data-ttu-id="a2069-210">b.</span><span class="sxs-lookup"><span data-stu-id="a2069-210">b.</span></span> <span data-ttu-id="a2069-211">Nella sezione **membri** seleziona l'account utente e fai clic su **Rimuovi** ![Rimuovi icona](../../media/ITPro-EAC-RemoveIcon.gif).</span><span class="sxs-lookup"><span data-stu-id="a2069-211">In the **Member** section, select the user account, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span> <span data-ttu-id="a2069-212">Al termine, fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="a2069-212">When you're finished, click **Save**.</span></span>

### <a name="step-7-optional-additional-precautionary-steps"></a><span data-ttu-id="a2069-213">Passaggio 7 facoltativo: Precauzioni di prevenzione aggiuntive</span><span class="sxs-lookup"><span data-stu-id="a2069-213">Step 7 Optional: Additional precautionary steps</span></span>

1. <span data-ttu-id="a2069-214">Assicurarsi di verificare i messaggi inviati.</span><span class="sxs-lookup"><span data-stu-id="a2069-214">Make sure that you verify your sent items.</span></span> <span data-ttu-id="a2069-215">Potrebbe essere necessario informare gli utenti nell'elenco dei contatti che l'account è stato compromesso.</span><span class="sxs-lookup"><span data-stu-id="a2069-215">You may have to inform people on your contacts list that your account was compromised.</span></span> <span data-ttu-id="a2069-216">Un utente malintenzionato potrebbe aver richiesto loro del denaro, fingendo (spoofing) che l’utente originale si trovasse bloccato in un paese/area geografica diversa e avesse necessità di denaro, oppure il malintenzionato potrebbe anche inviare dei virus per assumere il controllo dei loro computer. </span><span class="sxs-lookup"><span data-stu-id="a2069-216">The attacker may have asked them for money, spoofing, for example, that you were stranded in a different country and needed money, or the attacker may send them a virus to also hijack their computers.</span></span>

2. <span data-ttu-id="a2069-217">Qualsiasi altro servizio utilizzato con l'account di Exchange e il suo account di posta elettronica alternativo potrebbe essere compromesso.</span><span class="sxs-lookup"><span data-stu-id="a2069-217">Any other service that used this Exchange account as its alternative email account may have been compromised.</span></span> <span data-ttu-id="a2069-218">Prima di tutto, eseguire questi passaggi per l'abbonamento a Microsoft 365 poi seguire la stessa procedura per gli altri account.</span><span class="sxs-lookup"><span data-stu-id="a2069-218">First, do these steps for your Microsoft 365 subscription, and then do these steps for your other accounts.</span></span>

3. <span data-ttu-id="a2069-219">Assicurarsi che le informazioni di contatto, ad esempio numeri di telefono e indirizzi, siano corrette.</span><span class="sxs-lookup"><span data-stu-id="a2069-219">Make sure that your contact information, such as telephone numbers and addresses, is correct.</span></span>

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a><span data-ttu-id="a2069-220">Proteggere Microsoft 365 come un professionista della sicurezza informatica</span><span class="sxs-lookup"><span data-stu-id="a2069-220">Secure Microsoft 365 like a cybersecurity pro</span></span>

<span data-ttu-id="a2069-221">L'abbonamento a Microsoft 365 include un potente set di funzionalità di protezione che consente di proteggere i propri dati e quelli degli altri utenti.</span><span class="sxs-lookup"><span data-stu-id="a2069-221">Your Microsoft 365 subscription comes with a powerful set of security capabilities that you can use to protect your data and your users.</span></span>  <span data-ttu-id="a2069-222">Usare la [Roadmap della sicurezza di Microsoft 365: principali priorità per i primi 30 giorni, 90 giorni e oltre](security-roadmap.md) per implementare le procedure consigliate da Microsoft per proteggere il tenant di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a2069-222">Use the [Microsoft 365 security roadmap - Top priorities for the first 30 days, 90 days, and beyond](security-roadmap.md) to implement Microsoft recommended best practices for securing your Microsoft 365 tenant.</span></span>

- <span data-ttu-id="a2069-223">Attività da eseguire i primi 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="a2069-223">Tasks to accomplish in the first 30 days.</span></span>  <span data-ttu-id="a2069-224">Queste hanno effetto immediato e sono a basso impatto per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="a2069-224">These have immediate affect and are low-impact to your users.</span></span>

- <span data-ttu-id="a2069-225">Attività da completare in 90 giorni.</span><span class="sxs-lookup"><span data-stu-id="a2069-225">Tasks to accomplish in 90 days.</span></span> <span data-ttu-id="a2069-226">Queste attività richiedono una quantità di tempo leggermente superiore per la pianificazione e l'implementazione, ma aumentano notevolmente il livello di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="a2069-226">These take a bit more time to plan and implement but greatly improve your security posture.</span></span>

- <span data-ttu-id="a2069-227">Dopo 90 giorni.</span><span class="sxs-lookup"><span data-stu-id="a2069-227">Beyond 90 days.</span></span> <span data-ttu-id="a2069-228">Questi miglioramenti si instaurano nei primi 90 giorni di lavoro effettuato.</span><span class="sxs-lookup"><span data-stu-id="a2069-228">These enhancements build in your first 90 days work.</span></span>

## <a name="see-also"></a><span data-ttu-id="a2069-229">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a2069-229">See also</span></span>

- [<span data-ttu-id="a2069-230">Rilevare e risolvere gli attacchi injection alle regole e ai moduli personalizzati di Outlook in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a2069-230">Detect and Remediate Outlook Rules and Custom Forms Injections Attacks in Microsoft 365</span></span>](detect-and-remediate-outlook-rules-forms-attack.md)

- [<span data-ttu-id="a2069-231">Internet Crime Complaint Center</span><span class="sxs-lookup"><span data-stu-id="a2069-231">Internet Crime Complaint Center</span></span>](https://www.ic3.gov/Home/Ransomware)

- [<span data-ttu-id="a2069-232">Securities and Exchange Commission (SEC) - Frode “Phishing”</span><span class="sxs-lookup"><span data-stu-id="a2069-232">Securities and Exchange Commission - "Phishing" Fraud</span></span>](https://www.sec.gov/investor/pubs/phishing.htm)

- <span data-ttu-id="a2069-233">Per segnalare messaggi di posta elettronica indesiderata direttamente a Microsoft e all'amministratore, [usare il componente aggiuntivo Segnala messaggio](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span><span class="sxs-lookup"><span data-stu-id="a2069-233">To report spam email directly to Microsoft and your admin [Use the Report Message add-in](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)</span></span>
