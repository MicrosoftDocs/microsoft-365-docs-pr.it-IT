---
title: Integrazione del server SIEM con i servizi e le applicazioni di Microsoft 365
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/15/2019
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
description: Leggere questo articolo per ottenere una panoramica dell'integrazione del server SIEM con Microsoft 365.
ms.openlocfilehash: bea6141022fef1275a7e291217f698f52613f170
ms.sourcegitcommit: d8d001c03c28c10bea005d1c9b5f4a8f393af706
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/16/2019
ms.locfileid: "38677509"
---
# <a name="siem-server-integration-with-microsoft-365-services-and-applications"></a><span data-ttu-id="89215-103">Integrazione del server SIEM con i servizi e le applicazioni di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="89215-103">SIEM server integration with Microsoft 365 services and applications</span></span>

## <a name="summary"></a><span data-ttu-id="89215-104">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="89215-104">Summary</span></span>

<span data-ttu-id="89215-105">Se l'organizzazione utilizza un server di gestione eventi e informazioni di sicurezza (SIEM) o se si prevede di ottenere un server SIEM al più presto, potrebbe essere utile sapere come si integrerà con Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="89215-105">If your organization is using a Security Information and Event Management (SIEM) server, or if you are planning to get a SIEM server soon, you might be wondering how that'll integrate with Microsoft 365 or Office 365.</span></span> <span data-ttu-id="89215-106">In questo articolo viene fornito un elenco delle risorse che è possibile utilizzare per configurare l'integrazione dei server SIEM con i servizi e le applicazioni di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="89215-106">This article provides a list of resources you can use to set up SIEM server integration with your Microsoft 365 services and applications.</span></span>

> [!TIP]
> <span data-ttu-id="89215-107">Se non si dispone ancora di un server SIEM e si esplorano le opzioni, prendere in considerazione **[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)**.</span><span class="sxs-lookup"><span data-stu-id="89215-107">If you don't have a SIEM server yet and are exploring your options, consider **[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)**.</span></span>

## <a name="do-i-need-a-siem-server"></a><span data-ttu-id="89215-108">È necessario un server SIEM?</span><span class="sxs-lookup"><span data-stu-id="89215-108">Do I need a SIEM server?</span></span>

<span data-ttu-id="89215-109">Se è necessario un server SIEM dipende da molti fattori, ad esempio i requisiti di sicurezza dell'organizzazione e il luogo in cui si trovano i dati.</span><span class="sxs-lookup"><span data-stu-id="89215-109">Whether you need a SIEM server depends on many factors, such as your organization's security requirements and where your data resides.</span></span> <span data-ttu-id="89215-110">Microsoft 365 include una vasta gamma di funzionalità di sicurezza che soddisfano le esigenze di sicurezza di molte organizzazioni senza server aggiuntivi, ad esempio un server SIEM.</span><span class="sxs-lookup"><span data-stu-id="89215-110">Microsoft 365 includes a wide variety of security features that meet many organizations' security needs without additional servers, such as a SIEM server.</span></span> <span data-ttu-id="89215-111">Alcune organizzazioni presentano circostanze speciali che richiedono l'utilizzo di un server SIEM.</span><span class="sxs-lookup"><span data-stu-id="89215-111">Some organizations have special circumstances that require the use of a SIEM server.</span></span> <span data-ttu-id="89215-112">Ecco alcuni esempi:</span><span class="sxs-lookup"><span data-stu-id="89215-112">Here are some examples:</span></span>

- <span data-ttu-id="89215-113">In *Fabrikam* sono disponibili contenuto e applicazioni in locale e alcuni nel cloud (dispongono di una distribuzione di cloud ibrido).</span><span class="sxs-lookup"><span data-stu-id="89215-113">*Fabrikam* has some content and applications on premises, and some in the cloud (they have a hybrid cloud deployment).</span></span> <span data-ttu-id="89215-114">Per ottenere i rapporti sulla sicurezza tra tutti i contenuti e le applicazioni, Fabrikam ha implementato un server SIEM.</span><span class="sxs-lookup"><span data-stu-id="89215-114">To get security reports across all their content and applications, Fabrikam has implemented a SIEM server.</span></span> 

- <span data-ttu-id="89215-115">*Contoso* è un'organizzazione per i servizi finanziari con requisiti di sicurezza particolarmente severi.</span><span class="sxs-lookup"><span data-stu-id="89215-115">*Contoso* is a financial services organization that has particularly stringent security requirements.</span></span> <span data-ttu-id="89215-116">Sono stati aggiunti un server SIEM all'ambiente per usufruire della protezione di sicurezza aggiuntiva necessaria.</span><span class="sxs-lookup"><span data-stu-id="89215-116">They have added a SIEM server to their environment to take advantage of the extra security protection they require.</span></span>

## <a name="siem-server-integration-with-microsoft-365"></a><span data-ttu-id="89215-117">Integrazione del server SIEM con Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="89215-117">SIEM server integration with Microsoft 365</span></span>

<span data-ttu-id="89215-118">Un server SIEM può ricevere dati da un'ampia gamma di servizi e applicazioni di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="89215-118">A SIEM server can receive data from a wide variety of Microsoft 365 services and applications.</span></span> <span data-ttu-id="89215-119">Nella tabella seguente sono elencati diversi servizi e applicazioni di Microsoft 365 insieme agli input del server SIEM e risorse per ulteriori informazioni sull'integrazione del server SIEM.</span><span class="sxs-lookup"><span data-stu-id="89215-119">The following table lists several Microsoft 365 services and applications along with SIEM server inputs, and resources to learn more about SIEM server integration.</span></span> 

| <span data-ttu-id="89215-120">Servizio o applicazione Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="89215-120">Microsoft 365 Service or Application</span></span> | <span data-ttu-id="89215-121">Input del server SIEM</span><span class="sxs-lookup"><span data-stu-id="89215-121">SIEM server inputs</span></span> | <span data-ttu-id="89215-122">Risorse per approfondire</span><span class="sxs-lookup"><span data-stu-id="89215-122">Resources to learn more</span></span> |
| --- | --- | --- |
| [<span data-ttu-id="89215-123">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="89215-123">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)  | <span data-ttu-id="89215-124">Registri di controllo</span><span class="sxs-lookup"><span data-stu-id="89215-124">Audit logs</span></span> | [<span data-ttu-id="89215-125">Integrazione di SIEM con Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="89215-125">SIEM integration with Office 365 Advanced Threat Protection</span></span>](siem-integration-with-office-365-ti.md) |
| [<span data-ttu-id="89215-126">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="89215-126">Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/) | <span data-ttu-id="89215-127">Endpoint HTTPS ospitato in Azure</span><span class="sxs-lookup"><span data-stu-id="89215-127">HTTPS endpoint hosted in Azure</span></span> <br/><span data-ttu-id="89215-128">API REST</span><span class="sxs-lookup"><span data-stu-id="89215-128">REST API</span></span>| [<span data-ttu-id="89215-129">Tirare gli avvisi agli strumenti di SIEM</span><span class="sxs-lookup"><span data-stu-id="89215-129">Pull alerts to your SIEM tools</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem) |
| [<span data-ttu-id="89215-130">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="89215-130">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) | <span data-ttu-id="89215-131">Integrazione del registro</span><span class="sxs-lookup"><span data-stu-id="89215-131">Log integration</span></span> | [<span data-ttu-id="89215-132">Integrazione di SIEM con Microsoft cloud app Security</span><span class="sxs-lookup"><span data-stu-id="89215-132">SIEM integration with Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/siem) |

> [!TIP]
> <span data-ttu-id="89215-133">Dai un'occhiata a [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview), che include un numero di connettori per le soluzioni Microsoft, disponibile fuori dalla scatola e fornendo integrazione in tempo reale, incluse le soluzioni Microsoft Threat Protection e Microsoft 365 Sources, tra cui Office 365, Azure ad, Azure ATP e Microsoft cloud app Security e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="89215-133">Take a look at [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview), which comes with a number of connectors for Microsoft solutions, available out of the box and providing real-time integration, including Microsoft Threat Protection solutions, and Microsoft 365 sources, including Office 365, Azure AD, Azure ATP, and Microsoft Cloud App Security, and more.</span></span>

### <a name="audit-logging-must-be-turned-on"></a><span data-ttu-id="89215-134">La registrazione di controllo deve essere attivata</span><span class="sxs-lookup"><span data-stu-id="89215-134">Audit logging must be turned on</span></span>

<span data-ttu-id="89215-135">Verificare che la registrazione di controllo sia attivata prima di configurare l'integrazione del server SIEM.</span><span class="sxs-lookup"><span data-stu-id="89215-135">Make sure audit logging is turned on before you configure SIEM server integration.</span></span> 

- <span data-ttu-id="89215-136">Per SharePoint Online, OneDrive for business e Azure Active Directory, [la registrazione di controllo è attivata nel centro sicurezza & conformità](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off).</span><span class="sxs-lookup"><span data-stu-id="89215-136">For SharePoint Online, OneDrive for Business, and Azure Active Directory, [audit logging is turned on in the Security & Compliance Center](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off).</span></span>

- <span data-ttu-id="89215-137">Per Exchange Online, la [registrazione di controllo è attivata con Windows PowerShell](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing).</span><span class="sxs-lookup"><span data-stu-id="89215-137">For Exchange Online, [audit logging is turned on with Windows PowerShell](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing).</span></span>
 
## <a name="additional-resources"></a><span data-ttu-id="89215-138">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="89215-138">Additional resources</span></span>

[<span data-ttu-id="89215-139">Integrare soluzioni di sicurezza nel centro sicurezza di Azure</span><span class="sxs-lookup"><span data-stu-id="89215-139">Integrate security solutions in Azure Security Center</span></span>](https://docs.microsoft.com/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[<span data-ttu-id="89215-140">Integrare gli avvisi dell'API di sicurezza di Microsoft Graph con un SIEM</span><span class="sxs-lookup"><span data-stu-id="89215-140">Integrate Microsoft Graph Security API alerts with a SIEM</span></span>](https://docs.microsoft.com/graph/security-integration)