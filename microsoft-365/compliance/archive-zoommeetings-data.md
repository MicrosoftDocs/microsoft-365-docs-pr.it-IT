---
title: Configurare un connettore per archiviare i dati delle riunioni zoom in Microsoft 365
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
description: Gli amministratori possono configurare un connettore per importare e archiviare i dati dalle riunioni zoom di Globanet in Microsoft 365. In questo modo è possibile archiviare i dati da origini dati di terze parti in Microsoft 365, in modo da poter usare le funzionalità di conformità, ad esempio il blocco legale, la ricerca di contenuti e i criteri di conservazione per gestire i dati di terze parti dell'organizzazione.
ms.openlocfilehash: c61c9a40d85b3bea266df9b1f2dba32301e54e08
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620202"
---
# <a name="set-up-a-connector-to-archive-zoom-meetings-data"></a>Configurare un connettore per archiviare i dati delle riunioni zoom

Usare un connettore Globanet nel Centro conformità Microsoft 365 per importare e archiviare i dati da Zoom Riunioni alle cassette postali degli utenti nell'organizzazione di Microsoft 365. Globanet fornisce un [connettore Zoom Meetings](https://globanet.com/zoom/) configurato per acquisire elementi dall'origine dati di terze parti (regolarmente) e importare tali elementi in Microsoft 365. Il connettore converte il contenuto delle riunioni (incluse chat, file registrati e metadati) dall'account Zoom riunioni in un formato di messaggio di posta elettronica e quindi importa tali elementi nelle cassette postali degli utenti in Microsoft 365.

Dopo aver archiviato i dati delle riunioni zoom nelle cassette postali degli utenti, è possibile applicare le funzionalità di conformità di Microsoft 365, ad esempio il blocco per controversia legale, eDiscovery, i criteri di conservazione e le etichette di conservazione e la conformità delle comunicazioni. L'uso di un connettore zoom riunioni per importare e archiviare i dati in Microsoft 365 può aiutare l'organizzazione a rimanere conforme ai criteri normativi e governativi.

## <a name="overview-of-archiving-zoom-meetings-data"></a>Panoramica dell'archiviazione dei dati delle riunioni zoom

Nella seguente panoramica viene illustrato il processo di utilizzo di un connettore per archiviare i dati delle riunioni zoom in Microsoft 365.

![Flusso di lavoro di archiviazione delle riunioni zoom](../media/ZoomMeetingsConnectorWorkflow.png)

1. L'organizzazione collabora con zoom riunioni per configurare un sito Zoom riunioni.

2. Una volta ogni 24 ore, gli elementi delle riunioni da Zoom Riunioni vengono copiati nel sito Globanet Merge1. Il connettore converte inoltre il contenuto delle riunioni in un formato di messaggio di posta elettronica.

3. Il connettore zoom riunioni creato nel Centro conformità Microsoft 365, si connette a Globanet Merge1 ogni giorno e trasferisce i messaggi delle riunioni in una posizione sicura di Archiviazione di Azure nel cloud Microsoft.

4. Il connettore importa le riunioni convertite nelle cassette postali di utenti specifici utilizzando il valore della proprietà *Email* e il mapping automatico degli utenti, come descritto nel passaggio 3. Nelle cassette postali degli utenti viene creata una nuova sottocartella nella cartella Posta in arrivo denominata **Zoom Riunioni** e gli elementi delle riunioni vengono importati in tale cartella. Il connettore esegue questa operazione utilizzando il valore della *proprietà Email.* Ogni elemento della riunione contiene questa proprietà, che viene popolata con l'indirizzo di posta elettronica di ogni partecipante alla riunione.

## <a name="before-you-begin"></a>Prima di iniziare

- Creare un account Globanet Merge1 per i connettori Microsoft. Per creare questo account, contattare [il supporto clienti Di Globanet.](https://globanet.com/ms-connectors-contact) Si accederà a questo account quando si crea il connettore nel passaggio 1.

- Ottenere il nome utente e la password per l'account Zoom Business o Zoom Enterprise dell'organizzazione. Sarà necessario accedere a questo account nel passaggio 2 quando si configura il connettore Zoom riunioni.

- Creare le applicazioni seguenti in [Zoom Marketplace:](https://marketplace.zoom.us)

  - Applicazione OAuth

  - Applicazione JWT

  Dopo aver creato queste applicazioni, la piattaforma Zoom genera un set di credenziali univoche usate per generare i token. Questi token vengono utilizzati per autenticare il connettore quando si connette all'account Zoom e copia gli elementi nel sito Merge1. Questi token verranno utilizzati quando si configura il connettore zoom nel passaggio 2.

  Per istruzioni dettagliate su come creare le applicazioni OAuth e JWT, vedere il Manuale dell'utente di [Merge1 Third-Party Connectors.](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Zoom%20Meetings%20User%20Guide%20.pdf)

- L'utente che crea il connettore zoom riunioni nel passaggio 1 (e lo completa nel passaggio 3) deve essere assegnato al ruolo di importazione/esportazione delle cassette postali in Exchange Online. Questo ruolo è necessario per aggiungere connettori nella pagina **Connettori** dati nel Centro conformità Microsoft 365. Per impostazione predefinita, questo ruolo non è assegnato a un gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo di importazione/esportazione delle cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online. In or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members. Per ulteriori informazioni, vedere le sezioni [Creazione](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) di gruppi di ruoli o Modifica gruppi [di](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) ruoli nell'articolo "Gestire i gruppi di ruoli in Exchange Online".

## <a name="step-1-set-up-the-zoom-meetings-connector"></a>Passaggio 1: Configurare il connettore zoom riunioni

Il primo passaggio consiste nell'accedere ai **connettori** dati nel Centro conformità Microsoft 365 e creare un connettore Zoom riunioni.

1. Accedere a [https://compliance.microsoft.com](https://compliance.microsoft.com/) e quindi fare clic su **Connettori dati** Zoom  >  **Riunioni.**

2. Nella pagina **di descrizione del** prodotto Zoom riunioni fare clic su **Aggiungi connettore.**

3. Nella pagina **Condizioni per il servizio** fare clic su **Accetta.**

4. Immettere un nome univoco che identifichi il connettore, quindi fare clic su **Avanti.**

5. Accedere all'account Merge1 per configurare il connettore.

## <a name="step-2-configure-the-zoom-meetings-connector"></a>Passaggio 2: Configurare il connettore Zoom riunioni

Il secondo passaggio consiste nel configurare il connettore Zoom riunioni nel sito Merge1. Per ulteriori informazioni su come configurare il connettore zoom riunioni nel sito Globanet Merge1, vedere il Manuale dell'utente di [Merge1 Third-Party Connectors.](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Zoom%20Meetings%20User%20Guide%20.pdf)

Dopo aver fatto **clic su & fine,** viene visualizzata la pagina **Mapping** utenti nella procedura guidata del connettore nel Centro conformità Microsoft 365.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Passaggio 3: mappare gli utenti e completare la configurazione del connettore

1. Nella pagina **Mapping utenti esterni a utenti di Microsoft 365** abilitare il mapping automatico degli utenti.

   Gli elementi zoom riunioni includono una proprietà denominata *Posta* elettronica che contiene gli indirizzi di posta elettronica per gli utenti dell'organizzazione. Se il connettore può associare questo indirizzo a un utente di Microsoft 365, gli elementi vengono importati nella cassetta postale dell'utente

2. Fare **clic** su Avanti, rivedere le impostazioni e passare alla pagina **Connettori** dati per visualizzare l'avanzamento del processo di importazione per il nuovo connettore.

## <a name="step-4-monitor-the-zoom-meetings-connector"></a>Passaggio 4: Monitorare il connettore zoom riunioni

Dopo aver creato il connettore Zoom Riunioni, è possibile visualizzare lo stato del connettore nel Centro conformità Microsoft 365.

1. Andare a [https://compliance.microsoft.com](https://compliance.microsoft.com) e fare clic su **Connettori dati** nel riquadro di spostamento sinistro.

2. Fare clic **sulla scheda Connettori** e quindi selezionare il **connettore Zoom riunioni** per visualizzare la pagina a comparsa. Questa pagina contiene le proprietà e le informazioni sul connettore.

3. In **Stato connettore con origine** fare clic sul collegamento Scarica **registro** per aprire (o salvare) il registro di stato per il connettore. Questo log contiene informazioni sui dati importati nel cloud Microsoft.

## <a name="known-issues"></a>Problemi noti

- Al momento, non è possibile importare allegati o elementi di dimensioni superiori a 10 MB. Il supporto per gli elementi più grandi sarà disponibile in un secondo momento.

- Per il funzionamento del connettore Zoom riunioni, è necessario abilitare le registrazioni durante la configurazione di Zoom riunioni.
