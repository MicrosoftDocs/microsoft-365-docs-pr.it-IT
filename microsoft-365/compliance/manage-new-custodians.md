---
title: Gestire i custodi in un Advanced eDiscovery caso
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
description: Informazioni su come visualizzare i dettagli, modificare e modificare in blocco l'elenco dei Advanced eDiscovery caso.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a1e9e9d481073c8bb2827d5d65537dbf2b63ef1f
ms.sourcegitcommit: 555b200b618085706dabf8648d27fb6d6427cfce
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/30/2020
ms.locfileid: "49739869"
---
# <a name="manage-custodians-in-an-advanced-ediscovery-case"></a>Gestire i custodi in un Advanced eDiscovery caso

La pagina Custodi della **scheda Origini** di un caso Advanced eDiscovery contiene un elenco di tutti i custodi che sono stati aggiunti al caso. Dopo aver aggiunto i custodi a un caso, i dettagli su ogni responsabile vengono raccolti automaticamente da Azure Active Directory e sono visualizzabili in Advanced eDiscovery.

![Gestire i custodi](../media/CustodianDetails.PNG)

## <a name="view-custodian-details"></a>Visualizzare i dettagli del responsabile

Per visualizzare i dettagli su un responsabile, fare clic sul responsabile nell'elenco nella **scheda Custodi.** Viene visualizzata una pagina a comparsa contenente le informazioni seguenti sul responsabile:

- Informazioni contatto

  - **Nome visualizzato** - Nome visualizzato nella rubrica del responsabile. Questa è in genere la combinazione del nome, dell'iniziale e del cognome del responsabile.
  
   - **Posta/SMTP** - Indirizzo SMTP primario per il responsabile, ad esempio, brianj@contoso.onmicrosoft.com. Viene inoltre elencato il nome dell'entità utente (UPN) del responsabile.

  - **Title:** la posizione del responsabile.

  - **Department** - Nome del reparto in cui lavora il responsabile.

  - **Manager** : responsabile del responsabile del responsabile. Il manager designato riceverà tutte le comunicazioni di escalation per questo responsabile.
  
- Informazioni sulle posizioni

  - **City** - Città in cui si trova il responsabile.

  - **State** - Stato o provincia nell'indirizzo del responsabile.

  - **Country/Region** - Paese/area geografica in cui si trova il responsabile.

  - **Office** - Posizione dell'ufficio nel luogo di lavoro del responsabile.

- Informazioni sul caso

  - **Stato blocco** - Indica se il responsabile è stato messo in attesa. 

  - **Stato comunicazione**: Indica se al responsabile della conservazione è stato emesso un avviso di blocco. Se al responsabile è stato emesso un avviso, il valore di questa proprietà è **Published.** Se al responsabile non è stato emesso un avviso, lo stato è **Non pubblicato.** 

  - **Status** : stato del responsabile del caso. Lo stato **Attivo** indica che il responsabile fa parte del caso. Se un responsabile viene rilasciato da un caso, lo stato viene modificato in **Rilasciato**. 

- Origini dati e informazioni di indicizzazione

    - **Origini dati:** mostra il numero e il tipo di origini dati (cassette postali, siti e Teams) associate al responsabile del caso e che fanno parte del caso.

    - **Ora aggiornamento indice** - Indica l'ora e la data dell'ultimo trigger del processo di indicizzazione avanzato. Questa proprietà indicherà anche quando è in corso il processo di indicizzazione avanzato.


## <a name="edit-a-custodian"></a>Modificare un responsabile

Con l'avanzamento del caso, potresti scoprire che potrebbero essere presenti origini dati aggiuntive pertinenti a un responsabile specifico & caso. In altri scenari, è possibile rimuovere determinate origini dati che sono state esaminate e ritenute non rilevanti.

Per aggiornare le origini dati associate a un responsabile:

1. Passare a **eDiscovery > Advanced eDiscovery** aprire il caso.
  
2. Fare clic **sulla scheda** Origini.
  
3. Nella pagina **Custodi** selezionare un responsabile nell'elenco e fare clic su **Modifica** nella pagina a comparsa.

    ![Modifica origini dati](../media/EditCustodianDataSource.PNG)
  
4. Fare **clic sulla scheda Scegli** origini dati per modificare le impostazioni per la cassetta postale Exchange e l'account OneDrive, fare clic su Scegli origini **dati.**
  
5. Fare clic **sulla scheda Seleziona** origini dati aggiuntive per aggiungere o rimuovere Teams, SharePoint o Exchange cassette postali associate al responsabile. 

    Per ulteriori informazioni sulle origini dati associate a un responsabile, vedere [Add custodians to a case.](add-custodians-to-case.md) 
  
6. Fare **clic su Inserisci blocchi di** custodia per abilitare o disabilitare il blocco per il responsabile.

## <a name="re-index-custodian-data"></a>Re-index custodian data

Nella maggior parte dei flussi di lavoro di eDiscovery per indagini legali, viene ricercato un sottoinsieme dei dati di un responsabile dopo l'aggiunta del responsabile a una causa legale. A causa di file di dimensioni molto grandi o di possibili danneggiamenti dei dati, alcuni elementi nelle origini dati associate a un responsabile possono essere parzialmente indicizzati. Utilizzando la [funzionalità di indicizzazione](indexing-custodian-data.md) avanzata nell'Advanced eDiscovery, la maggior parte degli elementi parzialmente indicizzati può essere automaticamente corretti tramite la nuova indicizzazione di questi elementi su richiesta.

Quando un responsabile viene aggiunto a un caso, i dati che si trovano nelle origini dati associate al responsabile vengono automaticamente indicizzati (tramite il processo di indicizzazione avanzato). Ciò significa che puoi lasciare i dati sul posto invece di doverli scaricare e correggere e quindi cercarli offline. Tuttavia, durante il ciclo di vita di un caso legale, le nuove origini dati potrebbero essere associate a un responsabile. In questo caso, è possibile indicizzare nuovamente i dati del responsabile eseguendo di nuovo il processo di indicizzazione avanzato per correggere eventuali elementi parzialmente indicizzati e aggiornare l'indice per i dati del responsabile.

Per attivare il processo di re-indicizzazione per risolvere gli elementi parzialmente indicizzati:

1. Passare a **eDiscovery > Advanced eDiscovery** aprire il caso.

2. Fare clic **sulla scheda** Origini.

3. Nella pagina **Custodi** selezionare un responsabile i cui dati devono essere reindicizzati.

4. Nella pagina a comparsa fare clic su **Aggiorna indice.**

   Viene visualizzata una finestra di dialogo che conferma la creazione del processo di indicizzazione.

La re-indicizzazione dei dati di custodia è un processo a esecuzione lunga. il processo corrispondente creato è denominato **Re-indexing custodian data**. È possibile tenere traccia dello stato nella **scheda Processi** o nella scheda **Custodi** monitorando lo stato nella **colonna Stato processo di** indicizzazione.

Per altre informazioni, vedere:

- [Gestire gli errori di elaborazione](processing-data-for-case.md)

- [Gestire processi](managing-jobs-ediscovery20.md)

## <a name="release-a-custodian-from-a-case"></a>Rilasciare un responsabile da un caso

Un depositario viene rilasciato in situazioni in cui un caso è chiuso, il depositario non è più obbligato a conservare il contenuto per un caso o quando il depositario è ritenuto non più rilevante per il caso. 

Se rilasci un responsabile dopo la pubblicazione di un avviso di blocco, al responsabile verrà inviata una notifica di rilascio. Inoltre, vengono rimosse le eventuali esenzioni inserite nelle origini dati associate al responsabile. Se il responsabile è stato sottoposto *a* un blocco invisibile all'utente , in cui non sono state emesse notifiche di blocco legale, non verrà inviata una notifica di rilascio, ma le eventuali conservazioni nelle origini dati associate a tale responsabile verranno rimosse.

Per rilasciare un responsabile: 

1. Passare a **eDiscovery > Advanced eDiscovery** aprire il caso.

2. Fare clic **sulla scheda** Origini.

3. Nella pagina **Custodi,** quindi selezionare il responsabile che verrà rilasciato dal caso.

4. Nella pagina a comparsa fare clic su **Rilascia responsabile.**

   Viene visualizzata una pagina di avviso in cui viene spiegato che, se viene applicata un'esenzione a un'origine dati associata al responsabile, l'esenzione verrà rimossa e che qualsiasi altro blocco associato a un caso di Advanced eDiscovery diverso verrà comunque applicato. Che include altri tipi di funzionalità di conservazione e conservazione (ad esempio un criterio Microsoft 365 conservazione).

5. Fare **clic su** Sì per confermare che si desidera rilasciare il responsabile. 

    Lo stato dell'utente nella scheda **Custodi** è  impostato su Rilasciato e lo stato di blocco nella pagina a comparsa viene impostato su **False.**  

> [!NOTE]
> Un responsabile potrebbe essere coinvolto contemporaneamente in diversi casi legali. Quando un responsabile viene rilasciato da un caso, le esenzioni e le notifiche su altre questioni non saranno influenzate.

## <a name="bulk-edit-custodians"></a>Responsabile della modifica in blocco

Puoi usare l'editor in blocco per modificare più custodi contemporaneamente. A tale scopo, è sufficiente selezionare  due o più custodi nella scheda Custodi per visualizzare l'editor in blocco e quindi fare clic su una delle attività.

![Pagina a comparsa per modificare le impostazioni di più custodi](../media/AeDBulkEditCustodians.png)
