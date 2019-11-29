---
title: Utilizzo di Esplora contenuto di classificazione dei dati (anteprima)
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Esplora contenuto consente di visualizzare in modo nativo gli elementi con etichetta.
ms.openlocfilehash: 6f062901acbf149f6fc56c266d10b370ed0c1112
ms.sourcegitcommit: 8ca97fa879ae4ea44468be629d6c32b429efeeec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/16/2019
ms.locfileid: "39268550"
---
# <a name="using-data-classification-content-explorer-preview"></a>Utilizzo di Esplora contenuto di classificazione dei dati (anteprima)

Esplora contenuto di classificazione dei dati consente di visualizzare in modo nativo gli elementi che sono stati riepilogati nella pagina di panoramica.

## <a name="content-explorer"></a>Esplora contenuto

Esplora contenuto è uno snapshot corrente degli elementi che hanno un'etichetta di riservatezza, un'etichetta di conservazione o sono stati classificati come tipo di informazioni riservate nell'organizzazione.

![schermata compressa di Esplora contenuto](media/data-classification-content-explorer-1.png)

### <a name="permissions"></a>Autorizzazioni

Esistono due ruoli che consentono di accedere a Esplora contenuto:

- **Visualizzatore elenco di Esplora contenuto**: l'appartenenza a questo ruolo consente di visualizzare ogni elemento e la relativa posizione.

- **Visualizzatore contenuto di Esplora contenuto**: l'appartenenza a questo ruolo consente di visualizzare il contenuto di ogni elemento dell'elenco.

L'account usato per accedere a Esplora contenuto deve essere in uno o entrambi i ruoli. Questi sono ruoli indipendenti e non cumulativi. Ad esempio, se si vuole concedere a un account la possibilità di visualizzare solo gli elementi e le relative posizioni, concedere i diritti di Visualizzatore elenco di Esplora contenuto. Se si vuole che lo stesso account sia in grado di visualizzare anche il contenuto degli elementi dell'elenco, concedere anche i diritti di Visualizzatore contenuto di Esplora contenuto.

### <a name="how-to-use-content-explorer"></a>Come usare Esplora contenuto

1. Aprire **Centro conformità Microsoft 365**  > **Classificazione dei dati** > **Esplora contenuto**.
2. Se si conosce il nome dell'etichetta o il tipo di informazioni riservate, è possibile digitarlo nella casella di ricerca.
3. In alternativa, è possibile cercare l'elemento espandendo il tipo di etichetta e selezionando l'etichetta dall'elenco. Di seguito viene mostrato un elemento della parte di etichetta di conservazione dell'elenco.
4. Selezionare una posizione in **Tutte le posizioni** ed eseguire il drill-down nella struttura di cartelle fino all'elemento.
5. Fare doppio clic per aprire l'elemento in modo nativo in Esplora contenuto.

## <a name="see-also"></a>Vedere anche

- [Etichette di riservatezza](sensitivity-labels.md)
- [Etichette di conservazione](labels.md)
- [Tipi di informazioni riservate disponibili da cercare](what-the-sensitive-information-types-look-for.md)
- [Panoramica dei criteri di conservazione](retention-policies.md)
