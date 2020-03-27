---
title: Inserire un blocco sul posto di una cassetta postale eliminata in modo reversibile in Exchange Online
f1.keywords:
- NOCSH
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
ms.openlocfilehash: 1986a4bfca72c192b268984b7d2f49eb2e88134a
ms.sourcegitcommit: 7646e2d742d1b2fad085a00200a2a10461dd4bac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/26/2020
ms.locfileid: "42978156"
---
# <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-in-exchange-online"></a>Inserire un blocco sul posto di una cassetta postale eliminata in modo reversibile in Exchange Online

Informazioni su come creare un blocco sul posto per una cassetta postale eliminata temporaneamente per renderla inattiva e conservarne il contenuto. È quindi possibile utilizzare gli strumenti di Microsoft eDiscovery per cercare la cassetta postale inattiva.

> [!IMPORTANT]
> Continuando a investire in modi diversi per conservare il contenuto delle cassette postali, si annuncia la previdenza delle archiviazioni sul posto nell'interfaccia di amministrazione di Exchange (EAC). A partire dal 1 ° luglio 2020 non è possibile creare nuove archiviazioni sul posto in Exchange Online. Tuttavia, sarà comunque possibile gestire le archiviazioni sul posto in EAC o utilizzando il cmdlet **Set-MailboxSearch** in Exchange Online PowerShell. Tuttavia, a partire dal 1 ° ottobre 2020, non sarà possibile gestire le archiviazioni sul posto. Verranno rimossi solo nell'interfaccia di amministrazione di Exchange o tramite il cmdlet **Remove-MailboxSearch** . Per ulteriori informazioni sul pensionamento delle archiviazioni sul posto, vedere [pensionamento degli strumenti di eDiscovery legacy](legacy-ediscovery-retirement.md).
  
Potrebbe verificarsi una situazione in cui una persona ha lasciato la propria organizzazione e l'account utente e la cassetta postale corrispondenti sono stati eliminati. Successivamente, si rende conto che esistono informazioni nella cassetta postale che devono essere conservate. Cosa potete fare? Se il periodo di conservazione della cassetta postale eliminata non è scaduto, è possibile applicare un blocco sul posto alla cassetta postale eliminata (denominata cassetta postale eliminata temporaneamente) e renderla una cassetta postale inattiva. Una *cassetta postale inattiva* viene utilizzata per mantenere la posta elettronica di un ex dipendente dopo che lui o lei lascia l'organizzazione. I contenuti di una cassetta postale inattiva vengono conservati per la durata del blocco sul posto che è stato inserito nella cassetta postale eliminata temporaneamente quando è stato reso inattivo. Dopo che la cassetta postale è stata resa inattiva, è possibile eseguire una ricerca nella cassetta postale utilizzando eDiscovery sul posto in Exchange Online, ricerca contenuto nel centro sicurezza & Compliance o eDiscovery Center in SharePoint Online. 
  
> [!NOTE]
> In Exchange Online, una cassetta postale con eliminazione temporanea è una cassetta postale che è stata eliminata, ma che può essere recuperata entro un periodo di conservazione specifico. Il periodo di conservazione delle cassette postali con eliminazione temporanea in Exchange Online è pari a 30 giorni. Questo significa che la cassetta postale può essere recuperata (o resa una cassetta postale inattiva) entro 30 giorni dall'eliminazione. Dopo 30 giorni, una cassetta postale eliminata temporaneamente è contrassegnata per l'eliminazione definitiva e non può essere recuperata o resa inattiva. 
  
## <a name="before-you-begin"></a>Prima di iniziare

- È necessario utilizzare il cmdlet **New-MailboxSearch** in Windows PowerShell per attivare il blocco sul posto di una cassetta postale eliminata temporaneamente. Non è possibile utilizzare l'interfaccia di amministrazione di Exchange (EAC) o il centro eDiscovery in SharePoint Online. 

- Per informazioni su come usare Windows PowerShell per connettersi a Exchange Online, vedere [Connessione a Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).

- Eseguire il seguente comando per ottenere informazioni sull'identità delle cassette postali eliminate temporaneamente nell'organizzazione. 

  ```powershell
  Get-Mailbox -SoftDeletedMailbox | FL Name,WhenSoftDeleted,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

- Per ulteriori informazioni sulle cassette postali inattive, vedere [Overview of inactive Mailboxes in Office 365](inactive-mailboxes-in-office-365.md).

## <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-to-make-it-an-inactive-mailbox"></a>Inserire un blocco sul posto di una cassetta postale eliminata temporaneamente per renderla una cassetta postale inattiva

Utilizzare il cmdlet **New-MailboxSearch** per rendere una cassetta postale eliminata in maniera reversibile una cassetta postale inattiva. Per ulteriori informazioni, vedere [New-MailboxSearch](https://technet.microsoft.com/library/74303b47-bb49-407c-a43b-590356eae35c.aspx).
  
1. Creare una variabile che contiene le proprietà della cassetta postale eliminata temporaneamente.

   ```powershell
   $SoftDeletedMailbox = Get-Mailbox -SoftDeletedMailbox -Identity <identity of soft-deleted mailbox>
   ```

    > [!IMPORTANT]
    > Nel comando precedente, utilizzare il valore della proprietà **Distinguished** o **ExchangeGuid** per identificare la cassetta postale eliminata temporaneamente. Queste proprietà sono univoche per ogni cassetta postale dell'organizzazione, mentre è possibile che una cassetta postale attiva e una cassetta postale eliminata temporaneamente possano avere lo stesso indirizzo SMTP primario. 
  
2. Creare un blocco sul posto e inserirlo nella cassetta postale eliminata temporaneamente. In questo esempio non viene specificata alcuna durata del blocco. Questo significa che gli elementi vengono conservati a tempo indeterminato o fino a quando il blocco non viene rimosso dalla cassetta postale inattiva.

   ```powershell
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true
    ```

   È inoltre possibile specificare una durata del blocco quando si crea il blocco sul posto. In questo esempio vengono mantenute gli elementi della cassetta postale inattiva per circa 7 anni.

   ```powershell
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true -ItemHoldPeriod 2777
   ```

3. Dopo alcuni istanti, eseguire uno dei comandi seguenti per verificare che la cassetta postale eliminata temporaneamente sia una cassetta postale inattiva.

   ```powershell
   Get-Mailbox -InactiveMailboxOnly
   ```

    Oppure
    
   ```powershell
   Get-Mailbox -InactiveMailboxOnly -Identity $SoftDeletedMailbox.DistinguishedName  | FL IsInactiveMailbox
   ```

## <a name="more-information"></a>Ulteriori informazioni

Dopo aver reso una cassetta postale eliminata in maniera reversibile una cassetta postale inattiva, è possibile gestire la cassetta postale in diversi modi. Per altre informazioni, vedere:
  
- [Cambiare la durata del blocco per una cassetta postale inattiva](change-the-hold-duration-for-an-inactive-mailbox.md)

- [Recuperare una cassetta postale inattiva](recover-an-inactive-mailbox.md)

- [Ripristinare una cassetta postale inattiva](restore-an-inactive-mailbox.md)

- [Eliminare una cassetta postale inattiva](delete-an-inactive-mailbox.md) (rimuovendo il blocco)
