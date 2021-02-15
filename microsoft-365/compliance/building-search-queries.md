---
title: Creare query di ricerca in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom: seo-marvel-mar2020
description: Usare parole chiave e condizioni per restringere l'ambito della ricerca durante la ricerca di dati con Advanced eDiscovery in Microsoft 365.
ms.openlocfilehash: 8ec1e099625bb081f8a915f08ac818fddcc2b60d
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751113"
---
# <a name="build-search-collection-queries-in-advanced-ediscovery"></a>Creare query di raccolta di ricerca in Advanced eDiscovery

Quando si compilano query di ricerca per raccogliere dati in un caso di Advanced eDiscovery, è possibile utilizzare le parole chiave per trovare contenuti e condizioni specifici per restringere l'ambito della ricerca per restituire gli elementi più rilevanti per l'indagine legale.

![Utilizzare parole chiave e condizioni per restringere i risultati di una ricerca](../media/SearchQueryBox.png)

## <a name="keyword-searches"></a>Ricerche con parole chiave

Digitare una query con parole chiave nella **casella Parole** chiave della query di ricerca. È possibile specificare parole chiave, proprietà dei messaggi di posta elettronica, ad esempio date di invio e ricezione, oppure proprietà del documento, ad esempio i nomi di file o la data dell'ultima modifica di un documento. È anche possibile usare query più complesse che usano un operatore booleano, ad esempio **AND**, **OR**, **NOT** o **NEAR**. È inoltre possibile cercare informazioni riservate (ad esempio numeri di previdenza sociale) nei documenti in SharePoint e OneDrive (non nei messaggi di posta elettronica) o cercare documenti condivisi esternamente. Se si lascia vuota **la casella Parole** chiave, tutto il contenuto che si trova nei percorsi di contenuto specificati si trova nei risultati della ricerca.

## <a name="keyword-list"></a>Elenco di parole chiave

In alternativa, è  possibile selezionare la casella di controllo Mostra elenco parole chiave e digitare una parola chiave o una frase parola chiave in ogni riga. Le parole chiave in ogni riga sono connesse da un operatore logico (rappresentato come *c:s* nella sintassi della query di ricerca) che ha funzionalità simili all'operatore **OR** nella query di ricerca creata. Ciò significa che gli elementi che contengono qualsiasi parola chiave in qualsiasi riga sono presenti nei risultati della ricerca. È possibile aggiungere fino a 180 righe nell'elenco delle parole chiave nelle query di ricerca advanced eDiscovery.

![Usare l'elenco di parole chiave per ottenere statistiche su ogni parola chiave nella query](../media/KeywordListSearch.png)

Perché usare l'elenco di parole chiave? Puoi ottenere statistiche che mostrano il numero di elementi che corrispondono a ogni parola chiave nell'elenco delle parole chiave. Ciò consente di identificare rapidamente le parole chiave più (e meno efficaci). È inoltre possibile utilizzare una frase parola chiave (racchiusa tra parentesi) in una riga dell'elenco delle parole chiave. Per ulteriori informazioni sulle statistiche di ricerca, vedere [Statistiche della ricerca.](search-statistics-in-advanced-ediscovery.md)

## <a name="conditions"></a>Condizioni

È possibile aggiungere condizioni di ricerca per restringere l'ambito di una ricerca e restituire un set di risultati più perfezionato. Ogni condizione aggiunge una clausola alla query di ricerca creata ed eseguita all'avvio della ricerca. Una condizione è collegata logicamente alla query con parole chiave specificata nella casella delle parole chiave da un operatore logico (rappresentato come *c:c* nella sintassi della query di ricerca) che ha funzionalità simili all'operatore **AND.** Ciò significa che gli elementi devono soddisfare sia la query con parole chiave che una o più condizioni da includere nei risultati della ricerca. Ecco in che modo le condizioni aiutano a limitare i risultati. Per un elenco e una descrizione delle condizioni che è possibile utilizzare in una query di ricerca, vedere la sezione "Condizioni di ricerca" in Query con parole chiave [e condizioni di ricerca.](keyword-queries-and-search-conditions.md#search-conditions)
