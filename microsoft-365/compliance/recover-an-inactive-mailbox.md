---
title: Recuperare una cassetta postale inattiva
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
ms.assetid: 35d0ecdb-7cb0-44be-ad5c-69df2f8f8b25
ms.custom: seo-marvel-apr2020
description: Informazioni su come recuperare il contenuto di una cassetta postale inattiva in Office 365 converterla in una nuova cassetta postale contenente il contenuto della cassetta postale inattiva.
ms.openlocfilehash: e7f5ea9e3d47bf6b7ee6de495d2f5f47984cdf8f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926174"
---
# <a name="recover-an-inactive-mailbox"></a>Recuperare una cassetta postale inattiva

Una cassetta postale inattiva (che è un tipo di cassetta postale eliminata temporaneamente) viene utilizzata per mantenere la posta elettronica di un precedente dipendente dopo che quest'ultimo ha lasciato l'organizzazione. Se tale dipendente torna nell'organizzazione o se un altro dipendente assume le responsabilità del dipendente precedente, esistono due modi che consentono di rendere disponibile il contenuto della cassetta postale inattiva a un utente:

- **Ripristinare una cassetta postale inattiva.** Se l'ex dipendente torna nell'organizzazione o se un nuovo dipendente viene assunto per assumere le responsabilità professionali dell'ex dipendente, è possibile recuperare il contenuto della cassetta postale inattiva. Questo metodo consente di convertire la cassetta postale inattiva in una nuova cassetta postale attiva con il contenuto della cassetta postale inattiva. Dopo essere stata recuperata, la cassetta postale inattiva non esiste più. Le procedure descritte in questo argomento illustrano tale metodo.

- **Ripristinare una cassetta postale inattiva.** Se un altro dipendente assume le responsabilità lavorative dell'ex dipendente o se un altro utente deve accedere al contenuto della cassetta postale inattiva, è possibile ripristinare (o unire) il contenuto della cassetta postale inattiva in una cassetta postale esistente. È inoltre possibile ripristinare l'archivio da una cassetta postale inattiva. Per le procedure per questo metodo, vedere [Restore an inactive mailbox in Office 365](restore-an-inactive-mailbox.md).

Vedere la sezione [Ulteriori informazioni](#more-information) per maggiori dettagli sulle differenze tra recupero e ripristino di una cassetta postale inattiva, oltre a una descrizione di cosa accade quando viene recuperata una cassetta postale inattiva.

> [!NOTE]
> Non è possibile recuperare o ripristinare una cassetta postale inattiva configurata con un archivio con espansione automatica. Se è necessario recuperare i dati da una cassetta postale inattiva con un archivio con espansione automatica, utilizzare la ricerca contenuto per esportare i dati dalla cassetta postale e quindi importare in un'altra cassetta postale. Per istruzioni, vedere gli argomenti seguenti:
>
> - [Ricerca contenuto](content-search.md)
> - [Esportare i risultati della ricerca di contenuto](export-search-results.md)

## <a name="requirements-to-recover-an-inactive-mailbox"></a>Requisiti per il ripristino di una cassetta postale inattiva

- È necessario utilizzare Exchange Online PowerShell per recuperare una cassetta postale inattiva. Non è possibile usare l'interfaccia di amministrazione di Exchange (EAC). Per istruzioni dettagliate, vedere [Connettersi a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

- Eseguire il seguente comando per ottenere informazioni di identità per le cassette postali inattive dell'organizzazione.

  ```powershell
  Get-Mailbox -InactiveMailboxOnly | Format-List Name,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

  Utilizzare le informazioni restituite da questo comando per recuperare una cassetta postale inattiva specifica.

## <a name="recover-inactive-mailboxes"></a>Ripristinare le cassette postali inattive

Utilizzare il cmdlet **New-Mailbox** con il  *parametro InactiveMailbox*  per ripristinare una cassetta postale inattiva.

1. Creare una variabile che contiene le proprietà della cassetta postale inattiva.

   ```powershell
   $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
   ```

   > [!IMPORTANT]
   > Nel comando precedente, usare il valore della proprietà **DistinguishedName** o **ExchangeGUID** per identificare la cassetta postale inattiva. Queste proprietà sono univoche per ogni cassetta postale nell'organizzazione, mentre è possibile che una cassetta postale attiva e una cassetta postale inattiva possano avere lo stesso indirizzo SMTP primario.

2. In questo esempio vengono utilizzate le proprietà ottenute con il comando precedente e viene recuperata la cassetta postale inattiva in una cassetta postale attiva per l'utente Ann Beebe. Assicurarsi che i valori specificati per i parametri  *Name*  e  *MicrosoftOnlineServicesID*  siano univoci all'interno dell'organizzazione.

   ```powershell
   New-Mailbox -InactiveMailbox $InactiveMailbox.DistinguishedName -Name annbeebe -FirstName Ann -LastName Beebe -DisplayName "Ann Beebe" -MicrosoftOnlineServicesID Ann.Beebe@contoso.com -Password (ConvertTo-SecureString -String 'P@ssw0rd' -AsPlainText -Force) -ResetPasswordOnNextLogon $true
   ```

   L'indirizzo SMTP primario per la cassetta postale inattiva recuperata avrà lo stesso valore di quello specificato dal parametro *MicrosoftOnlineServicesID.*

Dopo il ripristino di una cassetta postale inattiva, viene creato anche un nuovo account utente. Devi attivare questo account utente assegnando una licenza. Per assegnare una licenza nell'Microsoft 365 di amministrazione, vedere Aggiungere utenti e [assegnare licenze contemporaneamente.](../admin/add-users/add-users.md)

## <a name="more-information"></a>Ulteriori informazioni

- **Qual è la differenza principale tra il recupero e il ripristino di una cassetta postale inattiva?** Quando si recupera una cassetta postale inattiva, la cassetta postale viene convertita in una nuova cassetta postale, il contenuto e la struttura della cassetta postale vengono conservati e la cassetta postale viene collegata a un nuovo account utente. After it's recovered, the inactive mailbox no longer exists, and any changes made to the content in the new mailbox will affect the content that was originally on hold in the inactive mailbox. Conversely, when you restore an inactive mailbox, the contents are merely copied to another mailbox. The inactive mailbox is preserved and remains an inactive mailbox. Le eventuali modifiche apportate al contenuto nella cassetta postale di destinazione non vengono applicate al contenuto originale conservato nella cassetta postale inattiva. La cassetta postale inattiva può comunque essere cercata utilizzando eDiscovery sul posto, i suoi contenuti possono essere ripristinati in un'altra cassetta postale oppure può essere recuperata o eliminata in un secondo momento.

- **Cosa accade quando viene recuperata una cassetta postale inattiva?** Quando si recupera una cassetta postale inattiva, si verifica quanto segue:

  - Il blocco applicato a una cassetta postale inattiva viene modificato o rimosso in base al tipo di blocco applicato alla cassetta postale inattiva prima del ripristino.

    - **Conservazione per controversia legale.** Se il blocco per controversia legale è stato abilitato per la cassetta postale inattiva, viene rimosso dalla cassetta postale recuperata.

    - **Le esenzioni sul** In-Place sul posto vengono rimosse dalla cassetta postale recuperata. Ciò significa che la cassetta postale recuperata viene rimossa come cassetta postale di origine da qualsiasi In-Place di archiviazione o In-Place ricerca eDiscovery.

    - **Microsoft 365 criteri di conservazione con blocco di conservazione.** Se la cassetta postale inattiva è stata assegnata a un criterio di conservazione con blocco di conservazione (denominato criterio di conservazione *bloccato),* la cassetta postale recuperata viene assegnata allo stesso criterio di conservazione bloccato. Per ulteriori informazioni sui criteri di conservazione bloccati, vedere [[Use Preservation Lock to restrict changes to retention policies and retention label policies](retention-preservation-lock.md).

    - **Microsoft 365 criteri di conservazione senza blocco di conservazione.** La cassetta postale inattiva viene rimossa da qualsiasi criterio Microsoft 365 di conservazione sbloccato applicato. Tuttavia, il blocco per controversia legale è abilitato sulla cassetta postale recuperata per impedire l'eliminazione del contenuto della cassetta postale in base a qualsiasi criterio di conservazione a livello di organizzazione che elimina contenuto precedente a una data di validità specifica. È possibile mantenere il blocco per controversia legale o rimuoverlo. Per ulteriori informazioni, vedere [Create a Litigation Hold.](create-a-litigation-hold.md)

  - Il periodo di recupero di un singolo elemento (che è definito dalla proprietà della cassetta postale **RetainDeletedItemsFor** ) è impostato su 30 giorni. In genere, quando si crea una nuova cassetta postale in Exchange Online, il periodo di conservazione è impostato su 14 giorni. Impostandolo sul valore massimo di 30 giorni, si ha più tempo per recuperare i dati eliminati definitivamente (o cancellati) dalla cassetta postale inattiva. È anche possibile disabilitare il recupero di un singolo elemento o reimpostare il periodo di conservazione di un singolo elemento sul valore predefinito di 14 giorni. Per ulteriori informazioni, vedere [Enable or disable single item recovery for a mailbox](/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-single-item-recovery).

  - Il blocco della conservazione è abilitato e la sua durata è impostata su 30 giorni. Ciò significa che i criteri di conservazione Exchange predefiniti e tutti i criteri di conservazione Microsoft 365 Exchange a livello di organizzazione o Exchange assegnati alla nuova cassetta postale non verranno elaborati per 30 giorni. In questo modo, il dipendente che ritorna nell'organizzazione o il nuovo proprietario della cassetta postale inattiva ha tutto il tempo di gestire i vecchi messaggi. In caso contrario, il criterio di conservazione Exchange o Microsoft 365 potrebbe eliminare gli elementi della cassetta postale precedente (o spostare gli elementi nella cassetta postale di archiviazione, se abilitata) scaduti in base alle impostazioni configurate per i criteri di conservazione di Exchange o Microsoft 365. Dopo 30 giorni, il blocco della conservazione scade, la proprietà della cassetta postale **RetentionHoldEnabled** viene impostata su **False** e Assistente cartelle gestite avvia l'elaborazione dei criteri assegnati alla cassetta postale. Se non è necessario questo intervallo di tempo aggiuntivo, è possibile rimuovere il blocco della conservazione. In alternativa, è possibile aumentare la durata del blocco della conservazione utilizzando il comando **Set-Mailbox -EndDateForRetentionHold**. Per ulteriori informazioni, vedere [Place a mailbox on retention hold](/exchange/security-and-compliance/messaging-records-management/mailbox-retention-hold).

- **Mettere un blocco sulla cassetta postale recuperata se è necessario mantenere lo stato originale della cassetta postale inattiva.** Per evitare che il nuovo proprietario o il nuovo criterio di conservazione elimini definitivamente i messaggi dalla cassetta postale inattiva ripristinata, è possibile impostare il blocco per controversia legale per la cassetta postale. Per ulteriori informazioni, vedere [Create a Litigation Hold.](./create-a-litigation-hold.md)

- **Quale ID utente è possibile utilizzare quando si recupera una cassetta postale inattiva?** Quando si recupera una cassetta postale inattiva, il valore specificato per il parametro  *MicrosoftOnlineServicesID*  può essere diverso da quello originale associato alla cassetta postale inattiva. È inoltre possibile utilizzare l'ID utente originale. Tuttavia, come indicato in precedenza, assicurarsi che i valori utilizzati per  *Name*  e  *MicrosoftOnlineServicesID*  siano univoci all'interno dell'organizzazione quando si recupera la cassetta postale inattiva.

- **Cosa fare se il periodo di conservazione della cassetta postale inattiva è scaduto?** Se una cassetta postale inattiva è stata eliminata temporaneamente meno di 30 giorni prima, non è possibile utilizzare il comando **New-Mailbox -InactiveMailbox** per recuperarla. È necessario ripristinarlo ripristinando l'account utente corrispondente. Per ulteriori informazioni, vedere [Delete a user from your organization](../admin/add-users/delete-a-user.md).

- **Come si stabilisce se il periodo di conservazione di una cassetta postale inattiva eliminata temporaneamente è scaduto?** Eseguire il comando riportato di seguito.

  ```powershell
  Get-Mailbox -InactiveMailboxOnly <identity of inactive mailbox> | Format-List ExternalDirectoryObjectId
  ```

  Se non è presente un valore per la proprietà **ExternalDirectoryObjectId**, il periodo di conservazione della cassetta postale è scaduto ed è possibile recuperare la cassetta postale inattiva eseguendo il comando **New-Mailbox -InactiveMailbox**. Se è presente un valore per la proprietà **ExternalDirectoryObjectId,** il periodo di conservazione della cassetta postale eliminata in modo reverso non è scaduto ed è necessario ripristinare la cassetta postale ripristinando l'account utente. Vedere [Eliminare un utente dall'organizzazione](../admin/add-users/delete-a-user.md).

- **Prendere in considerazione l'abilitazione della cassetta postale di archiviazione dopo aver recuperato la cassetta postale inattiva.** In questo modo l'utente che ritorna nell'organizzazione o il nuovo dipendente possono spostare i vecchi messaggi nella cassetta postale di archiviazione. Quando scade il blocco della conservazione, i criteri di archiviazione che fanno parte dei criteri di conservazione predefiniti di Exchange assegnati alle cassette postali di Exchange Online spostano gli elementi risalenti ad almeno due anni prima nella cassetta postale di archiviazione. Se non si abilita la cassetta postale di archiviazione, gli elementi risalenti a più di due anni prima rimarranno nella cassetta postale principale dell'utente. Per ulteriori informazioni, vedere [Enable archive mailboxes](enable-archive-mailboxes.md).