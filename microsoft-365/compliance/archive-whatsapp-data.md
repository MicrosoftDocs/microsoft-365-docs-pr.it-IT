---
title: Configurare un connettore per archiviare i dati di WhatsApp in Microsoft 365
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
description: Gli amministratori possono configurare un connettore TeleMessage per importare e archiviare i dati di WhatsApp in Microsoft 365. In questo modo è possibile archiviare i dati da origini dati di terze parti in Microsoft 365 in modo da poter utilizzare funzionalità di conformità come il blocco legale, la ricerca di contenuto e i criteri di conservazione per gestire i dati di terze parti dell'organizzazione.
ms.openlocfilehash: a8f588e6bbe5180865a2053b055230e4f35ed96a
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822166"
---
# <a name="set-up-a-connector-to-archive-whatsapp-data"></a>Configurare un connettore per archiviare i dati di WhatsApp

Usa il connettore TeleMessage nel Centro conformità Microsoft 365 per importare e archiviare chiamate WhatsApp, chat, allegati, file e messaggi eliminati. Dopo aver configurato e configurato un connettore, il connettore si connette all'account TeleMessage dell'organizzazione una volta al giorno e importa la comunicazione mobile dei dipendenti tramite l'archivio what Telefono sapp di TeleMessage o l'archivio cloud di TeleMessage WhatsApp nelle cassette postali di Microsoft 365.

Dopo aver archiviato i dati di WhatsApp nelle cassette postali degli utenti, è possibile applicare ai dati di WhatsApp funzionalità di conformità Microsoft 365 quali conservazione per controversia legale, Ricerca contenuto e criteri di conservazione Microsoft 365. Ad esempio, è possibile cercare i messaggi WhatsApp utilizzando Ricerca contenuto o associare la cassetta postale che contiene i messaggi WhatsApp a un responsabile in Advanced eDiscovery caso. L'utilizzo di un connettore WhatsApp per importare e archiviare i dati in Microsoft 365 può aiutare l'organizzazione a rimanere conforme ai criteri governativi e normativi.

## <a name="overview-of-archiving-whatsapp-data"></a>Panoramica dell'archiviazione dei dati di WhatsApp

Nella panoramica seguente viene illustrato il processo di utilizzo di un connettore per archiviare i dati di WhatsApp in Microsoft 365.

![Flusso di lavoro di archiviazione WhatsApp](../media/WhatsAppConnectorWorkflow.png)

1. L'organizzazione collabora con TeleMessage per configurare un connettore di Archivio WhatsApp. Per ulteriori informazioni, vedere [WhatsApp Archiver.](https://www.telemessage.com/office365-activation-for-whatsapp-archiver)

2. In tempo reale, i dati WhatsApp dell'organizzazione vengono copiati nel sito TeleMessage.

3. Il connettore WhatsApp creato nel Centro conformità Microsoft 365 si connette ogni giorno al sito TeleMessage e trasferisce i dati di WhatsApp dalle 24 ore precedenti a una posizione Archiviazione di Azure sicura nel cloud Microsoft. Il connettore converte anche i dati WhatsApp del contenuto in un formato di messaggio di posta elettronica.

4. Il connettore importa i dati di WhatsApp nella cassetta postale di un utente specifico. Viene creata una **nuova cartella denominata WhatsApp Archiver** nella cassetta postale dell'utente specifico e gli elementi vengono importati in essa. Il connettore esegue questo mapping utilizzando il valore della proprietà Indirizzo di posta elettronica *dell'utente.* Ogni messaggio WhatsApp contiene questa proprietà, che viene popolata con l'indirizzo di posta elettronica di ogni partecipante del messaggio.

   Oltre al mapping automatico degli utenti tramite il valore della proprietà Indirizzo di posta elettronica *dell'utente,* è anche possibile implementare il mapping personalizzato caricando un file di mapping CSV. Questo file di mapping contiene il numero di telefono cellulare e l Microsoft 365 indirizzo di posta elettronica corrispondente per gli utenti dell'organizzazione. Se si abilita sia il mapping automatico degli utenti che il mapping personalizzato, per ogni elemento WhatsApp il connettore esamina innanzitutto il file di mapping personalizzato. Se non trova un utente Microsoft 365 valido corrispondente al numero di cellulare di un utente, il connettore utilizzerà i valori nella proprietà dell'indirizzo di posta elettronica dell'elemento che sta tentando di importare. Se il connettore non trova un utente Microsoft 365 valido nel file di mapping personalizzato o nella proprietà dell'indirizzo di posta elettronica dell'elemento WhatsApp, l'elemento non verrà importato.

## <a name="before-you-set-up-a-connector"></a>Prima di configurare un connettore

Alcuni dei passaggi di implementazione necessari per archiviare i dati di comunicazione WhatsApp sono esterni a Microsoft 365 e devono essere completati prima di poter creare il connettore nel Centro conformità.

- Ordina il [servizio WhatsApp Archiver da TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365) e ottieni un account di amministrazione valido per la tua organizzazione. Sarà necessario accedere a questo account quando si crea il connettore nel Centro conformità.

- Registrare tutti gli utenti che richiedono l'archiviazione WhatsApp nell'account TeleMessage. Quando si registrano gli utenti, assicurarsi di usare lo stesso indirizzo di posta elettronica utilizzato per l'account Microsoft 365 account.

- Installa [l'app TeleMessage WhatsApp Telefono Archiver](https://www.telemessage.com/mobile-archiver/whatsapp-phone-archiver-2/) sui telefoni cellulari dei dipendenti e attivala. In alternativa, è possibile installare le normali app WhatsApp o WhatsApp Business sui telefoni cellulari dei dipendenti e attivare il servizio WhatsApp Cloud Archiver eseguendo la scansione di un codice QR sul sito Web TeleMessage. Per ulteriori informazioni, vedere [WhatsApp Cloud Archiver.](https://www.telemessage.com/mobile-archiver/whatsapp-archiver/whatsapp-cloud-archiver/)

- All'utente che crea un connettore di rete Verizon deve essere assegnato il ruolo Esportazione importazione cassette postali in Exchange Online. Questa operazione è necessaria per aggiungere connettori nella pagina **Connettori** dati nel Centro Microsoft 365 conformità. Per impostazione predefinita, questo ruolo non è assegnato ad alcun gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo Esportazione importazione cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online. In caso contrario, è possibile creare un gruppo di ruoli, assegnare il ruolo Importazione/Esportazione cassette postali e quindi aggiungere gli utenti appropriati come membri. Per ulteriori informazioni, vedere le sezioni [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) o Modify role [groups](/Exchange/permissions-exo/role-groups#modify-role-groups) nell'articolo "Manage role groups in Exchange Online".

- Questo connettore dati è disponibile in GCC nel cloud Microsoft 365 us government. Le applicazioni e i servizi di terze parti possono comportare l'archiviazione, la trasmissione e l'elaborazione dei dati dei clienti dell'organizzazione in sistemi di terze parti esterni all'infrastruttura di Microsoft 365 e pertanto non coperti dagli impegni di conformità e protezione dei dati di Microsoft 365. Microsoft non fa alcuna rappresentazione che utilizzi questo prodotto per connettersi ad applicazioni di terze parti implica che tali applicazioni di terze parti siano conformi a FEDRAMP.

## <a name="create-a-whatsapp-archiver-connector"></a>Creare un connettore di Archiviazione WhatsApp

Dopo aver completato i prerequisiti descritti nella sezione precedente, è possibile creare il connettore WhatsApp nel Centro Microsoft 365 conformità. Il connettore utilizza le informazioni fornite per connettersi al sito TeleMessage e trasferire i dati di WhatsApp nelle caselle delle cassette postali dell'utente corrispondenti in Microsoft 365.

1. Vai a [https://compliance.microsoft.com](https://compliance.microsoft.com/) e quindi fai clic su **Connettori dati**  >  **WhatsApp Archiver**.

2. Nella pagina **Descrizione prodotto WhatsApp Archiver** fare clic su **Aggiungi connettore**

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
