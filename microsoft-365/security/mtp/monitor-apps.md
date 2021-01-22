---
title: Monitoraggio delle app & report - Centro sicurezza
description: Scopri come ottenere maggiori informazioni sull'uso delle app cloud nella tua organizzazione. Include diversi tipi di app, il relativo livello di rischio e avvisi.
keywords: sicurezza, malware, Microsoft 365, M365, centro sicurezza, monitorare, report, app
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: ed5fcfc16c08272a6a1d55af210ab48528538048
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930523"
---
# <a name="app-monitoring-and-reporting-in-the-microsoft-365-security-center"></a><span data-ttu-id="239e2-105">Monitoraggio e creazione di report delle app nel Centro sicurezza Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="239e2-105">App monitoring and reporting in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="239e2-106">Questi report forniscono maggiori informazioni su come vengono usate le app cloud nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="239e2-106">These reports provide more insight into how cloud apps are being used in your organization.</span></span> <span data-ttu-id="239e2-107">Include diversi tipi di app, il relativo livello di rischio e avvisi.</span><span class="sxs-lookup"><span data-stu-id="239e2-107">Includes different kinds of apps, their level of risk, and alerts.</span></span>

## <a name="monitor-email-accounts-at-risk"></a><span data-ttu-id="239e2-108">Monitorare gli account di posta elettronica a rischio</span><span class="sxs-lookup"><span data-stu-id="239e2-108">Monitor email accounts at risk</span></span>

<span data-ttu-id="239e2-109">**La protezione della posta** elettronica mostra gli account di posta elettronica a rischio.</span><span class="sxs-lookup"><span data-stu-id="239e2-109">**Email protection** shows email accounts at risk.</span></span> <span data-ttu-id="239e2-110">Puoi selezionare un account da analizzare ulteriormente in Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="239e2-110">You can select an account to investigate further in Microsoft Defender Security Center.</span></span>

![Scheda di protezione della posta elettronica](../../media/email-protection.png)

## <a name="monitor-app-permissions-granted-by-users"></a><span data-ttu-id="239e2-112">Monitorare le autorizzazioni dell'app concesse dagli utenti</span><span class="sxs-lookup"><span data-stu-id="239e2-112">Monitor app permissions granted by users</span></span>

<span data-ttu-id="239e2-113">**Cloud App Security: le app OAuth** elencano le app individuate da Cloud App Security a cui sono state concesse autorizzazioni dagli utenti.</span><span class="sxs-lookup"><span data-stu-id="239e2-113">**Cloud App Security - OAuth apps** lists apps discovered by Cloud App Security that have been granted permissions by users.</span></span> <span data-ttu-id="239e2-114">Il catalogo dei rischi di Cloud App Security include oltre 16.000 app valutate utilizzando oltre 70 fattori di rischio.</span><span class="sxs-lookup"><span data-stu-id="239e2-114">Cloud App Security's risk catalog includes over 16,000 apps that are assessed using over 70 risk factors.</span></span>

<span data-ttu-id="239e2-115">I fattori di rischio partono dalle informazioni generali, ad esempio l'autore dell'app.</span><span class="sxs-lookup"><span data-stu-id="239e2-115">The risk factors start from general information, such as the app publisher.</span></span> <span data-ttu-id="239e2-116">Passa quindi a misure e controlli di sicurezza, ad esempio se l'app supporta la crittografia in stato attivo o fornisce un log di controllo dell'attività dell'utente.</span><span class="sxs-lookup"><span data-stu-id="239e2-116">It then moves to security measures and controls, such as whether the app supports encryption at rest or provides an audit log of user activity.</span></span>

![Scheda app OAuth di Cloud App Security](../../media/cloud-app-security-oauth-apps.png)

## <a name="monitor-cloud-app-user-accounts"></a><span data-ttu-id="239e2-118">Monitorare gli account utente delle app cloud</span><span class="sxs-lookup"><span data-stu-id="239e2-118">Monitor cloud app user accounts</span></span>

<span data-ttu-id="239e2-119">**Gli account delle app cloud per la revisione** elencano gli account che potrebbero richiedere attenzione.</span><span class="sxs-lookup"><span data-stu-id="239e2-119">**Cloud app accounts for review** lists accounts that may require attention.</span></span>

![Account dell'app cloud per la scheda da rivedere](../../media/cloud-app-accounts-for-review.png)

## <a name="understand-which-cloud-apps-are-used"></a><span data-ttu-id="239e2-121">Comprendere quali app cloud vengono usate</span><span class="sxs-lookup"><span data-stu-id="239e2-121">Understand which cloud apps are used</span></span>

<span data-ttu-id="239e2-122">**Le app cloud individuate (categorie)** mostrano i tipi di app in uso nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="239e2-122">**Discovered cloud apps (categories)** show what kinds of apps are being used in your organization.</span></span> <span data-ttu-id="239e2-123">Si collega al dashboard di Cloud Discovery in Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="239e2-123">It links to the Cloud Discovery dashboard in Cloud App Security.</span></span> <span data-ttu-id="239e2-124">Per altre informazioni, vedi [Guida introduttiva: Usare le app individuate.](https://docs.microsoft.com/cloud-app-security/discovered-apps)</span><span class="sxs-lookup"><span data-stu-id="239e2-124">For more information, see [Quickstart: Work with discovered apps](https://docs.microsoft.com/cloud-app-security/discovered-apps).</span></span>  

![Scheda categorie app cloud individuate](../../media/discovered-cloud-apps-categories.png)

## <a name="monitor-where-users-access-cloud-apps"></a><span data-ttu-id="239e2-126">Monitorare dove gli utenti accedono alle app cloud</span><span class="sxs-lookup"><span data-stu-id="239e2-126">Monitor where users access cloud apps</span></span>

<span data-ttu-id="239e2-127">**I percorsi di attività delle app** cloud mostrano dove gli utenti accedono alle app cloud.</span><span class="sxs-lookup"><span data-stu-id="239e2-127">**Cloud app activity locations** show where users are accessing cloud apps.</span></span>

![Scheda posizioni attività app cloud](../../media/cloud-app-activity-locations.png)

## <a name="monitor-health-for-infrastructure-workloads"></a><span data-ttu-id="239e2-129">Monitorare l'integrità per i carichi di lavoro dell'infrastruttura</span><span class="sxs-lookup"><span data-stu-id="239e2-129">Monitor health for infrastructure workloads</span></span>

<span data-ttu-id="239e2-130">**Integrità dell'infrastruttura** mostra gli avvisi sullo stato di integrità per i carichi di lavoro dell'infrastruttura in Azure Defender.</span><span class="sxs-lookup"><span data-stu-id="239e2-130">**Infrastructure health** shows health status alerts for infrastructure workloads in Azure Defender.</span></span>

<span data-ttu-id="239e2-131">Azure Defender fornisce la gestione unificata della sicurezza e Defender per Office 365 nei carichi di lavoro locali e cloud.</span><span class="sxs-lookup"><span data-stu-id="239e2-131">Azure Defender provides unified security management and Defender for Office 365 across on-premises and cloud workloads.</span></span> <span data-ttu-id="239e2-132">È possibile raccogliere, cercare e analizzare i dati di sicurezza provenienti da origini diverse, inclusi firewall e altre soluzioni partner.</span><span class="sxs-lookup"><span data-stu-id="239e2-132">You can collect, search, and analyze security data from different sources, including firewalls and other partner solutions.</span></span>

<span data-ttu-id="239e2-133">Per ulteriori informazioni, vedere la [documentazione di Azure Defender.](https://docs.microsoft.com/azure/security-center/)</span><span class="sxs-lookup"><span data-stu-id="239e2-133">For more information, see [Azure Defender Documentation](https://docs.microsoft.com/azure/security-center/).</span></span>

![Scheda integrità dell'infrastruttura](../../media/infrastructure-health.png)
