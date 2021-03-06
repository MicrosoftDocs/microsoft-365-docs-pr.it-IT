---
title: Configurare un connettore per archiviare i dati&T SMS/MMS Network
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
description: Gli amministratori possono configurare un connettore TeleMessage per importare e archiviare SMS mms dalla rete mobile AT&T. In questo modo è possibile archiviare i dati da origini dati di terze parti in Microsoft 365 in modo da poter utilizzare funzionalità di conformità come il blocco legale, la ricerca di contenuto e i criteri di conservazione per gestire i dati di terze parti dell'organizzazione.
ms.openlocfilehash: 5d07c24a2730a405683e064f76c5b95a219dcb2a
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822058"
---
# <a name="set-up-a-connector-to-archive-att-smsmms-data"></a>Configurare un connettore per archiviare i dati AT&T SMS/MMS

Utilizzare un connettore TeleMessage nel centro Microsoft 365 conformità per importare e archiviare i dati SMS MMS da AT&T Mobile Network. Dopo aver configurato e configurato un connettore, si connette alla rete AT&T dell'organizzazione una volta al giorno e importa i dati di SMS e MMS nelle cassette postali in Microsoft 365.

Dopo l'archiviazione dei messaggi SMS e MMS nelle cassette postali degli utenti, è possibile applicare funzionalità di conformità di Microsoft 365, ad esempio conservazione per controversia legale, Ricerca contenuto e criteri di conservazione Microsoft 365 ai dati di at&T Network. Ad esempio, è possibile cercare i dati di rete AT&T utilizzando Ricerca contenuto o associare la cassetta postale che contiene i dati del connettore di rete AT&T a un responsabile in un caso Advanced eDiscovery. L'utilizzo di un connettore di rete AT&T per importare e archiviare i dati in Microsoft 365 può aiutare l'organizzazione a rimanere conforme ai criteri governativi e normativi.

## <a name="overview-of-archiving-att-network-data"></a>Panoramica dell'archiviazione dei dati di&T

Nella panoramica seguente viene illustrato il processo di utilizzo di un connettore per archiviare i dati di at&T Network in Microsoft 365.

![Flusso di lavoro di archiviazione di rete ATT](../media/ATTNetworkConnectorWorkflow.png)

1. L'organizzazione collabora con TeleMessage per configurare un connettore at&T Network. Per informazioni, vedere [AT&T Network Archiver](https://www.telemessage.com/office365-activation-for-atnt-network-archiver/).

2. In tempo reale, SMS messaggi MMS dalla rete AT&T dell'organizzazione vengono copiati nel sito TeleMessage.

3. Il connettore di rete AT&T creato nel Centro conformità Microsoft 365 si connette ogni giorno al sito TeleMessage e trasferisce i messaggi SMS e MMS dalle 24 ore precedenti a una posizione Archiviazione di Azure sicura nel cloud Microsoft. Il connettore converte anche il contenuto dei messaggi SMS MMS in un formato di messaggio di posta elettronica.

4. Il connettore importa gli elementi di comunicazione mobile nella cassetta postale di utenti specifici. Nella cassetta postale dell'utente viene creata una nuova cartella denominata **AT&T SMS/MMS Network Archiver** e gli elementi vengono importati in essa. Il connettore esegue questo mapping utilizzando il valore della proprietà Indirizzo di posta elettronica *dell'utente.* Ogni SMS e mms contiene questa proprietà, che viene popolata con l'indirizzo di posta elettronica di ogni partecipante del messaggio.
 
   Oltre al mapping automatico degli utenti utilizzando il valore della proprietà Indirizzo di posta elettronica *dell'utente,* è anche possibile definire un mapping personalizzato caricando un file di mapping CSV. Questo file di mapping contiene il numero di telefono cellulare e l Microsoft 365 indirizzo di posta elettronica corrispondente per gli utenti dell'organizzazione. Se si abilita sia il mapping automatico degli utenti che il mapping personalizzato, per ogni elemento di posta elettronica il connettore esamina innanzitutto il file di mapping personalizzato. Se non trova un utente Microsoft 365 valido che corrisponde a un numero di cellulare, il connettore utilizza i valori nella proprietà dell'indirizzo di posta elettronica dell'elemento che sta tentando di importare. Se il connettore non trova un utente Microsoft 365 valido nel file di mapping personalizzato o nella proprietà dell'indirizzo di posta elettronica dell'elemento di posta elettronica, l'elemento non verrà importato.

## <a name="before-you-begin"></a>Prima di iniziare

Alcuni dei passaggi di implementazione necessari per archiviare i dati di at&T Network sono esterni a Microsoft 365 e devono essere completati prima di poter creare il connettore nel Centro conformità.

- Ordinare [il servizio di archiviazione per dispositivi mobili da TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365/) e ottenere un account di amministrazione valido per l'organizzazione. Sarà necessario accedere a questo account quando si crea il connettore nel Centro conformità.

- Ottieni il tuo account AT&T e i dettagli di contatto di fatturazione in modo da poter compilare i moduli di onboarding di TeleMessage e ordinare il servizio di archiviazione dei messaggi da AT&T.

- Registrare tutti gli utenti che richiedono l'archiviazione&T SMS/MMS Network nell'account TeleMessage. Quando si registrano gli utenti, assicurarsi di usare lo stesso indirizzo di posta elettronica utilizzato per l'account Microsoft 365 account.

- I dipendenti devono disporre di telefoni cellulari di proprietà aziendale e responsabili dell'azienda nella rete mobile AT&T. L'archiviazione dei messaggi Microsoft 365 non è disponibile per i dispositivi BYOD (Bring Your Own Devices) o di proprietà dei dipendenti.

- All'utente che crea un connettore di rete AT&T deve essere assegnato il ruolo Esportazione importazione cassette postali in Exchange Online. Questa operazione è necessaria per aggiungere connettori nella pagina **Connettori** dati nel Centro Microsoft 365 conformità. Per impostazione predefinita, questo ruolo non è assegnato ad alcun gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo Esportazione importazione cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online. In caso contrario, è possibile creare un gruppo di ruoli, assegnare il ruolo Importazione/Esportazione cassette postali e quindi aggiungere gli utenti appropriati come membri. Per ulteriori informazioni, vedere le sezioni [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) o Modify role [groups](/Exchange/permissions-exo/role-groups#modify-role-groups) nell'articolo "Manage role groups in Exchange Online".

- Questo connettore dati è disponibile in GCC nel cloud Microsoft 365 us government. Le applicazioni e i servizi di terze parti possono comportare l'archiviazione, la trasmissione e l'elaborazione dei dati dei clienti dell'organizzazione in sistemi di terze parti esterni all'infrastruttura di Microsoft 365 e pertanto non coperti dagli impegni di conformità e protezione dei dati di Microsoft 365. Microsoft non fa alcuna rappresentazione che utilizzi questo prodotto per connettersi ad applicazioni di terze parti implica che tali applicazioni di terze parti siano conformi a FEDRAMP.

## <a name="create-a-att-network-connector"></a>Creare un connettore di&AT

Dopo aver completato i prerequisiti descritti nella sezione precedente, è possibile creare un connettore di rete AT&T nel Centro Microsoft 365 conformità. Il connettore utilizza le informazioni fornite per connettersi al sito TeleMessage e trasferire i messaggi SMS e MMS alle caselle delle cassette postali dell'utente corrispondenti in Microsoft 365.

1. Passare a [https://compliance.microsoft.com](https://compliance.microsoft.com/) e quindi fare clic su **Connettori dati** AT&rete  \  **T**.

2. Nella pagina **at&T Network product** description fare clic su Add **connector**

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
