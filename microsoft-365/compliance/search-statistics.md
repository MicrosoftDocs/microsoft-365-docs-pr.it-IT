---
title: Statistiche della ricerca
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
description: ''
ms.openlocfilehash: 665ffe5fea6fa6996b405198524ef7dfb51e162f
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601743"
---
# <a name="search-statistics"></a>Statistiche della ricerca

Un modo efficace per convalidare i risultati della ricerca quando si verifica un problema di dati consiste nel visualizzare le statistiche sui risultati della ricerca per assicurarsi che siano allineate alle aspettative. Quando una ricerca è terminata, le seguenti statistiche di alto livello vengono visualizzate in **stato** nella pagina riquadro a comparsa dettagli ricerca:

![Pagina di ricerca statisics nella pagina riquadro a comparsa dettagli ricerca](media/SearchDetailsFlyout.png)

- Il numero e le dimensioni stimati degli elementi corrispondenti ai criteri di ricerca.

- Il numero e le dimensioni degli elementi parzialmente indicizzati (denominati anche *elementi non indicizzati*) che non sono disponibili per la ricerca ma che sono stati trovati nei percorsi di contenuto che sono stati inclusi nella ricerca.

- Il numero di cassette postali e i siti di cui è stata eseguita la ricerca.

Per visualizzare statistiche più dettagliate, fare clic su **statistiche** nella pagina del riquadro a comparsa dettagli ricerca. Nella pagina **statistiche di ricerca** è possibile visualizzare il riepilogo della ricerca, la posizione principale che conteneva gli elementi corrispondenti ai risultati della ricerca e le statistiche dettagliate sulla query di ricerca.

![Elenco a discesa Statistiche di ricerca](media/SearchStatisticsDropDownList.png)

## <a name="summary"></a>Riepilogo

Nella visualizzazione **Riepilogo** , è possibile visualizzare i risultati della ricerca suddivisi in base al tipo di posizione (ad esempio, le posizioni includono le cassette postali di Exchange e i siti di SharePoint). Per ogni tipo di percorso vengono visualizzate le informazioni seguenti:

- Il numero di posizioni con elementi che corrispondono ai criteri di ricerca.

- Il numero totale di elementi di ogni tipo di posizione corrispondenti ai criteri di ricerca.

- La dimensione totale degli elementi di ogni tipo di posizione corrispondenti ai criteri di ricerca.

## <a name="top-locations"></a>Posizioni principali

Nella visualizzazione **posizioni superiori** , vengono visualizzati i singoli percorsi di contenuto con la maggior parte degli elementi corrispondenti ai criteri di ricerca. Per ogni percorso del contenuto, vengono visualizzate le seguenti informazioni:

- Nome del percorso. l'indirizzo di posta elettronica per le cassette postali e l'URL per i siti di SharePoint

- Tipo di posizione

- Numero di elementi che corrispondono ai criteri di ricerca

- Dimensione totale di tutti gli elementi che corrispondono ai criteri di ricerca.

## <a name="queries"></a>Query

Nella visualizzazione **query** , è possibile visualizzare le statistiche dettagliate per ogni componente della query di ricerca. Se è stato utilizzato l'elenco di parole chiave nella query di ricerca, è possibile visualizzare le statistiche avanzate nella visualizzazione **query** che mostrano il numero di elementi che corrispondono a ogni parola chiave o frase di parola chiave. In questo modo è possibile identificare rapidamente quali parti della query sono le più (e meno) effettive. 

Nella visualizzazione **query** vengono visualizzate le informazioni seguenti:

 - **Tipo di percorso** : il tipo di percorso del contenuto per le statistiche visualizzate nella riga.

- **Part** -questa colonna visualizzerà uno dei seguenti valori: **Primary** o **keyword**. **Principale** indica che la riga presenta statistiche sull'intera query. **Keyword** significa che le statistiche della riga sono relative a uno dei componenti di query.

- **Condition** : il componente di query effettivo della query di ricerca a cui si riferisce la riga. Se il valore nella colonna **parte** è **primario**, vengono visualizzate le statistiche per l'intera query di ricerca. Se il valore è **keyword**, vengono visualizzate le statistiche per il componente della query visualizzata nella colonna **query** . Ad esempio, se è stato utilizzato l'elenco delle parole chiave, vengono visualizzate le statistiche.

  Di seguito sono riportate alcune altre informazioni relative alle statistiche visualizzate nella colonna **query** :
  
  - Quando si esegue la ricerca di tutto il contenuto nelle cassette postali (non specificando alcuna parola chiave), la query effettiva è **(dimensioni >= 0)** , in modo che tutti gli elementi vengano restituiti
  
  - Quando si eseguono ricerche in siti di SharePoint e OneDrive, nella query di ricerca vengono aggiunti i due componenti seguenti:
    
    **Not IsExternalContent: 1** -questo esclude qualsiasi contenuto di un'organizzazione di SharePoint locale
    
    **Not isOneNotePage: 1** -questo esclude tutti i file di OneNote, poiché si tratta di duplicati di qualsiasi documento corrispondente alla query di ricerca.

- **Posizioni nella ricerca** Il numero di posizioni di contenuto che presentano elementi che corrispondono alla query di ricerca per la parte o la condizione visualizzata nella riga. Si noti che le cassette postali di archiviazione vengono contate come percorso separato se contengono elementi che soddisfano i criteri di ricerca.

- **Elementi** : il numero totale di elementi che corrispondono ai criteri di ricerca per la parte o la condizione visualizzata nella riga.

- **Dimensione** : il numero totale di elementi che corrispondono ai criteri di ricerca per la parte o la condizione visualizzata nella riga.

