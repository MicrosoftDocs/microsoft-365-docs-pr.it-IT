---
title: Criteri MAM per l'ambiente di testing di Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/16/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Utilizzare questa guida dei laboratori di testing per aggiungere criteri di gestione (MAM) Intune applicazione per dispositivi mobili per l'organizzazione di 365 Microsoft ambiente di testing.
ms.openlocfilehash: f00379a5e70dce5e07c031a7647b27041d3fa9d1
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868908"
---
# <a name="mam-policies-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="f9123-103">Criteri MAM per l'ambiente di testing di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f9123-103">MAM policies for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="f9123-104">Con le istruzioni riportate in questo articolo, aggiungere criteri di gestione (MAM) Intune applicazione per dispositivi mobili per l'organizzazione di 365 Microsoft ambiente di testing.</span><span class="sxs-lookup"><span data-stu-id="f9123-104">With the instructions in this article, you add Intune mobile application management (MAM) policies to your Microsoft 365 Enterprise test environment.</span></span>

![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="f9123-106">Fare clic [qui](https://aka.ms/m365etlgstack) per consultare una mappa di tutti gli articoli relativi alla guida al lab test di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="f9123-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="f9123-107">Fase 1: Preparare l'ambiente di testing Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f9123-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="f9123-108">Se si desidera configurare i criteri MAM in un modo semplice con i requisiti minimi, seguire le istruzioni di [configurazione di base semplificata](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="f9123-108">If you just want to configure MAM policies in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="f9123-109">Se si desidera configurare i criteri MAM in un'azienda simulata, seguire le istruzioni [nell'autenticazione pass-through](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="f9123-109">If you want to configure MAM policies in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="f9123-p101">Test automatizzati licenze e l'appartenenza al gruppo non richiede l'ambiente di testing simulato enterprise, che include una rete intranet simulata connessione a Internet e la sincronizzazione delle directory per una foresta Windows Server Active Directory. Viene fornito qui come un'opzione in modo che sia possibile testare gestione automatica delle licenze e l'appartenenza al gruppo e sperimentare in un ambiente che rappresenta una tipica organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f9123-p101">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
>  

## <a name="phase-2-create-and-deploy-mam-policies-for-ios-and-android-devices"></a><span data-ttu-id="f9123-112">Fase 2: creare e distribuire criteri MAM per i dispositivi iOS e Android</span><span class="sxs-lookup"><span data-stu-id="f9123-112">Phase 2: Create and deploy MAM policies for iOS and Android devices</span></span>

<span data-ttu-id="f9123-113">In questa fase, è possibile creare e distribuire due diversi criteri MAM: uno per i dispositivi iOS e uno per i dispositivi Android.</span><span class="sxs-lookup"><span data-stu-id="f9123-113">In this phase, you create and deploy two different MAM policies: one for iOS devices and one for Android devices.</span></span>
  
1. <span data-ttu-id="f9123-114">Accedere al portale di Office 365 in ([https://portal.office.com](https://portal.office.com)) ed eseguire l'accesso alla sottoscrizione di prova di Office 365 con l'account di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="f9123-114">Go to the Office 365 portal at ([https://portal.office.com](https://portal.office.com)) and sign in to your Office 365 trial subscription with your global administrator account.</span></span>
    
2. <span data-ttu-id="f9123-115">In una nuova scheda del browser, aprire il portale Azure al [https://portal.azure.com](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="f9123-115">On a new tab of your browser, open the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>

3. <span data-ttu-id="f9123-116">Nella scheda Azure portale in Internet Explorer, nel riquadro di spostamento fare clic su **tutti i servizi**, digitare **Intune**e quindi fare clic su **Intune**.</span><span class="sxs-lookup"><span data-stu-id="f9123-116">On the Azure portal tab in Internet Explorer, in the navigation pane, click **All services**, type **Intune**, and then click **Intune**.</span></span>
    
4. <span data-ttu-id="f9123-p102">Se viene visualizzato un messaggio **non è abilitata la gestione dei dispositivi ancora** su blade **Microsoft Intune** , farvi clic. Su blade **autorità di gestione dei dispositivi mobili** , fare clic su **Autorità MDM Intune**e quindi fare clic su **Scegli**. Aggiornare la scheda browser.</span><span class="sxs-lookup"><span data-stu-id="f9123-p102">If you see a **You haven't enabled device management yet** message on the **Microsoft Intune** blade, click it. On the **Mobile Device Management authority** blade, click **Intune MDM Authority**, and then click **Choose**. Refresh your browser tab.</span></span>
    
5. <span data-ttu-id="f9123-120">Nel riquadro di spostamento a sinistra fare clic su **Gruppi**.</span><span class="sxs-lookup"><span data-stu-id="f9123-120">In the left navigation pane, click **Groups**.</span></span>
    
6. <span data-ttu-id="f9123-121">Su blade **gruppi a tutti i gruppi** , fare clic su **+ nuovo gruppo**.</span><span class="sxs-lookup"><span data-stu-id="f9123-121">On the **Groups-All groups** blade, click **+ New Group**.</span></span>
    
7. <span data-ttu-id="f9123-122">Su blade **gruppo** , selezionare **Office 365** per **gruppo tipo?**, digitare **gestiti gli utenti di dispositivi iOS** nella casella **nome**, selezionare **assegnato** nel **tipo di appartenenza**e quindi fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="f9123-122">On the **Group** blade, select **Office 365** for **Group type?**, type **Managed iOS device users** in **Name**, select **Assigned** in **Membership type**,  and then click **Create**.</span></span> 
    
8. <span data-ttu-id="f9123-123">Chiudere il pannello **Gruppo**.</span><span class="sxs-lookup"><span data-stu-id="f9123-123">Close the **Group** blade.</span></span>
    
9. <span data-ttu-id="f9123-124">Su blade **gruppi a tutti i gruppi** , fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="f9123-124">On the **Groups-All groups** blade, click **Add**.</span></span>
    
10. <span data-ttu-id="f9123-125">Su blade **gruppo** , selezionare **Office 365** per **gruppo tipo?**, digitare **gestiti Android utente dispositivo** in **nome**, selezionare **assegnato** nel **tipo di appartenenza**e quindi fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="f9123-125">On the **Group** blade, select **Office 365** for **Group type?**, type **Managed Android device user** in **Name**, select **Assigned** in **Membership type**,  and then click **Create**.</span></span>
    
11. <span data-ttu-id="f9123-126">Chiudere blade **gruppi a tutti i gruppi** .</span><span class="sxs-lookup"><span data-stu-id="f9123-126">Close the **Groups-All groups** blade.</span></span>
    
12. <span data-ttu-id="f9123-127">Nel pannello **Intune**, nell'elenco **Attività rapide** fare clic su **Crea nuovi criteri di conformità**.</span><span class="sxs-lookup"><span data-stu-id="f9123-127">On the **Intune** blade, in the **Quick tasks** list, click **Create a compliance policy**.</span></span>
    
13. <span data-ttu-id="f9123-128">Nel pannello **Profili dei criteri di conformità**, fare clic su **Crea criterio**.</span><span class="sxs-lookup"><span data-stu-id="f9123-128">On the **Compliance Policy Profiles** blade, click **Create Policy**.</span></span>
    
14. <span data-ttu-id="f9123-p103">Nel pannello **Crea criterio**, in **Nome** digitare **iOS**. In **Piattaforma**, selezionare **iOS**, fare clic su **OK** nel pannello **Criteri di conformità di iOS**, quindi fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="f9123-p103">On the **Create Policy** blade, in **Name**, type **iOS**. In **Platform**, select **iOS**, click **OK** on the **iOS compliance policy** blade, and then click **Create**.</span></span>
    
15. <span data-ttu-id="f9123-131">Nel pannello **Profili dei criteri di conformità**, fare clic su **Crea criterio**.</span><span class="sxs-lookup"><span data-stu-id="f9123-131">On the **Compliance Policy Profiles** blade, click **Create Policy**.</span></span>
    
16. <span data-ttu-id="f9123-p104">Nel pannello **Crea criterio**, in **Nome** digitare **Android**. In **Piattaforma**, selezionare **Android**, fare clic su **OK** nel pannello **Criteri di conformità di Android**, quindi fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="f9123-p104">On the **Create Policy** blade, in **Name**, type **Android**. In **Platform**, select **Android**, click **OK** on the **Android compliance policy** blade, and then click **Create**.</span></span>
    
17. <span data-ttu-id="f9123-134">Nel pannello **Profili dei criteri di conformità**, fare clic sul nome del criterio **Android**.</span><span class="sxs-lookup"><span data-stu-id="f9123-134">On the **Compliance Policy Profiles** blade, click the **Android** policy name.</span></span>
    
18. <span data-ttu-id="f9123-135">Nella barra di spostamento a sinistra del pannello **Android - Proprietà**, fare clic su **Assegnazioni**, quindi su **Seleziona gruppi**.</span><span class="sxs-lookup"><span data-stu-id="f9123-135">In the left navigation of the **Android - Properties** blade, click **Assignments**, and then click **Select groups**.</span></span>
    
19. <span data-ttu-id="f9123-136">Nel pannello **Seleziona gruppi**, fare clic sul gruppo **Utenti dei dispositivi Android gestiti**, quindi fare clic su **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="f9123-136">On the **Select groups** blade, click the **Managed Android device users** group, and then click **Select**.</span></span>
    
20. <span data-ttu-id="f9123-137">Fare clic su **Salva**e quindi chiudere blade **Android - assegnazioni** .</span><span class="sxs-lookup"><span data-stu-id="f9123-137">Click **Save**, and then close the **Android - Assignments** blade.</span></span>
    
21. <span data-ttu-id="f9123-138">Nel pannello **Profili dei criteri di conformità**, fare clic sul nome del criterio **iOS**.</span><span class="sxs-lookup"><span data-stu-id="f9123-138">On the **Compliance Policy Profiles** blade, click the **iOS** policy name.</span></span>
    
22. <span data-ttu-id="f9123-139">Nella barra di spostamento a sinistra del pannello **iOS - Proprietà**, fare clic su **Assegnazioni**, quindi su **Seleziona gruppi**.</span><span class="sxs-lookup"><span data-stu-id="f9123-139">In the left navigation of the **iOS - Properties** blade, click **Assignments**, and then click **Select groups**.</span></span>
    
23. <span data-ttu-id="f9123-140">Nel pannello **Seleziona gruppi**, fare clic sul gruppo **Utenti dei dispositivi iOS gestiti**, quindi fare clic su **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="f9123-140">On the **Select groups** blade, click the **Managed iOS device users** group, and then click **Select**.</span></span>
    
24. <span data-ttu-id="f9123-141">Fare clic su **Salva**e quindi chiudere blade **iOS - assegnazioni** .</span><span class="sxs-lookup"><span data-stu-id="f9123-141">Click **Save**, and then close the **iOS - Assignments** blade.</span></span>
    
25. <span data-ttu-id="f9123-142">Chiudere il pannello **Profili dei criteri di conformità**.</span><span class="sxs-lookup"><span data-stu-id="f9123-142">Close the **Compliance Policy Profiles** blade.</span></span>
    
26. <span data-ttu-id="f9123-143">Nel pannello **Intune**, fare clic su **Gestisci app** nella barra di spostamento a sinistra.</span><span class="sxs-lookup"><span data-stu-id="f9123-143">On the **Intune** blade, click **Manage apps** in the left navigation.</span></span>
    
27. <span data-ttu-id="f9123-144">Nel pannello **App mobili**, fare clic su **App**.</span><span class="sxs-lookup"><span data-stu-id="f9123-144">On the **Mobile Apps** blade, click **Apps**.</span></span>
    
28. <span data-ttu-id="f9123-145">Nell'elenco delle app, fare clic su **PowerPoint**, </span><span class="sxs-lookup"><span data-stu-id="f9123-145">In the list of apps, click **PowerPoint**,</span></span> 
    
29. <span data-ttu-id="f9123-p105">Nel pannello **Panoramica di PowerPoint**, fare clic su **Assegnazioni > Seleziona gruppi > Dispositivi iOS gestiti > Seleziona**. In **Tipo**, selezionare **Disponibile**, quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f9123-p105">On the **PowerPoint Overview** blade, click **Assignments > Select groups > Managed iOS devices > Select**. In **Type**, select **Available**, and then click **Save**.</span></span>
    
30. <span data-ttu-id="f9123-148">Ripetere il passaggio 29 per le applicazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f9123-148">Repeat step 29 for the following apps:</span></span>
    
    - <span data-ttu-id="f9123-149">Outlook per Android</span><span class="sxs-lookup"><span data-stu-id="f9123-149">Outlook for Android</span></span>
    
    - <span data-ttu-id="f9123-150">Word per iOS</span><span class="sxs-lookup"><span data-stu-id="f9123-150">Word for iOS</span></span>
    
    - <span data-ttu-id="f9123-151">Excel per iOS</span><span class="sxs-lookup"><span data-stu-id="f9123-151">Excel for iOS</span></span>
    
    - <span data-ttu-id="f9123-152">Outlook per iOS</span><span class="sxs-lookup"><span data-stu-id="f9123-152">Outlook for iOS</span></span>
    
    - <span data-ttu-id="f9123-153">Microsoft Dynamics CRM su iPad per iOS</span><span class="sxs-lookup"><span data-stu-id="f9123-153">Microsoft Dynamics CRM on iPad for iOS</span></span>
    
    - <span data-ttu-id="f9123-154">Microsoft Dynamics CRM su iPhone per iOS</span><span class="sxs-lookup"><span data-stu-id="f9123-154">Microsoft Dynamics CRM on iPhone for iOS</span></span>
    
    - <span data-ttu-id="f9123-155">Dynamics CRM per telefoni per Android</span><span class="sxs-lookup"><span data-stu-id="f9123-155">Dynamics CRM for Phones for Android</span></span>
    
    - <span data-ttu-id="f9123-156">Dynamics CRM per tablet per Android</span><span class="sxs-lookup"><span data-stu-id="f9123-156">Dynamics CRM for Tablets for Android</span></span>
    
    - <span data-ttu-id="f9123-157">Excel per Android</span><span class="sxs-lookup"><span data-stu-id="f9123-157">Excel for Android</span></span>
    
    - <span data-ttu-id="f9123-158">Word per Android</span><span class="sxs-lookup"><span data-stu-id="f9123-158">Word for Android</span></span>
    
    - <span data-ttu-id="f9123-159">OneNote per iOS</span><span class="sxs-lookup"><span data-stu-id="f9123-159">OneNote for iOS</span></span>
    
31. <span data-ttu-id="f9123-160">Chiudere il pannello **App mobili - App**.</span><span class="sxs-lookup"><span data-stu-id="f9123-160">Close the **Mobile Apps - Apps** blade.</span></span>
    
32. <span data-ttu-id="f9123-161">Nel pannello **App mobili**, fare clic su **Criteri di protezione delle app**.</span><span class="sxs-lookup"><span data-stu-id="f9123-161">On the **Mobile Apps** blade, click **App Protection Policies**.</span></span>
    
33. <span data-ttu-id="f9123-162">Nel pannello **Criteri di protezione delle app**, fare clic su **Aggiungi un criterio**.</span><span class="sxs-lookup"><span data-stu-id="f9123-162">On the **App Protection Policies** blade, click **Add a policy**.</span></span>
    
34. <span data-ttu-id="f9123-163">Nel pannello **Aggiungi un criterio**, digitare **iOS**, quindi fare clic su **Selezionare le app richieste**.</span><span class="sxs-lookup"><span data-stu-id="f9123-163">On the **Add a policy** blade, type **iOS**, and then click **Select required apps**.</span></span>
    
35. <span data-ttu-id="f9123-164">Nel pannello **App**, fare clic su **PowerPoint**, **Microsoft Dynamics CRM su iPhone**, **Excel**, **Microsoft Dynamics CRM su iPhone**, **Word**, **OneNote** e **Outlook**, quindi fare clic su **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="f9123-164">On the **Apps** blade, click **PowerPoint**, **Microsoft Dynamics CRM on iPhone**, **Excel**, **Microsoft Dynamics CRM on iPhone**, **Word**, **OneNote**, and **Outlook**, and then click **Select**.</span></span>
    
36. <span data-ttu-id="f9123-165">Nel pannello **Aggiungi un criterio**, fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="f9123-165">On the **Add a policy** blade, click **Create**.</span></span>
    
37. <span data-ttu-id="f9123-166">Nel pannello **Criteri di protezione delle app**, fare clic su **Aggiungi un criterio**.</span><span class="sxs-lookup"><span data-stu-id="f9123-166">On the **App Protection Policies** blade, click **Add a policy**.</span></span>
    
38. <span data-ttu-id="f9123-167">Nel pannello **Aggiungi un criterio**, digitare **Android**, selezionare **Android** in **Piattaforma**, quindi fare clic su **Selezionare le app richieste**.</span><span class="sxs-lookup"><span data-stu-id="f9123-167">On the **Add a policy** blade, type **Android**, select **Android** in **Platform**, and then click **Select required apps**.</span></span>
    
39. <span data-ttu-id="f9123-168">Nel pannello **App**, fare clic su **PowerPoint**, **Dynamics CRM per tablet**, **Excel**, **Word**, **Outlook** e **Dynamics CRM per cellulari**, quindi fare clic su **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="f9123-168">On the **Apps** blade, click **PowerPoint**, **Dynamics CRM for tablets**, **Excel**, **Word**, **Outlook**, and **Dynamics CRM for phones**, and then click **Select**.</span></span>
    
40. <span data-ttu-id="f9123-169">Nel pannello **Aggiungi un criterio**, fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="f9123-169">On the **Add a policy** blade, click **Create**.</span></span>
    
<span data-ttu-id="f9123-170">Ora si dispone di due criteri MAM, uno per i dispositivi iOS e uno per i dispositivi Android, e sono pronti per essere utilizzati con le impostazioni di testing per le app selezionate.</span><span class="sxs-lookup"><span data-stu-id="f9123-170">You now have two MAM policies, one for iOS devices and one for Android devices, and are ready to experiment with testing settings for the selected apps.</span></span> 
  
## <a name="next-step"></a><span data-ttu-id="f9123-171">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="f9123-171">Next step</span></span>

<span data-ttu-id="f9123-172">Esplora le funzionalità aggiuntive [gestione dei dispositivi mobili](m365-enterprise-test-lab-guides.md#mobile-device-management) disponibili nell'ambiente di testing.</span><span class="sxs-lookup"><span data-stu-id="f9123-172">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="f9123-173">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f9123-173">See also</span></span>

<span data-ttu-id="f9123-174">[Guide dei laboratori di testing Microsoft Enterprise 365](m365-enterprise-test-lab-guides.md).</span><span class="sxs-lookup"><span data-stu-id="f9123-174">[Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
[<span data-ttu-id="f9123-175">Registrazione dei dispositivi iOS e Android nell'ambiente di testing di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f9123-175">Enroll iOS and Android devices in your Microsoft 365 Enterprise test environment</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[<span data-ttu-id="f9123-176">Distribuzione di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f9123-176">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="f9123-177">Sicurezza (EMS) + mobilità aziendale</span><span class="sxs-lookup"><span data-stu-id="f9123-177">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
