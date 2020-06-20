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

An inactive mailbox is used to preserve a former employee's email after he or she leaves your organization. When you no longer need to preserve the contents of an inactive mailbox, you can permanently delete the inactive mailbox by removing the hold. Also, it's possible that multiple holds might be placed on an inactive mailbox. For example, an inactive mailbox might be placed on Litigation Hold and on one or more In-Place Holds. Inoltre, è possibile applicare un criterio di conservazione (creato nel centro sicurezza e conformità di Office 365 o Microsoft 365) alla cassetta postale inattiva. È necessario rimuovere tutte le esenzioni e i criteri di conservazione da una cassetta postale inattiva per eliminarla. After you remove the holds and retention policies, the inactive mailbox is marked for deletion and is permanently deleted after it's processed.
  
> [!IMPORTANT]
> Continuando a investire in modi diversi per conservare il contenuto delle cassette postali, si annuncia la prepensionamento delle archiviazioni sul posto nell'interfaccia di amministrazione di Exchange. Per creare una cassetta postale inattiva, è necessario utilizzare i criteri di conservazione per controversia legale. A partire dal 1 ° luglio 2020 non è possibile creare nuove archiviazioni sul posto in Exchange Online. Tuttavia, sarà comunque possibile modificare la durata del blocco di un blocco sul posto posto in una cassetta postale inattiva. Tuttavia, a partire dal 1 ° ottobre 2020, non sarà possibile modificare la durata del blocco. È possibile eliminare una cassetta postale inattiva solo rimuovendo il blocco sul posto. Le cassette postali inattive esistenti che si trovano sul blocco sul posto continueranno a essere conservate finché il blocco non viene rimosso. Per ulteriori informazioni sul pensionamento delle archiviazioni sul posto, vedere [pensionamento degli strumenti di eDiscovery legacy](legacy-ediscovery-retirement.md).
  
Vedere la sezione [Ulteriori informazioni](#more-information) per una descrizione di cosa succede dopo che i blocchi vengono rimossi da una cassetta postale inattiva.
  
## <a name="before-you-delete-an-inactive-mailbox"></a>Prima di eliminare una cassetta postale inattiva

- È necessario utilizzare Exchange Online PowerShell per rimuovere un blocco per controversia legale da una cassetta postale inattiva. Non è possibile utilizzare l'interfaccia di amministrazione di Exchange (EAC). Per istruzioni dettagliate, vedere [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554). È possibile utilizzare Exchange Online PowerShell o l'interfaccia di amministrazione di Exchange (EAC) per rimuovere un blocco sul posto da una cassetta postale inattiva. 
    
- È possibile copiare i contenuti di una cassetta postale inattiva in un'altra cassetta postale prima di rimuovere il blocco ed eliminare una cassetta postale inattiva. Per ulteriori informazioni, vedere [ripristinare una cassetta postale inattiva in Office 365](restore-an-inactive-mailbox.md).
    
- Se si rimuove il blocco o il criterio di conservazione da una cassetta postale inattiva e il periodo di conservazione delle cassette postali eliminate temporaneamente per la cassetta postale è scaduto, la cassetta postale viene eliminata definitivamente. Una volta eliminata, non è possibile recuperarla. Prima di rimuovere il blocco, assicurarsi che il contenuto della cassetta postale non sia più necessario. Se si desidera attivare nuovamente una cassetta postale inattiva, è possibile recuperarla. Per ulteriori informazioni, vedere [recuperare una cassetta postale inattiva in Office 365](recover-an-inactive-mailbox.md).
    
- Per ulteriori informazioni sulle cassette postali inattive, vedere [inactive Mailboxes in Office 365](inactive-mailboxes-in-office-365.md).
    
## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a>Passaggio 1: identificare i blocchi su una cassetta postale inattiva

Come indicato in precedenza, un blocco per controversia legale, un blocco sul posto o un criterio di conservazione potrebbe essere posizionato su una cassetta postale inattiva. Il primo passaggio consiste nell'identificare i blocchi su una cassetta postale inattiva.
  
Eseguire il seguente comando per visualizzare le informazioni sul blocco per tutte le cassette postali inattive dell'organizzazione.
  
```powershell
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,InPlaceHolds
```

The value of **True** for the **LitigationHoldEnabled** property indicates that the inactive mailbox is on Litigation Hold. If an In-Place Hold is placed on an inactive mailbox, the GUID for the hold is displayed as the value for the **InPlaceHolds** property. For example, the following results for two inactive mailboxes show that a Litigation Hold is placed on Ann Beebe and that two In-Place Holds are placed on Pilar Pinilla. 
  
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
> Se sono abilitati numerosi blocchi sul posto per una cassetta postale inattiva, non vengono visualizzati tutti i GUID dei blocchi sul posto. È possibile eseguire il comando seguente per visualizzare tutti i GUID del blocco sul posto:`Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`
  
## <a name="step-2-remove-a-hold-from-an-inactive-mailbox"></a>Passaggio 2: Rimuovere un blocco da una cassetta postale inattiva

After you identify what type of hold is placed on the inactive mailbox (and whether there are multiple holds), the next step is to remove the holds on the mailbox. As previously stated, you have to remove all holds to permanently delete an inactive mailbox. 
  
### <a name="remove-a-litigation-hold"></a>Rimozione di un blocco per controversia legale

As previously stated, you have to use Windows PowerShell to remove a Litigation Hold from an inactive mailbox. You can't use the EAC. Run the following command to remove a Litigation Hold.
  
```powershell
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldEnabled $false
```

> [!TIP]
> The best way to identify an inactive mailbox is by using its Distinguished Name or Exchange GUID value. Using one of these values helps prevent accidentally specifying the wrong mailbox. 
  
### <a name="remove-in-place-holds"></a>Rimozione dei blocchi sul posto

 Esistono due modi per rimuovere un blocco sul posto da una cassetta postale inattiva: 
  
- **Eliminare l'oggetto blocco sul posto** Se la cassetta postale inattiva che si desidera eliminare in modo definitivo è l'unica cassetta postale di origine per un blocco sul posto, è possibile eliminare l'oggetto blocco sul posto. 
    
    > [!NOTE]
    > You have to disable the hold before you can delete an In-Place Hold object. If you try to delete an In-Place Hold object that has the hold enabled, you'll receive an error message. 
  
- **Rimuovere la cassetta postale inattiva come cassetta postale di origine di un blocco sul posto** Se si desidera mantenere altre cassette postali di origine per un blocco sul posto, è possibile rimuovere la cassetta postale inattiva dall'elenco di cassette postali di origine e conservare l'oggetto blocco sul posto. 
    
#### <a name="use-the-eac-to-delete-an-in-place-hold"></a>Utilizzare EAC per eliminare un blocco sul posto

1. If you know the name of the In-Place Hold that you want to delete, you can go to the next step. Otherwise, run the following command to get the name of the In-Place Hold that is placed on the inactive mailbox that you want to permanently delete. Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).
    
   ```powershell
   Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
   ```

2. In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.
    
3. Selezionare il blocco sul posto che si desidera eliminare, quindi fare clic su **modifica** ![ icona modifica ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) .
    
4. On the **In-Place eDiscovery &amp; Hold** properties page, click **In-Place Hold**, uncheck the **Place content matching the search query in selected mailboxes on hold** box, and then click **Save**.
    
5. On the **In-Place eDiscovery &amp; Hold** page, select the In-Place Hold again, and then click **Delete**![Delete icon](../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).
    
6. Nell'avviso, fare clic su **Sì** per eliminare il blocco sul posto. 
    
#### <a name="use-exchange-online-powershell-to-delete-an-in-place-hold"></a>Utilizzare PowerShell di Exchange Online per eliminare un blocco sul posto

1. Create a variable that contains the properties of the In-Place Hold that you want to delete. Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).
    
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

1. If you know the name of the In-Place Hold that's placed on the inactive mailbox, you can go to the next step. Otherwise, run the following command to get the name of the In-Place Hold placed on the mailbox. Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).
    
   ```powershell
   Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
   ```

2. In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.
    
3. Selezionare il blocco sul posto applicato alla cassetta postale inattiva, quindi fare clic su **modifica** ![ icona modifica ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) .
    
4. On the **In-Place eDiscovery &amp; Hold** properties page, click **Sources**.
    
5. Nell'elenco delle cassette postali di origine, fare clic sul nome della cassetta postale inattiva che si desidera rimuovere, quindi fare clic su **Rimuovi**![Icona Rimuovi](../media/adf01106-cc79-475c-8673-065371c1897b.gif).
    
6. Click **Save** to save the change. A message is displayed saying the operation was successfully completed. 
    
7. Ripetere i passaggi da 1 a 6 per rimuovere altri blocchi sul posto applicati alla cassetta postale inattiva.
    
#### <a name="use-exchange-online-powershell-to-remove-an-inactive-mailbox-from-an-in-place-hold"></a>Utilizzare PowerShell di Exchange Online per rimuovere una cassetta postale inattiva da un blocco sul posto

If the In-Place Hold contains a large number of source mailboxes, it's possible the inactive mailbox won't be listed on the **Sources** page in the EAC. Up to 3,000 mailboxes are displayed on the **Sources** page when you edit an In-Place Hold. If an inactive mailbox isn't listed on the **Sources** page, you can use Exchange Online PowerShell to remove it from the In-Place Hold. 
  
1. Create a variable that contains the properties of the In-Place Hold placed on the inactive mailbox. Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).
    
    ```powershell
    $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
    ```

2. Verificare che la cassetta postale inattiva sia elencata come cassetta postale di origine per il blocco sul posto. 
    
   ```powershell
   $InPlaceHold.Sources
   ```

   **Nota:** La proprietà *Sources* del blocco sul posto identifica le cassette postali di origine in base alle rispettive proprietà *legacyExchangeDN* . Poiché questa proprietà identifica le cassette postali inattive in modo univoco, l'utilizzo della proprietà *Sources* dal blocco sul posto consente di evitare la rimozione della cassetta postale errata. Ciò consente inoltre di evitare problemi se due cassette postali hanno lo stesso alias o indirizzo SMTP. 
   
3. Remove the inactive mailbox from the list of source mailboxes in the variable. Be sure to use the **LegacyExchangeDN** of the inactive mailbox that's returned by the command in the previous step. 
    
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

- **An inactive mailbox is a type of soft-deleted mailbox.** In Exchange Online, a soft-deleted mailbox is a mailbox that's been deleted but can be recovered within a specific retention period. The soft-deleted mailbox retention period in Exchange Online is 30 days. This means that the mailbox can be recovered within 30 days of being soft-deleted. After 30 days, a soft-deleted mailbox is marked for permanent deletion and can't be recovered. 
    
- **Cosa succede dopo aver rimosso il blocco su una cassetta postale inattiva?** La cassetta postale viene considerata come altre cassette postali con eliminazione temporanea e viene contrassegnata per l'eliminazione definitiva alla scadenza del periodo di conservazione di 30 giorni. Questo periodo di conservazione inizia alla data in cui la cassetta postale viene resa inattiva. Questa data è nota come la data di eliminazione temporanea, ovvero la data in cui l'account utente corrispondente è stato eliminato o quando la cassetta postale di Exchange Online è stata eliminata con il cmdlet **Remove-Mailbox** . La data di eliminazione temporanea non è la data in cui si rimuove il blocco. 
    
- **Is an inactive mailbox permanently deleted immediately after the hold is removed?** If the soft-deleted date for an inactive mailbox is older than 30 days, the mailbox won't be permanently deleted as soon as you remove the hold. The mailbox will be marked for permanent deletion and is deleted the next time it's processed. 
    
- **In che modo il periodo di conservazione delle cassette postali con eliminazione temporanea influisce sulle cassette postali inattive?** Se la data di eliminazione temporanea di una cassetta postale inattiva risale a più di 30 giorni prima della data in cui è stato rimosso il blocco, la cassetta postale viene contrassegnata per l'eliminazione definitiva. Tuttavia, se una cassetta postale inattiva ha una data di eliminazione temporanea entro gli ultimi 30 giorni e si rimuove il blocco, è possibile ripristinare la cassetta postale fino a quando non scade il periodo di conservazione delle cassette postali con eliminazione temporanea. Per ulteriori dettagli, vedere [Eliminare o ripristinare le cassette postali utente in Exchange Online](https://go.microsoft.com/fwlink/?linkid=856835). Alla scadenza del periodo di conservazione delle cassette postali con eliminazione temporanea, è necessario seguire le procedure per il ripristino di una cassetta postale inattiva. Per ulteriori informazioni, vedere [recuperare una cassetta postale inattiva in Office 365](recover-an-inactive-mailbox.md).
    
- **Come vengono visualizzate le informazioni su una cassetta postale inattiva dopo la rimozione del blocco?** Dopo la rimozione di un'esenzione e la cassetta postale inattiva viene ripristinata a una cassetta postale eliminata temporaneamente, non verrà restituita utilizzando il parametro *InactiveMailboxOnly* con il cmdlet **Get-Mailbox** . Tuttavia, è possibile visualizzare le informazioni sulla cassetta postale utilizzando il comando **Get-Mailbox -SoftDeletedMailbox**. Ad esempio: 
    
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

  Nell'esempio precedente, la proprietà *WhenSoftDeleted* identifica la data di eliminazione temporanea, che in questo esempio è il 30 ottobre 2014. Se questa cassetta postale eliminata temporaneamente è stata precedentemente una cassetta postale inattiva per la quale è stato rimosso il blocco, verrà eliminato definitivamente 30 giorni dopo il valore della proprietà *WhenSoftDeleted* . In questo caso, la cassetta postale viene eliminata definitivamente dopo il 30 novembre 2014.

