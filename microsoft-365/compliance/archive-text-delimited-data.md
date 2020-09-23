---
title: Configurare un connettore per l'archiviazione dei dati delimitati da testo in Microsoft 365
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
description: Gli amministratori possono configurare un connettore per l'importazione e l'archiviazione dei dati delimitati da testo da Globanet in Microsoft 365. In questo modo è possibile archiviare i dati provenienti da origini dati di terze parti in Microsoft 365 per poter utilizzare le funzionalità di conformità, come la conservazione legale, la ricerca di contenuto e i criteri di ritenzione per gestire i dati di terze parti dell'organizzazione.
ms.openlocfilehash: 854e678067a26fd5fa1f89eb4b2f4f0327eac7a0
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "48196575"
---
# <a name="set-up-a-connector-to-archive-text-delimited-data"></a>Configurare un connettore per l'archiviazione dei dati delimitati da testo

Utilizzare un connettore di Globanet nel centro conformità di Microsoft 365 per importare e archiviare i dati delimitati da testo nelle cassette postali degli utenti nell'organizzazione Microsoft 365. [Globanet](https://globanet.com/merge1/) fornisce un connettore delimitato da testo configurato per acquisire elementi da un'origine dati di terze parti (su base regolare) e importare tali elementi in Microsoft 365. Il connettore converte il contenuto dall'origine dati delimitata da testo a un formato di messaggio di posta elettronica e quindi importa tali elementi nella cassetta postale dell'utente in Microsoft 365.

Dopo che i dati delimitati da testo sono archiviati nelle cassette postali degli utenti, è possibile applicare funzionalità di conformità di Microsoft 365, ad esempio conservazione per controversia legale, eDiscovery, criteri di conservazione e etichette per il mantenimento e conformità della comunicazione. L'utilizzo di un connettore zoom meetings per l'importazione e l'archiviazione dei dati in Microsoft 365 può aiutare l'organizzazione a rimanere conforme ai criteri governativi e normativi.

Dopo l'archiviazione, le comunicazioni di origine delimitate da testo possono essere conservate, controllate per la conformità e recuperate per eDiscovery e per la governance delle informazioni interne.

## <a name="overview-of-archiving-the-text-delimited-source"></a>Panoramica dell'archiviazione dell'origine delimitata da testo

Nella panoramica seguente viene illustrato il processo di utilizzo di un connettore per archiviare le informazioni di origine delimitate da testo in Microsoft 365.

![Flusso di lavoro di archiviazione per i dati delimitati da testo](../media/TextDelimitedConnectorWorkflow.png)

1. L'organizzazione opera con l'origine delimitata da testo per impostare e configurare un sito delimitato da testo.

2. Una volta ogni 24 ore, i messaggi di chat provenienti dall'origine delimitata da testo vengono copiati nel sito Merge1 di Globanet. Il connettore converte anche il contenuto in un formato di messaggio di posta elettronica.

3. Il connettore delimitato da testo creato nel centro conformità di Microsoft 365, si connette al sito di Globanet Merge1 ogni giorno e trasferisce i messaggi a una posizione di archiviazione sicura di Azure nel cloud Microsoft.

4. Il connettore importa gli elementi del messaggio convertiti nelle cassette postali di utenti specifici utilizzando il valore della proprietà di *posta elettronica* del mapping automatico degli utenti, come descritto nel passaggio 3. Verrà creata una nuova sottocartella nella cartella posta in arrivo denominata **Text-Delimited** nelle cassette postali degli utenti e gli elementi del messaggio verranno importati nella cartella. Il connettore esegue questa operazione utilizzando il valore della proprietà di *posta elettronica* . Ogni messaggio contiene questa proprietà, che viene popolata con l'indirizzo di posta elettronica di ogni partecipante del messaggio.

## <a name="before-you-begin"></a>Prima di iniziare

- Creare un account Merge1 di Globanet per i connettori Microsoft. A tale scopo, contattare il [supporto clienti di Globanet](https://globanet.com/ms-connectors-contact). È necessario accedere a questo account quando si crea il connettore nel passaggio 1.

- L'utente che crea il connettore delimitato da testo nel passaggio 1 (e lo completa nel passaggio 3) deve essere assegnato al ruolo di importazione/esportazione delle cassette postali in Exchange Online. Questo ruolo è necessario per aggiungere connettori nella pagina **dei connettori dati** nel centro conformità di Microsoft 365. Per impostazione predefinita, questo ruolo non è assegnato a nessun gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo import export delle cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online. In alternativa, è possibile creare un gruppo di ruoli, assegnare il ruolo di esportazione delle cassette postali e quindi aggiungere gli utenti corretti come membri. Per ulteriori informazioni, vedere la sezione creare gruppi di [ruoli](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) o [modificare gruppi di ruoli](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) nell'articolo "gestire i gruppi di ruoli in Exchange Online".

## <a name="step-1-set-up-the-text-delimited-connector"></a>Passaggio 1: configurare il connettore delimitato da testo

Il primo passaggio consiste nell'accedere alla pagina **dei connettori dati** nel centro conformità di Microsoft 365 e creare un connettore per i dati delimitati da testo.

1. Andare a [https://compliance.microsoft.com](https://compliance.microsoft.com/) e quindi fare clic su **connettori dati**  >  **delimitati da testo**.

2. Nella pagina Descrizione prodotto **delimitato da testo** fare clic su **Aggiungi connettore**.

3. Nella pagina **condizioni del servizio** fare clic su **Accetto**.

4. Immettere un nome univoco che identifichi il connettore e quindi fare clic su **Avanti**.

5. Accedere al proprio account di Merge1 per configurare il connettore.

## <a name="step-2-configure-the-text-delimited-connector-on-the-globanet-merge1-site"></a>Passaggio 2: configurare il connettore delimitato da testo nel sito di Merge1 di Globanet

Il secondo passaggio consiste nel configurare il connettore delimitato da testo nel sito di Merge1. Per informazioni sulla configurazione del connettore delimitato da testo nel sito di Globanet Merge1, vedere [Merge1 di terze parti dei connettori utente](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Text-Delimited%20User%20Guide%20.pdf).

Dopo aver fatto clic su **salva & fine**, tornare al centro conformità Microsoft 365 alla pagina **mapping utenti** della procedura guidata del connettore.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Passaggio 3: mappare gli utenti e completare la configurazione del connettore

Per eseguire il mapping degli utenti e completare la configurazione del connettore nel centro conformità di Microsoft 365, eseguire la procedura seguente:

1. Nella pagina mapping **utenti esterni a Microsoft 365** , abilitare il mapping automatico degli utenti. Gli elementi di origine delimitati da testo includono una proprietà denominata *posta elettronica*, che contiene gli indirizzi di posta elettronica per gli utenti dell'organizzazione. Se il connettore può associare questo indirizzo a un utente di Microsoft 365, gli elementi vengono importati nella cassetta postale dell'utente.

2. Nella pagina **consenso amministratore** fare clic sul pulsante **Fornisci consenso** . L'utente verrà reindirizzato al sito Microsoft. Fare clic su **accetta** per fornire il consenso.

   L'organizzazione deve autorizzare il servizio di importazione di Office 365 per accedere ai dati delle cassette postali nell'organizzazione. Per fornire il consenso dell'amministratore, è necessario essere connessi con le credenziali di un amministratore globale di Microsoft 365 e quindi accettare la richiesta di consenso. Se non è stato eseguito l'accesso come amministratore globale, è possibile accedere a [Questa pagina](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) ed eseguire l'accesso con le credenziali di amministratore globale per accettare la richiesta.

3. Fare clic su **Avanti**, esaminare le impostazioni, quindi passare alla pagina **connettori dati** per visualizzare lo stato di avanzamento del processo di importazione per il nuovo connettore.

## <a name="step-4-monitor-the-text-delimited-connector"></a>Passaggio 4: monitorare il connettore delimitato da testo

Dopo aver creato il connettore delimitato da testo, è possibile visualizzare lo stato del connettore nel centro conformità di Microsoft 365.

1. Andare a [https://compliance.microsoft.com](https://compliance.microsoft.com) e fare clic su **connettori dati** nel NAV sinistro.

2. Fare clic sulla scheda **connettori** e quindi selezionare il connettore **delimitato da testo** per visualizzare la pagina del riquadro a comparsa, che contiene le proprietà e le informazioni sul connettore.

3. In **stato connettore con origine**fare clic sul collegamento **Scarica log** per aprire o salvare il registro di stato del connettore. Questo log contiene informazioni sui dati che sono stati importati nel cloud Microsoft.

## <a name="known-issues"></a>Problemi noti

- Al momento, non è supportato l'importazione di allegati o elementi di dimensioni superiori a 10 MB. Il supporto per gli elementi di grandi dimensioni sarà disponibile in un secondo momento.
