---
title: Limiti di ricerca avanzati in Microsoft Defender ATP
description: Comprendere i vari limiti dei servizi che mantengono reattivo il servizio di ricerca avanzato
keywords: ricerca avanzata, ricerca delle minacce, ricerca di minacce informatiche, mdatp, microsoft defender atp, wdatp, ricerca, query, telemetria, schema, kusto, limite CPU, limite di query, risorse, risultati massimi
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 8a9279d1dd2a6465553b576609bb81cdf4e03fa0
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499532"
---
# <a name="advanced-hunting-service-limits"></a>Limiti del servizio di ricerca avanzata

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Defender per endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

>Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhunting-abovefoldlink)

Per mantenere il servizio efficiente e reattivo, la ricerca avanzata imposta vari limiti per le query eseguite manualmente e tramite [regole di rilevamento personalizzate.](custom-detection-rules.md) Fare riferimento alla tabella seguente per comprendere questi limiti.

| Limite | Dimensioni | Ciclo di aggiornamento | Descrizione |
|--|--|--|--|
| DataRange | 30 giorni | Ogni query | Ogni query può cercare dati fino agli ultimi 30 giorni. |
| Set di risultati | 10.000 righe | Ogni query | Ogni query può restituire fino a 10.000 record. |
| Timeout | 10 minuti | Ogni query | Ogni query può essere eseguita per un massimo di 10 minuti. Se non viene completato entro 10 minuti, il servizio visualizza un errore.
| Risorse CPU | In base alle dimensioni del tenant | - Nell'ora e quindi ogni 15 minuti<br>- Ogni giorno alle 12.00 | Il servizio applica separatamente il limite giornaliero e di 15 minuti. Per ogni limite, il [portale visualizza](advanced-hunting-errors.md) un errore ogni volta che viene eseguita una query e il tenant ha utilizzato più del 10% delle risorse allocate. Le query vengono bloccate se il tenant ha raggiunto il 100% fino al successivo ciclo giornaliero o di 15 minuti. |

>[!NOTE] 
>Un set separato di limiti si applica alle query di ricerca avanzate eseguite tramite l'API. [Informazioni sulle API di ricerca avanzata](run-advanced-query-api.md)

I clienti che eseguono più query regolarmente devono tenere traccia del consumo e applicare le [procedure](advanced-hunting-best-practices.md) consigliate di ottimizzazione per ridurre al minimo le interruzioni derivanti dal superamento di questi limiti.

## <a name="related-topics"></a>Argomenti correlati

- [Procedure consigliate per la ricerca avanzata](advanced-hunting-best-practices.md)
- [Gestire gli errori di ricerca avanzata](advanced-hunting-errors.md)
- [Panoramica della rilevazione avanzata](advanced-hunting-overview.md)
- [Regole di rilevamento personalizzate](custom-detection-rules.md)
