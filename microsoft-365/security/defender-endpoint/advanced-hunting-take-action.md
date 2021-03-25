---
title: Eseguire azioni sui risultati delle query di ricerca avanzata in Microsoft Threat Protection
description: Affrontare rapidamente le minacce e gli asset interessati nei risultati delle query di ricerca avanzate
keywords: ricerca avanzata, ricerca delle minacce, ricerca di minacce informatiche, mdatp, microsoft defender atp, ricerca wdatp, query, telemetria, rilevamenti personalizzati, schema, kusto, evitare timeout, righe di comando, ID processo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 09/20/2020
ms.technology: mde
ms.openlocfilehash: 79d720a8b996f826548b79834e5d5c2048e28c2b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51067413"
---
# <a name="take-action-on-advanced-hunting-query-results"></a>Eseguire un'azione sui risultati delle query di ricerca avanzata

**Si applica a:**
- [Microsoft Defender ATP](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

Puoi contenere rapidamente minacce o affrontare asset compromessi che trovi nella ricerca [avanzata](advanced-hunting-overview.md) usando opzioni di azione potenti e complete. Con queste opzioni, è possibile:

- Eseguire varie azioni sui dispositivi
- File in quarantena

## <a name="required-permissions"></a>Autorizzazioni necessarie

Per essere in grado di eseguire azioni tramite la ricerca avanzata, è necessario un ruolo in Defender per Endpoint con autorizzazioni per inviare azioni di correzione [nei dispositivi](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/user-roles#permission-options). Se non è possibile eseguire un'azione, contattare un amministratore globale per ottenere l'autorizzazione seguente:

*Azioni di correzione attive > gestione delle minacce e delle vulnerabilità - Gestione delle correzioni*

## <a name="take-various-actions-on-devices"></a>Eseguire varie azioni sui dispositivi

È possibile eseguire le azioni seguenti nei dispositivi identificati dalla `DeviceId` colonna nei risultati della query:

- Isolare i dispositivi interessati per contenere un'infezione o impedire lo spostamento laterale di attacchi
- Raccogliere un pacchetto di indagine per ottenere ulteriori informazioni forensi
- Eseguire un'analisi antivirus per trovare e rimuovere le minacce utilizzando gli ultimi aggiornamenti di security intelligence
- Avviare un'indagine automatizzata per controllare e correggere le minacce nel dispositivo e probabilmente in altri dispositivi interessati
- Limitare l'esecuzione dell'app solo ai file eseguibili firmati da Microsoft, impedendo attività di minacce successive tramite malware o altri file eseguibili non attendibili

Per altre informazioni su come vengono eseguite queste azioni di risposta tramite Defender for Endpoint, [leggi azioni di risposta nei dispositivi](respond-machine-alerts.md).

## <a name="quarantine-files"></a>File in quarantena

È possibile distribuire *l'azione di* quarantena sui file in modo che siano automaticamente messi in quarantena quando vengono rilevati. Quando si seleziona questa azione, è possibile scegliere tra le colonne seguenti per identificare i file nei risultati della query da mettere in quarantena:

- `SHA1` — Nella maggior parte delle tabelle di ricerca avanzate, si tratta dell'SHA-1 del file interessato dall'azione registrata. Ad esempio, se un file è stato copiato, si tratta del file copiato.
- `InitiatingProcessSHA1` — Nella maggior parte delle tabelle di ricerca avanzate, questo è il file responsabile dell'avvio dell'azione registrata. Ad esempio, se è stato avviato un processo figlio, si tratta del processo padre. 
- `SHA256` - Questo è l'equivalente SHA-256 del file identificato dalla `SHA1` colonna.
- `InitiatingProcessSHA256` - Questo è l'equivalente SHA-256 del file identificato dalla `InitiatingProcessSHA1` colonna.

Per ulteriori informazioni su come vengono eseguite le azioni di quarantena e su come è possibile ripristinare i file, [vedere Azioni di risposta nei file](respond-file-alerts.md).

>[!NOTE]
>Per individuare i file e mettereli in quarantena, i risultati della query devono includere `DeviceId` anche valori come identificatori di dispositivo.  

## <a name="take-action"></a>Eseguire un'azione

Per eseguire una delle azioni descritte, selezionare uno o più record nei risultati della query e quindi fare clic **su Azioni.** Una procedura guidata ti guiderà nel processo di selezione e invio delle azioni preferite.

![Immagine del record selezionato con il pannello per l'ispezione del record](images/ah-take-actions.png)

## <a name="review-actions-taken"></a>Rivedere le azioni intraprese

Ogni azione viene registrata singolarmente nel centro notifiche, in **Cronologia centro** notifiche (  >   [security.microsoft.com/action-center/history](https://security.microsoft.com/action-center/history)). Passare al centro notifiche per controllare lo stato di ogni azione.
 
## <a name="related-topics"></a>Argomenti correlati

- [Panoramica della ricerca avanzata](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Comprendere lo schema](advanced-hunting-schema-reference.md)
- [Usare i risultati delle query](advanced-hunting-query-results.md)
- [Applicare le procedure consigliate per le query](advanced-hunting-best-practices.md)
- [Panoramica dei rilevamenti personalizzati](overview-custom-detections.md)
