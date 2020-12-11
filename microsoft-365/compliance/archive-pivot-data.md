---
title: Configurare un connettore per l'archiviazione dei dati pivot in Microsoft 365
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
description: Gli amministratori possono configurare un connettore per l'importazione e l'archiviazione dei dati di pivot da Globanet in Microsoft 365. Questo connettore consente di archiviare i dati provenienti da origini dati di terze parti in Microsoft 365, in modo da poter utilizzare le funzionalità di conformità, come la conservazione legale, la ricerca di contenuto e i criteri di ritenzione per gestire i dati di terze parti dell'organizzazione.
ms.openlocfilehash: 23badcb2a8d2873f03b86499ccfd4c9a96b81090
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620373"
---
# <a name="set-up-a-connector-to-archive-pivot-data"></a>Configurare un connettore in modo che i dati di pivot vengano archiviati

Utilizzare un connettore di Globanet nel centro conformità di Microsoft 365 per importare e archiviare i dati dalla piattaforma pivot alle cassette postali degli utenti nell'organizzazione Microsoft 365. Globanet fornisce un connettore [pivot](https://globanet.com/pivot/) configurato per acquisire elementi dall'origine dati di terze parti (su base regolare) e quindi importare tali elementi in Microsoft 365. Pivot è una piattaforma di messaggistica istantanea che consente la collaborazione con i partecipanti al mercato finanziario. Il connettore converte gli elementi, ad esempio i messaggi di chat, dagli account pivot di un utente a un formato di messaggio di posta elettronica e quindi importa tali elementi nelle cassette postali degli utenti in Microsoft 365.

Dopo che i dati di pivot sono archiviati nelle cassette postali degli utenti, è possibile applicare le funzionalità di conformità di Microsoft 365 come il blocco per controversia legale, eDiscovery, criteri di conservazione e etichette di conservazione e conformità alla comunicazione. L'utilizzo di un connettore pivot per l'importazione e l'archiviazione dei dati in Microsoft 365 può aiutare l'organizzazione a rimanere conforme ai criteri governativi e normativi.

## <a name="overview-of-archiving-pivot-data"></a>Panoramica dei dati di pivot di archiviazione

Nella panoramica seguente viene illustrato il processo di utilizzo di un connettore per l'archiviazione dei dati di pivot in Microsoft 365.

![Flusso di lavoro di archiviazione per i dati pivot](../media/PivotConnectorWorkflow.png)

1. L'organizzazione utilizza pivot per impostare e configurare un sito di origine pivot.

2. Una volta ogni 24 ore, gli elementi pivot vengono copiati nel sito Merge1 di Globanet. Il connettore converte anche gli elementi pivot in un formato di messaggio di posta elettronica.

3. Il connettore pivot creato nel centro conformità Microsoft 365, si connette al sito di Globanet Merge1 ogni giorno e trasferisce gli elementi pivot in una posizione di archiviazione sicura di Azure nel cloud Microsoft.

4. Il connettore importa gli elementi pivot nelle cassette postali di utenti specifici utilizzando il valore della proprietà di *posta elettronica* del mapping automatico degli utenti, come descritto nel [passaggio 3](#step-3-map-users-and-complete-the-connector-setup). Viene creata una sottocartella nella cartella posta in arrivo denominata **pivot** nelle cassette postali degli utenti e gli elementi vengono importati in tale cartella. Il connettore esegue questa operazione utilizzando il valore della proprietà di *posta elettronica* . Ogni elemento pivot contiene questa proprietà, che viene popolata con l'indirizzo di posta elettronica di tutti i partecipanti all'elemento.

## <a name="before-you-begin"></a>Informazioni preliminari

- Creare un account Merge1 di Globanet per i connettori Microsoft. Per creare questo account, contattare il [supporto clienti di Globanet](https://globanet.com/ms-connectors-contact/). Si eseguirà l'accesso a questo account quando si crea il connettore nel passaggio 1.

- L'utente che crea il connettore pivot nel passaggio 1 (e lo completa nel passaggio 3) deve essere assegnato al ruolo di importazione/esportazione delle cassette postali in Exchange Online. Questo ruolo è necessario per aggiungere connettori nella pagina dei connettori dati nel centro conformità di Microsoft 365. Per impostazione predefinita, questo ruolo non è assegnato a un gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo import export delle cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online. In alternativa, è possibile creare un gruppo di ruoli, assegnare il ruolo di esportazione delle cassette postali e quindi aggiungere gli utenti corretti come membri. Per ulteriori informazioni, vedere la sezione creare gruppi di [ruoli](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) o [modificare gruppi di ruoli](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) nell'articolo "gestire i gruppi di ruoli in Exchange Online".

## <a name="step-1-set-up-the-pivot-connector"></a>Passaggio 1: configurare il connettore pivot

Il primo passaggio consiste nell'accedere alla pagina **dei connettori dati** nel centro conformità Microsoft e creare un connettore per i dati di pivot.

1. Andare a [https://compliance.microsoft.com](https://compliance.microsoft.com/) e quindi fare clic su pivot **Data Connectors**  >  .

2. Nella pagina Descrizione prodotto **pivot** fare clic su **Aggiungi connettore**.

3. Nella pagina **condizioni del servizio** fare clic su **Accetto**.

4. Immettere un nome univoco che identifichi il connettore e quindi fare clic su **Avanti**.

5. Accedere al proprio account di Merge1 per configurare il connettore.

## <a name="step-2-configure-the-pivot-connector-on-the-globanet-merge1-site"></a>Passaggio 2: configurare il connettore pivot nel sito Merge1 di Globanet

Il secondo passaggio consiste nel configurare il connettore pivot nel sito di Merge1. Per informazioni su come configurare il connettore pivot nel sito di Globanet Merge1, vedere [Merge1 di terze parti dei connettori utente](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Pivot%20User%20Guide%20.pdf).

Dopo aver fatto clic su **salva & fine**, viene visualizzata la pagina di **mapping degli utenti** nella procedura guidata del connettore nel centro conformità di Microsoft 365.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Passaggio 3: mappare gli utenti e completare la configurazione del connettore

Per eseguire il mapping degli utenti e completare la configurazione del connettore nel centro conformità di Microsoft 356, eseguire la procedura seguente:

1. Nella pagina mapping pivot Users **to Microsoft 365** Users, abilitare la mappatura automatica degli utenti. Gli elementi pivot includono una proprietà denominata *posta elettronica*, che contiene gli indirizzi di posta elettronica per gli utenti dell'organizzazione. Se il connettore può associare questo indirizzo a un utente di Microsoft 365, gli elementi vengono importati nella cassetta postale dell'utente.

2. Fare clic su **Avanti**, rivedere le impostazioni e passare alla pagina **connettori dati** per visualizzare lo stato di avanzamento del processo di importazione per il nuovo connettore.

## <a name="step-4-monitor-the-pivot-connector"></a>Passaggio 4: monitorare il connettore pivot

Dopo aver creato il connettore pivot, è possibile visualizzare lo stato del connettore nel centro conformità di Microsoft 365.

1. Andare a [https://compliance.microsoft.com](https://compliance.microsoft.com) e fare clic su **connettori dati** nel NAV sinistro.

2. Fare clic sulla scheda **connettori** e quindi selezionare il connettore **pivot** per visualizzare la pagina del riquadro a comparsa. Questa pagina contiene le proprietà e le informazioni sul connettore.

3. In **stato connettore con origine** fare clic sul collegamento **Scarica log** per aprire o salvare il registro di stato del connettore. Questo log contiene dati che sono stati importati nel cloud Microsoft.

## <a name="known-issues"></a>Problemi noti

- Al momento, non è supportato l'importazione di allegati o elementi di dimensioni superiori a 10 MB. Il supporto per gli elementi di grandi dimensioni sarà disponibile in un secondo momento.
