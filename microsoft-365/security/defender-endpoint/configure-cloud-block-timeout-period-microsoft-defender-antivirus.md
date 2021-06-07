---
title: Configurare il periodo di timeout Antivirus Microsoft Defender blocco cloud
description: Puoi configurare per quanto tempo Antivirus Microsoft Defender l'esecuzione di un file durante l'attesa di una determinazione del cloud.
keywords: Antivirus Microsoft Defender, antimalware, sicurezza, defender, cloud, timeout, blocco, periodo, secondi
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.date: 06/04/2021
ms.openlocfilehash: dfb75b77119d9550931c3e476323bde67a3b148f
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789088"
---
# <a name="configure-the-cloud-block-timeout-period"></a><span data-ttu-id="a16a0-104">Configurare il periodo di timeout del blocco cloud</span><span class="sxs-lookup"><span data-stu-id="a16a0-104">Configure the cloud block timeout period</span></span>

<span data-ttu-id="a16a0-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="a16a0-105">**Applies to:**</span></span>

- [<span data-ttu-id="a16a0-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="a16a0-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="a16a0-107">Quando Antivirus Microsoft Defender trova un file sospetto, può impedire l'esecuzione del file durante la query al [Antivirus Microsoft Defender cloud.](cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="a16a0-107">When Microsoft Defender Antivirus finds a suspicious file, it can prevent the file from running while it queries the [Microsoft Defender Antivirus cloud service](cloud-protection-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="a16a0-108">Il periodo predefinito di blocco [del](configure-block-at-first-sight-microsoft-defender-antivirus.md) file è 10 secondi.</span><span class="sxs-lookup"><span data-stu-id="a16a0-108">The default period that the file is [blocked](configure-block-at-first-sight-microsoft-defender-antivirus.md) is 10 seconds.</span></span> <span data-ttu-id="a16a0-109">Se si è un amministratore della sicurezza, è possibile specificare più tempo di attesa prima che sia consentita l'esecuzione del file.</span><span class="sxs-lookup"><span data-stu-id="a16a0-109">If you're a security administrator, you can specify more time to wait before the file is allowed to run.</span></span> <span data-ttu-id="a16a0-110">L'estensione del periodo di timeout del blocco cloud può contribuire a garantire che sia disponibile tempo sufficiente per ricevere una corretta determinazione dal servizio cloud Antivirus Microsoft Defender cloud.</span><span class="sxs-lookup"><span data-stu-id="a16a0-110">Extending the cloud block timeout period can help ensure there is enough time to receive a proper determination from the Microsoft Defender Antivirus cloud service.</span></span>

## <a name="prerequisites-to-use-the-extended-cloud-block-timeout"></a><span data-ttu-id="a16a0-111">Prerequisiti per l'utilizzo del timeout del blocco cloud esteso</span><span class="sxs-lookup"><span data-stu-id="a16a0-111">Prerequisites to use the extended cloud block timeout</span></span>

<span data-ttu-id="a16a0-112">[Il blocco al primo sguardo](configure-block-at-first-sight-microsoft-defender-antivirus.md) e i relativi prerequisiti devono essere abilitati prima di poter specificare un periodo di timeout esteso.</span><span class="sxs-lookup"><span data-stu-id="a16a0-112">[Block at first sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) and its prerequisites must be enabled before you can specify an extended timeout period.</span></span>

## <a name="specify-the-extended-timeout-period-using-microsoft-endpoint-manager"></a><span data-ttu-id="a16a0-113">Specificare il periodo di timeout esteso utilizzando Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="a16a0-113">Specify the extended timeout period using Microsoft Endpoint Manager</span></span>

<span data-ttu-id="a16a0-114">È possibile specificare il periodo di timeout del blocco cloud con un criterio di sicurezza [degli endpoint in Microsoft Endpoint Manager](/mem/intune/protect/endpoint-security-policy).</span><span class="sxs-lookup"><span data-stu-id="a16a0-114">You can specify the cloud block timeout period with an [endpoint security policy in Microsoft Endpoint Manager](/mem/intune/protect/endpoint-security-policy).</span></span>

1. <span data-ttu-id="a16a0-115">Accedere all'Endpoint Manager di amministrazione ( [https://endpoint.microsoft.com/](https://endpoint.microsoft.com/) ) e accedere.</span><span class="sxs-lookup"><span data-stu-id="a16a0-115">Go to the Endpoint Manager admin center ([https://endpoint.microsoft.com/](https://endpoint.microsoft.com/)) and sign in.</span></span>

2. <span data-ttu-id="a16a0-116">Selezionare **Endpoint security** e quindi in **Manage** scegliere **Antivirus.**</span><span class="sxs-lookup"><span data-stu-id="a16a0-116">Select **Endpoint security**, and then under **Manage**, choose **Antivirus**.</span></span>

3. <span data-ttu-id="a16a0-117">Selezionare (o creare) un criterio antivirus.</span><span class="sxs-lookup"><span data-stu-id="a16a0-117">Select (or create) an antivirus policy.</span></span>

4. <span data-ttu-id="a16a0-118">Nella sezione **Impostazioni di configurazione** espandere Protezione **cloud**.</span><span class="sxs-lookup"><span data-stu-id="a16a0-118">In the **Configuration settings** section, expand **Cloud protection**.</span></span> <span data-ttu-id="a16a0-119">Quindi, nella casella Timeout esteso **defender cloud in** secondi, specificare il tempo maggiore, in secondi, da 1 secondo a 50 secondi.</span><span class="sxs-lookup"><span data-stu-id="a16a0-119">Then, in the **Defender Cloud Extended Timeout In Seconds** box, specify the more time, in seconds, from 1 second to 50 seconds.</span></span> <span data-ttu-id="a16a0-120">Qualsiasi valore specificato viene aggiunto ai 10 secondi predefiniti.</span><span class="sxs-lookup"><span data-stu-id="a16a0-120">Whatever you specify is added to the default 10 seconds.</span></span>

5. <span data-ttu-id="a16a0-121">(Questo passaggio è facoltativo) Apportare altre modifiche ai criteri antivirus.</span><span class="sxs-lookup"><span data-stu-id="a16a0-121">(This step is optional) Make any other changes to your antivirus policy.</span></span> <span data-ttu-id="a16a0-122">(Serve assistenza?</span><span class="sxs-lookup"><span data-stu-id="a16a0-122">(Need help?</span></span> <span data-ttu-id="a16a0-123">Vedere [Impostazioni per Antivirus Microsoft Defender criteri in Microsoft Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-windows).)</span><span class="sxs-lookup"><span data-stu-id="a16a0-123">See [Settings for Microsoft Defender Antivirus policy in Microsoft Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-windows).)</span></span>

6. <span data-ttu-id="a16a0-124">Scegliere **Avanti** e completare la configurazione dei criteri.</span><span class="sxs-lookup"><span data-stu-id="a16a0-124">Choose **Next**, and finish configuring your policy.</span></span>

## <a name="specify-the-extended-timeout-period-using-group-policy"></a><span data-ttu-id="a16a0-125">Specificare il periodo di timeout esteso tramite Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="a16a0-125">Specify the extended timeout period using Group Policy</span></span>

<span data-ttu-id="a16a0-126">È possibile utilizzare Criteri di gruppo per specificare un timeout esteso per i controlli cloud.</span><span class="sxs-lookup"><span data-stu-id="a16a0-126">You can use Group Policy to specify an extended timeout for cloud checks.</span></span>

1. <span data-ttu-id="a16a0-127">Nel computer di gestione di Criteri di gruppo aprire Console [Gestione Criteri di gruppo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="a16a0-127">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))</span></span>

2. <span data-ttu-id="a16a0-128">Fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e quindi scegliere **Modifica.**</span><span class="sxs-lookup"><span data-stu-id="a16a0-128">Right-click the Group Policy Object you want to configure and then select **Edit**.</span></span>

3. <span data-ttu-id="a16a0-129">**Nell'Editor Gestione Criteri di gruppo** passare a Configurazione **computer** e quindi selezionare **Modelli amministrativi.**</span><span class="sxs-lookup"><span data-stu-id="a16a0-129">In the **Group Policy Management Editor**, go to **Computer configuration**, and then select **Administrative templates**.</span></span>

3. <span data-ttu-id="a16a0-130">Espandere l'albero per **Windows componenti**  >  **Antivirus Microsoft Defender**  >  **MpEngine**.</span><span class="sxs-lookup"><span data-stu-id="a16a0-130">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **MpEngine**.</span></span>

4. <span data-ttu-id="a16a0-131">Fare doppio clic **su Configura controllo cloud esteso** e verificare che l'opzione sia abilitata.</span><span class="sxs-lookup"><span data-stu-id="a16a0-131">Double-click **Configure extended cloud check** and ensure the option is enabled.</span></span> 

   <span data-ttu-id="a16a0-132">Specificare la quantità di tempo aggiuntiva per impedire l'esecuzione del file in attesa di una determinazione del cloud.</span><span class="sxs-lookup"><span data-stu-id="a16a0-132">Specify the extra amount of time to prevent the file from running while waiting for a cloud determination.</span></span> <span data-ttu-id="a16a0-133">Specificare il tempo aggiuntivo, in secondi, da 1 secondo a 50 secondi.</span><span class="sxs-lookup"><span data-stu-id="a16a0-133">Specify the extra time, in seconds, from 1 second to 50 seconds.</span></span> <span data-ttu-id="a16a0-134">Qualsiasi valore specificato viene aggiunto ai 10 secondi predefiniti.</span><span class="sxs-lookup"><span data-stu-id="a16a0-134">Whatever you specify is added to the default 10 seconds.</span></span>

5. <span data-ttu-id="a16a0-135">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="a16a0-135">Select **OK**.</span></span>

 