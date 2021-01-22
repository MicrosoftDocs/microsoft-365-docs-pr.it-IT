---
title: Eseguire azioni sui risultati delle query di ricerca avanzata in Microsoft 365 Defender
description: Affrontare rapidamente le minacce e le risorse interessate nei risultati delle query di ricerca avanzata
keywords: ricerca avanzata, ricerca delle minacce, ricerca delle minacce informatiche, protezione dalle minacce Microsoft, Microsoft 365, mtp, m365, ricerca, query, telemetria, azione
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
ms.technology: m365d
ms.openlocfilehash: 9e8ad544cfe17d0d8e5c895e208b42ec56555565
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932179"
---
# <a name="take-action-on-advanced-hunting-query-results"></a>Eseguire un'azione sui risultati delle query di ricerca avanzata

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Puoi contenere rapidamente minacce o risolvere le risorse compromesse che trovi nella ricerca [avanzata](advanced-hunting-overview.md) usando opzioni di azione potenti e complete. Con queste opzioni, è possibile:

- Eseguire varie azioni sui dispositivi
- File in quarantena

## <a name="required-permissions"></a>Autorizzazioni necessarie
Per essere in grado di eseguire azioni tramite la ricerca avanzata, è necessario un ruolo in Microsoft Defender per Endpoint con le autorizzazioni per inviare azioni di correzione [nei dispositivi.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options) Se non è possibile eseguire un'azione, contattare un amministratore globale per ottenere l'autorizzazione seguente:

*Azioni di correzione attive > gestione delle minacce e delle vulnerabilità - Gestione delle correzioni*

## <a name="take-various-actions-on-devices"></a>Eseguire varie azioni sui dispositivi
È possibile eseguire le azioni seguenti sui dispositivi identificati dalla `DeviceId` colonna nei risultati delle query:

- Isolare i dispositivi interessati per contenere un'infezione o impedire lo spostamento laterale degli attacchi
- Raccogliere il pacchetto di analisi per ottenere ulteriori informazioni forensi
- Eseguire un'analisi antivirus per individuare e rimuovere le minacce utilizzando gli ultimi aggiornamenti delle funzionalità di intelligence per la sicurezza
- Avviare un'indagine automatizzata per controllare e correggere le minacce nel dispositivo e probabilmente in altri dispositivi interessati
- Limitare l'esecuzione dell'app solo ai file eseguibili firmati da Microsoft, impedendo attività successive di minacce tramite malware o altri file eseguibili non attendibili

Per altre informazioni su come vengono eseguite queste azioni di risposta tramite Microsoft Defender for Endpoint, leggi le azioni [di risposta nei dispositivi.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts)
   
## <a name="quarantine-files"></a>File in quarantena
È possibile distribuire *l'azione di* quarantena sui file in modo che siano automaticamente messi in quarantena quando vengono rilevati. Quando si seleziona questa azione, è possibile scegliere tra le colonne seguenti per identificare i file nei risultati della query da mettere in quarantena:

- `SHA1` - Nella maggior parte delle tabelle di ricerca avanzate, si tratta dell'SHA-1 del file interessato dall'azione registrata. Ad esempio, se un file è stato copiato, si tratta del file copiato.
- `InitiatingProcessSHA1` — Nella maggior parte delle tabelle di ricerca avanzate, questo è il file responsabile dell'avvio dell'azione registrata. Ad esempio, se è stato avviato un processo figlio, si tratta del processo padre. 
- `SHA256` - Questo è l'equivalente SHA-256 del file identificato dalla `SHA1` colonna.
- `InitiatingProcessSHA256` - Questo è l'equivalente SHA-256 del file identificato dalla `InitiatingProcessSHA1` colonna.

Per altre informazioni su come vengono eseguite le azioni di quarantena e su come ripristinare i file, leggi le azioni [di risposta sui file.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts)

>[!NOTE]
>Per individuare i file e mettere in quarantena i file, i risultati della query devono includere `DeviceId` anche valori come identificatori di dispositivo.  

## <a name="take-action"></a>Eseguire un'azione
Per eseguire una delle azioni descritte, selezionare uno o più record nei risultati della query e quindi **selezionare Eseguire azioni.** Una procedura guidata ti guiderà nel processo di selezione e invio delle azioni preferite.

![Immagine del record selezionato con un pannello per esaminare il record](../../media/mtp-ah/ah-take-actions.png)

## <a name="review-actions-taken"></a>Esaminare le azioni intraprese
Ogni azione viene registrata singolarmente nel centro notifiche in **Cronologia del** centro notifiche ( [](mtp-action-center.md)  >   [security.microsoft.com/action-center/history](https://security.microsoft.com/action-center/history)). Passare al centro notifiche per controllare lo stato di ogni azione.
 
## <a name="related-topics"></a>Argomenti correlati
- [Panoramica della ricerca avanzata](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Usare i risultati delle query](advanced-hunting-query-results.md)
- [Comprendere lo schema](advanced-hunting-schema-tables.md)
- [Panoramica del centro notifiche](mtp-action-center.md)
