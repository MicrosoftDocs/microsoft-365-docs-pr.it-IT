---
title: Monitoraggio e creazione di report delle app nel centro sicurezza Microsoft 365
description: Descrive come è possibile ottenere ulteriori informazioni sull'utilizzo delle app Cloud nell'organizzazione
keywords: sicurezza, malware, Microsoft 365, M365, Centro sicurezza, monitoraggio, report, app
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.openlocfilehash: f7b3f2fcaac71eefa2579a0c3fd66666fe00f605
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42087681"
---
# <a name="app-monitoring-and-reporting-in-the-microsoft-365-security-center"></a><span data-ttu-id="0d0fa-104">Monitoraggio e creazione di report delle app nel centro sicurezza Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0d0fa-104">App monitoring and reporting in the Microsoft 365 security center</span></span>

<span data-ttu-id="0d0fa-105">Questi rapporti offrono maggiori informazioni su come vengono utilizzate le app Cloud nell'organizzazione, inclusi i tipi di app, il livello di rischio e gli avvisi.</span><span class="sxs-lookup"><span data-stu-id="0d0fa-105">These reports provide more insight into how cloud apps are being used in your organization, including what kinds of apps, their level of risk, and alerts.</span></span>

## <a name="monitor-email-accounts-at-risk"></a><span data-ttu-id="0d0fa-106">Monitorare gli account di posta elettronica a rischio</span><span class="sxs-lookup"><span data-stu-id="0d0fa-106">Monitor email accounts at risk</span></span>

<span data-ttu-id="0d0fa-107">La **protezione della posta** elettronica Visualizza gli account di posta elettronica a rischio.</span><span class="sxs-lookup"><span data-stu-id="0d0fa-107">**Email protection** shows email accounts at risk.</span></span> <span data-ttu-id="0d0fa-108">È possibile fare clic su un account per esaminare ulteriormente il Centro sicurezza di Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="0d0fa-108">You can click an account to investigate further in Microsoft Defender Security Center.</span></span>

![Scheda di protezione della posta elettronica](../../media/email-protection.png)

## <a name="monitor-app-permissions-granted-by-users"></a><span data-ttu-id="0d0fa-110">Monitorare le autorizzazioni delle app concesse dagli utenti</span><span class="sxs-lookup"><span data-stu-id="0d0fa-110">Monitor app permissions granted by users</span></span>

<span data-ttu-id="0d0fa-111">**Cloud app Security-OAuth Apps** elenca le app scoperte dalla protezione delle app cloud alle quali sono state concesse le autorizzazioni per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="0d0fa-111">**Cloud App Security - OAuth apps** lists apps discovered by Cloud App Security that have been granted permissions by users.</span></span> <span data-ttu-id="0d0fa-112">Il catalogo rischi di cloud app Security include oltre 16.000 app valutate con oltre 70 fattori di rischio.</span><span class="sxs-lookup"><span data-stu-id="0d0fa-112">Cloud App Security's risk catalog includes over 16,000 apps that are assessed using over 70 risk factors.</span></span>

<span data-ttu-id="0d0fa-113">I fattori di rischio partono da informazioni generali, ad esempio l'editore app, per le misure di sicurezza e i controlli, ad esempio se l'app supporta la crittografia a riposo o fornisce un registro di controllo delle attività degli utenti.</span><span class="sxs-lookup"><span data-stu-id="0d0fa-113">The risk factors start from general information, such as the app publisher, to security measures and controls, such as whether the app supports for encryption at rest or provides an audit log of user activity.</span></span>

![Cloud app Security OAuth Apps Card](../../media/cloud-app-security-oauth-apps.png)

## <a name="monitor-cloud-app-user-accounts"></a><span data-ttu-id="0d0fa-115">Monitorare gli account utente delle app Cloud</span><span class="sxs-lookup"><span data-stu-id="0d0fa-115">Monitor cloud app user accounts</span></span>

<span data-ttu-id="0d0fa-116">Gli **account delle app cloud per gli elenchi di revisione** possono richiedere attenzione.</span><span class="sxs-lookup"><span data-stu-id="0d0fa-116">**Cloud app accounts for review** lists accounts that may require attention.</span></span>

![Account app cloud per la scheda di Revisione](../../media/cloud-app-accounts-for-review.png)

## <a name="understand-which-cloud-apps-are-used"></a><span data-ttu-id="0d0fa-118">Informazioni sulle app Cloud utilizzate</span><span class="sxs-lookup"><span data-stu-id="0d0fa-118">Understand which cloud apps are used</span></span>

<span data-ttu-id="0d0fa-119">Le **app del cloud scoperte (categorie)** mostrano quali tipi di app vengono utilizzate nell'organizzazione e si collegano al dashboard di individuazione cloud in cloud app Security.</span><span class="sxs-lookup"><span data-stu-id="0d0fa-119">**Discovered cloud apps (categories)** show what kinds of apps are being used in your organization and links to the Cloud Discovery dashboard in Cloud App Security.</span></span> <span data-ttu-id="0d0fa-120">Per ulteriori informazioni, vedere [Guida introduttiva: lavorare con le app scoperte](https://docs.microsoft.com/cloud-app-security/discovered-apps).</span><span class="sxs-lookup"><span data-stu-id="0d0fa-120">For more information, see [Quickstart: Work with discovered apps](https://docs.microsoft.com/cloud-app-security/discovered-apps).</span></span>  

![Scheda categorie di applicazioni cloud scoperte](../../media/discovered-cloud-apps-categories.png)

## <a name="monitor-where-users-access-cloud-apps"></a><span data-ttu-id="0d0fa-122">Monitorare la posizione in cui gli utenti accedono alle app Cloud</span><span class="sxs-lookup"><span data-stu-id="0d0fa-122">Monitor where users access cloud apps</span></span>

<span data-ttu-id="0d0fa-123">Le **posizioni delle attività delle app Cloud** mostrano dove gli utenti accedono alle app cloud.</span><span class="sxs-lookup"><span data-stu-id="0d0fa-123">**Cloud app activity locations** show where users are accessing cloud apps.</span></span>

![Scheda percorsi attività app Cloud](../../media/cloud-app-activity-locations.png)

## <a name="monitor-health-for-infrastructure-workloads"></a><span data-ttu-id="0d0fa-125">Monitorare l'integrità dei carichi di lavoro dell'infrastruttura</span><span class="sxs-lookup"><span data-stu-id="0d0fa-125">Monitor health for infrastructure workloads</span></span>

<span data-ttu-id="0d0fa-126">L' **integrità dell'infrastruttura** Visualizza gli avvisi sullo stato dell'integrità per i carichi di lavoro dell'infrastruttura in Azure Security Center.</span><span class="sxs-lookup"><span data-stu-id="0d0fa-126">**Infrastructure health** shows health status alerts for infrastructure workloads in Azure Security Center.</span></span>

<span data-ttu-id="0d0fa-127">Azure Security Center fornisce la gestione della sicurezza unificata e la protezione avanzata dalle minacce tra carichi di lavoro locali e cloud.</span><span class="sxs-lookup"><span data-stu-id="0d0fa-127">Azure Security Center provides unified security management and advanced threat protection across on-premises and cloud workloads.</span></span> <span data-ttu-id="0d0fa-128">È possibile raccogliere, ricercare e analizzare i dati di sicurezza provenienti da un'ampia gamma di origini, tra cui i firewall e altre soluzioni partner.</span><span class="sxs-lookup"><span data-stu-id="0d0fa-128">You can collect, search, and analyze security data from a variety of sources, including firewalls and other partner solutions.</span></span>

<span data-ttu-id="0d0fa-129">Per ulteriori informazioni, vedere [documentazione relativa al centro sicurezza di Azure](https://docs.microsoft.com/azure/security-center/).</span><span class="sxs-lookup"><span data-stu-id="0d0fa-129">For more information, see [Azure Security Center Documentation](https://docs.microsoft.com/azure/security-center/).</span></span>

![Scheda di integrità dell'infrastruttura](../../media/infrastructure-health.png)
