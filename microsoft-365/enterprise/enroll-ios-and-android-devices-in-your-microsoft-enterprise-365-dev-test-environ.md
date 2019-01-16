---
title: Registrazione dei dispositivi iOS e Android nell'ambiente di testing di Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/11/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 49c7758a-1c01-4153-9b63-5eae3f6305ce
description: Utilizzare questa guida dei laboratori di testing per registrare i dispositivi nell'ambiente di test Microsoft 365 e gestirle in modalità remota.
ms.openlocfilehash: a78db19099ccacd1b2f62e8438d1749f28d22f52
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2019
ms.locfileid: "26868416"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="9d43d-103">Registrazione dei dispositivi iOS e Android nell'ambiente di testing di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="9d43d-103">Enroll iOS and Android devices in your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="9d43d-104">Seguendo le istruzioni fornite in questo articolo, sarà possibile registrare e verificare le funzionalità di gestione di dispositivi mobili base iOS e dei dispositivi Android nell'ambiente di test Microsoft 365 aziendale.</span><span class="sxs-lookup"><span data-stu-id="9d43d-104">By following the instructions provided in this article, you'll be able to enroll and test basic mobile device management capabilities for iOS and Android devices in your Microsoft 365 Enterprise test environment.</span></span>

![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> <span data-ttu-id="9d43d-106">Fare clic [qui](https://aka.ms/m365etlgstack) per consultare una mappa di tutti gli articoli relativi alla guida al lab test di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="9d43d-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="9d43d-107">Fase 1: Preparare l'ambiente di testing Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="9d43d-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="9d43d-108">Se si desidera effettuare la registrazione iOS e dispositivi Android un modo semplice con i requisiti minimi, seguire le istruzioni di [configurazione di base semplificata](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="9d43d-108">If you just want to enroll iOS and Android devices in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="9d43d-109">Se si desidera registrare iOS e dei dispositivi Android in un'azienda simulato, seguire le istruzioni [nell'autenticazione pass-through](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="9d43d-109">If you want to enroll iOS and Android devices in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="9d43d-p101">Test automatizzati licenze e l'appartenenza al gruppo non richiede l'ambiente di testing simulato enterprise, che include una rete intranet simulata connessione a Internet e la sincronizzazione delle directory per una foresta Windows Server Active Directory. Viene fornito qui come un'opzione in modo che sia possibile testare gestione automatica delle licenze e l'appartenenza al gruppo e sperimentare in un ambiente che rappresenta una tipica organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9d43d-p101">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
>  

## <a name="phase-2-enroll-your-ios-and-android-devices"></a><span data-ttu-id="9d43d-112">Fase 2: Registrare i iOS e i dispositivi Android</span><span class="sxs-lookup"><span data-stu-id="9d43d-112">Phase 2: Enroll your iOS and Android devices</span></span>

<span data-ttu-id="9d43d-113">Innanzitutto, utilizzare le istruzioni riportate in [installare ed eseguire l'accesso all'app portale della società](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) per personalizzare le app portale della società Intune Microsoft per l'ambiente di testing.</span><span class="sxs-lookup"><span data-stu-id="9d43d-113">First, use the instructions in [Install and sign in to the Company Portal app](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) to customize the Microsoft Intune Company Portal app for your test environment.</span></span>

<span data-ttu-id="9d43d-114">Successivamente, utilizzare le istruzioni in [configurare l'accesso alle risorse della società](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) per registrare un dispositivo iOS.</span><span class="sxs-lookup"><span data-stu-id="9d43d-114">Next, use the instructions in [Set up access to your company resources](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) to enroll an iOS device.</span></span>

<span data-ttu-id="9d43d-115">Successivamente, utilizzare le istruzioni nella [registrazione dispositivo Android Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) per registrare un dispositivo Android.</span><span class="sxs-lookup"><span data-stu-id="9d43d-115">Next, use the instructions in [Enroll your Android device in Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) to enroll an Android device.</span></span>

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a><span data-ttu-id="9d43d-116">Fase 3: Gestire i iOS e dispositivi Android in remoto</span><span class="sxs-lookup"><span data-stu-id="9d43d-116">Phase 3: Manage your iOS and Android devices remotely</span></span>

<span data-ttu-id="9d43d-p102">Intune Microsoft sono disponibili sia blocco remoto e il passcode reimpostare funzionalità. Se si perde il dispositivo, è possibile bloccare il dispositivo in modalità remota. Se si dimentica il passcode, è possibile reimpostare in remoto.</span><span class="sxs-lookup"><span data-stu-id="9d43d-p102">Microsoft Intune provides both remote lock and passcode reset capabilities. If someone loses their device, you can lock the device remotely. If someone forgets their passcode, you can reset it remotely.</span></span>
  
<span data-ttu-id="9d43d-120">Per bloccare un dispositivo Android o iOS da postazione remota:</span><span class="sxs-lookup"><span data-stu-id="9d43d-120">To lock an iOS or Android device remotely:</span></span>

1. <span data-ttu-id="9d43d-121">Accedere al portale di Azure al [https://portal.azure.com](https://portal.azure.com) con le credenziali dell'account di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="9d43d-121">Sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="9d43d-122">Fare clic su **tutti i servizi**, digitare **Intune**e quindi fare clic su **Intune**.</span><span class="sxs-lookup"><span data-stu-id="9d43d-122">Click **All services**, type **Intune**, and then click **Intune**.</span></span>
3. <span data-ttu-id="9d43d-123">Fare clic su **dispositivi > tutti i dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="9d43d-123">Click **Devices > All devices**.</span></span>
4. <span data-ttu-id="9d43d-124">Nell'elenco dei dispositivi, fare clic su un dispositivo Android o iOS e quindi fare clic sull'azione **Blocca remoto** .</span><span class="sxs-lookup"><span data-stu-id="9d43d-124">In the list of devices, click an iOS or Android device, and then click the **Remote lock** action.</span></span>

    
<span data-ttu-id="9d43d-125">Per reimpostare il passcode in remoto:</span><span class="sxs-lookup"><span data-stu-id="9d43d-125">To reset the passcode remotely:</span></span>

1. <span data-ttu-id="9d43d-126">Se necessario, accedere al portale di Azure al [https://portal.azure.com](https://portal.azure.com) con le credenziali dell'account di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="9d43d-126">If needed, sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="9d43d-127">Fare clic su **tutti i servizi**, digitare **Intune**e quindi fare clic su **Intune**.</span><span class="sxs-lookup"><span data-stu-id="9d43d-127">Click **All services**, type **Intune**, and then click **Intune**.</span></span>
3. <span data-ttu-id="9d43d-128">Fare clic su **dispositivi > tutti i dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="9d43d-128">Click **Devices > All devices**.</span></span>
4. <span data-ttu-id="9d43d-p103">Dall'elenco dei dispositivi di gestione, fare clic su un dispositivo Android o iOS e scegliere **... Ulteriori**. Scegliere quindi l'azione remoto dispositivo **rimuovere passcode** .</span><span class="sxs-lookup"><span data-stu-id="9d43d-p103">From the list of devices you manage, click an iOS or Android device, and choose **...More**. Then choose the **Remove passcode** device remote action.</span></span>

<span data-ttu-id="9d43d-131">Per la sperimentazione aggiuntiva, vedere [azioni disponibili dispositivi](https://docs.microsoft.com/intune/device-management#available-device-actions).</span><span class="sxs-lookup"><span data-stu-id="9d43d-131">For additional experimentation, see [Available device actions](https://docs.microsoft.com/intune/device-management#available-device-actions).</span></span>

    
## <a name="next-step"></a><span data-ttu-id="9d43d-132">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="9d43d-132">Next step</span></span>

<span data-ttu-id="9d43d-133">Esplora le funzionalità aggiuntive [gestione dei dispositivi mobili](m365-enterprise-test-lab-guides.md#mobile-device-management) disponibili nell'ambiente di testing.</span><span class="sxs-lookup"><span data-stu-id="9d43d-133">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="9d43d-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9d43d-134">See Also</span></span>

[<span data-ttu-id="9d43d-135">Guide al lab di test di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="9d43d-135">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)
  
[<span data-ttu-id="9d43d-136">Ambiente di testing di criteri di conformità di dispositivo per la propria azienda 365 Microsoft</span><span class="sxs-lookup"><span data-stu-id="9d43d-136">Device compliance policies for your Microsoft 365 Enterprise test environment</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[<span data-ttu-id="9d43d-137">Distribuzione di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="9d43d-137">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="9d43d-138">Sicurezza (EMS) + mobilità aziendale</span><span class="sxs-lookup"><span data-stu-id="9d43d-138">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
