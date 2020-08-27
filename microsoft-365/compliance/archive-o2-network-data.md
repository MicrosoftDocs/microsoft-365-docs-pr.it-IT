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
ROBOTS: NOINDEX, NOFOLLOW
description: Gli amministratori possono configurare un connettore di telemessaggio per importare e archiviare i dati SMS e MMS dalla rete mobile O2 in Microsoft 365. In questo modo è possibile archiviare i dati provenienti da origini dati di terze parti in Microsoft 365 per poter utilizzare le funzionalità di conformità, come la conservazione legale, la ricerca di contenuto e i criteri di ritenzione per gestire i dati di terze parti dell'organizzazione.
ms.openlocfilehash: 4911e00cf8bcf641ef7f3386ff3297bf082b7f12
ms.sourcegitcommit: b144e8ba1ab0c40fa7e0e8e893b5cb44aa2d8243
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2020
ms.locfileid: "47282660"
---
# <a name="set-up-a-connector-to-archive-o2-network-data-preview"></a>Configurare un connettore per archiviare i dati di rete di O2 (anteprima)

Utilizzare un connettore di invio di messaggi nel centro conformità di Microsoft 365 per importare e archiviare i messaggi SMS e le chiamate vocali dalla rete mobile O2. Dopo aver configurato e configurato un connettore, si connette alla rete O2 dell'organizzazione una volta al giorno e importa le chiamate vocali e SMS alle cassette postali in Microsoft 365.

Dopo che i messaggi SMS e le chiamate vocali vengono archiviati nelle cassette postali degli utenti, è possibile applicare le funzionalità di conformità di Microsoft 365 come il blocco per controversia legale, la ricerca di contenuto e i criteri di conservazione Microsoft 365 ai dati di rete O2 Ad esempio, è possibile cercare i messaggi SMS di rete di O2 e le chiamate vocali tramite la ricerca contenuto o associare la cassetta postale contenente i dati di rete O2 con un custode in un caso di eDiscovery avanzato. L'utilizzo di un connettore di rete O2 per l'importazione e l'archiviazione dei dati in Microsoft 365 può aiutare l'organizzazione a rimanere conforme ai criteri governativi e normativi.

## <a name="overview-of-archiving-o2-network-data"></a>Panoramica dei dati di rete di archiviazione O2

Nella panoramica seguente viene illustrato il processo di utilizzo di un connettore per archiviare i dati di rete di O2 in Microsoft 365.

![Flusso di lavoro di archiviazione di rete O2](../media/O2NetworkConnectorWorkflow.png)

1. L'organizzazione funziona con TeleMessage e O2 per configurare un connettore di rete O2. Per ulteriori informazioni, vedere [O2 Network Archiver](https://www.telemessage.com/office365-activation-for-o2-network-archiver).

2. Una volta ogni 24 ore, i messaggi SMS e le chiamate vocali provenienti dalla rete O2 dell'organizzazione vengono copiati nel sito di telemessaggio.

3. Il connettore di rete O2 creato nel centro conformità Microsoft 365 si connette al sito di telemessaggio ogni giorno e trasferisce i messaggi SMS e le chiamate vocali dalle 24 ore precedenti a una posizione di archiviazione sicura di Azure nel cloud Microsoft. Il connettore converte anche il contenuto dei messaggi SMS e delle chiamate vocali in un formato di messaggio di posta elettronica.

4. Il connettore importa gli elementi di comunicazione per dispositivi mobili nella cassetta postale di utenti specifici. Viene creata una nuova cartella denominata **O2 SMS e Voice Network Archiver** in una cassetta postale di un utente specifico e gli elementi vengono importati. Il connettore esegue questo mapping utilizzando il valore della proprietà dell' *indirizzo di posta elettronica dell'utente* . Ogni messaggio SMS e chiamata vocale contiene questa proprietà, che viene popolata con l'indirizzo di posta elettronica di ogni partecipante del messaggio.

   Oltre a eseguire il mapping automatico degli utenti utilizzando il valore della proprietà dell' *indirizzo di posta elettronica dell'utente* , è anche possibile definire un mapping personalizzato caricando un file di mapping CSV. Questo file di mapping contiene il numero di cellulare e l'indirizzo di posta elettronica Microsoft 365 corrispondente per gli utenti dell'organizzazione. Se si abilitano sia il mapping degli utenti automatici che il mapping personalizzato, per ogni elemento O2 il connettore analizza il file di mapping personalizzato. Se non trova un utente valido di Microsoft 365 che corrisponde al numero di cellulare di un utente, il connettore utilizzerà i valori della proprietà dell'indirizzo di posta elettronica dell'elemento che sta tentando di importare. Se il connettore non trova un utente valido di Microsoft 365 nel file di mapping personalizzato o nella proprietà dell'indirizzo di posta elettronica dell'elemento O2, l'elemento non verrà importato.

## <a name="before-you-begin"></a>Prima di iniziare

Molti dei passaggi di implementazione necessari per archiviare i dati di rete di O2 sono esterni a Microsoft 365 e devono essere completati prima di poter creare un connettore nel centro conformità.

- Ordinare il [servizio di archiviazione di rete O2 da TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365/) e ottenere un account di amministrazione valido per l'organizzazione. Sarà necessario accedere a questo account quando si crea il connettore nel centro conformità.

- Ottenere l'account di rete O2 e i dettagli dei contatti per la fatturazione in modo da poter compilare i moduli di onboarding del telemessaggio e ordinare il servizio di archiviazione dei messaggi da O2.

- Registrare tutti gli utenti che richiedono l'archiviazione di messaggi vocali e di rete vocale O2 nell'account TeleMessage. Quando si registrano gli utenti, assicurarsi di utilizzare lo stesso indirizzo di posta elettronica utilizzato per il proprio account Microsoft 365.

- I dipendenti devono disporre di telefoni cellulari di proprietà aziendale e responsabili per le aziende sulla rete mobile O2. L'archiviazione dei messaggi in Microsoft 365 non è disponibile per i dispositivi di proprietà dei dipendenti o "Bring Your Own Devices (BYOD).

- L'organizzazione deve autorizzare il servizio di importazione di Office 365 per accedere ai dati delle cassette postali nell'organizzazione. Sarà necessario fornire questo consenso quando si crea il connettore. Per acconsentire a questa richiesta, accedere a [Questa pagina](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), accedere con le credenziali di un amministratore globale di Office 365 e quindi accettare la richiesta. È necessario completare questo passaggio prima di poter creare correttamente un connettore di rete O2.

- All'utente che crea un connettore di rete O2 deve essere assegnato il ruolo di importazione/esportazione delle cassette postali in Exchange Online. Questa operazione è necessaria per aggiungere connettori nella pagina **connettori dati** del centro conformità di Microsoft 365. Per impostazione predefinita, questo ruolo non è assegnato ad alcun gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo import export delle cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online. In alternativa, è possibile creare un gruppo di ruoli, assegnare il ruolo di esportazione delle cassette postali e quindi aggiungere gli utenti corretti come membri. Per ulteriori informazioni, vedere la sezione creare gruppi di [ruoli](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) o [modificare gruppi di ruoli](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) nell'articolo "gestire i gruppi di ruoli in Exchange Online".

## <a name="create-an-o2-network-connector"></a>Creare un connettore di rete O2

Dopo aver completato i prerequisiti descritti nella sezione precedente, è possibile creare un connettore di rete O2 nel centro conformità di Microsoft 365. Il connettore utilizza le informazioni fornite per la connessione al sito di telemessaggio e il trasferimento dei messaggi SMS e delle chiamate vocali alle caselle della cassetta postale dell'utente corrispondente in Microsoft 365.

1. Andare a [https://compliance.microsoft.com](https://compliance.microsoft.com/) e quindi fare clic su **connettori dati** di \> **rete O2**.

2. Nella pagina Descrizione prodotto di **rete O2** fare clic su **Aggiungi connettore**

3. Nella pagina **condizioni del servizio** fare clic su **Accetto**.

4. Nella pagina **accesso a telemessaggio** , in passaggio 3, immettere le informazioni necessarie nelle caselle seguenti e quindi fare clic su **Avanti**.

   - **Nome utente:** Nome utente del telemessaggio.

   - **Password:** La password del telemessaggio.

5. Dopo aver creato il connettore, è possibile chiudere la finestra popup e passare alla pagina successiva.

6. Nella pagina **mapping utenti** abilitare il mapping automatico degli utenti e fare clic su **Avanti**. Nel caso in cui sia necessario un mapping personalizzato caricare un file CSV e fare clic su **Avanti**.

7. Fornire il consenso dell'amministratore e quindi fare clic su **Avanti**.

   Per fornire il consenso dell'amministratore, è necessario essere connessi con le credenziali di un amministratore globale di Office 365 e quindi accettare la richiesta di consenso. Se non è stato eseguito l'accesso come amministratore globale, è possibile accedere a [Questa pagina](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) e accedere usando le credenziali di amministratore globale per accettare la richiesta.

8. Esaminare le impostazioni e quindi fare clic su **fine** per creare il connettore.

9. Passare alla scheda Connettori della pagina **connettori dati** per visualizzare lo stato di avanzamento del processo di importazione per il nuovo connettore.

## <a name="known-issues"></a>Problemi noti

- Il connettore non importa alcun elemento di dimensioni superiori a 10 MB.
