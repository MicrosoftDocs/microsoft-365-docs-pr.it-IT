---
title: Configurare un connettore per archiviare Cisco Jabber sui dati MS SQL in Microsoft 365
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
description: Gli amministratori possono configurare un connettore per l'importazione e l'archiviazione dei dati Jabber Cisco da Globanet in Microsoft 365. Questo connettore consente di archiviare i dati provenienti da origini dati di terze parti in Microsoft 365, in modo da poter utilizzare le funzionalità di conformità, come la conservazione legale, la ricerca di contenuto e i criteri di ritenzione per gestire i dati di terze parti dell'organizzazione.
ms.openlocfilehash: c87449c35d588fd886d9d108f136eea0a4799ccf
ms.sourcegitcommit: ae3aa7f29be16d08950cf23cad489bc069aa8617
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/09/2020
ms.locfileid: "48409190"
---
# <a name="set-up-a-connector-to-archive-cisco-jabber-data-preview"></a>Configurare un connettore per l'archiviazione dei dati Jabber Cisco (Preview)

Utilizzare un connettore di Globanet nel centro conformità di Microsoft 365 per importare e archiviare i dati dalla piattaforma Cisco Jabber alle cassette postali degli utenti nell'organizzazione Microsoft 365. Globanet fornisce un connettore [Cisco Jabber](https://globanet.com/jabber/) configurato per acquisire elementi dal database MS SQL di Jabber, ad esempio i messaggi di chat di 1:1 e le chat di gruppo e quindi importare tali elementi in Microsoft 365. Il connettore recupera i dati dal database MS SQL di Cisco Jabber, lo elabora e converte i contenuti dall'account Jabber Cisco di un utente in un formato di messaggio di posta elettronica e quindi importa tali elementi nella cassetta postale dell'utente in Microsoft 365.

Dopo che i dati di Jabber Cisco sono archiviati nelle cassette postali degli utenti, è possibile applicare le funzionalità di conformità di Microsoft 365 come il blocco per controversia legale, eDiscovery, criteri di conservazione e etichette di conservazione e conformità alla comunicazione. L'utilizzo di un connettore Jabber Cisco per l'importazione e l'archiviazione dei dati in Microsoft 365 può aiutare l'organizzazione a rimanere conforme ai criteri governativi e normativi.

## <a name="overview-of-archiving-cisco-jabber-data"></a>Panoramica dell'archiviazione dei dati di Cisco Jabber

Nella panoramica seguente viene illustrato il processo di utilizzo di un connettore per l'archiviazione dei dati di Jabber Cisco in Microsoft 365.

![Flusso di lavoro di archiviazione per i dati Cisco Jabber](../media/CiscoJabberonMSSQLConnectorWorkflow.png)

1. L'organizzazione collabora con Cisco per impostare e configurare un Jabber Cisco sul database MS SQL.

2. Una volta ogni 24 ore, gli elementi Jabber Cisco vengono copiati dal database MS SQL al sito di Globanet Merge1. Il connettore converte anche il contenuto dei messaggi di chat in un formato di messaggio di posta elettronica.

3. Il connettore di Jabber Cisco creato nel centro conformità Microsoft 365 si connette al sito di Globanet Merge1 ogni giorno e trasferisce gli elementi in una posizione di archiviazione sicura di Azure nel cloud Microsoft.

4. Il mapping utente automatico come connettore importa gli elementi nelle cassette postali di utenti specifici utilizzando il valore della proprietà di *posta elettronica* descritta nel [passaggio 3](#step-3-map-users-and-complete-the-connector-setup). Una sottocartella della cartella posta in arrivo denominata **Cisco Jabber su MS SQL** viene creata nelle cassette postali degli utenti e gli elementi del messaggio vengono importati in tale cartella. Il connettore esegue questa operazione utilizzando il valore della proprietà di *posta elettronica* . Ogni elemento Jabber Cisco contiene questa proprietà, che viene popolata con l'indirizzo di posta elettronica di ogni partecipante dei messaggi.

## <a name="before-you-begin"></a>Prima di iniziare

- Creare un account Merge1 di Globanet per i connettori Microsoft. A tale scopo, contattare il [supporto clienti di Globanet](https://globanet.com/ms-connectors-contact/). È necessario accedere a questo account quando si crea il connettore nel passaggio 1.

- È necessario configurare un database MS SQL per recuperare gli elementi Jabber prima di creare il connettore nel passaggio 1. È possibile specificare le impostazioni di connessione per il database MS SQL quando si configura il connettore Cisco Jabber nel passaggio 2. Per ulteriori informazioni, vedere la [Guida per l'utente dei connettori di terze parti di Merge1](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20MS%20SQL%20User%20Guide%20.pdf).

- L'utente che crea il connettore di Jabber Cisco nel passaggio 1 (e lo completa nel passaggio 3) deve essere assegnato al ruolo di importazione/esportazione delle cassette postali in Exchange Online. Questo ruolo è necessario per aggiungere connettori nella pagina **dei connettori dati** nel centro conformità di Microsoft 365. Per impostazione predefinita, questo ruolo non è assegnato a nessun gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo import export delle cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online. In alternativa, è possibile creare un gruppo di ruoli, assegnare il ruolo di esportazione delle cassette postali e quindi aggiungere gli utenti corretti come membri. Per ulteriori informazioni, vedere la sezione creare gruppi di [ruoli](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) o [modificare gruppi di ruoli](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) nell'articolo "gestire i gruppi di ruoli in Exchange Online".

## <a name="step-1-set-up-the-cisco-jabber-connector"></a>Passaggio 1: configurare il connettore Jabber Cisco

Il primo passaggio consiste nell'accedere ai **connettori di dati** nel centro conformità di Microsoft 365 e creare un connettore per Cisco Jabber sui dati MS SQL.

1. Andare a [https://compliance.microsoft.com](https://compliance.microsoft.com/) e quindi fare clic su **connettori dati**  >  **Cisco Jabber su MS SQL**.

2. Nella pagina di descrizione del prodotto **Cisco Jabber su MS SQL** fare clic su **Aggiungi connettore**.

3. Nella pagina **condizioni del servizio** fare clic su **Accetto**.

4. Immettere un nome univoco che identifichi il connettore e quindi fare clic su **Avanti**.

5. Accedere al proprio account di Merge1 per configurare il connettore.

## <a name="step-2-configure-the-cisco-jabber-connector-on-the-globanet-merge1-site"></a>Passaggio 2: configurare il connettore di Jabber Cisco sul sito di Merge1 di Globanet

Il secondo passaggio consiste nel configurare il Jabber Cisco sul connettore MS SQL sul sito di Merge1 di Globanet. Per informazioni su come configurare la Jabber Cisco sul connettore MS SQL, vedere [Merge1 di terze parti connettori utente](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20MS%20SQL%20User%20Guide%20.pdf).

Dopo aver fatto clic su **salva & fine**, è possibile tornare al centro conformità Microsoft 365 alla pagina **mapping utenti** nella procedura guidata del connettore.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Passaggio 3: mappare gli utenti e completare la configurazione del connettore

Per eseguire il mapping degli utenti e completare il connettore configurato nel centro conformità Microsoft 365, attenersi alla seguente procedura:

1. Sulla pagina **Cisco Jabber della mappa degli utenti di MS SQL alla pagina Microsoft 365** Users, abilitare il mapping automatico degli utenti. La Jabber Cisco sugli elementi di MS SQL include una proprietà chiamata *posta elettronica*, che contiene gli indirizzi di posta elettronica per gli utenti dell'organizzazione. Se il connettore può associare questo indirizzo a un utente di Microsoft 365, gli elementi vengono importati nella cassetta postale dell'utente.

2. Nella pagina **consenso amministratore** fare clic su **Fornisci consenso**. L'utente verrà reindirizzato al sito Microsoft. Fare clic su **accetta** per fornire il consenso.

   L'organizzazione deve autorizzare il servizio di importazione di Office 365 per accedere ai dati delle cassette postali nell'organizzazione. Per fornire il consenso dell'amministratore, è necessario essere connessi con le credenziali di un amministratore globale di Microsoft 365 e quindi accettare la richiesta di consenso. Se non è stato eseguito l'accesso come amministratore globale, è possibile accedere a [Questa pagina](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) ed eseguire l'accesso con le credenziali di amministratore globale per accettare la richiesta.

3. Fare clic su **Avanti**, rivedere le impostazioni e passare alla pagina **connettori dati** per visualizzare lo stato di avanzamento del processo di importazione per il nuovo connettore.

## <a name="step-4-monitor-the-cisco-jabber-connector"></a>Passaggio 4: monitorare il connettore Jabber Cisco

Dopo aver creato la Jabber Cisco sul connettore MS SQL, è possibile visualizzare lo stato del connettore nel centro conformità di Microsoft 365.

1. Andare a [https://compliance.microsoft.com](https://compliance.microsoft.com) e fare clic su **connettori dati** nel NAV sinistro.

2. Fare clic sulla scheda **connettori** e quindi selezionare il connettore **Cisco Jabber su MS SQL** per visualizzare la pagina a comparsa, che contiene le proprietà e le informazioni sul connettore.

3. In **stato connettore con origine**fare clic sul collegamento **Scarica log** per aprire o salvare il registro di stato del connettore. Questo log contiene dati che sono stati importati nel cloud Microsoft.

## <a name="known-issues"></a>Problemi noti

- Al momento, non è supportato l'importazione di allegati o elementi di dimensioni superiori a 10 MB. Il supporto per gli elementi di grandi dimensioni sarà disponibile in un secondo momento.
