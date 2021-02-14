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
ms.openlocfilehash: 83fa620852ea9b2e0cd50d50b6715742658b7239
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2020
ms.locfileid: "44815433"
---
# <a name="manage-office-365-message-encryption"></a>Gestire Office 365 Message Encryption

Dopo aver completato la configurazione della crittografia dei messaggi di Office 365, è possibile personalizzare la configurazione della distribuzione in diversi modi. Ad esempio, è possibile configurare se abilitare i  pass code una sola volta, visualizzare il pulsante Crittografa in Outlook sul Web e altro ancora. Le attività descritte in questo articolo illustrano come.

## <a name="manage-whether-google-yahoo-and-microsoft-account-recipients-can-use-these-accounts-to-sign-in-to-the-office-365-message-encryption-portal"></a>Stabilire se i destinatari di Google, Yahoo e Account Microsoft possono usare questi account per accedere al portale di crittografia dei messaggi di Office 365

Quando si configurano le nuove funzionalità di crittografia dei messaggi di Office 365, gli utenti dell'organizzazione possono inviare messaggi a destinatari esterni all'organizzazione. Se il destinatario utilizza un *ID di social* network, ad esempio un account Google, un account Yahoo o un account Microsoft, il destinatario può accedere al portale OME con un ID di social network. Se si desidera, è possibile scegliere di non consentire ai destinatari di utilizzare GLI ID social per accedere al portale OME.
  
### <a name="to-manage-whether-recipients-can-use-social-ids-to-sign-in-to-the-ome-portal"></a>Per stabilire se i destinatari possono utilizzare gli ID social per accedere al portale OME
  
1. [Connettersi a Exchange Online utilizzando Remote PowerShell.](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx)

2. Eseguire il cmdlet Set-OMEConfiguration con il parametro SocialIdSignIn nel modo seguente:

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter"> -SocialIdSignIn <$true|$false>
   ```

   Ad esempio, per disabilitare gli ID social:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $false
   ```

   Per abilitare gli ID di social network:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $true
   ```

## <a name="manage-the-use-of-one-time-pass-codes-for-the-office-365-message-encryption-portal"></a>Gestire l'uso di pass code una sola volta per il portale di crittografia dei messaggi di Office 365

Se il destinatario di un messaggio crittografato da OME non utilizza Outlook, indipendentemente dall'account utilizzato dal destinatario, il destinatario riceve un collegamento alla visualizzazione Web in un periodo di tempo limitato che consente di leggere il messaggio. Questo collegamento include un codice di passaggio una sola volta. Gli amministratori possono decidere se i destinatari possono utilizzare pass code una sola volta per accedere al portale OME.
  
### <a name="to-manage-whether-ome-generates-one-time-pass-codes"></a>Per determinare se OME genera pass code una sola volta
  
1. Utilizzare un account aziendale o dell'istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione e avviare una sessione Windows PowerShell e connettersi a Exchange Online. Per istruzioni, vedere [Connettersi a PowerShell di Exchange Online](https://aka.ms/exopowershell).

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

Gli amministratori possono decidere se visualizzare questo pulsante agli utenti finali.
  
### <a name="to-manage-whether-the-encrypt-button-appears-in-outlook-on-the-web"></a>Per gestire se il pulsante Crittografa viene visualizzato in Outlook sul Web
  
1. Utilizzare un account aziendale o dell'istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione e avviare una sessione Windows PowerShell e connettersi a Exchange Online. Per istruzioni, vedere [Connettersi a PowerShell di Exchange Online](https://aka.ms/exopowershell).

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

L'app di posta iOS non è in grado di decrittografare i messaggi protetti con crittografia dei messaggi di Office 365. Gli amministratori di Microsoft 365 possono applicare la decrittografia sul lato servizio per i messaggi recapitati all'app di posta iOS. Quando scegli di usare la decrittografia sul lato servizio, il servizio invia una copia decrittografata del messaggio al dispositivo iOS. Il dispositivo client archivia una copia decrittografata del messaggio. Il messaggio conserva anche le informazioni sui diritti di utilizzo anche se l'app di posta elettronica iOS non applica i diritti di utilizzo sul lato client all'utente. L'utente può copiare o stampare il messaggio anche se in origine non disponeva dei diritti necessari. Tuttavia, se l'utente tenta di completare un'azione che richiede il server di posta di Microsoft 365, ad esempio l'inoltro del messaggio, il server non consente l'azione se l'utente in origine non ha il diritto di utilizzo per farlo. Tuttavia, gli utenti finali possono aggirare la restrizione di utilizzo "Non inoltrare" inoltrando il messaggio da un account diverso all'interno dell'app di posta iOS. Indipendentemente dal fatto che sia stata impostata la decrittografia sul lato servizio della posta, gli allegati alla posta crittografata e protetti da diritti non possono essere visualizzati nell'app di posta iOS.
  
Se si sceglie di non consentire l'invio dei messaggi decrittografati agli utenti dell'app di posta elettronica iOS, gli utenti ricevono un messaggio che indica che non dispongono dei diritti per visualizzare il messaggio. Per impostazione predefinita, la decrittografia lato servizio dei messaggi di posta elettronica non è abilitata.
  
Per altre informazioni e per una visualizzazione dell'esperienza client, vedi Visualizzare i messaggi crittografati [sul tuo iPhone o iPad.](https://support.microsoft.com/en-us/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf)
  
### <a name="to-manage-whether-ios-mail-app-users-can-view-messages-protected-by-office-365-message-encryption"></a>Per gestire se gli utenti dell'app di posta elettronica iOS possono visualizzare i messaggi protetti dalla crittografia dei messaggi di Office 365
  
1. Utilizzare un account aziendale o dell'istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione e avviare una sessione Windows PowerShell e connettersi a Exchange Online. Per istruzioni, vedere [Connettersi a PowerShell di Exchange Online](https://aka.ms/exopowershell).

2. Eseguire il cmdlet Set-ActiveSyncOrganizations con il parametro AllowRMSSupportForUnenlightenedApps:

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps <$true|$false>
   ```

   Ad esempio, per configurare il servizio per decrittografare i messaggi prima di essere inviati ad app senza protezione dei dati aziendali come l'app di posta iOS:

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $true
   ```

   Oppure, per configurare il servizio in modo che non invii messaggi decrittografati alle app senza protezione dei dati aziendali:

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $false
   ```

> [!NOTE]
> I singoli criteri cassetta postale (OWA/ActiveSync) sostituiscono queste impostazioni (ad esempio se -IRMEnabled è impostato su False all'interno del rispettivo criterio cassetta postale OWA o del criterio Cassetta postale di ActiveSync, queste configurazioni non verrebbero applicate).

## <a name="enable-service-side-decryption-of-email-attachments-for-web-browser-mail-clients"></a>Abilitare la decrittografia lato servizio degli allegati di posta elettronica per i client di posta elettronica del Web browser

In genere, quando si utilizza la crittografia dei messaggi di Office 365, gli allegati vengono crittografati automaticamente. Gli amministratori possono applicare la decrittografia sul lato servizio per gli allegati di posta elettronica scaricati dagli utenti da un Web browser.
  
Quando si utilizza la decrittografia sul lato servizio, il servizio invia una copia decrittografata del file al dispositivo. Il messaggio è ancora crittografato. L'allegato di posta elettronica mantiene anche le informazioni sui diritti di utilizzo anche se il browser non applica i diritti di utilizzo sul lato client all'utente. L'utente può copiare o stampare l'allegato di posta elettronica anche se in origine non dispone dei diritti necessari. Tuttavia, se l'utente tenta di completare un'azione che richiede il server di posta di Microsoft 365, ad esempio l'inoltro dell'allegato, il server non consente l'azione se l'utente in origine non ha il diritto di utilizzo per farlo.
  
Indipendentemente dal fatto che sia stata impostata la decrittografia degli allegati sul lato servizio, gli utenti non possono visualizzare gli allegati alla posta crittografata e protetta da diritti nell'app di posta iOS.
  
Se si sceglie di non consentire gli allegati di posta elettronica decrittografati, ovvero l'impostazione predefinita, gli utenti ricevono un messaggio che indica che non dispongono dei diritti per visualizzare l'allegato.
  
Per ulteriori informazioni su come Microsoft 365 implementa la crittografia per i messaggi di posta elettronica e gli allegati di posta elettronica con l'opzione Encrypt-Only, vedere [Encrypt-Only option for emails.](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)
  
### <a name="to-manage-whether-email-attachments-are-decrypted-on-download-from-a-web-browser"></a>Per gestire se gli allegati di posta elettronica vengono decrittografati al download da un Web browser
  
1. Utilizzare un account aziendale o dell'istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione e avviare una sessione Windows PowerShell e connettersi a Exchange Online. Per istruzioni, vedere [Connettersi a PowerShell di Exchange Online](https://aka.ms/exopowershell).

2. Eseguire il cmdlet Set-IRMConfiguration con il parametro DecryptAttachmentForEncryptOnly:

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly <$true|$false>
   ```

   Ad esempio, per configurare il servizio per decrittografare gli allegati di posta elettronica quando un utente li scarica da un Web browser:

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
   ```

   Per configurare il servizio in modo che gli allegati di posta elettronica crittografati non siano al momento del download:

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $false
   ```

## <a name="ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail"></a>Verificare che tutti i destinatari esterni utilizzino il portale OME per leggere la posta crittografata

È possibile utilizzare modelli di personalizzazione personalizzati per forzare i destinatari a ricevere un messaggio wrapper che li invogli a leggere la posta elettronica crittografata nel portale OME invece di utilizzare Outlook o Outlook sul Web. Questa operazione può essere utile se si desidera un maggiore controllo sul modo in cui i destinatari utilizzano la posta ricevuta. Ad esempio, se i destinatari esterni visualizzano la posta elettronica nel portale Web, è possibile impostare una data di scadenza per il messaggio e revocare il messaggio di posta elettronica. Queste funzionalità sono supportate solo tramite il portale OME. È possibile utilizzare l'opzione Crittografa e l'opzione Non inoltrare durante la creazione delle regole del flusso di posta.

### <a name="use-a-custom-template-to-force-all-external-recipients-to-use-the-ome-portal-and-for-encrypted-email"></a>Utilizzare un modello personalizzato per forzare tutti i destinatari esterni a utilizzare il portale OME e per la posta elettronica crittografata

1. Utilizzare un account aziendale o dell'istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione e avviare una sessione Windows PowerShell e connettersi a Exchange Online. Per istruzioni, vedere [Connettersi a PowerShell di Exchange Online](https://aka.ms/exopowershell).

2. Eseguire il cmdlet New-TransportRule seguente:

   ```powershell
   New-TransportRule -name "<mail flow rule name>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "<option name>" -ApplyRightsProtectionCustomizationTemplate "<template name>"
   ```

    dove:

   - `mail flow rule name` è il nome che si desidera utilizzare per la nuova regola del flusso di posta.

   - `option name` è o `Encrypt` `Do Not Forward` .

   - `template name` è il nome fornito al modello di personalizzazione, ad esempio `OME Configuration` .

   Per crittografare tutta la posta elettronica esterna con il modello "Configurazione OME" e applicare l'Encrypt-Only seguente:

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

Ci auguriamo che non sia possibile, ma, se necessario, disabilitare le nuove funzionalità per OME è molto semplice. Prima di tutto, è necessario rimuovere tutte le regole del flusso di posta create che utilizzano le nuove funzionalità di OME. Per informazioni sulla rimozione delle regole del flusso di posta, vedere [Manage mail flow rules.](https://technet.microsoft.com/library/jj657505%28v=exchg.150%29.aspx) Quindi, completare questi passaggi in PowerShell di Exchange Online.
  
### <a name="to-disable-the-new-capabilities-for-ome"></a>Per disabilitare le nuove funzionalità per OME
  
1. Utilizzando un account aziendale o dell'istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione, avviare una sessione Windows PowerShell e connettersi a Exchange Online. Per istruzioni, vedere [Connettersi a PowerShell di Exchange Online](https://aka.ms/exopowershell).

2. Se è stato **abilitato** il pulsante Crittografa in Outlook sul Web, disabilitarlo eseguendo il cmdlet Set-IRMConfiguration con il parametro SimplifiedClientAccessEnabled. In caso contrario, ignorare questo passaggio.

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

3. Disabilitare le nuove funzionalità per OME eseguendo il cmdlet Set-IRMConfiguration con il parametro AzureRMSLicensingEnabled impostato su false:

   ```powershell
   Set-IRMConfiguration -AzureRMSLicensingEnabled $false
   ```
