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
ms.openlocfilehash: 75d709cc1f98a12bb6f5a5b6539583a33be500b6
ms.sourcegitcommit: 195172dd836e8a793e8e0c2db3323b7391bc51ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2020
ms.locfileid: "47255746"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-threat-protection"></a>Cercare in modo proattivo minacce con la ricerca avanzata di Microsoft Threat Protection

**Si applica a:**
- Microsoft Threat Protection

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

La ricerca avanzata è uno strumento di ricerca delle minacce basato sulla query che permette di esplorare dati non elaborati fino a 30 giorni. È possibile controllare in modo proattivo eventi nella rete per localizzare indicatori ed entità interessanti. L'accesso flessibile ai dati facilita la ricerca non vincolata delle minacce conosciute e potenziali.
<p></p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]

È possibile usare le stesse query di ricerca delle minacce per creare regole di rilevamento personalizzate. Queste regole vengono eseguite automaticamente per il controllo di diversi eventi e dello stato di salute del sistema e per le relative risposte, tra cui attività di violazione sospette e computer non configurati correttamente.

La caratteristica è simile alla [ricerca avanzata in Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview), tranne per il fatto che nel centro sicurezza Microsoft 365, Advanced Hunting supporta le query che esaminano i dati provenienti da diverse aree di lavoro, inclusi i dati relativi a dispositivi, messaggi di posta elettronica, app e identità di Microsoft Defender ATP, Office 365 ATP, Microsoft cloud app Security e Azure ATP. Per utilizzare la ricerca avanzata, [attivare Microsoft Threat Protection](mtp-enable.md).

## <a name="get-started-with-advanced-hunting"></a>Introduzione alla ricerca avanzata

È consigliabile passare attraverso diverse fasi per diventare rapidamente operativi con la ricerca avanzata.

| Obiettivo di formazione | Descrizione | Risorsa |
|--|--|--|
| **Avere un'idea della lingua** | La ricerca avanzata si basa sul [linguaggio di query di Kusto](https://docs.microsoft.com/azure/kusto/query/), che supporta la stessa sintassi e gli stessi operatori. Iniziare ad apprendere il linguaggio di query eseguendone la prima. | [Informazioni generali sul linguaggio di query](advanced-hunting-query-language.md) |
| **Informazioni su come utilizzare i risultati della query** | Informazioni sui grafici e sui vari modi in cui è possibile visualizzare o esportare i risultati. Scoprire come è possibile ottimizzare rapidamente le query, eseguire il drill-down per ottenere informazioni più ricche e intraprendere azioni di risposta. | - [Utilizzo dei risultati delle query](advanced-hunting-query-results.md)<br>- [Eseguire un'azione sui risultati delle query](advanced-hunting-take-action.md) |
| **Comprensione dello schema** | È possibile ottenere una conoscenza buona e approfondita delle tabelle nello schema e delle relative colonne. Questo consente di determinare dove cercare i dati e come creare le query. | [Informazioni di riferimento sullo schema](advanced-hunting-schema-tables.md) |
| **Sfruttare le query predefinite** | Esplorare le raccolte di query predefinite che coprono diversi scenari di ricerca delle minacce. | - [Utilizzo di query condivise](advanced-hunting-shared-queries.md)<br>- [Andare a caccia](advanced-hunting-go-hunt.md) |
| **Ottimizzare le query** | Informazioni su come creare query efficienti e query che combinino dati da email e dispositivi. | - [Procedure consigliate per le query](advanced-hunting-best-practices.md) <br>- [Cercare tra i dispositivi e i messaggi di posta elettronica](advanced-hunting-query-emails-devices.md) |
| **Creare regole di rilevamento personalizzate** | Informazioni su come è possibile utilizzare le query di ricerca avanzate per attivare gli avvisi e applicare automaticamente le azioni di risposta. | - [Panoramica sui rilevamenti personalizzati](custom-detections-overview.md)<br>- [Regole di rilevamento personalizzate](custom-detection-rules.md) |

## <a name="get-access"></a>Ottenere l'accesso
Per utilizzare la ricerca avanzata o altre funzionalità di [protezione dalle minacce di Microsoft](microsoft-threat-protection.md) , è necessario essere assegnati a un ruolo appropriato in Azure ad. Si noti che l'accesso ai dati dell'endpoint è influenzato dalle impostazioni del controllo di accesso basato sui ruoli in Microsoft Defender ATP. [Informazioni sulla gestione dell'accesso a Microsoft Threat Protection](mtp-permissions.md)

## <a name="data-freshness-and-update-frequency"></a>Aggiornamento dei dati e frequenza degli aggiornamenti
I dati di caccia avanzati possono essere categorizzati in due tipi distinti, ognuno consolidati in modo diverso.

- **Dati relativi a eventi o attività** : popola le tabelle relative agli avvisi, agli eventi di sicurezza, agli eventi di sistema e alle valutazioni di routine. La ricerca avanzata riceve questi dati quasi subito dopo che i sensori che li raccolgono li trasmettono correttamente ai servizi cloud corrispondenti. Ad esempio, è possibile iniziare a eseguire query sui dati degli eventi da sensori integri su workstation o controller di dominio quasi subito dopo essere disponibili su Microsoft Defender ATP e Azure ATP.
- **Dati entità** : popola le tabelle con informazioni consolidate su utenti e dispositivi. Questi dati provengono da origini dati relativamente statiche, ad esempio le voci di Active Directory e le origini dinamiche, ad esempio i registri eventi. Per fornire dati aggiornati, le tabelle vengono aggiornate ogni 15 minuti con tutte le nuove informazioni, aggiungendo righe che potrebbero non essere completamente popolate. Ogni 24 ore, i dati vengono consolidati per inserire un record che contiene il set di dati più recente e completo su ogni entità.

## <a name="time-zone"></a>Fuso orario
Tutte le informazioni sul tempo nella ricerca avanzata sono nel fuso orario UTC.

## <a name="related-topics"></a>Argomenti correlati
- [Apprendere il linguaggio delle query](advanced-hunting-query-language.md)
- [Usare i risultati delle query](advanced-hunting-query-results.md)
- [Intraprendere azioni sui risultati della query](advanced-hunting-take-action.md)
- [Utilizzare le query condivise](advanced-hunting-shared-queries.md)
- [Cercare tra dispositivi, posta elettronica, app e identità](advanced-hunting-query-emails-devices.md)
- [Comprendere lo schema](advanced-hunting-schema-tables.md)
- [Applicare le procedure consigliate per le query](advanced-hunting-best-practices.md)
- [Panoramica dei rilevamenti personalizzati](custom-detections-overview.md)
