---
title: Registrazione dei dispositivi iOS e Android nell'ambiente di testing di Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/11/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 49c7758a-1c01-4153-9b63-5eae3f6305ce
description: Utilizzare questa guida del laboratorio di testing per registrare i dispositivi nell'ambiente di testing di Microsoft 365 e gestirli in remoto.
ms.openlocfilehash: 0dde7acd10ad78327adb4862346639e05a276b4e
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2019
ms.locfileid: "36981997"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="505db-103">Registrazione dei dispositivi iOS e Android nell'ambiente di testing di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="505db-103">Enroll iOS and Android devices in your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="505db-104">Seguendo le istruzioni riportate in questo articolo, sarà possibile registrare e testare le funzionalità di base per la gestione dei dispositivi mobili per iOS e Android nell'ambiente di testing di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="505db-104">By following the instructions provided in this article, you'll be able to enroll and test basic mobile device management capabilities for iOS and Android devices in your Microsoft 365 Enterprise test environment.</span></span>

![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> <span data-ttu-id="505db-106">Fare clic [qui](https://aka.ms/m365etlgstack) per consultare una mappa di tutti gli articoli relativi alla guida al lab test di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="505db-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="505db-107">Fase 1: creare l'ambiente di testing di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="505db-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="505db-108">Se si desidera registrare i dispositivi iOS e Android in modo semplice con i requisiti minimi, seguire le istruzioni contenute in [Lightweight base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="505db-108">If you just want to enroll iOS and Android devices in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="505db-109">Se si desidera registrare i dispositivi iOS e Android in un'azienda simulata, seguire le istruzioni riportate nell' [autenticazione pass-through](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="505db-109">If you want to enroll iOS and Android devices in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="505db-110">La verifica delle licenze automatizzate e dell'appartenenza ai gruppi non richiede l'ambiente di testing dell'organizzazione simulata, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per una foresta di servizi di dominio Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="505db-110">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="505db-111">Viene fornito come opzione in modo che sia possibile testare la licenza automatizzata e l'appartenenza ai gruppi e sperimentarla in un ambiente che rappresenta un'organizzazione tipica.</span><span class="sxs-lookup"><span data-stu-id="505db-111">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
>  

## <a name="phase-2-enroll-your-ios-and-android-devices"></a><span data-ttu-id="505db-112">Fase 2: registrare i dispositivi iOS e Android</span><span class="sxs-lookup"><span data-stu-id="505db-112">Phase 2: Enroll your iOS and Android devices</span></span>

<span data-ttu-id="505db-113">In primo luogo, utilizzare le istruzioni riportate in [Install and Sign in to the Company Portal app](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) per personalizzare l'app portale aziendale di Microsoft Intune per l'ambiente di testing.</span><span class="sxs-lookup"><span data-stu-id="505db-113">First, use the instructions in [Install and sign in to the Company Portal app](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) to customize the Microsoft Intune Company Portal app for your test environment.</span></span>

<span data-ttu-id="505db-114">Successivamente, seguire le istruzioni riportate in [configurare l'accesso alle risorse aziendali](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) per registrare un dispositivo iOS.</span><span class="sxs-lookup"><span data-stu-id="505db-114">Next, use the instructions in [Set up access to your company resources](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) to enroll an iOS device.</span></span>

<span data-ttu-id="505db-115">Successivamente, seguire le istruzioni riportate in [registrazione del dispositivo Android in Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) per registrare un dispositivo Android.</span><span class="sxs-lookup"><span data-stu-id="505db-115">Next, use the instructions in [Enroll your Android device in Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) to enroll an Android device.</span></span>

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a><span data-ttu-id="505db-116">Fase 3: gestire i dispositivi iOS e Android in remoto</span><span class="sxs-lookup"><span data-stu-id="505db-116">Phase 3: Manage your iOS and Android devices remotely</span></span>

<span data-ttu-id="505db-117">Microsoft Intune fornisce sia la funzionalità di blocco remoto sia quella di reimpostazione del passcode.</span><span class="sxs-lookup"><span data-stu-id="505db-117">Microsoft Intune provides both remote lock and passcode reset capabilities.</span></span> <span data-ttu-id="505db-118">Se un utente perde il proprio dispositivo, è possibile bloccare il dispositivo in modalità remota.</span><span class="sxs-lookup"><span data-stu-id="505db-118">If someone loses their device, you can lock the device remotely.</span></span> <span data-ttu-id="505db-119">Se qualcuno dimentica il proprio codice di accesso, è possibile reimpostarlo in remoto.</span><span class="sxs-lookup"><span data-stu-id="505db-119">If someone forgets their passcode, you can reset it remotely.</span></span>
  
<span data-ttu-id="505db-120">Per bloccare un dispositivo iOS o Android in remoto:</span><span class="sxs-lookup"><span data-stu-id="505db-120">To lock an iOS or Android device remotely:</span></span>

1. <span data-ttu-id="505db-121">Accedere al portale di Azure [https://portal.azure.com](https://portal.azure.com) con le credenziali dell'account di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="505db-121">Sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="505db-122">Fare clic su **tutti i servizi**, digitare **Intune**, quindi fare clic su **Intune**.</span><span class="sxs-lookup"><span data-stu-id="505db-122">Click **All services**, type **Intune**, and then click **Intune**.</span></span>
3. <span data-ttu-id="505db-123">Fare clic su **dispositivi > tutti i dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="505db-123">Click **Devices > All devices**.</span></span>
4. <span data-ttu-id="505db-124">Nell'elenco dei dispositivi, fare clic su un dispositivo iOS o Android, quindi fare clic sull'azione **blocco remoto** .</span><span class="sxs-lookup"><span data-stu-id="505db-124">In the list of devices, click an iOS or Android device, and then click the **Remote lock** action.</span></span>

    
<span data-ttu-id="505db-125">Per reimpostare il passcode in remoto:</span><span class="sxs-lookup"><span data-stu-id="505db-125">To reset the passcode remotely:</span></span>

1. <span data-ttu-id="505db-126">Se necessario, accedere al portale di Azure [https://portal.azure.com](https://portal.azure.com) con le credenziali dell'account di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="505db-126">If needed, sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="505db-127">Fare clic su **tutti i servizi**, digitare **Intune**, quindi fare clic su **Intune**.</span><span class="sxs-lookup"><span data-stu-id="505db-127">Click **All services**, type **Intune**, and then click **Intune**.</span></span>
3. <span data-ttu-id="505db-128">Fare clic su **dispositivi > tutti i dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="505db-128">Click **Devices > All devices**.</span></span>
4. <span data-ttu-id="505db-129">Dall'elenco dei dispositivi gestiti, fare clic su un dispositivo iOS o Android e scegliere **... Altre informazioni**.</span><span class="sxs-lookup"><span data-stu-id="505db-129">From the list of devices you manage, click an iOS or Android device, and choose **...More**.</span></span> <span data-ttu-id="505db-130">Scegliere **quindi l'azione** remota del dispositivo di accesso remoto.</span><span class="sxs-lookup"><span data-stu-id="505db-130">Then choose the **Remove passcode** device remote action.</span></span>

<span data-ttu-id="505db-131">Per ulteriori esperimenti, vedere [available device actions](https://docs.microsoft.com/intune/device-management#available-device-actions).</span><span class="sxs-lookup"><span data-stu-id="505db-131">For additional experimentation, see [Available device actions](https://docs.microsoft.com/intune/device-management#available-device-actions).</span></span>

    
## <a name="next-step"></a><span data-ttu-id="505db-132">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="505db-132">Next step</span></span>

<span data-ttu-id="505db-133">Esplorare le funzionalità e le funzionalità aggiuntive per la [gestione dei dispositivi mobili](m365-enterprise-test-lab-guides.md#mobile-device-management) nell'ambiente di testing.</span><span class="sxs-lookup"><span data-stu-id="505db-133">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="505db-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="505db-134">See Also</span></span>

[<span data-ttu-id="505db-135">Guide al lab di test di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="505db-135">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)
  
[<span data-ttu-id="505db-136">Criteri di conformità dei dispositivi per l'ambiente di testing di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="505db-136">Device compliance policies for your Microsoft 365 Enterprise test environment</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[<span data-ttu-id="505db-137">Distribuzione di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="505db-137">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

