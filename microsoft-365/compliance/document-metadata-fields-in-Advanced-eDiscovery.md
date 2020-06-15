---
title: Campi dei metadati del documento in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: In questo articolo vengono definiti i campi dei metadati per i documenti in un set di revisione in un caso in Advanced eDiscovery in Microsoft 365.
ms.openlocfilehash: 19a8b4968ea4b1d82cd6a9e9278530e6c155ef3f
ms.sourcegitcommit: df6cc8c2eb2a65c7668f2953b0f7ec783a596d15
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/13/2020
ms.locfileid: "44726455"
---
# <a name="document-metadata-fields-in-advanced-ediscovery"></a>Campi dei metadati del documento in Advanced eDiscovery

Nella tabella seguente sono elencati i campi dei metadati per i documenti in un set di revisione in un caso in Advanced eDiscovery. La tabella contiene le informazioni seguenti:

- **Name campo e nome** campo di **visualizzazione:** nome del campo dei metadati e nome del campo visualizzato quando si visualizzano i metadati dei file di un documento selezionato in un set di revisione. Quando si visualizzano i metadati dei file di un documento, non vengono inclusi alcuni campi di metadati. Questi campi sono evidenziati con un asterisco (*).

- **Nome del campo ricercabile:** Nome della proprietà di cui è possibile eseguire la ricerca durante l'esecuzione di una [query del set di revisione](review-set-search.md). Una cella vuota indica che non è possibile cercare il campo in una query del set di revisione.

- **Nome del campo esportato:** Nome del campo dei metadati incluso quando vengono esportati i documenti.  Una cella vuota indica che il campo non è incluso nei metadati esportati.

- **Descrizione:** Descrizione del campo dei metadati.

> [!NOTE]
> Il campo **parole chiave** in [Review set Search](https://docs.microsoft.com/microsoft-365/compliance/review-set-search) utilizza Keyword Query Language (KQL). I campi elencati nella colonna **nome campo ricercabile** possono essere utilizzati nel campo **parole chiave** di una ricerca set di revisione per formare query complesse senza che sia necessario utilizzare il generatore di query. Per ulteriori informazioni su KQL, vedere [Keyword Query Language Reference Syntax](https://go.microsoft.com/fwlink/?LinkId=269603).

|Nome del **campo** e **nome del campo di visualizzazione**|**Nome del campo ricercabile**|**Nome del campo esportato**|**Descrizione**|
|:-----|:-----|:-----|:-----|
|ID contenuto allegato|AttachmentContentId||ID contenuto allegato dell'elemento.|
|Nomi degli allegati|AttachmentNames|Attachment_Names|Elenco di nomi degli allegati.|
|Punteggio Privilege del cliente del procuratore|AttorneyClientPrivilegeScore||Punteggio di contenuto del modello di privilegio avvocato-client.|
|Author|Author|Doc_authors|Autore dei metadati del documento.|
|Ccn|Ccn|Email_bcc|Campo Ccn per i tipi di messaggio. Format è **DisplayName \<SMTPAddress> **.|
|CC|CC|Email_cc|Campo CC per i tipi di messaggio. Format è **DisplayName \<SMTPAddress> **.|
|Etichette di conformità|ComplianceLabels|Compliance_labels|[Etichette di conservazione](labels.md) applicate ai contenuti di Office 365.|
|Percorso composto|CompoundPath|Compound_path|Percorso leggibile che descrive l'origine dell'elemento.|
|Contenuto|Contenuto||Testo estratto dell'elemento.|
|Corpo di conversazione|Corpo di conversazione||Corpo di conversazione dell'elemento.|
|Argomento di conversazione|Argomento di conversazione||Argomento relativo alla conversazione dell'elemento.|
|ID conversazione|ConversationId|Conversation_ID|ID conversazione dal messaggio.|
|Indice di conversazione||Conversation_index|Indice di conversazione dal messaggio.|
|Tempo di conversazione in formato PDF|ConversationPdfTime||Data in cui è stata creata la versione PDF della conversazione.|
|Tempo di infiammazione della conversazione|ConversationRedactionBurnTime||Data in cui è stata creata la versione PDF della conversazione per la chat.|
|Data di creazione del documento|CreatedTime|Doc_date_created|Creare la data dai metadati del documento.|
|Custode|Custode|Custode|Nome del custode a cui è stato associato l'elemento.|
|Data|Data|Data|La data è un campo calcolato che dipende dal tipo di file.<br /><br />Posta elettronica: data di invio<br />Allegati di posta elettronica: data dell'Ultima modifica del documento, se non disponibile, data di invio dell'elemento padre<br />Documenti incorporati: data dell'Ultima modifica del documento; Se non è disponibile, data dell'Ultima modifica dell'elemento padre<br />Documenti di SPO (inclusi gli allegati moderni): data dell'Ultima modifica di SharePoint; Se non è disponibile, la data dell'Ultima modifica del documento<br />Documenti non Office 365: data dell'Ultima modifica<br />Riunioni: data di inizio riunione<br />Segreteria telefonica: data di invio<br />IM: data di invio|
|Altri percorsi|Dedupedcompoundpath|Deduped_compound_path|Elenco di percorsi composti di documenti che sono duplicati esatti (posta elettronica: in base al contenuto, documenti: basato sull'hash).|
|Altri depositari|DedupedCustodians|Deduped_custodians|Elenco dei depositari dei documenti che sono duplicati esatti (per la posta elettronica, in base al contenuto, per i documenti, in base all'hash).|
|Altri ID file|DedupedFileIds|Deduped_file_IDs|Elenco di ID file dei documenti che sono duplicati esatti (per la posta elettronica, in base al contenuto, per i documenti, in base all'hash).|
|Commenti del documento|DocComments|Doc_comments|Commenti dei metadati del documento.|
|Azienda del documento||Doc_company|Azienda dei metadati del documento.|
|DocIndex*|||Indice della famiglia. **-1** o **0** indica che è la radice.|
|Parole chiave del documento||Doc_keywords|Parole chiave dei metadati del documento.|
|Documento modificato da||Doc_modified_by|Data dell'Ultima modifica da parte dei metadati del documento.|
|Revisione del documento||Doc_revision|Revisione dei metadati del documento.|
|Oggetto del documento||Doc_subject|Oggetto dei metadati del documento.|
|Modello di documento||Doc_template|Modello dei metadati del documento.|
|Tema dominante|DominantTheme|Dominant_theme|Tema dominante calcolato per l'analisi.|
|Sottoinsieme duplicato||Duplicate_subset|ID gruppo per duplicati esatti.|
|EmailAction*||Email_action|I valori sono **None**, **Reply**o **forward**; in base alla riga dell'oggetto di un messaggio.|
|Conferma di recapito della posta elettronica||Email_delivery_receipt|Indirizzo di posta elettronica fornito nelle intestazioni Internet per la ricezione del recapito.|
|Importanza|EmailImportance|Email_importance|Importanza del messaggio: **0** -basso; **1** -normale; **2** -alto|
|EmailLevel||Email_level|Indica il livello di un messaggio all'interno del thread di posta elettronica a cui appartiene; gli allegati ereditano il valore del messaggio padre.|
|ID messaggio di posta elettronica||Email_message_ID|ID messaggio Internet dal messaggio.|
|EmailReadReceipt*||Email_read_receipt|Indirizzo di posta elettronica fornito nelle intestazioni Internet per la conferma di lettura.|
|Sicurezza della posta elettronica|EmailSecurity|Email_security|Impostazione di sicurezza del messaggio: **0** -None; **1** -firmato; **2** -crittografato; **3** -crittografati e firmati.|
|Sensibilità della posta elettronica|EmailSensitivity|email_sensitivity|Impostazione della sensibilità del messaggio: **0** -None; **1** personale; **2** -privato; **3** -CompanyConfidential.|
|Set di messaggi di posta elettronica|Messaggi di posta elettronica|Email_set|ID gruppo per tutti i messaggi nello stesso set di posta elettronica.|
|EmailThread*||Email_thread|Posizione del messaggio all'interno del set di messaggi di posta elettronica; è costituito da ID di nodi dalla radice al messaggio corrente e separati da punti (.).|
|Tipo di contenuto Estratto||Extracted_content_type|Tipo di contenuto estratto, sotto forma di tipo MIME; ad esempio, **image/jpeg**|
|ExtractedTextLength*||Extracted_text_length|Numero di caratteri nel testo estratto.|
|Pertinenza della famiglia Punteggio caso problema 1 *||Family_relevance_score_case_issue_1|Pertinenza della famiglia Punteggio caso problema 1 dalla pertinenza.|
|FamilyDuplicateSet*||Family_duplicate_set|Identificatore numerico per le famiglie che sono duplicati esatti tra loro (stesso contenuto e tutti gli stessi allegati).|
|ID famiglia|FamilyId|Family_ID|Gruppi di ID famiglia insieme tutti gli elementi; per la posta elettronica, sono inclusi il messaggio e tutti gli allegati. per i documenti, sono inclusi il documento e tutti gli elementi incorporati.|
|Dimensione famiglia||Family_size|Numero di documenti nella famiglia.|
|Pertinenza del file score caso problema 1 *||File_relevance_score_case_issue_1|Numero di rilevanza dei file caso problema 1 dalla pertinenza.|
|Classe file|Fileclass|File_class|Per il contenuto di SharePoint e OneDrive: **Document**; per i contenuti di Exchange: **e-mail** o **allegato**.|
|ID file|FileId|File_ID|Identificatore di documento univoco all'interno del caso.|
|Data di creazione del file System||File_system_date_created|Data creazione dal file System (si applica solo ai dati non di Office 365).|
|Data del file System modificato||File_system_date_modified|Data di modifica del file System (si applica solo ai dati non di Office 365).|
|Tipo di file|FileType||Tipo di file dell'elemento in base all'estensione di file.|
|Ha allegato|HasAttachment|Email_has_attachment|Indica se il messaggio contiene allegati o meno.|
|Ha un avvocato|HasAttorney||Ha valore **true** se almeno uno dei partecipanti è presente nell'elenco degli avvocati. in caso contrario, il valore è **false**.|
|HasText||Has_text|Indica se il testo dell'elemento è o meno; i valori possibili sono **true** e **false**.|
|ID non modificabile||Immutable_ID|Questo ID viene utilizzato per identificare in modo univoco un documento all'interno di un set di revisione. Questo campo non può essere utilizzato in una ricerca set di revisione e l'ID non può essere utilizzato per accedere a un documento nel relativo percorso nativo.|
|Tipo inclusivo|InclusiveType|Inclusive_type|Tipo incluso calcolato per analisi: **0** -non incluso; **1** -Inclusive; **2** -incluso meno; copia **3** -inclusive.|
|In Rispondi a ID||In_reply_to_ID|In Rispondi a ID del messaggio.|
|È rappresentativo|Rappresentante|Is_representative|Un documento in ogni set di duplicati esatti è contrassegnato come rappresentante.|
|Classe Item|ItemClass|Item_class|Classe Item fornita da Exchange Server; ad esempio, **IPM. Note**|
|Last modified date|LastModifiedDate|Doc_date_modified|Data dell'Ultima modifica da metadati del documento.|
|ID di carico|LoadId|Load_ID|ID del set di carico in cui l'elemento è stato aggiunto a un set di revisione.|
|Posizione|Posizione|Posizione|Stringa che indica il tipo di percorso da cui sono stati provenienti i documenti.<br /><br />**Dati importati** -dati Non Office 365<br />**Teams** -Microsoft Teams<br />Cassette postali **di Exchange Exchange**<br />**SharePoint** -siti di SharePoint<br />**OneDrive** -account OneDrive|
|Nome percorso|LocationName|Location_name|Stringa che identifica l'origine dell'elemento. Per Exchange, questo sarà l'indirizzo SMTP della cassetta postale; per SharePoint e OneDrive, l'URL per la raccolta siti.|
|Contrassegnata come rappresentante|MarkAsRepresentative||Un documento di ogni gruppo di duplicati esatti è contrassegnato come rappresentanti.|
|Contrassegnata come problema di caso precontrassegnata 1 *||Marked_as_pre_tagged_Case_issue_1|Contrassegnata come problema di caso precontrassegnate 1 dalla pertinenza.|
|Contrassegnato come caso di Seed problema 1 *||Marked_as_seed_Case_issue_1|Contrassegnata come problema del Seed case 1 dalla pertinenza.|
|Data di fine riunione|MeetingEndDate|Meeting_end_date|Data di fine riunione per le riunioni.|
|Data di inizio riunione|MeetingStartDate|Meeting_start_date|Data di inizio della riunione per le riunioni.|
|Tipo di messaggio|MessageKind|Message_kind|Tipo di messaggio da cercare. Valori possibili: ** <br /> <br /> contatti <br /> documenti di <br /> posta elettronica <br /> externaldata <br /> Fax <br /> im <br /> Journals <br /> Meetings <br /> microsoftteams** (restituisce gli elementi da chat, riunioni e chiamate in Microsoft Teams) ** <br /> Note <br /> Post <br /> rssfeeds <br /> attività <br /> segreteria telefonica**| 
|Interno nativo|NativeExtension|Native_extension|Interno nativo dell'elemento.|
|Nome file nativo|NativeFileName|Native_file_name|Nome file nativo dell'elemento.|
|NativeMD5||Native_MD5|Hash MD5 (valore hash a 128 bit) del flusso di file.|
|NativeSHA256||Native_SHA_256|Hash SHA256 (valore hash a 256 bit) del flusso di file.|
|Ordinamento ND/ET: esclusione degli allegati|NdEtSortExclAttach|ND_ET_sort_excl_attach|Concatenazione del set di thread di posta elettronica e del set di quasi duplicati (ND). Questo campo viene utilizzato per l'ordinamento efficiente al momento della revisione. Un **D** è preceduto da set ND e un **e** è preceduto ai set di et.|
|Ordinamento ND/ET: inclusi gli allegati|NdEtSortInclAttach|ND_ET_sort_incl_attach|Concatenazione di un set di thread di posta elettronica e di set quasi duplicati (ND). Questo campo viene utilizzato per l'ordinamento efficiente al momento della revisione. Un **D** è preceduto da set ND e un **e** è preceduto ai set di et. Ogni elemento di posta elettronica in un set di ET è seguito dagli allegati corretti.|
|Rilevanza normalizzata caso problema 1||Normalized_relevance_score_case_issue_1|Rilevanza normalizzata caso problema 1 dalla pertinenza.|
|Autori di O365||O365_authors|Autore da SharePoint.|
|O365 creato da||O365_created_by|Creato da da SharePoint.|
|Data di O365 creata||O365_date_created|Data di creazione da SharePoint.|
|Data di O365 modificata||O365_date_modified|Data dell'Ultima modifica di SharePoint.|
|O365 modificato da||O365_modified_by|Modificato da da SharePoint.|
|ID padre|ParentId|Parent_ID|ID del padre dell'elemento.|
|ParentNode||Parent_node|Il messaggio di posta elettronica precedente più vicino nel thread di posta elettronica.|
|Percorso padre|ParentPath|Parent_path|Percorso composto del padre diretto dell'elemento.|
|Domini dei partecipanti|ParticipantDomains|Email_participant_domains|Elenco di tutti i domini dei partecipanti di un messaggio.|
|Partecipanti|Partecipanti|Email_participants|Elenco di tutti i partecipanti a un messaggio; ad esempio, sender, to, CC, BCC.|
|ID pivot|PivotId|Pivot_ID|ID di un pivot.|
|Potenzialmente privilegiati|PotentiallyPrivileged|Potentially_privileged|True se il modello di rilevamento dei privilegi avvocato-client considera il documento potenzialmente privilegiato|
|Stato di elaborazione|ProcessingStatus|Error_code|Stato di elaborazione dopo che l'elemento è stato aggiunto a un set di revisione.|
|Leggere la percentuale del caso numero 1||Read_percent_Case_issue_1|Leggere la percentuale di caso numero 1 dalla pertinenza.|
|Lettura percentile|ReadPercentile||Leggere il percentile per il documento in base alla pertinenza.|
|Numero destinatari||Recipient_count|Numero di destinatari nel messaggio.|
|Domini destinatario|RecipientDomains|Email_recipient_domains|Elenco di tutti i domini dei destinatari di un messaggio.|
|Destinatari|Destinatari|Email_recipients|Elenco di tutti i destinatari di un messaggio (to, CC, BCC).|
|Problema del gruppo di carico di pertinenza 1||Relevance_load_group_case_issue_1|Problema del gruppo di carico di rilevanza 1 dalla pertinenza.|
|Stato pertinenza Descrizione caso problema 1||Relevance_status_description_Case_issue_1|Stato di pertinenza Descrizione caso problema 1 dalla pertinenza.|
|Tag di pertinenza caso problema 1||Relevance_tag_case_issue_1|Tag di pertinenza caso problema 1 dalla pertinenza.|
|Commento pertinenza||Relevance_comment|Campo dei commenti dalla pertinenza.|
|Punteggio di pertinenza|RelevanceScore||Punteggio di pertinenza di un documento in base alla pertinenza.|
|Tag pertinenza|RelevanceTag||Punteggio di pertinenza di un documento in base alla pertinenza.|
|ID rappresentativo|RepresentativeId||Identificatore numerico di ogni set di duplicati esatti.|
|Mittente|Mittente|Email_sender|Campo mittente (da) per i tipi di messaggio. Format è **DisplayName \<SmtpAddress> **.|
|Mittente/autore|SenderAuthor||Campo calcolato composto dal mittente o dall'autore dell'elemento.|
|Dominio mittente|SenderDomain|Email_sender_domain|Dominio del mittente.|
|Inviati|Inviati|Email_date_sent|Data di invio del messaggio.|
|Imposta ordine: First Inclusive|SetOrderInclusivesFirst|Set_order_inclusives_first|Campo di ordinamento-posta elettronica e allegati: contatore cronologico; documenti: pivot prima quindi discendendo Punteggio di somiglianza.|
|SimilarityPercent||Similarity_percent|Indica il modo in cui un documento è simile al pivot del set di duplicati vicino.|
|Dimensioni dei file nativi|Dimensioni|Native_size|Numero di byte dell'elemento nativo.|
|Oggetto|Oggetto|Email_subject|Oggetto del messaggio.|
|Subject/title|SubjectTitle||Campo calcolato che include l'oggetto o il titolo dell'elemento.|
|Tag per caso problema 1||Tagged_by_Case_issue_1|Utente che ha contrassegnato questo documento per il caso problema 1 in rilevanza.|
|Categorie|Categorie|Categorie|Tag applicati in un set di revisione.|
|Elenco temi|Tema|Themes_list|Elenco temi come calcolato per l'analisi.|
|Titolo|Titolo|Doc_title|Titolo dei metadati del documento.|
|A|A|Email_to|To Field per i tipi di messaggio. Il formato **è \<SmtpAddress> DisplayName**|
|Univoco nel set di posta elettronica|UniqueInEmailSet||**False** se è presente un duplicato dell'allegato nel relativo set di posta elettronica.|
|È stato rimediato|WasRemediated|Was_Remediated|Ha valore **true** se l'elemento è stato rimediato, altrimenti **false**.|
|Word count|WordCount|Word_count|Numero di parole nell'elemento.|
|||||

> [!NOTE]
> Per ulteriori informazioni sulle proprietà disponibili per la ricerca durante la ricerca di percorsi di contenuto di Office 365 quando si raccolgono dati per un caso avanzato di eDiscovery, vedere [keyword queries and Search Conditions for content search](keyword-queries-and-search-conditions.md).
