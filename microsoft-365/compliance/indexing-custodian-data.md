---
title: Indicizzazione avanzata dei dati dei responsabili
f1.keywords:
- NOCSH
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
description: Quando un responsabile viene aggiunto a un caso di Advanced eDiscovery, tutti i contenuti considerati parzialmente indicizzati vengono rielaborati per renderlo completamente disponibile per la ricerca.
ms.openlocfilehash: 908d01cacc103639e1f9efe965240c33a5296ba9
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/05/2021
ms.locfileid: "49750757"
---
# <a name="advanced-indexing-of-custodian-data"></a>Indicizzazione avanzata dei dati dei responsabili

Quando un responsabile viene aggiunto a un caso di Advanced eDiscovery, tutti i contenuti considerati parzialmente indicizzati vengono rielaborati per renderlo completamente disponibile per la ricerca.  Questo processo è denominato *indicizzazione avanzata.* Il contenuto può essere parzialmente indicizzato per diversi motivi, tra cui l'esistenza di immagini, tipi di file non supportati o quando vengono rilevati limiti di dimensione dei file di indicizzazione.

Per ulteriori informazioni sull'elaborazione del supporto e sugli elementi parzialmente indicizzati, vedere:

- [Tipi di file supportati in Advanced eDiscovery](supported-filetypes-ediscovery20.md)

- [Partially indexed items in Content Search in Office 365](partially-indexed-items-in-content-search.md) (Elementi parzialmente indicizzati in Ricerca contenuto in Office 365)

- [Formati di file indicizzati dalla ricerca di Exchange](https://docs.microsoft.com/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [Estensioni dei nomi di file sottoposti a ricerca per indicizzazione e tipi di file analizzati predefiniti in SharePoint Server](https://docs.microsoft.com/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a>Visualizzazione dei risultati di indicizzazione avanzati

Una volta completato il processo di indicizzazione avanzata, è possibile comprendere l'efficacia della rielaborazione.  Nella visualizzazione dei risultati di indicizzazione avanzata nella scheda **Elaborazione** di un caso, nel grafico viene elencato il numero di elementi aggiunti all'indice *ibrido.*  L'indice ibrido è dove Advanced eDiscovery archivia il contenuto rielaborato.

Questa visualizzazione include anche il numero di elementi che richiedono la correzione e un altro grafico degli errori in base al tipo di file. Per altre informazioni, vedere:

- [Correzione degli errori durante l'elaborazione dei dati](error-remediation-when-processing-data-in-advanced-ediscovery.md)

- [Correzione degli errori dei singoli elementi](single-item-error-remediation.md)

## <a name="updating-the-advanced-index-for-custodians"></a>Aggiornamento dell'indice avanzato per i responsabile

Quando un responsabile viene aggiunto a un caso di Advanced eDiscovery, tutti gli elementi parzialmente indicizzati vengono rielaborati. Tuttavia, con il passare del tempo, è possibile aggiungere elementi indicizzati più parzialmente alla cassetta postale o all'account di OneDrive di un utente.  Se necessario, è possibile aggiornare l'indice per un responsabile specifico. Per ulteriori informazioni, vedere [Gestire i responsabile in un caso di Advanced eDiscovery.](manage-new-custodians.md#re-index-custodian-data) È inoltre possibile aggiornare l'indice di tutti i responsabile in un caso facendo clic sull'indice **Di** aggiornamento nella **scheda** Elaborazione.

> [!NOTE]
> L'aggiornamento degli indici dei responsabile è un processo di lunga durata. È consigliabile non aggiornare gli indici più di una volta al giorno in un caso.
