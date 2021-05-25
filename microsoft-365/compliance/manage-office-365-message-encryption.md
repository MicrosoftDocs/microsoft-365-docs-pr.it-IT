---
title: Gestire Office 365 Message Encryption
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 5/8/2019
search.appverid:
- MET150
ms.assetid: 09f6737e-f03f-4bc8-8281-e46d24ee2a74
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Dopo aver completato la configurazione di Office 365 Message Encryption (OME), scopri come personalizzare la distribuzione in diversi modi.
ms.openlocfilehash: a2b3dde44ea541deb41eeb9d55d5ed745fa6c719
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2021
ms.locfileid: "52650985"
---
# <a name="manage-office-365-message-encryption"></a><span data-ttu-id="05454-103">Gestire Office 365 Message Encryption</span><span class="sxs-lookup"><span data-stu-id="05454-103">Manage Office 365 Message Encryption</span></span>

<span data-ttu-id="05454-104">Dopo aver completato la configurazione di Office 365 Message Encryption (OME), è possibile personalizzare la configurazione della distribuzione in diversi modi.</span><span class="sxs-lookup"><span data-stu-id="05454-104">Once you've finished setting up Office 365 Message Encryption (OME), you can customize the configuration of your deployment in several ways.</span></span> <span data-ttu-id="05454-105">Ad esempio, è possibile configurare se abilitare i  pass code una sola volta, visualizzare il pulsante Crittografa Outlook sul Web e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="05454-105">For example, you can configure whether to enable one-time pass codes, display the **Encrypt** button in Outlook on the web, and more.</span></span> <span data-ttu-id="05454-106">Le attività descritte in questo articolo descrivono come.</span><span class="sxs-lookup"><span data-stu-id="05454-106">The tasks in this article describe how.</span></span>

## <a name="manage-whether-google-yahoo-and-microsoft-account-recipients-can-use-these-accounts-to-sign-in-to-the-office-365-message-encryption-portal"></a><span data-ttu-id="05454-107">Stabilire se i destinatari di Google, Yahoo e Account Microsoft possono usare questi account per accedere al portale Office 365 Message Encryption utenti</span><span class="sxs-lookup"><span data-stu-id="05454-107">Manage whether Google, Yahoo, and Microsoft Account recipients can use these accounts to sign in to the Office 365 Message Encryption portal</span></span>

<span data-ttu-id="05454-108">Quando si configurano le nuove funzionalità Office 365 Message Encryption, gli utenti dell'organizzazione possono inviare messaggi a destinatari esterni all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="05454-108">When you set up the new Office 365 Message Encryption capabilities, users in your organization can send messages to recipients that are outside of your organization.</span></span> <span data-ttu-id="05454-109">Se il destinatario usa un *ID di social* network, ad esempio un account Google, un account Yahoo o un account Microsoft, il destinatario può accedere al portale OME con un ID social.</span><span class="sxs-lookup"><span data-stu-id="05454-109">If the recipient uses a *social ID* such as a Google account, Yahoo account, or Microsoft account, the recipient can sign in to the OME portal with a social ID.</span></span> <span data-ttu-id="05454-110">Se si desidera, è possibile scegliere di non consentire ai destinatari di utilizzare ID di social network per accedere al portale OME.</span><span class="sxs-lookup"><span data-stu-id="05454-110">If you want, you can choose not to allow recipients to use social IDs to sign in to the OME portal.</span></span>
  
### <a name="to-manage-whether-recipients-can-use-social-ids-to-sign-in-to-the-ome-portal"></a><span data-ttu-id="05454-111">Per gestire se i destinatari possono utilizzare gli ID social per accedere al portale OME</span><span class="sxs-lookup"><span data-stu-id="05454-111">To manage whether recipients can use social IDs to sign in to the OME portal</span></span>
  
1. <span data-ttu-id="05454-112">[Connessione utilizzare Exchange Online PowerShell remoto.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="05454-112">[Connect to Exchange Online Using Remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="05454-113">Eseguire il cmdlet Set-OMEConfiguration con il parametro SocialIdSignIn come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="05454-113">Run the Set-OMEConfiguration cmdlet with the SocialIdSignIn parameter as follows:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter"> -SocialIdSignIn <$true|$false>
   ```

   <span data-ttu-id="05454-114">Ad esempio, per disabilitare gli ID social:</span><span class="sxs-lookup"><span data-stu-id="05454-114">For example, to disable social IDs:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $false
   ```

   <span data-ttu-id="05454-115">Per abilitare gli ID social:</span><span class="sxs-lookup"><span data-stu-id="05454-115">To enable social IDs:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $true
   ```

## <a name="manage-the-use-of-one-time-pass-codes-for-the-office-365-message-encryption-portal"></a><span data-ttu-id="05454-116">Gestire l'utilizzo di codici di accesso una sola volta per il Office 365 Message Encryption portale</span><span class="sxs-lookup"><span data-stu-id="05454-116">Manage the use of one-time pass codes for the Office 365 Message Encryption portal</span></span>

<span data-ttu-id="05454-117">Se il destinatario di un messaggio crittografato da OME non utilizza Outlook, indipendentemente dall'account utilizzato dal destinatario, il destinatario riceve un collegamento di visualizzazione Web a tempo limitato che consente loro di leggere il messaggio.</span><span class="sxs-lookup"><span data-stu-id="05454-117">If the recipient of a message encrypted by OME doesn't use Outlook, regardless of the account used by the recipient, the recipient receives a limited-time web-view link that lets them read the message.</span></span> <span data-ttu-id="05454-118">Questo collegamento include un pass code una sola volta.</span><span class="sxs-lookup"><span data-stu-id="05454-118">This link includes a one-time pass code.</span></span> <span data-ttu-id="05454-119">Gli amministratori possono decidere se i destinatari possono utilizzare pass code una sola volta per accedere al portale OME.</span><span class="sxs-lookup"><span data-stu-id="05454-119">As an administrator, you can decide if recipients can use one-time pass codes to sign in to the OME portal.</span></span>
  
### <a name="to-manage-whether-ome-generates-one-time-pass-codes"></a><span data-ttu-id="05454-120">Per gestire se OME genera pass code una sola volta</span><span class="sxs-lookup"><span data-stu-id="05454-120">To manage whether OME generates one-time pass codes</span></span>
  
1. <span data-ttu-id="05454-121">Utilizzare un account aziendale o dell'istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione e avviare una sessione Windows PowerShell e connettersi a Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="05454-121">Use a work or school account that has global administrator permissions in your organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="05454-122">Per istruzioni, vedere [Connettersi a PowerShell di Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="05454-122">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="05454-123">Eseguire il cmdlet Set-OMEConfiguration con il parametro OTPEnabled:</span><span class="sxs-lookup"><span data-stu-id="05454-123">Run the Set-OMEConfiguration cmdlet with the OTPEnabled parameter:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter"> -OTPEnabled <$true|$false>
   ```

   <span data-ttu-id="05454-124">Ad esempio, per disabilitare i pass code una sola volta:</span><span class="sxs-lookup"><span data-stu-id="05454-124">For example, to disable one-time pass codes:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $false
   ```

   <span data-ttu-id="05454-125">Per abilitare i pass code una sola volta:</span><span class="sxs-lookup"><span data-stu-id="05454-125">To enable one-time pass codes:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $true
   ```

## <a name="manage-the-display-of-the-encrypt-button-in-outlook-on-the-web"></a><span data-ttu-id="05454-126">Gestire la visualizzazione del pulsante Crittografa in Outlook sul Web</span><span class="sxs-lookup"><span data-stu-id="05454-126">Manage the display of the Encrypt button in Outlook on the web</span></span>

<span data-ttu-id="05454-127">L'amministratore può decidere se visualizzare questo pulsante agli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="05454-127">As an administrator, you can manage whether to display this button to end users.</span></span>
  
### <a name="to-manage-whether-the-encrypt-button-appears-in-outlook-on-the-web"></a><span data-ttu-id="05454-128">Per gestire se il pulsante Crittografa viene visualizzato Outlook sul Web</span><span class="sxs-lookup"><span data-stu-id="05454-128">To manage whether the Encrypt button appears in Outlook on the web</span></span>
  
1. <span data-ttu-id="05454-129">Utilizzare un account aziendale o dell'istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione e avviare una sessione Windows PowerShell e connettersi a Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="05454-129">Use a work or school account that has global administrator permissions in your organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="05454-130">Per istruzioni, vedere [Connettersi a PowerShell di Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="05454-130">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="05454-131">Eseguire il cmdlet Set-IRMConfiguration con il parametro -SimplifiedClientAccessEnabled:</span><span class="sxs-lookup"><span data-stu-id="05454-131">Run the Set-IRMConfiguration cmdlet with the -SimplifiedClientAccessEnabled parameter:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled <$true|$false>
   ```

   <span data-ttu-id="05454-132">Ad esempio, per disabilitare il **pulsante Crittografa:**</span><span class="sxs-lookup"><span data-stu-id="05454-132">For example, to disable the **Encrypt** button:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

   <span data-ttu-id="05454-133">Per abilitare il **pulsante Crittografa:**</span><span class="sxs-lookup"><span data-stu-id="05454-133">To enable the **Encrypt** button:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $true
   ```

## <a name="enable-service-side-decryption-of-email-messages-for-ios-mail-app-users"></a><span data-ttu-id="05454-134">Abilitare la decrittografia lato servizio dei messaggi di posta elettronica per gli utenti dell'app di posta iOS</span><span class="sxs-lookup"><span data-stu-id="05454-134">Enable service-side decryption of email messages for iOS mail app users</span></span>

<span data-ttu-id="05454-135">L'app di posta iOS non può decrittografare i messaggi protetti con Office 365 Message Encryption.</span><span class="sxs-lookup"><span data-stu-id="05454-135">The iOS mail app can't decrypt messages protected with Office 365 Message Encryption.</span></span> <span data-ttu-id="05454-136">Come amministratore Microsoft 365, puoi applicare la decrittografia sul lato servizio per i messaggi recapitati all'app di posta iOS.</span><span class="sxs-lookup"><span data-stu-id="05454-136">As a Microsoft 365 administrator, you can apply service-side decryption for messages delivered to the iOS mail app.</span></span> <span data-ttu-id="05454-137">Quando scegli di usare la decrittografia sul lato servizio, il servizio invia una copia decrittografata del messaggio al dispositivo iOS.</span><span class="sxs-lookup"><span data-stu-id="05454-137">When you choose to do use service-side decryption, the service sends a decrypted copy of the message to the iOS device.</span></span> <span data-ttu-id="05454-138">Il dispositivo client archivia una copia decrittografata del messaggio.</span><span class="sxs-lookup"><span data-stu-id="05454-138">The client device stores a decrypted copy of the message.</span></span> <span data-ttu-id="05454-139">Il messaggio conserva anche le informazioni sui diritti di utilizzo anche se l'app di posta iOS non applica all'utente i diritti di utilizzo sul lato client.</span><span class="sxs-lookup"><span data-stu-id="05454-139">The message also retains information about usage rights even though the iOS mail app doesn't apply client-side usage rights to the user.</span></span> <span data-ttu-id="05454-140">L'utente può copiare o stampare il messaggio anche se originariamente non disponeva dei diritti necessari.</span><span class="sxs-lookup"><span data-stu-id="05454-140">The user can copy or print the message even if they didn't originally have the rights to do so.</span></span> <span data-ttu-id="05454-141">Tuttavia, se l'utente tenta di completare un'azione che richiede il server di posta Microsoft 365, ad esempio l'inoltro del messaggio, il server non consente l'azione se l'utente originariamente non ha il diritto di utilizzo per farlo.</span><span class="sxs-lookup"><span data-stu-id="05454-141">However, if the user attempts to complete an action that requires the Microsoft 365 mail server, such as forwarding the message, the server won't permit the action if the user didn't originally have the usage right to do so.</span></span> <span data-ttu-id="05454-142">Tuttavia, gli utenti finali possono aggirare la restrizione di utilizzo "Non inoltrare" inoltrando il messaggio da un account diverso all'interno dell'app di posta iOS.</span><span class="sxs-lookup"><span data-stu-id="05454-142">However, end users can work around "Do Not Forward" usage restriction by forwarding the message from a different account within the iOS mail app.</span></span> <span data-ttu-id="05454-143">Indipendentemente dal fatto che sia stata impostata la decrittografia sul lato servizio della posta, gli allegati alla posta crittografata e protetti da diritti non possono essere visualizzati nell'app di posta iOS.</span><span class="sxs-lookup"><span data-stu-id="05454-143">Regardless of whether you set up service-side decryption of mail, attachments to encrypted and rights protected mail can't be viewed in the iOS mail app.</span></span>
  
<span data-ttu-id="05454-144">Se si sceglie di non consentire l'invio di messaggi decrittografati agli utenti dell'app di posta elettronica iOS, gli utenti ricevono un messaggio che indica che non dispongono dei diritti per visualizzare il messaggio.</span><span class="sxs-lookup"><span data-stu-id="05454-144">If you choose not to allow decrypted messages to be sent to iOS mail app users, users receive a message that states that they don't have the rights to view the message.</span></span> <span data-ttu-id="05454-145">Per impostazione predefinita, la decrittografia sul lato servizio dei messaggi di posta elettronica non è abilitata.</span><span class="sxs-lookup"><span data-stu-id="05454-145">By default, service-side decryption of email messages is not enabled.</span></span>
  
<span data-ttu-id="05454-146">Per ulteriori informazioni e per una visualizzazione dell'esperienza client, vedere [View encrypted messages on your iPhone or iPad](https://support.microsoft.com/en-us/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf).</span><span class="sxs-lookup"><span data-stu-id="05454-146">For more information, and for a view of the client experience, see [View encrypted messages on your iPhone or iPad](https://support.microsoft.com/en-us/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf).</span></span>
  
### <a name="to-manage-whether-ios-mail-app-users-can-view-messages-protected-by-office-365-message-encryption"></a><span data-ttu-id="05454-147">Per gestire se gli utenti dell'app di posta elettronica iOS possono visualizzare i messaggi protetti da Office 365 Message Encryption</span><span class="sxs-lookup"><span data-stu-id="05454-147">To manage whether iOS mail app users can view messages protected by Office 365 Message Encryption</span></span>
  
1. <span data-ttu-id="05454-148">Utilizzare un account aziendale o dell'istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione e avviare una sessione Windows PowerShell e connettersi a Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="05454-148">Use a work or school account that has global administrator permissions in your organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="05454-149">Per istruzioni, vedere [Connettersi a PowerShell di Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="05454-149">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="05454-150">Eseguire il cmdlet Set-ActiveSyncOrganizations con il parametro AllowRMSSupportForUnenlightenedApps:</span><span class="sxs-lookup"><span data-stu-id="05454-150">Run the Set-ActiveSyncOrganizations cmdlet with the AllowRMSSupportForUnenlightenedApps parameter:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps <$true|$false>
   ```

   <span data-ttu-id="05454-151">Ad esempio, per configurare il servizio in modo che decrittografi i messaggi prima di essere inviati ad app senza luce come l'app di posta iOS:</span><span class="sxs-lookup"><span data-stu-id="05454-151">For example, to configure the service to decrypt messages before they're sent to unenlightened apps like the iOS mail app:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $true
   ```

   <span data-ttu-id="05454-152">In caso contrario, per configurare il servizio in modo che non invii messaggi decrittografati alle app senza protezione:</span><span class="sxs-lookup"><span data-stu-id="05454-152">Or, to configure the service not to send decrypted messages to unenlightened apps:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $false
   ```

> [!NOTE]
> <span data-ttu-id="05454-153">I singoli criteri cassetta postale (OWA/ActiveSync) sostituiscono queste impostazioni (ad esempio, se -IRMEnabled è impostato su False all'interno del rispettivo criterio cassetta postale di OWA o del criterio Cassetta postale di ActiveSync, queste configurazioni non vengono applicate).</span><span class="sxs-lookup"><span data-stu-id="05454-153">Individual mailbox policies (OWA/ActiveSync) override these settings (i.e. if -IRMEnabled is set to False within the respective OWA Mailbox policy, or ActiveSync Mailbox policy, then these configurations would not apply).</span></span>

## <a name="enable-service-side-decryption-of-email-attachments-for-web-browser-mail-clients"></a><span data-ttu-id="05454-154">Abilitare la decrittografia sul lato servizio degli allegati di posta elettronica per i client di posta del Browser Web</span><span class="sxs-lookup"><span data-stu-id="05454-154">Enable service-side decryption of email attachments for web browser mail clients</span></span>

<span data-ttu-id="05454-155">In genere, quando si utilizza Office 365 crittografia dei messaggi, gli allegati vengono crittografati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="05454-155">Normally, when you use Office 365 message encryption, attachments are automatically encrypted.</span></span> <span data-ttu-id="05454-156">Gli amministratori possono applicare la decrittografia sul lato servizio per gli allegati di posta elettronica scaricati dagli utenti da un Web browser.</span><span class="sxs-lookup"><span data-stu-id="05454-156">As an administrator, you can apply service-side decryption for email attachments that users download from a web browser.</span></span>
  
<span data-ttu-id="05454-157">Quando usi la decrittografia sul lato servizio, il servizio invia una copia decrittografata del file al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="05454-157">When you use service-side decryption, the service sends a decrypted copy of the file to the device.</span></span> <span data-ttu-id="05454-158">Il messaggio è ancora crittografato.</span><span class="sxs-lookup"><span data-stu-id="05454-158">The message is still encrypted.</span></span> <span data-ttu-id="05454-159">L'allegato di posta elettronica mantiene anche le informazioni sui diritti di utilizzo anche se il browser non applica all'utente i diritti di utilizzo sul lato client.</span><span class="sxs-lookup"><span data-stu-id="05454-159">The email attachment also keeps information about usage rights even though the browser doesn't apply client-side usage rights to the user.</span></span> <span data-ttu-id="05454-160">L'utente può copiare o stampare l'allegato di posta elettronica anche se originariamente non disponeva dei diritti necessari.</span><span class="sxs-lookup"><span data-stu-id="05454-160">The user can copy or print the email attachment even if they didn't originally have the rights to do so.</span></span> <span data-ttu-id="05454-161">Tuttavia, se l'utente tenta di completare un'azione che richiede il server di posta Microsoft 365, ad esempio l'inoltro dell'allegato, il server non consente l'azione se l'utente originariamente non ha il diritto di utilizzo per farlo.</span><span class="sxs-lookup"><span data-stu-id="05454-161">However, if the user tries to complete an action that requires the Microsoft 365 mail server, such as forwarding the attachment, the server won't permit the action if the user didn't originally have the usage right to do so.</span></span>
  
<span data-ttu-id="05454-162">Indipendentemente dalla configurazione della decrittografia sul lato servizio degli allegati, gli utenti non possono visualizzare gli allegati alla posta crittografata e protetta da diritti nell'app di posta iOS.</span><span class="sxs-lookup"><span data-stu-id="05454-162">Regardless of whether you set up service-side decryption of attachments, users can't view any attachments to encrypted and rights protected mail in the iOS mail app.</span></span>
  
<span data-ttu-id="05454-163">Se si sceglie di non consentire gli allegati di posta elettronica decrittografati, ovvero l'impostazione predefinita, gli utenti riceveranno un messaggio che indica che non dispongono dei diritti per visualizzare l'allegato.</span><span class="sxs-lookup"><span data-stu-id="05454-163">If you choose not to allow decrypted email attachments, which is the default, users receive a message that states that they don't have the rights to view the attachment.</span></span>
  
<span data-ttu-id="05454-164">Per ulteriori informazioni su come Microsoft 365 la crittografia per i messaggi di posta elettronica e gli allegati di posta elettronica con l'opzione Encrypt-Only, vedere [Encrypt-Only option for emails.](/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)</span><span class="sxs-lookup"><span data-stu-id="05454-164">For more information about how Microsoft 365 implements encryption for emails and email attachments with the Encrypt-Only option, see [Encrypt-Only option for emails.](/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)</span></span>
  
### <a name="to-manage-whether-email-attachments-are-decrypted-on-download-from-a-web-browser"></a><span data-ttu-id="05454-165">Per gestire se gli allegati di posta elettronica vengono decrittografati durante il download da un Web browser</span><span class="sxs-lookup"><span data-stu-id="05454-165">To manage whether email attachments are decrypted on download from a web browser</span></span>
  
1. <span data-ttu-id="05454-166">Utilizzare un account aziendale o dell'istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione e avviare una sessione Windows PowerShell e connettersi a Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="05454-166">Use a work or school account that has global administrator permissions in your organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="05454-167">Per istruzioni, vedere [Connettersi a PowerShell di Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="05454-167">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="05454-168">Eseguire il cmdlet Set-IRMConfiguration con il parametro DecryptAttachmentForEncryptOnly:</span><span class="sxs-lookup"><span data-stu-id="05454-168">Run the Set-IRMConfiguration cmdlet with the DecryptAttachmentForEncryptOnly parameter:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly <$true|$false>
   ```

   <span data-ttu-id="05454-169">Ad esempio, per configurare il servizio per decrittografare gli allegati di posta elettronica quando un utente li scarica da un Web browser:</span><span class="sxs-lookup"><span data-stu-id="05454-169">For example, to configure the service to decrypt email attachments when a user downloads them from a web browser:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
   ```

   <span data-ttu-id="05454-170">Per configurare il servizio in modo che gli allegati di posta elettronica crittografati non siano stati scaricati:</span><span class="sxs-lookup"><span data-stu-id="05454-170">To configure the service to leave encrypted email attachments as they are upon download:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $false
   ```

## <a name="ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail"></a><span data-ttu-id="05454-171">Verificare che tutti i destinatari esterni utilizzino il portale OME per leggere la posta crittografata</span><span class="sxs-lookup"><span data-stu-id="05454-171">Ensure all external recipients use the OME Portal to read encrypted mail</span></span>

<span data-ttu-id="05454-172">È possibile utilizzare modelli di personalizzazione personalizzati per forzare i destinatari a ricevere un messaggio wrapper che li invogli a leggere la posta elettronica crittografata nel portale OME invece di usare Outlook o Outlook sul Web.</span><span class="sxs-lookup"><span data-stu-id="05454-172">You can use custom branding templates to force recipients to receive a wrapper mail that directs them to read encrypted email in the OME Portal instead of using Outlook or Outlook on the web.</span></span> <span data-ttu-id="05454-173">Questa operazione può essere utile se si desidera un maggiore controllo su come i destinatari utilizzano la posta che ricevono.</span><span class="sxs-lookup"><span data-stu-id="05454-173">You might want to do this if you use want greater control over how recipients use the mail they receive.</span></span> <span data-ttu-id="05454-174">Ad esempio, se i destinatari esterni visualizzano la posta elettronica nel portale Web, è possibile impostare una data di scadenza per il messaggio di posta elettronica e revocare il messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="05454-174">For example, if external recipients view email in the web portal, you can set an expiration date for the email, and you can revoke the email.</span></span> <span data-ttu-id="05454-175">Queste funzionalità sono supportate solo tramite il portale OME.</span><span class="sxs-lookup"><span data-stu-id="05454-175">These features are only supported through the OME Portal.</span></span> <span data-ttu-id="05454-176">È possibile utilizzare l'opzione Crittografa e l'opzione Non inoltrare durante la creazione delle regole del flusso di posta.</span><span class="sxs-lookup"><span data-stu-id="05454-176">You can use the Encrypt option and the Do Not Forward option when creating the mail flow rules.</span></span>

### <a name="use-a-custom-template-to-force-all-external-recipients-to-use-the-ome-portal-and-for-encrypted-email"></a><span data-ttu-id="05454-177">Utilizzare un modello personalizzato per forzare tutti i destinatari esterni a utilizzare il portale OME e per la posta elettronica crittografata</span><span class="sxs-lookup"><span data-stu-id="05454-177">Use a custom template to force all external recipients to use the OME Portal and for encrypted email</span></span>

1. <span data-ttu-id="05454-178">Utilizzare un account aziendale o dell'istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione e avviare una sessione Windows PowerShell e connettersi a Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="05454-178">Use a work or school account that has global administrator permissions in your organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="05454-179">Per istruzioni, vedere [Connettersi a PowerShell di Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="05454-179">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="05454-180">Eseguire il cmdlet New-TransportRule:</span><span class="sxs-lookup"><span data-stu-id="05454-180">Run the New-TransportRule cmdlet:</span></span>

   ```powershell
   New-TransportRule -name "<mail flow rule name>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "<option name>" -ApplyRightsProtectionCustomizationTemplate "<template name>"
   ```

    <span data-ttu-id="05454-181">dove:</span><span class="sxs-lookup"><span data-stu-id="05454-181">where:</span></span>

   - <span data-ttu-id="05454-182">`mail flow rule name` è il nome che si desidera utilizzare per la nuova regola del flusso di posta.</span><span class="sxs-lookup"><span data-stu-id="05454-182">`mail flow rule name` is the name you want to use for the new mail flow rule.</span></span>

   - <span data-ttu-id="05454-183">`option name` è o `Encrypt` `Do Not Forward` .</span><span class="sxs-lookup"><span data-stu-id="05454-183">`option name` is either `Encrypt` or `Do Not Forward`.</span></span>

   - <span data-ttu-id="05454-184">`template name` è il nome che hai fornito al modello di personalizzazione personalizzato, ad esempio `OME Configuration` .</span><span class="sxs-lookup"><span data-stu-id="05454-184">`template name` is the name you gave the custom branding template, for example `OME Configuration`.</span></span>

   <span data-ttu-id="05454-185">Per crittografare tutti i messaggi di posta elettronica esterni con il modello "Configurazione OME" e applicare l'Encrypt-Only seguente:</span><span class="sxs-lookup"><span data-stu-id="05454-185">To encrypt all external email with the "OME Configuration" template and apply the Encrypt-Only option:</span></span>

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Encrypt" -ApplyRightsProtectionCustomizationTemplate "OME Configuration"
   ```

   <span data-ttu-id="05454-186">Per crittografare tutta la posta elettronica esterna con il modello "Configurazione OME" e applicare l'opzione Non inoltrare:</span><span class="sxs-lookup"><span data-stu-id="05454-186">To encrypt all external email with the "OME Configuration" template and apply the Do Not Forward option:</span></span>

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Do Not Forward" -ApplyRightsProtectionCustomizationTemplate "OME Configuration"
   ```

## <a name="customize-the-appearance-of-email-messages-and-the-ome-portal"></a><span data-ttu-id="05454-187">Personalizzare l'aspetto dei messaggi di posta elettronica e del portale OME</span><span class="sxs-lookup"><span data-stu-id="05454-187">Customize the appearance of email messages and the OME portal</span></span>

<span data-ttu-id="05454-188">Per informazioni dettagliate su come personalizzare OME per l'organizzazione, vedere Aggiungere il marchio [dell'organizzazione ai messaggi crittografati.](add-your-organization-brand-to-encrypted-messages.md)</span><span class="sxs-lookup"><span data-stu-id="05454-188">For detailed information about how you can customize OME for your organization, see [Add your organization's brand to your encrypted messages](add-your-organization-brand-to-encrypted-messages.md).</span></span>
  
## <a name="disable-the-new-capabilities-for-ome"></a><span data-ttu-id="05454-189">Disabilitare le nuove funzionalità per OME</span><span class="sxs-lookup"><span data-stu-id="05454-189">Disable the new capabilities for OME</span></span>

<span data-ttu-id="05454-190">Ci auguriamo che non sia possibile, ma, se necessario, disabilitare le nuove funzionalità per OME è molto semplice.</span><span class="sxs-lookup"><span data-stu-id="05454-190">We hope it doesn't come to it, but if you need to, disabling the new capabilities for OME is very straightforward.</span></span> <span data-ttu-id="05454-191">Prima di tutto, è necessario rimuovere tutte le regole del flusso di posta create che utilizzano le nuove funzionalità OME.</span><span class="sxs-lookup"><span data-stu-id="05454-191">First, you'll need to remove any mail flow rules you've created that use the new OME capabilities.</span></span> <span data-ttu-id="05454-192">Per informazioni sulla rimozione delle regole del flusso di posta, vedere [Manage mail flow rules](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules).</span><span class="sxs-lookup"><span data-stu-id="05454-192">For information about removing mail flow rules, see [Manage mail flow rules](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules).</span></span> <span data-ttu-id="05454-193">Quindi, completare questi passaggi in Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="05454-193">Then, complete these steps in Exchange Online PowerShell.</span></span>
  
### <a name="to-disable-the-new-capabilities-for-ome"></a><span data-ttu-id="05454-194">Per disabilitare le nuove funzionalità per OME</span><span class="sxs-lookup"><span data-stu-id="05454-194">To disable the new capabilities for OME</span></span>
  
1. <span data-ttu-id="05454-195">Utilizzando un account aziendale o dell'istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione, avviare una sessione Windows PowerShell e connettersi a Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="05454-195">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="05454-196">Per istruzioni, vedere [Connettersi a PowerShell di Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="05454-196">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="05454-197">Se è stato **abilitato** il pulsante Crittografa Outlook sul Web, disabilitarlo eseguendo il cmdlet Set-IRMConfiguration con il parametro SimplifiedClientAccessEnabled.</span><span class="sxs-lookup"><span data-stu-id="05454-197">If you enabled the **Encrypt** button in Outlook on the web, disable it by running the Set-IRMConfiguration cmdlet with the SimplifiedClientAccessEnabled parameter.</span></span> <span data-ttu-id="05454-198">In caso contrario, ignorare questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="05454-198">Otherwise, skip this step.</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

3. <span data-ttu-id="05454-199">Disabilitare le nuove funzionalità per OME eseguendo il cmdlet Set-IRMConfiguration con il parametro AzureRMSLicensingEnabled impostato su false:</span><span class="sxs-lookup"><span data-stu-id="05454-199">Disable the new capabilities for OME by running the Set-IRMConfiguration cmdlet with the AzureRMSLicensingEnabled parameter set to false:</span></span>

   ```powershell
   Set-IRMConfiguration -AzureRMSLicensingEnabled $false
   ```
