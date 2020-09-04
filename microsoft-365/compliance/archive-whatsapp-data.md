---
title: Configurare un connettore per l'archiviazione dei dati WhatsApp in Microsoft 365
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
ROBOTS: NOINDEX, NOFOLLOW
description: Gli amministratori possono configurare un connettore di telemessaggio per importare e archiviare i dati di WhatsApp in Microsoft 365. In questo modo è possibile archiviare i dati provenienti da origini dati di terze parti in Microsoft 365 per poter utilizzare le funzionalità di conformità, come la conservazione legale, la ricerca di contenuto e i criteri di ritenzione per gestire i dati di terze parti dell'organizzazione.
ms.openlocfilehash: fbd0e30cf8016da9479d5f1e24715d2e2aaa628c
ms.sourcegitcommit: a6625f76e8f19eebd9353ed70c00d32496ec06eb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2020
ms.locfileid: "47361871"
---
# <a name="set-up-a-connector-to-archive-whatsapp-data-preview"></a>Configurare un connettore per archiviare i dati di WhatsApp (anteprima)

Utilizzare il connettore TeleMessage nel centro conformità di Microsoft 365 per importare e archiviare le chiamate, le chat, gli allegati, i file e i messaggi eliminati di WhatsApp. Dopo aver configurato e configurato un connettore, si connette all'account del telemessaggio dell'organizzazione una volta al giorno e importa la comunicazione mobile dei dipendenti utilizzando l'Archiver TeleMessage WhatsApp Phone o il messaggio TeleMessage WhatsApp cloud Archiver alle cassette postali in Microsoft 365.

Dopo che i dati di WhatsApp sono archiviati nelle cassette postali degli utenti, è possibile applicare le funzionalità di conformità di Microsoft 365, ad esempio il blocco per controversia legale, la ricerca di contenuto e i criteri di conservazione di Microsoft 365. Ad esempio, è possibile cercare i messaggi di WhatsApp usando la ricerca contenuto o associare la cassetta postale che contiene i messaggi di WhatsApp con un custode in un caso avanzato di eDiscovery. L'utilizzo di un connettore WhatsApp per l'importazione e l'archiviazione dei dati in Microsoft 365 può aiutare l'organizzazione a rimanere conforme ai criteri governativi e normativi.

## <a name="overview-of-archiving-whatsapp-data"></a>Panoramica dell'archiviazione dei dati di WhatsApp

Nella panoramica seguente viene illustrato il processo di utilizzo di un connettore per l'archiviazione dei dati WhatsApp in Microsoft 365.

![Flusso di lavoro di archiviazione WhatsApp](../media/WhatsAppConnectorWorkflow.png)

1. L'organizzazione collabora con TeleMessage per configurare un connettore di archiviazione WhatsApp. Per ulteriori informazioni, vedere [WhatsApp Archiver](https://www.telemessage.com/office365-activation-for-whatsapp-archiver).

2. Una volta ogni 24 ore, i dati WhatsApp dell'organizzazione vengono copiati nel sito di telemessaggio.

3. Il connettore WhatsApp creato nel centro conformità di Microsoft 365 si connette al sito di telemessaggio ogni giorno e trasferisce i dati di WhatsApp dalle 24 ore precedenti in una posizione di archiviazione sicura di Azure nel cloud Microsoft. Il connettore converte anche i dati del contenuto WhatsApp in un formato di messaggio di posta elettronica.

4. Il connettore importa i dati di WhatsApp nella cassetta postale di un utente specifico. Viene creata una nuova cartella denominata **WhatsApp Archiver** nella cassetta postale dell'utente specifico e gli elementi vengono importati. Il connettore esegue questo mapping utilizzando il valore della proprietà dell' *indirizzo di posta elettronica dell'utente* . Ogni messaggio WhatsApp contiene questa proprietà, che viene popolata con l'indirizzo di posta elettronica di ogni partecipante del messaggio.

   Oltre a eseguire il mapping automatico degli utenti utilizzando il valore della proprietà dell' *indirizzo di posta elettronica dell'utente* , è inoltre possibile implementare il mapping personalizzato caricando un file di mapping CSV. Questo file di mapping contiene il numero di cellulare e l'indirizzo di posta elettronica Microsoft 365 corrispondente per gli utenti dell'organizzazione. Se si abilitano sia il mapping automatico degli utenti che il mapping personalizzato, per ogni elemento WhatsApp il connettore analizza il file di mapping personalizzato. Se non trova un utente valido di Microsoft 365 che corrisponde al numero di cellulare di un utente, il connettore utilizzerà i valori della proprietà dell'indirizzo di posta elettronica dell'elemento che sta tentando di importare. Se il connettore non trova un utente valido di Microsoft 365 nel file di mapping personalizzato o nella proprietà dell'indirizzo di posta elettronica dell'elemento WhatsApp, l'elemento non verrà importato.

## <a name="before-you-begin"></a>Prima di iniziare

Alcuni dei passaggi di implementazione necessari per archiviare i dati di comunicazione di WhatsApp sono esterni a Microsoft 365 e devono essere completati prima di poter creare il connettore nel centro conformità.

- Ordinare il [servizio di archiviazione WhatsApp da TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365) e ottenere un account di amministrazione valido per l'organizzazione. Sarà necessario accedere a questo account quando si crea il connettore nel centro conformità.

- Registrare tutti gli utenti che richiedono l'archiviazione di WhatsApp nell'account TeleMessage. Quando si registrano gli utenti, assicurarsi di utilizzare lo stesso indirizzo di posta elettronica utilizzato per il proprio account Microsoft 365.

- Installare l'app TeleMessage [WhatsApp Phone Archiver](https://www.telemessage.com/mobile-archiver/whatsapp-phone-archiver-2/) sui telefoni cellulari dei dipendenti e attivarla. In alternativa, è possibile installare le normali app WhatsApp o WhatsApp business sui telefoni cellulari dei dipendenti e attivare il servizio di archiviazione cloud di WhatsApp analizzando un codice QR sul sito Web di telemessaggio. Per ulteriori informazioni, vedere [WhatsApp cloud Archiver](https://www.telemessage.com/mobile-archiver/whatsapp-archiver/whatsapp-cloud-archiver/).

- L'organizzazione deve autorizzare il servizio di importazione di Office 365 per accedere ai dati delle cassette postali nell'organizzazione. Sarà necessario fornire questo consenso quando si crea il connettore. Per acconsentire a questa richiesta, accedere a [Questa pagina](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), accedere con le credenziali di Microsoft 365 Global Admin e quindi accettare la richiesta. È necessario completare questo passaggio prima di poter creare correttamente Verizon Network Connector.

- All'utente che crea un connettore di rete Verizon deve essere assegnato il ruolo di importazione/esportazione delle cassette postali in Exchange Online. Questa operazione è necessaria per aggiungere connettori nella pagina **connettori dati** del centro conformità di Microsoft 365. Per impostazione predefinita, questo ruolo non è assegnato ad alcun gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo import export delle cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online. In alternativa, è possibile creare un gruppo di ruoli, assegnare il ruolo di esportazione delle cassette postali e quindi aggiungere gli utenti corretti come membri. Per ulteriori informazioni, vedere la sezione creare gruppi di [ruoli](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) o [modificare gruppi di ruoli](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) nell'articolo "gestire i gruppi di ruoli in Exchange Online".

## <a name="create-a-whatsapp-archiver-connector"></a>Creare un connettore di archiviazione WhatsApp

Dopo aver completato i prerequisiti descritti nella sezione precedente, è possibile creare il connettore WhatsApp nel centro conformità di Microsoft 365. Il connettore utilizza le informazioni fornite per la connessione al sito di telemessaggio e trasferisce i dati WhatsApp nelle caselle della cassetta postale dell'utente corrispondente in Microsoft 365.

1. Andare a [https://compliance.microsoft.com](https://compliance.microsoft.com/) e quindi fare clic su **connettori dati**  >  **WhatsApp Archiver**.

2. Nella pagina Descrizione prodotto **archiviatore WhatsApp** fare clic su **Aggiungi connettore**

3. Nella pagina **condizioni del servizio** fare clic su **Accetto**.

4. Nella pagina **accesso a telemessaggio** , in passaggio 3, immettere le informazioni necessarie nelle caselle seguenti e quindi fare clic su **Avanti**.

   - **Nome utente:** Nome utente del telemessaggio.

   - **Password:** La password del telemessaggio.

5. Dopo aver creato il connettore, è possibile chiudere la finestra popup e passare alla pagina successiva.

6. Nella pagina **mapping utenti** abilitare il mapping automatico degli utenti e fare clic su **Avanti**. Nel caso in cui sia necessario un mapping personalizzato caricare un file CSV e fare clic su **Avanti**.

7. Fornire il consenso dell'amministratore e quindi fare clic su **Avanti**.

   Per fornire il consenso dell'amministratore, è necessario essere connessi con le credenziali di un amministratore globale di Office 365 e quindi accettare la richiesta di consenso. Se non è stato eseguito l'accesso come amministratore globale, è possibile accedere a [Questa pagina](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) ed eseguire l'accesso con le credenziali di amministratore globale per accettare la richiesta.

8. Esaminare le impostazioni e quindi fare clic su **fine** per creare il connettore.

9. Passare alla scheda Connettori della pagina **connettori dati** per visualizzare lo stato di avanzamento del processo di importazione per il nuovo connettore.

## <a name="known-issues"></a>Problemi noti

- Al momento, non è supportato l'importazione di allegati di dimensioni superiori a 10 MB, ma il supporto per gli elementi di grandi dimensioni sarà disponibile in una data successiva.
