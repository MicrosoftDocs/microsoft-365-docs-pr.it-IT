---
title: Quote avanzate di caccia e parametri di utilizzo in Microsoft 365 Defender
description: Comprendere le varie quote e i parametri di utilizzo (limiti di servizio) che mantengono attivo il servizio di caccia avanzato
keywords: caccia avanzata, caccia alle minacce, Cyber Threat Hunting, Microsoft Threat Protection, Microsoft 365, MTP, M365, Search, query, telemetria, schema, kusto, limite della CPU, limite di query, risorse, risultati massimi, quota, parametri, allocazione
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: bab63d9e5939f87f6a1edbf62d256b82552e4fe9
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847369"
---
# <a name="advanced-hunting-quotas-and-usage-parameters"></a>Quote avanzate di caccia e parametri di utilizzo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

Per mantenere l'esecuzione del servizio e rispondere, Advanced Hunting imposta varie quote e parametri di utilizzo (noti anche come "limiti del servizio"). Queste quote e parametri si applicano alle query eseguite manualmente e tramite [regole di rilevamento personalizzate](custom-detection-rules.md). I clienti che eseguono più query regolarmente devono tenere conto dei consumi e [applicare le procedure consigliate](advanced-hunting-best-practices.md) per ridurre al minimo le interruzioni.

Fare riferimento alla tabella seguente per comprendere le quote esistenti e i parametri di utilizzo.

| Quota o parametro | Dimensioni | Ciclo di aggiornamento | Descrizione |
|--|--|--|--|
| DataRange | 30 giorni | Ogni query | Ogni query può cercare i dati da un massimo di 30 giorni. |
| Set di risultati | 10.000 righe | Ogni query | Ogni query può restituire fino a 10.000 record. |
| Timeout | 10 minuti | Ogni query | Ogni query può essere eseguita per un massimo di 10 minuti. Se il servizio non viene completato entro 10 minuti, verrà visualizzato un errore.
| Risorse della CPU | In base alle dimensioni del tenant | -All'ora e quindi ogni 15 minuti<br>-Ogni giorno a mezzanotte | Il servizio impone la quota giornaliera e quella di 15 minuti separatamente. Per ogni quota, nel [portale viene visualizzato un errore](advanced-hunting-errors.md) ogni volta che viene eseguita una query e il tenant ha consumato più del 10% delle risorse allocate. Le query vengono bloccate se il tenant ha raggiunto il 100% fino al successivo ciclo giornaliero o di 15 minuti. |

>[!NOTE] 
>Un insieme separato di quote e parametri si applica alle query di ricerca avanzate eseguite tramite l'API. [Leggere le API di caccia avanzate](https://docs.microsoft.com/microsoft-365/security/mtp/api-advanced-hunting)

## <a name="related-topics"></a>Argomenti correlati

- [Procedure consigliate per la ricerca avanzata](advanced-hunting-best-practices.md)
- [Gestire gli errori di ricerca avanzata](advanced-hunting-errors.md)
- [Panoramica della ricerca avanzata](advanced-hunting-overview.md)
- [Panoramica dei rilevamenti personalizzati](custom-detections-overview.md)