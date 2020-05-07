---
title: Pianificare la conformità alla comunicazione
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
ms.openlocfilehash: 214c5376d4c074525253707e181eee69cefff85e
ms.sourcegitcommit: eb3c7f473e8fe62624f52c9bb38dcd6a96fa58a3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "44045851"
---
# <a name="plan-for-communication-compliance"></a>Pianificare la conformità alla comunicazione

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

Selezionare revisori dedicati per monitorare e leggere gli avvisi su una cadenza regolare nel [centro conformità di Microsoft 365](https://compliance.microsoft.com/). Tenere presente che è necessario [creare un nuovo gruppo di ruoli](communication-compliance-configure.md#step-1-required-enable-permissions-for-communication-compliance) per abilitare le autorizzazioni per i revisori con l' **amministratore revisione di supervisione**, la **gestione dei casi**, l' **amministratore della conformità**e i ruoli di **Revisione** per esaminare e correggere i messaggi con le corrispondenze di criteri.

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
