---
title: Inserire un In-Place blocco su una cassetta postale eliminata in Exchange Online
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
ms.custom:
- seo-marvel-apr2020
description: Informazioni su come creare un blocco In-Place per una cassetta postale eliminata in modo resciso per renderla inattiva e conservarne il contenuto.
ms.openlocfilehash: d72a5407bfafabed30466447e404cdd4196678ae
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226096"
---
# <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-in-exchange-online"></a>Inserire un In-Place blocco su una cassetta postale eliminata in Exchange Online

Informazioni su come creare un blocco In-Place per una cassetta postale eliminata in modo resciso per renderla inattiva e conservarne il contenuto. È quindi possibile utilizzare gli strumenti di Microsoft eDiscovery per eseguire ricerche nella cassetta postale inattiva.

> [!IMPORTANT]
> Mentre continuiamo a investire in modi diversi per conservare il contenuto delle cassette postali, annunciamo il ritiro delle esenzioni In-Place nell'interfaccia di amministrazione di Exchange (EAC). A partire dal 1° luglio 2020 non sarà possibile creare nuove esenzioni In-Place in Exchange Online. Tuttavia, sarà comunque possibile gestire In-Place blocchi nell'interfaccia di amministrazione di Exchange o utilizzando il cmdlet **Set-MailboxSearch** in Exchange Online PowerShell. Tuttavia, a partire dal 1° ottobre 2020, non sarà possibile gestire le In-Place esenzioni. Sarà possibile rimuoverli solo nell'interfaccia di amministrazione di Exchange o utilizzando il cmdlet **Remove-MailboxSearch.** Per ulteriori informazioni sul ritiro delle In-Place, vedere [Ritiro degli strumenti di eDiscovery legacy.](legacy-ediscovery-retirement.md)

Potrebbe verificarsi una situazione in cui una persona ha lasciato l'organizzazione e l'account utente e la cassetta postale corrispondenti sono stati eliminati. In seguito, ci si rende conto che nella cassetta postale sono presenti informazioni che devono essere conservate. Cosa potete fare? Se il periodo di conservazione della cassetta postale eliminata non è scaduto, è possibile impostare un blocco In-Place sulla cassetta postale eliminata (denominata cassetta postale eliminata in modo reversivi) e renderla una cassetta postale inattiva. Una  *cassetta postale inattiva*  viene utilizzata per conservare la posta elettronica di un ex dipendente dopo aver lasciato l'organizzazione. Il contenuto di una cassetta postale inattiva viene conservato per tutta la durata del blocco In-Place che è stato inserito nella cassetta postale eliminata in modo reversivo quando è stata resa inattiva. Dopo aver reso inattiva la cassetta postale, è possibile eseguire ricerche nella cassetta postale utilizzando In-Place eDiscovery in Exchange Online, Ricerca contenuto nel Centro sicurezza & conformità o centro eDiscovery in SharePoint Online.

> [!NOTE]
> In Exchange Online, una cassetta postale con eliminazione temporanea è una cassetta postale che è stata eliminata, ma che può essere recuperata entro un periodo di conservazione specifico. Il periodo di conservazione delle cassette postali con eliminazione temporanea in Exchange Online è pari a 30 giorni. Ciò significa che la cassetta postale può essere recuperata (o resa una cassetta postale inattiva) entro 30 giorni dall'eliminazione. Dopo 30 giorni, una cassetta postale eliminata definitivamente viene contrassegnata per l'eliminazione permanente e non può essere ripristinata o resa inattiva.

## <a name="requirements-for-in-place-holds"></a>Requisiti per le In-Place di archiviazione

- È necessario utilizzare il cmdlet **New-MailboxSearch** in Windows PowerShell per In-Place blocco su una cassetta postale eliminata in modo recidiva. Non è possibile utilizzare l'interfaccia Exchange (EAC) o il Centro eDiscovery in SharePoint Online.

- Per informazioni su come usare Windows PowerShell per connettersi a Exchange Online, vedere [Connessione a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

- Eseguire il comando seguente per ottenere informazioni sull'identità delle cassette postali con eliminazione recidiva nell'organizzazione.

  ```powershell
  Get-Mailbox -SoftDeletedMailbox | FL Name,WhenSoftDeleted,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

- Per ulteriori informazioni sulle cassette postali inattive, vedere [Overview of inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).

## <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-to-make-it-an-inactive-mailbox"></a>Inserire un In-Place blocco su una cassetta postale eliminata in modo resciso per renderla una cassetta postale inattiva

Utilizzare il cmdlet **New-MailboxSearch** per fare in modo che una cassetta postale eliminata in modo resciso sia una cassetta postale inattiva. Per ulteriori informazioni, vedere [New-MailboxSearch](/powershell/module/exchange/new-mailboxsearch).

1. Creare una variabile contenente le proprietà della cassetta postale eliminata in modo recidiva.

   ```powershell
   $SoftDeletedMailbox = Get-Mailbox -SoftDeletedMailbox -Identity <identity of soft-deleted mailbox>
   ```

    > [!IMPORTANT]
    > Nel comando precedente, utilizzare il valore della **proprietà DistinguishedName** o **ExchangeGuid** per identificare la cassetta postale eliminata in modo recidiva. Queste proprietà sono univoche per ogni cassetta postale dell'organizzazione, mentre è possibile che una cassetta postale attiva e una cassetta postale eliminata in modo reciso abbia lo stesso indirizzo SMTP primario.

2. Creare un In-Place e posizionarlo nella cassetta postale eliminata in modo recidiva. In questo esempio non viene specificata alcuna durata del blocco. Ciò significa che gli elementi verranno mantenuti a tempo indeterminato o finché il blocco non viene rimosso dalla cassetta postale inattiva.

   ```powershell
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true
    ```

   È inoltre possibile specificare una durata del blocco quando si crea l'In-Place blocco. In questo esempio vengono conservati gli elementi nella cassetta postale inattiva per circa 7 anni.

   ```powershell
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true -ItemHoldPeriod 2777
   ```

3. Dopo alcuni istanti, eseguire uno dei comandi seguenti per verificare che la cassetta postale eliminata in modo reversibili sia una cassetta postale inattiva.

   ```powershell
   Get-Mailbox -InactiveMailboxOnly
   ```

    Oppure

   ```powershell
   Get-Mailbox -InactiveMailboxOnly -Identity $SoftDeletedMailbox.DistinguishedName  | FL IsInactiveMailbox
   ```

## <a name="more-information"></a>Ulteriori informazioni

Dopo aver fatto di una cassetta postale eliminata in modo recidiva una cassetta postale inattiva, è possibile gestire la cassetta postale in diversi modi. Per altre informazioni, vedere:

- [Cambiare la durata del blocco per una cassetta postale inattiva](change-the-hold-duration-for-an-inactive-mailbox.md)

- [Recuperare una cassetta postale inattiva](recover-an-inactive-mailbox.md)

- [Ripristinare una cassetta postale inattiva](restore-an-inactive-mailbox.md)

- [Eliminare una cassetta postale inattiva](delete-an-inactive-mailbox.md) (rimuovendo il blocco)