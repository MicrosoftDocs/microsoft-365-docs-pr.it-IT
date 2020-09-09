---
title: Configurare un connettore in modo che i dati di archiviazione FX Connect vengano archiviati in Microsoft 365
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
ROBOTS: NOINDEX, NOFOLLOW
description: Gli amministratori possono configurare un connettore per l'importazione e l'archiviazione dei dati da Globanet FX Connect in Microsoft 365. Questo connettore consente di archiviare i dati provenienti da origini dati di terze parti in Microsoft 365, in modo da poter utilizzare le funzionalità di conformità, come la conservazione legale, la ricerca di contenuto e i criteri di ritenzione per gestire i dati di terze parti dell'organizzazione.
ms.openlocfilehash: d22313ab1de1700c14ee4b35f6a0e3dbcae73ae3
ms.sourcegitcommit: 57b37a3ce40f205c7320d5be1a0d906dd492b863
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2020
ms.locfileid: "47405587"
---
# <a name="set-up-a-connector-to-archive-fx-connect-data-preview"></a>Configurare un connettore in modo che i dati di archiviazione FX Connect (anteprima)

Utilizzare un connettore di Globanet nel centro conformità di Microsoft 365 per importare e archiviare i dati dalla piattaforma di collaborazione FX Connect alle cassette postali degli utenti nell'organizzazione Microsoft 365. Globanet fornisce un connettore [FX Connect](https://globanet.com/fx-connect/) configurato per acquisire gli elementi di connessione FX e importare tali elementi in Microsoft 365. Il connettore converte il contenuto da FX Connect, ad esempio mestieri, messaggi e altri dettagli dall'account di connessione FX dell'organizzazione, a un formato di messaggio di posta elettronica e quindi importa tali elementi nella cassetta postale dell'utente in Microsoft 365.

Dopo che i dati di connessione FX sono archiviati nelle cassette postali degli utenti, è possibile applicare le funzionalità di conformità di Microsoft 365 come conservazione per controversia legale, eDiscovery, criteri di conservazione e etichette per il mantenimento e conformità della comunicazione. L'utilizzo di un connettore FX Connect per l'importazione e l'archiviazione dei dati in Microsoft 365 può aiutare l'organizzazione a rimanere conforme ai criteri governativi e normativi.

## <a name="overview-of-archiving-fx-connect-data"></a>Panoramica dell'archiviazione dei dati di connessione FX

Nella panoramica seguente viene illustrato il processo di utilizzo di un connettore per archiviare le informazioni su FX Connect in Microsoft 365.

![Flusso di lavoro di archiviazione per i dati di connessione FX](../media/FXConnectConnectorWorkflow.png)

1. L'organizzazione è compatibile con FX Connect per impostare e configurare un sito FX Connect.

2. Una volta ogni 24 ore, gli elementi provenienti da account di connessione FX vengono copiati nel sito Merge1 di Globanet. Il connettore converte gli elementi FX Connect anche in un formato di messaggio di posta elettronica.

3. Il connettore FX Connect creato nel centro conformità Microsoft 365, si connette al sito di Globanet Merge1 ogni giorno e trasferisce gli elementi FX Connect in una posizione di archiviazione sicura di Azure nel cloud Microsoft.

4. Il connettore consente di importare gli elementi nelle cassette postali di utenti specifici utilizzando il valore della proprietà di *posta elettronica* del mapping automatico degli utenti, come descritto nel [passaggio 3](#step-3-map-users-and-complete-the-connector-setup). Una sottocartella della cartella posta in arrivo denominata **FX Connect** viene creata nelle cassette postali degli utenti e gli elementi vengono importati in tale cartella. Il connettore esegue questa operazione utilizzando il valore della proprietà di *posta elettronica* . Ogni elemento FX Connect contiene questa proprietà, che viene popolata con l'indirizzo di posta elettronica di tutti i partecipanti all'elemento.

## <a name="before-you-begin"></a>Informazioni preliminari

- Creare un account Merge1 di Globanet per i connettori Microsoft.  A tale scopo, contattare il [supporto clienti di Globanet](https://globanet.com/ms-connectors-contact). È necessario accedere a questo account quando si crea il connettore nel passaggio 1.

- L'utente che crea il connettore FX Connect nel passaggio 1 (e lo completa nel passaggio 3) deve essere assegnato al ruolo di importazione/esportazione delle cassette postali in Exchange Online. Questo ruolo è necessario per aggiungere connettori nella pagina **dei connettori dati** nel centro conformità di Microsoft 365. Per impostazione predefinita, questo ruolo non è assegnato a nessun gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo import export delle cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online. In alternativa, è possibile creare un gruppo di ruoli, assegnare il ruolo di esportazione delle cassette postali e quindi aggiungere gli utenti corretti come membri. Per ulteriori informazioni, vedere la sezione creare gruppi di [ruoli](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) o [modificare gruppi di ruoli](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) nell'articolo "gestire i gruppi di ruoli in Exchange Online".

## <a name="step-1-set-up-the-fx-connect-connector"></a>Passaggio 1: configurare il connettore di connessione FX

Il primo passaggio consiste nell'accedere alla pagina **dei connettori dati** nel centro conformità di Microsoft 365 e creare un connettore per i dati di connessione FX.

1. Andare a [https://compliance.microsoft.com](https://compliance.microsoft.com/) e quindi fare clic su **connettori dati**  >  **FX Connect**.

2. Nella pagina Descrizione prodotto **FX Connect** fare clic su **Aggiungi connettore**.

3. Nella pagina **condizioni del servizio** fare clic su **Accetto**.

4. Immettere un nome univoco che identifichi il connettore e quindi fare clic su **Avanti**.

5. Accedere al proprio account di Merge1 per configurare il connettore.

## <a name="step-2-configure-the-fx-connect-connector-on-the-globanet-merge1-site"></a>Passaggio 2: configurare il connettore FX Connect nel sito Merge1 di Globanet

Il secondo passaggio consiste nel configurare il connettore FX Connect nel sito Merge1. Per informazioni su come configurare il connettore FX Connect, vedere [Merge1 Third-Party Connectors user guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20FX%20Connect%20User%20Guide%20.pdf).

Dopo aver fatto clic su **salva & fine**, è possibile tornare al centro conformità di Microsoft 365 alla pagina **mapping utenti** nella procedura guidata del connettore.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Passaggio 3: mappare gli utenti e completare la configurazione del connettore

Per eseguire il mapping degli utenti e completare la configurazione del connettore nel centro conformità di Microsoft 365, eseguire la procedura seguente:

1. Nella pagina mapping **FX Connect users to Microsoft 365** Users, abilitare la mappatura automatica degli utenti. Gli elementi FX Connect includono una proprietà denominata *posta elettronica*, che contiene gli indirizzi di posta elettronica per gli utenti dell'organizzazione. Se il connettore può associare questo indirizzo a un utente di Microsoft 365, gli elementi vengono importati nella cassetta postale dell'utente.

2. Nella pagina **consenso amministratore** fare clic sul pulsante **Fornisci consenso** . L'utente verrà reindirizzato al sito Microsoft. Fare clic su **accetta** per fornire il consenso.

   L'organizzazione deve autorizzare il servizio di importazione di Office 365 per accedere ai dati delle cassette postali nell'organizzazione. Per fornire il consenso dell'amministratore, è necessario essere connessi con le credenziali di un amministratore globale di Microsoft 365 e quindi accettare la richiesta di consenso. Se non è stato eseguito l'accesso come amministratore globale, è possibile accedere a [Questa pagina](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) ed eseguire l'accesso con le credenziali di amministratore globale per accettare la richiesta.

3. Fare clic su **Avanti**, esaminare le impostazioni, quindi passare alla pagina **connettori dati** per visualizzare lo stato di avanzamento del processo di importazione per il nuovo connettore.

## <a name="step-4-monitor-the-fx-connect-connector"></a>Passaggio 4: monitorare il connettore di connessione FX

Dopo aver creato il connettore FX Connect, è possibile visualizzare lo stato del connettore nel centro conformità di Microsoft 365.

1. Andare a <https://compliance.microsoft.com/> e fare clic su **connettori dati** nel NAV sinistro.

2. Fare clic sulla scheda **connettori** e quindi selezionare il connettore **FX Connect** per visualizzare la pagina del riquadro a comparsa, che contiene le proprietà e le informazioni sul connettore.

3. In **stato connettore con origine**fare clic sul collegamento **Scarica log** per aprire o salvare il registro di stato del connettore. Questo log contiene dati che sono stati importati nel cloud Microsoft.

## <a name="known-issues"></a>Problemi noti

- Al momento, non è supportato l'importazione di allegati di dimensioni superiori a 10 MB, ma il supporto per gli elementi di grandi dimensioni sarà disponibile in una data successiva.
