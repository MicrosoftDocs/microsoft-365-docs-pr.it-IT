---
title: Criteri di conformità dei dispositivi per l'ambiente di testing di Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/14/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Utilizzare questa guida del laboratorio di testing per aggiungere criteri di conformità dei dispositivi di Intune all'ambiente di testing di Microsoft 365 Enterprise.
ms.openlocfilehash: dbe0592dfcac7090da194c85db8e788e8e64a0e7
ms.sourcegitcommit: 2c2248b03f7753d64490f2f7e56ec644a235b65a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/15/2019
ms.locfileid: "38639806"
---
# <a name="device-compliance-policies-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="6c80c-103">Criteri di conformità dei dispositivi per l'ambiente di testing di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="6c80c-103">Device compliance policies for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="6c80c-104">Con le istruzioni riportate in questo articolo, è possibile aggiungere un criterio di conformità del dispositivo Intune all'ambiente di testing di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="6c80c-104">With the instructions in this article, you add an Intune device compliance policy to your Microsoft 365 Enterprise test environment.</span></span>

![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="6c80c-106">Fare clic [qui](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) per consultare una mappa di tutti gli articoli relativi alla guida al lab test di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="6c80c-106">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="6c80c-107">Fase 1: Creare l'ambiente di testing di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="6c80c-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="6c80c-108">Se si desidera solo configurare i criteri MAM in modo semplice con i requisiti minimi, seguire le istruzioni in [Lightweight base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="6c80c-108">If you just want to configure MAM policies in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="6c80c-109">Se si desidera configurare i criteri MAM in un'azienda simulata, seguire le istruzioni riportate nell' [autenticazione pass-through](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="6c80c-109">If you want to configure MAM policies in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="6c80c-110">La verifica delle licenze automatizzate e dell'appartenenza ai gruppi non richiede l'ambiente di testing dell'organizzazione simulata, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per una foresta di servizi di dominio Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="6c80c-110">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="6c80c-111">Viene fornito come opzione in modo che sia possibile testare la licenza automatizzata e l'appartenenza ai gruppi e sperimentarla in un ambiente che rappresenta un'organizzazione tipica.</span><span class="sxs-lookup"><span data-stu-id="6c80c-111">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a><span data-ttu-id="6c80c-112">Fase 2: creare un criterio di conformità del dispositivo per i dispositivi Windows 10</span><span class="sxs-lookup"><span data-stu-id="6c80c-112">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>

<span data-ttu-id="6c80c-113">In questa fase, è possibile creare un criterio di conformità del dispositivo per i dispositivi Windows 10.</span><span class="sxs-lookup"><span data-stu-id="6c80c-113">In this phase, you create a device compliance policy for Windows 10 devices.</span></span>
  
1. <span data-ttu-id="6c80c-114">Accedere al portale di Office 365 all'indirizzo[https://portal.office.com](https://portal.office.com)() e accedere alla sottoscrizione di laboratorio di testing di Office 365 con l'account di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="6c80c-114">Go to the Office 365 portal at ([https://portal.office.com](https://portal.office.com)) and sign in to your Office 365 test lab subscription with your global administrator account.</span></span>
    
2. <span data-ttu-id="6c80c-115">In una nuova scheda del browser, aprire il portale di Azure all' [https://portal.azure.com](https://portal.azure.com)indirizzo.</span><span class="sxs-lookup"><span data-stu-id="6c80c-115">On a new tab of your browser, open the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>

3. <span data-ttu-id="6c80c-116">Nella scheda portale di Azure nel browser, nel riquadro di spostamento, fare clic su **tutti i servizi**, digitare **Intune**, quindi fare clic su **Intune**.</span><span class="sxs-lookup"><span data-stu-id="6c80c-116">On the Azure portal tab in your browser, in the navigation pane, click **All services**, type **Intune**, and then click **Intune**.</span></span>
    
4. <span data-ttu-id="6c80c-117">Se viene visualizzato un messaggio **che non è stato abilitato** per la gestione **dei** dispositivi, fare clic su di esso.</span><span class="sxs-lookup"><span data-stu-id="6c80c-117">If you see a **You haven't enabled device management yet** message on the **Microsoft Intune** blade, click it.</span></span> <span data-ttu-id="6c80c-118">Sul blade di **gestione dei dispositivi mobili** , fare clic su **autorità MDM di Intune**, quindi fare clic su **Scegli**.</span><span class="sxs-lookup"><span data-stu-id="6c80c-118">On the **Mobile Device Management authority** blade, click **Intune MDM Authority**, and then click **Choose**.</span></span> <span data-ttu-id="6c80c-119">Aggiornare la scheda del browser.</span><span class="sxs-lookup"><span data-stu-id="6c80c-119">Refresh your browser tab.</span></span>
    
5. <span data-ttu-id="6c80c-120">Nel riquadro di spostamento a sinistra fare clic su **Gruppi**.</span><span class="sxs-lookup"><span data-stu-id="6c80c-120">In the left navigation pane, click **Groups**.</span></span>
    
6. <span data-ttu-id="6c80c-121">Nel pannello **gruppi-tutti i gruppi** fare clic su **+ nuovo gruppo**.</span><span class="sxs-lookup"><span data-stu-id="6c80c-121">On the **Groups-All groups** blade, click **+ New Group**.</span></span>
    
7. <span data-ttu-id="6c80c-122">Nel pannello **gruppo** , selezionare **Office 365** o **sicurezza** per **tipo di gruppo**, digitare utenti dei **dispositivi Windows 10 gestiti** in **nome**, selezionare **assegnato** in **tipo di appartenenza**e quindi fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="6c80c-122">On the **Group** blade, select **Office 365** or **Security** for **Group type?**, type **Managed Windows 10 device users** in **Name**, select **Assigned** in **Membership type**,  and then click **Create**.</span></span> 
    
8. <span data-ttu-id="6c80c-123">Chiudere il pannello **Gruppo**.</span><span class="sxs-lookup"><span data-stu-id="6c80c-123">Close the **Group** blade.</span></span>
    
11. <span data-ttu-id="6c80c-124">Chiudere il Blade **gruppi-tutti i gruppi** .</span><span class="sxs-lookup"><span data-stu-id="6c80c-124">Close the **Groups-All groups** blade.</span></span>
    
12. <span data-ttu-id="6c80c-125">Nell'elenco **attività rapide** del Blade di **Microsoft Intune** fare clic su **Crea un criterio di conformità**.</span><span class="sxs-lookup"><span data-stu-id="6c80c-125">On the **Microsoft Intune** blade, in the **Quick tasks** list, click **Create a compliance policy**.</span></span>
    
13. <span data-ttu-id="6c80c-126">Nel pannello **Profili dei criteri di conformità**, fare clic su **Crea criterio**.</span><span class="sxs-lookup"><span data-stu-id="6c80c-126">On the **Compliance Policy Profiles** blade, click **Create Policy**.</span></span>
    
14. <span data-ttu-id="6c80c-127">Nel pannello **Crea criterio** , in **nome**, digitare **Windows 10**.</span><span class="sxs-lookup"><span data-stu-id="6c80c-127">On the **Create Policy** blade, in **Name**, type **Windows 10**.</span></span> <span data-ttu-id="6c80c-128">In **piattaforma**selezionare **Windows 10 e versioni successive**, fare clic su **OK** nel Blade **criteri di conformità di Windows 10** e quindi fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="6c80c-128">In **Platform**, select **Windows 10 and later**, click **OK** on the **Windows 10 compliance policy** blade, and then click **Create**.</span></span> <span data-ttu-id="6c80c-129">Chiudere il Blade **Windows 10** .</span><span class="sxs-lookup"><span data-stu-id="6c80c-129">Close the **Windows 10** blade.</span></span>
    
15. <span data-ttu-id="6c80c-130">Nel pannello **profili dei criteri di conformità** , fare clic sul nome del criterio di **Windows 10** .</span><span class="sxs-lookup"><span data-stu-id="6c80c-130">On the **Compliance Policy Profiles** blade, click the **Windows 10** policy name.</span></span>
    
16. <span data-ttu-id="6c80c-131">Nel pannello di **Windows 10** , fare clic su **assegnazioni**, quindi fare clic su **Seleziona gruppi da includere**.</span><span class="sxs-lookup"><span data-stu-id="6c80c-131">On the **Windows 10** blade, click **Assignments**, and then click **Select groups to include**.</span></span>
    
17. <span data-ttu-id="6c80c-132">Nel pannello **Seleziona gruppi da includere** , fare clic sul gruppo **utenti di dispositivi Windows 10 gestiti** e quindi fare clic su **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="6c80c-132">On the **Select groups to include** blade, click the **Managed Windows 10 device users** group, and then click **Select**.</span></span>
    
18. <span data-ttu-id="6c80c-133">Fare clic su **Salva**e quindi chiudere il Blade **Windows 10-assegnazioni** .</span><span class="sxs-lookup"><span data-stu-id="6c80c-133">Click **Save**, and then close the **Windows 10 - Assignments** blade.</span></span>
    
19. <span data-ttu-id="6c80c-134">Chiudere il pannello **Profili dei criteri di conformità**.</span><span class="sxs-lookup"><span data-stu-id="6c80c-134">Close the **Compliance Policy Profiles** blade.</span></span>
    
20. <span data-ttu-id="6c80c-135">Sul blade di **Microsoft Intune** , fare clic su **app client** nella barra di spostamento a sinistra.</span><span class="sxs-lookup"><span data-stu-id="6c80c-135">On the **Microsoft Intune** blade, click **Client apps** in the left navigation.</span></span>
    
21. <span data-ttu-id="6c80c-136">Sul Blade **Apps client** fare clic su **app**e quindi su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="6c80c-136">On the **Client Apps** blade, click **Apps**, and then click **Add**.</span></span> 

22. <span data-ttu-id="6c80c-137">Nel pannello **Aggiungi applicazione** selezionare tipo di **app**e quindi selezionare **Windows 10** in **Office 365 Suite**.</span><span class="sxs-lookup"><span data-stu-id="6c80c-137">In the **Add app** blade, select **App type**, and then select **Windows 10** under **Office 365 Suite**.</span></span>

23. <span data-ttu-id="6c80c-138">Fare clic su **Configura app Suite**e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="6c80c-138">Click **Configure App Suite**, and then click **OK**.</span></span>

24. <span data-ttu-id="6c80c-139">Fare clic su **informazioni su App Suite**, digitare le app **di Office per Windows 10** in **nome della famiglia**, le app **di Office per Windows 10** nella **Descrizione della famiglia**e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="6c80c-139">Click **App Suite Information**, type **Office Apps for Windows 10** in **Suite Name**, **Office Apps for Windows 10** in **Suite Description**, and then click **OK**.</span></span>

25. <span data-ttu-id="6c80c-140">Fare clic su **impostazioni della famiglia di applicazioni**, selezionare **semestrale** nel **canale di aggiornamento**e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="6c80c-140">Click **App Suite Settings**, select **Semi-Annual** in **Update channel**, and then click **OK**.</span></span>

26. <span data-ttu-id="6c80c-141">Nel pannello **Aggiungi applicazione** fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="6c80c-141">On the **Add app** blade, click **Add**.</span></span>

<span data-ttu-id="6c80c-142">Ora si dispone di un criterio di conformità del dispositivo per testare le app selezionate nei criteri di conformità dei dispositivi **Windows 10** e per i membri del gruppo di **utenti del dispositivo Windows 10 gestito** .</span><span class="sxs-lookup"><span data-stu-id="6c80c-142">You now have a device compliance policy for testing the selected apps in the **Windows 10** device compliance policy and for members of the **Managed Windows 10 device users** group.</span></span> <span data-ttu-id="6c80c-143">Tenere presente che selezionando Office 365 come tipo di gruppo verranno create risorse aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="6c80c-143">Please note that selecting Office 365 as the group type will create additional resources.</span></span> 
  
## <a name="next-step"></a><span data-ttu-id="6c80c-144">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="6c80c-144">Next step</span></span>

<span data-ttu-id="6c80c-145">Esplorare le funzionalità e le funzionalità aggiuntive per la [gestione dei dispositivi mobili](m365-enterprise-test-lab-guides.md#mobile-device-management) nell'ambiente di testing.</span><span class="sxs-lookup"><span data-stu-id="6c80c-145">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="6c80c-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6c80c-146">See also</span></span>

<span data-ttu-id="6c80c-147">[Guide del laboratorio di testing di Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md).</span><span class="sxs-lookup"><span data-stu-id="6c80c-147">[Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
[<span data-ttu-id="6c80c-148">Registrazione dei dispositivi iOS e Android nell'ambiente di testing di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="6c80c-148">Enroll iOS and Android devices in your Microsoft 365 Enterprise test environment</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[<span data-ttu-id="6c80c-149">Distribuzione di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="6c80c-149">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="6c80c-150">Enterprise Mobility + Security (EMS)</span><span class="sxs-lookup"><span data-stu-id="6c80c-150">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
