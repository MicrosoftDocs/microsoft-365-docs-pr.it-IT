---
title: Esportare i campi di report in Office 365 Advanced eDiscovery
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 840a5aff-ecd0-4e56-ad22-fe99bc143687
description: Vengono descritti tutti i campi inclusi nei report di esportazione per Advanced eDiscovery.
ms.openlocfilehash: cc585fcabefa9036d91162b6418c3e5e9c752378
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2019
ms.locfileid: "40805839"
---
# <a name="export-report-fields-in-office-365-advanced-ediscovery"></a>Esportare i campi di report in Office 365 Advanced eDiscovery

> [!NOTE]
> Per usare Advanced eDiscovery è necessario avere Office 365 E3 con il componente aggiuntivo Advanced Compliance o un abbonamento E5 dell'organizzazione. Se non si ha questo piano e si desidera provare Advanced eDiscovery, è possibile [richiedere una valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
In questo argomento vengono descritti i campi avanzati del rapporto di esportazione di eDiscovery per lo standard e tutti i modelli.
  
## <a name="export-report-fields"></a>Esportare i campi del report

Nella tabella seguente sono elencati i campi per ogni modello di esportazione.
  
|**Nome del campo di esportazione**|**Gruppo**|**Descrizione**|**Disponibile nel modello standard**|**Disponibile in tutti i modelli**|
|:-----|:-----|:-----|:-----|:-----|
|Row_number  <br/> |Generale  <br/> |Numero di riga.  <br/> |Sì  <br/> |Sì  <br/> |
|File_ID  <br/> |Generale  <br/> |ID file.  <br/> |Sì  <br/> |Sì  <br/> |
|File_class  <br/> |Elaborazione  <br/> |Classe file.  <br/> |Sì  <br/> |Sì  <br/> |
|Family_ID  <br/> |Elaborazione  <br/> |Identificatore numerico utilizzato per raggruppare i file (in genere l'istanza di posta elettronica e i relativi allegati).  <br/> |Sì  <br/> |Sì  <br/> |
|For_review  <br/> |Elaborazione  <br/> |Contrassegna per indicare che il campo verrà incluso nell'esportazione per la revisione.  <br/> |Sì  <br/> |Sì  <br/> |
|Native_file_name  <br/> |Elaborazione  <br/> |Nome file nativo, senza riferimenti alla cartella e all'estensione.  <br/> |Sì  <br/> |Sì  <br/> |
|Custodi  <br/> |Generale  <br/> |Custode del file.  <br/> |Sì  <br/> |Sì  <br/> |
|Set_ID  <br/> |Analisi  <br/> |ID "ND set" o "set di posta elettronica".  <br/> |Sì  <br/> |Sì  <br/> |
|Inclusive_type  <br/> |Posta elettronica  <br/> |Indica se il file è incluso, in base ai valori seguenti: 0-non incluso, 1-inclusive, 2-inclusive meno, 3-inclusive Copy.  <br/> |Sì  <br/> |Sì  <br/> |
|Marked_as_pivot  <br/> |Quasi duplicati  <br/> |Indica se il file è un pivot.  <br/> |Sì  <br/> |Sì  <br/> |
|Similarity_percent  <br/> |Quasi duplicati  <br/> |Percentuale di somiglianza rispetto al pivot.  <br/> |Sì  <br/> |Sì  <br/> |
|Duplicate_subset  <br/> |Quasi duplicati  <br/> |Identificatore univoco del sottoinsieme duplicato. Indica se il file contiene duplicati di testo esatti.  <br/> |Sì  <br/> |Sì  <br/> |
|Data  <br/> |Generale  <br/> |Data del file (dipende dal tipo di file-messaggio di posta elettronica: data di invio; documento: data modifica).  <br/> |Sì  <br/> |Sì  <br/> |
|Dominant_theme  <br/> |Analisi  <br/> |Tema principale del file.  <br/> |Sì  <br/> |Sì  <br/> |
|Themes_list  <br/> |Temi  <br/> |Elenco di nomi di tema.  <br/> |Sì  <br/> |Sì  <br/> |
|ND_set  <br/> |EquiSet  <br/> |Identificatore numerico univoco di un set di Nearduplicate.  <br/> |Sì  <br/> |Sì  <br/> |
|Email_set  <br/> |Posta elettronica  <br/> |Identificatore numerico univoco di un set di messaggi di posta elettronica.  <br/> |Sì  <br/> |Sì  <br/> |
|Email_thread  <br/> |Posta elettronica  <br/> |Descrive la posizione del messaggio di posta elettronica all'interno del set di posta elettronica costituito da tutti gli ID dei nodi dalla radice al messaggio di posta elettronica corrente, separati da periodi.  <br/> |Sì  <br/> |Sì  <br/> |
|Email_subject  <br/> |Posta elettronica  <br/> |Oggetto del messaggio di posta elettronica.  <br/> |Sì  <br/> |Sì  <br/> |
|Email_date_sent  <br/> |Posta elettronica  <br/> |Data in cui è stato inviato il messaggio di posta elettronica.  <br/> |Sì  <br/> |Sì  <br/> |
|Email_participants  <br/> |Posta elettronica  <br/> |Indirizzi di posta elettronica di tutti i partecipanti a un thread di posta elettronica, inclusi i collegamenti mancanti.  <br/> |Sì  <br/> |Sì  <br/> |
|Email_participant_domains  <br/> |Posta elettronica  <br/> |Domini di tutti i partecipanti a un thread di posta elettronica, incluso il collegamento mancante.  <br/> |Sì  <br/> |Sì  <br/> |
|Email_sender  <br/> |Posta elettronica  <br/> |Nome e/o indirizzo del mittente del messaggio di posta elettronica.  <br/> |Sì  <br/> |Sì  <br/> |
|Email_sender_domain  <br/> |Posta elettronica  <br/> |Dominio del mittente del messaggio di posta elettronica.  <br/> |Sì  <br/> |Sì  <br/> |
|Email_to  <br/> |Posta elettronica  <br/> |Al destinatario del messaggio di posta elettronica.  <br/> |Sì  <br/> |Sì  <br/> |
|Email_cc  <br/> |Posta elettronica  <br/> |Destinatario CC del messaggio di posta elettronica.  <br/> |Sì  <br/> |Sì  <br/> |
|Email_bcc  <br/> |Posta elettronica  <br/> |Destinatario Ccn del messaggio di posta elettronica.  <br/> |Sì  <br/> |Sì  <br/> |
|Email_recipient_domains  <br/> |Posta elettronica  <br/> |Domini di posta elettronica destinatari (a, CC e Ccn).  <br/> |Sì  <br/> |Sì  <br/> |
|Email_date_received  <br/> |Posta elettronica  <br/> |Data in cui è stata ricevuta la posta elettronica.  <br/> |Sì  <br/> |Sì  <br/> |
|Email_action  <br/> |Posta elettronica  <br/> |Valori: secondo l'oggetto di posta elettronica: "forward" (per "FW:"), "Rispondi" (per "RE:") o "altro" (altro testo soggetto).  <br/> |Sì  <br/> |Sì  <br/> |
|Meeting_Start_Date/Time  <br/> ||La data e l'ora in cui è stato avviato un elemento della riunione.  <br/> |Sì  <br/> |Sì  <br/> |
|Meeting_End_Date/Time  <br/> ||La data e l'ora di fine di un elemento della riunione.  <br/> |Sì  <br/> |Sì  <br/> |
|File_relevance_score  <br/> |Pertinenza  <br/> |Punteggio di pertinenza (0-100). Per ogni problema.  <br/> |Sì  <br/> |Sì  <br/> |
|Family_relevance_score  <br/> |Pertinenza  <br/> |Punteggio di pertinenza massimo della famiglia (0-100). Per ogni problema.  <br/> |Sì  <br/> |Sì  <br/> |
|Relevance_tag  <br/> |Pertinenza  <br/> |Tag del file, se il file è stato contrassegnato manualmente in pertinenza. Per ogni problema.  <br/> |Sì  <br/> |Sì  <br/> |
|Relevance_load_group  <br/> |Pertinenza  <br/> |Gruppo di caricamento della pertinenza, del file specificato, con un campo per problema.  <br/> |Sì  <br/> |Sì  <br/> |
|Normalized_relevance_score  <br/> |Pertinenza  <br/> |Punteggio di pertinenza normalizzata (0-100), che è paragonabile tra problemi e carichi.  <br/> |Sì  <br/> |Sì  <br/> |
|Marked_as_seed  <br/> |Pertinenza  <br/> |Tag del file, se è stato impostato come file di inizializzazione in pertinenza per ogni problema/categoria.  <br/> |Sì  <br/> |Sì  <br/> |
|Marked_as_pre-Tagged  <br/> |Pertinenza  <br/> |Contrassegnare il file, se è stato impostato come precodificato in pertinenza per problema/categoria.  <br/> |Sì  <br/> |Sì  <br/> |
|Relevance_status_description  <br/> |Pertinenza  <br/> |Descrizione dello stato di pertinenza.  <br/> |Sì  <br/> |Sì  <br/> |
|Aggiungere commenti  <br/> |Generale  <br/> |Commento immesso dall'utente.  <br/> |Sì  <br/> |Sì  <br/> |
|Export_input_path  <br/> |Elaborazione  <br/> |Esporta percorso di input.  <br/> |Sì  <br/> |Sì  <br/> |
|Pivot_ID  <br/> |Quasi duplicati  <br/> |ID pivot del file.  <br/> |Sì  <br/> |Sì  <br/> |
|Family_size  <br/> |Elaborazione  <br/> |Numero di file in una famiglia.  <br/> |Sì  <br/> |Sì  <br/> |
|Native_type  <br/> |Elaborazione  <br/> |Tipo di file nativo. Ad esempio, foglio di calcolo o presentazione.  <br/> |Sì  <br/> |Sì  <br/> |
|Native_MD5  <br/> |Elaborazione  <br/> |Valore hash MD5 del file nativo.  <br/> |Sì  <br/> |Sì  <br/> |
|Native_size  <br/> |Elaborazione  <br/> |Dimensione del file nativo.  <br/> |Sì  <br/> |Sì  <br/> |
|Native_extension  <br/> |Elaborazione  <br/> |Estensione di file nativa.  <br/> |Sì  <br/> |Sì  <br/> |
|Doc_date_modified  <br/> |Proprietà del documento  <br/> |Data file nativo è stato modificato, ricavato dai metadati del file.  <br/> |Sì  <br/> |Sì  <br/> |
|Doc_date_created  <br/> |Proprietà del documento  <br/> |Data file nativo è stato creato, ricavato dai metadati del file.  <br/> |Sì  <br/> |Sì  <br/> |
|Doc_modified_by  <br/> |Proprietà del documento  <br/> |Utente che ha modificato il file nativo, ricavato dai metadati del file.  <br/> |Sì  <br/> |Sì  <br/> |
|O365_date_modified  <br/> |Proprietà del documento  <br/> |Data file nativo è stato modificato, ricavato dal campo SharePoint o Exchange.  <br/> |Sì  <br/> |Sì  <br/> |
|O365_date_created  <br/> |Proprietà del documento  <br/> |Data file nativo è stato creato, ricavato da campi di SharePoint o di Exchange.  <br/> |Sì  <br/> |Sì  <br/> |
|O365_modified_by  <br/> |Proprietà del documento  <br/> |Utente che ha modificato l'ultimo file nativo, ricavato da campi di SharePoint o di Exchange.  <br/> |Sì  <br/> |Sì  <br/> |
|Compound_path  <br/> |Elaborazione  <br/> |Percorso del file nativo che include l'origine composta.  <br/> |Sì  <br/> |Sì  <br/> |
|Input_path  <br/> |Elaborazione  <br/> |Percorso del file di input.  <br/> |Sì  <br/> |Sì  <br/> |
|Input_date_modified  <br/> |Elaborazione  <br/> |Data e ora dell'Ultima modifica del file di input.  <br/> |Sì  <br/> |Sì  <br/> |
|ND_ET_sort_excl_attach  <br/> |Analisi  <br/> |Concatenazione del set di messaggi di posta elettronica e set ND per la revisione. ' S'è aggiunto come prefisso ai set ND è È viene aggiunto al messaggio di posta elettronica imposta.  <br/> |Sì  <br/> |Sì  <br/> |
|ND_ET_sort_incl_attach  <br/> |Analisi  <br/> |La concatenazione del set di messaggi di posta elettronica e del set ND per la revisione ' d'viene aggiunta come prefisso ai set ND è È viene aggiunta ai set di messaggi di posta elettronica. Inoltre, ogni messaggio di posta elettronica all'interno di un Email_set è seguito dagli allegati corretti.  <br/> |Sì  <br/> |Sì  <br/> |
|Deduped_custodians  <br/> |Generale  <br/> |Custodi dei file deduplicati  <br/> |Sì  <br/> |Sì  <br/> |
|Deduped_file_IDs  <br/> |Generale  <br/> |ID dei file deduplicati  <br/> |Sì  <br/> |Sì  <br/> |
|Deduped_paths  <br/> |Generale  <br/> |Percorsi dei file deduplicati  <br/> |Sì  <br/> |Sì  <br/> |
|File_key  <br/> |Generale  <br/> |Identificatore interno per uso futuro.  <br/> |Sì  <br/> |Sì  <br/> |
|Export_native_path  <br/> |Elaborazione  <br/> |Percorso del file nativo nel pacchetto di esportazione.  <br/> |Sì  <br/> |Sì  <br/> |
|Extracted_text_path  <br/> |Elaborazione  <br/> |Percorso del file estratto.  <br/> |Sì  <br/> |Sì  <br/> |
|Process_batch  <br/> |Elaborazione  <br/> |Identificatore batch per il batch di importazione.  <br/> |Sì  <br/> |Sì  <br/> |
|Process_status_ID  <br/> |Elaborazione  <br/> |Identificatore che rappresenta lo stato della fase di elaborazione.  <br/> |Sì  <br/> |Sì  <br/> |
|Process_status_description  <br/> |Elaborazione  <br/> |Descrizione stato fase di elaborazione: descrizione riuscita o errore.  <br/> |Sì  <br/> |Sì  <br/> |
|Export_status_ID  <br/> |Elaborazione  <br/> |ID dello stato di esportazione.  <br/> |Sì  <br/> |Sì  <br/> |
|Export_status_description  <br/> |Elaborazione  <br/> |Descrizione dello stato di esportazione; Descrizione riuscita o errore.  <br/> |Sì  <br/> |Sì  <br/> |
|Read_percent  <br/> |Pertinenza  <br/> |Lettura% (0-100). Per ogni problema.  <br/> |Sì  <br/> |Sì  <br/> |
|Doc_author  <br/> |Proprietà di documento  <br/> |Proprietà del documento: Author.  <br/> |No  <br/> |Sì  <br/> |
|Doc_comments  <br/> |Proprietà di documento  <br/> |Proprietà del documento: commenti.  <br/> |No  <br/> |Sì  <br/> |
|Doc_keywords  <br/> |Proprietà di documento  <br/> |Proprietà del documento: parole chiave.  <br/> |No  <br/> |Sì  <br/> |
|Doc_last_saved_by  <br/> |Proprietà di documento  <br/> |Proprietà del documento: ultimo salvataggio da.  <br/> |No  <br/> |Sì  <br/> |
|Doc_revision  <br/> |Proprietà di documento  <br/> |Proprietà del documento: numero di revisione.  <br/> |No  <br/> |Sì  <br/> |
|Doc_subject  <br/> |Proprietà di documento  <br/> |Proprietà del documento: subject.  <br/> |No  <br/> |Sì  <br/> |
|Doc_template  <br/> |Proprietà di documento  <br/> |Proprietà documento: modello.  <br/> |No  <br/> |Sì  <br/> |
|Doc_title  <br/> |Proprietà di documento  <br/> |Proprietà del documento: title.  <br/> |No  <br/> |Sì  <br/> |
|Email_has_attachment  <br/> |Posta elettronica  <br/> |Indica se il messaggio di posta elettronica contiene uno o più allegati.  <br/> |No  <br/> |Sì  <br/> |
|Email_importance  <br/> |Posta elettronica  <br/> |Valore della proprietà di posta elettronica.  <br/> |No  <br/> |Sì  <br/> |
|Email_level  <br/> |Posta elettronica  <br/> |Indica il livello di posta elettronica all'interno del thread di posta elettronica. Per gli allegati, il valore del messaggio di posta elettronica allegato.  <br/> |No  <br/> |Sì  <br/> |
|Email_recipients  <br/> |Posta elettronica  <br/> |Nome e/o indirizzo per i destinatari di posta elettronica (a, CC e Ccn).  <br/> |No  <br/> |Sì  <br/> |
|Email_security  <br/> |Posta elettronica  <br/> |Proprietà di sicurezza della posta elettronica.  <br/> |No  <br/> |Sì  <br/> |
|Email_sensitivity  <br/> |Posta elettronica  <br/> |Proprietà di sensitivity della posta elettronica.  <br/> |No  <br/> |Sì  <br/> |
|Export_batch  <br/> |Elaborazione  <br/> |Nome del batch di esportazione dell'ultimo file.  <br/> |No  <br/> |Sì  <br/> |
|Export_session  <br/> |Elaborazione  <br/> |ID della sessione di esportazione dell'ultimo file, inclusa la data.  <br/> |No  <br/> |Sì  <br/> |
|Extracted_text_length  <br/> |Elaborazione  <br/> |Lunghezza caratteri del file di testo estratto.  <br/> |No  <br/> |Sì  <br/> |
|Family_duplicate_set  <br/> |Elaborazione  <br/> |Identificatore numerico per le famiglie che sono duplicati esatti del testo di ogni altro (rispettivamente-tutti i membri delle famiglie sono duplicati esatti).  <br/> |No  <br/> |Sì  <br/> |
|Has_Text  <br/> |Elaborazione  <br/> |Indica se è presente un testo nel file: 0-No; 1-Sì.  <br/> |No  <br/> |Sì  <br/> |
|Input_file_ID  <br/> |Elaborazione  <br/> |ID del file di input da cui è stato estratto il file.  <br/> |No  <br/> |Sì  <br/> |
|Native_SHA_256  <br/> |Elaborazione  <br/> |Valore hash SHA-256 del file nativo.  <br/> |No  <br/> |Sì  <br/> |
|O365_authors  <br/> |Proprietà di documento  <br/> |Utenti che hanno modificato il file nativo, ricavato da campi di SharePoint o di Exchange.  <br/> |No  <br/> |Sì  <br/> |
|O365_created_by  <br/> |Proprietà di documento  <br/> |Utente che ha creato il file nativo, ricavato da campi di SharePoint o di Exchange.  <br/> |No  <br/> |Sì  <br/> |
|Parent_node  <br/> |Posta elettronica  <br/> |Collega un nodo in un thread di posta elettronica al nodo padre più vicino che non è un collegamento mancante.  <br/> |No  <br/> |Sì  <br/> |
|Set_order_inclusives_first  <br/> |Posta elettronica  <br/> |Messaggi di posta elettronica e allegati: contatore ordine cronologico (incluso per primo). Documenti: pivot prima e resto per Punteggio di somiglianza, discendente.  <br/> |No  <br/> |Sì  <br/> |
|Tagged_By  <br/> |Pertinenza  <br/> |Utente che ha aggiunto il file in pertinenza per il problema specifico.  <br/> |No  <br/> |Sì  <br/> |
|Word_count  <br/> |Analisi  <br/> |Numero di parole nel documento.  <br/> |No  <br/> |Sì  <br/> |
|
   
## <a name="related-topics"></a>Argomenti correlati

[Office 365 Advanced eDiscovery](office-365-advanced-ediscovery.md)
  
[Esportazione di dati di case con Advanced eDiscovery](export-case-data-in-advanced-ediscovery.md)
  
[Esportazione dei risultati](export-results-in-advanced-ediscovery.md)
  
[Visualizzazione della cronologia batch ed esportazione dei risultati precedenti](view-batch-history-and-export-past-results.md)
  

