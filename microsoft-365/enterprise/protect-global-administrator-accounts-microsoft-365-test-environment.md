---
title: Proteggere gli account di amministratore globale nell'ambiente di testing di Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/16/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Attenersi alla procedura seguente per proteggere gli account di amministratore globale nell'ambiente di testing di Microsoft 365 Enterprise.
ms.openlocfilehash: cded424188447f96e5614f31d3e207bb541d438e
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32290859"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="721c9-103">Proteggere gli account di amministratore globale nell'ambiente di testing di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="721c9-103">Protect global administrator accounts in your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="721c9-104">È possibile impedire attacchi digitali all'organizzazione assicurando che gli account di amministratore siano il più sicuro possibile.</span><span class="sxs-lookup"><span data-stu-id="721c9-104">You can prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> <span data-ttu-id="721c9-105">In questo articolo viene descritto come utilizzare i criteri di accesso condizionale di cloud app di Office 365 e di Azure ad per proteggere gli account di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="721c9-105">This article describes how to use Office 365 Cloud App Security and Azure AD conditional access policies to protect global administrator accounts.</span></span>

<span data-ttu-id="721c9-106">Sono disponibili due fasi per la protezione degli account amministratore globale nell'ambiente di testing di Microsoft 365 Enterprise:</span><span class="sxs-lookup"><span data-stu-id="721c9-106">There are two phases to protecting global administrator accounts in your Microsoft 365 Enterprise test environment:</span></span>

1.  <span data-ttu-id="721c9-107">Creare l'ambiente di testing Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="721c9-107">Create the Microsoft 365 Enterprise test environment.</span></span>
2.  <span data-ttu-id="721c9-108">Proteggere l'account di amministratore globale dedicato.</span><span class="sxs-lookup"><span data-stu-id="721c9-108">Protect your dedicated global administrator account.</span></span>

![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="721c9-110">Fare clic [qui](https://aka.ms/m365etlgstack) per consultare una mappa di tutti gli articoli relativi alla guida al lab test di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="721c9-110">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

> [!NOTE]
> <span data-ttu-id="721c9-111">L'ambiente di testing di Microsoft 365 Enterprise utilizza le versioni E5 di Office 365 e Enterprise Management + Security (EMS).</span><span class="sxs-lookup"><span data-stu-id="721c9-111">The Microsoft 365 Enterprise test environment uses E5 versions of Office 365 and Enterprise Management + Security (EMS).</span></span> <span data-ttu-id="721c9-112">La funzionalità di sicurezza delle app cloud di Office 365 è disponibile solo nella versione E5 di Office 365.</span><span class="sxs-lookup"><span data-stu-id="721c9-112">The Office 365 Cloud App Security feature is only available in the E5 version Office 365.</span></span> 

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="721c9-113">Fase 1: creare l'ambiente di testing di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="721c9-113">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="721c9-114">Se si desidera semplicemente testare la protezione degli account amministratore globale con i requisiti minimi, seguire le istruzioni riportate in [Lightweight base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="721c9-114">If you just want to test global administrator account protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="721c9-115">Se si desidera testare la protezione degli account amministratore globale in un'azienda simulata, seguire le istruzioni riportate nell' [autenticazione pass-through](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="721c9-115">If you want to test global administrator account protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>

  
> [!NOTE]
> <span data-ttu-id="721c9-116">Testing Global Administrator account Protection non richiede l'ambiente di testing dell'organizzazione simulata, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per un servizio di dominio Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="721c9-116">Testing global administrator account protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="721c9-117">Viene fornito come opzione in modo che sia possibile testare la protezione degli account amministratore globale e sperimentarla in un ambiente che rappresenta un'organizzazione tipica.</span><span class="sxs-lookup"><span data-stu-id="721c9-117">It is provided here as an option so that you can test global administrator account protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-cloud-app-security-and-conditional-access-policies"></a><span data-ttu-id="721c9-118">Fase 2: configurare i criteri di protezione delle app cloud e degli accessi condizionali</span><span class="sxs-lookup"><span data-stu-id="721c9-118">Phase 2: Configure Cloud App Security and conditional access policies</span></span>

<span data-ttu-id="721c9-119">Per prima cosa, creare un criterio di sicurezza per l'applicazione cloud di Office 365 per monitorare l'attività dell'account amministratore globale e inviare avvisi all'indirizzo di posta elettronica dell'account di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="721c9-119">First, create an Office 365 Cloud App Security policy to monitor global administrator account activity and send alerts to the email address of your global administrator account.</span></span> 

1. <span data-ttu-id="721c9-120">Accedere al [portale Office 365 Security _AMP_ Compliance](https://protection.office.com/) utilizzando l'account di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="721c9-120">Sign in to the [Office 365 Security & Compliance portal](https://protection.office.com/) using your global administrator account.</span></span>
2. <span data-ttu-id="721c9-121">Nel riquadro di spostamento a sinistra fare clic su **Avvisi > Gestisci gli avvisi avanzati**.</span><span class="sxs-lookup"><span data-stu-id="721c9-121">In the left navigation pane, click **Alerts > Manage advanced alerts**.</span></span>
3. <span data-ttu-id="721c9-122">Nella pagina **Gestisci gli avvisi avanzati**, fare clic su **Attiva Office 365 Cloud App Security**, quindi fare clic su **Vai a Office 365 Cloud App Security**.</span><span class="sxs-lookup"><span data-stu-id="721c9-122">On the **Manage advanced alerts** page, click **Turn on Office 365 Cloud App Security**, and then click **Go to Office 365 Cloud App Security**.</span></span>
4. <span data-ttu-id="721c9-123">Nella nuova scheda **Dashboard**, fare clic su **Controllo > Criteri**.</span><span class="sxs-lookup"><span data-stu-id="721c9-123">On the new **Dashboard** tab, click **Control > Policies**.</span></span>
5. <span data-ttu-id="721c9-124">Nella pagina **Criterio**, fare clic su **Crea criterio**, quindi fare clic su **Criteri attività**.</span><span class="sxs-lookup"><span data-stu-id="721c9-124">On the **Policy** page, click **Create policy**, and then click **Activity policy**.</span></span>
6. <span data-ttu-id="721c9-125">In **Nome criterio**, digitare **Attività amministrativa**.</span><span class="sxs-lookup"><span data-stu-id="721c9-125">In **Policy name**, type **Administrative activity**.</span></span>
7. <span data-ttu-id="721c9-126">In **Gravità del criterio**, fare clic su **Elevata**.</span><span class="sxs-lookup"><span data-stu-id="721c9-126">In **Policy severity**, click **High**.</span></span>
8. <span data-ttu-id="721c9-127">In **Categoria**, fare clic su **Account con privilegi**.</span><span class="sxs-lookup"><span data-stu-id="721c9-127">In **Category**, click **Privileged accounts**.</span></span>
9. <span data-ttu-id="721c9-128">In **Crea filtri per il criterio**, in **Attività corrispondenti a tutti gli elementi seguenti**, fare clic su **Attività amministrativa**.</span><span class="sxs-lookup"><span data-stu-id="721c9-128">In **Create filters for the policy**, in **Activities matching all of the following**, click **Administrative activity**.</span></span>
10. <span data-ttu-id="721c9-p104">In **Avvisi**, fare clic su **Invia l'avviso come messaggio di posta elettronica**. In **A**, digitare l'indirizzo di posta elettronica dell'account di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="721c9-p104">In **Alerts**, click **Send alert as email**. In **To**, type the email address of your global administrator account.</span></span>
11. <span data-ttu-id="721c9-131">Nella parte inferiore della pagina fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="721c9-131">At the bottom of the page, click **Create**.</span></span>
12. <span data-ttu-id="721c9-132">Chiudere la scheda **Dashboard** .</span><span class="sxs-lookup"><span data-stu-id="721c9-132">Close the **Dashboard** tab.</span></span>
    
<span data-ttu-id="721c9-133">Successivamente, creare un nuovo account utente come amministratore globale dedicato.</span><span class="sxs-lookup"><span data-stu-id="721c9-133">Next, create a new user account as a dedicated global administrator.</span></span>

1. <span data-ttu-id="721c9-134">In una scheda separata, aprire l'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="721c9-134">On a separate tab, open the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span>
2. <span data-ttu-id="721c9-135">In **utenti attivi**fare clic su **Aggiungi utente**.</span><span class="sxs-lookup"><span data-stu-id="721c9-135">Under **Active users**, click **Add a user**.</span></span>
3. <span data-ttu-id="721c9-136">Nella pagina **nuovo utente** , digitare **DedicatedAdmin** in **nome**, **nome visualizzato**e nome **utente**.</span><span class="sxs-lookup"><span data-stu-id="721c9-136">On the **New user** page, type **DedicatedAdmin** in **First name**, **Display name**, and **Username**.</span></span>
4. <span data-ttu-id="721c9-137">Fare clic su **password**, fare clic su **fammi creare la password**e quindi digitare una password complessa.</span><span class="sxs-lookup"><span data-stu-id="721c9-137">Click **Password**, click **Let me create the password**, and then type a strong password.</span></span> <span data-ttu-id="721c9-138">Registrare la password per il nuovo account in una posizione sicura.</span><span class="sxs-lookup"><span data-stu-id="721c9-138">Record the password for this new account in a secure location.</span></span>
5. <span data-ttu-id="721c9-139">Cancellare **fare in modo che l'utente modifichi la password al primo accesso**.</span><span class="sxs-lookup"><span data-stu-id="721c9-139">Clear **Make this user change their password when they first sign in**.</span></span>
6. <span data-ttu-id="721c9-140">Fare clic su **ruoli**, quindi su **amministratore globale**.</span><span class="sxs-lookup"><span data-stu-id="721c9-140">Click **Roles**, and then click **Global administrator**.</span></span>
7. <span data-ttu-id="721c9-141">Fare clic su **licenze di prodotto**e quindi accendere le licenze **Enterprise Mobility + Security e5** e **Office 365 Enterprise E5** .</span><span class="sxs-lookup"><span data-stu-id="721c9-141">Click **Product licenses**, and then turn the **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5 licenses** on.</span></span>
8. <span data-ttu-id="721c9-142">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="721c9-142">Click **Add**.</span></span>
9. <span data-ttu-id="721c9-143">Nella **pagina utente è stata aggiunta**l'opzione **Invia password tramite posta elettronica**e quindi fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="721c9-143">On the **User was added page**, clear **Send password in email**, and then click **Close**.</span></span>

<span data-ttu-id="721c9-144">Successivamente, creare un nuovo gruppo denominato GlobalAdmins e aggiungere l'account di DedicatedAdmin.</span><span class="sxs-lookup"><span data-stu-id="721c9-144">Next, create a new group named GlobalAdmins and add the DedicatedAdmin account to it.</span></span>

1. <span data-ttu-id="721c9-145">Nella scheda interfaccia di **amministrazione di Microsoft 365** fare clic sull'icona gruppi nel riquadro di spostamento a sinistra, quindi fare clic su **gruppi**.</span><span class="sxs-lookup"><span data-stu-id="721c9-145">On the **Microsoft 365 admin center** tab, click the groups icon in the left navigation, and then click **Groups**.</span></span>
2. <span data-ttu-id="721c9-146">Fare clic su **Aggiungi gruppo**.</span><span class="sxs-lookup"><span data-stu-id="721c9-146">Click **Add a group**.</span></span>
3. <span data-ttu-id="721c9-147">Nella pagina **nuovo gruppo** digitare **GlobalAdmins**.</span><span class="sxs-lookup"><span data-stu-id="721c9-147">On the **New Group** page, type **GlobalAdmins**.</span></span>
4. <span data-ttu-id="721c9-148">Fare clic su **Seleziona proprietario** fare clic sull'account amministratore globale, quindi fare clic su **Aggiungi > Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="721c9-148">Click **Select owner** click your global administrator account, and then click **Add > Close**.</span></span>
5. <span data-ttu-id="721c9-149">Nell'elenco dei gruppi fare clic sul gruppo **GlobalAdmins** .</span><span class="sxs-lookup"><span data-stu-id="721c9-149">In the list of groups, click the **GlobalAdmins** group.</span></span>
6. <span data-ttu-id="721c9-150">Nella pagina **GlobalAdmins** fare clic su **modifica per membro**, quindi fare clic su **Aggiungi membri**.</span><span class="sxs-lookup"><span data-stu-id="721c9-150">On the **GlobalAdmins** page, click **Edit for Member**, and then click **Add members**.</span></span>
7. <span data-ttu-id="721c9-151">Nell'elenco, fare clic sull'account **DedicatedAdmin** , quindi fare clic su **Salva _GT_ Close _GT_ Close > Admin Center**.</span><span class="sxs-lookup"><span data-stu-id="721c9-151">In the list, click the **DedicatedAdmin** account, and then click **Save > Close > Close > Admin center**.</span></span>

<span data-ttu-id="721c9-152">Successivamente, creare criteri di accesso condizionale per richiedere l'autenticazione a più fattori per gli account di amministratore globale e negare l'autenticazione se il rischio di ingresso è medio o elevato.</span><span class="sxs-lookup"><span data-stu-id="721c9-152">Next, create conditional access policies to require multifactor authentication for global administrator accounts and to deny authentication if the sign-in risk is medium or high.</span></span>

<span data-ttu-id="721c9-153">Questo primo criterio richiede che tutti gli account di amministratore globale utilizzino AMF.</span><span class="sxs-lookup"><span data-stu-id="721c9-153">This first policy requires that all global administrator accounts use MFA.</span></span>

1. <span data-ttu-id="721c9-154">In una nuova scheda del browser, passare a [https://portal.azure.com](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="721c9-154">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="721c9-155">Fare clic su **accesso condizionale di Azure Active Directory >**.</span><span class="sxs-lookup"><span data-stu-id="721c9-155">Click **Azure Active Directory > Conditional access**.</span></span>
3. <span data-ttu-id="721c9-156">Nel pannello **criteri di accesso condizionale** fare clic su **criteri di base: richiedere l'autenticazione master per gli amministratori (anteprima)**.</span><span class="sxs-lookup"><span data-stu-id="721c9-156">On the **Conditional access – Policies** blade, click **Baseline policy: Require MFA for admins (preview)**.</span></span>
4. <span data-ttu-id="721c9-157">Nei **criteri di base...**</span><span class="sxs-lookup"><span data-stu-id="721c9-157">On the **Baseline policies…**</span></span> <span data-ttu-id="721c9-158">Blade, fare clic su **Use Policy immediatamente _GT_ Save**.</span><span class="sxs-lookup"><span data-stu-id="721c9-158">blade, click **Use policy immediately > Save**.</span></span>

<span data-ttu-id="721c9-159">Questo secondo criterio blocca l'accesso all'autenticazione dell'account amministratore globale quando il rischio di ingresso è medio o elevato.</span><span class="sxs-lookup"><span data-stu-id="721c9-159">This second policy blocks access to global administrator account authentication when the sign-in risk is medium or high.</span></span>

1. <span data-ttu-id="721c9-160">Nel pannello **criteri di accesso condizionale** fare clic su **nuovo criterio**.</span><span class="sxs-lookup"><span data-stu-id="721c9-160">On the **Conditional access – Policies** blade, click **New policy**.</span></span>
2. <span data-ttu-id="721c9-161">Nel **nuovo** Blade, digitare **Global Administrators** in **Name**.</span><span class="sxs-lookup"><span data-stu-id="721c9-161">On the **New** blade, type **Global administrators** in **Name**.</span></span>
3. <span data-ttu-id="721c9-162">Nella sezione **assegnazioni** fare clic su **utenti e gruppi**.</span><span class="sxs-lookup"><span data-stu-id="721c9-162">In the **Assignments** section, click **Users and groups**.</span></span>
4. <span data-ttu-id="721c9-163">Nella scheda **Includi** del Blade **utenti e gruppi** fare clic su **Seleziona utenti e gruppi _GT_ utenti e gruppi > seleziona**.</span><span class="sxs-lookup"><span data-stu-id="721c9-163">On the **Include** tab of the **Users and groups** blade, click **Select users and groups > Users and groups > Select**.</span></span>
5. <span data-ttu-id="721c9-164">Nel pannello **Seleziona** , fare clic sul **GlobalAdmins _GT_ selezionare > fatto**.</span><span class="sxs-lookup"><span data-stu-id="721c9-164">On the **Select** blade, click the **GlobalAdmins > Select > Done**.</span></span>
6. <span data-ttu-id="721c9-165">Nella sezione **assegnazioni** fare clic su **condizioni**.</span><span class="sxs-lookup"><span data-stu-id="721c9-165">In the **Assignments** section, click **Conditions**.</span></span>
7. <span data-ttu-id="721c9-166">Nel pannello **condizioni** fare clic su **rischio di accesso**, fare clic **su Sì** per **Configura**, fare clic su **alto** e **medio**, quindi fare clic su **Seleziona** e **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="721c9-166">On the **Conditions** blade, click **Sign-in risk**, click **Yes** for **Configure**, click **High** and **Medium**, and then click **Select** and **Done**.</span></span>
8. <span data-ttu-id="721c9-167">Nella sezione **controlli di accesso** del **nuovo** Blade, fare clic su **Grant**.</span><span class="sxs-lookup"><span data-stu-id="721c9-167">In the **Access controls** section of the **New** blade, click **Grant**.</span></span>
9. <span data-ttu-id="721c9-168">Sul Blade **Grant** , fare clic su **Blocca accesso**, quindi fare clic su **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="721c9-168">On the **Grant** blade, click **Block access**, and then click **Select**.</span></span>
10. <span data-ttu-id="721c9-169">Nel **nuovo** Blade, fare clic **su** **attiva per abilitare il criterio**, quindi fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="721c9-169">On the **New** blade, click **On** for **Enable policy**, and then click **Create**.</span></span>
11. <span data-ttu-id="721c9-170">Chiudere le schede di interfaccia di amministrazione di **Azure Portal** e **Microsoft 365** .</span><span class="sxs-lookup"><span data-stu-id="721c9-170">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="721c9-171">Per testare il primo criterio, disconnettersi e accedere con l'account DedicatedAdmin.</span><span class="sxs-lookup"><span data-stu-id="721c9-171">To test the first policy, sign out and sign in with the DedicatedAdmin account.</span></span> <span data-ttu-id="721c9-172">È necessario che venga richiesto di configurare l'autenticazione master nell'account utente.</span><span class="sxs-lookup"><span data-stu-id="721c9-172">You should be prompted to configure MFA on the user account.</span></span> <span data-ttu-id="721c9-173">Questo dimostra che il primo criterio viene applicato.</span><span class="sxs-lookup"><span data-stu-id="721c9-173">This demonstrates that the first policy is being applied.</span></span>

<span data-ttu-id="721c9-174">Vedere il passaggio [Proteggi account amministratore globale](identity-designate-protect-admin-accounts.md#identity-global-admin) nella fase di identità per informazioni e collegamenti per proteggere gli account di amministratore globale in produzione.</span><span class="sxs-lookup"><span data-stu-id="721c9-174">See the [Protect global administrator accounts](identity-designate-protect-admin-accounts.md#identity-global-admin) step in the Identity phase for information and links to protect your global administrator accounts in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="721c9-175">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="721c9-175">Next step</span></span>

<span data-ttu-id="721c9-176">Esplorare altre caratteristiche e funzionalità [identità](m365-enterprise-test-lab-guides.md#identity) nell'ambiente di test.</span><span class="sxs-lookup"><span data-stu-id="721c9-176">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="721c9-177">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="721c9-177">See also</span></span>

[<span data-ttu-id="721c9-178">Fase 2: identità</span><span class="sxs-lookup"><span data-stu-id="721c9-178">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="721c9-179">Guide al lab di test di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="721c9-179">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="721c9-180">Distribuzione di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="721c9-180">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="721c9-181">Documentazione di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="721c9-181">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
