---
title: Governance delle app in Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Implementare le funzionalità di governance delle app di Microsoft per gestire le app.
ms.openlocfilehash: bc8c739132de52abb69c15479cd851462e9f6ce7
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420313"
---
# <a name="app-governance-add-on-to-microsoft-cloud-app-security-in-preview"></a><span data-ttu-id="2ef08-103">Componente aggiuntivo di governance delle app a Microsoft Cloud App Security (in anteprima)</span><span class="sxs-lookup"><span data-stu-id="2ef08-103">App governance add-on to Microsoft Cloud App Security (in preview)</span></span>

><span data-ttu-id="2ef08-104">*[Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="2ef08-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="2ef08-105">Gli attacchi informatici sono diventati sempre più sofisticati nei modi in cui sfruttano le app distribuite nelle infrastrutture locali e cloud, stabilendo un punto di partenza per l'escalation dei privilegi, lo spostamento laterale e l'esfiltrazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="2ef08-105">Cyberattacks have become increasingly sophisticated in the ways they exploit the apps you have deployed in your on-premises and cloud infrastructures, establishing a starting point for privilege escalation, lateral movement, and exfiltration of your data.</span></span> <span data-ttu-id="2ef08-106">Per comprendere i potenziali rischi e arrestare questi tipi di attacchi, è necessario ottenere una visibilità chiara sul comportamento di conformità delle app dell'organizzazione per identificare rapidamente quando un'app presenta comportamenti anomali e per rispondere quando questi comportamenti presentano rischi per l'ambiente, i dati e gli utenti.</span><span class="sxs-lookup"><span data-stu-id="2ef08-106">To understand the potential risks and stop these types of attacks, you need to gain clear visibility into your organization’s app compliance posture to quickly identify when an app exhibits anomalous behaviors and to respond when these behaviors present risks to your environment, data, and users.</span></span>

<span data-ttu-id="2ef08-107">La funzionalità del componente aggiuntivo della governance delle app per Microsoft Cloud App Security è una funzionalità di gestione della sicurezza e dei criteri progettata per le app abilitate per OAuth che accedono ai dati Microsoft 365 tramite l’API di Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="2ef08-107">The app governance add-on feature to Microsoft Cloud App Security is a security and policy management capability designed for OAuth-enabled apps that access Microsoft 365 data through Microsoft Graph APIs.</span></span> <span data-ttu-id="2ef08-108">La governance delle app offre visibilità, correzione e governance complete su come queste app e i relativi utenti accedono, utilizzano e condividono i dati sensibili archiviati in Microsoft 365 tramite informazioni dettagliate di utilità pratica e avvisi e azioni automatizzati dei criteri.</span><span class="sxs-lookup"><span data-stu-id="2ef08-108">App governance delivers full visibility, remediation, and governance into how these apps and their users access, use, and share your sensitive data stored in Microsoft 365 through actionable insights and automated policy alerts and actions.</span></span>

<!--
The scale of ongoing cybersecurity incidents affecting large enterprises and smaller businesses highlights the dangers of supply chain attacks and the need to strengthen the security and compliance posture of every organization. Accelerated cloud adoption with Microsoft 365 and its rich application ecosystem are constantly growing. Attackers are gaining organizational footholds through applications because:

- Users are typically unaware of the risks when consenting to the use of applications. 
- App developers and independent software vendors (ISVs) do not yet have Security Development Lifecycle (SDL) best practices in place to address attacker techniques.
-->

<span data-ttu-id="2ef08-109">La governance delle app offre funzionalità complete:</span><span class="sxs-lookup"><span data-stu-id="2ef08-109">App governance provides you with comprehensive:</span></span>

- <span data-ttu-id="2ef08-110">**Insights**: consultare una visualizzazione di tutte le app di terze parti per la piattaforma di Microsoft 365 nel tenant in un unico dashboard.</span><span class="sxs-lookup"><span data-stu-id="2ef08-110">**Insights**: See a view of all the third-party apps for the Microsoft 365 platform in your tenant on a single dashboard.</span></span> <span data-ttu-id="2ef08-111">È possibile visualizzare lo stato di tutte le app e le attività di avviso, e reagire o rispondere a queste.</span><span class="sxs-lookup"><span data-stu-id="2ef08-111">You can see all the apps’ status and alert activities and react or respond to them.</span></span>
- <span data-ttu-id="2ef08-112">**Governance**: creare criteri proattivi o reattivi per i modelli e i comportamenti delle app e utenti, e proteggere gli utenti dall'uso di app non conformi o dannose e limitare l'accesso delle app rischiose ai dati.</span><span class="sxs-lookup"><span data-stu-id="2ef08-112">**Governance**: Create proactive or reactive policies for app and user patterns and behaviors and protect your users from using non-compliant or malicious apps and limiting the access of risky apps to your data.</span></span>
- <span data-ttu-id="2ef08-113">**Rilevamento**: ricevere avvisi e notifiche quando si verificano anomalie nell'attività dell'app e quando vengono utilizzare app non conformi, dannose o rischiose.</span><span class="sxs-lookup"><span data-stu-id="2ef08-113">**Detection**: Be alerted and notified when there are anomalies in app activity and when non-compliant, malicious, or risky apps are used.</span></span>
- <span data-ttu-id="2ef08-114">**Correzione**: oltre alle funzionalità di correzione automatica, usare i controlli di correzione in modo tempestivo per rispondere ai rilevamenti anomali delle attività delle app.</span><span class="sxs-lookup"><span data-stu-id="2ef08-114">**Remediation**: Along with automatic remediation capabilities, use remediation controls in a timely manner to respond to anomalous app activity detections.</span></span>

<span data-ttu-id="2ef08-115">La governance delle app è una soluzione basata su piattaforma che è parte integrante dell'ecosistema di app di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2ef08-115">App governance is a platform-based solution that is an integral part of the Microsoft 365 app ecosystem.</span></span> <span data-ttu-id="2ef08-116">La governance delle app supervisiona e gestisce le app abilitate per OAuth registrate con Azure Active Directory (Azure AD) e accede ai dati tramite l'API di Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="2ef08-116">App governance oversees and governs OAuth-enabled apps that are registered with Azure Active Directory (Azure AD) and access data through the Microsoft Graph API.</span></span> <span data-ttu-id="2ef08-117">La governance delle app offre controlli del comportamento delle applicazioni per rafforzare il comportamento di sicurezza e conformità dell'infrastruttura IT.</span><span class="sxs-lookup"><span data-stu-id="2ef08-117">App governance provides you with application behavior controls to help strengthen the security and compliance posture of your IT infrastructure.</span></span>

<!--
Unlike other application governance products in the marketplace, MAPG is a platform-based solution that is an integral part of the Microsoft 365 application ecosystem. MAPG's initial focus is on OAuth-enabled apps published to the Microsoft 365 platform that are registered with Azure AD and access data through the Graph API. For the initial release, MAPG does not support other, non-OAuth-enabled M365 apps, add-ins (such as PowerBI), or other app vendor ecosystems such as Google, Facebook, Amazon Web Services, Workplace, and Salesforce. MAPG’s focus is on third-party published apps for the Microsoft 365 application platform.

Microsoft allows developers to build cloud applications using Azure Active Directory (Azure AD), Microsoft’s cloud identity platform, and other resources and access to tenant data through the Microsoft Graph. Because of MAPG's visibility, insights, and control capabilities, app developers have the incentive to comply with publisher verification, self-attestation, and Microsoft certification, and can build high-quality productivity apps that are secure and compliant.
-->

## <a name="a-first-glimpse-at-app-governance"></a><span data-ttu-id="2ef08-118">Primo sguardo alla governance delle app</span><span class="sxs-lookup"><span data-stu-id="2ef08-118">A first glimpse at app governance</span></span>

<span data-ttu-id="2ef08-119">Per visualizzare il dashboard di governance delle app, passare a [https://compliance.microsoft.com/appgovernance](https://compliance.microsoft.com/appgovernance).</span><span class="sxs-lookup"><span data-stu-id="2ef08-119">To see the app governance dashboard, go to [https://compliance.microsoft.com/appgovernance](https://compliance.microsoft.com/appgovernance).</span></span> <span data-ttu-id="2ef08-120">Tenere presente che l'account di accesso deve disporre di uno dei [ ruoli di amministratore](app-governance-get-started.md#administrator-roles) per visualizzare i dati di governance.</span><span class="sxs-lookup"><span data-stu-id="2ef08-120">Note that your sign-in account must have one of the [administrator roles](app-governance-get-started.md#administrator-roles) to view any app governance data.</span></span>

## <a name="app-governance-integration-with-azure-ad-and-microsoft-cloud-app-security"></a><span data-ttu-id="2ef08-121">Integrazione della governance delle app con Azure AD e Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="2ef08-121">App governance integration with Azure AD and Microsoft Cloud App Security</span></span>

<span data-ttu-id="2ef08-122">Governance delle app, Azure AD e Microsoft Cloud App Security raccolgono e forniscono insiemi di dati diversi:</span><span class="sxs-lookup"><span data-stu-id="2ef08-122">App governance, Azure AD, and Microsoft Cloud App Security collect and provide different data sets:</span></span>

- <span data-ttu-id="2ef08-123">La governance delle app fornisce informazioni dettagliate sull'attività di un'app a livello di API.</span><span class="sxs-lookup"><span data-stu-id="2ef08-123">App governance provides detailed information about an app’s activity at the API level.</span></span>
- <span data-ttu-id="2ef08-124">Azure AD fornisce metadati di base dell’app e informazioni dettagliate sugli accessi alle app.</span><span class="sxs-lookup"><span data-stu-id="2ef08-124">Azure AD provides foundational app metadata and detailed information on sign-ins to apps.</span></span>
- <span data-ttu-id="2ef08-125">Microsoft Cloud App Security fornisce informazioni sul rischio dell’app.</span><span class="sxs-lookup"><span data-stu-id="2ef08-125">Microsoft Cloud App Security provides app risk information.</span></span>

<span data-ttu-id="2ef08-126">Condividendo le informazioni tra governance delle app, Azure AD e Microsoft Cloud App Security, è possibile visualizzare informazioni aggregate in un portale e collegarsi facilmente a un altro portale per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="2ef08-126">By sharing information across app governance, Azure AD, and Microsoft Cloud App Security, you can display aggregate information in one portal and easily link to another portal for more information.</span></span> <span data-ttu-id="2ef08-127">Ecco alcuni esempi:</span><span class="sxs-lookup"><span data-stu-id="2ef08-127">Here are some examples:</span></span>

- <span data-ttu-id="2ef08-128">Informazioni di accesso alle app nella governance delle app:</span><span class="sxs-lookup"><span data-stu-id="2ef08-128">App sign-in information in app governance:</span></span>

  <span data-ttu-id="2ef08-129">Dal portale di governance delle app è possibile visualizzare l’attività di accesso aggregata per ogni app e collegarsi all’interfaccia di amministrazione di Azure Active Directory per i dettagli degli eventi di accesso.</span><span class="sxs-lookup"><span data-stu-id="2ef08-129">From the app governance portal, you can see the aggregated sign-in activity for each app and link back to the Azure Active Directory admin center for the details of sign-in events.</span></span>

<!--
- App API usage information in the Azure Active Directory admin center:

  From the Azure Active Directory admin center, you can see the aggregated app usage information and link to the app governance portal for the details of app usage.
-->
- <span data-ttu-id="2ef08-130">Informazioni sull’utilizzo dell'API nel portale di Microsoft Cloud App Security:</span><span class="sxs-lookup"><span data-stu-id="2ef08-130">API usage information in the Microsoft Cloud App Security portal:</span></span>

  <span data-ttu-id="2ef08-131">Dal portale di Microsoft Cloud App Security è possibile visualizzare il livello di utilizzo dell'API e aggregare il trasferimento dei dati e collegarsi al portale di governance delle app per i dettagli.</span><span class="sxs-lookup"><span data-stu-id="2ef08-131">From the Microsoft Cloud App Security portal, you can see API usage level and aggregate data transfer and link to the app governance portal for the details.</span></span>

<span data-ttu-id="2ef08-132">Di seguito è riportato un riepilogo dell’integrazione.</span><span class="sxs-lookup"><span data-stu-id="2ef08-132">Here's a summary of the integration.</span></span>

![Integrazione della governance delle app con Azure Active Directory e Microsoft Cloud App Security](..\media\manage-app-protection-governance\mapg-integration.png)

<span data-ttu-id="2ef08-134">Inoltre, la governance delle app invia i propri avvisi come segnali a Microsoft Cloud App Security e Microsoft 365 Defender, e riceve avvisi da Microsoft Cloud App Security per abilitare un'analisi più dettagliata degli eventi imprevisti di sicurezza basati su app.</span><span class="sxs-lookup"><span data-stu-id="2ef08-134">Additionally, app governance sends its alerts as signals to Microsoft Cloud App Security and Microsoft 365 Defender, and app governance receives alerts from Microsoft Cloud App Security, to enable more detailed analysis of app-based security incidents.</span></span>

<!--
Integration of alerts with MCAS and M365 Defender
Azure AD IP detections in progress to surface in M365 Defender

## Integration with Azure AD

**Feedback from Anand:** We should add some details on how MAPG works with M365 Defender (previously MTP). Also, we should highlight the integration with MCAS and AAD.

Key cross-reference resources:

- [What is application management in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-application-management)
- [Common application management scenarios for Azure Active Directory (especially scenarios 3-4)](https://docs.microsoft.com/cloud-app-security/monitor-alerts)
- [Azure Active Directory Identity Governance documentation](https://docs.microsoft.com/azure/active-directory/governance/)
- [Managing access to apps using Azure AD](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-access-management)

## Integration with Microsoft Cloud App Security

Key cross-reference resources:

- [Cloud App Security anomaly detection alerts investigation guide](https://docs.microsoft.com/cloud-app-security/investigate-anomaly-alerts#unusual-addition-of-credentials-to-an-oauth-app)
- [Monitor alerts raised in Cloud App Security](https://docs.microsoft.com/cloud-app-security/monitor-alerts)
- [Control which third-party cloud OAuth apps get permissions](https://docs.microsoft.com/cloud-app-security/manage-app-permissions)

-->

## <a name="using-app-governance"></a><span data-ttu-id="2ef08-135">Uso della governance delle app</span><span class="sxs-lookup"><span data-stu-id="2ef08-135">Using app governance</span></span>

<span data-ttu-id="2ef08-136">L'uso della governance delle app per proteggere il tenant e i relativi dati da app potenzialmente dannose o con un comportamento non corretto rientra in queste tre funzionalità principali:</span><span class="sxs-lookup"><span data-stu-id="2ef08-136">Using app governance to protect your tenant and its data from potentially malicious or ill-behaved apps falls into these three core capabilities:</span></span>

| <span data-ttu-id="2ef08-137">Funzionalità</span><span class="sxs-lookup"><span data-stu-id="2ef08-137">Capability</span></span> | <span data-ttu-id="2ef08-138">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2ef08-138">Description</span></span> |
|:-------|:-----|
| [<span data-ttu-id="2ef08-139">Visibilità e dati analitici delle app</span><span class="sxs-lookup"><span data-stu-id="2ef08-139">App visibility and insights</span></span>](app-governance-visibility-insights-overview.md) | <span data-ttu-id="2ef08-140">Ottenere una visualizzazione a 360° del traffico e dell'attività delle applicazioni di Microsoft 365 nel tenant.</span><span class="sxs-lookup"><span data-stu-id="2ef08-140">Get a 360° view on traffic and activity of the Microsoft 365 applications in your tenant.</span></span> |
| [<span data-ttu-id="2ef08-141">Criteri delle app per governance più avanzata</span><span class="sxs-lookup"><span data-stu-id="2ef08-141">App policies for reinforced governance</span></span>](app-governance-app-policies-overview.md) | <span data-ttu-id="2ef08-142">Creare criteri proattivi o reattivi per le app, che consentiranno di applicare la governance per le app di Microsoft 3635.</span><span class="sxs-lookup"><span data-stu-id="2ef08-142">Create proactive or reactive app policies, which will allow you to enforce governance for your Microsoft 3635 apps.</span></span> |
| [<span data-ttu-id="2ef08-143">Rilevamento e correzione</span><span class="sxs-lookup"><span data-stu-id="2ef08-143">Detection and remediation</span></span>](app-governance-detect-remediate-overview.md) | <span data-ttu-id="2ef08-144">In base agli avvisi di rilevamento della piattaforma o agli avvisi di rilevamento generati dai criteri, monitorare le app per rilevare comportamenti anomali e correggerli automaticamente in base alle impostazioni dei criteri delle app o manualmente.</span><span class="sxs-lookup"><span data-stu-id="2ef08-144">Based on platform detection alerts or policy-generated detection alerts, monitor your apps for anomalous app behavior and remediate them, either automatically based on app policy settings or manually.</span></span> |
|||
