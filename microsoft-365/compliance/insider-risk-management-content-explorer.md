---
title: Insider risk management Content Explorer
description: Informazioni su Esplora contenuto per la gestione dei rischi insider in Microsoft 365
keywords: Microsoft 365, gestione dei rischi Insider, gestione dei rischi, conformità
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: 6eb8bf91f5af60658686066b75b33b7a8dabe6bc
ms.sourcegitcommit: e03bc2945e63f7f2638257e530056ae9283b45d9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/13/2020
ms.locfileid: "49070870"
---
# <a name="insider-risk-management-content-explorer"></a>Insider risk management Content Explorer

Esplora contenuto per la gestione dei rischi insider consente agli utenti a cui è stato assegnato il ruolo insider *risk management investigators* di esaminare il contesto e i dettagli del contenuto associato all'attività negli avvisi. Per tutti gli avvisi confermati per un caso, le copie dei dati e dei file dei messaggi vengono archiviate come snapshot nel tempo degli elementi, mantenendo i file e i messaggi originali nelle origini di archiviazione. La copia dei dati e dei messaggi è trasparente per l'utente associato all'avviso e per il proprietario del contenuto. Se il contenuto include le autorizzazioni di Information Rights Management, queste autorizzazioni vengono mantenute per il contenuto copiato e gli utenti a cui è assegnato il ruolo *Insider Risk Management Investigators* dovranno disporre di tali autorizzazioni e diritti se devono aprire e visualizzare i file. A ogni file e messaggio viene assegnato automaticamente un ID file univoco nel caso di gestione dei rischi Insider a scopo di gestione. I documenti associati alle attività degli indicatori di dispositivo non sono inclusi in Esplora contenuto.

![Insider Risk Management Content Explorer](../media/insider-risk-content-explorer.png)

## <a name="column-options"></a>Opzioni colonna

Per semplificare agli analisti e agli investigatori del rischio di esaminare i dati e i messaggi acquisiti e di esaminare il contesto del caso, in Esplora contenuto sono inclusi diversi strumenti di filtro e ordinamento. Per l'ordinamento di base, le colonne della classe **Data** e **File** supportano l'ordinamento utilizzando i titoli di colonna nel riquadro della coda di contenuto. Sono disponibili altre colonne della coda da aggiungere alla visualizzazione per fornire pivot diversi su file e messaggi.

Per aggiungere o rimuovere intestazioni di colonna per la coda di contenuto, utilizzare il **controllo Modifica** colonne e selezionare una delle opzioni di colonna seguenti. Queste colonne sono associate alle condizioni comuni, di posta elettronica e delle proprietà del documento supportate in Esplora contenuto e elencate più avanti in questo articolo.

| **Opzione colonna** | **Descrizione** |
|:------------------|:----------------|
| **Author** | Il campo dell'autore dei documenti di Office, che persiste se un documento viene copiato. Ad esempio, se un utente crea un documento e lo invia tramite posta elettronica a un altro utente che lo carica in SharePoint, il documento manterrà comunque l'autore originale. |
| **Ccn** | Disponibile per i messaggi di posta elettronica, gli utenti nel campo Ccn messaggio. |
| **Cc** | Disponibile per i messaggi di posta elettronica, gli utenti nel campo Cc messaggio. |
| **Percorso composto** | Percorso leggibile che descrive l'origine dell'elemento. |
| **ID conversazione** | ID conversazione dal messaggio. |
| **Indice conversazione** | Indice della conversazione dal messaggio. |
| **Ora creazione** | Ora di creazione del file o del messaggio di posta elettronica. |
| **Data** | Per la posta elettronica, la data di un messaggio ricevuto da un destinatario o inviato da un mittente. Per i documenti, data dell'ultima modifica di un documento. |
| **Tema dominante** | Tema dominante calcolato per l'analisi. |
| **ID set di posta elettronica** | ID gruppo per tutti i messaggi nello stesso set di posta elettronica. |
| **ID famiglia** | Id famiglia raggruppa tutti gli elementi; per la posta elettronica, questa colonna include il messaggio e tutti gli allegati; per i documenti, questa colonna include il documento e gli eventuali elementi incorporati. |
| **Classe file** | Per il contenuto di SharePoint e OneDrive: **Documento;** per il contenuto di Exchange: **Posta elettronica o **allegato.** |
| **File ID** | Identificatore di documento univoco all'interno del caso. |
| **Icona del tipo di file** | L'estensione di un file; ad esempio docx, one, pptx o xlsx. Questo campo corrisponde alla proprietà del sito FileExtension. |
| **ID** | Identificatore GUID del file. |
| **ID non modificabile** | ID non modificabile archiviato in Office 365. |
| **Tipo inclusivo** | Tipo inclusivo calcolato per l'analisi: **0** - non inclusivo; **1** - inclusivo; **2** - inclusive minus; **3** - Copia inclusiva. |
| **Data ultima modifica** | La data dell'ultima modifica di un documento. |
| **Contrassegnato come rappresentativo** | Un documento di ogni set di duplicati esatti viene contrassegnato come rappresentanti. |
| **Tipo di messaggio** | Tipo di messaggio di posta elettronica da cercare. Valori possibili: contatti, documenti, posta elettronica, dati esterni, fax, messaggistica istantanea, journal, riunioni, Microsoft Teams (restituisce elementi da chat, riunioni e chiamate in Microsoft Teams), note, post, rssfeed, attività, segreteria telefonica |
| **Partecipanti** | Elenco di tutti i partecipanti di un messaggio; ad esempio Mittente, A, Cc, Ccn. |
| **Pivot ID** | ID di un pivot. |
| **Received** | La data in cui un messaggio di posta elettronica viene ricevuto da un destinatario. Questo campo corrisponde alla proprietà Received email. |
| **Destinatari** | Tutti i campi del destinatario in un messaggio di posta elettronica. Questi campi sono A, Cc e Ccn. |
| **ID rappresentante** | Identificatore numerico di ogni set di duplicati esatti. |
| **Mittente** | Il mittente di un messaggio di posta elettronica. |
| **Mittente/Autore** | Per la posta elettronica, l'utente che ha inviato un messaggio. Per i documenti, l'utente menzionato nel campo dell'autore dei documenti di Office. È possibile digitare più nomi, separati da virgole. Due o più valori sono collegati logicamente dall'operatore OR. |
| **Inviato** | La data in cui un messaggio di posta elettronica viene inviato dal mittente. Questo campo è la stessa proprietà della proprietà Posta inviata. |
| **Dimensioni** | Per la posta elettronica e i documenti, la dimensione dell'elemento (in byte). |
| **Oggetto** | Il testo nella riga dell'oggetto di un messaggio di posta elettronica. |
| **Oggetto/Titolo** | Per la posta elettronica, il testo nella riga dell'oggetto di un messaggio. Per i documenti, il titolo del documento. Come spiegato in precedenza, la proprietà Title è un metadati specificati Microsoft Office documenti. È possibile digitare il nome di più di un oggetto/titolo, separati da virgole. Due o più valori sono collegati logicamente dall'operatore OR. |
| **Elenco Temi** | Elenco temi calcolato per l'analisi. |
| **Titolo** | Il titolo del documento. La proprietà Title è rappresentata dai metadati specificati nei documenti di Office. È diverso dal nome del file del documento. |
| **To** | Destinatario di un messaggio di posta elettronica nel campo A. |

## <a name="advanced-search-conditions"></a>Condizioni di ricerca avanzate

È possibile aggiungere condizioni di ricerca per restringere l'ambito di una ricerca e restituire un set di risultati più perfezionato. Ogni condizione aggiunge una clausola alla query di ricerca creata ed eseguita all'avvio della ricerca. Una condizione è collegata logicamente alla query con parole chiave (specificata nella casella delle parole chiave) da un operatore logico (rappresentato come c:c) che ha funzionalità simili all'operatore AND. Ciò significa che gli elementi devono soddisfare sia la query con parole chiave che una o più condizioni da includere nei risultati della ricerca. Questa funzionalità è il modo in cui le condizioni consentono di limitare i risultati.

Per gli strumenti di ricerca e filtro avanzati, espandere **il** riquadro Filtro sul lato sinistro della coda di contenuto. Seleziona il **pulsante Aggiungi una condizione** per aprire l'elenco delle condizioni:

### <a name="operators-used-with-conditions"></a>Operatori utilizzati con condizioni

|**Operatore**|**Equivalente nella query**|**Descrizione**|
|:-----------|:-------------------|:--------------|
| **Dopo** |`property>date`| Utilizzato con condizioni relative alla data. Restituisce gli elementi che sono stati inviati, ricevuti o modificati dopo la data specificata.|
| **Prima** |`property<date`| Utilizzato con condizioni relative alla data. Restituisce gli elementi che sono stati inviati, ricevuti o modificati prima della data specificata.|
| **Between** |`date..date`| Utilizzato con condizioni relative alla data e alla dimensione. Se utilizzato con una condizione relativa alla data, restituisce gli elementi che sono stati inviati, ricevuti o modificati entro l'intervallo di date specificato. Se utilizzato con una condizione relativa alla dimensione, restituisce gli elementi di dimensioni comprese nell'intervallo specificato.|
| **Contiene tutti** |`(property:value) OR (property:value)`| Utilizzato con condizioni per le proprietà che specificano un valore di stringa. Restituisce gli elementi che contengono tutti uno o più valori stringa specificati. |
| **Contains any of** |`(property:value) OR (property:value)`| Utilizzato con condizioni per le proprietà che specificano un valore di stringa. Restituisce gli elementi che contengono una parte qualsiasi di uno o più valori di stringa specificati.|
| **Non contiene nessuno dei** |`-property:value`  <br/> `NOT property:value`| Utilizzato con condizioni per le proprietà che specificano un valore di stringa. Restituisce gli elementi che non contengono parti del valore di stringa specificato.|
| **Non è uguale ad alcuno dei** |`-property=value`  <br/> `NOT property=value`| Utilizzato con condizioni per le proprietà che specificano un valore di stringa. Restituisce gli elementi che non contengono la stringa specificata.|
| **Uguale a** |`size=value`| Restituisce gli elementi uguali alle dimensioni specificate. <sup>1</sup>|
| **Equals any of** |`(property=value) OR (property=value)`| Utilizzato con condizioni per le proprietà che specificano un valore di stringa. Restituisce gli elementi che corrispondono esattamente a uno o più valori di stringa specificati.|
| **Uguale a nessuno di** |`(property=value) OR (property=value)`| Utilizzato con condizioni per le proprietà che specificano un valore di stringa. Restituisce gli elementi che non corrispondono a uno o più valori stringa specificati. |
| **Maggiore di** |`size>value`| Restituisce gli elementi in cui la proprietà specificata è maggiore del valore specificato. <sup>1</sup>|
| **Greater or equal** |`size>=value`| Restituisce gli elementi in cui la proprietà specificata è maggiore o uguale al valore specificato. <sup>1</sup>|
| **Minore di** |`size<value`| Restituisce gli elementi maggiori o uguali al valore specifico. <sup>1</sup>|
| **Less or equal** |`size<=value`| Restituisce gli elementi maggiori o uguali al valore specifico. <sup>1</sup>|
| **Not equal** |`size<>value`| Restituisce gli elementi che non sono uguali alle dimensioni specificate. <sup>1</sup>|

> [!NOTE]
> <sup>1</sup> Questo operatore è disponibile solo per le condizioni che utilizzano la proprietà Size.

### <a name="common-property-conditions"></a>Condizioni comuni delle proprietà

| **Opzione condizione** | **Descrizione** |
|:---------------------|:----------------|
| **Data** | Per la posta elettronica, la data di un messaggio ricevuto da un destinatario o inviato da un mittente. Per i documenti, data dell'ultima modifica di un documento. |
| **Mittente/Autore** | Per la posta elettronica, l'utente che ha inviato un messaggio. Per i documenti, l'utente menzionato nel campo dell'autore dei documenti di Office. È possibile digitare più nomi, separati da virgole. Due o più valori sono collegati logicamente dall'operatore **OR**. |
| **Dimensioni** | Per la posta elettronica e i documenti, la dimensione dell'elemento (in byte). |
| **Oggetto/Titolo** | Per la posta elettronica, il testo nella riga dell'oggetto di un messaggio. Per i documenti, il titolo del documento. La proprietà Title nei documenti è specificata nei Microsoft Office documenti. È possibile digitare il nome di più di un oggetto/titolo, separati da virgole. Due o più valori sono collegati logicamente dall'operatore OR. |

### <a name="email-property-conditions"></a>Condizioni delle proprietà di posta elettronica

Nella tabella seguente sono elencate le condizioni delle proprietà dei messaggi di posta elettronica disponibili in Esplora contenuto.

| **Opzione condizione** | **Descrizione** |
|:---------------------|:----------------|
| **Ccn** | Campo Ccn di un messaggio di posta elettronica. |
| **Cc** | Campo Cc di un messaggio di posta elettronica. |
| **Sicurezza della posta elettronica** | Impostazione di sicurezza del messaggio. |
| **Riservatezza della posta elettronica** | Impostazione di riservatezza del messaggio. |
| **ID set di posta elettronica** | ID gruppo per tutti i messaggi nello stesso set di posta elettronica. |
| **From** | Il mittente di un messaggio di posta elettronica. |
| **Ha allegato** | Indica se un messaggio contiene un allegato. Utilizzare i valori **true** o **false.** |
| **Priorità** | La priorità di un messaggio di posta elettronica, che può essere specificata dall'utente al momento dell'invio di un messaggio. Per impostazione predefinita, i messaggi vengono inviati con una priorità normale, a meno che il mittente non imposti la priorità **high** (alta) o **low** (bassa). |
| **Data di fine riunione** | Data di fine della riunione per le riunioni. |
| **Data di inizio della riunione** | Data di inizio della riunione per le riunioni. |
| **Tipo di messaggio** | Tipo di messaggio di posta elettronica da cercare. Valori possibili: contatti, documenti, posta elettronica, dati esterni, fax, messaggistica istantanea, journal, riunioni, Microsoft Teams (restituisce elementi da chat, riunioni e chiamate in Microsoft Teams), note, post, rssfeed, attività, segreteria telefonica |
| **Dominio partecipante** | Elenco di tutti i domini dei partecipanti di un messaggio. |
| **Partecipanti** | Tutti i campi degli utenti in un messaggio di posta elettronica. Questi campi sono From, To, Cc e Bcc. |
| **Received** | La data in cui un messaggio di posta elettronica viene ricevuto da un destinatario. |
| **Domini destinatario** | Elenco di tutti i domini dei destinatari di un messaggio. |
| **Mittente** | Campo Mittente (Da) per i tipi di messaggio.  Il formato **è DisplayName. \<SmtpAddress>** |
| **Dominio del mittente** | Dominio del mittente. |
| **Oggetto** | Il testo nella riga dell'oggetto di un messaggio di posta elettronica.  <br/> **Nota:** Quando si utilizza la proprietà Subject in una query, la ricerca restituisce tutti i messaggi in cui la riga dell'oggetto contiene il testo che si sta cercando. In altre parole, la query non restituisce solo i messaggi che hanno una corrispondenza esatta. Ad esempio, se si cerca , i risultati includeranno i messaggi con oggetto `subject:"Quarterly Financials"` "Quarterly Financials 2018". |
| **To** | Il campo To (A) di un messaggio di posta elettronica. |
| **Univoco nel set di e-mail** | False se è presente un duplicato dell'allegato nel relativo set di e-mail. |

## <a name="document-property-conditions"></a>Condizioni delle proprietà del documento

Nella tabella seguente sono elencate le condizioni delle proprietà dei documenti disponibili in Esplora contenuto. Molte di queste condizioni di proprietà sono condivise con i set da rivedere inclusi nei [casi di Advanced eDiscovery.](document-metadata-fields-in-Advanced-eDiscovery.md)

| **Opzione condizione** | **Descrizione** |
|:---------------------|:----------------|
| **Punteggio privilegio avvocato-client** | Punteggio del contenuto del modello di privilegio avvocato-client. |
| **Author** | Il campo dell'autore dei documenti di Office, che persiste se un documento viene copiato. Ad esempio, se un utente crea un documento e lo invia tramite posta elettronica a un altro utente che lo carica in SharePoint, il documento manterrà comunque l'autore originale. |
| **Etichette di conformità** | Etichette di conformità applicate in Office 365. |
| **Percorso composto** | Percorso leggibile che descrive l'origine dell'elemento. |
| **ID conversazione** | ID conversazione dal messaggio. |
| **Ora creazione** | Ora di creazione del file o del messaggio di posta elettronica. |
| **Responsabile** | Nome del responsabile a cui è stato associato l'elemento. |
| **Tema dominante** | Tema dominante calcolato per l'analisi. |
| **ID famiglia** | Id famiglia raggruppa tutti gli elementi; per la posta elettronica, questo campo include il messaggio e tutti gli allegati; per i documenti, questo campo include il documento e gli eventuali elementi incorporati. |
| **Classe file** | Per il contenuto di SharePoint e OneDrive: **Documento;** per il contenuto di Exchange: **Posta elettronica o **allegato.** |
| **Tipi di file** | L'estensione di un file; ad esempio docx, one, pptx o xlsx. |
| **Ha un avvocato partecipante** | True quando almeno uno dei partecipanti viene trovato nell'elenco degli avvocati. in caso contrario, il valore è False. |
| **ID non modificabile** | ID non modificabile archiviato in Office 365. |
| **Tipo inclusivo** | Tipo inclusivo calcolato per l'analisi: **0** - non inclusivo; **1** - inclusivo; **2** - inclusive minus; **3** - Copia inclusiva. |
| **Classe Item** | Classe di elementi fornita dal server Exchange; ad esempio **IPM. Nota** |
| **Data ultima modifica** | La data dell'ultima modifica di un documento. |
| **Load ID** | ID carico, in cui l'elemento è stato caricato in un insieme da rivedere. |
| **Nome della posizione** | Stringa che identifica l'origine dell'elemento.  Per Exchange, questo campo sarà l'indirizzo SMTP della cassetta postale. Per SharePoint e OneDrive, l'URL della raccolta siti. |
| **Contrassegnato come rappresentativo** | Un documento di ogni set di duplicati esatti viene contrassegnato come rappresentanti. |
| **Estensione di file nativa** | Estensione nativa dell'elemento. |
| **Nome file nativo** | Nome file nativo dell'elemento. |
| **NdEtSortExclAttach** | Concatenazione del set di e-mail e del set di ND per un ordinamento efficiente in fase di revisione; D viene aggiunto come prefisso ai set di ND e E ai set di e-mail. |
| **Pivot ID** | ID di un pivot. |
| **Potenzialmente privilegiato** | True se il modello di rilevamento dei privilegi avvocato-client considera il documento potenzialmente privilegiato. |
| **Stato elaborazione** | Stato di elaborazione dopo l'aggiunta dell'elemento a un insieme da rivedere. |
| **Percentile di lettura** | Percentile di lettura per il documento in base alla rilevanza. |
| **Punteggio di pertinenza** | Punteggio di pertinenza di un documento in base alla pertinenza. |
| **Tag di pertinenza** | Punteggio di pertinenza di un documento in base alla pertinenza. |
| **ID rappresentante** | Identificatore numerico di ogni set di duplicati esatti. |
| **Tag** | Tag applicati in un insieme da rivedere. |
| **Elenco Temi** | Elenco temi calcolato per l'analisi. |
| **Titolo** | Il titolo del documento. La proprietà Title è rappresentata dai metadati specificati nei documenti di Office. È diverso dal nome del file del documento. |
| **È stato corretti** | True se l'elemento è stato corretti, in caso contrario False. |
| **Conteggio parole** | Numero di parole in un file. |
