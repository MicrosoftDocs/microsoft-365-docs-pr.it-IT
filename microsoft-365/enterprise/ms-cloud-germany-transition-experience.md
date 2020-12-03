---
title: L'esperienza cliente durante la migrazione ai servizi di Office 365 nelle nuove aree data center tedesche
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
ms.assetid: 706d5449-45e5-4b0c-a012-ab60501899ad
description: "Riepilogo: informazioni sull'esperienza di spostamento da Microsoft Cloud Germany (Microsoft Cloud Deutschland) a servizi di Office 365 nella nuova area datacenter tedesca."
ms.openlocfilehash: a44fbe504a9a710856deeb3baf258feb124ce7ae
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2020
ms.locfileid: "49551696"
---
# <a name="customer-experience-during-the-migration-to-office-365-services-in-the-new-german-datacenter-regions"></a><span data-ttu-id="2a552-103">L'esperienza cliente durante la migrazione ai servizi di Office 365 nelle nuove aree data center tedesche</span><span class="sxs-lookup"><span data-stu-id="2a552-103">Customer experience during the migration to Office 365 services in the new German datacenter regions</span></span>

<span data-ttu-id="2a552-104">Le migrazioni tenant sono progettate in modo da avere un effetto minimo sugli amministratori e sugli utenti.</span><span class="sxs-lookup"><span data-stu-id="2a552-104">Tenant migrations are designed to have minimal effect on administrators and users.</span></span> <span data-ttu-id="2a552-105">Esistono tuttavia alcune considerazioni su ciascun carico di lavoro.</span><span class="sxs-lookup"><span data-stu-id="2a552-105">However, there are considerations for each workload.</span></span> <span data-ttu-id="2a552-106">Leggere le sezioni seguenti per una migliore comprensione dell'esperienza di migrazione per i carichi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="2a552-106">Please review the following sections to have a better understanding of the migration experience for the workloads.</span></span>

<span data-ttu-id="2a552-107">Di seguito sono riportate le principali differenze tra Microsoft Cloud Deutschland e Office 365 Services nelle nuove aree del datacenter tedesco.</span><span class="sxs-lookup"><span data-stu-id="2a552-107">Following are the key differences between Microsoft Cloud Deutschland and Office 365 services in the new German datacenter regions.</span></span>

| <span data-ttu-id="2a552-108">Categoria</span><span class="sxs-lookup"><span data-stu-id="2a552-108">Category</span></span> | <span data-ttu-id="2a552-109">Microsoft Cloud Deutschland (Microsoft Cloud Deutschland)</span><span class="sxs-lookup"><span data-stu-id="2a552-109">Microsoft Cloud Deutschland (Microsoft Cloud Deutschland)</span></span> | <span data-ttu-id="2a552-110">I servizi di Office 365 nelle nuove aree data center tedesche</span><span class="sxs-lookup"><span data-stu-id="2a552-110">Office 365 services in the new German datacenter regions</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="2a552-111">Servizi Microsoft 365 disponibili per la sottoscrizione a un solo tenant di Office 365</span><span class="sxs-lookup"><span data-stu-id="2a552-111">Microsoft 365 services available for subscription with just one Office 365 tenant</span></span> | <span data-ttu-id="2a552-112">15 servizi</span><span class="sxs-lookup"><span data-stu-id="2a552-112">15 services</span></span> | <span data-ttu-id="2a552-113">29 servizi</span><span class="sxs-lookup"><span data-stu-id="2a552-113">29 services</span></span> <br><br> <span data-ttu-id="2a552-114">Per ulteriori informazioni, vedere [Qual è la disponibilità del servizio tra le diverse offerte di servizi cloud di Office 365?](ms-cloud-germany-transition.md#serv-avail).</span><span class="sxs-lookup"><span data-stu-id="2a552-114">For more information, see [What is the service availability between the different Office 365 cloud service offerings?](ms-cloud-germany-transition.md#serv-avail).</span></span> |
| <span data-ttu-id="2a552-115">Nuove funzionalità</span><span class="sxs-lookup"><span data-stu-id="2a552-115">New features</span></span> | <span data-ttu-id="2a552-116">Nessuna nuova funzionalità disponibile.</span><span class="sxs-lookup"><span data-stu-id="2a552-116">No new features are available.</span></span> | <span data-ttu-id="2a552-117">Le nuove funzionalità saranno disponibili in modo coerente con i servizi di Office 365.</span><span class="sxs-lookup"><span data-stu-id="2a552-117">New features will be available consistent with Office 365 services.</span></span> |
| <span data-ttu-id="2a552-118">Trustee dei dati</span><span class="sxs-lookup"><span data-stu-id="2a552-118">Data trustee</span></span> | <span data-ttu-id="2a552-119">Sì</span><span class="sxs-lookup"><span data-stu-id="2a552-119">Yes</span></span> | <span data-ttu-id="2a552-120">No</span><span class="sxs-lookup"><span data-stu-id="2a552-120">No</span></span> |
| <span data-ttu-id="2a552-121">Collaborazione tra il tenant e i tenant globali di Office 365</span><span class="sxs-lookup"><span data-stu-id="2a552-121">Cross-tenant collaboration with global Office 365 tenants</span></span> | <span data-ttu-id="2a552-122">No</span><span class="sxs-lookup"><span data-stu-id="2a552-122">No</span></span> | <span data-ttu-id="2a552-123">Sì</span><span class="sxs-lookup"><span data-stu-id="2a552-123">Yes</span></span> |
| <span data-ttu-id="2a552-124">Residenza dei dati dei clienti</span><span class="sxs-lookup"><span data-stu-id="2a552-124">Customer data residency</span></span> | <span data-ttu-id="2a552-125">I dati dei clienti verranno archiviati esclusivamente all'interno dei data center tedeschi.</span><span class="sxs-lookup"><span data-stu-id="2a552-125">Customer data will be stored solely within German data centers.</span></span> | <span data-ttu-id="2a552-126">Microsoft memorizzerà i seguenti dati dei clienti a riposo esclusivamente in Germania:</span><span class="sxs-lookup"><span data-stu-id="2a552-126">Microsoft will store the following Customer Data at rest exclusively within Germany:</span></span> <ul><li> <span data-ttu-id="2a552-127">Contenuto delle cassette postali di Exchange Online (corpo del messaggio di posta elettronica, voci del calendario e contenuto degli allegati di posta elettronica)</span><span class="sxs-lookup"><span data-stu-id="2a552-127">Exchange Online mailbox content (e-mail body, calendar entries, and the content of e-mail attachments)</span></span> </li><li> <span data-ttu-id="2a552-128">Contenuto del sito di SharePoint Online e file archiviati all'interno del sito e file caricati in OneDrive for business</span><span class="sxs-lookup"><span data-stu-id="2a552-128">SharePoint Online site content and the files stored within that site, and files uploaded to OneDrive for Business</span></span> </li></ul> |
| <span data-ttu-id="2a552-129">Condizioni applicabili</span><span class="sxs-lookup"><span data-stu-id="2a552-129">Applicable terms</span></span> | <span data-ttu-id="2a552-130">[Termini dei servizi online](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46) con questo [supplemento](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=64)</span><span class="sxs-lookup"><span data-stu-id="2a552-130">[Online Services Terms](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46) with this [supplement](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=64)</span></span> | [<span data-ttu-id="2a552-131">Condizioni dei Servizi online</span><span class="sxs-lookup"><span data-stu-id="2a552-131">Online Services Terms</span></span>](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46) |
||||

## <a name="azure-active-directory"></a><span data-ttu-id="2a552-132">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="2a552-132">Azure Active Directory</span></span>

<span data-ttu-id="2a552-133">Cosa non cambia:</span><span class="sxs-lookup"><span data-stu-id="2a552-133">What isn't changing:</span></span>

- <span data-ttu-id="2a552-134">Il dominio iniziale del tenant, ad esempio, `contoso.onmicrosoft.de` con ID tenant (Guid) e domini personalizzati persisterà dopo la migrazione.</span><span class="sxs-lookup"><span data-stu-id="2a552-134">Tenant initial domain (such as `contoso.onmicrosoft.de`) with tenant ID (GUID) and custom domains will persist after the migration.</span></span> 

- <span data-ttu-id="2a552-135">Le richieste di autenticazione per le risorse di cui è stata eseguita la migrazione a Office 365 Services sono concesse dal servizio di autenticazione di Office 365 Services Azure ( `login.microsoftonline.com` ).</span><span class="sxs-lookup"><span data-stu-id="2a552-135">Authentication requests for resources that are migrated to Office 365 services are granted by the Office 365 services Azure authentication service (`login.microsoftonline.com`).</span></span> <span data-ttu-id="2a552-136">Durante la migrazione, le risorse che rimangono ancora in Office 365 Germany vengono autenticate dal servizio di Azure in Germania esistente ( `login.microsoftonline.de` ).</span><span class="sxs-lookup"><span data-stu-id="2a552-136">During the migration, resources that remain still in Office 365 Germany are authenticated by the existing Germany Azure service (`login.microsoftonline.de`).</span></span>

<span data-ttu-id="2a552-137">Considerazioni da prendere in considerazione:</span><span class="sxs-lookup"><span data-stu-id="2a552-137">Considerations to note:</span></span>

- <span data-ttu-id="2a552-138">Per gli account di dominio gestito, dopo la copia del tenant iniziale di Azure Active Directory (Azure AD) (che è il primo passaggio della migrazione di Azure ad al servizio di Azure AD di Office 365 Services), le modifiche alle password, le modifiche apportate alle password self-service (SSPR) e le reimpostazioni delle password da 365 parte degli amministratori devono essere eseguite dai portali di servizio di</span><span class="sxs-lookup"><span data-stu-id="2a552-138">For managed domain accounts, after copying of the initial Azure Active Directory (Azure AD) tenant is complete (which is the first step of Azure AD migration to the Office 365 services Azure AD service), password changes, self-service password reset (SSPR) changes, and password resets by administrators must be done from the Office 365 service portals.</span></span> <span data-ttu-id="2a552-139">Le richieste di aggiornamento delle password dal servizio Germany non avranno esito positivo, in quanto il tenant di Azure AD è stato migrato ai servizi di Office 365.</span><span class="sxs-lookup"><span data-stu-id="2a552-139">Requests to update passwords from the Germany service won't succeed at this point, because the Azure AD tenant has been migrated to Office 365 services.</span></span> <span data-ttu-id="2a552-140">La reimpostazione delle password di dominio federato non è stata modificata, perché queste sono state completate nella directory locale.</span><span class="sxs-lookup"><span data-stu-id="2a552-140">Resets of federated domain passwords aren't affected, because these are completed in the on-premises directory.</span></span>

- <span data-ttu-id="2a552-141">Gli accessi di Azure sono presentati nel portale in cui l'utente tenta di accedere.</span><span class="sxs-lookup"><span data-stu-id="2a552-141">Azure sign-ins are presented in the portal where the user attempts access.</span></span> <span data-ttu-id="2a552-142">I registri di controllo sono disponibili solo dall'endpoint dei servizi di Office 365 dopo la transizione.</span><span class="sxs-lookup"><span data-stu-id="2a552-142">Audit logs are available from only the Office 365 services endpoint after transition.</span></span> <span data-ttu-id="2a552-143">Prima di eseguire la migrazione fino al completamento della migrazione, è consigliabile salvare i log di accesso e di controllo dal portale Microsoft Cloud Deutschland.</span><span class="sxs-lookup"><span data-stu-id="2a552-143">Before migration through to the completion of migration, you should save sign-in and audit logs from the Microsoft Cloud Deutschland portal.</span></span>

- <span data-ttu-id="2a552-144">Le reimpostazioni delle password, le modifiche alla password, la reimpostazione della password da parte di un amministratore per le organizzazioni gestite (che non utilizzano Active Directory Federation Services) devono essere eseguite tramite il portale dei servizi di Office 365.</span><span class="sxs-lookup"><span data-stu-id="2a552-144">Password resets, password changes, password reset by an administrator for managed organizations (that are not using Active Directory Federation Services) must be performed via the Office 365 services portal.</span></span> <span data-ttu-id="2a552-145">I tentativi degli utenti che accedono ai portali di Microsoft Cloud Deutschland per reimpostare le password avranno esito negativo.</span><span class="sxs-lookup"><span data-stu-id="2a552-145">Attempts by users who access Microsoft Cloud Deutschland portals to reset passwords will fail.</span></span>

- <span data-ttu-id="2a552-146">Le richieste del soggetto dei dati (richieste DSR) del regolamento generale sulla protezione dei dati (GDPR) vengono eseguite dal portale di amministrazione di Office 365 Services Azure per le richieste future.</span><span class="sxs-lookup"><span data-stu-id="2a552-146">General Data Protection Regulation (GDPR) Data Subject Requests (DSRs) are executed from the Office 365 services Azure admin portal for future requests.</span></span> <span data-ttu-id="2a552-147">Tutti i dati di diagnostica legacy o non clienti che risiedono in Microsoft Cloud Deutschland vengono eliminati entro e non oltre 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="2a552-147">Any legacy or non-customer diagnostic data that is resident in Microsoft Cloud Deutschland is deleted at or before 30 days.</span></span>

## <a name="subscriptions--licenses"></a><span data-ttu-id="2a552-148">Abbonamenti & licenze</span><span class="sxs-lookup"><span data-stu-id="2a552-148">Subscriptions & Licenses</span></span>

- <span data-ttu-id="2a552-149">Le sottoscrizioni di Office 365 e Dynamics di Microsoft Cloud Deutschland sono state passate all'area tedesca con la rilocazione di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="2a552-149">Office 365 and Dynamics subscriptions from Microsoft Cloud Deutschland are transitioned to the German region with the Azure AD relocation.</span></span> <span data-ttu-id="2a552-150">L'organizzazione viene quindi aggiornata in modo da riflettere le nuove sottoscrizioni di servizi di Office 365.</span><span class="sxs-lookup"><span data-stu-id="2a552-150">The organization is then updated to reflect new Office 365 services subscriptions.</span></span> <span data-ttu-id="2a552-151">Durante il breve processo di trasferimento della sottoscrizione, le modifiche apportate agli abbonamenti vengono bloccate.</span><span class="sxs-lookup"><span data-stu-id="2a552-151">During the brief subscription transfer process, changes to subscriptions are blocked.</span></span>

- <span data-ttu-id="2a552-152">Poiché il tenant viene inoltrato a servizi di Office 365, le relative sottoscrizioni e licenze specifiche per la Germania sono standardizzate con le nuove offerte di servizi di Office 365.</span><span class="sxs-lookup"><span data-stu-id="2a552-152">As the tenant is transitioned to Office 365 services, its Germany-specific subscriptions and licenses are standardized with new Office 365 services offerings.</span></span> <span data-ttu-id="2a552-153">Per gli abbonamenti a Germania trasferiti sono stati acquistati gli abbonamenti ai servizi di Office 365 corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="2a552-153">Corresponding Office 365 services subscriptions are purchased for the transferred Germany subscriptions.</span></span> <span data-ttu-id="2a552-154">Agli utenti che dispongono di licenze tedesche verranno assegnate le licenze per i servizi di Office 365.</span><span class="sxs-lookup"><span data-stu-id="2a552-154">Users who have Germany licenses will be assigned Office 365 services licenses.</span></span> <span data-ttu-id="2a552-155">Al termine, le sottoscrizioni legacy Germany vengono annullate e rimosse dal tenant corrente dei servizi di Office 365.</span><span class="sxs-lookup"><span data-stu-id="2a552-155">Upon completion, legacy Germany subscriptions are canceled and removed from the current Office 365 services tenant.</span></span>

- <span data-ttu-id="2a552-156">Dopo la migrazione dei singoli carichi di lavoro, le funzionalità aggiuntive vengono rese disponibili tramite i servizi di Office 365 (ad esempio Microsoft Planner e Microsoft Flow) a causa delle nuove sottoscrizioni dei servizi di Office 365.</span><span class="sxs-lookup"><span data-stu-id="2a552-156">After migration of the individual workloads, additional functionality is made available through the Office 365 services (such as Microsoft Planner and Microsoft Flow) because of the new Office 365 services subscriptions.</span></span> <span data-ttu-id="2a552-157">Se appropriato per la propria organizzazione, il tenant o l'amministratore delle licenze può disabilitare i nuovi piani di servizio Man mano che si pianifica la gestione delle modifiche per introdurre i nuovi servizi.</span><span class="sxs-lookup"><span data-stu-id="2a552-157">If appropriate for your organization, the tenant or licensing administrator can disable new service plans as you plan for change management to introduce the new services.</span></span> <span data-ttu-id="2a552-158">Per istruzioni su come disabilitare i piani di servizio assegnati alle licenze degli utenti, vedere [Disable access to Microsoft 365 Services while assigning User licenses](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses).</span><span class="sxs-lookup"><span data-stu-id="2a552-158">For guidance on how to disable service plans that are assigned to users' licenses, see [Disable access to Microsoft 365 services while assigning user licenses](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses).</span></span>

## <a name="exchange-online"></a><span data-ttu-id="2a552-159">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="2a552-159">Exchange Online</span></span>

- <span data-ttu-id="2a552-160">Transizione degli URL delle risorse dall'endpoint legacy Germany `outlook.office.de` all'endpoint dei servizi di Office 365 `outlook.office365.com` dopo la migrazione.</span><span class="sxs-lookup"><span data-stu-id="2a552-160">Exchange resource URLs transition from the legacy Germany endpoint `outlook.office.de` to the Office 365 services endpoint `outlook.office365.com` after the migration.</span></span> <span data-ttu-id="2a552-161">Gli utenti possono accedere alla propria cassetta postale migrata utilizzando l'URL legacy fino al completamento della migrazione.</span><span class="sxs-lookup"><span data-stu-id="2a552-161">Your users may access their migrated mailbox by using the legacy URL until the migration completes.</span></span> <span data-ttu-id="2a552-162">I clienti devono eseguire la transizione degli utenti al nuovo URL appena possibile dopo che la migrazione di Exchange ha iniziato a non influire sulla pensione dell'ambiente Germany.</span><span class="sxs-lookup"><span data-stu-id="2a552-162">Customers should transition users to the new URL as soon as possible after Exchange migration begins to avoid affecting retirement of the Germany environment.</span></span> <span data-ttu-id="2a552-163">Gli URL dei servizi di Office 365 per i servizi Outlook diventano disponibili solo dopo l'avvio della migrazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="2a552-163">The Office 365 services URLs for Outlook services become available only after Exchange migration begins.</span></span>

- <span data-ttu-id="2a552-164">Le cassette postali vengono migrate come processo back-end.</span><span class="sxs-lookup"><span data-stu-id="2a552-164">Mailboxes are migrated as a backend process.</span></span> <span data-ttu-id="2a552-165">Gli utenti dell'organizzazione possono trovarsi in Microsoft Cloud Deutschland o nell'area tedesca durante la transizione e fanno parte della stessa organizzazione di Exchange (nello stesso elenco indirizzi globale).</span><span class="sxs-lookup"><span data-stu-id="2a552-165">Users in your organization may be in either Microsoft Cloud Deutschland or the German region during the transition and are part of the same Exchange organization (in the same global address list).</span></span>

- <span data-ttu-id="2a552-166">Gli utenti di Outlook Web App che accedono al servizio utilizzando un URL in cui la cassetta postale non risiede vedranno un prompt di autenticazione supplementare.</span><span class="sxs-lookup"><span data-stu-id="2a552-166">Users of the Outlook Web App who access the service by using a URL where their mailbox does not reside will see an extra authentication prompt.</span></span> <span data-ttu-id="2a552-167">Ad esempio, se la cassetta postale dell'utente si trova nei servizi di Office 365 e la connessione Outlook Web App dell'utente utilizza l'endpoint legacy `outlook.office.de` , l'utente eseguirà prima l'autenticazione a `login.microsoftonline.de` e quindi a `login.microsoftonline.com` .</span><span class="sxs-lookup"><span data-stu-id="2a552-167">For example, if the user's mailbox is in the Office 365 services and the user's Outlook Web App connection uses the legacy endpoint `outlook.office.de`, the user will first authenticate to `login.microsoftonline.de`, and then to `login.microsoftonline.com`.</span></span> <span data-ttu-id="2a552-168">Al termine della migrazione, l'utente può accedere al nuovo URL ( `https://outlook.office365.com` ) e vedrà solo la richiesta di accesso singola e prevista.</span><span class="sxs-lookup"><span data-stu-id="2a552-168">When migration is complete, the user can access the new URL (`https://outlook.office365.com`), and they'll see only the single, expected sign-in request.</span></span> 

## <a name="office-services"></a><span data-ttu-id="2a552-169">Servizi di Office</span><span class="sxs-lookup"><span data-stu-id="2a552-169">Office Services</span></span>

<span data-ttu-id="2a552-170">I servizi Office Online sono accessibili tramite `office.de` prima e durante la transizione.</span><span class="sxs-lookup"><span data-stu-id="2a552-170">Office Online services are accessible via `office.de` before and during the transition.</span></span> <span data-ttu-id="2a552-171">Dopo che le cassette postali degli utenti sono state transizione ai servizi di Office 365, gli utenti devono iniziare a utilizzare gli URL dei servizi di Office 365.</span><span class="sxs-lookup"><span data-stu-id="2a552-171">After users' mailboxes are transitioned to the Office 365 services, users should begin to use Office 365 services URLs.</span></span> <span data-ttu-id="2a552-172">Dopo la migrazione dei carichi di lavoro successivi ai servizi di Office 365, l'interfaccia del portale di office.com inizierà a funzionare.</span><span class="sxs-lookup"><span data-stu-id="2a552-172">As subsequent workloads migrate to Office 365 services, their interface from the office.com portal will begin to work.</span></span>

## <a name="exchange-online-protection"></a><span data-ttu-id="2a552-173">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="2a552-173">Exchange Online Protection</span></span>

- <span data-ttu-id="2a552-174">Le funzionalità di Exchange Online Protection (EOP) back-end vengono copiate nella nuova area di Germania.</span><span class="sxs-lookup"><span data-stu-id="2a552-174">Back-end Exchange Online Protection (EOP) features are copied to new Germany region.</span></span>
- <span data-ttu-id="2a552-175">Gli utenti del Centro sicurezza e conformità di Office 365 devono passare all'utilizzo degli URL globali, `https://protection.office.com` come parte della migrazione.</span><span class="sxs-lookup"><span data-stu-id="2a552-175">Office 365 Security and Compliance Center users need to transition to using global URLs, `https://protection.office.com`, as part of the migration.</span></span>

## <a name="skype-for-business-online"></a><span data-ttu-id="2a552-176">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="2a552-176">Skype for Business Online</span></span>

<span data-ttu-id="2a552-177">I clienti esistenti di Skype for Business online verranno trasferiti a Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2a552-177">Existing Skype for Business Online customers will transition to Microsoft Teams.</span></span> <span data-ttu-id="2a552-178">Per ulteriori informazioni, vedere [https://aka.ms/SkypeToTeams-Home](https://aka.ms/SkypeToTeams-Home) .</span><span class="sxs-lookup"><span data-stu-id="2a552-178">For more information, see [https://aka.ms/SkypeToTeams-Home](https://aka.ms/SkypeToTeams-Home).</span></span>

## <a name="office-365-video"></a><span data-ttu-id="2a552-179">Office 365 Video</span><span class="sxs-lookup"><span data-stu-id="2a552-179">Office 365 Video</span></span>

<span data-ttu-id="2a552-180">Il video di Office 365 viene ritirato il 1 ° marzo 2021 e il video di Office 365 non è supportato dopo che è stata completata la migrazione di SharePoint Online alle nuove aree del datacenter tedesco.</span><span class="sxs-lookup"><span data-stu-id="2a552-180">Office 365 Video is being retired on March 1, 2021, and Office 365 Video won't be supported after migration of SharePoint Online to the new German datacenter regions is completed.</span></span> <span data-ttu-id="2a552-181">Il contenuto del video di Office 365 verrà migrato come parte della migrazione di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="2a552-181">Content from Office 365 Video will be migrated as part of migrating SharePoint Online.</span></span> <span data-ttu-id="2a552-182">Tuttavia, i video in Office 365 video non verranno riprodotti nell'interfaccia utente video di Office 365 dopo la migrazione di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="2a552-182">However, videos in Office 365 Video won't play back in the Office 365 Video UI after the SharePoint migration.</span></span> <span data-ttu-id="2a552-183">Per ulteriori informazioni sulla sequenza temporale della migrazione, vedere la [sezione transizione video di Office 365 a Microsoft Stream (Classic)](https://docs.microsoft.com/stream/migrate-from-office-365#microsoft-cloud-deutschland-timeline).</span><span class="sxs-lookup"><span data-stu-id="2a552-183">Learn more about the migration timeline on [Office 365 Video transition to Microsoft Stream (classic) overview](https://docs.microsoft.com/stream/migrate-from-office-365#microsoft-cloud-deutschland-timeline).</span></span>

## <a name="next-step"></a><span data-ttu-id="2a552-184">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="2a552-184">Next step</span></span>

[<span data-ttu-id="2a552-185">Comprendere le operazioni e gli impatti delle fasi di migrazione</span><span class="sxs-lookup"><span data-stu-id="2a552-185">Understand migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)

## <a name="more-information"></a><span data-ttu-id="2a552-186">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="2a552-186">More information</span></span>

<span data-ttu-id="2a552-187">Guida introduttiva:</span><span class="sxs-lookup"><span data-stu-id="2a552-187">Getting started:</span></span>

- [<span data-ttu-id="2a552-188">Migrazione da Microsoft Cloud Deutschland a Office 365 Services nelle nuove aree del datacenter tedesco</span><span class="sxs-lookup"><span data-stu-id="2a552-188">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="2a552-189">Assistenza per la migrazione di Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="2a552-189">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="2a552-190">Come acconsentire esplicitamente a eseguire la migrazione</span><span class="sxs-lookup"><span data-stu-id="2a552-190">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)

<span data-ttu-id="2a552-191">Spostamento attraverso la transizione:</span><span class="sxs-lookup"><span data-stu-id="2a552-191">Moving through the transition:</span></span>

- [<span data-ttu-id="2a552-192">Operazioni e impatto delle fasi di migrazione</span><span class="sxs-lookup"><span data-stu-id="2a552-192">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="2a552-193">Ulteriore prelavoro</span><span class="sxs-lookup"><span data-stu-id="2a552-193">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="2a552-194">Informazioni aggiuntive su [Servizi](ms-cloud-germany-transition-add-general.md), [dispositivi](ms-cloud-germany-transition-add-devices.md), [esperienze](ms-cloud-germany-transition-add-experience.md)e [ad FS](ms-cloud-germany-transition-add-adfs.md).</span><span class="sxs-lookup"><span data-stu-id="2a552-194">Additional information for [services](ms-cloud-germany-transition-add-general.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="2a552-195">App Cloud:</span><span class="sxs-lookup"><span data-stu-id="2a552-195">Cloud apps:</span></span>

- [<span data-ttu-id="2a552-196">Informazioni sul programma di migrazione di Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="2a552-196">Dynamics 365 migration program information</span></span>](https://aka.ms/d365ceoptin)
- [<span data-ttu-id="2a552-197">Informazioni sul programma di migrazione di Power BI</span><span class="sxs-lookup"><span data-stu-id="2a552-197">Power BI migration program information</span></span>](https://aka.ms/pbioptin)
- [<span data-ttu-id="2a552-198">Guida introduttiva all'aggiornamento di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2a552-198">Getting started with your Microsoft Teams upgrade</span></span>](https://aka.ms/SkypeToTeams-Home)