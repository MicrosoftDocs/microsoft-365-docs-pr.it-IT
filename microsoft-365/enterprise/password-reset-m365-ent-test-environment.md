---
title: Reimpostazione della password per l'ambiente di testing di Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/30/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: "Riepilogo: informazioni sulla configurazione e sul test di reimpostazione della password per l'ambiente di testing di Microsoft 365."
ms.openlocfilehash: a90cb362a2831bf0bcf3fe05932e3a4345d52b2e
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868861"
---
# <a name="password-reset-for-your-microsoft-365-test-environment"></a><span data-ttu-id="be35c-103">Reimpostazione della password per l'ambiente di testing di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="be35c-103">Password reset for your Microsoft 365 test environment</span></span>

<span data-ttu-id="be35c-104">La reimpostazione della password self-service di Azure AD consente agli utenti di reimpostare o sbloccare le password o gli account.</span><span class="sxs-lookup"><span data-stu-id="be35c-104">Azure AD self-service password reset (SSPR) allows users to reset or unlock their passwords or accounts.</span></span> 

<span data-ttu-id="be35c-105">Questo articolo descrive come configurare e testare le reimpostazioni della password nell'ambiente di testing di Microsoft 365 in due fasi:</span><span class="sxs-lookup"><span data-stu-id="be35c-105">This article describes how you can configure and test password resets in your Microsoft 365 test environment in two phases:</span></span>

1.  <span data-ttu-id="be35c-106">Creare l'ambiente di testing dell'organizzazione simulata di Microsoft 365 con per la sincronizzazione hash delle password.</span><span class="sxs-lookup"><span data-stu-id="be35c-106">Create the Microsoft 365 simulated enterprise test environment with password hash synchronization.</span></span>
2.  <span data-ttu-id="be35c-107">Configurare e testare la reimpostazione della password per l'account utente 2.</span><span class="sxs-lookup"><span data-stu-id="be35c-107">Configure and test password reset for the User 2 account.</span></span>
    
![Guide del laboratorio di testing per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="be35c-109">Fare clic [qui](https://aka.ms/m365etlgstack) per consultare una mappa di tutti gli articoli relativi alla guida al lab test di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="be35c-109">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="be35c-110">Fase 1: configurare la sincronizzazione hash delle password per l'ambiente di testing di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="be35c-110">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="be35c-p101">Seguire le istruzioni riportate in [sincronizzazione hash delle password per Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Di seguito è riportata la configurazione risultante.</span><span class="sxs-lookup"><span data-stu-id="be35c-p101">Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Here is your resulting configuration.</span></span>
  
![L'organizzazione simulata con ambiente di testing per l'autenticazione pass-through](media/pass-through-auth-m365-ent-test-environment/Phase2.png)
  
<span data-ttu-id="be35c-114">Questa configurazione è costituita da:</span><span class="sxs-lookup"><span data-stu-id="be35c-114">This configuration consists of:</span></span> 
  
- <span data-ttu-id="be35c-115">Abbonamenti di valutazione o permanenti a Office 365 E5 ed EMS E5.</span><span class="sxs-lookup"><span data-stu-id="be35c-115">Office 365 E5 and EMS E5 trial or permanent subscriptions.</span></span>
- <span data-ttu-id="be35c-116">Una intranet dell’organizzazione semplificata connessa a Internet e costituita dalle macchine virtuali DC1 APP1 e CLIENT1 in una sottorete di una rete virtuale Azure.</span><span class="sxs-lookup"><span data-stu-id="be35c-116">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="be35c-117">Azure AD Connect viene eseguito su APP1 per sincronizzare il dominio TESTLAB Windows Server AD per il tenant Azure AD degli abbonamenti a Office 365 ed EMS E5.</span><span class="sxs-lookup"><span data-stu-id="be35c-117">Azure AD Connect runs on APP1 to synchronize the TESTLAB Windows Server AD domain to the Azure AD tenant of your Office 365 and EMS E5 subscriptions.</span></span>

## <a name="phase-2-configure-and-test-password-reset"></a><span data-ttu-id="be35c-118">Fase 2: configurare e testare la reimpostazione della password</span><span class="sxs-lookup"><span data-stu-id="be35c-118">Phase 2: Configure and test password reset</span></span>

<span data-ttu-id="be35c-119">In questa fase, è possibile configurare la reimpostazione della password nel tenant di Azure AD attraverso l'appartenenza a un gruppo e quindi verificarne il funzionamento.</span><span class="sxs-lookup"><span data-stu-id="be35c-119">In this phase, you configure password reset in the Azure AD tenant through group membership, and then verify that it works.</span></span>

<span data-ttu-id="be35c-120">Innanzitutto, abilitare la reimpostazione della password per gli account in un gruppo specifico di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="be35c-120">First, enable password reset for the accounts in a specific Azure AD group.</span></span>

1. <span data-ttu-id="be35c-121">Aprire [https://portal.azure.com](https://portal.azure.com) da un'istanza privata del browser, quindi accedere usando le credenziali dell'account di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="be35c-121">From a private instance of your browser, open [https://portal.azure.com](https://portal.azure.com), and then sign in with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="be35c-122">Nel portale di Azure fare clic su **Azure Active Directory > Gruppi > Nuovo gruppo**.</span><span class="sxs-lookup"><span data-stu-id="be35c-122">In the Azure portal, click **Azure Active Directory > Groups > New group**.</span></span>
3. <span data-ttu-id="be35c-p102">Impostare **Tipo di gruppo** su **Sicurezza**, **Nome del gruppo** su **Reimpostazione della password** e **Tipo di appartenenza** su **Assegnato**. Fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="be35c-p102">Set the **Group type** to **Security**, **Group name** to **PWReset**, and the **Membership type** to **Assigned**. Click **Create**.</span></span>
5. <span data-ttu-id="be35c-125">Fare clic sul gruppo **Reimpostazione della password** nell'elenco, quindi fare clic su **Membri**.</span><span class="sxs-lookup"><span data-stu-id="be35c-125">Click the **PWReset** group in the list, and then click **Members**.</span></span>
6. <span data-ttu-id="be35c-p103">Fare clic su **Aggiungi membri**, su **Utente 2**, quindi su **Seleziona**. Chiudere le pagine **Reimpostazione della password** e **Gruppo**.</span><span class="sxs-lookup"><span data-stu-id="be35c-p103">Click **Add members**, click **User 2**, and then click **Select**. Close the **PWReset** and **Group** pages.</span></span>
7. <span data-ttu-id="be35c-128">Nella pagina di Azure Active Directory, fare clic su **Reimpostazione della password**.</span><span class="sxs-lookup"><span data-stu-id="be35c-128">On the Azure Active Directory page, click **Password reset**.</span></span>
8. <span data-ttu-id="be35c-129">Dalla pagina **Proprietà**, sotto l'opzione **Reimpostazione password self-service abilitata**, scegliere **Selezionato**.</span><span class="sxs-lookup"><span data-stu-id="be35c-129">From the **Properties** page, under the option **Self Service Password Reset Enabled**, choose **Selected**.</span></span>
9. <span data-ttu-id="be35c-130">Da **Seleziona gruppo**, selezionare **Reimpostazione della password**, quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="be35c-130">From **Select group**, select **PWReset**, and then click **Save**.</span></span>
10. <span data-ttu-id="be35c-131">Chiudere l'istanza privata del browser.</span><span class="sxs-lookup"><span data-stu-id="be35c-131">Close the private browser instance.</span></span>

<span data-ttu-id="be35c-132">Successivamente, testare la reimpostazione della password per l'account utente 2.</span><span class="sxs-lookup"><span data-stu-id="be35c-132">Next, you test password reset for the User 2 account.</span></span>

1. <span data-ttu-id="be35c-133">Aprire una nuova istanza privata del browser e passare alla pagina [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).</span><span class="sxs-lookup"><span data-stu-id="be35c-133">Open a new private browser instance and browse to [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).</span></span>
2. <span data-ttu-id="be35c-134">Accedere con le credenziali dell'account utente 2.</span><span class="sxs-lookup"><span data-stu-id="be35c-134">Sign in with the User 2 account credentials.</span></span>
3. <span data-ttu-id="be35c-135">In \*\*Mantenere l'accesso all'account \*\*, inserire il proprio numero di telefono cellulare e l'account di posta elettronica personale o aziendale per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="be35c-135">In **Don’t lose access to your account**, set the authentication phone to your mobile phone number and the authentication email to your work or personal email account.</span></span>
4. <span data-ttu-id="be35c-136">Dopo che sono stati verificati entrambi, fare clic su **Approvato** e chiudere l'istanza privata del browser.</span><span class="sxs-lookup"><span data-stu-id="be35c-136">After both are verified, click **Looks good** and close the private instance of the browser.</span></span>
5. <span data-ttu-id="be35c-137">Aprire una nuova istanza del browser privata e accedere a [https://aka.ms/sspr](https://aka.ms/sspr).</span><span class="sxs-lookup"><span data-stu-id="be35c-137">Open a new private browser instance and go to [https://aka.ms/sspr](https://aka.ms/sspr).</span></span>
6. <span data-ttu-id="be35c-138">Accedere con le credenziali dell'account utente 2, digitare i caratteri del CAPTCHA e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="be35c-138">Sign in with the User 2 account credentials, type the characters from the CAPTCHA, and then click **Next**.</span></span>
8. <span data-ttu-id="be35c-p104">Come **primo passaggio di verifica**, fare clic su **Inviare un messaggio all'indirizzo di posta elettronica alternativo**, quindi fare clic su **Posta elettronica**. All'avvenuta ricezione, digitare il codice di verifica e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="be35c-p104">For **verification step 1**, click **Email my alternate email**, and then click **Email**. When you receive the email, type the verification code, and then click **Next**.</span></span>
9. <span data-ttu-id="be35c-p105">In **Recuperare l'account**, digitare la nuova password per l'account utente 2 e quindi fare clic su **Fine**. Annotare la password dell'account utente 2 modificata e archiviarla in un luogo sicuro.</span><span class="sxs-lookup"><span data-stu-id="be35c-p105">In **Get back into your account**, type a new password for the User 2 account, and then click **Finish**. Note the changed password of the User 2 account and store it in a safe location.</span></span>
10. <span data-ttu-id="be35c-p106">In una scheda separata dello stesso browser, digitare [https://portal.office.com](https://portal.office.com), quindi accedere con il nome dell'account utente 2 e la nuova password. Dovrebbe essere visualizzata la pagina **Office Home**.</span><span class="sxs-lookup"><span data-stu-id="be35c-p106">In a separate tab of the same browser, go to [https://portal.office.com](https://portal.office.com), and then sign in with the User 2 account name and its new password. You should see the **Office Home** page.</span></span>

<span data-ttu-id="be35c-145">Vedere il passaggio [Semplificare la reimpostazione della password](identity-password-reset.md) nella fase Identità per informazioni e collegamenti per configurare la reimpostazione della password.</span><span class="sxs-lookup"><span data-stu-id="be35c-145">See the [Simplify password resets](identity-password-reset.md) step in the Identity phase for information and links to configure password resets in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="be35c-146">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="be35c-146">Next step</span></span>

<span data-ttu-id="be35c-147">Esplorare altre caratteristiche e funzionalità [identità](m365-enterprise-test-lab-guides.md#identity) nell'ambiente di test.</span><span class="sxs-lookup"><span data-stu-id="be35c-147">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="be35c-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="be35c-148">See also</span></span>

[<span data-ttu-id="be35c-149">Guide al lab di test di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="be35c-149">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="be35c-150">Distribuzione di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="be35c-150">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="be35c-151">Documentazione di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="be35c-151">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
