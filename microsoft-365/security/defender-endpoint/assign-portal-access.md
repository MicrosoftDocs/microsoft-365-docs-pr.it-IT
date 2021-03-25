---
title: Assegnare l'accesso utente a Microsoft Defender Security Center
description: Assegnare l'accesso in lettura e scrittura o di sola lettura al portale di Microsoft Defender per endpoint.
keywords: assegnare ruoli utente, assegnare l'accesso in lettura e scrittura, assegnare l'accesso di sola lettura, utente, ruoli utente, ruoli
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
ms.date: 11/28/2018
ms.technology: mde
ms.openlocfilehash: 71215c4988351644cfa4d79503c097c932caf9d6
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164767"
---
# <a name="assign-user-access-to-microsoft-defender-security-center"></a><span data-ttu-id="01a27-104">Assegnare l'accesso utente a Microsoft Defender Security Center</span><span class="sxs-lookup"><span data-stu-id="01a27-104">Assign user access to Microsoft Defender Security Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="01a27-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="01a27-105">**Applies to:**</span></span>
- <span data-ttu-id="01a27-106">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="01a27-106">Azure Active Directory</span></span>
- <span data-ttu-id="01a27-107">Office 365</span><span class="sxs-lookup"><span data-stu-id="01a27-107">Office 365</span></span>
- [<span data-ttu-id="01a27-108">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="01a27-108">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="01a27-109">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="01a27-109">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="01a27-110">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="01a27-110">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="01a27-111">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="01a27-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="01a27-112">Defender for Endpoint supporta due modi per gestire le autorizzazioni:</span><span class="sxs-lookup"><span data-stu-id="01a27-112">Defender for Endpoint supports two ways to manage permissions:</span></span>

- <span data-ttu-id="01a27-113">**Gestione delle autorizzazioni di base:** impostare le autorizzazioni per l'accesso completo o di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="01a27-113">**Basic permissions management**: Set permissions to either full access or read-only.</span></span>
- <span data-ttu-id="01a27-114">**Controllo degli accessi** in base al ruolo : consente di impostare autorizzazioni granulari definendo i ruoli, assegnando gruppi di utenti di Azure AD ai ruoli e concedendo ai gruppi di utenti l'accesso ai gruppi di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="01a27-114">**Role-based access control (RBAC)**: Set granular permissions by defining roles, assigning Azure AD user groups to the roles, and granting the user groups access to device groups.</span></span> <span data-ttu-id="01a27-115">Per ulteriori informazioni sul controllo degli accessi in base al ruolo, vedere [Manage portal access using role-based access control](rbac.md).</span><span class="sxs-lookup"><span data-stu-id="01a27-115">For more information on RBAC, see [Manage portal access using role-based access control](rbac.md).</span></span>

> [!NOTE]
> <span data-ttu-id="01a27-116">Se sono già state assegnate autorizzazioni di base, è possibile passare a RBAC in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="01a27-116">If you have already assigned basic permissions, you may switch to RBAC anytime.</span></span> <span data-ttu-id="01a27-117">Prima di eseguire il passaggio, considerare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="01a27-117">Consider the following before making the switch:</span></span>
> 
> - <span data-ttu-id="01a27-118">Agli utenti con accesso completo (gli utenti a cui è assegnato il ruolo di amministratore globale o amministratore della sicurezza in Azure AD), viene automaticamente assegnato il ruolo di amministratore predefinito defender per endpoint, che dispone anche dell'accesso completo.</span><span class="sxs-lookup"><span data-stu-id="01a27-118">Users with full access (users that are assigned the Global Administrator or Security Administrator directory role in Azure AD), are automatically assigned the default Defender for Endpoint administrator role, which also has full access.</span></span> <span data-ttu-id="01a27-119">È possibile assegnare ulteriori gruppi di utenti di Azure AD al ruolo di amministratore di Defender for Endpoint dopo il passaggio a RBAC.</span><span class="sxs-lookup"><span data-stu-id="01a27-119">Additional Azure AD user groups can be assigned to the Defender for Endpoint administrator role after switching to RBAC.</span></span>  <span data-ttu-id="01a27-120">Solo gli utenti assegnati al ruolo di amministratore di Defender for Endpoint possono gestire le autorizzazioni tramite RBAC.</span><span class="sxs-lookup"><span data-stu-id="01a27-120">Only users assigned to the Defender for Endpoint administrator role can manage permissions using RBAC.</span></span> 
> - <span data-ttu-id="01a27-121">Gli utenti con accesso di sola lettura (Lettori di sicurezza) perderanno l'accesso al portale finché non viene loro assegnato un ruolo.</span><span class="sxs-lookup"><span data-stu-id="01a27-121">Users that have read-only access (Security Readers) will lose access to the portal until they are assigned a role.</span></span> <span data-ttu-id="01a27-122">Si noti che solo i gruppi di utenti di Azure AD possono essere assegnati a un ruolo in RBAC.</span><span class="sxs-lookup"><span data-stu-id="01a27-122">Note that only Azure AD user groups can be assigned a role under RBAC.</span></span>
> - <span data-ttu-id="01a27-123">Dopo il passaggio al controllo degli accessi in base al ruolo, non sarà possibile tornare a utilizzare la gestione delle autorizzazioni di base.</span><span class="sxs-lookup"><span data-stu-id="01a27-123">After switching to RBAC, you will not be able to switch back to using basic permissions management.</span></span>

## <a name="related-topics"></a><span data-ttu-id="01a27-124">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="01a27-124">Related topics</span></span>

- [<span data-ttu-id="01a27-125">Usare le autorizzazioni di base per accedere al portale</span><span class="sxs-lookup"><span data-stu-id="01a27-125">Use basic permissions to access the portal</span></span>](basic-permissions.md)
- [<span data-ttu-id="01a27-126">Gestire l'accesso al portale tramite RBAC</span><span class="sxs-lookup"><span data-stu-id="01a27-126">Manage portal access using RBAC</span></span>](rbac.md)
