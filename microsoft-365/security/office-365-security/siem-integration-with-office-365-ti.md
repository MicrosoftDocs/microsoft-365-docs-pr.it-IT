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
ms.date: 11/22/2019
ms.collection:
- M365-security-compliance
description: Integrare il server SIEM dell'organizzazione con Office 365 Advanced Threat Protection e gli eventi relativi alle minacce correlati nell'API di gestione delle attività di Office 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0527a998e7049960df840c7756ef5deaafaf5ade
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035273"
---
# <a name="siem-integration-with-advanced-threat-protection"></a><span data-ttu-id="3ccba-103">Integrazione di SIEM con Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="3ccba-103">SIEM integration with Advanced Threat Protection</span></span>

<span data-ttu-id="3ccba-104">Se l'organizzazione utilizza un server di gestione eventi e incidenti di sicurezza (SIEM), è possibile integrare Office 365 Advanced Threat Protection con il server SIEM.</span><span class="sxs-lookup"><span data-stu-id="3ccba-104">If your organization is using a security incident and event management (SIEM) server, you can integrate Office 365 Advanced Threat Protection with your SIEM server.</span></span> <span data-ttu-id="3ccba-105">L'integrazione di SIEM consente di visualizzare le informazioni, ad esempio malware o phishing rilevate da Office 365 Advanced Protection, nei report di SIEM server.</span><span class="sxs-lookup"><span data-stu-id="3ccba-105">SIEM integration enables you to view information, such as malware or phish detected by Office 365 Advanced Protection, in your SIEM server reports.</span></span> <span data-ttu-id="3ccba-106">Per configurare l'integrazione di SIEM, è possibile utilizzare l' [API di gestione delle attività di Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span><span class="sxs-lookup"><span data-stu-id="3ccba-106">To set up SIEM integration, you use the [Office 365 Activity Management API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span> 

<span data-ttu-id="3ccba-107">L'API di gestione delle attività di Office 365 recupera informazioni sulle azioni e sugli eventi degli utenti, dell'amministratore, del sistema e dei criteri dai registri delle attività di Microsoft 365 per le aziende e di Azure Active Directory dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3ccba-107">The Office 365 Activity Management API retrieves information about user, admin, system, and policy actions and events from your organization's Microsoft 365 for business and Azure Active Directory activity logs.</span></span> <span data-ttu-id="3ccba-108">Lo [schema office 365 Advanced Threat Protection](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) è compatibile con Advanced Threat Protection, quindi se l'organizzazione dispone di Office 365 Advanced Threat Protection Plan 1 o Plan 2 o Office 365 E5, è comunque possibile utilizzare la stessa API per l'integrazione del server Siem.</span><span class="sxs-lookup"><span data-stu-id="3ccba-108">The [Office 365 Advanced Threat Protection schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) works with Advanced Threat Protection, so if your organization has the Office 365 Advanced Threat Protection Plan 1 or Plan 2 or Office 365 E5, you can still use that same API for your SIEM server integration.</span></span> 

<span data-ttu-id="3ccba-109">Come parte degli aggiornamenti più recenti, sono stati aggiunti anche eventi provenienti da funzionalità di analisi e risposta automatizzate in Office 365 ATP Plan 2 all'interno dell'API di gestione di Office 365 Management.</span><span class="sxs-lookup"><span data-stu-id="3ccba-109">As part of our recent updates, we have also added events from automated investigation and response capabilities in Office 365 ATP Plan 2 within the Office 365 Management Activity API.</span></span> <span data-ttu-id="3ccba-110">Oltre a includere i dati relativi ai dettagli relativi alle indagini di base, quali ID, nome e stato, contiene anche informazioni di alto livello sulle azioni e sulle entità di indagine.</span><span class="sxs-lookup"><span data-stu-id="3ccba-110">In addition to including data about core investigation details such as ID, name and status, it also contains high-level information about investigation actions and entities.</span></span>   

<span data-ttu-id="3ccba-111">Il server SIEM o un altro sistema analogo deve eseguire il polling del carico di lavoro **generale** per accedere agli eventi di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="3ccba-111">The SIEM server or other similar system should poll the **audit.general** workload to access detection events.</span></span> <span data-ttu-id="3ccba-112">Per ulteriori informazioni, vedere [Introduzione alle API di gestione di Office 365](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span><span class="sxs-lookup"><span data-stu-id="3ccba-112">To learn more see [Get started with Office 365 Management APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span> <span data-ttu-id="3ccba-113">Inoltre, i seguenti valori di **AuditLogRecordType** sono rilevanti per gli eventi ATP di Office 365:</span><span class="sxs-lookup"><span data-stu-id="3ccba-113">In addition, the following values of **AuditLogRecordType** are relevant for Office 365 ATP events:</span></span>

### <a name="enum-auditlogrecordtype---type-edmint32"></a><span data-ttu-id="3ccba-114">Enum: AuditLogRecordType-Type: EDM. Int32</span><span class="sxs-lookup"><span data-stu-id="3ccba-114">Enum: AuditLogRecordType - Type: Edm.Int32</span></span>

#### <a name="auditlogrecordtype"></a><span data-ttu-id="3ccba-115">AuditLogRecordType</span><span class="sxs-lookup"><span data-stu-id="3ccba-115">AuditLogRecordType</span></span>

|<span data-ttu-id="3ccba-116">Valore</span><span class="sxs-lookup"><span data-stu-id="3ccba-116">Value</span></span>|<span data-ttu-id="3ccba-117">Nome membro</span><span class="sxs-lookup"><span data-stu-id="3ccba-117">Member name</span></span>|<span data-ttu-id="3ccba-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3ccba-118">Description</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3ccba-119">28</span><span class="sxs-lookup"><span data-stu-id="3ccba-119">28</span></span>|<span data-ttu-id="3ccba-120">ThreatIntelligence</span><span class="sxs-lookup"><span data-stu-id="3ccba-120">ThreatIntelligence</span></span>|<span data-ttu-id="3ccba-121">Eventi di phishing e malware da Exchange Online Protection e Office 365 Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="3ccba-121">Phishing and malware events from Exchange Online Protection and Office 365 Advanced Threat Protection.</span></span>|
|<span data-ttu-id="3ccba-122">41</span><span class="sxs-lookup"><span data-stu-id="3ccba-122">41</span></span>|<span data-ttu-id="3ccba-123">ThreatIntelligenceUrl</span><span class="sxs-lookup"><span data-stu-id="3ccba-123">ThreatIntelligenceUrl</span></span>|<span data-ttu-id="3ccba-124">Collegamenti sicuri ATP gli eventi Time-of-Block e Block override di Office 365 Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="3ccba-124">ATP Safe Links time-of-block and block override events from Office 365 Advanced Threat Protection.</span></span>|
|<span data-ttu-id="3ccba-125">47</span><span class="sxs-lookup"><span data-stu-id="3ccba-125">47</span></span>|<span data-ttu-id="3ccba-126">ThreatIntelligenceAtpContent</span><span class="sxs-lookup"><span data-stu-id="3ccba-126">ThreatIntelligenceAtpContent</span></span>|<span data-ttu-id="3ccba-127">Eventi di phishing e malware per i file in SharePoint Online, OneDrive for business e Microsoft teams dalla protezione avanzata dalle minacce di Office 365.</span><span class="sxs-lookup"><span data-stu-id="3ccba-127">Phishing and malware events for files in SharePoint Online, OneDrive for Business, and Microsoft Teams from Office 365 Advanced Threat Protection.</span></span>|
|<span data-ttu-id="3ccba-128">64</span><span class="sxs-lookup"><span data-stu-id="3ccba-128">64</span></span>|<span data-ttu-id="3ccba-129">Indagine</span><span class="sxs-lookup"><span data-stu-id="3ccba-129">AirInvestigation</span></span>|<span data-ttu-id="3ccba-130">Eventi di ricerca e di risposta automatizzati, ad esempio i dettagli dell'indagine e gli elementi rilevanti di Office 365 Advanced Threat Protection Plan 2.</span><span class="sxs-lookup"><span data-stu-id="3ccba-130">Automated investigation and response events, such as investigation details and relevant artifacts from Office 365 Advanced Threat Protection Plan 2.</span></span>|


> [!IMPORTANT]
> <span data-ttu-id="3ccba-131">È necessario essere un amministratore globale o disporre del ruolo di amministratore della sicurezza assegnato per il Centro sicurezza & Compliance per configurare l'integrazione di SIEM con Office 365 Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="3ccba-131">You must be a global administrator or have the security administrator role assigned for the Security & Compliance Center to set up SIEM integration with Office 365 Advanced Threat Protection.</span></span><br/><span data-ttu-id="3ccba-132">La registrazione di controllo deve essere attivata per l'ambiente Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3ccba-132">Audit logging must be turned on for your Microsoft 365 environment.</span></span> <span data-ttu-id="3ccba-133">Per ottenere assistenza, vedere [attivazione o disattivazione della ricerca dei log di controllo](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="3ccba-133">To get help with this, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="3ccba-134">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="3ccba-134">Related topics</span></span>

[<span data-ttu-id="3ccba-135">Analisi delle minacce e risposta alle minacce in Office 365</span><span class="sxs-lookup"><span data-stu-id="3ccba-135">Office 365 threat investigation and response</span></span>](office-365-ti.md)

[<span data-ttu-id="3ccba-136">Indagine automatizzata e risposta (AIR) in Office 365</span><span class="sxs-lookup"><span data-stu-id="3ccba-136">Automated investigation and response (AIR) in Office 365</span></span>](automated-investigation-response-office.md)

[<span data-ttu-id="3ccba-137">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="3ccba-137">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)

[<span data-ttu-id="3ccba-138">Smart report e informazioni dettagliate nel centro sicurezza &amp; e conformità</span><span class="sxs-lookup"><span data-stu-id="3ccba-138">Smart reports and insights in the Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="3ccba-139">Autorizzazioni nel centro sicurezza &amp; e conformità</span><span class="sxs-lookup"><span data-stu-id="3ccba-139">Permissions in the Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
  
