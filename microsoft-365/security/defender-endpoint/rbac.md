---
title: Usare il controllo dell'accesso basato sui ruoli per concedere l'accesso specifico a Microsoft Defender Security Center
description: Creare ruoli e gruppi all'interno delle operazioni di sicurezza per concedere l'accesso al portale.
keywords: rbac, role, based, access, control, groups, control, tier, aad
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d95163bd7caf6e05295fc35b3f9c2bf95230dc83
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51063842"
---
# <a name="manage-portal-access-using-role-based-access-control"></a><span data-ttu-id="72d5c-104">Gestire l'accesso al portale tramite il controllo di accesso basato sui ruoli</span><span class="sxs-lookup"><span data-stu-id="72d5c-104">Manage portal access using role-based access control</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="72d5c-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="72d5c-105">**Applies to:**</span></span>
- <span data-ttu-id="72d5c-106">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="72d5c-106">Azure Active Directory</span></span>
- <span data-ttu-id="72d5c-107">Office 365</span><span class="sxs-lookup"><span data-stu-id="72d5c-107">Office 365</span></span>

> <span data-ttu-id="72d5c-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="72d5c-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="72d5c-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="72d5c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-rbac-abovefoldlink)

<span data-ttu-id="72d5c-110">Utilizzando il controllo degli accessi in base ai ruoli (RBAC, Role-Based Access Control), è possibile creare ruoli e gruppi all'interno del team delle operazioni di sicurezza per concedere l'accesso appropriato al portale.</span><span class="sxs-lookup"><span data-stu-id="72d5c-110">Using role-based access control (RBAC), you can create roles and groups within your security operations team to grant appropriate access to the  portal.</span></span> <span data-ttu-id="72d5c-111">In base ai ruoli e ai gruppi creati, si dispone di un controllo accurato sulle operazioni che gli utenti con accesso al portale possono visualizzare e fare.</span><span class="sxs-lookup"><span data-stu-id="72d5c-111">Based on the roles and groups you create, you have fine-grained control over what users with access to the portal can see and do.</span></span> 

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bJ2a]

<span data-ttu-id="72d5c-112">I team delle operazioni di sicurezza con distribuzione geografica di grandi dimensioni in genere adottano un modello basato su livelli per assegnare e autorizzare l'accesso ai portali di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="72d5c-112">Large geo-distributed security operations teams typically adopt a tier-based model to assign and authorize access to security portals.</span></span> <span data-ttu-id="72d5c-113">I livelli tipici includono i tre livelli seguenti:</span><span class="sxs-lookup"><span data-stu-id="72d5c-113">Typical tiers include the following three levels:</span></span>

<span data-ttu-id="72d5c-114">Livello</span><span class="sxs-lookup"><span data-stu-id="72d5c-114">Tier</span></span> | <span data-ttu-id="72d5c-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="72d5c-115">Description</span></span>
:---|:---
<span data-ttu-id="72d5c-116">Livello 1</span><span class="sxs-lookup"><span data-stu-id="72d5c-116">Tier 1</span></span> | <span data-ttu-id="72d5c-117">**Team delle operazioni di sicurezza locale /team IT**</span><span class="sxs-lookup"><span data-stu-id="72d5c-117">**Local security operations team / IT team**</span></span> <br> <span data-ttu-id="72d5c-118">Questo team in genere analizza e analizza gli avvisi contenuti nella georilevazione e si riassegna al livello 2 nei casi in cui è necessaria una correzione attiva.</span><span class="sxs-lookup"><span data-stu-id="72d5c-118">This team usually triages and investigates alerts contained within their geolocation and escalates to Tier 2 in cases where an active remediation is required.</span></span>
<span data-ttu-id="72d5c-119">Livello 2</span><span class="sxs-lookup"><span data-stu-id="72d5c-119">Tier 2</span></span> | <span data-ttu-id="72d5c-120">**Team operativo per la sicurezza regionale**</span><span class="sxs-lookup"><span data-stu-id="72d5c-120">**Regional security operations team**</span></span> <br> <span data-ttu-id="72d5c-121">Questo team può visualizzare tutti i dispositivi per la propria area geografica ed eseguire azioni di correzione.</span><span class="sxs-lookup"><span data-stu-id="72d5c-121">This team can see all the devices for their region and perform remediation actions.</span></span>
<span data-ttu-id="72d5c-122">Livello 3   </span><span class="sxs-lookup"><span data-stu-id="72d5c-122">Tier 3</span></span> | <span data-ttu-id="72d5c-123">**Team globale per le operazioni di sicurezza**</span><span class="sxs-lookup"><span data-stu-id="72d5c-123">**Global security operations team**</span></span> <br> <span data-ttu-id="72d5c-124">Questo team è costituito da esperti di sicurezza e sono autorizzati a visualizzare ed eseguire tutte le azioni dal portale.</span><span class="sxs-lookup"><span data-stu-id="72d5c-124">This team consists of security experts and are authorized to see and perform all actions from the portal.</span></span>

<span data-ttu-id="72d5c-125">Defender for Endpoint RBAC è progettato per supportare il modello di scelta basato sui livelli o sui ruoli e offre un controllo granulare sui ruoli che possono essere visualizzati, sui dispositivi a cui possono accedere e sulle azioni che possono eseguire.</span><span class="sxs-lookup"><span data-stu-id="72d5c-125">Defender for Endpoint RBAC is designed to support your tier- or role-based model of choice and gives you granular control over what roles can see, devices they can access, and actions they can take.</span></span> <span data-ttu-id="72d5c-126">Il framework RBAC è centrato sui controlli seguenti:</span><span class="sxs-lookup"><span data-stu-id="72d5c-126">The RBAC framework is centered around the following controls:</span></span>

- <span data-ttu-id="72d5c-127">**Controllare gli utenti che possono eseguire azioni specifiche**</span><span class="sxs-lookup"><span data-stu-id="72d5c-127">**Control who can take specific action**</span></span>
  - <span data-ttu-id="72d5c-128">Crea ruoli personalizzati e controlla quali funzionalità di Defender for Endpoint possono accedere con granularità.</span><span class="sxs-lookup"><span data-stu-id="72d5c-128">Create custom roles and control what Defender for Endpoint capabilities they can access with granularity.</span></span>
 
- <span data-ttu-id="72d5c-129">**Controllare chi può visualizzare informazioni su gruppi di dispositivi o gruppi specifici**</span><span class="sxs-lookup"><span data-stu-id="72d5c-129">**Control who can see information on specific device group or groups**</span></span>
  - <span data-ttu-id="72d5c-130">[Creare gruppi di dispositivi](machine-groups.md) in base a criteri specifici, ad esempio nomi, tag, domini e altri, quindi concedere loro l'accesso ai ruoli usando un gruppo di utenti di Azure Active Directory (Azure AD) specifico.</span><span class="sxs-lookup"><span data-stu-id="72d5c-130">[Create device groups](machine-groups.md) by specific criteria such as names, tags, domains, and others, then grant role access to them using a specific  Azure Active Directory (Azure AD) user group.</span></span>

<span data-ttu-id="72d5c-131">Per implementare l'accesso basato sui ruoli, è necessario definire i ruoli di amministratore, assegnare le autorizzazioni corrispondenti e assegnare i gruppi di utenti di Azure AD assegnati ai ruoli.</span><span class="sxs-lookup"><span data-stu-id="72d5c-131">To implement role-based access, you'll need to define admin roles, assign corresponding permissions, and assign Azure AD user groups assigned to the roles.</span></span>


### <a name="before-you-begin"></a><span data-ttu-id="72d5c-132">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="72d5c-132">Before you begin</span></span>
<span data-ttu-id="72d5c-133">Prima di utilizzare RBAC, è importante comprendere i ruoli che possono concedere le autorizzazioni e le conseguenze dell'attivazione del controllo degli accessi in base al ruolo.</span><span class="sxs-lookup"><span data-stu-id="72d5c-133">Before using RBAC, it's important that you understand the roles that can grant permissions and the consequences of turning on RBAC.</span></span>


> [!WARNING]
> <span data-ttu-id="72d5c-134">Prima di abilitare la funzionalità, è importante disporre di un ruolo amministratore globale o amministratore della sicurezza in Azure AD e che i gruppi di Azure AD sono pronti per ridurre il rischio di essere bloccati dal portale.</span><span class="sxs-lookup"><span data-stu-id="72d5c-134">Before enabling the feature, it's important that you have a Global Administrator role or Security Administrator role in Azure AD and that you have your Azure AD groups ready to reduce the risk of being locked out of the portal.</span></span> 

<span data-ttu-id="72d5c-135">Quando accedi per la prima volta a Microsoft Defender Security Center, ti viene concesso l'accesso completo o l'accesso in sola lettura.</span><span class="sxs-lookup"><span data-stu-id="72d5c-135">When you first log in to Microsoft Defender Security Center, you're granted either full access or read only access.</span></span> <span data-ttu-id="72d5c-136">I diritti di accesso completo vengono concessi agli utenti con ruoli di amministratore della sicurezza o amministratore globale in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="72d5c-136">Full access rights are granted to users with Security Administrator or Global Administrator roles in Azure AD.</span></span> <span data-ttu-id="72d5c-137">L'accesso in sola lettura viene concesso agli utenti con un ruolo lettore di sicurezza in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="72d5c-137">Read only access is granted to users with a Security Reader role in Azure AD.</span></span> 

<span data-ttu-id="72d5c-138">Un utente con un ruolo di amministratore defender per endpoint globale ha accesso illimitato a tutti i dispositivi, indipendentemente dall'associazione del gruppo di dispositivi e dalle assegnazioni dei gruppi di utenti di Azure AD</span><span class="sxs-lookup"><span data-stu-id="72d5c-138">Someone with a Defender for Endpoint Global administrator role has unrestricted access to all devices, regardless of their device group association and the Azure AD user groups assignments</span></span>

> [!WARNING]
> <span data-ttu-id="72d5c-139">Inizialmente, solo gli utenti con diritti di amministratore globale o amministratore della sicurezza di Azure AD saranno in grado di creare e assegnare ruoli in Microsoft Defender Security Center, pertanto è importante avere i gruppi appropriati pronti in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="72d5c-139">Initially, only those with Azure AD Global Administrator or Security Administrator rights will be able to create and assign roles in Microsoft Defender Security Center, therefore, having the right groups ready in Azure AD is important.</span></span>
>
> <span data-ttu-id="72d5c-140">**Se si attiva il controllo dell'accesso basato sui ruoli, gli utenti con autorizzazioni di sola lettura (ad esempio, gli utenti assegnati al ruolo lettore di Sicurezza di Azure AD) perderanno l'accesso fino a quando non vengono assegnati a un ruolo.**</span><span class="sxs-lookup"><span data-stu-id="72d5c-140">**Turning on role-based access control will cause users with read-only permissions (for example, users assigned to Azure AD Security reader role) to lose access until they are assigned to a role.**</span></span> 
>
><span data-ttu-id="72d5c-141">Agli utenti con autorizzazioni di amministratore viene assegnato automaticamente il ruolo predefinito predefinito di amministratore globale defender per endpoint con autorizzazioni complete.</span><span class="sxs-lookup"><span data-stu-id="72d5c-141">Users with admin permissions are automatically assigned the default built-in Defender for Endpoint global administrator role with full permissions.</span></span> <span data-ttu-id="72d5c-142">Dopo aver scelto di usare RBAC, puoi assegnare altri utenti che non sono amministratori globali o di sicurezza di Azure AD al ruolo di amministratore globale di Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="72d5c-142">After opting in to use RBAC, you can assign additional users that are not Azure AD Global or Security Administrators to the Defender for Endpoint global administrator role.</span></span> 
>
> <span data-ttu-id="72d5c-143">Dopo aver scelto di usare RBAC, non è possibile ripristinare i ruoli iniziali come quando si è effettuato l'accesso al portale per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="72d5c-143">After opting in to use RBAC, you cannot revert to the initial roles as when you first logged into the portal.</span></span> 



## <a name="related-topic"></a><span data-ttu-id="72d5c-144">Argomento correlato</span><span class="sxs-lookup"><span data-stu-id="72d5c-144">Related topic</span></span>
- [<span data-ttu-id="72d5c-145">Creare e gestire gruppi di dispositivi in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="72d5c-145">Create and manage device groups in Microsoft Defender for Endpoint</span></span>](machine-groups.md)
