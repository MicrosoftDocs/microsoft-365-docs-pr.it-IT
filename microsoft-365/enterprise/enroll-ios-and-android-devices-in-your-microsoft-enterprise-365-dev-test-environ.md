---
title: Registrazione dei dispositivi iOS e Android nell'ambiente di testing di Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 49c7758a-1c01-4153-9b63-5eae3f6305ce
description: Utilizzare questa guida del laboratorio di testing per registrare i dispositivi nell'ambiente di testing di Microsoft 365 e gestirli in remoto.
ms.openlocfilehash: 98670e64045b36dcdafb46c6ff798b8be7fd6dc1
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2019
ms.locfileid: "40801871"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="1620f-103">Registrazione dei dispositivi iOS e Android nell'ambiente di testing di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="1620f-103">Enroll iOS and Android devices in your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="1620f-104">*Questa guida al lab di test può essere usata solo per ambienti di testing di Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="1620f-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="1620f-105">Seguendo le istruzioni riportate in questo articolo, sarà possibile registrare e testare le funzionalità di base per la gestione dei dispositivi mobili per iOS e Android nell'ambiente di testing di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="1620f-105">By following the instructions provided in this article, you'll be able to enroll and test basic mobile device management capabilities for iOS and Android devices in your Microsoft 365 Enterprise test environment.</span></span>

![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> <span data-ttu-id="1620f-107">Fare clic [qui](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) per consultare una mappa di tutti gli articoli relativi alla guida al lab test di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="1620f-107">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="1620f-108">Fase 1: Creare l'ambiente di testing di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="1620f-108">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="1620f-109">Se si desidera registrare i dispositivi iOS e Android in modo semplice con i requisiti minimi, seguire le istruzioni contenute in [Lightweight base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="1620f-109">If you just want to enroll iOS and Android devices in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="1620f-110">Se si desidera registrare i dispositivi iOS e Android in un'azienda simulata, seguire le istruzioni riportate nell' [autenticazione pass-through](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="1620f-110">If you want to enroll iOS and Android devices in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="1620f-111">La verifica delle licenze automatizzate e dell'appartenenza ai gruppi non richiede l'ambiente di testing dell'organizzazione simulata, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per una foresta di servizi di dominio Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="1620f-111">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="1620f-112">Viene fornito come opzione in modo che sia possibile testare la licenza automatizzata e l'appartenenza ai gruppi e sperimentarla in un ambiente che rappresenta un'organizzazione tipica.</span><span class="sxs-lookup"><span data-stu-id="1620f-112">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
>  

## <a name="phase-2-enroll-your-ios-and-android-devices"></a><span data-ttu-id="1620f-113">Fase 2: registrare i dispositivi iOS e Android</span><span class="sxs-lookup"><span data-stu-id="1620f-113">Phase 2: Enroll your iOS and Android devices</span></span>

<span data-ttu-id="1620f-114">In primo luogo, utilizzare le istruzioni riportate in [Install and Sign in to the Company Portal app](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) per personalizzare l'app portale aziendale di Microsoft Intune per l'ambiente di testing.</span><span class="sxs-lookup"><span data-stu-id="1620f-114">First, use the instructions in [Install and sign in to the Company Portal app](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) to customize the Microsoft Intune Company Portal app for your test environment.</span></span>

<span data-ttu-id="1620f-115">Successivamente, seguire le istruzioni riportate in [configurare l'accesso alle risorse aziendali](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) per registrare un dispositivo iOS.</span><span class="sxs-lookup"><span data-stu-id="1620f-115">Next, use the instructions in [Set up access to your company resources](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) to enroll an iOS device.</span></span>

<span data-ttu-id="1620f-116">Successivamente, seguire le istruzioni riportate in [registrazione del dispositivo Android in Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) per registrare un dispositivo Android.</span><span class="sxs-lookup"><span data-stu-id="1620f-116">Next, use the instructions in [Enroll your Android device in Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) to enroll an Android device.</span></span>

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a><span data-ttu-id="1620f-117">Fase 3: gestire i dispositivi iOS e Android in remoto</span><span class="sxs-lookup"><span data-stu-id="1620f-117">Phase 3: Manage your iOS and Android devices remotely</span></span>

<span data-ttu-id="1620f-118">Microsoft Intune fornisce sia la funzionalità di blocco remoto sia quella di reimpostazione del passcode.</span><span class="sxs-lookup"><span data-stu-id="1620f-118">Microsoft Intune provides both remote lock and passcode reset capabilities.</span></span> <span data-ttu-id="1620f-119">Se un utente perde il proprio dispositivo, è possibile bloccare il dispositivo in modalità remota.</span><span class="sxs-lookup"><span data-stu-id="1620f-119">If someone loses their device, you can lock the device remotely.</span></span> <span data-ttu-id="1620f-120">Se qualcuno dimentica il proprio codice di accesso, è possibile reimpostarlo in remoto.</span><span class="sxs-lookup"><span data-stu-id="1620f-120">If someone forgets their passcode, you can reset it remotely.</span></span>
  
<span data-ttu-id="1620f-121">Per bloccare un dispositivo iOS o Android in remoto:</span><span class="sxs-lookup"><span data-stu-id="1620f-121">To lock an iOS or Android device remotely:</span></span>

1. <span data-ttu-id="1620f-122">Accedere al portale di Azure [https://portal.azure.com](https://portal.azure.com) con le credenziali dell'account di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="1620f-122">Sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="1620f-123">Nella scheda portale di Azure nel browser, digitare **Intune** nella casella di ricerca e quindi fare clic su **Intune**.</span><span class="sxs-lookup"><span data-stu-id="1620f-123">On the Azure portal tab in your browser, type **Intune** in the search box, and then click **Intune**.</span></span>
3. <span data-ttu-id="1620f-124">Fare clic su **dispositivi > tutti i dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="1620f-124">Click **Devices > All devices**.</span></span>
4. <span data-ttu-id="1620f-125">Nell'elenco dei dispositivi, fare clic su un dispositivo iOS o Android, quindi fare clic sull'azione **blocco remoto** .</span><span class="sxs-lookup"><span data-stu-id="1620f-125">In the list of devices, click an iOS or Android device, and then click the **Remote lock** action.</span></span>

    
<span data-ttu-id="1620f-126">Per reimpostare il passcode in remoto:</span><span class="sxs-lookup"><span data-stu-id="1620f-126">To reset the passcode remotely:</span></span>

1. <span data-ttu-id="1620f-127">Se necessario, accedere al portale di Azure [https://portal.azure.com](https://portal.azure.com) con le credenziali dell'account di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="1620f-127">If needed, sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="1620f-128">Nella scheda portale di Azure nel browser, digitare **Intune** nella casella di ricerca e quindi fare clic su **Intune**.</span><span class="sxs-lookup"><span data-stu-id="1620f-128">On the Azure portal tab in your browser, type **Intune** in the search box, and then click **Intune**.</span></span>
3. <span data-ttu-id="1620f-129">Fare clic su **dispositivi > tutti i dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="1620f-129">Click **Devices > All devices**.</span></span>
4. <span data-ttu-id="1620f-130">Dall'elenco dei dispositivi gestiti, fare clic su un dispositivo iOS o Android e scegliere **... Altre informazioni**.</span><span class="sxs-lookup"><span data-stu-id="1620f-130">From the list of devices you manage, click an iOS or Android device, and choose **...More**.</span></span> <span data-ttu-id="1620f-131">Scegliere **quindi l'azione** remota del dispositivo di accesso remoto.</span><span class="sxs-lookup"><span data-stu-id="1620f-131">Then choose the **Remove passcode** device remote action.</span></span>

<span data-ttu-id="1620f-132">Per ulteriori esperimenti, vedere [available device actions](https://docs.microsoft.com/intune/device-management#available-device-actions).</span><span class="sxs-lookup"><span data-stu-id="1620f-132">For additional experimentation, see [Available device actions](https://docs.microsoft.com/intune/device-management#available-device-actions).</span></span>

    
## <a name="next-step"></a><span data-ttu-id="1620f-133">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="1620f-133">Next step</span></span>

<span data-ttu-id="1620f-134">Esplorare le funzionalità e le funzionalità aggiuntive per la [gestione dei dispositivi mobili](m365-enterprise-test-lab-guides.md#mobile-device-management) nell'ambiente di testing.</span><span class="sxs-lookup"><span data-stu-id="1620f-134">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="1620f-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1620f-135">See Also</span></span>

[<span data-ttu-id="1620f-136">Guide al lab di test di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="1620f-136">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)
  
[<span data-ttu-id="1620f-137">Criteri di conformità dei dispositivi per l'ambiente di testing di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="1620f-137">Device compliance policies for your Microsoft 365 Enterprise test environment</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[<span data-ttu-id="1620f-138">Distribuzione di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="1620f-138">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

