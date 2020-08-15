---
title: Isolamento del tenant in Office 365 Video
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: In questo articolo, trovare una spiegazione del modo in cui l'isolamento tenant mantiene i video archiviati di ogni tenant separati in Office 365 video.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3f46812bb2bf9432252c2de6bb46fbb47cb71221
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691283"
---
# <a name="tenant-isolation-in-office-365-video"></a>Isolamento del tenant in Office 365 Video

> [!NOTE]
> Il video di Office 365 verrà sostituito da Microsoft Stream. Per ulteriori informazioni sul nuovo servizio video aziendale che consente di aggiungere servizi di intelligence alla collaborazione video e di conoscere i piani di transizione per i clienti Microsoft 365 video attuali, vedere [transizione video di Office 365 a Microsoft Stream Overview](https://docs.microsoft.com/stream/migrate-from-office-365).

## <a name="introduction"></a>Introduzione

Lo spazio di archiviazione di Azure viene utilizzato per archiviare i dati di più servizi di Office 365, tra cui Office 365 video e Sway. Nello spazio di archiviazione di Azure è incluso l'archiviazione BLOB, ovvero un archivio oggetti cloud estremamente scalabile e basato sul REST utilizzato per l'archiviazione dei dati non strutturati. Lo spazio di archiviazione di Azure utilizza un semplice modello di controllo di accesso; ogni sottoscrizione di Azure è in grado di creare uno o più account di archiviazione. Ogni account di archiviazione dispone di una sola chiave segreta utilizzata per controllare l'accesso a tutti i dati dell'account di archiviazione. Questo supporta lo scenario tipico in cui l'archiviazione è associata alle applicazioni e tali applicazioni dispongono del controllo completo sui dati associati; ad esempio, Sway archivia il contenuto nello spazio di archiviazione di Azure. Tutti i contenuti dei clienti per Sway sono archiviati in account di archiviazione di Azure condivisi. Il contenuto di ogni utente si trova in una struttura di directory distinta di BLOB nell'archiviazione di Azure.

I sistemi che gestiscono l'accesso agli ambienti dei clienti (ad esempio, il portale di Azure, SMAPI e così via) sono isolati all'interno di un'applicazione di Azure gestita da Microsoft. Questo separa logicamente l'infrastruttura di accesso dei clienti dal livello di archiviazione e applicazioni del cliente.

## <a name="tenant-isolation-in-office-365-video"></a>Isolamento del tenant in Office 365 Video

[Office 365 video](https://support.office.com/article/Meet-Office-365-Video-ca1cc1a9-a615-46e1-b6a3-40dbd99939a6) è un portale aziendale che fornisce alle organizzazioni una destinazione estremamente sicura, a livello di organizzazione, per la pubblicazione, la condivisione e la scoperta di contenuti video. In Office 365 video, i video di ogni tenant vengono mantenuti isolati e crittografati in tutti i percorsi e sono disponibili solo per gli utenti autenticati che dispongono dell'accesso e delle autorizzazioni per i video dell'organizzazione. Office 365 video utilizza una combinazione di tecnologie per eseguire le operazioni seguenti:

- SharePoint Online viene utilizzato per archiviare i file video e i metadati (titolo video, descrizione e così via). Fornisce inoltre il livello di sicurezza e conformità (inclusa l'autenticazione) e le funzionalità di ricerca.
- Servizi di Azure Media fornisce la transcodifica, il flusso adattivo, il recapito sicuro (utilizzando la crittografia AES) e le funzionalità di anteprima.

[Azure Media Services](https://azure.microsoft.com/services/media-services/) è un'offerta Platform-as-a-Service per l'abilitazione dei flussi di lavoro multimediali end-to-end nel cloud. La piattaforma fornisce un'API REST per il caricamento, la codifica, la crittografia (con PlayReady) e il recapito dei contenuti multimediali tramite i datacenter di Azure in tutto il mondo.

Tutti i caricamenti per il video di Office 365 si verificano tramite HTTPS. Quando viene caricato un file video, viene archiviato in SharePoint Online e una copia del file viene inviata tramite un canale crittografato ai servizi di Azure Media. Azure Media Services esegue la transcodifica del video in più formati ottimizzati per la visualizzazione dell'esperienza (ad esempio, per dispositivi mobili, larghezza di banda ridotta, larghezza di banda elevata e così via). Questi file, insieme al file originale acquisito durante il caricamento, vengono archiviati nell'archiviazione BLOB di Azure. I file vengono crittografati con AES 128 per l'algoritmo di compressione di crittografia comune MPEG (o versione precedente di PlayReady) per la riproduzione e crittografati utilizzando la crittografia di archiviazione AES 256 prima di essere archiviati in archiviazione BLOB di Azure. Utilizzando l'SDK client di Azure Media Services, i clienti possono controllare la crittografia utilizzata. Ad esempio, un cliente potrebbe applicare la crittografia di archiviazione di Azure Media Services (AES 256) a un asset multimediale di alto valore prima di caricare lo spazio di archiviazione BLOB di Azure.)

Azure Media Services genera anche un'anteprima del video, che trasmette insieme ai metadati delle anteprime a SharePoint Online tramite un canale crittografato.
