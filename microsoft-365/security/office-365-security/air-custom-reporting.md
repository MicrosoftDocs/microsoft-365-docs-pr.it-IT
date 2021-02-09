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
# <a name="custom-or-third-party-reporting-solutions-for-microsoft-defender-for-office-365"></a><span data-ttu-id="616d1-104">Soluzioni di creazione di report personalizzate o di terze parti per Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="616d1-104">Custom or third-party reporting solutions for Microsoft Defender for Office 365</span></span>

<span data-ttu-id="616d1-105">Con [Microsoft Defender per Office 365,](office-365-atp.md)si ottengono informazioni [dettagliate sulle indagini automatizzate.](air-view-investigation-results.md)</span><span class="sxs-lookup"><span data-stu-id="616d1-105">With [Microsoft Defender for Office 365](office-365-atp.md), you get [detailed information about automated investigations](air-view-investigation-results.md).</span></span> <span data-ttu-id="616d1-106">Tuttavia, alcune organizzazioni utilizzano anche una soluzione di creazione di report personalizzata o di terze parti.</span><span class="sxs-lookup"><span data-stu-id="616d1-106">However, some organizations also use a custom or third-party reporting solution.</span></span> <span data-ttu-id="616d1-107">Se l'organizzazione desidera [](office-365-air.md) integrare le informazioni sulle indagini automatizzate con una soluzione di questo tipo, è possibile utilizzare l'API Office 365 Management Activity.</span><span class="sxs-lookup"><span data-stu-id="616d1-107">If your organization wants to integrate information about [automated investigations](office-365-air.md) with such a solution, you can use the Office 365 Management Activity API.</span></span>

<span data-ttu-id="616d1-108">Risorse per configurare l'integrazione</span><span class="sxs-lookup"><span data-stu-id="616d1-108">Resources to configure integration</span></span>

|<span data-ttu-id="616d1-109">Risorsa</span><span class="sxs-lookup"><span data-stu-id="616d1-109">Resource</span></span>|<span data-ttu-id="616d1-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="616d1-110">Description</span></span>|
|:---|:---|
|[<span data-ttu-id="616d1-111">Panoramica delle API di gestione di Office 365</span><span class="sxs-lookup"><span data-stu-id="616d1-111">Office 365 Management APIs overview</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)|<span data-ttu-id="616d1-112">L'API Office 365 Management Activity fornisce informazioni su vari eventi, azioni ed eventi di utenti, amministratori, sistema e criteri dai log attività di Microsoft 365 e Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="616d1-112">The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Microsoft 365 and Azure Active Directory activity logs.</span></span>|
|[<span data-ttu-id="616d1-113">Introduzione alle API di gestione di Office 365</span><span class="sxs-lookup"><span data-stu-id="616d1-113">Get started with Office 365 Management APIs</span></span>](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)|<span data-ttu-id="616d1-114">L'API di gestione di Office 365 usa Azure AD per fornire servizi di autenticazione per l'applicazione per accedere ai dati di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="616d1-114">The Office 365 Management API uses Azure AD to provide authentication services for your application to access Microsoft 365 data.</span></span> <span data-ttu-id="616d1-115">Seguire i passaggi descritti in questo articolo per configurarlo.</span><span class="sxs-lookup"><span data-stu-id="616d1-115">Follow the steps in this article to set this up.</span></span>|
|[<span data-ttu-id="616d1-116">Riferimento API Office 365 Management Activity</span><span class="sxs-lookup"><span data-stu-id="616d1-116">Office 365 Management Activity API reference</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)|<span data-ttu-id="616d1-117">È possibile usare l'API Office 365 Management Activity per recuperare informazioni sulle azioni e gli eventi di utenti, amministratori, sistema e criteri dai log attività di Microsoft 365 e Azure AD.</span><span class="sxs-lookup"><span data-stu-id="616d1-117">You can use the Office 365 Management Activity API to retrieve information about user, admin, system, and policy actions and events from Microsoft 365 and Azure AD activity logs.</span></span> <span data-ttu-id="616d1-118">Leggi questo articolo per altre informazioni su come funziona.</span><span class="sxs-lookup"><span data-stu-id="616d1-118">Read this article to learn more about how this works.</span></span>|
|[<span data-ttu-id="616d1-119">Schema API Office 365 Management Activity</span><span class="sxs-lookup"><span data-stu-id="616d1-119">Office 365 Management Activity API schema</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)|<span data-ttu-id="616d1-120">Panoramica dello schema comune e di [Defender per Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) e dello [schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) di analisi e risposta alle minacce per informazioni su tipi specifici di dati disponibili tramite l'API Office 365 Management Activity.</span><span class="sxs-lookup"><span data-stu-id="616d1-120">Get an overview of the [Common schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) and the [Defender for Office 365 and threat investigation and response schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) to learn about specific kinds of data available through the Office 365 Management Activity API.</span></span>|
|

## <a name="see-also"></a><span data-ttu-id="616d1-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="616d1-121">See also</span></span>

- [<span data-ttu-id="616d1-122">Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="616d1-122">Microsoft Defender for Office 365</span></span>](office-365-atp.md)
- [<span data-ttu-id="616d1-123">Analisi e risposta automatizzate in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="616d1-123">Automated investigation and response in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
