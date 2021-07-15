---
title: Informazioni su visibilità e dati analitici
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
description: Informazioni su visibilità e dati analitici.
ms.openlocfilehash: ee485c972193c515bafec55f58a7a89aa1f567f1
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420126"
---
# <a name="learn-about-visibility-and-insights"></a><span data-ttu-id="eaebe-103">Informazioni su visibilità e dati analitici</span><span class="sxs-lookup"><span data-stu-id="eaebe-103">Learn about visibility and insights</span></span>

><span data-ttu-id="eaebe-104">*[Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="eaebe-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="eaebe-105">Con la governance delle app Microsoft, è possibile ottenere rapidamente visibilità e dati analitici significativi sull'ecosistema di applicazioni Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="eaebe-105">With Microsoft app governance, you can quickly gain visibility and meaningful insights on your Microsoft 365 application ecosystem.</span></span> <span data-ttu-id="eaebe-106">È necessario iniziare dalla dashboard di governance delle app che fornisce un riepilogo dettagliato degli avvisi e delle app nel tenant che richiedono l'attenzione dell'amministratore.</span><span class="sxs-lookup"><span data-stu-id="eaebe-106">You start from the app governance dashboard that provides a high-level summary of the alerts and apps in your tenant that require administrator attention.</span></span>

<span data-ttu-id="eaebe-107">La visibilità e i dati analitici della governance delle app consente di visualizzare:</span><span class="sxs-lookup"><span data-stu-id="eaebe-107">With app governance visibility and insights, you can see:</span></span>

- <span data-ttu-id="eaebe-108">Un elenco delle app abilitate per OAuth che accedono ai dati di Microsoft 365 tramite le API di Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="eaebe-108">A list of the OAuth-enabled apps that access Microsoft 365 data via Microsoft Graph APIs.</span></span>
- <span data-ttu-id="eaebe-109">Una visualizzazione dettagliata delle attività dell'app in modo da consentire all’utente di reagire o rispondere di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="eaebe-109">A rich view on app activities so that you can react or respond to them.</span></span>

>[!Note]
><span data-ttu-id="eaebe-110">Le app esclusive di Azure, a cui non sono concesse le autorizzazioni necessarie per accedere alle risorse Microsoft 365, non vengono visualizzate nella governance delle app.</span><span class="sxs-lookup"><span data-stu-id="eaebe-110">Azure-only apps that are not granted permissions to access Microsoft 365 resources are not displayed in app governance.</span></span>
>

<span data-ttu-id="eaebe-111">Per una panoramica dei ruoli di amministratore necessari alla visibilità e ai dati analitici, vedere [Ruoli di amministratore](app-governance-get-started.md#administrator-roles).</span><span class="sxs-lookup"><span data-stu-id="eaebe-111">See [administrator roles](app-governance-get-started.md#administrator-roles) for an overview of required administrator roles for visibility and insights.</span></span>

<!--
From messaging doc, page 21:

View M365 App List & Metadata
View M365 App List of Consented Users
View M365 App Permissions
View M365 App Permission Usage
View Over permissioned Apps
Aggregate M365 API Usage Data by Workload (count, download/upload)
Per-App M365 API Usage Data by Workload (count, download/upload)
Per-User M365 API Usage Data by Workload (count, download/upload)
M365 API Usage Data For High-Value/Classified Assets (count, download/upload)
M365 API Error Analysis per App
-->

<span data-ttu-id="eaebe-112">Con la governance delle app, è possibile visualizzare:</span><span class="sxs-lookup"><span data-stu-id="eaebe-112">With app governance, you can see:</span></span>

- <span data-ttu-id="eaebe-113">Una dashboard di tutti i dati analitici.</span><span class="sxs-lookup"><span data-stu-id="eaebe-113">A dashboard of all insights.</span></span>
- <span data-ttu-id="eaebe-114">I dati a cui hanno avuto accesso una o tutte le app con dati analitici a livello di carico di lavoro e utente.</span><span class="sxs-lookup"><span data-stu-id="eaebe-114">Data accessed by single and all apps with workload and user level insights.</span></span>
- <span data-ttu-id="eaebe-115">Informazioni e metadati dell'app, ad esempio autorizzazioni, data di registrazione e certificazione.</span><span class="sxs-lookup"><span data-stu-id="eaebe-115">App information and metadata, such as permissions, registration date, and certification.</span></span>
- <span data-ttu-id="eaebe-116">Informazioni e metadati dell'autore, ad esempio nome e stato di verifica.</span><span class="sxs-lookup"><span data-stu-id="eaebe-116">Publisher information and metadata, such as name and verification status.</span></span>
- <span data-ttu-id="eaebe-117">Utilizzo delle principali risorse (e-mail e file) nel tenant.</span><span class="sxs-lookup"><span data-stu-id="eaebe-117">Usage of top resources (emails and files) across the tenant.</span></span>
- <span data-ttu-id="eaebe-118">Dati analitici su:</span><span class="sxs-lookup"><span data-stu-id="eaebe-118">Insights on:</span></span>

  - <span data-ttu-id="eaebe-119">App con privilegi elevati.</span><span class="sxs-lookup"><span data-stu-id="eaebe-119">High-privileged apps.</span></span>
  - <span data-ttu-id="eaebe-120">App con troppi privilegi.</span><span class="sxs-lookup"><span data-stu-id="eaebe-120">Overprivileged apps.</span></span>
  - <span data-ttu-id="eaebe-121">App a utilizzo elevato.</span><span class="sxs-lookup"><span data-stu-id="eaebe-121">High-usage apps.</span></span>
  - <span data-ttu-id="eaebe-122">Principali utenti autorizzati e relativi dati a cui può accedere un'app specifica.</span><span class="sxs-lookup"><span data-stu-id="eaebe-122">Top consented users whose data a specific app can access.</span></span>
  - <span data-ttu-id="eaebe-123">Account prioritari con dati a cui un'app specifica può accedere.</span><span class="sxs-lookup"><span data-stu-id="eaebe-123">Priority accounts who have data that a specific app can access.</span></span>

- <span data-ttu-id="eaebe-124">Una visualizzazione cumulativa degli utenti che accedono alle app.</span><span class="sxs-lookup"><span data-stu-id="eaebe-124">A cumulative view of users accessing apps.</span></span>
- <span data-ttu-id="eaebe-125">Dati analitici degli avvisi.</span><span class="sxs-lookup"><span data-stu-id="eaebe-125">Alerts insights.</span></span>
- <span data-ttu-id="eaebe-126">Dati analitici sull'elenco dei criteri.</span><span class="sxs-lookup"><span data-stu-id="eaebe-126">Policy list insights.</span></span>
<span data-ttu-id="eaebe-127"><!--></span><span class="sxs-lookup"><span data-stu-id="eaebe-127"><!--></span></span>
- <span data-ttu-id="eaebe-128">Criteri creati in MCAS nel portale di governance delle app.</span><span class="sxs-lookup"><span data-stu-id="eaebe-128">Policies created in MCAS in the app governance portal.</span></span>
-->
- <span data-ttu-id="eaebe-129">Avvisi per le app abilitate per OAuth generati in MCAS, nel portale di governance delle app.</span><span class="sxs-lookup"><span data-stu-id="eaebe-129">Alerts for OAuth apps generated in MCAS, in the app governance portal.</span></span>

<span data-ttu-id="eaebe-130">È inoltre possibile:</span><span class="sxs-lookup"><span data-stu-id="eaebe-130">You can also:</span></span>

- <span data-ttu-id="eaebe-131">Eseguire il drill-down di una singola app (pagina dell'app) con tutti i dati analitici associati.</span><span class="sxs-lookup"><span data-stu-id="eaebe-131">Drill down to a single app (app page) with all its associated insights.</span></span>
- <span data-ttu-id="eaebe-132">Eseguire il drill-down degli utenti principali in base ai dati e agli account prioritari all'interno di una singola app.</span><span class="sxs-lookup"><span data-stu-id="eaebe-132">Drill-down into top users by data, and priority accounts within a single app.</span></span>

## <a name="next-step"></a><span data-ttu-id="eaebe-133">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="eaebe-133">Next step</span></span>

[<span data-ttu-id="eaebe-134">Introduzione ai dati analitici dell’applicazione</span><span class="sxs-lookup"><span data-stu-id="eaebe-134">Get started with application insights.</span></span>](app-governance-visibility-insights-get-started.md)
