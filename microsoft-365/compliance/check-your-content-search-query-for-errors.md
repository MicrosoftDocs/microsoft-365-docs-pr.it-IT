---
title: Verificare la presenza di errori nella query di Ricerca contenuto
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
search.appverid:
- MOE150
- MET150
ms.assetid: 88898874-e262-4c5c-b6d2-4e697497fc74
ms.custom: seo-marvel-apr2020
description: Informazioni su come rilevare errori e errori di digitazione nella query con parole chiave per ricerca contenuto, prima di eseguire la ricerca.
ms.openlocfilehash: 939ac3d227f176a0b74138107ced5dd5b7142bcd
ms.sourcegitcommit: 7ebed5810480d7c49f8ca03207b5ea84993d253f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "51488213"
---
# <a name="check-your-content-search-query-for-errors"></a>Verificare la presenza di errori nella query di Ricerca contenuto
  
Ecco un elenco dei caratteri non supportati che controlliamo. I caratteri non supportati sono spesso nascosti e in genere causano un errore di ricerca o restituiscono risultati imprevisti.
  
- **Virgolette intelligenti** : le virgolette singole e doppie intelligenti (denominate anche virgolette graffe) non sono supportate. In una query di ricerca è possibile utilizzare solo virgolette semplici. 

- **Caratteri non stampabili e** di controllo - I caratteri non stampabili e di controllo non rappresentano un simbolo scritto, ad esempio un carattere alfanumerico. Esempi di caratteri non stampabili e di controllo includono caratteri che formattano testo o righe di testo separate. 

- **Segni da** sinistra a destra e da destra a sinistra- Questi segni sono caratteri di controllo utilizzati per indicare la direzione del testo per le lingue da sinistra a destra (ad esempio inglese e spagnolo) e le lingue da destra a sinistra (ad esempio arabo ed ebraico).

- **Operatori booleani** minuscoli- Se si utilizza un operatore booleano, ad esempio **AND**, **OR** e **NOT** in una query di ricerca, è necessario che sia maiuscolo. Quando si verifica la presenza di errori di digitazione in una query, la sintassi della query spesso indica che viene utilizzato un operatore Boolean anche se è possibile utilizzare operatori minuscoli. ad  `(WordA or WordB) and (WordC or WordD)` esempio.

## <a name="what-happens-if-a-query-has-an-unsupported-character"></a>Cosa succede se una query ha un carattere non supportato?

Se nella query vengono trovati caratteri non supportati, viene visualizzato un messaggio di avviso che indica che sono stati trovati caratteri non supportati e suggerisce un'alternativa. È quindi possibile mantenere la query originale o sostituirla con la query rivista suggerita.

Ecco un esempio del messaggio di avviso visualizzato dopo aver fatto clic su Controlla **query** per errori di digitazione per la query di ricerca nello screenshot precedente. Si noti che la query originale ha utilizzato le virgolette intelligenti e gli operatori booleani minuscoli.
  
![Viene visualizzato un messaggio di avviso con una revisione suggerita per la query](../media/23214b30-8e52-412c-bd80-63fb1b3ed52d.png)
  
## <a name="how-to-prevent-unsupported-characters-in-your-search-queries"></a>Come impedire i caratteri non supportati nelle query di ricerca

I caratteri non supportati vengono in genere aggiunti a una query quando si copiano la query o parti della query da altre applicazioni , ad esempio Microsoft Word o Microsoft Excel, e li si incolla nella casella delle parole chiave nella pagina della query di una ricerca contenuto. Il modo migliore per impedire i caratteri non supportati è semplicemente digitare la query nella casella parola chiave. Oppure è possibile copiare una query da Word o Excel e quindi incollarla in un editor di testo normale, ad esempio Blocco note Microsoft. Salvare il file di testo e selezionare **ANSI** **nell'elenco a** discesa Codifica. Questa operazione rimuoverà la formattazione e i caratteri non supportati. È quindi possibile copiare e incollare la query dal file di testo alla casella di query con parole chiave. 
