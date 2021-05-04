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
description: Gli amministratori possono configurare un connettore TeleMessage per importare e archiviare SMS, MMS e chiamate vocali dai telefoni cellulari Android. In questo modo è possibile archiviare i dati da origini dati di terze parti in Microsoft 365 in modo da poter utilizzare funzionalità di conformità come il blocco legale, la ricerca di contenuto e i criteri di conservazione per gestire i dati di terze parti dell'organizzazione.
ms.openlocfilehash: 92dcfbebaeb9f138b5a057d36e328967c43c9544
ms.sourcegitcommit: b169f6ad3e44a7fcebf77f43be9eb5edd84ea5ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2021
ms.locfileid: "52077236"
---
# <a name="set-up-a-connector-to-archive-android-mobile-data"></a>Configurare un connettore per archiviare i dati mobili Android

Usa un connettore TeleMessage nel Centro conformità Microsoft 365 per importare e archiviare SMS, MMS, chiamate vocali e registri delle chiamate dai telefoni cellulari Android. Dopo aver configurato e configurato un connettore, il connettore si connette all'account TeleMessage dell'organizzazione una volta al giorno e importa le comunicazioni mobili dei dipendenti che utilizzano l'archivio Android Di TeleMessage nelle cassette postali in Microsoft 365.

Dopo l'archiviazione dei dati dei telefoni cellulari Android nelle cassette postali degli utenti, è possibile applicare ai dati di Android Archiver funzionalità di conformità Microsoft 365 quali conservazione per controversia legale, ricerca contenuto e criteri di conservazione Microsoft 365. Ad esempio, è possibile eseguire ricerche nelle comunicazioni mobili di Android Archiver utilizzando Ricerca contenuto o associare la cassetta postale che contiene i dati del connettore di Archiviazione Android a un responsabile in un caso Advanced eDiscovery androide. L'utilizzo di un connettore di Archiviazione Android per importare e archiviare i dati in Microsoft 365 può aiutare l'organizzazione a rimanere conforme ai criteri governativi e normativi.

## <a name="overview-of-archiving-android-mobile-data"></a>Panoramica dell'archiviazione dei dati mobili Android

La panoramica seguente illustra il processo di utilizzo di un connettore per archiviare i dati mobili Android in Microsoft 365.

![Flusso di lavoro del connettore di Archiviazione Android](../media/AndroidArchiverConnectorWorkflow.png)

1. L'organizzazione collabora con TeleMessage per configurare un connettore Android Archiver. Per altre informazioni, vedi [Android Archiver.](https://www.telemessage.com/office365-activation-for-android-archiver/)

2. In tempo reale, SMS, MMS, chiamate vocali e registri delle chiamate dai telefoni cellulari Android dell'organizzazione vengono copiati nel sito TeleMessage.

3. Il connettore Android Archiver creato nel Centro conformità Microsoft 365 si connette ogni giorno al sito TeleMessage e trasferisce i dati Android dalle 24 ore precedenti a una posizione Archiviazione di Azure sicura nel cloud Microsoft. Il connettore converte anche i dati Android in un formato di messaggio di posta elettronica.

4. Il connettore importa gli elementi di comunicazione mobile nella cassetta postale di un utente specifico. Viene creata una nuova cartella denominata Android Archiver nella cassetta postale dell'utente specifico e gli elementi vengono importati in essa. Il connettore esegue il mapping utilizzando il valore della proprietà Indirizzo di posta elettronica *dell'utente.* Ogni messaggio di posta elettronica contiene questa proprietà, che viene popolata con l'indirizzo di posta elettronica di ogni partecipante del messaggio di posta elettronica. Oltre al mapping automatico degli utenti utilizzando il valore della proprietà Indirizzo di posta elettronica *dell'utente,* è anche possibile definire un mapping personalizzato caricando un file di mapping CSV. Questo file di mapping deve contenere il numero di cellulare e l Microsoft 365 corrispondente della cassetta postale per ogni utente. Se si abilita il mapping automatico degli utenti e si fornisce un mapping personalizzato, per ogni elemento di posta elettronica il connettore guarderà innanzitutto il file di mapping personalizzato. Se non viene trovato un utente Microsoft 365 valido che corrisponde al numero di cellulare di un utente, il connettore utilizzerà la proprietà dell'indirizzo di posta elettronica dell'utente dell'elemento di posta elettronica. Se il connettore non trova un utente Microsoft 365 valido nel file di mapping personalizzato o nella proprietà Dell'indirizzo di posta elettronica dell'utente dell'elemento di posta elettronica, *l'elemento* non verrà importato.

## <a name="before-you-begin"></a>Prima di iniziare

Alcuni dei passaggi di implementazione necessari per archiviare i dati di comunicazione Android sono esterni a Microsoft 365 e devono essere completati prima di poter creare il connettore nel Centro conformità.

- Ordina il [servizio Android Archiver da TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365) e ottieni un account di amministrazione valido per la tua organizzazione. Sarà necessario accedere a questo account quando si crea il connettore.

- Registrare tutti gli utenti che richiedono il servizio Android Archiver nell'account TeleMessage. Quando si registrano gli utenti, assicurarsi di usare lo stesso indirizzo di posta elettronica utilizzato per l'account Microsoft 365 account.

- Installare e attivare l'app TeleMessage Android Archiver sui telefoni cellulari dei dipendenti.

- All'utente che crea un connettore Android Archiver deve essere assegnato il ruolo Esportazione importazione cassette postali in Exchange Online. Questa operazione è necessaria per aggiungere connettori nella pagina **Connettori** dati nel Centro Microsoft 365 conformità. Per impostazione predefinita, questo ruolo non è assegnato ad alcun gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo Esportazione importazione cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online. In caso contrario, è possibile creare un gruppo di ruoli, assegnare il ruolo Importazione/Esportazione cassette postali e quindi aggiungere gli utenti appropriati come membri. Per ulteriori informazioni, vedere le sezioni [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) o Modify role [groups](/Exchange/permissions-exo/role-groups#modify-role-groups) nell'articolo "Manage role groups in Exchange Online".

## <a name="create-an-android-archiver-connector"></a>Creare un connettore di Archiviazione Android

L'ultimo passaggio consiste nel creare un connettore Di archiviazione Android nel Centro Microsoft 365 conformità. Il connettore utilizza le informazioni fornite per connettersi al sito TeleMessage e trasferire le comunicazioni Android alle caselle delle cassette postali utente corrispondenti in Microsoft 365.

1. Vai a [https://compliance.microsoft.com](https://compliance.microsoft.com) e fai clic su **Connettori dati** Android  >  **Archiver**.

2. Nella pagina **Descrizione del prodotto Android Archiver** fare clic su **Aggiungi connettore.**

3. Nella pagina **Condizioni di servizio** fare clic su **Accetta.**

4. Nella pagina **Accesso a TeleMessage,** in Passaggio 3, immettere le informazioni necessarie nelle caselle seguenti e quindi fare clic su **Avanti.**

   - **Nome utente:** Nome utente TeleMessage.

   - **Password:** Password TeleMessage.

5. Dopo aver creato il connettore, chiudere la finestra popup e fare clic su **Avanti.**

6. Nella pagina **Mapping utenti** abilitare il mapping automatico degli utenti e fare clic su **Avanti.** Nel caso in cui sia necessario un mapping personalizzato caricare un file CSV e fare clic su **Avanti.**

7. Rivedere le impostazioni e quindi fare clic **su Fine** per creare il connettore.

8. Passare alla scheda Connettori nella **pagina Connettori dati** per visualizzare l'avanzamento del processo di importazione per il nuovo connettore.

## <a name="known-issues"></a>Problemi noti

- Al momento non è possibile importare allegati o elementi di dimensioni superiori a 10 MB. Il supporto per gli elementi più grandi sarà disponibile in un secondo momento.
