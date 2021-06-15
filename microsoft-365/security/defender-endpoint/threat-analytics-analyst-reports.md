---
title: Informazioni sulla sezione relativa al report degli analisti nell'analisi delle minacce.
ms.reviewer: ''
description: Come la sezione report dei report di analisi delle minacce fornisce informazioni su minacce, mitigazione, rilevamenti, query di ricerca avanzate e altro ancora.
keywords: report degli analisti, analisi delle minacce, rilevamenti, query di ricerca avanzate, mitigazioni,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: e791249418503ada5d98b74c8ae273664851cc8e
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926440"
---
# <a name="the-analyst-report-in-threat-analytics"></a>Report degli analisti nell'analisi delle minacce

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Ogni [report di analisi delle minacce](threat-analytics.md) include sezioni dinamiche e una sezione scritta completa denominata report degli _analisti._ Per accedere a questa sezione, aprire il report sulla minaccia rilevata e selezionare la scheda **Report analista.**

![Immagine della sezione del report degli analisti di un report di analisi delle minacce](images/ta-analyst-report-small.png)

_Sezione del report degli analisti di un report di analisi delle minacce_

## <a name="scan-the-analyst-report"></a>Analizzare il report degli analisti 
Ogni sezione del report degli analisti è progettata per fornire informazioni utili. Sebbene i report varino, la maggior parte dei report include le sezioni descritte nella tabella seguente.

| Sezione Report | Descrizione |
|--|--|
| Riepilogo esecutivo | Panoramica della minaccia, incluso il momento in cui è stata vista per la prima volta, le motivazioni, gli eventi importanti, gli obiettivi principali e strumenti e tecniche distinti. È possibile utilizzare queste informazioni per valutare ulteriormente come definire la priorità della minaccia nel contesto del settore, della posizione geografica e della rete. |
| Analisi | Informazioni tecniche sulle minacce, inclusi i dettagli di un attacco e il modo in cui gli utenti malintenzionati potrebbero utilizzare una nuova tecnica o una nuova superficie di attacco | 
| MiTRE ATT&CK osservate | Come vengono mappate le tecniche osservate al framework di attacco [MITRE ATT&CK](https://attack.mitre.org/) | 
| [Mitigazioni](#apply-additional-mitigations) | Consigli che possono arrestare o ridurre l'impatto della minaccia. Questa sezione include anche le mitigazioni che non vengono rilevate in modo dinamico come parte del report di analisi delle minacce. |
| [Dettagli rilevamento](#understand-how-each-threat-can-be-detected) | Rilevamenti specifici e generici forniti da soluzioni di sicurezza Microsoft che possono visualizzare attività o componenti associati alla minaccia. | 
| [Rilevazione avanzata](#find-subtle-threat-artifacts-using-advanced-hunting) | [Query di ricerca avanzate per](advanced-hunting-overview.md) identificare in modo proattivo le possibili attività di minaccia. La maggior parte delle query viene fornita per integrare i rilevamenti, in particolare per individuare componenti o comportamenti potenzialmente dannosi che non possono essere valutati in modo dinamico come dannosi. | 
| Riferimenti | Pubblicazioni Microsoft e di terze parti a cui fanno riferimento gli analisti durante la creazione del report. Il contenuto dell'analisi delle minacce si basa sui dati convalidati dai ricercatori Microsoft. Le informazioni provenienti da fonti di terze parti disponibili pubblicamente sono chiaramente identificate come tali. | 
| Log delle modifiche | Il momento in cui il report è stato pubblicato e quando sono state apportate modifiche significative al report. |

## <a name="apply-additional-mitigations"></a>Applicare misure di prevenzione aggiuntive
L'analisi delle minacce tiene traccia [dinamicamente dello stato degli aggiornamenti della sicurezza e delle configurazioni sicure.](threat-analytics.md#mitigations-review-list-of-mitigations-and-the-status-of-your-devices) Queste informazioni sono disponibili come grafici e tabelle nella **scheda Mitigazioni.**

Oltre a queste mitigazioni monitorate, il report degli analisti illustra anche le mitigazioni non _monitorate_ in modo dinamico. Ecco alcuni esempi di mitigazioni importanti che non vengono rilevate in modo dinamico:

- Bloccare i messaggi di posta elettronica con allegati con estensione _lnk_ o altri tipi di file sospetti
- Randomizzare le password dell'amministratore locale
- Informare gli utenti finali della posta elettronica di phishing e di altri vettori di minacce
- Attivare regole specifiche [di riduzione della superficie di attacco](attack-surface-reduction.md)

Sebbene sia possibile utilizzare la scheda **Mitigazioni** per valutare la posizione della sicurezza rispetto a una minaccia, questi suggerimenti consentono di adottare ulteriori misure per migliorare la propria posizione di sicurezza. Leggere attentamente tutte le indicazioni di mitigazione nel report degli analisti e applicarle quando possibile.

## <a name="understand-how-each-threat-can-be-detected"></a>Comprendere in che modo ogni minaccia può essere rilevata
Il report degli analisti fornisce anche i rilevamenti dalle funzionalità antivirus e di risposta _(EDR)_ di Microsoft Defender for Endpoint.

### <a name="antivirus-detections"></a>Rilevamenti antivirus
Questi rilevamenti sono disponibili nei dispositivi con [Antivirus Microsoft Defender](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) attivato. Quando questi rilevamenti si verificano nei dispositivi che sono stati onboarded in Microsoft Defender for Endpoint, attivano anche avvisi che illuminano i grafici nel report.

>[!NOTE]
>Nel report degli analisti sono inoltre elencati i rilevamenti **generici** in grado di identificare un'ampia gamma di minacce, oltre a componenti o comportamenti specifici della minaccia monitorata. Questi rilevamenti generici non si riflettono nei grafici.

### <a name="endpoint-detection-and-response-edr-alerts"></a>Avvisi di rilevamento e risposta degli endpoint (EDR)
EDR avvisi vengono generati per [i dispositivi onboarded in Microsoft Defender per Endpoint.](onboard-configure.md) Questi avvisi in genere si basano sui segnali di sicurezza raccolti dal sensore Microsoft Defender for Endpoint e su altre funzionalità degli endpoint, ad esempio antivirus, protezione di rete, protezione dalle manomissioni, che fungono da potenti origini del segnale.

Come l'elenco dei rilevamenti antivirus, alcuni avvisi EDR sono progettati per contrassegnare genericamente comportamenti sospetti che potrebbero non essere associati alla minaccia rilevata. In questi casi, il report identificherà chiaramente l'avviso come "generico" e non influirà su alcun grafico nel report.

## <a name="find-subtle-threat-artifacts-using-advanced-hunting"></a>Trovare artefatti di minacce sottili con la ricerca avanzata
Sebbene i rilevamenti consentano di identificare e arrestare automaticamente la minaccia rilevata, molte attività di attacco lasciano tracce sottili che richiedono un'ispezione aggiuntiva. Alcune attività di attacco presentano comportamenti che possono anche essere normali, quindi rilevarle in modo dinamico può causare rumori operativi o anche falsi positivi.

[La ricerca avanzata](advanced-hunting-overview.md) offre un'interfaccia di query basata su Kusto Query Language che semplifica l'individuazione di indicatori sottili dell'attività di minaccia. Consente inoltre di visualizzare informazioni contestuali e verificare se gli indicatori sono connessi a una minaccia.

Le query di ricerca avanzate nei report degli analisti sono state controllati dagli analisti Microsoft e sono pronti per l'esecuzione nell'editor di [query di ricerca avanzata.](https://securitycenter.windows.com/advanced-hunting) È inoltre possibile utilizzare le query per creare regole [di rilevamento personalizzate che](custom-detection-rules.md) attivano avvisi per corrispondenze future.


## <a name="related-topics"></a>Argomenti correlati
- [Panoramica dell'analisi delle minacce](threat-analytics.md)
- [Trovare in modo proattivo le minacce con la ricerca avanzata](advanced-hunting-overview.md) 
- [Regole di rilevamento personalizzate](custom-detection-rules.md)