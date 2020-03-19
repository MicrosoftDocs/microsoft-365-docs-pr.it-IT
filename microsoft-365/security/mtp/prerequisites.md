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
ms.openlocfilehash: c482e46cf51cbf11960c02663221df0c136b067c
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857180"
---
# <a name="microsoft-threat-protection-prerequisites"></a><span data-ttu-id="0b439-104">Prerequisiti di Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="0b439-104">Microsoft Threat Protection prerequisites</span></span>

<span data-ttu-id="0b439-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="0b439-105">**Applies to:**</span></span>
- <span data-ttu-id="0b439-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="0b439-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="0b439-107">Informazioni sui requisiti di licenza, hardware e software e altre impostazioni di configurazione per il provisioning e l'utilizzo di Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="0b439-107">Learn about the licensing, hardware and software requirements, and other configuration settings to provision and use Microsoft Threat Protection.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="0b439-108">Requisiti per la licenza</span><span class="sxs-lookup"><span data-stu-id="0b439-108">Licensing requirements</span></span>
<span data-ttu-id="0b439-109">Per utilizzare Microsoft Threat Protection, è necessaria una singola licenza o una combinazione di licenze.</span><span class="sxs-lookup"><span data-stu-id="0b439-109">To use Microsoft Threat Protection, you need either a single license or a combination of licenses.</span></span>

### <a name="single-license"></a><span data-ttu-id="0b439-110">Licenza singola</span><span class="sxs-lookup"><span data-stu-id="0b439-110">Single license</span></span>
<span data-ttu-id="0b439-111">È possibile utilizzare *una* delle licenze seguenti:</span><span class="sxs-lookup"><span data-stu-id="0b439-111">You can use *one* of the following licenses:</span></span>

- <span data-ttu-id="0b439-112">Microsoft 365 E5 o a5</span><span class="sxs-lookup"><span data-stu-id="0b439-112">Microsoft 365 E5 or A5</span></span>
- <span data-ttu-id="0b439-113">Sicurezza di Microsoft 365 E5 o sicurezza a5</span><span class="sxs-lookup"><span data-stu-id="0b439-113">Microsoft 365 E5 Security or A5 Security</span></span>

### <a name="combination-of-licenses"></a><span data-ttu-id="0b439-114">Combinazione di licenze</span><span class="sxs-lookup"><span data-stu-id="0b439-114">Combination of licenses</span></span>
<span data-ttu-id="0b439-115">È inoltre possibile utilizzare una combinazione di licenze per gli abbonamenti E5 o a5 a Office 365, *Enterprise Mobility + Security (EMS)* e Windows.</span><span class="sxs-lookup"><span data-stu-id="0b439-115">You can also use a combination of licenses for E5 or A5 subscriptions to Office 365, *Enterprise Mobility + Security (EMS)*, and Windows.</span></span> <span data-ttu-id="0b439-116">La combinazione di licenze deve includere *tutte* le licenze seguenti:</span><span class="sxs-lookup"><span data-stu-id="0b439-116">The license combination must include *all* of these licenses:</span></span>

- <span data-ttu-id="0b439-117">Office 365 E5 o a5</span><span class="sxs-lookup"><span data-stu-id="0b439-117">Office 365 E5 or A5</span></span>
- <span data-ttu-id="0b439-118">*Enterprise Mobility + Security (EMS)* E5 o a5</span><span class="sxs-lookup"><span data-stu-id="0b439-118">*Enterprise Mobility + Security (EMS)* E5 or A5</span></span>
- <span data-ttu-id="0b439-119">Windows E5 o a5</span><span class="sxs-lookup"><span data-stu-id="0b439-119">Windows E5 or A5</span></span>

<span data-ttu-id="0b439-120">Per ulteriori informazioni, [vedere i piani del servizio Microsoft 365 Enterprise](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span><span class="sxs-lookup"><span data-stu-id="0b439-120">For more information, [view the Microsoft 365 Enterprise service plans](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span></span>

> <span data-ttu-id="0b439-121">Non si dispone ancora di una licenza?</span><span class="sxs-lookup"><span data-stu-id="0b439-121">Don't have license yet?</span></span> [<span data-ttu-id="0b439-122">Provare o acquistare un abbonamento a Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0b439-122">Try or buy a Microsoft 365 subscription</span></span>](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a><span data-ttu-id="0b439-123">Controllare le licenze esistenti</span><span class="sxs-lookup"><span data-stu-id="0b439-123">Check your existing  licenses</span></span>
<span data-ttu-id="0b439-124">Accedere a Microsoft 365 Admin Center ([admin.Microsoft.com](https://admin.microsoft.com/)) per visualizzare le licenze esistenti.</span><span class="sxs-lookup"><span data-stu-id="0b439-124">Go to Microsoft 365 admin center ([admin.microsoft.com](https://admin.microsoft.com/)) to view your existing licenses.</span></span> <span data-ttu-id="0b439-125">Nell'interfaccia di amministrazione, andare in **Fatturazione** > **Licenze**.</span><span class="sxs-lookup"><span data-stu-id="0b439-125">In the admin center, go to **Billing** > **Licenses**.</span></span>

>[!NOTE]
> <span data-ttu-id="0b439-126">Per poter visualizzare le informazioni sulla licenza, è necessario essere assegnati al ruolo di **amministratore di fatturazione** o **lettore globale** [in Azure ad](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) .</span><span class="sxs-lookup"><span data-stu-id="0b439-126">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see license information.</span></span> <span data-ttu-id="0b439-127">Se si verificano problemi di accesso, rivolgersi a un amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="0b439-127">If you encounter access problems, contact a global admin.</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="0b439-128">Requisiti per il browser</span><span class="sxs-lookup"><span data-stu-id="0b439-128">Browser requirements</span></span>
<span data-ttu-id="0b439-129">Accedere a Microsoft Threat Protection nel centro sicurezza Microsoft 365 utilizzando Microsoft Edge, Internet Explorer 11 o qualsiasi Web browser compatibile con HTML 5.</span><span class="sxs-lookup"><span data-stu-id="0b439-129">Access Microsoft Threat Protection in the Microsoft 365 security center using Microsoft Edge, Internet Explorer 11, or any HTML 5 compliant web browser.</span></span>

## <a name="microsoft-threat-protection-for-us-government-community-cloud-and-us-government-community-cloud-high-gcc-high-customers"></a><span data-ttu-id="0b439-130">Microsoft Threat Protection per il governo degli Stati Uniti Cloud Community and US Government community Cloud High (GCC High) clienti</span><span class="sxs-lookup"><span data-stu-id="0b439-130">Microsoft Threat Protection for US Government Community Cloud and US Government Community Cloud High (GCC High) customers</span></span>
<span data-ttu-id="0b439-131">Attualmente, Microsoft Threat Protection non è disponibile per i clienti americani GCC e GCC High.</span><span class="sxs-lookup"><span data-stu-id="0b439-131">Currently, Microsoft Threat Protection is not available to US GCC and GCC High customers.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="0b439-132">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="0b439-132">Related topics</span></span>
- [<span data-ttu-id="0b439-133">Panoramica su Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="0b439-133">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="0b439-134">Attivare Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="0b439-134">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)
