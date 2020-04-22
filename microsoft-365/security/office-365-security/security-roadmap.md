---
title: Roadmap sulla sicurezza-priorità principali per i primi 30 giorni, 90 giorni e oltre
f1.keywords:
- NOCSH
ms.author: bcarter
author: BrendaCarter
manager: laurawi
ms.date: 10/08/2018
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
ms.assetid: 28c86a1c-e4dd-4aad-a2a6-c768a21cb352
description: "Consigli principali del team di Cybersecurity di Microsoft per l'implementazione delle funzionalità di protezione per proteggere l'ambiente Microsoft 365. "
ms.openlocfilehash: f00cf7c63e84f19ac2cae080adb87209b32d3012
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633726"
---
# <a name="security-roadmap---top-priorities-for-the-first-30-days-90-days-and-beyond"></a>Roadmap sulla sicurezza-priorità principali per i primi 30 giorni, 90 giorni e oltre

In questo articolo sono inclusi i principali consigli del team di Cybersecurity di Microsoft per l'implementazione delle funzionalità di protezione per proteggere l'ambiente Microsoft 365. Questo articolo è adattato da una sessione di Microsoft Ignite- [secure microsoft 365 like a Cybersecurity Pro: priorità principali per i primi 30 giorni, 90 giorni e oltre](https://www.youtube.com/watch?v=luignzNyR-o). Questa sessione è stata sviluppata e presentata da Mark Simos e Matt Kemelhar, Enterprise Cybersecurity Architects.

Contenuto dell'articolo:

- [Risultati della roadmap](security-roadmap.md#Roadmap)

- [30 giorni: potenti vittorie veloci](security-roadmap.md#Thirdaydays)

- [90 giorni-protezione avanzata](security-roadmap.md#Ninetydays)

- [Oltre](security-roadmap.md#Beyond)

## <a name="roadmap-outcomes"></a>Risultati della roadmap
<a name="Roadmap"> </a>

Questi suggerimenti sulla roadmap sono disponibili in tre fasi in un ordine logico con i seguenti obiettivi.

|||
|:-----|:-----|
| |Risultati
|30 giorni|Configurazione rapida:  <br/> * Protezioni di base per gli amministratori  <br/> * Registrazione e analisi  <br/> * Protezioni identità di base  <br/> Configurazione tenant  <br/>  Preparare le parti interessate|
|90 giorni|Protezioni avanzate:  <br/> * Account amministratore  <br/>  * Account &amp; utente dati  <br/>  Visibilità nella conformità, nelle minacce e nelle esigenze degli utenti  <br/>  Adattare e implementare criteri e protezioni predefiniti|
|Oltre|Modificare e affinare i criteri e i controlli chiave  <br/> Estendere le protezioni alle dipendenze locali  <br/> Integrazione con processi aziendali e di sicurezza (legale, Insider Threat, ecc.)|



## <a name="30-days--powerful-quick-wins"></a>30 giorni: potenti vittorie veloci
<a name="Thirdaydays"> </a>

Queste attività possono essere eseguite rapidamente e hanno un impatto minimo sugli utenti.

|||
|:-----|:-----|
|Area|Attività|
|Gestione della sicurezza|* Verificare il Punteggio sicuro e prendere nota del punteggio corrente ([https://securescore.office.com](https://securescore.office.com)).  <br/>  * Abilitare la registrazione di controllo per Office 365. Vedere [Search the audit log](../../compliance/search-the-audit-log-in-security-and-compliance.md).  <br/> * [Configurare Microsoft 365 per una maggiore sicurezza](tenant-wide-setup-for-increased-security.md) .  <br/>  * Esaminare periodicamente dashboard e report in Microsoft 365 Security Center e cloud app Security.|
|Protezione dalle minacce|[Connettere microsoft 365 a Microsoft cloud app Security](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security) per avviare il monitoraggio utilizzando i criteri di rilevamento delle minacce predefiniti per comportamenti anomali. Per creare una linea di base per il rilevamento delle anomalie, sono necessari sette giorni.  <br><br/>  Implementare la protezione per gli account di amministrazione:  <br/> * Utilizzare gli account di amministrazione dedicati per l'attività di amministrazione.  <br/>  * Applicare l'autenticazione a più fattori (AMF) per gli account di amministratore.  <br/>  * Utilizzare un [dispositivo Windows 10 estremamente sicuro](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-highly-secure) per l'attività di amministrazione.|
|Gestione di identità e accesso|* [Abilitare Azure Active Directory Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).  <br/> * Per gli ambienti di identità federati, applicare la sicurezza degli account (lunghezza della password, validità, complessità e così via).|
|Protezione delle informazioni| Esaminare i consigli di protezione delle informazioni di esempio. La protezione delle informazioni richiede un coordinamento nell'organizzazione. Per iniziare, usare queste risorse:  <br/> * [Protezione delle informazioni di Office 365 per GDPR](https://aka.ms/o365gdpr) <br/> * [Proteggere siti e file di SharePoint Online](https://docs.microsoft.com/Office365/enterprise/secure-sharepoint-online-sites-and-files) (include la condivisione, la classificazione, la prevenzione della perdita di dati e la protezione delle informazioni di Azure)|

## <a name="90-days--enhanced-protections"></a>90 giorni-protezione avanzata
<a name="Ninetydays"> </a>

Queste attività richiedono una quantità di tempo leggermente superiore per la pianificazione e l'implementazione, ma aumentano notevolmente il livello di sicurezza.

|||
|:-----|:-----|
|Area|Attività|
|Gestione della sicurezza|* Verificare il Punteggio sicuro per le azioni consigliate per[https://securescore.office.com](https://securescore.office.com)l'ambiente ().  <br/>  * Continuare a esaminare periodicamente i dashboard e i report nel centro sicurezza Microsoft 365, nel cloud app Security e negli strumenti di SIEM. <br/> * Cercare e implementare gli aggiornamenti software. <br/> * Condurre simulazioni di attacco per attacchi di password Spear-phishing, password-spray e Brute Force usando [simulatore d'attacco](attack-simulator.md) (incluso in [Office 365 Threat Intelligence](office-365-ti.md)).  <br/> * Cercare il rischio di condivisione rivedendo i report incorporati in cloud app Security (nella scheda indagare). <br/> * Verificare il [Punteggio di conformità](https://docs.microsoft.com/microsoft-365/compliance/compliance-score) per esaminare lo stato delle normative che si applicano all'organizzazione, ad esempio GDPR, NIST 800-171.|
|Protezione dalle minacce| Implementare protezioni avanzate per gli account di amministrazione: <br/> * Configurare le [workstation di accesso privilegiate](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/privileged-access-workstations) (PAWs) per l'attività di amministrazione. <br/> * Configurare [Azure ad Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure). <br/> * Configurare uno strumento di gestione degli eventi e delle informazioni di sicurezza (SIEM) per raccogliere i dati di registrazione da Office 365, cloud app Security e altri servizi, AD esempio AD FS. Il registro di controllo archivia i dati per soli 90 giorni. L'acquisizione di questi dati in strumento di SIEM consente di archiviare i dati per un periodo di tempo più lungo.|
|Gestione di identità e accesso|* Abilitare e applicare Mae per tutti gli utenti. <br/> * Implementare una serie di [criteri di accesso condizionale e correlati](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-policies-configurations). |
|Protezione delle informazioni| Adattare e implementare i criteri di protezione delle informazioni. Tali risorse includono esempi: <br/> * [Protezione delle informazioni di Office 365 per GDPR](https://aka.ms/o365gdpr) <br/> * [Proteggere siti e file di SharePoint Online](https://docs.microsoft.com/Office365/enterprise/secure-sharepoint-online-sites-and-files) <br/> <br> Utilizzare i criteri di prevenzione della perdita di dati e gli strumenti di monitoraggio in Microsoft 365 per i dati archiviati in Microsoft 365 (invece di cloud app Security). <br><br>Utilizzare cloud app Security con Microsoft 365 per funzionalità di avviso avanzate (oltre alla prevenzione della perdita di dati).|

## <a name="beyond"></a>Oltre
<a name="Beyond"> </a>

Si tratta di importanti misure di sicurezza che si basano sui lavori precedenti.

|||
|:-----|:-----|
|Area|Attività|
|Gestione della sicurezza|* Continuare a pianificare azioni successive utilizzando il Punteggio sicuro [https://securescore.office.com](https://securescore.office.com)(). <br/> * Continuare a esaminare periodicamente i dashboard e i report nel centro sicurezza Microsoft 365, nel cloud app Security e negli strumenti di SIEM. <br/> * Continuare a cercare e implementare gli aggiornamenti software. <br/> * Integrazione di eDiscovery nei processi di risposta legale e di minacce.|
|Protezione dalle minacce|* Implementare [l'accesso con privilegi sicuri](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/securing-privileged-access) (Spa) per i componenti di identità in locale (ad, ADFS). <br/> * Utilizzare cloud app Security per monitorare le minacce Insider. <br/> * Individuare l'ombreggiatura dell'utilizzo di SaaS tramite cloud app Security.|
|Gestione di identità e accesso|* Affinare i criteri e i processi operativi. <br/> * Utilizzare Azure AD Identity Protection per identificare le minacce Insider.|
|Protezione delle informazioni| Affinare i criteri di protezione delle informazioni: <br/> * Microsoft 365 e Office 365, etichette di riservatezza e prevenzione della perdita di dati (DLP) o Azure Information Protection. <br/> * Criteri e avvisi relativi alla sicurezza delle app cloud.|

Vedere anche: [come attenuare le attacchi cibernetici rapide, ad esempio Petya e WannaCrypt](https://cloudblogs.microsoft.com/microsoftsecure/2018/02/21/how-to-mitigate-rapid-cyberattacks-such-as-petya-and-wannacrypt/).
