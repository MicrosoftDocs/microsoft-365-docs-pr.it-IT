---
title: Valutazione pilota di Defender for Endpoint
description: Abilita il tuo Microsoft 365 Defender di prova o un ambiente pilota.
keywords: Microsoft 365 Defender prova, provare Microsoft 365 Defender, valutare Microsoft 365 Defender, laboratorio di valutazione Microsoft 365 Defender, pilota di Microsoft 365 Defender, sicurezza informatica, minaccia persistente avanzata, sicurezza aziendale, dispositivi, dispositivo, identità, utenti, dati, applicazioni, incidenti, analisi e correzione automatizzate, ricerca avanzata
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 4345ac0a2758e87160be83c6abd96cdbaa6822dc
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458188"
---
# <a name="pilot-mde-evaluation"></a><span data-ttu-id="ee82a-104">Valutazione MDE pilota</span><span class="sxs-lookup"><span data-stu-id="ee82a-104">Pilot MDE Evaluation</span></span>

>[!NOTE]
><span data-ttu-id="ee82a-105">Allo scopo di guidare l'utente attraverso una distribuzione tipica, questo scenario copre solo l'uso di Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="ee82a-105">For the purpose of guiding you through a typical deployment, this scenario will only cover the use of Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="ee82a-106">Defender for Endpoint supporta l'uso di altri strumenti di onboarding, ma non copre questi scenari nella guida alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="ee82a-106">Defender for Endpoint supports the use of other onboarding tools but won't cover those scenarios in the deployment guide.</span></span> <span data-ttu-id="ee82a-107">Per altre informazioni, vedi [Onboard di dispositivi a Microsoft Defender per Endpoint.](onboard-configure.md)</span><span class="sxs-lookup"><span data-stu-id="ee82a-107">For more information, see [Onboard devices to Microsoft Defender for Endpoint](onboard-configure.md).</span></span>

## <a name="step-1-check-license-state"></a><span data-ttu-id="ee82a-108">Passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="ee82a-108">Step 1.</span></span> <span data-ttu-id="ee82a-109">Controllare lo stato della licenza</span><span class="sxs-lookup"><span data-stu-id="ee82a-109">Check license state</span></span>

<span data-ttu-id="ee82a-110">Il controllo dello stato della licenza e del provisioning corretto può essere eseguito tramite l'interfaccia di amministrazione o tramite il **portale Microsoft Azure .**</span><span class="sxs-lookup"><span data-stu-id="ee82a-110">Checking for the license state and whether it got properly provisioned, can be done through the admin center or through the **Microsoft Azure portal**.</span></span>

1. <span data-ttu-id="ee82a-111">Per visualizzare le licenze, passare al **portale di Microsoft Azure** e passare alla Microsoft Azure licenza del [portale.](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products)</span><span class="sxs-lookup"><span data-stu-id="ee82a-111">To view your licenses, go to the **Microsoft Azure portal** and navigate to the [Microsoft Azure portal license section](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products).</span></span>

   ![Immagine della pagina Licenze di Azure](images/atp-licensing-azure-portal.png)

1. <span data-ttu-id="ee82a-113">In alternativa, nell'interfaccia di amministrazione passare a **Fatturazione**  >  **Abbonamenti.**</span><span class="sxs-lookup"><span data-stu-id="ee82a-113">Alternately, in the admin center, navigate to **Billing** > **Subscriptions**.</span></span>

    <span data-ttu-id="ee82a-114">Sullo schermo verranno visualizzate tutte le licenze di cui è stato eseguito il provisioning e il relativo **stato corrente.**</span><span class="sxs-lookup"><span data-stu-id="ee82a-114">On the screen, you'll see all the provisioned licenses and their current **Status**.</span></span>

    ![Immagine delle licenze di fatturazione](images/atp-billing-subscriptions.png)

## <a name="step-2-onboard-endpoints-using-any-of-the-supported-management-tools"></a><span data-ttu-id="ee82a-116">Passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="ee82a-116">Step 2.</span></span> <span data-ttu-id="ee82a-117">Onboardare gli endpoint usando uno degli strumenti di gestione supportati</span><span class="sxs-lookup"><span data-stu-id="ee82a-117">Onboard endpoints using any of the supported management tools</span></span>

<span data-ttu-id="ee82a-118">[L'argomento Pianificare](deployment-strategy.md) la distribuzione descrive i passaggi generali da eseguire per distribuire Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="ee82a-118">The [Plan deployment](deployment-strategy.md) topic outlines the general steps you need to take to deploy Defender for Endpoint.</span></span>  

<span data-ttu-id="ee82a-119">Guarda questo video per una breve panoramica del processo di onboarding e scopri gli strumenti e i metodi disponibili.</span><span class="sxs-lookup"><span data-stu-id="ee82a-119">Watch this video for a quick overview of the onboarding process and learn about the available tools and methods.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bGqr]

<span data-ttu-id="ee82a-120">Dopo aver identificato l'architettura, è necessario decidere quale metodo di distribuzione utilizzare.</span><span class="sxs-lookup"><span data-stu-id="ee82a-120">After identifying your architecture, you'll need to decide which deployment method to use.</span></span> <span data-ttu-id="ee82a-121">Lo strumento di distribuzione scelto influisce sulla modalità di onboard degli endpoint nel servizio.</span><span class="sxs-lookup"><span data-stu-id="ee82a-121">The deployment tool you choose influences how you onboard endpoints to the service.</span></span>

### <a name="onboarding-tool-options"></a><span data-ttu-id="ee82a-122">Opzioni dello strumento di onboarding</span><span class="sxs-lookup"><span data-stu-id="ee82a-122">Onboarding tool options</span></span>

<span data-ttu-id="ee82a-123">Nella tabella seguente sono elencati gli strumenti disponibili in base all'endpoint da eseguire l'onboard.</span><span class="sxs-lookup"><span data-stu-id="ee82a-123">The following table lists the available tools based on the endpoint that you need to onboard.</span></span>

| <span data-ttu-id="ee82a-124">Endpoint</span><span class="sxs-lookup"><span data-stu-id="ee82a-124">Endpoint</span></span>     | <span data-ttu-id="ee82a-125">Opzioni degli strumenti</span><span class="sxs-lookup"><span data-stu-id="ee82a-125">Tool options</span></span>                       |
|--------------|------------------------------------------|
| <span data-ttu-id="ee82a-126">**Windows**</span><span class="sxs-lookup"><span data-stu-id="ee82a-126">**Windows**</span></span>  |  [<span data-ttu-id="ee82a-127">Script locale (fino a 10 dispositivi)</span><span class="sxs-lookup"><span data-stu-id="ee82a-127">Local script (up to 10 devices)</span></span>](../defender-endpoint/configure-endpoints-script.md) <br> [<span data-ttu-id="ee82a-128">Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="ee82a-128">Group Policy</span></span>](../defender-endpoint/configure-endpoints-gp.md) <br> [<span data-ttu-id="ee82a-129">Microsoft Endpoint Manager/ Gestione dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="ee82a-129">Microsoft Endpoint Manager/ Mobile Device Manager</span></span>](../defender-endpoint/configure-endpoints-mdm.md) <br> [<span data-ttu-id="ee82a-130">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="ee82a-130">Microsoft Endpoint Configuration Manager</span></span>](../defender-endpoint/configure-endpoints-sccm.md) <br> [<span data-ttu-id="ee82a-131">Script VDI</span><span class="sxs-lookup"><span data-stu-id="ee82a-131">VDI scripts</span></span>](../defender-endpoint/configure-endpoints-vdi.md) <br> [<span data-ttu-id="ee82a-132">Integrazione con Azure Defender</span><span class="sxs-lookup"><span data-stu-id="ee82a-132">Integration with Azure Defender</span></span>](../defender-endpoint/configure-server-endpoints.md#integration-with-azure-defender) |
| <span data-ttu-id="ee82a-133">**macOS**</span><span class="sxs-lookup"><span data-stu-id="ee82a-133">**macOS**</span></span>    | [<span data-ttu-id="ee82a-134">Script locali</span><span class="sxs-lookup"><span data-stu-id="ee82a-134">Local scripts</span></span>](../defender-endpoint/mac-install-manually.md) <br> [<span data-ttu-id="ee82a-135">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="ee82a-135">Microsoft Endpoint Manager</span></span>](../defender-endpoint/mac-install-with-intune.md) <br> [<span data-ttu-id="ee82a-136">JAMF Pro</span><span class="sxs-lookup"><span data-stu-id="ee82a-136">JAMF Pro</span></span>](../defender-endpoint/mac-install-with-jamf.md) <br> [<span data-ttu-id="ee82a-137">Gestione di dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="ee82a-137">Mobile Device Management</span></span>](../defender-endpoint/mac-install-with-other-mdm.md) |
| <span data-ttu-id="ee82a-138">**Linux Server**</span><span class="sxs-lookup"><span data-stu-id="ee82a-138">**Linux Server**</span></span> | [<span data-ttu-id="ee82a-139">Script locale</span><span class="sxs-lookup"><span data-stu-id="ee82a-139">Local script</span></span>](../defender-endpoint/linux-install-manually.md) <br> [<span data-ttu-id="ee82a-140">Pupazzo</span><span class="sxs-lookup"><span data-stu-id="ee82a-140">Puppet</span></span>](../defender-endpoint/linux-install-with-puppet.md) <br> [<span data-ttu-id="ee82a-141">Ansible</span><span class="sxs-lookup"><span data-stu-id="ee82a-141">Ansible</span></span>](../defender-endpoint/linux-install-with-ansible.md)|
| <span data-ttu-id="ee82a-142">**iOS**</span><span class="sxs-lookup"><span data-stu-id="ee82a-142">**iOS**</span></span>      | [<span data-ttu-id="ee82a-143">Basato su app</span><span class="sxs-lookup"><span data-stu-id="ee82a-143">App-based</span></span>](../defender-endpoint/ios-install.md)                                |
| <span data-ttu-id="ee82a-144">**Android**</span><span class="sxs-lookup"><span data-stu-id="ee82a-144">**Android**</span></span>  | [<span data-ttu-id="ee82a-145">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="ee82a-145">Microsoft Endpoint Manager</span></span>](../defender-endpoint/android-intune.md)               |
