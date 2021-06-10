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
- m365solution-scenario
ms.custom: ''
description: Utilizzare Microsoft 365 etichette e criteri di conservazione per gestire i dati personali nell'Microsoft 365 locale.
ms.openlocfilehash: 62c2386ac8f9c5b31650df8be2c2a411d8b75959
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928437"
---
# <a name="govern-information-subject-to-data-privacy-regulation"></a>Disciplinare le informazioni soggette alla normativa sulla privacy dei dati

I controlli di governance delle informazioni possono essere utilizzati nel proprio ambiente per soddisfare le esigenze di conformità alla privacy dei dati, tra cui un numero specifico del Regolamento generale sulla protezione dei dati (GDPR), HIPAA-HITECH (legge sulla privacy dell'assistenza sanitaria degli Stati Uniti), californiano Consumer Protection Act (CCPA) e il Brazil Data Protection Act (LGPD). 

Questi controlli rientrano principalmente nelle aree della soluzione seguenti:

- Criteri di conservazione
- Etichette di conservazione
- Gestione dei record

## <a name="data-privacy-regulations-impacting-information-governance-controls"></a>Normative sulla privacy dei dati che influiscono sui controlli di governance delle informazioni

Ecco un elenco di esempio delle normative sulla privacy dei dati che possono riguardare i controlli di governance delle informazioni:

- Articolo GDPR (13)(2)(a)
- Articolo GDPR (5)(1)(f)
- HIPAA-HITECH (45 CFR 164.312(c)(2))
- HIPAA-HITECH (45 CFR 164.316(b)(1)(i))
- HIPAA-HITECH (45 CFR 164.316(b)(1)(ii))
- Articolo LGPD 46

Per ulteriori informazioni su queste normative, vedere l'articolo valutare i rischi per la privacy dei [dati e identificare le informazioni riservate.](information-protection-deploy-assess.md)

Per la governance delle informazioni, le normative sulla privacy dei dati in genere richiedono quanto segue:

- È consigliabile utilizzare uno schema tecnico per la conservazione e l'eliminazione dei dati personali archiviati in Microsoft 365.
- Se si desidera archiviare i dati personali, informare l'oggetto della durata dell'archiviazione dei dati, una procedura standard ora disponibile nei sistemi Web front-end.
- I dati personali devono essere protetti da trattamento, perdita o alterazione accidentali utilizzando metodi verificabili.
- Qualsiasi azione eseguita sui dati personali deve essere documentata e tale documentazione deve essere conservata per un periodo specificato.

Poiché le normative sulla privacy dei dati non sono molto specifiche per quanto riguarda la conservazione e l'eliminazione dei dati, è necessario prendere in considerazione altri fattori che potrebbero dettare linee guida sulla governance delle informazioni per le informazioni personali archiviate nella sottoscrizione Microsoft 365. Ecco alcuni esempi:

- Eliminare gli account utente dopo 5 anni di inattività e richiede l'eliminazione o l'anonimizzazione dei dati dell'account dopo tale punto, richiedendo l'orchestrazione tra il sistema che archivia i dati e i flussi di lavoro correlati alle notifiche e ad altre attività di automazione.
- Configurazione delle regole per mantenere i criteri e le procedure correlati al GDPR per tre anni dopo che sono state sostituite, in linea con la pianificazione di conservazione dell'organizzazione per i criteri e le procedure.
- Mantenere una sottoscrizione separata per comunicare con gli utenti tramite l'organizzazione di supporto. Tutte le comunicazioni di posta elettronica sono state conservate ed eliminate dopo due settimane per ridurre l'eventuale accumulo di debiti per la privacy nel sistema.

Una domanda chiave a cui rispondere è: 

- Per quanto tempo le informazioni contenenti dati personali devono essere conservate per motivi aziendali validi per evitare pratiche di "conservarlo per sempre"? Questo deve essere bilanciato con le esigenze di conservazione per la continuità aziendale.

Indipendentemente dalle ragioni legali e aziendali per la conservazione o l'eliminazione delle informazioni personali, Microsoft offre diverse funzionalità per implementare lo schema di governance dei dati in Microsoft 365.

## <a name="managing-information-governance-in-microsoft-365"></a>Gestione della governance delle informazioni in Microsoft 365

Per iniziare, vedere [Manage information governance](../compliance/manage-information-governance.md) and Data [Retention, Deletion and Destruction in Microsoft 365](/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).

### <a name="develop-data-retention-schedules-for-containers-email-and-content"></a>Sviluppare pianificazioni di conservazione dei dati per contenitori, posta elettronica e contenuto

Tenere presente quanto segue:

- La definizione di una pianificazione di conservazione dei dati per i tipi di informazioni definiti deve essere considerata un prerequisito per l'implementazione di qualsiasi schema di conservazione o eliminazione.

- Dato il numero di tipi di informazioni che la maggior parte delle organizzazioni considera importanti e le pianificazioni di conservazione dei record di grandi dimensioni corrispondenti, l'implementazione di una strategia di conservazione dei dati e gestione dei record richiede la pianificazione. 

- La chiave per stabilire una strategia di governance dei dati efficace di questo tipo è concentrarsi sulle funzioni aziendali e sui tipi di informazioni con priorità più alta che richiedono una gestione più formale. Alcuni esempi sono i contratti legali, i rendiconti finanziari e la documentazione relativa alla conformità normativa. Evitare di avere una pianificazione di conservazione separata per ogni singolo tipo di informazioni. Provare a utilizzare il più possibile le categorie generali, ad esempio con pianificazioni di conservazione di 7 anni per i contenuti aziendali generali.

- Una volta che i tipi di informazioni personali nell'ambiente sono più noti, stabilire pianificazioni di conservazione ed eliminazione per questo tipo di contenuto e modificare l'architettura delle informazioni per semplificare la governance di questo tipo di informazioni. Ad esempio, isolare le informazioni personali in siti, raccolte o cartelle separati con accesso controllato.

### <a name="retention-policies-and-retention-labels"></a>Criteri di conservazione ed etichette di conservazione.

Utilizzare [i criteri di conservazione e le etichette](../compliance/retention.md) di conservazione per conservare o eliminare contenuto in Microsoft 365 che contiene o dovrebbe contenere dati personali.

### <a name="records-management"></a>Gestione dei record

Utilizzare le etichette di conservazione che dichiarano il contenuto di un record per implementare una soluzione di gestione [dei record](../compliance/records-management.md) per i dati in Microsoft 365.

Per la privacy dei dati, le richieste dell'oggetto dei dati (DSR) ricevute dall'ufficio legale sono dichiarate un record e possono essere archiviate a tempo indeterminato o smaltite con la prova, per rispettare le specifiche di conservazione delle attività normative.