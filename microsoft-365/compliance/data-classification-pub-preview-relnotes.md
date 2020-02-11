---
title: Note sulla versione di anteprima della classificazione dei dati (anteprima)
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
description: Note sulla versione di anteprima pubblica della classificazione dei dati.
ms.openlocfilehash: fecf643d12cf544c16570c173b15bb1e0dc043f0
ms.sourcegitcommit: 3d17c1d6b80672719b1878e2f321f0de39595226
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2020
ms.locfileid: "41887339"
---
# <a name="data-classification-public-preview-release-notes-preview"></a>Note sulla versione di anteprima pubblica della classificazione dei dati (anteprima)

Questa anteprima pubblica introduce nuove funzionalità, grazie alle quali l'analisi del contenuto riservato e del contenuto con etichetta inizia *prima* della creazione di criteri. Tale operazione è nota come **gestione senza modifiche**. Consente di vedere l'impatto di tutte le etichette di conservazione e di riservatezza sul proprio ambiente e permette di valutare la necessità di iniziare a usare criteri di protezione e di governance.

Per un'esperienza ottimale con questa anteprima pubblica, leggere le note sulla versione. I punti attualmente in sospeso verranno risolti nella versione di disponibilità generale.

## <a name="permissions-for-accessing-content-explorer"></a>Autorizzazioni per accedere a Esplora contenuto

L'accesso a Esplora contenuto è estremamente limitato perché consente di leggere il contenuto dei file digitalizzati. L'accesso a Esplora contenuto richiede l'appartenenza ai gruppi di ruolo **Visualizzatore elenco di esplora contenuto** e **Visualizzatore contenuto di Esplora contenuto**. Nessun account ha accesso a Esplora contenuto per impostazione predefinita. Consultare [Utilizzo di Esplora contenuto di classificazione dei dati (anteprima)](data-classification-content-explorer.md#permissions). Un amministratore globale, un amministratore di conformità o un amministratore dei dati può assegnare l'appartenenza ai gruppi di ruolo **Visualizzatore elenco di Esplora contenuto** e **Visualizzatore contenuto di Esplora contenuto** necessaria.

> [!TIP]
> I gruppi di ruolo **Visualizzatore elenco di Esplora contenuto**e **Visualizzatore contenuto di Esplora contenuto** potrebbero non essere presenti nella pagina autorizzazioni mentre i controlli di accesso basati sui ruoli sono distribuiti a livello mondiale. Se non sono presenti nella pagina autorizzazioni, è necessario creare un gruppo di ruoli personalizzato e assegnare il ruolo `data classification list viewer` e o i ruoli `data classification content viewer` al gruppo di ruoli personalizzato.

## <a name="exchange-mailbox-count"></a>Numero di cassette postali di Exchange

Quando si esegue l'analisi delle cassette postali di Exchange, viene visualizzata una piccola descrizione comando. Questo per evidenziare che il totale visualizzato per il tipo di informazioni riservate, l'etichetta di riservatezza e l'etichetta di conservazione potrebbe non corrispondere esattamente al numero di elementi presenti nella cassetta postale. Ciò avviene perché il drill-down nella cartella recupera la visualizzazione in tempo reale del contenuto, che è classificato, mentre viene calcolato il totale.

## <a name="seeing-guids-instead-of-label-names"></a>Visualizzare GUID anziché nomi etichette

I clienti dell'anteprima privata hanno visto che istanze di eliminazione di etichette con cui erano stati contrassegnati contenuti hanno causato la restituzione di GUID a 32 bit in Esplora contenuto e Esplora attività anziché la visualizzazione del nome dell'etichetta. 

## <a name="rendering-of-encrypted-documents"></a>Rendering di documenti crittografati

I file di SharePoint, Exchange e OneDrive crittografati non verranno visualizzati in Esplora contenuto. Si tratta di un problema delicato che richiede un equilibrio tra la necessità di visualizzare il contenuto del file in Esplora contenuto e la necessità di mantenere crittografato il contenuto. Con le autorizzazioni concesse dai gruppi di ruoli **Visualizzatore elenco di Esplora contenuto** e **Visualizzatore contenuto di Esplora contenuto**, si potrà vedere una visualizzazione elenco dei file, i metadati del file e un collegamento che è possibile usare per accedere al contenuto tramite il client Web.

## <a name="supported-characters-in-retention-label-names-in-sharepoint-search"></a>Caratteri supportati nei nomi delle etichette di conservazione nel servizio di ricerca di SharePoint

Il servizio di ricerca di SharePoint non supporta nomi delle etichette di conservazione contenenti `-` o `_`. Ad esempio, non supporta `Label-MIP` e `Label_MIP`. Il servizio di ricerca di SharePoint non supporta tali caratteri nei nomi delle etichette di riservatezza e nei nomi dei tipi di informazioni riservate.

## <a name="see-also"></a>Vedere anche

- [Introduzione alla classificazione dei dati (anteprima)](data-classification-overview.md)
- [Visualizzazione delle attività con etichette (anteprima)](data-classification-activity-explorer.md)
- [Visualizzare il contenuto con etichetta (anteprima)](data-classification-content-explorer.md)
- [Etichette di riservatezza](sensitivity-labels.md)
- [Etichette di conservazione](labels.md)
- [Tipi di informazioni riservate disponibili da cercare](what-the-sensitive-information-types-look-for.md)

