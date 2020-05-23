---
title: Panoramica-ricerca avanzata
description: Informazioni sulle query di ricerca avanzata in Microsoft 365 e sul loro utilizzo per individuare in modo proattivo i rischi e i punti di debolezza della rete
keywords: caccia avanzata, caccia alle minacce, Cyber Threat Hunting, Microsoft Threat Protection, Microsoft 365, MTP, M365, Search, query, telemetria, rilevamenti personalizzati, schema, kusto, Microsoft 365, Microsoft Threat Protection
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
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3e8f83b943e83c37ecf13af1221c043d413bd6b5
ms.sourcegitcommit: 8d9509e617ede7cc5ba933c54fb9300d2d1c6344
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "44347832"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-threat-protection"></a>Cercare in modo proattivo minacce con la ricerca avanzata di Microsoft Threat Protection

**Si applica a:**
- Microsoft Threat Protection

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

La ricerca avanzata è uno strumento di ricerca delle minacce basato sulla query che permette di esplorare dati non elaborati fino a 30 giorni. È possibile controllare in modo proattivo eventi nella rete per localizzare indicatori ed entità interessanti. L'accesso flessibile ai dati facilita la ricerca non vincolata delle minacce conosciute e potenziali.

È possibile utilizzare le stesse query di ricerca di minacce per creare regole di rilevamento personalizzate. Queste regole vengono eseguite automaticamente per controllare e rispondere a vari eventi e Stati del sistema, tra cui l'attività di violazione sospetta e i computer non configurati correttamente.

Nel centro sicurezza Microsoft 365, Advanced Hunting supporta le query che esaminano i dati provenienti da diverse aree di lavoro, inclusi i dati relativi a dispositivi, messaggi di posta elettronica, app e identità di Microsoft Defender ATP, Office 365 ATP, Microsoft cloud app Security e Azure ATP. Per utilizzare la ricerca avanzata, [attivare Microsoft Threat Protection](mtp-enable.md).

## <a name="get-started-with-advanced-hunting"></a>Introduzione alla ricerca avanzata

È consigliabile passare attraverso diverse fasi per diventare rapidamente operativi con la ricerca avanzata.

| Obiettivo di formazione | Descrizione | Risorsa |
|--|--|--|
| **Avere un'idea della lingua** | La ricerca avanzata si basa sul [linguaggio di query Kusto](https://docs.microsoft.com/azure/kusto/query/), supportandone la sintassi e gli operatori. Iniziare ad apprendere il linguaggio di query eseguendone la prima. | [Informazioni generali sul linguaggio di query](advanced-hunting-query-language.md) |
| **Informazioni su come utilizzare i risultati della query** | Informazioni sui grafici e sui vari modi in cui è possibile visualizzare o esportare i risultati. Scoprire come è possibile ottimizzare rapidamente le query e eseguire il drill-down per ottenere informazioni più complete. | [Usare i risultati delle query](advanced-hunting-query-results.md) |
| **Comprensione dello schema** | È possibile ottenere una conoscenza buona e approfondita delle tabelle nello schema e delle relative colonne. Questo consente di determinare dove cercare i dati e come creare le query. | [Informazioni di riferimento sullo schema](advanced-hunting-schema-tables.md) |
| **Sfruttare le query predefinite** | Esplorare le raccolte di query predefinite che coprono diversi scenari di ricerca delle minacce. | [Utilizzare le query condivise](advanced-hunting-shared-queries.md) |
| **Ottimizzare le query** | Informazioni su come creare query efficienti e query che combinino dati da email e dispositivi. | - [Procedure consigliate per le query](advanced-hunting-shared-queries.md) <br>- [Cercare tra i dispositivi e i messaggi di posta elettronica](advanced-hunting-best-practices.md) |
| **Creare regole di rilevamento personalizzate** | Informazioni su come è possibile utilizzare le query di ricerca avanzate per attivare gli avvisi e applicare automaticamente le azioni di risposta. | - [Panoramica sui rilevamenti personalizzati](custom-detections-overview.md)<br>- [Regole di rilevamento personalizzate](custom-detection-rules.md) |

## <a name="get-access"></a>Ottenere l'accesso
Per utilizzare la ricerca avanzata o altre funzionalità di [protezione dalle minacce di Microsoft](microsoft-threat-protection.md) , è necessario essere assegnati a un ruolo appropriato in Azure ad. Si noti che l'accesso ai dati dell'endpoint è influenzato dalle impostazioni del controllo di accesso basato sui ruoli in Microsoft Defender ATP. [Informazioni sulla gestione dell'accesso a Microsoft Threat Protection](mtp-permissions.md)

## <a name="get-help-as-you-write-queries"></a>Ottenere assistenza nella scrittura delle query
Trarre vantaggio dalle seguenti funzionalità per scrivere query più velocemente:
- **AutoSuggest** : durante la scrittura di query, la ricerca avanzata fornisce suggerimenti da IntelliSense. 
- **Riferimento di schema** — accanto all’area di lavoro è disponibile il riferimento a uno schema che include l'elenco di tabelle e le relative colonne. Per altre informazioni, passare il puntatore su un elemento. Fare doppio clic su un elemento per inserirlo nell'editor di query.

## <a name="related-topics"></a>Argomenti correlati
- [Apprendere il linguaggio delle query](advanced-hunting-query-language.md)
- [Usare i risultati delle query](advanced-hunting-query-results.md)
- [Utilizzare le query condivise](advanced-hunting-shared-queries.md)
- [Ricerca delle minacce attraverso dispositivi ed email](advanced-hunting-query-emails-devices.md)
- [Comprendere lo schema](advanced-hunting-schema-tables.md)
- [Applicazione delle procedure consigliate per le query](advanced-hunting-best-practices.md)
- [Panoramica dei rilevamenti personalizzati](custom-detections-overview.md)
