---
title: Configurare un connettore per archiviare i dati di origine XIP in Microsoft 365
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
description: Gli amministratori possono configurare un connettore per importare e archiviare i dati di origine XIP da Veritas a Microsoft 365. Questo connettore consente di archiviare i dati da origini dati di terze parti in Microsoft 365. Dopo l'archiviazione di questi dati, è possibile utilizzare funzionalità di conformità come il blocco legale, la ricerca di contenuto e i criteri di conservazione per gestire i dati di terze parti.
ms.openlocfilehash: a3906d9a79c214ca7cfc25f868c5f24661f40004
ms.sourcegitcommit: 778103d20a2b4c43e524aa436775764d8d8d4c33
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2021
ms.locfileid: "53096637"
---
# <a name="set-up-a-connector-to-archive-xip-source-data"></a>Configurare un connettore per archiviare i dati di origine XIP

Utilizzare un connettore Veritas nel Centro conformità Microsoft 365 per importare e archiviare i dati dalla piattaforma di origine XIP alle cassette postali degli utenti nell'Microsoft 365 organizzazione. Veritas fornisce un [connettore XIP](https://globanet.com/xip/) che consente di utilizzare un file XIP per importare elementi Microsoft 365. Un file XIP è simile a un file ZIP, ma consente di utilizzare una firma digitale. La firma digitale viene verificata da Veritas Merge 1 prima dell'estrazione del file di origine XIP. Il connettore converte il contenuto dal file di origine XIP in un formato di messaggio di posta elettronica e quindi importa tali elementi nelle cassette postali degli utenti in Microsoft 365.

Dopo aver archiviato i dati di origine XIP nelle cassette postali degli utenti, è possibile applicare funzionalità di conformità Microsoft 365 quali conservazione per controversia legale, eDiscovery, criteri di conservazione ed etichette di conservazione e conformità delle comunicazioni. L'utilizzo di un connettore XIP per importare e archiviare i dati in Microsoft 365 può aiutare l'organizzazione a rimanere conforme ai criteri governativi e normativi.

## <a name="overview-of-archiving-the-xip-source-data"></a>Panoramica dell'archiviazione dei dati di origine XIP

Nella panoramica seguente viene illustrato il processo di utilizzo di un connettore per archiviare i dati di origine XIP in Microsoft 365.

![Flusso di lavoro di archiviazione per i dati di origine XIP](../media/XIPConnectorWorkflow.png)

1. L'organizzazione collabora con l'origine XIP per configurare un sito XIP.

2. Una volta ogni 24 ore, gli elementi di origine XIP vengono copiati nel sito Veritas Merge1. Il connettore converte anche il contenuto in un formato di messaggio di posta elettronica.

3. Il connettore XIP creato nel Centro conformità Microsoft 365, si connette ogni giorno al sito Veritas Merge1 e trasferisce i messaggi in una posizione Archiviazione di Azure sicura nel cloud Microsoft.

4. Il connettore importa gli elementi dei messaggi convertiti nelle cassette postali di utenti specifici utilizzando il valore della proprietà *Email* del mapping automatico degli utenti, come descritto nel [passaggio 3.](#step-3-map-users-and-complete-the-connector-setup) Nelle cassette postali degli utenti viene creata una sottocartella nella cartella Posta in arrivo denominata **XIP** e gli elementi vengono importati in tale cartella. Il connettore determina in quale cassetta postale importare gli elementi utilizzando il valore della *proprietà Email.* Ogni elemento di origine contiene questa proprietà, che viene popolata con l'indirizzo di posta elettronica di ogni partecipante.

## <a name="before-you-begin"></a>Prima di iniziare

- Creare un account Veritas Merge1 per i connettori Microsoft. Per creare un account, contattare il [Supporto clienti Veritas.](https://www.veritas.com/content/support/) È necessario accedere a questo account quando si crea il connettore nel passaggio 1.

- L'utente che crea il connettore XIP nel passaggio 1 (e lo completa nel passaggio 3) deve essere assegnato al ruolo Esportazione importazione cassette postali in Exchange Online. Questo ruolo è necessario per aggiungere connettori nella pagina Connettori dati nell'Centro conformità Microsoft 365. Per impostazione predefinita, questo ruolo non viene assegnato ad alcun gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo Esportazione importazione cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online. In caso contrario, è possibile creare un gruppo di ruoli, assegnare il ruolo Importazione/Esportazione cassette postali e quindi aggiungere gli utenti appropriati come membri. Per ulteriori informazioni, vedere le sezioni [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) o Modify role [groups](/Exchange/permissions-exo/role-groups#modify-role-groups) nell'articolo "Manage role groups in Exchange Online".

## <a name="step-1-set-up-the-xip-connector"></a>Passaggio 1: Configurare il connettore XIP

Il primo passaggio consiste nell'accedere alla pagina **Connettori** dati nel Centro conformità Microsoft365 e creare un connettore per i dati di origine XIP.

1. Passare a [https://compliance.microsoft.com](https://compliance.microsoft.com/) e quindi fare clic su **Connettori dati** \> **XIP.**

2. Nella pagina **Descrizione prodotto XIP** fare clic **su Aggiungi nuovo connettore.**

3. Nella pagina **Condizioni di servizio** fare clic su **Accetta.**

4. Immettere un nome univoco che identifichi il connettore e quindi fare clic su **Avanti.**

5. Accedere all'account Merge1 per configurare il connettore.

## <a name="step-2-configure-the-xip-connector-on-the-veritas-merge1-site"></a>Passaggio 2: Configurare il connettore XIP nel sito Veritas Merge1

Il secondo passaggio consiste nel configurare il connettore XIP nel sito Merge1. Per informazioni su come configurare il connettore XIP, vedere [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20XIP%20User%20Guide%20.pdf).

Dopo aver fatto **clic su Salva & fine,** viene visualizzata la pagina **Mapping** utenti nella procedura guidata del connettore Centro conformità Microsoft 365 visualizzata.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Passaggio 3: mappare gli utenti e completare la configurazione del connettore

Per mappare gli utenti e completare la configurazione del connettore, attenersi alla seguente procedura:

1. Nella pagina **Mapping utenti XIP Microsoft 365 utenti,** abilitare il mapping automatico degli utenti. Gli elementi di origine XIP includono una proprietà denominata *Email*, che contiene gli indirizzi di posta elettronica per gli utenti dell'organizzazione. Se il connettore può associare questo indirizzo a un Microsoft 365 utente, gli elementi vengono importati nella cassetta postale dell'utente.

2. Fare **clic** su Avanti, rivedere le impostazioni e passare alla pagina **Connettori** dati per visualizzare l'avanzamento del processo di importazione per il nuovo connettore.

## <a name="step-4-monitor-the-xip-connector"></a>Passaggio 4: Monitorare il connettore XIP

Dopo aver creato il connettore XIP, è possibile visualizzare lo stato del connettore nella Centro conformità Microsoft 365.

1. Vai a [https://compliance.microsoft.com](https://compliance.microsoft.com/) e fai clic su **Connettori dati** nel riquadro di spostamento sinistro.

2. Fare clic **sulla scheda Connettori** e quindi selezionare il **connettore XIP** per visualizzare la pagina a comparsa, contenente le proprietà e le informazioni sul connettore.

3. In **Stato connettore con origine** fare clic sul collegamento Scarica **registro** per aprire (o salvare) il registro di stato per il connettore. Questo registro contiene i dati importati nel cloud Microsoft.

## <a name="known-issues"></a>Problemi noti

- Al momento non è possibile importare allegati o elementi di dimensioni superiori a 10 MB. Il supporto per gli elementi più grandi sarà disponibile in un secondo momento.