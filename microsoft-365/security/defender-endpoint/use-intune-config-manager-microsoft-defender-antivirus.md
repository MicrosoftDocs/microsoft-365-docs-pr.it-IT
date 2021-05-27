---
title: Configurare Antivirus Microsoft Defender tramite Microsoft Endpoint Manager
description: Usare Microsoft Endpoint Manager e Microsoft Intune per configurare Microsoft Defender AV e Endpoint Protection
keywords: scep, intune, endpoint protection, configurazione
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/24/2021
ms.reviewer: phuijbr, oogunrinde
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.openlocfilehash: ab77f3ab5ac9385d1ce049061730d2192e3bcb0c
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683752"
---
# <a name="use-microsoft-endpoint-manager-to-configure-and-manage-microsoft-defender-antivirus"></a><span data-ttu-id="0adc1-104">Utilizzare Microsoft Endpoint Manager per configurare e gestire le Antivirus Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="0adc1-104">Use Microsoft Endpoint Manager to configure and manage Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="0adc1-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="0adc1-105">**Applies to:**</span></span>

- [<span data-ttu-id="0adc1-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="0adc1-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="0adc1-107">È possibile utilizzare [Microsoft Endpoint Manager](/mem/endpoint-manager-overview) per configurare Antivirus Microsoft Defender analisi.</span><span class="sxs-lookup"><span data-stu-id="0adc1-107">You can use [Microsoft Endpoint Manager](/mem/endpoint-manager-overview) to configure Microsoft Defender Antivirus scans.</span></span> <span data-ttu-id="0adc1-108">[Microsoft Intune](/mem/intune/fundamentals/what-is-intune) e [Configuration Manager](/mem/configmgr/core/understand/introduction) fanno ora parte di Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="0adc1-108">[Microsoft Intune](/mem/intune/fundamentals/what-is-intune) and [Configuration Manager](/mem/configmgr/core/understand/introduction) are now part of Endpoint Manager.</span></span>  

## <a name="configure-microsoft-defender-antivirus-scans-in-endpoint-manager"></a><span data-ttu-id="0adc1-109">Configurare Antivirus Microsoft Defender analisi in Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="0adc1-109">Configure Microsoft Defender Antivirus scans in Endpoint Manager</span></span>

1. <span data-ttu-id="0adc1-110">Accedere all'Microsoft Endpoint Manager di amministrazione ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) e accedere.</span><span class="sxs-lookup"><span data-stu-id="0adc1-110">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), and sign in.</span></span>

2. <span data-ttu-id="0adc1-111">Passare a **Endpoint Security**.</span><span class="sxs-lookup"><span data-stu-id="0adc1-111">Navigate to **Endpoint Security**.</span></span>

3. <span data-ttu-id="0adc1-112">In **Gestisci** scegliere **Antivirus.**</span><span class="sxs-lookup"><span data-stu-id="0adc1-112">Under **Manage**, choose **Antivirus**.</span></span>

4. <span data-ttu-id="0adc1-113">Selezionare i criteri Antivirus Microsoft Defender criteri.</span><span class="sxs-lookup"><span data-stu-id="0adc1-113">Select your Microsoft Defender Antivirus policy.</span></span> 

5. <span data-ttu-id="0adc1-114">In **Gestisci** scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="0adc1-114">Under **Manage**, choose **Properties**.</span></span>

6. <span data-ttu-id="0adc1-115">Accanto a **Impostazioni di configurazione** scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="0adc1-115">Next to **Configuration settings**, choose **Edit**.</span></span>

7. <span data-ttu-id="0adc1-116">Espandere la **sezione Analisi** ed esaminare o modificare le impostazioni di analisi.</span><span class="sxs-lookup"><span data-stu-id="0adc1-116">Expand the **Scan** section, and review or edit your scanning settings.</span></span>

8. <span data-ttu-id="0adc1-117">Scegliere **Revisione e salvataggio**</span><span class="sxs-lookup"><span data-stu-id="0adc1-117">Choose **Review + save**</span></span>


> [!TIP]
> <span data-ttu-id="0adc1-118">Hai bisogno di assistenza?</span><span class="sxs-lookup"><span data-stu-id="0adc1-118">Need help?</span></span> <span data-ttu-id="0adc1-119">Vedi [Gestire la sicurezza degli endpoint in Microsoft Intune](/mem/intune/protect/endpoint-security).</span><span class="sxs-lookup"><span data-stu-id="0adc1-119">See [Manage endpoint security in Microsoft Intune](/mem/intune/protect/endpoint-security).</span></span>


## <a name="related-articles"></a><span data-ttu-id="0adc1-120">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="0adc1-120">Related articles</span></span>

- [<span data-ttu-id="0adc1-121">Articoli di riferimento per gli strumenti di gestione e configurazione</span><span class="sxs-lookup"><span data-stu-id="0adc1-121">Reference articles for management and configuration tools</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="0adc1-122">Antivirus Microsoft Defender in Windows 10</span><span class="sxs-lookup"><span data-stu-id="0adc1-122">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)