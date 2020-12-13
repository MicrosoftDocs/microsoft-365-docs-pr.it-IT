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
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: Informazioni su come gli amministratori globali di Office 365 possono applicare il marchio dell'organizzazione ai messaggi di posta elettronica crittografati & contenuto del portale di crittografia.
ms.openlocfilehash: 77fd5e08afa1a4d8ae5f6386fa65b88b6ea2be4d
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663233"
---
# <a name="add-your-organizations-brand-to-your-microsoft-365-for-business-message-encryption-encrypted-messages"></a>Aggiungere il marchio dell'organizzazione ai messaggi crittografati per la crittografia dei messaggi di Microsoft 365 per le aziende

È possibile applicare il marchio dell'azienda per personalizzare l'aspetto dei messaggi di posta elettronica dell'organizzazione e del portale di crittografia. Prima di iniziare, è necessario applicare le autorizzazioni di amministratore globale all'account aziendale o dell'Istituto di istruzione. Quando si dispone di queste autorizzazioni, utilizzare i cmdlet Get-OMEConfiguration e Set-OMEConfiguration Windows PowerShell per personalizzare queste parti dei messaggi di posta elettronica crittografati:
  
- Testo introduttivo

- Disclaimer text

- URL per l'informativa sulla privacy dell'organizzazione

- Testo nel portale OME

- Logo visualizzato nel messaggio di posta elettronica e nel portale OME o se utilizzare un logo

- Colore di sfondo nel messaggio di posta elettronica e nel portale OME

È anche possibile ripristinare l'aspetto predefinito in qualsiasi momento.

Se si desidera un maggiore controllo, utilizzare la crittografia avanzata dei messaggi di Office 365 per creare più modelli per i messaggi di posta elettronica crittografati provenienti dall'organizzazione. Utilizzare questi modelli per controllare le parti dell'esperienza dell'utente finale. Ad esempio, specificare se i destinatari possono utilizzare gli account Google, Yahoo e Microsoft per accedere al portale di crittografia. Utilizzare i modelli per soddisfare diversi casi di utilizzo, ad esempio:

- Singoli reparti, ad esempio finanza, vendite e così via.

- Prodotti diversi

- Diverse aree geografiche o paesi

- Se si desidera consentire la revoca di messaggi di posta elettronica

- Se si desidera che i messaggi di posta elettronica inviati a destinatari esterni scadano dopo un determinato numero di giorni.

Dopo aver creato i modelli, è possibile applicarli ai messaggi di posta elettronica crittografati utilizzando le regole del flusso di messaggi di Exchange. Se si dispone della crittografia avanzata dei messaggi di Office 365, è possibile revocare tutti i messaggi di posta elettronica che sono stati creati utilizzando questi modelli.

## <a name="work-with-ome-branding-templates"></a>Utilizzo dei modelli di personalizzazione OME

È possibile modificare diverse funzionalità all'interno di un modello di branding. È possibile modificare, ma non rimuovere, il modello predefinito. Se si dispone di una crittografia avanzata dei messaggi, è anche possibile creare, modificare e rimuovere modelli personalizzati. Utilizzare Windows PowerShell per l'utilizzo di un modello di personalizzazione alla volta.

- [Set-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-omeconfiguration) : consente di modificare il modello di personalizzazione predefinito o un modello personalizzato di personalizzazione creato.
- [New-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/new-omeconfiguration) -creare un nuovo modello di branding, solo crittografia avanzata dei messaggi.
- [Remove-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/remove-omeconfiguration) -rimuove un modello di personalizzazione personalizzato, solo la crittografia avanzata dei messaggi. Non è possibile eliminare il modello di personalizzazione predefinito.
  
## <a name="modify-an-ome-branding-template"></a>Modificare un modello di branding OME

Utilizzare Windows PowerShell per modificare un modello di branding alla volta. Se si dispone di una crittografia avanzata dei messaggi, è anche possibile creare, modificare e rimuovere modelli personalizzati.

1. Utilizzo di un account aziendale o dell'Istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione, avviare una sessione di Windows PowerShell e connettersi a Exchange Online. Per istruzioni, vedere [Connettersi a PowerShell di Exchange Online](https://aka.ms/exopowershell).

2. Utilizzare il cmdlet Set-OMEConfiguration come descritto in [set-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/Set-OMEConfiguration) oppure utilizzare la seguente tabella grafica e le relative istruzioni.

![Parti di posta elettronica personalizzabili](../media/ome-template-breakout.png)

|**Per personalizzare questa funzionalità dell'esperienza di crittografia**|**Utilizzare questi comandi**|
|:-----|:-----|
|Colore di sfondo|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -BackgroundColor "<#RRGGBB hexadecimal color code or name value>"` <br/> **Esempio:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -BackgroundColor "#ffffff"` <br/> Per ulteriori informazioni sui colori di sfondo, vedere la sezione [colori di sfondo](#background-color-reference) più avanti in questo articolo.|
|Logo|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -Image <Byte[]>` <br/> **Esempio:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> Formati di file supportati: png, jpg, bmp o tiff  <br/> Dimensione ottimale relativa al file del logo: inferiore a 40 KB  <br/> Dimensioni ottimali dell'immagine del logo: 170x70 pixel. Se l'immagine supera queste dimensioni, il logo viene ridimensionato per essere visualizzato nel portale. Il servizio non modifica il file grafico stesso. Per ottenere risultati ottimali, utilizzare le dimensioni ottimali.|
|Testo accanto al nome e all'indirizzo di posta elettronica del mittente|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -IntroductionText "<String up to 1024 characters>"` <br/> **Esempio:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -IntroductionText "has sent you a secure message."`|
|Testo visualizzato sul pulsante "Leggi messaggio"|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -ReadButtonText "<String up to 1024 characters>"` <br/> **Esempio:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -ReadButtonText "Read Secure Message."`|
|Testo visualizzato sotto il pulsante "Leggi messaggio"|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -EmailText "<String up to 1024 characters>"` <br/> **Esempio:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system."`|
|URL del collegamento all'informativa sulla privacy|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PrivacyStatementURL "<URL>"` <br/> **Esempio:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -PrivacyStatementURL "https://contoso.com/privacystatement.html"`|
|dichiarazione di non responsabilità nella posta elettronica che contiene il messaggio crittografato|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -DisclaimerText "<Disclaimer statement. String of up to 1024 characters.>"` <br/> **Esempio:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -DisclaimerText "This message is confidential for the use of the addressee only."`|
|testo visualizzato nella parte superiore del portale di visualizzazione del messaggio crittografato|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PortalText "<Text for your portal. String of up to 128 characters.>"` <br/> **Esempio:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal."`|
|Per abilitare o disabilitare l'autenticazione con un codice Pass una tantum per questo modello personalizzato|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -OTPEnabled <$true|$false>` <br/> **Esempi:** <br/>Per abilitare i codici di accesso una tantum per questo modello personalizzato <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $true` <br/> Per disabilitare i codici di accesso una tantum per questo modello personalizzato <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $false`|
|Per abilitare o disabilitare l'autenticazione con identità Microsoft, Google o Yahoo per questo modello personalizzato|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -SocialIdSignIn <$true|$false>` <br/> **Esempi:** <br/>Per abilitare gli ID di social networking per questo modello personalizzato <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $true` <br/> Per disabilitare gli ID di social networking per questo modello personalizzato <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $false`|

## <a name="create-an-ome-branding-template-advanced-message-encryption"></a>Creare un modello di branding OME (Advanced Message Encryption)

Se si dispone della crittografia dei messaggi avanzata di Office 365, è possibile creare modelli di personalizzazione personalizzati per l'organizzazione utilizzando il cmdlet [New-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/new-omeconfiguration) . Dopo aver creato il modello, è possibile modificare il modello utilizzando il cmdlet Set-OMEConfiguration come descritto in [Modify an ome branding template](#modify-an-ome-branding-template). È possibile creare più modelli.

Per creare un nuovo modello di personalizzazione personalizzato:

1. Utilizzo di un account aziendale o dell'Istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione, avviare una sessione di Windows PowerShell e connettersi a Exchange Online. Per istruzioni, vedere [Connettersi a PowerShell di Exchange Online](https://aka.ms/exopowershell).

2. Utilizzare il cmdlet [New-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/new-omeconfiguration) per creare un nuovo modello.

   ```powershell
   New-OMEConfiguration -Identity "<OMEConfigurationName>"
   ```

   Ad esempio,

   ```powershell
   New-OMEConfiguration -Identity "Custom branding template"
   ```

## <a name="return-the-default-branding-template-to-its-original-values"></a>Ripristinare i valori originali del modello di personalizzazione predefinito

Per rimuovere tutte le modifiche dal modello predefinito, incluse le personalizzazioni del marchio e così via, eseguire la procedura seguente:
  
1. Utilizzo di un account aziendale o dell'Istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione, avviare una sessione di Windows PowerShell e connettersi a Exchange Online. Per istruzioni, vedere [Connettersi a PowerShell di Exchange Online](https://aka.ms/exopowershell).

2. Utilizzare il cmdlet **set-OMEConfiguration** come descritto in [set-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/Set-OMEConfiguration). Per rimuovere le personalizzazioni personalizzate dell'organizzazione dai valori DisclaimerText, EmailText e PortalText, impostare il valore su una stringa vuota `""` . Per tutti i valori di immagine, ad esempio logo, impostare il valore su  `"$null"` .

   Nella tabella seguente vengono descritte le impostazioni predefinite dell'opzione di personalizzazione della crittografia.

   **Per ripristinare il testo e l'immagine predefiniti per questa funzionalità dell'esperienza di crittografia**|**Utilizzare questi comandi**|
   |:-----|:-----|
   |Testo predefinito fornito con i messaggi di posta elettronica crittografati  <br/> Il testo predefinito viene visualizzato sopra le istruzioni per la visualizzazione di messaggi crittografati|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -EmailText "<empty string>"` <br/> **Esempio:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""`|
   |dichiarazione di non responsabilità nella posta elettronica che contiene il messaggio crittografato|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" DisclaimerText "<empty string>"` <br/> **Esempio:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""`|
   |testo visualizzato nella parte superiore del portale di visualizzazione del messaggio crittografato|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PortalText "<empty string>"` <br/> **Esempio ripristinando il valore predefinito:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""`|
   |Logo|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -Image <"$null">` <br/> **Esempio ripristinando il valore predefinito:** <br/>  `Set-OMEConfiguration -Identity "OME configuration" -Image $null`|
   |Colore di sfondo|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -BackgroundColor "$null">` <br/> **Esempio ripristinando il valore predefinito:** <br/> `Set-OMEConfiguration -Identity "OME configuration" -BackgroundColor $null`|
   |

## <a name="remove-a-custom-branding-template-advanced-message-encryption"></a>Rimuovere un modello di personalizzazione personalizzato (Advanced Message Encryption)

È possibile rimuovere o eliminare solo i modelli di personalizzazione che sono stati apportati. Non è possibile rimuovere il modello di personalizzazione predefinito.

Per rimuovere un modello di personalizzazione personalizzato:
  
1. Utilizzo di un account aziendale o dell'Istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione, avviare una sessione di Windows PowerShell e connettersi a Exchange Online. Per istruzioni, vedere [Connettersi a PowerShell di Exchange Online](https://aka.ms/exopowershell).

2. Utilizzare il cmdlet **Remove-OMEConfiguration** come indicato di seguito:

   ```powershell
   Remove-OMEConfiguration -Identity ""<OMEConfigurationName>"
   ```

   Ad esempio,

   ```powershell
   Remove-OMEConfiguration -Identity "Branding template 1"
   ```

   Per ulteriori informazioni, vedere [Remove-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/remove-omeconfiguration).

## <a name="create-an-exchange-mail-flow-rule-that-applies-your-custom-branding-to-encrypted-emails"></a>Creare una regola del flusso di posta di Exchange che applica il branding personalizzato ai messaggi di posta elettronica crittografati

Dopo aver modificato il modello predefinito o creato nuovi modelli di branding, è possibile creare le regole del flusso di posta di Exchange per applicare il marchio personalizzato in base a determinate condizioni. Una regola di questo tipo applicherà il marchio personalizzato negli scenari seguenti:

- Se il messaggio di posta elettronica è stato crittografato manualmente dall'utente finale utilizzando Outlook o Outlook sul Web, in precedenza Outlook Web App

- Se il messaggio di posta elettronica è stato crittografato automaticamente da una regola del flusso di posta di Exchange o da un criterio di prevenzione

Per informazioni su come creare una regola del flusso di posta di Exchange che applica la crittografia, vedere [definire le regole del flusso di posta per crittografare i messaggi di posta elettronica in Office 365](define-mail-flow-rules-to-encrypt-email.md).

1. In un Web browser, utilizzando un account aziendale o dell'Istituto di istruzione a cui sono state concesse le autorizzazioni di amministratore globale, [accedere a Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).

2. Scegliere il riquadro **amministratore** .

3. Nell'interfaccia di amministrazione di Microsoft 365 fare clic su interfaccia di **Amministrazione** di \> **Exchange**.

4. Nell'interfaccia di amministrazione di Exchange, andare a regole del **flusso di posta** \>  e selezionare **nuova** nuova ![ icona ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **creare una nuova regola**. Per ulteriori informazioni sull'utilizzo di EAC, vedere interfaccia [di amministrazione di Exchange in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).

5. In **nome** Digitare un nome per la regola, ad esempio branding per il reparto vendite.

6. In **applica questa regola se**, selezionare la condizione in cui **il mittente si trova all'interno dell'organizzazione** e altre condizioni desiderate nell'elenco delle condizioni disponibili. Ad esempio, potrebbe essere necessario applicare un modello di branding specifico a:

   - Tutti i messaggi di posta elettronica crittografati inviati dai membri del reparto Finanze
   - Messaggi di posta elettronica crittografati inviati con una determinata parola chiave, ad esempio "esterno" o "partner"
   - Messaggi di posta elettronica crittografati inviati a un dominio specifico

7. Da **procedere come segue**, selezionare **modifica la sicurezza dei** messaggi \> **applicare il marchio personalizzato ai messaggi ome**. Successivamente, dal menu a discesa, selezionare un modello di personalizzazione.

8. Optional È possibile configurare la regola del flusso di posta per applicare la crittografia e il marchio personalizzato. Da **procedere come segue**, selezionare **modifica la sicurezza dei messaggi**, quindi fare clic su **applica la crittografia dei messaggi di Office 365 e Rights Protection**. Selezionare un modello RMS nell'elenco, scegliere **Salva** e quindi fare clic su **OK**.
  
   L'elenco dei modelli include modelli e opzioni predefiniti e tutti i modelli personalizzati creati. Se l'elenco è vuoto, verificare di aver configurato la crittografia dei messaggi di Office 365 con le nuove funzionalità. Per istruzioni, vedere [configurare le nuove funzionalità di crittografia dei messaggi di Office 365](set-up-new-message-encryption-capabilities.md). Per informazioni sui modelli predefiniti, vedere [Configuring and Managing templates for Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates). Per informazioni sull'opzione non **inoltrare** , vedere non [inoltrare l'opzione per i messaggi di posta elettronica](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails). Per informazioni sull'opzione **solo crittografia** , vedere [opzione di crittografia solo per i messaggi di posta elettronica](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).

   Fare clic su **Aggiungi azione** se si desidera specificare un'altra azione.

## <a name="background-color-reference"></a>Riferimento al colore di sfondo

I nomi di colore che è possibile utilizzare per il colore di sfondo sono limitati. Invece del nome di un colore, è possibile utilizzare un valore di codice esadecimale (#RRGGBB). È possibile utilizzare un valore di codice esadecimale corrispondente a un nome di colore oppure è possibile utilizzare un valore di codice esadecimale personalizzato. Tenere presente che il valore del codice esadecimale viene racchiuso tra virgolette (ad esempio, `"#f0f8ff"` ).

Nella tabella seguente sono descritti i nomi dei colori di sfondo disponibili e i valori del codice esadecimale corrispondenti.

|||
|---|---|
|**Nome colore**|**Codice colore**|
|`aliceblue`|#f0f8ff|
|`antiquewhite`|#faebd7|
|`aqua`|#00ffff|
|`aquamarine`|#7fffd4|
|`azure`|#f0ffff|
|`beige`|#f5f5dc|
|`bisque`|#ffe4c4|
|`black`|#000000|
|`blanchedalmond`|#ffebcd|
|`blue`|#0000ff|
|`blueviolet`|#8a2be2|
|`brown`|#a52a2a|
|`burlywood`|#deb887|
|`cadetblue`|#5f9ea0|
|`chartreuse`|#7fff00|
|`chocolate`|#d2691e|
|`coral`|#ff7f50|
|`cornflowerblue`|#6495ed|
|`cornsilk`|#fff8dc|
|`crimson`|#dc143c|
|`cyan`|#00ffff|
|`darkblue`|#00008b|
|`darkcyan`|#008b8b|
|`darkgoldenrod`|#b8860b|
|`darkgray`|#a9a9a9|
|`darkgreen`|#006400|
|`darkkhaki`|#bdb76b|
|`darkmagenta`|#8b008b|
|`darkolivegreen`|#556b2f|
|`darkorange`|#ff8c00|
|`darkorchid`|#9932cc|
|`darkred`|#8b0000|
|`darksalmon`|#e9967a|
|`darkseagreen`|#8fbc8f|
|`darkslateblue`|#483d8b|
|`darkslategray`|#2f4f4f|
|`darkturquoise`|#00ced1|
|`darkviolet`|#9400d3|
|`deeppink`|#ff1493|
|`deepskyblue`|#00bfff|
|`dimgray`|#696969|
|`dodgerblue`|#1e90ff|
|`firebrick`|#b22222|
|`floralwhite`|#fffaf0|
|`forestgreen`|#228b22|
|`fuchsia`|#ff00ff|
|`gainsboro`|#dcdcdc|
|`ghostwhite`|#f8f8ff|
|`gold`|#ffd700|
|`goldenrod`|#daa520|
|`gray`|#808080|
|`green`|#008000|
|`greenyellow`|#adff2f|
|`honeydew`|#f0fff0|
|`hotpink`|#ff69b4|
|`indianred`|#cd5c5c|
|`indigo`|#4b0082|
|`ivory`|#fffff0|
|`khaki`|#f0e68c|
|`lavender`|#e6e6fa|
|`lavenderblush`|#fff0f5|
|`lawngreen`|#7cfc00|
|`lemonchiffon`|#fffacd|
|`lightblue`|#add8e6|
|`lightcoral`|#f08080|
|`lightcyan`|#e0ffff|
|`lightgoldenrodyellow`|#fafad2|
|`lightgray`|#d3d3d3|
|`lightgrey`|#d3d3d3|
|`lightgreen`|#90ee90|
|`lightpink`|#ffb6c1|
|`lightsalmon`|#ffa07a|
|`lightseagreen`|#20b2aa|
|`lightskyblue`|#87cefa|
|`lightslategray`|#778899|
|`lightsteelblue`|#b0c4de|
|`lightyellow`|#ffffe0|
|`lime`|#00ff00|
|`limegreen`|#32cd32|
|`linen`|#faf0e6|
|`magenta`|#ff00ff|
|`maroon`|#800000|
|`mediumaquamarine`|#66cdaa|
|`mediumblue`|#0000cd|
|`mediumorchid`|#ba55d3|
|`mediumpurple`|#9370db|
|`mediumseagreen`|#3cb371|
|`mediumslateblue`|#7b68ee|
|`mediumspringgreen`|#00fa9a|
|`mediumturquoise`|#48d1cc|
|`mediumvioletred`|#c71585|
|`midnightblue`|#191970|
|`mintcream`|#f5fffa|
|`mistyrose`|#ffe4e1|
|`moccasin`|#ffe4b5|
|`navajowhite`|#ffdead|
|`navy`|#000080|
|`oldlace`|#fdf5e6|
|`olive`|#808000|
|`olivedrab`|#6b8e23|
|`orange`|#ffa500|
|`orangered`|#ff4500|
|`orchid`|#da70d6|
|`palegoldenrod`|#eee8aa|
|`palegreen`|#98fb98|
|`paleturquoise`|#afeeee|
|`palevioletred`|#db7093|
|`papayawhip`|#ffefd5|
|`peachpuff`|#ffdab9|
|`peru`|#cd853f|
|`pink`|#ffc0cb|
|`plum`|#dda0dd|
|`powderblue`|#b0e0e6|
|`purple`|#800080|
|`red`|#ff0000|
|`rosybrown`|#bc8f8f|
|`royalblue`|#4169e1|
|`saddlebrown`|#8b4513|
|`salmon`|#fa8072|
|`sandybrown`|#f4a460|
|`seagreen`|#00ff00|
|`seashell`|#fff5ee|
|`sienna`|#a0522d|
|`silver`|#c0c0c0|
|`skyblue`|#87ceeb|
|`slateblue`|#6a5acd|
|`slategray`|#708090|
|`snow`|#fffafa|
|`springgreen`|#00ff7f|
|`steelblue`|#4682b4|
|`tan`|#d2b48c|
|`teal`|#008080|
|`thistle`|#d8bfd8|
|`tomato`|#ff6347|
|`turquoise`|#40e0d0|
|`violet`|#ee82ee|
|`wheat`|#f5deb3|
|`white`|#ffffff|
|`whitesmoke`|#f5f5f5|
|`yellow`|#ffff00|
|`yellowgreen`|#9acd32|
