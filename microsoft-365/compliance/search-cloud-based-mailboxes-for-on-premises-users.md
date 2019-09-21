---
title: Ricerca di cassette postali basate sul cloud per gli utenti locali in Office 365
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
- MST160
- MET150
ms.assetid: 3f7dde1a-a8ea-4366-86da-8ee6777f357c
description: Utilizzare lo strumento di ricerca contenuto nel centro sicurezza & Compliance per cercare ed esportare i dati di chat di MicrosoftTeams (denominati chat di 1xN) per gli utenti locali in una distribuzione ibrida di Exchange.
ms.openlocfilehash: 38aff6116bd3cd8e4ba9f0f46d6fd81f790803f3
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37084740"
---
# <a name="searching-cloud-based-mailboxes-for-on-premises-users-in-office-365"></a>Ricerca di cassette postali basate sul cloud per gli utenti locali in Office 365

Se l'organizzazione dispone di una distribuzione ibrida di Exchange e ha abilitato Microsoft teams, gli utenti possono utilizzare l'applicazione chat teams per la messaggistica istantanea. Per l'utente basato sul cloud, i dati della chat dei team (denominati anche chat di 1xN) vengono salvati nella cassetta postale basata sul cloud principale. Quando un utente locale utilizza l'applicazione Team Chat, la cassetta postale principale si trova in locale. Per ovviare a questa limitazione, Microsoft ha rilasciato una nuova funzionalità in cui è stata creata un'area di archiviazione basata su cloud (denominata cassetta postale basata su cloud per gli utenti locali) per archiviare i dati di chat dei team per gli utenti locali. In questo modo è possibile utilizzare lo strumento di ricerca contenuto nel centro sicurezza & Compliance per cercare ed esportare i dati di chat dei team per gli utenti locali. 
  
Di seguito sono riportati i requisiti e le limitazioni per la configurazione delle cassette postali basate sul cloud per gli utenti locali:
  
- Gli account utente nel servizio directory locale (ad esempio Active Directory) devono essere sincronizzati con Azure Active Directory, il servizio directory di Office 365. Questo significa che un account utente di posta elettronica viene creato in Office 365 ed è associato a un utente la cui cassetta postale principale si trova nell'organizzazione locale.

- All'utente la cui cassetta postale principale si trova nell'organizzazione locale deve essere assegnata una licenza di Microsoft teams e una licenza di Exchange Online piano 1.
    
- La cassetta postale basata sul cloud per gli utenti locali viene utilizzata solo per archiviare i dati della chat dei team. Un utente locale non è in grado di accedere alla cassetta postale basata sul cloud o di accedervi in alcun modo. Non può essere utilizzato per inviare o ricevere messaggi di posta elettronica. 
    
- È necessario inviare una richiesta al supporto tecnico Microsoft per consentire all'organizzazione di cercare i dati della chat dei team nelle cassette postali basate sul cloud per gli utenti locali. Per abilitare questa funzionalità in questo articolo, vedere [presentazione di una richiesta con il supporto tecnico Microsoft](#filing-a-request-with-microsoft-support-to-enable-this-feature) . 
    
 **Nota:** Le conversazioni dei canali di teams vengono sempre memorizzate nella cassetta postale basata sul cloud associata al team. Questo significa che è possibile usare la ricerca contenuto per le conversazioni del canale di ricerca senza dover presentare una richiesta di supporto. Per ulteriori informazioni sulla ricerca delle conversazioni dei canali di teams, vedere [Searching Microsoft Teams and Office 365 groups](content-search.md#searching-microsoft-teams-and-office-365-groups).
  
## <a name="how-it-works"></a>Funzionamento

Se un utente abilitato a Microsoft teams dispone di una cassetta postale locale e il relativo account utente/identità è stato sincronizzato con il cloud, Microsoft crea una cassetta postale basata sul cloud per archiviare i dati di chat dei team di 1xN. Dopo che i dati della chat dei team vengono archiviati nella cassetta postale basata sul cloud, vengono indicizzati per la ricerca. In questo modo è possibile utilizzare la ricerca del contenuto (e le ricerche associate ai casi di eDiscovery) per cercare, visualizzare in anteprima ed esportare i dati di chat dei team per gli utenti locali. È inoltre possibile utilizzare ** \*** i cmdlet di ComplianceSearch in PowerShell per la sicurezza & Compliance Center per cercare i dati di chat dei team per gli utenti locali. 
  
Nell'immagine seguente viene illustrato il flusso di lavoro del modo in cui i dati della chat dei team per gli utenti locali sono disponibili per la ricerca, l'anteprima e l'esportazione.
  
![Archiviazione basata sul cloud per gli utenti locali in Microsoft Teams](media/895845f8-2ceb-47ed-96c9-5ab7f1aea916.png)
  
Oltre a questa nuova funzionalità, è comunque possibile utilizzare la ricerca contenuto per cercare, visualizzare in anteprima ed esportare il contenuto dei team nel sito di SharePoint basato sul cloud e nella cassetta postale di Exchange associata a ciascun dato di chat teams di Microsoft e 1xN teams nella cassetta postale di Exchange Online per utenti basati sul cloud.

## <a name="filing-a-request-with-microsoft-support-to-enable-this-feature"></a>Archiviazione di una richiesta con il supporto tecnico Microsoft per abilitare questa funzionalità

È necessario presentare una richiesta con il supporto tecnico Microsoft per consentire all'organizzazione di utilizzare l'interfaccia utente grafica nel centro sicurezza & conformità per cercare i dati di chat dei team nelle cassette postali basate sul cloud per gli utenti locali. Questa funzionalità è disponibile in PowerShell per Centro sicurezza & Compliance. Non è necessario inviare una richiesta di supporto per utilizzare PowerShell per cercare i dati di chat dei team per gli utenti locali. 
  
Includere le informazioni seguenti quando si invia la richiesta al supporto tecnico Microsoft:
  
- Il nome di dominio predefinito dell'organizzazione di Office 365.
    
- Il nome del tenant e l'ID tenant dell'organizzazione di Office 365. È possibile trovare queste informazioni nel portale di Azure Active Directory (in **Manage** \> **Properties**). Vedere [trovare l'ID tenant di Office 365](https://support.office.com/article/6891b561-a52d-4ade-9f39-b492285e2c9b).
    
- Il titolo o la descrizione seguente dello scopo della richiesta di supporto: "abilitare la ricerca di contenuto dell'applicazione per gli utenti locali". Ciò consente di instradare la richiesta al team di ingegneri di eDiscovery di Office 365 che implementerà la richiesta. 
    
Dopo aver apportato la modifica dell'ingegneria, il supporto tecnico Microsoft invierà una data di distribuzione stimata. Il processo di distribuzione richiede di solito 2 – 3 settimane dopo aver inviato la richiesta di supporto. 
  
### <a name="what-happens-after-this-feature-is-enabled"></a>Cosa succede dopo che questa funzionalità è stata abilitata?

Dopo la distribuzione di questa funzionalità nell'organizzazione di Office 365, vengono apportate le modifiche seguenti nella ricerca contenuto e nelle ricerche associate a un caso di eDiscovery nel centro sicurezza & Compliance:
  
- La casella di controllo **Aggiungi contenuto app di Office per gli utenti locali** viene aggiunta sotto le **posizioni** nella ricerca contenuto. 
    
    ![La casella di controllo "Aggiungi contenuto app di Office per gli utenti locali" viene aggiunta all'interfaccia utente per la ricerca di contenuto](media/599e751e-17bd-408d-a18c-127538de6e85.png)
  
- Gli utenti locali vengono visualizzati nella selezione percorsi di contenuto che si utilizza per selezionare le cassette postali degli utenti da cercare. 
    

  
## <a name="searching-for-teams-chat-content-in-cloud-based-mailboxes-for-on-premises-users"></a>Ricerca di contenuti per la chat di team in cassette postali basate su cloud per utenti locali

Dopo che la funzionalità è stata abilitata, è possibile utilizzare la ricerca contenuto nel centro sicurezza & conformità per cercare i dati di chat dei team nelle cassette postali basate sul cloud per gli utenti locali. 
  
1. Nel centro sicurezza & conformità, accedere a ricerca **** \> **contenuto** ricerca
    
2. Nella pagina **ricerca** fare clic ![su Aggiungi nuova](media/8ee52980-254b-440b-99a2-18d068de62d3.gif) icona di **ricerca**.
    
    Come illustrato in precedenza, la casella **di controllo Aggiungi contenuto app di Office per gli utenti locali** viene visualizzata in **percorsi**. È selezionata per impostazione predefinita.
    
3. Se necessario, creare la query di parole chiave e aggiungere condizioni alla query di ricerca. Per cercare solo i dati delle chat del team, è possibile aggiungere la query seguente nella casella **parole chiave** : 
    
    ```
    kind:im
    ``` 

4. A questo punto, è possibile scegliere una delle seguenti opzioni in **percorsi**:
    
    - **Tutte le posizioni:** Selezionare questa opzione per eseguire la ricerca nelle cassette postali di tutti gli utenti dell'organizzazione. Quando la casella di controllo è selezionata, verranno cercate anche tutte le cassette postali basate sul cloud per gli utenti locali. 
    
    - **Posizioni specifiche:** Selezionare questa opzione e quindi fare clic su **modifica** \> scegliere utente, gruppi o team per eseguire la ricerca di cassette postali specifiche. Come spiegato in precedenza, lo strumento di selezione percorsi consente di cercare gli utenti locali. 
    
5. Salvare ed eseguire la ricerca. Tutti i risultati di ricerca delle cassette postali basate sul cloud per gli utenti locali possono essere visualizzati in anteprima come tutti gli altri risultati della ricerca. È inoltre possibile esportare i risultati della ricerca (compresi i dati della chat dei team) in un file PST. Per ulteriori informazioni, vedere: 
    
    - [Create a search](content-search.md#create-a-search)
    
    - [Preview search results](content-search.md#preview-search-results)
    
    - [Esportare i risultati della Ricerca contenuto](export-search-results.md)
    
## <a name="using-powershell-to-search-for-teams-chat-data-in-cloud-based-mailboxes-for-on-premises-users"></a>Utilizzo di PowerShell per cercare i dati di chat dei team in cassette postali basate su cloud per gli utenti locali

È possibile utilizzare i cmdlet **New-ComplianceSearch** e **set-ComplianceSearch** in PowerShell per la sicurezza & Compliance Center per eseguire ricerche nella cassetta postale basata sul cloud per gli utenti locali. Come spiegato in precedenza, non è necessario inviare una richiesta di supporto per utilizzare PowerShell per cercare i dati di chat dei team per gli utenti locali. 
  
1. [Connettersi a PowerShell per Centro sicurezza & Compliance](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).
    
2. Eseguire il seguente comando di PowerShell per creare una ricerca di contenuto che esegua ricerche nelle cassette postali basate sul cloud degli utenti locali.
    
    ```
    New-ComplianceSearch <name of new search> -ContentMatchQuery <search query> -ExchangeLocation <on-premises user> -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```
   
    Il parametro *IncludeUserAppContent* viene utilizzato per specificare la cassetta postale basata sul cloud per l'utente o gli utenti specificati dal parametro *ExchangeLocation* . *AllowNotFoundExchangeLocationsEnabled* consente alle cassette postali basate sul cloud per gli utenti locali. Quando si utilizza il `$true` valore per questo parametro, la ricerca non tenta di convalidare l'esistenza della cassetta postale prima che venga eseguita. Questa operazione è necessaria per eseguire ricerche nelle cassette postali basate sul cloud per gli utenti locali, in quanto questi tipi di cassette postali non vengono risolti come cassette postali normali. 
    
    Nell'esempio seguente vengono ricercate le chat di Teams (che sono messaggi istantanei) che contengono la parola chiave "Redstone" nella cassetta postale basata sul cloud di Sara Davis, che è un utente locale nell'organizzazione contoso.
  
    ```
    New-ComplianceSearch "Redstone_Search" -ContentMatchQuery "redstone AND kind:im" -ExchangeLocation sarad@contoso.com -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```

   Dopo aver creato una ricerca, accertarsi di utilizzare il cmdlet **Start-ComplianceSearch** per eseguire la ricerca. 
  
Per ulteriori informazioni sull'utilizzo di questi cmdlet, vedere:
  
- [New-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-compliancesearch)
    
- [Set-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/set-compliancesearch)
    
- [Start-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/start-compliancesearch)
    

## <a name="known-issues"></a>Problemi noti

- Attualmente, è possibile solo cercare, visualizzare in anteprima ed esportare il contenuto nelle cassette postali basate su cloud per gli utenti locali. L'inserimento di una cassetta postale basata sul cloud per un utente locale in un blocco associato a un caso di eDiscovery o di assegnazione a un criterio di conservazione di Office 365 non è supportato. 
    
- La selezione percorso contenuto per eDiscovery contiene gli utenti locali e consente di selezionarli. Tuttavia, come spiegato in precedenza, il blocco non verrà applicato all'utente locale.
    
## <a name="frequently-asked-questions"></a>Domande frequenti

 **Dove si trovano le cassette postali basate sul cloud per gli utenti locali?**
  
Le cassette postali basate sul cloud vengono create e archiviate nello stesso datacenter dell'organizzazione di Office 365. 
  
 **Esistono altri requisiti diversi dall'invio di una richiesta di supporto?**
  
 Come spiegato in precedenza, le identità degli utenti con cassette postali on-Prem devono essere sincronizzate con l'organizzazione basata su cloud in modo che venga creato un account utente di posta elettronica corrispondente per ogni account utente locale in Office 365. L'organizzazione deve disporre anche di un abbonamento a Office 365 Enterprise, ad esempio un abbonamento a Office 365 Enterprise E1, E3 o E5. 
  
 **Esiste il rischio di perdere i dati della chat dei team se la cassetta postale locale dell'utente viene migrata nel cloud?**
  
No. Quando si esegue la migrazione della cassetta postale principale di un utente locale nel cloud, i dati della chat dei team per tale utente verranno migrati nella nuova cassetta postale principale basata sul cloud.
  
 **È possibile applicare un blocco eDiscovery o I criteri di conservazione di Office 365 agli utenti locali?**
  
No.
  
 **La ricerca di contenuto può trovare chat di Team precedenti per gli utenti locali prima del momento in cui l'organizzazione ha inviato la richiesta per abilitare questa funzionalità?**
  
Microsoft ha avviato l'archiviazione dei dati di chat dei team per gli utenti locali il 31 gennaio 2018. Pertanto, se l'identità di un utente di team locale è stata sincronizzata tra Active Directory e Azure Active Directory da questa data, i dati della chat dei team vengono archiviati in una cassetta postale basata sul cloud ed è possibile eseguire ricerche tramite ricerca contenuto. Microsoft sta lavorando anche per archiviare i dati della chat di Teams da prima del 31 gennaio 2018 nelle cassette postali basate sul cloud per gli utenti locali. Ulteriori informazioni su questo saranno disponibili a breve.

 **Gli utenti locali devono disporre di una licenza per archiviare i dati della chat dei team in una cassetta postale basata su cloud?**
  
Sì. Per archiviare i dati di chat dei team per un utente locale in una cassetta postale basata su cloud, all'utente deve essere assegnata una licenza Microsoft teams e una licenza di Exchange Online Plan in Office 365 (o Microsoft 365).
