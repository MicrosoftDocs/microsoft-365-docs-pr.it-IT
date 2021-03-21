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
ms.openlocfilehash: a619a6ff5256b3b70302d1bef4f0bc21bd7ac3e3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927907"
---
# <a name="manage-access-to-microsoft-365-defender-with-azure-active-directory-global-roles"></a><span data-ttu-id="f8aca-104">Gestire l'accesso a Microsoft 365 Defender con i ruoli globali di Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="f8aca-104">Manage access to Microsoft 365 Defender with Azure Active Directory global roles</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f8aca-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="f8aca-105">**Applies to:**</span></span>
- <span data-ttu-id="f8aca-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f8aca-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="f8aca-107">Esistono due modi per gestire l'accesso a Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f8aca-107">There are two ways to manage access to Microsoft 365 Defender</span></span>
- <span data-ttu-id="f8aca-108">**Ruoli globali di Azure Active Directory (AD)**</span><span class="sxs-lookup"><span data-stu-id="f8aca-108">**Global Azure Active Directory (AD) roles**</span></span>
- <span data-ttu-id="f8aca-109">**Accesso al ruolo personalizzato**</span><span class="sxs-lookup"><span data-stu-id="f8aca-109">**Custom role access**</span></span>

<span data-ttu-id="f8aca-110">Gli account assegnati ai ruoli **globali di Azure Active Directory (AD)** seguenti possono accedere ai dati e alle funzionalità di Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="f8aca-110">Accounts assigned the following **Global Azure Active Directory (AD) roles** can access Microsoft 365 Defender functionality and data:</span></span>
- <span data-ttu-id="f8aca-111">Amministratore globale</span><span class="sxs-lookup"><span data-stu-id="f8aca-111">Global administrator</span></span>
- <span data-ttu-id="f8aca-112">Amministratore della sicurezza</span><span class="sxs-lookup"><span data-stu-id="f8aca-112">Security administrator</span></span>
- <span data-ttu-id="f8aca-113">Operatore della sicurezza</span><span class="sxs-lookup"><span data-stu-id="f8aca-113">Security Operator</span></span>
- <span data-ttu-id="f8aca-114">Ruolo con autorizzazioni di lettura globali</span><span class="sxs-lookup"><span data-stu-id="f8aca-114">Global Reader</span></span>
- <span data-ttu-id="f8aca-115">Ruolo con autorizzazioni di lettura per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="f8aca-115">Security Reader</span></span>

<span data-ttu-id="f8aca-116">Per rivedere gli account con questi ruoli, [vedere Autorizzazioni nel Centro sicurezza Microsoft 365](https://security.microsoft.com/permissions).</span><span class="sxs-lookup"><span data-stu-id="f8aca-116">To review accounts with these roles, [view Permissions in the Microsoft 365 security center](https://security.microsoft.com/permissions).</span></span>

<span data-ttu-id="f8aca-117">**L'accesso** ai ruoli personalizzati è una nuova funzionalità di Microsoft 365 Defender e consente di gestire l'accesso a dati, attività e funzionalità specifici in Microsoft Defender 365.</span><span class="sxs-lookup"><span data-stu-id="f8aca-117">**Custom role** access is a new capability in Microsoft 365 Defender and allows you to manage access to specific data, tasks, and capabilities in Microsoft Defender 365.</span></span> <span data-ttu-id="f8aca-118">I ruoli personalizzati offrono un maggiore controllo rispetto ai ruoli globali di Azure AD, fornendo agli utenti solo l'accesso necessario con i ruoli meno permissivi necessari.</span><span class="sxs-lookup"><span data-stu-id="f8aca-118">Custom roles offer more control than global Azure AD roles, providing users only the access they need with the least-permissive roles necessary.</span></span>  <span data-ttu-id="f8aca-119">I ruoli personalizzati possono essere creati oltre ai ruoli globali di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="f8aca-119">Custom roles can be created in addition to global Azure AD roles.</span></span> <span data-ttu-id="f8aca-120">[Ulteriori informazioni sui ruoli personalizzati.](custom-roles.md)</span><span class="sxs-lookup"><span data-stu-id="f8aca-120">[Learn more about custom roles](custom-roles.md).</span></span>

> <span data-ttu-id="f8aca-121">! [NOTA] Questo articolo si applica solo alla gestione dei ruoli globali di Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f8aca-121">![NOTE] This article applies only to managing global Azure Active Directory roles.</span></span> <span data-ttu-id="f8aca-122">Per ulteriori informazioni sull'utilizzo del controllo di accesso basato sui ruoli personalizzato, vedere Ruoli personalizzati per il controllo di [accesso basato sui ruoli.](custom-roles.md)</span><span class="sxs-lookup"><span data-stu-id="f8aca-122">For more information about using custom role-based access control, see [Custom roles for role-based access control](custom-roles.md)</span></span>

## <a name="access-to-functionality"></a><span data-ttu-id="f8aca-123">Accesso alle funzionalità</span><span class="sxs-lookup"><span data-stu-id="f8aca-123">Access to functionality</span></span>
<span data-ttu-id="f8aca-124">L’accesso alle funzionalità specifiche è determinato dal [ruolo di Azure AD](/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="f8aca-124">Access to specific functionality is determined by your [Azure AD role](/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> <span data-ttu-id="f8aca-125">Rivolgersi a un amministratore globale se è necessario accedere a funzionalità specifiche per le quali deve essere assegnato un nuovo ruolo a un utente o a un gruppo di utenti.</span><span class="sxs-lookup"><span data-stu-id="f8aca-125">Contact a global administrator if you need access to specific functionality that requires you or your user group be assigned a new role.</span></span>

### <a name="approve-pending-automated-tasks"></a><span data-ttu-id="f8aca-126">Approva attività automatiche in sospeso</span><span class="sxs-lookup"><span data-stu-id="f8aca-126">Approve pending automated tasks</span></span>
<span data-ttu-id="f8aca-127">[L’indagine automatizzata e la correzione](mtp-autoir-actions.md) possono intervenire sui messaggi di posta elettronica, le regole di invio, i file, i meccanismi di salvataggio e altri elementi trovati durante l’indagine.</span><span class="sxs-lookup"><span data-stu-id="f8aca-127">[Automated investigation and remediation](mtp-autoir-actions.md) can take action on emails, forwarding rules, files, persistence mechanisms, and other artifacts found during investigations.</span></span> <span data-ttu-id="f8aca-128">Per approvare o rifiutare azioni in sospeso che richiedono un'approvazione esplicita, è necessario possedere determinati ruoli in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f8aca-128">To approve or reject pending actions that require explicit approval, you must have certain roles assigned in Microsoft 365.</span></span> <span data-ttu-id="f8aca-129">Per altre informazioni, vedere [Autorizzazioni del centro notifiche](mtp-action-center.md#required-permissions-for-action-center-tasks).</span><span class="sxs-lookup"><span data-stu-id="f8aca-129">To learn more, see [Action center permissions](mtp-action-center.md#required-permissions-for-action-center-tasks).</span></span>

## <a name="access-to-data"></a><span data-ttu-id="f8aca-130">Accesso ai dati</span><span class="sxs-lookup"><span data-stu-id="f8aca-130">Access to data</span></span>
<span data-ttu-id="f8aca-131">L'accesso ai dati di Microsoft 365 Defender può essere controllato utilizzando l'ambito assegnato ai gruppi di utenti in Microsoft Defender for Endpoint role-based access control (RBAC).</span><span class="sxs-lookup"><span data-stu-id="f8aca-131">Access to Microsoft 365 Defender data can be controlled using the scope assigned to user groups in Microsoft Defender for Endpoint role-based access control (RBAC).</span></span> <span data-ttu-id="f8aca-132">Se l'ambito dell'accesso non è stato limitato a un set specifico di dispositivi in Defender for Endpoint, si avrà accesso completo ai dati in Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="f8aca-132">If your access has not been scoped to a specific set of devices in the Defender for Endpoint, you will have full access to data in Microsoft 365 Defender.</span></span> <span data-ttu-id="f8aca-133">Tuttavia, dopo aver definito l'ambito dell'account, verranno visualizzati solo i dati relativi ai dispositivi inclusi nell'ambito.</span><span class="sxs-lookup"><span data-stu-id="f8aca-133">However, once your account is scoped, you will only see data about the devices in your scope.</span></span>

<span data-ttu-id="f8aca-134">Ad esempio, se apparteni a un solo gruppo di utenti con un ruolo Microsoft Defender for Endpoint e a tale gruppo di utenti è stato assegnato l'accesso solo ai dispositivi di vendita, in Microsoft 365 Defender verranno visualizzati solo i dati relativi ai dispositivi di vendita.</span><span class="sxs-lookup"><span data-stu-id="f8aca-134">For example, if you belong to only one user group with a Microsoft Defender for Endpoint role and that user group has been given access to sales devices only, you will see only data about sales devices in Microsoft 365 Defender.</span></span> [<span data-ttu-id="f8aca-135">Altre informazioni sulle impostazioni RBAC in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f8aca-135">Learn more about RBAC settings in Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a><span data-ttu-id="f8aca-136">Controlli di accesso in Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="f8aca-136">Microsoft Cloud App Security access controls</span></span>
<span data-ttu-id="f8aca-137">Durante l'anteprima, Microsoft 365 Defender non applica i controlli di accesso in base alle impostazioni di Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="f8aca-137">During the preview, Microsoft 365 Defender does not enforce access controls based on  Cloud App Security settings.</span></span> <span data-ttu-id="f8aca-138">L'accesso ai dati di Microsoft 365 Defender non è influenzato da queste impostazioni.</span><span class="sxs-lookup"><span data-stu-id="f8aca-138">Access to Microsoft 365 Defender data is not affected by these settings.</span></span>

## <a name="related-topics"></a><span data-ttu-id="f8aca-139">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="f8aca-139">Related topics</span></span>
- [<span data-ttu-id="f8aca-140">Ruoli personalizzati nel controllo di accesso basato sui ruoli per Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f8aca-140">Custom roles in role-based access control for Microsoft 365 Defender</span></span>](custom-roles.md)
- [<span data-ttu-id="f8aca-141">Ruoli di Azure AD</span><span class="sxs-lookup"><span data-stu-id="f8aca-141">Azure AD roles</span></span>](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [<span data-ttu-id="f8aca-142">Controllo degli accessi in base al ruolo di Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="f8aca-142">Microsoft Defender for Endpoint RBAC</span></span>](/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [<span data-ttu-id="f8aca-143">Ruoli di Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="f8aca-143">Cloud App Security roles</span></span>](/cloud-app-security/manage-admins)