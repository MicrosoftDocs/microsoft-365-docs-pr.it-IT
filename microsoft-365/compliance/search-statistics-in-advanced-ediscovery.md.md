---
title: Statistiche della ricerca
ms.author: markjjo
author: esclee
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
ms.openlocfilehash: fe4d1c92230bcc4e6e1136eeb43c99cc6d8297ca
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37084152"
---
# <a name="search-statistics"></a>Statistiche della ricerca

Un modo per convalidare i risultati della ricerca consiste nell'esaminare le statistiche sui risultati per assicurarsi che siano allineate alle aspettative. Al termine della ricerca, le statistiche di alto livello vengono visualizzate nel riquadro a comparsa dettagli ricerca:
- Numero e volume degli elementi recuperati dalla ricerca
- Numero e volume degli elementi parzialmente indicizzati/non indicizzati che sono stati trovati nei percorsi di ricerca
- Numero di cassette postali e percorsi ricercati.
Per visualizzare statistiche più dettagliate, fare clic su "statistiche" nel riquadro a comparsa dettagli ricerca.

## <a name="summary"></a>Riepilogo

In visualizzazione Riepilogo, è possibile visualizzare i risultati della ricerca suddivisi in base al tipo di posizione (ad esempio, Exchange). Per ogni tipo di posizione, è possibile visualizzare le informazioni seguenti:
- Numero di posizioni in cui sono stati confrontati gli elementi che corrispondono alle condizioni di ricerca
- Il numero di elementi provenienti da questi percorsi che corrispondono alle condizioni di ricerca
- Volume totale di elementi che corrispondono alle condizioni di ricerca.

## <a name="top-locations"></a>Posizioni principali

Nella visualizzazione posizioni principali, vengono visualizzati i singoli percorsi con la maggior parte delle corrispondenze. Per ogni posizione, è possibile visualizzare le informazioni seguenti:
- Nome della posizione (ad esempio, URL di SharePoint)
- Tipo di posizione
- Numero di elementi che corrispondono alle condizioni di ricerca
- Volume totale di elementi che corrispondono alle condizioni di ricerca.

## <a name="queries"></a>Query

Se sono state utilizzate (c:s) parole chiave o righe di parole chiave nella query, è possibile visualizzare la scomposizione della query nella visualizzazione query per tipo di percorso. Per ogni tipo di posizione, verrà visualizzato quanto segue:

- Parte: questa colonna avrà la parola "Primary" o "keyword". "Primary" indica che la riga presenta statistiche sull'intera query, mentre "keyword" indica uno dei componenti di query.

- Query: il componente di query effettivo a cui fa riferimento la riga. Se la parte è "Primary", questa sarà l'intera query. Se parte è "parola chiave", in questo caso verrà visualizzato uno dei componenti di query.
  
  - Quando si esegue una ricerca in tutte le cassette postali Contentin (non specificando alcuna parola chiave), la query effettiva è (dimensioni >= 0), in modo che tutti gli elementi vengano restituiti
  
  - Quando si eseguono ricerche in siti di SharePoint Online e OneDrive for business, vengono aggiunti i due componenti seguenti:
    
    - NOT IsExternalContent: 1-esclude qualsiasi contenuto proveniente da un'organizzazione di SharePoint locale
    
    - NOT isOneNotePage: 1-esclude tutti i file di OneNote perché sono duplicati di qualsiasi documento corrispondente alla query di ricerca.

- Il numero di posizioni con elementi che corrispondono alle condizioni di ricerca.

- Il numero di elementi provenienti da questi percorsi che corrispondono alle condizioni di ricerca.

- Volume totale di elementi che corrispondono alle condizioni di ricerca.