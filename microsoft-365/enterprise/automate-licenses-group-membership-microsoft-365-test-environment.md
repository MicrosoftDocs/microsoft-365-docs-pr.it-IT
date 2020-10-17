---
title: Automatizzare le licenze e l'appartenenza ai gruppi per l'ambiente di testing di Microsoft 365 per l'organizzazione
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Configurare la gestione delle licenze basate su gruppo e l'appartenenza a gruppi dinamici nell'ambiente di testing di Microsoft 365 per l'organizzazione.
ms.openlocfilehash: d770e7be3b0b55855f1fee26a45d55260c3074cb
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487577"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="b6393-103">Automatizzare le licenze e l'appartenenza ai gruppi per l'ambiente di testing di Microsoft 365 per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="b6393-103">Automate licensing and group membership for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="b6393-104">*Questa guida del laboratorio di testing può essere utilizzata solo per Microsoft 365 per gli ambienti di testing dell'organizzazione.*</span><span class="sxs-lookup"><span data-stu-id="b6393-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="b6393-105">La gestione delle licenze basate su gruppo assegna o rimuove automaticamente le licenze per un account utente basato sull'appartenenza a un gruppo.</span><span class="sxs-lookup"><span data-stu-id="b6393-105">Group-based licensing automatically assigns or removes licenses for a user account based on group membership.</span></span> <span data-ttu-id="b6393-106">L'appartenenza a un gruppo dinamico aggiunge o rimuove membri a un gruppo in base alle proprietà degli account utente, ad esempio **reparto** o **paese**.</span><span class="sxs-lookup"><span data-stu-id="b6393-106">Dynamic group membership adds or removes members to a group based on user account properties, such as **Department** or **Country**.</span></span> <span data-ttu-id="b6393-107">In questo articolo vengono illustrati sia l'aggiunta che la rimozione dei membri del gruppo nell'ambiente di testing di Microsoft 365 per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b6393-107">This article steps you through demonstrations of both adding and removing group members in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="b6393-108">La configurazione delle licenze automatiche e l'appartenenza a gruppi dinamici nell'ambiente di testing di Microsoft 365 per l'organizzazione implica due fasi:</span><span class="sxs-lookup"><span data-stu-id="b6393-108">Setting up auto-licensing and dynamic group membership in your Microsoft 365 for enterprise test environment involves two phases:</span></span>

- [<span data-ttu-id="b6393-109">Fase 1: creare l'ambiente di testing di Microsoft 365 per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="b6393-109">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="b6393-110">Fase 2: configurare e testare l'appartenenza a gruppi dinamici e la gestione automatica delle licenze</span><span class="sxs-lookup"><span data-stu-id="b6393-110">Phase 2: Configure and test dynamic group membership and automatic licensing</span></span>](#phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing)

![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="b6393-112">Per una mappa visiva su tutti gli articoli della guida del laboratorio di testing di Microsoft 365 for Enterprise, accedere a [microsoft 365 per la guida dello stack del laboratorio di testing dell'organizzazione](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="b6393-112">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="b6393-113">Fase 1: creare l'ambiente di testing di Microsoft 365 per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="b6393-113">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="b6393-114">Se si desidera testare solo la licenza automatizzata e l'appartenenza al gruppo in modo semplice con i requisiti minimi, seguire le istruzioni contenute in [Lightweight base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="b6393-114">If you want to only test automated licensing and group membership in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="b6393-115">Se si desidera testare la licenza automatizzata e l'appartenenza a un gruppo in un'azienda simulata, seguire le istruzioni riportate nell' [autenticazione pass-through](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="b6393-115">If you want to test automated licensing and group membership in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="b6393-116">Testing Automatic Licensing and Group Membership non richiede l'ambiente di testing dell'organizzazione simulata, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per una foresta di servizi di dominio Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="b6393-116">Testing automated licensing and group membership doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="b6393-117">È disponibile come opzione in modo che sia possibile testare la licenza automatizzata e l'appartenenza ai gruppi e sperimentarla in un ambiente che rappresenta un'organizzazione tipica.</span><span class="sxs-lookup"><span data-stu-id="b6393-117">It's provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span>
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a><span data-ttu-id="b6393-118">Fase 2: configurare e testare l'appartenenza a gruppi dinamici e la gestione automatica delle licenze</span><span class="sxs-lookup"><span data-stu-id="b6393-118">Phase 2: Configure and test dynamic group membership and automatic licensing</span></span>

<span data-ttu-id="b6393-119">Innanzitutto, creare un nuovo gruppo denominato Sales e aggiungere una regola di appartenenza a un gruppo dinamico in modo che gli account utente con il **reparto** impostato su **vendite** aderiscano automaticamente al gruppo Sales.</span><span class="sxs-lookup"><span data-stu-id="b6393-119">First, create a new group named Sales, and add a dynamic group membership rule so that user accounts with the **Department** set to **Sales** automatically join the Sales group.</span></span>

1. <span data-ttu-id="b6393-120">In un'istanza privata del browser Internet, accedere all'interfaccia di [amministrazione di microsoft 365](https://admin.microsoft.com) con l'account di amministratore globale dell'abbonamento al laboratorio di testing di Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="b6393-120">In a private instance of your internet browser, sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with the global administrator account of your Microsoft 365 E5 test lab subscription.</span></span>
2. <span data-ttu-id="b6393-121">In una scheda separata del browser, accedere al portale di Azure all'indirizzo [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="b6393-121">On a separate tab of your browser, go to the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>
3. <span data-ttu-id="b6393-122">Nel portale di Azure, immettere **gruppi** nella casella di ricerca e quindi selezionare **gruppi**.</span><span class="sxs-lookup"><span data-stu-id="b6393-122">In the Azure portal, enter **groups** in the search box, and then select **Groups**.</span></span>
4. <span data-ttu-id="b6393-123">nel riquadro **tutti i gruppi** selezionare **nuovo gruppo**.</span><span class="sxs-lookup"><span data-stu-id="b6393-123">in the **All groups** pane, select **New group**.</span></span>
5. <span data-ttu-id="b6393-124">In **tipo di gruppo**selezionare **Microsoft 365**.</span><span class="sxs-lookup"><span data-stu-id="b6393-124">In **Group type**, select **Microsoft 365**.</span></span>
6. <span data-ttu-id="b6393-125">In **nome gruppo**immettere **Sales**.</span><span class="sxs-lookup"><span data-stu-id="b6393-125">In **Group name**, enter **Sales**.</span></span>
7. <span data-ttu-id="b6393-126">In **tipo di appartenenza**, selezionare **utente dinamico**.</span><span class="sxs-lookup"><span data-stu-id="b6393-126">In **Membership type**, select **Dynamic user**.</span></span>
8. <span data-ttu-id="b6393-127">Selezionare **membri dinamici degli utenti**.</span><span class="sxs-lookup"><span data-stu-id="b6393-127">Select **Dynamic user members**.</span></span>
9. <span data-ttu-id="b6393-128">Nel riquadro **delle regole di appartenenza dinamica** :</span><span class="sxs-lookup"><span data-stu-id="b6393-128">In the **Dynamic membership rules** pane:</span></span> 
   - <span data-ttu-id="b6393-129">Selezionare la proprietà **Department** .</span><span class="sxs-lookup"><span data-stu-id="b6393-129">Select the **department** property.</span></span>
   - <span data-ttu-id="b6393-130">Selezionare l'operatore **Equals** .</span><span class="sxs-lookup"><span data-stu-id="b6393-130">Select the **Equals** operator.</span></span>
   - <span data-ttu-id="b6393-131">Nella casella **valore** immettere **Sales**.</span><span class="sxs-lookup"><span data-stu-id="b6393-131">In the **Value** box, enter **Sales**.</span></span>
10. <span data-ttu-id="b6393-132">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b6393-132">Select **Save**.</span></span>
11. <span data-ttu-id="b6393-133">Selezionare **Crea**.</span><span class="sxs-lookup"><span data-stu-id="b6393-133">Select **Create**.</span></span>

<span data-ttu-id="b6393-134">Successivamente, configurare il gruppo vendite in modo che ai membri venga assegnata automaticamente la licenza Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="b6393-134">Next, configure the Sales group so that members are automatically assigned the Microsoft 365 E5 license.</span></span>

1. <span data-ttu-id="b6393-135">Selezionare il gruppo **vendite** e quindi fare clic su **licenze**.</span><span class="sxs-lookup"><span data-stu-id="b6393-135">Select the **Sales** group, and then select **Licenses**.</span></span>
2. <span data-ttu-id="b6393-136">Nel riquadro **Aggiorna assegnazioni licenze** selezionare **Microsoft 365 E5**e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b6393-136">In the **Update license assignments** pane, select **Microsoft 365 E5**, and then select **Save**.</span></span>
3. <span data-ttu-id="b6393-137">Chiudere la scheda del portale di Azure nel browser.</span><span class="sxs-lookup"><span data-stu-id="b6393-137">In your browser, close the Azure portal tab.</span></span>

<span data-ttu-id="b6393-138">Successivamente, testare l'appartenenza a gruppi dinamici e la gestione delle licenze automatiche nell'account User 4:</span><span class="sxs-lookup"><span data-stu-id="b6393-138">Next, test dynamic group membership and automatic licensing on the User 4 account:</span></span>

1. <span data-ttu-id="b6393-139">Nella scheda **Microsoft Office Home** del browser selezionare **admin**.</span><span class="sxs-lookup"><span data-stu-id="b6393-139">From the **Microsoft Office Home** tab in your browser, select **Admin**.</span></span>
2. <span data-ttu-id="b6393-140">Nella scheda dell'interfaccia di **amministrazione di Microsoft 365** selezionare **utenti attivi**.</span><span class="sxs-lookup"><span data-stu-id="b6393-140">From the **Microsoft 365 admin center** tab, select **Active users**.</span></span>
3. <span data-ttu-id="b6393-141">Nella pagina **utenti attivi** selezionare l'account **User 4** .</span><span class="sxs-lookup"><span data-stu-id="b6393-141">On the **Active users** page, select the **User 4** account.</span></span>
4. <span data-ttu-id="b6393-142">Nel riquadro **User 4** , selezionare **modifica** per **licenze di prodotto**.</span><span class="sxs-lookup"><span data-stu-id="b6393-142">On the **User 4** pane, select **Edit** for **Product licenses**.</span></span>
5. <span data-ttu-id="b6393-143">Nel riquadro **licenze di prodotto** disabilitare la licenza **Microsoft 365 E5** e quindi fare clic su **Salva**  >  **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="b6393-143">On the **Product licenses** pane, disable the **Microsoft 365 E5** license, and then select **Save** > **Close**.</span></span>
6. <span data-ttu-id="b6393-144">Nelle proprietà dell'account User 4, verificare che non siano state assegnate licenze di prodotto e che non vi siano appartenenze a gruppi.</span><span class="sxs-lookup"><span data-stu-id="b6393-144">In the properties of the User 4 account, verify that no product licenses have been assigned and there are no group memberships.</span></span>
7. <span data-ttu-id="b6393-145">Per **informazioni sui contatti**, selezionare **modifica**.</span><span class="sxs-lookup"><span data-stu-id="b6393-145">For **Contact information**, select **Edit**.</span></span>
8. <span data-ttu-id="b6393-146">Nel riquadro **modifica informazioni contatto** selezionare informazioni di **contatto**.</span><span class="sxs-lookup"><span data-stu-id="b6393-146">In the **Edit Contact information** pane, select **Contact information**.</span></span>
9. <span data-ttu-id="b6393-147">Nella casella **Department** immettere **Sales**e quindi fare clic su **Salva**  >  **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="b6393-147">In the **Department** box, enter **Sales**, and then select **Save** > **Close**.</span></span>
10. <span data-ttu-id="b6393-148">Attendere alcuni minuti, quindi selezionare periodicamente l'icona **Aggiorna** nell'angolo in alto a destra del riquadro account User 4.</span><span class="sxs-lookup"><span data-stu-id="b6393-148">Wait a few minutes, and then periodically select the **Refresh** icon in the upper-right of the User 4 account pane.</span></span>

<span data-ttu-id="b6393-149">Nel tempo, dovrebbe essere visualizzato il seguente:</span><span class="sxs-lookup"><span data-stu-id="b6393-149">In time, you should see the:</span></span>

- <span data-ttu-id="b6393-150">Proprietà **appartenenze a gruppi** aggiornata con il gruppo **Sales** .</span><span class="sxs-lookup"><span data-stu-id="b6393-150">**Group memberships** property updated with the **Sales** group.</span></span>
- <span data-ttu-id="b6393-151">Proprietà delle **licenze di prodotto** aggiornate con la licenza **Microsoft 365 E5** .</span><span class="sxs-lookup"><span data-stu-id="b6393-151">**Product licenses** property updated with the **Microsoft 365 E5** license.</span></span>

<span data-ttu-id="b6393-152">Vedere questi articoli per distribuire l'appartenenza a gruppi dinamici e la gestione automatica delle licenze in produzione:</span><span class="sxs-lookup"><span data-stu-id="b6393-152">See these articles to deploy dynamic group membership and automatic licensing in production:</span></span>

- [<span data-ttu-id="b6393-153">Gestione delle licenze basate su gruppo in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="b6393-153">Group-based licensing in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)
- [<span data-ttu-id="b6393-154">Gruppi dinamici in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="b6393-154">Dynamic groups in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)

## <a name="next-step"></a><span data-ttu-id="b6393-155">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="b6393-155">Next step</span></span>

<span data-ttu-id="b6393-156">Esplorare altre caratteristiche e funzionalità [identità](m365-enterprise-test-lab-guides.md#identity) nell'ambiente di test.</span><span class="sxs-lookup"><span data-stu-id="b6393-156">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="b6393-157">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b6393-157">See also</span></span>

[<span data-ttu-id="b6393-158">Roadmap dell'identità</span><span class="sxs-lookup"><span data-stu-id="b6393-158">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="b6393-159">Guide ai lab di test di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="b6393-159">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="b6393-160">Panoramica di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="b6393-160">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="b6393-161">Microsoft 365 per la documentazione relativa all'organizzazione</span><span class="sxs-lookup"><span data-stu-id="b6393-161">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
