---
title: Gestire l'accesso ai dati di Microsoft Threat Protection nel Centro sicurezza Microsoft 365
description: Informazioni su come gestire le autorizzazioni per i dati in Microsoft Threat Protection
keywords: accesso, autorizzazioni, MTP, Microsoft Threat Protection, M365, sicurezza, MCAS, MDATP, Cloud App Security, Microsoft Defender Advanced Threat Protection, ambito, definizione dell’ambito, RBAC
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 96a8694f5cbc7c27d27acbd5ec0aabe8712c6f06
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201076"
---
# <a name="manage-access-to-microsoft-threat-protection"></a><span data-ttu-id="cf701-104">Gestire l’accesso a Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="cf701-104">Manage access to Microsoft Threat Protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="cf701-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="cf701-105">**Applies to:**</span></span>
- <span data-ttu-id="cf701-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="cf701-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="cf701-107">Gli account assegnati ai seguenti ruoli di Azure Active Directory (AD) possono accedere alle funzionalità e ai dati di Microsoft Threat Protection:</span><span class="sxs-lookup"><span data-stu-id="cf701-107">Accounts assigned the following Azure Active Directory (AD) roles can access Microsoft Threat Protection functionality and data:</span></span>
- <span data-ttu-id="cf701-108">Amministratore globale</span><span class="sxs-lookup"><span data-stu-id="cf701-108">Global administrator</span></span>
- <span data-ttu-id="cf701-109">Amministratore della sicurezza</span><span class="sxs-lookup"><span data-stu-id="cf701-109">Security administrator</span></span>
- <span data-ttu-id="cf701-110">Operatore della sicurezza</span><span class="sxs-lookup"><span data-stu-id="cf701-110">Security Operator</span></span>
- <span data-ttu-id="cf701-111">Ruolo con autorizzazioni di lettura globali</span><span class="sxs-lookup"><span data-stu-id="cf701-111">Global Reader</span></span>
- <span data-ttu-id="cf701-112">Ruolo con autorizzazioni di lettura per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="cf701-112">Security Reader</span></span>

<span data-ttu-id="cf701-113">Per rivedere gli account con questi ruoli, [vedere Autorizzazioni nel Centro sicurezza Microsoft 365](https://security.microsoft.com/permissions).</span><span class="sxs-lookup"><span data-stu-id="cf701-113">To review accounts with these roles, [view Permissions in the Microsoft 365 security center](https://security.microsoft.com/permissions).</span></span>

## <a name="access-to-functionality"></a><span data-ttu-id="cf701-114">Accesso alle funzionalità</span><span class="sxs-lookup"><span data-stu-id="cf701-114">Access to functionality</span></span>
<span data-ttu-id="cf701-115">L’accesso alle funzionalità specifiche è determinato dal [ruolo di Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="cf701-115">Access to specific functionality is determined by your [Azure AD role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> <span data-ttu-id="cf701-116">Rivolgersi a un amministratore globale se è necessario accedere a funzionalità specifiche per le quali deve essere assegnato un nuovo ruolo a un utente o a un gruppo di utenti.</span><span class="sxs-lookup"><span data-stu-id="cf701-116">Contact a global administrator if you need access to specific functionality that requires you or your user group be assigned a new role.</span></span>

### <a name="approve-pending-automated-tasks"></a><span data-ttu-id="cf701-117">Approva attività automatiche in sospeso</span><span class="sxs-lookup"><span data-stu-id="cf701-117">Approve pending automated tasks</span></span>
<span data-ttu-id="cf701-118">[L’indagine automatizzata e la correzione](mtp-autoir-actions.md) possono intervenire sui messaggi di posta elettronica, le regole di invio, i file, i meccanismi di salvataggio e altri elementi trovati durante l’indagine.</span><span class="sxs-lookup"><span data-stu-id="cf701-118">[Automated investigation and remediation](mtp-autoir-actions.md) can take action on emails, forwarding rules, files, persistence mechanisms, and other artifacts found during investigations.</span></span> <span data-ttu-id="cf701-119">Per approvare o rifiutare azioni in sospeso che richiedono un'approvazione esplicita, è necessario possedere determinati ruoli in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cf701-119">To approve or reject pending actions that require explicit approval, you must have certain roles assigned in Microsoft 365.</span></span> <span data-ttu-id="cf701-120">Per altre informazioni, vedere [Autorizzazioni del centro notifiche](mtp-action-center.md#required-permissions-for-action-center-tasks).</span><span class="sxs-lookup"><span data-stu-id="cf701-120">To learn more, see [Action center permissions](mtp-action-center.md#required-permissions-for-action-center-tasks).</span></span>

## <a name="access-to-data"></a><span data-ttu-id="cf701-121">Accesso ai dati</span><span class="sxs-lookup"><span data-stu-id="cf701-121">Access to data</span></span>
<span data-ttu-id="cf701-122">È possibile controllare l'accesso ai dati di Microsoft Threat Protection tramite l'ambito assegnato ai gruppi di utenti nel controllo dell'accesso in base ai ruoli di Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="cf701-122">Access to Microsoft Threat Protection data can be controlled using the scope assigned to user groups in Microsoft Defender ATP role-based access control (RBAC).</span></span> <span data-ttu-id="cf701-123">Se l'ambito di accesso non è stato applicato a un set di dispositivi specifico in Microsoft Defender ATP, si avrà accesso completo ai dati di Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="cf701-123">If your access has not been scoped to a specific set of devices in the Microsoft Defender ATP, you will have full access to data in Microsoft Threat Protection.</span></span> <span data-ttu-id="cf701-124">Tuttavia, dopo aver definito l'ambito dell'account, verranno visualizzati solo i dati relativi ai dispositivi inclusi nell'ambito.</span><span class="sxs-lookup"><span data-stu-id="cf701-124">However, once your account is scoped, you will only see data about the devices in your scope.</span></span>

<span data-ttu-id="cf701-125">Ad esempio, se si appartiene a un solo gruppo di utenti con un ruolo di Microsoft Defender ATP a cui è stato concesso l'accesso solo ai dispositivi di vendita, verranno visualizzati solo i dati relativi ai dispositivi di vendita in Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="cf701-125">For example, if you belong to only one user group with a Microsoft Defender ATP role and that user group has been given access to sales devices only, you will see only data about sales devices in Microsoft Threat Protection.</span></span> [<span data-ttu-id="cf701-126">Scopri di più sulle impostazioni del controllo dell'accesso in base ai ruoli in Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="cf701-126">Learn more about RBAC settings in Microsoft Defender ATP</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a><span data-ttu-id="cf701-127">Controlli di accesso in Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="cf701-127">Microsoft Cloud App Security access controls</span></span>
<span data-ttu-id="cf701-128">Durante l'anteprima Microsoft Threat Protection non applica i controlli di accesso in base alle impostazioni di Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="cf701-128">During the preview, Microsoft Threat Protection does not enforce access controls based on  Cloud App Security settings.</span></span> <span data-ttu-id="cf701-129">L'accesso ai dati di Microsoft Threat Protection non dipende da queste impostazioni.</span><span class="sxs-lookup"><span data-stu-id="cf701-129">Access to Microsoft Threat Protection data is not affected by these settings.</span></span>

## <a name="related-topics"></a><span data-ttu-id="cf701-130">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="cf701-130">Related topics</span></span>

- [<span data-ttu-id="cf701-131">Ruoli di Azure AD</span><span class="sxs-lookup"><span data-stu-id="cf701-131">Azure AD roles</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [<span data-ttu-id="cf701-132">Controllo dell'accesso in base ai ruoli di Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="cf701-132">Microsoft Defender ATP RBAC</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [<span data-ttu-id="cf701-133">Ruoli di Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="cf701-133">Cloud App Security roles</span></span>](https://docs.microsoft.com/cloud-app-security/manage-admins)
