---
title: Office 365 Advanced Threat Protection
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 12/03/2019
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
ms.openlocfilehash: 65f123e77d5b38163dfe4e8971426d8a1135b571
ms.sourcegitcommit: ba223b4fd069fc6fd09c2a2e34c770a18bc7b2a2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2019
ms.locfileid: "39866708"
---
# <a name="office-365-advanced-threat-protection"></a>Office 365 Advanced Threat Protection

> [!IMPORTANT]
> Questo articolo è rivolto ai clienti aziendali di [Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description). Se si utilizza Outlook.com, Office 365 Home o Office 365 Personal e si cercano informazioni sui collegamenti sicuri di Outlook, vedere [Advanced Outlook.com security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2).

## <a name="overview"></a>Panoramica

Office 365 Advanced Threat Protection (ATP) protegge l'organizzazione dalle minacce dannose rappresentate da messaggi di posta elettronica, collegamenti (URL) e strumenti di collaborazione. ATP include:

- [Criteri di protezione dalle minacce](#configure-atp-policies): consente di definire i criteri di protezione dalle minacce per impostare il livello di protezione appropriato per l'organizzazione. 

- [Report](#view-office-365-atp-reports): consente di visualizzare report in tempo reale per monitorare le prestazioni ATP dell'organizzazione. 

- [Funzionalità di analisi e risposta alle minacce](#use-threat-investigation-and-response-capabilities): consente di usare strumenti all'avanguardia per analizzare, comprendere, simulare e prevenire minacce. 

- [Funzionalità di risposta automatica agli incidenti](#save-time-with-automated-incident-response): consente di risparmiare tempo e fatica nell'analisi e nell'attenuazione delle minacce.

## <a name="office-365-atp-plan-1-and-plan-2"></a>Office 365 ATP - Piano 1 e Piano 2

ATP è incluso in Office 365 E5. Tuttavia, Office 365 ATP - Piano 1 e Office 365 ATP - Piano 2 sono disponibili come componente aggiuntivo per alcuni abbonamenti. Per altre informazioni, vedere [Disponibilità delle funzionalità tra i piani di Advanced Threat Protection (ATP)](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).

> [!TIP]
> Se non si ha ancora Office 365 ATP, è possibile [avviare una versione di valutazione gratuita](https://go.microsoft.com/fwlink/p/?LinkID=698279).


## <a name="configure-atp-policies"></a>Configurare i criteri ATP

Con Office 365 ATP il team di sicurezza dell'organizzazione può configurare la protezione definendo criteri nel Centro sicurezza e conformità di Office 365. A questo scopo, passare a [https://protection.office.com](https://protection.office.com) > **Gestione delle minacce** > **Criteri**. 

> [!TIP]
> Per un rapido elenco dei criteri da definire, vedere [Protezione dalle minacce](protect-against-threats.md).

I criteri definiti per l'organizzazione determinano il comportamento e il livello di protezione per le minacce predefinite. Le opzioni criteri sono estremamente flessibili. Ad esempio, il team di sicurezza dell'organizzazione può impostare la protezione dalle minacce specifiche a livello di utente, organizzazione, destinatari e dominio. È importante rivedere regolarmente i criteri perché ogni giorno emergono nuove minacce e nuove sfide.  

- **[Allegati sicuri di ATP](atp-safe-attachments.md)**: fornisce protezione zero-day per salvaguardare il sistema di messaggistica, verificando l'eventuale presenza di contenuto dannoso negli allegati di posta elettronica. Consente di instradare in un ambiente speciale tutti i messaggi e gli allegati che non hanno un'impronta digitale del virus o del malware, quindi usa tecniche di apprendimento automatico e analisi per individuare intenti dannosi. Se non vengono rilevate attività sospette, il messaggio viene inoltrato alla cassetta postale. Per altre informazioni, vedere [Configurare i criteri Allegati sicuri in Office 365 ATP](set-up-atp-safe-attachments-policies.md).

- **[Collegamenti sicuri di ATP](atp-safe-links.md)**: consente di verificare gli URL quando gli utenti vi fanno clic, ad esempio nei messaggi di posta elettronica e nei file Office. La protezione è in corso e viene applicata a tutti i messaggi e all'ambiente di Office. I collegamenti vengono analizzati per ogni clic: i collegamenti sicuri rimangono accessibili e i collegamenti dannosi sono bloccati in modo dinamico. Per altre informazioni, vedere [Configurare i criteri Collegamenti sicuri in Office 365 ATP](https://docs.microsoft.com/office365/securitycompliance/set-up-atp-safe-links-policies). 

- **[ATP per SharePoint, OneDrive e Microsoft Teams](atp-for-spo-odb-and-teams.md)**: protegge l'organizzazione quando gli utenti collaborano e condividono file, identificando e bloccando i file dannosi nei siti del team e nelle raccolte documenti. Per altre informazioni, vedere [Office 365 ATP per SharePoint, OneDrive e Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md). 

- **[Protezione anti-phishing ATP](atp-anti-phishing.md)**: rileva i tentativi di imitare i propri utenti e i domini personalizzati. Applica i modelli di apprendimento automatico e gli algoritmi avanzati di rilevamento delle imitazioni per evitare attacchi di phishing. Per altre informazioni, vedere [Configurare i criteri anti-phishing e anti-phishing di Office 365 ATP](set-up-anti-phishing-policies.md).

## <a name="view-office-365-atp-reports"></a>Visualizzare i report di Office 365 ATP

Office 365 ATP include una [dashboard dei report](view-reports-for-atp.md) avanzata per monitorare le prestazioni di ATP. È possibile accedervi da **Report** > **Dashboard** nel Centro sicurezza e conformità. 

I report vengono aggiornati in tempo reale, fornendo le informazioni più recenti. Questi report forniscono anche suggerimenti e inviano avvisi in caso di minacce imminenti. I report predefiniti includono quanto segue: 

- [Esplora minacce (o rilevamenti in tempo reale)](threat-explorer.md)

- [Report dello stato di protezione dalle minacce](view-reports-for-atp.md#threat-protection-status-report)

- [Report dei tipi di file di ATP](view-reports-for-atp.md#atp-file-types-report)

- [Report della gestione dei messaggi di ATP](view-reports-for-atp.md#atp-message-disposition-report)

- ... e molti altri. 

## <a name="use-threat-investigation-and-response-capabilities"></a>Usare le funzionalità di analisi e risposta alle minacce

Office 365 ATP - Piano 2 include i migliori [strumenti per l'analisi e la risposta alle minacce](office-365-ti.md) che consentono al team di sicurezza dell'organizzazione di prevedere, comprendere e prevenire attacchi dannosi. 

- I **[tracker](threat-trackers.md)** delle minacce offrono le soluzioni di intelligence più recenti per risolvere gli attuali problemi di sicurezza informatica. Ad esempio, consentono di visualizzare informazioni sull'ultima versione del malware e adottare contromisure prima che diventi una minaccia effettiva per l'organizzazione. I tracker disponibili includono [Tracker degni di nota](threat-trackers.md#noteworthy-trackers), [Tracker di tendenza](threat-trackers.md#trending-trackers), [Query registrate](threat-trackers.md#tracked-queries) e [Query salvate](threat-trackers.md#saved-queries).

- **[Esplora minacce (o rilevamenti in tempo reale)](threat-explorer.md)** (anche noto come Explorer) è un report in tempo reale che consente di identificare e analizzare le minacce recenti. È possibile configurare Explorer per visualizzare dati per periodi personalizzati.

- Il **[simulatore di attacchi](attack-simulator.md)** consente di eseguire scenari di attacco realistici nell'organizzazione al fine di identificarne le vulnerabilità. Sono disponibili le simulazioni dei tipi di attacco correnti, tra cui [un attacco spear-phishing con nome visualizzato](attack-simulator.md#display-name-spear-phishing-attack), un [attacco password spraying](attack-simulator.md#password-spray-attack), un [attacco di forza bruta alle password](attack-simulator.md#brute-force-password-attack) e altro ancora.
    
## <a name="save-time-with-automated-incident-response"></a>Risparmiare tempo con la risposta automatica agli incidenti

(**NOVITÀ!**) Quando si analizza un potenziale cyberattacco, il tempo è un fattore essenziale. Prima vengono identificate e attenuate le minacce, meglio sarà per l'organizzazione. Le funzionalità di [risposta automatica agli incidenti](automated-investigation-response-office.md) includono un set di playbook di sicurezza che possono essere avviati automaticamente, ad esempio quando viene generato un avviso, o manualmente, ad esempio da una visualizzazione di Explorer. Grazie alla risposta automatica agli incidenti il team delle operazioni di sicurezza può risparmiare tempo e fatica perché tale funzionalità consente di attenuare le minacce in modo efficace ed efficiente. Per ulteriori informazioni, vedere [Adattatore Office 365](automated-investigation-response-office.md).

## <a name="permissions-required-to-use-atp-features"></a>Autorizzazioni necessarie per usare le funzionalità di ATP

Per accedere alle funzionalità di ATP nel Centro sicurezza e conformità, è necessario disporre di un ruolo appropriato. La tabella seguente include alcuni esempi:

|Ruolo o gruppo di ruoli  |Risorse per approfondire  |
|---------|---------|
|Amministratore globale di Office 365, che può essere assegnato a Azure Active Directory o al Centro sicurezza e conformità di Office 365 |[Informazioni sui ruoli di amministratore di Office 365](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)|
|Amministratore della sicurezza, che può essere assegnato a Azure Active Directory o al Centro sicurezza e conformità di Office 365 |[Autorizzazioni del ruolo di amministratore in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br><br/>[Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md)|
|Gestione dell'organizzazione di Exchange Online (assegnata a Exchange Online)|[Autorizzazioni in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)<br><br> [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)|
|Ricerca ed eliminazione (questa operazione è assegnata solo al Centro sicurezza e conformità di Office 365) |[Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md) |

Per altre informazioni, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).

## <a name="get-office-365-atp"></a>Ottenere Office 365 ATP

Office 365 ATP è incluso in alcuni abbonamenti, ad esempio Microsoft 365 E5, Office 365 E5, Office 365 A5 e Microsoft 365 Business. Se l'abbonamento non include Office 365 ATP, è possibile acquistare ATP - Piano 1 o ATP - Piano 2 come componente aggiuntivo per alcuni abbonamenti. Per altre informazioni, vedere le risorse seguenti:

- [Disponibilità di Office 365 Advanced Threat Protection (ATP)](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#office-365-advanced-threat-protection-atp-availability) per un elenco degli abbonamenti che includono i piani ATP.

- [Disponibilità delle funzionalità tra i piani di Advanced Threat Protection (ATP)](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans) per un elenco delle funzionalità incluse in Piano 1 e Piano 2.

- [Acquista il piano di Office 365 Advanced Threat Protection più adatto alle tue esigenze](https://products.office.com/exchange/advance-threat-protection#pmg-allup-content) per confrontare e acquistare i piani di Office 365 ATP.

- [Avviare una versione di versione di valutazione gratuita](https://go.microsoft.com/fwlink/p/?LinkID=698279)

## <a name="new-features-in-office-365-atp"></a>Nuove funzionalità in Office 365 ATP

Nuove caratteristiche vengono continuamente aggiunte a Office 365 ATP. Per altre informazioni, vedere le risorse seguenti:

- [Roadmap di Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection) offre un elenco delle nuove funzionalità in fase di sviluppo e implementazione.

- [Descrizione del servizio Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp) illustra le funzionalità e include informazioni sulla disponibilità dei piani ATP.
