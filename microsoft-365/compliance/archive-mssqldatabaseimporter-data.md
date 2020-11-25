---
title: Configurare un connettore per l'archiviazione dei dati dal database MS SQL
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
description: Gli amministratori possono configurare un connettore per l'importazione e l'archiviazione dei dati dal database MS SQL. Questo connettore consente di archiviare i dati provenienti da origini dati di terze parti in Microsoft 365. Dopo l'archiviazione dei dati, è possibile utilizzare le funzionalità di conformità, ad esempio la conservazione legale, la ricerca del contenuto e i criteri di ritenzione per gestire i dati di terze parti.
ms.openlocfilehash: 576ba38616b9a6a9c1b0e7c78c5e8d03c5a0e9df
ms.sourcegitcommit: 95b85a1fdf43e3f0839483fa22e279262703f15f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/24/2020
ms.locfileid: "49407300"
---
# <a name="set-up-a-connector-to-archive-data-from-ms-sql-database"></a>Configurare un connettore per l'archiviazione dei dati dal database MS SQL

Utilizzare un connettore di Globanet nel centro conformità di Microsoft 365 per importare e archiviare i dati dal database MS SQL alle cassette postali degli utenti nell'organizzazione Microsoft 365. Globanet fornisce un connettore di importazione di database MS SQL configurato per acquisire elementi da un database utilizzando un file di configurazione XML e importare tali elementi in Microsoft 365. Il connettore converte il contenuto dal database MS SQL a un formato di messaggio di posta elettronica e quindi importa tali elementi nelle cassette postali degli utenti in Microsoft 365.

Dopo che il contenuto del database MS SQL è stato archiviato nelle cassette postali degli utenti, è possibile applicare le funzionalità di conformità di Microsoft 365, ad esempio il blocco per controversia legale, eDiscovery, criteri di conservazione e etichette L'utilizzo di un connettore di database MS SQL per l'importazione e l'archiviazione dei dati in Microsoft 365 può aiutare l'organizzazione a rimanere conforme ai criteri governativi e normativi.

## <a name="overview-of-archiving-the-ms-sql-data"></a>Panoramica dell'archiviazione dei dati di MS SQL

Nella panoramica seguente viene illustrato il processo di utilizzo di un connettore per l'archiviazione dei dati di MS SQL in Microsoft 365.

![Flusso di lavoro di archiviazione per dati MS SQL](../media/MSSQLDatabaseConnectorWorkflow.png)

1. L'organizzazione utilizza un provider di database MS SQL per impostare e configurare un sito di database MS SQL.

2. Una volta ogni 24 ore, gli elementi di database MS SQL vengono copiati nel sito Merge1 di Globanet. Il connettore converte anche questo contenuto in un formato di messaggio di posta elettronica.

3. Il connettore di importazione del database di MS SQL creato nel centro conformità Microsoft 365, si connette al sito di Globanet Merge1 ogni giorno e trasferisce i messaggi a una posizione di archiviazione sicura di Azure nel cloud Microsoft.

4. Il connettore importa gli elementi di database MS SQL convertiti nelle cassette postali di utenti specifici utilizzando il valore della proprietà di *posta elettronica* del mapping automatico degli utenti, come descritto nel [passaggio 3](#step-3-map-users-and-complete-the-connector-setup). Una sottocartella della cartella posta in arrivo denominata **MS SQL importatore database** viene creata nelle cassette postali degli utenti e gli elementi vengono importati in tale cartella. Il connettore determina la cassetta postale a cui importare gli elementi utilizzando il valore della proprietà di *posta elettronica* . Ogni elemento del database MS SQL contiene questa proprietà, che viene popolata con l'indirizzo di posta elettronica di tutti i partecipanti all'elemento.

## <a name="before-you-begin"></a>Informazioni preliminari

- Creare un account Merge1 di Globanet per i connettori Microsoft. Per creare un account, contattare il [supporto clienti di Globanet](https://globanet.com/contact-us/). È necessario accedere a questo account quando si crea il connettore nel passaggio 1.

- L'utente che crea il connettore dell'utilità di importazione del database di MS SQL nel passaggio 1 (e lo completa nel passaggio 3) deve essere assegnato al ruolo di esportazione delle cassette postali in Exchange Online. Questo ruolo è necessario per aggiungere connettori nella pagina dei connettori dati nel centro conformità di Microsoft 365. Per impostazione predefinita, questo ruolo non è assegnato a nessun gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo import export delle cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online. In alternativa, è possibile creare un gruppo di ruoli, assegnare il ruolo di esportazione delle cassette postali e quindi aggiungere gli utenti corretti come membri. Per ulteriori informazioni, vedere la sezione creare gruppi di [ruoli](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) o [modificare gruppi di ruoli](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) nell'articolo "gestire i gruppi di ruoli in Exchange Online".

## <a name="step-1-set-up-the-ms-sql-database-importer-connector"></a>Passaggio 1: configurare il connettore dell'utilità di importazione del database di MS SQL

Il primo passaggio consiste nell'accedere alla pagina **dei connettori dati** nel centro conformità di Microsoft365 e creare un connettore per il database MS SQL.

1. Andare a [https://compliance.microsoft.com](https://compliance.microsoft.com) e quindi fare clic su **connettore dati**  >  **MS SQL importatore database**.

2. Nella pagina Descrizione prodotto **importatore database di MS SQL** fare clic su **Aggiungi nuovo connettore**.

3. Nella pagina **condizioni del servizio** fare clic su **Accetto**.

4. Immettere un nome univoco che identifichi il connettore e quindi fare clic su **Avanti**.

5. Accedere al proprio account di Merge1 per configurare il connettore.

## <a name="step-2-configure-the-ms-sql-database-importer-connector-on-the-globanet-merge1-site"></a>Passaggio 2: configurare il connettore dell'utilità di importazione del database di MS SQL nel sito Merge1 di Globanet

Il secondo passaggio consiste nel configurare il connettore dell'utilità di importazione del database di MS SQL nel sito di Merge1. Per informazioni su come configurare l'utilità di importazione del database di MS SQL, vedere [Merge1 di terze parti dei connettori utente](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20MS%20SQL%20Database%20Importer%20User%20Guide%20.pdf).

Dopo aver fatto clic su **salva & fine**, viene visualizzata la pagina di **mapping degli utenti** nella procedura guidata del connettore nel centro conformità di Microsoft 365.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Passaggio 3: mappare gli utenti e completare la configurazione del connettore

Per eseguire il mapping degli utenti e completare la configurazione del connettore, eseguire la procedura seguente:

1. Nella pagina utenti **utilità di importazione del database MS SQL di Microsoft 365** , abilitare la mappatura automatica degli utenti. Gli elementi di database MS SQL includono una proprietà denominata *posta elettronica*, che contiene gli indirizzi di posta elettronica per gli utenti dell'organizzazione. Se il connettore può associare questo indirizzo a un utente di Microsoft 365, gli elementi vengono importati nella cassetta postale dell'utente.

2. Nella pagina **consenso amministratore** fare clic sul pulsante **Fornisci consenso** . L'utente verrà reindirizzato al sito Microsoft. Fare clic su **accetta** per fornire il consenso.

   L'organizzazione deve autorizzare il servizio di importazione di Office 365 per accedere ai dati delle cassette postali nell'organizzazione. Per fornire il consenso dell'amministratore, è necessario essere connessi con le credenziali di un amministratore globale di Microsoft 365 e quindi accettare la richiesta di consenso. Se non è stato eseguito l'accesso come amministratore globale, è possibile accedere a [Questa pagina](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) ed eseguire l'accesso con le credenziali di amministratore globale per accettare la richiesta.

3. Fare clic su **Avanti**, rivedere le impostazioni e passare alla pagina **connettori dati** per visualizzare lo stato di avanzamento del processo di importazione per il nuovo connettore.

## <a name="step-4-monitor-the-ms-sql-database-importer-connector"></a>Passaggio 4: monitorare il connettore dell'utilità di importazione del database di MS SQL

Dopo aver creato il connettore dell'utilità di importazione del database di MS SQL, è possibile visualizzare lo stato del connettore nel centro conformità di Microsoft 365.

1. Andare a <https://compliance.microsoft.com/> e fare clic su **connettori dati** nel NAV sinistro.

2. Fare clic sulla scheda **connettori** e quindi selezionare il connettore di **importazione** **database di MS SQL** per visualizzare la pagina del riquadro a comparsa, che contiene le proprietà e le informazioni sul connettore.

3. In **stato connettore con origine** fare clic sul collegamento **Scarica log** per aprire o salvare il registro di stato del connettore. Questo log contiene dati che sono stati importati nel cloud Microsoft.

## <a name="known-issues"></a>Problemi noti

- Al momento, non è supportato l'importazione di allegati o elementi di dimensioni superiori a 10 MB. Il supporto per gli elementi di grandi dimensioni sarà disponibile in un secondo momento.
