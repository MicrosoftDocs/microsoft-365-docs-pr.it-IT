---
title: Il linguaggio delle query in Ricerca avanzata in Microsoft Threat Protection
description: Creare una prima query di ricerca delle minacce, conoscere gli operatori più comuni e altri aspetti del linguaggio di query di Ricerca avanzata
keywords: caccia avanzata, caccia alle minacce, Cyber Threat Hunting, Microsoft Threat Protection, Microsoft 365, MTP, M365, Search, query, language, Learn, First query, telemetria, eventi, telemetria, rilevamenti personalizzati, schema, kusto, operatori, tipi di dati
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: acc515d046b1ebd2ff7c5dd9c52b363fe99f0b9e
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42087466"
---
# <a name="learn-the-advanced-hunting-query-language"></a>Scoprire il linguaggio delle query in Ricerca avanzata

**Si applica a:**
- Microsoft Threat Protection

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Ricerca avanzata si basa sul [linguaggio delle query in Esplora dati](https://docs.microsoft.com/azure/kusto/query/). È possibile usare la sintassi e gli operatori di Esplora dati per creare query che individuano informazioni nello [schema](advanced-hunting-schema-tables.md) specificamente strutturate per Ricerca avanzata. Per comprendere meglio questi concetti, eseguire la prima query.

## <a name="try-your-first-query"></a>Provare la prima query

nel Centro sicurezza Microsoft 365 andare su **Ricerca** per eseguire la prima query. Usare l'esempio seguente:

```kusto
// Finds PowerShell execution events that could involve a download.
DeviceProcessEvents 
| where Timestamp > ago(7d)
| where FileName in ("powershell.exe", "POWERSHELL.EXE", "powershell_ise.exe", "POWERSHELL_ISE.EXE") 
| where ProcessCommandLine has "Net.WebClient"
        or ProcessCommandLine has "DownloadFile"
        or ProcessCommandLine has "Invoke-WebRequest"
        or ProcessCommandLine has "Invoke-Shellcode"
        or ProcessCommandLine contains "http:"
| project Timestamp, DeviceName, InitiatingProcessFileName, FileName, ProcessCommandLine
| top 100 by Timestamp
```

Questo è come apparirà in Ricerca avanzata.

![Immagine della query in Ricerca avanzata di Microsoft Defender Advanced Threat Protection](../../media/advanced-hunting-query-example.png)

La query inizia con un breve commento che descrive il contenuto. In un secondo momento si può decidere di salvare la query e condividerla con altri utenti dell'organizzazione.

```kusto
// Finds PowerShell execution events that could involve a download.
DeviceProcessEvents
```

La query viene in genere avviata con un nome di tabella seguito da una serie di elementi avviati da una pipe (`|`). In questo esempio, iniziamo aggiungendo il nome della tabella `DeviceProcessEvents` e gli elementi reindirizzati, se necessario.

Il primo elemento reindirizzato è l'ambito del filtro del periodo entro i sette giorni precedenti. Il mantenimento dell'intervallo di tempo il più possibile ravvicinato assicura che le query vengano eseguite bene, che restituiscano risultati gestibili e che non scadano.

```kusto
| where Timestamp > ago(7d)
```

L'intervallo di tempo è seguito immediatamente da una ricerca di file che rappresenta l'applicazione di PowerShell.

```kusto
| where FileName in ("powershell.exe", "POWERSHELL.EXE", "powershell_ise.exe", "POWERSHELL_ISE.EXE")
```

In seguito, la query cerca le righe di comando usate in genere con PowerShell per scaricare i file.

```kusto
| where ProcessCommandLine has "Net.WebClient"
        or ProcessCommandLine has "DownloadFile"
        or ProcessCommandLine has "Invoke-WebRequest"
        or ProcessCommandLine has "Invoke-Shellcode"
        or ProcessCommandLine contains "http:"
```

Ora che la query identifica chiaramente i dati da individuare, è possibile aggiungere elementi che definiscono come appaiono i risultati. `project` restituisce colonne specifiche e `top` limita il numero di risultati, rendendo i risultati ben formattati, ragionevolmente grandi e facili da elaborare.

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, FileName, ProcessCommandLine
| top 100 by Timestamp
```

Fare clic su **Esegui query** per visualizzare i risultati. È possibile espandere la visualizzazione dello schermo in modo da concentrarsi sulla query di ricerca e sui risultati.

## <a name="learn-common-query-operators-for-advanced-hunting"></a>Informazioni sugli operatori di query più comuni per la Ricerca avanzata

Ora che è stata eseguita la prima query e si ha un'idea generale dei relativi componenti, è il momento di tornare indietro e imparare alcune nozioni di base. Il linguaggio delle query di Esplora dati usato in Ricerca avanzata supporta una serie di operatori, di seguito sono elencati i più comuni.

| Operatore | Descrizione e utilizzo |
|--|--|
| `where` | Filtrare una tabella nel sottoinsieme di righe che soddisfano un predicato. |
| `summarize` | Creare una tabella che aggrega il contenuto della tabella di input. |
| `join` | Unire le righe di due tabelle per creare una nuova tabella in base ai valori corrispondenti delle colonne specificate di ogni tabella. |
| `count` | Restituire il numero di record nel set di record di input. |
| `top` | Restituire i primi N record ordinati in base alle colonne specificate. |
| `limit` | Tornare al numero specificato di righe. |
| `project` | Selezionare le colonne da includere, rinominare o rilasciare e inserire nuove colonne calcolate. |
| `extend` | Creare colonne calcolate e accodarle al set di risultati. |
| `makeset` |  Restituire una matrice dinamica (JSON) del set di valori distinti che Expr accetta nel gruppo. |
| `find` | Trovare le righe che corrispondono a un predicato in un set di tabelle. |

Per vedere un esempio pratico di questi operatori, eseguirli nella sezione **Introduzione** in Ricerca avanzata.

## <a name="understand-data-types-and-their-query-syntax-implications"></a>Informazioni sui tipi di dati e sulle implicazioni della sintassi delle query

I dati nelle tabelle di Ricerca avanzata sono generalmente classificati nei seguenti tipi di dati.

| Tipo di dati | Descrizione e implicazioni delle query |
|--|--|
| `datetime` | Informazioni sui dati e sull'ora che rappresentano in genere timestamp dell'evento |
| `string` | Stringa di caratteri |
| `bool` | True o False |
| `int` | Valore numerico 32 bit  |
| `long` | Valore numerico 64 bit |

## <a name="use-sample-queries"></a>Usare query di esempio

La sezione **Introduzione** presenta alcune semplici query che impiegano operatori di uso comune. Provare a eseguire queste query e apportare piccole modifiche.

![Immagine della finestra di Ricerca avanzata](../../media/advanced-hunting-get-started.png)

>[!NOTE]
>Oltre agli esempi di query di base, è anche possibile accedere [query condivise](advanced-hunting-shared-queries.md) per specifici scenari di ricerca delle minacce. Esplorare le query condivise sul lato sinistro della pagina o sul repository di query GitHub.

## <a name="access-query-language-documentation"></a>Documentazione sulle query

Per altre informazioni sul linguaggio delle query di Esplora dati e sugli operatori supportati, vedere [Documentazione sul linguaggio delle query di Esplora dati](https://docs.microsoft.com/azure/kusto/query/).

## <a name="related-topics"></a>Argomenti correlati
- [Ricerca proattiva delle minacce](advanced-hunting-overview.md)
- [Utilizzare le query condivise](advanced-hunting-shared-queries.md)
- [Ricerca delle minacce attraverso dispositivi e email](advanced-hunting-query-emails-devices.md)
- [Comprensione dello schema](advanced-hunting-schema-tables.md)
- [Applicazione delle procedure consigliate per le query](advanced-hunting-best-practices.md)
