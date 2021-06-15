---
title: Microsoft Managed Desktop e ITIL
description: Correla le fasi ITIL con Microsoft Managed Desktop informazioni e articoli
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione, ITISM
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.localizationpriority: normal
ms.openlocfilehash: f51c99ed39e9f647f3e069c22eb3e37441f57be5
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924480"
---
# <a name="microsoft-managed-desktop-and-itil"></a>Microsoft Managed Desktop e ITIL

Molte organizzazioni trovano utile strutturare i propri servizi IT in base a un modello di servizio IT formalizzato (ITSM), ad esempio [ITIL.](https://www.axelos.com/best-practice-solutions/itil) 

Microsoft Managed Desktop consente all'organizzazione di conformarsi a molti aspetti chiave di tali modelli ITSM formalizzati. Utilizzando ITIL come esempio, questo articolo consente di visualizzare le connessioni tra le fasi e i processi ITIL comuni e le funzionalità Microsoft Managed Desktop equivalenti, ove applicabile. Queste informazioni si applicano solo alla Microsoft Managed Desktop dell'organizzazione.

Per informazioni più complete su ITIL e sulle relative fasi e processi, vedere la [relativa documentazione.](https://www.axelos.com/best-practice-solutions/itil)


## <a name="service-design"></a>Progettazione dei servizi

Questa tabella mette in relazione le fasi e i processi ITIL chiave Microsoft Managed Desktop funzionalità, con collegamenti alla documentazione per informazioni dettagliate:



|Processo ITIL |Descrizione  |Documentazione |
|---------|---------|---------|
|Gestione a livello di servizio     | I tempi di risposta sono definiti per le richieste di supporto dell'amministratore e gli eventi imprevisti.  |  [Supporto amministratore per Microsoft Managed Desktop](working-with-managed-desktop/admin-support.md)  |
|Gestione del catalogo dei servizi     | La descrizione del servizio che dettaglia i componenti del servizio viene mantenuta fedele allo stato del servizio, disponibile per tutti i clienti correnti e interessati.<br><br>Prerequisiti dettagliati per comprendere cosa è necessario per il funzionamento del servizio.  | - [Microsoft Managed Desktop servizio](service-description/index.md)<br><br>- [Prepararsi per la registrazione in Microsoft Managed Desktop](get-ready/index.md)  |
|Gestione della sicurezza delle informazioni     | Informazioni di sicurezza, inclusa la sicurezza delle informazioni per il servizio.<br><br> Criteri correlati alla sicurezza e altre informazioni sulla configurazione dei dispositivi.   | - [Sicurezza in Microsoft Managed Desktop](service-description/security.md)<br><br>- [Configurazione del dispositivo](service-description/device-policies.md)  |
|Gestione della disponibilità     |  Microsoft Managed Desktop bilancia la responsabilità con l'organizzazione per garantire la disponibilità del servizio.<br><br>Gli amministratori e gli utenti hanno route al rispettivo supporto in caso di problemi di servizio o disponibilità. | - [Microsoft Managed Desktop operazioni e monitoraggio](service-description/operations-and-monitoring.md)<br><br>- [Supporto dell'amministratore per Microsoft Managed Desktop](working-with-managed-desktop/admin-support.md)<br>- [Ottenere assistenza per gli utenti](working-with-managed-desktop/end-user-support.md)  |



## <a name="service-transition"></a>Transizione del servizio


|Processo ITIL |Descrizione  |Documentazione |
|---------|---------|---------|
|Gestione delle modifiche     | Equilibrio di responsabilità definito, panoramica del processo e tipi correlati alla gestione delle modifiche disponibili.  | [Microsoft Managed Desktop operazioni e monitoraggio](service-description/operations-and-monitoring.md#change-management) |
|Gestione delle versioni e della distribuzione     |  Microsoft Managed Desktop gestisce gli aggiornamenti per i dispositivi registrati nel servizio.  | [Modalità di gestione degli aggiornamenti in Microsoft Managed Desktop](service-description/updates.md)        |
|Gestione delle risorse di servizio e della configurazione     | Le informazioni relative alla distribuzione Microsoft Managed Desktop dell'organizzazione sono disponibili nel portale di amministrazione IT.  | [Supporto amministratore per Microsoft Managed Desktop](working-with-managed-desktop/admin-support.md) |
|Gestione delle conoscenze     | Le informazioni sul Microsoft Managed Desktop vengono mantenute aggiornate in questo sito.   | [Cronologia modifiche per la documentazione di Microsoft Managed Desktop](change-history-managed-desktop.md)        |



## <a name="service-operation"></a>Operazione del servizio


|Processo ITIL |Descrizione  |Documentazione  |
|---------|---------|---------|
|Gestione eventi     |  Vengono forniti dettagli sul monitoraggio dei dispositivi.<br><br>Le procedure operative standard per il Microsoft Managed Desktop sono dettagliate. |  - [Sicurezza in Microsoft Managed Desktop](service-description/security.md)<br>- [Microsoft Managed Desktop operazioni e monitoraggio](service-description/operations-and-monitoring.md)       |
|Gestione degli incidenti  | Microsoft Managed Desktop analizza e agisce sugli eventi imprevisti in base alle definizioni di gravità definite.  |  [Definizioni di gravità delle richieste di supporto](working-with-managed-desktop/admin-support.md#support-request-severity-definitions)       |
|Gestione dell'evasione delle richieste     |  Vengono definiti il processo per le richieste di informazioni e le richieste di modifica Microsoft Managed Desktop servizio.         |[Supporto amministratore per Microsoft Managed Desktop](working-with-managed-desktop/admin-support.md)         |
|Gestione dei problemi     | Eventuali problemi relativi al servizio devono essere indirizzati al team dell'account locale in questo momento. | Documentazione in fase di sviluppo |
|Gestione degli accessi     | Accedere ai componenti e alle responsabilità di gestione per i clienti per garantire che le funzionalità siano dettagliate.  | [Gestione di identità e accesso](service-description/security.md#identity-and-access-management)        |
