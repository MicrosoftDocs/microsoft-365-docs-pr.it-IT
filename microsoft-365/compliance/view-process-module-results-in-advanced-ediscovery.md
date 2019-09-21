---
title: Visualizza i risultati del modulo di processo in Office 365 Advanced eDiscovery
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: c6f016cb-409f-4ae9-911c-1395cf0c86ea
description: 'Informazioni su come trovare i risultati di un modulo di processo eseguito in Office 365 Advanced eDiscovery, incluso lo stato delle attività e il riepilogo dei processi.  '
ms.openlocfilehash: 4bbdbf68f71e3459ff2ddcd8ba3fb33e52f16825
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37084285"
---
# <a name="view-process-module-results-in-office-365-advanced-ediscovery"></a>Visualizza i risultati del modulo di processo in Office 365 Advanced eDiscovery

Dopo l'avvio del **processo** di **preparazione** \> , è possibile visualizzare lo stato e i risultati. 
  
> [!NOTE]
> Per usare Advanced eDiscovery è necessario avere Office 365 E3 con il componente aggiuntivo Advanced Compliance o un abbonamento E5 dell'organizzazione. Se non si ha questo piano e si desidera provare Advanced eDiscovery, è possibile [richiedere una valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
## <a name="process-task-status"></a>Stato attività processo

Nei **risultati**del **processo** \> di **preparazione** \> la pagina mostra lo stato corrente (se il processo è in esecuzione) oppure lo stato dell'ultimo processo di elaborazione, come illustrato nell'esempio seguente.
  
![Stato delle attività del modulo processo](media/9430f9e7-a4dd-47c7-ac2e-2c6a60fc948b.png)
  
Le attività visualizzate possono variare a seconda delle opzioni di elaborazione selezionate. 
  
- **Inventario**: Advanced eDiscovery scorre tutti i file selezionati per il processo ed esegue la raccolta di dati di base.
    
- **Calcolo delle firme**: consente di calcolare le firme digitali MD5.
    
- **Estrazione dei composti**: estrae i file interni o contenuti in modo ricorsivo da file compositi (ad esempio, PST, zip, msg). I file estratti sono archiviati nella cartella case del caso.
    
- **Database di sincronizzazione**: processo di database interno.
    
- **Copia file**: copia i file di processo. Questa attività viene sempre visualizzata, anche quando è selezionata l'opzione file di copia avanzata.
    
- **Estrazione del testo**: quando sono presenti file nativi, Advanced eDiscovery estrae testo da questi file tramite DTSearch. Il testo estratto di questi file è memorizzato come file di testo nella cartella case.
    
- **Aggiornamento dei metadati**: elabora i metadati caricati. 
    
- **Finalizzazione**: elaborazione interna che consente di finalizzare i dati dei file di caso caricati (ad esempio, identificare i file di errore e di successo). 
    
Stato attività: visualizzato dopo il completamento dell'attività. Mentre le attività sono in esecuzione, viene visualizzata la durata di esecuzione.
  
> [!NOTE]
> Le attività completate possono includere anche i totali per i file che hanno completato l'elaborazione o i file con errori. 
  
> [!TIP]
> "Annulla" fornisce un'opzione di rollback per interrompere l'esecuzione del processo e quindi eseguire il rollback al popolamento precedente dei dati o ai dati elaborati salvati. Rollback Annulla tutti i dati elaborati. Se non si desidera che i dati elaborati vengano persi (ad esempio, si prevede di ricaricare i file), selezionare l'opzione "Annulla" in questa finestra per scegliere di non eseguire il rollback. 
  
## <a name="process-summary"></a>Riepilogo del processo

In preparare \> il \> riepilogo \> del processo dei risultati del processo, viene visualizzata una scomposizione dei risultati di file caricati in base ai risultati dell'elaborazione e dell'errore del file.
  
I riquadri presentano una visualizzazione grafica delle statistiche dei file importati, come indicato di seguito:
  
- **Riepilogo processi accumulare**d: tutti i file nel caso.
    
- **Riepilogo del processo ultimo**: file caricati dall'ultima sessione o dall'azione. 
    
- **Famiglie ultimo**: informazioni sulla famiglia nel caso (se presente).
    
- Se sono stati aggiunti file di **seeding** , il numero di file di seeding è elencato per ogni problema definito per i file. 
    
    Se la marcatura dei file di **inizializzazione** non è riuscita, nota anche. 
    
- Se sono stati aggiunti file **con tag preselezionati** , il numero di file contrassegnati è elencato per ogni problema definito per i file. 
    
    Se la marcatura dei file **precontrassegnati** ha avuto esito negativo, viene anche rilevato. 
    
![Riepilogo modulo processo](media/2086a691-9e3d-4117-beb2-a5c3a9a4cc94.png)
  
## <a name="process-summary-accumulated-and-last-charts"></a>Riepilogo del processo accumulato e ultimo grafico

La barra sinistra include i file di origine + estratti: tutti i file trovati. 
  
La barra destra, elaborata, include:
  
- File con errori di caricamento
    
- File caricati correttamente, che possono includere: 
    
  - **Existing**: file caricati prima e ora caricati di nuovo (inclusi i duplicati).
    
  - **Testo**: file univoci con testo.
    
  - **Non testuale**: file di testo vuoti, file di testo nativo vuoti, file non di testo nativi. 
    
  - **Duplicate**s: file duplicati con testo.
    
## <a name="last-process-errors"></a>Ultimi errori del processo

Nei risultati \> \> del \> processo di preparazione, vengono visualizzati i dettagli relativi agli errori dell'ultima sessione o all'azione eseguita.
  
![Errori modulo processo](media/4771d0f4-4217-445a-9ba4-8b6541c5ad09.png)
  
## <a name="see-also"></a>Vedere anche

[Office 365 Advanced eDiscovery](office-365-advanced-ediscovery.md)
  
[Esecuzione del modulo di elaborazione e caricamento dei dati](run-the-process-module-and-load-data-in-advanced-ediscovery.md)

