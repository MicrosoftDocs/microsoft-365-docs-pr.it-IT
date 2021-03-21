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
description: Usa i criteri di controllo e di avviso e le richieste dell'oggetto dei dati per monitorare e rispondere a eventi imprevisti relativi ai dati personali.
ms.openlocfilehash: 4070cd772d243bcfba33bfb164fd05e1f0911b3b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928425"
---
# <a name="monitor-and-respond-to-data-privacy-incidents-in-your-organization"></a>Monitorare e rispondere agli incidenti di privacy dei dati nell'organizzazione

Le funzionalità di Microsoft 365 sono disponibili per monitorare, analizzare e rispondere agli incidenti relativi alla privacy dei dati nell'organizzazione durante l'operatività delle funzionalità correlate. La presenza di processi, procedure e altra documentazione per ognuno di questi elementi può essere importante anche per dimostrare la conformità agli organismi normativi.

Ad esempio: 

- Criteri di controllo e avviso
- Richieste dell'oggetto dei dati (tra cui ricerca contenuto ed eDiscovery)
- Strumenti di indagine e report aggiuntivi

## <a name="data-privacy-regulations-impacting-the-use-of-monitoring-and-response-tools"></a>Normative sulla privacy dei dati che influiscono sull'uso di strumenti di monitoraggio e risposta

Ecco un elenco di esempio delle normative sulla privacy dei dati che possono riguardare i controlli di governance delle informazioni:

- Articolo LGPD 46
- LGPD Articolo 48
- Articolo GDPR (5)(1)(f)
- Articolo GDPR (15)(1)(e)
- HIPAA-HITECH (45 C.F.R. 164.308(a)(1)(ii)(D))
- HIPAA-HITECH (45 C.F.R. 164.308(a)(6)(ii)
- HIPAA-HITECH (45 C.F.R. 164.312(b))
- CCPA (1798.105(c))

Per ulteriori informazioni, vedere [Valutare i rischi per la privacy dei dati e identificare le informazioni riservate.](information-protection-deploy-assess.md)

Le normative sulla privacy dei dati in genere prescindono quanto segue per il monitoraggio e la risposta:

- Controllo, avviso e creazione di report per le attività relative all'archiviazione, alla condivisione e all'elaborazione dei dati personali
- La possibilità di rispondere a una richiesta dell'oggetto dei dati (DSR) e, in alcuni casi, eseguire misure di indagine e altre misure amministrative per conformarsi a tali richieste.

L'organizzazione può anche desiderare di eseguire attività di monitoraggio e risposta per altri scopi, ad esempio per altre esigenze di conformità o per motivi aziendali. La definizione dello schema di monitoraggio e risposta per la privacy dei dati deve essere eseguita nell'ambito del monitoraggio generale e della pianificazione, implementazione e gestione delle risposte.

Per iniziare a usare uno schema di monitoraggio e risposta in Microsoft 365 per le normative sulla privacy dei dati, in questo articolo sono elencate le funzionalità utili in Microsoft 365 per rispondere a domande quali: 

- Che tipo di tecniche quotidiane di monitoraggio, indagine e segnalazione sono disponibili per i diversi tipi di dati e origini?
- Quali meccanismi saranno necessari per gestire le richieste dell'oggetto dei dati (DSR) ed eventuali azioni correttive, ad esempio l'anonimizzazione, la redazione e l'eliminazione.

## <a name="auditing-and-alert-policies-in-the-security-and-compliance-center"></a>Criteri di controllo e avviso nel Centro sicurezza e conformità

Vedere questi articoli per configurare il controllo, il controllo avanzato e i criteri di avviso:

- [Controllo unificato](../compliance/search-the-audit-log-in-security-and-compliance.md)
- [Controllo delle cassette postali](../compliance/enable-mailbox-auditing.md)
- [Controllo avanzato](../compliance/advanced-audit.md)
- [Criteri di avviso](../compliance/alert-policies.md)

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a>Richieste degli soggetti dei dati per il GDPR e il CCPA

Per informazioni su come rispondere a una richiesta DSR in Microsoft 365, vedere Richieste dell'soggetto dei dati per il GDPR e [il CCPA.](/compliance/regulatory/gdpr-dsr-Office365)

## <a name="manage-deleted-users-in-microsoft-stream"></a>Gestire gli utenti eliminati in Microsoft Stream

Per Microsoft Stream, quando un utente viene eliminato da Azure Active Directory (Azure AD), se il nome è stato associato a un video stream pubblicato prima di tale punto, l'indirizzo di posta elettronica rimane associato al video. Vedi [Gestire gli utenti eliminati da Microsoft Stream](/stream/managing-deleted-users) per rimuoverlo.

## <a name="insider-risk-management-as-an-investigative-tool"></a>Gestione dei rischi insider come strumento di indagine

La gestione dei rischi insider [in Microsoft 365](../compliance/insider-risk-management.md) è una funzionalità dell'interfaccia di amministrazione di Microsoft Compliance che consente di ridurre al minimo i rischi interni consentendo di rilevare, analizzare e intraprendere azioni in caso di attività rischiose nell'organizzazione.