---
title: Configurare un connettore per archiviare Cisco Jabber sui dati SQL ms in Microsoft 365
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
description: Gli amministratori possono configurare un connettore per importare e archiviare i dati di Cisco Jabber da Globanet in Microsoft 365. Questo connettore consente di archiviare i dati da origini dati di terze parti in Microsoft 365. Dopo l'archiviazione di questi dati, è possibile utilizzare funzionalità di conformità come la conservazione a livello legale, la ricerca di contenuto e i criteri di conservazione per gestire i dati di terze parti.
ms.openlocfilehash: 2790a29cdfa090372976d78de2e5cc5e5c5ce12e
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620042"
---
# <a name="set-up-a-connector-to-archive-cisco-jabber-data"></a>Configurare un connettore per archiviare i dati di Cisco Jabber

Usare un connettore Globanet nel Centro conformità Microsoft 365 per importare e archiviare i dati dalla piattaforma Cisco Jabber alle cassette postali degli utenti nell'organizzazione di Microsoft 365. Globanet fornisce un connettore [Cisco Jabber](https://globanet.com/jabber/) configurato per acquisire elementi dal database MS SQL di Jabber, ad esempio messaggi di chat 1:1 e chat di gruppo e quindi importare tali elementi in Microsoft 365. Il connettore recupera i dati dal database MS SQL di Cisco Jabber, lo elabora e converte il contenuto dall'account Cisco Jabber di un utente in un formato di messaggio di posta elettronica e quindi importa tali elementi nella cassetta postale dell'utente in Microsoft 365.

Dopo aver archiviato i dati di Cisco Jabber nelle cassette postali degli utenti, è possibile applicare le funzionalità di conformità di Microsoft 365, ad esempio il blocco per controversia legale, eDiscovery, i criteri di conservazione e le etichette di conservazione e la conformità delle comunicazioni. L'uso di un connettore Cisco Jabber per importare e archiviare i dati in Microsoft 365 può aiutare l'organizzazione a rimanere conforme ai criteri normativi e governativi.

## <a name="overview-of-archiving-cisco-jabber-data"></a>Panoramica dell'archiviazione dei dati Cisco Jabber

Nella seguente panoramica viene illustrato il processo di utilizzo di un connettore per archiviare i dati di Cisco Jabber in Microsoft 365.

![Flusso di lavoro di archiviazione per i dati Cisco Jabber](../media/CiscoJabberonMSSQLConnectorWorkflow.png)

1. L'organizzazione collabora con Cisco per configurare un Cisco Jabber in MS SQL Database.

2. Una volta ogni 24 ore, gli elementi di Cisco Jabber vengono copiati dal database ms SQL nel sito Globanet Merge1. Il connettore converte inoltre il contenuto dei messaggi di chat in un formato di messaggio di posta elettronica.

3. Il connettore Cisco Jabber creato nel Centro conformità Microsoft 365 si connette ogni giorno al sito Globanet Merge1 e trasferisce gli elementi in una posizione sicura di Archiviazione di Azure nel cloud Microsoft.

4. Il mapping automatico degli utenti come connettore importa gli elementi nelle cassette postali di utenti specifici utilizzando il valore della proprietà *Email* del descritto [nel passaggio 3.](#step-3-map-users-and-complete-the-connector-setup) Nelle cassette postali degli utenti viene creata una sottocartella nella cartella Posta in arrivo denominata **Cisco Jabber su MS SQL** e gli elementi del messaggio vengono importati in tale cartella. Il connettore determina in quale cassetta postale importare gli elementi utilizzando il valore della proprietà *Email.* Ogni elemento Cisco Jabber contiene questa proprietà, che viene popolata con l'indirizzo di posta elettronica di ogni partecipante.

## <a name="before-you-begin"></a>Prima di iniziare

- Creare un account Globanet Merge1 per i connettori Microsoft. Per creare questo account, contattare [il supporto clienti Di Globanet.](https://globanet.com/ms-connectors-contact/) Si accederà a questo account quando si crea il connettore nel passaggio 1.

- Configurare un database ms SQL per recuperare gli elementi jabber prima di creare il connettore nel passaggio 1. Durante la configurazione del connettore Cisco Jabber nel passaggio 2 verranno specificate le impostazioni di connessione per il database MS SQL. Per ulteriori informazioni, vedere il Manuale dell'utente di [Merge1 Third-Party Connectors.](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20MS%20SQL%20User%20Guide%20.pdf)

- L'utente che crea il connettore Cisco Jabber nel passaggio 1 (e lo completa nel passaggio 3) deve essere assegnato al ruolo di importazione/esportazione delle cassette postali in Exchange Online. Questo ruolo è necessario per aggiungere connettori nella pagina **Connettori** dati nel Centro conformità Microsoft 365. Per impostazione predefinita, questo ruolo non è assegnato a un gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo di importazione/esportazione delle cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online. In or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members. Per ulteriori informazioni, vedere le sezioni [Creazione](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) di gruppi di ruoli o Modifica gruppi [di](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) ruoli nell'articolo "Gestire i gruppi di ruoli in Exchange Online".

## <a name="step-1-set-up-the-cisco-jabber-connector"></a>Passaggio 1: Configurare il connettore Cisco Jabber

Il primo passaggio consiste  nell'accedere ai connettori dati nel Centro conformità Microsoft 365 e creare un connettore per Cisco Jabber sui dati SQL MS.

1. Accedere a [https://compliance.microsoft.com](https://compliance.microsoft.com/) e quindi fare clic su **Connettori dati**  >  **Cisco Jabber su MS SQL**.

2. Nella pagina **di descrizione del prodotto Cisco Jabber in MS SQL,** fare clic **su Aggiungi connettore.**

3. Nella pagina **Condizioni per il servizio** fare clic su **Accetta.**

4. Immettere un nome univoco che identifichi il connettore e quindi fare clic su **Avanti.**

5. Accedere all'account Merge1 per configurare il connettore.

## <a name="step-2-configure-the-cisco-jabber-connector-on-the-globanet-merge1-site"></a>Passaggio 2: Configurare il connettore Cisco Jabber nel sito Globanet Merge1

Il secondo passaggio consiste nel configurare il connettore Cisco Jabber su MS SQL nel sito Globanet Merge1. Per informazioni su come configurare Cisco Jabber su ms SQL connettore, vedere il Manuale dell'utente di [Merge1 Third-Party Connectors.](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20MS%20SQL%20User%20Guide%20.pdf)

Dopo aver fatto **clic su & fine,** viene visualizzata la pagina **Mapping** utenti nella procedura guidata del connettore nel Centro conformità Microsoft 365.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Passaggio 3: mappare gli utenti e completare la configurazione del connettore

Per mappare gli utenti e completare la configurazione del connettore nel Centro conformità Microsoft 365, attenersi alla seguente procedura:

1. Nella pagina Mappa Cisco Jabber in MS SQL utenti agli utenti di **Microsoft 365,** abilitare il mapping automatico degli utenti. Gli elementi cisco Jabber in MS SQL includono una proprietà denominata *Email,* che contiene gli indirizzi di posta elettronica per gli utenti dell'organizzazione. Se il connettore può associare questo indirizzo a un utente di Microsoft 365, gli elementi vengono importati nella cassetta postale dell'utente.

2. Fare **clic** su Avanti, rivedere le impostazioni e passare alla pagina **Connettori** dati per visualizzare l'avanzamento del processo di importazione per il nuovo connettore.

## <a name="step-4-monitor-the-cisco-jabber-connector"></a>Passaggio 4: Monitorare il connettore Cisco Jabber

Dopo aver creato il connettore Cisco Jabber su MS SQL, è possibile visualizzare lo stato del connettore nel Centro conformità Microsoft 365.

1. Andare a [https://compliance.microsoft.com](https://compliance.microsoft.com) e fare clic su **Connettori dati** nel riquadro di spostamento sinistro.

2. Fare clic **sulla scheda Connettori** e quindi selezionare **Il connettore cisco Jabber** su MS SQL per visualizzare la pagina a comparsa. Questa pagina contiene le proprietà e le informazioni sul connettore.

3. In **Stato connettore con origine** fare clic sul collegamento Scarica **registro** per aprire (o salvare) il registro di stato per il connettore. Questo log contiene i dati che sono stati importati nel cloud Microsoft.

## <a name="known-issues"></a>Problemi noti

- Al momento, non è possibile importare allegati o elementi di dimensioni superiori a 10 MB. Il supporto per gli elementi più grandi sarà disponibile in un secondo momento.
