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
ms.custom:
- Ent_Solutions
description: Panoramica della pianificazione, della distribuzione e del funzionamento continuo dei tenant di Microsoft 365.
ms.openlocfilehash: f7daeaed149b5b6199ac9012b3ffa3d811029099
ms.sourcegitcommit: 99a7354e6a6b4d9d5202674ef57852d52a43fef6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/20/2021
ms.locfileid: "49908635"
---
# <a name="tenant-management-for-microsoft-365-for-enterprise"></a>Gestione tenant per Microsoft 365 per le aziende

La creazione di un percorso per la trasformazione digitale dell'organizzazione con il cloud computing richiede una base solida su cui i dipendenti possono fare affidamento su produttività, collaborazione, prestazioni, privacy, conformità e sicurezza.

La corretta configurazione dei tenant di Microsoft 365 fornisce questa base, lasciando ai dipendenti di concentrarsi sul lavoro svolto e sul reparto IT per concentrarsi sulle soluzioni end-to-end che forniscono ulteriore valore aziendale. 

Questa soluzione illustra la configurazione di tale base nei passaggi seguenti:

1. Determinare i tenant
2. Ottimizzare la rete
3. Sincronizzare le identità e applicare gli accesso sicuri
4. Eseguire la migrazione di dispositivi Windows, client di Office e server e dati di Office locali
5. Distribuire la gestione di dispositivi e app

Ma prima di tutto, prendiamoci un momento per capire che cos'è un tenant e che aspetto ha un tenant che fornisce una base ferma.

## <a name="a-microsoft-365-tenant-defined"></a>Un tenant di Microsoft 365 definito

Un tenant di Microsoft 365 è un'istanza dedicata dei servizi di Microsoft 365 e dei dati dell'organizzazione archiviati in una posizione predefinita specifica, ad esempio Europa o Nord America. Questa posizione viene specificata quando si crea il tenant per l'organizzazione. Ogni tenant di Microsoft 365 è distinto, univoco e separato da tutti gli altri tenant di Microsoft 365. Si crea un tenant di Microsoft 365 quando si acquistano uno o più prodotti da Microsoft, ad esempio Microsoft 365 E3 o E5, e un set di licenze per ognuno.

Il tenant di Microsoft 365 include anche un tenant di Azure Active Directory (Azure AD), che è un'istanza dedicata di Azure AD per gli account utente, i gruppi e altri oggetti. Ogni tenant di Azure AD è distinto, univoco e separato da tutti gli altri tenant di Azure AD. Anche se l'organizzazione può avere più tenant di Azure AD che è possibile configurare con le sottoscrizioni di Azure, i tenant di Microsoft 365 possono usare solo un singolo tenant di Azure AD, quello creato al momento della creazione del tenant. 

Ecco un esempio:

![Un tenant di Microsoft 365 di esempio con il tenant di Azure AD](../media/tenant-management-overview/tenant-management-example-tenant.png)

*La gestione* tenant è la pianificazione, la distribuzione e il funzionamento continuo dei tenant di Microsoft 365. 

## <a name="attributes-of-a-well-designed-and-operating-tenant"></a>Attributi di un tenant ben progettato e operativo

Oltre al nome e alla posizione corretti per il tenant, esistono altri elementi da pianificare, distribuire e gestire per garantire che le esperienze utente con le app di produttività cloud come Microsoft Teams ed Exchange Online siano efficaci, sicure ed &mdash; &mdash; efficienti.

Ecco gli elementi:

- Si dispone del set corretto di prodotti (sottoscrizioni) e licenze.
  - Il set di prodotti corrisponde alle esigenze aziendali, IT e di sicurezza.
  - Esiste un numero adeguato di licenze per i dipendenti e cambiamenti previsti nel personale.
- Per la rete:
  - Sono stati configurati i nomi di dominio DNS corretti.
  - Per le reti aziendali, il traffico di rete verso la rete Microsoft è stato ottimizzato per i lavoratori sul posto.
  - Il traffico di rete è stato ottimizzato per i lavoratori remoti che usano un client VPN.
- Gli account, i gruppi e altri oggetti di Servizi di dominio Active Directory sono stati sincronizzati.
  - Gli account tenant di Azure AD sono mappati alle cassette postali di Exchange Online con i domini DNS corretti per gli indirizzi di posta elettronica.
  - Agli account utente sono state assegnate le licenze corrette dai prodotti acquistati corretti (ad esempio Microsoft 365 E3 o E5).
- La gestione delle identità e degli accessi è stata configurata.
  - È necessario l'accesso utente sicuro con autenticazione a più fattori o senza password.
  - Si dispone di criteri di accesso condizionale che applicano i requisiti di accesso e le restrizioni per livelli di sicurezza più elevati.
- I server Office locali e i relativi dati sono stati migrati nelle app cloud o vengono usati in una configurazione ibrida.
- Si esegue la gestione dei dispositivi con Intune o Basic Mobility and Security integrato in Microsoft 365.
  - I dispositivi di proprietà dell'organizzazione vengono registrati e gestiti.
  - Le app per i dispositivi personali vengono gestite.

Ecco un esempio di un tenant di Microsoft 365 con tutti questi elementi sul posto.

![Un tenant di Microsoft 365 di esempio](../media/tenant-management-overview/tenant-management-tenant-config.png)

In questa illustrazione, il tenant di Microsoft 365 include:

- Prodotti e licenze per Microsoft 365 E3 ed E5.
- App di produttività di Microsoft 365.
- Intune con i dispositivi registrati e i criteri di dispositivi e applicazioni.
- Un tenant di Azure AD con account utente sincronizzato (non vengono visualizzati i gruppi e altri oggetti directory), i domini e i criteri di accesso condizionale.

## <a name="tenant-capabilities-for-microsoft-365-for-enterprise"></a>Funzionalità tenant per Microsoft 365 per le aziende

Nelle sezioni e nella tabella seguenti sono elencate le funzionalità principali e le licenze per i passaggi di questa soluzione.

### <a name="tenant"></a>Tenant

| Capacità o funzionalità | Descrizione | Licenze |
|:-------|:-----|:-------|
| Più tenant | Ogni tenant di Microsoft 365 è distinto, univoco e separato da tutti gli altri tenant di Microsoft 365. Con più tenant, esistono restrizioni e considerazioni aggiuntive per la gestione e la fornitura di servizi agli utenti. | Microsoft 365 E3 o E5 | 
| Migrazione delle cassette postali tra tenant | Gli amministratori tenant possono spostare le cassette postali tra tenant con dipendenze dell'infrastruttura minime nei sistemi locali. In questo modo si elimina la necessità di eseguire l'offboard e l'onboard delle cassette postali. | Microsoft 365 E3 o E5 | 
| Multi-Geo | Il tenant può archiviare i dati in pausa nelle altre posizioni geografiche del datacenter scelte per soddisfare i requisiti di residenza dei dati. | Microsoft 365 E3 o E5 | 
| Spostare i dati di base in un nuovo data center geografico | Poiché Microsoft aggiunge nuove posizioni geografiche del datacenter per ulteriori risorse di capacità e calcolo, è possibile richiedere uno spostamento geografico del datacenter per la residenza dei dati in-geo per i dati principali dei clienti. | Microsoft 365 E3 o E5 | 
||||

### <a name="networking"></a>Rete

| Capacità o funzionalità | Descrizione | Licenze |
|:-------|:-----|:-------|
| Network Insights | Metriche delle prestazioni di rete raccolte dal tenant di Microsoft 365 per facilitare la progettazione dei perimetri di rete per le sedi degli uffici. | Microsoft 365 E3 o E5 | 
| Automatizzare gli aggiornamenti degli endpoint | Automatizzare la configurazione e gli aggiornamenti continui per gli endpoint di Microsoft 365 nei file PAC client e nei dispositivi e servizi di rete. | Microsoft 365 E3 o E5 | 
||||

### <a name="identity"></a>Identità

| Capacità o funzionalità | Descrizione | Licenze |
|:-------|:-----|:-------|
| Sincronizzare Active Directory Domain Services (AD DS) locale con il tenant di Azure AD    | Sfruttare il provider di identità locale per account utente, gruppi e altri oggetti. | Microsoft 365 E3 o E5 |
| MFA applicata con le impostazioni predefinite per la sicurezza   | Proteggere le identità e i dispositivi dalla compromissione richiedendo una seconda forma di autenticazione per gli accessi. Le impostazioni predefinite per la sicurezza richiedono l'autenticazione a più fattori per tutti gli account utente.   | Microsoft 365 E3 o E5 |
| MFA applicata con l'accesso condizionale| Richiedere l'autenticazione a più fattori in base agli attributi dell'accesso con i criteri di accesso condizionale.    | Microsoft 365 E3 o E5 | 
| MFA applicata con l'accesso condizionale basato sul rischio   | Richiedere l'autenticazione a più fattori in base al rischio di accesso dell'utente con Microsoft Defender per identità. | Microsoft 365 E5 o E3 con licenze di Azure AD Premium P2 | 
| Reimpostazione della password self-service    | Consentire agli utenti di reimpostare o sbloccare le password o gli account personali.  | Microsoft 365 E3 o E5 |
||||

### <a name="migration"></a>Migrazione

| Capacità o funzionalità | Descrizione | Licenze |
|:-------|:-----|:-------|
| Eseguire la migrazione a Windows 10 | Eseguire la migrazione dei dispositivi che eseguono Windows 7 o Windows 8.1 a Windows 10 Enterprise. | Licenze di Windows 10 Enterprise incluse in Microsoft 365 E3 o E5 | 
| Eseguire la migrazione a Microsoft 365 Apps for enterprise | Eseguire la migrazione delle app client di Office, ad esempio Word e PowerPoint, alle versioni installate dal cloud aggiornate con nuove funzionalità. | Microsoft 365 E3 o E5 | 
| Eseguire la migrazione di server e dati locali a Microsoft 365 | Eseguire la migrazione delle cassette postali di Exchange, dei siti di SharePoint e di Skype for Business online ai servizi cloud di Microsoft 365. | Microsoft 365 E3 o E5 | 
||||

### <a name="device-and-app-management"></a>Gestione di dispositivi e app

| Capacità o funzionalità | Descrizione | Licenze |
|:-------|:-----|:-------|
| Microsoft Intune | Un servizio basato sul cloud che fornisce la gestione dei dispositivi mobili (MDM) e la gestione delle applicazioni mobili (MAM) per controllare il modo in cui vengono usati l'applicazione e i dispositivi dell'organizzazione, inclusi telefoni cellulari, tablet e portatili. | Microsoft 365 E3 o E5 | 
| Basic Mobility + Security | Proteggere e gestire i dispositivi mobili degli utenti come iPhone, iPad, Android e telefoni Windows con questo servizio incorporato.  | Microsoft 365 E3 o E5 | 
||||

## <a name="next-steps"></a>Passaggi successivi

Seguire questa procedura per configurare e gestire i tenant di Microsoft 365.

1. [Determinare i tenant](tenant-management-tenants.md)
2. [Ottimizzare la rete](tenant-management-networking.md)
3. [Sincronizzare le identità e applicare gli accesso sicuri](tenant-management-identity.md)
4. [Eseguire la migrazione dei server e dei dati di Office locali](tenant-management-migration.md)
5. [Distribuire la gestione di dispositivi e app](tenant-management-device-management.md)

[![Passaggi per distribuire e gestire un tenant di Microsoft 365](../media/tenant-management-overview/tenant-management-step-grid.png)](tenant-management-tenants.md)

Ogni passaggio descrive le opzioni di distribuzione, riepiloga i risultati e le attività di manutenzione in corso.

Per comprendere in che modo un'organizzazione fittizia ma rappresentativa multi-nazionale ha distribuito gli elementi del tenant di Microsoft 365, vedere il [case study Contoso.](../enterprise/contoso-case-study.md)
