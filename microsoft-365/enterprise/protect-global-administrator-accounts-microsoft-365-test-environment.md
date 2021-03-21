---
title: Proteggere gli account di amministratore globale nell'ambiente di testing di Microsoft 365 per le aziende
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
description: Eseguire questa procedura per proteggere gli account amministratore globale nell'ambiente di testing di Microsoft 365 per le aziende.
ms.openlocfilehash: 3eab538b59e460857e2fa195aaacf51051f94d6b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918883"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="5710a-103">Proteggere gli account di amministratore globale nell'ambiente di testing di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="5710a-103">Protect global administrator accounts in your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="5710a-104">*Questa guida al laboratorio di testing può essere utilizzata solo per gli ambienti di testing di Microsoft 365 per le aziende.*</span><span class="sxs-lookup"><span data-stu-id="5710a-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="5710a-105">È possibile impedire attacchi digitali all'organizzazione assicurando che gli account di amministratore siano il più sicuri possibile.</span><span class="sxs-lookup"><span data-stu-id="5710a-105">You can prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> 

<span data-ttu-id="5710a-106">Questo articolo descrive come usare i criteri di accesso condizionale di Azure Active Directory (Azure AD) per proteggere gli account di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="5710a-106">This article describes how to use Azure Active Directory (Azure AD) conditional access policies to protect global administrator accounts.</span></span>

<span data-ttu-id="5710a-107">La protezione degli account di amministratore globale nell'ambiente di testing di Microsoft 365 per le aziende prevede due fasi:</span><span class="sxs-lookup"><span data-stu-id="5710a-107">Protecting global administrator accounts in your Microsoft 365 for enterprise test environment involves two phases:</span></span>
- [<span data-ttu-id="5710a-108">Fase 1: creare l'ambiente di testing di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="5710a-108">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="5710a-109">Fase 2: configurare i criteri di accesso condizionale</span><span class="sxs-lookup"><span data-stu-id="5710a-109">Phase 2: Configure conditional access policies</span></span>](#phase-2-configure-conditional-access-policies)

![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="5710a-111">Per una mappa visiva a tutti gli articoli nello stack guida del laboratorio di testing di Microsoft 365 per le aziende, passare a [Microsoft 365 per enterprise Test Lab Guide Stack.](../downloads/Microsoft365EnterpriseTLGStack.pdf)</span><span class="sxs-lookup"><span data-stu-id="5710a-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="5710a-112">Fase 1: creare l'ambiente di testing di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="5710a-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="5710a-113">Se si desidera testare la protezione dell'account amministratore globale in modo leggero con i requisiti minimi, seguire le istruzioni in [Configurazione di base leggera](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="5710a-113">If you want to test global administrator account protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="5710a-114">Se si desidera testare la protezione dell'account amministratore globale in un'organizzazione simulata, seguire le istruzioni in [Autenticazione pass-through.](pass-through-auth-m365-ent-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="5710a-114">If you want to test global administrator account protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="5710a-115">Il test della protezione dell'account amministratore globale non richiede l'ambiente di testing aziendale simulato, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per Servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5710a-115">Testing global administrator account protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="5710a-116">Viene fornito qui come opzione in modo da poter testare la protezione dell'account amministratore globale e sperimentarla in un ambiente che rappresenta un'organizzazione tipica.</span><span class="sxs-lookup"><span data-stu-id="5710a-116">It is provided here as an option so that you can test global administrator account protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-conditional-access-policies"></a><span data-ttu-id="5710a-117">Fase 2: configurare i criteri di accesso condizionale</span><span class="sxs-lookup"><span data-stu-id="5710a-117">Phase 2: Configure conditional access policies</span></span>

<span data-ttu-id="5710a-118">Creare innanzitutto un nuovo account utente come amministratore globale dedicato.</span><span class="sxs-lookup"><span data-stu-id="5710a-118">First, create a new user account as a dedicated global administrator.</span></span>

1. <span data-ttu-id="5710a-119">In una scheda separata, aprire l'interfaccia di amministrazione di [Microsoft 365.](https://admin.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="5710a-119">On a separate tab, open the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span>
2. <span data-ttu-id="5710a-120">Selezionare **Utenti**  >  **Utenti attivi** e quindi Aggiungi **utente.**</span><span class="sxs-lookup"><span data-stu-id="5710a-120">Select **Users** > **Active users**, and then select **Add a user**.</span></span>
3. <span data-ttu-id="5710a-121">Nel riquadro **Aggiungi utente** immettere **DedicatedAdmin** nelle caselle **Nome,** **Nome visualizzato** e **Nome utente.**</span><span class="sxs-lookup"><span data-stu-id="5710a-121">In the **Add user** pane, enter **DedicatedAdmin** in the **First name**, **Display name**, and **Username** boxes.</span></span>
4. <span data-ttu-id="5710a-122">Selezionare **Password,** selezionare **Consenti la creazione della password** e quindi immettere una password complessa.</span><span class="sxs-lookup"><span data-stu-id="5710a-122">Select **Password**, select **Let me create the password**, and then enter a strong password.</span></span> <span data-ttu-id="5710a-123">Registrare la password per il nuovo account in una posizione sicura.</span><span class="sxs-lookup"><span data-stu-id="5710a-123">Record the password for this new account in a secure location.</span></span>
5. <span data-ttu-id="5710a-124">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="5710a-124">Select **Next**.</span></span>
6. <span data-ttu-id="5710a-125">Nel riquadro **Assegna licenze di prodotto** selezionare Microsoft **365 E5** e quindi selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="5710a-125">In the **Assign product licenses** pane, select **Microsoft 365 E5**, and then select **Next**.</span></span>
7. <span data-ttu-id="5710a-126">Nel riquadro **Impostazioni facoltative** selezionare **Ruoli**  >  **Accesso all'interfaccia di amministrazione** Amministratore  >  **globale**  >  **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="5710a-126">In the **Optional settings** pane, select **Roles** > **Admin center access** > **Global admin** > **Next**.</span></span>
8. <span data-ttu-id="5710a-127">Nel riquadro **You're almost done** selezionare **Finish adding** e quindi **close**.</span><span class="sxs-lookup"><span data-stu-id="5710a-127">On the **You're almost done** pane, select **Finish adding**, and then select **Close**.</span></span>

<span data-ttu-id="5710a-128">Successivamente, creare un nuovo gruppo denominato GlobalAdmins e aggiungerne l'account DedicatedAdmin.</span><span class="sxs-lookup"><span data-stu-id="5710a-128">Next, create a new group named GlobalAdmins and add the DedicatedAdmin account to it.</span></span>

1. <span data-ttu-id="5710a-129">Nella scheda Interfaccia di amministrazione di **Microsoft 365** selezionare **Gruppi** nel riquadro di spostamento sinistro e **quindi** gruppi .</span><span class="sxs-lookup"><span data-stu-id="5710a-129">On the **Microsoft 365 admin center** tab, select **Groups** in the left navigation, and then select **Groups**.</span></span>
2. <span data-ttu-id="5710a-130">Selezionare **Aggiungi un gruppo**.</span><span class="sxs-lookup"><span data-stu-id="5710a-130">Select **Add a group**.</span></span>
3. <span data-ttu-id="5710a-131">Nel riquadro **Scegliere un tipo di gruppo** selezionare **Sicurezza** e quindi fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="5710a-131">In the **Choose a group type** pane, select **Security**, and then select **Next**.</span></span>
4. <span data-ttu-id="5710a-132">Nel riquadro **Configura le nozioni di** base selezionare Crea **gruppo** e quindi fare clic su **Chiudi.**</span><span class="sxs-lookup"><span data-stu-id="5710a-132">In the **Set up the basics** pane, select **Create group**, and then select **Close**.</span></span>
5. <span data-ttu-id="5710a-133">Nel riquadro **Rivedere e completare l'aggiunta del** gruppo, immettere **GlobalAdmins** e quindi selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="5710a-133">In the **Review and finish adding group** pane, enter **GlobalAdmins**, and then select **Next**.</span></span>
7. <span data-ttu-id="5710a-134">Nell'elenco dei gruppi selezionare il **gruppo GlobalAdmins.**</span><span class="sxs-lookup"><span data-stu-id="5710a-134">In the list of groups, select the **GlobalAdmins** group.</span></span>
8. <span data-ttu-id="5710a-135">Nel riquadro **GlobalAdmins** selezionare **Membri** e quindi **Selezionare Visualizza tutti e gestisci membri**.</span><span class="sxs-lookup"><span data-stu-id="5710a-135">In the **GlobalAdmins** pane, select **Members**, and then select **View all and manage members**.</span></span>
9. <span data-ttu-id="5710a-136">Nel riquadro **GlobalAdmins** selezionare **Aggiungi** membri, selezionare **l'account DedicatedAdmin** e l'account amministratore globale, quindi selezionare **Salva**  >  **Chiudi**  >  **Chiudi.**</span><span class="sxs-lookup"><span data-stu-id="5710a-136">In the **GlobalAdmins** pane, select **Add members**, select the **DedicatedAdmin** account and your global admin account, and then select **Save** > **Close** > **Close**.</span></span>

<span data-ttu-id="5710a-137">Successivamente, creare criteri di accesso condizionale per richiedere l'autenticazione a più fattori per gli account amministratore globale e per negare l'autenticazione se il rischio di accesso è medio o elevato.</span><span class="sxs-lookup"><span data-stu-id="5710a-137">Next, create conditional access policies to require multi-factor authentication for global administrator accounts and to deny authentication if the sign-in risk is medium or high.</span></span>

<span data-ttu-id="5710a-138">Questo primo criterio richiede che tutti gli account amministratore globale utilizzino l'autenticazione a più fattori.</span><span class="sxs-lookup"><span data-stu-id="5710a-138">This first policy requires that all global administrator accounts use MFA.</span></span>

1. <span data-ttu-id="5710a-139">In una nuova scheda del browser passare a [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="5710a-139">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="5710a-140">Fare **clic su Azure Active Directory**  >  **Security** Conditional  >  **Access**.</span><span class="sxs-lookup"><span data-stu-id="5710a-140">Click **Azure Active Directory** > **Security** > **Conditional Access**.</span></span>
3. <span data-ttu-id="5710a-141">Nel riquadro **Accesso condizionale - Criteri** selezionare Criterio di **base: Richiedi MFA per gli amministratori (anteprima).**</span><span class="sxs-lookup"><span data-stu-id="5710a-141">In the **Conditional access – Policies** pane, select **Baseline policy: Require MFA for admins (preview)**.</span></span>
4. <span data-ttu-id="5710a-142">Nel riquadro **Criteri di base** selezionare Usa criteri immediatamente > **Salva**.</span><span class="sxs-lookup"><span data-stu-id="5710a-142">In the **Baseline policy** pane, select **Use policy immediately > Save**.</span></span>

<span data-ttu-id="5710a-143">Questo secondo criterio blocca l'accesso all'autenticazione dell'account amministratore globale quando il rischio di accesso è medio o elevato.</span><span class="sxs-lookup"><span data-stu-id="5710a-143">This second policy blocks access to global administrator account authentication when the sign-in risk is medium or high.</span></span>

1. <span data-ttu-id="5710a-144">Nel riquadro **Accesso condizionale - Criteri** selezionare Nuovo **criterio.**</span><span class="sxs-lookup"><span data-stu-id="5710a-144">In the **Conditional access – Policies** pane, select **New policy**.</span></span>
2. <span data-ttu-id="5710a-145">Nel riquadro **Nuovo** immettere **Amministratori globali** in **Nome**.</span><span class="sxs-lookup"><span data-stu-id="5710a-145">In the **New** pane, enter **Global administrators** in **Name**.</span></span>
3. <span data-ttu-id="5710a-146">Nella sezione **Assegnazioni** selezionare **Utenti e gruppi**.</span><span class="sxs-lookup"><span data-stu-id="5710a-146">In the **Assignments** section, select **Users and groups**.</span></span>
4. <span data-ttu-id="5710a-147">Nella scheda **Includi** del riquadro **Utenti** e gruppi selezionare **Seleziona** utenti e gruppi  >  **Utenti e** gruppi  >  **Selezionare**.</span><span class="sxs-lookup"><span data-stu-id="5710a-147">On the **Include** tab of the **Users and groups** pane, select **Select users and groups** > **Users and groups** > **Select**.</span></span>
5. <span data-ttu-id="5710a-148">Nel riquadro **Seleziona** selezionare il **gruppo GlobalAdmins** e quindi **selezionare Seleziona**  >  **fatto.**</span><span class="sxs-lookup"><span data-stu-id="5710a-148">In the **Select** pane, select the **GlobalAdmins** group, and then select **Select** > **Done**.</span></span>
6. <span data-ttu-id="5710a-149">Nella sezione **Assegnazioni** selezionare **Condizioni**.</span><span class="sxs-lookup"><span data-stu-id="5710a-149">In the **Assignments** section, select **Conditions**.</span></span>
7. <span data-ttu-id="5710a-150">Nel riquadro **Condizioni** selezionare **Rischio** di accesso, **selezionare** Sì per **Configura,** **selezionare** Alto e **Medio** e quindi **selezionare Seleziona** e **Fatto.**</span><span class="sxs-lookup"><span data-stu-id="5710a-150">In the **Conditions** pane, select **Sign-in risk**, select **Yes** for **Configure**, select **High** and **Medium**, and then select **Select** and **Done**.</span></span>
8. <span data-ttu-id="5710a-151">Nella sezione **Controlli di** accesso del **riquadro Nuovo** selezionare **Concedi**.</span><span class="sxs-lookup"><span data-stu-id="5710a-151">In the **Access controls** section of the **New** pane, select **Grant**.</span></span>
9. <span data-ttu-id="5710a-152">Nel riquadro **Concedi** seleziona **Blocca accesso** e quindi seleziona **Seleziona.**</span><span class="sxs-lookup"><span data-stu-id="5710a-152">In the **Grant** pane, select **Block access**, and then select **Select**.</span></span>
10. <span data-ttu-id="5710a-153">Nel riquadro **Nuovo** selezionare **Attivato** per **Abilita criterio** e quindi selezionare **Crea**.</span><span class="sxs-lookup"><span data-stu-id="5710a-153">In the **New** pane, select **On** for **Enable policy**, and then select **Create**.</span></span>
11. <span data-ttu-id="5710a-154">Chiudere il **portale di Azure e** le schede dell'interfaccia di amministrazione di Microsoft **365.**</span><span class="sxs-lookup"><span data-stu-id="5710a-154">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="5710a-155">Per testare il primo criterio, disconnettersi e accedere con l'account DedicatedAdmin.</span><span class="sxs-lookup"><span data-stu-id="5710a-155">To test the first policy, sign out and sign in with the DedicatedAdmin account.</span></span> <span data-ttu-id="5710a-156">Dovrebbe essere richiesto di configurare l'autenticazione a più fattori.</span><span class="sxs-lookup"><span data-stu-id="5710a-156">You should be prompted to configure MFA.</span></span> <span data-ttu-id="5710a-157">Questo dimostra che viene applicato il primo criterio.</span><span class="sxs-lookup"><span data-stu-id="5710a-157">This demonstrates that the first policy is being applied.</span></span>

## <a name="next-step"></a><span data-ttu-id="5710a-158">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="5710a-158">Next step</span></span>

<span data-ttu-id="5710a-159">Esplorare altre caratteristiche e funzionalità [identità](m365-enterprise-test-lab-guides.md#identity) nell'ambiente di test.</span><span class="sxs-lookup"><span data-stu-id="5710a-159">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="5710a-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5710a-160">See also</span></span>

[<span data-ttu-id="5710a-161">Guida di orientamento all'identità</span><span class="sxs-lookup"><span data-stu-id="5710a-161">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="5710a-162">Guide ai lab di test di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="5710a-162">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="5710a-163">Panoramica di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="5710a-163">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="5710a-164">Documentazione di Microsoft 365 for enterprise</span><span class="sxs-lookup"><span data-stu-id="5710a-164">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)