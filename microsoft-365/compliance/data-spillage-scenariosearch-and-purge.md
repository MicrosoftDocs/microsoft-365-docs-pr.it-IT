---
title: scenario di fuoriuscita dei dati della serie Solution di eDiscovery-ricerca ed eliminazione
ms.author: markjjo
author: markjjo
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MET150
ms.assetid: d945f7dd-f62f-4ca7-b3e7-469824cfd493
description: Utilizzare Office 365 eDiscovery e gli strumenti di ricerca per gestire e rispondere a un evento di fuoriuscita dei dati nell'organizzazione.
ms.openlocfilehash: 06c02a9d5f31f8b7d6845214c10a150b6cacf379
ms.sourcegitcommit: 03a83ff76c8162b850c4c552759c49f2a4750574
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2020
ms.locfileid: "41558363"
---
# <a name="ediscovery-solution-series-data-spillage-scenario---search-and-purge"></a>serie di soluzioni di eDiscovery: scenario di fuoriuscita dei dati-ricerca ed eliminazione

 **Che cos'è il versamento dei dati e perché si dovrebbe interessare?** La fuoriuscita dei dati avviene quando un documento riservato viene rilasciato in un ambiente non attendibile. Quando viene rilevato un problema di fuoriuscita dei dati, è importante valutare rapidamente le dimensioni e le posizioni del versamento, esaminare le attività degli utenti che lo circondano e quindi eliminare definitivamente i dati versati dal sistema. 
  
## <a name="data-spillage-scenario"></a>Scenario di fuoriuscita dei dati

Si è un responsabile della sicurezza delle informazioni di primo livello presso contoso. Si è informati di una situazione di fuoriuscita dei dati in cui un dipendente ha condiviso inconsapevolmente un documento estremamente riservato con più persone tramite posta elettronica. Si desidera valutare rapidamente chi ha ricevuto il documento internamente ed esternamente. Una volta identificati, si desidera condividere i risultati dei casi con altri ricercatori per esaminare e quindi rimuovere definitivamente i dati da Office 365. Dopo aver completato l'analisi, si desidera generare un report con l'evidenza della rimozione definitiva e di altri dettagli del caso per qualsiasi riferimento futuro.
  
### <a name="scope-of-this-article"></a>Ambito di questo articolo

In questo documento viene fornito un elenco di istruzioni su come rimuovere definitivamente un messaggio da Office 365 in modo che non sia accessibile o ripristinabile. Per eliminare un messaggio e renderlo ripristinabile fino alla scadenza del periodo di conservazione degli elementi eliminati, vedere [cercare ed eliminare i messaggi di posta elettronica nell'organizzazione di Office 365](search-for-and-delete-messages-in-your-organization.md).
  
## <a name="workflow-for-managing-data-spillage-incidents"></a>Flusso di lavoro per la gestione degli incidenti di perdita dei dati

Ecco come gestire un problema di fuoriuscita dei dati:

![Il flusso di lavoro in 8 passaggi per la gestione degli incidenti di fuoriuscita dei dati](media/O365-eDiscoverySolutions-DataSpillage-workflow.png)
  
[Optional Passaggio 1: gestire gli utenti autorizzati a accedere al caso e impostare i limiti di conformità](#optional-step-1-manage-who-can-access-the-case-and-set-compliance-boundaries)<br/>
[Passaggio 2: creare un caso di eDiscovery](#step-2-create-an-ediscovery-case)<br/>
[Passaggio 3: ricerca dei dati versati](#step-3-search-for-the-spilled-data)<br/>
[Passaggio 4: esaminare e convalidare i risultati del caso](#step-4-review-and-validate-case-findings)<br/>
[Passaggio 5: utilizzare il registro di traccia dei messaggi per verificare la condivisione di dati versati](#step-5-use-message-trace-log-to-check-how-spilled-data-was-shared)<br/>
[Passaggio 6: preparare le cassette postali](#step-6-prepare-the-mailboxes)<br/>
[Passaggio 7: eliminare definitivamente i dati versati](#step-7-permanently-delete-the-spilled-data)<br/>
[Passaggio 8: verificare, fornire una prova di eliminazione e controllo](#step-8-verify-provide-a-proof-of-deletion-and-audit)<br/>

## <a name="things-to-know-before-you-start"></a>Elementi da sapere prima di iniziare

- Quando una cassetta postale è in attesa, un messaggio eliminato rimane nella cartella elementi ripristinabili fino alla scadenza del periodo di conservazione o al rilascio del blocco. Il [passaggio 6](#step-6-prepare-the-mailboxes) descrive come rimuovere il blocco dalle cassette postali. Prima di rimuovere il blocco, consultare la gestione dei record o i reparti legali. È possibile che l'organizzazione disponga di un criterio che definisce se una cassetta postale in attesa o un evento di perdita dei dati ha la priorità. 
    
- Per controllare le cassette postali degli utenti che un ricercatore di perdita di dati può cercare e gestire gli utenti autorizzati ad accedere al caso, è possibile configurare i limiti di conformità e creare un gruppo di ruoli personalizzato, descritto nel [passaggio 1](#optional-step-1-manage-who-can-access-the-case-and-set-compliance-boundaries). A tale scopo, è necessario essere membri del gruppo di ruoli Gestione organizzazione o assegnare il ruolo di gestione dei ruoli. Se nell'organizzazione o nell'amministratore sono già stati configurati limiti di conformità, è possibile ignorare il passaggio 1.
    
- Per creare un caso, è necessario essere membri del gruppo di ruoli di eDiscovery Manager o essere membri di un gruppo di ruoli personalizzato assegnato al ruolo di gestione dei casi. Se non si è membri, chiedere a un amministratore di Office 365 di [aggiungersi al gruppo di ruoli eDiscovery Manager](assign-ediscovery-permissions.md).
    
- Per creare ed eseguire una ricerca di contenuto, è necessario essere un membro del gruppo di ruoli di gestione di eDiscovery o disporre del ruolo di gestione della ricerca di conformità. Per eliminare i messaggi, è necessario essere un membro del gruppo di ruoli Gestione organizzazione o disporre del ruolo di gestione di ricerca ed eliminazione. Per informazioni su come aggiungere gli utenti a un gruppo di ruoli, vedere [Assegnare autorizzazioni di eDiscovery nel Centro sicurezza e conformità](https://docs.microsoft.com/microsoft-365/compliance/assign-ediscovery-permissions).
    
- Per eseguire una ricerca nelle attività di eDiscovery del registro di controllo di Office 365 nel passaggio 8, è necessario che il controllo sia attivato per l'organizzazione. È possibile cercare le attività eseguite negli ultimi 90 giorni. Per ulteriori informazioni su come abilitare e utilizzare il controllo, vedere la sezione [controllo del processo di analisi del versamento dei dati](#auditing-the-data-spillage-investigation-process) nel passaggio 8. 
    
## <a name="optional-step-1-manage-who-can-access-the-case-and-set-compliance-boundaries"></a>Optional Passaggio 1: gestire gli utenti autorizzati a accedere al caso e impostare i limiti di conformità

A seconda della prassi organizzativa, è necessario controllare chi può accedere al caso di eDiscovery utilizzato per analizzare un problema di fuoriuscita dei dati e impostare i limiti di conformità. Il modo più semplice per eseguire questa operazione consiste nell'aggiungere ricercatori come membri di un gruppo di ruoli esistente nel centro sicurezza & compliance e quindi aggiungere il gruppo di ruolo come membro del caso eDiscovery. Per informazioni sui gruppi di ruoli incorporati di eDiscovery e su come aggiungere membri a un caso di eDiscovery, vedere [assign eDiscovery Permissions](assign-ediscovery-permissions.md).
  
È inoltre possibile creare un nuovo gruppo di ruoli che sia allineato con le esigenze dell'organizzazione. Ad esempio, potrebbe essere necessario che un gruppo di investigatori per il versamento dei dati nell'organizzazione acceda e collabori su tutti i casi di perdita dei dati. A tale scopo, è possibile creare un gruppo di ruoli "investigatore per la fuoriuscita dei dati", assegnando i ruoli corretti (esportazione, decrittografia RMS, revisione, anteprima, ricerca di conformità e gestione dei casi), aggiungendo gli investigatori di versamento dei dati al gruppo di ruoli e quindi aggiungendo la gruppo di ruolo come membro del caso di eDiscovery di perdita dei dati. Per istruzioni dettagliate su come eseguire questa operazione, vedere [configurare i limiti di conformità per le indagini di eDiscovery in Office 365](tagging-and-assessment-in-advanced-ediscovery.md) . 
  
## <a name="step-2-create-an-ediscovery-case"></a>Passaggio 2: creare un caso di eDiscovery

Un caso di eDiscovery rappresenta un modo efficace per gestire l'analisi del versamento dei dati. È possibile aggiungere membri al gruppo di ruoli creato nel passaggio 1, aggiungere il gruppo di ruoli come membro di un nuovo caso di eDiscovery, eseguire ricerche iterative per individuare i dati rovesciati, esportare un report in condivisione, monitorare lo stato del caso e quindi fare riferimento ai dettagli del c. ASE, se necessario. Valutare la possibilità di stabilire una convenzione di denominazione per i casi di eDiscovery utilizzati per gli incidenti relativi alla fuoriuscita dei dati e fornire quante più informazioni possibile nel caso di nome e descrizione, in modo da poter individuare e fare riferimento in futuro, se necessario.
  
Per creare un nuovo caso, è possibile utilizzare eDiscovery nel centro sicurezza e conformità. Vedere "creare un nuovo caso" in [casi di eDiscovery](ediscovery-cases.md#step-2-create-a-new-case).
  
## <a name="step-3-search-for-the-spilled-data"></a>Passaggio 3: ricerca dei dati versati

Dopo aver creato un caso e l'accesso gestito, è possibile utilizzare il caso per cercare in modo iterativo i dati riversati e identificare le cassette postali che contengono i dati versati. Si utilizzerà la stessa query di ricerca utilizzata per trovare i messaggi di posta elettronica per eliminare gli stessi messaggi nel [passaggio 7](#step-7-permanently-delete-the-spilled-data).
  
Per creare una ricerca di contenuto associata a un caso di eDiscovery, vedere la sezione relativa alla creazione e all'esecuzione di una ricerca di contenuto associata a un caso in [eDiscovery](ediscovery-cases.md#step-5-create-and-run-a-content-search-associated-with-a-case)case.
  
 **Importante:** Le parole chiave utilizzate nella query di ricerca possono contenere i dati di cui è stata eseguita la ricerca. Ad esempio, se si cercano documenti contenenti un numero di previdenza sociale e si utilizza la parola chiave it As Search, è necessario eliminare la query in seguito per evitare ulteriori fuoriuscite. Per ulteriori informazioni, vedere [eliminazione della query di ricerca](#deleting-the-search-query) nel passaggio 8. 
  
## <a name="step-4-review-and-validate-case-findings"></a>Passaggio 4: esaminare e convalidare i risultati del caso

Dopo aver creato una ricerca di contenuto, è necessario esaminare e convalidare i risultati della ricerca e verificare che siano costituiti solo dai messaggi di posta elettronica che devono essere eliminati. In una ricerca di contenuto, è possibile visualizzare in anteprima un campionamento casuale di 1.000 messaggi di posta elettronica senza esportare i risultati della ricerca per evitare un ulteriore versamento dei dati. Per ulteriori informazioni sulle limitazioni relative all'anteprima, vedere [limits for content search](limits-for-content-search.md).
  
Se si dispone di più di 1.000 cassette postali o più di 100 messaggi di posta elettronica per cassetta postale da esaminare, è possibile suddividere la ricerca iniziale in più ricerche utilizzando parole chiave aggiuntive o condizioni quali l'intervallo di date o il mittente/destinatario ed esaminare i risultati di ogni ricerca singolarmente. Assicurarsi di prendere nota di tutte le query di ricerca da utilizzare quando si eliminano i messaggi nel [passaggio 7](#step-7-permanently-delete-the-spilled-data).

Se a un custode o a un utente finale viene assegnata una licenza di Office 365 E5, è possibile esaminare fino a 10.000 risultati della ricerca in una sola volta utilizzando Office 365 Advanced eDiscovery. Se sono presenti più di 10.000 messaggi di posta elettronica da rivedere, è possibile dividere la query di ricerca per intervallo di date ed esaminare ogni risultato singolarmente, in base alla quale i risultati della ricerca vengono ordinati per data. In Advanced eDiscovery, è possibile contrassegnare i risultati della ricerca utilizzando l' **etichetta come** caratteristica nel pannello anteprima e filtrare il risultato della ricerca in base al tag etichettato. Questa operazione è utile quando si collabora con un revisore secondario. Utilizzando strumenti di analisi aggiuntivi in Advanced eDiscovery, ad esempio il riconoscimento ottico dei caratteri, il threading della posta elettronica e la codifica predittiva, è possibile elaborare e rivedere rapidamente migliaia di messaggi e contrassegnarli per ulteriori riesami. Vedere [la pagina relativa alla configurazione rapida di Office 365 Advanced eDiscovery](quick-setup-for-advanced-ediscovery.md).

Quando si trova un messaggio di posta elettronica contenente dati versati, controllare i destinatari del messaggio per determinare se è stato condiviso esternamente. Per tracciare ulteriormente un messaggio, è possibile raccogliere le informazioni del mittente e l'intervallo di date in modo che sia possibile utilizzare i registri di traccia dei messaggi, come descritto nel [passaggio 5](#step-5-use-message-trace-log-to-check-how-spilled-data-was-shared).

Afer sono stati verificati i risultati della ricerca, è possibile che si desideri condividere i risultati con altri utenti per una revisione secondaria. Gli utenti a cui è stato assegnato il caso nel passaggio 1 possono esaminare il contenuto del caso sia in eDiscovery che in Advanced eDiscovery e approvare i risultati del caso. È inoltre possibile generare un report senza esportare il contenuto effettivo. È inoltre possibile utilizzare lo stesso rapporto come prova dell'eliminazione, descritta nel [passaggio 8](#step-8-verify-provide-a-proof-of-deletion-and-audit).
  
 **Per generare un report statistico:**
  
1. Passare alla pagina di **ricerca** nel caso di eDiscovery e fare clic sulla ricerca per la quale si desidera generare un report. 
    
2. Nella pagina riquadro a comparsa, fare clic su **altro > rapporto di esportazione**.
 
      Viene visualizzata la pagina del rapporto di esportazione.

    ![Selezionare la ricerca e quindi fare clic su altro > rapporto di esportazione nella pagina a comparsa](media/O365-eDiscoverySolutions-DataSpillage-ExportReport1.png)
    
3. Selezionare **tutti gli elementi, inclusi quelli con formato non riconosciuto, crittografati oppure non indicizzati per altri motivi** e quindi fare clic su **genera report**.

4. Nel caso di eDiscovery, fare clic su **Esporta** per visualizzare l'elenco dei processi di esportazione. Potrebbe essere necessario fare clic su **Aggiorna** per aggiornare l'elenco in modo da visualizzare il processo di esportazione appena creato.

5. Fare clic sul processo di esportazione e quindi fare clic su **Scarica** report nella pagina a comparsa.
 
    ![Nella pagina Esporta, fare clic sull'esportazione e quindi su "download report"](media/O365-eDiscoverySolutions-DataSpillage-ExportReport2.png)

Il rapporto **riepilogativo di esportazione** contiene il numero di posizioni trovate con i risultati e le dimensioni dei risultati della ricerca. È possibile utilizzare questo parametro per confrontare il report generato dopo l'eliminazione e fornire la prova dell'eliminazione. Il rapporto sui **risultati** contiene un riepilogo più dettagliato dei risultati di ricerca, inclusi l'oggetto, il mittente, i destinatari, se la posta elettronica è stata letta, le date e le dimensioni di ogni messaggio. Se uno dei dettagli in questo report contiene i dati di versamento effettivi, assicurarsi di eliminare definitivamente il file results. csv al termine dell'indagine.

Per ulteriori informazioni sull'esportazione di report, vedere [Export a content search report](export-a-content-search-report.md).
    
## <a name="step-5-use-message-trace-log-to-check-how-spilled-data-was-shared"></a>Passaggio 5: utilizzare il registro di traccia dei messaggi per verificare la condivisione di dati versati

Per ulteriori informazioni sull'eventuale condivisione di messaggi di posta elettronica con i dati riversati, è possibile eseguire una query sui registri di traccia dei messaggi con il mittente e le informazioni sull'intervallo di date raccolte nel passaggio 4. Si noti che il periodo di conservazione per la traccia dei messaggi è di 30 giorni per i dati in tempo reale e di 90 giorni per i dati cronologici.
  
È possibile utilizzare la traccia dei messaggi nel centro sicurezza e conformità o utilizzare i cmdlet corrispondenti in PowerShell di Exchange Online. È importante tenere presente che l'analisi dei messaggi non offre garanzie complete sulla completezza di dati restituiti. Per ulteriori informazioni sull'utilizzo della traccia dei messaggi, vedere: 
  
- [Traccia dei messaggi nel Centro sicurezza e conformità](https://support.office.com/article/3e64f99d-ac33-4aba-91c5-9cb4ca476803.aspx)
    
- [Nuova traccia dei messaggi nel centro sicurezza & conformità](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/)
    
## <a name="step-6-prepare-the-mailboxes"></a>Passaggio 6: preparare le cassette postali

Dopo aver esaminato e convalidato che i risultati della ricerca contengono solo i messaggi che devono essere eliminati, è necessario raccogliere un elenco degli indirizzi di posta elettronica delle cassette postali interessate da utilizzare nel passaggio 7 quando si eliminano i dati rovesciati. Potrebbe anche essere necessario preparare le cassette postali prima di poter eliminare definitivamente i messaggi di posta elettronica a seconda che il ripristino di un singolo elemento sia abilitato nelle cassette postali che contengono i dati riversati o se una di queste cassette postali è in attesa.
  
### <a name="get-a-list-of-addresses-of-mailboxes-with-spilled-data"></a>Ottenere un elenco di indirizzi delle cassette postali con dati rovesciati

Sono disponibili due modi per raccogliere un elenco di indirizzi di posta elettronica delle cassette postali con dati rovesciati.

**Opzione 1: ottenere un elenco di indirizzi delle cassette postali con dati rovesciati**

1. Aprire il caso eDiscovery, passare alla pagina di **ricerca** e selezionare la ricerca di contenuto appropriata. 
    
2. Nella pagina riquadro a comparsa fare clic su **Visualizza risultati**.
    
3. Nell'elenco a discesa **Singoli risultati** fare clic su **Statistiche ricerca**.
    
4. Nell'elenco a discesa **tipo** fare clic su **posizioni principali**.
    
    ![Ottenere un elenco delle cassette postali che contengono i risultati della ricerca nella pagina posizioni principali nelle statistiche di ricerca](media/O365-eDiscoverySolutions-DataSpillage-TopLocations.png)

    Viene visualizzato un elenco delle cassette postali che contengono i risultati della ricerca. Viene visualizzato anche il numero di elementi di ogni cassetta postale che corrispondono alla query di ricerca.
    
5. Copiare le informazioni nell'elenco e salvarle in un file oppure fare clic su **download** per scaricare le informazioni in un file CSV. 
    
**Opzione 2: ottenere percorsi delle cassette postali dal rapporto di esportazione**

Aprire il rapporto di riepilogo di esportazione scaricato nel [passaggio 4](#step-4-review-and-validate-case-findings). Nella prima colonna del report, l'indirizzo di posta elettronica di ogni cassetta postale è elencato in **posizioni**.
  
### <a name="prepare-the-mailboxes-so-you-can-delete-the-spilled-data"></a>Preparare le cassette postali in modo da poter eliminare i dati versati

Se il ripristino di un singolo elemento è abilitato o se una cassetta postale è in attesa, verrà mantenuto un messaggio eliminato definitivamente (eliminato) nella cartella elementi ripristinabili. Pertanto, prima di poter eliminare i dati versati, è necessario controllare le configurazioni delle cassette postali esistenti e disabilitare il ripristino di un singolo elemento e rimuovere qualsiasi blocco o criterio di conservazione di Office 365. Tenere presente che è possibile preparare una cassetta postale alla volta, quindi eseguire lo stesso comando in cassette postali diverse o creare uno script di PowerShell per preparare più cassette postali contemporaneamente.

- Vedere "passaggio 1: raccogliere informazioni sulla cassetta postale" in [eliminare gli elementi nella cartella elementi ripristinabili delle cassette postali basate sul cloud in attesa](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-1-collect-information-about-the-mailbox) per istruzioni su come verificare se il ripristino di un singolo elemento è abilitato o se la cassetta postale è stata inserita o è stata assegnata a un criterio di conservazione. 
    
- Vedere "passaggio 2: preparare la cassetta postale" in [eliminare gli elementi nella cartella elementi ripristinabili delle cassette postali basate sul cloud in attesa](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-2-prepare-the-mailbox) per istruzioni sulla disabilitazione del ripristino di un singolo elemento. 
    
- Vedere "passaggio 3: rimuovere tutte le esenzioni dalla cassetta postale" in [eliminare gli elementi nella cartella elementi ripristinabili delle cassette postali basate sul cloud in attesa](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-3-remove-all-holds-from-the-mailbox) per istruzioni su come rimuovere un blocco o un criterio di conservazione da una cassetta postale. 

- Vedere "passaggio 4: rimuovere il ritardo dalla cassetta postale" in [eliminare gli elementi nella cartella elementi ripristinabili delle cassette postali basate sul cloud in attesa](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-4-remove-the-delay-hold-from-the-mailbox) per istruzioni sulla rimozione del blocco di ritardo che viene inserito nella cassetta postale dopo la rimozione di qualsiasi tipo di blocco.
    
 **Importante:** Consultare la gestione dei record o i reparti giuridici prima di rimuovere un blocco o un criterio di conservazione. È possibile che l'organizzazione disponga di un criterio che definisce se una cassetta postale in attesa o un problema di fuoriuscita dei dati è prioritaria. 
  
Assicurarsi di ripristinare le configurazioni precedenti della cassetta postale dopo aver verificato che i dati versati siano stati eliminati definitivamente. Per informazioni dettagliate, vedere il [passaggio 7](#step-7-permanently-delete-the-spilled-data).

## <a name="step-7-permanently-delete-the-spilled-data"></a>Passaggio 7: eliminare definitivamente i dati versati

Utilizzando i percorsi delle cassette postali raccolte e preparate nel passaggio 6 e la query di ricerca creata e affinata nel passaggio 3 per trovare i messaggi di posta elettronica che contengono i dati rovesciati, è ora possibile eliminare definitivamente i dati versati.  Come spiegato in precedenza, per eliminare i messaggi, è necessario essere membri del gruppo di ruoli Gestione organizzazione o assegnare il ruolo di gestione di ricerca ed eliminazione. Per informazioni su come aggiungere gli utenti a un gruppo di ruoli, vedere [Assegnare autorizzazioni di eDiscovery nel Centro sicurezza e conformità](https://docs.microsoft.com/microsoft-365/compliance/assign-ediscovery-permissions).

Per eliminare i messaggi versati, vedere i passaggi 2 & 3 per [cercare ed eliminare i messaggi di posta elettronica](https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization)
  
## <a name="step-8-verify-provide-a-proof-of-deletion-and-audit"></a>Passaggio 8: verificare, fornire una prova di eliminazione e controllo

Il passaggio finale del flusso di lavoro per gestire un problema di fuoriuscita dei dati consiste nel verificare che i dati versati siano stati rimossi definitivamente dalla cassetta postale accedendo al caso eDiscovery e rieseguendo la stessa query di ricerca utilizzata per eliminare i dati per verificare che non siano presenti risultati e restituito. Dopo aver verificato che i dati versati siano stati rimossi definitivamente, è possibile esportare un report e includerlo (insieme al rapporto originale) come prova dell'eliminazione. È quindi possibile [chiudere il caso](ediscovery-cases.md#optional-step-9-close-a-case), che consentirà di riaprirlo se si è in futuro riferirlo. Inoltre, è anche possibile ripristinare lo stato precedente delle cassette postali, eliminare la query di ricerca utilizzata per individuare i dati rovesciati e cercare i record di controllo delle attività eseguite durante la gestione dell'evento di fuoriuscita dei dati. 
  
### <a name="reverting-the-mailboxes-to-their-previous-state"></a>Ripristinare lo stato precedente delle cassette postali

Se nel passaggio 6 è stata modificata la configurazione delle cassette postali per preparare le cassette postali prima che i dati siano stati eliminati, sarà necessario ripristinarli allo stato precedente. Vedere "passaggio 6: ripristinare lo stato precedente della cassetta postale" in [eliminare gli elementi nella cartella elementi ripristinabili delle cassette postali basate sul cloud in attesa](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-6-revert-the-mailbox-to-its-previous-state).
  
### <a name="deleting-the-search-query"></a>Eliminazione della query di ricerca

Se le parole chiave della query di ricerca creata e utilizzata nel passaggio 3 contengono alcuni tra tutti i dati effettivamente eliminati, è necessario eliminare la query di ricerca per impedire l'ulteriore fuoriuscita dei dati.
  
1. Nel centro sicurezza e conformità, aprire il caso eDiscovery, passare alla pagina di **ricerca** e selezionare la ricerca di contenuto appropriata.
    
2. Nella pagina a comparsa fare clic su **Elimina**.

    ![Selezionare la ricerca e quindi fare clic su Elimina nella pagina riquadro a comparsa](media/O365-eDiscoverySolutions-DataSpillage-DeleteSearch.png)
    
### <a name="auditing-the-data-spillage-investigation-process"></a>Controllo del processo di analisi della fuoriuscita dei dati

È possibile eseguire una ricerca nel registro di controllo di Office 365 per le attività di eDiscovery eseguite durante l'indagine. È inoltre possibile eseguire una ricerca nel registro di controllo per restituire i record di controllo per il comando **New-ComplianceSearchAction-Purge** eseguito nel passaggio 7 per eliminare i dati riversati. Per altre informazioni, vedere:

- [Eseguire ricerche nel log di controllo](search-the-audit-log-in-security-and-compliance.md)

- [Cercare le attività di eDiscovery nel log di controllo](search-for-ediscovery-activities-in-the-audit-log.md)
  
