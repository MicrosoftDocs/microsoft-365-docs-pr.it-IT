---
title: Operazioni di Desktop gestiti Microsoft e monitoraggio
description: ''
keywords: Servizio Microsoft Desktop gestiti, Microsoft 365, documentazione
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 12/18/2018
ms.openlocfilehash: 66945d44df150b5be9af9a9dfe52daa4d7468298
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2019
ms.locfileid: "26868453"
---
# <a name="microsoft-managed-desktop-operations-and-monitoring"></a>Operazioni di Desktop gestiti Microsoft e monitoraggio

<!-- Operations and monitoring: -->


## <a name="change-management"></a>Gestione modifica ordini

In un servizio che offre, il bilanciamento delle responsabilità di, ad esempio la manutenzione dell'hardware e protezione aggiornamenti viene spostato il provider di servizi (Microsoft) anziché il cliente (si). Tuttavia, è necessario assicurarsi che terze parti e software personalizzato continua a funzionare come previsto quando vengono eseguito il rollback degli aggiornamenti.

Per i prodotti in locale, l'organizzazione si presuppone che tutte le responsabilità per la gestione delle modifiche.

### <a name="balance-of-responsibility"></a>Bilanciamento delle responsabilità

Responsabilità | Servizio Microsoft Desktop gestiti | Software client Microsoft 365 | Client e server locali | parte 3 e il software personalizzati
----- | ----- | ----- | ----- | -----
Fornire nuove funzionalità | Microsoft | Microsoft | Entrambi | Cliente
Testare nuove funzionalità per controllo qualità |  Microsoft | Microsoft | Entrambi | Cliente
Comunicare nuove funzionalità | Entrambi | Entrambi | Entrambi | Cliente
Integrare software personalizzato | Entrambi | Entrambi | Cliente | Cliente
Applicare aggiornamenti della sicurezza | Microsoft | Microsoft | Cliente | Cliente
Gestire software di sistema | Microsoft | Microsoft | Cliente | Cliente
Pacchetto di distribuzione | Microsoft | Microsoft | Cliente | Cliente


### <a name="change-process-overview"></a>Panoramica del processo di modifica

Di seguito è riportato un riepilogo di come il processo di modifica è condivisa tra Microsoft e clienti. 



<table>
<tr><th></th><th><p>Il ruolo di Microsoft:</p></th><th><p>Ruolo del cliente:</p></th></tr>
<tr><td>Prima di una modifica</td><td><ul><li>Creare le aspettative sulle modifiche al servizio.</li><li>Inviare notifiche ai clienti 5 giorni in anticipo per le modifiche che richiedono l'intervento dell'amministratore.</li><li>Per le modifiche di emergenza, applicare una riduzione dei rischi prima della notifica.</li></ul></td><td><ul><li>Capire cosa aspettarsi da modifiche e comunicazioni.</li><li>Lettura Microsoft gestiti Desktop centro messaggi regolarmente.</li><li>Rivedere e aggiornare i processi di gestione delle modifiche interni.</li><li>Comprendere e controllare la conformità ai requisiti Desktop gestiti Microsoft. </li><li>Confermare e approvare, quando necessario.</li></ul></td></tr><tr><td>Durante una modifica</td><td><ul><li>Versione e distribuire gli aggiornamenti di sicurezza e non correlati alla sicurezza mensili per i client Windows 10 e Office 365.</li><li>Monitorare i segnali dati e supporto tecnico di code per impatto.</li></ul></td><td><ul><li>Controllo Microsoft Managed Desktop Message Center ed esaminare le informazioni aggiuntive.</li><li>   Eseguire qualsiasi azione necessaria, se applicabile e testare le applicazioni.</li><li>Se si verifica uno scenario di riparazione, creare una richiesta di supporto.</li></ul></td></tr><tr><td>Dopo una modifica</td><td><ul><li>Raccolta commenti e suggerimenti dei clienti per migliorare l'implementazione delle modifiche future.</li><li>Monitorare i segnali dati e supporto tecnico di code per impatto.</li></ul></td><td><ul><li>Collaborare con persone nell'organizzazione di utilizzare la modifica.</li><li>   Esaminare i processi di gestione di modifica e l'adozione le opportunità per migliorare l'efficienza.</li><li>Fornire commenti e suggerimenti specifici nello strumento di amministrazione e suggerimenti.</li><li>Formazione degli utenti per inviare commenti e suggerimenti app specifiche tramite l'Hub di commenti e suggerimenti di Windows e quindi sul pulsante Smile in applicazioni di Office.</li></ul></td></tr>
<table> 






### <a name="change-types"></a>Tipi di modifica

Esistono diversi tipi di modifiche apportate al servizio su base regolare. Il canale di comunicazione per le modifiche e le azioni che i clienti sono responsabili della varia.

Non tutte le modifiche abbiano lo stesso impatto sugli utenti o richiedono azione. Alcuni lavoratori sono pianificati e alcune non pianificati per la loro natura (aggiornamenti non correlati alla sicurezza e la protezione in genere non vengono pianificata). A seconda del tipo di modifica, il canale di comunicazione può variare. Nella tabella seguente sono elencati i tipi di modifiche desiderati per il servizio Microsoft Desktop gestiti.

|   | Funzionalità |   Aggiornamenti non della sicurezza |  Sicurezza
--- | --- | --- | ---
**Tipo di modifica** | -Aggiornamenti delle funzionalità<br>-Nuove funzionalità o applicazioni<br>-Deprecate | Aggiornamenti rapidi del client per problemi | Patch di sicurezza
**Preventivamente** | avviso di 5 giorni per le modifiche che richiedono l'azione |    No, che sono inclusi nella versione mensile   | No, che sono inclusi nella versione mensile 
**Canale di comunicazione** | -Centro messaggi<br>-Avviso messaggio di posta elettronica | -Centro messaggi<br>-Avviso messaggio di posta elettronica | -Centro messaggi<br>-Avviso messaggio di posta elettronica<br>-Bollettino o CVE 
**Richiede un intervento di amministrazione tenant** | A volte |  Raramente |    Raramente 
**Tipo di azione** | Modificare le impostazioni | Comunicare le modifiche agli utenti | Modificare le impostazioni di amministrazione     
**È necessario testare** | Controllare le applicazioni aziendali, inclusi servizi di accesso remoto |  A volte. Verificare le correzioni utilizzando processi o personalizzazioni |   Raramente 
**Esempi di modifica** | -Aggiornamenti delle funzionalità: portale di amministrazione IT semplificato invio ticket di supporto e revisione<br>-Nuove funzionalità o applicazioni: semestrale rilascio di un aggiornamento di funzionalità Windows 10 | Aggiornamenti rapidi basati sui bug segnalati dai clienti |  


## <a name="standard-operating-procedures"></a>Procedure operative standard

Il servizio Microsoft Desktop gestiti viene implementato e gestito da Microsoft nella propria istanza di Microsoft cloud dove si potrebbe effettuare altre attività amministrative. Microsoft si è responsabili della Managed Microsoft Desktop specifici dell'installazione, configurazione e l'utilizzo. 

Per i prodotti in locale, l'organizzazione ha in tutte le responsabilità per la gestione di programma di installazione e configurazione e le attività operative.

Categories |    Microsoft potrà | Verrà cliente
--- | --- | ---
Rete (proxy, controllo dei pacchetti, VPN)  | Consigliare e pianificare con i clienti per ridurre al minimo i rischi per gli utenti aziendali. | : Consente di creare una richiesta di supporto per ottenere informazioni per una modifica alla configurazione pianificate, inclusi i dettagli di configurazione, ambito, sequenza temporale e informazioni pertinenti per Microsoft per la revisione.<br>-Applicare una modifica solo dopo che Microsoft Operations Desktop gestiti ha valutato e consigliato.
Account di servizio |-Implementare, in modo sicuro archiviare e gestire le credenziali.<br> -Comunicare accessi non autorizzati o per l'utilizzo di queste credenziali per il team addetto alle operazioni di protezione. | : Consente di creare una richiesta di supporto per ottenere informazioni per una modifica alla configurazione pianificate, inclusi i dettagli di configurazione, ambito, sequenza temporale e informazioni pertinenti per Microsoft per la revisione.<br>-Applicare una modifica solo dopo che Microsoft Operations Desktop gestiti ha valutato e consigliato.<br>-Non assegna criteri, l'autenticazione a più fattori, accesso condizionato o la distribuzione delle applicazioni per gli account di servizio Desktop gestiti Microsoft.<br>-Non reimpostare la password oppure utilizzare le credenziali.<br>-Se attività sospette sono osservata nei registri di controllo Intune o Azure, correlati a questi account di servizio, aprire una richiesta di supporto Sev C per Microsoft Operations Desktop gestiti.
Gruppi di dispositivi | -Implementare e gestire l'appartenenza di dispositivi all'interno dei gruppi di Desktop gestiti Microsoft.<br>-Utilizzare i gruppi di Desktop gestiti Microsoft per gestire l'assegnazione e il rilascio di configurazione e aggiornamenti ai dispositivi. | : Consente di creare una richiesta di supporto per ottenere informazioni per una modifica alla configurazione pianificate, inclusi i dettagli di configurazione, ambito, sequenza temporale e informazioni pertinenti per Microsoft per la revisione.<br>-Applicare una modifica solo dopo che Microsoft Operations Desktop gestiti ha valutato e consigliato.<br>-Non modificare i membri di un gruppo di Microsoft Desktop gestiti.<br>-Per assegnare i certificati aziendali per i servizi, ad esempio VPN, Hello Windows per la crittografia Business o di posta elettronica o configurazione di profili aziendale Wi-Fi solo utilizzare i gruppi.<br>-In Gestione condivisa esiste, in modo esplicito escludere tutti i gruppi di Desktop gestiti Microsoft durante la distribuzione di Configuration Manager.
Criteri |  -Implementare e gestire i criteri di Desktop gestiti Microsoft che regolano lo stato della configurazione dei dispositivi nel servizio.<br>-Distribuzione degli aggiornamenti, dei criteri o Windows, in modo incrementale utilizzando gruppi di dispositivi.<br> -In modo esplicito escludere assegnazione gruppi non - Microsoft Managed Desktop. | : Consente di creare una richiesta di supporto per ottenere informazioni per una modifica alla configurazione pianificate, inclusi i dettagli di configurazione, ambito, sequenza temporale e informazioni pertinenti per Microsoft per la revisione.<br>-Applicare una modifica solo dopo che Microsoft Operations Desktop gestiti ha valutato e consigliato.<br>-Non modificare o assegnare criteri Desktop gestiti Microsoft a dispositivi o utenti non gestiti dal servizio Microsoft Desktop gestiti.
Windows Defender Advanced Threat Protection | Monitorare e analizzare i dispositivi nell'ambito del servizio Microsoft Desktop gestiti. | : Consente di creare una richiesta di supporto per ottenere informazioni per una modifica alla configurazione pianificate, inclusi i dettagli di configurazione, ambito, sequenza temporale e informazioni pertinenti per Microsoft per la revisione.<br>-Applica una modifica solo dopo che Microsoft Operations Desktop gestiti ha valutato e consigliato
Microsoft Store for Business |  Configurare e gestire il profilo Autopilot Windows per il servizio Microsoft Desktop gestiti. | : Consente di creare una richiesta di supporto per ottenere informazioni per una modifica alla configurazione pianificate, inclusi i dettagli di configurazione, ambito, sequenza temporale e informazioni pertinenti per Microsoft per la revisione.<br>-Applicare una modifica solo dopo che Microsoft Operations Desktop gestiti ha valutato e consigliato.<br>-Non modificare la configurazione del profilo Autopilot di Windows Desktop gestiti Microsoft o aggiunta/rimozione di dispositivi assegnati.
Certificati | | : Consente di creare una richiesta di supporto 60 giorni prima di un certificato senza scadenza, la richiesta di informazioni per una modifica alla configurazione pianificate, inclusi i dettagli di configurazione, ambito, sequenza temporale e informazioni pertinenti per Microsoft per la revisione.<br>-Applicare una modifica solo dopo che Microsoft Operations Desktop gestiti ha valutato e consigliato.<br>: Consente di aggiornare tutti i certificati necessari per configurare i profili di certificati, profili VPN e Wi-Fi profili.




## <a name="device-wipe-with-factory-reset"></a>Cancellazione di dispositivo con ripristino dei valori predefiniti

Team addetto alle operazioni di Desktop gestiti è possibile effettuare una factory reimpostare su dispositivi Desktop gestiti Microsoft gestiti che devono essere ricreata l'immagine. Ciò è utile se è necessario fornire un dispositivo a un dipendente specifico o se un utente ha lasciato l'azienda. 

Esistono alcuni requisiti:

- Amministratore tenant del cliente deve inviare una richiesta di servizio
- È necessario il nome del computer per il dispositivo
- Account utente deve essere di Azure Active Directory prima di eseguire il ripristino

Team addetto alle operazioni di Desktop gestiti verrà:

- Cercare il nome del dispositivo Intune
- Inviare che il ripristino dei valori predefiniti comando al dispositivo

>[!NOTE]
>Non rimuovere l'account utente di Azure Active Directory prima il ripristino dei valori predefiniti. Se l'utente non è in Azure Active Directory, non è possibile inviare Intune che il ripristino dei valori predefiniti comando al dispositivo. 

Il dispositivo verrà avviato nella configurazione guidata e tutte le applicazioni preinstallate e le impostazioni verranno applicate nuovamente. Utente del dispositivo deve fornire insieme iniziale di informazioni nuovamente. 

Quando viene reimpostato il dispositivo, è possibile assegnare a un utente diverso all'interno dell'organizzazione. I dati dell'utente precedente o dati dell'organizzazione non saranno nel dispositivo. L'utente successivo verrà inoltrate attraverso lo stesso processo che ha eseguita la persona precedente con un nuovo dispositivo Desktop gestiti Microsoft.

BitLocker è un componente chiave della protezione dei dati del processo. Grazie alla crittografia BitLocker su dispositivi Desktop gestiti Microsoft, i dati dell'unità rimangano protetto anche dopo l'applicazione di ripristino dei valori predefiniti per il dispositivo. I dati che era nell'unità non sarà disponibili per l'utente successivo del dispositivo. Per ulteriori informazioni, vedere [BitLocker overview](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview).

Per ulteriori informazioni, vedere [Factory reimpostare un dispositivo](https://docs.microsoft.com/intune/devices-wipe#factory-reset-a-device). 
