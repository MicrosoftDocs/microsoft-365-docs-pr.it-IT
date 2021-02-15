---
title: Distribuire la protezione delle informazioni per le normative sulla privacy dei dati con Microsoft 365
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/22/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-overview
ms.custom: ''
description: Configurare l'infrastruttura di sicurezza e di servizio per proteggere le informazioni e rispettare le normative sulla privacy dei dati.
ms.openlocfilehash: 9af0a113d9b0eb2cbca07fdf457cd8bb7db3e094
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842297"
---
# <a name="deploy-information-protection-for-data-privacy-regulations-with-microsoft-365"></a>Distribuire la protezione delle informazioni per le normative sulla privacy dei dati con Microsoft 365

L'organizzazione potrebbe essere soggetta a normative regionali sulla privacy dei dati che richiedono di proteggere, gestire e fornire diritti e controllo sulle informazioni personali archiviate nell'infrastruttura IT, sia in locale che nel cloud. L'esempio migliore di una normativa sulla privacy dei dati è il Regolamento generale sulla protezione dei dati (GDPR) dell'Unione Europea. La mancata conformità alle normative sulla privacy dei dati può comportare sanzioni sostanziali.

Esempi di tipi di dati in Microsoft 365 includono sessioni di chat in Microsoft Teams, messaggi di posta elettronica in Exchange e file in SharePoint e OneDrive. Questa soluzione fornisce indicazioni su come valutare i rischi e identificare le informazioni, proteggere, governare e rispondere agli incidenti di privacy dei dati per i dati personali archiviati nei servizi di Microsoft 365 soggetti alle normative sulla privacy dei dati.

![Che cos'è la protezione delle informazioni per le normative sulla privacy dei dati](../media/information-protection-deploy/information-protection-data-privacy-regulations-overview.png)

Vengono inoltre fornite informazioni aggiuntive sull'uso dei controlli di identità, dispositivo e protezione dalle minacce di Microsoft 365 per le esigenze di privacy dei dati. 

Per soddisfare i criteri di protezione delle informazioni per la conformità alle normative sulla privacy dei dati, usare queste funzionalità e funzionalità di Microsoft 365.

| Capacità o funzionalità | Descrizione | Licenze |
|:-------|:-----|:-------|
| Compliance Manager | Gestire le attività di conformità alle normative, ottenere un punteggio complessivo della configurazione di conformità corrente e trovare suggerimenti per il miglioramento di questo strumento di valutazione dei rischi basato sul flusso di lavoro nel Centro conformità Microsoft 365. | Microsoft 365 E3 e E5 |
| Microsoft Defender per Office 365 | Proteggere le app e i dati di Microsoft 365, ad esempio i messaggi di posta elettronica, i documenti di Office e gli strumenti di collaborazione, da eventuali attacchi. | Microsoft 365 E3 e E5 | 
| Etichette di riservatezza | Classificare e proteggere i dati dell'organizzazione senza compromettere la produttività degli utenti e la loro capacità di collaborare aggiungendo etichette con vari livelli di protezione a messaggi di posta elettronica, file o siti. | Microsoft 365 E3 ed E5 |
| Prevenzione della perdita dei dati (DLP) | Rilevare, comunicare e bloccare la condivisione rischiosa, involontaria o inappropriata, come la condivisione di dati che contengono informazioni personali, sia all'interno che all'esterno. | Microsoft 365 E3 ed E5 | 
| Etichette e criteri di conservazione dei dati | Implementare controlli di governance delle informazioni, come la durata di conservazione dei dati e i requisiti per l'archiviazione dei dati personali dei clienti, per garantire la conformità con i criteri o le normative sui dati dell'organizzazione. | Microsoft 365 E3 ed E5 |
| Crittografia della posta elettronica | Inviare e ricevere messaggi di posta elettronica tra persone all'interno e all'esterno dell'organizzazione che contengono dati regolamentati, come i dati personali dei clienti. | Microsoft 365 E3 ed E5 |
||||

## <a name="organization-of-the-guidance-in-this-solution"></a>Organizzazione delle linee guida in questa soluzione

Per aiutarti a comprendere gli strumenti di Microsoft 365 disponibili per identificare, gestire, controllare e monitorare i dati personali soggetti a una o più normative relative alla privacy, questa guida è organizzata in sezioni.
 
![Passaggi per implementare la protezione delle informazioni per le normative sulla privacy dei dati](../media/information-protection-deploy/information-protection-data-privacy-regulations-steps.png)

Ognuna di queste sezioni corrisponde a un articolo separato in questa soluzione.

>[!Note]
>Se si ha già familiarità con gli obblighi di privacy dei dati ed è in esecuzione su un piano esistente, è possibile concentrarsi sulle indicazioni relative a prevenzione, protezione, conservazione e analisi.

>[!Important]
>Seguire queste indicazioni non ti rende necessariamente conforme alle normative sulla privacy dei dati, soprattutto considerando il numero di passaggi necessari che non sono nel contesto delle funzionalità. L'utente è responsabile di garantire la conformità e di consultare i team legali e di conformità o di richiedere indicazioni e consigli da terze parti che si specializzano nella conformità.
>

## <a name="plan-assess-data-privacy-risks-and-identify-sensitive-items"></a>Pianificare: valutare i rischi per la privacy dei dati e identificare gli elementi sensibili

La valutazione delle normative sulla privacy dei dati e dei rischi a cui l'organizzazione è soggetta è un primo passo fondamentale da intraprendere prima di iniziare a implementare miglioramenti, inclusi quelli raggiungibili tramite la configurazione di Microsoft 365. Ciò può includere una valutazione generale della conformità o l'identificazione di particolari tipi di informazioni sensibili soggetti ai controlli normativi che l'organizzazione deve rispettare, nonché il verificarsi di tali tipi nell'ambiente Microsoft 365.

Per ulteriori informazioni, vedere Valutare i rischi [per la privacy dei dati e identificare gli elementi sensibili.](information-protection-deploy-assess.md)

## <a name="track-run-risk-assessments-and-check-your-compliance-score"></a>Tenere traccia: eseguire valutazioni dei rischi e controllare il punteggio di conformità

Compliance Manager, disponibile nel Centro conformità Microsoft 365, offre una capacità integrata di tenere traccia e gestire le azioni di miglioramento nel complesso, nonché quelle relative a più normative sulla privacy dei dati che si applicano all'utente.

Sfrutta i modelli di valutazione predefiniti specifici per ogni regolamento, in cui puoi tenere traccia delle attività per ogni modello di valutazione selezionato, nonché visualizzare controlli normativi specifici e correlarli ad azioni specifiche.

Per ulteriori informazioni, vedere [Usare Compliance Manager per gestire le azioni di miglioramento.](information-protection-deploy-compliance.md)

## <a name="prevent-protect-personal-data"></a>Impedisci: proteggere i dati personali

Microsoft 365 offre una serie di funzionalità di protezione da identità, dispositivi e minacce che è possibile usare per garantire la conformità alle normative sulla privacy dei dati. 

Per ulteriori informazioni, vedere [Use identity, device, and threat protection for data privacy regulation.](information-protection-deploy-identity-device-threat.md)

Questo articolo descrive brevemente ciò che le normative sulla privacy dei dati in genere chiamano in queste aree e fornisce un elenco delle soluzioni di Microsoft 365 correlate, con collegamenti a ulteriori informazioni che consentono di soddisfare eventuali requisiti di implementazione. 

## <a name="protect-information-subject-to-data-privacy-regulation"></a>Proteggere le informazioni soggette alle normative sulla privacy dei dati

Le normative sulla privacy dei dati stabiliscino una serie di controlli sulla protezione delle informazioni personali che possono essere utilizzati nel tuo ambiente, inclusi più di 40 controlli di Protezione delle informazioni solo nelle quattro normative sulla privacy dei dati nel nostro set di esempi di GDPR, California Consumer Protection Act (CCPA), HIPAA-HITECH (United States health care privacy act) e brazil Data Protection Act (LGPD).

Per ulteriori informazioni, vedere Proteggere le informazioni soggette alla normativa sulla privacy dei [dati nell'organizzazione.](information-protection-deploy-protect-information.md)

In questo articolo vengono riportati i principali schemi di controllo che possono essere utilizzati per soddisfare le esigenze di protezione delle informazioni per la privacy dei dati nell'organizzazione.

## <a name="retain-govern-information-subject-to-data-privacy-regulation"></a>Conservare: gestire le informazioni soggette alle normative sulla privacy dei dati

Le normative sulla privacy dei dati sono necessarie per i controlli di governance delle informazioni personali che possono essere utilizzati nel proprio ambiente, inclusi più di ventiquattro controlli nelle quattro normative sulla privacy dei dati nel nostro set di campioni di GDPR, CCPA, HIPAA-HITECH e LGPD.

Per ulteriori informazioni, vedere [Governare le informazioni soggette alla normativa sulla privacy dei dati nell'organizzazione.](information-protection-deploy-govern.md)

Anche se le normative sulla privacy dei dati possono essere vaghe per quanto riguarda la governance delle informazioni, ad esempio la conservazione, l'eliminazione e l'archiviazione, questo articolo illustra i principali schemi di controllo che è possibile utilizzare per soddisfare le esigenze di governance delle informazioni per la privacy dei dati &mdash; &mdash; nell'organizzazione.

## <a name="investigate-monitor-investigate-and-respond-to-data-privacy-incidents"></a>Analizzare: monitorare, analizzare e rispondere agli incidenti di privacy dei dati

Sono disponibili funzionalità di Microsoft 365 che consentono di monitorare, analizzare e rispondere agli incidenti di privacy dei dati nell'organizzazione durante l'operatività delle funzionalità correlate. 

Disporre di processi, procedure e altra documentazione per ognuno di questi può essere importante per dimostrare la conformità agli organismi normativi.

Per ulteriori informazioni, vedere [Monitorare e rispondere agli incidenti di privacy dei dati nell'organizzazione.](information-protection-deploy-monitor-respond.md)
