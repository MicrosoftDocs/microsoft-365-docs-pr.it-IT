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
description: Informazioni su come ripristinare il contenuto di una cassetta postale inattiva in Office 365 mediante la conversione in una nuova cassetta postale contenente il contenuto della cassetta postale inattiva.
ms.openlocfilehash: 077355d31c3159b4970b00ee9c461d6a77cd3cf7
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2020
ms.locfileid: "45127463"
---
# <a name="recover-an-inactive-mailbox"></a>Recuperare una cassetta postale inattiva

An inactive mailbox (which is a type of soft-deleted mailbox) is used to preserve a former employee's email after he or she leaves your organization. If that employee returns to your organization or if another employee takes on the job responsibilities of the former employee, there are two ways that you can make the contents of the inactive mailbox available to a user: 
  
- **Recuperare una cassetta postale inattiva.** Se l'ex dipendente torna alla propria organizzazione o se viene assunto un nuovo dipendente per assumersi le responsabilità dei processi dell'ex dipendente, è possibile recuperare il contenuto della cassetta postale inattiva. Questo metodo consente di convertire la cassetta postale inattiva in una nuova cassetta postale attiva con il contenuto della cassetta postale inattiva. Dopo essere stata recuperata, la cassetta postale inattiva non esiste più. Le procedure descritte in questo argomento illustrano tale metodo. 
    
- **Ripristinare una cassetta postale inattiva.** Se un altro dipendente assume le responsabilità del processo dell'ex dipendente o se un altro utente deve accedere al contenuto della cassetta postale inattiva, è possibile ripristinare (o unire) il contenuto della cassetta postale inattiva a una cassetta postale esistente. È inoltre possibile ripristinare l'archivio da una cassetta postale inattiva. Per le procedure per questo metodo, vedere [ripristinare una cassetta postale inattiva in Office 365](restore-an-inactive-mailbox.md).

Vedere la sezione [Ulteriori informazioni](#more-information) per maggiori dettagli sulle differenze tra recupero e ripristino di una cassetta postale inattiva, oltre a una descrizione di cosa accade quando viene recuperata una cassetta postale inattiva.
  
## <a name="requirements-to-recover-an-inactive-mailbox"></a>Requisiti per il ripristino di una cassetta postale inattiva

- È necessario utilizzare Exchange Online PowerShell per recuperare una cassetta postale inattiva. Non è possibile usare l'interfaccia di amministrazione di Exchange (EAC). Per istruzioni dettagliate, vedere [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554).
    
- Eseguire il seguente comando per ottenere informazioni di identità per le cassette postali inattive dell'organizzazione. 

    ```powershell
    Get-Mailbox -InactiveMailboxOnly | FL Name,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
    ```

    Utilizzare le informazioni restituite da questo comando per recuperare una cassetta postale inattiva specifica.

## <a name="recover-an-inactive-mailbox"></a>Recuperare una cassetta postale inattiva

Utilizzare il cmdlet **New-Mailbox** con il parametro *InactiveMailbox* per recuperare una cassetta postale inattiva. 
  
1. Creare una variabile che contiene le proprietà della cassetta postale inattiva. 
    
    ```powershell
    $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
    ```

    > [!IMPORTANT]
    > In the previous command, use the value of the **DistinguishedName** or **ExchangeGUID** property to identify the inactive mailbox. These properties are unique for each mailbox in your organization, whereas it's possible that an active and an inactive mailbox might have the same primary SMTP address. 
  
2. In questo esempio vengono utilizzate le proprietà ottenute con il comando precedente e viene recuperata la cassetta postale inattiva in una cassetta postale attiva per l'utente Ann Beebe. Verificare che i valori specificati per i parametri *Name* e *MicrosoftOnlineServicesID* siano univoci all'interno dell'organizzazione. 

    ```powershell
    New-Mailbox -InactiveMailbox $InactiveMailbox.DistinguishedName -Name annbeebe -FirstName Ann -LastName Beebe -DisplayName "Ann Beebe" -MicrosoftOnlineServicesID Ann.Beebe@contoso.com -Password (ConvertTo-SecureString -String 'P@ssw0rd' -AsPlainText -Force) -ResetPasswordOnNextLogon $true
    ```

    L'indirizzo SMTP primario per la cassetta postale inattiva recuperata avrà lo stesso valore di quello specificato dal parametro *MicrosoftOnlineServicesID* . 
    
Dopo aver ripristinato una cassetta postale inattiva, viene creato anche un nuovo account utente. È necessario attivare questo account utente assegnando una licenza. Per assegnare una licenza nell'interfaccia di amministrazione di Microsoft 365, vedere [assegnare o annullare l'assegnazione delle licenze per microsoft 365 for business](https://go.microsoft.com/fwlink/p/?LinkId=276798).
  
## <a name="more-information"></a>Ulteriori informazioni

- **Qual è la differenza principale tra il recupero e il ripristino di una cassetta postale inattiva?** Quando si recupera una cassetta postale inattiva, la cassetta postale viene convertita in una nuova cassetta postale, il contenuto e la struttura della cassetta postale vengono conservati e la cassetta postale viene collegata a un nuovo account utente. After it's recovered, the inactive mailbox no longer exists, and any changes made to the content in the new mailbox will affect the content that was originally on hold in the inactive mailbox. Conversely, when you restore an inactive mailbox, the contents are merely copied to another mailbox. The inactive mailbox is preserved and remains an inactive mailbox. Le eventuali modifiche apportate al contenuto nella cassetta postale di destinazione non vengono applicate al contenuto originale conservato nella cassetta postale inattiva. La cassetta postale inattiva può comunque essere cercata utilizzando eDiscovery sul posto, i suoi contenuti possono essere ripristinati in un'altra cassetta postale oppure può essere recuperata o eliminata in un secondo momento. 

- **Cosa accade quando viene recuperata una cassetta postale inattiva?** Quando si recupera una cassetta postale inattiva, si verifica quanto segue: 

   - Il blocco applicato a una cassetta postale inattiva è stato modificato o rimosso in base al tipo di blocco applicato alla cassetta postale inattiva prima che venisse ripristinato.
  
     - **Blocco per controversia legale.** Se la conservazione per controversia legale è stata abilitata per la cassetta postale inattiva, viene rimossa dalla cassetta postale recuperata.
  
     - Archiviazione **sul posto** Le esenzioni sul posto vengono rimosse dalla cassetta postale recuperata. Questo significa che la cassetta postale recuperata viene rimossa come cassetta postale di origine da qualsiasi blocco sul posto o ricerca eDiscovery sul posto.
     
     - **Criterio di conservazione Microsoft 365 con blocco conservazione.** Se la cassetta postale inattiva è stata assegnata a un criterio di conservazione con blocco conservazione (denominato *criterio di conservazione bloccato*), la cassetta postale recuperata viene assegnata allo stesso criterio di conservazione bloccato. Per ulteriori informazioni sui criteri di conservazione bloccati, vedere [use Preservation Lock to conforme ai requisiti normativi](retention.md#use-preservation-lock-to-comply-with-regulatory-requirements).
  
     - **Criterio di conservazione Microsoft 365 senza blocco conservazione.** La cassetta postale inattiva viene rimossa da qualsiasi criterio di conservazione Microsoft 365 sbloccato che è stato applicato. Tuttavia, il blocco per controversia legale è abilitato sulla cassetta postale recuperata per impedire l'eliminazione del contenuto delle cassette postali in base a criteri di conservazione a livello di organizzazione che eliminano il contenuto antecedente a una determinata età. È possibile mantenere il blocco per controversia legale o rimuoverlo. Per ulteriori informazioni, vedere [creazione di un blocco per controversia legale](create-a-litigation-hold.md).

  - The single item recovery period (which is defined by the **RetainDeletedItemsFor** mailbox property) is set to 30 days. Typically, when a new mailbox is created in Exchange Online, this retention period is set to 14 days. Setting this to the maximum value of 30 days gives you more time to recover any data that's been permanently deleted (or purged) from the inactive mailbox. You can also disable single item recovery or set the single item recovery period back to the default of 14 days. For more information, see [Enable or disable single item recovery for a mailbox](https://go.microsoft.com/fwlink/?linkid=856769).
  
  - Il blocco della conservazione è abilitato e la sua durata è impostata su 30 giorni. Questo significa che i criteri di conservazione di Exchange predefiniti e tutti i criteri di conservazione Microsoft 365 a livello di organizzazione o di Exchange assegnati alla nuova cassetta postale non verranno elaborati per 30 giorni. In questo modo, il dipendente che ritorna nell'organizzazione o il nuovo proprietario della cassetta postale inattiva ha tutto il tempo di gestire i vecchi messaggi. In caso contrario, i criteri di conservazione di Exchange o Microsoft 365 potrebbero eliminare gli elementi della cassetta postale precedenti (o spostare gli elementi nella cassetta postale di archiviazione, se abilitata) che sono scaduti in base alle impostazioni configurate per i criteri di conservazione di Exchange o Microsoft 365. Dopo 30 giorni, il blocco della conservazione scade, la proprietà della cassetta postale **RetentionHoldEnabled** viene impostata su **False** e Assistente cartelle gestite avvia l'elaborazione dei criteri assegnati alla cassetta postale. Se non è necessario questo intervallo di tempo aggiuntivo, è possibile rimuovere il blocco della conservazione. In alternativa, è possibile aumentare la durata del blocco della conservazione utilizzando il comando **Set-Mailbox -EndDateForRetentionHold**. Per ulteriori informazioni, vedere [Place a mailbox on retention hold](https://go.microsoft.com/fwlink/?linkid=856300).

- **Inserire un blocco sulla cassetta postale recuperata se è necessario conservare lo stato originale della cassetta postale inattiva.** Per impedire che il nuovo proprietario della cassetta postale o il criterio di conservazione elimini definitivamente i messaggi dalla cassetta postale inattiva recuperata, è possibile inserire la cassetta postale per il blocco per controversia legale. Per ulteriori informazioni, vedere [posizionare una cassetta postale sul blocco per controversia legale](https://go.microsoft.com/fwlink/?linkid=856286).
    
- **Quale ID utente è possibile utilizzare quando si recupera una cassetta postale inattiva?** Quando si ripristina una cassetta postale inattiva, il valore specificato per il parametro *MicrosoftOnlineServicesID* può essere diverso da quello originale associato alla cassetta postale inattiva. È inoltre possibile utilizzare l'ID utente originale. Tuttavia, come indicato in precedenza, assicurarsi che i valori utilizzati per *Name* e *MicrosoftOnlineServicesID* siano univoci all'interno dell'organizzazione quando si ripristina la cassetta postale inattiva. 
    
- **Cosa fare se il periodo di conservazione della cassetta postale inattiva è scaduto?** Se una cassetta postale inattiva è stata eliminata temporaneamente meno di 30 giorni prima, non è possibile utilizzare il comando **New-Mailbox -InactiveMailbox** per recuperarla. È necessario recuperarla ripristinando l'account utente corrispondente. Per ulteriori informazioni, vedere [Eliminare o ripristinare un utente](https://go.microsoft.com/fwlink/p/?LinkId=279162).
    
- **Come si stabilisce se il periodo di conservazione di una cassetta postale inattiva eliminata temporaneamente è scaduto?** Eseguire il comando riportato di seguito. 
    
    ```powershell
    Get-Mailbox -InactiveMailboxOnly <identity of inactive mailbox> | FL ExternalDirectoryObjectId
  ```

    Se non è presente un valore per la proprietà **ExternalDirectoryObjectId**, il periodo di conservazione della cassetta postale è scaduto ed è possibile recuperare la cassetta postale inattiva eseguendo il comando **New-Mailbox -InactiveMailbox**. Se è presente un valore per la proprietà **ExternalDirectoryObjectId** , il periodo di conservazione della cassetta postale eliminata temporaneamente non è scaduto ed è necessario ripristinare la cassetta postale ripristinando l'account utente. Vedere [Eliminare o ripristinare un utente](https://go.microsoft.com/fwlink/p/?LinkId=279162)
    
- **Prendere in considerazione l'abilitazione della cassetta postale di archiviazione dopo aver recuperato la cassetta postale inattiva.** In questo modo l'utente che ritorna nell'organizzazione o il nuovo dipendente possono spostare i vecchi messaggi nella cassetta postale di archiviazione. Quando scade il blocco della conservazione, i criteri di archiviazione che fanno parte dei criteri di conservazione predefiniti di Exchange assegnati alle cassette postali di Exchange Online spostano gli elementi risalenti ad almeno due anni prima nella cassetta postale di archiviazione. Se non si abilita la cassetta postale di archiviazione, gli elementi risalenti a più di due anni prima rimarranno nella cassetta postale principale dell'utente. Per ulteriori informazioni, vedere [abilitare le cassette postali di archiviazione](enable-archive-mailboxes.md).
 