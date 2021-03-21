---
title: Writeback della password per l'ambiente di testing di Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/22/2019
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
description: "Riepilogo: configurare il writeback della password per l'ambiente di testing di Microsoft 365."
ms.openlocfilehash: f1118c22ad1f65ea29bb14afacb7506a60d1fe1a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921481"
---
# <a name="password-writeback-for-your-microsoft-365-test-environment"></a><span data-ttu-id="c8d87-103">Writeback della password per l'ambiente di testing di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c8d87-103">Password writeback for your Microsoft 365 test environment</span></span>

<span data-ttu-id="c8d87-104">*Questa guida al laboratorio di testing può essere utilizzata solo per gli ambienti di testing di Microsoft 365 per le aziende.*</span><span class="sxs-lookup"><span data-stu-id="c8d87-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="c8d87-105">Gli utenti possono usare il writeback delle password per aggiornare le password tramite Azure Active Directory (Azure AD), che viene quindi replicato in Servizi di dominio Active Directory (AD DS) locale.</span><span class="sxs-lookup"><span data-stu-id="c8d87-105">Users can use password writeback to update their passwords through Azure Active Directory (Azure AD), which is then replicated to your local Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="c8d87-106">Con il writeback delle password, gli utenti non devono aggiornare le password tramite Servizi di dominio Active Directory locale in cui sono archiviati gli account utente originali.</span><span class="sxs-lookup"><span data-stu-id="c8d87-106">With password writeback, users don't have to update their passwords through the on-premises AD DS where their original user accounts are stored.</span></span> <span data-ttu-id="c8d87-107">Ciò consente agli utenti mobili o remoti che non dispongono di una connessione di accesso remoto alla rete locale.</span><span class="sxs-lookup"><span data-stu-id="c8d87-107">This helps roaming or remote users who don't have a remote access connection to their on-premises network.</span></span>

<span data-ttu-id="c8d87-108">In questo articolo viene descritto come configurare l'ambiente di testing di Microsoft 365 per il writeback delle password.</span><span class="sxs-lookup"><span data-stu-id="c8d87-108">This article describes how to configure your Microsoft 365 test environment for password writeback.</span></span>

<span data-ttu-id="c8d87-109">La configurazione dell'ambiente di testing per il writeback delle password prevede due fasi:</span><span class="sxs-lookup"><span data-stu-id="c8d87-109">Configuring your test environment for password writeback involves two phases:</span></span>
- [<span data-ttu-id="c8d87-110">Fase 1: configurare la sincronizzazione hash delle password per l'ambiente di testing di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c8d87-110">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [<span data-ttu-id="c8d87-111">Fase 2: abilitare il writeback delle password per il dominio TESTLAB Active Directory Domain Services.</span><span class="sxs-lookup"><span data-stu-id="c8d87-111">Phase 2: Enable password writeback for the TESTLAB AD DS domain</span></span>](#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain)
  
![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="c8d87-113">Per una mappa visiva a tutti gli articoli nello stack guida del laboratorio di testing di Microsoft 365 per le aziende, passare a [Microsoft 365 per enterprise Test Lab Guide Stack.](../downloads/Microsoft365EnterpriseTLGStack.pdf)</span><span class="sxs-lookup"><span data-stu-id="c8d87-113">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="c8d87-114">Fase 1: configurare la sincronizzazione hash delle password per l'ambiente di testing di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c8d87-114">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="c8d87-115">Prima di tutto, seguire le istruzioni in [Sincronizzazione hash password](password-hash-sync-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="c8d87-115">First, follow the instructions in [password hash synchronization](password-hash-sync-m365-ent-test-environment.md).</span></span> <span data-ttu-id="c8d87-116">La configurazione risultante è simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="c8d87-116">Your resulting configuration looks like this:</span></span>
  
![L'organizzazione simulata con ambiente di testing per la sincronizzazione hash delle password](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="c8d87-118">Questa configurazione è costituita da:</span><span class="sxs-lookup"><span data-stu-id="c8d87-118">This configuration consists of:</span></span>
  
- <span data-ttu-id="c8d87-119">Un abbonamento di valutazione o a pagamento a Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="c8d87-119">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="c8d87-120">Intranet dell'organizzazione semplificata connessa a Internet, costituita da macchine virtuali DC1, APP1 e CLIENT1 in una subnet di una rete virtuale di Azure.</span><span class="sxs-lookup"><span data-stu-id="c8d87-120">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>
- <span data-ttu-id="c8d87-121">Azure AD Connect viene eseguito su APP1 per sincronizzare il dominio TESTLAB di Active Directory Domain Services con il tenant di Azure AD dell'abbonamento a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c8d87-121">Azure AD Connect runs on APP1 to synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Microsoft 365 subscription.</span></span>

## <a name="phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain"></a><span data-ttu-id="c8d87-122">Fase 2: abilitare il writeback delle password per il dominio TESTLAB Active Directory Domain Services.</span><span class="sxs-lookup"><span data-stu-id="c8d87-122">Phase 2: Enable password writeback for the TESTLAB AD DS domain</span></span>

<span data-ttu-id="c8d87-123">Per iniziare, configurare l'account utente 1 con il ruolo amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="c8d87-123">First, configure the User 1 account with the global administrator role.</span></span>

1. <span data-ttu-id="c8d87-124">Dall’[Interfaccia di amministrazione di Microsoft 365](https://portal.microsoft.com), accedere con l'account di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="c8d87-124">From the [Microsoft 365 admin center](https://portal.microsoft.com), sign in with your global administrator account.</span></span>

2. <span data-ttu-id="c8d87-125">Selezionare **Utenti attivi**.</span><span class="sxs-lookup"><span data-stu-id="c8d87-125">Select **Active users**.</span></span>
 
3. <span data-ttu-id="c8d87-126">Nella pagina **Utenti attivi** selezionare l'account **user1,**</span><span class="sxs-lookup"><span data-stu-id="c8d87-126">On the **Active users** page, select the **user1** account,</span></span>

4. <span data-ttu-id="c8d87-127">Nel riquadro **user1** selezionare **Modifica** accanto a **Ruoli**.</span><span class="sxs-lookup"><span data-stu-id="c8d87-127">On the **user1** pane, select **Edit** next to **Roles**.</span></span>

5. <span data-ttu-id="c8d87-128">Nel riquadro **Modifica ruoli utente** per utente1 selezionare Amministratore **globale,** **salva** e **quindi** chiudi.</span><span class="sxs-lookup"><span data-stu-id="c8d87-128">On the **Edit user roles** pane for user1, select **Global administrator**, select **Save**, and then select **Close**.</span></span>

<span data-ttu-id="c8d87-129">Quindi, configurare l'account Utente 1 con le impostazioni di sicurezza che gli consentono di cambiare le password per conto di altri utenti nel dominio TESTLAB Active Directory Domain Services.</span><span class="sxs-lookup"><span data-stu-id="c8d87-129">Next, configure the User 1 account with the security settings that allow it to change passwords on behalf of other users in the TESTLAB AD DS domain.</span></span>

1. <span data-ttu-id="c8d87-130">Dal [portale di Azure](https://portal.azure.com), accedere con l'account di amministratore globale e connettersi ad APP1 con l'account TESTLAB\Utente1.</span><span class="sxs-lookup"><span data-stu-id="c8d87-130">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2. <span data-ttu-id="c8d87-131">Dal desktop di APP1, selezionare **Start**, immettere **active** e quindi selezionare **Utenti e computer di Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="c8d87-131">From the desktop of APP1, select **Start**, enter **active**, and then select **Active Directory Users and Computers**.</span></span>

3. <span data-ttu-id="c8d87-132">Sulla barra dei menu selezionare **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="c8d87-132">On the menu bar, select **View**.</span></span> <span data-ttu-id="c8d87-133">Se **funzionalità avanzate** non è abilitata, selezionarla per abilitarla.</span><span class="sxs-lookup"><span data-stu-id="c8d87-133">If **Advanced features** is not enabled, select it to enable it.</span></span>

4. <span data-ttu-id="c8d87-134">Nel riquadro dell'albero, selezionare e tenere premuto (o fare clic con il pulsante destro del mouse) sul dominio, selezionare **Proprietà** e quindi selezionare la **scheda** Sicurezza.</span><span class="sxs-lookup"><span data-stu-id="c8d87-134">In the tree pane, select and hold (or right-click) your domain, select **Properties**, and then select the **Security** tab.</span></span>

5. <span data-ttu-id="c8d87-135">Selezionare **Avanzate**.</span><span class="sxs-lookup"><span data-stu-id="c8d87-135">Select **Advanced**.</span></span>

6. <span data-ttu-id="c8d87-136">Nella scheda **Autorizzazioni** selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="c8d87-136">On the **Permissions** tab, select **Add**.</span></span>

7. <span data-ttu-id="c8d87-137">Selezionare **Selezionare un'entità,** immettere **User1** e quindi selezionare **OK.**</span><span class="sxs-lookup"><span data-stu-id="c8d87-137">Select **Select a principal**, enter **User1**, and then select **OK**.</span></span>

8. <span data-ttu-id="c8d87-138">In **Si applica a**, selezionare **Oggetti utente discendenti**.</span><span class="sxs-lookup"><span data-stu-id="c8d87-138">In **Applies to**, select **Descendant User objects**.</span></span>

9. <span data-ttu-id="c8d87-139">In **Autorizzazioni**, selezionare le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c8d87-139">Under **Permissions**, select the following:</span></span>

    - <span data-ttu-id="c8d87-140">**Cambia password**</span><span class="sxs-lookup"><span data-stu-id="c8d87-140">**Change password**</span></span>
    - <span data-ttu-id="c8d87-141">**Reimpostare la password**</span><span class="sxs-lookup"><span data-stu-id="c8d87-141">**Reset password**</span></span>

10. <span data-ttu-id="c8d87-142">In **Proprietà**, selezionare le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c8d87-142">Under **Properties**, select the following:</span></span>
    - <span data-ttu-id="c8d87-143">**Scrittura lockoutTime**</span><span class="sxs-lookup"><span data-stu-id="c8d87-143">**Write lockoutTime**</span></span>
    - <span data-ttu-id="c8d87-144">**Scrittura pwdLastSet**</span><span class="sxs-lookup"><span data-stu-id="c8d87-144">**Write pwdLastSet**</span></span>

11. <span data-ttu-id="c8d87-145">Selezionare **OK** tre volte per salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="c8d87-145">Select **OK** three times to save the changes.</span></span>

12. <span data-ttu-id="c8d87-146">Chiudere **Utenti e computer di Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="c8d87-146">Close **Active Directory Users and Computers**.</span></span>

<span data-ttu-id="c8d87-147">Successivamente, configurare Azure AD Connect su APP1 per il writeback delle password.</span><span class="sxs-lookup"><span data-stu-id="c8d87-147">Next, configure Azure AD Connect on APP1 for password writeback.</span></span>

1. <span data-ttu-id="c8d87-148">Se necessario, connettersi ad APP1 con l'account TESTLAB\Utente1.</span><span class="sxs-lookup"><span data-stu-id="c8d87-148">If needed, connect to APP1 with the TESTLAB\User1 account.</span></span>

2. <span data-ttu-id="c8d87-149">Dal desktop di APP1, fare doppio clic su **Azure AD Connect**.</span><span class="sxs-lookup"><span data-stu-id="c8d87-149">From the desktop of APP1, double-click **Azure AD Connect**.</span></span>

3. <span data-ttu-id="c8d87-150">Nella pagina **iniziale selezionare** **Configura**.</span><span class="sxs-lookup"><span data-stu-id="c8d87-150">On the **Welcome page**, select **Configure**.</span></span>

4. <span data-ttu-id="c8d87-151">Nella pagina **Attività aggiuntive** selezionare Personalizza opzioni **di sincronizzazione** e **quindi** avanti .</span><span class="sxs-lookup"><span data-stu-id="c8d87-151">On the **Additional tasks** page, select **Customize synchronization options**, and then select **Next**.</span></span>

5. <span data-ttu-id="c8d87-152">Nella pagina **Connetti ad Azure AD** immetti le credenziali dell'account amministratore globale e quindi seleziona **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="c8d87-152">On the **Connect to Azure AD** page, enter your global administrator account credentials, and then select **Next**.</span></span>

6. <span data-ttu-id="c8d87-153">Nelle pagine **Connect directories** and **Domain/OU filtering** selezionare **Next.**</span><span class="sxs-lookup"><span data-stu-id="c8d87-153">On the **Connect directories** and **Domain/OU filtering** pages, select **Next**.</span></span>

7. <span data-ttu-id="c8d87-154">Nella pagina **Funzionalità facoltative** selezionare **Writeback password** e **quindi** avanti .</span><span class="sxs-lookup"><span data-stu-id="c8d87-154">On the **Optional features** page, select **Password writeback**, and then select **Next**.</span></span>

8. <span data-ttu-id="c8d87-155">Nella pagina **Pronto per la configurazione** selezionare **Configura** e attendere il completamento del processo.</span><span class="sxs-lookup"><span data-stu-id="c8d87-155">On the **Ready to configure** page, select **Configure** and wait for the process to finish.</span></span>

9. <span data-ttu-id="c8d87-156">Al termine della configurazione, selezionare **Esci.**</span><span class="sxs-lookup"><span data-stu-id="c8d87-156">When you see the configuration finish, select **Exit**.</span></span>

<span data-ttu-id="c8d87-157">A questo punto è possibile testare il writeback delle password per gli utenti di computer che non sono connessi alla rete virtuale della rete Intranet simulata.</span><span class="sxs-lookup"><span data-stu-id="c8d87-157">You are now ready to test password writeback for users on computers that aren't connected to the virtual network of your simulated intranet.</span></span>

<span data-ttu-id="c8d87-158">La configurazione risultante è simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="c8d87-158">Your resulting configuration looks like this:</span></span>

![L'organizzazione simulata con ambiente di testing per l'autenticazione pass-through](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

<span data-ttu-id="c8d87-160">Questa configurazione è costituita da:</span><span class="sxs-lookup"><span data-stu-id="c8d87-160">This configuration consists of:</span></span>

- <span data-ttu-id="c8d87-161">Una versione di valutazione di Microsoft 365 E5 o sottoscrizioni a pagamento con il dominio DNS TESTLAB.\<*your domain name*></span><span class="sxs-lookup"><span data-stu-id="c8d87-161">A Microsoft 365 E5 trial or paid subscriptions with the DNS domain TESTLAB.\<*your domain name*></span></span> <span data-ttu-id="c8d87-162">registrato.</span><span class="sxs-lookup"><span data-stu-id="c8d87-162">registered.</span></span>
- <span data-ttu-id="c8d87-163">Intranet dell'organizzazione semplificata connessa a Internet, costituita da macchine virtuali DC1, APP1 e CLIENT1 in una subnet di una rete virtuale di Azure.</span><span class="sxs-lookup"><span data-stu-id="c8d87-163">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>
- <span data-ttu-id="c8d87-164">Azure AD Connect viene eseguito su APP1 per sincronizzare l'elenco di account e gruppi dal tenant di Azure AD dell'abbonamento a Microsoft 365 al dominio TESTLAB di Active Directory Domain Services.</span><span class="sxs-lookup"><span data-stu-id="c8d87-164">Azure AD Connect runs on APP1 to synchronize the list of accounts and groups from the Azure AD tenant of your Microsoft 365 subscription to the TESTLAB AD DS domain.</span></span>
- <span data-ttu-id="c8d87-165">Il writeback delle password è abilitato in modo che gli utenti possono modificare la password tramite Azure AD senza dover essere connessi alla rete intranet semplificata.</span><span class="sxs-lookup"><span data-stu-id="c8d87-165">Password writeback is enabled so that users can change their passwords through Azure AD without having to be connected to the simplified intranet.</span></span>

## <a name="next-step"></a><span data-ttu-id="c8d87-166">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="c8d87-166">Next step</span></span>

<span data-ttu-id="c8d87-167">Esplorare altre caratteristiche e funzionalità [identità](m365-enterprise-test-lab-guides.md#identity) nell'ambiente di test.</span><span class="sxs-lookup"><span data-stu-id="c8d87-167">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="c8d87-168">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c8d87-168">See also</span></span>

[<span data-ttu-id="c8d87-169">Guide ai lab di test di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="c8d87-169">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="c8d87-170">Panoramica di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="c8d87-170">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="c8d87-171">Documentazione di Microsoft 365 for enterprise</span><span class="sxs-lookup"><span data-stu-id="c8d87-171">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)