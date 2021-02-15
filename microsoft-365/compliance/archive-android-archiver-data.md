---
title: Configurare un connettore per archiviare i dati mobili Android
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
description: Gli amministratori possono configurare un connettore TeleMessage per importare e archiviare SMS, MMS e chiamate vocali dai telefoni cellulari Android. In questo modo è possibile archiviare i dati da origini dati di terze parti in Microsoft 365, in modo da poter usare le funzionalità di conformità, ad esempio il blocco legale, la ricerca di contenuti e i criteri di conservazione per gestire i dati di terze parti dell'organizzazione.
ms.openlocfilehash: 5837d5247ca7ac82389d2781110883058ca98bb7
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620531"
---
# <a name="set-up-a-connector-to-archive-android-mobile-data"></a>Configurare un connettore per archiviare i dati mobili Android

Usare un connettore TeleMessage nel Centro conformità Microsoft 365 per importare e archiviare SMS, MMS, chiamate vocali e registri delle chiamate dai telefoni cellulari Android. Dopo aver configurato e configurato un connettore, il connettore si connette all'account TeleMessage dell'organizzazione una volta al giorno e importa la comunicazione mobile dei dipendenti tramite l'archivio Android Di TeleMessage nelle cassette postali di Microsoft 365.

Dopo aver archiviato i dati dei telefoni cellulari Android nelle cassette postali degli utenti, è possibile applicare le funzionalità di conformità di Microsoft 365, ad esempio conservazione per controversia legale, Ricerca contenuto e criteri di conservazione di Microsoft 365 ai dati di Archiviazione Android. Ad esempio, è possibile cercare le comunicazioni mobili di Android Archiver utilizzando Ricerca contenuto o associare la cassetta postale contenente i dati del connettore di Archiviazione Android a un responsabile in un caso di Advanced eDiscovery. L'uso di un connettore di archiviazione Android per importare e archiviare i dati in Microsoft 365 può aiutare l'organizzazione a rimanere conforme ai criteri normativi e governativi.

## <a name="overview-of-archiving-android-mobile-data"></a>Panoramica dell'archiviazione dei dati per dispositivi mobili Android

La seguente panoramica spiega il processo di utilizzo di un connettore per archiviare i dati mobili Android in Microsoft 365.

![Flusso di lavoro del connettore di Archiviazione Android](../media/AndroidArchiverConnectorWorkflow.png)

1. L'organizzazione collabora con TeleMessage per configurare un connettore di Archiviazione Android. Per altre informazioni, vedi [Android Archiver.](https://www.telemessage.com/office365-activation-for-android-archiver/)

2. Una volta ogni 24 ore, SMS, MMS, chiamate vocali e registri delle chiamate dai telefoni cellulari Android dell'organizzazione vengono copiati nel sito TeleMessage.

3. Il connettore di Archiviazione Android creato nel Centro conformità Microsoft 365 si connette al sito TeleMessage ogni giorno e trasferisce i dati Android dalle 24 ore precedenti a una posizione di archiviazione sicura di Azure in Microsoft Cloud. Il connettore converte anche i dati Android in un formato di messaggio di posta elettronica.

4. Il connettore importa gli elementi di comunicazione mobile nella cassetta postale di un utente specifico. Viene creata una nuova cartella denominata Android Archiver nella cassetta postale dell'utente specifico e gli elementi vengono importati in essa. Il connettore esegue il mapping utilizzando il valore della *proprietà dell'indirizzo di posta* elettronica dell'utente. Ogni messaggio di posta elettronica contiene questa proprietà, che viene popolata con l'indirizzo di posta elettronica di ogni partecipante del messaggio di posta elettronica. Oltre al mapping automatico degli utenti tramite il valore della proprietà *Dell'indirizzo* di posta elettronica dell'utente, è anche possibile definire un mapping personalizzato caricando un file di mapping CSV. Questo file di mapping deve contenere il numero di cellulare dell'utente e l'indirizzo della cassetta postale di Microsoft 365 corrispondente per ogni utente. Se si abilita il mapping automatico degli utenti e si fornisce un mapping personalizzato, per ogni elemento di posta elettronica il connettore guarderà innanzitutto il file di mapping personalizzato. Se non trova un utente di Microsoft 365 valido che corrisponde al numero di cellulare di un utente, il connettore utilizzerà la proprietà dell'indirizzo di posta elettronica dell'utente dell'elemento di posta elettronica. Se il connettore non trova un utente di Microsoft 365 valido nel file di mapping personalizzato o nella proprietà *dell'indirizzo* di posta elettronica dell'utente dell'elemento di posta elettronica, l'elemento non verrà importato.

## <a name="before-you-begin"></a>Prima di iniziare

Alcuni dei passaggi di implementazione necessari per archiviare i dati di comunicazione Android sono esterni a Microsoft 365 e devono essere completati prima di poter creare il connettore nel Centro conformità.

- Ordinare [il servizio Di archiviazione Android da TeleMessage e](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365) ottenere un account di amministrazione valido per l'organizzazione. È necessario accedere a questo account quando si crea il connettore.

- Registrare tutti gli utenti che richiedono il servizio Di archiviazione Android nell'account TeleMessage. Quando si registrano gli utenti, assicurarsi di usare lo stesso indirizzo di posta elettronica usato per il proprio account Microsoft 365.

- Installare e attivare l'app TeleMessage Android Archiver sui telefoni cellulari dei dipendenti.

- All'utente che crea un connettore di archiviazione Android deve essere assegnato il ruolo importazione/esportazione delle cassette postali in Exchange Online. Questa operazione è necessaria per aggiungere connettori nella pagina **Connettori** dati nel Centro conformità Microsoft 365. Per impostazione predefinita, questo ruolo non è assegnato ad alcun gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo di importazione/esportazione delle cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online. In or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members. Per ulteriori informazioni, vedere le sezioni [Creazione](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) di gruppi di ruoli o Modifica gruppi [di](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) ruoli nell'articolo "Gestire i gruppi di ruoli in Exchange Online".

## <a name="create-an-android-archiver-connector"></a>Creare un connettore di Archiviazione Android

L'ultimo passaggio consiste nel creare un connettore di Archiviazione Android nel Centro conformità Microsoft 365. Il connettore utilizza le informazioni fornite per connettersi al sito TeleMessage e trasferire le comunicazioni Android alle caselle delle cassette postali utente corrispondenti in Microsoft 365.

1. Andare a [https://compliance.microsoft.com](https://compliance.microsoft.com) e fare clic su **Connettori di dati** android  >  **Archiver.**

2. Nella pagina **della descrizione del prodotto Android Archiver,** fare clic **su Aggiungi connettore.**

3. Nella pagina **Condizioni per il servizio** fare clic su **Accetta.**

4. Nella pagina **Accesso a TeleMessage,** al passaggio 3, immettere le informazioni necessarie nelle caselle seguenti e quindi fare clic su **Avanti.**

   - **Nome utente:** Nome utente TeleMessage.

   - **Password:** La password di TeleMessage.

5. Dopo aver creato il connettore, chiudere la finestra popup e fare clic su **Avanti.**

6. Nella pagina **Mapping utenti abilitare** il mapping automatico degli utenti e fare clic su **Avanti.** Nel caso in cui sia necessario un mapping personalizzato caricare un file CSV e fare clic su **Avanti.**

7. Rivedere le impostazioni, quindi fare clic su **Fine** per creare il connettore.

8. Passare alla scheda Connettori nella **pagina Connettori** dati per visualizzare l'avanzamento del processo di importazione per il nuovo connettore.

## <a name="known-issues"></a>Problemi noti

- Al momento, non è possibile importare allegati o elementi di dimensioni superiori a 10 MB. Il supporto per gli elementi più grandi sarà disponibile in un secondo momento.
