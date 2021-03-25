---
title: Scenari e opportunità per i partner di Microsoft Defender ATP
ms.reviewer: ''
description: Scopri come puoi estendere le offerte di sicurezza esistenti oltre al framework aperto e a un ricco set di API per creare estensioni e integrazioni con Microsoft Defender ATP
keywords: API, partner, estendere, open framework, api, estensioni, integrazioni, rilevamento, gestione, risposta, vulnerabilità, intelligence
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 1db82afa06fd0b6b3d7228aaf3020c5496ed69e7
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186894"
---
# <a name="microsoft-defender-for-endpoint-partner-opportunities-and-scenarios"></a>Scenari e opportunità per i partner di Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


I partner possono estendere facilmente le offerte di sicurezza esistenti oltre al framework aperto e a un set completo e completo di API per creare estensioni e integrazioni con Defender for Endpoint. 

Le API si estendono su aree funzionali, tra cui rilevamento, gestione, risposta, vulnerabilità e un'ampia gamma di casi d'uso a livello di intelligence. In base al caso d'uso e alle necessità, i partner possono trasmettere o eseguire query sui dati da Defender per Endpoint. 


## <a name="scenario-1-external-alert-correlation-and-automated-investigation-and-remediation"></a>Scenario 1: correlazione degli avvisi esterni e analisi e correzione automatizzate
Defender for Endpoint offre funzionalità di analisi e correzione automatizzate uniche per guidare la risposta agli incidenti su larga scala. 

L'integrazione della funzionalità di analisi e risposta automatizzata con altre soluzioni, ad esempio prodotti di sicurezza di rete o altri prodotti per la sicurezza degli endpoint, aiuterà a risolvere gli avvisi. L'integrazione riduce al minimo anche le complessità che circondano la correlazione del segnale di rete e del dispositivo, snellendo in modo efficace le azioni di indagine e correzione delle minacce nei dispositivi.

Defender for Endpoint aggiunge il supporto per questo scenario nei moduli seguenti:

- Gli avvisi esterni possono essere inseriti in Defender per Endpoint e presentati affiancati a avvisi aggiuntivi basati su dispositivo da Defender per Endpoint. Questa visualizzazione fornisce il contesto completo dell'avviso, con il processo reale e la storia completa dell'attacco.

- Una volta generato un avviso, il segnale viene condiviso tra tutti gli endpoint protetti da Defender per Endpoint nell'organizzazione. Defender for Endpoint richiede una risposta immediata automatizzata o assistita dall'operatore per risolvere l'avviso.

## <a name="scenario-2-security-orchestration-and-automation-response-soar-integration"></a>Scenario 2: integrazione dell'orchestrazione della sicurezza e della risposta di automazione (SOAR)
Le soluzioni di orchestrazione possono aiutare a creare playbook e integrare il modello di dati rtf e le azioni che le API di Defender for Endpoint espongono per orchestrare le risposte, ad esempio query per i dati del dispositivo, attivare l'isolamento del dispositivo, bloccare/consentire, risolvere gli avvisi e altri.

## <a name="scenario-3-indicators-matching"></a>Scenario 3: corrispondenza degli indicatori 
La corrispondenza degli indicatori di compromissione (IoC) è una funzionalità essenziale in ogni soluzione di protezione degli endpoint. Questa funzionalità è disponibile in Defender for Endpoint e consente di impostare un elenco di indicatori per la prevenzione, il rilevamento e l'esclusione delle entità. È possibile definire l'azione da eseguire e la durata per l'applicazione dell'azione.

Gli scenari precedenti fungono da esempi di estendibilità della piattaforma. Non sei limitato agli esempi e ti invitiamo sicuramente a sfruttare il framework aperto per individuare ed esplorare altri scenari.

Segui i passaggi descritti in [Diventare un partner Microsoft Defender for Endpoint per](get-started-partner-integration.md) integrare la soluzione in Defender for Endpoint.

## <a name="related-topic"></a>Argomento correlato
- [Panoramica della gestione e delle API](management-apis.md)
