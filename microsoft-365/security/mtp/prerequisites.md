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
ms.openlocfilehash: 66b3f7e446416b6252050e6f41a2b22d99d25767
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209236"
---
# <a name="microsoft-threat-protection-prerequisites"></a><span data-ttu-id="e7648-104">Prerequisiti di Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="e7648-104">Microsoft Threat Protection prerequisites</span></span>

<span data-ttu-id="e7648-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="e7648-105">**Applies to:**</span></span>
- <span data-ttu-id="e7648-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="e7648-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="e7648-107">Informazioni sui requisiti di licenza, hardware e software e altre impostazioni di configurazione per il provisioning e l'utilizzo di Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="e7648-107">Learn about the licensing, hardware and software requirements, and other configuration settings to provision and use Microsoft Threat Protection.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="e7648-108">Requisiti per la licenza</span><span class="sxs-lookup"><span data-stu-id="e7648-108">Licensing requirements</span></span>

>[!IMPORTANT]
><span data-ttu-id="e7648-109">A partire dal 12 maggio 2020, Microsoft eseguirà gradualmente nuove esperienze ottimizzate in merito ai requisiti di licenza e [all'attivazione di Microsoft Threat Protection](mtp-enable.md).</span><span class="sxs-lookup"><span data-stu-id="e7648-109">Starting May 12, 2020, Microsoft will gradually roll out new, optimized experiences around licensing requirements and [turning on Microsoft Threat Protection](mtp-enable.md).</span></span> <span data-ttu-id="e7648-110">Per alcune settimane durante questo periodo, alcuni clienti inizieranno a visualizzare le modifiche apportate alle esperienze del portale.</span><span class="sxs-lookup"><span data-stu-id="e7648-110">For several weeks during this period, some customers will start to see changes to their portal experiences.</span></span> <span data-ttu-id="e7648-111">Le informazioni sulle nuove esperienze sono state contrassegnate come **nuova esperienza** in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="e7648-111">Information about the new experiences are marked **New experience** in this article.</span></span>

<span data-ttu-id="e7648-112">Per utilizzare Microsoft Threat Protection, è necessaria una singola licenza o una combinazione di licenze.</span><span class="sxs-lookup"><span data-stu-id="e7648-112">To use Microsoft Threat Protection, you need either a single license or a combination of licenses.</span></span> <span data-ttu-id="e7648-113">Queste licenze o combinazioni di licenze consentono di accedere alle funzionalità di protezione dalle minacce di Microsoft senza costi aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="e7648-113">These licenses or license combinations give you access to Microsoft Threat Protection features without additional cost.</span></span>

### <a name="single-license"></a><span data-ttu-id="e7648-114">Licenza singola</span><span class="sxs-lookup"><span data-stu-id="e7648-114">Single license</span></span>
<span data-ttu-id="e7648-115">È possibile utilizzare *una* delle licenze seguenti:</span><span class="sxs-lookup"><span data-stu-id="e7648-115">You can use *one* of the following licenses:</span></span>

- <span data-ttu-id="e7648-116">Microsoft 365 E5 o a5</span><span class="sxs-lookup"><span data-stu-id="e7648-116">Microsoft 365 E5 or A5</span></span>
- <span data-ttu-id="e7648-117">Sicurezza di Microsoft 365 E5 o sicurezza a5</span><span class="sxs-lookup"><span data-stu-id="e7648-117">Microsoft 365 E5 Security or A5 Security</span></span>

### <a name="combination-of-licenses"></a><span data-ttu-id="e7648-118">Combinazione di licenze</span><span class="sxs-lookup"><span data-stu-id="e7648-118">Combination of licenses</span></span>
<span data-ttu-id="e7648-119">È inoltre possibile utilizzare una combinazione di licenze per gli abbonamenti E5 o a5 a Office 365, *Enterprise Mobility + Security (EMS)* e Windows.</span><span class="sxs-lookup"><span data-stu-id="e7648-119">You can also use a combination of licenses for E5 or A5 subscriptions to Office 365, *Enterprise Mobility + Security (EMS)*, and Windows.</span></span> <span data-ttu-id="e7648-120">La combinazione di licenze deve includere *tutte* le licenze seguenti:</span><span class="sxs-lookup"><span data-stu-id="e7648-120">The license combination must include *all* of these licenses:</span></span>

- <span data-ttu-id="e7648-121">Office 365 E5 o a5</span><span class="sxs-lookup"><span data-stu-id="e7648-121">Office 365 E5 or A5</span></span>
- <span data-ttu-id="e7648-122">*Enterprise Mobility + Security (EMS)* E5 o a5</span><span class="sxs-lookup"><span data-stu-id="e7648-122">*Enterprise Mobility + Security (EMS)* E5 or A5</span></span>
- <span data-ttu-id="e7648-123">Windows 10 Enterprise E5 o a5</span><span class="sxs-lookup"><span data-stu-id="e7648-123">Windows 10 Enterprise E5 or A5</span></span>

<span data-ttu-id="e7648-124">Per ulteriori informazioni, [vedere i piani del servizio Microsoft 365 Enterprise](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span><span class="sxs-lookup"><span data-stu-id="e7648-124">For more information, [view the Microsoft 365 Enterprise service plans](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span></span>

> <span data-ttu-id="e7648-125">Non si dispone ancora di una licenza?</span><span class="sxs-lookup"><span data-stu-id="e7648-125">Don't have license yet?</span></span> [<span data-ttu-id="e7648-126">Provare o acquistare un abbonamento a Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e7648-126">Try or buy a Microsoft 365 subscription</span></span>](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)


<span data-ttu-id="e7648-127">**Nuova esperienza:** A partire dal 12 maggio 2020, i clienti riceveranno gradualmente le modifiche apportate a questa esperienza.</span><span class="sxs-lookup"><span data-stu-id="e7648-127">**New experience:** Starting May 12, 2020, customers will gradually receive changes to this experience.</span></span> <span data-ttu-id="e7648-128">Per gli utenti con la nuova esperienza, la possibilità di abilitare Microsoft Threat Protection sarà disponibile per *tutti* i clienti con una delle licenze seguenti:</span><span class="sxs-lookup"><span data-stu-id="e7648-128">For those with the new experience, the option to turn on Microsoft Threat Protection will be available to *all* customers with any of the following licenses:</span></span>

- <span data-ttu-id="e7648-129">Microsoft 365 E5 o a5</span><span class="sxs-lookup"><span data-stu-id="e7648-129">Microsoft 365 E5 or A5</span></span>
- <span data-ttu-id="e7648-130">Sicurezza di Microsoft 365 E5 o sicurezza a5</span><span class="sxs-lookup"><span data-stu-id="e7648-130">Microsoft 365 E5 Security or A5 Security</span></span>
- <span data-ttu-id="e7648-131">Windows 10 Enterprise E5 o a5</span><span class="sxs-lookup"><span data-stu-id="e7648-131">Windows 10 Enterprise E5 or A5</span></span>
- <span data-ttu-id="e7648-132">Enterprise Mobility + Security (EMS) E5 o a5</span><span class="sxs-lookup"><span data-stu-id="e7648-132">Enterprise Mobility + Security (EMS) E5 or A5</span></span> 
- <span data-ttu-id="e7648-133">Office 365 E5 o a5</span><span class="sxs-lookup"><span data-stu-id="e7648-133">Office 365 E5 or A5</span></span>
- <span data-ttu-id="e7648-134">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="e7648-134">Microsoft Defender Advanced Threat Protection</span></span> 
- <span data-ttu-id="e7648-135">Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="e7648-135">Azure Advanced Threat Protection</span></span> 
- <span data-ttu-id="e7648-136">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="e7648-136">Microsoft Cloud App Security</span></span> 
- <span data-ttu-id="e7648-137">Protezione avanzata dalle minacce di Office 365 (piano 2)</span><span class="sxs-lookup"><span data-stu-id="e7648-137">Office 365 Advanced Threat Protection (Plan 2)</span></span> 

### <a name="check-your-existing--licenses"></a><span data-ttu-id="e7648-138">Controllare le licenze esistenti</span><span class="sxs-lookup"><span data-stu-id="e7648-138">Check your existing  licenses</span></span>
<span data-ttu-id="e7648-139">Accedere a Microsoft 365 Admin Center ([admin.Microsoft.com](https://admin.microsoft.com/)) per visualizzare le licenze esistenti.</span><span class="sxs-lookup"><span data-stu-id="e7648-139">Go to Microsoft 365 admin center ([admin.microsoft.com](https://admin.microsoft.com/)) to view your existing licenses.</span></span> <span data-ttu-id="e7648-140">Nell'interfaccia di amministrazione, andare in **Fatturazione** > **Licenze**.</span><span class="sxs-lookup"><span data-stu-id="e7648-140">In the admin center, go to **Billing** > **Licenses**.</span></span>

>[!NOTE]
> <span data-ttu-id="e7648-141">Per poter visualizzare le informazioni sulla licenza, è necessario essere assegnati al ruolo di **amministratore di fatturazione** o **lettore globale** [in Azure ad](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) .</span><span class="sxs-lookup"><span data-stu-id="e7648-141">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see license information.</span></span> <span data-ttu-id="e7648-142">Se si verificano problemi di accesso, rivolgersi a un amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="e7648-142">If you encounter access problems, contact a global admin.</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="e7648-143">Requisiti per il browser</span><span class="sxs-lookup"><span data-stu-id="e7648-143">Browser requirements</span></span>
<span data-ttu-id="e7648-144">Accedere a Microsoft Threat Protection nel centro sicurezza Microsoft 365 utilizzando Microsoft Edge, Internet Explorer 11 o qualsiasi Web browser compatibile con HTML 5.</span><span class="sxs-lookup"><span data-stu-id="e7648-144">Access Microsoft Threat Protection in the Microsoft 365 security center using Microsoft Edge, Internet Explorer 11, or any HTML 5 compliant web browser.</span></span>

## <a name="us-gcc-and-gcc-high-availability"></a><span data-ttu-id="e7648-145">Disponibilità elevata di GCC e GCC</span><span class="sxs-lookup"><span data-stu-id="e7648-145">US GCC and GCC High availability</span></span>
<span data-ttu-id="e7648-146">Attualmente, Microsoft Threat Protection non è disponibile per i clienti di US Government community Cloud (GCC) e Government community Cloud High (GCC High).</span><span class="sxs-lookup"><span data-stu-id="e7648-146">Currently, Microsoft Threat Protection is not available to US Government Community Cloud (GCC) and Government Community Cloud High (GCC High) customers.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="e7648-147">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="e7648-147">Related topics</span></span>
- [<span data-ttu-id="e7648-148">Panoramica su Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="e7648-148">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="e7648-149">Attivare Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="e7648-149">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)
