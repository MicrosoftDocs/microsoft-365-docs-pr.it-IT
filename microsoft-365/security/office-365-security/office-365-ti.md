---
title: Analisi delle minacce & funzionalità di risposta-Microsoft Defender per Office 365 piano 2
f1.keywords:
- NOCSH
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
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Informazioni sulle funzionalità di ricerca e risposta alle minacce in Microsoft Defender per Office 365 piano.
ms.openlocfilehash: dc6a3dec096b6834d024cc4ff74a5b7600c33d45
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794233"
---
# <a name="threat-investigation-and-response"></a>Analisi e risposta alle minacce

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Le funzionalità di ricerca e risposta alle minacce in [Microsoft Defender per Office 365](office-365-atp.md) aiutano gli analisti e gli amministratori della protezione a proteggere gli utenti di Microsoft 365 per le aziende dell'organizzazione:

- Semplificare l'identificazione, il monitoraggio e la comprensione di attacchi cibernetici
- Assistenza per l'indirizzamento rapido delle minacce in Exchange Online, SharePoint Online, OneDrive for business e Microsoft Teams
- Fornire informazioni e conoscenze per aiutare le operazioni di sicurezza a impedire la attacchi cibernetici alla propria organizzazione
- Utilizzo di [indagini e risposte automatiche in Office 365](automated-investigation-response-office.md) per minacce critiche basate sulla posta elettronica

Le funzionalità di ricerca e di risposta alle minacce forniscono informazioni dettagliate sui rischi e sulle azioni di risposta correlate disponibili nel centro sicurezza & conformità. Queste informazioni possono aiutare il team di sicurezza dell'organizzazione a proteggere gli utenti dagli attacchi basati su file o posta elettronica. Le funzionalità consentono di monitorare i segnali e raccogliere dati provenienti da più origini, ad esempio attività utente, autenticazione, posta elettronica, PC compromessi e incidenti di sicurezza. I decision maker aziendali e il team delle operazioni di sicurezza possono utilizzare queste informazioni per comprendere e rispondere alle minacce per la propria organizzazione e proteggere la propria proprietà intellettuale.

## <a name="get-acquainted-with-threat-investigation-and-response-tools"></a>Familiarizzare con gli strumenti di ricerca e di risposta alle minacce

L'analisi delle minacce e la superficie delle funzionalità di risposta nel centro sicurezza & Compliance, come un insieme di strumenti e flussi di lavoro di risposta, tra cui:

- [Dashboard di minacce](#threat-dashboard)
- [Explorer](#threat-explorer)
- [Eventi imprevisti](#incidents)
- [Simulatore di attacchi](#attack-simulator)
- [Analisi e risposta automatizzate](automated-investigation-response-office.md)

### <a name="threat-dashboard"></a>Dashboard di minacce

Utilizzare il dashboard di minacce (indicato anche come [dashboard di sicurezza](security-dashboard.md)) per vedere rapidamente quali minacce sono state affrontate e come modo visivo per segnalare ai responsabili delle decisioni aziendali come i servizi di Microsoft 365 proteggono l'azienda.

![Dashboard di minacce](../../media/ce013a31-3f80-4d09-bb95-bfb7623b8bc4.png)

Per visualizzare e utilizzare questo dashboard, nel centro sicurezza & conformità, accedere a **Threat Management** \> **Dashboard**.

### <a name="threat-explorer"></a>Esplora minacce

Utilizzare [Esplora minacce (e rilevamenti in tempo reale)](threat-explorer.md) per analizzare le minacce, vedere il volume degli attacchi nel tempo e analizzare i dati dalle famiglie di minacce, dall'infrastruttura di attacco e altro ancora. L'esploratore di minacce (noto anche come esploratore) è il punto di partenza per il flusso di lavoro dell'analisi di qualsiasi analista di sicurezza.

![Esplora minacce](../../media/7a7cecee-17f0-4134-bcb8-7cee3f3c3890.png)

Per visualizzare e utilizzare questo report, nel centro sicurezza & conformità accedere a **gestione minacce** \> .

### <a name="incidents"></a>Eventi imprevisti

Utilizzare l'elenco degli eventi non consentiti (anche questo è denominato indagini) per visualizzare un elenco degli incidenti di sicurezza in volo. Gli eventi non consentiti vengono utilizzati per tenere conto di minacce quali messaggi di posta elettronica sospetti e per eseguire ulteriori indagini e correggere i problemi.

![Elenco degli incidenti di minacce correnti in Office 365](../../media/acadd4c7-d2de-4146-aeb8-90cfad805a9c.png)

Per visualizzare l'elenco degli incidenti correnti per l'organizzazione, nel centro sicurezza & conformità, accedere a operazioni di  \> **Verifica** degli \> **incidenti** di gestione delle minacce.

![Nel centro sicurezza & conformità scegliere Threat Management \> Review](../../media/e0f46454-fa38-40f0-a120-b595614d1d22.png)

### <a name="attack-simulator"></a>Simulatore di attacchi

Utilizzare simulatore di attacco per configurare ed eseguire attacchi cibernetici realistici nell'organizzazione e identificare le persone vulnerabili prima che un cyberattack reale influisca sulla propria azienda. Per ulteriori informazioni, vedere [Attack Simulator in Office 365](attack-simulator.md).

### <a name="automated-investigation-and-response"></a>Analisi e risposta alle minacce automatizzate

Utilizzare le funzionalità di analisi e risposta automatizzate per risparmiare tempo e risorse per la correlazione di contenuto, dispositivi e persone a rischio di minacce all'interno dell'organizzazione. I processi AIR possono iniziare ogni volta che vengono attivati determinati avvisi o quando vengono avviati dal team delle operazioni di sicurezza. Per ulteriori informazioni, vedere [Automatic Investigation and Response in Office 365](automated-investigation-response-office.md).

## <a name="threat-intelligence-widgets"></a>Widget di intelligence per le minacce

Nell'ambito dell'offerta di Microsoft Defender per Office 365 piano 2, gli analisti di sicurezza possono esaminare i dettagli relativi a una minaccia nota. Ciò è utile per determinare se sono disponibili ulteriori misure preventive/passaggi che possono essere adottati per garantire la sicurezza degli utenti.

![Tendenze della sicurezza che mostrano informazioni sulle minacce recenti](../../media/11e7d40d-139b-4c56-8d52-c091c8654151.png)

## <a name="how-do-we-get-these-capabilities"></a>Come si ottengono queste funzionalità?

Microsoft 365 Threat Investigation and response capabilities sono incluse in Microsoft Defender per Office 365 piano 2, incluso in Enterprise E5 o come componente aggiuntivo di determinate sottoscrizioni. Per ulteriori informazioni, vedere [difensore per Office 365 piano 1 e piano 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2).

## <a name="required-roles-and-permissions"></a>Ruoli e autorizzazioni necessari

Microsoft Defender per Office 365 utilizza il controllo di accesso basato sui ruoli. Le autorizzazioni vengono assegnate tramite alcuni ruoli in Azure Active Directory, nell'interfaccia di amministrazione di Microsoft 365 o nel centro sicurezza & Compliance.

> [!TIP]
> Anche se alcuni ruoli, ad esempio amministratore della sicurezza, possono essere assegnati nel centro sicurezza & Compliance, considerare l'utilizzo dell'interfaccia di amministrazione di Microsoft 365 o di Azure Active Directory. Per informazioni sui ruoli, sui gruppi di ruoli e sulle autorizzazioni, vedere le risorse seguenti:
>
> - [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md)
>
> - [Autorizzazioni del ruolo di amministratore in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)

****

|Attività|Ruoli e autorizzazioni|
|---|---|
|Utilizzare il dashboard di minacce (o il nuovo [dashboard di sicurezza](security-dashboard.md)) <p> Visualizzare le informazioni sulle minacce recenti o correnti|Uno dei seguenti: <ul><li>**Amministratore globale**</li><li>**Amministratore della sicurezza**</li><li>**Lettore di sicurezza**</li></ul> <p> Questi ruoli possono essere assegnati in Azure Active Directory ( <https://portal.azure.com> ) o nell'interfaccia di amministrazione di Microsoft 365 ( <https://admin.microsoft.com> ).|
|Utilizzo di [Esplora minacce (e rilevamenti in tempo reale)](threat-explorer.md) per l'analisi delle minacce|Uno dei seguenti: <ul><li>**Amministratore globale**</li><li>**Amministratore della sicurezza**</li><li>**Lettore di sicurezza**</li></ul> <p> Questi ruoli possono essere assegnati in Azure Active Directory ( <https://portal.azure.com> ) o nell'interfaccia di amministrazione di Microsoft 365 ( <https://admin.microsoft.com> ).|
|Visualizzare gli incidenti (noti anche come indagini) <p> Aggiungere messaggi di posta elettronica a un evento imprevisto|Uno dei seguenti: <ul><li>**Amministratore globale**</li><li>**Amministratore della sicurezza**</li><li>**Lettore di sicurezza**</li></ul> <p> Questi ruoli possono essere assegnati in Azure Active Directory ( <https://portal.azure.com> ) o nell'interfaccia di amministrazione di Microsoft 365 ( <https://admin.microsoft.com> ).|
|Attivare le azioni di posta elettronica in un evento imprevisto <p> Individuare ed eliminare i messaggi di posta elettronica sospetti|Uno dei seguenti: <ul><li>**Amministratore globale**</li><li>**Amministratore della sicurezza** più il ruolo **di ricerca ed eliminazione**</li></ul> <p> I ruoli amministratore **globale** e **amministratore della sicurezza** possono essere assegnati in Azure Active Directory ( <https://portal.azure.com> ) o nell'interfaccia di amministrazione di Microsoft 365 ( <https://admin.microsoft.com> ). <p> Il ruolo **Search and Purge** deve essere assegnato al centro sicurezza & Compliance ( <https://protection.office.com> ).|
|Integrazione di Microsoft Defender per Office 365 piano 2 con Microsoft Defender per endpoint  <p> Integrazione di Microsoft Defender per Office 365 piano 2 con un server SIEM|L' **amministratore globale** o il ruolo di **amministratore della sicurezza** assegnato in Azure Active Directory ( <https://portal.azure.com> ) o nell'interfaccia di amministrazione di Microsoft 365 ( <https://admin.microsoft.com> ). <p> --- **più** --- <p> Ruolo appropriato assegnato in altre applicazioni, ad esempio il [Centro sicurezza di Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles) o il server Siem.|
|

## <a name="next-steps"></a>Passaggi successivi

- [Informazioni sui tracker di minacce: nuove e degne di nota](threat-trackers.md)

- [Individuare ed esaminare messaggi di posta elettronica dannosi recapitati (Office 365 Threat Investigation and Response)](investigate-malicious-email-that-was-delivered.md)

- [Integrazione di Office 365 Threat Investigation and Response with Microsoft Defender for endpoint](integrate-office-365-ti-with-wdatp.md)

- [Informazioni sul simulatore di attacco](attack-simulator.md)
