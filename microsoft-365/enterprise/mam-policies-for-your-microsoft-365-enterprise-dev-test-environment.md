---
title: Criteri di conformità dei dispositivi per l'ambiente di testing di Microsoft 365 per l'organizzazione
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
description: Utilizzare questa guida del laboratorio di testing per aggiungere criteri di conformità dei dispositivi di Intune all'ambiente di testing di Microsoft 365 per l'organizzazione.
ms.openlocfilehash: d42c9a603ca581941cb5a8f30b9ecd9d6f780759
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367096"
---
# <a name="device-compliance-policies-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="77bdb-103">Criteri di conformità dei dispositivi per l'ambiente di testing di Microsoft 365 per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="77bdb-103">Device compliance policies for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="77bdb-104">*Questa guida del laboratorio di testing può essere utilizzata solo per Microsoft 365 per gli ambienti di testing dell'organizzazione.*</span><span class="sxs-lookup"><span data-stu-id="77bdb-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="77bdb-105">In questo articolo viene descritto come aggiungere un criterio di conformità del dispositivo Intune per i dispositivi Windows 10 e le app Microsoft 365 per Enterprise all'ambiente di testing di Microsoft 365 per Enterprise.</span><span class="sxs-lookup"><span data-stu-id="77bdb-105">This article describes how to add an Intune device compliance policy for Windows 10 devices and Microsoft 365 Apps for enterprise to your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="77bdb-106">L'aggiunta di un criterio di conformità del dispositivo di Intune implica due fasi:</span><span class="sxs-lookup"><span data-stu-id="77bdb-106">Adding an Intune device compliance policy involves two phases:</span></span>
- [<span data-ttu-id="77bdb-107">Fase 1: creare l'ambiente di testing di Microsoft 365 per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="77bdb-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="77bdb-108">Fase 2: creare un criterio di conformità del dispositivo per i dispositivi Windows 10</span><span class="sxs-lookup"><span data-stu-id="77bdb-108">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>](#phase-2-create-a-device-compliance-policy-for-windows-10-devices)

![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="77bdb-110">Per una mappa visiva su tutti gli articoli della guida del laboratorio di testing di Microsoft 365 for Enterprise, accedere a [microsoft 365 per la guida dello stack del laboratorio di testing dell'organizzazione](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="77bdb-110">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="77bdb-111">Fase 1: creare l'ambiente di testing di Microsoft 365 per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="77bdb-111">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="77bdb-112">Se si desidera configurare i criteri MAM solo in modo semplice con i requisiti minimi, seguire le istruzioni in [Lightweight base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="77bdb-112">If you want to configure MAM policies in only a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="77bdb-113">Se si desidera configurare i criteri MAM in un'azienda simulata, seguire le istruzioni riportate nell' [autenticazione pass-through](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="77bdb-113">If you want to configure MAM policies in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="77bdb-114">Testing Automatic Licensing and Group Membership non richiede l'ambiente di testing dell'organizzazione simulata, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per una foresta di servizi di dominio Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="77bdb-114">Testing automated licensing and group membership doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="77bdb-115">È disponibile come opzione in modo che sia possibile testare la licenza automatizzata e l'appartenenza ai gruppi e sperimentarla in un ambiente che rappresenta un'organizzazione tipica.</span><span class="sxs-lookup"><span data-stu-id="77bdb-115">It's provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span>
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a><span data-ttu-id="77bdb-116">Fase 2: creare un criterio di conformità del dispositivo per i dispositivi Windows 10</span><span class="sxs-lookup"><span data-stu-id="77bdb-116">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>

<span data-ttu-id="77bdb-117">In questa fase, è possibile creare un criterio di conformità del dispositivo per i dispositivi Windows 10.</span><span class="sxs-lookup"><span data-stu-id="77bdb-117">In this phase, you create a device compliance policy for Windows 10 devices.</span></span> <span data-ttu-id="77bdb-118">In questa fase vengono utilizzati Microsoft Intune e l'interfaccia di [amministrazione di Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) per aggiungere un gruppo e creare un criterio di conformità.</span><span class="sxs-lookup"><span data-stu-id="77bdb-118">This phase uses Microsoft Intune and the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) to add a group, and create a compliance policy.</span></span>

1. <span data-ttu-id="77bdb-119">Accedere all'interfaccia di [amministrazione di microsoft 365](https://admin.microsoft.com)e accedere all'abbonamento al laboratorio di testing di Microsoft 365 con l'account di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="77bdb-119">Go to the [Microsoft 365 admin center](https://admin.microsoft.com), and sign in to your Microsoft 365 test lab subscription with your global administrator account.</span></span> <span data-ttu-id="77bdb-120">Selezionare l'interfaccia di amministrazione di **Endpoint Manager** .</span><span class="sxs-lookup"><span data-stu-id="77bdb-120">Select the **Endpoint Manager** admin center.</span></span> <span data-ttu-id="77bdb-121">Verrà aperto l'interfaccia di [amministrazione di Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) .</span><span class="sxs-lookup"><span data-stu-id="77bdb-121">The [Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) opens.</span></span>

    <span data-ttu-id="77bdb-122">Se un messaggio simile a non è stato abilitato per la **gestione dei dispositivi** , viene visualizzato il messaggio, quindi selezionare Intune come autorità MDM.</span><span class="sxs-lookup"><span data-stu-id="77bdb-122">If a message similar to **You haven't enabled device management yet** message is shown, then select Intune as the MDM authority.</span></span> <span data-ttu-id="77bdb-123">Per la procedura specifica, vedere [impostare l'autorità di gestione dei dispositivi mobili](/mem/intune/fundamentals/mdm-authority-set).</span><span class="sxs-lookup"><span data-stu-id="77bdb-123">For the specific steps, see [Set the mobile device management authority](/mem/intune/fundamentals/mdm-authority-set).</span></span>

    <span data-ttu-id="77bdb-124">L'interfaccia di amministrazione di Endpoint Manager si concentra sulla gestione dei dispositivi e sulla gestione delle app.</span><span class="sxs-lookup"><span data-stu-id="77bdb-124">The Endpoint Manager admin center focuses on device management and app management.</span></span> <span data-ttu-id="77bdb-125">Per un tour di questo interfaccia di amministrazione, vedere [tutorial: Walkthrough Intune in Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager).</span><span class="sxs-lookup"><span data-stu-id="77bdb-125">For a tour of this admin center, see [Tutorial: Walkthrough Intune in Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager).</span></span>

2. <span data-ttu-id="77bdb-126">In **gruppi**, aggiungere un nuovo gruppo di **sicurezza** o di **Microsoft 365** denominato **utenti del dispositivo Windows 10 gestiti**, con un tipo di appartenenza **assegnato** .</span><span class="sxs-lookup"><span data-stu-id="77bdb-126">In **Groups**, add a new **Microsoft 365** or **Security** group named **Managed Windows 10 device users**, with an **Assigned** membership type.</span></span> <span data-ttu-id="77bdb-127">Nei passaggi successivi, verranno assegnati i criteri di conformità a questo gruppo.</span><span class="sxs-lookup"><span data-stu-id="77bdb-127">In the next steps, you'll assign your compliance policy to this group.</span></span> 

    <span data-ttu-id="77bdb-128">Per i passaggi specifici e per informazioni su **Microsoft 365** o gruppi di **sicurezza** , vedere [aggiungere gruppi per l'organizzazione di utenti e dispositivi](/mem/intune/fundamentals/groups-add).</span><span class="sxs-lookup"><span data-stu-id="77bdb-128">For the specific steps, and for information on **Microsoft 365** or **Security** groups, see [Add groups to organize users and devices](/mem/intune/fundamentals/groups-add).</span></span>

3. <span data-ttu-id="77bdb-129">In **dispositivi**, creare un criterio di conformità di Windows 10.</span><span class="sxs-lookup"><span data-stu-id="77bdb-129">In **Devices**, create a Windows 10 compliance policy.</span></span> <span data-ttu-id="77bdb-130">Assegnare questo criterio al gruppo di **utenti di dispositivi Windows 10 gestito** creato.</span><span class="sxs-lookup"><span data-stu-id="77bdb-130">Assign this policy to the **Managed Windows 10 device users** group you created.</span></span>

    <span data-ttu-id="77bdb-131">Nel criterio, è possibile bloccare le password semplici, richiedere un firewall, richiedere che il servizio antimalware di Microsoft Defender sia in esecuzione e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="77bdb-131">In your policy, you can block simple passwords, require a firewall, require the Microsoft Defender Antimalware service be running, and more.</span></span> <span data-ttu-id="77bdb-132">I criteri di conformità in genere includono le impostazioni di base o il minimo indispensabile per ogni dispositivo.</span><span class="sxs-lookup"><span data-stu-id="77bdb-132">A compliance policy typically includes the base settings, or bare minimum that every device should have.</span></span>

    <span data-ttu-id="77bdb-133">Per i passaggi specifici e per informazioni sulle impostazioni di conformità disponibili che è possibile configurare, vedere [use Compliance Policies to set rules for Devices you manage](/mem/intune/protect/device-compliance-get-started).</span><span class="sxs-lookup"><span data-stu-id="77bdb-133">For the specific steps, and for information on the available compliance settings you can configure, see [Use compliance policies to set rules for devices you manage](/mem/intune/protect/device-compliance-get-started).</span></span>

<span data-ttu-id="77bdb-134">Al termine, si dispone di un criterio di conformità del dispositivo per i membri di testing nel gruppo di **utenti di dispositivi Windows 10 gestito** .</span><span class="sxs-lookup"><span data-stu-id="77bdb-134">When finished, you have a device compliance policy for testing members in the **Managed Windows 10 device users** group.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="77bdb-135">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="77bdb-135">Next step</span></span>

<span data-ttu-id="77bdb-136">Esplorare le funzionalità e le funzionalità aggiuntive per la [gestione dei dispositivi mobili](m365-enterprise-test-lab-guides.md#mobile-device-management) nell'ambiente di testing.</span><span class="sxs-lookup"><span data-stu-id="77bdb-136">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="77bdb-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="77bdb-137">See also</span></span>

<span data-ttu-id="77bdb-138">[Microsoft 365 per le guide dei laboratori di testing Enterprise](m365-enterprise-test-lab-guides.md).</span><span class="sxs-lookup"><span data-stu-id="77bdb-138">[Microsoft 365 for enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
[<span data-ttu-id="77bdb-139">Registrazione dei dispositivi iOS e Android nell'ambiente di testing di Microsoft 365 per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="77bdb-139">Enroll iOS and Android devices in your Microsoft 365 for enterprise test environment</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[<span data-ttu-id="77bdb-140">Panoramica di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="77bdb-140">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="77bdb-141">Enterprise Mobility + Security (EMS)</span><span class="sxs-lookup"><span data-stu-id="77bdb-141">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
