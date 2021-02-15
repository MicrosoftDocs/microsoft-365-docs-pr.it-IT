---
title: Microsoft Managed Desktop e ITIL
description: Correla le fasi ITIL con le informazioni e gli articoli di Microsoft Managed Desktop
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione, ITISM
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.openlocfilehash: e545b64670bb92c40465f1c50b2cb46b9fd7a8d8
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841436"
---
# <a name="microsoft-managed-desktop-and-itil"></a>Microsoft Managed Desktop e ITIL

Molte organizzazioni trovano utile strutturare i propri servizi IT in base a un modello di servizio IT formalizzato (ITSM), ad esempio [ITIL.](https://www.axelos.com/best-practice-solutions/itil) 

Microsoft Managed Desktop consente all'organizzazione di conformarsi a molti aspetti chiave di tali modelli ITSM formalizzati. Utilizzando ITIL come esempio, questo articolo consente di visualizzare le connessioni tra le fasi e i processi ITIL comuni e le funzionalità equivalenti di Microsoft Managed Desktop, ove applicabile. Queste informazioni si applicano solo alla parte Microsoft Managed Desktop dell'organizzazione.

Per informazioni più complete su ITIL e le relative fasi e processi, vedere la [relativa documentazione.](https://www.axelos.com/best-practice-solutions/itil)


## <a name="service-design"></a>Progettazione dei servizi

Questa tabella mette in relazione le fasi e i processi ITIL chiave con le funzionalità di Microsoft Managed Desktop, con collegamenti alla documentazione per informazioni dettagliate:



|Processo ITIL |Descrizione  |Documentazione |
|---------|---------|---------|
|Gestione a livello di servizio     | I tempi di risposta sono definiti per le richieste di supporto dell'amministratore e gli eventi imprevisti.  |  [Supporto amministratore per Microsoft Managed Desktop](working-with-managed-desktop/admin-support.md)  |
|Gestione del catalogo dei servizi     | La descrizione del servizio che dettaglia i componenti del servizio viene mantenuta allo stato del servizio, disponibile per tutti i clienti correnti e interessati.<br><br>Prerequisiti dettagliati per comprendere cosa è necessario per il funzionamento del servizio.  | - [Descrizione del servizio Microsoft Managed Desktop](service-description/index.md)<br><br>- [Prepararsi per la registrazione in Microsoft Managed Desktop](get-ready/index.md)  |
|Gestione della sicurezza delle informazioni     | Informazioni sulla sicurezza, inclusa la sicurezza delle informazioni per il servizio.<br><br> Criteri correlati alla sicurezza e altre informazioni sulla configurazione dei dispositivi.   | - [Sicurezza in Microsoft Managed Desktop](service-description/security.md)<br><br>- [Configurazione del dispositivo](service-description/device-policies.md)  |
|Gestione della disponibilità     |  Microsoft Managed Desktop bilancia la responsabilità con l'organizzazione per garantire la disponibilità del servizio.<br><br>Gli amministratori e gli utenti hanno instradato al rispettivo supporto in caso di problemi di servizio o disponibilità. | - [Operazioni e monitoraggio di Microsoft Managed Desktop](service-description/operations-and-monitoring.md)<br><br>- [Supporto dell'amministratore per Microsoft Managed Desktop](working-with-managed-desktop/admin-support.md)<br>- [Ottenere assistenza per gli utenti](working-with-managed-desktop/end-user-support.md)  |



## <a name="service-transition"></a>Transizione del servizio


|Processo ITIL |Descrizione  |Documentazione |
|---------|---------|---------|
|Gestione delle modifiche     | Equilibrio definito di responsabilità, panoramica del processo e tipi correlati alla gestione delle modifiche disponibili.  | [Operazioni e monitoraggio di Microsoft Managed Desktop](service-description/operations-and-monitoring.md#change-management) |
|Gestione delle versioni e della distribuzione     |  Microsoft Managed Desktop gestisce gli aggiornamenti per i dispositivi registrati nel servizio.  | [Modalità di gestione degli aggiornamenti in Microsoft Managed Desktop](service-description/updates.md)        |
|Gestione delle risorse di servizio e della configurazione     | Le informazioni relative alla distribuzione di Microsoft Managed Desktop dell'organizzazione sono disponibili nel portale di amministrazione IT.  | [Supporto amministratore per Microsoft Managed Desktop](working-with-managed-desktop/admin-support.md) |
|Gestione delle conoscenze     | Le informazioni sul servizio Microsoft Managed Desktop vengono mantenute aggiornate in questo sito.   | [Cronologia modifiche per la documentazione di Microsoft Managed Desktop](change-history-managed-desktop.md)        |



## <a name="service-operation"></a>Operazione del servizio


|Processo ITIL |Descrizione  |Documentazione  |
|---------|---------|---------|
|Gestione degli eventi     |  Vengono forniti dettagli sul monitoraggio dei dispositivi.<br><br>Le procedure operative standard per il servizio Microsoft Managed Desktop sono dettagliate. |  - [Sicurezza in Microsoft Managed Desktop](service-description/security.md)<br>- [Operazioni e monitoraggio di Microsoft Managed Desktop](service-description/operations-and-monitoring.md)       |
|Gestione degli incidenti  | Microsoft Managed Desktop analizza e agisce sugli eventi imprevisti in base alle definizioni di gravità definite.  |  [Definizioni di gravità delle richieste di supporto](working-with-managed-desktop/admin-support.md#support-request-severity-definitions)       |
|Gestione dell'evasione delle richieste     |  Vengono definiti il processo per le richieste di informazioni e le richieste di modifica relative al servizio Microsoft Managed Desktop.         |[Supporto amministratore per Microsoft Managed Desktop](working-with-managed-desktop/admin-support.md)         |
|Gestione dei problemi     | Eventuali problemi relativi al servizio devono essere indirizzati al team dell'account locale in questo momento. | Documentazione in fase di sviluppo |
|Gestione degli accessi     | Accedere ai componenti e alle responsabilità di gestione dei clienti per garantire che le funzionalità siano dettagliate.  | [Gestione delle identità e degli accessi](service-description/security.md#identity-and-access-management)        |
