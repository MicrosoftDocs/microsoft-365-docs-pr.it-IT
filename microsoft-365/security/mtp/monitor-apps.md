---
title: Monitoraggio delle app & Reporting-Centro sicurezza
description: Informazioni su come acquisire maggiori informazioni sull'utilizzo delle app Cloud nell'organizzazione. Include diversi tipi di app, il livello di rischio e gli avvisi.
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f73c6b010677cdc481655d1d5310872fd1a99126
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920515"
---
# <a name="app-monitoring-and-reporting-in-the-microsoft-365-security-center"></a><span data-ttu-id="c3a38-105">Monitoraggio e creazione di report delle app nel centro sicurezza Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c3a38-105">App monitoring and reporting in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c3a38-106">Questi rapporti offrono maggiori informazioni su come vengono utilizzate le app Cloud nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c3a38-106">These reports provide more insight into how cloud apps are being used in your organization.</span></span> <span data-ttu-id="c3a38-107">Include diversi tipi di app, il livello di rischio e gli avvisi.</span><span class="sxs-lookup"><span data-stu-id="c3a38-107">Includes different kinds of apps, their level of risk, and alerts.</span></span>

## <a name="monitor-email-accounts-at-risk"></a><span data-ttu-id="c3a38-108">Monitorare gli account di posta elettronica a rischio</span><span class="sxs-lookup"><span data-stu-id="c3a38-108">Monitor email accounts at risk</span></span>

<span data-ttu-id="c3a38-109">La **protezione della posta** elettronica Visualizza gli account di posta elettronica a rischio.</span><span class="sxs-lookup"><span data-stu-id="c3a38-109">**Email protection** shows email accounts at risk.</span></span> <span data-ttu-id="c3a38-110">È possibile selezionare un account per approfondire il Centro sicurezza di Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="c3a38-110">You can select an account to investigate further in Microsoft Defender Security Center.</span></span>

![Scheda di protezione della posta elettronica](../../media/email-protection.png)

## <a name="monitor-app-permissions-granted-by-users"></a><span data-ttu-id="c3a38-112">Monitorare le autorizzazioni delle app concesse dagli utenti</span><span class="sxs-lookup"><span data-stu-id="c3a38-112">Monitor app permissions granted by users</span></span>

<span data-ttu-id="c3a38-113">**Cloud app Security-OAuth Apps** elenca le app scoperte dalla protezione delle app cloud alle quali sono state concesse le autorizzazioni per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="c3a38-113">**Cloud App Security - OAuth apps** lists apps discovered by Cloud App Security that have been granted permissions by users.</span></span> <span data-ttu-id="c3a38-114">Il catalogo rischi di cloud app Security include oltre 16.000 app valutate con oltre 70 fattori di rischio.</span><span class="sxs-lookup"><span data-stu-id="c3a38-114">Cloud App Security's risk catalog includes over 16,000 apps that are assessed using over 70 risk factors.</span></span>

<span data-ttu-id="c3a38-115">I fattori di rischio partono dalle informazioni generali, ad esempio l'editore app.</span><span class="sxs-lookup"><span data-stu-id="c3a38-115">The risk factors start from general information, such as the app publisher.</span></span> <span data-ttu-id="c3a38-116">Si sposta quindi su misure di sicurezza e controlli, ad esempio se l'app supporta la crittografia a riposo o fornisce un registro di controllo delle attività degli utenti.</span><span class="sxs-lookup"><span data-stu-id="c3a38-116">It then moves to security measures and controls, such as whether the app supports encryption at rest or provides an audit log of user activity.</span></span>

![Cloud app Security OAuth Apps Card](../../media/cloud-app-security-oauth-apps.png)

## <a name="monitor-cloud-app-user-accounts"></a><span data-ttu-id="c3a38-118">Monitorare gli account utente delle app Cloud</span><span class="sxs-lookup"><span data-stu-id="c3a38-118">Monitor cloud app user accounts</span></span>

<span data-ttu-id="c3a38-119">Gli **account delle app cloud per gli elenchi di revisione** possono richiedere attenzione.</span><span class="sxs-lookup"><span data-stu-id="c3a38-119">**Cloud app accounts for review** lists accounts that may require attention.</span></span>

![Account app cloud per la scheda di Revisione](../../media/cloud-app-accounts-for-review.png)

## <a name="understand-which-cloud-apps-are-used"></a><span data-ttu-id="c3a38-121">Informazioni sulle app Cloud utilizzate</span><span class="sxs-lookup"><span data-stu-id="c3a38-121">Understand which cloud apps are used</span></span>

<span data-ttu-id="c3a38-122">Le **app del cloud scoperte (categorie)** mostrano quali tipi di app vengono utilizzate nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c3a38-122">**Discovered cloud apps (categories)** show what kinds of apps are being used in your organization.</span></span> <span data-ttu-id="c3a38-123">Si collega al dashboard di individuazione cloud in cloud app Security.</span><span class="sxs-lookup"><span data-stu-id="c3a38-123">It links to the Cloud Discovery dashboard in Cloud App Security.</span></span> <span data-ttu-id="c3a38-124">Per ulteriori informazioni, vedere [Guida introduttiva: lavorare con le app scoperte](https://docs.microsoft.com/cloud-app-security/discovered-apps).</span><span class="sxs-lookup"><span data-stu-id="c3a38-124">For more information, see [Quickstart: Work with discovered apps](https://docs.microsoft.com/cloud-app-security/discovered-apps).</span></span>  

![Scheda categorie di applicazioni cloud scoperte](../../media/discovered-cloud-apps-categories.png)

## <a name="monitor-where-users-access-cloud-apps"></a><span data-ttu-id="c3a38-126">Monitorare la posizione in cui gli utenti accedono alle app Cloud</span><span class="sxs-lookup"><span data-stu-id="c3a38-126">Monitor where users access cloud apps</span></span>

<span data-ttu-id="c3a38-127">Le **posizioni delle attività delle app Cloud** mostrano dove gli utenti accedono alle app cloud.</span><span class="sxs-lookup"><span data-stu-id="c3a38-127">**Cloud app activity locations** show where users are accessing cloud apps.</span></span>

![Scheda percorsi attività app Cloud](../../media/cloud-app-activity-locations.png)

## <a name="monitor-health-for-infrastructure-workloads"></a><span data-ttu-id="c3a38-129">Monitorare l'integrità dei carichi di lavoro dell'infrastruttura</span><span class="sxs-lookup"><span data-stu-id="c3a38-129">Monitor health for infrastructure workloads</span></span>

<span data-ttu-id="c3a38-130">L' **integrità dell'infrastruttura** Visualizza gli avvisi sullo stato dell'integrità per i carichi di lavoro dell'infrastruttura in Azure Defender.</span><span class="sxs-lookup"><span data-stu-id="c3a38-130">**Infrastructure health** shows health status alerts for infrastructure workloads in Azure Defender.</span></span>

<span data-ttu-id="c3a38-131">Azure Defender fornisce la gestione della sicurezza unificata e il difensore per Office 365 tra carichi di lavoro locali e cloud.</span><span class="sxs-lookup"><span data-stu-id="c3a38-131">Azure Defender provides unified security management and Defender for Office 365 across on-premises and cloud workloads.</span></span> <span data-ttu-id="c3a38-132">È possibile raccogliere, cercare e analizzare i dati di sicurezza provenienti da origini diverse, tra cui i firewall e altre soluzioni partner.</span><span class="sxs-lookup"><span data-stu-id="c3a38-132">You can collect, search, and analyze security data from different sources, including firewalls and other partner solutions.</span></span>

<span data-ttu-id="c3a38-133">Per ulteriori informazioni, vedere [documentazione di Azure Defender](https://docs.microsoft.com/azure/security-center/).</span><span class="sxs-lookup"><span data-stu-id="c3a38-133">For more information, see [Azure Defender Documentation](https://docs.microsoft.com/azure/security-center/).</span></span>

![Scheda di integrità dell'infrastruttura](../../media/infrastructure-health.png)
