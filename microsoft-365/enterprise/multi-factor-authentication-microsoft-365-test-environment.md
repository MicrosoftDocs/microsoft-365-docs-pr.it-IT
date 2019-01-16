---
title: Ambiente di testing di autenticazione a più fattori per la propria azienda 365 Microsoft
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
description: Configurare l'autenticazione a più fattori tramite messaggi di testo inviati a Smartphone nell'ambiente di test Microsoft 365 aziendale.
ms.openlocfilehash: 353f09253794670e8107e084acb3a01cd309fd60
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2019
ms.locfileid: "26868281"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="30fa5-103">Ambiente di testing di autenticazione a più fattori per la propria azienda 365 Microsoft</span><span class="sxs-lookup"><span data-stu-id="30fa5-103">Multi-factor authentication for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="30fa5-p101">Per un livello aggiuntivo di protezione per l'accesso a Office 365 o qualsiasi servizio o applicazione che utilizza il tenant di Azure Active Directory per l'organizzazione, è possibile abilitare l'autenticazione multifattore Azure, che richiede più di solo un nome utente e una password per verificare un account. Con l'autenticazione a più fattori, sono necessari per confermare una telefonata, digitare un codice di verifica inviato un messaggio di testo o specificare una password di app per i telefoni smart dopo aver immesso correttamente le password degli utenti. È possibile accedere solo dopo che è state soddisfatte questo secondo fattore di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="30fa5-p101">For an additional level of security for signing in to Office 365 or any service or application that uses the Azure AD tenant for your organization, you can enable Azure multi-factor authentication, which requires more than just a username and password to verify an account. With multi-factor authentication, users are required to acknowledge a phone call, type a verification code sent in a text message, or specify an app password on their smart phones after correctly entering their passwords. They can sign in only after this second authentication factor has been satisfied.</span></span> 
  
<span data-ttu-id="30fa5-107">In questo articolo viene descritto come attivare e testare l'autenticazione basata su messaggi di testo per un account specifico.</span><span class="sxs-lookup"><span data-stu-id="30fa5-107">This article describes how to enable and test text message-based authentication for a specific account.</span></span>
  
<span data-ttu-id="30fa5-108">Esistono due fasi di configurazione dell'autenticazione a più fattori per un account nell'ambiente di test Microsoft 365 aziendale:</span><span class="sxs-lookup"><span data-stu-id="30fa5-108">There are two phases to setting up multi-factor authentication for an account in your Microsoft 365 Enterprise test environment:</span></span>
  
1. <span data-ttu-id="30fa5-109">Creare l'ambiente di test Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="30fa5-109">Create the Microsoft 365 Enterprise test environment.</span></span>
    
2. <span data-ttu-id="30fa5-110">Abilitare e testare l'autenticazione a più fattori per l'account User 2.</span><span class="sxs-lookup"><span data-stu-id="30fa5-110">Enable and test multi-factor authentication for the User 2 account.</span></span>

![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="30fa5-112">Fare clic [qui](https://aka.ms/m365etlgstack) per consultare una mappa di tutti gli articoli relativi alla guida al lab test di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="30fa5-112">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="30fa5-113">Fase 1: Preparare l'ambiente di testing Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="30fa5-113">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="30fa5-114">Se si desidera testare l'autenticazione a più fattori in un modo semplice con i requisiti minimi, seguire le istruzioni di [configurazione di base semplificata](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="30fa5-114">If you just want to test multi-factor authentication in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="30fa5-115">Se si desidera testare l'autenticazione a più fattori in un'azienda simulata, seguire le istruzioni [nell'autenticazione pass-through](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="30fa5-115">If you want to test multi-factor authentication in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="30fa5-p102">Test dell'autenticazione a più fattori non richiede l'ambiente di testing simulato enterprise, che include una rete intranet simulata connessione a Internet e la sincronizzazione delle directory per una foresta Windows Server Active Directory. Viene fornito qui come un'opzione in modo che sia possibile testare l'autenticazione a più fattori e sperimentare in un ambiente che rappresenta una tipica organizzazione.</span><span class="sxs-lookup"><span data-stu-id="30fa5-p102">Testing multi-factor authentication does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test multi-factor authentication and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a><span data-ttu-id="30fa5-118">Fase 2: Abilitare e testare l'autenticazione a più fattori per l'account User 2</span><span class="sxs-lookup"><span data-stu-id="30fa5-118">Phase 2: Enable and test multi-factor authentication for the User 2 account</span></span>

<span data-ttu-id="30fa5-119">Abilitare l'autenticazione a più fattori per l'account User 2 procedendo nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="30fa5-119">Enable multi-factor authentication for the User 2 account with these steps:</span></span>
  
1. <span data-ttu-id="30fa5-120">Aprire un'istanza privata separata del browser, accedere al portale di Office ([https://office.com](https://office.com)) e quindi accedere con l'account amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="30fa5-120">Open a separate, private instance of your browser, go to the Office portal ([https://office.com](https://office.com)), and then sign in with your global administrator account.</span></span>
    
2. <span data-ttu-id="30fa5-121">Dalla pagina principale del portale, fare clic su **Admin**.</span><span class="sxs-lookup"><span data-stu-id="30fa5-121">From the main portal page, click **Admin**.</span></span>
    
3. <span data-ttu-id="30fa5-122">Nel riquadro di spostamento sinistro fare clic su **Utenti > Utenti attivi**.</span><span class="sxs-lookup"><span data-stu-id="30fa5-122">In the left navigation, click **Users > Active users**.</span></span>
    
4. <span data-ttu-id="30fa5-123">Nel riquadro utenti attivi, fare clic su **più > configurazione di autenticazione a più fattori**.</span><span class="sxs-lookup"><span data-stu-id="30fa5-123">In the Active users pane, click **More > Multi-factor authentication setup**.</span></span>
    
5. <span data-ttu-id="30fa5-124">Nell'elenco, selezionare l'account **utente 2** .</span><span class="sxs-lookup"><span data-stu-id="30fa5-124">In the list, select the **User 2** account.</span></span>
    
6. <span data-ttu-id="30fa5-125">Nella sezione **User 2**, sotto **Azioni rapide**, fare clic su **Abilita**.</span><span class="sxs-lookup"><span data-stu-id="30fa5-125">In the **User 2** section, under **Quick steps**, click **Enable**.</span></span>
    
7. <span data-ttu-id="30fa5-126">Nella finestra di dialogo **Informazioni sull'abilitazione dell'autenticazione più fattori** fare clic su **Abilita Multi-Factor Auth**.</span><span class="sxs-lookup"><span data-stu-id="30fa5-126">In the **About enabling multi-factor auth** dialog box, click **Enable multi-factor auth**.</span></span>
    
8. <span data-ttu-id="30fa5-127">Nella finestra di dialogo **Aggiorna completata** fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="30fa5-127">In the **Updates successful** dialog box, click **Close**.</span></span>
    
9. <span data-ttu-id="30fa5-128">Nella scheda **Microsoft Office Home** fare clic sull'icona dell'account utente in alto a destra, quindi fare clic su **Disconnetti**.</span><span class="sxs-lookup"><span data-stu-id="30fa5-128">On the **Microsoft Office Home** tab, click the user account icon in the upper right, and then click **Sign out**.</span></span>
    
10. <span data-ttu-id="30fa5-129">Chiudere l'istanza del browser.</span><span class="sxs-lookup"><span data-stu-id="30fa5-129">Close your browser instance.</span></span>
   
<span data-ttu-id="30fa5-130">Completare la configurazione dell'account User 2 per utilizzare un messaggio di testo per la convalida e testarla con questa procedura:</span><span class="sxs-lookup"><span data-stu-id="30fa5-130">Complete the configuration for the User 2 account to use a text message for validation and test it with these steps:</span></span>
  
1. <span data-ttu-id="30fa5-131">Aprire una nuova istanza del browser privata.</span><span class="sxs-lookup"><span data-stu-id="30fa5-131">Open a new, private instance of your browser.</span></span>
    
2. <span data-ttu-id="30fa5-132">Accedere al portale di Office ([https://office.com](https://office.com)) e accedere con l'account utente 2 (user2 @\<nome organizzazione >. onmicrosoft.com) e una password.</span><span class="sxs-lookup"><span data-stu-id="30fa5-132">Go to the Office portal ([https://office.com](https://office.com)) and sign in with the User 2 account (user2@\<organization name>.onmicrosoft.com) and password.</span></span>
    
3. <span data-ttu-id="30fa5-p103">Dopo l'accesso, viene chiesto di configurare l'account per ulteriori informazioni. Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="30fa5-p103">After signing in, you are prompted to set up the account for more information. Click **Next**.</span></span>
    
4. <span data-ttu-id="30fa5-135">Nella pagina **Verifica aggiuntiva di sicurezza**:</span><span class="sxs-lookup"><span data-stu-id="30fa5-135">On the **Additional security verification** page:</span></span>
    
   - <span data-ttu-id="30fa5-136">Selezionare il paese o l'area geografica.</span><span class="sxs-lookup"><span data-stu-id="30fa5-136">Select your country or region.</span></span>
    
   - <span data-ttu-id="30fa5-137">Digitare il numero di telefono dello smartphone che riceverà i messaggi di testo.</span><span class="sxs-lookup"><span data-stu-id="30fa5-137">Type phone number of the smart phone that will receive text messages.</span></span>
    
   - <span data-ttu-id="30fa5-138">Nel **metodo**, fare clic su **Invia automaticamente un codice di un messaggio**.</span><span class="sxs-lookup"><span data-stu-id="30fa5-138">In **Method**, click **Send me a code by text message**.</span></span>
    
5. <span data-ttu-id="30fa5-139">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="30fa5-139">Click **Next**.</span></span>
    
6. <span data-ttu-id="30fa5-140">Immettere il codice di verifica del messaggio di testo ricevuto sullo smartphone e quindi fare clic su **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="30fa5-140">Enter the verification code from the text message received on your smart phone, and then click **Verify**.</span></span>
    
7. <span data-ttu-id="30fa5-141">Nella pagina **Passaggio 3: Mantenere le applicazioni esistenti**, annotare la password dell'app visualizzata per l'account User 2 in una posizione sicura e fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="30fa5-141">On the **Step 3: Keep your existing applications** page, record the displayed app password for the User 2 account in a secure location, and then click **Done**.</span></span>
    
8. <span data-ttu-id="30fa5-p104">Se è la prima volta che si accede con l'account User 2, viene richiesto di modificare la password. Digitare la password originale e una nuova password due volte, quindi fare clic su **Aggiornare la password ed eseguire l'accesso**. Annotare nome e password in una posizione sicura.</span><span class="sxs-lookup"><span data-stu-id="30fa5-p104">If this is the first time you signed in with the User 2 account, you are prompted to change the password. Type the original password and a new password twice, and then click **Update password and sign in**. Record the new password in a secure location.</span></span>
    
    <span data-ttu-id="30fa5-145">È consigliabile vedere del portale di Office per l'utente 2 nella scheda **Home page di Microsoft Office** del browser.</span><span class="sxs-lookup"><span data-stu-id="30fa5-145">You should see the Office portal for User 2 on the **Microsoft Office Home** tab of your browser.</span></span>


<span data-ttu-id="30fa5-146">Nella fase di identità per informazioni e collegamenti per distribuire l'autenticazione a più fattori nell'ambiente di produzione, vedere la sezione [configurare l'autenticazione a più fattori](identity-multi-factor-authentication.md) .</span><span class="sxs-lookup"><span data-stu-id="30fa5-146">See the [Set up multi-factor authentication](identity-multi-factor-authentication.md) step in the Identity phase for information and links to deploy multi-factor authentication in production.</span></span>
    
## <a name="next-step"></a><span data-ttu-id="30fa5-147">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="30fa5-147">Next step</span></span>

<span data-ttu-id="30fa5-148">Esplorare altre caratteristiche e funzionalità [identità](m365-enterprise-test-lab-guides.md#identity) nell'ambiente di test.</span><span class="sxs-lookup"><span data-stu-id="30fa5-148">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="30fa5-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="30fa5-149">See also</span></span>

[<span data-ttu-id="30fa5-150">Fase 2: identità</span><span class="sxs-lookup"><span data-stu-id="30fa5-150">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="30fa5-151">Guide al lab di test di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="30fa5-151">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="30fa5-152">Distribuzione di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="30fa5-152">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="30fa5-153">Documentazione di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="30fa5-153">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
