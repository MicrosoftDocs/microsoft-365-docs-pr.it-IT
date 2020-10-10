---
title: Il linguaggio delle query in Ricerca avanzata in Microsoft Threat Protection
description: Creare una prima query di ricerca delle minacce, conoscere gli operatori più comuni e altri aspetti del linguaggio di query di Ricerca avanzata
keywords: caccia avanzata, caccia alle minacce, Cyber Threat Hunting, Microsoft Threat Protection, Microsoft 365, MTP, M365, Search, query, language, Learn, First query, telemetria, eventi, telemetria, rilevamenti personalizzati, schema, kusto, operatori, tipi di dati, download di PowerShell, esempio di query
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
ms.openlocfilehash: 35de1504d4d7ddd3512b6cc3e478b138c1f43c29
ms.sourcegitcommit: a83acd5b9eeefd2e20e5bac916fe29d09fb53de9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/10/2020
ms.locfileid: "48418122"
---
# <a name="learn-the-advanced-hunting-query-language"></a>Scoprire il linguaggio delle query in Ricerca avanzata

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft Threat Protection

Ricerca avanzata si basa sul [linguaggio delle query in Esplora dati](https://docs.microsoft.com/azure/kusto/query/). È possibile utilizzare gli operatori e le istruzioni di Kusto per creare query che consentono di individuare le informazioni in uno [schema](advanced-hunting-schema-tables.md)specializzato. Per comprendere meglio questi concetti, eseguire la prima query.

## <a name="try-your-first-query"></a>Provare la prima query

In Microsoft 365 Security Center, andare a **caccia** per eseguire la prima query. Usare l'esempio seguente:

```kusto
// Finds PowerShell execution events that could involve a download
union DeviceProcessEvents, DeviceNetworkEvents
| where Timestamp > ago(7d)
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
// Suspicious commands
| where ProcessCommandLine has_any("WebClient",
 "DownloadFile",
 "DownloadData",
 "DownloadString",
"WebRequest",
"Shellcode",
"http",
"https")
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

**[Eseguire la query in Advanced Hunting](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI2TW0sCURSF93PQfxh8Moisp956yYIgQtLoMaYczJpbzkkTpN_et_dcdPQkcpjbmrXXWftyetKTQG5lKqmMpeB9IJksJJKZDOWdZ8wKeP5wvcm3OLgZbMXmXCmIxjnYIfcAVgYvRi8w3TnfsXEDGAG47pCCZXyP5ViO4KeNbt-Up-hEuJmB6lvButnY8XSL-cDl0M2I-GwxVX8Fe2H5zMzHiKjEVB0eEsnBrszfBIWuXOLrxCJ7VqEBfM3DWUYTkNKrv1p5y3X0jwetemzOQ_NSVuuXZ1c6aNTKRaN8VvWhY9n7OS-o6J5r7mYeQypdEKc1m1qfiqpjCSuspsDntt2J61bEvTlXls5AgQfFl5bHM_gr_BhO2RF1rztoBv2tWahrso_TtzkL93KGMGZVr2pe7eWR-xeZl91f_113UOsx3nDR4Y9j5R6kaCq8ajr_YWfFeedsd27L7it-Z6dAZyxsJq1d9-2ZOSzK3y2NVd8-zUPjtZaJnYsIH4Md7AmdeAcd2Cl1XoURc5PzXlfU8U9P54WcswL6t_TW9Q__qX-xygQAAA&runQuery=true&timeRangeId=week)**

### <a name="describe-the-query-and-specify-the-tables-to-search"></a>Descrivere la query e specificare le tabelle di cui eseguire la ricerca
All'inizio della query è stato aggiunto un breve commento per descrivere il relativo contenuto. Questo commento aiuta se in seguito si decide di salvare la query e condividerla con altri utenti dell'organizzazione. 

```kusto
// Finds PowerShell execution events that could involve a download
```

La query in genere inizia con un nome di tabella seguito da diversi elementi che iniziano con una pipe ( `|` ). In questo esempio viene avviata la creazione di un'Unione di due tabelle  `DeviceProcessEvents` e `DeviceNetworkEvents` , quindi, vengono aggiunti gli elementi reindirizzati in base alle esigenze.

```kusto
union DeviceProcessEvents, DeviceNetworkEvents
```
### <a name="set-the-time-range"></a>Impostare l'intervallo di tempo
Il primo elemento con pipe è un filtro temporale che ha come ambito i sette giorni precedenti. La limitazione dell'intervallo di tempo consente di garantire la corretta esecuzione delle query, restituire risultati gestibili e non eseguire il timeout.

```kusto
| where Timestamp > ago(7d)
```

### <a name="check-specific-processes"></a>Controllare i processi specifici
L'intervallo di tempo è subito seguito da una ricerca dei nomi dei file di processo che rappresentano l'applicazione PowerShell.

```kusto
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
```

### <a name="search-for-specific-command-strings"></a>Ricerca di stringhe di comandi specifiche
Successivamente, la query Cerca stringhe nelle righe di comando che vengono in genere utilizzate per scaricare i file tramite PowerShell.

```kusto
// Suspicious commands
| where ProcessCommandLine has_any("WebClient",
    "DownloadFile",
    "DownloadData",
    "DownloadString",
    "WebRequest",
    "Shellcode",
    "http",
    "https")
```

### <a name="customize-result-columns-and-length"></a>Personalizzare le colonne dei risultati e la lunghezza 
Ora che la query identifica chiaramente i dati che si desidera individuare, è possibile definire i risultati. `project` restituisce colonne specifiche e `top` limita il numero di risultati. Questi operatori contribuiscono a garantire che i risultati siano ben formattati e ragionevolmente grandi e facili da elaborare.

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

Selezionare **Esegui query** per visualizzare i risultati. Utilizzare l'icona Espandi nell'angolo superiore destro dell'editor di query per concentrarsi sulla query di caccia e sui risultati. 

![Immagine del controllo Espandi nell'editor di query di ricerca avanzata](../../media/advanced-hunting-expand.png)

>[!TIP]
>È possibile visualizzare i risultati delle query come grafici e regolare rapidamente i filtri. Per ulteriori informazioni, [vedere Utilizzo dei risultati delle query](advanced-hunting-query-results.md)

## <a name="learn-common-query-operators"></a>Informazioni sugli operatori di query comuni

È sufficiente eseguire la prima query e avere un'idea generale dei relativi componenti. È il momento di fare un po' di marcia indietro e imparare alcune nozioni di base. Il linguaggio delle query di Esplora dati usato in Ricerca avanzata supporta una serie di operatori, di seguito sono elencati i più comuni.

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

## <a name="understand-data-types"></a>Informazioni sui tipi di dati

Advanced Hunting supporta i tipi di dati di Kusto, inclusi i seguenti tipi comuni:

| Tipo di dati | Descrizione e implicazioni delle query |
|--|--|
| `datetime` | Informazioni sui dati e sull'ora che in genere rappresentano timestamp dell'evento. [Vedere formati DateTime supportati](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/datetime) |
| `string` | Stringa di caratteri in UTF-8 racchiusa tra virgolette singole ( `'` ) o virgolette doppie ( `"` ). [Per saperne di più sulle stringhe](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/string) |
| `bool` | Questo tipo di dati supporta `true` o `false` dichiara. [Vedere i valori letterali e gli operatori supportati](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/bool) |
| `int` | numero intero a 32 bit  |
| `long` | numero intero a 64 bit |

Per ulteriori informazioni su questi tipi di dati, [leggere informazioni sui tipi di dati scalari di Kusto](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/).

## <a name="get-help-as-you-write-queries"></a>Ottenere assistenza nella scrittura delle query
Trarre vantaggio dalle seguenti funzionalità per scrivere query più velocemente:
- **AutoSuggest**: durante la scrittura di query, la ricerca avanzata fornisce suggerimenti da IntelliSense. 
- **Albero dello schema**: una rappresentazione dello schema che include l'elenco delle tabelle e delle relative colonne viene fornita accanto all'area di lavoro. Per altre informazioni, passare il puntatore su un elemento. Fare doppio clic su un elemento per inserirlo nell'editor di query.
- **[Riferimenti dello schema](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)**: riferimenti in-Portal con descrizioni di tabelle e colonne, nonché tipi di evento supportati ( `ActionType` valori) e query di esempio

## <a name="work-with-multiple-queries-in-the-editor"></a>Utilizzo di più query nell'editor
È possibile utilizzare l'editor di query per sperimentare più query. Per utilizzare più query:

- Separare ogni query con una linea vuota.
- Posizionare il cursore su qualsiasi parte di una query per selezionare la query prima di eseguirla. Verrà eseguita solo la query selezionata. Per eseguire un'altra query, spostare il cursore di conseguenza e selezionare **Esegui query**.

![Immagine dell'editor di query con più query](../../media/mtp-ah/ah-multi-query.png)

## <a name="use-sample-queries"></a>Usare query di esempio

La sezione **Introduzione** presenta alcune semplici query che impiegano operatori di uso comune. Provare a eseguire queste query e apportare piccole modifiche.

![Immagine della finestra di Ricerca avanzata](../../media/advanced-hunting-get-started.png)

>[!NOTE]
>Oltre agli esempi di query di base, è anche possibile accedere [query condivise](advanced-hunting-shared-queries.md) per specifici scenari di ricerca delle minacce. Esplorare le query condivise sul lato sinistro della pagina o l'archivio di [query GitHub](https://aka.ms/hunting-queries).

## <a name="access-query-language-documentation"></a>Documentazione sulle query

Per altre informazioni sul linguaggio delle query di Esplora dati e sugli operatori supportati, vedere [Documentazione sul linguaggio delle query di Esplora dati](https://docs.microsoft.com/azure/kusto/query/).

## <a name="related-topics"></a>Argomenti correlati
- [Panoramica della ricerca avanzata](advanced-hunting-overview.md)
- [Usare i risultati delle query](advanced-hunting-query-results.md)
- [Utilizzare le query condivise](advanced-hunting-shared-queries.md)
- [Cercare tra dispositivi, posta elettronica, app e identità](advanced-hunting-query-emails-devices.md)
- [Comprendere lo schema](advanced-hunting-schema-tables.md)
- [Applicare le procedure consigliate per le query](advanced-hunting-best-practices.md)
