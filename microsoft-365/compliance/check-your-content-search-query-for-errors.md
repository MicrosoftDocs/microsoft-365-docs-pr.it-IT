---
title: Verificare la presenza di errori nella query di Ricerca contenuto
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 11/30/2016
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 88898874-e262-4c5c-b6d2-4e697497fc74
ms.custom:
- seo-marvel-apr2020
description: Informazioni su come controllare la query di parole chiave per la ricerca di contenuto per errori e refusi, ad esempio i caratteri non supportati e gli operatori booleani minuscoli.
ms.openlocfilehash: 489afd8b2fe19742b63232d323197afecc257ccc
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035628"
---
# <a name="check-your-content-search-query-for-errors"></a>Verificare la presenza di errori nella query di Ricerca contenuto

Quando si crea o si modifica una ricerca di contenuto, è possibile che Microsoft 365 verifichi la query per i caratteri non supportati e gli operatori booleani minuscoli. Come? Basta fare clic su **Controlla query per errori di battitura** nella pagina query di una ricerca contenuto. 
  
![Fare clic su "controlla query per errori di battitura" per controllare la query di ricerca per i caratteri non supportati](../media/e5314306-cfb2-481d-9b5c-13ce658156e7.png)
  
Di seguito è indicato un elenco dei caratteri non supportati che vengono verificati. I caratteri non supportati sono spesso nascosti e in genere causano un errore di ricerca o restituiscono risultati indesiderati.
  
- Virgolette **Smart** -le virgolette singole e doppie (chiamate anche virgolette) non sono supportate. In una query di ricerca è possibile utilizzare solo virgolette semplici. 
    
- **Caratteri non stampabili e di controllo** : i caratteri non stampabili e di controllo non rappresentano un simbolo scritto, ad esempio un carattere alfanumerico. Alcuni esempi di caratteri di controllo e non stampabili includono caratteri che formattano il testo o righe separate di testo. 
    
- **Segni da sinistra a destra e da destra a sinistra** -questi contrassegni sono caratteri di controllo utilizzati per indicare la direzione del testo per le lingue da sinistra a destra, ad esempio l'inglese e lo spagnolo, e le lingue da destra a sinistra, ad esempio l'arabo e l'ebraico.
    
- **Operatori booleani minuscoli** : se si utilizza un operatore booleano, ad esempio **e**, **o**e **non** in una query di ricerca, è necessario che sia maiuscolo. Quando si controlla una query per errori di battitura, la sintassi della query indica spesso che è in uso un operatore booleano, anche se possono essere utilizzati operatori minuscoli; ad esempio, `(WordA or WordB) and (WordC or WordD)`.
    
## <a name="what-happens-if-a-query-has-an-unsupported-character"></a>Cosa succede se una query ha un carattere non supportato?

Se nella query sono presenti caratteri non supportati, viene visualizzato un messaggio di avviso che indica che sono stati trovati caratteri non supportati e che viene suggerita un'alternativa. È quindi necessario mantenere la query originale o sostituirla con la query riveduta consigliata. Di seguito è riportato un esempio del messaggio di avviso visualizzato dopo aver fatto clic su **Controlla query per errori** di recapito per la query di ricerca nella schermata precedente. Si noti che la query originale contiene le virgolette intelligenti e gli operatori booleani minuscoli. 
  
![Viene visualizzato un messaggio di avviso con una revisione consigliata per la query](../media/23214b30-8e52-412c-bd80-63fb1b3ed52d.png)
  
## <a name="how-to-prevent-unsupported-characters-in-your-search-queries"></a>Come impedire i caratteri non supportati nelle query di ricerca

I caratteri non supportati vengono in genere aggiunti a una query quando si copia la query o parti della query da altre applicazioni, ad esempio Microsoft Word o Microsoft Excel, e incollarle nella casella parola chiave della pagina query di una ricerca di contenuto. Il modo migliore per evitare che i caratteri non supportati è solo digitare la query nella casella parola chiave. In alternativa, è possibile copiare una query da Word o Excel e incollarla in un editor di testo normale, ad esempio il blocco note Microsoft. Salvare il file di testo e selezionare **ANSI** nell'elenco a discesa **Encoding** . In questo modo, verranno rimossi tutti i caratteri di formattazione e non supportati. È quindi possibile copiare e incollare la query dal file di testo nella casella query parola chiave. 
