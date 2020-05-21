---
title: Creare una query per individuare dati riservati memorizzati nei siti
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
- SPO_Content
localization_priority: Normal
search.appverid:
- MOE150
- MET150
description: Con la prevenzione della perdita di dati (DLP) in SharePoint Online, è possibile individuare i documenti che contengono dati riservati in tutto il tenant. Dopo aver individuato i documenti, è possibile collaborare con i proprietario al fine di proteggere i dati. In questo argomento viene illustrato come creare una query per cercare dati riservati.
ms.openlocfilehash: 78f7f07bf6b2fbb0781f4bda8716b84399eef561
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "44327914"
---
# <a name="form-a-query-to-find-sensitive-data-stored-on-sites"></a>Creare una query per trovare i dati sensibili archiviati nei siti

Gli utenti memorizzano spesso dati riservati, ad esempio il numero della carta di credito, il numero di previdenza sociale o il codice fiscale e con il tempo possono esporre l'organizzazione al rischio di perdita di tali dati. I documenti archiviati nei siti, inclusi i siti di OneDrive for business, possono essere condivisi con utenti esterni all'organizzazione che non devono avere accesso alle informazioni. Con la prevenzione della perdita di dati (DLP) in SharePoint Online, è possibile individuare i documenti che contengono dati riservati in tutto il tenant. Dopo aver individuato i documenti, è possibile collaborare con i proprietario al fine di proteggere i dati. In questo argomento viene illustrato come creare una query per cercare dati riservati.
  
> [!NOTE]
> Electronic Discovery, o eDiscovery e DLP sono funzionalità Premium che richiedono [SharePoint Online piano 2](https://go.microsoft.com/fwlink/?LinkId=510080). 
  
## <a name="forming-a-basic-dlp-query"></a>Creazione di una query DLP di base

Una query DLP di base è formata da tre parti: SensitiveType, intervallo conteggio e intervallo di confidenza. Come illustrato nella figura seguente, **SensitiveType: " \< tipo \> "** è obbligatorio e** | \< \> ** entrambi gli intervalli di conteggio e di** | \< confidenza \> ** sono facoltativi. 
  
![Query di esempio divisa in necessaria e facoltativa](../media/DLP-query-example-text.png)
  
### <a name="sensitive-type---required"></a>SensitiveType - obbligatorio

Quindi, a cosa corrisponde ogni parte? La proprietà e il nome di un tipo di informazioni vengono in genere iniziati con le query di SharePoint DLP `SensitiveType:"` dall' [inventario dei tipi di informazioni riservate](https://go.microsoft.com/fwlink/?LinkID=509999)e terminano con un `"` . È inoltre possibile utilizzare il nome di un [tipo di informazioni riservate personalizzato](create-a-custom-sensitive-information-type.md) creato per l'organizzazione. Ad esempio, è possibile cercare documenti che includono numeri di carta di credito. In tal caso, è necessario utilizzare il formato seguente: `SensitiveType:"Credit Card Number"` . Poiché non è stato incluso l'intervallo di conteggio o la riservatezza, la query restituisce tutti i documenti in cui viene rilevato un numero di carta di credito. Questa è la query più semplice da eseguire e restituisce il maggior numero di risultati. Ricordare che vengono presi in considerazione sia l'ortografia che il numero di spazi. 
  
### <a name="ranges---optional"></a>Intervalli - facoltativo

Entrambe le due parti successive sono intervalli, quindi esaminiamo rapidamente l'aspetto di un intervallo. Nelle query di SharePoint DLP, un intervallo di base è rappresentato da due numeri separati da due periodi, che sono analoghi a quanto segue: `[number]..[number]` . Ad esempio, se `10..20` viene utilizzato, quell'intervallo catturerà i numeri da 10 a 20. Sono disponibili molte combinazioni di intervallo e molte sono descritte in questo argomento. 
  
Aggiungere un intervallo di count alla query. È possibile utilizzare l'intervallo di Count per definire il numero di occorrenze di informazioni riservate che un documento deve contenere prima che sia incluso nei risultati della query. Ad esempio, se si desidera che la query restituisca solo i documenti che contengono esattamente cinque numeri di carta di credito, utilizzare la seguente operazione: `SensitiveType:"Credit Card Number|5"` . L'intervallo di conteggio consente anche di identificare i documenti a rischio elevato. Ad esempio, l'organizzazione potrebbe considerare a rischio i documenti con 5 o più numeri di carta di credito. Per trovare i documenti che corrispondono a questo criterio, è necessario utilizzare la query seguente: `SensitiveType:"Credit Card Number|5.."` . In alternativa, è possibile trovare documenti con cinque o meno numeri di carta di credito utilizzando la query seguente: `SensitiveType:"Credit Card Number|..5"` . 
  
#### <a name="confidence-range"></a>Intervallo di confidenza

Infine, intervallo di confidenza consiste nel livello di confidenza con il quale il tipo di informazione riservata identificata rappresenta effettivamente una corrispondenza. I valori relativi all'intervallo di confidenza funzionano in modo analogo all'intervallo di conteggio. È possibile creare una query senza includere un intervallo di conteggio. Ad esempio, per cercare i documenti con un numero qualsiasi di numeri di carta di credito, purché l'intervallo di confidenza sia pari o superiore al 85%, è necessario utilizzare la query seguente: `SensitiveType:"Credit Card Number|*|85.."` . 
  
> [!IMPORTANT]
> L'asterisco ( `*` ) è un carattere jolly che indica che viene utilizzato qualsiasi valore. È possibile utilizzare il carattere jolly ( `*` ) nell'intervallo di conteggio o nell'intervallo di confidenza, ma non in un tipo riservato. 
  
### <a name="additional-query-properties-and-search-operators-available-in-the-ediscovery-center"></a>Ulteriori proprietà della query e operatori di ricerca sono disponibili nel Centro eDiscovery

DLP in SharePoint introduce anche la proprietà LastSensitiveContentScan, che consente di cercare i file analizzati in un intervallo di tempo specifico. Per gli esempi di query con la `LastSensitiveContentScan` proprietà, vedere gli [esempi di query complesse](#examples-of-complex-queries) nella sezione successiva. 
  
È possibile utilizzare non solo le proprietà specifiche di DLP per creare una query, ma anche le proprietà di ricerca di eDiscovery di SharePoint standard, ad esempio `Author` o `FileExtension` . È possibile utilizzare gli operatori per creare query complesse. Per l'elenco delle proprietà e degli operatori disponibili, vedere l'articolo [utilizzo di proprietà e operatori di ricerca con](https://go.microsoft.com/fwlink/?LinkId=510093) il post di Blog di eDiscovery. 
  
## <a name="examples-of-complex-queries"></a>Esempi

Negli esempi seguenti vengono utilizzati diversi tipi, proprietà e operatori sensibili per illustrare in che modo è possibile affinare le query per trovare esattamente ciò che si sta cercando.
  
|**Query**|**Spiegazione**|
|:-----|:-----|
| `SensitiveType:"International Banking Account Number (IBAN)"` <br/> |Il nome potrebbe sembrare strano perché è così lungo, ma è il nome corretto per quel tipo di sensibili. Assicurarsi di utilizzare nomi esatti dall'inventario dei [tipi di informazioni riservate](https://go.microsoft.com/fwlink/?LinkID=509999). È inoltre possibile utilizzare il nome di un [tipo di informazioni riservate personalizzato](create-a-custom-sensitive-information-type.md) creato per l'organizzazione.  <br/> |
| `SensitiveType:"Credit Card Number|1..4294967295|1..100"` <br/> |In questo modo vengono restituiti documenti con almeno una corrispondenza al tipo sensibile "numero di carta di credito". I valori per ogni intervallo corrispondono ai rispettivi valori minimi e massimi. Un modo più semplice per scrivere questa query è `SensitiveType:"Credit Card Number"` , ma qual è il divertimento in questo?  <br/> |
| `SensitiveType:"Credit Card Number| 5..25" AND LastSensitiveContentScan:"8/11/2018..8/13/2018"` <br/> |Restituisce documenti con 5-25 numeri di carta di credito che sono stati analizzati dall'11 agosto 2018 al 13 agosto 2018.  <br/> |
| `SensitiveType:"Credit Card Number| 5..25" AND LastSensitiveContentScan:"8/11/2018..8/13/2018" NOT FileExtension:XLSX` <br/> |Restituisce documenti con 5-25 numeri di carta di credito che sono stati analizzati dall'11 agosto 2018 al 13 agosto 2018. I file con estensione XLSX non sono inclusi nei risultati della query.  `FileExtension`è una delle numerose proprietà che è possibile includere in una query. Per ulteriori informazioni, vedere [utilizzo di proprietà e operatori di ricerca con eDiscovery](https://go.microsoft.com/fwlink/?LinkId=510093).  <br/> |
| `SensitiveType:"Credit Card Number" OR SensitiveType:"U.S. Social Security Number (SSN)"` <br/> |In questo modo vengono restituiti i documenti che contengono sia un numero di carta di credito che un numero di previdenza sociale.  <br/> |
   
## <a name="examples-of-queries-to-avoid"></a>Esempi

Non tutte le query vengono create allo stesso modo. Nella tabella seguente vengono forniti esempi di query che non funzionano con DLP in SharePoint e viene descritto il motivo.
  
|**Query non supportate**|**Motivo**|
|:-----|:-----|
| `SensitiveType:"Credit Card Number|.."` <br/> |Aggiungere almeno un numero.  <br/> |
| `SensitiveType:"NotARule"` <br/> |"NotARule" non è un nome di tipo sensibile valido. Solo i nomi dei [tipi di informazioni riservate](https://go.microsoft.com/fwlink/?LinkID=509999) funzionano nell'inventario delle query DLP.  <br/> |
| `SensitiveType:"Credit Card Number|0"` <br/> |Zero non è valido come valore minimo o valore massimo di un intervallo.  <br/> |
| `SensitiveType:"Credit Card Number"` <br/> |Potrebbe essere difficile da vedere, ma c'è spazio vuoto supplementare tra "credito" e "carta" che rende la query non valida. Utilizzare nomi di tipo sensibili esatti dall' [inventario dei tipi di informazioni riservate](https://go.microsoft.com/fwlink/?LinkID=509999).  <br/> |
| `SensitiveType:"Credit Card Number|1. .3"` <br/> |La parte di due periodi non deve essere separata da uno spazio.  <br/> |
| `SensitiveType:"Credit Card Number| |1..|80.."` <br/> |Sono presenti troppi delimitatori di pipe (|). Seguire questo formato invece:`SensitiveType: "Credit Card Number|1..|80.."` <br/> |
| `SensitiveType:"Credit Card Number|1..|80..101"` <br/> |Poiché i valori di sicurezza rappresentano una percentuale, non possono superare 100. Scegliere un numero compreso tra 1 e 100.  <br/> |
   
## <a name="for-more-information"></a>Ulteriori informazioni

- [Definizioni di entità per il tipo di informazioni riservate](sensitive-information-type-entity-definitions.md)
- [Eseguire una Ricerca contenuto](content-search.md)
- [Query con parole chiave e condizioni di ricerca per la Ricerca contenuto](keyword-queries-and-search-conditions.md)
  

