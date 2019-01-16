---
title: Ambiente di testing di criteri di conformità di dispositivo per la propria azienda 365 Microsoft
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/14/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Utilizzare questa guida dei laboratori di testing per aggiungere criteri di conformità Intune dispositivo per l'organizzazione di 365 Microsoft ambiente di testing.
ms.openlocfilehash: 1d957c5cdc888251224bbca43fe82ab0a15e7a93
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2019
ms.locfileid: "26868908"
---
# <a name="device-compliance-policies-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="83479-103">Ambiente di testing di criteri di conformità di dispositivo per la propria azienda 365 Microsoft</span><span class="sxs-lookup"><span data-stu-id="83479-103">Device compliance policies for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="83479-104">Con le istruzioni riportate in questo articolo, aggiungere criteri di conformità dispositivo Intune all'ambiente di testing Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="83479-104">With the instructions in this article, you add an Intune device compliance policy to your Microsoft 365 Enterprise test environment.</span></span>

![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="83479-106">Fare clic [qui](https://aka.ms/m365etlgstack) per consultare una mappa di tutti gli articoli relativi alla guida al lab test di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="83479-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="83479-107">Fase 1: Preparare l'ambiente di testing Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="83479-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="83479-108">Se si desidera configurare i criteri MAM in un modo semplice con i requisiti minimi, seguire le istruzioni di [configurazione di base semplificata](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="83479-108">If you just want to configure MAM policies in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="83479-109">Se si desidera configurare i criteri MAM in un'azienda simulata, seguire le istruzioni [nell'autenticazione pass-through](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="83479-109">If you want to configure MAM policies in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="83479-p101">Test automatizzati licenze e l'appartenenza al gruppo non richiede l'ambiente di testing simulato enterprise, che include una rete intranet simulata connessione a Internet e la sincronizzazione delle directory per una foresta Windows Server Active Directory. Viene fornito qui come un'opzione in modo che sia possibile testare gestione automatica delle licenze e l'appartenenza al gruppo e sperimentare in un ambiente che rappresenta una tipica organizzazione.</span><span class="sxs-lookup"><span data-stu-id="83479-p101">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a><span data-ttu-id="83479-112">Fase 2: Creare un criterio di conformità di dispositivo per i dispositivi Windows 10</span><span class="sxs-lookup"><span data-stu-id="83479-112">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>

<span data-ttu-id="83479-113">In questa fase è creare un criterio di conformità di dispositivo per i dispositivi Windows 10.</span><span class="sxs-lookup"><span data-stu-id="83479-113">In this phase, you create a device compliance policy for Windows 10 devices.</span></span>
  
1. <span data-ttu-id="83479-114">Accedere al portale di Office in ([https://office.com](https://office.com)) ed eseguire l'accesso alla sottoscrizione di prova di Office 365 con l'account di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="83479-114">Go to the Office portal at ([https://office.com](https://office.com)) and sign in to your Office 365 trial subscription with your global administrator account.</span></span>
    
2. <span data-ttu-id="83479-115">In una nuova scheda del browser, aprire il portale Azure al [https://portal.azure.com](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="83479-115">On a new tab of your browser, open the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>

3. <span data-ttu-id="83479-116">Nella scheda portal Azure nel browser, nel riquadro di spostamento fare clic su **tutti i servizi**, digitare **Intune**e quindi fare clic su **Intune**.</span><span class="sxs-lookup"><span data-stu-id="83479-116">On the Azure portal tab in your browser, in the navigation pane, click **All services**, type **Intune**, and then click **Intune**.</span></span>
    
4. <span data-ttu-id="83479-p102">Se viene visualizzato un messaggio **non è abilitata la gestione dei dispositivi ancora** su blade **Microsoft Intune** , farvi clic. Su blade **autorità di gestione dei dispositivi mobili** , fare clic su **Autorità MDM Intune**e quindi fare clic su **Scegli**. Aggiornare la scheda browser.</span><span class="sxs-lookup"><span data-stu-id="83479-p102">If you see a **You haven't enabled device management yet** message on the **Microsoft Intune** blade, click it. On the **Mobile Device Management authority** blade, click **Intune MDM Authority**, and then click **Choose**. Refresh your browser tab.</span></span>
    
5. <span data-ttu-id="83479-120">Nel riquadro di spostamento a sinistra fare clic su **Gruppi**.</span><span class="sxs-lookup"><span data-stu-id="83479-120">In the left navigation pane, click **Groups**.</span></span>
    
6. <span data-ttu-id="83479-121">Su blade **gruppi a tutti i gruppi** , fare clic su **+ nuovo gruppo**.</span><span class="sxs-lookup"><span data-stu-id="83479-121">On the **Groups-All groups** blade, click **+ New Group**.</span></span>
    
7. <span data-ttu-id="83479-122">Su blade **gruppo** , selezionare **Office 365** per **gruppo tipo?**, digitare **gli utenti di dispositivi gestiti Windows 10** nella casella **nome**, selezionare **assegnato** nel **tipo di appartenenza**e quindi fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="83479-122">On the **Group** blade, select **Office 365** for **Group type?**, type **Managed Windows 10 device users** in **Name**, select **Assigned** in **Membership type**,  and then click **Create**.</span></span> 
    
8. <span data-ttu-id="83479-123">Chiudere il pannello **Gruppo**.</span><span class="sxs-lookup"><span data-stu-id="83479-123">Close the **Group** blade.</span></span>
    
11. <span data-ttu-id="83479-124">Chiudere blade **gruppi a tutti i gruppi** .</span><span class="sxs-lookup"><span data-stu-id="83479-124">Close the **Groups-All groups** blade.</span></span>
    
12. <span data-ttu-id="83479-125">Su blade **Microsoft Intune** , nell'elenco **attività veloce** , fare clic su **Crea un criterio di conformità**.</span><span class="sxs-lookup"><span data-stu-id="83479-125">On the **Microsoft Intune** blade, in the **Quick tasks** list, click **Create a compliance policy**.</span></span>
    
13. <span data-ttu-id="83479-126">Nel pannello **Profili dei criteri di conformità**, fare clic su **Crea criterio**.</span><span class="sxs-lookup"><span data-stu-id="83479-126">On the **Compliance Policy Profiles** blade, click **Create Policy**.</span></span>
    
14. <span data-ttu-id="83479-p103">In **nome**blade **Creare criteri** , digitare **Windows 10**. **Piattaforma**, selezionare **Windows 10 e versioni successive**, fare clic su **OK** nella blade **Windows 10 criteri di conformità** e quindi fare clic su **Crea**. Chiudere blade **Windows 10** .</span><span class="sxs-lookup"><span data-stu-id="83479-p103">On the **Create Policy** blade, in **Name**, type **Windows 10**. In **Platform**, select **Windows 10 and later**, click **OK** on the **Windows 10 compliance policy** blade, and then click **Create**. Close the **Windows 10** blade.</span></span>
    
15. <span data-ttu-id="83479-130">Scegliere il nome del criterio **Windows 10** blade **Profili dei criteri di conformità** .</span><span class="sxs-lookup"><span data-stu-id="83479-130">On the **Compliance Policy Profiles** blade, click the **Windows 10** policy name.</span></span>
    
16. <span data-ttu-id="83479-131">Su blade **10 Windows** , fare clic su **assegnazioni**e quindi fare clic su **Seleziona gruppi da includere**.</span><span class="sxs-lookup"><span data-stu-id="83479-131">On the **Windows 10** blade, click **Assignments**, and then click **Select groups to include**.</span></span>
    
17. <span data-ttu-id="83479-132">Su blade **Selezionare gruppi da includere** fare clic sul gruppo di **utenti di dispositivi gestiti Windows 10** e quindi fare clic su **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="83479-132">On the **Select groups to include** blade, click the **Managed Windows 10 device users** group, and then click **Select**.</span></span>
    
18. <span data-ttu-id="83479-133">Fare clic su **Salva**e quindi chiudere blade **Windows 10 - assegnazioni** .</span><span class="sxs-lookup"><span data-stu-id="83479-133">Click **Save**, and then close the **Windows 10 - Assignments** blade.</span></span>
    
19. <span data-ttu-id="83479-134">Chiudere il pannello **Profili dei criteri di conformità**.</span><span class="sxs-lookup"><span data-stu-id="83479-134">Close the **Compliance Policy Profiles** blade.</span></span>
    
20. <span data-ttu-id="83479-135">Su blade **Intune Microsoft** , fare clic su **applicazioni Client** nel riquadro di spostamento sinistro.</span><span class="sxs-lookup"><span data-stu-id="83479-135">On the **Microsoft Intune** blade, click **Client apps** in the left navigation.</span></span>
    
21. <span data-ttu-id="83479-136">Su blade **Applicazioni Client** , fare clic su **App**e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="83479-136">On the **Client Apps** blade, click **Apps**, and then click **Add**.</span></span> 

22. <span data-ttu-id="83479-137">In blade **Aggiungi app** , selezionare **il tipo di App**e quindi selezionare **Windows 10** in **Famiglia di prodotti di Office 365**.</span><span class="sxs-lookup"><span data-stu-id="83479-137">In the **Add app** blade, select **App type**, and then select **Windows 10** under **Office 365 Suite**.</span></span>

23. <span data-ttu-id="83479-138">Fare clic su **Configura Suite App**e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="83479-138">Click **Configure App Suite**, and then click **OK**.</span></span>

24. <span data-ttu-id="83479-139">Fare clic su **App Suite informazioni**, digitare **Office applicazioni per Windows 10** in **Nome famiglia di prodotti** **Office applicazioni per Windows 10** nel campo **Descrizione famiglia di prodotti**e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="83479-139">Click **App Suite Information**, type **Office Apps for Windows 10** in **Suite Name**, **Office Apps for Windows 10** in **Suite Description**, and then click **OK**.</span></span>

25. <span data-ttu-id="83479-140">Fare clic su **Impostazioni App famiglia di prodotti**, selezionare **semi-annuale** nel **canale di aggiornamento**e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="83479-140">Click **App Suite Settings**, select **Semi-Annual** in **Update channel**, and then click **OK**.</span></span>

26. <span data-ttu-id="83479-141">Su blade **Aggiungi app** , fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="83479-141">On the **Add app** blade, click **Add**.</span></span>

<span data-ttu-id="83479-142">È ora disponibile un criterio di conformità di dispositivo per testare le app selezionate in Criteri di conformità del dispositivo **Windows 10** e per i membri del gruppo di **utenti di dispositivi gestiti Windows 10** .</span><span class="sxs-lookup"><span data-stu-id="83479-142">You now have a device compliance policy for testing the selected apps in the **Windows 10** device compliance policy and for members of the **Managed Windows 10 device users** group.</span></span> 
  
## <a name="next-step"></a><span data-ttu-id="83479-143">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="83479-143">Next step</span></span>

<span data-ttu-id="83479-144">Esplora le funzionalità aggiuntive [gestione dei dispositivi mobili](m365-enterprise-test-lab-guides.md#mobile-device-management) disponibili nell'ambiente di testing.</span><span class="sxs-lookup"><span data-stu-id="83479-144">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="83479-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="83479-145">See also</span></span>

<span data-ttu-id="83479-146">[Guide dei laboratori di testing Microsoft Enterprise 365](m365-enterprise-test-lab-guides.md).</span><span class="sxs-lookup"><span data-stu-id="83479-146">[Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
[<span data-ttu-id="83479-147">Registrazione dei dispositivi iOS e Android nell'ambiente di testing di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="83479-147">Enroll iOS and Android devices in your Microsoft 365 Enterprise test environment</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[<span data-ttu-id="83479-148">Distribuzione di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="83479-148">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="83479-149">Sicurezza (EMS) + mobilità aziendale</span><span class="sxs-lookup"><span data-stu-id="83479-149">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
