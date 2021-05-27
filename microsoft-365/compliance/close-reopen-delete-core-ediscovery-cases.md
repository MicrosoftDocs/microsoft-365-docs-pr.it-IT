---
title: Chiudere, riaprire ed eliminare i casi di eDiscovery di base
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: In questo articolo viene descritto come gestire i casi di eDiscovery di base. Ciò include la chiusura di un caso, la riapertura di un caso chiuso e l'eliminazione di un caso.
ms.openlocfilehash: d729c91d4e81ad12d0b4b16574aa4edad8e239a3
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2021
ms.locfileid: "52684100"
---
# <a name="close-reopen-and-delete-a-core-ediscovery-case"></a>Chiudere, riaprire ed eliminare un caso di Core eDiscovery

In questo articolo viene descritto come chiudere, riaprire ed eliminare i casi di eDiscovery di base in Microsoft 365.

## <a name="close-a-case"></a>Chiudere un caso

Una volta completata la causa legale o l'indagine supportata da un caso di Core eDiscovery, è possibile chiudere il caso. Ecco cosa accade quando si chiude un caso:
  
- Se il caso contiene blocchi di eDiscovery, verranno disattivati. Dopo che il blocco è stato disattivato, un periodo di tolleranza di 30 giorni (denominato blocco di *ritardo)* viene applicato alle posizioni di contenuto che erano in attesa. Ciò consente di evitare che il contenuto venga eliminato immediatamente e offre agli amministratori la possibilità di cercare e ripristinare il contenuto prima che venga eliminato definitivamente dopo la scadenza del periodo di attesa. Per ulteriori informazioni, vedere [Rimozione di percorsi di contenuto da un blocco di eDiscovery.](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold)

- Con la chiusura di un caso vengono disattivati solo i blocchi specifici associati. Se altre esenzioni vengono collocate in un percorso di contenuto (ad esempio un blocco per controversia legale, un criterio di conservazione o un blocco di un altro caso di eDiscovery di base), tali blocchi verranno comunque mantenuti.

- Il caso è ancora elencato nella pagina Core eDiscovery nel Centro Microsoft 365 conformità. I dettagli, i blocchi, le ricerche e i membri di un caso chiuso vengono mantenuti.

- È possibile modificare un caso dopo che è stato chiuso. Ad esempio, è possibile aggiungere o rimuovere membri, creare ricerche ed esportare risultati di ricerca. La differenza principale tra i casi attivi e chiusi è che i blocchi di eDiscovery vengono disattivati quando un caso viene chiuso.

Per chiudere un caso:
  
1. Nel Centro Microsoft 365 conformità fare clic su **eDiscovery** Core per visualizzare l'elenco dei casi di eDiscovery di base  >   nell'organizzazione.

2. Fare clic sul nome del caso che si desidera chiudere.

   ![Chiudere il caso nella home page del caso](../media/eDiscoveryCaseHomePage.png)

3. Nella home page, in **Stato,** fare clic **su Chiudi caso.**

    Viene visualizzato un avviso che indica che le esenzioni associate al caso verranno disattivate.

4. Fare **clic su Sì** per chiudere il caso.

    Lo stato nella home page del caso viene modificato da **Attivo** a **Chiuso.**

5. Nella pagina **Core eDiscovery** fare clic su **Aggiorna** per aggiornare lo stato del caso chiuso. Per il completamento del processo di chiusura possono essere necessari fino a 60 minuti.

    Al termine del processo, lo stato del caso viene modificato in **Chiuso** nella **pagina Core eDiscovery.**

## <a name="reopen-a-closed-case"></a>Riaprire un caso chiuso

Quando si riapre un caso, le eventuali eDiscovery conservate al momento della chiusura del caso non verranno ripristinate automaticamente. Dopo la riapertura del caso, è necessario passare alla pagina **Esenzioni** e attivare le esenzioni precedenti. Per attivare un blocco, selezionarlo per visualizzare la pagina a comparsa, quindi impostare l'interruttore dello **Stato** su **On**.
  
1. Nel Centro Microsoft 365 conformità fare clic su **eDiscovery** Core per visualizzare l'elenco dei casi di eDiscovery di base  >   nell'organizzazione.

2. Fare clic sul nome del caso che si desidera riaprire.

   ![Riaprire un caso chiuso](../media/eDiscoveryCaseHomePageReopen.png)

3. Nella home page, in **Stato, fare** clic su **Riapri caso.**

    Viene visualizzato un avviso che indica che le esenzioni associate al caso al momento della chiusura non verranno attivate automaticamente.

4. Fare **clic su Sì** per riaprire il caso.

    Lo stato nella pagina a comparsa della home page del caso viene modificato da **Chiuso** ad **Attivo.**

5. Nella pagina **Core eDiscovery** fare clic su **Aggiorna** per aggiornare lo stato del caso riaperto. Il completamento del processo di riapertura potrebbe richiedere fino a 60 minuti. 

    Al termine del processo, lo stato del caso viene modificato in **Attivo** nella **pagina Core eDiscovery.**

6. (Facoltativo) Per attivare eventuali esenzioni associate al  caso riaperto, passare alla scheda Esenzioni, selezionare un'esenzione e quindi selezionare la casella di controllo in **Stato** nella pagina del riquadro a comparsa di blocco.
  
## <a name="delete-a-case"></a>Eliminare un caso

È inoltre possibile eliminare i casi di eDiscovery core attivi e chiusi. Quando si elimina un caso, tutte le ricerche e le esportazioni nel caso vengono eliminate e il caso viene rimosso dall'elenco dei casi nella pagina **eDiscovery** di base nel Centro conformità Microsoft 365. Non è possibile riaprire un caso eliminato.

Prima di poter eliminare un caso ,sia esso attivo  o chiuso, è necessario eliminare tutte le eDiscovery associate al caso. Ciò include l'eliminazione delle esenzioni con stato **Disattivato.** 

Per eliminare un blocco di eDiscovery:

1. Passare alla **scheda Esenzioni** nel caso in cui si desidera eliminare.

2. Selezionare l'esenzione che si desidera eliminare.

3. Nella pagina a comparsa fare clic su **Elimina.**

      ![Eliminare un blocco di eDiscovery](../media/DeleteeDiscoveryHold.png)

Per eliminare un caso:

1. Nel Centro Microsoft 365 conformità fare clic su **eDiscovery** Core per visualizzare l'elenco dei casi di eDiscovery di base  >   nell'organizzazione.

2. Fare clic sul nome del caso che si desidera eliminare.

3. Nella home page del caso, in **Stato,** fare clic **su Elimina caso.**

      ![Eliminare un caso](../media/eDiscoveryCaseHomePageDelete.png)

Se il caso che si sta tentando di eliminare contiene ancora blocchi di eDiscovery, verrà visualizzato un messaggio di errore. Sarà necessario eliminare tutte le esenzioni associate al caso e quindi riprovare a eliminare il caso.
