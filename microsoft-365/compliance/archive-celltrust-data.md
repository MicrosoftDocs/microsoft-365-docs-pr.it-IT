---
title: Configurare un connettore per l'archiviazione dei dati di CellTrust in Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: Gli amministratori possono configurare un connettore per l'importazione e l'archiviazione dei dati di CellTrust da Globanet a Microsoft 365. Questo connettore consente di archiviare i dati provenienti da origini dati di terze parti in Microsoft 365. Dopo l'archiviazione dei dati, è possibile utilizzare le funzionalità di conformità, ad esempio la conservazione legale, la ricerca del contenuto e i criteri di ritenzione per gestire i dati di terze parti.
ms.openlocfilehash: 5870e823562f86b8b984e81fd03eeebd1b01f0ff
ms.sourcegitcommit: a3215cc22faa47e935d22300c481e47ab2680b44
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/21/2020
ms.locfileid: "49722913"
---
# <a name="set-up-a-connector-to-archive-celltrust-data"></a>Configurare un connettore per l'archiviazione dei dati di CellTrust

Utilizzare un connettore di Globanet nel centro conformità di Microsoft 365 per importare e archiviare i dati dalla piattaforma CellTrust alle cassette postali degli utenti nell'organizzazione Microsoft 365. Globanet fornisce un connettore [CellTrust](https://globanet.com/celltrust/) che consente di acquisire elementi dall'origine dati di terze parti e di importare tali elementi in Microsoft 365. Il connettore converte il contenuto dei messaggi SMS dagli account di CellTrust a un formato di messaggio di posta elettronica e quindi importa tali elementi nella cassetta postale dell'utente in Microsoft 365.

Dopo che i dati di CellTrust sono archiviati nelle cassette postali degli utenti, è possibile applicare le funzionalità di conformità di Microsoft 365 come la conservazione per controversia legale, eDiscovery, i criteri di conservazione e le etichette e la conformità alla comunicazione. L'utilizzo di un connettore CellTrust per l'importazione e l'archiviazione dei dati in Microsoft 365 può aiutare l'organizzazione a rimanere conforme ai criteri governativi e normativi.

## <a name="overview-of-archiving-celltrust-data"></a>Panoramica dell'archiviazione dei dati di CellTrust

Nella panoramica seguente viene illustrato il processo di utilizzo di un connettore per l'archiviazione dei dati di CellTrust in Microsoft 365.

![Flusso di lavoro di archiviazione per i dati di CellTrust](../media/CellTrustConnectorWorkflow.png)

1. L'organizzazione collabora con CellTrust per impostare e configurare un sito di CellTrust.

2. Una volta ogni 24 ore, gli elementi di CellTrust vengono copiati nel sito di Merge1 di Globanet. Il connettore converte anche il contenuto di un messaggio in un formato di messaggio di posta elettronica.

3. Il connettore CellTrust creato nel centro conformità di Microsoft 365 si connette al sito di Merge1 di Globanet ogni giorno e trasferisce i messaggi a una posizione di archiviazione sicura di Azure nel cloud Microsoft.

4. Il mapping utente automatico come connettore importa gli elementi nelle cassette postali di utenti specifici utilizzando il valore della proprietà di *posta elettronica* descritta nel [passaggio 3](#step-3-map-users-and-complete-the-connector-setup). Una sottocartella della cartella posta in arrivo denominata **CellTrust** viene creata nelle cassette postali degli utenti e gli elementi del messaggio vengono importati in tale cartella. Il connettore determina la cassetta postale a cui importare gli elementi utilizzando il valore della proprietà di *posta elettronica* . Ogni elemento di CellTrust contiene questa proprietà, che viene popolata con l'indirizzo di posta elettronica di ogni partecipante.

## <a name="before-you-begin"></a>Prima di iniziare

- Creare un account Merge1 per i connettori Microsoft. Per creare un account, contattare il [supporto clienti di Globanet](https://globanet.com/contact-us/). È necessario accedere a questo account quando si crea il connettore nel passaggio 1.

- L'utente che crea il connettore CellTrust nel passaggio 1 (e lo completa nel passaggio 3) deve essere assegnato al ruolo di importazione/esportazione delle cassette postali in Exchange Online. Questo ruolo è necessario per aggiungere connettori nella pagina **dei connettori dati** nel centro conformità di Microsoft 365. Per impostazione predefinita, questo ruolo non è assegnato ad alcun gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo import export delle cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online. In alternativa, è possibile creare un gruppo di ruoli, assegnare il ruolo di esportazione delle cassette postali e quindi aggiungere gli utenti corretti come membri. Per ulteriori informazioni, vedere la sezione creare gruppi di [ruoli](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) o [modificare gruppi di ruoli](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) nell'articolo "gestire i gruppi di ruoli in Exchange Online".

## <a name="step-1-set-up-the-celltrust-connector"></a>Passaggio 1: configurare il connettore CellTrust

Il primo passaggio consiste nell'accedere ai **connettori di dati** nel centro conformità di Microsoft 365 e creare un connettore per i dati di CellTrust.

1. Andare a [https://compliance.microsoft.com](https://compliance.microsoft.com/) e quindi fare clic su **connettori dati** \> **CellTrust**.

2. Nella pagina Descrizione prodotto **CellTrust** fare clic su **Aggiungi connettore**.

3. Nella pagina **condizioni del servizio** fare clic su **Accetto**.

4. Immettere un nome univoco che identifichi il connettore e quindi fare clic su **Avanti**.

5. Accedere al proprio account di Merge1 per configurare il connettore.

## <a name="step-2-configure-the-celltrust-connector-on-the-globanet-merge1-site"></a>Passaggio 2: configurare il connettore di CellTrust nel sito di Merge1 di Globanet

Il secondo passaggio consiste nel configurare il connettore di CellTrust nel sito di Merge1 di Globanet. Per informazioni su come configurare il connettore di CellTrust, vedere [Merge1 di terze parti dei connettori utente](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20CellTrust%20User%20Guide%20.pdf).

Dopo aver fatto clic su **salva & fine**, viene visualizzata la pagina di **mapping degli utenti** nella procedura guidata del connettore nel centro conformità di Microsoft 365.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Passaggio 3: mappare gli utenti e completare la configurazione del connettore

Per eseguire il mapping degli utenti e completare il connettore configurato nel centro conformità Microsoft 365, attenersi alla seguente procedura:

1. Nella pagina mapping **utenti di CellTrust a Microsoft 365** , abilitare il mapping automatico degli utenti. Gli elementi di CellTrust includono una proprietà denominata *posta elettronica*, che contiene gli indirizzi di posta elettronica per gli utenti dell'organizzazione. Se il connettore può associare questo indirizzo a un utente di Microsoft 365, gli elementi vengono importati nella cassetta postale dell'utente.

2. Fare clic su **Avanti**, rivedere le impostazioni e passare alla pagina **connettori dati** per visualizzare lo stato di avanzamento del processo di importazione per il nuovo connettore.

## <a name="step-4-monitor-the-celltrust-connector"></a>Passaggio 4: monitorare il connettore di CellTrust

Dopo aver creato il connettore CellTrust, è possibile visualizzare lo stato del connettore nel centro conformità di Microsoft 365.

1. Andare a [https://compliance.microsoft.com](https://compliance.microsoft.com/) e fare clic su **connettori dati** nel NAV sinistro.

2. Fare clic sulla scheda **connettori** e quindi selezionare il connettore **CellTrust** per visualizzare la pagina del riquadro a comparsa, che contiene le proprietà e le informazioni sul connettore.

3. In **stato connettore con origine** fare clic sul collegamento **Scarica log** per aprire o salvare il registro di stato del connettore. Questo log contiene dati che sono stati importati nel cloud Microsoft.

## <a name="known-issues"></a>Problemi noti

- Al momento, non è supportato l'importazione di allegati o elementi di dimensioni superiori a 10 MB. Il supporto per gli elementi di grandi dimensioni sarà disponibile in un secondo momento.
