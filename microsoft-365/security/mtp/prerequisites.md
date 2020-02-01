---
title: Prerequisiti di Microsoft Threat Protection
description: Informazioni sui requisiti di licenza, hardware e software e altre impostazioni di configurazione per Microsoft Threat Protection
keywords: requisiti, prerequisiti, hardware, software, browser, MTP, M365, License
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
ms.openlocfilehash: d45be77abd404f87484d0f8390f09f1b9bc3b8ce
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600008"
---
# <a name="microsoft-threat-protection-prerequisites"></a><span data-ttu-id="fe0e0-104">Prerequisiti di Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="fe0e0-104">Microsoft Threat Protection prerequisites</span></span>

<span data-ttu-id="fe0e0-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="fe0e0-105">**Applies to:**</span></span>
- <span data-ttu-id="fe0e0-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="fe0e0-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="fe0e0-107">Informazioni sui requisiti di licenza, hardware e software e altre impostazioni di configurazione per eseguire e sfruttare Sicurezza Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fe0e0-107">Learn about the licensing, hardware and software requirements, and other configuration settings to run and use the Microsoft 365 security.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="fe0e0-108">Requisiti per la licenza</span><span class="sxs-lookup"><span data-stu-id="fe0e0-108">Licensing requirements</span></span>
<span data-ttu-id="fe0e0-109">Sicurezza Microsoft 365 richiede una delle licenze seguenti:</span><span class="sxs-lookup"><span data-stu-id="fe0e0-109">Microsoft 365 security requires one of the following licenses:</span></span>

- <span data-ttu-id="fe0e0-110">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="fe0e0-110">Microsoft 365 E5</span></span> 
- <span data-ttu-id="fe0e0-111">Office 365 E5, Enterprise Mobility + Security E5 e Windows E5</span><span class="sxs-lookup"><span data-stu-id="fe0e0-111">Office 365 E5, Enterprise Mobility + Security E5, and Windows E5</span></span>

<span data-ttu-id="fe0e0-112">Queste licenze possono essere acquisite dalla [pagina Microsoft 365 Enterprise](https://www.microsoft.com/en-us/microsoft-365/enterprise).</span><span class="sxs-lookup"><span data-stu-id="fe0e0-112">You can acquire these licenses from the [Microsoft 365 enterprise page](https://www.microsoft.com/en-us/microsoft-365/enterprise).</span></span>

### <a name="check-your-existing--licenses"></a><span data-ttu-id="fe0e0-113">Controllare le licenze esistenti</span><span class="sxs-lookup"><span data-stu-id="fe0e0-113">Check your existing  licenses</span></span>
<span data-ttu-id="fe0e0-114">Andare nell'interfaccia di amministrazione di Microsoft 365 su [admin.microsoft.com](https://admin.microsoft.com/) per visualizzare le licenze esistenti.</span><span class="sxs-lookup"><span data-stu-id="fe0e0-114">Go to Microsoft 365 admin center at [admin.microsoft.com](https://admin.microsoft.com/) to view your existing licenses.</span></span> <span data-ttu-id="fe0e0-115">Nell'interfaccia di amministrazione, andare in **Fatturazione** > **Licenze**.</span><span class="sxs-lookup"><span data-stu-id="fe0e0-115">In the admin center, go to **Billing** > **Licenses**.</span></span>

<span data-ttu-id="fe0e0-116">È necessario avere il ruolo di **amministratore fatturazione** o **lettore globale** [ in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) per poter visualizzare le informazioni sulla licenza.</span><span class="sxs-lookup"><span data-stu-id="fe0e0-116">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see licensing information.</span></span> <span data-ttu-id="fe0e0-117">Se si verificano problemi di accesso, rivolgersi a un amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="fe0e0-117">If you encounter access problems, contact a global admin.</span></span>  

## <a name="browser-requirements"></a><span data-ttu-id="fe0e0-118">Requisiti per il browser</span><span class="sxs-lookup"><span data-stu-id="fe0e0-118">Browser requirements</span></span>
<span data-ttu-id="fe0e0-119">Per accedere al Centro sicurezza Microsoft 365, è possibile usare un browser.</span><span class="sxs-lookup"><span data-stu-id="fe0e0-119">Access to Microsoft 365 security center is done through a browser.</span></span> <span data-ttu-id="fe0e0-120">Internet Explorer e Microsoft Edge sono supportati.</span><span class="sxs-lookup"><span data-stu-id="fe0e0-120">Internet Explorer and Microsoft Edge is supported.</span></span> <span data-ttu-id="fe0e0-121">È supportato anche qualsiasi browser compatibile con HTML5.</span><span class="sxs-lookup"><span data-stu-id="fe0e0-121">Any HTML5 compliant browsers are also supported.</span></span>

## <a name="related-topics"></a><span data-ttu-id="fe0e0-122">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="fe0e0-122">Related topics</span></span>
- [<span data-ttu-id="fe0e0-123">Panoramica su Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="fe0e0-123">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="fe0e0-124">Attivare Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="fe0e0-124">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)