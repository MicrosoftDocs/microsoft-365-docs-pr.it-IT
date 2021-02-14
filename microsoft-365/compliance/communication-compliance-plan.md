---
title: Piano per la conformità delle comunicazioni
description: Informazioni sulla pianificazione dell'utilizzo della conformità delle comunicazioni nell'organizzazione.
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: d64edc9d80722080db18c45127bfc82110d1ea9e
ms.sourcegitcommit: fdb5f9d865037c0ae23aae34a5c0f06b625b2f69
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/18/2020
ms.locfileid: "48131538"
---
# <a name="plan-for-communication-compliance"></a>Piano per la conformità delle comunicazioni

Prima di iniziare a [usare](communication-compliance.md) la conformità delle comunicazioni nell'organizzazione, esistono importanti attività e considerazioni di pianificazione che devono essere esaminate dai team di information technology e di gestione della conformità. Una conoscenza approfondita e una pianificazione approfondita della distribuzione nelle aree seguenti consentono di garantire che l'implementazione e l'uso delle funzionalità di conformità delle comunicazioni siano uniformi e siano allineati alle procedure consigliate per la soluzione.

## <a name="work-with-stakeholders-in-your-organization"></a>Collaborare con gli stakeholder dell'organizzazione

Identificare le parti interessate appropriate nell'organizzazione per collaborare per eseguire azioni sugli avvisi di conformità delle comunicazioni. Alcuni stakeholder consigliati da prendere in considerazione, [](communication-compliance.md#workflow) tra cui la pianificazione iniziale e il flusso di lavoro di conformità delle comunicazioni end-to-end, sono persone delle aree seguenti dell'organizzazione:

- Information Technology
- Conformità
- Privacy
- Sicurezza
- Risorse umane
- Esigenze legali

## <a name="plan-for-the-investigation-and-remediation-workflow"></a>Pianificare il flusso di lavoro di analisi e correzione

Selezionare gli stakeholder dedicati per monitorare ed esaminare gli avvisi e i casi con cadenza regolare nel Centro conformità [Microsoft 365.](https://compliance.microsoft.com/) Assicurarsi di comprendere come assegnare utenti e cointeressati ai diversi gruppi di ruoli di conformità delle comunicazioni nell'organizzazione.

A seconda di come si desidera gestire gli avvisi e i criteri di comunicazione, è necessario assegnare gli utenti a uno o più gruppi di ruoli per amministratori, revisori e investigatori. È possibile assegnare utenti a gruppi di ruoli specifici per gestire diversi set di funzionalità di conformità delle comunicazioni. Oppure si può decidere di assegnare tutti gli utenti di conformità delle comunicazioni al gruppo di ruoli Conformità comunicazioni. Utilizzare uno o più gruppi di ruoli per soddisfare al meglio i requisiti di gestione della conformità.

Pianificare la scelta tra queste opzioni del gruppo di ruoli durante la configurazione della conformità delle comunicazioni:

|**Ruolo**|**Autorizzazioni di ruolo**|
|:-----|:-----|
| **Conformità delle comunicazioni** | Utilizzare questo gruppo di ruoli per gestire la conformità delle comunicazioni per l'organizzazione in un singolo gruppo. Aggiungendo tutti gli account utente per amministratori, analisti, investigatori e visualizzatori designati, è possibile configurare le autorizzazioni di conformità delle comunicazioni in un singolo gruppo. Questo gruppo di ruoli contiene tutti i ruoli di autorizzazione di conformità delle comunicazioni. Questa configurazione è il modo più semplice per iniziare rapidamente a usare la conformità delle comunicazioni ed è adatta per le organizzazioni che non necessitano di autorizzazioni separate definite per gruppi di utenti separati. |
| **Communication Compliance Admin** | Utilizzare questo gruppo di ruoli per configurare inizialmente la conformità delle comunicazioni e successivamente per separare gli amministratori della conformità delle comunicazioni in un gruppo definito. Gli utenti assegnati a questo gruppo di ruoli possono creare, leggere, aggiornare ed eliminare i criteri di conformità delle comunicazioni, le impostazioni globali e le assegnazioni dei gruppi di ruoli. Gli utenti assegnati a questo gruppo di ruoli non possono visualizzare gli avvisi dei messaggi. |
| **Analista di conformità delle comunicazioni** | Utilizzare questo gruppo per assegnare autorizzazioni agli utenti che fungeranno da analisti della conformità delle comunicazioni. Gli utenti assegnati a questo gruppo di ruoli possono visualizzare i criteri in cui sono assegnati come revisori, visualizzare i metadati dei messaggi (non il contenuto dei messaggi), inoltrare ad altri revisori o inviare notifiche agli utenti. Gli analisti non possono risolvere gli avvisi in sospeso. |
| **Communication Compliance Investigator** | Utilizzare questo gruppo per assegnare autorizzazioni agli utenti che fungeranno da investigatori della conformità delle comunicazioni. Gli utenti assegnati a questo gruppo di ruoli possono visualizzare i metadati e il contenuto dei messaggi, inoltrare ad altri revisori, inoltrare a un caso di Advanced eDiscovery, inviare notifiche agli utenti e risolvere l'avviso. |
| **Visualizzatore conformità comunicazioni** | Utilizzare questo gruppo per assegnare autorizzazioni agli utenti che gestiranno i report di comunicazione. Gli utenti assegnati a questo gruppo di ruoli possono accedere a tutti i widget di report nella home page di conformità delle comunicazioni e visualizzare tutti i report di conformità delle comunicazioni. |

## <a name="plan-for-policies"></a>Pianificare i criteri

La creazione di criteri di [](communication-compliance-feature-reference.md#policy-templates) conformità delle comunicazioni è rapida e semplice con i modelli predefiniti per il linguaggio offensivo, le informazioni riservate e la conformità alle normative. I criteri di conformità delle comunicazioni personalizzati consentono di rilevare e indagare i problemi specifici dell'organizzazione e dei requisiti.

Quando si pianificano i criteri di conformità delle comunicazioni, considerare le aree seguenti:

- Considerare l'aggiunta di tutti gli utenti dell'organizzazione come nell'ambito dei criteri di conformità delle comunicazioni. L'identificazione di utenti specifici come nell'ambito dei singoli criteri è utile in alcune circostanze, tuttavia la maggior parte delle organizzazioni deve includere tutti gli utenti nei criteri di conformità delle comunicazioni ottimizzati per il rilevamento di molestie o molestie.
- Per semplificare la configurazione, prendere in considerazione la creazione di gruppi per gli utenti che necessitano di una revisione delle comunicazioni. Se si usano gruppi; potrebbero essere necessari diversi. Ad esempio, se si desidera analizzare le comunicazioni tra due gruppi distinti di persone o se si desidera specificare un gruppo che non è supervisionato.
- Configurare la percentuale di comunicazioni da rivedere al 100% per garantire che i criteri intercettino tutti i problemi di interesse nelle comunicazioni per l'organizzazione.
- È possibile analizzare le comunicazioni [da origini di terze parti](communication-compliance-feature-reference.md#supported-communication-types) per i dati importati nelle cassette postali dell'organizzazione di Microsoft 365. Per includere la revisione delle comunicazioni in queste piattaforme, è necessario configurare un connettore per questi servizi prima che i messaggi che soddicheranno le condizioni dei criteri siano monitorati dai criteri di comunicazione.
- I criteri possono supportare lingue di monitoraggio diverse dall'inglese nei criteri di conformità delle comunicazioni personalizzati. Creare un [dizionario di](communication-compliance-feature-reference.md#custom-keyword-dictionaries) parole chiave personalizzato di parole offensive nel linguaggio scelto o creare un modello di apprendimento automatico personalizzato usando classificatori formabili [in](classifier-get-started-with.md) Microsoft 365.
- Tutte le organizzazioni hanno standard di comunicazione e esigenze di criteri diversi. Monitorare la ricerca di [](communication-compliance-feature-reference.md#conditional-settings) parole chiave specifiche utilizzando le condizioni dei criteri di conformità delle comunicazioni o monitorare tipi specifici di informazioni con [tipi di informazioni sensibili personalizzati.](create-a-custom-sensitive-information-type.md)

## <a name="ready-to-get-started"></a>Pronti per iniziare?

Per configurare la conformità delle comunicazioni per l'organizzazione di Microsoft 365, vedere Configurare la conformità delle comunicazioni per [Microsoft 365](communication-compliance-configure.md) o consultare il [case study](communication-compliance-case-study.md) per Contoso e come ha configurato rapidamente un criterio di conformità delle comunicazioni per monitorare il linguaggio offensivo nelle comunicazioni di Microsoft Teams, Exchange Online e Yammer.
