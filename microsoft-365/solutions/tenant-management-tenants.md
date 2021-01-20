---
title: Passaggio 1. Microsoft 365 per i tenant Enterprise
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
ms.custom:
- Ent_Solutions
description: Distribuire e gestire singoli o più tenant di Microsoft 365, con opzioni per percorsi multi-Geo e mobili.
ms.openlocfilehash: 567a2cb46e715ec560bf973a33ab83cfa63d403b
ms.sourcegitcommit: 99a7354e6a6b4d9d5202674ef57852d52a43fef6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/20/2021
ms.locfileid: "49908592"
---
# <a name="step-1-your-microsoft-365-for-enterprise-tenants"></a><span data-ttu-id="36e55-104">Passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="36e55-104">Step 1.</span></span> <span data-ttu-id="36e55-105">Microsoft 365 per i tenant Enterprise</span><span class="sxs-lookup"><span data-stu-id="36e55-105">Your Microsoft 365 for enterprise tenants</span></span>

<span data-ttu-id="36e55-106">Una delle prime decisioni del tenant è il numero di spettatori.</span><span class="sxs-lookup"><span data-stu-id="36e55-106">One of your first tenant decisions is how many to have.</span></span> <span data-ttu-id="36e55-107">Ogni tenant di Microsoft 365 è distinto, univoco e separato da tutti gli altri tenant di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="36e55-107">Each Microsoft 365 tenant is distinct, unique, and separate from all other Microsoft 365 tenants.</span></span> <span data-ttu-id="36e55-108">Il tenant di Azure AD corrispondente è anche distinto, univoco e separato da tutti gli altri tenant di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="36e55-108">It’s corresponding Azure AD tenant is also distinct, unique, and separate from all other Microsoft 365 tenants.</span></span>

## <a name="single-tenant"></a><span data-ttu-id="36e55-109">Singolo tenant</span><span class="sxs-lookup"><span data-stu-id="36e55-109">Single tenant</span></span>
<span data-ttu-id="36e55-110">La presenza di un singolo tenant semplifica molti aspetti dell'utilizzo dell'organizzazione da parte di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="36e55-110">Having a single tenant simplifies many aspects of your organization’s use of Microsoft 365.</span></span> <span data-ttu-id="36e55-111">Un singolo tenant indica un singolo tenant di Azure AD con un solo set di account, gruppi e criteri.</span><span class="sxs-lookup"><span data-stu-id="36e55-111">A single tenant means a single Azure AD tenant with a single set of accounts, groups, and policies.</span></span> <span data-ttu-id="36e55-112">Le autorizzazioni e la condivisione delle risorse all'interno dell'organizzazione possono essere eseguite tramite questo provider di identità centrale.</span><span class="sxs-lookup"><span data-stu-id="36e55-112">Permissions and sharing of resources across your organization can be done through this central identity provider.</span></span>

<span data-ttu-id="36e55-113">Un singolo tenant fornisce la collaborazione e la produttività più ricche di funzionalità e semplificate per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="36e55-113">A single tenant provides the most feature-rich and simplified collaboration and productivity experience for your users.</span></span>

<span data-ttu-id="36e55-114">Di seguito è riportato un esempio che mostra il percorso predefinito e il tenant di Azure AD di un tenant di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="36e55-114">Here is an example showing the default location and Azure AD tenant of a Microsoft 365 tenant.</span></span>

![Un singolo tenant di Microsoft 365 con il tenant di Azure AD](../media/tenant-management-overview/tenant-management-example-tenant.png)

## <a name="multiple-tenants"></a><span data-ttu-id="36e55-116">Più tenant</span><span class="sxs-lookup"><span data-stu-id="36e55-116">Multiple tenants</span></span>

<span data-ttu-id="36e55-117">Esistono molti motivi per i quali l'organizzazione può disporre di più tenant:</span><span class="sxs-lookup"><span data-stu-id="36e55-117">There are many reasons why your organization could have multiple tenants:</span></span>

- <span data-ttu-id="36e55-118">Isolamento amministrativo</span><span class="sxs-lookup"><span data-stu-id="36e55-118">Administrative isolation</span></span>
- <span data-ttu-id="36e55-119">Decentralizzato IT</span><span class="sxs-lookup"><span data-stu-id="36e55-119">Decentralized IT</span></span>
- <span data-ttu-id="36e55-120">Decisioni storiche</span><span class="sxs-lookup"><span data-stu-id="36e55-120">Historical decisions</span></span>
- <span data-ttu-id="36e55-121">Fusioni, acquisizioni o dismissioni</span><span class="sxs-lookup"><span data-stu-id="36e55-121">Mergers, acquisitions, or divestitures</span></span>
- <span data-ttu-id="36e55-122">Separazione netta del branding per organizzazioni di conglomerati</span><span class="sxs-lookup"><span data-stu-id="36e55-122">Clear separation of branding for conglomerate organizations</span></span>
- <span data-ttu-id="36e55-123">Tenant di preproduzione, test o sandbox</span><span class="sxs-lookup"><span data-stu-id="36e55-123">Pre-production, test, or sandbox tenants</span></span>

<span data-ttu-id="36e55-124">Di seguito è riportato un esempio di un'organizzazione che dispone di due tenant (tenant A e tenant B) nello stesso data center geografico predefinito.</span><span class="sxs-lookup"><span data-stu-id="36e55-124">Here is an example of an organization that has two tenants (Tenant A and Tenant B) in the same default datacenter geo.</span></span> <span data-ttu-id="36e55-125">Ogni tenant come tenant di Azure AD separato.</span><span class="sxs-lookup"><span data-stu-id="36e55-125">Each tenant as a separate Azure AD tenant.</span></span>

![Più tenant Microsoft 365 con i propri tenant di Azure AD](../media/tenant-management-overview/tenant-management-example-multi-tenant.png)

<span data-ttu-id="36e55-127">Quando si dispone di più tenant, esistono restrizioni e considerazioni aggiuntive per la gestione e la fornitura di servizi agli utenti.</span><span class="sxs-lookup"><span data-stu-id="36e55-127">When you have multiple tenants, there are restrictions and additional considerations when managing them and providing services to your users.</span></span>

### <a name="inter-tenant-collaboration"></a><span data-ttu-id="36e55-128">Collaborazione tra tenant</span><span class="sxs-lookup"><span data-stu-id="36e55-128">Inter-tenant collaboration</span></span>

<span data-ttu-id="36e55-129">Se si desidera consentire agli utenti di collaborare in maniera più efficace tra i diversi tenant di Microsoft 365 in modo sicuro, le opzioni di collaborazione tra tenant includono l'utilizzo di una posizione centrale per file e conversazioni, la condivisione di calendari, l'utilizzo di messaggistica istantanea, le chiamate audio/video per la comunicazione e la protezione dell'accesso alle risorse e alle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="36e55-129">If you want your users to collaborate more effectively across different Microsoft 365 tenants in a secure manner, inter-tenant collaboration options include using a central location for files and conversations, sharing calendars, using IM, audio/video calls for communication, and securing access to resources and applications.</span></span>

<span data-ttu-id="36e55-130">Per ulteriori informazioni, vedere [Microsoft 365 Inter-Tenant Collaboration](../enterprise/microsoft-365-inter-tenant-collaboration.md).</span><span class="sxs-lookup"><span data-stu-id="36e55-130">For more information, see [Microsoft 365 inter-tenant collaboration](../enterprise/microsoft-365-inter-tenant-collaboration.md).</span></span>

### <a name="cross-tenant-mailbox-migration-preview"></a><span data-ttu-id="36e55-131">Migrazione delle cassette postali tra tenant (anteprima)</span><span class="sxs-lookup"><span data-stu-id="36e55-131">Cross-tenant mailbox migration (preview)</span></span>

<span data-ttu-id="36e55-132">Prima di eseguire la migrazione delle cassette postali Cross-tenant (in anteprima), quando si spostano cassette postali di Exchange Online tra i tenant, è necessario trasferisce completamente una cassetta postale utente dal tenant corrente (il tenant di origine) in locale e quindi Onboard a un nuovo tenant (il tenant di destinazione).</span><span class="sxs-lookup"><span data-stu-id="36e55-132">Prior to cross-tenant mailbox migration (in preview), when moving Exchange Online mailboxes between tenants, you have to completely offboard a user mailbox from their current tenant (the source tenant) to on-premises and then onboard them to a new tenant (the target tenant).</span></span> <span data-ttu-id="36e55-133">Con la nuova funzionalità di migrazione delle cassette postali Cross-tenant, gli amministratori tenant in entrambi i tenant di origine e di destinazione possono spostare le cassette postali tra i tenant con dipendenze dell'infrastruttura minime nei rispettivi sistemi locali.</span><span class="sxs-lookup"><span data-stu-id="36e55-133">With the new cross-tenant mailbox migration feature, tenant administrators in both source and target tenants can move mailboxes between the tenants with minimal infrastructure dependencies in their on-premises systems.</span></span> <span data-ttu-id="36e55-134">In questo modo viene eliminata la necessità di disabilitare le cassette postali e di bordo.</span><span class="sxs-lookup"><span data-stu-id="36e55-134">This removes the need to off-board and onboard mailboxes.</span></span>

<span data-ttu-id="36e55-135">Di seguito sono disponibili due tenant di esempio e le relative cassette postali prima della migrazione delle cassette postali tra tenant.</span><span class="sxs-lookup"><span data-stu-id="36e55-135">Here are two example tenants and their mailboxes before cross-tenant mailbox migration.</span></span>

![Più tenant Microsoft 365 e le relative cassette postali](../media/tenant-management-overview/tenant-management-cross-tenant-mailbox-before.png)

<span data-ttu-id="36e55-137">In questa figura, due tenant separati dispongono di propri domini e set di cassette postali di Exchange.</span><span class="sxs-lookup"><span data-stu-id="36e55-137">In this illustration, two separate tenants have their own domains and set of Exchange mailboxes.</span></span>

<span data-ttu-id="36e55-138">Di seguito è indicato il tenant di destinazione (tenant A) dopo la migrazione delle cassette postali tra tenant.</span><span class="sxs-lookup"><span data-stu-id="36e55-138">Here is the target tenant (Tenant A) after cross-tenant mailbox migration.</span></span>

![Il tenant di destinazione dopo la migrazione delle cassette postali tra tenant](../media/tenant-management-overview/tenant-management-cross-tenant-mailbox-after.png)

<span data-ttu-id="36e55-140">In questa figura, un singolo tenant dispone di entrambi i domini e di entrambi i gruppi di cassette postali di Exchange.</span><span class="sxs-lookup"><span data-stu-id="36e55-140">In this illustration, a single tenant has both domains and both sets of Exchange mailboxes.</span></span>

<span data-ttu-id="36e55-141">Per ulteriori informazioni, vedere [Cross-tenant Mailbox Migration](../enterprise/cross-tenant-mailbox-migration.md).</span><span class="sxs-lookup"><span data-stu-id="36e55-141">For more information, see [Cross-tenant mailbox migration](../enterprise/cross-tenant-mailbox-migration.md).</span></span>

### <a name="tenant-to-tenant-migrations"></a><span data-ttu-id="36e55-142">Migrazioni da tenant a tenant</span><span class="sxs-lookup"><span data-stu-id="36e55-142">Tenant-to-tenant migrations</span></span>

<span data-ttu-id="36e55-143">Esistono diversi approcci architetturali per fusioni, acquisizioni, dismissioni e altri scenari che potrebbero portare alla migrazione di un tenant di Microsoft 365 esistente a un nuovo tenant.</span><span class="sxs-lookup"><span data-stu-id="36e55-143">There are several architectural approaches for mergers, acquisitions, divestitures, and other scenarios that might lead you to migrate an existing Microsoft 365 tenant to a new tenant.</span></span> 

<span data-ttu-id="36e55-144">Per informazioni dettagliate, vedere [migrazioni tenant-to-tenant di Microsoft 365](../enterprise/microsoft-365-tenant-to-tenant-migrations.md).</span><span class="sxs-lookup"><span data-stu-id="36e55-144">For detailed guidance, see [Microsoft 365 tenant-to-tenant migrations](../enterprise/microsoft-365-tenant-to-tenant-migrations.md).</span></span>

## <a name="multi-geo-for-a-tenant"></a><span data-ttu-id="36e55-145">Multi-Geo per un tenant</span><span class="sxs-lookup"><span data-stu-id="36e55-145">Multi-Geo for a tenant</span></span>

<span data-ttu-id="36e55-146">Con Microsoft 365 multi-Geo, è possibile eseguire il provisioning e l'archiviazione dei dati a riposo nelle altre posizioni geografiche del datacenter che si è scelto di soddisfare i requisiti di residenza dei dati e allo stesso tempo sbloccare l'implementazione globale delle esperienze di produttività moderne ai propri dipendenti.</span><span class="sxs-lookup"><span data-stu-id="36e55-146">With Microsoft 365 Multi-Geo, you can provision and store data at rest in the other datacenter geo locations that you've chosen to meet data residency requirements, and at the same time unlock your global rollout of modern productivity experiences to your workers.</span></span>

<span data-ttu-id="36e55-147">In un ambiente multi-geografico, il tenant Microsoft 365 è costituito da una posizione predefinita o centrale in cui è stata creata originariamente la sottoscrizione Microsoft 365 e da una o più posizioni satellite.</span><span class="sxs-lookup"><span data-stu-id="36e55-147">In a Multi-Geo environment, your Microsoft 365 tenant consists of a default or central location where your Microsoft 365 subscription was originally created and one or more satellite locations.</span></span> <span data-ttu-id="36e55-148">In un tenant multi-Geo, le informazioni sulle posizioni geografiche, i gruppi e le informazioni degli utenti vengono padroneggiate in un tenant di Azure AD globale.</span><span class="sxs-lookup"><span data-stu-id="36e55-148">In a multi-geo tenant, the information about geo locations, groups, and user information is mastered in a global Azure AD tenant.</span></span> <span data-ttu-id="36e55-149">Poiché le informazioni sul tenant sono padroneggiate in modo centralizzato e sincronizzate in ogni posizione geografica, le esperienze di collaborazione che coinvolgono tutti gli utenti della società sono condivise tra le diverse posizioni.</span><span class="sxs-lookup"><span data-stu-id="36e55-149">Because your tenant information is mastered centrally and synchronized into each geo location, collaboration experiences involving anyone from your company are shared across the locations.</span></span>

<span data-ttu-id="36e55-150">Di seguito è riportato un esempio di un'organizzazione che ha la posizione predefinita in Europa e una località satellite in Nord America.</span><span class="sxs-lookup"><span data-stu-id="36e55-150">Here is an example of an organization that has its default location in Europe and a satellite location in North America.</span></span> <span data-ttu-id="36e55-151">Entrambe le posizioni condividono lo stesso tenant di Azure AD globale per il tenant single Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="36e55-151">Both locations share the same global Azure AD tenant for the single Microsoft 365 tenant.</span></span>

![Esempio di un tenant multi-Geo Microsoft 365](../media/tenant-management-overview/tenant-management-example-multi-geo.png)

<span data-ttu-id="36e55-153">Per ulteriori informazioni, vedere [Microsoft 365 Multi-Geo](../enterprise/microsoft-365-multi-geo.md).</span><span class="sxs-lookup"><span data-stu-id="36e55-153">For more information, see [Microsoft 365 Multi-Geo](../enterprise/microsoft-365-multi-geo.md).</span></span>

## <a name="moving-core-data-to-a-new-datacenter-geo"></a><span data-ttu-id="36e55-154">Spostamento dei dati di base in un nuovo datacenter Geo</span><span class="sxs-lookup"><span data-stu-id="36e55-154">Moving core data to a new datacenter geo</span></span>

<span data-ttu-id="36e55-155">Microsoft continua ad aprire nuovo datacenter GEOS per i servizi di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="36e55-155">Microsoft continues to open new datacenter geos for Microsoft 365 services.</span></span> <span data-ttu-id="36e55-156">Questi nuovi datacenter GEOS aggiungono capacità e risorse di calcolo per supportare la crescita della domanda e dell'utilizzo dei clienti in continua espansione.</span><span class="sxs-lookup"><span data-stu-id="36e55-156">These new datacenter geos add capacity and compute resources to support our ongoing customer demand and usage growth.</span></span> <span data-ttu-id="36e55-157">Inoltre, il nuovo datacenter GEOS offre la residenza di dati in-Geo per i dati di base dei clienti.</span><span class="sxs-lookup"><span data-stu-id="36e55-157">Additionally, the new datacenter geos offer in-geo data residency for core customer data.</span></span>

<span data-ttu-id="36e55-158">Anche se l'apertura di un nuovo datacenter Geo non ha un impatto sull'utente e sui dati di base archiviati in un datacenter geografico già esistente, Microsoft consente di richiedere una migrazione precoce dei dati del cliente principale dell'organizzazione a riposo in un nuovo Data Center Geo.</span><span class="sxs-lookup"><span data-stu-id="36e55-158">Although opening a new datacenter geo does not impact you and your core data stored in an already existing datacenter geo, Microsoft allows you to request an early migration of your organization's core customer data at rest to a new datacenter geo.</span></span>

<span data-ttu-id="36e55-159">Di seguito è riportato un esempio in cui un tenant Microsoft 365 è stato spostato dal datacenter geografico Unione europea (EU) a quello che si trova nel Regno Unito (UK).</span><span class="sxs-lookup"><span data-stu-id="36e55-159">Here is an example in which a Microsoft 365 tenant was moved from the European Union (EU) datacenter geo to the one located in the United Kingdom (UK).</span></span>

![Esempio di spostamento di un tenant di Microsoft 365 tra datacenter GEOS](../media/tenant-management-overview/tenant-management-example-tenant-move.png)

<span data-ttu-id="36e55-161">Per ulteriori informazioni, vedere [Moving core data to New Microsoft 365 datacenter GEOS](../enterprise/moving-data-to-new-datacenter-geos.md).</span><span class="sxs-lookup"><span data-stu-id="36e55-161">For more information, see [Moving core data to new Microsoft 365 datacenter geos](../enterprise/moving-data-to-new-datacenter-geos.md).</span></span>

## <a name="products-and-licenses-for-a-tenant"></a><span data-ttu-id="36e55-162">Prodotti e licenze per un tenant</span><span class="sxs-lookup"><span data-stu-id="36e55-162">Products and licenses for a tenant</span></span>

<span data-ttu-id="36e55-163">Il tenant Microsoft 365 viene creato durante l'acquisto del primo prodotto, ad esempio Microsoft 365 E3.</span><span class="sxs-lookup"><span data-stu-id="36e55-163">Your Microsoft 365 tenant gets created when you purchase your first product, such as Microsoft 365 E3.</span></span> <span data-ttu-id="36e55-164">Insieme al prodotto ci sono le licenze che pagano una tariffa mensile o annuale.</span><span class="sxs-lookup"><span data-stu-id="36e55-164">Along with the product are licenses, which are charged a monthly or annual fee.</span></span> <span data-ttu-id="36e55-165">Un amministratore assegna quindi una licenza disponibile da uno dei prodotti a un account utente, direttamente o tramite l'appartenenza a un gruppo.</span><span class="sxs-lookup"><span data-stu-id="36e55-165">An administrator then assigns an available license from one of your products to a user account, either directly or through group membership.</span></span> <span data-ttu-id="36e55-166">A seconda delle esigenze aziendali dell'organizzazione, è possibile disporre di un insieme di prodotti, ognuno con il proprio pool di licenze.</span><span class="sxs-lookup"><span data-stu-id="36e55-166">Depending on your organization's business needs, you might have a set of products, each with their own pool of licenses.</span></span> 

<span data-ttu-id="36e55-167">La determinazione del set di prodotti e il numero di licenze per ognuna richiede una pianificazione per:</span><span class="sxs-lookup"><span data-stu-id="36e55-167">Determining the set of products and the number of licenses for each requires some planning to:</span></span>

- <span data-ttu-id="36e55-168">Assicurarsi di disporre di licenze sufficienti per gli account utente che richiedono funzionalità avanzate.</span><span class="sxs-lookup"><span data-stu-id="36e55-168">Ensure you have enough licenses for the user accounts that need advanced features.</span></span>
- <span data-ttu-id="36e55-169">Impedire l'esecuzione delle licenze o la presenza di troppe licenze non assegnate, in base alle modifiche apportate al personale dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="36e55-169">Prevent you from running out of licenses or having too many unassigned licenses, based on changes in staffing at your organization.</span></span>


## <a name="results-of-step-1"></a><span data-ttu-id="36e55-170">Risultati del Passaggio 1</span><span class="sxs-lookup"><span data-stu-id="36e55-170">Results of Step 1</span></span>

<span data-ttu-id="36e55-171">Per i tenant di Microsoft 365 per Enterprise, sono state determinate le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="36e55-171">For your Microsoft 365 for enterprise tenants, you have determined:</span></span>

- <span data-ttu-id="36e55-172">Numero di tenant necessari.</span><span class="sxs-lookup"><span data-stu-id="36e55-172">How many tenants you have or need.</span></span>
- <span data-ttu-id="36e55-173">Per ogni tenant, quali prodotti e licenze devono essere acquistati.</span><span class="sxs-lookup"><span data-stu-id="36e55-173">For each tenant, which products and licenses must be purchased.</span></span>
- <span data-ttu-id="36e55-174">Se un tenant deve essere multi-Geo per conformarsi ai requisiti di residenza dei dati.</span><span class="sxs-lookup"><span data-stu-id="36e55-174">Whether a tenant needs to be Multi-Geo to comply with data residency requirements.</span></span>
- <span data-ttu-id="36e55-175">Se è necessario configurare la collaborazione tra tenant.</span><span class="sxs-lookup"><span data-stu-id="36e55-175">Whether you need to set up inter-tenant collaboration.</span></span>
- <span data-ttu-id="36e55-176">Se è necessario eseguire la migrazione di un tenant a un altro.</span><span class="sxs-lookup"><span data-stu-id="36e55-176">Whether you need to migrate one tenant to another.</span></span>
- <span data-ttu-id="36e55-177">Se è necessario spostare i dati di base da un datacenter geografico a un altro.</span><span class="sxs-lookup"><span data-stu-id="36e55-177">Whether you need to move core data from one datacenter geo to new one.</span></span>

<span data-ttu-id="36e55-178">Di seguito è riportato un esempio di nuovo tenant.</span><span class="sxs-lookup"><span data-stu-id="36e55-178">Here is an example of a new tenant.</span></span>

![Esempio di un nuovo tenant](../media/tenant-management-overview/tenant-management-tenant-build-step1.png)

<span data-ttu-id="36e55-180">In questa figura, il tenant ha:</span><span class="sxs-lookup"><span data-stu-id="36e55-180">In this illustration, the tenant has:</span></span>

- <span data-ttu-id="36e55-181">Posizione predefinita corrispondente a un datacenter geografico Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="36e55-181">A default location corresponding to a Microsoft 365 datacenter geo.</span></span>
- <span data-ttu-id="36e55-182">Un insieme di prodotti e licenze.</span><span class="sxs-lookup"><span data-stu-id="36e55-182">A set of products and licenses.</span></span>
- <span data-ttu-id="36e55-183">L'insieme delle app per la produttività del cloud, alcune delle quali specifiche per i prodotti.</span><span class="sxs-lookup"><span data-stu-id="36e55-183">The set of cloud productivity apps, some of which are specific to products.</span></span>
- <span data-ttu-id="36e55-184">Un tenant di Azure AD contenente account di amministratore globale e un nome di dominio DNS iniziale.</span><span class="sxs-lookup"><span data-stu-id="36e55-184">An Azure AD tenant that contains global administrator accounts and an initial DNS domain name.</span></span>

<span data-ttu-id="36e55-185">Quando si passa attraverso i passaggi aggiuntivi di questa soluzione, sarà possibile creare questa figura.</span><span class="sxs-lookup"><span data-stu-id="36e55-185">As we move through the additional steps of this solution, we will build out this figure.</span></span>

## <a name="ongoing-maintenance-for-tenants"></a><span data-ttu-id="36e55-186">Manutenzione continua per i tenant</span><span class="sxs-lookup"><span data-stu-id="36e55-186">Ongoing maintenance for tenants</span></span>

<span data-ttu-id="36e55-187">Su base continuativa, potrebbe essere necessario eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="36e55-187">On an ongoing basis, you might need to:</span></span>

- <span data-ttu-id="36e55-188">Aggiungere un nuovo tenant.</span><span class="sxs-lookup"><span data-stu-id="36e55-188">Add a new tenant.</span></span>
- <span data-ttu-id="36e55-189">Aggiungere nuovi prodotti a un tenant con un numero iniziale di licenze.</span><span class="sxs-lookup"><span data-stu-id="36e55-189">Add new products to a tenant with an initial number of licenses.</span></span>
- <span data-ttu-id="36e55-190">Modificare l'insieme delle licenze per un prodotto in un tenant per adeguare la modifica dei requisiti del personale.</span><span class="sxs-lookup"><span data-stu-id="36e55-190">Change the set of licenses for a product in a tenant to adjust for changing staff requirements.</span></span>
- <span data-ttu-id="36e55-191">Spostare i dati di base da un tenant a una nuova posizione geografica del datacenter.</span><span class="sxs-lookup"><span data-stu-id="36e55-191">Move your core data from a tenant to a new datacenter geo location.</span></span>
- <span data-ttu-id="36e55-192">Aggiungere multi-Geo per i requisiti di residenza dei dati.</span><span class="sxs-lookup"><span data-stu-id="36e55-192">Add Multi-Geo for data residency requirements.</span></span>
- <span data-ttu-id="36e55-193">Configurare la collaborazione tra tenant.</span><span class="sxs-lookup"><span data-stu-id="36e55-193">Set up inter-tenant collaboration.</span></span>

## <a name="next-step"></a><span data-ttu-id="36e55-194">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="36e55-194">Next step</span></span>

<span data-ttu-id="36e55-195">[![Passaggio 2. Ottimizzazione del tenant per la rete per l'accesso](../media/tenant-management-overview/tenant-management-step-grid-networking.png)](tenant-management-networking.md)</span><span class="sxs-lookup"><span data-stu-id="36e55-195">[![Step 2. Optimize your tenant for network for access](../media/tenant-management-overview/tenant-management-step-grid-networking.png)](tenant-management-networking.md)</span></span>

<span data-ttu-id="36e55-196">Continuare con la [rete](tenant-management-networking.md) per fornire una rete ottimale da parte dei dipendenti ai servizi cloud di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="36e55-196">Continue with [networking](tenant-management-networking.md) to provide optimal networking from your workers to Microsoft 365 cloud services.</span></span>
