---
title: Office 365 Advanced Threat Protection
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 10/03/2019
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
- MOE150
ms.assetid: e100fe7c-f2a1-4b7d-9e08-622330b83653
ms.collection:
- M365-security-compliance
description: Office 365 Advanced Threat Protection include allegati e collegamenti sicuri, strumenti avanzati anti-phishing, strumenti di report e funzionalità Threat Intelligence.
ms.openlocfilehash: dbfff642563117a479db1ac36e76700cca71dd75
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2019
ms.locfileid: "38032201"
---
# <a name="office-365-advanced-threat-protection"></a>Office 365 Advanced Threat Protection

> [!IMPORTANT]
> Questo articolo è rivolto ai clienti aziendali di [Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description). Se si utilizza Outlook.com, Office 365 Home o Office 365 Personal e si cercano informazioni sui collegamenti sicuri di Outlook, vedere [Advanced Outlook.com security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2).

## <a name="overview"></a>Panoramica

Office 365 Advanced Threat Protection (ATP) protegge l'organizzazione dalle minacce dannose rappresentate da messaggi di posta elettronica, collegamenti (URL) e strumenti di collaborazione. ATP include:

- [Criteri di protezione dalle minacce](#configure-atp-policies): consente di definire i criteri di protezione dalle minacce per impostare il livello di protezione appropriato per l'organizzazione. 

- [Report](#view-atp-reports): consente di visualizzare report in tempo reale per monitorare le prestazioni ATP dell'organizzazione. 

- [Funzionalità di analisi e risposta alle minacce](#use-threat-investigation-and-response-capabilities): consente di usare strumenti all'avanguardia per analizzare, comprendere, simulare e prevenire minacce. 

- [Funzionalità di analisi e risposta automatizzate](#save-time-with-automated-investigation-and-response): consente di risparmiare tempo e fatica nell'analisi e nell'attenuazione delle minacce.

## <a name="office-365-atp-plan-1-and-plan-2"></a>Office 365 ATP - Piano 1 e Piano 2

ATP è incluso in Office 365 E5. Tuttavia, ATP - Piano 1 e ATP - Piano 2 sono disponibili come componente aggiuntivo per alcuni abbonamenti. Per altre informazioni, vedere [Disponibilità delle funzionalità tra i piani di Advanced Threat Protection (ATP)](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).

## <a name="configure-atp-policies"></a>Configurare i criteri ATP

Office 365 ATP offre numerosi strumenti per impostare un livello di protezione appropriato per la propria organizzazione. 

Il team di sicurezza dell'organizzazione deve definire i criteri per ogni strumento ATP nel Centro sicurezza e conformità di Office 365. Per accedere alle opzioni criteri, vedere **Criteri di gestione** > **delle minacce**. Per altre informazioni, vedere [Protezione dalle minacce](protect-against-threats.md).

I criteri definiti per l'organizzazione determinano il comportamento e il livello di protezione per le minacce predefinite. Le opzioni criteri sono estremamente flessibili. Ad esempio, il team di sicurezza dell'organizzazione può impostare la protezione dalle minacce specifiche a livello di utente, organizzazione, destinatari e dominio. È importante rivedere regolarmente i criteri perché ogni giorno emergono nuove minacce e nuove sfide.  

- [Allegati sicuri di ATP](atp-safe-attachments.md): fornisce protezione zero-day per salvaguardare il sistema di messaggistica, verificando l'eventuale presenza di contenuto dannoso negli allegati di posta elettronica. Consente di instradare in un ambiente speciale tutti i messaggi e gli allegati che non hanno un'impronta digitale del virus o del malware, quindi usa tecniche di apprendimento automatico e analisi per individuare intenti dannosi. Se non vengono rilevate attività sospette, il messaggio viene inoltrato alla cassetta postale. Per altre informazioni, vedere [Configurare i criteri Allegati sicuri in Office 365 ATP](set-up-atp-safe-attachments-policies.md).

- [Collegamenti sicuri di ATP](atp-safe-links.md): consente di verificare gli URL quando gli utenti vi fanno clic, ad esempio nei messaggi di posta elettronica e nei file Office. La protezione è in corso e viene applicata a tutti i messaggi e all'ambiente di Office. I collegamenti vengono analizzati per ogni clic: i collegamenti sicuri rimangono accessibili e i collegamenti dannosi sono bloccati in modo dinamico. Per altre informazioni, vedere [Configurare i criteri Collegamenti sicuri in Office 365 ATP](https://docs.microsoft.com/office365/securitycompliance/set-up-atp-safe-links-policies). 

- [ATP per SharePoint, OneDrive e Microsoft Teams](atp-for-spo-odb-and-teams.md): protegge l'organizzazione quando gli utenti collaborano e condividono file, identificando e bloccando i file dannosi nei siti del team e nelle raccolte documenti. Per altre informazioni, vedere [Office 365 ATP per SharePoint, OneDrive e Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md). 

- [Protezione anti-phishing ATP](atp-anti-phishing.md): rileva i tentativi di imitare i propri utenti e i domini personalizzati. Applica i modelli di apprendimento automatico e gli algoritmi avanzati di rilevamento delle imitazioni per evitare attacchi di phishing. Per altre informazioni, vedere [Configurare i criteri anti-phishing e anti-phishing di Office 365 ATP](set-up-anti-phishing-policies.md).

## <a name="view-atp-reports"></a>Visualizzare i report di ATP

Office 365 ATP include una [dashboard dei report](view-reports-for-atp.md) avanzata per monitorare le prestazioni ATP. È possibile accedervi da **Report > Dashboard** nel Centro sicurezza e conformità. 

I report vengono aggiornati in tempo reale, fornendo le informazioni più recenti. Questi report forniscono anche suggerimenti e inviano avvisi in caso di minacce imminenti. I report predefiniti includono quanto segue: 

- [Esplora minacce (o rilevamenti in tempo reale)](threat-explorer.md)

- [Report dello stato di protezione dalle minacce](view-reports-for-atp.md#threat-protection-status-report)

- [Report dei tipi di file di ATP](view-reports-for-atp.md#atp-file-types-report)

- [Report della gestione dei messaggi di ATP](view-reports-for-atp.md#atp-message-disposition-report)

- ... e altro ancora. 

## <a name="use-threat-investigation-and-response-capabilities"></a>Usare le funzionalità di analisi e risposta alle minacce

Office 365 ATP - Piano 2 include i migliori [strumenti per l'analisi e la risposta alle minacce](office-365-ti.md) che consentono al team di sicurezza dell'organizzazione di prevedere, comprendere e prevenire attacchi dannosi. 

- I [tracker delle minacce](threat-trackers.md) offrono le soluzioni di intelligence più recenti per risolvere gli attuali problemi di sicurezza informatica. Ad esempio, consentono di visualizzare informazioni sull'ultima versione del malware e adottare contromisure prima che diventi una minaccia effettiva per l'organizzazione. I tracker disponibili includono [Tracker degni di nota](threat-trackers.md#noteworthy-trackers), [Tracker di tendenza](threat-trackers.md#trending-trackers), [Query registrate](threat-trackers.md#tracked-queries) e [Query salvate](threat-trackers.md#saved-queries).

- [Esplora minacce (o rilevamenti in tempo reale)](threat-explorer.md) (anche noto come Explorer) è un report in tempo reale che consente di identificare e analizzare le minacce recenti. È possibile configurare Explorer per visualizzare dati per periodi personalizzati.

- Il [simulatore di attacchi](attack-simulator.md) consente di eseguire scenari di attacco realistici nell'organizzazione al fine di identificarne le vulnerabilità. Sono disponibili le simulazioni dei tipi di attacco correnti, tra cui [un attacco spear-phishing con nome visualizzato](attack-simulator.md#display-name-spear-phishing-attack), un [attacco password spraying](attack-simulator.md#password-spray-attack), un [attacco di forza bruta alle password](attack-simulator.md#brute-force-password-attack) e altro ancora.
    
## <a name="save-time-with-automated-investigation-and-response"></a>Risparmiare tempo con Automated Investigation and Response

(**NOVITÀ!**) Quando si analizza un potenziale cyberattacco, il tempo è un fattore essenziale. Prima vengono identificate e attenuate le minacce, meglio sarà per l'organizzazione. Gli abbonamenti elencati di seguito includono ora le funzionalità di [Automated Investigation and Response (AIR)](automated-investigation-response-office.md). Se non si dispone di queste funzionalità, verranno presto installate se si ha uno di questi abbonamenti.

Office 365 AIR è incluso negli abbonamenti seguenti:

- Microsoft 365 E5
- Microsoft 365 E5 Security
- Office 365 E5
- Office 365 Advanced Threat Protection (Piano 2)

AIR include un set di playbook di sicurezza che possono essere avviati automaticamente, ad esempio quando viene generato un avviso, o manualmente, ad esempio da una visualizzazione di Explorer. Il team delle operazioni di sicurezza può risparmiare tempo e fatica grazie ad AIR, che consente di attenuare le minacce, in modo efficace ed efficiente. Per altre informazioni, vedere [Automated Investigation and Response (AIR) con Office 365](automated-investigation-response-office.md).

## <a name="permissions-required-to-use-atp-features"></a>Autorizzazioni necessarie per usare le funzionalità di ATP

Per accedere alle funzionalità di ATP nel Centro sicurezza e conformità, è necessario disporre di un ruolo appropriato. La tabella seguente include alcuni esempi:

|Ruolo o gruppo di ruoli  |Risorse per approfondire  |
|---------|---------|
|Amministratore globale di Office 365 |[Informazioni sui ruoli di amministratore di Office 365](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)|
|Amministratore della sicurezza |[Autorizzazioni del ruolo di amministratore in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Gestione organizzazione di Exchange Online |[Autorizzazioni in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) <br>e<br> [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)|

Per ulteriori informazioni, vedere:

- [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md) 

- [Fornire agli utenti l'accesso al Centro sicurezza e conformità](grant-access-to-the-security-and-compliance-center.md)

## <a name="get-office-365-atp"></a>Ottieni Office 365 ATP

Office 365 ATP - Piano 2 è incluso in Office 365 Enterprise E5, Office 365 Education A5 e Microsoft 365 Business. Se l'abbonamento non include Office 365 ATP, è possibile acquistare ATP - Piano 1 o ATP - Piano 2 come componente aggiuntivo per alcuni abbonamenti. Per altre informazioni, vedere le risorse seguenti:

- Per un elenco degli abbonamenti che includono i piani ATP, vedere [Disponibilità di Office 365 Advanced Threat Protection (ATP)](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#office-365-advanced-threat-protection-atp-availability).

- Per un elenco delle funzionalità incluse in Piano 1 e Piano 2, vedere [Disponibilità delle funzionalità tra i piani di Advanced Threat Protection (ATP)](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).

- Per confrontare e acquistare i piani di Office 365 ATP, vedere [Ottieni il piano Office 365 Advanced Threat Protection giusto](https://products.office.com/exchange/advance-threat-protection#pmg-allup-content).

## <a name="new-features-in-office-365-atp"></a>Nuove funzionalità in Office 365 ATP

Nuove caratteristiche vengono continuamente aggiunte a Office 365 ATP. Per altre informazioni, vedere le risorse seguenti:

- La [Roadmap di Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection) offre un elenco delle nuove funzionalità in fase di sviluppo e implementazione.

- [Descrizione del servizio Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp) descrive le funzionalità e la disponibilità dei piani ATP.
