---
title: Writeback della password per l'ambiente di testing di Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/20/2018
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
description: "Riepilogo: configurare il writeback della password per l'ambiente di testing di Microsoft 365."
ms.openlocfilehash: 8148341359b66b147ecc5cf9b4927621db1f78dd
ms.sourcegitcommit: 6f94b7a272e33c492957336eae28f439e438c85b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/13/2019
ms.locfileid: "29993227"
---
# <a name="password-writeback-for-your-microsoft-365-test-environment"></a><span data-ttu-id="39944-103">Writeback della password per l'ambiente di testing di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="39944-103">Password writeback for your Microsoft 365 test environment</span></span>

<span data-ttu-id="39944-p101">Il writeback della password consente agli utenti di aggiornare le password tramite Azure Active Directory (Azure AD), che viene replicato nell'istanza locale di Active Directory Domain Services (AD DS). Grazie al writeback delle password gli utenti non devono aggiornare le password tramite l'istanza locale di Windows Server Active Directory in cui sono archiviati gli account utente originali. Questa funzione è utile per gli utenti che lavorano da remoto o in roaming e non dispongono di una connessione di accesso remoto alla rete locale.</span><span class="sxs-lookup"><span data-stu-id="39944-p101">Password writeback allows users to update their passwords through Azure Active Directory (AD), which is then replicated to your local Windows Server Active Directory (AD). With password writeback, users don’t need to update their passwords through the on-premises Windows Server AD where their original user accounts are stored. This helps roaming or remote users who do not have a remote access connection to their on-premises network.</span></span>

<span data-ttu-id="39944-107">In questo articolo viene descritto come configurare l'ambiente di testing di Microsoft 365 per il writeback delle password.</span><span class="sxs-lookup"><span data-stu-id="39944-107">This article describes how you can configure your Microsoft 365 test environment for password writeback.</span></span>

<span data-ttu-id="39944-108">Esistono due fasi per la configurazione:</span><span class="sxs-lookup"><span data-stu-id="39944-108">There are two phases to setting this up:</span></span>

1.  <span data-ttu-id="39944-109">Creare l'ambiente di testing dell'organizzazione simulata di Microsoft 365 con per la sincronizzazione hash delle password.</span><span class="sxs-lookup"><span data-stu-id="39944-109">Create the Microsoft 365 simulated enterprise test environment with password hash synchronization.</span></span>
2.  <span data-ttu-id="39944-110">Abilitare il writeback delle password per il dominio TESTLAB di Windows Server Active Directory.</span><span class="sxs-lookup"><span data-stu-id="39944-110">Enable password writeback for the TESTLAB Windows Server AD domain.</span></span>
    
![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="39944-112">Fare clic [qui](https://aka.ms/m365etlgstack) per consultare una mappa di tutti gli articoli relativi alla guida al lab test di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="39944-112">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="39944-113">Fase 1: configurare la sincronizzazione hash delle password per l'ambiente di testing di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="39944-113">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="39944-p102">Seguire le istruzioni riportate in [sincronizzazione hash delle password per Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Di seguito è riportata la configurazione risultante.</span><span class="sxs-lookup"><span data-stu-id="39944-p102">Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Here is your resulting configuration.</span></span>
  
![L'organizzazione simulata con ambiente di testing per la sincronizzazione hash delle password](media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="39944-117">Questa configurazione è costituita da:</span><span class="sxs-lookup"><span data-stu-id="39944-117">This configuration consists of:</span></span> 
  
- <span data-ttu-id="39944-118">Abbonamenti di valutazione o permanenti a Office 365 E5 ed EMS E5.</span><span class="sxs-lookup"><span data-stu-id="39944-118">Office 365 E5 and EMS E5 trial or permanent subscriptions.</span></span>
- <span data-ttu-id="39944-119">Una intranet dell’organizzazione semplificata connessa a Internet e costituita dalle macchine virtuali DC1 APP1 e CLIENT1 in una sottorete di una rete virtuale Azure.</span><span class="sxs-lookup"><span data-stu-id="39944-119">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="39944-120">Azure AD Connect viene eseguito su APP1 per sincronizzare il dominio TESTLAB Windows Server AD per il tenant Azure AD degli abbonamenti a Office 365 ed EMS E5.</span><span class="sxs-lookup"><span data-stu-id="39944-120">Azure AD Connect runs on APP1 to synchronize the TESTLAB Windows Server AD domain to the Azure AD tenant of your Office 365 and EMS E5 subscriptions.</span></span>

## <a name="phase-2-enable-password-writeback-for-the-testlab-windows-server-ad-domain"></a><span data-ttu-id="39944-121">Fase 2: abilitare il writeback delle password per il dominio TESTLAB di Windows Server Active Directory</span><span class="sxs-lookup"><span data-stu-id="39944-121">Phase 2: Enable password writeback for the TESTLAB Windows Server AD domain</span></span>

<span data-ttu-id="39944-122">Per iniziare, configurare l'account utente 1 con il ruolo amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="39944-122">First, configure the User 1 account with the global administrator role.</span></span>

1. <span data-ttu-id="39944-123">Dal [portale di Office](https://office.com), accedere con l'account di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="39944-123">From the [Office portal](https://office.com), sign in with your global administrator account.</span></span>

2. <span data-ttu-id="39944-p103">Fare clic sul riquadro **Amministrazione**. Dalla nuova scheda dell’**interfaccia di amministrazione di Microsoft 365** del browser, fare clic su **Utenti attivi**.</span><span class="sxs-lookup"><span data-stu-id="39944-p103">Click the **Admin** tile. From the new **Microsoft 365 admin center** tab of your browser, click **Active users**.</span></span>
 
3. <span data-ttu-id="39944-126">Nella pagina **Utenti attivi**, fare clic sull’account **Utente1**,</span><span class="sxs-lookup"><span data-stu-id="39944-126">On the **Active users** page, click the **user1** account,</span></span>

4. <span data-ttu-id="39944-127">Nel riquadro **Utente1**, fare clic su **Modifica** accanto a **Ruoli**.</span><span class="sxs-lookup"><span data-stu-id="39944-127">On the **user1** pane, click **Edit** next to **Roles**.</span></span>

5. <span data-ttu-id="39944-p104">Nel riquadro **Modifica ruoli utente** per utente1, fare clic su **Amministratore globale**. Fare clic su **Salva** e quindi su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="39944-p104">On the **Edit user roles** pane for user1, click **Global administrator**. Click **Save**, and then click **Close**.</span></span>

<span data-ttu-id="39944-130">Quindi, configurare l'account Utente 1 con le impostazioni di sicurezza che gli consentono di cambiare le password per conto di altri utenti nel dominio TESTLAB di Windows Server Active Directory.</span><span class="sxs-lookup"><span data-stu-id="39944-130">Next, configure the User 1 account with the security settings that allow it to change passwords on behalf of other users in the TESTLAB Windows Server AD domain.</span></span>

1. <span data-ttu-id="39944-131">Dal [portale di Azure](https://portal.azure.com), accedere con l'account di amministratore globale e connettersi ad APP1 con l'account TESTLAB\Utente1.</span><span class="sxs-lookup"><span data-stu-id="39944-131">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2.  <span data-ttu-id="39944-132">Dal desktop di APP1, fare clic su **Inizio**, digitare **attivo**, quindi fare clic su **Utenti e computer di Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="39944-132">From the desktop of APP1, click **Start**, type **active**, and then click **Active Directory Users and Computers**.</span></span>

3. <span data-ttu-id="39944-p105">Fare clic su **Visualizza** nella barra dei menu. Se l’opzione **Funzionalità avanzate** non è attiva, fare clic per abilitarla.</span><span class="sxs-lookup"><span data-stu-id="39944-p105">Click **View** in the menu bar. If **Advanced features** is not enabled, click it to enable it.</span></span>

4. <span data-ttu-id="39944-135">Nel riquadro della struttura, fare clic con il pulsante destro del mouse sul dominio, fare clic su **Proprietà** e quindi sulla scheda **Protezione**.</span><span class="sxs-lookup"><span data-stu-id="39944-135">In the tree pane, right-click your domain, click **Properties**, and then click the **Security** tab.</span></span>

5. <span data-ttu-id="39944-136">Fare clic su **Avanzate**.</span><span class="sxs-lookup"><span data-stu-id="39944-136">Click **Advanced**.</span></span>

6. <span data-ttu-id="39944-137">Nella scheda **Autorizzazioni**, fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="39944-137">On the **Permissions** tab, click **Add**.</span></span>

7. <span data-ttu-id="39944-138">Fare clic su **Seleziona un'entità**, digitare **Utente1**, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="39944-138">Click **Select a principal**, type **User1**, and then click **OK**.</span></span>

8. <span data-ttu-id="39944-139">In **Si applica a**, selezionare **Oggetti utente discendenti**.</span><span class="sxs-lookup"><span data-stu-id="39944-139">In **Applies to**, select **Descendant User objects**.</span></span>

9. <span data-ttu-id="39944-140">In **Autorizzazioni**, selezionare le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="39944-140">Under **Permissions**, select the following:</span></span>

    - <span data-ttu-id="39944-141">Cambiare la password</span><span class="sxs-lookup"><span data-stu-id="39944-141">Change password</span></span>
    - <span data-ttu-id="39944-142">Reimpostare la password</span><span class="sxs-lookup"><span data-stu-id="39944-142">Reset password</span></span>

10. <span data-ttu-id="39944-143">In **Proprietà**, selezionare le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="39944-143">Under **Properties**, select the following:</span></span>
    - <span data-ttu-id="39944-144">Scrittura lockoutTime</span><span class="sxs-lookup"><span data-stu-id="39944-144">Write lockoutTime</span></span>
    - <span data-ttu-id="39944-145">Scrittura pwdLastSet</span><span class="sxs-lookup"><span data-stu-id="39944-145">Write pwdLastSet</span></span>

11. <span data-ttu-id="39944-146">Fare clic su **OK** tre volte per salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="39944-146">Click **OK** three times to save the changes.</span></span>

12. <span data-ttu-id="39944-147">Chiudere **Utenti e computer di Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="39944-147">Close **Active Directory Users and Computers**.</span></span>

<span data-ttu-id="39944-148">Successivamente, configurare Azure AD Connect su APP1 per il writeback delle password.</span><span class="sxs-lookup"><span data-stu-id="39944-148">Next, configure Azure AD Connect on APP1 for password writeback.</span></span>

1. <span data-ttu-id="39944-149">Se necessario, connettersi ad APP1 con l'account TESTLAB\Utente1.</span><span class="sxs-lookup"><span data-stu-id="39944-149">If needed, connect to APP1 with the TESTLAB\User1 account.</span></span>

2. <span data-ttu-id="39944-150">Dal desktop di APP1, fare doppio clic su **Azure AD Connect**.</span><span class="sxs-lookup"><span data-stu-id="39944-150">From the desktop of APP1, double-click **Azure AD Connect**.</span></span>

3. <span data-ttu-id="39944-151">Nella **Pagina di benvenuto** fare clic su **Configura**.</span><span class="sxs-lookup"><span data-stu-id="39944-151">On the **Welcome page**, click **Configure**.</span></span>

4. <span data-ttu-id="39944-152">Nella pagina **Attività aggiuntive**, fare clic su **Personalizza le opzioni di sincronizzazione**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="39944-152">On the **Additional tasks** page, click **Customize synchronization options**, and then click **Next**.</span></span>

5. <span data-ttu-id="39944-153">Nella pagina **Connessione ad Azure AD**, digitare le credenziali dell'account Utente 1 e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="39944-153">On the **Connect to Azure AD** page, type the User 1 account credentials, and then click **Next**.</span></span>

6. <span data-ttu-id="39944-154">Nelle pagine **Connessione delle directory** e **Filtro di domini/unità organizzative**, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="39944-154">On the **Connect directories** and **Domain/OU filtering** pages, click **Next**.</span></span>

7. <span data-ttu-id="39944-155">Nella pagina **Funzionalità facoltative**, selezionare **Writeback password** e fare clic su Avanti.</span><span class="sxs-lookup"><span data-stu-id="39944-155">On the **Optional features** page, select **Password writeback** and click Next.</span></span> 

8. <span data-ttu-id="39944-156">Nella pagina **Pronto per la configurazione**, fare clic su **Configura** e attendere il completamento del processo.</span><span class="sxs-lookup"><span data-stu-id="39944-156">On the **Ready to configure** page, click **Configure** and wait for the process to finish.</span></span>

9. <span data-ttu-id="39944-157">Quando viene visualizzata la fine della configurazione, fare clic su **Esci**.</span><span class="sxs-lookup"><span data-stu-id="39944-157">When you see the configuration finish, click **Exit**.</span></span>

<span data-ttu-id="39944-158">È ora possibile testare il writeback delle password per gli utenti in computer non connessi alla rete virtuale della rete intranet simulata.</span><span class="sxs-lookup"><span data-stu-id="39944-158">You are now ready to test password writeback for users on computers that are not connected to the virtual network of your simulated intranet.</span></span>

<span data-ttu-id="39944-159">Di seguito è riportata la configurazione risultante:</span><span class="sxs-lookup"><span data-stu-id="39944-159">Here is your resulting configuration:</span></span>

![L'organizzazione simulata con ambiente di testing per l'autenticazione pass-through](media/pass-through-auth-m365-ent-test-environment/Phase1.png)

<span data-ttu-id="39944-161">Questa configurazione è costituita da:</span><span class="sxs-lookup"><span data-stu-id="39944-161">This configuration consists of:</span></span>

- <span data-ttu-id="39944-162">Abbonamenti di valutazione o permanenti a Office 365 E5 ed EMS E5 con dominio DNS TESTLAB.\<nome dominio> registrato.</span><span class="sxs-lookup"><span data-stu-id="39944-162">Office 365 E5 and EMS E5 trial or permanent subscriptions with the DNS domain TESTLAB.\<your domain name> registered.</span></span>
- <span data-ttu-id="39944-163">Una intranet dell’organizzazione semplificata connessa a Internet e costituita dalle macchine virtuali DC1 APP1 e CLIENT1 in una sottorete di una rete virtuale Azure.</span><span class="sxs-lookup"><span data-stu-id="39944-163">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="39944-164">Periodicamente, Azure AD Connect viene eseguito su APP1 per sincronizzare l'elenco di account e gruppi dal tenant degli abbonamenti a Office 365 ed EMS E5 al dominio TESTLAB Windows Server AD.</span><span class="sxs-lookup"><span data-stu-id="39944-164">Azure AD Connect runs on APP1 to synchronize the list of accounts and groups from the Azure AD tenant of your Office 365 and EMS E5 subscriptions to the TESTLAB Windows Server AD domain.</span></span> 
- <span data-ttu-id="39944-165">Il writeback delle password è abilitato in modo che gli utenti possono modificare la password tramite Azure AD senza dover essere connessi alla rete intranet semplificata.</span><span class="sxs-lookup"><span data-stu-id="39944-165">Password writeback is enabled so that users can change their passwords through Azure AD without having to be connected to the simplified intranet.</span></span>

<span data-ttu-id="39944-166">Vedere il passaggio [Semplificare gli aggiornamenti delle password](identity-password-writeback.md) nella fase Identità per informazioni e collegamenti per configurare il writeback della password nell’ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="39944-166">See the [Simplify password updates](identity-password-writeback.md) step in the Identity phase for information and links to configure password writeback in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="39944-167">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="39944-167">Next step</span></span>

<span data-ttu-id="39944-168">Esplorare altre caratteristiche e funzionalità [identità](m365-enterprise-test-lab-guides.md#identity) nell'ambiente di test.</span><span class="sxs-lookup"><span data-stu-id="39944-168">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="39944-169">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="39944-169">See also</span></span>

[<span data-ttu-id="39944-170">Guide al lab di test di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="39944-170">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="39944-171">Distribuzione di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="39944-171">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="39944-172">Documentazione di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="39944-172">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)


