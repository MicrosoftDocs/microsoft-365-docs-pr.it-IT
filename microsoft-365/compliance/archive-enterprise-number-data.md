---
title: Configurare un connettore per archiviare i dati da TeleMessage Enterprise Number Archiver
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
description: Gli amministratori possono configurare un connettore per importare e archiviare i dati SMS e MMS da TeleMessage Enterprise Number Archiver. In questo modo è possibile archiviare i dati da origini dati di terze parti in Microsoft 365, in modo da poter usare le funzionalità di conformità, ad esempio il blocco legale, la ricerca di contenuti e i criteri di conservazione per gestire i dati di terze parti dell'organizzazione.
ms.openlocfilehash: 01c2807606449c576e292f8819a861b1193b4723
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620022"
---
# <a name="set-up-a-connector-to-archive-enterprise-number-data"></a>Configurare un connettore per archiviare i dati relativi al numero aziendale

Utilizzare un connettore TeleMessage nel Centro conformità Microsoft 365 per importare e archiviare messaggi SMS (Short Messaging Service) e MMS (Multimedia Messaging Service), messaggi di chat, registrazioni di chiamate vocali e registri delle chiamate vocali dall'Enterprise Number Archiver. Dopo aver configurato e configurato un connettore, il connettore si connette all'account TeleMessage dell'organizzazione una volta al giorno e importa i dati di comunicazione mobile dei dipendenti tramite l'Archivio numeri aziendali TeleMessage nelle cassette postali di Microsoft 365.

Dopo aver archiviato i dati del connettore TeleMessage Enterprise Number Archiver nelle cassette postali degli utenti, è possibile applicare le funzionalità di conformità di Microsoft 365, ad esempio conservazione per controversia legale, Ricerca contenuto, archiviazione In-Place, controllo, conformità delle comunicazioni e criteri di conservazione di Microsoft 365 ai dati di Enterprise Number Archiver. Ad esempio, è possibile eseguire ricerche in SMS, MMS e Chiamata vocale teleMessage Enterprise Number Archiver utilizzando Ricerca contenuto o associare la cassetta postale contenente i dati del connettore Enterprise Number Archiver a un responsabile in un caso di Advanced eDiscovery. L'uso di un connettore Enterprise Number Archiver per importare e archiviare i dati in Microsoft 365 può aiutare l'organizzazione a rimanere conforme ai criteri normativi e governativi.

## <a name="overview-of-archiving-enterprise-number-data"></a>Panoramica dell'archiviazione dei dati relativi al numero aziendale

Nella seguente panoramica viene illustrato il processo di utilizzo di un connettore per archiviare i dati della rete aziendale in Microsoft 365.

![Flusso di lavoro per l'archiviazione dei numeri aziendali](../media/EnterpriseNumberConnectorWorkflow.png)

1. L'organizzazione collabora con TeleMessage per configurare un connettore Enterprise Number Archiver. Per ulteriori dettagli, fare riferimento a [questo sito.](https://www.telemessage.com/office365-activation-for-enterprise-number-archiver/)

2. Il connettore Enterprise Number Archiver creato nel Centro conformità Microsoft 365 si connette al sito TeleMessage ogni giorno e trasferisce i messaggi di posta elettronica dalle 24 ore precedenti a un'area di archiviazione sicura di Azure in Microsoft Cloud.

3. Il connettore importa gli elementi di comunicazione mobile nella cassetta postale di un utente specifico. Viene creata una nuova cartella denominata Enterprise Number Archiver nella cassetta postale dell'utente specifico e gli elementi vengono importati in essa. Il connettore esegue il mapping utilizzando il valore della *proprietà dell'indirizzo di posta* elettronica dell'utente. Ogni messaggio di posta elettronica contiene questa proprietà, che viene popolata con l'indirizzo di posta elettronica di ogni partecipante del messaggio di posta elettronica. Oltre al mapping automatico degli utenti tramite il valore della proprietà *Dell'indirizzo* di posta elettronica dell'utente, è anche possibile definire un mapping personalizzato caricando un file di mapping CSV. Questo file di mapping deve contenere il numero di cellulare dell'utente e l'indirizzo della cassetta postale di Microsoft 365 corrispondente per ogni utente. Se si abilita il mapping automatico degli utenti e si fornisce un mapping personalizzato, per ogni elemento di posta elettronica il connettore guarderà innanzitutto il file di mapping personalizzato. Se non trova un utente di Microsoft 365 valido che corrisponde al numero di cellulare di un utente, il connettore utilizzerà la proprietà dell'indirizzo di posta elettronica dell'utente dell'elemento di posta elettronica. Se il connettore non trova un utente di Microsoft 365 valido nel file di mapping personalizzato o nella proprietà *dell'indirizzo* di posta elettronica dell'utente dell'elemento di posta elettronica, l'elemento non verrà importato.

## <a name="before-you-begin"></a>Prima di iniziare

Alcuni dei passaggi di implementazione necessari per archiviare i dati di Enterprise Number Archiver sono esterni a Microsoft 365 e devono essere completati prima di poter creare il connettore nel Centro conformità.

- Ordinare [il servizio Enterprise Number Archiver da TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365) e ottenere un account di amministrazione valido per l'organizzazione. È necessario accedere a questo account quando si crea il connettore nel Centro conformità.

- Registrare tutti gli utenti che richiedono l'archiviazione DI RETE SMS/MMS nell'account TeleMessage. Quando si registrano gli utenti, assicurarsi di usare lo stesso indirizzo di posta elettronica usato per l'account di Microsoft 365.

- Installare e attivare l'app TeleMessage Enterprise Number Archiver sui telefoni cellulari dei dipendenti.

- All'utente che crea un connettore Enterprise Number Archiver deve essere assegnato il ruolo di importazione/esportazione delle cassette postali in Exchange Online. Questa operazione è necessaria per aggiungere connettori nella pagina **Connettori** dati nel Centro conformità Microsoft 365. Per impostazione predefinita, questo ruolo non è assegnato ad alcun gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo di importazione/esportazione delle cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online. In or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members. Per ulteriori informazioni, vedere le sezioni [Creazione](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) di gruppi di ruoli o Modifica gruppi [di](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) ruoli nell'articolo "Gestire i gruppi di ruoli in Exchange Online".

## <a name="create-an-enterprise-number-archiver-connector"></a>Creare un connettore Enterprise Number Archiver

Dopo aver completato i prerequisiti descritti nella sezione precedente, è possibile creare un connettore Enterprise Number Archiver nel Centro conformità Microsoft 365. Il connettore utilizza le informazioni fornite per connettersi al sito TeleMessage e trasferire sms, MMS e messaggi di chiamata vocale alle caselle della cassetta postale utente corrispondenti in Microsoft 365.

1. Passare a [https://compliance.microsoft.com](https://compliance.microsoft.com/) e quindi fare clic su **Connettori dati** Enterprise Number \> **Archiver.**

2. Nella pagina **di descrizione del prodotto Enterprise Number Archiver** fare clic su **Add connector**

3. Nella pagina **Condizioni per il servizio** fare clic su **Accetta.**

4. Nella pagina **Accesso a TeleMessage,** al passaggio 3, immettere le informazioni necessarie nelle caselle seguenti e quindi fare clic su **Avanti.**

   - **Nome utente:** Nome utente TeleMessage.

   - **Password:** La password di TeleMessage.

5. Dopo aver creato il connettore, è possibile chiudere la finestra popup e passare alla pagina successiva.

6. Nella pagina **Mapping utenti** abilitare il mapping automatico degli utenti. Per abilitare il mapping personalizzato, caricare un file CSV contenente le informazioni sul mapping degli utenti e quindi fare clic su **Avanti.**

7. Rivedere le impostazioni, quindi fare clic su **Fine** per creare il connettore.

8. Passare alla scheda Connettori nella **pagina Connettori** dati per visualizzare l'avanzamento del processo di importazione per il nuovo connettore.

## <a name="known-issues"></a>Problemi noti

- Al momento, non è possibile importare allegati o elementi di dimensioni superiori a 10 MB. Il supporto per gli elementi più grandi sarà disponibile in un secondo momento.
