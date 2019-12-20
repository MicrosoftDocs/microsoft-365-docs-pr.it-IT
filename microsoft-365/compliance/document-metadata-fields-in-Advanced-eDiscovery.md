---
title: Campi dei metadati del documento in Advanced eDiscovery
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
description: ''
ms.openlocfilehash: 39ce4518e12b4446b339cbf7341a354bf5bd8876
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2019
ms.locfileid: "40805969"
---
# <a name="document-metadata-fields-in-advanced-ediscovery"></a>Campi dei metadati del documento in Advanced eDiscovery

Nella tabella seguente sono elencati i campi dei metadati per i documenti in un set di revisione in un caso in Advanced eDiscovery. La tabella contiene le informazioni seguenti:

- Nome del campo dei metadati (nella colonna **nome campo** ).

- Nome della proprietà di cui è possibile eseguire la ricerca durante l'esecuzione di una [query del set di revisione](review-set-search.md) (nella colonna **nome campo ricercabile** ). Una cella vuota indica che non è possibile cercare il campo in una query del set di revisione.

- Nome del campo dei metadati incluso quando vengono esportati i documenti (nella colonna **nome campo esportato** ).  Una cella vuota indica che il campo meta data non è incluso nei metadati esportati.

- Nome del campo dei metadati visualizzato quando si visualizzano i metadati dei file di un documento selezionato in un set di revisione (nella colonna **nome campo di visualizzazione** ). Una cella vuota indica che il campo metadati non è incluso quando si visualizzano i file di dati di un documento.

- Descrizione del campo meta data (nella **colonna Descrizione**).

|Nome del campo|Nome del campo ricercabile|Nome del campo esportato|Nome del campo di visualizzazione|Descrizione|
|:-|:-|:-|:-|:-|
| ID contenuto allegato | AttachmentContentId |  | ID contenuto allegato | ID contenuto allegato dell'elemento. |
| Nomi degli allegati | AttachmentNames | Attachment_Names | Nomi degli allegati | Elenco di nomi degli allegati. |
| Punteggio Privilege del cliente del procuratore | AttorneyClientPrivilegeScore |  | Punteggio Privilege del cliente del procuratore | Punteggio di contenuto del modello di privilegio avvocato-client. |
| Author | Author | Doc_authors | Author | Autore dei metadati del documento. |
| Ccn | Ccn | Email_bcc | Ccn | Campo Ccn per i tipi di messaggio.  Format è **DisplayName \<SmtpAddress>**. |
| CC | CC | Email_cc | CC | Campo CC per i tipi di messaggio.  Format è **DisplayName \<SmtpAddress>**. |
| Etichette di conformità | ComplianceLabels | Compliance_labels | Etichette di conformità |[Etichette di conservazione](labels.md) applicate ai contenuti di Office 365. |
| Percorso composto | CompoundPath | Compound_path | Percorso composto | Percorso leggibile che descrive l'origine dell'elemento. |
| Contenuto | Contenuto |  |  | Testo estratto dell'elemento. |
| Corpo di conversazione | Corpo di conversazione |  | Corpo di conversazione | Corpo di conversazione dell'elemento. |
| Argomento di conversazione | Argomento di conversazione |  | Argomento di conversazione | Argomento relativo alla conversazione dell'elemento. |
| ID conversazione | ConversationId | Conversation_ID | ID conversazione | ID conversazione dal messaggio. |
| Indice di conversazione |  | Conversation_index | Indice di conversazione | Indice di conversazione dal messaggio. |
| Tempo di conversazione in formato PDF | ConversationPdfTime |  | Tempo di conversazione in formato PDF | Data in cui è stata creata la versione PDF della conversazione. |
| Tempo di infiammazione della conversazione | ConversationRedactionBurnTime |  | Tempo di infiammazione della conversazione | Data in cui è stata creata la versione PDF della conversazione per la chat. |
| Data di creazione del documento | CreatedTime | Doc_date_created | Data di creazione del documento | Creare la data dai metadati del documento. |
| Custode | Custode | Custode | Custode | Nome del custode a cui è stato associato l'elemento. |
| Data | Data | Data | Data | La data è un campo calcolato che dipende dal tipo di file.<br />**Posta elettronica**: data di invio<br />**Allegati di posta elettronica**: data dell'Ultima modifica del documento, se non disponibile, data di invio dell'elemento padre<br />**Documenti incorporati**: data dell'Ultima modifica del documento, se non disponibile, data dell'Ultima modifica dell'elemento padre.<br />**Documenti di SPO (inclusi gli allegati moderni)**: data dell'Ultima modifica di SharePoint, se non disponibile, data dell'Ultima modifica del documento<br />**Documenti non Office**: data dell'Ultima modifica<br />**Riunioni**: data di inizio riunione<br />**Segreteria telefonica**: data di invio<br />**Im**: data di invio. |
| Altri percorsi | Dedupedcompoundpath | Deduped_compound_path | Altri percorsi | Elenco di percorsi composti di documenti che sono duplicati esatti (posta elettronica: in base al contenuto, documenti: basato sull'hash). |
| Altri depositari | DedupedCustodians | Deduped_custodians | Altri depositari | Elenco dei depositari dei documenti che sono duplicati esatti (per la posta elettronica: in base al contenuto, per i documenti: basati su hash). |
| Altri ID file | DedupedFileIds | Deduped_file_IDs | Altri ID file | Elenco di ID file di documenti che sono duplicati esatti (per la posta elettronica: in base al contenuto, per i documenti: basati su hash). |
| Commenti del documento | DocComments | Doc_comments | Commenti del documento | Commenti dei metadati del documento. |
| Azienda del documento |  | Doc_company | Azienda del documento | Azienda dei metadati del documento. |
| DocIndex |  |  |  | Indice della famiglia. -1 o 0 indica che è la radice. |
| Parole chiave del documento |  | Doc_keywords | Parole chiave del documento | Parole chiave dei metadati del documento. |
| Documento modificato da |  | Doc_modified_by | Documento modificato da | Data dell'Ultima modifica da parte dei metadati del documento. |
| Revisione del documento |  | Doc_revision | Revisione del documento | Revisione dei metadati del documento. |
| Oggetto del documento |  | Doc_subject | Oggetto del documento | Oggetto dei metadati del documento. |
| Modello di documento |  | Doc_template | Modello di documento | Modello dei metadati del documento. |
| Tema dominante | DominantTheme | Dominant_theme | Tema dominante | Tema dominante calcolato per l'analisi. |
| Sottoinsieme duplicato |  | Duplicate_subset | Sottoinsieme duplicato | ID gruppo per duplicati esatti. |
| EmailAction |  | Email_action |  | None, Rispondi, inoltra in base alla riga dell'oggetto di un messaggio. |
| Conferma di recapito della posta elettronica |  | Email_delivery_receipt | Conferma di recapito della posta elettronica | Indirizzo di posta elettronica fornito nelle intestazioni Internet per la ricezione del recapito. |
| Importanza | EmailImportance | Email_importance | Importanza | Importanza del messaggio: **0**: basso; **1**: normale; **2**: alto |
| EmailLevel |  | Email_level |  | Indica il livello di un messaggio all'interno del thread di posta elettronica a cui appartiene; gli allegati ereditano il valore del messaggio padre. |
| ID messaggio di posta elettronica |  | Email_message_ID | ID messaggio di posta elettronica | ID messaggio Internet dal messaggio. |
| EmailReadReceipt |  | Email_read_receipt |  | Indirizzo di posta elettronica fornito nelle intestazioni Internet per la conferma di lettura. |
| Sicurezza della posta elettronica | EmailSecurity | Email_security | Sicurezza della posta elettronica | Impostazione di sicurezza del messaggio: **0**: None; **1**: firmato; **2**: crittografato; **3**: crittografato e firmato. |
| Sensibilità della posta elettronica | EmailSensitivity | email_sensitivity | Sensibilità della posta elettronica | Impostazione di sensitivity del messaggio: **0**: None; **1**: personale; **2**: privato; **3**: CompanyConfidential. |
| Set di messaggi di posta elettronica | Messaggi di posta elettronica | Email_set | Set di messaggi di posta elettronica | ID gruppo per tutti i messaggi nello stesso set di posta elettronica. |
| EmailThread |  | Email_thread |  | Posizione del messaggio all'interno del set di messaggi di posta elettronica; è costituito da tutti gli ID dei nodi dalla radice al messaggio corrente, separati da punto. |
| Tipo di contenuto Estratto |  | Extracted_content_type | Tipo di contenuto Estratto | Tipo di contenuto estratto, sotto forma di tipo MIME; ad esempio, image/jpeg. |
| ExtractedTextLength |  | Extracted_text_length |  | Numero di caratteri nel testo estratto. |
| Pertinenza della famiglia Punteggio caso problema 1 |  | Family_relevance_score_case_issue_1 |  | Pertinenza della famiglia Punteggio caso problema 1 dalla pertinenza. |
| FamilyDuplicateSet |  | Family_duplicate_set |  | Identificatore numerico per le famiglie che sono duplicati esatti tra loro (stesso contenuto e tutti gli stessi allegati). |
| ID famiglia | FamilyId | Family_ID | ID famiglia | Gruppi di ID famiglia insieme tutti gli elementi; per la posta elettronica, sono inclusi il messaggio e tutti gli allegati. per i documenti, sono inclusi il documento e tutti gli elementi incorporati. |
| Dimensione famiglia |  | Family_size | Dimensione famiglia | Numero di documenti nella famiglia. |
| Rilevanza del file caso problema 1 |  | File_relevance_score_case_issue_1 |  | Numero di rilevanza dei file caso problema 1 dalla pertinenza. |
| Classe file | Fileclass | File_class | Classe file | Per il contenuto di SharePoint e OneDrive: **Document**; per il contenuto da Exchange: * * E-mail o **allegato**. |
| ID file | FileId | File_ID | ID file | Identificatore di documento univoco all'interno del caso.|
| Data di creazione del file System |  | File_system_date_created | Data di creazione del file System | Data creazione dal file System (si applica solo ai dati non di Office 365). |
| Data del file System modificato |  | File_system_date_modified | Data del file System modificato | Data di modifica del file System (si applica solo ai dati non di Office 365). |
| Tipo di file | FileType |  | Tipo di file | Tipo di file dell'elemento, in base all'estensione del file. |
| Ha allegato | HasAttachment | Email_has_attachment | Ha allegato | Indica se il messaggio contiene allegati o meno. |
| Ha un avvocato | HasAttorney |  | Ha un avvocato | Ha valore true se almeno uno dei partecipanti è presente nell'elenco degli avvocati. in caso contrario, il valore è false. |
| HasText |  | Has_text |  | Indica se l'elemento contiene o meno testo, se i valori possibili sono true e false. |
| ID non modificabile | ImmutableId | Immutable_ID | ID non modificabile | ID non modificabile memorizzato in Office 365. |
| Tipo inclusivo | InclusiveType | Inclusive_type | Tipo inclusivo | Tipo incluso calcolato per analisi: **0** -non incluso; **1** -Inclusive; **2** -incluso meno; copia **3** -inclusive. |
| In Rispondi a ID |  | In_reply_to_ID | In Rispondi a ID | In Rispondi a ID del messaggio. |
| È rappresentativo | Rappresentante | Is_representative | È rappresentativo | Un documento in ogni set di duplicati esatti è contrassegnato come rappresentante. |
| Classe Item | ItemClass | Item_class | Classe Item | Classe Item fornita da Exchange Server; ad esempio, **IPM. Note** |
| Last modified date | LastModifiedDate | Doc_date_modified | Last modified date | Data dell'Ultima modifica da metadati del documento. |
| ID di carico | LoadId | Load_ID | ID di carico | ID carico, in cui l'elemento è stato caricato in un set di revisione. |
| Posizione | Posizione | Posizione | Posizione | Stringa che indica il tipo di percorso da cui sono stati provenienti i documenti.<br />Dati importati non O365-><br />Teams-> Teams<br />ESO-> Exchange<br />SharePoint ><br />OneDrive for business-> OneDrive |
| Nome percorso | LocationName | Location_name | Nome percorso | Stringa che identifica l'origine dell'elemento.  Per Exchange, questo sarà l'indirizzo SMTP della cassetta postale.  Per SharePoint e OneDrive, l'URL della raccolta siti. |
| Contrassegnata come rappresentante | MarkAsRepresentative |  | Contrassegnata come rappresentante | Un documento di ogni gruppo di duplicati esatti è contrassegnato come rappresentanti. |
| Contrassegnato come numero di caso con tag 1 |  | Marked_as_pre_tagged_Case_issue_1 |  | Contrassegnata come problema di caso precontrassegnate 1 dalla pertinenza. |
| Contrassegnato come caso di Seed problema 1 |  | Marked_as_seed_Case_issue_1 |  | Contrassegnata come problema del Seed case 1 dalla pertinenza. |
| Data di fine riunione | MeetingEndDate | Meeting_end_date | Data di fine riunione | Data di fine riunione per le riunioni. |
| Data di inizio riunione | MeetingStartDate | Meeting_start_date | Data di inizio riunione | Data di inizio della riunione per le riunioni. |
| Tipo di messaggio | MessageKind | Message_kind | Tipo di messaggio | Tipo di messaggio da cercare.<br />Valori possibili: <br />contatti <br />documenti <br />email <br />externaldata <br />fax <br />im <br />riviste <br />riunioni <br />microsoftteams (restituisce elementi da chat, riunioni e chiamate in Microsoft Teams) <br />Note <br />messaggi <br />rssfeeds <br />attività <br />Voicemail |
| Interno nativo | NativeExtension | Native_extension | Interno nativo | Interno nativo dell'elemento. |
| Nome file nativo | NativeFileName | Native_file_name | Nome file nativo | Nome file nativo dell'elemento. |
| NativeMD5 |  | Native_MD5 |  | Hash MD5 del flusso di file. |
| Ordinamento ND/ET: esclusione degli allegati | NdEtSortExclAttach | ND_ET_sort_excl_attach | Ordinamento ND/ET: esclusione degli allegati | Concatenazione del set di posta elettronica e del set ND per l'ordinamento efficiente al momento della revisione; D viene aggiunto come prefisso ai set ND ed e viene aggiunto ai set di posta elettronica. |
| Ordinamento ND/ET: inclusi gli allegati | NdEtSortInclAttach | ND_ET_sort_incl_attach | Ordinamento ND/ET: inclusi gli allegati | Concatenazione del set di posta elettronica e del set ND per l'ordinamento efficiente al momento della revisione; D viene aggiunto come prefisso ai set ND ed e viene aggiunto ai set di posta elettronica. Ogni messaggio di posta elettronica all'interno di un set di posta elettronica è seguito dagli allegati corretti. |
| Rilevanza normalizzata caso problema 1 |  | Normalized_relevance_score_case_issue_1 |  | Rilevanza normalizzata caso problema 1 dalla pertinenza. |
| Autori di O365 |  | O365_authors | Autori di O365 | Autore da SharePoint. |
| O365 creato da |  | O365_created_by | O365 creato da | Creato da da SharePoint. |
| Data di O365 creata |  | O365_date_created | Data di O365 creata | Data di creazione da SharePoint. |
| Data di O365 modificata |  | O365_date_modified | Data di O365 modificata | Data dell'Ultima modifica di SharePoint. |
| O365 modificato da |  | O365_modified_by | O365 modificato da | Modificato da da SharePoint. |
| ID padre | ParentId | Parent_ID | ID padre | ID del padre dell'elemento. |
| ParentNode |  | Parent_node |  | Il messaggio di posta elettronica precedente più vicino nel thread di posta elettronica. |
| Percorso padre | ParentPath | Parent_path | Percorso padre | Percorso composto del padre diretto dell'elemento. |
| Domini dei partecipanti | ParticipantDomains | Email_participant_domains | Domini dei partecipanti | Elenco di tutti i domini dei partecipanti di un messaggio. |
| Partecipanti | Partecipanti | Email_participants | Partecipanti | Elenco di tutti i partecipanti a un messaggio; ad esempio, sender, to, CC, BCC. |
| ID pivot | PivotId | Pivot_ID | ID pivot | ID di un pivot. |
| Potenzialmente privilegiati | PotentiallyPrivileged | Potentially_privileged | Potenzialmente privilegiati | True se il modello di rilevamento dei privilegi avvocato-client considera il documento potenzialmente privilegiato |
| Stato di elaborazione | ProcessingStatus | Error_code | Stato di elaborazione | Stato di elaborazione dopo che l'elemento è stato aggiunto a un set di revisione. |
| Leggere la percentuale del caso numero 1 |  | Read_percent_Case_issue_1 |  | Leggere la percentuale di caso numero 1 dalla pertinenza. |
| Lettura percentile | ReadPercentile |  | Lettura percentile | Leggere il percentile per il documento in base alla pertinenza. |
| Numero destinatari |  | Recipient_count | Numero destinatari | Numero di destinatari nel messaggio. |
| Domini destinatario | RecipientDomains | Email_recipient_domains | Domini destinatario | Elenco di tutti i domini dei destinatari di un messaggio. |
| Destinatari | Destinatari | Email_recipients | Destinatari | Elenco di tutti i destinatari di un messaggio (to, CC, BCC). |
| Problema del gruppo di carico di pertinenza 1 |  | Relevance_load_group_case_issue_1 |  | Problema del gruppo di carico di rilevanza 1 dalla pertinenza. |
| Stato pertinenza Descrizione caso problema 1 |  | Relevance_status_description_Case_issue_1 |  | Stato di pertinenza Descrizione caso problema 1 dalla pertinenza. |
| Tag di pertinenza caso problema 1 |  | Relevance_tag_case_issue_1 |  | Tag di pertinenza caso problema 1 dalla pertinenza. |
| Commento pertinenza |  | Relevance_comment | Commento pertinenza | Campo dei commenti dalla pertinenza. |
| Punteggio di pertinenza | RelevanceScore |  | Punteggio di pertinenza | Punteggio di pertinenza di un documento in base alla pertinenza. |
| Tag pertinenza | RelevanceTag |  | Tag pertinenza | Punteggio di pertinenza di un documento in base alla pertinenza. |
| ID rappresentativo | RepresentativeId |  | ID rappresentativo | Identificatore numerico di ogni set di duplicati esatti. |
| Mittente | Mittente | Email_sender | Mittente | Campo mittente (da) per i tipi di messaggio.  Format è **DisplayName \<SmtpAddress>**. |
| Mittente/autore | SenderAuthor |  | Mittente/autore | Campo calcolato composto dal mittente o dall'autore dell'elemento. |
| Dominio del mittente | SenderDomain | Email_sender_domain | Dominio del mittente | Dominio del mittente. |
| Inviati | Inviati | Email_date_sent | Inviati | Data di invio del messaggio. |
| Imposta ordine: First Inclusive | SetOrderInclusivesFirst | Set_order_inclusives_first | Impostare Order: Inclusive First. | Campo di ordinamento-posta elettronica e allegati: contatore cronologico, documenti: pivot prima quindi per Punteggio di somiglianza, discendente. |
| SimilarityPercent |  | Similarity_percent |  | Indica il modo in cui un documento è simile al pivot del set di duplicati vicino. |
| Dimensioni dei file nativi | Dimensioni | Native_size | Dimensioni dei file nativi | Numero di byte dell'elemento nativo. |
| Oggetto | Oggetto | Email_subject | Oggetto | Oggetto del messaggio. |
| Subject/title | SubjectTitle |  | Subject/title | Campo calcolato che include l'oggetto o il titolo dell'elemento. |
| Tag per caso problema 1 |  | Tagged_by_Case_issue_1 |  | Utente che ha contrassegnato questo documento per il caso problema 1 in rilevanza. |
| Tag | Tag | Tag | Tag | Tag applicati in un set di revisione. |
| Elenco temi | Tema | Themes_list | Elenco temi | Elenco temi come calcolato per l'analisi. |
| Titolo | Titolo | Doc_title | Titolo | Titolo dei metadati del documento. |
| A | A | Email_to | A | To Field per i tipi di messaggio.  Format è **DisplayName\<SmtpAddress>** |
| Univoco nel set di posta elettronica | UniqueInEmailSet |  | Univoco nel set di posta elettronica | False se è presente un duplicato dell'allegato nel relativo set di posta elettronica. |
| È stato rimediato | WasRemediated | Was_Remediated | È stato rimediato | Ha valore true se l'elemento è stato rimediato, altrimenti false. |
| Word count | WordCount | Word_count | Word count | Numero di parole nell'elemento. |
||||||

  > [!NOTE]
  > Per ulteriori informazioni sulle proprietà disponibili per la ricerca durante la ricerca di percorsi di contenuto di Office 365 quando si raccolgono dati per un caso avanzato di eDiscovery, vedere [keyword queries and Search Conditions for content search](keyword-queries-and-search-conditions.md).