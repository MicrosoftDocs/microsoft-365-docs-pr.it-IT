---
title: Reimpostazione della password per l'ambiente di testing di Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/19/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: "Riepilogo: informazioni sulla configurazione e sul test di reimpostazione della password per l'ambiente di testing di Microsoft 365."
ms.openlocfilehash: 30ce8517d1b0eb8967bd7cb26abba780d81eb8b0
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2019
ms.locfileid: "33353157"
---
# <a name="password-reset-for-your-microsoft-365-test-environment"></a><span data-ttu-id="0b0a0-103">Reimpostazione della password per l'ambiente di testing di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0b0a0-103">Password reset for your Microsoft 365 test environment</span></span>

<span data-ttu-id="0b0a0-104">La reimpostazione self-service (SSPR) di Azure Active Directory (AD Azure) consente agli utenti di reimpostare o sbloccare le proprie password o account.</span><span class="sxs-lookup"><span data-stu-id="0b0a0-104">Azure AD self-service password reset (SSPR) allows users to reset or unlock their passwords or accounts.</span></span> 

<span data-ttu-id="0b0a0-105">Questo articolo descrive come configurare e testare la reimpostazione della password nel proprio ambiente di test di Microsoft 365 in tre fasi:</span><span class="sxs-lookup"><span data-stu-id="0b0a0-105">This article describes how you can configure and test password resets in your Microsoft 365 test environment in two phases:</span></span>

1.  <span data-ttu-id="0b0a0-106">Creare l'ambiente di testing di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="0b0a0-106">Create the Microsoft 365 Enterprise test environment.</span></span>
2.  <span data-ttu-id="0b0a0-107">Attivare il writeback delle password.</span><span class="sxs-lookup"><span data-stu-id="0b0a0-107">Enable password writeback.</span></span>
3.  <span data-ttu-id="0b0a0-108">Configurare e testare la reimpostazione della password per l'account utente 2.</span><span class="sxs-lookup"><span data-stu-id="0b0a0-108">Configure and test password reset for the User 2 account.</span></span>
    
![Guide del laboratorio di testing per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="0b0a0-110">Fare clic [qui](https://aka.ms/m365etlgstack) per consultare una mappa di tutti gli articoli relativi alla guida al lab test di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="0b0a0-110">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="0b0a0-111">Fase 1: configurare la sincronizzazione hash delle password per l'ambiente di testing di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0b0a0-111">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="0b0a0-p101">Prima di tutto, seguire le istruzioni riportate in [Sincronizzazione hash delle password](password-hash-sync-m365-ent-test-environment.md). Di seguito è riportata la configurazione risultante.</span><span class="sxs-lookup"><span data-stu-id="0b0a0-p101">First, follow the instructions in [password hash synchronization](password-hash-sync-m365-ent-test-environment.md). Here is your resulting configuration.</span></span>
  
![L'organizzazione simulata con ambiente di testing per la sincronizzazione hash delle password](media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="0b0a0-115">Questa configurazione è costituita da:</span><span class="sxs-lookup"><span data-stu-id="0b0a0-115">This configuration consists of:</span></span> 
  
- <span data-ttu-id="0b0a0-116">Abbonamenti di valutazione o a pagamento a Office 365 E5 ed EMS E5.</span><span class="sxs-lookup"><span data-stu-id="0b0a0-116">Office 365 E5 and EMS E5 trial or paid subscriptions.</span></span>
- <span data-ttu-id="0b0a0-117">Una intranet dell’organizzazione semplificata connessa a Internet e costituita dalle macchine virtuali DC1 APP1 e CLIENT1 in una sottorete di una rete virtuale Azure.</span><span class="sxs-lookup"><span data-stu-id="0b0a0-117">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="0b0a0-118">Azure AD Connect viene eseguito in APP1 per sincronizzare il dominio TESTLAB di Active Directory Domain Services (AD DS) per il tenant Azure Active Directory degli abbonamenti a Office 365 ed EMS E5.</span><span class="sxs-lookup"><span data-stu-id="0b0a0-118">Azure AD Connect runs on APP1 to synchronize the TESTLAB Active Directory Domain Services (AD DS) domain to the Azure AD tenant of your Office 365 and EMS E5 subscriptions periodically.</span></span>


## <a name="phase-2-enable-password-writeback"></a><span data-ttu-id="0b0a0-119">Fase 2: Abilitare il writeback delle password</span><span class="sxs-lookup"><span data-stu-id="0b0a0-119">Phase 2: Enable password writeback for the TESTLAB AD DS domain</span></span>

<span data-ttu-id="0b0a0-120">Seguire le istruzioni in[Fase 2 delle guide al lab di test sul writeback delle password](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span><span class="sxs-lookup"><span data-stu-id="0b0a0-120">Next, follow the instructions in [Phase 2 of the password writeback](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain) Test Lab Guide.</span></span>

<span data-ttu-id="0b0a0-121">Per usare la reimpostazione delle password è necessario abilitare il writeback delle password.</span><span class="sxs-lookup"><span data-stu-id="0b0a0-121">You must have password writeback enabled to use password reset.</span></span>
  
## <a name="phase-3-configure-and-test-password-reset"></a><span data-ttu-id="0b0a0-122">Fase 3: Configurare e testare la reimpostazione della password</span><span class="sxs-lookup"><span data-stu-id="0b0a0-122">Phase 2: Configure and test password reset</span></span>

<span data-ttu-id="0b0a0-123">In questa fase, è possibile configurare la reimpostazione della password nel tenant di Azure AD attraverso l'appartenenza a un gruppo e quindi verificarne il funzionamento.</span><span class="sxs-lookup"><span data-stu-id="0b0a0-123">In this phase, you configure password reset in the Azure AD tenant through group membership, and then verify that it works.</span></span>

<span data-ttu-id="0b0a0-124">Innanzitutto, abilitare la reimpostazione della password per gli account in un gruppo specifico di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="0b0a0-124">First, enable password reset for the accounts in a specific Azure AD group.</span></span>

1. <span data-ttu-id="0b0a0-125">Aprire [https://portal.azure.com](https://portal.azure.com) da un'istanza privata del browser, quindi accedere usando le credenziali dell'account di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="0b0a0-125">From a private instance of your browser, open [https://portal.azure.com](https://portal.azure.com), and then sign in with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="0b0a0-126">Nel portale di Azure fare clic su **Azure Active Directory > Gruppi > Nuovo gruppo**.</span><span class="sxs-lookup"><span data-stu-id="0b0a0-126">In the Azure portal, click **Azure Active Directory > Groups > New group**.</span></span>
3. <span data-ttu-id="0b0a0-p102">Impostare **Tipo di gruppo** su **Sicurezza**, **Nome del gruppo** su **Reimpostazione della password** e **Tipo di appartenenza** su **Assegnato**. Fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="0b0a0-p102">Set the **Group type** to **Security**, **Group name** to **PWReset**, and the **Membership type** to **Assigned**. Click **Create**.</span></span>
5. <span data-ttu-id="0b0a0-129">Fare clic sul gruppo **Reimpostazione della password** nell'elenco, quindi fare clic su **Membri**.</span><span class="sxs-lookup"><span data-stu-id="0b0a0-129">Click the **PWReset** group in the list, and then click **Members**.</span></span>
6. <span data-ttu-id="0b0a0-p103">Fare clic su **Aggiungi membri**, su **Utente 2**, quindi su **Seleziona**. Chiudere le pagine **Reimpostazione della password** e **Gruppo**.</span><span class="sxs-lookup"><span data-stu-id="0b0a0-p103">Click **Add members**, click **User 2**, and then click **Select**. Close the **PWReset** and **Group** pages.</span></span>
7. <span data-ttu-id="0b0a0-132">Nella pagina di Azure Active Directory, fare clic su **Reimpostazione della password**.</span><span class="sxs-lookup"><span data-stu-id="0b0a0-132">On the Azure Active Directory page, click **Password reset**.</span></span>
8. <span data-ttu-id="0b0a0-133">Dalla pagina **Proprietà**, sotto l'opzione **Reimpostazione password self-service abilitata**, scegliere **Selezionato**.</span><span class="sxs-lookup"><span data-stu-id="0b0a0-133">From the **Properties** page, under the option **Self Service Password Reset Enabled**, choose **Selected**.</span></span>
9. <span data-ttu-id="0b0a0-134">Da **Seleziona gruppo**, selezionare **Reimpostazione della password**, quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="0b0a0-134">From **Select group**, select **PWReset**, and then click **Save**.</span></span>
10. <span data-ttu-id="0b0a0-135">Chiudere l'istanza privata del browser.</span><span class="sxs-lookup"><span data-stu-id="0b0a0-135">Close the private browser instance.</span></span>

<span data-ttu-id="0b0a0-136">Successivamente, testare la reimpostazione della password per l'account utente 2.</span><span class="sxs-lookup"><span data-stu-id="0b0a0-136">Next, you test password reset for the User 2 account.</span></span>

1. <span data-ttu-id="0b0a0-137">Aprire una nuova istanza privata del browser e passare alla pagina [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).</span><span class="sxs-lookup"><span data-stu-id="0b0a0-137">Open a new private browser instance and browse to [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).</span></span>
2. <span data-ttu-id="0b0a0-138">Accedere con le credenziali dell'account utente 2.</span><span class="sxs-lookup"><span data-stu-id="0b0a0-138">Sign in with the User 2 account credentials.</span></span>
3. <span data-ttu-id="0b0a0-139">In \*\*Mantenere l'accesso all'account \*\*, inserire il proprio numero di telefono cellulare e l'account di posta elettronica personale o aziendale per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="0b0a0-139">In **Don’t lose access to your account**, set the authentication phone to your mobile phone number and the authentication email to your work or personal email account.</span></span>
4. <span data-ttu-id="0b0a0-140">Dopo che sono stati verificati entrambi, fare clic su **Approvato** e chiudere l'istanza privata del browser.</span><span class="sxs-lookup"><span data-stu-id="0b0a0-140">After both are verified, click **Looks good** and close the private instance of the browser.</span></span>
5. <span data-ttu-id="0b0a0-141">Aprire una nuova istanza del browser privata e accedere a [https://aka.ms/sspr](https://aka.ms/sspr).</span><span class="sxs-lookup"><span data-stu-id="0b0a0-141">Open a new private browser instance and go to [https://aka.ms/sspr](https://aka.ms/sspr).</span></span>
6. <span data-ttu-id="0b0a0-142">Accedere con le credenziali dell'account utente 2, digitare i caratteri del CAPTCHA e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="0b0a0-142">Sign in with the User 2 account credentials, type the characters from the CAPTCHA, and then click **Next**.</span></span>
8. <span data-ttu-id="0b0a0-p104">Come **primo passaggio di verifica**, fare clic su **Inviare un messaggio all'indirizzo di posta elettronica alternativo**, quindi fare clic su **Posta elettronica**. All'avvenuta ricezione, digitare il codice di verifica e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="0b0a0-p104">For **verification step 1**, click **Email my alternate email**, and then click **Email**. When you receive the email, type the verification code, and then click **Next**.</span></span>
9. <span data-ttu-id="0b0a0-p105">In **Recuperare l'account**, digitare la nuova password per l'account utente 2 e quindi fare clic su **Fine**. Annotare la password dell'account utente 2 modificata e archiviarla in un luogo sicuro.</span><span class="sxs-lookup"><span data-stu-id="0b0a0-p105">In **Get back into your account**, type a new password for the User 2 account, and then click **Finish**. Note the changed password of the User 2 account and store it in a safe location.</span></span>
10. <span data-ttu-id="0b0a0-147">In una scheda separata del browser stesso, passare a [ https://portal.office.com ](https://portal.office.com), quindi accedere con il nome dell'account utente 2 e la nuova password.</span><span class="sxs-lookup"><span data-stu-id="0b0a0-147">In a separate tab of the same browser, go to [https://portal.office.com](https://portal.office.com), and then sign in with the User 2 account name and its new password. You should see the Office Home page.</span></span> <span data-ttu-id="0b0a0-148">Verrà visualizzata la pagina **Microsoft Office Home**.</span><span class="sxs-lookup"><span data-stu-id="0b0a0-148">You should see the **Microsoft Office Home** page.</span></span>

<span data-ttu-id="0b0a0-149">Vedere il passaggio [Semplificare la reimpostazione della password](identity-password-reset.md#identity-pw-reset) nella fase Identità per informazioni e collegamenti per configurare la reimpostazione della password.</span><span class="sxs-lookup"><span data-stu-id="0b0a0-149">See the [Simplify password resets](identity-password-reset.md#identity-pw-reset) step in the Identity phase for information and links to configure password resets in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="0b0a0-150">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="0b0a0-150">Next step</span></span>

<span data-ttu-id="0b0a0-151">Esplorare altre caratteristiche e funzionalità [identità](m365-enterprise-test-lab-guides.md#identity) nell'ambiente di test.</span><span class="sxs-lookup"><span data-stu-id="0b0a0-151">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="0b0a0-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0b0a0-152">See also</span></span>

[<span data-ttu-id="0b0a0-153">Guide al lab di test di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="0b0a0-153">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="0b0a0-154">Distribuzione di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="0b0a0-154">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="0b0a0-155">Documentazione di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="0b0a0-155">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
