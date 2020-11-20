---
title: Registrare i dispositivi iOS/iPados e Android nell'ambiente di testing di Microsoft 365 per l'organizzazione
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/19/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 49c7758a-1c01-4153-9b63-5eae3f6305ce
description: Utilizzare questa guida del laboratorio di testing per registrare i dispositivi nell'ambiente di testing di Microsoft 365 e gestirli in remoto.
ms.openlocfilehash: 06f83d1ed61bcc530b6aa974d7730f1aadc0ecbd
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367084"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="3eb11-103">Registrazione dei dispositivi iOS e Android nell'ambiente di testing di Microsoft 365 per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="3eb11-103">Enroll iOS and Android devices in your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="3eb11-104">*Questa guida del laboratorio di testing può essere utilizzata solo per Microsoft 365 per gli ambienti di testing dell'organizzazione.*</span><span class="sxs-lookup"><span data-stu-id="3eb11-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="3eb11-105">In questo articolo viene descritto come eseguire la registrazione e il testing delle funzionalità di base per la gestione dei dispositivi mobili per iOS/iPados e i dispositivi Android nell'ambiente di testing Microsoft 365 for Enterprise.</span><span class="sxs-lookup"><span data-stu-id="3eb11-105">This article describes how to enroll and test basic mobile device management capabilities for iOS/iPadOS and Android devices in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="3eb11-106">La registrazione di dispositivi iOS/iPados e Android nell'ambiente di testing comporta tre fasi:</span><span class="sxs-lookup"><span data-stu-id="3eb11-106">Enrolling iOS/iPadOS and Android devices in your test environment involves three phases:</span></span>
- [<span data-ttu-id="3eb11-107">Fase 1: creare l'ambiente di testing di Microsoft 365 per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="3eb11-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="3eb11-108">Fase 2: registrare i dispositivi iOS/iPados e Android</span><span class="sxs-lookup"><span data-stu-id="3eb11-108">Phase 2: Enroll your iOS/iPadOS and Android devices</span></span>](#phase-2-enroll-your-ios-and-android-devices)
- [<span data-ttu-id="3eb11-109">Fase 3: gestire i dispositivi iOS/iPados e Android in remoto</span><span class="sxs-lookup"><span data-stu-id="3eb11-109">Phase 3: Manage your iOS/iPadOS and Android devices remotely</span></span>](#phase-3-manage-your-ios-and-android-devices-remotely)

![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> <span data-ttu-id="3eb11-111">Per una mappa visiva su tutti gli articoli della guida del laboratorio di testing di Microsoft 365 for Enterprise, accedere a [microsoft 365 per la guida dello stack del laboratorio di testing dell'organizzazione](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="3eb11-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="3eb11-112">Fase 1: creare l'ambiente di testing di Microsoft 365 per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="3eb11-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="3eb11-113">Se si desidera registrare i dispositivi iOS/iPados e Android in modo semplice con i requisiti minimi, seguire le istruzioni contenute in [Lightweight base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="3eb11-113">If you want to enroll iOS/iPadOS and Android devices in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="3eb11-114">Se si desidera registrare i dispositivi iOS/iPados e Android in un'azienda simulata, seguire le istruzioni riportate nell' [autenticazione pass-through](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="3eb11-114">If you want to enroll iOS/iPadOS and Android devices in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="3eb11-115">Testing Automatic Licensing and Group Membership non richiede l'ambiente di testing dell'organizzazione simulata, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per una foresta di servizi di dominio Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="3eb11-115">Testing automated licensing and group membership doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="3eb11-116">È disponibile come opzione in modo che sia possibile testare la licenza automatizzata e l'appartenenza ai gruppi ed è possibile sperimentarla in un ambiente che rappresenta un'organizzazione tipica.</span><span class="sxs-lookup"><span data-stu-id="3eb11-116">It's provided here as an option so that you can test automated licensing and group membership, and you can experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-enroll-your-ios-and-android-devices"></a><span data-ttu-id="3eb11-117">Fase 2: registrare i dispositivi iOS e Android</span><span class="sxs-lookup"><span data-stu-id="3eb11-117">Phase 2: Enroll your iOS and Android devices</span></span>

<span data-ttu-id="3eb11-118">Se si sta prendendo in considerazione una soluzione di gestione dei dispositivi mobili (MDM) per la gestione del dispositivo, è possibile utilizzare Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="3eb11-118">If you're considering a mobile device management (MDM) solution to manage your devices, you can use Microsoft Intune.</span></span> <span data-ttu-id="3eb11-119">Quando si utilizza un provider MDM, tra cui Intune, i dispositivi vengono "registrati".</span><span class="sxs-lookup"><span data-stu-id="3eb11-119">When working with any MDM provider, including Intune, devices are "enrolled".</span></span> <span data-ttu-id="3eb11-120">Quando si effettua la registrazione, ricevono le caratteristiche e le impostazioni configurate.</span><span class="sxs-lookup"><span data-stu-id="3eb11-120">When enrolled, they receive the features and settings you configure.</span></span> 

<span data-ttu-id="3eb11-121">In Intune, esistono alcuni modi per registrare i dispositivi iOS/iPados e Android.</span><span class="sxs-lookup"><span data-stu-id="3eb11-121">In Intune, there are a few ways to enroll your iOS/iPadOS and Android devices.</span></span> <span data-ttu-id="3eb11-122">È possibile scegliere l'opzione di registrazione più adatta per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3eb11-122">You can choose the enrollment option that works best for your organization.</span></span> <span data-ttu-id="3eb11-123">Per ulteriori informazioni e indicazioni, vedere gli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="3eb11-123">For more information and guidance, see the following articles:</span></span>

- [<span data-ttu-id="3eb11-124">Guida alla distribuzione: registrare i dispositivi iOS e iPados in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="3eb11-124">Deployment guide: Enroll iOS and iPadOS devices in Microsoft Intune</span></span>](/mem/intune/fundamentals/deployment-guide-enrollment-ios-ipados)
- [<span data-ttu-id="3eb11-125">Guida alla distribuzione: registrare i dispositivi Android in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="3eb11-125">Deployment guide: Enroll Android devices in Microsoft Intune</span></span>](/mem/intune/fundamentals/deployment-guide-enrollment-android)

<span data-ttu-id="3eb11-126">Se si è pronti per l'utilizzo di Intune per la gestione dei dispositivi e si desidera una guida, è possibile che le informazioni seguenti possano essere utili:</span><span class="sxs-lookup"><span data-stu-id="3eb11-126">If you're ready to use Intune for device management, and want some guidance, then the following information may help:</span></span>

- [<span data-ttu-id="3eb11-127">Panoramica della gestione dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="3eb11-127">Device management overview</span></span>](/mem/intune/fundamentals/what-is-device-management)
- [<span data-ttu-id="3eb11-128">Esercitazione: procedura dettagliata di Intune in Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="3eb11-128">Tutorial: Walkthrough Intune in Microsoft Endpoint Manager</span></span>](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)
- [<span data-ttu-id="3eb11-129">Guida alla distribuzione: installazione o spostamento in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="3eb11-129">Deployment guide: Setup or move to Microsoft Intune</span></span>](/mem/intune/fundamentals/deployment-guide-intune-setup)

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a><span data-ttu-id="3eb11-130">Fase 3: gestire i dispositivi iOS e Android in remoto</span><span class="sxs-lookup"><span data-stu-id="3eb11-130">Phase 3: Manage your iOS and Android devices remotely</span></span>

<span data-ttu-id="3eb11-131">Microsoft Intune offre funzionalità di ripristino di codice e di blocco remoto.</span><span class="sxs-lookup"><span data-stu-id="3eb11-131">Microsoft Intune provides remote lock and passcode reset feature.</span></span> <span data-ttu-id="3eb11-132">Se un utente perde il dispositivo, è possibile bloccare il dispositivo in remoto.</span><span class="sxs-lookup"><span data-stu-id="3eb11-132">If someone loses their device, you can remotely lock the device.</span></span> <span data-ttu-id="3eb11-133">Se qualcuno dimentica il proprio codice di accesso, è possibile reimpostarlo in remoto.</span><span class="sxs-lookup"><span data-stu-id="3eb11-133">If someone forgets their passcode, you can remotely reset it.</span></span>

- <span data-ttu-id="3eb11-134">Per bloccare in remoto un dispositivo iOS/iPados o Android, vedere [Remote Lock Devices with Intune](/mem/intune/remote-actions/device-remote-lock).</span><span class="sxs-lookup"><span data-stu-id="3eb11-134">To remotely lock an iOS/iPadOS or Android device, see [Remotely lock devices with Intune](/mem/intune/remote-actions/device-remote-lock).</span></span>
- <span data-ttu-id="3eb11-135">Per reimpostare in remoto il codice di accesso, vedere [reimpostare o rimuovere un codice di accesso al dispositivo in Intune](/mem/intune/remote-actions/device-passcode-reset).</span><span class="sxs-lookup"><span data-stu-id="3eb11-135">To remotely reset the passcode, see [Reset or remove a device passcode in Intune](/mem/intune/remote-actions/device-passcode-reset).</span></span>

<span data-ttu-id="3eb11-136">Per le attività aggiuntive che è possibile eseguire in remoto, vedere [available device actions](/mem/intune/remote-actions/device-management#available-device-actions).</span><span class="sxs-lookup"><span data-stu-id="3eb11-136">For additional tasks you can run remotely, see [available device actions](/mem/intune/remote-actions/device-management#available-device-actions).</span></span>
    
## <a name="next-step"></a><span data-ttu-id="3eb11-137">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="3eb11-137">Next step</span></span>

<span data-ttu-id="3eb11-138">Esplorare le funzionalità e le funzionalità aggiuntive per la [gestione dei dispositivi mobili](m365-enterprise-test-lab-guides.md#mobile-device-management) nell'ambiente di testing.</span><span class="sxs-lookup"><span data-stu-id="3eb11-138">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="3eb11-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3eb11-139">See Also</span></span>

[<span data-ttu-id="3eb11-140">Guide ai lab di test di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="3eb11-140">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)
  
[<span data-ttu-id="3eb11-141">Criteri di conformità dei dispositivi per l'ambiente di testing di Microsoft 365 per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="3eb11-141">Device compliance policies for your Microsoft 365 for enterprise test environment</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[<span data-ttu-id="3eb11-142">Panoramica di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="3eb11-142">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)
