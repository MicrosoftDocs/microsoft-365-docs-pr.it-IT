---
title: Monitorare e rispondere agli incidenti sulla privacy dei dati nell'organizzazione
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
description: Utilizzare i criteri di controllo e di avviso e le richieste del soggetto dei dati per monitorare e rispondere agli incidenti dei dati personali.
ms.openlocfilehash: 296220ac8b34d9ce10c783194b78ca344e746b84
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377200"
---
# <a name="monitor-and-respond-to-data-privacy-incidents-in-your-organization"></a>Monitorare e rispondere agli incidenti sulla privacy dei dati nell'organizzazione

Sono disponibili funzionalità di Microsoft 365 che consentono di monitorare, indagare e rispondere agli incidenti sulla privacy dei dati nell'organizzazione durante la operazionalizzare delle funzionalità correlate. L'utilizzo di processi, procedure e altre documentazioni per ognuna di queste operazioni può anche essere importante per dimostrare la conformità agli organismi di regolamentazione.

Ad esempio: 

- Criteri di controllo e avviso
- Richieste del soggetto dei dati (inclusa la ricerca di contenuto e eDiscovery)
- Ulteriori strumenti e report di analisi

## <a name="data-privacy-regulations-impacting-the-use-of-monitoring-and-response-tools"></a>Normative sulla privacy dei dati che influiscono sull'utilizzo degli strumenti di monitoraggio e risposta

Ecco un elenco di esempi di regolamenti sulla privacy dei dati che possono riguardare i controlli di governance delle informazioni:

- LGPD articolo 46
- LGPD articolo 48
- Articolo di GDPR (5) (1) (f)
- Articolo di GDPR (15) (1) (e)
- HIPAA-HITECH (45 C.F.R. 164.308 (a) (1) (II) (D))
- HIPAA-HITECH (45 C.F.R. 164.308(a)(6)(ii)
- HIPAA-HITECH (45 C.F.R. 164.312 (b))
- CCPA (1798.105 (c))

Per ulteriori informazioni, vedere [valutare i rischi per la privacy dei dati e identificare informazioni riservate](information-protection-deploy-assess.md).

Le normative sulla privacy dei dati richiedono generalmente le seguenti operazioni per il monitoraggio e la risposta:

- Controllo, avviso e Reporting per attività relative all'archiviazione, alla condivisione e all'elaborazione dei dati personali
- La capacità di rispondere a una richiesta del soggetto dei dati (DSR) e, in alcuni casi, di eseguire indagini e altre misure amministrative per conformarsi a tali richieste.

L'organizzazione può anche eseguire attività di monitoraggio e risposta per altri scopi, ad esempio altre esigenze di conformità o per motivi aziendali. La definizione del sistema di monitoraggio e di risposta per la privacy dei dati deve essere svolta come parte del monitoraggio e della pianificazione di risposta, implementazione e gestione generali.

Per iniziare a utilizzare uno schema di monitoraggio e risposta in Microsoft 365 per le normative sulla privacy dei dati, in questo articolo sono elencate le funzionalità utili di Microsoft 365 per rispondere a domande quali: 

- Che tipo di monitoraggio giornaliero, di analisi e di creazione di report sono disponibili per i diversi tipi di dati e le origini?
- Quali sono i meccanismi necessari per gestire le richieste degli interessati (richieste DSR) e le azioni correttive, ad esempio Anonymization, redazione ed eliminazione.

## <a name="auditing-and-alert-policies-in-the-security-and-compliance-center"></a>Criteri di controllo e di avviso nel centro sicurezza e conformità

Vedere questi articoli per la configurazione del controllo, del controllo avanzato e dei criteri di avviso:

- [Controllo unificato](../compliance/search-the-audit-log-in-security-and-compliance.md)
- [Controllo delle cassette postali](../compliance/enable-mailbox-auditing.md)
- [Controllo avanzato](../compliance/advanced-audit.md)
- [Criteri di avviso](../compliance/alert-policies.md)

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a>Richieste del soggetto dei dati per GDPR e CCPA

Per informazioni su come rispondere a un DSR in Microsoft 365, vedere [richieste degli interessati per GDPR e CCPA](../compliance/gdpr-dsr-office365.md) .

## <a name="manage-deleted-users-in-microsoft-stream"></a>Gestire gli utenti eliminati in Microsoft Stream

Per Microsoft Stream, quando un utente viene eliminato da Azure Active Directory (Azure AD), se il relativo nome è stato associato a un video del flusso postato prima di quel momento, l'indirizzo di posta elettronica rimane associato al video. Per rimuoverlo, vedere [gestire gli utenti eliminati da Microsoft Stream](https://docs.microsoft.com/stream/managing-deleted-users) .

## <a name="additional-investigative-tools"></a>Strumenti di analisi aggiuntivi

Di seguito sono disponibili due strumenti aggiuntivi che possono essere utili per il monitoraggio, l'analisi e la correzione degli incidenti relativi alla privacy dei dati nell'organizzazione:

- [Gestione dei rischi insider in microsoft 365](../compliance/insider-risk-management.md), una funzionalità dell'interfaccia di amministrazione di conformità Microsoft per ridurre al minimo i rischi interni, consentendo di rilevare, indagare ed eseguire azioni sulle attività a rischio nell'organizzazione.
- [Indagini sui dati in microsoft 365](../compliance/overview-data-investigations.md), una funzionalità dell'interfaccia di amministrazione di conformità di Microsoft per la ricerca di dati sensibili, dannosi o fuori luogo in Microsoft 365, quindi esaminare cosa è successo per eseguire le azioni appropriate per correggere l'incidente.
