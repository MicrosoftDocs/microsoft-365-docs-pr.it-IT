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
description: Gli amministratori possono configurare un connettore per importare e archiviare SMS mms da TeleMessage Enterprise Number Archiver. In questo modo è possibile archiviare i dati da origini dati di terze parti in Microsoft 365 in modo da poter utilizzare funzionalità di conformità come il blocco legale, la ricerca di contenuto e i criteri di conservazione per gestire i dati di terze parti dell'organizzazione.
ms.openlocfilehash: 1615aaed21eca6d0c8c22343e19c1ea93b693aaa
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822203"
---
# <a name="set-up-a-connector-to-archive-enterprise-number-data"></a>Configurare un connettore per archiviare i Enterprise numerici

Utilizzare un connettore TeleMessage nel Centro conformità Microsoft 365 per importare e archiviare i messaggi del servizio di messaggistica breve (SMS) e mms (Multimedia Messaging Service), i messaggi di chat, le registrazioni delle chiamate vocali e i registri delle chiamate vocali dall'utilità di archiviazione numeri di Enterprise. Dopo aver configurato e configurato un connettore, il connettore si connette all'account TeleMessage dell'organizzazione una volta al giorno e importa i dati di comunicazione mobile dei dipendenti utilizzando l'archivio numeri telemessage Enterprise per le cassette postali in Microsoft 365.

Dopo aver archiviato i dati del connettore TeleMessage Enterprise Number Archiver nelle cassette postali degli utenti, è possibile applicare funzionalità di conformità Microsoft 365 quali conservazione per controversia legale, ricerca contenuto, archiviazione In-Place, controllo, conformità delle comunicazioni e criteri di conservazione Microsoft 365 ai dati di Enterprise Number Archiver. Ad esempio, è possibile eseguire una ricerca nel SMS, MMS e Voice Call di TeleMessage Enterprise Number Archiver utilizzando Ricerca contenuto o associare la cassetta postale che contiene i dati del connettore di archiviazione dei numeri di Enterprise a un responsabile in un caso Advanced eDiscovery. L'utilizzo Enterprise connettore Number Archiver per importare e archiviare i dati in Microsoft 365 può aiutare l'organizzazione a rimanere conforme ai criteri normativi e governativi.

## <a name="overview-of-archiving-enterprise-number-data"></a>Panoramica dell'archiviazione Enterprise dati numerici

Nella panoramica seguente viene illustrato il processo di utilizzo di un connettore per archiviare Enterprise di rete in Microsoft 365.

![Enterprise Flusso di lavoro di archiviazione dei numeri](../media/EnterpriseNumberConnectorWorkflow.png)

1. L'organizzazione collabora con TeleMessage per configurare un connettore di archiviazione Enterprise numero. Per ulteriori dettagli, vedere [qui](https://www.telemessage.com/office365-activation-for-enterprise-number-archiver/).

2. Il connettore Enterprise Number Archiver creato nel Centro conformità Microsoft 365 si connette ogni giorno al sito TeleMessage e trasferisce i messaggi di posta elettronica dalle 24 ore precedenti a un'area Archiviazione di Azure sicura nel cloud Microsoft.

3. Il connettore importa gli elementi di comunicazione mobile nella cassetta postale di un utente specifico. Una nuova cartella denominata Enterprise Number Archiver viene creata nella cassetta postale dell'utente specifico e gli elementi vengono importati in essa. Il connettore esegue il mapping utilizzando il valore della proprietà Indirizzo di posta elettronica *dell'utente.* Ogni messaggio di posta elettronica contiene questa proprietà, che viene popolata con l'indirizzo di posta elettronica di ogni partecipante del messaggio di posta elettronica. Oltre al mapping automatico degli utenti utilizzando il valore della proprietà Indirizzo di posta elettronica *dell'utente,* è anche possibile definire un mapping personalizzato caricando un file di mapping CSV. Questo file di mapping deve contenere il numero di cellulare dell'utente e l'indirizzo Microsoft 365 corrispondente per ogni utente. Se si abilita il mapping automatico degli utenti e si fornisce un mapping personalizzato, per ogni elemento di posta elettronica il connettore guarderà innanzitutto il file di mapping personalizzato. Se non trova un utente Microsoft 365 valido corrispondente al numero di cellulare di un utente, il connettore utilizzerà la proprietà Dell'indirizzo di posta elettronica dell'utente dell'elemento di posta elettronica. Se il connettore non trova un utente Microsoft 365 valido nel file di mapping personalizzato o nella proprietà dell'indirizzo di posta elettronica dell'utente dell'elemento di posta elettronica, *l'elemento* non verrà importato.

## <a name="before-you-set-up-a-connector"></a>Prima di configurare un connettore

Alcuni dei passaggi di implementazione necessari per archiviare i Enterprise number archiver sono esterni a Microsoft 365 e devono essere completati prima di poter creare il connettore nel Centro conformità.

- Ordinare [il Enterprise Number Archiver da TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365) e ottenere un account di amministrazione valido per l'organizzazione. Sarà necessario accedere a questo account quando si crea il connettore nel Centro conformità.

- Registrare tutti gli utenti che richiedono Enterprise archiviazione SMS/MMS Network nell'account TeleMessage. Quando si registrano gli utenti, assicurarsi di usare lo stesso indirizzo di posta elettronica utilizzato per l'account Microsoft 365 account.

- Installare e attivare l'app TeleMessage Enterprise Number Archiver sui telefoni cellulari dei dipendenti.

- All'utente che crea un Enterprise di archiviazione dei numeri deve essere assegnato il ruolo Esportazione importazione cassette postali in Exchange Online. Questa operazione è necessaria per aggiungere connettori nella pagina **Connettori** dati nel Centro Microsoft 365 conformità. Per impostazione predefinita, questo ruolo non è assegnato ad alcun gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo Esportazione importazione cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online. In caso contrario, è possibile creare un gruppo di ruoli, assegnare il ruolo Importazione/Esportazione cassette postali e quindi aggiungere gli utenti appropriati come membri. Per ulteriori informazioni, vedere le sezioni [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) o Modify role [groups](/Exchange/permissions-exo/role-groups#modify-role-groups) nell'articolo "Manage role groups in Exchange Online".

- Questo connettore dati è disponibile in GCC nel cloud Microsoft 365 us government. Le applicazioni e i servizi di terze parti possono comportare l'archiviazione, la trasmissione e l'elaborazione dei dati dei clienti dell'organizzazione in sistemi di terze parti esterni all'infrastruttura di Microsoft 365 e pertanto non coperti dagli impegni di conformità e protezione dei dati di Microsoft 365. Microsoft non fa alcuna rappresentazione che utilizzi questo prodotto per connettersi ad applicazioni di terze parti implica che tali applicazioni di terze parti siano conformi a FEDRAMP.

## <a name="create-an-enterprise-number-archiver-connector"></a>Creare un connettore Enterprise archivio numeri

Dopo aver completato i prerequisiti descritti nella sezione precedente, è possibile creare un connettore Enterprise Number Archiver nel Centro Microsoft 365 conformità. Il connettore utilizza le informazioni fornite per connettersi al sito TeleMessage e trasferire i messaggi di SMS, MMS e chiamate vocali alle caselle delle cassette postali dell'utente corrispondenti in Microsoft 365.

1. Passare a [https://compliance.microsoft.com](https://compliance.microsoft.com/) e quindi fare clic su **Connettori** \> **dati Enterprise Archivio numeri**.

2. Nella pagina **Enterprise descrizione del prodotto Number Archiver** fare clic **su Aggiungi connettore**

3. Nella pagina **Condizioni di servizio** fare clic su **Accetta.**

4. Nella pagina **Accesso a TeleMessage,** in Passaggio 3, immettere le informazioni necessarie nelle caselle seguenti e quindi fare clic su **Avanti.**

   - **Nome utente:** Nome utente TeleMessage.

   - **Password:** Password TeleMessage.

5. Dopo aver creato il connettore, è possibile chiudere la finestra popup e passare alla pagina successiva.

6. Nella pagina **Mapping utenti** abilitare il mapping automatico degli utenti. Per abilitare il mapping personalizzato, caricare un file CSV contenente le informazioni sul mapping degli utenti e quindi fare clic su **Avanti.**

7. Rivedere le impostazioni e quindi fare clic **su Fine** per creare il connettore.

8. Passare alla scheda Connettori nella **pagina Connettori dati** per visualizzare l'avanzamento del processo di importazione per il nuovo connettore.

## <a name="known-issues"></a>Problemi noti

- Al momento non è possibile importare allegati o elementi di dimensioni superiori a 10 MB. Il supporto per gli elementi più grandi sarà disponibile in un secondo momento.