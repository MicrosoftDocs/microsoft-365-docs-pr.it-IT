---
title: Creare query di ricerca
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
description: Utilizzare parole chiave e condizioni per limitare l'ambito della ricerca durante la ricerca di dati con Advanced eDiscovery in Microsoft 365.
ms.openlocfilehash: 7a6d175016053cd963b03cae91ff43f9c4b3336c
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41596293"
---
# <a name="build-search-queries"></a>Creare query di ricerca

Quando si crea una query di ricerca, è possibile utilizzare parole chiave per individuare contenuti e condizioni specifici per limitare l'ambito della ricerca per restituire gli elementi più rilevanti per la propria indagine legale.

![Utilizzare parole chiave e condizioni per limitare i risultati di una ricerca](media/SearchQueryBox.png)

## <a name="keyword-searches"></a>Ricerche di parole chiave

Digitare una query di parole chiave nella casella **Keywords** della query di ricerca. È possibile specificare le parole chiave, le proprietà del messaggio di posta elettronica, ad esempio le date inviate e ricevute, o le proprietà del documento, ad esempio i nomi di file o la data dell'Ultima modifica di un documento. È anche possibile usare query più complesse che usano un operatore booleano, ad esempio **AND**, **OR**, **NOT** o **NEAR**. È inoltre possibile cercare informazioni riservate (ad esempio i numeri di previdenza sociale) nei documenti di SharePoint e OneDrive (non nei messaggi di posta elettronica) oppure cercare documenti che sono stati condivisi esternamente. Se si lascia vuota la casella **parole chiave** , tutto il contenuto che si trova nei percorsi di contenuto specificato è incluso nei risultati della ricerca.
    
In alternativa, è possibile selezionare la casella di controllo **Mostra elenco parole chiave** e digitare una parola chiave o una frase di parole chiave in ogni riga. Se si esegue questa operazione, le parole chiave in ogni riga sono connesse da un operatore logico, rappresentato come *c:s* nella sintassi della query di ricerca, che è simile alla funzionalità all'operatore **or** nella query di ricerca creata. Questo significa che gli elementi che contengono qualsiasi parola chiave in qualsiasi riga sono inclusi nei risultati della ricerca.

![Utilizzare l'elenco di parole chiave per ottenere statistiche su ogni parola chiave nella query](media/KeywordListSearch.png)

Perché usare l'elenco di parole chiave? È possibile ottenere statistiche che mostrano quanti elementi corrispondono a ciascuna parola chiave nell'elenco delle parole chiave. In questo modo è possibile identificare rapidamente le parole chiave più (e meno) effettive. È inoltre possibile utilizzare una frase parola chiave (racchiusa tra parentesi) in una riga dell'elenco parole chiave. Per ulteriori informazioni sulle statistiche di ricerca, vedere [Search Statistics](search-statistics.md).

> [!NOTE]
> Per contribuire a ridurre i problemi causati da elenchi di parole chiave di grandi dimensioni, è possibile limitare il numero massimo di 20 righe nell'elenco delle parole chiave.

## <a name="conditions"></a>Condizioni
    
È possibile aggiungere condizioni di ricerca per limitare l'ambito di una ricerca e restituire un insieme di risultati più raffinato. Ogni condizione aggiunge una clausola alla query di ricerca creata ed eseguita all'avvio della ricerca. Una condizione è connessa logicamente alla query di parole chiave specificata nella casella parola chiave da un operatore logico (rappresentato come *c:c* nella sintassi della query di ricerca) simile alla funzionalità all'operatore **and** . Questo significa che gli elementi devono soddisfare sia la query con parole chiave sia una o più condizioni da includere nei risultati della ricerca. Ecco in che modo le condizioni aiutano a limitare i risultati. Per un elenco e una descrizione delle condizioni che è possibile utilizzare in una query di ricerca, vedere la sezione "condizioni di ricerca" in [query di parole chiave e condizioni di ricerca](keyword-queries-and-search-conditions.md#search-conditions).
