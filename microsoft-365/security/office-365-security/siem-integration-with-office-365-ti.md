---
title: Integrazione di SIEM con Microsoft Defender per Office 365
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
description: Integrare il server SIEM dell'organizzazione con Microsoft Defender per Office 365 e gli eventi relativi alle minacce correlate nell'API di gestione delle attività di Office 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6253ed0133bf53bdbeca71bb595a850e25441311
ms.sourcegitcommit: 4debeb8f0fce67f361676340fc390f1b283a3069
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/03/2020
ms.locfileid: "49561706"
---
# <a name="siem-integration-with-microsoft-defender-for-office-365"></a><span data-ttu-id="24f9f-103">Integrazione di SIEM con Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="24f9f-103">SIEM integration with Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="24f9f-104">Se l'organizzazione utilizza un server di gestione eventi e informazioni di sicurezza (SIEM), è possibile integrare Microsoft Defender per Office 365 con il server SIEM.</span><span class="sxs-lookup"><span data-stu-id="24f9f-104">If your organization is using a security information and event management (SIEM) server, you can integrate Microsoft Defender for Office 365 with your SIEM server.</span></span> <span data-ttu-id="24f9f-105">È possibile configurare questa integrazione utilizzando l'API di [gestione delle attività di Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span><span class="sxs-lookup"><span data-stu-id="24f9f-105">You can set up this integration by using the [Office 365 Activity Management API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span>

<span data-ttu-id="24f9f-106">L'integrazione di SIEM consente di visualizzare le informazioni, ad esempio malware o phishing rilevate da Microsoft Defender per Office 365, nei report di SIEM server.</span><span class="sxs-lookup"><span data-stu-id="24f9f-106">SIEM integration enables you to view information, such as malware or phish detected by Microsoft Defender for Office 365, in your SIEM server reports.</span></span>

- <span data-ttu-id="24f9f-107">Per visualizzare un esempio di integrazione di SIEM con Microsoft Defender per Office 365, vedere [Tech Community Blog: migliorare l'efficacia del SOC con Defender per office 365 e l'API di gestione di O365](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).</span><span class="sxs-lookup"><span data-stu-id="24f9f-107">To see an example of SIEM integration with Microsoft Defender for Office 365, see [Tech Community blog: Improve the Effectiveness of your SOC with Defender for Office 365 and the O365 Management API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).</span></span>

- <span data-ttu-id="24f9f-108">Per ulteriori informazioni sulle API di gestione di Office 365, vedere [Panoramica delle API di gestione](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)di Office 365.</span><span class="sxs-lookup"><span data-stu-id="24f9f-108">To learn more about the Office 365 Management APIs, see [Office 365 Management APIs overview](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview).</span></span>

## <a name="how-siem-integration-works"></a><span data-ttu-id="24f9f-109">Funzionamento dell'integrazione di SIEM</span><span class="sxs-lookup"><span data-stu-id="24f9f-109">How SIEM integration works</span></span>

<span data-ttu-id="24f9f-110">L'API di gestione delle attività di Office 365 recupera informazioni sulle azioni e sugli eventi degli utenti, dell'amministratore, del sistema e dei criteri dai registri delle attività di Microsoft 365 e Azure Active Directory dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="24f9f-110">The Office 365 Activity Management API retrieves information about user, admin, system, and policy actions and events from your organization's Microsoft 365 and Azure Active Directory activity logs.</span></span> <span data-ttu-id="24f9f-111">Se l'organizzazione dispone di Microsoft Defender per Office 365 piano 1 o 2 o Office 365 E5, è possibile utilizzare lo [schema Microsoft Defender per office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema).</span><span class="sxs-lookup"><span data-stu-id="24f9f-111">If your organization has Microsoft Defender for Office 365 Plan 1 or 2, or Office 365 E5, you can use the [Microsoft Defender for Office 365 schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema).</span></span>

<span data-ttu-id="24f9f-112">Recentemente, gli eventi provenienti da indagini automatizzate e funzionalità di risposta in [Microsoft Defender per office 365 piano 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) sono stati aggiunti all'API di attività di gestione di Office 365.</span><span class="sxs-lookup"><span data-stu-id="24f9f-112">Recently, events from automated investigation and response capabilities in [Microsoft Defender for Office 365 Plan 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) were added to the Office 365 Management Activity API.</span></span> <span data-ttu-id="24f9f-113">Oltre a includere i dati relativi ai dettagli dell'analisi di base, quali ID, nome e stato, l'API contiene anche informazioni di alto livello sulle azioni e sulle entità di indagine.</span><span class="sxs-lookup"><span data-stu-id="24f9f-113">In addition to including data about core investigation details such as ID, name and status, the API also contains high-level information about investigation actions and entities.</span></span>

<span data-ttu-id="24f9f-114">Il server SIEM o un altro sistema analogo esegue il polling del **controllo.** carico di lavoro generale per accedere agli eventi di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="24f9f-114">The SIEM server or other similar system polls the **audit.general** workload to access detection events.</span></span> <span data-ttu-id="24f9f-115">Per ulteriori informazioni, vedere [Introduzione a Office 365 Management Apis](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span><span class="sxs-lookup"><span data-stu-id="24f9f-115">To learn more, see [Get started with Office 365 Management APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span>

## <a name="enum-auditlogrecordtype---type-edmint32"></a><span data-ttu-id="24f9f-116">Enum: AuditLogRecordType-Type: EDM. Int32</span><span class="sxs-lookup"><span data-stu-id="24f9f-116">Enum: AuditLogRecordType - Type: Edm.Int32</span></span>

### <a name="auditlogrecordtype"></a><span data-ttu-id="24f9f-117">AuditLogRecordType</span><span class="sxs-lookup"><span data-stu-id="24f9f-117">AuditLogRecordType</span></span>

<span data-ttu-id="24f9f-118">Nella tabella seguente sono riepilogati i valori di **AuditLogRecordType** rilevanti per gli eventi di Microsoft Defender per Office 365:</span><span class="sxs-lookup"><span data-stu-id="24f9f-118">The following table summarizes the values of **AuditLogRecordType** that are relevant for Microsoft Defender for Office 365 events:</span></span>

|<span data-ttu-id="24f9f-119">Valore</span><span class="sxs-lookup"><span data-stu-id="24f9f-119">Value</span></span>|<span data-ttu-id="24f9f-120">Nome membro</span><span class="sxs-lookup"><span data-stu-id="24f9f-120">Member name</span></span>|<span data-ttu-id="24f9f-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="24f9f-121">Description</span></span>|
|---|---|---|
|<span data-ttu-id="24f9f-122">28</span><span class="sxs-lookup"><span data-stu-id="24f9f-122">28</span></span>|<span data-ttu-id="24f9f-123">ThreatIntelligence</span><span class="sxs-lookup"><span data-stu-id="24f9f-123">ThreatIntelligence</span></span>|<span data-ttu-id="24f9f-124">Eventi di phishing e malware da Exchange Online Protection e Microsoft Defender per Office 365.</span><span class="sxs-lookup"><span data-stu-id="24f9f-124">Phishing and malware events from Exchange Online Protection and Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="24f9f-125">41</span><span class="sxs-lookup"><span data-stu-id="24f9f-125">41</span></span>|<span data-ttu-id="24f9f-126">ThreatIntelligenceUrl</span><span class="sxs-lookup"><span data-stu-id="24f9f-126">ThreatIntelligenceUrl</span></span>|<span data-ttu-id="24f9f-127">Collegamenti sicuri gli eventi Time-of-Block e Block override di Microsoft Defender per Office 365.</span><span class="sxs-lookup"><span data-stu-id="24f9f-127">Safe Links time-of-block and block override events from Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="24f9f-128">47</span><span class="sxs-lookup"><span data-stu-id="24f9f-128">47</span></span>|<span data-ttu-id="24f9f-129">ThreatIntelligenceAtpContent</span><span class="sxs-lookup"><span data-stu-id="24f9f-129">ThreatIntelligenceAtpContent</span></span>|<span data-ttu-id="24f9f-130">Eventi di phishing e malware per i file in SharePoint Online, OneDrive for business e Microsoft teams, da Microsoft Defender per Office 365.</span><span class="sxs-lookup"><span data-stu-id="24f9f-130">Phishing and malware events for files in SharePoint Online, OneDrive for Business, and Microsoft Teams, from Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="24f9f-131">64</span><span class="sxs-lookup"><span data-stu-id="24f9f-131">64</span></span>|<span data-ttu-id="24f9f-132">Indagine</span><span class="sxs-lookup"><span data-stu-id="24f9f-132">AirInvestigation</span></span>|<span data-ttu-id="24f9f-133">Eventi di analisi e di risposta automatizzati, ad esempio i dettagli dell'indagine e gli elementi rilevanti, da Microsoft Defender per Office 365 piano 2.</span><span class="sxs-lookup"><span data-stu-id="24f9f-133">Automated investigation and response events, such as investigation details and relevant artifacts, from Microsoft Defender for Office 365 Plan 2.</span></span>|
|

> [!IMPORTANT]
> <span data-ttu-id="24f9f-134">È necessario essere un amministratore globale o disporre del ruolo di amministratore della sicurezza assegnato per il Centro sicurezza & Compliance per configurare l'integrazione di SIEM con Microsoft Defender per Office 365.</span><span class="sxs-lookup"><span data-stu-id="24f9f-134">You must be a global administrator or have the security administrator role assigned for the Security & Compliance Center to set up SIEM integration with Microsoft Defender for Office 365.</span></span><br/><span data-ttu-id="24f9f-135">La registrazione di controllo deve essere attivata per l'ambiente Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="24f9f-135">Audit logging must be turned on for your Microsoft 365 environment.</span></span> <span data-ttu-id="24f9f-136">Per ottenere assistenza, vedere [attivazione o disattivazione della ricerca dei log di controllo](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="24f9f-136">To get help with this, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="24f9f-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="24f9f-137">See also</span></span>

[<span data-ttu-id="24f9f-138">Analisi delle minacce e risposta alle minacce in Office 365</span><span class="sxs-lookup"><span data-stu-id="24f9f-138">Office 365 threat investigation and response</span></span>](office-365-ti.md)

[<span data-ttu-id="24f9f-139">Indagine automatizzata e risposta (AIR) in Office 365</span><span class="sxs-lookup"><span data-stu-id="24f9f-139">Automated investigation and response (AIR) in Office 365</span></span>](automated-investigation-response-office.md)

