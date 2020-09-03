---
title: Controlli della tecnologia Microsoft 365
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
ms.custom:
- seo-marvel-apr2020
description: In questo articolo viene fornita una panoramica degli strumenti e delle tecnologie utilizzate da Microsoft per il controllo della tecnologia in Microsoft 365.
ms.openlocfilehash: 66faac9c045dd9b6f6c0c7ea29ca1570e3ad8e19
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332701"
---
# <a name="microsoft-365-technology-controls"></a>Controlli della tecnologia Microsoft 365 

Microsoft utilizza diversi strumenti e tecnologie per controllare, gestire e verificare l'accesso ai dati dei clienti nei suoi servizi online. Queste informazioni si applicano a Exchange Online, SharePoint Online, archivio protetto e cassetta del cliente, autenticazione a più fattori e altro ancora. Yammer utilizza controlli simili descritti nei [controlli di accesso di Yammer Enterprise](microsoft-365-yammer-enterprise-access-controls.md).

Gli ingegneri di Microsoft 365 hanno accesso a zero in piedi ai dati dei clienti di Microsoft 365. Gli ingegneri devono passare attraverso un processo di approvazione Microsoft prima dell'accesso ai dati dei clienti per le operazioni del servizio. Se il cliente autorizza la funzionalità di archivio protetto dei clienti per Exchange Online e SharePoint Online, l'accesso ai dati dei clienti richiede l'approvazione del cliente. Dopo aver approvato, gli account amministrativi specifici del servizio vengono provisioning di accesso just-in-time per le attività richieste dalla richiesta di servizio.

## <a name="lockbox-and-customer-lockbox"></a>Archivio protetto e archivio protetto dei clienti

Anche se raro, un cliente può richiedere assistenza da Microsoft che espone i contenuti dei clienti a un tecnico Microsoft. Per controllare l'accesso a Exchange Online, Microsoft utilizza un sistema di controllo di accesso denominato archivio protetto. Prima che l'assistente tecnico di Microsoft acceda a qualsiasi sistema o dati di Exchange Online o SharePoint Online, deve inviare una richiesta di accesso tramite archivio protetto. Tutte le richieste di servizio per Exchange Online e SharePoint Online vengono gestite dal sistema dell'archivio protetto. Sia con l'archivio protetto che con l'archivio protetto dei clienti, tutti gli accessi approvati sono rintracciabili con un utente univoco, rendendo gli ingegneri responsabili per la gestione delle informazioni relative ai clienti.

> [!NOTE]
> Exchange Online include tutti i dati Skype for business archiviati nelle cassette postali degli utenti. La copertura Skype for business non include le registrazioni di Skype meeting broadcast o il contenuto caricato nelle riunioni da parte degli utenti. SharePoint Online include OneDrive for business.

L'archivio protetto elabora le richieste per le autorizzazioni che conferiscono agli ingegneri la possibilità di eseguire funzioni operative e amministrative all'interno del servizio. Gli ingegneri inviano richieste tramite archivio protetto e un responsabile di Microsoft deve approvare la richiesta prima che il tecnico possa accedere ai dati dei clienti. Dopo l'approvazione da parte del responsabile, il tecnico ha un accesso limitato a livello di spazio ai dati dei clienti per lavorare sul problema del cliente.

L'archivio protetto dei clienti per Microsoft 365 consente di soddisfare gli obblighi di conformità se sono necessarie procedure per l'autorizzazione di accesso ai dati esplicita. Questo è un requisito per alcuni standard di conformità, ad esempio FedRAMP e HIPAA. L'archivio protetto dei clienti inserisce l'utente nel processo di approvazione dell'archivio protetto e fornisce la possibilità di controllare l'autorizzazione di Microsoft Access al contenuto di Exchange Online o SharePoint Online per le operazioni del servizio.

Nell'istanza rara quando un tecnico del servizio Microsoft ha bisogno dell'accesso ai dati, si concede l'accesso solo ai dati necessari per risolvere il problema e per un periodo di tempo limitato. Se si rifiuta una richiesta di accesso, gli ingegneri Microsoft non possono accedere al contenuto e non saranno in grado di completare le operazioni di servizio. Se si approva la richiesta, gli ingegneri Microsoft dispongono dell'accesso just-in-time al contenuto tramite interfacce di gestione monitorate e vincolate.

Le azioni eseguite dal tecnico del supporto sono registrate per il controllo e sono accessibili tramite l' [API di gestione delle attività di Office 365](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis) e il [Centro sicurezza e conformità](https://protection.office.com/).

>[!NOTE]
> L'archivio protetto dei clienti è disponibile in [Microsoft 365 E5](https://products.office.com/business/office-365-enterprise-e5-business-software) come acquisto di un componente aggiuntivo. Per ulteriori informazioni, vedere [richieste dell'archivio clienti di Microsoft 365](https://support.office.com/article/Office-365-Customer-Lockbox-Requests-36f9cdd1-e64c-421b-a7e4-4a54d16440a2).

## <a name="just-in-time-access"></a>Accesso just-in-Time

Microsoft utilizza il principio di accesso JIT (just-in-Time) per Microsoft 365 per attenuare i rischi di manomissioni delle credenziali e gli attacchi laterali. JIT consente di rimuovere l'accesso amministrativo permanente ai servizi e di sostituire i diritti con la possibilità di elevare i ruoli su richiesta. La rimozione dei diritti di accesso permanente da parte degli amministratori garantisce che le credenziali siano disponibili solo quando sono necessarie e riducono i rischi di furto delle credenziali.

Il modello di accesso JIT richiede agli ingegneri la richiesta di privilegi elevati per un periodo di tempo limitato per l'esecuzione delle mansioni amministrative. Inoltre, gli ingegneri utilizzano account temporanei creati con password complesse generate dal computer e sono stati concessi solo i ruoli che consentono loro di eseguire le attività necessarie. Ad esempio, l'accesso amministrativo concesso dall'archivio protetto è associato al tempo e la quantità di tempo di accesso concessa dipende dal ruolo richiesto. Un tecnico specifica il periodo di tempo necessario per l'accesso alla richiesta al sistema dell'archivio protetto. Il sistema dell'archivio protetto rifiuta le richieste quando il tempo richiesto supera il tempo massimo consentito per l'elevazione. Dopo la scadenza, l'accesso amministrativo viene rimosso e scade l'account temporaneo.

Quando sono autorizzati e approvati per l'accesso, gli ingegneri ricevono una password amministrativa monouso generata dal sistema di autorizzazione. Ogni volta che viene approvata una richiesta di accesso elevato, vengono generate nuove password. La password viene copiata in una cassetta di sicurezza per le password, è separata dalle credenziali del tecnico per l'ambiente aziendale Microsoft ed è valida solo per la sessione di accesso con privilegi elevati approvato.

## <a name="constrained-management-interfaces"></a>Interfacce di gestione vincolate

Gli ingegneri utilizzano due interfacce di gestione per eseguire attività amministrative: Remote Desktop tramite gateway di Servizi terminal protetti (STG) e Remote PowerShell. All'interno di queste interfacce di gestione, i criteri software e i controlli di accesso predispongono limitazioni significative sulle applicazioni eseguite e sui comandi e sui cmdlet disponibili.

I server Microsoft 365 limitano le sessioni simultanee a una sessione per ogni amministratore del team per servizio, per ogni server. STG consentire solo una singola sessione simultanea per gli utenti e non consentire più sessioni. Utilizzando una singola sessione per ogni server, STG consente agli amministratori del team del servizio Microsoft 365 di connettersi contemporaneamente a più server, in modo che gli amministratori possano svolgere efficacemente le proprie mansioni. Gli amministratori del team di servizio non dispongono delle autorizzazioni per gli stessi STG. STG viene utilizzato solo per applicare i requisiti di crittografia e autenticazione a più fattori. Dopo che l'amministratore del team di servizio si è connesso a un server specifico tramite un STG, il server specifico impone un limite di sessione di uno per ogni amministratore.

Le restrizioni di utilizzo e i requisiti di connessione e configurazione per il personale Microsoft 365 sono stabiliti da criteri di gruppo di Active Directory. Questi criteri includono le caratteristiche seguenti:

- STG utilizzare solo la crittografia [FIPS](https://www.microsoft.com/TrustCenter/Compliance/FIPS) 140-2 convalidata.
- Le sessioni STG si disconnettono dopo 30 minuti di inattività.
- Le sessioni STG vengono disattivate automaticamente dopo 24 ore.

Le connessioni a STG richiedono anche l'utilizzo di una smart card fisica e di un account separati dalle credenziali Microsoft Corporate dell'ingegnere. Gli ingegneri sono rilasciati smart card diverse per varie piattaforme e piattaforme di gestione segreti garantiscono l'archiviazione sicura delle credenziali. STG utilizza criteri di gruppo di Active Directory per controllare gli utenti che possono accedere ai server remoti, il numero di sessioni consentite e le impostazioni di timeout di inattività. Ulteriori criteri limitano l'accesso alle applicazioni consentite e limitano l'accesso a Internet.

Oltre all'accesso remoto utilizzando STG appositamente configurati, Exchange Online consente agli utenti con il ruolo di Service Engineer Operations di accedere a determinate funzionalità amministrative nei server di produzione tramite Remote PowerShell. A tale scopo, è necessario che l'utente sia autorizzato per l'accesso in sola lettura (debug) all'ambiente di produzione Microsoft 365. L'escalation dei privilegi è abilitata nello stesso modo in cui è abilitata per STG utilizzando il processo di archivio protetto.

Per l'accesso remoto, ogni datacenter ha un IP virtuale con bilanciamento del carico che funge da singolo punto di accesso. I cmdlet di PowerShell remoti disponibili si basano sul livello di privilegio identificato nell'attestazione di accesso ottenuta durante l'autenticazione. Questi cmdlet forniscono l'unica funzionalità amministrativa accessibile dagli utenti che si connettono utilizzando questo metodo. Remote PowerShell limita l'ambito dei comandi disponibili per il tecnico e si basa sul livello di accesso concesso tramite il processo di archivio protetto. Ad esempio, in Exchange Online, Get-Mailbox potrebbe essere disponibile, ma Set-Mailbox non lo sarebbe.
