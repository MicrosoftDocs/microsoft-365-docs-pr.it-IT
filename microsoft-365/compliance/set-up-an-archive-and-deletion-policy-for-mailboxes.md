---
title: Configurare un criterio di archiviazione ed eliminazione per le cassette postali nell'organizzazione di Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MBS150
- BCS160
ms.assetid: ec3587e4-7b4a-40fb-8fb8-8aa05aeae2ce
description: Creare un criterio di archiviazione ed eliminazione in Office 365 che sposta automaticamente gli elementi nella cassetta postale di archiviazione di un utente.
ms.openlocfilehash: 801f97b658df08cd3c548c6aed99018a8613b473
ms.sourcegitcommit: 1d376287f6c1bf5174873e89ed4bf7bb15bc13f6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/14/2019
ms.locfileid: "38686611"
---
# <a name="set-up-an-archive-and-deletion-policy-for-mailboxes-in-your-office-365-organization"></a>Configurare un criterio di archiviazione ed eliminazione per le cassette postali nell'organizzazione di Office 365

 In Office 365, gli amministratori possono creare un criterio di eliminazione e archiviazione che sposta automaticamente gli elementi nella cassetta postale di archiviazione di un utente ed Elimina automaticamente gli elementi dalla cassetta postale. L'amministratore esegue questa operazione creando un criterio di conservazione assegnato alle cassette postali e sposta gli elementi nella cassetta postale di archiviazione di un utente dopo un determinato periodo di tempo e che elimina anche gli elementi dalla cassetta postale dopo aver raggiunto un determinato limite di validità. Le regole effettive che determinano gli elementi spostati o eliminati e quando ciò accade sono denominati tag di conservazione. I tag di conservazione sono collegati a un criterio di conservazione, che a sua sua è assegnato alla cassetta postale di un utente. Un tag di conservazione applica le impostazioni di conservazione ai singoli messaggi e alle cartelle della cassetta postale di un utente. Definisce per quanto tempo un messaggio rimane nella cassetta postale e l'azione che viene eseguita quando il messaggio raggiunge l'età di conservazione specificata. Quando un messaggio raggiunge il periodo di validità della conservazione, viene spostato nella cassetta postale di archiviazione dell'utente oppure viene eliminato. 
  
La procedura descritta in questo articolo consentirà di impostare un criterio di conservazione e archiviazione per un'organizzazione fittizia denominata Alpine House. La configurazione di questo criterio include le attività seguenti:
  
- Abilitazione di una cassetta postale di archiviazione per ogni utente dell'organizzazione. Questo consente agli utenti di aggiungere l'archiviazione delle cassette postali ed è necessario affinché i criteri di conservazione possano spostare gli elementi nella cassetta postale di archiviazione. Consente inoltre a un utente di archiviare le informazioni di archiviazione spostando gli elementi nella cassetta postale di archiviazione. 
    
- Creazione di tre tag di conservazione personalizzati che eseguono le operazioni seguenti: 
    
  - Sposta automaticamente gli elementi di 3 anni nella cassetta postale di archiviazione dell'utente. Lo spostamento degli elementi nella cassetta postale di archiviazione libera lo spazio nella cassetta postale principale di un utente.
    
  - Elimina automaticamente gli elementi di 5 anni dalla cartella Posta eliminata. Questo libera anche lo spazio nella cassetta postale principale dell'utente. Gli utenti avranno la possibilità di recuperare questi elementi, se necessario. Per ulteriori dettagli, vedere la nota a piè di pagina nella sezione [altre informazioni](#more-information) . 
    
  - Consente di eliminare automaticamente (e definitivamente) gli elementi che hanno 7 anni dalla cassetta postale principale e da quella di archiviazione. A causa delle normative di conformità, alcune organizzazioni sono tenute a conservare la posta elettronica per un determinato periodo di tempo. Dopo la scadenza di questo periodo di tempo, un'organizzazione potrebbe voler rimuovere definitivamente queste cassette postali degli utenti. 
    
- Creazione di un nuovo criterio di conservazione e aggiunta di nuovi tag di conservazione personalizzati. Inoltre, verranno aggiunti anche i tag di conservazione incorporati al nuovo criterio di conservazione. Sono inclusi i tag personali che gli utenti possono assegnare agli elementi nella propria cassetta postale. È inoltre possibile aggiungere un tag di conservazione che consente di spostare gli elementi dalla cartella elementi ripristinabili nella cassetta postale principale dell'utente alla cartella elementi ripristinabili nella cassetta postale di archiviazione. Questo consente di liberare spazio nella cartella elementi ripristinabili di un utente quando la relativa cassetta postale viene bloccata.
    
È possibile seguire alcuni o tutti i passaggi descritti in questo articolo per configurare un criterio di eliminazione e archiviazione per le cassette postali nella propria organizzazione. È consigliabile testare questo processo su poche cassette postali prima di implementarlo in tutte le cassette postali dell'organizzazione.
  
## <a name="before-you-begin"></a>Prima di iniziare

- Per eseguire la procedura descritta in questo argomento, è necessario essere un amministratore globale dell'organizzazione di Office 365. 
    
-  Quando si crea un nuovo account utente in Office 365 e si assegna all'utente una licenza di Exchange Online, viene creata automaticamente una cassetta postale per l'utente. Quando si crea la cassetta postale, viene automaticamente assegnato un criterio di conservazione predefinito, denominato criterio di gestione record di messaggistica predefinito. In questo articolo viene creato un nuovo criterio di conservazione e quindi viene assegnato alle cassette postali degli utenti, sostituendo il criterio di gestione record di messaggistica predefinito. Una cassetta postale può disporre di un solo criterio di conservazione a cui è assegnato un solo momento.
    
- Per ulteriori informazioni sui tag di conservazione e i criteri di conservazione in Exchange Online, vedere Tag di conservazione [e criteri di conservazione](https://go.microsoft.com/fwlink/p/?LinkId=404424).
    
## <a name="step-1-enable-archive-mailboxes-for-users"></a>Passaggio 1: abilitare le cassette postali di archiviazione per gli utenti

Il primo passaggio consiste nell'abilitare la cassetta postale di archiviazione per ogni utente dell'organizzazione. La cassetta postale di archiviazione di un utente deve essere abilitata in modo che un tag di conservazione con l'azione di conservazione "Sposta nell'archivio" possa spostare l'elemento dopo la scadenza dell'età di conservazione. 
  
> [!NOTE]
> È possibile abilitare le cassette postali di archiviazione in qualsiasi momento durante questo processo, purché siano abilitate a un certo punto prima di completare il processo. Se una cassetta postale di archiviazione non è abilitata, non viene eseguita alcuna azione su tutti gli elementi a cui è assegnato un criterio di archiviazione. 
  
1. Passare a [https://protection.office.com](https://protection.office.com).
    
2. Sign in to Office 365 using your global administrator account.
    
    
3. Nel centro sicurezza & conformità, accedere a \> **Archivio**di **governance dei dati** .
    
    Viene visualizzato un elenco delle cassette postali nell'organizzazione e se la corrispondente cassetta postale di archiviazione è abilitata o disabilitata. 
    
4. Seleziona tutte le cassette postali facendo clic sul primo nell'elenco, tenendo premuto il tasto **MAIUSC** e facendo clic sull'ultimo nell'elenco. 
    
    > [!TIP]
    > In questo passaggio si presuppone che non siano abilitate le cassette postali di archiviazione. Se si dispone di cassette postali con l'archivio abilitato, tenere premuto il tasto **CTRL** e fare clic su ogni cassetta postale che dispone di una cassetta postale di archiviazione disabilitata. In alternativa, è possibile fare clic sull'intestazione di colonna **cassetta postale di archiviazione** per ordinare le righe in base al fatto che la cassetta postale di archiviazione sia abilitata o disabilitata per semplificare la selezione delle cassette postali. 
  
5. Nel riquadro dei dettagli, in **modifica in blocco**, fare clic su **Abilita**.
    
    Viene visualizzato un messaggio di avviso in cui viene indicato che gli elementi più vecchi di due anni verranno spostati nella nuova cassetta postale di archiviazione. Ciò è dovuto al fatto che i criteri di conservazione predefiniti a cui viene assegnata una nuova cassetta postale utente quando viene creata dispongono di un tag di criteri di archiviazione predefinito che ha un'età di conservazione di 2 anni. Il tag del criterio predefinito di archiviazione personalizzato che verrà creato nel passaggio 2 ha un'età di conservazione di 3 anni. Questo significa che gli elementi che hanno una età di 3 anni verranno spostati nella cassetta postale di archiviazione.
    
6. Fare clic su **Sì** per chiudere il messaggio di avviso e avviare il processo per abilitare la cassetta postale di archiviazione per ogni cassetta postale selezionata. 
    
7. Al termine del processo **, fare clic** ![su Aggiorna](media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) aggiornamento per aggiornare l'elenco nella pagina **Archivio** . 
    
    La cassetta postale di archiviazione è abilitata per tutti gli utenti dell'organizzazione.
    
    ![L'elenco delle cassette postali con la cassetta postale di archiviazione abilitata](media/61a7cb97-1bed-4808-aa5f-b6b761cfa8de.png)
  
8. Lasciare aperto il Centro sicurezza & conformità. Verrà utilizzato nel passaggio successivo.
    
## <a name="step-2-create-new-retention-tags-for-the-archive-and-deletion-policies"></a>Passaggio 2: creare nuovi tag di conservazione per i criteri di eliminazione e archiviazione

In questo passaggio verranno creati i tre tag di conservazione personalizzati descritti in precedenza.
  
- Alpine House 3 year move to Archive (criteri di archiviazione personalizzati)
    
- Alpine House 7 year permanentemente Delete (criterio di eliminazione personalizzato)
    
- Casa Alpina elementi eliminati 5 anni eliminare e consentire il ripristino (tag personalizzato per la cartella Posta eliminata)
    
Per creare nuovi tag di conservazione, è possibile utilizzare l'interfaccia di amministrazione di Exchange (EAC) nell'organizzazione di Exchange Online.
  
1. Nel centro sicurezza & conformità, fare clic sull'icona di avvio delle app nell'angolo in alto a sinistra, quindi fare clic sul riquadro **amministratore** . 
    
2. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft 365, fare clic su interfacce di **Amministrazione**, quindi su **Exchange**.
    
    ![Screenshot Visualizza l'interfaccia di amministrazione di Microsoft 365 con l'opzione interfaccia di amministrazione espansa ed Exchange selezionata.](media/47399df2-0bc4-42e2-b183-07750a46bc68.png)
  
3. Nell'interfaccia di amministrazione di Exchange, andare a **tag di conservazione** per la **gestione** \> della conformità
    
    Viene visualizzato un elenco dei tag di conservazione per l'organizzazione.
    
### <a name="create-a-custom-archive-default-policy-tag"></a>Creare un tag di criteri predefinito di archiviazione personalizzato
  
In primo luogo, verrà creato un tag dei criteri predefiniti di archiviazione personalizzato che sposterà gli elementi nella cassetta postale di archiviazione dopo 3 anni. 
  
1. Nella pagina **tag di conservazione** , fare clic su **nuova**![icona](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif)nuovo tag, quindi selezionare **applicato automaticamente all'intera cassetta postale (impostazione predefinita)**. 
    
2. Nel **nuovo tag applicato automaticamente alla pagina intera cassetta postale (impostazione predefinita)** , completare i seguenti campi: 
    
    ![Impostazioni per creare un nuovo tag del criterio di archiviazione predefinito](media/41c0a43c-9c72-44e0-8947-da0831896432.png)
  
1. **Nome** Digitare un nome per il nuovo tag di conservazione. 
    
2. **Azione di conservazione** Selezionare **Sposta in archivio** per spostare gli elementi nella cassetta postale di archiviazione al termine della scadenza del periodo di conservazione. 
    
3. **Periodo di conservazione** Selezionare **quando l'elemento raggiunge la data di validità seguente (in giorni)** e quindi immettere la durata del periodo di conservazione. Per questo scenario, gli elementi verranno spostati nella cassetta postale di archiviazione dopo 1095 giorni (3 anni).
    
4. **Commento** (facoltativo) digitare un commento che spieghi lo scopo del tag di conservazione personalizzato. 
    
3. Fare clic su **Salva** per creare la tag di archiviazione personalizzato. 
    
    Il nuovo archivio di criteri di archiviazione viene visualizzato nell'elenco dei tag di conservazione.
    
### <a name="create-a-custom-deletion-default-policy-tag"></a>Creare un tag dei criteri predefiniti per l'eliminazione personalizzata
  
Successivamente, verrà creato un altro tag personalizzato, ma questo sarà un criterio di eliminazione che elimina definitivamente gli elementi dopo 7 anni.
  
1. Nella pagina **tag di conservazione** , fare clic su **nuova**![icona](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif)nuovo tag, quindi selezionare **applicato automaticamente all'intera cassetta postale (impostazione predefinita)**. 
    
2. Nel **nuovo tag applicato automaticamente alla pagina intera cassetta postale (impostazione predefinita)** , completare i seguenti campi: 
    
    ![Impostazioni per creare un nuovo tag dei criteri predefiniti per l'eliminazione](media/f1f0ff62-eec9-4824-8e7c-d93dcfb09a79.png)
  
1. **Nome** Digitare un nome per il nuovo tag di conservazione. 
    
2. **Azione di conservazione** Selezionare **Elimina definitivamente per eliminare** gli elementi dalla cassetta postale quando scade il periodo di conservazione. 
    
3. **Periodo di conservazione** Selezionare **quando l'elemento raggiunge la data di validità seguente (in giorni)** e quindi immettere la durata del periodo di conservazione. Per questo scenario, gli elementi verranno eliminati dopo 2555 giorni (7 anni).
    
4. **Commento** (facoltativo) digitare un commento che spieghi lo scopo del tag di conservazione personalizzato. 
    
3. Fare clic su **Salva** per creare il tag di eliminazione personalizzato. 
    
    Il nuovo tag di eliminazione viene visualizzato nell'elenco delle etichette di conservazione.
    
### <a name="create-a-custom-retention-policy-tag-for-the-deleted-items-folder"></a>Creare un tag dei criteri di conservazione personalizzati per la cartella Posta eliminata
  
L'ultimo tag di conservazione creato è un tag del criterio di conservazione (RPT) personalizzato per la cartella Posta eliminata. Questo tag eliminerà gli elementi nella cartella Posta eliminata dopo 5 anni e fornirà un periodo di ripristino quando gli utenti possono utilizzare lo strumento Recupera elementi eliminati per recuperare un elemento.
  
1. Nella pagina **tag di conservazione** , fare clic su **nuova** ![icona](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif)nuovo tag, quindi selezionare **applicato automaticamente a una cartella predefinita**. 
    
2. Nel **nuovo tag applicato automaticamente a una pagina predefinita della cartella** , completare i seguenti campi: 
    
    ![Impostazioni per la creazione di un nuovo tag dei criteri di conservazione per la cartella Posta eliminata](media/6f3104bd-5edb-48ac-884d-5fe13d81dd1d.png)
  
1. **Nome** Digitare un nome per il nuovo tag di conservazione. 
    
2. **Applicare questo tag alla cartella predefinita seguente** Nell'elenco a discesa selezionare **elementi eliminati**.
    
3. **Azione di conservazione** Selezionare **Elimina e Consenti ripristino** per eliminare gli elementi quando il periodo di conservazione scade, ma Consenti agli utenti di recuperare un elemento eliminato all'interno del periodo di conservazione degli elementi eliminati, che per impostazione predefinita è di 14 giorni. 
    
4. **Periodo di conservazione** Selezionare **quando l'elemento raggiunge la data di validità seguente (in giorni)** e quindi immettere la durata del periodo di conservazione. Per questo scenario, gli elementi verranno eliminati dopo 1825 giorni (5 anni).
    
5. **Commento** (facoltativo) digitare un commento che spieghi lo scopo del tag di conservazione personalizzato. 
    
3. Fare clic su **Salva** per creare il RPT personalizzato per la cartella Posta eliminata. 
    
    Il nuovo RPT viene visualizzato nell'elenco dei tag di conservazione.

## <a name="step-3-create-a-new-retention-policy"></a>Passaggio 3: creare un nuovo criterio di conservazione

Dopo aver creato i tag di conservazione personalizzati, il passaggio successivo consiste nel creare un nuovo criterio di conservazione e aggiungere i tag di conservazione. Verranno aggiunti i tre tag di conservazione personalizzati creati nel passaggio 2 e i tag incorporati che sono stati citati nella prima sezione. Nel passaggio 4, è possibile assegnare questo nuovo criterio di conservazione alle cassette postali degli utenti.
  
1. Nell'interfaccia di amministrazione di Exchange, andare a **criteri di conservazione**di **Compliance Management** \> .
    
2. Nella pagina **criteri di conservazione** fare clic su **nuova** ![icona](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif)nuova.
    
3. Nella casella **nome** Digitare un nome per il nuovo criterio di conservazione. ad esempio, i **criteri di eliminazione e archiviazione delle case alpine**. 
    
4. In **tag di conservazione**fare **** ![clic su Aggiungi](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif)nuova icona.
    
    Viene visualizzato un elenco dei tag di conservazione nell'organizzazione. Tenere presente che sono visualizzati i tag personalizzati creati nel passaggio 2.
    
5. Aggiungere i 9 tag di conservazione evidenziati nello screenshot seguente (questi tag sono descritti in maggiore dettaglio nella sezione [altre informazioni](#more-information) ). Per aggiungere un tag di conservazione, selezionarlo e fare clic su **Aggiungi**. 
    
    ![Aggiungere tag di conservazione ai nuovi criteri di conservazione](media/d8e87176-0716-4238-9e6a-7c4af35541dc.png)
  
    > [!TIP]
    > È possibile selezionare più tag di conservazione tenendo premuto il tasto **CTRL** e facendo clic su ogni tag. 
  
6. Dopo aver aggiunto i tag di conservazione, fare clic su **OK**.
    
7. Nella pagina **nuovo criterio di conservazione** , fare clic su **Salva** per creare il nuovo criterio. 
    
    Il nuovo criterio di conservazione viene visualizzato nell'elenco. Selezionarla per visualizzare i tag di conservazione a esso collegati nel riquadro dei dettagli.
    
    ![I nuovi criteri di conservazione e l'elenco dei tag di conservazione collegati](media/63bc45e6-110b-4dc9-a85f-8eb1961a8258.png)
  
## <a name="step-4-assign-the-new-retention-policy-to-user-mailboxes"></a>Passaggio 4: assegnare il nuovo criterio di conservazione alle cassette postali degli utenti

Quando viene creata una nuova cassetta postale, per impostazione predefinita viene assegnato un criterio di conservazione denominato criterio di gestione record di messaggistica predefinito. In questo passaggio, si sostituirà questo criterio di conservazione, in quanto una cassetta postale può disporre di un solo criterio di conservazione assegnato, assegnando il nuovo criterio di conservazione creato nel passaggio 3 alle cassette postali utente nell'organizzazione. In questo passaggio si presuppone che il nuovo criterio venga assegnato a tutte le cassette postali dell'organizzazione.
  
1. Nell'interfaccia di amministrazione di Exchange, accedere a **Destinatari** \> **Cassette postali**.
    
    Viene visualizzato un elenco di tutte le cassette postali utente nell'organizzazione. 
    
2. Seleziona tutte le cassette postali facendo clic sul primo nell'elenco, tenendo premuto il tasto **MAIUSC** e facendo clic sull'ultimo nell'elenco. 
    
3. Nel riquadro dei dettagli a destra dell'interfaccia di amministrazione di Exchange, in **modifica in blocco**, fare clic su **altre opzioni**.
    
4. In **Criterio di conservazione**, fare clic su **Aggiorna**.
    
5. Nell'elenco a discesa **selezionare** il criterio di conservazione della pagina **Assegna criteri** di conservazione in blocco selezionare i criteri di conservazione creati nel passaggio 3. ad esempio, i **criteri di conservazione e archiviazione delle case alpine**.
    
6. Fare clic su **Salva** per salvare la nuova assegnazione dei criteri di conservazione. 
    
7. Per verificare che i nuovi criteri di conservazione siano stati assegnati alle cassette postali, è possibile eseguire le operazioni seguenti: selezionare una cassetta postale nella pagina cassette postali, quindi fare clic su modifica. 
    
1. Selezionare una cassetta postale nella pagina **cassette postali** , quindi fare clic](media/d7dc7e5f-17a1-4eb9-b42d-487db59e2e21.png)su **modifica** ![modifica. 
    
2. Nella pagina delle proprietà della cassetta postale per l'utente selezionato, fare clic su **funzionalità cassette postali**.
    
    Il nome del nuovo criterio assegnato alla cassetta postale viene visualizzato nell'elenco a discesa **criteri di conservazione** . 

## <a name="optional-step-5-run-the-managed-folder-assistant-to-apply-the-new-settings"></a>Optional Passaggio 5: eseguire l'Assistente cartelle gestite per applicare le nuove impostazioni

Dopo aver applicato il nuovo criterio di conservazione alle cassette postali nel passaggio 4, è possibile che siano necessari fino a 7 giorni in Exchange Online per applicare le nuove impostazioni di conservazione alle cassette postali. Ciò è dovuto al fatto che un processo denominato Assistente cartelle gestite elabora le cassette postali una volta ogni 7 giorni. Invece di attendere l'esecuzione dell'Assistente cartelle gestite, è possibile forzare la procedura eseguendo il cmdlet **Start-ManagedFolderAssistant** in PowerShell di Exchange Online. 
  
 **Cosa succede quando si esegue l'Assistente cartelle gestite?** Applica le impostazioni nel criterio di conservazione esaminando gli elementi nella cassetta postale e determinando se sono soggetti alla conservazione. Vengono quindi timbrati gli elementi soggetti alla conservazione con il tag di conservazione appropriato e quindi viene eseguita l'azione di conservazione specificata sugli elementi oltre l'età di conservazione. 
  
Di seguito sono riportati i passaggi per connettersi a Exchange Online PowerShell, quindi eseguire l'Assistente cartelle gestite in tutte le cassette postali dell'organizzazione.
  
1. Nel computer locale aprire Windows PowerShell ed eseguire il comando seguente.
    
    ```powershell
    $UserCredential = Get-Credential
    ```

    Nella finestra di dialogo **richiesta credenziali di Windows PowerShell** Digitare il nome utente e la password per l'account di amministratore globale di Office 365 e quindi fare clic su **OK**.
    
2. Eseguire il comando riportato di seguito.
    
    ```powershell
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    ```

3. Eseguire il comando riportato di seguito.
    
    ```powershell
    Import-PSSession $Session
    ```

4. Per verificare di essere connessi alla propria organizzazione Exchange Online, eseguire il seguente comando per visualizzare un elenco di tutte le cassette postali dell'organizzazione:
    
    ```powershell
    Get-Mailbox
    ```

    > [!NOTE]
    > Per ulteriori informazioni o se si riscontrano problemi di connessione per l'organizzazione di Exchange Online, vedere [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=517283). 
  
5. Eseguire i due comandi seguenti per avviare l'Assistente cartelle gestite per tutte le cassette postali degli utenti nell'organizzazione.
    
    ```powershell
    $Mailboxes = Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"}
    ```

    ```powershell
    $Mailboxes.Identity | Start-ManagedFolderAssistant
    ```

È tutto. È stato configurato un criterio di archiviazione e eliminazione per l'organizzazione della casa alpina.
  
## <a name="optional-step-6-make-the-new-retention-policy-the-default-for-your-organization"></a>Optional Passaggio 6: rendere il nuovo criterio di conservazione il valore predefinito per l'organizzazione

Nel passaggio 4, è necessario assegnare il nuovo criterio di conservazione alle cassette postali esistenti. Tuttavia, è possibile configurare Exchange online in modo che i nuovi criteri di conservazione vengano assegnati a nuove cassette postali create in futuro. A tale scopo, è possibile utilizzare PowerShell di Exchange Online per aggiornare il piano della cassetta postale predefinito dell'organizzazione. Un *piano per le cassette postali* è un modello che consente di configurare automaticamente le proprietà nelle nuove cassette postali.  In questo passaggio facoltativo è possibile sostituire il criterio di conservazione corrente assegnato al piano della cassetta postale (per impostazione predefinita, il criterio di gestione record di messaggistica predefinito) con il criterio di conservazione creato nel passaggio 3. Dopo aver aggiornato il piano della cassetta postale, il nuovo criterio di conservazione verrà assegnato a nuove cassette postali.

1. [Connettersi a PowerShell di Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=517283) o vedere passaggio 5.

2. Eseguire il seguente comando per visualizzare le informazioni sui piani delle cassette postali nell'organizzazione.

    ```powershell
    Get-MailboxPlan | Format-Table DisplayName,RetentionPolicy,IsDefault
    ```
    
    Tenere presente il piano della cassetta postale impostato come predefinito.

3. Eseguire il seguente comando per assegnare il nuovo criterio di conservazione creato nel passaggio 3, ad esempio il **criterio di conservazione e archiviazione delle case alpine**, nel piano della cassetta postale predefinito. In questo esempio si presuppone che il nome del piano della cassetta postale predefinito sia **ExchangeOnlineEnterprise**.

    ```powershell
    Set-MailboxPlan "ExchangeOnlineEnterprise" -RetentionPolicy "Alpine House Archive and Retention Policy"
    ```

4. È possibile rieseguire il comando riportato nel passaggio 2 per verificare che il criterio di conservazione assegnato al piano della cassetta postale predefinito sia stato modificato.

## <a name="more-information"></a>Altre informazioni

- Come viene calcolato il periodo di validità della conservazione? L'età di conservazione degli elementi della cassetta postale viene calcolata a partire dalla data di recapito o dalla data di creazione per gli elementi, ad esempio i messaggi Draft che non sono stati inviati ma che sono stati creati dall'utente. Quando Assistente cartelle gestite elabora gli elementi in una cassetta postale, applica una data di inizio e una data di scadenza a tutti gli elementi con tag di conservazione utilizzando l'azione di conservazione Elimina e consenti ripristino o Elimina definitivamente. Gli elementi con un tag di archiviazione vengono contrassegnati con una data di spostamento. 
    
- Nella tabella seguente sono disponibili ulteriori informazioni su ogni tag di conservazione aggiunto al criterio di conservazione personalizzato creato eseguendo la procedura descritta in questo argomento.
    
    |**Tag di conservazione**|**Cosa fa questo tag**|**Incorporato o personalizzato?**|**Tipo**|
    |:-----|:-----|:-----|:-----|
    |Casa Alpina 3 anni sposta nell'archivio  <br/> |Sposta gli elementi di 1095 giorni (3 anni) nella cassetta postale di archiviazione.  <br/> |Personalizzato (vedere [il passaggio 2: creare nuovi tag di conservazione per i criteri di eliminazione e di archiviazione](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies))  <br/> |Tag del criterio predefinito (Archivio); Questo tag viene applicato automaticamente all'intera cassetta postale.  <br/> |
    |Casa Alpina 7 anni Elimina definitivamente  <br/> |Elimina definitivamente gli elementi nella cassetta postale principale o nella cassetta postale di archiviazione quando hanno 7 anni.  <br/> |Personalizzato (vedere [il passaggio 2: creare nuovi tag di conservazione per i criteri di eliminazione e di archiviazione](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies))  <br/> |Tag dei criteri predefiniti (soppressione); Questo tag viene applicato automaticamente all'intera cassetta postale.  <br/> |
    |Casa Alpina elementi eliminati 5 anni eliminare e consentire il ripristino  <br/> |Elimina gli elementi dalla cartella Posta eliminata di 5 anni. Gli utenti possono recuperare questi elementi per un massimo di 14 giorni dopo l'eliminazione.<sup>\*</sup> <br/> |Personalizzato (vedere [il passaggio 2: creare nuovi tag di conservazione per i criteri di eliminazione e di archiviazione](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies))  <br/> |Tag del criterio di conservazione (elementi eliminati); Questo tag viene applicato automaticamente agli elementi nella cartella Posta eliminata.  <br/> |
    |Spostamento nell'archivio degli elementi ripristinabili 14 giorni  <br/> |Sposta gli elementi che sono stati nella cartella elementi ripristinabili per 14 giorni nella cartella elementi ripristinabili nella cassetta postale di archiviazione.  <br/> |Built-in  <br/> |Tag del criterio di conservazione (elementi ripristinabili); Questo tag viene applicato automaticamente agli elementi nella cartella elementi ripristinabili.  <br/> |
    |Posta indesiderata  <br/> |Elimina definitivamente gli elementi presenti nella cartella posta indesiderata per 30 giorni. Gli utenti possono recuperare questi elementi per un massimo di 14 giorni dopo l'eliminazione.<sup>\*</sup> <br/> |Built-in  <br/> |Tag del criterio di conservazione (posta indesiderata) Questo tag viene applicato automaticamente agli elementi contenuti nella cartella posta indesiderata.  <br/> |
    |Elimina dopo 1 mese  <br/> |Elimina definitivamente gli elementi di 30 giorni. Gli utenti possono recuperare questi elementi per un massimo di 14 giorni dopo l'eliminazione.<sup>\*</sup> <br/> |Built-in  <br/> |Personali Questo tag può essere applicato dagli utenti.  <br/> |
    |Elimina dopo 1 anno  <br/> |Elimina definitivamente gli elementi di 365 giorni. Gli utenti possono recuperare questi elementi per un massimo di 14 giorni dopo l'eliminazione.<sup>\*</sup> <br/> |Built-in  <br/> |Personali Questo tag può essere applicato dagli utenti.  <br/> |
    |Non eliminare mai  <br/> |Questo tag impedisce che gli elementi vengano eliminati da un criterio di conservazione.  <br/> |Built-in  <br/> |Personali Questo tag può essere applicato dagli utenti.  <br/> |
    |Sposta elementi personali in archivio dopo 1 anni  <br/> |Sposta gli elementi nella cassetta postale di archiviazione dopo 1 anno.  <br/> |Built-in  <br/> |Personali Questo tag può essere applicato dagli utenti.  <br/> |
   
    > <sup>\*</sup>Gli utenti possono utilizzare lo strumento Recupera elementi eliminati in Outlook e Outlook sul Web (in precedenza noto come Outlook Web App) per recuperare un elemento eliminato all'interno del periodo di conservazione degli elementi eliminati, che per impostazione predefinita è di 14 giorni in Exchange Online. Un amministratore può utilizzare Windows PowerShell per aumentare il periodo di conservazione degli elementi eliminati fino a un massimo di 30 giorni. Per ulteriori informazioni, vedere: [recuperare gli elementi eliminati in Outlook per Windows](https://support.office.com/article/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce) e [modificare il periodo di conservazione degli elementi eliminati per una cassetta postale in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=286940)
  
- Se si utilizza il tag di conservazione degli **elementi ripristinabili per 14 giorni** , viene liberato lo spazio di archiviazione nella cartella elementi ripristinabili nella cassetta postale principale dell'utente. Questo è utile quando la cassetta postale di un utente viene messa in attesa, il che significa che non è mai stata eliminata definitivamente la cassetta postale dell'utente. Senza spostare gli elementi nella cassetta postale di archiviazione, è possibile che venga raggiunta la quota di archiviazione per la cartella elementi ripristinabili nella cassetta postale principale. Per ulteriori informazioni su questo e su come evitarlo, vedere [aumentare la quota degli elementi ripristinabili per le cassette postali in blocco](https://go.microsoft.com/fwlink/p/?LinkId=786479).
