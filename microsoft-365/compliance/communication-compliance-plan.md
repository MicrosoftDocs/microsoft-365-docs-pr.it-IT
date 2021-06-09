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

Prima di iniziare a utilizzare [la conformità](communication-compliance.md) delle comunicazioni nell'organizzazione, esistono importanti attività e considerazioni di pianificazione che devono essere esaminate dai team di information technology e di gestione della conformità. La comprensione approfondita e la pianificazione della distribuzione nelle aree seguenti consentono di garantire che l'implementazione e l'utilizzo delle funzionalità di conformità delle comunicazioni siano uniformi e siano allineati alle procedure consigliate per la soluzione.

## <a name="work-with-stakeholders-in-your-organization"></a>Collaborare con le parti interessate nell'organizzazione

Identificare le parti interessate appropriate nell'organizzazione per collaborare per l'applicazione di azioni sugli avvisi di conformità delle comunicazioni. Alcuni stakeholder consigliati da prendere in considerazione, inclusi nella pianificazione iniziale e nel flusso di lavoro end-to-end [per](communication-compliance.md#workflow) la conformità delle comunicazioni, sono persone provenienti dalle aree seguenti dell'organizzazione:

- Information technology
- Conformità
- Privacy
- Sicurezza
- Risorse umane
- Esigenze legali

## <a name="plan-for-the-investigation-and-remediation-workflow"></a>Pianificare il flusso di lavoro di analisi e correzione

Selezionare stakeholder dedicati per monitorare ed esaminare gli avvisi e i casi a cadenza regolare nel Centro [Microsoft 365 conformità](https://compliance.microsoft.com/). Assicurarsi di comprendere come assegnare utenti e cointeressati a diversi gruppi di ruoli di conformità delle comunicazioni nell'organizzazione.

A seconda di come si desidera gestire gli avvisi e i criteri di comunicazione, è necessario assegnare gli utenti a uno o più gruppi di ruoli per amministratori, revisori e investigatori. È possibile assegnare utenti a gruppi di ruoli specifici per gestire diversi set di funzionalità di conformità delle comunicazioni. Oppure si può decidere di assegnare tutti gli utenti di conformità delle comunicazioni al gruppo di ruoli Conformità comunicazione. Utilizzare uno o più gruppi di ruoli per soddisfare al meglio i requisiti di gestione della conformità.

Pianificare la scelta tra queste opzioni del gruppo di ruoli durante la configurazione della conformità delle comunicazioni:

|**Ruolo**|**Autorizzazioni del ruolo**|
|:-----|:-----|
| **Conformità delle comunicazioni** | Utilizzare questo gruppo di ruoli per gestire la conformità delle comunicazioni per l'organizzazione in un singolo gruppo. Aggiungendo tutti gli account utente per amministratori, analisti, investigatori e visualizzatori designati, è possibile configurare le autorizzazioni di conformità delle comunicazioni in un singolo gruppo. Questo gruppo di ruoli contiene tutti i ruoli di autorizzazione di conformità delle comunicazioni. Questa configurazione è il modo più semplice per iniziare rapidamente a utilizzare la conformità delle comunicazioni ed è adatta per le organizzazioni che non necessitano di autorizzazioni separate definite per gruppi di utenti distinti. |
| **Amministratore per la conformità delle comunicazioni** | Utilizzare questo gruppo di ruoli per configurare inizialmente la conformità delle comunicazioni e successivamente per separare gli amministratori di conformità delle comunicazioni in un gruppo definito. Gli utenti assegnati a questo gruppo di ruoli possono creare, leggere, aggiornare ed eliminare criteri di conformità delle comunicazioni, impostazioni globali e assegnazioni di gruppi di ruoli. Gli utenti assegnati a questo gruppo di ruoli non possono visualizzare gli avvisi dei messaggi. |
| **Communication Compliance Analyst** | Utilizzare questo gruppo per assegnare autorizzazioni agli utenti che fungeranno da analisti della conformità delle comunicazioni. Gli utenti assegnati a questo gruppo di ruoli possono visualizzare i criteri in cui sono assegnati come revisori, visualizzare i metadati dei messaggi (non il contenuto del messaggio), inoltrare ad altri revisori o inviare notifiche agli utenti. Gli analisti non possono risolvere gli avvisi in sospeso. |
| **Communication Compliance Investigator** | Utilizzare questo gruppo per assegnare autorizzazioni agli utenti che agiranno come investigatori della conformità delle comunicazioni. Gli utenti assegnati a questo gruppo di ruoli possono visualizzare i metadati e il contenuto dei messaggi, inoltrare a revisori aggiuntivi, inoltrare a un caso di Advanced eDiscovery, inviare notifiche agli utenti e risolvere l'avviso. |
| **Visualizzatore della conformità delle comunicazioni** | Utilizzare questo gruppo per assegnare autorizzazioni agli utenti che gestiranno i report di comunicazione. Gli utenti assegnati a questo gruppo di ruoli possono accedere a tutti i widget di report nella home page di conformità delle comunicazioni e possono visualizzare tutti i report di conformità delle comunicazioni. |

## <a name="plan-for-policies"></a>Pianificare i criteri

La creazione di criteri di [](communication-compliance-feature-reference.md#policy-templates) conformità delle comunicazioni è semplice e veloce con i modelli predefiniti per il linguaggio offensivo, le informazioni riservate e la conformità normativa. I criteri di conformità delle comunicazioni personalizzati consentono di rilevare e indagare i problemi specifici dell'organizzazione e dei requisiti.

Quando si pianificano i criteri di conformità delle comunicazioni, considerare le aree seguenti:

- Prendere in considerazione l'aggiunta di tutti gli utenti dell'organizzazione come nell'ambito dei criteri di conformità delle comunicazioni. L'identificazione di utenti specifici come nell'ambito di singoli criteri è utile in alcune circostanze, tuttavia la maggior parte delle organizzazioni deve includere tutti gli utenti nei criteri di conformità delle comunicazioni ottimizzati per il rilevamento di molestie o discriminazioni.
- Per semplificare la configurazione, è consigliabile creare gruppi per gli utenti che necessitano di una revisione delle comunicazioni. Se si usano gruppi; potrebbero essere necessari diversi. ad esempio per controllare le comunicazioni tra due diversi gruppi di utenti oppure se si vuole specificare che un gruppo non sarà supervisionato.
- Configurare la percentuale di comunicazioni da esaminare al 100% per garantire che i criteri riesercino tutti i problemi di interesse nelle comunicazioni per l'organizzazione.
- È possibile analizzare le comunicazioni [da origini di terze parti](communication-compliance-feature-reference.md#supported-communication-types) per i dati importati nelle cassette postali dell'Microsoft 365 organizzazione. Per includere la revisione delle comunicazioni in queste piattaforme, è necessario configurare un connettore per questi servizi prima che i messaggi che sodicheranno le condizioni dei criteri siano monitorati dai criteri di comunicazione.
- I criteri possono supportare lingue di monitoraggio diverse dall'inglese nei criteri di conformità alle comunicazioni personalizzati. Crea un [dizionario di](communication-compliance-feature-reference.md#custom-keyword-dictionaries) parole chiave personalizzato di parole offensive nel linguaggio scelto o crea il tuo modello di apprendimento automatico usando classificatori addestrabili [in](classifier-get-started-with.md) Microsoft 365.
- Tutte le organizzazioni hanno standard di comunicazione e esigenze di criteri diversi. Monitorare la ricerca di parole chiave specifiche utilizzando le condizioni dei [criteri](communication-compliance-feature-reference.md#conditional-settings) di conformità delle comunicazioni o monitorare la ricerca di tipi specifici di informazioni con tipi di informazioni [riservate personalizzati.](create-a-custom-sensitive-information-type.md)

## <a name="ready-to-get-started"></a>Pronti per iniziare?

Per configurare la conformità delle comunicazioni per l'organizzazione di Microsoft 365, vedere Configurare la conformità delle comunicazioni per [Microsoft 365](communication-compliance-configure.md) o consultare il [case study](communication-compliance-case-study.md) per Contoso e come hanno configurato rapidamente un criterio di conformità delle comunicazioni per monitorare la lingua offensiva nelle comunicazioni Microsoft Teams, Exchange Online e Yammer.
