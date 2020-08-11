---
title: Configurare un connettore per l'archiviazione dei dati dall'archivio dei numeri dell'organizzazione TeleMessage
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: Gli amministratori possono configurare un connettore per l'importazione e l'archiviazione dei dati SMS e MMS dall'archiviatore di numeri dell'organizzazione TeleMessage. In questo modo è possibile archiviare i dati provenienti da origini dati di terze parti in Microsoft 365 per poter utilizzare le funzionalità di conformità, come la conservazione legale, la ricerca di contenuto e i criteri di ritenzione per gestire i dati di terze parti dell'organizzazione.
ms.openlocfilehash: 71e1f62b1108a6aa7a02c12ddde69d6abc55bcd9
ms.sourcegitcommit: d39694d7b2c98350b0d568dfd03fa0ef44ed4c1d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/10/2020
ms.locfileid: "46602212"
---
# <a name="set-up-a-connector-to-archive-enterprise-number-data-preview"></a>Configurare un connettore per archiviare i dati dei numeri dell'organizzazione (anteprima)

Utilizzare un connettore di invio di messaggi nel centro conformità di Microsoft 365 per importare e archiviare i messaggi SMS (Short Messaging Service) e MMS (Multimedia Messaging Service), i messaggi di chat, le registrazioni delle chiamate vocali e i log delle chiamate vocali dall'Archivio numeri Enterprise. Dopo aver configurato e configurato un connettore, si connette all'account del telemessaggio dell'organizzazione una volta al giorno e importa i dati di comunicazione per dispositivi mobili dei dipendenti utilizzando l'archiviatore di numeri Enterprise per i messaggi nelle cassette postali in Microsoft 365.

Dopo che i dati del connettore di archiviazione dei numeri Enterprise del telemessaggio sono archiviati nelle cassette postali degli utenti, è possibile applicare le funzionalità di conformità di Microsoft 365, ad esempio il blocco per controversia legale, la ricerca contenuto, l'archiviazione sul posto, il controllo, la conformità alla comunicazione e i criteri di conservazione di Microsoft 365 ai dati di archiviazione Ad esempio, è possibile cercare il numero di telefono dell'organizzazione di messaggi SMS, MMS e chiamate vocali tramite ricerca contenuto o associare la cassetta postale contenente i dati del connettore di archiviazione numeri Enterprise con un custode in un caso di eDiscovery avanzato. L'utilizzo di un connettore Archiver numero Enterprise per l'importazione e l'archiviazione dei dati in Microsoft 365 può aiutare l'organizzazione a rimanere conforme ai criteri governativi e normativi.

## <a name="overview-of-archiving-enterprise-number-data"></a>Panoramica dei dati relativi ai numeri dell'organizzazione di archiviazione

Nella panoramica seguente viene illustrato il processo di utilizzo di un connettore per archiviare i dati di rete dell'organizzazione in Microsoft 365.

![Flusso di lavoro archiviazione numero Enterprise](../media/EnterpriseNumberConnectorWorkflow.png)

1. L'organizzazione collabora con TeleMessage per configurare un connettore di archiviazione dei numeri Enterprise. Per ulteriori informazioni, vedere [qui](https://www.telemessage.com/office365-activation-for-enterprise-number-archiver/).

2. Il connettore di archiviazione dei numeri dell'organizzazione creato nel centro conformità di Microsoft 365 si connette al sito di telemessaggio ogni giorno e trasferisce i messaggi di posta elettronica dalle 24 ore precedenti a un'area di memorizzazione di Azure sicura nel cloud Microsoft.

3. Il connettore importa gli elementi di comunicazione per dispositivi mobili sulla cassetta postale di un utente specifico. Verrà creata una nuova cartella denominata Enterprise Number Archiver nella cassetta postale dell'utente specifico e gli elementi verranno importati. Il connettore esegue il mapping utilizzando il valore della proprietà dell' *indirizzo di posta elettronica dell'utente* . Ogni messaggio di posta elettronica contiene questa proprietà, che viene popolata con l'indirizzo di posta elettronica di ogni partecipante del messaggio di posta elettronica. Oltre a eseguire il mapping automatico degli utenti utilizzando il valore della proprietà dell' *indirizzo di posta elettronica dell'utente* , è anche possibile definire un mapping personalizzato caricando un file di mapping CSV. Questo file di mapping deve contenere il numero di cellulare dell'utente e l'indirizzo della cassetta postale di Microsoft 365 corrispondente per ogni utente. Se si Abilita il mapping automatico degli utenti e si fornisce un mapping personalizzato, per ogni elemento di posta elettronica il connettore osserverà per la prima volta il file di mapping personalizzato. Se non trova un utente valido di Microsoft 365 che corrisponde al numero di cellulare di un utente, il connettore utilizzerà la proprietà dell'indirizzo di posta elettronica dell'utente dell'elemento di posta elettronica. Se il connettore non trova un utente valido di Microsoft 365 nel file di mapping personalizzato o nella proprietà dell' *indirizzo di posta elettronica dell'utente* dell'elemento di posta elettronica, l'elemento non verrà importato.

## <a name="before-you-begin"></a>Prima di iniziare

Molti dei passaggi di implementazione necessari per archiviare i dati del Archiver dei numeri Enterprise sono esterni a Microsoft 365 e devono essere completati prima di poter creare il connettore nel centro conformità.

- Ordinare il [servizio Archiver numero Enterprise da TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365) e ottenere un account di amministrazione valido per l'organizzazione. Sarà necessario accedere a questo account quando si crea il connettore nel centro conformità.

- Registrare tutti gli utenti che richiedono l'archiviazione di rete SMS/MMS dell'organizzazione nell'account TeleMessage. Quando si registrano gli utenti, assicurarsi di utilizzare lo stesso indirizzo di posta elettronica utilizzato per il proprio account Microsoft 365.

- Installare e attivare l'app per il numero di telefono dell'organizzazione TeleMessage sui telefoni cellulari dei dipendenti.

- L'organizzazione deve autorizzare il servizio di importazione di Office 365 per accedere ai dati delle cassette postali nell'organizzazione. Sarà necessario fornire questo consenso quando si crea il connettore. Per acconsentire a questa richiesta, accedere a [Questa pagina](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), accedere con le credenziali di un amministratore globale di Office 365 e quindi accettare la richiesta. È necessario completare questo passaggio prima di poter creare correttamente un connettore di rete Bell.

- All'utente che crea un connettore di archiviazione numeri Enterprise deve essere assegnato il ruolo di importazione/esportazione delle cassette postali in Exchange Online. Questa operazione è necessaria per aggiungere connettori nella pagina **connettori dati** del centro conformità di Microsoft 365. Per impostazione predefinita, questo ruolo non è assegnato ad alcun gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo import export delle cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online. In alternativa, è possibile creare un gruppo di ruoli, assegnare il ruolo di esportazione delle cassette postali e quindi aggiungere gli utenti corretti come membri. Per ulteriori informazioni, vedere la sezione creare gruppi di [ruoli](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) o [modificare gruppi di ruoli](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) nell'articolo "gestire i gruppi di ruoli in Exchange Online".

## <a name="create-an-enterprise-number-archiver-connector"></a>Creare un connettore di archiviazione numeri Enterprise

Dopo aver completato i prerequisiti descritti nella sezione precedente, è possibile creare un connettore di archiviazione dei numeri Enterprise nel centro conformità di Microsoft 365. Il connettore utilizza le informazioni fornite per la connessione al sito di telemessaggio e il trasferimento di SMS, MMS e messaggi vocali alle caselle della cassetta postale dell'utente corrispondente in Microsoft 365.

1. Passare a [https://compliance.microsoft.com](https://compliance.microsoft.com/) e quindi fare clic su **Data Connectors** \> **Enterprise Number Archiver**.

2. Nella pagina Descrizione prodotto **Archiver numero Enterprise** fare clic su **Aggiungi connettore**

3. Nella pagina **condizioni del servizio** fare clic su **Accetto**.

4. Nella pagina **accesso a telemessaggio** , in passaggio 3, immettere le informazioni necessarie nelle caselle seguenti e quindi fare clic su **Avanti**.

   - **Nome utente:** Nome utente del telemessaggio.

   - **Password:** La password del telemessaggio.

5. Dopo aver creato il connettore, è possibile chiudere la finestra popup e passare alla pagina successiva.

6. Nella pagina **mapping utenti** abilitare il mapping automatico degli utenti. Per abilitare il mapping personalizzato, caricare un file CSV che contiene le informazioni di mapping degli utenti e quindi fare clic su **Avanti**.

7. Fornire il consenso dell'amministratore e quindi fare clic su **Avanti**.

   Per fornire il consenso dell'amministratore, è necessario essere connessi con le credenziali di un amministratore globale di Office 365 e quindi accettare la richiesta di consenso. Se non è stato eseguito l'accesso come amministratore globale, è possibile accedere a [Questa pagina](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) e accedere usando le credenziali di amministratore globale per accettare la richiesta.

8. Esaminare le impostazioni e quindi fare clic su **fine** per creare il connettore.

9. Passare alla scheda Connettori della pagina **connettori dati** per visualizzare lo stato di avanzamento del processo di importazione per il nuovo connettore.

## <a name="known-issues"></a>Problemi noti

- Il connettore non importa alcun elemento di dimensioni superiori a 10 MB.
