---
title: Passaggio 1. Il Microsoft 365 per i tenant aziendali
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
- tenant-management
- m365solution-scenario
ms.custom:
- Ent_Solutions
description: Distribuire e gestire tenant singoli o Microsoft 365, con opzioni per posizioni multi-geografiche e in movimento.
ms.openlocfilehash: 4d9bd685fce6fb2f11b8e17bebae6460e0c10bd2
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406385"
---
# <a name="step-1-your-microsoft-365-for-enterprise-tenants"></a><span data-ttu-id="84406-104">Passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="84406-104">Step 1.</span></span> <span data-ttu-id="84406-105">Il Microsoft 365 per i tenant aziendali</span><span class="sxs-lookup"><span data-stu-id="84406-105">Your Microsoft 365 for enterprise tenants</span></span>

<span data-ttu-id="84406-106">Una delle prime decisioni del tenant è il numero di utenti.</span><span class="sxs-lookup"><span data-stu-id="84406-106">One of your first tenant decisions is how many to have.</span></span> <span data-ttu-id="84406-107">Ogni Microsoft 365 tenant è distinto, univoco e separato da tutti gli Microsoft 365 tenant.</span><span class="sxs-lookup"><span data-stu-id="84406-107">Each Microsoft 365 tenant is distinct, unique, and separate from all other Microsoft 365 tenants.</span></span> <span data-ttu-id="84406-108">Il tenant di Azure AD corrispondente è anche distinto, univoco e separato da tutti gli Microsoft 365 tenant.</span><span class="sxs-lookup"><span data-stu-id="84406-108">It’s corresponding Azure AD tenant is also distinct, unique, and separate from all other Microsoft 365 tenants.</span></span>

## <a name="single-tenant"></a><span data-ttu-id="84406-109">Tenant singolo</span><span class="sxs-lookup"><span data-stu-id="84406-109">Single tenant</span></span>
<span data-ttu-id="84406-110">La presenza di un singolo tenant semplifica molti aspetti dell'uso delle Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="84406-110">Having a single tenant simplifies many aspects of your organization’s use of Microsoft 365.</span></span> <span data-ttu-id="84406-111">Un singolo tenant indica un singolo tenant di Azure AD con un singolo set di account, gruppi e criteri.</span><span class="sxs-lookup"><span data-stu-id="84406-111">A single tenant means a single Azure AD tenant with a single set of accounts, groups, and policies.</span></span> <span data-ttu-id="84406-112">Le autorizzazioni e la condivisione delle risorse nell'organizzazione possono essere eseguite tramite questo provider di identità centrale.</span><span class="sxs-lookup"><span data-stu-id="84406-112">Permissions and sharing of resources across your organization can be done through this central identity provider.</span></span>

<span data-ttu-id="84406-113">Un singolo tenant offre agli utenti l'esperienza di collaborazione e produttività più ricca di funzionalità e semplificata.</span><span class="sxs-lookup"><span data-stu-id="84406-113">A single tenant provides the most feature-rich and simplified collaboration and productivity experience for your users.</span></span>

<span data-ttu-id="84406-114">Ecco un esempio che mostra la posizione predefinita e il tenant di Azure AD di un tenant Microsoft 365 locale.</span><span class="sxs-lookup"><span data-stu-id="84406-114">Here is an example showing the default location and Azure AD tenant of a Microsoft 365 tenant.</span></span>

![Un singolo tenant Microsoft 365 con il tenant di Azure AD](../media/tenant-management-overview/tenant-management-example-tenant.png)

## <a name="multiple-tenants"></a><span data-ttu-id="84406-116">Più tenant</span><span class="sxs-lookup"><span data-stu-id="84406-116">Multiple tenants</span></span>

<span data-ttu-id="84406-117">Esistono molti motivi per cui l'organizzazione potrebbe avere più tenant:</span><span class="sxs-lookup"><span data-stu-id="84406-117">There are many reasons why your organization could have multiple tenants:</span></span>

- <span data-ttu-id="84406-118">Isolamento amministrativo</span><span class="sxs-lookup"><span data-stu-id="84406-118">Administrative isolation</span></span>
- <span data-ttu-id="84406-119">IT decentralizzato</span><span class="sxs-lookup"><span data-stu-id="84406-119">Decentralized IT</span></span>
- <span data-ttu-id="84406-120">Decisioni cronologiche</span><span class="sxs-lookup"><span data-stu-id="84406-120">Historical decisions</span></span>
- <span data-ttu-id="84406-121">Fusioni, acquisizioni o cessioni</span><span class="sxs-lookup"><span data-stu-id="84406-121">Mergers, acquisitions, or divestitures</span></span>
- <span data-ttu-id="84406-122">Separazione chiara della personalizzazione per le organizzazioni conglomerate</span><span class="sxs-lookup"><span data-stu-id="84406-122">Clear separation of branding for conglomerate organizations</span></span>
- <span data-ttu-id="84406-123">Tenant di pre-produzione, test o sandbox</span><span class="sxs-lookup"><span data-stu-id="84406-123">Pre-production, test, or sandbox tenants</span></span>

<span data-ttu-id="84406-124">Ecco un esempio di un'organizzazione che dispone di due tenant (Tenant A e Tenant B) nello stesso datacenter geo predefinito.</span><span class="sxs-lookup"><span data-stu-id="84406-124">Here is an example of an organization that has two tenants (Tenant A and Tenant B) in the same default datacenter geo.</span></span> <span data-ttu-id="84406-125">Ogni tenant come tenant di Azure AD separato.</span><span class="sxs-lookup"><span data-stu-id="84406-125">Each tenant as a separate Azure AD tenant.</span></span>

![Più Microsoft 365 tenant con i propri tenant di Azure AD](../media/tenant-management-overview/tenant-management-example-multi-tenant.png)

<span data-ttu-id="84406-127">Quando si dispone di più tenant, esistono restrizioni e considerazioni aggiuntive per la gestione e la fornitura di servizi agli utenti.</span><span class="sxs-lookup"><span data-stu-id="84406-127">When you have multiple tenants, there are restrictions and additional considerations when managing them and providing services to your users.</span></span>

### <a name="inter-tenant-collaboration"></a><span data-ttu-id="84406-128">Collaborazione tra tenant</span><span class="sxs-lookup"><span data-stu-id="84406-128">Inter-tenant collaboration</span></span>

<span data-ttu-id="84406-129">Se si desidera che gli utenti collaborino in modo più efficace tra tenant di Microsoft 365 diversi in modo sicuro, le opzioni di collaborazione tra tenant includono l'utilizzo di una posizione centrale per file e conversazioni, la condivisione di calendari, l'utilizzo di messaggistica istantanea, chiamate audio/video per la comunicazione e la protezione dell'accesso a risorse e applicazioni.</span><span class="sxs-lookup"><span data-stu-id="84406-129">If you want your users to collaborate more effectively across different Microsoft 365 tenants in a secure manner, inter-tenant collaboration options include using a central location for files and conversations, sharing calendars, using IM, audio/video calls for communication, and securing access to resources and applications.</span></span>

<span data-ttu-id="84406-130">Per ulteriori informazioni, vedere [Microsoft 365 collaborazione tra tenant.](../enterprise/microsoft-365-inter-tenant-collaboration.md)</span><span class="sxs-lookup"><span data-stu-id="84406-130">For more information, see [Microsoft 365 inter-tenant collaboration](../enterprise/microsoft-365-inter-tenant-collaboration.md).</span></span>

### <a name="cross-tenant-mailbox-migration-preview"></a><span data-ttu-id="84406-131">Migrazione delle cassette postali tra tenant (anteprima)</span><span class="sxs-lookup"><span data-stu-id="84406-131">Cross-tenant mailbox migration (preview)</span></span>

<span data-ttu-id="84406-132">Prima della migrazione delle cassette postali tra tenant (in anteprima), quando si spostano le cassette postali di Exchange Online tra tenant, è necessario eseguire completamente l'offboard di una cassetta postale utente dal tenant corrente (il tenant di origine) a quello locale e quindi eseguire l'onboardboard in un nuovo tenant (il tenant di destinazione).</span><span class="sxs-lookup"><span data-stu-id="84406-132">Prior to cross-tenant mailbox migration (in preview), when moving Exchange Online mailboxes between tenants, you have to completely offboard a user mailbox from their current tenant (the source tenant) to on-premises and then onboard them to a new tenant (the target tenant).</span></span> <span data-ttu-id="84406-133">Con la nuova funzionalità di migrazione delle cassette postali tra tenant, gli amministratori tenant nei tenant di origine e di destinazione possono spostare le cassette postali tra i tenant con dipendenze minime dell'infrastruttura nei sistemi locali.</span><span class="sxs-lookup"><span data-stu-id="84406-133">With the new cross-tenant mailbox migration feature, tenant administrators in both source and target tenants can move mailboxes between the tenants with minimal infrastructure dependencies in their on-premises systems.</span></span> <span data-ttu-id="84406-134">In questo modo viene rimossa la necessità di eseguire l'offboard e l'onboard delle cassette postali.</span><span class="sxs-lookup"><span data-stu-id="84406-134">This removes the need to off-board and onboard mailboxes.</span></span>

<span data-ttu-id="84406-135">Ecco due tenant di esempio e le relative cassette postali prima della migrazione delle cassette postali tra tenant.</span><span class="sxs-lookup"><span data-stu-id="84406-135">Here are two example tenants and their mailboxes before cross-tenant mailbox migration.</span></span>

![Più Microsoft 365 tenant e le relative cassette postali](../media/tenant-management-overview/tenant-management-cross-tenant-mailbox-before.png)

<span data-ttu-id="84406-137">In questa figura, due tenant separati hanno i propri domini e un set di Exchange cassette postali.</span><span class="sxs-lookup"><span data-stu-id="84406-137">In this illustration, two separate tenants have their own domains and set of Exchange mailboxes.</span></span>

<span data-ttu-id="84406-138">Ecco il tenant di destinazione (Tenant A) dopo la migrazione delle cassette postali tra tenant.</span><span class="sxs-lookup"><span data-stu-id="84406-138">Here is the target tenant (Tenant A) after cross-tenant mailbox migration.</span></span>

![Tenant di destinazione dopo la migrazione delle cassette postali tra tenant](../media/tenant-management-overview/tenant-management-cross-tenant-mailbox-after.png)

<span data-ttu-id="84406-140">In questa figura, un singolo tenant include sia domini che entrambi i set di Exchange cassette postali.</span><span class="sxs-lookup"><span data-stu-id="84406-140">In this illustration, a single tenant has both domains and both sets of Exchange mailboxes.</span></span>

<span data-ttu-id="84406-141">Per ulteriori informazioni, vedere [Cross-tenant mailbox migration](../enterprise/cross-tenant-mailbox-migration.md).</span><span class="sxs-lookup"><span data-stu-id="84406-141">For more information, see [Cross-tenant mailbox migration](../enterprise/cross-tenant-mailbox-migration.md).</span></span>

### <a name="tenant-to-tenant-migrations"></a><span data-ttu-id="84406-142">Migrazioni da tenant a tenant</span><span class="sxs-lookup"><span data-stu-id="84406-142">Tenant-to-tenant migrations</span></span>

<span data-ttu-id="84406-143">Esistono diversi approcci architetturali per fusioni, acquisizioni, cessioni e altri scenari che potrebbero portare alla migrazione di un tenant Microsoft 365 esistente a un nuovo tenant.</span><span class="sxs-lookup"><span data-stu-id="84406-143">There are several architectural approaches for mergers, acquisitions, divestitures, and other scenarios that might lead you to migrate an existing Microsoft 365 tenant to a new tenant.</span></span> 

<span data-ttu-id="84406-144">Per istruzioni dettagliate, vedere [Microsoft 365 migrazioni da tenant a tenant](../enterprise/microsoft-365-tenant-to-tenant-migrations.md).</span><span class="sxs-lookup"><span data-stu-id="84406-144">For detailed guidance, see [Microsoft 365 tenant-to-tenant migrations](../enterprise/microsoft-365-tenant-to-tenant-migrations.md).</span></span>

## <a name="multi-geo-for-a-tenant"></a><span data-ttu-id="84406-145">Multi-Geo per un tenant</span><span class="sxs-lookup"><span data-stu-id="84406-145">Multi-Geo for a tenant</span></span>

<span data-ttu-id="84406-146">Con Microsoft 365 Multi-Geo, è possibile effettuare il provisioning e archiviare i dati a riposo nelle altre posizioni geografiche del datacenter scelte per soddisfare i requisiti di residenza dei dati e allo stesso tempo sbloccare l'implementazione globale delle esperienze di produttività moderne per i dipendenti.</span><span class="sxs-lookup"><span data-stu-id="84406-146">With Microsoft 365 Multi-Geo, you can provision and store data at rest in the other datacenter geo locations that you've chosen to meet data residency requirements, and at the same time unlock your global rollout of modern productivity experiences to your workers.</span></span>

<span data-ttu-id="84406-147">In un ambiente Multi-Geo, il tenant di Microsoft 365 è costituito da una posizione predefinita o centrale in cui è stata originariamente creata la sottoscrizione Microsoft 365 e da una o più posizioni satellite.</span><span class="sxs-lookup"><span data-stu-id="84406-147">In a Multi-Geo environment, your Microsoft 365 tenant consists of a default or central location where your Microsoft 365 subscription was originally created and one or more satellite locations.</span></span> <span data-ttu-id="84406-148">In un tenant multi-geografico, le informazioni sulle posizioni geografiche, sui gruppi e sulle informazioni utente sono master in un tenant globale di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="84406-148">In a multi-geo tenant, the information about geo locations, groups, and user information is mastered in a global Azure AD tenant.</span></span> <span data-ttu-id="84406-149">Poiché le informazioni del tenant vengono masterate centralmente e sincronizzate in ogni posizione geografica, le esperienze di collaborazione che coinvolgono tutti gli utenti dell'azienda vengono condivise tra le posizioni.</span><span class="sxs-lookup"><span data-stu-id="84406-149">Because your tenant information is mastered centrally and synchronized into each geo location, collaboration experiences involving anyone from your company are shared across the locations.</span></span>

<span data-ttu-id="84406-150">Ecco un esempio di un'organizzazione che ha la sua posizione predefinita in Europa e una posizione satellite in Nord America.</span><span class="sxs-lookup"><span data-stu-id="84406-150">Here is an example of an organization that has its default location in Europe and a satellite location in North America.</span></span> <span data-ttu-id="84406-151">Entrambe le posizioni condividono lo stesso tenant globale di Azure AD per il tenant Microsoft 365 singolo.</span><span class="sxs-lookup"><span data-stu-id="84406-151">Both locations share the same global Azure AD tenant for the single Microsoft 365 tenant.</span></span>

![Esempio di tenant multi-Microsoft 365 geografico](../media/tenant-management-overview/tenant-management-example-multi-geo.png)

<span data-ttu-id="84406-153">Per ulteriori informazioni, vedere [Microsoft 365 Multi-Geo](../enterprise/microsoft-365-multi-geo.md).</span><span class="sxs-lookup"><span data-stu-id="84406-153">For more information, see [Microsoft 365 Multi-Geo](../enterprise/microsoft-365-multi-geo.md).</span></span>

## <a name="moving-core-data-to-a-new-datacenter-geo"></a><span data-ttu-id="84406-154">Spostamento dei dati di base in un nuovo data center geo</span><span class="sxs-lookup"><span data-stu-id="84406-154">Moving core data to a new datacenter geo</span></span>

<span data-ttu-id="84406-155">Microsoft continua ad aprire nuovi dati geografici del datacenter per Microsoft 365 servizi.</span><span class="sxs-lookup"><span data-stu-id="84406-155">Microsoft continues to open new datacenter geos for Microsoft 365 services.</span></span> <span data-ttu-id="84406-156">Questi nuovi geo datacenter aggiungono capacità e risorse di calcolo per supportare la crescita continua della domanda e dell'utilizzo dei clienti.</span><span class="sxs-lookup"><span data-stu-id="84406-156">These new datacenter geos add capacity and compute resources to support our ongoing customer demand and usage growth.</span></span> <span data-ttu-id="84406-157">Inoltre, i nuovi dati geografici del datacenter offrono la residenza dei dati in-geo per i dati principali dei clienti.</span><span class="sxs-lookup"><span data-stu-id="84406-157">Additionally, the new datacenter geos offer in-geo data residency for core customer data.</span></span>

<span data-ttu-id="84406-158">Sebbene l'apertura di un nuovo data center geo non influisca sull'utente e sui dati di base archiviati in un data center geo già esistente, Microsoft consente di richiedere una migrazione anticipata dei dati dei clienti principali dell'organizzazione in fase di riposo a un nuovo data center geo.</span><span class="sxs-lookup"><span data-stu-id="84406-158">Although opening a new datacenter geo does not impact you and your core data stored in an already existing datacenter geo, Microsoft allows you to request an early migration of your organization's core customer data at rest to a new datacenter geo.</span></span>

<span data-ttu-id="84406-159">Ecco un esempio in cui un tenant di Microsoft 365 è stato spostato dall'area geografica del datacenter dell'Unione Europea (UE) a quello situato nel Regno Unito (Regno Unito).</span><span class="sxs-lookup"><span data-stu-id="84406-159">Here is an example in which a Microsoft 365 tenant was moved from the European Union (EU) datacenter geo to the one located in the United Kingdom (UK).</span></span>

![Esempio di spostamento di un tenant Microsoft 365 tra le posizioni geografiche del datacenter](../media/tenant-management-overview/tenant-management-example-tenant-move.png)

<span data-ttu-id="84406-161">Per ulteriori informazioni, vedere [Moving core data to new Microsoft 365 datacenter geos](../enterprise/moving-data-to-new-datacenter-geos.md).</span><span class="sxs-lookup"><span data-stu-id="84406-161">For more information, see [Moving core data to new Microsoft 365 datacenter geos](../enterprise/moving-data-to-new-datacenter-geos.md).</span></span>

## <a name="products-and-licenses-for-a-tenant"></a><span data-ttu-id="84406-162">Prodotti e licenze per un tenant</span><span class="sxs-lookup"><span data-stu-id="84406-162">Products and licenses for a tenant</span></span>

<span data-ttu-id="84406-163">Il Microsoft 365 tenant viene creato quando si acquista il primo prodotto, ad esempio Microsoft 365 E3.</span><span class="sxs-lookup"><span data-stu-id="84406-163">Your Microsoft 365 tenant gets created when you purchase your first product, such as Microsoft 365 E3.</span></span> <span data-ttu-id="84406-164">Insieme al prodotto sono presenti licenze, a cui viene addebitata una tariffa mensile o annuale.</span><span class="sxs-lookup"><span data-stu-id="84406-164">Along with the product are licenses, which are charged a monthly or annual fee.</span></span> <span data-ttu-id="84406-165">Un amministratore assegna quindi una licenza disponibile da uno dei prodotti a un account utente, direttamente o tramite l'appartenenza al gruppo.</span><span class="sxs-lookup"><span data-stu-id="84406-165">An administrator then assigns an available license from one of your products to a user account, either directly or through group membership.</span></span> <span data-ttu-id="84406-166">A seconda delle esigenze aziendali dell'organizzazione, è possibile disporre di un set di prodotti, ognuno con il proprio pool di licenze.</span><span class="sxs-lookup"><span data-stu-id="84406-166">Depending on your organization's business needs, you might have a set of products, each with their own pool of licenses.</span></span> 

<span data-ttu-id="84406-167">Per determinare il set di prodotti e il numero di licenze per ognuno di essi, è necessario pianificare quanto prima:</span><span class="sxs-lookup"><span data-stu-id="84406-167">Determining the set of products and the number of licenses for each requires some planning to:</span></span>

- <span data-ttu-id="84406-168">Assicurarsi di disporre di licenze sufficienti per gli account utente che necessitano di funzionalità avanzate.</span><span class="sxs-lookup"><span data-stu-id="84406-168">Ensure you have enough licenses for the user accounts that need advanced features.</span></span>
- <span data-ttu-id="84406-169">Impedisci l'evaso delle licenze o la presenza di troppe licenze non assegnate, in base alle modifiche apportate al personale dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="84406-169">Prevent you from running out of licenses or having too many unassigned licenses, based on changes in staffing at your organization.</span></span>


## <a name="results-of-step-1"></a><span data-ttu-id="84406-170">Risultati del Passaggio 1</span><span class="sxs-lookup"><span data-stu-id="84406-170">Results of Step 1</span></span>

<span data-ttu-id="84406-171">Per il Microsoft 365 per i tenant aziendali, sono stati determinati:</span><span class="sxs-lookup"><span data-stu-id="84406-171">For your Microsoft 365 for enterprise tenants, you have determined:</span></span>

- <span data-ttu-id="84406-172">Numero di tenant necessari o di cui si ha bisogno.</span><span class="sxs-lookup"><span data-stu-id="84406-172">How many tenants you have or need.</span></span>
- <span data-ttu-id="84406-173">Per ogni tenant, quali prodotti e licenze devono essere acquistati.</span><span class="sxs-lookup"><span data-stu-id="84406-173">For each tenant, which products and licenses must be purchased.</span></span>
- <span data-ttu-id="84406-174">Indica se un tenant deve essere Multi-Geo per soddisfare i requisiti di residenza dei dati.</span><span class="sxs-lookup"><span data-stu-id="84406-174">Whether a tenant needs to be Multi-Geo to comply with data residency requirements.</span></span>
- <span data-ttu-id="84406-175">Indica se è necessario configurare la collaborazione tra tenant.</span><span class="sxs-lookup"><span data-stu-id="84406-175">Whether you need to set up inter-tenant collaboration.</span></span>
- <span data-ttu-id="84406-176">Se è necessario eseguire la migrazione di un tenant a un altro.</span><span class="sxs-lookup"><span data-stu-id="84406-176">Whether you need to migrate one tenant to another.</span></span>
- <span data-ttu-id="84406-177">Indica se è necessario spostare i dati di base da un datacenter geografico a uno nuovo.</span><span class="sxs-lookup"><span data-stu-id="84406-177">Whether you need to move core data from one datacenter geo to new one.</span></span>

<span data-ttu-id="84406-178">Ecco un esempio di nuovo tenant.</span><span class="sxs-lookup"><span data-stu-id="84406-178">Here is an example of a new tenant.</span></span>

![Esempio di un nuovo tenant](../media/tenant-management-overview/tenant-management-tenant-build-step1.png)

<span data-ttu-id="84406-180">In questa illustrazione, il tenant ha:</span><span class="sxs-lookup"><span data-stu-id="84406-180">In this illustration, the tenant has:</span></span>

- <span data-ttu-id="84406-181">Posizione predefinita corrispondente a una posizione geografica Microsoft 365 datacenter.</span><span class="sxs-lookup"><span data-stu-id="84406-181">A default location corresponding to a Microsoft 365 datacenter geo.</span></span>
- <span data-ttu-id="84406-182">Un set di prodotti e licenze.</span><span class="sxs-lookup"><span data-stu-id="84406-182">A set of products and licenses.</span></span>
- <span data-ttu-id="84406-183">Set di app di produttività cloud, alcune delle quali specifiche per i prodotti.</span><span class="sxs-lookup"><span data-stu-id="84406-183">The set of cloud productivity apps, some of which are specific to products.</span></span>
- <span data-ttu-id="84406-184">Tenant di Azure AD che contiene account di amministratore globale e un nome di dominio DNS iniziale.</span><span class="sxs-lookup"><span data-stu-id="84406-184">An Azure AD tenant that contains global administrator accounts and an initial DNS domain name.</span></span>

<span data-ttu-id="84406-185">Durante lo spostamento tra i passaggi aggiuntivi di questa soluzione, verrà compilata questa figura.</span><span class="sxs-lookup"><span data-stu-id="84406-185">As we move through the additional steps of this solution, we will build out this figure.</span></span>

## <a name="ongoing-maintenance-for-tenants"></a><span data-ttu-id="84406-186">Manutenzione continua per i tenant</span><span class="sxs-lookup"><span data-stu-id="84406-186">Ongoing maintenance for tenants</span></span>

<span data-ttu-id="84406-187">Su base continuativa, potrebbe essere necessario:</span><span class="sxs-lookup"><span data-stu-id="84406-187">On an ongoing basis, you might need to:</span></span>

- <span data-ttu-id="84406-188">Aggiungere un nuovo tenant.</span><span class="sxs-lookup"><span data-stu-id="84406-188">Add a new tenant.</span></span>
- <span data-ttu-id="84406-189">Aggiungere nuovi prodotti a un tenant con un numero iniziale di licenze.</span><span class="sxs-lookup"><span data-stu-id="84406-189">Add new products to a tenant with an initial number of licenses.</span></span>
- <span data-ttu-id="84406-190">Modificare il set di licenze per un prodotto in un tenant per adattare i requisiti del personale.</span><span class="sxs-lookup"><span data-stu-id="84406-190">Change the set of licenses for a product in a tenant to adjust for changing staff requirements.</span></span>
- <span data-ttu-id="84406-191">Spostare i dati di base da un tenant a una nuova posizione geografica del datacenter.</span><span class="sxs-lookup"><span data-stu-id="84406-191">Move your core data from a tenant to a new datacenter geo location.</span></span>
- <span data-ttu-id="84406-192">Aggiungere Multi-Geo per i requisiti di residenza dei dati.</span><span class="sxs-lookup"><span data-stu-id="84406-192">Add Multi-Geo for data residency requirements.</span></span>
- <span data-ttu-id="84406-193">Configurare la collaborazione tra tenant.</span><span class="sxs-lookup"><span data-stu-id="84406-193">Set up inter-tenant collaboration.</span></span>

## <a name="next-step"></a><span data-ttu-id="84406-194">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="84406-194">Next step</span></span>

<span data-ttu-id="84406-195">[![Passaggio 2. Ottimizzare il tenant per la rete per l'accesso](../media/tenant-management-overview/tenant-management-step-grid-networking.png)](tenant-management-networking.md)</span><span class="sxs-lookup"><span data-stu-id="84406-195">[![Step 2. Optimize your tenant for network for access](../media/tenant-management-overview/tenant-management-step-grid-networking.png)](tenant-management-networking.md)</span></span>

<span data-ttu-id="84406-196">Continuare con [la rete](tenant-management-networking.md) per fornire una rete ottimale dai lavoratori ai Microsoft 365 cloud.</span><span class="sxs-lookup"><span data-stu-id="84406-196">Continue with [networking](tenant-management-networking.md) to provide optimal networking from your workers to Microsoft 365 cloud services.</span></span>
