---
title: Esploratore contenuto gestione dei rischi Insider
description: Informazioni su Insider Risk Management Content Explorer in Microsoft 365
keywords: Microsoft 365, gestione dei rischi Insider, gestione dei rischi, conformità
localization_priority: Normal
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: e48b18ee905bc8589ad3fd6145630b436603ae15
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "44327050"
---
# <a name="insider-risk-management-content-explorer"></a>Esploratore contenuto gestione dei rischi Insider

L'esploratore contenuto di gestione dei rischi insider consente agli utenti assegnati al ruolo **investigatori di gestione dei rischi Insider** di esaminare il contesto e i dettagli delle comunicazioni acquisite negli avvisi. Per tutti gli avvisi, le copie dei dati e i file dei messaggi vengono archiviati come snapshot nel tempo degli elementi, mantenendo i file e i messaggi originali nelle origini di archiviazione. La copia di dati e messaggi è trasparente per il dipendente associato all'avviso e per il proprietario del contenuto. Le impostazioni di autorizzazione e i diritti di accesso per i dati vengono mantenuti per il contenuto copiato e i messaggi e gli analisti dei rischi e gli investigatori devono disporre di tali autorizzazioni e diritti, se necessario, per aprire e visualizzare i file. A ciascun file e al messaggio viene assegnato automaticamente un ID file univoco nel caso di gestione dei rischi Insider per la gestione.

## <a name="column-options"></a>Opzioni di colonna

Per semplificare l'analisi dei dati e dei messaggi acquisiti e esaminare il contesto, è possibile includere più strumenti di filtro e ordinamento per gli analisti e gli investigatori del rischio. Per l'ordinamento di base, le colonne **Data** e **classe file** supportano l'ordinamento utilizzando i titoli di colonna nel riquadro coda di contenuto. Altre colonne della coda sono disponibili per l'aggiunta alla visualizzazione per fornire pivot diversi nei file e nei messaggi.

Per aggiungere o rimuovere intestazioni di colonna per la coda di contenuto, utilizzare il controllo **modifica colonne** e selezionare una delle opzioni seguenti della colonna. Queste colonne vengono mappate alle condizioni comuni, di posta elettronica e delle proprietà del documento supportate in Esplora contenuto e elencate più avanti in questo argomento.

| **Opzione colonna** | **Descrizione** |
|:------------------|:----------------|
| **Author** | Il campo dell'autore dei documenti di Office, che persiste se un documento viene copiato. Ad esempio, se un utente crea un documento e lo invia tramite posta elettronica a qualcun altro che lo carica in SharePoint, il documento conserva comunque l'autore originale. |
| **Ccn** | Disponibile per i messaggi di posta elettronica, gli utenti nel campo dei messaggi Ccn. |
| **Cc** | Disponibile per i messaggi di posta elettronica, gli utenti nel campo del messaggio CC. |
| **Percorso composto** | Percorso leggibile che descrive l'origine dell'elemento. |
| **ID conversazione** | ID conversazione dal messaggio. |
| **Indice di conversazione** | Indice di conversazione dal messaggio. |
| **Ora di creazione** | L'ora in cui è stato creato il file o il messaggio di posta elettronica. |
| **Data** | Per la posta elettronica, la data di un messaggio ricevuto da un destinatario o inviato da un mittente. Per i documenti, la data dell'Ultima modifica di un documento. |
| **Tema dominante** | Tema dominante calcolato per l'analisi. |
| **ID set di posta elettronica** | ID gruppo per tutti i messaggi nello stesso set di posta elettronica. |
| **ID famiglia** | Gruppi di ID famiglia insieme tutti gli elementi; per la posta elettronica, sono inclusi il messaggio e tutti gli allegati. per i documenti, sono inclusi il documento e tutti gli elementi incorporati. |
| **Classe file** | Per il contenuto di SharePoint e OneDrive: **Document**; per il contenuto da Exchange: * * E-mail o **allegato**. |
| **ID file** | Identificatore di documento univoco all'interno del caso. |
| **Icona tipo di file** | L'estensione di un file; ad esempio, docx, 1, pptx o xlsx. Corrisponde alla proprietà dei siti FileExtension. |
| **ID** | Identificatore GUID per il file. |
| **ID non modificabile** | ID non modificabile memorizzato in Office 365. |
| **Tipo inclusivo** | Tipo incluso calcolato per analisi: **0** -non incluso; **1** -Inclusive; **2** -incluso meno; copia **3** -inclusive. |
| **Data ultima modifica** | La data dell'ultima modifica di un documento. |
| **Contrassegnata come rappresentante** | Un documento di ogni gruppo di duplicati esatti è contrassegnato come rappresentanti. |
| **Tipo di messaggio** | Il tipo di messaggio di posta elettronica da cercare. Valori possibili: contatti, documenti, messaggi di posta elettronica, dati esterni, fax, messaggistica istantanea, registrazioni, riunioni, Microsoft Teams (restituisce elementi da chat, riunioni e chiamate in Microsoft Teams), note, post, rssfeeds, attività, segreteria telefonica |
| **Partecipanti** | Elenco di tutti i partecipanti a un messaggio; ad esempio, sender, to, CC, BCC. |
| **ID pivot** | ID di un pivot. |
| **Received** | La data in cui un messaggio di posta elettronica viene ricevuto da un destinatario. Corrisponde alla proprietà della posta elettronica Received (Ricevuto). |
| **Destinatari** | Tutti i campi dei destinatari in un messaggio di posta elettronica. Questi campi sono a, CC e Ccn. |
| **ID rappresentativo** | Identificatore numerico di ogni set di duplicati esatti. |
| **Mittente** | Il mittente di un messaggio di posta elettronica. |
| **Mittente/autore** | Per la posta elettronica, l'utente che ha inviato un messaggio. Per i documenti, l'utente menzionato nel campo dell'autore dei documenti di Office. È possibile digitare più nomi, separati da virgole. Due o più valori sono collegati logicamente dall'operatore OR. |
| **Inviati** | La data in cui un messaggio di posta elettronica viene inviato dal mittente. Corrisponde alla proprietà della posta elettronica Sent (Inviato). |
| **Dimensioni** | Per la posta elettronica e i documenti, la dimensione dell'elemento (in byte). |
| **Oggetto** | Il testo nella riga dell'oggetto di un messaggio di posta elettronica. |
| **Subject/title** | Per la posta elettronica, il testo nella riga dell'oggetto di un messaggio. Per i documenti, il titolo del documento. Come spiegato in precedenza, la proprietà title è costituita da metadati specificati nei documenti di Microsoft Office. È possibile digitare il nome di più di un oggetto/titolo, separati da virgole. Due o più valori sono collegati logicamente dall'operatore OR. |
| **Elenco temi** | Elenco temi come calcolato per l'analisi. |
| **Titolo** | Il titolo del documento. La proprietà Title è rappresentata dai metadati specificati nei documenti di Office. È diverso dal nome di file del documento. |
| **To** | Il destinatario di un messaggio di posta elettronica nel campo a. |

## <a name="advanced-search-conditions"></a>Condizioni di ricerca avanzate

È possibile aggiungere condizioni di ricerca per limitare l'ambito di una ricerca e restituire un insieme di risultati più raffinato. Ogni condizione aggiunge una clausola alla query di ricerca creata ed eseguita all'avvio della ricerca. Una condizione è connessa logicamente alla query con parole chiave, specificata nella casella parola chiave, da un operatore logico (rappresentato come c:c) simile alla funzionalità all'operatore AND. Questo significa che gli elementi devono soddisfare sia la query con parole chiave sia una o più condizioni da includere nei risultati della ricerca. Ecco in che modo le condizioni aiutano a limitare i risultati.

Per gli strumenti avanzati per il filtro e la ricerca, espandere il riquadro dei **filtri** sul lato sinistro della coda di contenuto. Selezionare il pulsante **Aggiungi condizione** per aprire l'elenco delle condizioni:

### <a name="operators-used-with-conditions"></a>Operatori utilizzati con condizioni

|**Operatore**|**Equivalente nella query**|**Descrizione**|
|:-----------|:-------------------|:--------------|
| **Dopo** |`property>date`| Utilizzato con condizioni relative alla data. Restituisce gli elementi che sono stati inviati, ricevuti o modificati dopo la data specificata.|
| **Prima** |`property<date`| Utilizzato con condizioni relative alla data. Restituisce gli elementi che sono stati inviati, ricevuti o modificati prima della data specificata.|
| **Tra** |`date..date`| Utilizzato con condizioni relative alla data e alla dimensione. Se utilizzato con una condizione relativa alla data, restituisce gli elementi che sono stati inviati, ricevuti o modificati entro l'intervallo di date specificato. Se utilizzato con una condizione relativa alla dimensione, restituisce gli elementi di dimensioni comprese nell'intervallo specificato.|
| **Contiene tutti i** |`(property:value) OR (property:value)`| Utilizzato con condizioni per le proprietà che specificano un valore di stringa. Restituisce gli elementi che contengono tutti uno o più valori stringa specificati. |
| **Contains any of** |`(property:value) OR (property:value)`| Utilizzato con condizioni per le proprietà che specificano un valore di stringa. Restituisce gli elementi che contengono una parte qualsiasi di uno o più valori di stringa specificati.|
| **Contiene nessuno di** |`-property:value`  <br/> `NOT property:value`| Utilizzato con condizioni per le proprietà che specificano un valore di stringa. Restituisce gli elementi che non contengono parti del valore di stringa specificato.|
| **Non è uguale a una delle** |`-property=value`  <br/> `NOT property=value`| Utilizzato con condizioni per le proprietà che specificano un valore di stringa. Restituisce gli elementi che non contengono la stringa specificata.|
| **È uguale a** |`size=value`| Restituisce gli elementi equivalenti alla dimensione specificata. <sup>1</sup>|
| **Equals any of** |`(property=value) OR (property=value)`| Utilizzato con condizioni per le proprietà che specificano un valore di stringa. Restituisce gli elementi che corrispondono esattamente a uno o più valori di stringa specificati.|
| **Uguale a None di** |`(property=value) OR (property=value)`| Utilizzato con condizioni per le proprietà che specificano un valore di stringa. Restituisce gli elementi che non corrispondono a uno o più valori stringa specificati. |
| **Maggiore di** |`size>value`| Restituisce gli elementi in cui la proprietà specificata è maggiore del valore specificato. <sup>1</sup>|
| **Greater or equal** |`size>=value`| Restituisce gli elementi in cui la proprietà specificata è maggiore o uguale al valore specificato. <sup>1</sup>|
| **Meno di** |`size<value`| Restituisce gli elementi che sono maggiori o uguali al valore specifico. <sup>1</sup>|
| **Less or equal** |`size<=value`| Restituisce gli elementi che sono maggiori o uguali al valore specifico. <sup>1</sup>|
| **Not equal** |`size<>value`| Restituisce gli elementi che non sono uguali alle dimensioni specificate. <sup>1</sup>|

> [!NOTE]
> <sup>1</sup> questo operatore è disponibile solo per le condizioni che utilizzano la proprietà Size.

### <a name="common-property-conditions"></a>Condizioni comuni delle proprietà

| **Opzione condizione** | **Descrizione** |
|:---------------------|:----------------|
| **Data** | Per la posta elettronica, la data di un messaggio ricevuto da un destinatario o inviato da un mittente. Per i documenti, la data dell'Ultima modifica di un documento. |
| **Mittente/autore** | Per la posta elettronica, l'utente che ha inviato un messaggio. Per i documenti, l'utente menzionato nel campo dell'autore dei documenti di Office. È possibile digitare più nomi, separati da virgole. Due o più valori sono collegati logicamente dall'operatore **OR**. |
| **Dimensioni** | Per la posta elettronica e i documenti, la dimensione dell'elemento (in byte). |
| **Subject/title** | Per la posta elettronica, il testo nella riga dell'oggetto di un messaggio. Per i documenti, il titolo del documento. La proprietà title nei documenti è costituita dai metadati specificati nei documenti di Microsoft Office. È possibile digitare il nome di più di un oggetto/titolo, separati da virgole. Due o più valori sono collegati logicamente dall'operatore OR. |

### <a name="email-property-conditions"></a>Condizioni della proprietà di posta elettronica

Nella tabella seguente sono elencate le condizioni delle proprietà dei messaggi di posta elettronica disponibili in Content Explorer.

| **Opzione condizione** | **Descrizione** |
|:---------------------|:----------------|
| **Ccn** | Il campo Ccn di un messaggio di posta elettronica. |
| **Cc** | Campo CC di un messaggio di posta elettronica. |
| **Sicurezza della posta elettronica** | Impostazione di sicurezza del messaggio. |
| **Sensibilità della posta elettronica** | Impostazione di sensibilità del messaggio. |
| **ID set di posta elettronica** | ID gruppo per tutti i messaggi nello stesso set di posta elettronica. |
| **From** | Il mittente di un messaggio di posta elettronica. |
| **Ha allegato** | Indica se un messaggio ha un allegato. Utilizzare i valori **true** o **false**. |
| **Importanza** | La priorità di un messaggio di posta elettronica, che può essere specificata dall'utente al momento dell'invio di un messaggio. Per impostazione predefinita, i messaggi vengono inviati con una priorità normale, a meno che il mittente non imposti la priorità **high** (alta) o **low** (bassa). |
| **Data di fine riunione** | Data di fine riunione per le riunioni. |
| **Data di inizio riunione** | Data di inizio della riunione per le riunioni. |
| **Tipo di messaggio** | Il tipo di messaggio di posta elettronica da cercare. Valori possibili: contatti, documenti, messaggi di posta elettronica, dati esterni, fax, messaggistica istantanea, registrazioni, riunioni, Microsoft Teams (restituisce elementi da chat, riunioni e chiamate in Microsoft Teams), note, post, rssfeeds, attività, segreteria telefonica |
| **Dominio del partecipante** | Elenco di tutti i domini dei partecipanti di un messaggio. |
| **Partecipanti** | Tutti i campi persone in un messaggio di posta elettronica. Questi campi sono da, a, CC e Ccn. |
| **Received** | La data in cui un messaggio di posta elettronica viene ricevuto da un destinatario. |
| **Domini destinatario** | Elenco di tutti i domini dei destinatari di un messaggio. |
| **Mittente** | Campo mittente (da) per i tipi di messaggio.  Format è **DisplayName \< SmtpAddress>**. |
| **Dominio del mittente** | Dominio del mittente. |
| **Oggetto** | Il testo nella riga dell'oggetto di un messaggio di posta elettronica.  <br/> **Nota:** Quando si utilizza la proprietà Subject in una query, la ricerca restituisce tutti i messaggi in cui la riga dell'oggetto contiene il testo che si sta cercando. In altre parole, la query non restituisce solo i messaggi che hanno una corrispondenza esatta. Ad esempio, se si cerca `subject:"Quarterly Financials"` , i risultati includono i messaggi con l'oggetto "Financials trimestrali 2018". |
| **To** | Il campo To (A) di un messaggio di posta elettronica. |
| **Univoco nel set di posta elettronica** | False se è presente un duplicato dell'allegato nel relativo set di posta elettronica. |

## <a name="document-property-conditions"></a>Condizioni per le proprietà del documento

Nella tabella seguente sono elencate le condizioni delle proprietà dei documenti disponibili in Content Explorer. Molte di queste condizioni di proprietà sono condivise con i set di revisione inclusi in [Advanced eDiscovery Cases](document-metadata-fields-in-Advanced-eDiscovery.md).

| **Opzione condizione** | **Descrizione** |
|:---------------------|:----------------|
| **Punteggio Privilege avvocato-cliente** | Punteggio di contenuto del modello di privilegio avvocato-client. |
| **Author** | Il campo dell'autore dei documenti di Office, che persiste se un documento viene copiato. Ad esempio, se un utente crea un documento e lo invia tramite posta elettronica a qualcun altro che lo carica in SharePoint, il documento conserva comunque l'autore originale. |
| **Etichette di conformità** | Etichette di conformità applicate in Office 365. |
| **Percorso composto** | Percorso leggibile che descrive l'origine dell'elemento. |
| **ID conversazione** | ID conversazione dal messaggio. |
| **Ora di creazione** | L'ora in cui è stato creato il file o il messaggio di posta elettronica. |
| **Custode** | Nome del custode a cui è stato associato l'elemento. |
| **Tema dominante** | Tema dominante calcolato per l'analisi. |
| **ID famiglia** | Gruppi di ID famiglia insieme tutti gli elementi; per la posta elettronica, sono inclusi il messaggio e tutti gli allegati. per i documenti, sono inclusi il documento e tutti gli elementi incorporati. |
| **Classe file** | Per il contenuto di SharePoint e OneDrive: **Document**; per il contenuto da Exchange: * * E-mail o **allegato**. |
| **Tipi di file** | L'estensione di un file; ad esempio, docx, 1, pptx o xlsx. |
| **Ha un partecipante all'avvocato** | Ha valore true se almeno uno dei partecipanti è presente nell'elenco degli avvocati. in caso contrario, il valore è false. |
| **ID non modificabile** | ID non modificabile memorizzato in Office 365. |
| **Tipo inclusivo** | Tipo incluso calcolato per analisi: **0** -non incluso; **1** -Inclusive; **2** -incluso meno; copia **3** -inclusive. |
| **Classe Item** | Classe Item fornita da Exchange Server; ad esempio, **IPM. Note** |
| **Data ultima modifica** | La data dell'ultima modifica di un documento. |
| **ID di carico** | ID carico, in cui l'elemento è stato caricato in un set di revisione. |
| **Nome percorso** | Stringa che identifica l'origine dell'elemento.  Per Exchange, questo sarà l'indirizzo SMTP della cassetta postale. Per SharePoint e OneDrive, l'URL della raccolta siti. |
| **Contrassegnata come rappresentante** | Un documento di ogni gruppo di duplicati esatti è contrassegnato come rappresentanti. |
| **Estensione di file nativa** | Interno nativo dell'elemento. |
| **Nome file nativo** | Nome file nativo dell'elemento. |
| **NdEtSortExclAttach** | Concatenazione del set di posta elettronica e del set ND per l'ordinamento efficiente al momento della revisione; D viene aggiunto come prefisso ai set ND ed e viene aggiunto ai set di posta elettronica. |
| **ID pivot** | ID di un pivot. |
| **Potenzialmente privilegiati** | True se il modello di rilevamento dei privilegi avvocato-client considera il documento potenzialmente privilegiato. |
| **Stato di elaborazione** | Stato di elaborazione dopo che l'elemento è stato aggiunto a un set di revisione. |
| **Lettura percentile** | Leggere il percentile per il documento in base alla pertinenza. |
| **Punteggio di pertinenza** | Punteggio di pertinenza di un documento in base alla pertinenza. |
| **Tag pertinenza** | Punteggio di pertinenza di un documento in base alla pertinenza. |
| **ID rappresentativo** | Identificatore numerico di ogni set di duplicati esatti. |
| **Categorie** | Tag applicati in un set di revisione. |
| **Elenco temi** | Elenco temi come calcolato per l'analisi. |
| **Titolo** | Il titolo del documento. La proprietà Title è rappresentata dai metadati specificati nei documenti di Office. È diverso dal nome di file del documento. |
| **È stato rimediato** | Ha valore true se l'elemento è stato rimediato, altrimenti false. |
| **Conteggio parole** | Il numero di parole presenti in un file. |
