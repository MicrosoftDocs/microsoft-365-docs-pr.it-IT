---
title: Analisi delle minacce e risposta alle minacce in Office 365
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 12/03/2019
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
ms.openlocfilehash: 63b5579c5a3e52273064f85a901a6b592e7dd939
ms.sourcegitcommit: 8fda7852b2a5baa92b8a365865b014ea6d100bbc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/03/2019
ms.locfileid: "39813736"
---
# <a name="office-365-threat-investigation-and-response"></a>Analisi delle minacce e risposta alle minacce in Office 365

Le funzionalità di ricerca e risposta alle minacce in [office 365 Advanced Threat Protection](office-365-atp.md) aiutano gli analisti e gli amministratori della sicurezza a proteggere gli utenti di Office 365 dell'organizzazione per:
  
- Semplificare l'identificazione, il monitoraggio e la comprensione di attacchi cibernetici
    
- Assistenza per l'indirizzamento rapido delle minacce in Exchange Online, SharePoint Online, OneDrive for business e Microsoft Teams
    
- Fornire informazioni e conoscenze per aiutare le operazioni di sicurezza a impedire la attacchi cibernetici alla propria organizzazione

- Utilizzo della [risposta automatica degli incidenti](automated-investigation-response-office.md) per le minacce critiche basate sulla posta elettronica
    
Le funzionalità di ricerca e di risposta alle minacce consentono di approfondire i rischi e le azioni di risposta correlate disponibili nel &amp; Centro sicurezza e conformità di Office 365. Queste informazioni possono aiutare il team di sicurezza dell'organizzazione a proteggere gli utenti di Office 365 da attacchi basati su file o posta elettronica. Le funzionalità consentono di monitorare i segnali e raccogliere dati provenienti da più origini, ad esempio attività utente, autenticazione, posta elettronica, PC compromessi e incidenti di sicurezza. I decision maker aziendali e gli amministratori globali di Office 365, gli amministratori della sicurezza e gli analisti di sicurezza possono utilizzare queste informazioni per comprendere e rispondere alle minacce per gli utenti di Office 365 e proteggere la proprietà intellettuale.

## <a name="get-acquainted-with-threat-investigation-and-response-tools"></a>Familiarizzare con gli strumenti di ricerca e di risposta alle minacce

Analisi delle minacce e funzionalità di risposta emergono &amp; nel centro sicurezza e conformità, come un insieme di strumenti e flussi di lavoro di risposta, tra cui il [dashboard di minacce](#threat-dashboard), l' [esploratore](#threat-explorer), gli [incidenti](#incidents), il [simulatore di attacco](#attack-simulator)e la [risposta automatica agli incidenti](automated-investigation-response-office.md).
  
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

### <a name="attack-simulator"></a>Simulatore di attacco

Utilizzare simulatore di attacco per configurare ed eseguire attacchi cibernetici realistici nell'organizzazione e identificare le persone vulnerabili prima che un cyberattack reale influisca sulla propria azienda. Per ulteriori informazioni, vedere [Attack Simulator in Office 365](attack-simulator.md).

### <a name="automated-investigation-and-response"></a>Analisi e risposta alle minacce automatizzate

Utilizzare le funzionalità di analisi e risposta automatizzate per risparmiare tempo e risorse per la correlazione di contenuto, dispositivi e persone a rischio di minacce all'interno dell'organizzazione. I processi AIR possono iniziare ogni volta che vengono attivati determinati avvisi o quando vengono avviati dal team delle operazioni di sicurezza. Per altre informazioni, vedere [Risposta automatica agli incidenti in Office 365](automated-investigation-response-office.md). 
  
## <a name="threat-intelligence-widgets"></a>Widget di intelligence per le minacce

Nell'ambito dell'offerta di Office 365 Advanced Threat Protection piano 2, gli analisti di sicurezza possono esaminare i dettagli relativi a una minaccia nota. Ciò è utile per determinare se sono disponibili ulteriori misure preventive/passaggi che possono essere adottati per garantire la sicurezza degli utenti.
  
![Tendenze della sicurezza che mostrano informazioni sulle minacce recenti](../media/11e7d40d-139b-4c56-8d52-c091c8654151.png) 
  
## <a name="how-do-we-get-these-capabilities"></a>Come si ottengono queste funzionalità?

Le funzionalità di ricerca e risposta alle minacce di Office 365 sono incluse in Office 365 Advanced Threat Protection Plan 2 e Enterprise E5. 

> [!TIP]
> Se l'organizzazione dispone di un abbonamento a Office 365 che non include queste funzionalità di analisi e di risposta alle minacce, è possibile acquistare Office 365 Advanced Threat Protection Plan 2 come componente aggiuntivo. Per ulteriori informazioni sulle opzioni di piano, vedere [Descrizione del servizio office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) e [acquistare o modificare un componente aggiuntivo per Office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/buy-or-edit-an-add-on).
  
1. In qualità di amministratore globale di Office 365, [https://admin.microsoft.com](https://admin.microsoft.com) passare a e accedere con l'account aziendale o dell'Istituto di istruzione per Office 365. 
    
2. Scegliere **admin** \> **Billing** per vedere cosa include la sottoscrizione corrente. 
    - Se si vede **office 365 Enterprise E5**, la propria organizzazione dispone di Office 365 Advanced Threat Protection Plan 2 (che include le funzionalità di analisi e di risposta alle minacce). 
    - Se viene visualizzato un abbonamento diverso, ad esempio **office 365 Enterprise E3** o **Office 365 Enterprise E1**, è consigliabile aggiungere Office 365 Advanced Threat Protection Plan 2. A tale scopo, scegliere **+ Aggiungi sottoscrizione**.
    
3. Nell'interfaccia di amministrazione di Microsoft 365 scegliere **utenti** \> **attivi**.
    
4. Assegnare le licenze di Office 365 Advanced Threat Protection Plan 2 a tutti gli utenti attivi. Solo gli utenti che dispongono di una licenza per questo verranno visualizzati nei report, ad esempio in Esplora risorse.
    
5. Assegnare i ruoli agli utenti dell'organizzazione che lavoreranno con la protezione avanzata dalle minacce di Office 365. Vedere [fornire agli utenti l'accesso al centro sicurezza &amp; e conformità di Office 365](grant-access-to-the-security-and-compliance-center.md)e fare riferimento alla tabella seguente:<br/><br/>


  |**Per eseguire questa attività...** <br/> |**È necessario disporre di questi ruoli** <br/> |  
  |:-----|:-----|
  |Utilizzare il dashboard di minacce (o il nuovo [dashboard di sicurezza](security-dashboard.md))<br/> Visualizzare le informazioni sulle minacce recenti o correnti  <br/> |Uno dei seguenti valori (assegnati in Azure Active Directory o nel centro sicurezza &amp; e conformità di Office 365): <br/>- **Amministratore globale di Office 365**  <br/> - **Amministratore della sicurezza** <br/>- **Lettore di sicurezza** <br/> |
  |Utilizzo di [Esplora minacce (e rilevamenti in tempo reale)](threat-explorer.md) per l'analisi delle minacce  <br/> |Uno dei seguenti valori (assegnati in Azure Active Directory o nel centro sicurezza &amp; e conformità di Office 365): <br/>- **Amministratore globale di Office 365**  <br/> - **Amministratore della sicurezza** <br/>- **Lettore di sicurezza** <br/> |
  |Visualizzare gli incidenti (noti anche come indagini) <br/> Aggiungere messaggi di posta elettronica a un evento imprevisto  <br/> |Uno dei seguenti valori (assegnati in Azure Active Directory o nel centro sicurezza &amp; e conformità di Office 365): <br/>- **Amministratore globale di Office 365**  <br/> - **Amministratore della sicurezza** <br/>- **Lettore di sicurezza** <br/>  <br/> |
  |Attivare le azioni di posta elettronica in un evento imprevisto  <br/> Individuare ed eliminare i messaggi di posta elettronica sospetti  <br/> |Uno dei seguenti valori (assegnati in Azure Active Directory o nel centro sicurezza &amp; e conformità di Office 365): <br/>- **Amministratore globale di Office 365**  <br/> - **Amministratore della sicurezza** <br/>---e---<br/>- **Search and Purge** (assegnato solo nel centro sicurezza &amp; e conformità di Office 365)  <br/> |
  |Integrazione di Office 365 Advanced Threat Protection Plan 2 con Microsoft Defender ATP  <br/> Integrazione di Office 365 Advanced Threat Protection Plan 2 con un server SIEM  <br/> |Uno dei seguenti valori (assegnati in Azure Active Directory o nel centro sicurezza &amp; e conformità di Office 365): <br/>- **Amministratore globale di Office 365**  <br/> - **Amministratore della sicurezza** <br/>---e---<br/>Un ruolo appropriato assegnato in altre applicazioni, ad esempio Microsoft Defender Security Center o un server SIEM.  <br/> |
   
Per informazioni sui ruoli, sui gruppi di ruoli e sulle autorizzazioni, vedere [Permissions in &amp; The Office 365 Security Compliance Center](permissions-in-the-security-and-compliance-center.md).
    
## <a name="next-steps"></a>Passaggi successivi

- [Informazioni sui tracker di minacce: nuove e degne di nota](threat-trackers.md)
    
- [Individuare ed esaminare messaggi di posta elettronica dannosi recapitati (Office 365 Threat Investigation and Response)](investigate-malicious-email-that-was-delivered.md)
    
- [Integrazione di Office 365 Threat Investigation and Response with Microsoft Defender Advanced Threat Protection](integrate-office-365-ti-with-wdatp.md)
    
- [Informazioni sul simulatore di attacco](attack-simulator.md)
  

