---
title: Configurare un connettore per archiviare i dati di Jive in Microsoft 365
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
description: Gli amministratori possono configurare un connettore per l'importazione e l'archiviazione dei dati di Jive da Globanet in Microsoft 365. Questo connettore consente di archiviare i dati provenienti da origini dati di terze parti in Microsoft 365, in modo da poter utilizzare le funzionalità di conformità, come la conservazione legale, la ricerca di contenuto e i criteri di ritenzione per gestire i dati di terze parti dell'organizzazione.
ms.openlocfilehash: e89404362505dbe276e351e95ebd30a0c0bdf88c
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620393"
---
# <a name="set-up-a-connector-to-archive-jive-data"></a>Configurare un connettore per archiviare i dati di Jive

Utilizzare un connettore di Globanet nel centro conformità di Microsoft 365 per importare e archiviare i dati dalla piattaforma di collaborazione alle cassette postali degli utenti nell'organizzazione Microsoft 365. Globanet fornisce un connettore [Jive](https://globanet.com/jive/) configurato per acquisire elementi dall'origine dati di terze parti (su base regolare) e quindi importare tali elementi in Microsoft 365. Il connettore converte il contenuto, ad esempio i messaggi di posta elettronica, le chat e gli allegati dall'account Jive di un utente a un formato di messaggio di posta elettronica e quindi importa tali elementi nella cassetta postale dell'utente in Microsoft 365.

Dopo che i dati di Jive sono archiviati nelle cassette postali degli utenti, è possibile applicare le funzionalità di conformità di Microsoft 365 come il blocco per controversia legale, eDiscovery, criteri di conservazione e etichette di conservazione e conformità della comunicazione. L'utilizzo di un connettore Jive per l'importazione e l'archiviazione dei dati in Microsoft 365 può aiutare l'organizzazione a rimanere conforme ai criteri governativi e normativi.

## <a name="overview-of-archiving-jive-data"></a>Panoramica dell'archiviazione dei dati di Jive

Nella panoramica seguente viene illustrato il processo di utilizzo di un connettore per archiviare i dati di Jive in Microsoft 365.

![Flusso di lavoro di archiviazione per i dati di Jive](../media/JiveConnectorWorkflow.png)

1. L'organizzazione collabora con Jive per impostare e configurare un sito di Jive.

2. Una volta ogni 24 ore, gli elementi di Jive vengono copiati nel sito Merge1 di Globanet. Il connettore converte anche il contenuto degli elementi di Jive in un formato di messaggio di posta elettronica.

3. Il connettore di Jive creato nel centro conformità di Microsoft 365 si connette al sito di Globanet Merge1 ogni giorno e trasferisce il contenuto in una posizione di archiviazione sicura di Azure nel cloud Microsoft.

4. Il connettore importa gli elementi convertiti nelle cassette postali di utenti specifici utilizzando il valore della proprietà di *posta elettronica* del mapping automatico degli utenti, come descritto nel [passaggio 3](#step-3-map-users-and-complete-the-connector-setup). Viene creata una nuova sottocartella nella cartella posta in arrivo denominata **Jive** nelle cassette postali degli utenti e gli elementi vengono importati in tale cartella. Il connettore esegue questa operazione utilizzando il valore della proprietà di *posta elettronica* . Ogni elemento Jive contiene questa proprietà, che viene popolata con l'indirizzo di posta elettronica di tutti i partecipanti all'elemento.

## <a name="before-you-begin"></a>Informazioni preliminari

- Creare un account Merge1 di Globanet per i connettori Microsoft. Per creare questo account, contattare il [supporto clienti di globanet](https://globanet.com/ms-connectors-contact/). Si eseguirà l'accesso a questo account quando si crea il connettore nel passaggio 1.

- L'utente che crea il connettore Jive nel passaggio 1 (e lo completa nel passaggio 3) deve essere assegnato al ruolo di importazione/esportazione delle cassette postali in Exchange Online. Questo ruolo è necessario per aggiungere connettori nella pagina **dei connettori dati** nel centro conformità di Microsoft 365. Per impostazione predefinita, questo ruolo non è assegnato a un gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo import export delle cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online. In alternativa, è possibile creare un gruppo di ruoli, assegnare il ruolo di esportazione delle cassette postali e quindi aggiungere gli utenti corretti come membri. Per ulteriori informazioni, vedere la sezione creare gruppi di [ruoli](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) o [modificare gruppi di ruoli](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) nell'articolo "gestire i gruppi di ruoli in Exchange Online".

## <a name="step-1-set-up-the-jive-connector"></a>Passaggio 1: configurare il connettore Jive

Il primo passaggio consiste nell'accedere alla pagina **dei connettori dati** nel centro conformità di Microsoft 365 e creare un connettore per i dati di Jive.

1. Andare a [https://compliance.microsoft.com](https://compliance.microsoft.com/) e quindi fare clic su **connettori di dati**  >  **Jive**.

2. Nella pagina Descrizione prodotto **Jive** fare clic su **Aggiungi connettore**.

3. Nella pagina **condizioni del servizio** fare clic su **Accetto**.

4. Immettere un nome univoco che identifichi il connettore e quindi fare clic su **Avanti**.

5. Accedere al proprio account di Merge1 per configurare il connettore.

## <a name="step-2-configure-the-jive-connector"></a>Passaggio 2: configurare il connettore Jive

Il secondo passaggio consiste nel configurare il connettore Jive nel sito di Merge1. Per informazioni su come configurare il connettore di Jive, vedere [Merge1 di terze parti dei connettori utente](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Jive%20User%20Guide.pdf).

Dopo aver fatto clic su **salva & fine**, viene visualizzata la pagina di **mapping degli utenti** nella procedura guidata del connettore nel centro conformità di Microsoft 365.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Passaggio 3: mappare gli utenti e completare la configurazione del connettore

Per eseguire il mapping degli utenti e completare la configurazione del connettore nel centro conformità di Microsoft 365, attenersi alla procedura seguente:

1. Nella pagina **Mappa utenti di Jive a Microsoft 365** , abilitare il mapping automatico degli utenti. Gli elementi di Jive includono una proprietà denominata *posta elettronica*, che contiene gli indirizzi di posta elettronica per gli utenti dell'organizzazione. Se il connettore può associare questo indirizzo a un utente di Microsoft 365, gli elementi vengono importati nella cassetta postale dell'utente.

2. Fare clic su **Avanti**, rivedere le impostazioni e passare alla pagina **connettori dati** per visualizzare lo stato di avanzamento del processo di importazione per il nuovo connettore.

## <a name="step-4-monitor-the-jive-connector"></a>Passaggio 4: monitorare il connettore Jive

Dopo aver creato il connettore Jive, è possibile visualizzare lo stato del connettore nel centro conformità di Microsoft 365.

1. Andare a [https://compliance.microsoft.com](https://compliance.microsoft.com) e fare clic su **connettori dati** nel NAV sinistro.

2. Fare clic sulla scheda **connettori** e quindi selezionare il connettore **Jive** per visualizzare la pagina del riquadro a comparsa. Questa pagina contiene le proprietà e le informazioni sul connettore.

3. In **stato connettore con origine** fare clic sul collegamento **Scarica log** per aprire o salvare il registro di stato del connettore. Questo log contiene informazioni sui dati che sono stati importati nel cloud Microsoft.

## <a name="known-issues"></a>Problemi noti

- Al momento, non è supportato l'importazione di allegati o elementi di dimensioni superiori a 10 MB. Il supporto per gli elementi di grandi dimensioni sarà disponibile in un secondo momento.
