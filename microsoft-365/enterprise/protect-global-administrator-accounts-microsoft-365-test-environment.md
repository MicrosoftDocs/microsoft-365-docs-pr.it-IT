---
title: Proteggere gli account di amministratore globale nell'ambiente di test Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- TLG
- Ent_TLGs
description: Utilizzare la procedura seguente per proteggere gli account di amministratore globale nell'ambiente di test Microsoft 365 aziendale.
ms.openlocfilehash: 4d444e217c5a232811701f6519c2eb3ebe86df70
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2019
ms.locfileid: "26868302"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="58106-103">Proteggere gli account di amministratore globale nell'ambiente di test Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="58106-103">Protect global administrator accounts in your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="58106-p101">È possibile impedire attacchi di tipo digitale nella propria organizzazione per garantire che l'account amministratore siano la massima protezione. In questo articolo viene descritto come utilizzare criteri di accesso condizionale sicurezza App Cloud di Office 365 e Azure Active Directory per proteggere gli account di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="58106-p101">You can prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible. This article describes how to use Office 365 Cloud App Security and Azure AD conditional access policies to protect global administrator accounts.</span></span>

<span data-ttu-id="58106-106">Esistono due fasi di proteggere gli account di amministratore globale nell'ambiente di test Microsoft 365 aziendale:</span><span class="sxs-lookup"><span data-stu-id="58106-106">There are two phases to protecting global administrator accounts in your Microsoft 365 Enterprise test environment:</span></span>

1.  <span data-ttu-id="58106-107">Creare l'ambiente di test Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="58106-107">Create the Microsoft 365 Enterprise test environment.</span></span>
2.  <span data-ttu-id="58106-108">Proteggere il tuo account amministratore globale dedicato.</span><span class="sxs-lookup"><span data-stu-id="58106-108">Protect your dedicated global administrator account.</span></span>

![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="58106-110">Fare clic [qui](https://aka.ms/m365etlgstack) per consultare una mappa di tutti gli articoli relativi alla guida al lab test di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="58106-110">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="58106-111">Fase 1: Preparare l'ambiente di testing Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="58106-111">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="58106-112">Se si desidera testare la protezione dell'account amministratore globale in un modo semplice con i requisiti minimi, seguire le istruzioni di [configurazione di base semplificata](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="58106-112">If you just want to test global administrator account protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="58106-113">Se si desidera testare la protezione dell'account amministratore globale in un'azienda simulata, seguire le istruzioni [nell'autenticazione pass-through](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="58106-113">If you want to test global administrator account protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="58106-p102">Test account amministratore globale protection non richiede l'ambiente di testing simulato enterprise, che include una rete intranet simulata connessi a Internet e la sincronizzazione delle directory per una foresta Windows Server Active Directory. Viene fornito qui come un'opzione in modo da poter testare la protezione dell'account amministratore globale e sperimentare in un ambiente che rappresenta una tipica organizzazione.</span><span class="sxs-lookup"><span data-stu-id="58106-p102">Testing global administrator account protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test global administrator account protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-cloud-app-security-and-conditional-access-policies"></a><span data-ttu-id="58106-116">Fase 2: Configurare la sicurezza di applicazione Cloud e i criteri di accesso condizionale</span><span class="sxs-lookup"><span data-stu-id="58106-116">Phase 2: Configure Cloud App Security and conditional access policies</span></span>

<span data-ttu-id="58106-117">Creare un criterio di protezione di applicazioni di Office 365 Cloud per monitorare l'attività di account amministratore globale e inviare gli avvisi per l'indirizzo di posta elettronica dell'account di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="58106-117">First, create an Office 365 Cloud App Security policy to monitor global administrator account activity and send alerts to the email address of your global administrator account.</span></span> 

1. <span data-ttu-id="58106-118">Accedere al portale di Office in [http://portal.office.com](http://portal.office.com) utilizzando l'account amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="58106-118">Sign in to the Office portal at [http://portal.office.com](http://portal.office.com) using your global administrator account.</span></span>
2. <span data-ttu-id="58106-p103">Fare clic su tessera di **amministrazione** . Nella scheda di **interfaccia di amministrazione di Office** , fare clic su **Admin Center > sicurezza e conformità**.</span><span class="sxs-lookup"><span data-stu-id="58106-p103">Click the **Admin** tile. On the **Office Admin center** tab, click **Admin centers > Security & Compliance**.</span></span>
3. <span data-ttu-id="58106-121">Nel riquadro di spostamento a sinistra fare clic su **Avvisi > Gestisci gli avvisi avanzati**.</span><span class="sxs-lookup"><span data-stu-id="58106-121">In the left navigation pane, click **Alerts > Manage advanced alerts**.</span></span>
4. <span data-ttu-id="58106-122">Nella pagina **Gestisci gli avvisi avanzati**, fare clic su **Attiva Office 365 Cloud App Security**, quindi fare clic su **Vai a Office 365 Cloud App Security**.</span><span class="sxs-lookup"><span data-stu-id="58106-122">On the **Manage advanced alerts** page, click **Turn on Office 365 Cloud App Security**, and then click **Go to Office 365 Cloud App Security**.</span></span>
5. <span data-ttu-id="58106-123">Nella nuova scheda **Dashboard**, fare clic su **Controllo > Criteri**.</span><span class="sxs-lookup"><span data-stu-id="58106-123">On the new **Dashboard** tab, click **Control > Policies**.</span></span>
6. <span data-ttu-id="58106-124">Nella pagina **Criterio**, fare clic su **Crea criterio**, quindi fare clic su **Criteri attività**.</span><span class="sxs-lookup"><span data-stu-id="58106-124">On the **Policy** page, click **Create policy**, and then click **Activity policy**.</span></span>
7. <span data-ttu-id="58106-125">In **Nome criterio**, digitare **Attività amministrativa**.</span><span class="sxs-lookup"><span data-stu-id="58106-125">In **Policy name**, type **Administrative activity**.</span></span>
8. <span data-ttu-id="58106-126">In **Gravità del criterio**, fare clic su **Elevata**.</span><span class="sxs-lookup"><span data-stu-id="58106-126">In **Policy severity**, click **High**.</span></span>
9. <span data-ttu-id="58106-127">In **Categoria**, fare clic su **Account con privilegi**.</span><span class="sxs-lookup"><span data-stu-id="58106-127">In **Category**, click **Privileged accounts**.</span></span>
10. <span data-ttu-id="58106-128">In **Crea filtri per il criterio**, in **Attività corrispondenti a tutti gli elementi seguenti**, fare clic su **Attività amministrativa**.</span><span class="sxs-lookup"><span data-stu-id="58106-128">In **Create filters for the policy**, in **Activities matching all of the following**, click **Administrative activity**.</span></span>
11. <span data-ttu-id="58106-p104">In **Avvisi**, fare clic su **Invia l'avviso come messaggio di posta elettronica**. In **A**, digitare l'indirizzo di posta elettronica dell'account di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="58106-p104">In **Alerts**, click **Send alert as email**. In **To**, type the email address of your global administrator account.</span></span>
12. <span data-ttu-id="58106-131">Nella parte inferiore della pagina fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="58106-131">At the bottom of the page, click **Create**.</span></span>
13. <span data-ttu-id="58106-132">Chiudere la scheda **del Dashboard** .</span><span class="sxs-lookup"><span data-stu-id="58106-132">Close the **Dashboard** tab.</span></span>
    
<span data-ttu-id="58106-133">Successivamente, creare un nuovo account utente come amministratore globale dedicato.</span><span class="sxs-lookup"><span data-stu-id="58106-133">Next, create a new user account as a dedicated global administrator.</span></span>

1. <span data-ttu-id="58106-134">Nella scheda di **interfaccia di amministrazione di Office** , in **utenti attivi**, fare clic su **Aggiungi utente**.</span><span class="sxs-lookup"><span data-stu-id="58106-134">On the **Office Admin center** tab, under **Active users**, click **Add a user**.</span></span>
2. <span data-ttu-id="58106-135">Nella pagina **nuovo utente** , digitare **DedicatedAdmin** in **nome**, **nome visualizzato**e **nome utente**.</span><span class="sxs-lookup"><span data-stu-id="58106-135">On the **New user** page, type **DedicatedAdmin** in **First name**, **Display name**, and **Username**.</span></span>
3. <span data-ttu-id="58106-p105">Fare clic su **Password**, fare clic su **Crea la password**e quindi digitare una password complessa. Registrare la password per il nuovo account in un luogo sicuro.</span><span class="sxs-lookup"><span data-stu-id="58106-p105">Click **Password**, click **Let me create the password**, and then type a strong password. Record the password for this new account in a secure location.</span></span>
4. <span data-ttu-id="58106-138">Deselezionare **che l'utente di modificare la password quando accedono prima**.</span><span class="sxs-lookup"><span data-stu-id="58106-138">Clear **Make this user change their password when they first sign in**.</span></span>
5. <span data-ttu-id="58106-139">Fare clic su **ruoli**e quindi fare clic su **amministratore globale**.</span><span class="sxs-lookup"><span data-stu-id="58106-139">Click **Roles**, and then click **Global administrator**.</span></span>
6. <span data-ttu-id="58106-140">Fare clic su **licenze per i prodotti**e quindi attivare la **mobilità aziendale + E5 di sicurezza** e **le licenze di Office 365 Enterprise E5** .</span><span class="sxs-lookup"><span data-stu-id="58106-140">Click **Product licenses**, and then turn the **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5 licenses** on.</span></span>
7. <span data-ttu-id="58106-141">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="58106-141">Click **Add**.</span></span>
8. <span data-ttu-id="58106-142">In **utente è stato aggiunto pagina**, deselezionare **inviare password tramite posta elettronica**e quindi fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="58106-142">On the **User was added page**, clear **Send password in email**, and then click **Close**.</span></span>

<span data-ttu-id="58106-143">Successivamente, creare un nuovo gruppo denominato GlobalAdmins e aggiungere l'account di DedicatedAdmin.</span><span class="sxs-lookup"><span data-stu-id="58106-143">Next, create a new group named GlobalAdmins and add the DedicatedAdmin account to it.</span></span>

1. <span data-ttu-id="58106-144">Nella scheda di **interfaccia di amministrazione di Office** , fare clic sull'icona gruppi nel riquadro di spostamento sinistra e quindi fare clic su **gruppi**.</span><span class="sxs-lookup"><span data-stu-id="58106-144">On the **Office Admin center** tab, click the groups icon in the left navigation, and then click **Groups**.</span></span>
2. <span data-ttu-id="58106-145">Fare clic su **Aggiungi un gruppo**.</span><span class="sxs-lookup"><span data-stu-id="58106-145">Click **Add a group**.</span></span>
3. <span data-ttu-id="58106-146">Nella pagina **Nuovo gruppo** digitare **GlobalAdmins**.</span><span class="sxs-lookup"><span data-stu-id="58106-146">On the **New Group** page, type **GlobalAdmins**.</span></span>
4. <span data-ttu-id="58106-147">Fare clic su fare clic su **Seleziona proprietario** l'account amministratore globale e quindi fare clic su **Aggiungi > Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="58106-147">Click **Select owner** click your global administrator account, and then click **Add > Close**.</span></span>
5. <span data-ttu-id="58106-148">Nell'elenco dei gruppi fare clic sul gruppo **GlobalAdmins** .</span><span class="sxs-lookup"><span data-stu-id="58106-148">In the list of groups, click the **GlobalAdmins** group.</span></span>
6. <span data-ttu-id="58106-149">Nella pagina **GlobalAdmins** , fare clic su **Modifica per membro**e quindi fare clic su **Aggiungi membri**.</span><span class="sxs-lookup"><span data-stu-id="58106-149">On the **GlobalAdmins** page, click **Edit for Member**, and then click **Add members**.</span></span>
7. <span data-ttu-id="58106-150">Nell'elenco, fare clic sull'account **DedicatedAdmin** e quindi fare clic su **salvare > Chiudi > Chiudi > Admin center**.</span><span class="sxs-lookup"><span data-stu-id="58106-150">In the list, click the **DedicatedAdmin** account, and then click **Save > Close > Close > Admin center**.</span></span>

<span data-ttu-id="58106-151">Successivamente, creare criteri di accesso condizionale per richiedere l'autenticazione a più fattori per gli account di amministratore globale e Nega l'autenticazione se il rischio di accesso è medio o elevato.</span><span class="sxs-lookup"><span data-stu-id="58106-151">Next, create conditional access policies to require multifactor authentication for global administrator accounts and to deny authentication if the sign-in risk is medium or high.</span></span>

<span data-ttu-id="58106-152">Questo criterio primo richiede che tutti gli account di amministratore globale utilizzano MFA.</span><span class="sxs-lookup"><span data-stu-id="58106-152">This first policy requires that all global administrator accounts use MFA.</span></span>

1. <span data-ttu-id="58106-153">In una nuova scheda del browser, accedere a [https://portal.azure.com](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="58106-153">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="58106-154">Fare clic su **Azure Active Directory > accesso condizionato**.</span><span class="sxs-lookup"><span data-stu-id="58106-154">Click **Azure Active Directory > Conditional access**.</span></span>
3. <span data-ttu-id="58106-155">Su blade **accesso condizionato-criteri** , fare clic su **dei criteri di base: richiedono MFA per gli amministratori (preview)**.</span><span class="sxs-lookup"><span data-stu-id="58106-155">On the **Conditional access – Policies** blade, click **Baseline policy: Require MFA for admins (preview)**.</span></span>
4. <span data-ttu-id="58106-p106">Su blade **... criteri di base** , fare clic su **utilizzare immediatamente criterio > Salva**.</span><span class="sxs-lookup"><span data-stu-id="58106-p106">On the **Baseline policies…** blade, click **Use policy immediately > Save**.</span></span>

<span data-ttu-id="58106-158">In questo secondo criterio blocca l'accesso all'autenticazione account amministratore globale quando il rischio di accesso è medio o elevato.</span><span class="sxs-lookup"><span data-stu-id="58106-158">This second policy blocks access to global administrator account authentication when the sign-in risk is medium or high.</span></span>

1. <span data-ttu-id="58106-159">Su blade **accesso condizionato-criteri** , fare clic su **nuovo criterio**.</span><span class="sxs-lookup"><span data-stu-id="58106-159">On the **Conditional access – Policies** blade, click **New policy**.</span></span>
2. <span data-ttu-id="58106-160">Blade **New** , nella **casella Nome**digitare **gli amministratori globali** .</span><span class="sxs-lookup"><span data-stu-id="58106-160">On the **New** blade, type **Global administrators** in **Name**.</span></span>
3. <span data-ttu-id="58106-161">Nella sezione **assegnazioni** , fare clic su **utenti e gruppi**.</span><span class="sxs-lookup"><span data-stu-id="58106-161">In the **Assignments** section, click **Users and groups**.</span></span>
4. <span data-ttu-id="58106-162">Nella scheda **Includi** della blade **utenti e gruppi** , fare clic su **selezionare utenti e gruppi > utenti e gruppi > selezionare**.</span><span class="sxs-lookup"><span data-stu-id="58106-162">On the **Include** tab of the **Users and groups** blade, click **Select users and groups > Users and groups > Select**.</span></span>
5. <span data-ttu-id="58106-163">Scegliere blade **Selezionare** il **GlobalAdmins > selezionare > Fine**.</span><span class="sxs-lookup"><span data-stu-id="58106-163">On the **Select** blade, click the **GlobalAdmins > Select > Done**.</span></span>
6. <span data-ttu-id="58106-164">Nella sezione **assegnazioni** , fare clic su **condizioni**.</span><span class="sxs-lookup"><span data-stu-id="58106-164">In the **Assignments** section, click **Conditions**.</span></span>
7. <span data-ttu-id="58106-165">Su blade **condizioni** , fare clic su **accesso rischio**, fare clic su **Sì** per **configurare**, fare clic su **Medium**e **High** e quindi fare clic su **Seleziona** e **Fine**.</span><span class="sxs-lookup"><span data-stu-id="58106-165">On the **Conditions** blade, click **Sign-in risk**, click **Yes** for **Configure**, click **High** and **Medium**, and then click **Select** and **Done**.</span></span>
8. <span data-ttu-id="58106-166">Nella sezione **accedere a controlli** di blade **New** , fare clic su **Concedi**.</span><span class="sxs-lookup"><span data-stu-id="58106-166">In the **Access controls** section of the **New** blade, click **Grant**.</span></span>
9. <span data-ttu-id="58106-167">Su blade **Grant** , fare clic su **bloccare l'accesso**e quindi fare clic su **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="58106-167">On the **Grant** blade, click **Block access**, and then click **Select**.</span></span>
10. <span data-ttu-id="58106-168">Su blade **New** , fare clic **su** per **abilitare i criteri**e quindi fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="58106-168">On the **New** blade, click **On** for **Enable policy**, and then click **Create**.</span></span>
11. <span data-ttu-id="58106-169">Chiudere le schede di **interfaccia di amministrazione di Office** e **portale Azure** .</span><span class="sxs-lookup"><span data-stu-id="58106-169">Close the **Azure portal** and **Office Admin center** tabs.</span></span>

<span data-ttu-id="58106-p107">Per testare il primo criterio, disconnettersi e accedere con l'account DedicatedAdmin. È necessario richiedere configurare MFA l'account utente. Dimostra che il primo criterio viene applicato.</span><span class="sxs-lookup"><span data-stu-id="58106-p107">To test the first policy, sign out and sign in with the DedicatedAdmin account. You should be prompted to configure MFA on the user account. This demonstrates that the first policy is being applied.</span></span>

<span data-ttu-id="58106-173">Nella fase di identità per informazioni e collegamenti per proteggere gli account di amministratore globale nell'ambiente di produzione, vedere la sezione [account amministratore globale di protezione](identity-designate-protect-admin-accounts.md) .</span><span class="sxs-lookup"><span data-stu-id="58106-173">See the [Protect global administrator accounts](identity-designate-protect-admin-accounts.md) step in the Identity phase for information and links to protect your global administrator accounts in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="58106-174">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="58106-174">Next step</span></span>

<span data-ttu-id="58106-175">Esplorare altre caratteristiche e funzionalità [identità](m365-enterprise-test-lab-guides.md#identity) nell'ambiente di test.</span><span class="sxs-lookup"><span data-stu-id="58106-175">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="58106-176">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="58106-176">See also</span></span>

[<span data-ttu-id="58106-177">Fase 2: identità</span><span class="sxs-lookup"><span data-stu-id="58106-177">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="58106-178">Guide al lab di test di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="58106-178">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="58106-179">Distribuzione di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="58106-179">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="58106-180">Documentazione di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="58106-180">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
