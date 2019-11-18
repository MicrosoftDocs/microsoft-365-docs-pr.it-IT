---
title: Gestire Office 365 Message Encryption
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
description: Dopo aver configurato Office 365 Message Encryption (OME), è possibile personalizzare la configurazione della distribuzione in diversi modi. Ad esempio, è possibile configurare la possibilità di abilitare i codici Pass una tantum, visualizzare il pulsante Proteggi in Outlook sul Web e altro ancora. Le attività descritte in questo articolo illustrano come fare.
ms.openlocfilehash: 780be179485fa18f7e0da0fabc7bb5365238da94
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2019
ms.locfileid: "38686418"
---
# <a name="manage-office-365-message-encryption"></a>Gestire Office 365 Message Encryption

Dopo aver configurato Office 365 Message Encryption (OME), è possibile personalizzare la configurazione della distribuzione in diversi modi. Ad esempio, è possibile configurare la possibilità di abilitare i codici Pass una tantum, visualizzare il pulsante **Crittografa** in Outlook sul Web e altro ancora. Le attività descritte in questo articolo illustrano come fare.

## <a name="manage-whether-google-yahoo-and-microsoft-account-recipients-can-use-these-accounts-to-sign-in-to-the-office-365-message-encryption-portal"></a>Gestire se i destinatari di Google, Yahoo e Microsoft account possono utilizzare questi account per accedere al portale di crittografia dei messaggi di Office 365

Quando si configurano le nuove funzionalità di crittografia dei messaggi di Office 365, gli utenti dell'organizzazione possono inviare messaggi ai destinatari esterni all'organizzazione di Office 365. Se il destinatario utilizza un *ID sociale* , ad esempio un account Google, un account Yahoo o un account Microsoft, il destinatario può accedere al portale ome con un ID sociale. Se lo si desidera, è possibile scegliere di non consentire ai destinatari di utilizzare gli ID di social networking per accedere al portale OME.
  
### <a name="to-manage-whether-recipients-can-use-social-ids-to-sign-in-to-the-ome-portal"></a>Per gestire se i destinatari possono utilizzare gli ID di social networking per accedere al portale OME
  
1. [Connettersi a Exchange Online tramite Remote PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).

2. Eseguire il cmdlet Set-OMEConfiguration con il parametro SocialIdSignIn, come indicato di seguito:

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter"> -SocialIdSignIn <$true|$false>
   ```

   Ad esempio, per disabilitare gli ID di social networking:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $false
   ```

   Per abilitare gli ID di social networking:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $true
   ```

## <a name="manage-the-use-of-one-time-pass-codes-for-the-office-365-message-encryption-portal"></a>Gestire l'utilizzo di codici pass monouso per il portale di crittografia dei messaggi di Office 365

Se il destinatario di un messaggio crittografato da OME non utilizza Outlook, indipendentemente dall'account utilizzato dal destinatario, il destinatario riceverà un collegamento di visualizzazione Web con tempo limitato che consente di leggere il messaggio. Questo collegamento include un codice Pass One-Time. In qualità di amministratore, è possibile decidere se i destinatari possono utilizzare codici di passaggio una tantum per accedere al portale OME.
  
### <a name="to-manage-whether-ome-generates-one-time-pass-codes"></a>Per gestire se la OME genera codici di Pass One-Time
  
1. Utilizzare un account aziendale o dell'Istituto di istruzione che disponga delle autorizzazioni di amministratore globale nell'organizzazione di Office 365 e avviare una sessione di Windows PowerShell e connettersi a Exchange Online. Per istruzioni, vedere [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Eseguire il cmdlet Set-OMEConfiguration con il parametro OTPEnabled:

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter "> -OTPEnabled <$true|$false>
   ```

   Ad esempio, per disabilitare i codici pass monouso:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $false
   ```

   Per abilitare i codici di passaggio una tantum:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $true
   ```

## <a name="manage-the-display-of-the-encrypt-button-in-outlook-on-the-web"></a>Gestire la visualizzazione del pulsante di crittografia in Outlook sul Web

In qualità di amministratore, è possibile decidere se visualizzare questo pulsante per gli utenti finali.
  
### <a name="to-manage-whether-the-encrypt-button-appears-in-outlook-on-the-web"></a>Per gestire se il pulsante Crittografa viene visualizzato in Outlook sul Web
  
1. Utilizzare un account aziendale o dell'Istituto di istruzione che disponga delle autorizzazioni di amministratore globale nell'organizzazione di Office 365 e avviare una sessione di Windows PowerShell e connettersi a Exchange Online. Per istruzioni, vedere [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Eseguire il cmdlet Set-IRMConfiguration con il parametro-SimplifiedClientAccessEnabled:

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled <$true|$false>
   ```

   Ad esempio, per disabilitare il pulsante di **crittografia** :

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

   Per abilitare il pulsante di **crittografia** :

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $true
   ```

## <a name="enable-service-side-decryption-of-email-messages-for-ios-mail-app-users"></a>Abilitare la decrittografia sul posto del servizio dei messaggi di posta elettronica per gli utenti delle app di posta elettronica iOS

L'app di posta iOS non può decrittografare i messaggi protetti con la crittografia dei messaggi di Office 365. In qualità di amministratore di Office 365, è possibile applicare la decrittografia sul posto di servizio per i messaggi recapitati all'app di posta elettronica iOS. Quando si sceglie di utilizzare la decrittografia sul posto del servizio, il servizio invia una copia decrittografata del messaggio al dispositivo iOS. Il dispositivo client archivia una copia decrittografata del messaggio. Il messaggio conserva anche informazioni sui diritti di utilizzo anche se l'app di posta iOS non applica i diritti di utilizzo sul fianco del client all'utente. L'utente può copiare o stampare il messaggio anche se in origine non dispone dei diritti necessari. Tuttavia, se l'utente tenta di eseguire un'azione che richiede il server di posta di Office 365, ad esempio l'inoltro del messaggio, il server non consentirà l'azione se l'utente non ha originariamente il diritto di utilizzo. Tuttavia, gli utenti finali possono aggirare la restrizione di utilizzo "non inoltrare" inoltrando il messaggio da un account diverso all'interno dell'app di posta iOS. Indipendentemente dal fatto che sia stata configurata la decrittografia sul posto del servizio, gli allegati ai messaggi crittografati e i diritti protetti non possano essere visualizzati nell'app mail iOS.
  
Se si sceglie di non consentire l'invio di messaggi decrittografati agli utenti delle app di posta elettronica iOS, gli utenti riceveranno un messaggio che indica che non dispongono dei diritti per visualizzare il messaggio. Per impostazione predefinita, la decrittografia sul posto di servizio dei messaggi di posta elettronica non è abilitata.
  
Per ulteriori informazioni e per una panoramica dell'esperienza client, vedere [visualizzare i messaggi crittografati sul vostro iPhone o iPad](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf).
  
### <a name="to-manage-whether-ios-mail-app-users-can-view-messages-protected-by-office-365-message-encryption"></a>Per gestire se gli utenti delle app di posta elettronica iOS possono visualizzare i messaggi protetti dalla crittografia dei messaggi di Office 365
  
1. Utilizzare un account aziendale o dell'Istituto di istruzione che disponga delle autorizzazioni di amministratore globale nell'organizzazione di Office 365 e avviare una sessione di Windows PowerShell e connettersi a Exchange Online. Per istruzioni, vedere [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Eseguire il cmdlet Set-ActiveSyncOrganizations con il parametro AllowRMSSupportForUnenlightenedApps:

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps <$true|$false>
   ```

   Ad esempio, per configurare il servizio per decrittografare i messaggi prima che vengano inviati a app non illuminate come app mail iOS:

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $true
   ```

   In alternativa, per configurare il servizio per non inviare messaggi decrittografati a app non illuminate:

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $false
   ```

> [!NOTE]
> I singoli criteri cassetta postale (OWA/ActiveSync) sovrascrivono queste impostazioni (ad esempio, se-IRMEnabled è impostato su false all'interno del rispettivo criterio cassetta postale OWA oppure in un criterio cassetta postale di ActiveSync, queste configurazioni non sarebbero valide).

## <a name="enable-service-side-decryption-of-email-attachments-for-web-browser-mail-clients"></a>Abilitare la decrittografia sul fianco del servizio degli allegati di posta elettronica per i client di posta del browser Web

In genere, quando si utilizza la crittografia dei messaggi di Office 365, gli allegati vengono crittografati automaticamente. Come amministratore di Office 365, è possibile applicare la decrittografia sul posto di servizio per gli allegati di posta elettronica che gli utenti scaricano da un Web browser.
  
Quando si utilizza la decrittografia sul posto del servizio, il servizio invia una copia decrittografata del file al dispositivo. Il messaggio è ancora crittografato. L'allegato di posta elettronica conserva anche informazioni sui diritti di utilizzo anche se il browser non applica i diritti di utilizzo sul fianco del client all'utente. L'utente può copiare o stampare l'allegato di posta elettronica anche se in origine non dispone dei diritti necessari. Tuttavia, se l'utente tenta di eseguire un'azione che richiede il server di posta di Office 365, ad esempio l'inoltro dell'allegato, il server non consentirà l'azione se l'utente non ha originariamente il diritto di utilizzo.
  
Indipendentemente dal fatto che sia stata configurata la decrittografia sul posto del servizio degli allegati, gli utenti non possono visualizzare gli allegati ai messaggi crittografati e protetti per la posta nell'app di posta elettronica iOS.
  
Se si sceglie di non consentire gli allegati di posta elettronica decrittografati, ovvero l'impostazione predefinita, gli utenti riceveranno un messaggio che indica che non dispongono dei diritti per visualizzare l'allegato.
  
Per ulteriori informazioni sul modo in cui Office 365 implementa la crittografia per i messaggi di posta elettronica e gli allegati con l'opzione solo crittografia, vedere l' [opzione crittografia solo per i messaggi di posta elettronica.](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)
  
### <a name="to-manage-whether-email-attachments-are-decrypted-on-download-from-a-web-browser"></a>Per gestire se gli allegati di posta elettronica vengono decrittografati per il download da un Web browser
  
1. Utilizzare un account aziendale o dell'Istituto di istruzione che disponga delle autorizzazioni di amministratore globale nell'organizzazione di Office 365 e avviare una sessione di Windows PowerShell e connettersi a Exchange Online. Per istruzioni, vedere [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Eseguire il cmdlet Set-IRMConfiguration con il parametro DecryptAttachmentFromPortal:

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentFromPortal <$true|$false>
   ```

   Ad esempio, per configurare il servizio per decrittografare gli allegati di posta elettronica quando un utente li scarica da un Web browser:

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentFromPortal $true
   ```

   Per configurare il servizio per lasciare gli allegati di posta elettronica crittografati al momento del download:

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentFromPortal $false
   ```

## <a name="ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail--office-365-advanced-message-encryption-only"></a>Assicurarsi che tutti i destinatari esterni utilizzino il portale OME per leggere la posta crittografata, solo la crittografia dei messaggi avanzata di Office 365

Se si dispone della crittografia dei messaggi avanzata di Office 365, è possibile utilizzare modelli di personalizzazione personalizzati per imporre ai destinatari la ricezione di un messaggio di posta elettronica wrapper per la lettura di messaggi crittografati nel portale OME anziché l'utilizzo di Outlook o Outlook sul Web. Potrebbe essere necessario eseguire questa operazione se si desidera utilizzare un maggiore controllo su come i destinatari utilizzano la posta ricevuta. Ad esempio, se i destinatari esterni visualizzano la posta elettronica nel portale Web, è possibile impostare una data di scadenza per il messaggio di posta elettronica ed è possibile revocare il messaggio di posta elettronica. Queste funzionalità sono supportate solo tramite il portale OME. Per creare le regole del flusso di posta, è possibile utilizzare l'opzione Crittografa e l'opzione non inoltrare.

### <a name="create-a-custom-template-to-force-all-external-recipients-to-use-the-ome-portal-and-for-encrypted-email-to-be-revocable-and-expire-in-7-days"></a>Creare un modello personalizzato per imporre a tutti i destinatari esterni di utilizzare il portale OME e per la posta elettronica crittografata come revocabile e scadere in 7 giorni

1. Utilizzare un account aziendale o dell'Istituto di istruzione che disponga delle autorizzazioni di amministratore globale nell'organizzazione di Office 365 e avviare una sessione di Windows PowerShell e connettersi a Exchange Online. Per istruzioni, vedere [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Eseguire il cmdlet New-OMEConfiguration:

   ```powershell
   New-OMEConfiguration -Identity "<template name>" -ExternalMailExpiryInDays 7
   ```

   dove `template name` è il nome che si desidera utilizzare per il modello di branding personalizzato per la crittografia dei messaggi di Office 365. For example,

   ```powershell
   New-OMEConfiguration -Identity "<One week expiration>" -ExternalMailExpiryInDays 7
   ```

3. Eseguire il cmdlet New-TransportRule:

   ```powershell
   New-TransportRule -name "<mail flow rule name>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "<option name>" -ApplyRightsProtectionCustomizationTemplate "<template name>"
   ```

    dove:

   - `mail flow rule name`è il nome che si desidera utilizzare per la nuova regola del flusso di posta.

   - `option name`è `Encrypt` o `Do Not Forward`.

   - `template name`è il nome assegnato al modello personalizzato per la personalizzazione, ad esempio `One week expiration`.

   Per crittografare tutti i messaggi di posta elettronica esterni con il modello "scadenza una settimana" e applicare l'opzione solo crittografia:

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Encrypt" -ApplyRightsProtectionCustomizationTemplate "<One week expiration>"
   ```

   Per crittografare tutti i messaggi di posta elettronica esterni con il modello "scadenza una settimana" e applicare l'opzione non inoltrare:

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Do Not Forward" -ApplyRightsProtectionCustomizationTemplate "<One week expiration>"
   ```

## <a name="customize-the-appearance-of-email-messages-and-the-ome-portal"></a>Personalizzare l'aspetto dei messaggi di posta elettronica e del portale OME

Per informazioni dettagliate su come personalizzare OME per la propria organizzazione, vedere [aggiungere il marchio dell'organizzazione ai messaggi crittografati](add-your-organization-brand-to-encrypted-messages.md).
  
## <a name="disable-the-new-capabilities-for-ome"></a>Disabilitare le nuove funzionalità di OME

Si spera che non venga ad esso, ma se necessario, la disabilitazione delle nuove funzionalità per OME è molto semplice. Per prima cosa, è necessario rimuovere le regole del flusso di posta create che utilizzano le nuove funzionalità OME. Per informazioni sulla rimozione delle regole del flusso di posta, vedere [Manage Mail Flow Rules](https://technet.microsoft.com/library/jj657505%28v=exchg.150%29.aspx). Eseguire quindi i passaggi seguenti in PowerShell di Exchange Online.
  
### <a name="to-disable-the-new-capabilities-for-ome"></a>Per disabilitare le nuove funzionalità di OME
  
1. Utilizzo di un account aziendale o dell'Istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione di Office 365, avviare una sessione di Windows PowerShell e connettersi a Exchange Online. Per istruzioni, vedere [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Se è stato abilitato il pulsante di **crittografia** in Outlook sul Web, disabilitarlo eseguendo il cmdlet Set-IRMConfiguration con il parametro SimplifiedClientAccessEnabled. In caso contrario, ignorare questo passaggio.

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

3. Disabilitare le nuove funzionalità di OME eseguendo il cmdlet Set-IRMConfiguration con il parametro AzureRMSLicensingEnabled impostato su false:

   ```powershell
   Set-IRMConfiguration -AzureRMSLicensingEnabled $false
   ```
