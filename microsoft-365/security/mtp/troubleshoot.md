---
title: Risoluzione dei problemi relativi al servizio Microsoft 365 Defender
description: Individuare soluzioni e risolvere i problemi noti di Microsoft 365 Defender
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
ms.openlocfilehash: 16cb1116f400c8d0a83ccc4cac23da06cd1be2a4
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844669"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a><span data-ttu-id="ea038-104">Risoluzione dei problemi relativi al servizio Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ea038-104">Troubleshoot Microsoft 365 Defender service issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="ea038-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="ea038-105">**Applies to:**</span></span>
- <span data-ttu-id="ea038-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ea038-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="ea038-107">In questa sezione vengono affrontati i problemi che potrebbero verificarsi durante l'utilizzo del servizio Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="ea038-107">This section addresses issues that might arise as you use the Microsoft 365 Defender service.</span></span>


## <a name="i-dont-see-microsoft-365-defender-content"></a><span data-ttu-id="ea038-108">Non viene visualizzato il contenuto Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ea038-108">I don't see Microsoft 365 Defender content</span></span>
<span data-ttu-id="ea038-109">Se non si visualizzano le funzionalità nel riquadro di spostamento, ad esempio gli eventi non consentiti, il centro azioni o la ricerca nel portale, è necessario verificare che il tenant disponga delle licenze appropriate.</span><span class="sxs-lookup"><span data-stu-id="ea038-109">If you don't see capabilities on the navigation pane such as the Incidents, Action Center, or Hunting in your portal, you'll need to verify that your tenant has the appropriate licenses.</span></span> 

<span data-ttu-id="ea038-110">Per altre informazioni, vedere [Prerequisiti](prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="ea038-110">For more information, see [Prerequisites](prerequisites.md).</span></span>

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a><span data-ttu-id="ea038-111">Microsoft Defender per gli avvisi di identità non viene visualizzato negli incidenti Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ea038-111">Microsoft Defender for Identity alerts are not showing up in the Microsoft 365 Defender incidents</span></span>
<span data-ttu-id="ea038-112">Se si dispone di Microsoft Defender per Identity distribuito nell'ambiente, ma non si vedono i difensori per gli avvisi di identità come parte degli incidenti Microsoft 365 Defender, è necessario verificare che Microsoft cloud app Security and Defender for Identity Integration sia abilitato.</span><span class="sxs-lookup"><span data-stu-id="ea038-112">If you have Microsoft Defender for Identity deployed in your environment but you're not seeing Defender for Identity alerts as part of Microsoft 365 Defender incidents, you'll need to ensure that the Microsoft Cloud App Security and Defender for Identity integration is enabled.</span></span> 

<span data-ttu-id="ea038-113">Per ulteriori informazioni, vedere [Microsoft Defender for Identity Integration](https://docs.microsoft.com/cloud-app-security/aatp-integration).</span><span class="sxs-lookup"><span data-stu-id="ea038-113">For more information, see [Microsoft Defender for Identity integration](https://docs.microsoft.com/cloud-app-security/aatp-integration).</span></span>

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a><span data-ttu-id="ea038-114">Dove si trova la pagina impostazioni per l'attivazione del servizio?</span><span class="sxs-lookup"><span data-stu-id="ea038-114">Where is the settings page for turning the service on?</span></span>
<span data-ttu-id="ea038-115">Per abilitare Microsoft 365 Defender, accedere alle **Impostazioni** dal riquadro di spostamento nel centro sicurezza di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ea038-115">To turn on Microsoft 365 Defender, access **Settings** from the navigation pane in the Microsoft 365 security center.</span></span> <span data-ttu-id="ea038-116">Questo elemento di spostamento è visibile solo se si dispone delle [autorizzazioni e delle licenze prerequisite](mtp-enable.md#check-license-eligibility-and-required-permissions).</span><span class="sxs-lookup"><span data-stu-id="ea038-116">This navigation item is visible only if you have the [prerequisite permissions and licenses](mtp-enable.md#check-license-eligibility-and-required-permissions).</span></span>
 

