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
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: "Riepilogo: informazioni sulla configurazione e sul test di reimpostazione della password per l'ambiente di testing di Microsoft 365."
ms.openlocfilehash: 13169824866e91c1a09d412a875d2f4ce4391fa8
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339383"
---
# <a name="password-reset-for-your-microsoft-365-test-environment"></a><span data-ttu-id="8bbe6-103">Reimpostazione della password per l'ambiente di testing di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8bbe6-103">Password reset for your Microsoft 365 test environment</span></span>

<span data-ttu-id="8bbe6-104">*Questa guida al laboratorio di testing può essere utilizzata solo per Microsoft 365 per ambienti di test aziendali.*</span><span class="sxs-lookup"><span data-stu-id="8bbe6-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="8bbe6-105">La reimpostazione self-service (SSPR) di Azure Active Directory (AD Azure) consente agli utenti di reimpostare o sbloccare le proprie password o account.</span><span class="sxs-lookup"><span data-stu-id="8bbe6-105">Azure Active Directory (Azure AD) self-service password reset (SSPR) allows users to reset or unlock their passwords or accounts.</span></span>

<span data-ttu-id="8bbe6-106">In questo articolo viene descritto come configurare e testare le reimpostazioni della password nell'Microsoft 365 di test.</span><span class="sxs-lookup"><span data-stu-id="8bbe6-106">This article describes how to configure and test password resets in your Microsoft 365 test environment.</span></span>

<span data-ttu-id="8bbe6-107">La configurazione di SSPR prevede tre fasi:</span><span class="sxs-lookup"><span data-stu-id="8bbe6-107">Setting up SSPR involves three phases:</span></span>
- [<span data-ttu-id="8bbe6-108">Fase 1: configurare la sincronizzazione hash delle password per l'ambiente di testing di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8bbe6-108">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [<span data-ttu-id="8bbe6-109">Fase 2: Abilitare il writeback delle password</span><span class="sxs-lookup"><span data-stu-id="8bbe6-109">Phase 2: Enable password writeback</span></span>](#phase-2-enable-password-writeback)
- [<span data-ttu-id="8bbe6-110">Fase 3: Configurare e testare la reimpostazione della password</span><span class="sxs-lookup"><span data-stu-id="8bbe6-110">Phase 3: Configure and test password reset</span></span>](#phase-3-configure-and-test-password-reset)
    
![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="8bbe6-112">Per una mappa visiva a tutti gli articoli dello stack Microsoft 365 per enterprise Test Lab Guide, passare a [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="8bbe6-112">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="8bbe6-113">Fase 1: configurare la sincronizzazione hash delle password per l'ambiente di testing di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8bbe6-113">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="8bbe6-114">Prima di tutto, seguire le istruzioni in [Sincronizzazione hash password](password-hash-sync-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="8bbe6-114">First, follow the instructions in [password hash synchronization](password-hash-sync-m365-ent-test-environment.md).</span></span> 

<span data-ttu-id="8bbe6-115">La configurazione risultante è simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="8bbe6-115">Your resulting configuration looks like this:</span></span>
  
![L'organizzazione simulata con ambiente di testing per la sincronizzazione hash delle password](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="8bbe6-117">Questa configurazione è costituita da:</span><span class="sxs-lookup"><span data-stu-id="8bbe6-117">This configuration consists of:</span></span>
  
- <span data-ttu-id="8bbe6-118">Un abbonamento di valutazione o a pagamento a Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="8bbe6-118">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="8bbe6-119">Intranet dell'organizzazione semplificata connessa a Internet, costituita da macchine virtuali DC1, APP1 e CLIENT1 in una subnet di una rete virtuale di Azure.</span><span class="sxs-lookup"><span data-stu-id="8bbe6-119">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>
- <span data-ttu-id="8bbe6-120">Azure AD Connect viene eseguito su APP1 per sincronizzare il dominio TESTLAB di Active Directory Domain Services con il tenant di Azure AD dell'abbonamento a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8bbe6-120">Azure AD Connect runs on APP1 to synchronize the TESTLAB Active Directory Domain Services (AD DS) domain to the Azure AD tenant of your Microsoft 365 subscription.</span></span>

## <a name="phase-2-enable-password-writeback"></a><span data-ttu-id="8bbe6-121">Fase 2: Abilitare il writeback delle password</span><span class="sxs-lookup"><span data-stu-id="8bbe6-121">Phase 2: Enable password writeback</span></span>

<span data-ttu-id="8bbe6-122">Seguire le istruzioni in[Fase 2 delle guide al lab di test sul writeback delle password](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span><span class="sxs-lookup"><span data-stu-id="8bbe6-122">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span></span>

<span data-ttu-id="8bbe6-123">Per usare la reimpostazione delle password è necessario abilitare il writeback delle password.</span><span class="sxs-lookup"><span data-stu-id="8bbe6-123">You must have password writeback enabled to use password reset.</span></span>
  
## <a name="phase-3-configure-and-test-password-reset"></a><span data-ttu-id="8bbe6-124">Fase 3: Configurare e testare la reimpostazione della password</span><span class="sxs-lookup"><span data-stu-id="8bbe6-124">Phase 3: Configure and test password reset</span></span>

<span data-ttu-id="8bbe6-125">In questa fase, configurare la reimpostazione della password nel tenant di Azure AD tramite l'appartenenza al gruppo e quindi verificare che funzioni.</span><span class="sxs-lookup"><span data-stu-id="8bbe6-125">In this phase, configure password reset in the Azure AD tenant through group membership, and then verify that it works.</span></span>

<span data-ttu-id="8bbe6-126">Innanzitutto, abilitare la reimpostazione della password per gli account in un gruppo specifico di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="8bbe6-126">First, enable password reset for the accounts in a specific Azure AD group.</span></span>

1. <span data-ttu-id="8bbe6-127">Aprire [https://portal.azure.com](https://portal.azure.com) da un'istanza privata del browser, quindi accedere usando le credenziali dell'account di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="8bbe6-127">From a private instance of your browser, open [https://portal.azure.com](https://portal.azure.com), and then sign in with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="8bbe6-128">Nel portale di Azure, **selezionare** Azure Active Directory  >    >  **Nuovo gruppo**.</span><span class="sxs-lookup"><span data-stu-id="8bbe6-128">In the Azure portal, select **Azure Active Directory** > **Groups** > **New group**.</span></span>
3. <span data-ttu-id="8bbe6-129">Impostare **Tipo di gruppo** su **Sicurezza**, **Nome del gruppo** su **Reimpostazione della password** e **Tipo di appartenenza** su **Assegnato**.</span><span class="sxs-lookup"><span data-stu-id="8bbe6-129">Set the **Group type** to **Security**, **Group name** to **PWReset**, and the **Membership type** to **Assigned**.</span></span>
4. <span data-ttu-id="8bbe6-130">Selezionare **Membri**, trovare e selezionare **Utente 3**, **selezionare Seleziona** e quindi **crea**.</span><span class="sxs-lookup"><span data-stu-id="8bbe6-130">Select **Members**, find and select **User 3**, select **Select**, and then select **Create**.</span></span>
5. <span data-ttu-id="8bbe6-131">Chiudere il riquadro **Gruppi**.</span><span class="sxs-lookup"><span data-stu-id="8bbe6-131">Close the **Groups** pane.</span></span>
6. <span data-ttu-id="8bbe6-132">Nel riquadro Azure Active Directory selezionare **Reimpostazione password** nel riquadro di spostamento sinistro.</span><span class="sxs-lookup"><span data-stu-id="8bbe6-132">In the Azure Active Directory pane, select **Password reset** in the left navigation.</span></span>
7. <span data-ttu-id="8bbe6-133">Nel riquadro **Reimpostazione password-Proprietà** scegliere **Selezionato** sotto l'opzione **Reimpostazione password self-service abilitata**.</span><span class="sxs-lookup"><span data-stu-id="8bbe6-133">In the **Password reset-Properties** pane, under the option **Self Service Password Reset Enabled**, choose **Selected**.</span></span>
8. <span data-ttu-id="8bbe6-134">Selezionare **Seleziona gruppo,** selezionare il **gruppo PWReset** e quindi **selezionare Seleziona**  >  **Salva.**</span><span class="sxs-lookup"><span data-stu-id="8bbe6-134">Select **Select group**, select the **PWReset** group, and then select **Select** > **Save**.</span></span>
9. <span data-ttu-id="8bbe6-135">Chiudere l'istanza privata del browser.</span><span class="sxs-lookup"><span data-stu-id="8bbe6-135">Close the private browser instance.</span></span>

<span data-ttu-id="8bbe6-136">Testare quindi la reimpostazione della password per l'account Utente 3.</span><span class="sxs-lookup"><span data-stu-id="8bbe6-136">Next, test password reset for the User 3 account.</span></span>

1. <span data-ttu-id="8bbe6-137">Aprire una nuova istanza privata del browser e passare alla pagina [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).</span><span class="sxs-lookup"><span data-stu-id="8bbe6-137">Open a new private browser instance and browse to [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).</span></span>
1. <span data-ttu-id="8bbe6-138">Accedere con le credenziali dell'account utente 3.</span><span class="sxs-lookup"><span data-stu-id="8bbe6-138">Sign in with the User 3 account credentials.</span></span>
1. <span data-ttu-id="8bbe6-139">In **Ulteriori informazioni necessarie** selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="8bbe6-139">In **More information required**, select **Next**.</span></span> 
1. <span data-ttu-id="8bbe6-140">In **Mantenere l'accesso all'account**, inserire il proprio numero di telefono cellulare e l'account di posta elettronica personale o aziendale per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="8bbe6-140">In **Don't lose access to your account**, set the authentication phone to your mobile phone number and the authentication email to your work or personal email account.</span></span>
1. <span data-ttu-id="8bbe6-141">Dopo aver verificato entrambi, selezionare **Sembra buono** e quindi chiudere l'istanza privata del browser.</span><span class="sxs-lookup"><span data-stu-id="8bbe6-141">After both are verified, select **Looks good**, and then close the private instance of the browser.</span></span>
1. <span data-ttu-id="8bbe6-142">In una nuova istanza privata del browser passare a [https://aka.ms/sspr](https://aka.ms/sspr) .</span><span class="sxs-lookup"><span data-stu-id="8bbe6-142">In a new private browser instance, go to [https://aka.ms/sspr](https://aka.ms/sspr).</span></span>
1. <span data-ttu-id="8bbe6-143">Immettere il nome dell'account utente 3, immettere i caratteri da CAPTCHA e quindi selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="8bbe6-143">Enter the User 3 account name, enter the characters from the CAPTCHA, and then select **Next**.</span></span>
1. <span data-ttu-id="8bbe6-144">Per **il passaggio di verifica 1,** selezionare Invia **e-mail all'indirizzo di posta** elettronica alternativo, quindi selezionare Posta **elettronica**.</span><span class="sxs-lookup"><span data-stu-id="8bbe6-144">For **verification step 1**, select **Email my alternate email**, and then select **Email**.</span></span> <span data-ttu-id="8bbe6-145">Quando si riceve il messaggio di posta elettronica, immettere il codice di verifica e quindi selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="8bbe6-145">When you receive the email, enter the verification code, and then select **Next**.</span></span>
1. <span data-ttu-id="8bbe6-146">In **Torna all'account** immettere una nuova password per l'account Utente 3 e quindi selezionare **Fine.**</span><span class="sxs-lookup"><span data-stu-id="8bbe6-146">In **Get back into your account**, enter a new password for the User 3 account, and then select **Finish**.</span></span> <span data-ttu-id="8bbe6-147">Prendere nota della password cambiata dell'account utente 3 e conservarla in un luogo sicuro.</span><span class="sxs-lookup"><span data-stu-id="8bbe6-147">Note the changed password of the User 3 account and store it in a safe location.</span></span>
1. <span data-ttu-id="8bbe6-148">In una scheda separata del browser stesso, passare a [https://admin.microsoft.com](https://admin.microsoft.com) e quindi accedere con il nome dell'account utente 3 e la nuova password.</span><span class="sxs-lookup"><span data-stu-id="8bbe6-148">In a separate tab of the same browser, go to [https://admin.microsoft.com](https://admin.microsoft.com), and then sign in with the User 3 account name and its new password.</span></span> <span data-ttu-id="8bbe6-149">Verrà visualizzata la **Home Page Microsoft Office**.</span><span class="sxs-lookup"><span data-stu-id="8bbe6-149">You should see the **Microsoft Office Home** page.</span></span>

## <a name="next-step"></a><span data-ttu-id="8bbe6-150">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="8bbe6-150">Next step</span></span>

<span data-ttu-id="8bbe6-151">Esplorare altre caratteristiche e funzionalità [identità](m365-enterprise-test-lab-guides.md#identity) nell'ambiente di test.</span><span class="sxs-lookup"><span data-stu-id="8bbe6-151">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="8bbe6-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8bbe6-152">See also</span></span>

[<span data-ttu-id="8bbe6-153">Guide ai lab di test di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="8bbe6-153">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="8bbe6-154">Panoramica di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="8bbe6-154">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="8bbe6-155">Documentazione di Microsoft 365 for enterprise</span><span class="sxs-lookup"><span data-stu-id="8bbe6-155">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)