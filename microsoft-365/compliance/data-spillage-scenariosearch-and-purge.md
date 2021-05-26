---
title: Serie di soluzioni eDiscovery Scenario di fuoriuscita di dati - Ricerca ed eliminazione
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MET150
ms.assetid: d945f7dd-f62f-4ca7-b3e7-469824cfd493
description: Utilizzare eDiscovery e gli strumenti di ricerca per gestire e rispondere a un incidente di fuoriuscita di dati nell'organizzazione.
ms.openlocfilehash: 4305dbdb2fb59e4275852c88f8b74f6c4128a5cb
ms.sourcegitcommit: 727a75b604d5ff5946a0854662ad5a8b049f2874
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2021
ms.locfileid: "52653524"
---
# <a name="ediscovery-solution-series-data-spillage-scenario---search-and-purge"></a>Serie di soluzioni eDiscovery: scenario di fuoriuscita di dati - Ricerca ed eliminazione

 **Che cos'è la fuoriuscita di dati e perché è importante?** La perdita di dati si verifica quando un documento riservato viene rilasciato in un ambiente non attendibile. Quando viene rilevato un incidente di fuoriuscita di dati, è importante valutare rapidamente le dimensioni e le posizioni della fuoriuscita, esaminare le attività degli utenti intorno a esso e quindi eliminare definitivamente i dati versati dal sistema. 
  
## <a name="data-spillage-scenario"></a>Scenario di fuoriuscita di dati

Si è un responsabile della sicurezza delle informazioni presso Contoso. Si è informati di una situazione di fuoriuscita di dati in cui un dipendente ha condiviso inconsapevolmente un documento estremamente riservato con più persone tramite posta elettronica. Si desidera valutare rapidamente chi ha ricevuto questo documento internamente ed esternamente. Una volta identificato, si desidera condividere i risultati del caso con altri investigatori per esaminare e quindi rimuovere definitivamente i dati da Office 365. Al termine dell'indagine, si desidera generare un report con la prova della rimozione definitiva e altri dettagli del caso per qualsiasi riferimento futuro.
  
### <a name="scope-of-this-article"></a>Ambito di questo articolo

In questo documento viene fornito un elenco di istruzioni su come rimuovere definitivamente un messaggio da Microsoft 365 in modo che non sia accessibile o ripristinabile. Per eliminare un messaggio e renderlo ripristinabile fino alla scadenza del periodo di conservazione degli elementi eliminati, vedere [Search for and delete email messages in your organization](search-for-and-delete-messages-in-your-organization.md).
  
## <a name="workflow-for-managing-data-spillage-incidents"></a>Flusso di lavoro per la gestione degli incidenti di fuoriuscita di dati

Ecco come gestire un evento imprevisto di fuoriuscita di dati:

![Flusso di lavoro in 8 passaggi per la gestione degli incidenti di fuoriuscita di dati](../media/O365-eDiscoverySolutions-DataSpillage-workflow.png)
  
[(Facoltativo) Passaggio 1: gestire chi può accedere al caso e impostare i limiti di conformità](#optional-step-1-manage-who-can-access-the-case-and-set-compliance-boundaries)<br/>
[Passaggio 2: Creare un caso di eDiscovery](#step-2-create-an-ediscovery-case)<br/>
[Passaggio 3: cercare i dati sversati](#step-3-search-for-the-spilled-data)<br/>
[Passaggio 4: Esaminare e convalidare i risultati dei casi](#step-4-review-and-validate-case-findings)<br/>
[Passaggio 5: Utilizzare il registro di traccia dei messaggi per verificare la modalità di condivisione dei dati riversati](#step-5-use-message-trace-log-to-check-how-spilled-data-was-shared)<br/>
[Passaggio 6: Preparare le cassette postali](#step-6-prepare-the-mailboxes)<br/>
[Passaggio 7: Eliminare definitivamente i dati sversati](#step-7-permanently-delete-the-spilled-data)<br/>
[Passaggio 8: verificare, fornire una prova di eliminazione e controllare](#step-8-verify-provide-a-proof-of-deletion-and-audit)<br/>

## <a name="things-to-know-before-you-start"></a>Informazioni da conoscere prima di iniziare

- Quando una cassetta postale è in attesa, un messaggio eliminato rimane nella cartella Elementi ripristinabili fino alla scadenza del periodo di conservazione o al rilascio del blocco. [Il passaggio 6](#step-6-prepare-the-mailboxes) descrive come rimuovere il blocco dalle cassette postali. Prima di rimuovere il blocco, rivolgersi alla gestione dei record o ai reparti legali. L'organizzazione potrebbe avere un criterio che definisce se una cassetta postale in attesa o un evento imprevisto di perdita dei dati ha la priorità. 
    
- Per controllare quali cassette postali degli utenti un investigatore per la fuoriuscita di dati può cercare e gestire chi può accedere al caso, è possibile impostare i limiti di conformità e creare un gruppo di ruoli personalizzato, descritto nel [passaggio 1.](#optional-step-1-manage-who-can-access-the-case-and-set-compliance-boundaries) A tale scopo, è necessario essere membri del gruppo di ruoli Gestione organizzazione o essere assegnati al ruolo di gestione dei ruoli. Se l'utente o l'amministratore dell'organizzazione ha già impostato limiti di conformità, è possibile ignorare il passaggio 1.
    
- Per creare un caso, è necessario essere membri del gruppo di ruoli Manager eDiscovery o essere membri di un gruppo di ruoli personalizzato a cui è assegnato il ruolo Gestione casi. If you're not a member, ask a Microsoft 365 administrator to [add you to the eDiscovery manager role group](assign-ediscovery-permissions.md).
    
- Per creare ed eseguire una ricerca di contenuto, è necessario essere un membro del gruppo di ruoli di gestione di eDiscovery o disporre del ruolo di gestione della ricerca di conformità. Per eliminare i messaggi, è necessario essere un membro del gruppo di ruoli Gestione organizzazione o disporre del ruolo di gestione di ricerca ed eliminazione. Per informazioni su come aggiungere gli utenti a un gruppo di ruoli, vedere [Assegnare autorizzazioni di eDiscovery nel Centro sicurezza e conformità](./assign-ediscovery-permissions.md).
    
- Per eseguire ricerche nelle attività di eDiscovery del log di controllo nel passaggio 8, è necessario che il controllo sia attivato per l'organizzazione. È possibile cercare le attività eseguite negli ultimi 90 giorni. Per ulteriori informazioni su come abilitare e usare il controllo, vedere la sezione Controllo [del](#auditing-the-data-spillage-investigation-process) processo di indagine sulla fuoriuscita di dati nel passaggio 8. 
    
## <a name="optional-step-1-manage-who-can-access-the-case-and-set-compliance-boundaries"></a>(Facoltativo) Passaggio 1: gestire chi può accedere al caso e impostare i limiti di conformità

A seconda della pratica dell'organizzazione, è necessario controllare chi può accedere al caso di eDiscovery utilizzato per analizzare un evento imprevisto di sversamento dei dati e impostare i limiti di conformità. Il modo più semplice per eseguire questa operazione è aggiungere gli investigatori come membri di un gruppo di ruoli esistente nel Centro sicurezza & Conformità e quindi aggiungere il gruppo di ruoli come membro del caso di eDiscovery. Per informazioni sui gruppi di ruoli eDiscovery incorporati e su come aggiungere membri a un caso di eDiscovery, vedere [Assign eDiscovery permissions](assign-ediscovery-permissions.md).
  
È inoltre possibile creare un nuovo gruppo di ruoli in linea con le esigenze dell'organizzazione. Ad esempio, è possibile che un gruppo di investigatori della fuoriuscita di dati nell'organizzazione possa accedere e collaborare a tutti i casi di fuoriuscita di dati. A tale scopo, è possibile creare un gruppo di ruoli "Investigatore perdita dati", assegnare i ruoli appropriati (Export, RMS Decrypt, Review, Preview, Compliance Search e Case Management), aggiungere gli investigatori per la fuoriuscita di dati al gruppo di ruoli e quindi aggiungere il gruppo di ruoli come membro del caso di eDiscovery per la fuoriuscita di dati. Per istruzioni dettagliate su come eseguire questa operazione, vedere [Set up compliance boundaries for eDiscovery investigations in Office 365.](tagging-and-assessment-in-advanced-ediscovery.md) 
  
## <a name="step-2-create-an-ediscovery-case"></a>Passaggio 2: Creare un caso di eDiscovery

Un caso di eDiscovery rappresenta un modo efficace per gestire l'indagine sulla fuoriuscita di dati. È possibile aggiungere membri al gruppo di ruoli creato nel passaggio 1, aggiungere il gruppo di ruoli come membro di un nuovo caso di eDiscovery, eseguire ricerche iterative per trovare i dati fuoriusciti, esportare un report da condividere, tenere traccia dello stato del caso e quindi fare riferimento ai dettagli del caso, se necessario. Prendere in considerazione la possibilità di stabilire una convenzione di denominazione per i casi di eDiscovery utilizzati per gli incidenti di fuoriuscita di dati e fornire il maggior numero di informazioni possibile nel nome e nella descrizione del caso in modo da poter individuare e fare riferimento in futuro, se necessario.
  
Per creare un nuovo caso, è possibile utilizzare eDiscovery nel Centro sicurezza e conformità. Vedere "Creare un nuovo caso" in [Introduzione a Core eDiscovery.](get-started-core-ediscovery.md#step-3-create-a-core-ediscovery-case)
  
## <a name="step-3-search-for-the-spilled-data"></a>Passaggio 3: cercare i dati sversati

Dopo aver creato un caso e l'accesso gestito, è possibile utilizzare il caso per cercare in modo iterativo i dati riversati e identificare le cassette postali che contengono i dati versati. Verrà utilizzata la stessa query di ricerca utilizzata per trovare i messaggi di posta elettronica per eliminare gli stessi messaggi [nel passaggio 7.](#step-7-permanently-delete-the-spilled-data)
  
Per creare una ricerca di contenuto associata a un caso di eDiscovery, vedere [Search for content in a Core eDiscovery case.](search-for-content-in-core-ediscovery.md)
  
> [!IMPORTANT]
> Le parole chiave utilizzate nella query di ricerca possono contenere i dati effettivamente fuoriusciti che si stanno cercando. Ad esempio, se si cercano documenti contenenti un numero di previdenza sociale e si utilizza la parola chiave it come parola chiave di ricerca, è necessario eliminare la query in seguito per evitare ulteriori perdite. Vedere [Eliminazione della query di ricerca](#deleting-the-search-query) nel passaggio 8.
  
## <a name="step-4-review-and-validate-case-findings"></a>Passaggio 4: Esaminare e convalidare i risultati dei casi

Dopo aver creato una ricerca di contenuto, è necessario esaminare e convalidare i risultati della ricerca e verificare che siano costituiti solo dai messaggi di posta elettronica che devono essere eliminati. In una ricerca di contenuto è possibile visualizzare in anteprima un campionamento casuale di 1.000 messaggi di posta elettronica senza esportare i risultati della ricerca per evitare ulteriori perdite di dati. Per ulteriori informazioni sulle limitazioni dell'anteprima, vedere [Limiti per la ricerca di contenuto.](limits-for-content-search.md)
  
Se si dispone di più di 1.000 cassette postali o più di 100 messaggi di posta elettronica per ogni cassetta postale da esaminare, è possibile dividere la ricerca iniziale in più ricerche utilizzando parole chiave o condizioni aggiuntive, ad esempio intervallo di date o mittente/destinatario, ed esaminare i risultati di ogni ricerca singolarmente. Annotare tutte le query di ricerca da utilizzare quando si eliminano i messaggi [nel passaggio 7.](#step-7-permanently-delete-the-spilled-data)

Se a un responsabile o a un utente finale viene assegnata una licenza Office 365 E5, è possibile esaminare fino a 10.000 risultati di ricerca contemporaneamente usando Advanced eDiscovery. Se sono presenti più di 10.000 messaggi di posta elettronica da esaminare, è possibile dividere la query di ricerca per intervallo di date ed esaminare ogni risultato singolarmente quando i risultati della ricerca vengono ordinati in base alla data. In Advanced eDiscovery, puoi contrassegnare i risultati della ricerca usando la funzionalità **Etichetta** come nel pannello di anteprima e filtrare il risultato della ricerca in base al tag etichettato. Ciò è utile quando si collabora con un revisore secondario. Utilizzando strumenti di analisi aggiuntivi in Advanced eDiscovery, ad esempio il riconoscimento ottico dei caratteri, il threading della posta elettronica e la codifica predittiva, è possibile elaborare e rivedere rapidamente migliaia di messaggi e contrassegnarli per un'ulteriore revisione. Vedi [Configurazione rapida per Advanced eDiscovery](./get-started-with-advanced-ediscovery.md).

Quando si trova un messaggio di posta elettronica contenente dati riversati, controllare i destinatari del messaggio per determinare se è stato condiviso esternamente. Per tracciare ulteriormente un messaggio, è possibile raccogliere informazioni sul mittente e intervalli di date in modo da poter utilizzare i registri di traccia dei messaggi. Questo processo è descritto nel [passaggio 5](#step-5-use-message-trace-log-to-check-how-spilled-data-was-shared).

Dopo aver verificato i risultati della ricerca, è possibile condividere i risultati con altri utenti per una revisione secondaria. Gli utenti assegnati al caso nel passaggio 1 possono esaminare il contenuto del caso sia in eDiscovery che Advanced eDiscovery e approvare i risultati del caso. È inoltre possibile generare un report senza esportare il contenuto effettivo. È inoltre possibile utilizzare questo stesso report come prova di eliminazione, descritta [nel passaggio 8.](#step-8-verify-provide-a-proof-of-deletion-and-audit)
  
 **Per generare un report statistico:**
  
1. Passare alla **pagina Ricerca** nel caso di eDiscovery e fare clic sulla ricerca per cui si desidera generare un report. 
    
2. Nella pagina a comparsa fare clic su **Altro > esporta report.**
 
      Viene visualizzata la pagina Esporta report.

    ![Selezionare la ricerca e quindi fare clic su Altro > esporta report nella pagina a comparsa](../media/O365-eDiscoverySolutions-DataSpillage-ExportReport1.png)
    
3. Selezionare **Tutti gli elementi,** inclusi quelli con formato non riconosciuto, sono crittografati o non sono stati indicizzati per altri motivi e quindi fare clic su Genera **report.**

4. Nel caso di eDiscovery, fare clic su **Esporta** per visualizzare l'elenco dei processi di esportazione. Potrebbe essere necessario fare clic **su Aggiorna** per aggiornare l'elenco per visualizzare il processo di esportazione creato.

5. Fare clic sul processo di esportazione e quindi su **Scarica** report nella pagina a comparsa.
 
    ![Nella pagina Esporta fare clic sull'esportazione e quindi su "Scarica report"](../media/O365-eDiscoverySolutions-DataSpillage-ExportReport2.png)

Il **report Riepilogo** esportazione contiene il numero di posizioni trovate con i risultati e le dimensioni dei risultati della ricerca. È possibile utilizzarlo per confrontare con il report generato dopo l'eliminazione e fornire come prova di eliminazione. Il report **Risultati** contiene un riepilogo più dettagliato dei risultati della ricerca, inclusi l'oggetto, il mittente, i destinatari, se il messaggio è stato letto, le date e le dimensioni di ogni messaggio. Se uno dei dettagli in questo report contiene i dati effettivamente sversati, assicurarsi di eliminare definitivamente il file Results.csv al termine dell'indagine.

Per ulteriori informazioni sull'esportazione di report, vedere [Export a Content Search report.](export-a-content-search-report.md)
    
## <a name="step-5-use-message-trace-log-to-check-how-spilled-data-was-shared"></a>Passaggio 5: Utilizzare il registro di traccia dei messaggi per verificare la modalità di condivisione dei dati riversati

Per analizzare ulteriormente se la posta elettronica con dati sversati è stata condivisa, è possibile facoltativamente eseguire una query nei registri di traccia dei messaggi con le informazioni sul mittente e sull'intervallo di date raccolte nel passaggio 4. Il periodo di conservazione per la traccia dei messaggi è di 30 giorni per i dati in tempo reale e di 90 giorni per i dati cronologici.
  
È possibile utilizzare Traccia messaggi nel Centro sicurezza e conformità o i cmdlet corrispondenti in Exchange Online PowerShell. È importante notare che l'analisi dei messaggi non offre garanzie complete sulla completezza dei dati restituiti. Per ulteriori informazioni sull'utilizzo di Traccia messaggi, vedere: 
  
- [Traccia dei messaggi nel Centro sicurezza e conformità](../security/office-365-security/message-trace-scc.md)
    
- [Nuova traccia dei messaggi nel Centro sicurezza & conformità](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/)
    
## <a name="step-6-prepare-the-mailboxes"></a>Passaggio 6: Preparare le cassette postali

Dopo aver esaminato e verificato che i risultati della ricerca contengano solo i messaggi che devono essere eliminati, è necessario raccogliere un elenco degli indirizzi di posta elettronica delle cassette postali in cui è stato generato l'impatto da utilizzare nel passaggio 7 quando si eliminano i dati sversati. Potrebbe inoltre essere necessario preparare le cassette postali prima di poter eliminare definitivamente i messaggi di posta elettronica a seconda che sia abilitato il ripristino di un singolo elemento nelle cassette postali che contengono i dati versati o se una di queste cassette postali è in attesa.
  
### <a name="get-a-list-of-addresses-of-mailboxes-with-spilled-data"></a>Ottenere un elenco di indirizzi di cassette postali con dati riversati

Esistono due modi per raccogliere un elenco di indirizzi di posta elettronica delle cassette postali con dati riversati.

**Opzione 1: ottenere un elenco di indirizzi di cassette postali con dati riversati**

1. Aprire il caso eDiscovery, passare alla **pagina Ricerca** e selezionare la ricerca di contenuto appropriata. 
    
2. Nella pagina a comparsa fare clic su **Visualizza risultati.**
    
3. Nell'elenco a discesa **Singoli risultati** fare clic su **Statistiche ricerca**.
    
4. **Nell'elenco a** discesa Tipo fare clic su **Posizioni principali.**
    
    ![Ottenere un elenco delle cassette postali che contengono i risultati della ricerca nella pagina Posizioni principali nelle statistiche di ricerca](../media/O365-eDiscoverySolutions-DataSpillage-TopLocations.png)

    Viene visualizzato un elenco delle cassette postali che contengono i risultati della ricerca. Viene visualizzato anche il numero di elementi in ogni cassetta postale che corrispondono alla query di ricerca.
    
5. Copiare le informazioni nell'elenco e salvarle in un file o fare clic su **Scarica** per scaricare le informazioni in un file CSV. 
    
**Opzione 2: ottenere le posizioni delle cassette postali dal report di esportazione**

Aprire il report Riepilogo esportazione scaricato nel [passaggio 4.](#step-4-review-and-validate-case-findings) Nella prima colonna del report, l'indirizzo di posta elettronica di ogni cassetta postale è elencato in **Posizioni**.
  
### <a name="prepare-the-mailboxes-so-you-can-delete-the-spilled-data"></a>Preparare le cassette postali in modo da poter eliminare i dati sversati

Se il ripristino di un singolo elemento è abilitato o se una cassetta postale viene messa in attesa, un messaggio eliminato definitivamente (eliminato) verrà conservato nella cartella Elementi ripristinabili. Pertanto, prima di poter eliminare i dati versati, è necessario controllare le configurazioni delle cassette postali esistenti e disabilitare il ripristino di un singolo elemento e rimuovere qualsiasi blocco o criterio di conservazione. Tenere presente che è possibile preparare una cassetta postale alla volta e quindi eseguire lo stesso comando in cassette postali diverse o creare uno script di PowerShell per preparare più cassette postali contemporaneamente.

- Vedere "Passaggio 1: raccogliere informazioni sulla cassetta postale" in Eliminare gli elementi nella cartella Elementi ripristinabili delle cassette postali basate sul cloud in attesa per istruzioni su come verificare se il ripristino di un singolo elemento è abilitato o se la cassetta postale è messa [in](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-1-collect-information-about-the-mailbox) attesa o è assegnata a un criterio di conservazione. 

- Per istruzioni sulla disabilitazione del ripristino di un singolo elemento, vedere "Passaggio 2: preparare la cassetta postale" in Eliminare elementi nella cartella Elementi ripristinabili delle cassette postali basate su [cloud.](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-2-prepare-the-mailbox) 

- Per istruzioni su come rimuovere un blocco o un criterio di conservazione da una cassetta postale, vedere "Passaggio 3: rimuovere tutti i blocchi dalla cassetta postale" in Eliminare gli elementi nella cartella Elementi ripristinabili delle cassette postali basate su [cloud.](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-3-remove-all-holds-from-the-mailbox) 

- Vedere "Passaggio 4: rimuovere il blocco di ritardo dalla cassetta postale" in Eliminare gli elementi nella cartella Elementi ripristinabili delle cassette postali basate sul [cloud](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-4-remove-the-delay-hold-from-the-mailbox) in attesa per istruzioni sulla rimozione del blocco di ritardo che viene effettuato sulla cassetta postale dopo la rimozione di qualsiasi tipo di blocco.

> [!IMPORTANT]
> Prima di rimuovere un blocco o un criterio di conservazione, rivolgersi ai reparti legali o di gestione dei record. L'organizzazione potrebbe avere un criterio che definisce se una cassetta postale in attesa o un evento imprevisto di perdita dei dati ha la priorità. 
  
Assicurarsi di ripristinare le configurazioni precedenti della cassetta postale dopo aver verificato che i dati sversati siano stati eliminati definitivamente. Vedere i dettagli nel [passaggio 7](#step-7-permanently-delete-the-spilled-data).

## <a name="step-7-permanently-delete-the-spilled-data"></a>Passaggio 7: Eliminare definitivamente i dati sversati

Utilizzando le posizioni delle cassette postali raccolte e preparate nel passaggio 6 e la query di ricerca creata e perfezionata nel passaggio 3 per trovare i messaggi di posta elettronica che contengono i dati sversati, è ora possibile eliminare definitivamente i dati versati.  Come spiegato in precedenza, per eliminare i messaggi, è necessario essere membri del gruppo di ruoli Gestione organizzazione o essere assegnati al ruolo di gestione Ricerca ed eliminazione. Per informazioni su come aggiungere gli utenti a un gruppo di ruoli, vedere [Assegnare autorizzazioni di eDiscovery nel Centro sicurezza e conformità](./assign-ediscovery-permissions.md).

Per eliminare i messaggi sversati, vedere [Cercare ed eliminare i messaggi di posta elettronica.](search-for-and-delete-messages-in-your-organization.md)

Quando si eliminano dati riversati, tenere presenti i seguenti limiti:

- Il numero massimo di cassette postali in una ricerca che è possibile utilizzare per eliminare elementi eseguendo un'azione di ricerca ed eliminazione è 50.000. Se la ricerca creata nel passaggio 3 cerca più di 50.000 cassette postali, l'azione di eliminazione avrà esito negativo. La ricerca in più di 50.000 cassette postali in un'unica operazione può in genere verificarsi quando si configura la ricerca in modo da includere tutte le cassette postali dell'organizzazione. Questa restrizione si applica inoltre quando meno di 50.000 cassette postali contengono elementi che corrispondono alla query di ricerca.

- È possibile rimuovere un massimo di 10 elementi per ogni cassetta postale alla volta. Poiché la possibilità di cercare e rimuovere i messaggi è uno strumento di intervento, questo limite garantisce che i messaggi vengano rimossi rapidamente dalle cassette postali. Questa funzionalità non ha lo scopo di pulizia delle cassette postali degli utenti.

> [!IMPORTANT]
> Gli elementi di posta elettronica in un caso di Advanced eDiscovery non possono essere eliminati usando le procedure descritte in questo articolo. Ciò è dovuto al fatto che gli elementi in un set di revisione sono copie di elementi nel servizio live copiati e archiviati in un percorso Archiviazione di Azure revisione. Ciò significa che non verranno restituiti da una ricerca di contenuto creata nel passaggio 3. Per eliminare elementi in un insieme da rivedere, è necessario eliminare il caso di Advanced eDiscovery che contiene l'insieme da rivedere. Per altre informazioni, vedere [Chiudere o eliminare un caso di Advanced eDiscovery](close-or-delete-case.md).
  
## <a name="step-8-verify-provide-a-proof-of-deletion-and-audit"></a>Passaggio 8: verificare, fornire una prova di eliminazione e controllare

Il passaggio finale del flusso di lavoro per gestire un evento imprevisto di fuoriuscita di dati consiste nel verificare che i dati sversati siano stati rimossi definitivamente dalla cassetta postale andando al caso eDiscovery e rieseguindo la stessa query di ricerca utilizzata per eliminare tali dati per verificare che non venga restituito alcun risultato. Dopo aver confermato che i dati sversati sono stati rimossi definitivamente, è possibile esportare un report e includerlo (insieme al report originale) come prova di eliminazione. È quindi possibile [chiudere il caso](close-reopen-delete-core-ediscovery-cases.md) che consentirà di riaprirlo se è necessario fare riferimento a esso in futuro. Inoltre, è anche possibile ripristinare lo stato precedente delle cassette postali, eliminare la query di ricerca utilizzata per trovare i dati versati e cercare i record di controllo delle attività eseguite durante la gestione dell'evento imprevisto di fuoriuscita di dati.
  
### <a name="reverting-the-mailboxes-to-their-previous-state"></a>Ripristino dello stato precedente delle cassette postali

Se è stata modificata una configurazione delle cassette postali nel passaggio 6 per preparare le cassette postali prima dell'eliminazione dei dati versati, sarà necessario ripristinarle allo stato precedente. Vedere "Passaggio 6: ripristinare lo stato precedente della cassetta postale" in Eliminare gli elementi nella cartella Elementi ripristinabili delle cassette postali [basate sul cloud in attesa.](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-6-revert-the-mailbox-to-its-previous-state)
  
### <a name="deleting-the-search-query"></a>Eliminazione della query di ricerca

Se le parole chiave nella query di ricerca creata e utilizzata nel passaggio 3 contengono alcuni di tutti i dati effettivamente sversati, è consigliabile eliminare la query di ricerca per evitare ulteriori perdite di dati.
  
1. Nel Centro sicurezza e conformità aprire il caso eDiscovery, passare alla pagina **Ricerca** e selezionare la ricerca di contenuto appropriata.

2. Nella pagina a comparsa fare clic su **Elimina.**

    ![Selezionare la ricerca e quindi fare clic su Elimina nella pagina a comparsa](../media/O365-eDiscoverySolutions-DataSpillage-DeleteSearch.png)

### <a name="auditing-the-data-spillage-investigation-process"></a>Controllo del processo di indagine sulla fuoriuscita di dati

È possibile cercare nel log di controllo le attività di eDiscovery eseguite durante l'indagine. È inoltre possibile eseguire una ricerca nel log di controllo per restituire i record di controllo per il comando **New-ComplianceSearchAction -Purge** eseguito nel passaggio 7 per eliminare i dati sversati. Per ulteriori informazioni, vedere:

- [Eseguire ricerche nel log di controllo](search-the-audit-log-in-security-and-compliance.md)

- [Cercare le attività di eDiscovery nel log di controllo](search-for-ediscovery-activities-in-the-audit-log.md)
