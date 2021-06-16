---
title: Integrazione SIEM con Microsoft Defender per Office 365
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: None
search.appverid:
- MET150
- MOE150
ms.assetid: eb56b69b-3170-4086-82cf-ba40a530fa1b
ms.date: 08/21/2020
ms.collection:
- M365-security-compliance
description: Integrare il server SIEM dell'organizzazione con Microsoft Defender per Office 365 e gli eventi di minaccia correlati nell'API Office 365 Activity Management.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f3d6bbacb4a64060ecd03cbb28eee3256f41827e
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/14/2021
ms.locfileid: "52929780"
---
# <a name="siem-integration-with-microsoft-defender-for-office-365"></a><span data-ttu-id="f96ce-103">Integrazione SIEM con Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="f96ce-103">SIEM integration with Microsoft Defender for Office 365</span></span>

<span data-ttu-id="f96ce-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="f96ce-104">**Applies to**</span></span>
- [<span data-ttu-id="f96ce-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="f96ce-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="f96ce-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="f96ce-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="f96ce-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f96ce-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="f96ce-108">Se l'organizzazione usa un server siEM (Security Information and Event Management), è possibile integrare Microsoft Defender per Office 365 con il server SIEM.</span><span class="sxs-lookup"><span data-stu-id="f96ce-108">If your organization is using a security information and event management (SIEM) server, you can integrate Microsoft Defender for Office 365 with your SIEM server.</span></span> <span data-ttu-id="f96ce-109">Puoi configurare questa integrazione usando [l'API Office 365 Activity Management.](/office/office-365-management-api/office-365-management-activity-api-reference)</span><span class="sxs-lookup"><span data-stu-id="f96ce-109">You can set up this integration by using the [Office 365 Activity Management API](/office/office-365-management-api/office-365-management-activity-api-reference).</span></span>

<span data-ttu-id="f96ce-110">L'integrazione SIEM consente di visualizzare informazioni, ad esempio malware o phish rilevati da Microsoft Defender per Office 365, nei report del server SIEM.</span><span class="sxs-lookup"><span data-stu-id="f96ce-110">SIEM integration enables you to view information, such as malware or phish detected by Microsoft Defender for Office 365, in your SIEM server reports.</span></span>

- <span data-ttu-id="f96ce-111">Per un esempio di integrazione SIEM con Microsoft Defender per Office 365, vedi il blog di Tech Community: Migliorare l'efficacia del TUO SOC con Defender per Office 365 e l'API di gestione [di O365.](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)</span><span class="sxs-lookup"><span data-stu-id="f96ce-111">To see an example of SIEM integration with Microsoft Defender for Office 365, see [Tech Community blog: Improve the Effectiveness of your SOC with Defender for Office 365 and the O365 Management API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).</span></span>

- <span data-ttu-id="f96ce-112">Per altre informazioni sulle API di Office 365 Management, vedi panoramica delle API di Office 365 [Management.](/office/office-365-management-api/office-365-management-apis-overview)</span><span class="sxs-lookup"><span data-stu-id="f96ce-112">To learn more about the Office 365 Management APIs, see [Office 365 Management APIs overview](/office/office-365-management-api/office-365-management-apis-overview).</span></span>

## <a name="how-siem-integration-works"></a><span data-ttu-id="f96ce-113">Funzionamento dell'integrazione SIEM</span><span class="sxs-lookup"><span data-stu-id="f96ce-113">How SIEM integration works</span></span>

<span data-ttu-id="f96ce-114">L'API Office 365 activity management consente di recuperare informazioni sulle azioni e gli eventi degli utenti, degli amministratori, del sistema e dei criteri dai registri delle attività Microsoft 365 e Azure Active Directory'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f96ce-114">The Office 365 Activity Management API retrieves information about user, admin, system, and policy actions and events from your organization's Microsoft 365 and Azure Active Directory activity logs.</span></span> <span data-ttu-id="f96ce-115">Se l'organizzazione dispone di Microsoft Defender per Office 365 Piano 1 o 2 o Office 365 E5, è possibile utilizzare Microsoft Defender per Office 365 [schema.](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)</span><span class="sxs-lookup"><span data-stu-id="f96ce-115">If your organization has Microsoft Defender for Office 365 Plan 1 or 2, or Office 365 E5, you can use the [Microsoft Defender for Office 365 schema](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema).</span></span>

<span data-ttu-id="f96ce-116">Di recente, gli eventi delle funzionalità di analisi e risposta automatizzate in [Microsoft Defender per Office 365 Piano 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) sono stati aggiunti all'API di Office 365 Management Activity.</span><span class="sxs-lookup"><span data-stu-id="f96ce-116">Recently, events from automated investigation and response capabilities in [Microsoft Defender for Office 365 Plan 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) were added to the Office 365 Management Activity API.</span></span> <span data-ttu-id="f96ce-117">Oltre a includere dati sui dettagli dell'indagine di base, ad esempio ID, nome e stato, l'API contiene anche informazioni di alto livello sulle azioni ed entità di indagine.</span><span class="sxs-lookup"><span data-stu-id="f96ce-117">In addition to including data about core investigation details such as ID, name and status, the API also contains high-level information about investigation actions and entities.</span></span>

<span data-ttu-id="f96ce-118">Il server SIEM o un altro sistema simile esegue il polling del **carico di lavoro audit.general** per accedere agli eventi di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="f96ce-118">The SIEM server or other similar system polls the **audit.general** workload to access detection events.</span></span> <span data-ttu-id="f96ce-119">Per altre informazioni, vedi [Introduzione alle API Office 365 management](/office/office-365-management-api/get-started-with-office-365-management-apis).</span><span class="sxs-lookup"><span data-stu-id="f96ce-119">To learn more, see [Get started with Office 365 Management APIs](/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span>

## <a name="enum-auditlogrecordtype---type-edmint32"></a><span data-ttu-id="f96ce-120">Enumerazione: AuditLogRecordType - Tipo: Edm.Int32</span><span class="sxs-lookup"><span data-stu-id="f96ce-120">Enum: AuditLogRecordType - Type: Edm.Int32</span></span>

### <a name="auditlogrecordtype"></a><span data-ttu-id="f96ce-121">AuditLogRecordType</span><span class="sxs-lookup"><span data-stu-id="f96ce-121">AuditLogRecordType</span></span>

<span data-ttu-id="f96ce-122">Nella tabella seguente sono riepilogati i valori di **AuditLogRecordType** rilevanti per Microsoft Defender per Office 365 eventi:</span><span class="sxs-lookup"><span data-stu-id="f96ce-122">The following table summarizes the values of **AuditLogRecordType** that are relevant for Microsoft Defender for Office 365 events:</span></span>

|<span data-ttu-id="f96ce-123">Valore</span><span class="sxs-lookup"><span data-stu-id="f96ce-123">Value</span></span>|<span data-ttu-id="f96ce-124">Nome membro</span><span class="sxs-lookup"><span data-stu-id="f96ce-124">Member name</span></span>|<span data-ttu-id="f96ce-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f96ce-125">Description</span></span>|
|---|---|---|
|<span data-ttu-id="f96ce-126">28</span><span class="sxs-lookup"><span data-stu-id="f96ce-126">28</span></span>|<span data-ttu-id="f96ce-127">ThreatIntelligence</span><span class="sxs-lookup"><span data-stu-id="f96ce-127">ThreatIntelligence</span></span>|<span data-ttu-id="f96ce-128">Eventi di phishing e malware da Exchange Online Protection e Microsoft Defender per Office 365.</span><span class="sxs-lookup"><span data-stu-id="f96ce-128">Phishing and malware events from Exchange Online Protection and Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="f96ce-129">41</span><span class="sxs-lookup"><span data-stu-id="f96ce-129">41</span></span>|<span data-ttu-id="f96ce-130">ThreatIntelligenceUrl</span><span class="sxs-lookup"><span data-stu-id="f96ce-130">ThreatIntelligenceUrl</span></span>|<span data-ttu-id="f96ce-131">Tempo di blocco e blocco degli eventi di sostituzione dei collegamenti sicuri da Microsoft Defender per Office 365.</span><span class="sxs-lookup"><span data-stu-id="f96ce-131">Safe Links time-of-block and block override events from Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="f96ce-132">47</span><span class="sxs-lookup"><span data-stu-id="f96ce-132">47</span></span>|<span data-ttu-id="f96ce-133">ThreatIntelligenceAtpContent</span><span class="sxs-lookup"><span data-stu-id="f96ce-133">ThreatIntelligenceAtpContent</span></span>|<span data-ttu-id="f96ce-134">Eventi di phishing e malware per i file in SharePoint Online, OneDrive for Business e Microsoft Teams, da Microsoft Defender per Office 365.</span><span class="sxs-lookup"><span data-stu-id="f96ce-134">Phishing and malware events for files in SharePoint Online, OneDrive for Business, and Microsoft Teams, from Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="f96ce-135">64</span><span class="sxs-lookup"><span data-stu-id="f96ce-135">64</span></span>|<span data-ttu-id="f96ce-136">AirInvestigation</span><span class="sxs-lookup"><span data-stu-id="f96ce-136">AirInvestigation</span></span>|<span data-ttu-id="f96ce-137">Eventi di indagine e risposta automatizzati, ad esempio dettagli dell'indagine e artefatti rilevanti, da Microsoft Defender per Office 365 Piano 2.</span><span class="sxs-lookup"><span data-stu-id="f96ce-137">Automated investigation and response events, such as investigation details and relevant artifacts, from Microsoft Defender for Office 365 Plan 2.</span></span>|
|

> [!IMPORTANT]
> <span data-ttu-id="f96ce-138">Devi essere un amministratore globale o avere il ruolo di amministratore della sicurezza assegnato per il portale di Microsoft 365 Defender per configurare l'integrazione SIEM con Microsoft Defender per Office 365.</span><span class="sxs-lookup"><span data-stu-id="f96ce-138">You must be a global administrator or have the security administrator role assigned for the Microsoft 365 Defender portal to set up SIEM integration with Microsoft Defender for Office 365.</span></span>
>
> <span data-ttu-id="f96ce-139">La registrazione di controllo deve essere attivata per l'Microsoft 365 locale.</span><span class="sxs-lookup"><span data-stu-id="f96ce-139">Audit logging must be turned on for your Microsoft 365 environment.</span></span> <span data-ttu-id="f96ce-140">Per informazioni su questo argomento, vedere Attivare o disattivare la ricerca nel [log di controllo.](../../compliance/turn-audit-log-search-on-or-off.md)</span><span class="sxs-lookup"><span data-stu-id="f96ce-140">To get help with this, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f96ce-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f96ce-141">See also</span></span>

[<span data-ttu-id="f96ce-142">Analisi delle minacce e risposta alle minacce in Office 365</span><span class="sxs-lookup"><span data-stu-id="f96ce-142">Office 365 threat investigation and response</span></span>](office-365-ti.md)

[<span data-ttu-id="f96ce-143">Analisi e risposta automatizzate (AIR) in Office 365</span><span class="sxs-lookup"><span data-stu-id="f96ce-143">Automated investigation and response (AIR) in Office 365</span></span>](automated-investigation-response-office.md)