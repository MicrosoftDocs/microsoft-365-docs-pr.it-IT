---
title: Ricerca ed eliminazione di messaggi - Guida di Amministrazione
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8c36bb03-e716-4fdd-9958-4aa7a2a1db42
description: Gli amministratori possono utilizzare il cmdlet Search-Mailbox per cercare cassette postali utente ed eliminare messaggi da una cassetta postale.
ms.openlocfilehash: bb375bc7a3273e78acb44807e51a1cee0261e7af
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37084169"
---
# <a name="search-for-and-delete-messages---admin-help"></a>Ricerca ed eliminazione di messaggi - Guida di Amministrazione
  
Gli amministratori possono utilizzare il cmdlet **Search-Mailbox** per cercare cassette postali utente ed eliminare messaggi da una cassetta postale. 
  
Per cercare ed eliminare i messaggi in un solo passaggio, eseguire il cmdlet **Search-Mailbox** con l'opzione  _DeleteContent_. Tuttavia, durante questa operazione non è possibile visualizzare in anteprima i risultati di ricerca o creare un registro dei messaggi che verrà restituito dalla ricerca e si potrebbero inavvertitamente eliminare messaggi. Per visualizzare in anteprima un registro dei messaggi trovati nella ricerca prima che vengano eliminati, eseguire il cmdlet **Search-Mailbox** con l'opzione  _LogOnly_. 
  
Come ulteriore salvaguardia, è possibile prima copiare i messaggi su un'altra cassetta postale utilizzando i parametri  _TargetMailbox_ e  _TargetFolder_. Nell'effettuare questa operazione, mantenere una copia dei messaggi eliminati nel caso sia necessario accedervi di nuovo. 
  
## <a name="before-you-begin"></a>Informazioni preliminari

- Tempo stimato per il completamento: 10 minuti. Il tempo effettivo potrebbe variare in base alla dimensione della cassetta postale e della query di ricerca.
    
- Non è possibile utilizzare l'interfaccia di amministrazione di Exchange per eseguire tali procedure. È necessario utilizzare la shell.
    
- Per cercare ed eliminare messaggi nelle cassette postali degli utenti, è necessario ricoprire entrambi i seguenti ruoli di gestione:
    
  - **Ricerca cassette postali**-questo ruolo consente di cercare i messaggi su più cassette postali dell'organizzazione. Agli amministratori non viene assegnato questo ruolo per impostazione predefinita. Per assegnare a se stessi questo ruolo per poter effettuare ricerche nelle cassette postali, aggiungersi come membro del gruppo di ruoli Gestione individuazione. Vedere [Add a User to the Discovery Management Role Group](http://technet.microsoft.com/library/729e09d8-614b-431f-ae04-ae41fb4c628e.aspx).
    
  - **Esportazione delle cassette postali** -questo ruolo consente di eliminare i messaggi dalla cassetta postale di un utente. Per impostazione predefinita, questo ruolo non è assegnato ad alcun gruppo di ruoli. Per eliminare i messaggi dalle cassette postali degli utenti, è possibile aggiungere il ruolo Esportazione/importazione delle cassette postali al gruppo di ruoli Gestione organizzazione. Per ulteriori informazioni, vedere la sezione "aggiungere un ruolo a un gruppo di ruoli" in [Manage Role](http://technet.microsoft.com/library/ab9b7a3b-bf67-4ba1-bde5-8e6ac174b82c.aspx) groups. 
    
- Se la cassetta postale dalla quale si desidera eliminare i messaggi ha la funzione di individuazione di singoli elementi, è necessario prima disabilitare la funzione. Per ulteriori informazioni, vedere [Abilitare o disabilitare il ripristino di un singolo elemento per una cassetta postale](http://technet.microsoft.com/library/2e7f1bcd-8395-45ad-86ce-22868bd46af0.aspx).
    
- Se la cassetta postale dalla quale si desidera eliminare i messaggi è stata bloccata, si consiglia di verificare con i responsabili della gestione dei record o con il dipartimento legale prima di rimuovere l'opzione di conservazione ed eliminare il contenuto delle cassette postali. Dopo aver ottenuto l'approvazione, seguire i passaggi elencati nell'argomento [pulizia della cartella elementi ripristinabili](http://technet.microsoft.com/library/82c310f8-de2f-46f2-8e1a-edb6055d6e69.aspx).
    
- Una singola ricerca può essere eseguita su un massimo di 10.000 cassette postali con il cmdlet **Search-Mailbox**. Se si è un'organizzazione Exchange Online con più di 10.000 cassette postali, è possibile utilizzare la funzionalità Ricerca di conformità (o il corrispondente cmdlet **New-ComplianceSearch** ) per cercare un numero illimitato di cassette postali. È possibile utilizzare il cmdlet **New-ComplianceSearchAction** per eliminare i messaggi restituiti da una ricerca di conformità. Per ulteriori informazioni, vedere [Cercare ed eliminare messaggi dall'organizzazione di Office 365](https://go.microsoft.com/fwlink/p/?LinkId=786856).
    
- Se si include una query di ricerca (usando il parametro  *SearchQuery*  ), il cmdlet **Search-Mailbox** restituirà un massimo di 10.000 elementi nei risultati della ricerca. Pertanto se si include una query di ricerca, potrebbe essere necessario eseguire il comando **Search-Mailbox** più volte per eliminare più di 10.000 elementi. 
    
- La cassetta postale di archiviazione dell'utente verrà cercata anche eseguendo il cmdlet **Search-Mailbox**. Allo stesso modo, gli elementi nella cassetta postale di archiviazione principale verranno eliminati quando si utilizza il cmdlet **Search-Mailbox** con l'opzione  _DeleteContent_. Per prevenire questa situazione, è possibile includere l'opzione  *DoNotIncludeArchive*  .
    
## <a name="search-messages-and-log-the-search-results"></a>Ricerca di messaggi e registrazione dei risultati della ricerca

Con questo esempio viene effettuata una ricerca nella cassetta postale di April Stewart per individuare i messaggi contenenti la frase "Your bank statement" nell'oggetto e il risultato viene registrato nella cartella SearchAndDeleteLog della cassetta postale dell'amministratore. I messaggi non vengono copiati né eliminati nella cassetta postale di destinazione.
  
```
Search-Mailbox -Identity "April Stewart" -SearchQuery 'Subject:"Your bank statement"' -TargetMailbox administrator -TargetFolder "SearchAndDeleteLog" -LogOnly -LogLevel Full
```

Nell'esempio seguente in tutte le cassette postali dell'organizzazione si cercano i messaggi con qualsiasi tipo di file allegato contenente la parola "Trojan" nel nome file e viene inviato un messaggio del registro alla cassetta postale dell'amministratore.
  
```
Get-Mailbox -ResultSize unlimited | Search-Mailbox -SearchQuery attachment:trojan* -TargetMailbox administrator -TargetFolder "SearchAndDeleteLog" -LogOnly -LogLevel Full
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Search-Mailbox](http://technet.microsoft.com/library/9ee3b02c-d343-4816-a583-a90b1fad4b26.aspx).
  
 
## <a name="search-and-delete-messages"></a>Ricerca ed eliminazione dei messaggi

Con questo esempio viene effettuata una ricerca nella cassetta postale di April Stewart per individuare i messaggi contenenti la frase "Your bank statement" nell'oggetto; tali messaggi vengono eliminati dalla cassetta postale di origine senza che vengano copiati i risultati di ricerca su un'altra cartella. Come spiegato precedentemente, è necessario avere il ruolo di gestione Esportazione/Importazione delle cassette postali per eliminare messaggi dalla cassetta postale di un utente.
  
> [!IMPORTANT]
> Quando si utilizza il cmdlet **Search-Mailbox** con l'opzione  _DeleteContent_, i messaggi vengono eliminati permanentemente dalla cassetta postale di origine. Prima di eliminare permanentemente i messaggi, si consiglia di utilizzare l'opzione  _LogOnly_ per creare un registro dei messaggi trovati nella ricerca prima che vengano eliminati oppure copiare i messaggi su un'altra cassetta postale prima di eliminarli dalla cassetta postale di origine. 
  
```
Search-Mailbox -Identity "April Stewart" -SearchQuery 'Subject:"Your bank statement"' -DeleteContent
```

Con questo esempio viene effettuata una ricerca nella cassetta postale di April Stewart per individuare i messaggi contenenti la frase "Your bank statement" nell'oggetto. Il risultato viene copiato nella cartella AprilStewart-DeletedMessages nella cassetta postale BackupMailbox e i messaggi vengono eliminati dalla cassetta postale di April.
  
```
Search-Mailbox -Identity "April Stewart" -SearchQuery 'Subject:"Your bank statement"' -TargetMailbox "BackupMailbox" -TargetFolder "AprilStewart-DeletedMessages" -LogLevel Full -DeleteContent
```

In questo esempio si cercano in tutte le cassette postali dell'organizzazione i messaggi con la riga di oggetto "Download this file" e quindi li si elimina in modo definitivo. 
  
```
Get-Mailbox -ResultSize unlimited | Search-Mailbox -SearchQuery 'Subject:"Download this file"' -DeleteContent
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Search-Mailbox](http://technet.microsoft.com/library/9ee3b02c-d343-4816-a583-a90b1fad4b26.aspx).

## <a name="using-the--loglevel-full-parameter"></a>Usando il parametro -LogLevel Full

In alcuni degli esempi precedenti, il parametro  _LogLevel_ con valore  `Full` viene utilizzato per registrare informazioni dettagliate sui risultati restituiti dal cmdlet **Search-Mailbox**. Quando si include questo parametro, un messaggio di posta elettronica viene creato e inviato alla cassetta postale specificata dal parametro  _TargetMailbox_. Il file di registro (che è un file in formato CSV denominato Search Results.csv) è allegato a questo messaggio di posta elettronica e si trova nella cartella specificata dal parametro  _TargetFolder_. Il file di registro contiene una riga per ogni messaggio incluso nei risultati della ricerca quando si esegue il cmdlet **Search-Mailbox**. 
