---
title: Configurare le impostazioni di Microsoft Defender Security Center
description: Utilizzare la pagina delle impostazioni per configurare le impostazioni generali, le autorizzazioni, le api e le regole.
keywords: impostazioni, impostazioni generali, autorizzazioni, api, regole
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 5869e8406158eb6d6b2f48b3083cb9011bb3951d
ms.sourcegitcommit: dc1ac43a57fac6f57438859dd668f927d94fdf34
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/07/2021
ms.locfileid: "51604346"
---
# <a name="configure-microsoft-defender-security-center-settings"></a><span data-ttu-id="e282d-104">Configurare le impostazioni di Microsoft Defender Security Center</span><span class="sxs-lookup"><span data-stu-id="e282d-104">Configure Microsoft Defender Security Center settings</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e282d-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="e282d-105">**Applies to:**</span></span>
- [<span data-ttu-id="e282d-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="e282d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e282d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e282d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="e282d-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="e282d-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="e282d-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="e282d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-prefsettings-abovefoldlink)

<span data-ttu-id="e282d-110">Usa il menu **Impostazioni** per modificare le impostazioni generali, le funzionalità avanzate, abilitare l'esperienza di anteprima, le notifiche tramite posta elettronica e la funzionalità di intelligence per le minacce personalizzata.</span><span class="sxs-lookup"><span data-stu-id="e282d-110">Use the **Settings** menu to modify general settings, advanced features, enable the preview experience, email notifications, and the custom threat intelligence feature.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="e282d-111">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="e282d-111">In this section</span></span>

<span data-ttu-id="e282d-112">Argomento</span><span class="sxs-lookup"><span data-stu-id="e282d-112">Topic</span></span> | <span data-ttu-id="e282d-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e282d-113">Description</span></span>
:---|:---
<span data-ttu-id="e282d-114">Impostazioni generali</span><span class="sxs-lookup"><span data-stu-id="e282d-114">General settings</span></span> | <span data-ttu-id="e282d-115">Modificare le impostazioni generali precedentemente definite come parte del processo di onboarding.</span><span class="sxs-lookup"><span data-stu-id="e282d-115">Modify your general settings that were previously defined as part of the onboarding process.</span></span>
<span data-ttu-id="e282d-116">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="e282d-116">Permissions</span></span> | <span data-ttu-id="e282d-117">Gestire l'accesso al portale tramite RBAC e i gruppi di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="e282d-117">Manage portal access using RBAC as well as device groups.</span></span>
<span data-ttu-id="e282d-118">API</span><span class="sxs-lookup"><span data-stu-id="e282d-118">APIs</span></span> | <span data-ttu-id="e282d-119">Abilita l'integrazione di intel e SIEM per le minacce.</span><span class="sxs-lookup"><span data-stu-id="e282d-119">Enable the threat intel and SIEM integration.</span></span>
<span data-ttu-id="e282d-120">Regole</span><span class="sxs-lookup"><span data-stu-id="e282d-120">Rules</span></span> | <span data-ttu-id="e282d-121">Configurare le regole di eliminazione e le impostazioni di automazione.</span><span class="sxs-lookup"><span data-stu-id="e282d-121">Configure suppressions rules and automation settings.</span></span>
<span data-ttu-id="e282d-122">Gestione dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="e282d-122">Device management</span></span> | <span data-ttu-id="e282d-123">Dispositivi onboard e offboard.</span><span class="sxs-lookup"><span data-stu-id="e282d-123">Onboard and offboard devices.</span></span>
<span data-ttu-id="e282d-124">Valutazioni di rete</span><span class="sxs-lookup"><span data-stu-id="e282d-124">Network assessments</span></span> | <span data-ttu-id="e282d-125">Scegli i dispositivi da analizzare regolarmente e aggiungi all'inventario dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="e282d-125">Choose devices to be scanned regularly and added to the device inventory.</span></span>
