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
ms.openlocfilehash: ef26a2ebc25d7f55e7dc22347d85767dab970536
ms.sourcegitcommit: 9224a7a5886c0c5fa0bc12bd9f7234a0eba90023
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/02/2020
ms.locfileid: "42372054"
---
# <a name="microsoft-threat-protection-prerequisites"></a><span data-ttu-id="3cbed-104">Prerequisiti di Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="3cbed-104">Microsoft Threat Protection prerequisites</span></span>

<span data-ttu-id="3cbed-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="3cbed-105">**Applies to:**</span></span>
- <span data-ttu-id="3cbed-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="3cbed-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="3cbed-107">Informazioni sui requisiti di licenza, hardware e software e altre impostazioni di configurazione per il provisioning e l'utilizzo di Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="3cbed-107">Learn about the licensing, hardware and software requirements, and other configuration settings to provision and use Microsoft Threat Protection.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="3cbed-108">Requisiti per la licenza</span><span class="sxs-lookup"><span data-stu-id="3cbed-108">Licensing requirements</span></span>
<span data-ttu-id="3cbed-109">Per utilizzare Microsoft Threat Protection, è necessaria *una* delle seguenti licenze o combinazioni di licenze:</span><span class="sxs-lookup"><span data-stu-id="3cbed-109">To use Microsoft Threat Protection, you need *one* of the following licenses or combination of licenses:</span></span>

- <span data-ttu-id="3cbed-110">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="3cbed-110">Microsoft 365 E5</span></span>
- <span data-ttu-id="3cbed-111">Microsoft 365 E5 Security</span><span class="sxs-lookup"><span data-stu-id="3cbed-111">Microsoft 365 E5 Security</span></span>
- <span data-ttu-id="3cbed-112">Office 365 E5 e "Enterprise Mobility + Security E5 (EMS E5)" e Windows E5</span><span class="sxs-lookup"><span data-stu-id="3cbed-112">Office 365 E5 and "Enterprise Mobility + Security E5 (EMS E5)" and Windows E5</span></span>
- <span data-ttu-id="3cbed-113">Microsoft 365 A5</span><span class="sxs-lookup"><span data-stu-id="3cbed-113">Microsoft 365 A5</span></span>
- <span data-ttu-id="3cbed-114">Microsoft 365 A5 Security</span><span class="sxs-lookup"><span data-stu-id="3cbed-114">Microsoft 365 A5 Security</span></span>
- <span data-ttu-id="3cbed-115">Office 365 a5 e "Enterprise Mobility + Security a5 (EMS a5)" e Windows a5</span><span class="sxs-lookup"><span data-stu-id="3cbed-115">Office 365 A5 and "Enterprise Mobility + Security A5 (EMS A5)" and Windows A5</span></span>

<span data-ttu-id="3cbed-116">Per ulteriori informazioni, [vedere i piani del servizio Microsoft 365 Enterprise](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span><span class="sxs-lookup"><span data-stu-id="3cbed-116">For more information, [view the Microsoft 365 Enterprise service plans](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span></span>

> <span data-ttu-id="3cbed-117">Non si dispone ancora di una licenza?</span><span class="sxs-lookup"><span data-stu-id="3cbed-117">Don't have license yet?</span></span> [<span data-ttu-id="3cbed-118">Provare o acquistare un abbonamento a Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3cbed-118">Try or buy a Microsoft 365 subscription</span></span>](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a><span data-ttu-id="3cbed-119">Controllare le licenze esistenti</span><span class="sxs-lookup"><span data-stu-id="3cbed-119">Check your existing  licenses</span></span>
<span data-ttu-id="3cbed-120">Accedere a Microsoft 365 Admin Center ([admin.Microsoft.com](https://admin.microsoft.com/)) per visualizzare le licenze esistenti.</span><span class="sxs-lookup"><span data-stu-id="3cbed-120">Go to Microsoft 365 admin center ([admin.microsoft.com](https://admin.microsoft.com/)) to view your existing licenses.</span></span> <span data-ttu-id="3cbed-121">Nell'interfaccia di amministrazione, andare in **Fatturazione** > **Licenze**.</span><span class="sxs-lookup"><span data-stu-id="3cbed-121">In the admin center, go to **Billing** > **Licenses**.</span></span>

>[!NOTE]
> <span data-ttu-id="3cbed-122">Per poter visualizzare le informazioni sulla licenza, è necessario essere assegnati al ruolo di **amministratore di fatturazione** o **lettore globale** [in Azure ad](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) .</span><span class="sxs-lookup"><span data-stu-id="3cbed-122">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see license information.</span></span> <span data-ttu-id="3cbed-123">Se si verificano problemi di accesso, rivolgersi a un amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="3cbed-123">If you encounter access problems, contact a global admin.</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="3cbed-124">Requisiti per il browser</span><span class="sxs-lookup"><span data-stu-id="3cbed-124">Browser requirements</span></span>
<span data-ttu-id="3cbed-125">Accedere a Microsoft Threat Protection nel centro sicurezza Microsoft 365 utilizzando Microsoft Edge, Internet Explorer 11 o qualsiasi Web browser compatibile con HTML 5.</span><span class="sxs-lookup"><span data-stu-id="3cbed-125">Access Microsoft Threat Protection in the Microsoft 365 security center using Microsoft Edge, Internet Explorer 11, or any HTML 5 compliant web browser.</span></span>

## <a name="related-topics"></a><span data-ttu-id="3cbed-126">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="3cbed-126">Related topics</span></span>
- [<span data-ttu-id="3cbed-127">Panoramica su Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="3cbed-127">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="3cbed-128">Attivare Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="3cbed-128">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)
