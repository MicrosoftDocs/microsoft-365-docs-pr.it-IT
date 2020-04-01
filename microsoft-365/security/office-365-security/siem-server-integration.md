---
title: " Integrazione del server di sicurezza e di gestione eventi (SIEM) con i servizi e le applicazioni Microsoft 365"
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/18/2019
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
description: Ottenere una panoramica delle informazioni di sicurezza e dell'integrazione del server di gestione eventi (SIEM) con i servizi e le applicazioni cloud di Microsoft 365
ms.openlocfilehash: a4ef144d02ebf0481481861c3dfa60a43b4f3ace
ms.sourcegitcommit: a7b2cd892cb65a61ee246268e1af2f8b9e526f6b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2020
ms.locfileid: "43081221"
---
# <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a><span data-ttu-id="aff23-103">Integrazione del server di sicurezza e di gestione eventi (SIEM) con i servizi e le applicazioni Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="aff23-103">Security Information and Event Management (SIEM) server integration with Microsoft 365 services and applications</span></span>

## <a name="summary"></a><span data-ttu-id="aff23-104">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="aff23-104">Summary</span></span>

<span data-ttu-id="aff23-105">L'organizzazione utilizza o pianifica la pianificazione per ottenere un server di gestione eventi e informazioni di sicurezza (SIEM)?</span><span class="sxs-lookup"><span data-stu-id="aff23-105">Is your organization using or planning to get a Security Information and Event Management (SIEM) server?</span></span> <span data-ttu-id="aff23-106">Potrebbe essere utile sapere come si integra con Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="aff23-106">You might be wondering how it integrates with Microsoft 365 or Office 365.</span></span> <span data-ttu-id="aff23-107">In questo articolo viene fornito un elenco delle risorse che è possibile utilizzare per integrare il server SIEM con i servizi e le applicazioni di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="aff23-107">This article provides a list of resources you can use to integrate your SIEM server with Microsoft 365 services and applications.</span></span>

> [!TIP]
> <span data-ttu-id="aff23-108">Se non si dispone ancora di un server SIEM e si esplorano le opzioni, prendere in considerazione **[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)**.</span><span class="sxs-lookup"><span data-stu-id="aff23-108">If you don't have a SIEM server yet and are exploring your options, consider **[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)**.</span></span>

## <a name="do-i-need-a-siem-server"></a><span data-ttu-id="aff23-109">È necessario un server SIEM?</span><span class="sxs-lookup"><span data-stu-id="aff23-109">Do I need a SIEM server?</span></span>

<span data-ttu-id="aff23-110">Se è necessario un server SIEM dipende da molti fattori, ad esempio i requisiti di sicurezza dell'organizzazione e il luogo in cui si trovano i dati.</span><span class="sxs-lookup"><span data-stu-id="aff23-110">Whether you need a SIEM server depends on many factors, such as your organization's security requirements and where your data resides.</span></span> <span data-ttu-id="aff23-111">Microsoft 365 include una vasta gamma di funzionalità di sicurezza che soddisfano le esigenze di sicurezza di molte organizzazioni senza server aggiuntivi, ad esempio un server SIEM.</span><span class="sxs-lookup"><span data-stu-id="aff23-111">Microsoft 365 includes a wide variety of security features that meet many organizations' security needs without additional servers, such as a SIEM server.</span></span> <span data-ttu-id="aff23-112">Alcune organizzazioni presentano circostanze speciali che richiedono l'utilizzo di un server SIEM.</span><span class="sxs-lookup"><span data-stu-id="aff23-112">Some organizations have special circumstances that require the use of a SIEM server.</span></span> <span data-ttu-id="aff23-113">Ecco alcuni esempi:</span><span class="sxs-lookup"><span data-stu-id="aff23-113">Here are some examples:</span></span>

- <span data-ttu-id="aff23-114">In *Fabrikam* sono disponibili contenuto e applicazioni in locale e alcuni nel cloud (dispongono di una distribuzione di cloud ibrido).</span><span class="sxs-lookup"><span data-stu-id="aff23-114">*Fabrikam* has some content and applications on premises, and some in the cloud (they have a hybrid cloud deployment).</span></span> <span data-ttu-id="aff23-115">Per ottenere i rapporti sulla sicurezza tra tutti i contenuti e le applicazioni, Fabrikam ha implementato un server SIEM.</span><span class="sxs-lookup"><span data-stu-id="aff23-115">To get security reports across all their content and applications, Fabrikam has implemented a SIEM server.</span></span>

- <span data-ttu-id="aff23-116">*Contoso* è un'organizzazione per i servizi finanziari con requisiti di sicurezza particolarmente severi.</span><span class="sxs-lookup"><span data-stu-id="aff23-116">*Contoso* is a financial services organization that has particularly stringent security requirements.</span></span> <span data-ttu-id="aff23-117">Sono stati aggiunti un server SIEM all'ambiente per usufruire della protezione di sicurezza aggiuntiva necessaria.</span><span class="sxs-lookup"><span data-stu-id="aff23-117">They have added a SIEM server to their environment to take advantage of the extra security protection they require.</span></span>

## <a name="siem-server-integration-with-microsoft-365"></a><span data-ttu-id="aff23-118">Integrazione del server SIEM con Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="aff23-118">SIEM server integration with Microsoft 365</span></span>

<span data-ttu-id="aff23-119">Un server SIEM può ricevere dati da un'ampia gamma di servizi e applicazioni di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="aff23-119">A SIEM server can receive data from a wide variety of Microsoft 365 services and applications.</span></span> <span data-ttu-id="aff23-120">Nella tabella seguente sono elencati diversi servizi e applicazioni di Microsoft 365, oltre a fattori di input e risorse del server SIEM per ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="aff23-120">The following table lists several Microsoft 365 services and applications, along with SIEM server inputs and resources to learn more.</span></span>

||||
|---|---|---|
|<span data-ttu-id="aff23-121">**Servizio o applicazione Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="aff23-121">**Microsoft 365 Service or Application**</span></span>|<span data-ttu-id="aff23-122">**Input/metodi del server SIEM**</span><span class="sxs-lookup"><span data-stu-id="aff23-122">**SIEM server inputs/methods**</span></span>|<span data-ttu-id="aff23-123">**Risorse per approfondire**</span><span class="sxs-lookup"><span data-stu-id="aff23-123">**Resources to learn more**</span></span>|
|[<span data-ttu-id="aff23-124">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="aff23-124">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)|<span data-ttu-id="aff23-125">Registri di controllo</span><span class="sxs-lookup"><span data-stu-id="aff23-125">Audit logs</span></span>|[<span data-ttu-id="aff23-126">Integrazione di SIEM con Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="aff23-126">SIEM integration with Office 365 Advanced Threat Protection</span></span>](siem-integration-with-office-365-ti.md)|
|[<span data-ttu-id="aff23-127">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="aff23-127">Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)|<span data-ttu-id="aff23-128">Endpoint HTTPS ospitato in Azure</span><span class="sxs-lookup"><span data-stu-id="aff23-128">HTTPS endpoint hosted in Azure</span></span> <br/><span data-ttu-id="aff23-129">API REST</span><span class="sxs-lookup"><span data-stu-id="aff23-129">REST API</span></span>|[<span data-ttu-id="aff23-130">Tirare gli avvisi agli strumenti di SIEM</span><span class="sxs-lookup"><span data-stu-id="aff23-130">Pull alerts to your SIEM tools</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem)|
|[<span data-ttu-id="aff23-131">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="aff23-131">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)|<span data-ttu-id="aff23-132">Integrazione del registro</span><span class="sxs-lookup"><span data-stu-id="aff23-132">Log integration</span></span>|[<span data-ttu-id="aff23-133">Integrazione di SIEM con Microsoft cloud app Security</span><span class="sxs-lookup"><span data-stu-id="aff23-133">SIEM integration with Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/siem)|
|

> [!TIP]
> <span data-ttu-id="aff23-134">Dai un'occhiata a [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview).</span><span class="sxs-lookup"><span data-stu-id="aff23-134">Take a look at [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview).</span></span> <span data-ttu-id="aff23-135">Azure Sentinel è dotato di connettori per le soluzioni Microsoft.</span><span class="sxs-lookup"><span data-stu-id="aff23-135">Azure Sentinel comes with connectors for Microsoft solutions.</span></span> <span data-ttu-id="aff23-136">Questi connettori sono disponibili "fuori dalla scatola" e forniscono l'integrazione in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="aff23-136">These connectors are available "out of the box" and provide for real-time integration.</span></span> <span data-ttu-id="aff23-137">È possibile utilizzare Azure Sentinel con le soluzioni Microsoft Threat Protection e Microsoft 365 Services, tra cui Office 365, Azure AD, Azure ATP, Microsoft cloud app Security e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="aff23-137">You can use Azure Sentinel with your Microsoft Threat Protection solutions and Microsoft 365 services, including Office 365, Azure AD, Azure ATP, Microsoft Cloud App Security, and more.</span></span>

### <a name="audit-logging-must-be-turned-on"></a><span data-ttu-id="aff23-138">La registrazione di controllo deve essere attivata</span><span class="sxs-lookup"><span data-stu-id="aff23-138">Audit logging must be turned on</span></span>

<span data-ttu-id="aff23-139">Verificare che la registrazione di controllo sia attivata prima di configurare l'integrazione del server SIEM.</span><span class="sxs-lookup"><span data-stu-id="aff23-139">Make sure that audit logging is turned on before you configure SIEM server integration.</span></span>

- <span data-ttu-id="aff23-140">Per SharePoint Online, OneDrive for business e Azure Active Directory, [la registrazione di controllo è attivata nel centro sicurezza & conformità](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="aff23-140">For SharePoint Online, OneDrive for Business, and Azure Active Directory, [audit logging is turned on in the Security & Compliance Center](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="aff23-141">Per Exchange Online, vedere [gestire il controllo delle cassette postali](../../compliance/enable-mailbox-auditing.md).</span><span class="sxs-lookup"><span data-stu-id="aff23-141">For Exchange Online, see [Manage mailbox auditing](../../compliance/enable-mailbox-auditing.md).</span></span>

## <a name="more-resources"></a><span data-ttu-id="aff23-142">Altre risorse</span><span class="sxs-lookup"><span data-stu-id="aff23-142">More resources</span></span>

[<span data-ttu-id="aff23-143">Integrare soluzioni di sicurezza nel centro sicurezza di Azure</span><span class="sxs-lookup"><span data-stu-id="aff23-143">Integrate security solutions in Azure Security Center</span></span>](https://docs.microsoft.com/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[<span data-ttu-id="aff23-144">Integrare gli avvisi dell'API di sicurezza di Microsoft Graph con un SIEM</span><span class="sxs-lookup"><span data-stu-id="aff23-144">Integrate Microsoft Graph Security API alerts with a SIEM</span></span>](https://docs.microsoft.com/graph/security-integration)
