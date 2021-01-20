---
title: Gestione tenant per Microsoft 365 per Enterprise
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
description: Una panoramica sulla pianificazione, la distribuzione e il funzionamento continuo dei tenant Microsoft 365.
ms.openlocfilehash: f7daeaed149b5b6199ac9012b3ffa3d811029099
ms.sourcegitcommit: 99a7354e6a6b4d9d5202674ef57852d52a43fef6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/20/2021
ms.locfileid: "49908635"
---
# <a name="tenant-management-for-microsoft-365-for-enterprise"></a>Gestione tenant per Microsoft 365 per Enterprise

La creazione di un percorso per la trasformazione digitale dell'organizzazione con il cloud computing richiede un solido fondamento su cui i dipendenti possono contare per la produttività, la collaborazione, le prestazioni, la privacy, la conformità e la sicurezza.

La corretta configurazione dei tenant di Microsoft 365 fornisce tale fondamento, lasciando i lavoratori a concentrarsi su come svolgere il proprio lavoro e il proprio reparto IT per concentrarsi sulle soluzioni end-to-end che forniscono un valore aziendale aggiuntivo. 

Questa soluzione consente di eseguire la configurazione di tale fondamento nei passaggi seguenti:

1. Determinare i tenant
2. Ottimizzare la rete
3. Sincronizzare le identità e applicare gli accessi sicuri
4. Eseguire la migrazione di dispositivi Windows, client di Office e server e dati locali di Office
5. Distribuire la gestione di dispositivi e app

Tuttavia, prima di tutto, è necessario un momento per capire cosa è un tenant e cosa assomiglia a un tenant che fornisce una base stabile.

## <a name="a-microsoft-365-tenant-defined"></a>Un tenant di Microsoft 365 definito

Un tenant di Microsoft 365 è un'istanza dedicata dei servizi di Microsoft 365 e dei dati dell'organizzazione archiviati all'interno di una specifica posizione predefinita, ad esempio Europa o Nord America. Questo percorso viene specificato quando si crea il tenant per l'organizzazione. Ogni tenant di Microsoft 365 è distinto, univoco e separato da tutti gli altri tenant di Microsoft 365. È possibile creare un tenant di Microsoft 365 quando si acquista uno o più prodotti da Microsoft, ad esempio Microsoft 365 E3 o E5, e un insieme di licenze per ognuno di essi.

Il tenant Microsoft 365 include anche un tenant di Azure Active Directory (Azure AD), che è un'istanza dedicata di Azure AD per gli account utente, i gruppi e gli altri oggetti. Ogni tenant di Azure AD è distinto, univoco e separato da tutti gli altri tenant di Azure AD. Anche se l'organizzazione può disporre di più tenant di Azure AD che è possibile configurare con le sottoscrizioni di Azure, i tenant di Microsoft 365 possono utilizzare solo un singolo tenant di Azure AD, quello creato durante la creazione del tenant. 

Ecco un esempio:

![Un esempio Microsoft 365 tenant con il tenant di Azure AD](../media/tenant-management-overview/tenant-management-example-tenant.png)

*Gestione tenant* è la pianificazione, la distribuzione e il funzionamento continuo dei tenant Microsoft 365. 

## <a name="attributes-of-a-well-designed-and-operating-tenant"></a>Attributi di un tenant ben disegnato e operativo

Oltre al nome e alla posizione corretti per il tenant, sono disponibili ulteriori elementi per pianificare, distribuire e gestire le esperienze degli utenti con le app per la produttività del cloud, &mdash; ad esempio Microsoft teams ed Exchange Online, che &mdash; sono effettive, sicure e performanti.

Ecco gli elementi:

- Si dispone del set corretto di prodotti (abbonamenti) e licenze.
  - Il set di prodotti corrisponde alle esigenze aziendali, IT e di sicurezza.
  - Vi è un numero adeguato di licenze per i dipendenti e le modifiche anticipate del personale.
- Per la rete:
  - Sono stati configurati i nomi di dominio DNS corretti.
  - Per le reti aziendali, il traffico di rete è stato ottimizzato per la rete Microsoft per i lavoratori onsite.
  - È stato ottimizzato il traffico di rete per i dipendenti remoti che utilizzano un client VPN.
- Sono stati sincronizzati gli account di servizi di dominio Active Directory (AD DS), i gruppi e gli altri oggetti.
  - Gli account tenant di Azure AD vengono mappati alle cassette postali di Exchange Online con i domini DNS corretti per gli indirizzi di posta elettronica.
  - Agli account utente sono state assegnate le licenze corrette dai prodotti acquistati corretti (come Microsoft 365 E3 o E5).
- Sono state configurate forti identità e gestione degli accessi.
  - Si richiede l'accesso sicuro degli utenti con password o autenticazione a più fattori (AMF).
  - Si dispone di criteri di accesso condizionale che applicano i requisiti e le restrizioni per i livelli di sicurezza più elevati.
- I server di Office locali e i relativi dati sono stati migrati nelle app Cloud o sono stati utilizzati in una configurazione ibrida.
- Si sta eseguendo la gestione dei dispositivi con Intune o la mobilità di base e la sicurezza integrata in Microsoft 365.
  - I dispositivi di proprietà dell'organizzazione vengono registrati e gestiti.
  - Le app per i dispositivi personali vengono gestite.

Di seguito è riportato un esempio di tenant Microsoft 365 con tutti questi elementi sul posto.

![Un esempio di Microsoft 365 tenant](../media/tenant-management-overview/tenant-management-tenant-config.png)

In questa figura, il tenant di Microsoft 365 include:

- Prodotti e licenze per Microsoft 365 E3 ed E5.
- App per la produttività di Microsoft 365.
- Intune con i dispositivi registrati e i criteri di dispositivo e applicazione.
- Un tenant di Azure AD con account utente sincronizzato (gruppi e altri oggetti directory non visualizzati), domini e criteri di accesso condizionale.

## <a name="tenant-capabilities-for-microsoft-365-for-enterprise"></a>Funzionalità tenant per Microsoft 365 per Enterprise

Nelle sezioni e nelle tabelle riportate di seguito sono elencate le funzionalità e le licenze principali per la procedura descritta in questa soluzione.

### <a name="tenant"></a>Tenant

| Capacità o funzionalità | Descrizione | Licenze |
|:-------|:-----|:-------|
| Più tenant | Ogni tenant di Microsoft 365 è distinto, univoco e separato da tutti gli altri tenant di Microsoft 365. Con più tenant, esistono restrizioni e considerazioni aggiuntive per la gestione e la fornitura di servizi agli utenti. | Microsoft 365 E3 o E5 | 
| Migrazione delle cassette postali tra tenant | Gli amministratori tenant possono spostare le cassette postali tra i tenant con dipendenze dell'infrastruttura minime nei rispettivi sistemi locali. In questo modo viene eliminata la necessità di disabilitare le cassette postali e di bordo. | Microsoft 365 E3 o E5 | 
| Multi-Geo | Il tenant può archiviare i dati a riposo nelle altre posizioni geografiche del datacenter che si è scelto di soddisfare i requisiti di residenza dei dati. | Microsoft 365 E3 o E5 | 
| Spostare i dati di base in un nuovo datacenter Geo | Poiché Microsoft aggiunge nuovo datacenter GEOS per ulteriori capacità e risorse di calcolo, è possibile richiedere una mossa geografica del datacenter per la residenza dei dati in-Geo per i dati di base dei clienti. | Microsoft 365 E3 o E5 | 
||||

### <a name="networking"></a>Rete

| Capacità o funzionalità | Descrizione | Licenze |
|:-------|:-----|:-------|
| Informazioni di rete | Metriche delle prestazioni di rete raccolte dal tenant Microsoft 365 per facilitare la progettazione di perimetri di rete per le posizioni di Office. | Microsoft 365 E3 o E5 | 
| Automatizzare gli aggiornamenti degli endpoint | Automatizzare la configurazione e gli aggiornamenti in continuazione per gli endpoint di Microsoft 365 nei file PAC client e nei dispositivi e servizi di rete. | Microsoft 365 E3 o E5 | 
||||

### <a name="identity"></a>Identità

| Capacità o funzionalità | Descrizione | Licenze |
|:-------|:-----|:-------|
| Sincronizzare servizi di dominio Active Directory (AD DS) locali con il tenant di Azure AD    | Sfruttare il provider di identità locale per gli account utente, i gruppi e gli altri oggetti. | Microsoft 365 E3 o E5 |
| MFA applicata con le impostazioni predefinite per la sicurezza   | Proteggere le identità e i dispositivi dalla compromissione richiedendo una seconda forma di autenticazione per gli accessi. Le impostazioni predefinite per la sicurezza richiedono l'autenticazione a più fattori per tutti gli account utente.   | Microsoft 365 E3 o E5 |
| MFA applicata con l'accesso condizionale| Richiedere l'AMF in base agli attributi dei criteri di accesso condizionale.    | Microsoft 365 E3 o E5 | 
| MFA applicata con l'accesso condizionale basato sul rischio   | Richiedere l'autenticazione a più fattori in base al rischio di accesso dell'utente con Microsoft Defender per identità. | Microsoft 365 E5 o E3 con licenze di Azure AD Premium P2 | 
| Reimpostazione della password self-service    | Consentire agli utenti di reimpostare o sbloccare le password o gli account personali.  | Microsoft 365 E3 o E5 |
||||

### <a name="migration"></a>Migrazione

| Capacità o funzionalità | Descrizione | Licenze |
|:-------|:-----|:-------|
| Eseguire la migrazione a Windows 10 | Eseguire la migrazione dei dispositivi che eseguono Windows 7 o Windows 8,1 a Windows 10 Enterprise. | Licenze di Windows 10 Enterprise incluse in Microsoft 365 E3 o E5 | 
| Eseguire la migrazione a Microsoft 365 Apps for Enterprise | Eseguire la migrazione delle app client di Office, ad esempio Word e PowerPoint, alle versioni installate dal cloud aggiornate con nuove funzionalità. | Microsoft 365 E3 o E5 | 
| Eseguire la migrazione di dati e server locali a Microsoft 365 | Eseguire la migrazione delle cassette postali di Exchange, dei siti di SharePoint e di Skype for business online ai servizi cloud di Microsoft 365. | Microsoft 365 E3 o E5 | 
||||

### <a name="device-and-app-management"></a>Gestione di dispositivi e app

| Capacità o funzionalità | Descrizione | Licenze |
|:-------|:-----|:-------|
| Microsoft Intune | Servizio basato su cloud che fornisce la gestione dei dispositivi mobili (MDM) e la gestione delle applicazioni mobili (MAM) per controllare il modo in cui vengono utilizzate l'applicazione e i dispositivi dell'organizzazione, inclusi telefoni cellulari, tablet e laptop. | Microsoft 365 E3 o E5 | 
| Basic Mobility + Security | Proteggere e gestire i dispositivi mobili degli utenti come iPhone, iPad, Android e telefoni Windows con questo servizio incorporato.  | Microsoft 365 E3 o E5 | 
||||

## <a name="next-steps"></a>Passaggi successivi

Attenersi alla procedura seguente per configurare e gestire i tenant di Microsoft 365.

1. [Determinare i tenant](tenant-management-tenants.md)
2. [Ottimizzare la rete](tenant-management-networking.md)
3. [Sincronizzare le identità e applicare gli accessi sicuri](tenant-management-identity.md)
4. [Migrare i dati e i server di Office locali](tenant-management-migration.md)
5. [Distribuire la gestione di dispositivi e app](tenant-management-device-management.md)

[![Passaggi per la distribuzione e la gestione di un tenant di Microsoft 365](../media/tenant-management-overview/tenant-management-step-grid.png)](tenant-management-tenants.md)

In ogni passaggio vengono descritte le opzioni di distribuzione, vengono riepilogati i risultati e le attività di manutenzione in esecuzione.

Per comprendere come un'organizzazione multi-nazionale fittizia ma rappresentativa ha distribuito gli elementi del tenant Microsoft 365, vedere il [Case Study di Contoso](../enterprise/contoso-case-study.md).
