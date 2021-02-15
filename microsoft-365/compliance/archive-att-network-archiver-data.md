---
title: Configurare un connettore per archiviare i dati di AT&T SMS/MMS Network
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
description: Gli amministratori possono configurare un connettore TeleMessage per importare e archiviare i dati SMS e MMS da AT&T Mobile Network. In questo modo è possibile archiviare i dati da origini dati di terze parti in Microsoft 365, in modo da poter usare le funzionalità di conformità, ad esempio il blocco legale, la ricerca di contenuti e i criteri di conservazione per gestire i dati di terze parti dell'organizzazione.
ms.openlocfilehash: ba728a690db4d4c31158ad68fc853c29218226cc
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620122"
---
# <a name="set-up-a-connector-to-archive-att-smsmms-data"></a>Configurare un connettore per archiviare i dati AT&T SMS/MMS

Usare un connettore TeleMessage nel Centro conformità Microsoft 365 per importare e archiviare i dati SMS e MMS da AT&T Mobile Network. Dopo aver configurato e configurato un connettore, si connette alla rete AT&T dell'organizzazione una volta al giorno e importa i dati SMS e MMS nelle cassette postali di Microsoft 365.

Dopo aver archiviato i messaggi SMS e MMS nelle cassette postali degli utenti, è possibile applicare le funzionalità di conformità di Microsoft 365, ad esempio il blocco per controversia legale, Ricerca contenuto e i criteri di conservazione di Microsoft 365 ai dati di AT&T Network. Ad esempio, è possibile cercare i dati di at&T Network utilizzando Ricerca contenuto o associare la cassetta postale contenente i dati del connettore di rete AT&T a un responsabile in un caso di Advanced eDiscovery. L'uso di un connettore di rete AT&T per importare e archiviare i dati in Microsoft 365 può aiutare l'organizzazione a rimanere conforme ai criteri normativi e governativi.

## <a name="overview-of-archiving-att-network-data"></a>Panoramica dell'archiviazione dei&T Network at

Nella panoramica seguente viene illustrato il processo di utilizzo di un connettore per archiviare i dati di AT&T Network in Microsoft 365.

![Flusso di lavoro di archiviazione di rete ATT](../media/ATTNetworkConnectorWorkflow.png)

1. L'organizzazione collabora con TeleMessage per configurare un connettore di&T. Per informazioni, vedere [AT&T Network Archiver.](https://www.telemessage.com/office365-activation-for-atnt-network-archiver/)

2. Una volta ogni 24 ore, i messaggi SMS e MMS dalla rete AT&T dell'organizzazione vengono copiati nel sito TeleMessage.

3. Il connettore di rete AT&T creato nel Centro conformità Microsoft 365 si connette ogni giorno al sito TeleMessage e trasferisce i messaggi SMS e MMS dalle 24 ore precedenti a una posizione di archiviazione sicura di Azure in Microsoft Cloud. Il connettore converte inoltre il contenuto dei messaggi SMS e MMS in un formato di messaggio di posta elettronica.

4. Il connettore importa gli elementi di comunicazione mobile nella cassetta postale di utenti specifici. Nella cassetta postale dell'utente viene creata una nuova cartella denominata **AT&T SMS/MMS Network Archiver** e gli elementi vengono importati in essa. Il connettore esegue questo mapping utilizzando il valore della proprietà *Dell'indirizzo di posta* elettronica dell'utente. Ogni MESSAGGIO SMS e MMS contiene questa proprietà, che viene popolata con l'indirizzo di posta elettronica di ogni partecipante del messaggio.
 
   Oltre al mapping automatico degli utenti tramite il valore della proprietà *Dell'indirizzo* di posta elettronica dell'utente, è anche possibile definire un mapping personalizzato caricando un file di mapping CSV. Questo file di mapping contiene il numero di cellulare e l'indirizzo di posta elettronica di Microsoft 365 corrispondente per gli utenti dell'organizzazione. Se si abilita il mapping automatico degli utenti e il mapping personalizzato, per ogni elemento di posta elettronica il connettore esamina innanzitutto il file di mapping personalizzato. Se non trova un utente di Microsoft 365 valido che corrisponde a un numero di cellulare, il connettore usa i valori nella proprietà dell'indirizzo di posta elettronica dell'elemento che sta tentando di importare. Se il connettore non trova un utente di Microsoft 365 valido nel file di mapping personalizzato o nella proprietà dell'indirizzo di posta elettronica dell'elemento di posta elettronica, l'elemento non verrà importato.

## <a name="before-you-begin"></a>Prima di iniziare

Alcuni dei passaggi di implementazione necessari per archiviare i dati di at&T Network sono esterni a Microsoft 365 e devono essere completati prima di poter creare il connettore nel Centro conformità.

- Ordinare [il servizio di archiviazione per dispositivi mobili da TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365/) e ottenere un account di amministrazione valido per l'organizzazione. È necessario accedere a questo account quando si crea il connettore nel Centro conformità.

- Ottieni il tuo account AT&T e i dettagli di contatto di fatturazione in modo da poter compilare i moduli di onboarding di TeleMessage e ordinare il servizio di archiviazione dei messaggi da AT&T.

- Registrare tutti gli utenti che richiedono l'archiviazione&T SMS/MMS Network nell'account TeleMessage. Quando si registrano gli utenti, assicurarsi di usare lo stesso indirizzo di posta elettronica usato per il proprio account Microsoft 365.

- I dipendenti devono disporre di telefoni cellulari di proprietà aziendale e responsabili dell'azienda nella rete mobile AT&T. L'archiviazione dei messaggi in Microsoft 365 non è disponibile per i dispositivi BYOD (Bring Your Own Devices) di proprietà dei dipendenti.

- All'utente che crea un connettore di rete AT&T deve essere assegnato il ruolo di importazione/esportazione delle cassette postali in Exchange Online. Questa operazione è necessaria per aggiungere connettori nella pagina **Connettori dati** nel Centro conformità Microsoft 365. Per impostazione predefinita, questo ruolo non è assegnato ad alcun gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo di importazione/esportazione delle cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online. In or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members. Per ulteriori informazioni, vedere le sezioni [Creazione](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) di gruppi di ruoli o Modifica gruppi [di](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) ruoli nell'articolo "Gestire i gruppi di ruoli in Exchange Online".

## <a name="create-a-att-network-connector"></a>Creare un connettore di&T AT

Dopo aver completato i prerequisiti descritti nella sezione precedente, è possibile creare un connettore di rete AT&T nel Centro conformità Microsoft 365. Il connettore utilizza le informazioni fornite per connettersi al sito TeleMessage e trasferire i messaggi SMS e MMS alle caselle delle cassette postali utente corrispondenti in Microsoft 365.

1. Accedere a [https://compliance.microsoft.com](https://compliance.microsoft.com/) e quindi fare clic su **Connettori dati** AT&T  \  **Network**.

2. Nella pagina **di descrizione del prodotto at&T Network,** fare clic **su Aggiungi connettore**

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
