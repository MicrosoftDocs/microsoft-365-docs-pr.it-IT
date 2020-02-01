---
title: Raccogliere i dati per un caso in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: esclee
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
ms.openlocfilehash: a6b86d9f86edc427e10c02a99e3cda3e5e79db66
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595853"
---
# <a name="collect-data-for-a-case-in-advanced-ediscovery"></a>Raccogliere i dati per un caso in Advanced eDiscovery

Dopo aver identificato i depositari e le origini dati di interesse per il caso, è necessario identificare il set di documenti in cui eseguire l'approfondimento. È possibile utilizzare lo strumento di ricerca in Advanced eDiscovery per identificarli da posizioni detentive e non detentive in Office 365.

Dopo aver eseguito una ricerca, è possibile visualizzare le statistiche sugli elementi recuperati, ad esempio le posizioni con la maggior parte degli elementi corrispondenti alla query di ricerca. È inoltre possibile visualizzare in anteprima un sottoinsieme dei risultati. Dopo aver identificato il set di documenti che si desidera esaminare ulteriormente, è possibile aggiungere i risultati della ricerca a un set di revisione da raccogliere ed elaborare.

## <a name="create-a-search"></a>Creare una ricerca

Selezionando **nuova ricerca** nella scheda **ricerche** verrà avviata una procedura guidata che consentirà di creare una ricerca. Per informazioni dettagliate su come creare una ricerca, vedere [creare una ricerca per raccogliere i dati](create-search-to-collect-data.md).

Dopo la creazione di una ricerca, viene visualizzata una pagina a comparsa con dettagli. I pulsanti **statistiche** e **Anteprima** non sono disponibili inizialmente perché la ricerca non è ancora stata completata. È possibile tenere conto dello stato di avanzamento della ricerca nella scheda **ricerche** .

## <a name="view-search-results-and-statistics"></a>Visualizzare i risultati della ricerca e le statistiche

Sono disponibili due componenti di una ricerca di contenuto: statistiche (stime) e anteprima. Dopo aver completato ognuno di questi componenti, lo stato visualizzato nelle colonne corrispondenti nella scheda **ricerche** cambia da **inviato** a **in corso** a **completato**.

Una volta completata la stima della ricerca, selezionare la ricerca per visualizzare la pagina del riquadro a comparsa, in cui vengono visualizzate le statistiche di alto livello sui risultati della ricerca. A questo punto, il pulsante **statistiche** sarà attivo. È possibile selezionarla per visualizzare le statistiche di ricerca, ad esempio:

- Riepilogo
- Posizioni principali
- Query

Per ulteriori informazioni sulle statistiche di ricerca, vedere [Search Statistics](search-statistics.md).

Dopo aver completato l'anteprima, il pulsante **Anteprima** sarà attivo. Selezionarla per visualizzare in anteprima un sottoinsieme di campionamento dei risultati.

## <a name="adding-search-results-to-a-review-set"></a>Aggiunta dei risultati di ricerca a un set di Revisione

Quando si è pronti per la raccolta e l'elaborazione di tutti i risultati di una ricerca, è possibile farlo aggiungendola a un set di revisione. Per ulteriori informazioni, vedere [Add Data to a Review set](add-data-to-review-set.md).
