---
title: Ripristinare una cassetta postale inattiva
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 97e06a7a-ef9a-4ce8-baea-18b9e20449a3
description: Informazioni su come ripristinare (o unire) il contenuto di una cassetta postale inattiva in una cassetta postale esistente in Office 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bc9039d21f76affce7f58f1f83597dd9e5eb4ecf
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917300"
---
# <a name="restore-an-inactive-mailbox"></a>Ripristinare una cassetta postale inattiva

Una cassetta postale inattiva (che è un tipo di cassetta postale eliminata temporaneamente) viene utilizzata per mantenere la posta elettronica di un precedente dipendente dopo che quest'ultimo ha lasciato l'organizzazione. Se un altro dipendente assume le responsabilità del dipendente rimosso o se quest'ultimo ritorna nell'organizzazione, esistono due modi che consentono di rendere disponibile il contenuto della cassetta postale inattiva a un utente:

- **Ripristinare una cassetta postale inattiva** Se l'altro dipendente assume le responsabilità di un dipendente rimosso o se un altro utente deve accedere al contenuto della cassetta postale inattiva, è possibile ripristinare (o unire) il contenuto della cassetta postale inattiva in una cassetta postale esistente. È inoltre possibile ripristinare l'archivio da una cassetta postale inattiva. Dopo il ripristino, la cassetta postale inattiva viene mantenuta e viene conservata come una cassetta postale inattiva. In questo argomento vengono descritte le procedure per il ripristino di una cassetta postale inattiva.

- **Recuperare una cassetta postale inattiva** Se il dipendente rimosso torna nell'organizzazione oppure se un nuovo dipendente viene assunto per ricoprire il ruolo del dipendente rimosso, è possibile recuperare i contenuti della cassetta postale inattiva. Questo metodo consente di convertire la cassetta postale inattiva in una nuova cassetta postale con il contenuto della cassetta postale inattiva. Dopo essere stata recuperata, la cassetta postale inattiva non esiste più. Per le procedure dettagliate, vedere [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).

Per ulteriori [informazioni sulle](#more-information) differenze tra il ripristino e il ripristino di una cassetta postale inattiva, vedere la sezione Ulteriori informazioni in questo articolo.

> [!NOTE]
> Non è possibile recuperare o ripristinare una cassetta postale inattiva configurata con un archivio con espansione automatica. Se è necessario recuperare i dati da una cassetta postale inattiva con un archivio con espansione automatica, utilizzare la ricerca contenuto per esportare i dati dalla cassetta postale e quindi importare in un'altra cassetta postale. Per istruzioni, vedere gli argomenti seguenti:
>
> - [Ricerca contenuto](content-search.md)
> - [Esportare i risultati della ricerca di contenuto](export-search-results.md)

## <a name="requirements-to-restore-an-inactive-mailbox"></a>Requisiti per ripristinare una cassetta postale inattiva

- È necessario utilizzare Exchange Online PowerShell per ripristinare una cassetta postale inattiva. Non è possibile usare l'interfaccia di amministrazione di Exchange (EAC). Per istruzioni dettagliate, vedere [Connettersi a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

- Eseguire il comando seguente in Exchange Online PowerShell per ottenere informazioni sull'identità per le cassette postali inattive nell'organizzazione.

  ```powershell
  Get-Mailbox -InactiveMailboxOnly | Format-List Name,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

  Utilizzare le informazioni restituite da questo comando per ripristinare una cassetta postale inattiva specifica.

- Per ulteriori informazioni sulle cassette postali inattive, vedere [Cassette postali inattive in Office 365](inactive-mailboxes-in-office-365.md).

## <a name="restore-inactive-mailboxes"></a>Ripristinare le cassette postali inattive

Utilizzare il cmdlet **New-MailboxRestoreRequest** con i parametri  _SourceMailbox_ e  _TargetMailbox_ per ripristinare il contenuto di una cassetta postale inattiva in una cassetta postale esistente. Per ulteriori informazioni sull'utilizzo di questo cmdlet, vedere [New-MailboxRestoreRequest](/powershell/module/exchange/new-mailboxrestorerequest).

1. Creare una variabile che contiene le proprietà della cassetta postale inattiva.

   ```powershell
   $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
   ```

   > [!IMPORTANT]
   > Nel comando precedente, usare il valore della proprietà **DistinguishedName** o **ExchangeGUID** per identificare la cassetta postale inattiva. Queste proprietà sono univoche per ogni cassetta postale nell'organizzazione, mentre è possibile che una cassetta postale attiva e una cassetta postale inattiva possano avere lo stesso indirizzo SMTP primario.

2. Ripristinare il contenuto della cassetta postale inattiva in una cassetta postale esistente. Il contenuto della cassetta postale inattiva (cassetta postale di origine) viene unito nelle cartelle corrispondenti nella cassetta postale esistente (cassetta postale di destinazione).

   ```powershell
   New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -TargetMailbox newemployee@contoso.com -AllowLegacyDNMismatch
   ```

   In alternativa, è possibile specificare una cartella di primo livello nella cassetta postale di destinazione in cui si desidera ripristinare il contenuto dalla cassetta postale inattiva. Se la cartella di destinazione specificata o la struttura di cartelle di destinazione non esiste già nella cassetta postale di destinazione, viene creata durante il processo di ripristino.

   Questo esempio consente di copiare elementi e sottocartelle da una cassetta postale inattiva a una cartella denominata "Cassetta postale inattiva" nella struttura di cartelle di primo livello della cassetta postale di destinazione.

   ```powershell
   New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -TargetMailbox newemployee@contoso.com -TargetRootFolder "Inactive Mailbox" -AllowLegacyDNMismatch
   ```

## <a name="restore-the-archive-from-an-inactive-mailbox"></a>Ripristinare l'archivio da una cassetta postale inattiva

Se una cassetta postale inattiva dispone di una cassetta postale di archiviazione, è anche possibile ripristinarla nella cassetta postale di archiviazione di una cassetta postale esistente. Per ripristinare l'archivio da una cassetta postale inattiva, è necessario aggiungere le opzioni _SourceIsArchive_ e _TargetIsArchive_ al comando utilizzato per ripristinare una cassetta postale inattiva.

1. Creare una variabile che contiene le proprietà della cassetta postale inattiva.

   ```powershell
   $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
   ```

   > [!NOTE]
   > Nel comando precedente, usare il valore della proprietà **DistinguishedName** o **ExchangeGUID** per identificare la cassetta postale inattiva. Queste proprietà sono univoche per ogni cassetta postale nell'organizzazione, mentre è possibile che una cassetta postale attiva e una cassetta postale inattiva possano avere lo stesso indirizzo SMTP primario.

2. Ripristinare il contenuto dell'archivio dalla cassetta postale inattiva (archivio di origine) all'archivio di una cassetta postale esistente (archivio di destinazione). In questo esempio, il contenuto dell'archivio di origine viene copiato in una cartella denominata "Archivio della cassetta postale inattiva" nell'archivio della cassetta postale di destinazione.

   ```powershell
   New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -SourceIsArchive -TargetMailbox newemployee@contoso.com -TargetIsArchive -TargetRootFolder "Inactive Mailbox Archive" -AllowLegacyDNMismatch
   ```

## <a name="more-information"></a>Ulteriori informazioni

- **Qual è la differenza principale tra il recupero e il ripristino di una cassetta postale inattiva?** When you recover an inactive mailbox, the mailbox is basically converted to a new mailbox, the contents and folder structure of the inactive mailbox are retained, and the mailbox is linked to a new user account. After it's recovered, the inactive mailbox no longer exists, and any changes made to the content in the new mailbox will affect the content that was originally on hold in the inactive mailbox. Conversely, when you restore an inactive mailbox, the contents are merely copied to another mailbox. The inactive mailbox is preserved and remains an inactive mailbox. Any changes made to the content in the target mailbox won't affect the original content held in the inactive mailbox. La cassetta postale inattiva può comunque essere ricercata utilizzando lo strumento Ricerca [contenuto,](content-search.md)il relativo contenuto può essere ripristinato in un'altra cassetta postale oppure può essere ripristinato o eliminato in un secondo momento.

- **Come si trovano le cassette postali inattive?** Per ottenere un elenco delle cassette postali inattive nell'organizzazione e visualizzare le informazioni utili per il ripristino di una cassetta postale inattiva, è possibile eseguire questo comando.

  ```powershell
  Get-Mailbox -InactiveMailboxOnly | Format-List Name,PrimarySMTPAddress,DistinguishedName,ExchangeGUID,LegacyExchangeDN,ArchiveStatus
  ```

- **Utilizzare un blocco per controversia legale o un Microsoft 365 di conservazione per conservare il contenuto della cassetta postale inattiva.** Se si desidera mantenere lo stato di una cassetta postale inattiva dopo [](create-a-litigation-hold.md) il ripristino, è possibile applicare un criterio di conservazione per controversia legale alla cassetta postale di destinazione o applicare un criterio di conservazione [Microsoft 365](retention.md) prima di ripristinare la cassetta postale inattiva. Ciò impedirà l'eliminazione definitiva degli elementi della cassetta postale inattiva dopo averli ripristinati nella cassetta postale di destinazione.

- **Abilitare il blocco della conservazione sulla cassetta postale di destinazione prima di ripristinare una cassetta postale inattiva.** Poiché gli elementi di una cassetta postale inattiva potrebbero non essere recenti, prendere in considerazione di abilitare un blocco della conservazione alla cassetta postale di destinazione prima di ripristinare una cassetta postale inattiva. Quando si applica un blocco della conservazione a una cassetta postale, il criterio di conservazione assegnato non verrà elaborato finché il blocco della conservazione non viene rimosso o scade. In questo modo il proprietario della cassetta postale di destinazione ha tutto il tempo per gestire i messaggi meno recenti della cassetta postale inattiva. In caso contrario, i criteri di conservazione potrebbero eliminare gli elementi meno recenti (o spostarli nella cassetta postale di archiviazione, se abilitata) che sono scaduti in base alle impostazioni di conservazione configurate per la cassetta postale di destinazione. Per ulteriori informazioni, vedere [Place a mailbox on retention hold in Exchange Online](/exchange/security-and-compliance/messaging-records-management/mailbox-retention-hold).

- **Cosa consente di fare l'opzione AllowLegacyDNMismatch?** Negli esempi precedenti sul ripristino di una cassetta postale inattiva, l'opzione **AllowLegacyDNMismatch** viene utilizzata per consentire il ripristino della cassetta postale inattiva in una cassetta postale di destinazione diversa. In un comune scenario di ripristino, l'obiettivo è quello di ripristinare il contenuto in cui le cassette postali di origine e di destinazione sono la stessa cassetta postale. In questo caso, per impostazione predefinita, il cmdlet **New-MailboxRestoreRequest** consente di verificare che il valore della proprietà **LegacyExchangeDN** per le cassette postali di origine e di destinazione sia lo stesso. Ciò impedisce di ripristinare accidentalmente una cassetta postale di origine nella cassetta postale di destinazione errata. Se si tenta di ripristinare una cassetta postale inattiva senza l'utilizzo dell'opzione **AllowLegacyDNMismatch**, il comando potrebbe avere esito negativo se le cassette postali di origine e di destinazione presentano valori diversi per la proprietà **LegacyExchangeDN**.

- **È possibile utilizzare altri parametri con il cmdlet New-MailboxRestoreRequest per implementare scenari di ripristino diversi per le cassette postali inattive.** Ad esempio, è possibile eseguire questo comando per ripristinare l'archivio dalla cassetta postale inattiva nella cassetta postale principale della cassetta postale di destinazione.

  ```powershell
  New-MailboxRestoreRequest -SourceMailbox <inactive mailbox> -SourceIsArchive -TargetMailbox <target mailbox> -TargetRootFolder "Inactive Mailbox Archive" -AllowLegacyDNMismatch
  ```

  È inoltre possibile ripristinare la cassetta postale principale inattiva nell'archivio della cassetta postale di destinazione eseguendo questo comando.

  ```powershell
  New-MailboxRestoreRequest -SourceMailbox <inactive mailbox> -TargetMailbox <target mailbox> -TargetIsArchive -TargetRootFolder "Inactive Mailbox" -AllowLegacyDNMismatch
  ```

- **Cosa consente di fare il parametro TargetRootFolder?** Come descritto in precedenza, è possibile utilizzare il parametro **TargetRootFolder** per specificare una cartella nel livello superiore della struttura della cartella (denominato anche radice) nella cassetta postale di destinazione in cui ripristinare il contenuto della cassetta postale inattiva. Se non si utilizza questo parametro, gli elementi della cassetta postale inattiva vengono uniti in cartelle predefinite corrispondenti della cassetta postale di destinazione e le cartelle personalizzate vengono ricreate nella radice della cassetta postale di destinazione. Le seguenti illustrazioni evidenziano le differenze nell'utilizzo o meno del parametro **TargetRootFolder**.

  **Gerarchia delle cartelle nella cassetta postale di destinazione quando il parametro TargetRootFolder non viene utilizzato**

  ![Schermata visualizzata quando non viene utilizzato il parametro TargetRootFolder](../media/76a759af-f483-4d1c-8cc7-243435b5562e.png)

  **Gerarchia delle cartelle nella cassetta postale di destinazione quando il parametro TargetRootFolder viene utilizzato**

  ![Schermata visualizzata quando viene utilizzato il parametro TargetRootFolder](../media/300da592-7323-48db-b8a4-07012259d113.png)