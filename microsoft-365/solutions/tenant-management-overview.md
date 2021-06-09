---
title: Gestione tenant per Microsoft 365 per le aziende
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
- m365solution-overview
- tenant-management
ms.custom:
- Ent_Solutions
description: Panoramica della pianificazione, della distribuzione e del funzionamento continuo dei tenant Microsoft 365 tenant.
ms.openlocfilehash: 42bde00fbd4ddc1cf92236f099a22b2260dbb980
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/03/2021
ms.locfileid: "50405679"
---
# <a name="tenant-management-for-microsoft-365-for-enterprise"></a>Gestione tenant per Microsoft 365 per le aziende

La creazione di un percorso per la trasformazione digitale dell'organizzazione con il cloud computing richiede una solida base su cui i dipendenti possono fare affidamento su produttività, collaborazione, prestazioni, privacy, conformità e sicurezza.

La corretta configurazione dei tenant di Microsoft 365 fornisce tale base, lasciando che i dipendenti si concentrino sul lavoro svolto e sul reparto IT per concentrarsi sulle soluzioni end-to-end che forniscono ulteriore valore aziendale. 

Questa soluzione illustra la configurazione di tale base nei passaggi seguenti:

1. Determinare i tenant
2. Ottimizzare la rete
3. Sincronizzare le identità e applicare gli accesso sicuri
4. Eseguire la migrazione Windows dispositivi, Office client e server e dati Office locali
5. Distribuire la gestione di dispositivi e app

Ma prima di tutto, è necessario prendere un momento per comprendere che cos'è un tenant e come appare un tenant che fornisce una solida base.

## <a name="a-microsoft-365-tenant-defined"></a>Un Microsoft 365 tenant definito

Un tenant Microsoft 365 è un'istanza dedicata dei servizi di Microsoft 365 e dei dati dell'organizzazione archiviati in una posizione predefinita specifica, ad esempio Europa o Nord America. Questa posizione viene specificata quando si crea il tenant per l'organizzazione. Ogni Microsoft 365 tenant è distinto, univoco e separato da tutti gli Microsoft 365 tenant. Si crea un tenant Microsoft 365 quando si acquista uno o più prodotti da Microsoft, ad esempio Microsoft 365 E3 o E5, e un set di licenze per ognuno di essi.

Il tenant Microsoft 365 include anche un tenant di Azure Active Directory (Azure AD), che è un'istanza dedicata di Azure AD per gli account utente, i gruppi e altri oggetti. Ogni tenant di Azure AD è distinto, univoco e separato da tutti gli altri tenant di Azure AD. Anche se l'organizzazione può avere più tenant di Azure AD che è possibile configurare con le sottoscrizioni di Azure, i tenant di Microsoft 365 possono usare solo un singolo tenant di Azure AD, quello creato al momento della creazione del tenant. 

Ecco un esempio:

![Un esempio Microsoft 365 tenant con il tenant di Azure AD](../media/tenant-management-overview/tenant-management-example-tenant.png)

*La gestione tenant* è la pianificazione, la distribuzione e il funzionamento continuo dei tenant Microsoft 365 tenant. 

## <a name="attributes-of-a-well-designed-and-operating-tenant"></a>Attributi di un tenant ben progettato e operativo

Oltre al nome e alla posizione corretti per il tenant, sono disponibili altri elementi per pianificare, distribuire e gestire per garantire che le esperienze utente con le app di produttività cloud come Microsoft Teams e Exchange Online siano efficaci, sicure e &mdash; &mdash; performanti.

Ecco gli elementi:

- Si dispone del set corretto di prodotti (sottoscrizioni) e licenze.
  - Il set di prodotti soddisfa le esigenze aziendali, IT e di sicurezza.
  - C'è un numero adeguato di licenze per i dipendenti e cambiamenti previsti nel personale.
- Per la rete:
  - Sono stati configurati i nomi di dominio DNS corretti.
  - Per le reti aziendali, è stato ottimizzato il traffico di rete verso la rete Microsoft per i lavoratori in sede.
  - Il traffico di rete è stato ottimizzato per i lavoratori remoti che utilizzano un client VPN.
- Gli account, i gruppi e altri oggetti di Servizi di dominio Active Directory sono stati sincronizzati.
  - Gli account tenant di Azure AD sono mappati Exchange Online cassette postali con i domini DNS corretti per gli indirizzi di posta elettronica.
  - Agli account utente sono state assegnate le licenze corrette dai prodotti acquistati corretti (ad esempio Microsoft 365 E3 o E5).
- La gestione delle identità e degli accessi è stata configurata.
  - È necessario un accesso utente sicuro con autenticazione a più fattori o senza password.
  - Si dispone di criteri di accesso condizionale che applicano i requisiti di accesso e le restrizioni per livelli di sicurezza più elevati.
- I server Office locali e i relativi dati sono stati migrati nelle app cloud o vengono usati in una configurazione ibrida.
- Si sta eseguendo la gestione dei dispositivi con Intune o Dispositivi mobili di base e sicurezza incorporati Microsoft 365.
  - I dispositivi di proprietà dell'organizzazione vengono registrati e gestiti.
  - Le app per i dispositivi personali vengono gestite.

Ecco un esempio di un tenant Microsoft 365 con tutti questi elementi sul posto.

![Un esempio Microsoft 365 tenant](../media/tenant-management-overview/tenant-management-tenant-config.png)

In questa figura, il tenant Microsoft 365 include:

- Prodotti e licenze per Microsoft 365 E3 ed E5.
- Microsoft 365 di produttività.
- Intune con i dispositivi registrati e i criteri di dispositivi e applicazioni.
- Tenant di Azure AD con account utente sincronizzato (i gruppi e altri oggetti directory non vengono visualizzati), i domini e i criteri di accesso condizionale.

## <a name="tenant-capabilities-for-microsoft-365-for-enterprise"></a>Funzionalità tenant per Microsoft 365 per le aziende

Nelle sezioni e nella tabella seguenti sono elencate le funzionalità principali e le licenze per i passaggi di questa soluzione.

### <a name="tenant"></a>Tenant

| Capacità o funzionalità | Descrizione | Licenze |
|:-------|:-----|:-------|
| Più tenant | Ogni Microsoft 365 tenant è distinto, univoco e separato da tutti gli Microsoft 365 tenant. Con più tenant, esistono restrizioni e considerazioni aggiuntive per la gestione e la fornitura di servizi agli utenti. | Microsoft 365 E3 o E5 | 
| Migrazione delle cassette postali tra tenant | Gli amministratori tenant possono spostare le cassette postali tra tenant con dipendenze minime dell'infrastruttura nei sistemi locali. In questo modo viene rimossa la necessità di eseguire l'offboard e l'onboard delle cassette postali. | Microsoft 365 E3 o E5 | 
| Multi-Geo | Il tenant può archiviare i dati in pausa nelle altre posizioni geografiche del datacenter scelte per soddisfare i requisiti di residenza dei dati. | Microsoft 365 E3 o E5 | 
| Spostare i dati di base in un nuovo data center geo | Poiché Microsoft aggiunge nuovi dati geografici per la capacità e le risorse di calcolo aggiuntive, è possibile richiedere uno spostamento geografico del datacenter per la residenza dei dati in-geo per i dati principali dei clienti. | Microsoft 365 E3 o E5 | 
||||

### <a name="networking"></a>Rete

| Capacità o funzionalità | Descrizione | Licenze |
|:-------|:-----|:-------|
| Informazioni dettagliate sulla rete | Metriche delle prestazioni di rete raccolte dal tenant Microsoft 365 per facilitare la progettazione dei perimetri di rete per le posizioni dell'ufficio. | Microsoft 365 E3 o E5 | 
| Automatizzare gli aggiornamenti degli endpoint | Automatizzare la configurazione e gli aggiornamenti continui per Microsoft 365 endpoint nei file PAC del client e nei dispositivi e servizi di rete. | Microsoft 365 E3 o E5 | 
||||

### <a name="identity"></a>Identità

| Capacità o funzionalità | Descrizione | Licenze |
|:-------|:-----|:-------|
| Sincronizzare Servizi di dominio Active Directory locale con il tenant di Azure AD    | Sfruttare il provider di identità locale per account utente, gruppi e altri oggetti. | Microsoft 365 E3 o E5 |
| MFA applicata con le impostazioni predefinite per la sicurezza   | Proteggere le identità e i dispositivi dalla compromissione richiedendo una seconda forma di autenticazione per gli accessi. Le impostazioni predefinite per la sicurezza richiedono l'autenticazione a più fattori per tutti gli account utente.   | Microsoft 365 E3 o E5 |
| MFA applicata con l'accesso condizionale| Richiedi autenticazione a più fattori in base agli attributi dell'accesso con criteri di accesso condizionale.    | Microsoft 365 E3 o E5 | 
| MFA applicata con l'accesso condizionale basato sul rischio   | Richiedere l'autenticazione a più fattori in base al rischio di accesso dell'utente con Microsoft Defender per identità. | Microsoft 365 E5 o E3 con licenze di Azure AD Premium P2 | 
| Reimpostazione della password self-service    | Consentire agli utenti di reimpostare o sbloccare le password o gli account personali.  | Microsoft 365 E3 o E5 |
||||

### <a name="migration"></a>Migrazione

| Capacità o funzionalità | Descrizione | Licenze |
|:-------|:-----|:-------|
| Eseguire la migrazione a Windows 10 | Eseguire la migrazione dei dispositivi che Windows 7 o Windows 8.1 a Windows 10 Enterprise. | Windows 10 Enterprise licenze incluse con Microsoft 365 E3 o E5 | 
| Eseguire la migrazione a Microsoft 365 Apps for enterprise | Eseguire la Office app client, ad esempio Word e PowerPoint, alle versioni installate dal cloud aggiornate con nuove funzionalità. | Microsoft 365 E3 o E5 | 
| Eseguire la migrazione di dati e server locali a Microsoft 365 | Eseguire la migrazione Exchange cassette postali, SharePoint siti e Skype for Business Online a Microsoft 365 cloud. | Microsoft 365 E3 o E5 | 
||||

### <a name="device-and-app-management"></a>Gestione di dispositivi e app

| Capacità o funzionalità | Descrizione | Licenze |
|:-------|:-----|:-------|
| Microsoft Intune | Un servizio basato su cloud che fornisce la gestione dei dispositivi mobili (MDM) e la gestione delle applicazioni mobili (MAM) per controllare la modalità di utilizzo dell'applicazione dell'organizzazione e dei dispositivi, inclusi telefoni cellulari, tablet e portatili. | Microsoft 365 E3 o E5 | 
| Basic Mobility + Security | Proteggi e gestisci i dispositivi mobili degli utenti come iPhone, iPad, Android e Windows telefoni con questo servizio incorporato.  | Microsoft 365 E3 o E5 | 
||||

## <a name="next-steps"></a>Passaggi successivi

Seguire questa procedura per configurare e gestire i tenant Microsoft 365 utenti.

1. [Determinare i tenant](tenant-management-tenants.md)
2. [Ottimizzare la rete](tenant-management-networking.md)
3. [Sincronizzare le identità e applicare gli accesso sicuri](tenant-management-identity.md)
4. [Eseguire la migrazione dei dati e dei server Office locali](tenant-management-migration.md)
5. [Distribuire la gestione di dispositivi e app](tenant-management-device-management.md)

[![Passaggi per distribuire e gestire un tenant Microsoft 365](../media/tenant-management-overview/tenant-management-step-grid.png)](tenant-management-tenants.md)

Ogni passaggio descrive le opzioni di distribuzione, riepiloga i risultati e le attività di manutenzione in corso.

Per comprendere in che modo un'organizzazione multinazionale fittizia ma rappresentativa ha distribuito gli elementi del tenant Microsoft 365, vedere il [case study Contoso.](../enterprise/contoso-case-study.md)
