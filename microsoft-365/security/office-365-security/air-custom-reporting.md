---
title: Soluzioni di creazione di report personalizzate con analisi e risposta automatizzate
keywords: SIEM, API, AIR, autoIR, ATP, indagine automatizzata, integrazione, report personalizzato
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Scopri come integrare analisi e risposte automatizzate con una soluzione di reporting personalizzata o di terze parti.
ms.date: 01/29/2021
ms.custom:
- air
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 82f3b38e5b6e31313c94f5ac389e883f6b076540
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206722"
---
# <a name="custom-or-third-party-reporting-solutions-for-microsoft-defender-for-office-365"></a>Soluzioni di creazione di report personalizzate o di terze parti per Microsoft Defender per Office 365

Con [Microsoft Defender per Office 365,](defender-for-office-365.md)si ottengono informazioni [dettagliate sulle indagini automatizzate.](air-view-investigation-results.md) Tuttavia, alcune organizzazioni utilizzano anche una soluzione di creazione di report personalizzata o di terze parti. Se l'organizzazione desidera [](office-365-air.md) integrare le informazioni sulle indagini automatizzate con una soluzione di questo tipo, è possibile usare l'API di attività di gestione di Office 365.

**Si applica a**
- [Microsoft Defender per Office 365 Piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Con [Microsoft Defender per Office 365,](defender-for-office-365.md)si ottengono informazioni [dettagliate sulle indagini automatizzate.](air-view-investigation-results.md) Tuttavia, alcune organizzazioni utilizzano anche una soluzione di creazione di report personalizzata o di terze parti. Se l'organizzazione desidera integrare le informazioni sulle indagini automatizzate con una soluzione di questo tipo, è possibile usare l'API di attività di gestione di Office 365.

|Risorsa|Descrizione|
|:---|:---|
|[Panoramica delle API di gestione di Office 365](/office/office-365-management-api/office-365-management-apis-overview)|L'API di attività di gestione di Office 365 fornisce informazioni su varie azioni ed eventi di utenti, amministratori, sistema e criteri dai log attività di Microsoft 365 e Azure Active Directory.|
|[Introduzione alle API di gestione di Office 365](/office/office-365-management-api/get-started-with-office-365-management-apis)|L'API di gestione di Office 365 usa Azure AD per fornire servizi di autenticazione per l'applicazione per accedere ai dati di Microsoft 365. Seguire i passaggi descritti in questo articolo per configurare questa impostazione.|
|[Riferimento API Office 365 Management Activity](/office/office-365-management-api/office-365-management-activity-api-reference)|È possibile utilizzare l'API di attività di gestione di Office 365 per recuperare informazioni sulle azioni e gli eventi di utenti, amministratori, sistema e criteri dai log attività di Microsoft 365 e Azure AD. Leggi questo articolo per altre informazioni su come funziona.|
|[Schema API Office 365 Management Activity](/office/office-365-management-api/office-365-management-activity-api-schema)|Ottenere una panoramica dello [schema comune](/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) e di Defender per [Office 365](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) e dello schema di analisi e risposta delle minacce per informazioni sui tipi specifici di dati disponibili tramite l'API di attività di gestione di Office 365.|
|

## <a name="see-also"></a>Vedere anche

- [Microsoft Defender per Office 365](defender-for-office-365.md)
- [Analisi e risposta automatizzate in Microsoft 365 Defender](/microsoft-365/security/defender/m365d-autoir)
