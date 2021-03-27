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
description: Informazioni su come gli amministratori globali di Office 365 possono applicare la personalizzazione dell'organizzazione ai messaggi di posta elettronica crittografati & contenuto del portale di crittografia.
ms.openlocfilehash: 2898e12ad00d11cd9eb2f3be5d817ef113607e79
ms.sourcegitcommit: 94fa3e57fa6505551d84ae7b458150dceff30db7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/26/2021
ms.locfileid: "51394714"
---
# <a name="add-your-organizations-brand-to-your-microsoft-365-for-business-message-encryption-encrypted-messages"></a>Aggiungere il marchio dell'organizzazione ai messaggi crittografati di Crittografia messaggi di Microsoft 365 per le aziende

È possibile applicare il marchio aziendale per personalizzare l'aspetto dei messaggi di posta elettronica dell'organizzazione e del portale di crittografia. Per iniziare, è necessario applicare le autorizzazioni di amministratore globale all'account aziendale o dell'istituto di istruzione. Dopo aver disporre di queste autorizzazioni, utilizzare i cmdlet Get-OMEConfiguration e Set-OMEConfiguration Windows PowerShell per personalizzare queste parti dei messaggi di posta elettronica crittografati:
  
- Testo introduttivo

- Disclaimer text

- URL dell'informativa sulla privacy dell'organizzazione

- Testo nel portale OME

- Logo visualizzato nel messaggio di posta elettronica e nel portale OME o se usare un logo

- Colore di sfondo nel messaggio di posta elettronica e nel portale OME

È anche possibile ripristinare l'aspetto predefinito in qualsiasi momento.

Se si desidera un maggiore controllo, usare Crittografia avanzata messaggi di Office 365 per creare più modelli per i messaggi di posta elettronica crittografati provenienti dall'organizzazione. Utilizzare questi modelli per controllare parti dell'esperienza utente finale. Ad esempio, specificare se i destinatari possono utilizzare google, yahoo e account Microsoft per accedere al portale di crittografia. Utilizzare i modelli per soddisfare diversi casi d'uso, ad esempio:

- Singoli reparti, ad esempio Finance, Sales e così via.

- Prodotti diversi

- Aree geografiche o paesi diversi

- Se si desidera consentire la revoca dei messaggi di posta elettronica

- Indica se i messaggi di posta elettronica inviati a destinatari esterni scadono dopo un numero di giorni specificato.

Dopo aver creato i modelli, è possibile applicarli ai messaggi di posta elettronica crittografati utilizzando le regole del flusso di posta di Exchange. Se si dispone di Office 365 Advanced Message Encryption, è possibile revocare qualsiasi messaggio di posta elettronica personalizzato usando questi modelli.

## <a name="work-with-ome-branding-templates"></a>Utilizzare i modelli di personalizzazione di OME

È possibile modificare diverse funzionalità all'interno di un modello di personalizzazione. È possibile modificare, ma non rimuovere, il modello predefinito. Se si dispone di Crittografia avanzata dei messaggi, è anche possibile creare, modificare e rimuovere modelli personalizzati. Usa Windows PowerShell per usare un modello di personalizzazione alla volta.

- [Set-OMEConfiguration:](/powershell/module/exchange/set-omeconfiguration) modificare il modello di personalizzazione predefinito o un modello di personalizzazione personalizzato creato.
- [New-OMEConfiguration](/powershell/module/exchange/new-omeconfiguration) - Crea un nuovo modello di personalizzazione, solo crittografia avanzata dei messaggi.
- [Remove-OMEConfiguration](/powershell/module/exchange/remove-omeconfiguration) : consente di rimuovere un modello di personalizzazione personalizzato, solo crittografia avanzata dei messaggi. Non è possibile eliminare il modello di personalizzazione predefinito.
  
## <a name="modify-an-ome-branding-template"></a>Modificare un modello di personalizzazione OME

Usa Windows PowerShell per modificare un modello di personalizzazione alla volta. Se si dispone di Crittografia avanzata dei messaggi, è anche possibile creare, modificare e rimuovere modelli personalizzati.

1. Utilizzando un account aziendale o dell'istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione, avviare una sessione Windows PowerShell e connettersi a Exchange Online. Per istruzioni, vedere [Connettersi a PowerShell di Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

2. Utilizzare il cmdlet Set-OMEConfiguration come descritto in [Set-OMEConfiguration](/powershell/module/exchange/Set-OMEConfiguration) oppure utilizzare la figura e la tabella seguenti per istruzioni.

![Parti di posta elettronica personalizzabili](../media/ome-template-breakout.png)

|**Per personalizzare questa funzionalità dell'esperienza di crittografia**|**Usare questi comandi**|
|:-----|:-----|
|Colore di sfondo|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -BackgroundColor "<#RRGGBB hexadecimal color code or name value>"` <br/> **Esempio:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -BackgroundColor "#ffffff"` <br/> Per ulteriori informazioni sui colori di sfondo, vedere la sezione [Colori di sfondo](#background-color-reference) più avanti in questo articolo.|
|Logo|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -Image <Byte[]>` <br/> **Esempio:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> Formati di file supportati: png, jpg, bmp o tiff  <br/> Dimensione ottimale relativa al file del logo: inferiore a 40 KB  <br/> Dimensioni ottimali dell'immagine del logo: 170x70 pixel. Se l'immagine supera queste dimensioni, il servizio ridimensiona il logo per la visualizzazione nel portale. Il servizio non modifica il file grafico stesso. Per ottenere risultati ottimali, utilizzare le dimensioni ottimali.|
|Testo accanto al nome e all'indirizzo di posta elettronica del mittente|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -IntroductionText "<String up to 1024 characters>"` <br/> **Esempio:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -IntroductionText "has sent you a secure message."`|
|Testo visualizzato sul pulsante "Leggi messaggio"|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -ReadButtonText "<String up to 1024 characters>"` <br/> **Esempio:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -ReadButtonText "Read Secure Message."`|
|Testo visualizzato sotto il pulsante "Leggi messaggio"|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -EmailText "<String up to 1024 characters>"` <br/> **Esempio:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system."`|
|URL per il collegamento All'informativa sulla privacy|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PrivacyStatementURL "<URL>"` <br/> **Esempio:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -PrivacyStatementURL "https://contoso.com/privacystatement.html"`|
|dichiarazione di non responsabilità nella posta elettronica che contiene il messaggio crittografato|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -DisclaimerText "<Disclaimer statement. String of up to 1024 characters.>"` <br/> **Esempio:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -DisclaimerText "This message is confidential for the use of the addressee only."`|
|testo visualizzato nella parte superiore del portale di visualizzazione del messaggio crittografato|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PortalText "<Text for your portal. String of up to 128 characters.>"` <br/> **Esempio:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal."`|
|Per abilitare o disabilitare l'autenticazione con un pass code una sola volta per questo modello personalizzato|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -OTPEnabled <$true|$false>` <br/> **Esempi:** <br/>Per abilitare passcode una sola volta per questo modello personalizzato <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $true` <br/> Per disabilitare i passcode una sola volta per questo modello personalizzato <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $false`|
|Per abilitare o disabilitare l'autenticazione con le identità Microsoft, Google o Yahoo per questo modello personalizzato|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -SocialIdSignIn <$true|$false>` <br/> **Esempi:** <br/>Per abilitare gli ID di social network per questo modello personalizzato <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $true` <br/> Per disabilitare gli ID di social network per questo modello personalizzato <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $false`|

## <a name="create-an-ome-branding-template-advanced-message-encryption"></a>Creare un modello di personalizzazione OME (Crittografia avanzata messaggi)

Se si dispone della crittografia avanzata dei messaggi di Office 365, è possibile creare modelli di personalizzazione personalizzati per l'organizzazione utilizzando il cmdlet [New-OMEConfiguration.](/powershell/module/exchange/new-omeconfiguration) Dopo aver creato il modello, modificare il modello utilizzando il cmdlet Set-OMEConfiguration come descritto in [Modify an OME branding template](#modify-an-ome-branding-template). È possibile creare più modelli.

Per creare un nuovo modello di personalizzazione personalizzato:

1. Utilizzando un account aziendale o dell'istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione, avviare una sessione Windows PowerShell e connettersi a Exchange Online. Per istruzioni, vedere [Connettersi a PowerShell di Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

2. Utilizzare il cmdlet [New-OMEConfiguration](/powershell/module/exchange/new-omeconfiguration) per creare un nuovo modello.

   ```powershell
   New-OMEConfiguration -Identity "<OMEConfigurationName>"
   ```

   Ad esempio,

   ```powershell
   New-OMEConfiguration -Identity "Custom branding template"
   ```

## <a name="return-the-default-branding-template-to-its-original-values"></a>Ripristinare i valori originali del modello di personalizzazione predefinito

Per rimuovere tutte le modifiche dal modello predefinito, incluse le personalizzazioni del marchio e così via, completare la procedura seguente:
  
1. Utilizzando un account aziendale o dell'istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione, avviare una sessione Windows PowerShell e connettersi a Exchange Online. Per istruzioni, vedere [Connettersi a PowerShell di Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

2. Utilizzare il cmdlet **Set-OMEConfiguration** come descritto in [Set-OMEConfiguration](/powershell/module/exchange/Set-OMEConfiguration). Per rimuovere le personalizzazioni dell'organizzazione dai valori DisclaimerText, EmailText e PortalText, impostare il valore su una stringa vuota, `""` . Per tutti i valori dell'immagine, ad esempio Logo, imposta il valore su  `"$null"` .

   Nella tabella seguente vengono descritte le impostazioni predefinite dell'opzione di personalizzazione della crittografia.

   |Per ripristinare il testo e l'immagine predefiniti per questa funzionalità dell'esperienza di crittografia|Usare questi comandi|
   |:-----|:-----|
   |Testo predefinito fornito con messaggi di posta elettronica crittografati.  Il testo predefinito viene visualizzato sopra le istruzioni per la visualizzazione di messaggi crittografati|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -EmailText "<empty string>"` <br/> **Esempio:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""`|
   |dichiarazione di non responsabilità nella posta elettronica che contiene il messaggio crittografato|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" DisclaimerText "<empty string>"` <br/> **Esempio:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""`|
   |testo visualizzato nella parte superiore del portale di visualizzazione del messaggio crittografato|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PortalText "<empty string>"` <br/> **Esempio di ripristino dell'impostazione predefinita:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""`|
   |Logo|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -Image <"$null">` <br/> **Esempio di ripristino dell'impostazione predefinita:** <br/>  `Set-OMEConfiguration -Identity "OME configuration" -Image $null`|
   |Colore di sfondo|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -BackgroundColor "$null">` <br/> **Esempio di ripristino dell'impostazione predefinita:** <br/> `Set-OMEConfiguration -Identity "OME configuration" -BackgroundColor $null`|

## <a name="remove-a-custom-branding-template-advanced-message-encryption"></a>Rimuovere un modello di personalizzazione (Crittografia avanzata messaggi)

Puoi solo rimuovere o eliminare i modelli di personalizzazione che hai creato. Non è possibile rimuovere il modello di personalizzazione predefinito.

Per rimuovere un modello di personalizzazione personalizzato:
  
1. Utilizzando un account aziendale o dell'istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione, avviare una sessione Windows PowerShell e connettersi a Exchange Online. Per istruzioni, vedere [Connettersi a PowerShell di Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

2. Utilizzare il cmdlet **Remove-OMEConfiguration** come segue:

   ```powershell
   Remove-OMEConfiguration -Identity ""<OMEConfigurationName>"
   ```

   Ad esempio,

   ```powershell
   Remove-OMEConfiguration -Identity "Branding template 1"
   ```

   Per ulteriori informazioni, vedere [Remove-OMEConfiguration.](/powershell/module/exchange/remove-omeconfiguration)

## <a name="create-an-exchange-mail-flow-rule-that-applies-your-custom-branding-to-encrypted-emails"></a>Creare una regola del flusso di posta di Exchange che applica la personalizzazione ai messaggi di posta elettronica crittografati

Dopo aver modificato il modello predefinito o aver creato nuovi modelli di personalizzazione, è possibile creare regole del flusso di posta di Exchange per applicare la personalizzazione in base a determinate condizioni. Una regola di questo tipo applierà la personalizzazione negli scenari seguenti:

- Se il messaggio di posta elettronica è stato crittografato manualmente dall'utente finale utilizzando Outlook o Outlook sul Web, in precedenza Outlook Web App

- Se il messaggio di posta elettronica è stato crittografato automaticamente da una regola del flusso di posta di Exchange o da un criterio di prevenzione della perdita di dati

Per informazioni su come creare una regola del flusso di posta di Exchange che applica la crittografia, vedere Definire le regole del flusso di posta per crittografare i messaggi di posta [elettronica in Office 365.](define-mail-flow-rules-to-encrypt-email.md)

1. In un Web browser, usando un account aziendale o dell'istituto di istruzione a cui sono state concesse autorizzazioni di amministratore globale, accedere a [Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).

2. Scegliere il **riquadro** Amministratore.

3. Nell'interfaccia di amministrazione di Microsoft 365 scegliere **Interfaccia di amministrazione Di** \> **Exchange.**

4. Nell'interfaccia di amministrazione di Exchange, andare a **Flusso** di posta \> **Regole** e selezionare **Nuova** icona Crea una ![ nuova ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **regola.** Per ulteriori informazioni sull'utilizzo dell'interfaccia di amministrazione di Exchange, vedere Interfaccia di amministrazione [di Exchange in Exchange Online.](/exchange/exchange-admin-center)

5. In **Nome** digitare un nome per la regola, ad esempio Personalizzazione per il reparto vendite.

6. In **Applica questa regola se**, selezionare la condizione **Il** mittente si trova all'interno dell'organizzazione e altre condizioni desiderate nell'elenco delle condizioni disponibili. Ad esempio, potresti voler applicare un particolare modello di personalizzazione a:

   - Tutti i messaggi di posta elettronica crittografati inviati dai membri del reparto finanziario
   - Messaggi di posta elettronica crittografati inviati con una determinata parola chiave, ad esempio "Esterno" o "Partner"
   - Messaggi di posta elettronica crittografati inviati a un dominio specifico

7. In **Eseguire le operazioni seguenti** selezionare Modifica la sicurezza dei **messaggi** \> **Applica personalizzazione ai messaggi OME.** Nell'elenco a discesa selezionare quindi un modello di personalizzazione.

8. (Facoltativo) È possibile configurare la regola del flusso di posta per applicare la crittografia e la personalizzazione. In **Eseguire le operazioni seguenti** selezionare Modifica la sicurezza **dei** messaggi e quindi scegliere Applica crittografia messaggi di **Office 365 e protezione dei diritti.** Selezionare un modello RMS nell'elenco, scegliere **Salva** e quindi **OK.**
  
   L'elenco dei modelli include i modelli e le opzioni predefiniti e gli eventuali modelli personalizzati creati. Se l'elenco è vuoto, assicurarsi di aver configurato la crittografia dei messaggi di Office 365 con le nuove funzionalità. Per istruzioni, vedere [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md). Per informazioni sui modelli predefiniti, vedere [Configuring and managing templates for Azure Information Protection.](/information-protection/deploy-use/configure-policy-templates) Per informazioni **sull'opzione Non inoltrare,** vedere [Opzione Non inoltrare per i messaggi di posta elettronica.](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails) Per informazioni sull'opzione **crittografa** solo, vedere [Opzione Crittografa solo per i messaggi di posta elettronica.](/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)

   Scegliere **Aggiungi azione** se si desidera specificare un'altra azione.

## <a name="background-color-reference"></a>Informazioni di riferimento sul colore di sfondo

I nomi dei colori che è possibile utilizzare per il colore di sfondo sono limitati. Invece di un nome di colore, puoi usare un valore di codice esadecimale (#RRGGBB). È possibile utilizzare un valore di codice esadecimale che corrisponde a un nome di colore oppure un valore di codice esadecimale personalizzato. Assicurarsi di racchiudere il valore del codice esadecimale tra virgolette (ad esempio, `"#f0f8ff"` ).

I nomi dei colori di sfondo disponibili e i valori del codice esadecimale corrispondenti sono descritti nella tabella seguente.

|**Nome colore**|**Codice colore**|
|---|---|
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