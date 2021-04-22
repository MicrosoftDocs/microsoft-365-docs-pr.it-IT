---
title: Panoramica della ricerca avanzata in Microsoft Defender for Endpoint
description: Usare le funzionalità di ricerca delle minacce in Microsoft Defender for Endpoint per creare query che rilevano minacce e punti deboli nella rete
keywords: ricerca avanzata, ricerca delle minacce, ricerca di minacce informatiche, Microsoft Defender for Endpoint, ricerca, query, telemetria, rilevamenti personalizzati, schema, kusto, fuso orario, UTC
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
ms.openlocfilehash: 114c0192f77411016fcb13ec2b912f4440ffa6e0
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934358"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting"></a>Ricerca proattiva di minacce con ricerca avanzata

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

>Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhunting-abovefoldlink)

La ricerca avanzata è uno strumento di ricerca delle minacce basato sulla query che permette di esplorare dati non elaborati fino a 30 giorni. È possibile esaminare in modo proattivo gli eventi nella rete per individuare gli indicatori di minaccia e le entità. L'accesso flessibile ai dati consente la ricerca senza vincoli delle minacce note e potenziali.

Guarda questo video per una breve panoramica della ricerca avanzata e una breve esercitazione che ti permetterà di iniziare rapidamente.
<br />
<br />

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bGqo]

È possibile usare le stesse query di ricerca delle minacce per creare regole di rilevamento personalizzate. Queste regole vengono eseguite automaticamente per cercare e quindi rispondere a attività sospette di violazione, computer non configurati correttamente e altri risultati.

>[!TIP]
>Usa [la ricerca avanzata in Microsoft 365 Defender](/microsoft-365/security/defender/advanced-hunting-overview) per cercare minacce usando i dati di Defender for Endpoint, Microsoft Defender per Office 365, Microsoft Cloud App Security e Microsoft Defender for Identity. [Attivare Microsoft 365 Defender](/microsoft-365/security/defender/m365d-enable).<br><br>
Per altre informazioni su come spostare i flussi di lavoro di ricerca avanzata da Microsoft Defender per Endpoint a Microsoft 365 Defender, vedere [Migrate advanced hunting queries from Microsoft Defender for Endpoint](/microsoft-365/security/defender/advanced-hunting-migrate-from-mde).

## <a name="get-started-with-advanced-hunting"></a>Introduzione alla ricerca avanzata

Eseguire i passaggi seguenti per aumentare le conoscenze di ricerca avanzate.

È consigliabile passare attraverso diverse fasi per diventare rapidamente operativi con la ricerca avanzata.

| Obiettivo di formazione | Descrizione | Risorsa |
|--|--|--|
| **Informazioni sulla lingua** | La ricerca avanzata si basa [sul linguaggio di query Kusto,](https://docs.microsoft.com/azure/kusto/query/)che supporta la stessa sintassi e gli stessi operatori. Iniziare ad apprendere il linguaggio di query eseguendone la prima. | [Informazioni generali sul linguaggio di query](advanced-hunting-query-language.md) |
| **Informazioni su come utilizzare i risultati della query** | Informazioni sui grafici e sui vari modi in cui è possibile visualizzare o esportare i risultati. Scopri come modificare rapidamente le query ed eseguire il drill-down per ottenere informazioni più dettagliate. | [Usare i risultati delle query](advanced-hunting-query-results.md) |
| **Comprensione dello schema** | È possibile ottenere una conoscenza buona e approfondita delle tabelle nello schema e delle relative colonne. Informazioni su dove cercare i dati durante la creazione delle query. | [Informazioni di riferimento sullo schema](advanced-hunting-schema-reference.md) |
| **Utilizzare le query predefinite** | Esplorare le raccolte di query predefinite che coprono diversi scenari di ricerca delle minacce. | [Query condivise](advanced-hunting-shared-queries.md) |
| **Ottimizzare le query e gestire gli errori** | Comprendere come creare query efficienti e senza errori. | - [Procedure consigliate per le query](advanced-hunting-best-practices.md)<br>- [Gestire gli errori](advanced-hunting-errors.md) |
| **Ottenere la copertura più completa** | Utilizzare le impostazioni di controllo per fornire una migliore copertura dei dati per l'organizzazione. | - [Estendere la copertura di ricerca avanzata](advanced-hunting-extend-data.md) |
| **Eseguire un'indagine rapida** | Eseguire rapidamente una query di ricerca avanzata per analizzare le attività sospette. | - [Ricerca rapida di informazioni su entità o eventi con *go hunt*](advanced-hunting-go-hunt.md) |
| **Contenere minacce e compromissione degli indirizzi** | Rispondere agli attacchi tramite la messa in rete dei file, la limitazione dell'esecuzione dell'app e altre azioni | - [Eseguire un'azione sui risultati delle query di ricerca avanzata](advanced-hunting-take-action.md) |
| **Creare regole di rilevamento personalizzate** | Comprendere come è possibile utilizzare query di ricerca avanzate per attivare avvisi ed eseguire automaticamente azioni di risposta. | - [Panoramica dei rilevamenti personalizzati](overview-custom-detections.md)<br>- [Regole di rilevamento personalizzate](custom-detection-rules.md) |

## <a name="data-freshness-and-update-frequency"></a>Aggiornamento dei dati e frequenza di aggiornamento

I dati di ricerca avanzata possono essere categorizzati in due tipi distinti, ognuno consolidato in modo diverso.

- **Dati relativi a eventi o** attività: popola le tabelle relative a avvisi, eventi di sicurezza, eventi di sistema e valutazioni di routine. La ricerca avanzata riceve questi dati quasi subito dopo che i sensori che li raccolgono li trasmettono correttamente a Defender for Endpoint.
- **Dati entità:** popola le tabelle con informazioni consolidate su utenti e dispositivi. Questi dati provengono sia da origini dati relativamente statiche che da origini dinamiche, ad esempio voci di Active Directory e registri eventi. Per fornire dati aggiornati, le tabelle vengono aggiornate con eventuali nuove informazioni ogni 15 minuti, aggiungendo righe che potrebbero non essere completamente popolate. Ogni 24 ore, i dati vengono consolidati per inserire un record contenente il set di dati più recente e completo su ogni entità.

## <a name="time-zone"></a>Fuso orario

Le informazioni sull'ora nella ricerca avanzata si trova attualmente nel fuso orario UTC.

## <a name="related-topics"></a>Argomenti correlati

- [Apprendere il linguaggio delle query](advanced-hunting-query-language.md)
- [Usare i risultati delle query](advanced-hunting-query-results.md)
- [Utilizzare le query condivise](advanced-hunting-shared-queries.md)
- [Comprensione dello schema](advanced-hunting-schema-reference.md)
- [Applicare le procedure consigliate per le query](advanced-hunting-best-practices.md)
- [Panoramica dei rilevamenti personalizzati](overview-custom-detections.md)
