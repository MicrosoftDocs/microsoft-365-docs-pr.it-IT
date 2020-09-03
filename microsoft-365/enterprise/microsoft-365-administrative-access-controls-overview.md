---
title: Controlli di accesso amministrativo in Microsoft 365
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
f1.keywords:
- NOCSH
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom: seo-marvel-apr2020
description: In questo articolo viene fornita una panoramica dei controlli di accesso amministrativo e della categorizzazione dei dati in Microsoft 365.
ms.openlocfilehash: 817a5907566435d021fe78d89b5c9476c04318d0
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332593"
---
# <a name="administrative-access-controls-in-microsoft-365"></a><span data-ttu-id="24daf-103">Controlli di accesso amministrativo in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="24daf-103">Administrative access controls in Microsoft 365</span></span> 

<span data-ttu-id="24daf-104">Microsoft ha investito fortemente nei sistemi e nei controlli che automatizzano la maggior parte delle operazioni di Microsoft 365, limitando intenzionalmente l'accesso ai contenuti dei clienti da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="24daf-104">Microsoft has invested heavily in systems and controls that automate most Microsoft 365 operations while intentionally limiting access to customer content by Microsoft.</span></span> <span data-ttu-id="24daf-105">Gli esseri umani regolano il servizio e il software gestisce il servizio.</span><span class="sxs-lookup"><span data-stu-id="24daf-105">Humans govern the service, and software operates the service.</span></span> <span data-ttu-id="24daf-106">Ciò consente a Microsoft di gestire Microsoft 365 in scala e gestire i rischi di minacce interne ai contenuti dei clienti.</span><span class="sxs-lookup"><span data-stu-id="24daf-106">This enables Microsoft to manage Microsoft 365 at scale and manage the risks of internal threats to customer content.</span></span>

<span data-ttu-id="24daf-107">Per impostazione predefinita, i tecnici Microsoft dispongono di privilegi amministrativi pari a zero e di accesso a zero in piedi ai contenuti dei clienti in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="24daf-107">By default, Microsoft engineers have zero standing administrative privileges and zero standing access to customer content in Microsoft 365.</span></span> <span data-ttu-id="24daf-108">Un tecnico Microsoft può disporre di un accesso limitato, controllato e protetto al contenuto di un cliente per un periodo di tempo limitato.</span><span class="sxs-lookup"><span data-stu-id="24daf-108">A Microsoft engineer can have limited, audited, and secured access to a customer's content for a limited amount of time.</span></span> <span data-ttu-id="24daf-109">L'accesso è necessario solo per le operazioni di servizio e solo quando è approvato da un membro di Microsoft Senior Management.</span><span class="sxs-lookup"><span data-stu-id="24daf-109">Access is only when necessary for service operations and only when approved by a member of Microsoft senior management.</span></span> <span data-ttu-id="24daf-110">Per i clienti con licenza archivio protetto, il cliente fornisce l'approvazione di accesso ai propri contenuti ospitati in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="24daf-110">For Customer Lockbox licensed customers, the customer provides access approval to their content hosted on Microsoft 365.</span></span>

<span data-ttu-id="24daf-111">Microsoft fornisce servizi online utilizzando più moduli di recapito cloud:</span><span class="sxs-lookup"><span data-stu-id="24daf-111">Microsoft provides online services using multiple forms of cloud delivery:</span></span>

- <span data-ttu-id="24daf-112">**Cloud pubblici:** Include versioni multi-tenant di Microsoft 365, Azure e di altri servizi ospitati in Nord America, Sud America, Europa, Asia, Australia e così via.</span><span class="sxs-lookup"><span data-stu-id="24daf-112">**Public clouds:** Includes multi-tenant versions of Microsoft 365, Azure, and other services hosted in North America, South America, Europe, Asia, Australia, etc.</span></span>
- <span data-ttu-id="24daf-113">**Nubi nazionali:** Include tutte le nubi sovrane e di terze parti al di fuori degli Stati Uniti (eccetto quelle riportate in precedenza), ad esempio Microsoft 365 in Cina (gestite da 21Vianet) e Microsoft 365 in Germania (gestite da Microsoft, ma in un modello in cui un amministratore di dati tedesco, Deutsche Telekom, controlla e monitora l'accesso di Microsoft ai dati e ai sistemi dei clienti).</span><span class="sxs-lookup"><span data-stu-id="24daf-113">**National clouds:** Includes all sovereign and third party-operated clouds outside of the United States (except ones noted previously), such as Microsoft 365 in China (operated by 21Vianet), and Microsoft 365 in Germany (operated by Microsoft, but under a model in which a German data trustee, Deutsche Telekom, controls and monitors Microsoft's access to customer data and systems that contain customer data).</span></span>
- <span data-ttu-id="24daf-114">**Cloud governativi:** Include i servizi Microsoft 365 e Azure che sono disponibili per i clienti del governo degli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="24daf-114">**Government clouds:** Includes Microsoft 365 and Azure services that are available to United States government customers.</span></span>

<span data-ttu-id="24daf-115">Ai fini di questo articolo, Microsoft 365 Services include:</span><span class="sxs-lookup"><span data-stu-id="24daf-115">For purposes of this article, Microsoft 365 services include:</span></span>

- [<span data-ttu-id="24daf-116">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="24daf-116">Exchange Online</span></span>](https://docs.microsoft.com/Exchange/exchange-online)
- [<span data-ttu-id="24daf-117">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="24daf-117">Exchange Online Protection</span></span>](https://docs.microsoft.com/Office365/SecurityCompliance/eop/exchange-online-protection-overview)
- [<span data-ttu-id="24daf-118">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="24daf-118">SharePoint Online</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-online)
- [<span data-ttu-id="24daf-119">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="24daf-119">OneDrive for Business</span></span>](https://docs.microsoft.com/OneDrive/onedrive)
- [<span data-ttu-id="24daf-120">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="24daf-120">Skype for Business</span></span>](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online)
- [<span data-ttu-id="24daf-121">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="24daf-121">Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/Teams-overview)
- [<span data-ttu-id="24daf-122">Yammer</span><span class="sxs-lookup"><span data-stu-id="24daf-122">Yammer</span></span>](https://docs.microsoft.com/yammer/yammer-landing-page)

## <a name="microsoft-365-access-controls"></a><span data-ttu-id="24daf-123">Controlli di accesso di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="24daf-123">Microsoft 365 access controls</span></span>

<span data-ttu-id="24daf-124">Per gli scopi di controllo di accesso, Microsoft categorizza i dati di Microsoft 365 come dati dei clienti o altri tipi di dati.</span><span class="sxs-lookup"><span data-stu-id="24daf-124">For access control purposes, Microsoft categorizes Microsoft 365 data as customer data or other types of data.</span></span>

### <a name="customer-data"></a><span data-ttu-id="24daf-125">Dati cliente
</span><span class="sxs-lookup"><span data-stu-id="24daf-125">Customer data</span></span>

<span data-ttu-id="24daf-126">I dati dei clienti sono tutti i dati forniti da o per conto di un cliente quando si utilizzano i servizi Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="24daf-126">Customer data is all data provided by or on behalf of a customer when using Microsoft 365 services.</span></span> <span data-ttu-id="24daf-127">Si tratta di contenuti dei clienti creati o caricati direttamente dagli utenti di Microsoft 365, tra cui:</span><span class="sxs-lookup"><span data-stu-id="24daf-127">This is customer content directly created or uploaded by Microsoft 365 users, including:</span></span>

- <span data-ttu-id="24daf-128">Messaggi di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="24daf-128">Emails</span></span>
- <span data-ttu-id="24daf-129">Contenuto di SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="24daf-129">SharePoint Online content</span></span>
- <span data-ttu-id="24daf-130">Messaggi istantanei</span><span class="sxs-lookup"><span data-stu-id="24daf-130">Instant messages</span></span>
- <span data-ttu-id="24daf-131">Elementi del calendario</span><span class="sxs-lookup"><span data-stu-id="24daf-131">Calendar items</span></span>
- <span data-ttu-id="24daf-132">Documenti</span><span class="sxs-lookup"><span data-stu-id="24daf-132">Documents</span></span>
- <span data-ttu-id="24daf-133">Contacts</span><span class="sxs-lookup"><span data-stu-id="24daf-133">Contacts</span></span>
- <span data-ttu-id="24daf-134">Informazioni identificabili dall'utente finale (EUII) (dati univoci per un utente o che sono collegabili a un singolo utente, ma non include il contenuto del cliente)</span><span class="sxs-lookup"><span data-stu-id="24daf-134">End-user identifiable information (EUII) (data that is unique to a user or that is linkable to an individual user but does not include customer content)</span></span>

### <a name="other-types-of-data"></a><span data-ttu-id="24daf-135">Altri tipi di dati</span><span class="sxs-lookup"><span data-stu-id="24daf-135">Other types of data</span></span>

<span data-ttu-id="24daf-136">Altri tipi di dati includono:</span><span class="sxs-lookup"><span data-stu-id="24daf-136">Other types of data include:</span></span>

- <span data-ttu-id="24daf-137">**Dati account:** Include i dati amministrativi (informazioni fornite dagli amministratori quando eseguono la registrazione o l'acquisto di servizi) e i dati di pagamento (informazioni sugli strumenti di pagamento, ad esempio i dettagli delle carte di credito).</span><span class="sxs-lookup"><span data-stu-id="24daf-137">**Account data:** Includes administrative data (information provided by administrators when they sign-up or purchase services), and payment data (information about payment instruments, such as credit card details).</span></span>
- <span data-ttu-id="24daf-138">**Informazioni identificabili dall'organizzazione:** Include i dati utilizzati per identificare un tenant, i dati di utilizzo e non collegabili a un singolo utente o inclusi nel contenuto del cliente.</span><span class="sxs-lookup"><span data-stu-id="24daf-138">**Organizationally identifiable information:** Includes data used to identify a tenant, usage data, and not linkable to an individual user or included in customer content.</span></span>
- <span data-ttu-id="24daf-139">**Metadati di sistema:** Include i registri dei servizi che contengono le impostazioni di configurazione, lo stato del sistema, gli indirizzi IP di Microsoft e le informazioni tecniche sugli abbonamenti e sui tenant.</span><span class="sxs-lookup"><span data-stu-id="24daf-139">**System metadata:** Includes service logs that contain configuration settings, system status, Microsoft IP addresses, and technical information about subscriptions and tenants.</span></span>

<span data-ttu-id="24daf-140">Microsoft ha stabilito meccanismi di controllo di accesso per garantire che nessuno abbia accesso non autorizzato ai dati dei clienti o ai dati di controllo di accesso.</span><span class="sxs-lookup"><span data-stu-id="24daf-140">Microsoft has established access control mechanisms to ensure that no one has unapproved access to Customer Data or access control data.</span></span> <span data-ttu-id="24daf-141">I dati di controllo di accesso gestiscono l'accesso ad altri tipi di dati o funzioni all'interno dell'ambiente, tra cui l'accesso al contenuto del cliente o EUII, le password Microsoft, i certificati di sicurezza e altri dati correlati all'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="24daf-141">Access control data manages access to other types of data or functions within the environment, including access to customer content or EUII, Microsoft passwords, security certificates, and other authentication-related data.</span></span> <span data-ttu-id="24daf-142">I meccanismi di controllo di accesso proteggono anche dall'accesso fisico, logico o remoto non approvato all'ambiente di produzione Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="24daf-142">Access control mechanisms also guard against unapproved physical, logical, or remote access to the Microsoft 365 production environment.</span></span>

<span data-ttu-id="24daf-143">Sono disponibili tre categorie di controlli di accesso utilizzati da Microsoft per l'utilizzo di Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="24daf-143">There are three categories of access controls used by Microsoft for operating Microsoft 365:</span></span>

- <span data-ttu-id="24daf-144">Controlli di isolamento</span><span class="sxs-lookup"><span data-stu-id="24daf-144">Isolation controls</span></span>
- <span data-ttu-id="24daf-145">Controlli del personale</span><span class="sxs-lookup"><span data-stu-id="24daf-145">Personnel controls</span></span>
- <span data-ttu-id="24daf-146">Controlli di tecnologia</span><span class="sxs-lookup"><span data-stu-id="24daf-146">Technology controls</span></span>

<span data-ttu-id="24daf-147">Quando vengono combinati, questi controlli consentono di prevenire e rilevare azioni dannose in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="24daf-147">When combined, these controls help prevent and detect malicious actions in Microsoft 365.</span></span> <span data-ttu-id="24daf-148">Oltre ai controlli di isolamento, del personale e della tecnologia utilizzati da Microsoft, esiste una quarta categoria di controlli: quelli implementati dai clienti.</span><span class="sxs-lookup"><span data-stu-id="24daf-148">In addition to the isolation, personnel, and technology controls used by Microsoft, there is a fourth category of controls: those implemented by customers.</span></span>

<span data-ttu-id="24daf-149">Microsoft 365 consente di gestire i dati allo stesso modo in cui i dati vengono gestiti in ambienti locali.</span><span class="sxs-lookup"><span data-stu-id="24daf-149">Microsoft 365 allows you to manage data the same way data is managed in on-premises environments.</span></span> <span data-ttu-id="24daf-150">La persona che firma un'organizzazione per Microsoft 365 diventa automaticamente un amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="24daf-150">The person who signs up an organization for Microsoft 365 automatically becomes a global administrator.</span></span> <span data-ttu-id="24daf-151">L'amministratore globale ha accesso a tutte le funzionalità nei portali di gestione e può:</span><span class="sxs-lookup"><span data-stu-id="24daf-151">The global admin has access to all features in management portals and can:</span></span>

- <span data-ttu-id="24daf-152">Creare o modificare gli utenti</span><span class="sxs-lookup"><span data-stu-id="24daf-152">Create or edit users</span></span>
- <span data-ttu-id="24daf-153">Assegnare ruoli di amministratore ad altri utenti</span><span class="sxs-lookup"><span data-stu-id="24daf-153">Assign admin roles to others</span></span>
- <span data-ttu-id="24daf-154">Reimposta password utente</span><span class="sxs-lookup"><span data-stu-id="24daf-154">Reset user passwords</span></span>
- <span data-ttu-id="24daf-155">Gestire le licenze utente</span><span class="sxs-lookup"><span data-stu-id="24daf-155">Manage user licenses</span></span>
- <span data-ttu-id="24daf-156">Gestire domini</span><span class="sxs-lookup"><span data-stu-id="24daf-156">Manage domains</span></span>
- <span data-ttu-id="24daf-157">Approvare le richieste dell'archivio clienti</span><span class="sxs-lookup"><span data-stu-id="24daf-157">Approve Customer Lockbox requests</span></span>

<span data-ttu-id="24daf-158">È consigliabile che ogni organizzazione configuri almeno due account di amministratore.</span><span class="sxs-lookup"><span data-stu-id="24daf-158">We recommend that each organization configure at least two admin accounts.</span></span> <span data-ttu-id="24daf-159">Per le organizzazioni aziendali di grandi dimensioni, è consigliabile disporre di account di amministrazione specializzati che svolgono funzioni diverse.</span><span class="sxs-lookup"><span data-stu-id="24daf-159">For large enterprise organizations, we recommend specialized admin accounts that serve different functions.</span></span>

<span data-ttu-id="24daf-160">Per informazioni sull'assegnazione di ruoli e autorizzazioni di amministratore, vedere [assegnare ruoli di amministratore](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles) e [informazioni sui ruoli di amministratore](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="24daf-160">For information about assigning admin roles and permissions, see [Assign admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles) and [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>

## <a name="related-links"></a><span data-ttu-id="24daf-161">Collegamenti correlati</span><span class="sxs-lookup"><span data-stu-id="24daf-161">Related Links</span></span>

- [<span data-ttu-id="24daf-162">Controlli di isolamento</span><span class="sxs-lookup"><span data-stu-id="24daf-162">Isolation Controls</span></span>](microsoft-365-isolation-controls.md)
- [<span data-ttu-id="24daf-163">Controlli del personale</span><span class="sxs-lookup"><span data-stu-id="24daf-163">Personnel Controls</span></span>](microsoft-365-personnel-controls.md)
- [<span data-ttu-id="24daf-164">Controlli di tecnologia</span><span class="sxs-lookup"><span data-stu-id="24daf-164">Technology Controls</span></span>](microsoft-365-technology-controls.md)
- [<span data-ttu-id="24daf-165">Monitoraggio e controllo dei controlli di accesso </span><span class="sxs-lookup"><span data-stu-id="24daf-165">Monitoring and Auditing Access Controls</span></span>](microsoft-365-monitoring-and-auditing-access-controls.md)
- [<span data-ttu-id="24daf-166">Controlli di accesso di Yammer Enterprise</span><span class="sxs-lookup"><span data-stu-id="24daf-166">Yammer Enterprise Access Controls</span></span>](microsoft-365-yammer-enterprise-access-controls.md)
