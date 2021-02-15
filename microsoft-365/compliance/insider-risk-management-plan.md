---
title: Piano per la gestione dei rischi Insider
description: Informazioni su come pianificare l'utilizzo dei criteri di gestione dei rischi Insider nell'organizzazione.
keywords: Microsoft 365, rischio Insider, gestione dei rischi, conformità
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
ms.openlocfilehash: f2581c4756a57926ab4a4539be8c383b0479e567
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126625"
---
# <a name="plan-for-insider-risk-management"></a>Piano per la gestione dei rischi Insider

Prima di iniziare a usare la gestione dei rischi [Insider](insider-risk-management.md) nell'organizzazione, sono presenti importanti attività e considerazioni di pianificazione che devono essere esaminate dai team di gestione delle informazioni e della conformità. Una conoscenza approfondita e una pianificazione approfondita della distribuzione nelle aree seguenti consentono di garantire che l'implementazione e l'uso delle funzionalità di gestione dei rischi Insider siano uniformi e siano allineati alle procedure consigliate per la soluzione.

## <a name="work-with-stakeholders-in-your-organization"></a>Collaborare con gli stakeholder dell'organizzazione

Identificare gli stakeholder appropriati nell'organizzazione per collaborare per eseguire azioni su avvisi e casi di gestione dei rischi Insider. Alcuni stakeholder consigliati da prendere in considerazione, tra cui la pianificazione iniziale e il flusso di lavoro end-to-end [insider risk management,](insider-risk-management.md#workflow) sono persone delle aree seguenti dell'organizzazione:

- Information Technology
- Conformità
- Privacy
- Sicurezza
- Risorse umane
- Esigenze legali

## <a name="determine-any-regional-compliance-requirements"></a>Determinare eventuali requisiti di conformità regionali

Aree geografiche e organizzative diverse possono avere requisiti di conformità e privacy diversi da altre aree dell'organizzazione. Collaborare con le parti interessate in queste aree per assicurarsi che comprenda i controlli di conformità e privacy nella gestione dei rischi insider e come devono essere utilizzati in diverse aree dell'organizzazione. In alcuni scenari, i requisiti di conformità e privacy potrebbero richiedere criteri che designino o restringeno alcune parti interessate da indagini e casi in base al caso di un utente o a requisiti normativi o di criteri per l'area.

Se si dispone di requisiti per specifici stakeholder da coinvolgere in indagini caso che coinvolgono utenti in determinate aree geografiche, ruoli o divisioni, è possibile implementare criteri di gestione dei rischi [Insider](insider-risk-management-policies.md) separati (anche se identici) per le diverse aree geografiche e le diverse popolazioni. Questa configurazione agevola la ricerca e la gestione dei casi rilevanti per i ruoli e le aree geografiche dei cointeressati. Inoltre, è consigliabile creare processi e criteri per le aree geografiche in cui investigatori e revisori parlano la stessa lingua degli utenti per semplificare il processo di escalation per gli avvisi e i casi di gestione dei rischi Insider.

## <a name="plan-for-the-review-and-investigation-workflow"></a>Pianificare il flusso di lavoro di revisione e analisi

Selezionare gli stakeholder dedicati per monitorare ed esaminare gli avvisi e i casi con cadenza regolare nel Centro conformità [Microsoft 365.](https://compliance.microsoft.com/) Assicurarsi di comprendere come assegnare le diverse parti interessate ai diversi gruppi di ruoli disponibili nella gestione dei rischi Insider.

A seconda della struttura del team di gestione della conformità, sono disponibili opzioni per assegnare utenti a gruppi di ruoli specifici per gestire diversi set di funzionalità di gestione dei rischi Insider. Scegliere tra queste opzioni del gruppo di ruoli quando si configura la gestione dei rischi Insider:

| **Gruppo di ruolo** | **Autorizzazioni di ruolo** |
| :---- | :---------------- |
| **Gestione dei rischi Insider** | Utilizzare questo gruppo di ruoli per gestire la gestione dei rischi Insider per l'organizzazione in un singolo gruppo. Aggiungendo tutti gli account utente per amministratori, analisti e investigatori designati, è possibile configurare le autorizzazioni di gestione dei rischi Insider in un singolo gruppo. Questo gruppo di ruoli contiene tutti i ruoli di autorizzazione per la gestione dei rischi Insider. Questa configurazione è il modo più semplice per iniziare rapidamente a usare la gestione dei rischi Insider ed è adatta per le organizzazioni che non necessitano di autorizzazioni separate definite per gruppi di utenti separati.|
| **Amministratore gestione dei rischi Insider** | Utilizzare questo gruppo di ruoli per configurare inizialmente la gestione dei rischi Insider e successivamente per separare gli amministratori dei rischi Insider in un gruppo definito.  Gli utenti di questo gruppo di ruoli possono creare, leggere, aggiornare ed eliminare i criteri di gestione dei rischi Insider, le impostazioni globali e le assegnazioni dei gruppi di ruoli. |
| **Analisti gestione dei rischi Insider** | Utilizzare questo gruppo per assegnare autorizzazioni agli utenti che fungeranno da analisti dei casi di rischio Insider. Gli utenti di questo gruppo di ruoli possono accedere a tutti i modelli di avvisi, casi e avvisi per la gestione dei rischi Insider. Non possono accedere a Esplora contenuto con rischio Insider. |
| **Investigatori gestione dei rischi Insider** | Utilizzare questo gruppo per assegnare autorizzazioni agli utenti che agiranno come investigatori dei dati di rischio Insider. Gli utenti di questo gruppo di ruoli possono accedere a tutti gli avvisi di gestione dei rischi Insider, i casi, i modelli di avviso e Esplora contenuto per tutti i casi. |

## <a name="understand-requirements-and-dependencies"></a>Informazioni su requisiti e dipendenze

A seconda di come si prevede di implementare i criteri di gestione dei rischi Insider, è necessario disporre degli abbonamenti alle licenze di Microsoft 365 adeguati e comprendere e pianificare alcuni prerequisiti della soluzione.

**Licenze:** La gestione dei rischi Insider è disponibile nell'ambito di un'ampia selezione di abbonamenti alle licenze di Microsoft 365. Per informazioni dettagliate, vedere [l'articolo Introduttivo alla gestione dei rischi Insider.](insider-risk-management-configure.md#subscriptions-and-licensing)

Se non si dispone di un piano Microsoft 365 Enterprise E5 esistente e si vuole provare la gestione dei rischi Insider, è possibile aggiungere [Microsoft 365](/office365/admin/try-or-buy-microsoft-365) all'abbonamento esistente o iscriversi [per](https://www.microsoft.com/microsoft-365/enterprise) una versione di valutazione di Microsoft 365 Enterprise E5.

**Requisiti dei modelli di criteri:** A seconda del modello di criteri scelto, è necessario comprendere e pianificare i requisiti prima di configurare la gestione dei rischi Insider nell'organizzazione:

- Quando si  usa il modello di furto di dati da parte degli utenti, è necessario configurare un connettore per le risorse umane di Microsoft 365 per importare periodicamente le informazioni sulla data di licenziamento e di chiusura per gli utenti dell'organizzazione. Per istruzioni [dettagliate](import-hr-data.md) sulla configurazione del connettore risorse umane di Microsoft 365 per l'organizzazione, vedere l'articolo Importare dati con il connettore risorse umane.
- Quando  si utilizzano modelli di perdita di dati, è necessario configurare almeno un criterio di prevenzione della perdita dei dati (DLP) per definire le informazioni riservate nell'organizzazione e per ricevere avvisi di rischio Insider per gli avvisi dei criteri DLP di gravità elevata. Vedere [l'articolo creare, testare e](create-test-tune-dlp-policy.md) ottimizzare un criterio DLP per istruzioni dettagliate per configurare i criteri DLP per l'organizzazione.
- Quando si usano **modelli di violazione dei** criteri di sicurezza, è necessario abilitare Microsoft Defender for Endpoint per l'integrazione della gestione dei rischi Insider in Defender Security Center per importare gli avvisi di violazione della sicurezza. Vedi [l'articolo Configurare le funzionalità avanzate in Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/advanced-features) per istruzioni dettagliate per abilitare l'integrazione di Defender for Endpoint con la gestione dei rischi Insider.
- Quando si usano **modelli utente** scontenti, è necessario configurare un connettore risorse umane di Microsoft 365 per importare periodicamente informazioni sullo stato di prestazioni o abbassamento di livello per gli utenti dell'organizzazione. Per istruzioni [dettagliate](import-hr-data.md) sulla configurazione del connettore risorse umane di Microsoft 365 per l'organizzazione, vedere l'articolo Importare dati con il connettore risorse umane.

## <a name="test-with-a-small-group-of-users-in-a-production-environment"></a>Testare con un piccolo gruppo di utenti in un ambiente di produzione

Prima di abilitare la soluzione a livello generale nell'ambiente di produzione, è consigliabile testare i criteri con un piccolo gruppo di utenti di produzione durante l'esecuzione delle revisioni legali, della conformità e della privacy necessarie nell'organizzazione. La valutazione della gestione dei rischi insider in un ambiente di testing richiederebbe la generazione di azioni utente simulate e di altri segnali per creare avvisi per la valutazione e casi per l'elaborazione. Questo approccio non è pratico per la maggior parte delle organizzazioni, pertanto è preferibile testare la gestione dei rischi Insider con un piccolo gruppo di utenti in un ambiente di produzione.

Mantenere abilitata la funzionalità di anonimizzazione nelle impostazioni dei criteri per anonimizzare i nomi visualizzati degli utenti nella console di gestione dei rischi Insider durante questo test per mantenere la privacy all'interno dello strumento. Questa impostazione consente di proteggere la privacy degli utenti che hanno corrispondenze ai criteri e di promuovere l'obiettività nell'analisi e nell'analisi dei dati per gli avvisi di rischio Insider.

Se non vengono visualizzati avvisi subito dopo la configurazione di un criterio di gestione dei rischi Insider, è possibile che la soglia minima di rischio non sia stata ancora raggiunta. Un buon modo per verificare se il criterio viene attivato e funziona come previsto è vedere se l'utente è nell'ambito del criterio nella **pagina** Utenti.

## <a name="resources-for-stakeholders"></a>Risorse per gli stakeholder

Condividere la documentazione sulla gestione dei rischi insider con gli stakeholder dell'organizzazione inclusi nel flusso di lavoro di gestione e correzione:

- [Creare e gestire i criteri dei rischi Insider](insider-risk-management-policies.md)
- [Esaminare gli avvisi relativi ai rischi Insider](insider-risk-management-alerts.md)
- [Intervenire riguardo ai casi di rischio Insider](insider-risk-management-cases.md)
- [Esaminare i dati del caso con Esplora contenuto rischio Insider](insider-risk-management-content-explorer.md)
- [Creare modelli di avviso relativi ai rischi Insider](insider-risk-management-notices.md)

## <a name="ready-to-get-started"></a>Pronti per iniziare?

Sei pronto a configurare la gestione dei rischi Insider per la tua organizzazione? Leggere gli articoli seguenti:

- [Introduzione alle impostazioni di gestione dei rischi Insider](insider-risk-management-settings.md) per configurare le impostazioni dei criteri globali.
- [Introduzione alla gestione dei rischi Insider per](insider-risk-management-configure.md) configurare i prerequisiti, creare criteri e iniziare a ricevere avvisi.
