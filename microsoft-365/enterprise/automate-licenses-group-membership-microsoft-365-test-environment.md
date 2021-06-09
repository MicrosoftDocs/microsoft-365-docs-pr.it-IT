---
title: Automatizzare le licenze e l'appartenenza ai gruppi per l'Microsoft 365 per l'ambiente di testing aziendale
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
description: Configurare le licenze basate su gruppi e l'appartenenza a gruppi dinamici nell'Microsoft 365 per l'ambiente di testing aziendale.
ms.openlocfilehash: 26840e2884202a0fa9c4bb563f3d7c653482ef87
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905369"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="e8967-103">Automatizzare le licenze e l'appartenenza ai gruppi per l'Microsoft 365 per l'ambiente di testing aziendale</span><span class="sxs-lookup"><span data-stu-id="e8967-103">Automate licensing and group membership for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="e8967-104">*Questa guida al laboratorio di testing può essere utilizzata solo per Microsoft 365 per ambienti di test aziendali.*</span><span class="sxs-lookup"><span data-stu-id="e8967-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="e8967-105">Le licenze basate su gruppo assegnano o rimuove automaticamente le licenze per un account utente in base all'appartenenza al gruppo.</span><span class="sxs-lookup"><span data-stu-id="e8967-105">Group-based licensing automatically assigns or removes licenses for a user account based on group membership.</span></span> <span data-ttu-id="e8967-106">L'appartenenza a un gruppo dinamico aggiunge o rimuove membri a un gruppo in base alle proprietà dell'account utente, ad esempio **Department** o **Country.**</span><span class="sxs-lookup"><span data-stu-id="e8967-106">Dynamic group membership adds or removes members to a group based on user account properties, such as **Department** or **Country**.</span></span> <span data-ttu-id="e8967-107">In questo articolo vengono illustrate le dimostrazioni relative all'aggiunta e alla rimozione di membri del gruppo nell'Microsoft 365 per l'ambiente di testing aziendale.</span><span class="sxs-lookup"><span data-stu-id="e8967-107">This article steps you through demonstrations of both adding and removing group members in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="e8967-108">La configurazione della licenza automatica e dell'appartenenza a gruppi dinamici nel Microsoft 365 per l'ambiente di testing aziendale prevede due fasi:</span><span class="sxs-lookup"><span data-stu-id="e8967-108">Setting up auto-licensing and dynamic group membership in your Microsoft 365 for enterprise test environment involves two phases:</span></span>

- [<span data-ttu-id="e8967-109">Fase 1: creare l'ambiente di testing Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="e8967-109">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="e8967-110">Fase 2: configurare e testare l'appartenenza a gruppi dinamici e le licenze automatiche</span><span class="sxs-lookup"><span data-stu-id="e8967-110">Phase 2: Configure and test dynamic group membership and automatic licensing</span></span>](#phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing)

![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="e8967-112">Per una mappa visiva a tutti gli articoli dello stack Microsoft 365 per enterprise Test Lab Guide, passare a [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="e8967-112">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="e8967-113">Fase 1: creare l'ambiente di testing Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="e8967-113">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="e8967-114">Se si desidera testare solo le licenze automatizzate e l'appartenenza ai gruppi in modo leggero con i requisiti minimi, seguire le istruzioni in [Configurazione di base lightweight](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="e8967-114">If you want to only test automated licensing and group membership in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="e8967-115">Se si desidera testare le licenze automatizzate e l'appartenenza a gruppi in un'azienda simulata, seguire le istruzioni in [Autenticazione pass-through.](pass-through-auth-m365-ent-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="e8967-115">If you want to test automated licensing and group membership in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="e8967-116">Il test delle licenze automatizzate e dell'appartenenza ai gruppi non richiede l'ambiente di testing aziendale simulato, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per una foresta di Servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e8967-116">Testing automated licensing and group membership doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="e8967-117">Viene fornito qui come opzione in modo da poter testare le licenze automatizzate e l'appartenenza ai gruppi e sperimentarla in un ambiente che rappresenta un'organizzazione tipica.</span><span class="sxs-lookup"><span data-stu-id="e8967-117">It's provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span>
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a><span data-ttu-id="e8967-118">Fase 2: configurare e testare l'appartenenza a gruppi dinamici e le licenze automatiche</span><span class="sxs-lookup"><span data-stu-id="e8967-118">Phase 2: Configure and test dynamic group membership and automatic licensing</span></span>

<span data-ttu-id="e8967-119">Innanzitutto, crea un nuovo gruppo denominato Sales e aggiungi una regola di appartenenza a un gruppo dinamico in modo che gli account utente con **Department** impostato su **Sales** si uniranno automaticamente al gruppo Sales.</span><span class="sxs-lookup"><span data-stu-id="e8967-119">First, create a new group named Sales, and add a dynamic group membership rule so that user accounts with the **Department** set to **Sales** automatically join the Sales group.</span></span>

1. <span data-ttu-id="e8967-120">In un'istanza privata del browser Internet, accedere all'interfaccia di amministrazione di [Microsoft 365](https://admin.microsoft.com) con l'account di amministratore globale dell'Microsoft 365 E5 del laboratorio di testing.</span><span class="sxs-lookup"><span data-stu-id="e8967-120">In a private instance of your internet browser, sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with the global administrator account of your Microsoft 365 E5 test lab subscription.</span></span>
2. <span data-ttu-id="e8967-121">In una scheda separata del browser passare al portale di Azure all'indirizzo [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="e8967-121">On a separate tab of your browser, go to the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>
3. <span data-ttu-id="e8967-122">Nel portale di Azure immettere **i gruppi** nella casella di ricerca e quindi selezionare **Gruppi**.</span><span class="sxs-lookup"><span data-stu-id="e8967-122">In the Azure portal, enter **groups** in the search box, and then select **Groups**.</span></span>
4. <span data-ttu-id="e8967-123">nel riquadro **Tutti i** gruppi selezionare **Nuovo gruppo**.</span><span class="sxs-lookup"><span data-stu-id="e8967-123">in the **All groups** pane, select **New group**.</span></span>
5. <span data-ttu-id="e8967-124">In **Tipo di gruppo** selezionare **Microsoft 365**.</span><span class="sxs-lookup"><span data-stu-id="e8967-124">In **Group type**, select **Microsoft 365**.</span></span>
6. <span data-ttu-id="e8967-125">In **Nome gruppo** immettere **Vendite.**</span><span class="sxs-lookup"><span data-stu-id="e8967-125">In **Group name**, enter **Sales**.</span></span>
7. <span data-ttu-id="e8967-126">In **Tipo di appartenenza** selezionare **Utente dinamico**.</span><span class="sxs-lookup"><span data-stu-id="e8967-126">In **Membership type**, select **Dynamic user**.</span></span>
8. <span data-ttu-id="e8967-127">Selezionare **Membri utente dinamici**.</span><span class="sxs-lookup"><span data-stu-id="e8967-127">Select **Dynamic user members**.</span></span>
9. <span data-ttu-id="e8967-128">Nel riquadro **Regole di appartenenza** dinamiche:</span><span class="sxs-lookup"><span data-stu-id="e8967-128">In the **Dynamic membership rules** pane:</span></span> 
   - <span data-ttu-id="e8967-129">Selezionare la **proprietà del** reparto.</span><span class="sxs-lookup"><span data-stu-id="e8967-129">Select the **department** property.</span></span>
   - <span data-ttu-id="e8967-130">Selezionare **l'operatore Equals.**</span><span class="sxs-lookup"><span data-stu-id="e8967-130">Select the **Equals** operator.</span></span>
   - <span data-ttu-id="e8967-131">Nella casella **Valore** immettere **Vendite**.</span><span class="sxs-lookup"><span data-stu-id="e8967-131">In the **Value** box, enter **Sales**.</span></span>
10. <span data-ttu-id="e8967-132">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e8967-132">Select **Save**.</span></span>
11. <span data-ttu-id="e8967-133">Selezionare **Crea**.</span><span class="sxs-lookup"><span data-stu-id="e8967-133">Select **Create**.</span></span>

<span data-ttu-id="e8967-134">Configurare quindi il gruppo Vendite in modo che ai membri sia assegnata automaticamente la Microsoft 365 E5 licenza.</span><span class="sxs-lookup"><span data-stu-id="e8967-134">Next, configure the Sales group so that members are automatically assigned the Microsoft 365 E5 license.</span></span>

1. <span data-ttu-id="e8967-135">Selezionare il **gruppo** Vendite e quindi **Licenze**.</span><span class="sxs-lookup"><span data-stu-id="e8967-135">Select the **Sales** group, and then select **Licenses**.</span></span>
2. <span data-ttu-id="e8967-136">Nel riquadro **Aggiorna assegnazioni licenze** selezionare **Microsoft 365 E5** e quindi selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e8967-136">In the **Update license assignments** pane, select **Microsoft 365 E5**, and then select **Save**.</span></span>
3. <span data-ttu-id="e8967-137">Nel browser chiudere la scheda Portale di Azure.</span><span class="sxs-lookup"><span data-stu-id="e8967-137">In your browser, close the Azure portal tab.</span></span>

<span data-ttu-id="e8967-138">Testare quindi l'appartenenza a gruppi dinamici e le licenze automatiche nell'account Utente 4:</span><span class="sxs-lookup"><span data-stu-id="e8967-138">Next, test dynamic group membership and automatic licensing on the User 4 account:</span></span>

1. <span data-ttu-id="e8967-139">Nella scheda **Microsoft Office Home** nel browser seleziona **Amministratore.**</span><span class="sxs-lookup"><span data-stu-id="e8967-139">From the **Microsoft Office Home** tab in your browser, select **Admin**.</span></span>
2. <span data-ttu-id="e8967-140">Nella scheda **Microsoft 365 di amministrazione** selezionare Utenti **attivi**.</span><span class="sxs-lookup"><span data-stu-id="e8967-140">From the **Microsoft 365 admin center** tab, select **Active users**.</span></span>
3. <span data-ttu-id="e8967-141">Nella pagina **Utenti attivi** selezionare l'account **Utente 4.**</span><span class="sxs-lookup"><span data-stu-id="e8967-141">On the **Active users** page, select the **User 4** account.</span></span>
4. <span data-ttu-id="e8967-142">Nel riquadro **Utente 4** selezionare **Modifica** per **Licenze prodotto**.</span><span class="sxs-lookup"><span data-stu-id="e8967-142">On the **User 4** pane, select **Edit** for **Product licenses**.</span></span>
5. <span data-ttu-id="e8967-143">Nel riquadro **Licenze prodotto** disabilitare la licenza **Microsoft 365 E5** e quindi selezionare **Salva**  >  **chiudi.**</span><span class="sxs-lookup"><span data-stu-id="e8967-143">On the **Product licenses** pane, disable the **Microsoft 365 E5** license, and then select **Save** > **Close**.</span></span>
6. <span data-ttu-id="e8967-144">Nelle proprietà dell'account Utente 4 verificare che non siano state assegnate licenze di prodotto e che non vi siano appartenenze a gruppi.</span><span class="sxs-lookup"><span data-stu-id="e8967-144">In the properties of the User 4 account, verify that no product licenses have been assigned and there are no group memberships.</span></span>
7. <span data-ttu-id="e8967-145">Per **Informazioni di contatto,** selezionare **Modifica.**</span><span class="sxs-lookup"><span data-stu-id="e8967-145">For **Contact information**, select **Edit**.</span></span>
8. <span data-ttu-id="e8967-146">Nel riquadro **Modifica informazioni contatto** selezionare Informazioni di **contatto**.</span><span class="sxs-lookup"><span data-stu-id="e8967-146">In the **Edit Contact information** pane, select **Contact information**.</span></span>
9. <span data-ttu-id="e8967-147">Nella casella **Reparto** immettere **Vendite** e quindi selezionare **Salva**  >  **chiudi.**</span><span class="sxs-lookup"><span data-stu-id="e8967-147">In the **Department** box, enter **Sales**, and then select **Save** > **Close**.</span></span>
10. <span data-ttu-id="e8967-148">Attendere alcuni minuti e quindi selezionare periodicamente l'icona **Aggiorna** nell'angolo superiore destro del riquadro Account utente 4.</span><span class="sxs-lookup"><span data-stu-id="e8967-148">Wait a few minutes, and then periodically select the **Refresh** icon in the upper-right of the User 4 account pane.</span></span>

<span data-ttu-id="e8967-149">Nel tempo dovrebbe essere visualizzato:</span><span class="sxs-lookup"><span data-stu-id="e8967-149">In time, you should see the:</span></span>

- <span data-ttu-id="e8967-150">**Proprietà memberships** del gruppo aggiornata con il **gruppo Sales.**</span><span class="sxs-lookup"><span data-stu-id="e8967-150">**Group memberships** property updated with the **Sales** group.</span></span>
- <span data-ttu-id="e8967-151">**Proprietà licenze** di prodotto aggiornata con la **Microsoft 365 E5** licenza.</span><span class="sxs-lookup"><span data-stu-id="e8967-151">**Product licenses** property updated with the **Microsoft 365 E5** license.</span></span>

<span data-ttu-id="e8967-152">Vedi questi articoli per distribuire l'appartenenza a gruppi dinamici e le licenze automatiche in produzione:</span><span class="sxs-lookup"><span data-stu-id="e8967-152">See these articles to deploy dynamic group membership and automatic licensing in production:</span></span>

- [<span data-ttu-id="e8967-153">Licenze basate su gruppo in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="e8967-153">Group-based licensing in Azure Active Directory</span></span>](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)
- [<span data-ttu-id="e8967-154">Gruppi dinamici in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="e8967-154">Dynamic groups in Azure Active Directory</span></span>](/azure/active-directory/users-groups-roles/groups-create-rule)

## <a name="next-step"></a><span data-ttu-id="e8967-155">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="e8967-155">Next step</span></span>

<span data-ttu-id="e8967-156">Esplorare altre caratteristiche e funzionalità [identità](m365-enterprise-test-lab-guides.md#identity) nell'ambiente di test.</span><span class="sxs-lookup"><span data-stu-id="e8967-156">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="e8967-157">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e8967-157">See also</span></span>

[<span data-ttu-id="e8967-158">Guida di orientamento all'identità</span><span class="sxs-lookup"><span data-stu-id="e8967-158">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="e8967-159">Guide ai lab di test di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="e8967-159">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="e8967-160">Panoramica di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="e8967-160">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="e8967-161">Documentazione di Microsoft 365 for enterprise</span><span class="sxs-lookup"><span data-stu-id="e8967-161">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)