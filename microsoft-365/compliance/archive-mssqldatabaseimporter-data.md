---
title: Configurare un connettore per archiviare i dati da MS database SQL
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
description: Gli amministratori possono configurare un connettore per importare e archiviare i dati da MS database SQL. Questo connettore consente di archiviare i dati da origini dati di terze parti in Microsoft 365. Dopo l'archiviazione di questi dati, è possibile utilizzare funzionalità di conformità come il blocco legale, la ricerca di contenuto e i criteri di conservazione per gestire i dati di terze parti.
ms.openlocfilehash: 494e91085494ba027a80480faba3cfb189cbd928
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164217"
---
# <a name="set-up-a-connector-to-archive-data-from-ms-sql-database"></a>Configurare un connettore per archiviare i dati da MS database SQL

Utilizzare un connettore Veritas nel Centro conformità Microsoft 365 per importare e archiviare i dati da MS database SQL alle cassette postali degli utenti nell'organizzazione Microsoft 365 locale. Veritas fornisce un connettore di importazione ms database SQL configurato per acquisire elementi da un database utilizzando un file di configurazione XML e importare tali elementi in Microsoft 365. Il connettore converte il contenuto da MS database SQL in un formato di messaggio di posta elettronica e quindi importa tali elementi nelle cassette postali degli utenti in Microsoft 365.

Dopo che il contenuto di MS database SQL archiviato nelle cassette postali degli utenti, è possibile applicare Microsoft 365 di conformità, ad esempio conservazione per controversia legale, eDiscovery, criteri di conservazione ed etichette di conservazione. L'utilizzo di un connettore ms database SQL per importare e archiviare i dati in Microsoft 365 può aiutare l'organizzazione a rimanere conforme ai criteri governativi e normativi.

## <a name="overview-of-archiving-the-ms-sql-data"></a>Panoramica dell'archiviazione dei dati SQL ms

Nella panoramica seguente viene illustrato il processo di utilizzo di un connettore per archiviare i dati SQL ms in Microsoft 365.

![Flusso di lavoro di archiviazione per i dati SQL ms](../media/MSSQLDatabaseConnectorWorkflow.png)

1. L'organizzazione collabora con un provider di servizi database SQL MS per configurare un sito ms database SQL.

2. Una volta ogni 24 ore, gli database SQL ms vengono copiati nel sito Veritas Merge1. Il connettore converte anche questo contenuto in un formato di messaggio di posta elettronica.

3. Il connettore microsoft database SQL Importer creato nel Centro conformità Microsoft 365, si connette al sito Veritas Merge1 ogni giorno e trasferisce i messaggi in una posizione Archiviazione di Azure sicura nel cloud Microsoft.

4. Il connettore importa gli elementi database SQL MS convertiti nelle cassette postali di utenti specifici utilizzando il valore della proprietà *Email* del mapping automatico degli utenti, come descritto nel [passaggio 3.](#step-3-map-users-and-complete-the-connector-setup) Nelle cassette postali degli utenti viene creata una sottocartella nella cartella Posta in arrivo denominata **MS database SQL Importer** e gli elementi vengono importati in tale cartella. Il connettore determina in quale cassetta postale importare gli elementi utilizzando il valore della *proprietà Email.* Ogni elemento di MS database SQL contiene questa proprietà, che viene popolata con l'indirizzo di posta elettronica di ogni partecipante dell'elemento.

## <a name="before-you-begin"></a>Prima di iniziare

- Creare un account Veritas Merge1 per i connettori Microsoft. Per creare un account, contattare il [Supporto clienti Veritas.](https://www.veritas.com/content/support/) È necessario accedere a questo account quando si crea il connettore nel passaggio 1.

- L'utente che crea il connettore dell'utilità di importazione di MS database SQL nel passaggio 1 (e lo completa nel passaggio 3) deve essere assegnato al ruolo Esportazione importazione cassette postali in Exchange Online. Questo ruolo è necessario per aggiungere connettori nella pagina Connettori dati nel Centro Microsoft 365 conformità. Per impostazione predefinita, questo ruolo non viene assegnato ad alcun gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo Esportazione importazione cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online. In caso contrario, è possibile creare un gruppo di ruoli, assegnare il ruolo Importazione/Esportazione cassette postali e quindi aggiungere gli utenti appropriati come membri. Per ulteriori informazioni, vedere le sezioni [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) o Modify role [groups](/Exchange/permissions-exo/role-groups#modify-role-groups) nell'articolo "Manage role groups in Exchange Online".

## <a name="step-1-set-up-the-ms-sql-database-importer-connector"></a>Passaggio 1: Configurare il connettore dell'utilità di database SQL MS

Il primo passaggio consiste nell'accedere alla pagina **Connettori** dati nel Centro conformità Microsoft365 e creare un connettore per ms database SQL.

1. Passare a [https://compliance.microsoft.com](https://compliance.microsoft.com) e quindi fare clic su **Connettori dati** MS  >  **database SQL Importer**.

2. Nella pagina **MS database SQL Descrizione prodotto** dell'utilità di importazione fare clic su Aggiungi nuovo **connettore.**

3. Nella pagina **Condizioni di servizio** fare clic su **Accetta.**

4. Immettere un nome univoco che identifichi il connettore e quindi fare clic su **Avanti.**

5. Accedere all'account Merge1 per configurare il connettore.

## <a name="step-2-configure-the-ms-sql-database-importer-connector-on-the-veritas-merge1-site"></a>Passaggio 2: Configurare il connettore dell'utilità di database SQL MS nel sito Veritas Merge1

Il secondo passaggio consiste nel configurare il connettore dell'utilità di database SQL MS nel sito Merge1. Per informazioni su come configurare l'utilità di database SQL MS, vedere [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20MS%20SQL%20Database%20Importer%20User%20Guide%20.pdf).

Dopo aver fatto **clic su Salva & fine,** viene visualizzata la pagina **Mapping** utenti nella procedura guidata del connettore nel Centro Microsoft 365 conformità.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Passaggio 3: mappare gli utenti e completare la configurazione del connettore

Per mappare gli utenti e completare la configurazione del connettore, attenersi alla seguente procedura:

1. Nella pagina **Mappare gli utenti database SQL importatori** a Microsoft 365 utenti, abilitare il mapping automatico degli utenti. Gli elementi database SQL ms includono una proprietà denominata *Email*, che contiene gli indirizzi di posta elettronica per gli utenti dell'organizzazione. Se il connettore può associare questo indirizzo a un Microsoft 365 utente, gli elementi vengono importati nella cassetta postale dell'utente.

2. Fare **clic** su Avanti, rivedere le impostazioni e passare alla pagina **Connettori** dati per visualizzare l'avanzamento del processo di importazione per il nuovo connettore.

## <a name="step-4-monitor-the-ms-sql-database-importer-connector"></a>Passaggio 4: Monitorare il connettore dell'utilità di database SQL MS

Dopo aver creato il connettore database SQL'utilità di importazione ms, è possibile visualizzare lo stato del connettore nel Centro Microsoft 365 conformità.

1. Vai a <https://compliance.microsoft.com/> e fai clic su **Connettori dati** nel riquadro di spostamento sinistro.

2. Fare clic **sulla scheda Connettori** e quindi selezionare il connettore di importazione **ms database SQL**  per visualizzare la pagina a comparsa, che contiene le proprietà e le informazioni sul connettore.

3. In **Stato connettore con origine** fare clic sul collegamento Scarica **registro** per aprire (o salvare) il registro di stato per il connettore. Questo registro contiene i dati importati nel cloud Microsoft.

## <a name="known-issues"></a>Problemi noti

- Al momento non è possibile importare allegati o elementi di dimensioni superiori a 10 MB. Il supporto per gli elementi più grandi sarà disponibile in un secondo momento.