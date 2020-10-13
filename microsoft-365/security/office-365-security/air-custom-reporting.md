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
ms.openlocfilehash: 9bc5de44700b7f1b7207f8fae002adcb55d32841
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "48446684"
---
# <a name="use-the-management-activity-api-for-custom-or-third-party-reporting-solutions"></a><span data-ttu-id="f6386-104">Utilizzare l'API di gestione attività per soluzioni di Reporting personalizzate o di terze parti</span><span class="sxs-lookup"><span data-stu-id="f6386-104">Use the Management Activity API for custom or third-party reporting solutions</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="f6386-105">Con [Microsoft Defender per Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp), vengono [fornite informazioni dettagliate sulle indagini automatizzate](air-view-investigation-results.md).</span><span class="sxs-lookup"><span data-stu-id="f6386-105">With [Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp), you get [detailed information about automated investigations](air-view-investigation-results.md).</span></span> <span data-ttu-id="f6386-106">Tuttavia, alcune organizzazioni utilizzano anche una soluzione di reporting personalizzata o di terze parti.</span><span class="sxs-lookup"><span data-stu-id="f6386-106">However, some organizations also use a custom or third-party reporting solution.</span></span> <span data-ttu-id="f6386-107">Se l'organizzazione desidera integrare informazioni su indagini automatizzate con una soluzione di questo tipo, è possibile utilizzare l'API di attività di gestione di Office 365.</span><span class="sxs-lookup"><span data-stu-id="f6386-107">If your organization wants to integrate information about automated investigations with such a solution, you can use the Office 365 Management Activity API.</span></span>

<span data-ttu-id="f6386-108">Per impostare questa impostazione, utilizzare le risorse seguenti:</span><span class="sxs-lookup"><span data-stu-id="f6386-108">Use the following resources to set this up:</span></span>

****

|<span data-ttu-id="f6386-109">Risorsa</span><span class="sxs-lookup"><span data-stu-id="f6386-109">Resource</span></span>|<span data-ttu-id="f6386-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f6386-110">Description</span></span>|
|---|---|
|[<span data-ttu-id="f6386-111">Panoramica delle API di gestione di Office 365</span><span class="sxs-lookup"><span data-stu-id="f6386-111">Office 365 Management APIs overview</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)|<span data-ttu-id="f6386-112">L'API di attività di gestione di Office 365 fornisce informazioni su varie azioni e eventi relativi a utenti, amministratori, sistemi e criteri dei log attività di Microsoft 365 e Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f6386-112">The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Microsoft 365 and Azure Active Directory activity logs.</span></span>|
|[<span data-ttu-id="f6386-113">Iniziare a utilizzare le API di gestione di Office 365</span><span class="sxs-lookup"><span data-stu-id="f6386-113">Get started with Office 365 Management APIs</span></span>](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)|<span data-ttu-id="f6386-114">L'API di gestione di Office 365 utilizza Azure AD per fornire servizi di autenticazione per l'applicazione per accedere ai dati di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f6386-114">The Office 365 Management API uses Azure AD to provide authentication services for your application to access Microsoft 365 data.</span></span> <span data-ttu-id="f6386-115">Seguire la procedura descritta in questo articolo per configurare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="f6386-115">Follow the steps in this article to set this up.</span></span>|
|[<span data-ttu-id="f6386-116">Riferimento API Office 365 Management Activity</span><span class="sxs-lookup"><span data-stu-id="f6386-116">Office 365 Management Activity API reference</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)|<span data-ttu-id="f6386-117">È possibile utilizzare l'API di attività di gestione di Office 365 per recuperare le informazioni sulle azioni e sugli eventi degli utenti, dell'amministratore, del sistema e dei criteri dai registri delle attività di Microsoft 365 e Azure AD.</span><span class="sxs-lookup"><span data-stu-id="f6386-117">You can use the Office 365 Management Activity API to retrieve information about user, admin, system, and policy actions and events from Microsoft 365 and Azure AD activity logs.</span></span> <span data-ttu-id="f6386-118">Leggere questo articolo per ulteriori informazioni su come funziona.</span><span class="sxs-lookup"><span data-stu-id="f6386-118">Read this article to learn more about how this works.</span></span>|
|[<span data-ttu-id="f6386-119">Schema API Office 365 Management Activity</span><span class="sxs-lookup"><span data-stu-id="f6386-119">Office 365 Management Activity API schema</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)|<span data-ttu-id="f6386-120">Ottenere una panoramica dello [schema comune](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) e dello [schema di analisi e risposta di Office 365 ATP and Threat](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) per informazioni su tipi specifici di dati disponibili tramite l'API di attività di gestione di Office 365.</span><span class="sxs-lookup"><span data-stu-id="f6386-120">Get an overview of the [Common schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) and the [Office 365 ATP and threat investigation and response schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) to learn about specific kinds of data available through the Office 365 Management Activity API.</span></span>|
|

## <a name="see-also"></a><span data-ttu-id="f6386-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f6386-121">See also</span></span>

- [<span data-ttu-id="f6386-122">Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="f6386-122">Microsoft Defender for Office 365</span></span>](office-365-atp.md)

- [<span data-ttu-id="f6386-123">Analisi e risposta automatizzate in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f6386-123">Automated investigation and response in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
