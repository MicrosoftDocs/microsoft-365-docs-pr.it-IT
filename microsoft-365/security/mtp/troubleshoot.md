---
title: Risoluzione dei problemi relativi al servizio Microsoft Threat Protection
description: Individuare le soluzioni e aggirare i problemi noti relativi a Microsoft Threat Protection
keywords: risoluzione dei problemi relativi alla protezione dalle minacce Microsoft, risoluzione dei problemi, Azure ATP, problemi, componente aggiuntivo, pagina impostazioni
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
ms.openlocfilehash: bcf5b79fcd2fdf0a5af5648e6f6b7ea65d69594c
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201292"
---
# <a name="troubleshoot-microsoft-threat-protection-service-issues"></a><span data-ttu-id="77520-104">Risoluzione dei problemi relativi al servizio Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="77520-104">Troubleshoot Microsoft Threat Protection service issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="77520-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="77520-105">**Applies to:**</span></span>
- <span data-ttu-id="77520-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="77520-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="77520-107">Questa sezione consente di risolvere i problemi che potrebbero verificarsi se si utilizza il servizio Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="77520-107">This section addresses issues that might arise as you use the Microsoft Threat Protection service.</span></span>


## <a name="i-dont-see-microsoft-threat-protection-content"></a><span data-ttu-id="77520-108">Non viene visualizzato il contenuto di Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="77520-108">I don't see Microsoft Threat Protection content</span></span>
<span data-ttu-id="77520-109">Se non si visualizzano le funzionalità nel riquadro di spostamento, ad esempio gli eventi non consentiti, il centro azioni o la ricerca nel portale, è necessario verificare che il tenant disponga delle licenze appropriate.</span><span class="sxs-lookup"><span data-stu-id="77520-109">If you don't see capabilities on the navigation pane such as the Incidents, Action Center, or Hunting in your portal, you'll need to verify that your tenant has the appropriate licenses.</span></span> 

<span data-ttu-id="77520-110">Per altre informazioni, vedere [Prerequisiti](prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="77520-110">For more information, see [Prerequisites](prerequisites.md).</span></span>

## <a name="azure-atp-alerts-are-not-showing-up-in-the-microsoft-threat-protection-incidents"></a><span data-ttu-id="77520-111">Gli avvisi di Azure ATP non sono visualizzati tra gli incidenti di Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="77520-111">Azure ATP alerts are not showing up in the Microsoft Threat Protection incidents</span></span>
<span data-ttu-id="77520-112">Se si utilizza Azure ATP nell'ambiente distribuito ma non è possibile vedere gli avvisi di Azure ATP come incidenti di Microsoft Threat Protection, è necessario verificare che sia abilitata l'integrazione di Microsoft Cloud App Security e Azure ATP.</span><span class="sxs-lookup"><span data-stu-id="77520-112">If you have Azure ATP deployed in your environment but you're not seeing Azure ATP alerts as part of Microsoft Threat Protection incidents, you'll need to ensure that the Microsoft Cloud App Security and Azure ATP integration is enabled.</span></span> 

<span data-ttu-id="77520-113">Per altre informazioni, vedere [Integrazione di Azure ATP](https://docs.microsoft.com/cloud-app-security/aatp-integration).</span><span class="sxs-lookup"><span data-stu-id="77520-113">For more information, see [Azure ATP integration](https://docs.microsoft.com/cloud-app-security/aatp-integration).</span></span>

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a><span data-ttu-id="77520-114">Dove si trova la pagina impostazioni per l'attivazione del servizio?</span><span class="sxs-lookup"><span data-stu-id="77520-114">Where is the settings page for turning the service on?</span></span>
<span data-ttu-id="77520-115">Per abilitare Microsoft Threat Protection, accedere alle **Impostazioni** dal riquadro di spostamento nel centro sicurezza di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="77520-115">To turn on Microsoft Threat Protection, access **Settings** from the navigation pane in the Microsoft 365 security center.</span></span> <span data-ttu-id="77520-116">Questo elemento di spostamento è visibile solo se si dispone delle [autorizzazioni e delle licenze prerequisite](mtp-enable.md#check-license-eligibility-and-required-permissions).</span><span class="sxs-lookup"><span data-stu-id="77520-116">This navigation item is visible only if you have the [prerequisite permissions and licenses](mtp-enable.md#check-license-eligibility-and-required-permissions).</span></span>
 

