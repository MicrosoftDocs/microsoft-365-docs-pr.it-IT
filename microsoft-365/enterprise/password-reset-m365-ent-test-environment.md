---
title: Reimpostazione della password per l'ambiente di testing di Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/13/2019
audience: ITPro
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
ms.openlocfilehash: c8d5ed0c7feac98afd3230a305f4ab1f850ca7f8
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42066142"
---
# <a name="password-reset-for-your-microsoft-365-test-environment"></a><span data-ttu-id="b937d-103">Reimpostazione della password per l'ambiente di testing di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b937d-103">Password reset for your Microsoft 365 test environment</span></span>

<span data-ttu-id="b937d-104">*Questa guida al lab di test può essere usata solo per ambienti di testing di Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="b937d-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="b937d-105">La reimpostazione self-service (SSPR) di Azure Active Directory (AD Azure) consente agli utenti di reimpostare o sbloccare le proprie password o account.</span><span class="sxs-lookup"><span data-stu-id="b937d-105">Azure Active Directory (Azure AD) self-service password reset (SSPR) allows users to reset or unlock their passwords or accounts.</span></span> 

<span data-ttu-id="b937d-106">Questo articolo descrive come configurare e testare la reimpostazione della password nel proprio ambiente di test di Microsoft 365 in tre fasi:</span><span class="sxs-lookup"><span data-stu-id="b937d-106">This article describes how you can configure and test password resets in your Microsoft 365 test environment in three phases:</span></span>

1.  <span data-ttu-id="b937d-107">Creare l'ambiente di testing di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="b937d-107">Create the Microsoft 365 Enterprise test environment.</span></span>
2.  <span data-ttu-id="b937d-108">Attivare il writeback delle password.</span><span class="sxs-lookup"><span data-stu-id="b937d-108">Enable password writeback.</span></span>
3.  <span data-ttu-id="b937d-109">Configurare e testare la reimpostazione della password per l'account utente 3.</span><span class="sxs-lookup"><span data-stu-id="b937d-109">Configure and test password reset for the User 3 account.</span></span>
    
![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="b937d-111">Fare clic [qui](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) per consultare una mappa di tutti gli articoli relativi alla guida al lab test di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="b937d-111">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="b937d-112">Fase 1: configurare la sincronizzazione hash delle password per l'ambiente di testing di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b937d-112">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="b937d-p101">Prima di tutto, seguire le istruzioni riportate in [Sincronizzazione hash delle password](password-hash-sync-m365-ent-test-environment.md). Di seguito è riportata la configurazione risultante.</span><span class="sxs-lookup"><span data-stu-id="b937d-p101">First, follow the instructions in [password hash synchronization](password-hash-sync-m365-ent-test-environment.md). Here is your resulting configuration.</span></span>
  
![L'organizzazione simulata con ambiente di testing per la sincronizzazione hash delle password](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="b937d-116">Questa configurazione è costituita da:</span><span class="sxs-lookup"><span data-stu-id="b937d-116">This configuration consists of:</span></span> 
  
- <span data-ttu-id="b937d-117">Abbonamenti di valutazione o a pagamento a Microsoft 365 E5 o a Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="b937d-117">Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions.</span></span>
- <span data-ttu-id="b937d-118">Una intranet dell’organizzazione semplificata connessa a Internet e costituita dalle macchine virtuali DC1 APP1 e CLIENT1 in una sottorete di una rete virtuale Azure.</span><span class="sxs-lookup"><span data-stu-id="b937d-118">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="b937d-119">Azure AD Connect viene eseguito su APP1 per sincronizzare il dominio TESTLAB di Active Directory Domain Services con il tenant di Azure AD dell'abbonamento a Microsoft 365 o a Office 365.</span><span class="sxs-lookup"><span data-stu-id="b937d-119">Azure AD Connect runs on APP1 to synchronize the TESTLAB Active Directory Domain Services (AD DS) domain to the Azure AD tenant of your Microsoft 365 or Office 365 subscription.</span></span>

## <a name="phase-2-enable-password-writeback"></a><span data-ttu-id="b937d-120">Fase 2: Abilitare il writeback delle password</span><span class="sxs-lookup"><span data-stu-id="b937d-120">Phase 2: Enable password writeback</span></span>

<span data-ttu-id="b937d-121">Seguire le istruzioni in[Fase 2 delle guide al lab di test sul writeback delle password](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span><span class="sxs-lookup"><span data-stu-id="b937d-121">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span></span>

<span data-ttu-id="b937d-122">Per usare la reimpostazione delle password è necessario abilitare il writeback delle password.</span><span class="sxs-lookup"><span data-stu-id="b937d-122">You must have password writeback enabled to use password reset.</span></span>
  
## <a name="phase-3-configure-and-test-password-reset"></a><span data-ttu-id="b937d-123">Fase 3: Configurare e testare la reimpostazione della password</span><span class="sxs-lookup"><span data-stu-id="b937d-123">Phase 3: Configure and test password reset</span></span>

<span data-ttu-id="b937d-124">In questa fase, è possibile configurare la reimpostazione della password nel tenant di Azure AD attraverso l'appartenenza a un gruppo e quindi verificarne il funzionamento.</span><span class="sxs-lookup"><span data-stu-id="b937d-124">In this phase, you configure password reset in the Azure AD tenant through group membership, and then verify that it works.</span></span>

<span data-ttu-id="b937d-125">Innanzitutto, abilitare la reimpostazione della password per gli account in un gruppo specifico di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="b937d-125">First, enable password reset for the accounts in a specific Azure AD group.</span></span>

1. <span data-ttu-id="b937d-126">Aprire [https://portal.azure.com](https://portal.azure.com) da un'istanza privata del browser, quindi accedere usando le credenziali dell'account di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="b937d-126">From a private instance of your browser, open [https://portal.azure.com](https://portal.azure.com), and then sign in with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="b937d-127">Nel portale di Azure fare clic su **Azure Active Directory > Gruppi > Nuovo gruppo**.</span><span class="sxs-lookup"><span data-stu-id="b937d-127">In the Azure portal, click **Azure Active Directory > Groups > New group**.</span></span>
3. <span data-ttu-id="b937d-128">Impostare **Tipo di gruppo** su **Sicurezza**, **Nome del gruppo** su **Reimpostazione della password** e **Tipo di appartenenza** su **Assegnato**.</span><span class="sxs-lookup"><span data-stu-id="b937d-128">Set the **Group type** to **Security**, **Group name** to **PWReset**, and the **Membership type** to **Assigned**.</span></span> 
4. <span data-ttu-id="b937d-129">Fare clic su **Membri**, trovare e selezionare **Utente 3**, quindi fare clic su **Seleziona** e infine fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="b937d-129">Click **Members**, find and select **User 3**, and then click **Select**, and then click **Create**.</span></span>
5. <span data-ttu-id="b937d-130">Chiudere il riquadro **Gruppi**.</span><span class="sxs-lookup"><span data-stu-id="b937d-130">Close the **Groups** pane.</span></span>
6. <span data-ttu-id="b937d-131">Nel menu di spostamento a sinistra del riquadro di Azure Active Directory fare clic su **Reimpostazione password**.</span><span class="sxs-lookup"><span data-stu-id="b937d-131">In the Azure Active Directory pane, click **Password reset** in the left navigation.</span></span>
7. <span data-ttu-id="b937d-132">Nel riquadro **Reimpostazione password-Proprietà** scegliere **Selezionato** sotto l'opzione **Reimpostazione password self-service abilitata**.</span><span class="sxs-lookup"><span data-stu-id="b937d-132">In the **Password reset-Properties** pane, under the option **Self Service Password Reset Enabled**, choose **Selected**.</span></span>
8. <span data-ttu-id="b937d-133">Fare clic su **Seleziona gruppo**, selezionare il gruppo **PWReset** e quindi fare clic su **Seleziona > Salva**.</span><span class="sxs-lookup"><span data-stu-id="b937d-133">Click **Select group**, select the **PWReset** group, and then click **Select > Save**.</span></span>
9. <span data-ttu-id="b937d-134">Chiudere l'istanza privata del browser.</span><span class="sxs-lookup"><span data-stu-id="b937d-134">Close the private browser instance.</span></span>

<span data-ttu-id="b937d-135">Successivamente, testare la reimpostazione della password per l'account utente 3.</span><span class="sxs-lookup"><span data-stu-id="b937d-135">Next, you test password reset for the User 3 account.</span></span>

1. <span data-ttu-id="b937d-136">Aprire una nuova istanza privata del browser e passare alla pagina [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).</span><span class="sxs-lookup"><span data-stu-id="b937d-136">Open a new private browser instance and browse to [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).</span></span>
2. <span data-ttu-id="b937d-137">Accedere con le credenziali dell'account utente 3.</span><span class="sxs-lookup"><span data-stu-id="b937d-137">Sign in with the User 3 account credentials.</span></span>
3. <span data-ttu-id="b937d-138">In \*\*Sono necessarie altre informazioni \*\* fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="b937d-138">In **More information required**, click **Next**.</span></span> 
5. <span data-ttu-id="b937d-139">In \*\*Mantenere l'accesso all'account \*\*, inserire il proprio numero di telefono cellulare e l'account di posta elettronica personale o aziendale per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="b937d-139">In **Don’t lose access to your account**, set the authentication phone to your mobile phone number and the authentication email to your work or personal email account.</span></span>
7. <span data-ttu-id="b937d-140">Dopo che sono stati verificati entrambi, fare clic su **Approvato** e chiudere l'istanza privata del browser.</span><span class="sxs-lookup"><span data-stu-id="b937d-140">After both are verified, click **Looks good** and close the private instance of the browser.</span></span>
8. <span data-ttu-id="b937d-141">Aprire una nuova istanza del browser privata e accedere a [https://aka.ms/sspr](https://aka.ms/sspr).</span><span class="sxs-lookup"><span data-stu-id="b937d-141">Open a new private browser instance and go to [https://aka.ms/sspr](https://aka.ms/sspr).</span></span>
9. <span data-ttu-id="b937d-142">Digitare il nome dell'account utente 3, digitare i caratteri del CAPTCHA e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="b937d-142">Type the User 3 account name, type the characters from the CAPTCHA, and then click **Next**.</span></span>
10. <span data-ttu-id="b937d-p102">Come **primo passaggio di verifica**, fare clic su **Inviare un messaggio all'indirizzo di posta elettronica alternativo**, quindi fare clic su **Posta elettronica**. All'avvenuta ricezione, digitare il codice di verifica e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="b937d-p102">For **verification step 1**, click **Email my alternate email**, and then click **Email**. When you receive the email, type the verification code, and then click **Next**.</span></span>
11. <span data-ttu-id="b937d-145">In **Tornare all'account** digitare una nuova password per l'account utente 3 e quindi fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="b937d-145">In **Get back into your account**, type a new password for the User 3 account, and then click **Finish**.</span></span> <span data-ttu-id="b937d-146">Prendere nota della password cambiata dell'account utente 3 e conservarla in un luogo sicuro.</span><span class="sxs-lookup"><span data-stu-id="b937d-146">Note the changed password of the User 3 account and store it in a safe location.</span></span>
12. <span data-ttu-id="b937d-147">In una scheda separata del browser stesso, passare a [https://portal.office.com](https://portal.office.com) e quindi accedere con il nome dell'account utente 3 e la nuova password.</span><span class="sxs-lookup"><span data-stu-id="b937d-147">In a separate tab of the same browser, go to [https://portal.office.com](https://portal.office.com), and then sign in with the User 3 account name and its new password.</span></span> <span data-ttu-id="b937d-148">Verrà visualizzata la **Home Page Microsoft Office**.</span><span class="sxs-lookup"><span data-stu-id="b937d-148">You should see the **Microsoft Office Home** page.</span></span>

<span data-ttu-id="b937d-149">Vedere il passaggio [Semplificare la reimpostazione della password](identity-secure-your-passwords.md#identity-pw-reset) nella fase Identità per informazioni e collegamenti per configurare la reimpostazione della password.</span><span class="sxs-lookup"><span data-stu-id="b937d-149">See the [Simplify password resets](identity-secure-your-passwords.md#identity-pw-reset) step in the Identity phase for information and links to configure password resets in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="b937d-150">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="b937d-150">Next step</span></span>

<span data-ttu-id="b937d-151">Esplorare altre caratteristiche e funzionalità [identità](m365-enterprise-test-lab-guides.md#identity) nell'ambiente di test.</span><span class="sxs-lookup"><span data-stu-id="b937d-151">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="b937d-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b937d-152">See also</span></span>

[<span data-ttu-id="b937d-153">Guide al lab di test di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="b937d-153">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="b937d-154">Distribuzione di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="b937d-154">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="b937d-155">Documentazione di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="b937d-155">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
