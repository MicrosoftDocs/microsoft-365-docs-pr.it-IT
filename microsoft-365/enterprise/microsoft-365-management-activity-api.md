---
title: API Office 365 Management Activity
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-analytics
f1.keywords:
- NOCSH
description: In questo articolo è possibile trovare un breve riepilogo sull'API di attività di gestione di Office 365 e sulle informazioni fornite dai registri delle attività.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8d51f27f28b0adb84ef43004664ef310567263b9
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332305"
---
# <a name="office-365-management-activity-api"></a>API Office 365 Management Activity

Microsoft fornisce Reporting Services che è possibile utilizzare per ottenere informazioni transazionali aggregate sul tenant di Office 365. L' [API di attività di gestione di Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview#office-365-management-activity-api) utilizza una struttura RESTful standard del settore e OAuth V2 per l'autenticazione. In questo modo è più facile iniziare a sperimentare con il recupero dei dati e l'ingestione in strumenti e applicazioni di visualizzazione. L'API fornisce un feed di dati con informazioni sull'utente, l'amministratore, le operazioni e le attività di sicurezza in Office 365. I dati possono essere conservati per scopi normativi oppure combinati con i dati di log acquistati da un'infrastruttura locale o da altre origini. In questo modo viene creata una soluzione di monitoraggio per le operazioni, la sicurezza e la conformità all'interno dell'organizzazione.

L'API di attività di gestione di Office 365 fornisce informazioni su varie azioni e eventi relativi a utenti, amministratori, sistemi e criteri dei log attività di Office 365 e Azure Active Directory. L'API fornisce uno schema di controllo coerente con oltre 10 campi comuni in tutti i servizi. L'API consente alle organizzazioni di semplificare le connessioni tra gli eventi e consente di creare nuovi modi per ragionare sui dati.

Dozzine di fornitori di software indipendenti (ISV) hanno collaborato con Microsoft e hanno costruito soluzioni basate sull'API. Alcune soluzioni sono incentrate unicamente sui dati di Office 365 e su altri dati di origine provenienti da più provider cloud e sistemi locali per creare una visualizzazione unificata delle attività relative a operazioni, sicurezza e conformità. 

Per ulteriori informazioni, vedere la Guida di [riferimento all'API dell'attività di gestione di Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).
