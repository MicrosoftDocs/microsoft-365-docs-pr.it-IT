---
title: Visualizzare i risultati di un'indagine automatizzata in Office 365
keywords: ARIA, autoIR, ATP, automatizzato, investigazione, risposta, correzione, minacce, avanzate, minacce, protezione
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Durante e dopo un'indagine automatizzata in Office 365, è possibile visualizzare i risultati e i risultati principali.
ms.openlocfilehash: 638559efe5f7028a647b466c030a339c677601ce
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/13/2020
ms.locfileid: "42633844"
---
# <a name="details-and-results-of-an-automated-investigation-in-office-365"></a>Informazioni dettagliate e risultati di un'indagine automatizzata in Office 365

Quando si verifica un' [analisi automatizzata](office-365-air.md) in [Office 365 Advanced Threat Protection](office-365-atp.md), i dettagli relativi a tali indagini sono disponibili durante e dopo il processo di analisi automatizzato. Se di dispone delle autorizzazioni necessarie, è possibile visualizzare i dettagli in una visualizzazione dei dettagli dell'indagine. La vista dei dettagli dell'indagine consente di avere uno stato aggiornato e la possibilità di approvare eventuali azioni in sospeso. 

## <a name="view-details-of-an-investigation"></a>Visualizzare i dettagli di un'indagine

1. Andare su [https://protection.office.com](https://protection.office.com) ed eseguire l'accesso. Questo porta al centro sicurezza & Compliance.

2. Eseguire una delle operazioni seguenti:

    - Andare al > **Dashboard**di **gestione delle minacce**. Questo porta al dashboard di [sicurezza](security-dashboard.md). I widget aria vengono visualizzati nella parte superiore del [dashboard di sicurezza](security-dashboard.md). Selezionare un widget, ad esempio **Riepilogo indagini**.

    - Andare a > **indagini**sulla **gestione delle minacce**. 

    Entrambi i metodi consentono di eseguire l'elenco delle indagini.

    ![Pagina di ricerca principale per AIR](../../media/air-maininvestigationpage.png) 

3. Nell'elenco delle indagini selezionare un elemento nella colonna **ID** . Verrà visualizzata la pagina Dettagli analisi, a partire dal grafico di analisi in visualizzazione.

    ![Pagina del grafico dell'indagine aerea](../../media/air-investigationgraphpage.png)

   Utilizzare le varie schede per ulteriori informazioni sull'indagine.

## <a name="view-details-about-an-alert-related-to-an-investigation"></a>Visualizzare i dettagli relativi a un avviso relativo a un'indagine

Alcuni tipi di avvisi attivano l'analisi automatizzata in Office 365. Per ulteriori informazioni, vedere [Alerts](automated-investigation-response-office.md#alerts). Utilizzare la procedura seguente per visualizzare i dettagli relativi a un avviso associato a un'indagine automatizzata.

1. Andare su [https://protection.office.com](https://protection.office.com) ed eseguire l'accesso. Questo porta al centro sicurezza & Compliance.

2. Andare a > **indagini**sulla **gestione delle minacce**.

3. Nell'elenco delle indagini selezionare un elemento nella colonna **ID** . 

4. Per informazioni dettagliate sull'apertura di un'indagine, selezionare la scheda **avvisi** . Tutti gli avvisi che hanno attivato l'indagine sono elencati qui.

5. Selezionare un elemento nell'elenco. Verrà aperto un riquadro a comparsa con informazioni dettagliate sull'avviso e collegamenti a ulteriori operazioni.

6. Esaminare le informazioni nel riquadro a comparsa e, a seconda dell'avviso specifico, eseguire un'azione, ad esempio **risolvere**, **sopprimere**o **informare gli utenti**. 

    - La **risoluzione** equivale alla chiusura di un avviso
    
    - Non **consente a** un criterio di attivare avvisi per un determinato periodo di tempo
    
    - **Notify gli utenti** avviano un messaggio di posta elettronica con gli indirizzi di posta elettronica degli utenti già immessi e consentono al team di operazioni di sicurezza di digitare un testo per gli utenti. (Analogo all'invio di un messaggio ai destinatari tramite [Esplora minacce](threat-explorer.md)).  

## <a name="how-to-use-the-various-tabs"></a>Come usare le varie schede

Nelle sezioni seguenti vengono illustrate le varie schede della pagina indagini automatizzate e il modo in cui è possibile utilizzare le informazioni.

### <a name="automated-investigations-page"></a>Pagina indagini automatizzate

Nella pagina indagini automatizzate vengono visualizzate le indagini dell'organizzazione e gli stati correnti.

![Pagina di ricerca principale per AIR](../../media/air-maininvestigationpage.png) 
  
È possibile:
- Passare direttamente a un'indagine (selezionare un **ID di ricerca**).
- Applicare filtri. Scegliere tra il **tipo di analisi**, l'intervallo di **tempo**, **lo stato**o una combinazione di questi.
- Esportare i dati in un file. csv.

Lo stato dell'indagine indica lo stato di avanzamento dell'analisi e delle azioni. Durante l'esecuzione dell'indagine, lo stato cambia per indicare se sono state trovate minacce e se le azioni sono state approvate. 

|Stato  |Cosa significa  |
|---------|---------|
|In avvio | L'analisi viene accodata per iniziare a breve |
|In esecuzione | L'inchiesta è iniziata e sta conducendo la sua analisi |
|Non sono state trovate minacce | L'indagine ha completato l'analisi e non sono state trovate minacce |
|Terminato dal sistema | L'inchiesta non è stata chiusa ed è scaduta dopo 7 giorni |
|Azione in sospeso | Nell'inchiesta sono state individuate minacce con azioni consigliate.  L'analisi continua a essere eseguita dopo che sono state trovate le minacce iniziali e le azioni consigliate, pertanto è necessario controllare il registro prima di approvare le azioni per verificare se gli analizzatori sono ancora in corso. |
|Minacce trovate | L'inchiesta ha rilevato minacce, ma le minacce non sono disponibili in aria.  Si tratta di azioni dell'utente in cui non è ancora presente un'azione aria di direzione. |
|Corretti | L'inchiesta è stata completata ed è stata completamente rimediata (tutte le azioni sono state approvate) |
|Parzialmente rimediato | L'inchiesta è terminata e sono state approvate alcune delle azioni consigliate |
|Terminato dall'utente | Un amministratore ha terminato l'indagine |
|Esito negativo | Si è verificato un errore durante l'indagine che impediva di raggiungere una conclusione sulle minacce |
|Accodamento tramite limitazione | L'indagine è in attesa di analisi a causa di limitazioni di elaborazione del sistema (per proteggere le prestazioni del servizio) |
|Terminata mediante limitazione | L'inchiesta non è stata completata in tempi sufficienti a causa di limitazioni del volume e dell'elaborazione del sistema di analisi. È possibile riattivare l'indagine selezionando il messaggio di posta elettronica in Esplora risorse e selezionando l'azione indaga. |

### <a name="investigation-graph"></a>Grafico dell'indagine

Quando si apre una specifica indagine, viene visualizzata la pagina del grafico delle indagini. In questa pagina vengono illustrate tutte le diverse entità: messaggi di posta elettronica, utenti (e loro attività) e dispositivi che sono stati analizzati automaticamente come parte dell'avviso che è stato attivato.

![Pagina del grafico dell'indagine aerea](../../media/air-investigationgraphpage.png)

È possibile:
- Ottenere una panoramica visiva dell'indagine corrente.
- Visualizzare un riepilogo della durata dell'indagine.
- Selezionare un nodo nella visualizzazione per visualizzare i dettagli per il nodo.
- Selezionare una scheda all'interno della parte superiore per visualizzare i dettagli per tale scheda.

### <a name="alert-investigation"></a>Indagine sugli avvisi

Nella scheda **avvisi** per un'indagine, è possibile visualizzare gli avvisi rilevanti per l'indagine. I dettagli includono l'avviso che ha attivato l'indagine e altri avvisi correlati, ad esempio l'accesso rischioso, le violazioni dei criteri DLP e così via, che sono correlate all'inchiesta. Da questa pagina, un analista di sicurezza può anche visualizzare ulteriori dettagli sui singoli avvisi.

![Pagina avvisi aria](../../media/air-investigationalertspage.png)

È possibile:
- Ottenere una panoramica visiva dell'avviso di attivazione corrente e degli eventuali avvisi associati.
- Selezionare un avviso nell'elenco per aprire una pagina di volo che Visualizza i dettagli degli avvisi completi.

### <a name="email-investigation"></a>Indagine tramite posta elettronica

Nella scheda **posta elettronica** per un'indagine, è possibile visualizzare i messaggi di e-mail originali e i cluster di messaggi di posta elettronica analoghi identificati nell'ambito dell'inchiesta. 

Dato il volume totale di messaggi di posta elettronica che gli utenti di un'organizzazione inviano e ricevono, oltre alla natura multi-utente delle comunicazioni e degli attacchi di posta elettronica, il processo di 
- clustering dei messaggi di posta elettronica in base a attributi simili provenienti da un'intestazione, corpo, URL e allegati del messaggio; 
- separazione di messaggi di posta elettronica dannosi dal buon messaggio di posta elettronica; e 
- esecuzione di un'azione su messaggi di posta elettronica dannosi 

può richiedere molto tempo. AIR ora automatizza questo processo, salvando il tempo e lo sforzo del team di sicurezza dell'organizzazione. 

Durante il passaggio di analisi della posta elettronica possono essere identificati due tipi di cluster di posta elettronica: cluster di somiglianza e cluster di indicatori. 
- I cluster di somiglianza sono messaggi di posta elettronica identificati dalla ricerca di messaggi di posta elettronica con attributi di contenuto e mittente simili. Tali cluster vengono valutati per i contenuti dannosi in base ai risultati di rilevamento originali. I cluster di posta elettronica che contengono sufficienti rilevamenti di posta elettronica dannosi sono considerati dannosi.
- I cluster di indicatori sono messaggi di posta elettronica identificati tramite la ricerca per la stessa entità indicatore (hash di file o URL) dal messaggio di posta elettronica originale. Quando l'entità file/URL originale viene identificata come dannosa, AIR applica l'indicatore verdetto all'intero gruppo di messaggi di posta elettronica che contiene tale entità. Un file identificato come malware indica che il cluster di messaggi di posta elettronica che contiene il file viene trattato come messaggio di posta elettronica antimalware.

L'obiettivo del raggruppamento è la ricerca e la ricerca di altri messaggi di posta elettronica correlati inviati dallo stesso mittente come parte di un attacco o di una campagna.  In alcuni casi, la posta elettronica legittima può innescare un'indagine (ad esempio, un utente segnala un messaggio di posta elettronica di marketing).  In questi scenari, il clustering di posta elettronica dovrebbe identificare che i cluster di posta elettronica non sono dannosi – quando lo fa in modo appropriato, **non** indicherà una minaccia né la rimozione della posta elettronica.

La scheda **posta elettronica** Visualizza anche gli elementi di posta elettronica relativi all'indagine, ad esempio i dettagli di posta elettronica segnalati dall'utente, il messaggio di posta elettronica originale riportato, i messaggi di posta elettronica zapped a causa di malware/phishing e così via.

Il numero di messaggi di posta elettronica identificati nella scheda posta elettronica rappresenta attualmente la somma totale di tutti gli SMS visualizzati nella scheda **posta elettronica** . Poiché i messaggi di posta elettronica sono presenti in più cluster, il conteggio totale effettivo dei messaggi di posta elettronica identificati (ed è influenzato dalle azioni correttive) è il numero di messaggi di posta elettronica univoci presenti in tutti i cluster e nei messaggi di posta elettronica dei destinatari originali. 

Entrambi i messaggi di posta elettronica di Explorer e conteggio aria sono per ogni destinatario, in quanto i verdetti di sicurezza, le azioni e i percorsi di recapito variano in base al destinatario. Pertanto, un messaggio di posta elettronica originale inviato a tre utenti conta come un totale di tre messaggi di posta elettronica anziché un messaggio di posta elettronica. Nota potrebbero verificarsi casi in cui un messaggio di posta elettronica viene contato due o più volte, poiché il messaggio di posta elettronica può avere più azioni su di esso e potrebbe essere più copie del messaggio di posta elettronica una volta che tutte le azioni si verificano. Ad esempio, un messaggio di posta elettronica antimalware rilevato al momento del parto può comportare un messaggio di posta elettronica bloccato (in quarantena) e un messaggio di posta elettronica sostituito (il file di minacce è stato sostituito da un file di avviso e quindi recapitato alla cassetta postale Poiché vi sono letteralmente due copie del messaggio di posta elettronica nel sistema, entrambe possono essere conteggiate nei conteggi dei cluster. 

I conteggi dei messaggi di posta elettronica vengono calcolati al momento dell'indagine e alcuni conteggi vengono ricalcolati quando si apre l'indagine comparsa (in base a una query sottostante). Il numero di messaggi di posta elettronica visualizzati per i cluster di posta elettronica nella scheda posta elettronica e il valore della quantità di posta elettronica visualizzato nel riquadro a comparsa del cluster vengono calcolati al momento dell'indagine e non cambiano. Il numero di posta elettronica visualizzato nella parte inferiore della scheda posta elettronica del riquadro a comparsa del cluster di posta elettronica e il numero di messaggi di posta elettronica visualizzati in Esplora riflettono i messaggi di posta elettronica ricevuti dopo l'analisi iniziale dell'indagine. In questo modo un cluster di posta elettronica che mostra una quantità originale di 10 messaggi di posta elettronica mostrerà una lista di posta elettronica di 15 quando altri cinque messaggi di posta elettronica arrivano tra la fase di analisi dell'inchiesta e quando l'amministratore esamina l'indagine.  Analogamente, le indagini precedenti potrebbero avere un numero maggiore rispetto alle query di Explorer, poiché i dati di ATP P2 scadono dopo 7 giorni per le prove e 30 giorni per le licenze a pagamento.  La visualizzazione dei conteggi cronologici e correnti di count in visualizzazioni diverse viene eseguita per indicare l'impatto della posta elettronica al momento dell'indagine e l'impatto corrente fino al momento in cui viene eseguita la correzione.

Si consideri, ad esempio, lo scenario seguente. Il primo gruppo di tre messaggi di posta elettronica è stato ritenuto phishing. Un altro gruppo di messaggi simili con lo stesso IP e l'oggetto è stato trovato e considerato dannoso, in quanto alcuni di essi sono stati identificati come phishing durante il rilevamento iniziale. 

![Pagina di ricerca della posta elettronica AEREa](../../media/air-investigationemailpage.png)

È possibile:
- Ottenere una panoramica visiva dei risultati del clustering corrente e delle minacce trovate.
- Fare clic su un'entità cluster o su un elenco di minacce per aprire una pagina di volo che Visualizza i dettagli degli avvisi completi.
- Esaminare ulteriormente il cluster di posta elettronica facendo clic sul collegamento ' Apri in Esplora risorse ' nella parte superiore della scheda ' dettagli cluster di posta elettronica '

![Messaggi di posta elettronica di analisi AEREa con dettagli a comparsa](../../media/air-investigationemailpageflyoutdetails.png)

> [!NOTE]
> Nel contesto della posta elettronica, è possibile che venga visualizzata una superficie di minaccia per l'anomalia del volume come parte dell'indagine. Un'anomalia del volume indica un picco nei messaggi di posta elettronica simili nei pressi del tempo dell'evento di indagine rispetto ai tempi precedenti. Questo picco del traffico di posta elettronica con caratteristiche simili (ad esempio, dominio del mittente e del soggetto, somiglianza del corpo e IP del mittente) è tipico dell'inizio delle campagne di posta elettronica o degli attacchi. Tuttavia, la massa, la posta indesiderata e le campagne di posta elettronica legittime condividono queste caratteristiche. Le anomalie dei volumi rappresentano una potenziale minaccia e, di conseguenza, potrebbero essere meno gravi rispetto alle minacce di malware o phishing identificate con motori anti-virus, detonazione o reputazione dannosa.

### <a name="user-investigation"></a>Analisi degli utenti

Nella scheda **utenti** è possibile visualizzare tutti gli utenti identificati come parte dell'indagine. Gli account utente vengono visualizzati nell'inchiesta quando si verifica un evento o un'indicazione del fatto che tali account utente potrebbero essere intaccati o compromessi.

Ad esempio, nell'immagine seguente, l'aria ha identificato indicatori di compromesso e anomalie basate su una nuova regola di posta in arrivo che è stata creata. Ulteriori dettagli (prova) dell'indagine sono disponibili tramite visualizzazioni dettagliate all'interno di questa scheda. gli indicatori di compromesso e anomalie possono includere anche rilevamenti di anomalie dalla [sicurezza delle app cloud di Microsoft](https://docs.microsoft.com/cloud-app-security).

![Pagina utenti di analisi AEREa](../../media/air-investigationuserspage.png)

È possibile:
- Ottenere una panoramica visiva dei risultati e dei rischi individuati dall'utente.
- Selezionare un utente per l'apertura di una pagina di fly-out che Visualizza i dettagli degli avvisi completi.

### <a name="machine-investigation"></a>Indagine del computer

Nella scheda **computer** , è possibile visualizzare tutti i computer identificati come parte dell'indagine. 

![Pagina macchina dell'analisi aerea](../../media/air-investigationmachinepage.png)

Come parte di alcuni PlayBook, AIR correla le minacce alla posta elettronica ai dispositivi (ad esempio, malware con zapping). Ad esempio, un'analisi passa un hash di file dannosi a [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection
) per esaminare. Questo consente l'analisi automatizzata delle macchine rilevanti per gli utenti, per garantire che le minacce vengano affrontate sia nel cloud che negli endpoint. 

È possibile:
- Ottenere una panoramica visiva dei computer e delle minacce correnti trovati.
- Selezionare un computer per aprire una visualizzazione che si riferisce alle [indagini ATP Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations) correlate in Microsoft Defender Security Center.

### <a name="entity-investigation"></a>Indagine su entità

Nella scheda **entità** , è possibile visualizzare le entità identificate e analizzate nell'ambito dell'indagine. 

In questa sezione, è possibile visualizzare le entità indagate e i dettagli dei tipi di entità, ad esempio i messaggi di posta elettronica, i cluster, gli indirizzi IP, gli utenti e altro ancora. È inoltre possibile vedere quante entità sono state analizzate e le minacce che sono state associate a ognuna di esse. 

![Pagina delle entità di indagine AEREa](../../media/air-investigationentitiespage.png)

È possibile:
- Ottenere una panoramica visiva delle entità investigative e delle minacce trovate.
- Selezionare un'entità per aprire una pagina di fly-out che Visualizza i dettagli dell'entità correlata.

![Dettagli sulle entità di indagine AEREa](../../media/air-investigationsentitiespagedetails.png)

### <a name="playbook-log"></a>Registro PlayBook

Nella scheda **log** , è possibile visualizzare tutti i passaggi del PlayBook che si sono verificati durante l'indagine. Il log acquisisce un inventario completo di tutti gli analizzatori e le azioni completate dalle funzionalità di analisi automatica di Office 365 come parte di AIR. Viene fornita una chiara visualizzazione di tutti i passaggi, tra cui l'azione stessa, una descrizione e la durata dell'effettivo dall'inizio alla fine. 

![Pagina del registro delle indagini AEREe](../../media/air-investigationlogpage.png)

È possibile:
- Ottenere una panoramica visiva dei passaggi di PlayBook eseguiti.
- Esportare i risultati in un file CSV.
- Filtrare la visualizzazione.

|Dell'analizzatore dell' | Descrizione |
|-----|-----|
|Indagini sulle violazioni DLP |Esaminare eventuali violazioni rilevate da [Office 365 prevenzione della perdita di dati](../../compliance/data-loss-prevention-policies.md) (DLP) |
|Estrazione degli indicatori di posta elettronica |Estrarre indicatori dall'intestazione, dal corpo e dal contenuto di un messaggio di posta elettronica per l'analisi |
|Reputazione hash file |Rilevare anomalie in base agli hash dei file per gli utenti e i computer dell'organizzazione |
|Identificazione del cluster di posta |Analisi del cluster di posta elettronica basata su intestazione, corpo, contenuto e URL |
|Analisi del volume del cluster di posta |Analisi del cluster di posta elettronica basata su modelli di volume del flusso di posta in uscita |
|Indagine sulla delega della posta |Esaminare l'accesso alla delega della posta per le cassette postali degli utenti correlate all'analisi |
|Analisi delle regole di inoltro della posta |Esaminare le regole di inoltro della posta per le cassette postali degli utenti relative a questa indagine |
|Rilevato malware rilevati |Rilevare la presenza di malware mancante recapitato alla cassetta postale dell'utente nell'organizzazione |
|Detonazione su richiesta |Detonazione su richiesta attivata per i messaggi di posta elettronica, gli allegati e gli URL |
|Indagine sull'anomalia della posta in uscita |Rilevare anomalie basate su modelli di invio di flussi di posta cronologici per gli utenti dell'organizzazione |
|Indagine su malware e posta indesiderata in uscita |Rilevare malware, phishing o posta indesiderata intra-org e in uscita provenienti da utenti dell'organizzazione |
|Indagine sul dominio del mittente |Controllo su richiesta della reputazione del dominio da [Microsoft Intelligent Security Graph](https://www.microsoft.com/security/operations/intelligence) e fonti di intelligence per le minacce esterne |
|Indagine IP del mittente | Controllo su richiesta della reputazione IP dal [grafico Microsoft Intelligent Security Graph](https://www.microsoft.com/security/operations/intelligence) e dalle fonti di intelligence per le minacce esterne |
|Indagine clic URL | Esaminare i clic degli utenti protetti da [collegamenti sicuri di Office 365 ATP](atp-safe-links.md) nell'organizzazione |
|Indagine sulla reputazione URL |Verifica su richiesta sulla reputazione URL del grafico di [sicurezza intelligente di Microsoft](https://www.microsoft.com/security/operations/intelligence) e delle origini di intelligence per le minacce esterne |
|Indagine sulle attività degli utenti |Analisi delle anomalie delle attività degli utenti in [Microsoft cloud app Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) |
|Estrazione degli indicatori di messaggi di posta elettronica segnalati dall'utente |Estrarre indicatori dall'intestazione, dal corpo e dal contenuto della [posta elettronica segnalata dall'utente](enable-the-report-message-add-in.md) per l'analisi |

### <a name="recommended-actions"></a>Azioni consigliate

Nella scheda **azioni** , è possibile visualizzare tutte le azioni di PlayBook consigliate per la correzione dopo il completamento dell'indagine. 

Azioni acquisire i passaggi consigliati da Microsoft al termine di un'indagine. È possibile eseguire le azioni di correzione selezionando una o più azioni. Se si fa clic su **approva** è possibile iniziare la correzione. (Sono necessarie autorizzazioni appropriate: il ruolo ' Search and Purge ' è necessario per eseguire azioni da Explorer e AIR). Ad esempio, un lettore di sicurezza è in grado di visualizzare le azioni, ma non di approvarle. Nota: non è necessario approvare ogni azione. Se non si è d'accordo con l'azione consigliata o l'organizzazione non sceglie alcuni tipi di azioni, è possibile scegliere di **rifiutare** le azioni o semplicemente ignorarle e non intraprendere alcuna azione. L'approvazione e/o il rifiuto di tutte le azioni consente di chiudere completamente l'indagine (lo stato viene ripristinato), lasciando inalterate alcune azioni allo stato dell'inchiesta che cambia in uno stato parzialmente rimediato.

![Pagina azione indagini AEREe](../../media/air-investigationactionspage.png)

È possibile:
- Ottenere una panoramica visiva delle azioni consigliate in PlayBook.
- Selezionare una singola azione o più azioni.
- Approvare o rifiutare le azioni consigliate con i commenti.
- Esportare i risultati in un file CSV.
- Filtrare la visualizzazione.

## <a name="next-steps"></a>Passaggi successivi

- [Esaminare e approvare le azioni in sospeso](air-remediation-actions.md)

- [Informazioni sull'analisi e la risposta automatizzate in Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)