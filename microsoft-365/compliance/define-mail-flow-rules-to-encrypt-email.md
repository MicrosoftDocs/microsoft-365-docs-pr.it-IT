---
title: Definire regole del flusso di posta per crittografare i messaggi di posta elettronica
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 9b7daf19-d5f2-415b-bc43-a0f5f4a585e8
ms.collection:
- M365-security-compliance
description: Gli amministratori possono imparare a creare regole del flusso di posta (regole di trasporto) per crittografare e decrittografare i messaggi utilizzando la crittografia dei messaggi di Office 365.
ms.openlocfilehash: f9e9440c40b68f36d0dcca069dcd0797412af184
ms.sourcegitcommit: f70f75b9dd163c00a3c6bc4b9f9b055e90c50367
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2020
ms.locfileid: "43790705"
---
# <a name="define-mail-flow-rules-to-encrypt-email-messages"></a>Definire regole del flusso di posta per crittografare i messaggi di posta elettronica

In qualità di amministratore globale, è possibile creare regole del flusso di posta (note anche come regole di trasporto) per proteggere i messaggi di posta elettronica inviati e ricevuti. È possibile configurare le regole per crittografare i messaggi di posta elettronica in uscita e rimuovere la crittografia dai messaggi crittografati provenienti dall'interno dell'organizzazione o dalle risposte ai messaggi crittografati inviati dall'organizzazione. Per creare queste regole, è possibile utilizzare l'interfaccia di amministrazione di Exchange (EAC) o Exchange Online PowerShell. Oltre alle regole di crittografia generali, è inoltre possibile scegliere di abilitare o disabilitare le opzioni di crittografia dei messaggi individuali per gli utenti finali.

Non è possibile crittografare la posta in ingresso dai mittenti all'esterno dell'organizzazione.

Se di recente è stata eseguita la migrazione da AD RMS a Azure Information Protection, è necessario esaminare le regole del flusso di posta esistenti per assicurarsi che possano continuare a funzionare nel nuovo ambiente. Inoltre, se si desidera sfruttare le nuove funzionalità di crittografia dei messaggi di Office 365 disponibili tramite Azure Information Protection, è necessario aggiornare le regole del flusso di posta esistenti. In caso contrario, gli utenti continueranno a ricevere messaggi di posta elettronica crittografati che utilizzano il formato di allegato HTML precedente anziché la nuova esperienza OME senza problemi. Se non è ancora stato configurato OME, vedere [configurare le nuove funzionalità di crittografia dei messaggi di Office 365](set-up-new-message-encryption-capabilities.md) per informazioni.

Per informazioni sui componenti che compongono le regole del flusso di posta e sulla modalità di funzionamento delle regole del flusso di posta, vedere [Mail Flow Rules (Transport Rules) in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules). Per ulteriori informazioni su come funzionano le regole del flusso di posta con Azure Information Protection, vedere [configurazione delle regole del flusso di posta di Exchange Online per le etichette di Azure Information Protection](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-exo-rules).

> [!IMPORTANT]
> Per gli ambienti ibridi di Exchange, gli utenti locali possono inviare messaggi crittografati tramite OME solo se la posta elettronica viene instradata tramite Exchange Online. Per configurare OME in un ambiente Exchange ibrido, è necessario prima [configurare Hybrid usando la procedura guidata di configurazione ibrida](https://docs.microsoft.com/Exchange/exchange-hybrid) e quindi [configurare il flusso di posta dal server di posta elettronica a Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365). Dopo aver configurato la posta elettronica per il flusso tramite Office 365, è possibile configurare le regole del flusso di posta per OME utilizzando queste linee guida.

## <a name="create-mail-flow-rules-to-encrypt-email-messages-with-the-new-ome-capabilities"></a>Creare regole del flusso di posta per crittografare i messaggi di posta elettronica con le nuove funzionalità OME

È possibile definire le regole del flusso di posta per l'attivazione della crittografia dei messaggi con le nuove funzionalità OME tramite EAC.

### <a name="use-the-eac-to-create-a-rule-for-encrypting-email-messages-with-the-new-ome-capabilities"></a>Utilizzo dell'interfaccia di amministrazione di Exchange per creare una regola per la crittografia dei messaggi di posta elettronica con le nuove funzionalità OME

1. In un Web browser, utilizzando un account aziendale o dell'Istituto di istruzione a cui sono state concesse le autorizzazioni di amministratore globale, [accedere a Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).

2. Scegliere il riquadro **amministratore** .

3. Nell'interfaccia di amministrazione di Microsoft 365 fare clic su interfaccia di **Amministrazione** \> di **Exchange**.

4. Nell'interfaccia di amministrazione di Exchange, andare a **regole** del **flusso** \> di posta e selezionare **nuova** ![nuova icona](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **creare una nuova regola**. Per ulteriori informazioni sull'utilizzo di EAC, vedere interfaccia [di amministrazione di Exchange in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).

5. In **nome**Digitare un nome per la regola, ad esempio crittografare la posta per DrToniRamos@hotmail.com.

6. In **Applica questa regola se** selezionare una condizione e, se necessario, immettere un valore. Ad esempio, per crittografare i messaggi indirizzati a DrToniRamos@hotmail.com:

   1. In **Applica questa regola se**, selezionare **il destinatario è**.

   2. Selezionare un nome esistente dall'elenco dei contatti o digitare un nuovo indirizzo di posta elettronica nella casella **Controlla nomi**.

      - Per selezionare un nome esistente, selezionarlo dall'elenco e quindi fare clic su **OK**.

      - Per immettere un nuovo nome, digitare un indirizzo di posta elettronica nella casella **Controlla nomi** e quindi fare clic su **Controlla nomi** \> **OK**.

7. Per aggiungere altre condizioni, scegliere **altre opzioni** , quindi fare clic su **Aggiungi condizione** e selezionare dall'elenco.

   Ad esempio, per applicare la regola solo se il destinatario si trova all'esterno dell'organizzazione, selezionare **Aggiungi condizione** e quindi selezionare **il destinatario è esterno/interno** \> all' **esterno dell'organizzazione** \> **OK**.

8. Per abilitare la crittografia utilizzando le nuove funzionalità OME, **fare**clic su **modifica la sicurezza dei messaggi** e quindi scegliere **Apply Office 365 Message Encryption and Rights Protection**. Selezionare un modello RMS nell'elenco, scegliere **Salva**e quindi fare clic su **OK**.
  
  L'elenco dei modelli include tutti i modelli e le opzioni predefiniti, nonché tutti i modelli personalizzati creati per l'utilizzo da parte di Office 365. Se l'elenco è vuoto, verificare di aver configurato la crittografia dei messaggi di Office 365 con le nuove funzionalità descritte in [configurare le nuove funzionalità di crittografia dei messaggi di office 365](set-up-new-message-encryption-capabilities.md). Per informazioni sui modelli predefiniti, vedere [Configuring and Managing templates for Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates). Per informazioni sull'opzione non **inoltrare** , vedere non [inoltrare l'opzione per i messaggi di posta elettronica](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails). Per informazioni sull'opzione **solo crittografia** , vedere [opzione di crittografia solo per i messaggi di posta elettronica](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).

  Se si desidera specificare un'altra azione, è possibile scegliere **Aggiungi azione** .

### <a name="use-the-eac-to-update-an-existing-mail-flow-rule-to-use-the-new-ome-capabilities"></a>Utilizzo dell'interfaccia di amministrazione di Exchange per aggiornare una regola del flusso di posta esistente per l'utilizzo delle nuove funzionalità OME

1. In un Web browser, utilizzando un account aziendale o dell'Istituto di istruzione a cui sono state concesse le autorizzazioni di amministratore globale, [accedere a Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).

2. Scegliere il riquadro **amministratore** .

3. Nell'interfaccia di amministrazione di Microsoft 365 fare clic su interfaccia di **Amministrazione** \> di **Exchange**.

4. Nell'interfaccia di amministrazione di Exchange, andare a **Flusso di posta** \> **Regole**.

5. Nell'elenco delle regole del flusso di posta, selezionare la regola che si desidera modificare per utilizzare le nuove funzionalità ome e quindi scegliere **modifica** ![icona](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)modifica.

6. Per abilitare la crittografia utilizzando le nuove funzionalità OME, scegliere **modifica la sicurezza dei messaggi** e quindi **fare**clic su **applica crittografia messaggi di Office 365 e protezione dei diritti**. Selezionare un modello RMS nell'elenco, scegliere **Salva** e quindi fare clic su **OK**.

   L'elenco dei modelli include tutti i modelli e le opzioni predefiniti, nonché tutti i modelli personalizzati creati per l'utilizzo da parte di Office 365. Se l'elenco è vuoto, verificare di aver configurato la crittografia dei messaggi di Office 365 con le nuove funzionalità descritte in [configurare le nuove funzionalità di crittografia dei messaggi di office 365 basate su Azure Information Protection](set-up-new-message-encryption-capabilities.md). Per informazioni sui modelli predefiniti, vedere [Configuring and Managing templates for Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates). Per informazioni sull'opzione non **inoltrare** , vedere non [inoltrare l'opzione per i messaggi di posta elettronica](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails). Per informazioni sull'opzione **solo crittografia** , vedere [opzione di crittografia solo per i messaggi di posta elettronica](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).

   Se si desidera specificare un'altra azione, è possibile scegliere **Aggiungi azione** .

7. Nell'elenco **eseguire le operazioni seguenti** rimuovere tutte le azioni assegnate per **modificare la sicurezza** \> dei messaggi **applicare la versione precedente di ome**.

8. Fare clic su **Salva**.

## <a name="create-mail-flow-rules-to-remove-encryption-for-outgoing-email-messages-with-the-new-ome-capabilities"></a>Creare regole del flusso di posta per rimuovere la crittografia per i messaggi di posta elettronica in uscita con le nuove funzionalità OME

È possibile definire le regole del flusso di posta per l'attivazione rimuovere la crittografia dei messaggi con le nuove funzionalità OME utilizzando l'interfaccia di amministrazione di Exchange.

### <a name="use-the-eac-to-create-a-rule-to-remove-encryption-from-email-messages-with-the-new-ome-capabilities"></a>Utilizzo dell'interfaccia di amministrazione di Exchange per creare una regola per rimuovere la crittografia dai messaggi di posta elettronica con le nuove funzionalità OME

1. In un Web browser, utilizzando un account aziendale o dell'Istituto di istruzione a cui sono state concesse le autorizzazioni di amministratore globale, [accedere a Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).

2. Scegliere il riquadro **amministratore** .

3. Nell'interfaccia di amministrazione di Microsoft 365 fare clic su interfaccia di **Amministrazione** \> di **Exchange**.

4. Nell'interfaccia di amministrazione di Exchange, andare a **regole** del **flusso** \> di posta e selezionare **nuova** ![nuova icona](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **creare una nuova regola**. Per ulteriori informazioni sull'utilizzo di EAC, vedere interfaccia [di amministrazione di Exchange in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).

5. In **nome**Digitare un nome per la regola, ad esempio Rimuovi la crittografia dalla posta in uscita.

6. In **applica questa regola se** si selezionano le condizioni in cui la crittografia deve essere rimossa dai messaggi, aggiungere **il mittente si trova** \> **all'interno dell'organizzazione**. A questo punto, aggiungere altre condizioni per assegnare destinatari specifici, ad esempio **il destinatario si trova** \> **all'esterno dell'organizzazione**.

7. In **effettuare le seguenti operazioni**, selezionare **modifica la sicurezza** \> **dei messaggi rimuovere Office 365 Message Encryption and Rights Protection**.

8. Selezionare **Salva**.

## <a name="create-mail-flow-rules-for-office-365-message-encryption-without-the-new-capabilities"></a>Creare regole del flusso di posta per la crittografia dei messaggi di Office 365 senza le nuove funzionalità

Se l'organizzazione non è stata ancora spostata nelle nuove funzionalità OME, utilizzare queste attività per definire le regole del flusso di posta per crittografare i messaggi per l'organizzazione. Microsoft consiglia di effettuare un piano per passare alle nuove funzionalità OME non appena è ragionevole per la propria organizzazione. Per istruzioni, vedere [configurare le nuove funzionalità di crittografia dei messaggi di Office 365 basate su Azure Information Protection](set-up-new-message-encryption-capabilities.md).

### <a name="use-the-eac-to-create-a-mail-flow-rule-for-encrypting-email-messages-without-the-new-ome-capabilities"></a>Utilizzo dell'interfaccia di amministrazione di Exchange per creare una regola del flusso di posta per la crittografia dei messaggi di posta elettronica senza le nuove funzionalità OME

1. In un Web browser, utilizzando un account aziendale o dell'Istituto di istruzione a cui sono state concesse le autorizzazioni di amministratore globale, [accedere a Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).

2. Scegliere il riquadro **amministratore** .

3. Nell'interfaccia di amministrazione di Microsoft 365 fare clic su interfaccia di **Amministrazione** \> di **Exchange**.

4. Nell'interfaccia di amministrazione di Exchange, andare a **regole** del **flusso** \> di posta e selezionare **nuova** ![nuova icona](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **creare una nuova regola**. Per ulteriori informazioni sull'utilizzo di EAC, vedere interfaccia [di amministrazione di Exchange in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).

5. In **nome**Digitare un nome per la regola, ad esempio crittografare la posta per DrToniRamos@hotmail.com.

6. In **Applica questa regola se** selezionare una condizione e, se necessario, immettere un valore. Ad esempio, per crittografare i messaggi indirizzati a DrToniRamos@hotmail.com:

   1. In **Applica questa regola se**, selezionare **il destinatario è**.

   2. Selezionare un nome esistente dall'elenco dei contatti o digitare un nuovo indirizzo di posta elettronica nella casella **Controlla nomi**.

      - Per selezionare un nome esistente, selezionarlo dall'elenco e quindi fare clic su **OK**.

      - Per immettere un nuovo nome, digitare un indirizzo di posta elettronica nella casella **Controlla nomi** e quindi fare clic su **Controlla nomi** \> **OK**.

7. Per aggiungere altre condizioni, scegliere **altre opzioni** , quindi fare clic su **Aggiungi condizione** e selezionare dall'elenco.

   Ad esempio, per applicare la regola solo se il destinatario si trova all'esterno dell'organizzazione, selezionare **Aggiungi condizione** e quindi selezionare **il destinatario è esterno/interno** \> all' **esterno dell'organizzazione** \> **OK**.

8. Per abilitare la crittografia senza utilizzare le nuove funzionalità ome, **fare quanto segue**, selezionare **modifica la sicurezza** \> dei messaggi **applicare la versione precedente di ome**e quindi fare clic su **Salva**.

  Se viene visualizzato un messaggio di errore che non è abilitato per la gestione delle licenze IRM, non è stato ancora configurato OME per la propria organizzazione. Se si desidera configurare OME adesso, è necessario configurarlo per utilizzare le nuove funzionalità OME. Per informazioni, vedere [configurare le nuove funzionalità di crittografia dei messaggi di Office 365 basate su Azure Information Protection](set-up-new-message-encryption-capabilities.md). Microsoft non supporta più la configurazione di nuove distribuzioni di OME senza le nuove funzionalità.

  Se si desidera specificare un'altra azione, è possibile scegliere **Aggiungi azione** .

### <a name="use-exchange-online-powershell-to-create-a-mail-flow-rule-for-encrypting-email-messages-without-the-new-ome-capabilities"></a>Utilizzare PowerShell di Exchange Online per creare una regola del flusso di posta per la crittografia dei messaggi di posta elettronica senza le nuove funzionalità OME

1. Connettersi a PowerShell per Exchange Online. Per ulteriori informazioni, vedere [Connessione a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).

2. Creare una regola utilizzando il cmdlet **New-TransportRule** e impostare il parametro _ApplyOME_ su `$true`.

   In questo esempio si presuppone che tutti i messaggi di posta elettronica inviati a DrToniRamos@hotmail.com debbano essere crittografati.

   ```powershell
   New-TransportRule -Name "Encrypt rule for Dr Toni Ramos" -SentTo "DrToniRamos@hotmail.com" -SentToScope "NotinOrganization" -ApplyOME $true
   ```

   **Note**:

   - Il nome univoco della nuova regola è "crittografare la regola per la Dott. ssa Toni Ramos".

   - Il parametro _SentTo_ consente di specificare i destinatari dei messaggi (identificati per nome, indirizzo di posta elettronica, nome distinto e così via). In questo esempio, il destinatario è identificato dall'indirizzo di posta elettronica "DrToniRamos@hotmail.com".

   - Il parametro _SentToScope_ consente di specificare la posizione dei destinatari del messaggio. In questo esempio, la cassetta postale del destinatario si trova in Hotmail e non fa parte dell'organizzazione, quindi viene `NotInOrganization` utilizzato il valore.

   Per informazioni dettagliate su sintassi e parametri, vedere [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/New-TransportRule).

### <a name="remove-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a>Rimuovere la crittografia dalle risposte di posta elettronica crittografate senza le nuove funzionalità OME

Quando gli utenti di posta elettronica inviano messaggi crittografati, i relativi destinatari possono rispondere con risposte crittografate. È possibile creare regole del flusso di posta per rimuovere automaticamente la crittografia dalle risposte in modo che gli utenti di posta elettronica nell'organizzazione non debbano accedere al portale di crittografia per visualizzarli. È possibile utilizzare l'interfaccia di amministrazione di Exchange o i cmdlet di Windows PowerShell per definire queste regole. Se non si utilizzano ancora le nuove funzionalità OME, è possibile decrittografare solo i messaggi inviati dall'interno dell'organizzazione o i messaggi che rispondono ai messaggi inviati dall'interno dell'organizzazione. Non è possibile decrittografare i messaggi crittografati provenienti dall'esterno dell'organizzazione.

#### <a name="use-the-eac-to-create-a-rule-for-removing-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a>Utilizzo dell'interfaccia di amministrazione di Exchange per creare una regola per la rimozione della crittografia dalle risposte di posta elettronica crittografate senza le nuove funzionalità OME

1. In un Web browser, utilizzando un account aziendale o dell'Istituto di istruzione a cui sono state concesse le autorizzazioni di amministratore, [accedere a Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).

2. Scegliere il riquadro **amministratore** .

3. Nell'interfaccia di amministrazione di Microsoft 365 fare clic su interfaccia di **Amministrazione** \> di **Exchange**.

4. Nell'interfaccia di amministrazione di Exchange, andare a **regole** del **flusso** \> di posta e selezionare **nuova** ![nuova icona](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **creare una nuova regola**. Per ulteriori informazioni sull'utilizzo di EAC, vedere interfaccia [di amministrazione di Exchange in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).

5. In **nome**Digitare un nome per la regola, ad esempio Rimuovi la crittografia dalla posta in arrivo.

6. In **applica questa regola se** si selezionano le condizioni in cui la crittografia deve essere rimossa dai messaggi, ad esempio **il destinatario si trova** \> **all'interno dell'organizzazione**.

7. In **effettuare le seguenti operazioni**, selezionare **modifica la sicurezza** \> dei messaggi **rimuovere la versione precedente di ome**.

8. Selezionare **Salva**.

#### <a name="use-exchange-online-powershell-to-create-a-rule-to-remove-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a>Utilizzo di PowerShell di Exchange Online per creare una regola per rimuovere la crittografia dalle risposte di posta elettronica crittografate senza le nuove funzionalità OME

1. Connettersi a PowerShell per Exchange Online. Per ulteriori informazioni, vedere [Connessione a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).

2. Creare una regola utilizzando il cmdlet **New-TransportRule** e impostare il parametro _RemoveOME_ su `$true`.

   In questo esempio viene rimossa la crittografia da tutti i messaggi inviati ai destinatari nell'organizzazione.

   ```powershell
   New-TransportRule -Name "Remove encryption from incoming mail" -SentToScope "InOrganization" -RemoveOME $true
   ```

   **Note**:

   - Il nome univoco della nuova regola è "Rimuovi crittografia dalla posta in arrivo".

   - Il parametro _SentToScope_ consente di specificare la posizione dei destinatari del messaggio. In questo esempio viene utilizzato il `InOrganization` valore Value, che indica quanto segue:

     - Il destinatario è una cassetta postale, un utente di posta, un gruppo o una cartella pubblica abilitata all'utilizzo della posta nell'organizzazione.

       oppure

     - L'indirizzo di posta elettronica del destinatario si trova in un dominio accettato configurato come dominio autorevole o come dominio di inoltro interno nell'organizzazione _e_ il messaggio è stato inviato o ricevuto tramite una connessione autenticata.

Per informazioni dettagliate su sintassi e parametri, vedere [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/New-TransportRule).

## <a name="related-topics"></a>Argomenti correlati

[Crittografia in Office 365](encryption.md)

[Configurare le nuove funzionalità di Office 365 Message Encryption](set-up-new-message-encryption-capabilities.md)

[Aggiungere una personalizzazione ai messaggi crittografati](add-your-organization-brand-to-encrypted-messages.md)

[Regole del flusso di posta (regole di trasporto) in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=506707)

[Regole del flusso di posta (regole di trasporto in Exchange Online Protection](https://go.microsoft.com/fwlink/p/?LinkId=506708)
