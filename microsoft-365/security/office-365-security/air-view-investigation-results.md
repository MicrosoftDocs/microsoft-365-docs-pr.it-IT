---
title: Visualizzare i risultati di un'indagine automatizzata in Microsoft 365
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
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Durante e dopo un'analisi automatizzata in Microsoft 365, è possibile visualizzare i risultati e i risultati principali.
ms.date: 11/05/2020
ms.openlocfilehash: 4dc74987619c3f958c874927af6e4240b9d7e154
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357286"
---
# <a name="details-and-results-of-an-automated-investigation-in-microsoft-365"></a>Dettagli e risultati di un'indagine automatizzata in Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Quando si verifica un' [indagine automatizzata](office-365-air.md) in [Microsoft Defender per Office 365](office-365-atp.md), i dettagli relativi a tali indagini sono disponibili durante e dopo il processo di analisi automatizzato. Se si dispone delle autorizzazioni necessarie, è possibile visualizzare tali dettagli nel centro sicurezza Microsoft 365. I dettagli dell'analisi forniscono lo stato di aggiornamento e la possibilità di approvare le azioni in sospeso.

## <a name="investigation-status"></a>Stato analisi

Lo stato dell'indagine indica lo stato di avanzamento dell'analisi e delle azioni. Durante l'esecuzione dell'indagine, lo stato cambia per indicare se sono state trovate minacce e se le azioni sono state approvate.

|Stato|Descrizione|
|---|---|
|**In avvio**|L'indagine è stata attivata e in attesa di avviare l'esecuzione.|
|**In esecuzione**|Il processo di indagine è iniziato ed è in corso. Questo stato si verifica anche quando vengono approvate le [azioni in sospeso](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions) .|
|**Non sono state trovate minacce**|L'inchiesta è terminata e non sono state identificate minacce (account utente, messaggio di posta elettronica, URL o file). <p> **Suggerimento**: se si sospetta che qualcosa sia stato perso (ad esempio, un falso negativo), è possibile eseguire un'azione utilizzando [Esplora minacce](threat-explorer.md).|
|**Minacce trovate**|L'analisi automatizzata ha riscontrato problemi, ma non sono state eseguite azioni correttive specifiche per risolvere tali problemi. <p> Lo stato delle **minacce individuate** può verificarsi quando è stato identificato un tipo di attività dell'utente, ma non sono disponibili azioni di pulizia. Negli esempi sono incluse le attività utente seguenti: <ul><li>Un evento di [prevenzione della perdita di dati](https://docs.microsoft.com/Microsoft-365/compliance/data-loss-prevention-policies) (DLP)</li><li>Anomalia nell'invio di messaggi di posta elettronica</li><li>Malware inviato</li><li>Phishing inviati</li></ul> <p> Nell'inchiesta non sono stati trovati URL dannosi, file o messaggi di posta elettronica da correggere e non è stata rilevata alcuna attività della cassetta postale, ad esempio la disattivazione delle regole di inoltro o la delega. <p> **Suggerimento**: se si sospetta che qualcosa sia stato perso (ad esempio, un falso negativo), è possibile esaminare e intraprendere un'azione tramite l'utilizzo di [Esplora minacce](threat-explorer.md).|
|**Terminato dal sistema**|L'indagine è stata interrotta. L'analisi può essere interrotta per diversi motivi: <ul><li>Le azioni in sospeso dell'indagine sono state scadute. Timeout delle azioni in sospeso dopo aver atteso l'approvazione per una settimana.</li><li>Sono presenti troppe azioni. Ad esempio, se sono presenti troppi utenti che fanno clic su URL dannosi, può superare la capacità dell'indagine di eseguire tutti gli analizzatori, in modo che l'analisi venga interrotta.</li></ul> <p> **Suggerimento**: se un'analisi si interrompe prima che vengano eseguite azioni, provare a utilizzare [Threat Explorer](threat-explorer.md) per individuare e risolvere le minacce.|
|**Azione in sospeso**|L'inchiesta ha individuato una minaccia, ad esempio un messaggio di posta indesiderata, un URL dannoso o un'impostazione di cassetta postale rischiosa e un'azione per correggere tale minaccia è in [attesa di approvazione](air-review-approve-pending-completed-actions.md). <p> Lo stato dell' **azione in sospeso** viene attivato quando viene trovata una minaccia con un'azione corrispondente. Tuttavia, l'elenco delle azioni in sospeso può aumentare durante l'esecuzione di un'indagine. Controllare il [registro delle indagini](#playbook-log) per verificare se altri elementi sono ancora in attesa di completamento.|
|**Corretti**|L'inchiesta è stata completata e tutte le azioni di correzione sono state approvate (viene indicato come completamente corretti). <p> **Nota**: le azioni di correzione approvate possono avere errori che impediscono l'esecuzione delle azioni. Indipendentemente dal fatto che le azioni di correzione siano state completate correttamente, lo stato dell'inchiesta non cambia. Controllare il [registro delle indagini](#playbook-log) per ottenere risultati dettagliati.|
|**Parzialmente rimediato**|L'analisi ha portato a operazioni di correzione e alcune sono state approvate e completate. Altre azioni sono ancora [in sospeso](air-review-approve-pending-completed-actions.md).|
|**Operazione non riuscita**|Almeno un analizzatore dell'analisi ha riscontrato un problema in cui non è stato possibile completarlo correttamente. <p> **Nota**: se un'indagine ha esito negativo dopo che sono state approvate le azioni di correzione, le azioni di correzione potrebbero essere state eseguite correttamente. Controllare il [registro delle indagini](#playbook-log) per ottenere risultati dettagliati.|
|**Accodamento tramite limitazione**|Viene eseguita un'analisi in una coda. Quando vengono completate altre indagini, vengono avviate indagini accodate. La limitazione consente di evitare scarse prestazioni del servizio.  <p> **Suggerimento**: le azioni in sospeso possono limitare il numero di nuove indagini che è possibile eseguire. Assicurarsi di [approvare (o rifiutare) le azioni in sospeso](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions).|
|**Terminata mediante limitazione**|Se una ricerca viene mantenuta troppo a lungo in coda, si interrompe. <p> **Suggerimento**: è possibile [avviare un'indagine da Esplora minacce](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).|
|

## <a name="view-details-of-an-investigation"></a>Visualizzare i dettagli di un'indagine

1. Accedere al centro sicurezza & conformità ( [https://protection.office.com](https://protection.office.com) ) ed eseguire l'accesso.

2. Eseguire una delle operazioni seguenti:

    - Andare al dashboard di **gestione delle minacce** \> **Dashboard**. Questo porta al dashboard di [sicurezza](security-dashboard.md). I widget aria vengono visualizzati nella parte superiore del [dashboard di sicurezza](security-dashboard.md). Selezionare un widget, ad esempio **Riepilogo indagini**.

    - Andare a indagini sulla **gestione delle minacce** \> **Investigations**.

    Entrambi i metodi consentono di eseguire l'elenco delle indagini.

    ![Pagina di ricerca principale per AIR](../../media/air-maininvestigationpage.png)

3. Nell'elenco delle indagini selezionare un elemento nella colonna **ID** . Verrà visualizzata la pagina Dettagli analisi, a partire dal grafico di analisi in visualizzazione.

    ![Pagina del grafico dell'indagine aerea](../../media/air-investigationgraphpage.png)

   Utilizzare le varie schede per ulteriori informazioni sull'indagine.

## <a name="view-details-about-an-alert-related-to-an-investigation"></a>Visualizzare i dettagli relativi a un avviso relativo a un'indagine

Alcuni tipi di avvisi attivano l'analisi automatizzata in Microsoft 365. Per ulteriori informazioni, vedere [criteri di avviso che attivano le indagini automatizzate](office-365-air.md#which-alert-policies-trigger-automated-investigations).

Utilizzare la procedura seguente per visualizzare i dettagli relativi a un avviso associato a un'indagine automatizzata.

1. Accedere al centro sicurezza & conformità ( [https://protection.office.com](https://protection.office.com) ) ed eseguire l'accesso.

2. Andare a indagini sulla **gestione delle minacce** \> **Investigations**.

3. Nell'elenco delle indagini selezionare un elemento nella colonna **ID** .

4. Per informazioni dettagliate sull'apertura di un'indagine, selezionare la scheda **avvisi** . Tutti gli avvisi che hanno attivato l'indagine sono elencati qui.

5. Selezionare un elemento nell'elenco. Verrà aperto un riquadro a comparsa con informazioni dettagliate sull'avviso e collegamenti a ulteriori operazioni.

6. Esaminare le informazioni nel riquadro a comparsa e, a seconda dell'avviso specifico, eseguire un'azione, ad esempio **risolvere**, **sopprimere** o **informare gli utenti**.

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

- Applicare filtri. Scegliere tra il **tipo di analisi**, l'intervallo di **tempo**, **lo stato** o una combinazione di questi.

- Esportare i dati in un file. csv.

### <a name="investigation-graph"></a>Grafico dell'indagine

Quando si apre una specifica indagine, viene visualizzata la pagina del grafico delle indagini. In questa pagina vengono illustrate tutte le diverse entità: messaggi di posta elettronica, utenti (e loro attività) e dispositivi che sono stati analizzati automaticamente come parte dell'avviso che è stato attivato.

![Pagina del grafico dell'indagine aerea](../../media/air-investigationgraphpage.png)

È possibile:

- Ottenere una panoramica visiva dell'indagine corrente.
- Visualizzare un riepilogo della durata dell'indagine.
- Selezionare un nodo nella visualizzazione per visualizzare i dettagli per il nodo.
- Selezionare una scheda all'interno della parte superiore per visualizzare i dettagli per tale scheda.

### <a name="alert-investigation"></a>Indagine sugli avvisi

Nella scheda **avvisi** per un'indagine, è possibile visualizzare gli avvisi rilevanti per l'indagine. I dettagli includono l'avviso che ha attivato l'indagine e altri avvisi correlati, ad esempio l'accesso rischioso, le violazioni dei [criteri DLP](https://docs.microsoft.com/Microsoft-365/compliance/data-loss-prevention-policies) e così via, che sono correlate all'inchiesta. Da questa pagina, un analista di sicurezza può anche visualizzare ulteriori dettagli sui singoli avvisi.

![Pagina avvisi aria](../../media/air-investigationalertspage.png)

È possibile:

- Ottenere una panoramica visiva dell'avviso di attivazione corrente e degli eventuali avvisi associati.
- Selezionare un avviso nell'elenco per aprire una pagina di volo che Visualizza i dettagli degli avvisi completi.

### <a name="email-investigation"></a>Indagine tramite posta elettronica

Nella scheda **posta elettronica** per un'indagine, è possibile visualizzare i messaggi di e-mail originali e i cluster di messaggi di posta elettronica analoghi identificati nell'ambito dell'inchiesta. La scheda **posta elettronica** Visualizza anche gli elementi di posta elettronica relativi all'indagine, ad esempio i dettagli di posta elettronica segnalati dall'utente, il messaggio di posta elettronica originale riportato, i messaggi di posta elettronica zapped a causa di malware/phishing e così via.

![Pagina di ricerca della posta elettronica AEREa](../../media/air-investigationemailpage.png)

Con l'indagine tramite posta elettronica, è possibile:

- Ottenere una panoramica visiva dei risultati del clustering corrente e delle minacce trovate.
- Fare clic su un'entità cluster o su un elenco di minacce per aprire una pagina di volo che Visualizza i dettagli degli avvisi completi.
- Esaminare ulteriormente il cluster di posta elettronica facendo clic sul collegamento **Apri in Esplora nella** parte superiore della scheda **Dettagli cluster di posta elettronica**

![Messaggi di posta elettronica di analisi AEREa con dettagli a comparsa](../../media/air-investigationemailpageflyoutdetails.png)

Dato il volume totale di messaggi di posta elettronica che gli utenti di un'organizzazione inviano e ricevono, oltre alla natura multiutente delle comunicazioni e degli attacchi di posta elettronica, il processo seguente può richiedere una quantità di tempo significativa:

1. Clustering dei messaggi di posta elettronica basati su attributi simili provenienti da un'intestazione, un corpo, un URL e degli allegati del messaggio.
2. Separazione di messaggi di posta elettronica dannosi dal buon messaggio di posta elettronica.
3. Azione su messaggi di posta elettronica dannosi.

AIR automatizza questo processo, salvando il tempo e lo sforzo del team di sicurezza dell'organizzazione.

#### <a name="types-of-email-clusters"></a>Tipi di cluster di posta elettronica

È possibile identificare tre diversi tipi di cluster di posta elettronica durante il passaggio di analisi della posta elettronica: cluster di somiglianza (tutte le indagini), cluster di indicatori (tutte le indagini) e cluster di cassette postali/utenti. Nella tabella seguente vengono descritti questi tipi di cluster di posta elettronica.

|Cluster di posta elettronica|Descrizione|
|---|---|
|Cluster di somiglianza|Messaggi di posta elettronica identificati dalla ricerca di messaggi di posta elettronica con attributi di contenuto e mittente simili. Tali cluster vengono valutati per i contenuti dannosi in base ai risultati di rilevamento originali. I cluster di posta elettronica che contengono sufficienti rilevamenti di posta elettronica dannosi sono considerati dannosi.|
|Cluster di indicatori|Messaggi di posta elettronica identificati tramite la ricerca per la stessa entità indicatore (hash di file o URL) dal messaggio di posta elettronica originale. Quando l'entità file/URL originale viene identificata come dannosa, AIR applica l'indicatore verdetto all'intero gruppo di messaggi di posta elettronica che contiene tale entità. Un file identificato come malware indica che il cluster di messaggi di posta elettronica che contiene il file viene trattato come messaggio di posta elettronica antimalware.|
|Cluster di cassette postali/utenti|Messaggi di posta elettronica relativi all'utente coinvolto in un'indagine di compromesso dell'utente. Questi cluster di posta elettronica sono per un'ulteriore analisi da parte del team delle operazioni di sicurezza e non generano azioni di correzione della posta elettronica. <p> The Compromised User Security PlayBook esamina i messaggi di posta elettronica inviati dall'utente analizzato per comprendere l'impatto potenziale dei messaggi di posta elettronica inviati dalla cassetta postale.|

> [!NOTE]
> L'obiettivo del raggruppamento è la ricerca e la ricerca di altri messaggi di posta elettronica correlati inviati dallo stesso mittente come parte di un attacco o di una campagna.  In alcuni casi, la posta elettronica legittima potrebbe attivare un'indagine (ad esempio, un utente segnala un messaggio di posta elettronica di marketing).  In questi scenari, il clustering di posta elettronica dovrebbe identificare che i cluster di posta elettronica non sono dannosi – quando lo fa in modo appropriato, **non** indicherà una minaccia o la rimozione della posta elettronica.

#### <a name="email-classifications"></a>Classificazione della posta elettronica

Poiché i messaggi di posta elettronica vengono analizzati, sono classificati come *dannosi*, *sospetti* o *puliti* (come in, *non identificati come una minaccia*):

- I *messaggi di posta elettronica dannosi* inviati dalla cassetta postale o dall'utente indicano un potenziale compromesso della cassetta postale/account. Sono visualizzati altri utenti e cassette postali che possono essere influenzati da messaggi di posta elettronica dannosi come parte di un compromesso.

- I messaggi di posta elettronica *sospetti* inviati dalla cassetta postale/utente indicano il potenziale per un account compromesso o un'attività di posta indesiderata. Questi messaggi includono qualsiasi messaggio di posta indesiderata o in blocco inviato dalla cassetta postale.

- La *pulizia* dei messaggi di posta elettronica (messaggi di posta elettronica che non sono considerati una minaccia) inviati dalla cassetta postale/utente può fornire al team delle operazioni di sicurezza la visualizzazione di messaggi di posta elettronica legittimi inviati. Tuttavia, questi messaggi di posta elettronica possono includere anche i dati exfiltration se l'account di posta elettronica è compromesso.

#### <a name="more-about-email-counts"></a>Altre informazioni sui conteggi di posta elettronica

Il numero di messaggi di posta elettronica identificati nella scheda posta elettronica rappresenta al momento la somma totale di tutte le e-mail che sono state visualizzate nella scheda **posta elettronica** . Poiché i messaggi di posta elettronica sono presenti in più cluster, il conteggio totale effettivo dei messaggi di posta elettronica identificati (ed è influenzato dalle azioni correttive) è il numero di messaggi di posta elettronica univoci presenti in tutti i cluster e nei messaggi di posta elettronica dei destinatari originali.

Entrambi i messaggi di posta elettronica per l' [esploratore](threat-explorer.md) e il numero di aria su una base per destinatario, perché i verdetti di sicurezza, le azioni e i percorsi di recapito variano in base al destinatario. Pertanto, un messaggio di posta elettronica originale inviato a tre utenti conta come un totale di tre messaggi di posta elettronica anziché un messaggio di posta elettronica.

Potrebbero verificarsi casi in cui un messaggio di posta elettronica viene contato due o più volte, ad esempio quando un messaggio di posta elettronica contiene più azioni o quando sono presenti più copie del messaggio di posta elettronica quando si verificano tutte le azioni.

Ad esempio, un messaggio di posta elettronica antimalware rilevato al momento del parto può comportare sia un messaggio di posta elettronica bloccato (in quarantena) che un messaggio di posta elettronica sostituito (file di minacce sostituito da un file di avviso, quindi recapitato alla cassetta postale dell'utente Poiché vi sono letteralmente due copie del messaggio di posta elettronica nel sistema, entrambe possono essere conteggiate nei conteggi dei cluster.

> [!IMPORTANT]
> Di seguito sono riportate alcune considerazioni da tenere presenti:
>
> - I conteggi dei messaggi di posta elettronica vengono calcolati al momento dell'indagine e alcuni conteggi vengono ricalcolati quando si apre l'indagine comparsa (in base a una query sottostante).
>
> - Il numero di messaggi di posta elettronica visualizzati per i cluster di posta elettronica nella scheda **posta elettronica** e il valore della quantità di posta elettronica visualizzato nel riquadro a comparsa del cluster vengono calcolati al momento dell'indagine e non cambiano.
>
> - Il numero di posta elettronica visualizzato nella parte inferiore della scheda **posta elettronica** del riquadro a comparsa del cluster di posta elettronica e il numero di messaggi di posta elettronica visualizzati in Esplora riflettono i messaggi di posta elettronica ricevuti dopo l'analisi iniziale dell'indagine.

Di conseguenza, un cluster di posta elettronica che mostra una quantità originale di 10 messaggi di posta elettronica mostrerebbe un totale di 15 messaggi di posta elettronica quando vengono visualizzati altri cinque messaggio di posta elettronica tra la fase di analisi dell'inchiesta e quando l'amministratore esamina l'indagine. Analogamente, le indagini precedenti potrebbero iniziare a mostrare conteggi superiori rispetto alle query di Esplora risorse, poiché i dati in Microsoft Defender per Office 365 piano 2 scadono dopo 7 giorni per le prove e dopo 30 giorni per le licenze a pagamento.

La visualizzazione dei conteggi cronologici e correnti di count in visualizzazioni diverse viene eseguita per indicare l'impatto della posta elettronica al momento dell'indagine e l'impatto corrente fino al momento in cui viene eseguita la correzione.

> [!NOTE]
> Nel contesto della posta elettronica, è possibile che venga visualizzata una superficie di minaccia per l'anomalia del volume come parte dell'indagine. Un'anomalia del volume indica un picco nei messaggi di posta elettronica simili nei pressi del tempo dell'evento di indagine rispetto ai tempi precedenti. Questo picco del traffico di posta elettronica con caratteristiche simili (ad esempio, dominio del mittente e del soggetto, somiglianza del corpo e IP del mittente) è tipico dell'inizio delle campagne di posta elettronica o degli attacchi.
> Tuttavia, la massa, la posta indesiderata e le campagne di posta elettronica legittime condividono queste caratteristiche.
>
> Le anomalie dei volumi rappresentano una potenziale minaccia e, di conseguenza, potrebbero essere meno gravi rispetto alle minacce di malware o phishing identificate con motori anti-virus, detonazione o reputazione dannosa.

### <a name="user-investigation"></a>Analisi degli utenti

Nella scheda **utenti** è possibile visualizzare tutti gli utenti identificati come parte dell'indagine. Gli account utente vengono visualizzati nell'inchiesta quando si verifica un evento o un'indicazione del fatto che tali account utente potrebbero essere intaccati o compromessi.

Ad esempio, nell'immagine seguente, l'aria ha identificato indicatori di compromesso e anomalie basate su una nuova regola di posta in arrivo che è stata creata. Ulteriori dettagli (prova) dell'indagine sono disponibili tramite visualizzazioni dettagliate all'interno di questa scheda. Gli indicatori di compromesso e anomalie possono includere anche rilevamenti di anomalie da [Microsoft cloud app Security](https://docs.microsoft.com/cloud-app-security).

![Pagina utenti di analisi AEREa](../../media/air-investigationuserspage.png)

È possibile:

- Ottenere una panoramica visiva dei risultati e dei rischi individuati dall'utente.

- Selezionare un utente per l'apertura di una pagina di fly-out che Visualizza i dettagli degli avvisi completi.

### <a name="machine-investigation"></a>Indagine del computer

Nella scheda **computer** , è possibile visualizzare tutti i computer identificati come parte dell'indagine.

![Pagina macchina dell'analisi aerea](../../media/air-investigationmachinepage.png)

Come parte di alcuni PlayBook, AIR correla le minacce alla posta elettronica ai dispositivi (ad esempio, malware con zapping). Ad esempio, un'analisi passa un hash di file dannosi a [Microsoft Defender per endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection
) da esaminare. Questo consente l'analisi automatizzata delle macchine rilevanti per gli utenti, per garantire che le minacce vengano affrontate sia nel cloud che negli endpoint.

È possibile:

- Ottenere una panoramica visiva dei computer e delle minacce correnti trovati.

- Selezionare un computer per aprire una visualizzazione che si riferisce alle [indagini Microsoft Defender per endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations) in Microsoft Defender Security Center.

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

### <a name="recommended-actions"></a>Azioni consigliate

Nella scheda **azioni** , è possibile visualizzare tutte le azioni di PlayBook consigliate per la correzione dopo il completamento dell'indagine. Azioni acquisire i passaggi consigliati da Microsoft al termine di un'indagine. È possibile eseguire le azioni di correzione selezionando una o più azioni.

Selezionando **approva** è possibile iniziare la correzione. (Sono necessarie autorizzazioni appropriate: il ruolo di **ricerca ed eliminazione** è necessario per eseguire azioni da Esplora risorse e dall'aria).

Ad esempio, un lettore di sicurezza è in grado di visualizzare le azioni, ma non di approvarle.

> [!IMPORTANT]
> Non è necessario approvare ogni azione. Se non si è d'accordo con l'azione consigliata o l'organizzazione non sceglie alcuni tipi di azioni, è possibile scegliere di **rifiutare** le azioni o semplicemente ignorarle e non intraprendere alcuna azione.
> L'approvazione e/o il rifiuto di tutte le azioni consente di chiudere completamente l'indagine (lo stato viene ripristinato), lasciando inalterate alcune azioni allo stato dell'inchiesta che cambia in uno stato parzialmente rimediato.

![Pagina azione indagini AEREe](../../media/air-investigationactionspage.png)

È possibile:

- Ottenere una panoramica visiva delle azioni consigliate in PlayBook.
- Selezionare una singola azione o più azioni.
- Approvare o rifiutare le azioni consigliate con i commenti.
- Esportare i risultati in un file CSV.
- Filtrare la visualizzazione.

## <a name="next-steps"></a>Passaggi successivi

- [Esaminare e approvare le azioni in sospeso](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions)
