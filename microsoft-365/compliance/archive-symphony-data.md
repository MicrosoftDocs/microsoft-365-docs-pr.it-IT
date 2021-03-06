---
title: Configurare un connettore per archiviare i dati di Symphony in Microsoft 365
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
description: Gli amministratori possono configurare un connettore per importare e archiviare i dati da Veritas Symphony in Microsoft 365. Questo connettore consente di archiviare i dati da origini dati di terze parti in Microsoft 365. Dopo l'archiviazione di questi dati, è possibile utilizzare funzionalità di conformità come il blocco legale, la ricerca di contenuto e i criteri di conservazione per gestire i dati di terze parti.
ms.openlocfilehash: b3ddb6826f7ef68808a819ee1d860b020efea98a
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163980"
---
# <a name="set-up-a-connector-to-archive-symphony-data"></a>Configurare un connettore per archiviare i dati di Symphony

Utilizzare un connettore Veritas nel Centro Microsoft 365 conformità per importare e archiviare i dati di Symphony nelle cassette postali degli utenti dell'Microsoft 365'organizzazione. Sinfonia è una piattaforma di messaggistica e collaborazione utilizzata nel settore dei servizi finanziari. Veritas fornisce un connettore dati [Disinfezione](https://globanet.com/symphony) nel Centro conformità di Microsoft 365 che è possibile configurare per acquisire gli elementi dall'origine dati di terze parti (a intervalli regolari) e quindi importare tali elementi nelle cassette postali degli utenti. Il connettore converte il contenuto di un elemento dall'account sinfonico in un formato di messaggio di posta elettronica e quindi importa l'elemento in una cassetta postale in Microsoft 365.

Dopo l'archiviazione delle comunicazioni di Sinfonia nelle cassette postali degli utenti, è possibile applicare funzionalità di conformità Microsoft 365 quali conservazione per controversia legale, eDiscovery, criteri di conservazione ed etichette di conservazione e conformità delle comunicazioni. L'utilizzo di un connettore di Sinfonia per importare e archiviare i dati in Microsoft 365 può aiutare l'organizzazione a rimanere conforme ai criteri governativi e normativi.

## <a name="overview-of-archiving-symphony-data"></a>Panoramica dell'archiviazione dei dati di Symphony

Nella panoramica seguente viene illustrato il processo di utilizzo di un connettore dati per archiviare le comunicazioni di Symphony Microsoft 365.

![Flusso di lavoro per l'archiviazione Disas](../media/SymphonyConnectorWorkflow.png)

1. L'organizzazione collabora con La sinfonia per configurare un sito di sinfonia.

2. Una volta ogni 24 ore, i messaggi di chat di Symphony vengono copiati nel sito Veritas Merge1. Il connettore converte anche il contenuto di un messaggio di chat in un formato di messaggio di posta elettronica.

3. Il connettore sinfonico creato nel Centro conformità Microsoft 365, si connette ogni giorno al sito Veritas Merge1 e trasferisce i messaggi in una posizione Archiviazione di Azure sicura nel cloud Microsoft.

4. Il connettore importa gli elementi dei messaggi convertiti nelle cassette postali di utenti specifici utilizzando il valore della proprietà *Email* del mapping automatico degli utenti, come descritto nel passaggio 3. Viene creata una nuova sottocartella nella cartella Posta in arrivo **denominata Sinfonia** nelle cassette postali degli utenti e gli elementi del messaggio vengono importati in tale cartella. Il connettore determina in quale cassetta postale importare gli elementi utilizzando il valore della *proprietà Email.* Ogni messaggio di chat contiene questa proprietà, che viene popolata con l'indirizzo di posta elettronica di ogni partecipante.

## <a name="before-you-begin"></a>Prima di iniziare

- Creare un account Veritas Merge1 per i connettori Microsoft. Per creare un account, contattare il [Supporto clienti Veritas.](https://globanet.com/ms-connectors-contact) Si accederà a questo account quando si crea il connettore nel passaggio 1.

- L'utente che crea il connettore sinfonico nel passaggio 1 (e lo completa nel passaggio 3) deve essere assegnato al ruolo Esportazione importazione cassette postali in Exchange Online. Questo ruolo è necessario per aggiungere connettori nella pagina **Connettori** dati nel Centro Microsoft 365 conformità. Per impostazione predefinita, questo ruolo non viene assegnato a un gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo Esportazione importazione cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online. In caso contrario, è possibile creare un gruppo di ruoli, assegnare il ruolo Importazione/Esportazione cassette postali e quindi aggiungere gli utenti appropriati come membri. Per ulteriori informazioni, vedere le sezioni [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) o Modify role [groups](/Exchange/permissions-exo/role-groups#modify-role-groups) nell'articolo "Manage role groups in Exchange Online".

## <a name="step-1-set-up-the-symphony-connector"></a>Passaggio 1: Configurare il connettore sinfonico

Il primo passaggio consiste nell'accedere alla pagina **Connettori** dati nel Centro conformità Microsoft 365 e creare un connettore per i dati di Symphony.

1. Passare a [https://compliance.microsoft.com](https://compliance.microsoft.com/) e quindi fare clic su **Connettori dati**  >  **sinfonia**.

2. Nella pagina **Descrizione** prodotto Di sinfonia fare clic **su Aggiungi connettore.**

3. Nella pagina **Condizioni di servizio** fare clic su **Accetta.**

4. Immettere un nome univoco che identifichi il connettore e quindi fare clic su **Avanti.**

5. Accedere all'account Merge1 per configurare il connettore.

## <a name="configure-the-symphony-connector-on-the-veritas-merge1-site"></a>Configurare il connettore Sinfonia nel sito Veritas Merge1

Il secondo passaggio consiste nel configurare il connettore sinfonico nel sito Merge1. Per informazioni sulla configurazione del connettore sinfonico nel sito Veritas Merge1, vedere [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Symphony%20User%20Guide%20.pdf).

Dopo aver fatto **clic su Salva & fine,** viene visualizzata la pagina **Mapping** utenti nella procedura guidata del connettore nel Centro Microsoft 365 conformità.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Passaggio 3: mappare gli utenti e completare la configurazione del connettore

Per mappare gli utenti e completare la configurazione del connettore nel Centro Microsoft 365 conformità, attenersi alla seguente procedura:

1. Nella pagina **Mapping utenti esterni a Microsoft 365** utenti, abilitare il mapping automatico degli utenti. Gli elementi di Symphony includono una proprietà denominata *Email*, che contiene gli indirizzi di posta elettronica per gli utenti dell'organizzazione. Se il connettore può associare questo indirizzo a un Microsoft 365 utente, gli elementi vengono importati nella cassetta postale dell'utente.

2. Fare **clic** su Avanti, rivedere le impostazioni e quindi passare alla pagina **Connettori** dati per visualizzare l'avanzamento del processo di importazione per il nuovo connettore.

## <a name="step-4-monitor-the-symphony-connector"></a>Passaggio 4: Monitorare il connettore sinfonico

Dopo aver creato il connettore sinfonico, è possibile visualizzare lo stato del connettore nel Centro Microsoft 365 conformità.

1. Vai a [https://compliance.microsoft.com](https://compliance.microsoft.com) e fai clic su **Connettori dati** nel riquadro di spostamento sinistro.

2. Fare clic **sulla scheda Connettori** e quindi selezionare il **connettore sinfonico** per visualizzare la pagina a comparsa. Questa pagina contiene le proprietà e le informazioni sul connettore.

3. In **Stato connettore con origine** fare clic sul collegamento Scarica **registro** per aprire (o salvare) il registro di stato per il connettore. Questo registro contiene informazioni sui dati importati nel cloud Microsoft.

## <a name="known-issues"></a>Problemi noti

- Al momento non è possibile importare allegati o elementi di dimensioni superiori a 10 MB. Il supporto per gli elementi più grandi sarà disponibile in un secondo momento.