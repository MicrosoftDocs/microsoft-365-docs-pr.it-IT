---
title: Traccia messaggio nel Centro sicurezza e conformità
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 3e64f99d-ac33-4aba-91c5-9cb4ca476803
description: Gli amministratori possono utilizzare la traccia dei messaggi nel centro sicurezza & Compliance per scoprire cosa è successo ai messaggi.
ms.openlocfilehash: 12600eeb5242f0de5fc187be81b9311d4f9cb645
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635317"
---
# <a name="message-trace-in-the-security--compliance-center"></a>Traccia messaggio nel Centro sicurezza e conformità

## <a name="overview"></a>Panoramica

La traccia dei messaggi nel centro sicurezza & conformità segue i messaggi di posta elettronica durante il viaggio nell'organizzazione di Exchange Online. È possibile determinare se un messaggio è stato ricevuto, rifiutato, posticipato o recapitato dal servizio. Mostra inoltre quali azioni sono state eseguite sul messaggio prima del raggiungimento dello stato finale.

La traccia dei messaggi nel centro sicurezza & conformità migliora la traccia del messaggio originale disponibile nell'interfaccia di amministrazione di Exchange (EAC). È possibile utilizzare le informazioni contenute nella traccia dei messaggi per rispondere in modo efficiente alle domande degli utenti sull'accaduto ai messaggi, risolvere i problemi relativi al flusso di posta e convalidare le modifiche dei criteri.

> [!NOTE]
> * Per eseguire una traccia dei messaggi, è necessario essere membri del gruppo di ruoli Gestione organizzazione, gestione conformità o supporto tecnico. Per altre informazioni, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md). <br/><br/>* Il numero massimo di messaggi visualizzati nei risultati dipende dal tipo di rapporto selezionato (vedere la sezione scegliere il tipo di [report](#choose-report-type) per informazioni dettagliate). Il cmdlet [Get-HistoricalSearch](https://docs.microsoft.com/powershell/module/exchange/reporting/get-historicalsearch) in PowerShell di Exchange Online o Exchange Online Protection PowerShell restituisce tutti i messaggi nei risultati.

## <a name="open-message-trace"></a>Aprire la traccia dei messaggi

1. Aprire il Centro sicurezza & Compliance <https://protection.office.com>all'indirizzo.

2. Espande il **flusso di posta**e quindi seleziona **traccia messaggi**.

## <a name="message-trace-page"></a>Pagina di traccia dei messaggi

Da qui è possibile avviare una nuova traccia predefinita facendo clic sul pulsante **Start a Trace** . In questo modo verranno ricercati tutti i messaggi per tutti i mittenti e i destinatari negli ultimi due giorni. In alternativa, è possibile utilizzare una delle query archiviate dalle categorie di query disponibili ed eseguirle così come sono oppure utilizzarle come punti di partenza per le proprie query:

- **Query predefinite**: query incorporate fornite da Office 365.

- **Query personalizzate**: query salvate dagli amministratori dell'organizzazione per un utilizzo futuro.

- **Query autosaved**: le ultime dieci query eseguite più di recente. Questo elenco semplifica la scelta del punto in cui è stato interrotto.

Anche in questa pagina è disponibile una sezione per i **report scaricabili** per le richieste inviate, nonché i report stessi quando sono disponibili per il download.

## <a name="options-for-a-new-message-trace"></a>Opzioni per una nuova traccia dei messaggi

### <a name="filter-by-senders-and-recipients"></a>Filtrare in base a mittenti e destinatari

I valori predefiniti sono **tutti i mittenti** e **tutti i destinatari**, ma è possibile utilizzare i campi seguenti per filtrare i risultati:

- **Da queste persone**: fare clic in questo campo per selezionare uno o più mittenti dall'organizzazione. È anche possibile iniziare a digitare un nome e gli elementi nell'elenco verranno filtrati in base a ciò che è stato digitato, analogamente alla modalità di funzionamento di una pagina di ricerca.

- **A queste persone**: fare clic in questo campo per selezionare uno o più destinatari nell'organizzazione.

> [!NOTE]
> È inoltre possibile digitare gli indirizzi di posta elettronica di mittenti e destinatari esterni. I caratteri jolly sono supportati, ad esempio `*@contoso.com`, ma non è possibile utilizzare più voci con caratteri jolly nello stesso campo contemporaneamente. <br/><br/> È possibile incollare più mittenti o elenchi di destinatari separati da punti e virgola (`;`). spazi (`\s`), ritorni a`\r`capo () o righe successive`\n`().

### <a name="time-range"></a>Intervallo di tempo

Il valore predefinito è **2 giorni**, ma è possibile specificare intervalli di data/ora fino a 90 giorni. Quando si utilizzano intervalli di data/ora, prendere in considerazione i seguenti problemi:

- Per impostazione predefinita, è possibile selezionare l'intervallo di tempo in visualizzazione **Slider** utilizzando una linea temporale. È possibile selezionare solo le impostazioni giorno o ora visualizzate. Se si tenta di selezionare un valore tra i valori interattivi, la bolla iniziale/finale verrà agganciata all'impostazione visualizzata più vicina.

  ![Intervallo di tempo del dispositivo di scorrimento in una nuova traccia dei messaggi nel centro sicurezza & conformità](../../media/55a9e9c1-f7d5-4047-b217-824e8b976bcb.png)

  Tuttavia, è anche possibile passare alla visualizzazione **personalizzata** in cui è possibile specificare i valori di data e ora di **inizio** e di **fine** (incluse le ore) ed è anche possibile selezionare il **fuso orario** per l'intervallo data/ora. Si noti che l'impostazione del **fuso orario** si applica sia agli input di query sia ai risultati delle query.

  ![Un intervallo di tempo personalizzato in una nuova traccia dei messaggi nel centro sicurezza & Compliance](../../media/ed4c8d50-9ea5-4694-93f9-ee3ab6660b4f.png)

  Per 10 o meno giorni, i risultati sono disponibili istantaneamente come report **riepilogativo** . Se si specifica un intervallo di tempo pari leggermente superiore a 10 giorni, i risultati verranno posticipati perché sono disponibili solo come file CSV scaricabile ( **Riepilogo avanzato** o rapporti **estesi** ).

  Per ulteriori informazioni sui diversi tipi di report, vedere la sezione [scegliere il tipo di report](#choose-report-type) in questo argomento.

  **Nota**: i report di riepilogo e Extended Enhanced vengono preparati utilizzando i dati di traccia dei messaggi archiviati e possono richiedere fino a diverse ore prima che il report sia disponibile per il download. A seconda del numero di altri amministratori che hanno inoltrato le richieste di rapporto nello stesso momento, è possibile che si verifichi un ritardo prima dell'inizio dell'elaborazione per la richiesta in coda.

- Il salvataggio di una query in visualizzazione **Slider** consente di salvare l'intervallo di tempo relativo (ad esempio, 3 giorni da oggi). Il salvataggio di una query nella visualizzazione **personalizzata** consente di salvare l'intervallo di data/ora assoluto (ad esempio, 2018-05-06 13:00 a 2018-05-08 18:00).

### <a name="more-search-options"></a>Altre opzioni di ricerca

#### <a name="delivery-status"></a>Stato del recapito

È possibile lasciare il valore predefinito **tutti** selezionati oppure è possibile selezionare uno dei seguenti valori per filtrare i risultati:

- **Recapitato**: il messaggio è stato correttamente recapitato alla destinazione prevista.

- **In sospeso**: il recapito del messaggio viene tentato o ritentato.

- **Expanded**: un destinatario del gruppo di distribuzione è stato espanso prima del recapito ai singoli membri del gruppo.

- **Errore**: il messaggio non è stato recapitato.

- In **quarantena**: il messaggio è stato messo in quarantena (come posta indesiderata, massa o phishing). For more information, see [Quarantine email messages in Office 365](quarantine-email-messages.md).

- **Filtrato come posta indesiderata**: il messaggio è stato identificato come posta indesiderata e rifiutato o bloccato (non in quarantena).

- **Ottenere lo stato:** Il messaggio è stato ricevuto di recente da Office 365, ma non sono ancora disponibili altri dati sullo stato. Eseguire il controllo in pochi minuti.

**Nota**: i valori **in sospeso, in** **quarantena**e **filtro come posta indesiderata** sono disponibili solo per le ricerche di meno di 10 giorni. È inoltre possibile che vi sia un ritardo di 5-10 minuti tra lo stato di recapito effettivo e quello riportato.

#### <a name="message-id"></a>ID messaggio

Questo è l'ID del messaggio Internet (detto anche ID client) trovato nel campo di intestazione **Message-ID:** nell'intestazione del messaggio. Gli utenti possono fornire questo valore per esaminare i messaggi specifici.

Questo valore rimane immutato per tutta la durata del messaggio. Per i messaggi creati in Microsoft 365 o Exchange, il valore è nel formato `<GUID@ServerFQDN>`, incluse le parentesi angolari\< \>(). Ad esempio, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`. Altri sistemi di messaggistica possono utilizzare una sintassi o valori diversi. Questo valore deve essere univoco, ma non tutti i sistemi di posta elettronica seguono scrupolosamente questo requisito. Se il campo di intestazione **Message-ID:** non esiste o è vuoto per i messaggi in arrivo provenienti da origini esterne, viene assegnato un valore arbitrario.

Quando si utilizza l' **ID messaggio** per filtrare i risultati, assicurarsi di includere la stringa completa, incluse le parentesi angolari.

#### <a name="direction"></a>Direction

È possibile lasciare il valore predefinito **tutti** selezionati oppure è possibile selezionare in **ingresso** (messaggi inviati a destinatari nell'organizzazione) o in **uscita** (messaggi inviati dagli utenti dell'organizzazione) per filtrare i risultati.

#### <a name="original-client-ip-address"></a>Indirizzo IP del client originale

È possibile archiviare i risultati in base all'indirizzo IP del client per esaminare i computer compromessi che inviano grandi quantità di posta indesiderata o malware. Anche se i messaggi possono sembrare provenienti da più mittenti, è probabile che nello stesso computer vengano generati tutti i messaggi.

**Nota**: le informazioni sull'indirizzo IP del client sono disponibili solo per 10 giorni ed è disponibile solo nei rapporti di riepilogo o **Extended** **Enhanced** (file CSV scaricabili).

### <a name="choose-report-type"></a>Scegliere il tipo di rapporto

I tipi di report disponibili sono i seguenti:

- **Riepilogo**: disponibile se l'intervallo di tempo è inferiore a 10 giorni e non richiede ulteriori opzioni di filtro. I risultati sono disponibili quasi immediatamente dopo aver fatto clic su **Cerca**. Il report restituisce fino a 20000 risultati.

- **Riepilogo avanzato** o **esteso**: questi rapporti sono disponibili solo come file CSV scaricabili e richiedono una o più delle seguenti opzioni di filtro, indipendentemente dall'intervallo di tempo: **da queste persone**, **a queste persone**o all' **ID del messaggio**. È possibile utilizzare i caratteri jolly per i mittenti o i destinatari, \*ad esempio @contoso. com. Il rapporto riepilogativo avanzato restituisce fino a 50000 risultati. Il report esteso restituisce fino a 1000 risultati.

**Note**:

- Il riepilogo avanzato e i report estesi vengono preparati utilizzando i dati di traccia dei messaggi archiviati e possono richiedere fino a diverse ore prima che il report sia disponibile per il download. A seconda del numero di altri amministratori che hanno inoltrato le richieste di rapporto nello stesso momento, è possibile che si verifichi un ritardo prima che la richiesta in coda inizi a essere elaborata.

- Anche se è possibile selezionare un riepilogo avanzato o un report esteso per qualsiasi intervallo di data/ora, in genere le ultime quattro ore di dati archiviati non saranno ancora disponibili per questi due tipi di report.

Quando si fa clic su **Avanti**, viene visualizzata una pagina di riepilogo in cui sono elencate le opzioni di filtro selezionate, un titolo univoco (modificabile) per il report e l'indirizzo di posta elettronica che riceve la notifica al termine della traccia del messaggio (modificabile anche e deve trovarsi in uno dei domini accettati dell'organizzazione). Fare clic su **prepara rapporto** per inviare la traccia dei messaggi. Nella pagina di **traccia dei messaggi** principale, è possibile visualizzare lo stato del report nella sezione **report scaricabili** .

Per ulteriori informazioni sulle informazioni restituite nei diversi tipi di report, vedere la sezione successiva.

## <a name="message-trace-results"></a>Risultati della traccia dei messaggi

I diversi tipi di report restituiscono livelli di informazioni diversi. Le informazioni disponibili nei diversi rapporti sono descritte nelle sezioni seguenti.

### <a name="summary-report-output"></a>Output del rapporto riepilogativo

Dopo aver eseguito la traccia dei messaggi, i risultati verranno elencati, ordinati in base alla data/ora decrescente (la più recente è la prima).

![Risultati del rapporto riepilogativo per la traccia dei messaggi nel centro sicurezza & Compliance](../../media/0664bafe-0b03-477b-b571-0b046ac8c977.png)

Il rapporto riepilogativo contiene le informazioni seguenti:

- **Data**: la data e l'ora in cui il messaggio è stato ricevuto dal servizio, utilizzando il fuso orario UTC configurato.

- **Sender**: l'indirizzo di posta elettronica del mittente (*dominio**alias*@).

- **Destinatario**: l'indirizzo di posta elettronica del destinatario o dei destinatari. Per un messaggio inviato a più destinatari, è presente una riga per ogni destinatario. Se il destinatario è un gruppo di distribuzione, un gruppo di distribuzione dinamico o un gruppo di sicurezza abilitato alla posta elettronica, il gruppo sarà il primo destinatario e quindi ogni membro del gruppo si trova su una riga distinta.

- **Subject**: i primi 256 caratteri del campo **Subject:** del messaggio.

- **Stato**: questi valori sono descritti nella sezione [stato di recapito](#delivery-status) .

Per impostazione predefinita, i primi risultati di 250 sono caricati e prontamente disponibili. Quando si scorre verso il basso, si verifica una leggera pausa quando viene caricato il prossimo batch di risultati. Invece di scorrere, è possibile fare clic su **carica tutto** per caricare tutti i risultati fino a un massimo di 10.000.

È possibile fare clic sulle intestazioni di colonna per ordinare i risultati in base ai valori della colonna in ordine crescente o decrescente.

È possibile fare clic su **Filtra risultati** per filtrare i risultati in base a una o più colonne.

È possibile esportare i risultati dopo aver selezionato una o più righe facendo clic su **Esporta risultati** e quindi selezionando **Esporta tutti**i risultati, **Esporta i risultati caricati**o **Esporta selezionati**.

#### <a name="find-related-records-for-this-message"></a>Individuare i record correlati per il messaggio

I record dei messaggi correlati sono record che condividono lo stesso ID messaggio. Tenere presente che anche un singolo messaggio inviato tra due persone può generare più record. Il numero di record aumenta quando il messaggio viene influenzato dall'espansione del gruppo di distribuzione, dall'inoltro, dalle regole del flusso di posta (note anche come regole di trasporto) e così via.

Dopo aver selezionato la casella di controllo di una riga, è possibile trovare i record correlati per il messaggio facendo clic sul pulsante **trova correlato** visualizzato oppure selezionando **altre opzioni** ![ulteriori](../../media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **record correlati per il messaggio**.

Per ulteriori informazioni sull'ID del messaggio, vedere la sezione relativa all'ID del messaggio descritta in precedenza in questo argomento.

#### <a name="message-trace-details"></a>Dettagli di traccia dei messaggi

Nell'output del rapporto riepilogativo, è possibile visualizzare i dettagli relativi a un messaggio utilizzando uno dei metodi seguenti:

- Selezionare la riga (fare clic in un punto qualsiasi della riga tranne la casella di controllo).

- Selezionare la casella di controllo della riga e fare clic su](../../media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **altre opzioni** ![per **visualizzare i dettagli dei messaggi**.

   ![Dettagli dopo aver fatto doppio clic su una riga del rapporto riepilogativo risultati traccia messaggio nel centro sicurezza & conformità](../../media/e50ee7cd-810a-4c06-8b58-e56ffd7028d1.png)

I dettagli della traccia dei messaggi contengono le informazioni aggiuntive seguenti che non sono presenti nel rapporto riepilogativo:

- **Eventi messaggio**: questa sezione contiene classificazioni che consentono di categorizzare le azioni che il servizio assume sui messaggi. **Alcuni degli eventi più interessanti** che è possibile riscontrare sono:

  - **Receive**: il messaggio è stato ricevuto dal servizio.

  - **Send**: il messaggio è stato inviato dal servizio.

  - **Esito negativo**: il messaggio non è stato recapitato.

  - **Recapita**: il messaggio è stato recapitato a una cassetta postale.

  - **Expand**: il messaggio è stato inviato a un gruppo di distribuzione espanso.

  - **Trasferimento**: i destinatari sono stati spostati in un messaggio di biforcati a causa della conversione del contenuto, dei limiti del destinatario del messaggio o degli agenti.

  - **Posticipare**: il recapito del messaggio è stato posticipato e potrebbe essere ritentato in un secondo momento.

  - **Risolto**: il messaggio è stato reindirizzato a un nuovo indirizzo del destinatario basato su una ricerca di Active Directory. In questo caso, l'indirizzo originale del destinatario verrà visualizzato in una riga separata nella traccia del messaggio insieme allo stato di consegna finale per il messaggio.

  Note:

  - Un messaggio non movimentato che è stato recapitato correttamente genererà più voci di **evento** nella traccia dei messaggi.

  - Questo elenco non è inteso come esaustivo. Per le descrizioni di altri eventi, vedere [tipi di evento nel registro di verifica messaggi](https://docs.microsoft.com/Exchange/mail-flow/transport-logs/message-tracking#event-types-in-the-message-tracking-log). Si noti che questo collegamento è un argomento del server Exchange (Exchange locale).

- **Ulteriori informazioni**: questa sezione contiene i seguenti dettagli:

  - **ID messaggio**: questo valore è descritto nella sezione [ID messaggio](#message-id) descritta in precedenza in questo argomento. Ad esempio, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.

  - **Dimensione messaggio**

  - **Da IP**: l'indirizzo IP del computer in cui è stato inviato il messaggio. Per i messaggi in uscita inviati da Exchange Online, il valore è vuoto.

  - **To IP**: l'indirizzo IP o gli indirizzi in cui il servizio ha tentato di recapitare il messaggio. Se il messaggio contiene più destinatari, vengono visualizzati. Per i messaggi in ingresso inviati a Exchange Online, il valore è vuoto.

### <a name="enhanced-summary-reports"></a>Rapporti di riepilogo avanzati

I report di riepilogo avanzati disponibili (completati) sono disponibili nella sezione **report scaricabili** all'inizio della traccia dei messaggi. Nel report sono disponibili le informazioni seguenti:

- **origin_timestamp**<sup>*</sup>: la data e l'ora in cui il messaggio è stato ricevuto inizialmente dal servizio, utilizzando il fuso orario UTC configurato.

- **sender_address**: l'indirizzo di posta elettronica del mittente (*dominio**alias*@).

- **Recipient_status**: lo stato del recapito del messaggio al destinatario. Se il messaggio è stato inviato a più destinatari, mostrerà tutti i destinatari e lo stato corrispondente per ognuno, nel formato: \<*stato*\>dell' *Indirizzo*\>##\<di posta elettronica. Ad esempio:

  - **# #Receive, Send** indica che il messaggio è stato ricevuto dal servizio e che è stato inviato alla destinazione desiderata.

  - **# #Receive, Fail** indica che il messaggio è stato ricevuto dal servizio ma il recapito alla destinazione desiderata non è riuscito.

  - **# #Receive, Deliver** indica che il messaggio è stato ricevuto dal servizio e che è stato recapitato alla cassetta postale del destinatario.

- **MESSAGE_SUBJECT**: i primi 256 caratteri del campo **Subject** del messaggio.

- **total_bytes**: la dimensione del messaggio in byte, inclusi gli allegati.

- **message_id**: questo valore è descritto nella sezione [ID messaggio](#message-id) descritta in precedenza in questo argomento. Ad esempio, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.

- **network_message_id**: un valore di ID messaggio univoco che persiste in tutte le copie del messaggio che potrebbe essere creato a causa della biforcazione o dell'espansione del gruppo di distribuzione. Un valore di esempio `1341ac7b13fb42ab4d4408cf7f55890f`è.

- **original_client_ip**: l'indirizzo IP del client del mittente.

- **direzionalità**: indica se il messaggio è stato inviato all'interno (1) all'organizzazione o se è stato inviato in uscita (2) dall'organizzazione.

- **connector_id**: il nome del connettore di origine o di destinazione. Per ulteriori informazioni sui connettori in Exchange Online, vedere [Configure Mail Flow using Connectors in Office 365](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).

- **delivery_priority**<sup>*</sup>: indica se il messaggio è stato inviato con priorità **alta**, **bassa**o **normale** .

<sup>*</sup>Queste proprietà sono disponibili solo in rapporti di riepilogo avanzati.

### <a name="extended-reports"></a>Rapporti estesi

I report estesi disponibili (completati) sono disponibili nella sezione **report scaricabili** all'inizio della traccia dei messaggi. Quasi tutte le informazioni provenienti da un rapporto riepilogativo avanzato sono disponibili in un report esteso (ad eccezione di **origin_timestamp** e **delivery_priority**). Le informazioni aggiuntive seguenti sono disponibili solo in un report esteso:

- **Client_IP**: l'indirizzo IP del server di posta elettronica o del client di messaggistica che ha inviato il messaggio.

- **client_hostname**: il nome host o FQDN del server di posta elettronica o del client di messaggistica che ha inviato il messaggio.

- **server_ip**: l'indirizzo IP del server di origine o di destinazione.

- **server_hostname**: il nome host o FQDN del server di destinazione.

- **source_context**: informazioni aggiuntive associate al campo di **origine** . Ad esempio:

  - `Protocol Filter Agent`

  - `3489061114359050000`

- **origine**: componente di Exchange Online responsabile dell'evento. Ad esempio:

  - `AGENT`

  - `MAILBOXRULE`

  - `SMTP`

- **event_id**: corrispondono ai valori di **evento del messaggio** illustrati nella sezione [trova i record correlati per questo messaggio](#find-related-records-for-this-message) .

- **internal_message_id**: un identificatore del messaggio assegnato dal server Exchange Online che sta attualmente elaborando il messaggio.

- **recipient_address**: gli indirizzi di posta elettronica dei destinatari del messaggio. Gli indirizzi di posta elettronica multipli sono separati dal carattere punto e virgola (;).

- **recipient_count**: il numero totale di destinatari nel messaggio.

- **related_recipient_address**: utilizzato con `EXPAND`, `REDIRECT`ed `RESOLVE` eventi per visualizzare gli altri indirizzi di posta elettronica dei destinatari associati al messaggio.

- **riferimento**: questo campo contiene informazioni aggiuntive per tipi specifici di eventi. Ad esempio:

  - **DSN**: contiene il collegamento al rapporto, che corrisponde al valore **message_id** della notifica sullo stato del recapito associato (noto anche come DSN, rapporto di mancato recapito, NDR o messaggio di rimbalzo) se un DSN viene generato dopo questo evento. Se si tratta di un messaggio DSN, questo campo contiene il valore **message_id** del messaggio originale per il quale è stato generato il DSN.

  - **Expand**: contiene il valore **related_recipient_address** dei messaggi correlati.

  - **Receive**: potrebbe contenere il valore **message_id** del messaggio correlato se il messaggio è stato generato da altri processi, ad esempio le regole di posta in arrivo.

  - **Send**: contiene il valore **internal_message_id** di tutti i messaggi DSN.

  - **Transfer**: contiene il valore **internal_message_id** del messaggio in fase di fork (ad esempio, tramite la conversione del contenuto, i limiti del destinatario del messaggio o gli agenti).

  - **MAILBOXRULE**: contiene il valore **internal_message_id** del messaggio in ingresso che ha causato la generazione del messaggio in uscita da parte della regola di posta in arrivo.

    Per altri tipi di eventi, questo campo in genere è vuoto.

- **return_path**: l'indirizzo di posta elettronica restituito specificato dal comando **mail from** che ha inviato il messaggio. Anche se questo campo non è mai vuoto, può avere il valore dell'indirizzo mittente nullo rappresentato come `<>`.

- **message_info**: informazioni aggiuntive sul messaggio. Ad esempio:

  - Data-ora di origine del messaggio in formato UTC `DELIVER` per `SEND` gli eventi e. La data-ora di origination è l'ora in cui il messaggio è stato immesso per la prima volta nell'organizzazione di Exchange Online. La data e l'ora UTC sono rappresentate nel formato data/ora ISO 8601 `yyyy-mm-ddThh:mm:ss.fffZ`:, `yyyy` dove = anno `mm` , = mese `dd` , = giorno `T` , indica l'inizio del componente tempo, `hh` = ora, `mm` = minuto, `ss` = secondo, `fff` = frazioni di secondo e `Z` significa `Zulu`, che è un altro modo per indicare UTC.

  - Errori di autenticazione. Ad esempio, è possibile visualizzare il valore `11a` e il tipo di autenticazione utilizzato quando si è verificato l'errore di autenticazione.

- **tenant_id**: valore GUID che rappresenta l'organizzazione di Exchange Online (ad esempio, `39238e87-b5ab-4ef6-a559-af54c6b07b42`).

- **original_server_ip**: l'indirizzo IP del server originale.

- **custom_data**: contiene i dati relativi a tipi di evento specifici. Per ulteriori informazioni, vedere le sezioni seguenti.

#### <a name="custom_data-values"></a>custom_data valori

Il campo **custom_data** di un `AGENTINFO` evento viene utilizzato da una vasta gamma di agenti di Exchange Online per registrare i dettagli di elaborazione dei messaggi. Alcuni degli agenti più interessanti sono descritti nelle sezioni seguenti.

#### <a name="spam-filter-agent"></a>Agente filtro posta indesiderata

Un valore **custom_data** che inizia con `S:SFA` è dall'agente filtro posta indesiderata. I dettagli della chiave sono descritti nella tabella seguente:

|**Valore**|**Descrizione**|
|:-----|:-----|
|`SFV=NSPM`|Il messaggio è stato contrassegnato come non indesiderato ed è stato inviato al destinatario.|
|`SFV=SPM`|Il messaggio è stato contrassegnato come posta indesiderata dal filtro contenuto.|
|`SFV=BLK`|Le regole del filtro sono state ignorate e il messaggio è stato bloccato perché è stato originato da un mittente bloccato.|
|`SFV=SKS`|Il messaggio è stato contrassegnato come posta indesiderata prima di essere elaborato dal filtro contenuto. Questo include i messaggi che corrispondono alle regole di trasporto, che lo contrassegnano automaticamente come indesiderato e che ignorano tutte le regole del filtro aggiuntive.|
|`SCL=<number>`|Per ulteriori informazioni sui diversi valori SCL e sul loro significato, vedere [Spam Confidence levels](spam-confidence-levels.md).|
|`PCL=<number>`|Il valore del livello di confidenza di Phishing (PCL) del messaggio. Questi possono essere interpretati nello stesso modo in cui i valori SCL sono documentati nei [livelli di probabilità di posta indesiderata](spam-confidence-levels.md).|
|`DI=SB`|Il mittente del messaggio è stato bloccato.|
|`DI=SQ`|Il messaggio è stato messo in quarantena.|
|`DI=SD`|Il messaggio è stato eliminato.|
|`DI=SJ`|Il messaggio è stato inviato alla cartella posta indesiderata del destinatario.|
|`DI=SN`|Il messaggio è stato instradato tramite un pool di recapito ad alto rischio.|
|`DI=SO`|Il messaggio è instradato attraverso un pool di recapito ad alto rischio. Per ulteriori informazioni, vedere [pool di recapito ad alto rischio per i messaggi in uscita](high-risk-delivery-pool-for-outbound-messages.md).|
|`SFS=[a]|SFS=[b]`|Indica una corrispondenza tra le regole relative alla posta indesiderata.|
|`IPV=CAL`|Il messaggio è stato consentito tramite il filtro da posta indesiderata poiché l'indirizzo IP è stato specificato in un elenco di indirizzi IP bloccati nel filtro di connessione.|
|`H=<EHLOstring>`|Stringa HELO o EHLO del server della posta connesso.|
|`PTR=<ReverseDNS>`|Il record PTR dell'indirizzo IP di invio, anche noto come indirizzo DNS inverso.|

Un esempio **custom_data** valore per un messaggio filtrato per la posta indesiderata in questo modo:

`S:SFA=SUM|SFV=SPM|IPV=CAL|SRV=BULK|SFS=470454002|SFS=349001|SCL=9|SCORE=-1|LIST=0|DI=SN|RD=ftmail.inc.com|H=ftmail.inc.com|CIP=98.129.140.74|SFP=1501|ASF=1|CTRY=US|CLTCTRY=|LANG=en|LAT=287|LAT=260|LAT=18;`

#### <a name="malware-filter-agent"></a>Agente filtro antimalware

Un valore **custom_data** che inizia con `S:AMA` l'agente di filtro antimalware. I dettagli della chiave sono descritti nella tabella seguente:

|**Valore**|**Descrizione**|
|:-----|:-----|
|`AMA=SUM|v=1|`o`AMA=EV|v=1`|È stato determinato che il messaggio contiene malware. `SUM`indica che il malware potrebbe essere stato rilevato da un numero qualsiasi di motori. `EV`indica che il malware è stato rilevato da un motore specifico. Quando viene rilevato malware da un motore, questo attiva le seguenti azioni.|
|`Action=r`|Il messaggio è stato sostituito.|
|`Action=p`|Il messaggio è stato ignorato.|
|`Action=d`|Il messaggio è stato rinviato.|
|`Action=s`|Il messaggio è stato eliminato.|
|`Action=st`|Il messaggio è stato ignorato.|
|`Action=sy`|Il messaggio è stato ignorato.|
|`Action=ni`|Il messaggio è stato rifiutato.|
|`Action=ne`|Il messaggio è stato rifiutato.|
|`Action=b`|Il messaggio è stato bloccato.|
|`Name=<malware>`|Il nome del malware rilevato.|
|`File=<filename>`|Il nome del file che contiene malware.|

Un esempio di **custom_data** valore per un messaggio che contiene malware è simile al seguente:

`S:AMA=SUM|v=1|action=b|error=|atch=1;S:AMA=EV|engine=M|v=1|sig=1.155.974.0|name=DOS/Test_File|file=filename;S:AMA=EV|engine=A|v=1|sig=201707282038|name=Test_File|file=filename`

#### <a name="transport-rule-agent"></a>Agente delle regole di trasporto

Un valore **custom_data** che inizia con`S:TRA` è l'agente della regola di trasporto per le regole del flusso di posta (note anche come regole di trasporto). I dettagli della chiave sono descritti nella tabella seguente:

|**Valore**|**Descrizione**|
|:-----|:-----|
|`ETR|ruleId=<guid>`|L'ID regola corrispondente.|
|`St=<datetime>`|Data e ora in formato UTC quando si è verificata la corrispondenza della regola.|
|`Action=<ActionDefinition>`|L'azione che è stata applicata. Per un elenco delle azioni disponibili, vedere [Mail Flow Rule Actions in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).|
|`Mode=<Mode>`|La modalità della regola. I valori validi sono: <br/>* **Enforce**: tutte le azioni della regola verranno applicate. <br/>* **Test con suggerimenti per i criteri:**: tutte le azioni di suggerimento per i criteri verranno inviate, ma non verranno applicate altre azioni di applicazione. <br/>* **Test senza suggerimenti**per i criteri: le azioni verranno elencate in un file di registro, tuttavia i mittenti non riceveranno alcuna notifica e le azioni di applicazione non verranno applicate.|

Un esempio di **custom_data** valore per i messaggi che soddisfano le condizioni di una regola del flusso di posta è simile al seguente:

`S:TRA=ETR|ruleId=19a25eb2-3e43-4896-ad9e-47b6c359779d|st=7/17/2017 12:31:25 AM|action=ApplyHtmlDisclaimer|sev=1|mode=Enforce`
