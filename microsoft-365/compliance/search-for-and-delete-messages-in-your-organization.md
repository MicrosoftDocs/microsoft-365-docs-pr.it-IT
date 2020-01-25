---
title: Cercare i messaggi di posta elettronica ed eliminarli dall'organizzazione di Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 3526fd06-b45f-445b-aed4-5ebd37b3762a
description: Usare la funzionalità di ricerca e rimozione nel Centro sicurezza e conformità di Office 365 per cercare un messaggio di posta elettronica ed eliminarlo da tutte le cassette postali dell'organizzazione.
ms.openlocfilehash: 53ec50ddd42e1d17580f4b1581ef8d8fe02f97bf
ms.sourcegitcommit: 3dca80f268006658a0b721aa4f6df1224c7964dc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2020
ms.locfileid: "41259974"
---
# <a name="search-for-and-delete-email-messages-in-your-office-365-organization"></a>Cercare i messaggi di posta elettronica ed eliminarli dall'organizzazione di Office 365

**Questo articolo è rivolto agli amministratori. Per cercare gli elementi nella propria cassetta postale per eliminarli, vedere [Trovare un messaggio o un elemento con Ricerca immediata](https://support.office.com/article/69748862-5976-47b9-98e8-ed179f1b9e4d)**|
   
È possibile utilizzare la funzionalità Ricerca contenuto in Office 365 per cercare un messaggio di posta elettronica ed eliminarlo da tutte le cassette postali nell'organizzazione. Ciò è utile per trovare e rimuovere messaggi potenzialmente dannosi o ad alto rischio, ad esempio:
  
- Messaggi contenenti virus o allegati pericolosi
    
- Messaggi di phishing
    
- Messaggi contenenti dati sensibili
    
> [!CAUTION]
> Con l’operazione di ricerca e rimozione, chiunque abbia le autorizzazioni necessarie può eliminare i messaggi di posta elettronica dalle cassette postali nell'organizzazione. 
  
## <a name="before-you-begin"></a>Prima di iniziare

- Per creare ed eseguire una ricerca di contenuto, è necessario essere membro del gruppo di ruoli **Gestione di eDiscovery** o disporre del ruolo di gestione della **Ricerca di conformità**. Per eliminare i messaggi, è necessario essere membro del gruppo di ruoli **Gestione dell’organizzazione** o disporre del ruolo di gestione **Search And Purge**. Per informazioni su come aggiungere gli utenti a un gruppo di ruoli, vedere [Assegnare autorizzazioni di eDiscovery nel Centro sicurezza e conformità](assign-ediscovery-permissions.md).
    
- Per eliminare i messaggi, è necessario usare PowerShell in Centro sicurezza e conformità. Per informazioni su come connettersi, vedere il [Passaggio 2](#step-2-connect-to-security--compliance-center-powershell).
    
- È possibile rimuovere al massimo 10 elementi per ogni cassetta postale alla volta. Poiché la possibilità di cercare e di rimuovere i messaggi è uno strumento di intervento, questo limite garantisce che i messaggi vengano rimossi rapidamente dalle cassette postali. Lo scopo di questa funzionalità non è svuotare le cassette postali degli utenti. Per eliminare più di 10 elementi, è possibile usare il comando **Search-Mailbox -DeleteContent** in Exchange Online PowerShell. Vedere [Cercare ed eliminare i messaggi](search-for-and-delete-messagesadmin-help.md).
    
- Il numero massimo di cassette postali supportato dalla ricerca di contenuto per eliminare gli elementi con un'operazione di ricerca e rimozione è 50.000. Se la ricerca di contenuto, creata nel [Passaggio 1](#step-1-create-a-content-search-to-find-the-message-to-delete), include più di 50.000 cassette postali di origine, l'azione di rimozione, creata nel Passaggio 3, non riuscirà. Vedere la sezione [Ulteriori informazioni](#more-information) per ottenere suggerimenti su come eseguire un'operazione di ricerca e rimozione su più di 50.000 cassette postali. 
    
- La procedura descritta in questo articolo può essere usata solo per eliminare elementi nelle cassette postali e cartelle pubbliche di Exchange Online. Non è possibile usarla per eliminare il contenuto dai siti di SharePoint o OneDrive for Business.
    
## <a name="step-1-create-a-content-search-to-find-the-message-to-delete"></a>Passaggio 1: creare una ricerca di contenuto per trovare il messaggio da eliminare

Il primo passaggio consiste nel creare ed eseguire una ricerca contenuto per trovare il messaggio da rimuovere dalle cassette postali dell'organizzazione. È possibile creare la ricerca tramite il Centro sicurezza e conformità o eseguendo i cmdlet **New-ComplianceSearch** e **Start-ComplianceSearch**. I messaggi che soddisfano la query per la ricerca verranno eliminati eseguendo il comando **New-ComplianceSearchAction -Purge** nel [Passaggio 3](#step-3-delete-the-message). Per informazioni sulla creazione di una Ricerca contenuto e sulla configurazione delle query di ricerca, vedere gli argomenti seguenti: 
  
- [Ricerca contenuto in Office 365](content-search.md)
    
- [Query con parole chiave per la Ricerca contenuto](keyword-queries-and-search-conditions.md)
    
- [New-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/New-ComplianceSearch)
    
- [Start-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/Start-ComplianceSearch)
    
> [!NOTE]
> I percorsi di contenuto all'interno dei quali viene eseguita la Ricerca contenuto creata in questo passaggio non possono includere siti di SharePoint o OneDrive for Business. In una Ricerca contenuto che verrà usata per inviare messaggi di posta elettronica è possibile includere solo cassette postali e cartelle pubbliche. Se la Ricerca contenuto include siti, si riceverà un messaggio di errore al Passaggio 3 quando si esegue il cmdlet **New-ComplianceSearchAction**. 
  
### <a name="tips-for-finding-messages-to-remove"></a>Suggerimenti per cercare i messaggi da rimuovere

L'obiettivo della query di ricerca è limitare i risultati della ricerca solo al messaggio o ai messaggi da rimuovere. Di seguito sono riportati alcuni suggerimenti:
  
- Se si conosce la frase o il testo esatto della riga dell'oggetto del messaggio, utilizzare la proprietà **Subject** nella query di ricerca. 
    
- Se si conosce la data esatta (o l'intervallo di date) del messaggio, includere la proprietà **Received** nella query di ricerca. 
    
- Se si conosce il mittente del messaggio, includere la proprietà **From** nella query di ricerca. 
    
- Visualizzare in anteprima i risultati della ricerca per verificare che la ricerca di contenuto restituisca solo il messaggio (o i messaggi) da eliminare.
    
- Per ottenere il numero totale di risultati, usare le statistiche di stima della ricerca, visualizzate nel riquadro dei dettagli della ricerca nel Centro di sicurezza e conformità oppure tramite il cmdlet [Get-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517934).  
    
Ecco due esempi di query per trovare messaggi di posta elettronica sospetti.
  
- Questa query restituisce i messaggi che sono stati ricevuti dagli utenti tra il 13 aprile 2016 e il 14 aprile 2016 e che contengono le parole "action" e "required" nella riga dell'oggetto.
    
    ```powershell
    (Received:4/13/2016..4/14/2016) AND (Subject:'Action required')
    ```

- Questa query restituisce i messaggi che sono stati inviati da chatsuwloginsset12345@outlook.com e che contengono la frase esatta "Update your account information" nella riga dell'oggetto.
    
    ```powershell
    (From:chatsuwloginsset12345@outlook.com) AND (Subject:"Update your account information")
    ```

## <a name="step-2-connect-to-security--compliance-center-powershell"></a>Passaggio 2: Connettersi a PowerShell in Centro sicurezza e conformità

Il passaggio successivo consiste nel connettersi a PowerShell in Centro sicurezza e conformità per l'organizzazione. Per ottenere istruzioni dettagliate, vedere [Connettersi a PowerShell in Centro sicurezza e conformità](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).
  
Se l'account di Office 365 usa l'autenticazione a più fattori o l'autenticazione federata, non è possibile usare le istruzioni riportate nell'argomento precedente per la connessione a PowerShell in Centro sicurezza e conformità. Per farlo, vedere le istruzioni nell’argomento [Connettersi a PowerShell in Centro sicurezza e conformità mediante l'autenticazione a più fattori](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell).
  
## <a name="step-3-delete-the-message"></a>Passaggio 3: Eliminare il messaggio

Dopo aver creato e perfezionato una ricerca di contenuto affinché restituisca il messaggio da rimuovere e dopo essersi connessi a PowerShell in Centro sicurezza e conformità, occorre eseguire il cmdlet **New-ComplianceSearchAction** per eliminare il messaggio. È possibile eliminare il messaggio in maniera temporanea o definitiva. Un messaggio eliminato temporaneamente viene spostato nella cartella Elementi ripristinabili dell’utente e viene conservato fino alla scadenza del periodo di conservazione degli elementi eliminati. I messaggi eliminati definitivamente vengono contrassegnati per la rimozione definitiva dalla cassetta postale e saranno rimossi definitivamente durante la successiva elaborazione da parte dell’Assistente cartelle gestite. Se il ripristino di un singolo elemento è abilitato per la cassetta postale, gli elementi eliminati definitivamente verranno rimossi in modo permanente dopo la scadenza del periodo di conservazione. Se viene applicato un blocco a una cassetta postale, i messaggi eliminati vengono conservati finché la durata del periodo di conservazione dell'elemento non scade o finché il blocco non viene rimosso.
  
Nell'esempio seguente il comando elimina temporaneamente i risultati della ricerca restituiti da una ricerca di contenuto denominata "Remove Phishing Message". 

```powershell
New-ComplianceSearchAction -SearchName "Remove Phishing Message" -Purge -PurgeType SoftDelete
```

Per eliminare definitivamente gli elementi restituiti dalla ricerca contenuto "Remove Phishing Message", eseguire questo comando:

```powershell
New-ComplianceSearchAction -SearchName "Remove Phishing Message" -Purge -PurgeType HardDelete
```

Quando si esegue il comando precedente per eliminare i messaggi temporaneamente o definitivamente, la ricerca specificata dal parametro *SearchName* è la ricerca contenuto creata nel Passaggio 1. 
  
Per altre informazioni, vedere [New-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/New-ComplianceSearchAction).

## <a name="more-information"></a>Ulteriori informazioni

- **Come si vede lo stato dell'operazione di ricerca e rimozione?**

    Eseguire il comando **Get-ComplianceSearchAction** per vedere lo stato dell'operazione di eliminazione. All'oggetto creato quando si esegue il cmdlet **New-ComplianceSearchAction** viene assegnato un nome in questo formato: `<name of Content Search>_Purge`. 
    
- **Cosa succede dopo l'eliminazione di un messaggio?**

   Un messaggio eliminato con il comando `New-ComplianceSearchAction -Purge -PurgeType HardDelete` viene spostato nella cartella Ripuliture e non è accessibile all'utente. Una volta spostato nella cartella Ripuliture, il messaggio viene conservato per la durata del periodo di conservazione degli elementi eliminati se il ripristino di un singolo elemento è abilitato per la cassetta postale. In Office 365, il ripristino di un singolo elemento è abilitato per impostazione predefinita quando viene creata una nuova cassetta postale. Dopo la scadenza del periodo di conservazione degli elementi eliminati, il messaggio viene contrassegnato per l'eliminazione permanente e verrà eliminato da Office 365 alla successiva elaborazione della cassetta postale da parte dell'Assistente cartelle gestite. 

   Usando il comando `New-ComplianceSearchAction -Purge -PurgeType SoftDelete`, i messaggi vengono spostati nella cartella Eliminazioni nella cartella Elementi ripristinabili dell'utente. Non viene rimosso immediatamente da Office 365. L'utente può recuperare i messaggi nella cartella Elementi eliminati per la durata del periodo di conservazione degli elementi eliminati configurato per la cassetta postale. Dopo la scadenza di questo periodo di conservazione (o se l'utente elimina il messaggio prima della scadenza), il messaggio viene spostato nella cartella di eliminazione e non è più accessibile da parte dell'utente. Una volta spostato nella cartella Ripuliture, il messaggio viene mantenuto per la durata del periodo di conservazione degli elementi eliminati configurato per la cassetta postale, se il ripristino di un singolo elemento è abilitato. In Office 365, il ripristino di un singolo elemento è abilitato per impostazione predefinita quando viene creata una nuova cassetta postale. Dopo la scadenza del periodo di conservazione degli elementi eliminati, il messaggio viene contrassegnato per l'eliminazione permanente e verrà eliminato da Office 365 alla successiva elaborazione della cassetta postale da parte dell'Assistente cartelle gestite. 
    
- **Come si fa a eliminare un messaggio da più di 50.000 cassette postali?**

    Come spiegato in precedenza, è possibile eseguire un'operazione di ricerca e rimozione su un massimo di 50.000 cassette postali. Se è necessario eseguire un'operazione di ricerca e rimozione su più di 50.000 cassette postali, è consigliabile creare dei filtri delle autorizzazioni di ricerca temporanei per ridurre il numero di cassette postali in cui eseguire la ricerca a meno di 50.000. Se ad esempio nell'organizzazione sono presenti cassette postali in dipartimenti, stati o paesi diversi, è possibile creare un filtro delle autorizzazioni di ricerca in base a una di queste proprietà delle cassette postali per eseguire la ricerca in un sottoinsieme di cassette postali dell'organizzazione. Dopo aver creato il filtro delle autorizzazioni di ricerca, è necessario creare la ricerca, come descritto nel Passaggio 1, e quindi eliminare il messaggio, come descritto nel Passaggio 3. È quindi possibile modificare il filtro in modo da cercare e rimuovere i messaggi in un insieme di cassette postali diverso. Per altre informazioni sulla creazione di filtri delle autorizzazioni di ricerca, vedere [Configurare i filtri delle autorizzazioni per la Ricerca contenuto](permissions-filtering-for-content-search.md).
    
- **Gli elementi non indicizzati inclusi nei risultati della ricerca verranno eliminati?**

    No, il comando “New-ComplianceSearchAction -Purge” non elimina gli elementi non indicizzati. 
    
- **Cosa succede se un messaggio viene eliminato da una cassetta postale soggetta a blocco sul posto o a blocco per controversia legale o se viene assegnato a un criterio di conservazione di Office 365?**

    Dopo che il messaggio è stato eliminato e spostato nella cartella Ripuliture, il messaggio viene conservato fino alla scadenza del periodo di conservazione. Se la durata di conservazione è illimitata, gli elementi vengono mantenuti fino a quando non viene rimosso il blocco o viene modificata la durata di conservazione.
    
- **Perché il flusso di lavoro di ricerca e rimozione è diviso tra diversi gruppi di ruoli del centro sicurezza e conformità?**

    Come indicato in precedenza, per eseguire ricerche nelle cassette postali, è necessario essere membri del gruppo di ruoli di responsabili di eDiscovery o disporre del ruolo di gestione di ricerca di conformità. Per eliminare i messaggi, è necessario essere membri del gruppo di ruoli di gestione dell'organizzazione o disporre del ruolo di gestione di ricerca ed eliminazione. In questo modo è possibile controllare chi può eseguire ricerche nelle cassette postali dell'organizzazione e chi può eliminare i messaggi. 
