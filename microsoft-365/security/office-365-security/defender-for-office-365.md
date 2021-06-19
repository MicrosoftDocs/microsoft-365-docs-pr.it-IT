---
title: Microsoft Defender per Office 365
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
localization_priority: Priority
search.appverid:
- MET150
- MOE150
ms.assetid: e100fe7c-f2a1-4b7d-9e08-622330b83653
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Microsoft Defender per Office 365 include allegati e collegamenti sicuri, strumenti avanzati anti-phishing, strumenti di report e funzionalità Threat Intelligence.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8bdb1e16c20b623934bb4fb994fcb8c6ef5f5ff0
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028469"
---
# <a name="microsoft-defender-for-office-365"></a>Microsoft Defender per Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> Questo articolo è rivolto ai clienti aziendali di [Microsoft Defender per Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description). Se si utilizza Outlook.com, Microsoft 365 Family o Microsoft 365 Personal e si cercano informazioni su Collegamenti sicuri o Allegati sicuri in Outlook, vedere [Sicurezza avanzata Outlook.com per gli abbonati a Microsoft 365](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Microsoft Defender per Office 365 protegge l'organizzazione da minacce dannose derivanti da messaggi di posta elettronica, collegamenti (URL) e strumenti di collaborazione. Defender per Office 365 include:

- **[Criteri di protezione dalle minacce](#configure-microsoft-defender-for-office-365-policies)**: consente di definire i criteri di protezione dalle minacce per impostare il livello di protezione appropriato per l'organizzazione.

- **[Report](#view-microsoft-defender-for-office-365-reports)**: consente di visualizzare report in tempo reale per monitorare le prestazioni di Defender per Office 365 dell'organizzazione.

- **[Funzionalità di analisi e risposta alle minacce](#use-threat-investigation-and-response-capabilities)**: consente di utilizzare strumenti all'avanguardia per analizzare, comprendere, simulare e prevenire minacce.

- **[Funzionalità di analisi e risposta automatizzate](office-365-air.md)**: consente di risparmiare tempo e fatica nell'analisi e nell'attenuazione delle minacce.

## <a name="interactive-guide-to-microsoft-defender-for-office-365"></a>Guida interattiva di Defender per Office 365
In questa guida interattiva imparerai a proteggere la tua organizzazione con Microsoft Defender per Office 365. Vedrai come Defender per Office 365 può aiutarti a definire criteri di protezione, analizzare le minacce per la tua organizzazione e rispondere agli attacchi.

[Consulta la guida interattiva](https://aka.ms/MSDO-IG)

## <a name="getting-started"></a>Introduzione

Se non si ha familiarità con Microsoft Defender per Office 365 o per *fare pratica*, potrebbe essere utile dividere la configurazione iniziale di Defender per Office 365 in blocchi, analizzarla e visualizzare i report usando questo articolo come riferimento. Di seguito sono riportati i primi blocchi di configurazione:

- Configurare tutto con "*anti*" nel nome.
  - anti-malware
  - anti-phishing
  - anti-spam
- Configurare tutto con "*sicuri*" nel nome.
  - Collegamenti sicuri
  - Allegati sicuri
- Difendere i carichi di lavoro (ad esempio SharePoint Online, OneDrive e Teams)
- Proteggere con Zero-Hour Auto Purge

Per altre informazioni, [fare clic su questo collegamento](protect-against-threats.md).

> [!NOTE]
> Microsoft Defender per Office 365 è disponibile in due diversi tipi di piani. È possibile stabilire se si dispone di **Piano 1** se sono presenti "protezione in tempo reale" e **Piano 2**, se si dispone di Cronologia minacce. Il piano di cui si dispone influisce sugli strumenti visualizzati, quindi assicurarsi di conoscere il piano durante l’apprendimento.

## <a name="microsoft-defender-for-office-365-plan-1-and-plan-2"></a>Microsoft Defender per Office 365 Piano 1 e Piano 2

La tabella seguente riepiloga cosa è incluso in ogni piano.

****

|Microsoft Defender per Office 365 Piano 1|Microsoft Defender per Office 365 Piano 2|
|---|---|
|Funzionalità di configurazione, protezione e rilevamento: <ul><li>[Allegati sicuri](safe-attachments.md)</li><li>[Collegamenti sicuri](safe-links.md)</li><li>[Allegati sicuri per SharePoint, OneDrive e Microsoft Teams](mdo-for-spo-odb-and-teams.md)</li><li>[Anti-phishing in Defender per la protezione di Office 365](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</li><li>[Rilevamenti in tempo reale](threat-explorer.md)</li></ul>|Funzionalità di Microsoft Defender per Office 365 Piano 1 <br>--- più ---<br> Funzionalità di automazione, analisi, correzione e formazione:<ul><li>[Tracker delle minacce](threat-trackers.md)</li><li>[Esplora minacce](threat-explorer.md)</li><li>[Analisi e risposta automatizzate](office-365-air.md)</li><li>[Simulatore di attacchi](attack-simulator.md)</li><li>[Visualizzazioni campagna](campaigns.md)</li></ul>|
|

- Microsoft Defender per Office 365 Piano 2 è incluso in Office 365 E5, Office 365 A5, Microsoft 365 E5 Security e Microsoft 365 E5.

- Microsoft Defender per Office 365 Piano 1 è incluso in Microsoft 365 Business Premium.

- Microsoft Defender per Office 365 Piano 1 e Microsoft Defender per Office 365 Piano 2 sono disponibili come componenti aggiuntivi per determinati abbonamenti. Per altre informazioni, vedere [Disponibilità delle funzionalità nei piani di Microsoft Defender per Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).

- La caratteristica [Documenti sicuri](safe-docs.md) è disponibile solo per gli utenti che dispongono di licenze Microsoft 365 E5 o Microsoft 365 E5 Security (non incluse nei piani di Microsoft Defender per Office 365).

- Se l'abbonamento attuale non include Microsoft Defender per Office 365, [contattare il reparto vendite per iniziare con una versione di valutazione](https://info.microsoft.com/ww-landing-M365SMB-web-contact.html) e vedere cosa Microsoft Defender per Office 365 può fare per l'organizzazione.

## <a name="configure-microsoft-defender-for-office-365-policies"></a>Configurazione criteri di Microsoft Defender per Office 365

Con Microsoft Defender per Office 365, il team di sicurezza dell'organizzazione può configurare la protezione definendo i criteri in Microsoft 365 Defender (passare a <https://security.microsoft.com> \> **Posta elettronica e collaborazione** \> **Criteri e regole**.)

Scopri di più guardando [questo video](https://www.youtube.com/watch?v=vivvTmWJ_3c). 

> [!TIP]
> Per un rapido elenco dei criteri da definire, vedere [Protezione dalle minacce](protect-against-threats.md).

## <a name="defender-for-office-365-policies"></a>Criteri Defender per Office 365

I criteri definiti per l'organizzazione determinano il comportamento e il livello di protezione per le minacce predefinite. Le opzioni criteri sono estremamente flessibili. Ad esempio, il team di sicurezza dell'organizzazione può impostare la protezione dalle minacce specifiche a livello di utente, organizzazione, destinatari e dominio. È importante rivedere regolarmente i criteri perché ogni giorno emergono nuove minacce e nuove sfide.

- **[Allegati sicuri](safe-attachments.md)**: fornisce protezione zero-day per salvaguardare il sistema di messaggistica, verificando l'eventuale presenza di contenuto dannoso negli allegati di posta elettronica. Consente di instradare in un ambiente speciale tutti i messaggi e gli allegati che non hanno un'impronta digitale del virus o del malware, quindi usa tecniche di apprendimento automatico e analisi per individuare intenti dannosi. Se non vengono rilevate attività sospette, il messaggio viene inoltrato alla cassetta postale. Per altre informazioni, vedere [Configurare i criteri Allegati sicuri](set-up-safe-attachments-policies.md).

- **[Collegamenti sicuri](safe-links.md)**: consente di verificare gli URL quando gli utenti vi fanno clic, ad esempio nei messaggi di posta elettronica e nei file Office. La protezione è in corso e viene applicata a tutti i messaggi e all'ambiente di Office. I collegamenti vengono analizzati per ogni clic: i collegamenti sicuri rimangono accessibili e i collegamenti dannosi sono bloccati in modo dinamico. Per altre informazioni, vedere [Configurare i criteri Collegamenti sicuri](set-up-safe-links-policies.md).

- **[Allegati sicuri per SharePoint, OneDrive e Microsoft Teams](mdo-for-spo-odb-and-teams.md)**: protegge l'organizzazione quando gli utenti collaborano e condividono file, identificando e bloccando i file dannosi nei siti del team e nelle raccolte documenti. Per altre informazioni, vedere [Attivare Microsoft Defender per Office 365 per SharePoint, OneDrive e Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md).

- **[Protezione anti-phishing in Microsoft Defender per Office 365](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)**: rileva i tentativi di imitare i propri utenti e i domini interni o personalizzati. Applica i modelli di apprendimento automatico e gli algoritmi avanzati di rilevamento delle imitazioni per evitare attacchi di phishing. Per altre informazioni, vedere [Configurare i criteri anti-phishing in Microsoft Defender per Office 365](configure-atp-anti-phishing-policies.md).

## <a name="view-microsoft-defender-for-office-365-reports"></a>Visualizzazione report di Microsoft Defender per Office 365

Microsoft Defender per Office 365 include un [dashboard avanzato per la creazione di report](view-reports-for-mdo.md) per monitorare le prestazioni di Microsoft Defender per Office 365. È possibile accedervi da **Report** \> **Dashboard** nel portale di Microsoft 365 Defender.

I report vengono aggiornati in tempo reale, fornendo le informazioni più recenti. Questi report forniscono anche suggerimenti e inviano avvisi in caso di minacce imminenti. I report predefiniti includono quanto segue:

- [Esplora minacce (o rilevamenti in tempo reale)](threat-explorer.md)
- [Report dello stato di protezione dalle minacce](view-reports-for-mdo.md#threat-protection-status-report)
- ... e molti altri.

## <a name="use-threat-investigation-and-response-capabilities"></a>Usare le funzionalità di analisi e risposta alle minacce

Microsoft Defender per Office 365 Piano 2 include i migliori [strumenti per l'analisi e la risposta alle minacce](office-365-ti.md) che consentono al team di sicurezza dell'organizzazione di prevedere, comprendere e prevenire attacchi dannosi.

- I **[tracker](threat-trackers.md)** delle minacce offrono le soluzioni di intelligence più recenti per risolvere gli attuali problemi di sicurezza informatica. Ad esempio, consentono di visualizzare informazioni sull'ultima versione del malware e adottare contromisure prima che diventi una minaccia effettiva per l'organizzazione. I tracker disponibili includono [Tracker degni di nota](threat-trackers.md#noteworthy-trackers), [Tracker di tendenza](threat-trackers.md#trending-trackers), [Query registrate](threat-trackers.md#tracked-queries) e [Query salvate](threat-trackers.md#saved-queries).

- **[Esplora minacce (o rilevamenti in tempo reale)](threat-explorer.md)** (anche noto come Explorer) è un report in tempo reale che consente di identificare e analizzare le minacce recenti. È possibile configurare Explorer per visualizzare dati per periodi personalizzati.

- Il **[simulatore di attacchi](attack-simulator.md)** consente di eseguire scenari di attacco realistici nell'organizzazione al fine di identificarne le vulnerabilità. Sono disponibili le simulazioni dei tipi di attacco correnti, tra cui un attacco spear-phishing con furto delle credenziali e tramite allegato, un attacco password spraying, un attacco di forza bruta alle password.

## <a name="save-time-with-automated-investigation-and-response"></a>Risparmiare tempo con Automated Investigation and Response

(**NOVITÀ!**) Quando si analizza un potenziale cyberattacco, il tempo è un fattore essenziale. Prima vengono identificate e attenuate le minacce, meglio sarà per l'organizzazione. Le funzionalità di [analisi e risposta automatizzate](office-365-air.md) includono un set di playbook di sicurezza che possono essere avviati automaticamente, ad esempio quando viene generato un avviso, o manualmente, ad esempio da una visualizzazione di Explorer. Grazie alla risposta automatica agli incidenti il team delle operazioni di sicurezza può risparmiare tempo e fatica perché tale funzionalità consente di attenuare le minacce in modo efficace ed efficiente. Per ulteriori informazioni, vedere [Adattatore Office 365](office-365-air.md).

## <a name="permissions-required-to-use-microsoft-defender-for-office-365-features"></a>Autorizzazioni necessarie per usare le funzionalità di Microsoft Defender per Office 365

Per accedere alle funzionalità di Microsoft Defender per Office 365 in Microsoft 365 Defender, è necessario disporre di un ruolo appropriato. La tabella seguente include alcuni esempi:

|Ruolo o gruppo di ruoli|Risorse per approfondire|
|---|---|
|Amministratore globale, che può essere assegnato in Azure Active Directory o in Microsoft 365 Defender|[Informazioni sui ruoli di amministratore di Microsoft 365](../../admin/add-users/about-admin-roles.md)|
|Amministratore della sicurezza, che può essere assegnato in Azure Active Directory o in Microsoft 365 Defender|[Autorizzazioni del ruolo di amministratore in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) <p> [Autorizzazioni in Microsoft 365 Defender](permissions-in-the-security-and-compliance-center.md)|
|Gestione dell'organizzazione di Exchange Online (assegnata a Exchange Online)|[Autorizzazioni in Exchange Online](/exchange/permissions-exo/permissions-exo) <p> [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell)|
|Ricerca ed eliminazione, assegnato solo in Microsoft 365 Defender|[Autorizzazioni in Microsoft 365 Defender](permissions-in-the-security-and-compliance-center.md)|

Per altre informazioni, vedere [Autorizzazioni in Microsoft 365 Defender](permissions-in-the-security-and-compliance-center.md).

## <a name="get-microsoft-defender-for-office-365"></a>Ottenere Microsoft Defender per Office 365

Microsoft Defender per Office 365 è incluso in alcuni abbonamenti, ad esempio Microsoft 365 E5, Office 365 E5, Office 365 A5 e Microsoft 365 Business Premium. Se l'abbonamento non include Defender per Office 365, è possibile acquistare Defender per Office 365 Piano 1 o Defender per Office 365 Piano 2 come componente aggiuntivo per determinati abbonamenti. Per altre informazioni, vedere le risorse seguenti:

- [Disponibilità di Microsoft Defender per Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#office-365-advanced-threat-protection-atp-availability) per un elenco di abbonamenti che includono i piani per Defender per Office 365.

- [Disponibilità delle funzionalità tra i piani di Microsoft Defender per Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans) per un elenco delle funzionalità incluse in Piano 1 e Piano 2.

- [Ottenere il giusto Microsoft Defender per Office 365](https://products.office.com/exchange/advance-threat-protection#pmg-allup-content) per confrontare i piani e acquistare Defender per Office 365.

- [Avviare una versione di versione di valutazione gratuita](https://go.microsoft.com/fwlink/p/?LinkID=698279)

## <a name="new-features-in-microsoft-defender-for-office-365"></a>Nuove funzionalità di Microsoft Defender per Office 365

Nuove funzionalità vengono aggiunte continuamente a Microsoft Defender per Office 365. Per altre informazioni, vedere le risorse seguenti:

- [Roadmap di Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=Microsoft%2CDefender%2Cfor%2COffice%2C365) offre un elenco delle nuove funzionalità in fase di sviluppo e implementazione.

- [Descrizione del servizio Microsoft Defender per Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp) descrive le funzionalità e la disponibilità nei piani di Defender per Office 365.

## <a name="see-also"></a>Vedere anche

- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

- [Analisi e risposta automatizzate in Microsoft 365 Defender](../defender/m365d-autoir.md)

