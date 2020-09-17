---
title: Microsoft Managed Desktop e ITIL
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, Service, Documentation, ITISM
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.openlocfilehash: 4b735ec28b655dfc01c874bc4865388d11247b67
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2020
ms.locfileid: "47947961"
---
# <a name="microsoft-managed-desktop-and-itil"></a>Microsoft Managed Desktop e ITIL

Molte organizzazioni trovano utili per strutturare i propri servizi IT seguendo le linee di un modello di servizio IT formalizzato (ITSM), ad esempio [ITIL](https://www.axelos.com/best-practice-solutions/itil). 

Microsoft Managed Desktop consente all'organizzazione di rispettare numerosi aspetti chiave di tali modelli di ITSM formalizzati. Se si utilizza ITIL come esempio, questo argomento consente di visualizzare le connessioni tra le fasi e i processi ITIL comuni e le caratteristiche equivalenti del desktop Microsoft gestite, se applicabile. Questo si applica solo alla parte Microsoft Managed Desktop dell'organizzazione.

Per informazioni più dettagliate su ITIL e sulle relative fasi e processo, vedere la [documentazione](https://www.axelos.com/best-practice-solutions/itil).


## <a name="service-design"></a>Progettazione del servizio

In questa tabella sono riferite le fasi e i processi ITIL principali alle funzionalità di Microsoft Managed Desktop, con collegamenti alla documentazione per i dettagli:



|Processo ITIL |Descrizione  |Documentazione |
|---------|---------|---------|
|Gestione a livello di servizio     | I tempi di risposta vengono definiti per le richieste di supporto dell'amministratore e gli incidenti.  |  [Supporto amministratori per Microsoft Managed Desktop](working-with-managed-desktop/admin-support.md)  |
|Gestione del catalogo dei servizi     | Descrizione del servizio i componenti del servizio vengono mantenuti converiti allo stato del servizio, disponibili a tutti i clienti attuali e interessati.<br><br>Requisiti preliminari dettagliati per comprendere cosa è necessario per gestire il servizio.  | - [Descrizione del servizio Microsoft Managed Desktop](service-description/index.md)<br><br>- [Prepararsi per la registrazione in Microsoft Managed Desktop](get-ready/index.md)  |
|Gestione della sicurezza delle informazioni     | Informazioni sulla sicurezza, inclusa la sicurezza delle informazioni per il servizio.<br><br> Criteri relativi alla sicurezza e altre informazioni su come vengono configurati i dispositivi.   | - [Sicurezza in Microsoft Managed Desktop](service-description/security.md)<br><br>- [Configurazione dispositivo](service-description/device-policies.md)  |
|Gestione della disponibilità     |  Microsoft Managed Desktop bilancia la responsabilità dell'organizzazione per garantire la disponibilità del servizio.<br><br>Gli amministratori e gli utenti dispongono di route per il supporto relativo in caso di problemi relativi al servizio o alla disponibilità. | - [Monitoraggio e operazioni di Microsoft Managed Desktop](service-description/operations-and-monitoring.md)<br><br>- [Supporto di amministrazione per Microsoft Managed Desktop](working-with-managed-desktop/admin-support.md)<br>- [Ottenere assistenza per gli utenti](working-with-managed-desktop/end-user-support.md)  |



## <a name="service-transition"></a>Transizione del servizio


|Processo ITIL |Descrizione  |Documentazione |
|---------|---------|---------|
|Gestione delle modifiche     | Sono stati definiti il bilanciamento della responsabilità, la panoramica dei processi e i tipi relativi alla gestione delle modifiche disponibili.  | [Monitoraggio e operazioni di Microsoft Managed Desktop](service-description/operations-and-monitoring.md#change-management) |
|Gestione dei rilasci e delle distribuzioni     |  Microsoft Managed Desktop gestisce gli aggiornamenti per i dispositivi registrati nel servizio.  | [Come vengono gestiti gli aggiornamenti in Microsoft Managed Desktop](service-description/updates.md)        |
|Gestione delle risorse e della configurazione del servizio     | Le informazioni relative alla distribuzione di Microsoft Managed Desktop dell'organizzazione sono disponibili nel portale di amministrazione IT.  | [Supporto amministratori per Microsoft Managed Desktop](working-with-managed-desktop/admin-support.md) |
|Gestione delle informazioni     | Le informazioni sul servizio Microsoft Managed Desktop vengono mantenute aggiornate su questo sito.   | [Cronologia modifiche per la documentazione di Microsoft Managed Desktop](change-history-managed-desktop.md)        |



## <a name="service-operation"></a>Operazione del servizio


|Processo ITIL |Descrizione  |Documentazione  |
|---------|---------|---------|
|Gestione eventi     |  Sono disponibili informazioni dettagliate sul monitoraggio dei dispositivi.<br><br>Le procedure operative standard per il servizio Microsoft Managed Desktop sono dettagliate. |  - [Sicurezza in Microsoft Managed Desktop](service-description/security.md)<br>- [Monitoraggio e operazioni di Microsoft Managed Desktop](service-description/operations-and-monitoring.md)       |
|Gestione degli incidenti  | Microsoft Managed Desktop analizzerà e agirà su incidenti per definizioni di gravità definite.  |  [Definizioni di Severity richieste di supporto](working-with-managed-desktop/admin-support.md#support-request-severity-definitions)       |
|Gestione delle richieste di evasione     |  Vengono definiti i processi per le richieste di informazioni e le richieste di modifica relative al servizio Microsoft Managed Desktop.         |[Supporto amministratori per Microsoft Managed Desktop](working-with-managed-desktop/admin-support.md)         |
|Gestione dei problemi     | Qualsiasi problema con il servizio deve essere indirizzato al team dell'account locale in questo momento. | Documentazione in sviluppo |
|Gestione degli accessi     | I componenti di gestione accessi e le responsabilità del cliente per garantire la funzionalità sono dettagliate.  | [Gestione di identità e accesso](service-description/security.md#identity-and-access-management)        |
