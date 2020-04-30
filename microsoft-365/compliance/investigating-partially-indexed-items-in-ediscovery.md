---
title: Analisi degli elementi parzialmente indicizzati in eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/26/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 4e8ff113-6361-41e2-915a-6338a7e2a1ed
description: Gli elementi parzialmente indicizzati (denominati anche elementi non indicizzati) sono elementi e documenti delle cassette postali di Exchange nei siti di SharePoint e OneDrive che per qualche motivo non sono stati completamente indicizzati per la ricerca di contenuto. In questo articolo, è possibile capire perché gli elementi non possono essere indicizzati per la ricerca e vengono restituiti come elementi parzialmente indicizzati, identificare gli errori di ricerca per gli elementi parzialmente indicizzati e utilizzare uno script di PowerShell per determinare l'esposizione dell'organizzazione agli elementi di posta elettronica parzialmente indicizzati.
ms.openlocfilehash: 0053ec5b03f5d32af1a39be94474c05f74ec3234
ms.sourcegitcommit: 60c1932dcca249355ef7134df0ceb0e57757dc81
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/29/2020
ms.locfileid: "43942129"
---
# <a name="investigating-partially-indexed-items-in-ediscovery"></a>Analisi degli elementi parzialmente indicizzati in eDiscovery

Una ricerca di contenuto eseguita dal centro sicurezza & conformità include automaticamente gli elementi parzialmente indicizzati nei risultati della ricerca stimati durante l'esecuzione di una ricerca. Gli elementi parzialmente indicizzati sono gli elementi della cassetta postale di Exchange e i documenti sui siti di SharePoint e OneDrive for business che per qualche motivo non sono stati completamente indicizzati per la ricerca. La maggior parte dei messaggi di posta elettronica e i documenti del sito vengono indicizzati correttamente perché rientrano nei [limiti di indicizzazione dei messaggi di posta elettronica](limits-for-content-search.md#indexing-limits-for-email-messages) Tuttavia, alcuni elementi possono superare questi limiti di indicizzazione e verranno parzialmente indicizzati. Di seguito sono riportati altri motivi per i quali gli elementi non possono essere indicizzati per la ricerca e vengono restituiti come elementi parzialmente indicizzati durante l'esecuzione di una ricerca di contenuto:
  
- I messaggi di posta elettronica dispongono di un file allegato di un tipo di file che non può essere indicizzato. nella maggior parte dei casi, il tipo di file non è [riconosciuto o non è supportato per l'indicizzazione](partially-indexed-items-in-content-search.md#file-types-not-indexed-for-search)
    
- I messaggi di posta elettronica dispongono di un file allegato privo di un gestore valido, ad esempio file di immagine. Questa è la causa più comune degli elementi di posta elettronica parzialmente indicizzati
    
- Troppi file allegati a un messaggio di posta elettronica
    
- Un file allegato a un messaggio di posta elettronica è troppo grande
    
- Il tipo di file è supportato per l'indicizzazione, ma si è verificato un errore di indicizzazione per un file specifico.
    
Anche se varia, la maggior parte delle organizzazioni clienti ha meno dell'1% del contenuto in base al volume e meno del 12% del contenuto in base alle dimensioni parzialmente indicizzate. Il motivo della differenza tra il volume e la dimensione è che i file più grandi hanno una probabilità maggiore di contenere contenuto che non può essere completamente indicizzato.
  
## <a name="why-does-the-partially-indexed-item-count-change-for-a-search"></a>Perché il conteggio degli elementi parzialmente indicizzato cambia per una ricerca?

Dopo aver eseguito una ricerca contenuto nel centro sicurezza & conformità, il numero totale e le dimensioni degli elementi parzialmente indicizzati nei percorsi ricercati sono elencati nelle statistiche dei risultati di ricerca visualizzati nelle statistiche dettagliate per la ricerca. Nota Queste sono denominate *voci non indicizzate* nelle statistiche di ricerca. Di seguito sono riportati alcuni aspetti che influiscono sul numero di elementi parzialmente indicizzati restituiti nei risultati della ricerca: 
  
- Se un elemento è parzialmente indicizzato e corrisponde alla query di ricerca, è incluso sia nel conteggio (sia nelle dimensioni) degli elementi dei risultati di ricerca e degli elementi parzialmente indicizzati. Tuttavia, quando vengono esportati i risultati della stessa ricerca, l'elemento viene incluso solo con un set di risultati di ricerca. non è incluso come elemento parzialmente indicizzato.
    
- Se si specifica un intervallo di date per una query di ricerca, inclusa nella query di parole chiave o tramite una condizione, qualsiasi elemento parzialmente indicizzato che non corrisponde all'intervallo di date non è incluso nel numero di elementi parzialmente indicizzati. Solo gli elementi parzialmente indicizzati che rientrano nell'intervallo di date sono inclusi nel numero di elementi parzialmente indicizzati.
    
 **Nota:** Gli elementi parzialmente indicizzati che si trovano in siti di SharePoint e OneDrive *non sono* inclusi nella stima degli elementi parzialmente indicizzati visualizzati nelle statistiche dettagliate per la ricerca. Tuttavia, gli elementi parzialmente indicizzati possono essere esportati quando si esportano i risultati di una ricerca di contenuto. Ad esempio, se si cercano solo i siti in una ricerca di contenuto, gli elementi parzialmente indicizzati per il numero stimato saranno pari a zero. 
  
## <a name="calculating-the-ratio-of-partially-indexed-items-in-your-organization"></a>Calcolo del rapporto tra gli elementi parzialmente indicizzati nell'organizzazione

Per comprendere l'esposizione dell'organizzazione a elementi parzialmente indicizzati, è possibile eseguire una ricerca per tutto il contenuto in tutte le cassette postali (utilizzando una query parola chiave vuota). Nell'esempio seguente, sono presenti 56.208 (4.830 MB) elementi completamente indicizzati e 470 (316 MB) di elementi parzialmente indicizzati.
  
![Esempio di statistiche di ricerca che mostrano elementi parzialmente indicizzati](../media/0f6a5cf7-4c98-44a0-a0dd-5aed67124641.png)
  
Per determinare la percentuale di elementi parzialmente indicizzati, è possibile utilizzare i calcoli riportati di seguito.
  
 **Per calcolare il rapporto tra gli elementi parzialmente indicizzati nell'organizzazione:**

`(Total number of partially indexed items/Total number of items) x 100`


`(470/56,208) x 100 = 0.84%`
 
Utilizzando i risultati della ricerca dell'esempio precedente, il 84% di tutti gli elementi delle cassette postali è parzialmente indicizzato.
  
 **Per calcolare la percentuale delle dimensioni degli elementi parzialmente indicizzati nell'organizzazione:**

`(Size of all partially indexed items/Size of all items) x 100`

`(316 MB/4830 MB) x 100 = 6.54%`

Nell'esempio precedente, il 6,54% delle dimensioni totali degli elementi delle cassette postali è compreso tra gli elementi parzialmente indicizzati. Come indicato in precedenza, la maggior parte delle organizzazioni clienti ha meno dell'1% del contenuto in base al volume e meno del 12% del contenuto in base alle dimensioni parzialmente indicizzate.

## <a name="working-with-partially-indexed-items"></a>Utilizzo di elementi parzialmente indicizzati

Nei casi in cui è necessario esaminare parzialmente gli elementi per convalidare che non contengono informazioni rilevanti, è possibile [esportare un rapporto di ricerca contenuto](export-a-content-search-report.md) che contiene informazioni sugli elementi parzialmente indicizzati. Quando si esporta un rapporto di ricerca contenuto, assicurarsi di scegliere una delle opzioni di esportazione che includa gli elementi parzialmente indicizzati. 
  
![Scegliere la seconda o la terza opzione per esportare gli elementi parzialmente indicizzati](../media/624a62b4-78f7-4329-ab5d-e62e3b369885.png)
  
Quando si esportano i risultati della ricerca del contenuto o un rapporto di ricerca contenuto utilizzando una di queste opzioni, l'esportazione include un report denominato unindexed Items. csv. Questo rapporto include la maggior parte delle stesse informazioni del file ResultsLog. csv. Tuttavia, il file unindexed Items. csv include anche due campi correlati agli elementi parzialmente indicizzati: **tag di errore** e proprietà di **errore**. Questi campi contengono informazioni sull'errore di indicizzazione per ogni elemento parzialmente indicizzato. L'utilizzo delle informazioni contenute in questi due campi consente di determinare se l'errore di indicizzazione per un determinato impatto dell'indagine. In caso affermativo, è possibile eseguire una ricerca di contenuto mirato e recuperare ed esportare messaggi di posta elettronica specifici e documenti di SharePoint o OneDrive in modo da poterli esaminare per determinare se sono rilevanti per la propria indagine. Per istruzioni dettagliate, vedere [preparare un file CSV per una ricerca di contenuto mirata in Office 365](csv-file-for-an-id-list-content-search.md).
  
 **Nota:** Il file unindexed Items. csv contiene anche campi denominati **tipo di errore** e **messaggio di errore**. Si tratta di campi legacy che contengono informazioni simili alle informazioni nei campi dei **tag di errore** e delle **proprietà di errore** , ma con informazioni meno dettagliate. È possibile ignorare tali campi legacy. 
  
## <a name="errors-related-to-partially-indexed-items"></a>Errori relativi agli elementi parzialmente indicizzati

I tag di errore sono costituiti da due parti di informazioni, l'errore e il tipo di file. Ad esempio, in questa coppia errore/filetype:

```text
 parseroutputsize_xls
```

   
 `parseroutputsize`è l'errore ed `xls` è il tipo di file del file su cui si è verificato l'errore. Nei casi in cui il tipo di file non è stato riconosciuto o il tipo di file non è stato applicato all'errore, `noformat` verrà visualizzato il valore al posto del tipo di file. 
  
Di seguito è riportato un elenco di errori di indicizzazione e una descrizione della possibile causa dell'errore.
  
|**Tag di errore**|**Descrizione**|
|:-----|:-----|
| `attachmentcount` <br/> |Un messaggio di posta elettronica aveva troppi allegati e alcuni di questi allegati non sono stati elaborati.  <br/> |
| `attachmentdepth` <br/> |La funzione di recupero contenuto e l'analizzatore del documento hanno rilevato troppi livelli di allegati annidati all'interno di altri allegati. Alcuni di questi allegati non sono stati elaborati.  <br/> |
| `attachmentrms` <br/> |Un allegato non è stato in grado di decodificare perché è protetto da RMS.  <br/> |
| `attachmentsize` <br/> |Un file allegato a un messaggio di posta elettronica è troppo grande e non è stato possibile elaborarlo.  <br/> |
| `indexingtruncated` <br/> |Quando si scrive il messaggio di posta elettronica elaborato nell'indice, una delle proprietà indicizzabili è troppo grande ed è stata troncata. Le proprietà troncate sono elencate nel campo proprietà errore.  <br/> |
| `invalidunicode` <br/> |Un messaggio di posta elettronica contiene testo che non può essere elaborato come Unicode valido. L'indicizzazione per questo elemento potrebbe essere incompleta.  <br/> |
| `parserencrypted` <br/> |Il contenuto dell'allegato o del messaggio di posta elettronica è crittografato e Microsoft 365 non è in grado di decodificare il contenuto.  <br/> |
| `parsererror` <br/> |Si è verificato un errore sconosciuto durante l'analisi. Questo in genere deriva da un errore del software o da un arresto del servizio.  <br/> |
| `parserinputsize` <br/> |Un allegato è troppo grande per la gestione del parser e l'analisi di tale allegato non è stata eseguita o non è stata completata.  <br/> |
| `parsermalformed` <br/> |Un allegato non è stato corretto e non è stato possibile gestirlo dal parser. Questo risultato può essere costituito da vecchi formati di file, file creati da software incompatibili o virus che fingono di essere diversi da quelli richiesti.  <br/> |
| `parseroutputsize` <br/> |L'output dell'analisi di un allegato è troppo grande e deve essere troncato.  <br/> |
| `parserunknowntype` <br/> |Un allegato ha un tipo di file che Microsoft 365 non è in grado di rilevare.  <br/> |
| `parserunsupportedtype` <br/> |Un allegato aveva un tipo di file rilevato da Office 365could, ma l'analisi del tipo di file non è supportata.  <br/> |
| `propertytoobig` <br/> |Il valore di una proprietà di posta elettronica nell'archivio di Exchange era troppo grande per essere recuperato e il messaggio non è stato elaborato. Questo accade in genere solo alla proprietà Body di un messaggio di posta elettronica.  <br/> |
| `retrieverrms` <br/> |La funzione di recupero contenuto non è riuscita a decodificare un messaggio protetto da RMS.  <br/> |
| `wordbreakertruncated` <br/> |Nel documento sono state identificate troppe parole durante l'indicizzazione. L'elaborazione della proprietà si è interrotta al raggiungimento del limite e la proprietà è troncata.  <br/> |
   
Nei campi di errore vengono descritti i campi che sono stati modificati dall'errore di elaborazione elencato nel campo tag error. Se si esegue la ricerca di una proprietà `subject` `participants`, ad esempio, gli errori nel corpo del messaggio non influiscono sui risultati della ricerca. Questo può essere utile quando si determinano esattamente gli elementi parzialmente indicizzati che potrebbe essere necessario approfondire.
  
## <a name="using-a-powershell-script-to-determine-your-organizations-exposure-to-partially-indexed-email-items"></a>Utilizzo di uno script di PowerShell per determinare l'esposizione dell'organizzazione a elementi di posta elettronica parzialmente indicizzati

Nei passaggi seguenti viene illustrato come eseguire uno script di PowerShell che consente di cercare tutti gli elementi in tutte le cassette postali di Exchange e quindi di generare un report sul rapporto tra l'organizzazione e gli elementi di posta elettronica parzialmente indicizzati (conta e per dimensione) e visualizza il numero di elementi (e il relativo tipo di file) per ogni errore di indicizzazione che si verifica. Utilizzare le descrizioni dei tag di errore nella sezione precedente per identificare l'errore di indicizzazione.
  
1. Salvare il testo seguente in un file di script di Windows PowerShell utilizzando un suffisso FileName di. ps1. ad esempio, `PartiallyIndexedItems.ps1`.

```powershell
  write-host "**************************************************"
  write-host "     Security & Compliance Center      " -foregroundColor yellow -backgroundcolor darkgreen
  write-host "   eDiscovery Partially Indexed Item Statistics   " -foregroundColor yellow -backgroundcolor darkgreen
  write-host "**************************************************"
  " " 
  # Create a search with Error Tags Refinders enabled
  Remove-ComplianceSearch "RefinerTest" -Confirm:$false -ErrorAction 'SilentlyContinue'
  New-ComplianceSearch -Name "RefinerTest" -ContentMatchQuery "size>0" -RefinerNames ErrorTags -ExchangeLocation ALL
  Start-ComplianceSearch "RefinerTest"
  # Loop while search is in progress
  do{
      Write-host "Waiting for search to complete..."
      Start-Sleep -s 5
      $complianceSearch = Get-ComplianceSearch "RefinerTest"
  }while ($complianceSearch.Status -ne 'Completed')
  $refiners = $complianceSearch.Refiners | ConvertFrom-Json
  $errorTagProperties = $refiners.Entries | Get-Member -MemberType NoteProperty
  $partiallyIndexedRatio = $complianceSearch.UnindexedItems / $complianceSearch.Items
  $partiallyIndexedSizeRatio = $complianceSearch.UnindexedSize / $complianceSearch.Size
  " "
  "===== Partially indexed items ====="
  "         Total          Ratio"
  "Count    {0:N0}{1:P2}" -f $complianceSearch.Items.ToString("N0").PadRight(15, " "), $partiallyIndexedRatio
  "Size(GB) {0:N2}{1:P2}" -f ($complianceSearch.Size / 1GB).ToString("N2").PadRight(15, " "), $partiallyIndexedSizeRatio
  " "
  Write-Host ===== Reasons for partially indexed items =====
  foreach($errorTagProperty in $errorTagProperties)
  {
      $name = $refiners.Entries.($errorTagProperty.Name).Name
      $count = $refiners.Entries.($errorTagProperty.Name).TotalCount
      $frag = $name.Split("{_}")
      $errorTag = $frag[0]
      $fileType = $frag[1]
      if ($errorTag -ne $lastErrorTag)
      {
          $errorTag
      }
      "    " + $fileType + " => " + $count
      $lastErrorTag = $errorTag
  }
  
```

2. [Connettersi a PowerShell in Centro sicurezza e conformità](https://go.microsoft.com/fwlink/p/?linkid=627084).
    
3. In PowerShell Centro sicurezza & conformità, passare alla cartella in cui è stato salvato lo script nel passaggio 1, quindi eseguire lo script. Per esempio:

    ```powershell
    .\PartiallyIndexedItems.ps1
    ```

Di seguito è riportato un esempio per l'output restituito dallo script.
  
![Esempio di output da script che genera un report sull'esposizione dell'organizzazione a elementi di posta elettronica parzialmente indicizzati](../media/aeab5943-c15d-431a-bdb2-82f135abc2f3.png)
  
Tenere presente quanto segue:
  
1. Il numero totale e le dimensioni degli elementi di posta elettronica e il rapporto tra l'organizzazione e gli elementi di posta elettronica parzialmente indicizzati (conteggio e per dimensione)
    
2. Tag di errore dell'elenco e tipi di file corrispondenti per i quali si è verificato l'errore.
  
## <a name="see-also"></a>Vedere anche

[Partially indexed items in Content Search in Office 365](partially-indexed-items-in-content-search.md) (Elementi parzialmente indicizzati in Ricerca contenuto in Office 365)
