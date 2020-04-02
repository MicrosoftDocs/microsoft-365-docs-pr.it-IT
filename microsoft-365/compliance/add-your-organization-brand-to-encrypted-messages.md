---
title: Aggiungere il marchio dell'organizzazione ai messaggi crittografati
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 4/1/2020
search.appverid:
- MET150
- MOE150
ms.assetid: 7a29260d-2959-42aa-8916-feceff6ee51d
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: In qualità di amministratore globale di Office 365, è possibile applicare il marchio dell'organizzazione ai messaggi di posta elettronica crittografati dell'organizzazione e ai contenuti del portale di crittografia.
ms.openlocfilehash: 5a3f5426fecd6ce5df6ace5b0080de33fb50e21f
ms.sourcegitcommit: e695bcfc69203da5d3d96f3d6a891664a0e27ae2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "43106018"
---
# <a name="add-your-organizations-brand-to-your-encrypted-messages"></a>Aggiungere il logo della propria organizzazione ai messaggi crittografati

In qualità di amministratore di Exchange Online o Exchange Online Protection, è possibile applicare il marchio dell'azienda per personalizzare l'aspetto dei messaggi di posta elettronica di crittografia messaggi di Office 365 dell'organizzazione e il contenuto del portale di crittografia. Utilizzando i cmdlet Get-OMEConfiguration e set-OMEConfiguration di Windows PowerShell, è possibile personalizzare i seguenti aspetti dell'esperienza di visualizzazione per i destinatari dei messaggi di posta elettronica crittografati:
  
- Testo introduttivo del messaggio di posta elettronica contenente il messaggio crittografato

- Testo della dichiarazione di non responsabilità del messaggio di posta elettronica contenente il messaggio crittografato

- URL dell'informativa sulla privacy per l'organizzazione

- Testo visualizzato nel portale OME

- Logo visualizzato nel messaggio di posta elettronica e nel portale OME o se utilizzare un logo

- Colore di sfondo nel messaggio di posta elettronica e nel portale OME

È anche possibile ripristinare l'aspetto predefinito in qualsiasi momento.

Se si desidera un maggiore controllo, è possibile utilizzare la crittografia avanzata dei messaggi di Office 365 e creare più modelli per i messaggi di posta elettronica crittografati provenienti dall'organizzazione. Utilizzando questi modelli, è possibile controllare più solo l'aspetto dei messaggi di posta elettronica, ma anche controllare le parti dell'esperienza dell'utente finale. Ad esempio, è possibile specificare se i destinatari di posta elettronica a cui è applicato il modello e che utilizzano Google, Yahoo e gli account Microsoft possono utilizzare questi account per accedere al portale di crittografia dei messaggi di Office 365. È possibile utilizzare i modelli per soddisfare diversi casi di utilizzo, ad esempio:

- Modelli per ogni reparto, ad esempio Finance, Sales e così via.

- Modelli per prodotti diversi

- Modelli per aree geografiche o paesi diversi

- Se si desidera consentire la revoca di messaggi di posta elettronica

- Se si desidera che i messaggi di posta elettronica inviati a destinatari esterni scadano dopo un determinato numero di giorni.

Dopo aver creato i modelli, è possibile applicarli ai messaggi di posta elettronica crittografati utilizzando le regole del flusso di messaggi di Exchange. Se si dispone della crittografia avanzata dei messaggi di Office 365, è possibile revocare tutti i messaggi di posta elettronica che sono stati creati utilizzando questi modelli.

## <a name="work-with-ome-branding-templates"></a>Utilizzo dei modelli di personalizzazione OME

È possibile modificare diverse funzionalità all'interno di un modello di branding. È possibile modificare, ma non rimuovere, il modello predefinito. Se si dispone di una crittografia avanzata dei messaggi, è anche possibile creare, modificare e rimuovere modelli personalizzati. Utilizzare Windows PowerShell per l'utilizzo di un modello di personalizzazione alla volta. Per utilizzare questi cmdlet, è necessario disporre di un account aziendale o dell'Istituto di istruzione che disponga delle autorizzazioni di amministratore globale nell'organizzazione di Office 365.

- [Set-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/set-omeconfiguration) : consente di modificare il modello di personalizzazione predefinito o un modello personalizzato di personalizzazione creato.
- [New-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/new-omeconfiguration) -creare un nuovo modello di branding, solo crittografia avanzata dei messaggi.
- [Remove-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/remove-omeconfiguration) -rimuove un modello di personalizzazione personalizzato, solo la crittografia avanzata dei messaggi. Non è possibile eliminare il modello di personalizzazione predefinito.
  
## <a name="modify-an-ome-branding-template"></a>Modificare un modello di branding OME

Utilizzare Windows PowerShell per modificare un modello di branding alla volta. Se si dispone di una crittografia avanzata dei messaggi, è anche possibile creare, modificare e rimuovere modelli personalizzati.

1. Utilizzo di un account aziendale o dell'Istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione di Office 365, avviare una sessione di Windows PowerShell e connettersi a Exchange Online. Per istruzioni, vedere [Connettersi a PowerShell di Exchange Online](https://aka.ms/exopowershell).

2. Modificare il modello utilizzando il cmdlet Set-OMEConfiguration come descritto in [set-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/Set-OMEConfiguration) oppure utilizzare la seguente tabella grafica e per indicazioni.

![Parti di posta elettronica personalizzabili](../media/ome-template-breakout.png)

|**Per personalizzare questa funzionalità dell'esperienza di crittografia**|**Utilizzare questi comandi**|
|:-----|:-----|
|Colore di sfondo|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -BackgroundColor "<Hexadecimal color code>"` <br/> **Esempio:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -BackgroundColor "#ffffff"`|
|Logo|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <Byte[]>` <br/> **Esempio:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> Formati di file supportati: png, jpg, bmp o tiff  <br/> Dimensione ottimale relativa al file del logo: inferiore a 40 KB  <br/> Dimensioni ottimali dell'immagine del logo: 170x70 pixel. Se l'immagine supera queste dimensioni, il logo viene ridimensionato per essere visualizzato nel portale. Il servizio non modifica il file grafico stesso. Per ottenere risultati ottimali, utilizzare le dimensioni ottimali.|
|Testo accanto al nome e all'indirizzo di posta elettronica del mittente|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -IntroductionText "<String up to 1024 characters>"` <br/> **Esempio:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -IntroductionText "has sent you a secure message."`|
|Testo visualizzato sul pulsante "Leggi messaggio"|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -ReadButtonText "<String up to 1024 characters>"` <br/> **Esempio:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -ReadButtonText "Read Secure Message."`|
|Testo visualizzato sotto il pulsante "Leggi messaggio"|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<String up to 1024 characters>"` <br/> **Esempio:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system."`|
|URL del collegamento all'informativa sulla privacy|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PrivacyStatementURL "<URL>"` <br/> **Esempio:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -PrivacyStatementURL "https://contoso.com/privacystatement.html"`|
|dichiarazione di non responsabilità nella posta elettronica che contiene il messaggio crittografato|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -DisclaimerText "<Disclaimer statement. String of up to 1024 characters.>"` <br/> **Esempio:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -DisclaimerText "This message is confidential for the use of the addressee only."`|
|testo visualizzato nella parte superiore del portale di visualizzazione del messaggio crittografato|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<Text for your portal. String of up to 128 characters.>"` <br/> **Esempio:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal."`|
|Per abilitare o disabilitare l'autenticazione con un codice Pass una tantum per questo modello personalizzato|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -OTPEnabled <$true|$false>` <br/> **Esempi:** <br/>Per abilitare i codici di accesso una tantum per questo modello personalizzato <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $true` <br/> Per disabilitare i codici di accesso una tantum per questo modello personalizzato <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $false`|
|Per abilitare o disabilitare l'autenticazione con identità Microsoft, Google o Yahoo per questo modello personalizzato|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -SocialIdSignIn <$true|$false>` <br/> **Esempi:** <br/>Per abilitare gli ID di social networking per questo modello personalizzato <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $true` <br/> Per disabilitare gli ID di social networking per questo modello personalizzato <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $false`|

## <a name="create-an-ome-branding-template-advanced-message-encryption"></a>Creare un modello di branding OME (Advanced Message Encryption)

Se si dispone della crittografia dei messaggi avanzata di Office 365, è possibile creare modelli di personalizzazione personalizzati per l'organizzazione utilizzando il cmdlet [New-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/new-omeconfiguration) . Dopo aver creato il modello, è possibile modificare il modello utilizzando il cmdlet Set-OMEConfiguration, come descritto in [Modify an ome branding template](#modify-an-ome-branding-template). È possibile creare più modelli.

Per creare un nuovo modello di personalizzazione personalizzato:

1. Utilizzo di un account aziendale o dell'Istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione di Office 365, avviare una sessione di Windows PowerShell e connettersi a Exchange Online. Per istruzioni, vedere [Connettersi a PowerShell di Exchange Online](https://aka.ms/exopowershell).

2. Utilizzare il cmdlet [New-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/new-omeconfiguration) per creare un nuovo modello.

   ```powershell
   New-OMEConfiguration -Identity <OMEConfigurationIdParameter>
   ```

   For example,

   ```powershell
   New-OMEConfiguration -Identity "Custom branding template"
   ```

## <a name="return-the-default-branding-template-to-its-original-values"></a>Ripristinare i valori originali del modello di personalizzazione predefinito

Per rimuovere tutte le modifiche dal modello predefinito, incluse le personalizzazioni del marchio e così via, eseguire la procedura seguente:
  
1. Utilizzo di un account aziendale o dell'Istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione di Office 365, avviare una sessione di Windows PowerShell e connettersi a Exchange Online. Per istruzioni, vedere [Connettersi a PowerShell di Exchange Online](https://aka.ms/exopowershell).

2. Utilizzare il cmdlet **set-OMEConfiguration** come descritto in [set-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/Set-OMEConfiguration). Per rimuovere le personalizzazioni personalizzate dell'organizzazione dai valori DisclaimerText, EmailText e PortalText, impostare il valore su una stringa vuota `""`. Per tutti i valori di immagine, ad esempio logo, impostare il `"$null"`valore su.

   Nella tabella seguente vengono descritte le impostazioni predefinite dell'opzione di personalizzazione della crittografia.

   **Per ripristinare il testo e l'immagine predefiniti per questa funzionalità dell'esperienza di crittografia**|**Utilizzare questi comandi**|
   |:-----|:-----|
   |Testo predefinito che accompagna i messaggi di posta elettronica crittografati  <br/> Il testo predefinito viene visualizzato sopra le istruzioni per la visualizzazione di messaggi crittografati|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<empty string>"` <br/> **Esempio:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""`|
   |dichiarazione di non responsabilità nella posta elettronica che contiene il messaggio crittografato|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<empty string>"` <br/> **Esempio:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""`|
   |testo visualizzato nella parte superiore del portale di visualizzazione del messaggio crittografato|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<empty string>"` <br/> **Esempio ripristinando il valore predefinito:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""`|
   |Logo|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <"$null">` <br/> **Esempio ripristinando il valore predefinito:** <br/>  `Set-OMEConfiguration -Identity "OME configuration" -Image $null`|
   |Colore di sfondo|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -BackgroundColor <"$null">` <br/> **Esempio ripristinando il valore predefinito:** <br/> `Set-OMEConfiguration -Identity "OME configuration" -BackgroundColor $null`|
   |

## <a name="remove-a-custom-branding-template-advanced-message-encryption"></a>Rimuovere un modello di personalizzazione personalizzato (Advanced Message Encryption)

È possibile rimuovere o eliminare solo i modelli di personalizzazione che sono stati apportati. Non è possibile rimuovere il modello di personalizzazione predefinito.

Per rimuovere un modello di personalizzazione personalizzato:
  
1. Utilizzo di un account aziendale o dell'Istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione di Office 365, avviare una sessione di Windows PowerShell e connettersi a Exchange Online. Per istruzioni, vedere [Connettersi a PowerShell di Exchange Online](https://aka.ms/exopowershell).

2. Utilizzare il cmdlet **Remove-OMEConfiguration** come indicato di seguito:

   ```powershell
   Remove-OMEConfiguration -Identity "<OMEConfigurationIdParameter>
   ```

   For example,

   ```powershell
   Remove-OMEConfiguration -Identity "Branding template 1"
   ```

   Per ulteriori informazioni, vedere [Remove-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/remove-omeconfiguration).

## <a name="create-an-exchange-mail-flow-rule-that-applies-your-custom-branding-to-encrypted-emails"></a>Creare una regola del flusso di posta di Exchange che applica il branding personalizzato ai messaggi di posta elettronica crittografati

Dopo aver modificato il modello predefinito o creato nuovi modelli di branding, è possibile creare le regole del flusso di posta di Exchange per applicare il marchio personalizzato in base a determinate condizioni. Una regola di questo tipo applicherà il marchio personalizzato negli scenari seguenti:

- Se il messaggio di posta elettronica è stato crittografato manualmente dall'utente finale dal client Outlook o Outlook sul Web (in precedenza noto come Outlook Web App)

- Se il messaggio di posta elettronica è stato crittografato automaticamente da una regola del flusso di posta di Exchange 365 o da un criterio di prevenzione della perdita

Per informazioni su come creare una regola del flusso di posta di Exchange che applica la crittografia, vedere [definire le regole del flusso di posta per crittografare i messaggi di posta elettronica in Office 365](define-mail-flow-rules-to-encrypt-email.md).

1. In un Web browser, utilizzando un account aziendale o dell'Istituto di istruzione a cui sono state concesse le autorizzazioni di amministratore globale, [accedere a Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).

2. Scegliere il riquadro **amministratore** .

3. Nell'interfaccia di amministrazione di Microsoft 365 fare clic su interfaccia di **Amministrazione** \> di **Exchange**.

4. Nell'interfaccia di amministrazione di Exchange, andare a **regole** del **flusso** \> di posta e selezionare **nuova** ![nuova icona](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **creare una nuova regola**. Per ulteriori informazioni sull'utilizzo di EAC, vedere interfaccia [di amministrazione di Exchange in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).

5. In **nome**Digitare un nome per la regola, ad esempio branding per il reparto vendite.

6. In **applica questa regola se**, selezionare la condizione in cui **il mittente si trova all'interno dell'organizzazione** e altre condizioni desiderate nell'elenco delle condizioni disponibili. Ad esempio, potrebbe essere necessario applicare un modello di branding specifico a:

   - Tutti i messaggi di posta elettronica crittografati inviati dai membri del reparto Finanze
   - Messaggi di posta elettronica crittografati inviati con una determinata parola chiave, ad esempio "esterno" o "partner"
   - Messaggi di posta elettronica crittografati inviati a un dominio specifico

7. Da **procedere come segue**, selezionare **modifica la sicurezza** > dei messaggi**applicare il marchio personalizzato ai messaggi ome**. Successivamente, dal menu a discesa, selezionare un modello di branding tra quelli creati o modificati.

8. Optional Se si desidera che la regola del flusso di posta applichi la crittografia oltre al marchio personalizzato, **fare**clic su **modifica la sicurezza dei messaggi**e quindi scegliere **Apply Office 365 Message Encryption and Rights Protection**. Selezionare un modello RMS nell'elenco, scegliere **Salva**e quindi fare clic su **OK**.
  
   L'elenco dei modelli include tutti i modelli e le opzioni predefiniti, nonché tutti i modelli personalizzati creati per l'utilizzo da parte di Office 365. Se l'elenco è vuoto, verificare di aver configurato la crittografia dei messaggi di Office 365 con le nuove funzionalità descritte in [configurare le nuove funzionalità di crittografia dei messaggi di office 365](set-up-new-message-encryption-capabilities.md). Per informazioni sui modelli predefiniti, vedere [Configuring and Managing templates for Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates). Per informazioni sull'opzione non **inoltrare** , vedere non [inoltrare l'opzione per i messaggi di posta elettronica](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails). Per informazioni sull'opzione **solo crittografia** , vedere [opzione di crittografia solo per i messaggi di posta elettronica](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).

   Fare clic su **Aggiungi azione** se si desidera specificare un'altra azione.
