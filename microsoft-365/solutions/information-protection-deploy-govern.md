---
title: Disciplinare le informazioni soggette alla normativa sulla privacy dei dati
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
ms.custom: ''
description: Utilizzare le etichette e i criteri di conservazione di Microsoft 365 per gestire i dati personali nell'ambiente Microsoft 365.
ms.openlocfilehash: 766995b9c758d4ae8cbf7140fb259d208cfb7771
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2020
ms.locfileid: "47949253"
---
# <a name="govern-information-subject-to-data-privacy-regulation"></a>Disciplinare le informazioni soggette alla normativa sulla privacy dei dati

I controlli di governance delle informazioni possono essere utilizzati nel proprio ambiente per aiutare a soddisfare le esigenze di conformità alla privacy dei dati, tra cui un numero specifico per il regolamento generale sulla protezione dei dati (GDPR), HIPAA-HITECH (United States Health Care Privacy Act), California Consumer Protection Act (CCPA) e the Brazil Data Protection Act (LGPD). 

Questi controlli rientrano principalmente nelle aree di soluzione seguenti:

- Criteri di conservazione
- Etichette di conservazione
- Gestione dei record

## <a name="data-privacy-regulations-impacting-information-governance-controls"></a>Normative sulla privacy dei dati che influiscono sui controlli di governance

Ecco un elenco di esempi di regolamenti sulla privacy dei dati che possono riguardare i controlli di governance delle informazioni:

- Articolo GDPR (13) (2) (a)
- Articolo di GDPR (5) (1) (f)
- HIPAA-HITECH (45 CFR 164.312 (c) (2))
- HIPAA-HITECH (45 CFR 164.316 (b) (1) (i))
- HIPAA-HITECH (45 CFR 164.316 (b) (1) (II))
- LGPD articolo 46

Per ulteriori informazioni su queste normative, vedere l' [articolo valutare i rischi per la privacy dei dati e identificare le informazioni riservate](information-protection-deploy-assess.md).

Per la governance delle informazioni, le normative sulla privacy dei dati in genere richiedono quanto segue:

- È consigliabile utilizzare un sistema tecnico per la conservazione e l'eliminazione dei dati personali archiviati in Microsoft 365.
- Se si desidera archiviare i dati personali, informare l'oggetto del periodo di archiviazione dei dati, che è una prassi standard ora disponibile nei sistemi Web front-end.
- I dati personali devono essere protetti dall'elaborazione, dalla perdita o dall'alterazione accidentale mediante metodi verificabili.
- Tutte le azioni eseguite nei confronti dei dati personali devono essere documentate e la documentazione deve essere conservata per un periodo specificato.

Poiché le normative sulla privacy dei dati non sono molto specifiche per quanto riguarda la conservazione e l'eliminazione dei dati, è necessario tenere in considerazione altri fattori che possono imporre linee guida per la governance delle informazioni per le informazioni personali archiviate nell'abbonamento a Microsoft 365. Di seguito sono riportati alcuni esempi:

- Invecchiamento degli account consumer dopo 5 anni di inattività e richiede l'eliminazione o la Anonymization dei dati degli account dopo quel momento, richiedendo l'orchestrazione tra il sistema che archivia i dati e i flussi di lavoro relativi alle notifiche e ad altre automazioni.
- Configuring rules for keeping Policy and Procedures related to GDPR around per tre anni dopo che sono stati sostituiti, che si allinea con la pianificazione di conservazione dell'organizzazione per i criteri e le procedure.
- Gestione di una sottoscrizione separata per la comunicazione con i consumatori tramite l'organizzazione di supporto. Tutte le comunicazioni di posta elettronica sono state conservate ed eliminate dopo due settimane per ridurre la formazione di debiti sulla privacy nel sistema.

Una domanda fondamentale per rispondere è: 

- In che modo le informazioni contenenti i dati personali devono essere mantenute in giro per motivi aziendali validi per evitare che le procedure vengano "conservate per sempre"? Questo deve essere bilanciato con le esigenze di conservazione per la continuità aziendale.

Indipendentemente dai motivi legali e aziendali per mantenere le informazioni personali intorno o eliminarlo, Microsoft fornisce una serie di funzionalità per implementare lo schema di governance dei dati in Microsoft 365.

## <a name="managing-information-governance-in-microsoft-365"></a>Gestione della governance delle informazioni in Microsoft 365

Per iniziare, vedere [Manage information governance](../compliance/manage-information-governance.md) and [data retention, Deletion and Destruction in Microsoft 365](https://docs.microsoft.com/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).

### <a name="develop-data-retention-schedules-for-containers-email-and-content"></a>Sviluppare pianificazioni di conservazione dei dati per contenitori, messaggi di posta elettronica e contenuto

Tenere presente quanto segue:

- La creazione di una pianificazione di conservazione dei dati per i tipi di informazioni definite deve essere considerata un prerequisito per l'implementazione di qualsiasi schema di conservazione o eliminazione.

- Dato il numero di tipi di informazioni che la maggior parte delle organizzazioni considera importanti e le corrispondenti pianificazioni di conservazione dei record di grandi dimensioni che vengono configurate con essi, l'implementazione di una strategia di conservazione e gestione di record richiede la pianificazione 

- La chiave per la definizione di una strategia di governance dei dati efficace di questo tipo è quella di concentrarsi sulle funzioni aziendali e sui tipi di informazioni con priorità più alta che richiedono una gestione più formale. Esempi sono i contratti legali, i rendiconti finanziari e la documentazione relativa alla conformità alle normative. Provare a evitare di disporre di una pianificazione di conservazione separata per ogni singolo tipo di informazioni. Provare a utilizzare le categorie generali il più possibile, ad esempio, con le pianificazioni di conservazione di 7 anni per il contenuto aziendale generale.

- Una volta che i tipi di informazioni personali nel proprio ambiente sono più noti, stabilire le pianificazioni di conservazione ed eliminazione per questo tipo di contenuto e modificare l'architettura delle informazioni per semplificare la governance di questo tipo di informazioni. Ad esempio, isolare le informazioni personali in siti, raccolte o cartelle separate con accesso controllato.

### <a name="retention-policies-and-retention-labels"></a>Criteri di conservazione ed etichette di conservazione.

Utilizzare i [criteri di conservazione e le etichette di conservazione](../compliance/retention.md) per mantenere o eliminare il contenuto in Microsoft 365 che contiene o dovrebbe contenere dati personali.

### <a name="records-management"></a>Gestione dei record

Utilizzare le etichette di conservazione che dichiarano il contenuto un record per implementare una [soluzione di gestione dei record](../compliance/records-management.md) per i dati in Microsoft 365.

Per la privacy dei dati, le richieste del soggetto dei dati (richieste DSR) ricevute dal reparto legale vengono dichiarate come record e possono essere archiviate indefinitamente o eliminate con la prova, per conformarsi alle specifiche di conservazione delle attività normative.

