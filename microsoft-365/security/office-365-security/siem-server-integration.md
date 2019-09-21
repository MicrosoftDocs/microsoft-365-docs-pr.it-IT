---
title: Integrazione del server SIEM con Microsoft 365
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 06/17/2019
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
description: "Riepilogo: leggere questo articolo per ottenere una panoramica dell'integrazione del server SIEM con Microsoft 365."
ms.openlocfilehash: 97f1c1d1f1862d140e014b4460ac9f40cb1934bb
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37084845"
---
# <a name="siem-server-integration-with-microsoft-365-services-and-applications"></a><span data-ttu-id="42f00-103">Integrazione del server SIEM con i servizi e le applicazioni di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="42f00-103">SIEM server integration with Microsoft 365 services and applications</span></span>

## <a name="overview"></a><span data-ttu-id="42f00-104">Panoramica</span><span class="sxs-lookup"><span data-stu-id="42f00-104">Overview</span></span>

<span data-ttu-id="42f00-105">Se l'organizzazione utilizza un server di gestione eventi e informazioni di sicurezza (SIEM) o se si prevede di ottenere un server SIEM al più presto, potrebbe essere utile sapere come si integrerà con Microsoft 365, tra cui Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="42f00-105">If your organization is using a Security Information and Event Management (SIEM) server, or if you are planning to get a SIEM server soon, you might be wondering how that'll integrate with your Microsoft 365, including Office 365 E5.</span></span> <span data-ttu-id="42f00-106">Se è necessario un server SIEM dipende da molti fattori, ad esempio i requisiti di sicurezza dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="42f00-106">Whether you need a SIEM server depends on many factors, such as your organization's security requirements.</span></span> <span data-ttu-id="42f00-107">Microsoft 365 offre una vasta gamma di funzionalità di sicurezza; Tuttavia, se l'organizzazione dispone di contenuto e applicazioni in locale e nel cloud (come nel caso di una distribuzione di cloud ibrido), è possibile valutare l'aggiunta di un server SIEM per una maggiore protezione.</span><span class="sxs-lookup"><span data-stu-id="42f00-107">Microsoft 365 offers a variety of security features; however, if your organization has content and applications on premises and in the cloud (as in the case of a hybrid cloud deployment), you might consider adding a SIEM server for extra protection.</span></span> <span data-ttu-id="42f00-108">In alternativa, se l'organizzazione ha requisiti di sicurezza particolarmente severi che è necessario soddisfare, è consigliabile aggiungere un server SIEM all'ambiente.</span><span class="sxs-lookup"><span data-stu-id="42f00-108">Or, if your organization has particularly stringent security requirements you must meet, you might consider adding a SIEM server to your environment.</span></span>

## <a name="siem-server-integration-microsoft-365"></a><span data-ttu-id="42f00-109">Integrazione di server SIEM Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="42f00-109">SIEM server integration Microsoft 365</span></span>

<span data-ttu-id="42f00-110">Un server SIEM può ricevere dati da un'ampia gamma di servizi e applicazioni di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="42f00-110">A SIEM server can receive data from a wide variety of Microsoft 365 services and applications.</span></span> <span data-ttu-id="42f00-111">Nella tabella seguente sono elencati diversi servizi e applicazioni di Microsoft 365 insieme agli input del server SIEM e dove andare per ulteriori informazioni sull'integrazione del server SIEM.</span><span class="sxs-lookup"><span data-stu-id="42f00-111">The following table lists several Microsoft 365 services and applications along with SIEM server inputs and where to go to learn more about SIEM server integration.</span></span> 

| <span data-ttu-id="42f00-112">Servizio o applicazione Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="42f00-112">Microsoft 365 Service or Application</span></span> | <span data-ttu-id="42f00-113">Input del server SIEM</span><span class="sxs-lookup"><span data-stu-id="42f00-113">SIEM server inputs</span></span> | <span data-ttu-id="42f00-114">Risorse per ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="42f00-114">Resources to learn more</span></span> |
| --- | --- | --- |
| [<span data-ttu-id="42f00-115">Protezione avanzata dalle minacce di Office 365</span><span class="sxs-lookup"><span data-stu-id="42f00-115">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md) <br/><span data-ttu-id="42f00-116">oppure</span><span class="sxs-lookup"><span data-stu-id="42f00-116">or</span></span><br/>[<span data-ttu-id="42f00-117">Office 365 Threat Intelligence</span><span class="sxs-lookup"><span data-stu-id="42f00-117">Office 365 Threat Intelligence</span></span>](office-365-ti.md) | <span data-ttu-id="42f00-118">Registri di controllo</span><span class="sxs-lookup"><span data-stu-id="42f00-118">Audit logs</span></span> | [<span data-ttu-id="42f00-119">Integrazione di SIEM con Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="42f00-119">SIEM integration with Office 365 Advanced Threat Protection</span></span>](siem-integration-with-office-365-ti.md) |
| [<span data-ttu-id="42f00-120">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="42f00-120">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) | <span data-ttu-id="42f00-121">Integrazione del registro</span><span class="sxs-lookup"><span data-stu-id="42f00-121">Log integration</span></span> | [<span data-ttu-id="42f00-122">Integrazione di SIEM con Microsoft cloud app Security</span><span class="sxs-lookup"><span data-stu-id="42f00-122">SIEM integration with Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/siem) |
| [<span data-ttu-id="42f00-123">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="42f00-123">Microsoft Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/) | <span data-ttu-id="42f00-124">Integrazione del registro</span><span class="sxs-lookup"><span data-stu-id="42f00-124">Log integration</span></span> | [<span data-ttu-id="42f00-125">Tirare gli avvisi agli strumenti di SIEM</span><span class="sxs-lookup"><span data-stu-id="42f00-125">Pull alerts to your SIEM tools</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem) |
| <span data-ttu-id="42f00-126">[Centro sicurezza di Azure](https://docs.microsoft.com/azure/security-center/security-center-intro) (Protezione dalle minacce e rilevamento delle minacce)</span><span class="sxs-lookup"><span data-stu-id="42f00-126">[Azure Security Center](https://docs.microsoft.com/azure/security-center/security-center-intro) (Threat Protection and Threat Detection)</span></span> | <span data-ttu-id="42f00-127">Avvisi</span><span class="sxs-lookup"><span data-stu-id="42f00-127">Alerts</span></span> | [<span data-ttu-id="42f00-128">Esportazione dei dati di sicurezza di Azure nella configurazione di SIEM-pipeline-anteprima</span><span class="sxs-lookup"><span data-stu-id="42f00-128">Azure Security data export to SIEM - Pipeline Configuration - Preview</span></span>](https://docs.microsoft.com/azure/security-center/security-center-export-data-to-siem) |
|[<span data-ttu-id="42f00-129">Analisi avanzata delle minacce di Azure</span><span class="sxs-lookup"><span data-stu-id="42f00-129">Azure Advanced Threat Analytics</span></span>](https://docs.microsoft.com/azure/security/azure-threat-detection) | <span data-ttu-id="42f00-130">Monitor di Azure</span><span class="sxs-lookup"><span data-stu-id="42f00-130">Azure Monitor</span></span> | [<span data-ttu-id="42f00-131">Blog Utilizzo di Azure monitor per l'integrazione con gli strumenti di SIEM</span><span class="sxs-lookup"><span data-stu-id="42f00-131">(Blog) Use Azure Monitor to integrate with SIEM tools</span></span>](https://azure.microsoft.com/blog/use-azure-monitor-to-integrate-with-siem-tools) |
|[<span data-ttu-id="42f00-132">Protezione dell'identità di Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="42f00-132">Azure Active Directory Identity Protection</span></span>](https://docs.microsoft.com/azure/active-directory/identity-protection/overview) |<span data-ttu-id="42f00-133">Integrazione del registro</span><span class="sxs-lookup"><span data-stu-id="42f00-133">Log integration</span></span> |[<span data-ttu-id="42f00-134">Integrare gli avvisi dell'API di sicurezza di Microsoft Graph con un SIEM</span><span class="sxs-lookup"><span data-stu-id="42f00-134">Integrate Microsoft Graph Security API alerts with a SIEM</span></span>](https://docs.microsoft.com/graph/security-siemintegration) |


## <a name="audit-logging-must-be-turned-on"></a><span data-ttu-id="42f00-135">La registrazione di controllo deve essere attivata</span><span class="sxs-lookup"><span data-stu-id="42f00-135">Audit logging must be turned on</span></span>

<span data-ttu-id="42f00-136">Verificare che la registrazione di controllo sia attivata prima di configurare l'integrazione del server SIEM.</span><span class="sxs-lookup"><span data-stu-id="42f00-136">Make sure audit logging is turned on before you configure SIEM server integration.</span></span> 

- <span data-ttu-id="42f00-137">Per SharePoint Online, OneDrive for business e Azure Active Directory, [la registrazione di controllo è attivata nel centro sicurezza & conformità](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off).</span><span class="sxs-lookup"><span data-stu-id="42f00-137">For SharePoint Online, OneDrive for Business, and Azure Active Directory, [audit logging is turned on in the Security & Compliance Center](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off).</span></span>

- <span data-ttu-id="42f00-138">Per Exchange Online, la [registrazione di controllo è attivata con Windows PowerShell](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing).</span><span class="sxs-lookup"><span data-stu-id="42f00-138">For Exchange Online, [audit logging is turned on with Windows PowerShell](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing).</span></span>
 
## <a name="see-also"></a><span data-ttu-id="42f00-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="42f00-139">See Also</span></span>

[<span data-ttu-id="42f00-140">Adozione del cloud e soluzioni ibride</span><span class="sxs-lookup"><span data-stu-id="42f00-140">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
  
[<span data-ttu-id="42f00-141">Test Lab Guide (TLG) per l’adozione del cloud</span><span class="sxs-lookup"><span data-stu-id="42f00-141">Cloud adoption Test Lab Guides (TLGs)</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-test-lab-guides-tlgs)


