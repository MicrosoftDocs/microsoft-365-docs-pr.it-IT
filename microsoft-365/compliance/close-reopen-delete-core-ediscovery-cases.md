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
description: In questo articolo viene descritto come gestire i casi di eDiscovery di base. Questo include la chiusura di un caso, la riapertura di un caso chiuso e l'eliminazione di un caso.
ms.openlocfilehash: 45282486c2c3b1d00b99a1cda5968b3bb042f6c2
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208418"
---
# <a name="close-reopen-and-delete-a-core-ediscovery-case"></a>Chiudere, riaprire ed eliminare un caso di eDiscovery di base

In questo articolo viene descritto come chiudere, riaprire ed eliminare i casi di eDiscovery di base in Microsoft 365.

## <a name="close-a-case"></a>Chiudere un caso

Quando la causa legale o l'indagine supportata da un caso di eDiscovery di base è stata completata, è possibile chiudere il caso. Ecco cosa succede quando si chiude un caso:
  
- Se il caso contiene posizioni di contenuto in eDiscovery Hold, tali esenzioni verranno disattivate. Potrebbe risultare che il contenuto venga eliminato o rimosso definitivamente, dall'utente o da un processo automatizzato, ad esempio un criterio di eliminazione.

- La chiusura di un caso disattiva solo le esenzioni associate a quel caso. Se altre esenzioni vengono inserite in una posizione di contenuto, ad esempio un blocco per controversia legale, un criterio di conservazione o un'esenzione da un caso di eDiscovery di base diverso, tali esenzioni verranno comunque mantenute.

- Il caso è ancora elencato nella pagina principale di eDiscovery nel centro conformità di Microsoft 365. Vengono mantenuti i dettagli, le esenzioni, le ricerche e i membri di un caso chiuso.

- È possibile modificare un caso dopo che è stato chiuso. Ad esempio, è possibile aggiungere o rimuovere membri, creare ricerche ed esportare i risultati della ricerca. La differenza principale tra casi attivi e chiusi è che le esenzioni di eDiscovery sono disattivate quando un caso è chiuso.

Per chiudere un caso:
  
1. Nel centro conformità di Microsoft 365, fare clic su **eDiscovery**  >  **Core** per visualizzare l'elenco dei casi di eDiscovery di base nell'organizzazione.

2. Fare clic sul nome del caso che si desidera chiudere.

    Viene visualizzata la pagina Gestisci il riquadro a comparsa di **questo caso** .

3. In **Manage case status**fare clic su **Chiudi caso**.

    Viene visualizzato un messaggio di avviso in cui viene indicato che le esenzioni associate al caso saranno disattivate.

4. Fare clic su **Sì** per chiudere il caso.

    Lo stato della pagina **Gestisci** il riquadro a comparsa di questo caso è stato modificato da **attivo** a **chiusura**.

5. Chiudere la pagina **Gestisci questo caso** .

6. Nella pagina **Core eDiscovery** , fare clic su **Aggiorna** per aggiornare lo stato del caso chiuso. Il completamento del processo di chiusura potrebbe richiedere fino a 60 minuti.

    Al termine del processo, lo stato della distinzione tra maiuscole e minuscole viene cambiato in **Closed** nella pagina di **eDiscovery di base** . Fare di nuovo clic sul nome del caso per visualizzare la pagina Gestisci il riquadro a comparsa di **questo caso** , che contiene informazioni su quando il caso è stato chiuso e chi l'ha chiusa.

## <a name="reopen-a-closed-case"></a>Riaprire un caso chiuso

Quando si riapre un caso, tutte le esenzioni di eDiscovery che erano sul posto quando il caso è stato chiuso non verranno ripristinate automaticamente. Dopo la riapertura del caso, è necessario andare alla pagina **esenzioni** e abilitare le esenzioni precedenti. Per attivare un'esenzione, selezionarla per visualizzare la pagina del riquadro a comparsa e quindi impostare l'interruttore di **stato** **su**attivato.
  
1. Nel centro conformità di Microsoft 365, fare clic su **eDiscovery**  >  **Core** per visualizzare l'elenco dei casi di eDiscovery di base nell'organizzazione.

2. Fare clic sul nome del caso che si desidera riaprire.

    Viene visualizzata la pagina Gestisci il riquadro a comparsa di **questo caso** . 

3. In **Manage case status**fare clic su **riapri caso**.

    Viene visualizzato un messaggio di avviso in cui viene indicato che le esenzioni associate al caso in cui è stata chiusa non verranno attivate automaticamente.

4. Fare clic su **Sì** per riaprire il caso.

    Lo stato della pagina **Gestisci** il riquadro a comparsa di questo caso è stato modificato da **chiuso** a **attivo**.

5. Chiudere la pagina **Gestisci questo caso** . 

6. Nella pagina **eDiscovery di base** fare clic su **Aggiorna** per aggiornare lo stato del caso riaperto. Per il completamento del processo di riapertura, potrebbero essere necessari fino a 60 minuti. 

    Al termine del processo, lo stato del caso viene modificato in **attivo** nella pagina di **eDiscovery di base** . 
  
## <a name="delete-a-case"></a>Eliminazione di un caso

È inoltre possibile eliminare i casi di eDiscovery core attivi e chiusi. Quando si elimina un caso, tutte le ricerche e le esportazioni nel caso vengono eliminate e il caso viene rimosso dall'elenco dei casi nella pagina di **eDiscovery di base** nel centro conformità di Microsoft 365. Non è possibile riaprire un caso eliminato.

Prima di eliminare un caso (che sia attivo o chiuso), è necessario innanzitutto eliminare *tutte le* esenzioni di eDiscovery associate al caso. Che include l'eliminazione di esenzioni con stato **disattivata**. 

Per eliminare un blocco di eDiscovery:

1. Andare alla scheda **esenzioni** nel caso in cui si desidera eliminare.

2. Fare clic sul blocco che si desidera eliminare.

3. Nella pagina a comparsa fare clic su **Elimina blocco**.

Per eliminare un caso:

1. Nel centro conformità di Microsoft 365, fare clic su **eDiscovery**  >  **Core** per visualizzare l'elenco dei casi di eDiscovery di base nell'organizzazione.

2. Fare clic sul nome del caso che si desidera eliminare.

3. In **Gestione stato caso** nella pagina riquadro a comparsa fare clic su **Elimina caso**.

Se il caso che si sta tentando di eliminare contiene ancora eDiscovery, verrà visualizzato un messaggio di errore. Sarà necessario eliminare tutte le esenzioni associate al caso e quindi riprovare per eliminare il caso.
