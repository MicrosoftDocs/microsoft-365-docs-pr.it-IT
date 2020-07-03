---
title: Aggiungere origini dati non detentive a un caso avanzato di eDiscovery
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
description: È possibile aggiungere origini dati non detentive a un caso di eDiscovery avanzato e inserire un'esenzione nell'origine dati. Le origini dati non detentive vengono reindicizzate, pertanto qualsiasi contenuto ritenuto parzialmente indicizzato viene rielaborato per renderlo completamente e rapidamente ricercabile.
ms.openlocfilehash: 2009a8cc82dc9407e9871409e85cdcd321ea9bb0
ms.sourcegitcommit: 51a9f34796535309b8ca8b52da92da0a3621327b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2020
ms.locfileid: "45024746"
---
# <a name="add-non-custodial-data-sources-to-an-advanced-ediscovery-case"></a>Aggiungere origini dati non detentive a un caso avanzato di eDiscovery

In Advanced eDiscovery casi, non sempre soddisfare le proprie esigenze per associare un'origine dati Microsoft 365 con un custode nel caso. Tuttavia, potrebbe essere necessario associare tali dati a un caso in modo che sia possibile cercarlo, aggiungerlo al set di revisione e rivederlo. La nuova funzionalità denominata *origini dati non detentive* consente di aggiungere dati a un caso senza dover associare i dati a un custode. Applica inoltre la stessa funzionalità avanzata di eDiscovery ai dati non detentivi disponibili per i dati associati al custode. Due delle funzionalità più utili che è possibile applicare ai dati non detentivi sono l'inserimento e l'elaborazione in attesa tramite l' [indicizzazione avanzata](indexing-custodian-data.md).

## <a name="add-a-non-custodial-data-source"></a>Aggiunta di un'origine dati non priva di detenzione

Eseguire la procedura seguente per aggiungere e gestire origini dati non detentive in un caso di eDiscovery avanzato.

1. Nella Home page di **Advanced eDiscovery** fare clic sul caso per il quale si desidera aggiungere i dati.

2. Nella pagina **origini** fare clic sulla scheda **percorsi dati** e quindi fare clic su **Aggiungi percorso dati**.

3. Fare clic su **Aggiungi percorso dati** e scegliere le origini dati che si desidera aggiungere al caso. È possibile aggiungere più cassette postali e siti.

4. Nella pagina **scegliere i percorsi** della procedura guidata, aggiungere le cassette postali o i siti (o entrambi) come origini dati non detentive al caso.

5. Dopo aver aggiunto le origini dati, fare clic su **Avanti**.

6. Nella pagina **Place** holds scegliere le origini dati che si desidera inserire in attesa selezionando o deselezionando la casella di controllo associata.

7. Verificare le selezioni di blocco e quindi fare clic su **Invia**.

   Ogni origine dati non priva di detenzione aggiunta è elencata nella pagina **origini dati** .

   Inoltre, un processo denominato *reindicizzazione dei dati non detentivi* viene creato e visualizzato nella scheda **processi** del caso. Una volta creato, il processo di indicizzazione avanzato è stato avviato e le origini dati vengono reindicizzate.

## <a name="managing-the-hold-on-non-custodial-data-sources"></a>Gestione del blocco su origini dati non detentive

Dopo aver posizionato un'esenzione su un'origine dati non di detenzione, viene creato automaticamente un criterio di conservazione che contiene tutte le origini dati non detentive del caso. Quando si impostano altre origini dati non detentive, queste vengono aggiunte ai criteri di blocco.

1. Nella **Home** page del caso, fare clic sulla scheda **esenzioni** .

2. Nella pagina **esenzioni** e fare clic su **NCDSHold \<GUID\> -**, in cui il valore GUID è univoco per il caso.

3. Nella pagina a comparsa fare clic su **Modifica blocco** per visualizzare tutte le origini dati non detentive che sono state inserite in attesa.

È possibile eseguire le seguenti attività di gestione su origini dati non detentive:

- È possibile modificare il blocco per creare un blocco basato su query applicato a tutte le origini dati non detentive nel caso.

- È possibile rilasciare un'origine dati non detentiva dall'esenzione. Il rilascio di un'origine dati non rimuove l'origine dati non affidatario dal caso. Rimuove solo il blocco che è stato inserito nell'origine dati.
