---
title: Autenticazione a più fattori dell'ambiente di testing di Microsoft 365 per le aziende
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
description: Configurare l'autenticazione a più fattori utilizzando i messaggi di testo inviati a uno smart phone nell'ambiente di testing di Microsoft 365 per le aziende.
ms.openlocfilehash: aeb8940a9499909b8c568d1230f9aa45aee07b3d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923757"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="c3bd3-103">Autenticazione a più fattori per l'ambiente di testing di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="c3bd3-103">Multi-factor authentication for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="c3bd3-104">*Questa guida al laboratorio di testing può essere usata sia per gli ambienti di testing di Microsoft 365 per le aziende che per gli ambienti di testing di Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="c3bd3-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="c3bd3-105">Per un ulteriore livello di sicurezza per l'accesso a Microsoft 365 o a qualsiasi servizio o applicazione che utilizza il tenant di Azure AD per la sottoscrizione, è possibile abilitare l'autenticazione a più fattori di Azure AD, che richiede più di un nome utente e una password per verificare un account.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-105">For an additional level of security for signing in to Microsoft 365 or any service or application that uses the Azure AD tenant for your subscription, you can enable Azure AD multi-factor authentication, which requires more than just a username and password to verify an account.</span></span>

<span data-ttu-id="c3bd3-106">Con l'autenticazione a più fattori, gli utenti devono confermare una chiamata telefonica, digitare un codice di verifica inviato in un SMS o verificare l'autenticazione con un'app sui propri smartphone dopo aver immesso correttamente le password.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-106">With multi-factor authentication, users are required to acknowledge a phone call, type a verification code sent in a text message, or verify the authentication with an app on their smart phones after correctly entering their passwords.</span></span> <span data-ttu-id="c3bd3-107">Possono accedere solo dopo che questo secondo fattore di autenticazione è soddisfatto.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-107">They can sign in only after this second authentication factor is satisfied.</span></span>
  
<span data-ttu-id="c3bd3-108">In questo articolo viene descritto come abilitare e testare l'autenticazione basata su SMS per un account utente specifico.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-108">This article describes how to enable and test text message-based authentication for a specific user account.</span></span>
  
<span data-ttu-id="c3bd3-109">La configurazione dell'autenticazione a più fattori per un account nell'ambiente di testing di Microsoft 365 per le aziende prevede due fasi e una terza fase facoltativa:</span><span class="sxs-lookup"><span data-stu-id="c3bd3-109">Setting up multi-factor authentication for an account in your Microsoft 365 for enterprise test environment involves two phases and a third optional phase:</span></span>
- [<span data-ttu-id="c3bd3-110">Fase 1: creare l'ambiente di testing di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="c3bd3-110">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="c3bd3-111">Fase 2: Abilitare e testare l'autenticazione a più fattori per l'account User 2</span><span class="sxs-lookup"><span data-stu-id="c3bd3-111">Phase 2: Enable and test multi-factor authentication for the User 2 account</span></span>](#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account)
- [<span data-ttu-id="c3bd3-112">Fase 3: abilitare e testare l'autenticazione a più fattori con un criterio di accesso condizionale</span><span class="sxs-lookup"><span data-stu-id="c3bd3-112">Phase 3: Enable and test multi-factor authentication with a conditional access policy</span></span>](#phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy)

![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="c3bd3-114">Per una mappa visiva a tutti gli articoli nello stack guida del laboratorio di testing di Microsoft 365 per le aziende, passare a [Microsoft 365 per enterprise Test Lab Guide Stack.](../downloads/Microsoft365EnterpriseTLGStack.pdf)</span><span class="sxs-lookup"><span data-stu-id="c3bd3-114">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="c3bd3-115">Fase 1: creare l'ambiente di testing di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="c3bd3-115">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="c3bd3-116">Se si desidera solo testare l'autenticazione a più fattori in modo leggero con i requisiti minimi, seguire le istruzioni in [Configurazione di base leggera](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="c3bd3-116">If you just want to test multi-factor authentication in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="c3bd3-117">Se si desidera testare l'autenticazione a più fattori in un'organizzazione simulata, seguire le istruzioni in [Autenticazione pass-through.](pass-through-auth-m365-ent-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="c3bd3-117">If you want to test multi-factor authentication in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="c3bd3-118">Il test dell'autenticazione a più fattori non richiede l'ambiente di testing aziendale simulato, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per una foresta di Servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-118">Testing multi-factor authentication does not require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="c3bd3-119">Questo test viene fornito qui come opzione in modo per consentire di testare l’autenticazione a più fattori e sperimentarla in un ambiente che rappresenta un'organizzazione tipica.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-119">It is provided here as an option so that you can test multi-factor authentication and experiment with it in an environment that represents a typical organization.</span></span>
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a><span data-ttu-id="c3bd3-120">Fase 2: Abilitare e testare l'autenticazione a più fattori per l'account User 2</span><span class="sxs-lookup"><span data-stu-id="c3bd3-120">Phase 2: Enable and test multi-factor authentication for the User 2 account</span></span>

<span data-ttu-id="c3bd3-121">Abilitare l'autenticazione a più fattori per l'account User 2 procedendo nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="c3bd3-121">Enable multi-factor authentication for the User 2 account with these steps:</span></span>
  
1. <span data-ttu-id="c3bd3-122">Aprire un'istanza privata separata del browser, passare all'interfaccia di amministrazione di Microsoft 365 ( ) e quindi accedere [https://portal.microsoft.com](https://portal.microsoft.com) con l'account di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-122">Open a separate, private instance of your browser, go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)), and then sign in with your global administrator account.</span></span>
    
2. <span data-ttu-id="c3bd3-123">Nel riquadro di spostamento sinistro selezionare **Utenti**  >  **Utenti attivi**.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-123">In the left navigation, select **Users** > **Active users**.</span></span>
    
3. <span data-ttu-id="c3bd3-124">Nel riquadro Utenti attivi selezionare **Autenticazione a più fattori.**</span><span class="sxs-lookup"><span data-stu-id="c3bd3-124">In the Active users pane, select **Multi-factor authentication**.</span></span>
    
4. <span data-ttu-id="c3bd3-125">Nell'elenco selezionare **l'account Utente 2.**</span><span class="sxs-lookup"><span data-stu-id="c3bd3-125">In the list, select the **User 2** account.</span></span>
    
5. <span data-ttu-id="c3bd3-126">Nella sezione **Utente 2,** in **Passaggi rapidi,** selezionare **Abilita.**</span><span class="sxs-lookup"><span data-stu-id="c3bd3-126">In the **User 2** section, under **Quick steps**, select **Enable**.</span></span>
    
6. <span data-ttu-id="c3bd3-127">Nella finestra **di dialogo Informazioni sull'abilitazione dell'autenticazione** a più fattori selezionare **Abilita autenticazione a più fattori.**</span><span class="sxs-lookup"><span data-stu-id="c3bd3-127">In the **About enabling multi-factor auth** dialog box, select **Enable multi-factor auth**.</span></span>
    
7. <span data-ttu-id="c3bd3-128">Nella finestra **di dialogo** Aggiornamenti riusciti selezionare **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-128">In the **Updates successful** dialog box, select **Close**.</span></span>
    
8. <span data-ttu-id="c3bd3-129">Nella scheda Interfaccia di amministrazione di **Microsoft 365** selezionare l'icona dell'account utente in alto a destra e quindi **selezionare Disconnetto**.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-129">On the **Microsoft 365 admin center** tab, select the user account icon in the upper right, and then select **Sign out**.</span></span>
    
9. <span data-ttu-id="c3bd3-130">Chiudere l'istanza del browser.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-130">Close your browser instance.</span></span>
   
<span data-ttu-id="c3bd3-131">Completare la configurazione dell'account User 2 per utilizzare un messaggio di testo per la convalida e testarla con questa procedura:</span><span class="sxs-lookup"><span data-stu-id="c3bd3-131">Complete the configuration for the User 2 account to use a text message for validation and test it with these steps:</span></span>
  
1. <span data-ttu-id="c3bd3-132">Apri una nuova istanza privata del browser.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-132">Open a new, private instance of your browser.</span></span>
    
2. <span data-ttu-id="c3bd3-133">Accedere all'interfaccia di amministrazione di [Microsoft 365](https://admin.microsoft.com) e accedere con il nome account utente 2 e la password.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-133">Go to the [Microsoft 365 admin center](https://admin.microsoft.com) and sign in with the User 2 account name and password.</span></span>
    
3. <span data-ttu-id="c3bd3-134">Dopo l'accesso, viene richiesto di configurare l'account per ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-134">After signing in, you are prompted to set up the account for more information.</span></span> <span data-ttu-id="c3bd3-135">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-135">Select **Next**.</span></span>
    
4. <span data-ttu-id="c3bd3-136">Nella pagina **Verifica aggiuntiva di sicurezza**:</span><span class="sxs-lookup"><span data-stu-id="c3bd3-136">On the **Additional security verification** page:</span></span>
    
   - <span data-ttu-id="c3bd3-137">Selezionare il paese o l'area geografica.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-137">Select your country or region.</span></span>
    
   - <span data-ttu-id="c3bd3-138">Immettere il numero di telefono dello smart phone che riceverà messaggi di testo.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-138">Enter the phone number of the smart phone that will receive text messages.</span></span>
    
   - <span data-ttu-id="c3bd3-139">In **Metodo** selezionare **Invia un codice tramite SMS.**</span><span class="sxs-lookup"><span data-stu-id="c3bd3-139">In **Method**, select **Send me a code by text message**.</span></span>
    
5. <span data-ttu-id="c3bd3-140">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-140">Select **Next**.</span></span>
    
6. <span data-ttu-id="c3bd3-141">Immetti il codice di verifica dal messaggio di testo ricevuto sullo smart phone e quindi seleziona **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-141">Enter the verification code from the text message received on your smart phone, and then select **Verify**.</span></span>
    
7. <span data-ttu-id="c3bd3-142">Nella pagina **Passaggio 3: mantenere le applicazioni esistenti** selezionare **Fatto.**</span><span class="sxs-lookup"><span data-stu-id="c3bd3-142">On the **Step 3: Keep your existing applications** page, select **Done**.</span></span>
    
8. <span data-ttu-id="c3bd3-143">Se è la prima volta che si accede con l'account User 2, viene richiesto di modificare la password.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-143">If this is the first time you signed in with the User 2 account, you are prompted to change the password.</span></span> <span data-ttu-id="c3bd3-144">Immettere la password originale e una nuova password due volte, quindi selezionare **Aggiorna password e accedi.**</span><span class="sxs-lookup"><span data-stu-id="c3bd3-144">Enter the original password and a new password twice, and then select **Update password and sign in**.</span></span> <span data-ttu-id="c3bd3-145">Annotare nome e password in una posizione sicura.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-145">Record the new password in a secure location.</span></span>
    
    <span data-ttu-id="c3bd3-146">Dovrebbe essere visualizzato il portale di Office per l'utente 2 **nella Microsoft Office Home** del browser.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-146">You should see the Office portal for User 2 on the **Microsoft Office Home** tab of your browser.</span></span>

## <a name="phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy"></a><span data-ttu-id="c3bd3-147">Fase 3: abilitare e testare l'autenticazione a più fattori con un criterio di accesso condizionale</span><span class="sxs-lookup"><span data-stu-id="c3bd3-147">Phase 3: Enable and test multi-factor authentication with a conditional access policy</span></span>

<span data-ttu-id="c3bd3-148">*Questa fase può essere utilizzata solo per un ambiente di testing di Microsoft 365 per le aziende.*</span><span class="sxs-lookup"><span data-stu-id="c3bd3-148">*This phase can only be used for a Microsoft 365 for enterprise test environment.*</span></span>

<span data-ttu-id="c3bd3-149">In questa fase, si abilita l'autenticazione a più fattori per l'account Utente 3 utilizzando un gruppo e un criterio di accesso condizionale.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-149">In this phase, you enable multi-factor authentication for the User 3 account using a group and a conditional access policy.</span></span>

<span data-ttu-id="c3bd3-150">Successivamente, crea un nuovo gruppo denominato MFAUsers e aggiungi l'account User 3.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-150">Next, create a new group named MFAUsers and add the User 3 account to it.</span></span>

1. <span data-ttu-id="c3bd3-151">Nella scheda Interfaccia di amministrazione di **Microsoft 365** selezionare **Gruppi** nel riquadro di spostamento sinistro e **quindi** gruppi .</span><span class="sxs-lookup"><span data-stu-id="c3bd3-151">On the **Microsoft 365 admin center** tab, select **Groups** in the left navigation, and then select **Groups**.</span></span>
2. <span data-ttu-id="c3bd3-152">Selezionare **Aggiungi un gruppo**.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-152">Select **Add a group**.</span></span>
3. <span data-ttu-id="c3bd3-153">Nel riquadro **Scegliere un tipo di gruppo** selezionare **Sicurezza** e quindi fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="c3bd3-153">In the **Choose a group type** pane, select **Security**, and then select **Next**.</span></span>
4. <span data-ttu-id="c3bd3-154">Nel riquadro **Configura le nozioni di** base selezionare Crea **gruppo** e quindi fare clic su **Chiudi.**</span><span class="sxs-lookup"><span data-stu-id="c3bd3-154">In the **Set up the basics** pane, select **Create group**, and then select **Close**.</span></span>
5. <span data-ttu-id="c3bd3-155">Nel riquadro **Rivedere e completare l'aggiunta del** gruppo, immettere **MFAUsers** e quindi selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="c3bd3-155">In the **Review and finish adding group** pane, enter **MFAUsers**, and then select **Next**.</span></span>
6. <span data-ttu-id="c3bd3-156">Nell'elenco dei gruppi selezionare il **gruppo MFAUsers.**</span><span class="sxs-lookup"><span data-stu-id="c3bd3-156">In the list of groups, select the **MFAUsers** group.</span></span>
7. <span data-ttu-id="c3bd3-157">Nel riquadro **MFAUsers** selezionare **Membri** e quindi **Selezionare Visualizza tutti e gestisci membri**.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-157">In the **MFAUsers** pane, select **Members**, and then select **View all and manage members**.</span></span>
8. <span data-ttu-id="c3bd3-158">Nel riquadro **MFAUsers** selezionare **Aggiungi** membri, selezionare l'account **Utente 3** e quindi selezionare **Salva**  >  **Chiudi**  >  **Chiudi.**</span><span class="sxs-lookup"><span data-stu-id="c3bd3-158">In the **MFAUsers** pane, select **Add members**, select the **User 3** account, and then select **Save** > **Close** > **Close**.</span></span>

<span data-ttu-id="c3bd3-159">Creare quindi un criterio di accesso condizionale per richiedere l'autenticazione a più fattori per i membri del gruppo MFAUsers.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-159">Next, create a conditional access policy to require multifactor authentication for members of the MFAUsers group.</span></span>

1. <span data-ttu-id="c3bd3-160">In una nuova scheda del browser passare a [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="c3bd3-160">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="c3bd3-161">Selezionare **Azure Active Directory**  >  **Security** Conditional  >  **Access**.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-161">Select **Azure Active Directory** > **Security** > **Conditional Access**.</span></span>
3. <span data-ttu-id="c3bd3-162">Nel riquadro **Accesso condizionale - Criteri** selezionare Nuovo **criterio.**</span><span class="sxs-lookup"><span data-stu-id="c3bd3-162">In the **Conditional access – Policies** pane, select **New policy**.</span></span>
4. <span data-ttu-id="c3bd3-163">Nel riquadro **Nuovo** immettere **MFA per gli account utente** nella **casella** Nome.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-163">In the **New** pane, enter **MFA for user accounts** in the **Name** box.</span></span>
5. <span data-ttu-id="c3bd3-164">Nella sezione **Assegnazioni** selezionare **Utenti e gruppi**.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-164">In the **Assignments** section, select **Users and groups**.</span></span>
6. <span data-ttu-id="c3bd3-165">Nella scheda **Includi** del riquadro **Utenti** e gruppi selezionare **Seleziona** utenti e gruppi  >  **Utenti e** gruppi  >  **Selezionare**.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-165">On the **Include** tab of the **Users and groups** pane, select **Select users and groups** > **Users and groups** > **Select**.</span></span>
7. <span data-ttu-id="c3bd3-166">Nel riquadro **Select** selezionare il **gruppo MFAUsers** e quindi **selezionare Select**  >  **Done.**</span><span class="sxs-lookup"><span data-stu-id="c3bd3-166">In the **Select** pane, select the **MFAUsers** group, and then select **Select** > **Done**.</span></span>
8. <span data-ttu-id="c3bd3-167">Nella sezione **Controlli di** accesso del **riquadro Nuovo** selezionare **Concedi**.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-167">In the **Access controls** section of the **New** pane, select **Grant**.</span></span>
9. <span data-ttu-id="c3bd3-168">Nel riquadro **Concedi** selezionare **Richiedi autenticazione a più fattori** e quindi selezionare **Seleziona.**</span><span class="sxs-lookup"><span data-stu-id="c3bd3-168">In the **Grant** pane, select **Require multi-factor authentication**, and then select **Select**.</span></span>
10. <span data-ttu-id="c3bd3-169">Nel riquadro **Nuovo** selezionare **Attivato** per **Abilita criterio** e quindi selezionare **Crea**.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-169">In the **New** pane, select **On** for **Enable policy**, and then select **Create**.</span></span>
11. <span data-ttu-id="c3bd3-170">Chiudere il **portale di Azure e** le schede dell'interfaccia di amministrazione di Microsoft **365.**</span><span class="sxs-lookup"><span data-stu-id="c3bd3-170">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="c3bd3-171">Per testare questo criterio, disconnettersi e accedere con l'account Utente 3.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-171">To test this policy, sign out and sign in with the User 3 account.</span></span> <span data-ttu-id="c3bd3-172">Dovrebbe essere richiesto di configurare l'autenticazione a più fattori.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-172">You should be prompted to configure MFA.</span></span> <span data-ttu-id="c3bd3-173">Ciò dimostra che viene applicato il criterio MFAUsers.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-173">This demonstrates that the MFAUsers policy is being applied.</span></span>

## <a name="next-step"></a><span data-ttu-id="c3bd3-174">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="c3bd3-174">Next step</span></span>

<span data-ttu-id="c3bd3-175">Esplorare altre caratteristiche e funzionalità [identità](m365-enterprise-test-lab-guides.md#identity) nell'ambiente di test.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-175">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="c3bd3-176">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c3bd3-176">See also</span></span>

[<span data-ttu-id="c3bd3-177">Guida di orientamento all'identità</span><span class="sxs-lookup"><span data-stu-id="c3bd3-177">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="c3bd3-178">Guide ai lab di test di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="c3bd3-178">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="c3bd3-179">Panoramica di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="c3bd3-179">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="c3bd3-180">Documentazione di Microsoft 365 for enterprise</span><span class="sxs-lookup"><span data-stu-id="c3bd3-180">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)