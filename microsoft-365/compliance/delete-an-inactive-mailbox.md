---
title: Eliminare una cassetta postale inattiva
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
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
ms.openlocfilehash: 94a20bee1ca3d11a193a25efeb6d73f356e1d58d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909926"
---
# <a name="delete-an-inactive-mailbox"></a>Eliminare una cassetta postale inattiva

Una cassetta postale inattiva viene utilizzata per conservare la posta elettronica di un ex dipendente dopo l'uscita dall'organizzazione. When you no longer need to preserve the contents of an inactive mailbox, you can permanently delete the inactive mailbox by removing the hold. Also, it's possible that multiple holds might be placed on an inactive mailbox. For example, an inactive mailbox might be placed on Litigation Hold and on one or more In-Place Holds. Inoltre, un criterio di conservazione (creato nel Centro sicurezza e conformità in Office 365 o Microsoft 365) potrebbe essere applicato alla cassetta postale inattiva. È necessario rimuovere tutti i blocchi e i criteri di conservazione da una cassetta postale inattiva per eliminarla. After you remove the holds and retention policies, the inactive mailbox is marked for deletion and is permanently deleted after it's processed.
  
> [!IMPORTANT]
> Continuando a investire in modi diversi per conservare il contenuto delle cassette postali, stiamo annunciando il ritiro delle In-Place esenzioni nell'interfaccia di amministrazione di Exchange. Ciò significa che è consigliabile utilizzare i blocchi per controversia legale e i criteri di conservazione per creare una cassetta postale inattiva. A partire dal 1° luglio 2020 non sarà possibile creare nuovi blocchi In-Place in Exchange Online. Tuttavia, sarà comunque possibile modificare la durata del blocco di un'In-Place di archiviazione posta su una cassetta postale inattiva. Tuttavia, a partire dal 1° ottobre 2020, non sarà possibile modificare la durata del blocco. Sarà possibile eliminare una cassetta postale inattiva solo rimuovendo l'In-Place blocco. Le cassette postali inattive esistenti In-Place conservazione verranno mantenute finché il blocco non viene rimosso. Per ulteriori informazioni sul ritiro delle In-Place, vedere [Ritiro degli strumenti di eDiscovery legacy.](legacy-ediscovery-retirement.md)
  
Vedere la sezione [Ulteriori informazioni](#more-information) per una descrizione di cosa succede dopo che i blocchi vengono rimossi da una cassetta postale inattiva.
  
## <a name="before-you-delete-an-inactive-mailbox"></a>Prima di eliminare una cassetta postale inattiva

- È necessario utilizzare Exchange Online PowerShell per rimuovere un blocco per controversia legale da una cassetta postale inattiva. Non è possibile utilizzare l'interfaccia di amministrazione di Exchange (EAC). Per istruzioni dettagliate, vedere [Connettersi a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

- È possibile copiare i contenuti di una cassetta postale inattiva in un'altra cassetta postale prima di rimuovere il blocco ed eliminare una cassetta postale inattiva. Per informazioni dettagliate, vedere [Restore an inactive mailbox in Office 365](restore-an-inactive-mailbox.md).

- Se si rimuove il blocco o il criterio di conservazione da una cassetta postale inattiva e il periodo di conservazione della cassetta postale eliminata temporaneamente per la cassetta postale è scaduto, la cassetta postale verrà eliminata definitivamente. Una volta eliminata, non è possibile recuperarla. Prima di rimuovere il blocco, assicurarsi che il contenuto della cassetta postale non sia più necessario. Se si desidera riattivare una cassetta postale inattiva, è possibile ripristinarla. Per informazioni dettagliate, vedere [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).

- Per ulteriori informazioni sulle cassette postali inattive, vedere [Cassette postali inattive in Office 365.](inactive-mailboxes-in-office-365.md)

## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a>Passaggio 1: identificare i blocchi su una cassetta postale inattiva

Come indicato in precedenza, un blocco per controversia legale, In-Place blocco o un criterio di conservazione potrebbe essere posizionato su una cassetta postale inattiva. Il primo passaggio consiste nell'identificare i blocchi su una cassetta postale inattiva.
  
Eseguire il seguente comando per visualizzare le informazioni sul blocco per tutte le cassette postali inattive dell'organizzazione.
  
```powershell
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,InPlaceHolds
```

Il valore di **True** per la proprietà **LitigationHoldEnabled** indica che la cassetta postale inattiva ha un blocco per controversia legale. Se in una cassetta postale inattiva è abilitato un blocco sul posto, il GUID del blocco viene visualizzato come il valore per la proprietà **InPlaceHolds**. Ad esempio, i risultati seguenti per due cassette postali inattive mostrano che il blocco per controversia legale è stato posto su Ann Beebe e che un criterio di conservazione e blocco In-Place viene posizionato su Pilar Pinilla.
  
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
InPlaceHolds          : {c0ba3ce811b6432a8751430937152491, mbxba6f4ba25b62490aaaa253eea27426ab}
```

> [!TIP]
> Se molte In-Place esenzioni o criteri di conservazione vengono inseriti in una cassetta postale inattiva, non verranno visualizzati tutti In-Place GUID di archiviazione. È possibile eseguire il comando seguente per visualizzare tutti i GUID nella proprietà InPlaceHolds:  `Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`
  
Per ulteriori informazioni sull'identificazione dei blocchi, vedere [How to identify the type of hold placed on a mailbox](identify-a-hold-on-an-exchange-online-mailbox.md).

## <a name="step-2-remove-a-hold-from-an-inactive-mailbox"></a>Passaggio 2: Rimuovere un blocco da una cassetta postale inattiva

Dopo aver identificato il tipo di blocco applicato alla cassetta postale inattiva (e se sono presenti più blocchi), il passaggio successivo consiste nel rimuovere i blocchi sulla cassetta postale. Come descritto in precedenza, è necessario rimuovere tutti i blocchi per eliminare definitivamente una cassetta postale inattiva.
  
### <a name="remove-a-litigation-hold"></a>Rimozione di un blocco per controversia legale

Come descritto in precedenza, è necessario utilizzare Windows PowerShell per rimuovere un blocco per controversia legale da una cassetta postale inattiva. Non è possibile usare l'interfaccia di amministrazione di Exchange. Eseguire il comando riportato di seguito per rimuovere un blocco per controversia legale.
  
```powershell
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldEnabled $false
```

> [!TIP]
> Il modo migliore per identificare una cassetta postale inattiva è utilizzando il valore del relativo nome distinto o del GUID di Exchange. L'utilizzo di uno di questi valori consente di non specificare accidentalmente la cassetta postale errata. 
  
### <a name="remove-an-inactive-mailbox-from-a-retention-policy"></a>Rimuovere una cassetta postale inattiva da un criterio di conservazione

La procedura per rimuovere una cassetta postale inattiva da un criterio di conservazione di Microsoft 365 dipende dal fatto che il criterio di conservazione assegnato alla cassetta postale inattiva sia a livello di organizzazione o esplicito. sul tipo di criterio di conservazione assegnato alla cassetta postale inattiva.

- Criteri di conservazione a livello di organizzazione assegnati a tutte le cassette postali dell'organizzazione. Utilizzare il cmdlet **Get-OrganizationConfig** in PowerShell di Exchange Online per ottenere informazioni sui criteri di conservazione a livello di organizzazione.

- Criteri di conservazione percorso specifici assegnati a cassette postali specifiche. Si tratta di criteri assegnati ai percorsi di contenuto di utenti specifici. Utilizzare il cmdlet **Get-Mailbox -IncludeInactiveMailbox** in PowerShell di Exchange Online per ottenere informazioni sui criteri di conservazione assegnati a cassette postali inattive specifiche.

#### <a name="remove-an-inactive-mailbox-from-an-organization-wide-retention-policy"></a>Rimuovere una cassetta postale inattiva da un criterio di conservazione a livello di organizzazione

Eseguire il comando seguente in PowerShell di Exchange Online per escludere una cassetta postale inattiva da un criterio di conservazione a livello di organizzazione.

```powershell
Set-Mailbox <identity of inactive mailbox> -ExcludeFromOrgHolds <retention policy GUID without prefix or suffix>
```

Per ulteriori informazioni sull'identificazione dei criteri di conservazione a livello di organizzazione applicati a una cassetta postale inattiva e sull'ottenimento del GUID per un criterio di conservazione, vedere la sezione "Get-OrganizationConfig" in Come identificare il tipo di blocco applicato [a](identify-a-hold-on-an-exchange-online-mailbox.md#get-organizationconfig)una cassetta postale.

In alternativa, è possibile eseguire il comando seguente per rimuovere la cassetta postale inattiva da tutti i criteri a livello di organizzazione:

```powershell
Set-Mailbox <identity of inactive mailbox> -ExcludeFromAllOrgHolds
```

#### <a name="remove-an-inactive-mailbox-from-a-specific-location-retention-policy"></a>Rimuovere una cassetta postale inattiva da un criterio di conservazione percorso specifico

Eseguire il comando seguente in [PowerShell &](/powershell/exchange/connect-to-scc-powershell) Centro sicurezza e conformità per rimuovere una cassetta postale inattiva da un criterio di conservazione esplicito.

```powershell
Set-RetentionCompliancePolicy -Identity <retention policy GUID without prefix or suffix> -AddExchangeLocationException <identity of inactive mailbox>
```

Per ulteriori informazioni sull'identificazione di criteri di conservazione percorso specifici applicati a una cassetta postale inattiva e su come ottenere il GUID per un criterio di conservazione, vedere la sezione "Get-Mailbox" in Come identificare il tipo di blocco applicato [a](identify-a-hold-on-an-exchange-online-mailbox.md#get-mailbox)una cassetta postale.

### <a name="remove-in-place-holds"></a>Rimozione dei blocchi sul posto

 Esistono due modi per rimuovere un blocco sul posto da una cassetta postale inattiva: 
  
- **Eliminare l'In-Place blocco .** Se la cassetta postale inattiva che si desidera eliminare definitivamente è l'unica cassetta postale di origine per un blocco In-Place, è possibile eliminare l'oggetto In-Place blocco. 

    > [!NOTE]
    > È necessario disattivare il blocco prima di eliminare un oggetto blocco sul posto. Se si tenta di eliminare un oggetto blocco sul posto con il blocco abilitato, verrà visualizzato un messaggio di errore. 
  
- **Rimuovere la cassetta postale inattiva come cassetta postale di origine di un In-Place blocco**. Se si desidera mantenere altre cassette postali di origine per un blocco sul posto, è possibile rimuovere la cassetta postale inattiva dall'elenco di cassette postali di origine e conservare l'oggetto blocco sul posto.

#### <a name="delete-an-in-place-hold"></a>Eliminare un blocco In-Place blocco

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

#### <a name="remove-an-inactive-mailbox-from-an-in-place-hold"></a>Rimuovere una cassetta postale inattiva da un In-Place blocco

Se il blocco sul posto contiene un numero elevato di cassette postali di origine, è possibile che la cassetta postale inattiva non sia riportata nella pagina **Origini** nell'interfaccia di amministrazione di Exchange. Vengono visualizzate fino a 3.000 cassette postali nella pagina **Origini** quando si modifica un blocco sul posto. Se una cassetta postale inattiva non è indicata nella pagina **Origini**, è possibile utilizzare PowerShell di Exchange Online per rimuoverla dal blocco sul posto. 
  
1. Creare una variabile che contiene le proprietà del blocco sul posto applicato alla cassetta postale inattiva. Utilizzare il GUID del blocco sul posto che è stato acquisito nel [Passaggio 1: Identificare i blocchi su una cassetta postale inattiva](#step-1-identify-the-holds-on-an-inactive-mailbox).

    ```powershell
    $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
    ```

2. Verificare che la cassetta postale inattiva sia elencata come cassetta postale di origine per il blocco sul posto. 

   ```powershell
   $InPlaceHold.Sources
   ```

   > [!NOTE]
   > La proprietà *Sources* del blocco sul posto consente di identificare le cassette postali di origine dalle loro proprietà *LegacyExchangeDN*. Poiché questa proprietà identifica le cassette postali inattive in modo univoco, l'utilizzo della proprietà *Sources* dal blocco sul posto consente di evitare la rimozione della cassetta postale errata. Ciò consente inoltre di evitare problemi se due cassette postali hanno lo stesso alias o indirizzo SMTP. 

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

## <a name="more-information"></a>Ulteriori informazioni

- **Una cassetta postale inattiva è un tipo di cassetta postale con eliminazione temporanea.** In Exchange Online, una cassetta postale con eliminazione temporanea è una cassetta postale che è stata eliminata, ma che può essere recuperata entro un periodo di conservazione specifico. Il periodo di conservazione delle cassette postali con eliminazione temporanea in Exchange Online è pari a 30 giorni. Ciò significa che la cassetta postale può essere recuperata entro 30 giorni dall'eliminazione temporanea. Dopo 30 giorni, una cassetta postale con eliminazione temporanea viene contrassegnata per l'eliminazione definitiva e non può essere ripristinata.

- **Cosa succede dopo aver rimosso il blocco su una cassetta postale inattiva?** La cassetta postale viene considerata come altre cassette postali con eliminazione temporanea e viene contrassegnata per l'eliminazione definitiva alla scadenza del periodo di conservazione di 30 giorni. Questo periodo di conservazione inizia alla data in cui la cassetta postale viene resa inattiva. Questa data è nota come data di eliminazione recidiva, ovvero la data in cui l'account utente corrispondente è stato eliminato o quando la cassetta postale di Exchange Online è stata eliminata con il cmdlet **Remove-Mailbox.** La data di eliminazione temporanea non è la data in cui si rimuove il blocco.

- **Una cassetta postale inattiva viene eliminata definitivamente subito dopo la rimozione del blocco?** Se la data di eliminazione temporanea di una cassetta postale inattiva risale a più di 30 giorni prima, la cassetta postale non viene eliminata definitivamente non appena si rimuove il blocco. La cassetta postale viene contrassegnata per l'eliminazione definitiva e viene eliminata la volta successiva che viene elaborata.

- **In che modo il periodo di conservazione delle cassette postali con eliminazione temporanea influisce sulle cassette postali inattive?** Se la data di eliminazione temporanea di una cassetta postale inattiva risale a più di 30 giorni prima della data in cui è stato rimosso il blocco, la cassetta postale viene contrassegnata per l'eliminazione definitiva. Tuttavia, se una cassetta postale inattiva ha una data di eliminazione temporanea entro gli ultimi 30 giorni e si rimuove il blocco, è possibile ripristinare la cassetta postale fino a quando non scade il periodo di conservazione delle cassette postali con eliminazione temporanea. Per ulteriori dettagli, vedere [Eliminare o ripristinare le cassette postali utente in Exchange Online](/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes). Dopo la scadenza del periodo di conservazione della cassetta postale eliminata in modo reverso, è necessario seguire le procedure per il ripristino di una cassetta postale inattiva. Per informazioni dettagliate, vedere [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).

- **Come vengono visualizzate le informazioni su una cassetta postale inattiva dopo la rimozione del blocco?** Dopo che un blocco è stato rimosso e la cassetta postale inattiva viene ripristinata in una cassetta postale eliminata in modo recintato, non verrà restituita utilizzando il parametro *InactiveMailboxOnly* con il cmdlet **Get-Mailbox.** Tuttavia, è possibile visualizzare le informazioni sulla cassetta postale utilizzando il comando **Get-Mailbox -SoftDeletedMailbox**. Ad esempio:

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

  Nell'esempio precedente, la *proprietà WhenSoftDeleted* identifica la data di eliminazione recidiva, che in questo esempio è il 30 ottobre 2014. Se questa cassetta postale eliminata temporaneamente era in precedenza una cassetta postale inattiva per la quale è stato rimosso il blocco, verrà eliminata definitivamente 30 giorni dopo il valore della proprietà *WhenSoftDeleted.* In questo caso, la cassetta postale viene eliminata definitivamente dopo il 30 novembre 2014.