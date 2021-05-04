---
title: Configurare un connettore per archiviare i dati di rete TELUS in Microsoft 365
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
description: Gli amministratori possono configurare un connettore TeleMessage per importare e archiviare SMS dati dalla rete TELUS in Microsoft 365. In questo modo è possibile archiviare i dati da origini dati di terze parti in Microsoft 365 in modo da poter utilizzare funzionalità di conformità come il blocco legale, la ricerca di contenuto e i criteri di conservazione per gestire i dati di terze parti dell'organizzazione.
ms.openlocfilehash: 13ac3306d2541f5bc7393152abb6cefb5a11123e
ms.sourcegitcommit: b169f6ad3e44a7fcebf77f43be9eb5edd84ea5ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2021
ms.locfileid: "52077350"
---
# <a name="set-up-a-connector-to-archive-telus-network-data"></a>Configurare un connettore per archiviare i dati di rete TELUS

Utilizzare il connettore TeleMessage nel Centro conformità Microsoft 365 per importare e archiviare i dati del servizio di messaggistica breve (SMS) dalla rete TELUS dell'organizzazione. Dopo aver configurato e configurato un connettore, si connette alla rete TELUS dell'organizzazione una volta al giorno e importa i dati SMS nelle cassette postali in Microsoft 365.

Dopo SMS messaggi archiviati nelle cassette postali degli utenti, è possibile applicare ai dati TELUS funzionalità di conformità Microsoft 365 quali conservazione per controversia legale, ricerca contenuto e Microsoft 365 di conservazione. Ad esempio, è possibile cercare i messaggi teLUS SMS utilizzando Ricerca contenuto o associare la cassetta postale che contiene i dati TELUS a un responsabile in un caso Advanced eDiscovery caso. L'utilizzo di un connettore di rete TELUS per importare e archiviare i dati in Microsoft 365 può aiutare l'organizzazione a rimanere conforme ai criteri governativi e normativi.

## <a name="overview-of-archiving-telus-network-data"></a>Panoramica dell'archiviazione dei dati di rete TELUS

Nella panoramica seguente viene illustrato il processo di utilizzo di un connettore per archiviare i dati di rete TELUS in Microsoft 365.

![Flusso di lavoro di archiviazione di rete TELUS](../media/TelusNetworkConnectorWorkflow.png)

1. L'organizzazione collabora con TeleMessage e TELUS per configurare un connettore di rete TELUS. Per ulteriori informazioni, vedere [TELUS Network Archiver.](https://www.telemessage.com/office365-activation-for-telus-network-archiver/)

2. In tempo reale, SMS messaggi dalla rete TELUS dell'organizzazione vengono copiati nel sito TeleMessage.

3. Il connettore di rete TELUS creato nel Centro conformità Microsoft 365 si connette ogni giorno al sito TeleMessage e trasferisce i messaggi SMS dalle 24 ore precedenti a una posizione Archiviazione di Azure sicura nel cloud Microsoft. Il connettore converte anche il contenuto dei messaggi SMS in un formato di messaggio di posta elettronica.

4. Il connettore importa gli elementi di comunicazione mobile nella cassetta postale di un utente specifico. Una nuova cartella denominata **TELUS SMS Network Archiver** viene creata nella cassetta postale dell'utente specifico e gli elementi vengono importati in essa. Il connettore esegue il mapping utilizzando il valore della proprietà Indirizzo di posta elettronica *dell'utente.* Ogni SMS contiene questa proprietà, che viene popolata con l'indirizzo di posta elettronica di ogni partecipante SMS messaggio.

   Oltre al mapping automatico degli utenti tramite il valore della proprietà Indirizzo di posta elettronica *dell'utente,* è anche possibile implementare il mapping personalizzato caricando un file di mapping CSV. Questo file di mapping contiene il numero di telefono cellulare e l Microsoft 365 indirizzo di posta elettronica corrispondente per gli utenti dell'organizzazione. Se si abilita sia il mapping automatico degli utenti che il mapping personalizzato, per ogni elemento TELUS il connettore esamina innanzitutto il file di mapping personalizzato. Se non trova un utente Microsoft 365 valido corrispondente al numero di cellulare di un utente, il connettore utilizzerà i valori nella proprietà dell'indirizzo di posta elettronica dell'elemento che sta tentando di importare. Se il connettore non trova un utente Microsoft 365 valido nel file di mapping personalizzato o nella proprietà dell'indirizzo di posta elettronica dell'elemento TELUS, l'elemento non verrà importato.

## <a name="before-you-begin"></a>Prima di iniziare

Alcuni dei passaggi di implementazione necessari per archiviare i dati di rete TELUS sono esterni a Microsoft 365 e devono essere completati prima di poter creare un connettore nel Centro conformità.

- Ordinare [il servizio Archivio di rete TELUS da TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365) e ottenere un account di amministrazione valido per l'organizzazione. Sarà necessario accedere a questo account quando si crea il connettore nel Centro conformità.

- Ottieni il tuo account di rete TELUS e i dettagli di contatto di fatturazione in modo da poter compilare i moduli di onboarding di TeleMessage e ordinare il servizio di archiviazione dei messaggi da TELUS.

- Registrare tutti gli utenti che richiedono teLUS SMS Archiviazione di rete nell'account TeleMessage. Quando si registrano gli utenti, assicurarsi di usare lo stesso indirizzo di posta elettronica utilizzato per l'account Microsoft 365 account.

- I dipendenti devono disporre di telefoni cellulari di proprietà aziendale e responsabili dell'azienda nella rete mobileTELUS. L'archiviazione dei Microsoft 365 non è disponibile per i dispositivi BYOD (Bring Your Own Devices) o di proprietà dei dipendenti.

- All'utente che crea un connettore di rete TELUS deve essere assegnato il ruolo Esportazione importazione cassette postali in Exchange Online. Questa operazione è necessaria per aggiungere connettori nella pagina **Connettori** dati nel Centro Microsoft 365 conformità. Per impostazione predefinita, questo ruolo non è assegnato ad alcun gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo Esportazione importazione cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online. In caso contrario, è possibile creare un gruppo di ruoli, assegnare il ruolo Importazione/Esportazione cassette postali e quindi aggiungere gli utenti appropriati come membri. Per ulteriori informazioni, vedere le sezioni [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) o Modify role [groups](/Exchange/permissions-exo/role-groups#modify-role-groups) nell'articolo "Manage role groups in Exchange Online".

## <a name="create-a-telus-network-connector"></a>Creare un connettore di rete TELUS

Dopo aver completato i prerequisiti descritti nella sezione precedente, è possibile creare il connettore di rete TELUS nel Centro Microsoft 365 conformità. Il connettore utilizza le informazioni fornite per connettersi al sito TeleMessage e trasferire SMS messaggi nelle caselle delle cassette postali dell'utente corrispondenti in Microsoft 365.

1. Passare a [https://compliance.microsoft.com](https://compliance.microsoft.com/) e quindi fare clic su **Connettori dati** RETE  >  **TELUS**.

2. Nella pagina **Descrizione prodotto rete TELUS** fare clic su **Aggiungi connettore**

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
