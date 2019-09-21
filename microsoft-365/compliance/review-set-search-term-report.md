---
title: Generare il rapporto termini di ricerca per un set di Revisione
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
ROBOTS: NOINDEX, NOFOLLOW
description: ''
ms.openlocfilehash: 877c0017359ab9193c4cae81cbef4240909053a8
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37084751"
---
# <a name="generate-search-term-report-for-a-review-set"></a>Generare il rapporto termini di ricerca per un set di Revisione

In eDiscovery, una delle condizioni utilizzate più frequentemente per l'esecuzione di query nei documenti è l'utilizzo dei termini di ricerca parole chiave. Identificando i documenti che contengono le parole chiave specifiche (denominate anche *termini*) importanti per un caso, i revisori possono iniziare ad ottenere una comprensione di alto livello di cosa devono affrontare. In Advanced eDiscovery in Microsoft 365, è possibile eseguire questa operazione generando rapporti termini di ricerca per le query salvate all'interno di un set di revisione.

## <a name="step-1-create-a-saved-query-in-the-review-set"></a>Passaggio 1: creare una query salvata nel set di Revisione

Per generare un rapporto di termini di ricerca significativo, creare una query salvata che definisce il set di documenti nel set di revisione per il quale si desidera generare un rapporto di termini di ricerca. Ad esempio, è possibile utilizzare un intervallo di date o il set effettivo di termini di ricerca (utilizzando la scheda condizione parole chiave) per creare la query. Per ulteriori informazioni sulle query dei set di revisione, vedere [query sui dati in un set di revisione](review-set-search.md).

## <a name="step-2-generate-a-search-term-report"></a>Passaggio 2: generare un rapporto di termini di ricerca

Esistono due modi diversi per generare un rapporto termini di ricerca: tramite il menu di scelta rapida della query salvata creata al passaggio 1 o tramite la console di gestione dei rapporti termini di ricerca.

- Per utilizzare il menu di scelta rapida, aprire il menu di scelta rapida della query salvata creata nel passaggio 1, quindi fare clic su **Genera rapporto termini di ricerca**.

- Per utilizzare la console di gestione, andare a **Manage Review set > visualizzare i report dei termini di ricerca**, fare clic su **nuovo**e quindi selezionare la query salvata creata al passaggio 1.

Immettere quindi i termini che si desidera segnalare, separati da NewLine. Se la query salvata creata al passaggio 1 è stata utilizzata la scheda condizione parola chiave, la pagina del riquadro a comparsa verrà prepopolata con i termini della prima scheda di condizione di parola chiave utilizzata nella query salvata.

Selezionare fino a tre pivot per il report e quindi fare clic su **genera**, che avvierà il processo di generazione del rapporto termini di ricerca.

### <a name="what-is-a-pivot"></a>Che cos'è un pivot?

Pivot sono la modalità di organizzazione del rapporto. Si consideri l'esempio seguente.

- La query salvata recupera 10 documenti: doc1 thru doc10.

- Doc1, Doc2, DOC3, DOC4, DOC5, DOC6 e DOC7 contengono il termine "eDiscovery".

- DOC6, DOC7, DOC8, doc9 e doc10 contengono il termine "Investigation".

- Doc1, DOC3, DOC5, DOC7, doc9 sono del custode A.

- Doc2, DOC4, DOC6, DOC8, doc10 sono del custode B.

In questo caso, se si desidera generare un rapporto sui termini "eDiscovery" e "Investigation" e pivot nei depositari, il report dei termini di ricerca verrebbe organizzato come indicato di seguito:

- "eDiscovery"-custode A: 4 documenti

- "eDiscovery"-custode B: 3 documenti

- "Investigation"-custode A: 2 documenti

- "Indagine"-custode B: 3 documenti

## <a name="step-3-download-report"></a>Passaggio 3: scaricare il report

Nella console di gestione dei termini di ricerca è possibile monitorare lo stato di un processo del rapporto termini di ricerca creato in precedenza. Al termine del processo, è possibile fare clic sulla riga per il rapporto termini di ricerca e fare clic su "download", che scaricherà il rapporto termini di ricerca in formato CSV. Vi sarà una riga per ogni tupla (termine di ricerca, pivot) e ogni riga conterrà le informazioni seguenti:

- Quanti documenti sono stati recuperati?

- Quante volte è stato trovato il termine di ricerca nei documenti?

- Qual è il volume totale dei documenti recuperati?

- Quante famiglie sono state recuperate?

- Qual è il numero totale di documenti di tali famiglie, inclusi i documenti che non hanno il termine di ricerca?

- Qual è il volume totale di quanto sopra?