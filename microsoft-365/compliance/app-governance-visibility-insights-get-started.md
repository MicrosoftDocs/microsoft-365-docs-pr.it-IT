---
title: Introduzione a visibilità e dati analitici
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Introduzione a visibilità e dati analitici.
ms.openlocfilehash: 93be3557c32345e81c7126b669ead8edf8ebac21
ms.sourcegitcommit: 997a21b83795789cda0a6b4a77f9985a3233d0c0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2021
ms.locfileid: "53430481"
---
# <a name="get-started-with-visibility-and-insights"></a><span data-ttu-id="d0139-103">Introduzione a visibilità e dati analitici</span><span class="sxs-lookup"><span data-stu-id="d0139-103">Get started with visibility and insights</span></span>

><span data-ttu-id="d0139-104">*[Indicazioni sulle licenze Microsoft 365 per la sicurezza e la conformità](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="d0139-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="d0139-105">Il primo punto da cui iniziare è il dashboard di governance delle app in [https://aka.ms/appgovernance](https://aka.ms/appgovernance).</span><span class="sxs-lookup"><span data-stu-id="d0139-105">The first place to get started is the app governance dashboard at [https://aka.ms/appgovernance](https://aka.ms/appgovernance).</span></span> <span data-ttu-id="d0139-106">Tenere presente che l'account di accesso deve disporre di uno di [questi ruoli di amministratore della governance delle app](app-governance-get-started.md#administrator-roles) per visualizzare i dati di governance.</span><span class="sxs-lookup"><span data-stu-id="d0139-106">Note that your sign-in account must have one of [these app governance administrator roles](app-governance-get-started.md#administrator-roles) to view any app governance data.</span></span>

![Pagina della governance delle app nel Centro conformità Microsoft 365](..\media\manage-app-protection-governance\mapg-cc-overview.png)

<span data-ttu-id="d0139-108">È anche possibile accedere al dashboard di governance delle app dall'**Interfaccia di amministrazione di Microsoft 365 > Centro conformità Microsoft 365 > Governance delle app > Pagina panoramica**.</span><span class="sxs-lookup"><span data-stu-id="d0139-108">You can also access the app governance dashboard from **Microsoft 365 admin center > Microsoft 365 Compliance Center > App governance > Overview page**.</span></span>

## <a name="whats-available-on-the-dashboard"></a><span data-ttu-id="d0139-109">Elementi disponibili nel dashboard</span><span class="sxs-lookup"><span data-stu-id="d0139-109">What’s available on the dashboard</span></span>

<span data-ttu-id="d0139-110">Il dashboard contiene un riepilogo dei componenti dell'ecosistema delle app Microsoft 365 nel tenant:</span><span class="sxs-lookup"><span data-stu-id="d0139-110">The dashboard contains a summary of the components of the Microsoft 365 app ecosystem in the tenant:</span></span>

- <span data-ttu-id="d0139-111">**Riepilogo del tenant**: numero delle categorie principali di app e avvisi.</span><span class="sxs-lookup"><span data-stu-id="d0139-111">**Tenant summary**: The count of key app and alert categories.</span></span>
- <span data-ttu-id="d0139-112">**Avvisi di rilevamento e dei criteri**: gli avvisi attivi più recenti nel tenant</span><span class="sxs-lookup"><span data-stu-id="d0139-112">**Detection and policy alerts**: The most recent active alerts in the tenant</span></span>
- <span data-ttu-id="d0139-113">**Accesso ai dati e alle risorse**: accesso aggregato all'API dell'applicazione e utilizzo complessivo delle risorse principali nel tenant.</span><span class="sxs-lookup"><span data-stu-id="d0139-113">**Data and resources access**: Aggregate application API access and overall usage of top resources in the tenant.</span></span> <span data-ttu-id="d0139-114">Passare il puntatore del mouse su ogni colonna mensile del grafico per visualizzare il valore corrispondente.</span><span class="sxs-lookup"><span data-stu-id="d0139-114">Mouse over each month column in the graph to see the corresponding value.</span></span>
- <span data-ttu-id="d0139-115">**Migliorare la protezione e la governance delle app**: azioni consigliate, ad esempio la creazione di criteri di utilizzo o autorizzazione delle app.</span><span class="sxs-lookup"><span data-stu-id="d0139-115">**Improve your app protection and governance**: Recommended actions such as creating an app usage or permissions policy.</span></span>
- <span data-ttu-id="d0139-116">**App più popolari in base alla categoria**: le app principali ordinate in base alle categorie seguenti:</span><span class="sxs-lookup"><span data-stu-id="d0139-116">**Top apps by categories**: The top apps sorted by these categories:</span></span>
  
  - <span data-ttu-id="d0139-117">**Tutte le categorie**: ordina in base a tutte le categorie disponibili.</span><span class="sxs-lookup"><span data-stu-id="d0139-117">**All categories**: Sorts across all available categories.</span></span>
  - <span data-ttu-id="d0139-118">**Privilegi elevati**: i privilegi elevati sono una categoria determinata internamente in base all'apprendimento automatico e ai segnali della piattaforma.</span><span class="sxs-lookup"><span data-stu-id="d0139-118">**High privilege**: High privilege is an internally determined category based on platform machine learning and signals.</span></span>
  - <span data-ttu-id="d0139-119">**Livello di privilegi troppo elevato**: quando la governance dell'app riceve dati di telemetria che indicano che un'autorizzazione concessa a un'applicazione non è stata usata nei 90 giorni precedenti, tale applicazione ha un livello di privilegi troppo elevato.</span><span class="sxs-lookup"><span data-stu-id="d0139-119">**Overprivileged**: When app governance receives telemetry that indicates that a permission granted to an application has not been used in the last 90 days, that application is overprivileged.</span></span> <span data-ttu-id="d0139-120">La governance dell'app deve essere eseguita per almeno 90 giorni per determinare se un'app ha un livello di privilegi troppo elevato.</span><span class="sxs-lookup"><span data-stu-id="d0139-120">App governance must be operating for at least 90 days to determine if any app is overprivileged.</span></span>  
  - <span data-ttu-id="d0139-121">**Non verificate**: le applicazioni che non hanno ricevuto la [certificazione dell'editore](https://docs.microsoft.com/azure/active-directory/develop/publisher-verification-overview) vengono considerate non verificate.</span><span class="sxs-lookup"><span data-stu-id="d0139-121">**Unverified**: Applications that have not received [publisher certification](https://docs.microsoft.com/azure/active-directory/develop/publisher-verification-overview) are considered unverified.</span></span>
  - <span data-ttu-id="d0139-122">**Solo app**: le [autorizzazioni dell'applicazione](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#permission-types) vengono usate dalle app che possono essere eseguite senza un utente connesso.</span><span class="sxs-lookup"><span data-stu-id="d0139-122">**App only**: [Application permissions](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#permission-types) are used by apps that can run without a signed-in user present.</span></span> <span data-ttu-id="d0139-123">Le app con autorizzazioni per accedere ai dati nel tenant rappresentano sono potenzialmente ad alto rischio.</span><span class="sxs-lookup"><span data-stu-id="d0139-123">Apps with permissions to access data across the tenant are potentially a higher risk.</span></span>
  - <span data-ttu-id="d0139-124">**Nuove app**: le nuove app Microsoft 365 registrate negli ultimi sette giorni.</span><span class="sxs-lookup"><span data-stu-id="d0139-124">**New apps**: New Microsoft 365 apps that have been registered in the last seven days.</span></span>  

## <a name="next-step"></a><span data-ttu-id="d0139-125">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="d0139-125">Next step</span></span>

<span data-ttu-id="d0139-126">[Ottenere dati analitici su un'app specifica](app-governance-visibility-insights-view-apps.md).</span><span class="sxs-lookup"><span data-stu-id="d0139-126">[Get detailed insights on a specific app](app-governance-visibility-insights-view-apps.md).</span></span>
