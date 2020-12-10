---
title: Creare una Extranet B2B con guest gestiti.
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
- m365initiative-externalcollab
ms.custom: ''
localization_priority: Normal
f1.keywords: NOCSH
description: Informazioni su come creare un sito Extranet o un team B2B con clienti gestiti provenienti da un'organizzazione partner.
ms.openlocfilehash: cfb7cc4310cb83f9ce7761c95f021724b7d75faf
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613597"
---
# <a name="create-a-b2b-extranet-with-managed-guests"></a><span data-ttu-id="6a0c4-103">Creare una Extranet B2B con guest gestiti.</span><span class="sxs-lookup"><span data-stu-id="6a0c4-103">Create a B2B extranet with managed guests</span></span>

<span data-ttu-id="6a0c4-104">È possibile utilizzare la [gestione dei diritti di Azure Active Directory](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview) per creare una rete Extranet B2B per collaborare con un'organizzazione partner che utilizza Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6a0c4-104">You can use [Azure Active Directory Entitlement Management](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview) to create a B2B extranet to collaborate with a partner organization that uses Azure Active Directory.</span></span> <span data-ttu-id="6a0c4-105">Questo consente agli utenti di eseguire la registrazione automatica nel sito o nel team Extranet e di ricevere l'accesso tramite un flusso di lavoro di approvazione.</span><span class="sxs-lookup"><span data-stu-id="6a0c4-105">This allows users to self-enroll in the extranet site or team and receive access via an approval workflow.</span></span>

<span data-ttu-id="6a0c4-106">Con questo metodo di condivisione delle risorse per la collaborazione, l'organizzazione partner può contribuire a mantenere e approvare gli ospiti alla fine, riducendo l'onere per il reparto IT e consentendo ai più familiari del contratto di collaborazione di gestire l'accesso degli utenti.</span><span class="sxs-lookup"><span data-stu-id="6a0c4-106">With this method of sharing resources for collaboration, the partner organization can help maintain and approve the guests on their end, reducing the burden on your IT department and allowing those most familiar with the collaboration agreement to manage user access.</span></span>

<span data-ttu-id="6a0c4-107">In questo articolo vengono illustrati i passaggi per creare un pacchetto di risorse (in questo caso, un sito o un team) che è possibile condividere con un'organizzazione partner tramite un modello di registrazione di accesso self-service.</span><span class="sxs-lookup"><span data-stu-id="6a0c4-107">This article walks through the steps to create a package of resources (in this case, a site or team) that you can share with a partner organization through a self-service access registration model.</span></span> 

<span data-ttu-id="6a0c4-108">Prima di iniziare, creare il sito o il team che si desidera condividere con l'organizzazione partner e abilitarlo per la condivisione degli ospiti.</span><span class="sxs-lookup"><span data-stu-id="6a0c4-108">Before you begin, create the site or team that you want to share with the partner organization and enable it for guest sharing.</span></span> <span data-ttu-id="6a0c4-109">Per ulteriori informazioni, vedere [collaborare con gli utenti di un sito](collaborate-in-site.md) o [collaborare con gli ospiti di un team](collaborate-as-team.md) .</span><span class="sxs-lookup"><span data-stu-id="6a0c4-109">See [Collaborate with guests in a site](collaborate-in-site.md) or [Collaborate with guests in a team](collaborate-as-team.md) for more information.</span></span> <span data-ttu-id="6a0c4-110">È inoltre consigliabile esaminare [creare un ambiente di condivisione Guest sicuro](create-secure-guest-sharing-environment.md) per informazioni sulle funzionalità di sicurezza e conformità che è possibile utilizzare per gestire i criteri di governance durante la collaborazione con gli utenti.</span><span class="sxs-lookup"><span data-stu-id="6a0c4-110">We also recommend that you review [Create a secure guest sharing environment](create-secure-guest-sharing-environment.md) for information about security and compliance features that you can use to help maintain your governance policies when collaborating with guests.</span></span>

## <a name="license-requirements"></a><span data-ttu-id="6a0c4-111">Requisiti di licenza</span><span class="sxs-lookup"><span data-stu-id="6a0c4-111">License requirements</span></span>

<span data-ttu-id="6a0c4-112">L'utilizzo di questa funzionalità richiede una licenza P2 di Azure AD Premium.</span><span class="sxs-lookup"><span data-stu-id="6a0c4-112">Using this feature requires an Azure AD Premium P2 license.</span></span> 

<span data-ttu-id="6a0c4-113">Nubi specializzate, come Azure Germany e Azure China 21Vianet, non sono attualmente disponibili per l'uso.</span><span class="sxs-lookup"><span data-stu-id="6a0c4-113">Specialized clouds, such as Azure Germany and Azure China 21Vianet, are not currently available for use.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="6a0c4-114">Dimostrazione video</span><span class="sxs-lookup"><span data-stu-id="6a0c4-114">Video demonstration</span></span>

<span data-ttu-id="6a0c4-115">In questo video vengono illustrate le procedure descritte in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="6a0c4-115">This video demonstrates the procedures covered in this article.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4wKUj?autoplay=false]

## <a name="connect-the-partner-organization"></a><span data-ttu-id="6a0c4-116">Connettere l'organizzazione partner</span><span class="sxs-lookup"><span data-stu-id="6a0c4-116">Connect the partner organization</span></span>

<span data-ttu-id="6a0c4-117">Per invitare gli ospiti da un'organizzazione partner, è necessario aggiungere il dominio del partner come organizzazione connessa in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6a0c4-117">In order to invite guests from a partner organization, you need to add the partner's domain as a connected organization in Azure Active Directory.</span></span>

<span data-ttu-id="6a0c4-118">Per aggiungere un'organizzazione connessa</span><span class="sxs-lookup"><span data-stu-id="6a0c4-118">To add a connected organization</span></span>
1. <span data-ttu-id="6a0c4-119">In [Azure Active Directory](https://aad.portal.azure.com)fare clic su **governance delle identità**.</span><span class="sxs-lookup"><span data-stu-id="6a0c4-119">In [Azure Active Directory](https://aad.portal.azure.com), click **Identity Governance**.</span></span>
2. <span data-ttu-id="6a0c4-120">Fare clic su **organizzazioni connesse**.</span><span class="sxs-lookup"><span data-stu-id="6a0c4-120">Click **Connected organizations**.</span></span>
4. <span data-ttu-id="6a0c4-121">Fare clic su **Aggiungi organizzazione connessa**.</span><span class="sxs-lookup"><span data-stu-id="6a0c4-121">Click **Add connected organization**.</span></span>
5. <span data-ttu-id="6a0c4-122">Digitare un nome e una descrizione per l'organizzazione, quindi fare clic su **Avanti: directory + dominio**.</span><span class="sxs-lookup"><span data-stu-id="6a0c4-122">Type a name and description for the organization, and then click **Next: Directory + domain**.</span></span>
6. <span data-ttu-id="6a0c4-123">Fare clic su **Aggiungi directory + dominio**.</span><span class="sxs-lookup"><span data-stu-id="6a0c4-123">Click **Add directory + domain**.</span></span>
7. <span data-ttu-id="6a0c4-124">Digitare il dominio per l'organizzazione che si desidera connettere e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="6a0c4-124">Type the domain for the organization that you want to connect, and then click **Add**.</span></span>
8. <span data-ttu-id="6a0c4-125">Fare clic su **Connetti** e quindi su **Avanti: sponsor**.</span><span class="sxs-lookup"><span data-stu-id="6a0c4-125">Click **Connect**, and then click **Next: Sponsors**.</span></span>
9. <span data-ttu-id="6a0c4-126">Aggiungere persone dall'organizzazione o dall'organizzazione a cui si sta effettuando la connessione per gli utenti a cui si desidera approvare l'accesso.</span><span class="sxs-lookup"><span data-stu-id="6a0c4-126">Add people from your organization or the organization that you're connecting to who you want to approve access for guests.</span></span>
10. <span data-ttu-id="6a0c4-127">Fare clic su **Avanti: recensione + crea**.</span><span class="sxs-lookup"><span data-stu-id="6a0c4-127">Click **Next: Review + Create**.</span></span>
11. <span data-ttu-id="6a0c4-128">Esaminare le impostazioni selezionate e quindi fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="6a0c4-128">Review the settings that you've chosen and then click **Create**.</span></span>

    ![Schermata della pagina organizzazioni connesse in Azure Active Directory](../media/identity-governance-connected-organizations.png)

## <a name="choose-the-resources-to-share"></a><span data-ttu-id="6a0c4-130">Scegliere le risorse da condividere</span><span class="sxs-lookup"><span data-stu-id="6a0c4-130">Choose the resources to share</span></span>

<span data-ttu-id="6a0c4-131">Il primo passaggio per la selezione delle risorse da condividere con un'organizzazione partner consiste nel creare un catalogo che li contenga.</span><span class="sxs-lookup"><span data-stu-id="6a0c4-131">The first step in selecting resources to share with a partner organization is to create a catalog to contain them.</span></span>

<span data-ttu-id="6a0c4-132">Per creare un catalogo</span><span class="sxs-lookup"><span data-stu-id="6a0c4-132">To create a catalog</span></span>
1. <span data-ttu-id="6a0c4-133">In [Azure Active Directory](https://aad.portal.azure.com)fare clic su **governance delle identità**.</span><span class="sxs-lookup"><span data-stu-id="6a0c4-133">In [Azure Active Directory](https://aad.portal.azure.com), click **Identity Governance**.</span></span>
2. <span data-ttu-id="6a0c4-134">Fare clic su **cataloghi**.</span><span class="sxs-lookup"><span data-stu-id="6a0c4-134">Click **Catalogs**.</span></span>
3. <span data-ttu-id="6a0c4-135">Fare clic su **nuovo catalogo**.</span><span class="sxs-lookup"><span data-stu-id="6a0c4-135">Click **New catalog**.</span></span>
4. <span data-ttu-id="6a0c4-136">Digitare un nome e una descrizione per il catalogo e assicurarsi che sia **abilitato** sia abilitato **per gli utenti esterni** siano entrambi impostati su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="6a0c4-136">Type a name and description for the catalog and ensure that **Enabled** and **Enabled for external users** are both set to **Yes**.</span></span>
5. <span data-ttu-id="6a0c4-137">Fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="6a0c4-137">Click **Create**.</span></span>

   ![Schermata della pagina cataloghi in Azure Active Directory Identity governance](../media/identity-governance-catalogs.png)

<span data-ttu-id="6a0c4-139">Dopo aver creato il catalogo, è necessario aggiungere il sito o il team di SharePoint che si desidera condividere con l'organizzazione partner.</span><span class="sxs-lookup"><span data-stu-id="6a0c4-139">Once the catalog has been created, you add the SharePoint site or team that you want to share with the partner organization.</span></span>

<span data-ttu-id="6a0c4-140">Per aggiungere risorse a un catalogo</span><span class="sxs-lookup"><span data-stu-id="6a0c4-140">To add resources to a catalog</span></span>
1. <span data-ttu-id="6a0c4-141">In Azure AD Identity governance fare clic su **cataloghi** e quindi fare clic sul catalogo in cui si desidera aggiungere risorse.</span><span class="sxs-lookup"><span data-stu-id="6a0c4-141">In Azure AD Identity Governance, click **Catalogs**, and then click the catalog where you want to add resources.</span></span>
2. <span data-ttu-id="6a0c4-142">Fare clic su **risorse** e quindi su **Aggiungi risorse**.</span><span class="sxs-lookup"><span data-stu-id="6a0c4-142">Click **Resources** and then click **Add resources**.</span></span>
3. <span data-ttu-id="6a0c4-143">Selezionare i team o i siti di SharePoint che si desidera includere nella rete Extranet, quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="6a0c4-143">Select the teams or SharePoint sites that you want to include in your extranet, and then click **Add**.</span></span>

   ![Schermata della pagina risorse catalogo in Azure Active Directory Identity governance](../media/identity-governance-catalog-resource.png)

<span data-ttu-id="6a0c4-145">Dopo aver definito le risorse che si desidera condividere, il passaggio successivo consiste nel creare un pacchetto di Access, che definisce il tipo di accesso che gli utenti partner sono concessi e il processo di approvazione per i nuovi utenti partner che richiedono l'accesso.</span><span class="sxs-lookup"><span data-stu-id="6a0c4-145">Once you've defined the resources that you want to share, the next step is to create an access package, which defines the type of access that partner users are granted and the approval process for new partner users requesting access.</span></span>

<span data-ttu-id="6a0c4-146">Per creare un pacchetto di Access</span><span class="sxs-lookup"><span data-stu-id="6a0c4-146">To create an access package</span></span>
1. <span data-ttu-id="6a0c4-147">In Azure AD Identity governance, fare clic su **cataloghi**, quindi fare clic sul catalogo in cui si desidera creare un pacchetto di accesso.</span><span class="sxs-lookup"><span data-stu-id="6a0c4-147">In Azure AD Identity Governance, click **Catalogs**, and then click the catalog where you want to create an access package.</span></span>
2. <span data-ttu-id="6a0c4-148">Fare clic su **Access** Packages, quindi fare clic su **nuovo pacchetto di accesso**.</span><span class="sxs-lookup"><span data-stu-id="6a0c4-148">Click **Access packages**, and then click **New access package**.</span></span>
3. <span data-ttu-id="6a0c4-149">Digitare un nome e una descrizione per il pacchetto di accesso e quindi fare clic su **Avanti: ruoli risorse**.</span><span class="sxs-lookup"><span data-stu-id="6a0c4-149">Type a name and description for the access package, and then click **Next: Resource roles**.</span></span>
4. <span data-ttu-id="6a0c4-150">Scegliere le risorse del catalogo che si desidera utilizzare per l'Extranet.</span><span class="sxs-lookup"><span data-stu-id="6a0c4-150">Choose the resources from the catalog that you want to use for your extranet.</span></span>
5. <span data-ttu-id="6a0c4-151">Per ogni risorsa, nella colonna **ruolo** scegliere il ruolo utente che si desidera concedere agli utenti che utilizzano la rete Extranet.</span><span class="sxs-lookup"><span data-stu-id="6a0c4-151">For each resource, in the **Role** column, choose the user role you want to grant to the guests who use the extranet.</span></span>
6. <span data-ttu-id="6a0c4-152">Fare clic su **Avanti: richieste**.</span><span class="sxs-lookup"><span data-stu-id="6a0c4-152">Click **Next: Requests**.</span></span>
7. <span data-ttu-id="6a0c4-153">In **utenti che possono richiedere l'accesso**, scegliere **per gli utenti non presenti nella directory**.</span><span class="sxs-lookup"><span data-stu-id="6a0c4-153">Under **Users who can request access**, choose **For users not in your directory**.</span></span>
8. <span data-ttu-id="6a0c4-154">Verificare che l'opzione **specifiche organizzazioni connesse** sia selezionata e quindi fare clic su **Aggiungi directory**.</span><span class="sxs-lookup"><span data-stu-id="6a0c4-154">Ensure that the **Specific connected organizations** option is selected, and then click **Add directories**.</span></span>
9. <span data-ttu-id="6a0c4-155">Scegliere l'organizzazione connessa aggiunta in precedenza e quindi fare clic su **Seleziona**</span><span class="sxs-lookup"><span data-stu-id="6a0c4-155">Choose the connected organization that you add earlier, and then click **Select**</span></span>
10. <span data-ttu-id="6a0c4-156">In **approvazione**, scegliere **Sì** per **richiedere l'approvazione**.</span><span class="sxs-lookup"><span data-stu-id="6a0c4-156">Under **Approval**, choose **Yes** for **Require approval**.</span></span>
11. <span data-ttu-id="6a0c4-157">In **primo responsabile approvazione** scegliere uno dei garanti aggiunti in precedenza o scegliere un utente specifico.</span><span class="sxs-lookup"><span data-stu-id="6a0c4-157">Under **First approver**, choose one of the sponsors that you added earlier or choose a specific user.</span></span>
12. <span data-ttu-id="6a0c4-158">Fare clic su **Aggiungi fallback** e selezionare un responsabile approvazione fallback.</span><span class="sxs-lookup"><span data-stu-id="6a0c4-158">Click **Add fallback** and select a fallback approver.</span></span>
13. <span data-ttu-id="6a0c4-159">In **attiva**, scegliere **Sì**.</span><span class="sxs-lookup"><span data-stu-id="6a0c4-159">Under **Enable**, choose **Yes**.</span></span>
14. <span data-ttu-id="6a0c4-160">Fare clic su **Avanti: ciclo** di vita.</span><span class="sxs-lookup"><span data-stu-id="6a0c4-160">Click **Next: Lifecycle**.</span></span>
15. <span data-ttu-id="6a0c4-161">Scegliere le impostazioni di scadenza e revisione di Access che si desidera utilizzare e quindi fare clic su **Avanti: recensione + crea**.</span><span class="sxs-lookup"><span data-stu-id="6a0c4-161">Choose the expiration and access review settings that you want to use, and then click **Next: Review + Create**.</span></span>
16. <span data-ttu-id="6a0c4-162">Esaminare le impostazioni, quindi fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="6a0c4-162">Review your settings, and then click **Create**.</span></span>

    ![Screenshot della schermata Access Packages in Azure Active Directory Identity governance](../media/identity-governance-access-packages.png)

<span data-ttu-id="6a0c4-164">Se si è in partnership con un'organizzazione di grandi dimensioni, è possibile che si desideri nascondere il pacchetto di accesso.</span><span class="sxs-lookup"><span data-stu-id="6a0c4-164">If you're partnering with a large organization, you may want to hide the access package.</span></span> <span data-ttu-id="6a0c4-165">Se il pacchetto è nascosto, gli utenti dell'organizzazione partner non vedranno il pacchetto sul proprio portale di *accesso* .</span><span class="sxs-lookup"><span data-stu-id="6a0c4-165">If the package is hidden, then users in the partner organization will not see the package on their *My Access* portal.</span></span> <span data-ttu-id="6a0c4-166">Al contrario, è necessario inviare un collegamento diretto per iscriversi al pacchetto.</span><span class="sxs-lookup"><span data-stu-id="6a0c4-166">Instead, they must be sent a direct link to sign up for the package.</span></span> <span data-ttu-id="6a0c4-167">Se si nasconde il pacchetto di Access, è possibile ridurre il numero di richieste di accesso inappropriate e consentire anche di mantenere i pacchetti di accesso disponibili organizzati nel portale dell'organizzazione partner.</span><span class="sxs-lookup"><span data-stu-id="6a0c4-167">Hiding the access package can reduce the number of inappropriate access requests and can also help keep available access packages organized in the partner organization's portal.</span></span>

<span data-ttu-id="6a0c4-168">Per impostare un pacchetto di accesso su nascosto</span><span class="sxs-lookup"><span data-stu-id="6a0c4-168">To set an access package to hidden</span></span>
1. <span data-ttu-id="6a0c4-169">In Azure AD Identity governance, fare clic su **Access** Packages, quindi fare clic sul pacchetto di accesso.</span><span class="sxs-lookup"><span data-stu-id="6a0c4-169">In Azure AD Identity Governance, click **Access packages**, and then click your access package.</span></span>
2. <span data-ttu-id="6a0c4-170">Nella pagina **Panoramica** fare clic su **modifica**.</span><span class="sxs-lookup"><span data-stu-id="6a0c4-170">On the **Overview** page, click **Edit**.</span></span>
3. <span data-ttu-id="6a0c4-171">In **Proprietà**, scegliere **Sì** per **nascosto**, quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="6a0c4-171">Under **Properties**, choose **Yes** for **Hidden**, and then click **Save**.</span></span>

   ![Schermata di una finestra di modifica delle proprietà di un pacchetto di Access](../media/identity-governance-access-package-hidden.png)

## <a name="invite-partner-users"></a><span data-ttu-id="6a0c4-173">Invitare gli utenti partner</span><span class="sxs-lookup"><span data-stu-id="6a0c4-173">Invite partner users</span></span>

<span data-ttu-id="6a0c4-174">Se si imposta il pacchetto di accesso su nascosto, è necessario inviare un collegamento diretto all'organizzazione partner in modo che possano richiedere l'accesso al sito o al team.</span><span class="sxs-lookup"><span data-stu-id="6a0c4-174">If you set the access package to hidden, you need to send a direct link to the partner organization so that they can request access to your site or team.</span></span>

<span data-ttu-id="6a0c4-175">Per trovare il collegamento al portale di accesso</span><span class="sxs-lookup"><span data-stu-id="6a0c4-175">To find the access portal link</span></span>
1. <span data-ttu-id="6a0c4-176">In Azure AD Identity governance, fare clic su **Access** Packages, quindi fare clic sul pacchetto di accesso.</span><span class="sxs-lookup"><span data-stu-id="6a0c4-176">In Azure AD Identity Governance, click **Access packages**, and then click your access package.</span></span>
2. <span data-ttu-id="6a0c4-177">Nella pagina **Panoramica** fare clic su **copia nel** collegamento degli Appunti per il **collegamento portale My Access**.</span><span class="sxs-lookup"><span data-stu-id="6a0c4-177">On the **Overview** page, click **Copy to clipboard** link for the **My Access portal link**.</span></span>

   ![Schermata delle proprietà del pacchetto di accesso con il collegamento al portale di accesso](../media/identity-governance-access-portal-link.png)

<span data-ttu-id="6a0c4-179">Dopo aver copiato il collegamento, è possibile condividerlo con il contatto nell'organizzazione partner e inviarlo agli utenti del team di collaborazione.</span><span class="sxs-lookup"><span data-stu-id="6a0c4-179">Once you have copied the link, you can share it with your contact at the partner organization and they can send it to the users on their collaboration team.</span></span>

## <a name="see-also"></a><span data-ttu-id="6a0c4-180">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6a0c4-180">See Also</span></span>

[<span data-ttu-id="6a0c4-181">Creare un ambiente di condivisione guest sicuro</span><span class="sxs-lookup"><span data-stu-id="6a0c4-181">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)
