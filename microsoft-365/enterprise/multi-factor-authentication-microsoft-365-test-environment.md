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
description: Configurare l'autenticazione a più fattori utilizzando messaggi di testo inviati a uno smartphone nell'ambiente di testing di Microsoft 365 per le aziende.
ms.openlocfilehash: 4c59405c1ce59cafaf0309e2314e5cbfa4eb080a
ms.sourcegitcommit: c1dd5be42fe0c5dcc7c05817c941edd9076febf8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2020
ms.locfileid: "49558443"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="ff933-103">Autenticazione a più fattori per l'ambiente di testing di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="ff933-103">Multi-factor authentication for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="ff933-104">*Questa guida del laboratorio di testing può essere usata sia per gli ambienti di testing di Microsoft 365 per le aziende che per Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="ff933-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="ff933-105">Per un ulteriore livello di sicurezza per l'accesso a Microsoft 365 o a qualsiasi servizio o applicazione che usa il tenant di Azure AD per l'abbonamento, è possibile abilitare l'autenticazione a più fattori di Azure AD, che richiede più di un nome utente e una password per verificare un account.</span><span class="sxs-lookup"><span data-stu-id="ff933-105">For an additional level of security for signing in to Microsoft 365 or any service or application that uses the Azure AD tenant for your subscription, you can enable Azure AD multi-factor authentication, which requires more than just a username and password to verify an account.</span></span>

<span data-ttu-id="ff933-106">Con l'autenticazione a più fattori, gli utenti devono confermare una chiamata telefonica, digitare un codice di verifica inviato in un SMS o verificare l'autenticazione con un'app sullo smartphone dopo aver immesso correttamente le password.</span><span class="sxs-lookup"><span data-stu-id="ff933-106">With multi-factor authentication, users are required to acknowledge a phone call, type a verification code sent in a text message, or verify the authentication with an app on their smart phones after correctly entering their passwords.</span></span> <span data-ttu-id="ff933-107">Possono accedere solo dopo aver soddisfatto questo secondo fattore di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="ff933-107">They can sign in only after this second authentication factor is satisfied.</span></span>
  
<span data-ttu-id="ff933-108">In questo articolo viene descritto come abilitare e testare l'autenticazione basata su SMS per un account utente specifico.</span><span class="sxs-lookup"><span data-stu-id="ff933-108">This article describes how to enable and test text message-based authentication for a specific user account.</span></span>
  
<span data-ttu-id="ff933-109">La configurazione dell'autenticazione a più fattori per un account nell'ambiente di testing di Microsoft 365 per le aziende prevede due fasi e una terza fase facoltativa:</span><span class="sxs-lookup"><span data-stu-id="ff933-109">Setting up multi-factor authentication for an account in your Microsoft 365 for enterprise test environment involves two phases and a third optional phase:</span></span>
- [<span data-ttu-id="ff933-110">Fase 1: creare l'ambiente di testing di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="ff933-110">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="ff933-111">Fase 2: Abilitare e testare l'autenticazione a più fattori per l'account User 2</span><span class="sxs-lookup"><span data-stu-id="ff933-111">Phase 2: Enable and test multi-factor authentication for the User 2 account</span></span>](#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account)
- [<span data-ttu-id="ff933-112">Fase 3: abilitare e testare l'autenticazione a più fattori con un criterio di accesso condizionale</span><span class="sxs-lookup"><span data-stu-id="ff933-112">Phase 3: Enable and test multi-factor authentication with a conditional access policy</span></span>](#phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy)

![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="ff933-114">Per una mappa visiva di tutti gli articoli della guida del lab di test di Microsoft 365 per le aziende, passare a [Microsoft 365 per enterprise Test Lab Guide Stack.](../downloads/Microsoft365EnterpriseTLGStack.pdf)</span><span class="sxs-lookup"><span data-stu-id="ff933-114">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="ff933-115">Fase 1: creare l'ambiente di testing di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="ff933-115">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="ff933-116">Se si desidera semplicemente testare l'autenticazione a più fattori in modo leggero con i requisiti minimi, seguire le istruzioni in [Configurazione di base lightweight.](lightweight-base-configuration-microsoft-365-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="ff933-116">If you just want to test multi-factor authentication in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="ff933-117">Se si desidera testare l'autenticazione a più fattori in un'organizzazione simulata, seguire le istruzioni in [Autenticazione pass-through.](pass-through-auth-m365-ent-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="ff933-117">If you want to test multi-factor authentication in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="ff933-118">Il test dell'autenticazione a più fattori non richiede l'ambiente di testing aziendale simulato, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per una foresta di Servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ff933-118">Testing multi-factor authentication does not require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="ff933-119">Questo test viene fornito qui come opzione in modo per consentire di testare l’autenticazione a più fattori e sperimentarla in un ambiente che rappresenta un'organizzazione tipica.</span><span class="sxs-lookup"><span data-stu-id="ff933-119">It is provided here as an option so that you can test multi-factor authentication and experiment with it in an environment that represents a typical organization.</span></span>
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a><span data-ttu-id="ff933-120">Fase 2: Abilitare e testare l'autenticazione a più fattori per l'account User 2</span><span class="sxs-lookup"><span data-stu-id="ff933-120">Phase 2: Enable and test multi-factor authentication for the User 2 account</span></span>

<span data-ttu-id="ff933-121">Abilitare l'autenticazione a più fattori per l'account User 2 procedendo nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="ff933-121">Enable multi-factor authentication for the User 2 account with these steps:</span></span>
  
1. <span data-ttu-id="ff933-122">Aprire un'istanza privata separata del browser, passare all'interfaccia di amministrazione di Microsoft 365 ( ) e quindi accedere [https://portal.microsoft.com](https://portal.microsoft.com) con l'account amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="ff933-122">Open a separate, private instance of your browser, go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)), and then sign in with your global administrator account.</span></span>
    
2. <span data-ttu-id="ff933-123">Nel riquadro di spostamento sinistro selezionare **Utenti**  >  **attivi.**</span><span class="sxs-lookup"><span data-stu-id="ff933-123">In the left navigation, select **Users** > **Active users**.</span></span>
    
3. <span data-ttu-id="ff933-124">Nel riquadro Utenti attivi selezionare **Autenticazione a più fattori.**</span><span class="sxs-lookup"><span data-stu-id="ff933-124">In the Active users pane, select **Multi-factor authentication**.</span></span>
    
4. <span data-ttu-id="ff933-125">Nell'elenco, selezionare **l'account User 2.**</span><span class="sxs-lookup"><span data-stu-id="ff933-125">In the list, select the **User 2** account.</span></span>
    
5. <span data-ttu-id="ff933-126">Nella sezione **User 2** selezionare **Enable** in **Quick steps.**</span><span class="sxs-lookup"><span data-stu-id="ff933-126">In the **User 2** section, under **Quick steps**, select **Enable**.</span></span>
    
6. <span data-ttu-id="ff933-127">Nella finestra **di dialogo Informazioni sull'abilitazione dell'autenticazione** a più fattori selezionare Abilita autenticazione a più **fattori.**</span><span class="sxs-lookup"><span data-stu-id="ff933-127">In the **About enabling multi-factor auth** dialog box, select **Enable multi-factor auth**.</span></span>
    
7. <span data-ttu-id="ff933-128">Nella finestra **di dialogo Aggiornamenti** riusciti selezionare **Chiudi.**</span><span class="sxs-lookup"><span data-stu-id="ff933-128">In the **Updates successful** dialog box, select **Close**.</span></span>
    
8. <span data-ttu-id="ff933-129">Nella scheda dell'interfaccia di amministrazione di **Microsoft 365** selezionare l'icona dell'account utente in alto a destra e quindi **selezionare Disconnetto.**</span><span class="sxs-lookup"><span data-stu-id="ff933-129">On the **Microsoft 365 admin center** tab, select the user account icon in the upper right, and then select **Sign out**.</span></span>
    
9. <span data-ttu-id="ff933-130">Chiudere l'istanza del browser.</span><span class="sxs-lookup"><span data-stu-id="ff933-130">Close your browser instance.</span></span>
   
<span data-ttu-id="ff933-131">Completare la configurazione dell'account User 2 per utilizzare un messaggio di testo per la convalida e testarla con questa procedura:</span><span class="sxs-lookup"><span data-stu-id="ff933-131">Complete the configuration for the User 2 account to use a text message for validation and test it with these steps:</span></span>
  
1. <span data-ttu-id="ff933-132">Aprire una nuova istanza privata del browser.</span><span class="sxs-lookup"><span data-stu-id="ff933-132">Open a new, private instance of your browser.</span></span>
    
2. <span data-ttu-id="ff933-133">Passare all'interfaccia di amministrazione di [Microsoft 365](https://admin.microsoft.com) e accedere con il nome account utente 2 e la password.</span><span class="sxs-lookup"><span data-stu-id="ff933-133">Go to the [Microsoft 365 admin center](https://admin.microsoft.com) and sign in with the User 2 account name and password.</span></span>
    
3. <span data-ttu-id="ff933-134">Dopo l'accesso, viene richiesto di configurare l'account per ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="ff933-134">After signing in, you are prompted to set up the account for more information.</span></span> <span data-ttu-id="ff933-135">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="ff933-135">Select **Next**.</span></span>
    
4. <span data-ttu-id="ff933-136">Nella pagina **Verifica aggiuntiva di sicurezza**:</span><span class="sxs-lookup"><span data-stu-id="ff933-136">On the **Additional security verification** page:</span></span>
    
   - <span data-ttu-id="ff933-137">Selezionare il paese o l'area geografica.</span><span class="sxs-lookup"><span data-stu-id="ff933-137">Select your country or region.</span></span>
    
   - <span data-ttu-id="ff933-138">Immettere il numero di telefono dello smartphone che riceverà messaggi di testo.</span><span class="sxs-lookup"><span data-stu-id="ff933-138">Enter the phone number of the smart phone that will receive text messages.</span></span>
    
   - <span data-ttu-id="ff933-139">Nel **metodo** selezionare **Invia un codice tramite messaggio di testo.**</span><span class="sxs-lookup"><span data-stu-id="ff933-139">In **Method**, select **Send me a code by text message**.</span></span>
    
5. <span data-ttu-id="ff933-140">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="ff933-140">Select **Next**.</span></span>
    
6. <span data-ttu-id="ff933-141">Immetti il codice di verifica dal messaggio di testo ricevuto sullo smartphone e quindi seleziona **Verifica.**</span><span class="sxs-lookup"><span data-stu-id="ff933-141">Enter the verification code from the text message received on your smart phone, and then select **Verify**.</span></span>
    
7. <span data-ttu-id="ff933-142">Nella pagina **Passaggio 3: Mantenere le applicazioni esistenti** selezionare **Fatto.**</span><span class="sxs-lookup"><span data-stu-id="ff933-142">On the **Step 3: Keep your existing applications** page, select **Done**.</span></span>
    
8. <span data-ttu-id="ff933-143">Se è la prima volta che si accede con l'account User 2, viene richiesto di modificare la password.</span><span class="sxs-lookup"><span data-stu-id="ff933-143">If this is the first time you signed in with the User 2 account, you are prompted to change the password.</span></span> <span data-ttu-id="ff933-144">Immettere la password originale e una nuova password due volte, quindi selezionare **Aggiorna password ed eseguire l'accesso.**</span><span class="sxs-lookup"><span data-stu-id="ff933-144">Enter the original password and a new password twice, and then select **Update password and sign in**.</span></span> <span data-ttu-id="ff933-145">Annotare nome e password in una posizione sicura.</span><span class="sxs-lookup"><span data-stu-id="ff933-145">Record the new password in a secure location.</span></span>
    
    <span data-ttu-id="ff933-146">Il portale di Office per User 2 dovrebbe essere visualizzato **nella Microsoft Office Home** del browser.</span><span class="sxs-lookup"><span data-stu-id="ff933-146">You should see the Office portal for User 2 on the **Microsoft Office Home** tab of your browser.</span></span>

## <a name="phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy"></a><span data-ttu-id="ff933-147">Fase 3: abilitare e testare l'autenticazione a più fattori con un criterio di accesso condizionale</span><span class="sxs-lookup"><span data-stu-id="ff933-147">Phase 3: Enable and test multi-factor authentication with a conditional access policy</span></span>

<span data-ttu-id="ff933-148">*Questa fase può essere usata solo per un ambiente di testing di Microsoft 365 per le aziende.*</span><span class="sxs-lookup"><span data-stu-id="ff933-148">*This phase can only be used for a Microsoft 365 for enterprise test environment.*</span></span>

<span data-ttu-id="ff933-149">In questa fase, si abilita l'autenticazione a più fattori per l'account User 3 utilizzando un gruppo e un criterio di accesso condizionale.</span><span class="sxs-lookup"><span data-stu-id="ff933-149">In this phase, you enable multi-factor authentication for the User 3 account using a group and a conditional access policy.</span></span>

<span data-ttu-id="ff933-150">Successivamente, crea un nuovo gruppo denominato MFAUsers e aggiungi l'account User 3.</span><span class="sxs-lookup"><span data-stu-id="ff933-150">Next, create a new group named MFAUsers and add the User 3 account to it.</span></span>

1. <span data-ttu-id="ff933-151">Nella scheda **dell'interfaccia di amministrazione di Microsoft 365** selezionare Gruppi **nel** riquadro di spostamento sinistro e quindi **selezionare Gruppi.**</span><span class="sxs-lookup"><span data-stu-id="ff933-151">On the **Microsoft 365 admin center** tab, select **Groups** in the left navigation, and then select **Groups**.</span></span>
2. <span data-ttu-id="ff933-152">Selezionare **Aggiungi gruppo.**</span><span class="sxs-lookup"><span data-stu-id="ff933-152">Select **Add a group**.</span></span>
3. <span data-ttu-id="ff933-153">Nel riquadro **Scegliere un tipo di** gruppo selezionare **Sicurezza** e quindi fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="ff933-153">In the **Choose a group type** pane, select **Security**, and then select **Next**.</span></span>
4. <span data-ttu-id="ff933-154">Nel riquadro **Set up the basics** selezionare **Create group** e quindi **close.**</span><span class="sxs-lookup"><span data-stu-id="ff933-154">In the **Set up the basics** pane, select **Create group**, and then select **Close**.</span></span>
5. <span data-ttu-id="ff933-155">Nel riquadro **Rivedere e completare l'aggiunta del** gruppo, immettere **MFAUsers** e quindi selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="ff933-155">In the **Review and finish adding group** pane, enter **MFAUsers**, and then select **Next**.</span></span>
6. <span data-ttu-id="ff933-156">Nell'elenco dei gruppi, selezionare il **gruppo MFAUsers.**</span><span class="sxs-lookup"><span data-stu-id="ff933-156">In the list of groups, select the **MFAUsers** group.</span></span>
7. <span data-ttu-id="ff933-157">Nel riquadro **MFAUsers** selezionare **Membri** e quindi selezionare **Visualizza tutti e gestisci membri.**</span><span class="sxs-lookup"><span data-stu-id="ff933-157">In the **MFAUsers** pane, select **Members**, and then select **View all and manage members**.</span></span>
8. <span data-ttu-id="ff933-158">Nel riquadro **MFAUsers** seleziona **Aggiungi membri,** seleziona l'account **User 3** e quindi seleziona **Salva**  >  **chiudi.**  >  </span><span class="sxs-lookup"><span data-stu-id="ff933-158">In the **MFAUsers** pane, select **Add members**, select the **User 3** account, and then select **Save** > **Close** > **Close**.</span></span>

<span data-ttu-id="ff933-159">Successivamente, creare un criterio di accesso condizionale per richiedere l'autenticazione a più fattori per i membri del gruppo MFAUsers.</span><span class="sxs-lookup"><span data-stu-id="ff933-159">Next, create a conditional access policy to require multifactor authentication for members of the MFAUsers group.</span></span>

1. <span data-ttu-id="ff933-160">In una nuova scheda del browser passare a [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="ff933-160">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="ff933-161">Selezionare **Accesso condizionale per la sicurezza** di Azure Active  >    >  Directory.</span><span class="sxs-lookup"><span data-stu-id="ff933-161">Select **Azure Active Directory** > **Security** > **Conditional Access**.</span></span>
3. <span data-ttu-id="ff933-162">Nel riquadro **Accesso condizionale - Criteri** selezionare Nuovo **criterio.**</span><span class="sxs-lookup"><span data-stu-id="ff933-162">In the **Conditional access – Policies** pane, select **New policy**.</span></span>
4. <span data-ttu-id="ff933-163">Nel riquadro **Nuovo** immettere **MFA per gli account utente** nella **casella** Nome.</span><span class="sxs-lookup"><span data-stu-id="ff933-163">In the **New** pane, enter **MFA for user accounts** in the **Name** box.</span></span>
5. <span data-ttu-id="ff933-164">Nella sezione **Assegnazioni** selezionare **Utenti e gruppi.**</span><span class="sxs-lookup"><span data-stu-id="ff933-164">In the **Assignments** section, select **Users and groups**.</span></span>
6. <span data-ttu-id="ff933-165">Nella scheda **Includi** del **riquadro** Utenti e gruppi selezionare **Seleziona** utenti e  >  **gruppi.**  >  </span><span class="sxs-lookup"><span data-stu-id="ff933-165">On the **Include** tab of the **Users and groups** pane, select **Select users and groups** > **Users and groups** > **Select**.</span></span>
7. <span data-ttu-id="ff933-166">Nel riquadro **Select** selezionare il gruppo **MFAUsers** e quindi **selezionare Select**  >  **Done.**</span><span class="sxs-lookup"><span data-stu-id="ff933-166">In the **Select** pane, select the **MFAUsers** group, and then select **Select** > **Done**.</span></span>
8. <span data-ttu-id="ff933-167">Nella sezione **Controlli di** accesso del **riquadro Nuovo** selezionare **Concedi.**</span><span class="sxs-lookup"><span data-stu-id="ff933-167">In the **Access controls** section of the **New** pane, select **Grant**.</span></span>
9. <span data-ttu-id="ff933-168">Nel riquadro **Concedi** selezionare Richiedi autenticazione a **più fattori** e quindi selezionare **Seleziona.**</span><span class="sxs-lookup"><span data-stu-id="ff933-168">In the **Grant** pane, select **Require multi-factor authentication**, and then select **Select**.</span></span>
10. <span data-ttu-id="ff933-169">Nel riquadro **Nuovo** selezionare **Attivato** per **Abilita criterio** e quindi selezionare **Crea.**</span><span class="sxs-lookup"><span data-stu-id="ff933-169">In the **New** pane, select **On** for **Enable policy**, and then select **Create**.</span></span>
11. <span data-ttu-id="ff933-170">Chiudere il **portale di Azure e** le schede dell'interfaccia di amministrazione di Microsoft **365.**</span><span class="sxs-lookup"><span data-stu-id="ff933-170">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="ff933-171">Per testare questo criterio, disconnettersi e accedere con l'account User 3.</span><span class="sxs-lookup"><span data-stu-id="ff933-171">To test this policy, sign out and sign in with the User 3 account.</span></span> <span data-ttu-id="ff933-172">Dovrebbe essere richiesto di configurare l'autenticazione a più fattori.</span><span class="sxs-lookup"><span data-stu-id="ff933-172">You should be prompted to configure MFA.</span></span> <span data-ttu-id="ff933-173">Ciò dimostra che il criterio MFAUsers viene applicato.</span><span class="sxs-lookup"><span data-stu-id="ff933-173">This demonstrates that the MFAUsers policy is being applied.</span></span>

## <a name="next-step"></a><span data-ttu-id="ff933-174">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="ff933-174">Next step</span></span>

<span data-ttu-id="ff933-175">Esplorare altre caratteristiche e funzionalità [identità](m365-enterprise-test-lab-guides.md#identity) nell'ambiente di test.</span><span class="sxs-lookup"><span data-stu-id="ff933-175">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="ff933-176">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ff933-176">See also</span></span>

[<span data-ttu-id="ff933-177">Guida di orientamento all'identità</span><span class="sxs-lookup"><span data-stu-id="ff933-177">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="ff933-178">Guide ai lab di test di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="ff933-178">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="ff933-179">Panoramica di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="ff933-179">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="ff933-180">Documentazione di Microsoft 365 for enterprise</span><span class="sxs-lookup"><span data-stu-id="ff933-180">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
