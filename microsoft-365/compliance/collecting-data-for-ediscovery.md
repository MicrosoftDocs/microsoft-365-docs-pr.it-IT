---
title: Raccogliere i dati per un caso in Advanced eDiscovery
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
description: Informazioni su come identificare un set di documenti per la revisione in un'indagine tramite lo strumento di ricerca in Advanced eDiscovery.
ms.custom: seo-marvel-2020
ms.openlocfilehash: 725c289324a8e4d5bd4d7a7b9ddd9e091b6d6241
ms.sourcegitcommit: a3c2c737995088c1bad3b12ab401a7ef242b0272
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2020
ms.locfileid: "47956199"
---
# <a name="collect-data-for-a-case-in-advanced-ediscovery"></a>Raccogliere i dati per un caso in Advanced eDiscovery

Dopo aver identificato i depositari e le origini dati di interesse per il caso, è necessario identificare il set di documenti in cui eseguire l'approfondimento. È possibile utilizzare lo strumento di ricerca in Advanced eDiscovery per identificare i documenti rilevanti provenienti da posizioni detentive e non detentive in Microsoft 365.

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

## <a name="add-search-results-to-a-review-set"></a>Aggiungere i risultati della ricerca a un insieme da rivedere

Quando si è pronti per la raccolta e l'elaborazione di tutti i risultati di una ricerca, è possibile farlo aggiungendola a un set di revisione. Per ulteriori informazioni, vedere [Add Data to a Review set](add-data-to-review-set.md).

## <a name="add-non-microsoft-365-data-to-a-review-set"></a>Aggiungere dati non Microsoft 365 a un set di Revisione

Come parte del processo di raccolta per un caso, è anche possibile aggiungere dati non di Office 365 a un set di revisione ed esaminare e analizzare insieme ai dati di Office 365 raccolti tramite lo strumento di ricerca. Quando si aggiungono non Office 365, è necessario associarlo a un determinato custode nel caso. Per ulteriori informazioni, vedere [caricare i dati non Microsoft 365 in un set di revisione](load-non-Office-365-data-into-a-review-set.md).
