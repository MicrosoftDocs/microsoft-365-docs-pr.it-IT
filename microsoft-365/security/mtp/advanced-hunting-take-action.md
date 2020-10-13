---
title: Eseguire un'azione sui risultati delle query di ricerca avanzata in Microsoft Threat Protection
description: Indirizzare rapidamente le minacce e gli asset coinvolti nei risultati della query di ricerca avanzata
keywords: caccia avanzata, caccia alle minacce, Cyber Threat Hunting, Microsoft Threat Protection, Microsoft 365, MTP, M365, Search, query, telemetria, Take Action
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
ms.openlocfilehash: 7250feffa69cc1a6cc37908a599dff0fab6c5e6c
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "48429655"
---
# <a name="take-action-on-advanced-hunting-query-results"></a>Eseguire un'azione sui risultati delle query di ricerca avanzata

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft Threat Protection

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

È possibile contenere rapidamente le minacce o l'indirizzo di risorse compromesse che si trovano in [Advanced Hunting](advanced-hunting-overview.md) con opzioni di azione avanzate e potenti. Con queste opzioni, è possibile:

- Eseguire diverse azioni sui dispositivi
- File di quarantena

## <a name="required-permissions"></a>Autorizzazioni necessarie
Per poter intervenire tramite la caccia avanzata, è necessario un ruolo in Microsoft Defender ATP con [autorizzazioni per l'invio di azioni correttive sui dispositivi](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options). Se non è possibile eseguire l'azione, contattare un amministratore globale per ottenere l'autorizzazione seguente:

*Azioni correttive attive > gestione delle minacce e delle vulnerabilità-gestione della correzione*

## <a name="take-various-actions-on-devices"></a>Eseguire diverse azioni sui dispositivi
È possibile eseguire le azioni seguenti sui dispositivi identificati dalla `DeviceId` colonna nei risultati delle query:

- Isolare i dispositivi coinvolti per contenere un'infezione o impedire che gli attacchi vengano spostati lateralmente
- Raccolta del pacchetto di analisi per ottenere ulteriori informazioni forensi
- Eseguire un'analisi antivirus per individuare e rimuovere le minacce con gli aggiornamenti più recenti di intelligence sulla sicurezza
- Avviare un'indagine automatizzata per controllare e correggere le minacce sul dispositivo e, eventualmente, su altri dispositivi coinvolti
- Limitare l'esecuzione delle app solo ai file eseguibili con firma Microsoft, impedendo successive attività di minacce tramite malware o altri eseguibili non attendibili

Per ulteriori informazioni sul modo in cui vengono eseguite queste azioni di risposta tramite Microsoft Defender ATP, [leggere informazioni sulle azioni di risposta sui dispositivi](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts).
   
## <a name="quarantine-files"></a>File di quarantena
È possibile distribuire l'azione di *quarantena* sui file in modo che vengano automaticamente messi in quarantena quando vengono rilevati. Quando si seleziona questa azione, è possibile scegliere tra le colonne seguenti per identificare i file nei risultati della query per la quarantena:

- `SHA1` -Nella maggior parte delle tabelle di caccia avanzate, questo è l'SHA-1 del file che è stato influenzato dall'azione registrata. Ad esempio, se un file è stato copiato, questo è il file copiato.
- `InitiatingProcessSHA1` -Nella maggior parte delle tabelle di caccia avanzate, questo è il file responsabile dell'avvio dell'azione registrata. Ad esempio, se è stato avviato un processo figlio, questo è il processo padre. 
- `SHA256` : Questo è l'equivalente SHA-256 del file identificato dalla `SHA1` colonna.
- `InitiatingProcessSHA256` : Questo è l'equivalente SHA-256 del file identificato dalla `InitiatingProcessSHA1` colonna.

Per ulteriori informazioni sul modo in cui vengono eseguite le operazioni di quarantena e sulla modalità di ripristino dei file, [leggere informazioni sulle azioni di risposta sui file](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts).

>[!NOTE]
>Per individuare i file e metterli in quarantena, i risultati della query devono includere anche `DeviceId` valori come identificatori di dispositivo.  

## <a name="take-action"></a>Azione
Per eseguire una qualsiasi delle azioni descritte, selezionare uno o più record nei risultati della query e quindi fare clic su **azioni**. Una procedura guidata vi guiderà nel processo di selezione e quindi di invio delle azioni preferite.

![Immagine del record selezionato con pannello per l'ispezione del record](../../media/mtp-ah/ah-take-actions.png)

## <a name="review-actions-taken"></a>Esaminare le azioni intraprese
Ogni azione viene registrata singolarmente nell' [Action Center](mtp-action-center.md) in **Action Center**  >  **History** ([Security.Microsoft.com/Action-Center/History](https://security.microsoft.com/action-center/history)). Andare al centro azioni per controllare lo stato di ogni azione.
 
## <a name="related-topics"></a>Argomenti correlati
- [Panoramica della ricerca avanzata](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Usare i risultati delle query](advanced-hunting-query-results.md)
- [Comprendere lo schema](advanced-hunting-schema-tables.md)
- [Panoramica del centro operazioni](mtp-action-center.md)
