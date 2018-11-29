---
title: Automatizzare l'appartenenza al gruppo e sulle licenze per l'ambiente di test Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- TLG
- Ent_TLGs
description: Configurare basata su gruppo di gestione delle licenze e l'appartenenza al gruppo dinamica nell'ambiente di test Microsoft 365 aziendale.
ms.openlocfilehash: 46d2f0ca063b387d1a4a51b4ea97bd5d60c03fe5
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868667"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="af941-103">Automatizzare l'appartenenza al gruppo e sulle licenze per l'ambiente di test Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="af941-103">Automate licensing and group membership for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="af941-p101">Basata su gruppo di licenze automaticamente assegna o rimuove le licenze per un account utente in base all'appartenenza. L'appartenenza al gruppo dinamico aggiunge o rimuove i membri di un gruppo basato sulla proprietà degli account utente, ad esempio reparto o paese. In questo articolo esaminato una dimostrazione di entrambi nel proprio ambiente di test Microsoft 365 aziendale.</span><span class="sxs-lookup"><span data-stu-id="af941-p101">Group-based licensing automatically assigns or removes licenses for a user account based on group membership. Dynamic group membership adds or removes members to a group based on user account properties, such as Department or Country. This article steps you through a demonstration of both in your Microsoft 365 Enterprise test environment.</span></span>

<span data-ttu-id="af941-107">Esistono due fasi per impostare l'appartenenza al gruppo di licenze automatico e dinamica nell'ambiente di test Microsoft 365 aziendale:</span><span class="sxs-lookup"><span data-stu-id="af941-107">There are two phases to setting up auto-licensing and dynamic group membership in your Microsoft 365 Enterprise test environment:</span></span>

1. <span data-ttu-id="af941-108">Creare l'ambiente di test Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="af941-108">Create the Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="af941-109">Configurare e testare l'appartenenza al gruppo dinamico e la gestione automatica delle licenze.</span><span class="sxs-lookup"><span data-stu-id="af941-109">Configure and test dynamic group membership and automatic licensing.</span></span>

![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="af941-111">Fare clic [qui](https://aka.ms/m365etlgstack) per consultare una mappa di tutti gli articoli relativi alla guida al lab test di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="af941-111">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="af941-112">Fase 1: Preparare l'ambiente di testing Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="af941-112">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="af941-113">Se si desidera testare gestione automatica delle licenze e l'appartenenza al gruppo in un modo semplice con i requisiti minimi, seguire le istruzioni di [configurazione di base semplificata](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="af941-113">If you just want to test automated licensing and group membership in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="af941-114">Se si desidera testare gestione automatica delle licenze e l'appartenenza al gruppo in un'azienda simulata, seguire le istruzioni [nell'autenticazione pass-through](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="af941-114">If you want to test automated licensing and group membership in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="af941-p102">Test automatizzati licenze e l'appartenenza al gruppo non richiede l'ambiente di testing simulato enterprise, che include una rete intranet simulata connessione a Internet e la sincronizzazione delle directory per una foresta Windows Server Active Directory. Viene fornito qui come un'opzione in modo che sia possibile testare gestione automatica delle licenze e l'appartenenza al gruppo e sperimentare in un ambiente che rappresenta una tipica organizzazione.</span><span class="sxs-lookup"><span data-stu-id="af941-p102">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a><span data-ttu-id="af941-117">Fase 2: Configurare e testare l'appartenenza al gruppo dinamico e la gestione automatica delle licenze</span><span class="sxs-lookup"><span data-stu-id="af941-117">Phase 2: Configure and test dynamic group membership and automatic licensing</span></span>

<span data-ttu-id="af941-118">Per prima cosa, si crea un nuovo gruppo di vendite e aggiungere una regola di appartenenza al gruppo dinamico in modo che gli account utente con il reparto impostato su vendite vengono aggiunti automaticamente al gruppo vendite.</span><span class="sxs-lookup"><span data-stu-id="af941-118">First, you create a new Sales group and add a dynamic group membership rule so that user accounts with the Department set to Sales are automatically added to the Sales group.</span></span>

1. <span data-ttu-id="af941-119">Utilizza un'istanza del browser Internet privata, accedere al portale di Office 365 in [https://portal.office.com](https://portal.office.com) con l'account amministratore globale della sottoscrizione di prova di Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="af941-119">Using a private instance of your Internet browser, sign in to the Office 365 portal at [https://portal.office.com](https://portal.office.com) with the global administrator account of your Office 365 E5 trial subscription.</span></span>
2. <span data-ttu-id="af941-120">In una scheda separata del browser, accedere al portale di Azure in [https://portal.azure.com](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="af941-120">On a separate tab of your browser, go to the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>
3. <span data-ttu-id="af941-121">Nel portale di Azure fare clic su **Azure Active Directory > Utenti e gruppi > Tutti i gruppi**.</span><span class="sxs-lookup"><span data-stu-id="af941-121">In the Azure portal, click **Azure Active Directory > Users and groups > All groups**.</span></span>
4. <span data-ttu-id="af941-122">Su blade **tutti i gruppi** , fare clic su **nuovo gruppo**.</span><span class="sxs-lookup"><span data-stu-id="af941-122">On the **All groups** blade, click **New group**.</span></span>
5. <span data-ttu-id="af941-123">In **tipo di gruppo**, selezionare **Office 365**.</span><span class="sxs-lookup"><span data-stu-id="af941-123">In **Group type**, select **Office 365**.</span></span>
6. <span data-ttu-id="af941-124">In **nome gruppo**digitare **vendite**.</span><span class="sxs-lookup"><span data-stu-id="af941-124">In **Group name**, type **Sales**.</span></span>
7. <span data-ttu-id="af941-125">In **tipo di appartenenza**, selezionare **utente dinamica** .</span><span class="sxs-lookup"><span data-stu-id="af941-125">In **Membership type**, select **Dynamic user** .</span></span>
8. <span data-ttu-id="af941-126">Fare clic su **Aggiungere query dinamica**.</span><span class="sxs-lookup"><span data-stu-id="af941-126">Click **Add dynamic query**.</span></span>
9. <span data-ttu-id="af941-127">Selezionare **Reparto** in **Dove aggiungere utenti**</span><span class="sxs-lookup"><span data-stu-id="af941-127">In **Add users where**, select **department**.</span></span>
10. <span data-ttu-id="af941-128">Nel campo successivo, selezionare **Uguale a**.</span><span class="sxs-lookup"><span data-stu-id="af941-128">In the next field, select **Equals**.</span></span>
11. <span data-ttu-id="af941-129">Nel campo successivo digitare **vendite**.</span><span class="sxs-lookup"><span data-stu-id="af941-129">In the next field, type **Sales**.</span></span>
12. <span data-ttu-id="af941-130">Fare clic su **Aggiungi query** e quindi su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="af941-130">Click **Add query**, and then click **Create**.</span></span>
13. <span data-ttu-id="af941-131">Chiudere server blade **gruppo** e i **gruppi di tutti i gruppi** .</span><span class="sxs-lookup"><span data-stu-id="af941-131">Close the **Group** and **Groups-All groups** blades.</span></span>

<span data-ttu-id="af941-132">Punto, configurare il gruppo di vendita in modo che i membri vengono assegnati automaticamente Office 365 E5 e mobilità aziendale + sicurezza E5 licenze.</span><span class="sxs-lookup"><span data-stu-id="af941-132">Next, you configure the Sales group so that members are automatically assigned Office 365 E5 and Enterprise Mobility + Security E5 licenses.</span></span>

1. <span data-ttu-id="af941-133">Su blade **Panoramica** per Azure Active Directory, fare clic su **licenze > tutti i prodotti**.</span><span class="sxs-lookup"><span data-stu-id="af941-133">On the **Overview** blade for Azure Active Directory, click **Licenses > All products**.</span></span>
2. <span data-ttu-id="af941-134">Nell'elenco, selezionare **Enterprise Mobility + Security E5** e **Office 365 Enterprise E5**, quindi fare clic su **Assegna**.</span><span class="sxs-lookup"><span data-stu-id="af941-134">In the list, select **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5**, and then click **Assign**.</span></span>
3. <span data-ttu-id="af941-135">Su blade **assegnare licenze** , fare clic su **utenti e gruppi**.</span><span class="sxs-lookup"><span data-stu-id="af941-135">On the **Assign license** blade, click **Users and groups**.</span></span>
4. <span data-ttu-id="af941-136">Nell'elenco dei gruppi, selezionare il gruppo di **Sales** .</span><span class="sxs-lookup"><span data-stu-id="af941-136">In the list of groups, select the **Sales** group.</span></span>
5. <span data-ttu-id="af941-137">Fare clic su **Seleziona**, quindi su **Assegna**.</span><span class="sxs-lookup"><span data-stu-id="af941-137">Click **Select**, and then click **Assign**.</span></span>
6. <span data-ttu-id="af941-138">Chiudere la scheda del portale di Azure nel browser.</span><span class="sxs-lookup"><span data-stu-id="af941-138">Close the Azure portal tab in your browser.</span></span>

<span data-ttu-id="af941-139">Successivamente, testare l'appartenenza al gruppo dinamico e licenze automatica dell'account utente 4.</span><span class="sxs-lookup"><span data-stu-id="af941-139">Next, you test dynamic group membership and automatic licensing on the User 4 account.</span></span> 

1. <span data-ttu-id="af941-140">Nella scheda **Home page di Microsoft Office** nel browser, fare clic su **amministratore**.</span><span class="sxs-lookup"><span data-stu-id="af941-140">From the **Microsoft Office Home** tab in your browser, click **Admin**.</span></span>
2. <span data-ttu-id="af941-141">Dalla scheda di **interfaccia di amministrazione di Office** , fare clic su **utenti attivi**.</span><span class="sxs-lookup"><span data-stu-id="af941-141">From the **Office Admin center** tab, click **Active users**.</span></span>
3. <span data-ttu-id="af941-142">Nella pagina **utenti** fare clic sull'account **utente 4** .</span><span class="sxs-lookup"><span data-stu-id="af941-142">On the **Active users** page, click the **User 4** account.</span></span>
4. <span data-ttu-id="af941-143">Nel riquadro di **utente 4** , fare clic su **Modifica** per **le licenze del prodotto**.</span><span class="sxs-lookup"><span data-stu-id="af941-143">On the **User 4** pane, click **Edit** for **Product licenses**.</span></span>
5. <span data-ttu-id="af941-144">Nel riquadro di **licenze per i prodotti** , attivare la **mobilità aziendale + E5 di sicurezza** e le licenze di **Office 365 Enterprise E5** disattivato e quindi fare clic su **salvare > Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="af941-144">On the **Product licenses** pane, turn the **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5** licenses off, and then click **Save > Close**.</span></span>
6. <span data-ttu-id="af941-145">Nelle proprietà dell'account utente 4, verificare che non è stati assegnati alcun licenze per i prodotti e non sono disponibili appartenenze ai gruppi.</span><span class="sxs-lookup"><span data-stu-id="af941-145">In the properties of the User 4 account, verify that no product licenses have been assigned and there are no group memberships.</span></span>
7. <span data-ttu-id="af941-146">Per **informazioni di contatto**, scegliere **Modifica** .</span><span class="sxs-lookup"><span data-stu-id="af941-146">Click **Edit** for **Contact information**.</span></span>
8. <span data-ttu-id="af941-147">Nel riquadro **informazioni contatto modificare** , fare clic su **informazioni di contatto**.</span><span class="sxs-lookup"><span data-stu-id="af941-147">In the **Edit Contact information** pane, click **Contact information**.</span></span>
9. <span data-ttu-id="af941-148">Nel campo **reparto** digitare **Sales**e quindi fare clic su **salvare > Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="af941-148">In the **Department** field, type **Sales**, and then click **Save > Close**.</span></span>
10. <span data-ttu-id="af941-149">Attendere qualche minuto e quindi periodicamente l'icona Aggiorna in alto a destra del riquadro di account utente 4.</span><span class="sxs-lookup"><span data-stu-id="af941-149">Wait a few minutes, and then periodically click the refresh icon in the upper-right of the User 4 account pane.</span></span> 

<span data-ttu-id="af941-150">Nel tempo dovrebbe essere visualizzato il:</span><span class="sxs-lookup"><span data-stu-id="af941-150">In time you should see the:</span></span>

- <span data-ttu-id="af941-151">**Appartenenze a gruppi** della proprietà con il gruppo di **Sales** .</span><span class="sxs-lookup"><span data-stu-id="af941-151">**Group memberships** property updated with the **Sales** group.</span></span>
- <span data-ttu-id="af941-152">**Licenze per i prodotti** della proprietà con le licenze **Enterprise mobilità + sicurezza E5** e **Office 365 Enterprise E5** .</span><span class="sxs-lookup"><span data-stu-id="af941-152">**Product licenses** property updated with the **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5** licenses.</span></span>

<span data-ttu-id="af941-153">Nella fase di identità per informazioni e collegamenti per distribuire l'appartenenza al gruppo dinamico e la gestione automatica delle licenze nell'ambiente di produzione, vedere la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="af941-153">See these steps in the Identity phase for information and links to deploy dynamic group membership and automatic licensing in production:</span></span>

- [<span data-ttu-id="af941-154">Configurare l'assegnazione automatica delle licenze</span><span class="sxs-lookup"><span data-stu-id="af941-154">Set up automatic licensing</span></span>](identity-group-based-licensing.md)
- [<span data-ttu-id="af941-155">Configurare l'appartenenza a gruppi dinamici</span><span class="sxs-lookup"><span data-stu-id="af941-155">Set up dynamic group membership</span></span>](identity-automatic-group-membership.md)

## <a name="next-step"></a><span data-ttu-id="af941-156">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="af941-156">Next step</span></span>

<span data-ttu-id="af941-157">Esplorare altre caratteristiche e funzionalità [identità](m365-enterprise-test-lab-guides.md#identity) nell'ambiente di test.</span><span class="sxs-lookup"><span data-stu-id="af941-157">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="af941-158">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="af941-158">See also</span></span>

[<span data-ttu-id="af941-159">Fase 2: identità</span><span class="sxs-lookup"><span data-stu-id="af941-159">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="af941-160">Guide al lab di test di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="af941-160">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="af941-161">Distribuzione di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="af941-161">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="af941-162">Documentazione di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="af941-162">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
