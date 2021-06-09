---
title: Configurare un connettore per archiviare i dati SMS/MMS Network
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
description: Gli amministratori possono configurare un connettore TeleMessage per importare e archiviare i SMS mms dalla rete Bell. In questo modo è possibile archiviare i dati da origini dati di terze parti in Microsoft 365 in modo da poter utilizzare funzionalità di conformità come il blocco legale, la ricerca di contenuto e i criteri di conservazione per gestire i dati di terze parti dell'organizzazione.
ms.openlocfilehash: 7cfdb4556c19261b7e377df72ebe96b9cf20c992
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822215"
---
# <a name="set-up-a-connector-to-archive-bell-network-data"></a>Configurare un connettore per archiviare i dati di Bell Network

Utilizzare un connettore TeleMessage nel Centro conformità Microsoft 365 per importare e archiviare i messaggi di Servizio di messaggistica breve (SMS) e MMS (Multimedia Messaging Service) dalla rete Bell. Dopo aver configurato e configurato un connettore, il connettore si connette alla rete Bell dell'organizzazione una volta al giorno e importa i messaggi SMS e MMS nelle cassette postali in Microsoft 365.

Dopo l'archiviazione dei messaggi SMS e MMS nelle cassette postali degli utenti, è possibile applicare ai dati di Bell Network le funzionalità di conformità di Microsoft 365, ad esempio conservazione per controversia legale, ricerca contenuto e criteri di conservazione Microsoft 365. Ad esempio, è possibile cercare Bell Network SMS/MMS utilizzando Ricerca contenuto o associare la cassetta postale che contiene i dati del connettore di rete Bell a un responsabile in un caso Advanced eDiscovery locale. L'utilizzo di un connettore bell network per importare e archiviare i dati in Microsoft 365 può aiutare l'organizzazione a rimanere conforme ai criteri governativi e normativi.

## <a name="overview-of-archiving-bell-network-data"></a>Panoramica dell'archiviazione dei dati di Bell Network

Nella panoramica seguente viene illustrato il processo di utilizzo di un connettore per archiviare i dati di Bell Network in Microsoft 365.

![Flusso di lavoro di archiviazione di rete Bell](../media/BellNetworkConnectorWorkflow.png)

1. L'organizzazione collabora con TeleMessage e Bell per configurare un connettore bell network. Per ulteriori informazioni, vedere [Bell Network Archiver.](https://www.telemessage.com/office365-activation-for-bell-network-archiver)

2. In tempo reale, SMS messaggi MMS dalla rete Bell dell'organizzazione vengono copiati nel sito TeleMessage.

3. Il connettore bell network creato nel Centro conformità Microsoft 365 si connette ogni giorno al sito TeleMessage e trasferisce i messaggi SMS e MMS dalle 24 ore precedenti a una posizione Archiviazione di Azure sicura nel cloud Microsoft. Il connettore converte anche il contenuto dei messaggi SMS MMS in un formato di messaggio di posta elettronica.

4. Il connettore importa gli elementi di comunicazione mobile nella cassetta postale di utenti specifici. Viene creata una nuova cartella denominata **Bell SMS/MMS Network Archiver** nella cassetta postale di un utente specifico e gli elementi vengono importati in essa. Il connettore esegue questo mapping utilizzando il valore della proprietà Indirizzo di posta elettronica *dell'utente.* Ogni SMS e mms contiene questa proprietà, che viene popolata con l'indirizzo di posta elettronica di ogni partecipante del messaggio.

   Oltre al mapping automatico degli utenti utilizzando il valore della proprietà Indirizzo di posta elettronica *dell'utente,* è anche possibile definire un mapping personalizzato caricando un file di mapping CSV. Questo file di mapping contiene il numero di telefono cellulare e l Microsoft 365 indirizzo di posta elettronica corrispondente per gli utenti dell'organizzazione. Se si abilita sia il mapping automatico degli utenti che il mapping personalizzato, per ogni elemento bell network il connettore esamina innanzitutto il file di mapping personalizzato. Se non trova un utente Microsoft 365 valido corrispondente al numero di cellulare di un utente, il connettore utilizzerà i valori nella proprietà dell'indirizzo di posta elettronica dell'elemento che sta tentando di importare. Se il connettore non trova un utente Microsoft 365 valido nel file di mapping personalizzato o nella proprietà dell'indirizzo di posta elettronica dell'elemento Bell Network, l'elemento non verrà importato.

## <a name="before-you-set-up-a-connector"></a>Prima di configurare un connettore

Alcuni dei passaggi di implementazione necessari per archiviare i dati di Bell Network sono esterni a Microsoft 365 e devono essere completati prima di poter creare un connettore nel Centro conformità.

- Ordinare il [servizio Bell Network Archiver da TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365/) e ottenere un account di amministrazione valido per l'organizzazione. Sarà necessario accedere a questo account quando si crea il connettore nel Centro conformità.

- Ottenere l'account Bell Network e i dettagli di contatto di fatturazione in modo da poter compilare i moduli di onboarding di TeleMessage e ordinare il servizio di archiviazione dei messaggi da Bell.

- Registrare tutti gli utenti che richiedono l SMS/MMS Network archiviazione nell'account TeleMessage. Quando si registrano gli utenti, assicurarsi di usare lo stesso indirizzo di posta elettronica utilizzato per l'account Microsoft 365 account.

- I dipendenti devono disporre di telefoni cellulari di proprietà aziendale e responsabili dell'azienda nella rete mobile Bell. L'archiviazione dei messaggi Microsoft 365 non è disponibile per i dispositivi BYOD (Bring Your Own Devices) o di proprietà dei dipendenti.

- All'utente che crea un connettore di rete Bell deve essere assegnato il ruolo Esportazione importazione cassette postali in Exchange Online. Questa operazione è necessaria per aggiungere connettori nella pagina **Connettori** dati nel Centro Microsoft 365 conformità. Per impostazione predefinita, questo ruolo non è assegnato ad alcun gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo Esportazione importazione cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online. In caso contrario, è possibile creare un gruppo di ruoli, assegnare il ruolo Importazione/Esportazione cassette postali e quindi aggiungere gli utenti appropriati come membri. Per ulteriori informazioni, vedere le sezioni [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) o Modify role [groups](/Exchange/permissions-exo/role-groups#modify-role-groups) nell'articolo "Manage role groups in Exchange Online".

- Questo connettore dati è disponibile in GCC nel cloud Microsoft 365 us government. Le applicazioni e i servizi di terze parti possono comportare l'archiviazione, la trasmissione e l'elaborazione dei dati dei clienti dell'organizzazione in sistemi di terze parti esterni all'infrastruttura di Microsoft 365 e pertanto non coperti dagli impegni di conformità e protezione dei dati di Microsoft 365. Microsoft non fa alcuna rappresentazione che utilizzi questo prodotto per connettersi ad applicazioni di terze parti implica che tali applicazioni di terze parti siano conformi a FEDRAMP.

## <a name="create-a-bell-network-connector"></a>Creare un connettore di rete Bell

L'ultimo passaggio consiste nel creare un connettore bell network nel centro Microsoft 365 conformità. Il connettore utilizza le informazioni fornite per connettersi al sito TeleMessage e trasferire i messaggi SMS/MMS alle caselle delle cassette postali utente corrispondenti in Microsoft 365.

1. Vai a [https://compliance.microsoft.com](https://compliance.microsoft.com) e quindi fai clic su **Connettori** dati  >  **Bell SMS/MMS Network Archiver**.

2. Nella pagina **Descrizione del prodotto** Bell Network, fare clic **su Aggiungi connettore**

3. Nella pagina **Condizioni di servizio** fare clic su **Accetta.**

4. Nella pagina **Accesso a TeleMessage,** in Passaggio 3, immettere le informazioni necessarie nelle caselle seguenti e quindi fare clic su **Avanti.**

   - **Nome utente:** Nome utente TeleMessage.

   - **Password:** Password TeleMessage.

5. Dopo aver creato il connettore, è possibile chiudere la finestra popup e passare alla pagina successiva.

6. Nella pagina **Mapping utenti** abilitare il mapping automatico degli utenti. Per abilitare il mapping personalizzato, caricare un file CSV contenente le informazioni sul mapping degli utenti e quindi fare clic su **Avanti.**

7. Rivedere le impostazioni e quindi fare clic **su Fine** per creare il connettore.

8. Passare alla **scheda Connettori** nella pagina **Connettori** di dati nel Centro conformità per visualizzare l'avanzamento del processo di importazione per il nuovo connettore.

## <a name="known-issues"></a>Problemi noti

- Al momento non è possibile importare allegati o elementi di dimensioni superiori a 10 MB. Il supporto per gli elementi più grandi sarà disponibile in un secondo momento.
