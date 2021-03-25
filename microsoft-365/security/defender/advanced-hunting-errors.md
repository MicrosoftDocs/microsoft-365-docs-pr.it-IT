---
title: Gestire gli errori nella ricerca avanzata per Microsoft 365 Defender
description: Comprendere gli errori visualizzati quando si utilizza la ricerca avanzata
keywords: ricerca avanzata, ricerca delle minacce, ricerca di minacce informatiche, microsoft threat protection, Microsoft 365, mtp, m365, ricerca, query, telemetria, schema, kusto, timeout, risorse, errori, errore sconosciuto, limiti, quota, parametro, allocazione
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: e2c10474db5cbfc63e098ac1c2107dd6c29500e9
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51066765"
---
# <a name="handle-advanced-hunting-errors"></a>Gestire gli errori di ricerca avanzata

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


La ricerca avanzata visualizza errori per segnalare errori di sintassi e ogni volta che le query vengono eseguite su [quote e parametri di utilizzo predefiniti.](advanced-hunting-limits.md) Fare riferimento alla tabella seguente per suggerimenti su come risolvere o evitare errori.

| Tipo di errore | Causa | Risoluzione | Esempi di messaggi di errore |
|--|--|--|--|
| Errori di sintassi | La query contiene nomi non riconosciuti, inclusi i riferimenti a operatori, colonne, funzioni o tabelle inesistenti. | Verificare che i [riferimenti agli operatori e alle funzioni Kusto siano](/azure/data-explorer/kusto/query/) corretti. Controllare [lo schema per](advanced-hunting-schema-tables.md) le colonne, le funzioni e le tabelle di ricerca avanzate corrette. Racchiudere le stringhe di variabili tra virgolette in modo che siano riconosciute. Durante la scrittura delle query, utilizzare i suggerimenti di completamento automatico IntelliSense. | `A recognition error occurred.` |
| Errori semantici | Mentre la query utilizza nomi di operatore, colonna, funzione o tabella validi, esistono errori nella struttura e nella logica risultante. In alcuni casi, la ricerca avanzata identifica l'operatore specifico che ha causato l'errore. | Verificare la presenza di errori nella struttura della query. Per istruzioni, fare riferimento alla documentazione [di Kusto.](/azure/data-explorer/kusto/query/) Durante la scrittura delle query, utilizzare i suggerimenti di completamento automatico IntelliSense. |  `'project' operator: Failed to resolve scalar expression named 'x'`|
| Timeout | Una query può essere eseguita solo entro [un periodo limitato prima del timeout.](advanced-hunting-limits.md) Questo errore può verificarsi con maggiore frequenza quando si eseguono query complesse. | [Ottimizzare la query](advanced-hunting-best-practices.md) | `Query exceeded the timeout period.` |
| Limitazione della CPU | Le query nello stesso tenant hanno superato le risorse [della CPU](advanced-hunting-limits.md) allocate in base alle dimensioni del tenant. | Il servizio controlla l'utilizzo delle risorse della CPU ogni 15 minuti e ogni giorno e visualizza avvisi dopo che l'utilizzo supera il 10% della quota allocata. Se si raggiunge l'utilizzo al 100%, il servizio blocca le query fino al successivo ciclo giornaliero o di 15 minuti. [Ottimizzare le query per evitare di raggiungere le quote della CPU](advanced-hunting-best-practices.md) | - `This query used X% of your organization's allocated resources for the current 15 minutes.`<br>- `You have exceeded processing resources allocated to this tenant. You can run queries again in <duration>.` |
| Limite di dimensioni dei risultati superato  | La dimensione aggregata del set di risultati per la query ha superato la dimensione massima. Questo errore può verificarsi se il set di risultati è così grande che il troncamento al limite di 10.000 record non può ridurlo a una dimensione accettabile. È più probabile che i risultati con più colonne con contenuto ridimensionabile siano influenzati da questo errore. | [Ottimizzare la query](advanced-hunting-best-practices.md) | `Result size limit exceeded. Use "summarize" to aggregate results, "project" to drop uninteresting columns, or "take" to truncate results.` |
| Consumo eccessivo di risorse | La query ha consumato quantità eccessive di risorse ed è stato interrotto il completamento. In alcuni casi, la ricerca avanzata identifica l'operatore specifico che non è stato ottimizzato. | [Ottimizzare la query](advanced-hunting-best-practices.md) | -`Query stopped due to excessive resource consumption.`<br>-`Query stopped. Adjust use of the <operator name> operator to avoid excessive resource consumption.` |
| Errori sconosciuti | La query non è riuscita a causa di un motivo sconosciuto. | Provare a eseguire di nuovo la query. Contattare Microsoft tramite il portale se le query continuano a restituire errori sconosciuti. | `An unexpected error occurred during query execution. Please try again in a few minutes.`

## <a name="related-topics"></a>Argomenti correlati
- [Procedure consigliate per la ricerca avanzata](advanced-hunting-best-practices.md)
- [Quote e parametri di utilizzo](advanced-hunting-limits.md)
- [Comprendere lo schema](advanced-hunting-schema-tables.md)
- [Panoramica del linguaggio di query Kusto](/azure/data-explorer/kusto/query/)