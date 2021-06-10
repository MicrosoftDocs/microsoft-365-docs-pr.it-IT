---
title: Gestione dei rischi insider Esplora contenuto
description: Informazioni sulla gestione dei rischi insider Esplora contenuto in Microsoft 365
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
ms.openlocfilehash: 44a17471f1e2ba92d0099f62b95dec8d0e56a224
ms.sourcegitcommit: b6763a8ab240fbdd56078a7c9452445d0c4b9545
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2021
ms.locfileid: "51957493"
---
# <a name="insider-risk-management-content-explorer"></a>Gestione dei rischi insider Esplora contenuto

Gestione dei rischi insider **Esplora contenuto** consente agli utenti assegnati al ruolo Insider Risk *Management Investigators* di esaminare il contesto e i dettagli del contenuto associato all'attività negli avvisi. I dati del caso in Esplora contenuto vengono aggiornati ogni giorno per includere nuove attività. Per tutti gli avvisi confermati per un caso, le copie dei dati e dei file dei messaggi vengono archiviate come snapshot nel tempo degli elementi, mantenendo i file e i messaggi originali nelle origini di archiviazione. Se necessario, i file di dati del caso possono essere esportati come file di documento portatile (PDF) o nel formato di file originale.

La copia di dati e messaggi è trasparente per l'utente associato all'avviso e per il proprietario del contenuto. Per i nuovi casi, il popolamento del contenuto in Esplora contenuto richiede in genere circa un'ora. Per i casi con grandi quantità di contenuto, la creazione di uno snapshot potrebbe richiedere più tempo. Se il contenuto è ancora in fase di caricamento in Esplora contenuto, verrà visualizzato un indicatore di stato che visualizza la percentuale di completamento.

In alcuni casi, i dati associati a un caso potrebbero non essere disponibili come snapshot per la revisione in Esplora contenuto. Questa situazione può verificarsi quando i dati del caso sono stati eliminati o spostati o quando si verifica un errore temporaneo durante l'elaborazione dei dati del caso. In questo caso, **selezionare** Visualizza file nella barra di avviso per visualizzare i nomi dei file, il percorso e il motivo dell'errore per ogni file. Se necessario, queste informazioni possono essere esportate in un file .csv (valori delimitati da virgole).

Se il contenuto include autorizzazioni di Information Rights Management, queste autorizzazioni vengono mantenute per il contenuto copiato e gli utenti assegnati al ruolo *Insider Risk Management Investigators* dovranno disporre di queste autorizzazioni e diritti se devono aprire e visualizzare i file. A ogni file e messaggio viene assegnato automaticamente un ID file univoco nel caso di gestione dei rischi insider a scopo di gestione. I documenti associati alle attività degli indicatori di dispositivo non sono inclusi in Esplora contenuto.

>[!Note]
>Esplora contenuto include attività correlate Microsoft Office file. Le attività a livello di sito, ad esempio quando un SharePoint viene eliminato o se vengono modificate le autorizzazioni del sito, non vengono incluse in Esplora contenuto.

## <a name="column-options"></a>Opzioni colonna

Per semplificare agli analisti e agli investigatori del rischio di esaminare i dati e i messaggi acquisiti ed esaminare il contesto del caso, in Esplora contenuto sono inclusi diversi strumenti di filtro e ordinamento. Per l'ordinamento di base, le colonne **della** classe **Date e File** supportano l'ordinamento utilizzando i titoli delle colonne nel riquadro della coda di contenuto. Sono disponibili altre colonne della coda da aggiungere alla visualizzazione per fornire pivot diversi sui file e sui messaggi.

Per aggiungere o rimuovere intestazioni di colonna per la coda di contenuto, utilizzare il **controllo Modifica** colonne e selezionare una delle opzioni di colonna seguenti. Queste colonne vengono mappate alle condizioni comuni, di posta elettronica e delle proprietà del documento supportate in Esplora contenuto ed elencate più avanti in questo articolo.

| **Opzione colonna** | **Descrizione** |
|:------------------|:----------------|
| **Author** | Il campo dell'autore dei documenti di Office, che persiste se un documento viene copiato. Ad esempio, se un utente crea un documento e lo invia tramite posta elettronica a un altro utente che lo carica SharePoint, il documento conserverà comunque l'autore originale. |
| **Ccn** | Disponibile per i messaggi di posta elettronica, gli utenti nel campo Ccn messaggio. |
| **Cc** | Disponibile per i messaggi di posta elettronica, gli utenti nel campo Cc message. |
| **Percorso composto** | Percorso leggibile che descrive l'origine dell'elemento. |
| **ID conversazione** | ID conversazione dal messaggio. |
| **Indice conversazione** | Indice della conversazione dal messaggio. |
| **Ora creazione** | Ora in cui è stato creato il file o il messaggio di posta elettronica. |
| **Data (UTC)** | Per la posta elettronica, la data di un messaggio ricevuto da un destinatario o inviato da un mittente. Per i documenti, data dell'ultima modifica di un documento. La data è nel formato UTC (Coordinated Universal Time).|
| **Tema dominante** | Tema dominante calcolato per l'analisi. |
| **ID set di posta elettronica** | ID gruppo per tutti i messaggi nello stesso set di posta elettronica. |
| **ID famiglia** | Id famiglia raggruppa tutti gli elementi; per la posta elettronica, questa colonna include il messaggio e tutti gli allegati; per i documenti, questa colonna include il documento e tutti gli elementi incorporati. |
| **Classe File** | Per il contenuto di SharePoint e OneDrive: **Document**; per il contenuto da Exchange: **Posta elettronica** o **Allegato.** |
| **File ID** | Identificatore del documento univoco all'interno del caso. |
| **Icona tipo di file** | Estensione di un file. ad esempio docx, one, pptx o xlsx. Questo campo corrisponde alla proprietà del sito FileExtension. |
| **ID** | Identificatore GUID del file. |
| **ID non modificabile** | ID non modificabile archiviato in Office 365. |
| **Tipo inclusivo** | Tipo inclusivo calcolato per l'analisi: **0** - non inclusivo; **1** - inclusivo; **2** - inclusivo meno; **3** - Copia inclusiva. |
| **Data ultima modifica** | La data dell'ultima modifica di un documento. |
| **Contrassegnato come rappresentativo** | Un documento di ogni set di duplicati esatti viene contrassegnato come rappresentanti. |
| **Tipo di messaggio** | Tipo di messaggio di posta elettronica da cercare. Valori possibili: contatti, documenti, posta elettronica, dati esterni, fax, im, journal, riunioni, microsoft teams (restituisce elementi da chat, riunioni e chiamate in Microsoft Teams), note, post, feed RSS, attività, segreteria telefonica |
| **Partecipanti** | Elenco di tutti i partecipanti di un messaggio; ad esempio Mittente, A, Cc, Ccn. |
| **Pivot ID** | ID di un pivot. |
| **Received** | La data in cui un messaggio di posta elettronica viene ricevuto da un destinatario. Questo campo corrisponde alla proprietà Received email. |
| **Destinatari** | Tutti i campi dei destinatari in un messaggio di posta elettronica. Questi campi sono A, Cc e Ccn. |
| **ID rappresentante** | Identificatore numerico di ogni set di duplicati esatti. |
| **Mittente** | Il mittente di un messaggio di posta elettronica. |
| **Mittente/Autore** | Per la posta elettronica, l'utente che ha inviato un messaggio. Per i documenti, l'utente menzionato nel campo dell'autore dei documenti di Office. È possibile digitare più nomi, separati da virgole. Due o più valori sono collegati logicamente dall'operatore OR. |
| **Tipi di informazioni sensibili** | Tipi di informazioni riservate identificati nel contenuto. |
| **Etichette di riservatezza** | Etichette di riservatezza applicate al contenuto. |
| **Inviato** | La data in cui un messaggio di posta elettronica viene inviato dal mittente. Questo campo è la stessa proprietà della proprietà Posta elettronica inviata. |
| **Dimensioni** | Per la posta elettronica e i documenti, la dimensione dell'elemento (in byte). |
| **Oggetto** | Il testo nella riga dell'oggetto di un messaggio di posta elettronica. |
| **Oggetto/Titolo** | Per la posta elettronica, il testo nella riga dell'oggetto di un messaggio. Per i documenti, il titolo del documento. Come spiegato in precedenza, la proprietà Title è un Microsoft Office documenti. È possibile digitare il nome di più di un oggetto/titolo, separati da virgole. Due o più valori sono collegati logicamente dall'operatore OR. |
| **Elenco Temi** | Elenco temi calcolato per l'analisi. |
| **Titolo** | Il titolo del documento. La proprietà Title è rappresentata dai metadati specificati nei documenti di Office. È diverso dal nome del file del documento. |
| **To** | Destinatario di un messaggio di posta elettronica nel campo A. |

## <a name="filtering"></a>Filtro

È possibile utilizzare uno o più filtri per restringere l'ambito di una ricerca e restituire un set di risultati più perfezionato. Per impostare un filtro, selezionare **Filtri** nella parte superiore della coda di contenuto. Molti filtri includono opzioni di filtro aggiuntive per limitare i risultati restituiti dal filtro. Ad esempio, il *filtro Data* include controlli per configurare una data *di inizio* e una data *di fine* per il **filtro** Data. Selezionare uno o più elementi di filtro dalle categorie seguenti:

### <a name="common-filters"></a>Filtri comuni

| **Filter** | **Descrizione** |
|:---------------------|:----------------|
| **Data (UTC)** | Per la posta elettronica, la data di un messaggio ricevuto da un destinatario o inviato da un mittente. Per i documenti, data dell'ultima modifica di un documento. |
| **Mittente/Autore** | Per la posta elettronica, l'utente che ha inviato un messaggio. Per i documenti, la persona citata nel *campo Autore* da Office documenti. È possibile digitare più nomi, separati da virgole. |
| **Source** | Percorso del documento nell'organizzazione. Ad esempio, un percorso SharePoint sito specifico. |
| **Oggetto/Titolo** | Per la posta elettronica, il testo nella riga dell'oggetto di un messaggio. Per i documenti, il titolo del documento. La proprietà Title nei documenti è specificata nei Microsoft Office documenti. È possibile digitare il nome di più di un oggetto/titolo, separati da virgole. Due o più valori sono collegati logicamente dall'operatore OR. |

### <a name="email-filters"></a>Filtri di posta elettronica

| **Filter** | **Descrizione** |
|:---------------------|:----------------|
| **Ccn** | Campo Ccn di un messaggio di posta elettronica. |
| **Cc** | Campo Cc di un messaggio di posta elettronica. |
| **Ha allegato** | Indica se un messaggio ha un allegato. I valori sono elencati **come true** o **false.** |
| **È allegato di posta elettronica** | Se il documento è un allegato, il valore viene elencato come **Sì.** |
| **Documento incorporato** | Se il documento è incorporato nel messaggio di posta elettronica, il valore viene elencato come **Sì.** |
| **Allegato in linea** | Se il documento è un allegato in linea con il messaggio di posta elettronica, il valore viene elencato come **Sì.** |
| **Partecipanti** | Tutti i campi delle persone in un messaggio di posta elettronica. Questi campi sono From, To, Cc e Bcc. |
| **Received** | La data in cui un messaggio di posta elettronica viene ricevuto da un destinatario. |
| **Domini destinatari** | Elenco di tutti i domini di destinatari di un messaggio. |
| **Destinatari** | Destinatari del messaggio di posta elettronica. |
| **Mittente** | Campo Mittente (Da) per i tipi di messaggio.  Il formato **è DisplayName \<SmtpAddress>**. |
| **Dominio del mittente** | Dominio del mittente. |
| **To** | Il campo To (A) di un messaggio di posta elettronica. |
| **Univoco nel set di posta elettronica** | False se è presente un duplicato dell'allegato nel relativo set di posta elettronica. |

## <a name="document-filters"></a>Filtri documento

| **Filtri** | **Descrizione** |
|:---------------------|:----------------|
| **Etichette di conformità** | Etichette di conformità applicate in Office 365. |
| **Ora creazione (UTC)** | Data e ora di creazione del file o del messaggio di posta elettronica. La data e l'ora sono nel formato UTC (Coordinated Universal Time). |
| **Data ultima modifica (UTC)** | La data dell'ultima modifica di un documento. La data e l'ora sono nel formato UTC (Coordinated Universal Time). |
| **Estensione del file** | Tipo di estensione del file. |
| **Eventi attività utente** | Attività per gli elementi correlati a attività utente specifiche in un caso.  Ad esempio, quando si seleziona un collegamento a "Esplora contenuto" per un'attività nella pagina **Attività** utente di un caso, questo filtro viene utilizzato per visualizzare gli elementi correlati a tale attività. |
| **Prodotto di lavoro** | Tipo di prodotto di lavoro per il documento. Ad esempio, annotazioni o tag nel documento. |
