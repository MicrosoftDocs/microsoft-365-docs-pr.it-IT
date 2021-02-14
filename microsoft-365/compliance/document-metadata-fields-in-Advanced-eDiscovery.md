---
title: Campi dei metadati dei documenti in Advanced eDiscovery
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
description: Questo articolo definisce i campi dei metadati per i documenti in una recensione impostata in un caso in Advanced eDiscovery in Microsoft 365.
ms.openlocfilehash: 2bf9773f6c36e53231bb577c30e9900bf3e24df7
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358444"
---
# <a name="document-metadata-fields-in-advanced-ediscovery"></a>Campi dei metadati del documento in Advanced eDiscovery

Nella tabella seguente sono elencati i campi dei metadati per i documenti in un insieme da rivedere in un caso in Advanced eDiscovery. Nella tabella sono disponibili le informazioni seguenti:

- **Nome campo** e nome campo **visualizzato:** il nome del campo dei metadati e il nome del campo visualizzato quando si visualizzano i metadati del file di un documento selezionato in un insieme da rivedere. Alcuni campi di metadati non vengono inclusi quando si visualizzano i metadati del file di un documento. Questi campi sono evidenziati con un asterisco (*).

- **Nome campo ricercabile:** Nome della proprietà che è possibile cercare quando si esegue una [query di insieme da rivedere.](review-set-search.md) Una cella vuota indica che non è possibile cercare il campo in una query di insieme da rivedere.

- **Nome campo esportato:** Nome del campo dei metadati incluso durante l'esportazione dei documenti.  Una cella vuota indica che il campo non è incluso nei metadati esportati.

- **Descrizione:** Descrizione del campo dei metadati.

> [!NOTE]
> Il **campo Parole** chiave nella ricerca di set da [rivedere](https://docs.microsoft.com/microsoft-365/compliance/review-set-search) utilizza Keyword Query Language (KQL). I campi elencati nella colonna **Nome** campo  ricercabile possono essere utilizzati nel campo Parole chiave in un insieme di ricerche da rivedere per creare query complesse senza dover utilizzare il generatore di query. Per ulteriori informazioni su KQL, vedere Informazioni di riferimento [sulla sintassi di Keyword Query Language.](https://go.microsoft.com/fwlink/?LinkId=269603)

|**Nome campo** e **nome campo visualizzato**|**Nome campo ricercabile**|**Nome campo esportato**|**Descrizione**|
|:-----|:-----|:-----|:-----|
|ID contenuto allegato|AttachmentContentId||ID contenuto allegato dell'elemento.|
|Nomi allegati|AttachmentNames|Attachment_Names|Elenco di nomi di allegati.|
|Punteggio privilegio avvocato client|AttorneyClientPrivilegeScore||Punteggio del contenuto del modello di privilegio avvocato-client.|
|Author|Author|Doc_authors|Autore dai metadati del documento.|
|Ccn|Ccn|Email_bcc|Campo Ccn per i tipi di messaggio. Il formato **è DisplayName. \<SMTPAddress>**|
|CC|Cc|Email_cc|Campo Cc per i tipi di messaggio. Il formato **è DisplayName. \<SMTPAddress>**|
|Etichette di conformità|ComplianceLabels|Compliance_labels|[Etichette di](retention.md) conservazione applicate al contenuto in Office 365.|
|Percorso composto|CompoundPath|Compound_path|Percorso leggibile che descrive l'origine dell'elemento.|
|Content*|Contenuto||Testo estratto dell'elemento.|
|Corpo della conversazione|Corpo della conversazione||Corpo della conversazione dell'elemento.|
|Argomento conversazione|Argomento conversazione||Argomento di conversazione dell'elemento.|
|ID conversazione|ConversationId|Conversation_ID|ID conversazione dal messaggio.|
|Indice conversazione||Conversation_index|Indice della conversazione dal messaggio.|
|Ora pdf conversazione|ConversationPdfTime||Data di creazione della versione PDF della conversazione.|
|Tempo di masterizzazione della redazione della conversazione|ConversationRedactionBurnTime||Data in cui è stata creata la versione PDF della conversazione per Chat.|
|Data di creazione del documento|CreatedTime|Doc_date_created|Creare la data dai metadati del documento.|
|Responsabile|Responsabile|Responsabile|Nome del responsabile a cui è stato associato l'elemento.|
|Data|Data|Data|La data è un campo calcolato che dipende dal tipo di file.<br /><br />Email: Sent date<br />Allegati di posta elettronica: data dell'ultima modifica del documento; se non disponibile, data di invio dell'elemento padre<br />Documenti incorporati: data dell'ultima modifica del documento; se non disponibile, la data dell'ultima modifica dell'elemento padre<br />Documenti di SharePoint SharePoint (inclusi gli allegati moderni): data dell'ultima modifica di SharePoint; se non disponibile, la data dell'ultima modifica dei documenti<br />Documenti non di Office 365: data dell'ultima modifica<br />Riunioni: data di inizio della riunione<br />VoiceMail: Data di invio<br />Messaggistica istantanea: data di invio|
|Altri percorsi|Dedupedcompoundpath|Deduped_compound_path|Elenco di percorsi composti di documenti che sono duplicati esatti (posta elettronica: in base al contenuto, documenti: in base all'hash).|
|Altri responsabile|DedupedCustodians|Deduped_custodians|Elenco dei responsabile dei documenti che sono duplicati esatti (per la posta elettronica, in base al contenuto, per i documenti, in base all'hash).|
|Altri ID file|DedupedFileIds|Deduped_file_IDs|Elenco di ID file di documenti che sono duplicati esatti (per la posta elettronica, in base al contenuto, per i documenti, in base all'hash).|
|Commenti documento|DocComments|Doc_comments|Commenti dai metadati del documento.|
|Documentare la società||Doc_company|Società dai metadati del documento.|
|DocIndex*|||Indice della famiglia. **-1** o **0** indica che è la radice.|
|Parole chiave del documento||Doc_keywords|Parole chiave dai metadati del documento.|
|Documento modificato da||Doc_modified_by|Data dell'ultima modifica in base ai metadati del documento.|
|Revisione documento||Doc_revision|Revisione dai metadati del documento.|
|Oggetto documento||Doc_subject|Oggetto dai metadati del documento.|
|Modello di documento||Doc_template|Modello dai metadati del documento.|
|Tema dominante|DominantTheme|Dominant_theme|Tema dominante calcolato per l'analisi.|
|Sottoinsieme duplicato||Duplicate_subset|ID gruppo per duplicati esatti.|
|EmailAction*||Email_action|I valori **sono None,** **Reply** o **Forward;** in base all'oggetto di un messaggio.|
|Conferma recapito posta elettronica||Email_delivery_receipt|Indirizzo di posta elettronica fornito nelle intestazioni Internet per la conferma di recapito.|
|Priorità|EmailImportance|Email_importance|Importanza del messaggio: **0** - Basso; **1** - Normale; **2** - Alto|
|EmailLevel*||Email_level|Indica il livello di un messaggio all'interno del thread di posta elettronica a cui appartiene; gli allegati ereditano il valore del messaggio padre.|
|ID messaggio di posta elettronica||Email_message_ID|ID messaggio Internet del messaggio.|
|EmailReadReceipt*||Email_read_receipt|Indirizzo di posta elettronica fornito nelle intestazioni Internet per la conferma di lettura.|
|Sicurezza della posta elettronica|EmailSecurity|Email_security|Impostazione di sicurezza del messaggio: **0** - Nessuno; **1** - Firmato; **2** - Crittografato; **3** - Crittografato e firmato.|
|Riservatezza della posta elettronica|EmailSensitivity|email_sensitivity|Impostazione di riservatezza del messaggio: **0** - Nessuno; **1** Personale; **2** - Privato; **3** - CompanyConfidential.|
|Set di e-mail|EmailSet|Email_set|ID gruppo per tutti i messaggi nello stesso set di posta elettronica.|
|EmailThread*||Email_thread|Posizione del messaggio all'interno del set di e-mail; è costituito da ID nodo dalla radice al messaggio corrente e separati da punti (.).|
|Tipo di contenuto estratto||Extracted_content_type|Tipo di contenuto estratto sotto forma di tipo mime; ad esempio **image/jpeg**|
|ExtractedTextLength*||Extracted_text_length|Numero di caratteri nel testo estratto.|
|Punteggio di pertinenza della famiglia Caso problema 1*||Family_relevance_score_case_issue_1|Punteggio di pertinenza della famiglia Caso numero 1 dalla rilevanza.|
|FamilyDuplicateSet*||Family_duplicate_set|Identificatore numerico per le famiglie che sono duplicati esatti l'uno dell'altro (stesso contenuto e tutti gli stessi allegati).|
|ID famiglia|FamilyId|Family_ID|Id famiglia raggruppa tutti gli elementi; per la posta elettronica, questo include il messaggio e tutti gli allegati; per i documenti, sono inclusi il documento e gli elementi incorporati.|
|Dimensioni famiglia||Family_size|Numero di documenti della famiglia.|
|Punteggio di pertinenza file Caso problema 1*||File_relevance_score_case_issue_1|Punteggio di pertinenza file Caso 1 dalla rilevanza.|
|Classe file|FileClass|File_class|Per il contenuto di SharePoint e OneDrive: **Documento;** per il contenuto di Exchange: **posta elettronica** o **allegato.**|
|File ID|FileId|File_ID|Identificatore di documento univoco all'interno del caso.|
|Data di creazione del file system||File_system_date_created|Data di creazione dal file system (si applica solo ai dati non di Office 365).|
|Data di modifica del file system||File_system_date_modified|Data di modifica dal file system (si applica solo ai dati non di Office 365).|
|Tipo di file|FileType||Tipo di file dell'elemento in base all'estensione di file.|
|ID gruppo| GroupID|  |ID gruppo per il contenuto raggruppato.|
|Ha allegato|HasAttachment|Email_has_attachment|Indica se il messaggio contiene allegati.|
|Ha avvocato|HasAttorney||**True** quando almeno uno dei partecipanti viene trovato nell'elenco degli avvocati. in caso contrario, il valore è **False.**|
|HasText*||Has_text|Indica se l'elemento contiene testo. i valori possibili **sono True** e **False.**|
|ID non modificabile||Immutable_ID|Questo ID viene utilizzato per identificare in modo univoco un documento all'interno di un insieme da rivedere. Questo campo non può essere utilizzato in una ricerca di set di recensioni e l'ID non può essere utilizzato per accedere a un documento nella posizione nativa.|
|Tipo inclusivo|InclusiveType|Inclusive_type|Tipo inclusivo calcolato per l'analisi: **0** - non inclusivo; **1** - inclusivo; **2** - inclusive minus; **3** - Copia inclusiva.|
|In Risposta a ID||In_reply_to_ID|In risposta all'ID del messaggio.|
|Allegato moderno| IsModernAttachment|  |Questo file è un allegato moderno o un file collegato.|
|Deriva dalla versione del documento | IsFromDocumentVersion |  |Il documento corrente è di una versione diversa di un altro documento.|
|Allegato di posta elettronica | IsEmailAttachment|  |Questo elemento deriva da un allegato di posta elettronica che viene visualizzato come elemento allegato al messaggio.|
|Allegato inline| IsInlineAttachment|  |È stato allegato in linea e viene visualizzato nel corpo del messaggio.|
|È rappresentativo|IsRepresentative|Is_representative|Un documento in ogni set di duplicati esatti viene contrassegnato come rappresentativo.|
|Classe item|Itemclass|Item_class|Classe di elementi fornita dal server Exchange; ad esempio **IPM. Nota**|
|Last modified date|LastModifiedDate|Doc_date_modified|Data dell'ultima modifica dai metadati del documento.|
|Load ID|LoadId|Load_ID|ID del set di carico in cui l'elemento è stato aggiunto a un insieme da rivedere.|
|Posizione|Posizione|Posizione|Stringa che indica il tipo di posizione da cui sono stati provenienti i documenti.<br /><br />**Dati importati** - Dati non di Office 365<br />**Teams** - Microsoft Teams<br />**Exchange** - Cassette postali di Exchange<br />**SharePoint** - Siti di SharePoint<br />**OneDrive** - Account di OneDrive|
|Nome della posizione|LocationName|Location_name|Stringa che identifica l'origine dell'elemento. Per Exchange, questo sarà l'indirizzo SMTP della cassetta postale; per SharePoint e OneDrive, l'URL della raccolta siti.|
|Contrassegnato come rappresentativo|MarkAsRepresentative||Un documento di ogni set di duplicati esatti viene contrassegnato come rappresentanti.|
|Contrassegnato come problema del caso pre tagged 1*||Marked_as_pre_tagged_Case_issue_1|Contrassegnato come caso pre tagged numero 1 dalla rilevanza.|
|Contrassegnato come seed case issue 1*||Marked_as_seed_Case_issue_1|Contrassegnato come caso di seme numero 1 dalla rilevanza.|
|Data di fine riunione|MeetingEndDate|Meeting_end_date|Data di fine della riunione per le riunioni.|
|Data di inizio riunione|MeetingStartDate|Meeting_start_date|Data di inizio della riunione per le riunioni.|
|Tipo di messaggio|MessageKind|Message_kind|Tipo di messaggio da cercare. Valori possibili: contacts **<br /> <br /> <br /> docs <br /> email <br /> externaldata <br /> faxes <br /> im <br /> journals meetings <br /> <br /> microsoftteams** (returns items from chats, meetings, and calls in Microsoft Teams) **<br /> notes posts <br /> <br /> rssfeeds <br /> tasks <br /> voicemail**| 
|Estensione nativa|NativeExtension|Native_extension|Estensione nativa dell'elemento.|
|Nome file nativo|NativeFileName|Native_file_name|Nome file nativo dell'elemento.|
|NativeMD5||Native_MD5|Hash MD5 (valore hash a 128 bit) del flusso di file.|
|NativeSHA256||Native_SHA_256|Hash SHA256 (valore hash a 256 bit) del flusso di file.|
|Ordinamento ND/ET: esclusione degli allegati|NdEtSortExclAttach|ND_ET_sort_excl_attach|Concatenazione del set di thread di posta elettronica (ET) e del set di ND (Near-duplicate). Questo campo viene utilizzato per un ordinamento efficiente in fase di revisione. Una **D** è preceduta da set di ND e **un E** è preceduto da set ET.|
|Ordinamento ND/ET: allegati inclusi|NdEtSortInclAttach|ND_ET_sort_incl_attach|Concatenazione di un set di thread di posta elettronica (ET) e di un set di ND (near-duplicate). Questo campo viene utilizzato per un ordinamento efficiente in fase di revisione. Una **D** è preceduta da set di ND e **un E** è preceduto da set ET. Ogni elemento di posta elettronica in un insieme et è seguito dai relativi allegati appropriati.|
|Punteggio di pertinenza normalizzato Caso problema 1||Normalized_relevance_score_case_issue_1|Punteggio di pertinenza normalizzato Caso 1 dalla rilevanza.|
|Autori di O365||O365_authors|Autore da SharePoint.|
|O365 creato da||O365_created_by|Creato da SharePoint.|
|Data di creazione di O365||O365_date_created|Data di creazione da SharePoint.|
|Data di modifica di O365||O365_date_modified|Data dell'ultima modifica da SharePoint.|
|O365 modificato da||O365_modified_by|Modificato da SharePoint.|
|ID padre|ParentId|Parent_ID|ID dell'elemento padre.|
|ParentNode||Parent_node|Il messaggio di posta elettronica precedente più vicino nel thread di posta elettronica.|
|Percorso padre|ParentPath|Parent_path|Percorso composto dell'elemento padre diretto dell'elemento.|
|Domini partecipante|ParticipantDomains|Email_participant_domains|Elenco di tutti i domini dei partecipanti di un messaggio.|
|Partecipanti|Partecipanti|Email_participants|Elenco di tutti i partecipanti di un messaggio; ad esempio Mittente, A, Cc, Ccn.|
|Pivot ID|PivotId|Pivot_ID|ID di un pivot.|
|Potenzialmente privilegiato|PotentiallyPrivileged|Potentially_privileged|True se il modello di rilevamento dei privilegi avvocato-client considera il documento potenzialmente privilegiato|
|Stato elaborazione|ProcessingStatus|Error_code|Stato di elaborazione dopo l'aggiunta dell'elemento a un insieme da rivedere.|
|Lettura della percentuale di casi emissione 1||Read_percent_Case_issue_1|Leggere la percentuale di casi numero 1 dalla rilevanza.|
|Percentile di lettura|ReadPercentile||Percentile di lettura per il documento in base alla rilevanza.|
|Numero destinatari||Recipient_count|Numero di destinatari nel messaggio.|
|Domini destinatario|RecipientDomains|Email_recipient_domains|Elenco di tutti i domini dei destinatari di un messaggio.|
|Destinatari|Destinatari|Email_recipients|Elenco di tutti i destinatari di un messaggio (A, Cc, Ccn).|
|Problema 1 del gruppo di caricamento per pertinenza||Relevance_load_group_case_issue_1|Caso 1 del gruppo di caricamento per pertinenza dalla rilevanza.|
|Descrizione stato pertinenza Caso problema 1||Relevance_status_description_Case_issue_1|Descrizione dello stato di pertinenza Caso 1 dalla rilevanza.|
|Caso di tag di pertinenza 1||Relevance_tag_case_issue_1|Caso del tag di pertinenza 1 dalla rilevanza.|
|Commento per pertinenza||Relevance_comment|Campo Commento da Rilevanza.|
|Punteggio di pertinenza|RelevanceScore||Punteggio di pertinenza di un documento in base alla rilevanza.|
|Tag di pertinenza|RelevanceTag||Punteggio di pertinenza di un documento in base alla rilevanza.|
|ID rappresentante|RepresentativeId||Identificatore numerico di ogni set di duplicati esatti.|
|Mittente|Mittente|Email_sender|Campo Mittente (Da) per i tipi di messaggio. Il formato **è DisplayName. \<SmtpAddress>**|
|Mittente/Autore|SenderAuthor||Campo calcolato costituito dal mittente o dall'autore dell'elemento.|
|Dominio del mittente|SenderDomain|Email_sender_domain|Dominio del mittente.|
|Inviato|Inviato|Email_date_sent|Data di invio del messaggio.|
|Set Order: Inclusive First|SetOrderInclusivesFirst|Set_order_inclusives_first|Campo di ordinamento - posta elettronica e allegati: anti-cronologico; documents: pivot first then by descending similarity score.|
|SimilarityPercent||Similarity_percent|Indica l'analoga tra un documento e il pivot del set di duplicati vicini.|
|Dimensioni dei file nativi|Dimensioni|Native_size|Numero di byte dell'elemento nativo.|
|Oggetto|Oggetto|Email_subject|Oggetto del messaggio.|
|Oggetto/Titolo|SubjectTitle||Campo calcolato costituito dall'oggetto o dal titolo dell'elemento.|
|Tagged by Case issue 1||Tagged_by_Case_issue_1|Utente che ha contrassegnato questo documento per il caso 1 in Rilevanza.|
|Tag|Tag|Tag|Tag applicati in un insieme da rivedere.|
|Elenco Temi|ThemesList|Themes_list|Elenco temi calcolato per l'analisi.|
|Titolo|Titolo|Doc_title|Titolo dai metadati del documento.|
|A|A|Email_to|Campo A per i tipi di messaggio. Il formato **è DisplayName \<SmtpAddress>**|
|Univoco nel set di e-mail|UniqueInEmailSet||**False** se è presente un duplicato dell'allegato nel set di e-mail.|
|È stato corretti|WasRemediated|Was_Remediated|**True** se l'elemento è stato corretti, altrimenti **False.**|
|Word count|WordCount|Word_count|Numero di parole nell'elemento.|
|||||

> [!NOTE]
> Per ulteriori informazioni sulle proprietà disponibili per la ricerca nelle posizioni dei contenuti di Office 365 quando si raccolgono dati per un caso di Advanced eDiscovery, vedere Query con parole chiave e condizioni di ricerca per [Ricerca contenuto.](keyword-queries-and-search-conditions.md)
