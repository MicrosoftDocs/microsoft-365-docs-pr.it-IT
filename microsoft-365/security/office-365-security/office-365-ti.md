---
title: Analisi delle minacce & funzionalità di risposta - Microsoft Defender per Office 365 Piano 2
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 12/09/2019
audience: Admin
ms.topic: overview
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
description: Informazioni sulle funzionalità di analisi delle minacce e di risposta in Microsoft Defender per Office 365 Piano.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b0a9ff9c06f7e97d6f74c901c156bfae6c9eb91d
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083705"
---
# <a name="threat-investigation-and-response"></a>Analisi e risposta alle minacce

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Microsoft Defender per Office 365 Piano 2](defender-for-office-365.md)


Le funzionalità di analisi e risposta alle minacce in [Microsoft Defender per Office 365](defender-for-office-365.md) aiutare gli analisti e gli amministratori della sicurezza a proteggere la Microsoft 365 dell'organizzazione per gli utenti aziendali:

- Semplifica l'identificazione, il monitoraggio e la comprensione degli attacchi informatici
- Aiutare a risolvere rapidamente le minacce in Exchange Online, SharePoint Online, OneDrive for Business e Microsoft Teams
- Fornire informazioni dettagliate e conoscenze per aiutare le operazioni di sicurezza a prevenire attacchi informatici contro l'organizzazione
- Utilizzo di [indagini e risposte automatizzate in Office 365](automated-investigation-response-office.md) minacce critiche basate sulla posta elettronica

Le funzionalità di analisi e risposta alle minacce forniscono informazioni dettagliate sulle minacce e sulle azioni di risposta correlate disponibili nel portale Microsoft 365 Defender sicurezza. Queste informazioni dettagliate possono aiutare il team di sicurezza dell'organizzazione a proteggere gli utenti da attacchi basati su file o posta elettronica. Le funzionalità consentono di monitorare i segnali e raccogliere dati da più origini, ad esempio attività degli utenti, autenticazione, posta elettronica, PC compromessi e incidenti di sicurezza. I decision maker aziendali e il team delle operazioni di sicurezza possono utilizzare queste informazioni per comprendere e rispondere alle minacce contro l'organizzazione e proteggere la proprietà intellettuale.

## <a name="get-acquainted-with-threat-investigation-and-response-tools"></a>Acquisire familiarità con gli strumenti di indagine e risposta alle minacce

Le funzionalità di analisi e risposta alle minacce si esertono nel portale Microsoft 365 Defender, sotto forma di un insieme di strumenti e flussi di lavoro di risposta, tra cui:

- [Explorer](#explorer)
- [Eventi imprevisti](#incidents)
- [Formazione per la simulazione di attacchi](attack-simulation-training.md)
- [Analisi e risposta automatizzate](automated-investigation-response-office.md)

### <a name="explorer"></a>Explorer

Usa [Esplora risorse (e rilevamenti](threat-explorer.md) in tempo reale) per analizzare le minacce, vedere il volume di attacchi nel tempo e analizzare i dati in base alle famiglie di minacce, all'infrastruttura degli utenti malintenzionati e altro ancora. Explorer (noto anche come Threat Explorer) è il punto di partenza per il flusso di lavoro di indagine di qualsiasi analista della sicurezza.

![Esplora minacce](../../media/7a7cecee-17f0-4134-bcb8-7cee3f3c3890.png)

Per visualizzare e usare questo report, nel portale Microsoft 365 Defender, passare a **Posta elettronica & collaborazione**  >  **Explorer.**

### <a name="incidents"></a>Eventi imprevisti

Usa l'elenco Eventi imprevisti (denominato anche Indagini) per visualizzare un elenco degli incidenti di sicurezza in volo. Gli eventi imprevisti vengono utilizzati per tenere traccia di minacce come messaggi di posta elettronica sospetti e per eseguire ulteriori indagini e correzioni.

![Elenco degli eventi imprevisti di Office 365](../../media/acadd4c7-d2de-4146-aeb8-90cfad805a9c.png)

Per visualizzare l'elenco degli eventi imprevisti correnti per l'organizzazione, nel portale di Microsoft 365 Defender passare a Eventi imprevisti **&**  >  **avvisi eventi imprevisti**.

![Nel Centro sicurezza & conformità scegliere Verifica gestione \> minacce](../../media/e0f46454-fa38-40f0-a120-b595614d1d22.png)

### <a name="attack-simulation-training"></a>Formazione per la simulazione di attacchi

Usa la formazione sulla simulazione di attacchi per configurare ed eseguire attacchi informatici realistici nell'organizzazione e identificare le persone vulnerabili prima che un attacco informatico reale influisca sull'azienda. Per ulteriori informazioni, vedere [Simulate a phishing attack](attack-simulation-training.md).

Per visualizzare e usare questa funzionalità nel portale di Microsoft 365 Defender, passare a **Email & collaboration** Attack simulation  >  **training**.

### <a name="automated-investigation-and-response"></a>Indagine e reazione automatizzate

Usa le funzionalità di analisi e risposta automatizzate (AIR) per risparmiare tempo e fatica correlati a contenuti, dispositivi e persone a rischio di minacce nell'organizzazione. I processi AIR possono iniziare ogni volta che vengono attivati determinati avvisi o quando vengono avviati dal team delle operazioni di sicurezza. Per ulteriori informazioni, vedere analisi e risposta [automatizzate in Office 365](automated-investigation-response-office.md).

## <a name="threat-intelligence-widgets"></a>Widget di Intelligence per le minacce

Nell'ambito dell'offerta Microsoft Defender for Office 365 Piano 2, gli analisti della sicurezza possono esaminare i dettagli su una minaccia nota. Ciò è utile per determinare se è possibile adottare misure/misure preventive aggiuntive per mantenere gli utenti al sicuro.

![Tendenze della sicurezza che mostrano informazioni sulle minacce recenti](../../media/11e7d40d-139b-4c56-8d52-c091c8654151.png)

## <a name="how-do-we-get-these-capabilities"></a>Come si ottengono queste funzionalità?

Microsoft 365 le funzionalità di analisi e risposta alle minacce sono incluse in Microsoft Defender per Office 365 Piano 2, incluso in Enterprise E5 o come componente aggiuntivo per determinate sottoscrizioni. Per altre informazioni, vedi [Defender per Office 365 Piano 1 e Piano 2.](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2)

## <a name="required-roles-and-permissions"></a>Ruoli e autorizzazioni necessari

Microsoft Defender per Office 365 usa il controllo dell'accesso basato sui ruoli. Le autorizzazioni vengono assegnate tramite determinati ruoli in Azure Active Directory, interfaccia di amministrazione di Microsoft 365 o nel Microsoft 365 Defender portale.

> [!TIP]
> Anche se alcuni ruoli, ad esempio Amministratore sicurezza, possono essere assegnati nel portale di Microsoft 365 Defender, è consigliabile utilizzare il interfaccia di amministrazione di Microsoft 365 o Azure Active Directory. Per informazioni sui ruoli, i gruppi di ruoli e le autorizzazioni, vedere le risorse seguenti:
>
> - [Autorizzazioni nel portale di Microsoft 365 Defender](permissions-microsoft-365-security-center.md)
> - [Autorizzazioni del ruolo di amministratore in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)

<br>

****

|Attività|Ruoli e autorizzazioni|
|---|---|
|Usare il dashboard di gestione delle & delle minacce (o il nuovo [dashboard di sicurezza)](security-dashboard.md) <p> Visualizzare informazioni sulle minacce recenti o correnti|Uno dei seguenti: <ul><li>**Amministratore globale**</li><li>**Amministratore della sicurezza**</li><li>**Lettore sicurezza**</li></ul> <p> Questi ruoli possono essere assegnati in Azure Active Directory ( ) o nella interfaccia di amministrazione di Microsoft 365 <https://portal.azure.com> ( <https://admin.microsoft.com> ).|
|Usare [Esplora risorse (e i rilevamenti](threat-explorer.md) in tempo reale) per analizzare le minacce|Uno dei seguenti: <ul><li>**Amministratore globale**</li><li>**Amministratore della sicurezza**</li><li>**Lettore sicurezza**</li></ul> <p> Questi ruoli possono essere assegnati in Azure Active Directory ( ) o nella interfaccia di amministrazione di Microsoft 365 <https://portal.azure.com> ( <https://admin.microsoft.com> ).|
|Visualizzare gli eventi imprevisti (denominati anche indagini) <p> Aggiungere messaggi di posta elettronica a un evento imprevisto|Uno dei seguenti: <ul><li>**Amministratore globale**</li><li>**Amministratore della sicurezza**</li><li>**Lettore sicurezza**</li></ul> <p> Questi ruoli possono essere assegnati in Azure Active Directory ( ) o nella interfaccia di amministrazione di Microsoft 365 <https://portal.azure.com> ( <https://admin.microsoft.com> ).|
|Attivare azioni di posta elettronica in un evento imprevisto <p> Trovare ed eliminare messaggi di posta elettronica sospetti|Uno dei seguenti: <ul><li>**Amministratore globale**</li><li>**Security Administrator** plus the **Search and Purge** role</li></ul> <p> I **ruoli Amministratore** globale e **Amministratore** sicurezza possono essere assegnati in Azure Active Directory ( ) o interfaccia di amministrazione di Microsoft 365 <https://portal.azure.com> ( <https://admin.microsoft.com> ). <p> Il **ruolo Ricerca ed eliminazione** deve essere assegnato nei ruoli di collaborazione & posta elettronica nel portale di Microsoft 36 Defender (  <https://security.microsoft.com> ).|
|Integrare Microsoft Defender per Office 365 Piano 2 con Microsoft Defender for Endpoint <p> Integrare Microsoft Defender per Office 365 Piano 2 con un server SIEM|Il **ruolo Amministratore globale** o **Amministratore** sicurezza assegnato in Azure Active Directory ( ) o nel interfaccia di amministrazione di Microsoft 365 <https://portal.azure.com> ( <https://admin.microsoft.com> ). <p> --- **plus** --- <p> Un ruolo appropriato assegnato in applicazioni aggiuntive (ad esempio [Microsoft Defender Security Center](/windows/security/threat-protection/microsoft-defender-atp/user-roles) o il server SIEM).|
|

## <a name="next-steps"></a>Passaggi successivi

- [Informazioni su Threat Trackers - New e Noteworthy](threat-trackers.md)
- [Trovare e analizzare i messaggi di posta elettronica dannosi recapitati (Office 365 e risposta alle minacce)](investigate-malicious-email-that-was-delivered.md)
- [Integrare Office 365 analisi e risposta alle minacce con Microsoft Defender for Endpoint](integrate-office-365-ti-with-mde.md)
- [Simulare un attacco di phishing](attack-simulation-training.md)
