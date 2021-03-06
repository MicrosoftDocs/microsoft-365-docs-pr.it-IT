---
title: Configurare un connettore per archiviare Cisco Jabber nei dati SQL ms in Microsoft 365
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
description: Gli amministratori possono configurare un connettore per importare e archiviare Cisco Jabber in MS SQL dati da Veritas in Microsoft 365. Questo connettore consente di archiviare i dati da origini dati di terze parti in Microsoft 365. Dopo l'archiviazione di questi dati, è possibile utilizzare funzionalità di conformità come il blocco legale, la ricerca di contenuto e i criteri di conservazione per gestire i dati di terze parti.
ms.openlocfilehash: 01899e4142d6e60fb10a101f7af8e9b4143a38c8
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764303"
---
# <a name="set-up-a-connector-to-archive-cisco-jabber-on-ms-sql-data"></a>Configurare un connettore per archiviare Cisco Jabber nei dati SQL ms

Utilizzare un connettore Veritas nel Centro conformità Microsoft 365 per importare e archiviare i dati dalla piattaforma Cisco Jabber alle cassette postali degli utenti nell'organizzazione Microsoft 365 locale. Veritas fornisce un connettore [Cisco Jabber](https://globanet.com/jabber/) configurato per acquisire elementi dal database SQL MS di Jabber, ad esempio messaggi di chat 1:1 e chat di gruppo e quindi importare tali elementi in Microsoft 365. Il connettore recupera i dati dal database SQL MS di Cisco Jabber, lo elabora e converte il contenuto dall'account Cisco Jabber di un utente in un formato di messaggio di posta elettronica e quindi importa tali elementi nella cassetta postale dell'utente in Microsoft 365.

Dopo aver archiviato i dati di Cisco Jabber nelle cassette postali degli utenti, è possibile applicare funzionalità di conformità Microsoft 365 quali conservazione per controversia legale, eDiscovery, criteri di conservazione ed etichette di conservazione e conformità delle comunicazioni. L'utilizzo di un connettore Cisco Jabber per importare e archiviare i dati in Microsoft 365 può aiutare l'organizzazione a rimanere conforme ai criteri governativi e normativi.

## <a name="overview-of-archiving-cisco-jabber-data"></a>Panoramica dell'archiviazione dei dati Cisco Jabber

Nella panoramica seguente viene illustrato il processo di utilizzo di un connettore per archiviare Cisco Jabber nei dati SQL ms in Microsoft 365.

![Flusso di lavoro di archiviazione per i dati Cisco Jabber](../media/CiscoJabberonMSSQLConnectorWorkflow.png)

1. L'organizzazione collabora con Cisco per configurare un Cisco Jabber in MS database SQL.

2. Una volta ogni 24 ore, gli elementi Cisco Jabber vengono copiati dal database SQL ms al sito Veritas Merge1. Il connettore converte anche il contenuto dei messaggi di chat in un formato di messaggio di posta elettronica.

3. Il connettore Cisco Jabber creato nel Centro conformità Microsoft 365 si connette ogni giorno al sito Veritas Merge1 e trasferisce gli elementi in una posizione Archiviazione di Azure sicura nel cloud Microsoft.

4. Il mapping automatico degli utenti come connettore importa gli elementi nelle cassette postali di utenti specifici utilizzando il valore della *proprietà Email* di descritta nel [passaggio 3.](#step-3-map-users-and-complete-the-connector-setup) Nelle cassette postali degli utenti viene creata una sottocartella nella cartella Posta in arrivo denominata **Cisco Jabber** in MS SQL e gli elementi del messaggio vengono importati in tale cartella. Il connettore determina in quale cassetta postale importare gli elementi utilizzando il valore della *proprietà Email.* Ogni elemento Cisco Jabber contiene questa proprietà, che viene popolata con l'indirizzo di posta elettronica di ogni partecipante.

## <a name="before-you-begin"></a>Prima di iniziare

- Creare un account Veritas Merge1 per i connettori Microsoft. Per creare questo account, contattare il [supporto tecnico Veritas.](https://www.veritas.com/content/support/) Si accederà a questo account quando si crea il connettore nel passaggio 1.

- Configurare un'istanza di DATABASE SQL per recuperare gli elementi jabber da prima di creare il connettore nel passaggio 1. Quando si configura il connettore Cisco Jabber nel passaggio 2, verranno specificate le impostazioni di connessione per l'database SQL MS. Per ulteriori informazioni, vedere [merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20MS%20SQL%20User%20Guide%20.pdf).

- L'utente che crea il connettore Cisco Jabber nel passaggio 1 (e lo completa nel passaggio 3) deve essere assegnato al ruolo Esportazione importazione cassette postali in Exchange Online. Questo ruolo è necessario per aggiungere connettori nella pagina **Connettori** dati nel Centro Microsoft 365 conformità. Per impostazione predefinita, questo ruolo non viene assegnato a un gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo Esportazione importazione cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online. In caso contrario, è possibile creare un gruppo di ruoli, assegnare il ruolo Importazione/Esportazione cassette postali e quindi aggiungere gli utenti appropriati come membri. Per ulteriori informazioni, vedere le sezioni [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) o Modify role [groups](/Exchange/permissions-exo/role-groups#modify-role-groups) nell'articolo "Manage role groups in Exchange Online".

## <a name="step-1-set-up-the-cisco-jabber-on-ms-sql-connector"></a>Passaggio 1: Configurare Cisco Jabber in MS SQL connector

Il primo passaggio consiste  nell'accedere ai connettori dati nel Centro conformità Microsoft 365 e creare un connettore per Cisco Jabber nei dati SQL MS.

1. Passare a [https://compliance.microsoft.com](https://compliance.microsoft.com/) e quindi fare clic su **Connettori dati**  >  **Cisco Jabber su MS SQL**.

2. Nella pagina **Cisco Jabber on MS SQL** product description fare clic **su Add connector**.

3. Nella pagina **Condizioni di servizio** fare clic su **Accetta.**

4. Immettere un nome univoco che identifichi il connettore e quindi fare clic su **Avanti.**

5. Accedere all'account Merge1 per configurare il connettore.

## <a name="step-2-configure-the-cisco-jabber-on-ms-sql-connector-on-the-veritas-merge1-site"></a>Passaggio 2: Configurare il connettore Cisco Jabber su MS SQL nel sito Veritas Merge1

Il secondo passaggio consiste nel configurare il connettore Cisco Jabber su MS SQL nel sito Veritas Merge1. Per informazioni su come configurare il connettore Cisco Jabber su MS SQL, vedere [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20MS%20SQL%20User%20Guide%20.pdf).

Dopo aver fatto **clic su Salva & fine,** viene visualizzata la pagina **Mapping** utenti nella procedura guidata del connettore nel Centro Microsoft 365 conformità.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Passaggio 3: mappare gli utenti e completare la configurazione del connettore

Per mappare gli utenti e completare la configurazione del connettore nel Centro Microsoft 365 conformità, attenersi alla seguente procedura:

1. Nella pagina **Mappa Cisco Jabber in MS SQL utenti** a Microsoft 365 utenti, abilitare il mapping automatico degli utenti. Gli elementi Cisco Jabber on MS SQL includono una proprietà denominata *Email*, che contiene gli indirizzi di posta elettronica per gli utenti dell'organizzazione. Se il connettore può associare questo indirizzo a un Microsoft 365 utente, gli elementi vengono importati nella cassetta postale dell'utente.

2. Fare **clic** su Avanti, rivedere le impostazioni e passare alla pagina **Connettori** dati per visualizzare l'avanzamento del processo di importazione per il nuovo connettore.

## <a name="step-4-monitor-the-cisco-jabber-connector"></a>Passaggio 4: Monitorare il connettore Cisco Jabber

Dopo aver creato il connettore Cisco Jabber su MS SQL, è possibile visualizzare lo stato del connettore nel Centro Microsoft 365 conformità.

1. Vai a [https://compliance.microsoft.com](https://compliance.microsoft.com) e fai clic su **Connettori dati** nel riquadro di spostamento sinistro.

2. Fare clic **sulla scheda Connettori** e quindi selezionare **Cisco Jabber in MS SQL** connettore per visualizzare la pagina a comparsa. Questa pagina contiene le proprietà e le informazioni sul connettore.

3. In **Stato connettore con origine** fare clic sul collegamento Scarica **registro** per aprire (o salvare) il registro di stato per il connettore. Questo registro contiene i dati importati nel cloud Microsoft.

## <a name="known-issues"></a>Problemi noti

- Al momento non è possibile importare allegati o elementi di dimensioni superiori a 10 MB. Il supporto per gli elementi più grandi sarà disponibile in un secondo momento.
