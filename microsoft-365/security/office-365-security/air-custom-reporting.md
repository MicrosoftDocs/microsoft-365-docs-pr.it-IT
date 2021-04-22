---
title: Soluzioni di creazione di report personalizzate con analisi e risposta automatizzate
keywords: SIEM, API, AIR, autoIR, Microsoft Defender for Endpoint, indagine automatizzata, integrazione, report personalizzato
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
ms.openlocfilehash: 4a7ccc0f07691c5183b9cb7a6e5b3f512f35f76b
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935402"
---
# <a name="custom-or-third-party-reporting-solutions-for-microsoft-defender-for-office-365"></a><span data-ttu-id="2630f-104">Soluzioni di creazione di report personalizzate o di terze parti per Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="2630f-104">Custom or third-party reporting solutions for Microsoft Defender for Office 365</span></span>

<span data-ttu-id="2630f-105">Con [Microsoft Defender per Office 365,](defender-for-office-365.md)si ottengono informazioni [dettagliate sulle indagini automatizzate.](air-view-investigation-results.md)</span><span class="sxs-lookup"><span data-stu-id="2630f-105">With [Microsoft Defender for Office 365](defender-for-office-365.md), you get [detailed information about automated investigations](air-view-investigation-results.md).</span></span> <span data-ttu-id="2630f-106">Tuttavia, alcune organizzazioni utilizzano anche una soluzione di creazione di report personalizzata o di terze parti.</span><span class="sxs-lookup"><span data-stu-id="2630f-106">However, some organizations also use a custom or third-party reporting solution.</span></span> <span data-ttu-id="2630f-107">Se l'organizzazione desidera [](office-365-air.md) integrare le informazioni sulle indagini automatizzate con una soluzione di questo tipo, è possibile usare l'API di attività di gestione di Office 365.</span><span class="sxs-lookup"><span data-stu-id="2630f-107">If your organization wants to integrate information about [automated investigations](office-365-air.md) with such a solution, you can use the Office 365 Management Activity API.</span></span>

<span data-ttu-id="2630f-108">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="2630f-108">**Applies to**</span></span>
- [<span data-ttu-id="2630f-109">Microsoft Defender per Office 365 Piano 2</span><span class="sxs-lookup"><span data-stu-id="2630f-109">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="2630f-110">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2630f-110">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="2630f-111">Con [Microsoft Defender per Office 365,](defender-for-office-365.md)si ottengono informazioni [dettagliate sulle indagini automatizzate.](air-view-investigation-results.md)</span><span class="sxs-lookup"><span data-stu-id="2630f-111">With [Microsoft Defender for Office 365](defender-for-office-365.md), you get [detailed information about automated investigations](air-view-investigation-results.md).</span></span> <span data-ttu-id="2630f-112">Tuttavia, alcune organizzazioni utilizzano anche una soluzione di creazione di report personalizzata o di terze parti.</span><span class="sxs-lookup"><span data-stu-id="2630f-112">However, some organizations also use a custom or third-party reporting solution.</span></span> <span data-ttu-id="2630f-113">Se l'organizzazione desidera integrare le informazioni sulle indagini automatizzate con una soluzione di questo tipo, è possibile usare l'API di attività di gestione di Office 365.</span><span class="sxs-lookup"><span data-stu-id="2630f-113">If your organization wants to integrate information about automated investigations with such a solution, you can use the Office 365 Management Activity API.</span></span>

|<span data-ttu-id="2630f-114">Risorsa</span><span class="sxs-lookup"><span data-stu-id="2630f-114">Resource</span></span>|<span data-ttu-id="2630f-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2630f-115">Description</span></span>|
|:---|:---|
|[<span data-ttu-id="2630f-116">Panoramica delle API di gestione di Office 365</span><span class="sxs-lookup"><span data-stu-id="2630f-116">Office 365 Management APIs overview</span></span>](/office/office-365-management-api/office-365-management-apis-overview)|<span data-ttu-id="2630f-117">L'API di attività di gestione di Office 365 fornisce informazioni su varie azioni ed eventi di utenti, amministratori, sistema e criteri dai log attività di Microsoft 365 e Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2630f-117">The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Microsoft 365 and Azure Active Directory activity logs.</span></span>|
|[<span data-ttu-id="2630f-118">Introduzione alle API di gestione di Office 365</span><span class="sxs-lookup"><span data-stu-id="2630f-118">Get started with Office 365 Management APIs</span></span>](/office/office-365-management-api/get-started-with-office-365-management-apis)|<span data-ttu-id="2630f-119">L'API di gestione di Office 365 usa Azure AD per fornire servizi di autenticazione per l'applicazione per accedere ai dati di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2630f-119">The Office 365 Management API uses Azure AD to provide authentication services for your application to access Microsoft 365 data.</span></span> <span data-ttu-id="2630f-120">Seguire i passaggi descritti in questo articolo per configurare questa impostazione.</span><span class="sxs-lookup"><span data-stu-id="2630f-120">Follow the steps in this article to set this up.</span></span>|
|[<span data-ttu-id="2630f-121">Riferimento API Office 365 Management Activity</span><span class="sxs-lookup"><span data-stu-id="2630f-121">Office 365 Management Activity API reference</span></span>](/office/office-365-management-api/office-365-management-activity-api-reference)|<span data-ttu-id="2630f-122">È possibile utilizzare l'API di attività di gestione di Office 365 per recuperare informazioni sulle azioni e gli eventi di utenti, amministratori, sistema e criteri dai log attività di Microsoft 365 e Azure AD.</span><span class="sxs-lookup"><span data-stu-id="2630f-122">You can use the Office 365 Management Activity API to retrieve information about user, admin, system, and policy actions and events from Microsoft 365 and Azure AD activity logs.</span></span> <span data-ttu-id="2630f-123">Leggi questo articolo per altre informazioni su come funziona.</span><span class="sxs-lookup"><span data-stu-id="2630f-123">Read this article to learn more about how this works.</span></span>|
|[<span data-ttu-id="2630f-124">Schema API Office 365 Management Activity</span><span class="sxs-lookup"><span data-stu-id="2630f-124">Office 365 Management Activity API schema</span></span>](/office/office-365-management-api/office-365-management-activity-api-schema)|<span data-ttu-id="2630f-125">Ottenere una panoramica dello [schema comune](/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) e di Defender per [Office 365](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) e dello schema di analisi e risposta delle minacce per informazioni sui tipi specifici di dati disponibili tramite l'API di attività di gestione di Office 365.</span><span class="sxs-lookup"><span data-stu-id="2630f-125">Get an overview of the [Common schema](/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) and the [Defender for Office 365 and threat investigation and response schema](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) to learn about specific kinds of data available through the Office 365 Management Activity API.</span></span>|
|

## <a name="see-also"></a><span data-ttu-id="2630f-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2630f-126">See also</span></span>

- [<span data-ttu-id="2630f-127">Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="2630f-127">Microsoft Defender for Office 365</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="2630f-128">Analisi e risposta automatizzate in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2630f-128">Automated investigation and response in Microsoft 365 Defender</span></span>](/microsoft-365/security/defender/m365d-autoir)
