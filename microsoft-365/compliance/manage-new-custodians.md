---
title: Gestire i depositari in un caso avanzato di eDiscovery
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
description: ''
ms.openlocfilehash: 17c77f14267f988a071e201733ae54ad9c438547
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37083791"
---
# <a name="manage-custodians-in-an-advanced-ediscovery-case"></a>Gestire i depositari in un caso avanzato di eDiscovery

La scheda depositari in Advanced eDiscovery contiene un elenco di tutti i depositari che sono stati aggiunti al caso. Dopo aver aggiunto i depositari a un caso, i dettagli relativi a ogni custode vengono raccolti automaticamente da Azure Active Directory e sono visualizzabili in Advanced eDiscovery.

![Gestire i depositari](media/CustodianDetails.PNG)

## <a name="view-custodian-details"></a>Visualizzare i dettagli del custode

Per visualizzare i dettagli relativi a un custode, fare clic sul custode dall'elenco nella scheda **depositari** . Viene visualizzata una pagina a comparsa che contiene le seguenti informazioni sul custode:

- Informazioni di contatto

  - **Nome** visualizzato-nome visualizzato nella rubrica del custode. Questo è in genere la combinazione del nome, dell'iniziale e del cognome del custode.
  
   - **Mail/SMTP** : l'indirizzo SMTP primario per il custode, ad esempio brianj@contoso.onmicrosoft.com. Si noti che anche il nome dell'entità utente (UPN) del custode è elencato.

  - **Title** -titolo del processo del custode.

  - **Department** -nome del reparto in cui lavora il custode.

  - **Manager** -responsabile del custode. Il responsabile designato riceverà eventuali comunicazioni di escalation per questo custode.
  
- Informazioni sulle posizioni

  - **City** : la città in cui si trova il custode.

  - **Stato** : lo stato o la provincia nell'indirizzo del custode.

  - **Paese/area** geografica-paese/area geografica in cui si trova il custode.

  - **Office** : la sede dell'ufficio nel luogo di lavoro del custode.

- Informazioni sul caso

  - **Stato blocco** -indica se il custode è stato messo in attesa. 

  - **Stato della comunicazione**: indica se il custode ha emesso un avviso di esenzione. Se al custode è stato emesso un avviso, viene **pubblicato**questo valore di questa proprietà. Se al custode non è stato emesso alcun avviso, lo stato non viene **pubblicato**. 

  - **Status** : lo stato del custode all'interno del caso. Lo stato **attivo** indica che il custode è parte del caso. Se un custode viene rilasciato da un caso, lo stato viene modificato in **rilasciato**. 

- Origini dati e informazioni sull'indicizzazione

    - **Origini dati** : consente di visualizzare il numero e il tipo di origini dati (cassette postali, siti e Team) associati al custode e fanno parte del caso.

    - **Tempo di aggiornamento dell'indice** : indica la data e l'ora in cui è stato attivato l'ultimo processo di indicizzazione avanzato. Questa proprietà indicherà anche quando il processo di indicizzazione avanzato è attualmente in corso.


## <a name="edit-a-custodian"></a>Modificare un custode

Man mano che il caso progredisce, è possibile rilevare che potrebbero essere presenti ulteriori origini dati rilevanti per un determinato custode & il caso. In altri scenari potrebbe essere necessario rimuovere determinate origini dati che sono state esaminate e ritenute irrilevanti.

Per aggiornare le origini dati associate a un custode:

1. Accedere a **eDiscovery > Advanced eDiscovery** e aprire il caso.
  
2. Fare clic sulla scheda **depositari** .
  
3. Selezionare un custode dall'elenco e fare clic su **modifica** nella pagina a comparsa.

    ![Modificare origini dati](media/EditCustodianDataSource.PNG)
  
4. Fare clic su scegliere la scheda **origini dati** per modificare le impostazioni per la cassetta postale di Exchange e l'account OneDrive della banca depositaria, fare clic su **Scegli origini dati**.
  
5. Fare clic sulla scheda **Seleziona origini dati aggiuntive** per aggiungere o rimuovere team, SharePoint o cassette postali di Exchange associati al custode. 

    Per ulteriori informazioni sulle origini dati associate a un custode, vedere "passaggio 3: associare altre origini dati a un custode" in [Aggiungi depositari a un caso](add-custodians-to-case.md#step-3-associate-additional-data-sources-to-a-custodian). 
  
6. Fare clic su **Place detentive** holds per abilitare o disabilitare il blocco per il custode.

## <a name="resolve-custodian-processing-errors"></a>Risolvere gli errori di elaborazione del custode

Nella maggior parte dei flussi di lavoro di eDiscovery per le indagini giudiziarie, viene cercato un sottoinsieme di dati di un custode dopo che il custode è stato aggiunto a un caso legale. A causa dei file di dimensioni molto grandi o di un possibile danneggiamento dei dati, alcuni elementi nelle origini dati associate a un custode possono essere parzialmente indicizzati. Utilizzando la funzionalità di [indicizzazione avanzata](indexing-custodian-data.md) in Advanced eDiscovery, è possibile correggere automaticamente gli elementi indicizzati in modo automatico riindicizzando questi elementi su richiesta.

Quando un custode viene aggiunto a un caso, i dati che si trovano nelle origini dati associate al custode vengono reindicizzati automaticamente (tramite il processo di indicizzazione avanzato). Questo significa che è possibile lasciare i dati sul posto invece di scaricarli e rimediarli e quindi cercarli in modalità non in linea. Tuttavia, durante il ciclo di vita di un caso legale, è possibile associare nuove origini dati a un custode. In questo caso, è necessario reindicizzare i dati del custode rieseguendo il processo di indicizzazione avanzato per correggere gli elementi parzialmente indicizzati e aggiornare l'indice per i dati del custode.

Per attivare il processo di reindicizzazione per risolvere gli elementi parzialmente indicizzati:

1. Accedere a **eDiscovery > Advanced eDiscovery** e aprire il caso.

2. Fare clic **sulla scheda depositari**e quindi selezionare un custode i cui dati devono essere reindicizzati. 

3. Nella pagina riquadro a comparsa fare clic su **Aggiorna indice**.

   Viene visualizzata una finestra di dialogo che indica che è stato creato il processo di indicizzazione.

La reindicizzazione dei dati del custode è un processo a esecuzione prolungata. il processo corrispondente creato è denominato **reindicizzazione dei dati del custode**. È possibile monitorare lo stato di avanzamento nella scheda **processi** o nella scheda **depositari** monitorando lo stato nella colonna **stato processo di indicizzazione** .

Per ulteriori informazioni, vedere:

- [Gestire gli errori di elaborazione](processing-data-for-case.md)

- [Gestire processi](managing-jobs-ediscovery20.md)

## <a name="release-a-custodian-from-a-case"></a>Rilasciare un custode da un caso

Un custode viene rilasciato in situazioni in cui un caso è chiuso, il custode non è più in dovere di preservare il contenuto di un caso o quando il custode è ritenuto non più pertinente al caso. 

Se si rilascia un custode dopo la pubblicazione di un avviso di esenzione, verrà inviato un avviso di rilascio al custode. Inoltre, tutte le esenzioni inserite nelle origini dati associate al custode vengono rimosse. Se il custode è stato collocato in una conservazione *invisibile all'utente*, in cui non sono state rilasciate notifiche per la conservazione legale, non verrà inviato un avviso di rilascio, ma verranno rimosse tutte le esenzioni eseguite su origini dati associate a tale custode.

Per rilasciare un custode: 

1. Accedere a **eDiscovery > Advanced eDiscovery** e aprire il caso.

2.  Passare alla scheda **depositari** .

3.  Fare clic sulla **scheda depositari**e quindi selezionare il custode che viene rilasciato dal caso.

4. Nella pagina riquadro a comparsa fare clic su **rilascia custode**.

   Viene visualizzata una pagina di avviso in cui viene spiegato che se un blocco è posizionato su un'origine dati associata al custode, il blocco verrà rimosso e qualsiasi altro blocco associato a un caso di eDiscovery avanzato verrà applicato. Che include altri tipi di funzionalità di conservazione e conservazione in Office 365, ad esempio i criteri di conservazione di Office 365.

5. Fare clic su **Sì** per confermare che si desidera rilasciare il custode. 

    Si noti che lo stato di questo utente nella scheda **depositari** è impostato su **rilasciato** e lo **stato di blocco** sulla pagina a comparsa viene modificato in **false**. 

> [!NOTE]
> Un custode potrebbe essere coinvolto contemporaneamente in numerosi casi legali. Quando un custode viene rilasciato da un caso, le esenzioni e le notifiche su altre questioni non verranno influenzate.

## <a name="bulk-edit-custodians"></a>Modifica in blocco di custodi

È possibile utilizzare l'editor di massa per modificare più depositari contemporaneamente. A tale scopo, è sufficiente selezionare due o più depositari nella scheda **depositari** per visualizzare l'editor di massa e quindi fare clic su una delle attività.

![Pagina a comparsa per modificare le impostazioni di più depositari](media/AeDBulkEditCustodians.png)