---
title: Analisi delle & funzionalità di risposta alle minacce - Microsoft Defender per Office 365 Piano 2
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
description: Informazioni sulle funzionalità di analisi e risposta alle minacce in Microsoft Defender per Office 365 Plan.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 32b23dca0d4cb70407ce91a652e458b729b3c12f
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150737"
---
# <a name="threat-investigation-and-response"></a>Analisi e risposta alle minacce

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
-    [Microsoft Defender per Office 365 piano 2](https://go.microsoft.com/fwlink/?linkid=2148715)


Le funzionalità di analisi e risposta alle minacce in [Microsoft Defender per Office 365](office-365-atp.md) consentono agli analisti e agli amministratori della sicurezza di proteggere gli utenti di Microsoft 365 per le aziende dell'organizzazione tramite:

- Semplificando l'identificazione, il monitoraggio e la comprensione degli attacchi informatici
- Aiutare a risolvere rapidamente le minacce in Exchange Online, SharePoint Online, OneDrive for Business e Microsoft Teams
- Fornire informazioni dettagliate e conoscenze per aiutare le operazioni di sicurezza a prevenire attacchi informatici contro l'organizzazione
- Utilizzo di [analisi e risposta automatizzate in Office 365](automated-investigation-response-office.md) per minacce critiche basate sulla posta elettronica

Le funzionalità di analisi e risposta alle minacce forniscono informazioni dettagliate sulle minacce e sulle azioni di risposta correlate disponibili nel Centro sicurezza & conformità. Queste informazioni possono aiutare il team di sicurezza dell'organizzazione a proteggere gli utenti da attacchi basati su file o posta elettronica. Le funzionalità consentono di monitorare i segnali e raccogliere dati da più origini, ad esempio attività degli utenti, autenticazione, posta elettronica, PC compromessi ed eventi imprevisti di sicurezza. I decisori aziendali e il team delle operazioni di sicurezza possono utilizzare queste informazioni per comprendere e rispondere alle minacce contro l'organizzazione e proteggere la proprietà intellettuale.

## <a name="get-acquainted-with-threat-investigation-and-response-tools"></a>Acquisire familiarità con gli strumenti di analisi e risposta alle minacce

Le funzionalità di analisi e risposta alle minacce sono disponibili nel Centro sicurezza & conformità, sotto forma di un set di strumenti e flussi di lavoro di risposta, tra cui:

- [Dashboard delle minacce](#threat-dashboard)
- [Explorer](#threat-explorer)
- [Eventi imprevisti](#incidents)
- [Simulatore di attacchi](#attack-simulator)
- [Analisi e risposta automatizzate](automated-investigation-response-office.md)

### <a name="threat-dashboard"></a>Dashboard delle minacce

Usare il dashboard delle minacce (noto anche come [dashboard](security-dashboard.md)di sicurezza) per vedere rapidamente quali minacce sono state trattate e come modo visivo per segnalare ai decisori aziendali come i servizi di Microsoft 365 stanno proteggendo l'azienda.

![Dashboard delle minacce](../../media/ce013a31-3f80-4d09-bb95-bfb7623b8bc4.png)

Per visualizzare e usare questo dashboard, nel Centro sicurezza & conformità passare al dashboard **di gestione delle** \> **minacce.**

### <a name="threat-explorer"></a>Esplora minacce

Usare [Esplora minacce (e](threat-explorer.md) i rilevamenti in tempo reale) per analizzare le minacce, vedere il volume di attacchi nel tempo e analizzare i dati in base alle famiglie di minacce, all'infrastruttura degli utenti malintenzionati e altro ancora. Esplora minacce (noto anche come Esplora risorse) è il punto di partenza per il flusso di lavoro di indagine di qualsiasi analista della sicurezza.

![Esplora minacce](../../media/7a7cecee-17f0-4134-bcb8-7cee3f3c3890.png)

Per visualizzare e usare questo report, nel Centro sicurezza & conformità passare a **Esplora gestione** \> **minacce.**

### <a name="incidents"></a>Eventi imprevisti

Usa l'elenco Degli eventi imprevisti (denominato anche Indagini) per visualizzare un elenco degli eventi imprevisti di sicurezza in versione di fuga. Gli eventi imprevisti vengono utilizzati per tenere traccia di minacce come messaggi di posta elettronica sospetti e per eseguire ulteriori indagini e correzioni.

![Elenco degli eventi imprevisti di minacce correnti in Office 365](../../media/acadd4c7-d2de-4146-aeb8-90cfad805a9c.png)

Per visualizzare l'elenco degli eventi imprevisti correnti per l'organizzazione,  nel Centro sicurezza & conformità passare a Verifica eventi imprevisti per la gestione \>  \> **delle minacce.**

![Nel Centro sicurezza & conformità scegliere Verifica gestione \> minacce](../../media/e0f46454-fa38-40f0-a120-b595614d1d22.png)

### <a name="attack-simulator"></a>Simulatore di attacchi

Usa il simulatore di attacchi per configurare ed eseguire attacchi informatici realistici nell'organizzazione e identificare le persone vulnerabili prima che un attacco informatico reale influisca sulla tua azienda. Per altre informazioni, vedere [Simulatore di attacchi in Office 365.](attack-simulator.md)

### <a name="automated-investigation-and-response"></a>Analisi e risposta alle minacce automatizzate

Usa le funzionalità di analisi e risposta automatizzate (AIR) per risparmiare tempo e fatica correlati a contenuti, dispositivi e persone a rischio dalle minacce all'interno dell'organizzazione. I processi AIR possono iniziare ogni volta che vengono attivati determinati avvisi o quando vengono avviati dal team delle operazioni di sicurezza. Per altre informazioni, vedere [analisi e risposta automatizzate in Office 365.](automated-investigation-response-office.md)

## <a name="threat-intelligence-widgets"></a>Widget intelligence per le minacce

Nell'ambito dell'offerta Microsoft Defender per Office 365 Piano 2, gli analisti della sicurezza possono esaminare i dettagli su una minaccia nota. Ciò è utile per determinare se è possibile adottare misure/misure preventive aggiuntive per mantenere gli utenti al sicuro.

![Tendenze della sicurezza che mostrano informazioni sulle minacce recenti](../../media/11e7d40d-139b-4c56-8d52-c091c8654151.png)

## <a name="how-do-we-get-these-capabilities"></a>Come si ottengono queste funzionalità?

Le funzionalità di analisi e risposta alle minacce di Microsoft 365 sono incluse in Microsoft Defender per Office 365 Piano 2, incluso in Enterprise E5 o come componente aggiuntivo per determinati abbonamenti. Per altre informazioni, vedere [Defender per Office 365 Piano 1 e Piano 2.](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2)

## <a name="required-roles-and-permissions"></a>Ruoli e autorizzazioni necessari

Microsoft Defender per Office 365 usa il controllo dell'accesso basato sui ruoli. Le autorizzazioni vengono assegnate tramite determinati ruoli in Azure Active Directory, nell'interfaccia di amministrazione di Microsoft 365 o nel Centro sicurezza & conformità.

> [!TIP]
> Anche se alcuni ruoli, ad esempio Amministratore della sicurezza &, possono essere assegnati nel Centro sicurezza e conformità, è consigliabile usare l'interfaccia di amministrazione di Microsoft 365 o Azure Active Directory. Per informazioni sui ruoli, sui gruppi di ruoli e sulle autorizzazioni, vedere le risorse seguenti:
>
> - [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md)
>
> - [Autorizzazioni del ruolo di amministratore in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)

****

|Attività|Ruoli e autorizzazioni|
|---|---|
|Usare il dashboard delle minacce (o il nuovo [dashboard sicurezza)](security-dashboard.md) <p> Visualizzare informazioni sulle minacce recenti o correnti|Uno dei seguenti: <ul><li>**Amministratore globale**</li><li>**Amministratore della sicurezza**</li><li>**Lettore di sicurezza**</li></ul> <p> Questi ruoli possono essere assegnati in Azure Active Directory ( ) o nell'interfaccia di amministrazione di <https://portal.azure.com> Microsoft 365 ( <https://admin.microsoft.com> ).|
|Usare [Esplora minacce (e rilevamenti](threat-explorer.md) in tempo reale) per analizzare le minacce|Uno dei seguenti: <ul><li>**Amministratore globale**</li><li>**Amministratore della sicurezza**</li><li>**Lettore di sicurezza**</li></ul> <p> Questi ruoli possono essere assegnati in Azure Active Directory ( ) o nell'interfaccia di amministrazione di <https://portal.azure.com> Microsoft 365 ( <https://admin.microsoft.com> ).|
|Visualizzare gli eventi imprevisti (denominati anche indagini) <p> Aggiungere messaggi di posta elettronica a un evento imprevisto|Uno dei seguenti: <ul><li>**Amministratore globale**</li><li>**Amministratore della sicurezza**</li><li>**Lettore di sicurezza**</li></ul> <p> Questi ruoli possono essere assegnati in Azure Active Directory ( ) o nell'interfaccia di amministrazione di <https://portal.azure.com> Microsoft 365 ( <https://admin.microsoft.com> ).|
|Attivare azioni di posta elettronica in un evento imprevisto <p> Trovare ed eliminare messaggi di posta elettronica sospetti|Uno dei seguenti: <ul><li>**Amministratore globale**</li><li>**Amministratore della sicurezza** e ruolo **Ricerca ed eliminazione**</li></ul> <p> I **ruoli Amministratore** globale e **Amministratore** della sicurezza possono essere assegnati in Azure Active Directory ( ) o nell'interfaccia di amministrazione di <https://portal.azure.com> Microsoft 365 ( <https://admin.microsoft.com> ). <p> Il **ruolo Ricerca ed eliminazione** deve essere assegnato nel Centro sicurezza & conformità ( <https://protection.office.com> ).|
|Integrare Microsoft Defender per Office 365 Piano 2 con Microsoft Defender for Endpoint  <p> Integrare Microsoft Defender per Office 365 Piano 2 con un server SIEM|**L'amministratore globale o** il ruolo **amministratore** della sicurezza assegnato in Azure Active Directory ( ) o nell'interfaccia di amministrazione di <https://portal.azure.com> Microsoft 365 ( <https://admin.microsoft.com> ). <p> --- **plus** --- <p> Un ruolo appropriato assegnato in altre applicazioni (ad esempio [Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles) o il server SIEM).|
|

## <a name="next-steps"></a>Passaggi successivi

- [Informazioni sui tracker delle minacce - Novità e degna di nota](threat-trackers.md)

- [Trovare e analizzare i messaggi di posta elettronica dannosi recapitati (Office 365 Threat Investigation and Response)](investigate-malicious-email-that-was-delivered.md)

- [Integrare Office 365 Threat Investigation and Response con Microsoft Defender for Endpoint](integrate-office-365-ti-with-wdatp.md)

- [Informazioni sul simulatore di attacchi](attack-simulator.md)
