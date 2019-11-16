---
title: Autenticazione a più fattori per l'ambiente di testing di Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Configurare l'autenticazione a più fattori tramite messaggi di testo inviati a uno Smart Phone nell'ambiente di testing di Microsoft 365 Enterprise.
ms.openlocfilehash: af4ae63f52fa74084dfddf0e6861c5ae3ba2aedb
ms.sourcegitcommit: 9ee873c6a2f738a0c99921e036894b646742e706
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/15/2019
ms.locfileid: "38673262"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="bd818-103">Autenticazione a più fattori per l'ambiente di testing di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="bd818-103">Multi-factor authentication for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="bd818-104">*Questa guida del laboratorio di testing può essere utilizzata per ambienti di testing Microsoft 365 Enterprise e Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="bd818-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="bd818-105">Per un ulteriore livello di sicurezza per l'accesso a Office 365 o qualsiasi servizio o applicazione che utilizza il tenant di Azure AD per l'organizzazione, è possibile abilitare l'autenticazione a più fattori di Azure, che richiede più di un semplice nome utente e una password per verificare un account.</span><span class="sxs-lookup"><span data-stu-id="bd818-105">For an additional level of security for signing in to Office 365 or any service or application that uses the Azure AD tenant for your organization, you can enable Azure multi-factor authentication, which requires more than just a username and password to verify an account.</span></span> <span data-ttu-id="bd818-106">Con l'autenticazione a più fattori, agli utenti viene richiesto di riconoscere una telefonata, digitare un codice di verifica inviato in un messaggio di testo oppure specificare una password per l'app negli smartphone dopo aver inserito correttamente le password.</span><span class="sxs-lookup"><span data-stu-id="bd818-106">With multi-factor authentication, users are required to acknowledge a phone call, type a verification code sent in a text message, or specify an app password on their smart phones after correctly entering their passwords.</span></span> <span data-ttu-id="bd818-107">L'accesso è consentito solo dopo che un secondo fattore di autenticazione viene soddisfatto.</span><span class="sxs-lookup"><span data-stu-id="bd818-107">They can sign in only after this second authentication factor has been satisfied.</span></span> 
  
<span data-ttu-id="bd818-108">In questo articolo viene descritto come abilitare e testare l'autenticazione basata su messaggi di testo per un account specifico.</span><span class="sxs-lookup"><span data-stu-id="bd818-108">This article describes how to enable and test text message-based authentication for a specific account.</span></span>
  
<span data-ttu-id="bd818-109">Sono disponibili due fasi per configurare l'autenticazione a più fattori per un account nell'ambiente di testing di Microsoft 365 Enterprise:</span><span class="sxs-lookup"><span data-stu-id="bd818-109">There are two phases to setting up multi-factor authentication for an account in your Microsoft 365 Enterprise test environment:</span></span>
  
1. <span data-ttu-id="bd818-110">Creare l'ambiente di testing di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="bd818-110">Create the Microsoft 365 Enterprise test environment.</span></span>
    
2. <span data-ttu-id="bd818-111">Abilitare e testare l'autenticazione a più fattori per l'account User 2.</span><span class="sxs-lookup"><span data-stu-id="bd818-111">Enable and test multi-factor authentication for the User 2 account.</span></span>

![Guide del laboratorio di testing per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="bd818-113">Fare clic [qui](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) per consultare una mappa di tutti gli articoli relativi alla guida al lab test di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="bd818-113">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="bd818-114">Fase 1: Creare l'ambiente di testing di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="bd818-114">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="bd818-115">Se si desidera testare l'autenticazione a più fattori in modo semplice con i requisiti minimi, seguire le istruzioni contenute in [Lightweight base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="bd818-115">If you just want to test multi-factor authentication in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="bd818-116">Se si desidera testare l'autenticazione a più fattori in un'azienda simulata, seguire le istruzioni riportate nell' [autenticazione pass-through](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="bd818-116">If you want to test multi-factor authentication in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="bd818-117">Se si verifica l'autenticazione a più fattori, non è necessario l'ambiente di testing dell'organizzazione simulata, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per una foresta di servizi di dominio Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="bd818-117">Testing multi-factor authentication does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="bd818-118">Questo test viene fornito qui come opzione in modo per consentire di testare l’autenticazione a più fattori e sperimentarla in un ambiente che rappresenta un'organizzazione tipica.</span><span class="sxs-lookup"><span data-stu-id="bd818-118">It is provided here as an option so that you can test multi-factor authentication and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a><span data-ttu-id="bd818-119">Fase 2: Abilitare e testare l'autenticazione a più fattori per l'account User 2</span><span class="sxs-lookup"><span data-stu-id="bd818-119">Phase 2: Enable and test multi-factor authentication for the User 2 account</span></span>

<span data-ttu-id="bd818-120">Abilitare l'autenticazione a più fattori per l'account User 2 procedendo nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="bd818-120">Enable multi-factor authentication for the User 2 account with these steps:</span></span>
  
1. <span data-ttu-id="bd818-121">Aprire un'istanza separata, privata del browser, accedere all'interfaccia di amministrazione di Microsoft 365 ([https://portal.microsoft.com](https://portal.microsoft.com)) e quindi accedere con l'account di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="bd818-121">Open a separate, private instance of your browser, go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)), and then sign in with your global administrator account.</span></span>
    
2. <span data-ttu-id="bd818-122">Nel riquadro di spostamento sinistro fare clic su **Utenti > Utenti attivi**.</span><span class="sxs-lookup"><span data-stu-id="bd818-122">In the left navigation, click **Users > Active users**.</span></span>
    
3. <span data-ttu-id="bd818-123">Nel riquadro utenti attivi, fare clic su **altre > configurazione dell'autenticazione a più fattori**.</span><span class="sxs-lookup"><span data-stu-id="bd818-123">In the Active users pane, click **More > Multi-factor authentication setup**.</span></span>
    
4. <span data-ttu-id="bd818-124">Nell'elenco, selezionare l'account **User 2** .</span><span class="sxs-lookup"><span data-stu-id="bd818-124">In the list, select the **User 2** account.</span></span>
    
5. <span data-ttu-id="bd818-125">Nella sezione **User 2**, sotto **Azioni rapide**, fare clic su **Abilita**.</span><span class="sxs-lookup"><span data-stu-id="bd818-125">In the **User 2** section, under **Quick steps**, click **Enable**.</span></span>
    
6. <span data-ttu-id="bd818-126">Nella finestra di dialogo **Informazioni sull'abilitazione dell'autenticazione più fattori** fare clic su **Abilita Multi-Factor Auth**.</span><span class="sxs-lookup"><span data-stu-id="bd818-126">In the **About enabling multi-factor auth** dialog box, click **Enable multi-factor auth**.</span></span>
    
7. <span data-ttu-id="bd818-127">Nella finestra di dialogo **aggiornamenti con esito positivo** fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="bd818-127">In the **Updates successful** dialog box, click **Close**.</span></span>
    
8. <span data-ttu-id="bd818-128">Nella scheda dell'interfaccia di **amministrazione di Microsoft 365** fare clic sull'icona dell'account utente in alto a destra, quindi fare clic su **Esci**.</span><span class="sxs-lookup"><span data-stu-id="bd818-128">On the **Microsoft 365 admin center** tab, click the user account icon in the upper right, and then click **Sign out**.</span></span>
    
9. <span data-ttu-id="bd818-129">Chiudere l'istanza del browser.</span><span class="sxs-lookup"><span data-stu-id="bd818-129">Close your browser instance.</span></span>
   
<span data-ttu-id="bd818-130">Completare la configurazione dell'account User 2 per utilizzare un messaggio di testo per la convalida e testarla con questa procedura:</span><span class="sxs-lookup"><span data-stu-id="bd818-130">Complete the configuration for the User 2 account to use a text message for validation and test it with these steps:</span></span>
  
1. <span data-ttu-id="bd818-131">Aprire una nuova istanza privata del browser.</span><span class="sxs-lookup"><span data-stu-id="bd818-131">Open a new, private instance of your browser.</span></span>
    
2. <span data-ttu-id="bd818-132">Accedere al portale di Office 365 ([https://portal.office.com](https://portal.office.com)) ed eseguire l'accesso con il nome e la password dell'account utente 2.</span><span class="sxs-lookup"><span data-stu-id="bd818-132">Go to the Office 365 portal ([https://portal.office.com](https://portal.office.com)) and sign in with the User 2 account name and password.</span></span>
    
3. <span data-ttu-id="bd818-133">Dopo aver eseguito l'accesso, viene richiesto di configurare l'account per ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="bd818-133">After signing in, you are prompted to set up the account for more information.</span></span> <span data-ttu-id="bd818-134">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="bd818-134">Click **Next**.</span></span>
    
4. <span data-ttu-id="bd818-135">Nella pagina **Verifica aggiuntiva di sicurezza**:</span><span class="sxs-lookup"><span data-stu-id="bd818-135">On the **Additional security verification** page:</span></span>
    
   - <span data-ttu-id="bd818-136">Selezionare il paese o l'area geografica.</span><span class="sxs-lookup"><span data-stu-id="bd818-136">Select your country or region.</span></span>
    
   - <span data-ttu-id="bd818-137">Digitare il numero di telefono dello smartphone che riceverà i messaggi di testo.</span><span class="sxs-lookup"><span data-stu-id="bd818-137">Type phone number of the smart phone that will receive text messages.</span></span>
    
   - <span data-ttu-id="bd818-138">In **Metodo**, fare clic su **Inviami un codice tramite messaggio di testo**.</span><span class="sxs-lookup"><span data-stu-id="bd818-138">In **Method**, click **Send me a code by text message**.</span></span>
    
5. <span data-ttu-id="bd818-139">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="bd818-139">Click **Next**.</span></span>
    
6. <span data-ttu-id="bd818-140">Immettere il codice di verifica del messaggio di testo ricevuto sullo smartphone e quindi fare clic su **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="bd818-140">Enter the verification code from the text message received on your smart phone, and then click **Verify**.</span></span>
    
7. <span data-ttu-id="bd818-141">Nella pagina **Passaggio 3: Mantenere le applicazioni esistenti**, annotare la password dell'app visualizzata per l'account User 2 in una posizione sicura e fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="bd818-141">On the **Step 3: Keep your existing applications** page, record the displayed app password for the User 2 account in a secure location, and then click **Done**.</span></span>
    
8. <span data-ttu-id="bd818-p104">Se è la prima volta che si accede con l'account User 2, viene richiesto di modificare la password. Digitare la password originale e una nuova password due volte, quindi fare clic su **Aggiornare la password ed eseguire l'accesso**. Annotare nome e password in una posizione sicura.</span><span class="sxs-lookup"><span data-stu-id="bd818-p104">If this is the first time you signed in with the User 2 account, you are prompted to change the password. Type the original password and a new password twice, and then click **Update password and sign in**. Record the new password in a secure location.</span></span>
    
    <span data-ttu-id="bd818-145">Verrà visualizzato il portale di Office per l'utente 2 nella scheda **Microsoft Office Home** del browser.</span><span class="sxs-lookup"><span data-stu-id="bd818-145">You should see the Office portal for User 2 on the **Microsoft Office Home** tab of your browser.</span></span>


<span data-ttu-id="bd818-146">Per informazioni e collegamenti per la distribuzione dell'autenticazione a più fattori in produzione, vedere la procedura di [configurazione dell'autenticazione](identity-secure-user-sign-ins.md#identity-mfa) a più fattori nella fase Identity.</span><span class="sxs-lookup"><span data-stu-id="bd818-146">See the [Set up multi-factor authentication](identity-secure-user-sign-ins.md#identity-mfa) step in the Identity phase for information and links to deploy multi-factor authentication in production.</span></span>
    
## <a name="next-step"></a><span data-ttu-id="bd818-147">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="bd818-147">Next step</span></span>

<span data-ttu-id="bd818-148">Esplorare altre caratteristiche e funzionalità [identità](m365-enterprise-test-lab-guides.md#identity) nell'ambiente di test.</span><span class="sxs-lookup"><span data-stu-id="bd818-148">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="bd818-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bd818-149">See also</span></span>

[<span data-ttu-id="bd818-150">Fase 2: identità</span><span class="sxs-lookup"><span data-stu-id="bd818-150">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="bd818-151">Guide al lab di test di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="bd818-151">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

<span data-ttu-id="bd818-152">[Distribuzione di Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="bd818-152">[Microsoft 365 Enterprise deployment](deploy-microsoft-365-enterprise.md)</span></span>

[<span data-ttu-id="bd818-153">Documentazione di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="bd818-153">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
