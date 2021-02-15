---
title: Aggiungere origini dati non di tipo responsabile a un caso di Advanced eDiscovery
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
description: È possibile aggiungere origini dati non di tipo responsabile a un caso di Advanced eDiscovery e impostare un blocco sull'origine dati. Le origini dati non di responsabilità vengono reindicizzate, quindi qualsiasi contenuto contrassegnato come parzialmente indicizzato viene rielaborato per renderlo completamente e rapidamente disponibile per la ricerca.
ms.openlocfilehash: 467f0e1167bfebe21bd3f2bbd52acd81529b8685
ms.sourcegitcommit: 36d12e02f6fda199ae7f2fb72fe52d7e2b5b4efd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/31/2020
ms.locfileid: "49740353"
---
# <a name="add-non-custodial-data-sources-to-an-advanced-ediscovery-case"></a>Aggiungere origini dati non di tipo responsabile a un caso di Advanced eDiscovery

Nei casi di Advanced eDiscovery, non sempre è necessario associare un'origine dati di Microsoft 365 a un responsabile nel caso. Tuttavia, potrebbe essere comunque necessario associare i dati a un caso in modo da poterli cercare, aggiungerli a un insieme di recensioni e analizzarli e esaminarli. La funzionalità di Advanced eDiscovery è denominata origini dati *non* depositario e consente di aggiungere dati a un caso senza doverlo associare a un responsabile. Applica inoltre la stessa funzionalità advanced eDiscovery ai dati non di tipo depositario disponibili per i dati associati al responsabile. Due delle operazioni più utili che è possibile applicare ai dati non di tipo non responsabile sono la conservazione e l'elaborazione tramite [l'indicizzazione avanzata.](indexing-custodian-data.md)

## <a name="add-a-non-custodial-data-source"></a>Aggiungere un'origine dati non responsabile

Seguire questa procedura per aggiungere e gestire origini dati non di proprietà in un caso di Advanced eDiscovery.

1. Nella home page **di Advanced eDiscovery** fare clic sul caso a cui si desidera aggiungere i dati.

2. Fare clic **sulla scheda Origini** dati e quindi su Aggiungi origine **dati** Aggiungi  >  **percorsi dati.**

3. Nella pagina a comparsa **New non-custodial data locations** scegliere le origini dati che si desidera aggiungere al caso. È possibile aggiungere più cassette postali e siti espandendo le sezioni **di SharePoint** o **Exchange** e quindi facendo clic su **Modifica.**

   ![Aggiungere siti di SharePoint e cassette postali di Exchange come origini dati non di tipo depositario](../media/NonCustodialDataSources1.png)

   - **SharePoint** - Fare clic **su Modifica** per aggiungere siti. Selezionare un sito nell'elenco oppure è possibile cercare un sito digitando l'URL del sito nella barra di ricerca. Selezionare i siti che si desidera aggiungere come origini dati non di tipo responsabile e fare clic su **Aggiungi.**

   - **Exchange** - Fare clic **su Modifica** per aggiungere cassette postali. Digitare un nome o un alias (almeno tre caratteri) nella casella di ricerca per le cassette postali o i gruppi di distribuzione. Selezionare le cassette postali che si desidera aggiungere come origini dati non di proprietà e fare clic su **Aggiungi.**

   > [!NOTE]
   > È possibile utilizzare le **sezioni di SharePoint** ed **Exchange** per aggiungere siti e cassette postali associati a un team o a un gruppo di Yammer come origini dati non di tipo responsabile. È necessario aggiungere separatamente la cassetta postale e il sito associati a un team o a un gruppo di Yammer.

4. Dopo aver aggiunto origini dati non di tipo responsabile, è possibile impostare o meno l'archiviazione di tali posizioni. Selezionare o deselezionare la casella **di** controllo Esenzione accanto all'origine dati per metterla in attesa.

5. Fare **clic** su Aggiungi nella parte inferiore della pagina a comparsa Nuovi percorsi dati **non** di proprietà per aggiungere le origini dati al caso.

   Ogni origine dati non responsabile aggiunta viene elencata nella **pagina Origini** dati. Le origini dati non di tipo responsabile sono identificate dal **valore data location** nella colonna Source **type.**

   ![Origini dati non di tipo responsabile nella scheda Origini dati](../media/NonCustodialDataSources2.png)

Dopo aver aggiunto origini dati non di tipo responsabile al caso, viene creato e visualizzato  nella scheda Processi del caso un processo denominato Reindicizzazione dei dati *non* di tipo non responsabile. Dopo la creazione del processo, viene avviato il processo di indicizzazione avanzata e le origini dati vengono reindicizzate.

## <a name="manage-the-hold-for-non-custodial-data-sources"></a>Gestire l'esenzione per le origini dati non dei depositario

Dopo aver posto un'esenzione su un'origine dati non responsabile, viene creato automaticamente un criterio di blocco contenente le origini dati non di tipo non responsabile per il caso. Quando si posizionano in attesa altre origini dati non di tipo responsabile, queste vengono aggiunte a questo criterio di blocco.

1. Aprire il caso advanced eDiscovery e selezionare la **scheda Esenzione.**

2. Fare **clic su \<GUID\> NCDSHold-**, dove il valore GUID è univoco per il caso.

   Nella pagina a comparsa vengono visualizzate informazioni e statistiche sulle origini dati non riservate all'esenzione.

   ![La pagina a comparsa per il blocco di origini dati non di proprietà visualizza le statistiche](../media/NonCustodialDataSourcesHoldFlyout.png)

3. Fare **clic su Modifica** esenzione per visualizzare le origini dati non di tipo responsabile ed eseguire le attività di gestione seguenti:

   - Nella pagina **Posizioni** è possibile rilasciare un'origine dati non responsabile rimuovendo l'origine dall'esenzione. Il rilascio di un'origine dati non rimuove l'origine dati non responsabile dal caso. Rimuove solo l'esenzione che è stata inserita nell'origine dati.

   - Nella pagina **Query,** è possibile modificare l'esenzione per creare un'esenzione basata su query applicata a tutte le origini dati non-custodial nel caso.
