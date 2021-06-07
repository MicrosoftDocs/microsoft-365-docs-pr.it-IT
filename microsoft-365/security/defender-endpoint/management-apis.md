---
title: Panoramica di gestione e API
ms.reviewer: ''
description: Informazioni sugli strumenti di gestione e sulle categorie di API in Microsoft Defender for Endpoint
keywords: onboarding, api, siem, rbac, accesso, portale, integrazione, indagine, risposta, entità, entità, contesto utente, contesto dell'applicazione, streaming
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
ms.openlocfilehash: 34fb58c2e32f69cda064bb6db4b180c78ba5d451
ms.sourcegitcommit: f0118e61e490496cb23189cc5c73b23e2ba939be
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/05/2021
ms.locfileid: "52780154"
---
# <a name="overview-of-management-and-apis"></a>Panoramica di gestione e API 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mgt-apis-abovefoldlink)


Defender for Endpoint supporta un'ampia gamma di opzioni per garantire che i clienti possano adottare facilmente la piattaforma. 

Riconoscendo che gli ambienti e le strutture dei clienti possono variare, Defender for Endpoint è stato creato con flessibilità e controllo granulare per soddisfare le diverse esigenze dei clienti. 

## <a name="endpoint-onboarding-and-portal-access"></a>Onboarding degli endpoint e accesso al portale 

L'onboarding dei dispositivi è completamente integrato in Microsoft Endpoint Manager e Microsoft Intune per i dispositivi client e Azure Defender per i dispositivi server, offrendo un'esperienza end-to-end completa di configurazione, distribuzione e monitoraggio. Inoltre, Microsoft Defender for Endpoint supporta Criteri di gruppo e altri strumenti di terze parti usati per la gestione dei dispositivi.

Defender for Endpoint offre un controllo specifico su ciò che gli utenti con accesso al portale possono vedere e fare attraverso la flessibilità del controllo degli accessi in base ai ruoli (RBAC). Il modello RBAC supporta tutte le funzionalità della struttura dei team di sicurezza:
- Organizzazioni e team di sicurezza distribuiti a livello globale
- Team per le operazioni di sicurezza dei modelli a più livelli
- Divisioni completamente segregate con singoli team di gestione centralizzata della sicurezza globale 

## <a name="available-apis"></a>API disponibili
La soluzione Microsoft Defender for Endpoint si basa su una piattaforma pronta per l'integrazione.

Defender for Endpoint espone gran parte dei dati e delle azioni tramite un set di API programmatiche. Queste API ti consentiranno di automatizzare i flussi di lavoro e innovare in base alle funzionalità di Defender for Endpoint.

![Immagine dell'API e dell'integrazione disponibili in Microsoft Defender for Endpoint](images/mdatp-apis.png)  

Le API defender per endpoint possono essere raggruppate in tre:
- API di Microsoft Defender per endpoint 
- API di streaming di dati non elaborati
- Integrazione SIEM

## <a name="microsoft-defender-for-endpoint-apis"></a>API di Microsoft Defender per endpoint

Defender for Endpoint offre un modello API a più livelli che espone dati e funzionalità in un modello strutturato, chiaro e facile da usare, esposto tramite un modello di autenticazione e autorizzazione standard basato su Azure AD che consente l'accesso nel contesto di utenti o applicazioni SaaS. Il modello API è stato progettato per esporre entità e funzionalità in un formato coerente. 

Guarda questo video per una breve panoramica delle API di Defender for Endpoint. 
>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4d73M]

**L'API** investigation espone la ricchezza di Defender per Endpoint, ovvero l'esposizione di entità calcolate o "profilate" (ad esempio, dispositivo, utente e file) ed eventi discreti (ad esempio, la creazione di processi e la creazione di file) che in genere descrivono un comportamento correlato a un'entità, consentendo l'accesso ai dati tramite interfacce di indagine che consentono l'accesso basato su query ai dati. Per altre informazioni, vedi [API supportate.](exposed-apis-list.md)

**L'API** di risposta espone la possibilità di eseguire azioni nel servizio e nei dispositivi, consentendo ai clienti di inserire indicatori, gestire le impostazioni, lo stato degli avvisi, nonché eseguire azioni di risposta su dispositivi a livello di programmazione, ad esempio isolare i dispositivi dalla rete, i file di quarantena e altri. 

## <a name="raw-data-streaming-api"></a>API di streaming di dati non elaborati 
Defender for Endpoint raw data streaming API offre ai clienti la possibilità di spedire eventi e avvisi in tempo reale dalle loro istanze quando si verificano all'interno di un singolo flusso di dati, fornendo un meccanismo di recapito a bassa latenza e velocità effettiva elevata.

Le informazioni sull'evento Defender for Endpoint vengono spinte direttamente nell'archiviazione di Azure per la conservazione dei dati a lungo termine o in Hub eventi di Azure per l'utilizzo da parte di servizi di visualizzazione o motori di elaborazione dati aggiuntivi. 

Per altre informazioni, vedi [API di streaming di dati non elaborati.](raw-data-export.md)

La nuova API Microsoft 365 Defender Streaming include eventi di posta elettronica e di avviso oltre agli eventi del dispositivo. Per altre informazioni, vedi [Microsoft 365 Defender Streaming API.](../defender/streaming-api.md)


## <a name="siem-api"></a>SIEM API
Quando abiliti l'integrazione delle informazioni di sicurezza e della gestione degli eventi (SIEM), ti consente di estrarre i rilevamenti da Microsoft Defender Security Center usando la soluzione SIEM o connettendoti direttamente all'API REST dei rilevamenti. In questo modo viene attivata la sezione dei dettagli di accesso al connettore SIEM con valori precompilato e viene creata un'applicazione nel tenant di Azure Active Directory (Azure AD). Per ulteriori informazioni, vedere [Integrazione SIEM.](enable-siem-integration.md)

## <a name="related-topics"></a>Argomenti correlati
- [Accedere alle API di Microsoft Defender for Endpoint ](apis-intro.md)
- [API supportate](exposed-apis-list.md)
- [Opportunità tecniche per i partner](partner-integration.md)

