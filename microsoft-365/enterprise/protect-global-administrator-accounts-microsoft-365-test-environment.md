---
title: Proteggere gli account di amministratore globale nell'ambiente di testing di Microsoft 365 Enterprise
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
description: Attenersi alla procedura seguente per proteggere gli account di amministratore globale nell'ambiente di testing di Microsoft 365 Enterprise.
ms.openlocfilehash: e6b93e3888873b6d78fec1802d179ed9624ffa63
ms.sourcegitcommit: e525bcf073a61e1350484719a0c3ceb6ff0d8db1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/06/2020
ms.locfileid: "43153869"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="787e1-103">Proteggere gli account di amministratore globale nell'ambiente di testing di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="787e1-103">Protect global administrator accounts in your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="787e1-104">*Questa guida al lab di test può essere usata solo per ambienti di testing di Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="787e1-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="787e1-105">È possibile impedire attacchi digitali all'organizzazione assicurando che gli account di amministratore siano il più sicuro possibile.</span><span class="sxs-lookup"><span data-stu-id="787e1-105">You can prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> <span data-ttu-id="787e1-106">In questo articolo viene descritto come utilizzare i criteri di accesso condizionale di Azure Active Directory (Azure AD) per proteggere gli account di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="787e1-106">This article describes how to use Azure Active Directory (Azure AD) Conditional Access policies to protect global administrator accounts.</span></span>

<span data-ttu-id="787e1-107">Sono disponibili due fasi per la protezione degli account amministratore globale nell'ambiente di testing di Microsoft 365 Enterprise:</span><span class="sxs-lookup"><span data-stu-id="787e1-107">There are two phases to protecting global administrator accounts in your Microsoft 365 Enterprise test environment:</span></span>

1.  <span data-ttu-id="787e1-108">Creare l'ambiente di testing di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="787e1-108">Create the Microsoft 365 Enterprise test environment.</span></span>
2.  <span data-ttu-id="787e1-109">Proteggere l'account di amministratore globale dedicato.</span><span class="sxs-lookup"><span data-stu-id="787e1-109">Protect your dedicated global administrator account.</span></span>

![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="787e1-111">Fare clic [qui](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) per consultare una mappa di tutti gli articoli relativi alla guida al lab test di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="787e1-111">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="787e1-112">Fase 1: Creare l'ambiente di testing di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="787e1-112">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="787e1-113">Se si desidera semplicemente testare la protezione degli account amministratore globale con i requisiti minimi, seguire le istruzioni riportate in [Lightweight base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="787e1-113">If you just want to test global administrator account protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="787e1-114">Se si desidera testare la protezione degli account amministratore globale in un'azienda simulata, seguire le istruzioni riportate nell' [autenticazione pass-through](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="787e1-114">If you want to test global administrator account protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="787e1-115">Testing Global Administrator account Protection non richiede l'ambiente di testing dell'organizzazione simulata, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per un servizio di dominio Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="787e1-115">Testing global administrator account protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="787e1-116">Viene fornito come opzione in modo che sia possibile testare la protezione degli account amministratore globale e sperimentarla in un ambiente che rappresenta un'organizzazione tipica.</span><span class="sxs-lookup"><span data-stu-id="787e1-116">It is provided here as an option so that you can test global administrator account protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-conditional-access-policies"></a><span data-ttu-id="787e1-117">Fase 2: configurare i criteri di accesso condizionale</span><span class="sxs-lookup"><span data-stu-id="787e1-117">Phase 2: Configure Conditional Access policies</span></span>

<span data-ttu-id="787e1-118">Per prima cosa, creare un nuovo account utente come amministratore globale dedicato.</span><span class="sxs-lookup"><span data-stu-id="787e1-118">First, create a new user account as a dedicated global administrator.</span></span>

1. <span data-ttu-id="787e1-119">In una scheda separata, aprire l'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="787e1-119">On a separate tab, open the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span>
2. <span data-ttu-id="787e1-120">Fare clic su **utenti > utenti attivi**, quindi fare clic su **Aggiungi utente**.</span><span class="sxs-lookup"><span data-stu-id="787e1-120">Click **Users > Active users**, and then click **Add a user**.</span></span>
3. <span data-ttu-id="787e1-121">Nel riquadro **Aggiungi utente** , digitare **DedicatedAdmin** in **nome**, **nome visualizzato**e **nomeutente**.</span><span class="sxs-lookup"><span data-stu-id="787e1-121">In the **Add user** pane, type **DedicatedAdmin** in **First name**, **Display name**, and **Username**.</span></span>
4. <span data-ttu-id="787e1-122">Fare clic su **password**, fare clic su **fammi creare la password**e quindi digitare una password complessa.</span><span class="sxs-lookup"><span data-stu-id="787e1-122">Click **Password**, click **Let me create the password**, and then type a strong password.</span></span> <span data-ttu-id="787e1-123">Registrare la password per il nuovo account in una posizione sicura.</span><span class="sxs-lookup"><span data-stu-id="787e1-123">Record the password for this new account in a secure location.</span></span>
5. <span data-ttu-id="787e1-124">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="787e1-124">Click **Next**.</span></span>
6. <span data-ttu-id="787e1-125">Nel riquadro **assegna licenze di prodotto** selezionare **Microsoft 365 e5** o **Office 365 E5**e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="787e1-125">In the **Assign product licenses** pane, select **Microsoft 365 E5** or **Office 365 E5**, and then click **Next**.</span></span>
7. <span data-ttu-id="787e1-126">Nel riquadro **impostazioni facoltative** fare clic su **ruoli**, quindi selezionare interfaccia di **Amministrazione** e **amministratore globale**. Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="787e1-126">In the **Optional settings** pane, click **Roles**, and then select **Admin center access** and **Global admin**. Click **Next**.</span></span>
8. <span data-ttu-id="787e1-127">Nel riquadro **quasi finito** , fare clic su **fine aggiungendo**, quindi fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="787e1-127">On the **You're almost done** pane, click **Finish adding**, and then click **Close**.</span></span>

<span data-ttu-id="787e1-128">Successivamente, creare un nuovo gruppo denominato GlobalAdmins e aggiungere l'account di DedicatedAdmin.</span><span class="sxs-lookup"><span data-stu-id="787e1-128">Next, create a new group named GlobalAdmins and add the DedicatedAdmin account to it.</span></span>

1. <span data-ttu-id="787e1-129">Nella scheda interfaccia di **amministrazione di Microsoft 365** fare clic su **gruppi** nel riquadro di spostamento sinistro e quindi su **gruppi**.</span><span class="sxs-lookup"><span data-stu-id="787e1-129">On the **Microsoft 365 admin center** tab, click **Groups** in the left navigation, and then click **Groups**.</span></span>
2. <span data-ttu-id="787e1-130">Fare clic su **Aggiungi gruppo**.</span><span class="sxs-lookup"><span data-stu-id="787e1-130">Click **Add a group**.</span></span>
3. <span data-ttu-id="787e1-131">Nel riquadro **scegliere un tipo di gruppo** selezionare **sicurezza**e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="787e1-131">In the **Choose a group type** pane, select **Security**, and then click **Next**.</span></span>
4. <span data-ttu-id="787e1-132">Nel riquadro **Configura le nozioni di base** fare clic su **Crea gruppo**e quindi fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="787e1-132">In the **Set up the basics** pane, click **Create group**, and then click **Close**.</span></span>
5. <span data-ttu-id="787e1-133">Nel riquadro **revisione e termina aggiunta gruppo** digitare **GlobalAdmins**e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="787e1-133">In the **Review and finish adding group** pane, type **GlobalAdmins**, and then click **Next**.</span></span>
7. <span data-ttu-id="787e1-134">Nell'elenco dei gruppi fare clic sul gruppo **GlobalAdmins** .</span><span class="sxs-lookup"><span data-stu-id="787e1-134">In the list of groups, click the **GlobalAdmins** group.</span></span>
8. <span data-ttu-id="787e1-135">Nel riquadro **GlobalAdmins** , fare clic su **membri**, quindi fare clic su **Visualizza tutti e Gestisci membri**.</span><span class="sxs-lookup"><span data-stu-id="787e1-135">In the **GlobalAdmins** pane, click **Members**, and then click **View all and manage members**.</span></span>
9. <span data-ttu-id="787e1-136">Nel riquadro **GlobalAdmins** , fare clic su **Aggiungi membri**, selezionare l'account **DedicatedAdmin** e l'account di amministratore globale, quindi fare clic su **Salva > Chiudi > Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="787e1-136">In the **GlobalAdmins** pane, click **Add members**, select the **DedicatedAdmin** account and your global admin account, and then click **Save > Close > Close**.</span></span>

<span data-ttu-id="787e1-137">Successivamente, creare criteri di accesso condizionale per richiedere l'autenticazione a più fattori per gli account di amministratore globale e negare l'autenticazione se il rischio di ingresso è medio o elevato.</span><span class="sxs-lookup"><span data-stu-id="787e1-137">Next, create Conditional Access policies to require multifactor authentication for global administrator accounts and to deny authentication if the sign-in risk is medium or high.</span></span>

<span data-ttu-id="787e1-138">Questo primo criterio richiede che tutti gli account di amministratore globale utilizzino AMF.</span><span class="sxs-lookup"><span data-stu-id="787e1-138">This first policy requires that all global administrator accounts use MFA.</span></span>

1. <span data-ttu-id="787e1-139">In una nuova scheda del browser, passare a [https://portal.azure.com](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="787e1-139">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="787e1-140">Fare clic su **Azure Active Directory > sicurezza > accesso condizionale**.</span><span class="sxs-lookup"><span data-stu-id="787e1-140">Click **Azure Active Directory > Security > Conditional Access**.</span></span>
3. <span data-ttu-id="787e1-141">Nel riquadro **criteri di accesso condizionale** fare clic su **criteri di base: richiedere l'autenticazione master per gli amministratori (anteprima)**.</span><span class="sxs-lookup"><span data-stu-id="787e1-141">In the **Conditional access – Policies** pane, click **Baseline policy: Require MFA for admins (preview)**.</span></span>
4. <span data-ttu-id="787e1-142">Nel riquadro **criteri di base** , fare clic su **usa criteri immediatamente > Salva**.</span><span class="sxs-lookup"><span data-stu-id="787e1-142">In the **Baseline policy** pane, click **Use policy immediately > Save**.</span></span>

<span data-ttu-id="787e1-143">Questo secondo criterio blocca l'accesso all'autenticazione dell'account amministratore globale quando il rischio di ingresso è medio o elevato.</span><span class="sxs-lookup"><span data-stu-id="787e1-143">This second policy blocks access to global administrator account authentication when the sign-in risk is medium or high.</span></span>

1. <span data-ttu-id="787e1-144">Nel riquadro **criteri di accesso condizionale** fare clic su **nuovo criterio**.</span><span class="sxs-lookup"><span data-stu-id="787e1-144">In the **Conditional access – Policies** pane, click **New policy**.</span></span>
2. <span data-ttu-id="787e1-145">Nel **nuovo** riquadro, digitare **Global Administrators** in **nome**.</span><span class="sxs-lookup"><span data-stu-id="787e1-145">In the **New** pane, type **Global administrators** in **Name**.</span></span>
3. <span data-ttu-id="787e1-146">Nella sezione **assegnazioni** fare clic su **utenti e gruppi**.</span><span class="sxs-lookup"><span data-stu-id="787e1-146">In the **Assignments** section, click **Users and groups**.</span></span>
4. <span data-ttu-id="787e1-147">Nella scheda **Includi** del riquadro **utenti e gruppi** fare clic su **Seleziona utenti e gruppi > utenti e gruppi > selezionare**.</span><span class="sxs-lookup"><span data-stu-id="787e1-147">On the **Include** tab of the **Users and groups** pane, click **Select users and groups > Users and groups > Select**.</span></span>
5. <span data-ttu-id="787e1-148">Nel riquadro **Seleziona** fare clic sul gruppo **GlobalAdmins** e quindi fare clic su **Seleziona > operazione completata**.</span><span class="sxs-lookup"><span data-stu-id="787e1-148">In the **Select** pane, click the **GlobalAdmins** group, and then click **Select > Done**.</span></span>
6. <span data-ttu-id="787e1-149">Nella sezione **assegnazioni** fare clic su **condizioni**.</span><span class="sxs-lookup"><span data-stu-id="787e1-149">In the **Assignments** section, click **Conditions**.</span></span>
7. <span data-ttu-id="787e1-150">Nel riquadro **condizioni** fare clic su **rischio di accesso**, fare clic **su Sì** per **Configura**, fare clic su **alto** e **medio**, quindi fare clic su **Seleziona** e **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="787e1-150">In the **Conditions** pane, click **Sign-in risk**, click **Yes** for **Configure**, click **High** and **Medium**, and then click **Select** and **Done**.</span></span>
8. <span data-ttu-id="787e1-151">Nella sezione **controlli di accesso** del **nuovo** riquadro fare clic su **Concedi**.</span><span class="sxs-lookup"><span data-stu-id="787e1-151">In the **Access controls** section of the **New** pane, click **Grant**.</span></span>
9. <span data-ttu-id="787e1-152">Nel riquadro **Concedi** , fare clic su **Blocca accesso**, quindi fare clic su **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="787e1-152">In the **Grant** pane, click **Block access**, and then click **Select**.</span></span>
10. <span data-ttu-id="787e1-153">Nel **nuovo** riquadro, fare clic **su** attiva per **abilitare il criterio**, quindi fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="787e1-153">In the **New** pane, click **On** for **Enable policy**, and then click **Create**.</span></span>
11. <span data-ttu-id="787e1-154">Chiudere le schede di interfaccia di amministrazione di **Azure Portal** e **Microsoft 365** .</span><span class="sxs-lookup"><span data-stu-id="787e1-154">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="787e1-155">Per testare il primo criterio, disconnettersi e accedere con l'account DedicatedAdmin.</span><span class="sxs-lookup"><span data-stu-id="787e1-155">To test the first policy, sign out and sign in with the DedicatedAdmin account.</span></span> <span data-ttu-id="787e1-156">È necessario che venga richiesto di configurare l'autenticazione master.</span><span class="sxs-lookup"><span data-stu-id="787e1-156">You should be prompted to configure MFA.</span></span> <span data-ttu-id="787e1-157">Questo dimostra che il primo criterio viene applicato.</span><span class="sxs-lookup"><span data-stu-id="787e1-157">This demonstrates that the first policy is being applied.</span></span>

<span data-ttu-id="787e1-158">Vedere il passaggio [Proteggi account amministratore globale](identity-create-protect-global-admins.md#identity-global-admin) nella fase di identità per informazioni e collegamenti per proteggere gli account di amministratore globale in produzione.</span><span class="sxs-lookup"><span data-stu-id="787e1-158">See the [Protect global administrator accounts](identity-create-protect-global-admins.md#identity-global-admin) step in the Identity phase for information and links to protect your global administrator accounts in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="787e1-159">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="787e1-159">Next step</span></span>

<span data-ttu-id="787e1-160">Esplorare altre caratteristiche e funzionalità [identità](m365-enterprise-test-lab-guides.md#identity) nell'ambiente di test.</span><span class="sxs-lookup"><span data-stu-id="787e1-160">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="787e1-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="787e1-161">See also</span></span>

[<span data-ttu-id="787e1-162">Fase 2: identità</span><span class="sxs-lookup"><span data-stu-id="787e1-162">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="787e1-163">Guide al lab di test di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="787e1-163">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

<span data-ttu-id="787e1-164">[Distribuzione di Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="787e1-164">[Microsoft 365 Enterprise deployment](deploy-microsoft-365-enterprise.md)</span></span>

[<span data-ttu-id="787e1-165">Documentazione di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="787e1-165">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
