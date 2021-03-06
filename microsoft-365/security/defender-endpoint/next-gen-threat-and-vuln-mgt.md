---
title: Gestione di minacce e vulnerabilità
description: Questa nuova funzionalità usa un approccio basato sul rischio che cambia il gioco per l'individuazione, la definizione delle priorità e la correzione delle vulnerabilità degli endpoint e delle configurazioni erre.
keywords: threat & gestione delle vulnerabilità, gestione di minacce e vulnerabilità, Microsoft Defender for Endpoint TVM, Microsoft Defender for Endpoint-TVM, gestione delle vulnerabilità, valutazione delle vulnerabilità, analisi delle minacce e vulnerabilità, valutazione della configurazione sicura, Microsoft Defender for Endpoint, vulnerabilità degli endpoint, generazione successiva
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: overview
ms.technology: mde
ms.openlocfilehash: 474b8f032d32668eaea3a477da013c2b8e74019b
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934166"
---
# <a name="threat-and-vulnerability-management"></a>Gestione di minacce e vulnerabilità

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

Identificare, valutare e correggere in modo efficace i punti deboli degli endpoint è fondamentale per eseguire un programma di sicurezza sano e ridurre i rischi dell'organizzazione. La gestione di minacce e vulnerabilità funge da infrastruttura per la riduzione dell'esposizione dell'organizzazione, l'ingrandimento della superficie degli endpoint e l'aumento della resilienza organizzativa.

Individuare le vulnerabilità e le configurazioni erre in tempo reale con i sensori e senza la necessità di agenti o analisi periodiche. Assegna la priorità alle vulnerabilità in base al panorama delle minacce, ai rilevamenti nell'organizzazione, alle informazioni riservate sui dispositivi vulnerabili e al contesto aziendale.

Guarda questo video per una breve panoramica di gestione di minacce e vulnerabilità.

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4mLsn]

## <a name="bridging-the-workflow-gaps"></a>Colmare le lacune del flusso di lavoro

Minacce e gestione delle vulnerabilità sono integrate, in tempo reale e basate sul cloud. È completamente integrato con lo stack di sicurezza degli endpoint Microsoft, il Graph Microsoft Intelligent Security e la knowledge base di analisi delle applicazioni.  

La gestione delle vulnerabilità è la prima soluzione nel settore a colmare il divario tra l'amministrazione della sicurezza e l'amministrazione IT durante il processo di correzione. Crea un'attività o un ticket di sicurezza integrando con Microsoft Intune e Microsoft Endpoint Configuration Manager.

### <a name="real-time-discovery"></a>Individuazione in tempo reale

Per individuare le vulnerabilità degli endpoint e la configurazione errata, gestione di minacce e vulnerabilità usa lo stesso defender incorporato senza agenti per i sensori endpoint per ridurre le analisi di rete ingombranti e il sovraccarico IT.

Fornisce inoltre:

- **Inventario dei dispositivi in tempo reale:** i dispositivi onboarded in Defender for Endpoint segnalano e inviano automaticamente i dati di configurazione della sicurezza e delle vulnerabilità nel dashboard.
- **Visibilità del software e delle** vulnerabilità - Ottica nell'inventario software dell'organizzazione e modifiche software come installazioni, disinstallazioni e patch. Le vulnerabilità individuate di recente vengono segnalate con consigli di mitigazione utilizzabili per le applicazioni di prima e terza parte.
- **Contesto di runtime dell'applicazione** - Visibilità sui modelli di utilizzo delle applicazioni per una definizione di priorità e un processo decisionale migliori.
- **Configurazione postura** - Visibilità nella configurazione della sicurezza dell'organizzazione o configurazioni erre. I problemi vengono segnalati nel dashboard con consigli sulla sicurezza utilizzabili.

### <a name="intelligence-driven-prioritization"></a>Definizione delle priorità basata sull'intelligence

Minacce e gestione delle vulnerabilità aiuta i clienti a definire le priorità e a concentrarsi sui punti di debolezza che rappresentano il rischio più urgente e più alto per l'organizzazione. Unisce i suggerimenti per la sicurezza con le minacce dinamiche e il contesto aziendale:

- **Esposizione di attacchi emergenti in modalità selvaggia-** Allinea dinamicamente la definizione di priorità dei suggerimenti sulla sicurezza. Threat and gestione delle vulnerabilità si concentra sulle vulnerabilità attualmente sfruttate nelle minacce selvagge ed emergenti che rappresentano il rischio più alto.
- **Pinpointing active breaches** - Correla le informazioni gestione di minacce e vulnerabilità e EDR per dare priorità alle vulnerabilità sfruttate in una violazione attiva all'interno dell'organizzazione.
- **Protezione di asset di alto valore-** Identificare i dispositivi esposti con applicazioni business-critical, dati riservati o utenti di alto valore.

### <a name="seamless-remediation"></a>Correzione senza problemi

Threat and gestione delle vulnerabilità consente agli amministratori della sicurezza e agli amministratori IT di collaborare senza problemi per risolvere i problemi.

- **Richieste di correzione inviate all'IT** - Creare un'attività di correzione in Microsoft Intune da un suggerimento di sicurezza specifico. Microsoft prevede di espandere questa funzionalità ad altre piattaforme di gestione della sicurezza IT.
- **Mitigazioni alternative:** ottenere informazioni dettagliate su ulteriori mitigazioni, ad esempio modifiche alla configurazione che possono ridurre i rischi associati alle vulnerabilità del software.
- **Stato di correzione in tempo reale** - Monitoraggio in tempo reale dello stato e dello stato delle attività di correzione nell'organizzazione.

## <a name="threat-and-vulnerability-management-walk-through"></a>Minacce e gestione delle vulnerabilità walk-through

Guarda questo video per una panoramica completa di gestione di minacce e vulnerabilità.

>[!VIDEO https://aka.ms/MDATP-TVM-Interactive-Guide]

## <a name="navigation-pane"></a>Riquadro di spostamento 

Area | Descrizione
:---|:---
**Dashboard**   | Ottieni una visualizzazione di alto livello del punteggio di esposizione dell'organizzazione, Microsoft Secure Score for Devices, distribuzione dell'esposizione dei dispositivi, consigli di sicurezza principali, software più vulnerabile, attività di correzione principali e dati dei dispositivi più esposti.
[**Consigli sulla sicurezza**](tvm-security-recommendation.md) | Vedi l'elenco dei suggerimenti per la sicurezza e informazioni sulle minacce correlate. Quando si seleziona un elemento dall'elenco, viene aperto un riquadro a comparsa con i dettagli della vulnerabilità, un collegamento per aprire la pagina del software e le opzioni di correzione e eccezione. Puoi anche aprire un ticket in Intune se i dispositivi vengono aggiunti tramite Azure Active Directory e hai abilitato le connessioni intune in Defender for Endpoint.
[**Correzione**](tvm-remediation.md) | Vedi le attività di correzione create e le eccezioni di raccomandazione.
[**Inventario software**](tvm-software-inventory.md) | Vedi l'elenco dei software vulnerabili nell'organizzazione, insieme alle informazioni sulla debolezza e sulle minacce.
[**Punti deboli**](tvm-weaknesses.md) | Vedi l'elenco delle vulnerabilità ed esposizioni comuni (CVE) nell'organizzazione.
[**Sequenza temporale eventi**](threat-and-vuln-mgt-event-timeline.md) | Visualizzare gli eventi che possono influire sui rischi dell'organizzazione.

## <a name="apis"></a>API

Esegui gestione di minacce e vulnerabilità api correlate per automatizzare i flussi gestione delle vulnerabilità flussi di lavoro. Per ulteriori informazioni, vedere questo [post di blog di Microsoft Tech Community](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/threat-amp-vulnerability-management-apis-are-now-generally/ba-p/1304615).

Vedi gli articoli seguenti per le API correlate:

- [Accedere a API di Microsoft Defender per endpoint](exposed-apis-list.md)
- [API del computer](machine.md)
- [API di raccomandazione](vulnerability.md)
- [API punteggio](score.md)
- [API software](software.md)
- [API di vulnerabilità](vulnerability.md)
- [Elencare le vulnerabilità per computer e software](get-all-vulnerabilities-by-machines.md)

## <a name="see-also"></a>Vedere anche

- [Sistemi operativi e piattaforme supportati](tvm-supported-os.md)
- [Dashboard delle minacce gestione delle vulnerabilità sicurezza](tvm-dashboard-insights.md)
- [BLOG: Microsoft Threat & Vulnerability Management aiuta ora migliaia di clienti a individuare, definire le priorità e correggere le vulnerabilità in tempo reale](https://www.microsoft.com/security/blog/2019/07/02/microsofts-threat-vulnerability-management-now-helps-thousands-of-customers-to-discover-prioritize-and-remediate-vulnerabilities-in-real-time/)
