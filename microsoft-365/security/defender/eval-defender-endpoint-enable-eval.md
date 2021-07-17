---
title: Abilitare la valutazione di Microsoft Defender for Endpoint, attivare la valutazione per MDE
description: Abilitare il laboratorio Microsoft 365 Defender di valutazione o l'ambiente pilota, incluso il controllo dello stato della licenza e gli enpoint di onboarding
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.date: 07/09/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 48186dbfcde897022ac74dfad604c739a45ab68f
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458098"
---
# <a name="enable-microsoft-defender-for-endpoint-evaluation-environment"></a><span data-ttu-id="b4868-103">Abilitare l'ambiente di valutazione di Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="b4868-103">Enable Microsoft Defender for Endpoint evaluation environment</span></span>


<span data-ttu-id="b4868-104">Questo articolo illustra i passaggi per configurare l'ambiente di valutazione per Microsoft Defender for Endpoint usando i dispositivi di produzione.</span><span class="sxs-lookup"><span data-stu-id="b4868-104">This article will guide you through the steps on setting up the evaluation environment for Microsoft Defender for Endpoint using production devices.</span></span> 


>[!TIP]
><span data-ttu-id="b4868-105">Microsoft Defender for Endpoint include anche un laboratorio di valutazione nel prodotto in cui puoi aggiungere dispositivi preconfigurato ed eseguire simulazioni per valutare le funzionalità della piattaforma.</span><span class="sxs-lookup"><span data-stu-id="b4868-105">Microsoft Defender for Endpoint also comes with an in-product evaluation lab where you can add pre-configured devices and run simulations to evaluate the capabilities of the platform.</span></span> <span data-ttu-id="b4868-106">Il laboratorio offre un'esperienza di configurazione semplificata che può aiutare a dimostrare rapidamente il valore di Microsoft Defender per Enpdoint, includendo indicazioni per molte funzionalità come la ricerca avanzata e l'analisi delle minacce.</span><span class="sxs-lookup"><span data-stu-id="b4868-106">The lab comes with a simplified set-up experience that can help quickly demonstrate the value of Microsoft Defender for Enpdoint including guidance for many features like advanced hunting and threat analytics.</span></span> <span data-ttu-id="b4868-107">Per ulteriori informazioni, vedere [Evaluate capabilities.](/defender-endpoint/evaluation-lab.md)</span><span class="sxs-lookup"><span data-stu-id="b4868-107">For more information, see [Evaluate capabilities](/defender-endpoint/evaluation-lab.md).</span></span> <br> <span data-ttu-id="b4868-108">La differenza principale tra le indicazioni fornite in questo articolo e il laboratorio di valutazione è che l'ambiente di valutazione usa dispositivi di produzione, mentre il laboratorio di valutazione usa dispositivi non di produzione.</span><span class="sxs-lookup"><span data-stu-id="b4868-108">The main difference between the guidance provided in this article and the evaluation lab is the evaluation environment uses production devices whereas the evaluation lab uses non-production devices.</span></span> 

<span data-ttu-id="b4868-109">Usa la procedura seguente per abilitare la valutazione per Microsoft Defender per Endpoint.</span><span class="sxs-lookup"><span data-stu-id="b4868-109">Use the following steps to enable the evaluation for Microsoft Defender for Endpoint.</span></span>

![Passaggi per abilitare Microsoft Defender per Endpoint nell'ambiente di valutazione di Microsoft Defender](../../media/defender/m365-defender-endpoint-eval-enable-steps.png)

- [<span data-ttu-id="b4868-111">Passaggio 1. Controllare lo stato della licenza</span><span class="sxs-lookup"><span data-stu-id="b4868-111">Step 1. Check license state</span></span>](#step-1-check-license-state)
- [<span data-ttu-id="b4868-112">Passaggio 2. Endpoint di onboard</span><span class="sxs-lookup"><span data-stu-id="b4868-112">Step 2. Onboard endpoints</span></span>](#step-2-onboard-endpoints-using-any-of-the-supported-management-tools)


## <a name="step-1-check-license-state"></a><span data-ttu-id="b4868-113">Passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="b4868-113">Step 1.</span></span> <span data-ttu-id="b4868-114">Controllare lo stato della licenza</span><span class="sxs-lookup"><span data-stu-id="b4868-114">Check license state</span></span>

<span data-ttu-id="b4868-115">Dovrai prima controllare lo stato della licenza per verificare che sia stato eseguito correttamente il provisioning.</span><span class="sxs-lookup"><span data-stu-id="b4868-115">You'll first need to check the license state to verify that it was properly provisioned.</span></span> <span data-ttu-id="b4868-116">È possibile eseguire questa operazione tramite l'interfaccia di amministrazione o **tramite il Microsoft Azure portale.**</span><span class="sxs-lookup"><span data-stu-id="b4868-116">You can do this through the admin center or through the **Microsoft Azure portal**.</span></span>


1. <span data-ttu-id="b4868-117">Per visualizzare le licenze, passare al **portale di Microsoft Azure** e passare alla Microsoft Azure licenza del [portale.](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products)</span><span class="sxs-lookup"><span data-stu-id="b4868-117">To view your licenses, go to the **Microsoft Azure portal** and navigate to the [Microsoft Azure portal license section](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products).</span></span>

   ![Immagine della pagina Licenze di Azure](../../media/defender/atp-licensing-azure-portal.png)

1. <span data-ttu-id="b4868-119">In alternativa, nell'interfaccia di amministrazione passare a **Fatturazione**  >  **Abbonamenti.**</span><span class="sxs-lookup"><span data-stu-id="b4868-119">Alternately, in the admin center, navigate to **Billing** > **Subscriptions**.</span></span>

    <span data-ttu-id="b4868-120">Sullo schermo verranno visualizzate tutte le licenze di cui è stato eseguito il provisioning e il relativo **stato corrente.**</span><span class="sxs-lookup"><span data-stu-id="b4868-120">On the screen, you'll see all the provisioned licenses and their current **Status**.</span></span>

    ![Immagine delle licenze di fatturazione](../../media/defender/atp-billing-subscriptions.png)

## <a name="step-2-onboard-endpoints-using-any-of-the-supported-management-tools"></a><span data-ttu-id="b4868-122">Passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="b4868-122">Step 2.</span></span> <span data-ttu-id="b4868-123">Onboardare gli endpoint usando uno degli strumenti di gestione supportati</span><span class="sxs-lookup"><span data-stu-id="b4868-123">Onboard endpoints using any of the supported management tools</span></span>

<span data-ttu-id="b4868-124">Dopo aver verificato che lo stato della licenza sia stato effettuato correttamente, puoi avviare l'onboarding dei dispositivi nel servizio.</span><span class="sxs-lookup"><span data-stu-id="b4868-124">After verifying that the license state has been provisioned properly, you can start onboarding devices to the service.</span></span> 

<span data-ttu-id="b4868-125">Ai fini della valutazione di Microsoft Defender for Endpoint, ti consigliamo di scegliere un paio di dispositivi Windows 10 su cui eseguire la valutazione.</span><span class="sxs-lookup"><span data-stu-id="b4868-125">For the purpose of evaluating Microsoft Defender for Endpoint, we recommend choosing a couple of Windows 10 devices to conduct the evaluation on.</span></span> 

<span data-ttu-id="b4868-126">[L'argomento Pianificare](../defender-endpoint/deployment-strategy.md) la distribuzione descrive i passaggi generali da eseguire per distribuire Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="b4868-126">The [Plan deployment](../defender-endpoint/deployment-strategy.md) topic outlines the general steps you need to take to deploy Defender for Endpoint.</span></span>  

<span data-ttu-id="b4868-127">Guarda questo video per una breve panoramica del processo di onboarding e scopri gli strumenti e i metodi disponibili.</span><span class="sxs-lookup"><span data-stu-id="b4868-127">Watch this video for a quick overview of the onboarding process and learn about the available tools and methods.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bGqr]

### <a name="onboarding-tool-options"></a><span data-ttu-id="b4868-128">Opzioni dello strumento di onboarding</span><span class="sxs-lookup"><span data-stu-id="b4868-128">Onboarding tool options</span></span>

<span data-ttu-id="b4868-129">Nella tabella seguente sono elencati gli strumenti disponibili in base all'endpoint da eseguire l'onboard.</span><span class="sxs-lookup"><span data-stu-id="b4868-129">The following table lists the available tools based on the endpoint that you need to onboard.</span></span>

<span data-ttu-id="b4868-130">Endpoint</span><span class="sxs-lookup"><span data-stu-id="b4868-130">Endpoint</span></span> | <span data-ttu-id="b4868-131">Opzioni degli strumenti</span><span class="sxs-lookup"><span data-stu-id="b4868-131">Tool options</span></span>
:---|:---
<span data-ttu-id="b4868-132">**Windows**</span><span class="sxs-lookup"><span data-stu-id="b4868-132">**Windows**</span></span> | <span data-ttu-id="b4868-133">[Script locale (fino a 10 dispositivi),](../defender-endpoint/configure-endpoints-script.md)Criteri di [gruppo,](../defender-endpoint/configure-endpoints-gp.md) [Microsoft Endpoint Manager/ Gestione](../defender-endpoint/configure-endpoints-mdm.md)dispositivi mobili, [Microsoft Endpoint Configuration Manager](../defender-endpoint/configure-endpoints-sccm.md), [script VDI,](../defender-endpoint/configure-endpoints-vdi.md)integrazione [con Azure Defender](../defender-endpoint/configure-server-endpoints.md#integration-with-azure-defender)</span><span class="sxs-lookup"><span data-stu-id="b4868-133">[Local script (up to 10 devices)](../defender-endpoint/configure-endpoints-script.md),  [Group Policy](../defender-endpoint/configure-endpoints-gp.md),  [Microsoft Endpoint Manager/ Mobile Device Manager](../defender-endpoint/configure-endpoints-mdm.md),  [Microsoft Endpoint Configuration Manager](../defender-endpoint/configure-endpoints-sccm.md),  [VDI scripts](../defender-endpoint/configure-endpoints-vdi.md),  [Integration with Azure Defender](../defender-endpoint/configure-server-endpoints.md#integration-with-azure-defender)</span></span>
<span data-ttu-id="b4868-134">**macOS**</span><span class="sxs-lookup"><span data-stu-id="b4868-134">**macOS**</span></span> | <span data-ttu-id="b4868-135">[Script locali](../defender-endpoint/mac-install-manually.md), [Microsoft Endpoint Manager](../defender-endpoint/mac-install-with-intune.md), [JAMF Pro](../defender-endpoint/mac-install-with-jamf.md), Gestione [dispositivi mobili](../defender-endpoint/mac-install-with-other-mdm.md)</span><span class="sxs-lookup"><span data-stu-id="b4868-135">[Local scripts](../defender-endpoint/mac-install-manually.md),  [Microsoft Endpoint Manager](../defender-endpoint/mac-install-with-intune.md),  [JAMF Pro](../defender-endpoint/mac-install-with-jamf.md),  [Mobile Device Management](../defender-endpoint/mac-install-with-other-mdm.md)</span></span>
<span data-ttu-id="b4868-136">**Linux Server**</span><span class="sxs-lookup"><span data-stu-id="b4868-136">**Linux Server**</span></span> | <span data-ttu-id="b4868-137">[Script locale,](../defender-endpoint/linux-install-manually.md)  [Pupazzo,](../defender-endpoint/linux-install-with-puppet.md)  [Ansible](../defender-endpoint/linux-install-with-ansible.md)</span><span class="sxs-lookup"><span data-stu-id="b4868-137">[Local script](../defender-endpoint/linux-install-manually.md),  [Puppet](../defender-endpoint/linux-install-with-puppet.md),  [Ansible](../defender-endpoint/linux-install-with-ansible.md)</span></span>
<span data-ttu-id="b4868-138">**iOS**</span><span class="sxs-lookup"><span data-stu-id="b4868-138">**iOS**</span></span> | [<span data-ttu-id="b4868-139">Basato su app</span><span class="sxs-lookup"><span data-stu-id="b4868-139">App-based</span></span>](../defender-endpoint/ios-install.md)
<span data-ttu-id="b4868-140">**Android**</span><span class="sxs-lookup"><span data-stu-id="b4868-140">**Android**</span></span> | [<span data-ttu-id="b4868-141">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="b4868-141">Microsoft Endpoint Manager</span></span>](../defender-endpoint/android-intune.md)



## <a name="next-step"></a><span data-ttu-id="b4868-142">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="b4868-142">Next step</span></span>
[<span data-ttu-id="b4868-143">Configurare il progetto pilota per Microsoft Defender per Endpoint</span><span class="sxs-lookup"><span data-stu-id="b4868-143">Setup the pilot for Microsoft Defender for Endpoint</span></span>](eval-defender-endpoint-pilot.md)
 
<span data-ttu-id="b4868-144">Torna alla panoramica per [valutare Microsoft Defender for Endpoint](eval-defender-endpoint-overview.md)</span><span class="sxs-lookup"><span data-stu-id="b4868-144">Return to the overview for [Evaluate Microsoft Defender for Endpoint](eval-defender-endpoint-overview.md)</span></span>

<span data-ttu-id="b4868-145">Tornare alla panoramica per [valutare e valutare Microsoft 365 Defender](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="b4868-145">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>