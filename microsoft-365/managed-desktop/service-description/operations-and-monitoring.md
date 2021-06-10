---
title: Microsoft Managed Desktop operazioni e monitoraggio
description: Who esegue i vari processi di modifica
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: 3e56066f0b4e63fc9b73bbecf5aaa3180ffd2e4f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920421"
---
# <a name="microsoft-managed-desktop-operations-and-monitoring"></a>Microsoft Managed Desktop operazioni e monitoraggio

<!-- Operations and monitoring: -->


## <a name="change-management"></a>Gestione delle modifiche

In un'offerta di servizi, l'equilibrio di responsabilità per operazioni quali la manutenzione dell'hardware e gli aggiornamenti della sicurezza si spostano al provider del servizio (Microsoft) anziché al cliente (amministratore). Tuttavia, è comunque necessario assicurarsi che il software non Microsoft e personalizzato continui a funzionare come previsto quando vengono evasi gli aggiornamenti.

Per i prodotti locali, l'organizzazione si assume tutte le responsabilità della gestione delle modifiche.

### <a name="balance-of-responsibility"></a>Equilibrio di responsabilità

Responsabilità | Microsoft Managed Desktop servizio | Microsoft 365 software client | Client e server locali | software non Microsoft e personalizzato
----- | ----- | ----- | ----- | -----
Fornire nuove funzionalità | Microsoft | Microsoft | Entrambi | Cliente
Testare nuove funzionalità per controllo qualità |  Microsoft | Microsoft | Entrambi | Cliente
Comunicare nuove funzionalità | Entrambi | Entrambi | Entrambi | Cliente
Integrare software personalizzato | Entrambi | Entrambi | Cliente | Cliente
Applicare aggiornamenti della sicurezza | Microsoft | Microsoft | Cliente | Cliente
Gestire software di sistema | Microsoft | Microsoft | Cliente | Cliente
Pacchetto per la distribuzione | Microsoft | Microsoft | Cliente | Cliente


### <a name="change-process-overview"></a>Panoramica del processo di modifica

Ecco un riepilogo della modalità di condivisione del processo di modifica tra Microsoft e i clienti: 



<table>
<tr><th></th><th><p>Ruolo di Microsoft:</p></th><th><p>Ruolo del cliente:</p></th></tr>
<tr><td>Prima di una modifica</td><td><ul><li>Creare le aspettative sulle modifiche al servizio.</li><li>Informare i clienti con 5 giorni di anticipo per le modifiche che richiedono l'intervento dell'amministratore.</li><li>Per le modifiche di emergenza, applicare una mitigazione prima di notificare.</li></ul></td><td><ul><li>Capire cosa aspettarsi da modifiche e comunicazioni.</li><li>Leggere Microsoft Managed Desktop message center regolarmente.</li><li>Rivedere e aggiornare i processi di gestione delle modifiche interni.</li><li>Comprendere e verificare la conformità ai requisiti Microsoft Managed Desktop sicurezza. </li><li>Confermare e approvare, se necessario.</li></ul></td></tr><tr><td>Durante una modifica</td><td><ul><li>Rilasciare e distribuire aggiornamenti mensili per la sicurezza e non per Windows 10 e Office 365 client.</li><li>Monitorare i segnali di dati e supportare le code per l'impatto.</li></ul></td><td><ul><li>Controllare il Microsoft Managed Desktop messaggi ed esaminare eventuali informazioni aggiuntive.</li><li>   Eseguire qualsiasi azione necessaria, se applicabile, e testare le applicazioni.</li><li>Se si verifica uno scenario di interruzione/correzione, creare una richiesta di supporto.</li></ul></td></tr><tr><td>Dopo una modifica</td><td><ul><li>Raccogliere il feedback dei clienti per migliorare l'implementazione delle modifiche future.</li><li>Monitorare i segnali di dati e supportare le code per l'impatto.</li></ul></td><td><ul><li>Collaborare con gli utenti dell'organizzazione per adottare la modifica.</li><li>   Esaminare i processi di gestione delle modifiche e dell'adozione per trovare opportunità per ottenere efficienza.</li><li>Fornisci feedback generale e feedback specifico nello strumento di feedback dell'amministratore.</li><li>Formare gli utenti a fornire commenti e suggerimenti specifici dell'app Hub di Windows Feedback e il pulsante Smile nelle app Office app.</li></ul></td></tr>
<table> 






### <a name="change-types"></a>Modificare i tipi

Esistono diversi tipi di modifiche che vengono apportate regolarmente al servizio. Il canale di comunicazione per tali modifiche e le azioni di cui si è responsabili variano.

Non tutte le modifiche hanno lo stesso impatto sugli utenti oppure richiedono un intervento. Alcuni sono pianificati e altri non pianificati per natura (gli aggiornamenti non relativi alla sicurezza e gli aggiornamenti della sicurezza in genere non sono pianificati). A seconda del tipo di modifica, il canale di comunicazione può variare. Nella tabella seguente sono elencati i tipi di modifiche previste per il Microsoft Managed Desktop servizio.

|   | Funzionalità |   Aggiornamenti non relativi alla sicurezza |  Sicurezza
--- | --- | --- | ---
**Tipo di modifica** | - Aggiornamenti delle funzionalità<br>- Nuove funzionalità o applicazioni<br>- Funzionalità deprecate | Aggiornamenti rapidi del client per problemi | Aggiornamenti della sicurezza
**Notifiche anticipate** | Avviso di cinque giorni per le modifiche che richiedono un'azione | No, tali modifiche sono incluse nel rilascio mensile    | No, le modifiche sono incluse nel rilascio mensile 
**Canale di comunicazione** | - Centro messaggi<br>- Avviso di posta elettronica | - Centro messaggi<br>- Avviso di posta elettronica | - Centro messaggi<br>- Avviso di posta elettronica
**Richiede un'azione di amministratore globale** | A volte |  Raramente |    Raramente 
**Tipo di azione** | Modificare le impostazioni | Comunicare le modifiche agli utenti | Modificare le impostazioni di amministrazione     
**Richiede test** | Controllare le applicazioni aziendali, inclusi i servizi di accesso remoto |  A volte. Verificare le correzioni utilizzando processi o personalizzazioni |   Raramente 
**Esempi di modifiche** | - Aggiornamenti delle funzionalità: invio e revisione semplificati del ticket di supporto del portale di amministrazione IT<br>- Nuove funzionalità o applicazioni: Semi-Annual rilascio di un aggiornamento Windows 10 funzionalità | Aggiornamenti rapidi basati sui bug segnalati dai clienti |  


## <a name="standard-operating-procedures"></a>Procedure operative standard

Il Microsoft Managed Desktop viene implementato e gestito da Microsoft nell'istanza cloud Microsoft in cui è possibile eseguire altre attività amministrative. Microsoft è l'unico responsabile della Microsoft Managed Desktop, della configurazione e del funzionamento specifici. 

Per i prodotti locali, l'organizzazione si assume tutta la responsabilità della gestione dell'installazione e delle attività di configurazione e operative.

Categorie |    Microsoft | Il cliente
--- | --- | ---
Rete (proxy, ispezione pacchetti, VPN)  | Consigliare e pianificare con i clienti per ridurre al minimo i rischi per gli utenti aziendali. | - Creare una richiesta di supporto che richiede informazioni per una modifica della configurazione pianificata, inclusi i dettagli di configurazione, l'ambito, la sequenza temporale e altri dettagli pertinenti che Microsoft deve esaminare.<br>- Applicare una modifica solo dopo che Microsoft Managed Desktop operations ha valutato e consigliato.
Account di servizio |- Implementare, archiviare e gestire in modo sicuro le credenziali.<br> - Comunicare l'accesso non autorizzato o l'uso di queste credenziali al team delle operazioni di sicurezza. | - Creare una richiesta di supporto che richiede informazioni per una modifica della configurazione pianificata, inclusi i dettagli di configurazione, l'ambito, la sequenza temporale e altri dettagli pertinenti che Microsoft deve esaminare.<br>- Applicare una modifica solo dopo che Microsoft Managed Desktop operations ha valutato e consigliato.<br>- Non assegnare criteri, autenticazione a più fattori, accesso condizionale o distribuzione di applicazioni agli Microsoft Managed Desktop di servizio.<br>- Non reimpostare la password o usare le credenziali.<br>- Aprire una richiesta di supporto sev C per Microsoft Managed Desktop operazioni se vengono osservate attività sospette in Intune o nei log di controllo di Azure, correlati a questi account di servizio.
Gruppi di dispositivi | - Implementare e gestire l'appartenenza dei dispositivi all'interno Microsoft Managed Desktop gruppi.<br>- Usare i Microsoft Managed Desktop per gestire l'assegnazione e il rilascio della configurazione e degli aggiornamenti per i dispositivi. | - Creare una richiesta di supporto che richiede informazioni per una modifica della configurazione pianificata, inclusi i dettagli di configurazione, l'ambito, la sequenza temporale e altri dettagli pertinenti che Microsoft deve esaminare.<br>- Applicare una modifica solo dopo che Microsoft Managed Desktop operations ha valutato e consigliato.<br>- Non modificare l'appartenenza di Microsoft Managed Desktop gruppo.<br>- Usa solo i gruppi per assegnare certificati aziendali per servizi come VPN, Windows Hello for Business o crittografia della posta elettronica o configurazione del profilo Wi-Fi aziendale.<br>- In caso di co-gestione, escludere in modo esplicito Microsoft Managed Desktop gruppi durante la distribuzione del client di Configuration Manager.
Criteri |  - Implementare e gestire i criteri Microsoft Managed Desktop che regolano lo stato di configurazione dei dispositivi all'interno del servizio.<br>- Distribuire gli aggiornamenti, a criteri o Windows, in modo incrementale usando i gruppi di dispositivi.<br> - Escludere esplicitamente la destinazione di gruppi non Microsoft Managed Desktop destinazione. | - Creare una richiesta di supporto che richiede informazioni per una modifica della configurazione pianificata, inclusi i dettagli di configurazione, l'ambito, la sequenza temporale e altri dettagli pertinenti che Microsoft deve esaminare.<br>- Applicare una modifica solo dopo che Microsoft Managed Desktop operations ha valutato e consigliato.<br>- Non modificare o assegnare Microsoft Managed Desktop criteri di sicurezza ai dispositivi o agli utenti non gestiti dal Microsoft Managed Desktop servizio.
Microsoft Defender per endpoint | Monitorare e analizzare i dispositivi nell'ambito del Microsoft Managed Desktop servizio. | - Creare una richiesta di supporto che richiede informazioni per una modifica della configurazione pianificata, inclusi i dettagli di configurazione, l'ambito, la sequenza temporale e altri dettagli pertinenti che Microsoft deve esaminare.<br>- Applicare una modifica solo dopo che Microsoft Managed Desktop operations ha valutato e consigliato
Microsoft Store per le aziende |  Configurare e gestire il Windows Autopilot per il Microsoft Managed Desktop servizio. | - Creare una richiesta di supporto che richiede informazioni per una modifica della configurazione pianificata, inclusi i dettagli di configurazione, l'ambito, la sequenza temporale e altri dettagli pertinenti che Microsoft deve esaminare.<br>- Applicare una modifica solo dopo che Microsoft Managed Desktop operations ha valutato e consigliato.<br>- Non modificare la configurazione del Microsoft Managed Desktop Windows autopilot o aggiungere/rimuovere i dispositivi assegnati.
Certificati | | - Creare una richiesta di supporto 60 giorni prima della scadenza di un certificato, richiedendo informazioni per una modifica della configurazione pianificata, inclusi i dettagli di configurazione, l'ambito, la sequenza temporale e altri dettagli pertinenti da esaminare da Microsoft.<br>- Applicare una modifica solo dopo che Microsoft Managed Desktop operations ha valutato e consigliato.<br>- Aggiornare tutti i certificati necessari per configurare profili di certificato, profili VPN e Wi-Fi certificati.




## <a name="device-wipe-with-factory-reset"></a>Cancellazione del dispositivo con reimpostazione in fabbrica

Il team Microsoft Managed Desktop Operations può eseguire una reimpostazione in fabbrica dei dispositivi registrati nel servizio quando necessario. La reimpostazione è utile se devi fornire un dispositivo a un altro dipendente o se un dipendente lascia l'azienda. 

Esistono alcuni requisiti:

- L'amministratore globale deve inviare una richiesta di servizio.
- Includi il nome del computer del dispositivo nella richiesta.
- L'account utente deve essere in Azure AD prima di reimpostare il dispositivo.

Il team delle operazioni desktop gestite farà quanto segue:

- Cercare il nome del dispositivo in Intune
- Inviare il comando di reimpostazione in fabbrica al dispositivo

>[!NOTE]
>Non rimuovere l'account utente da Azure AD prima che il dispositivo venga reimpostato. Se l'utente non è in Azure AD, Intune non può inviare il comando di reimpostazione in fabbrica al dispositivo. 

Il dispositivo verrà avviato nell'esperienza predefinita e tutte le applicazioni e le impostazioni preinstallate verranno applicate di nuovo. L'utente del dispositivo deve fornire di nuovo le informazioni di configurazione iniziali. 

Quando il dispositivo è stato reimpostato, puoi assegnarlo a un'altra persona dell'organizzazione. Nessuno dei dati dell'utente precedente o dei dati aziendali sarà nel dispositivo. L'utente successivo dovrà passare attraverso lo stesso processo che l'utente precedente ha fatto con un nuovo Microsoft Managed Desktop dispositivo.

BitLocker è un componente chiave della sicurezza dei dati in questo processo. Con BitLocker crittografia nei Microsoft Managed Desktop, i dati nell'unità rimangono sicuri anche dopo la reimpostazione in fabbrica del dispositivo. I dati presenti nell'unità non saranno disponibili per l'utente successivo del dispositivo. Per ulteriori informazioni, vedere [BitLocker panoramica.](/windows/security/information-protection/bitlocker/bitlocker-overview)

Per altre informazioni, vedi [Reimpostazione in fabbrica di un dispositivo.](/intune/remote-actions/devices-wipe#factory-reset-a-device)