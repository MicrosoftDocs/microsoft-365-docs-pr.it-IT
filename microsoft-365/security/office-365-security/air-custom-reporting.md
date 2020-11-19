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
- m365initiative-defender-office365
description: Informazioni su come integrare l'analisi e la risposta automatizzate con una soluzione di report personalizzata o di terze parti.
ms.date: 09/29/2020
ms.custom:
- air
ms.openlocfilehash: 7b0b0570624b2e0dd40d40b178951a747698afe2
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357468"
---
# <a name="use-the-management-activity-api-for-custom-or-third-party-reporting-solutions"></a>Utilizzare l'API di gestione attività per soluzioni di Reporting personalizzate o di terze parti

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Con [Microsoft Defender per Office 365](office-365-atp.md), vengono [fornite informazioni dettagliate sulle indagini automatizzate](air-view-investigation-results.md). Tuttavia, alcune organizzazioni utilizzano anche una soluzione di reporting personalizzata o di terze parti. Se l'organizzazione desidera integrare informazioni su indagini automatizzate con una soluzione di questo tipo, è possibile utilizzare l'API di attività di gestione di Office 365.

Per impostare questa impostazione, utilizzare le risorse seguenti:

****

|Risorsa|Descrizione|
|---|---|
|[Panoramica delle API di gestione di Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)|L'API di attività di gestione di Office 365 fornisce informazioni su varie azioni e eventi relativi a utenti, amministratori, sistemi e criteri dei log attività di Microsoft 365 e Azure Active Directory.|
|[Iniziare a utilizzare le API di gestione di Office 365](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)|L'API di gestione di Office 365 utilizza Azure AD per fornire servizi di autenticazione per l'applicazione per accedere ai dati di Microsoft 365. Seguire la procedura descritta in questo articolo per configurare l'operazione.|
|[Riferimento API Office 365 Management Activity](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)|È possibile utilizzare l'API di attività di gestione di Office 365 per recuperare le informazioni sulle azioni e sugli eventi degli utenti, dell'amministratore, del sistema e dei criteri dai registri delle attività di Microsoft 365 e Azure AD. Leggere questo articolo per ulteriori informazioni su come funziona.|
|[Schema API Office 365 Management Activity](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)|Ottenere una panoramica dello [schema comune](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) e del [difensore per Office 365 e l'analisi delle minacce e lo schema di risposta](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) per informazioni sui tipi di dati specifici disponibili tramite l'API di attività di gestione di Office 365.|
|

## <a name="see-also"></a>Vedere anche

- [Microsoft Defender per Office 365](office-365-atp.md)

- [Analisi e risposta automatizzate in Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
