---
title: Chiudere o eliminare un caso
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
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Informazioni su cosa accade quando un'indagine o un caso legale supportato da un caso avanzato di eDiscovery è chiuso o eliminato.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e64f5cc0483129396a28cbf657778001e5d372a7
ms.sourcegitcommit: 261d51b90a9ad53a6a42348c414b1b1e1230c37f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "44292412"
---
# <a name="close-or-delete-an-advanced-ediscovery-case"></a>Chiudere o eliminare un caso avanzato di eDiscovery

Quando la causa legale o l'indagine supportata da un caso avanzato di eDiscovery è stata completata, è possibile chiudere o eliminare un caso. È inoltre possibile riaprire un caso chiuso.

## <a name="close-a-case"></a>Chiudere un caso

Ecco cosa succede quando si chiude un caso avanzato di eDiscovery:

- Se il caso contiene eventuali posizioni di contenuto in attesa, tali esenzioni saranno disattivate. Potrebbe risultare che il contenuto venga eliminato o rimosso definitivamente, dall'utente o da un processo automatizzato, ad esempio un criterio di eliminazione.

- La chiusura di un caso disattiva solo le esenzioni associate a quel caso. Se altre esenzioni sono posizionate in una posizione di contenuto, ad esempio una conservazione per controversia legale, un blocco di eDiscovery di base o un'esenzione da un caso eDiscovery avanzato diverso, tali esenzioni verranno mantenute.

- Il caso è ancora elencato nella pagina eDiscovery nel centro conformità di Microsoft 365. Vengono mantenuti i dettagli, le esenzioni, le ricerche e i membri di un caso chiuso.

- È possibile modificare un caso dopo che è stato chiuso. Ad esempio, è possibile aggiungere o rimuovere membri, creare ricerche, esportare i risultati della ricerca e preparare i risultati della ricerca per l'analisi in Advanced eDiscovery. La differenza principale tra casi attivi e chiusi consiste nel fatto che le esenzioni sono disattivate quando un caso viene chiuso.

Per chiudere un caso:

1. Nella pagina **Advanced eDiscovery** selezionare il caso che si desidera chiudere.

2. Nella scheda **Impostazioni** , in **informazioni sul caso**, fare clic su **Seleziona**.

3. Fare clic su **Chiudi caso**.

   Il completamento del processo di chiusura potrebbe richiedere fino a 60 minuti.

## <a name="reopen-a-closed-case"></a>Riaprire un caso chiuso

Quando si riapre un caso di eDiscovery avanzato, tutte le esenzioni sul posto quando il caso è stato chiuso non verranno ripristinate automaticamente. Dopo la riapertura del caso, è necessario passare alla scheda **esenzioni** e abilitare le esenzioni precedenti. Per attivare un'esenzione, selezionarla per visualizzare la pagina del riquadro a comparsa e quindi impostare l'interruttore di **stato** **su**attivato.

Per riaprire un caso chiuso:

1. Nella pagina **Advanced eDiscovery** selezionare il caso che si desidera eliminare.

2. Nella scheda **Impostazioni** , in **informazioni sul caso**, fare clic su **Seleziona**.

3. Fare clic su **riapri caso**.

   Per il completamento del processo di riapertura, potrebbero essere necessari fino a 60 minuti.

## <a name="delete-a-case"></a>Eliminazione di un caso

È possibile eliminare i casi di eDiscovery avanzati sia attivi che chiusi. Quando si elimina un caso, vengono eliminati tutti i componenti associati al caso, ad esempio l'elenco dei depositari, le comunicazioni, le ricerche, i set di revisione e il processo di esportazione. La distinzione tra maiuscole e minuscole viene rimossa dall'elenco dei casi della pagina **Advanced eDiscovery** nel centro conformità di Microsoft 365. Non è possibile ripristinare o riaprire un caso eliminato.

> [!NOTE]
> Negli scenari di perdita dei dati, l'unico modo per rimuovere gli elementi in un set di revisione consiste nell'eliminare il caso Advanced eDiscovery. Gli altri metodi "Search and Purge" non rimuovono gli elementi da un set di revisione.

Prima di poter eliminare un caso (che sia attivo o chiuso), è necessario prima eliminare *tutti* gli appigli associati al caso. Che include l'eliminazione di esenzioni con stato **disattivata**.

Per eliminare le esenzioni associate a un caso:

1. Passare alla scheda **esenzioni** nel caso Advanced eDiscovery che si desidera eliminare.

2. Fare clic sul blocco che si desidera eliminare.

3. Nella pagina a comparsa fare clic su **Elimina blocco**.

Per eliminare un caso:

1. Nella pagina **Advanced eDiscovery** selezionare il caso che si desidera eliminare.

2. Nella scheda **Impostazioni** , in **informazioni sul caso**, fare clic su **Seleziona**.

3. Fare clic su **Delete case**.
