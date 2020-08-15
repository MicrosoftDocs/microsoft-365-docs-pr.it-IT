---
title: Microsoft 365 principi fondamentali della difesa contro gli attacchi Denial of Service
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
description: In che modo Microsoft utilizza i principi fondamentali dell'assorbimento, del rilevamento e dell'attenuazione in difesa degli attacchi DoS (Denial of Service).
ms.openlocfilehash: b04ec717f7c97e44c6ed4011156666e8c27f06c0
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691155"
---
# <a name="core-principles-of-defense-against-denial-of-service-attacks"></a>Principi fondamentali della difesa contro gli attacchi Denial of Service

I tre principi fondamentali per la difesa dagli attacchi DoS basati sulla rete sono assorbimento, rilevamento e attenuazione. L'assorbimento avviene prima del rilevamento e il rilevamento avviene prima dell'attenuazione. L'assorbimento è la migliore difesa rispetto a un attacco DoS. Se non è possibile rilevare l'attacco, non può essere attenuato. Tuttavia, se non è possibile assorbire anche il più piccolo attacco DoS, i servizi non sopravvivranno abbastanza a lungo per rilevare l'attacco.

Per la maggior parte delle organizzazioni non è economicamente possibile acquistare la capacità in eccesso per assorbire gli attacchi DoS, poiché ciò richiede un notevole investimento in tecnologia e competenze tecniche. Questo evidenzia uno dei vantaggi per la sicurezza dell'utilizzo dei servizi cloud Microsoft. La scalabilità dei servizi Microsoft garantisce una forte protezione della rete per i clienti cloud in modo economico. Tuttavia, anche su vasta scala, è necessario un bilanciamento tra assorbimento, rilevamento e attenuazione. Per trovare questo bilanciamento, Microsoft studia i tassi di crescita degli attacchi per valutare la quantità di risorse che Microsoft deve assorbire.

Il rilevamento è un gioco Cat-and-mouse. È necessario cercare continuamente nuovi modi in cui gli utenti sono in attacco e tentano di sconfiggere i sistemi. Detect-> mitigate-> Detect-> attenuare e così via, è uno stato perpetuo persistente che continua all'infinito.

## <a name="defending-against-dos-attacks"></a>Difesa dagli attacchi DoS

Per difendersi correttamente da un attacco DoS, è essenziale il rilevamento precoce. Se si rileva un attacco prima che il sistema venga sovraccaricato, i difensori possono eseguire un piano di risposta.

La formula seguente consente di approssimare il tempo necessario per l'impatto di un attacco DoS:

   **Capacità massima (in byte/sec)/frequenza di crescita (in byte/sec) = tempo di impatto (in sec)**

Se il time-to-Detection si verifica dopo il periodo di impatto, è probabile che l'attacco DoS avrà esito positivo. Se il tempo di rilevamento si verifica prima del tempo di impatto, i servizi assaliti dovrebbero rimanere online e accessibili se si utilizzano le strategie di attenuazione. Pertanto, esistono solo due operazioni che è possibile eseguire per difendersi dagli attacchi DoS:

- Aumentare la capacità di innalzamento del limite massimo di capacità (che a sua volta fornisce più tempo per rilevare un attacco); o
- Consente di ridurre il tempo necessario per il rilevamento.

Aumentare la capacità ha un impatto fiscale diretto. Microsoft consiglia ai clienti di sviluppare almeno la capacità di assorbimento di base per garantire che possano sopravvivere a un certo livello di attacco DoS. La capacità effettiva di assorbimento varia da cliente a cliente, in quanto ogni cliente ha le proprie soglie per l'esposizione, il rischio e l'esborso finanziario. Per motivi economici, gli investimenti nella ricerca e nel tempo per i modi per ridurre il tempo di rilevamento sono di solito la difesa più conveniente.
