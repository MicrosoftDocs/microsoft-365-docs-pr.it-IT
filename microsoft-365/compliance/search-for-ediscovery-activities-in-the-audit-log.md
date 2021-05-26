---
title: Cercare le attività di eDiscovery nel log di controllo
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 67cc7f42-a53d-4751-b929-6005c80798f7
description: Informazioni sugli eventi registrati quando gli utenti a cui sono assegnate autorizzazioni di eDiscovery eseguono le attività ricerca contenuto, Core eDiscovery e Advanced eDiscovery nel Centro Microsoft 365 conformità.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8b1f3f235f3411e2f637e4e32104c6179643757d
ms.sourcegitcommit: 4f6ef4cd09c3ed36dc0be3702b0636bad6cff8a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/26/2021
ms.locfileid: "52657694"
---
# <a name="search-for-ediscovery-activities-in-the-audit-log"></a>Cercare le attività di eDiscovery nel log di controllo

Le attività correlate a Ricerca contenuto e eDiscovery (per Core eDiscovery e Advanced eDiscovery) eseguite nel Centro conformità di Microsoft 365 o eseguendo i cmdlet di PowerShell corrispondenti vengono registrate nel log di controllo. Gli eventi vengono registrati quando gli amministratori o i responsabili di eDiscovery (o qualsiasi utente a cui sono state assegnate autorizzazioni di eDiscovery) eseguono le attività di ricerca contenuto e eDiscovery di base seguenti nel Centro conformità di Microsoft 365:
  
- Creazione e gestione di core e Advanced eDiscovery casi

- Creazione, avvio e modifica di ricerche contenuto

- Esecuzione di azioni di ricerca, ad esempio l'anteprima, l'esportazione e l'eliminazione dei risultati della ricerca

- Gestione dei custodi e dei set di revisione in Advanced eDiscovery

- Configurazione del filtro delle autorizzazioni per ricerca contenuto

- Gestione del ruolo di amministratore di eDiscovery
  
Per ulteriori informazioni sulla ricerca nel log di controllo, sulle autorizzazioni necessarie e sull'esportazione dei risultati della ricerca, vedere [Search the audit log in the Microsoft 365 compliance center](search-the-audit-log-in-security-and-compliance.md).
  
## <a name="how-to-search-for-and-view-ediscovery-activities"></a>Come cercare e visualizzare le attività di eDiscovery

Attualmente, è necessario eseguire alcune operazioni specifiche per visualizzare le attività di eDiscovery nel log di controllo. Ecco come fare.
  
1. Vai a <https://compliance.microsoft.com> e accedi usando il tuo account aziendale o dell'istituto di istruzione.

2. Nel riquadro di spostamento sinistro del Centro Microsoft 365 conformità fare clic **su Mostra tutto** e quindi su **Controlla.**

3. **Nell'elenco a** discesa Attività, in Attività **di eDiscovery** o **Advanced eDiscovery,** fare clic su una o più attività da cercare.

    > [!NOTE]
    > **L'elenco** a discesa Attività include anche un gruppo di attività denominate **attività cmdlet di eDiscovery** che restituiscono record dal log di controllo del cmdlet.
  
4. Selezionare un intervallo di data e ora per visualizzare gli eventi di eDiscovery che si sono verificati all'interno di tale periodo.

5. Nella casella **Utenti** selezionare uno o più utenti per cui visualizzare i risultati della ricerca. Lasciare vuota questa casella per restituire le voci per tutti gli utenti.

6. Fare clic su **Cerca** per eseguire la ricerca usando i criteri di ricerca.

7. Dopo aver visualizzato i risultati della ricerca, è possibile fare clic su **Filtra risultati** per filtrare o ordinare i record attività risultanti. Purtroppo, non è possibile utilizzare il filtro per escludere in modo esplicito determinate attività. 

8. Per visualizzare i dettagli di un'attività, fare clic sul record dell'attività nell'elenco dei risultati della ricerca. 

    Viene **visualizzata** una pagina a comparsa Dettagli contenente le proprietà dettagliate del record dell'evento. Per visualizzare ulteriori dettagli, fare clic **su Altre informazioni.** Per una descrizione di queste proprietà, vedere la [sezione Proprietà dettagliate per le attività di eDiscovery.](#detailed-properties-for-ediscovery-activities)

9. Se lo si desidera, è possibile esportare i risultati della ricerca nei log di controllo in un file CSV e quindi utilizzare la funzionalità power query di Excel per formattare e filtrare questi record. Per ulteriori informazioni, vedi [Esportare, configurare e visualizzare i record del log di audit](export-view-audit-log-records.md).

## <a name="ediscovery-activities"></a>Attività di eDiscovery

Nella tabella seguente vengono descritte le attività ricerca contenuto ed eDiscovery di base registrate quando un amministratore o un responsabile di eDiscovery esegue un'attività correlata a eDiscovery utilizzando il Centro conformità o eseguendo il cmdlet corrispondente in PowerShell del Centro sicurezza & conformità. Si noti inoltre che alcune attività eseguite in Advanced eDiscovery potrebbero essere restituite quando si esegue la ricerca di attività in questo elenco.
  
> [!NOTE]
> Le attività di eDiscovery descritte in questa sezione forniscono informazioni simili alle attività dei cmdlet di eDiscovery descritte nella sezione successiva. È consigliabile utilizzare le attività di eDiscovery descritte in questa sezione perché verranno visualizzate nei risultati della ricerca nei log di controllo entro 30 minuti. Sono necessari fino a 24 ore prima che le attività del cmdlet eDiscovery vengano visualizzate nei risultati della ricerca nei log di controllo.
  
|**Nome descrittivo**|**Operazione**|**Cmdlet corrispondente**|**Descrizione**|
|:-----|:-----|:-----|:-----|
|Membro aggiunto al caso di eDiscovery  <br/> |CaseMemberAdded  <br/> |Add-ComplianceCaseMember  <br/> |Un utente è stato aggiunto come membro di un caso di eDiscovery. Come membro di un caso, un utente può eseguire diverse attività correlate al caso a seconda che gli siano state assegnate le autorizzazioni necessarie.  <br/> |
|Ricerca contenuto modificata  <br/> |SearchUpdated  <br/> |Set-ComplianceSearch  <br/> |È stata modificata una ricerca di contenuto esistente. Le modifiche possono includere l'aggiunta o la rimozione di percorsi di contenuto o la modifica della query di ricerca.  <br/> |
|Appartenenza all'amministratore di eDiscovery modificata  <br/> |CaseAdminUpdated  <br/> |Update-eDiscoveryCaseAdmin  <br/> |L'elenco degli amministratori di eDiscovery nell'organizzazione è stato modificato. Questa attività viene registrata quando l'elenco degli amministratori di eDiscovery viene sostituito con un gruppo di nuovi utenti. Se viene aggiunto o rimosso un singolo utente, viene registrata l'operazione CaseAdminAdded.  <br/> |
|Caso di eDiscovery modificato  <br/> |CaseUpdated  <br/> |Set-ComplianceCase  <br/> |Un caso di eDiscovery è stato modificato. Le modifiche includono la chiusura di un caso aperto o la riapertura di un caso chiuso.  <br/> |
|Appartenenza a un caso di eDiscovery modificato  <br/> |CaseMemberUpdated  <br/> |Update-ComplianceCaseMember  <br/> |L'elenco di appartenenze di un caso di eDiscovery è stato modificato. Questa attività viene registrata quando tutti i membri vengono sostituiti con un gruppo di nuovi utenti. Se viene aggiunto o rimosso un singolo membro, viene registrata l'operazione CaseMemberAdded o CaseMemberRemoved.  <br/> |
|Filtro delle autorizzazioni di ricerca modificato  <br/> |SearchPermissionUpdated  <br/> |Set-ComplianceSecurityFilter  <br/> |È stato modificato un filtro delle autorizzazioni di ricerca.  <br/> |
|Query di ricerca modificata per il blocco caso di eDiscovery  <br/> |HoldUpdated  <br/> |Set-CaseHoldRule  <br/> |È stata modificata una conservazione basata su query associata a un caso di eDiscovery. Le possibili modifiche includono la modifica della query o dell'intervallo di date per un blocco basato su query.  <br/> |
|Elemento di anteprima ricerca contenuto scaricato  <br/> |PreviewItemDownloaded  <br/> |N/D  <br/> |Un utente ha scaricato un elemento nel computer locale (facendo clic sul **collegamento Scarica elemento** originale) durante l'anteprima dei risultati della ricerca.  <br/> |
|Elemento di anteprima ricerca contenuto elencato  <br/> |PreviewItemListed  <br/> |N/D  <br/> |Un utente  ha fatto clic su Anteprima risultati di ricerca per visualizzare la pagina dei risultati di ricerca di anteprima, in cui sono elencati fino a 1000 elementi dai risultati di una ricerca contenuto.  <br/> |
|Elemento di anteprima della ricerca contenuto visualizzato  <br/> |PreviewItemRendered  <br/> |N/D  <br/> |Un responsabile di eDiscovery ha visualizzato un elemento facendo clic su di esso durante l'anteprima dei risultati della ricerca.  <br/> |
|Ricerca contenuto creata  <br/> |SearchCreated  <br/> |New-ComplianceSearch  <br/> |È stata creata una nuova ricerca contenuto.  <br/> |
|Amministratore di eDiscovery creato  <br/> |CaseAdminAdded  <br/> |Add-eDiscoveryCaseAdmin  <br/> |Un utente è stato aggiunto come amministratore di eDiscovery nell'organizzazione.  <br/> |
|Caso di eDiscovery creato  <br/> |CaseAdded  <br/> |New-ComplianceCase  <br/> |È stato creato un caso di eDiscovery. Quando viene creato un caso, è necessario assegnargli solo un nome. Altre attività correlate al caso, ad esempio l'aggiunta di membri, la creazione di blocchi e la creazione di ricerche di contenuto associate al caso, comportano la registrazione di eventi aggiuntivi.  <br/> |
|Filtro autorizzazioni di ricerca creato  <br/> |SearchPermissionCreated  <br/> |New-ComplianceSecurityFilter  <br/> |È stato creato un filtro delle autorizzazioni di ricerca.  <br/> |
|Query di ricerca creata per il blocco caso di eDiscovery  <br/> |HoldCreated  <br/> |New-CaseHoldRule  <br/> |È stata creata un'esenzione basata su query associata a un caso di eDiscovery.  <br/> |
|Ricerca contenuto eliminata  <br/> |SearchRemoved  <br/> |Remove-ComplianceSearch  <br/> |È stata eliminata una ricerca di contenuto esistente.  <br/> |
|Amministratore di eDiscovery eliminato  <br/> |CaseAdminRemoved  <br/> |Remove-eDiscoveryCaseAdmin  <br/> |Un amministratore di eDiscovery è stato eliminato dall'organizzazione.  <br/> |
|Caso di eDiscovery eliminato  <br/> |CaseRemoved  <br/> |Remove-ComplianceCase  <br/> |Un caso di eDiscovery è stato eliminato. Per poter eliminare il caso, è necessario rimuovere qualsiasi blocco associato al caso.  <br/> |
|Filtro delle autorizzazioni di ricerca eliminate  <br/> |SearchPermissionRemoved  <br/> |Remove-ComplianceSecurityFilter  <br/> |È stato eliminato un filtro delle autorizzazioni di ricerca.  <br/> |
|Query di ricerca eliminata per il blocco caso di eDiscovery  <br/> |HoldRemoved  <br/> |Remove-CaseHoldRule  <br/> |Un blocco basato su query associato a un caso di eDiscovery è stato eliminato. La rimozione della query dal blocco è spesso il risultato dell'eliminazione di un'esenzione. Quando viene eliminata un'esenzione o una query di blocco, vengono rilasciati i percorsi del contenuto in attesa.  <br/> |
|Esportazione scaricata della ricerca contenuto  <br/> |SearchExportDownloaded  <br/> |N/D  <br/> |Un utente ha scaricato i risultati di una ricerca di contenuto nel computer locale. Prima **di poter scaricare i risultati della** ricerca, è necessario iniziare l'esportazione avviata dell'attività di ricerca contenuto.  <br/> |
|Risultati visualizzati in anteprima della ricerca contenuto  <br/> |SearchPreviewed  <br/> |N/D  <br/> |Un utente ha visualizzato in anteprima i risultati di una ricerca di contenuto.  <br/> |
|Risultati eliminati della ricerca contenuto  <br/> |SearchResultsPurged  <br/> |New-ComplianceSearchAction  <br/> |Un utente ha eliminato i risultati di una ricerca di contenuto eseguendo il **comando New-ComplianceSearchAction -Purge.**  <br/> |
|Analisi rimossa della ricerca contenuto  <br/> |RemovedSearchResultsSentToZoom  <br/> |Remove-ComplianceSearchAction  <br/> |Un'azione di preparazione della ricerca contenuto (per preparare i risultati della Advanced eDiscovery) è stata eliminata. Se l'azione di preparazione è precedente a meno di due settimane, i risultati della ricerca preparati per Advanced eDiscovery sono stati eliminati dall'Microsoft Azure di archiviazione. Se l'azione di preparazione è precedente a 2 settimane, questo evento indica che è stata eliminata solo l'azione di preparazione corrispondente.  <br/> |
|È stata rimossa l'esportazione della ricerca contenuto  <br/> |RemovedSearchExported  <br/> |Remove-ComplianceSearchAction  <br/> |Un'azione di esportazione della ricerca contenuto è stata eliminata. Se l'azione di esportazione ha meno di due settimane, i risultati della ricerca caricati nell'area di Microsoft Azure di archiviazione sono stati eliminati. Se l'azione di esportazione è precedente a 2 settimane, questo evento indica che è stata eliminata solo l'azione di esportazione corrispondente.  <br/> |
|Membro rimosso dal caso di eDiscovery  <br/> |CaseMemberRemoved  <br/> |Remove-ComplianceCaseMember  <br/> |Un utente è stato rimosso come membro di un caso di eDiscovery.  <br/> |
|Risultati di anteprima rimossi della ricerca contenuto  <br/> |RemovedSearchPreviewed  <br/> |Remove-ComplianceSearchAction  <br/> |Un'azione di anteprima della ricerca contenuto è stata eliminata.  <br/> |
|Azione di eliminazione rimossa eseguita nella ricerca contenuto  <br/> |RemovedSearchResultsPurged  <br/> |Remove-ComplianceSearchAction  <br/> |Un'azione di eliminazione della ricerca contenuto è stata eliminata.  <br/> |
|Report di ricerca rimosso  <br/> |SearchReportRemoved  <br/> |Remove-ComplianceSearchAction  <br/> |Un'azione del report esportazione ricerca contenuto è stata eliminata.  <br/> |
|Analisi avviata della ricerca di contenuto  <br/> |SearchResultsSentToZoom  <br/> |New-ComplianceSearchAction  <br/> |I risultati di una ricerca di contenuto sono stati preparati per l'analisi in Advanced eDiscovery.  <br/> |
|Ricerca contenuto avviata  <br/> |SearchStarted  <br/> |Start-ComplianceSearch  <br/> |È stata avviata una ricerca di contenuto. Quando si crea o si modifica una ricerca di contenuto utilizzando l Microsoft 365 gui del Centro conformità, la ricerca viene avviata automaticamente. Se si crea o si modifica una ricerca utilizzando il cmdlet **New-ComplianceSearch** o **Set-ComplianceSearch,** è necessario eseguire il cmdlet **Start-ComplianceSearch** per avviare la ricerca.  <br/> |
|Esportazione avviata della ricerca contenuto  <br/> |SearchExported  <br/> |New-ComplianceSearchAction  <br/> |Un utente ha esportato i risultati di una ricerca di contenuto.  <br/> |
|Report di esportazione avviato  <br/> |SearchReport  <br/> |New-ComplianceSearchAction  <br/> |Un utente ha esportato un report di ricerca contenuto.  <br/> |
|Ricerca contenuto interrotta  <br/> |SearchStopped  <br/> |Stop-ComplianceSearch  <br/> |Un utente ha interrotto una ricerca di contenuto.  <br/> |
|(nessuno)|CaseViewed|Get-ComplianceCase|Un utente ha visualizzato l'elenco dei casi nella pagina Core **eDiscovery** o nella pagina **Advanced eDiscovery** nel Centro conformità o eseguendo il cmdlet Get-ComplianceCase.|
|(nessuno)|SearchViewed|Get-ComplianceSearch|Un utente ha visualizzato l'elenco nelle ricerche di contenuto (elencate nella scheda **Ricerche)** nel Centro conformità o eseguendo il cmdlet. Questa attività viene registrata anche quando un utente visualizza l'elenco delle  ricerche di contenuto associate a un caso di eDiscovery (facendo clic sulla scheda Ricerche in un caso) o eseguendo il **comando Get-ComplianceSearch -Case.**|
|(nessuno)|ViewedSearchExported|Get-ComplianceSearchAction -Export|Un utente ha visualizzato l'elenco dei  processi di esportazione della ricerca contenuto (elencati nella scheda Esportazioni) nel Centro conformità o eseguendo il cmdlet. Questa attività viene registrata anche quando un utente visualizza l'elenco dei  processi di esportazione in un caso di eDiscovery (elencato nella scheda Esportazioni in un caso) o eseguendo il **comando Get-ComplianceSearchAction -Case -Export.**|
|(nessuno)|ViewedSearchPreviewed|Get-ComplianceSearchAction -Preview|Un utente visualizza in anteprima i risultati di una ricerca di contenuto nel Centro conformità o eseguendo il cmdlet.|
|||||
  
## <a name="advanced-ediscovery-activities"></a>Attività di Advanced eDiscovery 

Nella tabella seguente vengono descritte le Advanced eDiscovery attività registrate nel log di controllo. Queste attività possono essere usate per tenere traccia della progressione dell'attività in un Advanced eDiscovery caso.

|**Nome descrittivo**|**Operazione**|**Descrizione**|
|:-----|:-----|:-----|
|Aggiungere dati a un altro insieme da rivedere|AddWorkingSetQueryToWorkingSet|L'utente ha aggiunto i documenti di un insieme da rivedere a un altro insieme da rivedere.|
|Aggiunti dati a un insieme da rivedere|AddQueryToWorkingSet|L'utente ha aggiunto i risultati della ricerca da una ricerca di contenuto associata a un caso di Advanced eDiscovery a un insieme da rivedere.|
|Sono stati aggiunti dati non di Microsoft 365 a un insieme da rivedere|AddNonOffice365DataToWorkingSet|L'utente ha aggiunto dati non di Microsoft 365 a un insieme da rivedere.|
|Aggiunta di documenti con correzione a un insieme da rivedere|AddRemediatedData|L'utente carica i documenti con errori di indicizzazione corretti in un insieme da rivedere.|
|Dati analizzati nell'insieme da rivedere|RunAlgo|L'utente ha eseguito analisi sui documenti in un insieme da rivedere.|
|Documento con annotazioni nell'insieme da rivedere|AnnotateDocument|L'utente ha annotato un documento in un insieme da rivedere. L'annotazione include la correzione del contenuto di un documento.|
|Set di carichi confrontati|LoadComparisonJob|L'utente ha confrontato due set di carichi diversi in insieme da rivedere. Un set di carichi si verifica quando i dati di una ricerca di contenuto associata al caso vengono aggiunti a un insieme da rivedere.|
|Documenti corretti convertiti in PDF|BurnJob|L'utente ha convertito in file PDF tutti i documenti corretti di un insieme da rivedere.|
|Creato insieme da rivedere|CreateWorkingSet|L'utente ha creato un insieme da rivedere.|
|Ricerca insieme da rivedere creata|CreateWorkingSetSearch|L'utente ha creato una query di ricerca che consente di cercare i documenti in un insieme da rivedere.|
|Creato tag|CreateTag|L'utente ha creato un gruppo di tag in un insieme da rivedere. Un gruppo di tag può contenere uno o più tag figlio. Questi tag vengono usati per contrassegnare i documenti nell'insieme da rivedere.|
|Ricerca insieme da rivedere eliminata|DeleteWorkingSetSearch|Un utente ha eliminato una query di ricerca in un insieme da rivedere.|
|Tag eliminato|DeleteTag|L'utente ha eliminato un tag o un gruppo di tag in un insieme da rivedere.|
|Documento scaricato|DownloadDocument|L'utente ha scaricato un documento da un insieme da rivedere.|
|Tag modificato|UpdateTag|L'utente ha modificato un tag in un insieme da rivedere.|
|Esportati documenti da un insieme da rivedere|ExportJob|L'utente ha esportato dei documenti da un insieme da rivedere.|
|Impostazione caso modificata|UpdateCaseSettings|L'utente ha modificato le impostazioni per un caso. Le impostazioni per il caso includono le informazioni sul caso, le autorizzazioni di accesso e le impostazioni che controllano il comportamento di ricerca e analisi.|
|Ricerca insieme da rivedere modificata|UpdateWorkingSetSearch|Un utente ha modificato una query di ricerca in un insieme da rivedere.|
|Visualizzazione dell'anteprima della ricerca dell'insieme da rivedere|PreviewWorkingSetSearch|Un utente ha visualizzato in anteprima i risultati di una query di ricerca in un insieme da rivedere.|
|Corretti i documenti con errori|ErrorRemediationJob|L'utente corregge i file che contengono errori di indicizzazione.|
|Documento con tag|TagFiles|L'utente contrassegna un documento in un insieme da rivedere.|
|Contrassegnati i risultati di una query|TagJob|Un utente contrassegna tutti i documenti che corrispondono ai criteri della query di ricerca in un insieme da rivedere.|
|Documento visualizzato nell'insieme da rivedere|ViewDocument|L'utente ha visualizzato un documento in un insieme da rivedere.|
|||

## <a name="ediscovery-cmdlet-activities"></a>Attività dei cmdlet di eDiscovery

Nella tabella seguente sono elencati i record del registro di controllo dei cmdlet registrati quando un amministratore o un utente esegue un'attività correlata a eDiscovery utilizzando il Centro conformità o eseguendo il cmdlet corrispondente in PowerShell del Centro sicurezza & conformità. Le informazioni dettagliate nel record del registro di controllo sono diverse per le attività dei cmdlet elencate in questa tabella e le attività di eDiscovery descritte nella sezione precedente.
  
Come indicato in precedenza, sono necessari fino a 24 ore prima che le attività dei cmdlet di eDiscovery vengano visualizzate nei risultati della ricerca nel log di controllo.
  
> [!TIP]
> I cmdlet nella colonna **Operation** nella tabella seguente sono collegati all'argomento corrispondente della Guida relativo ai cmdlet in TechNet. Passare all'argomento della Guida del cmdlet per una descrizione dei parametri disponibili per ogni cmdlet. Il parametro e il valore del parametro utilizzati con un cmdlet sono inclusi nella voce del registro di controllo per ogni attività del cmdlet di eDiscovery registrata. 
  
|**Nome descrittivo**|**Operation (cmdlet)**|**Descrizione**|
|:-----|:-----|:-----|
|Blocco creato nel caso di eDiscovery  <br/> |[New-CaseHoldPolicy](/powershell/module/exchange/new-caseholdpolicy) <br/> |È stata creata un'esenzione per un caso di eDiscovery. È possibile creare un'esenzione con o senza specificare un'origine di contenuto. Se vengono specificate origini di contenuto, verranno identificate nella voce del log di controllo.  <br/> |
|Blocco eliminato dal caso di eDiscovery  <br/> |[Remove-CaseHoldPolicy](/powershell/module/exchange/remove-caseholdpolicy) <br/> |Un'esenzione associata a un caso di eDiscovery è stata eliminata. L'eliminazione di un'esenzione rilascia tutti i percorsi di contenuto dall'esenzione. L'eliminazione del blocco comporta anche l'eliminazione delle regole di blocco del caso associate al blocco (vedere **Remove-CaseHoldRule** di seguito).  <br/> |
|Blocco modificato nel caso di eDiscovery  <br/> |[Set-CaseHoldPolicy](/powershell/module/exchange/set-caseholdpolicy) <br/> |Un'esenzione associata a eDiscovery è stata modificata. Le possibili modifiche includono l'aggiunta o la rimozione di percorsi di contenuto o la disattivazione (disabilitazione) del blocco.  <br/> |
|Query di ricerca creata per il blocco caso di eDiscovery  <br/> |[New-CaseHoldRule](/powershell/module/exchange/new-caseholdrule) <br/> |È stata creata un'esenzione basata su query associata a un caso di eDiscovery.  <br/> |
|Query di ricerca eliminata per il blocco caso di eDiscovery  <br/> |[Remove-CaseHoldRule](/powershell/module/exchange/remove-caseholdrule) <br/> |Un blocco basato su query associato a un caso di eDiscovery è stato eliminato. La rimozione della query dal blocco è spesso il risultato dell'eliminazione di un'esenzione. Quando viene eliminata un'esenzione o una query di blocco, vengono rilasciati i percorsi del contenuto in attesa.  <br/> |
|Query di ricerca modificata per il blocco caso di eDiscovery  <br/> |[Set-CaseHoldRule](/powershell/module/exchange/set-caseholdrule) <br/> |È stata modificata una conservazione basata su query associata a un caso di eDiscovery. Le possibili modifiche includono la modifica della query o dell'intervallo di date per un blocco basato su query.  <br/> |
|Caso di eDiscovery creato  <br/> |[New-ComplianceCase](/powershell/module/exchange/new-compliancecase) <br/> |È stato creato un caso di eDiscovery. Quando viene creato un caso, è necessario assegnargli solo un nome. Altre attività correlate al caso, ad esempio l'aggiunta di membri, la creazione di blocchi e la creazione di ricerche di contenuto associate al caso, comportano la registrazione di eventi aggiuntivi.  <br/> |
|Caso di eDiscovery eliminato  <br/> |[Remove-ComplianceCase](/powershell/module/exchange/remove-compliancecase) <br/> |Un caso di eDiscovery è stato eliminato. Per poter eliminare il caso, è necessario rimuovere qualsiasi blocco associato al caso.  <br/> |
|Caso di eDiscovery modificato  <br/> |[Set-ComplianceCase](/powershell/module/exchange/set-compliancecase) <br/> |Un caso di eDiscovery è stato modificato. Le modifiche includono la chiusura di un caso aperto o la riapertura di un caso chiuso.  <br/> |
|Membro aggiunto al caso di eDiscovery  <br/> |[Add-ComplianceCaseMember](/powershell/module/exchange/add-compliancecasemember) <br/> |Un utente è stato aggiunto come membro di un caso di eDiscovery. Come membro di un caso, un utente può eseguire diverse attività correlate al caso a seconda che gli siano state assegnate le autorizzazioni necessarie.  <br/> |
|Membro rimosso dal caso di eDiscovery  <br/> |[Remove-ComplianceCaseMember](/powershell/module/exchange/remove-compliancecasemember) <br/> |Un utente è stato rimosso come membro di un caso di eDiscovery.  <br/> |
|Appartenenza a un caso di eDiscovery modificato  <br/> |[Update-ComplianceCaseMember](/powershell/module/exchange/update-compliancecasemember) <br/> |L'elenco di appartenenze di un caso di eDiscovery è stato modificato. Questa attività viene registrata quando tutti i membri vengono sostituiti con un gruppo di nuovi utenti. Se viene aggiunto o rimosso un singolo membro, viene registrata l'operazione **Add-ComplianceCaseMember** **o Remove-ComplianceCaseMember.**  <br/> |
|Ricerca contenuto creata  <br/> |[New-ComplianceSearch](/powershell/module/exchange/new-compliancesearch) <br/> |È stata creata una nuova ricerca contenuto.  <br/> |
|Ricerca contenuto eliminata  <br/> |[Remove-ComplianceSearch](/powershell/module/exchange/remove-compliancesearch) <br/> |È stata eliminata una ricerca di contenuto esistente.  <br/> |
|Ricerca contenuto modificata  <br/> |[Set-ComplianceSearch](/powershell/module/exchange/set-compliancesearch) <br/> |È stata modificata una ricerca di contenuto esistente. Le modifiche possono includere l'aggiunta o la rimozione di percorsi di contenuto in cui viene eseguita la ricerca e la modifica della query di ricerca.  <br/> |
|Ricerca contenuto avviata  <br/> |[Start-ComplianceSearch](/powershell/module/exchange/start-compliancesearch) <br/> |È stata avviata una ricerca di contenuto. Quando si crea o si modifica una ricerca di contenuto utilizzando l'interfaccia utente grafica del Centro conformità, la ricerca viene avviata automaticamente. Se si crea o si modifica una ricerca utilizzando il cmdlet **New-ComplianceSearch** o **Set-ComplianceSearch,** è necessario eseguire il cmdlet **Start-ComplianceSearch** per avviare la ricerca.  <br/> |
|Ricerca contenuto interrotta  <br/> |[Stop-ComplianceSearch](/powershell/module/exchange/stop-compliancesearch) <br/> |Una ricerca di contenuto in esecuzione è stata interrotta.  <br/> |
|Azione di ricerca contenuto creata  <br/> |[New-ComplianceSearchAction](/powershell/module/exchange/new-compliancesearchaction) <br/> |È stata creata un'azione di ricerca contenuto. Le azioni di ricerca contenuto includono l'anteprima dei risultati della ricerca, l'esportazione dei risultati della ricerca, la preparazione dei risultati della ricerca per l'analisi in Advanced eDiscovery e l'eliminazione definitiva degli elementi che corrispondono ai criteri di ricerca di una ricerca di contenuto.  <br/> |
|Azione di ricerca contenuto eliminata  <br/> |[Remove-ComplianceSearchAction](/powershell/module/exchange/remove-compliancesearchaction) <br/> |Un'azione di ricerca contenuto è stata eliminata.  <br/> |
|Filtro autorizzazioni di ricerca creato  <br/> |[New-ComplianceSecurityFilter](/powershell/module/exchange/new-compliancesecurityfilter) <br/> |È stato creato un filtro delle autorizzazioni di ricerca.  <br/> |
|Filtro delle autorizzazioni di ricerca eliminate  <br/> |[Remove-ComplianceSecurityFilter](/powershell/module/exchange/remove-compliancesecurityfilter) <br/> |È stato eliminato un filtro delle autorizzazioni di ricerca.  <br/> |
|Filtro delle autorizzazioni di ricerca modificato  <br/> |[Set-ComplianceSecurityFilter](/powershell/module/exchange/set-compliancesecurityfilter) <br/> |È stato modificato un filtro delle autorizzazioni di ricerca.  <br/> |
|Amministratore di eDiscovery creato  <br/> |[Add-eDiscoveryCaseAdmin](/powershell/module/exchange/add-ediscoverycaseadmin) <br/> |Un utente è stato aggiunto come amministratore di eDiscovery nell'organizzazione.  <br/> |
|Amministratore di eDiscovery eliminato  <br/> |[Remove-eDiscoveryCaseAdmin](/powershell/module/exchange/remove-ediscoverycaseadmin) <br/> |Un amministratore di eDiscovery è stato eliminato dall'organizzazione.  <br/> |
|Appartenenza all'amministratore di eDiscovery modificata  <br/> |[Update-eDiscoveryCaseAdmin](/powershell/module/exchange/update-ediscoverycaseadmin) <br/> |L'elenco degli amministratori di eDiscovery nell'organizzazione è stato modificato. Questa attività viene registrata quando l'elenco degli amministratori di eDiscovery viene sostituito con un gruppo di nuovi utenti. Se viene aggiunto o rimosso un singolo utente, viene registrata l'operazione **Add-eDiscoveryCaseAdmin** **o Remove-eDiscoveryCaseAdmin.**  <br/> |

## <a name="detailed-properties-for-ediscovery-activities"></a>Proprietà dettagliate per le attività di eDiscovery

Nella tabella seguente vengono descritte le  proprietà incluse  quando si fa clic su Ulteriori informazioni nella pagina Dettagli per un'attività di eDiscovery elencata nei risultati della ricerca. Queste proprietà sono incluse anche nel file CSV quando si esportano i risultati della ricerca nel log di controllo. Un record del log di controllo per un'attività di eDiscovery non includerà tutte le proprietà dettagliate elencate di seguito.
  
> [!TIP]
> Quando si esportano i risultati della ricerca, il file CSV contiene una colonna denominata **Detail** che contiene le proprietà dettagliate descritte nella tabella seguente in una proprietà multivalore. È possibile utilizzare la funzionalità Power Query in Excel per dividere questa colonna in più colonne in modo che ogni proprietà abbia una propria colonna. In questo modo è possibile ordinare e filtrare in base a una o più di queste proprietà. Per ulteriori informazioni, vedere la sezione "Esportare i risultati della ricerca in un file" in [Search the audit log](search-the-audit-log-in-security-and-compliance.md#step-4-export-the-search-results-to-a-file). 
  
|**Proprietà**|**Descrizione**|
|:-----|:-----|
|Caso  <br/> |Identità (GUID) del caso di eDiscovery creato, modificato o eliminato.  <br/> |
|ClientApplication  <br/> |Le attività cmdlet di eDiscovery hanno un valore **di EMC** per questa proprietà. Ciò indica che l'attività è stata eseguita utilizzando l'interfaccia utente grafica del Centro conformità o eseguendo il cmdlet in PowerShell.  <br/> |
|ClientIP  <br/> |L'indirizzo IP del dispositivo utilizzato al momento della registrazione dell'attività. L'indirizzo IP viene visualizzato in formato IPv4 o IPv6.  <br/> |
|ClientRequestId  <br/> | Per le attività di eDiscovery, questa proprietà è in genere vuota.  <br/> |
|CmdletVersion  <br/> |Numero di build per la versione del Centro conformità in esecuzione nell'organizzazione.  <br/> |
|CreationTime  <br/> |Data e ora in formato UTC (Coordinated Universal Time) in cui è stata completata l'attività di eDiscovery.  <br/> |
|EffectiveOrganization  <br/> |Nome dell'organizzazione di Microsoft 365.  <br/> |
|ExchangeLocations  <br/> |Il Exchange Online cassette postali incluse in una ricerca di contenuto o in attesa in un caso di eDiscovery.  <br/> |
|Esclusioni  <br/> |Posizioni delle cassette postali o dei siti escluse da una ricerca di contenuto o da un blocco in un caso di eDiscovery.  <br/> |
|ExtendedProperties  <br/> |Proprietà aggiuntive di una ricerca di contenuto, di un'azione di ricerca del contenuto o di un blocco in un caso di eDiscovery, ad esempio il GUID dell'oggetto e i parametri cmdlet e cmdlet corrispondenti utilizzati durante l'esecuzione dell'attività.  <br/> |
|Id  <br/> |ID della voce di report. L'ID identifica in modo univoco la voce del registro di controllo.  <br/> |
|NonPIIParameters  <br/> |Elenco dei parametri (senza valori) utilizzati con il cmdlet identificato nella proprietà Operation. I parametri elencati in questa proprietà sono gli stessi elencati nella proprietà Parameters.  <br/> |
|ObjectId  <br/> |GUID o nome dell'oggetto, ad esempio una ricerca contenuto o un caso di eDiscovery, creato, modificato o eliminato dall'attività elencata nella proprietà Operation. Questo oggetto viene identificato anche nella colonna Item nei risultati della ricerca nel log di controllo.  <br/> |
|ObjectType  <br/> |Tipo di oggetto eDiscovery creato, eliminato o modificato dall'utente. ad esempio un'azione di ricerca del contenuto (anteprima, esportazione o eliminazione), un caso di eDiscovery o una ricerca di contenuto.  <br/> |
|Operazione  <br/> |Nome dell'operazione corrispondente all'attività di eDiscovery eseguita.  <br/> |
|OrganizationId  <br/> |GUID dell'organizzazione Microsoft 365 locale.  <br/> |
|Parametri  <br/> |Nome e valore dei parametri utilizzati con il cmdlet corrispondente.  <br/> |
|PublicFolderLocations  <br/> |I percorsi delle cartelle pubbliche Exchange Online inclusi in una ricerca di contenuto o messi in attesa in un caso di eDiscovery.  <br/> |
|Query  <br/> |Query di ricerca associata all'attività, ad esempio una ricerca di contenuto o un'esenzione basata su query.  <br/> |
|RecordType  <br/> |Tipo di operazione indicato dal record. Il valore **18** indica un evento correlato a un'attività elencata nella sezione [Attività cmdlet di eDiscovery.](#ediscovery-cmdlet-activities) Il valore **24** indica un evento correlato a un'attività elencata nella sezione Come cercare e visualizzare le attività [di eDiscovery.](#how-to-search-for-and-view-ediscovery-activities)  <br/> |
|ResultStatus  <br/> |Indica se l'azione specificata nella proprietà Operation ha avuto esito positivo o meno.  <br/> |
|SecurityComplianceCenterEventType  <br/> |Indica che l'attività era un evento del Centro conformità. Tutte le attività di eDiscovery avranno un valore pari a **0** per questa proprietà.  <br/> |
|SharepointLocations  <br/> |I SharePoint Online inclusi in una ricerca di contenuto o messi in attesa in un caso di eDiscovery.  <br/> |
|StartTime  <br/> |Data e ora in formato UTC (Coordinated Universal Time) in cui è stata avviata l'attività di eDiscovery.  <br/> |
|UserId  <br/> |Utente che ha eseguito l'attività (specificata nella proprietà Operation) che ha comportato la registrazione del record. I record per le attività di eDiscovery eseguite dagli account di sistema (ad esempio NT AUTHORITY\SYSTEM) sono inclusi anche nel registro di controllo.  <br/> |
|UserKey  <br/> |ID alternativo per l'utente identificato nella proprietà UserId. Per le attività di eDiscovery, il valore di questa proprietà è in genere lo stesso della proprietà UserId.  <br/> |
|UserServicePlan  <br/> |Sottoscrizione utilizzata dall'organizzazione. Per le attività di eDiscovery, questa proprietà è in genere vuota.  <br/> |
|UserType  <br/> |Tipo di utente che ha eseguito l'operazione. I valori seguenti indicano il tipo di utente.  <br/> 0 Un utente normale. 2 Un amministratore dell'organizzazione. 3 Un amministratore del datacenter Microsoft o un account di sistema del datacenter. 4 Un account di sistema. 5 Un'applicazione. 6 Un'entità servizio. |
|Version  <br/> |Indica il numero di versione dell'attività (identificata dalla proprietà Operation) registrata.  <br/> |
|Carico di lavoro  <br/> |Servizio in cui si è verificata l'attività. Per le attività di eDiscovery, il valore è **SecurityComplianceCenter.**  <br/> |
