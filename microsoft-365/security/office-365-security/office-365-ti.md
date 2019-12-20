---
title: Office 365 Threat Investigation and response capabilities in Office 365 Advanced Threat Protection piano 2
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 12/09/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 32405da5-bee1-4a4b-82e5-8399df94c512
ms.collection:
- M365-security-compliance
description: Scoprire in che modo le funzionalità di intelligence in Office 365 Advanced Threat Protection consentono di ricercare le minacce per la propria organizzazione, di rispondere a malware, phishing e altri attacchi che Office 365 ha rilevato per conto dell'utente e di cercare una minaccia indicatori.
ms.openlocfilehash: 45c12647b999e626cb620046aabc95fb4bfa8f4c
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2019
ms.locfileid: "40808121"
---
# <a name="office-365-threat-investigation-and-response"></a>Analisi delle minacce e risposta alle minacce in Office 365

Le funzionalità di ricerca e risposta alle minacce in [office 365 Advanced Threat Protection](office-365-atp.md) aiutano gli analisti e gli amministratori della sicurezza a proteggere gli utenti di Office 365 dell'organizzazione per:
- Semplificare l'identificazione, il monitoraggio e la comprensione di attacchi cibernetici
- Assistenza per l'indirizzamento rapido delle minacce in Exchange Online, SharePoint Online, OneDrive for business e Microsoft Teams
- Fornire informazioni e conoscenze per aiutare le operazioni di sicurezza a impedire la attacchi cibernetici alla propria organizzazione
- Utilizzo di [indagini e risposte automatiche in Office 365](automated-investigation-response-office.md) per minacce critiche basate sulla posta elettronica
    
Le funzionalità di ricerca e di risposta alle minacce consentono di approfondire i rischi e le azioni di risposta correlate disponibili nel &amp; Centro sicurezza e conformità di Office 365. Queste informazioni possono aiutare il team di sicurezza dell'organizzazione a proteggere gli utenti di Office 365 da attacchi basati su file o posta elettronica. Le funzionalità consentono di monitorare i segnali e raccogliere dati provenienti da più origini, ad esempio attività utente, autenticazione, posta elettronica, PC compromessi e incidenti di sicurezza. I decision maker aziendali e il team delle operazioni di sicurezza possono utilizzare queste informazioni per comprendere e rispondere alle minacce per la propria organizzazione e proteggere la propria proprietà intellettuale.

## <a name="get-acquainted-with-threat-investigation-and-response-tools"></a>Familiarizzare con gli strumenti di ricerca e di risposta alle minacce

Superficie delle funzionalità di ricerca e risposta alle minacce &amp; nel centro sicurezza e conformità, come un insieme di strumenti e flussi di lavoro di risposta, inclusi i seguenti:
- [Dashboard di minacce](#threat-dashboard)
- [Explorer](#threat-explorer)
- [Incidenti](#incidents)
- [Simulatore di attacchi](#attack-simulator)
- [Analisi e risposta alle minacce automatizzate](automated-investigation-response-office.md)

### <a name="threat-dashboard"></a>Dashboard di minacce

Utilizzare il dashboard di minacce (indicato anche come [dashboard di sicurezza](security-dashboard.md)) per vedere rapidamente quali minacce sono state affrontate e come modo visivo per segnalare ai responsabili delle decisioni aziendali come i servizi di Office 365 proteggano la propria azienda.
  
![Dashboard di minacce](../media/ce013a31-3f80-4d09-bb95-bfb7623b8bc4.png)
  
&amp; Per visualizzare e utilizzare questo dashboard, nel centro sicurezza e conformità di Office 365 accedere a **Threat Management** \> **Dashboard**.
  
### <a name="threat-explorer"></a>Esplora minacce

Utilizzare [Esplora minacce (e rilevamenti in tempo reale)](threat-explorer.md) per analizzare le minacce, vedere il volume degli attacchi nel tempo e analizzare i dati dalle famiglie di minacce, dall'infrastruttura di attacco e altro ancora. L'esploratore di minacce (noto anche come esploratore) è il punto di partenza per il flusso di lavoro dell'analisi di qualsiasi analista di sicurezza.
  
![Esplora minacce](../media/7a7cecee-17f0-4134-bcb8-7cee3f3c3890.png)
  
&amp; Per visualizzare e utilizzare questo report, nel centro sicurezza e conformità di Office 365 accedere a **gestione** \> minacce. ****
  
### <a name="incidents"></a>Incidenti

Utilizzare l'elenco degli eventi non consentiti (anche questo è denominato indagini) per visualizzare un elenco degli incidenti di sicurezza in volo. Gli eventi non consentiti vengono utilizzati per tenere conto di minacce quali messaggi di posta elettronica sospetti e per eseguire ulteriori indagini e correggere i problemi.
  
![Elenco degli incidenti di minacce correnti in Office 365](../media/acadd4c7-d2de-4146-aeb8-90cfad805a9c.png)
  
Per visualizzare l'elenco degli eventi imprevisti correnti per l'organizzazione, nel centro &amp; conformità sicurezza accedere a operazioni di \> **Verifica** \> degli **incidenti**di **gestione delle minacce** .
  
![Nel centro sicurezza &amp; e conformità scegliere Threat Management \> Review](../media/e0f46454-fa38-40f0-a120-b595614d1d22.png)

### <a name="attack-simulator"></a>Simulatore di attacchi

Utilizzare simulatore di attacco per configurare ed eseguire attacchi cibernetici realistici nell'organizzazione e identificare le persone vulnerabili prima che un cyberattack reale influisca sulla propria azienda. Per ulteriori informazioni, vedere [Attack Simulator in Office 365](attack-simulator.md).

### <a name="automated-investigation-and-response"></a>Analisi e risposta alle minacce automatizzate

Utilizzare le funzionalità di analisi e risposta automatizzate per risparmiare tempo e risorse per la correlazione di contenuto, dispositivi e persone a rischio di minacce all'interno dell'organizzazione. I processi AIR possono iniziare ogni volta che vengono attivati determinati avvisi o quando vengono avviati dal team delle operazioni di sicurezza. Per ulteriori informazioni, vedere [Automatic Investigation and Response in Office 365](automated-investigation-response-office.md). 
  
## <a name="threat-intelligence-widgets"></a>Widget di intelligence per le minacce

Nell'ambito dell'offerta di Office 365 Advanced Threat Protection piano 2, gli analisti di sicurezza possono esaminare i dettagli relativi a una minaccia nota. Ciò è utile per determinare se sono disponibili ulteriori misure preventive/passaggi che possono essere adottati per garantire la sicurezza degli utenti.
  
![Tendenze della sicurezza che mostrano informazioni sulle minacce recenti](../media/11e7d40d-139b-4c56-8d52-c091c8654151.png) 
  
## <a name="how-do-we-get-these-capabilities"></a>Come si ottengono queste funzionalità?

Le funzionalità di ricerca e risposta alle minacce di Office 365 sono incluse in Office 365 Advanced Threat Protection Plan 2, incluso in Enterprise E5 o come componente aggiuntivo di determinate sottoscrizioni. Per ulteriori informazioni, vedere [Office 365 ATP Plan 1 e Plan 2](office-365-atp.md#office-365-atp-plan-1-and-plan-2).

## <a name="required-roles-and-permissions"></a>Ruoli e autorizzazioni necessari

Office 365 Advanced Threat Protection utilizza il controllo di accesso basato sui ruoli. Le autorizzazioni vengono assegnate tramite alcuni ruoli in Azure Active Directory, nell'interfaccia di amministrazione di Microsoft 365 o nel centro protezione & conformità di Office 365.

> [!TIP]
> Anche se alcuni ruoli, ad esempio amministratore della sicurezza, possono essere assegnati nel centro conformità & sicurezza di Office 365, considerare l'utilizzo dell'interfaccia di amministrazione di Microsoft 365 o di Azure Active Directory. Per informazioni sui ruoli, sui gruppi di ruoli e sulle autorizzazioni, vedere le risorse seguenti:
> - [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md)
> - [Autorizzazioni del ruolo di amministratore in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)


|Attività |Ruoli e autorizzazioni |  
|:-----|:-----|
|Utilizzare il dashboard di minacce (o il nuovo [dashboard di sicurezza](security-dashboard.md))<br/> <br/>Visualizzare le informazioni sulle minacce recenti o correnti  <br/> |Uno dei seguenti: <br/>- **Amministratore globale di Office 365**  <br/> - **Amministratore della sicurezza** <br/>- **Lettore di sicurezza** <br/> <br/>Questi ruoli possono essere assegnati in Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) o nell'interfaccia di amministrazione di Microsoft 365[https://admin.microsoft.com](https://admin.microsoft.com)(). |
|Utilizzo di [Esplora minacce (e rilevamenti in tempo reale)](threat-explorer.md) per l'analisi delle minacce  <br/> |Uno dei seguenti: <br/>- **Amministratore globale di Office 365**  <br/> - **Amministratore della sicurezza** <br/>- **Lettore di sicurezza** <br/> <br/>Questi ruoli possono essere assegnati in Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) o nell'interfaccia di amministrazione di Microsoft 365[https://admin.microsoft.com](https://admin.microsoft.com)(). |
|Visualizzare gli incidenti (noti anche come indagini) <br/> Aggiungere messaggi di posta elettronica a un evento imprevisto  <br/> |Uno dei seguenti: <br/>- **Amministratore globale di Office 365**  <br/> - **Amministratore della sicurezza** <br/>- **Lettore di sicurezza** <br/> <br/>Questi ruoli possono essere assegnati in Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) o nell'interfaccia di amministrazione di Microsoft 365[https://admin.microsoft.com](https://admin.microsoft.com)().  |
|Attivare le azioni di posta elettronica in un evento imprevisto <br/> <br/> Individuare ed eliminare i messaggi di posta elettronica sospetti  <br/> |Uno dei seguenti: <br/>- **Amministratore globale di Office 365**  <br/> - **Amministratore della sicurezza** più il ruolo **di ricerca ed eliminazione**<br/><br/>I ruoli amministratore **globale** e **amministratore della sicurezza** possono essere assegnati in Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) o nell'interfaccia di amministrazione di Microsoft[https://admin.microsoft.com](https://admin.microsoft.com)365 (). <br/><br/>Il ruolo **Search and Purge** deve essere assegnato al centro[https://protection.office.com](https://protection.office.com)sicurezza & conformità di Office 365. |
|Integrazione di Office 365 Advanced Threat Protection Plan 2 con Microsoft Defender Advanced Threat Protection  <br/><br/> Integrazione di Office 365 Advanced Threat Protection Plan 2 con un server SIEM  <br/> |L' **amministratore globale di Office 365** o il ruolo di **amministratore della sicurezza** assegnato in Azure Active Directory[https://portal.azure.com](https://portal.azure.com)() o nell'interfaccia di amministrazione di[https://admin.microsoft.com](https://admin.microsoft.com)Microsoft 365 ().<br/>--- **più** ---<br/>Un ruolo appropriato assegnato in altre applicazioni, ad esempio il [Centro sicurezza di Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles) o il server Siem.  |
   
    
## <a name="next-steps"></a>Passaggi successivi

- [Informazioni sui tracker di minacce: nuove e degne di nota](threat-trackers.md)
    
- [Individuare ed esaminare messaggi di posta elettronica dannosi recapitati (Office 365 Threat Investigation and Response)](investigate-malicious-email-that-was-delivered.md)
    
- [Integrazione di Office 365 Threat Investigation and Response with Microsoft Defender Advanced Threat Protection](integrate-office-365-ti-with-wdatp.md)
    
- [Informazioni sul simulatore di attacco](attack-simulator.md)
  

