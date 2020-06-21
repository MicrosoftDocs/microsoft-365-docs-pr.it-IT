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
ms.openlocfilehash: f63c59403e84e79d1a4a5cf2b8a5544f5646781c
ms.sourcegitcommit: 51e47ca4b355436a2ad3deb154060eb1927428e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2020
ms.locfileid: "44773852"
---
# <a name="microsoft-threat-protection-prerequisites"></a><span data-ttu-id="51cc0-104">Prerequisiti di Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="51cc0-104">Microsoft Threat Protection prerequisites</span></span>

<span data-ttu-id="51cc0-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="51cc0-105">**Applies to:**</span></span>
- <span data-ttu-id="51cc0-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="51cc0-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="51cc0-107">Informazioni sulla gestione delle licenze e di altri requisiti per il provisioning e l'utilizzo di [Microsoft Threat Protection](microsoft-threat-protection.md).</span><span class="sxs-lookup"><span data-stu-id="51cc0-107">Learn about licensing and other requirements for provisioning and using [Microsoft Threat Protection](microsoft-threat-protection.md).</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="51cc0-108">Requisiti per la licenza</span><span class="sxs-lookup"><span data-stu-id="51cc0-108">Licensing requirements</span></span>
<span data-ttu-id="51cc0-109">Una qualsiasi di queste licenze consente di accedere alle funzionalità di Microsoft Threat Protection in Microsoft 365 Security Center senza costi aggiuntivi:</span><span class="sxs-lookup"><span data-stu-id="51cc0-109">Any of these licenses gives you access to Microsoft Threat Protection features in Microsoft 365 security center without additional cost:</span></span>

- <span data-ttu-id="51cc0-110">Microsoft 365 E5 o a5</span><span class="sxs-lookup"><span data-stu-id="51cc0-110">Microsoft 365 E5 or A5</span></span>
- <span data-ttu-id="51cc0-111">Sicurezza di Microsoft 365 E5 o sicurezza a5</span><span class="sxs-lookup"><span data-stu-id="51cc0-111">Microsoft 365 E5 Security or A5 Security</span></span>
- <span data-ttu-id="51cc0-112">Windows 10 Enterprise E5 o a5</span><span class="sxs-lookup"><span data-stu-id="51cc0-112">Windows 10 Enterprise E5 or A5</span></span>
- <span data-ttu-id="51cc0-113">Enterprise Mobility + Security (EMS) E5 o a5</span><span class="sxs-lookup"><span data-stu-id="51cc0-113">Enterprise Mobility + Security (EMS) E5 or A5</span></span> 
- <span data-ttu-id="51cc0-114">Office 365 E5 o a5</span><span class="sxs-lookup"><span data-stu-id="51cc0-114">Office 365 E5 or A5</span></span>
- <span data-ttu-id="51cc0-115">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="51cc0-115">Microsoft Defender Advanced Threat Protection</span></span>
- <span data-ttu-id="51cc0-116">Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="51cc0-116">Azure Advanced Threat Protection</span></span> 
- <span data-ttu-id="51cc0-117">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="51cc0-117">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="51cc0-118">Protezione avanzata dalle minacce di Office 365 (piano 2)</span><span class="sxs-lookup"><span data-stu-id="51cc0-118">Office 365 Advanced Threat Protection (Plan 2)</span></span>

> [!NOTE]
> <span data-ttu-id="51cc0-119">Le licenze di valutazione per Office 365 attualmente non consentono l'accesso a Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="51cc0-119">Trial licenses for Office 365 currently do not provide access to Microsoft Threat Protection.</span></span>

<span data-ttu-id="51cc0-120">Per ulteriori informazioni, [vedere i piani del servizio Microsoft 365 Enterprise](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span><span class="sxs-lookup"><span data-stu-id="51cc0-120">For more information, [view the Microsoft 365 Enterprise service plans](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span></span>

> <span data-ttu-id="51cc0-121">Non si dispone ancora di una licenza?</span><span class="sxs-lookup"><span data-stu-id="51cc0-121">Don't have license yet?</span></span> [<span data-ttu-id="51cc0-122">Provare o acquistare un abbonamento a Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="51cc0-122">Try or buy a Microsoft 365 subscription</span></span>](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a><span data-ttu-id="51cc0-123">Controllare le licenze esistenti</span><span class="sxs-lookup"><span data-stu-id="51cc0-123">Check your existing  licenses</span></span>
<span data-ttu-id="51cc0-124">Accedere a Microsoft 365 Admin Center ([admin.Microsoft.com](https://admin.microsoft.com/)) per visualizzare le licenze esistenti.</span><span class="sxs-lookup"><span data-stu-id="51cc0-124">Go to Microsoft 365 admin center ([admin.microsoft.com](https://admin.microsoft.com/)) to view your existing licenses.</span></span> <span data-ttu-id="51cc0-125">Nell'interfaccia di amministrazione, andare in **Fatturazione** > **Licenze**.</span><span class="sxs-lookup"><span data-stu-id="51cc0-125">In the admin center, go to **Billing** > **Licenses**.</span></span>

>[!NOTE]
> <span data-ttu-id="51cc0-126">Per poter visualizzare le informazioni sulla licenza, è necessario essere assegnati al ruolo di **amministratore di fatturazione** o **lettore globale** [in Azure ad](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) .</span><span class="sxs-lookup"><span data-stu-id="51cc0-126">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see license information.</span></span> <span data-ttu-id="51cc0-127">Se si verificano problemi di accesso, rivolgersi a un amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="51cc0-127">If you encounter access problems, contact a global admin.</span></span>

## <a name="required-permissions"></a><span data-ttu-id="51cc0-128">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="51cc0-128">Required permissions</span></span>
<span data-ttu-id="51cc0-129">Per l'elenco dei ruoli necessari e per la modalità di regolamentazione dell'accesso ai dati, leggere informazioni sulla [gestione dell'accesso a Microsoft Threat Protection](mtp-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="51cc0-129">For the list of required roles and how access to data is regulated, read about [managing access to Microsoft Threat Protection](mtp-permissions.md).</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="51cc0-130">Requisiti per il browser</span><span class="sxs-lookup"><span data-stu-id="51cc0-130">Browser requirements</span></span>
<span data-ttu-id="51cc0-131">Accedere a Microsoft Threat Protection nel centro sicurezza Microsoft 365 utilizzando Microsoft Edge, Internet Explorer 11 o qualsiasi Web browser compatibile con HTML 5.</span><span class="sxs-lookup"><span data-stu-id="51cc0-131">Access Microsoft Threat Protection in the Microsoft 365 security center using Microsoft Edge, Internet Explorer 11, or any HTML 5 compliant web browser.</span></span>

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a><span data-ttu-id="51cc0-132">Disponibilità a noi GCC, GCC High e altre istituzioni governative degli Stati Uniti</span><span class="sxs-lookup"><span data-stu-id="51cc0-132">Availability to US GCC, GCC High, and other US government institutions</span></span>
<span data-ttu-id="51cc0-133">Attualmente, Microsoft Threat Protection *non* è disponibile per:</span><span class="sxs-lookup"><span data-stu-id="51cc0-133">Currently, Microsoft Threat Protection is *not* available to:</span></span>
- <span data-ttu-id="51cc0-134">Cloud (GCC) del governo degli Stati Uniti</span><span class="sxs-lookup"><span data-stu-id="51cc0-134">US Government Community Cloud (GCC)</span></span>
- <span data-ttu-id="51cc0-135">Cloud degli Stati Uniti nube alto (GCC High)</span><span class="sxs-lookup"><span data-stu-id="51cc0-135">US Government Community Cloud High (GCC High)</span></span>
- <span data-ttu-id="51cc0-136">Dipartimento della difesa degli Stati Uniti</span><span class="sxs-lookup"><span data-stu-id="51cc0-136">US Department of Defense</span></span>
- <span data-ttu-id="51cc0-137">Tutte le istituzioni governative degli Stati Uniti con licenze commerciali</span><span class="sxs-lookup"><span data-stu-id="51cc0-137">All US government institutions with commercial licenses</span></span>

## <a name="related-topics"></a><span data-ttu-id="51cc0-138">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="51cc0-138">Related topics</span></span>
- [<span data-ttu-id="51cc0-139">Panoramica su Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="51cc0-139">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="51cc0-140">Attivare Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="51cc0-140">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)
- [<span data-ttu-id="51cc0-141">Gestire l'accesso e le autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="51cc0-141">Manage access and permissions</span></span>](mtp-permissions.md)
