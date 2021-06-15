---
title: Risolvere i problemi relativi agli strumenti di creazione di report per Microsoft Defender AV
description: Identificare e risolvere i problemi comuni quando si tenta di segnalare lo stato di protezione di Microsoft Defender AV in Conformità degli aggiornamenti
keywords: risolvere i problemi, errore, correggere, conformità degli aggiornamenti, oms, monitorare, report, Microsoft Defender AV
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 405955de63de9f84a783ca1b8c0348c3935440cd
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926176"
---
# <a name="troubleshoot-microsoft-defender-antivirus-reporting-in-update-compliance"></a><span data-ttu-id="181aa-104">Risolvere i problemi relativi alla creazione di report di Microsoft Defender Antivirus nella procedura di aggiornamento per la conformità</span><span class="sxs-lookup"><span data-stu-id="181aa-104">Troubleshoot Microsoft Defender Antivirus reporting in Update Compliance</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="181aa-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="181aa-105">**Applies to:**</span></span>

- [<span data-ttu-id="181aa-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="181aa-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

> [!IMPORTANT]
> <span data-ttu-id="181aa-107">Il 31 marzo 2020 verrà rimossa la Antivirus Microsoft Defender di report di Conformità degli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="181aa-107">On March 31, 2020, the Microsoft Defender Antivirus reporting feature of Update Compliance will be removed.</span></span> <span data-ttu-id="181aa-108">È possibile continuare a definire ed esaminare i criteri di conformità della sicurezza [usando Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager), che consente un controllo più fine sulle funzionalità e gli aggiornamenti di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="181aa-108">You can continue to define and review security compliance policies using [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager), which allows finer control over security features and updates.</span></span>

<span data-ttu-id="181aa-109">È possibile utilizzare Antivirus Microsoft Defender conformità degli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="181aa-109">You can use Microsoft Defender Antivirus with Update Compliance.</span></span> <span data-ttu-id="181aa-110">Vedrai lo stato per le licenze E3, B, F1, VL e Pro licenze.</span><span class="sxs-lookup"><span data-stu-id="181aa-110">You’ll see status for E3, B, F1, VL, and Pro licenses.</span></span> <span data-ttu-id="181aa-111">Tuttavia, per le licenze E5, è necessario usare [il portale di Microsoft Defender for Endpoint.](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)</span><span class="sxs-lookup"><span data-stu-id="181aa-111">However, for E5 licenses, you need to use the [Microsoft Defender for Endpoint portal](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span> <span data-ttu-id="181aa-112">Per ulteriori informazioni sulle opzioni di licenza, vedere [Windows 10 opzioni di licenza del prodotto.](https://www.microsoft.com/licensing/product-licensing/windows10.aspx)</span><span class="sxs-lookup"><span data-stu-id="181aa-112">To learn more about licensing options, see [Windows 10 product licensing options](https://www.microsoft.com/licensing/product-licensing/windows10.aspx).</span></span>

<span data-ttu-id="181aa-113">Quando si usa Windows conformità agli aggiornamenti di Windows Analytics per ottenere la segnalazione dello stato di protezione dei dispositivi o [degli endpoint](/windows/deployment/update/update-compliance-using#wdav-assessment) della rete che usano Antivirus Microsoft Defender, è possibile che si verifichino problemi o problemi.</span><span class="sxs-lookup"><span data-stu-id="181aa-113">When you use [Windows Analytics Update Compliance to obtain reporting into the protection status of devices or endpoints](/windows/deployment/update/update-compliance-using#wdav-assessment) in your network that are using Microsoft Defender Antivirus, you might encounter problems or issues.</span></span>

<span data-ttu-id="181aa-114">In genere, gli indicatori più comuni di un problema sono:</span><span class="sxs-lookup"><span data-stu-id="181aa-114">Typically, the most common indicators of a problem are:</span></span>
- <span data-ttu-id="181aa-115">Viene visualizzato solo un numero limitato o un sottoinsieme di tutti i dispositivi che si prevedeva di visualizzare</span><span class="sxs-lookup"><span data-stu-id="181aa-115">You only see a small number or subset of all the devices you were expecting to see</span></span>
- <span data-ttu-id="181aa-116">Non viene visualizzato alcun dispositivo</span><span class="sxs-lookup"><span data-stu-id="181aa-116">You do not see any devices at all</span></span>
- <span data-ttu-id="181aa-117">I report e le informazioni visualizzati sono obsoleti (più vecchi di pochi giorni)</span><span class="sxs-lookup"><span data-stu-id="181aa-117">The reports and information you do see is outdated (older than a few days)</span></span>

<span data-ttu-id="181aa-118">Per codici di errore comuni e ID evento correlati al servizio Antivirus Microsoft Defender che non sono correlati alla conformità degli aggiornamenti, vedere Antivirus Microsoft Defender [eventi](troubleshoot-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="181aa-118">For common error codes and event IDs related to the Microsoft Defender Antivirus service that are not related to Update Compliance, see [Microsoft Defender Antivirus events](troubleshoot-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="181aa-119">Esistono tre passaggi per la risoluzione di questi problemi:</span><span class="sxs-lookup"><span data-stu-id="181aa-119">There are three steps to troubleshooting these problems:</span></span>

1. <span data-ttu-id="181aa-120">Verificare di aver soddisfatto tutti i prerequisiti</span><span class="sxs-lookup"><span data-stu-id="181aa-120">Confirm that you have met all prerequisites</span></span>
2. <span data-ttu-id="181aa-121">Verificare la connettività al Windows Defender basato su cloud</span><span class="sxs-lookup"><span data-stu-id="181aa-121">Check your connectivity to the Windows Defender cloud-based service</span></span>
3. <span data-ttu-id="181aa-122">Inviare i log di supporto</span><span class="sxs-lookup"><span data-stu-id="181aa-122">Submit support logs</span></span>

>[!IMPORTANT]
><span data-ttu-id="181aa-123">In genere sono necessari 3 giorni prima che i dispositivi inizino a comparire in Conformità degli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="181aa-123">It typically takes 3 days for devices to start appearing in Update Compliance.</span></span>


## <a name="confirm-prerequisites"></a><span data-ttu-id="181aa-124">Verificare i prerequisiti</span><span class="sxs-lookup"><span data-stu-id="181aa-124">Confirm prerequisites</span></span>

<span data-ttu-id="181aa-125">Per fare in modo che i dispositivi siano visualizzati correttamente in Conformità degli aggiornamenti, è necessario soddisfare alcuni prerequisiti sia per il servizio di conformità degli aggiornamenti che per Antivirus Microsoft Defender:</span><span class="sxs-lookup"><span data-stu-id="181aa-125">In order for devices to properly show up in Update Compliance, you have to meet certain prerequisites for both the Update Compliance service and for Microsoft Defender Antivirus:</span></span>

>[!div class="checklist"]
>- <span data-ttu-id="181aa-126">Gli endpoint usano il Antivirus Microsoft Defender come unica app di protezione antivirus.</span><span class="sxs-lookup"><span data-stu-id="181aa-126">Endpoints are using Microsoft Defender Antivirus as the sole antivirus protection app.</span></span> <span data-ttu-id="181aa-127">[L'uso di qualsiasi altra app antivirus causerà](microsoft-defender-antivirus-compatibility.md) la disabilitazione di Microsoft Defender AV e l'endpoint non verrà segnalato in Conformità degli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="181aa-127">[Using any other antivirus app will cause Microsoft Defender AV to disable itself](microsoft-defender-antivirus-compatibility.md) and the endpoint will not be reported in Update Compliance.</span></span>
> - <span data-ttu-id="181aa-128">[La protezione consegnata dal cloud è abilitata.](enable-cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="181aa-128">[Cloud-delivered protection is enabled](enable-cloud-protection-microsoft-defender-antivirus.md).</span></span>
> - <span data-ttu-id="181aa-129">Gli endpoint possono [connettersi al cloud di Microsoft Defender AV](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)</span><span class="sxs-lookup"><span data-stu-id="181aa-129">Endpoints can [connect to the Microsoft Defender AV cloud](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)</span></span>
> - <span data-ttu-id="181aa-130">Se l'endpoint è Windows 10 versione 1607 o precedente, Windows 10 dati di diagnostica devono essere impostati [sul livello avanzato](/windows/configuration/configure-windows-diagnostic-data-in-your-organization#enhanced-level).</span><span class="sxs-lookup"><span data-stu-id="181aa-130">If the endpoint is running Windows 10 version 1607 or earlier, [Windows 10 diagnostic data must be set to the Enhanced level](/windows/configuration/configure-windows-diagnostic-data-in-your-organization#enhanced-level).</span></span>
> - <span data-ttu-id="181aa-131">Sono 3 giorni che tutti i requisiti sono stati soddisfatti</span><span class="sxs-lookup"><span data-stu-id="181aa-131">It has been 3 days since all requirements have been met</span></span>

<span data-ttu-id="181aa-132">"È possibile utilizzare Antivirus Microsoft Defender conformità degli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="181aa-132">“You can use Microsoft Defender Antivirus with Update Compliance.</span></span> <span data-ttu-id="181aa-133">Vedrai lo stato per le licenze E3, B, F1, VL e Pro licenze.</span><span class="sxs-lookup"><span data-stu-id="181aa-133">You’ll see status for E3, B, F1, VL, and Pro licenses.</span></span> <span data-ttu-id="181aa-134">Tuttavia, per le licenze E5, devi usare il portale di Microsoft Defender for Endpoint (/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span><span class="sxs-lookup"><span data-stu-id="181aa-134">However, for E5 licenses, you need to use the Microsoft Defender for Endpoint portal (/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span> <span data-ttu-id="181aa-135">Per ulteriori informazioni sulle opzioni di licenza, vedere Windows 10 opzioni di licenza del prodotto"</span><span class="sxs-lookup"><span data-stu-id="181aa-135">To learn more about licensing options, see Windows 10 product licensing options"</span></span>

<span data-ttu-id="181aa-136">Se tutti i prerequisiti precedenti sono stati soddisfatti, potrebbe essere necessario procedere al passaggio successivo per raccogliere informazioni di diagnostica e inviarle a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="181aa-136">If the above prerequisites have all been met, you might need to proceed to the next step to collect diagnostic information and send it to us.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="181aa-137">Raccogliere dati di diagnostica per la risoluzione dei problemi di conformità degli aggiornamenti</span><span class="sxs-lookup"><span data-stu-id="181aa-137">Collect diagnostic data for Update Compliance troubleshooting</span></span>](collect-diagnostic-data.md)  

## <a name="related-topics"></a><span data-ttu-id="181aa-138">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="181aa-138">Related topics</span></span>

- [<span data-ttu-id="181aa-139">Antivirus Microsoft Defender in Windows 10</span><span class="sxs-lookup"><span data-stu-id="181aa-139">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="181aa-140">Distribuire Antivirus Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="181aa-140">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)