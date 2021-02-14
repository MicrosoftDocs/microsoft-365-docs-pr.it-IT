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
ms.custom: seo-marvel-apr2020
description: Informazioni su come rilevare errori e errori di digitazione nella query con parole chiave per la ricerca di contenuto, prima di eseguire la ricerca.
ms.openlocfilehash: 250db272014d5801bfb3927d14072eea94bd635f
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818095"
---
# <a name="check-your-content-search-query-for-errors"></a>Verificare la presenza di errori nella query di Ricerca contenuto

Quando si crea o si modifica una ricerca di contenuto, è possibile fare in modo che Microsoft 365 controlli la query per verificare la presenza di caratteri non supportati e operatori booleani minuscoli. Come? È sufficiente **fare clic su Controlla errori di digitazione** nella pagina di query di una ricerca di contenuto. 
  
![Fare clic su "Controlla errori di digitazione nella query" per verificare la presenza di caratteri non supportati nella query di ricerca](../media/e5314306-cfb2-481d-9b5c-13ce658156e7.png)
  
Ecco un elenco dei caratteri non supportati che controlliamo. I caratteri non supportati sono spesso nascosti e in genere causano un errore di ricerca o restituiscono risultati indesiderati.
  
- **Virgolette inglesi** - Le virgolette singole e doppie intelligenti (denominate anche virgolette inglesi) non sono supportate. In una query di ricerca è possibile utilizzare solo le virgolette semplici. 
    
- **Caratteri non stampabili** e di controllo: i caratteri non stampabili e di controllo non rappresentano un simbolo scritto, ad esempio un carattere alfanumerico. Tra gli esempi di caratteri non stampabili e di controllo sono inclusi i caratteri che formattano il testo o righe di testo separate. 
    
- Segni da sinistra a destra e da destra a **sinistra-** Questi segni sono caratteri di controllo utilizzati per indicare la direzione del testo per le lingue da sinistra a destra (ad esempio inglese e spagnolo) e lingue da destra a sinistra (ad esempio arabo ed ebraico).
    
- **Operatori booleani minuscoli:** se si utilizza un operatore booleano, ad esempio **AND**, **OR** e **NOT** in una query di ricerca, è necessario che sia maiuscolo. Quando viene verificata la presenza di errori di digitazione in una query, la sintassi della query spesso indica che viene utilizzato un operatore booleano anche se è possibile utilizzare operatori minuscoli. ad esempio  `(WordA or WordB) and (WordC or WordD)` .
    
## <a name="what-happens-if-a-query-has-an-unsupported-character"></a>Cosa succede se una query contiene un carattere non supportato?

Se nella query vengono trovati caratteri non supportati, viene visualizzato un messaggio di avviso che indica che sono stati trovati caratteri non supportati e suggerisce un'alternativa. È quindi possibile mantenere la query originale o sostituirla con la query modificata suggerita. Ecco un esempio del messaggio di avviso visualizzato dopo aver fatto clic su Controlla **query** per errori di digitazione per la query di ricerca nello screenshot precedente. Si noti che la query originale contiene virgolette intelligenti e operatori booleani minuscoli. 
  
![Viene visualizzato un messaggio di avviso con una revisione suggerita per la query](../media/23214b30-8e52-412c-bd80-63fb1b3ed52d.png)
  
## <a name="how-to-prevent-unsupported-characters-in-your-search-queries"></a>Come impedire i caratteri non supportati nelle query di ricerca

I caratteri non supportati vengono in genere aggiunti a una query quando si copia la query o parti di tale query da altre applicazioni, ad esempio Microsoft Word o Microsoft Excel, e li si incolla nella casella delle parole chiave nella pagina della query di una ricerca di contenuto. Il modo migliore per impedire i caratteri non supportati è semplicemente digitare la query nella casella della parola chiave. Oppure è possibile copiare una query da Word o Excel e quindi incollarla in un editor di testo normale, ad esempio Blocco note Microsoft. Salvare il file di testo e selezionare **ANSI** **nell'elenco a** discesa Codifica. In questo modo verranno rimosso tutti i caratteri di formattazione e non supportati. È quindi possibile copiare e incollare la query dal file di testo alla casella di query con parole chiave. 
