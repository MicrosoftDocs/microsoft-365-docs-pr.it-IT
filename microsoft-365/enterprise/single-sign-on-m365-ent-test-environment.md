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
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: "Riepilogo: informazioni sulla configurazione e sul test di Azure AD Seamless Single Sign-On per l'ambiente di testing di Microsoft 365."
ms.openlocfilehash: f98f82de50feb2a9f92d1ecc4775c5307b314a72
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487607"
---
# <a name="azure-ad-seamless-single-sign-on-for-your-microsoft-365-test-environment"></a><span data-ttu-id="7af23-103">Azure AD Seamless Single Sign-On per l'ambiente di testing di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7af23-103">Azure AD Seamless Single Sign-on for your Microsoft 365 test environment</span></span>

<span data-ttu-id="7af23-104">*Questa guida del laboratorio di testing può essere utilizzata per ambienti di testing Microsoft 365 per Enterprise e Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="7af23-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="7af23-p101">Azure AD seamless Single Sign-On (SSO senza soluzione di continuità) consente di firmare automaticamente gli utenti quando sono presenti nei propri PC o dispositivi connessi alla propria rete organizzativa. Azure AD seamless SSO fornisce agli utenti un facile accesso alle applicazioni basate su cloud senza bisogno di ulteriori componenti locali.</span><span class="sxs-lookup"><span data-stu-id="7af23-p101">Azure AD Seamless Single Sign-On (Seamless SSO) automatically signs in users when they are on their PCs or devices that are connected to their organization network. Azure AD Seamless SSO provides users with easy access to cloud-based applications without needing any additional on-premises components.</span></span>

<span data-ttu-id="7af23-107">In questo articolo viene descritto come configurare l'ambiente di testing di Microsoft 365 per Azure AD seamless SSO.</span><span class="sxs-lookup"><span data-stu-id="7af23-107">This article describes how to configure your Microsoft 365 test environment for Azure AD Seamless SSO.</span></span>

<span data-ttu-id="7af23-108">La configurazione di Azure AD seamless SSO comporta due fasi:</span><span class="sxs-lookup"><span data-stu-id="7af23-108">Setting up Azure AD Seamless SSO involves two phases:</span></span>
- [<span data-ttu-id="7af23-109">Fase 1: configurare la sincronizzazione hash delle password per l'ambiente di testing di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7af23-109">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [<span data-ttu-id="7af23-110">Fase 2: configurare Azure AD Connect su APP1 per Azure AD Seamless Single Sign-On</span><span class="sxs-lookup"><span data-stu-id="7af23-110">Phase 2: Configure Azure AD Connect on APP1 for Azure AD Seamless SSO</span></span>](#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso)
   
![Guide del laboratorio di testing per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="7af23-112">Per una mappa visiva su tutti gli articoli della guida del laboratorio di testing di Microsoft 365 for Enterprise, accedere a [microsoft 365 per la guida dello stack del laboratorio di testing dell'organizzazione](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="7af23-112">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="7af23-113">Fase 1: configurare la sincronizzazione hash delle password per l'ambiente di testing di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7af23-113">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="7af23-114">Seguire le istruzioni riportate in [sincronizzazione hash delle password per Microsoft 365](password-hash-sync-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="7af23-114">Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md).</span></span> 

<span data-ttu-id="7af23-115">La configurazione risultante è simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="7af23-115">Your resulting configuration looks like this:</span></span>
  
![L'organizzazione simulata con ambiente di testing per la sincronizzazione hash delle password](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="7af23-117">Questa configurazione è costituita da:</span><span class="sxs-lookup"><span data-stu-id="7af23-117">This configuration consists of:</span></span>
  
- <span data-ttu-id="7af23-118">Un abbonamento di valutazione o a pagamento a Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="7af23-118">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="7af23-119">Una Intranet dell'organizzazione semplificata connessa a Internet, costituita dalle macchine virtuali DC1, APP1 e CLIENT1 in una subnet di una rete virtuale di Azure.</span><span class="sxs-lookup"><span data-stu-id="7af23-119">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>
- <span data-ttu-id="7af23-120">Azure AD Connect viene eseguito su APP1 per sincronizzare periodicamente il dominio servizi di dominio Active Directory di TESTLAB con il tenant di Azure AD della sottoscrizione Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7af23-120">Azure AD Connect runs on APP1 to periodically synchronize the TESTLAB Active Directory Domain Services (AD DS) domain to the Azure AD tenant of your Microsoft 365 subscription.</span></span>

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso"></a><span data-ttu-id="7af23-121">Fase 2: configurare Azure AD Connect su APP1 per Azure AD Seamless Single Sign-On</span><span class="sxs-lookup"><span data-stu-id="7af23-121">Phase 2: Configure Azure AD Connect on APP1 for Azure AD Seamless SSO</span></span>

<span data-ttu-id="7af23-122">In questa fase, configurare Azure AD Connect su APP1 per Azure AD seamless SSO e quindi verificarne il funzionamento.</span><span class="sxs-lookup"><span data-stu-id="7af23-122">In this phase, configure Azure AD Connect on APP1 for Azure AD Seamless SSO, and then verify that it works.</span></span>

### <a name="configure-azure-ad-connect-on-app1"></a><span data-ttu-id="7af23-123">Configurare Azure AD Connect su APP1</span><span class="sxs-lookup"><span data-stu-id="7af23-123">Configure Azure AD Connect on APP1</span></span>

1. <span data-ttu-id="7af23-124">Dal [portale di Azure](https://portal.azure.com), accedere con l'account di amministratore globale e connettersi ad APP1 con l'account TESTLAB\User1.</span><span class="sxs-lookup"><span data-stu-id="7af23-124">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2. <span data-ttu-id="7af23-125">Dal desktop di APP1, eseguire Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="7af23-125">From the APP1 desktop, run Azure AD Connect.</span></span>

3. <span data-ttu-id="7af23-126">Nella **pagina iniziale**, selezionare **Configura**.</span><span class="sxs-lookup"><span data-stu-id="7af23-126">On the **Welcome page**, select **Configure**.</span></span>

4. <span data-ttu-id="7af23-127">Nella pagina **attività aggiuntive** selezionare **Cambia accesso utente**e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="7af23-127">On the **Additional tasks** page, select **Change user sign-in**, and then select **Next**.</span></span>

5. <span data-ttu-id="7af23-128">Nella pagina **connessione ad Azure ad** , immettere le credenziali dell'account amministratore globale e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="7af23-128">On the **Connect to Azure AD** page, enter your global administrator account credentials, and then select **Next**.</span></span>

6. <span data-ttu-id="7af23-129">Nella pagina **di accesso dell'utente** , selezionare **Abilita Single Sign-on**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="7af23-129">On the **User sign-in** page, select **Enable single sign-on**, and then select **Next**.</span></span>

7. <span data-ttu-id="7af23-130">Nella pagina **Abilita Single Sign-on** selezionare **Enter credentials**.</span><span class="sxs-lookup"><span data-stu-id="7af23-130">On the **Enable single sign-on** page, select **Enter credentials**.</span></span>

8. <span data-ttu-id="7af23-131">Nella finestra di dialogo **sicurezza di Windows** , immettere **User1** e la password dell'account User1, selezionare **OK**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="7af23-131">In the **Windows Security** dialog box, enter **user1** and the password of the user1 account, select **OK**, and then select **Next**.</span></span>

9. <span data-ttu-id="7af23-132">Nella pagina **pronto per la configurazione** , selezionare **Configure**.</span><span class="sxs-lookup"><span data-stu-id="7af23-132">On the **Ready to Configure** page, select **Configure**.</span></span>

10. <span data-ttu-id="7af23-133">Nella pagina **Configurazione completata** selezionare **Esci**.</span><span class="sxs-lookup"><span data-stu-id="7af23-133">On the **Configuration complete** page, select **Exit**.</span></span>

11. <span data-ttu-id="7af23-134">Dal portale di Azure, nel riquadro sinistro, selezionare **Azure Active Directory**  >  **Azure ad Connect**.</span><span class="sxs-lookup"><span data-stu-id="7af23-134">From the Azure portal, in the left pane, select **Azure Active Directory** > **Azure AD Connect**.</span></span> <span data-ttu-id="7af23-135">Verificare che la funzionalità **Single Sign-on** venga visualizzata come **abilitata**.</span><span class="sxs-lookup"><span data-stu-id="7af23-135">Verify that the **Seamless single sign-on** feature appears as **Enabled**.</span></span>

<span data-ttu-id="7af23-136">Successivamente, verificare la possibilità di accedere all'abbonamento con il <strong>User1@testlab.</strong>\<*your public domain*></span><span class="sxs-lookup"><span data-stu-id="7af23-136">Next, test the ability to sign in to your subscription with the <strong>user1@testlab.</strong>\<*your public domain*></span></span> <span data-ttu-id="7af23-137">per l’account User1.</span><span class="sxs-lookup"><span data-stu-id="7af23-137">user name of the User1 account.</span></span>

1. <span data-ttu-id="7af23-138">Da Internet Explorer su APP1, selezionare l'icona Impostazioni, quindi selezionare **Opzioni Internet**.</span><span class="sxs-lookup"><span data-stu-id="7af23-138">From Internet Explorer on APP1, select the settings icon, and then select **Internet Options**.</span></span>
 
2. <span data-ttu-id="7af23-139">In **Opzioni Internet**selezionare la scheda **sicurezza** .</span><span class="sxs-lookup"><span data-stu-id="7af23-139">In **Internet Options**, select the **Security** tab.</span></span>

3. <span data-ttu-id="7af23-140">Selezionare **Intranet locale**e quindi selezionare **siti**.</span><span class="sxs-lookup"><span data-stu-id="7af23-140">Select **Local intranet**, and then select **Sites**.</span></span>

4. <span data-ttu-id="7af23-141">In **Intranet locale**, selezionare **Avanzate**.</span><span class="sxs-lookup"><span data-stu-id="7af23-141">In **Local intranet**, select **Advanced**.</span></span>

5. <span data-ttu-id="7af23-142">In **Aggiungi questo sito Web all'area**, immettere **https<span>://</span>AutoLogon.microsoftazuread-SSO.com**, selezionare **Aggiungi**  >  **Chiudi**  >  **OK**  >  **OK**.</span><span class="sxs-lookup"><span data-stu-id="7af23-142">In **Add this website to the zone**, enter **https<span>://</span>autologon.microsoftazuread-sso.com**, select **Add** > **Close** > **OK** > **OK**.</span></span>

6. <span data-ttu-id="7af23-143">Disconnettersi e quindi accedere nuovamente specificando un account diverso.</span><span class="sxs-lookup"><span data-stu-id="7af23-143">Sign out, and then sign in again, this time specifying a different account.</span></span>

7. <span data-ttu-id="7af23-144">Quando viene richiesto di eseguire l'accesso, specificare <strong>User1@testlab.</strong>\<*your public domain*></span><span class="sxs-lookup"><span data-stu-id="7af23-144">When prompted to sign in, specify <strong>user1@testlab.</strong>\<*your public domain*></span></span> <span data-ttu-id="7af23-145">nome e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="7af23-145">name, and then select **Next**.</span></span> <span data-ttu-id="7af23-146">È quindi possibile accedere come User1 senza che venga richiesta una password.</span><span class="sxs-lookup"><span data-stu-id="7af23-146">You should successfully sign in as User1 without being prompted for a password.</span></span> <span data-ttu-id="7af23-147">Ciò dimostra che Seamless SSO funziona correttamente.</span><span class="sxs-lookup"><span data-stu-id="7af23-147">This proves that Azure AD Seamless SSO is working.</span></span>

<span data-ttu-id="7af23-148">Si noti che sebbene User1 disponga di autorizzazioni di amministratore di dominio per il dominio TESTLAB di Active Directory Domain Services, non è un amministratore globale per Azure AD.</span><span class="sxs-lookup"><span data-stu-id="7af23-148">Notice that although User1 has domain administrator permissions for the TESTLAB AD DS domain, it is not a global administrator for Azure AD.</span></span> <span data-ttu-id="7af23-149">Di conseguenza, l'icona **Amministratore** non sarà visibile.</span><span class="sxs-lookup"><span data-stu-id="7af23-149">Therefore, you will not see the **Admin** icon as an option.</span></span>

<span data-ttu-id="7af23-150">Di seguito è riportata la configurazione risultante:</span><span class="sxs-lookup"><span data-stu-id="7af23-150">Here is your resulting configuration:</span></span>

![L'organizzazione simulata con ambiente di testing per l'autenticazione pass-through](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

<span data-ttu-id="7af23-152">Questa configurazione è costituita da:</span><span class="sxs-lookup"><span data-stu-id="7af23-152">This configuration consists of:</span></span>

- <span data-ttu-id="7af23-153">Una versione di valutazione di Microsoft 365 E5 o abbonamenti a pagamento con dominio DNS testlab.\<*your domain name*></span><span class="sxs-lookup"><span data-stu-id="7af23-153">A Microsoft 365 E5 trial or paid subscriptions with the DNS domain testlab.\<*your domain name*></span></span> <span data-ttu-id="7af23-154">registrato.</span><span class="sxs-lookup"><span data-stu-id="7af23-154">registered.</span></span>
- <span data-ttu-id="7af23-155">Una Intranet dell'organizzazione semplificata connessa a Internet, costituita dalle macchine virtuali DC1, APP1 e CLIENT1 in una subnet di una rete virtuale di Azure.</span><span class="sxs-lookup"><span data-stu-id="7af23-155">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>
- <span data-ttu-id="7af23-156">Azure AD Connect viene eseguito su APP1 per sincronizzare l'elenco di account e gruppi dal tenant di Azure AD dell'abbonamento a Microsoft 365 al dominio TESTLAB di Active Directory Domain Services.</span><span class="sxs-lookup"><span data-stu-id="7af23-156">Azure AD Connect runs on APP1 to synchronize the list of accounts and groups from the Azure AD tenant of your Microsoft 365 subscription to the TESTLAB AD DS domain.</span></span>
- <span data-ttu-id="7af23-157">Azure AD seamless SSO è abilitato in modo che i computer della rete Intranet simulata possano accedere alle risorse cloud di Microsoft 365 senza specificare una password per l'account utente.</span><span class="sxs-lookup"><span data-stu-id="7af23-157">Azure AD Seamless SSO is enabled so that computers on the simulated intranet can sign in to Microsoft 365 cloud resources without specifying a user account password.</span></span>

## <a name="next-step"></a><span data-ttu-id="7af23-158">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="7af23-158">Next step</span></span>

<span data-ttu-id="7af23-159">Esplorare altre caratteristiche e funzionalità [identità](m365-enterprise-test-lab-guides.md#identity) nell'ambiente di test.</span><span class="sxs-lookup"><span data-stu-id="7af23-159">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="7af23-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7af23-160">See also</span></span>

[<span data-ttu-id="7af23-161">Guide ai lab di test di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="7af23-161">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="7af23-162">Panoramica di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="7af23-162">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="7af23-163">Microsoft 365 per la documentazione relativa all'organizzazione</span><span class="sxs-lookup"><span data-stu-id="7af23-163">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
