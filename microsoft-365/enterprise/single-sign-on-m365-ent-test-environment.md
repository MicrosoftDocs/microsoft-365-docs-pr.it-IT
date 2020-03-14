---
title: Azure AD Seamless Single Sign-On per l'ambiente di testing di Microsoft 365
f1.keywords:
- NOCSH
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
- TLGS
- Ent_TLGs
ms.assetid: ''
description: "Riepilogo: informazioni sulla configurazione e sul test di Azure AD Seamless Single Sign-On per l'ambiente di testing di Microsoft 365."
ms.openlocfilehash: d2b17acb2b57e379fe204e3ea4402b3f00ef7d6c
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/13/2020
ms.locfileid: "42633164"
---
# <a name="azure-ad-seamless-single-sign-on-for-your-microsoft-365-test-environment"></a><span data-ttu-id="bbd89-103">Azure AD Seamless Single Sign-On per l'ambiente di testing di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="bbd89-103">Azure AD Seamless Single Sign-on for your Microsoft 365 test environment</span></span>

<span data-ttu-id="bbd89-104">*Questa guida al lab di test può essere usata sia per ambienti di testing di Microsoft 365 Enterprise che Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="bbd89-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="bbd89-p101">Azure AD Seamless Single Sign-On consente agli utenti di eseguire l'accesso automaticamente quando utilizzano il proprio PC o i dispositivi connessi alla rete aziendale. Azure AD Seamless Single Sign-On permette agli utenti di accedere facilmente alle applicazioni basate sul cloud senza usare componenti aggiuntivi in locale.</span><span class="sxs-lookup"><span data-stu-id="bbd89-p101">Azure AD Seamless Single Sign-On (SSO) automatically signs in users when they are on their PCs or devices that are connected to their organization network. Azure AD Seamless SSO provides users with easy access to cloud-based applications without needing any additional on-premises components.</span></span>

<span data-ttu-id="bbd89-107">In questo articolo viene descritto come configurare l'ambiente di testing di Microsoft 365 per Azure AD Seamless SSO.</span><span class="sxs-lookup"><span data-stu-id="bbd89-107">This article describes how you can configure your Microsoft 365 test environment for Azure AD Seamless SSO.</span></span>

<span data-ttu-id="bbd89-108">Esistono due fasi per la configurazione:</span><span class="sxs-lookup"><span data-stu-id="bbd89-108">There are two phases to setting this up:</span></span>

1.  <span data-ttu-id="bbd89-109">Creare l'ambiente di testing dell'organizzazione simulata di Microsoft 365 con per la sincronizzazione hash delle password.</span><span class="sxs-lookup"><span data-stu-id="bbd89-109">Create the Microsoft 365 simulated enterprise test environment with password hash synchronization.</span></span>
2.  <span data-ttu-id="bbd89-110">Configurare Azure AD Connect su APP1 per Azure AD Seamless Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="bbd89-110">Configure Azure AD Connect on APP1 for Azure AD Seamless SSO.</span></span>
    
![Guide del laboratorio di testing per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="bbd89-112">Fare clic [qui](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) per consultare una mappa di tutti gli articoli relativi alla guida al lab test di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="bbd89-112">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="bbd89-113">Fase 1: configurare la sincronizzazione hash delle password per l'ambiente di testing di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="bbd89-113">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="bbd89-p102">Seguire le istruzioni riportate in [sincronizzazione hash delle password per Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Di seguito è riportata la configurazione risultante.</span><span class="sxs-lookup"><span data-stu-id="bbd89-p102">Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Here is your resulting configuration.</span></span>
  
![L'organizzazione simulata con ambiente di testing per la sincronizzazione hash delle password](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="bbd89-117">Questa configurazione è costituita da:</span><span class="sxs-lookup"><span data-stu-id="bbd89-117">This configuration consists of:</span></span> 
  
- <span data-ttu-id="bbd89-118">Abbonamenti di valutazione o a pagamento a Microsoft 365 E5 o a Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="bbd89-118">Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions.</span></span>
- <span data-ttu-id="bbd89-119">Una intranet dell’organizzazione semplificata connessa a Internet e costituita dalle macchine virtuali DC1 APP1 e CLIENT1 in una sottorete di una rete virtuale Azure.</span><span class="sxs-lookup"><span data-stu-id="bbd89-119">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="bbd89-120">Azure AD Connect viene eseguito su APP1 per sincronizzare periodicamente il dominio TESTLAB di Active Directory Domain Services con il tenant di Azure AD dell'abbonamento a Microsoft 365 o a Office 365.</span><span class="sxs-lookup"><span data-stu-id="bbd89-120">Azure AD Connect runs on APP1 to synchronize the TESTLAB Active Directory Domain Services (AD DS) domain to the Azure AD tenant of your Microsoft 365 or Office 365 subscription periodically.</span></span>

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso"></a><span data-ttu-id="bbd89-121">Fase 2: configurare Azure AD Connect su APP1 per Azure AD Seamless Single Sign-On</span><span class="sxs-lookup"><span data-stu-id="bbd89-121">Phase 2: Configure Azure AD Connect on APP1 for Azure AD Seamless SSO</span></span>

<span data-ttu-id="bbd89-122">In questa fase, si configura Azure AD Connect su APP1 per Azure AD Seamless Single Sign-On e se ne verifica il funzionamento.</span><span class="sxs-lookup"><span data-stu-id="bbd89-122">In this phase, you configure Azure AD Connect on APP1 for Azure AD Seamless SSO, and then verify that it works.</span></span>

### <a name="configure-azure-ad-connect-on-app1"></a><span data-ttu-id="bbd89-123">Configurare Azure AD Connect su APP1</span><span class="sxs-lookup"><span data-stu-id="bbd89-123">Configure Azure AD Connect on APP1</span></span>

1. <span data-ttu-id="bbd89-124">Dal [portale di Azure](https://portal.azure.com), accedere con l'account di amministratore globale e connettersi ad APP1 con l'account TESTLAB\User1.</span><span class="sxs-lookup"><span data-stu-id="bbd89-124">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2. <span data-ttu-id="bbd89-125">Dal desktop di APP1, eseguire Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="bbd89-125">From the desktop of APP1, run Azure AD Connect.</span></span>

3. <span data-ttu-id="bbd89-126">Nella **Pagina di benvenuto** fare clic su **Configura**.</span><span class="sxs-lookup"><span data-stu-id="bbd89-126">On the **Welcome page**, click **Configure**.</span></span>

4. <span data-ttu-id="bbd89-127">Nella pagina **Attività aggiuntive** fare clic su **Cambia l'accesso utente**, quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="bbd89-127">On the **Additional tasks** page, click **Change user sign-in**, and then click **Next**.</span></span>

5. <span data-ttu-id="bbd89-128">Nella pagina **Connessione ad Azure AD** digitare le credenziali dell'account amministratore globale e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="bbd89-128">On the **Connect to Azure AD** page, type your global administrator account credentials, and then click **Next**.</span></span>

6. <span data-ttu-id="bbd89-129">Nella pagina **Accesso utente**, selezionare **Abilita Single Sign-On**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="bbd89-129">On the **User sign-in** page, select **Enable single sign-on**, and then click **Next**.</span></span>

7. <span data-ttu-id="bbd89-130">Nella pagina **Abilita Single Sign-On**, fare clic su **Immetti credenziali**.</span><span class="sxs-lookup"><span data-stu-id="bbd89-130">On the **Enable single sign-on** page, click **Enter credentials**.</span></span>

8. <span data-ttu-id="bbd89-p103">Nella finestra di dialogo **Sicurezza di Windows**, digitare **user1** e la password dell'account user1, quindi fare clic su **OK**. Poi, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="bbd89-p103">In the **Windows Security** dialog box, type **user1** and the password of the user1 account, and then click **OK**. Click **Next**.</span></span>

9. <span data-ttu-id="bbd89-133">Nella pagina **Pronto per la configurazione** fare clic su **Configura**.</span><span class="sxs-lookup"><span data-stu-id="bbd89-133">On the **Ready to Configure** page, click **Configure**.</span></span>

10. <span data-ttu-id="bbd89-134">Nella pagina **Configurazione completata**, fare clic su **Esci**.</span><span class="sxs-lookup"><span data-stu-id="bbd89-134">On the **Configuration complete** page, click **Exit**.</span></span>

11. <span data-ttu-id="bbd89-p104">Dal portale di Azure, nel riquadro sinistro fare clic su **Azure Active Directory > Azure AD Connect**. Verificare che la funzionalità **Accesso Single Sign-On facile** venga visualizzata come **Attivata**.</span><span class="sxs-lookup"><span data-stu-id="bbd89-p104">From the Azure portal, in the left pane, click **Azure Active Directory > Azure AD Connect**. Verify that the **Seamless single sign-on** feature appears as **Enabled**.</span></span>

<span data-ttu-id="bbd89-137">Successivamente, verificare la possibilità di accedere all'abbonamento con il nome utente <strong>user1@testlab.</strong>\<dominio pubblico> dell'account User1.</span><span class="sxs-lookup"><span data-stu-id="bbd89-137">Next, test the ability to sign in to your subscription with the <strong>user1@testlab.</strong>\<your public domain> user name of the User1 account.</span></span>

1. <span data-ttu-id="bbd89-138">Da Internet Explorer su AAP1, fare clic sull'icona delle impostazioni, quindi fare clic su **Opzioni Internet**.</span><span class="sxs-lookup"><span data-stu-id="bbd89-138">From Internet Explorer on APP1, click the settings icon, and then click **Internet Options**.</span></span>
 
2. <span data-ttu-id="bbd89-139">In **Opzioni Internet**, fare clic sulla scheda **Sicurezza**.</span><span class="sxs-lookup"><span data-stu-id="bbd89-139">In **Internet Options**, click the **Security** tab.</span></span>

3. <span data-ttu-id="bbd89-140">Fare clic su **Intranet locale**, quindi su **Siti**.</span><span class="sxs-lookup"><span data-stu-id="bbd89-140">Click **Local intranet**, and then click **Sites**.</span></span>

4. <span data-ttu-id="bbd89-141">In **Intranet locale**, fare clic su **Avanzate**.</span><span class="sxs-lookup"><span data-stu-id="bbd89-141">In **Local intranet**, click **Advanced**.</span></span>

5. <span data-ttu-id="bbd89-142">In **Aggiungi questo sito Web alla zona**, digitare **https<span>://</span>autologon.microsoftazuread-sso.com**, quindi fare clic su **Aggiungi > Chiudi > OK > OK**.</span><span class="sxs-lookup"><span data-stu-id="bbd89-142">In **Add this website to the zone**, type **https<span>://</span>autologon.microsoftazuread-sso.com**, click **Add > Close > OK > OK**.</span></span>

6. <span data-ttu-id="bbd89-143">Disconnettersi e quindi accedere nuovamente specificando un account diverso.</span><span class="sxs-lookup"><span data-stu-id="bbd89-143">Sign out, and then sign in again, this time specifying a different account.</span></span>

7. <span data-ttu-id="bbd89-144">Quando viene richiesto di accedere, specificare il nome <strong>user1@testlab.</strong>\<dominio pubblico>, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="bbd89-144">When prompted to sign in, specify <strong>user1@testlab.</strong>\<your public domain> name, and then click **Next**.</span></span> <span data-ttu-id="bbd89-145">È quindi possibile accedere come User1 senza che venga richiesta una password.</span><span class="sxs-lookup"><span data-stu-id="bbd89-145">You should successfully sign in as User1 without being prompted for a password.</span></span> <span data-ttu-id="bbd89-146">Ciò dimostra che Seamless SSO funziona correttamente.</span><span class="sxs-lookup"><span data-stu-id="bbd89-146">This proves that Azure AD Seamless SSO is working.</span></span>

<span data-ttu-id="bbd89-147">Si noti che sebbene User1 disponga di autorizzazioni di amministratore di dominio per il dominio TESTLAB di Active Directory Domain Services, non è un amministratore globale per Azure AD.</span><span class="sxs-lookup"><span data-stu-id="bbd89-147">Notice that although User1 has domain administrator permissions for the TESTLAB AD DS domain, it is not a global administrator for Azure AD.</span></span> <span data-ttu-id="bbd89-148">Di conseguenza, l'icona **Amministratore** non sarà visibile.</span><span class="sxs-lookup"><span data-stu-id="bbd89-148">Therefore, you will not see the **Admin** icon as an option.</span></span>

<span data-ttu-id="bbd89-149">Di seguito è riportata la configurazione risultante:</span><span class="sxs-lookup"><span data-stu-id="bbd89-149">Here is your resulting configuration:</span></span>

![L'organizzazione simulata con ambiente di testing per l'autenticazione pass-through](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

 
<span data-ttu-id="bbd89-151">Questa configurazione è costituita da:</span><span class="sxs-lookup"><span data-stu-id="bbd89-151">This configuration consists of:</span></span>

- <span data-ttu-id="bbd89-152">Abbonamenti di valutazione o a pagamento a Microsoft 365 E5 o a Office 365 E5 con il dominio DNS testlab.\<nome dominio> registrato.</span><span class="sxs-lookup"><span data-stu-id="bbd89-152">Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions with the DNS domain testlab.\<your domain name> registered.</span></span>
- <span data-ttu-id="bbd89-153">Una intranet dell’organizzazione semplificata connessa a Internet e costituita dalle macchine virtuali DC1 APP1 e CLIENT1 in una sottorete di una rete virtuale Azure.</span><span class="sxs-lookup"><span data-stu-id="bbd89-153">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="bbd89-154">Azure AD Connect viene eseguito su APP1 per sincronizzare l'elenco di account e gruppi dal tenant di Azure AD dell'abbonamento a Microsoft 365 o a Office 365 al dominio TESTLAB di Active Directory Domain Services.</span><span class="sxs-lookup"><span data-stu-id="bbd89-154">Azure AD Connect runs on APP1 to synchronize the list of accounts and groups from the Azure AD tenant of your Microsoft 365 or Office 365 subscription to the TESTLAB AD DS domain.</span></span> 
- <span data-ttu-id="bbd89-155">Azure AD Seamless SSO viene abilitato in modo che i computer sulla rete Intranet simulata possano accedere alle risorse cloud di Microsoft 365 senza specificare una password per l'account utente.</span><span class="sxs-lookup"><span data-stu-id="bbd89-155">Azure AD Seamless SSO is enabled so that computers on the simulated intranet can sign in to Microsoft 365 cloud resources without specifing a user account password.</span></span>

<span data-ttu-id="bbd89-156">Vedere il passaggio [Semplificare l'accesso utente](identity-secure-your-passwords.md#identity-sso) nella fase Identità per informazioni e collegamenti per configurare Azure AD Seamless SSO.</span><span class="sxs-lookup"><span data-stu-id="bbd89-156">See the [Simplify user sign-in](identity-secure-your-passwords.md#identity-sso) step in the Identity phase for information and links to configure Azure AD Seamless SSO in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="bbd89-157">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="bbd89-157">Next step</span></span>

<span data-ttu-id="bbd89-158">Esplorare altre caratteristiche e funzionalità [identità](m365-enterprise-test-lab-guides.md#identity) nell'ambiente di test.</span><span class="sxs-lookup"><span data-stu-id="bbd89-158">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="bbd89-159">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bbd89-159">See also</span></span>

[<span data-ttu-id="bbd89-160">Guide al lab di test di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="bbd89-160">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="bbd89-161">Distribuzione di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="bbd89-161">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="bbd89-162">Documentazione di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="bbd89-162">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)


