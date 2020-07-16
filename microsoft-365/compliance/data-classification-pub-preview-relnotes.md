---
title: Note sulla versione della classificazione dei dati
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
description: Note sulla versione per la classificazione dei dati.
ms.openlocfilehash: 71d8e8e4fffddc4c9373a2bdd37d4509337ec231
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2020
ms.locfileid: "45127141"
---
# <a name="data-classification-release-notes"></a>Note sulla versione della classificazione dei dati

Per un'esperienza ottimale con la classificazione dei dati, leggere le note sulla versione.

## <a name="exchange-mailbox-count"></a>Numero di cassette postali di Exchange

Quando si esegue l'analisi delle cassette postali di Exchange, viene visualizzata una piccola descrizione comando. Questo per evidenziare che il totale visualizzato per il tipo di informazioni riservate, l'etichetta di riservatezza e l'etichetta di conservazione potrebbe non corrispondere esattamente al numero di elementi presenti nella cassetta postale. Ciò avviene perché il drill-down nella cartella recupera la visualizzazione in tempo reale del contenuto, che è classificato, mentre viene calcolato il totale.


## <a name="rendering-of-encrypted-documents"></a>Rendering di documenti crittografati

I file di SharePoint, Exchange e OneDrive crittografati non verranno visualizzati in Esplora contenuto. Si tratta di un problema delicato che richiede un equilibrio tra la necessità di visualizzare il contenuto del file in Esplora contenuto e la necessità di mantenere crittografato il contenuto. Con le autorizzazioni concesse dai gruppi di ruoli **Visualizzatore elenco di Esplora contenuto** e **Visualizzatore contenuto di Esplora contenuto**, si potrà vedere una visualizzazione elenco dei file, i metadati del file e un collegamento che è possibile usare per accedere al contenuto tramite il client Web.

## <a name="supported-characters-in-retention-label-names-in-sharepoint-search"></a>Caratteri supportati nei nomi delle etichette di conservazione nel servizio di ricerca di SharePoint

Il servizio di ricerca di SharePoint non supporta nomi delle etichette di conservazione contenenti `-` o `_`. Ad esempio, non supporta `Label-MIP` e `Label_MIP`. Il servizio di ricerca di SharePoint non supporta tali caratteri nei nomi delle etichette di riservatezza e nei nomi dei tipi di informazioni riservate.

## <a name="onedrive-remains-in-preview"></a>OneDrive rimane disponibile in anteprima

Durante il programma di anteprima, abbiamo ascoltato i preziosi feedback degli utenti sull'integrazione di OneDrive. Mentre lavoriamo sulle specifiche, potrebbero verificarsi flussi o dati incoerenti. Continueremo a presentare OneDrive in anteprima finché non saranno applicate tutte le correzioni. Apprezziamo molto il continuo supporto degli utenti.


## <a name="see-also"></a>Vedere anche

- [Introduzione alla classificazione dei dati (anteprima)](data-classification-overview.md)
- [Visualizzazione delle attività con etichette (anteprima)](data-classification-activity-explorer.md)
- [Visualizzare il contenuto con etichetta (anteprima)](data-classification-content-explorer.md)
- [Informazioni sulle etichette di riservatezza](sensitivity-labels.md)
- [Informazioni sui criteri e sulle etichette di conservazione](retention.md)
- [Definizioni delle entità tipo di informazioni sensibili](sensitive-information-type-entity-definitions.md)