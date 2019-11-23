---
title: Autenticazione pass-through per l'ambiente di testing di Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/21/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLG
- Ent_TLGs
ms.assetid: ''
description: "Riepilogo: configurare l'autenticazione pass-through per l'ambiente di testing di Microsoft 365."
ms.openlocfilehash: ed21007932b455c4f24af83434af75d44e583574
ms.sourcegitcommit: fb3815ee186b2b3ec790ee32a9d7b1628d623b0b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "39202317"
---
# <a name="pass-through-authentication-for-your-microsoft-365-test-environment"></a><span data-ttu-id="854b3-103">Autenticazione pass-through per l'ambiente di testing di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="854b3-103">Pass-through authentication for your Microsoft 365 test environment</span></span>

<span data-ttu-id="854b3-104">*Questa guida al lab di test può essere usata sia per ambienti di testing di Microsoft 365 Enterprise che Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="854b3-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="854b3-105">Le organizzazioni che vogliono usare direttamente l'infrastruttura di Active Directory Domain Services locale per l'autenticazione per le applicazioni e servizi basati sul cloud di Microsoft, possono usare l'autenticazione pass-through.</span><span class="sxs-lookup"><span data-stu-id="854b3-105">Organizations that want to directly use their on-premises Active Directory Domain Services (AD DS) infrastructure for authentication to Microsoft cloud-based services and applications can use pass-through authentication.</span></span> <span data-ttu-id="854b3-106">In questo articolo viene descritto come configurare l'ambiente di testing di Microsoft 365 per l'autenticazione pass-through, con la seguente configurazione come risultato:</span><span class="sxs-lookup"><span data-stu-id="854b3-106">This article describes how you can configure your Microsoft 365 test environment for pass-through authentication, resulting in the following configuration:</span></span>
  
![L'organizzazione simulata con ambiente di testing per l'autenticazione pass-through](media/pass-through-auth-m365-ent-test-environment/Phase2.png)
  
<span data-ttu-id="854b3-108">Le fasi principali della configurazione dell'ambiente di testing sono tre:</span><span class="sxs-lookup"><span data-stu-id="854b3-108">There are two phases to setting up this test environment:</span></span>

1.  <span data-ttu-id="854b3-109">Creare l'ambiente di testing dell'organizzazione simulata di Microsoft 365 con per la sincronizzazione hash delle password.</span><span class="sxs-lookup"><span data-stu-id="854b3-109">Create the Microsoft 365 simulated enterprise test environment with password hash synchronization.</span></span>
2.  <span data-ttu-id="854b3-110">Configurare Azure AD Connect su APP1 per l'autenticazione pass-through.</span><span class="sxs-lookup"><span data-stu-id="854b3-110">Configure Azure AD Connect on APP1 for pass-through authentication.</span></span>
    
![Guide del laboratorio di testing per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="854b3-112">Fare clic [qui](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) per consultare una mappa di tutti gli articoli relativi alla guida al lab test di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="854b3-112">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="854b3-113">Fase 1: configurare la sincronizzazione hash delle password per l'ambiente di testing di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="854b3-113">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="854b3-p102">Seguire le istruzioni riportate in [sincronizzazione hash delle password per Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Di seguito è riportata la configurazione risultante.</span><span class="sxs-lookup"><span data-stu-id="854b3-p102">Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Here is your resulting configuration.</span></span>
  
![L'organizzazione simulata con ambiente di testing per la sincronizzazione hash delle password](media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="854b3-117">Questa configurazione è costituita da:</span><span class="sxs-lookup"><span data-stu-id="854b3-117">This configuration consists of:</span></span> 
  
- <span data-ttu-id="854b3-118">Abbonamenti di valutazione o a pagamento a Microsoft 365 E5 o a Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="854b3-118">Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions.</span></span>
- <span data-ttu-id="854b3-119">Una intranet dell’organizzazione semplificata connessa a Internet e costituita dalle macchine virtuali DC1 APP1 e CLIENT1 in una sottorete di una rete virtuale Azure.</span><span class="sxs-lookup"><span data-stu-id="854b3-119">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> <span data-ttu-id="854b3-120">Azure AD Connect viene eseguito su APP1 per sincronizzare periodicamente il dominio TESTLAB di Active Directory Domain Services con il tenant di Azure AD dell'abbonamento a Microsoft 365 o a Office 365.</span><span class="sxs-lookup"><span data-stu-id="854b3-120">Azure AD Connect runs on APP1 to synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Microsoft 365 or Office 365 subscription periodically.</span></span>

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-pass-through-authentication"></a><span data-ttu-id="854b3-121">Fase 2: configurare Azure AD Connect su APP1 per l'autenticazione pass-through</span><span class="sxs-lookup"><span data-stu-id="854b3-121">Phase 2: Configure Azure AD Connect on APP1 for pass-through authentication</span></span>

<span data-ttu-id="854b3-122">Questa fase riguarda la configurazione di Azure AD Connect su APP1 per l'uso dell'autenticazione pass-through e verificare che funzioni.</span><span class="sxs-lookup"><span data-stu-id="854b3-122">In this phase, you configure Azure AD Connect on APP1 to use pass-through authentication, and then verify that it works.</span></span>

### <a name="configure-azure-ad-connect-on-app1"></a><span data-ttu-id="854b3-123">Configurare Azure AD Connect su APP1</span><span class="sxs-lookup"><span data-stu-id="854b3-123">Configure Azure AD Connect on APP1</span></span>

1.  <span data-ttu-id="854b3-124">Dal [portale di Azure](https://portal.azure.com), accedere con l'account di amministratore globale e connettersi ad APP1 con l'account TESTLAB\User1.</span><span class="sxs-lookup"><span data-stu-id="854b3-124">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2.  <span data-ttu-id="854b3-125">Dal desktop di APP1, eseguire Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="854b3-125">From the desktop of APP1, run Azure AD Connect.</span></span>

3.  <span data-ttu-id="854b3-126">Nella **Pagina di benvenuto** fare clic su **Configura**.</span><span class="sxs-lookup"><span data-stu-id="854b3-126">On the **Welcome page**, click **Configure**.</span></span>

4.  <span data-ttu-id="854b3-127">Nella pagina Attività addizionali fare clic su **Cambia l'accesso utente**, quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="854b3-127">On the Additional tasks page, click **Change user sign-in**, and then click **Next**.</span></span>

5.  <span data-ttu-id="854b3-128">Nella pagina **Connessione ad Azure AD**, digitare le credenziali dell'account amministratore globale e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="854b3-128">On the **Connect to Azure AD** page, type your global administrator account credentials, and then click **Next**.</span></span>

6.  <span data-ttu-id="854b3-129">Nella pagina **Accesso utente** fare clic su **Autenticazione pass-through**, quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="854b3-129">On the **User sign-in** page, click **Pass-through authentication**, and then click **Next**.</span></span>

7.  <span data-ttu-id="854b3-130">Nella pagina **Pronto per la configurazione** fare clic su **Configura**.</span><span class="sxs-lookup"><span data-stu-id="854b3-130">On the **Ready to configure** page, click **Configure**.</span></span>

8.  <span data-ttu-id="854b3-131">Nella pagina **Configurazione completata**, fare clic su **Esci**.</span><span class="sxs-lookup"><span data-stu-id="854b3-131">On the **Configuration complete** page, click **Exit**.</span></span>

9.  <span data-ttu-id="854b3-p104">Dal portale di Azure, nel riquadro sinistro, fare clic su **Azure Active Directory > Azure AD Connect**. Verificare che la funzionalità **Autenticazione pass-through** venga visualizzata come **Attivata**.</span><span class="sxs-lookup"><span data-stu-id="854b3-p104">From the Azure portal, in the left pane, click **Azure Active Directory > Azure AD Connect**. Verify that the **Pass-through authentication** feature appears as **Enabled**.</span></span>

10. <span data-ttu-id="854b3-p105">Fare clic su **Autenticazione pass-through**. Nel riquadro **Autenticazione pass-through** sono elencati i server in cui sono installati gli Agenti di autenticazione. APP1 sarà presente nell'elenco. Chiudere il riquadro **Autenticazione pass-through**.</span><span class="sxs-lookup"><span data-stu-id="854b3-p105">Click **Pass-through authentication**. The **Pass-through authentication** pane lists the servers where your Authentication Agents are installed. You should see APP1 in the list. Close the **Pass-through authentication** pane.</span></span>

<span data-ttu-id="854b3-138">Successivamente, verificare la possibilità di accedere all'abbonamento con il nome utente <strong>user1@testlab.</strong>\<dominio pubblico> dell'account User1.</span><span class="sxs-lookup"><span data-stu-id="854b3-138">Next, test the ability to sign in to your Office 365 subscription with the <strong>user1@testlab.</strong>\<your public domain> user name of the User1 account.</span></span>

1. <span data-ttu-id="854b3-139">Da APP1, disconnettersi e quindi accedere nuovamente specificando un account diverso.</span><span class="sxs-lookup"><span data-stu-id="854b3-139">From APP1, sign out of Office 365, and then sign in again, this time specifying a different account.</span></span>

2. <span data-ttu-id="854b3-140">Quando vengono richiesti nome utente e password, specificare <strong>user1@testlab.</strong>\<dominio pubblico> e la password per User1.</span><span class="sxs-lookup"><span data-stu-id="854b3-140">When prompted for a user name and password, specify <strong>user1@testlab.</strong>\<your public domain> and the User1 password.</span></span> <span data-ttu-id="854b3-141">Dovrebbe essere possibile accedere come User1.</span><span class="sxs-lookup"><span data-stu-id="854b3-141">You should successfully sign in as User1.</span></span>

<span data-ttu-id="854b3-142">Si noti che sebbene User1 disponga di autorizzazioni di amministratore di dominio per il dominio TESTLAB AD DS, non è un amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="854b3-142">Notice that although User1 has domain administrator permissions for the TESTLAB AD DS domain, it is not a global administrator for Azure AD and Office 365.</span></span> <span data-ttu-id="854b3-143">Di conseguenza, l'icona **Amministratore** non sarà visibile.</span><span class="sxs-lookup"><span data-stu-id="854b3-143">Therefore, you will not see the **Admin** icon as an option.</span></span>

<span data-ttu-id="854b3-144">Di seguito è riportata la configurazione risultante:</span><span class="sxs-lookup"><span data-stu-id="854b3-144">Here is your resulting configuration:</span></span>

![L'organizzazione simulata con ambiente di testing per l'autenticazione pass-through](media/pass-through-auth-m365-ent-test-environment/Phase2.png)
 
<span data-ttu-id="854b3-146">Questa configurazione è costituita da:</span><span class="sxs-lookup"><span data-stu-id="854b3-146">This configuration consists of:</span></span>

- <span data-ttu-id="854b3-147">Abbonamenti di valutazione o a pagamento a Microsoft 365 E5 o a Office 365 E5 con il dominio DNS testlab.\<nome dominio> registrato.</span><span class="sxs-lookup"><span data-stu-id="854b3-147">Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions with the DNS domain testlab.\<your domain name> registered.</span></span>
- <span data-ttu-id="854b3-p108">Una intranet dell'organizzazione semplificata connessa a Internet e costituita dalle macchine virtuali DC1, APP1 e CLIENT1 in una sottorete di una rete virtuale Azure. Un Agente di autenticazione viene eseguito su APP1 per gestire le richieste di autenticazione pass-through dal tenant di Azure AD dell'abbonamento a Microsoft 365 o a Office 365.</span><span class="sxs-lookup"><span data-stu-id="854b3-p108">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network. An Authentication Agent runs on APP1 to handle pass-through authentication requests from the Azure AD tenant of your Microsoft 365 or Office 365 subscription.</span></span>

## <a name="next-step"></a><span data-ttu-id="854b3-150">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="854b3-150">Next step</span></span>

<span data-ttu-id="854b3-151">Esplorare altre caratteristiche e funzionalità [identità](m365-enterprise-test-lab-guides.md#identity) nell'ambiente di test.</span><span class="sxs-lookup"><span data-stu-id="854b3-151">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="854b3-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="854b3-152">See also</span></span>

[<span data-ttu-id="854b3-153">Guide al lab di test di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="854b3-153">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="854b3-154">Distribuzione di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="854b3-154">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="854b3-155">Documentazione di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="854b3-155">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
