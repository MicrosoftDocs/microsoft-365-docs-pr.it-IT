---
title: Configurare un connettore per archiviare i dati di rete O2 in Microsoft 365
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
description: Gli amministratori possono configurare un connettore TeleMessage per importare e archiviare i dati SMS MMS dalla rete mobile O2 in Microsoft 365. In questo modo è possibile archiviare i dati da origini dati di terze parti in Microsoft 365 in modo da poter utilizzare funzionalità di conformità come il blocco legale, la ricerca di contenuto e i criteri di conservazione per gestire i dati di terze parti dell'organizzazione.
ms.openlocfilehash: f2604589fb91d36a8fc4a8d94be88757f198fa58
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822190"
---
# <a name="set-up-a-connector-to-archive-o2-network-data"></a>Configurare un connettore per archiviare i dati di rete O2

Utilizzare un connettore TeleMessage nel Centro conformità Microsoft 365 per importare e archiviare i messaggi del servizio di messaggistica breve (SMS) e le chiamate vocali dalla rete mobile O2. Dopo aver configurato e configurato un connettore, si connette alla rete O2 dell'organizzazione una volta al giorno e importa SMS e chiamate vocali alle cassette postali in Microsoft 365.

Dopo SMS i messaggi e le chiamate vocali vengono archiviati nelle cassette postali degli utenti, è possibile applicare ai dati di rete di O2 le funzionalità di conformità di Microsoft 365, ad esempio conservazione per controversia legale, ricerca contenuto e criteri di conservazione Microsoft 365. Ad esempio, è possibile cercare i messaggi SMS di rete O2 e le chiamate vocali utilizzando Ricerca contenuto o associare la cassetta postale che contiene i dati di rete O2 a un responsabile in un caso Advanced eDiscovery caso. L'utilizzo di un connettore di rete O2 per importare e archiviare i dati in Microsoft 365 può aiutare l'organizzazione a rimanere conforme ai criteri governativi e normativi.

## <a name="overview-of-archiving-o2-network-data"></a>Panoramica dell'archiviazione dei dati di rete O2

Nella panoramica seguente viene illustrato il processo di utilizzo di un connettore per archiviare i dati di rete O2 in Microsoft 365.

![Flusso di lavoro di archiviazione di rete O2](../media/O2NetworkConnectorWorkflow.png)

1. L'organizzazione collabora con TeleMessage e O2 per configurare un connettore di rete O2. Per ulteriori informazioni, vedere [O2 Network Archiver.](https://www.telemessage.com/office365-activation-for-o2-network-archiver)

2. Una volta ogni 24 ore, SMS messaggi e chiamate vocali dalla rete O2 dell'organizzazione vengono copiati nel sito TeleMessage.

3. Il connettore di rete O2 creato nel Centro conformità Microsoft 365 si connette ogni giorno al sito TeleMessage e trasferisce i messaggi e le chiamate vocali di SMS dalle 24 ore precedenti a una posizione Archiviazione di Azure sicura nel cloud Microsoft. Il connettore converte inoltre il contenuto dei messaggi SMS e delle chiamate vocali in un formato di messaggio di posta elettronica.

4. Il connettore importa gli elementi di comunicazione mobile nella cassetta postale di utenti specifici. Una nuova cartella denominata **O2 SMS e Voice Network Archiver** viene creata nella cassetta postale di un utente specifico e gli elementi vengono importati in essa. Il connettore esegue questo mapping utilizzando il valore della proprietà Indirizzo di posta elettronica *dell'utente.* Ogni SMS messaggio e chiamata vocale contiene questa proprietà, che viene popolata con l'indirizzo di posta elettronica di ogni partecipante del messaggio.

   Oltre al mapping automatico degli utenti utilizzando il valore della proprietà Indirizzo di posta elettronica *dell'utente,* è anche possibile definire un mapping personalizzato caricando un file di mapping CSV. Questo file di mapping contiene il numero di telefono cellulare e l Microsoft 365 indirizzo di posta elettronica corrispondente per gli utenti dell'organizzazione. Se si abilita sia il mapping automatico degli utenti che il mapping personalizzato, per ogni elemento O2 il connettore esamina innanzitutto il file di mapping personalizzato. Se non trova un utente Microsoft 365 valido corrispondente al numero di cellulare di un utente, il connettore utilizzerà i valori nella proprietà dell'indirizzo di posta elettronica dell'elemento che sta tentando di importare. Se il connettore non trova un utente Microsoft 365 valido nel file di mapping personalizzato o nella proprietà dell'indirizzo di posta elettronica dell'elemento O2, l'elemento non verrà importato.

## <a name="before-you-set-up-a-connector"></a>Prima di configurare un connettore

Alcuni dei passaggi di implementazione necessari per archiviare i dati di rete di O2 sono esterni a Microsoft 365 e devono essere completati prima di poter creare un connettore nel Centro conformità.

- Ordinare [il servizio O2 Network Archiver da TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365/) e ottenere un account di amministrazione valido per l'organizzazione. Sarà necessario accedere a questo account quando si crea il connettore nel Centro conformità.

- Ottenere l'account di rete O2 e i dettagli di contatto di fatturazione in modo da poter compilare i moduli di onboarding di TeleMessage e ordinare il servizio di archiviazione dei messaggi da O2.

- Registrare tutti gli utenti che richiedono l'archiviazione SMS O2 e Voice Network nell'account TeleMessage. Quando si registrano gli utenti, assicurarsi di usare lo stesso indirizzo di posta elettronica utilizzato per l'account Microsoft 365 account.

- I dipendenti devono disporre di telefoni cellulari di proprietà aziendale e responsabili dell'azienda nella rete mobile O2. L'archiviazione dei messaggi Microsoft 365 non è disponibile per i dispositivi BYOD (Bring Your Own Devices) o di proprietà dei dipendenti.

- All'utente che crea un connettore di rete O2 deve essere assegnato il ruolo Esportazione importazione cassette postali in Exchange Online. Questa operazione è necessaria per aggiungere connettori nella pagina **Connettori** dati nel Centro Microsoft 365 conformità. Per impostazione predefinita, questo ruolo non è assegnato ad alcun gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo Esportazione importazione cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online. In caso contrario, è possibile creare un gruppo di ruoli, assegnare il ruolo Importazione/Esportazione cassette postali e quindi aggiungere gli utenti appropriati come membri. Per ulteriori informazioni, vedere le sezioni [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) o Modify role [groups](/Exchange/permissions-exo/role-groups#modify-role-groups) nell'articolo "Manage role groups in Exchange Online".

- Questo connettore dati è disponibile in GCC nel cloud Microsoft 365 us government. Le applicazioni e i servizi di terze parti possono comportare l'archiviazione, la trasmissione e l'elaborazione dei dati dei clienti dell'organizzazione in sistemi di terze parti esterni all'infrastruttura di Microsoft 365 e pertanto non coperti dagli impegni di conformità e protezione dei dati di Microsoft 365. Microsoft non fa alcuna rappresentazione che utilizzi questo prodotto per connettersi ad applicazioni di terze parti implica che tali applicazioni di terze parti siano conformi a FEDRAMP.

## <a name="create-an-o2-network-connector"></a>Creare un connettore di rete O2

Dopo aver completato i prerequisiti descritti nella sezione precedente, è possibile creare un connettore di rete O2 nel Centro Microsoft 365 conformità. Il connettore utilizza le informazioni fornite per connettersi al sito TeleMessage e trasferire SMS messaggi e chiamate vocali alle caselle delle cassette postali dell'utente corrispondenti in Microsoft 365.

1. Passare a [https://compliance.microsoft.com](https://compliance.microsoft.com/) e quindi fare clic su **Connettori dati** \> **O2 Rete**.

2. Nella pagina **Descrizione prodotto rete O2** fare clic su **Aggiungi connettore**

3. Nella pagina **Condizioni di servizio** fare clic su **Accetta.**

4. Nella pagina **Accesso a TeleMessage,** in Passaggio 3, immettere le informazioni necessarie nelle caselle seguenti e quindi fare clic su **Avanti.**

   - **Nome utente:** Nome utente TeleMessage.

   - **Password:** Password TeleMessage.

5. Dopo aver creato il connettore, è possibile chiudere la finestra popup e passare alla pagina successiva.

6. Nella pagina **Mapping utenti** abilitare il mapping automatico degli utenti e fare clic su **Avanti.** Nel caso in cui sia necessario un mapping personalizzato caricare un file CSV e fare clic su **Avanti.**

7. Rivedere le impostazioni e quindi fare clic **su Fine** per creare il connettore.

8. Passare alla scheda Connettori nella **pagina Connettori dati** per visualizzare l'avanzamento del processo di importazione per il nuovo connettore.

## <a name="known-issues"></a>Problemi noti

- Al momento non è possibile importare allegati o elementi di dimensioni superiori a 10 MB. Il supporto per gli elementi più grandi sarà disponibile in un secondo momento.