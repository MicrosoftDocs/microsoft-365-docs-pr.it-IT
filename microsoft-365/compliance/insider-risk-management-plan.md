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
ms.openlocfilehash: ca15f26cf8eb19990c3252acf66ba50d52567e44
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "44327124"
---
# <a name="plan-for-insider-risk-management"></a>Piano per la gestione dei rischi Insider

Prima di iniziare a utilizzare la [gestione dei rischi Insider](insider-risk-management.md) nell'organizzazione, sono importanti le attività di pianificazione e le considerazioni che devono essere esaminate dai team di gestione della conformità e della tecnologia delle informazioni. La comprensione e la pianificazione approfondite per la distribuzione nelle aree seguenti consentiranno di garantire che l'implementazione e l'utilizzo delle funzionalità di gestione dei rischi Insider siano uniformi e siano allineate alle procedure consigliate per la soluzione.

## <a name="work-with-stakeholders-in-your-organization"></a>Collaborare con le parti interessate nell'organizzazione

Identificare le parti interessate appropriate nell'organizzazione per collaborare all'esecuzione di azioni su avvisi e casi di gestione dei rischi Insider. Alcune parti interessate consigliate per valutare l'inclusione della pianificazione iniziale e del flusso di lavoro end-to-end di [gestione dei rischi Insider](insider-risk-management.md#workflow) sono persone provenienti dalle aree dell'organizzazione seguenti:

- Tecnologia delle informazioni
- Conformità
- Privacy
- Sicurezza
- Risorse umane
- Ufficio legale

## <a name="determine-any-regional-compliance-requirements"></a>Determinare i requisiti di conformità regionali

Diverse aree geografiche e organizzative possono avere requisiti per la conformità e la privacy che sono significativamente diversi da altre aree dell'organizzazione. Collaborare con le parti interessate in queste aree per assicurarsi che siano in grado di comprendere i controlli relativi alla conformità e alla privacy nella gestione dei rischi Insider e come devono essere utilizzati in aree diverse dell'organizzazione. In alcuni scenari, i requisiti relativi alla conformità e alla privacy potrebbero richiedere criteri che designino o limitino alcune parti interessate da indagini e casi in base alla causa di un utente o ai requisiti normativi o di criteri per l'area.

Se si dispone di requisiti per coinvolgere specifiche parti interessate nel caso di indagini che coinvolgono dipendenti in determinate aree geografiche, ruoli o divisioni, è possibile implementare [criteri di gestione dei rischi](insider-risk-management-policies.md) separati (anche se identici) che si riferiscono a diverse aree geografiche e popolazioni. In questo modo, è più facile per gli stakeholder giusti valutare e gestire i casi rilevanti per i ruoli e le aree geografiche. È inoltre possibile valutare la possibilità di creare processi e criteri per le aree geografiche in cui gli investigatori e i revisori parlano la stessa lingua degli utenti per semplificare il processo di escalation per gli avvisi e i casi di gestione dei rischi Insider.

## <a name="plan-for-the-review-and-investigation-workflow"></a>Pianificare il flusso di lavoro per la revisione e l'analisi

Selezionare le parti interessate dedicate per monitorare ed esaminare gli avvisi e i casi su una cadenza regolare nel [centro conformità di Microsoft 365](https://compliance.microsoft.com/). Assicurarsi di comprendere come verranno assegnate diverse parti interessate ai diversi gruppi di ruoli disponibili nella gestione dei rischi Insider.

A seconda della struttura del team di gestione della conformità, sono disponibili opzioni per assegnare gli utenti a specifici gruppi di ruoli per gestire diversi insiemi di funzionalità di gestione dei rischi Insider. Scegliere da queste opzioni del gruppo di ruolo durante la configurazione della gestione dei rischi Insider:

| **Gruppo di ruolo** | **Autorizzazioni di ruolo** |
| :---- | :---------------- |
| **Gestione dei rischi Insider** | Utilizzare questo gruppo di ruoli per gestire la gestione dei rischi Insider per la propria organizzazione in un singolo gruppo. Aggiungendo tutti gli account utente per gli amministratori, gli analisti e gli investigatori designati, è possibile configurare le autorizzazioni di gestione dei rischi insider in un singolo gruppo. Questo gruppo di ruoli contiene tutti i ruoli di autorizzazione di gestione dei rischi Insider. Questa configurazione è il modo più semplice per iniziare rapidamente con la gestione dei rischi Insider ed è adatta per le organizzazioni che non necessitano di autorizzazioni separate definite per gruppi di utenti separati.|
| **Amministratore di gestione dei rischi Insider** | Utilizzare questo gruppo di ruoli per configurare inizialmente la gestione dei rischi Insider e successivamente per separare gli amministratori del rischio insider in un gruppo definito.  Gli utenti di questo gruppo di ruoli possono creare, leggere, aggiornare ed eliminare i criteri di gestione dei rischi Insider, le impostazioni globali e le assegnazioni di gruppi di ruoli. |
| **Analisti di gestione dei rischi Insider** | Utilizzare questo gruppo per assegnare le autorizzazioni agli utenti che fungeranno da analisti dei casi di rischio Insider. Gli utenti di questo gruppo di ruoli possono accedere a tutti i modelli di avvisi, casi e notifiche di gestione dei rischi Insider. Non possono accedere all'esploratore di contenuto a rischio Insider. |
| **Investigatori della gestione dei rischi Insider** | Utilizzare questo gruppo per assegnare le autorizzazioni agli utenti che agiranno come investigatori dei dati di rischio Insider. Gli utenti di questo gruppo di ruoli possono accedere a tutti gli avvisi di gestione dei rischi Insider, i casi, i modelli di avvisi e l'Esplora contenuto per tutti i casi. |

## <a name="understand-requirements-and-dependencies"></a>Comprendere i requisiti e le dipendenze

A seconda del modo in cui si prevede di implementare i criteri di gestione dei rischi Insider, è necessario disporre delle sottoscrizioni di licenza Microsoft 365 appropriate e comprendere e pianificare alcuni prerequisiti della soluzione.

**Licenze:** La gestione dei rischi Insider è disponibile come parte di una vasta gamma di abbonamenti alle licenze Microsoft 365. Per informazioni dettagliate, vedere la [Guida introduttiva all'articolo sulla gestione dei rischi Insider](insider-risk-management-configure.md#before-you-begin) .

Se non si dispone di un piano Microsoft 365 Enterprise E5 esistente e si desidera tentare la gestione dei rischi Insider, è possibile [aggiungere microsoft 365](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) alla sottoscrizione esistente oppure [iscriversi per una versione di valutazione](https://www.microsoft.com/microsoft-365/enterprise) di Microsoft 365 Enterprise E5.

**Requisiti dei modelli di criteri:** A seconda del modello di criteri, potrebbero essere necessari requisiti per comprendere e pianificare prima di configurare la gestione dei rischi Insider nell'organizzazione:

- Quando si utilizza il modello di **furto dei dati** per i dipendenti in uscita, è necessario configurare un connettore Microsoft 365 HR per importare periodicamente le informazioni relative alle dimissioni e alla data di fine per gli impiegati dell'organizzazione. Per informazioni dettagliate su come configurare il connettore Microsoft 365 HR per l'organizzazione, vedere l'argomento [Import Data with the HR Connector](import-hr-data.md) .
- Quando si utilizza il modello per le **perdite di dati** , è necessario configurare almeno un criterio di prevenzione della perdita di dati (DLP) per definire le informazioni riservate nell'organizzazione e ricevere avvisi di rischio Insider per gli avvisi di criteri DLP di elevata gravità. Per informazioni dettagliate su come configurare i criteri DLP per la propria organizzazione, vedere l'argomento [creare, testare e ottimizzare un criterio DLP](create-test-tune-dlp-policy.md) .

## <a name="test-with-a-small-group-of-users-in-a-production-environment"></a>Eseguire il test con un gruppo limitato di utenti in un ambiente di produzione

Prima di abilitare la soluzione in modo generale nell'ambiente di produzione, è possibile esaminare i criteri con un piccolo gruppo di utenti di produzione durante l'esecuzione di una richiesta di conformità, privacy e giudizi legali nell'organizzazione. La valutazione della gestione dei rischi insider in un ambiente di testing richiede che vengano generate azioni utente simulate e altri segnali per creare avvisi per la valutazione e i casi di elaborazione. Spesso questo non è pratico per la maggior parte delle organizzazioni, quindi è preferibile testare la gestione dei rischi Insider con un piccolo gruppo di utenti in un ambiente di produzione.

Mantenere la caratteristica Anonymization nelle impostazioni dei criteri abilitata a pseudonymize i nomi visualizzati dall'utente nella console di gestione dei rischi Insider durante questo testing per mantenere la privacy all'interno dello strumento. Questo consente di proteggere la privacy degli utenti che hanno corrispondenze di criteri e può contribuire a promuovere l'oggettività nelle analisi dei dati e nelle recensioni di informazioni per gli avvisi sui rischi Inside

Se non vengono visualizzati avvisi subito dopo la configurazione di un criterio di gestione dei rischi Insider, può significare che la soglia di rischio minima non è ancora stata soddisfatta. Un buon modo per controllare se il criterio viene attivato e funzionante come previsto è vedere se l'utente è in ambito per il criterio nella pagina **utenti** .

## <a name="resources-for-stakeholders"></a>Risorse per le parti interessate

Condividere la documentazione relativa alla gestione dei rischi Insider con le parti interessate nell'organizzazione incluse nel flusso di lavoro per la gestione e la correzione:

- [Creare e gestire i criteri dei rischi Insider](insider-risk-management-policies.md)
- [Esaminare gli avvisi relativi ai rischi Insider](insider-risk-management-alerts.md)
- [Intervenire riguardo ai casi di rischio Insider](insider-risk-management-cases.md)
- [Esaminare i dati dei casi con l'esploratore dei contenuti di rischio Insider](insider-risk-management-content-explorer.md)
- [Creare modelli di avviso relativi ai rischi Insider](insider-risk-management-notices.md)

## <a name="ready-to-get-started"></a>Pronti per iniziare?

È possibile configurare la gestione dei rischi Insider per la propria organizzazione? Vedere [Introduzione alla gestione dei rischi Insider](insider-risk-management-configure.md) per configurare i prerequisiti, creare criteri e iniziare a ricevere avvisi.
