---
title: Informazioni sulla sezione relativa al report dell'analista nell'analisi delle minacce
ms.reviewer: ''
description: Informazioni sulla sezione del report dell'analista di ogni report di analisi delle minacce. Informazioni su come fornisce informazioni su minacce, mitigazioni, rilevamenti, query di ricerca avanzata e altro ancora.
keywords: report dell'analista, analisi delle minacce, rilevamenti, query di ricerca avanzata, mitigazioni,
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
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 650282e0dce49cc392eeb7501f91b3ffed9f0707
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167560"
---
# <a name="understand-the-analyst-report-in-threat-analytics"></a>Informazioni sul report dell'analista nell'analisi delle minacce

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Si applica a:**
- Microsoft 365 Defender

> Si vuole provare Microsoft 365 Defender? È possibile [valutarlo in un ambiente lab o](https://aka.ms/mtp-trial-lab) eseguire il progetto pilota in [produzione.](https://aka.ms/m365d-pilotplaybook)
>

[!INCLUDE [Prerelease](../includes/prerelease.md)]

Ogni [report di analisi delle minacce](threat-analytics.md) include sezioni dinamiche e una sezione scritta completa denominata report _dell'analista._ Per accedere a questa sezione, aprire il report sulla minaccia rilevata e selezionare la scheda **report Analista.**

![Immagine della sezione del report dell'analista di un report di analisi delle minacce](../../media/threat-analytics/ta_analystreport_mtp.png)

_Sezione del report dell'analista di un report di analisi delle minacce_

## <a name="scan-the-analyst-report"></a>Analizzare il report dell'analista 
Ogni sezione del report dell'analista è progettata per fornire informazioni utili. Sebbene i report varino, la maggior parte dei report include le sezioni descritte nella tabella seguente.

| Sezione Report | Descrizione |
|--|--|
| Riepilogo esecutivo | Panoramica della minaccia, tra cui quando è stata vista per la prima volta, le sue motivazioni, eventi importanti, obiettivi principali e strumenti e tecniche distinti. È possibile utilizzare queste informazioni per valutare ulteriormente come classificare in ordine di priorità la minaccia nel contesto del settore, della posizione geografica e della rete. |
| Analisi | Informazioni tecniche sulle minacce, inclusi i dettagli di un attacco e il modo in cui gli utenti malintenzionati potrebbero utilizzare una nuova tecnica o superficie di attacco | 
| Tecniche di miTRE ATT&CK osservate | Come le tecniche osservate sono mappate al framework di attacco [MITRE ATT&CK](https://attack.mitre.org/) | 
| [Mitigazioni](#apply-additional-mitigations) | Consigli che possono arrestare o ridurre l'impatto della minaccia. Questa sezione include anche le mitigazioni che non vengono monitorate dinamicamente come parte del report di analisi delle minacce. |
| [Dettagli di rilevamento](#understand-how-each-threat-can-be-detected) | Rilevamenti specifici e generici forniti da soluzioni di sicurezza Microsoft in grado di visualizzare attività o componenti associati alla minaccia. | 
| [Ricerca avanzata](#find-subtle-threat-artifacts-using-advanced-hunting) | [Query di ricerca avanzata per](advanced-hunting-overview.md) identificare in modo proattivo le possibili attività di minaccia. La maggior parte delle query viene fornita per integrare i rilevamenti, in particolare per individuare componenti o comportamenti potenzialmente dannosi che non possono essere valutati dinamicamente come dannosi. | 
| Riferimenti | Pubblicazioni Microsoft e di terze parti a cui fanno riferimento gli analisti durante la creazione del report. Il contenuto dell'analisi delle minacce si basa sui dati convalidati dai ricercatori Microsoft. Le informazioni provenienti da fonti di terze parti disponibili pubblicamente sono chiaramente identificate come tali. | 
| Log delle modifiche | L'ora in cui il report è stato pubblicato e quando sono state apportate modifiche significative al report. |

## <a name="apply-additional-mitigations"></a>Applicare misure di prevenzione aggiuntive
Analisi delle minacce tiene traccia dinamicamente [dello stato degli aggiornamenti della sicurezza e delle configurazioni protette.](threat-analytics.md#mitigations-review-list-of-mitigations-and-the-status-of-your-devices) Queste informazioni sono disponibili come grafici e tabelle nella scheda **Mitigazioni.**

Oltre a queste mitigazioni monitorate, il report dell'analista illustra anche le mitigazioni non _monitorate_ in modo dinamico. Ecco alcuni esempi di misure di prevenzione importanti che non vengono rilevate in modo dinamico:

- Bloccare i messaggi di posta elettronica _con allegati con estensione lnk_ o altri tipi di file sospetti
- Randomizzare le password dell'amministratore locale
- Informare gli utenti finali della posta elettronica di phishing e di altri vettori di minacce
- Attivare regole specifiche [per la riduzione della superficie di attacco](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction)

Anche se è possibile usare la scheda **Mitigazioni** per valutare il livello di sicurezza contro una minaccia, questi consigli consentono di intraprendere ulteriori passi per migliorare la propria posizione di sicurezza. Leggere attentamente tutte le indicazioni sulla mitigazione nel report dell'analista e applicarle quando possibile.

## <a name="understand-how-each-threat-can-be-detected"></a>Comprendere in che modo ogni minaccia può essere rilevata
Il report dell'analista fornisce anche i rilevamenti dalle funzionalità di rilevamento e risposta degli endpoint (EDR) di Microsoft Defender per _Endpoint._

### <a name="antivirus-detections"></a>Rilevamenti antivirus
Questi rilevamenti sono disponibili nei dispositivi con [Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) attivato. Quando questi rilevamenti si verificano nei dispositivi su cui è stato eseguito l'onboarded in Microsoft Defender for Endpoint, attivano anche avvisi che attivano i grafici nel report.

>[!NOTE]
>Nel report dell'analista sono inoltre elencati i rilevamenti generici in grado di identificare un'ampia gamma di minacce, oltre a componenti o comportamenti specifici della minaccia monitorata.  Questi rilevamenti generici non si riflettono nei grafici.

### <a name="endpoint-detection-and-response-edr-alerts"></a>Avvisi di rilevamento e risposta degli endpoint (EDR)
Gli avvisi edR vengono generati [per i dispositivi onboarded in Microsoft Defender per Endpoint.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/onboard-configure) Questi avvisi si basano in genere sui segnali di sicurezza raccolti dal sensore Microsoft Defender per endpoint e su altre funzionalità degli endpoint, ad esempio antivirus, protezione di rete e protezione dalle manomissioni, che fungono da potenti origini del segnale.

Come l'elenco dei rilevamenti antivirus, alcuni avvisi EDR sono progettati per contrassegnare genericamente comportamenti sospetti che potrebbero non essere associati alla minaccia rilevata. In questi casi, il report identificherà chiaramente l'avviso come "generico" e non influirà su alcun grafico nel report.

### <a name="email-related-detections-and-mitigations"></a>Rilevamenti e mitigazioni correlati alla posta elettronica
I rilevamenti e le mitigazioni correlati alla posta elettronica di Microsoft Defender per Office 365, sono inclusi nei report degli analisti oltre ai dati degli endpoint già disponibili da Microsoft Defender per Endpoint. 

Le informazioni sui tentativi di posta elettronica non consentite forniscono informazioni dettagliate sul fatto che l'organizzazione fosse un obiettivo della minaccia affrontata nel report dell'analista anche se l'attacco è stato effettivamente bloccato prima del recapito o recapitato nella cartella posta indesiderata.

## <a name="find-subtle-threat-artifacts-using-advanced-hunting"></a>Trovare artefatti per le minacce con la ricerca avanzata
Anche se i rilevamenti consentono di identificare e arrestare automaticamente la minaccia monitorata, molte attività di attacco lasciano tracce sottili che richiedono un'ispezione aggiuntiva. Alcune attività di attacco presentano comportamenti che possono anche essere normali, quindi il rilevamento dinamico può causare rumori operativi o persino falsi positivi.

[La ricerca avanzata](advanced-hunting-overview.md) fornisce un'interfaccia di query basata sul linguaggio di query Kusto che semplifica l'individuazione di indicatori discreti dell'attività di minaccia. Consente inoltre di visualizzare informazioni contestuali e verificare se gli indicatori sono collegati a una minaccia.

Le query di ricerca avanzata nei report degli analisti sono state oggetto di controllo da parte degli analisti Microsoft e sono pronte per l'esecuzione [nell'editor di query di ricerca avanzata.](https://security.microsoft.com/advanced-hunting) È inoltre possibile utilizzare le query per creare regole [di rilevamento personalizzate che](custom-detection-rules.md) attivano avvisi per corrispondenze future.


>[!NOTE]
> L'analisi delle minacce è disponibile anche in [Microsoft Defender per Endpoint.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) Tuttavia, non dispone dell'integrazione dei dati tra Microsoft Defender per Office e Microsoft Defender per Endpoint di Microsoft 365 Defender Threat Analytics.


## <a name="related-topics"></a>Argomenti correlati
- [Panoramica dell'analisi delle minacce](threat-analytics.md)
- [Trovare in modo proattivo le minacce con la ricerca avanzata](advanced-hunting-overview.md) 
- [Regole di rilevamento personalizzate](custom-detection-rules.md)
