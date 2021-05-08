---
title: Quote di ricerca avanzate e parametri di utilizzo in Microsoft 365 Defender
description: Comprendere le varie quote e i parametri di utilizzo (limiti del servizio) che mantengono reattivo il servizio di ricerca avanzata
keywords: ricerca avanzata, ricerca delle minacce, ricerca di minacce informatiche, Microsoft 365 Defender, Microsoft 365, m365, ricerca, query, telemetria, schema, kusto, limite cpu, limite di query, risorse, risultati massimi, quota, parametri, allocazione
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: d7563a8299bbe7d543b065bb25eeb3bc90a854b9
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245601"
---
# <a name="advanced-hunting-quotas-and-usage-parameters"></a>Quote di ricerca avanzate e parametri di utilizzo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

Per mantenere il servizio efficiente e reattivo, la ricerca avanzata imposta diverse quote e parametri di utilizzo (noti anche come "limiti del servizio"). Queste quote e parametri si applicano separatamente alle query eseguite manualmente e alle query eseguite utilizzando [regole di rilevamento personalizzate.](custom-detection-rules.md) I clienti che eseguono regolarmente più query devono tenere conto di questi limiti e applicare le procedure consigliate di ottimizzazione [per](advanced-hunting-best-practices.md) ridurre al minimo le interruzioni.

Fare riferimento alla tabella seguente per comprendere le quote esistenti e i parametri di utilizzo.

| Quota o parametro | Dimensioni | Ciclo di aggiornamento | Descrizione |
|--|--|--|--|
| DataRange | 30 giorni | Ogni query | Ogni query può cercare dati fino agli ultimi 30 giorni. |
| Set di risultati | 10.000 righe | Ogni query | Ogni query può restituire fino a 10.000 record. |
| Timeout | 10 minuti | Ogni query | Ogni query può essere eseguita per un massimo di 10 minuti. Se non viene completato entro 10 minuti, il servizio visualizza un errore.
| Risorse CPU | In base alle dimensioni del tenant | Ogni 15 minuti | Il [portale visualizza un errore ogni](advanced-hunting-errors.md) volta che viene eseguita una query e il tenant ha utilizzato più del 10% delle risorse allocate. Le query vengono bloccate se il tenant ha raggiunto il 100% fino al successivo ciclo di 15 minuti. |

>[!NOTE] 
>Un set separato di quote e parametri si applica alle query di ricerca avanzate eseguite tramite l'API. [Informazioni sulle API di ricerca avanzata](./api-advanced-hunting.md)

## <a name="related-topics"></a>Argomenti correlati

- [Procedure consigliate per la ricerca avanzata](advanced-hunting-best-practices.md)
- [Gestire gli errori di ricerca avanzata](advanced-hunting-errors.md)
- [Panoramica della rilevazione avanzata](advanced-hunting-overview.md)
- [Panoramica dei rilevamenti personalizzati](custom-detections-overview.md)