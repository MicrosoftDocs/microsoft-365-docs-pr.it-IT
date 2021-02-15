---
title: Statistiche della ricerca in Advance eDiscovery
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
description: Convalidare i risultati della ricerca visualizzando le statistiche generate dopo l'esecuzione di una ricerca di raccolta in Advanced eDiscovery.
ms.openlocfilehash: 5b6cfdaffc7851a00035a4edcc9d490b229c455d
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/05/2021
ms.locfileid: "49750777"
---
# <a name="search-statistics-in-advanced-ediscovery"></a>Statistiche della ricerca in Advanced eDiscovery

Un modo per convalidare i risultati della ricerca è quello di esaminare le statistiche relative ai risultati per assicurarsi che siano allineati alle aspettative. Al termine di una ricerca, le statistiche di alto livello vengono visualizzate nel riquadro a comparsa dei dettagli della ricerca:

- Numero e volume di elementi recuperati dalla ricerca

- Numero e volume di elementi parzialmente indicizzati o non indicizzati trovati nei percorsi di ricerca

- Numero di cassette postali e percorsi ricercati.
Per visualizzare statistiche più dettagliate, fai clic su "Statistiche" dal riquadro a comparsa dei dettagli della ricerca.

## <a name="summary-view"></a>Visualizzazione Riepilogo

Nella visualizzazione Riepilogo, è possibile visualizzare i risultati della ricerca suddivisi per tipo di posizione (ad esempio Exchange). Per ogni tipo di posizione, è possibile vedere:

- Numero di posizioni in cui sono presenti elementi che soddisfano le condizioni di ricerca

- Numero di elementi da questi percorsi che soddisfano le condizioni di ricerca

- Volume totale di elementi che soddisfano le condizioni di ricerca.

## <a name="top-locations-view"></a>Visualizzazione Posizioni principali

Nella visualizzazione Posizioni principali vengono visualizzate le singole posizioni con il maggior numero di corrispondenze. Per ogni posizione, verranno visualizzati:

- Nome percorso (ad esempio URL di SharePoint)

- Tipo di posizione

- Numero di elementi che soddisfano le condizioni di ricerca

- Volume totale di elementi che soddisfano le condizioni di ricerca.

## <a name="queries-view"></a>Visualizzazione Query

Se nella query sono state utilizzate righe di parole chiave o parole chiave (c:s), è possibile visualizzare la suddivisione della query nella visualizzazione Query per tipo di posizione. Per ogni tipo di posizione, verrà visualizzato:

- Parte: questa colonna avrà la parola "Primary" o "Keyword". "Primary" indica che la riga presenta le statistiche sull'intera query, mentre "Keyword" indica uno dei componenti della query.

- Query: il componente di query effettivo a cui fa riferimento la riga. Se Part è "Primary", questa sarà l'intera query. Se part era "Keyword", verrà visualizzato uno dei componenti di query qui.
  
  - Quando si esegue una ricerca in tutto il contenuto nelle cassette postali (senza specificare alcuna parola chiave), la query effettiva è (dimensione >= 0) in modo che tutti gli elementi siano restituiti
  
  - Quando si esegue una ricerca nei siti di SharePoint Online e OneDrive for Business, vengono aggiunti i due componenti seguenti:
    
    - NOT IsExternalContent:1 - esclude qualsiasi contenuto da un'organizzazione di SharePoint locale
    
    - NOT isOneNotePage: 1 - esclude tutti i file di OneNote perché si tratta di duplicati di qualsiasi documento che corrisponde alla query di ricerca.

- Numero di posizioni in cui sono presenti elementi che soddisfano le condizioni di ricerca.

- Numero di elementi di questi percorsi che soddisfano le condizioni di ricerca.

- Volume totale di elementi che soddisfano le condizioni di ricerca.
