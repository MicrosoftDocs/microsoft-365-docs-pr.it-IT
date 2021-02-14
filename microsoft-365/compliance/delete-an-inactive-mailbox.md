---
title: Eliminare una cassetta postale inattiva
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 9/5/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: f5caf497-5e8d-4b7a-bfff-d02942f38150
ms.custom:
- seo-marvel-apr2020
description: Quando non è più necessario conservare il contenuto di una cassetta postale inattiva di Microsoft 365, è possibile eliminare definitivamente la cassetta postale inattiva.
ms.openlocfilehash: 05357ce1b3e10394854844f15ec6a18c1c427d5b
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817895"
---
# <a name="delete-an-inactive-mailbox"></a>Eliminare una cassetta postale inattiva

An inactive mailbox is used to preserve a former employee's email after he or she leaves your organization. When you no longer need to preserve the contents of an inactive mailbox, you can permanently delete the inactive mailbox by removing the hold. Also, it's possible that multiple holds might be placed on an inactive mailbox. For example, an inactive mailbox might be placed on Litigation Hold and on one or more In-Place Holds. Inoltre, un criterio di conservazione (creato nel Centro sicurezza e conformità in Office 365 o Microsoft 365) potrebbe essere applicato alla cassetta postale inattiva. È necessario rimuovere tutti i blocchi e i criteri di conservazione da una cassetta postale inattiva per eliminarla. After you remove the holds and retention policies, the inactive mailbox is marked for deletion and is permanently deleted after it's processed.
  
> [!IMPORTANT]
> Continuando a investire in modi diversi per conservare il contenuto delle cassette postali, stiamo annunciando il ritiro delle In-Place blocchi nell'interfaccia di amministrazione di Exchange. Ciò significa che è consigliabile utilizzare i blocchi per controversia legale e i criteri di conservazione per creare una cassetta postale inattiva. A partire dal 1° luglio 2020 non sarà possibile creare nuovi blocchi In-Place in Exchange Online. Tuttavia, sarà comunque possibile modificare la durata del blocco di un'In-Place blocco su una cassetta postale inattiva. Tuttavia, a partire dal 1° ottobre 2020, non sarà possibile modificare la durata del blocco. You'll only be able to delete an inactive mailbox by removing the In-Place Hold. Le cassette postali inattive esistenti In-Place conservazione verranno mantenute finché il blocco non viene rimosso. Per ulteriori informazioni sul ritiro dei blocchi In-Place, vedere [Ritiro degli strumenti legacy di eDiscovery.](legacy-ediscovery-retirement.md)
  
Vedere la sezione [Ulteriori informazioni](#more-information) per una descrizione di cosa succede dopo che i blocchi vengono rimossi da una cassetta postale inattiva.
  
## <a name="before-you-delete-an-inactive-mailbox"></a>Prima di eliminare una cassetta postale inattiva

- È necessario utilizzare Exchange Online PowerShell per rimuovere un blocco per controversia legale da una cassetta postale inattiva. Non è possibile utilizzare l'interfaccia di amministrazione di Exchange (EAC). Per istruzioni dettagliate, vedere [Connettersi a Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554). È possibile utilizzare Exchange Online PowerShell o l'interfaccia di amministrazione di Exchange (EAC) per rimuovere un blocco sul posto da una cassetta postale inattiva. 
    
- È possibile copiare i contenuti di una cassetta postale inattiva in un'altra cassetta postale prima di rimuovere il blocco ed eliminare una cassetta postale inattiva. Per informazioni dettagliate, vedere [Ripristinare una cassetta postale inattiva in Office 365.](restore-an-inactive-mailbox.md)
    
- Se si rimuove il blocco o il criterio di conservazione da una cassetta postale inattiva e il periodo di conservazione della cassetta postale eliminata temporaneamente per la cassetta postale è scaduto, la cassetta postale verrà eliminata definitivamente. Una volta eliminata, non è possibile recuperarla. Prima di rimuovere il blocco, assicurarsi che il contenuto della cassetta postale non sia più necessario. Se si desidera attivare nuovamente una cassetta postale inattiva, è possibile recuperarla. Per informazioni dettagliate, vedere [Recuperare una cassetta postale inattiva in Office 365.](recover-an-inactive-mailbox.md)
    
- Per ulteriori informazioni sulle cassette postali inattive, vedere [Cassette postali inattive in Office 365.](inactive-mailboxes-in-office-365.md)
    
## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a>Passaggio 1: identificare i blocchi su una cassetta postale inattiva

Come indicato in precedenza, un blocco per controversia legale, un In-Place conservazione o un criterio di conservazione potrebbe essere posizionato su una cassetta postale inattiva. Il primo passaggio consiste nell'identificare i blocchi su una cassetta postale inattiva.
  
Eseguire il seguente comando per visualizzare le informazioni sul blocco per tutte le cassette postali inattive dell'organizzazione.
  
```powershell
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,InPlaceHolds
```

Il valore di **True** per la proprietà **LitigationHoldEnabled** indica che la cassetta postale inattiva ha un blocco per controversia legale. Se in una cassetta postale inattiva è abilitato un blocco sul posto, il GUID del blocco viene visualizzato come il valore per la proprietà **InPlaceHolds**. Ad esempio, i risultati seguenti per due cassette postali inattive mostrano che un blocco per controversia legale è applicato ad Ann Beebe e che due blocchi sul posto sono applicati a Pilar Pinilla. 
  
```text
DisplayName           : Ann Beebe
Name                  : annb
IsInactiveMailbox     : True
LitigationHoldEnabled : True
InPlaceHolds          : {}
...
DisplayName           : Pilar Pinilla
Name                  : pilarp
IsInactiveMailbox     : True
LitigationHoldEnabled : False
InPlaceHolds          : {c0ba3ce811b6432a8751430937152491, ba6f4ba25b62490aaaa253eea27426ab}
```

> [!TIP]
> Se sono abilitati numerosi blocchi sul posto per una cassetta postale inattiva, non vengono visualizzati tutti i GUID dei blocchi sul posto. È possibile eseguire il comando seguente per visualizzare tutti i GUID In-Place blocco:  `Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`
  
## <a name="step-2-remove-a-hold-from-an-inactive-mailbox"></a>Passaggio 2: Rimuovere un blocco da una cassetta postale inattiva

Dopo aver identificato il tipo di blocco applicato alla cassetta postale inattiva (e se sono presenti più blocchi), il passaggio successivo consiste nel rimuovere i blocchi sulla cassetta postale. Come descritto in precedenza, è necessario rimuovere tutti i blocchi per eliminare definitivamente una cassetta postale inattiva. 
  
### <a name="remove-a-litigation-hold"></a>Rimozione di un blocco per controversia legale

Come descritto in precedenza, è necessario utilizzare Windows PowerShell per rimuovere un blocco per controversia legale da una cassetta postale inattiva. Non è possibile usare l'interfaccia di amministrazione di Exchange. Eseguire il comando riportato di seguito per rimuovere un blocco per controversia legale.
  
```powershell
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldEnabled $false
```

> [!TIP]
> Il modo migliore per identificare una cassetta postale inattiva è utilizzando il valore del relativo nome distinto o del GUID di Exchange. L'utilizzo di uno di questi valori consente di non specificare accidentalmente la cassetta postale errata. 
  
### <a name="remove-in-place-holds"></a>Rimozione dei blocchi sul posto

 Esistono due modi per rimuovere un blocco sul posto da una cassetta postale inattiva: 
  
- **Eliminare l'In-Place blocco** Se la cassetta postale inattiva che si desidera eliminare definitivamente è l'unica cassetta postale di origine per un In-Place Hold, è sufficiente eliminare l'oggetto In-Place Hold. 
    
    > [!NOTE]
    > È necessario disattivare il blocco prima di eliminare un oggetto blocco sul posto. Se si tenta di eliminare un oggetto blocco sul posto con il blocco abilitato, verrà visualizzato un messaggio di errore. 
  
- **Rimuovere la cassetta postale inattiva come cassetta postale di origine di un blocco sul posto** Se si desidera mantenere altre cassette postali di origine per un blocco sul posto, è possibile rimuovere la cassetta postale inattiva dall'elenco di cassette postali di origine e conservare l'oggetto blocco sul posto. 
    
#### <a name="use-the-eac-to-delete-an-in-place-hold"></a>Utilizzare EAC per eliminare un blocco sul posto

1. Se si conosce il nome del blocco sul posto che si desidera eliminare, è possibile passare al passaggio successivo. In caso contrario, eseguire il seguente comando per ottenere il nome del blocco sul posto applicato alla cassetta postale inattiva che si desidera eliminare definitivamente. Utilizzare il GUID del blocco sul posto che è stato acquisito nel [Passaggio 1: Identificare i blocchi su una cassetta postale inattiva](#step-1-identify-the-holds-on-an-inactive-mailbox).
    
   ```powershell
   Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
   ```

2. In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.
    
3. Selezionare il In-Place esenzione che si desidera eliminare e quindi fare clic **sull'icona** ![ Modifica ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) modifica.
    
4. On the **In-Place eDiscovery &amp; Hold** properties page, click **In-Place Hold**, uncheck the **Place content matching the search query in selected mailboxes on hold** box, and then click **Save**.
    
5. On the **In-Place eDiscovery &amp; Hold** page, select the In-Place Hold again, and then click **Delete**![Delete icon](../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).
    
6. Nell'avviso, fare clic su **Sì** per eliminare il blocco sul posto. 
    
#### <a name="use-exchange-online-powershell-to-delete-an-in-place-hold"></a>Utilizzare PowerShell di Exchange Online per eliminare un blocco sul posto

1. Creare una variabile che contiene le proprietà del blocco sul posto che si desidera eliminare. Utilizzare il GUID del blocco sul posto che è stato acquisito nel [Passaggio 1: Identificare i blocchi su una cassetta postale inattiva](#step-1-identify-the-holds-on-an-inactive-mailbox).
    
   ```powershell
   $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
   ```

2. Disattivare il blocco in Blocco sul posto.
    
   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -InPlaceHoldEnabled $false
   ```

3. Eliminare il blocco sul posto.
    
   ```powershell
   Remove-MailboxSearch $InPlaceHold.Name
   ```

#### <a name="use-the-eac-to-remove-an-inactive-mailbox-from-an-in-place-hold"></a>Usare EAC per rimuovere una cassetta postale inattiva da un blocco sul posto

1. Se si conosce il nome del blocco sul posto che si desidera applicare alla cassetta postale inattiva, è possibile passare al passaggio successivo. In caso contrario, eseguire il seguente comando per ottenere il nome del blocco sul posto applicato alla cassetta postale. Utilizzare il GUID del blocco sul posto che è stato acquisito nel [Passaggio 1: Identificare i blocchi su una cassetta postale inattiva](#step-1-identify-the-holds-on-an-inactive-mailbox).
    
   ```powershell
   Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
   ```

2. In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.
    
3. Selezionare il In-Place blocco attivo nella cassetta postale inattiva, quindi fare clic **sull'icona** ![ Modifica ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) modifica.
    
4. On the **In-Place eDiscovery &amp; Hold** properties page, click **Sources**.
    
5. Nell'elenco delle cassette postali di origine, fare clic sul nome della cassetta postale inattiva che si desidera rimuovere, quindi fare clic su **Rimuovi**![Icona Rimuovi](../media/adf01106-cc79-475c-8673-065371c1897b.gif).
    
6. Fare clic su **Salva** per salvare la modifica. Verrà visualizzato un messaggio che indica che l'operazione è stata completata. 
    
7. Ripetere i passaggi da 1 a 6 per rimuovere altri blocchi sul posto applicati alla cassetta postale inattiva.
    
#### <a name="use-exchange-online-powershell-to-remove-an-inactive-mailbox-from-an-in-place-hold"></a>Utilizzare PowerShell di Exchange Online per rimuovere una cassetta postale inattiva da un blocco sul posto

Se il blocco sul posto contiene un numero elevato di cassette postali di origine, è possibile che la cassetta postale inattiva non sia riportata nella pagina **Origini** nell'interfaccia di amministrazione di Exchange. Vengono visualizzate fino a 3.000 cassette postali nella pagina **Origini** quando si modifica un blocco sul posto. Se una cassetta postale inattiva non è indicata nella pagina **Origini**, è possibile utilizzare PowerShell di Exchange Online per rimuoverla dal blocco sul posto. 
  
1. Creare una variabile che contiene le proprietà del blocco sul posto applicato alla cassetta postale inattiva. Utilizzare il GUID del blocco sul posto che è stato acquisito nel [Passaggio 1: Identificare i blocchi su una cassetta postale inattiva](#step-1-identify-the-holds-on-an-inactive-mailbox).
    
    ```powershell
    $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
    ```

2. Verificare che la cassetta postale inattiva sia elencata come cassetta postale di origine per il blocco sul posto. 
    
   ```powershell
   $InPlaceHold.Sources
   ```

   **Nota:** La *proprietà Sources* del blocco In-Place consente di identificare le cassette postali di origine in base alle proprietà *LegacyExchangeDN.* Poiché questa proprietà identifica le cassette postali inattive in modo univoco, l'utilizzo della proprietà *Sources* dal blocco sul posto consente di evitare la rimozione della cassetta postale errata. Ciò consente inoltre di evitare problemi se due cassette postali hanno lo stesso alias o indirizzo SMTP. 
   
3. Rimuovere la cassetta postale inattiva dall'elenco delle cassette postali di origine nella variabile. Assicurarsi di usare il **LegacyExchangeDN** della cassetta postale inattiva restituito dal comando nel passaggio precedente. 
    
    ```powershell
    $InPlaceHold.Sources.Remove("<LegacyExchangeDN of the inactive mailbox>")
    ```

    Ad esempio, il seguente comando consente di rimuovere la cassetta postale inattiva per Pilar Pinilla.
    
    ```powershell
    $InPlaceHold.Sources.Remove("/o=contoso/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/ cn=9c8dfff651ec4908950f5df60cbbda06-pilarp")
    ```

4. Verificare che la cassetta postale inattiva venga rimossa dall'elenco delle cassette postali di origine nella variabile.
    
   ```powershell
   $InPlaceHold.Sources
   ```

5. Modificare il blocco sul posto con l'elenco aggiornato delle cassette postali di origine, che non include la cassetta postale inattiva.
    
   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -SourceMailboxes $InPlaceHold.Sources
   ```

6. Verificare che la cassetta postale inattiva venga rimossa dall'elenco delle cassette postali di origine per il blocco sul posto.
    
   ```powershell
   Get-MailboxSearch $InPlaceHold.Name | FL Sources
   ```

## <a name="more-information"></a>Altre informazioni

- **Una cassetta postale inattiva è un tipo di cassetta postale con eliminazione temporanea.** In Exchange Online, una cassetta postale con eliminazione temporanea è una cassetta postale che è stata eliminata, ma che può essere recuperata entro un periodo di conservazione specifico. Il periodo di conservazione delle cassette postali con eliminazione temporanea in Exchange Online è pari a 30 giorni. Ciò significa che la cassetta postale può essere recuperata entro 30 giorni dall'eliminazione temporanea. Dopo 30 giorni, una cassetta postale con eliminazione temporanea viene contrassegnata per l'eliminazione definitiva e non può essere ripristinata. 
    
- **Cosa succede dopo aver rimosso il blocco su una cassetta postale inattiva?** La cassetta postale viene considerata come altre cassette postali con eliminazione temporanea e viene contrassegnata per l'eliminazione definitiva alla scadenza del periodo di conservazione di 30 giorni. Questo periodo di conservazione inizia alla data in cui la cassetta postale viene resa inattiva. Questa data è nota come data di eliminazione rescisa, ovvero la data in cui l'account utente corrispondente è stato eliminato o quando la cassetta postale di Exchange Online è stata eliminata con il cmdlet **Remove-Mailbox.** La data di eliminazione temporanea non è la data in cui si rimuove il blocco. 
    
- **Una cassetta postale inattiva viene eliminata definitivamente subito dopo la rimozione del blocco?** Se la data di eliminazione temporanea di una cassetta postale inattiva risale a più di 30 giorni prima, la cassetta postale non viene eliminata definitivamente non appena si rimuove il blocco. La cassetta postale viene contrassegnata per l'eliminazione definitiva e viene eliminata la volta successiva che viene elaborata. 
    
- **In che modo il periodo di conservazione delle cassette postali con eliminazione temporanea influisce sulle cassette postali inattive?** Se la data di eliminazione temporanea di una cassetta postale inattiva risale a più di 30 giorni prima della data in cui è stato rimosso il blocco, la cassetta postale viene contrassegnata per l'eliminazione definitiva. Tuttavia, se una cassetta postale inattiva ha una data di eliminazione temporanea entro gli ultimi 30 giorni e si rimuove il blocco, è possibile ripristinare la cassetta postale fino a quando non scade il periodo di conservazione delle cassette postali con eliminazione temporanea. Per ulteriori dettagli, vedere [Eliminare o ripristinare le cassette postali utente in Exchange Online](https://go.microsoft.com/fwlink/?linkid=856835). Alla scadenza del periodo di conservazione delle cassette postali con eliminazione temporanea, è necessario seguire le procedure per il ripristino di una cassetta postale inattiva. Per informazioni dettagliate, vedere [Recuperare una cassetta postale inattiva in Office 365.](recover-an-inactive-mailbox.md)
    
- **Come vengono visualizzate le informazioni su una cassetta postale inattiva dopo la rimozione del blocco?** Dopo che un blocco viene rimosso e la cassetta postale inattiva viene ripristinata a una cassetta postale eliminata in modo resciso, non verrà restituita utilizzando il parametro *InactiveMailboxOnly* con il cmdlet **Get-Mailbox.** Tuttavia, è possibile visualizzare le informazioni sulla cassetta postale utilizzando il comando **Get-Mailbox -SoftDeletedMailbox**. Ad esempio: 
    
  ```text
  Get-Mailbox -SoftDeletedMailbox -Identity pilarp | FL Name,Identity,LitigationHoldEnabled,In
  Placeholds,WhenSoftDeleted,IsInactiveMailbox
  Name                   : pilarp
  Identity               : Soft Deleted Objects\pilarp
  LitigationHoldEnabled  : False
  InPlaceHolds           : {}
  WhenSoftDeleted        : 10/30/2014 1:19:04 AM
  IsInactiveMailbox      : False
  ```

  Nell'esempio precedente, la *proprietà WhenSoftDeleted* identifica la data di eliminazione rescisa, che in questo esempio è il 30 ottobre 2014. Se questa cassetta postale eliminata temporaneamente era in precedenza una cassetta postale inattiva per la quale è stato rimosso il blocco, verrà eliminata definitivamente 30 giorni dopo il valore della proprietà *WhenSoftDeleted.* In questo caso, la cassetta postale viene eliminata definitivamente dopo il 30 novembre 2014.

