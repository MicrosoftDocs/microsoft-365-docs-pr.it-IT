---
title: Responsabilità e ruoli Microsoft Desktop gestiti
description: In questo argomento vengono descritti i ruoli e responsabilità fornite da Microsoft per Microsoft Desktop gestiti.
keywords: Servizio Microsoft Desktop gestiti, Microsoft 365, documentazione
ms.service: m365-md
author: jdeckerms
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 923cde6353e4ff5122317f2c053fef244ee7e1b6
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868920"
---
# <a name="microsoft-managed-desktop-roles-and-responsibilities"></a>Responsabilità e ruoli Microsoft Desktop gestiti


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/admin-access); do not delete.-->
<!-- from Roles and responsibilities -->

Se l'organizzazione è iscritto al desktop gestiti Microsoft, come Microsoft vengono automaticamente? E quali sono le responsabilità dell'organizzazione?

## <a name="microsofts-roles-and-responsibilities"></a>Ruoli e responsabilità di Microsoft

Di seguito sono alcuni ruoli chiave e le responsabilità che dovranno essere fornite all'utente da Microsoft.

Ruolo o responsabilità | Descrizione
--- | ---
Gestione di criteri di MDM | Microsoft verrà applicata criteri MDM in base alle procedure consigliate e prendere in considerazione le richieste per apportare modifiche ai criteri. È inoltre verranno apportate modifiche al tenant di come indicato in [criteri per i dispositivi](../service-description/device-policies.md).
Distribuzione di applicazioni | Microsoft distribuirà applicazioni approvate ai dispositivi Desktop gestiti Microsoft del client utilizzando Intune. Per ulteriori informazioni, vedere [Apps](../get-ready/apps.md). 
Supporto per utenti finali | Microsoft fornisce il supporto degli utenti finali per dispositivi, Windows e Office famiglia di prodotti per tutti gli utenti registrati. 
Supporto per i servizi Microsoft Desktop gestiti | Microsoft fornisce il supporto IT del cliente reparti attraverso un Team di operazioni di Desktop gestiti Microsoft. Il team verrà supporta la risoluzione dei problemi tecnici, modificare le richieste e gestione dei problemi per ambiente Desktop gestito Microsoft del cliente. Per ulteriori informazioni, vedere [ottenere supporto](../service-description/support.md).
Monitoraggio della protezione | Microsoft sarà possibile monitorare i dispositivi Desktop gestiti Microsoft customer utilizzo degli strumenti di analisi di Windows Defender. Se viene rilevata una minaccia da Microsoft gestiti Desktop Security Operations centro (SOC), Microsoft provvederà a darne comunicazione del cliente, isolare il dispositivo e risolvere il problema in modalità remota. Per ulteriori informazioni, vedere [Security](../service-description/security.md).
Aggiornare il monitoraggio e gestione | Microsoft sarà possibile monitorare attivamente dispositivi Desktop gestiti Microsoft cliente per verificare che siano installati gli aggiornamenti più recenti di qualità e funzionalità definizione per Microsoft Windows e Microsoft Office. Per ulteriori informazioni, vedere [modalità di gestione degli aggiornamenti](../service-description/updates.md).
Approvvigionamento dispositivo | Microsoft verrà consegna diretta ordinati dispositivi Desktop gestiti Microsoft per gli utenti finali o punto di distribuzione IT di propria scelta. Per ulteriori informazioni, vedere [dispositivi](../get-started/devices.md).

## <a name="your-roles-and-responsibilities"></a>I ruoli e responsabilità

Di seguito è un ulteriore gruppo di ruoli comuni che non vengono forniti da Microsoft, ma sono necessarie per una corretta distribuzione. Non è esauriente ma tipico per la maggior parte delle organizzazioni. 

Ruolo o reponsibility | Descrizione
--- | ---
Gestione modifica ordini | Microsoft Desktop gestiti comunicherà clienti, in precedenza, quando necessario modifiche da apportare al proprio ambiente Desktop gestito Microsoft. I clienti necessario disporre di proprio processo di gestione delle modifiche e devono disporre di un contatto con Microsoft Desktop gestiti. Il cliente è necessario disporre di risorse per esaminare e approvare le modifiche. Per ulteriori informazioni, vedere [Gestione e monitoraggio](../service-description/operations-and-monitoring.md).  
Gestione delle identità | Creazione di account utente, l'assegnazione di utenti ai gruppi e l'aggiornamento dei metadati. 
Gestione e la configurazione di office 365 | Amministrazione di Exchange Oonline, tra cui:<br>-Amministrazione messaggio di posta elettronica<br>-Configurazione mailbox e regola<br>-Exchange management in locale<br><br>Strumenti di collaborazione, amministrazione di SharePoint server, gestione del dominio, le regole di protezione e le informazioni impostate nel portale di amministrazione di Office 365 (Desktop gestiti Microsoft garantirà le applicazioni di Office vengono distribuite nei dispositivi degli utenti finali ed essere sempre aggiornate). 
Supporto per utenti finali | Il cliente fornirà il supporto degli utenti finali per: <br>-On l'infrastruttura del sito: tutti la connettività di rete e internet, VPN dell'infrastruttura e la configurazione client, apparecchiature sala conferenze locali, stampanti, server proxy e configurazione dei firewall.<br><br>-Le risorse cloud livello di azienda: messaggio di posta elettronica, SharePoint, i servizi di collaborazione e altre infrastruttura basata su cloud che riguarda l'impronta di tecnologia a livello aziendale.<br><br>-Applicazioni line-of-business: software personalizzato, software di terze parti 3rd, del software enterprise resource planning (ERP), gli strumenti di progettazione e un valore non specificato in questo documento.
Utente e raggruppamenti di dispositivo | Team addetto alle operazioni di Desktop gestiti Microsoft verrà creare e gestire dispositivo richiesto e gruppi di utenti come parte delle operazioni IT. Il cliente non verrà apportate modifiche a questi raggruppamenti senza prima delle operazioni IT contattare attraverso i canali supportati. Tutti i rilevamento delle modifiche verranno ripristinate.
App | I clienti verranno visualizzato un elenco di applicazioni che desiderano utilizzare all'interno dell'organizzazione (oltre apps inclusa di licenza Microsoft 365). I clienti forniscono inoltre un pacchetto da distribuire (Appx o MSI)<br>Il cliente è responsabile per:<br>-Gestione delle licenze app-indica il tipo corretto e quantità di licenze<br>-Assegnazione app-App assegnazione di gruppi di utenti di Azure Active Directory<br>-Aggiornamenti di app-monitoraggio, creazione del pacchetto e distribuzione degli aggiornamenti di sicurezza e funzionalità di app<br>-Applicazione utente test (accettazione)<br><br>Per ulteriori informazioni, vedere [Apps](../get-ready/apps.md)
Monitoraggio della protezione e una risposta | Se viene rilevato un problema di sicurezza che è compreso nell'ambito di Microsoft Operations Desktop gestiti, è necessario un elenco di contatti preferiti dei clienti in base all'importanza del problema.<br><br>Il cliente è responsabile per la ricerca e risoluzione dei problemi per i dispositivi non - Microsoft Managed Desktop e garantire che il Team di operazioni di Desktop gestiti Microsoft è informato di eventuali problemi che possono influire il servizio.
Supporto per le operazioni | Microsoft Operations Desktop gestiti è necessario che un elenco dei contatti preferiti dei clienti e agli esperti. È necessario queste nel caso si verifichi un evento imprevisto operativa non - Microsoft Managed Desktop. <br><br>Il cliente è responsabile per la ricerca e risoluzione dei problemi per i dispositivi non - Microsoft Managed Desktop e dei servizi e garantire che il Team di operazioni di Desktop gestiti Microsoft è sempre informato.
Infrastruttura di rete, inclusi VPN | Il programma di installazione, configurazione e gestione (inclusa la risoluzione dei problemi e il debug) dell'infrastruttura correlati alle reti e servizi, inclusa la connettività internet, rete controlli, la configurazione del proxy e dell'infrastruttura di connettività remota.<br><br>Per impostazione predefinita, Microsoft Desktop gestiti non specificare oppure è necessario un proxy. Tuttavia, se configurato (nell'hardware o software), è una raccolta di URL che deve disporre dell'autorizzazione per il proxy. Il cliente è responsabile per la risoluzione di eventuali conflitti o incompatibilità a causa di più proxy.<br><br>Per ulteriori informazioni, vedere [Configurazione del Proxy](../get-ready/network.md).
Stampa | Installare, gestire e amministrare stampanti e le code di stampa. Cloud stampa una soluzione consigliata, ma non è obbligatorio. 
Dispositivi mobili | I dispositivi e accessori non forniti da Microsoft Desktop gestiti. Team di operazioni di Desktop gestiti Microsoft supporta solo dispositivo Desktop gestiti Microsoft alloggiamento di espansione e accessori inclusi.




