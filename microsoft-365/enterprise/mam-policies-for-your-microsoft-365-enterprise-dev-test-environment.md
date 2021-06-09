---
title: Criteri di conformità dei dispositivi per l'ambiente Microsoft 365 per l'ambiente di testing aziendale
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
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Usa questa guida al laboratorio di testing per aggiungere i criteri di conformità dei dispositivi intune all'ambiente Microsoft 365 per l'ambiente di testing aziendale.
ms.openlocfilehash: d42c9a603ca581941cb5a8f30b9ecd9d6f780759
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367096"
---
# <a name="device-compliance-policies-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="86c75-103">Criteri di conformità dei dispositivi per l'ambiente Microsoft 365 per l'ambiente di testing aziendale</span><span class="sxs-lookup"><span data-stu-id="86c75-103">Device compliance policies for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="86c75-104">*Questa guida al laboratorio di testing può essere utilizzata solo per Microsoft 365 per ambienti di test aziendali.*</span><span class="sxs-lookup"><span data-stu-id="86c75-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="86c75-105">Questo articolo descrive come aggiungere criteri di conformità dei dispositivi Intune per Windows 10 dispositivi e Microsoft 365 Apps for enterprise all'ambiente di testing Microsoft 365 per le aziende.</span><span class="sxs-lookup"><span data-stu-id="86c75-105">This article describes how to add an Intune device compliance policy for Windows 10 devices and Microsoft 365 Apps for enterprise to your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="86c75-106">L'aggiunta di un criterio di conformità dei dispositivi intune prevede due fasi:</span><span class="sxs-lookup"><span data-stu-id="86c75-106">Adding an Intune device compliance policy involves two phases:</span></span>
- [<span data-ttu-id="86c75-107">Fase 1: creare l'ambiente di testing Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="86c75-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="86c75-108">Fase 2: creare criteri di conformità dei dispositivi per Windows 10 dispositivi</span><span class="sxs-lookup"><span data-stu-id="86c75-108">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>](#phase-2-create-a-device-compliance-policy-for-windows-10-devices)

![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="86c75-110">Per una mappa visiva a tutti gli articoli dello stack Microsoft 365 per enterprise Test Lab Guide, passare a [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="86c75-110">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="86c75-111">Fase 1: creare l'ambiente di testing Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="86c75-111">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="86c75-112">Se si desidera configurare i criteri MAM solo in modo leggero con i requisiti minimi, seguire le istruzioni in [Configurazione di base leggera](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="86c75-112">If you want to configure MAM policies in only a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="86c75-113">Se si desidera configurare i criteri MAM in un'azienda simulata, seguire le istruzioni in [Autenticazione pass-through.](pass-through-auth-m365-ent-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="86c75-113">If you want to configure MAM policies in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="86c75-114">Il test delle licenze automatizzate e dell'appartenenza ai gruppi non richiede l'ambiente di testing aziendale simulato, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per una foresta di Servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="86c75-114">Testing automated licensing and group membership doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="86c75-115">Viene fornito qui come opzione in modo da poter testare le licenze automatizzate e l'appartenenza ai gruppi e sperimentarla in un ambiente che rappresenta un'organizzazione tipica.</span><span class="sxs-lookup"><span data-stu-id="86c75-115">It's provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span>
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a><span data-ttu-id="86c75-116">Fase 2: creare criteri di conformità dei dispositivi per Windows 10 dispositivi</span><span class="sxs-lookup"><span data-stu-id="86c75-116">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>

<span data-ttu-id="86c75-117">In questa fase crei un criterio di conformità dei dispositivi per Windows 10 dispositivi.</span><span class="sxs-lookup"><span data-stu-id="86c75-117">In this phase, you create a device compliance policy for Windows 10 devices.</span></span> <span data-ttu-id="86c75-118">Questa fase usa Microsoft Intune e [l'Microsoft Endpoint Manager di](https://go.microsoft.com/fwlink/?linkid=2109431) amministrazione per aggiungere un gruppo e creare un criterio di conformità.</span><span class="sxs-lookup"><span data-stu-id="86c75-118">This phase uses Microsoft Intune and the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) to add a group, and create a compliance policy.</span></span>

1. <span data-ttu-id="86c75-119">Passare [all'Microsoft 365 di amministrazione](https://admin.microsoft.com)e accedere all'Microsoft 365 del laboratorio di testing con l'account di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="86c75-119">Go to the [Microsoft 365 admin center](https://admin.microsoft.com), and sign in to your Microsoft 365 test lab subscription with your global administrator account.</span></span> <span data-ttu-id="86c75-120">Selezionare **l'Endpoint Manager** di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="86c75-120">Select the **Endpoint Manager** admin center.</span></span> <span data-ttu-id="86c75-121">Verrà [Endpoint Manager'interfaccia di amministrazione.](https://go.microsoft.com/fwlink/?linkid=2109431)</span><span class="sxs-lookup"><span data-stu-id="86c75-121">The [Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) opens.</span></span>

    <span data-ttu-id="86c75-122">Se viene visualizzato un **messaggio** simile a Non hai ancora abilitato la gestione dei dispositivi, seleziona Intune come autorità MDM.</span><span class="sxs-lookup"><span data-stu-id="86c75-122">If a message similar to **You haven't enabled device management yet** message is shown, then select Intune as the MDM authority.</span></span> <span data-ttu-id="86c75-123">Per la procedura specifica, vedere [Set the mobile device management authority](/mem/intune/fundamentals/mdm-authority-set).</span><span class="sxs-lookup"><span data-stu-id="86c75-123">For the specific steps, see [Set the mobile device management authority](/mem/intune/fundamentals/mdm-authority-set).</span></span>

    <span data-ttu-id="86c75-124">L Endpoint Manager'interfaccia di amministrazione è incentrata sulla gestione dei dispositivi e sulla gestione delle app.</span><span class="sxs-lookup"><span data-stu-id="86c75-124">The Endpoint Manager admin center focuses on device management and app management.</span></span> <span data-ttu-id="86c75-125">Per una panoramica di questa interfaccia di amministrazione, vedere [Esercitazione: Procedura dettagliata di Intune in Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager).</span><span class="sxs-lookup"><span data-stu-id="86c75-125">For a tour of this admin center, see [Tutorial: Walkthrough Intune in Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager).</span></span>

2. <span data-ttu-id="86c75-126">In **Gruppi** aggiungi un nuovo gruppo **di Microsoft 365** o di sicurezza denominato **Utenti** Windows 10 dispositivi gestiti , con un **tipo di appartenenza** Assegnato. </span><span class="sxs-lookup"><span data-stu-id="86c75-126">In **Groups**, add a new **Microsoft 365** or **Security** group named **Managed Windows 10 device users**, with an **Assigned** membership type.</span></span> <span data-ttu-id="86c75-127">Nei passaggi successivi, i criteri di conformità verranno assegnati a questo gruppo.</span><span class="sxs-lookup"><span data-stu-id="86c75-127">In the next steps, you'll assign your compliance policy to this group.</span></span> 

    <span data-ttu-id="86c75-128">Per la procedura specifica e per informazioni su **Microsoft 365** **o** gruppi di sicurezza, vedere Aggiungere gruppi per organizzare utenti [e dispositivi.](/mem/intune/fundamentals/groups-add)</span><span class="sxs-lookup"><span data-stu-id="86c75-128">For the specific steps, and for information on **Microsoft 365** or **Security** groups, see [Add groups to organize users and devices](/mem/intune/fundamentals/groups-add).</span></span>

3. <span data-ttu-id="86c75-129">In **Dispositivi** creare un criterio Windows 10 di conformità.</span><span class="sxs-lookup"><span data-stu-id="86c75-129">In **Devices**, create a Windows 10 compliance policy.</span></span> <span data-ttu-id="86c75-130">Assegna questo criterio al **gruppo utenti Windows 10 dispositivo gestito** che hai creato.</span><span class="sxs-lookup"><span data-stu-id="86c75-130">Assign this policy to the **Managed Windows 10 device users** group you created.</span></span>

    <span data-ttu-id="86c75-131">Nei criteri è possibile bloccare password semplici, richiedere un firewall, richiedere l'esecuzione del servizio Microsoft Defender Antimalware e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="86c75-131">In your policy, you can block simple passwords, require a firewall, require the Microsoft Defender Antimalware service be running, and more.</span></span> <span data-ttu-id="86c75-132">Un criterio di conformità include in genere le impostazioni di base o il minimo indispensabile che ogni dispositivo deve avere.</span><span class="sxs-lookup"><span data-stu-id="86c75-132">A compliance policy typically includes the base settings, or bare minimum that every device should have.</span></span>

    <span data-ttu-id="86c75-133">Per i passaggi specifici e per informazioni sulle impostazioni di conformità disponibili che è possibile configurare, vedere Usare i criteri di conformità per impostare le regole [per i dispositivi gestiti.](/mem/intune/protect/device-compliance-get-started)</span><span class="sxs-lookup"><span data-stu-id="86c75-133">For the specific steps, and for information on the available compliance settings you can configure, see [Use compliance policies to set rules for devices you manage](/mem/intune/protect/device-compliance-get-started).</span></span>

<span data-ttu-id="86c75-134">Al termine, hai un criterio di conformità dei dispositivi per testare i membri nel gruppo **Utenti Windows 10 dispositivi gestiti.**</span><span class="sxs-lookup"><span data-stu-id="86c75-134">When finished, you have a device compliance policy for testing members in the **Managed Windows 10 device users** group.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="86c75-135">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="86c75-135">Next step</span></span>

<span data-ttu-id="86c75-136">Esplorare le [funzionalità e le funzionalità](m365-enterprise-test-lab-guides.md#mobile-device-management) di gestione dei dispositivi mobili aggiuntive nell'ambiente di testing.</span><span class="sxs-lookup"><span data-stu-id="86c75-136">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="86c75-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="86c75-137">See also</span></span>

<span data-ttu-id="86c75-138">[Microsoft 365 guide ai laboratori di testing aziendali](m365-enterprise-test-lab-guides.md).</span><span class="sxs-lookup"><span data-stu-id="86c75-138">[Microsoft 365 for enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
[<span data-ttu-id="86c75-139">Registrare dispositivi iOS e Android nell'ambiente di testing Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="86c75-139">Enroll iOS and Android devices in your Microsoft 365 for enterprise test environment</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[<span data-ttu-id="86c75-140">Panoramica di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="86c75-140">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="86c75-141">Enterprise Mobility + Security (EMS)</span><span class="sxs-lookup"><span data-stu-id="86c75-141">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
