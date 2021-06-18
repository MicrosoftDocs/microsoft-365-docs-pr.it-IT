---
title: Piano per la gestione dei rischi Insider
description: Informazioni su come pianificare l'utilizzo dei criteri di gestione dei rischi insider nell'organizzazione.
keywords: Microsoft 365, rischio insider, gestione dei rischi, conformità
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: 6884ec3b2bc7c24e4f7f6e62d9b24add3aeee2c0
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007346"
---
# <a name="plan-for-insider-risk-management"></a>Piano per la gestione dei rischi Insider

Prima di iniziare [a](insider-risk-management.md) usare la gestione dei rischi insider nell'organizzazione, esistono importanti attività e considerazioni di pianificazione che devono essere esaminate dai team di information technology e di gestione della conformità. La comprensione approfondita e la pianificazione della distribuzione nelle aree seguenti consentono di garantire che l'implementazione e l'utilizzo delle funzionalità di gestione dei rischi insider siano uniformi e siano allineati alle procedure consigliate per la soluzione.

## <a name="work-with-stakeholders-in-your-organization"></a>Collaborare con le parti interessate nell'organizzazione

Identificare i cointeressati appropriati dell'organizzazione per collaborare per l'azione sugli avvisi e i casi di gestione dei rischi insider. Alcuni stakeholder consigliati da prendere in considerazione, inclusi nella pianificazione iniziale e nel flusso di lavoro end-to-end per la gestione dei rischi [insider,](insider-risk-management.md#workflow) sono persone delle aree seguenti dell'organizzazione:

- Information technology
- Conformità
- Privacy
- Sicurezza
- Risorse umane
- Esigenze legali

## <a name="determine-any-regional-compliance-requirements"></a>Determinare eventuali requisiti di conformità regionali

Aree geografiche e organizzative diverse possono avere requisiti di conformità e privacy diversi da altre aree dell'organizzazione. Collaborare con gli stakeholder in queste aree per assicurarsi che comprenda i controlli di conformità e privacy nella gestione dei rischi insider e come devono essere utilizzati in diverse aree dell'organizzazione. In alcuni scenari, i requisiti di conformità e privacy potrebbero richiedere criteri che designno o limitano alcune parti interessate da indagini e casi in base al caso di un utente o ai requisiti normativi o di criteri per l'area.

Se si dispone di requisiti per specifici stakeholder da coinvolgere in indagini dei casi che coinvolgono utenti in determinate aree geografiche, ruoli o divisioni, è possibile implementare criteri di gestione dei rischi insider separati (anche se [identici)](insider-risk-management-policies.md) per le diverse aree geografiche e popolazioni. Questa configurazione agevola la ricerca e la gestione dei casi rilevanti per i ruoli e le aree geografiche dei cointeressati. Inoltre, è consigliabile creare processi e criteri per le aree geografiche in cui investigatori e revisori parlano la stessa lingua degli utenti per semplificare il processo di escalation per gli avvisi e i casi di gestione dei rischi insider.

## <a name="plan-for-the-review-and-investigation-workflow"></a>Pianificare il flusso di lavoro di revisione e analisi

Selezionare stakeholder dedicati per monitorare ed esaminare gli avvisi e i casi a cadenza regolare nel Centro conformità [Microsoft 365.](https://compliance.microsoft.com/) Assicurarsi di comprendere come assegnare le diverse parti interessate ai diversi gruppi di ruoli disponibili nella gestione dei rischi insider.

A seconda della struttura del team di gestione della conformità, è possibile assegnare utenti a specifici gruppi di ruolo per gestire diversi insiemi di funzionalità della gestione dei rischi Insider. Per visualizzare  la scheda Autorizzazioni nel Centro sicurezza & e conformità di Office 365  e gestire i gruppi di ruoli, è necessario essere assegnati al gruppo di ruoli Gestione organizzazione o assegnare il ruolo Gestione *ruoli.* Scegliere tra queste opzioni del gruppo di ruoli durante la configurazione della gestione dei rischi insider:

| **Gruppo di ruolo** | **Autorizzazioni del ruolo** |
| :------------- | :------------------- |
| **Insider Risk Management** | Usare questo gruppo di ruoli per la gestione dei rischi Insider per la propria organizzazione in un unico gruppo. Aggiungendo tutti gli account utente per amministratori, analisti, investigatori e revisori designati, è possibile configurare le autorizzazioni di gestione dei rischi insider in un singolo gruppo. Questo gruppo di ruoli contiene tutti i ruoli di autorizzazione per la gestione dei rischi insider e le autorizzazioni associate. Questa configurazione è il modo più semplice per iniziare rapidamente a usare la gestione dei rischi insider ed è adatta per le organizzazioni che non necessitano di autorizzazioni separate definite per gruppi distinti di utenti. Quando si utilizza questa configurazione, è necessario assicurarsi di avere sempre almeno un utente assegnato a questo gruppo di ruoli per assicurarsi che i criteri funzionino come previsto e in modo che l'utente possa creare e modificare i criteri, configurare le impostazioni della soluzione ed esaminare gli avvisi di integrità dei criteri. |
| **Insider Risk Management Admin** | Utilizzare questo gruppo di ruoli per configurare inizialmente la gestione dei rischi insider e successivamente per separare gli amministratori dei rischi insider in un gruppo definito. Gli utenti di questo gruppo di ruoli possono abilitare e visualizzare informazioni analitiche e creare, leggere, aggiornare ed eliminare criteri di gestione dei rischi insider, impostazioni globali e assegnazioni di gruppi di ruoli. Quando si utilizza questa configurazione, è necessario assicurarsi di avere sempre almeno un utente assegnato a questo gruppo di ruoli per assicurarsi che i criteri funzionino come previsto e in modo che l'utente possa creare e modificare i criteri, configurare le impostazioni della soluzione ed esaminare gli avvisi di integrità dei criteri. |
| **Analisti gestione dei rischi Insider** | Usare questo gruppo per assegnare le autorizzazioni agli utenti che fungeranno da analisti di casi di rischio Insider. Gli utenti di questo gruppo di ruoli possono accedere e visualizzare tutti gli avvisi, i casi, le informazioni analitiche e i modelli di avvisi per la gestione dei rischi insider. Non possono accedere a Esplora contenuto a rischio insider. |
| **Investigatori gestione dei rischi Insider** | Usare questo gruppo per assegnare le autorizzazioni agli utenti che fungeranno da investigatori dei dati relativi al rischio Insider. Gli utenti di questo gruppo di ruoli possono accedere a tutti gli avvisi di gestione dei rischi insider, i casi, i modelli di avviso e Esplora contenuto per tutti i casi. |
| **Revisori della gestione dei rischi insider** | Utilizzare questo gruppo per assegnare autorizzazioni agli utenti che controllano le attività di gestione dei rischi insider. Gli utenti di questo gruppo di ruoli possono accedere al log di controllo dei rischi insider. |

## <a name="understand-requirements-and-dependencies"></a>Informazioni su requisiti e dipendenze

A seconda di come si prevede di implementare i criteri di gestione dei rischi insider, è necessario disporre delle sottoscrizioni di licenza di Microsoft 365 appropriate e comprendere e pianificare alcuni prerequisiti della soluzione.

**Licenze:** La gestione dei rischi insider è disponibile nell'ambito di un'ampia selezione di abbonamenti alle licenze di Microsoft 365. Per informazioni dettagliate, vedere [l'articolo Introduzione alla gestione dei rischi insider.](insider-risk-management-configure.md#subscriptions-and-licensing)

Se non si dispone di un piano Microsoft 365 Enterprise E5 esistente e si desidera provare la gestione dei rischi insider, è possibile aggiungere [Microsoft 365](/office365/admin/try-or-buy-microsoft-365) all'abbonamento esistente o iscriversi [a](https://www.microsoft.com/microsoft-365/enterprise) una versione di valutazione di Microsoft 365 Enterprise E5.

**Requisiti dei modelli di criteri:** A seconda del modello di criteri scelto, è necessario comprendere e pianificare i requisiti prima di configurare la gestione dei rischi insider nell'organizzazione:

- Quando si  utilizza il modello Furto di dati per utenti in uscita, è necessario configurare un connettore risorse umane di Microsoft 365 per importare periodicamente le informazioni sulla data di chiusura e di chiusura per gli utenti dell'organizzazione. Vedere l'articolo [Importare dati con il connettore HR](import-hr-data.md) per istruzioni dettagliate su come configurare il connettore HR di Microsoft 365 per l'organizzazione.
- Quando **si** utilizzano modelli di perdita di dati, è necessario configurare almeno un criterio di prevenzione della perdita dei dati (DLP) per definire le informazioni riservate nell'organizzazione e per ricevere avvisi di rischio insider per gli avvisi dei criteri DLP di gravità elevata. Vedere l'articolo [Creare, testare e ottimizzare un criterio DLP](create-test-tune-dlp-policy.md) per istruzioni dettagliate su come configurare i criteri DLP per l'organizzazione.
- Quando si usano **modelli di violazione dei** criteri di sicurezza, è necessario abilitare Microsoft Defender for Endpoint per l'integrazione della gestione dei rischi insider nel Defender Security Center per importare gli avvisi di violazione di sicurezza. Vedi [l'articolo Configurare le funzionalità avanzate in Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/advanced-features) per istruzioni dettagliate per abilitare l'integrazione di Defender for Endpoint con la gestione dei rischi insider.
- Quando si **utilizzano modelli utente scontenti,** è necessario configurare un connettore risorse umane di Microsoft 365 per importare periodicamente le informazioni sullo stato delle prestazioni o dell'abbassamento di livello per gli utenti dell'organizzazione. Vedere l'articolo [Importare dati con il connettore HR](import-hr-data.md) per istruzioni dettagliate su come configurare il connettore HR di Microsoft 365 per l'organizzazione.

## <a name="test-with-a-small-group-of-users-in-a-production-environment"></a>Testare con un piccolo gruppo di utenti in un ambiente di produzione

Prima di abilitare la soluzione in modo generale nell'ambiente di produzione, è consigliabile testare i criteri con un piccolo set di utenti di produzione, effettuando le necessarie verifiche legali, di conformità e privacy nell'organizzazione. Per valutare la gestione dei rischi insider in un ambiente di testing è necessario generare azioni utente simulate e altri segnali per creare avvisi per la valutazione e i casi per l'elaborazione. Questo approccio non è pratico per la maggior parte delle organizzazioni, pertanto è preferibile testare la gestione dei rischi insider con un piccolo gruppo di utenti in un ambiente di produzione.

Mantenere abilitata la funzionalità di anonimizzazione nelle impostazioni dei criteri per anonimizzare i nomi visualizzati degli utenti nella console di gestione dei rischi insider durante questo test per mantenere la privacy all'interno dello strumento. Questa impostazione consente di proteggere la privacy degli utenti che hanno corrispondenze ai criteri e può contribuire a promuovere l'obiettività nell'analisi e nell'analisi dei dati per gli avvisi di rischio insider.

Se non vengono visualizzati avvisi subito dopo la configurazione di un criterio di gestione dei rischi insider, è possibile che la soglia minima di rischio non sia stata ancora raggiunta. Un buon modo per verificare se il criterio viene attivato e funziona come previsto è vedere se l'utente è nell'ambito del criterio nella **pagina** Utenti.

## <a name="resources-for-stakeholders"></a>Risorse per gli stakeholder

Condividere la documentazione sulla gestione dei rischi insider con gli stakeholder dell'organizzazione inclusi nel flusso di lavoro di gestione e correzione:

- [Creare e gestire i criteri dei rischi Insider](insider-risk-management-policies.md)
- [Esaminare gli avvisi relativi ai rischi Insider](insider-risk-management-alerts.md)
- [Intervenire riguardo ai casi di rischio Insider](insider-risk-management-cases.md)
- [Esaminare i dati del caso con Il rischio insider Esplora contenuto](insider-risk-management-content-explorer.md)
- [Creare modelli di avviso relativi ai rischi Insider](insider-risk-management-notices.md)

## <a name="ready-to-get-started"></a>Pronti per iniziare?

Pronto per configurare la gestione dei rischi insider per l'organizzazione? Leggere gli articoli seguenti:

- [Introduzione alle impostazioni di gestione dei rischi insider](insider-risk-management-settings.md) per configurare le impostazioni dei criteri globali.
- [Introduzione alla gestione dei rischi insider](insider-risk-management-configure.md) per configurare i prerequisiti, creare criteri e iniziare a ricevere avvisi.
