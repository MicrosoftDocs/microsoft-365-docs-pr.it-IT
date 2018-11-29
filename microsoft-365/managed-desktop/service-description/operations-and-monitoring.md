---
title: Operazioni di Desktop gestiti Microsoft e monitoraggio
description: ''
keywords: Servizio Microsoft Desktop gestiti, Microsoft 365, documentazione
ms.service: m365-md
author: jdeckerms
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 00bdc95c191ce16be219cf0dc251f72eaf054e22
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868453"
---
# <a name="microsoft-managed-desktop-operations-and-monitoring"></a>Operazioni di Desktop gestiti Microsoft e monitoraggio

<!-- Operations and monitoring: -->


## <a name="change-management"></a>Gestione modifica ordini

Microsoft e clienti condividerà la gestione delle modifiche per il servizio Microsoft Desktop gestiti. Responsabilità sono diversi per un servizio in linea e un client o server locale. 

### <a name="change-process-overview"></a>Panoramica del processo di modifica

Di seguito è riportato un riepilogo di come il processo di modifica è condivisa tra Microsoft e clienti. 



<table>
<tr><th></th><th><p>Microsoft potrà:</p></th><th><p>Clienti di:</p></th></tr>
<tr><td>Prima di una modifica</td><td><ul><li>Inviare notifiche ai clienti 5 giorni in anticipo per le modifiche che richiedono l'intervento dell'amministratore.</li><li>Per le modifiche di emergenza, applicare una riduzione dei rischi prima della notifica.</li></ul></td><td><ul><li>Leggere con attenzione posta elettronica di notifica.</li><li>Confermare e approvare, quando necessario.</li></ul></td></tr><tr><td>Durante una modifica</td><td><ul><li>Distribuire modifica per Windows 10 e Office, versione protezione e aggiornamenti non correlati alla sicurezza, in base alle esigenze.</li><li>Monitorare telemetria e le escalation di supporto per eventuali problemi imprevisti.</li></ul></td><td><ul><li>Gestire il processo di gestione di modifica interna.</li><li>Creare una richiesta di supporto, se necessario.</li></ul></td></tr><tr><td>Dopo una modifica</td><td><ul><li>Raccolta commenti e suggerimenti dei clienti per migliorare l'implementazione delle modifiche future.</li><li>Monitorare telemetria e le escalation di supporto per eventuali problemi imprevisti.</li></ul></td><td><ul><li>Leggere con attenzione posta elettronica di notifica.</li><li>Fornire commenti e suggerimenti specifici nello strumento di amministrazione e suggerimenti.</li><li>Formazione degli utenti per inviare commenti e suggerimenti app specifiche tramite l'Hub di commenti e suggerimenti di Windows e quindi sul pulsante Smile in applicazioni di Office.</li></ul></td></tr>
<table> 






### <a name="change-types"></a>Tipi di modifica

Esistono diversi tipi di modifiche apportate al servizio su base regolare. Il canale di comunicazione per le modifiche e le azioni che i clienti sono responsabili della varia.

I seguenti tipi di modifiche possono essere previsto:

Tipo di modifica | Notifica | Azione cliente
--- | --- | ---
Aggiornamenti di funzionalità e nuovi componenti di servizio | Posta elettronica | -Modifica agli utenti di comunicare<br><br> -Opera come richiesto da Microsoft<br><br> -Devono essere presentati entro 48 ore
Protezione aggiornamenti, aggiornamenti mensili sia le impostazioni di base | Posta elettronica, bollettino Microsoft sulla sicurezza o entry vulnerabilità comuni e rischi (CVE) | -Sicurezza mensile aggiornamenti verranno distribuiti mediante la [strategia di gestione di aggiornamento](updates.md).<br><br> -Verranno distribuite impostazioni per ridurre un rischio per l'intera organizzazione per proteggere l'organizzazione. (QUESTO NON VIENE VISUALIZZATA IN MODO CHE SIA UN CLIENTE)
Aggiornamenti di qualità, inclusi correzioni rapide, aggiornamenti dei servizi e non correlati alla sicurezza corretti criteri di base | Posta elettronica | Per avvisare quando necessario.
Aggiornamenti di emergenza: funzioni richieste di aggiornamenti del servizio, configurazione o software a ovviare:<br><br> -Critiche dei rischi di protezione<br><br> -Potenziale perdita di dati<br><br> -L'accesso ai dati di telemetria per la gestione dei dispositivi Desktop gestiti Microsoft | Per avvisare quando necessario.

## <a name="standard-operating-procedures"></a>Procedure operative standard

Questo servizio viene implementato e gestito da Microsoft nell'ambiente di cui è eseguire altre attività amministrative. Microsoft si è responsabili della Managed Microsoft Desktop specifici dell'installazione, configurazione e l'utilizzo. 

Per i prodotti in locale, l'organizzazione ha in tutte le responsabilità per la gestione operativa e le attività di configurazione.

Categories |    Azioni
--- | ---
Account di servizio |  Microsoft potrà:<br><br> -Implementare, in modo sicuro archiviare e gestire le credenziali<br><br> -Comunicare accessi non autorizzati o per l'utilizzo di queste credenziali per il team addetto alle operazioni di protezione<br><br><br><br>Clienti di:<br><br> -Aprire una richiesta di supporto informativo con Microsoft Operations Desktop gestiti quando si pianifica una modifica che potrebbe influire negativamente gli account<br><br> -Non assegna criteri, l'autenticazione a più fattori, accesso condizionato o la distribuzione delle applicazioni per gli account di servizio Desktop gestiti Microsoft<br><br> -Non reimpostare la password o utilizzare le credenziali<br><br> -Aprire una richiesta di supporto Sev C per operazioni di Desktop gestiti Microsoft se attività sospette sono osservata nei registri di controllo Intune o Azure, correlati a questi account di servizio
Gruppi di dispositivi | Microsoft potrà:<br><br> -Implementare e gestire l'appartenenza di dispositivi all'interno dei gruppi di Microsoft Desktop gestiti<br><br> -Utilizzare i gruppi di Desktop gestiti Microsoft per gestire l'assegnazione e il rilascio di configurazione e aggiornamenti ai dispositivi<br><br><br><br>Clienti di:<br><br> -Aprire una richiesta di supporto informativo con Microsoft Operations Desktop gestiti quando si pianifica una modifica che potrebbe influire negativamente i gruppi<br><br> -Non modificare i membri di un gruppo di Microsoft Desktop gestiti<br><br> -Utilizzare solo i gruppi per assegnare i certificati aziendali per i servizi, ad esempio VPN, Hello Windows per la crittografia Business o di posta elettronica o configurazione di profili aziendale Wi-Fi<br><br> -In Gestione condivisa esiste, in modo esplicito escludere tutti i gruppi di Desktop gestiti Microsoft durante la distribuzione di Configuration Manager
Criteri |  Microsoft potrà:<br><br> -Implementare e gestire i criteri di Desktop gestiti Microsoft che regolano lo stato della configurazione di dispositivi all'interno di servizio<br><br> -Distribuzione degli aggiornamenti, dei criteri o Windows, in modo incrementale utilizzando gruppi di dispositivi<br><br> -In modo esplicito escludere assegnazione gruppi non - Microsoft Managed Desktop<br><br><br><br>Verrà cliente:<br><br> -Aprire un ticket di supporto informativo con Microsoft Operations Desktop gestiti quando si pianifica una modifica che potrebbe influire negativamente lo stato della configurazione desiderata dei dispositivi<br><br> -Non modificare o assegnare criteri Desktop gestiti Microsoft a dispositivi o utenti non gestiti dal servizio Microsoft Desktop gestiti
Windows Defender Advanced Threat Protection | Microsoft potrà:<br><br> -Monitorare e analizzare i dispositivi nell'ambito del servizio Microsoft Desktop gestiti<br><br><br><br>Verrà cliente:<br><br> -Aprire un ticket di supporto informativo con Microsoft Operations Desktop gestiti quando si pianifica una modifica che potrebbe influire negativamente le funzionalità di monitoraggio o indagine di Microsoft Managed Desktop Security Operations Center
Microsoft Store for Business |  Microsoft potrà:<br><br> -Configurare e gestire il profilo Autopilot Windows per il servizio Microsoft Desktop gestiti<br><br><br><br>Verrà cliente:<br><br> -Aprire un ticket di supporto informativo con Microsoft Operations Desktop gestiti quando si pianifica una modifica che Apri potrebbero influire l'accesso all'archivio o si modifica il profilo Autopilot di Windows Desktop gestiti Microsoft<br><br> -Non modificare la configurazione del profilo Autopilot di Windows Desktop gestiti Microsoft o aggiunta/rimozione di dispositivi assegnati
Certificati |  Verrà cliente:<br><br> -Aprire un ticket di supporto informativo con Microsoft gestiti Desktop operazioni 60 giorni prima della scadenza di un certificato<br><br> : Consente di aggiornare tutti i certificati necessari per configurare: profili, profili VPN e Wi-Fi profili dei certificati



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
