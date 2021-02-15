---
title: Configurare un connettore per i dati di Webex Teams in Microsoft 365
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
description: Gli amministratori possono configurare un connettore per importare e archiviare i dati dal connettore Webex Teams di Globanet in Microsoft 365. Questo connettore consente di archiviare i dati da origini dati di terze parti in Microsoft 365, in modo da poter usare le funzionalità di conformità, ad esempio il blocco legale, la ricerca di contenuti e i criteri di conservazione per gestire i dati di terze parti dell'organizzazione.
ms.openlocfilehash: e116b02a53538f7eff4188b670fa6b42b873a9e9
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620222"
---
# <a name="set-up-a-connector-to-archive-webex-teams-data"></a>Configurare un connettore per archiviare i dati di Webex Teams

Usare un connettore Globanet nel Centro conformità Microsoft 365 per importare e archiviare i dati da Webex Teams alle cassette postali degli utenti nell'organizzazione di Microsoft 365. Globanet fornisce un [connettore Di Teams Webex](https://globanet.com/webex-teams/) configurato per acquisire elementi di comunicazione di Teams Webex e importarli in Microsoft 365. Il connettore converte il contenuto da Webex Teams, ad esempio chat 1:1, conversazioni di gruppo, conversazioni di canale e allegati dall'account Webex Teams dell'organizzazione, in un formato di messaggio di posta elettronica e quindi importa tali elementi nella cassetta postale dell'utente in Microsoft 365.

Dopo aver archiviato i dati di Webex Teams nelle cassette postali degli utenti, è possibile applicare le funzionalità di conformità di Microsoft 365, ad esempio il blocco per controversia legale, eDiscovery, i criteri di conservazione e le etichette di conservazione e la conformità delle comunicazioni. L'uso di un connettore di Teams Webex per importare e archiviare i dati in Microsoft 365 può aiutare l'organizzazione a rimanere conforme ai criteri normativi e governativi.

## <a name="overview-of-archiving-webex-teams-data"></a>Panoramica dell'archiviazione dei dati di Webex Teams

La panoramica seguente illustra il processo di utilizzo di un connettore per archiviare i dati di Teams Webex in Microsoft 365.

![Archiviazione del flusso di lavoro per i dati di Webex Teams](../media/WebexTeamsConnectorWorkflow.png)

1. L'organizzazione collabora con Webex Teams per configurare un sito di Teams Webex.

2. Una volta ogni 24 ore, gli elementi di Teams Webex vengono copiati nel sito Globanet Merge1. Il connettore converte inoltre gli elementi di Teams Webex in un formato di messaggio di posta elettronica.

3. Il connettore Di Teams Webex creato nel Centro conformità Microsoft 365, si connette a Globanet Merge1 ogni giorno e trasferisce gli elementi di Webex Teams in un percorso di archiviazione di Azure sicuro nel cloud Microsoft.

4. Il connettore importa gli elementi nelle cassette postali di utenti specifici utilizzando il valore della proprietà *Email* del mapping automatico degli utenti, come descritto [nel passaggio 3.](#step-3-map-users-and-complete-the-connector-setup) Nelle cassette postali degli utenti viene creata una sottocartella nella cartella Posta in arrivo denominata **Webex Teams** e gli elementi vengono importati in tale cartella. Il connettore esegue questa operazione utilizzando il valore della *proprietà Email.* Ogni elemento di Teams Webex contiene questa proprietà, che viene popolata con l'indirizzo di posta elettronica di ogni partecipante dell'elemento.

## <a name="before-you-begin"></a>Prima di iniziare

- Creare un account Globanet Merge1 per i connettori Microsoft. Per creare questo account, contattare [il supporto clienti Di Globanet.](https://globanet.com/ms-connectors-contact) Si accederà a questo account quando si crea il connettore nel passaggio 1.

- Creare un'applicazione in [https://developer.webex.com/](https://developer.webex.com) cui recuperare i dati dall'account di Teams Webex. Per istruzioni dettagliate sulla creazione dell'applicazione, vedere il Manuale dell'utente di [Merge1 Third-Party Connectors](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Webex%20Teams%20User%20Guide%20.pdf)

   Quando si crea questa applicazione, la piattaforma Webex genera un set di credenziali univoche. Queste credenziali vengono utilizzate nel passaggio 2 quando si configura il connettore di Teams Webex nel sito Di unione globale1.

- L'utente che crea il connettore di Teams Webex nel passaggio 1 (e lo completa nel passaggio 3) deve essere assegnato al ruolo di importazione/esportazione delle cassette postali in Exchange Online. Questo ruolo è necessario per aggiungere connettori nella pagina **Connettori** dati nel Centro conformità Microsoft 365. Per impostazione predefinita, questo ruolo non è assegnato a un gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo di importazione/esportazione delle cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online. In or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members. Per ulteriori informazioni, vedere le sezioni [Creazione](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) di gruppi di ruoli o Modifica gruppi [di](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) ruoli nell'articolo "Gestire i gruppi di ruoli in Exchange Online".

## <a name="step-1-set-up-the-webex-teams-connector"></a>Passaggio 1: Configurare il connettore Di Teams Webex

Il primo passaggio consiste nell'ottenere l'accesso ai connettori **dati** e configurare il [connettore di Teams Webex.](https://globanet.com/webex-teams/)

1. Passare a [https://compliance.microsoft.com](https://compliance.microsoft.com/) e quindi fare clic su **Connettori dati**  >  **Webex Teams.**

2. Nella pagina **di descrizione del prodotto Webex Teams** fare clic **su Aggiungi connettore.**

3. Nella pagina **Condizioni per il servizio** fare clic su **Accetta.**

4. Immettere un nome univoco che identifichi il connettore, quindi fare clic su **Avanti.**

5. Accedere all'account Merge1 per configurare il connettore.

## <a name="step-2-configure-the-webex-teams-connector-on-the-globanet-merge1-site"></a>Passaggio 2: Configurare il connettore Di Teams Webex nel sito Globanet Merge1

Il secondo passaggio consiste nel configurare il connettore di Teams Webex nel sito Merge1. Per informazioni su come configurare il connettore Di Teams Webex, vedere il Manuale dell'utente di [Merge1 Third-Party Connectors.](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Webex%20Teams%20User%20Guide%20.pdf)

Dopo aver fatto **clic su & fine,** viene visualizzata la pagina **Mapping** utenti nella procedura guidata del connettore nel Centro conformità Microsoft 365.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Passaggio 3: mappare gli utenti e completare la configurazione del connettore

Per mappare gli utenti e completare la configurazione del connettore nel Centro conformità Microsoft 365, attenersi alla seguente procedura:

1. Nella pagina Mappa utenti di Teams Webex agli utenti di **Microsoft 365** abilitare il mapping automatico degli utenti. Gli elementi di Teams Webex includono una proprietà denominata *Posta* elettronica, che contiene gli indirizzi di posta elettronica per gli utenti dell'organizzazione. Se il connettore può associare questo indirizzo a un utente di Microsoft 365, gli elementi vengono importati nella cassetta postale dell'utente.

2. Fare **clic** su Avanti, rivedere le  impostazioni e quindi passare alla pagina Connettori dati per visualizzare l'avanzamento del processo di importazione per il nuovo connettore.

## <a name="step-4-monitor-the-webex-teams-connector"></a>Passaggio 4: monitorare il connettore di Teams Webex

Dopo aver creato il connettore Di Teams Webex, è possibile visualizzare lo stato del connettore nel Centro conformità Microsoft 365.

1. Andare a [https://compliance.microsoft.com](https://compliance.microsoft.com) e fare clic su **Connettori dati** nel riquadro di spostamento sinistro.

2. Fare clic **sulla scheda Connettori** e quindi selezionare il **connettore Di Teams Webex** per visualizzare la pagina a comparsa. Questa pagina contiene le proprietà e le informazioni sul connettore.

3. In **Stato connettore con origine** fare clic sul collegamento Scarica **registro** per aprire (o salvare) il registro di stato per il connettore. Questo log contiene informazioni sui dati importati nel cloud Microsoft.

## <a name="known-issues"></a>Problemi noti

- Al momento, non è possibile importare allegati o elementi di dimensioni superiori a 10 MB. Il supporto per gli elementi più grandi sarà disponibile in un secondo momento.
