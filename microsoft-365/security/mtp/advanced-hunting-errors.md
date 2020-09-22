---
title: Gestire gli errori nella ricerca avanzata per la protezione dalle minacce di Microsoft
description: Comprendere gli errori visualizzati quando si utilizza la ricerca avanzata
keywords: caccia avanzata, caccia alle minacce, Cyber Threat Hunting, Microsoft Threat Protection, Microsoft 365, MTP, M365, Search, query, telemetria, schema, kusto, timeout, risorse, errori, errore sconosciuto
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 20133e0f5dda3abc583adf66cc20a1d8fde190cf
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198002"
---
# <a name="handle-advanced-hunting-errors"></a>Gestire gli errori di ricerca avanzata

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


Caccia avanzata Visualizza gli errori da notificare per errori di sintassi e ogni volta che le query hanno raggiunto [limiti predefiniti](advanced-hunting-limits.md). Fare riferimento alla tabella seguente per suggerimenti su come risolvere o evitare errori. 

| Tipo di errore | Causa | Risoluzione | Esempi di messaggi di errore |
|--|--|--|--|
| Errori di sintassi | La query contiene nomi non riconosciuti, inclusi i riferimenti a operatori, colonne, funzioni o tabelle inesistenti. | Verificare che i riferimenti agli [operatori e alle funzioni di Kusto](https://docs.microsoft.com/azure/data-explorer/kusto/query/) siano corretti. Controllare [lo schema](advanced-hunting-schema-tables.md) per le colonne, le funzioni e le tabelle di ricerca avanzata corrette. Racchiudere le stringhe variabili tra virgolette in modo che vengano riconosciute. Durante la scrittura delle query, utilizzare i suggerimenti di completamento automatico da IntelliSense. | `A recognition error occurred.` |
| Errori di semantica | Mentre la query utilizza nomi di operatori, colonne, funzioni o tabelle validi, esistono errori nella relativa struttura e logica risultante. In alcuni casi, la ricerca avanzata identifica l'operatore specifico che ha causato l'errore. | Verificare la ricerca di errori nella struttura di query. Fare riferimento alla [documentazione di Kusto](https://docs.microsoft.com/azure/data-explorer/kusto/query/) per indicazioni. Durante la scrittura delle query, utilizzare i suggerimenti di completamento automatico da IntelliSense. |  `'project' operator: Failed to resolve scalar expression named 'x'`|
| Timeout | Una query può essere eseguita solo in un [periodo limitato prima](advanced-hunting-limits.md)del timeout. Questo errore può verificarsi più frequentemente quando si eseguono query complesse. | [Ottimizzare la query](advanced-hunting-best-practices.md) | `Query exceeded the timeout period.` |
| Limitazione della CPU | Le query nello stesso tenant hanno superato le [risorse della CPU](advanced-hunting-limits.md) che sono state allocate in base alle dimensioni del tenant. | Il servizio verifica l'utilizzo delle risorse della CPU ogni 15 minuti e ogni giorno e visualizza gli avvisi dopo che l'utilizzo è superiore al 10% del limite assegnato. Se si raggiunge l'utilizzo del 100%, il servizio blocca le query fino al successivo ciclo giornaliero o di 15 minuti. [Ottimizzare le query per evitare di colpire i limiti della CPU](advanced-hunting-best-practices.md) | - `This query used X% of your organization's allocated resources for the current 15 minutes.`<br>- `You have exceeded processing resources allocated to this tenant. You can run queries again in <duration>.` |
| Superamento del limite di dimensione dei risultati  | La dimensione complessiva del set di risultati per la query ha superato il limite massimo. Questo errore può verificarsi se il set di risultati è talmente elevato che il troncamento al limite di 10.000 record non è in grado di ridurlo a una dimensione accettabile. I risultati con più colonne con contenuto considerevole hanno maggiori probabilità di essere influenzati da questo errore. | [Ottimizzare la query](advanced-hunting-best-practices.md) | `Result size limit exceeded. Use "summarize" to aggregate results, "project" to drop uninteresting columns, or "take" to truncate results.` |
| Consumi eccessivi delle risorse | La query ha consumato quantità eccessive di risorse ed è stato interrotto dal completamento. In alcuni casi, la ricerca avanzata identifica l'operatore specifico che non è stato ottimizzato. | [Ottimizzare la query](advanced-hunting-best-practices.md) | -`Query stopped due to excessive resource consumption.`<br>-`Query stopped. Adjust use of the <operator name> operator to avoid excessive resource consumption.` |
| Errori sconosciuti | La query non è riuscita a causa di un motivo sconosciuto. | Provare a eseguire di nuovo la query. Se le query continuano a restituire errori sconosciuti, contattare Microsoft tramite il portale. | `An unexpected error occurred during query execution. Please try again in a few minutes.`

## <a name="related-topics"></a>Argomenti correlati
- [Procedure consigliate per la ricerca avanzata](advanced-hunting-best-practices.md)
- [Limiti di servizio](advanced-hunting-limits.md)
- [Comprendere lo schema](advanced-hunting-schema-tables.md)
- [Panoramica del linguaggio di query di Kusto](https://docs.microsoft.com/azure/data-explorer/kusto/query/)
