---
title: Automatizzare la gestione delle licenze e dell'appartenenza ai gruppi per l'ambiente di testing Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Configurare la gestione delle licenze basate su gruppo e l'appartenenza a gruppi dinamici nell'ambiente di testing Microsoft 365 Enterprise.
ms.openlocfilehash: c3b515a9b453275f9b79ba2b90d5a4c14611c2aa
ms.sourcegitcommit: 2c2248b03f7753d64490f2f7e56ec644a235b65a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/15/2019
ms.locfileid: "38639796"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="c2ab8-103">Automatizzare la gestione delle licenze e dell'appartenenza ai gruppi per l'ambiente di testing Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="c2ab8-103">Automate licensing and group membership for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="c2ab8-104">La gestione delle licenze basate su gruppo assegna o rimuove automaticamente le licenze per un account utente basato sull'appartenenza a un gruppo.</span><span class="sxs-lookup"><span data-stu-id="c2ab8-104">Group-based licensing automatically assigns or removes licenses for a user account based on group membership.</span></span> <span data-ttu-id="c2ab8-105">L'appartenenza a un gruppo dinamico aggiunge o rimuove membri a un gruppo in base alle proprietà degli account utente, ad esempio reparto o paese.</span><span class="sxs-lookup"><span data-stu-id="c2ab8-105">Dynamic group membership adds or removes members to a group based on user account properties, such as Department or Country.</span></span> <span data-ttu-id="c2ab8-106">In questo articolo viene illustrata una dimostrazione di entrambi nell'ambiente di testing di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="c2ab8-106">This article steps you through a demonstration of both in your Microsoft 365 Enterprise test environment.</span></span>

<span data-ttu-id="c2ab8-107">Sono disponibili due fasi per la configurazione della licenza automatica e l'appartenenza a gruppi dinamici nell'ambiente di testing di Microsoft 365 Enterprise:</span><span class="sxs-lookup"><span data-stu-id="c2ab8-107">There are two phases to setting up auto-licensing and dynamic group membership in your Microsoft 365 Enterprise test environment:</span></span>

1. <span data-ttu-id="c2ab8-108">Creare l'ambiente di testing di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="c2ab8-108">Create the Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="c2ab8-109">Configurare e testare l'appartenenza a gruppi dinamici e la gestione automatica delle licenze.</span><span class="sxs-lookup"><span data-stu-id="c2ab8-109">Configure and test dynamic group membership and automatic licensing.</span></span>

![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="c2ab8-111">Fare clic [qui](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) per consultare una mappa di tutti gli articoli relativi alla guida al lab test di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="c2ab8-111">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="c2ab8-112">Fase 1: Creare l'ambiente di testing di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="c2ab8-112">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="c2ab8-113">Se si desidera solo testare la licenza automatizzata e l'appartenenza ai gruppi con i requisiti minimi, seguire le istruzioni contenute in [Lightweight base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="c2ab8-113">If you just want to test automated licensing and group membership in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="c2ab8-114">Se si desidera testare la licenza automatizzata e l'appartenenza a un gruppo in un'azienda simulata, seguire le istruzioni riportate nell' [autenticazione pass-through](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="c2ab8-114">If you want to test automated licensing and group membership in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="c2ab8-115">La verifica delle licenze automatizzate e dell'appartenenza ai gruppi non richiede l'ambiente di testing dell'organizzazione simulata, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per una foresta di servizi di dominio Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="c2ab8-115">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="c2ab8-116">Viene fornito come opzione in modo che sia possibile testare la licenza automatizzata e l'appartenenza ai gruppi e sperimentarla in un ambiente che rappresenta un'organizzazione tipica.</span><span class="sxs-lookup"><span data-stu-id="c2ab8-116">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a><span data-ttu-id="c2ab8-117">Fase 2: configurare e testare l'appartenenza a gruppi dinamici e la gestione automatica delle licenze</span><span class="sxs-lookup"><span data-stu-id="c2ab8-117">Phase 2: Configure and test dynamic group membership and automatic licensing</span></span>

<span data-ttu-id="c2ab8-118">Per prima cosa, è necessario creare un nuovo gruppo di vendita e aggiungere una regola di appartenenza a un gruppo dinamico in modo che gli account utente con il reparto impostato su Sales vengano automaticamente aggiunti al gruppo Sales.</span><span class="sxs-lookup"><span data-stu-id="c2ab8-118">First, you create a new Sales group and add a dynamic group membership rule so that user accounts with the Department set to Sales are automatically added to the Sales group.</span></span>

1. <span data-ttu-id="c2ab8-119">Se si utilizza un'istanza privata del browser Internet, accedere al portale di Office 365 [https://portal.office.com](https://portal.office.com) con l'account di amministratore globale dell'abbonamento al laboratorio di testing di Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="c2ab8-119">Using a private instance of your Internet browser, sign in to the Office 365 portal at [https://portal.office.com](https://portal.office.com) with the global administrator account of your Office 365 E5 test lab subscription.</span></span>
2. <span data-ttu-id="c2ab8-120">In una scheda separata del browser, accedere al portale di Azure all'indirizzo [https://portal.azure.com](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="c2ab8-120">On a separate tab of your browser, go to the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>
3. <span data-ttu-id="c2ab8-121">Nel portale di Azure fare clic su **Azure Active Directory > Utenti e gruppi > Tutti i gruppi**.</span><span class="sxs-lookup"><span data-stu-id="c2ab8-121">In the Azure portal, click **Azure Active Directory > Users and groups > All groups**.</span></span>
4. <span data-ttu-id="c2ab8-122">Nel pannello **tutti i gruppi** fare clic su **nuovo gruppo**.</span><span class="sxs-lookup"><span data-stu-id="c2ab8-122">On the **All groups** blade, click **New group**.</span></span>
5. <span data-ttu-id="c2ab8-123">In **tipo di gruppo**, selezionare **Office 365**.</span><span class="sxs-lookup"><span data-stu-id="c2ab8-123">In **Group type**, select **Office 365**.</span></span>
6. <span data-ttu-id="c2ab8-124">In **nome gruppo**digitare **Sales**.</span><span class="sxs-lookup"><span data-stu-id="c2ab8-124">In **Group name**, type **Sales**.</span></span>
7. <span data-ttu-id="c2ab8-125">In **tipo di appartenenza**, selezionare **utente dinamico** .</span><span class="sxs-lookup"><span data-stu-id="c2ab8-125">In **Membership type**, select **Dynamic user** .</span></span>
8. <span data-ttu-id="c2ab8-126">Fare clic su **Aggiungere query dinamica**.</span><span class="sxs-lookup"><span data-stu-id="c2ab8-126">Click **Add dynamic query**.</span></span>
9. <span data-ttu-id="c2ab8-127">Selezionare **Reparto** in **Dove aggiungere utenti**</span><span class="sxs-lookup"><span data-stu-id="c2ab8-127">In **Add users where**, select **department**.</span></span>
10. <span data-ttu-id="c2ab8-128">Nel campo successivo, selezionare **Uguale a**.</span><span class="sxs-lookup"><span data-stu-id="c2ab8-128">In the next field, select **Equals**.</span></span>
11. <span data-ttu-id="c2ab8-129">Nel campo successivo digitare **Sales**.</span><span class="sxs-lookup"><span data-stu-id="c2ab8-129">In the next field, type **Sales**.</span></span>
12. <span data-ttu-id="c2ab8-130">Fare clic su **Aggiungi query** e quindi su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="c2ab8-130">Click **Add query**, and then click **Create**.</span></span>
13. <span data-ttu-id="c2ab8-131">Chiudere le lame **gruppo** e **gruppi-tutti i gruppi** .</span><span class="sxs-lookup"><span data-stu-id="c2ab8-131">Close the **Group** and **Groups-All groups** blades.</span></span>

<span data-ttu-id="c2ab8-132">Successivamente, è possibile configurare il gruppo vendite in modo che ai membri vengano assegnate automaticamente le licenze di Office 365 E5 ed Enterprise Mobility + Security E5.</span><span class="sxs-lookup"><span data-stu-id="c2ab8-132">Next, you configure the Sales group so that members are automatically assigned Office 365 E5 and Enterprise Mobility + Security E5 licenses.</span></span>

1. <span data-ttu-id="c2ab8-133">Nel pannello **Panoramica** di Azure Active Directory, fare clic su **licenze > tutti i prodotti**.</span><span class="sxs-lookup"><span data-stu-id="c2ab8-133">On the **Overview** blade for Azure Active Directory, click **Licenses > All products**.</span></span>
2. <span data-ttu-id="c2ab8-134">Nell'elenco, selezionare **Enterprise Mobility + Security E5** e **Office 365 Enterprise E5**, quindi fare clic su **Assegna**.</span><span class="sxs-lookup"><span data-stu-id="c2ab8-134">In the list, select **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5**, and then click **Assign**.</span></span>
3. <span data-ttu-id="c2ab8-135">Sul blade di **assegnazione della licenza** , fare clic su **utenti e gruppi**.</span><span class="sxs-lookup"><span data-stu-id="c2ab8-135">On the **Assign license** blade, click **Users and groups**.</span></span>
4. <span data-ttu-id="c2ab8-136">Nell'elenco dei gruppi, selezionare il gruppo **vendite** .</span><span class="sxs-lookup"><span data-stu-id="c2ab8-136">In the list of groups, select the **Sales** group.</span></span>
5. <span data-ttu-id="c2ab8-137">Fare clic su **Seleziona**, quindi su **Assegna**.</span><span class="sxs-lookup"><span data-stu-id="c2ab8-137">Click **Select**, and then click **Assign**.</span></span>
6. <span data-ttu-id="c2ab8-138">Chiudere la scheda del portale di Azure nel browser.</span><span class="sxs-lookup"><span data-stu-id="c2ab8-138">Close the Azure portal tab in your browser.</span></span>

<span data-ttu-id="c2ab8-139">Successivamente, è possibile testare l'appartenenza a gruppi dinamici e la gestione delle licenze automatiche nell'account User 4.</span><span class="sxs-lookup"><span data-stu-id="c2ab8-139">Next, you test dynamic group membership and automatic licensing on the User 4 account.</span></span> 

1. <span data-ttu-id="c2ab8-140">Nella scheda **Microsoft Office Home** del browser, fare clic su **amministratore**.</span><span class="sxs-lookup"><span data-stu-id="c2ab8-140">From the **Microsoft Office Home** tab in your browser, click **Admin**.</span></span>
2. <span data-ttu-id="c2ab8-141">Nella scheda dell'interfaccia di **amministrazione di Microsoft 365** fare clic su **utenti attivi**.</span><span class="sxs-lookup"><span data-stu-id="c2ab8-141">From the **Microsoft 365 admin center** tab, click **Active users**.</span></span>
3. <span data-ttu-id="c2ab8-142">Nella pagina **utenti attivi** , fare clic sull'account **User 4** .</span><span class="sxs-lookup"><span data-stu-id="c2ab8-142">On the **Active users** page, click the **User 4** account.</span></span>
4. <span data-ttu-id="c2ab8-143">Nel riquadro **User 4** , fare clic su **modifica** per **licenze di prodotto**.</span><span class="sxs-lookup"><span data-stu-id="c2ab8-143">On the **User 4** pane, click **Edit** for **Product licenses**.</span></span>
5. <span data-ttu-id="c2ab8-144">Nel riquadro **licenze di prodotto** , disattivare le **licenze Enterprise Mobility + Security e5** e **Office 365 Enterprise E5** , quindi fare clic su **Salva > Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="c2ab8-144">On the **Product licenses** pane, turn the **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5** licenses off, and then click **Save > Close**.</span></span>
6. <span data-ttu-id="c2ab8-145">Nelle proprietà dell'account User 4, verificare che non siano state assegnate licenze di prodotto e che non vi siano appartenenze a gruppi.</span><span class="sxs-lookup"><span data-stu-id="c2ab8-145">In the properties of the User 4 account, verify that no product licenses have been assigned and there are no group memberships.</span></span>
7. <span data-ttu-id="c2ab8-146">Fare clic su **modifica** per **informazioni di contatto**.</span><span class="sxs-lookup"><span data-stu-id="c2ab8-146">Click **Edit** for **Contact information**.</span></span>
8. <span data-ttu-id="c2ab8-147">Nel riquadro **modifica informazioni contatto** fare clic su **informazioni di contatto**.</span><span class="sxs-lookup"><span data-stu-id="c2ab8-147">In the **Edit Contact information** pane, click **Contact information**.</span></span>
9. <span data-ttu-id="c2ab8-148">Nel campo **reparto** digitare **Sales**e quindi fare clic su **Salva > Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="c2ab8-148">In the **Department** field, type **Sales**, and then click **Save > Close**.</span></span>
10. <span data-ttu-id="c2ab8-149">Attendere alcuni minuti, quindi fare periodicamente clic sull'icona Aggiorna nell'angolo in alto a destra del riquadro account User 4.</span><span class="sxs-lookup"><span data-stu-id="c2ab8-149">Wait a few minutes, and then periodically click the refresh icon in the upper-right of the User 4 account pane.</span></span> 

<span data-ttu-id="c2ab8-150">Nel tempo dovrebbe essere visualizzato il seguente:</span><span class="sxs-lookup"><span data-stu-id="c2ab8-150">In time you should see the:</span></span>

- <span data-ttu-id="c2ab8-151">Proprietà **appartenenze a gruppi** aggiornata con il gruppo **Sales** .</span><span class="sxs-lookup"><span data-stu-id="c2ab8-151">**Group memberships** property updated with the **Sales** group.</span></span>
- <span data-ttu-id="c2ab8-152">Proprietà delle **licenze di prodotto** aggiornate con le licenze **Enterprise Mobility + Security e5** e **Office 365 Enterprise E5** .</span><span class="sxs-lookup"><span data-stu-id="c2ab8-152">**Product licenses** property updated with the **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5** licenses.</span></span>

<span data-ttu-id="c2ab8-153">Per informazioni e collegamenti per la distribuzione di appartenenza a gruppi dinamici e licenze automatiche in produzione, vedere questi passaggi nella fase di identità:</span><span class="sxs-lookup"><span data-stu-id="c2ab8-153">See these steps in the Identity phase for information and links to deploy dynamic group membership and automatic licensing in production:</span></span>

- [<span data-ttu-id="c2ab8-154">Configurare l'assegnazione automatica delle licenze</span><span class="sxs-lookup"><span data-stu-id="c2ab8-154">Set up automatic licensing</span></span>](identity-use-group-management.md#identity-group-license)
- [<span data-ttu-id="c2ab8-155">Configurare l'appartenenza a gruppi dinamica</span><span class="sxs-lookup"><span data-stu-id="c2ab8-155">Set up dynamic group membership</span></span>](identity-use-group-management.md#identity-dyn-groups)

## <a name="next-step"></a><span data-ttu-id="c2ab8-156">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="c2ab8-156">Next step</span></span>

<span data-ttu-id="c2ab8-157">Esplorare altre caratteristiche e funzionalità [identità](m365-enterprise-test-lab-guides.md#identity) nell'ambiente di test.</span><span class="sxs-lookup"><span data-stu-id="c2ab8-157">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="c2ab8-158">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c2ab8-158">See also</span></span>

[<span data-ttu-id="c2ab8-159">Fase 2: identità</span><span class="sxs-lookup"><span data-stu-id="c2ab8-159">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="c2ab8-160">Guide al lab di test di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="c2ab8-160">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

<span data-ttu-id="c2ab8-161">[Distribuzione di Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="c2ab8-161">[Microsoft 365 Enterprise deployment](deploy-microsoft-365-enterprise.md)</span></span>

[<span data-ttu-id="c2ab8-162">Documentazione di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="c2ab8-162">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
