---
title: Soluzioni di creazione di report personalizzate con analisi e risposta automatizzate
keywords: SIEM, API, AIR, autoIR, Microsoft Defender for Endpoint, indagine automatizzata, integrazione, report personalizzato
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
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
ms.openlocfilehash: 6ed752f9514f1d2c8cadeb7cbbd1d7b9311b1b5f
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275013"
---
# <a name="custom-or-third-party-reporting-solutions-for-microsoft-defender-for-office-365"></a>Soluzioni di creazione di report personalizzate o di terze parti per Microsoft Defender per Office 365

Con [Microsoft Defender per Office 365](defender-for-office-365.md), si ottengono informazioni [dettagliate sulle indagini automatizzate.](air-view-investigation-results.md) Tuttavia, alcune organizzazioni utilizzano anche una soluzione di creazione di report personalizzata o di terze parti. Se l'organizzazione vuole integrare le informazioni sulle indagini [automatizzate](office-365-air.md) con una soluzione di questo tipo, puoi usare l'API Office 365 Management Activity.

**Si applica a**
- [Microsoft Defender per Office 365 Piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Con [Microsoft Defender per Office 365](defender-for-office-365.md), si ottengono informazioni [dettagliate sulle indagini automatizzate.](air-view-investigation-results.md) Tuttavia, alcune organizzazioni utilizzano anche una soluzione di creazione di report personalizzata o di terze parti. Se l'organizzazione vuole integrare le informazioni sulle indagini automatizzate con una soluzione di questo tipo, puoi usare l'API Office 365 Management Activity.

|Risorsa|Descrizione|
|:---|:---|
|[Office 365 Panoramica delle API di gestione](/office/office-365-management-api/office-365-management-apis-overview)|L'API di Office 365 management fornisce informazioni su varie azioni ed eventi di utenti, amministratori, sistema e criteri da Microsoft 365 e Azure Active Directory log attività.|
|[Introduzione alle API Office 365 management](/office/office-365-management-api/get-started-with-office-365-management-apis)|L'API Office 365 management usa Azure AD per fornire servizi di autenticazione per l'applicazione per accedere Microsoft 365 dati. Seguire i passaggi descritti in questo articolo per configurare questa impostazione.|
|[Riferimento API Office 365 Management Activity](/office/office-365-management-api/office-365-management-activity-api-reference)|Puoi usare l'API Office 365 Management Activity per recuperare informazioni sulle azioni e gli eventi di utenti, amministratori, sistema e criteri da Microsoft 365 log attività di Azure AD. Leggi questo articolo per altre informazioni su come funziona.|
|[Schema API Office 365 Management Activity](/office/office-365-management-api/office-365-management-activity-api-schema)|Ottieni una panoramica dello [schema comune](/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) e di Defender per Office 365 e dello [schema](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) di analisi e risposta delle minacce per informazioni sui tipi specifici di dati disponibili tramite l'API Office 365 Management Activity.|
|

## <a name="see-also"></a>Vedere anche

- [Microsoft Defender per Office 365](defender-for-office-365.md)
- [Indagine e risposta automatizzate in Microsoft 365 Defender](/microsoft-365/security/defender/m365d-autoir)
