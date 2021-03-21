---
title: Roadmap per la sicurezza di Microsoft 365 - Priorità principali
f1.keywords:
- NOCSH
ms.author: bcarter
author: BrendaCarter
manager: laurawi
ms.date: 10/08/2018
audience: Admin
ms.topic: conceptual
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
ms.assetid: 28c86a1c-e4dd-4aad-a2a6-c768a21cb352
description: Consigli principali del team di sicurezza informatica di Microsoft per l'implementazione delle funzionalità di sicurezza per proteggere l'ambiente Microsoft 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: bd86262cd36d9482cd9a54e7fd7c336a6f0700dd
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929265"
---
# <a name="security-roadmap---top-priorities-for-the-first-30-days-90-days-and-beyond"></a>Roadmap per la sicurezza - Priorità principali per i primi 30 giorni, 90 giorni e oltre

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Questo articolo include i consigli principali del team di sicurezza informatica di Microsoft per l'implementazione delle funzionalità di sicurezza per proteggere l'ambiente Microsoft 365. Questo articolo è stato adattato da una sessione di Microsoft Ignite - Proteggere Microsoft 365 come un professionista della sicurezza informatica: priorità principali per i primi [30 giorni, 90](https://www.youtube.com/watch?v=luignzNyR-o)giorni e oltre . Questa sessione è stata sviluppata e presentata da Mark Simos e Matt Kemelhar, Enterprise Cybersecurity Architects.

Contenuto dell'articolo:

- [Risultati della roadmap](security-roadmap.md#Roadmap)
- [30 giorni: potenti successi rapidi](security-roadmap.md#Thirdaydays)
- [90 giorni : protezioni avanzate](security-roadmap.md#Ninetydays)
- [Oltre](security-roadmap.md#Beyond)

## <a name="roadmap-outcomes"></a>Risultati della roadmap
<a name="Roadmap"> </a>

Questi consigli di roadmap vengono a fasi in tre fasi in un ordine logico con gli obiettivi seguenti.

****

|Intervallo di tempo|Risultati|
|---|---|
|30 giorni|Configurazione rapida: <ul><li>Protezioni di amministrazione di base.</li><li>Registrazione e analisi.</li><li>Protezioni di base per le identità.</li></ul> <p> Configurazione tenant. <p> Preparare le parti interessate.|
|90 giorni|Protezioni avanzate: <ul><li>Account amministratore.</li><li>Dati e account utente.</li></ul> <p> Visibilità sulle esigenze di conformità, minacce e utenti. <p> Adattare e implementare criteri e protezioni predefiniti.|
|Oltre|Modificare e perfezionare i criteri e i controlli chiave. <p> Estendere le protezioni alle dipendenze locali. <p> Integrazione con i processi aziendali e di sicurezza (legale, insider threat e così via).|
|

## <a name="30-days--powerful-quick-wins"></a>30 giorni: potenti successi rapidi
<a name="Thirdaydays"> </a>

Queste attività possono essere eseguite rapidamente e hanno un impatto minimo sugli utenti.

****

|Area|Tasks|
|---|---|
|Gestione della sicurezza|<ul><li>Controlla Punteggio sicuro e prendi nota del punteggio corrente ( <https://securescore.office.com> ).</li><li>Attivare la registrazione di controllo per Office 365. Vedere [Search the audit log](../../compliance/search-the-audit-log-in-security-and-compliance.md).</li><li>[Configurare Microsoft 365 per una maggiore sicurezza.](tenant-wide-setup-for-increased-security.md)</li><li>Esaminare regolarmente dashboard e report nel Centro sicurezza Microsoft 365 e cloud App Security.</li></ul>|
|Protezione dalle minacce|[Connettere Microsoft 365 a Microsoft Cloud App Security](/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security) per avviare il monitoraggio usando i criteri di rilevamento delle minacce predefiniti per comportamenti anomali. Sono necessari sette giorni per creare una linea di base per il rilevamento di anomalie. <p>  Implementare la protezione per gli account amministratore:<ul><li>Usa account amministratore dedicati per le attività di amministratore.</li><li>Applicare l'autenticazione a più fattori (MFA) per gli account di amministratore.</li><li>Usa un [dispositivo Windows 10 altamente sicuro per](/windows-hardware/design/device-experiences/oem-highly-secure) le attività di amministratore.</li></ul>|
|Gestione delle identità e degli accessi|<ul><li>[Abilitare Azure Active Directory Identity Protection](/azure/active-directory/active-directory-identityprotection-enable).</li><li>Per gli ambienti con identità federate, applicare la sicurezza dell'account (lunghezza della password, validità, complessità e così via).</li></ul>|
|Protezione delle informazioni|Esaminare consigli di esempio sulla protezione delle informazioni. La protezione delle informazioni richiede il coordinamento all'interno dell'organizzazione. Per iniziare, usare queste risorse:<ul><li>[Information Protection di Office 365 per il GDPR](/compliance/regulatory/gdpr)</li><li>[Configurare Teams con tre livelli di protezione](../../solutions/configure-teams-three-tiers-protection.md) (tra cui condivisione, classificazione, prevenzione della perdita dei dati e Azure Information Protection)</li></ul>|
|

## <a name="90-days--enhanced-protections"></a>90 giorni : protezioni avanzate
<a name="Ninetydays"> </a>

Queste attività richiedono una quantità di tempo leggermente superiore per la pianificazione e l'implementazione, ma aumentano notevolmente il livello di sicurezza.

****

|Area|Attività|
|---|---|
|Gestione della sicurezza|<ul><li>Controllare Punteggio sicuro per le azioni consigliate per l'ambiente ( <https://securescore.office.com> ).</li><li>Continuare a esaminare regolarmente dashboard e report nel Centro sicurezza Microsoft 365, in Cloud App Security e negli strumenti SIEM.</li><li>Cercare e implementare gli aggiornamenti software.</li><li>Eseguire simulazioni di attacco per attacchi di spear-phishing, password spray e attacchi con password di forza bruta usando [Il simulatore](attack-simulator.md) di attacco (incluso in [Office 365 Threat Intelligence).](office-365-ti.md)</li><li>Cercare i rischi di condivisione esaminando i report predefiniti in Cloud App Security (nella scheda Analizza).</li><li>Controllare [Compliance Manager](../../compliance/compliance-manager.md) per verificare lo stato delle normative applicabili all'organizzazione (ad esempio GDPR, NIST 800-171).</li></ul>|
|Protezione dalle minacce|Implementare protezioni avanzate per gli account amministratore: <ul><li>Configurare [le workstation con accesso privilegiato](/security/compass/privileged-access-devices) (PAW) per le attività di amministratore.</li><li>Configurare [Azure AD Privileged Identity Management](/azure/active-directory/active-directory-privileged-identity-management-configure).</li><li>Configurare uno strumento siem (Security Information and Event Management) per raccogliere i dati di registrazione da Office 365, Cloud App Security e altri servizi, tra cui AD FS. Il log di controllo archivia i dati solo per 90 giorni. L'acquisizione di questi dati nello strumento SIEM consente di archiviare i dati per un periodo più lungo.</li></ul>|
|Gestione delle identità e degli accessi|<ul><li>Abilitare e applicare l'autenticazione a più fattori per tutti gli utenti.</li><li>Implementare un set di [accesso condizionale e criteri correlati.](microsoft-365-policies-configurations.md)</li></ul>|
|Protezione delle informazioni| Adattare e implementare i criteri di protezione delle informazioni. Queste risorse includono esempi: <ul><li>[Information Protection di Office 365 per il GDPR](/compliance/regulatory/gdpr)</li><li>[Configurare Teams con tre livelli di protezione](../../solutions/configure-teams-three-tiers-protection.md)</li></ul> <p> Usare i criteri di prevenzione della perdita dei dati e gli strumenti di monitoraggio in Microsoft 365 per i dati archiviati in Microsoft 365 (invece di Cloud App Security). <p> Usa Cloud App Security con Microsoft 365 per funzionalità di avviso avanzate (diverse dalla prevenzione della perdita di dati).|
|

## <a name="beyond"></a>Oltre
<a name="Beyond"> </a>

Si tratta di misure di sicurezza importanti che si basano sul lavoro precedente.

****

|Area|Attività|
|---|---|
|Gestione della sicurezza|<ul><li>Continuare a pianificare le azioni seguenti utilizzando Punteggio sicuro ( <https://securescore.office.com> ).</li><li>Continuare a esaminare regolarmente dashboard e report nel Centro sicurezza Microsoft 365, in Cloud App Security e negli strumenti SIEM.</li><li>Continuare a cercare e implementare gli aggiornamenti software.</li><li>Integrare eDiscovery nei processi legali e di risposta alle minacce.</li></ul>|
|Protezione dalle minacce|<ul><li>Implementare [l'accesso con](/windows-server/identity/securing-privileged-access/securing-privileged-access) privilegi sicuri (SPA) per i componenti di identità in locale (AD, AD FS).</li><li>Usa Cloud App Security per monitorare le minacce insider.</li><li>Individuare l'utilizzo saaS IT shadow tramite Cloud App Security.</li></ul>|
|Gestione delle identità e degli accessi|<ul><li>Affinare i criteri e i processi operativi.</li><li>Usare Azure AD Identity Protection per identificare le minacce insider.</li></ul>|
|Protezione delle informazioni|Affinare i criteri di protezione delle informazioni: <ul><li>Etichette di riservatezza e prevenzione della perdita dei dati (DLP) di Microsoft 365 e Office 365 o Azure Information Protection.</li><li>Avvisi e criteri di Cloud App Security.</li></ul>|
|

Vedi anche: [Come mitigare attacchi informatici rapidi come Petya e WannaCrypt.](https://cloudblogs.microsoft.com/microsoftsecure/2018/02/21/how-to-mitigate-rapid-cyberattacks-such-as-petya-and-wannacrypt/)