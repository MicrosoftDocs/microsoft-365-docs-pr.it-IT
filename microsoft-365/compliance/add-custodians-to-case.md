---
title: Aggiungere i custodi a un Advanced eDiscovery caso
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
description: Informazioni su come usare lo strumento di gestione dei depositario incorporato in Advanced eDiscovery per coordinare i flussi di lavoro e identificare le origini dati pertinenti in un caso.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9468fb889e9115b3652d1dba8a6c6632bb367fe3
ms.sourcegitcommit: 36d12e02f6fda199ae7f2fb72fe52d7e2b5b4efd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/31/2020
ms.locfileid: "49740343"
---
# <a name="add-custodians-to-an-advanced-ediscovery-case"></a>Aggiungere i custodi a un Advanced eDiscovery caso

Usa lo strumento di gestione dei depositario incorporato in Advanced eDiscovery per coordinare i flussi di lavoro sulla gestione dei depositati e sull'identificazione delle origini dati rilevanti e di custodia associate a un caso. Quando si aggiunge un responsabile, il sistema può identificare e posizionare automaticamente un blocco sulla cassetta postale Exchange e sull OneDrive for Business account. Durante il processo di individuazione dell'indagine, è anche possibile identificare altre origini dati (ad esempio cassette postali, siti o Teams) a cui un responsabile ha eseguito l'accesso o ha contribuito. In questo caso, è possibile utilizzare lo strumento di gestione del responsabile per associare tali origini dati a un responsabile specifico. Dopo aver aggiunto i custodi a un caso e aver associato un'altra origine dati, è possibile conservare rapidamente i dati ed eseguire ricerche nei dati del depositario.

È possibile aggiungere e gestire i depositati in Advanced eDiscovery casi in quattro passaggi:

1. Identificare i custodi.

2. Scegliere posizioni dei dati di archiviazione.

3. Configurare le impostazioni di blocco.

4. Esaminare i custodi e completare il processo.

   [![Scheda Origini in Advanced eDiscovery caso ](../media/AeD-Sources-Tab.png)](../media/AeD-Sources-Tab.png#lightbox)

## <a name="make-sure-you-have-the-necessary-permissions"></a>Assicurarsi di disporre delle autorizzazioni necessarie

Per aggiungere i custodi a un caso, è necessario essere membri del gruppo di ruoli Manager eDiscovery. In questo modo è possibile ottenere le autorizzazioni necessarie per aggiungere i custodi a un caso e mettere un blocco sulle origini dati di custodia. Per altre informazioni, vedere [Assegnare autorizzazioni di eDiscovery](get-started-with-advanced-ediscovery.md#step-2-assign-ediscovery-permissions).

## <a name="step-1-identify-custodians"></a>Passaggio 1: identificare i custodi

1. Accedere a e accedere con un account utente a cui sono state assegnate [https://compliance.microsoft.com](https://compliance.microsoft.com) le autorizzazioni di eDiscovery appropriate.

2. Nel riquadro di spostamento sinistro del Centro conformità Microsoft 365, fare clic su **Mostra tutto**, quindi su **eDiscovery > Advanced**.

3. Nella pagina **Advanced eDiscovery,** fare clic sulla **scheda** Casi e quindi selezionare il caso a cui si desidera aggiungere i custodi.

4. Fare clic **sulla scheda Origini** dati e quindi su Aggiungi origine **dati** Aggiungi  >  **nuovi custodi.**

5. Aggiungere uno o più utenti dell'organizzazione come custodi del caso digitando la prima parte del nome o dell'alias di una persona. Dopo aver trovato la persona corretta, selezionarne il nome per aggiungerla all'elenco.

## <a name="step-2-choose-custodian-data-locations"></a>Passaggio 2: Scegliere le posizioni dei dati di custodia

Dopo aver selezionato i custodi, il sistema tenta automaticamente di identificare e verificare questi utenti e le relative origini dati. Dopo aver aggiunto i custodi all'elenco, lo strumento include automaticamente la cassetta postale principale e OneDrive account per ogni responsabile. È possibile scegliere di non includere queste origini dati quando si aggiungono custodi al caso.

Oltre alla cassetta postale e all'account OneDrive di un responsabile, è anche possibile associare altre posizioni dati a un responsabile, ad esempio un sito di SharePoint o un team Microsoft di cui è membro il responsabile. In questo modo è possibile conservare, raccogliere, analizzare ed esaminare il contenuto in altre origini dati associate ai custodi del caso.

Per deselezionare la cassetta postale principale e OneDrive per un responsabile:

1. Espandere il responsabile per visualizzare le posizioni dei dati principali associate automaticamente a ogni responsabile.

2. Selezionare **Cancella**  accanto a Cassetta postale **o OneDrive** per rimuovere la cassetta postale o l'account OneDrive di un responsabile dall'associazione come posizione dati per questo responsabile.

   ![Configurare le posizioni da associare a un responsabile](../media/ConfigureCustodianLocations.png)

Per associare altre cassette postali, siti, Teams o Yammer a un responsabile specifico:

1. Espandere un responsabile per visualizzare i servizi seguenti per associare le posizioni dei dati al responsabile. Fare **clic su** Modifica accanto a un servizio per aggiungere una posizione dati.

   - **Exchange**: utilizzare per associare altre cassette postali al responsabile. Digitare nella casella di ricerca il nome o l'alias (almeno tre caratteri) delle cassette postali degli utenti o dei gruppi di distribuzione. Selezionare le cassette postali da assegnare al responsabile, quindi fare clic su **Aggiungi.**

   - **SharePoint**: consente di associare SharePoint siti al responsabile. Selezionare un sito nell'elenco o cercare un sito digitando un URL nella casella di ricerca. Selezionare i siti da assegnare al responsabile e quindi fare clic su **Aggiungi.**

   - **Teams**: consente di assegnare il Microsoft Teams di cui il responsabile è attualmente membro. Selezionare i team da assegnare al responsabile e quindi fare clic su **Aggiungi.** Dopo aver aggiunto un team, il sistema identifica e individua automaticamente la cassetta postale del sito e del gruppo SharePoint associata al team e li assegna al responsabile.

   - **Yammer**: consente di assegnare i Yammer di cui il responsabile è attualmente membro. Selezionare i gruppi da assegnare al responsabile e quindi fare clic su **Aggiungi.** Dopo aver aggiunto un team, il sistema identifica e individua automaticamente il sito SharePoint e la cassetta postale del gruppo associata a tale gruppo e li assegna al responsabile.

   > [!NOTE]
   > È possibile  utilizzare le opzioni di selezione Exchange e **SharePoint** per associare altri team o gruppi di Yammer (di cui un responsabile non è membro) a un responsabile. A tale scopo, è necessario aggiungere sia la cassetta postale che il sito associati a ogni team o Yammer gruppo.

2. È possibile visualizzare il numero totale di cassette postali, siti, Teams e gruppi di Yammer assegnati a ogni responsabile espandendo ogni responsabile nella tabella. Dopo aver finalizzato le posizioni dei dati assegnate per ogni responsabile, queste associazioni verranno mantenute e utilizzate durante le fasi di raccolta, elaborazione e revisione nel flusso di lavoro Advanced eDiscovery.

3. Dopo aver aggiunto i custodi e aver configurato le posizioni dei dati, fare clic su **Avanti** per passare alla pagina **Impostazioni di blocco.**  

## <a name="step-3-configure-hold-settings"></a>Passaggio 3: Configurare le impostazioni di blocco

 Dopo aver finalizzato i custodi e le relative posizioni dei dati, puoi mettere in attesa alcuni o tutti i custodi. Quando si mette in attesa un responsabile, tutto il contenuto in tutte le posizioni di contenuto associate al custode viene conservato fino a quando non si rimuove il blocco o non si rilascia il responsabile dall'esenzione. In alcuni casi, potresti voler aggiungere i custodi a un caso senza metterli in attesa.

Per mettere in attesa i custodi e le origini dati:

1. Nella pagina **Impostazioni esenzione** è possibile applicare un blocco ai singoli custodi selezionando la casella di controllo nella **colonna Esenzione.**

   In alternativa, puoi mettere in attesa tutti i custodi selezionando la casella **di** controllo Esenzione nella parte superiore della colonna.

2. Verificare le selezioni di blocco del responsabile e quindi fare clic su **Avanti.**

   > [!NOTE]
   > Se non si dispone di un'esenzione per un responsabile, il responsabile e le origini dati associate verranno aggiunti al caso, ma il contenuto di tali origini dati non verrà conservato dal blocco associato al caso.

## <a name="step-4-review-the-custodians-and-complete-the-process"></a>Passaggio 4: esaminare i custodi e completare il processo

Prima di aggiungere effettivamente i custodi al caso, è possibile esaminare l'elenco dei custodi, le posizioni dei dati a loro assegnate e le impostazioni di conservazione.

1. Verificare ed esaminare tutte le origini dati e l'impostazione di conservazione associata a ogni responsabile della tabella. Se necessario, tornare alle pagine  Identificare il **responsabile o** le impostazioni di blocco per apportare eventuali modifiche.

2. Fai **clic su** Invia per aggiungere i custodi e le relative posizioni di dati al caso e applicare tutte le impostazioni di conservazione.

   I nuovi custodi vengono aggiunti al caso e visualizzati nella **scheda Origini** dati.

   [![Custodi elencati nella scheda Origini dati ](../media/DataSourcesTab.png)](../media/DataSourcesTab.png#lightbox)
