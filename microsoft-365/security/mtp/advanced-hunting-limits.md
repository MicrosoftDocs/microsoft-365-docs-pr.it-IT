---
title: Limiti di caccia avanzati in Microsoft Threat Protection
description: Informazioni sui vari limiti di servizio che mantengono attivo il servizio di caccia avanzato
keywords: caccia avanzata, caccia alle minacce, Cyber Threat Hunting, Microsoft Threat Protection, Microsoft 365, MTP, M365, Search, query, telemetria, schema, kusto, limite della CPU, limite di query, risorse, numero massimo di risultati
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
- m365-initiative-m365-defender
ms.topic: article
ms.openlocfilehash: ad21b4241d7cbbcc85639a0a10b47971e5fcebcb
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/09/2020
ms.locfileid: "48412695"
---
# <a name="advanced-hunting-service-limits"></a>Limiti avanzati del servizio di caccia

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft Threat Protection

Per mantenere l'esecuzione del servizio e rispondere, Advanced Hunting imposta vari limiti per le query eseguite manualmente e tramite [le regole di rilevamento personalizzate](custom-detection-rules.md). Per informazioni sui limiti, vedere la tabella seguente.

| Limite | Dimensioni | Ciclo di aggiornamento | Descrizione |
|--|--|--|--|
| DataRange | 30 giorni | Ogni query | Ogni query può cercare i dati da un massimo di 30 giorni. |
| Set di risultati | 10.000 righe | Ogni query | Ogni query può restituire fino a 10.000 record. |
| Timeout | 10 minuti | Ogni query | Ogni query può essere eseguita per un massimo di 10 minuti. Se il servizio non viene completato entro 10 minuti, verrà visualizzato un errore.
| Risorse della CPU | In base alle dimensioni del tenant | -All'ora e quindi ogni 15 minuti<br>-Ogni giorno a mezzanotte | Il servizio applica i limiti giornalieri e di 15 minuti separatamente. Per ogni limite, il [portale Visualizza un errore](advanced-hunting-errors.md) ogni volta che viene eseguita una query e il tenant ha consumato più del 10% delle risorse allocate. Le query vengono bloccate se il tenant ha raggiunto il 100% fino al successivo ciclo giornaliero o di 15 minuti. |

>[!NOTE] 
>Un set di limiti separato si applica alle query di ricerca avanzate eseguite tramite l'API. [Leggere le API di caccia avanzate](https://docs.microsoft.com/microsoft-365/security/mtp/api-advanced-hunting)

I clienti che eseguono più query regolarmente devono tenere conto dei consumi e [applicare le procedure consigliate](advanced-hunting-best-practices.md) per l'ottimizzazione per ridurre al minimo il disturbo risultante dal superamento di tali limiti.

## <a name="related-topics"></a>Argomenti correlati

- [Procedure consigliate per la ricerca avanzata](advanced-hunting-best-practices.md)
- [Gestire gli errori di ricerca avanzata](advanced-hunting-errors.md)
- [Panoramica della ricerca avanzata](advanced-hunting-overview.md)
- [Panoramica dei rilevamenti personalizzati](custom-detections-overview.md)
