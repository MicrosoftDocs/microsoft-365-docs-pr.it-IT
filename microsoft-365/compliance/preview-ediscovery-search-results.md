---
title: Visualizzare in anteprima i risultati di una ricerca eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MED150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Visualizzare in anteprima un campione dei risultati restituiti da una Ricerca contenuto o da una ricerca Core eDiscovery nel Centro conformità Microsoft 365.
ms.openlocfilehash: a89c8c9ed2500b4e2a859c75be3da177203d1406
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538600"
---
# <a name="preview-ediscovery-search-results"></a>Visualizzare in anteprima i risultati di una ricerca di eDiscovery

Dopo aver eseguito una Ricerca contenuto o una ricerca associata a un caso di Core eDiscovery, è possibile visualizzare in anteprima un campione dei risultati restituiti dalla ricerca. La visualizzazione in anteprima degli elementi restituiti dalla query di ricerca consente di determinare se la ricerca restituisce i risultati previsti o se è necessario modificare la query ed eseguire di nuovo la ricerca.

Per visualizzare in anteprima un campione dei risultati restituiti da una ricerca:

1. Nel Centro conformità Microsoft 365, passare alla pagina Ricerca contenuto o a un caso di Core eDiscovery.

2. Selezionare la ricerca per visualizzare la pagina a comparsa.

3. Nella parte inferiore della pagina, fare clic su **Verifica campione**.

   ![Fare clic su Esamina esempio nella pagina a comparsa per visualizzare in anteprima i risultati](../media/PreviewSearchResults1.png)

   Viene visualizzata una pagina contenente un esempio dei risultati della ricerca.

4. Selezionare un elemento per visualizzarne il contenuto nel Riquadro di lettura.

   ![Visualizzare in anteprima gli elementi nel Riquadro di lettura](../media/PreviewSearchResults2.png)

   Nello screenshot precedente, le parole chiave della query di ricerca sono evidenziate quando si visualizza l'anteprima degli elementi.

## <a name="how-the-search-result-samples-are-selected"></a>Come vengono selezionati gli esempi dei risultati della ricerca

Per l'anteprima sono disponibili al massimo 1.000 elementi selezionati casualmente. Oltre a essere selezionati in modo casuale, gli elementi disponibili per l'anteprima devono anche soddisfare i criteri seguenti:

- È possibile visualizzare in anteprima un massimo di 100 elementi da un singolo percorso di contenuto (una cassetta postale o un sito). Ciò significa che è possibile che meno di 1.000 elementi siano disponibili per l'anteprima. Ad esempio, se si cerca in quattro cassette postali e la ricerca restituisce 1.500 elementi stimati, solo 400 saranno disponibili per l'anteprima, perché è possibile visualizzare in anteprima solo 100 elementi per ogni cassetta postale.

- Per gli elementi della cassetta postale, l'anteprima è disponibile solo per i messaggi di posta elettronica. Non è possibile visualizzare in anteprima elementi come attività, elementi del calendario e contatti.

- Per gli elementi del sito, l'anteprima è disponibile solo per i documenti. Non è possibile visualizzare in anteprima elementi come cartelle, elenchi o allegati di elenchi.

## <a name="file-types-supported-when-previewing-search-results"></a>Tipi di file supportati quando si visualizza l'anteprima dei risultati della ricerca

È possibile visualizzare l'anteprima dei tipi di file supportati nel riquadro di anteprima. Se un tipo di file non è supportato, è necessario scaricarne una copia nel computer locale facendo clic su **Scarica elemento originale**. Nelle pagine Web ASPX l'URL della pagina è incluso, anche se l'utente potrebbe non avere le autorizzazioni per accedere alla pagina. Gli elementi non indicizzati non sono disponibili per la visualizzazione in anteprima.

I tipi di file seguenti sono supportati e possono essere visualizzati in anteprima nel riquadro risultati della ricerca.
  
- .txt, .html, .mhtml

- .eml

- .doc, .docx, .docm

- .pptm, .pptx

- .pdf

Sono supportati anche i seguenti tipi di contenitori di file. È possibile visualizzare l'elenco di file nel contenitore nel riquadro di anteprima.
  
- .zip

- .gzip