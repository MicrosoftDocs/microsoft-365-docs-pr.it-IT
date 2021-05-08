---
title: Ottenere una formazione esperta sulla ricerca avanzata
description: Formazione e indicazioni gratuite da esperti di ricerca avanzata
keywords: ricerca avanzata, ricerca delle minacce, ricerca di minacce informatiche, Microsoft 365 Defender, Microsoft 365, m365, ricerca, query, lingua, formazione, scenari, da base a avanzata, video, istruzioni dettagliate
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 136e7cba26d55676fdf3b3b7f0f9ef967e7d7991
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245829"
---
# <a name="get-expert-training-on-advanced-hunting"></a>Ottenere una formazione esperta sulla ricerca avanzata

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender
- Microsoft Defender per endpoint

Aumenta rapidamente la tua conoscenza della ricerca avanzata con _Tracking the adversary,_ una serie di webcast per i nuovi analisti della sicurezza e i cacciatori di minacce esperti. La serie illustra le nozioni di base per creare query sofisticate. Inizia con il primo video sulle nozioni fondamentali o passa a video più avanzati adatti al tuo livello di esperienza.

| Titolo | Descrizione | Watch | Query | 
|--|--|--|--|
| Episodio 1: Nozioni fondamentali su KQL | Questo episodio illustra le nozioni di base della ricerca avanzata in Microsoft 365 Defender. Informazioni sui dati di ricerca avanzati disponibili e sulla sintassi e sugli operatori KQL di base. | [YouTube](https://youtu.be/0D9TkGjeJwM?t=351) (54:14) | [File di testo](https://github.com/microsoft/Microsoft-365-Defender-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%201%20-%20KQL%20Fundamentals.txt) |
| Episodio 2: Join | Continua a conoscere i dati nella ricerca avanzata e su come unire le tabelle. Informazioni su , , e join e comprendere `inner` `outer` le `unique` `semi` sfumature dell'aggiunta Kusto `innerunique` predefinita. | [YouTube](https://youtu.be/LMrO6K5TWOU?t=297) (53:33) | [File di testo](https://github.com/microsoft/Microsoft-365-Defender-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%202%20-%20Joins.txt) |
| Episodio 3: Riepilogo, pivot e visualizzazione dei dati | Ora che hai imparato a filtrare, modificare e unire i dati, è il momento di riepilogare, quantificare, eseguire pivot e visualizzare. In questo episodio vengono illustrati `summarize` l'operatore e vari calcoli, introducendo allo stesso tempo tabelle aggiuntive nello schema. Verrà inoltre descritto come trasformare i set di dati in grafici che consentono di estrarre informazioni dettagliate. | [YouTube](https://youtu.be/UKnk9U1NH6Y?t=296) (48:52) | [File di testo](https://github.com/microsoft/Microsoft-365-Defender-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%203%20-%20Summarizing%2C%20Pivoting%2C%20and%20Joining.txt) |
| Episodio 4: Diamo la caccia! Applicazione di KQL al rilevamento degli eventi imprevisti | In questo episodio imparerai a tenere traccia di alcune attività degli utenti malintenzionati. Usiamo la nostra migliore comprensione di Kusto e la ricerca avanzata per tenere traccia di un attacco. Scopri i trucchi effettivi usati nel campo, inclusi gli ABC della cybersecurity e come applicarli alla risposta agli incidenti. | [YouTube](https://youtu.be/2EUxOc_LNd8?t=291) (59:36) | [File di testo](https://github.com/microsoft/Microsoft-365-Defender-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%204%20-%20Lets%20Hunt.txt) 


Ottenere una formazione più esperta con *L33TSP3AK:* ricerca avanzata in Microsoft 365 Defender , una serie di webcast per gli analisti che desiderano espandere le proprie conoscenze tecniche e competenze pratiche nell'condurre indagini di sicurezza usando la ricerca avanzata in Microsoft 365 Defender. 

| Titolo | Descrizione | Watch | Query | 
|--|--|--|--|
| Episodio 1  | In questo episodio verranno apprese diverse procedure consigliate per l'esecuzione di query di ricerca avanzate. Tra gli argomenti trattati sono: come ottimizzare le query, usare la ricerca avanzata per ransomware, gestire JSON come tipo dinamico e lavorare con gli operatori di dati esterni. | [YouTube](https://www.youtube.com/watch?v=nMGbK-ALaVg&feature=youtu.be) (56:34) | [File di testo](https://github.com/microsoft/Microsoft-365-Defender-Hunting-Queries/blob/master/Webcasts/l33tSpeak/Performance%2C%20Json%20and%20dynamics%20operator%2C%20external%20data.txt)


## <a name="how-to-use-the-csl-file"></a>Come usare il file CSL
Prima di avviare un episodio, accedere al file di testo corrispondente [GitHub](https://github.com/microsoft/Microsoft-365-Defender-Hunting-Queries/tree/master/Webcasts) e copiarne il contenuto nell'editor di query di ricerca avanzata. Mentre guardi un episodio, puoi usare il contenuto copiato per seguire l'altoparlante ed eseguire query. 

L'estratto seguente di un file di testo contenente le query mostra un set completo di indicazioni contrassegnate come commenti con `//` .

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

Lo stesso file di testo include query prima e dopo i commenti, come illustrato di seguito. Per eseguire una query specifica con [più query nell'editor,](advanced-hunting-query-language.md#work-with-multiple-queries-in-the-editor)spostare il cursore su tale query e selezionare **Esegui query**.   

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
- [Panoramica della rilevazione avanzata](advanced-hunting-overview.md)
- [Scoprire il linguaggio delle query in Ricerca avanzata](advanced-hunting-query-language.md)
- [Usare i risultati delle query](advanced-hunting-query-results.md)
- [Utilizzare le query condivise](advanced-hunting-shared-queries.md)
- [Cercare tra dispositivi, posta elettronica, app e identità](advanced-hunting-query-emails-devices.md)
- [Comprendere lo schema](advanced-hunting-schema-tables.md)
- [Applicare le procedure consigliate per le query](advanced-hunting-best-practices.md)
