---
title: Configurare un connettore per i dati Teams Webex in Microsoft 365
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
description: Gli amministratori possono configurare un connettore per importare e archiviare i dati dal connettore webex Teams di Veritas in Microsoft 365. Questo connettore consente di archiviare i dati da origini dati di terze parti in Microsoft 365 in modo da poter utilizzare funzionalità di conformità come il blocco legale, la ricerca di contenuto e i criteri di conservazione per gestire i dati di terze parti dell'organizzazione.
ms.openlocfilehash: 654ca53fd4cd7c6091ff74360545ba335f753ffd
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163909"
---
# <a name="set-up-a-connector-to-archive-webex-teams-data"></a>Configurare un connettore per archiviare i dati Teams Webex

Utilizzare un connettore Veritas nel Centro conformità Microsoft 365 per importare e archiviare i dati da Webex Teams alle cassette postali degli utenti nell'Microsoft 365 organizzativa. Veritas fornisce un [connettore webex Teams](https://globanet.com/webex-teams/) configurato per acquisire elementi di comunicazione Webex Teams e importarli in Microsoft 365. Il connettore converte il contenuto da Webex Teams, ad esempio chat 1:1, conversazioni di gruppo, conversazioni di canale e allegati dall'account Webex Teams dell'organizzazione, in un formato di messaggio di posta elettronica e quindi importa tali elementi nella cassetta postale dell'utente in Microsoft 365.

Dopo l'archiviazione dei Teams Webex nelle cassette postali degli utenti, è possibile applicare funzionalità di conformità Microsoft 365 quali conservazione per controversia legale, eDiscovery, criteri di conservazione ed etichette di conservazione e conformità delle comunicazioni. L'utilizzo di un connettore Teams Webex per importare e archiviare i dati in Microsoft 365 può aiutare l'organizzazione a rimanere conforme ai criteri governativi e normativi.

## <a name="overview-of-archiving-webex-teams-data"></a>Panoramica dell'archiviazione dei dati webex Teams

Nella panoramica seguente viene illustrato il processo di utilizzo di un connettore per archiviare webex Teams dati in Microsoft 365.

![Flusso di lavoro di archiviazione per i dati Teams Webex](../media/WebexTeamsConnectorWorkflow.png)

1. L'organizzazione collabora con Webex Teams per configurare un sito Webex Teams web.

2. Una volta ogni 24 ore, gli Teams Webex vengono copiati nel sito Veritas Merge1. Il connettore converte inoltre gli elementi webex Teams in un formato di messaggio di posta elettronica.

3. Il connettore di Teams Webex creato nel Centro conformità Microsoft 365, si connette ogni giorno a Veritas Merge1 e trasferisce gli elementi webex Teams in una posizione Archiviazione di Azure sicura nel cloud Microsoft.

4. Il connettore importa gli elementi nelle cassette postali di utenti specifici utilizzando il valore della proprietà *Email* del mapping automatico degli utenti, come descritto [nel passaggio 3.](#step-3-map-users-and-complete-the-connector-setup) Nelle cassette postali degli utenti viene creata una sottocartella nella cartella Posta in arrivo denominata **Webex Teams** e gli elementi vengono importati in tale cartella. Il connettore esegue questa operazione utilizzando il valore della *proprietà Email.* Ogni elemento webex Teams contiene questa proprietà, che viene popolata con l'indirizzo di posta elettronica di ogni partecipante dell'elemento.

## <a name="before-you-begin"></a>Prima di iniziare

- Creare un account Veritas Merge1 per i connettori Microsoft. Per creare questo account, contattare il [supporto tecnico Veritas.](https://globanet.com/ms-connectors-contact) Si accederà a questo account quando si crea il connettore nel passaggio 1.

- Creare un'applicazione in [https://developer.webex.com/](https://developer.webex.com) per recuperare i dati dall'account webex Teams. Per istruzioni dettagliate sulla creazione dell'applicazione, vedere [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Webex%20Teams%20User%20Guide%20.pdf)

   Quando si crea questa applicazione, la piattaforma Webex genera un set di credenziali univoche. Queste credenziali vengono utilizzate nel passaggio 2 quando si configura il connettore di Teams Webex nel sito Merge1 globale.

- L'utente che crea il connettore di Teams Webex nel passaggio 1 (e lo completa nel passaggio 3) deve essere assegnato al ruolo Esportazione importazione cassette postali in Exchange Online. Questo ruolo è necessario per aggiungere connettori nella pagina **Connettori** dati nel Centro Microsoft 365 conformità. Per impostazione predefinita, questo ruolo non viene assegnato a un gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo Esportazione importazione cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online. In caso contrario, è possibile creare un gruppo di ruoli, assegnare il ruolo Importazione/Esportazione cassette postali e quindi aggiungere gli utenti appropriati come membri. Per ulteriori informazioni, vedere le sezioni [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) o Modify role [groups](/Exchange/permissions-exo/role-groups#modify-role-groups) nell'articolo "Manage role groups in Exchange Online".

## <a name="step-1-set-up-the-webex-teams-connector"></a>Passaggio 1: Configurare il connettore di Teams Webex

Il primo passaggio consiste nell'ottenere l'accesso ai **connettori** dati e nella configurazione del connettore di Teams [Webex.](https://globanet.com/webex-teams/)

1. Passare a [https://compliance.microsoft.com](https://compliance.microsoft.com/) e quindi fare clic su **Connettori dati**  >  **Webex Teams**.

2. Nella pagina **Webex Teams** descrizione del prodotto fare clic **su Aggiungi connettore**.

3. Nella pagina **Condizioni di servizio** fare clic su **Accetta.**

4. Immettere un nome univoco che identifichi il connettore e quindi fare clic su **Avanti.**

5. Accedere all'account Merge1 per configurare il connettore.

## <a name="step-2-configure-the-webex-teams-connector-on-the-veritas-merge1-site"></a>Passaggio 2: Configurare il connettore di Teams Webex nel sito Veritas Merge1

Il secondo passaggio consiste nel configurare il connettore di Teams Webex nel sito Merge1. Per informazioni su come configurare il connettore di Teams Webex, vedere [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Webex%20Teams%20User%20Guide%20.pdf).

Dopo aver fatto **clic su Salva & fine,** viene visualizzata la pagina **Mapping** utenti nella procedura guidata del connettore nel Centro Microsoft 365 conformità.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Passaggio 3: mappare gli utenti e completare la configurazione del connettore

Per mappare gli utenti e completare la configurazione del connettore nel Centro Microsoft 365 conformità, attenersi alla seguente procedura:

1. Nella pagina **Mapping utenti webex Teams** utenti Microsoft 365 utenti, abilitare il mapping automatico degli utenti. Gli elementi webex Teams includono una proprietà denominata *Email*, che contiene gli indirizzi di posta elettronica per gli utenti dell'organizzazione. Se il connettore può associare questo indirizzo a un Microsoft 365 utente, gli elementi vengono importati nella cassetta postale dell'utente.

2. Fare **clic** su Avanti, rivedere le impostazioni e quindi passare alla pagina **Connettori** dati per visualizzare l'avanzamento del processo di importazione per il nuovo connettore.

## <a name="step-4-monitor-the-webex-teams-connector"></a>Passaggio 4: Monitorare il connettore di Teams Webex

Dopo aver creato il connettore di Teams Webex, è possibile visualizzare lo stato del connettore nel Centro Microsoft 365 conformità.

1. Vai a [https://compliance.microsoft.com](https://compliance.microsoft.com) e fai clic su **Connettori dati** nel riquadro di spostamento sinistro.

2. Fare clic **sulla scheda Connettori** e quindi selezionare il Teams **Webex** per visualizzare la pagina a comparsa. Questa pagina contiene le proprietà e le informazioni sul connettore.

3. In **Stato connettore con origine** fare clic sul collegamento Scarica **registro** per aprire (o salvare) il registro di stato per il connettore. Questo registro contiene informazioni sui dati importati nel cloud Microsoft.

## <a name="known-issues"></a>Problemi noti

- Al momento non è possibile importare allegati o elementi di dimensioni superiori a 10 MB. Il supporto per gli elementi più grandi sarà disponibile in un secondo momento.