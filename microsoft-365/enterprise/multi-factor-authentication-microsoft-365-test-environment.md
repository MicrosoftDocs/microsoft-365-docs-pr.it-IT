---
title: Microsoft 365 per l'autenticazione a più fattori dell'ambiente di testing dell'organizzazione
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
- seo-marvel-apr2020
description: Configurare l'autenticazione a più fattori tramite messaggi di testo inviati a uno Smart Phone nell'ambiente di testing di Microsoft 365 per l'organizzazione.
ms.openlocfilehash: 4ed50d37e0f4e73d5d1fc62e295df374c61b9786
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686275"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="4779a-103">Autenticazione a più fattori per l'ambiente di testing di Microsoft 365 per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="4779a-103">Multi-factor authentication for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="4779a-104">*Questa guida del laboratorio di testing può essere utilizzata per ambienti di testing Microsoft 365 per Enterprise e Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="4779a-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="4779a-105">Per un ulteriore livello di sicurezza per l'accesso a Microsoft 365 o qualsiasi servizio o applicazione che utilizza il tenant di Azure AD per l'abbonamento, è possibile abilitare l'autenticazione a più fattori di Azure, che richiede più di un semplice nome utente e una password per verificare un account.</span><span class="sxs-lookup"><span data-stu-id="4779a-105">For an additional level of security for signing in to Microsoft 365 or any service or application that uses the Azure AD tenant for your subscription, you can enable Azure multi-factor authentication, which requires more than just a username and password to verify an account.</span></span> 

<span data-ttu-id="4779a-106">Con l'autenticazione a più fattori, agli utenti viene richiesto di riconoscere una telefonata, digitare un codice di verifica inviato in un messaggio di testo oppure verificare l'autenticazione con un'app nei rispettivi smartphone dopo aver inserito correttamente le password.</span><span class="sxs-lookup"><span data-stu-id="4779a-106">With multi-factor authentication, users are required to acknowledge a phone call, type a verification code sent in a text message, or verify the authentication with an app on their smart phones after correctly entering their passwords.</span></span> <span data-ttu-id="4779a-107">L'accesso è consentito solo dopo che un secondo fattore di autenticazione viene soddisfatto.</span><span class="sxs-lookup"><span data-stu-id="4779a-107">They can sign in only after this second authentication factor has been satisfied.</span></span> 
  
<span data-ttu-id="4779a-108">In questo articolo viene descritto come abilitare e testare l'autenticazione basata su messaggi di testo per un account utente specifico.</span><span class="sxs-lookup"><span data-stu-id="4779a-108">This article describes how to enable and test text message-based authentication for a specific user account.</span></span>
  
<span data-ttu-id="4779a-109">Sono disponibili due fasi per configurare l'autenticazione a più fattori per un account nell'ambiente di testing di Microsoft 365 per l'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="4779a-109">There are two phases to setting up multi-factor authentication for an account in your Microsoft 365 for enterprise test environment:</span></span>
  
1. <span data-ttu-id="4779a-110">Creare l'ambiente di testing di Microsoft 365 per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4779a-110">Create the Microsoft 365 for enterprise test environment.</span></span>
    
2. <span data-ttu-id="4779a-111">Abilitare e testare l'autenticazione a più fattori per l'account User 2.</span><span class="sxs-lookup"><span data-stu-id="4779a-111">Enable and test multi-factor authentication for the User 2 account.</span></span>

3. <span data-ttu-id="4779a-112">Abilitare e testare l'autenticazione a più fattori con un criterio di accesso condizionale (facoltativo).</span><span class="sxs-lookup"><span data-stu-id="4779a-112">Enable and test multi-factor authentication with a conditional access policy (optional).</span></span>

![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="4779a-114">Accedere a [stack di guida del laboratorio di testing](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) per visualizzare una mappa visiva in tutti gli articoli della guida del laboratorio di testing di Microsoft 365 per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4779a-114">Go to [Test Lab Guide Stack](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="4779a-115">Fase 1: creare l'ambiente di testing di Microsoft 365 per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="4779a-115">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="4779a-116">Se si desidera testare l'autenticazione a più fattori in modo semplice con i requisiti minimi, seguire le istruzioni contenute in [Lightweight base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="4779a-116">If you just want to test multi-factor authentication in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="4779a-117">Se si desidera testare l'autenticazione a più fattori in un'azienda simulata, seguire le istruzioni riportate nell' [autenticazione pass-through](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="4779a-117">If you want to test multi-factor authentication in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="4779a-118">Se si verifica l'autenticazione a più fattori, non è necessario l'ambiente di testing dell'organizzazione simulata, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per una foresta di servizi di dominio Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="4779a-118">Testing multi-factor authentication does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="4779a-119">Questo test viene fornito qui come opzione in modo per consentire di testare l’autenticazione a più fattori e sperimentarla in un ambiente che rappresenta un'organizzazione tipica.</span><span class="sxs-lookup"><span data-stu-id="4779a-119">It is provided here as an option so that you can test multi-factor authentication and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a><span data-ttu-id="4779a-120">Fase 2: Abilitare e testare l'autenticazione a più fattori per l'account User 2</span><span class="sxs-lookup"><span data-stu-id="4779a-120">Phase 2: Enable and test multi-factor authentication for the User 2 account</span></span>

<span data-ttu-id="4779a-121">Abilitare l'autenticazione a più fattori per l'account User 2 procedendo nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="4779a-121">Enable multi-factor authentication for the User 2 account with these steps:</span></span>
  
1. <span data-ttu-id="4779a-122">Aprire un'istanza separata, privata del browser, accedere all'interfaccia di amministrazione di Microsoft 365 ( [https://portal.microsoft.com](https://portal.microsoft.com) ) e quindi accedere con l'account di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="4779a-122">Open a separate, private instance of your browser, go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)), and then sign in with your global administrator account.</span></span>
    
2. <span data-ttu-id="4779a-123">Nel riquadro di spostamento sinistro fare clic su **Utenti > Utenti attivi**.</span><span class="sxs-lookup"><span data-stu-id="4779a-123">In the left navigation, click **Users > Active users**.</span></span>
    
3. <span data-ttu-id="4779a-124">Nel riquadro utenti attivi fare clic su **autenticazione**a più fattori.</span><span class="sxs-lookup"><span data-stu-id="4779a-124">In the Active users pane, click **Multi-factor authentication**.</span></span>
    
4. <span data-ttu-id="4779a-125">Nell'elenco, selezionare l'account **User 2** .</span><span class="sxs-lookup"><span data-stu-id="4779a-125">In the list, select the **User 2** account.</span></span>
    
5. <span data-ttu-id="4779a-126">Nella sezione **User 2**, sotto **Azioni rapide**, fare clic su **Abilita**.</span><span class="sxs-lookup"><span data-stu-id="4779a-126">In the **User 2** section, under **Quick steps**, click **Enable**.</span></span>
    
6. <span data-ttu-id="4779a-127">Nella finestra di dialogo **Informazioni sull'abilitazione dell'autenticazione più fattori** fare clic su **Abilita Multi-Factor Auth**.</span><span class="sxs-lookup"><span data-stu-id="4779a-127">In the **About enabling multi-factor auth** dialog box, click **Enable multi-factor auth**.</span></span>
    
7. <span data-ttu-id="4779a-128">Nella finestra di dialogo **aggiornamenti con esito positivo** fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="4779a-128">In the **Updates successful** dialog box, click **Close**.</span></span>
    
8. <span data-ttu-id="4779a-129">Nella scheda dell'interfaccia di **amministrazione di Microsoft 365** fare clic sull'icona dell'account utente in alto a destra, quindi fare clic su **Esci**.</span><span class="sxs-lookup"><span data-stu-id="4779a-129">On the **Microsoft 365 admin center** tab, click the user account icon in the upper right, and then click **Sign out**.</span></span>
    
9. <span data-ttu-id="4779a-130">Chiudere l'istanza del browser.</span><span class="sxs-lookup"><span data-stu-id="4779a-130">Close your browser instance.</span></span>
   
<span data-ttu-id="4779a-131">Completare la configurazione dell'account User 2 per utilizzare un messaggio di testo per la convalida e testarla con questa procedura:</span><span class="sxs-lookup"><span data-stu-id="4779a-131">Complete the configuration for the User 2 account to use a text message for validation and test it with these steps:</span></span>
  
1. <span data-ttu-id="4779a-132">Aprire una nuova istanza privata del browser.</span><span class="sxs-lookup"><span data-stu-id="4779a-132">Open a new, private instance of your browser.</span></span>
    
2. <span data-ttu-id="4779a-133">Accedere all'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com) e accedere con il nome e la password dell'account utente 2.</span><span class="sxs-lookup"><span data-stu-id="4779a-133">Go to the [Microsoft 365 admin center](https://admin.microsoft.com) and sign in with the User 2 account name and password.</span></span>
    
3. <span data-ttu-id="4779a-134">Dopo aver eseguito l'accesso, viene richiesto di configurare l'account per ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="4779a-134">After signing in, you are prompted to set up the account for more information.</span></span> <span data-ttu-id="4779a-135">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="4779a-135">Click **Next**.</span></span>
    
4. <span data-ttu-id="4779a-136">Nella pagina **Verifica aggiuntiva di sicurezza**:</span><span class="sxs-lookup"><span data-stu-id="4779a-136">On the **Additional security verification** page:</span></span>
    
   - <span data-ttu-id="4779a-137">Selezionare il paese o l'area geografica.</span><span class="sxs-lookup"><span data-stu-id="4779a-137">Select your country or region.</span></span>
    
   - <span data-ttu-id="4779a-138">Digitare il numero di telefono dello smartphone che riceverà i messaggi di testo.</span><span class="sxs-lookup"><span data-stu-id="4779a-138">Type phone number of the smart phone that will receive text messages.</span></span>
    
   - <span data-ttu-id="4779a-139">In **Metodo**, fare clic su **Inviami un codice tramite messaggio di testo**.</span><span class="sxs-lookup"><span data-stu-id="4779a-139">In **Method**, click **Send me a code by text message**.</span></span>
    
5. <span data-ttu-id="4779a-140">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="4779a-140">Click **Next**.</span></span>
    
6. <span data-ttu-id="4779a-141">Immettere il codice di verifica del messaggio di testo ricevuto sullo smartphone e quindi fare clic su **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="4779a-141">Enter the verification code from the text message received on your smart phone, and then click **Verify**.</span></span>
    
7. <span data-ttu-id="4779a-142">Nella pagina **passaggio 3: mantenere le applicazioni esistenti** , fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="4779a-142">On the **Step 3: Keep your existing applications** page, click **Done**.</span></span>
    
8. <span data-ttu-id="4779a-p104">Se è la prima volta che si accede con l'account User 2, viene richiesto di modificare la password. Digitare la password originale e una nuova password due volte, quindi fare clic su **Aggiornare la password ed eseguire l'accesso**. Annotare nome e password in una posizione sicura.</span><span class="sxs-lookup"><span data-stu-id="4779a-p104">If this is the first time you signed in with the User 2 account, you are prompted to change the password. Type the original password and a new password twice, and then click **Update password and sign in**. Record the new password in a secure location.</span></span>
    
    <span data-ttu-id="4779a-146">Verrà visualizzato il portale di Office per l'utente 2 nella scheda **Microsoft Office Home** del browser.</span><span class="sxs-lookup"><span data-stu-id="4779a-146">You should see the Office portal for User 2 on the **Microsoft Office Home** tab of your browser.</span></span>

## <a name="phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy"></a><span data-ttu-id="4779a-147">Fase 3: abilitare e testare l'autenticazione a più fattori con un criterio di accesso condizionale</span><span class="sxs-lookup"><span data-stu-id="4779a-147">Phase 3: Enable and test multi-factor authentication with a conditional access policy</span></span>

<span data-ttu-id="4779a-148">*Questa fase può essere utilizzata solo per un ambiente di testing di Microsoft 365 per l'organizzazione.*</span><span class="sxs-lookup"><span data-stu-id="4779a-148">*This phase can only be used for a Microsoft 365 for enterprise test environment.*</span></span>

<span data-ttu-id="4779a-149">In questa fase è possibile abilitare l'autenticazione a più fattori per l'account User 3 utilizzando un gruppo e un criterio di accesso condizionale.</span><span class="sxs-lookup"><span data-stu-id="4779a-149">In this phase you enable multi-factor authentication for the User 3 account using a group and a conditional access policy.</span></span>

<span data-ttu-id="4779a-150">Successivamente, creare un nuovo gruppo denominato MFAUsers e aggiungere l'account User 3.</span><span class="sxs-lookup"><span data-stu-id="4779a-150">Next, create a new group named MFAUsers and add the User 3 account to it.</span></span>

1. <span data-ttu-id="4779a-151">Nella scheda interfaccia di **amministrazione di Microsoft 365** fare clic su **gruppi** nel riquadro di spostamento sinistro e quindi su **gruppi**.</span><span class="sxs-lookup"><span data-stu-id="4779a-151">On the **Microsoft 365 admin center** tab, click **Groups** in the left navigation, and then click **Groups**.</span></span>
2. <span data-ttu-id="4779a-152">Fare clic su **Aggiungi gruppo**.</span><span class="sxs-lookup"><span data-stu-id="4779a-152">Click **Add a group**.</span></span>
3. <span data-ttu-id="4779a-153">Nel riquadro **scegliere un tipo di gruppo** selezionare **sicurezza**e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="4779a-153">In the **Choose a group type** pane, select **Security**, and then click **Next**.</span></span>
4. <span data-ttu-id="4779a-154">Nel riquadro **Configura le nozioni di base** fare clic su **Crea gruppo**e quindi fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="4779a-154">In the **Set up the basics** pane, click **Create group**, and then click **Close**.</span></span>
5. <span data-ttu-id="4779a-155">Nel riquadro **revisione e termina aggiunta gruppo** digitare **MFAUsers**e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="4779a-155">In the **Review and finish adding group** pane, type **MFAUsers**, and then click **Next**.</span></span>
6. <span data-ttu-id="4779a-156">Nell'elenco dei gruppi fare clic sul gruppo **MFAUsers** .</span><span class="sxs-lookup"><span data-stu-id="4779a-156">In the list of groups, click the **MFAUsers** group.</span></span>
7. <span data-ttu-id="4779a-157">Nel riquadro **MFAUsers** , fare clic su **membri**, quindi fare clic su **Visualizza tutti e Gestisci membri**.</span><span class="sxs-lookup"><span data-stu-id="4779a-157">In the **MFAUsers** pane, click **Members**, and then click **View all and manage members**.</span></span>
8. <span data-ttu-id="4779a-158">Nel riquadro **MFAUsers** , fare clic su **Aggiungi membri**, selezionare l'account **User 3** e quindi fare clic su **Salva > Chiudi > Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="4779a-158">In the **MFAUsers** pane, click **Add members**, select the **User 3** account, and then click **Save > Close > Close**.</span></span>

<span data-ttu-id="4779a-159">Successivamente, creare un criterio di accesso condizionale per richiedere l'autenticazione a più fattori per i membri del gruppo MFAUsers.</span><span class="sxs-lookup"><span data-stu-id="4779a-159">Next, create a conditional access policy to require multifactor authentication for members of the MFAUsers group.</span></span>

1. <span data-ttu-id="4779a-160">In una nuova scheda del browser, passare a [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="4779a-160">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="4779a-161">Fare clic su **Azure Active Directory > sicurezza > accesso condizionale**.</span><span class="sxs-lookup"><span data-stu-id="4779a-161">Click **Azure Active Directory > Security > Conditional Access**.</span></span>
3. <span data-ttu-id="4779a-162">Nel riquadro **criteri di accesso condizionale** fare clic su **nuovo criterio**.</span><span class="sxs-lookup"><span data-stu-id="4779a-162">In the **Conditional access – Policies** pane, click **New policy**.</span></span>
4. <span data-ttu-id="4779a-163">Nel **nuovo** riquadro, digitare **AMF per gli account utente** in **nome**.</span><span class="sxs-lookup"><span data-stu-id="4779a-163">In the **New** pane, type **MFA for user accounts** in **Name**.</span></span>
5. <span data-ttu-id="4779a-164">Nella sezione **assegnazioni** fare clic su **utenti e gruppi**.</span><span class="sxs-lookup"><span data-stu-id="4779a-164">In the **Assignments** section, click **Users and groups**.</span></span>
6. <span data-ttu-id="4779a-165">Nella scheda **Includi** del riquadro **utenti e gruppi** fare clic su **Seleziona utenti e gruppi > utenti e gruppi > selezionare**.</span><span class="sxs-lookup"><span data-stu-id="4779a-165">On the **Include** tab of the **Users and groups** pane, click **Select users and groups > Users and groups > Select**.</span></span>
7. <span data-ttu-id="4779a-166">Nel riquadro **Seleziona** fare clic sul gruppo **MFAUsers** e quindi fare clic su **Seleziona > operazione completata**.</span><span class="sxs-lookup"><span data-stu-id="4779a-166">In the **Select** pane, click the **MFAUsers** group, and then click **Select > Done**.</span></span>
8. <span data-ttu-id="4779a-167">Nella sezione **controlli di accesso** del **nuovo** riquadro fare clic su **Concedi**.</span><span class="sxs-lookup"><span data-stu-id="4779a-167">In the **Access controls** section of the **New** pane, click **Grant**.</span></span>
9. <span data-ttu-id="4779a-168">Nel riquadro **Concedi** , fare clic su **Richiedi autenticazione**a più fattori, quindi fare clic su **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="4779a-168">In the **Grant** pane, click **Require multi-factor authentication**, and then click **Select**.</span></span>
10. <span data-ttu-id="4779a-169">Nel **nuovo** riquadro, fare clic **su** attiva per **abilitare il criterio**, quindi fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="4779a-169">In the **New** pane, click **On** for **Enable policy**, and then click **Create**.</span></span>
11. <span data-ttu-id="4779a-170">Chiudere le schede di interfaccia di amministrazione di **Azure Portal** e **Microsoft 365** .</span><span class="sxs-lookup"><span data-stu-id="4779a-170">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="4779a-171">Per testare questo criterio, disconnettersi e accedere con l'account User 3.</span><span class="sxs-lookup"><span data-stu-id="4779a-171">To test this policy, sign out and sign in with the User 3 account.</span></span> <span data-ttu-id="4779a-172">È necessario che venga richiesto di configurare l'autenticazione master.</span><span class="sxs-lookup"><span data-stu-id="4779a-172">You should be prompted to configure MFA.</span></span> <span data-ttu-id="4779a-173">Questo dimostra che è in corso l'applicazione del criterio MFAUsers.</span><span class="sxs-lookup"><span data-stu-id="4779a-173">This demonstrates that the MFAUsers policy is being applied.</span></span>

## <a name="next-step"></a><span data-ttu-id="4779a-174">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="4779a-174">Next step</span></span>

<span data-ttu-id="4779a-175">Esplorare altre caratteristiche e funzionalità [identità](m365-enterprise-test-lab-guides.md#identity) nell'ambiente di test.</span><span class="sxs-lookup"><span data-stu-id="4779a-175">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="4779a-176">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4779a-176">See also</span></span>

[<span data-ttu-id="4779a-177">Roadmap dell'identità</span><span class="sxs-lookup"><span data-stu-id="4779a-177">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="4779a-178">Guide ai lab di test di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="4779a-178">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="4779a-179">Panoramica di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="4779a-179">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="4779a-180">Microsoft 365 per la documentazione relativa all'organizzazione</span><span class="sxs-lookup"><span data-stu-id="4779a-180">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
