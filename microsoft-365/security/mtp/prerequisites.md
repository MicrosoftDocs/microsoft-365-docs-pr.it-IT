---
title: Prerequisiti di Microsoft Threat Protection
description: Informazioni sui requisiti di licenza, hardware e software e altre impostazioni di configurazione per Microsoft Threat Protection
keywords: requisiti, prerequisiti, hardware, software, browser, MTP, M365, License, E5, a5, EMS, Purchase
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 71e7b532e046015dd64e51fd422d276433d65b3a
ms.sourcegitcommit: 6ea9a910a8106a5f1aa589c55d166bfa67fd12a8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/18/2020
ms.locfileid: "44280535"
---
# <a name="microsoft-threat-protection-prerequisites"></a><span data-ttu-id="12682-104">Prerequisiti di Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="12682-104">Microsoft Threat Protection prerequisites</span></span>

<span data-ttu-id="12682-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="12682-105">**Applies to:**</span></span>
- <span data-ttu-id="12682-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="12682-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="12682-107">Informazioni sui requisiti di licenza, hardware e software e altre impostazioni di configurazione per il provisioning e l'utilizzo di Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="12682-107">Learn about the licensing, hardware and software requirements, and other configuration settings to provision and use Microsoft Threat Protection.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="12682-108">Requisiti per la licenza</span><span class="sxs-lookup"><span data-stu-id="12682-108">Licensing requirements</span></span>

>[!IMPORTANT]
><span data-ttu-id="12682-109">A partire dal 12 maggio 2020, Microsoft eseguirà gradualmente nuove esperienze ottimizzate in merito ai requisiti di licenza e [all'attivazione di Microsoft Threat Protection](mtp-enable.md).</span><span class="sxs-lookup"><span data-stu-id="12682-109">Starting May 12, 2020, Microsoft will gradually roll out new, optimized experiences around licensing requirements and [turning on Microsoft Threat Protection](mtp-enable.md).</span></span> <span data-ttu-id="12682-110">Per alcune settimane durante questo periodo, alcuni clienti inizieranno a visualizzare le modifiche apportate alle esperienze del portale.</span><span class="sxs-lookup"><span data-stu-id="12682-110">For several weeks during this period, some customers will start to see changes to their portal experiences.</span></span> <span data-ttu-id="12682-111">Le informazioni sulle nuove esperienze sono state contrassegnate come **nuova esperienza** in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="12682-111">Information about the new experiences are marked **New experience** in this article.</span></span>

<span data-ttu-id="12682-112">Per utilizzare Microsoft Threat Protection, è necessaria una singola licenza o una combinazione di licenze.</span><span class="sxs-lookup"><span data-stu-id="12682-112">To use Microsoft Threat Protection, you need either a single license or a combination of licenses.</span></span> <span data-ttu-id="12682-113">Queste licenze o combinazioni di licenze consentono di accedere alle funzionalità di protezione dalle minacce di Microsoft senza costi aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="12682-113">These licenses or license combinations give you access to Microsoft Threat Protection features without additional cost.</span></span>

### <a name="single-license"></a><span data-ttu-id="12682-114">Licenza singola</span><span class="sxs-lookup"><span data-stu-id="12682-114">Single license</span></span>
<span data-ttu-id="12682-115">È possibile utilizzare *una* delle licenze seguenti:</span><span class="sxs-lookup"><span data-stu-id="12682-115">You can use *one* of the following licenses:</span></span>

- <span data-ttu-id="12682-116">Microsoft 365 E5 o a5</span><span class="sxs-lookup"><span data-stu-id="12682-116">Microsoft 365 E5 or A5</span></span>
- <span data-ttu-id="12682-117">Sicurezza di Microsoft 365 E5 o sicurezza a5</span><span class="sxs-lookup"><span data-stu-id="12682-117">Microsoft 365 E5 Security or A5 Security</span></span>

### <a name="combination-of-licenses"></a><span data-ttu-id="12682-118">Combinazione di licenze</span><span class="sxs-lookup"><span data-stu-id="12682-118">Combination of licenses</span></span>
<span data-ttu-id="12682-119">È inoltre possibile utilizzare una combinazione di licenze per gli abbonamenti E5 o a5 a Office 365, *Enterprise Mobility + Security (EMS)* e Windows.</span><span class="sxs-lookup"><span data-stu-id="12682-119">You can also use a combination of licenses for E5 or A5 subscriptions to Office 365, *Enterprise Mobility + Security (EMS)*, and Windows.</span></span> <span data-ttu-id="12682-120">La combinazione di licenze deve includere *tutte* le licenze seguenti:</span><span class="sxs-lookup"><span data-stu-id="12682-120">The license combination must include *all* of these licenses:</span></span>

- <span data-ttu-id="12682-121">Office 365 E5 o a5</span><span class="sxs-lookup"><span data-stu-id="12682-121">Office 365 E5 or A5</span></span>
- <span data-ttu-id="12682-122">*Enterprise Mobility + Security (EMS)* E5 o a5</span><span class="sxs-lookup"><span data-stu-id="12682-122">*Enterprise Mobility + Security (EMS)* E5 or A5</span></span>
- <span data-ttu-id="12682-123">Windows 10 Enterprise E5 o a5</span><span class="sxs-lookup"><span data-stu-id="12682-123">Windows 10 Enterprise E5 or A5</span></span>

<span data-ttu-id="12682-124">Per ulteriori informazioni, [vedere i piani del servizio Microsoft 365 Enterprise](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span><span class="sxs-lookup"><span data-stu-id="12682-124">For more information, [view the Microsoft 365 Enterprise service plans](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span></span>

> <span data-ttu-id="12682-125">Non si dispone ancora di una licenza?</span><span class="sxs-lookup"><span data-stu-id="12682-125">Don't have license yet?</span></span> [<span data-ttu-id="12682-126">Provare o acquistare un abbonamento a Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="12682-126">Try or buy a Microsoft 365 subscription</span></span>](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)


<span data-ttu-id="12682-127">**Nuova esperienza:** A partire dal 12 maggio 2020, i clienti riceveranno gradualmente le modifiche apportate a questa esperienza.</span><span class="sxs-lookup"><span data-stu-id="12682-127">**New experience:** Starting May 12, 2020, customers will gradually receive changes to this experience.</span></span> <span data-ttu-id="12682-128">Per gli utenti con la nuova esperienza, la possibilità di abilitare Microsoft Threat Protection sarà disponibile per *tutti* i clienti con una delle licenze seguenti:</span><span class="sxs-lookup"><span data-stu-id="12682-128">For those with the new experience, the option to turn on Microsoft Threat Protection will be available to *all* customers with any of the following licenses:</span></span>

- <span data-ttu-id="12682-129">Microsoft 365 E5 o a5</span><span class="sxs-lookup"><span data-stu-id="12682-129">Microsoft 365 E5 or A5</span></span>
- <span data-ttu-id="12682-130">Sicurezza di Microsoft 365 E5 o sicurezza a5</span><span class="sxs-lookup"><span data-stu-id="12682-130">Microsoft 365 E5 Security or A5 Security</span></span>
- <span data-ttu-id="12682-131">Windows 10 Enterprise E5 o a5</span><span class="sxs-lookup"><span data-stu-id="12682-131">Windows 10 Enterprise E5 or A5</span></span>
- <span data-ttu-id="12682-132">Enterprise Mobility + Security (EMS) E5 o a5</span><span class="sxs-lookup"><span data-stu-id="12682-132">Enterprise Mobility + Security (EMS) E5 or A5</span></span> 
- <span data-ttu-id="12682-133">Office 365 E5 o a5</span><span class="sxs-lookup"><span data-stu-id="12682-133">Office 365 E5 or A5</span></span>
- <span data-ttu-id="12682-134">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="12682-134">Microsoft Defender Advanced Threat Protection</span></span> 
- <span data-ttu-id="12682-135">Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="12682-135">Azure Advanced Threat Protection</span></span> 
- <span data-ttu-id="12682-136">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="12682-136">Microsoft Cloud App Security</span></span> 
- <span data-ttu-id="12682-137">Protezione avanzata dalle minacce di Office 365 (piano 2)</span><span class="sxs-lookup"><span data-stu-id="12682-137">Office 365 Advanced Threat Protection (Plan 2)</span></span> 

### <a name="check-your-existing--licenses"></a><span data-ttu-id="12682-138">Controllare le licenze esistenti</span><span class="sxs-lookup"><span data-stu-id="12682-138">Check your existing  licenses</span></span>
<span data-ttu-id="12682-139">Accedere a Microsoft 365 Admin Center ([admin.Microsoft.com](https://admin.microsoft.com/)) per visualizzare le licenze esistenti.</span><span class="sxs-lookup"><span data-stu-id="12682-139">Go to Microsoft 365 admin center ([admin.microsoft.com](https://admin.microsoft.com/)) to view your existing licenses.</span></span> <span data-ttu-id="12682-140">Nell'interfaccia di amministrazione, andare in **Fatturazione** > **Licenze**.</span><span class="sxs-lookup"><span data-stu-id="12682-140">In the admin center, go to **Billing** > **Licenses**.</span></span>

>[!NOTE]
> <span data-ttu-id="12682-141">Per poter visualizzare le informazioni sulla licenza, è necessario essere assegnati al ruolo di **amministratore di fatturazione** o **lettore globale** [in Azure ad](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) .</span><span class="sxs-lookup"><span data-stu-id="12682-141">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see license information.</span></span> <span data-ttu-id="12682-142">Se si verificano problemi di accesso, rivolgersi a un amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="12682-142">If you encounter access problems, contact a global admin.</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="12682-143">Requisiti per il browser</span><span class="sxs-lookup"><span data-stu-id="12682-143">Browser requirements</span></span>
<span data-ttu-id="12682-144">Accedere a Microsoft Threat Protection nel centro sicurezza Microsoft 365 utilizzando Microsoft Edge, Internet Explorer 11 o qualsiasi Web browser compatibile con HTML 5.</span><span class="sxs-lookup"><span data-stu-id="12682-144">Access Microsoft Threat Protection in the Microsoft 365 security center using Microsoft Edge, Internet Explorer 11, or any HTML 5 compliant web browser.</span></span>

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a><span data-ttu-id="12682-145">Disponibilità a noi GCC, GCC High e altre istituzioni governative degli Stati Uniti</span><span class="sxs-lookup"><span data-stu-id="12682-145">Availability to US GCC, GCC High, and other US government institutions</span></span>
<span data-ttu-id="12682-146">Attualmente, Microsoft Threat Protection *non* è disponibile per:</span><span class="sxs-lookup"><span data-stu-id="12682-146">Currently, Microsoft Threat Protection is *not* available to:</span></span>
- <span data-ttu-id="12682-147">Cloud (GCC) del governo degli Stati Uniti</span><span class="sxs-lookup"><span data-stu-id="12682-147">US Government Community Cloud (GCC)</span></span>
- <span data-ttu-id="12682-148">Cloud degli Stati Uniti nube alto (GCC High)</span><span class="sxs-lookup"><span data-stu-id="12682-148">US Government Community Cloud High (GCC High)</span></span>
- <span data-ttu-id="12682-149">Dipartimento della difesa degli Stati Uniti</span><span class="sxs-lookup"><span data-stu-id="12682-149">US Department of Defense</span></span>
- <span data-ttu-id="12682-150">Tutte le istituzioni governative degli Stati Uniti con licenze commerciali</span><span class="sxs-lookup"><span data-stu-id="12682-150">All US government institutions with commercial licenses</span></span>

## <a name="related-topics"></a><span data-ttu-id="12682-151">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="12682-151">Related topics</span></span>
- [<span data-ttu-id="12682-152">Panoramica su Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="12682-152">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="12682-153">Attivare Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="12682-153">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)
