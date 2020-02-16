---
title: Aumentare la quota degli elementi ripristinabili per le cassette postali bloccate
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/12/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a8bdcbdd-9298-462f-b889-df26037a990c
description: "Abilitare la cassetta postale di archiviazione e attivare l'archiviazione automatica per aumentare le dimensioni della cartella elementi ripristinabili per una cassetta postale in Office 365. "
ms.openlocfilehash: 37d0e783f3b3a5157fe4a7a9b7d512b09c05d32c
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42072925"
---
# <a name="increase-the-recoverable-items-quota-for-mailboxes-on-hold"></a>Aumentare la quota degli elementi ripristinabili per le cassette postali bloccate

I criteri di conservazione predefiniti, denominati criteri di gestione record di messaggistica predefinita, che vengono applicati automaticamente alle nuove cassette postali in Exchange Online, contengono un tag di conservazione denominato elementi ripristinabili 14 giorni di spostamento in archivio. Questo tag di conservazione Sposta gli elementi dalla cartella elementi ripristinabili nella cassetta postale principale dell'utente alla cartella elementi ripristinabili nella cassetta postale di archiviazione dell'utente dopo la scadenza del periodo di conservazione di 14 giorni per un elemento. Affinché ciò accada, la cassetta postale di archiviazione dell'utente deve essere abilitata. Se la cassetta postale di archiviazione non è abilitata, non viene eseguita alcuna azione, ovvero gli elementi della cartella elementi ripristinabili per una cassetta postale in attesa non vengono spostati nella cassetta postale di archiviazione dopo la scadenza del periodo di conservazione di 14 giorni. Poiché non viene eliminato nulla da una cassetta postale in attesa, è possibile che la quota di archiviazione per la cartella elementi ripristinabili venga superata, soprattutto se la cassetta postale di archiviazione dell'utente non è abilitata. 
  
Per ridurre la possibilità di superare questo limite, la quota di archiviazione per la cartella elementi ripristinabili viene automaticamente aumentata da 30 GB a 100 GB quando viene inserita una cassetta postale in Exchange Online. Se la cassetta postale di archiviazione è abilitata, è aumentata anche la quota per la cartella elementi ripristinabili nella cassetta postale di archiviazione da 30 GB a 100 GB. Se la funzionalità di archiviazione in espansione automatica in Exchange Online è abilitata, la quota di archiviazione per la cartella elementi ripristinabili nell'archivio dell'utente sarà illimitata.
  
 Nella tabella seguente viene riepilogata la quota di archiviazione per la cartella elementi ripristinabili. 
  
|**Percorso della cartella elementi ripristinabili**|**Cassette postali non in attesa**|**Cassette postali in blocco**|
|:-----|:-----|:-----|
|Cassetta postale principale  <br/> |30 GB  <br/> |100 GB  <br/> |
|Cassetta postale di archiviazione<sup>\*</sup> <br/> |Illimitata  <br/> |Illimitata  <br/> |
|**Quota di archiviazione totale per la cartella elementi ripristinabili** <br/> |Illimitata  <br/> |Illimitata  <br/> |
   
> [!NOTE]
> <sup>\*</sup>La quota di archiviazione iniziale per la cassetta postale di archivio è di 100 GB per gli utenti con una licenza di Exchange Online (piano 2). Tuttavia, quando l'archiviazione in espansione automatica è attivata per le cassette postali in blocco, la quota di archiviazione per la cassetta postale di archivio e la cartella elementi ripristinabili viene aumentata a 110 GB. Se necessario, verrà eseguito il provisioning di un ulteriore spazio di archiviazione dell'archivio, che consentirà di ottenere un numero illimitato di archiviazione. Per ulteriori informazioni sull'archiviazione automatica, vedere [Overview of Unlimited Archiving in Office 365](unlimited-archiving.md). 
  
Quando la quota di archiviazione per la cartella elementi ripristinabili nella cassetta postale principale di una cassetta postale in attesa è vicina al raggiungimento del limite, è possibile eseguire le operazioni seguenti:
  
- **Abilitazione della cassetta postale** di archiviazione e attivazione dell'archiviazione automatica-è possibile abilitare una capacità illimitata di archiviazione per la cartella elementi ripristinabili semplicemente abilitando la cassetta postale di archiviazione e quindi attivando la caratteristica di archiviazione in espansione automatica in Exchange Online. Ciò comporta 110 GB per la cartella elementi ripristinabili nella cassetta postale principale e una quantità illimitata di capacità di archiviazione per la cartella elementi ripristinabili nell'archivio dell'utente. Vedere come: [abilitare le cassette postali di archiviazione nel centro sicurezza & Compliance](enable-archive-mailboxes.md) e [abilitare l'archiviazione illimitata in Office 365](enable-unlimited-archiving.md).
    
    > [!NOTE]
    > Dopo aver abilitato l'archivio per una cassetta postale vicina al superamento della quota di archiviazione per la cartella elementi ripristinabili, potrebbe essere necessario eseguire l'Assistente cartelle gestite per attivare manualmente l'assistente per elaborare la cassetta postale in modo che gli elementi scaduti vengano spostati nell' Cartella elementi ripristinabili nella cassetta postale di archiviazione. Per istruzioni, vedere [passaggio 4](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings) . Tenere presente che gli altri elementi della cassetta postale dell'utente possono essere spostati nella nuova cassetta postale di archiviazione. È consigliabile informare l'utente che può verificarsi dopo aver abilitato la cassetta postale di archiviazione. 
  
- **Creare un criterio di conservazione personalizzato per le cassette postali in attesa** -oltre che per abilitare la cassetta postale di archiviazione e l'archiviazione automatica per le cassette postali in blocco per controversia legale o in blocco sul posto, potrebbe essere necessario creare un criterio di conservazione personalizzato per le cassette postali in attesa. In questo modo è possibile applicare un criterio di conservazione alle cassette postali in blocco che differiscono dal criterio di gestione record di messaggistica predefinito applicato alle cassette postali che non sono in attesa. In questo modo è possibile applicare i tag di conservazione appositamente progettati per le cassette postali in blocco. Questo include la creazione di un nuovo tag di conservazione per la cartella elementi ripristinabili. 
    
Nella parte restante di questo argomento vengono descritte le procedure dettagliate per creare un criterio di conservazione personalizzato per le cassette postali in blocco.
  
[Passaggio 1: creare un tag di conservazione personalizzato per la cartella elementi ripristinabili](#step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder)

[[Passaggio 2: creare un nuovo criterio di conservazione per le cassette postali in blocco](#step-2-create-a-new-retention-policy-for-mailboxes-on-hold)

[Passaggio 3: applicare il nuovo criterio di conservazione alle cassette postali in blocco](#step-3-apply-the-new-retention-policy-to-mailboxes-on-hold)

[Optional Passaggio 4: eseguire l'Assistente cartelle gestite per applicare le nuove impostazioni di conservazione](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings)
  
## <a name="step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder"></a>Passaggio 1: creare un tag di conservazione personalizzato per la cartella elementi ripristinabili

Il primo passaggio consiste nel creare un tag di conservazione personalizzato (denominato tag dei criteri di conservazione o RPT) per la cartella elementi ripristinabili. Come spiegato in precedenza, questo RPT sposta gli elementi dalla cartella elementi ripristinabili nella cassetta postale principale dell'utente alla cartella elementi ripristinabili nella cassetta postale di archiviazione dell'utente. È necessario utilizzare PowerShell per creare un RPT per la cartella elementi ripristinabili. Non è possibile usare l'interfaccia di amministrazione di Exchange (EAC). 
  
1. [Connettersi a Exchange Online tramite la sessione remota di PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=517283)
    
2. Eseguire il seguente comando per creare un nuovo RPT per la cartella elementi ripristinabili: 
    
    ```powershell
    New-RetentionPolicyTag -Name <Name of RPT> -Type RecoverableItems -AgeLimitForRetention <Number of days> -RetentionAction MoveToArchive
    ```

    Ad esempio, il comando seguente crea un RPT per la cartella elementi ripristinabili denominata "elementi ripristinabili 30 giorni per le cassette postali in attesa", con un periodo di conservazione di 30 giorni. Ciò significa che, dopo che un elemento è stato nella cartella elementi ripristinabili per 30 giorni, verrà spostato nella cartella elementi ripristinabili nella cassetta postale di archiviazione dell'utente.
    
    ```powershell
    New-RetentionPolicyTag -Name "Recoverable Items 30 days for mailboxes on hold" -Type RecoverableItems -AgeLimitForRetention 30 -RetentionAction MoveToArchive
    ```

    > [!TIP]
    > È consigliabile che il periodo di conservazione (definito dal parametro _AgeLimitForRetention_ ) per gli elementi ripristinabili sia lo stesso del periodo di conservazione per le cassette postali a cui verrà applicato il RPT. In questo modo un utente può recuperare il periodo di conservazione degli elementi eliminati prima che vengano spostati nella cassetta postale di archiviazione. Nell'esempio precedente, il periodo di conservazione è stato impostato su 30 giorni in base all'ipotesi che il periodo di conservazione degli elementi eliminati per le cassette postali sia anche di 30 giorni. Per impostazione predefinita, una cassetta postale di Exchange Online è configurata per mantenere gli elementi eliminati per 14 giorni. Tuttavia, è possibile modificare questa impostazione fino a un massimo di 30 giorni. Per ulteriori informazioni, vedere [modificare il periodo di conservazione degli elementi eliminati per una cassetta postale in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=286940). 
  
## <a name="step-2-create-a-new-retention-policy-for-mailboxes-on-hold"></a>Passaggio 2: creare un nuovo criterio di conservazione per le cassette postali in blocco

Il passaggio successivo consiste nel creare un nuovo criterio di conservazione e nel aggiungere tag di conservazione, inclusi gli elementi ripristinabili che sono stati creati nel passaggio 1. Questo nuovo criterio verrà applicato alle cassette postali in attesa nel prossimo passaggio. 
  
Prima di creare il nuovo criterio di conservazione, determinare i tag di conservazione aggiuntivi che si desidera aggiungere. Per un elenco dei tag di conservazione aggiunti al criterio di gestione record di messaggistica predefinito e per informazioni sulla creazione di nuovi tag di conservazione, vedere gli argomenti seguenti:
  
- [Criteri di conservazione predefiniti di Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=746954)
    
- [Cartelle predefinite che supportano i tag di Criteri di conservazione](https://go.microsoft.com/fwlink/p/?LinkId=746957)
    
- La sezione "creare un tag di conservazione" nell'argomento [Create a Retention Policy](https://go.microsoft.com/fwlink/p/?LinkId=404422) .
    
È possibile utilizzare EAC o Exchange Online PowerShell per creare un criterio di conservazione.
  
### <a name="use-the-eac-to-create-a-retention-policy"></a>Creazione di un criterio di conservazione tramite l'interfaccia di amministrazione di Exchange
  
1. Nell'interfaccia di amministrazione di Exchange, accedere a **criteri di conservazione**per la **gestione** \> della conformità](../media/ITPro-EAC-AddIcon.gif)e quindi fare clic su **Aggiungi** ![icona Aggiungi.
    
2. Nella pagina **nuovo criterio di conservazione** , in **nome**, digitare un nome che descriva lo scopo del criterio di conservazione. ad esempio, i **criteri di gestione record di messaggistica per le cassette postali**. 
    
3. In **tag di conservazione**fare **** ![clic su Aggiungi](../media/ITPro-EAC-AddIcon.gif)icona Aggiungi.
    
4. Nell'elenco dei tag di conservazione, selezionare il RPT elementi ripristinabili creato nel passaggio 1, quindi fare clic su **Aggiungi**.
    
    ![Selezionare il tag di conservazione Elementi recuperabili personalizzato](../media/eb49866b-bdef-4fcd-a6d9-01607c01249b.png)
  
5. Selezionare i tag di conservazione aggiuntivi da aggiungere al criterio di conservazione. Ad esempio, potrebbe essere necessario aggiungere gli stessi tag inclusi nel criterio di gestione record di messaggistica predefinito.
    
6. Dopo aver aggiunto i tag di conservazione, fare clic su **OK**.
    
7. Fare clic su **Salva** per creare il nuovo criterio di conservazione. 
    
    Si noti che i tag di conservazione associati al criterio di conservazione vengono visualizzati nel riquadro dei dettagli.
    
    ![I tag di conversazione collegati al criterio di conservazione vengono visualizzati nel riquadro dei dettagli](../media/dad1c8f4-9928-4d6d-991a-6f6c5194eceb.png)
  
### <a name="use-exchange-online-powershell-to-create-a-retention-policy"></a>Utilizzare PowerShell di Exchange Online per creare un criterio di conservazione
  
Eseguire il seguente comando per creare nuovi criteri di conservazione per le cassette postali in blocco. 
  
```powershell
New-RetentionPolicy <Name of retention policy>  -RetentionPolicyTagLinks <list of retention tags>

```

Ad esempio, il comando seguente consente di creare i criteri di conservazione e i tag di conservazione collegati che vengono visualizzati nella figura precedente.
  
```powershell
New-RetentionPolicy "MRM Policy for Mailboxes on Hold"  -RetentionPolicyTagLinks "Recoverable Items 30 days for mailboxes on hold","1 Month Delete","1 Week Delete","1 Year Delete","5 Year Delete","6 Month Delete","Default 2 year move to archive","Junk Email","Never Delete","Personal 1 year move to archive","Personal 5 year move to archive"
```

## <a name="step-3-apply-the-new-retention-policy-to-mailboxes-on-hold"></a>Passaggio 3: applicare il nuovo criterio di conservazione alle cassette postali in blocco

L'ultimo passaggio consiste nell'applicare i nuovi criteri di conservazione creati nel passaggio 2 alle cassette postali in attesa nell'organizzazione. È possibile utilizzare EAC o Exchange Online PowerShell per applicare il criterio di conservazione a una singola cassetta postale o a più cassette postali. 
  
### <a name="use-the-eac-to-apply-the-new-retention-policy"></a>Utilizzo dell'interfaccia di amministrazione di Exchange per applicare il nuovo criterio di conservazione
  
1. Andare a **Destinatari** \> **Cassette postali**.
    
2. Nella visualizzazione elenco, selezionare la cassetta postale a cui si desidera applicare il criterio di conservazione, quindi fare **** ![clic su modifica](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)icona modifica.
    
3. Nella pagina **cassetta postale utente** , fare clic su **funzionalità cassette postali**.
    
4. In **criteri di conservazione**, selezionare i criteri di conservazione creati nel passaggio 2, quindi fare clic su **Salva**.
    
È inoltre possibile utilizzare EAC per applicare il criterio di conservazione a più cassette postali.
  
1. Andare a **Destinatari** \> **Cassette postali**.
    
2. Nell'elenco, utilizzare il tasto Maiusc o Ctrl per selezionare più cassette postali.
    
3. Nel riquadro dei dettagli, fare clic su **Altre opzioni**.
    
4. In **Criterio di conservazione**, fare clic su **Aggiorna**.
    
5. Nella pagina **assegnazione in blocco dei criteri di conservazione** selezionare i criteri di conservazione creati nel passaggio 2, quindi fare clic su **Salva**. 
    
### <a name="use-exchange-online-powershell-to-apply-the-new-retention-policy"></a>Utilizzare PowerShell di Exchange Online per applicare i nuovi criteri di conservazione
  
È possibile utilizzare PowerShell di Exchange Online per applicare un nuovo criterio di conservazione a una singola cassetta postale. Tuttavia, il vero potere di PowerShell è che è possibile utilizzarlo per identificare rapidamente tutte le cassette postali dell'organizzazione che si trovano su blocco per controversia legale o sul posto, quindi applicare il nuovo criterio di conservazione a tutte le cassette postali in attesa in un singolo comando. Di seguito sono riportati alcuni esempi di utilizzo di Exchange PowerShell per applicare un criterio di conservazione a una o più cassette postali. In tutti gli esempi viene applicato il criterio di conservazione creato nel passaggio 2.
  
In questo esempio viene applicato il nuovo criterio di conservazione alla cassetta postale di Pilar Pinilla.
  
```powershell
Set-Mailbox "Pilar Pinilla" -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

In questo esempio viene applicato il nuovo criterio di conservazione a tutte le cassette postali dell'organizzazione in blocco per controversia legale.
  
```powershell
$LitigationHolds = Get-Mailbox -ResultSize unlimited | Where-Object {$_.LitigationHoldEnabled -eq 'True'}
```

```powershell
$LitigationHolds.DistinguishedName | Set-Mailbox -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

In questo esempio viene applicato il nuovo criterio di conservazione a tutte le cassette postali dell'organizzazione che si trovano in blocco sul posto.
  
```powershell
$InPlaceHolds = Get-Mailbox -ResultSize unlimited | Where-Object {$_.InPlaceHolds -ne $null}
```

```powershell
$InPlaceHolds.DistinguishedName | Set-Mailbox -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

È possibile utilizzare il cmdlet **Get-Mailbox** per verificare che sia stato applicato il nuovo criterio di conservazione. 
  
Di seguito sono riportati alcuni esempi per verificare che i comandi negli esempi precedenti abbiano applicato il criterio di conservazione "criteri di gestione record di messaggistica per cassette postali in attesa" alle cassette postali in blocco per controversia legale e cassette postali sull'archiviazione sul posto.
  
```powershell
Get-Mailbox "Pilar Pinilla" | Select RetentionPolicy
```

```powershell
Get-Mailbox -ResultSize unlimited | Where-Object {$_.LitigationHoldEnabled -eq 'True'} | FT DisplayName,RetentionPolicy -Auto
```

```powershell
Get-Mailbox -ResultSize unlimited | Where-Object {$_.InPlaceHolds -ne $null} | FT DisplayName,RetentionPolicy -Auto
```

## <a name="optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings"></a>Optional Passaggio 4: eseguire l'Assistente cartelle gestite per applicare le nuove impostazioni di conservazione

Dopo aver applicato il nuovo criterio di conservazione alle cassette postali in attesa, possono essere necessari fino a 7 giorni in Exchange Online affinché l'Assistente cartelle gestite elabori queste cassette postali utilizzando le impostazioni del nuovo criterio di conservazione. Invece di attendere l'esecuzione dell'Assistente cartelle gestite, è possibile utilizzare il cmdlet **Start-ManagedFolderAssistant** per attivare manualmente l'assistente per elaborare le cassette postali a cui è stato applicato il nuovo criterio di conservazione. 
  
Eseguire il seguente comando per avviare l'Assistente cartelle gestite per la cassetta postale di Pilar Pinilla.
  
```powershell
Start-ManagedFolderAssistant "Pilar Pinilla"
```

Eseguire i seguenti comandi per avviare l'Assistente cartelle gestite per tutte le cassette postali in attesa.
  
```powershell
$MailboxesOnHold = Get-Mailbox -ResultSize unlimited | Where-Object {($_.InPlaceHolds -ne $null) -or ($_.LitigationHoldEnabled -eq "True")}
```

```powershell
$MailboxesOnHold.DistinguishedName | Start-ManagedFolderAssistant
```

## <a name="more-information"></a>Altre informazioni

- Dopo aver abilitato la cassetta postale di archiviazione di un utente, è consigliabile comunicare all'utente che altri elementi della cassetta postale (non solo gli elementi nella cartella elementi ripristinabili) potrebbero essere spostati nella cassetta postale di archiviazione. Ciò è dovuto al fatto che il criterio di gestione record di messaggistica predefinito assegnato alle cassette postali di Exchange Online contiene un tag di conservazione (denominati 2 anni di spostamento in Archivio) che sposta gli elementi nella cassetta postale di archiviazione due anni dopo la data in cui l'elemento è stato recapitato alla cassetta postale o creato dal utente. Per ulteriori informazioni, vedere [criteri di conservazione predefiniti in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=746954)
    
- Dopo aver abilitato la cassetta postale di archiviazione di un utente, si potrebbe anche informare l'utente che è possibile recuperare gli elementi eliminati nella cartella elementi ripristinabili nella cassetta postale di archiviazione. È possibile eseguire questa operazione in Outlook selezionando la cartella **posta eliminata** nella cassetta postale di archiviazione e quindi facendo clic su **Ripristina elementi eliminati dal server** nella scheda **Home** . Per ulteriori informazioni sul ripristino degli elementi eliminati, vedere [recuperare gli elementi eliminati in Outlook per Windows](https://go.microsoft.com/fwlink/p/?LinkId=624829). 
