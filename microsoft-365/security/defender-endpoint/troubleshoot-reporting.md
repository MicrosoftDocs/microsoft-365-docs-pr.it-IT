---
title: Risolvere i problemi relativi agli strumenti di creazione di report per Microsoft Defender AV
description: Identificare e risolvere i problemi comuni quando si tenta di segnalare lo stato di protezione di Microsoft Defender AV in Conformità degli aggiornamenti
keywords: risolvere i problemi, errore, correggere, conformità degli aggiornamenti, oms, monitorare, report, Microsoft Defender AV
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 3b1a1c807c86aa95148300298484319001b59963
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691593"
---
# <a name="troubleshoot-microsoft-defender-antivirus-reporting-in-update-compliance"></a><span data-ttu-id="a12b4-104">Risolvere i problemi relativi ai report di Microsoft Defender Antivirus in Conformità degli aggiornamenti</span><span class="sxs-lookup"><span data-stu-id="a12b4-104">Troubleshoot Microsoft Defender Antivirus reporting in Update Compliance</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a12b4-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="a12b4-105">**Applies to:**</span></span>

- [<span data-ttu-id="a12b4-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="a12b4-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

> [!IMPORTANT]
> <span data-ttu-id="a12b4-107">Il 31 marzo 2020, la funzionalità di segnalazione di Microsoft Defender Antivirus di Conformità degli aggiornamenti verrà rimossa.</span><span class="sxs-lookup"><span data-stu-id="a12b4-107">On March 31, 2020, the Microsoft Defender Antivirus reporting feature of Update Compliance will be removed.</span></span> <span data-ttu-id="a12b4-108">È possibile continuare a definire ed esaminare i criteri di conformità della sicurezza utilizzando [Microsoft Endpoint Manager,](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager)che consente un controllo più fine sulle funzionalità di sicurezza e gli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="a12b4-108">You can continue to define and review security compliance policies using [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager), which allows finer control over security features and updates.</span></span>

<span data-ttu-id="a12b4-109">Puoi usare Microsoft Defender Antivirus con la conformità degli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="a12b4-109">You can use Microsoft Defender Antivirus with Update Compliance.</span></span> <span data-ttu-id="a12b4-110">Verrà visualizzato lo stato per le licenze E3, B, F1, VL e Pro.</span><span class="sxs-lookup"><span data-stu-id="a12b4-110">You’ll see status for E3, B, F1, VL, and Pro licenses.</span></span> <span data-ttu-id="a12b4-111">Tuttavia, per le licenze E5, è necessario usare [il portale di Microsoft Defender for Endpoint.](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)</span><span class="sxs-lookup"><span data-stu-id="a12b4-111">However, for E5 licenses, you need to use the [Microsoft Defender for Endpoint portal](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span> <span data-ttu-id="a12b4-112">Per altre informazioni sulle opzioni di licenza, vedi [Opzioni di licenza dei prodotti Windows 10.](https://www.microsoft.com/licensing/product-licensing/windows10.aspx)</span><span class="sxs-lookup"><span data-stu-id="a12b4-112">To learn more about licensing options, see [Windows 10 product licensing options](https://www.microsoft.com/licensing/product-licensing/windows10.aspx).</span></span>

<span data-ttu-id="a12b4-113">Quando usi [Conformità aggiornamenti di Windows Analytics](/windows/deployment/update/update-compliance-using#wdav-assessment) per ottenere la segnalazione dello stato di protezione dei dispositivi o degli endpoint nella rete che usano Microsoft Defender Antivirus, potresti riscontrare problemi o problemi.</span><span class="sxs-lookup"><span data-stu-id="a12b4-113">When you use [Windows Analytics Update Compliance to obtain reporting into the protection status of devices or endpoints](/windows/deployment/update/update-compliance-using#wdav-assessment) in your network that are using Microsoft Defender Antivirus, you might encounter problems or issues.</span></span>

<span data-ttu-id="a12b4-114">In genere, gli indicatori più comuni di un problema sono:</span><span class="sxs-lookup"><span data-stu-id="a12b4-114">Typically, the most common indicators of a problem are:</span></span>
- <span data-ttu-id="a12b4-115">Viene visualizzato solo un numero limitato o un sottoinsieme di tutti i dispositivi che si prevedeva di visualizzare</span><span class="sxs-lookup"><span data-stu-id="a12b4-115">You only see a small number or subset of all the devices you were expecting to see</span></span>
- <span data-ttu-id="a12b4-116">Non viene visualizzato alcun dispositivo</span><span class="sxs-lookup"><span data-stu-id="a12b4-116">You do not see any devices at all</span></span>
- <span data-ttu-id="a12b4-117">I report e le informazioni visualizzati sono obsoleti (più vecchi di pochi giorni)</span><span class="sxs-lookup"><span data-stu-id="a12b4-117">The reports and information you do see is outdated (older than a few days)</span></span>

<span data-ttu-id="a12b4-118">Per codici di errore comuni e ID evento correlati al servizio Microsoft Defender Antivirus che non sono correlati alla conformità degli aggiornamenti, vedi [Eventi di Microsoft Defender Antivirus.](troubleshoot-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="a12b4-118">For common error codes and event IDs related to the Microsoft Defender Antivirus service that are not related to Update Compliance, see [Microsoft Defender Antivirus events](troubleshoot-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="a12b4-119">Esistono tre passaggi per la risoluzione di questi problemi:</span><span class="sxs-lookup"><span data-stu-id="a12b4-119">There are three steps to troubleshooting these problems:</span></span>

1. <span data-ttu-id="a12b4-120">Verificare di aver soddisfatto tutti i prerequisiti</span><span class="sxs-lookup"><span data-stu-id="a12b4-120">Confirm that you have met all prerequisites</span></span>
2. <span data-ttu-id="a12b4-121">Verificare la connettività al Windows Defender basato su cloud</span><span class="sxs-lookup"><span data-stu-id="a12b4-121">Check your connectivity to the Windows Defender cloud-based service</span></span>
3. <span data-ttu-id="a12b4-122">Inviare i log di supporto</span><span class="sxs-lookup"><span data-stu-id="a12b4-122">Submit support logs</span></span>

>[!IMPORTANT]
><span data-ttu-id="a12b4-123">In genere sono necessari 3 giorni prima che i dispositivi inizino a comparire in Conformità degli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="a12b4-123">It typically takes 3 days for devices to start appearing in Update Compliance.</span></span>


## <a name="confirm-prerequisites"></a><span data-ttu-id="a12b4-124">Verificare i prerequisiti</span><span class="sxs-lookup"><span data-stu-id="a12b4-124">Confirm prerequisites</span></span>

<span data-ttu-id="a12b4-125">Per fare in modo che i dispositivi siano visualizzati correttamente in Conformità degli aggiornamenti, è necessario soddisfare alcuni prerequisiti sia per il servizio di conformità degli aggiornamenti che per Microsoft Defender Antivirus:</span><span class="sxs-lookup"><span data-stu-id="a12b4-125">In order for devices to properly show up in Update Compliance, you have to meet certain prerequisites for both the Update Compliance service and for Microsoft Defender Antivirus:</span></span>

>[!div class="checklist"]
>- <span data-ttu-id="a12b4-126">Gli endpoint usano Microsoft Defender Antivirus come unica app di protezione antivirus.</span><span class="sxs-lookup"><span data-stu-id="a12b4-126">Endpoints are using Microsoft Defender Antivirus as the sole antivirus protection app.</span></span> <span data-ttu-id="a12b4-127">[L'uso di qualsiasi altra app antivirus causerà](microsoft-defender-antivirus-compatibility.md) la disabilitazione di Microsoft Defender AV e l'endpoint non verrà segnalato in Conformità degli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="a12b4-127">[Using any other antivirus app will cause Microsoft Defender AV to disable itself](microsoft-defender-antivirus-compatibility.md) and the endpoint will not be reported in Update Compliance.</span></span>
> - <span data-ttu-id="a12b4-128">[La protezione consegnata dal cloud è abilitata.](enable-cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="a12b4-128">[Cloud-delivered protection is enabled](enable-cloud-protection-microsoft-defender-antivirus.md).</span></span>
> - <span data-ttu-id="a12b4-129">Gli endpoint possono [connettersi al cloud di Microsoft Defender AV](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)</span><span class="sxs-lookup"><span data-stu-id="a12b4-129">Endpoints can [connect to the Microsoft Defender AV cloud](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)</span></span>
> - <span data-ttu-id="a12b4-130">Se l'endpoint esegue Windows 10 versione 1607 o precedente, i dati di diagnostica di [Windows 10](/windows/configuration/configure-windows-diagnostic-data-in-your-organization#enhanced-level)devono essere impostati sul livello avanzato .</span><span class="sxs-lookup"><span data-stu-id="a12b4-130">If the endpoint is running Windows 10 version 1607 or earlier, [Windows 10 diagnostic data must be set to the Enhanced level](/windows/configuration/configure-windows-diagnostic-data-in-your-organization#enhanced-level).</span></span>
> - <span data-ttu-id="a12b4-131">Sono 3 giorni che tutti i requisiti sono stati soddisfatti</span><span class="sxs-lookup"><span data-stu-id="a12b4-131">It has been 3 days since all requirements have been met</span></span>

<span data-ttu-id="a12b4-132">"È possibile utilizzare Microsoft Defender Antivirus con la conformità degli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="a12b4-132">“You can use Microsoft Defender Antivirus with Update Compliance.</span></span> <span data-ttu-id="a12b4-133">Verrà visualizzato lo stato per le licenze E3, B, F1, VL e Pro.</span><span class="sxs-lookup"><span data-stu-id="a12b4-133">You’ll see status for E3, B, F1, VL, and Pro licenses.</span></span> <span data-ttu-id="a12b4-134">Tuttavia, per le licenze E5, devi usare il portale di Microsoft Defender for Endpoint ( https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) .</span><span class="sxs-lookup"><span data-stu-id="a12b4-134">However, for E5 licenses, you need to use the Microsoft Defender for Endpoint portal (https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span> <span data-ttu-id="a12b4-135">Per altre informazioni sulle opzioni di licenza, vedi Opzioni di licenza dei prodotti Windows 10"</span><span class="sxs-lookup"><span data-stu-id="a12b4-135">To learn more about licensing options, see Windows 10 product licensing options"</span></span>

<span data-ttu-id="a12b4-136">Se tutti i prerequisiti precedenti sono stati soddisfatti, potrebbe essere necessario procedere al passaggio successivo per raccogliere informazioni di diagnostica e inviarle a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a12b4-136">If the above prerequisites have all been met, you might need to proceed to the next step to collect diagnostic information and send it to us.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="a12b4-137">Raccogliere dati di diagnostica per la risoluzione dei problemi di conformità degli aggiornamenti</span><span class="sxs-lookup"><span data-stu-id="a12b4-137">Collect diagnostic data for Update Compliance troubleshooting</span></span>](collect-diagnostic-data.md)  

## <a name="related-topics"></a><span data-ttu-id="a12b4-138">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="a12b4-138">Related topics</span></span>

- [<span data-ttu-id="a12b4-139">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="a12b4-139">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="a12b4-140">Distribuire Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="a12b4-140">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)