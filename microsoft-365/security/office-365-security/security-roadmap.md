---
title: Roadmap sulla sicurezza di Microsoft 365-priorità principali
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
ms.openlocfilehash: d62db9206a98078ae5adaad220a7c9b53ff116cd
ms.sourcegitcommit: 4debeb8f0fce67f361676340fc390f1b283a3069
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/03/2020
ms.locfileid: "49561700"
---
# <a name="security-roadmap---top-priorities-for-the-first-30-days-90-days-and-beyond"></a>Roadmap sulla sicurezza-priorità principali per i primi 30 giorni, 90 giorni e oltre

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


In questo articolo sono inclusi i principali consigli del team di Cybersecurity di Microsoft per l'implementazione delle funzionalità di protezione per proteggere l'ambiente Microsoft 365. Questo articolo è adattato da una sessione di Microsoft Ignite- [secure microsoft 365 like a Cybersecurity Pro: priorità principali per i primi 30 giorni, 90 giorni e oltre](https://www.youtube.com/watch?v=luignzNyR-o). Questa sessione è stata sviluppata e presentata da Mark Simos e Matt Kemelhar, Enterprise Cybersecurity Architects.

Contenuto dell'articolo:

- [Risultati della roadmap](security-roadmap.md#Roadmap)
- [30 giorni: potenti vittorie veloci](security-roadmap.md#Thirdaydays)
- [90 giorni-protezione avanzata](security-roadmap.md#Ninetydays)
- [Oltre](security-roadmap.md#Beyond)

## <a name="roadmap-outcomes"></a>Risultati della roadmap
<a name="Roadmap"> </a>

Questi suggerimenti sulla roadmap sono disponibili in tre fasi in un ordine logico con i seguenti obiettivi.

****

|Intervallo di tempo|Risultati|
|---|---|
|30 giorni|Configurazione rapida: <ul><li>Protezioni di base per gli amministratori.</li><li>Registrazione e analisi.</li><li>Protezione delle identità di base.</li></ul> <p> Configurazione tenant. <p> Preparare le parti interessate.|
|90 giorni|Protezioni avanzate: <ul><li>Account di amministratore.</li><li>Account utente e dati.</li></ul> <p> Visibilità in conformità, minacce e esigenze degli utenti. <p> Adattare e implementare criteri e protezioni predefiniti.|
|Oltre|Modificare e affinare i criteri e i controlli chiave. <p> Estendere le protezioni alle dipendenze locali. <p> Integrazione con processi aziendali e di sicurezza (Legal, Insider Threat, ecc.).|
|

## <a name="30-days--powerful-quick-wins"></a>30 giorni: potenti vittorie veloci
<a name="Thirdaydays"> </a>

Queste attività possono essere eseguite rapidamente e hanno un impatto minimo sugli utenti.

****

|Area|Attività|
|---|---|
|Gestione della sicurezza|<ul><li>Controllare il Punteggio sicuro e prendere nota del punteggio corrente ( <https://securescore.office.com> ).</li><li>Abilitare la registrazione di controllo per Office 365. Vedere [Search the audit log](../../compliance/search-the-audit-log-in-security-and-compliance.md).</li><li>[Configurare Microsoft 365 per una maggiore sicurezza](tenant-wide-setup-for-increased-security.md).</li><li>Esaminare periodicamente i dashboard e i report nel centro sicurezza Microsoft 365 e nel cloud app Security.</li></ul>|
|Protezione dalle minacce|[Connettere microsoft 365 a Microsoft cloud app Security](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security) per avviare il monitoraggio utilizzando i criteri di rilevamento delle minacce predefiniti per comportamenti anomali. Per creare una linea di base per il rilevamento delle anomalie, sono necessari sette giorni. <p>  Implementare la protezione per gli account di amministrazione:<ul><li>Utilizzare gli account di amministrazione dedicati per l'attività di amministrazione.</li><li>Applicare l'autenticazione a più fattori (AMF) per gli account di amministratore.</li><li>Utilizzare un [dispositivo Windows 10 estremamente sicuro](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-highly-secure) per l'attività di amministrazione.</li></ul>|
|Gestione di identità e accesso|<ul><li>[Abilitare Azure Active Directory Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).</li><li>Per gli ambienti di identità federati, applicare la sicurezza degli account (lunghezza della password, validità, complessità e così via).</li></ul>|
|Protezione delle informazioni|Esaminare i consigli di protezione delle informazioni di esempio. La protezione delle informazioni richiede un coordinamento nell'organizzazione. Per iniziare, usare queste risorse:<ul><li>[Information Protection di Office 365 per il GDPR](https://aka.ms/o365gdpr)</li><li>[Configurare Team con tre livelli di protezione](../../solutions/configure-teams-three-tiers-protection.md) (include la condivisione, la classificazione, la prevenzione della perdita di dati e la protezione delle informazioni di Azure)</li></ul>|
|

## <a name="90-days--enhanced-protections"></a>90 giorni-protezione avanzata
<a name="Ninetydays"> </a>

Queste attività richiedono una quantità di tempo leggermente superiore per la pianificazione e l'implementazione, ma aumentano notevolmente il livello di sicurezza.

****

|Area|Attività|
|---|---|
|Gestione della sicurezza|<ul><li>Controllare il Punteggio sicuro per le azioni consigliate per l'ambiente ( [https://securescore.office.com](https://securescore.office.com) ).</li><li>Continuare a esaminare periodicamente i dashboard e i report nel centro sicurezza Microsoft 365, nel cloud app Security e negli strumenti di SIEM.</li><li>Cercare e implementare gli aggiornamenti software.</li><li>Eseguire simulazioni di attacco per attacchi Spear-phishing, password-spray e per la forza bruta tramite [simulatore di attacco](attack-simulator.md) (incluso in [Office 365 Threat Intelligence](office-365-ti.md)).</li><li>Cercare il rischio di condivisione rivedendo i report incorporati in cloud app Security (nella scheda indagare).</li><li>Controllare [Compliance Manager](https://docs.microsoft.com/microsoft-365/compliance/compliance-manager) per esaminare lo stato delle regole che si applicano all'organizzazione, ad esempio GDPR, NIST 800-171.</li></ul>|
|Protezione dalle minacce|Implementare protezioni avanzate per gli account di amministrazione: <ul><li>Configurare le [postazioni di accesso privilegiate](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/privileged-access-workstations) (PAWs) per l'attività di amministrazione.</li><li>Configurare [Azure ad Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).</li><li>Configurare uno strumento di gestione degli eventi e delle informazioni di sicurezza (SIEM) per raccogliere i dati di registrazione da Office 365, cloud app Security e altri servizi, AD esempio AD FS. Il registro di controllo archivia i dati per soli 90 giorni. L'acquisizione di questi dati in strumento di SIEM consente di archiviare i dati per un periodo di tempo più lungo.</li></ul>|
|Gestione di identità e accesso|<ul><li>Abilitare e applicare Mae per tutti gli utenti.</li><li>Implementare un insieme di [criteri di accesso condizionale e correlati](microsoft-365-policies-configurations.md).</li></ul>|
|Protezione delle informazioni| Adattare e implementare i criteri di protezione delle informazioni. Tali risorse includono esempi: <ul><li>[Information Protection di Office 365 per il GDPR](https://aka.ms/o365gdpr)</li><li>[Configurare Teams con tre livelli di protezione](../../solutions/configure-teams-three-tiers-protection.md)</li></ul> <p> Utilizzare i criteri di prevenzione della perdita di dati e gli strumenti di monitoraggio in Microsoft 365 per i dati archiviati in Microsoft 365 (invece di cloud app Security). <p> Utilizzare cloud app Security con Microsoft 365 per funzionalità di avviso avanzate (oltre alla prevenzione della perdita di dati).|
|

## <a name="beyond"></a>Oltre
<a name="Beyond"> </a>

Si tratta di importanti misure di sicurezza che si basano sui lavori precedenti.

****

|Area|Attività|
|---|---|
|Gestione della sicurezza|<ul><li>Continuare a pianificare le azioni successive utilizzando il Punteggio sicuro ( <https://securescore.office.com> ).</li><li>Continuare a esaminare periodicamente i dashboard e i report nel centro sicurezza Microsoft 365, nel cloud app Security e negli strumenti di SIEM.</li><li>Continuare a cercare e implementare gli aggiornamenti software.</li><li>Integrazione di eDiscovery nei processi di risposta legale e di minacce.</li></ul>|
|Protezione dalle minacce|<ul><li>Implementare [l'accesso con privilegi sicuri](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/securing-privileged-access) (Spa) per i componenti di identità in locale (ad, ADFS).</li><li>Utilizzare cloud app Security per monitorare le minacce Insider.</li><li>Scoprire l'utilizzo dell'ombreggiatura SaaS tramite cloud app Security.</li></ul>|
|Gestione di identità e accesso|<ul><li>Affinare i criteri e i processi operativi.</li><li>Utilizzo di Azure AD Identity Protection per identificare le minacce Insider.</li></ul>|
|Protezione delle informazioni|Affinare i criteri di protezione delle informazioni: <ul><li>Microsoft 365 e Office 365, etichette di riservatezza e prevenzione della perdita di dati (DLP) o Azure Information Protection.</li><li>Avvisi e criteri di protezione delle app cloud.</li></ul>|
|

Vedere anche: [come attenuare le attacchi cibernetici rapide, ad esempio Petya e WannaCrypt](https://cloudblogs.microsoft.com/microsoftsecure/2018/02/21/how-to-mitigate-rapid-cyberattacks-such-as-petya-and-wannacrypt/).
