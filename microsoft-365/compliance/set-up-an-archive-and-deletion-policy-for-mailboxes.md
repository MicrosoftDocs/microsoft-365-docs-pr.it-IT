---
title: Configurare criteri di archiviazione ed eliminazione per le cassette postali in un'organizzazione
f1.keywords:
- NOCSH
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
- MET150
ms.assetid: ec3587e4-7b4a-40fb-8fb8-8aa05aeae2ce
ms.custom: seo-marvel-apr2020
description: Informazioni su come creare un criterio di archiviazione ed eliminazione in Microsoft 365 che sposta automaticamente gli elementi nella cassetta postale di archiviazione di un utente.
ms.openlocfilehash: cfe14b0821230831517e78ca6a56175a94d81eec
ms.sourcegitcommit: 8950d3cb0f3087be7105e370ed02c7a575d00ec2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "50597144"
---
# <a name="set-up-an-archive-and-deletion-policy-for-mailboxes-in-your-organization"></a>Configurare criteri di archiviazione ed eliminazione per le cassette postali in un'organizzazione

In Microsoft 365, gli amministratori possono creare criteri di archiviazione ed eliminazione che spostano automaticamente gli elementi nella cassetta postale di archiviazione di un utente ed eliminano automaticamente gli elementi dalla cassetta postale. L'amministratore esegue questa operazione creando un criterio di conservazione assegnato alle cassette postali e sposta gli elementi nella cassetta postale di archiviazione di un utente dopo un determinato periodo di tempo e che elimina anche gli elementi dalla cassetta postale dopo aver raggiunto un determinato limite di validità. Le regole effettive che determinano quali elementi vengono spostati o eliminati e quando ciò avviene sono denominati tag di conservazione. I tag di conservazione sono collegati a un criterio di conservazione, che a sua volta viene assegnato alla cassetta postale di un utente. Un tag di conservazione applica le impostazioni di conservazione a singoli messaggi e cartelle nella cassetta postale di un utente. Definisce per quanto tempo un messaggio rimane nella cassetta postale e quale azione viene eseguita quando il messaggio raggiunge il periodo di validità di conservazione specificato. Quando un messaggio raggiunge il periodo di conservazione, viene spostato nella cassetta postale di archiviazione dell'utente o viene eliminato.
  
I passaggi descritti in questo articolo configurano un criterio di archiviazione e conservazione per un'organizzazione fittizia denominata Alpine House. La configurazione di questo criterio include le attività seguenti:
  
- Abilitazione di una cassetta postale di archiviazione per ogni utente dell'organizzazione. Ciò fornisce agli utenti ulteriore spazio di archiviazione delle cassette postali ed è necessario in modo che un criterio di conservazione possa spostare gli elementi nella cassetta postale di archiviazione. Consente inoltre a un utente di archiviare le informazioni di archiviazione spostando gli elementi nella cassetta postale di archiviazione.

- Creazione di tre tag di conservazione personalizzati per eseguire le operazioni seguenti:

  - Sposta automaticamente gli elementi di 3 anni nella cassetta postale di archiviazione dell'utente. Lo spostamento degli elementi nella cassetta postale di archiviazione libera spazio nella cassetta postale principale di un utente.

  - Elimina automaticamente dalla cartella Posta eliminata gli elementi che hanno più di 5 anni. Ciò consente inoltre di liberare spazio nella cassetta postale principale dell'utente. Gli utenti avranno la possibilità di recuperare questi elementi, se necessario. Per ulteriori informazioni, vedere [la](#more-information) nota a piè di pagina nella sezione Ulteriori informazioni. 

  - Elimina automaticamente (e definitivamente) gli elementi che hanno 7 anni dalla cassetta postale principale e da quella di archiviazione. A causa delle normative di conformità, alcune organizzazioni devono conservare la posta elettronica per un determinato periodo di tempo. Una volta scaduto questo periodo di tempo, un'organizzazione potrebbe voler rimuovere definitivamente queste cassette postali utente degli elementi.

- Creazione di un nuovo criterio di conservazione e aggiunta dei nuovi tag di conservazione personalizzati. Inoltre, si aggiungeranno anche tag di conservazione incorporati al nuovo criterio di conservazione. Sono inclusi i tag personali che gli utenti possono assegnare agli elementi nella propria cassetta postale. Verrà inoltre aggiunto un tag di conservazione che sposta gli elementi dalla cartella Elementi ripristinabili nella cassetta postale principale dell'utente alla cartella Elementi ripristinabili nella cassetta postale di archiviazione. Ciò consente di liberare spazio nella cartella Elementi ripristinabili di un utente quando la cassetta postale viene messa in attesa.

È possibile seguire alcuni o tutti i passaggi descritti in questo articolo per configurare un criterio di archiviazione ed eliminazione per le cassette postali nell'organizzazione. Si consiglia di testare questo processo su alcune cassette postali prima di implementarlo in tutte le cassette postali dell'organizzazione.
  
## <a name="before-you-set-up-an-archive-and-deletion-policy"></a>Prima di configurare un criterio di archiviazione ed eliminazione

- Per eseguire i passaggi descritti in questo argomento, è necessario essere un amministratore globale dell'organizzazione. 

- Quando si crea un nuovo account utente e si assegna all'utente una licenza di Exchange Online, viene creata automaticamente una cassetta postale per l'utente. Quando viene creata, alla cassetta postale viene assegnato automaticamente un criterio di conservazione predefinito, denominato Criterio di gestione dei messaggistica predefinito. In questo articolo verrà creato un nuovo criterio di conservazione e quindi assegnato alle cassette postali degli utenti, sostituendo il criterio di gestione dei messaggistica predefinito. A una cassetta postale può essere assegnato un solo criterio di conservazione alla volta.

- Per ulteriori informazioni sui tag di conservazione e sui criteri di conservazione in Exchange Online, vedere [Tag di conservazione e criteri di conservazione.](https://go.microsoft.com/fwlink/p/?LinkId=404424)

## <a name="step-1-enable-archive-mailboxes-for-users"></a>Passaggio 1: abilitare le cassette postali di archiviazione per gli utenti

Il primo passaggio consiste nell'abilitare la cassetta postale di archiviazione per ogni utente dell'organizzazione. La cassetta postale di archiviazione di un utente deve essere abilitata in modo che un tag di conservazione con un'azione di conservazione "Sposta nell'archivio" possa spostare l'elemento dopo la scadenza del periodo di conservazione.
  
> [!NOTE]
> È possibile abilitare le cassette postali di archiviazione in qualsiasi momento durante questo processo, purché siano abilitate a un certo punto prima di completare il processo. Se una cassetta postale di archiviazione non è abilitata, non viene eseguita alcuna azione sugli elementi a cui è assegnato un criterio di archiviazione o eliminazione.
  
1. Passare a [https://protection.office.com](https://protection.office.com).

2. Accedere con l'account amministratore globale.
    
3. Nel Centro sicurezza & conformità passare a **Archivio governance** \> **delle informazioni.**

    Viene visualizzato un elenco delle cassette postali dell'organizzazione e se la cassetta postale di archiviazione corrispondente è abilitata o disabilitata.

4. Selezionare tutte le cassette postali facendo clic sulla prima  nell'elenco, tenendo premuto MAIUSC e quindi facendo clic sull'ultima nell'elenco.

    > [!TIP]
    > In questo passaggio si presuppone che non siano abilitate cassette postali di archiviazione. Se sono presenti cassette postali con l'archivio abilitato, tenere premuto il **tasto CTRL** e fare clic su ogni cassetta postale con una cassetta postale di archiviazione disabilitata. In or you can click the **Archive mailbox** column header to sort the rows based on whether the archive mailbox is enabled or disabled to make it easier to select mailboxes.
  
5. Nel riquadro dei dettagli, in **Modifica in blocco,** fare clic su **Abilita.**

    Viene visualizzato un avviso che indica che gli elementi più vecchi di due anni verranno spostati nella nuova cassetta postale di archiviazione. Ciò è dovuto al fatto che il criterio di conservazione predefinito assegnato a una nuova cassetta postale utente al momento della creazione ha un tag dei criteri predefiniti di archiviazione con un periodo di conservazione di 2 anni. Il tag dei criteri predefiniti di archiviazione personalizzato che verrà creato nel passaggio 2 ha un periodo di conservazione di 3 anni. Ciò significa che gli elementi di 3 anni o più verranno spostati nella cassetta postale di archiviazione.

6. Fare **clic su Sì** per chiudere il messaggio di avviso e avviare il processo per abilitare la cassetta postale di archiviazione per ogni cassetta postale selezionata.

7. Al termine del processo, fare clic **su** ![ Aggiorna per aggiornare ](../media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) l'elenco nella **pagina** Archivio.

    La cassetta postale di archiviazione è abilitata per tutti gli utenti dell'organizzazione.

    ![L'elenco delle cassette postali con la cassetta postale di archiviazione abilitata](../media/61a7cb97-1bed-4808-aa5f-b6b761cfa8de.png)

## <a name="step-2-create-new-retention-tags-for-the-archive-and-deletion-policies"></a>Passaggio 2: Creare nuovi tag di conservazione per i criteri di archiviazione ed eliminazione

In questo passaggio verranno creati i tre tag di conservazione personalizzati descritti in precedenza.
  
- Passaggio all'archivio di 3 anni di Alpine House (criterio di archiviazione personalizzato)

- Alpine House 7 Year Permanently Delete (custom deletion policy)

- Alpine House Deleted Items 5 Years Delete and Allow Recovery (tag personalizzato per la cartella Posta eliminata)

Per creare nuovi tag di conservazione, si utilizzerà l'interfaccia di amministrazione di Exchange (EAC) nell'organizzazione di Exchange Online. Assicurarsi di utilizzare la versione classica dell'interfaccia di amministrazione di Exchange.
  
1. Accedere e [https://admin.protection.outlook.com/ecp/](https://admin.protection.outlook.com/ecp/) accedere con le proprie credenziali.
  
2. Nell'interfaccia di amministrazione di Exchange, accedere ai **tag di conservazione della gestione** della  >  **conformità**

    Viene visualizzato un elenco dei tag di conservazione per l'organizzazione.

### <a name="create-a-custom-archive-default-policy-tag"></a>Creare un tag dei criteri predefiniti di archiviazione personalizzato
  
Prima di tutto, si creerà un tag dei criteri predefiniti di archiviazione personalizzato (DPT) che sposta gli elementi nella cassetta postale di archiviazione dopo 3 anni.
  
1. Nella pagina **Tag di conservazione** fare clic sull'icona Nuovo **tag** nuovo e quindi selezionare applicato automaticamente all'intera cassetta postale ![ ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) **(impostazione predefinita).**

2. Nella pagina **Nuovo tag applicato automaticamente all'intera cassetta postale (impostazione predefinita),** completare i seguenti campi: 

    ![Impostazioni per creare un nuovo tag dei criteri predefiniti di archiviazione](../media/41c0a43c-9c72-44e0-8947-da0831896432.png)
  
   1. **Nome** Digitare un nome per il nuovo tag di conservazione. 

   2. **Azione di conservazione** Selezionare **Sposta nell'archivio** per spostare gli elementi nella cassetta postale di archiviazione alla scadenza del periodo di conservazione.

   3. **Periodo di conservazione** Selezionare **Quando l'elemento raggiunge il periodo di** validità seguente (in giorni) e quindi immettere la durata del periodo di conservazione. Per questo scenario, gli elementi verranno spostati nella cassetta postale di archiviazione dopo 1095 giorni (3 anni).

   4. **Commento** (facoltativo) Digitare un commento che spieghi lo scopo del tag di conservazione personalizzato.

3. Fare **clic su** Salva per creare il DPT di archiviazione personalizzato.

    Il nuovo tag DPT di archiviazione viene visualizzato nell'elenco dei tag di conservazione.

### <a name="create-a-custom-deletion-default-policy-tag"></a>Creare un tag dei criteri predefiniti per l'eliminazione personalizzato
  
Successivamente, creerai un altro DPT personalizzato, ma questo sarà un criterio di eliminazione che elimina definitivamente gli elementi dopo 7 anni.
  
1. Nella pagina **Tag di conservazione** fare clic sull'icona Nuovo **tag** nuovo e quindi selezionare applicato automaticamente all'intera cassetta postale ![ ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) **(impostazione predefinita).**

2. Nella pagina **Nuovo tag applicato automaticamente all'intera cassetta postale (impostazione predefinita),** completare i seguenti campi: 

    ![Impostazioni per creare un nuovo tag dei criteri predefiniti di eliminazione](../media/f1f0ff62-eec9-4824-8e7c-d93dcfb09a79.png)
  
   1. **Nome** Digitare un nome per il nuovo tag di conservazione. 

   2. **Azione di conservazione** Selezionare **Elimina definitivamente per** eliminare gli elementi dalla cassetta postale alla scadenza del periodo di conservazione.

   3. **Periodo di conservazione** Selezionare **Quando l'elemento raggiunge il periodo di** validità seguente (in giorni) e quindi immettere la durata del periodo di conservazione. Per questo scenario, gli elementi verranno eliminati dopo 2555 giorni (7 anni).

   4. **Commento** (facoltativo) Digitare un commento che spieghi lo scopo del tag di conservazione personalizzato. 

3. Fare **clic su** Salva per creare il DPT di eliminazione personalizzato. 

    Il nuovo tag DPT di eliminazione viene visualizzato nell'elenco dei tag di conservazione.

### <a name="create-a-custom-retention-policy-tag-for-the-deleted-items-folder"></a>Creare un tag dei criteri di conservazione personalizzato per la cartella Posta eliminata
  
L'ultimo tag di conservazione che verrà creato è un tag dei criteri di conservazione personalizzato per la cartella Posta eliminata. Questo tag eliminerà gli elementi nella cartella Posta eliminata dopo 5 anni e fornisce un periodo di ripristino in cui gli utenti possono utilizzare lo strumento Recupera posta eliminata per ripristinare un elemento.
  
1. Nella pagina **Tag di conservazione** fare clic **sull'icona** Nuovo tag nuovo e quindi selezionare applicato ![ ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) **automaticamente a una cartella predefinita.**

2. Nella pagina **Nuovo tag applicato automaticamente a una cartella** predefinita, completare i campi seguenti:

    ![Impostazioni per creare un nuovo tag dei criteri di conservazione per la cartella Posta eliminata](../media/6f3104bd-5edb-48ac-884d-5fe13d81dd1d.png)
  
   1. **Nome** Digitare un nome per il nuovo tag di conservazione. 

   2. **Applica questo tag alla cartella predefinita seguente** Nell'elenco a discesa selezionare **Posta eliminata.**

   3. **Azione di conservazione** Selezionare **Elimina** e Consenti ripristino per eliminare gli elementi alla scadenza del periodo di conservazione, ma consentire agli utenti di recuperare un elemento eliminato entro il periodo di conservazione degli elementi eliminati (che per impostazione predefinita è 14 giorni).

   4. **Periodo di conservazione** Selezionare **Quando l'elemento raggiunge il periodo di** validità seguente (in giorni) e quindi immettere la durata del periodo di conservazione. Per questo scenario, gli elementi verranno eliminati dopo 1825 giorni (5 anni).

   5. **Commento** (facoltativo) Digitare un commento che spieghi lo scopo del tag di conservazione personalizzato. 

3. Fare **clic** su Salva per creare il RPT personalizzato per la cartella Posta eliminata.

    Il nuovo tag RPT viene visualizzato nell'elenco dei tag di conservazione.

## <a name="step-3-create-a-new-retention-policy"></a>Passaggio 3: Creare un nuovo criterio di conservazione

Dopo aver creato i tag di conservazione personalizzati, il passaggio successivo consiste nel creare un nuovo criterio di conservazione e aggiungere i tag di conservazione. Verranno aggiunti i tre tag di conservazione personalizzati creati nel passaggio 2 e i tag predefiniti menzionati nella prima sezione. Nel passaggio 4, si assegna questo nuovo criterio di conservazione alle cassette postali degli utenti.
  
1. Nell'interfaccia di amministrazione di Exchange, accedere a **Criteri di conservazione della gestione** della  >  **conformità.**

2. Nella pagina **Criteri di conservazione** fare clic **sull'icona** ![ ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) Nuovo.

3. Nella casella **Nome** digitare un nome per il nuovo criterio di conservazione. ad esempio, **l'archivio e i criteri di eliminazione di Alpine House.**

4. In **Tag di conservazione** fare clic **sull'icona** ![ Aggiungi ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) nuovo.

    Viene visualizzato un elenco dei tag di conservazione nell'organizzazione. Si noti che vengono visualizzati i tag personalizzati creati nel passaggio 2.

5. Aggiungere i 9 tag di conservazione evidenziati nello screenshot seguente (questi tag sono descritti in modo più dettagliato nella [sezione Ulteriori](#more-information) informazioni). Per aggiungere un tag di conservazione, selezionarlo e fare clic su **Aggiungi.**

    ![Aggiungere tag di conservazione al nuovo criterio di conservazione](../media/d8e87176-0716-4238-9e6a-7c4af35541dc.png)
  
    > [!TIP]
    > È possibile selezionare più tag di conservazione tenendo premuto **CTRL** e quindi facendo clic su ogni tag. 
  
6. Dopo aver aggiunto i tag di conservazione, fare clic su **OK.**

7. Nella pagina **Nuovi criteri di conservazione** fare clic su **Salva** per creare il nuovo criterio.

    Il nuovo criterio di conservazione viene visualizzato nell'elenco. Selezionarla per visualizzare i tag di conservazione collegati nel riquadro dei dettagli.

    ![Il nuovo criterio di conservazione e l'elenco dei tag di conservazione collegati](../media/63bc45e6-110b-4dc9-a85f-8eb1961a8258.png)
  
## <a name="step-4-assign-the-new-retention-policy-to-user-mailboxes"></a>Passaggio 4: Assegnare il nuovo criterio di conservazione alle cassette postali degli utenti

Quando viene creata una nuova cassetta postale, per impostazione predefinita viene assegnato un criterio di conservazione denominato Criterio di gestione dei messaggistica predefinito. In questo passaggio, questo criterio di conservazione verrà sostituito (poiché a una cassetta postale può essere assegnato un solo criterio di conservazione) assegnando il nuovo criterio di conservazione creato nel passaggio 3 alle cassette postali degli utenti nell'organizzazione. In questo passaggio si presuppone che il nuovo criterio verrà assegnato a tutte le cassette postali dell'organizzazione.
  
1. Nell'interfaccia di amministrazione di Exchange, accedere a **Cassette postali dei**  >  **destinatari.**

    Viene visualizzato un elenco di tutte le cassette postali utente dell'organizzazione.

2. Selezionare tutte le cassette postali facendo clic sulla prima  nell'elenco, tenendo premuto MAIUSC e quindi facendo clic sull'ultima nell'elenco. 

3. Nel riquadro dei dettagli sul lato destro dell'interfaccia di amministrazione di Exchange, in **Modifica in blocco,** fare clic **su Altre opzioni.**

4. In **Criterio di conservazione**, fare clic su **Aggiorna**.

5. Nella pagina **Assegnazione in** blocco  dei criteri di conservazione, nell'elenco a discesa Selezionare il criterio di conservazione, selezionare il criterio di conservazione creato nel passaggio 3. ad esempio, **l'archivio e i criteri di conservazione di Alpine House.**

6. Fare **clic su Salva** per salvare la nuova assegnazione dei criteri di conservazione.

7. Per verificare che il nuovo criterio di conservazione sia stato assegnato alle cassette postali, è possibile eseguire le operazioni seguenti:

   1. Selezionare una cassetta postale nella pagina **Cassette** postali, quindi fare clic **su Modifica** ![ ](../media/d7dc7e5f-17a1-4eb9-b42d-487db59e2e21.png) modifica.

   2. Nella pagina delle proprietà della cassetta postale per l'utente selezionato, fare clic su **Funzionalità cassetta postale.**

   Il nome del nuovo criterio assegnato alla cassetta postale viene visualizzato nell'elenco **a** discesa Criterio di conservazione.

## <a name="optional-step-5-run-the-managed-folder-assistant-to-apply-the-new-settings"></a>(Facoltativo) Passaggio 5: Eseguire l'Assistente cartelle gestite per applicare le nuove impostazioni

Dopo aver applicato il nuovo criterio di conservazione alle cassette postali nel passaggio 4, possono essere necessario fino a 7 giorni in Exchange Online per applicare le nuove impostazioni di conservazione alle cassette postali. Questo perché un processo  denominato Assistente cartelle gestite elabora le cassette postali almeno una volta ogni 7 giorni. Anziché attendere l'esecuzione dell'Assistente cartelle gestite, è possibile forzare questa operazione eseguendo il cmdlet **Start-ManagedFolderAssistant** in PowerShell di Exchange Online.

 **Cosa succede quando si esegue l'Assistente cartelle gestite?** Applica le impostazioni nel criterio di conservazione esaminando gli elementi nella cassetta postale e determinando se sono soggetti alla conservazione. Contrassegna quindi gli elementi soggetti alla conservazione con il tag di conservazione appropriato e quindi utilizza l'azione di conservazione specificata sugli elementi che hanno più di un periodo di conservazione.
  
Ecco la procedura per connettersi a PowerShell di Exchange Online e quindi eseguire l'Assistente cartelle gestite in ogni cassetta postale dell'organizzazione.

1. [Connettersi a PowerShell per Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=517283).
  
2. Eseguire i due comandi seguenti per avviare l'Assistente cartelle gestite per tutte le cassette postali degli utenti nell'organizzazione.

    ```powershell
    $Mailboxes = Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"}
    ```

    ```powershell
    $Mailboxes.Identity | Start-ManagedFolderAssistant
    ```

È tutto. È stato configurato un criterio di archiviazione ed eliminazione per l'organizzazione di Alpine House.

> [!NOTE]
> Come indicato in precedenza, l'Assistente cartelle gestite elabora le cassette postali almeno una volta ogni 7 giorni. Pertanto, è possibile che una cassetta postale possa essere elaborata più frequentemente dall'Assistente cartelle gestite. Inoltre, gli amministratori non possono prevedere la successiva elaborazione di una cassetta postale da parte dell'Assistente cartelle gestite, che è uno dei motivi per cui è possibile eseguirla manualmente. Tuttavia, se si desidera impedire temporaneamente all'Assistente cartelle gestite di applicare le nuove impostazioni di conservazione a una cassetta postale, è possibile eseguire il comando per disabilitare temporaneamente l'elaborazione di una cassetta postale da parte dell'Assistente cartelle `Set-Mailbox -ElcProcessingDisabled $true` gestite. Per abilitare nuovamente l'Assistente cartelle gestite per una cassetta postale, eseguire il `Set-Mailbox -ElcProcessingDisabled $false` comando. Infine, se un utente della cassetta postale dispone di un account disabilitato, non verranno elaborati gli elementi di spostamento nell'azione di archiviazione per tale cassetta postale.
  
## <a name="optional-step-6-make-the-new-retention-policy-the-default-for-your-organization"></a>(Facoltativo) Passaggio 6: Impostare il nuovo criterio di conservazione come predefinito per l'organizzazione

Nel passaggio 4, è necessario assegnare il nuovo criterio di conservazione alle cassette postali esistenti. Tuttavia, è possibile configurare Exchange Online in modo che il nuovo criterio di conservazione sia assegnato alle nuove cassette postali create in futuro. A tale scopo, utilizzare PowerShell di Exchange Online per aggiornare il piano delle cassette postali predefinito dell'organizzazione. Un *piano della cassetta* postale è un modello che configura automaticamente le proprietà delle nuove cassette postali.  In questo passaggio facoltativo, è possibile sostituire il criterio di conservazione corrente assegnato al piano della cassetta postale (per impostazione predefinita, il criterio di gestione record di messaggistica predefinito) con il criterio di conservazione creato nel passaggio 3. Dopo aver aggiornato il piano della cassetta postale, il nuovo criterio di conservazione verrà assegnato alle nuove cassette postali.

1. [Connettersi a PowerShell per Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=517283).

2. Eseguire il seguente comando per visualizzare informazioni sui piani delle cassette postali nell'organizzazione.

    ```powershell
    Get-MailboxPlan | Format-Table DisplayName,RetentionPolicy,IsDefault
    ```

    Si noti il piano della cassetta postale impostato come predefinito.

3. Eseguire il seguente comando per assegnare il nuovo criterio di conservazione creato nel passaggio 3 (ad esempio, **l'archivio di Alpine House** e il criterio di conservazione) al piano della cassetta postale predefinito. In questo esempio si presuppone che il nome del piano della cassetta postale predefinito sia **ExchangeOnlineEnterprise.**

    ```powershell
    Set-MailboxPlan "ExchangeOnlineEnterprise" -RetentionPolicy "Alpine House Archive and Retention Policy"
    ```

4. È possibile eseguire di nuovo il comando nel passaggio 2 per verificare che il criterio di conservazione assegnato al piano della cassetta postale predefinito sia stato modificato.

## <a name="more-information"></a>Ulteriori informazioni

- Come viene calcolato il periodo di validità della conservazione? Il periodo di validità della conservazione degli elementi della cassetta postale viene calcolato a partire dalla data di recapito o dalla data di creazione per elementi quali bozze di messaggi non inviati ma creati dall'utente. Quando Assistente cartelle gestite elabora gli elementi in una cassetta postale, applica una data di inizio e una data di scadenza a tutti gli elementi con tag di conservazione utilizzando l'azione di conservazione Elimina e consenti ripristino o Elimina definitivamente. Gli elementi con un tag di archiviazione vengono contrassegnati con una data di spostamento. 

- Nella tabella seguente sono disponibili ulteriori informazioni su ogni tag di conservazione aggiunto al criterio di conservazione personalizzato creato seguendo i passaggi descritti in questo argomento.

    | Tag di conservazione | Scopo del tag | Incorporato o personalizzato? | Tipo |
    |:-----|:-----|:-----|:-----|
    |Trasferimento all'archivio di Alpine House per 3 anni  <br/> |Sposta gli elementi vecchi di 1095 giorni (3 anni) nella cassetta postale di archiviazione.  <br/> |Personalizzato (vedere [Passaggio 2: Creare nuovi tag di conservazione per i criteri di archiviazione ed eliminazione)](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies)  <br/> |Tag criterio predefinito (archivio); questo tag viene applicato automaticamente all'intera cassetta postale.  <br/> |
    |Alpine House 7 Year Permanently Delete  <br/> |Elimina definitivamente gli elementi nella cassetta postale principale o nella cassetta postale di archiviazione quando hanno 7 anni.  <br/> |Personalizzato (vedere [Passaggio 2: Creare nuovi tag di conservazione per i criteri di archiviazione ed eliminazione)](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies)  <br/> |Tag criterio predefinito (eliminazione); questo tag viene applicato automaticamente all'intera cassetta postale.  <br/> |
    |Alpine House Deleted Items 5 Years Delete and Allow Recovery  <br/> |Elimina gli elementi dalla cartella Posta eliminata che hanno 5 anni. Gli utenti possono ripristinare questi elementi per un massimo di 14 giorni dopo l'eliminazione.<sup>\*</sup> <br/> |Personalizzato (vedere [Passaggio 2: Creare nuovi tag di conservazione per i criteri di archiviazione ed eliminazione)](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies)  <br/> |Tag dei criteri di conservazione (elementi eliminati); questo tag viene applicato automaticamente agli elementi nella cartella Posta eliminata.  <br/> |
    |Sposta elementi ripristinabili 14 giorni nell'archivio  <br/> |Sposta gli elementi presenti nella cartella Elementi ripristinabili per 14 giorni nella cartella Elementi ripristinabili nella cassetta postale di archiviazione.  <br/> |Built-in  <br/> |Tag dei criteri di conservazione (elementi ripristinabili); questo tag viene applicato automaticamente agli elementi nella cartella Elementi ripristinabili.  <br/> |
    |Posta indesiderata  <br/> |Elimina definitivamente gli elementi presenti nella cartella Posta indesiderata per 30 giorni. Gli utenti possono ripristinare questi elementi per un massimo di 14 giorni dopo l'eliminazione.<sup>\*</sup> <br/> |Built-in  <br/> |Tag dei criteri di conservazione (posta indesiderata); Questo tag viene applicato automaticamente agli elementi nella cartella Posta indesiderata.  <br/> |
    |Elimina dopo 1 mese  <br/> |Elimina definitivamente gli elementi vecchi di 30 giorni. Gli utenti possono ripristinare questi elementi per un massimo di 14 giorni dopo l'eliminazione.<sup>\*</sup> <br/> |Built-in  <br/> |Personale; questo tag può essere applicato dagli utenti.  <br/> |
    |Elimina dopo 1 anno  <br/> |Elimina definitivamente gli elementi vecchi di 365 giorni. Gli utenti possono ripristinare questi elementi per un massimo di 14 giorni dopo l'eliminazione.<sup>\*</sup> <br/> |Built-in  <br/> |Personale; questo tag può essere applicato dagli utenti.  <br/> |
    |Non eliminare mai  <br/> |Questo tag impedisce l'eliminazione degli elementi tramite un criterio di conservazione.  <br/> |Built-in  <br/> |Personale; questo tag può essere applicato dagli utenti.  <br/> |
    |Sposta elementi personali in archivio dopo 1 anni  <br/> |Sposta gli elementi nella cassetta postale di archiviazione dopo 1 anno.  <br/> |Built-in  <br/> |Personale; questo tag può essere applicato dagli utenti.  <br/> |

    > <sup>\*</sup> Gli utenti possono utilizzare lo strumento Recupera posta eliminata in Outlook e Outlook sul Web (in precedenza noto come Outlook Web App) per recuperare un elemento eliminato entro il periodo di conservazione degli elementi eliminati, che per impostazione predefinita è di 14 giorni in Exchange Online. Un amministratore può utilizzare Windows PowerShell per aumentare il periodo di conservazione degli elementi eliminati a un massimo di 30 giorni. Per ulteriori informazioni, vedere: Recuperare gli elementi eliminati [in Outlook per Windows](https://support.office.com/article/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce) e modificare il periodo di conservazione degli elementi eliminati per una cassetta postale in Exchange [Online](https://www.microsoft.com/?ref=go)
  
- L'utilizzo del tag di conservazione Sposta in archivio per **14** giorni degli elementi ripristinabili consente di liberare spazio di archiviazione nella cartella Elementi ripristinabili nella cassetta postale principale dell'utente. Ciò è utile quando la cassetta postale di un utente viene messa in attesa, il che significa che non viene mai eliminata definitivamente la cassetta postale dell'utente. Senza spostare gli elementi nella cassetta postale di archiviazione, è possibile che la quota di archiviazione per la cartella Elementi ripristinabili nella cassetta postale principale sia raggiunta. Per ulteriori informazioni su questo e su come evitarlo, vedere Aumentare la [quota elementi ripristinabili per le cassette postali in attesa.](https://go.microsoft.com/fwlink/p/?LinkId=786479)
