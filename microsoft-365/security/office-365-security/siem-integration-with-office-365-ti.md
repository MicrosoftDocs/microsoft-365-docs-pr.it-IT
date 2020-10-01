---
title: Integrazione di SIEM con Advanced Threat Protection
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
- MOE150
ms.assetid: eb56b69b-3170-4086-82cf-ba40a530fa1b
ms.date: 08/21/2020
ms.collection:
- M365-security-compliance
description: Integrare il server SIEM dell'organizzazione con Office 365 Advanced Threat Protection e gli eventi relativi alle minacce correlati nell'API di gestione delle attività di Office 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 544093960570fe0e68ac47dc7bf9965fba2d30a1
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327166"
---
# <a name="siem-integration-with-advanced-threat-protection"></a><span data-ttu-id="e4033-103">Integrazione di SIEM con Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="e4033-103">SIEM integration with Advanced Threat Protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="e4033-104">Se l'organizzazione utilizza un server di gestione eventi e incidenti di sicurezza (SIEM), è possibile integrare Office 365 Advanced Threat Protection (Office 365 ATP) con il server SIEM.</span><span class="sxs-lookup"><span data-stu-id="e4033-104">If your organization is using a security incident and event management (SIEM) server, you can integrate Office 365 Advanced Threat Protection (Office 365 ATP) with your SIEM server.</span></span> <span data-ttu-id="e4033-105">È possibile configurare questa integrazione utilizzando l'API di [gestione delle attività di Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span><span class="sxs-lookup"><span data-stu-id="e4033-105">You can set up this integration by using the [Office 365 Activity Management API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span> 

<span data-ttu-id="e4033-106">L'integrazione di SIEM consente di visualizzare le informazioni, ad esempio malware o phishing rilevate da Office 365 ATP, nei report di SIEM server.</span><span class="sxs-lookup"><span data-stu-id="e4033-106">SIEM integration enables you to view information, such as malware or phish detected by Office 365 ATP, in your SIEM server reports.</span></span> 

- <span data-ttu-id="e4033-107">Per visualizzare un esempio di integrazione di SIEM con Office 365 ATP, vedere [Tech Community Blog: migliorare l'efficacia del SOC con office 365 ATP e l'API di gestione di O365](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).</span><span class="sxs-lookup"><span data-stu-id="e4033-107">To see an example of SIEM integration with Office 365 ATP, see [Tech Community blog: Improve the Effectiveness of your SOC with Office 365 ATP and the O365 Management API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).</span></span>

- <span data-ttu-id="e4033-108">Per ulteriori informazioni sulle API di gestione di Office 365, vedere [Panoramica delle API di gestione](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)di Office 365.</span><span class="sxs-lookup"><span data-stu-id="e4033-108">To learn more about the Office 365 Management APIs, see [Office 365 Management APIs overview](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview).</span></span>

## <a name="how-siem-integration-works"></a><span data-ttu-id="e4033-109">Funzionamento dell'integrazione di SIEM</span><span class="sxs-lookup"><span data-stu-id="e4033-109">How SIEM integration works</span></span>

<span data-ttu-id="e4033-110">L'API di gestione delle attività di Office 365 recupera informazioni sulle azioni e sugli eventi degli utenti, dell'amministratore, del sistema e dei criteri dai registri delle attività di Microsoft 365 e Azure Active Directory dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e4033-110">The Office 365 Activity Management API retrieves information about user, admin, system, and policy actions and events from your organization's Microsoft 365 and Azure Active Directory activity logs.</span></span> <span data-ttu-id="e4033-111">Se l'organizzazione dispone di Office 365 ATP piano 1 o 2 oppure Office 365 E5, è possibile utilizzare lo [schema ATP di office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema).</span><span class="sxs-lookup"><span data-stu-id="e4033-111">If your organization has Office 365 ATP Plan 1 or 2, or Office 365 E5, you can use the [Office 365 ATP schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema).</span></span>  

<span data-ttu-id="e4033-112">Recentemente, gli eventi provenienti da indagini automatizzate e funzionalità di risposta in [office 365 ATP piano 2](office-365-atp.md#office-365-atp-plan-1-and-plan-2) sono stati aggiunti all'API di attività di gestione di Office 365.</span><span class="sxs-lookup"><span data-stu-id="e4033-112">Recently, events from automated investigation and response capabilities in [Office 365 ATP Plan 2](office-365-atp.md#office-365-atp-plan-1-and-plan-2) were added to the Office 365 Management Activity API.</span></span> <span data-ttu-id="e4033-113">Oltre a includere i dati relativi ai dettagli dell'analisi di base, quali ID, nome e stato, l'API contiene anche informazioni di alto livello sulle azioni e sulle entità di indagine.</span><span class="sxs-lookup"><span data-stu-id="e4033-113">In addition to including data about core investigation details such as ID, name and status, the API also contains high-level information about investigation actions and entities.</span></span>

<span data-ttu-id="e4033-114">Il server SIEM o un altro sistema analogo esegue il polling del **controllo.** carico di lavoro generale per accedere agli eventi di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="e4033-114">The SIEM server or other similar system polls the **audit.general** workload to access detection events.</span></span> <span data-ttu-id="e4033-115">Per ulteriori informazioni, vedere [Introduzione a Office 365 Management Apis](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span><span class="sxs-lookup"><span data-stu-id="e4033-115">To learn more, see [Get started with Office 365 Management APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span> 

## <a name="enum-auditlogrecordtype---type-edmint32"></a><span data-ttu-id="e4033-116">Enum: AuditLogRecordType-Type: EDM. Int32</span><span class="sxs-lookup"><span data-stu-id="e4033-116">Enum: AuditLogRecordType - Type: Edm.Int32</span></span>

### <a name="auditlogrecordtype"></a><span data-ttu-id="e4033-117">AuditLogRecordType</span><span class="sxs-lookup"><span data-stu-id="e4033-117">AuditLogRecordType</span></span>

<span data-ttu-id="e4033-118">Nella tabella seguente sono riepilogati i valori di **AuditLogRecordType** rilevanti per gli eventi ATP di Office 365:</span><span class="sxs-lookup"><span data-stu-id="e4033-118">The following table summarizes the values of **AuditLogRecordType** that are relevant for Office 365 ATP events:</span></span>

|<span data-ttu-id="e4033-119">Valore</span><span class="sxs-lookup"><span data-stu-id="e4033-119">Value</span></span>|<span data-ttu-id="e4033-120">Nome membro</span><span class="sxs-lookup"><span data-stu-id="e4033-120">Member name</span></span>|<span data-ttu-id="e4033-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e4033-121">Description</span></span>|
|---|---|---|
|<span data-ttu-id="e4033-122">28</span><span class="sxs-lookup"><span data-stu-id="e4033-122">28</span></span>|<span data-ttu-id="e4033-123">ThreatIntelligence</span><span class="sxs-lookup"><span data-stu-id="e4033-123">ThreatIntelligence</span></span>|<span data-ttu-id="e4033-124">Eventi di phishing e malware da Exchange Online Protection e Office 365 ATP.</span><span class="sxs-lookup"><span data-stu-id="e4033-124">Phishing and malware events from Exchange Online Protection and Office 365 ATP.</span></span>|
|<span data-ttu-id="e4033-125">41</span><span class="sxs-lookup"><span data-stu-id="e4033-125">41</span></span>|<span data-ttu-id="e4033-126">ThreatIntelligenceUrl</span><span class="sxs-lookup"><span data-stu-id="e4033-126">ThreatIntelligenceUrl</span></span>|<span data-ttu-id="e4033-127">Collegamenti sicuri gli eventi Time-of-Block e Block override di Office 365 ATP.</span><span class="sxs-lookup"><span data-stu-id="e4033-127">Safe Links time-of-block and block override events from Office 365 ATP.</span></span>|
|<span data-ttu-id="e4033-128">47</span><span class="sxs-lookup"><span data-stu-id="e4033-128">47</span></span>|<span data-ttu-id="e4033-129">ThreatIntelligenceAtpContent</span><span class="sxs-lookup"><span data-stu-id="e4033-129">ThreatIntelligenceAtpContent</span></span>|<span data-ttu-id="e4033-130">Eventi di phishing e malware per i file in SharePoint Online, OneDrive for business e Microsoft teams, da Office 365 ATP.</span><span class="sxs-lookup"><span data-stu-id="e4033-130">Phishing and malware events for files in SharePoint Online, OneDrive for Business, and Microsoft Teams, from Office 365 ATP.</span></span>|
|<span data-ttu-id="e4033-131">64</span><span class="sxs-lookup"><span data-stu-id="e4033-131">64</span></span>|<span data-ttu-id="e4033-132">Indagine</span><span class="sxs-lookup"><span data-stu-id="e4033-132">AirInvestigation</span></span>|<span data-ttu-id="e4033-133">Eventi di analisi e di risposta automatizzati, ad esempio i dettagli dell'indagine e gli elementi rilevanti, da Office 365 ATP piano 2.</span><span class="sxs-lookup"><span data-stu-id="e4033-133">Automated investigation and response events, such as investigation details and relevant artifacts, from Office 365 ATP Plan 2.</span></span>|
|

> [!IMPORTANT]
> <span data-ttu-id="e4033-134">È necessario essere un amministratore globale o disporre del ruolo di amministratore della sicurezza assegnato per il Centro sicurezza & Compliance per configurare l'integrazione di SIEM con Office 365 Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="e4033-134">You must be a global administrator or have the security administrator role assigned for the Security & Compliance Center to set up SIEM integration with Office 365 Advanced Threat Protection.</span></span><br/><span data-ttu-id="e4033-135">La registrazione di controllo deve essere attivata per l'ambiente Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e4033-135">Audit logging must be turned on for your Microsoft 365 environment.</span></span> <span data-ttu-id="e4033-136">Per ottenere assistenza, vedere [attivazione o disattivazione della ricerca dei log di controllo](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="e4033-136">To get help with this, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e4033-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e4033-137">See also</span></span>

[<span data-ttu-id="e4033-138">Analisi delle minacce e risposta alle minacce in Office 365</span><span class="sxs-lookup"><span data-stu-id="e4033-138">Office 365 threat investigation and response</span></span>](office-365-ti.md)

[<span data-ttu-id="e4033-139">Indagine automatizzata e risposta (AIR) in Office 365</span><span class="sxs-lookup"><span data-stu-id="e4033-139">Automated investigation and response (AIR) in Office 365</span></span>](automated-investigation-response-office.md)


