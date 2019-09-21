---
title: Indicizzazione avanzata dei dati per un'indagine
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 3d562dbc1fc696b1e6d2acccc92f69385da49510
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37082858"
---
# <a name="advanced-indexing-of-data-for-an-investigation"></a>Indicizzazione avanzata dei dati per un'indagine

Il contenuto del sistema attivo può essere parzialmente indicizzato per una serie di motivi, tra cui l'esistenza di immagini, tipi di file non supportati o durante l'indicizzazione dei limiti delle dimensioni dei file. Quando si ha a che fare con la fuoriuscita di dati ad alto rischio, è necessario assicurarsi che la ricerca abbia acquisito tutti i dati che si desidera esaminare. Quando una persona di interesse viene aggiunta a un'analisi dei dati, qualsiasi contenuto di Office 365 ritenuto rielaborato parzialmente indicizzato viene rielaborato per renderlo completamente ricercabile. Questo processo è denominato *Advanced indicizzazione*. 

Per ulteriori informazioni sull'elaborazione del supporto in Office 365 e sugli elementi parzialmente indicizzati, vedere:

- [Tipi di file supportati nelle indagini sui dati](supported-filetypes-datainvestigations.md)

- [Partially indexed items in Content Search in Office 365](partially-indexed-items-in-content-search.md) (Elementi parzialmente indicizzati in Ricerca contenuto in Office 365)

- [Formati di file indicizzati dalla ricerca di Exchange](https://docs.microsoft.com/en-us/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [Estensioni dei nomi di file sottoposti a ricerca per indicizzazione e tipi di file analizzati predefiniti in SharePoint Server](https://docs.microsoft.com/en-us/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a>Visualizzazione dei risultati di indicizzazione avanzati

Una volta completato il processo di indicizzazione avanzato, è possibile ottenere informazioni sull'efficacia del rielaborazione.  Nella visualizzazione indicizzazione persone di interesse, nel grafico vengono elencati tutti gli elementi aggiunti all' *Indice ibrido*.  L'indice ibrido è la posizione in cui l'analisi dei dati (Preview) archivia il contenuto rielaborato.

Il grafico include anche il numero di elementi che richiedono la correzione e un altro grafico degli errori per tipo di file. Per ulteriori informazioni, vedere [correzione degli errori durante l'elaborazione dei dati](error-remediation.md).

## <a name="updating-advanced-indexes-for-people-of-interest"></a>Aggiornamento degli indici avanzati per gli utenti interessati

Quando una persona di interesse viene aggiunta a un'analisi dei dati, tutti gli elementi parzialmente indicizzati vengono rielaborati. Tuttavia, con il passare del tempo, è possibile aggiungere elementi indicizzati in modo più parziale alla cassetta postale o all'account di OneDrive di un utente.  Se necessario, è possibile aggiornare gli indici.

> [!NOTE]
> L'aggiornamento degli indici degli utenti è un processo a esecuzione prolungata. Si consiglia di non aggiornare gli indici più di una volta al giorno in un'indagine.
