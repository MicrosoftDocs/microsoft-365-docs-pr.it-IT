---
title: Ricerca di attività di eDiscovery nel registro di controllo di Office 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/24/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid: MOE150
ms.assetid: 67cc7f42-a53d-4751-b929-6005c80798f7
description: Informazioni su come eseguire la ricerca nel registro di controllo di Office 365 per gli eventi che vengono registrati quando gli amministratori di conformità eseguono le attività di ricerca contenuto e di eDiscovery nel centro sicurezza & Compliance.
ms.openlocfilehash: ef9c40debb8c28f0d017423d29016ca4f52b7a17
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/13/2020
ms.locfileid: "42634154"
---
# <a name="search-for-ediscovery-activities-in-the-office-365-audit-log"></a>Ricerca di attività di eDiscovery nel registro di controllo di Office 365

Le attività relative alla ricerca di contenuto e al eDiscovery eseguite in centro sicurezza & conformità o eseguendo i cmdlet di Windows PowerShell corrispondenti vengono registrate nel registro di controllo di Office 365. Gli eventi vengono registrati quando gli amministratori o gli amministratori di conformità (o qualsiasi utente a cui vengono assegnate le autorizzazioni di eDiscovery) eseguono le seguenti attività di ricerca contenuto e correlate a eDiscovery nel centro sicurezza & Compliance:
  
- Creazione e gestione di casi eDiscovery
    
- Creazione, avvio e modifica di ricerche di contenuto
    
- Esecuzione di operazioni di ricerca di contenuto, ad esempio visualizzazione in anteprima, esportazione ed eliminazione dei risultati della ricerca
    
- Configurazione del filtro delle autorizzazioni per Ricerca contenuto
    
- Gestione del ruolo di amministratore di eDiscovery
    
> [!IMPORTANT]
> Le attività descritte in questo articolo sono solo il risultato delle attività di eDiscovery eseguite tramite il Centro sicurezza & Compliance. le attività di eDiscovery eseguite utilizzando lo strumento eDiscovery in locale in Exchange Online o il centro eDiscovery in SharePoint Online non sono incluse. 
  
Per ulteriori informazioni sulla ricerca nel registro di controllo di Office 365, le autorizzazioni necessarie e l'esportazione dei risultati della ricerca, vedere [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).
  
## <a name="how-to-search-for-and-view-ediscovery-activities"></a>Informazioni su come cercare e visualizzare le attività di eDiscovery

Al momento, è necessario eseguire alcune operazioni specifiche per visualizzare le attività di eDiscovery nel registro di controllo di Office 365. Ecco come fare.
  
1. Passare a [https://protection.office.com](https://protection.office.com).
    
2. Accedere a Office 365 usando l'account aziendale o dell'istituto di istruzione.
    
3. Nel riquadro sinistro fare clic su **Cerca**e quindi su **Ricerca log di controllo**.
    
4. Nell'elenco a discesa **attività** , in **attività eDiscovery**, fare clic su una o più attività da cercare. In alternativa, è possibile fare clic su **eDiscovery** per cercare tutte le attività relative a eDiscovery. 
    
    > [!NOTE]
    > L'elenco a discesa attività include anche un gruppo di attività denominate **attività cmdlet di eDiscovery** che restituiscono record dal registro di controllo del cmdlet. 
  
5.  Selezionare un intervallo di data e ora per visualizzare gli eventi di eDiscovery che si sono verificati entro quel periodo. 
    
6. Nella casella **utenti** selezionare uno o più utenti per visualizzare i risultati della ricerca. Lasciare vuota questa casella per restituire le voci per tutti gli utenti. 
    
7. Fare clic su **Cerca** per eseguire la ricerca usando i criteri di ricerca. 
    
8. Dopo la visualizzazione dei risultati della ricerca, è possibile fare clic su **Filtra risultati** per filtrare o ordinare i record di attività risultanti. Purtroppo, non è possibile utilizzare il filtro per escludere in modo esplicito determinate attività. 
    
9. Per visualizzare i dettagli relativi a un'attività, fare clic sul record attività nell'elenco dei risultati della ricerca. 
    
    Viene visualizzata una pagina **Dettagli** che contiene le proprietà dettagliate del record di evento. Per visualizzare ulteriori dettagli, fare clic su **altre informazioni**. Per una descrizione di queste proprietà, vedere la sezione relativa alle [proprietà dettagliate per le attività di eDiscovery](#detailed-properties-for-ediscovery-activities) . 

  
## <a name="ediscovery-activities"></a>Attività di eDiscovery

Nella tabella seguente vengono descritte le attività relative alla ricerca del contenuto e eDiscovery registrate quando un amministratore o un utente esegue un'attività correlata a eDiscovery utilizzando il Centro sicurezza & conformità o eseguendo il cmdlet corrispondente in Remote PowerShell connesso al centro sicurezza & conformità dell'organizzazione. 
  
> [!NOTE]
> Le attività di eDiscovery descritte in questa sezione forniscono informazioni simili alle attività del cmdlet eDiscovery descritte nella sezione successiva. È consigliabile utilizzare le attività di eDiscovery descritte in questa sezione perché verranno visualizzate nei risultati della ricerca del registro di controllo entro 30 minuti. Per visualizzare le attività del cmdlet eDiscovery nei risultati di ricerca del registro di controllo, sono necessarie fino a 24 ore. 
  
|**Nome descrittivo**|**Operazione**|**Cmdlet corrispondente**|**Descrizione**|
|:-----|:-----|:-----|:-----|
|Aggiunta di un membro a un caso di eDiscovery  <br/> |CaseMemberAdded  <br/> |Add-ComplianceCaseMember  <br/> |Un utente è stato aggiunto come membro di un caso di eDiscovery. Come membro di un caso, un utente può eseguire diverse attività correlate al caso, a seconda che siano state assegnate le autorizzazioni necessarie.  <br/> |
|Ricerca di contenuto modificata  <br/> |SearchUpdated  <br/> |Set-ComplianceSearch  <br/> |È stata modificata una ricerca di contenuto esistente. Le modifiche possono includere l'aggiunta o la rimozione di percorsi di contenuto o la modifica della query di ricerca.  <br/> |
|Appartenenza all'amministratore di eDiscovery modificata  <br/> |CaseAdminUpdated  <br/> |Update-eDiscoveryCaseAdmin  <br/> |L'elenco degli amministratori di eDiscovery nell'organizzazione è stato modificato. Questa attività viene registrata quando l'elenco degli amministratori di eDiscovery viene sostituito con un gruppo di nuovi utenti. Se un singolo utente viene aggiunto o rimosso, viene registrata l'operazione CaseAdminAdded.  <br/> |
|Caso eDiscovery modificato  <br/> |CaseUpdated  <br/> |Set-ComplianceCase  <br/> |È stato modificato un caso di eDiscovery. Le modifiche includono la chiusura di un caso aperto o la riapertura di un caso chiuso.  <br/> |
|Appartenenza al caso di eDiscovery modificata  <br/> |CaseMemberUpdated  <br/> |Update-ComplianceCaseMember  <br/> |L'elenco dei membri di un caso di eDiscovery è stato modificato. Questa attività viene registrata quando tutti i membri vengono sostituiti con un gruppo di nuovi utenti. Se un singolo membro viene aggiunto o rimosso, viene registrata l'operazione CaseMemberAdded o CaseMemberRemoved.  <br/> |
|Filtro delle autorizzazioni di ricerca modificato  <br/> |SearchPermissionUpdated  <br/> |Set-ComplianceSecurityFilter  <br/> |È stato modificato un filtro delle autorizzazioni di ricerca.  <br/> |
|Modifica della query di ricerca per il blocco dei casi di eDiscovery  <br/> |HoldUpdated  <br/> |Set-CaseHoldRule  <br/> |Un blocco basato su query associato a un caso di eDiscovery è stato modificato. Le possibili modifiche includono la modifica dell'intervallo di query o di data per un blocco basato su query.  <br/> |
|Elemento di anteprima ricerca contenuto scaricato  <br/> |PreviewItemDownloaded  <br/> |N/D  <br/> |Un utente ha scaricato un elemento nel computer locale (facendo clic sul collegamento **Scarica elemento originale** ) quando si visualizzano in anteprima i risultati della ricerca.  <br/> |
|Elemento di anteprima ricerca contenuto elencato  <br/> |PreviewItemListed  <br/> |N/D  <br/> |Un utente ha fatto clic su **Anteprima risultati della ricerca** per visualizzare la pagina di anteprima dei risultati di ricerca, che elenca fino a 1000 elementi dai risultati di una ricerca di contenuto.  <br/> |
|Elemento di anteprima ricerca contenuto visualizzato  <br/> |PreviewItemRendered  <br/> |N/D  <br/> |Un Manager di eDiscovery ha visualizzato un elemento facendo clic su di esso quando si visualizzano in anteprima i risultati della ricerca.  <br/> |
|Ricerca contenuto creata  <br/> |SearchCreated  <br/> |New-ComplianceSearch  <br/> |È stata creata una nuova ricerca di contenuto.  <br/> |
|Creato amministratore di eDiscovery  <br/> |CaseAdminAdded  <br/> |Add-eDiscoveryCaseAdmin  <br/> |Un utente è stato aggiunto come amministratore di eDiscovery nell'organizzazione.  <br/> |
|Caso creato di eDiscovery  <br/> |CaseAdded  <br/> |New-ComplianceCase  <br/> |È stato creato un caso di eDiscovery. Quando viene creato un caso, è necessario assegnargli solo un nome. Altre attività correlate al caso, ad esempio l'aggiunta di membri, la creazione di esenzioni e la creazione di ricerche di contenuto associate al caso determinano la registrazione di eventi aggiuntivi.  <br/> |
|Filtro delle autorizzazioni di ricerca creato  <br/> |SearchPermissionCreated  <br/> |New-ComplianceSecurityFilter  <br/> |È stato creato un filtro delle autorizzazioni di ricerca.  <br/> |
|Creazione della query di ricerca per il blocco dei casi di eDiscovery  <br/> |HoldCreated  <br/> |New-CaseHoldRule  <br/> |È stato creato un blocco basato su query associato a un caso di eDiscovery.  <br/> |
|Ricerca di contenuto eliminata  <br/> |SearchRemoved  <br/> |Remove-ComplianceSearch  <br/> |È stata eliminata una ricerca di contenuto esistente.  <br/> |
|Amministratore eDiscovery eliminato  <br/> |CaseAdminRemoved  <br/> |Remove-eDiscoveryCaseAdmin  <br/> |Un amministratore di eDiscovery è stato eliminato dall'organizzazione.  <br/> |
|Caso di eDiscovery eliminato  <br/> |CaseRemoved  <br/> |Remove-ComplianceCase  <br/> |Un caso di eDiscovery è stato eliminato. Tenere presente che ogni esenzione associata al caso deve essere rimossa prima che sia possibile eliminare il caso.  <br/> |
|Filtro delle autorizzazioni di ricerca eliminato  <br/> |SearchPermissionRemoved  <br/> |Remove-ComplianceSecurityFilter  <br/> |È stato eliminato un filtro delle autorizzazioni di ricerca.  <br/> |
|Query di ricerca eliminata per il blocco dei casi di eDiscovery  <br/> |HoldRemoved  <br/> |Remove-CaseHoldRule  <br/> |Un blocco basato su query associato a un caso di eDiscovery è stato eliminato. La rimozione della query dall'esenzione è spesso il risultato dell'eliminazione di un'esenzione. Quando viene eliminata un'esenzione o una query di blocco, vengono rilasciati i percorsi di contenuto in attesa.  <br/> |
|Esportazione di ricerca contenuto scaricata  <br/> |SearchExportDownloaded  <br/> |N/D  <br/> |Un utente ha scaricato i risultati di una ricerca di contenuto nel proprio computer locale. Si noti che è necessario avviare un' **esportazione iniziale dell'attività di ricerca contenuto** prima di poter scaricare i risultati della ricerca.  <br/> |
|Risultati visualizzati in anteprima della ricerca contenuto  <br/> |SearchPreviewed  <br/> |N/D  <br/> |Un utente ha visualizzato in anteprima i risultati di una ricerca di contenuto.  <br/> |
|Risultati della ricerca contenuto eliminati  <br/> |SearchResultsPurged  <br/> |New-ComplianceSearchAction  <br/> |Un utente ha eliminato i risultati di una ricerca di contenuto eseguendo il comando **New-ComplianceSearchAction-Purge** .  <br/> |
|Analisi della ricerca di contenuto rimossa  <br/> |RemovedSearchResultsSentToZoom  <br/> |Remove-ComplianceSearchAction  <br/> |È stata eliminata una ricerca di contenuto per preparare l'azione (per preparare i risultati della ricerca per Office 365 Advanced eDiscovery). Se l'azione di preparazione ha meno di due settimane, i risultati della ricerca preparati per Advanced eDiscovery sono stati eliminati dall'area di archiviazione di Microsoft Azure. Se l'azione di preparazione è antecedente a 2 settimane, questo evento indica che è stata eliminata solo l'azione di preparazione corrispondente.  <br/> |
|Esportazione di ricerca contenuto rimossa  <br/> |RemovedSearchExported  <br/> |Remove-ComplianceSearchAction  <br/> |Un'azione di esportazione ricerca contenuto è stata eliminata. Se l'operazione di esportazione ha meno di due settimane, i risultati della ricerca caricati nell'area di archiviazione di Microsoft Azure sono stati eliminati. Se l'azione di esportazione è antecedente a 2 settimane, questo evento indica che è stata eliminata solo l'azione di esportazione corrispondente.  <br/> |
|Membri rimossi dal caso di eDiscovery  <br/> |CaseMemberRemoved  <br/> |Remove-ComplianceCaseMember  <br/> |Un utente è stato rimosso come membro di un caso di eDiscovery.  <br/> |
|Risultati dell'anteprima rimossi della ricerca contenuto  <br/> |RemovedSearchPreviewed  <br/> |Remove-ComplianceSearchAction  <br/> |È stata eliminata un'azione anteprima ricerca contenuto.  <br/> |
|Azione di eliminazione rimossa eseguita nella ricerca contenuto  <br/> |RemovedSearchResultsPurged  <br/> |Remove-ComplianceSearchAction  <br/> |È stata eliminata un'azione di eliminazione della ricerca del contenuto.  <br/> |
|Report di ricerca rimosso  <br/> |SearchReportRemoved  <br/> |Remove-ComplianceSearchAction  <br/> |È stata eliminata un'azione del rapporto di ricerca di contenuto esportazione.  <br/> |
|Analisi introduttiva della ricerca contenuto  <br/> |SearchResultsSentToZoom  <br/> |New-ComplianceSearchAction  <br/> |I risultati di una ricerca di contenuto sono stati preparati per l'analisi in Advanced eDiscovery.  <br/> |
|Ricerca di contenuto avviata  <br/> |SearchStarted  <br/> |Start-ComplianceSearch  <br/> |È stata avviata una ricerca di contenuto. Quando si crea o si modifica una ricerca di contenuto utilizzando l'interfaccia di amministrazione di sicurezza & Compliance Center, la ricerca viene avviata automaticamente. Se si crea o si modifica una ricerca utilizzando il cmdlet **New-ComplianceSearch** o **set-ComplianceSearch** , è necessario eseguire il cmdlet **Start-ComplianceSearch** per avviare la ricerca.  <br/> |
|Inizio esportazione della ricerca contenuto  <br/> |SearchExported  <br/> |New-ComplianceSearchAction  <br/> |Un utente ha esportato i risultati di una ricerca di contenuto.  <br/> |
|Report di esportazione avviato  <br/> |SearchReport  <br/> |New-ComplianceSearchAction  <br/> |Un utente ha esportato un rapporto di ricerca contenuto.  <br/> |
|Ricerca di contenuto interrotta  <br/> |SearchStopped  <br/> |Stop-ComplianceSearch  <br/> |Un utente ha interrotto una ricerca di contenuto.  <br/> |
  
## <a name="ediscovery-cmdlet-activities"></a>attività del cmdlet eDiscovery

Nella tabella seguente sono elencati i record del registro di controllo del cmdlet che vengono registrati quando un amministratore o un utente esegue un'attività correlata a eDiscovery utilizzando il Centro sicurezza & Compliance oppure eseguendo il cmdlet corrispondente in Remote PowerShell connesso al centro sicurezza & conformità dell'organizzazione. Si noti che le informazioni dettagliate nel record del registro di controllo sono diverse per le attività dei cmdlet elencate in questa tabella e le attività di eDiscovery descritte nella sezione precedente. 
  
Come indicato in precedenza, sono necessarie fino a 24 ore prima che le attività del cmdlet di eDiscovery vengano visualizzate nei risultati di ricerca del registro di controllo.
  
> [!TIP]
> I cmdlet della colonna **Operation** nella tabella seguente sono collegati all'argomento della guida del cmdlet corrispondente su TechNet. Passare all'argomento della guida del cmdlet per una descrizione dei parametri disponibili per ogni cmdlet. Il parametro e il valore del parametro utilizzati con un cmdlet sono inclusi nella voce del registro di controllo per ogni attività del cmdlet eDiscovery registrata. 
  
|**Nome descrittivo**|**Operazione (cmdlet)**|**Descrizione**|
|:-----|:-----|:-----|
|Blocco creato nel caso di eDiscovery  <br/> |[New-CaseHoldPolicy](https://go.microsoft.com/fwlink/p/?LinkId=823813) <br/> |È stata creata un'esenzione per un caso di eDiscovery. È possibile creare un'esenzione con o senza specificare un'origine di contenuto. Se vengono specificate origini di contenuto, verranno identificate nella voce del registro di controllo.  <br/> |
|Blocco eliminato dal caso di eDiscovery  <br/> |[Remove-CaseHoldPolicy](https://go.microsoft.com/fwlink/p/?LinkId=823814) <br/> |Un'esenzione associata a un caso di eDiscovery è stata eliminata. L'eliminazione di un'esenzione rilascia tutti i percorsi di contenuto dall'esenzione. L'eliminazione dell'esenzione comporta anche l'eliminazione delle regole di blocco del caso associate all'esenzione (vedere **Remove-CaseHoldRule** below).  <br/> |
|Blocco modificato nel caso di eDiscovery  <br/> |[Set-CaseHoldPolicy](https://go.microsoft.com/fwlink/p/?LinkId=823815) <br/> |Un'esenzione associata a un eDiscovery è stata modificata. Le possibili modifiche includono l'aggiunta o la rimozione di posizioni di contenuto o la disattivazione del blocco.  <br/> |
|Creazione della query di ricerca per il blocco dei casi di eDiscovery  <br/> |[New-CaseHoldRule](https://go.microsoft.com/fwlink/p/?LinkId=823816) <br/> |È stato creato un blocco basato su query associato a un caso di eDiscovery.  <br/> |
|Query di ricerca eliminata per il blocco dei casi di eDiscovery  <br/> |[Remove-CaseHoldRule](https://go.microsoft.com/fwlink/p/?LinkId=823820) <br/> |Un blocco basato su query associato a un caso di eDiscovery è stato eliminato. La rimozione della query dall'esenzione è spesso il risultato dell'eliminazione di un'esenzione. Quando viene eliminata un'esenzione o una query di blocco, vengono rilasciati i percorsi di contenuto in attesa.  <br/> |
|Modifica della query di ricerca per il blocco dei casi di eDiscovery  <br/> |[Set-CaseHoldRule](https://go.microsoft.com/fwlink/p/?LinkId=823819) <br/> |Un blocco basato su query associato a un caso di eDiscovery è stato modificato. Le possibili modifiche includono la modifica dell'intervallo di query o di data per un blocco basato su query.  <br/> |
|Caso creato di eDiscovery  <br/> |[New-ComplianceCase](https://go.microsoft.com/fwlink/p/?LinkId=823842) <br/> |È stato creato un caso di eDiscovery. Quando viene creato un caso, è necessario assegnargli solo un nome. Altre attività correlate al caso, ad esempio l'aggiunta di membri, la creazione di esenzioni e la creazione di ricerche di contenuto associate al caso determinano la registrazione di eventi aggiuntivi.  <br/> |
|Caso di eDiscovery eliminato  <br/> |[Remove-ComplianceCase](https://go.microsoft.com/fwlink/p/?LinkId=823844) <br/> |Un caso di eDiscovery è stato eliminato. Tenere presente che ogni esenzione associata al caso deve essere rimossa prima che sia possibile eliminare il caso.  <br/> |
|Caso eDiscovery modificato  <br/> |[Set-ComplianceCase](https://go.microsoft.com/fwlink/p/?LinkId=823846) <br/> |È stato modificato un caso di eDiscovery. Le modifiche includono la chiusura di un caso aperto o la riapertura di un caso chiuso.  <br/> |
|Aggiunta di un membro a un caso di eDiscovery  <br/> |[Add-ComplianceCaseMember](https://go.microsoft.com/fwlink/p/?LinkId=823848) <br/> |Un utente è stato aggiunto come membro di un caso di eDiscovery. Come membro di un caso, un utente può eseguire diverse attività correlate al caso, a seconda che siano state assegnate le autorizzazioni necessarie.  <br/> |
|Membri rimossi dal caso di eDiscovery  <br/> |[Remove-ComplianceCaseMember](https://go.microsoft.com/fwlink/p/?LinkId=823849) <br/> |Un utente è stato rimosso come membro di un caso di eDiscovery.  <br/> |
|Appartenenza al caso di eDiscovery modificata  <br/> |[Update-ComplianceCaseMember](https://go.microsoft.com/fwlink/p/?LinkId=823850) <br/> |L'elenco dei membri di un caso di eDiscovery è stato modificato. Questa attività viene registrata quando tutti i membri vengono sostituiti con un gruppo di nuovi utenti. Se un singolo membro viene aggiunto o rimosso, viene registrata l'operazione **Add-ComplianceCaseMember** o **Remove-ComplianceCaseMember** .  <br/> |
|Ricerca contenuto creata  <br/> |[New-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517935) <br/> |È stata creata una nuova ricerca di contenuto.  <br/> |
|Ricerca di contenuto eliminata  <br/> |[Remove-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517936) <br/> |È stata eliminata una ricerca di contenuto esistente.  <br/> |
|Ricerca di contenuto modificata  <br/> |[Set-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517937) <br/> |È stata modificata una ricerca di contenuto esistente. Le modifiche possono includere l'aggiunta o la rimozione di percorsi di contenuto che vengono ricercati e la modifica della query di ricerca.  <br/> |
|Ricerca di contenuto avviata  <br/> |[Start-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517938) <br/> |È stata avviata una ricerca di contenuto. Quando si crea o si modifica una ricerca di contenuto utilizzando l'interfaccia di amministrazione di sicurezza & Compliance Center, la ricerca viene avviata automaticamente. Se si crea o si modifica una ricerca utilizzando il cmdlet **New-ComplianceSearch** o **set-ComplianceSearch** , è necessario eseguire il cmdlet **Start-ComplianceSearch** per avviare la ricerca.  <br/> |
|Ricerca di contenuto interrotta  <br/> |[Stop-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517939) <br/> |Una ricerca di contenuto in esecuzione è stata interrotta.  <br/> |
|Azione di ricerca contenuto creata  <br/> |[New-ComplianceSearchAction](https://go.microsoft.com/fwlink/p/?LinkId=527971) <br/> |È stata creata un'azione di ricerca del contenuto. Le azioni di ricerca contenuto includono l'anteprima dei risultati della ricerca, l'esportazione dei risultati di ricerca, la preparazione dei risultati della ricerca per l'analisi in Office 365 Advanced eDiscovery e l'eliminazione definitiva degli elementi che soddisfano i criteri di ricerca di una ricerca di contenuto.  <br/> |
|Azione di ricerca contenuto eliminata  <br/> |[Remove-ComplianceSearchAction](https://go.microsoft.com/fwlink/p/?LinkId=824027) <br/> |È stata eliminata un'azione di ricerca del contenuto.  <br/> |
|Filtro delle autorizzazioni di ricerca creato  <br/> |[New-ComplianceSecurityFilter](https://go.microsoft.com/fwlink/p/?LinkId=617542) <br/> |È stato creato un filtro delle autorizzazioni di ricerca.  <br/> |
|Filtro delle autorizzazioni di ricerca eliminato  <br/> |[Remove-ComplianceSecurityFilter](https://go.microsoft.com/fwlink/p/?LinkId=617543) <br/> |È stato eliminato un filtro delle autorizzazioni di ricerca.  <br/> |
|Filtro delle autorizzazioni di ricerca modificato  <br/> |[Set-ComplianceSecurityFilter](https://go.microsoft.com/fwlink/p/?LinkId=617544) <br/> |È stato modificato un filtro delle autorizzazioni di ricerca.  <br/> |
|Creato amministratore di eDiscovery  <br/> |[Add-eDiscoveryCaseAdmin](https://go.microsoft.com/fwlink/p/?LinkId=798217) <br/> |Un utente è stato aggiunto come amministratore di eDiscovery nell'organizzazione.  <br/> |
|Amministratore eDiscovery eliminato  <br/> |[Remove-eDiscoveryCaseAdmin](https://go.microsoft.com/fwlink/p/?LinkId=823945) <br/> |Un amministratore di eDiscovery è stato eliminato dall'organizzazione.  <br/> |
|Appartenenza all'amministratore di eDiscovery modificata  <br/> |[Update-eDiscoveryCaseAdmin](https://go.microsoft.com/fwlink/p/?LinkId=823946) <br/> |L'elenco degli amministratori di eDiscovery nell'organizzazione è stato modificato. Questa attività viene registrata quando l'elenco degli amministratori di eDiscovery viene sostituito con un gruppo di nuovi utenti. Se si aggiunge o si rimuove un singolo utente, viene registrata l'operazione **Add-eDiscoveryCaseAdmin** o **Remove-eDiscoveryCaseAdmin** .  <br/> |
   
## <a name="detailed-properties-for-ediscovery-activities"></a>Proprietà dettagliate per le attività di eDiscovery

Nella tabella seguente vengono descritte le proprietà incluse quando si fa clic su **altre informazioni** nella pagina dei **Dettagli** per un'attività di eDiscovery elencata nei risultati della ricerca. Queste proprietà sono incluse anche nel file CSV quando si esportano i risultati della ricerca del registro di controllo. Si noti che un record del registro di controllo per un'attività di eDiscovery non includerà tutte le proprietà dettagliate elencate di seguito. 
  
> [!TIP]
> Quando si esportano i risultati della ricerca, il file CSV contiene una colonna denominata **detail**, che contiene le proprietà dettagliate descritte nella tabella riportata di seguito in una proprietà multivalore. È possibile utilizzare la funzionalità Power query in Excel per dividere la colonna in più colonne in modo che ogni proprietà disponga di una colonna. In questo modo si consente di ordinare e filtrare una o più di queste proprietà. Per ulteriori informazioni, vedere la sezione "esportare i risultati della ricerca in un file" in [Search the audit log](search-the-audit-log-in-security-and-compliance.md#step-4-export-the-search-results-to-a-file). 
  
|**Proprietà**|**Descrizione**|
|:-----|:-----|
|Caso  <br/> |L'identità (GUID) del caso di eDiscovery che è stato creato, modificato o eliminato.  <br/> |
|ClientApplication  <br/> |le attività del cmdlet eDiscovery dispongono di un valore **EMC** per questa proprietà. Questo indica che l'attività è stata eseguita utilizzando il Centro sicurezza & Compliance GUI o l'esecuzione del cmdlet in PowerShell.  <br/> |
|ClientIP  <br/> |L'indirizzo IP del dispositivo utilizzato quando è stata registrata l'attività. L'indirizzo IP viene visualizzato in formato IPv4 o IPv6.  <br/> |
|ClientRequestId  <br/> | Per le attività di eDiscovery, questa proprietà è in genere vuota.  <br/> |
|CmdletVersion  <br/> |Il numero di build per la versione del Centro sicurezza & compliance in esecuzione nell'organizzazione.  <br/> |
|CreationTime  <br/> |Data e ora in formato UTC (Coordinated Universal Time) quando è stata completata l'attività eDiscovery.  <br/> |
|EffectiveOrganization  <br/> |Nome dell'organizzazione di Office 365.  <br/> |
|ExchangeLocations  <br/> |Le cassette postali di Exchange Online incluse in una ricerca di contenuto o in blocco in un caso di eDiscovery.  <br/> |
|Esclusioni  <br/> |Cassette postali o siti che sono esclusi da una ricerca di contenuto o da un'esenzione in un caso di eDiscovery.  <br/> |
|ExtendedProperties  <br/> |Altre proprietà di una ricerca di contenuto, un'azione di ricerca del contenuto o una conservazione in un caso di eDiscovery, ad esempio il GUID dell'oggetto e il cmdlet e i parametri del cmdlet corrispondenti che sono stati utilizzati al momento dell'esecuzione dell'attività.  <br/> |
|Id  <br/> |ID della voce del report. L'ID identifica in modo univoco la voce del registro di controllo.  <br/> |
|NonPIIParameters  <br/> |Elenco dei parametri (senza valori) utilizzati con il cmdlet identificato nella proprietà Operation. I parametri elencati in questa proprietà sono uguali a quelli elencati nella proprietà Parameters.  <br/> |
|ObjectId  <br/> |Il GUID o il nome dell'oggetto, ad esempio una ricerca di contenuto o un caso di eDiscovery, che è stato creato, modificato o eliminato dall'attività elencata nella proprietà Operation. Questo oggetto viene identificato anche nella colonna elemento dei risultati di ricerca del registro di controllo.  <br/> |
|ObjectType  <br/> |Il tipo di oggetto eDiscovery che l'utente ha creato, eliminato o modificato. ad esempio, un'azione di ricerca del contenuto (anteprima, esportazione o eliminazione), un caso di eDiscovery o una ricerca di contenuto.  <br/> |
|Operazione  <br/> |Nome dell'operazione che corrisponde all'attività eDiscovery che è stata eseguita.  <br/> |
|IDOrganizzazione  <br/> |GUID per l'organizzazione di Office 365.  <br/> |
|Parametri  <br/> |Il nome e il valore dei parametri utilizzati con il cmdlet corrispondente.  <br/> |
|PublicFolderLocations  <br/> |Posizioni delle cartelle pubbliche in Exchange Online incluse in una ricerca di contenuto o in attesa in un caso di eDiscovery.  <br/> |
|Query  <br/> |Query di ricerca associata all'attività, ad esempio una ricerca di contenuto o un blocco basato su query.  <br/> |
|RecordType  <br/> |Specifica il tipo di operazione indicata dal record. Il valore **18** indica un evento correlato a un'attività elencata nella sezione [attività cmdlet di eDiscovery](#ediscovery-cmdlet-activities) . Il valore **24** indica un evento correlato a un'attività elencata nella sezione informazioni [su come cercare e visualizzare le attività di eDiscovery](#how-to-search-for-and-view-ediscovery-activities) .  <br/> |
|ResultStatus  <br/> |Indica se l'azione (specificata nella proprietà Operation) ha avuto esito positivo o meno.  <br/> |
|SecurityComplianceCenterEventType  <br/> |Indica che l'attività è stata un evento del Centro sicurezza & conformità. Tutte le attività di eDiscovery avranno un valore pari a **0** per questa proprietà.  <br/> |
|SharepointLocations  <br/> |I siti di SharePoint Online inclusi in una ricerca di contenuto o in blocco in un caso di eDiscovery.  <br/> |
|StartTime  <br/> |Data e ora in formato UTC (Coordinated Universal Time) quando è stata avviata l'attività eDiscovery.  <br/> |
|UserId  <br/> |L'utente che ha eseguito l'attività, specificata nella proprietà Operation, che ha provocato la registrazione del record. Si noti che i record per l'attività di eDiscovery eseguita dagli account di sistema (come NT AUTHORITY\SYSTEM) sono inclusi anche nel registro di controllo.  <br/> |
|UserKey  <br/> |ID alternativo per l'utente identificato nella proprietà UserId. Per le attività di eDiscovery, il valore di questa proprietà è in genere identico a quello della proprietà UserId.  <br/> |
|UserServicePlan  <br/> |La sottoscrizione di Office 365 utilizzata dall'organizzazione. Per le attività di eDiscovery, questa proprietà è in genere vuota.  <br/> |
|UserType  <br/> |Il tipo di utente che ha eseguito l'operazione. I valori riportati di seguito indicano il tipo di utente.  <br/> 0 un utente normale. 2 un amministratore dell'organizzazione di Office 365. 3 un account di sistema dell'amministratore o del datacenter di Microsoft datacenter. 4 un account di sistema. 5 un'applicazione. 6 un'entità di servizio. |
|Version  <br/> |Indica il numero di versione dell'attività (identificata dalla proprietà Operation) registrata.  <br/> |
|Carico di lavoro  <br/> |Il servizio Office 365 in cui si è verificata l'attività. Per le attività di eDiscovery, il valore è **SecurityComplianceCenter**.  <br/> |
