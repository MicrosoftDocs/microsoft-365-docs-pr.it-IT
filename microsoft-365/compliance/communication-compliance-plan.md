---
title: Piano per la conformità delle comunicazioni
description: Informazioni sulla pianificazione dell'utilizzo della conformità di comunicazione nell'organizzazione.
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
ms.openlocfilehash: 4c44610f4d74fe9ebf3c8e549692d9cc7cc6cb34
ms.sourcegitcommit: 9550298946f8accb90cd59be7b46b71d4bf4f8cc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/08/2020
ms.locfileid: "46597423"
---
# <a name="plan-for-communication-compliance"></a>Piano per la conformità delle comunicazioni

Prima di iniziare a utilizzare la [conformità alla comunicazione](communication-compliance.md) nell'organizzazione, sono disponibili importanti attività di pianificazione e considerazioni che devono essere esaminate dai team di gestione della conformità e della tecnologia delle informazioni. La comprensione e la pianificazione approfondite per la distribuzione nelle aree seguenti consentiranno di garantire che l'implementazione e l'utilizzo delle funzionalità di conformità alla comunicazione siano uniformi e siano allineate alle procedure consigliate per la soluzione.

## <a name="work-with-stakeholders-in-your-organization"></a>Collaborare con le parti interessate nell'organizzazione

Identificare le parti interessate appropriate nell'organizzazione per collaborare per l'esecuzione di azioni sugli avvisi di conformità della comunicazione. Alcune parti interessate consigliate per valutare l'inclusione della pianificazione iniziale e del flusso di [lavoro](communication-compliance.md#workflow) per la conformità della comunicazione end-to-end sono persone provenienti dalle seguenti aree dell'organizzazione:

- Tecnologia delle informazioni
- Conformità
- Privacy
- Sicurezza
- Risorse umane
- Ufficio legale

## <a name="plan-for-the-investigation-and-remediation-workflow"></a>Pianificare il flusso di lavoro per l'analisi e la correzione

Selezionare le parti interessate dedicate per monitorare ed esaminare gli avvisi e i casi su una cadenza regolare nel [centro conformità di Microsoft 365](https://compliance.microsoft.com/). Assicurarsi di comprendere come verranno assegnati diversi ruoli di conformità della comunicazione alle parti interessate nell'organizzazione.

A seconda del modo in cui si desidera gestire i criteri di comunicazione e gli avvisi, è necessario creare uno o più nuovi gruppi di ruoli per gli amministratori, i revisori e gli investigatori. È possibile assegnare gli utenti a specifici gruppi di ruoli per gestire diversi insiemi di funzionalità di conformità della comunicazione. In alternativa, è possibile decidere di creare un gruppo di ruoli e assegnare tutti i ruoli di conformità alla comunicazione al gruppo. Creare un singolo gruppo di ruoli o più gruppi per soddisfare al meglio i requisiti di gestione della conformità.

Pianificare la scelta tra queste opzioni di ruolo quando si configurano i gruppi di ruoli di conformità della comunicazione:

|**Ruolo**|**Autorizzazioni di ruolo**|
|:-----|:-----|
| **Amministratore della conformità alla comunicazione** | Gli utenti assegnati a questo ruolo possono creare, leggere, aggiornare ed eliminare i criteri di conformità della comunicazione, le impostazioni globali e le assegnazioni dei gruppi di ruoli. Gli utenti assegnati a questo ruolo non possono visualizzare gli avvisi dei messaggi. |
| **Analisi di conformità della comunicazione** | Gli utenti assegnati a questo ruolo possono visualizzare i criteri in cui vengono assegnati come revisori, visualizzare i metadati dei messaggi (non il contenuto del messaggio), inoltrare a revisori aggiuntivi o inviare notifiche agli utenti. Gli analisti non sono in grado di risolvere gli avvisi in sospeso. |
| **Indagine di conformità della comunicazione** | Gli utenti assegnati a questo ruolo possono visualizzare i metadati e il contenuto del messaggio, inoltrare ai revisori aggiuntivi, inoltrare a un caso avanzato di eDiscovery, inviare notifiche agli utenti e risolvere l'avviso. |
| **Visualizzatore conformità comunicazione** | Gli utenti assegnati a questo ruolo possono accedere a tutti i widget per la creazione di report nella Home page conformità di comunicazione e visualizzare tutti i report di conformità della comunicazione. |
| **Gestione dei casi di conformità alla comunicazione** | Gli utenti assegnati a questo ruolo possono gestire i casi e agire sugli avvisi. Questo ruolo è necessario per la creazione di gruppi di ruoli personalizzati per amministratori, analisti e ricercatori. Non è necessario che questo ruolo sia assegnato ai gruppi personalizzati per i visualizzatori. |

## <a name="plan-for-policies"></a>Pianificare i criteri

La creazione di criteri di conformità della comunicazione è semplice e veloce con i [modelli](communication-compliance-feature-reference.md#policy-templates) predefiniti per il linguaggio offensivo, le informazioni riservate e la conformità alle normative. I criteri di conformità della comunicazione personalizzati consentono la flessibilità per individuare e indagare i problemi specifici dell'organizzazione e dei requisiti.

Quando si pianificano i criteri di conformità della comunicazione, tenere presente quanto segue:

- Valutare l'opportunità di aggiungere tutti gli utenti dell'organizzazione come ambito per i criteri di conformità della comunicazione. L'identificazione di utenti specifici come nell'ambito per i singoli criteri è utile in alcuni casi, tuttavia la maggior parte delle organizzazioni deve includere tutti gli utenti nei criteri di conformità della comunicazione ottimizzati per il rilevamento di molestie o discriminazione.
- Per semplificare l'installazione, valutare la possibilità di creare gruppi per gli utenti che hanno necessità di effettuare la revisione delle comunicazioni. Se si utilizzano i gruppi; potrebbe essere necessario più di un utente. Ad esempio, se si desidera eseguire l'analisi delle comunicazioni tra due gruppi distinti di persone oppure se si desidera specificare un gruppo non supervisionato.
- Configurare la percentuale di comunicazioni da esaminare al 100% per garantire che i criteri stiano intervenendo su tutti i problemi di comunicazione per l'organizzazione.
- È possibile eseguire l'analisi delle comunicazioni da [origini di terze parti](communication-compliance-feature-reference.md#supported-communication-types) per i dati importati nelle cassette postali nell'organizzazione Microsoft 365. Per includere la revisione delle comunicazioni in queste piattaforme, è necessario configurare un connettore per questi servizi prima che i messaggi vengano controllati dalle condizioni dei criteri di comunicazione.
- I criteri possono supportare i linguaggi di monitoraggio diversi dall'inglese nei criteri di conformità della comunicazione personalizzati. Creare una [parola chiave personalizzata dizionario](communication-compliance-feature-reference.md#custom-keyword-dictionaries) di parole offensive nella lingua di propria scelta o creare un proprio modello di apprendimento automatico utilizzando i [classificatori addestrabili](classifier-getting-started-with.md) in Microsoft 365.
- Tutte le organizzazioni hanno diversi standard di comunicazione e esigenze di criteri. Monitorare le parole chiave specifiche utilizzando [le condizioni dei criteri](communication-compliance-feature-reference.md#conditional-settings) di conformità della comunicazione o monitorare per tipi specifici di informazioni con [tipi di informazioni riservate personalizzati](create-a-custom-sensitive-information-type.md).

## <a name="ready-to-get-started"></a>Pronti per iniziare?

Per configurare la conformità di comunicazione per l'organizzazione Microsoft 365, vedere [Configure Communication Compliance for microsoft 365](communication-compliance-configure.md) o check-out the [Case Study for Contoso](communication-compliance-case-study.md) and how they configured quickly Compliance Communication Policy to monitor for offensive language in Microsoft teams, Exchange Online e Yammer Communications.
