---
title: Configurare il periodo di timeout del blocco cloud di Microsoft Defender Antivirus
description: Puoi configurare per quanto tempo Microsoft Defender Antivirus blocterà l'esecuzione di un file in attesa di una determinazione del cloud.
keywords: Microsoft Defender Antivirus, antimalware, sicurezza, defender, cloud, timeout, blocco, periodo, secondi
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 372d679f45d6f87392b612f757e6bdf1c6c6b9ad
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765804"
---
# <a name="configure-the-cloud-block-timeout-period"></a><span data-ttu-id="3f073-104">Configurare il periodo di timeout del blocco cloud</span><span class="sxs-lookup"><span data-stu-id="3f073-104">Configure the cloud block timeout period</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="3f073-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="3f073-105">**Applies to:**</span></span>

- [<span data-ttu-id="3f073-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="3f073-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="3f073-107">Quando Microsoft Defender Antivirus rileva un file sospetto, può impedire l'esecuzione del file durante la query al [servizio cloud Microsoft Defender Antivirus.](cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="3f073-107">When Microsoft Defender Antivirus finds a suspicious file, it can prevent the file from running while it queries the [Microsoft Defender Antivirus cloud service](cloud-protection-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="3f073-108">Il periodo predefinito per il blocco [del](configure-block-at-first-sight-microsoft-defender-antivirus.md) file è 10 secondi.</span><span class="sxs-lookup"><span data-stu-id="3f073-108">The default period that the file will be [blocked](configure-block-at-first-sight-microsoft-defender-antivirus.md) is 10 seconds.</span></span> <span data-ttu-id="3f073-109">È possibile specificare un ulteriore periodo di tempo prima che il file possa essere eseguito.</span><span class="sxs-lookup"><span data-stu-id="3f073-109">You can specify an additional period of time to wait before the file is allowed to run.</span></span> <span data-ttu-id="3f073-110">In questo modo è possibile assicurarsi che sia disponibile tempo sufficiente per ricevere una determinazione appropriata dal servizio cloud Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="3f073-110">This can help ensure there is enough time to receive a proper determination from the Microsoft Defender Antivirus cloud service.</span></span>

## <a name="prerequisites-to-use-the-extended-cloud-block-timeout"></a><span data-ttu-id="3f073-111">Prerequisiti per l'utilizzo del timeout del blocco cloud esteso</span><span class="sxs-lookup"><span data-stu-id="3f073-111">Prerequisites to use the extended cloud block timeout</span></span>

<span data-ttu-id="3f073-112">[Il blocco al primo sguardo](configure-block-at-first-sight-microsoft-defender-antivirus.md) e i relativi prerequisiti devono essere abilitati prima di poter specificare un periodo di timeout esteso.</span><span class="sxs-lookup"><span data-stu-id="3f073-112">[Block at first sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) and its prerequisites must be enabled before you can specify an extended timeout period.</span></span>

## <a name="specify-the-extended-timeout-period"></a><span data-ttu-id="3f073-113">Specificare il periodo di timeout esteso</span><span class="sxs-lookup"><span data-stu-id="3f073-113">Specify the extended timeout period</span></span>

<span data-ttu-id="3f073-114">È possibile utilizzare Criteri di gruppo per specificare un timeout esteso per i controlli cloud.</span><span class="sxs-lookup"><span data-stu-id="3f073-114">You can use Group Policy to specify an extended timeout for cloud checks.</span></span>

1. <span data-ttu-id="3f073-115">Nel computer di gestione di Criteri di gruppo, aprire console Gestione Criteri di [gruppo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="3f073-115">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="3f073-116">**Nell'Editor Gestione Criteri di gruppo** passare a Configurazione computer **e** fare clic su **Modelli amministrativi.**</span><span class="sxs-lookup"><span data-stu-id="3f073-116">In the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="3f073-117">Espandere l'albero fino **ai componenti di Windows > Microsoft Defender Antivirus > MpEngine**</span><span class="sxs-lookup"><span data-stu-id="3f073-117">Expand the tree to **Windows components > Microsoft Defender Antivirus > MpEngine**</span></span>

4. <span data-ttu-id="3f073-118">Fare doppio clic **su Configura controllo cloud esteso** e verificare che l'opzione sia abilitata.</span><span class="sxs-lookup"><span data-stu-id="3f073-118">Double-click **Configure extended cloud check** and ensure the option is enabled.</span></span> <span data-ttu-id="3f073-119">Specifica la quantità di tempo aggiuntiva per impedire l'esecuzione del file durante l'attesa di una determinazione del cloud.</span><span class="sxs-lookup"><span data-stu-id="3f073-119">Specify the additional amount of time to prevent the file from running while waiting for a cloud determination.</span></span> <span data-ttu-id="3f073-120">È possibile specificare il tempo aggiuntivo, in secondi, da 1 secondo a 50 secondi.</span><span class="sxs-lookup"><span data-stu-id="3f073-120">You can specify the additional time, in seconds, from 1 second to 50 seconds.</span></span> <span data-ttu-id="3f073-121">Questa ora verrà aggiunta ai 10 secondi predefiniti.</span><span class="sxs-lookup"><span data-stu-id="3f073-121">This time will be added to the default 10 seconds.</span></span>

5. <span data-ttu-id="3f073-122">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="3f073-122">Click **OK**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="3f073-123">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="3f073-123">Related topics</span></span>

- [<span data-ttu-id="3f073-124">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="3f073-124">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="3f073-125">Usare tecnologie antivirus di nuova generazione tramite la protezione basata su cloud</span><span class="sxs-lookup"><span data-stu-id="3f073-125">Use next-generation antivirus technologies through cloud-delivered protection</span></span>](cloud-protection-microsoft-defender-antivirus.md)
- [<span data-ttu-id="3f073-126">Configurare il blocco al primo avvistamento</span><span class="sxs-lookup"><span data-stu-id="3f073-126">Configure block at first sight</span></span>](configure-block-at-first-sight-microsoft-defender-antivirus.md)
- [<span data-ttu-id="3f073-127">Abilitare la protezione basata sul cloud</span><span class="sxs-lookup"><span data-stu-id="3f073-127">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)