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
description: Integrare il server SIEM dell'organizzazione con Microsoft Defender per Office 365 e gli eventi di minaccia correlati nell'API di gestione delle attività di Office 365.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ca8f86c831df16568ae569e7b21c7e0a33475948
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205175"
---
# <a name="siem-integration-with-microsoft-defender-for-office-365"></a><span data-ttu-id="62b68-103">Integrazione SIEM con Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="62b68-103">SIEM integration with Microsoft Defender for Office 365</span></span>

<span data-ttu-id="62b68-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="62b68-104">**Applies to**</span></span>
- [<span data-ttu-id="62b68-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="62b68-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="62b68-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="62b68-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="62b68-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="62b68-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="62b68-108">Se l'organizzazione usa un server SIEM (Security Information and Event Management), è possibile integrare Microsoft Defender per Office 365 con il server SIEM.</span><span class="sxs-lookup"><span data-stu-id="62b68-108">If your organization is using a security information and event management (SIEM) server, you can integrate Microsoft Defender for Office 365 with your SIEM server.</span></span> <span data-ttu-id="62b68-109">È possibile configurare questa integrazione usando l'API di gestione delle attività di [Office 365.](/office/office-365-management-api/office-365-management-activity-api-reference)</span><span class="sxs-lookup"><span data-stu-id="62b68-109">You can set up this integration by using the [Office 365 Activity Management API](/office/office-365-management-api/office-365-management-activity-api-reference).</span></span>

<span data-ttu-id="62b68-110">L'integrazione SIEM consente di visualizzare informazioni, ad esempio malware o phish rilevati da Microsoft Defender per Office 365, nei report del server SIEM.</span><span class="sxs-lookup"><span data-stu-id="62b68-110">SIEM integration enables you to view information, such as malware or phish detected by Microsoft Defender for Office 365, in your SIEM server reports.</span></span>

- <span data-ttu-id="62b68-111">Per un esempio di integrazione SIEM con Microsoft Defender per Office 365, vedere blog della community tech: migliorare l'efficacia del SOC con [Defender per Office 365 e l'API di gestione di O365.](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)</span><span class="sxs-lookup"><span data-stu-id="62b68-111">To see an example of SIEM integration with Microsoft Defender for Office 365, see [Tech Community blog: Improve the Effectiveness of your SOC with Defender for Office 365 and the O365 Management API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).</span></span>

- <span data-ttu-id="62b68-112">Per ulteriori informazioni sulle API di gestione di Office 365, vedere Panoramica delle API di gestione di [Office 365.](/office/office-365-management-api/office-365-management-apis-overview)</span><span class="sxs-lookup"><span data-stu-id="62b68-112">To learn more about the Office 365 Management APIs, see [Office 365 Management APIs overview](/office/office-365-management-api/office-365-management-apis-overview).</span></span>

## <a name="how-siem-integration-works"></a><span data-ttu-id="62b68-113">Funzionamento dell'integrazione SIEM</span><span class="sxs-lookup"><span data-stu-id="62b68-113">How SIEM integration works</span></span>

<span data-ttu-id="62b68-114">L'API di gestione delle attività di Office 365 recupera informazioni su azioni ed eventi di utenti, amministratori, sistema e criteri dai log attività di Microsoft 365 e Azure Active Directory dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="62b68-114">The Office 365 Activity Management API retrieves information about user, admin, system, and policy actions and events from your organization's Microsoft 365 and Azure Active Directory activity logs.</span></span> <span data-ttu-id="62b68-115">Se l'organizzazione dispone di Microsoft Defender per Office 365 Piano 1 o 2 o Office 365 E5, è possibile usare [lo schema di Microsoft Defender per Office 365.](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)</span><span class="sxs-lookup"><span data-stu-id="62b68-115">If your organization has Microsoft Defender for Office 365 Plan 1 or 2, or Office 365 E5, you can use the [Microsoft Defender for Office 365 schema](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema).</span></span>

<span data-ttu-id="62b68-116">Di recente, gli eventi delle funzionalità di analisi e risposta automatizzate in [Microsoft Defender per Office 365 Piano 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) sono stati aggiunti all'API di attività di gestione di Office 365.</span><span class="sxs-lookup"><span data-stu-id="62b68-116">Recently, events from automated investigation and response capabilities in [Microsoft Defender for Office 365 Plan 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) were added to the Office 365 Management Activity API.</span></span> <span data-ttu-id="62b68-117">Oltre a includere dati sui dettagli dell'indagine di base, ad esempio ID, nome e stato, l'API contiene anche informazioni di alto livello sulle azioni ed entità di indagine.</span><span class="sxs-lookup"><span data-stu-id="62b68-117">In addition to including data about core investigation details such as ID, name and status, the API also contains high-level information about investigation actions and entities.</span></span>

<span data-ttu-id="62b68-118">Il server SIEM o un altro sistema simile esegue il polling del **carico di lavoro audit.general** per accedere agli eventi di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="62b68-118">The SIEM server or other similar system polls the **audit.general** workload to access detection events.</span></span> <span data-ttu-id="62b68-119">Per altre informazioni, vedere Introduzione alle API di gestione di [Office 365.](/office/office-365-management-api/get-started-with-office-365-management-apis)</span><span class="sxs-lookup"><span data-stu-id="62b68-119">To learn more, see [Get started with Office 365 Management APIs](/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span>

## <a name="enum-auditlogrecordtype---type-edmint32"></a><span data-ttu-id="62b68-120">Enumerazione: AuditLogRecordType - Tipo: Edm.Int32</span><span class="sxs-lookup"><span data-stu-id="62b68-120">Enum: AuditLogRecordType - Type: Edm.Int32</span></span>

### <a name="auditlogrecordtype"></a><span data-ttu-id="62b68-121">AuditLogRecordType</span><span class="sxs-lookup"><span data-stu-id="62b68-121">AuditLogRecordType</span></span>

<span data-ttu-id="62b68-122">Nella tabella seguente sono riepilogati i valori di **AuditLogRecordType** rilevanti per gli eventi di Microsoft Defender per Office 365:</span><span class="sxs-lookup"><span data-stu-id="62b68-122">The following table summarizes the values of **AuditLogRecordType** that are relevant for Microsoft Defender for Office 365 events:</span></span>

|<span data-ttu-id="62b68-123">Valore</span><span class="sxs-lookup"><span data-stu-id="62b68-123">Value</span></span>|<span data-ttu-id="62b68-124">Nome membro</span><span class="sxs-lookup"><span data-stu-id="62b68-124">Member name</span></span>|<span data-ttu-id="62b68-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="62b68-125">Description</span></span>|
|---|---|---|
|<span data-ttu-id="62b68-126">28</span><span class="sxs-lookup"><span data-stu-id="62b68-126">28</span></span>|<span data-ttu-id="62b68-127">ThreatIntelligence</span><span class="sxs-lookup"><span data-stu-id="62b68-127">ThreatIntelligence</span></span>|<span data-ttu-id="62b68-128">Eventi di phishing e malware da Exchange Online Protection e Microsoft Defender per Office 365.</span><span class="sxs-lookup"><span data-stu-id="62b68-128">Phishing and malware events from Exchange Online Protection and Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="62b68-129">41</span><span class="sxs-lookup"><span data-stu-id="62b68-129">41</span></span>|<span data-ttu-id="62b68-130">ThreatIntelligenceUrl</span><span class="sxs-lookup"><span data-stu-id="62b68-130">ThreatIntelligenceUrl</span></span>|<span data-ttu-id="62b68-131">Safe Links time-of-block and block override events from Microsoft Defender for Office 365.</span><span class="sxs-lookup"><span data-stu-id="62b68-131">Safe Links time-of-block and block override events from Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="62b68-132">47</span><span class="sxs-lookup"><span data-stu-id="62b68-132">47</span></span>|<span data-ttu-id="62b68-133">ThreatIntelligenceAtpContent</span><span class="sxs-lookup"><span data-stu-id="62b68-133">ThreatIntelligenceAtpContent</span></span>|<span data-ttu-id="62b68-134">Eventi di phishing e malware per i file in SharePoint Online, OneDrive for Business e Microsoft Teams, da Microsoft Defender per Office 365.</span><span class="sxs-lookup"><span data-stu-id="62b68-134">Phishing and malware events for files in SharePoint Online, OneDrive for Business, and Microsoft Teams, from Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="62b68-135">64</span><span class="sxs-lookup"><span data-stu-id="62b68-135">64</span></span>|<span data-ttu-id="62b68-136">AirInvestigation</span><span class="sxs-lookup"><span data-stu-id="62b68-136">AirInvestigation</span></span>|<span data-ttu-id="62b68-137">Eventi di indagine e risposta automatizzati, ad esempio dettagli dell'indagine e artefatti rilevanti, da Microsoft Defender per Office 365 Piano 2.</span><span class="sxs-lookup"><span data-stu-id="62b68-137">Automated investigation and response events, such as investigation details and relevant artifacts, from Microsoft Defender for Office 365 Plan 2.</span></span>|
|

> [!IMPORTANT]
> <span data-ttu-id="62b68-138">Per configurare l &'integrazione di SIEM con Microsoft Defender per Office 365, è necessario essere un amministratore globale o disporre del ruolo di amministratore della sicurezza per il Centro sicurezza e conformità.</span><span class="sxs-lookup"><span data-stu-id="62b68-138">You must be a global administrator or have the security administrator role assigned for the Security & Compliance Center to set up SIEM integration with Microsoft Defender for Office 365.</span></span>
>
> <span data-ttu-id="62b68-139">La registrazione di controllo deve essere attivata per l'ambiente Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="62b68-139">Audit logging must be turned on for your Microsoft 365 environment.</span></span> <span data-ttu-id="62b68-140">Per informazioni su questo argomento, vedere Attivare o disattivare la ricerca nel [log di controllo.](../../compliance/turn-audit-log-search-on-or-off.md)</span><span class="sxs-lookup"><span data-stu-id="62b68-140">To get help with this, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="62b68-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="62b68-141">See also</span></span>

[<span data-ttu-id="62b68-142">Analisi delle minacce e risposta alle minacce in Office 365</span><span class="sxs-lookup"><span data-stu-id="62b68-142">Office 365 threat investigation and response</span></span>](office-365-ti.md)

[<span data-ttu-id="62b68-143">Analisi e risposta automatizzate (AIR) in Office 365</span><span class="sxs-lookup"><span data-stu-id="62b68-143">Automated investigation and response (AIR) in Office 365</span></span>](automated-investigation-response-office.md)