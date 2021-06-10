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
description: Quando un responsabile viene aggiunto a un caso Advanced eDiscovery, qualsiasi contenuto considerato parzialmente indicizzato viene rielaborato per renderlo completamente ricercabile.
ms.openlocfilehash: 904c8fe626ce8ece8f4b48bd5504e4011e9f4fb2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911210"
---
# <a name="advanced-indexing-of-custodian-data"></a>Indicizzazione avanzata dei dati dei responsabili

Quando un responsabile viene aggiunto a un caso Advanced eDiscovery, qualsiasi contenuto considerato parzialmente indicizzato viene rielaborato per renderlo completamente ricercabile.  Questo processo è denominato *indicizzazione avanzata.* Il contenuto può essere parzialmente indicizzato per diversi motivi, tra cui l'esistenza di immagini, tipi di file non supportati o quando vengono rilevati limiti di dimensione dei file di indicizzazione.

Per ulteriori informazioni sul supporto dell'elaborazione e sugli elementi parzialmente indicizzati, vedere:

- [Tipi di file supportati in Advanced eDiscovery](supported-filetypes-ediscovery20.md)

- [Elementi parzialmente indicizzati in Ricerca contenuto in Office 365](partially-indexed-items-in-content-search.md)

- [Formati di file indicizzati dalla ricerca di Exchange](/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [Estensioni dei nomi di file sottoposti a ricerca per indicizzazione e tipi di file analizzati predefiniti in SharePoint Server](/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a>Visualizzazione dei risultati di indicizzazione avanzati

Al termine del processo di indicizzazione avanzata, è possibile comprendere l'efficacia della rielaborazione.  Nella visualizzazione Risultati di indicizzazione avanzata della scheda **Elaborazione** di un caso, nel grafico viene elencato il numero di elementi aggiunti all'indice *ibrido.*  L'indice ibrido è il Advanced eDiscovery il contenuto rielaborato.

Questa visualizzazione include anche il numero di elementi che richiedono la correzione e un altro grafico di errori per tipo di file. Per altre informazioni, vedere:

- [Correzione degli errori durante l'elaborazione dei dati](error-remediation-when-processing-data-in-advanced-ediscovery.md)

- [Correzione degli errori dei singoli elementi](single-item-error-remediation.md)

## <a name="updating-the-advanced-index-for-custodians"></a>Aggiornamento dell'indice avanzato per i custodi

Quando un responsabile viene aggiunto a un caso Advanced eDiscovery, tutti gli elementi parzialmente indicizzati vengono rielaborati. Tuttavia, con il passare del tempo, è possibile aggiungere elementi indicizzati più parzialmente alla cassetta postale o all'account OneDrive utente.  Se necessario, è possibile aggiornare l'indice per un responsabile specifico. Per ulteriori informazioni, vedere [Manage custodians in an Advanced eDiscovery case](manage-new-custodians.md#re-index-custodian-data). È inoltre possibile aggiornare l'indice per tutti i custodi in un caso facendo clic su **Aggiorna indice** nella **scheda** Elaborazione.

> [!NOTE]
> L'aggiornamento degli indici di custodia è un processo a esecuzione lunga. È consigliabile non aggiornare gli indici più di una volta al giorno in un caso.