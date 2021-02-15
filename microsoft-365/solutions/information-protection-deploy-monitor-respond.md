---
title: Monitorare e rispondere agli incidenti di privacy dei dati nell'organizzazione
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 01/04/2021
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
description: Utilizzare i criteri di controllo e di avviso e le richieste degli utenti per monitorare e rispondere agli incidenti relativi ai dati personali.
ms.openlocfilehash: 3ae0f2a6528f6188500c7cee7732c6447013eaa6
ms.sourcegitcommit: ae646779d84e993cf80b1207e76b856a21be5790
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/04/2021
ms.locfileid: "49749588"
---
# <a name="monitor-and-respond-to-data-privacy-incidents-in-your-organization"></a>Monitorare e rispondere agli incidenti di privacy dei dati nell'organizzazione

Le funzionalità di Microsoft 365 sono disponibili per monitorare, analizzare e rispondere agli incidenti di privacy dei dati nell'organizzazione durante l'operatività delle funzionalità correlate. Disporre di processi, procedure e altra documentazione per ognuno di essi può anche essere importante per dimostrare la conformità agli organismi normativi.

Ad esempio: 

- Criteri di controllo e avviso
- Richieste dell'oggetto dei dati (incluse la ricerca di contenuto e eDiscovery)
- Altri strumenti di indagine e creazione di report

## <a name="data-privacy-regulations-impacting-the-use-of-monitoring-and-response-tools"></a>Normative sulla privacy dei dati che influiscono sull'uso di strumenti di monitoraggio e risposta

Ecco un elenco di esempio delle normative sulla privacy dei dati che possono riguardare i controlli di governance delle informazioni:

- Articolo LGPD 46
- Articolo LGPD 48
- Articolo GDPR (5)(1)(f)
- Articolo GDPR (15)(1)(e)
- HIPAA-HITECH (45 C.F.R. 164.308(a)(1)(ii)(D))
- HIPAA-HITECH (45 C.F.R. 164.308(a)(6)(ii)
- HIPAA-HITECH (45 C.F.R. 164.312(b))
- CCPA (1798.105(c))

Per ulteriori informazioni, vedere Valutare i [rischi per la privacy dei dati e identificare le informazioni riservate.](information-protection-deploy-assess.md)

Le normative sulla privacy dei dati in genere prescindono quanto segue per il monitoraggio e la risposta:

- Auditing, alerting, and reporting for activities related to the storage, sharing and processing of personal data
- La capacità di rispondere a una richiesta dell'soggetto dei dati (DSR) e, in alcuni casi, di eseguire indagini e altre misure amministrative per conformarsi a tali richieste.

L'organizzazione può anche voler eseguire attività di monitoraggio e risposta per altri scopi, ad esempio per altre esigenze di conformità o per motivi aziendali. La definizione dello schema di monitoraggio e risposta per la privacy dei dati deve essere eseguita nell'ambito della pianificazione, dell'implementazione e della gestione generali del monitoraggio e della risposta.

Per iniziare a usare uno schema di monitoraggio e risposta in Microsoft 365 per le normative sulla privacy dei dati, in questo articolo sono elencate le funzionalità utili di Microsoft 365 per rispondere a domande come: 

- Che tipo di tecniche quotidiane di monitoraggio, indagine e creazione di report sono disponibili per i diversi tipi di dati e origini?
- Quali meccanismi saranno necessari per gestire le richieste degli utenti dei dati (DSR) e tutte le azioni correttive, ad esempio l'anonimizzazione, la redazione e l'eliminazione.

## <a name="auditing-and-alert-policies-in-the-security-and-compliance-center"></a>Criteri di controllo e avviso nel Centro sicurezza e conformità

Vedi questi articoli per configurare il controllo, il controllo avanzato e i criteri di avviso:

- [Controllo unificato](../compliance/search-the-audit-log-in-security-and-compliance.md)
- [Controllo delle cassette postali](../compliance/enable-mailbox-auditing.md)
- [Controllo avanzato](../compliance/advanced-audit.md)
- [Criteri di avviso](../compliance/alert-policies.md)

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a>Richieste degli soggetti dei dati per GDPR e CCPA

Per informazioni su come rispondere a una richiesta DSR in Microsoft 365, vedere Le richieste dell'soggetto dei dati per il GDPR e [il CCPA.](../compliance/gdpr-dsr-office365.md)

## <a name="manage-deleted-users-in-microsoft-stream"></a>Gestire gli utenti eliminati in Microsoft Stream

Per Microsoft Stream, quando un utente viene eliminato da Azure Active Directory (Azure AD), se il nome è stato associato a un video di Stream pubblicato prima di quel punto, l'indirizzo di posta elettronica rimane associato al video. Vedi [Gestire gli utenti eliminati da Microsoft Stream](https://docs.microsoft.com/stream/managing-deleted-users) per rimuoverlo.

## <a name="insider-risk-management-as-an-investigative-tool"></a>Gestione dei rischi Insider come strumento di indagine

La gestione dei rischi Insider [in Microsoft 365](../compliance/insider-risk-management.md) è una funzionalità dell'interfaccia di amministrazione di Conformità Microsoft che consente di ridurre al minimo i rischi interni consentendo di rilevare, analizzare e intraprendere azioni su attività rischiose nell'organizzazione.
