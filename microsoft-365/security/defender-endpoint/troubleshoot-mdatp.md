---
title: Risolvere i problemi relativi al servizio Microsoft Defender for Endpoint
description: Trovare soluzioni e soluzioni alternative a problemi noti, ad esempio errori del server quando si tenta di accedere al servizio.
keywords: risolvere i problemi di microsoft Defender per l'endpoint, risolvere i problemi di Windows ATP, errore del server, accesso negato, credenziali non valide, nessun dato, portale dashboard, consenti, visualizzatore eventi
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
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: 112f682836da37ddfb51c103282518ff74563727
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186018"
---
# <a name="troubleshoot-service-issues"></a><span data-ttu-id="a84dc-104">Risolvere i problemi relativi ai servizi</span><span class="sxs-lookup"><span data-stu-id="a84dc-104">Troubleshoot service issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a84dc-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="a84dc-105">**Applies to:**</span></span>
- [<span data-ttu-id="a84dc-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="a84dc-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a84dc-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a84dc-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="a84dc-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="a84dc-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a84dc-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="a84dc-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


<span data-ttu-id="a84dc-110">Questa sezione risolve i problemi che possono verificarsi quando usi il servizio Microsoft Defender Advanced Threat.</span><span class="sxs-lookup"><span data-stu-id="a84dc-110">This section addresses issues that might arise as you use the Microsoft Defender Advanced Threat service.</span></span>

## <a name="server-error---access-is-denied-due-to-invalid-credentials"></a><span data-ttu-id="a84dc-111">Errore del server - Accesso negato a causa di credenziali non valide</span><span class="sxs-lookup"><span data-stu-id="a84dc-111">Server error - Access is denied due to invalid credentials</span></span>
<span data-ttu-id="a84dc-112">Se si verifica un errore del server quando si tenta di accedere al servizio, è necessario modificare le impostazioni dei cookie del browser.</span><span class="sxs-lookup"><span data-stu-id="a84dc-112">If you encounter a server error when trying to access the service, you’ll need to change your browser cookie settings.</span></span>
<span data-ttu-id="a84dc-113">Configurare il browser per consentire i cookie.</span><span class="sxs-lookup"><span data-stu-id="a84dc-113">Configure your browser to allow cookies.</span></span>

## <a name="elements-or-data-missing-on-the-portal"></a><span data-ttu-id="a84dc-114">Elementi o dati mancanti nel portale</span><span class="sxs-lookup"><span data-stu-id="a84dc-114">Elements or data missing on the portal</span></span>
<span data-ttu-id="a84dc-115">Se alcuni elementi o dati non sono presenti in Microsoft Defender Security Center, è possibile che le impostazioni proxy lo blocchino.</span><span class="sxs-lookup"><span data-stu-id="a84dc-115">If some elements or data is missing on Microsoft Defender Security Center it’s possible that proxy settings are blocking it.</span></span>

<span data-ttu-id="a84dc-116">Assicurati che sia `*.securitycenter.windows.com` incluso l'elenco di proxy consentiti.</span><span class="sxs-lookup"><span data-stu-id="a84dc-116">Make sure that `*.securitycenter.windows.com` is included the proxy allowlist.</span></span>


> [!NOTE]
> <span data-ttu-id="a84dc-117">È necessario utilizzare il protocollo HTTPS quando si aggiungono gli endpoint seguenti.</span><span class="sxs-lookup"><span data-stu-id="a84dc-117">You must use the HTTPS protocol when adding the following endpoints.</span></span>

## <a name="microsoft-defender-for-endpoint-service-shows-event-or-error-logs-in-the-event-viewer"></a><span data-ttu-id="a84dc-118">Il servizio Microsoft Defender for Endpoint mostra i registri eventi o di errore nel Visualizzatore eventi</span><span class="sxs-lookup"><span data-stu-id="a84dc-118">Microsoft Defender for Endpoint service shows event or error logs in the Event Viewer</span></span>

<span data-ttu-id="a84dc-119">Vedi Esaminare gli eventi e gli errori tramite il [Visualizzatore](event-error-codes.md) eventi per un elenco degli ID evento segnalati dal servizio Microsoft Defender per endpoint.</span><span class="sxs-lookup"><span data-stu-id="a84dc-119">See [Review events and errors using Event Viewer](event-error-codes.md) for a list of event IDs that are reported by the Microsoft Defender for Endpoint service.</span></span> <span data-ttu-id="a84dc-120">L'articolo contiene anche i passaggi per la risoluzione dei problemi relativi agli errori degli eventi.</span><span class="sxs-lookup"><span data-stu-id="a84dc-120">The article also contains troubleshooting steps for event errors.</span></span>

## <a name="microsoft-defender-for-endpoint-service-fails-to-start-after-a-reboot-and-shows-error-577"></a><span data-ttu-id="a84dc-121">Microsoft Defender for Endpoint service fails to start after a reboot and shows error 577</span><span class="sxs-lookup"><span data-stu-id="a84dc-121">Microsoft Defender for Endpoint service fails to start after a reboot and shows error 577</span></span>

<span data-ttu-id="a84dc-122">Se l'onboarding dei dispositivi viene completato correttamente ma Microsoft Defender for Endpoint non viene avviato dopo un riavvio e viene visualizzato l'errore 577, verificare che Windows Defender non sia disabilitato da un criterio.</span><span class="sxs-lookup"><span data-stu-id="a84dc-122">If onboarding devices successfully completes but Microsoft Defender for Endpoint does not start after a reboot and shows error 577, check that Windows Defender is not disabled by a policy.</span></span>

<span data-ttu-id="a84dc-123">Per altre informazioni, vedi [Verificare che Microsoft Defender Antivirus non sia disabilitato dai criteri.](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)</span><span class="sxs-lookup"><span data-stu-id="a84dc-123">For more information, see [Ensure that Microsoft Defender Antivirus is not disabled by policy](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy).</span></span>

## <a name="known-issues-with-regional-formats"></a><span data-ttu-id="a84dc-124">Problemi noti con i formati regionali</span><span class="sxs-lookup"><span data-stu-id="a84dc-124">Known issues with regional formats</span></span>

<span data-ttu-id="a84dc-125">**Formati di data e ora**</span><span class="sxs-lookup"><span data-stu-id="a84dc-125">**Date and time formats**</span></span><br>
<span data-ttu-id="a84dc-126">Esistono alcuni problemi noti relativi ai formati di data e ora.</span><span class="sxs-lookup"><span data-stu-id="a84dc-126">There are some known issues with the time and date formats.</span></span> 

<span data-ttu-id="a84dc-127">Sono supportati i formati di data seguenti:</span><span class="sxs-lookup"><span data-stu-id="a84dc-127">The following date formats are supported:</span></span>
- <span data-ttu-id="a84dc-128">MM/gg/aaaa</span><span class="sxs-lookup"><span data-stu-id="a84dc-128">MM/dd/yyyy</span></span>
- <span data-ttu-id="a84dc-129">gg/MM/aaaa</span><span class="sxs-lookup"><span data-stu-id="a84dc-129">dd/MM/yyyy</span></span>

<span data-ttu-id="a84dc-130">I formati di data e ora seguenti non sono attualmente supportati:</span><span class="sxs-lookup"><span data-stu-id="a84dc-130">The following date and time formats are currently not supported:</span></span>
- <span data-ttu-id="a84dc-131">Formato data aaaa/MM/gg</span><span class="sxs-lookup"><span data-stu-id="a84dc-131">Date format yyyy/MM/dd</span></span>
- <span data-ttu-id="a84dc-132">Formato data gg/MM/aa</span><span class="sxs-lookup"><span data-stu-id="a84dc-132">Date format dd/MM/yy</span></span>
- <span data-ttu-id="a84dc-133">Formato data con yy.</span><span class="sxs-lookup"><span data-stu-id="a84dc-133">Date format with yy.</span></span> <span data-ttu-id="a84dc-134">Mostrerà solo aaaa.</span><span class="sxs-lookup"><span data-stu-id="a84dc-134">Will only show yyyy.</span></span>
- <span data-ttu-id="a84dc-135">Formato ora HH:mm:ss non supportato (il formato AM/PM di 12 ore non è supportato).</span><span class="sxs-lookup"><span data-stu-id="a84dc-135">Time format HH:mm:ss is not supported (the 12 hour AM/PM format is not supported).</span></span> <span data-ttu-id="a84dc-136">È supportato solo il formato 24 ore.</span><span class="sxs-lookup"><span data-stu-id="a84dc-136">Only the 24-hour format is supported.</span></span>

<span data-ttu-id="a84dc-137">**Uso della virgola per indicare le migliaia**</span><span class="sxs-lookup"><span data-stu-id="a84dc-137">**Use of comma to indicate thousand**</span></span><br>
<span data-ttu-id="a84dc-138">Il supporto dell'utilizzo della virgola come separatore nei numeri non è supportato.</span><span class="sxs-lookup"><span data-stu-id="a84dc-138">Support of use of comma as a separator in numbers are not supported.</span></span> <span data-ttu-id="a84dc-139">Le aree in cui un numero è separato da una virgola per indicare mille, potranno vedere solo l'uso di un punto come separatore.</span><span class="sxs-lookup"><span data-stu-id="a84dc-139">Regions where a number is separated with a comma to indicate a thousand, will only see the use of a dot as a separator.</span></span> <span data-ttu-id="a84dc-140">Ad esempio, 15,5K viene visualizzato come 15,5K.</span><span class="sxs-lookup"><span data-stu-id="a84dc-140">For example, 15,5K is displayed as 15.5K.</span></span>

><span data-ttu-id="a84dc-141">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="a84dc-141">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a84dc-142">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="a84dc-142">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-troubleshoot-belowfoldlink)

## <a name="microsoft-defender-for-endpoint-tenant-was-automatically-created-in-europe"></a><span data-ttu-id="a84dc-143">Il tenant di Microsoft Defender for Endpoint è stato creato automaticamente in Europa</span><span class="sxs-lookup"><span data-stu-id="a84dc-143">Microsoft Defender for Endpoint tenant was automatically created in Europe</span></span>
<span data-ttu-id="a84dc-144">Quando si utilizza il Centro sicurezza di Azure per monitorare i server, viene creato automaticamente un tenant di Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="a84dc-144">When you use Azure Security Center to monitor servers, a Microsoft Defender for Endpoint tenant is automatically created.</span></span> <span data-ttu-id="a84dc-145">I dati di Microsoft Defender for Endpoint sono archiviati in Europa per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="a84dc-145">The Microsoft Defender for Endpoint data is stored in Europe by default.</span></span>





## <a name="related-topics"></a><span data-ttu-id="a84dc-146">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="a84dc-146">Related topics</span></span>
- [<span data-ttu-id="a84dc-147">Risolvere i problemi di onboarding di Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="a84dc-147">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
- [<span data-ttu-id="a84dc-148">Esaminare eventi ed errori tramite il Visualizzatore eventi</span><span class="sxs-lookup"><span data-stu-id="a84dc-148">Review events and errors using Event Viewer</span></span>](event-error-codes.md)
