---
title: Esportare i documenti da un insieme da rivedere
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
ms.openlocfilehash: cf8b11fa82398ab8cfa3981064741d0dbf349f71
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37083638"
---
# <a name="export-documents-from-a-review-set"></a>Esportare i documenti da un insieme da rivedere

È possibile esportare il contenuto per la presentazione o la revisione esterna da un set di revisione tramite uno dei metodi seguenti:

- [Scaricare documenti](#download-documents-from-a-review-set)
 
- [Esportare documenti](#export-documents-from-a-review-set)

## <a name="download-documents-from-a-review-set"></a>Scaricare i documenti da un set di Revisione

Download offre un modo semplice per scaricare contenuto da un set di recensioni in formato nativo. Sfrutta le caratteristiche di trasferimento dei dati del browser in modo che una richiesta del browser venga visualizzata una volta che il download è pronto. I file scaricati con questo metodo verranno zippati in un file contenitore e saranno file a livello di elemento. Questo significa che se si seleziona un allegato, verrà visualizzato automaticamente il messaggio di posta elettronica con l'allegato incluso. Analogamente, se si seleziona un foglio di calcolo di Excel incorporato in un documento di Word, verrà visualizzato il documento di Word con il foglio di calcolo di Excel incorporato. Gli elementi scaricati conserveranno la data dell'Ultima modifica che può essere visualizzata come proprietà di un file.

Per scaricare contenuto da un set di recensioni, iniziare selezionando i file che si desidera scaricare, quindi selezionare "Scarica" dal menu azioni.

![Schermata di una descrizione del computer generata automaticamente](media/eDiscoDownload.png)

## <a name="export-documents-from-a-review-set"></a>Esportare i documenti da un insieme da rivedere

Export consente agli utenti di personalizzare il contenuto incluso nel pacchetto di download. Fornisce una pagina di configurazione con le seguenti impostazioni:

### <a name="metadata-file"></a>File di metadati

Questo può essere considerato come il "Load file" che contiene i metadati associati ai file esportati. Per un elenco dei campi disponibili nel file di metadati, vedere \[link\]. Questo file può in genere essere ingerito da<sup>3 strumenti</sup> di terze parti a valle.

### <a name="tag-data"></a>Dati tag

Questo contenuto verrebbe aggiunto come campi nel file di metadati. Contiene tutte le informazioni sui tag applicate nei set di revisione.

### <a name="text-files"></a>File di testo

È possibile generare file di testo per ogni file esportato da un set di revisione. Spesso questi file sono necessari per i partner del servizio come parte dell'ingestione dei dati<sup>in 3 strumenti</sup> di terze parti a valle.

### <a name="redacted-files"></a>File redatti

Se durante la revisione vengono generati file PDF ritirati, questi sono disponibili durante l'esportazione. Gli utenti possono decidere se esportare solo i file nativi o sostituire i nativi che dispongono di redazioni con il masterizzato nei file PDF.

### <a name="export-location"></a>Percorso di esportazione

Il contenuto esportato viene recapitato a un BLOB di Azure fornito da Microsoft o è possibile utilizzare il BLOB di un cliente se i dettagli vengono forniti all'esportazione.

### <a name="export-structure"></a>Struttura di esportazione

Quando il contenuto viene esportato da un set di revisione, il contenuto è organizzato nella struttura seguente.

  - Cartella radice-ID download
    
      - Esporta\_caricamento\_file. csv = file di metadati
    
      - Summary. txt = un file di riepilogo con statistiche di esportazione
    
      - Input\_o file\_nativi = contiene tutti i file nativi
    
      - File\_Error = contiene eventuali file di errore inclusi nell'esportazione
        
          - ExtractionError – un CSV che contiene i metadati disponibili di file che non sono stati estratti correttamente dai file padre
        
          - ProcessingError – contenuto con errori di elaborazione. Questo contenuto è a livello di elemento significato se un allegato ha subito un errore di elaborazione, il messaggio di posta elettronica che contiene l'allegato verrà incluso in questa cartella.
    
      - File\_di\_testo estratti = contiene tutti i file di testo estratti generati durante l'elaborazione.