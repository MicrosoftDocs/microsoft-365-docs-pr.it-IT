---
title: Responsabilità e ruoli Microsoft Desktop gestiti
description: In questo argomento vengono descritti i ruoli e responsabilità fornite da Microsoft per Microsoft Desktop gestiti.
keywords: Servizio Microsoft Desktop gestiti, Microsoft 365, documentazione
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 96131f7577e0e655067c70bffdd75163ba790adf
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2019
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
Supporto per utenti finali | Microsoft fornisce il supporto degli utenti finali per dispositivi, Windows e Office famiglia di prodotti per tutti gli utenti registrati tramite l'app Guida è preinstallato in tutti i dispositivi Desktop gestiti Microsoft. 
Supporto per i servizi Microsoft Desktop gestiti | Microsoft fornisce il supporto IT del cliente reparti attraverso un Team di operazioni di Desktop gestiti Microsoft. Il team verrà supporta la risoluzione dei problemi tecnici, modificare le richieste e gestione dei problemi per ambiente Desktop gestito Microsoft del cliente. Per ulteriori informazioni, vedere [amministrazione il supporto per Microsoft Desktop gestiti](../working-with-managed-desktop/admin-support.md).
Monitoraggio della protezione | Microsoft sarà possibile monitorare i dispositivi Desktop gestiti Microsoft customer utilizzo degli strumenti di analisi di Windows Defender. Se viene rilevata una minaccia da Microsoft gestiti Desktop Security Operations centro (SOC), Microsoft provvederà a darne comunicazione del cliente, isolare il dispositivo e risolvere il problema in modalità remota. Per ulteriori informazioni, vedere [Security](../service-description/security.md).
Aggiornare il monitoraggio e gestione | Microsoft sarà possibile monitorare attivamente dispositivi Desktop gestiti Microsoft cliente per verificare che siano installati gli aggiornamenti più recenti di qualità e funzionalità di Microsoft Windows e Microsoft Office. Per ulteriori informazioni, vedere [modalità di gestione degli aggiornamenti](../service-description/updates.md).
Utente e raggruppamenti di dispositivo | Team addetto alle operazioni di Desktop gestiti Microsoft verrà creare e gestire dispositivo richiesto e gruppi di utenti come parte delle operazioni IT. Non deve le modifiche apportate a questi gruppi senza l'approvazione dal team addetto alle operazioni di Desktop gestiti Microsoft.

## <a name="your-roles-and-responsibilities"></a>I ruoli e responsabilità

Di seguito è un ulteriore gruppo di ruoli comuni e le responsabilità che non vengono fornite da Microsoft, ma sono necessarie per una corretta distribuzione. Non è esauriente ma è applicabile per la maggior parte delle organizzazioni. Esistono alcune gli elementi della struttura che sia Microsoft che cliente condividere responsibilties. 

Ruolo o responsabilità | Descrizione
--- | ---
Gestione modifica ordini | Microsoft avvisa i clienti, in precedenza, quando necessario modifiche da apportare al proprio ambiente Desktop gestito Microsoft. Il cliente è necessario disporre i propri la gestione delle modifiche del processo e un contatto stabilita con il team di Microsoft Operations Desktop gestiti. Il cliente è necessario anche disporrà delle risorse per esaminare e approvare le modifiche. Per ulteriori informazioni, vedere [Gestione e monitoraggio](../service-description/operations-and-monitoring.md).  
Gestione delle identità | Il cliente è responsabile della creazione di account utente, l'assegnazione di utenti ai gruppi e mantenere aggiornati i metadati. 
Gestione e la configurazione di office 365 | Microsoft è responsabile di garantire le applicazioni di Office da distribuire agli utenti finali e le applicazioni vengono mantenute aggiornate. <br><br> Il cliente è responsabile della gestione dei servizi di Office 365 e i criteri, inclusi Exchange Online responsabilità amministrative:<br>-Amministrazione messaggio di posta elettronica<br>-Configurazione mailbox e regola<br>-Exchange management in locale<br><br>Il cliente anche è responsabile per gli strumenti di collaborazione, amministrazione di SharePoint server, gestione del dominio, le regole di protezione e le informazioni impostate nel portale di amministrazione di Office 365. 
Supporto per utenti finali | Il cliente è compito di fornire supporto per l'utente finale per: <br>-On l'infrastruttura del sito: tutti la connettività di rete e internet, VPN dell'infrastruttura e la configurazione client, apparecchiature sala conferenze locali, stampanti, server proxy e configurazione dei firewall.<br><br>-Le risorse cloud livello di azienda: messaggio di posta elettronica, SharePoint, i servizi di collaborazione e altre infrastruttura basata su cloud che riguarda l'impronta di tecnologia a livello aziendale.<br><br>-Line di opportunità e di tutte le altre società specifiche applicazioni.
App | Microsoft fornisce informazioni aggiuntive sulla distribuzione di applicazioni approvate utilizzando Intune su richiesta.<br><br>Il cliente è responsabile per:<br>-Che fornisce un elenco delle App per la propria organizzazione (all'esterno di applicazioni di Office 365)<br>-Gestione delle licenze app<br>: Con il tipo corretto e la quantità di licenze<br>-Assegnazione app<br>-App assegnazione di gruppi di utenti di Azure Active Directory<br>-Aggiornamenti app<br>– Monitoraggio, la creazione del pacchetto e distribuzione degli aggiornamenti di sicurezza e funzionalità di app<br>-Applicazione utente test (accettazione)<br>-Fornitura di un pacchetto da distribuire appropriato<br><br>Per ulteriori informazioni, vedere [Apps](../get-ready/apps.md)
Monitoraggio della protezione e una risposta | Il cliente è responsabile per la ricerca e risoluzione dei problemi per i dispositivi non - Microsoft Managed Desktop e garantire che il Team di operazioni di Desktop gestiti Microsoft è informato di eventuali problemi che possono influire il servizio.
Supporto per le operazioni | Il cliente è compito di fornire un elenco dei contatti preferiti dei clienti e agli esperti. Microsoft è necessario che questi nel caso si verifichi un evento imprevisto operativa non - Microsoft Managed Desktop. <br><br>È anche responsabile per la ricerca e risoluzione dei problemi per i dispositivi non - Microsoft Managed Desktop e dei servizi e garantire che il Team di operazioni di Desktop gestiti Microsoft è sempre informato cliente.
Infrastruttura di rete, inclusi VPN | Il cliente è responsabile della gestione (inclusa la risoluzione dei problemi e il debug), configurazione e il programma di installazione di tutti i servizi, inclusa la connettività internet e l'infrastruttura correlati alle reti in rete controlli, la configurazione del proxy e remoti infrastruttura di integrazione applicativa.<br><br>Se viene configurato un proxy (in hardware o software), non esiste una raccolta di URL che deve disporre dell'autorizzazione per il proxy. Il cliente è responsabile per la risoluzione di eventuali conflitti o incompatibilità a causa di più proxy.<br><br>Per ulteriori informazioni, vedere [Configurazione del Proxy](../get-ready/network.md).
Stampa | Il cliente è responsabile dell'installazione, gestione e amministrazione di stampanti e le code di stampa. Cloud stampa una soluzione consigliata, ma non è obbligatorio. 




