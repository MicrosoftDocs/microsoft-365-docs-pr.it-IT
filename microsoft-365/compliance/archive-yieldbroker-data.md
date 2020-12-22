---
title: Configurare un connettore per l'archiviazione dei dati di Yieldbroker in Microsoft 365
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
description: Gli amministratori possono configurare un connettore per l'importazione e l'archiviazione dei dati di Yieldbroker da Globanet a Microsoft 365. Questo connettore consente di archiviare i dati provenienti da origini dati di terze parti in Microsoft 365. Dopo l'archiviazione dei dati, è possibile utilizzare le funzionalità di conformità, ad esempio la conservazione legale, la ricerca del contenuto e i criteri di ritenzione per gestire i dati di terze parti.
ms.openlocfilehash: 1591198dae3a7a5082c4f8f7ba925eb9e6dd680b
ms.sourcegitcommit: a3215cc22faa47e935d22300c481e47ab2680b44
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/21/2020
ms.locfileid: "49722950"
---
# <a name="set-up-a-connector-to-archive-yieldbroker-data-preview"></a>Configurare un connettore per l'archiviazione dei dati di Yieldbroker (anteprima)

Utilizzare un connettore di Globanet nel centro conformità di Microsoft 365 per importare e archiviare i dati da Yieldbroker alle cassette postali degli utenti nell'organizzazione Microsoft 365. Globanet fornisce un connettore [Yieldbroker](https://globanet.com/yieldbroker/) configurato per acquisire elementi dall'origine dati di terze parti e importare tali elementi in Microsoft 365. Il connettore converte il contenuto da Yieldbroker in un formato di messaggio di posta elettronica e quindi importa tali elementi nella cassetta postale dell'utente in Microsoft 365.

Dopo l'archiviazione di Yieldbroker nelle cassette postali degli utenti, è possibile applicare le funzionalità di conformità di Microsoft 365, ad esempio Blocco per controversia legale, eDiscovery, criteri di conservazione e etichette di conservazione. L'utilizzo di un connettore Yieldbroker per l'importazione e l'archiviazione dei dati in Microsoft 365 può aiutare l'organizzazione a rimanere conforme ai criteri governativi e normativi.

## <a name="overview-of-archiving-yieldbroker-data"></a>Panoramica dell'archiviazione dei dati di Yieldbroker

Nella panoramica seguente viene illustrato il processo di utilizzo di un connettore per l'archiviazione dei dati di Yieldbroker in Microsoft 365.

![Flusso di lavoro di archiviazione per i dati di Yieldbroker](../media/YieldbrokerConnectorWorkflow.png)

1. L'organizzazione utilizza Yieldbroker per impostare e configurare un sito di Yieldbroker.

2. Una volta ogni 24 ore, gli elementi di Yieldbroker vengono copiati nel sito di Merge1 di Globanet. Il connettore converte anche il contenuto in un formato di messaggio di posta elettronica.

3. Il connettore Yieldbroker creato nel centro conformità di Microsoft 365, si connette al sito di Merge1 di Globanet ogni giorno e trasferisce i messaggi a una posizione di archiviazione sicura di Azure nel cloud Microsoft.

4. Il connettore importa gli elementi di Yieldbroker convertiti nelle cassette postali di utenti specifici utilizzando il valore della proprietà di *posta elettronica* del mapping automatico degli utenti, come descritto nel [passaggio 3](#step-3-map-users-and-complete-the-connector-setup). Una sottocartella della cartella posta in arrivo denominata **Yieldbroker** viene creata nelle cassette postali degli utenti e gli elementi vengono importati in tale cartella. Il connettore determina la cassetta postale a cui importare gli elementi utilizzando il valore della proprietà di *posta elettronica* . Ogni Yieldbroker contiene questa proprietà, che viene popolata con l'indirizzo di posta elettronica di ogni partecipante all'elemento.

## <a name="before-you-begin"></a>Prima di iniziare

- Creare un account Merge1 di Globanet per i connettori Microsoft. Per creare un account, contattare il [supporto clienti di Globanet](https://globanet.com/contact-us/). È necessario accedere a questo account quando si crea il connettore nel passaggio 1.

- L'utente che crea il connettore Yieldbroker nel passaggio 1 (e lo completa nel passaggio 3) deve essere assegnato al ruolo di importazione/esportazione delle cassette postali in Exchange Online. Questo ruolo è necessario per aggiungere connettori nella pagina dei connettori dati nel centro conformità di Microsoft 365. Per impostazione predefinita, questo ruolo non è assegnato a nessun gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo import export delle cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online. In alternativa, è possibile creare un gruppo di ruoli, assegnare il ruolo di esportazione delle cassette postali e quindi aggiungere gli utenti corretti come membri. Per ulteriori informazioni, vedere la sezione creare gruppi di [ruoli](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) o [modificare gruppi di ruoli](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) nell'articolo "gestire i gruppi di ruoli in Exchange Online".

## <a name="step-1-set-up-the-yieldbroker-connector"></a>Passaggio 1: configurare il connettore Yieldbroker

Il primo passaggio consiste nell'accedere alla pagina **dei connettori dati** nel centro conformità di Microsoft 365 e creare un connettore per l'Yieldbroker.

1. Andare a [https://compliance.microsoft.com](https://compliance.microsoft.com/) e quindi fare clic su **connettori dati** &gt; **Yieldbroker**.

2. Nella pagina Descrizione prodotto **Yieldbroker** fare clic su **Aggiungi nuovo connettore**.

3. Nella pagina **condizioni del servizio** fare clic su **Accetto**.

4. Immettere un nome univoco che identifichi il connettore e quindi fare clic su **Avanti**.

5. Accedere al proprio account di Merge1 per configurare il connettore.

## <a name="step-2-configure-the-yieldbroker-connector-on-the-globanet-merge1-site"></a>Passaggio 2: configurare il connettore di Yieldbroker nel sito di Merge1 di Globanet

Il secondo passaggio consiste nel configurare il connettore di Yieldbroker nel sito di Merge1. Per informazioni su come configurare Yieldbroker, vedere [Merge1 Third-Party Connectors user guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Yieldbroker%20User%20Guide%20.pdf).

Dopo aver fatto clic su **salva & fine**, viene visualizzata la pagina di **mapping degli utenti** nella procedura guidata del connettore nel centro conformità di Microsoft 365.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Passaggio 3: mappare gli utenti e completare la configurazione del connettore

Per eseguire il mapping degli utenti e completare la configurazione del connettore, eseguire la procedura seguente:

1. Nella pagina mapping **utenti di Yieldbroker a Microsoft 365** , abilitare il mapping automatico degli utenti. Gli elementi di Yieldbroker includono una proprietà denominata *posta elettronica*, che contiene gli indirizzi di posta elettronica per gli utenti dell'organizzazione. Se il connettore può associare questo indirizzo a un utente di Microsoft 365, gli elementi vengono importati nella cassetta postale dell'utente.

2. Fare clic su **Avanti**, rivedere le impostazioni e passare alla pagina **connettori dati** per visualizzare lo stato di avanzamento del processo di importazione per il nuovo connettore.

## <a name="step-4-monitor-the-yieldbroker-connector"></a>Passaggio 4: monitorare il connettore di Yieldbroker

Dopo aver creato il connettore Yieldbroker, è possibile visualizzare lo stato del connettore nel centro conformità di Microsoft 365.

1. Andare a [https://compliance.microsoft.com](https://compliance.microsoft.com/) e fare clic su **connettori dati** nel NAV sinistro.

2. Fare clic sulla scheda **connettori** e quindi selezionare il connettore **Yieldbroker** per visualizzare la pagina del riquadro a comparsa, che contiene le proprietà e le informazioni sul connettore.

3. In **stato connettore con origine** fare clic sul collegamento **Scarica log** per aprire o salvare il registro di stato del connettore. Questo log contiene dati che sono stati importati nel cloud Microsoft.

## <a name="known-issues"></a>Problemi noti

- Al momento, non è supportato l'importazione di allegati o elementi di dimensioni superiori a 10 MB. Il supporto per gli elementi di grandi dimensioni sarà disponibile in un secondo momento.
