---
title: Microsoft 365 Multi-Geo
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.custom: seo-marvel-apr2020
ms.collection: Strat_SP_gtc
localization_priority: Normal
f1.keywords:
- NOCSH
description: In questo articolo vengono fornite informazioni su come espandere la presenza di Microsoft 365 a più aree geografiche con Microsoft 365 multi-Geo.
ms.openlocfilehash: cf5f655e2b205001c6c16ed05abc33d68324ff15
ms.sourcegitcommit: e53234b1f64ebca00e121da1706c02b3337c35f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "49580698"
---
# <a name="microsoft-365-multi-geo"></a><span data-ttu-id="5ff9b-103">Microsoft 365 Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="5ff9b-103">Microsoft 365 Multi-Geo</span></span>

<span data-ttu-id="5ff9b-104">Con Microsoft 365 Multi-Geo l'organizzazione può espandere la presenza di Microsoft 365 a più paesi/aree geografiche all'interno del tenant esistente.</span><span class="sxs-lookup"><span data-stu-id="5ff9b-104">With Microsoft 365 Multi-Geo, your organization can expand its Microsoft 365 presence to multiple geographic regions and/or countries within your existing tenant.</span></span> <span data-ttu-id="5ff9b-105">Invitare il team degli account Microsoft a iscrivere la propria società multi-nazionale a Microsoft 365 Multi-Geo.</span><span class="sxs-lookup"><span data-stu-id="5ff9b-105">Reach out to your Microsoft Account Team to sign up your Multi-National Company for Microsoft 365 Multi-Geo.</span></span>
  
<span data-ttu-id="5ff9b-106">Con Microsoft 365 Multi-Geo, è possibile effettuare il provisioning e archiviare i dati inattivi nelle posizioni geografiche scelte per soddisfare i requisiti di residenza dei dati e allo stesso tempo sbloccare lo sviluppo globale delle esperienze di produttività moderna per i dipendenti.</span><span class="sxs-lookup"><span data-stu-id="5ff9b-106">With Microsoft 365 Multi-Geo, you can provision and store data at rest in the geo locations that you've chosen to meet data residency requirements, and at the same time unlock your global roll out of modern productivity experiences to your workforce.</span></span>

<span data-ttu-id="5ff9b-107">Per un video introduttivo a Microsoft 365 multi-Geo, vedere [SharePoint Online e OneDrive multi-Geo per controllare dove si trovano i dati](https://www.youtube.com/watch?v=Do9U3JuROhk).</span><span class="sxs-lookup"><span data-stu-id="5ff9b-107">For a video introduction to Microsoft 365 Multi-Geo, see [SharePoint Online and OneDrive Multi-Geo to control where your data resides](https://www.youtube.com/watch?v=Do9U3JuROhk).</span></span>

## <a name="multi-geo-architecture"></a><span data-ttu-id="5ff9b-108">Architettura multi-Geo</span><span class="sxs-lookup"><span data-stu-id="5ff9b-108">Multi-Geo architecture</span></span>

<span data-ttu-id="5ff9b-109">In un ambiente multi-geografico, il tenant di Microsoft 365 è costituito da una posizione centrale (in cui è stato originariamente effettuato il provisioning dell'abbonamento a Microsoft 365) e una o più posizioni satellite.</span><span class="sxs-lookup"><span data-stu-id="5ff9b-109">In a Multi-Geo environment, your Microsoft 365 tenant consists of a central location (where your Microsoft 365 subscription was originally provisioned) and one or more satellite locations.</span></span> <span data-ttu-id="5ff9b-110">In un tenant Multi-Geo, le informazioni su località geografiche, gruppi e le informazioni utente, vengono acquisite in Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="5ff9b-110">In a multi-geo tenant, the information about geo locations, groups, and user information, is mastered in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="5ff9b-111">Poiché le informazioni del tenant sono acquisite in modo centralizzato e sincronizzate in ogni località geografica, la condivisione e le esperienze coinvolgono tutti gli utenti della società.</span><span class="sxs-lookup"><span data-stu-id="5ff9b-111">Because your tenant information is mastered centrally and synchronized into each geo location, sharing and experiences involving anyone from your company contain global awareness.</span></span>

![Schermata della mappa multi-geo dall'interfaccia di amministrazione di SharePoint.](../media/multi-geo-world-map.png)

<span data-ttu-id="5ff9b-113">Si noti che Microsoft 365 Multi-Geo non è progettato principalmente per ottimizzare le prestazioni, ma per soddisfare i requisiti di residenza dei dati.</span><span class="sxs-lookup"><span data-stu-id="5ff9b-113">Note that Microsoft 365 Multi-Geo is not designed for performance optimization, it is designed to meet data residency requirements.</span></span> <span data-ttu-id="5ff9b-114">Per informazioni sull'ottimizzazione delle prestazioni di Microsoft 365, vedere [Pianificazione della rete e ottimizzazione delle prestazioni per Microsoft 365](https://support.office.com/article/e5f1228c-da3c-4654-bf16-d163daee8848) o contattare il gruppo di supporto.</span><span class="sxs-lookup"><span data-stu-id="5ff9b-114">For information about performance optimization for Microsoft 365, see [Network planning and performance tuning for Microsoft 365](https://support.office.com/article/e5f1228c-da3c-4654-bf16-d163daee8848) or contact your support group.</span></span>

## <a name="terminology"></a><span data-ttu-id="5ff9b-115">Terminologia</span><span class="sxs-lookup"><span data-stu-id="5ff9b-115">Terminology</span></span>

<span data-ttu-id="5ff9b-116">Ecco i termini chiave usati nella descrizione di Microsoft 365 Multi-Geo:</span><span class="sxs-lookup"><span data-stu-id="5ff9b-116">Here are the key terms used in describing Microsoft 365 Multi-Geo:</span></span>

- <span data-ttu-id="5ff9b-117">**Posizione centrale** - la posizione geografica in cui è stato effettuato originariamente il provisioning del tenant.</span><span class="sxs-lookup"><span data-stu-id="5ff9b-117">**Central location** - the geo location where your tenant was originally provisioned.</span></span>
- <span data-ttu-id="5ff9b-118">**Amministratore geografico** - un amministratore che può gestire una o più posizioni satellite specificato.</span><span class="sxs-lookup"><span data-stu-id="5ff9b-118">**Geo administrator** - An administrator who can administer one or more specified satellite locations.</span></span>
- <span data-ttu-id="5ff9b-119">**Codice geografico** - un codice di tre lettere per una posizione geografica specificata.</span><span class="sxs-lookup"><span data-stu-id="5ff9b-119">**Geo code** - a three-letter code for a given geo location.</span></span>
- <span data-ttu-id="5ff9b-120">**Posizione geografica** - un'area geografica che può essere usata in un tenant multi-geo per ospitare dati, tra cui cassette postali di Exchange, OneDrive e siti di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="5ff9b-120">**Geo location** – A geographic location that can be used in a multi-geo tenant to host data, including Exchange mailboxes and OneDrive and SharePoint sites.</span></span>
- <span data-ttu-id="5ff9b-121">**Procedure dati posizione (PDL)** - proprietà dell’utente impostata dall'amministratore che indica la posizione geografica in cui si deve eseguire il provisioning della cassetta postale di Exchange di utenti e OneDrive.</span><span class="sxs-lookup"><span data-stu-id="5ff9b-121">**Preferred Data Location (PDL)** – A user property set by the administrator that indicates where the geo location where the users Exchange mailbox and OneDrive should be provisioned.</span></span> <span data-ttu-id="5ff9b-122">Il PDL determina anche se è stato effettuato il provisioning dei siti di SharePoint creati dall'utente.</span><span class="sxs-lookup"><span data-stu-id="5ff9b-122">The PDL also determines where SharePoint sites that are created by the user are provisioned.</span></span>
- <span data-ttu-id="5ff9b-123">**Posizione satellite** - posizioni geografiche in cui i carichi di lavoro di Microsoft 365 con supporto delle funzionalità Multi-Geo (Exchange, SharePoint e OneDrive) sono abilitati in un tenant multi-geografico.</span><span class="sxs-lookup"><span data-stu-id="5ff9b-123">**Satellite location** – The geo locations where the geo-aware Microsoft 365 workloads (SharePoint, OneDrive, and Exchange) are enabled in a multi-geo tenant.</span></span>
- <span data-ttu-id="5ff9b-124">**Tenant** - rappresentazione di un'organizzazione in Microsoft 365 che in genere contiene uno o più domini associati ad essa ad esempio, contoso.com.</span><span class="sxs-lookup"><span data-stu-id="5ff9b-124">**Tenant** – An organization's representation in Microsoft 365 which typically has one or more domains associated with it (for example, contoso.com).</span></span>

## <a name="licensing"></a><span data-ttu-id="5ff9b-125">Licenze</span><span class="sxs-lookup"><span data-stu-id="5ff9b-125">Licensing</span></span>

<span data-ttu-id="5ff9b-126">Microsoft 365 multi-Geo è disponibile come componente aggiuntivo per i seguenti piani di abbonamento Microsoft 365 per i clienti EA con un minimo di 250 postazioni Microsoft 365 nel loro tenant, di cui almeno il 5% deve utilizzare multi-Geo.</span><span class="sxs-lookup"><span data-stu-id="5ff9b-126">Microsoft 365 Multi-Geo is available as an add-on to the following Microsoft 365 subscription plans for EA customers with a minimum of 250 Microsoft 365 seats in their tenant, and a minimum of 5% of those seats using multi-geo.</span></span> <span data-ttu-id="5ff9b-127">Per informazioni dettagliate, contattare il team del proprio account Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5ff9b-127">Please contact your Microsoft account team for details.</span></span>

- <span data-ttu-id="5ff9b-128">Microsoft 365 F1, F3, E3 o E5</span><span class="sxs-lookup"><span data-stu-id="5ff9b-128">Microsoft 365 F1, F3, E3, or E5</span></span>
- <span data-ttu-id="5ff9b-129">Office 365 F3, E1, E3 o E5</span><span class="sxs-lookup"><span data-stu-id="5ff9b-129">Office 365 F3, E1, E3, or E5</span></span>
- <span data-ttu-id="5ff9b-130">Piano 1 o Piano 2 di Exchange Online</span><span class="sxs-lookup"><span data-stu-id="5ff9b-130">Exchange Online Plan 1 or Plan 2</span></span>
- <span data-ttu-id="5ff9b-131">Piano 1 o Piano 2 di OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="5ff9b-131">OneDrive for Business Plan 1 or Plan 2</span></span>
- <span data-ttu-id="5ff9b-132">Piano 1 o Piano 2 di SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="5ff9b-132">SharePoint Online Plan 1 or Plan 2</span></span>

## <a name="microsoft-365-multi-geo-availability"></a><span data-ttu-id="5ff9b-133">Disponibilità di Microsoft 365 Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="5ff9b-133">Microsoft 365 Multi-Geo availability</span></span>

<span data-ttu-id="5ff9b-134">Microsoft 365 Multi-Geo è attualmente disponibile in questi paesi/aree geografiche:</span><span class="sxs-lookup"><span data-stu-id="5ff9b-134">Microsoft 365 Multi-Geo is currently offered in these regions and countries:</span></span>

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

## <a name="getting-started"></a><span data-ttu-id="5ff9b-135">Introduzione</span><span class="sxs-lookup"><span data-stu-id="5ff9b-135">Getting started</span></span>

<span data-ttu-id="5ff9b-136">Seguire questi semplici passaggi per iniziare con Multi-Geo:</span><span class="sxs-lookup"><span data-stu-id="5ff9b-136">Follow these steps to get started with multi-geo:</span></span>

1. <span data-ttu-id="5ff9b-137">Collaborare con il team responsabile dell'account per aggiungere il piano di servizio _Multi-Geo Capabilities in Microsoft 365_.</span><span class="sxs-lookup"><span data-stu-id="5ff9b-137">Work with your account team to add the _Multi-Geo Capabilities in Microsoft 365_ service plan.</span></span> <span data-ttu-id="5ff9b-138">Verranno fornite le procedure per aggiungere il numero di licenze necessarie.</span><span class="sxs-lookup"><span data-stu-id="5ff9b-138">They will guide you to add the number of licenses needed.</span></span> <span data-ttu-id="5ff9b-139">La funzionalità Multi-Geo Capabilities è disponibile per i clienti EA con un minimo di 250 abbonamenti a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5ff9b-139">Multi-Geo feature is available to EA customers with a minimum of 250 Microsoft 365 subscriptions.</span></span>

   <span data-ttu-id="5ff9b-140">Prima di iniziare a usare Microsoft 365 Multi-Geo, Microsoft deve configurare il tenant di Exchange Online per il supporto Multi-Geo.</span><span class="sxs-lookup"><span data-stu-id="5ff9b-140">Before you can start using Microsoft 365 Multi-Geo, Microsoft needs to configure your Exchange Online tenant for multi-geo support.</span></span> <span data-ttu-id="5ff9b-141">La procedura di configurazione, da effettuare una sola volta, viene attivata dopo aver ordinato il piano di servizio *Multi-Geo Capabilities in Microsoft 365* e le licenze saranno visualizzate nel tenant.</span><span class="sxs-lookup"><span data-stu-id="5ff9b-141">This one-time configuration process is triggered after you order the *Multi-Geo Capabilities in Microsoft 365* service plan and the licenses show up in your tenant.</span></span> <span data-ttu-id="5ff9b-142">Le notifiche specifiche del carico di lavoro vengono ricevute nel [centro messaggi di microsoft 365](https://support.office.com/article/38FB3333-BFCC-4340-A37B-DEDA509C2093) dopo che il tenant ha completato il processo di configurazione per ogni carico di lavoro e quindi è possibile iniziare a configurare e utilizzare le funzionalità multi-geo di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5ff9b-142">You will receive workload specific notifications in the [Microsoft 365 message center](https://support.office.com/article/38FB3333-BFCC-4340-A37B-DEDA509C2093) once your tenant has completed the configuration process for each workload, and you then may begin configuring and using your Microsoft 365 Multi-Geo capabilities.</span></span> <span data-ttu-id="5ff9b-143">Il tempo necessario per configurare un tenant per il supporto multi-Geo varia da tenant a tenant, ma la maggior parte dei tenant termina entro un mese dalla ricezione delle licenze per le caratteristiche.</span><span class="sxs-lookup"><span data-stu-id="5ff9b-143">The time required to configure a tenant for Multi-Geo support varies from tenant to tenant, but most tenants finish within a month after receipt of the feature licenses.</span></span> <span data-ttu-id="5ff9b-144">I tenant più grandi o più complessi possono richiedere più tempo per completare il processo di configurazione.</span><span class="sxs-lookup"><span data-stu-id="5ff9b-144">Larger or more complex tenants may require more time to complete the configuration process.</span></span> <span data-ttu-id="5ff9b-145">Contattare il team dell'account per informazioni dettagliate sul tenant specifico se necessario.</span><span class="sxs-lookup"><span data-stu-id="5ff9b-145">Please contact your account team for details on your specific tenant should you require it.</span></span>

2. <span data-ttu-id="5ff9b-146">Leggere [Pianificare l'ambiente Multi-Geo](plan-for-multi-geo.md).</span><span class="sxs-lookup"><span data-stu-id="5ff9b-146">Read [Plan your multi-geo environment](plan-for-multi-geo.md).</span></span>

3. <span data-ttu-id="5ff9b-147">Informazioni sull’[amministrazione di un ambiente Multi-Geo](administering-a-multi-geo-environment.md) e [ sul riscontro degli utenti sull’ambiente](multi-geo-user-experience.md).</span><span class="sxs-lookup"><span data-stu-id="5ff9b-147">Learn about [administering a multi-geo environment](administering-a-multi-geo-environment.md) and [how your users will experience the environment](multi-geo-user-experience.md).</span></span>

4. <span data-ttu-id="5ff9b-148">Quando si è pronti per configurare Microsoft 365 Multi-Geo, [Configurare il tenant per Multi-Geo](multi-geo-tenant-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="5ff9b-148">When you are ready to set up Microsoft 365 Multi-Geo, [configure your tenant for multi-geo](multi-geo-tenant-configuration.md).</span></span>

5. <span data-ttu-id="5ff9b-149">[Impostare la ricerca](configure-search-for-multi-geo.md).</span><span class="sxs-lookup"><span data-stu-id="5ff9b-149">[Set up search](configure-search-for-multi-geo.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5ff9b-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5ff9b-150">See also</span></span>

[<span data-ttu-id="5ff9b-151">Multi-Geo in Exchange Online e OneDrive</span><span class="sxs-lookup"><span data-stu-id="5ff9b-151">Multi-Geo in Exchange Online and OneDrive</span></span>](https://Aka.ms/GoMultiGeo)

[<span data-ttu-id="5ff9b-152">Multi-Geo Capabilities in OneDrive e SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="5ff9b-152">Multi-Geo Capabilities in OneDrive and SharePoint Online</span></span>](multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md)

[<span data-ttu-id="5ff9b-153">Funzionalità Multi-Geo in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="5ff9b-153">Multi-Geo Capabilities in Exchange Online</span></span>](multi-geo-capabilities-in-exchange-online.md)

[<span data-ttu-id="5ff9b-154">Esperienza di Teams in un ambiente multi-geografico</span><span class="sxs-lookup"><span data-stu-id="5ff9b-154">Teams experience in a multi-geo environment</span></span>](https://docs.microsoft.com/microsoftteams/teams-experience-o365odb-spo-multi-geo)
