---
title: Criteri di conformità dei dispositivi per l'ambiente di testing di Microsoft 365 per l'organizzazione
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
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Utilizzare questa guida del laboratorio di testing per aggiungere criteri di conformità dei dispositivi di Intune all'ambiente di testing di Microsoft 365 per l'organizzazione.
ms.openlocfilehash: c1de822e5a97416bd0c672d88f2902d8986638c8
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487413"
---
# <a name="device-compliance-policies-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="c7fc1-103">Criteri di conformità dei dispositivi per l'ambiente di testing di Microsoft 365 per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="c7fc1-103">Device compliance policies for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="c7fc1-104">*Questa guida del laboratorio di testing può essere utilizzata solo per Microsoft 365 per gli ambienti di testing dell'organizzazione.*</span><span class="sxs-lookup"><span data-stu-id="c7fc1-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="c7fc1-105">In questo articolo viene descritto come aggiungere un criterio di conformità del dispositivo Intune per i dispositivi Windows 10 e le app Microsoft 365 per Enterprise all'ambiente di testing di Microsoft 365 per Enterprise.</span><span class="sxs-lookup"><span data-stu-id="c7fc1-105">This article describes how to add an Intune device compliance policy for Windows 10 devices and Microsoft 365 Apps for enterprise to your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="c7fc1-106">L'aggiunta di un criterio di conformità del dispositivo di Intune implica due fasi:</span><span class="sxs-lookup"><span data-stu-id="c7fc1-106">Adding an Intune device compliance policy involves two phases:</span></span>
- [<span data-ttu-id="c7fc1-107">Fase 1: creare l'ambiente di testing di Microsoft 365 per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="c7fc1-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="c7fc1-108">Fase 2: creare un criterio di conformità del dispositivo per i dispositivi Windows 10</span><span class="sxs-lookup"><span data-stu-id="c7fc1-108">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>](#phase-2-create-a-device-compliance-policy-for-windows-10-devices)

![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="c7fc1-110">Per una mappa visiva su tutti gli articoli della guida del laboratorio di testing di Microsoft 365 for Enterprise, accedere a [microsoft 365 per la guida dello stack del laboratorio di testing dell'organizzazione](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="c7fc1-110">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="c7fc1-111">Fase 1: creare l'ambiente di testing di Microsoft 365 per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="c7fc1-111">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="c7fc1-112">Se si desidera configurare i criteri MAM solo in modo semplice con i requisiti minimi, seguire le istruzioni in [Lightweight base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="c7fc1-112">If you want to configure MAM policies in only a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="c7fc1-113">Se si desidera configurare i criteri MAM in un'azienda simulata, seguire le istruzioni riportate nell' [autenticazione pass-through](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="c7fc1-113">If you want to configure MAM policies in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="c7fc1-114">Testing Automatic Licensing and Group Membership non richiede l'ambiente di testing dell'organizzazione simulata, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per una foresta di servizi di dominio Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="c7fc1-114">Testing automated licensing and group membership doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="c7fc1-115">È disponibile come opzione in modo che sia possibile testare la licenza automatizzata e l'appartenenza ai gruppi e sperimentarla in un ambiente che rappresenta un'organizzazione tipica.</span><span class="sxs-lookup"><span data-stu-id="c7fc1-115">It's provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span>
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a><span data-ttu-id="c7fc1-116">Fase 2: creare un criterio di conformità del dispositivo per i dispositivi Windows 10</span><span class="sxs-lookup"><span data-stu-id="c7fc1-116">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>

<span data-ttu-id="c7fc1-117">In questa fase, creare un criterio di conformità del dispositivo per i dispositivi Windows 10.</span><span class="sxs-lookup"><span data-stu-id="c7fc1-117">In this phase, create a device compliance policy for Windows 10 devices.</span></span>
  
1. <span data-ttu-id="c7fc1-118">Accedere all'interfaccia di [amministrazione di microsoft 365](https://admin.microsoft.com) e accedere all'abbonamento al laboratorio di testing di Microsoft 365 con l'account di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="c7fc1-118">Go to the [Microsoft 365 admin center](https://admin.microsoft.com) and sign in to your Microsoft 365 test lab subscription with your global administrator account.</span></span>
1. <span data-ttu-id="c7fc1-119">In una nuova scheda del browser, aprire il portale di Azure all'indirizzo [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="c7fc1-119">On a new tab of your browser, open the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>
1. <span data-ttu-id="c7fc1-120">Nella casella di ricerca del portale di Azure, immettere **Intune**e quindi fare clic su **Intune**.</span><span class="sxs-lookup"><span data-stu-id="c7fc1-120">In the search box of the Azure portal, enter **Intune**, and then select **Intune**.</span></span>
1. <span data-ttu-id="c7fc1-121">Se viene visualizzato un messaggio **che non è ancora stato abilitato** per la gestione dei dispositivi nel riquadro di **Microsoft Intune** , selezionarlo.</span><span class="sxs-lookup"><span data-stu-id="c7fc1-121">If you see a **You haven't enabled device management yet** message in the **Microsoft Intune** pane, select it.</span></span> <span data-ttu-id="c7fc1-122">Nel riquadro **autorità di gestione dei dispositivi mobili** selezionare **autorità**di amministrazione di Intune, quindi **scegliere Scegli**.</span><span class="sxs-lookup"><span data-stu-id="c7fc1-122">In the **Mobile Device Management authority** pane, select **Intune MDM Authority**, and then select **Choose**.</span></span>
1. <span data-ttu-id="c7fc1-123">Aggiornare la scheda del browser.</span><span class="sxs-lookup"><span data-stu-id="c7fc1-123">Refresh your browser tab.</span></span>
1. <span data-ttu-id="c7fc1-124">Nel riquadro di spostamento a sinistra, selezionare **gruppi**.</span><span class="sxs-lookup"><span data-stu-id="c7fc1-124">In the left navigation pane, select **Groups**.</span></span>
1. <span data-ttu-id="c7fc1-125">Nel riquadro **gruppi-tutti i gruppi** selezionare **+ nuovo gruppo**.</span><span class="sxs-lookup"><span data-stu-id="c7fc1-125">In the **Groups-All groups** pane, select **+ New Group**.</span></span>
1. <span data-ttu-id="c7fc1-126">Nel riquadro **gruppo** selezionare **Microsoft 365** o **sicurezza** per tipo di **gruppo**, immettere **gli utenti del dispositivo Windows 10 gestiti** in **nome**, selezionare **assegnato** in **tipo di appartenenza**e quindi selezionare **Crea**.</span><span class="sxs-lookup"><span data-stu-id="c7fc1-126">In the **Group** pane, select **Microsoft 365** or **Security** for **Group type?**, enter **Managed Windows 10 device users** in **Name**, select **Assigned** in **Membership type**,  and then select **Create**.</span></span>
1. <span data-ttu-id="c7fc1-127">Selezionare **Microsoft Intune**.</span><span class="sxs-lookup"><span data-stu-id="c7fc1-127">Select **Microsoft Intune**.</span></span>
1. <span data-ttu-id="c7fc1-128">Nell'elenco **attività rapide** del riquadro di **Microsoft Intune** selezionare **Crea un criterio di conformità**.</span><span class="sxs-lookup"><span data-stu-id="c7fc1-128">In the **Microsoft Intune** pane, in the **Quick tasks** list, select **Create a compliance policy**.</span></span>
1. <span data-ttu-id="c7fc1-129">Nel riquadro **profili criteri di conformità** , selezionare **Crea criterio**.</span><span class="sxs-lookup"><span data-stu-id="c7fc1-129">In the **Compliance Policy Profiles** pane, select **Create Policy**.</span></span>
1. <span data-ttu-id="c7fc1-130">Nel riquadro **Crea criterio** , in **nome**, immettere **Windows 10**.</span><span class="sxs-lookup"><span data-stu-id="c7fc1-130">In the **Create Policy** pane, in **Name**, enter **Windows 10**.</span></span> <span data-ttu-id="c7fc1-131">In **piattaforma**selezionare **Windows 10 e versioni successive**, fare clic su **OK** nel riquadro **criteri di conformità di Windows 10** e quindi selezionare **Crea**.</span><span class="sxs-lookup"><span data-stu-id="c7fc1-131">In **Platform**, select **Windows 10 and later**, select **OK** in the **Windows 10 compliance policy** pane, and then select **Create**.</span></span>
1. <span data-ttu-id="c7fc1-132">Selezionare **profili dei criteri di conformità**e quindi selezionare il nome del criterio di **Windows 10** .</span><span class="sxs-lookup"><span data-stu-id="c7fc1-132">Select **Compliance Policy Profiles**, and then select the **Windows 10** policy name.</span></span>
1. <span data-ttu-id="c7fc1-133">Nel riquadro di **Windows 10** , selezionare **assegnazioni**, quindi selezionare **gruppi da includere**.</span><span class="sxs-lookup"><span data-stu-id="c7fc1-133">In the **Windows 10** pane, select **Assignments**, and then select **Select groups to include**.</span></span>
1. <span data-ttu-id="c7fc1-134">Nel riquadro **Seleziona gruppi da includere** selezionare il gruppo di **utenti del dispositivo Windows 10 gestito** e quindi selezionare **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="c7fc1-134">In the **Select groups to include** pane, select the **Managed Windows 10 device users** group, and then select **Select**.</span></span>
1. <span data-ttu-id="c7fc1-135">Selezionare **Salva**, selezionare **Microsoft Intune-Panoramica**, quindi selezionare **app client** nella barra di spostamento a sinistra.</span><span class="sxs-lookup"><span data-stu-id="c7fc1-135">Select **Save**, select **Microsoft Intune-Overview**, and then select **Client apps** in the left navigation.</span></span>
1. <span data-ttu-id="c7fc1-136">Nel riquadro **app client** , selezionare **app**, quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="c7fc1-136">In the **Client Apps** pane, select **Apps**, and then select **Add**.</span></span>
1. <span data-ttu-id="c7fc1-137">Nel riquadro **Aggiungi app** selezionare tipo di **app**e quindi selezionare **Windows 10** in **Microsoft 365 Suite**.</span><span class="sxs-lookup"><span data-stu-id="c7fc1-137">In the **Add app** pane, select **App type**, and then select **Windows 10** under **Microsoft 365 Suite**.</span></span>
1. <span data-ttu-id="c7fc1-138">Nel riquadro **Aggiungi app** , seleziona **informazioni sulla famiglia di applicazioni**.</span><span class="sxs-lookup"><span data-stu-id="c7fc1-138">In the **Add App** pane, select **App Suite Information**.</span></span>
1. <span data-ttu-id="c7fc1-139">Nel riquadro **delle informazioni della famiglia** di applicazioni, immettere **Microsoft 365 Apps for Enterprise** sia in **Suite Name** che nella **Descrizione della famiglia**, quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="c7fc1-139">In the **App Suite Information** pane, enter **Microsoft 365 Apps for enterprise** in both **Suite Name** and **Suite Description**, and then select **OK**.</span></span>
1. <span data-ttu-id="c7fc1-140">Nel riquadro **Aggiungi applicazione** , selezionare **Configura app Suite**, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="c7fc1-140">In the **Add App** pane, select **Configure App Suite**, and then select **OK**.</span></span>
1. <span data-ttu-id="c7fc1-141">Nel riquadro **Aggiungi app** selezionare impostazioni della **famiglia di applicazioni**.</span><span class="sxs-lookup"><span data-stu-id="c7fc1-141">In the **Add App** pane, select **App Suite Settings**.</span></span>
1. <span data-ttu-id="c7fc1-142">Per il **canale di aggiornamento**, selezionare **organizzazione semestrale**e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="c7fc1-142">For **Update Channel**, select **Semi-Annual Enterprise**, and then select **OK**.</span></span>
1. <span data-ttu-id="c7fc1-143">Nel riquadro **Aggiungi applicazione** selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="c7fc1-143">In the **Add app** pane, select **Add**.</span></span>

<span data-ttu-id="c7fc1-144">Ora si dispone di un criterio di conformità del dispositivo per testare le app selezionate nei criteri di conformità dei dispositivi **Windows 10** e per i membri del gruppo di **utenti del dispositivo Windows 10 gestito** .</span><span class="sxs-lookup"><span data-stu-id="c7fc1-144">You now have a device compliance policy for testing the selected apps in the **Windows 10** device compliance policy and for members of the **Managed Windows 10 device users** group.</span></span> <span data-ttu-id="c7fc1-145">Tenere presente che se si seleziona **Microsoft 365** come tipo di gruppo, vengono create altre risorse.</span><span class="sxs-lookup"><span data-stu-id="c7fc1-145">Please note that selecting **Microsoft 365** as the group type creates additional resources.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="c7fc1-146">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="c7fc1-146">Next step</span></span>

<span data-ttu-id="c7fc1-147">Esplorare le funzionalità e le funzionalità aggiuntive per la [gestione dei dispositivi mobili](m365-enterprise-test-lab-guides.md#mobile-device-management) nell'ambiente di testing.</span><span class="sxs-lookup"><span data-stu-id="c7fc1-147">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="c7fc1-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c7fc1-148">See also</span></span>

<span data-ttu-id="c7fc1-149">[Microsoft 365 per le guide dei laboratori di testing Enterprise](m365-enterprise-test-lab-guides.md).</span><span class="sxs-lookup"><span data-stu-id="c7fc1-149">[Microsoft 365 for enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
[<span data-ttu-id="c7fc1-150">Registrazione dei dispositivi iOS e Android nell'ambiente di testing di Microsoft 365 per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="c7fc1-150">Enroll iOS and Android devices in your Microsoft 365 for enterprise test environment</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[<span data-ttu-id="c7fc1-151">Panoramica di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="c7fc1-151">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="c7fc1-152">Enterprise Mobility + Security (EMS)</span><span class="sxs-lookup"><span data-stu-id="c7fc1-152">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
