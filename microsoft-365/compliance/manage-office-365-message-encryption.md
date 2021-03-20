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
description: Dopo aver completato la configurazione di Office 365 Message Encryption (OME), informazioni su come personalizzare la distribuzione in diversi modi.
ms.openlocfilehash: 06e9d22d51c05fe9f7bc4c1a014607feafbf2dba
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908186"
---
# <a name="manage-office-365-message-encryption"></a>Gestire Office 365 Message Encryption

Dopo aver completato la configurazione della crittografia dei messaggi di Office 365, è possibile personalizzare la configurazione della distribuzione in diversi modi. Ad esempio, è possibile configurare se abilitare i  pass code una sola volta, visualizzare il pulsante Crittografa in Outlook sul Web e altro ancora. Le attività descritte in questo articolo descrivono come.

## <a name="manage-whether-google-yahoo-and-microsoft-account-recipients-can-use-these-accounts-to-sign-in-to-the-office-365-message-encryption-portal"></a>Gestire se i destinatari di Google, Yahoo e Account Microsoft possono usare questi account per accedere al portale di crittografia dei messaggi di Office 365

Quando si configurano le nuove funzionalità di crittografia dei messaggi di Office 365, gli utenti dell'organizzazione possono inviare messaggi a destinatari esterni all'organizzazione. Se il destinatario usa un *ID di social* network, ad esempio un account Google, un account Yahoo o un account Microsoft, il destinatario può accedere al portale OME con un ID social. Se si desidera, è possibile scegliere di non consentire ai destinatari di utilizzare ID di social network per accedere al portale OME.
  
### <a name="to-manage-whether-recipients-can-use-social-ids-to-sign-in-to-the-ome-portal"></a>Per gestire se i destinatari possono utilizzare gli ID social per accedere al portale OME
  
1. [Connettersi a Exchange Online utilizzando Remote PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)

2. Eseguire il cmdlet Set-OMEConfiguration con il parametro SocialIdSignIn come indicato di seguito:

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter"> -SocialIdSignIn <$true|$false>
   ```

   Ad esempio, per disabilitare gli ID social:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $false
   ```

   Per abilitare gli ID social:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $true
   ```

## <a name="manage-the-use-of-one-time-pass-codes-for-the-office-365-message-encryption-portal"></a>Gestire l'uso di codici di accesso una sola volta per il portale di crittografia dei messaggi di Office 365

Se il destinatario di un messaggio crittografato da OME non utilizza Outlook, indipendentemente dall'account utilizzato dal destinatario, il destinatario riceve un collegamento di visualizzazione Web a tempo limitato che consente loro di leggere il messaggio. Questo collegamento include un pass code una sola volta. Gli amministratori possono decidere se i destinatari possono utilizzare pass code una sola volta per accedere al portale OME.
  
### <a name="to-manage-whether-ome-generates-one-time-pass-codes"></a>Per gestire se OME genera pass code una sola volta
  
1. Utilizzare un account aziendale o dell'istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione e avviare una sessione Windows PowerShell e connettersi a Exchange Online. Per istruzioni, vedere [Connettersi a PowerShell di Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

2. Eseguire il cmdlet Set-OMEConfiguration con il parametro OTPEnabled:

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter "> -OTPEnabled <$true|$false>
   ```

   Ad esempio, per disabilitare i pass code una sola volta:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $false
   ```

   Per abilitare i pass code una sola volta:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $true
   ```

## <a name="manage-the-display-of-the-encrypt-button-in-outlook-on-the-web"></a>Gestire la visualizzazione del pulsante Crittografa in Outlook sul Web

L'amministratore può decidere se visualizzare questo pulsante agli utenti finali.
  
### <a name="to-manage-whether-the-encrypt-button-appears-in-outlook-on-the-web"></a>Per gestire se il pulsante Crittografa viene visualizzato in Outlook sul Web
  
1. Utilizzare un account aziendale o dell'istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione e avviare una sessione Windows PowerShell e connettersi a Exchange Online. Per istruzioni, vedere [Connettersi a PowerShell di Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

2. Eseguire il cmdlet Set-IRMConfiguration con il parametro -SimplifiedClientAccessEnabled:

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled <$true|$false>
   ```

   Ad esempio, per disabilitare il **pulsante Crittografa:**

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

   Per abilitare il **pulsante Crittografa:**

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $true
   ```

## <a name="enable-service-side-decryption-of-email-messages-for-ios-mail-app-users"></a>Abilitare la decrittografia lato servizio dei messaggi di posta elettronica per gli utenti dell'app di posta iOS

L'app di posta iOS non è in grado di decrittografare i messaggi protetti con crittografia dei messaggi di Office 365. In qualità di amministratore di Microsoft 365, puoi applicare la decrittografia sul lato servizio per i messaggi recapitati all'app di posta iOS. Quando scegli di usare la decrittografia sul lato servizio, il servizio invia una copia decrittografata del messaggio al dispositivo iOS. Il dispositivo client archivia una copia decrittografata del messaggio. Il messaggio conserva anche le informazioni sui diritti di utilizzo anche se l'app di posta iOS non applica all'utente i diritti di utilizzo sul lato client. L'utente può copiare o stampare il messaggio anche se originariamente non disponeva dei diritti necessari. Tuttavia, se l'utente tenta di completare un'azione che richiede il server di posta di Microsoft 365, ad esempio l'inoltro del messaggio, il server non consente l'azione se l'utente originariamente non ha il diritto di utilizzo per farlo. Tuttavia, gli utenti finali possono aggirare la restrizione di utilizzo "Non inoltrare" inoltrando il messaggio da un account diverso all'interno dell'app di posta iOS. Indipendentemente dal fatto che sia stata impostata la decrittografia sul lato servizio della posta, gli allegati alla posta crittografata e protetti da diritti non possono essere visualizzati nell'app di posta iOS.
  
Se si sceglie di non consentire l'invio di messaggi decrittografati agli utenti dell'app di posta elettronica iOS, gli utenti ricevono un messaggio che indica che non dispongono dei diritti per visualizzare il messaggio. Per impostazione predefinita, la decrittografia sul lato servizio dei messaggi di posta elettronica non è abilitata.
  
Per altre informazioni e per una visualizzazione dell'esperienza client, vedi Visualizzare i messaggi crittografati [sul tuo iPhone o iPad.](https://support.microsoft.com/en-us/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf)
  
### <a name="to-manage-whether-ios-mail-app-users-can-view-messages-protected-by-office-365-message-encryption"></a>Per gestire se gli utenti dell'app di posta iOS possono visualizzare i messaggi protetti dalla crittografia dei messaggi di Office 365
  
1. Utilizzare un account aziendale o dell'istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione e avviare una sessione Windows PowerShell e connettersi a Exchange Online. Per istruzioni, vedere [Connettersi a PowerShell di Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

2. Eseguire il cmdlet Set-ActiveSyncOrganizations con il parametro AllowRMSSupportForUnenlightenedApps:

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps <$true|$false>
   ```

   Ad esempio, per configurare il servizio in modo che decrittografi i messaggi prima di essere inviati ad app senza luce come l'app di posta iOS:

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $true
   ```

   In caso contrario, per configurare il servizio in modo che non invii messaggi decrittografati alle app senza protezione:

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $false
   ```

> [!NOTE]
> I singoli criteri cassetta postale (OWA/ActiveSync) sostituiscono queste impostazioni (ad esempio, se -IRMEnabled è impostato su False all'interno del rispettivo criterio cassetta postale di OWA o del criterio Cassetta postale di ActiveSync, queste configurazioni non vengono applicate).

## <a name="enable-service-side-decryption-of-email-attachments-for-web-browser-mail-clients"></a>Abilitare la decrittografia sul lato servizio degli allegati di posta elettronica per i client di posta del Browser Web

In genere, quando si utilizza la crittografia dei messaggi di Office 365, gli allegati vengono crittografati automaticamente. Gli amministratori possono applicare la decrittografia sul lato servizio per gli allegati di posta elettronica scaricati dagli utenti da un Web browser.
  
Quando usi la decrittografia sul lato servizio, il servizio invia una copia decrittografata del file al dispositivo. Il messaggio è ancora crittografato. L'allegato di posta elettronica mantiene anche le informazioni sui diritti di utilizzo anche se il browser non applica all'utente i diritti di utilizzo sul lato client. L'utente può copiare o stampare l'allegato di posta elettronica anche se originariamente non disponeva dei diritti necessari. Tuttavia, se l'utente tenta di completare un'azione che richiede il server di posta di Microsoft 365, ad esempio l'inoltro dell'allegato, il server non consente l'azione se l'utente originariamente non ha il diritto di utilizzo per farlo.
  
Indipendentemente dalla configurazione della decrittografia sul lato servizio degli allegati, gli utenti non possono visualizzare gli allegati alla posta crittografata e protetta da diritti nell'app di posta iOS.
  
Se si sceglie di non consentire gli allegati di posta elettronica decrittografati, ovvero l'impostazione predefinita, gli utenti riceveranno un messaggio che indica che non dispongono dei diritti per visualizzare l'allegato.
  
Per ulteriori informazioni su come Microsoft 365 implementa la crittografia per i messaggi di posta elettronica e gli allegati di posta elettronica con l'opzione Encrypt-Only, vedere [Encrypt-Only option for emails.](/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)
  
### <a name="to-manage-whether-email-attachments-are-decrypted-on-download-from-a-web-browser"></a>Per gestire se gli allegati di posta elettronica vengono decrittografati durante il download da un Web browser
  
1. Utilizzare un account aziendale o dell'istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione e avviare una sessione Windows PowerShell e connettersi a Exchange Online. Per istruzioni, vedere [Connettersi a PowerShell di Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

2. Eseguire il cmdlet Set-IRMConfiguration con il parametro DecryptAttachmentForEncryptOnly:

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly <$true|$false>
   ```

   Ad esempio, per configurare il servizio per decrittografare gli allegati di posta elettronica quando un utente li scarica da un Web browser:

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
   ```

   Per configurare il servizio in modo che gli allegati di posta elettronica crittografati non siano stati scaricati:

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $false
   ```

## <a name="ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail"></a>Verificare che tutti i destinatari esterni utilizzino il portale OME per leggere la posta crittografata

È possibile utilizzare modelli di personalizzazione personalizzati per forzare i destinatari a ricevere un messaggio wrapper che li invogli a leggere la posta elettronica crittografata nel portale OME invece di utilizzare Outlook o Outlook sul Web. Questa operazione può essere utile se si desidera un maggiore controllo su come i destinatari utilizzano la posta che ricevono. Ad esempio, se i destinatari esterni visualizzano la posta elettronica nel portale Web, è possibile impostare una data di scadenza per il messaggio di posta elettronica e revocare il messaggio di posta elettronica. Queste funzionalità sono supportate solo tramite il portale OME. È possibile utilizzare l'opzione Crittografa e l'opzione Non inoltrare durante la creazione delle regole del flusso di posta.

### <a name="use-a-custom-template-to-force-all-external-recipients-to-use-the-ome-portal-and-for-encrypted-email"></a>Utilizzare un modello personalizzato per forzare tutti i destinatari esterni a utilizzare il portale OME e per la posta elettronica crittografata

1. Utilizzare un account aziendale o dell'istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione e avviare una sessione Windows PowerShell e connettersi a Exchange Online. Per istruzioni, vedere [Connettersi a PowerShell di Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

2. Eseguire il cmdlet New-TransportRule:

   ```powershell
   New-TransportRule -name "<mail flow rule name>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "<option name>" -ApplyRightsProtectionCustomizationTemplate "<template name>"
   ```

    dove:

   - `mail flow rule name` è il nome che si desidera utilizzare per la nuova regola del flusso di posta.

   - `option name` è o `Encrypt` `Do Not Forward` .

   - `template name` è il nome che hai fornito al modello di personalizzazione personalizzato, ad esempio `OME Configuration` .

   Per crittografare tutti i messaggi di posta elettronica esterni con il modello "Configurazione OME" e applicare l'Encrypt-Only seguente:

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Encrypt" -ApplyRightsProtectionCustomizationTemplate "OME Configuration"
   ```

   Per crittografare tutta la posta elettronica esterna con il modello "Configurazione OME" e applicare l'opzione Non inoltrare:

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Do Not Forward" -ApplyRightsProtectionCustomizationTemplate "OME Configuration"
   ```

## <a name="customize-the-appearance-of-email-messages-and-the-ome-portal"></a>Personalizzare l'aspetto dei messaggi di posta elettronica e del portale OME

Per informazioni dettagliate su come personalizzare OME per l'organizzazione, vedere Aggiungere il marchio [dell'organizzazione ai messaggi crittografati.](add-your-organization-brand-to-encrypted-messages.md)
  
## <a name="disable-the-new-capabilities-for-ome"></a>Disabilitare le nuove funzionalità per OME

Ci auguriamo che non sia possibile, ma, se necessario, disabilitare le nuove funzionalità per OME è molto semplice. Prima di tutto, è necessario rimuovere tutte le regole del flusso di posta create che utilizzano le nuove funzionalità OME. Per informazioni sulla rimozione delle regole del flusso di posta, vedere [Manage mail flow rules](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules). Quindi, completare questi passaggi in PowerShell di Exchange Online.
  
### <a name="to-disable-the-new-capabilities-for-ome"></a>Per disabilitare le nuove funzionalità per OME
  
1. Utilizzando un account aziendale o dell'istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione, avviare una sessione Windows PowerShell e connettersi a Exchange Online. Per istruzioni, vedere [Connettersi a PowerShell di Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

2. Se è stato **abilitato** il pulsante Crittografa in Outlook sul Web, disabilitarlo eseguendo il cmdlet Set-IRMConfiguration con il parametro SimplifiedClientAccessEnabled. In caso contrario, ignorare questo passaggio.

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

3. Disabilitare le nuove funzionalità per OME eseguendo il cmdlet Set-IRMConfiguration con il parametro AzureRMSLicensingEnabled impostato su false:

   ```powershell
   Set-IRMConfiguration -AzureRMSLicensingEnabled $false
   ```