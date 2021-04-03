---
title: Informazioni dettagliate sul dashboard - gestione delle minacce e delle vulnerabilità
description: Il dashboard di gestione delle minacce e delle vulnerabilità può aiutare SecOps e gli amministratori della sicurezza a risolvere le minacce alla sicurezza informatica e a creare la resilienza della sicurezza dell'organizzazione.
keywords: mdatp-tvm, dashboard mdatp-tvm, gestione delle vulnerabilità & delle minacce, gestione delle minacce e delle vulnerabilità, gestione delle minacce basate sul rischio & vulnerabilità, configurazione della sicurezza, Punteggio microsoft sicuro per i dispositivi, punteggio di esposizione
search.appverid: met150
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 35dd300d828bfa48ad753d7c65f36b2555cf4f60
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500179"
---
# <a name="dashboard-insights---threat-and-vulnerability-management"></a>Informazioni dettagliate sul dashboard - gestione delle minacce e delle vulnerabilità

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**

- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Gestione di minacce e vulnerabilità](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

La gestione delle minacce e delle vulnerabilità è un componente di Defender for Endpoint e fornisce agli amministratori della sicurezza e ai team delle operazioni di sicurezza un valore univoco, tra cui:


- Informazioni sul rilevamento di endpoint in tempo reale e relativa risposta (EDR) correlate alle vulnerabilità degli endpoint
- Contesto di vulnerabilità del dispositivo prezioso durante indagini su eventi imprevisti
- Processi di correzione incorporati tramite Microsoft Intune e Microsoft Endpoint Configuration Manager  
  
Puoi usare la funzionalità di gestione delle minacce e delle vulnerabilità in [Microsoft Defender Security Center](https://securitycenter.windows.com/) per:

- Visualizzare il punteggio di esposizione e microsoft secure score per i dispositivi, insieme ai principali consigli per la sicurezza, vulnerabilità software, attività di correzione e dispositivi esposti
- Correlare le informazioni edR con le vulnerabilità degli endpoint ed elaborarle
- Selezionare le opzioni di correzione per eseguire il triage e tenere traccia delle attività di correzione
- Selezionare le opzioni di eccezione e tenere traccia delle eccezioni attive

> [!NOTE]
> I dispositivi che non sono attivi negli ultimi 30 giorni non vengono utilizzati nei dati che riflettono il punteggio di esposizione alla gestione delle minacce e delle vulnerabilità dell'organizzazione e il punteggio microsoft secure per i dispositivi.

Guarda questo video per una breve panoramica di ciò che si trova nel dashboard di gestione delle minacce e delle vulnerabilità.

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r1nv]

## <a name="threat-and-vulnerability-management-dashboard"></a>Dashboard di gestione delle minacce e delle vulnerabilità

 ![Portale di Microsoft Defender per endpoint](images/tvm-dashboard-devices.png)

Area | Descrizione
:---|:---
**Gruppi di dispositivi selezionati (#/#)**   | Filtra i dati di gestione delle minacce e delle vulnerabilità che vuoi visualizzare nel dashboard e nelle schede in base ai gruppi di dispositivi. Ciò che si seleziona nel filtro si applica in tutte le pagine di gestione delle minacce e delle vulnerabilità.
[**Punteggio di esposizione.**](tvm-exposure-score.md)   | Visualizzare lo stato corrente dell'esposizione dei dispositivi dell'organizzazione a minacce e vulnerabilità. Diversi fattori influiscono sul punteggio di esposizione dell'organizzazione: punti deboli rilevati nei dispositivi, probabilità che i dispositivi siano violati, valore dei dispositivi per l'organizzazione e avvisi pertinenti rilevati con i dispositivi. L'obiettivo è ridurre il punteggio di esposizione dell'organizzazione per essere più sicuro. Per ridurre il punteggio, è necessario correggere i problemi di configurazione della sicurezza correlati elencati nei suggerimenti per la sicurezza.
[**Punteggio di sicurezza Microsoft per dispositivi**](tvm-microsoft-secure-score-devices.md) | Vedere la sicurezza del sistema operativo, delle applicazioni, della rete, degli account e dei controlli di sicurezza dell'organizzazione. L'obiettivo è correggere i problemi di configurazione della sicurezza correlati per aumentare il punteggio per i dispositivi. Selezionando le barre verrà visualizzata la **pagina Suggerimenti per la** sicurezza.
**Distribuzione dell'esposizione dei dispositivi** | Scopri quanti dispositivi vengono esposti in base al livello di esposizione. Selezionare una sezione nel grafico ad  anello per passare alla pagina elenco Dispositivi e visualizzare i nomi dei dispositivi interessati, il livello di esposizione, il livello di rischio e altri dettagli, ad esempio dominio, piattaforma del sistema operativo, stato di integrità, data dell'ultima visualizzazione e tag.
**Principali suggerimenti per la sicurezza** | Vedere i consigli sulla sicurezza fascicolati ordinati e classificati in base all'esposizione ai rischi dell'organizzazione e all'urgenza necessaria. Selezionare **Mostra altro** per visualizzare il resto degli elementi consigliati per la sicurezza nell'elenco. Selezionare **Mostra eccezioni per** l'elenco dei suggerimenti che hanno un'eccezione.
**Software più vulnerabile** | Ottieni visibilità in tempo reale nell'inventario software dell'organizzazione con un elenco in pila di software vulnerabile installato nei dispositivi della rete e il loro impatto sul punteggio di esposizione dell'organizzazione. Seleziona un elemento per i dettagli o **Mostra altro** per visualizzare il resto dell'elenco dei software vulnerabili nella **pagina Inventario** software.
**Principali attività di correzione** | Tenere traccia delle attività di correzione generate dagli elementi consigliati per la sicurezza. È possibile selezionare ogni elemento nell'elenco  per visualizzare i  dettagli nella pagina Correzione o selezionare Mostra altro per visualizzare il resto delle attività di correzione e le eccezioni attive.
**Principali dispositivi esposti** | Visualizzare i nomi dei dispositivi esposti e il relativo livello di esposizione. Selezionare un nome di dispositivo dall'elenco per passare alla pagina del dispositivo in cui è possibile visualizzare gli avvisi, i rischi, gli incidenti, i suggerimenti per la sicurezza, il software installato e le vulnerabilità individuate associate ai dispositivi esposti. Seleziona **Mostra altro** per visualizzare il resto dell'elenco dei dispositivi esposti. Dall'elenco dei dispositivi puoi gestire i tag, avviare indagini automatizzate, avviare una sessione di risposta in tempo reale, raccogliere un pacchetto di indagine, eseguire l'analisi antivirus, limitare l'esecuzione delle app e isolare il dispositivo.

Per altre informazioni sulle icone usate in tutto il portale, vedi [Icone di Microsoft Defender for Endpoint.](portal-overview.md#microsoft-defender-for-endpoint-icons)


## <a name="related-topics"></a>Argomenti correlati

- [Panoramica della gestione delle minacce e delle vulnerabilità](next-gen-threat-and-vuln-mgt.md)
- [Punteggio di esposizione.](tvm-exposure-score.md)
- [Punteggio di sicurezza Microsoft per dispositivi](tvm-microsoft-secure-score-devices.md)
- [Consigli sulla sicurezza](tvm-security-recommendation.md)
- [Inventario software](tvm-software-inventory.md)
- [Sequenza temporale eventi](threat-and-vuln-mgt-event-timeline.md)

