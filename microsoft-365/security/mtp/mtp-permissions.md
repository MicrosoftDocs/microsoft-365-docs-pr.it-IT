---
title: Gestire l'accesso ai dati di Microsoft 365 Defender nel Centro sicurezza Microsoft 365
description: Informazioni su come gestire le autorizzazioni per i dati in Microsoft 365 Defender
keywords: accesso, autorizzazioni, MTP, Microsoft Threat Protection, M365, sicurezza, MCAS, MDATP, Cloud App Security, Microsoft Defender Advanced Threat Protection, ambito, definizione dell’ambito, RBAC
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 6f042b0c6314e8e5f80d40d76159712bc817a01c
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930139"
---
# <a name="manage-access-to-microsoft-365-defender"></a><span data-ttu-id="5c54d-104">Gestire l'accesso a Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5c54d-104">Manage access to Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="5c54d-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="5c54d-105">**Applies to:**</span></span>
- <span data-ttu-id="5c54d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5c54d-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="5c54d-107">Gli account assegnati ai ruoli di Azure Active Directory (AD) seguenti possono accedere alle funzionalità e ai dati di Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="5c54d-107">Accounts assigned the following Azure Active Directory (AD) roles can access Microsoft 365 Defender functionality and data:</span></span>
- <span data-ttu-id="5c54d-108">Amministratore globale</span><span class="sxs-lookup"><span data-stu-id="5c54d-108">Global administrator</span></span>
- <span data-ttu-id="5c54d-109">Amministratore della sicurezza</span><span class="sxs-lookup"><span data-stu-id="5c54d-109">Security administrator</span></span>
- <span data-ttu-id="5c54d-110">Operatore della sicurezza</span><span class="sxs-lookup"><span data-stu-id="5c54d-110">Security Operator</span></span>
- <span data-ttu-id="5c54d-111">Ruolo con autorizzazioni di lettura globali</span><span class="sxs-lookup"><span data-stu-id="5c54d-111">Global Reader</span></span>
- <span data-ttu-id="5c54d-112">Ruolo con autorizzazioni di lettura per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="5c54d-112">Security Reader</span></span>

<span data-ttu-id="5c54d-113">Per rivedere gli account con questi ruoli, [vedere Autorizzazioni nel Centro sicurezza Microsoft 365](https://security.microsoft.com/permissions).</span><span class="sxs-lookup"><span data-stu-id="5c54d-113">To review accounts with these roles, [view Permissions in the Microsoft 365 security center](https://security.microsoft.com/permissions).</span></span>

## <a name="access-to-functionality"></a><span data-ttu-id="5c54d-114">Accesso alle funzionalità</span><span class="sxs-lookup"><span data-stu-id="5c54d-114">Access to functionality</span></span>
<span data-ttu-id="5c54d-115">L’accesso alle funzionalità specifiche è determinato dal [ruolo di Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="5c54d-115">Access to specific functionality is determined by your [Azure AD role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> <span data-ttu-id="5c54d-116">Rivolgersi a un amministratore globale se è necessario accedere a funzionalità specifiche per le quali deve essere assegnato un nuovo ruolo a un utente o a un gruppo di utenti.</span><span class="sxs-lookup"><span data-stu-id="5c54d-116">Contact a global administrator if you need access to specific functionality that requires you or your user group be assigned a new role.</span></span>

### <a name="approve-pending-automated-tasks"></a><span data-ttu-id="5c54d-117">Approva attività automatiche in sospeso</span><span class="sxs-lookup"><span data-stu-id="5c54d-117">Approve pending automated tasks</span></span>
<span data-ttu-id="5c54d-118">[L’indagine automatizzata e la correzione](mtp-autoir-actions.md) possono intervenire sui messaggi di posta elettronica, le regole di invio, i file, i meccanismi di salvataggio e altri elementi trovati durante l’indagine.</span><span class="sxs-lookup"><span data-stu-id="5c54d-118">[Automated investigation and remediation](mtp-autoir-actions.md) can take action on emails, forwarding rules, files, persistence mechanisms, and other artifacts found during investigations.</span></span> <span data-ttu-id="5c54d-119">Per approvare o rifiutare azioni in sospeso che richiedono un'approvazione esplicita, è necessario possedere determinati ruoli in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5c54d-119">To approve or reject pending actions that require explicit approval, you must have certain roles assigned in Microsoft 365.</span></span> <span data-ttu-id="5c54d-120">Per altre informazioni, vedere [Autorizzazioni del centro notifiche](mtp-action-center.md#required-permissions-for-action-center-tasks).</span><span class="sxs-lookup"><span data-stu-id="5c54d-120">To learn more, see [Action center permissions](mtp-action-center.md#required-permissions-for-action-center-tasks).</span></span>

## <a name="access-to-data"></a><span data-ttu-id="5c54d-121">Accesso ai dati</span><span class="sxs-lookup"><span data-stu-id="5c54d-121">Access to data</span></span>
<span data-ttu-id="5c54d-122">L'accesso ai dati di Microsoft 365 Defender può essere controllato utilizzando l'ambito assegnato ai gruppi di utenti in Microsoft Defender for Endpoint role-based access control (RBAC).</span><span class="sxs-lookup"><span data-stu-id="5c54d-122">Access to Microsoft 365 Defender data can be controlled using the scope assigned to user groups in Microsoft Defender for Endpoint role-based access control (RBAC).</span></span> <span data-ttu-id="5c54d-123">Se l'ambito dell'accesso non è stato limitato a un set specifico di dispositivi in Defender for Endpoint, si avrà accesso completo ai dati in Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="5c54d-123">If your access has not been scoped to a specific set of devices in the Defender for Endpoint, you will have full access to data in Microsoft 365 Defender.</span></span> <span data-ttu-id="5c54d-124">Tuttavia, dopo aver definito l'ambito dell'account, verranno visualizzati solo i dati relativi ai dispositivi inclusi nell'ambito.</span><span class="sxs-lookup"><span data-stu-id="5c54d-124">However, once your account is scoped, you will only see data about the devices in your scope.</span></span>

<span data-ttu-id="5c54d-125">Ad esempio, se si appartiene a un solo gruppo di utenti con un ruolo Microsoft Defender for Endpoint e a tale gruppo di utenti è stato assegnato l'accesso solo ai dispositivi di vendita, verranno visualizzati solo i dati relativi ai dispositivi di vendita in Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="5c54d-125">For example, if you belong to only one user group with a Microsoft Defender for Endpoint role and that user group has been given access to sales devices only, you will see only data about sales devices in Microsoft 365 Defender.</span></span> [<span data-ttu-id="5c54d-126">Altre informazioni sulle impostazioni RBAC in Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="5c54d-126">Learn more about RBAC settings in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a><span data-ttu-id="5c54d-127">Controlli di accesso in Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="5c54d-127">Microsoft Cloud App Security access controls</span></span>
<span data-ttu-id="5c54d-128">Durante l'anteprima, Microsoft 365 Defender non applica i controlli di accesso in base alle impostazioni di Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="5c54d-128">During the preview, Microsoft 365 Defender does not enforce access controls based on  Cloud App Security settings.</span></span> <span data-ttu-id="5c54d-129">L'accesso ai dati di Microsoft 365 Defender non è influenzato da queste impostazioni.</span><span class="sxs-lookup"><span data-stu-id="5c54d-129">Access to Microsoft 365 Defender data is not affected by these settings.</span></span>

## <a name="related-topics"></a><span data-ttu-id="5c54d-130">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="5c54d-130">Related topics</span></span>

- [<span data-ttu-id="5c54d-131">Ruoli di Azure AD</span><span class="sxs-lookup"><span data-stu-id="5c54d-131">Azure AD roles</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [<span data-ttu-id="5c54d-132">Controllo degli accessi in base al ruolo di Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="5c54d-132">Microsoft Defender for Endpoint RBAC</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [<span data-ttu-id="5c54d-133">Ruoli di Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="5c54d-133">Cloud App Security roles</span></span>](https://docs.microsoft.com/cloud-app-security/manage-admins)
