---
title: Campi metadati documento in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: In questo articolo vengono definiti i campi di metadati per i documenti in un set di revisioni in un caso in Advanced eDiscovery in Microsoft 365.
ms.openlocfilehash: e801f60b69c796dfcd2cb6d83cc4fbc721dc7658
ms.sourcegitcommit: 5a1cb7d95070eef47d401a4693cc137a90550a5e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52259464"
---
# <a name="document-metadata-fields-in-advanced-ediscovery"></a>Campi metadati documento in Advanced eDiscovery

Nella tabella seguente sono elencati i campi di metadati per i documenti in un insieme di revisioni in un caso in Advanced eDiscovery. Nella tabella sono disponibili le informazioni seguenti:

- **Nome campo** e Nome campo **visualizzato:** il nome del campo dei metadati e il nome del campo visualizzato quando si visualizzano i metadati del file di un documento selezionato in un set di revisioni. Alcuni campi di metadati non vengono inclusi quando si visualizzano i metadati del file di un documento. Questi campi sono evidenziati con un asterisco (*).

- **Nome campo ricercabile:** Nome della proprietà che è possibile cercare durante l'esecuzione di una [query del set di revisione.](review-set-search.md) Una cella vuota indica che non è possibile cercare il campo in una query del set di revisione.

- **Nome campo esportato:** Nome del campo di metadati incluso quando i documenti vengono esportati.  Una cella vuota indica che il campo non è incluso nei metadati esportati.

- **Descrizione:** Descrizione del campo dei metadati.

> [!NOTE]
> Il **campo Parole** chiave nella ricerca del set di [revisione](./review-set-search.md) utilizza Keyword Query Language (KQL). I campi elencati nella colonna **Nome** campo  ricercabile possono essere utilizzati nel campo Parole chiave in una ricerca di set di revisione per formare query complesse senza dover utilizzare il generatore di query. Per ulteriori informazioni su KQL, vedere Keyword [Query Language syntax reference.](/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)

|**Nome campo** e **Nome campo visualizzato**|**Nome campo ricercabile**|**Nome campo esportato**|**Descrizione**|
|:-----|:-----|:-----|:-----|
|ID contenuto allegato|AttachmentContentId||ID contenuto allegato dell'elemento.|
|Punteggio di privilegio del cliente avvocato|AttorneyClientPrivilegeScore||Punteggio di contenuto del modello di privilegio avvocato-client.|
|Author|Author|Doc_authors|Autore dai metadati del documento.|
|Ccn|Ccn|Email_bcc|Campo Ccn per i tipi di messaggio. Il formato **è DisplayName \<SMTPAddress>**.|
|CC|Cc|Email_cc|Campo Cc per i tipi di messaggio. Il formato **è DisplayName \<SMTPAddress>**.|
|Etichette di conformità|ComplianceLabels|Compliance_labels|[Etichette di conservazione](retention.md) applicate al contenuto in Office 365.|
|Percorso composto|CompoundPath|Compound_path|Percorso leggibile che descrive l'origine dell'elemento.|
|Content*|Contenuto||Testo estratto dell'elemento.|
|Corpo conversazione|Corpo conversazione||Corpo della conversazione dell'elemento.|
|Argomento conversazione|Argomento conversazione||Argomento di conversazione dell'elemento.|
|ID conversazione|ConversationId|Email_conversation_ID|ID conversazione dal messaggio.|
|Indice conversazione||Conversation_index|Indice della conversazione dal messaggio.|
|Tempo pdf conversazione|ConversationPdfTime||Data di creazione della versione PDF della conversazione.|
|Tempo di masterizzazione redazione conversazione|ConversationRedactionBurnTime||Data in cui è stata creata la versione PDF della conversazione per Chat.|
|||Converted_file_path|Percorso del file di esportazione convertito. Solo per uso interno di Microsoft.|
|Data di creazione del documento|CreatedTime|Doc_date_created|Creare la data dai metadati del documento.|
|Custode|Custode|Custode|Nome del responsabile a cui è stato associato l'elemento.|
|Data|Data|Data|Date è un campo calcolato che dipende dal tipo di file.<br /><br />Posta elettronica: Data di invio<br />Allegati di posta elettronica: data dell'ultima modifica del documento;se non disponibile, data di invio dell'elemento padre<br />Documenti incorporati: data dell'ultima modifica del documento; se non disponibile, data dell'ultima modifica dell'elemento padre<br />Documenti di SpO (include allegati moderni): SharePoint data dell'ultima modifica; se non disponibile, la data dell'ultima modifica dei documenti<br />Documenti non Office 365: data ultima modifica<br />Riunioni: data di inizio della riunione<br />VoiceMail: Data di invio<br />Messaggistica istantanea: data di invio|
|Altri percorsi|Dedupedcompoundpath|Deduped_compound_path|Elenco di percorsi composti di documenti che sono duplicati esatti (posta elettronica: in base al contenuto, documenti: in base all'hash).|
|Altri custodi|DedupedCustodians|Deduped_custodians|Elenco dei custodi dei documenti che sono duplicati esatti (per la posta elettronica, in base al contenuto, per i documenti, in base all'hash).|
|Altri ID file|DedupedFileIds|Deduped_file_IDs|Elenco di ID file di documenti che sono duplicati esatti (per la posta elettronica, in base al contenuto, per i documenti, in base all'hash).|
|Commenti documento|DocComments|Doc_comments|Commenti dai metadati del documento.|
|Document company||Doc_company|Società dai metadati del documento.|
|DocIndex*|||Indice nella famiglia. **-1** o **0** indica che è la radice.|
|Parole chiave del documento||Doc_keywords|Parole chiave dai metadati del documento.|
|Documento modificato da||Doc_modified_by|Data dell'ultima modifica dai metadati del documento.|
|Revisione documento|Doc_Version|Doc_Version|Revisione dai metadati del documento.|
|Oggetto documento||Doc_subject|Oggetto dai metadati del documento.|
|Modello di documento||Doc_template|Modello dai metadati del documento.|
|DocLastSavedBy||Doc_last_saved_by|Nome dell'ultimo utente che ha salvato il documento.|
|Tema dominante|DominantTheme|Dominant_theme|Tema dominante calcolato per l'analisi.|
|Sottoinsieme duplicato||Duplicate_subset|ID gruppo per duplicati esatti.|
|EmailAction*||Email_action|I valori **sono None,** **Reply** o **Forward;** in base all'oggetto di un messaggio.|
|Conferma di recapito e-mail richiesta||Email_delivery_receipt_requested|Indirizzo di posta elettronica fornito nelle intestazioni Internet per la conferma di recapito.|
|Priorità|EmailImportance|Email_importance|Importanza del messaggio: **0** - Basso; **1** - Normale; **2** - Alta|
|EmailInternetHeaders|EmailInternetHeaders|Email_internet_headers|Set completo di intestazioni di posta elettronica dal messaggio di posta elettronica|
|EmailLevel*||Email_level|Indica il livello di un messaggio all'interno del thread di posta elettronica a cui appartiene. gli allegati ereditano il valore del messaggio padre.|
|ID messaggio di posta elettronica||Email_message_ID|ID messaggio Internet dal messaggio.|
|EmailReadReceiptRequested||Email_read_receipt_requested|Indirizzo di posta elettronica fornito nelle intestazioni Internet per la conferma di lettura.|
|Sicurezza della posta elettronica|EmailSecurity|Email_security|Impostazione di sicurezza del messaggio: **0** - Nessuno; **1** - Firmato; **2** - Crittografato; **3** - Crittografato e firmato.|
|Riservatezza della posta elettronica|EmailSensitivity|email_sensitivity|Impostazione di riservatezza del messaggio: **0** - Nessuno; **1** Personale; **2** - Privato; **3** - CompanyConfidential.|
|Set di messaggi di posta elettronica|EmailSet|Email_set|ID gruppo per tutti i messaggi nello stesso set di posta elettronica.|
|EmailThread*||Email_thread|Posizione del messaggio all'interno del set di messaggi di posta elettronica; è costituito da ID nodo dalla radice al messaggio corrente e sono separati da punti (.).|
|||Export_native_path|Percorso del file esportato.|
|Tipo di contenuto estratto||Native_type|Tipo di contenuto estratto sotto forma di tipo mime. ad esempio, **image/jpeg**|
|||Extracted_text_path|Percorso del file di testo estratto nell'esportazione.|
|ExtractedTextLength*||Extracted_text_length|Numero di caratteri nel testo estratto.|
|FamilyDuplicateSet*||Family_duplicate_set|Identificatore numerico per le famiglie che sono duplicati esatti l'uno dell'altro (stesso contenuto e tutti gli stessi allegati).|
|ID famiglia|FamilyId|Family_ID|Id famiglia raggruppa tutti gli elementi; per la posta elettronica, include il messaggio e tutti gli allegati; per i documenti, include il documento e tutti gli elementi incorporati.|
|Dimensioni famiglia||Family_size|Numero di documenti della famiglia.|
|Classe File|FileClass|File_class|Per il contenuto di SharePoint e OneDrive: **Document**; per il contenuto da Exchange: **Posta elettronica** o **Allegato.**|
|File ID|FileId|File_ID|Identificatore del documento univoco all'interno del caso.|
|Data di creazione del file system||File_system_date_created|Data di creazione dal file system (si applica solo ai dati non Office 365 dati).|
|Data di modifica del file system||File_system_date_modified|Data di modifica dal file system (si applica solo ai dati non Office 365 dati).|
|Tipo di file|FileType||Tipo di file dell'elemento in base all'estensione di file.|
|ID gruppo|GroupID||ID gruppo per il contenuto raggruppato.|
|Ha allegato|HasAttachment|Email_has_attachment|Indica se il messaggio contiene allegati.|
|Ha avvocato|HasAttorney||**True** quando almeno uno dei partecipanti viene trovato nell'elenco degli avvocati. in caso contrario, il valore è **False**.|
|HasText*||Has_text|Indica se l'elemento contiene testo. i valori possibili **sono True** e **False.**|
|ID non modificabile||Immutable_ID|Questo ID viene utilizzato per identificare in modo univoco un documento all'interno di un set di revisioni. Questo campo non può essere utilizzato in una ricerca di set di revisione e l'ID non può essere utilizzato per accedere a un documento nella posizione nativa.|
|Tipo inclusivo|InclusiveType|Inclusive_type|Tipo inclusivo calcolato per l'analisi: **0** - non inclusivo; **1** - inclusivo; **2** - inclusivo meno; **3** - Copia inclusiva.|
|In Risposta a ID||In_reply_to_ID|In risposta all'ID del messaggio.|
|InputFileExtension||Original_file_extension|Estensione di file originale del file.|
|InputFileID||Input_file_ID|ID file dell'elemento di primo livello nel set di revisioni. Per un allegato, questo ID sarà l'ID dell'elemento padre. Può essere usato per raggruppare le famiglie.|
|Allegato moderno| IsModernAttachment|  |Questo file è un allegato moderno o un file collegato.|
|È dalla versione del documento | IsFromDocumentVersion |  |Il documento corrente è di una versione diversa di un altro documento.|
|È allegato di posta elettronica | IsEmailAttachment|  |Questo elemento deriva da un allegato di posta elettronica visualizzato come elemento allegato al messaggio.|
|Allegato in linea| IsInlineAttachment|  |Questo messaggio è stato allegato in linea e viene visualizzato nel corpo del messaggio.|
|È rappresentativo|IsRepresentative|Is_representative|Un documento in ogni set di duplicati esatti viene contrassegnato come rappresentativo.|
|Classe Item|Itemclass|Item_class|Classe di elementi fornita dal server Exchange; ad esempio **IPM. Nota**|
|Last modified date|LastModifiedDate|Doc_date_modified|Data dell'ultima modifica dai metadati del documento.|
|Load ID|LoadId|Load_ID|ID del set di carico in cui l'elemento è stato aggiunto a un set di revisione.|
|Posizione|Posizione|Posizione|Stringa che indica il tipo di posizione da cui sono stati provenienti i documenti.<br /><br />**Dati importati** - Dati non Office 365 dati<br />**Teams** - Microsoft Teams<br />**Exchange** - Exchange cassette postali<br />**SharePoint** - SharePoint siti<br />**OneDrive** - OneDrive account|
|Nome percorso|LocationName|Location_name|Stringa che identifica l'origine dell'elemento. Per Exchange, questo sarà l'indirizzo SMTP della cassetta postale; per SharePoint e OneDrive, l'URL della raccolta siti.|
|||Marked_as_pivot|Questo file è il pivot in un set quasi duplicato.|
|Contrassegnato come rappresentativo|MarkAsRepresentative||Un documento di ogni set di duplicati esatti viene contrassegnato come rappresentanti.|
|Data fine riunione|MeetingEndDate|Meeting_end_date|Data di fine riunione per le riunioni.|
|Data inizio riunione|MeetingStartDate|Meeting_start_date|Data di inizio della riunione per le riunioni.|
|Tipo di messaggio|MessageKind|Message_kind|Tipo di messaggio da cercare. Valori possibili: contatti docs e-mail dati esterni fax im journals riunioni **<br /> <br /> <br /> <br /> <br /> <br /> <br /> <br /> <br /> <br /> microsoftteams** (restituisce elementi da chat, riunioni e chiamate in Microsoft Teams) note post **<br /> <br /> <br /> rssfeeds <br /> <br />** attività segreteria telefonica| 
|ID padre allegato moderno||ModernAttachment_ParentId|ID non modificabile dell'elemento padre del documento.|
|Estensione nativa|NativeExtension|Native_extension|Estensione nativa dell'elemento.|
|Nome file nativo|NativeFileName|Native_file_name|Nome file nativo dell'elemento.|
|NativeMD5||Native_MD5|Hash MD5 (valore hash a 128 bit) del flusso di file.|
|NativeSHA256||Native_SHA_256|Hash SHA256 (valore hash a 256 bit) del flusso di file.|
|ND/ET Sort: esclusione degli allegati|NdEtSortExclAttach|ND_ET_sort_excl_attach|Concatenazione del set di thread di posta elettronica (ET) e dell'insieme ND (Near-duplicate). Questo campo viene utilizzato per un ordinamento efficiente al momento della revisione. Una **D** è preceduta da set ND e **un E** è preceduto da set ET.|
|ND/ET Sort: inclusione di allegati|NdEtSortInclAttach|ND_ET_sort_incl_attach|Concatenazione di un set di thread di posta elettronica (ET) e di un set di ND (near-duplicate). Questo campo viene utilizzato per un ordinamento efficiente al momento della revisione. Una **D** è preceduta da set ND e **un E** è preceduto da set ET. Ogni elemento di posta elettronica in un insieme ET è seguito dai relativi allegati appropriati.|
|Autori di O365||O365_authors|Autore da SharePoint.|
|O365 creato da||O365_created_by|Creato da SharePoint.|
|Data di creazione di O365||O365_date_created|Data di creazione SharePoint.|
|Data di modifica di O365||O365_date_modified|Data dell'ultima modifica SharePoint.|
|O365 modificato da||O365_modified_by|Modificato da da SharePoint.|
|ID padre|ParentId|Container_ID|ID dell'elemento padre dell'elemento.|
|ParentNode||Parent_node|Il messaggio di posta elettronica precedente più vicino nel thread di posta elettronica.|
|Domini partecipanti|ParticipantDomains|Email_participant_domains|Elenco di tutti i domini dei partecipanti di un messaggio.|
|Partecipanti|Partecipanti|Email_participants|Elenco di tutti i partecipanti di un messaggio; ad esempio Mittente, A, Cc, Ccn.|
|Pivot ID|PivotId|Pivot_ID|ID di un pivot.|
|Potenzialmente privilegiato|PotentiallyPrivileged|Potentially_privileged|True se il modello di rilevamento dei privilegi avvocato-client considera il documento potenzialmente privilegiato|
|Stato elaborazione|ProcessingStatus|Error_code|Stato di elaborazione dopo l'aggiunta dell'elemento a un set di revisione.|
|Percentile di lettura|ReadPercentile||Percentile di lettura per il documento in base alla pertinenza.|
|Ricevuto|Ricevuto|Email_date_received|Data e ora in cui il messaggio di posta elettronica è stato ricevuto in formato UTC.|
|Numero destinatari||Recipient_count|Numero di destinatari nel messaggio.|
|Domini destinatari|RecipientDomains|Email_recipient_domains|Elenco di tutti i domini di destinatari di un messaggio.|
|Destinatari|Destinatari|Email_recipients|Elenco di tutti i destinatari di un messaggio (A, Cc, Ccn).|
|||Redacted_file_path|Percorso del file sostitutivo redatto nell'esportazione.|
|||Redacted_text_path|Percorso della sostituzione del file di testo nell'esportazione. Solo per uso interno di Microsoft.|
|Tag di pertinenza Caso 1||Relevance_tag_case_issue_1|Tag di pertinenza Caso 1 da Rilevanza.|
|Punteggio di pertinenza|RelevanceScore||Punteggio di pertinenza di un documento in base alla pertinenza.|
|Tag di pertinenza|RelevanceTag||Punteggio di pertinenza di un documento in base alla pertinenza.|
|ID rappresentante|RepresentativeId||Identificatore numerico di ogni set di duplicati esatti.|
|||Row_number|Numero di riga dell'elemento nel file di caricamento.|
|Mittente|Mittente|Email_sender|Campo Mittente (Da) per i tipi di messaggio. Il formato **è DisplayName \<SmtpAddress>**.|
|Mittente/Autore|SenderAuthor||Campo calcolato costituito dal mittente o dall'autore dell'elemento.|
|Dominio del mittente|SenderDomain|Email_sender_domain|Dominio del mittente.|
|Inviato|Inviato|Email_date_sent|Data di invio del messaggio.|
|Set Order: Inclusive First|SetOrderInclusivesFirst|Set_order_inclusives_first|Campo di ordinamento - posta elettronica e allegati: anti-cronologico; documents: pivot first then by descending similarity score.|
|SimilarityPercent||Similarity_percent|Indica quanto è simile un documento al pivot del set duplicato vicino.|
|Dimensioni native del file|Dimensioni|Native_size|Numero di byte dell'elemento nativo.|
|Oggetto|Oggetto|Email_subject|Oggetto del messaggio.|
|Oggetto/Titolo|SubjectTitle||Campo calcolato costituito dall'oggetto o dal titolo dell'elemento.|
|Tag|Tag|Tag|Tag applicati in un set di revisioni.|
|Elenco Temi|ThemesList|Themes_list|Elenco temi calcolato per l'analisi.|
|Titolo|Titolo|Doc_title|Titolo dai metadati del documento.|
|A|A|Email_to|Campo A per i tipi di messaggio. Il formato è **DisplayName \<SmtpAddress>**|
|Univoco nel set di posta elettronica|UniqueInEmailSet||**False** se è presente un duplicato dell'allegato nel relativo set di posta elettronica.|
|ID gruppo versione||Version_Group_Id|Raggruppa le diverse versioni dello stesso documento.|
|È stato corretti|WasRemediated|Was_Remediated|**True** se l'elemento è stato corretti, in caso contrario **False**.|
|Word count|WordCount|Word_count|Numero di parole nell'elemento.|
|||||

> [!NOTE]
> Per ulteriori informazioni sulle proprietà ricercabili durante la ricerca Office 365 percorsi di contenuto quando si raccolgono dati per un caso di Advanced eDiscovery, vedere Query con parole chiave e condizioni di ricerca per [Ricerca contenuto](keyword-queries-and-search-conditions.md).
