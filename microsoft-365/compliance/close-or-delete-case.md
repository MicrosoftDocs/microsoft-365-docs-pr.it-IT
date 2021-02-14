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
description: Informazioni su cosa accade quando un'indagine o un caso legale supportato da un caso di Advanced eDiscovery viene chiuso o eliminato.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ffdd93351325be0c4b5d6d8cdfb78e55b710c0be
ms.sourcegitcommit: 6746fae2f68400fd985711b1945b66766d2a59a4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/29/2020
ms.locfileid: "44419062"
---
# <a name="close-or-delete-an-advanced-ediscovery-case"></a>Chiudere o eliminare un caso di Advanced eDiscovery

Una volta completata la causa legale o l'indagine supportata da un caso di Advanced eDiscovery, è possibile chiudere o eliminare un caso. È inoltre possibile riaprire un caso chiuso.

## <a name="close-a-case"></a>Chiudere un caso

Ecco cosa accade quando si chiude un caso di Advanced eDiscovery:

- Se il caso contiene percorsi di contenuto in attesa, tali esenzioni verranno disattivate. Dopo che l'esenzione è stata disattivata, un periodo di tolleranza di 30 giorni (denominato blocco di *ritardo)* viene applicato ai percorsi di contenuto che erano in attesa. Ciò consente di evitare che il contenuto venga eliminato immediatamente e offre agli amministratori l'opportunità di cercare o recuperare contenuti che verranno eliminati definitivamente dopo la scadenza del periodo di attesa. Per ulteriori informazioni, vedere [Rimozione di percorsi di contenuto da un blocco di eDiscovery.](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold)

- La chiusura di un caso disattiva solo le esenzioni associate a tale caso. Se in un percorso di contenuto sono presenti altri blocchi , ad esempio un blocco per controversia legale, un blocco di eDiscovery di base o un blocco di un altro caso di Advanced eDiscovery, tali blocchi verranno mantenuti.

- Il caso è ancora elencato nella pagina eDiscovery nel Centro conformità Microsoft 365. I dettagli, le esenzioni, le ricerche e i membri di un caso chiuso vengono mantenuti.

- È possibile modificare un caso dopo che è stato chiuso. Ad esempio, è possibile aggiungere o rimuovere membri, creare ricerche, esportare i risultati della ricerca e preparare i risultati della ricerca per l'analisi in Advanced eDiscovery. La differenza principale tra casi attivi e chiusi consiste nel fatto che i blocchi vengono disattivati quando un caso viene chiuso.

Per chiudere un caso:

1. Nella pagina **Advanced eDiscovery** selezionare il caso che si desidera chiudere.

2. Nella scheda **Impostazioni,** in **Informazioni caso,** fare clic su **Seleziona.**

3. Fare **clic su Chiudi caso.**

   Il completamento del processo di chiusura potrebbe richiedere fino a 60 minuti.

## <a name="reopen-a-closed-case"></a>Riaprire un caso chiuso

Quando si riapre un caso di Advanced eDiscovery, tutti i blocchi che erano presenti al momento della chiusura del caso non verranno ripristinati automaticamente. Dopo la riapertura del caso, è  necessario passare alla scheda Esenzioni e attivare le esenzioni precedenti. Per attivare un'esenzione, selezionarla per visualizzare la pagina a comparsa e quindi impostare l'interruttore **Stato** su **Attivato.**

Per riaprire un caso chiuso:

1. Nella pagina **Advanced eDiscovery** selezionare il caso che si desidera riaprire.

2. Nella scheda **Impostazioni,** in **Informazioni caso,** fare clic su **Seleziona.**

3. Fare clic **su Riapri caso.**

   Il completamento del processo di riapertura potrebbe richiedere fino a 60 minuti.

## <a name="delete-a-case"></a>Eliminare un caso

È possibile eliminare sia i casi di Advanced eDiscovery attivi che chiusi. Quando si elimina un caso, vengono eliminati tutti i componenti associati al caso, ad esempio l'elenco dei responsabile, le comunicazioni, le ricerche, i set di revisioni e il processo di esportazione. Il caso viene rimosso dall'elenco dei casi nella pagina **Advanced eDiscovery** nel Centro conformità Microsoft 365. Non è possibile recuperare o riaprire un caso eliminato.

> [!NOTE]
> Negli scenari di perdita di dati, l'unico modo per rimuovere gli elementi in un insieme da rivedere è eliminare il caso di Advanced eDiscovery. Altri metodi di "ricerca ed eliminazione" non rimuovono elementi da un insieme da rivedere.

Prima di poter eliminare un caso (attivo o chiuso),  è necessario eliminare tutte le esenzioni associate al caso. Ciò include l'eliminazione delle esenzioni con stato **Disattivato.**

Per eliminare i blocchi associati a un caso:

1. Go the **Holds** tab in the Advanced eDiscovery case that you want to delete.

2. Fare clic sull'esenzione che si desidera eliminare.

3. Nella pagina a comparsa fare clic su **Elimina blocco.**

Per eliminare un caso:

1. Nella pagina **Advanced eDiscovery** selezionare il caso che si desidera eliminare.

2. Nella scheda **Impostazioni,** in **Informazioni caso,** fare clic su **Seleziona.**

3. Fare clic **su Elimina caso.**
