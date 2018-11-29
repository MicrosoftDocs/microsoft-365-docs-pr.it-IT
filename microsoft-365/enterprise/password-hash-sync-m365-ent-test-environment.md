---
title: Sincronizzazione hash delle password per l'ambiente di testing di Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- TLG
- Ent_TLGs
ms.assetid: ''
description: "Riepilogo: configurare e illustrare la sincronizzazione hash delle password e l'accesso per l'ambiente di testing di Microsoft 365."
ms.openlocfilehash: 3cee2b69ce34647627cb2b72f9e0f59a6fba17e9
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868853"
---
# <a name="password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="17eb3-103">Sincronizzazione hash delle password per l'ambiente di testing di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="17eb3-103">Password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="17eb3-p101">Molte organizzazioni usano Azure AD Connect e la sincronizzazione hash delle password per sincronizzare il set di account della foresta Windows Server Active Directory (AD) locale per il set di account nel tenant Azure AD degli abbonamenti a Office 365 ed EMS E5. In questo articolo viene illustrato come aggiungere la sincronizzazione hash delle password per l'ambiente di sviluppo e di testing di Microsoft 365, determinando la configurazione seguente:</span><span class="sxs-lookup"><span data-stu-id="17eb3-p101">Many organizations use Azure AD Connect and password hash synchronization to synchronize the set of accounts in their on-premises Windows Server Active Directory (AD) forest to the set of accounts in the Azure AD tenant of their Office 365 and EMS E5 subscriptions. This article describes how you can add password hash synchronization to your Microsoft 365 test environment, resulting in the following configuration:</span></span>
  
![L'organizzazione simulata con ambiente di testing per la sincronizzazione hash delle password](media/password-hash-sync-m365-ent-test-environment/Phase3.png)
  
<span data-ttu-id="17eb3-107">Le fasi principali della configurazione dell'ambiente di testing sono tre:</span><span class="sxs-lookup"><span data-stu-id="17eb3-107">There are two phases to setting up this test environment:</span></span>
  
1. <span data-ttu-id="17eb3-108">Creare l'ambiente di testing per l'organizzazione simulata di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="17eb3-108">Create the Microsoft 365 simulated enterprise test environment.</span></span>
2. <span data-ttu-id="17eb3-109">Installare e configurare Azure AD Connect su APP1.</span><span class="sxs-lookup"><span data-stu-id="17eb3-109">Install and configure Azure AD Connect on APP1.</span></span>
    
> [!TIP]
> <span data-ttu-id="17eb3-110">Fare clic [qui](https://aka.ms/m365etlgstack) per consultare una mappa di tutti gli articoli relativi alla guida al lab test di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="17eb3-110">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-create-the-microsoft-365-simulated-enterprise-test-environment"></a><span data-ttu-id="17eb3-111">Fase 1: creare l'ambiente di testing per l'organizzazione simulata di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="17eb3-111">Phase 1: Create the Microsoft 365 simulated enterprise test environment</span></span>

<span data-ttu-id="17eb3-p102">Seguire le istruzioni riportate in [configurazione di base per l'organizzazione simulata per Microsoft 365](simulated-ent-base-configuration-microsoft-365-enterprise.md). Questa è la configurazione risultante.</span><span class="sxs-lookup"><span data-stu-id="17eb3-p102">Follow the instructions in [simulated enterprise base configuration for Microsoft 365](simulated-ent-base-configuration-microsoft-365-enterprise.md). Here is your resulting configuration.</span></span>
  
![La configurazione di base per l'organizzazione simulata](media/password-hash-sync-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="17eb3-115">Questa configurazione è costituita da:</span><span class="sxs-lookup"><span data-stu-id="17eb3-115">This configuration consists of:</span></span> 
  
- <span data-ttu-id="17eb3-116">Abbonamenti di valutazione o permanenti a Office 365 E5 ed EMS E5.</span><span class="sxs-lookup"><span data-stu-id="17eb3-116">Office 365 E5 and EMS E5 trial or permanent subscriptions.</span></span>
- <span data-ttu-id="17eb3-p103">Una intranet dell’organizzazione semplificata connessa a Internet e costituita da tre macchine virtuali (DC1, APP1 e CLIENT1) in una rete virtuale Azure. DC1 è un controller di dominio per il dominio di Windows Server AD testlab.\<nome dominio pubblico>.</span><span class="sxs-lookup"><span data-stu-id="17eb3-p103">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines in an Azure virtual network. DC1 is a domain controller for the testlab.\<your public domain name> Windows Server AD domain.</span></span>

## <a name="phase-2-create-and-register-the-testlab-domain"></a><span data-ttu-id="17eb3-119">Fase 2: creare e registrare il dominio per il test lab</span><span class="sxs-lookup"><span data-stu-id="17eb3-119">Phase 2: Create and register the testlab domain</span></span>

<span data-ttu-id="17eb3-120">In questa fase si aggiunge un dominio pubblico DNS che viene aggiunto all'abbonamento.</span><span class="sxs-lookup"><span data-stu-id="17eb3-120">In this phase you add a public DNS domain and add it to your subscription.</span></span>

<span data-ttu-id="17eb3-p104">Innanzitutto, utilizzare il provider di registrazione DNS pubblico per creare un nuovo nome di dominio DNS pubblico basato sul proprio nome di dominio corrente e aggiungerlo all'abbonamento a Office 365. È consigliabile utilizzare il nome **testlab.**\<dominio pubblico>. Ad esempio, se il nome di dominio pubblico è <span>**contoso</span>.com**, aggiungere il nome di dominio pubblico **<span>testlab</span>.contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="17eb3-p104">First, work with your public DNS registration provider to create a new public DNS domain name based on your current domain name and add it to your Office 365 subscription. We recommend using the name **testlab.**\<your public domain>. For example, if your public domain name is <span>**contoso</span>.com**, add the public domain name **<span>testlab</span>.contoso.com**.</span></span>
  
<span data-ttu-id="17eb3-p105">Successivamente, aggiungere il dominio **testlab.**\<dominio pubblico> all'abbonamento permanente o di valutazione a Office 365 eseguendo la procedura di registrazione del dominio. Si tratta di aggiungere altri record DNS al dominio **testlab.**\<dominio pubblico>. Per ulteriori informazioni, vedere l'articolo relativo a come [aggiungere utenti e domini a Office 365](https://support.office.com/article/Add-users-and-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span><span class="sxs-lookup"><span data-stu-id="17eb3-p105">Next, you add the **testlab.**\<your public domain> domain to your Office 365 trial or permanent subscription by going through the domain registration process. This consists of adding additional DNS records to the **testlab.**\<your public domain> domain. For more information, see [Add users and domain to Office 365](https://support.office.com/article/Add-users-and-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span> 

<span data-ttu-id="17eb3-127">Di seguito è riportata la configurazione risultante.</span><span class="sxs-lookup"><span data-stu-id="17eb3-127">Here is your resulting configuration.</span></span>
  
![La registrazione del nome di dominio testlab](media/password-hash-sync-m365-ent-test-environment/Phase2.png)
  
<span data-ttu-id="17eb3-129">Questa configurazione è costituita da:</span><span class="sxs-lookup"><span data-stu-id="17eb3-129">This configuration consists of:</span></span>

- <span data-ttu-id="17eb3-130">Abbonamenti di valutazione o permanenti a Office 365 E5 ed EMS E5 con dominio DNS testlab.\<nome del dominio pubblico> registrato.</span><span class="sxs-lookup"><span data-stu-id="17eb3-130">Office 365 E5 and EMS E5 trial or permanent subscriptions with the DNS domain testlab.\<your public domain name> registered.</span></span>
- <span data-ttu-id="17eb3-131">Una intranet dell’organizzazione semplificata connessa a Internet e costituita dalle macchine virtuali DC1 APP1 e CLIENT1 in una sottorete di una rete virtuale Azure.</span><span class="sxs-lookup"><span data-stu-id="17eb3-131">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>

<span data-ttu-id="17eb3-132">Si noti come il testlab.\<nome di dominio pubblico> a questo punto è:</span><span class="sxs-lookup"><span data-stu-id="17eb3-132">Notice how the testlab.\<your public domain name> is now:</span></span>

- <span data-ttu-id="17eb3-133">Ospitato da record DNS pubblici.</span><span class="sxs-lookup"><span data-stu-id="17eb3-133">Supported by public DNS records.</span></span>
- <span data-ttu-id="17eb3-134">Registrato negli abbonamenti a Office 365 ed EMS.</span><span class="sxs-lookup"><span data-stu-id="17eb3-134">Registered in your Office 365 and EMS subscriptions.</span></span>
- <span data-ttu-id="17eb3-135">Il dominio di Windows Server AD sulla rete intranet simulata.</span><span class="sxs-lookup"><span data-stu-id="17eb3-135">The Windows Server AD domain on your simulated intranet.</span></span>
     
## <a name="phase-3-install-azure-ad-connect-on-app1"></a><span data-ttu-id="17eb3-136">Fase 3: installare Azure AD Connect su APP1</span><span class="sxs-lookup"><span data-stu-id="17eb3-136">Phase 3: Install Azure AD Connect on APP1</span></span>

<span data-ttu-id="17eb3-137">In questa fase, installare e configurare lo strumento Azure AD Connect su APP1 e verificarne il funzionamento.</span><span class="sxs-lookup"><span data-stu-id="17eb3-137">In this phase, you install and configure the Azure AD Connect tool on APP1, and then verify that it works.</span></span>
  
<span data-ttu-id="17eb3-138">In primo luogo, installare e configurare Azure AD Connect su APP1.</span><span class="sxs-lookup"><span data-stu-id="17eb3-138">First, you install and configure Azure AD Connect on APP1.</span></span>

1. <span data-ttu-id="17eb3-139">Dal [portale di Azure](https://portal.azure.com), accedere con l'account di amministratore globale e connettersi ad APP1 con l'account TESTLAB\\User1.</span><span class="sxs-lookup"><span data-stu-id="17eb3-139">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\\User1 account.</span></span>
    
2. <span data-ttu-id="17eb3-140">Dal desktop di APP1, aprire un prompt dei comandi di Windows PowerShell a livello di amministratore ed eseguire questi comandi:</span><span class="sxs-lookup"><span data-stu-id="17eb3-140">From the desktop of APP1, open an administrator-level Windows PowerShell command prompt, and then run these commands:</span></span>
    
   ```
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A7-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A8-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Stop-Process -Name Explorer -Force
   ```

3. <span data-ttu-id="17eb3-141">Dalla barra delle applicazioni, fare clic su **Internet Explorer** e accedere a [https://aka.ms/aadconnect](https://aka.ms/aadconnect).</span><span class="sxs-lookup"><span data-stu-id="17eb3-141">From the task bar, click **Internet Explorer** and go to [https://aka.ms/aadconnect](https://aka.ms/aadconnect).</span></span>
    
4. <span data-ttu-id="17eb3-142">Nella pagina Microsoft Azure Active Directory Connect, fare clic su **Download** e quindi su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="17eb3-142">On the Microsoft Azure Active Directory Connect page, click **Download**, and then click **Run**.</span></span>
    
5. <span data-ttu-id="17eb3-143">Nella pagina di **Benvenuto in Azure Active Directory Connect**, fare clic su **Accetto** e quindi su **Continua**.</span><span class="sxs-lookup"><span data-stu-id="17eb3-143">On the **Welcome to Azure AD Connect** page, click **I agree**, and then click **Continue**.</span></span>
    
6. <span data-ttu-id="17eb3-144">Nella pagina **Impostazioni rapide**, fare clic su **Usa impostazioni rapide**.</span><span class="sxs-lookup"><span data-stu-id="17eb3-144">On the **Express Settings** page, click **Use express settings**.</span></span>
    
7. <span data-ttu-id="17eb3-145">Nella pagina **Connessione ad Azure AD**, digitare il nome dell’account amministratore globale di Office 365 in **Nome utente**, digitare la password in **Password** e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="17eb3-145">On the **Connect to Azure AD** page, type your Office 365 global administrator account name in **Username,** type its password in **Password**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="17eb3-146">Nella pagina **Connessione ad AD DS**, digitare **TESTLAB\\User1** in **Nome utente**, digitare la relativa password in **Password** e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="17eb3-146">On the **Connect to AD DS** page, type **TESTLAB\\User1** in **Username,** type its password in **Password**, and then click **Next**.</span></span>
    
9. <span data-ttu-id="17eb3-147">Nella pagina **Pronto per la configurazione** fare clic su **Installa**.</span><span class="sxs-lookup"><span data-stu-id="17eb3-147">On the **Ready to configure** page, click **Install**.</span></span>
    
10. <span data-ttu-id="17eb3-148">Nella pagina **Configurazione completata**, fare clic su **Esci**.</span><span class="sxs-lookup"><span data-stu-id="17eb3-148">On the **Configuration complete** page, click **Exit**.</span></span>
    
11. <span data-ttu-id="17eb3-149">In Internet Explorer, passare al portale di Office 365 ([https://portal.office.com](https://portal.office.com)).</span><span class="sxs-lookup"><span data-stu-id="17eb3-149">In Internet Explorer, go to the Office 365 portal ([https://portal.office.com](https://portal.office.com)).</span></span>
    
12. <span data-ttu-id="17eb3-150">Dalla pagina principale del portale, fare clic su **Admin**.</span><span class="sxs-lookup"><span data-stu-id="17eb3-150">From the main portal page, click **Admin**.</span></span>
    
13. <span data-ttu-id="17eb3-151">Nel riquadro di spostamento sinistro fare clic su **Utenti > Utenti attivi**.</span><span class="sxs-lookup"><span data-stu-id="17eb3-151">In the left navigation, click **Users > Active users**.</span></span>
    
    <span data-ttu-id="17eb3-p106">Si noti l'account denominato **User1**. Questo account deriva dal dominio TESTLAB di Windows Server Active Directory ed è la prova che la sincronizzazione della directory ha funzionato.</span><span class="sxs-lookup"><span data-stu-id="17eb3-p106">Note the account named **User1**. This account is from the TESTLAB Windows Server AD domain and is proof that directory synchronization has worked.</span></span>
    
14. <span data-ttu-id="17eb3-p107">Fare clic sull'account **User1**. Per le licenze di prodotti, fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="17eb3-p107">Click the **User1** account. For product licenses, click **Edit**.</span></span>
    
15. <span data-ttu-id="17eb3-p108">In **Licenze di prodotti**, selezionare il paese e fare clic sul controllo **Disattiva** per **Office 365 Enterprise E5** (passando ad **Attiva**). Eseguire la stessa operazione per la licenza **Enterprise Mobility + Security E5**.</span><span class="sxs-lookup"><span data-stu-id="17eb3-p108">In **Product licenses**, select your scountry, and then click the **Off** control for **Office 365 Enterprise E5** (switching it to **On**). Do the same for the **Enterprise Mobility + Security E5** license.</span></span> 

16. <span data-ttu-id="17eb3-158">Fare clic su **Salva** nella parte inferiore della pagina e selezionare **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="17eb3-158">Click **Save** at the bottom of the page, and then click **Close**.</span></span>
    
<span data-ttu-id="17eb3-159">Successivamente, verificare la possibilità di accedere all'abbonamento a Office 365 con il nome utente <strong>user1@testlab.</strong>\<nome dominio> nome utente dell'account User1.</span><span class="sxs-lookup"><span data-stu-id="17eb3-159">Next, you test the ability to sign in to your Office 365 subscription with the <strong>user1@testlab.</strong>\<your domain name> user name of the User1 account.</span></span>

1. <span data-ttu-id="17eb3-160">Da APP1, disconnettersi da Office 365, quindi accedere nuovamente specificando un account diverso.</span><span class="sxs-lookup"><span data-stu-id="17eb3-160">From APP1, sign out of Office 365, and then sign in again, this time specifying a different account.</span></span>

2. <span data-ttu-id="17eb3-p109">Quando vengono richiesti nome utente e password, specificare <strong>user1@testlab.</strong>\<nome dominio> e la password per User1. Dovrebbe essere possibile accedere come User1.</span><span class="sxs-lookup"><span data-stu-id="17eb3-p109">When prompted for a user name and password, specify <strong>user1@testlab.</strong>\<your domain name> and the User1 password. You should successfully sign in as User1.</span></span> 
 
<span data-ttu-id="17eb3-p110">Si noti che sebbene User1 disponga di autorizzazioni di amministratore di dominio per il dominio TESTLAB Windows Server AD, non è un amministratore globale di Office 365. Di conseguenza, non si vedrà l'icona **Amministratore**.</span><span class="sxs-lookup"><span data-stu-id="17eb3-p110">Notice that although User1 has domain administrator permissions for the TESTLAB Windows Server AD domain, it is not an Office 365 global administrator. Therefore, you will not see the **Admin** icon as an option.</span></span> 

<span data-ttu-id="17eb3-165">Di seguito è riportata la configurazione risultante.</span><span class="sxs-lookup"><span data-stu-id="17eb3-165">Here is your resulting configuration.</span></span>

![L'organizzazione simulata con ambiente di testing per la sincronizzazione hash delle password](media/password-hash-sync-m365-ent-test-environment/Phase3.png)

<span data-ttu-id="17eb3-167">Questa configurazione è costituita da:</span><span class="sxs-lookup"><span data-stu-id="17eb3-167">This configuration consists of:</span></span> 
  
- <span data-ttu-id="17eb3-168">Abbonamenti di valutazione o permanenti a Office 365 E5 ed EMS E5 con dominio DNS TESTLAB.\<nome dominio> registrato.</span><span class="sxs-lookup"><span data-stu-id="17eb3-168">Office 365 E5 and EMS E5 trial or permanent subscriptions with the DNS domain TESTLAB.\<your domain name> registered.</span></span>
- <span data-ttu-id="17eb3-p111">Una intranet dell'organizzazione semplificata connessa a Internet e costituita dalle macchine virtuali DC1, APP1 e CLIENT1 in una sottorete di una rete virtuale Azure. Periodicamente, Azure AD Connect viene eseguito su APP1 per sincronizzare il dominio TESTLAB di Windows Server AD per il tenant Azure AD degli abbonamenti a Office 365 ed EMS E5.</span><span class="sxs-lookup"><span data-stu-id="17eb3-p111">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network. Azure AD Connect runs on APP1 to synchronize the TESTLAB Windows Server AD domain to the Azure AD tenant of your Office 365 and EMS E5 subscriptions periodically.</span></span>
- <span data-ttu-id="17eb3-171">L'account User1 nel dominio TESTLAB di Windows Server Active Directory è stato sincronizzato con il tenant Azure AD.</span><span class="sxs-lookup"><span data-stu-id="17eb3-171">The User1 account in the TESTLAB  Windows Server AD domain has been synchronized with the Azure AD tenant.</span></span>

## <a name="next-step"></a><span data-ttu-id="17eb3-172">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="17eb3-172">Next step</span></span>

<span data-ttu-id="17eb3-173">Esplorare altre caratteristiche e funzionalità [identità](m365-enterprise-test-lab-guides.md#identity) nell'ambiente di test.</span><span class="sxs-lookup"><span data-stu-id="17eb3-173">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="17eb3-174">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="17eb3-174">See also</span></span>

[<span data-ttu-id="17eb3-175">Guide al lab di test di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="17eb3-175">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="17eb3-176">Distribuzione di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="17eb3-176">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="17eb3-177">Documentazione di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="17eb3-177">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)


