---
title: Configurare un connettore per archiviare i dati ringcentral in Microsoft 365
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
description: Gli amministratori possono configurare un connettore per importare e archiviare i dati RingCentral da Veritas a Microsoft 365. Questo connettore consente di archiviare i dati da origini dati di terze parti in Microsoft 365. Dopo aver archiviato questi dati, è possibile utilizzare funzionalità di conformità come il blocco legale, eDiscovery e i criteri di conservazione per gestire i dati di terze parti.
ms.openlocfilehash: 4fc0b61d5bc47a573da3ef8dd12654316e77d073
ms.sourcegitcommit: 8c698d1a0c41baf5f35d07b0d765b4a5ead593d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/13/2021
ms.locfileid: "53408937"
---
# <a name="set-up-a-connector-to-archive-ringcentral-data-preview"></a>Configurare un connettore per archiviare i dati RingCentral (anteprima)

Utilizzare un connettore Veritas nel Centro conformità Microsoft 365 per importare e archiviare i dati dalla piattaforma RingCentral alle cassette postali degli utenti nell'Microsoft 365 organizzativa. Veritas fornisce il connettore RingCentral configurato per acquisire elementi dall'origine dati di terze parti e importare tali elementi in Microsoft 365. Il connettore converte contenuto come chat, allegati, attività, note e post da RingCentral in un formato di messaggio di posta elettronica e quindi importa tali elementi nelle cassette postali degli utenti in Microsoft 365.

Dopo l'archiviazione dei dati di RingCentral nelle cassette postali degli utenti, è possibile applicare Microsoft 365 di conformità, ad esempio conservazione per controversia legale, eDiscovery, criteri di conservazione ed etichette di conservazione. L'utilizzo di un connettore RingCentral per importare e archiviare i dati in Microsoft 365 può aiutare l'organizzazione a rimanere conforme ai criteri governativi e normativi.

## <a name="overview-of-archiving-ringcentral-data"></a>Panoramica dell'archiviazione dei dati RingCentral

Nella panoramica seguente viene illustrato il processo di utilizzo di un connettore per archiviare i dati ringcentral in Microsoft 365.

![Flusso di lavoro di archiviazione per i dati RingCentral](../media/RingCentralConnectorWorkflow.png)

1. L'organizzazione collabora con RingCentral per configurare un sito RingCentral.

2. Una volta ogni 24 ore, gli elementi RingCentral vengono copiati nel sito Veritas Merge1. Il connettore converte anche gli elementi RingCentral in un formato di messaggio di posta elettronica.

3. Il connettore RingCentral creato nel Centro conformità Microsoft 365, si connette al sito Veritas Merge1 ogni giorno e trasferisce il contenuto ringcentral in una posizione Archiviazione di Azure sicura nel cloud Microsoft.

4. Il connettore importa gli elementi convertiti nelle cassette postali di utenti specifici utilizzando il valore della proprietà *Email* del mapping automatico degli utenti, come descritto nel [passaggio 3.](#step-3-map-users-and-complete-the-connector-setup) Nelle cassette postali degli utenti viene creata una sottocartella nella cartella Posta in arrivo denominata **RingCentral** e gli elementi vengono importati in tale cartella. Il connettore determina in quale cassetta postale importare gli elementi utilizzando il valore della *proprietà Email.* Ogni elemento RingCentral contiene questa proprietà, che viene popolata con l'indirizzo di posta elettronica di ogni partecipante dell'elemento.

## <a name="before-you-set-up-a-connector"></a>Prima di configurare un connettore

- Creare un account Merge1 per i connettori Microsoft. Per creare questo account, contattare il [supporto tecnico Veritas.](https://www.veritas.com/form/requestacall/ms-connectors-contact) È necessario accedere a questo account quando si crea il connettore nel passaggio 1.

- Crea un'applicazione RingCentral per recuperare i dati dal tuo account RingCentral. Per istruzioni dettagliate sulla creazione dell'applicazione, vedere [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20RingCentral%20User%20Guide.pdf).

- L'utente che crea il connettore RingCentral nel passaggio 1 (e lo completa nel passaggio 3) deve essere assegnato al ruolo Esportazione importazione cassette postali in Exchange Online. Questo ruolo è necessario per aggiungere connettori nella pagina **Connettori** dati nell'Centro conformità Microsoft 365. Per impostazione predefinita, questo ruolo non viene assegnato ad alcun gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo Esportazione importazione cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online. In caso contrario, è possibile creare un gruppo di ruoli, assegnare il ruolo Importazione/Esportazione cassette postali e quindi aggiungere gli utenti appropriati come membri. Per ulteriori informazioni, vedere le sezioni [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) o Modify role [groups](/Exchange/permissions-exo/role-groups#modify-role-groups) nell'articolo "Manage role groups in Exchange Online".

## <a name="step-1-set-up-the-ringcentral-connector"></a>Passaggio 1: Configurare il connettore RingCentral

Il primo passaggio consiste nell'accedere alla pagina **Connettori** dati nell'Centro conformità Microsoft 365 e creare un connettore per i dati RingCentral.

1. Passare a <https://compliance.microsoft.com> e quindi fare clic su **Connettori dati**  >  **RingCentral**.

2. Nella pagina **Descrizione prodotto RingCentral** fare clic su **Aggiungi connettore.**

3. Nella pagina **Condizioni di servizio** fare clic su **Accetta.**

4. Immettere un nome univoco che identifichi il connettore e quindi fare clic su **Avanti.**

5. Accedere all'account Merge1 per configurare il connettore.

## <a name="step-2-configure-the-ringcentral-on-the-veritas-merge1-site"></a>Passaggio 2: Configurare RingCentral nel sito Veritas Merge1

Il secondo passaggio consiste nel configurare il connettore RingCentral nel sito Veritas Merge1. Per informazioni su come configurare il connettore RingCentral, vedere [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20RingCentral%20User%20Guide.pdf).

Dopo aver fatto **clic su Salva & fine,** verrà visualizzata la pagina **Mapping** utenti nella procedura guidata del connettore Centro conformità Microsoft 365 visualizzata.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Passaggio 3: mappare gli utenti e completare la configurazione del connettore

Per mappare gli utenti e completare la configurazione del connettore Centro conformità Microsoft 365, attenersi alla seguente procedura:

1. Nella pagina **Mappa utenti ringcentrali** Microsoft 365 utenti, abilitare il mapping automatico degli utenti. Gli elementi RingCentral includono una proprietà denominata *Email*, che contiene gli indirizzi di posta elettronica per gli utenti dell'organizzazione. Se il connettore può associare questo indirizzo a un Microsoft 365 utente, gli elementi vengono importati nella cassetta postale dell'utente.

2. Fare **clic** su Avanti, rivedere le impostazioni e quindi passare alla pagina **Connettori** dati per visualizzare l'avanzamento del processo di importazione per il nuovo connettore.

## <a name="step-4-monitor-the-ringcentral-connector"></a>Passaggio 4: Monitorare il connettore RingCentral

Dopo aver creato il connettore RingCentral, è possibile visualizzare lo stato del connettore nella Centro conformità Microsoft 365.

1. Vai a <https://compliance.microsoft.com/> e fai clic su **Connettori dati** nel riquadro di spostamento sinistro.

2. Fare clic **sulla scheda Connettori** e quindi selezionare il **connettore RingCentral** per visualizzare la pagina a comparsa, contenente le proprietà e le informazioni sul connettore.

3. In **Stato connettore con origine** fare clic sul collegamento Scarica **registro** per aprire (o salvare) il registro di stato per il connettore. Questo registro contiene i dati importati nel cloud Microsoft.

## <a name="known-issues"></a>Problemi noti

- Al momento non è possibile importare allegati o elementi di dimensioni superiori a 10 MB. Il supporto per gli elementi più grandi sarà disponibile in un secondo momento.
