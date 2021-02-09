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
description: Informazioni su come integrare analisi e risposte automatizzate con una soluzione di creazione di report personalizzata o di terze parti.
ms.date: 01/29/2021
ms.custom:
- air
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3d8363ada4de60d37cb0d247d8b1af74df4226d1
ms.sourcegitcommit: d739f48b991793c08522a3d5323beba27f0111b2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/08/2021
ms.locfileid: "50142976"
---
# <a name="custom-or-third-party-reporting-solutions-for-microsoft-defender-for-office-365"></a>Soluzioni di creazione di report personalizzate o di terze parti per Microsoft Defender per Office 365

Con [Microsoft Defender per Office 365,](office-365-atp.md)si ottengono informazioni [dettagliate sulle indagini automatizzate.](air-view-investigation-results.md) Tuttavia, alcune organizzazioni utilizzano anche una soluzione di creazione di report personalizzata o di terze parti. Se l'organizzazione desidera [](office-365-air.md) integrare le informazioni sulle indagini automatizzate con una soluzione di questo tipo, è possibile utilizzare l'API Office 365 Management Activity.

Risorse per configurare l'integrazione

|Risorsa|Descrizione|
|:---|:---|
|[Panoramica delle API di gestione di Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)|L'API Office 365 Management Activity fornisce informazioni su vari eventi, azioni ed eventi di utenti, amministratori, sistema e criteri dai log attività di Microsoft 365 e Azure Active Directory.|
|[Introduzione alle API di gestione di Office 365](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)|L'API di gestione di Office 365 usa Azure AD per fornire servizi di autenticazione per l'applicazione per accedere ai dati di Microsoft 365. Seguire i passaggi descritti in questo articolo per configurarlo.|
|[Riferimento API Office 365 Management Activity](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)|È possibile usare l'API Office 365 Management Activity per recuperare informazioni sulle azioni e gli eventi di utenti, amministratori, sistema e criteri dai log attività di Microsoft 365 e Azure AD. Leggi questo articolo per altre informazioni su come funziona.|
|[Schema API Office 365 Management Activity](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)|Panoramica dello schema comune e di [Defender per Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) e dello [schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) di analisi e risposta alle minacce per informazioni su tipi specifici di dati disponibili tramite l'API Office 365 Management Activity.|
|

## <a name="see-also"></a>Vedere anche

- [Microsoft Defender per Office 365](office-365-atp.md)
- [Analisi e risposta automatizzate in Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
