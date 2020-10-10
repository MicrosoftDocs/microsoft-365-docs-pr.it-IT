---
title: Ottenere una formazione esperta sulla ricerca avanzata
description: Formazione gratuita e guida di esperti di caccia avanzati
keywords: caccia avanzata, caccia alle minacce, Cyber Threat Hunting, Microsoft Threat Protection, Microsoft 365, MTP, M365, Search, query, language, training, scenarios, Basic to Advanced, video, Step-by-Step
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
- m365-initiative-m365-defender
ms.topic: article
ms.openlocfilehash: f06cb4190f8932f3a472356ba45adcc3bc35423c
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/09/2020
ms.locfileid: "48413319"
---
# <a name="get-expert-training-on-advanced-hunting"></a>Ottenere una formazione esperta sulla ricerca avanzata

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft Threat Protection

Migliorare rapidamente le proprie conoscenze sulla ricerca avanzata con _Tracking dell'avversario_, una serie di webcast per i nuovi analisti di sicurezza e i cacciatori di minacce stagionati. La serie guida l'utente attraverso le nozioni di base fino alla creazione di query sofisticate. Iniziare con il primo video sui fondamentali o passare a video più avanzati adatti al proprio livello di esperienza.


| Titolo | Descrizione | Guardare | Query | 
|--|--|--|--|
| Episode 1: Nozioni fondamentali su KQL | Questo episodio copre le nozioni di base della ricerca avanzata in Microsoft Threat Protection. Informazioni sui dati di caccia avanzati disponibili e sulla sintassi e sugli operatori di base di KQL. | [YouTube](https://youtu.be/0D9TkGjeJwM?t=351) (54:14) | [File CSL](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%201%20-%20KQL%20Fundamentals.csl) |
| Episodio 2: join | Continuare a imparare informazioni sui dati in Advanced Hunting e su come unire tabelle insieme. Informazioni su `inner` , `outer` , `unique` e `semi` join e comprendere le sfumature del join di Kusto predefinito `innerunique` . | [YouTube](https://youtu.be/LMrO6K5TWOU?t=297) (53:33) | [File CSL](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%202%20-%20Joins.csl) |
| Episodio 3: ricapitolazione, pivoting e visualizzazione dei dati | Dopo aver imparato a filtrare, modificare e unire i dati, è il momento di riepilogare, quantificare, pivot e visualizzare. In questo episodio vengono illustrati l' `summarize` operatore e vari calcoli, mentre vengono introdotti ulteriori tabelle nello schema. Verrà inoltre illustrato come trasformare i set di informazioni in grafici che consentono di estrarre Insight. | [YouTube](https://youtu.be/UKnk9U1NH6Y?t=296) (48:52) | [File CSL](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%203%20-%20Summarizing%2C%20Pivoting%2C%20and%20Joining.csl) |
| Episodio 4: Let ' s Hunt! Applicazione di KQL alla verifica degli incidenti | In questo episodio viene illustrato come monitorare alcune attività di un utente malintenzionato. Usiamo la nostra migliore comprensione di Kusto e Advanced Hunting per individuare un attacco. Informazioni sui trucchi effettivi utilizzati nel campo, tra cui ABC di Cybersecurity e su come applicarli alla risposta agli incidenti. | [YouTube](https://youtu.be/2EUxOc_LNd8?t=291) (59:36) | [File CSL](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%204%20-%20Lets%20Hunt.csl)

## <a name="how-to-use-the-csl-file"></a>Come utilizzare il file CSL
Prima di iniziare un episodio, accedere al [file kusto CSL corrispondente su GitHub](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/tree/master/Webcasts/TrackingTheAdversary) e copiarne il contenuto nell'editor di query di caccia avanzato. Quando si guarda un episodio, è possibile utilizzare il contenuto copiato per seguire gli altoparlanti ed eseguire le query. 

L'estratto seguente da un file CSL Visualizza un insieme completo di linee guida contrassegnate come commenti con `//` .

```kusto
// DeviceLogonEvents
// A table containing a row for each logon a device enrolled in Defender ATP
// Contains
// - Account information associated with the logon
// - The device which the account logged onto
// - The process which performed the logon
// - Network information (for network logons)
// - Timestamp
```

Lo stesso file CSL include le query prima e dopo i commenti come illustrato di seguito. Per eseguire una query specifica con [più query nell'editor](advanced-hunting-query-language.md#work-with-multiple-queries-in-the-editor), spostare il cursore su tale query e selezionare **Esegui query**.   

```kusto
DeviceLogonEvents
| count

// DeviceLogonEvents
// A table containing a row for each logon a device enrolled in Defender ATP
// Contains
// - Account information associated with the logon
// - The device which the account logged onto
// - The process which performed the logon
// - Network information (for network logons)
// - Timestamp

AppFileEvents
| take 100
| sort by Timestamp desc
```
     
## <a name="related-topics"></a>Argomenti correlati
- [Panoramica della ricerca avanzata](advanced-hunting-overview.md)
- [Scoprire il linguaggio delle query in Ricerca avanzata](advanced-hunting-query-language.md)
- [Usare i risultati delle query](advanced-hunting-query-results.md)
- [Utilizzare le query condivise](advanced-hunting-shared-queries.md)
- [Cercare tra dispositivi, posta elettronica, app e identità](advanced-hunting-query-emails-devices.md)
- [Comprendere lo schema](advanced-hunting-schema-tables.md)
- [Applicare le procedure consigliate per le query](advanced-hunting-best-practices.md)
