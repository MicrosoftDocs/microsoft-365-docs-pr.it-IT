---
title: Eseguire il modulo di processo in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
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
ms.assetid: dbc1e251-0596-443b-ac9b-f398ba955b73
description: Informazioni sulle linee guida per la preparazione dei file di dati per l'analisi con Advanced eDiscovery.
ms.openlocfilehash: 3773833d9d0af993b4ccb35bcd18276800c4081f
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662811"
---
# <a name="run-the-process-module-in-advanced-ediscovery-classic"></a>Eseguire il modulo di processo in Advanced eDiscovery (Classic)

I file dei casi vengono caricati in Advanced eDiscovery durante la **preparazione** del \> **processo**. 
  
> [!NOTE]
> Per usare Advanced eDiscovery è necessario avere Office 365 E3 con il componente aggiuntivo Advanced Compliance o un abbonamento E5 dell'organizzazione. Se non si ha questo piano e si desidera provare Advanced eDiscovery, è possibile [richiedere una valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
## <a name="guidelines-preparing-data-for-advanced-ediscovery"></a>Linee guida: preparazione dei dati per Advanced eDiscovery

- **Qualità**: identificare chiaramente la popolazione dei file del caso pertinente per il caso.
    
- **Carichi**: caricare i file in un percorso accessibile a Advanced eDiscovery.
    
- **ID file**: un identificatore di file univoco in Advanced eDiscovery. Se non è stato importato alcun identificatore di file, Advanced eDiscovery genera automaticamente l'ID. Se si mappa l'ID in un carico di processo successivo e si mappa un percorso diverso da quello del caricamento del processo iniziale, Advanced eDiscovery sostituirà il percorso (invece di aggiungere una nuova voce di file). L'ID può essere utilizzato come riferimento nel processo di esportazione. Il valore dell'ID non deve essere "-1".
    
- **MD5**: questa firma viene utilizzata per distinguere i file (due file non vengono considerati duplicati esatti, a meno che non dispongano dello stesso MD5). Per impostazione predefinita, Advanced eDiscovery calcola l'MD5 dei file. Quando i file caricati sono file di testo, è consigliabile caricare e mappare il valore MD5 originale anziché calcolarlo in Advanced eDiscovery.
    
- **Tipo di file e nome**:
    
  - Advanced eDiscovery è in grado di elaborare file di vari formati ed estrarre i file nativi caricati in un formato standard, ad esempio \* . TXT, HTML o. XML. L'elaborazione dei file di testo è più veloce rispetto ai file nativi. I file di testo estratti vengono archiviati nella cartella case.
    
  - Non caricare file che non possono essere estratti, ad esempio file di sistema o immagini grafiche. Questi file potrebbero ritardare l'elaborazione.
    
  - Verificare che i nomi dei file siano denominati in modo significativo e i percorsi siano corretti.
    
- **Percorso file**: Advanced eDiscovery è in grado di caricare file con lunghezze di percorso fino a 400 caratteri.
    
- **Estrazione** del testo: quando si estrae del testo da file nativi, oltre al testo normale, vengono estratti anche i seguenti elementi: testo nascosto (Excel e. doc), colonne nascoste (Excel), rilevamento delle modifiche (file con estensione doc), note degli altoparlanti (con estensione ppt), oggetti incorporati (ad esempio, oggetti di Excel in a. ppt). Questi possono essere visualizzati nell'editor di testo.
    
- **Ignora testo**: questa funzionalità facoltativa è definita dopo l'esecuzione del processo e prima dell'analisi. Ignorare il testo deve essere utilizzato con cautela perché il relativo utilizzo può ridurre le prestazioni dell'analisi dei file.
    
- **Testo multilingue**: Advanced eDiscovery attualmente non gestisce i nomi multilingue per i tag, il custode e i problemi.
    
- **Metadati**: determinare se sono presenti metadati che si desidera salvare nel database dei casi per riferimento futuro, ad esempio l'intervallo di date, le dimensioni dei file, il tipo di file, il custode e l'oggetto. I metadati possono essere caricati dopo che i file sono già stati caricati senza rieseguire l'inventario o l'aggiunta di un sovraccarico di rielaborazione. 
    
  - Se i file sono stati caricati originariamente in base al percorso, mappare la colonna percorso quando si importano successivamente i metadati. È possibile fare riferimento al file in base all'ID e mappare un percorso diverso. Questo è uno scenario utile quando si modificano i percorsi dei file.
    
  - Se i file sono stati originariamente caricati da ID file, mappare la colonna ID durante il caricamento dei metadati. Se si fa riferimento al file in base al percorso (anziché all'ID), i file verranno caricati di nuovo con un ID diverso. Advanced eDiscovery consente di creare copie dei file anziché i metadati di caricamento dei file esistenti.
    
- **Famiglie**: non è possibile caricare una famiglia senza il padre (capo della famiglia). 
    
- **Dimensioni file**: non è previsto alcun limite per la dimensione dei file caricati in Advanced eDiscovery. Per l'analisi (Analyze, pertinenza e così via), il limite è 5.242.880 caratteri del testo estratto. I file di grandi dimensioni vengono ignorati (ad esempio, in caso di pertinenza, i file non partecipano al processo di formazione per pertinenza e non ricevono un punteggio di pertinenza dopo il calcolo del batch).
    
- **Quantità file**: non è previsto alcun limite consigliato per il numero di file che possono essere gestiti in un singolo caso. Le prestazioni dipendono dalle risorse del sistema. 
    
## <a name="filtering-files"></a>Filtro dei file

Un'etichetta definita dall'utente può essere associata a un insieme di file per escluderli dal processo o da altre attività. Ogni sessione di processo è associata a un ID batch. Anche se l'ID batch non è visibile per l'esperto in pertinenza, è possibile eseguire questa operazione utilizzando un'utilità di ricerca, aggiungendo un filtro per il batch corrente e contrassegnando tutti i file corretti con un'etichetta definita dall'utente. 
  
## <a name="see-also"></a>Vedere anche

[Advanced eDiscovery (classico)](office-365-advanced-ediscovery.md)
  
[Esecuzione del modulo di elaborazione e caricamento dei dati](run-the-process-module-and-load-data-in-advanced-ediscovery.md)
  
[Visualizzazione dei risultati del modulo di elaborazione](view-process-module-results-in-advanced-ediscovery.md)

