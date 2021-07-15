---
title: Determinare il profilo di conformità dell'app
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
description: Determinare il profilo di conformità dell'app.
ms.openlocfilehash: 3d7cac319c31bac40a3aad2f6b9a4c16303f6a20
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420125"
---
# <a name="determine-your-app-compliance-posture"></a><span data-ttu-id="816df-103">Determinare il profilo di conformità dell'app</span><span class="sxs-lookup"><span data-stu-id="816df-103">Determine your app compliance posture</span></span>

><span data-ttu-id="816df-104">*[Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="816df-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="816df-105">La governance delle app di Microsoft consente di valutare rapidamente il profilo di conformità delle app di terze parti e il relativo accesso ai dati nel tenant di Microsoft 365 dalla pagina Panoramica della governance delle app nel [Centro conformità Microsoft 365](https://compliance.microsoft.com/appgovernance).</span><span class="sxs-lookup"><span data-stu-id="816df-105">Microsoft app governance allows you to quickly assess the compliance posture of the third-party apps and their access to data in your Microsoft 365 tenant from the app governance Overview page in the [Microsoft 365 Compliance Center](https://compliance.microsoft.com/appgovernance).</span></span>

![La pagina Panoramica della governance delle app nel Centro conformità Microsoft 365](..\media\manage-app-protection-governance\mapg-cc-overview.png)

>[!Note]
> <span data-ttu-id="816df-107">L'account di accesso deve disporre di uno di [questi ruoli](app-governance-get-started.md#administrator-roles) per visualizzare i dati di governance delle app.</span><span class="sxs-lookup"><span data-stu-id="816df-107">Your sign-in account must have one of [these roles](app-governance-get-started.md#administrator-roles) to view any app governance data.</span></span>
>

<span data-ttu-id="816df-108">In questa pagina puoi visualizzare:</span><span class="sxs-lookup"><span data-stu-id="816df-108">From this page, you can see:</span></span>

- <span data-ttu-id="816df-109">Per le app abilitate per OAuth che usano l'API Microsoft Graph:</span><span class="sxs-lookup"><span data-stu-id="816df-109">For OAuth-enabled apps that use the Microsoft Graph API:</span></span>

  - <span data-ttu-id="816df-110">Numero di app nel tenant</span><span class="sxs-lookup"><span data-stu-id="816df-110">How many are in your tenant</span></span>
  - <span data-ttu-id="816df-111">Numero di app con troppi privilegi</span><span class="sxs-lookup"><span data-stu-id="816df-111">How many might be overprivileged</span></span>
  - <span data-ttu-id="816df-112">Numero di privilegi elevati</span><span class="sxs-lookup"><span data-stu-id="816df-112">How many are high privilege</span></span>

  <span data-ttu-id="816df-113">Da queste informazioni è possibile determinare il livello di rischio per l'organizzazione da app con troppi privilegi e con privilegi elevati.</span><span class="sxs-lookup"><span data-stu-id="816df-113">From this information, you can determine the level of risk to your organization by overprivileged and high privilege apps.</span></span>

- <span data-ttu-id="816df-114">Per gli avvisi:</span><span class="sxs-lookup"><span data-stu-id="816df-114">For alerts:</span></span>

  - <span data-ttu-id="816df-115">Numero di avvisi attivi del tenant</span><span class="sxs-lookup"><span data-stu-id="816df-115">How many active alerts your tenant has</span></span>
  - <span data-ttu-id="816df-116">Numero di avvisi basati sui rilevamenti della governance delle app (**avvisi delle minacce**)</span><span class="sxs-lookup"><span data-stu-id="816df-116">How many are based on app governance detections (**Threat alerts**)</span></span>
  - <span data-ttu-id="816df-117">Numero di avvisi basati sui criteri delle app in uso (**avvisi dei criteri**)</span><span class="sxs-lookup"><span data-stu-id="816df-117">How many are based on app policies you have in place (**Policy alerts**)</span></span>
  - <span data-ttu-id="816df-118">I 10 avvisi più recenti</span><span class="sxs-lookup"><span data-stu-id="816df-118">The 10 latest alerts</span></span>

  <span data-ttu-id="816df-119">Da queste informazioni è possibile determinare la velocità con cui sono generati gli avvisi e il relativo numero di avvisi rilevati e basati su criteri.</span><span class="sxs-lookup"><span data-stu-id="816df-119">From this information, you can determine how quickly alerts are being generated and the relative number of detected and policy-based alerts.</span></span>

- <span data-ttu-id="816df-120">Per l’accesso ai dati e alle risorse:</span><span class="sxs-lookup"><span data-stu-id="816df-120">For data and resources access:</span></span>

  - <span data-ttu-id="816df-121">L’accesso ai dati dell'API dell'applicazione negli ultimi 90 giorni</span><span class="sxs-lookup"><span data-stu-id="816df-121">The application API data access in the last 90 days</span></span>
  - <span data-ttu-id="816df-122">L’utilizzo complessivo delle risorse principali negli ultimi 90 giorni</span><span class="sxs-lookup"><span data-stu-id="816df-122">The usage of the top resources in the last 90 days</span></span>

  <span data-ttu-id="816df-123">Da queste informazioni è possibile determinare il verificarsi di picchi anomali relativi all'accesso ai dati nel tenant di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="816df-123">From this information, you can determine if there are anomalous spikes in access to the data in your Microsoft 365 tenant.</span></span>
