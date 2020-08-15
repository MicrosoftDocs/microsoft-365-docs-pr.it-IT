---
title: Microsoft 365 Multi-Geo
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.custom: seo-marvel-apr2020
ms.collection: Strat_SP_gtc
localization_priority: Normal
f1.keywords:
- NOCSH
description: In questo articolo vengono fornite informazioni su come espandere la presenza di Microsoft 365 a più aree geografiche con Microsoft 365 multi-Geo.
ms.openlocfilehash: a5843b98b5d64dfb3872c3d8a5d48c0e56949c02
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691380"
---
# <a name="microsoft-365-multi-geo"></a><span data-ttu-id="2b70b-103">Microsoft 365 Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="2b70b-103">Microsoft 365 Multi-Geo</span></span>

<span data-ttu-id="2b70b-104">Con Microsoft 365 Multi-Geo l'organizzazione può espandere la presenza di Microsoft 365 a più paesi/aree geografiche all'interno del tenant esistente.</span><span class="sxs-lookup"><span data-stu-id="2b70b-104">With Microsoft 365 Multi-Geo, your organization can expand its Microsoft 365 presence to multiple geographic regions and/or countries within your existing tenant.</span></span> <span data-ttu-id="2b70b-105">Invitare il team degli account Microsoft a iscrivere la propria società multi-nazionale a Microsoft 365 Multi-Geo.</span><span class="sxs-lookup"><span data-stu-id="2b70b-105">Reach out to your Microsoft Account Team to sign up your Multi-National Company for Microsoft 365 Multi-Geo.</span></span>
  
<span data-ttu-id="2b70b-106">Con Microsoft 365 Multi-Geo, è possibile effettuare il provisioning e archiviare i dati inattivi nelle posizioni geografiche scelte per soddisfare i requisiti di residenza dei dati e allo stesso tempo sbloccare lo sviluppo globale delle esperienze di produttività moderna per i dipendenti.</span><span class="sxs-lookup"><span data-stu-id="2b70b-106">With Microsoft 365 Multi-Geo, you can provision and store data at rest in the geo locations that you've chosen to meet data residency requirements, and at the same time unlock your global roll out of modern productivity experiences to your workforce.</span></span>

#### <a name="video-introducing-microsoft-365-multi-geo"></a><span data-ttu-id="2b70b-107">Video: Introduzione a Microsoft 365 Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="2b70b-107">Video: Introducing Microsoft 365 Multi-Geo</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1Yk6B?autoplay=false]

<span data-ttu-id="2b70b-108">In un ambiente multi-geografico, il tenant di Microsoft 365 è costituito da una posizione centrale (in cui è stato originariamente effettuato il provisioning dell'abbonamento a Microsoft 365) e una o più posizioni satellite.</span><span class="sxs-lookup"><span data-stu-id="2b70b-108">In a Multi-Geo environment, your Microsoft 365 tenant consists of a central location (where your Microsoft 365 subscription was originally provisioned) and one or more satellite locations.</span></span> <span data-ttu-id="2b70b-109">In un tenant Multi-Geo, le informazioni su località geografiche, gruppi e le informazioni utente, vengono acquisite in Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="2b70b-109">In a multi-geo tenant, the information about geo locations, groups, and user information, is mastered in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="2b70b-110">Poiché le informazioni del tenant sono acquisite in modo centralizzato e sincronizzate in ogni località geografica, la condivisione e le esperienze coinvolgono tutti gli utenti della società.</span><span class="sxs-lookup"><span data-stu-id="2b70b-110">Because your tenant information is mastered centrally and synchronized into each geo location, sharing and experiences involving anyone from your company contain global awareness.</span></span>

![Schermata della mappa multi-geo dall'interfaccia di amministrazione di SharePoint.](../media/multi-geo-world-map.png)

<span data-ttu-id="2b70b-112">Si noti che Microsoft 365 Multi-Geo non è progettato principalmente per ottimizzare le prestazioni, ma per soddisfare i requisiti di residenza dei dati.</span><span class="sxs-lookup"><span data-stu-id="2b70b-112">Note that Microsoft 365 Multi-Geo is not designed for performance optimization, it is designed to meet data residency requirements.</span></span> <span data-ttu-id="2b70b-113">Per informazioni sull'ottimizzazione delle prestazioni di Microsoft 365, vedere [Pianificazione della rete e ottimizzazione delle prestazioni per Microsoft 365](https://support.office.com/article/e5f1228c-da3c-4654-bf16-d163daee8848) o contattare il gruppo di supporto.</span><span class="sxs-lookup"><span data-stu-id="2b70b-113">For information about performance optimization for Microsoft 365, see [Network planning and performance tuning for Microsoft 365](https://support.office.com/article/e5f1228c-da3c-4654-bf16-d163daee8848) or contact your support group.</span></span>

## <a name="terminology"></a><span data-ttu-id="2b70b-114">Terminologia</span><span class="sxs-lookup"><span data-stu-id="2b70b-114">Terminology</span></span>

<span data-ttu-id="2b70b-115">Ecco i termini chiave usati nella descrizione di Microsoft 365 Multi-Geo:</span><span class="sxs-lookup"><span data-stu-id="2b70b-115">Here are the key terms used in describing Microsoft 365 Multi-Geo:</span></span>

- <span data-ttu-id="2b70b-116">**Posizione centrale** - la posizione geografica in cui è stato effettuato originariamente il provisioning del tenant.</span><span class="sxs-lookup"><span data-stu-id="2b70b-116">**Central location** - the geo location where your tenant was originally provisioned.</span></span>
- <span data-ttu-id="2b70b-117">**Amministratore geografico** - un amministratore che può gestire una o più posizioni satellite specificato.</span><span class="sxs-lookup"><span data-stu-id="2b70b-117">**Geo administrator** - An administrator who can administer one or more specified satellite locations.</span></span>
- <span data-ttu-id="2b70b-118">**Codice geografico** - un codice di tre lettere per una posizione geografica specificata.</span><span class="sxs-lookup"><span data-stu-id="2b70b-118">**Geo code** - a three-letter code for a given geo location.</span></span>
- <span data-ttu-id="2b70b-119">**Posizione geografica** - un'area geografica che può essere usata in un tenant multi-geo per ospitare dati, tra cui cassette postali di Exchange, OneDrive e siti di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="2b70b-119">**Geo location** – A geographic location that can be used in a multi-geo tenant to host data, including Exchange mailboxes and OneDrive and SharePoint sites.</span></span>
- <span data-ttu-id="2b70b-120">**Procedure dati posizione (PDL)** - proprietà dell’utente impostata dall'amministratore che indica la posizione geografica in cui si deve eseguire il provisioning della cassetta postale di Exchange di utenti e OneDrive.</span><span class="sxs-lookup"><span data-stu-id="2b70b-120">**Preferred Data Location (PDL)** – A user property set by the administrator that indicates where the geo location where the users Exchange mailbox and OneDrive should be provisioned.</span></span> <span data-ttu-id="2b70b-121">Il PDL determina anche se è stato effettuato il provisioning dei siti di SharePoint creati dall'utente.</span><span class="sxs-lookup"><span data-stu-id="2b70b-121">The PDL also determines where SharePoint sites that are created by the user are provisioned.</span></span>
- <span data-ttu-id="2b70b-122">**Posizione satellite** - posizioni geografiche in cui i carichi di lavoro di Microsoft 365 con supporto delle funzionalità Multi-Geo (Exchange, SharePoint e OneDrive) sono abilitati in un tenant multi-geografico.</span><span class="sxs-lookup"><span data-stu-id="2b70b-122">**Satellite location** – The geo locations where the geo-aware Microsoft 365 workloads (SharePoint, OneDrive, and Exchange) are enabled in a multi-geo tenant.</span></span>
- <span data-ttu-id="2b70b-123">**Tenant** - rappresentazione di un'organizzazione in Microsoft 365 che in genere contiene uno o più domini associati ad essa ad esempio, contoso.com.</span><span class="sxs-lookup"><span data-stu-id="2b70b-123">**Tenant** – An organization's representation in Microsoft 365 which typically has one or more domains associated with it (for example, contoso.com).</span></span>

## <a name="licensing"></a><span data-ttu-id="2b70b-124">Licenze</span><span class="sxs-lookup"><span data-stu-id="2b70b-124">Licensing</span></span>

<span data-ttu-id="2b70b-125">Microsoft 365 multi-Geo è disponibile come componente aggiuntivo per i seguenti piani di abbonamento Microsoft 365 per i clienti EA con un minimo di 250 postazioni Microsoft 365 nel loro tenant, di cui almeno il 5% deve utilizzare multi-Geo.</span><span class="sxs-lookup"><span data-stu-id="2b70b-125">Microsoft 365 Multi-Geo is available as an add-on to the following Microsoft 365 subscription plans for EA customers with a minimum of 250 Microsoft 365 seats in their tenant, and a minimum of 5% of those seats using multi-geo.</span></span> <span data-ttu-id="2b70b-126">Per informazioni dettagliate, contattare il team del proprio account Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2b70b-126">Please contact your Microsoft account team for details.</span></span>

- <span data-ttu-id="2b70b-127">Microsoft 365 F1, E1, E3 o E5</span><span class="sxs-lookup"><span data-stu-id="2b70b-127">Microsoft 365 F1, E1, E3, or E5</span></span>
- <span data-ttu-id="2b70b-128">Piano 1 o Piano 2 di Exchange Online</span><span class="sxs-lookup"><span data-stu-id="2b70b-128">Exchange Online Plan 1 or Plan 2</span></span>
- <span data-ttu-id="2b70b-129">Piano 1 o Piano 2 di OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="2b70b-129">OneDrive for Business Plan 1 or Plan 2</span></span>
- <span data-ttu-id="2b70b-130">Piano 1 o Piano 2 di SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="2b70b-130">SharePoint Online Plan 1 or Plan 2</span></span>

## <a name="microsoft-365-multi-geo-availability"></a><span data-ttu-id="2b70b-131">Disponibilità di Microsoft 365 Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="2b70b-131">Microsoft 365 Multi-Geo availability</span></span>

<span data-ttu-id="2b70b-132">Microsoft 365 Multi-Geo è attualmente disponibile in questi paesi/aree geografiche:</span><span class="sxs-lookup"><span data-stu-id="2b70b-132">Microsoft 365 Multi-Geo is currently offered in these regions and countries:</span></span>

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

## <a name="getting-started"></a><span data-ttu-id="2b70b-133">Introduzione</span><span class="sxs-lookup"><span data-stu-id="2b70b-133">Getting started</span></span>

<span data-ttu-id="2b70b-134">Seguire questi semplici passaggi per iniziare con Multi-Geo:</span><span class="sxs-lookup"><span data-stu-id="2b70b-134">Follow these steps to get started with multi-geo:</span></span>

1. <span data-ttu-id="2b70b-135">Collaborare con il team responsabile dell'account per aggiungere il piano di servizio _Multi-Geo Capabilities in Microsoft 365_.</span><span class="sxs-lookup"><span data-stu-id="2b70b-135">Work with your account team to add the _Multi-Geo Capabilities in Microsoft 365_ service plan.</span></span> <span data-ttu-id="2b70b-136">Verranno fornite le procedure per aggiungere il numero di licenze necessarie.</span><span class="sxs-lookup"><span data-stu-id="2b70b-136">They will guide you to add the number of licenses needed.</span></span> <span data-ttu-id="2b70b-137">La funzionalità Multi-Geo Capabilities è disponibile per i clienti EA con un minimo di 250 abbonamenti a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2b70b-137">Multi-Geo feature is available to EA customers with a minimum of 250 Microsoft 365 subscriptions.</span></span>

   <span data-ttu-id="2b70b-138">Prima di iniziare a usare Microsoft 365 Multi-Geo, Microsoft deve configurare il tenant di Exchange Online per il supporto Multi-Geo.</span><span class="sxs-lookup"><span data-stu-id="2b70b-138">Before you can start using Microsoft 365 Multi-Geo, Microsoft needs to configure your Exchange Online tenant for multi-geo support.</span></span> <span data-ttu-id="2b70b-139">La procedura di configurazione, da effettuare una sola volta, viene attivata dopo aver ordinato il piano di servizio *Multi-Geo Capabilities in Microsoft 365* e le licenze saranno visualizzate nel tenant.</span><span class="sxs-lookup"><span data-stu-id="2b70b-139">This one-time configuration process is triggered after you order the *Multi-Geo Capabilities in Microsoft 365* service plan and the licenses show up in your tenant.</span></span> <span data-ttu-id="2b70b-140">Una volta che vengono applicate le licenze Multi-Geo, si riceveranno notifiche nel [Centro messaggi di Microsoft 365](https://support.office.com/article/38FB3333-BFCC-4340-A37B-DEDA509C2093) e sarà quindi possibile iniziare la configurazione e l'uso delle funzionalità di Microsoft 365 Multi-Geo.</span><span class="sxs-lookup"><span data-stu-id="2b70b-140">You'll receive notifications in the [Microsoft 365 message center](https://support.office.com/article/38FB3333-BFCC-4340-A37B-DEDA509C2093) once your Multi-Geo licenses are applied and you then may begin configuring and using your Microsoft 365 Multi-Geo capabilities.</span></span>

2. <span data-ttu-id="2b70b-141">Leggere [Pianificare l'ambiente Multi-Geo](plan-for-multi-geo.md).</span><span class="sxs-lookup"><span data-stu-id="2b70b-141">Read [Plan your multi-geo environment](plan-for-multi-geo.md).</span></span>

3. <span data-ttu-id="2b70b-142">Informazioni sull’[amministrazione di un ambiente Multi-Geo](administering-a-multi-geo-environment.md) e [ sul riscontro degli utenti sull’ambiente](multi-geo-user-experience.md).</span><span class="sxs-lookup"><span data-stu-id="2b70b-142">Learn about [administering a multi-geo environment](administering-a-multi-geo-environment.md) and [how your users will experience the environment](multi-geo-user-experience.md).</span></span>

4. <span data-ttu-id="2b70b-143">Quando si è pronti per configurare Microsoft 365 Multi-Geo, [Configurare il tenant per Multi-Geo](multi-geo-tenant-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="2b70b-143">When you are ready to set up Microsoft 365 Multi-Geo, [configure your tenant for multi-geo](multi-geo-tenant-configuration.md).</span></span>

5. <span data-ttu-id="2b70b-144">[Impostare la ricerca](configure-search-for-multi-geo.md).</span><span class="sxs-lookup"><span data-stu-id="2b70b-144">[Set up search](configure-search-for-multi-geo.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2b70b-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2b70b-145">See also</span></span>

[<span data-ttu-id="2b70b-146">Multi-Geo in Exchange Online e OneDrive</span><span class="sxs-lookup"><span data-stu-id="2b70b-146">Multi-Geo in Exchange Online and OneDrive</span></span>](https://Aka.ms/GoMultiGeo)

[<span data-ttu-id="2b70b-147">Multi-Geo Capabilities in OneDrive e SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="2b70b-147">Multi-Geo Capabilities in OneDrive and SharePoint Online</span></span>](multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md)

[<span data-ttu-id="2b70b-148">Funzionalità Multi-Geo in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="2b70b-148">Multi-Geo Capabilities in Exchange Online</span></span>](multi-geo-capabilities-in-exchange-online.md)

[<span data-ttu-id="2b70b-149">Esperienza di Teams in un ambiente multi-geografico</span><span class="sxs-lookup"><span data-stu-id="2b70b-149">Teams experience in a multi-geo environment</span></span>](https://docs.microsoft.com/microsoftteams/teams-experience-o365odb-spo-multi-geo)
