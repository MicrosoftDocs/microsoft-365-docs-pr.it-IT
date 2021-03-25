---
title: Prerequisiti di Microsoft 365 Defender
description: Informazioni sulle licenze, i requisiti hardware e software e altre impostazioni di configurazione per Microsoft 365 Defender
keywords: requisiti, prerequisiti, hardware, software, browser, MTP, M365, licenza, E5, A5, EMS, acquisto
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: f9904ecb5b9ab0a0f634903a5dc0ee3049d06b38
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51066746"
---
# <a name="microsoft-365-defender-prerequisites"></a><span data-ttu-id="b4bfe-104">Prerequisiti di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b4bfe-104">Microsoft 365 Defender prerequisites</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="b4bfe-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="b4bfe-105">**Applies to:**</span></span>
- <span data-ttu-id="b4bfe-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b4bfe-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="b4bfe-107">Informazioni sulle licenze e altri requisiti per il provisioning e l'uso [di Microsoft 365 Defender.](microsoft-365-defender.md)</span><span class="sxs-lookup"><span data-stu-id="b4bfe-107">Learn about licensing and other requirements for provisioning and using [Microsoft 365 Defender](microsoft-365-defender.md).</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="b4bfe-108">Requisiti per la licenza</span><span class="sxs-lookup"><span data-stu-id="b4bfe-108">Licensing requirements</span></span>
<span data-ttu-id="b4bfe-109">Una di queste licenze consente di accedere alle funzionalità di Microsoft 365 Defender nel Centro sicurezza Microsoft 365 senza costi aggiuntivi:</span><span class="sxs-lookup"><span data-stu-id="b4bfe-109">Any of these licenses gives you access to Microsoft 365 Defender features in Microsoft 365 security center without additional cost:</span></span>

- <span data-ttu-id="b4bfe-110">Microsoft 365 E5 o A5</span><span class="sxs-lookup"><span data-stu-id="b4bfe-110">Microsoft 365 E5 or A5</span></span>
- <span data-ttu-id="b4bfe-111">Microsoft 365 E5 Security o A5 Security</span><span class="sxs-lookup"><span data-stu-id="b4bfe-111">Microsoft 365 E5 Security or A5 Security</span></span>
- <span data-ttu-id="b4bfe-112">Windows 10 Enterprise E5 o A5</span><span class="sxs-lookup"><span data-stu-id="b4bfe-112">Windows 10 Enterprise E5 or A5</span></span>
- <span data-ttu-id="b4bfe-113">Enterprise Mobility + Security (EMS) E5 o A5</span><span class="sxs-lookup"><span data-stu-id="b4bfe-113">Enterprise Mobility + Security (EMS) E5 or A5</span></span> 
- <span data-ttu-id="b4bfe-114">Office 365 E5 o A5</span><span class="sxs-lookup"><span data-stu-id="b4bfe-114">Office 365 E5 or A5</span></span>
- <span data-ttu-id="b4bfe-115">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="b4bfe-115">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="b4bfe-116">Microsoft Defender per identità</span><span class="sxs-lookup"><span data-stu-id="b4bfe-116">Microsoft Defender for Identity</span></span> 
- <span data-ttu-id="b4bfe-117">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="b4bfe-117">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="b4bfe-118">Defender per Office 365 (Piano 2)</span><span class="sxs-lookup"><span data-stu-id="b4bfe-118">Defender for Office 365 (Plan 2)</span></span>

<span data-ttu-id="b4bfe-119">Per ulteriori informazioni, visualizzare i piani di servizio di [Microsoft 365 Enterprise.](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise)</span><span class="sxs-lookup"><span data-stu-id="b4bfe-119">For more information, [view the Microsoft 365 Enterprise service plans](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span></span>

> <span data-ttu-id="b4bfe-120">Non hai ancora la licenza?</span><span class="sxs-lookup"><span data-stu-id="b4bfe-120">Don't have license yet?</span></span> [<span data-ttu-id="b4bfe-121">Provare o acquistare un abbonamento a Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b4bfe-121">Try or buy a Microsoft 365 subscription</span></span>](../../commerce/try-or-buy-microsoft-365.md?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a><span data-ttu-id="b4bfe-122">Controllare le licenze esistenti</span><span class="sxs-lookup"><span data-stu-id="b4bfe-122">Check your existing  licenses</span></span>
<span data-ttu-id="b4bfe-123">Passare all'interfaccia di amministrazione di Microsoft 365 ([admin.microsoft.com](https://admin.microsoft.com/)) per visualizzare le licenze esistenti.</span><span class="sxs-lookup"><span data-stu-id="b4bfe-123">Go to Microsoft 365 admin center ([admin.microsoft.com](https://admin.microsoft.com/)) to view your existing licenses.</span></span> <span data-ttu-id="b4bfe-124">Nell'interfaccia di amministrazione, andare in **Fatturazione** > **Licenze**.</span><span class="sxs-lookup"><span data-stu-id="b4bfe-124">In the admin center, go to **Billing** > **Licenses**.</span></span>

>[!NOTE]
> <span data-ttu-id="b4bfe-125">Per poter visualizzare le informazioni  sulla licenza, devi essere assegnato al ruolo **Amministratore** fatturazione o Lettore globale [in Azure AD.](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)</span><span class="sxs-lookup"><span data-stu-id="b4bfe-125">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see license information.</span></span> <span data-ttu-id="b4bfe-126">Se si verificano problemi di accesso, rivolgersi a un amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="b4bfe-126">If you encounter access problems, contact a global admin.</span></span>

## <a name="required-permissions"></a><span data-ttu-id="b4bfe-127">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="b4bfe-127">Required permissions</span></span>
<span data-ttu-id="b4bfe-128">Per attivare Microsoft 365 **Defender,** è necessario essere un amministratore globale o un amministratore della sicurezza **in** Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b4bfe-128">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft 365 Defender.</span></span> <span data-ttu-id="b4bfe-129">Per l'elenco dei ruoli necessari per l'utilizzo di Microsoft 365 Defender e per informazioni su come viene regolamentato l'accesso ai dati, leggere informazioni sulla gestione dell'accesso a [Microsoft 365 Defender.](m365d-permissions.md)</span><span class="sxs-lookup"><span data-stu-id="b4bfe-129">For the list of roles required to use Microsoft 365 Defender and information on how access to data is regulated, read about [managing access to Microsoft 365 Defender](m365d-permissions.md).</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="b4bfe-130">Requisiti per il browser</span><span class="sxs-lookup"><span data-stu-id="b4bfe-130">Browser requirements</span></span>
<span data-ttu-id="b4bfe-131">Accedere a Microsoft 365 Defender nel Centro sicurezza Microsoft 365 usando Microsoft Edge, Internet Explorer 11 o qualsiasi web browser conforme a HTML 5.</span><span class="sxs-lookup"><span data-stu-id="b4bfe-131">Access Microsoft 365 Defender in the Microsoft 365 security center using Microsoft Edge, Internet Explorer 11, or any HTML 5 compliant web browser.</span></span>

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a><span data-ttu-id="b4bfe-132">Disponibilità per US GCC, GCC High e altre istituzioni governative statunitensi</span><span class="sxs-lookup"><span data-stu-id="b4bfe-132">Availability to US GCC, GCC High, and other US government institutions</span></span>
<span data-ttu-id="b4bfe-133">Attualmente, Microsoft 365 Defender *non è* disponibile per:</span><span class="sxs-lookup"><span data-stu-id="b4bfe-133">Currently, Microsoft 365 Defender is *not* available to:</span></span>
- <span data-ttu-id="b4bfe-134">US Government Community Cloud (GCC)</span><span class="sxs-lookup"><span data-stu-id="b4bfe-134">US Government Community Cloud (GCC)</span></span>
- <span data-ttu-id="b4bfe-135">US Government Community Cloud High (GCC High)</span><span class="sxs-lookup"><span data-stu-id="b4bfe-135">US Government Community Cloud High (GCC High)</span></span>
- <span data-ttu-id="b4bfe-136">US Department of Defense</span><span class="sxs-lookup"><span data-stu-id="b4bfe-136">US Department of Defense</span></span>
- <span data-ttu-id="b4bfe-137">Tutte le istituzioni governative statunitensi con licenze commerciali</span><span class="sxs-lookup"><span data-stu-id="b4bfe-137">All US government institutions with commercial licenses</span></span>

## <a name="related-topics"></a><span data-ttu-id="b4bfe-138">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="b4bfe-138">Related topics</span></span>
- [<span data-ttu-id="b4bfe-139">Panoramica di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b4bfe-139">Microsoft 365 Defender overview</span></span>](microsoft-365-defender.md)
- [<span data-ttu-id="b4bfe-140">Attivare Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b4bfe-140">Turn on Microsoft 365 Defender</span></span>](m365d-enable.md)
- [<span data-ttu-id="b4bfe-141">Gestire l'accesso e le autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="b4bfe-141">Manage access and permissions</span></span>](m365d-permissions.md)