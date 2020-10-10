---
title: Utilizzo di soluzioni di Reporting personalizzate con l'analisi e la risposta automatizzate
keywords: SIEM, API, AIR, autoIR, ATP, analisi automatizzata, integrazione, report personalizzato
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365-initiative-defender-office365
description: Informazioni su come integrare l'analisi e la risposta automatizzate con una soluzione di report personalizzata o di terze parti.
ms.date: 09/29/2020
ms.custom:
- air
ms.openlocfilehash: 429ceae87e3beeb9ec0a254b120289be4ab51d16
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/09/2020
ms.locfileid: "48411974"
---
# <a name="use-the-management-activity-api-for-custom-or-third-party-reporting-solutions"></a>Utilizzare l'API di gestione attività per soluzioni di Reporting personalizzate o di terze parti

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Con [Microsoft Defender per Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp), vengono [fornite informazioni dettagliate sulle indagini automatizzate](air-view-investigation-results.md). Tuttavia, alcune organizzazioni utilizzano anche una soluzione di reporting personalizzata o di terze parti. Se l'organizzazione desidera integrare informazioni su indagini automatizzate con una soluzione di questo tipo, è possibile utilizzare l'API di attività di gestione di Office 365.

Per impostare questa impostazione, utilizzare le risorse seguenti:

****

|Risorsa|Descrizione|
|---|---|
|[Panoramica delle API di gestione di Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)|L'API di attività di gestione di Office 365 fornisce informazioni su varie azioni e eventi relativi a utenti, amministratori, sistemi e criteri dei log attività di Microsoft 365 e Azure Active Directory.|
|[Iniziare a utilizzare le API di gestione di Office 365](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)|L'API di gestione di Office 365 utilizza Azure AD per fornire servizi di autenticazione per l'applicazione per accedere ai dati di Microsoft 365. Seguire la procedura descritta in questo articolo per configurare l'operazione.|
|[Guida di riferimento all'API dell'attività di gestione di Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)|È possibile utilizzare l'API di attività di gestione di Office 365 per recuperare le informazioni sulle azioni e sugli eventi degli utenti, dell'amministratore, del sistema e dei criteri dai registri delle attività di Microsoft 365 e Azure AD. Leggere questo articolo per ulteriori informazioni su come funziona.|
|[Schema API di attività di gestione di Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)|Ottenere una panoramica dello [schema comune](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) e dello [schema di analisi e risposta di Office 365 ATP and Threat](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) per informazioni su tipi specifici di dati disponibili tramite l'API di attività di gestione di Office 365.|
|

## <a name="see-also"></a>Vedere anche

- [Microsoft Defender per Office 365](office-365-atp.md)

- [Analisi e risposta automatizzate in Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
