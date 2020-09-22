---
title: Configurare un connettore per l'archiviazione dei dati di Symphony in Microsoft 365
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
description: Gli amministratori possono configurare un connettore per l'importazione e l'archiviazione dei dati da Globanet Symphony in Microsoft 365. Questo connettore consente di archiviare i dati provenienti da origini dati di terze parti in Microsoft 365, in modo da poter utilizzare le funzionalità di conformità, come la conservazione legale, la ricerca di contenuto e i criteri di ritenzione per gestire i dati di terze parti dell'organizzazione.
ms.openlocfilehash: ade08b0f6f82bb2c76cdaf033e276909b5ec2122
ms.sourcegitcommit: 57b37a3ce40f205c7320d5be1a0d906dd492b863
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2020
ms.locfileid: "47405531"
---
# <a name="set-up-a-connector-to-archive-symphony-data-preview"></a>Configurare un connettore per l'archiviazione dei dati di Symphony (anteprima)

Utilizzare un connettore di Globanet nel centro conformità di Microsoft 365 per importare e archiviare i dati di Symphony nelle cassette postali degli utenti nell'organizzazione Microsoft 365. Symphony è una piattaforma di messaggistica e collaborazione utilizzata nel settore dei servizi finanziari. Globanet fornisce un [connettore di dati Symphony](https://globanet.com/symphony) nel centro conformità di Microsoft 365 che è possibile configurare per acquisire elementi dall'origine dati di terze parti (su base regolare) e quindi importare tali elementi nelle cassette postali degli utenti. Il connettore converte il contenuto di un elemento dall'account Symphony in un formato di messaggio di posta elettronica e quindi importa l'elemento in una cassetta postale in Microsoft 365.

Dopo che le comunicazioni Symphony sono state archiviate nelle cassette postali degli utenti, è possibile applicare le funzionalità di conformità di Microsoft 365 come conservazione per controversia legale, eDiscovery, criteri di conservazione e etichette per il mantenimento e conformità della comunicazione. L'utilizzo di un connettore Symphony per l'importazione e l'archiviazione dei dati in Microsoft 365 può aiutare l'organizzazione a rimanere conforme ai criteri governativi e normativi.

## <a name="overview-of-archiving-symphony-data"></a>Panoramica dei dati di archiviazione Symphony

Nella panoramica seguente viene illustrato il processo di utilizzo di un connettore di dati per l'archiviazione delle comunicazioni Symphony in Microsoft 365.

![Flusso di lavoro di archiviazione Symphony](../media/SymphonyConnectorWorkflow.png)

1. La propria organizzazione collabora con Symphony per impostare e configurare un sito Symphony.

2. Una volta ogni 24 ore, i messaggi di chat provenienti da Symphony vengono copiati nel sito Merge1 di Globanet. Il connettore converte anche il contenuto di un messaggio di chat in un formato di messaggio di posta elettronica.

3. Il connettore Symphony creato nel centro conformità di Microsoft 365, si connette al sito di Globanet Merge1 ogni giorno e trasferisce i messaggi a una posizione di archiviazione sicura di Azure nel cloud Microsoft.

4. Il connettore importa gli elementi del messaggio convertiti nelle cassette postali di utenti specifici utilizzando il valore della proprietà di *posta elettronica* del mapping automatico degli utenti, come descritto nel passaggio 3. Viene creata una nuova sottocartella nella cartella posta in arrivo denominata **Symphony** nelle cassette postali degli utenti e gli elementi del messaggio vengono importati in tale cartella. Il connettore esegue questa operazione utilizzando il valore della proprietà di *posta elettronica* . Ogni messaggio di chat contiene questa proprietà, che viene popolata con l'indirizzo di posta elettronica di ogni partecipante del messaggio di chat.

## <a name="before-you-begin"></a>Informazioni preliminari

- Creare un account Merge1 di Globanet per i connettori Microsoft. A tale scopo, contattare il [supporto clienti di Globanet](https://globanet.com/ms-connectors-contact). È necessario accedere a questo account quando si crea il connettore nel passaggio 1.

- L'utente che crea il connettore Symphony nel passaggio 1 (e lo completa nel passaggio 3) deve essere assegnato al ruolo di importazione/esportazione delle cassette postali in Exchange Online. Questo ruolo è necessario per aggiungere connettori nella pagina **dei connettori dati** nel centro conformità di Microsoft 365. Per impostazione predefinita, questo ruolo non è assegnato a nessun gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo import export delle cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online. In alternativa, è possibile creare un gruppo di ruoli, assegnare il ruolo di esportazione delle cassette postali e quindi aggiungere gli utenti corretti come membri. Per ulteriori informazioni, vedere la sezione creare gruppi di [ruoli](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) o [modificare gruppi di ruoli](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) nell'articolo "gestire i gruppi di ruoli in Exchange Online".

## <a name="step-1-set-up-the-symphony-connector"></a>Passaggio 1: configurare il connettore Symphony

Il primo passaggio consiste nell'accedere alla pagina **dei connettori dati** nel centro conformità di Microsoft 365 e creare un connettore per i dati di Symphony.

1. Andare a [https://compliance.microsoft.com](https://compliance.microsoft.com/) e quindi fare clic su Symphony **connettori data**  >  **Symphony**.

2. Nella pagina Descrizione prodotto **Symphony** fare clic su **Aggiungi connettore**.

3. Nella pagina **condizioni del servizio** fare clic su **Accetto**.

4. Immettere un nome univoco che identifichi il connettore e quindi fare clic su **Avanti**.

5. Accedere al proprio account di Merge1 per configurare il connettore.

## <a name="configure-the-symphony-connector-on-the-globanet-merge1-site"></a>Configurare il connettore Symphony nel sito Merge1 di Globanet

Il secondo passaggio consiste nel configurare il connettore Symphony nel sito di Merge1. Per informazioni sulla configurazione del connettore Symphony nel sito di Globanet Merge1, vedere [Merge1 di terze parti dei connettori utente](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Symphony%20User%20Guide%20.pdf).

Dopo aver fatto clic su **salva & fine**, tornare al centro conformità Microsoft 365 alla pagina **mapping utenti** della procedura guidata del connettore.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Passaggio 3: mappare gli utenti e completare la configurazione del connettore

Per eseguire il mapping degli utenti e completare la configurazione del connettore nel centro conformità di Microsoft 365, eseguire la procedura seguente:

1. Nella pagina mapping **utenti esterni a Microsoft 365** , abilitare il mapping automatico degli utenti. Gli elementi sinfonici includono una proprietà denominata *posta elettronica*, che contiene gli indirizzi di posta elettronica per gli utenti dell'organizzazione. Se il connettore può associare questo indirizzo a un utente di Microsoft 365, gli elementi vengono importati nella cassetta postale dell'utente.

2. Nella pagina **consenso amministratore** fare clic sul pulsante **Fornisci consenso** . L'utente verrà reindirizzato al sito Microsoft. Fare clic su **accetta** per fornire il consenso.

   L'organizzazione deve autorizzare il servizio di importazione di Office 365 per accedere ai dati delle cassette postali nell'organizzazione. Per fornire il consenso dell'amministratore, è necessario essere connessi con le credenziali di un amministratore globale di Microsoft 365 e quindi accettare la richiesta di consenso. Se non è stato eseguito l'accesso come amministratore globale, è possibile accedere a [Questa pagina](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) ed eseguire l'accesso con le credenziali di amministratore globale per accettare la richiesta.

3. Fare clic su **Avanti**, esaminare le impostazioni, quindi passare alla pagina **connettori dati** per visualizzare lo stato di avanzamento del processo di importazione per il nuovo connettore.

## <a name="step-4-monitor-the-symphony-connector"></a>Passaggio 4: monitorare il connettore Symphony

Dopo aver creato il connettore Symphony, è possibile visualizzare lo stato del connettore nel centro conformità di Microsoft 365.

1. Andare a [https://compliance.microsoft.com](https://compliance.microsoft.com) e fare clic su **connettori dati** nel NAV sinistro.

2. Fare clic sulla scheda **connettori** e quindi selezionare il connettore **Symphony** per visualizzare la pagina del riquadro a comparsa, che contiene le proprietà e le informazioni sul connettore.

3. In **stato connettore con origine**fare clic sul collegamento **Scarica log** per aprire o salvare il registro di stato del connettore. Questo log contiene informazioni sui dati che sono stati importati nel cloud Microsoft.

## <a name="known-issues"></a>Problemi noti

- Al momento, non è supportato l'importazione di allegati di dimensioni superiori a 10 MB, ma il supporto per gli elementi di grandi dimensioni sarà disponibile in una data successiva.