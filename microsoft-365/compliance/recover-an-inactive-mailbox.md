---
title: Recuperare una cassetta postale inattiva
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/21/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 35d0ecdb-7cb0-44be-ad5c-69df2f8f8b25
description: "Se un ex dipendente ritorna all'organizzazione o se un nuovo dipendente viene assunto per assumere le responsabilità del lavoro di un dipendente defunto, è possibile recuperare il contenuto della cassetta postale inattiva in Office 365. Quando si ripristina una cassetta postale inattiva, viene convertita in una nuova cassetta postale che contiene il contenuto della cassetta postale inattiva. "
ms.openlocfilehash: d79bdf19e4e16d33f55caf10cd864b2627609db7
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636274"
---
# <a name="recover-an-inactive-mailbox"></a>Recuperare una cassetta postale inattiva

Una cassetta postale inattiva (che è un tipo di cassetta postale eliminata temporaneamente) viene utilizzata per mantenere la posta elettronica di un precedente dipendente dopo che quest'ultimo ha lasciato l'organizzazione. Se tale dipendente torna nell'organizzazione o se un altro dipendente assume le responsabilità del dipendente precedente, esistono due modi che consentono di rendere disponibile il contenuto della cassetta postale inattiva a un utente: 
  
- **Recuperare una cassetta postale inattiva** Se l'ex dipendente torna nell'organizzazione oppure se un nuovo dipendente viene assunto per ricoprire il ruolo del precedente dipendente, è possibile recuperare i contenuti della cassetta postale inattiva. Questo metodo consente di convertire la cassetta postale inattiva in una nuova cassetta postale attiva con il contenuto della cassetta postale inattiva. Dopo essere stata recuperata, la cassetta postale inattiva non esiste più. Le procedure descritte in questo argomento illustrano tale metodo. 
    
- **Ripristinare una cassetta postale inattiva** Se l'altro dipendente assume le responsabilità di un ex dipendente o se un altro utente deve accedere al contenuto della cassetta postale inattiva, è possibile ripristinare (o unire) il contenuto della cassetta postale inattiva in una cassetta postale esistente. È inoltre possibile ripristinare l'archivio da una cassetta postale inattiva. Per le procedure per questo metodo, vedere [ripristinare una cassetta postale inattiva in Office 365](restore-an-inactive-mailbox.md).
    
Vedere la sezione [Ulteriori informazioni](#more-information) per maggiori dettagli sulle differenze tra recupero e ripristino di una cassetta postale inattiva, oltre a una descrizione di cosa accade quando viene recuperata una cassetta postale inattiva.
  
## <a name="before-you-begin"></a>Prima di iniziare

- È necessario utilizzare Exchange Online PowerShell per ripristinare una cassetta postale inattiva. Non è possibile usare l'interfaccia di amministrazione di Exchange (EAC). Per istruzioni dettagliate, vedere [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554).
    
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
    > Nel comando precedente, usare il valore della proprietà **DistinguishedName** o **ExchangeGUID** per identificare la cassetta postale inattiva. Queste proprietà sono univoche per ogni cassetta postale nell'organizzazione, mentre è possibile che una cassetta postale attiva e una cassetta postale inattiva possano avere lo stesso indirizzo SMTP primario. 
  
2. In questo esempio vengono utilizzate le proprietà ottenute con il comando precedente e viene recuperata la cassetta postale inattiva in una cassetta postale attiva per l'utente Ann Beebe. Verificare che i valori specificati per i parametri *Name* e *MicrosoftOnlineServicesID* siano univoci all'interno dell'organizzazione. 

    ```powershell
    New-Mailbox -InactiveMailbox $InactiveMailbox.DistinguishedName -Name annbeebe -FirstName Ann -LastName Beebe -DisplayName "Ann Beebe" -MicrosoftOnlineServicesID Ann.Beebe@contoso.com -Password (ConvertTo-SecureString -String 'P@ssw0rd' -AsPlainText -Force) -ResetPasswordOnNextLogon $true
    ```

    L'indirizzo SMTP primario per la cassetta postale inattiva recuperata avrà lo stesso valore di quello specificato dal parametro *MicrosoftOnlineServicesID* . 
    
Dopo aver ripristinato una cassetta postale inattiva, viene creato anche un nuovo account utente. È necessario attivare questo account utente assegnando una licenza. Per assegnare una licenza nell'interfaccia di amministrazione di Microsoft 365, vedere [assegnare o annullare l'assegnazione delle licenze per microsoft 365 for business](https://go.microsoft.com/fwlink/p/?LinkId=276798).
  
## <a name="more-information"></a>Ulteriori informazioni

- **Qual è la differenza principale tra il recupero e il ripristino di una cassetta postale inattiva?** Quando si recupera una cassetta postale inattiva, la cassetta postale viene sostanzialmente convertita in una nuova cassetta postale, il contenuto e la struttura della cassetta postale vengono conservati e la cassetta postale viene collegata a un nuovo account utente. Dopo il recupero, la cassetta postale inattiva non esiste più e le eventuali modifiche apportate al contenuto della nuova cassetta postale vengono applicate al contenuto originariamente conservato nella cassetta postale inattiva. Al contrario, quando si ripristina una cassetta postale inattiva, il contenuto viene semplicemente copiato in un'altra cassetta postale. La cassetta postale inattiva viene conservata e rimane inattiva. Le eventuali modifiche apportate al contenuto nella cassetta postale di destinazione non vengono applicate al contenuto originale conservato nella cassetta postale inattiva. La cassetta postale inattiva può comunque essere cercata utilizzando eDiscovery sul posto, i suoi contenuti possono essere ripristinati in un'altra cassetta postale oppure può essere recuperata o eliminata in un secondo momento. 
    
- **Cosa accade quando viene recuperata una cassetta postale inattiva?** Quando si recupera una cassetta postale inattiva, si verifica quanto segue: 
    
  - Il blocco per controversia legale (se era stato abilitato per la cassetta postale inattiva) viene rimosso.
    
  - I blocchi sul posto vengono rimossi. Ciò indica che la cassetta postale inattiva viene rimossa come cassetta postale di origine da qualsiasi ricerca dei blocchi sul posto o di eDiscovery sul posto. 
    
  - La cassetta postale inattiva viene rimossa da qualsiasi criterio di conservazione Microsoft 365 che è stato applicato.
    
  - Il periodo di recupero di un singolo elemento (che è definito dalla proprietà della cassetta postale **RetainDeletedItemsFor** ) è impostato su 30 giorni. In genere, quando si crea una nuova cassetta postale in Exchange Online, il periodo di conservazione è impostato su 14 giorni. Impostandolo sul valore massimo di 30 giorni, si ha più tempo per recuperare i dati eliminati definitivamente (o cancellati) dalla cassetta postale inattiva. È anche possibile disabilitare il recupero di un singolo elemento o reimpostare il periodo di conservazione di un singolo elemento sul valore predefinito di 14 giorni. Per ulteriori informazioni, vedere [Enable or disable single item recovery for a mailbox](https://go.microsoft.com/fwlink/?linkid=856769).
    
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
 