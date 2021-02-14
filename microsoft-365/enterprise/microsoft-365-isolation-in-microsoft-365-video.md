---
title: Isolamento del tenant in Office 365 Video
ms.author: robmazz
author: robmazz
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
description: In questo articolo, trovare una spiegazione di come l'isolamento del tenant mantiene separati i video archiviati di ogni tenant in Office 365 Video.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 626a995fc5a3ac971c48cc87bec1017134e87b88
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332245"
---
# <a name="tenant-isolation-in-office-365-video"></a>Isolamento del tenant in Office 365 Video

> [!NOTE]
> Office 365 Video verrà sostituito da Microsoft Stream. Per ulteriori informazioni sul nuovo servizio video aziendale che aggiunge intelligence alla collaborazione video e sui piani di transizione per gli attuali clienti di Microsoft 365 Video, vedere Panoramica della transizione di [Office 365 Video](https://docs.microsoft.com/stream/migrate-from-office-365)a Microsoft Stream.

## <a name="introduction"></a>Introduzione

Archiviazione di Azure viene usata per archiviare i dati per più servizi di Office 365, tra cui Office 365 Video e Sway. L'archiviazione di Azure include l'archiviazione BLOB, un archivio oggetti cloud altamente scalabile basato su REST usato per l'archiviazione di dati non strutturati. Archiviazione di Azure usa un modello di controllo di accesso semplice; ogni sottoscrizione di Azure può creare uno o più account di archiviazione. Ogni account di archiviazione dispone di una singola chiave privata utilizzata per controllare l'accesso a tutti i dati in tale account di archiviazione. Questo supporta lo scenario tipico in cui l'archiviazione è associata alle applicazioni e tali applicazioni hanno il controllo completo sui dati associati; ad esempio Sway che archivia il contenuto in Archiviazione di Azure. Tutti i contenuti dei clienti per Sway vengono archiviati in account di archiviazione di Azure condivisi. Il contenuto di ogni utente si trova in un albero di directory separato di BLOB nell'archiviazione di Azure.

I sistemi che gestiscono l'accesso agli ambienti dei clienti (ad esempio, il portale di Azure, SMAPI e così via) sono isolati all'interno di un'applicazione Azure gestita da Microsoft. Ciò separa logicamente l'infrastruttura di accesso dei clienti dalle applicazioni dei clienti e dal livello di archiviazione.

## <a name="tenant-isolation-in-office-365-video"></a>Isolamento del tenant in Office 365 Video

[Office 365 Video](https://support.office.com/article/Meet-Office-365-Video-ca1cc1a9-a615-46e1-b6a3-40dbd99939a6) è un portale aziendale che offre alle organizzazioni una destinazione altamente sicura a livello di organizzazione per l'inserimento, la condivisione e l'individuazione di contenuti video. In Office 365 Video, i video di ogni tenant vengono mantenuti isolati e crittografati in tutte le posizioni e sono disponibili solo per gli utenti autenticati che dispongono di accesso e autorizzazioni per i video dell'organizzazione. Office 365 Video usa una combinazione di tecnologie per ottenere questo risultato:

- SharePoint Online viene utilizzato per archiviare il file video e i metadati (titolo, descrizione e così via). Fornisce inoltre il livello di sicurezza e conformità (inclusa l'autenticazione) e le funzionalità di ricerca.
- Servizi multimediali di Azure offre funzionalità di transcodamento, streaming adattivo, recapito sicuro (con crittografia AES) e funzionalità di anteprima.

[Servizi multimediali di Azure](https://azure.microsoft.com/services/media-services/) è un'offerta platform-as-a-service per l'abilitazione di flussi di lavoro multimediali end-to-end nel cloud. La piattaforma fornisce un'API REST per il caricamento, la codifica, la crittografia (con PlayReady) e la distribuzione di contenuti multimediali tramite data center di Azure in tutto il mondo.

Tutti i caricamenti per Office 365 Video vengono eseguiti tramite HTTPS. Quando un file video viene caricato, viene archiviato in SharePoint Online e una copia del file viene inviata tramite un canale crittografato a Servizi multimediali di Azure. Servizi multimediali di Azure transcodifica il video in più formati ottimizzati per l'esperienza di visualizzazione (ad esempio mobile, larghezza di banda ridotta, larghezza di banda elevata e così via). Questi file, insieme al file originale acquisito durante il caricamento, vengono archiviati nell'archiviazione BLOB di Azure. I file vengono crittografati con AES 128 per l'algoritmo di creazione di pacchetti MPEG Common Encryption (o una versione precedente di PlayReady) per la riproduzione e crittografati con la crittografia di archiviazione AES 256 prima di essere archiviati nell'archiviazione BLOB di Azure. Usando Azure Media Services Client SDK, i clienti possono controllare quale crittografia viene usata. Ad esempio, un cliente potrebbe applicare la crittografia di archiviazione di Servizi multimediali di Azure (AES 256) a un asset multimediale di alto valore prima di caricarlo nell'archiviazione BLOB di Azure.

Servizi multimediali di Azure genera anche un'anteprima per il video, che trasmette insieme ai metadati di anteprima a SharePoint Online tramite un canale crittografato.
