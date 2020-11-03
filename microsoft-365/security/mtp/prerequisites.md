---
title: Prerequisiti di Microsoft 365 Defender
description: Informazioni sui requisiti di licenza, hardware e software e altre impostazioni di configurazione per Microsoft 365 Defender
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
ms.openlocfilehash: 415cdb79a6aa9371ee2f07de579cfb2f873f1acb
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844777"
---
# <a name="microsoft-365-defender-prerequisites"></a><span data-ttu-id="f8603-104">Prerequisiti di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f8603-104">Microsoft 365 Defender prerequisites</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f8603-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="f8603-105">**Applies to:**</span></span>
- <span data-ttu-id="f8603-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f8603-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="f8603-107">Informazioni sulla gestione delle licenze e di altri requisiti per il provisioning e l'utilizzo di [Microsoft 365 Defender](microsoft-threat-protection.md).</span><span class="sxs-lookup"><span data-stu-id="f8603-107">Learn about licensing and other requirements for provisioning and using [Microsoft 365 Defender](microsoft-threat-protection.md).</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="f8603-108">Requisiti per la licenza</span><span class="sxs-lookup"><span data-stu-id="f8603-108">Licensing requirements</span></span>
<span data-ttu-id="f8603-109">Una qualsiasi di queste licenze consente di accedere alle funzionalità di Microsoft 365 Defender in Microsoft 365 Security Center senza costi aggiuntivi:</span><span class="sxs-lookup"><span data-stu-id="f8603-109">Any of these licenses gives you access to Microsoft 365 Defender features in Microsoft 365 security center without additional cost:</span></span>

- <span data-ttu-id="f8603-110">Microsoft 365 E5 o a5</span><span class="sxs-lookup"><span data-stu-id="f8603-110">Microsoft 365 E5 or A5</span></span>
- <span data-ttu-id="f8603-111">Sicurezza di Microsoft 365 E5 o sicurezza a5</span><span class="sxs-lookup"><span data-stu-id="f8603-111">Microsoft 365 E5 Security or A5 Security</span></span>
- <span data-ttu-id="f8603-112">Windows 10 Enterprise E5 o a5</span><span class="sxs-lookup"><span data-stu-id="f8603-112">Windows 10 Enterprise E5 or A5</span></span>
- <span data-ttu-id="f8603-113">Enterprise Mobility + Security (EMS) E5 o a5</span><span class="sxs-lookup"><span data-stu-id="f8603-113">Enterprise Mobility + Security (EMS) E5 or A5</span></span> 
- <span data-ttu-id="f8603-114">Office 365 E5 o a5</span><span class="sxs-lookup"><span data-stu-id="f8603-114">Office 365 E5 or A5</span></span>
- <span data-ttu-id="f8603-115">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="f8603-115">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="f8603-116">Microsoft Defender per identità</span><span class="sxs-lookup"><span data-stu-id="f8603-116">Microsoft Defender for Identity</span></span> 
- <span data-ttu-id="f8603-117">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="f8603-117">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="f8603-118">Difensore per Office 365 (piano 2)</span><span class="sxs-lookup"><span data-stu-id="f8603-118">Defender for Office 365 (Plan 2)</span></span>

> [!NOTE]
> <span data-ttu-id="f8603-119">Le licenze di valutazione per Office 365 attualmente non consentono l'accesso a Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="f8603-119">Trial licenses for Office 365 currently do not provide access to Microsoft 365 Defender.</span></span>

<span data-ttu-id="f8603-120">Per ulteriori informazioni, [vedere i piani del servizio Microsoft 365 Enterprise](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span><span class="sxs-lookup"><span data-stu-id="f8603-120">For more information, [view the Microsoft 365 Enterprise service plans](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span></span>

> <span data-ttu-id="f8603-121">Non si dispone ancora di una licenza?</span><span class="sxs-lookup"><span data-stu-id="f8603-121">Don't have license yet?</span></span> [<span data-ttu-id="f8603-122">Provare o acquistare un abbonamento a Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f8603-122">Try or buy a Microsoft 365 subscription</span></span>](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a><span data-ttu-id="f8603-123">Controllare le licenze esistenti</span><span class="sxs-lookup"><span data-stu-id="f8603-123">Check your existing  licenses</span></span>
<span data-ttu-id="f8603-124">Accedere a Microsoft 365 Admin Center ([admin.Microsoft.com](https://admin.microsoft.com/)) per visualizzare le licenze esistenti.</span><span class="sxs-lookup"><span data-stu-id="f8603-124">Go to Microsoft 365 admin center ([admin.microsoft.com](https://admin.microsoft.com/)) to view your existing licenses.</span></span> <span data-ttu-id="f8603-125">Nell'interfaccia di amministrazione, andare in **Fatturazione** > **Licenze**.</span><span class="sxs-lookup"><span data-stu-id="f8603-125">In the admin center, go to **Billing** > **Licenses**.</span></span>

>[!NOTE]
> <span data-ttu-id="f8603-126">Per poter visualizzare le informazioni sulla licenza, è necessario essere assegnati al ruolo di **amministratore di fatturazione** o **lettore globale** [in Azure ad](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) .</span><span class="sxs-lookup"><span data-stu-id="f8603-126">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see license information.</span></span> <span data-ttu-id="f8603-127">Se si verificano problemi di accesso, rivolgersi a un amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="f8603-127">If you encounter access problems, contact a global admin.</span></span>

## <a name="required-permissions"></a><span data-ttu-id="f8603-128">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="f8603-128">Required permissions</span></span>
<span data-ttu-id="f8603-129">È necessario essere un **amministratore globale** o un **amministratore della sicurezza** in Azure Active Directory per abilitare Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="f8603-129">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft 365 Defender.</span></span> <span data-ttu-id="f8603-130">Per l'elenco dei ruoli necessari per l'utilizzo di Microsoft 365 Defender e informazioni su come l'accesso ai dati è regolato, leggere informazioni sulla [gestione dell'accesso a microsoft 365 Defender](mtp-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="f8603-130">For the list of roles required to use Microsoft 365 Defender and information on how access to data is regulated, read about [managing access to Microsoft 365 Defender](mtp-permissions.md).</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="f8603-131">Requisiti per il browser</span><span class="sxs-lookup"><span data-stu-id="f8603-131">Browser requirements</span></span>
<span data-ttu-id="f8603-132">Accedere a Microsoft 365 Defender nel centro sicurezza Microsoft 365 utilizzando Microsoft Edge, Internet Explorer 11 o qualsiasi Web browser compatibile con HTML 5.</span><span class="sxs-lookup"><span data-stu-id="f8603-132">Access Microsoft 365 Defender in the Microsoft 365 security center using Microsoft Edge, Internet Explorer 11, or any HTML 5 compliant web browser.</span></span>

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a><span data-ttu-id="f8603-133">Disponibilità a noi GCC, GCC High e altre istituzioni governative degli Stati Uniti</span><span class="sxs-lookup"><span data-stu-id="f8603-133">Availability to US GCC, GCC High, and other US government institutions</span></span>
<span data-ttu-id="f8603-134">Attualmente, Microsoft 365 Defender *non* è disponibile per:</span><span class="sxs-lookup"><span data-stu-id="f8603-134">Currently, Microsoft 365 Defender is *not* available to:</span></span>
- <span data-ttu-id="f8603-135">Cloud (GCC) del governo degli Stati Uniti</span><span class="sxs-lookup"><span data-stu-id="f8603-135">US Government Community Cloud (GCC)</span></span>
- <span data-ttu-id="f8603-136">Cloud degli Stati Uniti nube alto (GCC High)</span><span class="sxs-lookup"><span data-stu-id="f8603-136">US Government Community Cloud High (GCC High)</span></span>
- <span data-ttu-id="f8603-137">Dipartimento della difesa degli Stati Uniti</span><span class="sxs-lookup"><span data-stu-id="f8603-137">US Department of Defense</span></span>
- <span data-ttu-id="f8603-138">Tutte le istituzioni governative degli Stati Uniti con licenze commerciali</span><span class="sxs-lookup"><span data-stu-id="f8603-138">All US government institutions with commercial licenses</span></span>

## <a name="related-topics"></a><span data-ttu-id="f8603-139">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="f8603-139">Related topics</span></span>
- [<span data-ttu-id="f8603-140">Panoramica di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f8603-140">Microsoft 365 Defender overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="f8603-141">Attiva Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f8603-141">Turn on Microsoft 365 Defender</span></span>](mtp-enable.md)
- [<span data-ttu-id="f8603-142">Gestire l'accesso e le autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="f8603-142">Manage access and permissions</span></span>](mtp-permissions.md)
