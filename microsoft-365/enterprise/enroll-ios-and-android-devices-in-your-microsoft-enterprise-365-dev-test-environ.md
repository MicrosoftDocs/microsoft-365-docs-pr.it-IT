---
title: Registrazione dei dispositivi iOS e Android nell'ambiente di testing di Microsoft 365 per l'organizzazione
f1.keywords:
- NOCSH
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
ms.openlocfilehash: 3736934dbb62e84aad6a91fcd1d65b4a47ef8637
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487697"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="1fd62-103">Registrazione dei dispositivi iOS e Android nell'ambiente di testing di Microsoft 365 per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="1fd62-103">Enroll iOS and Android devices in your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="1fd62-104">*Questa guida del laboratorio di testing può essere utilizzata solo per Microsoft 365 per gli ambienti di testing dell'organizzazione.*</span><span class="sxs-lookup"><span data-stu-id="1fd62-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="1fd62-105">In questo articolo viene descritto come eseguire la registrazione e il testing delle funzionalità di base per la gestione dei dispositivi mobili per iOS e Android nell'ambiente di testing Microsoft 365 for Enterprise.</span><span class="sxs-lookup"><span data-stu-id="1fd62-105">This article describes how to enroll and test basic mobile device management capabilities for iOS and Android devices in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="1fd62-106">La registrazione dei dispositivi iOS e Android nell'ambiente di testing comporta tre fasi:</span><span class="sxs-lookup"><span data-stu-id="1fd62-106">Enrolling iOS and Android devices in your test environment involves three phases:</span></span>
- [<span data-ttu-id="1fd62-107">Fase 1: creare l'ambiente di testing di Microsoft 365 per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="1fd62-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="1fd62-108">Fase 2: registrare i dispositivi iOS e Android</span><span class="sxs-lookup"><span data-stu-id="1fd62-108">Phase 2: Enroll your iOS and Android devices</span></span>](#phase-2-enroll-your-ios-and-android-devices)
- [<span data-ttu-id="1fd62-109">Fase 3: gestire i dispositivi iOS e Android in remoto</span><span class="sxs-lookup"><span data-stu-id="1fd62-109">Phase 3: Manage your iOS and Android devices remotely</span></span>](#phase-3-manage-your-ios-and-android-devices-remotely)

![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> <span data-ttu-id="1fd62-111">Per una mappa visiva su tutti gli articoli della guida del laboratorio di testing di Microsoft 365 for Enterprise, accedere a [microsoft 365 per la guida dello stack del laboratorio di testing dell'organizzazione](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="1fd62-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="1fd62-112">Fase 1: creare l'ambiente di testing di Microsoft 365 per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="1fd62-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="1fd62-113">Se si desidera registrare i dispositivi iOS e Android in modo semplice con i requisiti minimi, seguire le istruzioni in [Lightweight base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="1fd62-113">If you want to enroll iOS and Android devices in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="1fd62-114">Se si desidera registrare i dispositivi iOS e Android in un'azienda simulata, seguire le istruzioni riportate nell' [autenticazione pass-through](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="1fd62-114">If you want to enroll iOS and Android devices in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="1fd62-115">Testing Automatic Licensing and Group Membership non richiede l'ambiente di testing dell'organizzazione simulata, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per una foresta di servizi di dominio Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="1fd62-115">Testing automated licensing and group membership doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="1fd62-116">È disponibile come opzione in modo che sia possibile testare la licenza automatizzata e l'appartenenza ai gruppi ed è possibile sperimentarla in un ambiente che rappresenta un'organizzazione tipica.</span><span class="sxs-lookup"><span data-stu-id="1fd62-116">It's provided here as an option so that you can test automated licensing and group membership, and you can experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-enroll-your-ios-and-android-devices"></a><span data-ttu-id="1fd62-117">Fase 2: registrare i dispositivi iOS e Android</span><span class="sxs-lookup"><span data-stu-id="1fd62-117">Phase 2: Enroll your iOS and Android devices</span></span>

<span data-ttu-id="1fd62-118">In primo luogo, utilizzare le istruzioni riportate in [Install and Sign in to the Company Portal app](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) per personalizzare l'app portale aziendale di Microsoft Intune per l'ambiente di testing.</span><span class="sxs-lookup"><span data-stu-id="1fd62-118">First, use the instructions in [Install and sign in to the Company Portal app](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) to customize the Microsoft Intune Company Portal app for your test environment.</span></span>

<span data-ttu-id="1fd62-119">Successivamente, seguire le istruzioni riportate in [configurare l'accesso alle risorse aziendali](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) per registrare un dispositivo iOS.</span><span class="sxs-lookup"><span data-stu-id="1fd62-119">Next, use the instructions in [Set up access to your company resources](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) to enroll an iOS device.</span></span>

<span data-ttu-id="1fd62-120">Successivamente, seguire le istruzioni riportate in [registrazione del dispositivo Android in Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) per registrare un dispositivo Android.</span><span class="sxs-lookup"><span data-stu-id="1fd62-120">Next, use the instructions in [Enroll your Android device in Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) to enroll an Android device.</span></span>

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a><span data-ttu-id="1fd62-121">Fase 3: gestire i dispositivi iOS e Android in remoto</span><span class="sxs-lookup"><span data-stu-id="1fd62-121">Phase 3: Manage your iOS and Android devices remotely</span></span>

<span data-ttu-id="1fd62-122">Microsoft Intune fornisce sia la funzionalità di blocco remoto sia quella di reimpostazione del passcode.</span><span class="sxs-lookup"><span data-stu-id="1fd62-122">Microsoft Intune provides both remote lock and passcode reset capabilities.</span></span> <span data-ttu-id="1fd62-123">Se un utente perde il dispositivo, è possibile bloccare il dispositivo in remoto.</span><span class="sxs-lookup"><span data-stu-id="1fd62-123">If someone loses their device, you can remotely lock the device.</span></span> <span data-ttu-id="1fd62-124">Se qualcuno dimentica il proprio codice di accesso, è possibile reimpostarlo in remoto.</span><span class="sxs-lookup"><span data-stu-id="1fd62-124">If someone forgets their passcode, you can remotely reset it.</span></span>
  
<span data-ttu-id="1fd62-125">Per bloccare in remoto un dispositivo iOS o Android:</span><span class="sxs-lookup"><span data-stu-id="1fd62-125">To remotely lock an iOS or Android device:</span></span>

1. <span data-ttu-id="1fd62-126">Accedere al portale di Azure [https://portal.azure.com](https://portal.azure.com) con le credenziali dell'account di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="1fd62-126">Sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="1fd62-127">Nel portale di Azure, immettere **Intune** nella casella di ricerca e quindi fare clic su **Intune**.</span><span class="sxs-lookup"><span data-stu-id="1fd62-127">In the Azure portal, enter **Intune** in the search box, and then select **Intune**.</span></span>
3. <span data-ttu-id="1fd62-128">Fare clic su **dispositivi > tutti i dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="1fd62-128">Click **Devices > All devices**.</span></span>
4. <span data-ttu-id="1fd62-129">Nell'elenco dei dispositivi, selezionare un dispositivo iOS o Android, quindi selezionare l'azione **Remote Lock** .</span><span class="sxs-lookup"><span data-stu-id="1fd62-129">In the list of devices, select an iOS or Android device, and then select the **Remote lock** action.</span></span>
    
<span data-ttu-id="1fd62-130">Per reimpostare in remoto il codice di accesso:</span><span class="sxs-lookup"><span data-stu-id="1fd62-130">To remotely reset the passcode:</span></span>

1. <span data-ttu-id="1fd62-131">Se necessario, accedere al portale di Azure [https://portal.azure.com](https://portal.azure.com) con le credenziali dell'account di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="1fd62-131">If needed, sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="1fd62-132">Nel portale di Azure, immettere **Intune** nella casella di ricerca e quindi fare clic su **Intune**.</span><span class="sxs-lookup"><span data-stu-id="1fd62-132">In the Azure portal, enter **Intune** in the search box, and then select **Intune**.</span></span>
3. <span data-ttu-id="1fd62-133">Selezionare **dispositivi**per  >  **tutti i dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="1fd62-133">Select **Devices** > **All devices**.</span></span>
4. <span data-ttu-id="1fd62-134">Nell'elenco dei dispositivi gestiti, selezionare un dispositivo iOS o Android, selezionare \*\*... \*\*E quindi seleziona l'azione remota **Rimuovi** dispositivo di accesso.</span><span class="sxs-lookup"><span data-stu-id="1fd62-134">From the list of devices you manage, select an iOS or Android device, select **...More**, and then select the **Remove passcode** device remote action.</span></span>

<span data-ttu-id="1fd62-135">Per ulteriori esperimenti, vedere [available device actions](https://docs.microsoft.com/intune/device-management#available-device-actions).</span><span class="sxs-lookup"><span data-stu-id="1fd62-135">For additional experimentation, see [Available device actions](https://docs.microsoft.com/intune/device-management#available-device-actions).</span></span>
    
## <a name="next-step"></a><span data-ttu-id="1fd62-136">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="1fd62-136">Next step</span></span>

<span data-ttu-id="1fd62-137">Esplorare le funzionalità e le funzionalità aggiuntive per la [gestione dei dispositivi mobili](m365-enterprise-test-lab-guides.md#mobile-device-management) nell'ambiente di testing.</span><span class="sxs-lookup"><span data-stu-id="1fd62-137">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="1fd62-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1fd62-138">See Also</span></span>

[<span data-ttu-id="1fd62-139">Guide ai lab di test di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="1fd62-139">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)
  
[<span data-ttu-id="1fd62-140">Criteri di conformità dei dispositivi per l'ambiente di testing di Microsoft 365 per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="1fd62-140">Device compliance policies for your Microsoft 365 for enterprise test environment</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[<span data-ttu-id="1fd62-141">Panoramica di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="1fd62-141">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)
