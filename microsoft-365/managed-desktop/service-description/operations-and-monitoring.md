---
title: Monitoraggio e operazioni di Microsoft Managed Desktop
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, servizi, documentazione
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: 1ddac923849abfa2c912244c5ff987ec885f3d45
ms.sourcegitcommit: 4cbb4ec26f022f5f9d9481f55a8a6ee8406968d2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/01/2020
ms.locfileid: "49527594"
---
# <a name="microsoft-managed-desktop-operations-and-monitoring"></a>Monitoraggio e operazioni di Microsoft Managed Desktop

<!-- Operations and monitoring: -->


## <a name="change-management"></a>Gestione delle modifiche

In un'offerta di servizi, l'equilibrio di responsabilità per operazioni quali la manutenzione dell'hardware e gli aggiornamenti della sicurezza si spostano al provider del servizio (Microsoft) anziché al cliente (amministratore). Tuttavia, è comunque necessario assicurarsi che il software di terze parti e personalizzato continui a funzionare come previsto quando vengono implementati gli aggiornamenti.

Per i prodotti locali, l'organizzazione assume tutte le responsabilità per la gestione delle modifiche.

### <a name="balance-of-responsibility"></a>Equilibrio di responsabilità

Responsabilità | Servizio Microsoft Managed Desktop | Software client Microsoft 365 | Client e server locali | terze parti e software personalizzato
----- | ----- | ----- | ----- | -----
Fornire nuove funzionalità | Microsoft | Microsoft | Sia | Cliente
Testare nuove funzionalità per controllo qualità |  Microsoft | Microsoft | Sia | Cliente
Comunicare nuove funzionalità | Sia | Sia | Sia | Cliente
Integrare software personalizzato | Sia | Sia | Cliente | Cliente
Applicare aggiornamenti della sicurezza | Microsoft | Microsoft | Cliente | Cliente
Gestire software di sistema | Microsoft | Microsoft | Cliente | Cliente
Pacchetto per la distribuzione | Microsoft | Microsoft | Cliente | Cliente


### <a name="change-process-overview"></a>Panoramica del processo di modifica

Di seguito viene illustrato un riepilogo del modo in cui il processo di modifica viene condiviso tra Microsoft e i clienti. 



<table>
<tr><th></th><th><p>Ruolo di Microsoft:</p></th><th><p>Ruolo del cliente:</p></th></tr>
<tr><td>Prima di una modifica</td><td><ul><li>Creare le aspettative sulle modifiche al servizio.</li><li>Notificare ai clienti 5 giorni di anticipo le modifiche che richiedono l'intervento dell'amministratore.</li><li>Per le modifiche apportate alle emergenze, applicare una attenuazione prima della notifica.</li></ul></td><td><ul><li>Capire cosa aspettarsi da modifiche e comunicazioni.</li><li>Leggere regolarmente il centro messaggi di Microsoft Managed Desktop.</li><li>Rivedere e aggiornare i processi di gestione delle modifiche interni.</li><li>Comprendere e verificare la conformità con i requisiti di Microsoft Managed Desktop. </li><li>Riconoscere e approvare, se necessario.</li></ul></td></tr><tr><td>Durante una modifica</td><td><ul><li>Rilasciare e distribuire aggiornamenti mensili per la sicurezza e non relativi alla sicurezza per i client Windows 10 e Office 365.</li><li>Monitorare i segnali dati e le code di supporto per l'impatto.</li></ul></td><td><ul><li>Controllare il centro messaggi di Microsoft Managed Desktop e esaminare eventuali informazioni aggiuntive.</li><li>   Eseguire qualsiasi azione necessaria, se applicabile, e testare le applicazioni.</li><li>Se è presente uno scenario di interruzione/correzione, creare una richiesta di supporto.</li></ul></td></tr><tr><td>Dopo una modifica</td><td><ul><li>Raccogliere i commenti e suggerimenti dei clienti per migliorare l'implementazione delle modifiche future.</li><li>Monitorare i segnali dati e le code di supporto per l'impatto.</li></ul></td><td><ul><li>Collaborare con gli utenti dell'organizzazione per adottarne la modifica.</li><li>   Rivedere i processi di gestione delle modifiche e delle adozioni per opportunità di ottenere efficienze.</li><li>Fornire commenti e suggerimenti generali e commenti specifici nello strumento di feedback di amministratore.</li><li>Addestrare gli utenti a fornire commenti e suggerimenti specifici per l'app utilizzando l'hub feedback di Windows e il pulsante Smile nelle app di Office.</li></ul></td></tr>
<table> 






### <a name="change-types"></a>Tipi di modifica

Esistono diversi tipi di modifiche apportate al servizio su base regolare. Il canale di comunicazione per tali modifiche e le azioni che i clienti sono responsabili variano.

Non tutte le modifiche hanno lo stesso impatto sugli utenti oppure richiedono un intervento. Alcuni sono pianificati e alcuni non pianificati dalla propria natura (gli aggiornamenti di sicurezza e gli aggiornamenti della protezione non sono in genere pianificati). A seconda del tipo di modifica, il canale di comunicazione può variare. Nella tabella seguente sono elencati i tipi di modifiche che è possibile prevedere per il servizio Microsoft Managed Desktop.

|   | Funzionalità |   Aggiornamenti non della sicurezza |  Sicurezza
--- | --- | --- | ---
**Tipo di modifica** | -Aggiornamenti delle funzionalità<br>-Nuove funzionalità o applicazioni<br>-Funzionalità deprecate | Aggiornamenti rapidi del client per problemi | Patch di sicurezza
**Notifiche anticipate** | avviso di 5 giorni per le modifiche che richiedono un'azione |    No, queste sono incluse nella versione mensile   | No, queste sono incluse nella versione mensile 
**Canale di comunicazione** | -Centro messaggi<br>-Avviso di posta elettronica | -Centro messaggi<br>-Avviso di posta elettronica | -Centro messaggi<br>-Avviso di posta elettronica
**Richiede un'azione di amministratore globale** | A volte |  Raramente |    Raramente 
**Tipo di azione** | Modificare le impostazioni | Comunicare le modifiche agli utenti | Modificare le impostazioni di amministrazione     
**Richiede il testing** | Controllare le applicazioni aziendali, compresi i servizi di accesso remoto |  A volte. Verificare le correzioni utilizzando processi o personalizzazioni |   Raramente 
**Esempi di modifiche** | -Funzionalità aggiornamenti: portale di amministrazione IT semplificato invio ticket di supporto e Revisione<br>-Nuove funzionalità o applicazioni: Semi-Annual rilascio di un aggiornamento delle funzionalità di Windows 10 | Aggiornamenti rapidi basati sui bug segnalati dai clienti |  


## <a name="standard-operating-procedures"></a>Procedure operative standard

Il servizio Microsoft Managed Desktop è implementato e gestito da Microsoft nell'istanza di Microsoft Cloud in cui è possibile eseguire altre attività amministrative. Microsoft è l'unico responsabile dell'installazione, della configurazione e dell'operazione specifiche di Microsoft Managed Desktop. 

Per i prodotti locali, l'organizzazione assume tutte le responsabilità per la gestione del programma di installazione e la configurazione e le attività operative.

Categorie |    Microsoft si | La volontà del cliente
--- | --- | ---
Rete (proxy, controllo pacchetti, VPN)  | Consigliare e pianificare ai clienti di ridurre al minimo i rischi per gli utenti aziendali. | -Creare una richiesta di supporto che richiede informazioni per una modifica di configurazione pianificata, inclusi i dettagli di configurazione, l'ambito, la sequenza temporale e altre informazioni pertinenti per la revisione di Microsoft.<br>-Applicare una modifica solo una volta che le operazioni di Microsoft Managed Desktop sono state valutate e consigliate.
Account di servizio |-Implementare, archiviare in modo sicuro e gestire le credenziali.<br> -Comunicare l'accesso non autorizzato o l'utilizzo di queste credenziali al team delle operazioni di sicurezza. | -Creare una richiesta di supporto che richiede informazioni per una modifica di configurazione pianificata, inclusi i dettagli di configurazione, l'ambito, la sequenza temporale e altre informazioni pertinenti per la revisione di Microsoft.<br>-Applicare una modifica solo una volta che le operazioni di Microsoft Managed Desktop sono state valutate e consigliate.<br>-Non assegnare criteri, l'autenticazione a più fattori, l'accesso condizionale o la distribuzione di applicazioni agli account del servizio Microsoft Managed Desktop.<br>-Non reimpostare la password o utilizzare le credenziali.<br>-Aprire una richiesta di supporto per la gestione di Microsoft Managed Desktop se l'attività sospetta è osservata nei registri di controllo di Intune o Azure, in relazione a questi account di servizio.
Gruppi di dispositivi | -Implementare e gestire l'appartenenza ai dispositivi all'interno dei gruppi Microsoft Managed Desktop.<br>-Utilizzare i gruppi Microsoft Managed Desktop per gestire l'assegnazione e la versione di configurazione e gli aggiornamenti ai dispositivi. | -Creare una richiesta di supporto che richiede informazioni per una modifica di configurazione pianificata, inclusi i dettagli di configurazione, l'ambito, la sequenza temporale e altre informazioni pertinenti per la revisione di Microsoft.<br>-Applicare una modifica solo una volta che le operazioni di Microsoft Managed Desktop sono state valutate e consigliate.<br>-Non modificare l'appartenenza di un gruppo di desktop Microsoft gestito.<br>-Utilizzare solo i gruppi per assegnare certificati aziendali per servizi quali VPN, Windows Hello for business o mail Encryption o Corporate Wi-Fi profile Configuration.<br>-Dove esiste la cogestione, escludere esplicitamente tutti i gruppi di desktop gestiti Microsoft quando si distribuisce il client Configuration Manager.
Criteri |  -Implementare e gestire i criteri di Microsoft Managed Desktop che regolano lo stato di configurazione dei dispositivi all'interno del servizio.<br>-Distribuire gli aggiornamenti, i criteri o le finestre, utilizzando in modo incrementale i gruppi di dispositivi.<br> -Escludere esplicitamente i gruppi di desktop gestiti non Microsoft. | -Creare una richiesta di supporto che richiede informazioni per una modifica di configurazione pianificata, inclusi i dettagli di configurazione, l'ambito, la sequenza temporale e altre informazioni pertinenti per la revisione di Microsoft.<br>-Applicare una modifica solo una volta che le operazioni di Microsoft Managed Desktop sono state valutate e consigliate.<br>-Non modificare o assegnare criteri di Microsoft Managed Desktop ai dispositivi o agli utenti non gestiti dal servizio Microsoft Managed Desktop.
Microsoft Defender per endpoint | Monitorare e analizzare i dispositivi nell'ambito del servizio Microsoft Managed Desktop. | -Creare una richiesta di supporto che richiede informazioni per una modifica di configurazione pianificata, inclusi i dettagli di configurazione, l'ambito, la sequenza temporale e altre informazioni pertinenti per la revisione di Microsoft.<br>-Applicare una modifica solo una volta che le operazioni di Microsoft Managed Desktop sono state valutate e consigliate
Microsoft Store per le aziende |  Configurare e gestire il profilo di Windows Autopilot per il servizio Microsoft Managed Desktop. | -Creare una richiesta di supporto che richiede informazioni per una modifica di configurazione pianificata, inclusi i dettagli di configurazione, l'ambito, la sequenza temporale e altre informazioni pertinenti per la revisione di Microsoft.<br>-Applicare una modifica solo una volta che le operazioni di Microsoft Managed Desktop sono state valutate e consigliate.<br>-Non modificare la configurazione del profilo Microsoft Managed Desktop di Windows Autopilot o aggiungere/rimuovere i dispositivi assegnati.
Certificati | | -Creare una richiesta di supporto 60 giorni prima della scadenza di un certificato, richiedendo informazioni per una modifica di configurazione pianificata, inclusi i dettagli di configurazione, l'ambito, la sequenza temporale e altre informazioni pertinenti per la revisione di Microsoft.<br>-Applicare una modifica solo una volta che le operazioni di Microsoft Managed Desktop sono state valutate e consigliate.<br>-Aggiornare tutti i certificati necessari per configurare i profili dei certificati, i profili VPN e i profili di Wi-Fi.




## <a name="device-wipe-with-factory-reset"></a>Wipe del dispositivo con reset di fabbrica

Il team di Microsoft Managed Desktop Operations è in grado di eseguire un ripristino di fabbrica dei dispositivi registrati nel servizio, se necessario. Questa operazione è utile se è necessario assegnare un dispositivo a un dipendente diverso o se un dipendente lascia la propria azienda. 

Sono disponibili alcuni requisiti:

- L'amministratore globale deve inviare una richiesta di servizio.
- Includere il nome del computer del dispositivo nella richiesta.
- L'account utente deve trovarsi in Azure AD prima di reimpostare il dispositivo.

Il team delle operazioni desktop gestite farà quanto segue:

- Cercare il nome del dispositivo in Intune
- Inviare il comando Factory Reset al dispositivo

>[!NOTE]
>Non rimuovere l'account utente da Azure AD prima che il dispositivo venga reimpostato. Se l'utente non è in Azure AD, Intune non è in grado di inviare il comando Factory Reset al dispositivo. 

Il dispositivo verrà avviato nell'"esperienza fuori scatola" e verranno applicate di nuovo tutte le applicazioni e le impostazioni preinstallate. L'utente del dispositivo deve fornire di nuovo le informazioni di configurazione iniziali. 

Quando il dispositivo è stato reimpostato, è possibile assegnarlo a un'altra persona all'interno dell'organizzazione. Nessuno dei dati dell'utente o dati dell'organizzazione precedenti sarà nel dispositivo. L'utente successivo passerà attraverso lo stesso processo eseguito dalla persona precedente con un nuovo dispositivo Microsoft Managed Desktop.

BitLocker è un componente chiave della sicurezza dei dati in questo processo. Con la crittografia BitLocker sui dispositivi Microsoft Managed Desktop, i dati dell'unità rimangono sicuri anche dopo che il dispositivo è stato reimpostato in fabbrica. Tutti i dati presenti nell'unità non saranno disponibili per l'utente successivo del dispositivo. Per ulteriori informazioni, vedere [BitLocker Overview](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview).

Per ulteriori informazioni, vedere [Factory Reset a Device](https://docs.microsoft.com/intune/remote-actions/devices-wipe#factory-reset-a-device). 