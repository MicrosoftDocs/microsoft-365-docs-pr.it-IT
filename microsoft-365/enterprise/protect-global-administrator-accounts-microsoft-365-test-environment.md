---
title: Proteggere gli account di amministratore globale nell'ambiente di testing di Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/16/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Attenersi alla procedura seguente per proteggere gli account di amministratore globale nell'ambiente di testing di Microsoft 365 Enterprise.
ms.openlocfilehash: 7a6f99ae1123b07618dea9910a0bdd993e36ca13
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "34074146"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="f4f73-103">Proteggere gli account di amministratore globale nell'ambiente di testing di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f4f73-103">Protect global administrator accounts in your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="f4f73-104">È possibile impedire attacchi digitali all'organizzazione assicurando che gli account di amministratore siano il più sicuro possibile.</span><span class="sxs-lookup"><span data-stu-id="f4f73-104">You can prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> <span data-ttu-id="f4f73-105">In questo articolo viene descritto come utilizzare i criteri di accesso condizionale di Azure Active Directory (Azure AD) per proteggere gli account di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="f4f73-105">This article describes how to use Azure Active Directory (Azure AD) conditional access policies to protect global administrator accounts.</span></span>

<span data-ttu-id="f4f73-106">Sono disponibili due fasi per la protezione degli account amministratore globale nell'ambiente di testing di Microsoft 365 Enterprise:</span><span class="sxs-lookup"><span data-stu-id="f4f73-106">There are two phases to protecting global administrator accounts in your Microsoft 365 Enterprise test environment:</span></span>

1.  <span data-ttu-id="f4f73-107">Creare l'ambiente di testing di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="f4f73-107">Create the Microsoft 365 Enterprise test environment.</span></span>
2.  <span data-ttu-id="f4f73-108">Proteggere l'account di amministratore globale dedicato.</span><span class="sxs-lookup"><span data-stu-id="f4f73-108">Protect your dedicated global administrator account.</span></span>

![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="f4f73-110">Fare clic [qui](https://aka.ms/m365etlgstack) per consultare una mappa di tutti gli articoli relativi alla guida al lab test di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="f4f73-110">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="f4f73-111">Fase 1: creare l'ambiente di testing di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f4f73-111">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="f4f73-112">Se si desidera semplicemente testare la protezione degli account amministratore globale con i requisiti minimi, seguire le istruzioni riportate in [Lightweight base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="f4f73-112">If you just want to test global administrator account protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="f4f73-113">Se si desidera testare la protezione degli account amministratore globale in un'azienda simulata, seguire le istruzioni riportate nell' [autenticazione pass-through](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="f4f73-113">If you want to test global administrator account protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>

  
> [!NOTE]
> <span data-ttu-id="f4f73-114">Testing Global Administrator account Protection non richiede l'ambiente di testing dell'organizzazione simulata, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per un servizio di dominio Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="f4f73-114">Testing global administrator account protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="f4f73-115">Viene fornito come opzione in modo che sia possibile testare la protezione degli account amministratore globale e sperimentarla in un ambiente che rappresenta un'organizzazione tipica.</span><span class="sxs-lookup"><span data-stu-id="f4f73-115">It is provided here as an option so that you can test global administrator account protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-conditional-access-policies"></a><span data-ttu-id="f4f73-116">Fase 2: configurare i criteri di accesso condizionale</span><span class="sxs-lookup"><span data-stu-id="f4f73-116">Phase 2: Configure conditional access policies</span></span>

<span data-ttu-id="f4f73-117">Per prima cosa, creare un nuovo account utente come amministratore globale dedicato.</span><span class="sxs-lookup"><span data-stu-id="f4f73-117">First, create a new user account as a dedicated global administrator.</span></span>

1. <span data-ttu-id="f4f73-118">In una scheda separata, aprire l'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="f4f73-118">On a separate tab, open the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span>
2. <span data-ttu-id="f4f73-119">In **utenti attivi**fare clic su **Aggiungi utente**.</span><span class="sxs-lookup"><span data-stu-id="f4f73-119">Under **Active users**, click **Add a user**.</span></span>
3. <span data-ttu-id="f4f73-120">Nella pagina **nuovo utente** , digitare **DedicatedAdmin** in **nome**, **nome visualizzato**e nome **utente**.</span><span class="sxs-lookup"><span data-stu-id="f4f73-120">On the **New user** page, type **DedicatedAdmin** in **First name**, **Display name**, and **Username**.</span></span>
4. <span data-ttu-id="f4f73-121">Fare clic su **password**, fare clic su **fammi creare la password**e quindi digitare una password complessa.</span><span class="sxs-lookup"><span data-stu-id="f4f73-121">Click **Password**, click **Let me create the password**, and then type a strong password.</span></span> <span data-ttu-id="f4f73-122">Registrare la password per il nuovo account in una posizione sicura.</span><span class="sxs-lookup"><span data-stu-id="f4f73-122">Record the password for this new account in a secure location.</span></span>
5. <span data-ttu-id="f4f73-123">Cancellare **fare in modo che l'utente modifichi la password al primo accesso**.</span><span class="sxs-lookup"><span data-stu-id="f4f73-123">Clear **Make this user change their password when they first sign in**.</span></span>
6. <span data-ttu-id="f4f73-124">Fare clic su **ruoli**, quindi su **amministratore globale**.</span><span class="sxs-lookup"><span data-stu-id="f4f73-124">Click **Roles**, and then click **Global administrator**.</span></span>
7. <span data-ttu-id="f4f73-125">Fare clic su **licenze di prodotto**e quindi accendere le licenze **Enterprise Mobility + Security e5** e **Office 365 Enterprise E5** .</span><span class="sxs-lookup"><span data-stu-id="f4f73-125">Click **Product licenses**, and then turn the **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5 licenses** on.</span></span>
8. <span data-ttu-id="f4f73-126">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="f4f73-126">Click **Add**.</span></span>
9. <span data-ttu-id="f4f73-127">Nella **pagina utente è stata aggiunta**l'opzione **Invia password tramite posta elettronica**e quindi fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="f4f73-127">On the **User was added page**, clear **Send password in email**, and then click **Close**.</span></span>

<span data-ttu-id="f4f73-128">Successivamente, creare un nuovo gruppo denominato GlobalAdmins e aggiungere l'account di DedicatedAdmin.</span><span class="sxs-lookup"><span data-stu-id="f4f73-128">Next, create a new group named GlobalAdmins and add the DedicatedAdmin account to it.</span></span>

1. <span data-ttu-id="f4f73-129">Nella scheda interfaccia di **amministrazione di Microsoft 365** fare clic sull'icona gruppi nel riquadro di spostamento a sinistra, quindi fare clic su **gruppi**.</span><span class="sxs-lookup"><span data-stu-id="f4f73-129">On the **Microsoft 365 admin center** tab, click the groups icon in the left navigation, and then click **Groups**.</span></span>
2. <span data-ttu-id="f4f73-130">Fare clic su **Aggiungi gruppo**.</span><span class="sxs-lookup"><span data-stu-id="f4f73-130">Click **Add a group**.</span></span>
3. <span data-ttu-id="f4f73-131">Nella pagina **nuovo gruppo** digitare **GlobalAdmins**.</span><span class="sxs-lookup"><span data-stu-id="f4f73-131">On the **New Group** page, type **GlobalAdmins**.</span></span>
4. <span data-ttu-id="f4f73-132">Fare clic su **Seleziona proprietario** fare clic sull'account amministratore globale, quindi fare clic su **Aggiungi > Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="f4f73-132">Click **Select owner** click your global administrator account, and then click **Add > Close**.</span></span>
5. <span data-ttu-id="f4f73-133">Nell'elenco dei gruppi fare clic sul gruppo **GlobalAdmins** .</span><span class="sxs-lookup"><span data-stu-id="f4f73-133">In the list of groups, click the **GlobalAdmins** group.</span></span>
6. <span data-ttu-id="f4f73-134">Nella pagina **GlobalAdmins** fare clic su **modifica per membro**, quindi fare clic su **Aggiungi membri**.</span><span class="sxs-lookup"><span data-stu-id="f4f73-134">On the **GlobalAdmins** page, click **Edit for Member**, and then click **Add members**.</span></span>
7. <span data-ttu-id="f4f73-135">Nell'elenco, fare clic sull'account **DedicatedAdmin** , quindi fare clic su **salva > chiudi > Chiudi >** interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="f4f73-135">In the list, click the **DedicatedAdmin** account, and then click **Save > Close > Close > Admin center**.</span></span>

<span data-ttu-id="f4f73-136">Successivamente, creare criteri di accesso condizionale per richiedere l'autenticazione a più fattori per gli account di amministratore globale e negare l'autenticazione se il rischio di ingresso è medio o elevato.</span><span class="sxs-lookup"><span data-stu-id="f4f73-136">Next, create conditional access policies to require multifactor authentication for global administrator accounts and to deny authentication if the sign-in risk is medium or high.</span></span>

<span data-ttu-id="f4f73-137">Questo primo criterio richiede che tutti gli account di amministratore globale utilizzino AMF.</span><span class="sxs-lookup"><span data-stu-id="f4f73-137">This first policy requires that all global administrator accounts use MFA.</span></span>

1. <span data-ttu-id="f4f73-138">In una nuova scheda del browser, passare a [https://portal.azure.com](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="f4f73-138">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="f4f73-139">Fare clic su **Azure Active Directory > accesso condizionale**.</span><span class="sxs-lookup"><span data-stu-id="f4f73-139">Click **Azure Active Directory > Conditional access**.</span></span>
3. <span data-ttu-id="f4f73-140">Nel pannello **criteri di accesso condizionale** fare clic su **criteri di base: richiedere l'autenticazione master per gli amministratori (anteprima)**.</span><span class="sxs-lookup"><span data-stu-id="f4f73-140">On the **Conditional access – Policies** blade, click **Baseline policy: Require MFA for admins (preview)**.</span></span>
4. <span data-ttu-id="f4f73-141">Nei **criteri di base...**</span><span class="sxs-lookup"><span data-stu-id="f4f73-141">On the **Baseline policies…**</span></span> <span data-ttu-id="f4f73-142">Blade, fare clic su **Usa criteri immediatamente > Salva**.</span><span class="sxs-lookup"><span data-stu-id="f4f73-142">blade, click **Use policy immediately > Save**.</span></span>

<span data-ttu-id="f4f73-143">Questo secondo criterio blocca l'accesso all'autenticazione dell'account amministratore globale quando il rischio di ingresso è medio o elevato.</span><span class="sxs-lookup"><span data-stu-id="f4f73-143">This second policy blocks access to global administrator account authentication when the sign-in risk is medium or high.</span></span>

1. <span data-ttu-id="f4f73-144">Nel pannello **criteri di accesso condizionale** fare clic su **nuovo criterio**.</span><span class="sxs-lookup"><span data-stu-id="f4f73-144">On the **Conditional access – Policies** blade, click **New policy**.</span></span>
2. <span data-ttu-id="f4f73-145">Nel **nuovo** Blade, digitare **Global Administrators** in **Name**.</span><span class="sxs-lookup"><span data-stu-id="f4f73-145">On the **New** blade, type **Global administrators** in **Name**.</span></span>
3. <span data-ttu-id="f4f73-146">Nella sezione **assegnazioni** fare clic su **utenti e gruppi**.</span><span class="sxs-lookup"><span data-stu-id="f4f73-146">In the **Assignments** section, click **Users and groups**.</span></span>
4. <span data-ttu-id="f4f73-147">Nella scheda **Includi** del Blade **utenti e gruppi** fare clic su **Seleziona utenti e gruppi > utenti e gruppi > selezionare**.</span><span class="sxs-lookup"><span data-stu-id="f4f73-147">On the **Include** tab of the **Users and groups** blade, click **Select users and groups > Users and groups > Select**.</span></span>
5. <span data-ttu-id="f4f73-148">Nel pannello **Seleziona** , fare clic sul **GlobalAdmins > seleziona > fatto**.</span><span class="sxs-lookup"><span data-stu-id="f4f73-148">On the **Select** blade, click the **GlobalAdmins > Select > Done**.</span></span>
6. <span data-ttu-id="f4f73-149">Nella sezione **assegnazioni** fare clic su **condizioni**.</span><span class="sxs-lookup"><span data-stu-id="f4f73-149">In the **Assignments** section, click **Conditions**.</span></span>
7. <span data-ttu-id="f4f73-150">Nel pannello **condizioni** fare clic su **rischio di accesso**, fare clic **su Sì** per **Configura**, fare clic su **alto** e **medio**, quindi fare clic su **Seleziona** e **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="f4f73-150">On the **Conditions** blade, click **Sign-in risk**, click **Yes** for **Configure**, click **High** and **Medium**, and then click **Select** and **Done**.</span></span>
8. <span data-ttu-id="f4f73-151">Nella sezione **controlli di accesso** del **nuovo** Blade, fare clic su **Grant**.</span><span class="sxs-lookup"><span data-stu-id="f4f73-151">In the **Access controls** section of the **New** blade, click **Grant**.</span></span>
9. <span data-ttu-id="f4f73-152">Sul Blade **Grant** , fare clic su **Blocca accesso**, quindi fare clic su **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="f4f73-152">On the **Grant** blade, click **Block access**, and then click **Select**.</span></span>
10. <span data-ttu-id="f4f73-153">Nel **nuovo** Blade, fare clic **su** **attiva per abilitare il criterio**, quindi fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="f4f73-153">On the **New** blade, click **On** for **Enable policy**, and then click **Create**.</span></span>
11. <span data-ttu-id="f4f73-154">Chiudere le schede di interfaccia di amministrazione di **Azure Portal** e **Microsoft 365** .</span><span class="sxs-lookup"><span data-stu-id="f4f73-154">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="f4f73-155">Per testare il primo criterio, disconnettersi e accedere con l'account DedicatedAdmin.</span><span class="sxs-lookup"><span data-stu-id="f4f73-155">To test the first policy, sign out and sign in with the DedicatedAdmin account.</span></span> <span data-ttu-id="f4f73-156">È necessario che venga richiesto di configurare l'autenticazione master nell'account utente.</span><span class="sxs-lookup"><span data-stu-id="f4f73-156">You should be prompted to configure MFA on the user account.</span></span> <span data-ttu-id="f4f73-157">Questo dimostra che il primo criterio viene applicato.</span><span class="sxs-lookup"><span data-stu-id="f4f73-157">This demonstrates that the first policy is being applied.</span></span>

<span data-ttu-id="f4f73-158">Vedere il passaggio [Proteggi account amministratore globale](identity-designate-protect-admin-accounts.md#identity-global-admin) nella fase di identità per informazioni e collegamenti per proteggere gli account di amministratore globale in produzione.</span><span class="sxs-lookup"><span data-stu-id="f4f73-158">See the [Protect global administrator accounts](identity-designate-protect-admin-accounts.md#identity-global-admin) step in the Identity phase for information and links to protect your global administrator accounts in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="f4f73-159">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="f4f73-159">Next step</span></span>

<span data-ttu-id="f4f73-160">Esplorare altre caratteristiche e funzionalità [identità](m365-enterprise-test-lab-guides.md#identity) nell'ambiente di test.</span><span class="sxs-lookup"><span data-stu-id="f4f73-160">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="f4f73-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f4f73-161">See also</span></span>

[<span data-ttu-id="f4f73-162">Fase 2: identità</span><span class="sxs-lookup"><span data-stu-id="f4f73-162">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="f4f73-163">Guide al lab di test di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f4f73-163">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

<span data-ttu-id="f4f73-164">[Distribuzione di Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="f4f73-164">[Microsoft 365 Enterprise deployment](deploy-microsoft-365-enterprise.md)</span></span>

[<span data-ttu-id="f4f73-165">Documentazione di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f4f73-165">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
