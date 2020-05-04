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
ms.openlocfilehash: dfc2136f04ed128fc655386c6eef7b91c5e5ef3a
ms.sourcegitcommit: bd8d55f82ca008af1b93a9bb4d1545f68e8188ad
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2020
ms.locfileid: "44011275"
---
# <a name="microsoft-threat-protection-prerequisites"></a><span data-ttu-id="51594-104">Prerequisiti di Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="51594-104">Microsoft Threat Protection prerequisites</span></span>

<span data-ttu-id="51594-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="51594-105">**Applies to:**</span></span>
- <span data-ttu-id="51594-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="51594-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="51594-107">Informazioni sui requisiti di licenza, hardware e software e altre impostazioni di configurazione per il provisioning e l'utilizzo di Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="51594-107">Learn about the licensing, hardware and software requirements, and other configuration settings to provision and use Microsoft Threat Protection.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="51594-108">Requisiti per la licenza</span><span class="sxs-lookup"><span data-stu-id="51594-108">Licensing requirements</span></span>

>[!IMPORTANT]
><span data-ttu-id="51594-109">A partire dal 3 maggio 2020, Microsoft eseguirà gradualmente nuove esperienze ottimizzate in merito ai requisiti di licenza e [all'attivazione di Microsoft Threat Protection](mtp-enable.md).</span><span class="sxs-lookup"><span data-stu-id="51594-109">Starting May 3, 2020, Microsoft will gradually roll out new, optimized experiences around licensing requirements and [turning on Microsoft Threat Protection](mtp-enable.md).</span></span> <span data-ttu-id="51594-110">Per alcune settimane durante questo periodo, alcuni clienti inizieranno a visualizzare le modifiche apportate alle esperienze del portale.</span><span class="sxs-lookup"><span data-stu-id="51594-110">For several weeks during this period, some customers will start to see changes to their portal experiences.</span></span> <span data-ttu-id="51594-111">Le informazioni sulle nuove esperienze sono state contrassegnate come **nuova esperienza** in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="51594-111">Information about the new experiences are marked **New experience** in this article.</span></span>

<span data-ttu-id="51594-112">Per utilizzare Microsoft Threat Protection, è necessaria una singola licenza o una combinazione di licenze.</span><span class="sxs-lookup"><span data-stu-id="51594-112">To use Microsoft Threat Protection, you need either a single license or a combination of licenses.</span></span> <span data-ttu-id="51594-113">Queste licenze o combinazioni di licenze consentono di accedere alle funzionalità di protezione dalle minacce di Microsoft senza costi aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="51594-113">These licenses or license combinations give you access to Microsoft Threat Protection features without additional cost.</span></span>

### <a name="single-license"></a><span data-ttu-id="51594-114">Licenza singola</span><span class="sxs-lookup"><span data-stu-id="51594-114">Single license</span></span>
<span data-ttu-id="51594-115">È possibile utilizzare *una* delle licenze seguenti:</span><span class="sxs-lookup"><span data-stu-id="51594-115">You can use *one* of the following licenses:</span></span>

- <span data-ttu-id="51594-116">Microsoft 365 E5 o a5</span><span class="sxs-lookup"><span data-stu-id="51594-116">Microsoft 365 E5 or A5</span></span>
- <span data-ttu-id="51594-117">Sicurezza di Microsoft 365 E5 o sicurezza a5</span><span class="sxs-lookup"><span data-stu-id="51594-117">Microsoft 365 E5 Security or A5 Security</span></span>

### <a name="combination-of-licenses"></a><span data-ttu-id="51594-118">Combinazione di licenze</span><span class="sxs-lookup"><span data-stu-id="51594-118">Combination of licenses</span></span>
<span data-ttu-id="51594-119">È inoltre possibile utilizzare una combinazione di licenze per gli abbonamenti E5 o a5 a Office 365, *Enterprise Mobility + Security (EMS)* e Windows.</span><span class="sxs-lookup"><span data-stu-id="51594-119">You can also use a combination of licenses for E5 or A5 subscriptions to Office 365, *Enterprise Mobility + Security (EMS)*, and Windows.</span></span> <span data-ttu-id="51594-120">La combinazione di licenze deve includere *tutte* le licenze seguenti:</span><span class="sxs-lookup"><span data-stu-id="51594-120">The license combination must include *all* of these licenses:</span></span>

- <span data-ttu-id="51594-121">Office 365 E5 o a5</span><span class="sxs-lookup"><span data-stu-id="51594-121">Office 365 E5 or A5</span></span>
- <span data-ttu-id="51594-122">*Enterprise Mobility + Security (EMS)* E5 o a5</span><span class="sxs-lookup"><span data-stu-id="51594-122">*Enterprise Mobility + Security (EMS)* E5 or A5</span></span>
- <span data-ttu-id="51594-123">Windows 10 Enterprise E5 o a5</span><span class="sxs-lookup"><span data-stu-id="51594-123">Windows 10 Enterprise E5 or A5</span></span>

<span data-ttu-id="51594-124">Per ulteriori informazioni, [vedere i piani del servizio Microsoft 365 Enterprise](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span><span class="sxs-lookup"><span data-stu-id="51594-124">For more information, [view the Microsoft 365 Enterprise service plans](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span></span>

> <span data-ttu-id="51594-125">Non si dispone ancora di una licenza?</span><span class="sxs-lookup"><span data-stu-id="51594-125">Don't have license yet?</span></span> [<span data-ttu-id="51594-126">Provare o acquistare un abbonamento a Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="51594-126">Try or buy a Microsoft 365 subscription</span></span>](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)


<span data-ttu-id="51594-127">**Nuova esperienza:** A partire dal 3 maggio 2020, i clienti riceveranno gradualmente le modifiche apportate a questa esperienza.</span><span class="sxs-lookup"><span data-stu-id="51594-127">**New experience:** Starting May 3, 2020, customers will gradually receive changes to this experience.</span></span> <span data-ttu-id="51594-128">Per gli utenti con la nuova esperienza, la possibilità di abilitare Microsoft Threat Protection sarà disponibile per *tutti* i clienti con una delle licenze seguenti:</span><span class="sxs-lookup"><span data-stu-id="51594-128">For those with the new experience, the option to turn on Microsoft Threat Protection will be available to *all* customers with any of the following licenses:</span></span>

- <span data-ttu-id="51594-129">Microsoft 365 E5 o a5</span><span class="sxs-lookup"><span data-stu-id="51594-129">Microsoft 365 E5 or A5</span></span>
- <span data-ttu-id="51594-130">Sicurezza di Microsoft 365 E5 o sicurezza a5</span><span class="sxs-lookup"><span data-stu-id="51594-130">Microsoft 365 E5 Security or A5 Security</span></span>
- <span data-ttu-id="51594-131">Windows 10 Enterprise E5 o a5</span><span class="sxs-lookup"><span data-stu-id="51594-131">Windows 10 Enterprise E5 or A5</span></span>
- <span data-ttu-id="51594-132">Enterprise Mobility + Security (EMS) E5 o a5</span><span class="sxs-lookup"><span data-stu-id="51594-132">Enterprise Mobility + Security (EMS) E5 or A5</span></span> 
- <span data-ttu-id="51594-133">Office 365 E5 o a5</span><span class="sxs-lookup"><span data-stu-id="51594-133">Office 365 E5 or A5</span></span>
- <span data-ttu-id="51594-134">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="51594-134">Microsoft Defender Advanced Threat Protection</span></span> 
- <span data-ttu-id="51594-135">Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="51594-135">Azure Advanced Threat Protection</span></span> 
- <span data-ttu-id="51594-136">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="51594-136">Microsoft Cloud App Security</span></span> 
- <span data-ttu-id="51594-137">Protezione avanzata dalle minacce di Office 365 (piano 2)</span><span class="sxs-lookup"><span data-stu-id="51594-137">Office 365 Advanced Threat Protection (Plan 2)</span></span> 

### <a name="check-your-existing--licenses"></a><span data-ttu-id="51594-138">Controllare le licenze esistenti</span><span class="sxs-lookup"><span data-stu-id="51594-138">Check your existing  licenses</span></span>
<span data-ttu-id="51594-139">Accedere a Microsoft 365 Admin Center ([admin.Microsoft.com](https://admin.microsoft.com/)) per visualizzare le licenze esistenti.</span><span class="sxs-lookup"><span data-stu-id="51594-139">Go to Microsoft 365 admin center ([admin.microsoft.com](https://admin.microsoft.com/)) to view your existing licenses.</span></span> <span data-ttu-id="51594-140">Nell'interfaccia di amministrazione, andare in **Fatturazione** > **Licenze**.</span><span class="sxs-lookup"><span data-stu-id="51594-140">In the admin center, go to **Billing** > **Licenses**.</span></span>

>[!NOTE]
> <span data-ttu-id="51594-141">Per poter visualizzare le informazioni sulla licenza, è necessario essere assegnati al ruolo di **amministratore di fatturazione** o **lettore globale** [in Azure ad](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) .</span><span class="sxs-lookup"><span data-stu-id="51594-141">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see license information.</span></span> <span data-ttu-id="51594-142">Se si verificano problemi di accesso, rivolgersi a un amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="51594-142">If you encounter access problems, contact a global admin.</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="51594-143">Requisiti per il browser</span><span class="sxs-lookup"><span data-stu-id="51594-143">Browser requirements</span></span>
<span data-ttu-id="51594-144">Accedere a Microsoft Threat Protection nel centro sicurezza Microsoft 365 utilizzando Microsoft Edge, Internet Explorer 11 o qualsiasi Web browser compatibile con HTML 5.</span><span class="sxs-lookup"><span data-stu-id="51594-144">Access Microsoft Threat Protection in the Microsoft 365 security center using Microsoft Edge, Internet Explorer 11, or any HTML 5 compliant web browser.</span></span>

## <a name="microsoft-threat-protection-for-us-government-community-cloud-and-us-government-community-cloud-high-gcc-high-customers"></a><span data-ttu-id="51594-145">Microsoft Threat Protection per il governo degli Stati Uniti Cloud Community and US Government community Cloud High (GCC High) clienti</span><span class="sxs-lookup"><span data-stu-id="51594-145">Microsoft Threat Protection for US Government Community Cloud and US Government Community Cloud High (GCC High) customers</span></span>
<span data-ttu-id="51594-146">Attualmente, Microsoft Threat Protection non è disponibile per i clienti americani GCC e GCC High.</span><span class="sxs-lookup"><span data-stu-id="51594-146">Currently, Microsoft Threat Protection is not available to US GCC and GCC High customers.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="51594-147">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="51594-147">Related topics</span></span>
- [<span data-ttu-id="51594-148">Panoramica su Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="51594-148">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="51594-149">Attivare Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="51594-149">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)
