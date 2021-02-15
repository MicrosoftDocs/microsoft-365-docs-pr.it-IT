---
title: Configurare un connettore per archiviare i dati di rete di O2 in Microsoft 365
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
description: Gli amministratori possono configurare un connettore TeleMessage per importare e archiviare i dati SMS e MMS dalla rete mobile O2 in Microsoft 365. In questo modo è possibile archiviare i dati da origini dati di terze parti in Microsoft 365, in modo da poter usare le funzionalità di conformità, ad esempio il blocco legale, la ricerca di contenuti e i criteri di conservazione per gestire i dati di terze parti dell'organizzazione.
ms.openlocfilehash: 35dc19089a60f058583ce50350b803df5c894d92
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2020
ms.locfileid: "49619962"
---
# <a name="set-up-a-connector-to-archive-o2-network-data"></a>Configurare un connettore per archiviare i dati di rete O2

Usare un connettore TeleMessage nel Centro conformità Microsoft 365 per importare e archiviare messaggi SMS (Short Messaging Service) e chiamate vocali dalla rete mobile O2. Dopo aver configurato e configurato un connettore, si connette alla rete O2 dell'organizzazione una volta al giorno e importa SMS e chiamate vocali alle cassette postali in Microsoft 365.

Dopo aver archiviato i messaggi SMS e le chiamate vocali nelle cassette postali degli utenti, è possibile applicare le funzionalità di conformità di Microsoft 365, ad esempio il blocco per controversia legale, Ricerca contenuto e i criteri di conservazione di Microsoft 365 ai dati di rete di O2. Ad esempio, è possibile cercare messaggi SMS di rete O2 e chiamate vocali utilizzando Ricerca contenuto o associare la cassetta postale contenente i dati di rete O2 a un responsabile in un caso di Advanced eDiscovery. L'uso di un connettore di rete O2 per importare e archiviare i dati in Microsoft 365 può aiutare l'organizzazione a rimanere conforme ai criteri normativi e governativi.

## <a name="overview-of-archiving-o2-network-data"></a>Panoramica dell'archiviazione dei dati di rete O2

La panoramica seguente illustra il processo di utilizzo di un connettore per archiviare i dati di rete O2 in Microsoft 365.

![Flusso di lavoro di archiviazione di rete O2](../media/O2NetworkConnectorWorkflow.png)

1. L'organizzazione collabora con TeleMessage e O2 per configurare un connettore di rete O2. Per ulteriori informazioni, vedere [O2 Network Archiver.](https://www.telemessage.com/office365-activation-for-o2-network-archiver)

2. Una volta ogni 24 ore, i messaggi SMS e le chiamate vocali dalla rete O2 dell'organizzazione vengono copiati nel sito TeleMessage.

3. Il connettore di rete O2 creato nel Centro conformità Microsoft 365 si connette al sito TeleMessage ogni giorno e trasferisce i messaggi SMS e le chiamate vocali dalle 24 ore precedenti a una posizione sicura di Archiviazione di Azure in Microsoft Cloud. Il connettore converte inoltre il contenuto dei messaggi SMS e delle chiamate vocali in un formato di messaggio di posta elettronica.

4. Il connettore importa gli elementi di comunicazione mobile nella cassetta postale di utenti specifici. Viene creata una nuova **cartella denominata SMS O2** e Voice Network Archiver nella cassetta postale di un utente specifico e gli elementi vengono importati in essa. Il connettore esegue questo mapping utilizzando il valore della proprietà *Dell'indirizzo di posta* elettronica dell'utente. Ogni messaggio SMS e chiamata vocale contiene questa proprietà, che viene popolata con l'indirizzo di posta elettronica di ogni partecipante del messaggio.

   Oltre al mapping automatico degli utenti tramite il valore della proprietà *Dell'indirizzo* di posta elettronica dell'utente, è anche possibile definire un mapping personalizzato caricando un file di mapping CSV. Questo file di mapping contiene il numero di cellulare e l'indirizzo di posta elettronica di Microsoft 365 corrispondente per gli utenti dell'organizzazione. Se si abilita sia il mapping automatico degli utenti che il mapping personalizzato, per ogni elemento O2 il connettore esamina innanzitutto il file di mapping personalizzato. Se non trova un utente di Microsoft 365 valido che corrisponde al numero di cellulare di un utente, il connettore utilizzerà i valori nella proprietà dell'indirizzo di posta elettronica dell'elemento che sta tentando di importare. Se il connettore non trova un utente di Microsoft 365 valido nel file di mapping personalizzato o nella proprietà dell'indirizzo di posta elettronica dell'elemento O2, l'elemento non verrà importato.

## <a name="before-you-begin"></a>Prima di iniziare

Alcuni dei passaggi di implementazione necessari per archiviare i dati di rete di O2 sono esterni a Microsoft 365 e devono essere completati prima di poter creare un connettore nel Centro conformità.

- Ordinare il [servizio O2 Network Archiver da TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365/) e ottenere un account di amministrazione valido per l'organizzazione. Sarà necessario accedere a questo account quando si crea il connettore nel Centro conformità.

- Ottenere l'account di rete O2 e i dettagli di contatto di fatturazione in modo da poter compilare i moduli di onboarding di TeleMessage e ordinare il servizio di archiviazione dei messaggi da O2.

- Registrare tutti gli utenti che richiedono l'archiviazione di O2 SMS e Rete vocale nell'account TeleMessage. Quando si registrano gli utenti, assicurarsi di usare lo stesso indirizzo di posta elettronica usato per l'account di Microsoft 365.

- I dipendenti devono disporre di telefoni cellulari di proprietà aziendale e responsabili dell'azienda nella rete mobile O2. L'archiviazione dei messaggi in Microsoft 365 non è disponibile per i dispositivi BYOD (Bring Your Own Devices) di proprietà dei dipendenti.

- All'utente che crea un connettore di rete O2 deve essere assegnato il ruolo importazione/esportazione delle cassette postali in Exchange Online. Questa operazione è necessaria per aggiungere connettori nella pagina **Connettori** dati nel Centro conformità Microsoft 365. Per impostazione predefinita, questo ruolo non è assegnato ad alcun gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo di importazione/esportazione delle cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online. In or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members. Per ulteriori informazioni, vedere le sezioni [Creazione](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) di gruppi di ruoli o Modifica gruppi [di](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) ruoli nell'articolo "Gestire i gruppi di ruoli in Exchange Online".

## <a name="create-an-o2-network-connector"></a>Creare un connettore di rete O2

Dopo aver completato i prerequisiti descritti nella sezione precedente, è possibile creare un connettore di rete O2 nel Centro conformità Microsoft 365. Il connettore utilizza le informazioni fornite per connettersi al sito TeleMessage e trasferire messaggi SMS e chiamate vocali alle caselle delle cassette postali utente corrispondenti in Microsoft 365.

1. Passare a [https://compliance.microsoft.com](https://compliance.microsoft.com/) e quindi fare clic su **Connettori dati** \> **O2 Rete.**

2. Nella pagina della descrizione del prodotto di rete **O2,** fare clic **su Aggiungi connettore**

3. Nella pagina **Condizioni per il servizio** fare clic su **Accetta.**

4. Nella pagina **Accesso a TeleMessage,** al passaggio 3, immettere le informazioni necessarie nelle caselle seguenti e quindi fare clic su **Avanti.**

   - **Nome utente:** Nome utente TeleMessage.

   - **Password:** La password di TeleMessage.

5. Dopo aver creato il connettore, è possibile chiudere la finestra popup e passare alla pagina successiva.

6. Nella pagina **Mapping utenti abilitare** il mapping automatico degli utenti e fare clic su **Avanti.** Nel caso in cui sia necessario un mapping personalizzato caricare un file CSV e fare clic su **Avanti.**

7. Rivedere le impostazioni, quindi fare clic su **Fine** per creare il connettore.

8. Passare alla scheda Connettori nella **pagina Connettori dati** per visualizzare l'avanzamento del processo di importazione per il nuovo connettore.

## <a name="known-issues"></a>Problemi noti

- Al momento, non è possibile importare allegati o elementi di dimensioni superiori a 10 MB. Il supporto per gli elementi più grandi sarà disponibile in un secondo momento.
