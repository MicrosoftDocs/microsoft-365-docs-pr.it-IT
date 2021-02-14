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
ms.openlocfilehash: 17b243a7207fd6927188b42e585101ff1d258b76
ms.sourcegitcommit: 5c96d06496d40d2523edbea336f7355c3c77cc80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/29/2020
ms.locfileid: "44412795"
---
# <a name="close-reopen-and-delete-a-core-ediscovery-case"></a>Chiudere, riaprire ed eliminare un caso di Core eDiscovery

Questo articolo descrive come chiudere, riaprire ed eliminare i casi di eDiscovery di base in Microsoft 365.

## <a name="close-a-case"></a>Chiudere un caso

Una volta completata la causa legale o l'indagine supportata da un caso di Core eDiscovery, è possibile chiudere il caso. Ecco cosa accade quando si chiude un caso:
  
- Se il caso contiene percorsi di contenuto per il blocco di eDiscovery, tali blocchi verranno disattivati. Una volta disattivata l'esenzione, viene applicato un periodo di tolleranza di 30 giorni (denominato blocco di *ritardo)* ai percorsi di contenuto che erano in attesa. Ciò consente di impedire l'eliminazione immediata del contenuto e offre agli amministratori la possibilità di cercare e ripristinare il contenuto prima che possa essere eliminato definitivamente dopo la scadenza del periodo di blocco. Per ulteriori informazioni, vedere [Rimozione di percorsi di contenuto da un blocco di eDiscovery.](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold)

- La chiusura di un caso disattiva solo le esenzioni associate a tale caso. Se altri blocchi vengono inseriti in un percorso di contenuto (ad esempio un blocco per controversia legale, un criterio di conservazione o un blocco di un altro caso di Core eDiscovery), tali blocchi verranno mantenuti.

- Il caso è ancora elencato nella pagina Core eDiscovery nel Centro conformità Microsoft 365. I dettagli, le esenzioni, le ricerche e i membri di un caso chiuso vengono mantenuti.

- È possibile modificare un caso dopo che è stato chiuso. Ad esempio, è possibile aggiungere o rimuovere membri, creare ricerche ed esportare i risultati della ricerca. La differenza principale tra casi attivi e chiusi è che i blocchi di eDiscovery vengono disattivati quando un caso viene chiuso.

Per chiudere un caso:
  
1. Nel Centro conformità Microsoft 365 fare clic su **eDiscovery** Core per visualizzare l'elenco  >   dei casi di eDiscovery di base nell'organizzazione.

2. Fare clic sul nome del caso che si desidera chiudere.

    Viene **visualizzata la pagina Gestisci** questo caso a comparsa.

3. In **Gestisci stato caso fare** clic su Chiudi **caso.**

    Viene visualizzato un avviso che indica che le esenzioni associate al caso verranno disattivate.

4. Fare **clic su Sì** per chiudere il caso.

    Lo stato nella pagina **Gestisci questo caso** a comparsa viene modificato da **Attivo** a **Chiusura.**

5. Chiudere la **pagina Gestisci questo caso.**

6. Nella pagina **Core eDiscovery** fare clic su **Aggiorna** per aggiornare lo stato del caso chiuso. Il completamento del processo di chiusura potrebbe richiedere fino a 60 minuti.

    Al termine del processo, lo stato del caso viene modificato in **Chiuso** nella **pagina Core eDiscovery.** Fare di nuovo clic sul  nome del caso per visualizzare la pagina Gestisci questo caso a comparsa, che contiene informazioni sulla chiusura del caso e sull'utente che lo ha chiuso.

## <a name="reopen-a-closed-case"></a>Riaprire un caso chiuso

Quando si riapre un caso, tutti i blocchi di eDiscovery presenti al momento della chiusura del caso non verranno ripristinati automaticamente. Dopo la riapertura del caso, sarà necessario passare alla pagina **Esenzioni** e attivare le esenzioni precedenti. Per attivare un'esenzione, selezionarla per visualizzare la pagina a comparsa e quindi impostare l'interruttore **Stato** su **Attivato.**
  
1. Nel Centro conformità Microsoft 365 fare clic su **eDiscovery** Core per visualizzare l'elenco  >   dei casi di eDiscovery di base nell'organizzazione.

2. Fare clic sul nome del caso che si desidera riaprire.

    Viene **visualizzata la pagina Gestisci** questo caso a comparsa. 

3. In **Gestisci stato caso fare** clic su **Riapri caso.**

    Viene visualizzato un avviso che indica che le esenzioni associate al caso al momento della chiusura non verranno attivate automaticamente.

4. Fare **clic su Sì** per riaprire il caso.

    Lo stato nella pagina **Gestisci questo caso** a comparsa viene modificato da **Chiuso** ad **Attivo.**

5. Chiudere la **pagina Gestisci questo caso.** 

6. Nella pagina **Core eDiscovery** fare clic su **Aggiorna** per aggiornare lo stato del caso riaperto. Il completamento del processo di riapertura potrebbe richiedere fino a 60 minuti. 

    Al termine del processo, lo stato del caso viene modificato in **Attivo** nella **pagina Core eDiscovery.** 
  
## <a name="delete-a-case"></a>Eliminare un caso

È inoltre possibile eliminare i casi di eDiscovery core attivi e chiusi. Quando si elimina un caso, tutte le ricerche e le esportazioni nel caso vengono eliminate e il caso viene rimosso dall'elenco dei casi nella pagina **Core eDiscovery** nel Centro conformità Microsoft 365. Non è possibile riaprire un caso eliminato.

Prima di poter eliminare un caso (che sia attivo o chiuso), è necessario eliminare tutti i blocchi *di* eDiscovery associati al caso. Ciò include l'eliminazione delle esenzioni con stato **Disattivato.** 

Per eliminare un blocco di eDiscovery:

1. Passare alla **scheda Esenzioni** nel caso in cui si desidera eliminare.

2. Fare clic sull'esenzione che si desidera eliminare.

3. Nella pagina a comparsa fare clic su **Elimina blocco.**

Per eliminare un caso:

1. Nel Centro conformità Microsoft 365 fare clic su **eDiscovery** Core per visualizzare l'elenco  >   dei casi di eDiscovery di base nell'organizzazione.

2. Fare clic sul nome del caso che si desidera eliminare.

3. In **Gestisci stato caso nella** pagina a comparsa fare clic su Elimina **caso.**

Se il caso che si sta tentando di eliminare contiene ancora blocchi di eDiscovery, verrà visualizzato un messaggio di errore. Sarà necessario eliminare tutte le esenzioni associate al caso e quindi riprovare a eliminare il caso.
