---
title: Configurare un connettore per l'archiviazione nei dati di rete di&T SMS/MMS
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
description: Gli amministratori possono configurare un connettore di invio di messaggi per importare e archiviare i dati di SMS e MMS dalla rete su&T Mobile. In questo modo è possibile archiviare i dati provenienti da origini dati di terze parti in Microsoft 365 per poter utilizzare le funzionalità di conformità, come la conservazione legale, la ricerca di contenuto e i criteri di ritenzione per gestire i dati di terze parti dell'organizzazione.
ms.openlocfilehash: 809d1d3fa8f043306093a2cd3802c01d054f147a
ms.sourcegitcommit: b144e8ba1ab0c40fa7e0e8e893b5cb44aa2d8243
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2020
ms.locfileid: "47282634"
---
# <a name="set-up-a-connector-to-archive-att-smsmms-data-preview"></a>Configurare un connettore per l'archiviazione in&dati SMS/MMS (Preview)

Utilizzare un connettore di invio di messaggi nel centro conformità di Microsoft 365 per importare e archiviare i dati di SMS e MMS dalla rete mobile&T. Dopo aver configurato e configurato un connettore, si connette alla rete di&T dell'organizzazione una volta al giorno e importa i dati di SMS e MMS nelle cassette postali in Microsoft 365.

Dopo che i messaggi SMS e MMS sono archiviati nelle cassette postali degli utenti, è possibile applicare le funzionalità di conformità di Microsoft 365 come il blocco per controversia legale, la ricerca di contenuto e i criteri di conservazione di Microsoft 365 a&dati di rete T. Ad esempio, è possibile eseguire una ricerca in&i dati di rete T tramite ricerca contenuto o associare la cassetta postale contenente i dati del connettore di rete di&T con un custode in un caso di eDiscovery avanzato. L'utilizzo di un connettore di rete AT&T per l'importazione e l'archiviazione dei dati in Microsoft 365 può aiutare l'organizzazione a rimanere conforme ai criteri governativi e normativi.

## <a name="overview-of-archiving-att-network-data"></a>Panoramica dell'archiviazione in&dati di rete T

Nella panoramica seguente viene illustrato il processo di utilizzo di un connettore per archiviare i dati di rete di&T in Microsoft 365.

![Flusso di lavoro di archiviazione di rete ATT](../media/ATTNetworkConnectorWorkflow.png)

1. L'organizzazione collabora con TeleMessage per configurare un connettore di rete a&T. Per informazioni, vedere [AT&T Network Archiver](https://www.telemessage.com/office365-activation-for-atnt-network-archiver/).

2. Una volta che ogni 24 ore, i messaggi SMS e MMS provenienti dalla rete di&T dell'organizzazione vengono copiati nel sito di telemessaggio.

3. Il connettore di rete AT&T creato nel centro conformità Microsoft 365 si connette al sito di telemessaggio ogni giorno e trasferisce i messaggi SMS e MMS dalle 24 ore precedenti a una posizione di archiviazione sicura di Azure nel cloud Microsoft. Il connettore converte anche il contenuto dei messaggi SMS e MMS in un formato di messaggio di posta elettronica.

4. Il connettore importa gli elementi di comunicazione per dispositivi mobili nella cassetta postale di utenti specifici. Nella cassetta postale dell'utente viene creata una nuova cartella denominata **&T SMS/MMS Network Archiver** e gli elementi verranno importati. Il connettore esegue questo mapping utilizzando il valore della proprietà dell' *indirizzo di posta elettronica dell'utente* . Ogni messaggio SMS e MMS contiene questa proprietà, che viene popolata con l'indirizzo di posta elettronica di ogni partecipante del messaggio.
 
   Oltre a eseguire il mapping automatico degli utenti utilizzando il valore della proprietà dell' *indirizzo di posta elettronica dell'utente* , è anche possibile definire un mapping personalizzato caricando un file di mapping CSV. Questo file di mapping contiene il numero di cellulare e l'indirizzo di posta elettronica Microsoft 365 corrispondente per gli utenti dell'organizzazione. Se si abilitano sia il mapping degli utenti automatici che il mapping personalizzato, per ogni elemento di posta elettronica, il connettore cerca innanzitutto il file di mapping personalizzato. Se non è disponibile un utente valido di Microsoft 365 che corrisponde a un numero di telefono cellulare, il connettore utilizza i valori della proprietà dell'indirizzo di posta elettronica dell'elemento che sta tentando di importare. Se il connettore non trova un utente valido di Microsoft 365 nel file di mapping personalizzato o nella proprietà dell'indirizzo di posta elettronica dell'elemento di posta elettronica, l'elemento non verrà importato.

## <a name="before-you-begin"></a>Prima di iniziare

Molti dei passaggi di implementazione necessari per archiviare i dati di rete di&T sono esterni a Microsoft 365 e devono essere completati prima di poter creare il connettore nel centro conformità.

- Ordinare il [servizio di archiviazione per dispositivi mobili da TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365/) e ottenere un account di amministrazione valido per l'organizzazione. Sarà necessario accedere a questo account quando si crea il connettore nel centro conformità.

- Ottenere il proprio account a&T e i dettagli dei contatti per la fatturazione in modo da poter compilare i moduli di onboarding del telemessaggio e ordinare il servizio di archiviazione dei messaggi da&T.

- Registrare tutti gli utenti che richiedono&T SMS/MMS Network Archiving nell'account TeleMessage. Quando si registrano gli utenti, assicurarsi di utilizzare lo stesso indirizzo di posta elettronica utilizzato per il proprio account Microsoft 365.

- I dipendenti devono disporre di telefoni cellulari di proprietà aziendale e responsabili della società sulla rete mobile di&T. L'archiviazione dei messaggi in Microsoft 365 non è disponibile per i dispositivi di proprietà dei dipendenti o "Bring Your Own Devices (BYOD).

- L'organizzazione deve autorizzare il servizio di importazione di Office 365 per accedere ai dati delle cassette postali nell'organizzazione. Sarà necessario fornire questo consenso quando si crea il connettore. Per acconsentire a questa richiesta, accedere a [Questa pagina](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), accedere con le credenziali di un amministratore globale di Office 365 e quindi accettare la richiesta. È necessario completare questo passaggio prima di poter creare correttamente un connettore di rete di&T.

- All'utente che crea un connettore di rete a&T deve essere assegnato il ruolo di importazione/esportazione delle cassette postali in Exchange Online. Questa operazione è necessaria per aggiungere connettori nella pagina **connettori dati** del centro conformità di Microsoft 365. Per impostazione predefinita, questo ruolo non è assegnato ad alcun gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo import export delle cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online. In alternativa, è possibile creare un gruppo di ruoli, assegnare il ruolo di esportazione delle cassette postali e quindi aggiungere gli utenti corretti come membri. Per ulteriori informazioni, vedere la sezione creare gruppi di [ruoli](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) o [modificare gruppi di ruoli](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) nell'articolo "gestire i gruppi di ruoli in Exchange Online".

## <a name="create-a-att-network-connector"></a>Creare un connettore di rete a&T

Dopo aver completato i prerequisiti descritti nella sezione precedente, è possibile creare un connettore di rete a&T nel centro conformità di Microsoft 365. Il connettore utilizza le informazioni fornite per la connessione al sito di telemessaggio e il trasferimento dei messaggi SMS e MMS nelle caselle della cassetta postale dell'utente corrispondente in Microsoft 365.

1. Andare a [https://compliance.microsoft.com](https://compliance.microsoft.com/) e quindi fare clic su **connettori dati**  \  **in&rete T**.

2. Nella pagina Descrizione **prodotto di rete a&T** fare clic su **Aggiungi connettore**

3. Nella pagina **condizioni del servizio** fare clic su **Accetto**.

4. Nella pagina **accesso a telemessaggio** , in passaggio 3, immettere le informazioni necessarie nelle caselle seguenti e quindi fare clic su **Avanti**.

   - **Nome utente:** Nome utente del telemessaggio.

   - **Password:** La password del telemessaggio.

5. Dopo aver creato il connettore, è possibile chiudere la finestra popup e passare alla pagina successiva.

6. Nella pagina **mapping utenti** abilitare il mapping automatico degli utenti. Per abilitare il mapping personalizzato, caricare un file CSV che contiene le informazioni di mapping degli utenti e quindi fare clic su **Avanti**.

7. Fornire il consenso dell'amministratore e quindi fare clic su **Avanti**.

   Per fornire il consenso dell'amministratore, è necessario essere connessi con le credenziali di un amministratore globale di Office 365 e quindi accettare la richiesta di consenso. Se non è stato eseguito l'accesso come amministratore globale, è possibile accedere a [Questa pagina](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) e accedere usando le credenziali di amministratore globale per accettare la richiesta. 

8. Esaminare le impostazioni e quindi fare clic su **fine** per creare il connettore.

9. Passare alla scheda **connettori** della pagina **connettori dati** del centro conformità per visualizzare lo stato di avanzamento del processo di importazione per il nuovo connettore.

## <a name="known-issues"></a>Problemi noti

- Il connettore non importa alcun elemento di dimensioni superiori a 10 MB.
