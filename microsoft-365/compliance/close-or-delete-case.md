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
description: Informazioni su cosa accade quando un'indagine o un caso legale supportato da un Advanced eDiscovery caso viene chiuso o eliminato.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: efbcbe34e6d7d8b564bcfa0cf9bbd8a1fbb59709
ms.sourcegitcommit: 6749455c52b0f98a92f6fffbc2bb86caf3538bd8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2021
ms.locfileid: "53194629"
---
# <a name="close-or-delete-an-advanced-ediscovery-case"></a>Chiudere o eliminare un Advanced eDiscovery caso

Una volta completata la causa legale o l'indagine supportata da un Advanced eDiscovery, è possibile chiudere o eliminare un caso. È anche possibile riaprire un caso chiuso.

## <a name="close-a-case"></a>Chiudere un caso

Ecco cosa accade quando si chiude un Advanced eDiscovery caso:

- Se il caso contiene posizioni di contenuti bloccate, i blocchi vengono disattivati. Dopo che il blocco è stato disattivato, un periodo di tolleranza di 30 giorni (denominato blocco di *ritardo)* viene applicato alle posizioni di contenuto che erano in attesa. Ciò consente di impedire l'eliminazione immediata del contenuto e offre agli amministratori la possibilità di cercare o ripristinare il contenuto che verrà eliminato definitivamente dopo la scadenza del periodo di attesa di ritardo. Per ulteriori informazioni, vedere [Rimozione di percorsi di contenuto da un blocco di eDiscovery.](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold)

- Con la chiusura di un caso vengono disattivati solo i blocchi specifici associati. Se altre esenzioni vengono posizionate in un percorso di contenuto (ad esempio un blocco per controversia legale, un blocco eDiscovery di base o un blocco di un caso Advanced eDiscovery diverso), tali blocchi verranno comunque mantenuti.

- Il caso è ancora elencato nella pagina eDiscovery nell'Centro conformità Microsoft 365. I dettagli, i blocchi, le ricerche e i membri di un caso chiuso vengono mantenuti.

- È possibile modificare un caso dopo che è stato chiuso. Ad esempio, è possibile aggiungere o rimuovere membri, creare ricerche, esportare risultati di ricerca e preparare i risultati della ricerca per l'analisi in Advanced eDiscovery. La differenza principale tra casi attivi e chiusi è che con la chiusura di un caso vengono disattivati i blocchi.

Per chiudere un caso:

1. Nella pagina **Advanced eDiscovery**, selezionare il caso che si desidera chiudere.

2. Nella scheda **Impostazioni** in **Informazioni sul caso**, fare clic su **Seleziona**.

   ![Accedere alla pagina del riquadro a comparsa delle informazioni sul caso in Advanced eDiscovery caso](..\media\AeDSelectCaseInformation.png) 

3. Nella parte inferiore della pagina del riquadro a comparsa **Informazioni** caso fare clic su **Azioni** e quindi su **Chiudi caso.**

   Per il completamento del processo di chiusura possono essere necessari fino a 60 minuti.

## <a name="reopen-a-closed-case"></a>Riaprire un caso chiuso

Quando si riapre un Advanced eDiscovery caso, le eventuali esenzioni in essere al momento della chiusura del caso non verranno ripristinate automaticamente. Dopo la riapertura del caso, è  necessario passare alla scheda Esenzioni e attivare le esenzioni precedenti. Per attivare un blocco, selezionarlo per visualizzare la pagina a comparsa, quindi impostare l'interruttore dello **Stato** su **On**.

Per riaprire un caso chiuso:

1. Nella pagina **Advanced eDiscovery**, selezionare il caso che si desidera riaprire.

2. Nella scheda **Impostazioni** in **Informazioni sul caso**, fare clic su **Seleziona**.

3. Nella parte inferiore della pagina del riquadro a comparsa **Informazioni** caso fare clic su **Azioni** e quindi su **Riapri caso.**

   Il completamento del processo di riapertura potrebbe richiedere fino a 60 minuti.

## <a name="delete-a-case"></a>Eliminare un caso

È possibile eliminare sia i casi attivi che Advanced eDiscovery chiusi. Quando si elimina un caso, tutti i componenti associati al caso, come l'elenco di responsabili, comunicazioni, ricerche, insiemi da rivedere e processi esportati vengono eliminati. Il caso viene rimosso dall'elenco dei casi nella pagina **Advanced eDiscovery** nella Centro conformità Microsoft 365. Non è possibile ripristinare o riaprire un caso eliminato.

> [!NOTE]
> Negli scenari di fuoriuscita di dati, l'unico modo per rimuovere gli elementi in un set di revisione è eliminare il Advanced eDiscovery caso. Altri metodi di "ricerca ed eliminazione" non rimuovono elementi da un set di recensioni.

Prima di poter eliminare un caso( attivo o chiuso),  è necessario eliminare tutte le esenzioni associate al caso. Ciò include l'eliminazione delle esenzioni con stato **Disattivato.**

Per eliminare i blocchi associati a un caso:

1. Passare alla **scheda** Esenzioni Advanced eDiscovery caso che si desidera eliminare.

2. Fare clic sull'esenzione che si desidera eliminare.

3. Nella pagina a comparsa fare clic su **Elimina blocco.**

Per eliminare un caso:

1. Nella pagina **Advanced eDiscovery**, selezionare il caso che si desidera eliminare.

2. Nella scheda **Impostazioni** in **Informazioni sul caso**, fare clic su **Seleziona**.

3. Nella parte inferiore della pagina del riquadro a comparsa **Informazioni** caso fare clic su **Azioni** e quindi su **Elimina caso.**

