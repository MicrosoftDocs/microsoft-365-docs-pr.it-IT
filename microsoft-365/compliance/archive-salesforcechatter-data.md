---
title: Configurare un connettore per l'archiviazione dei dati delle chiacchiere Salesforce in Microsoft 365
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
description: Gli amministratori possono configurare un connettore per l'importazione e l'archiviazione dei dati Chatter di Salesforce da Globanet a Microsoft 365. Questo connettore consente di archiviare i dati provenienti da origini dati di terze parti in Microsoft 365. Dopo l'archiviazione dei dati, è possibile utilizzare le funzionalità di conformità, ad esempio la conservazione legale, la ricerca del contenuto e i criteri di ritenzione per gestire i dati di terze parti.
ms.openlocfilehash: 60d86cd01ef8da3a02839d4a3f815be02dc1ee01
ms.sourcegitcommit: a3215cc22faa47e935d22300c481e47ab2680b44
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/21/2020
ms.locfileid: "49723026"
---
# <a name="set-up-a-connector-to-archive-salesforce-chatter-data-preview"></a>Configurare un connettore per archiviare i dati delle chiacchiere Salesforce (anteprima)

Utilizzare un connettore di Globanet nel centro conformità di Microsoft 365 per importare e archiviare i dati dalla piattaforma di Salesforce Chatter alle cassette postali degli utenti nell'organizzazione Microsoft 365. Globanet fornisce un connettore di [Salesforce Chatter](http://globanet.com/chatter/) che consente di acquisire elementi dall'origine dati di terze parti e di importare tali elementi in Microsoft 365. Il connettore converte il contenuto, ad esempio chat, allegati e messaggi da Salesforce Chatter, in un formato di messaggio di posta elettronica e quindi importa tali elementi nella cassetta postale dell'utente in Microsoft 365.

Dopo la memorizzazione dei dati delle chiacchiere su Salesforce nelle cassette postali degli utenti, è possibile applicare le funzionalità di conformità di Microsoft 365 come conservazione per controversia legale, eDiscovery, criteri di conservazione e etichette per il mantenimento. L'utilizzo di un connettore di Salesforce Chatter per l'importazione e l'archiviazione dei dati in Microsoft 365 può aiutare l'organizzazione a rimanere conforme ai criteri governativi e normativi.

## <a name="overview-of-archiving-salesforce-chatter-data"></a>Panoramica dell'archiviazione dei dati relativi alle chiacchiere di Salesforce

Nella panoramica seguente viene illustrato il processo di utilizzo di un connettore per archiviare i dati delle chiacchiere Salesforce in Microsoft 365.

![Flusso di lavoro di archiviazione per i dati delle chiacchiere Salesforce](../media/SalesforceChatterConnectorWorkflow.png)

1. L'organizzazione collabora con Salesforce Chatter per impostare e configurare un sito di Salesforce Chatter.

2. Una volta ogni 24 ore, gli elementi Chatter di Salesforce vengono copiati nel sito Merge1 di Globanet. Il connettore consente anche di Salesforce elementi Chatter a un formato di messaggio di posta elettronica.

3. Il connettore Salesforce Chatter creato nel centro conformità di Microsoft 365, si connette al sito di Globanet Merge1 ogni giorno e trasferisce il contenuto Chatter in una posizione di archiviazione sicura di Azure nel cloud Microsoft.

4. Il connettore importa gli elementi convertiti nelle cassette postali di utenti specifici utilizzando il valore della proprietà di *posta elettronica* del mapping automatico degli utenti, come descritto nel [passaggio 3](#step-3-map-users-and-complete-the-connector-setup). Una sottocartella della cartella posta in arrivo denominata **Salesforce Chatter** viene creata nelle cassette postali degli utenti e gli elementi vengono importati in tale cartella. Il connettore determina la cassetta postale a cui importare gli elementi utilizzando il valore della proprietà di *posta elettronica* . Ogni elemento Chatter contiene questa proprietà, che viene popolata con l'indirizzo di posta elettronica di tutti i partecipanti all'elemento.

## <a name="before-you-begin"></a>Prima di iniziare

- Creare un account Merge1 per i connettori Microsoft. Per creare un account, contattare il [supporto clienti di Globanet](https://globanet.com/contact-us/). È necessario accedere a questo account quando si crea il connettore nel passaggio 1.

- Creare un'applicazione Salesforce e acquisire un token all'indirizzo [https://salesforce.com](https://salesforce.com) . Sarà necessario accedere all'account Salesforce come amministratore e ottenere un token personale utente per importare i dati. Inoltre, gli inneschi devono essere pubblicati sul sito Chatter per acquisire gli aggiornamenti, le eliminazioni e le modifiche. Questi trigger creeranno un post su un canale e Merge1 acquisirà le informazioni dal canale. Per istruzioni dettagliate su come creare l'applicazione e acquisire il token, vedere [Merge1 Third-Party Connectors user guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20SalesForce%20Chatter%20User%20Guide%20.pdf).

- L'utente che crea il connettore Salesforce Chatter nel passaggio 1 (e lo completa nel passaggio 3) deve essere assegnato al ruolo di importazione/esportazione delle cassette postali in Exchange Online. Questo ruolo è necessario per aggiungere connettori nella pagina **dei connettori dati** nel centro conformità di Microsoft 365. Per impostazione predefinita, questo ruolo non è assegnato a nessun gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo import export delle cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online. In alternativa, è possibile creare un gruppo di ruoli, assegnare il ruolo di esportazione delle cassette postali e quindi aggiungere gli utenti corretti come membri. Per ulteriori informazioni, vedere la sezione creare gruppi di [ruoli](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) o [modificare gruppi di ruoli](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) nell'articolo "gestire i gruppi di ruoli in Exchange Online".

## <a name="step-1-set-up-the-salesforce-chatter-connector"></a>Passaggio 1: configurare il connettore per il chattering di Salesforce

Il primo passaggio consiste nell'accedere alla pagina **dei connettori dati** nel centro conformità di Microsoft 365 e creare un connettore per i dati relativi alle chiacchiere.

1. Andare a [https://compliance.microsoft.com](https://compliance.microsoft.com/) e quindi fare clic su **connettori dati**  >  **Salesforce Chatter**.

2. Nella pagina relativa alla descrizione del prodotto **Salesforce** , fare clic su **Aggiungi connettore**.

3. Nella pagina **condizioni del servizio** fare clic su **Accetto**.

4. Immettere un nome univoco che identifichi il connettore e quindi fare clic su **Avanti**.

5. Accedere al proprio account di Merge1 per configurare il connettore.

## <a name="step-2-configure-the-salesforce-chatter-on-the-globanet-merge1-site"></a>Passaggio 2: configurare il chattering di Salesforce sul sito di Merge1 di Globanet

Il secondo passaggio consiste nel configurare il connettore di Salesforce Chatter sul sito di Merge1 di Globanet. Per informazioni su come configurare il connettore di Salesforce, vedere [Merge1 di terze parti dei connettori utente](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20SalesForce%20Chatter%20User%20Guide%20.pdf).

Dopo aver fatto clic su **salva & fine,** viene visualizzata la pagina di **mapping degli utenti** nella procedura guidata del connettore nel centro conformità di Microsoft 365.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Passaggio 3: mappare gli utenti e completare la configurazione del connettore

Per eseguire il mapping degli utenti e completare la configurazione del connettore nel centro conformità di Microsoft 365, eseguire la procedura seguente:

1. Nella pagina mapping utenti **di Salesforce Chatter to Microsoft 365** Users, abilitare il mapping automatico degli utenti. Gli elementi Chatter di Salesforce includono una proprietà denominata *posta elettronica*, che contiene gli indirizzi di posta elettronica per gli utenti dell'organizzazione. Se il connettore può associare questo indirizzo a un utente di Microsoft 365, gli elementi vengono importati nella cassetta postale dell'utente.

2. fare clic su **Avanti**, esaminare le impostazioni, quindi passare alla pagina **connettori dati** per visualizzare lo stato di avanzamento del processo di importazione per il nuovo connettore.

## <a name="step-4-monitor-the-salesforce-chatter-connector"></a>Passaggio 4: monitorare il connettore di chattering Salesforce

Dopo aver creato il connettore Salesforce Chatter, è possibile visualizzare lo stato del connettore nel centro conformità di Microsoft 365.

1. Andare a [https://compliance.microsoft.com](https://compliance.microsoft.com/) e fare clic su **connettori dati** nel NAV sinistro.

2. fare clic sulla scheda **connettori** e quindi su **Salesforce Chatter** Connector per visualizzare la pagina del riquadro a comparsa, che contiene le proprietà e le informazioni sul connettore.

3. In **stato connettore con origine** fare clic sul collegamento **Scarica log** per aprire o salvare il registro di stato del connettore. Questo log contiene dati che sono stati importati nel cloud Microsoft.

## <a name="known-issues"></a>Problemi noti

- Al momento, non è supportato l'importazione di allegati o elementi di dimensioni superiori a 10 MB. Il supporto per gli elementi di grandi dimensioni sarà disponibile in un secondo momento.
