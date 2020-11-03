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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 627791e9dc3d4bf18047a05734a4e275152d19da
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48845033"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-365-defender"></a>Caccia proattivamente per minacce con caccia avanzata in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

La ricerca avanzata è uno strumento di ricerca delle minacce basato sulla query che permette di esplorare dati non elaborati fino a 30 giorni. È possibile ispezionare in modo proattivo gli eventi della rete per individuare gli indicatori e le entità delle minacce. L'accesso flessibile ai dati consente di abilitare la ricerca non vincolata per minacce note e potenziali.
<p></p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]

È possibile usare le stesse query di ricerca delle minacce per creare regole di rilevamento personalizzate. Queste regole vengono eseguite automaticamente per controllare e quindi rispondere all'attività di violazione sospetta, ai computer non configurati e ad altri risultati.

Questa funzionalità è simile alla [ricerca avanzata in Microsoft Defender per endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview). Disponibile in Microsoft 365 Security Center, questa funzionalità supporta le query che controllano un set di dati più ampio da:

- Microsoft Defender ATP
- Microsoft Defender per Office 365
- Microsoft Cloud App Security
- Microsoft Defender per identità

Per utilizzare la funzionalità di ricerca avanzata, [attiva Microsoft 365 Defender](mtp-enable.md).

## <a name="get-started-with-advanced-hunting"></a>Introduzione alla ricerca avanzata

È consigliabile passare attraverso diversi passaggi per iniziare rapidamente con la ricerca avanzata.

| Obiettivo di formazione | Descrizione | Risorsa |
|--|--|--|
| **Impara la lingua** | La ricerca avanzata si basa sul [linguaggio di query di Kusto](https://docs.microsoft.com/azure/kusto/query/), che supporta la stessa sintassi e gli stessi operatori. Iniziare ad apprendere il linguaggio di query eseguendone la prima. | [Informazioni generali sul linguaggio di query](advanced-hunting-query-language.md) |
| **Informazioni su come utilizzare i risultati della query** | Informazioni sui grafici e sui vari modi in cui è possibile visualizzare o esportare i risultati. Scoprire come è possibile ottimizzare rapidamente le query, eseguire il drill-down per ottenere informazioni più ricche e intraprendere azioni di risposta. | - [Utilizzo dei risultati delle query](advanced-hunting-query-results.md)<br>- [Eseguire un'azione sui risultati delle query](advanced-hunting-take-action.md) |
| **Comprensione dello schema** | È possibile ottenere una conoscenza buona e approfondita delle tabelle nello schema e delle relative colonne. Informazioni su dove cercare i dati durante la creazione di query. | - [Riferimenti allo schema](advanced-hunting-schema-tables.md)<br>- [Transizione da Microsoft Defender per endpoint](advanced-hunting-migrate-from-mdatp.md) |
| **Ottenere suggerimenti ed esempi di esperti** | Allenarsi gratuitamente con le guide di Microsoft Experts. Esplorare le raccolte di query predefinite che coprono diversi scenari di ricerca delle minacce. | - [Ottenere una formazione esperta](advanced-hunting-expert-training.md)<br>- [Utilizzo di query condivise](advanced-hunting-shared-queries.md)<br>- [Andare a caccia](advanced-hunting-go-hunt.md)<br>- [Cercare minacce tra dispositivi, messaggi di posta elettronica, app e identità](advanced-hunting-query-emails-devices.md) |
| **Ottimizzare le query e gestire gli errori** | Informazioni su come creare query efficienti e prive di errori. | - [Procedure consigliate per le query](advanced-hunting-best-practices.md)<br>- [Gestire gli errori](advanced-hunting-errors.md) |
| **Creare regole di rilevamento personalizzate** | Informazioni su come è possibile utilizzare le query di ricerca avanzate per attivare gli avvisi e accettare automaticamente le azioni di risposta. | - [Panoramica sui rilevamenti personalizzati](custom-detections-overview.md)<br>- [Regole di rilevamento personalizzate](custom-detection-rules.md) |

## <a name="get-access"></a>Ottenere l'accesso
Per utilizzare la ricerca avanzata o altre funzionalità di [Microsoft 365 Defender](microsoft-threat-protection.md) , è necessario un ruolo appropriato in Azure Active Directory. Inoltre, l'accesso ai dati dell'endpoint è determinato dalle impostazioni del controllo di accesso basato sui ruoli (RBAC) in Microsoft Defender per endpoint. [Leggere informazioni sulla gestione dell'accesso a Microsoft 365 Defender](mtp-permissions.md)

## <a name="data-freshness-and-update-frequency"></a>Aggiornamento dei dati e frequenza degli aggiornamenti
I dati di caccia avanzati possono essere categorizzati in due tipi distinti, ognuno consolidati in modo diverso.

- **Dati relativi a eventi o attività** : popola le tabelle relative agli avvisi, agli eventi di sicurezza, agli eventi di sistema e alle valutazioni di routine. La ricerca avanzata riceve questi dati quasi subito dopo che i sensori che li raccolgono li trasmettono correttamente ai servizi cloud corrispondenti. Ad esempio, è possibile eseguire query sui dati di eventi da sensori integri su workstation o controller di dominio quasi immediatamente dopo che sono disponibili in Microsoft Defender per endpoint e Microsoft Defender per Identity.
- **Dati entità** : popola le tabelle con informazioni su utenti e dispositivi. Questi dati provengono da origini dati relativamente statiche e da origini dinamiche, ad esempio voci di Active Directory e registri eventi. Per fornire dati aggiornati, le tabelle vengono aggiornate con tutte le nuove informazioni ogni 15 minuti, aggiungendo righe che potrebbero non essere completamente popolate. Ogni 24 ore, i dati vengono consolidati per inserire un record che contiene il set di dati più recente e completo su ogni entità.

## <a name="time-zone"></a>Fuso orario
Le informazioni temporali nella ricerca avanzata sono nel fuso orario UTC.

## <a name="related-topics"></a>Argomenti correlati
- [Apprendere il linguaggio delle query](advanced-hunting-query-language.md)
- [Ottenere una formazione esperta](advanced-hunting-expert-training.md)
- [Utilizzare le query condivise](advanced-hunting-shared-queries.md)
- [Comprensione dello schema](advanced-hunting-schema-tables.md)
- [Applicare le procedure consigliate per le query](advanced-hunting-best-practices.md)
- [Panoramica dei rilevamenti personalizzati](custom-detections-overview.md)

