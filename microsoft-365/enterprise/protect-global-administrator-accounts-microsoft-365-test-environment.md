---
title: Proteggere gli account di amministratore globale nell'ambiente di testing di Microsoft 365 per l'organizzazione
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/12/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Attenersi alla procedura seguente per proteggere gli account di amministratore globale nell'ambiente di testing di Microsoft 365 per l'organizzazione.
ms.openlocfilehash: 1ae04e4761ed86e087e647464ad522466ed6abef
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487637"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="ae91e-103">Proteggere gli account di amministratore globale nell'ambiente di testing di Microsoft 365 per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="ae91e-103">Protect global administrator accounts in your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="ae91e-104">*Questa guida del laboratorio di testing può essere utilizzata solo per Microsoft 365 per gli ambienti di testing dell'organizzazione.*</span><span class="sxs-lookup"><span data-stu-id="ae91e-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="ae91e-105">È possibile impedire attacchi digitali all'organizzazione assicurando che gli account di amministratore siano il più sicuro possibile.</span><span class="sxs-lookup"><span data-stu-id="ae91e-105">You can prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> 

<span data-ttu-id="ae91e-106">In questo articolo viene descritto come utilizzare i criteri di accesso condizionale di Azure Active Directory (Azure AD) per proteggere gli account di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="ae91e-106">This article describes how to use Azure Active Directory (Azure AD) conditional access policies to protect global administrator accounts.</span></span>

<span data-ttu-id="ae91e-107">La protezione degli account di amministratore globale nell'ambiente di testing di Microsoft 365 per l'organizzazione implica due fasi:</span><span class="sxs-lookup"><span data-stu-id="ae91e-107">Protecting global administrator accounts in your Microsoft 365 for enterprise test environment involves two phases:</span></span>
- [<span data-ttu-id="ae91e-108">Fase 1: creare l'ambiente di testing di Microsoft 365 per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="ae91e-108">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="ae91e-109">Fase 2: configurare i criteri di accesso condizionale</span><span class="sxs-lookup"><span data-stu-id="ae91e-109">Phase 2: Configure conditional access policies</span></span>](#phase-2-configure-conditional-access-policies)

![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="ae91e-111">Per una mappa visiva su tutti gli articoli della guida del laboratorio di testing di Microsoft 365 for Enterprise, accedere a [microsoft 365 per la guida dello stack del laboratorio di testing dell'organizzazione](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="ae91e-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="ae91e-112">Fase 1: creare l'ambiente di testing di Microsoft 365 per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="ae91e-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="ae91e-113">Se si desidera testare la protezione degli account amministratore globale con i requisiti minimi, seguire le istruzioni contenute in [Lightweight base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="ae91e-113">If you want to test global administrator account protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="ae91e-114">Se si desidera testare la protezione degli account amministratore globale in un'azienda simulata, seguire le istruzioni riportate nell' [autenticazione pass-through](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="ae91e-114">If you want to test global administrator account protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="ae91e-115">Testing Global Administrator account Protection non richiede l'ambiente di testing dell'organizzazione simulata, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per un servizio di dominio Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="ae91e-115">Testing global administrator account protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="ae91e-116">Viene fornito come opzione in modo che sia possibile testare la protezione degli account amministratore globale e sperimentarla in un ambiente che rappresenta un'organizzazione tipica.</span><span class="sxs-lookup"><span data-stu-id="ae91e-116">It is provided here as an option so that you can test global administrator account protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-conditional-access-policies"></a><span data-ttu-id="ae91e-117">Fase 2: configurare i criteri di accesso condizionale</span><span class="sxs-lookup"><span data-stu-id="ae91e-117">Phase 2: Configure conditional access policies</span></span>

<span data-ttu-id="ae91e-118">Per prima cosa, creare un nuovo account utente come amministratore globale dedicato.</span><span class="sxs-lookup"><span data-stu-id="ae91e-118">First, create a new user account as a dedicated global administrator.</span></span>

1. <span data-ttu-id="ae91e-119">In una scheda separata, aprire l'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="ae91e-119">On a separate tab, open the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span>
2. <span data-ttu-id="ae91e-120">Selezionare **utenti**  >  **attivi**e quindi fare clic su **Aggiungi utente**.</span><span class="sxs-lookup"><span data-stu-id="ae91e-120">Select **Users** > **Active users**, and then select **Add a user**.</span></span>
3. <span data-ttu-id="ae91e-121">Nel riquadro **Aggiungi utente** , immettere **DedicatedAdmin** nelle caselle **nome**e cognome, **nome visualizzato**e nome **utente** .</span><span class="sxs-lookup"><span data-stu-id="ae91e-121">In the **Add user** pane, enter **DedicatedAdmin** in the **First name**, **Display name**, and **Username** boxes.</span></span>
4. <span data-ttu-id="ae91e-122">Seleziona **password**, quindi **fammi creare la password**e quindi immetti una password complessa.</span><span class="sxs-lookup"><span data-stu-id="ae91e-122">Select **Password**, select **Let me create the password**, and then enter a strong password.</span></span> <span data-ttu-id="ae91e-123">Registrare la password per il nuovo account in una posizione sicura.</span><span class="sxs-lookup"><span data-stu-id="ae91e-123">Record the password for this new account in a secure location.</span></span>
5. <span data-ttu-id="ae91e-124">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="ae91e-124">Select **Next**.</span></span>
6. <span data-ttu-id="ae91e-125">Nel riquadro **assegna licenze di prodotto** , selezionare **Microsoft 365 E5**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="ae91e-125">In the **Assign product licenses** pane, select **Microsoft 365 E5**, and then select **Next**.</span></span>
7. <span data-ttu-id="ae91e-126">Nel riquadro **impostazioni facoltative** , selezionare **ruoli**amministratore dell'interfaccia di amministrazione di  >  **accesso**  >  **globale**  >  **successivo**.</span><span class="sxs-lookup"><span data-stu-id="ae91e-126">In the **Optional settings** pane, select **Roles** > **Admin center access** > **Global admin** > **Next**.</span></span>
8. <span data-ttu-id="ae91e-127">Nel riquadro **quasi finito** , selezionare **fine aggiunta**, quindi selezionare **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="ae91e-127">On the **You're almost done** pane, select **Finish adding**, and then select **Close**.</span></span>

<span data-ttu-id="ae91e-128">Successivamente, creare un nuovo gruppo denominato GlobalAdmins e aggiungere l'account di DedicatedAdmin.</span><span class="sxs-lookup"><span data-stu-id="ae91e-128">Next, create a new group named GlobalAdmins and add the DedicatedAdmin account to it.</span></span>

1. <span data-ttu-id="ae91e-129">Nella scheda dell'interfaccia di **amministrazione di Microsoft 365** selezionare **gruppi** nel riquadro di spostamento sinistro e quindi selezionare **gruppi**.</span><span class="sxs-lookup"><span data-stu-id="ae91e-129">On the **Microsoft 365 admin center** tab, select **Groups** in the left navigation, and then select **Groups**.</span></span>
2. <span data-ttu-id="ae91e-130">Selezionare **Aggiungi un gruppo**.</span><span class="sxs-lookup"><span data-stu-id="ae91e-130">Select **Add a group**.</span></span>
3. <span data-ttu-id="ae91e-131">Nel riquadro **scegliere un tipo di gruppo** , selezionare **sicurezza**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="ae91e-131">In the **Choose a group type** pane, select **Security**, and then select **Next**.</span></span>
4. <span data-ttu-id="ae91e-132">Nel riquadro **Configura le nozioni di base** , selezionare **Crea gruppo**e quindi **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="ae91e-132">In the **Set up the basics** pane, select **Create group**, and then select **Close**.</span></span>
5. <span data-ttu-id="ae91e-133">Nel riquadro **revisione e termina aggiunta gruppo** , immettere **GlobalAdmins**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="ae91e-133">In the **Review and finish adding group** pane, enter **GlobalAdmins**, and then select **Next**.</span></span>
7. <span data-ttu-id="ae91e-134">Nell'elenco dei gruppi, selezionare il gruppo **GlobalAdmins** .</span><span class="sxs-lookup"><span data-stu-id="ae91e-134">In the list of groups, select the **GlobalAdmins** group.</span></span>
8. <span data-ttu-id="ae91e-135">Nel riquadro **GlobalAdmins** , selezionare **membri**, quindi fare clic su **Visualizza tutti e Gestisci membri**.</span><span class="sxs-lookup"><span data-stu-id="ae91e-135">In the **GlobalAdmins** pane, select **Members**, and then select **View all and manage members**.</span></span>
9. <span data-ttu-id="ae91e-136">Nel riquadro **GlobalAdmins** , selezionare **Aggiungi membri**, selezionare l'account **DedicatedAdmin** e l'account di amministratore globale e quindi fare clic su **Salva**  >  **Chiudi Chiudi**  >  **Close**.</span><span class="sxs-lookup"><span data-stu-id="ae91e-136">In the **GlobalAdmins** pane, select **Add members**, select the **DedicatedAdmin** account and your global admin account, and then select **Save** > **Close** > **Close**.</span></span>

<span data-ttu-id="ae91e-137">Successivamente, creare criteri di accesso condizionale per richiedere l'autenticazione a più fattori per gli account di amministratore globale e negare l'autenticazione se il rischio di ingresso è medio o elevato.</span><span class="sxs-lookup"><span data-stu-id="ae91e-137">Next, create conditional access policies to require multi-factor authentication for global administrator accounts and to deny authentication if the sign-in risk is medium or high.</span></span>

<span data-ttu-id="ae91e-138">Questo primo criterio richiede che tutti gli account di amministratore globale utilizzino AMF.</span><span class="sxs-lookup"><span data-stu-id="ae91e-138">This first policy requires that all global administrator accounts use MFA.</span></span>

1. <span data-ttu-id="ae91e-139">In una nuova scheda del browser, passare a [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="ae91e-139">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="ae91e-140">Fare **Azure Active Directory**clic su  >  **Security**  >  **accesso condizionale**per la sicurezza di Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ae91e-140">Click **Azure Active Directory** > **Security** > **Conditional Access**.</span></span>
3. <span data-ttu-id="ae91e-141">Nel riquadro **criteri di accesso condizionale** selezionare **criteri di base: richiedere l'autenticazione master per gli amministratori (anteprima)**.</span><span class="sxs-lookup"><span data-stu-id="ae91e-141">In the **Conditional access – Policies** pane, select **Baseline policy: Require MFA for admins (preview)**.</span></span>
4. <span data-ttu-id="ae91e-142">Nel riquadro **criteri di base** , selezionare **usa criteri immediatamente > Salva**.</span><span class="sxs-lookup"><span data-stu-id="ae91e-142">In the **Baseline policy** pane, select **Use policy immediately > Save**.</span></span>

<span data-ttu-id="ae91e-143">Questo secondo criterio blocca l'accesso all'autenticazione dell'account amministratore globale quando il rischio di ingresso è medio o elevato.</span><span class="sxs-lookup"><span data-stu-id="ae91e-143">This second policy blocks access to global administrator account authentication when the sign-in risk is medium or high.</span></span>

1. <span data-ttu-id="ae91e-144">Nel riquadro **criteri di accesso condizionale** selezionare **nuovo criterio**.</span><span class="sxs-lookup"><span data-stu-id="ae91e-144">In the **Conditional access – Policies** pane, select **New policy**.</span></span>
2. <span data-ttu-id="ae91e-145">Nel **nuovo** riquadro, immettere gli **amministratori globali** in **nome**.</span><span class="sxs-lookup"><span data-stu-id="ae91e-145">In the **New** pane, enter **Global administrators** in **Name**.</span></span>
3. <span data-ttu-id="ae91e-146">Nella sezione **assegnazioni** selezionare **utenti e gruppi**.</span><span class="sxs-lookup"><span data-stu-id="ae91e-146">In the **Assignments** section, select **Users and groups**.</span></span>
4. <span data-ttu-id="ae91e-147">Nella scheda **Includi** del riquadro **utenti e gruppi** Selezionare Seleziona utenti e **gruppi utenti e**  >  **gruppi**  >  **Select**.</span><span class="sxs-lookup"><span data-stu-id="ae91e-147">On the **Include** tab of the **Users and groups** pane, select **Select users and groups** > **Users and groups** > **Select**.</span></span>
5. <span data-ttu-id="ae91e-148">Nel riquadro **Seleziona** selezionare il gruppo **GlobalAdmins** e **quindi selezionare**  >  **fine**.</span><span class="sxs-lookup"><span data-stu-id="ae91e-148">In the **Select** pane, select the **GlobalAdmins** group, and then select **Select** > **Done**.</span></span>
6. <span data-ttu-id="ae91e-149">Nella sezione **assegnazioni** selezionare **condizioni**.</span><span class="sxs-lookup"><span data-stu-id="ae91e-149">In the **Assignments** section, select **Conditions**.</span></span>
7. <span data-ttu-id="ae91e-150">Nel riquadro **condizioni** selezionare rischio di **accesso**, selezionare **Sì** per **Configura**, selezionare **alto** e **medio**e quindi selezionare **Seleziona** e **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="ae91e-150">In the **Conditions** pane, select **Sign-in risk**, select **Yes** for **Configure**, select **High** and **Medium**, and then select **Select** and **Done**.</span></span>
8. <span data-ttu-id="ae91e-151">Nella sezione **controlli di accesso** del **nuovo** riquadro selezionare **Concedi**.</span><span class="sxs-lookup"><span data-stu-id="ae91e-151">In the **Access controls** section of the **New** pane, select **Grant**.</span></span>
9. <span data-ttu-id="ae91e-152">Nel riquadro **Concedi** selezionare **blocca l'accesso**e quindi selezionare **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="ae91e-152">In the **Grant** pane, select **Block access**, and then select **Select**.</span></span>
10. <span data-ttu-id="ae91e-153">Nel **nuovo** riquadro, selezionare attivato **per** **attivare il criterio**, quindi selezionare **Crea**.</span><span class="sxs-lookup"><span data-stu-id="ae91e-153">In the **New** pane, select **On** for **Enable policy**, and then select **Create**.</span></span>
11. <span data-ttu-id="ae91e-154">Chiudere le schede di interfaccia di amministrazione di **Azure Portal** e **Microsoft 365** .</span><span class="sxs-lookup"><span data-stu-id="ae91e-154">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="ae91e-155">Per testare il primo criterio, disconnettersi e accedere con l'account DedicatedAdmin.</span><span class="sxs-lookup"><span data-stu-id="ae91e-155">To test the first policy, sign out and sign in with the DedicatedAdmin account.</span></span> <span data-ttu-id="ae91e-156">È necessario che venga richiesto di configurare l'autenticazione master.</span><span class="sxs-lookup"><span data-stu-id="ae91e-156">You should be prompted to configure MFA.</span></span> <span data-ttu-id="ae91e-157">Questo dimostra che il primo criterio viene applicato.</span><span class="sxs-lookup"><span data-stu-id="ae91e-157">This demonstrates that the first policy is being applied.</span></span>

## <a name="next-step"></a><span data-ttu-id="ae91e-158">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="ae91e-158">Next step</span></span>

<span data-ttu-id="ae91e-159">Esplorare altre caratteristiche e funzionalità [identità](m365-enterprise-test-lab-guides.md#identity) nell'ambiente di test.</span><span class="sxs-lookup"><span data-stu-id="ae91e-159">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="ae91e-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ae91e-160">See also</span></span>

[<span data-ttu-id="ae91e-161">Roadmap dell'identità</span><span class="sxs-lookup"><span data-stu-id="ae91e-161">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="ae91e-162">Guide ai lab di test di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="ae91e-162">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="ae91e-163">Panoramica di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="ae91e-163">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="ae91e-164">Microsoft 365 per la documentazione relativa all'organizzazione</span><span class="sxs-lookup"><span data-stu-id="ae91e-164">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
