---
title: Ottenere una formazione avanzata sulla ricerca avanzata
description: Formazione e indicazioni gratuite da parte di esperti di ricerca avanzata
keywords: ricerca avanzata, ricerca delle minacce, ricerca delle minacce informatiche, protezione dalle minacce Microsoft, Microsoft 365, mtp, m365, ricerca, query, lingua, formazione, scenari, da base a avanzata, video, istruzioni dettagliate
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: aba0a6ab2c82c038eda8e66890c0c95303dea947
ms.sourcegitcommit: ea8a096df5acedecdce1780969f2b189c3fadf73
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2021
ms.locfileid: "50053836"
---
# <a name="get-expert-training-on-advanced-hunting"></a>Ottenere una formazione avanzata sulla ricerca avanzata

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

Aumenta rapidamente la tua conoscenza della ricerca avanzata con _Tracking the adversary,_ una serie di webcast per i nuovi analisti della sicurezza e i cercatori di minacce esperti. La serie guida l'utente attraverso le nozioni di base fino alla creazione di query sofisticate. Inizia con il primo video sulle nozioni fondamentali o passa a video più avanzati adatti al tuo livello di esperienza.


| Titolo | Descrizione | Watch | Query | 
|--|--|--|--|
| Episodio 1: nozioni fondamentali su KQL | Questo episodio illustra le nozioni di base della ricerca avanzata in Microsoft 365 Defender. Informazioni sui dati di ricerca avanzati disponibili e sulla sintassi ESQL di base e sugli operatori. | [YouTube](https://youtu.be/0D9TkGjeJwM?t=351) (54:14) | [File CSL](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%201%20-%20KQL%20Fundamentals.csl) |
| Episodio 2: partecipazioni | Continuare a conoscere i dati nella ricerca avanzata e su come unire le tabelle. Informazioni su , , e partecipazioni e comprendere le sfumature dell'aggiunta `inner` `outer` `unique` `semi` Kusto `innerunique` predefinita. | [YouTube](https://youtu.be/LMrO6K5TWOU?t=297) (53:33) | [File CSL](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%202%20-%20Joins.csl) |
| Episodio 3: riepilogo, pivot e visualizzazione dei dati | Ora che hai appreso come filtrare, modificare e unire i dati, è il momento di riepilogare, quantificare, pivot e visualizzare. Questo episodio illustra `summarize` l'operatore e vari calcoli, introducendo allo stesso tempo altre tabelle nello schema. Verrà inoltre descritto come trasformare i set di dati in grafici che consentono di estrarre informazioni dettagliate. | [YouTube](https://youtu.be/UKnk9U1NH6Y?t=296) (48:52) | [File CSL](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%203%20-%20Summarizing%2C%20Pivoting%2C%20and%20Joining.csl) |
| Episodio 4: diamo una risposta. Applicazione di KQL al rilevamento degli eventi imprevisti | In questo episodio imparerai a tenere traccia di alcune attività degli utenti malintenzionati. Usiamo la nostra migliore comprensione di Kusto e la ricerca avanzata per tenere traccia di un attacco. Scopri i trucchi effettivi usati sul campo, inclusi i criteri rubrica della cybersecurity e come applicarli alla risposta agli incidenti. | [YouTube](https://youtu.be/2EUxOc_LNd8?t=291) (59:36) | [File CSL](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%204%20-%20Lets%20Hunt.csl) 


Ottenere una formazione più avanzata con *L33TSP3AK: ricerca avanzata in Microsoft 365 Defender,* una serie di webcast per gli analisti che desiderano espandere le proprie conoscenze tecniche e competenze pratiche nell'esecuzione di indagini di sicurezza usando la ricerca avanzata in Microsoft 365 Defender. 

| Titolo | Descrizione | Watch | Query | 
|--|--|--|--|
| Episodio 1  | In questo episodio verranno apprese diverse procedure consigliate per l'esecuzione di query di ricerca avanzata. Tra gli argomenti trattati ci sono: come ottimizzare le query, usare la ricerca avanzata per ransomware, gestire JSON come tipo dinamico e lavorare con gli operatori di dati esterni. | [YouTube](https://www.youtube.com/watch?v=nMGbK-ALaVg&feature=youtu.be) (56:34) | [File CSL](https://github.com/microsoft/Microsoft-365-Defender-Hunting-Queries/blob/master/Webcasts/l33tSpeak/Performance%2C%20Json%20and%20dynamics%20operator%2C%20external%20data.csl)


## <a name="how-to-use-the-csl-file"></a>Come usare il file CSL
Prima di iniziare un episodio, accedere al [file CSL Kusto corrispondente su GitHub](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/tree/master/Webcasts/TrackingTheAdversary) e copiarne il contenuto nell'editor di query di ricerca avanzata. Mentre guardi un episodio, puoi usare il contenuto copiato per seguire l'altoparlante ed eseguire query. 

L'estratto seguente di un file CSL mostra un set completo di indicazioni contrassegnate come commenti con `//` .

```kusto
// DeviceLogonEvents
// A table containing a row for each logon a device enrolled in Microsoft Defender for Endpoint
// Contains
// - Account information associated with the logon
// - The device which the account logged onto
// - The process which performed the logon
// - Network information (for network logons)
// - Timestamp
```

Lo stesso file CSL include query prima e dopo i commenti, come illustrato di seguito. Per eseguire una query specifica con [più query nell'editor,](advanced-hunting-query-language.md#work-with-multiple-queries-in-the-editor)spostare il cursore in tale query e selezionare **Esegui query.**   

```kusto
DeviceLogonEvents
| count

// DeviceLogonEvents
// A table containing a row for each logon a device enrolled in Microsoft Defender for Endpoint
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
