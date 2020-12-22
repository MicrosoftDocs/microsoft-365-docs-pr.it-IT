---
title: Configurare un connettore per l'archiviazione Redtail parlare di dati in Microsoft 365
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
description: Gli amministratori possono configurare un connettore per l'importazione e l'archiviazione dei dati di Redtail Speak da Globanet a Microsoft 365. Questo connettore consente di archiviare i dati provenienti da origini dati di terze parti in Microsoft 365. Dopo l'archiviazione dei dati, è possibile utilizzare le funzionalità di conformità, ad esempio la conservazione legale, la ricerca del contenuto e i criteri di ritenzione per gestire i dati di terze parti.
ms.openlocfilehash: 546298288e69746856a1250cc4b87643dd479c91
ms.sourcegitcommit: a3215cc22faa47e935d22300c481e47ab2680b44
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/21/2020
ms.locfileid: "49723009"
---
# <a name="set-up-a-connector-to-archive-redtail-speak-data-preview"></a>Configurare un connettore per l'archiviazione dei dati di Redtail Speak (anteprima)

Utilizzare un connettore di Globanet nel centro conformità di Microsoft 365 per importare e archiviare i dati da Redtail parlare con le cassette postali degli utenti nell'organizzazione Microsoft 365. Globanet fornisce un connettore [Redtail Speak](https://globanet.com/redtail/) configurato per acquisire elementi dal server SFTP dell'organizzazione in cui gli elementi vengono ricevuti da Redtail. Il connettore converte il contenuto da Redtail parlare con un formato di messaggio di posta elettronica e quindi importa tali elementi nella cassetta postale dell'utente in Microsoft 365.

Dopo che i dati di Redtail Speak sono archiviati nelle cassette postali degli utenti, è possibile applicare le funzionalità di conformità di Microsoft 365 come il blocco per controversia legale, eDiscovery, i criteri di conservazione e etichette di conservazione. L'utilizzo di un connettore Speak di Redtail per l'importazione e l'archiviazione dei dati in Microsoft 365 può aiutare l'organizzazione a rimanere conforme ai criteri governativi e normativi.

## <a name="overview-of-archiving-the-redtail-speak-data"></a>Panoramica dell'archiviazione dei dati di Redtail Speak

Nella panoramica seguente viene illustrato il processo di utilizzo di un connettore per archiviare i dati di Redtail speak in Microsoft 365.

![Flusso di lavoro di archiviazione per Redtail Speak data](../media/RedtailSpeakConnectorWorkflow.png)

1. L'organizzazione collabora con Redtail parlare per impostare e configurare un gateway SMTP in cui i messaggi giornalieri vengono inoltrati da Redtail parlare con il server SFTP organizzazioni.

2. Una volta ogni 24 ore, gli elementi di Redtail Speak vengono copiati nel sito Globanet Merge1. Il connettore converte anche gli elementi speak di Redtail in un formato di messaggio di posta elettronica.

3. Il connettore Redtail Speak creato nel centro conformità di Microsoft 365 si connette al sito di Merge1 di Globanet ogni giorno e trasferisce i messaggi a una posizione di archiviazione sicura di Azure nel cloud Microsoft.

4. Il connettore importa gli elementi di Redtail convertiti parla alle cassette postali di utenti specifici utilizzando il valore della proprietà di *posta elettronica* del mapping automatico degli utenti, come descritto nel [passaggio 3](#step-3-map-users-and-complete-the-connector-setup). Viene creata una sottocartella nella cartella posta in arrivo denominata **Redtail Speak** nelle cassette postali degli utenti e gli elementi vengono importati in tale cartella. Il connettore determina la cassetta postale a cui importare gli elementi utilizzando il valore della proprietà di *posta elettronica* . Ogni elemento di Redtail Speak contiene questa proprietà, che viene popolata con l'indirizzo di posta elettronica di tutti i partecipanti all'elemento.

## <a name="before-you-begin"></a>Prima di iniziare

- Creare un account Merge1 di Globanet per i connettori Microsoft. Per creare un account, contattare il [supporto clienti di Globanet](https://globanet.com/contact-us/). È necessario accedere a questo account quando si crea il connettore nel passaggio 1.

- In STEP you, è necessario specificare il server SFTP dell'organizzazione. Ciò è necessario affinché Globanet Merge1 possa contattarlo per raccogliere i dati di Redtail Speak tramite SFTP.

- L'utente che crea il connettore dell'utilità di importazione di Redtail Speak nel passaggio 1 (e lo completa nel passaggio 3) deve essere assegnato al ruolo di esportazione delle cassette postali in Exchange Online. Questo ruolo è necessario per aggiungere connettori nella pagina dei connettori dati nel centro conformità di Microsoft 365. Per impostazione predefinita, questo ruolo non è assegnato a nessun gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo import export delle cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online. In alternativa, è possibile creare un gruppo di ruoli, assegnare il ruolo di esportazione delle cassette postali e quindi aggiungere gli utenti corretti come membri. Per ulteriori informazioni, vedere la sezione creare gruppi di [ruoli](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) o [modificare gruppi di ruoli](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) nell'articolo "gestire i gruppi di ruoli in Exchange Online".

## <a name="step-1-set-up-the-redtail-speak-connector"></a>Passaggio 1: configurare il connettore Speak di Redtail

Il primo passaggio consiste nell'accedere alla pagina **dei connettori dati** nel centro conformità di Microsoft 365 e creare un connettore per i dati di Redtail Speak.

1. Andare a [https://compliance.microsoft.com](https://compliance.microsoft.com/) e fare clic su **connettori dati** &gt; **Redtail Speak**.

2. Nella pagina Descrizione prodotto di **Redtail** , fare clic su **Aggiungi nuovo connettore**.

3. Nella pagina **condizioni del servizio** fare clic su **Accetto**.

4. Immettere un nome univoco che identifichi il connettore e quindi fare clic su **Avanti**.

5. Accedere al proprio account di Merge1 per configurare il connettore.

## <a name="step-2-configure-the-redtail-speak-connector-on-the-globanet-merge1-site"></a>Passaggio 2: configurare il connettore Speak di Redtail nel sito di Merge1 Globanet

Il secondo passaggio consiste nel configurare il connettore Speak di Redtail nel sito di Merge1. Per informazioni su come configurare il connettore di Redtail Speak, vedere [Merge1 Third-Party Connectors user guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Redtail%20Speak%20User%20Guide%20.pdf).

Dopo aver fatto clic su **salva & fine**, viene visualizzata la pagina di **mapping degli utenti** nella procedura guidata del connettore nel centro conformità di Microsoft 365.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Passaggio 3: mappare gli utenti e completare la configurazione del connettore

Per eseguire il mapping degli utenti e completare la configurazione del connettore, eseguire la procedura seguente:

1. Nella pagina **mappa Redtail Speak users to Microsoft 365** Users, abilitare il mapping automatico degli utenti. Gli elementi di Redtail Speak includono una proprietà denominata *posta elettronica*, che contiene gli indirizzi di posta elettronica per gli utenti dell'organizzazione. Se il connettore può associare questo indirizzo a un utente di Microsoft 365, gli elementi vengono importati nella cassetta postale dell'utente.

2. Fare clic su **Avanti**, rivedere le impostazioni e passare alla pagina **connettori dati** per visualizzare lo stato di avanzamento del processo di importazione per il nuovo connettore.

## <a name="step-4-monitor-the-redtail-speak-connector"></a>Passaggio 4: monitorare il connettore Speak di Redtail

Dopo aver creato il connettore Redtail Speak, è possibile visualizzare lo stato del connettore nel centro conformità di Microsoft 365.

1. Andare a [https://compliance.microsoft.com](https://compliance.microsoft.com/) e fare clic su **connettori dati** nel NAV sinistro.

2. Fare clic sulla scheda **connettori** e quindi selezionare il connettore **Redtail Speak** per visualizzare la pagina del riquadro a comparsa. In questa pagina vengono visualizzate le proprietà e le informazioni sul connettore.

3. In **stato connettore con origine** fare clic sul collegamento **Scarica log** per aprire o salvare il registro di stato del connettore. Questo log contiene dati che sono stati importati nel cloud Microsoft.

## <a name="known-issues"></a>Problemi noti

- Al momento, non è supportato l'importazione di allegati o elementi di dimensioni superiori a 10 MB. Il supporto per gli elementi di grandi dimensioni sarà disponibile in un secondo momento.
