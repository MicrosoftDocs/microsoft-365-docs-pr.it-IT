---
title: Configurare un connettore per archiviare i dati EML in Microsoft 365
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
description: Gli amministratori possono configurare un connettore per importare e archiviare i dati EML da Globanet in Microsoft 365. Questo connettore consente di archiviare i dati da origini dati di terze parti in Microsoft 365. Dopo l'archiviazione di questi dati, è possibile utilizzare funzionalità di conformità come la conservazione a livello legale, la ricerca di contenuto e i criteri di conservazione per gestire i dati di terze parti.
ms.openlocfilehash: 7c8649565df4e08fbdbdaf9c1cba0d890eb54b52
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620443"
---
# <a name="set-up-a-connector-to-archive-eml-data"></a>Configurare un connettore per archiviare i dati EML

Usare un connettore Globanet nel Centro conformità Microsoft 365 per importare e archiviare i dati EML nelle cassette postali degli utenti nell'organizzazione di Microsoft 365. EML è l'estensione di un messaggio di posta elettronica salvato in un file. Il connettore converte il contenuto di un elemento dal formato di origine a un formato di messaggio di posta elettronica e quindi importa l'elemento in una cassetta postale utente.

Dopo aver archiviato i messaggi EML nelle cassette postali degli utenti, è possibile applicare le funzionalità di conformità di Microsoft 365, ad esempio il blocco per controversia legale, eDiscovery, i criteri di conservazione e le etichette di conservazione. L'uso di un connettore EML per importare e archiviare i dati in Microsoft 365 può aiutare l'organizzazione a rimanere conforme ai criteri normativi e governativi.

## <a name="overview-of-archiving-eml-data"></a>Panoramica dell'archiviazione dei dati EML

La panoramica seguente illustra il processo di utilizzo di un connettore per archiviare i dati EML in Microsoft 365.

![Flusso di lavoro di archiviazione per i dati EML](../media/EMLConnectorWorkflow.png)

1. L'organizzazione collabora con l'origine EML per configurare un sito EML.

2. Una volta ogni 24 ore, gli elementi di contenuto dall'origine EML vengono copiati nel sito Globanet Merge1. Durante questo processo, il contenuto di un file EML viene convertito in un formato di messaggio di posta elettronica.

3. Il connettore EML creato nel Centro conformità Microsoft 365, si connette al sito Globanet Merge1 ogni giorno e trasferisce i messaggi in un percorso sicuro di Archiviazione di Azure nel cloud Microsoft.

4. Il connettore importa gli elementi dei messaggi convertiti nelle cassette postali di utenti specifici utilizzando il valore della proprietà *Email* del processo di mapping automatico degli utenti descritto [nel passaggio 3.](#step-3-map-users-and-complete-the-connector-setup) Durante questo processo viene creata una sottocartella nella cartella Posta in arrivo denominata **EML** nelle cassette postali degli utenti e gli elementi EML vengono importati in tale cartella. Il connettore determina in quale cassetta postale importare gli elementi utilizzando il valore della proprietà *Email.* Ogni messaggio contiene questa proprietà, che viene popolata con l'indirizzo di posta elettronica di ogni partecipante dell'elemento di contenuto.

## <a name="before-you-begin"></a>Prima di iniziare

- Creare un account Globanet Merge1 per i connettori Microsoft. Per creare un account, contattare [il supporto clienti Di Globanet.](https://globanet.com/ms-connectors-contact) Si accederà a questo account quando si crea il connettore nel passaggio 1.

- L'utente che crea il connettore EML nel passaggio 1 (e lo completa nel passaggio 3) deve essere assegnato al ruolo di importazione/esportazione delle cassette postali in Exchange Online. Questo ruolo è necessario per aggiungere connettori nella pagina **Connettori** dati nel Centro conformità Microsoft 365. Per impostazione predefinita, questo ruolo non è assegnato a un gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo di importazione/esportazione delle cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online. In or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members. Per ulteriori informazioni, vedere le sezioni [Creazione](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) di gruppi di ruoli o Modifica gruppi [di](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) ruoli nell'articolo "Gestire i gruppi di ruoli in Exchange Online".

## <a name="step-1-set-up-an-eml-connector"></a>Passaggio 1: Configurare un connettore EML

Il primo passaggio consiste nell'accedere alla pagina **Connettori** dati nel Centro conformità Microsoft 365 e creare un connettore per i dati EML.

1. Accedere a [https://compliance.microsoft.com](https://compliance.microsoft.com/) e quindi fare clic su **Connettori dati**  >  **EML.**

2. Nella pagina di descrizione del prodotto **EML,** fare clic **su Aggiungi connettore.**

3. Nella pagina **Condizioni per il servizio** fare clic su **Accetta.**

4. Immettere un nome univoco che identifichi il connettore, quindi fare clic su **Avanti.**

5. Accedere all'account Merge1 per configurare il connettore.

## <a name="step-2-configure-the-eml-connector-on-the-globanet-merge1-site"></a>Passaggio 2: Configurare il connettore EML nel sito Globanet Merge1

Il secondo passaggio consiste nel configurare il connettore EML nel sito Globanet Merge1. Per informazioni sulla configurazione del connettore EML, vedere il Manuale dell'utente di [Merge1 Third-Party Connectors.](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20EML%20User%20Guide%20.pdf)

Dopo aver fatto **clic su & fine,** viene visualizzata la pagina **Mapping** utenti nella procedura guidata del connettore nel Centro conformità Microsoft 365.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Passaggio 3: mappare gli utenti e completare la configurazione del connettore

Per mappare gli utenti e completare la configurazione del connettore nel Centro conformità Microsoft 365, attenersi alla seguente procedura:

1. Nella pagina **Mapping utenti esterni a utenti di Microsoft 365** abilitare il mapping automatico degli utenti. Gli elementi di origine EML includono una proprietà denominata *Email,* che contiene gli indirizzi di posta elettronica per gli utenti dell'organizzazione. Se il connettore può associare questo indirizzo a un utente di Microsoft 365, gli elementi EML vengono importati nella cassetta postale dell'utente.

2. Fare **clic** su Avanti, rivedere le  impostazioni e quindi passare alla pagina Connettori dati per visualizzare l'avanzamento del processo di importazione per il nuovo connettore.

## <a name="step-4-monitor-the-eml-connector"></a>Passaggio 4: Monitorare il connettore EML

Dopo aver creato il connettore EML, è possibile visualizzare lo stato del connettore nel Centro conformità Microsoft 365.

1. Andare a [https://compliance.microsoft.com](https://compliance.microsoft.com) e fare clic su **Connettori dati** nel riquadro di spostamento sinistro.

2. Fare clic **sulla scheda Connettori** e quindi selezionare il **connettore EML** per visualizzare la pagina a comparsa. Questa pagina contiene le proprietà e le informazioni sul connettore.

3. In **Stato connettore con origine** fare clic sul collegamento Scarica **registro** per aprire (o salvare) il registro di stato per il connettore. Questo log contiene informazioni sui dati importati nel cloud Microsoft.

## <a name="known-issues"></a>Problemi noti

- Al momento, non è possibile importare allegati o elementi di dimensioni superiori a 10 MB. Il supporto per gli elementi più grandi sarà disponibile in un secondo momento.
