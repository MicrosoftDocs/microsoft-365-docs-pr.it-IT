---
title: Onboard di dispositivi non Windows al servizio Microsoft Defender for Endpoint
description: Configurare dispositivi non Windows in modo che possano inviare i dati del sensore al servizio Microsoft Defender for Endpoint.
keywords: onboard non Windows dispositivi, macos, linux, gestione dei dispositivi, configurare Microsoft Defender per dispositivi endpoint
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 4aff505f9f35b6144360eed5992ac36cf0847617
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454710"
---
# <a name="onboard-non-windows-devices"></a><span data-ttu-id="93298-104">Aggiungere dispositivi non Windows</span><span class="sxs-lookup"><span data-stu-id="93298-104">Onboard non-Windows devices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="93298-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="93298-105">**Applies to:**</span></span>
- [<span data-ttu-id="93298-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="93298-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="93298-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="93298-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="93298-108">**Piattaforme**</span><span class="sxs-lookup"><span data-stu-id="93298-108">**Platforms**</span></span>
- <span data-ttu-id="93298-109">macOS</span><span class="sxs-lookup"><span data-stu-id="93298-109">macOS</span></span>
- <span data-ttu-id="93298-110">Linux</span><span class="sxs-lookup"><span data-stu-id="93298-110">Linux</span></span>

><span data-ttu-id="93298-111">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="93298-111">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="93298-112">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="93298-112">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-nonwindows-abovefoldlink) 

<span data-ttu-id="93298-113">Defender for Endpoint offre un'esperienza operativa di sicurezza centralizzata per Windows e piattaforme non Windows.</span><span class="sxs-lookup"><span data-stu-id="93298-113">Defender for Endpoint provides a centralized security operations experience for Windows as well as non-Windows platforms.</span></span> <span data-ttu-id="93298-114">Sarà possibile visualizzare gli avvisi di vari sistemi operativi supportati in Microsoft 365 Defender e proteggere meglio la rete dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="93298-114">You'll be able to see alerts from various supported operating systems (OS) in Microsoft 365 Defender and better protect your organization's network.</span></span> 

<span data-ttu-id="93298-115">Per il funzionamento dell'integrazione, devi conoscere esattamente le versioni di Linux e macOS compatibili con Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="93298-115">You'll need to know the exact Linux distros and macOS versions that are compatible with Defender for Endpoint for the integration to work.</span></span> <span data-ttu-id="93298-116">Per ulteriori informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="93298-116">For more information, see:</span></span>
- [<span data-ttu-id="93298-117">Requisiti di sistema di Microsoft Defender for Endpoint on Linux</span><span class="sxs-lookup"><span data-stu-id="93298-117">Microsoft Defender for Endpoint on Linux system requirements</span></span>](microsoft-defender-endpoint-linux.md#system-requirements)  
- <span data-ttu-id="93298-118">Requisiti di sistema di [Microsoft Defender per Endpoint su macOS](microsoft-defender-endpoint-mac.md#system-requirements).</span><span class="sxs-lookup"><span data-stu-id="93298-118">[Microsoft Defender for Endpoint on macOS system requirements](microsoft-defender-endpoint-mac.md#system-requirements).</span></span>

## <a name="onboarding-non-windows-devices"></a><span data-ttu-id="93298-119">Onboarding di dispositivi non Windows</span><span class="sxs-lookup"><span data-stu-id="93298-119">Onboarding non-Windows devices</span></span>
<span data-ttu-id="93298-120">Dovrai eseguire la procedura seguente per eseguire l'onboard di dispositivi non Windows dispositivo:</span><span class="sxs-lookup"><span data-stu-id="93298-120">You'll need to take the following steps to onboard non-Windows devices:</span></span>
1. <span data-ttu-id="93298-121">Seleziona il metodo di onboarding preferito:</span><span class="sxs-lookup"><span data-stu-id="93298-121">Select your preferred method of onboarding:</span></span>

   - <span data-ttu-id="93298-122">Per i dispositivi macOS, puoi scegliere di eseguire l'onboard tramite Microsoft Defender for Endpoint o tramite una soluzione di terze parti.</span><span class="sxs-lookup"><span data-stu-id="93298-122">For macOS devices, you can choose to onboard through Microsoft Defender for Endpoint or through a third-party solution.</span></span> <span data-ttu-id="93298-123">Per altre informazioni, vedi [Microsoft Defender per Endpoint su Mac.](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint-mac)</span><span class="sxs-lookup"><span data-stu-id="93298-123">For more information, see [Microsoft Defender for Endpoint on Mac](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint-mac).</span></span>

   - <span data-ttu-id="93298-124">Per altri dispositivi non Windows, scegli Onboard non Windows dispositivi **tramite l'integrazione di terze parti.**</span><span class="sxs-lookup"><span data-stu-id="93298-124">For other non-Windows devices, choose **Onboard non-Windows devices through third-party integration**.</span></span>   
    1. <span data-ttu-id="93298-125">Nel riquadro di spostamento selezionare **Partner di**  >  **interoperabilità**.</span><span class="sxs-lookup"><span data-stu-id="93298-125">In the navigation pane, select **Interoperability** > **Partners**.</span></span> <span data-ttu-id="93298-126">Verificare che la soluzione di terze parti sia elencata.</span><span class="sxs-lookup"><span data-stu-id="93298-126">Make sure the third-party solution is listed.</span></span>
    2. <span data-ttu-id="93298-127">Nella scheda **Applicazioni partner** seleziona il partner che supporta i dispositivi non Windows partner.</span><span class="sxs-lookup"><span data-stu-id="93298-127">In the **Partner Applications** tab, select the partner that supports your non-Windows devices.</span></span>
    3. <span data-ttu-id="93298-128">Seleziona **Apri pagina partner** per aprire la pagina del partner.</span><span class="sxs-lookup"><span data-stu-id="93298-128">Select **Open partner page** to open the partner's page.</span></span> <span data-ttu-id="93298-129">Segui le istruzioni fornite nella pagina.</span><span class="sxs-lookup"><span data-stu-id="93298-129">Follow the instructions provided on the page.</span></span>
    4. <span data-ttu-id="93298-130">Dopo aver creato un account o aver accettato la sottoscrizione alla soluzione partner, è consigliabile arrivare a una fase in cui a un amministratore globale tenant dell'organizzazione viene richiesto di accettare una richiesta di autorizzazione dall'applicazione partner.</span><span class="sxs-lookup"><span data-stu-id="93298-130">After creating an account or subscribing to the partner solution, you should get to a stage where a tenant Global Admin in your organization is asked to accept a permission request from the partner application.</span></span> <span data-ttu-id="93298-131">Leggere attentamente la richiesta di autorizzazione per assicurarsi che sia allineata al servizio richiesto.</span><span class="sxs-lookup"><span data-stu-id="93298-131">Read the permission request carefully to make sure that it is aligned with the service that you require.</span></span> 

        
2. <span data-ttu-id="93298-132">Eseguire un test di rilevamento seguendo le istruzioni della soluzione di terze parti.</span><span class="sxs-lookup"><span data-stu-id="93298-132">Run a detection test by following the instructions of the third-party solution.</span></span>

## <a name="offboard-non-windows-devices"></a><span data-ttu-id="93298-133">Offboard non Windows dispositivi</span><span class="sxs-lookup"><span data-stu-id="93298-133">Offboard non-Windows devices</span></span>

1. <span data-ttu-id="93298-134">Seguire la documentazione di terze parti per disconnettere la soluzione di terze parti da Microsoft Defender per Endpoint.</span><span class="sxs-lookup"><span data-stu-id="93298-134">Follow the third-party's documentation to disconnect the third-party solution from Microsoft Defender for Endpoint.</span></span>

2. <span data-ttu-id="93298-135">Rimuovere le autorizzazioni per la soluzione di terze parti nel tenant di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="93298-135">Remove permissions for the third-party solution in your Azure AD tenant.</span></span>
   1. <span data-ttu-id="93298-136">Accedere al [portale di Azure](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="93298-136">Sign in to the [Azure portal](https://portal.azure.com).</span></span>
   2. <span data-ttu-id="93298-137">Selezionare **Azure Active Directory > Enterprise applicazioni**.</span><span class="sxs-lookup"><span data-stu-id="93298-137">Select **Azure Active Directory > Enterprise Applications**.</span></span>
   3. <span data-ttu-id="93298-138">Seleziona l'applicazione che vuoi offboard.</span><span class="sxs-lookup"><span data-stu-id="93298-138">Select the application you'd like to offboard.</span></span>
   4. <span data-ttu-id="93298-139">Selezionare il **pulsante** Elimina.</span><span class="sxs-lookup"><span data-stu-id="93298-139">Select the **Delete** button.</span></span>


## <a name="related-topics"></a><span data-ttu-id="93298-140">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="93298-140">Related topics</span></span>
- [<span data-ttu-id="93298-141">Aggiungere di dispositivi Windows 10</span><span class="sxs-lookup"><span data-stu-id="93298-141">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="93298-142">Server di onboard</span><span class="sxs-lookup"><span data-stu-id="93298-142">Onboard servers</span></span>](configure-server-endpoints.md)
- [<span data-ttu-id="93298-143">Configurare le impostazioni di connettività Proxy e Internet</span><span class="sxs-lookup"><span data-stu-id="93298-143">Configure proxy and Internet connectivity settings</span></span>](configure-proxy-internet.md)
- [<span data-ttu-id="93298-144">Risoluzione dei problemi di onboarding di Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="93298-144">Troubleshooting Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
