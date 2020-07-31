---
title: Rispondere a un account di posta elettronica compromesso
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- M365-security-compliance
- m365solution-smb
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: Informazioni su come riconoscere e rispondere a un account di posta elettronica compromesso usando gli strumenti disponibili in Microsoft 365.
ms.openlocfilehash: cd9e5b4f9951bd332950cdc22ba3f3740d084dfb
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2020
ms.locfileid: "46527781"
---
# <a name="responding-to-a-compromised-email-account"></a><span data-ttu-id="f1f46-103">Rispondere a un account di posta elettronica compromesso</span><span class="sxs-lookup"><span data-stu-id="f1f46-103">Responding to a Compromised Email Account</span></span>

<span data-ttu-id="f1f46-104">**Riepilogo** Informazioni su come riconoscere e rispondere a un account di posta elettronica compromesso in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f1f46-104">**Summary** Learn how to recognize and respond to a compromised email account in Microsoft 365.</span></span>

## <a name="what-is-a-compromised-email-account-in-microsoft-365"></a><span data-ttu-id="f1f46-105">Che cos'è un account di posta elettronica compromesso in Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="f1f46-105">What is a Compromised Email Account in Microsoft 365?</span></span>

<span data-ttu-id="f1f46-106">L’accesso alle cassette postali, dati e altri servizi di Microsoft 365 viene controllato tramite l’uso di credenziali, ad esempio un nome utente e la password o il PIN.</span><span class="sxs-lookup"><span data-stu-id="f1f46-106">Access to Microsoft 365 mailboxes, data and other services, is controlled through the use of credentials, for example a user name and password or PIN.</span></span> <span data-ttu-id="f1f46-107">Quando un utente diverso da quello previsto sottrae queste credenziali, queste sono considerate compromesse.</span><span class="sxs-lookup"><span data-stu-id="f1f46-107">When someone other than the intended user steals those credentials, the stolen credentials are considered to be compromised.</span></span> <span data-ttu-id="f1f46-108">Con queste l'utente malintenzionato può accedere come utente originale ed effettuare operazioni illegali.</span><span class="sxs-lookup"><span data-stu-id="f1f46-108">With them the attacker can sign in as the original user and perform illicit actions.</span></span>
<span data-ttu-id="f1f46-109">Usando le credenziali rubate, l'autore dell'attacco può accedere alla cassetta postale di Microsoft 365, alle cartelle di SharePoint o ai file in OneDrive dell'utente.</span><span class="sxs-lookup"><span data-stu-id="f1f46-109">Using the stolen credentials, the attacker can access the user's Microsoft 365 mailbox, SharePoint folders, or files in the user's OneDrive.</span></span> <span data-ttu-id="f1f46-110">Un’operazione vista comunemente è l’invio da parte del pirata informatico di messaggi di posta elettronica a destinatari sia interni che esterni all'organizzazione dell'utente originale.</span><span class="sxs-lookup"><span data-stu-id="f1f46-110">One action commonly seen is the attacker sending emails as the original user to recipients both inside and outside of the organization.</span></span> <span data-ttu-id="f1f46-111">Quando un utente malintenzionato invia dei dati tramite messaggi di posta elettronica a destinatari esterni, si chiama esfiltrazione di dati.</span><span class="sxs-lookup"><span data-stu-id="f1f46-111">When the attacker emails data to external recipients, this is called data exfiltration.</span></span>

## <a name="symptoms-of-a-compromised-microsoft-email-account"></a><span data-ttu-id="f1f46-112">Sintomi di un account di posta elettronica Microsoft compromesso</span><span class="sxs-lookup"><span data-stu-id="f1f46-112">Symptoms of a Compromised Microsoft Email Account</span></span>

<span data-ttu-id="f1f46-113">Gli utenti potrebbero notare e segnalare attività insolite nelle proprie cassette postali di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f1f46-113">Users might notice and report unusual activity in their Microsoft 365 mailboxes.</span></span> <span data-ttu-id="f1f46-114">Ecco i sintomi più comuni:</span><span class="sxs-lookup"><span data-stu-id="f1f46-114">Here are some common symptoms:</span></span>

- <span data-ttu-id="f1f46-115">Attività sospette, ad esempio messaggi di posta elettronica mancanti o eliminati.</span><span class="sxs-lookup"><span data-stu-id="f1f46-115">Suspicious activity, such as missing or deleted emails.</span></span>

- <span data-ttu-id="f1f46-116">Altri utenti potrebbero ricevere messaggi di posta elettronica dall'account compromesso senza che sia presente il messaggio di posta elettronica corrispondente nella cartella **Posta inviata** del mittente.</span><span class="sxs-lookup"><span data-stu-id="f1f46-116">Other users might receive emails from the compromised account without the corresponding email existing in the **Sent Items** folder of the sender.</span></span>

- <span data-ttu-id="f1f46-117">La presenza di regole posta in arrivo che non sono state create dal proprietario o dall'amministratore.</span><span class="sxs-lookup"><span data-stu-id="f1f46-117">The presence of inbox rules that weren't created by the intended user or the administrator.</span></span> <span data-ttu-id="f1f46-118">Queste regole possono inoltrare messaggi di posta elettronica a indirizzi sconosciuti o spostarli automaticamente nelle cartelle di**Note**, **Posta indesiderata**, o **Sottoscrizioni RSS**.</span><span class="sxs-lookup"><span data-stu-id="f1f46-118">These rules may automatically forward emails to unknown addresses or move them to the **Notes**, **Junk Email**, or **RSS Subscriptions** folders.</span></span>

- <span data-ttu-id="f1f46-119">Il nome visualizzato dell'utente può essere modificato nell'elenco indirizzi globale.</span><span class="sxs-lookup"><span data-stu-id="f1f46-119">The user's display name might be changed in the Global Address List.</span></span>

- <span data-ttu-id="f1f46-120">Non è possibile inviare messaggi di posta elettronica dalla cassetta postale dell'utente.</span><span class="sxs-lookup"><span data-stu-id="f1f46-120">The user's mailbox is blocked from sending email.</span></span>

- <span data-ttu-id="f1f46-121">Le cartelle Posta inviata o Posta eliminata in Microsoft Outlook o Outlook sul web (precedentemente noto come Outlook Web App) contengono messaggi presenti comunemente in un account oggetto di un attacco, ad esempio "Mi sono bloccato a Milano, invia denaro."</span><span class="sxs-lookup"><span data-stu-id="f1f46-121">The Sent or Deleted Items folders in Microsoft Outlook or Outlook on the web (formerly known as Outlook Web App) contain common hacked-account messages, such as "I'm stuck in London, send money."</span></span>

- <span data-ttu-id="f1f46-122">Modifiche al profilo insolite, ad esempio un aggiornamento del nome, numero di telefono o codice postale.</span><span class="sxs-lookup"><span data-stu-id="f1f46-122">Unusual profile changes, such as the name, the telephone number, or the postal code were updated.</span></span>

- <span data-ttu-id="f1f46-123">Modifiche insolite alle credenziali, ad esempio, sono richiesti varie modifiche alla password.</span><span class="sxs-lookup"><span data-stu-id="f1f46-123">Unusual credential changes, such as multiple password changes are required.</span></span>

- <span data-ttu-id="f1f46-124">È stato aggiunto di recente un inoltro della posta di Outlook.</span><span class="sxs-lookup"><span data-stu-id="f1f46-124">Mail forwarding was recently added.</span></span>

- <span data-ttu-id="f1f46-125">È stata aggiunta una firma insolita, ad esempio una firma bancaria falsa o la fima per una ricetta medica.</span><span class="sxs-lookup"><span data-stu-id="f1f46-125">An unusual signature was recently added, such as a fake banking signature or a prescription drug signature.</span></span>

<span data-ttu-id="f1f46-126">Se un utente segnala qualsiasi dei sintomi precedenti, è necessario eseguire ulteriori analisi.</span><span class="sxs-lookup"><span data-stu-id="f1f46-126">If a user reports any of the above symptoms, you should perform further investigation.</span></span> <span data-ttu-id="f1f46-127">Il Centro sicurezza e conformità di Microsoft 365 e il portale di Azure offfrono strumenti che consentono di analizzare le attività di un account utente che si sospetta potrebbe essere compromesso.</span><span class="sxs-lookup"><span data-stu-id="f1f46-127">The Microsoft 365 Security & Compliance Center and the Azure Portal offer tools to help you investigate the activity of a user account that you suspect may be compromised.</span></span>

- <span data-ttu-id="f1f46-128">**Log di controllo unificati nel Centro sicurezza e conformità**: esaminare tutte le attività nell'account sospetto filtrando i risultati per l'intervallo di date che si estendono da immediatamente prima delle attività sospette alla data attuale.</span><span class="sxs-lookup"><span data-stu-id="f1f46-128">**Unified Audit Logs in the Security & Compliance Center**: Review all the activities for the suspected account by filtering the results for the date range spanning from immediately before the suspicious activity occurred to the current date.</span></span> <span data-ttu-id="f1f46-129">Non filtrare le attività durante la ricerca.</span><span class="sxs-lookup"><span data-stu-id="f1f46-129">Do not filter on the activities during the search.</span></span>

- <span data-ttu-id="f1f46-130">**Log di controllo dell'amministratore nell'interfaccia di amministrazione di Exchange**: in Exchange Online è possibile usare l'interfaccia di amministrazione di Exchange per cercare e visualizzare voci nel log di controllo dell'amministratore.</span><span class="sxs-lookup"><span data-stu-id="f1f46-130">**Admin Audit logs in the EAC**: In Exchange Online, you can use the Exchange admin center (EAC) to search for and view entries in the administrator audit log.</span></span> <span data-ttu-id="f1f46-131">Il log di controllo dell'amministratore registra operazioni specifiche, basate su cmdlet di PowerShell per Exchange Online, eseguite dagli amministratori e dagli utenti che dispongono di privilegi amministrativi.</span><span class="sxs-lookup"><span data-stu-id="f1f46-131">The administrator audit log records specific actions, based on Exchange Online PowerShell cmdlets, performed by administrators and users who have been assigned administrative privileges.</span></span> <span data-ttu-id="f1f46-132">Le voci nel registro di controllo dell'amministratore forniscono informazioni sul cmdlet eseguito, sui parametri utilizzati, sull'utente che ha eseguito il cmdlet e sugli oggetti coinvolti.</span><span class="sxs-lookup"><span data-stu-id="f1f46-132">Entries in the administrator audit log provide you with information about what cmdlet was run, which parameters were used, who ran the cmdlet, and what objects were affected.</span></span>

- <span data-ttu-id="f1f46-133">**Log di accesso di Azure AD e altri report sui rischi disponibili nel portale di Azure AD**: esaminare i valori nelle colonne seguenti:</span><span class="sxs-lookup"><span data-stu-id="f1f46-133">**Azure AD Sign-in logs and other risk reports in the Azure AD portal**: Examine the values in these columns:</span></span>

  - <span data-ttu-id="f1f46-134">Esaminare l'indirizzo IP</span><span class="sxs-lookup"><span data-stu-id="f1f46-134">Review IP address</span></span>

  - <span data-ttu-id="f1f46-135">Posizioni di accesso</span><span class="sxs-lookup"><span data-stu-id="f1f46-135">sign-in locations</span></span>

  - <span data-ttu-id="f1f46-136">Orari di accesso</span><span class="sxs-lookup"><span data-stu-id="f1f46-136">sign-in times</span></span>

  - <span data-ttu-id="f1f46-137">Esito dell’accesso</span><span class="sxs-lookup"><span data-stu-id="f1f46-137">sign-in success or failure</span></span>

## <a name="how-to-secure-and-restore-email-function-to-a-suspected-compromised-microsoft-365-account-and-mailbox"></a><span data-ttu-id="f1f46-138">Come proteggere e ripristinare la funzione di posta elettronica in un potenziale account e cassetta postale di Microsoft 365 compromessi.</span><span class="sxs-lookup"><span data-stu-id="f1f46-138">How to secure and restore email function to a suspected compromised Microsoft 365 account and mailbox</span></span>

> [!VIDEO https://videoplayercdn.osi.office.net/hub/?csid=ux-cms-en-us-msoffice&uuid=RE2jvOb&AutoPlayVideo=false]

<span data-ttu-id="f1f46-139">Anche l’accesso all’account è stato riacquisito rapidamente, un utente malintenzionato potrebbe aver aggiunto voci “back-door” che gli permettono di riprendere il controllo dell'account.</span><span class="sxs-lookup"><span data-stu-id="f1f46-139">Even after you've regained access to your account, the attacker may have added back-door entries that enable the attacker to resume control of the account.</span></span>

<span data-ttu-id="f1f46-140">È necessario eseguire la procedura seguente per accedere all'account il prima possibile per assicurarsi che l’autore dell’attacco non riprenda il controllo dell’account.</span><span class="sxs-lookup"><span data-stu-id="f1f46-140">You must perform all the following steps to regain access to your account the sooner the better to make sure that the hijacker doesn't resume control your account.</span></span> <span data-ttu-id="f1f46-141">Questa procedura consente di rimuovere le voci “back-door” che l’autore dell’attacco potrebbe aver aggiunto all’account.</span><span class="sxs-lookup"><span data-stu-id="f1f46-141">These steps help you remove any back-door entries that the hijacker may have added to your account.</span></span> <span data-ttu-id="f1f46-142">Dopo avere eseguito questi passaggi, è consigliabile eseguire una scansione con un programma antivirus per verificare che il computer non sia compromesso.</span><span class="sxs-lookup"><span data-stu-id="f1f46-142">After you perform these steps, we recommend that you run a virus scan to make sure that your computer isn't compromised.</span></span>

### <a name="step-1-reset-the-users-password"></a><span data-ttu-id="f1f46-143">Passaggio 1: Reimpostare la password dell’utente.</span><span class="sxs-lookup"><span data-stu-id="f1f46-143">Step 1 Reset the user's password</span></span>

> [!WARNING]
> <span data-ttu-id="f1f46-144">Non inviare la nuova password per l'utente desiderato tramite posta elettronica, poiché l’utente malintenzionato potrebbe ancora avere accesso alla cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="f1f46-144">Do not send the new password to the intended user through email as the attacker still has access to the mailbox at this point.</span></span>

1. <span data-ttu-id="f1f46-145">Seguire i passaggi descritti in Reimpostare la password di App Microsoft 365 for business per altri utenti in[Reimpostare le password per App Microsoft 365 for business](https://docs.microsoft.com/microsoft-365/admin/add-users/reset-passwords)</span><span class="sxs-lookup"><span data-stu-id="f1f46-145">Follow the Reset a Microsoft 365 Apps for business password for someone else procedures in [Reset Microsoft 365 Apps for business passwords](https://docs.microsoft.com/microsoft-365/admin/add-users/reset-passwords)</span></span>

<span data-ttu-id="f1f46-146">**Note**:</span><span class="sxs-lookup"><span data-stu-id="f1f46-146">**Notes**:</span></span>

- <span data-ttu-id="f1f46-147">Assicurarsi che la password sia complessa e che contenga lettere maiuscole e minuscole, almeno un numero e almeno un carattere speciale.</span><span class="sxs-lookup"><span data-stu-id="f1f46-147">Make sure that the password is strong and that it contains upper and lowercase letters, at least one number, and at least one special character.</span></span>

- <span data-ttu-id="f1f46-148">Non riutilizzare le cinque password più recenti.</span><span class="sxs-lookup"><span data-stu-id="f1f46-148">Don't reuse any of your last five passwords.</span></span> <span data-ttu-id="f1f46-149">Anche se il requisito di cronologia delle password consente di riutilizzare una password più recente, è necessario sceglierla in modo che un utente malintenzionato non possa indovinarla.</span><span class="sxs-lookup"><span data-stu-id="f1f46-149">Even though the password history requirement lets you reuse a more recent password, you should select something that the attacker can't guess.</span></span>

- <span data-ttu-id="f1f46-150">Se l'identità dell'utente locale è federata con Microsoft 365, è necessario cambiare la password locale e quindi informare l'amministratore della violazione.</span><span class="sxs-lookup"><span data-stu-id="f1f46-150">If your on-premises identity is federated with Microsoft 365, you must change your password on-premises, and then you must notify your administrator of the compromise.</span></span>

> [!TIP]
> <span data-ttu-id="f1f46-151">È altamente consigliabile abilitare l'autenticazione a più fattori (MFA) per evitare violazioni, soprattutto per gli account con privilegi amministrativi.</span><span class="sxs-lookup"><span data-stu-id="f1f46-151">We highly recommended that you enable Multi-Factor Authentication (MFA) in order to prevent compromise, especially for accounts with administrative privileges.</span></span>  <span data-ttu-id="f1f46-152">Per maggiori dettagli sull’autenticazione a più fattori, visitare [Configurare l’autenticazione a più fattori](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication).</span><span class="sxs-lookup"><span data-stu-id="f1f46-152">To learn more about MFA, go to [Set up multi-factor authentication](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication).</span></span>

### <a name="step-2-remove-suspicious-email-forwarding-addresses"></a><span data-ttu-id="f1f46-153">Passaggio 2: Rimuovere indirizzi di inoltro della posta elettronica</span><span class="sxs-lookup"><span data-stu-id="f1f46-153">Step 2 Remove suspicious email forwarding addresses</span></span>

1. <span data-ttu-id="f1f46-154">Aprire l’**interfaccia di amministrazione di Microsoft 365 > Utenti attivi**.</span><span class="sxs-lookup"><span data-stu-id="f1f46-154">Open the **Microsoft 365 admin center > Active Users**.</span></span>

2. <span data-ttu-id="f1f46-155">Trovare l'account utente in questione ed espandere le \*\* impostazioni della posta\*\*.</span><span class="sxs-lookup"><span data-stu-id="f1f46-155">Find the user account in question and expand **Mail Settings**.</span></span>

3. <span data-ttu-id="f1f46-156">Su **Inoltro della posta elettronica**, fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="f1f46-156">For **Email forwarding**, click **Edit**.</span></span>

4. <span data-ttu-id="f1f46-157">Rimuovere qualsiasi indirizzo di inoltro sospetto.</span><span class="sxs-lookup"><span data-stu-id="f1f46-157">Remove any suspicious forwarding addresses.</span></span>

### <a name="step-3-disable-any-suspicious-inbox-rules"></a><span data-ttu-id="f1f46-158">Passaggio 3 disabilitare tutte le regole di posta in arrivo sospette</span><span class="sxs-lookup"><span data-stu-id="f1f46-158">Step 3 Disable any suspicious inbox rules</span></span>

1. <span data-ttu-id="f1f46-159">Aprire la cassetta postale dell’utente con Outlook sul web.</span><span class="sxs-lookup"><span data-stu-id="f1f46-159">Sign in to the user's mailbox using Outlook on the web.</span></span>

2. <span data-ttu-id="f1f46-160">Fare clic sull'icona con l’ingranaggio e fare clic su **Posta**.</span><span class="sxs-lookup"><span data-stu-id="f1f46-160">Click on the gear icon and click **Mail**.</span></span>

3. <span data-ttu-id="f1f46-161">Fare clic su **Regole posta in arrivo e organizzazione** ed esaminare le regole.</span><span class="sxs-lookup"><span data-stu-id="f1f46-161">Click **Inbox and sweep rules** and review the rules.</span></span>

4. <span data-ttu-id="f1f46-162">Disattivare o eliminare le regole sospette.</span><span class="sxs-lookup"><span data-stu-id="f1f46-162">Disable or delete suspicious rules.</span></span>

### <a name="step-4-unblock-the-user-from-sending-mail"></a><span data-ttu-id="f1f46-163">Passaggio 4 Disattivare il blocco dell’invio di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="f1f46-163">Step 4 Unblock the user from sending mail</span></span>

<span data-ttu-id="f1f46-164">Se la cassetta postale compromessa è stata usata illecitamente per inviare posta indesiderata, è probabile che la l'invio di posta elettronica sia stato bloccato.</span><span class="sxs-lookup"><span data-stu-id="f1f46-164">If the suspected compromised mailbox was used illicitly to send spam email, it is likely that the mailbox has been blocked from sending mail.</span></span>

<span data-ttu-id="f1f46-165">Per sbloccare l’invio di posta elettronica da una cassetta postale, seguire le procedure descritte in [Rimozione di un utente dal portale Utenti con restrizioni dopo l'invio di posta elettronica indesiderata](removing-user-from-restricted-users-portal-after-spam.md).</span><span class="sxs-lookup"><span data-stu-id="f1f46-165">To unblock a mailbox from sending mail, follow the procedures in [Removing a user from the Restricted Users portal after sending spam email](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

### <a name="step-5-optional-block-the-user-account-from-signing-in"></a><span data-ttu-id="f1f46-166">Passaggio 5 facoltativo: Bloccare l’accesso all’account dell’utente</span><span class="sxs-lookup"><span data-stu-id="f1f46-166">Step 5 Optional: Block the user account from signing-in</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f1f46-167">È possibile bloccare l’accesso all’account compromesso fino a quando non si ritiene che sia sicuro abilitare di nuovo l'accesso.</span><span class="sxs-lookup"><span data-stu-id="f1f46-167">You can block the suspected compromised account from signing-in until you believe it is safe to re-enable access.</span></span>

1. <span data-ttu-id="f1f46-168">Passare all'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f1f46-168">Go to the Microsoft 365 admin center.</span></span>

2. <span data-ttu-id="f1f46-169">Nell'Interfaccia di amministrazione di Microsoft 365, selezionare **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="f1f46-169">In the Microsoft 365 admin center, select **Users**.</span></span>

3. <span data-ttu-id="f1f46-170">Selezionare il dipendente da bloccare e scegliere **Modifica** accanto a **Stato accesso** nel riquadro degli utenti.</span><span class="sxs-lookup"><span data-stu-id="f1f46-170">Select the employee that you want to block, and then choose **Edit** next to **Sign-in status** in the user pane.</span></span>

4. <span data-ttu-id="f1f46-171">Nel riquadro **Stato accesso** scegliere **Accesso bloccato** e quindi **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f1f46-171">On the **Sign-in status** pane, choose **Sign-in blocked** and then **Save**.</span></span>

5. <span data-ttu-id="f1f46-172">Nell'interfaccia di amministrazione nel riquadro di spostamento in basso a sinistra, espandere **Interfacce di amministrazione** e selezionare **Exchange**.</span><span class="sxs-lookup"><span data-stu-id="f1f46-172">In the Admin center, in the lower-left navigation pane, expand **Admin Centers** and select **Exchange**.</span></span>

6. <span data-ttu-id="f1f46-173">Nell'interfaccia di amministrazione di Exchange passare a **Destinatari > Cassette postali**.</span><span class="sxs-lookup"><span data-stu-id="f1f46-173">In the Exchange admin center, navigate to **Recipients > Mailboxes**.</span></span>

7. <span data-ttu-id="f1f46-174">Selezionare l'utente e nella relativa pagina delle proprietà, in **Dispositivi mobili**, selezionare **Disabilita Exchange ActiveSync**, **Disabilita OWA per i dispositivi** e rispondere **sì** per entrambi.</span><span class="sxs-lookup"><span data-stu-id="f1f46-174">Select the user, and on the user properties page, under **Mobile Devices**, click **Disable Exchange ActivcSync** and **Disable OWA for Devices** and answer **yes** to both.</span></span>

8. <span data-ttu-id="f1f46-175">In **Connettività posta elettronica** fare clic su **Disabilita** e rispondere **sì**.</span><span class="sxs-lookup"><span data-stu-id="f1f46-175">Under **Email Connectivity**, **Disable** and answer **yes**.</span></span>

### <a name="step-6-optional-remove-the-suspected-compromised-account-from-all-administrative-role-groups"></a><span data-ttu-id="f1f46-176">Passaggio 6 Facoltativo: Rimuovere l'account potenzialmente compromesso da tutti i gruppi di ruoli amministrativi</span><span class="sxs-lookup"><span data-stu-id="f1f46-176">Step 6 Optional: Remove the suspected compromised account from all administrative role groups</span></span>

> [!NOTE]
> <span data-ttu-id="f1f46-177">Dopo aver protetto l'account, è possibile ripristinare l'appartenenza ai gruppi di ruoli amministrativi.</span><span class="sxs-lookup"><span data-stu-id="f1f46-177">Administrative role group membership can be restored after the account has been secured.</span></span>

1. <span data-ttu-id="f1f46-178">Accedere all'interfaccia di amministrazione di Microsoft 365 con l'account di amministratore globale e aprire **Utenti attivi**.</span><span class="sxs-lookup"><span data-stu-id="f1f46-178">Sign in to the Microsoft 365 admin center with a global administrator account and open **Active Users**.</span></span>

2. <span data-ttu-id="f1f46-179">Individuare i possibili account compromessi e controllare manualmente se sono presenti dei ruoli amministrativi assegnati all'account.</span><span class="sxs-lookup"><span data-stu-id="f1f46-179">Find the suspected compromised account and manually check to see if there are any administrative roles assigned to the account.</span></span>

3. <span data-ttu-id="f1f46-180">Aprire il **Centro sicurezza e conformità**.</span><span class="sxs-lookup"><span data-stu-id="f1f46-180">Open the **Security & Compliance Center**.</span></span>

4. <span data-ttu-id="f1f46-181">Fare clic su **Autorizzazioni**.</span><span class="sxs-lookup"><span data-stu-id="f1f46-181">Click **Permissions**.</span></span>

5. <span data-ttu-id="f1f46-182">Controllare manualmente i gruppi di ruoli per verificare se l’account potenzialmente compromesso sia un membro di uno di questi account.</span><span class="sxs-lookup"><span data-stu-id="f1f46-182">Manually review the role groups to see if the suspected compromised account is a member of any of them.</span></span>  <span data-ttu-id="f1f46-183">Se è:</span><span class="sxs-lookup"><span data-stu-id="f1f46-183">If it is:</span></span>

   <span data-ttu-id="f1f46-184">a.</span><span class="sxs-lookup"><span data-stu-id="f1f46-184">a.</span></span> <span data-ttu-id="f1f46-185">Fare clic sul gruppo di ruoli e selezionare **Modifica gruppo di ruoli**.</span><span class="sxs-lookup"><span data-stu-id="f1f46-185">Click the role group and click **Edit Role Group**.</span></span>

   <span data-ttu-id="f1f46-186">b.</span><span class="sxs-lookup"><span data-stu-id="f1f46-186">b.</span></span> <span data-ttu-id="f1f46-187">Fare clic su **Scegli membri** e **Modifica** per rimuovere l'utente dal gruppo di ruoli.</span><span class="sxs-lookup"><span data-stu-id="f1f46-187">Click **Chose Members** and **Edit** to remove the user from the role group.</span></span>

6. <span data-ttu-id="f1f46-188">Aprire **l'interfaccia di amministrazione di Exchange**.</span><span class="sxs-lookup"><span data-stu-id="f1f46-188">Open the **Exchange admin center**.</span></span>

7. <span data-ttu-id="f1f46-189">Fare clic su **Autorizzazioni**.</span><span class="sxs-lookup"><span data-stu-id="f1f46-189">Click **Permissions**.</span></span>

8. <span data-ttu-id="f1f46-190">Controllare manualmente i gruppi di ruoli per verificare se l’account potenzialmente compromesso sia un membro di uno di questi account.</span><span class="sxs-lookup"><span data-stu-id="f1f46-190">Manually review the role groups to see if the suspected compromised account is a member of any of them.</span></span> <span data-ttu-id="f1f46-191">Se è:</span><span class="sxs-lookup"><span data-stu-id="f1f46-191">If it is:</span></span>

   <span data-ttu-id="f1f46-192">a.</span><span class="sxs-lookup"><span data-stu-id="f1f46-192">a.</span></span> <span data-ttu-id="f1f46-193">Fare clic sul gruppo di ruoli e selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="f1f46-193">Click the role group and click **Edit**.</span></span>

   <span data-ttu-id="f1f46-194">b.</span><span class="sxs-lookup"><span data-stu-id="f1f46-194">b.</span></span> <span data-ttu-id="f1f46-195">Fare clic sulla sezione**Membri** per rimuovere l'utente dal gruppo di ruoli.</span><span class="sxs-lookup"><span data-stu-id="f1f46-195">Use the **members** section to remove the user from the role group.</span></span>

### <a name="step-7-optional-additional-precautionary-steps"></a><span data-ttu-id="f1f46-196">Passaggio 7 facoltativo: Precauzioni di prevenzione aggiuntive</span><span class="sxs-lookup"><span data-stu-id="f1f46-196">Step 7 Optional: Additional precautionary steps</span></span>

1. <span data-ttu-id="f1f46-197">Assicurarsi di verificare i messaggi inviati.</span><span class="sxs-lookup"><span data-stu-id="f1f46-197">Make sure that you verify your sent items.</span></span> <span data-ttu-id="f1f46-198">Potrebbe essere necessario informare gli utenti nell'elenco dei contatti che l'account è stato compromesso.</span><span class="sxs-lookup"><span data-stu-id="f1f46-198">You may have to inform people on your contacts list that your account was compromised.</span></span> <span data-ttu-id="f1f46-199">Un utente malintenzionato potrebbe aver richiesto loro del denaro, fingendo (spoofing) che l’utente originale si trovasse bloccato in un paese/area geografica diversa e avesse necessità di denaro, oppure il malintenzionato potrebbe anche inviare dei virus per assumere il controllo dei loro computer. </span><span class="sxs-lookup"><span data-stu-id="f1f46-199">The attacker may have asked them for money, spoofing, for example, that you were stranded in a different country and needed money, or the attacker may send them a virus to also hijack their computers.</span></span>

2. <span data-ttu-id="f1f46-200">Qualsiasi altro servizio utilizzato con l'account di Exchange e il suo account di posta elettronica alternativo potrebbe essere compromesso.</span><span class="sxs-lookup"><span data-stu-id="f1f46-200">Any other service that used this Exchange account as its alternative email account may have been compromised.</span></span> <span data-ttu-id="f1f46-201">Prima di tutto, eseguire questi passaggi per l'abbonamento a Microsoft 365 poi seguire la stessa procedura per gli altri account.</span><span class="sxs-lookup"><span data-stu-id="f1f46-201">First, perform these steps for your Microsoft 365 subscription, and then perform these steps for your other accounts.</span></span>

3. <span data-ttu-id="f1f46-202">Assicurarsi che le informazioni di contatto, ad esempio numeri di telefono e indirizzi, siano corrette.</span><span class="sxs-lookup"><span data-stu-id="f1f46-202">Make sure that your contact information, such as telephone numbers and addresses, is correct.</span></span>

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a><span data-ttu-id="f1f46-203">Proteggere Microsoft 365 come un professionista della sicurezza informatica</span><span class="sxs-lookup"><span data-stu-id="f1f46-203">Secure Microsoft 365 like a cybersecurity pro</span></span>

<span data-ttu-id="f1f46-204">L'abbonamento a Microsoft 365 include un potente set di funzionalità di protezione che consente di proteggere i propri dati e quelli degli altri utenti.</span><span class="sxs-lookup"><span data-stu-id="f1f46-204">Your Microsoft 365 subscription comes with a powerful set of security capabilities that you can use to protect your data and your users.</span></span>  <span data-ttu-id="f1f46-205">Usare la [Roadmap della sicurezza di Microsoft 365: principali priorità per i primi 30 giorni, 90 giorni e oltre](security-roadmap.md) per implementare le procedure consigliate da Microsoft per proteggere il tenant di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f1f46-205">Use the [Microsoft 365 security roadmap - Top priorities for the first 30 days, 90 days, and beyond](security-roadmap.md) to implement Microsoft recommended best practices for securing your Microsoft 365 tenant.</span></span>

- <span data-ttu-id="f1f46-206">Attività da eseguire i primi 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="f1f46-206">Tasks to accomplish in the first 30 days.</span></span>  <span data-ttu-id="f1f46-207">Queste hanno effetto immediato e sono a basso impatto per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="f1f46-207">These have immediate affect and are low-impact to your users.</span></span>

- <span data-ttu-id="f1f46-208">Attività da completare in 90 giorni.</span><span class="sxs-lookup"><span data-stu-id="f1f46-208">Tasks to accomplish in 90 days.</span></span> <span data-ttu-id="f1f46-209">Queste attività richiedono una quantità di tempo leggermente superiore per la pianificazione e l'implementazione, ma aumentano notevolmente il livello di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="f1f46-209">These take a bit more time to plan and implement but greatly improve your security posture.</span></span>

- <span data-ttu-id="f1f46-210">Dopo 90 giorni.</span><span class="sxs-lookup"><span data-stu-id="f1f46-210">Beyond 90 days.</span></span> <span data-ttu-id="f1f46-211">Questi miglioramenti si instaurano nei primi 90 giorni di lavoro effettuato.</span><span class="sxs-lookup"><span data-stu-id="f1f46-211">These enhancements build in your first 90 days work.</span></span>

## <a name="see-also"></a><span data-ttu-id="f1f46-212">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f1f46-212">See also</span></span>

- [<span data-ttu-id="f1f46-213">Rilevare e risolvere gli attacchi injection alle regole e ai moduli personalizzati di Outlook in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f1f46-213">Detect and Remediate Outlook Rules and Custom Forms Injections Attacks in Microsoft 365</span></span>](detect-and-remediate-outlook-rules-forms-attack.md)

- [<span data-ttu-id="f1f46-214">Internet Crime Complaint Center</span><span class="sxs-lookup"><span data-stu-id="f1f46-214">Internet Crime Complaint Center</span></span>](https://www.ic3.gov/preventiontips.aspx)

- [<span data-ttu-id="f1f46-215">Securities and Exchange Commission (SEC) - Frode “Phishing”</span><span class="sxs-lookup"><span data-stu-id="f1f46-215">Securities and Exchange Commission - "Phishing" Fraud</span></span>](https://www.sec.gov/investor/pubs/phishing.htm)

- <span data-ttu-id="f1f46-216">Per segnalare messaggi di posta elettronica indesiderata direttamente a Microsoft e all'amministratore, [usare il componente aggiuntivo Segnala messaggio](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span><span class="sxs-lookup"><span data-stu-id="f1f46-216">To report spam email directly to Microsoft and your admin [Use the Report Message add-in](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)</span></span>
