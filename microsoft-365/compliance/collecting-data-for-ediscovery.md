---
title: Raccogliere dati per un caso in Advanced eDiscovery
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
description: Informazioni su come identificare un set di documenti da rivedere in un'indagine utilizzando lo strumento di ricerca in Advanced eDiscovery.
ms.custom: seo-marvel-2020
ms.openlocfilehash: b69127f1a372a9b843b9c7dac1b2909dd80b2988
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751269"
---
# <a name="collect-data-for-a-case-in-advanced-ediscovery"></a>Raccogliere dati per un caso in Advanced eDiscovery

Dopo aver identificato i responsabile e le origini dati di interesse per il caso, è il momento di identificare il set di documenti da approfondire. È possibile utilizzare lo strumento di ricerca in Advanced eDiscovery per identificare i documenti rilevanti da posizioni di depositario e non responsabile in Microsoft 365.

Dopo aver eseguito una ricerca, è possibile visualizzare le statistiche relative agli elementi recuperati, ad esempio le posizioni con il maggior numero di elementi corrispondenti alla query di ricerca. È inoltre possibile visualizzare in anteprima un sottoinsieme dei risultati. Dopo aver identificato il set di documenti che si desidera esaminare ulteriormente, è possibile aggiungere i risultati della ricerca a un insieme da raccogliere ed elaborare.

## <a name="create-a-search"></a>Creare una ricerca

Se **si seleziona Nuova** ricerca nella scheda **Ricerche,** verrà avviata una procedura guidata che guida l'utente nella creazione di una ricerca. Per informazioni dettagliate su come creare una ricerca, vedere [Creare una ricerca per raccogliere dati.](create-search-to-collect-data.md)

Dopo la creazione di una ricerca, viene visualizzata una pagina a comparsa con i dettagli. I **pulsanti Statistiche** e **Anteprima** non sono inizialmente disponibili perché la ricerca non è ancora stata completata. È possibile tenere traccia dell'avanzamento della ricerca nella **scheda** Ricerche.

## <a name="view-search-results-and-statistics"></a>Visualizzare i risultati e le statistiche della ricerca

Esistono due componenti di una ricerca di contenuto: Statistiche (stime) e Anteprima. Al termine di ognuno di questi componenti, lo stato visualizzato  nelle colonne  corrispondenti nella scheda Ricerche cambia da Inviato **a In corso** e **Completato.**

Una volta completata la stima della ricerca, selezionare la ricerca per visualizzare la pagina del riquadro a comparsa, in cui verranno visualizzate alcune statistiche di alto livello sui risultati della ricerca. A questo punto, il **pulsante** Statistiche sarà attivo. È possibile selezionarlo per visualizzare le statistiche di ricerca, ad esempio:

- Riepilogo
- Posizioni principali
- Query

Per ulteriori informazioni sulle statistiche di ricerca, vedere [Statistiche della ricerca.](search-statistics-in-advanced-ediscovery.md)

Al termine dell'anteprima, il **pulsante** Anteprima sarà attivo. Selezionarlo per visualizzare un'anteprima di un sottoinsieme campionato dei risultati.

## <a name="add-search-results-to-a-review-set"></a>Aggiungere i risultati della ricerca a un insieme da rivedere

Quando si è pronti per raccogliere ed elaborare tutti i risultati di una ricerca, è possibile aggiungerli a un insieme da rivedere. Per informazioni dettagliate, vedere [Aggiungere dati a un insieme da rivedere.](add-data-to-review-set.md)

## <a name="add-non-microsoft-365-data-to-a-review-set"></a>Aggiungere dati non Di Microsoft 365 a un insieme da rivedere

Come parte del processo di raccolta di un caso, è anche possibile aggiungere dati non di Office 365 a un insieme da rivedere e analizzare insieme ai dati di Office 365 raccolti tramite lo strumento di ricerca. Quando si aggiunge non Office 365, è necessario associarlo a un responsabile specifico nel caso. Per ulteriori informazioni, vedere [Caricare dati non Di Microsoft 365 in un insieme da rivedere.](load-non-Office-365-data-into-a-review-set.md)
