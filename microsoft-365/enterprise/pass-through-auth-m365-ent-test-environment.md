---
title: Autenticazione pass-through per l'ambiente di testing di Microsoft 365
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
description: "Riepilogo: configurare l'autenticazione pass-through per l'ambiente di testing di Microsoft 365."
ms.openlocfilehash: 26222f04617999104a1ad010eb189a0c01370a6d
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868473"
---
# <a name="pass-through-authentication-for-your-microsoft-365-test-environment"></a><span data-ttu-id="0f2ba-103">Autenticazione pass-through per l'ambiente di testing di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0f2ba-103">Pass-through authentication for your Microsoft 365 test environment</span></span>

<span data-ttu-id="0f2ba-p101">Le organizzazioni che vogliono usare direttamente l'infrastruttura di Windows Server Active Directory (AD) locale per l'autenticazione per le applicazioni e servizi basati sul cloud di Microsoft, possono utilizzare l'autenticazione pass-through. In questo articolo viene descritto come configurare l'ambiente di testing di Microsoft 365 per l'autenticazione pass-through, con la seguente configurazione come risultato:</span><span class="sxs-lookup"><span data-stu-id="0f2ba-p101">Organizations that want to directly use their on-premises Windows Server Active Directory (AD) infrastructure for authentication to Microsoft cloud-based services and applications can use pass-through authentication. This article describes how you can configure your Microsoft 365 test environment for pass-through authentication, resulting in the following configuration:</span></span>
  
![L'organizzazione simulata con ambiente di testing per l'autenticazione pass-through](media/pass-through-auth-m365-ent-test-environment/Phase2.png)
  
<span data-ttu-id="0f2ba-107">Le fasi principali della configurazione dell'ambiente di testing sono tre:</span><span class="sxs-lookup"><span data-stu-id="0f2ba-107">There are two phases to setting up this test environment:</span></span>

1.  <span data-ttu-id="0f2ba-108">Creare l'ambiente di testing dell'organizzazione simulata di Microsoft 365 con per la sincronizzazione hash delle password.</span><span class="sxs-lookup"><span data-stu-id="0f2ba-108">Create the Microsoft 365 simulated enterprise test environment with password hash synchronization.</span></span>
2.  <span data-ttu-id="0f2ba-109">Configurare Azure AD Connect su APP1 per l'autenticazione pass-through.</span><span class="sxs-lookup"><span data-stu-id="0f2ba-109">Configure Azure AD Connect on APP1 for pass-through authentication.</span></span>
    
![Guide del laboratorio di testing per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="0f2ba-111">Fare clic [qui](https://aka.ms/m365etlgstack) per consultare una mappa di tutti gli articoli relativi alla guida al lab test di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="0f2ba-111">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="0f2ba-112">Fase 1: configurare la sincronizzazione hash delle password per l'ambiente di testing di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0f2ba-112">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="0f2ba-p102">Seguire le istruzioni riportate in [sincronizzazione hash delle password per Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Di seguito è riportata la configurazione risultante.</span><span class="sxs-lookup"><span data-stu-id="0f2ba-p102">Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Here is your resulting configuration.</span></span>
  
![L'organizzazione simulata con ambiente di testing per la sincronizzazione hash delle password](media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="0f2ba-116">Questa configurazione è costituita da:</span><span class="sxs-lookup"><span data-stu-id="0f2ba-116">This configuration consists of:</span></span> 
  
- <span data-ttu-id="0f2ba-117">Abbonamenti di valutazione o permanenti a Office 365 E5 ed EMS E5.</span><span class="sxs-lookup"><span data-stu-id="0f2ba-117">Office 365 E5 and EMS E5 trial or permanent subscriptions.</span></span>
- <span data-ttu-id="0f2ba-p103">Una intranet dell'organizzazione semplificata connessa a Internet e costituita dalle macchine virtuali DC1, APP1 e CLIENT1 in una sottorete di una rete virtuale Azure. Periodicamente, Azure AD Connect viene eseguito su APP1 per sincronizzare il dominio TESTLAB di Windows Server AD per il tenant Azure AD degli abbonamenti a Office 365 ed EMS E5.</span><span class="sxs-lookup"><span data-stu-id="0f2ba-p103">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network. Azure AD Connect runs on APP1 to synchronize the TESTLAB Windows Server AD domain to the Azure AD tenant of your Office 365 and EMS E5 subscriptions periodically.</span></span>

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-pass-through-authentication"></a><span data-ttu-id="0f2ba-120">Fase 2: configurare Azure AD Connect su APP1 per l'autenticazione pass-through</span><span class="sxs-lookup"><span data-stu-id="0f2ba-120">Phase 2: Configure Azure AD Connect on APP1 for pass-through authentication</span></span>

<span data-ttu-id="0f2ba-121">Questa fase riguarda la configurazione di Azure AD Connect su APP1 per l'uso dell'autenticazione pass-through e verificare che funzioni.</span><span class="sxs-lookup"><span data-stu-id="0f2ba-121">In this phase, you configure Azure AD Connect on APP1 to use pass-through authentication, and then verify that it works.</span></span>

### <a name="configure-azure-ad-connect-on-app1"></a><span data-ttu-id="0f2ba-122">Configurare Azure AD Connect su APP1</span><span class="sxs-lookup"><span data-stu-id="0f2ba-122">Configure Azure AD Connect on APP1</span></span>

1.  <span data-ttu-id="0f2ba-123">Dal [portale di Azure](https://portal.azure.com), accedere con l'account di amministratore globale e connettersi ad APP1 con l'account TESTLAB\User1.</span><span class="sxs-lookup"><span data-stu-id="0f2ba-123">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2.  <span data-ttu-id="0f2ba-124">Dal desktop di APP1, eseguire Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="0f2ba-124">From the desktop of APP1, run Azure AD Connect.</span></span>

3.  <span data-ttu-id="0f2ba-125">Nella **Pagina di benvenuto** fare clic su **Configura**.</span><span class="sxs-lookup"><span data-stu-id="0f2ba-125">On the **Welcome page**, click **Configure**.</span></span>

4.  <span data-ttu-id="0f2ba-126">Nella pagina Attività addizionali fare clic su **Cambia l'accesso utente**, quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="0f2ba-126">On the Additional tasks page, click **Change user sign-in**, and then click **Next**.</span></span>

5.  <span data-ttu-id="0f2ba-127">Nella pagina **Connessione ad Azure AD**, digitare le credenziali dell'account amministratore globale e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="0f2ba-127">On the **Connect to Azure AD** page, type your global administrator account credentials, and then click **Next**.</span></span>

6.  <span data-ttu-id="0f2ba-128">Nella pagina **Accesso utente** fare clic su **Autenticazione pass-through**, quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="0f2ba-128">On the **User sign-in** page, click **Pass-through authentication**, and then click **Next**.</span></span>

7.  <span data-ttu-id="0f2ba-129">Nella pagina **Pronto per la configurazione** fare clic su **Configura**.</span><span class="sxs-lookup"><span data-stu-id="0f2ba-129">On the **Ready to configure** page, click **Configure**.</span></span>

8.  <span data-ttu-id="0f2ba-130">Nella pagina **Configurazione completata**, fare clic su **Esci**.</span><span class="sxs-lookup"><span data-stu-id="0f2ba-130">On the **Configuration complete** page, click **Exit**.</span></span>

9.  <span data-ttu-id="0f2ba-p104">Dal portale di Azure, nel riquadro sinistro, fare clic su **Azure Active Directory > Azure AD Connect**. Verificare che la funzionalità **Autenticazione pass-through** venga visualizzata come **Attivata**.</span><span class="sxs-lookup"><span data-stu-id="0f2ba-p104">From the Azure portal, in the left pane, click **Azure Active Directory > Azure AD Connect**. Verify that the **Pass-through authentication** feature appears as **Enabled**.</span></span>

10. <span data-ttu-id="0f2ba-p105">Fare clic su **Autenticazione pass-through**. Nel riquadro **Autenticazione pass-through** sono elencati i server in cui sono installati gli Agenti di autenticazione. APP1 sarà presente nell'elenco. Chiudere il riquadro **Autenticazione pass-through**.</span><span class="sxs-lookup"><span data-stu-id="0f2ba-p105">Click **Pass-through authentication**. The **Pass-through authentication** pane lists the servers where your Authentication Agents are installed. You should see APP1 in the list. Close the **Pass-through authentication** pane.</span></span>

<span data-ttu-id="0f2ba-137">Successivamente, verificare la possibilità di accedere all'abbonamento a Office 365 con il nome utente user1@testlab.\<dominio pubblico> dell'account User1.</span><span class="sxs-lookup"><span data-stu-id="0f2ba-137">Next, test the ability to sign in to your Office 365 subscription with the user1@testlab.\<your public domain> user name of the User1 account.</span></span>

1. <span data-ttu-id="0f2ba-138">Da APP1, disconnettersi da Office 365, quindi accedere nuovamente specificando un account diverso.</span><span class="sxs-lookup"><span data-stu-id="0f2ba-138">From APP1, sign out of Office 365, and then sign in again, this time specifying a different account.</span></span>

2. <span data-ttu-id="0f2ba-p106">Quando vengono richiesti nome utente e password, specificare user1@testlab.\<dominio pubblico> e la password per User1. Dovrebbe essere possibile accedere come User1.</span><span class="sxs-lookup"><span data-stu-id="0f2ba-p106">When prompted for a user name and password, specify user1@testlab.\<your public domain> and the User1 password. You should successfully sign in as User1.</span></span>

<span data-ttu-id="0f2ba-p107">Si noti che sebbene User1 disponga di autorizzazioni di amministratore di dominio per il dominio TESTLAB Windows Server AD, non è un amministratore globale di Office 365. Di conseguenza, non si vedrà l'icona **Amministratore**.</span><span class="sxs-lookup"><span data-stu-id="0f2ba-p107">Notice that although User1 has domain administrator permissions for the TESTLAB Windows Server AD domain, it is not an Office 365 global administrator. Therefore, you will not see the **Admin** icon as an option.</span></span>

<span data-ttu-id="0f2ba-143">Di seguito è riportata la configurazione risultante:</span><span class="sxs-lookup"><span data-stu-id="0f2ba-143">Here is your resulting configuration:</span></span>

![L'organizzazione simulata con ambiente di testing per l'autenticazione pass-through](media/pass-through-auth-m365-ent-test-environment/Phase2.png)
 
<span data-ttu-id="0f2ba-145">Questa configurazione è costituita da:</span><span class="sxs-lookup"><span data-stu-id="0f2ba-145">This configuration consists of:</span></span>

- <span data-ttu-id="0f2ba-146">Abbonamenti di valutazione o permanenti a Office 365 E5 ed EMS E5 con dominio DNS TESTLAB.\<nome dominio> registrato.</span><span class="sxs-lookup"><span data-stu-id="0f2ba-146">Office 365 E5 and EMS E5 trial or permanent subscriptions with the DNS domain TESTLAB.\<your domain name> registered.</span></span>
- <span data-ttu-id="0f2ba-p108">Una intranet dell'organizzazione semplificata connessa a Internet e costituita dalle macchine virtuali DC1, APP1 e CLIENT1 in una sottorete di una rete virtuale Azure. Un Agente di autenticazione viene eseguito su APP1 per gestire le richieste di autenticazione pass-through dal tenant Azure AD degli abbonamenti a Office 365 ed EMS E5.</span><span class="sxs-lookup"><span data-stu-id="0f2ba-p108">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network. An Authentication Agent runs on APP1 to handle pass-through authentication requests from the Azure AD tenant of your Office 365 and EMS E5 subscriptions.</span></span>

## <a name="next-step"></a><span data-ttu-id="0f2ba-149">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="0f2ba-149">Next step</span></span>

<span data-ttu-id="0f2ba-150">Esplorare altre caratteristiche e funzionalità [identità](m365-enterprise-test-lab-guides.md#identity) nell'ambiente di test.</span><span class="sxs-lookup"><span data-stu-id="0f2ba-150">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="0f2ba-151">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0f2ba-151">See also</span></span>

[<span data-ttu-id="0f2ba-152">Guide al lab di test di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="0f2ba-152">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="0f2ba-153">Distribuzione di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="0f2ba-153">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="0f2ba-154">Documentazione di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="0f2ba-154">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)


