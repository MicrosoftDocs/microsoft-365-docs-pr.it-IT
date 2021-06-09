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
description: Gli amministratori possono configurare un connettore per importare e archiviare i dati da Veritas Zoom Meetings in Microsoft 365. In questo modo è possibile archiviare i dati da origini dati di terze parti in Microsoft 365 in modo da poter utilizzare funzionalità di conformità come il blocco legale, la ricerca di contenuto e i criteri di conservazione per gestire i dati di terze parti dell'organizzazione.
ms.openlocfilehash: b67098f3ddb1149927f4b82270c8fa4f14bbe558
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163730"
---
# <a name="set-up-a-connector-to-archive-zoom-meetings-data"></a>Configurare un connettore per archiviare i dati delle riunioni zoom

Utilizzare un connettore Veritas nel centro Microsoft 365 conformità per importare e archiviare i dati dalle riunioni zoom alle cassette postali degli utenti nell'Microsoft 365 organizzativa. Veritas fornisce un [connettore riunioni zoom](https://globanet.com/zoom/) configurato per acquisire elementi dall'origine dati di terze parti (a intervalli regolari) e importare tali elementi in Microsoft 365. Il connettore converte il contenuto delle riunioni (incluse chat, file registrati e metadati) dall'account Zoom riunioni in un formato di messaggio di posta elettronica e quindi importa tali elementi nelle cassette postali degli utenti in Microsoft 365.

Dopo aver archiviato i dati delle riunioni zoom nelle cassette postali degli utenti, è possibile applicare funzionalità di conformità Microsoft 365 quali conservazione per controversia legale, eDiscovery, criteri di conservazione ed etichette di conservazione e conformità delle comunicazioni. L'utilizzo di un connettore riunioni zoom per importare e archiviare i dati in Microsoft 365 può aiutare l'organizzazione a rimanere conforme ai criteri governativi e normativi.

## <a name="overview-of-archiving-zoom-meetings-data"></a>Panoramica dell'archiviazione dei dati delle riunioni zoom

Nella panoramica seguente viene illustrato il processo di utilizzo di un connettore per archiviare i dati delle riunioni zoom in Microsoft 365.

![Flusso di lavoro per l'archiviazione delle riunioni zoom](../media/ZoomMeetingsConnectorWorkflow.png)

1. L'organizzazione collabora con le riunioni zoom per configurare e configurare un sito Riunioni zoom.

2. Una volta ogni 24 ore, gli elementi delle riunioni di Zoom Riunioni vengono copiati nel sito Veritas Merge1. Il connettore converte anche il contenuto delle riunioni in un formato di messaggio di posta elettronica.

3. Il connettore Riunioni zoom creato nel Centro conformità Microsoft 365, si connette ogni giorno a Veritas Merge1 e trasferisce i messaggi di riunione in una posizione Archiviazione di Azure sicura nel cloud Microsoft.

4. Il connettore importa gli elementi delle riunioni convertite nelle cassette postali di utenti specifici utilizzando il valore della proprietà *Email* e il mapping automatico degli utenti, come descritto nel passaggio 3. Nelle cassette postali degli utenti viene creata una nuova sottocartella nella cartella Posta in arrivo denominata **Zoom Riunioni** e gli elementi delle riunioni vengono importati in tale cartella. Il connettore esegue questa operazione utilizzando il valore della *proprietà Email.* Ogni elemento della riunione contiene questa proprietà, che viene popolata con l'indirizzo di posta elettronica di ogni partecipante alla riunione.

## <a name="before-you-begin"></a>Prima di iniziare

- Creare un account Veritas Merge1 per i connettori Microsoft. Per creare questo account, contattare il [supporto tecnico Veritas.](https://globanet.com/ms-connectors-contact) Si accederà a questo account quando si crea il connettore nel passaggio 1.

- Ottenere il nome utente e la password per l'account Zoom Business o Zoom Enterprise'organizzazione. È necessario accedere a questo account nel passaggio 2 quando si configura il connettore zoom riunioni.

- Creare le applicazioni seguenti in [Zoom Marketplace:](https://marketplace.zoom.us)

  - Applicazione OAuth

  - Applicazione JWT

  Dopo aver creato queste applicazioni, la piattaforma Zoom genera un set di credenziali univoche utilizzate per generare i token. Questi token vengono usati per autenticare il connettore quando si connette all'account Zoom e copia gli elementi nel sito Merge1. Questi token verranno utilizzati quando si configura il connettore zoom nel passaggio 2.

  Per istruzioni dettagliate su come creare le applicazioni OAuth e JWT, vedere [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Zoom%20Meetings%20User%20Guide%20.pdf).

- L'utente che crea il connettore zoom riunioni nel passaggio 1 (e lo completa nel passaggio 3) deve essere assegnato al ruolo Esportazione importazione cassette postali in Exchange Online. Questo ruolo è necessario per aggiungere connettori nella pagina **Connettori** dati nel Centro Microsoft 365 conformità. Per impostazione predefinita, questo ruolo non viene assegnato a un gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo Esportazione importazione cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online. In caso contrario, è possibile creare un gruppo di ruoli, assegnare il ruolo Importazione/Esportazione cassette postali e quindi aggiungere gli utenti appropriati come membri. Per ulteriori informazioni, vedere le sezioni [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) o Modify role [groups](/Exchange/permissions-exo/role-groups#modify-role-groups) nell'articolo "Manage role groups in Exchange Online".

## <a name="step-1-set-up-the-zoom-meetings-connector"></a>Passaggio 1: Configurare il connettore zoom riunioni

Il primo passaggio consiste  nell'accedere ai connettori di dati nel centro Microsoft 365 conformità e creare un connettore riunioni zoom.

1. Passare a [https://compliance.microsoft.com](https://compliance.microsoft.com/) e quindi fare clic su **Connettori dati** Zoom  >  **riunioni**.

2. Nella pagina **Descrizione del prodotto Zoom riunioni** fare clic su Aggiungi **connettore.**

3. Nella pagina **Condizioni di servizio** fare clic su **Accetta.**

4. Immettere un nome univoco che identifichi il connettore e quindi fare clic su **Avanti.**

5. Accedere all'account Merge1 per configurare il connettore.

## <a name="step-2-configure-the-zoom-meetings-connector"></a>Passaggio 2: Configurare il connettore zoom riunioni

Il secondo passaggio consiste nel configurare il connettore Zoom riunioni nel sito Merge1. Per ulteriori informazioni su come configurare il connettore zoom riunioni nel sito Veritas Merge1, vedere [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Zoom%20Meetings%20User%20Guide%20.pdf).

Dopo aver fatto **clic su Salva & fine,** viene visualizzata la pagina **Mapping** utenti nella procedura guidata del connettore nel Centro Microsoft 365 conformità.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Passaggio 3: mappare gli utenti e completare la configurazione del connettore

1. Nella pagina **Mapping utenti esterni a Microsoft 365** utenti, abilitare il mapping automatico degli utenti.

   Gli elementi zoom riunioni includono una proprietà denominata *Posta* elettronica che contiene gli indirizzi di posta elettronica per gli utenti dell'organizzazione. Se il connettore può associare questo indirizzo a un Microsoft 365 utente, gli elementi vengono importati nella cassetta postale dell'utente

2. Fare **clic** su Avanti, rivedere le impostazioni e passare alla pagina **Connettori** dati per visualizzare l'avanzamento del processo di importazione per il nuovo connettore.

## <a name="step-4-monitor-the-zoom-meetings-connector"></a>Passaggio 4: Monitorare il connettore zoom riunioni

Dopo aver creato il connettore Riunioni zoom, è possibile visualizzare lo stato del connettore nel Centro Microsoft 365 conformità.

1. Vai a [https://compliance.microsoft.com](https://compliance.microsoft.com) e fai clic su **Connettori dati** nel riquadro di spostamento sinistro.

2. Fare clic **sulla scheda Connettori** e quindi selezionare il **connettore Zoom riunioni** per visualizzare la pagina a comparsa. Questa pagina contiene le proprietà e le informazioni sul connettore.

3. In **Stato connettore con origine** fare clic sul collegamento Scarica **registro** per aprire (o salvare) il registro di stato per il connettore. Questo registro contiene informazioni sui dati importati nel cloud Microsoft.

## <a name="known-issues"></a>Problemi noti

- Al momento non è possibile importare allegati o elementi di dimensioni superiori a 10 MB. Il supporto per gli elementi più grandi sarà disponibile in un secondo momento.

- Per il funzionamento del connettore Riunioni zoom, è necessario abilitare le registrazioni durante la configurazione delle riunioni zoom.