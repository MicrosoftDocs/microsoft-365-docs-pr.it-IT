---
title: Automatizzare le licenze e l'appartenenza ai gruppi per l'ambiente di testing di Microsoft 365 per le aziende
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
description: Configurare le licenze basate su gruppi e l'appartenenza dinamica ai gruppi nell'ambiente di testing di Microsoft 365 per le aziende.
ms.openlocfilehash: d770e7be3b0b55855f1fee26a45d55260c3074cb
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487577"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="3ee3d-103">Automatizzare le licenze e l'appartenenza ai gruppi per l'ambiente di testing di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="3ee3d-103">Automate licensing and group membership for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="3ee3d-104">*Questa guida del laboratorio di testing può essere usata solo per gli ambienti di testing di Microsoft 365 per le aziende.*</span><span class="sxs-lookup"><span data-stu-id="3ee3d-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="3ee3d-105">Le licenze basate su gruppo assegnano o rimuove automaticamente le licenze per un account utente in base all'appartenenza ai gruppi.</span><span class="sxs-lookup"><span data-stu-id="3ee3d-105">Group-based licensing automatically assigns or removes licenses for a user account based on group membership.</span></span> <span data-ttu-id="3ee3d-106">L'appartenenza dinamica al gruppo aggiunge o rimuove membri a un gruppo in base alle proprietà dell'account utente, ad esempio **Reparto** o **Paese.**</span><span class="sxs-lookup"><span data-stu-id="3ee3d-106">Dynamic group membership adds or removes members to a group based on user account properties, such as **Department** or **Country**.</span></span> <span data-ttu-id="3ee3d-107">Questo articolo illustra le dimostrazioni dell'aggiunta e della rimozione dei membri del gruppo nell'ambiente di testing di Microsoft 365 per le aziende.</span><span class="sxs-lookup"><span data-stu-id="3ee3d-107">This article steps you through demonstrations of both adding and removing group members in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="3ee3d-108">La configurazione della licenza automatica e dell'appartenenza dinamica ai gruppi nell'ambiente di testing di Microsoft 365 per le aziende prevede due fasi:</span><span class="sxs-lookup"><span data-stu-id="3ee3d-108">Setting up auto-licensing and dynamic group membership in your Microsoft 365 for enterprise test environment involves two phases:</span></span>

- [<span data-ttu-id="3ee3d-109">Fase 1: creare l'ambiente di testing di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="3ee3d-109">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="3ee3d-110">Fase 2: configurare e testare l'appartenenza a gruppi dinamici e le licenze automatiche</span><span class="sxs-lookup"><span data-stu-id="3ee3d-110">Phase 2: Configure and test dynamic group membership and automatic licensing</span></span>](#phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing)

![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="3ee3d-112">Per una mappa visiva di tutti gli articoli della guida del lab di test di Microsoft 365 per le aziende, passare a [Microsoft 365 per enterprise Test Lab Guide Stack.](../downloads/Microsoft365EnterpriseTLGStack.pdf)</span><span class="sxs-lookup"><span data-stu-id="3ee3d-112">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="3ee3d-113">Fase 1: creare l'ambiente di testing di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="3ee3d-113">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="3ee3d-114">Se si desidera testare solo le licenze automatizzate e l'appartenenza ai gruppi in modo leggero con i requisiti minimi, seguire le istruzioni in [Configurazione di base lightweight.](lightweight-base-configuration-microsoft-365-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="3ee3d-114">If you want to only test automated licensing and group membership in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="3ee3d-115">Se si desidera testare le licenze automatizzate e l'appartenenza ai gruppi in un'azienda simulata, seguire le istruzioni in [Autenticazione pass-through.](pass-through-auth-m365-ent-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="3ee3d-115">If you want to test automated licensing and group membership in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="3ee3d-116">Il test delle licenze automatizzate e dell'appartenenza ai gruppi non richiede l'ambiente di testing aziendale simulato, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per una foresta di Servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3ee3d-116">Testing automated licensing and group membership doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="3ee3d-117">Qui viene fornito come opzione, in modo da poter testare le licenze automatizzate e l'appartenenza ai gruppi e sperimentarla in un ambiente che rappresenta un'organizzazione tipica.</span><span class="sxs-lookup"><span data-stu-id="3ee3d-117">It's provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span>
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a><span data-ttu-id="3ee3d-118">Fase 2: configurare e testare l'appartenenza a gruppi dinamici e le licenze automatiche</span><span class="sxs-lookup"><span data-stu-id="3ee3d-118">Phase 2: Configure and test dynamic group membership and automatic licensing</span></span>

<span data-ttu-id="3ee3d-119">Creare innanzitutto un nuovo gruppo denominato Sales e aggiungere una regola di appartenenza a un gruppo dinamico in modo che gli account utente con **reparto** impostato su **Vendite** si uniranno automaticamente al gruppo Vendite.</span><span class="sxs-lookup"><span data-stu-id="3ee3d-119">First, create a new group named Sales, and add a dynamic group membership rule so that user accounts with the **Department** set to **Sales** automatically join the Sales group.</span></span>

1. <span data-ttu-id="3ee3d-120">In un'istanza privata del browser Internet, accedere all'interfaccia di amministrazione di [Microsoft 365](https://admin.microsoft.com) con l'account amministratore globale dell'abbonamento al laboratorio di testing di Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="3ee3d-120">In a private instance of your internet browser, sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with the global administrator account of your Microsoft 365 E5 test lab subscription.</span></span>
2. <span data-ttu-id="3ee3d-121">In una scheda separata del browser passare al portale di Azure all'indirizzo [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="3ee3d-121">On a separate tab of your browser, go to the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>
3. <span data-ttu-id="3ee3d-122">Nel portale di Azure immetti **i gruppi nella** casella di ricerca e quindi seleziona **Gruppi.**</span><span class="sxs-lookup"><span data-stu-id="3ee3d-122">In the Azure portal, enter **groups** in the search box, and then select **Groups**.</span></span>
4. <span data-ttu-id="3ee3d-123">nel riquadro **Tutti i** gruppi selezionare **Nuovo gruppo.**</span><span class="sxs-lookup"><span data-stu-id="3ee3d-123">in the **All groups** pane, select **New group**.</span></span>
5. <span data-ttu-id="3ee3d-124">In **Tipo di gruppo** selezionare Microsoft **365.**</span><span class="sxs-lookup"><span data-stu-id="3ee3d-124">In **Group type**, select **Microsoft 365**.</span></span>
6. <span data-ttu-id="3ee3d-125">In **Nome gruppo** immettere **Vendite.**</span><span class="sxs-lookup"><span data-stu-id="3ee3d-125">In **Group name**, enter **Sales**.</span></span>
7. <span data-ttu-id="3ee3d-126">In **Tipo di appartenenza** selezionare **Utente dinamico.**</span><span class="sxs-lookup"><span data-stu-id="3ee3d-126">In **Membership type**, select **Dynamic user**.</span></span>
8. <span data-ttu-id="3ee3d-127">Selezionare **Membri utente dinamici.**</span><span class="sxs-lookup"><span data-stu-id="3ee3d-127">Select **Dynamic user members**.</span></span>
9. <span data-ttu-id="3ee3d-128">Nel riquadro **Regole di appartenenza** dinamiche:</span><span class="sxs-lookup"><span data-stu-id="3ee3d-128">In the **Dynamic membership rules** pane:</span></span> 
   - <span data-ttu-id="3ee3d-129">Selezionare la **proprietà del** reparto.</span><span class="sxs-lookup"><span data-stu-id="3ee3d-129">Select the **department** property.</span></span>
   - <span data-ttu-id="3ee3d-130">Selezionare **l'operatore Equals.**</span><span class="sxs-lookup"><span data-stu-id="3ee3d-130">Select the **Equals** operator.</span></span>
   - <span data-ttu-id="3ee3d-131">Nella casella **Valore** immettere **Vendite.**</span><span class="sxs-lookup"><span data-stu-id="3ee3d-131">In the **Value** box, enter **Sales**.</span></span>
10. <span data-ttu-id="3ee3d-132">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="3ee3d-132">Select **Save**.</span></span>
11. <span data-ttu-id="3ee3d-133">Selezionare **Crea**.</span><span class="sxs-lookup"><span data-stu-id="3ee3d-133">Select **Create**.</span></span>

<span data-ttu-id="3ee3d-134">Successivamente, configurare il gruppo Vendite in modo che ai membri sia assegnata automaticamente la licenza di Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="3ee3d-134">Next, configure the Sales group so that members are automatically assigned the Microsoft 365 E5 license.</span></span>

1. <span data-ttu-id="3ee3d-135">Selezionare il **gruppo** Vendite e quindi **Licenze.**</span><span class="sxs-lookup"><span data-stu-id="3ee3d-135">Select the **Sales** group, and then select **Licenses**.</span></span>
2. <span data-ttu-id="3ee3d-136">Nel riquadro **Aggiorna assegnazioni licenze** selezionare **Microsoft 365 E5** e quindi fare clic su **Salva.**</span><span class="sxs-lookup"><span data-stu-id="3ee3d-136">In the **Update license assignments** pane, select **Microsoft 365 E5**, and then select **Save**.</span></span>
3. <span data-ttu-id="3ee3d-137">Nel browser, chiudere la scheda del portale di Azure.</span><span class="sxs-lookup"><span data-stu-id="3ee3d-137">In your browser, close the Azure portal tab.</span></span>

<span data-ttu-id="3ee3d-138">Successivamente, testare l'appartenenza a gruppi dinamici e le licenze automatiche nell'account User 4:</span><span class="sxs-lookup"><span data-stu-id="3ee3d-138">Next, test dynamic group membership and automatic licensing on the User 4 account:</span></span>

1. <span data-ttu-id="3ee3d-139">Nella Microsoft Office **Home** del browser, selezionare **Amministratore.**</span><span class="sxs-lookup"><span data-stu-id="3ee3d-139">From the **Microsoft Office Home** tab in your browser, select **Admin**.</span></span>
2. <span data-ttu-id="3ee3d-140">Nella scheda **dell'interfaccia di amministrazione di Microsoft 365** selezionare **Utenti attivi.**</span><span class="sxs-lookup"><span data-stu-id="3ee3d-140">From the **Microsoft 365 admin center** tab, select **Active users**.</span></span>
3. <span data-ttu-id="3ee3d-141">Nella pagina **Utenti attivi** selezionare l'account **Utente 4.**</span><span class="sxs-lookup"><span data-stu-id="3ee3d-141">On the **Active users** page, select the **User 4** account.</span></span>
4. <span data-ttu-id="3ee3d-142">Nel riquadro **User 4** selezionare **Edit** for **Product licenses.**</span><span class="sxs-lookup"><span data-stu-id="3ee3d-142">On the **User 4** pane, select **Edit** for **Product licenses**.</span></span>
5. <span data-ttu-id="3ee3d-143">Nel riquadro **Licenze di** prodotto disabilitare la licenza di **Microsoft 365 E5** e quindi selezionare **Salva**  >  **chiudi.**</span><span class="sxs-lookup"><span data-stu-id="3ee3d-143">On the **Product licenses** pane, disable the **Microsoft 365 E5** license, and then select **Save** > **Close**.</span></span>
6. <span data-ttu-id="3ee3d-144">Nelle proprietà dell'account User 4 verificare che non siano state assegnate licenze di prodotto e che non vi siano appartenenze a gruppi.</span><span class="sxs-lookup"><span data-stu-id="3ee3d-144">In the properties of the User 4 account, verify that no product licenses have been assigned and there are no group memberships.</span></span>
7. <span data-ttu-id="3ee3d-145">Per **Informazioni sul contatto,** selezionare **Modifica.**</span><span class="sxs-lookup"><span data-stu-id="3ee3d-145">For **Contact information**, select **Edit**.</span></span>
8. <span data-ttu-id="3ee3d-146">Nel riquadro **Modifica informazioni contatto** selezionare Informazioni di **contatto.**</span><span class="sxs-lookup"><span data-stu-id="3ee3d-146">In the **Edit Contact information** pane, select **Contact information**.</span></span>
9. <span data-ttu-id="3ee3d-147">Nella casella **Reparto** immettere **Vendite** e quindi selezionare **Salva**  >  **chiudi.**</span><span class="sxs-lookup"><span data-stu-id="3ee3d-147">In the **Department** box, enter **Sales**, and then select **Save** > **Close**.</span></span>
10. <span data-ttu-id="3ee3d-148">Attendere alcuni minuti e quindi selezionare  periodicamente l'icona Aggiorna nell'angolo in alto a destra del riquadro dell'account utente 4.</span><span class="sxs-lookup"><span data-stu-id="3ee3d-148">Wait a few minutes, and then periodically select the **Refresh** icon in the upper-right of the User 4 account pane.</span></span>

<span data-ttu-id="3ee3d-149">Nel tempo, dovrebbe essere visualizzato:</span><span class="sxs-lookup"><span data-stu-id="3ee3d-149">In time, you should see the:</span></span>

- <span data-ttu-id="3ee3d-150">**Proprietà di appartenenza** al gruppo aggiornata con **il gruppo** Vendite.</span><span class="sxs-lookup"><span data-stu-id="3ee3d-150">**Group memberships** property updated with the **Sales** group.</span></span>
- <span data-ttu-id="3ee3d-151">**Proprietà licenze** di prodotto aggiornata con la licenza di **Microsoft 365 E5.**</span><span class="sxs-lookup"><span data-stu-id="3ee3d-151">**Product licenses** property updated with the **Microsoft 365 E5** license.</span></span>

<span data-ttu-id="3ee3d-152">Vedi questi articoli per distribuire l'appartenenza a gruppi dinamici e le licenze automatiche in produzione:</span><span class="sxs-lookup"><span data-stu-id="3ee3d-152">See these articles to deploy dynamic group membership and automatic licensing in production:</span></span>

- [<span data-ttu-id="3ee3d-153">Licenze basate su gruppo in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="3ee3d-153">Group-based licensing in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)
- [<span data-ttu-id="3ee3d-154">Gruppi dinamici in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="3ee3d-154">Dynamic groups in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)

## <a name="next-step"></a><span data-ttu-id="3ee3d-155">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="3ee3d-155">Next step</span></span>

<span data-ttu-id="3ee3d-156">Esplorare altre caratteristiche e funzionalità [identità](m365-enterprise-test-lab-guides.md#identity) nell'ambiente di test.</span><span class="sxs-lookup"><span data-stu-id="3ee3d-156">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="3ee3d-157">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3ee3d-157">See also</span></span>

[<span data-ttu-id="3ee3d-158">Guida di orientamento all'identità</span><span class="sxs-lookup"><span data-stu-id="3ee3d-158">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="3ee3d-159">Guide ai lab di test di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="3ee3d-159">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="3ee3d-160">Panoramica di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="3ee3d-160">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="3ee3d-161">Documentazione di Microsoft 365 for enterprise</span><span class="sxs-lookup"><span data-stu-id="3ee3d-161">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
