---
title: Traccia messaggio nel Centro sicurezza e conformità
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 3e64f99d-ac33-4aba-91c5-9cb4ca476803
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori possono usare la traccia dei messaggi nel Centro sicurezza & conformità per scoprire cosa è successo ai messaggi.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 292c59563d0fd42da62cb071e07d19f545f5eb20
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274473"
---
# <a name="message-trace-in-the-security--compliance-center"></a>Traccia messaggio nel Centro sicurezza e conformità

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

La traccia dei messaggi nel Centro sicurezza & conformità segue i messaggi di posta elettronica mentre viaggiano nell'organizzazione di Exchange Online. È possibile determinare se un messaggio è stato ricevuto, rifiutato, rinviato o recapitato dal servizio. Mostra inoltre quali azioni sono state eseguite sul messaggio prima del raggiungimento dello stato finale.

È possibile utilizzare le informazioni dalla traccia dei messaggi per rispondere in modo efficiente alle domande degli utenti su cosa è successo ai messaggi, risolvere i problemi relativi al flusso di posta e convalidare le modifiche ai criteri.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare?

- Per utilizzare la traccia dei **messaggi,** è necessario essere membri dei gruppi di ruoli **Gestione** organizzazione, Gestione conformità o Help **Desk** in **Exchange Online.** Per ulteriori informazioni, vedere [Autorizzazioni in Exchange Online](/exchange/permissions-exo/permissions-exo).

  **Note:** l'appartenenza al ruolo di Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft 365 offre agli utenti le autorizzazioni e le autorizzazioni necessarie per altre funzionalità di Microsoft 365.  Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).

- Il numero massimo di messaggi visualizzati nei risultati di una traccia dei messaggi dipende dal tipo di rapporto selezionato (per informazioni dettagliate, vedere la sezione [Scegliere](#choose-report-type) il tipo di report). Il cmdlet [Get-HistoricalSearch](/powershell/module/exchange/get-historicalsearch) in PowerShell di Exchange Online o PowerShell EOP autonomo restituisce tutti i messaggi nei risultati.

## <a name="open-message-trace"></a>Apri traccia messaggio

Aprire il Centro sicurezza & conformità in e quindi passare <https://protection.office.com/> a Flusso di **posta** \> **Traccia messaggio**.

Per passare direttamente alla **pagina Traccia messaggio,** aprire <https://protection.office.com/messagetrace> .

## <a name="message-trace-page"></a>Pagina di traccia dei messaggi

Da qui è possibile avviare una nuova traccia predefinita facendo clic sul **pulsante Avvia traccia.** Verranno cercati tutti i messaggi per tutti i mittenti e i destinatari degli ultimi due giorni. Oppure è possibile utilizzare una delle query archiviate delle categorie di query disponibili ed eseguirle così come sono oppure utilizzarle come punti di partenza per le proprie query:

- **Query predefinite**: query predefinite fornite da Microsoft 365.
- **Query personalizzate**: query salvate dagli amministratori dell'organizzazione per un utilizzo futuro.
- **Query salvate automaticamente**: le ultime dieci query eseguite più di recente. Questo elenco semplifica il prelievo da dove è stato lasciato.

In questa pagina è **inoltre** disponibile una sezione Report scaricabili per le richieste inviate e i report stessi quando sono disponibili per il download.

## <a name="options-for-a-new-message-trace"></a>Opzioni per una nuova traccia dei messaggi

### <a name="filter-by-senders-and-recipients"></a>Filtro in base a mittenti e destinatari

I valori predefiniti sono **Tutti i mittenti** e **Tutti i** destinatari, ma è possibile utilizzare i campi seguenti per filtrare i risultati:

- **Da queste persone:** fare clic in questo campo per selezionare uno o più mittenti dall'organizzazione. Puoi anche iniziare a digitare un nome e gli elementi nell'elenco verranno filtrati in base a ciò che hai digitato, in modo simile al comportamento di una pagina di ricerca.
- **A queste persone:** fare clic in questo campo per selezionare uno o più destinatari nell'organizzazione.

> [!NOTE]
>
> - È inoltre possibile digitare gli indirizzi di posta elettronica di mittenti e destinatari esterni. I caratteri jolly sono supportati (ad esempio, ), ma non è possibile utilizzare più voci contemporaneamente nello `*@contoso.com` stesso campo.
> - È possibile incollare più mittenti o elenchi di destinatari separati da punto e virgola ( `;` ). spazi ( `\s` ), ritorni a capo ( `\r` ) o righe seguenti ( `\n` ).

### <a name="time-range"></a>Intervallo di tempo

Il valore predefinito è **2 giorni,** ma è possibile specificare intervalli di data/ora fino a 90 giorni. Quando si utilizzano intervalli di data/ora, considerare questi problemi:

- Per impostazione predefinita, puoi selezionare l'intervallo di tempo nella **visualizzazione Dispositivo di** scorrimento usando una linea temporale. È possibile selezionare solo le impostazioni relative al giorno o all'ora visualizzate. Se si tenta di selezionare un valore in mezzo, la bolla iniziale/finale verrà agganciata all'impostazione visualizzata più vicina.

  ![Intervallo di tempo dispositivo di scorrimento in una nuova traccia dei messaggi nel Centro sicurezza & conformità](../../media/55a9e9c1-f7d5-4047-b217-824e8b976bcb.png)

  Tuttavia, è anche  possibile passare alla visualizzazione personalizzata  in cui è possibile specificare i valori  data inizio e data di fine (incluse le ore) ed è anche possibile selezionare il fuso orario per l'intervallo di data/ora.  Si noti che **l'impostazione Fuso** orario si applica sia agli input di query che ai risultati della query.

  ![Un intervallo di tempo personalizzato in una nuova traccia dei messaggi nel Centro sicurezza & conformità](../../media/ed4c8d50-9ea5-4694-93f9-ee3ab6660b4f.png)

  Per 10 giorni o meno, i risultati sono immediatamente disponibili come rapporto **di** riepilogo. Se si specifica un intervallo di tempo anche leggermente superiore a 10 giorni, i risultati verranno posticipati perché sono disponibili solo come file CSV scaricabile **(** riepilogo avanzato o report **estesi).**

  Per ulteriori informazioni sui diversi tipi di report, vedere la [sezione Scegliere](#choose-report-type) il tipo di report in questo articolo.

  > [!NOTE]
  > Il riepilogo avanzato e i report estesi vengono preparati utilizzando i dati di traccia dei messaggi archiviati e possono essere richieste fino a diverse ore prima che il report sia disponibile per il download. A seconda del numero di altri amministratori che hanno inviato richieste di report nello stesso momento, potresti anche notare un ritardo prima dell'inizio dell'elaborazione per la richiesta in coda.

- Il salvataggio di una query in **visualizzazione Dispositivo** di scorrimento consente di risparmiare l'intervallo di tempo relativo, ad esempio 3 giorni da oggi. Il salvataggio di una query **in** visualizzazione personalizzata consente di salvare l'intervallo di data/ora assoluto, ad esempio 2018-05-06 13.00- 2018-05-08 18:00.

### <a name="more-search-options"></a>Altre opzioni di ricerca

#### <a name="delivery-status"></a>Stato del recapito

È possibile lasciare selezionato il valore predefinito **Tutti** oppure selezionare uno dei valori seguenti per filtrare i risultati:

- **Recapitato**: il messaggio è stato recapitato correttamente alla destinazione prevista.
- **In** sospeso: tentativo o tentativo di recapito del messaggio.
- **Espanso**: un destinatario del gruppo di distribuzione è stato espanso prima del recapito ai singoli membri del gruppo.
- **Failed**: Il messaggio non è stato recapitato.
- **In quarantena:** il messaggio è stato messo in quarantena (come posta indesiderata, posta in blocco o phishing). Per ulteriori informazioni, vedere [Quarantined email messages in EOP](quarantine-email-messages.md).
- **Filtrato come posta indesiderata**: il messaggio è stato identificato come posta indesiderata ed è stato rifiutato o bloccato (non in quarantena).
- **Ottenere lo stato:** Il messaggio è stato ricevuto di recente da Microsoft 365, ma non sono ancora disponibili altri dati sullo stato. Eseguire il check back in pochi minuti.

> [!NOTE]
> I valori **In sospeso,** **In** quarantena e Filtro **come posta** indesiderata sono disponibili solo per le ricerche di meno di 10 giorni. Potrebbe inoltre verificarsi un ritardo di 5-10 minuti tra lo stato di recapito effettivo e quello segnalato.

#### <a name="message-id"></a>ID messaggio

Questo è l'ID del messaggio Internet (noto anche come ID client) che si trova nel campo di intestazione **Message-ID:** nell'intestazione del messaggio. Gli utenti possono fornire questo valore per analizzare messaggi specifici.

Questo valore rimane immutato per tutta la durata del messaggio. Per i messaggi creati in Microsoft 365 o Exchange, il valore è nel formato , incluse `<GUID@ServerFQDN>` le parentesi angolari ( \< \> ). Ad esempio, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`. Altri sistemi di messaggistica potrebbero utilizzare valori o sintassi diversi. Questo valore deve essere univoco, ma non tutti i sistemi di posta elettronica seguono rigorosamente questo requisito. Se il **campo di intestazione Message-ID:** non esiste o è vuoto per i messaggi in arrivo da origini esterne, viene assegnato un valore arbitrario.

Quando si utilizza **l'ID** messaggio per filtrare i risultati, assicurarsi di includere la stringa completa, incluse le parentesi angolari.

#### <a name="direction"></a>Direction

È possibile lasciare selezionato il valore predefinito **Tutti** oppure selezionare **In ingresso** (messaggi inviati ai destinatari nell'organizzazione) o In uscita **(messaggi** inviati dagli utenti dell'organizzazione) per filtrare i risultati.

#### <a name="original-client-ip-address"></a>Indirizzo IP del client originale

È possibile inviare i risultati in base all'indirizzo IP del client per analizzare i computer compromessi che inviano grandi quantità di posta indesiderata o malware. Anche se i messaggi potrebbero sembrare provenienti da più mittenti, è probabile che lo stesso computer generi tutti i messaggi.

> [!NOTE]
> Le informazioni sull'indirizzo IP del client sono disponibili solo  per 10 giorni ed è disponibile solo nel riepilogo avanzato o nei report estesi (file CSV scaricabili). 

### <a name="choose-report-type"></a>Scegliere il tipo di report

I tipi di report disponibili sono:

- **Riepilogo:** disponibile se l'intervallo di tempo è inferiore a 10 giorni e non richiede opzioni di filtro aggiuntive. I risultati sono disponibili quasi immediatamente dopo aver fatto clic su **Cerca.** Il report restituisce fino a 20000 risultati.
- **Riepilogo avanzato** **o** Esteso: questi report sono disponibili solo come file CSV scaricabili e richiedono una o più delle opzioni di filtro seguenti indipendentemente dall'intervallo di **tempo:** Da queste **persone,** A queste persone o **ID messaggio.** È possibile utilizzare caratteri jolly per i mittenti o i destinatari , ad esempio \* @contoso.com. Il rapporto riepilogativo avanzato restituisce fino a 50000 risultati. Il report esteso restituisce fino a 1000 risultati.

> [!NOTE]
>
> - Il riepilogo avanzato e i report estesi vengono preparati utilizzando i dati di traccia dei messaggi archiviati e il download del report può richiedere fino a diverse ore. A seconda del numero di altri amministratori che hanno inviato richieste di report nello stesso momento, potresti anche notare un ritardo prima che la richiesta in coda inizi a essere elaborata.
> - Sebbene sia possibile selezionare un riepilogo avanzato o un report esteso per qualsiasi intervallo di data/ora, in genere le ultime quattro ore di dati archiviati non saranno ancora disponibili per questi due tipi di report.
> - La dimensione massima per un report scaricabile è 500 MB. Se un report scaricabile supera i 500 MB, non è possibile aprire il report in Excel o blocco note.

Quando si fa clic su Avanti **,** viene visualizzata una pagina di riepilogo in cui sono elencate le opzioni di filtro selezionate, un titolo univoco (modificabile) per il report e l'indirizzo di posta elettronica che riceve la notifica al termine della traccia del messaggio (modificabile e deve essere in uno dei domini accettati dell'organizzazione). Fare **clic su Prepara report** per inviare la traccia del messaggio. Nella pagina **principale Traccia messaggi** è possibile visualizzare lo stato del report nella sezione Report **scaricabili.**

Per ulteriori informazioni sulle informazioni restituite nei diversi tipi di report, vedere la sezione successiva.

## <a name="message-trace-results"></a>Risultati di traccia dei messaggi

I diversi tipi di report restituiscono diversi livelli di informazioni. Le informazioni disponibili nei diversi report sono descritte nelle sezioni seguenti.

### <a name="summary-report-output"></a>Output rapporto riepilogativo

Dopo aver eseguito la traccia dei messaggi, i risultati verranno elencati, ordinati in base alla data/ora decrescente (la prima più recente).

![Risultati del rapporto riepilogativo per la traccia dei messaggi nel Centro sicurezza & conformità](../../media/0664bafe-0b03-477b-b571-0b046ac8c977.png)

Il rapporto riepilogativo contiene le informazioni seguenti:

- **Date**: data e ora in cui il messaggio è stato ricevuto dal servizio, utilizzando il fuso orario UTC configurato.
- **Sender**: Indirizzo di posta elettronica del mittente (*dominio alias* @ ).
- **Destinatario**: indirizzo di posta elettronica del destinatario o dei destinatari. Per un messaggio inviato a più destinatari, è presente una riga per destinatario. Se il destinatario è un gruppo di distribuzione, un gruppo di distribuzione dinamico o un gruppo di sicurezza abilitato alla posta elettronica, il gruppo sarà il primo destinatario e quindi ogni membro del gruppo si trova su una riga separata.
- **Subject**: I primi 256 caratteri del campo **Subject:** del messaggio.
- **Stato**: questi valori sono descritti nella [sezione Stato recapito.](#delivery-status)

Per impostazione predefinita, i primi 250 risultati vengono caricati e immediatamente disponibili. Quando si scorre verso il basso, si verifica una leggera pausa quando viene caricato il batch di risultati successivo. Anziché scorrere, è possibile fare clic su **Carica** tutto per caricare tutti i risultati fino a un massimo di 10.000.

È possibile fare clic sulle intestazioni di colonna per ordinare i risultati in base ai valori di tale colonna in ordine crescente o decrescente.

È possibile fare **clic su Filtra risultati** per filtrare i risultati in base a una o più colonne.

È possibile esportare i risultati dopo aver selezionato  una o più righe facendo clic su Esporta risultati e quindi selezionando Esporta tutti i **risultati,** Esporta risultati caricati o Esporta **selezionato.**

#### <a name="find-related-records-for-this-message"></a>Trovare i record correlati per questo messaggio

I record dei messaggi correlati sono record che hanno condiviso lo stesso ID messaggio. Tenere presente che anche un singolo messaggio inviato tra due persone può generare più record. Il numero di record aumenta quando il messaggio è interessato dall'espansione del gruppo di distribuzione, dall'inoltro, dalle regole del flusso di posta (note anche come regole di trasporto) e così via.

Dopo aver selezionato la casella di controllo di una riga,  è possibile trovare i record  correlati per il messaggio facendo clic sul pulsante Trova correlato visualizzato oppure selezionando Altre opzioni Altre opzioni Trova record correlati per ![ questo ](../../media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **messaggio**.

Per ulteriori informazioni sull'ID messaggio, vedere la sezione ID messaggio più indietro in questo articolo.

#### <a name="message-trace-details"></a>Dettagli traccia messaggio

Nell'output del rapporto di riepilogo è possibile visualizzare i dettagli di un messaggio utilizzando uno dei metodi seguenti:

- Selezionare la riga (fare clic in un punto qualsiasi della riga ad eccezione della casella di controllo).
- Selezionare la casella di controllo della riga e fare clic **su Altre opzioni** Altro Visualizza dettagli ![ ](../../media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **messaggio.**

   ![I dettagli dopo aver fatto doppio clic su una riga nella traccia dei messaggi del rapporto riepilogativo determinano il Centro sicurezza & conformità](../../media/e50ee7cd-810a-4c06-8b58-e56ffd7028d1.png)

I dettagli di traccia dei messaggi contengono le seguenti informazioni aggiuntive che non sono presenti nel rapporto riepilogativo:

- **Eventi messaggio**: in questa sezione sono contenute classificazioni che consentono di classificare le azioni eseguite dal servizio sui messaggi. **Alcuni degli eventi più interessanti** che potresti incontrare sono:
  - **Receive**: il messaggio è stato ricevuto dal servizio.
  - **Send**: il messaggio è stato inviato dal servizio.
  - **Fail**: Impossibile recapitare il messaggio.
  - **Recapita**: il messaggio è stato recapitato a una cassetta postale.
  - **Expand**: il messaggio è stato inviato a un gruppo di distribuzione espanso.
  - **Trasferimento:** i destinatari sono stati spostati in un messaggio biforcato a causa della conversione del contenuto, dei limiti dei destinatari dei messaggi o degli agenti.
  - **Rinvio:** il recapito del messaggio è stato posticipato e potrebbe essere eseguito un nuovo tentativo in un secondo momento.
  - **Risolto**: il messaggio è stato reindirizzato a un nuovo indirizzo del destinatario in base a una ricerca in Active Directory. In questo caso, l'indirizzo originale del destinatario verrà visualizzato in una riga separata nella traccia del messaggio insieme allo stato di consegna finale per il messaggio.

  > [!NOTE]
  >
  > - Un messaggio senza eventi recapitato correttamente genererà più voci **event** nella traccia dei messaggi.
  > - Questo elenco non deve essere esaustivo. Per le descrizioni di altri eventi, vedere [Event types in the message tracking log](/Exchange/mail-flow/transport-logs/message-tracking#event-types-in-the-message-tracking-log). Si noti che questo collegamento è un Exchange Server (Exchange locale).

- **Ulteriori informazioni**: Questa sezione contiene i dettagli seguenti:
  - **ID messaggio:** questo valore è descritto nella sezione [ID messaggio](#message-id) più indietro in questo articolo. Ad esempio, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.
  - **Dimensione messaggio**
  - **Da IP**: Indirizzo IP del computer che ha inviato il messaggio. Per i messaggi in uscita inviati da Exchange Online, il valore è vuoto.
  - **To IP**: Indirizzo IP o indirizzi in cui il servizio ha tentato di recapitare il messaggio. Se il messaggio ha più destinatari, questi vengono visualizzati. Per i messaggi in ingresso inviati a Exchange Online, il valore è vuoto.

### <a name="enhanced-summary-reports"></a>Report riepilogativo avanzato

I report di riepilogo avanzato disponibili (completati) sono disponibili nella **sezione Report scaricabili** all'inizio della traccia dei messaggi. Nel report sono disponibili le informazioni seguenti:

- **origin_timestamp**: data e ora in cui il messaggio è stato inizialmente ricevuto dal servizio, utilizzando <sup>*</sup> il fuso orario UTC configurato.
- **sender_address**: Indirizzo di posta elettronica del mittente (*dominio alias* @ ).
- **Recipient_status**: stato del recapito del messaggio al destinatario. Se il messaggio è stato inviato a più destinatari, verranno visualizzati tutti i destinatari e lo stato corrispondente per ognuno, nel formato: \<*email address*\> ## \<*status*\> . Ad esempio:
  - **##Receive, Send** indica che il messaggio è stato ricevuto dal servizio ed è stato inviato alla destinazione prevista.
  - **##Receive, Fail** indica che il messaggio è stato ricevuto dal servizio ma il recapito alla destinazione prevista non è riuscito.
  - **##Receive, Recapita** significa che il messaggio è stato ricevuto dal servizio ed è stato recapitato alla cassetta postale del destinatario.
- **message_subject**: I primi 256 caratteri del campo **Subject del** messaggio.
- **total_bytes**: Dimensioni del messaggio in byte, inclusi gli allegati.
- **message_id**: questo valore è descritto nella sezione [ID messaggio](#message-id) più indietro in questo articolo. Ad esempio, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.
- **network_message_id**: valore ID messaggio univoco che persiste in tutte le copie del messaggio che potrebbero essere create a causa della biforcazione o dell'espansione del gruppo di distribuzione. Un valore di esempio è `1341ac7b13fb42ab4d4408cf7f55890f` .
- **original_client_ip**: Indirizzo IP del client del mittente.
- **directionality**: Indica se il messaggio è stato inviato in ingresso (1) all'organizzazione o se è stato inviato in uscita (2) dall'organizzazione.
- **connector_id**: Nome del connettore di origine o di destinazione. Per ulteriori informazioni sui connettori in Exchange Online, vedere [Configure mail flow using connectors in Office 365.](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)
- **delivery_priority** <sup>*</sup> : indica se il messaggio è stato inviato con **priorità Alta,** Bassa **o** Normale.

<sup>*</sup> Queste proprietà sono disponibili solo nei report di riepilogo avanzato.

### <a name="extended-reports"></a>Report estesi

Disponibile (completato) I report estesi sono disponibili nella **sezione Report scaricabili** all'inizio della traccia dei messaggi. Praticamente tutte le informazioni di un rapporto riepilogativo avanzato sono disponibili in un report esteso (ad eccezione di origin_timestamp **e** **delivery_priority**). Le informazioni aggiuntive seguenti sono disponibili solo in un report esteso:

- **client_ip**: Indirizzo IP del server di posta elettronica o del client di messaggistica che ha inviato il messaggio.
- **client_hostname**: nome host o FQDN del server di posta elettronica o del client di messaggistica che ha inviato il messaggio.
- **server_ip**: Indirizzo IP del server di origine o di destinazione.
- **server_hostname**: nome host o FQDN del server di destinazione.
- **source_context**: informazioni aggiuntive associate al **campo di** origine. Ad esempio:
  - `Protocol Filter Agent`
  - `3489061114359050000`
- **source**: componente di Exchange Online responsabile dell'evento. Ad esempio:
  - `AGENT`
  - `MAILBOXRULE`
  - `SMTP`
- **event_id**: corrispondono ai valori **dell'evento Message** illustrati nella sezione Trovare i record [correlati per questo](#find-related-records-for-this-message) messaggio.
- **internal_message_id**: Identificatore del messaggio assegnato dal server Exchange Online che sta attualmente elaborando il messaggio.
- **recipient_address**: Gli indirizzi di posta elettronica dei destinatari del messaggio. Gli indirizzi di posta elettronica multipli sono separati dal carattere punto e virgola (;).
- **recipient_count**: numero totale di destinatari nel messaggio.
- **related_recipient_address**: utilizzato con , e gli eventi per visualizzare altri indirizzi di posta `EXPAND` elettronica dei destinatari associati al `REDIRECT` `RESOLVE` messaggio.
- **reference**: questo campo contiene informazioni aggiuntive per tipi specifici di eventi. Ad esempio:
  - **DSN**: contiene il collegamento al rapporto, ovvero il valore **message_id** della notifica sullo stato del recapito associata (nota anche come DSN, rapporto di mancato recapito, rapporto di mancato recapito o messaggio di mancato recapito) se viene generato un DSN in seguito a questo evento. Se si tratta di un messaggio DSN, questo campo contiene il message_id del messaggio originale per cui è stato generato il DSN. 
  - **EXPAND**: contiene **il related_recipient_address** dei messaggi correlati.
  - **RECEIVE**: potrebbe contenere **il message_id** del messaggio correlato se il messaggio è stato generato da altri processi (ad esempio, regole di Posta in arrivo).
  - **SEND**: contiene il **internal_message_id** di tutti i messaggi DSN.
  - **TRANSFER**: contiene **il internal_message_id** del messaggio che viene aggiunto in fork (ad esempio, in base alla conversione del contenuto, ai limiti dei destinatari del messaggio o agli agenti).
  - **MAILBOXRULE**: contiene il **internal_message_id** del messaggio in ingresso che ha causato la generazione del messaggio in uscita da parte della regola di Posta in arrivo. Per altri tipi di eventi, questo campo è in genere vuoto.
- **return_path**: Indirizzo di posta elettronica del mittente specificato dal **comando MAIL FROM** che ha inviato il messaggio. Anche se questo campo non è mai vuoto, il valore dell'indirizzo del mittente null può essere rappresentato come `<>` .
- **message_info**: Informazioni aggiuntive sul messaggio. Ad esempio:
  - Data e ora di origine del messaggio in UTC per `DELIVER` ed `SEND` eventi. La data-ora di origine è l'ora in cui il messaggio è entrato per la prima volta nell'organizzazione di Exchange Online. La data-ora UTC è rappresentata nel formato data-ora ISO 8601: , dove = anno, = mese, = giorno, indica l'inizio del componente `yyyy-mm-ddThh:mm:ss.fffZ` `yyyy` `mm` `dd` `T` ora, `hh` = ora, `mm` = minuto, = secondo, `ss` = `fff` `Z` `Zulu` frazioni di secondo e indica , che è un altro modo per indicare UTC.
  - Errori di autenticazione. Ad esempio, è possibile visualizzare il valore e il tipo di autenticazione utilizzato quando si è verificato `11a` l'errore di autenticazione.
- **tenant_id**: Valore GUID che rappresenta l'organizzazione di Exchange Online (ad esempio, `39238e87-b5ab-4ef6-a559-af54c6b07b42` ).
- **original_server_ip**: Indirizzo IP del server originale.
- **custom_data**: contiene dati correlati a tipi di evento specifici. Per ulteriori informazioni, vedere le sezioni seguenti.

#### <a name="custom_data-values"></a>custom_data valori

Il **custom_data** per un evento viene utilizzato da un'ampia gamma di agenti `AGENTINFO` di Exchange Online per registrare i dettagli dell'elaborazione dei messaggi. Alcuni degli agenti più interessanti sono descritti nelle sezioni seguenti.

#### <a name="spam-filter-agent"></a>Agente filtro posta indesiderata

Un **custom_data** che inizia con `S:SFA` deriva dall'agente di filtro della posta indesiderata. I dettagli principali sono descritti nella tabella seguente:

<br>

****

|Valore|Descrizione|
|---|---|
|`SFV=NSPM`|Il messaggio è stato contrassegnato come non indesiderato ed è stato inviato al destinatario.|
|`SFV=SPM`|Il messaggio è stato contrassegnato come posta indesiderata dal filtro di protezione da posta indesiderata (noto anche come filtro contenuto).|
|`SFV=BLK`|Le regole del filtro sono state ignorate e il messaggio è stato bloccato perché è stato originato da un mittente bloccato.|
|`SFV=SKS`|Il messaggio è stato contrassegnato come posta indesiderata prima di essere elaborato dal filtro di protezione da posta indesiderata. Questo include i messaggi che corrispondono alla regola del flusso di posta (nota anche come regola di trasporto) per contrassegnarlo automaticamente come indesiderato e ignorare tutte le regole del filtro aggiuntive.|
|`SCL=<number>`|Per ulteriori informazioni sui diversi valori SCL e sul loro significato, vedere [Livelli di probabilità di posta indesiderata.](spam-confidence-levels.md)|
|`PCL=<number>`|Il valore del livello di confidenza di Phishing (PCL) del messaggio. Questi valori possono essere interpretati allo stesso modo dei valori SCL documentati in Livelli di probabilità di [posta indesiderata.](spam-confidence-levels.md)|
|`DI=SB`|Il mittente del messaggio è stato bloccato.|
|`DI=SQ`|Il messaggio è stato messo in quarantena.|
|`DI=SD`|Il messaggio è stato eliminato.|
|`DI=SJ`|Il messaggio è stato inviato alla cartella Posta indesiderata del destinatario.|
|`DI=SN`|Il messaggio è stato instradato tramite un pool di recapito ad alto rischio.|
|`DI=SO`|Il messaggio è instradato attraverso un pool di recapito ad alto rischio. Per altre informazioni, vedere [Pool di recapito ad alto rischio per i messaggi in uscita](high-risk-delivery-pool-for-outbound-messages.md).|
|`SFS=[a]|SFS=[b]`|Indica una corrispondenza tra le regole relative alla posta indesiderata.|
|`IPV=CAL`|Il messaggio è stato consentito tramite il filtro da posta indesiderata poiché l'indirizzo IP è stato specificato in un elenco di indirizzi IP bloccati nel filtro di connessione.|
|`H=<EHLOstring>`|Stringa HELO o EHLO del server di posta elettronica connesso.|
|`PTR=<ReverseDNS>`|Il record PTR dell'indirizzo IP di invio, anche noto come indirizzo DNS inverso.|
|

Un esempio **custom_data** per un messaggio filtrato per la posta indesiderata come questo:

`S:SFA=SUM|SFV=SPM|IPV=CAL|SRV=BULK|SFS=470454002|SFS=349001|SCL=9|SCORE=-1|LIST=0|DI=SN|RD=ftmail.inc.com|H=ftmail.inc.com|CIP=98.129.140.74|SFP=1501|ASF=1|CTRY=US|CLTCTRY=|LANG=en|LAT=287|LAT=260|LAT=18;`

#### <a name="malware-filter-agent"></a>Agente filtro antimalware

Un **custom_data** che inizia con `S:AMA` deriva dall'agente di filtro antimalware. I dettagli principali sono descritti nella tabella seguente:

<br>

****

|Valore|Descrizione|
|---|---|
|`AMA=SUM|v=1|` o `AMA=EV|v=1`|È stato determinato che il messaggio contiene malware. `SUM` indica che il malware potrebbe essere stato rilevato da un numero qualsiasi di motori. `EV` indica che il malware è stato rilevato da un motore specifico. Quando viene rilevato malware da un motore, questo attiva le seguenti azioni.|
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
|

Un esempio **custom_data** valore per un messaggio contenente malware è simile al seguente:

`S:AMA=SUM|v=1|action=b|error=|atch=1;S:AMA=EV|engine=M|v=1|sig=1.155.974.0|name=DOS/Test_File|file=filename;S:AMA=EV|engine=A|v=1|sig=201707282038|name=Test_File|file=filename`

#### <a name="transport-rule-agent"></a>Agente regola di trasporto

Un **custom_data** che inizia con deriva dall'agente della regola di trasporto per le regole del flusso di posta `S:TRA` (note anche come regole di trasporto). I dettagli principali sono descritti nella tabella seguente:

<br>

****

|Valore|Descrizione|
|---|---|
|`ETR|ruleId=<guid>`|L'ID regola corrispondente.|
|`St=<datetime>`|Data e ora in FORMATO UTC in cui si è verificata la corrispondenza della regola.|
|`Action=<ActionDefinition>`|L'azione che è stata applicata. Per un elenco delle azioni disponibili, vedere [Mail flow rule actions in Exchange Online.](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)|
|`Mode=<Mode>`|La modalità della regola. I valori validi sono:<ul><li>**Enforce**: tutte le azioni sulla regola verranno applicate.</li><li>**Test con suggerimenti per i criteri:**: verranno inviate tutte le azioni di suggerimento per i criteri, ma non verranno eseguite altre azioni di applicazione.</li><li>**Test senza suggerimenti per i** criteri: le azioni verranno elencate in un file di registro, ma i mittenti non riceveranno alcuna notifica e le azioni di imposizione non verranno eseguite.</li></ul>|
|

Un esempio **custom_data** per un messaggio che soddisfa le condizioni di una regola del flusso di posta è simile al seguente:

`S:TRA=ETR|ruleId=19a25eb2-3e43-4896-ad9e-47b6c359779d|st=7/17/2017 12:31:25 AM|action=ApplyHtmlDisclaimer|sev=1|mode=Enforce`
