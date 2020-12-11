---
title: Configurare un connettore per archiviare i dati delle riunioni dello zoom in Microsoft 365
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
description: Gli amministratori possono configurare un connettore per l'importazione e l'archiviazione dei dati dalle riunioni dello zoom di Globanet in Microsoft 365. In questo modo è possibile archiviare i dati provenienti da origini dati di terze parti in Microsoft 365 per poter utilizzare le funzionalità di conformità, come la conservazione legale, la ricerca di contenuto e i criteri di ritenzione per gestire i dati di terze parti dell'organizzazione.
ms.openlocfilehash: c61c9a40d85b3bea266df9b1f2dba32301e54e08
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620202"
---
# <a name="set-up-a-connector-to-archive-zoom-meetings-data"></a>Configurare un connettore per archiviare i dati delle riunioni dello zoom

Utilizzare un connettore di Globanet nel centro conformità di Microsoft 365 per importare e archiviare i dati dalle riunioni di zoom alle cassette postali degli utenti nell'organizzazione Microsoft 365. Globanet fornisce un connettore per [riunioni zoom](https://globanet.com/zoom/) configurato per acquisire elementi dall'origine dati di terze parti (su base regolare) e importare tali elementi in Microsoft 365. Il connettore converte il contenuto delle riunioni (tra cui chat, file registrati e metadati) dall'account di riunioni zoom a un formato di messaggio di posta elettronica e quindi importa tali elementi nelle cassette postali degli utenti in Microsoft 365.

Dopo che i dati delle riunioni dello zoom sono archiviati nelle cassette postali degli utenti, è possibile applicare le funzionalità di conformità di Microsoft 365 come conservazione per controversia legale, eDiscovery, criteri di conservazione e etichette di mantenimento e conformità della comunicazione. L'utilizzo di un connettore zoom meetings per l'importazione e l'archiviazione dei dati in Microsoft 365 può aiutare l'organizzazione a rimanere conforme ai criteri governativi e normativi.

## <a name="overview-of-archiving-zoom-meetings-data"></a>Panoramica dei dati relativi alle riunioni dello zoom di archiviazione

Nella panoramica seguente viene illustrato il processo di utilizzo di un connettore per archiviare i dati delle riunioni dello zoom in Microsoft 365.

![Flusso di lavoro di archiviazione delle riunioni di zoom](../media/ZoomMeetingsConnectorWorkflow.png)

1. L'organizzazione funziona con le riunioni dello zoom per impostare e configurare un sito di riunioni zoom.

2. Una volta ogni 24 ore, gli elementi della riunione dalle riunioni dello zoom vengono copiati nel sito Merge1 di Globanet. Il connettore converte anche il contenuto delle riunioni in un formato di messaggio di posta elettronica.

3. Il connettore di riunioni zoom creato nel centro conformità di Microsoft 365, si connette a Globanet Merge1 ogni giorno e trasferisce i messaggi di riunione in una posizione di archiviazione sicura di Azure nel cloud Microsoft.

4. Il connettore importa gli elementi riunione convertiti nelle cassette postali di utenti specifici utilizzando il valore della proprietà di *posta elettronica* e il mapping automatico degli utenti, come descritto nel passaggio 3. Una nuova sottocartella nella cartella posta in arrivo denominata **riunioni zoom** viene creata nelle cassette postali degli utenti e gli elementi della riunione vengono importati in tale cartella. Il connettore esegue questa operazione utilizzando il valore della proprietà di *posta elettronica* . Ogni elemento della riunione contiene questa proprietà, che viene popolata con l'indirizzo di posta elettronica di tutti i partecipanti alla riunione.

## <a name="before-you-begin"></a>Informazioni preliminari

- Creare un account Merge1 di Globanet per i connettori Microsoft. Per creare questo account, contattare il [supporto clienti di Globanet](https://globanet.com/ms-connectors-contact). Si eseguirà l'accesso a questo account quando si crea il connettore nel passaggio 1.

- Ottenere il nome utente e la password per l'account aziendale dello zoom o dello zoom dell'organizzazione. È necessario accedere a questo account nel passaggio 2 quando si configura il connettore di riunioni zoom.

- Creare le applicazioni seguenti nel [Marketplace zoom](https://marketplace.zoom.us):

  - Applicazione OAuth

  - Applicazione JWT

  Dopo aver creato queste applicazioni, la piattaforma zoom genera un set di credenziali univoche utilizzate per generare i token. Questi token vengono utilizzati per autenticare il connettore quando si connette all'account di zoom e gli elementi vengono copiati nel sito di Merge1. Questi token verranno utilizzati quando si configura il connettore dello zoom nel passaggio 2.

  Per istruzioni dettagliate su come creare le applicazioni OAuth e JWT, vedere [Merge1 Third-Party Connectors user guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Zoom%20Meetings%20User%20Guide%20.pdf).

- L'utente che crea il connettore di riunioni zoom nel passaggio 1 (e lo completa nel passaggio 3) deve essere assegnato al ruolo di esportazione delle cassette postali in Exchange Online. Questo ruolo è necessario per aggiungere connettori nella pagina **dei connettori dati** nel centro conformità di Microsoft 365. Per impostazione predefinita, questo ruolo non è assegnato a un gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo import export delle cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online. In alternativa, è possibile creare un gruppo di ruoli, assegnare il ruolo di esportazione delle cassette postali e quindi aggiungere gli utenti corretti come membri. Per ulteriori informazioni, vedere la sezione creare gruppi di [ruoli](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) o [modificare gruppi di ruoli](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) nell'articolo "gestire i gruppi di ruoli in Exchange Online".

## <a name="step-1-set-up-the-zoom-meetings-connector"></a>Passaggio 1: configurare il connettore per riunioni zoom

Il primo passaggio consiste nell'accedere ai **connettori di dati** nel centro conformità di Microsoft 365 e creare un connettore di riunioni zoom.

1. Passare a [https://compliance.microsoft.com](https://compliance.microsoft.com/) e quindi fare clic su riunioni zoom **dei connettori dati**  >  .

2. Nella pagina Descrizione del prodotto **riunioni di zoom** fare clic su **Aggiungi connettore**.

3. Nella pagina **condizioni del servizio** fare clic su **Accetto**.

4. Immettere un nome univoco che identifichi il connettore e quindi fare clic su **Avanti**.

5. Accedere al proprio account di Merge1 per configurare il connettore.

## <a name="step-2-configure-the-zoom-meetings-connector"></a>Passaggio 2: configurare il connettore di riunioni zoom

Il secondo passaggio consiste nel configurare il connettore di riunioni zoom nel sito di Merge1. Per ulteriori informazioni su come configurare il connettore zoom meetings nel sito Globanet Merge1, vedere [Merge1 di terze parti dei connettori utente](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Zoom%20Meetings%20User%20Guide%20.pdf).

Dopo aver fatto clic su **salva & fine**, viene visualizzata la pagina di **mapping degli utenti** nella procedura guidata del connettore nel centro conformità di Microsoft 365.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Passaggio 3: mappare gli utenti e completare la configurazione del connettore

1. Nella pagina mapping **utenti esterni a Microsoft 365** , abilitare il mapping automatico degli utenti.

   Gli elementi di riunioni zoom includono una proprietà denominata *posta elettronica* che contiene gli indirizzi di posta elettronica per gli utenti dell'organizzazione. Se il connettore è in grado di associare l'indirizzo a un utente di Microsoft 365, gli elementi vengono importati nella cassetta postale dell'utente.

2. Fare clic su **Avanti**, rivedere le impostazioni e passare alla pagina **connettori dati** per visualizzare lo stato di avanzamento del processo di importazione per il nuovo connettore.

## <a name="step-4-monitor-the-zoom-meetings-connector"></a>Passaggio 4: monitorare il connettore di riunioni zoom

Dopo aver creato il connettore di riunioni zoom, è possibile visualizzare lo stato del connettore nel centro conformità di Microsoft 365.

1. Andare a [https://compliance.microsoft.com](https://compliance.microsoft.com) e fare clic su **connettori dati** nel NAV sinistro.

2. Fare clic sulla scheda **connettori** , quindi selezionare il connettore **Zoom Meetings** per visualizzare la pagina a comparsa. Questa pagina contiene le proprietà e le informazioni sul connettore.

3. In **stato connettore con origine** fare clic sul collegamento **Scarica log** per aprire o salvare il registro di stato del connettore. Questo log contiene informazioni sui dati che sono stati importati nel cloud Microsoft.

## <a name="known-issues"></a>Problemi noti

- Al momento, non è supportato l'importazione di allegati o elementi di dimensioni superiori a 10 MB. Il supporto per gli elementi di grandi dimensioni sarà disponibile in un secondo momento.

- Per il funzionamento del connettore di riunioni zoom, è necessario abilitare le registrazioni quando si configurano le riunioni dello zoom.
