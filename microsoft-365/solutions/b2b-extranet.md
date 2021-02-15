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
description: Informazioni su come creare un sito Extranet B2B o un team con utenti guest gestiti da un'organizzazione partner.
ms.openlocfilehash: cfb7cc4310cb83f9ce7761c95f021724b7d75faf
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613597"
---
# <a name="create-a-b2b-extranet-with-managed-guests"></a><span data-ttu-id="185c7-103">Creare una Extranet B2B con guest gestiti.</span><span class="sxs-lookup"><span data-stu-id="185c7-103">Create a B2B extranet with managed guests</span></span>

<span data-ttu-id="185c7-104">È possibile utilizzare [Azure Active Directory Entitlement Management](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview) per creare una extranet B2B per collaborare con un'organizzazione partner che usa Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="185c7-104">You can use [Azure Active Directory Entitlement Management](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview) to create a B2B extranet to collaborate with a partner organization that uses Azure Active Directory.</span></span> <span data-ttu-id="185c7-105">In questo modo gli utenti possono registrarsi autonomamente nel sito Extranet o nel team e ricevere l'accesso tramite un flusso di lavoro di approvazione.</span><span class="sxs-lookup"><span data-stu-id="185c7-105">This allows users to self-enroll in the extranet site or team and receive access via an approval workflow.</span></span>

<span data-ttu-id="185c7-106">Con questo metodo di condivisione delle risorse per la collaborazione, l'organizzazione partner può aiutare a mantenere e approvare gli utenti guest, riducendo il carico sul reparto IT e consentendo ai più familiari con il contratto di collaborazione di gestire l'accesso degli utenti.</span><span class="sxs-lookup"><span data-stu-id="185c7-106">With this method of sharing resources for collaboration, the partner organization can help maintain and approve the guests on their end, reducing the burden on your IT department and allowing those most familiar with the collaboration agreement to manage user access.</span></span>

<span data-ttu-id="185c7-107">In questo articolo viene illustrata la procedura per creare un pacchetto di risorse (in questo caso, un sito o un team) che è possibile condividere con un'organizzazione partner tramite un modello di registrazione dell'accesso in modalità self-service.</span><span class="sxs-lookup"><span data-stu-id="185c7-107">This article walks through the steps to create a package of resources (in this case, a site or team) that you can share with a partner organization through a self-service access registration model.</span></span> 

<span data-ttu-id="185c7-108">Prima di iniziare, creare il sito o il team che si desidera condividere con l'organizzazione partner e abilitarlo per la condivisione guest.</span><span class="sxs-lookup"><span data-stu-id="185c7-108">Before you begin, create the site or team that you want to share with the partner organization and enable it for guest sharing.</span></span> <span data-ttu-id="185c7-109">Per [ulteriori informazioni, vedere](collaborate-in-site.md) Collaborare con gli utenti guest in un sito o Collaborare con gli utenti guest in un [team.](collaborate-as-team.md)</span><span class="sxs-lookup"><span data-stu-id="185c7-109">See [Collaborate with guests in a site](collaborate-in-site.md) or [Collaborate with guests in a team](collaborate-as-team.md) for more information.</span></span> <span data-ttu-id="185c7-110">È inoltre consigliabile consultare Creare un ambiente di condivisione [guest](create-secure-guest-sharing-environment.md) sicuro per informazioni sulle funzionalità di sicurezza e conformità che è possibile utilizzare per mantenere i criteri di governance quando si collabora con gli utenti guest.</span><span class="sxs-lookup"><span data-stu-id="185c7-110">We also recommend that you review [Create a secure guest sharing environment](create-secure-guest-sharing-environment.md) for information about security and compliance features that you can use to help maintain your governance policies when collaborating with guests.</span></span>

## <a name="license-requirements"></a><span data-ttu-id="185c7-111">Requisiti di licenza</span><span class="sxs-lookup"><span data-stu-id="185c7-111">License requirements</span></span>

<span data-ttu-id="185c7-112">L'uso di questa funzionalità richiede una licenza di Azure AD Premium P2.</span><span class="sxs-lookup"><span data-stu-id="185c7-112">Using this feature requires an Azure AD Premium P2 license.</span></span> 

<span data-ttu-id="185c7-113">I cloud specializzati, come Azure Germania e Azure Cina 21Vianet, non sono attualmente disponibili per l'uso.</span><span class="sxs-lookup"><span data-stu-id="185c7-113">Specialized clouds, such as Azure Germany and Azure China 21Vianet, are not currently available for use.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="185c7-114">Dimostrazione video</span><span class="sxs-lookup"><span data-stu-id="185c7-114">Video demonstration</span></span>

<span data-ttu-id="185c7-115">In questo video vengono illustrate le procedure descritte in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="185c7-115">This video demonstrates the procedures covered in this article.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4wKUj?autoplay=false]

## <a name="connect-the-partner-organization"></a><span data-ttu-id="185c7-116">Connettere l'organizzazione partner</span><span class="sxs-lookup"><span data-stu-id="185c7-116">Connect the partner organization</span></span>

<span data-ttu-id="185c7-117">Per invitare guest da un'organizzazione partner, è necessario aggiungere il dominio del partner come organizzazione connessa in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="185c7-117">In order to invite guests from a partner organization, you need to add the partner's domain as a connected organization in Azure Active Directory.</span></span>

<span data-ttu-id="185c7-118">Per aggiungere un'organizzazione connessa</span><span class="sxs-lookup"><span data-stu-id="185c7-118">To add a connected organization</span></span>
1. <span data-ttu-id="185c7-119">In [Azure Active Directory,](https://aad.portal.azure.com)fare clic **su Identity Governance.**</span><span class="sxs-lookup"><span data-stu-id="185c7-119">In [Azure Active Directory](https://aad.portal.azure.com), click **Identity Governance**.</span></span>
2. <span data-ttu-id="185c7-120">Fare **clic su Organizzazioni connesse.**</span><span class="sxs-lookup"><span data-stu-id="185c7-120">Click **Connected organizations**.</span></span>
4. <span data-ttu-id="185c7-121">Fare **clic su Aggiungi organizzazione connessa.**</span><span class="sxs-lookup"><span data-stu-id="185c7-121">Click **Add connected organization**.</span></span>
5. <span data-ttu-id="185c7-122">Digitare un nome e una descrizione per l'organizzazione e quindi fare clic su **Avanti: Directory + dominio.**</span><span class="sxs-lookup"><span data-stu-id="185c7-122">Type a name and description for the organization, and then click **Next: Directory + domain**.</span></span>
6. <span data-ttu-id="185c7-123">Fare **clic su Aggiungi directory + dominio.**</span><span class="sxs-lookup"><span data-stu-id="185c7-123">Click **Add directory + domain**.</span></span>
7. <span data-ttu-id="185c7-124">Digitare il dominio dell'organizzazione che si desidera connettere e quindi fare clic su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="185c7-124">Type the domain for the organization that you want to connect, and then click **Add**.</span></span>
8. <span data-ttu-id="185c7-125">Fare **clic su** Connetti e quindi su **Avanti: Sponsor.**</span><span class="sxs-lookup"><span data-stu-id="185c7-125">Click **Connect**, and then click **Next: Sponsors**.</span></span>
9. <span data-ttu-id="185c7-126">Aggiungere persone dell'organizzazione o dell'organizzazione a cui ci si connette a chi si desidera approvare l'accesso per gli utenti guest.</span><span class="sxs-lookup"><span data-stu-id="185c7-126">Add people from your organization or the organization that you're connecting to who you want to approve access for guests.</span></span>
10. <span data-ttu-id="185c7-127">Fare **clic su Avanti: Rivedi + Crea.**</span><span class="sxs-lookup"><span data-stu-id="185c7-127">Click **Next: Review + Create**.</span></span>
11. <span data-ttu-id="185c7-128">Rivedere le impostazioni scelte e quindi fare clic su **Crea.**</span><span class="sxs-lookup"><span data-stu-id="185c7-128">Review the settings that you've chosen and then click **Create**.</span></span>

    ![Screenshot della pagina delle organizzazioni connesse in Azure Active Directory](../media/identity-governance-connected-organizations.png)

## <a name="choose-the-resources-to-share"></a><span data-ttu-id="185c7-130">Scegliere le risorse da condividere</span><span class="sxs-lookup"><span data-stu-id="185c7-130">Choose the resources to share</span></span>

<span data-ttu-id="185c7-131">Il primo passaggio per la selezione delle risorse da condividere con un'organizzazione partner consiste nel creare un catalogo in cui contenerle.</span><span class="sxs-lookup"><span data-stu-id="185c7-131">The first step in selecting resources to share with a partner organization is to create a catalog to contain them.</span></span>

<span data-ttu-id="185c7-132">Per creare un catalogo</span><span class="sxs-lookup"><span data-stu-id="185c7-132">To create a catalog</span></span>
1. <span data-ttu-id="185c7-133">In [Azure Active Directory,](https://aad.portal.azure.com)fare clic **su Identity Governance.**</span><span class="sxs-lookup"><span data-stu-id="185c7-133">In [Azure Active Directory](https://aad.portal.azure.com), click **Identity Governance**.</span></span>
2. <span data-ttu-id="185c7-134">Fare **clic su Cataloghi.**</span><span class="sxs-lookup"><span data-stu-id="185c7-134">Click **Catalogs**.</span></span>
3. <span data-ttu-id="185c7-135">Fare **clic su Nuovo catalogo.**</span><span class="sxs-lookup"><span data-stu-id="185c7-135">Click **New catalog**.</span></span>
4. <span data-ttu-id="185c7-136">Digitare un nome e una descrizione per il catalogo e assicurarsi che sia abilitato che abilitato per gli utenti **esterni** sia impostato su **Sì.** </span><span class="sxs-lookup"><span data-stu-id="185c7-136">Type a name and description for the catalog and ensure that **Enabled** and **Enabled for external users** are both set to **Yes**.</span></span>
5. <span data-ttu-id="185c7-137">Fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="185c7-137">Click **Create**.</span></span>

   ![Screenshot della pagina dei cataloghi in Azure Active Directory Identity Governance](../media/identity-governance-catalogs.png)

<span data-ttu-id="185c7-139">Dopo aver creato il catalogo, aggiungere il sito o il team di SharePoint che si desidera condividere con l'organizzazione partner.</span><span class="sxs-lookup"><span data-stu-id="185c7-139">Once the catalog has been created, you add the SharePoint site or team that you want to share with the partner organization.</span></span>

<span data-ttu-id="185c7-140">Per aggiungere risorse a un catalogo</span><span class="sxs-lookup"><span data-stu-id="185c7-140">To add resources to a catalog</span></span>
1. <span data-ttu-id="185c7-141">In Azure AD Identity Governance, fare clic **su Cataloghi** e quindi sul catalogo in cui si desidera aggiungere risorse.</span><span class="sxs-lookup"><span data-stu-id="185c7-141">In Azure AD Identity Governance, click **Catalogs**, and then click the catalog where you want to add resources.</span></span>
2. <span data-ttu-id="185c7-142">Fare **clic su** Risorse e quindi su Aggiungi **risorse.**</span><span class="sxs-lookup"><span data-stu-id="185c7-142">Click **Resources** and then click **Add resources**.</span></span>
3. <span data-ttu-id="185c7-143">Selezionare i team o i siti di SharePoint che si desidera includere nella rete Extranet e quindi fare clic su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="185c7-143">Select the teams or SharePoint sites that you want to include in your extranet, and then click **Add**.</span></span>

   ![Screenshot della pagina delle risorse del catalogo in Azure Active Directory Identity Governance](../media/identity-governance-catalog-resource.png)

<span data-ttu-id="185c7-145">Dopo aver definito le risorse che si desidera condividere, il passaggio successivo consiste nel creare un pacchetto di accesso, che definisce il tipo di accesso concesso agli utenti partner e il processo di approvazione per i nuovi utenti partner che richiedono l'accesso.</span><span class="sxs-lookup"><span data-stu-id="185c7-145">Once you've defined the resources that you want to share, the next step is to create an access package, which defines the type of access that partner users are granted and the approval process for new partner users requesting access.</span></span>

<span data-ttu-id="185c7-146">Per creare un pacchetto di accesso</span><span class="sxs-lookup"><span data-stu-id="185c7-146">To create an access package</span></span>
1. <span data-ttu-id="185c7-147">In Azure AD Identity Governance, fare clic **su Cataloghi** e quindi sul catalogo in cui si desidera creare un pacchetto di accesso.</span><span class="sxs-lookup"><span data-stu-id="185c7-147">In Azure AD Identity Governance, click **Catalogs**, and then click the catalog where you want to create an access package.</span></span>
2. <span data-ttu-id="185c7-148">Fare **clic su Pacchetti di** Access e quindi su Nuovo pacchetto di **accesso.**</span><span class="sxs-lookup"><span data-stu-id="185c7-148">Click **Access packages**, and then click **New access package**.</span></span>
3. <span data-ttu-id="185c7-149">Digitare un nome e una descrizione per il pacchetto di accesso e quindi fare clic su **Avanti: Ruoli risorsa.**</span><span class="sxs-lookup"><span data-stu-id="185c7-149">Type a name and description for the access package, and then click **Next: Resource roles**.</span></span>
4. <span data-ttu-id="185c7-150">Scegliere le risorse del catalogo che si desidera utilizzare per la rete Extranet.</span><span class="sxs-lookup"><span data-stu-id="185c7-150">Choose the resources from the catalog that you want to use for your extranet.</span></span>
5. <span data-ttu-id="185c7-151">Per ogni risorsa, nella **colonna Ruolo** scegliere il ruolo utente che si desidera concedere agli utenti guest che utilizzano la extranet.</span><span class="sxs-lookup"><span data-stu-id="185c7-151">For each resource, in the **Role** column, choose the user role you want to grant to the guests who use the extranet.</span></span>
6. <span data-ttu-id="185c7-152">Fare **clic su Avanti: Richieste.**</span><span class="sxs-lookup"><span data-stu-id="185c7-152">Click **Next: Requests**.</span></span>
7. <span data-ttu-id="185c7-153">In **Utenti che possono richiedere l'accesso** scegliere Per gli utenti non presenti nella **directory.**</span><span class="sxs-lookup"><span data-stu-id="185c7-153">Under **Users who can request access**, choose **For users not in your directory**.</span></span>
8. <span data-ttu-id="185c7-154">Verificare che **l'opzione Organizzazioni connesse** specifiche sia selezionata e quindi fare clic su Aggiungi **directory.**</span><span class="sxs-lookup"><span data-stu-id="185c7-154">Ensure that the **Specific connected organizations** option is selected, and then click **Add directories**.</span></span>
9. <span data-ttu-id="185c7-155">Scegliere l'organizzazione connessa aggiunta in precedenza e quindi fare clic su **Seleziona**</span><span class="sxs-lookup"><span data-stu-id="185c7-155">Choose the connected organization that you add earlier, and then click **Select**</span></span>
10. <span data-ttu-id="185c7-156">In **Approvazione** scegliere **Sì** per **Richiedi approvazione.**</span><span class="sxs-lookup"><span data-stu-id="185c7-156">Under **Approval**, choose **Yes** for **Require approval**.</span></span>
11. <span data-ttu-id="185c7-157">In **Primo responsabile approvazione** scegliere uno degli sponsor aggiunti in precedenza oppure scegliere un utente specifico.</span><span class="sxs-lookup"><span data-stu-id="185c7-157">Under **First approver**, choose one of the sponsors that you added earlier or choose a specific user.</span></span>
12. <span data-ttu-id="185c7-158">Fare **clic su Aggiungi fallback** e selezionare un responsabile approvazione di fallback.</span><span class="sxs-lookup"><span data-stu-id="185c7-158">Click **Add fallback** and select a fallback approver.</span></span>
13. <span data-ttu-id="185c7-159">In **Abilita** scegliere **Sì.**</span><span class="sxs-lookup"><span data-stu-id="185c7-159">Under **Enable**, choose **Yes**.</span></span>
14. <span data-ttu-id="185c7-160">Fare **clic su Avanti: Ciclo di vita.**</span><span class="sxs-lookup"><span data-stu-id="185c7-160">Click **Next: Lifecycle**.</span></span>
15. <span data-ttu-id="185c7-161">Scegliere le impostazioni di scadenza e verifica di accesso che si desidera utilizzare e quindi fare clic su **Avanti: Revisione + Crea.**</span><span class="sxs-lookup"><span data-stu-id="185c7-161">Choose the expiration and access review settings that you want to use, and then click **Next: Review + Create**.</span></span>
16. <span data-ttu-id="185c7-162">Rivedere le impostazioni e quindi fare clic su **Crea.**</span><span class="sxs-lookup"><span data-stu-id="185c7-162">Review your settings, and then click **Create**.</span></span>

    ![Screenshot della schermata dei pacchetti di accesso in Azure Active Directory Identity Governance](../media/identity-governance-access-packages.png)

<span data-ttu-id="185c7-164">Se stai collaborando con un'organizzazione di grandi dimensioni, puoi nascondere il pacchetto di accesso.</span><span class="sxs-lookup"><span data-stu-id="185c7-164">If you're partnering with a large organization, you may want to hide the access package.</span></span> <span data-ttu-id="185c7-165">Se il pacchetto è nascosto, gli utenti dell'organizzazione partner non potranno vedere il pacchetto nel portale *Di accesso.*</span><span class="sxs-lookup"><span data-stu-id="185c7-165">If the package is hidden, then users in the partner organization will not see the package on their *My Access* portal.</span></span> <span data-ttu-id="185c7-166">Al contrario, devono essere inviati un collegamento diretto per iscriversi al pacchetto.</span><span class="sxs-lookup"><span data-stu-id="185c7-166">Instead, they must be sent a direct link to sign up for the package.</span></span> <span data-ttu-id="185c7-167">Nascondere il pacchetto di accesso può ridurre il numero di richieste di accesso inappropriato e può anche contribuire a mantenere organizzati i pacchetti di accesso disponibili nel portale dell'organizzazione partner.</span><span class="sxs-lookup"><span data-stu-id="185c7-167">Hiding the access package can reduce the number of inappropriate access requests and can also help keep available access packages organized in the partner organization's portal.</span></span>

<span data-ttu-id="185c7-168">Per impostare un pacchetto di accesso come nascosto</span><span class="sxs-lookup"><span data-stu-id="185c7-168">To set an access package to hidden</span></span>
1. <span data-ttu-id="185c7-169">In Azure AD Identity Governance, fare clic **su Pacchetti di accesso** e quindi fare clic sul pacchetto di accesso.</span><span class="sxs-lookup"><span data-stu-id="185c7-169">In Azure AD Identity Governance, click **Access packages**, and then click your access package.</span></span>
2. <span data-ttu-id="185c7-170">Nella pagina **Panoramica** fare clic su **Modifica.**</span><span class="sxs-lookup"><span data-stu-id="185c7-170">On the **Overview** page, click **Edit**.</span></span>
3. <span data-ttu-id="185c7-171">In **Proprietà** scegliere **Sì** per **Nascosto** e quindi fare clic su **Salva.**</span><span class="sxs-lookup"><span data-stu-id="185c7-171">Under **Properties**, choose **Yes** for **Hidden**, and then click **Save**.</span></span>

   ![Screenshot of an edit access package properties screen](../media/identity-governance-access-package-hidden.png)

## <a name="invite-partner-users"></a><span data-ttu-id="185c7-173">Invitare utenti partner</span><span class="sxs-lookup"><span data-stu-id="185c7-173">Invite partner users</span></span>

<span data-ttu-id="185c7-174">Se si imposta il pacchetto di accesso su nascosto, è necessario inviare un collegamento diretto all'organizzazione partner in modo che possa richiedere l'accesso al sito o al team.</span><span class="sxs-lookup"><span data-stu-id="185c7-174">If you set the access package to hidden, you need to send a direct link to the partner organization so that they can request access to your site or team.</span></span>

<span data-ttu-id="185c7-175">Per trovare il collegamento al portale di accesso</span><span class="sxs-lookup"><span data-stu-id="185c7-175">To find the access portal link</span></span>
1. <span data-ttu-id="185c7-176">In Azure AD Identity Governance, fare clic **su Pacchetti di accesso** e quindi fare clic sul pacchetto di accesso.</span><span class="sxs-lookup"><span data-stu-id="185c7-176">In Azure AD Identity Governance, click **Access packages**, and then click your access package.</span></span>
2. <span data-ttu-id="185c7-177">Nella pagina **Panoramica** fare clic sul **collegamento Copia negli Appunti** per il collegamento al portale di My **Access.**</span><span class="sxs-lookup"><span data-stu-id="185c7-177">On the **Overview** page, click **Copy to clipboard** link for the **My Access portal link**.</span></span>

   ![Screenshot of access package properties with access portal link](../media/identity-governance-access-portal-link.png)

<span data-ttu-id="185c7-179">Dopo aver copiato il collegamento, è possibile condividerlo con il contatto nell'organizzazione partner e inviarlo agli utenti del team di collaborazione.</span><span class="sxs-lookup"><span data-stu-id="185c7-179">Once you have copied the link, you can share it with your contact at the partner organization and they can send it to the users on their collaboration team.</span></span>

## <a name="see-also"></a><span data-ttu-id="185c7-180">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="185c7-180">See Also</span></span>

[<span data-ttu-id="185c7-181">Creare un ambiente di condivisione guest sicuro</span><span class="sxs-lookup"><span data-stu-id="185c7-181">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)
