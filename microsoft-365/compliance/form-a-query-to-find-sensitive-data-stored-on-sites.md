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
description: Usare la prevenzione della perdita dei dati (DLP) in SharePoint Online per individuare i documenti che contengono dati sensibili in tutto il tenant.
ms.openlocfilehash: 04bf2e97dd2b5530838aef9fcb4b4467270d2d9d
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287480"
---
# <a name="form-a-query-to-find-sensitive-data-stored-on-sites"></a>Creare una query per trovare i dati sensibili archiviati nei siti

Gli utenti memorizzano spesso dati riservati, ad esempio il numero della carta di credito, il numero di previdenza sociale o il codice fiscale e con il tempo possono esporre l'organizzazione al rischio di perdita di tali dati. I documenti archiviati nei siti, inclusi OneDrive for Business, potrebbero essere condivisi con persone esterne all'organizzazione che non dovrebbero avere accesso alle informazioni. Con la prevenzione della perdita dei dati (DLP) in SharePoint Online, è possibile individuare i documenti che contengono dati sensibili in tutto il tenant. Dopo aver individuato i documenti, è possibile collaborare con i proprietario al fine di proteggere i dati. In questo argomento viene illustrato come creare una query per cercare dati riservati.

> [!NOTE]
> L'individuazione elettronica, eDiscovery e DLP sono funzionalità premium che richiedono SharePoint [Online Piano 2.](https://go.microsoft.com/fwlink/?LinkId=510080)

## <a name="forming-a-basic-dlp-query"></a>Creazione di una query DLP di base

Una query DLP di base è formata da tre parti: SensitiveType, intervallo conteggio e intervallo di confidenza. Come illustrato nell'immagine seguente, **SensitiveType:" \<type\> " è** obbligatorio ed **|\<count range\>** entrambi e sono **|\<confidence range\>** facoltativi.

![Query di esempio divisa in necessaria e facoltativa](../media/DLP-query-example-text.png)

### <a name="sensitive-type---required"></a>SensitiveType - obbligatorio

Quindi, a cosa corrisponde ogni parte? SharePoint Le query DLP in genere iniziano con la proprietà e un nome di tipo di informazioni dall'inventario dei tipi di informazioni riservate `SensitiveType:"` e terminano con un [](/Exchange/what-the-sensitive-information-types-in-exchange-look-for-exchange-2013-help) `"` . È inoltre possibile utilizzare il nome di un [tipo di informazioni](create-a-custom-sensitive-information-type.md) riservate personalizzato creato per l'organizzazione. Ad esempio, è possibile cercare documenti che includono numeri di carta di credito. In un'istanza di questo tipo si utilizzerà il formato seguente:  `SensitiveType:"Credit Card Number"` . Poiché non è stato incluso un intervallo di conteggio o di confidenza, la query restituisce tutti i documenti in cui viene rilevato un numero di carta di credito. Questa è la query più semplice da eseguire e restituisce il maggior numero di risultati. Ricordare che vengono presi in considerazione sia l'ortografia che il numero di spazi.

### <a name="ranges---optional"></a>Intervalli - facoltativo

Entrambe le due parti seguenti sono intervalli, quindi esaminiamo rapidamente l'aspetto di un intervallo. Nelle SharePoint DLP, un intervallo di base è rappresentato da due numeri separati da due punti, che hanno un aspetto simile al seguente: `[number]..[number]` . Ad esempio, se  `10..20` viene utilizzato, tale intervallo acquisisce numeri da 10 a 20. Sono disponibili molte combinazioni di intervallo e molte sono descritte in questo argomento.

Aggiungiamo un intervallo di conteggio alla query. È possibile utilizzare l'intervallo di conteggio per definire il numero di occorrenze di informazioni riservate che un documento deve contenere prima di essere incluso nei risultati della query. Ad esempio, se si desidera che la query restituirà solo i documenti che contengono esattamente cinque numeri di carta di credito, utilizzare:  `SensitiveType:"Credit Card Number|5"` . L'intervallo di conteggio consente anche di identificare i documenti a rischio elevato. Ad esempio, l'organizzazione potrebbe considerare a rischio i documenti con 5 o più numeri di carta di credito. Per trovare documenti che si adattano a questo criterio, utilizzare la query seguente:  `SensitiveType:"Credit Card Number|5.."` . In alternativa, è possibile trovare documenti con cinque o meno numeri di carta di credito utilizzando questa query:  `SensitiveType:"Credit Card Number|..5"` .

#### <a name="confidence-range"></a>Intervallo di confidenza

Infine, intervallo di confidenza consiste nel livello di confidenza con il quale il tipo di informazione riservata identificata rappresenta effettivamente una corrispondenza. I valori relativi all'intervallo di confidenza funzionano in modo analogo all'intervallo di conteggio. È possibile creare una query senza includere un intervallo di conteggio. Ad esempio, per cercare documenti con un numero qualsiasi di numeri di carta di credito, purché l'intervallo di probabilità sia dell'85% o superiore, utilizzare la query seguente:  `SensitiveType:"Credit Card Number|*|85.."` .

> [!IMPORTANT]
> L'asterisco ( `*` ) è un carattere jolly che indica che qualsiasi valore funziona. È possibile utilizzare il carattere jolly ( ) nell'intervallo di conteggio o nell'intervallo di confidenza, ma `*` non in un tipo sensibile.

### <a name="additional-query-properties-and-search-operators-available-in-the-ediscovery-center"></a>Ulteriori proprietà della query e operatori di ricerca sono disponibili nel Centro eDiscovery

DLP in SharePoint introduce anche la proprietà LastSensitiveContentScan, che consente di cercare i file analizzati in un intervallo di tempo specifico. Per esempi di query con  `LastSensitiveContentScan` la proprietà , vedere la sezione Esempi di [query](#examples-of-complex-queries) complesse nella sezione successiva.

È possibile utilizzare non solo proprietà specifiche della prevenzione della perdita dei dati per creare una query, ma anche proprietà di SharePoint di ricerca eDiscovery standard, ad esempio `Author` o `FileExtension` . È possibile utilizzare gli operatori per creare query complesse. Per l'elenco delle proprietà e degli operatori disponibili, vedere il post di blog [Using Search Properties and Operators with eDiscovery.](/archive/blogs/quentin/using-search-properties-and-operators-with-ediscovery)

## <a name="examples-of-complex-queries"></a>Esempi

Negli esempi seguenti vengono utilizzati tipi sensibili, proprietà e operatori diversi per illustrare come perfezionare le query per trovare esattamente ciò che si sta cercando.

<br>

****

|Query|Spiegazione|
|---|---|
|`SensitiveType:"International Banking Account Number (IBAN)"`|Il nome potrebbe sembrare strano perché è così lungo, ma è il nome corretto per quel tipo sensibile. Assicurarsi di utilizzare nomi esatti [dall'inventario dei tipi di informazioni riservate.](/Exchange/what-the-sensitive-information-types-in-exchange-look-for-exchange-2013-help) È inoltre possibile utilizzare il nome di un [tipo di informazioni](create-a-custom-sensitive-information-type.md) riservate personalizzato creato per l'organizzazione.|
|`SensitiveType:"Credit Card Number|1..4294967295|1..100"`|In questo modo vengono restituiti i documenti con almeno una corrispondenza con il tipo sensibile "Numero carta di credito". I valori per ogni intervallo corrispondono ai rispettivi valori minimi e massimi. Un modo più semplice per scrivere questa query è , ma  `SensitiveType:"Credit Card Number"` qual è il divertimento?|
|`SensitiveType:"Credit Card Number|5..25" AND LastSensitiveContentScan:"8/11/2018..8/13/2018"`|In questo modo vengono restituiti i documenti con 5-25 numeri di carta di credito analizzati dall'11 agosto 2018 al 13 agosto 2018.|
|`SensitiveType:"Credit Card Number|5..25" AND LastSensitiveContentScan:"8/11/2018..8/13/2018" NOT FileExtension:XLSX`|In questo modo vengono restituiti i documenti con 5-25 numeri di carta di credito analizzati dall'11 agosto 2018 al 13 agosto 2018. I file con estensione XLSX non vengono inclusi nei risultati della query.  `FileExtension` è una delle numerose proprietà che è possibile includere in una query. Per ulteriori informazioni, vedere [Using Search Properties and Operators with eDiscovery](/archive/blogs/quentin/using-search-properties-and-operators-with-ediscovery).|
|`SensitiveType:"Credit Card Number" OR SensitiveType:"U.S. Social Security Number (SSN)"`|In questo modo vengono restituiti i documenti che contengono sia un numero di carta di credito che un numero di previdenza sociale.|
|

## <a name="examples-of-queries-to-avoid"></a>Esempi

Non tutte le query vengono create allo stesso modo. Nella tabella seguente vengono forniti esempi di query che non funzionano con DLP in SharePoint e ne viene descritto il motivo.

<br>

****

|Query non supportate|Motivo|
|---|---|
|`SensitiveType:"Credit Card Number|.."`|Aggiungere almeno un numero.|
|`SensitiveType:"NotARule"`|"NotARule" non è un nome di tipo sensibile valido. Solo i nomi [nell'inventario dei tipi di informazioni riservate](/Exchange/what-the-sensitive-information-types-in-exchange-look-for-exchange-2013-help) funzionano nelle query DLP.|
|`SensitiveType:"Credit Card Number|0"`|Zero non è valido come valore minimo o massimo in un intervallo.|
|`SensitiveType:"Credit Card Number"`|Potrebbe essere difficile da visualizzare, ma c'è spazio vuoto aggiuntivo tra "Credito" e "Carta" che rende la query non valida. Utilizzare nomi di tipi sensibili esatti [dall'inventario dei tipi di informazioni riservate.](/Exchange/what-the-sensitive-information-types-in-exchange-look-for-exchange-2013-help)|
|`SensitiveType:"Credit Card Number|1. .3"`|La parte a due punti non deve essere separata da uno spazio.|
|`SensitiveType:"Credit Card Number| |1..|80.."`|Sono presenti troppi delimitatori di pipe ( \| ). Segui invece questo formato: `SensitiveType: "Credit Card Number|1..|80.."`|
|`SensitiveType:"Credit Card Number|1..|80..101"`|Poiché i valori di confidenza rappresentano una percentuale, non possono superare 100. Scegliere un numero compreso tra 1 e 100.|
|

## <a name="for-more-information"></a>Ulteriori informazioni

- [Definizioni delle entità tipo di informazioni sensibili](sensitive-information-type-entity-definitions.md)
- [Eseguire una Ricerca contenuto](content-search.md)
- [Query con parole chiave e condizioni di ricerca per la Ricerca contenuto](keyword-queries-and-search-conditions.md)
