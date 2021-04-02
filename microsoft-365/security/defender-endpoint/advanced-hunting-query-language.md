---
title: Scoprire il linguaggio delle query in Ricerca avanzata
description: Creare una prima query di ricerca delle minacce, conoscere gli operatori più comuni e altri aspetti del linguaggio di query di Ricerca avanzata
keywords: ricerca avanzata, ricerca delle minacce, ricerca di minacce informatiche, mdatp, microsoft defender atp, ricerca wdatp, query, lingua, imparare, prima query, telemetria, eventi, telemetria, rilevamenti personalizzati, schema, kusto, operatori, tipi di dati
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
ms.openlocfilehash: af612a051f133e4846e04033ab35ea39769d0193
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499538"
---
# <a name="learn-the-advanced-hunting-query-language"></a>Scoprire il linguaggio delle query in Ricerca avanzata

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Defender per endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

> Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhunting-abovefoldlink)

Ricerca avanzata si basa sul [linguaggio delle query in Esplora dati](https://docs.microsoft.com/azure/kusto/query/). È possibile utilizzare gli operatori e le istruzioni Kusto per creare query che individuano informazioni in uno [schema specializzato.](advanced-hunting-schema-reference.md) Per comprendere meglio questi concetti, eseguire la prima query.

## <a name="try-your-first-query"></a>Provare la prima query

In Microsoft Defender Security Center passare a **Ricerca avanzata** per eseguire la prima query. Usare l'esempio seguente:

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
**[Eseguire questa query nella ricerca avanzata](https://securitycenter.windows.com/hunting?query=H4sIAAAAAAAEAI2TT0vDQBDF5yz4HUJPFcTqyZsXqyCIBFvxKNGWtpo_NVlbC8XP7m8mado0K5Zls8nkzdu3b2Z70pNAbmUmqYyk4D2UTJYyllwGMmWNGQHrN_NNvsSBzUBrbMFMiWieAx3xDEBl4GL4AuNd8B0bNgARENcdUmIZ3yM5liPwac3bN-YZPGPU5ET1rWDc7Ox4uod8YDp4MzI-GkjlX4Ne2nly0zEkKzFWh4ZE5sSuTN8Ehq5couvEMnvmUAhez-HsRBMipVa_W_OG6vEfGtT12JRHpqV064e1Kx04NsxFzXxW1aFjp_djXmDRPbfY3XMMcLogTz2bWZ2KqmIJI6q6wKe2WYnrRsa9KVeU9kCBBo2v7BzPxF_Bx2DKiqh63SGoRoc6Njti48z_yL71XHQAcgAur6rXRpcqH3l-4knZF23Utsbq2MircEqmw-G__xR1TdZ1r7zb7XLezmx3etkvGr-ze6NdGdW92azUfpcdluWvr-aqbh_nofnqcWI3aYyOsBV7giduRUO7187LMKTT5rxvHHX80_t8IeeMgLquvL7-Ak3q-kz8BAAA&runQuery=true&timeRangeId=week)**

### <a name="describe-the-query-and-specify-the-tables-to-search"></a>Descrivere la query e specificare le tabelle in cui eseguire la ricerca
All'inizio della query è stato aggiunto un breve commento per descriverlo. Questo commento è utile se successivamente si decide di salvare la query e condividerla con altri utenti dell'organizzazione.

```kusto
// Finds PowerShell execution events that could involve a download
```
La query stessa inizierà in genere con un nome di tabella seguito da diversi elementi che iniziano con una pipe ( `|` ). In questo esempio si inizia creando un'unione di due tabelle e e si aggiungono elementi  `DeviceProcessEvents` tramite pipe in base alle `DeviceNetworkEvents` esigenze.

```kusto
union DeviceProcessEvents, DeviceNetworkEvents
```
### <a name="set-the-time-range"></a>Impostare l'intervallo di tempo
Il primo elemento con pipe è un filtro temporale con ambito per i sette giorni precedenti. La limitazione dell'intervallo di tempo garantisce che le query funzionino bene, restituiscono risultati gestibili e non si esercitino timeout.

```kusto
| where Timestamp > ago(7d)
```

### <a name="check-specific-processes"></a>Controllare processi specifici
L'intervallo di tempo è immediatamente seguito da una ricerca di nomi di file di processo che rappresentano l'applicazione PowerShell.

```kusto
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
```

### <a name="search-for-specific-command-strings"></a>Cercare stringhe di comando specifiche
In seguito, la query cerca le stringhe nelle righe di comando che in genere vengono usate per scaricare i file tramite PowerShell.

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
Ora che la query identifica chiaramente i dati che si desidera individuare, è possibile definire l'aspetto dei risultati. `project` restituisce colonne specifiche e `top` limita il numero di risultati. Questi operatori assicurano che i risultati siano ben formattati e ragionevolmente grandi e facili da elaborare.

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

Selezionare **Esegui query** per visualizzare i risultati. Utilizzare l'icona di espansione nella parte superiore destra dell'editor di query per concentrarsi sulla query di ricerca e sui risultati. 

![Immagine del controllo Expand nell'editor di query di ricerca avanzata](images/advanced-hunting-expand.png)

>[!TIP]
>È possibile visualizzare i risultati delle query come grafici e regolare rapidamente i filtri. Per informazioni dettagliate, [vedere Utilizzo dei risultati delle query](advanced-hunting-query-results.md)

## <a name="learn-common-query-operators-for-advanced-hunting"></a>Informazioni sugli operatori di query più comuni per la Ricerca avanzata

È stata appena eseguita la prima query e si ha un'idea generale dei relativi componenti. È il momento di eseguire il backtracking leggermente e apprendere alcune nozioni di base. Il linguaggio delle query di Esplora dati usato in Ricerca avanzata supporta una serie di operatori, di seguito sono elencati i più comuni.

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

Per visualizzare un esempio reale di questi  operatori, eseguili dalla sezione Introduzione della pagina di ricerca avanzata.

## <a name="understand-data-types"></a>Informazioni sui tipi di dati

La ricerca avanzata supporta i tipi di dati Kusto, inclusi i tipi comuni seguenti:

| Tipo di dati | Descrizione e implicazioni delle query |
|--|--|
| `datetime` | Informazioni sui dati e sull'ora che in genere rappresentano i timestamp degli eventi. [Vedere formati di datetime supportati](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/datetime) |
| `string` | Stringa di caratteri in FORMATO UTF-8 racchiusa tra virgolette singole ( ) o `'` doppie ( `"` ). [Altre informazioni sulle stringhe](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/string) |
| `bool` | Questo tipo di dati supporta `true` o `false` gli stati. [Vedere operatori e valori letterali supportati](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/bool) |
| `int` | Numero intero a 32 bit  |
| `long` | Numero intero a 64 bit |

Per ulteriori informazioni su questi tipi di dati, [vedere Kusto scalar data types](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/).

## <a name="get-help-as-you-write-queries"></a>Ottenere assistenza nella scrittura delle query
Trarre vantaggio dalle seguenti funzionalità per scrivere query più velocemente:

- **Autosuggest:** quando si scrivono query, la ricerca avanzata fornisce suggerimenti da IntelliSense.
- **Albero dello** schema: una rappresentazione dello schema che include l'elenco di tabelle e le relative colonne viene fornita accanto all'area di lavoro. Per altre informazioni, passare il puntatore su un elemento. Fare doppio clic su un elemento per inserirlo nell'editor di query.
- **[Riferimento allo](advanced-hunting-schema-reference.md#get-schema-information-in-the-security-center)** schema: riferimento nel portale con descrizioni di tabelle e colonne, tipi di eventi supportati (valori) `ActionType` e query di esempio

## <a name="work-with-multiple-queries-in-the-editor"></a>Utilizzare più query nell'editor
È possibile utilizzare l'editor di query per sperimentare più query. Per utilizzare più query:

- Separare ogni query con una riga vuota.
- Posizionare il cursore su qualsiasi parte di una query per selezionarla prima di eseguire la query. Verrà eseguita solo la query selezionata. Per eseguire un'altra query, spostare il cursore di conseguenza e selezionare **Esegui query**.

![Immagine dell'editor di query di ricerca avanzata con più ](images/ah-multi-query.png)
 _query Editor di query con più query_

## <a name="use-sample-queries"></a>Usare query di esempio

La sezione **Introduzione** presenta alcune semplici query che impiegano operatori di uso comune. Provare a eseguire queste query e apportare piccole modifiche.

![Immagine della scheda per iniziare la ricerca avanzata](images/atp-advanced-hunting.png)

> [!NOTE]
> Oltre agli esempi di query di base, è anche possibile accedere [query condivise](advanced-hunting-shared-queries.md) per specifici scenari di ricerca delle minacce. Esplorare le query condivise sul lato sinistro della pagina o [nell'archivio di query GitHub.](https://aka.ms/hunting-queries)

## <a name="access-comprehensive-query-language-reference"></a>Informazioni di riferimento complete sul linguaggio di query di Access

Per informazioni dettagliate sul linguaggio di query, vedere [la documentazione relativa al linguaggio di query Kusto.](https://docs.microsoft.com/azure/kusto/query/)

## <a name="related-topics"></a>Argomenti correlati
- [Panoramica della rilevazione avanzata](advanced-hunting-overview.md)
- [Usare i risultati delle query](advanced-hunting-query-results.md)
- [Utilizzare le query condivise](advanced-hunting-shared-queries.md)
- [Comprensione dello schema](advanced-hunting-schema-reference.md)
- [Applicare le procedure consigliate per le query](advanced-hunting-best-practices.md)
