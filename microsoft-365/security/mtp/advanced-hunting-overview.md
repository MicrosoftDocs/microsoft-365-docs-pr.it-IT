---
title: Panoramica - Ricerca avanzata
description: Informazioni sulle query di ricerca avanzata in Microsoft 365 e sul loro utilizzo per individuare in modo proattivo i rischi e i punti di debolezza della rete
keywords: ricerca avanzata, ricerca delle minacce, ricerca delle minacce informatiche, protezione dalle minacce Microsoft, Microsoft 365, mtp, m365, ricerca, query, telemetria, rilevamenti personalizzati, schema, kusto, Microsoft 365, Microsoft Threat Protection
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: 8fbf9c3d93434ec2dbc3f069bc0fbd3fe03fc260
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932275"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-365-defender"></a>Ricerca proattiva delle minacce con ricerca avanzata in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

> Si vuole provare Microsoft 365 Defender? È possibile [valutarlo in un ambiente lab o](https://aka.ms/mtp-trial-lab) eseguire il progetto pilota in [produzione.](https://aka.ms/m365d-pilotplaybook)
>

La ricerca avanzata è uno strumento di ricerca delle minacce basato sulla query che permette di esplorare dati non elaborati fino a 30 giorni. È possibile esaminare in modo proattivo gli eventi nella rete per individuare le entità e gli indicatori di minaccia. L'accesso flessibile ai dati consente la ricerca senza vincoli delle minacce note e potenziali.
<p></p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]

È possibile usare le stesse query di ricerca delle minacce per creare regole di rilevamento personalizzate. Queste regole vengono eseguite automaticamente per verificare e quindi rispondere a attività di violazione sospetta, computer non configurati correttamente e altri risultati.

Questa funzionalità è simile alla ricerca [avanzata in Microsoft Defender for Endpoint.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview) Disponibile nel Centro sicurezza Microsoft 365, questa funzionalità supporta le query che controllano un set di dati più ampio da:

- Microsoft Defender per endpoint
- Microsoft Defender per Office 365
- Microsoft Cloud App Security
- Che cosa è Microsoft Defender per identità?

Per usare la ricerca avanzata, [attivare Microsoft 365 Defender.](mtp-enable.md)

## <a name="get-started-with-advanced-hunting"></a>Introduzione alla ricerca avanzata

Ti consigliamo di eseguire diversi passaggi per iniziare rapidamente a usare la ricerca avanzata.

| Obiettivo di formazione | Descrizione | Risorsa |
|--|--|--|
| **Informazioni sulla lingua** | La ricerca avanzata si basa [sul linguaggio di query Kusto,](https://docs.microsoft.com/azure/kusto/query/)che supporta la stessa sintassi e gli stessi operatori. Iniziare ad apprendere il linguaggio di query eseguendone la prima. | [Informazioni generali sul linguaggio di query](advanced-hunting-query-language.md) |
| **Informazioni su come utilizzare i risultati della query** | Informazioni sui grafici e sui vari modi in cui è possibile visualizzare o esportare i risultati. Scopri come modificare rapidamente le query, eseguire il drill-down per ottenere informazioni più dettagliate ed eseguire azioni di risposta. | - [Utilizzare i risultati delle query](advanced-hunting-query-results.md)<br>- [Eseguire un'azione sui risultati della query](advanced-hunting-take-action.md) |
| **Comprensione dello schema** | È possibile ottenere una conoscenza buona e approfondita delle tabelle nello schema e delle relative colonne. Informazioni su dove cercare i dati durante la creazione delle query. | - [Informazioni di riferimento sullo schema](advanced-hunting-schema-tables.md)<br>- [Transizione da Microsoft Defender per Endpoint](advanced-hunting-migrate-from-mdatp.md) |
| **Ottenere suggerimenti ed esempi per esperti** | Formazione gratuita con le guide di esperti Microsoft. Esplorare le raccolte di query predefinite che coprono diversi scenari di ricerca delle minacce. | - [Ottenere una formazione di esperti](advanced-hunting-expert-training.md)<br>- [Usare query condivise](advanced-hunting-shared-queries.md)<br>- [Vai a ricerca](advanced-hunting-go-hunt.md)<br>- [Cercare minacce su dispositivi, messaggi di posta elettronica, app e identità](advanced-hunting-query-emails-devices.md) |
| **Ottimizzare le query e gestire gli errori** | Comprendere come creare query efficienti e senza errori. | - [Procedure consigliate per le query](advanced-hunting-best-practices.md)<br>- [Gestire gli errori](advanced-hunting-errors.md) |
| **Creare regole di rilevamento personalizzate** | Comprendere come usare le query di ricerca avanzata per attivare avvisi ed eseguire automaticamente azioni di risposta. | - [Panoramica dei rilevamenti personalizzati](custom-detections-overview.md)<br>- [Regole di rilevamento personalizzate](custom-detection-rules.md) |

## <a name="get-access"></a>Ottenere l'accesso
Per usare la ricerca avanzata o altre funzionalità di [Microsoft 365 Defender,](microsoft-threat-protection.md) è necessario un ruolo appropriato in Azure Active Directory. Inoltre, l'accesso ai dati degli endpoint è determinato dalle impostazioni del controllo di accesso basato sui ruoli (RBAC) in Microsoft Defender per endpoint. [Informazioni sulla gestione dell'accesso a Microsoft 365 Defender](mtp-permissions.md)

## <a name="data-freshness-and-update-frequency"></a>Aggiornamento dei dati e frequenza di aggiornamento
I dati di ricerca avanzata possono essere categorizzati in due tipi distinti, ognuno consolidato in modo diverso.

- **Dati relativi a eventi o** attività: popola le tabelle relative a avvisi, eventi di sicurezza, eventi di sistema e valutazioni di routine. La ricerca avanzata riceve questi dati quasi immediatamente dopo che i sensori che li raccolgono li trasmettono correttamente ai servizi cloud corrispondenti. Ad esempio, puoi eseguire query sui dati degli eventi da sensori integri su workstation o controller di dominio quasi immediatamente dopo che sono disponibili in Microsoft Defender per Endpoint e Microsoft Defender per l'identità.
- **Dati entità:** popola le tabelle con informazioni su utenti e dispositivi. Questi dati provengono sia da origini dati relativamente statiche che da origini dinamiche, ad esempio voci di Active Directory e registri eventi. Per fornire dati aggiornati, le tabelle vengono aggiornate con le nuove informazioni ogni 15 minuti, aggiungendo righe che potrebbero non essere completamente popolate. Ogni 24 ore, i dati vengono consolidati per inserire un record contenente il set di dati più recente e completo su ogni entità.

## <a name="time-zone"></a>Fuso orario
Le informazioni sull'ora nella ricerca avanzata si trova nel fuso orario UTC.

## <a name="related-topics"></a>Argomenti correlati
- [Apprendere il linguaggio delle query](advanced-hunting-query-language.md)
- [Ottenere una formazione esperta](advanced-hunting-expert-training.md)
- [Utilizzare le query condivise](advanced-hunting-shared-queries.md)
- [Comprensione dello schema](advanced-hunting-schema-tables.md)
- [Applicare le procedure consigliate per le query](advanced-hunting-best-practices.md)
- [Panoramica dei rilevamenti personalizzati](custom-detections-overview.md)

