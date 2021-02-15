---
title: Configurare un connettore per archiviare i dati di rete MMS/SMS di Bell
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
description: Gli amministratori possono configurare un connettore TeleMessage per importare e archiviare i dati SMS e MMS dalla rete Bell. In questo modo è possibile archiviare i dati da origini dati di terze parti in Microsoft 365, in modo da poter usare le funzionalità di conformità, ad esempio il blocco legale, la ricerca di contenuti e i criteri di conservazione per gestire i dati di terze parti dell'organizzazione.
ms.openlocfilehash: d615488e5f6441efd828a6b91c187e7a8f5ca2c8
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620477"
---
# <a name="set-up-a-connector-to-archive-bell-network-data"></a>Configurare un connettore per archiviare i dati della rete Bell

Utilizzare un connettore TeleMessage nel Centro conformità Microsoft 365 per importare e archiviare i messaggi SMS (Short Messaging Service) e MMS (Multimedia Messaging Service) dalla rete Bell. Dopo aver configurato e configurato un connettore, il connettore si connette alla rete Bell dell'organizzazione una volta al giorno e importa messaggi SMS e MMS nelle cassette postali di Microsoft 365.

Dopo aver archiviato i messaggi SMS e MMS nelle cassette postali degli utenti, è possibile applicare le funzionalità di conformità di Microsoft 365, ad esempio conservazione per controversia legale, Ricerca contenuto e criteri di conservazione di Microsoft 365 ai dati di Bell Network. Ad esempio, è possibile cercare SMS/MMS di Bell Network utilizzando Ricerca contenuto o associare la cassetta postale contenente i dati del connettore di rete Bell a un responsabile in un caso di Advanced eDiscovery. L'uso di un connettore di rete Bell per importare e archiviare i dati in Microsoft 365 può aiutare l'organizzazione a rimanere conforme ai criteri normativi e governativi.

## <a name="overview-of-archiving-bell-network-data"></a>Panoramica dell'archiviazione dei dati di Bell Network

La seguente panoramica spiega il processo di utilizzo di un connettore per archiviare i dati della rete Bell in Microsoft 365.

![Flusso di lavoro di archiviazione della rete Bell](../media/BellNetworkConnectorWorkflow.png)

1. L'organizzazione collabora con TeleMessage e Bell per configurare un connettore di rete Bell. Per ulteriori informazioni, vedere [Bell Network Archiver.](https://www.telemessage.com/office365-activation-for-bell-network-archiver)

2. Una volta ogni 24 ore, i messaggi SMS e MMS dalla rete Bell dell'organizzazione vengono copiati nel sito TeleMessage.

3. Il connettore bell network creato nel Centro conformità Microsoft 365 si connette al sito TeleMessage ogni giorno e trasferisce i messaggi SMS e MMS dalle 24 ore precedenti a una posizione sicura di Archiviazione di Azure in Microsoft Cloud. Il connettore converte inoltre il contenuto dei messaggi SMS e MMS in un formato di messaggio di posta elettronica.

4. Il connettore importa gli elementi di comunicazione mobile nella cassetta postale di utenti specifici. Viene creata una nuova cartella **denominata Bell SMS/MMS Network Archiver** nella cassetta postale di un utente specifico e gli elementi vengono importati in essa. Il connettore esegue questo mapping utilizzando il valore della proprietà *Dell'indirizzo di posta* elettronica dell'utente. Ogni MESSAGGIO SMS e MMS contiene questa proprietà, che viene popolata con l'indirizzo di posta elettronica di ogni partecipante del messaggio.

   Oltre al mapping automatico degli utenti tramite il valore della proprietà *Dell'indirizzo* di posta elettronica dell'utente, è anche possibile definire un mapping personalizzato caricando un file di mapping CSV. Questo file di mapping contiene il numero di cellulare e l'indirizzo di posta elettronica di Microsoft 365 corrispondente per gli utenti dell'organizzazione. Se si abilita sia il mapping automatico degli utenti che il mapping personalizzato, per ogni elemento della rete di Bell il connettore esamina innanzitutto il file di mapping personalizzato. Se non trova un utente di Microsoft 365 valido che corrisponde al numero di cellulare di un utente, il connettore utilizzerà i valori nella proprietà dell'indirizzo di posta elettronica dell'elemento che sta tentando di importare. Se il connettore non trova un utente di Microsoft 365 valido nel file di mapping personalizzato o nella proprietà dell'indirizzo di posta elettronica dell'elemento rete Bell, l'elemento non verrà importato.

## <a name="before-you-begin"></a>Prima di iniziare

Alcuni dei passaggi di implementazione necessari per archiviare i dati di Bell Network sono esterni a Microsoft 365 e devono essere completati prima di poter creare un connettore nel Centro conformità.

- Ordinare il [servizio Bell Network Archiver da TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365/) e ottenere un account di amministrazione valido per l'organizzazione. È necessario accedere a questo account quando si crea il connettore nel Centro conformità.

- Ottieni l'account di Rete Di Bell e i dettagli di contatto per la fatturazione in modo da poter compilare i moduli di onboarding di TeleMessage e ordinare il servizio di archiviazione dei messaggi da Bell.

- Registrare tutti gli utenti che richiedono l'archiviazione della rete SMS/MMS Bell nell'account TeleMessage. Quando si registrano gli utenti, assicurarsi di usare lo stesso indirizzo di posta elettronica usato per l'account di Microsoft 365.

- I dipendenti devono disporre di telefoni cellulari di proprietà dell'azienda e responsabili dell'azienda sulla rete mobile Bell. L'archiviazione dei messaggi in Microsoft 365 non è disponibile per i dispositivi BYOD (Bring Your Own Devices) di proprietà dei dipendenti.

- All'utente che crea un connettore di rete Bell deve essere assegnato il ruolo di importazione/esportazione delle cassette postali in Exchange Online. Questa operazione è necessaria per aggiungere connettori nella pagina **Connettori** dati nel Centro conformità Microsoft 365. Per impostazione predefinita, questo ruolo non è assegnato ad alcun gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo di importazione/esportazione delle cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online. In or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members. Per ulteriori informazioni, vedere le sezioni [Creazione](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) di gruppi di ruoli o Modifica gruppi [di](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) ruoli nell'articolo "Gestire i gruppi di ruoli in Exchange Online".

## <a name="create-a-bell-network-connector"></a>Creare un connettore di rete di Bell

L'ultimo passaggio consiste nel creare un connettore di rete di Bell nel Centro conformità Microsoft 365. Il connettore utilizza le informazioni fornite per connettersi al sito TeleMessage e trasferire i messaggi SMS/MMS alle caselle della cassetta postale utente corrispondenti in Microsoft 365.

1. Andare a [https://compliance.microsoft.com](https://compliance.microsoft.com) e fare clic su **Connettori dati** Bell  >  **SMS/MMS Network Archiver.**

2. Nella pagina **Descrizione prodotto** rete Bell, fare clic **su Aggiungi connettore**

3. Nella pagina **Condizioni per il servizio** fare clic su **Accetta.**

4. Nella pagina **Accesso a TeleMessage,** al passaggio 3, immettere le informazioni necessarie nelle caselle seguenti e quindi fare clic su **Avanti.**

   - **Nome utente:** Nome utente TeleMessage.

   - **Password:** La password di TeleMessage.

5. Dopo aver creato il connettore, è possibile chiudere la finestra popup e passare alla pagina successiva.

6. Nella pagina **Mapping utenti** abilitare il mapping automatico degli utenti. Per abilitare il mapping personalizzato, caricare un file CSV contenente le informazioni sul mapping degli utenti e quindi fare clic su **Avanti.**

7. Rivedere le impostazioni, quindi fare clic su **Fine** per creare il connettore.

8. Passare alla scheda **Connettori** nella pagina **Connettori** dati nel Centro conformità per visualizzare lo stato del processo di importazione per il nuovo connettore.

## <a name="known-issues"></a>Problemi noti

- Al momento, non è possibile importare allegati o elementi di dimensioni superiori a 10 MB. Il supporto per gli elementi più grandi sarà disponibile in un secondo momento.
