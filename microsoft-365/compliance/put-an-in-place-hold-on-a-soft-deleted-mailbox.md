---
title: Inserire un blocco sul posto di una cassetta postale eliminata in modo reversibile in Exchange Online
ms.author: markjjo
author: markjjo
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: ''
ms.assetid: 421f72bd-dd43-4be1-82f5-0ae9ac43bd00
description: Informazioni su come creare un blocco sul posto per una cassetta postale eliminata temporaneamente per renderla inattiva e conservarne il contenuto. È quindi possibile utilizzare gli strumenti di Microsoft eDiscovery per cercare la cassetta postale inattiva.
ms.openlocfilehash: ce4121e6187a765b5a9e23d6e6e11d8cc2640161
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37084403"
---
# <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-in-exchange-online"></a>Inserire un blocco sul posto di una cassetta postale eliminata in modo reversibile in Exchange Online

Informazioni su come creare un blocco sul posto per una cassetta postale eliminata temporaneamente per renderla inattiva e conservarne il contenuto. È quindi possibile utilizzare gli strumenti di Microsoft eDiscovery per cercare la cassetta postale inattiva.
  
> [!NOTE]
> È stata posticipata la data di scadenza per la creazione di nuove archiviazioni sul posto in Exchange Online (nei piani autonomi di Office 365 e Exchange Online). Tuttavia, più avanti nel corso di questo anno o all'inizio del prossimo, non sarà più possibile creare blocchi sul posto in Exchange Online. In alternativa all'utilizzo delle archiviazioni sul posto, è possibile utilizzare i criteri di [conservazione](https://go.microsoft.com/fwlink/?linkid=827811) o i [casi di eDiscovery](https://go.microsoft.com/fwlink/?linkid=780738) nel centro sicurezza & Compliance. Dopo la rimozione di nuove esenzioni sul posto, sarà comunque possibile modificare le esenzioni sul posto esistenti e creare nuove archiviazioni sul posto in Exchange Server 2013 e le distribuzioni ibride di Exchange continueranno a essere supportate. Inoltre, sarà ancora possibile applicare un blocco per controversia legale alle cassette postali. 
  
Potrebbe verificarsi una situazione in cui una persona ha lasciato la propria organizzazione e l'account utente e la cassetta postale corrispondenti sono stati eliminati. Successivamente, si rende conto che esistono informazioni nella cassetta postale che devono essere conservate. Cosa potete fare? Se il periodo di conservazione della cassetta postale eliminata non è scaduto, è possibile applicare un blocco sul posto alla cassetta postale eliminata (denominata cassetta postale eliminata temporaneamente) e renderla una cassetta postale inattiva. Una *cassetta postale inattiva* viene utilizzata per mantenere la posta elettronica di un ex dipendente dopo che lui o lei lascia l'organizzazione. I contenuti di una cassetta postale inattiva vengono conservati per la durata del blocco sul posto che è stato inserito nella cassetta postale eliminata temporaneamente quando è stato reso inattivo. Dopo che la cassetta postale è stata resa inattiva, è possibile eseguire una ricerca nella cassetta postale utilizzando eDiscovery sul posto in Exchange Online, ricerca contenuto nel centro sicurezza & Compliance o eDiscovery Center in SharePoint Online. 
  
> [!NOTE]
> In Exchange Online, una cassetta postale con eliminazione temporanea è una cassetta postale che è stata eliminata, ma che può essere recuperata entro un periodo di conservazione specifico. Il periodo di conservazione delle cassette postali con eliminazione temporanea in Exchange Online è pari a 30 giorni. Questo significa che la cassetta postale può essere recuperata (o resa una cassetta postale inattiva) entro 30 giorni dall'eliminazione. Dopo 30 giorni, una cassetta postale eliminata temporaneamente è contrassegnata per l'eliminazione definitiva e non può essere recuperata o resa inattiva. 
  
## <a name="before-you-begin"></a>Informazioni preliminari

- È necessario utilizzare il cmdlet **New-MailboxSearch** in Windows PowerShell per attivare il blocco sul posto di una cassetta postale eliminata temporaneamente. Non è possibile utilizzare l'interfaccia di amministrazione di Exchange (EAC) o il centro eDiscovery in SharePoint Online. 
    
- Per informazioni su come usare Windows PowerShell per connettersi a Exchange Online, vedere [Connessione a Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).
    
- Eseguire il seguente comando per ottenere informazioni sull'identità delle cassette postali eliminate temporaneamente nell'organizzazione. 
    
  ```
  Get-Mailbox -SoftDeletedMailbox | FL Name,WhenSoftDeleted,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

- Per ulteriori informazioni sulle cassette postali inattive, vedere [Overview of inactive Mailboxes in Office 365](inactive-mailboxes-in-office-365.md).
    
## <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-to-make-it-an-inactive-mailbox"></a>Inserire un blocco sul posto di una cassetta postale eliminata temporaneamente per renderla una cassetta postale inattiva

Utilizzare il cmdlet **New-MailboxSearch** per rendere una cassetta postale eliminata in maniera reversibile una cassetta postale inattiva. Per ulteriori informazioni, vedere [New-MailboxSearch](http://technet.microsoft.com/library/74303b47-bb49-407c-a43b-590356eae35c.aspx).
  
1. Creare una variabile che contiene le proprietà della cassetta postale eliminata temporaneamente. 
    
   ```
   $SoftDeletedMailbox = Get-Mailbox -SoftDeletedMailbox -Identity <identity of soft-deleted mailbox>
   ```

    > [!IMPORTANT]
    > Nel comando precedente, utilizzare il valore della proprietà **Distinguished** o **ExchangeGuid** per identificare la cassetta postale eliminata temporaneamente. Queste proprietà sono univoche per ogni cassetta postale dell'organizzazione, mentre è possibile che una cassetta postale attiva e una cassetta postale eliminata temporaneamente possano avere lo stesso indirizzo SMTP primario. 
  
2. Creare un blocco sul posto e inserirlo nella cassetta postale eliminata temporaneamente. In questo esempio non viene specificata alcuna durata del blocco. Questo significa che gli elementi vengono conservati a tempo indeterminato o fino a quando il blocco non viene rimosso dalla cassetta postale inattiva.
    
   ```
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true
    ```
   È inoltre possibile specificare una durata del blocco quando si crea il blocco sul posto. In questo esempio vengono mantenute gli elementi della cassetta postale inattiva per circa 7 anni.
    
   ```
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true -ItemHoldPeriod 2777
   ```

3. Dopo alcuni istanti, eseguire uno dei comandi seguenti per verificare che la cassetta postale eliminata temporaneamente sia una cassetta postale inattiva.
    
   ```
   Get-Mailbox -InactiveMailboxOnly
   ```

    Oppure
    
   ```
   Get-Mailbox -InactiveMailboxOnly -Identity $SoftDeletedMailbox.DistinguishedName  | FL IsInactiveMailbox
   ```

## <a name="more-information"></a>Ulteriori informazioni

Dopo aver reso una cassetta postale eliminata in maniera reversibile una cassetta postale inattiva, è possibile gestire la cassetta postale in diversi modi. Per ulteriori informazioni, vedere:
  
- [Cambiare la durata del blocco per una cassetta postale inattiva](change-the-hold-duration-for-an-inactive-mailbox.md)
    
- [Recuperare una cassetta postale inattiva](recover-an-inactive-mailbox.md)
    
- [Ripristinare una cassetta postale inattiva](restore-an-inactive-mailbox.md)
    
- [Eliminare una cassetta postale inattiva](delete-an-inactive-mailbox.md) (rimuovendo l'esenzione)
