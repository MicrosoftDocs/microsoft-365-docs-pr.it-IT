---
title: Integrazione del server SIEM con applicazioni e servizi di Microsoft 365
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/18/2019
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
- seo-marvel-apr2020
description: Panoramica dell'integrazione del server SiEM (Security Information and Event Management) con le applicazioni e i servizi cloud di Microsoft 365
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: bea8aa3914da4b813f3928eddbb6df9c98ef6605
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599948"
---
# <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a><span data-ttu-id="9aac6-103">Integrazione del server SiEM (Security Information and Event Management) con applicazioni e servizi di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9aac6-103">Security Information and Event Management (SIEM) server integration with Microsoft 365 services and applications</span></span>

<span data-ttu-id="9aac6-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="9aac6-104">**Applies to**</span></span>
- [<span data-ttu-id="9aac6-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="9aac6-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="9aac6-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="9aac6-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="9aac6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9aac6-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

## <a name="summary"></a><span data-ttu-id="9aac6-108">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="9aac6-108">Summary</span></span>

<span data-ttu-id="9aac6-109">L'organizzazione utilizza o pianifica di ottenere un server SiEM (Security Information and Event Management)</span><span class="sxs-lookup"><span data-stu-id="9aac6-109">Is your organization using or planning to get a Security Information and Event Management (SIEM) server?</span></span> <span data-ttu-id="9aac6-110">Potrebbe essere necessario chiedersi come si integra con Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="9aac6-110">You might be wondering how it integrates with Microsoft 365 or Office 365.</span></span> <span data-ttu-id="9aac6-111">In questo articolo viene fornito un elenco delle risorse che è possibile utilizzare per integrare il server SIEM con i servizi e le applicazioni di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9aac6-111">This article provides a list of resources you can use to integrate your SIEM server with Microsoft 365 services and applications.</span></span>

> [!TIP]
> <span data-ttu-id="9aac6-112">Se non si dispone ancora di un server SIEM e si stanno esplorando le opzioni, prendere in considerazione **[Microsoft Azure Sentinel.](/azure/sentinel/overview)**</span><span class="sxs-lookup"><span data-stu-id="9aac6-112">If you don't have a SIEM server yet and are exploring your options, consider **[Microsoft Azure Sentinel](/azure/sentinel/overview)**.</span></span>

## <a name="do-i-need-a-siem-server"></a><span data-ttu-id="9aac6-113">È necessario un server SIEM?</span><span class="sxs-lookup"><span data-stu-id="9aac6-113">Do I need a SIEM server?</span></span>

<span data-ttu-id="9aac6-114">La necessità di un server SIEM dipende da molti fattori, ad esempio i requisiti di sicurezza dell'organizzazione e la posizione dei dati.</span><span class="sxs-lookup"><span data-stu-id="9aac6-114">Whether you need a SIEM server depends on many factors, such as your organization's security requirements and where your data resides.</span></span> <span data-ttu-id="9aac6-115">Microsoft 365 include un'ampia gamma di funzionalità di sicurezza che soddisfano le esigenze di sicurezza di molte organizzazioni senza server aggiuntivi, ad esempio un server SIEM.</span><span class="sxs-lookup"><span data-stu-id="9aac6-115">Microsoft 365 includes a wide variety of security features that meet many organizations' security needs without additional servers, such as a SIEM server.</span></span> <span data-ttu-id="9aac6-116">Alcune organizzazioni hanno circostanze particolari che richiedono l'utilizzo di un server SIEM.</span><span class="sxs-lookup"><span data-stu-id="9aac6-116">Some organizations have special circumstances that require the use of a SIEM server.</span></span> <span data-ttu-id="9aac6-117">Di seguito vengono descritti alcuni esempi:</span><span class="sxs-lookup"><span data-stu-id="9aac6-117">Here are some examples:</span></span>

- <span data-ttu-id="9aac6-118">*Fabrikam* ha alcuni contenuti e applicazioni in locale e alcuni nel cloud (hanno una distribuzione cloud ibrida).</span><span class="sxs-lookup"><span data-stu-id="9aac6-118">*Fabrikam* has some content and applications on premises, and some in the cloud (they have a hybrid cloud deployment).</span></span> <span data-ttu-id="9aac6-119">Per ottenere report sulla sicurezza in tutto il contenuto e le applicazioni, Fabrikam ha implementato un server SIEM.</span><span class="sxs-lookup"><span data-stu-id="9aac6-119">To get security reports across all their content and applications, Fabrikam has implemented a SIEM server.</span></span>

- <span data-ttu-id="9aac6-120">*Contoso* è un'organizzazione di servizi finanziari con requisiti di sicurezza particolarmente stringenti.</span><span class="sxs-lookup"><span data-stu-id="9aac6-120">*Contoso* is a financial services organization that has particularly stringent security requirements.</span></span> <span data-ttu-id="9aac6-121">Hanno aggiunto un server SIEM al proprio ambiente per sfruttare la protezione di sicurezza aggiuntiva necessaria.</span><span class="sxs-lookup"><span data-stu-id="9aac6-121">They have added a SIEM server to their environment to take advantage of the extra security protection they require.</span></span>

## <a name="siem-server-integration-with-microsoft-365"></a><span data-ttu-id="9aac6-122">Integrazione del server SIEM con Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9aac6-122">SIEM server integration with Microsoft 365</span></span>

<span data-ttu-id="9aac6-123">Un server SIEM può ricevere dati da un'ampia gamma di applicazioni e servizi di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9aac6-123">A SIEM server can receive data from a wide variety of Microsoft 365 services and applications.</span></span> <span data-ttu-id="9aac6-124">Nella tabella seguente sono elencati diversi servizi e applicazioni di Microsoft 365, insieme agli input del server SIEM e alle risorse per saperne di più.</span><span class="sxs-lookup"><span data-stu-id="9aac6-124">The following table lists several Microsoft 365 services and applications, along with SIEM server inputs and resources to learn more.</span></span>

****

|<span data-ttu-id="9aac6-125">Servizio o applicazione Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9aac6-125">Microsoft 365 Service or Application</span></span>|<span data-ttu-id="9aac6-126">Input/metodi del server SIEM</span><span class="sxs-lookup"><span data-stu-id="9aac6-126">SIEM server inputs/methods</span></span>|<span data-ttu-id="9aac6-127">Risorse per approfondire</span><span class="sxs-lookup"><span data-stu-id="9aac6-127">Resources to learn more</span></span>|
|---|---|---|
|[<span data-ttu-id="9aac6-128">Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="9aac6-128">Microsoft Defender for Office 365</span></span>](defender-for-office-365.md)|<span data-ttu-id="9aac6-129">Log di controllo</span><span class="sxs-lookup"><span data-stu-id="9aac6-129">Audit logs</span></span>|[<span data-ttu-id="9aac6-130">Integrazione SIEM con Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="9aac6-130">SIEM integration with Microsoft Defender for Office 365</span></span>](siem-integration-with-office-365-ti.md)|
|[<span data-ttu-id="9aac6-131">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="9aac6-131">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/)|<span data-ttu-id="9aac6-132">Endpoint HTTPS ospitato in Azure</span><span class="sxs-lookup"><span data-stu-id="9aac6-132">HTTPS endpoint hosted in Azure</span></span> <p> <span data-ttu-id="9aac6-133">API REST</span><span class="sxs-lookup"><span data-stu-id="9aac6-133">REST API</span></span>|[<span data-ttu-id="9aac6-134">Pull degli avvisi agli strumenti SIEM</span><span class="sxs-lookup"><span data-stu-id="9aac6-134">Pull alerts to your SIEM tools</span></span>](../defender-endpoint/configure-siem.md)|
|[<span data-ttu-id="9aac6-135">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="9aac6-135">Microsoft Cloud App Security</span></span>](/cloud-app-security/what-is-cloud-app-security)|<span data-ttu-id="9aac6-136">Integrazione dei log</span><span class="sxs-lookup"><span data-stu-id="9aac6-136">Log integration</span></span>|[<span data-ttu-id="9aac6-137">Integrazione SIEM con Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="9aac6-137">SIEM integration with Microsoft Cloud App Security</span></span>](/cloud-app-security/siem)|
|

> [!TIP]
> <span data-ttu-id="9aac6-138">Dai un'occhiata [ad Azure Sentinel.](/azure/sentinel/overview)</span><span class="sxs-lookup"><span data-stu-id="9aac6-138">Take a look at [Azure Sentinel](/azure/sentinel/overview).</span></span> <span data-ttu-id="9aac6-139">Azure Sentinel include connettori per soluzioni Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9aac6-139">Azure Sentinel comes with connectors for Microsoft solutions.</span></span> <span data-ttu-id="9aac6-140">Questi connettori sono disponibili "out-of-the-box" e consentono l'integrazione in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="9aac6-140">These connectors are available "out of the box" and provide for real-time integration.</span></span> <span data-ttu-id="9aac6-141">È possibile usare Azure Sentinel con le soluzioni Microsoft 365 Defender e i servizi di Microsoft 365, tra cui Office 365, Azure AD, Microsoft Defender for Identity, Microsoft Cloud App Security e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="9aac6-141">You can use Azure Sentinel with your Microsoft 365 Defender solutions and Microsoft 365 services, including Office 365, Azure AD, Microsoft Defender for Identity, Microsoft Cloud App Security, and more.</span></span>

### <a name="audit-logging-must-be-turned-on"></a><span data-ttu-id="9aac6-142">La registrazione di controllo deve essere attivata</span><span class="sxs-lookup"><span data-stu-id="9aac6-142">Audit logging must be turned on</span></span>

<span data-ttu-id="9aac6-143">Verificare che la registrazione di controllo sia attivata prima di configurare l'integrazione del server SIEM.</span><span class="sxs-lookup"><span data-stu-id="9aac6-143">Make sure that audit logging is turned on before you configure SIEM server integration.</span></span>

- <span data-ttu-id="9aac6-144">Per SharePoint Online, OneDrive for Business e Azure Active Directory, la registrazione di controllo è attivata nel [Centro sicurezza & conformità](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="9aac6-144">For SharePoint Online, OneDrive for Business, and Azure Active Directory, [audit logging is turned on in the Security & Compliance Center](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="9aac6-145">Per Exchange Online, vedere [Manage mailbox auditing](../../compliance/enable-mailbox-auditing.md).</span><span class="sxs-lookup"><span data-stu-id="9aac6-145">For Exchange Online, see [Manage mailbox auditing](../../compliance/enable-mailbox-auditing.md).</span></span>

## <a name="more-resources"></a><span data-ttu-id="9aac6-146">Altre risorse</span><span class="sxs-lookup"><span data-stu-id="9aac6-146">More resources</span></span>

[<span data-ttu-id="9aac6-147">Integrare soluzioni di sicurezza in Azure Defender</span><span class="sxs-lookup"><span data-stu-id="9aac6-147">Integrate security solutions in Azure Defender</span></span>](/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[<span data-ttu-id="9aac6-148">Integrare gli avvisi delle API di sicurezza di Microsoft Graph con un SIEM</span><span class="sxs-lookup"><span data-stu-id="9aac6-148">Integrate Microsoft Graph Security API alerts with a SIEM</span></span>](/graph/security-integration)