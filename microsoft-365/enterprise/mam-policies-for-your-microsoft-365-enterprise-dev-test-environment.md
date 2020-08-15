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
ms.openlocfilehash: 3c77a7ea8ddc5120a2ce53fa0834dab213502657
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686755"
---
# <a name="device-compliance-policies-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="b5e78-103">Criteri di conformità dei dispositivi per l'ambiente di testing di Microsoft 365 per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="b5e78-103">Device compliance policies for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="b5e78-104">*Questa guida del laboratorio di testing può essere utilizzata solo per Microsoft 365 per gli ambienti di testing dell'organizzazione.*</span><span class="sxs-lookup"><span data-stu-id="b5e78-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="b5e78-105">Con le istruzioni riportate in questo articolo, è possibile aggiungere un criterio di conformità del dispositivo Intune per i dispositivi Windows 10 e le app Microsoft 365 per Enterprise all'ambiente di testing di Microsoft 365 per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b5e78-105">With the instructions in this article, you add an Intune device compliance policy for Windows 10 devices and Microsoft 365 Apps for enterprise to your Microsoft 365 for enterprise test environment.</span></span>

![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="b5e78-107">Fare clic [qui](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) per consultare una mappa di tutti gli articoli disponibili nella serie di guide al lab di test di Microsoft 365 per le aziende.</span><span class="sxs-lookup"><span data-stu-id="b5e78-107">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="b5e78-108">Fase 1: creare l'ambiente di testing di Microsoft 365 per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="b5e78-108">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="b5e78-109">Se si desidera solo configurare i criteri MAM in modo semplice con i requisiti minimi, seguire le istruzioni in [Lightweight base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="b5e78-109">If you just want to configure MAM policies in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="b5e78-110">Se si desidera configurare i criteri MAM in un'azienda simulata, seguire le istruzioni riportate nell' [autenticazione pass-through](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="b5e78-110">If you want to configure MAM policies in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="b5e78-111">La verifica delle licenze automatizzate e dell'appartenenza ai gruppi non richiede l'ambiente di testing dell'organizzazione simulata, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per una foresta di servizi di dominio Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="b5e78-111">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="b5e78-112">Viene fornito come opzione in modo che sia possibile testare la licenza automatizzata e l'appartenenza ai gruppi e sperimentarla in un ambiente che rappresenta un'organizzazione tipica.</span><span class="sxs-lookup"><span data-stu-id="b5e78-112">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a><span data-ttu-id="b5e78-113">Fase 2: creare un criterio di conformità del dispositivo per i dispositivi Windows 10</span><span class="sxs-lookup"><span data-stu-id="b5e78-113">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>

<span data-ttu-id="b5e78-114">In questa fase, è possibile creare un criterio di conformità del dispositivo per i dispositivi Windows 10.</span><span class="sxs-lookup"><span data-stu-id="b5e78-114">In this phase, you create a device compliance policy for Windows 10 devices.</span></span>
  
1. <span data-ttu-id="b5e78-115">Accedere all'interfaccia di [amministrazione di microsoft 365](https://admin.microsoft.com) e accedere all'abbonamento al laboratorio di testing di Microsoft 365 con l'account di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="b5e78-115">Go to the [Microsoft 365 admin center](https://admin.microsoft.com) and sign in to your Microsoft 365 test lab subscription with your global administrator account.</span></span>
    
2. <span data-ttu-id="b5e78-116">In una nuova scheda del browser, aprire il portale di Azure all'indirizzo [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="b5e78-116">On a new tab of your browser, open the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>

3. <span data-ttu-id="b5e78-117">Dalla scheda portale di Azure nel browser, digitare **Intune** nella casella di ricerca e quindi fare clic su **Intune**.</span><span class="sxs-lookup"><span data-stu-id="b5e78-117">From the Azure portal tab in your browser, type **Intune** in the search box, and then click **Intune**.</span></span>
    
4. <span data-ttu-id="b5e78-118">Se viene visualizzato un messaggio **che non è ancora stato abilitato** per la gestione dei dispositivi nel riquadro di **Microsoft Intune** , fare clic su di esso.</span><span class="sxs-lookup"><span data-stu-id="b5e78-118">If you see a **You haven't enabled device management yet** message In the **Microsoft Intune** pane, click it.</span></span> <span data-ttu-id="b5e78-119">Nel riquadro **autorità di gestione dei dispositivi mobili** , fare clic su **autorità MDM di Intune**, quindi fare clic su **Scegli**.</span><span class="sxs-lookup"><span data-stu-id="b5e78-119">In the **Mobile Device Management authority** pane, click **Intune MDM Authority**, and then click **Choose**.</span></span> <span data-ttu-id="b5e78-120">Aggiornare la scheda del browser.</span><span class="sxs-lookup"><span data-stu-id="b5e78-120">Refresh your browser tab.</span></span>
    
5. <span data-ttu-id="b5e78-121">Nel riquadro di spostamento a sinistra fare clic su **Gruppi**.</span><span class="sxs-lookup"><span data-stu-id="b5e78-121">In the left navigation pane, click **Groups**.</span></span>
    
6. <span data-ttu-id="b5e78-122">Nel riquadro **gruppi-tutti i gruppi** fare clic su **+ nuovo gruppo**.</span><span class="sxs-lookup"><span data-stu-id="b5e78-122">In the **Groups-All groups** pane, click **+ New Group**.</span></span>
    
7. <span data-ttu-id="b5e78-123">Nel riquadro **gruppo** selezionare **Microsoft 365** o **sicurezza** per tipo di **gruppo**, digitare utenti dei **dispositivi Windows 10 gestiti** in **nome**, selezionare **assegnato** in **tipo di appartenenza**e quindi fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="b5e78-123">In the **Group** pane, select **Microsoft 365** or **Security** for **Group type?**, type **Managed Windows 10 device users** in **Name**, select **Assigned** in **Membership type**,  and then click **Create**.</span></span> 
    
8. <span data-ttu-id="b5e78-124">Fare clic su **Microsoft Intune**.</span><span class="sxs-lookup"><span data-stu-id="b5e78-124">Click **Microsoft Intune**.</span></span> <span data-ttu-id="b5e78-125">Nell'elenco **attività rapide** del riquadro di **Microsoft Intune** fare clic su **Crea un criterio di conformità**.</span><span class="sxs-lookup"><span data-stu-id="b5e78-125">In the **Microsoft Intune** pane, in the **Quick tasks** list, click **Create a compliance policy**.</span></span>
    
9. <span data-ttu-id="b5e78-126">Nel riquadro **profili criteri di conformità** fare clic su **Crea criterio**.</span><span class="sxs-lookup"><span data-stu-id="b5e78-126">In the **Compliance Policy Profiles** pane, click **Create Policy**.</span></span>
    
10. <span data-ttu-id="b5e78-127">Nel riquadro **Crea criterio** , in **nome**, digitare **Windows 10**.</span><span class="sxs-lookup"><span data-stu-id="b5e78-127">In the **Create Policy** pane, in **Name**, type **Windows 10**.</span></span> <span data-ttu-id="b5e78-128">In **piattaforma**selezionare **Windows 10 e versioni successive**, fare clic su **OK** nel riquadro **criteri di conformità di Windows 10** e quindi fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="b5e78-128">In **Platform**, select **Windows 10 and later**, click **OK** In the **Windows 10 compliance policy** pane, and then click **Create**.</span></span> 
    
11. <span data-ttu-id="b5e78-129">Fare clic su **profili criteri di conformità**e quindi fare clic sul nome del criterio di **Windows 10** .</span><span class="sxs-lookup"><span data-stu-id="b5e78-129">Click **Compliance Policy Profiles**, and then click the **Windows 10** policy name.</span></span>
    
12. <span data-ttu-id="b5e78-130">Nel riquadro di **Windows 10** , fare clic su **assegnazioni**, quindi fare clic su **Seleziona gruppi da includere**.</span><span class="sxs-lookup"><span data-stu-id="b5e78-130">In the **Windows 10** pane, click **Assignments**, and then click **Select groups to include**.</span></span>
    
13. <span data-ttu-id="b5e78-131">Nel riquadro **Seleziona gruppi da includere** fare clic sul gruppo **utenti di dispositivi di Windows 10 gestiti** e quindi fare clic su **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="b5e78-131">In the **Select groups to include** pane, click the **Managed Windows 10 device users** group, and then click **Select**.</span></span>
    
14. <span data-ttu-id="b5e78-132">Fare clic su **Salva**, fare clic su **Microsoft Intune-Panoramica**, quindi fare clic su **app client** nella barra di spostamento a sinistra.</span><span class="sxs-lookup"><span data-stu-id="b5e78-132">Click **Save**, click **Microsoft Intune-Overview**, and then click **Client apps** in the left navigation.</span></span>
    
15. <span data-ttu-id="b5e78-133">Nel riquadro **app client** fare clic su **app**e quindi su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="b5e78-133">In the **Client Apps** pane, click **Apps**, and then click **Add**.</span></span> 

16. <span data-ttu-id="b5e78-134">Nel riquadro **Aggiungi app** selezionare tipo di **app**e quindi selezionare **Windows 10** in **Microsoft 365 Suite**.</span><span class="sxs-lookup"><span data-stu-id="b5e78-134">In the **Add app** pane, select **App type**, and then select **Windows 10** under **Microsoft 365 Suite**.</span></span>

17. <span data-ttu-id="b5e78-135">Nel riquadro **Aggiungi app** , seleziona **informazioni sulla famiglia di applicazioni**.</span><span class="sxs-lookup"><span data-stu-id="b5e78-135">In the **Add App** pane, select **App Suite Information**.</span></span>
 
18. <span data-ttu-id="b5e78-136">Nel riquadro **delle informazioni della famiglia** di applicazioni, digitare **Microsoft 365 Apps for Enterprise** sia nella **Descrizione**del **nome** della famiglia che della famiglia di prodotti.</span><span class="sxs-lookup"><span data-stu-id="b5e78-136">In the **App Suite Information** pane, type **Microsoft 365 Apps for enterprise** in both **Suite Name** and **Suite Description**.</span></span>
<span data-ttu-id="b5e78-137">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="b5e78-137">Click OK.</span></span>

19. <span data-ttu-id="b5e78-138">Nel riquadro **Aggiungi app** , selezionare **Configure app Suite**, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b5e78-138">In the **Add App** pane, select **Configure App Suite**, and then click **OK**.</span></span>

20. <span data-ttu-id="b5e78-139">Nel riquadro **Aggiungi app** selezionare impostazioni della **famiglia di applicazioni**.</span><span class="sxs-lookup"><span data-stu-id="b5e78-139">In the **Add App** pane, select **App Suite Settings**.</span></span>

21. <span data-ttu-id="b5e78-140">Per il **canale di aggiornamento**, selezionare **organizzazione semestrale**e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b5e78-140">For **Update Channel**, select **Semi-Annual Enterprise**, and then click **OK**.</span></span>

22. <span data-ttu-id="b5e78-141">Nel riquadro **Aggiungi applicazione** fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="b5e78-141">In the **Add app** pane, click **Add**.</span></span>

<span data-ttu-id="b5e78-142">Ora si dispone di un criterio di conformità del dispositivo per testare le app selezionate nei criteri di conformità dei dispositivi **Windows 10** e per i membri del gruppo di **utenti del dispositivo Windows 10 gestito** .</span><span class="sxs-lookup"><span data-stu-id="b5e78-142">You now have a device compliance policy for testing the selected apps in the **Windows 10** device compliance policy and for members of the **Managed Windows 10 device users** group.</span></span> <span data-ttu-id="b5e78-143">Tenere presente che selezionando Microsoft 365 come tipo di gruppo verranno create risorse aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="b5e78-143">Please note that selecting Microsoft 365 as the group type will create additional resources.</span></span> 
  
## <a name="next-step"></a><span data-ttu-id="b5e78-144">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="b5e78-144">Next step</span></span>

<span data-ttu-id="b5e78-145">Esplorare le funzionalità e le funzionalità aggiuntive per la [gestione dei dispositivi mobili](m365-enterprise-test-lab-guides.md#mobile-device-management) nell'ambiente di testing.</span><span class="sxs-lookup"><span data-stu-id="b5e78-145">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="b5e78-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b5e78-146">See also</span></span>

<span data-ttu-id="b5e78-147">[Microsoft 365 per le guide dei laboratori di testing Enterprise](m365-enterprise-test-lab-guides.md).</span><span class="sxs-lookup"><span data-stu-id="b5e78-147">[Microsoft 365 for enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
[<span data-ttu-id="b5e78-148">Registrazione dei dispositivi iOS e Android nell'ambiente di testing di Microsoft 365 per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="b5e78-148">Enroll iOS and Android devices in your Microsoft 365 for enterprise test environment</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[<span data-ttu-id="b5e78-149">Panoramica di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="b5e78-149">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="b5e78-150">Enterprise Mobility + Security (EMS)</span><span class="sxs-lookup"><span data-stu-id="b5e78-150">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
