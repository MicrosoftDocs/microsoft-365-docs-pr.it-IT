---
title: Aggiungere i responsabile a un caso di Advanced eDiscovery
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
description: Informazioni su come utilizzare lo strumento di gestione dei depositario incorporato in Advanced eDiscovery per coordinare i flussi di lavoro e identificare le origini dati pertinenti in un caso.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9468fb889e9115b3652d1dba8a6c6632bb367fe3
ms.sourcegitcommit: 36d12e02f6fda199ae7f2fb72fe52d7e2b5b4efd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/31/2020
ms.locfileid: "49740343"
---
# <a name="add-custodians-to-an-advanced-ediscovery-case"></a>Aggiungere i responsabile a un caso di Advanced eDiscovery

Utilizzare lo strumento di gestione dei responsabile incorporato in Advanced eDiscovery per coordinare i flussi di lavoro relativi alla gestione dei responsabile e all'identificazione delle origini dati rilevanti associate a un caso. Quando si aggiunge un responsabile, il sistema può identificare e inserire automaticamente un blocco nella cassetta postale di Exchange e nell'account OneDrive for Business. Durante il processo di individuazione dell'indagine, è anche possibile identificare altre origini dati (ad esempio cassette postali, siti o Teams) a cui un responsabile ha eseguito l'accesso o a cui ha contribuito. In questo caso, è possibile utilizzare lo strumento di gestione dei responsabile per associare tali origini dati a un responsabile specifico. Dopo aver aggiunto i responsabile a un caso e aver associato altre origini dati, è possibile conservare rapidamente i dati ed eseguire ricerche nei dati dei depositario.

È possibile aggiungere e gestire i responsabile nei casi di Advanced eDiscovery in quattro passaggi:

1. Identificare i responsabile.

2. Scegliere le posizioni dei dati dei depositario.

3. Configurare le impostazioni di blocco.

4. Esaminare i responsabile e completare il processo.

   [![Scheda Origini nel caso di Advanced eDiscovery ](../media/AeD-Sources-Tab.png)](../media/AeD-Sources-Tab.png#lightbox)

## <a name="make-sure-you-have-the-necessary-permissions"></a>Assicurarsi di disporre delle autorizzazioni necessarie

Per aggiungere i manager a un caso, è necessario essere membri del gruppo di ruoli Gestore di eDiscovery. In questo modo è possibile ottenere le autorizzazioni necessarie per aggiungere i responsabile a un caso e impostare un blocco sulle origini dati dei depositario. Per altre informazioni, vedere [Assegnare autorizzazioni di eDiscovery](get-started-with-advanced-ediscovery.md#step-2-assign-ediscovery-permissions).

## <a name="step-1-identify-custodians"></a>Passaggio 1: identificare i responsabile

1. Accedere con un account utente a cui sono state assegnate [https://compliance.microsoft.com](https://compliance.microsoft.com) le autorizzazioni di eDiscovery appropriate.

2. Nel riquadro di spostamento sinistro del Centro conformità Microsoft 365 fare clic su Mostra tutto e quindi su **eDiscovery > Avanzate.**

3. Nella pagina **Advanced eDiscovery** fare clic sulla scheda **Casi** e quindi selezionare il caso a cui si desidera aggiungere i responsabile.

4. Fare clic **sulla scheda Origini** dati e quindi su Aggiungi origine **dati** Aggiungi  >  **nuovi responsabile.**

5. Aggiungere uno o più utenti dell'organizzazione come responsabile del caso digitando la prima parte del nome o dell'alias di una persona. Dopo aver trovato la persona corretta, selezionarne il nome per aggiungerla all'elenco.

## <a name="step-2-choose-custodian-data-locations"></a>Passaggio 2: Scegliere le posizioni dei dati dei responsabile

Dopo aver selezionato i responsabile, il sistema tenta automaticamente di identificare e verificare questi utenti e le relative origini dati. Dopo aver aggiunto i responsabile all'elenco, lo strumento include automaticamente la cassetta postale principale e l'account OneDrive per ogni responsabile. È possibile scegliere di non includere queste origini dati quando si aggiungono i responsabile al caso.

Oltre alla cassetta postale del responsabile e all'account di OneDrive, è anche possibile associare altre posizioni di dati a un responsabile, ad esempio un sito di SharePoint o un team Microsoft di cui è membro il responsabile. Ciò consente di conservare, raccogliere, analizzare ed esaminare il contenuto in altre origini dati associate ai responsabile del caso.

Per deselezionare la cassetta postale principale e l'account di OneDrive per un responsabile:

1. Espandere il responsabile per visualizzare le posizioni dei dati principali associate automaticamente a ogni responsabile.

2. Selezionare **Cancella** accanto a Cassetta **postale** o **OneDrive** per rimuovere la cassetta postale del responsabile o l'account di OneDrive dall'associazione come posizione dati per questo responsabile.

   ![Configurare le posizioni da associare a un responsabile](../media/ConfigureCustodianLocations.png)

Per associare altre cassette postali, siti, gruppi di Teams o Yammer a un responsabile specifico:

1. Espandere un responsabile per visualizzare i servizi seguenti per associare le posizioni dei dati al responsabile. Fare **clic su** Modifica accanto a un servizio per aggiungere un percorso dati.

   - **Exchange**: consente di associare altre cassette postali al responsabile. Digitare nella casella di ricerca il nome o l'alias (almeno tre caratteri) delle cassette postali degli utenti o dei gruppi di distribuzione. Selezionare le cassette postali da assegnare al responsabile, quindi fare clic su **Aggiungi.**

   - **SharePoint:** utilizzare per associare i siti di SharePoint al responsabile. Selezionare un sito nell'elenco o cercare un sito digitando un URL nella casella di ricerca. Selezionare i siti da assegnare al responsabile e quindi fare clic su **Aggiungi.**

   - **Teams:** usare questa opzione per assegnare a Microsoft Teams il responsabile di cui è attualmente membro. Selezionare i team da assegnare al responsabile e quindi fare clic su **Aggiungi.** Dopo aver aggiunto un team, il sistema identifica e individua automaticamente il sito di SharePoint e la cassetta postale del gruppo associata a tale team e li assegna al responsabile.

   - **Yammer:** consente di assegnare i gruppi di Yammer di cui il responsabile è attualmente membro. Selezionare i gruppi da assegnare al responsabile e quindi fare clic su **Aggiungi.** Dopo aver aggiunto un team, il sistema identifica e individua automaticamente il sito di SharePoint e la cassetta postale del gruppo associata a tale gruppo e li assegna al responsabile.

   > [!NOTE]
   > È possibile utilizzare le selezione percorso di **Exchange** e **SharePoint** per associare altri team o gruppi di Yammer (di cui un responsabile non è membro) a un responsabile. A tale scopo, è necessario aggiungere sia la cassetta postale che il sito associati a ogni team o gruppo di Yammer.

2. È possibile visualizzare il numero totale di cassette postali, siti, team e gruppi di Yammer assegnati a ogni responsabile espandendo ogni responsabile nella tabella. Dopo aver finalizzato le posizioni dei dati assegnate per ogni responsabile, queste associazioni verranno mantenute e utilizzate durante le fasi di raccolta, elaborazione e revisione nel flusso di lavoro advanced eDiscovery.

3. After adding custodians and configuring their data locations, click **Next** to go to the **Hold settings** page.  

## <a name="step-3-configure-hold-settings"></a>Passaggio 3: Configurare le impostazioni di blocco

 Dopo aver finalizzato i responsabile e le relative posizioni dei dati, è possibile mettere in attesa alcuni o tutti i responsabile. Quando si mette in attesa un responsabile, tutto il contenuto in tutti i percorsi di contenuto associati al responsabile viene conservato fino a quando non si rimuove l'esenzione o si rilascia il responsabile dall'esenzione. In alcuni casi, è possibile aggiungere i responsabile a un caso senza metterli in attesa.

Per mettere in attesa i responsabile e le origini dati:

1. Nella pagina **impostazioni di** blocco, è possibile applicare un'esenzione ai singoli responsabile selezionando la casella di controllo nella **colonna Esenzione.**

   In alternativa, puoi mettere in attesa tutti  i responsabile selezionando la casella di controllo Esenzione nella parte superiore della colonna.

2. Verificare le selezioni del blocco del responsabile e quindi fare clic su **Avanti.**

   > [!NOTE]
   > Se non si posiziona un blocco su un responsabile, il responsabile e le origini dati associate verranno aggiunti al caso, ma il contenuto in tali origini dati non verrà conservato dal blocco associato al caso.

## <a name="step-4-review-the-custodians-and-complete-the-process"></a>Passaggio 4: esaminare i responsabile e completare il processo

Prima di aggiungere effettivamente i responsabile al caso, è possibile esaminare l'elenco dei responsabile, le posizioni dei dati loro assegnate e le impostazioni di blocco.

1. Verificare ed esaminare tutte le origini dati e l'impostazione di blocco associata a ogni responsabile della tabella. Se necessario, tornare alla pagina  Delle impostazioni di identificazione **del responsabile** o del blocco per apportare eventuali modifiche.

2. Fare **clic su** Invia per aggiungere i responsabile e le relative posizioni dei dati al caso e applicare tutte le impostazioni di blocco dei custodia.

   I nuovi responsabile vengono aggiunti al caso e visualizzati nella **scheda Origini** dati.

   [![Responsabile elencati nella scheda Origini dati ](../media/DataSourcesTab.png)](../media/DataSourcesTab.png#lightbox)
