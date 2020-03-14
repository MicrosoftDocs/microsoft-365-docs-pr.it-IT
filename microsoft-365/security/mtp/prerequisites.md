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
ms.openlocfilehash: 2b653575e9e79ffe3448f622ca5be2cef37999dd
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/13/2020
ms.locfileid: "42633954"
---
# <a name="microsoft-threat-protection-prerequisites"></a><span data-ttu-id="eb47f-104">Prerequisiti di Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="eb47f-104">Microsoft Threat Protection prerequisites</span></span>

<span data-ttu-id="eb47f-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="eb47f-105">**Applies to:**</span></span>
- <span data-ttu-id="eb47f-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="eb47f-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="eb47f-107">Informazioni sui requisiti di licenza, hardware e software e altre impostazioni di configurazione per il provisioning e l'utilizzo di Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="eb47f-107">Learn about the licensing, hardware and software requirements, and other configuration settings to provision and use Microsoft Threat Protection.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="eb47f-108">Requisiti per la licenza</span><span class="sxs-lookup"><span data-stu-id="eb47f-108">Licensing requirements</span></span>
<span data-ttu-id="eb47f-109">Per utilizzare Microsoft Threat Protection, è necessaria *una* delle seguenti licenze o combinazioni di licenze:</span><span class="sxs-lookup"><span data-stu-id="eb47f-109">To use Microsoft Threat Protection, you need *one* of the following licenses or combination of licenses:</span></span>

- <span data-ttu-id="eb47f-110">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="eb47f-110">Microsoft 365 E5</span></span>
- <span data-ttu-id="eb47f-111">Microsoft 365 E5 Security</span><span class="sxs-lookup"><span data-stu-id="eb47f-111">Microsoft 365 E5 Security</span></span>
- <span data-ttu-id="eb47f-112">Office 365 E5 e "Enterprise Mobility + Security E5 (EMS E5)" e Windows E5</span><span class="sxs-lookup"><span data-stu-id="eb47f-112">Office 365 E5 and "Enterprise Mobility + Security E5 (EMS E5)" and Windows E5</span></span>
- <span data-ttu-id="eb47f-113">Microsoft 365 A5</span><span class="sxs-lookup"><span data-stu-id="eb47f-113">Microsoft 365 A5</span></span>

<span data-ttu-id="eb47f-114">Per ulteriori informazioni, [vedere i piani del servizio Microsoft 365 Enterprise](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span><span class="sxs-lookup"><span data-stu-id="eb47f-114">For more information, [view the Microsoft 365 Enterprise service plans](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span></span>

> <span data-ttu-id="eb47f-115">Non si dispone ancora di una licenza?</span><span class="sxs-lookup"><span data-stu-id="eb47f-115">Don't have license yet?</span></span> [<span data-ttu-id="eb47f-116">Provare o acquistare un abbonamento a Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="eb47f-116">Try or buy a Microsoft 365 subscription</span></span>](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a><span data-ttu-id="eb47f-117">Controllare le licenze esistenti</span><span class="sxs-lookup"><span data-stu-id="eb47f-117">Check your existing  licenses</span></span>
<span data-ttu-id="eb47f-118">Accedere a Microsoft 365 Admin Center ([admin.Microsoft.com](https://admin.microsoft.com/)) per visualizzare le licenze esistenti.</span><span class="sxs-lookup"><span data-stu-id="eb47f-118">Go to Microsoft 365 admin center ([admin.microsoft.com](https://admin.microsoft.com/)) to view your existing licenses.</span></span> <span data-ttu-id="eb47f-119">Nell'interfaccia di amministrazione, andare in **Fatturazione** > **Licenze**.</span><span class="sxs-lookup"><span data-stu-id="eb47f-119">In the admin center, go to **Billing** > **Licenses**.</span></span>

>[!NOTE]
> <span data-ttu-id="eb47f-120">Per poter visualizzare le informazioni sulla licenza, è necessario essere assegnati al ruolo di **amministratore di fatturazione** o **lettore globale** [in Azure ad](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) .</span><span class="sxs-lookup"><span data-stu-id="eb47f-120">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see license information.</span></span> <span data-ttu-id="eb47f-121">Se si verificano problemi di accesso, rivolgersi a un amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="eb47f-121">If you encounter access problems, contact a global admin.</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="eb47f-122">Requisiti per il browser</span><span class="sxs-lookup"><span data-stu-id="eb47f-122">Browser requirements</span></span>
<span data-ttu-id="eb47f-123">Accedere a Microsoft Threat Protection nel centro sicurezza Microsoft 365 utilizzando Microsoft Edge, Internet Explorer 11 o qualsiasi Web browser compatibile con HTML 5.</span><span class="sxs-lookup"><span data-stu-id="eb47f-123">Access Microsoft Threat Protection in the Microsoft 365 security center using Microsoft Edge, Internet Explorer 11, or any HTML 5 compliant web browser.</span></span>

## <a name="microsoft-threat-protection-for-us-government-community-cloud-and-us-government-community-cloud-high-gcc-high-customers"></a><span data-ttu-id="eb47f-124">Microsoft Threat Protection per il governo degli Stati Uniti Cloud Community and US Government community Cloud High (GCC High) clienti</span><span class="sxs-lookup"><span data-stu-id="eb47f-124">Microsoft Threat Protection for US Government Community Cloud and US Government Community Cloud High (GCC High) customers</span></span>
<span data-ttu-id="eb47f-125">Attualmente, Microsoft Threat Protection non è disponibile per i clienti americani GCC e GCC High.</span><span class="sxs-lookup"><span data-stu-id="eb47f-125">Currently, Microsoft Threat Protection is not available to US GCC and GCC High customers.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="eb47f-126">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="eb47f-126">Related topics</span></span>
- [<span data-ttu-id="eb47f-127">Panoramica su Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="eb47f-127">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="eb47f-128">Attivare Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="eb47f-128">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)
