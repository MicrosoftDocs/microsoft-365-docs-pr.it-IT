---
title: Eseguire il modulo di processo e caricare i dati in Office 365 Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: c87bb0e5-301c-4d1d-958e-aabeb7990f44
description: 'Informazioni su come utilizzare il Centro sicurezza &amp; e conformità di Office 365 per accedere a Office 365 Advanced eDiscovery ed eseguire il modulo di processo per un caso.  '
ms.openlocfilehash: 60da3fd66ce33443e991ece2dc756c7d1ab0d14a
ms.sourcegitcommit: e741930c41abcde61add22d4b773dbf171ed72ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/07/2020
ms.locfileid: "42557826"
---
# <a name="run-the-process-module-and-load-data-in-advanced-ediscovery-classic"></a>Eseguire il modulo di processo e caricare i dati in Advanced eDiscovery (Classic)

> [!NOTE]
> Per usare Advanced eDiscovery è necessario avere Office 365 E3 con il componente aggiuntivo Advanced Compliance o un abbonamento E5 dell'organizzazione. Se non si ha questo piano e si desidera provare Advanced eDiscovery, è possibile [richiedere una valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
In questa sezione viene descritta la funzionalità del modulo di elaborazione di eDiscovery avanzato. 
  
Oltre ai dati dei file, i metadati, ad esempio il tipo di file, l'estensione, la posizione o il percorso, la data e l'ora di creazione, l'autore, il custode e l'oggetto possono essere caricati in Advanced eDiscovery e salvati per ogni caso. Alcuni metadati vengono calcolati da Advanced eDiscovery, ad esempio quando vengono caricati file nativi. 
  
Advanced eDiscovery fornisce i valori dei metadati di sistema, ad esempio raggruppamenti quasi duplicati o punteggi di rilevanza. Gli altri metadati, ad esempio le annotazioni di file, possono essere aggiunti dall'amministratore. 
  
## <a name="running-process"></a>Processo in esecuzione

> [!NOTE]
> I numeri di batch vengono assegnati a un file durante il processo per consentire la tracciabilità dei file. Il numero di batch consente inoltre l'identificazione dei batch di processo per le opzioni di rielaborazione. Sono disponibili filtri aggiuntivi per il filtro in base al numero di batch e alle sessioni. 
  
Eseguire la procedura seguente per eseguire il processo.
  
1. [Aprire il Centro sicurezza &amp; e conformità di Office 365](go-to-the-securitycompliance-center.md) . 
    
2. Andare a **Search &amp; Investigation** \> **eDiscovery** e quindi fare clic su **go to Advanced eDiscovery**.
    
3. In Advanced eDiscovery selezionare il caso appropriato nella pagina **casi** visualizzati e fare clic su **Vai a maiuscole/minuscole**.
    
4. In **preparare** \> l' **installazione**del **processo** \> selezionare un contenitore dall'elenco dei contenitori disponibili.
    
    ![Fare clic su processo per aggiungere i risultati della ricerca al caso](../media/50bdc55c-d378-4881-b302-31ef785fa359.png)
  
5. Fare clic su **Impostazioni avanzate...** se si desidera aggiungere il contenitore come file di seeding o come file con tag preselezionati. 
    
    Utilizzo dei file di seeding per accelerare la formazione di problemi con una ricchezza limitata (in genere 2% o meno). Per i file di seeding, è consigliabile selezionare una serie di file rilevanti e elaborare circa 20-50 Seeds per ogni problema (troppi file di sementi possono alterare i risultati della pertinenza). I file di seeding devono essere esaminati dalla stessa persona che dovrà addestrare il problema.
    
    Utilizzare i file con tag preselezionati per automatizzare la formazione sulla pertinenza. È necessario contrassegnare almeno 1.500 file e mantenere la proporzione dei file rilevanti per i non rilevanti come nell'insieme aggiunto a pertinenza. Questi file devono essere contrassegnati manualmente e devono essere sicuri della qualità del tagging.
    
    ![Schermata della pagina Impostazioni avanzate per l'elaborazione dei file batch](../media/3c25cb78-4484-41e5-bd34-3753c7ab6cf2.jpg)
  
  - Nella sezione **Seed** : 
    
    Scegliere **Contrassegna come file di seeding** per contrassegnare il contenitore come file di seeding. È inoltre necessario scegliere di assegnarli per ogni problema dall'elenco a discesa **per i problemi** . Scegliere **rilevanti** o **non rilevanti** dall'elenco a discesa dei **tag** . 
    
    > [!NOTE]
    > Dopo aver impostato i file come **Seed**, non è possibile contrassegnarli come **preselezionati**. 
  
  - Nella sezione **file con tag preselezionati** : 
    
    Scegliere **Contrassegna come file con tag** preselezionati per contrassegnare il contenitore come file con tag preselezionati. È inoltre necessario assegnarle per ogni problema dall'elenco **a discesa per i problemi** . Scegliere **rilevanti** o **non rilevanti** dall'elenco a discesa dei **tag** . 
    
    > [!NOTE]
    > Dopo aver impostato i file come **precontrassegnati**, non è possibile contrassegnarli come **Seed**. 
  
  - Nella sezione **tagging messaggio di posta elettronica** . impostare la parte di un messaggio di posta elettronica elaborata da contrassegnare come Seed o con tag preimpostati. 
    
6. Per iniziare, fare clic su **elabora**. Al termine, vengono visualizzati i risultati del processo.
    
7. Optional Se è necessario assegnare origini dati a un determinato custode, è possibile aggiungere e modificare i nomi dei depositari nei **depositari** \> **gestiscono** **e assegnano**i depositari nei **depositari** \> . 
    
Se si aggiunge il caso, è possibile procedere di nuovo.
  
## <a name="see-also"></a>Vedere anche

[Advanced eDiscovery (classica)](office-365-advanced-ediscovery.md)
  
[Visualizzazione dei risultati del modulo di elaborazione](view-process-module-results-in-advanced-ediscovery.md)

