---
title: Informazioni generali sulla ricerca avanzata di Microsoft Threat Protection
description: Informazioni sulle query di ricerca avanzata in Microsoft 365 e sul loro utilizzo per individuare in modo proattivo i rischi e i punti di debolezza della rete
keywords: caccia avanzata, caccia alle minacce, Cyber Threat Hunting, Microsoft Threat Protection, Microsoft 365, MTP, M365, Search, query, telemetria, rilevamenti personalizzati, schema, kusto, Microsoft 365, Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 791eee143c80e00a3fdb1fa4dbde8bbf41612e9a
ms.sourcegitcommit: 5b8e9935fe7bfcb96b8f8356119ce23152bd16a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2020
ms.locfileid: "41210351"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-threat-protection"></a>Cercare in modo proattivo minacce con la ricerca avanzata di Microsoft Threat Protection

**Si applica a:**
- Microsoft Threat Protection

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

La ricerca avanzata è uno strumento di ricerca delle minacce basato sulla query che permette di esplorare dati non elaborati fino a 30 giorni. È possibile controllare in modo proattivo eventi nella rete per localizzare indicatori ed entità interessanti. L'accesso flessibile ai dati facilita la ricerca non vincolata delle minacce conosciute e potenziali.

Nel centro sicurezza Microsoft 365, Advanced Hunting supporta le query che esaminano i dati di Microsoft Defender ATP, coprendo i dati dai dispositivi onboarded e Office 365 ATP, fornendo dati provenienti da messaggi di posta elettronica. Per utilizzare la ricerca avanzata, [attivare Microsoft Threat Protection](mtp-enable.md).

## <a name="get-started-with-advanced-hunting"></a>Introduzione alla ricerca avanzata

È consigliabile passare attraverso diverse fasi per diventare rapidamente operativi con la ricerca avanzata.

| Obiettivo di formazione | Descrizione | Risorsa |
|--|--|--|
| **Avere un'idea della lingua** | La ricerca avanzata si basa sul [linguaggio di query Kusto](https://docs.microsoft.com/azure/kusto/query/), supportandone la sintassi e gli operatori. Iniziare ad apprendere il linguaggio di query eseguendone la prima. | [Informazioni generali sul linguaggio di query](advanced-hunting-query-language.md) |
| **Comprensione dello schema** | È possibile ottenere una conoscenza buona e approfondita delle tabelle nello schema e delle relative colonne. Questo consente di determinare dove cercare i dati e come creare le query. | [Informazioni di riferimento sullo schema](advanced-hunting-schema-tables.md) |
| **Utilizzare le query predefinite** | Esplorare le raccolte di query predefinite che coprono diversi scenari di ricerca delle minacce. | [Utilizzare le query condivise](advanced-hunting-shared-queries.md)
| **Ottimizzare le query** | Informazioni su come creare query efficienti e query che combinino dati da email e dispositivi. | [Procedure consigliate per le query](advanced-hunting-shared-queries.md), [Ricerca attraverso dispositivi ed email](advanced-hunting-best-practices.md)

## <a name="get-help-as-you-write-queries"></a>Ottenere assistenza nella scrittura delle query
Trarre vantaggio dalle seguenti funzionalità per scrivere query più velocemente:
- **Suggerimenti automatici** — durante la scrittura di query, la ricerca avanzata propone suggerimenti. 
- **Riferimento di schema** — accanto all’area di lavoro è disponibile il riferimento a uno schema che include l'elenco di tabelle e le relative colonne. Per altre informazioni, passare il puntatore su un elemento. Fare doppio clic su un elemento per inserirlo nell'editor di query.

## <a name="drilldown-from-query-results"></a>Eseguire il drill-down dai risultati della query
Per visualizzare altre informazioni sulle entità, come computer, file, utenti, indirizzi IP e URL, fare clic sull'identificatore di entità nei risultati delle query. Quindi si aprirà una pagina profilo dettagliata per l’entità selezionata nel Microsoft Defender Security Center.

## <a name="tweak-your-queries-from-the-results"></a>Perfezionare le query dai risultati
Fare clic con il pulsante destro del mouse su un valore nel set di risultati per migliorare rapidamente la query. È possibile usare le opzioni per:

- Cercare in modo esplicito il valore selezionato (`==`)
- Escludere il valore selezionato dalla query (`!=`)
- Per aggiungere il valore alla query, è possibile usare gli operatori più avanzati, come `contains`, `starts with` e `ends with` 

![Immagine del set di risultati della ricerca avanzata Microsoft Defender ATP](../images/advanced-hunting-results-filter.png)

## <a name="filter-the-query-results"></a>Filtrare i risultati della query
I filtri visualizzati a destra forniscono un riepilogo del set di risultati. Ogni colonna ha una propria sezione in cui sono elencati i valori distinti individuati per quella colonna e il numero di istanze.

Perfezionare la query selezionando i pulsanti "+" o "-" sui valori che si desidera includere o escludere e quindi selezionare **Esegui query**.

![Immagine del filtro di ricerca avanzata](../images/advanced-hunting-filter.png)

Dopo avere applicato il filtro per modificare la query e aver eseguito la query, i risultati vengono aggiornati di conseguenza.

## <a name="related-topics"></a>Argomenti correlati
- [Apprendere il linguaggio delle query](advanced-hunting-query-language.md)
- [Utilizzare le query condivise](advanced-hunting-shared-queries.md)
- [Ricerca delle minacce attraverso dispositivi ed email](advanced-hunting-query-emails-devices.md)
- [Comprendere lo schema](advanced-hunting-schema-tables.md)
- [Applicazione delle procedure consigliate per le query](advanced-hunting-best-practices.md)