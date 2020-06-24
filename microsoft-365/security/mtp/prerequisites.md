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
ms.openlocfilehash: c64adf870d3669b983e11093196f59c82b1f59e0
ms.sourcegitcommit: bd5a08785b5ec320b04b02f8776e28bce5fb448f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "44844907"
---
# <a name="microsoft-threat-protection-prerequisites"></a><span data-ttu-id="3d5c2-104">Prerequisiti di Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="3d5c2-104">Microsoft Threat Protection prerequisites</span></span>

<span data-ttu-id="3d5c2-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="3d5c2-105">**Applies to:**</span></span>
- <span data-ttu-id="3d5c2-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="3d5c2-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="3d5c2-107">Informazioni sulla gestione delle licenze e di altri requisiti per il provisioning e l'utilizzo di [Microsoft Threat Protection](microsoft-threat-protection.md).</span><span class="sxs-lookup"><span data-stu-id="3d5c2-107">Learn about licensing and other requirements for provisioning and using [Microsoft Threat Protection](microsoft-threat-protection.md).</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="3d5c2-108">Requisiti per la licenza</span><span class="sxs-lookup"><span data-stu-id="3d5c2-108">Licensing requirements</span></span>
<span data-ttu-id="3d5c2-109">Una qualsiasi di queste licenze consente di accedere alle funzionalità di Microsoft Threat Protection in Microsoft 365 Security Center senza costi aggiuntivi:</span><span class="sxs-lookup"><span data-stu-id="3d5c2-109">Any of these licenses gives you access to Microsoft Threat Protection features in Microsoft 365 security center without additional cost:</span></span>

- <span data-ttu-id="3d5c2-110">Microsoft 365 E5 o a5</span><span class="sxs-lookup"><span data-stu-id="3d5c2-110">Microsoft 365 E5 or A5</span></span>
- <span data-ttu-id="3d5c2-111">Sicurezza di Microsoft 365 E5 o sicurezza a5</span><span class="sxs-lookup"><span data-stu-id="3d5c2-111">Microsoft 365 E5 Security or A5 Security</span></span>
- <span data-ttu-id="3d5c2-112">Windows 10 Enterprise E5 o a5</span><span class="sxs-lookup"><span data-stu-id="3d5c2-112">Windows 10 Enterprise E5 or A5</span></span>
- <span data-ttu-id="3d5c2-113">Enterprise Mobility + Security (EMS) E5 o a5</span><span class="sxs-lookup"><span data-stu-id="3d5c2-113">Enterprise Mobility + Security (EMS) E5 or A5</span></span> 
- <span data-ttu-id="3d5c2-114">Office 365 E5 o a5</span><span class="sxs-lookup"><span data-stu-id="3d5c2-114">Office 365 E5 or A5</span></span>
- <span data-ttu-id="3d5c2-115">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="3d5c2-115">Microsoft Defender Advanced Threat Protection</span></span>
- <span data-ttu-id="3d5c2-116">Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="3d5c2-116">Azure Advanced Threat Protection</span></span> 
- <span data-ttu-id="3d5c2-117">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="3d5c2-117">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="3d5c2-118">Protezione avanzata dalle minacce di Office 365 (piano 2)</span><span class="sxs-lookup"><span data-stu-id="3d5c2-118">Office 365 Advanced Threat Protection (Plan 2)</span></span>

> [!NOTE]
> <span data-ttu-id="3d5c2-119">Le licenze di valutazione per Office 365 attualmente non consentono l'accesso a Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="3d5c2-119">Trial licenses for Office 365 currently do not provide access to Microsoft Threat Protection.</span></span>

<span data-ttu-id="3d5c2-120">Per ulteriori informazioni, [vedere i piani del servizio Microsoft 365 Enterprise](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span><span class="sxs-lookup"><span data-stu-id="3d5c2-120">For more information, [view the Microsoft 365 Enterprise service plans](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span></span>

> <span data-ttu-id="3d5c2-121">Non si dispone ancora di una licenza?</span><span class="sxs-lookup"><span data-stu-id="3d5c2-121">Don't have license yet?</span></span> [<span data-ttu-id="3d5c2-122">Provare o acquistare un abbonamento a Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3d5c2-122">Try or buy a Microsoft 365 subscription</span></span>](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a><span data-ttu-id="3d5c2-123">Controllare le licenze esistenti</span><span class="sxs-lookup"><span data-stu-id="3d5c2-123">Check your existing  licenses</span></span>
<span data-ttu-id="3d5c2-124">Accedere a Microsoft 365 Admin Center ([admin.Microsoft.com](https://admin.microsoft.com/)) per visualizzare le licenze esistenti.</span><span class="sxs-lookup"><span data-stu-id="3d5c2-124">Go to Microsoft 365 admin center ([admin.microsoft.com](https://admin.microsoft.com/)) to view your existing licenses.</span></span> <span data-ttu-id="3d5c2-125">Nell'interfaccia di amministrazione, andare in **Fatturazione** > **Licenze**.</span><span class="sxs-lookup"><span data-stu-id="3d5c2-125">In the admin center, go to **Billing** > **Licenses**.</span></span>

>[!NOTE]
> <span data-ttu-id="3d5c2-126">Per poter visualizzare le informazioni sulla licenza, è necessario essere assegnati al ruolo di **amministratore di fatturazione** o **lettore globale** [in Azure ad](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) .</span><span class="sxs-lookup"><span data-stu-id="3d5c2-126">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see license information.</span></span> <span data-ttu-id="3d5c2-127">Se si verificano problemi di accesso, rivolgersi a un amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="3d5c2-127">If you encounter access problems, contact a global admin.</span></span>

## <a name="required-permissions"></a><span data-ttu-id="3d5c2-128">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="3d5c2-128">Required permissions</span></span>
<span data-ttu-id="3d5c2-129">Per abilitare Microsoft Threat Protection, è necessario essere un amministratore **globale** o un **amministratore della sicurezza** in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3d5c2-129">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft Threat Protection.</span></span> <span data-ttu-id="3d5c2-130">Per l'elenco dei ruoli necessari per l'utilizzo di Microsoft Threat Protection e informazioni su come l'accesso ai dati è regolato, leggere informazioni sulla [gestione dell'accesso a Microsoft Threat Protection](mtp-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="3d5c2-130">For the list of roles required to use Microsoft Threat Protection and information on how access to data is regulated, read about [managing access to Microsoft Threat Protection](mtp-permissions.md).</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="3d5c2-131">Requisiti per il browser</span><span class="sxs-lookup"><span data-stu-id="3d5c2-131">Browser requirements</span></span>
<span data-ttu-id="3d5c2-132">Accedere a Microsoft Threat Protection nel centro sicurezza Microsoft 365 utilizzando Microsoft Edge, Internet Explorer 11 o qualsiasi Web browser compatibile con HTML 5.</span><span class="sxs-lookup"><span data-stu-id="3d5c2-132">Access Microsoft Threat Protection in the Microsoft 365 security center using Microsoft Edge, Internet Explorer 11, or any HTML 5 compliant web browser.</span></span>

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a><span data-ttu-id="3d5c2-133">Disponibilità a noi GCC, GCC High e altre istituzioni governative degli Stati Uniti</span><span class="sxs-lookup"><span data-stu-id="3d5c2-133">Availability to US GCC, GCC High, and other US government institutions</span></span>
<span data-ttu-id="3d5c2-134">Attualmente, Microsoft Threat Protection *non* è disponibile per:</span><span class="sxs-lookup"><span data-stu-id="3d5c2-134">Currently, Microsoft Threat Protection is *not* available to:</span></span>
- <span data-ttu-id="3d5c2-135">Cloud (GCC) del governo degli Stati Uniti</span><span class="sxs-lookup"><span data-stu-id="3d5c2-135">US Government Community Cloud (GCC)</span></span>
- <span data-ttu-id="3d5c2-136">Cloud degli Stati Uniti nube alto (GCC High)</span><span class="sxs-lookup"><span data-stu-id="3d5c2-136">US Government Community Cloud High (GCC High)</span></span>
- <span data-ttu-id="3d5c2-137">Dipartimento della difesa degli Stati Uniti</span><span class="sxs-lookup"><span data-stu-id="3d5c2-137">US Department of Defense</span></span>
- <span data-ttu-id="3d5c2-138">Tutte le istituzioni governative degli Stati Uniti con licenze commerciali</span><span class="sxs-lookup"><span data-stu-id="3d5c2-138">All US government institutions with commercial licenses</span></span>

## <a name="related-topics"></a><span data-ttu-id="3d5c2-139">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="3d5c2-139">Related topics</span></span>
- [<span data-ttu-id="3d5c2-140">Panoramica su Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="3d5c2-140">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="3d5c2-141">Attivare Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="3d5c2-141">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)
- [<span data-ttu-id="3d5c2-142">Gestire l'accesso e le autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="3d5c2-142">Manage access and permissions</span></span>](mtp-permissions.md)
