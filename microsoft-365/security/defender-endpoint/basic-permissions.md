---
title: Usare le autorizzazioni di base per accedere a Microsoft Defender Security Center
description: Scopri come usare le autorizzazioni di base per accedere al portale di Microsoft Defender for Endpoint.
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
ms.technology: mde
ms.openlocfilehash: cb5762d2a9e4b62432aba6dacd1033ddc3c7daf2
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163672"
---
# <a name="use-basic-permissions-to-access-the-portal"></a><span data-ttu-id="5328a-104">Usare le autorizzazioni di base per accedere al portale</span><span class="sxs-lookup"><span data-stu-id="5328a-104">Use basic permissions to access the portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5328a-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="5328a-105">**Applies to:**</span></span>
- <span data-ttu-id="5328a-106">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="5328a-106">Azure Active Directory</span></span>
- [<span data-ttu-id="5328a-107">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="5328a-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5328a-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5328a-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="5328a-109">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="5328a-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="5328a-110">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="5328a-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-basicaccess-abovefoldlink)

<span data-ttu-id="5328a-111">Fare riferimento alle istruzioni seguenti per utilizzare la gestione delle autorizzazioni di base.</span><span class="sxs-lookup"><span data-stu-id="5328a-111">Refer to the instructions below to use basic permissions management.</span></span>

<span data-ttu-id="5328a-112">È possibile utilizzare una delle soluzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5328a-112">You can use either of the following solutions:</span></span>
- <span data-ttu-id="5328a-113">Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="5328a-113">Azure PowerShell</span></span>
- <span data-ttu-id="5328a-114">Portale di Azure</span><span class="sxs-lookup"><span data-stu-id="5328a-114">Azure portal</span></span>

<span data-ttu-id="5328a-115">Per un controllo granulare sulle autorizzazioni, [passare al controllo di accesso basato sui ruoli.](rbac.md)</span><span class="sxs-lookup"><span data-stu-id="5328a-115">For granular control over permissions, [switch to role-based access control](rbac.md).</span></span>

## <a name="assign-user-access-using-azure-powershell"></a><span data-ttu-id="5328a-116">Assegnare l'accesso utente tramite Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="5328a-116">Assign user access using Azure PowerShell</span></span>
<span data-ttu-id="5328a-117">È possibile assegnare agli utenti uno dei seguenti livelli di autorizzazioni:</span><span class="sxs-lookup"><span data-stu-id="5328a-117">You can assign users with one of the following levels of permissions:</span></span>
- <span data-ttu-id="5328a-118">Accesso completo (lettura e scrittura)</span><span class="sxs-lookup"><span data-stu-id="5328a-118">Full access (Read and Write)</span></span>
- <span data-ttu-id="5328a-119">Accesso in sola lettura</span><span class="sxs-lookup"><span data-stu-id="5328a-119">Read-only access</span></span>

### <a name="before-you-begin"></a><span data-ttu-id="5328a-120">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="5328a-120">Before you begin</span></span>

- <span data-ttu-id="5328a-121">Installare Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5328a-121">Install Azure PowerShell.</span></span> <span data-ttu-id="5328a-122">Per ulteriori informazioni, vedere [Come installare e configurare Azure PowerShell.](https://azure.microsoft.com/documentation/articles/powershell-install-configure/)</span><span class="sxs-lookup"><span data-stu-id="5328a-122">For more information, see, [How to install and configure Azure PowerShell](https://azure.microsoft.com/documentation/articles/powershell-install-configure/).</span></span><br>

    > [!NOTE]
    > <span data-ttu-id="5328a-123">È necessario eseguire i cmdlet di PowerShell in una riga di comando con privilegi elevati.</span><span class="sxs-lookup"><span data-stu-id="5328a-123">You need to run the PowerShell cmdlets in an elevated command-line.</span></span>

- <span data-ttu-id="5328a-124">Connettersi ad Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5328a-124">Connect to your Azure Active Directory.</span></span> <span data-ttu-id="5328a-125">Per ulteriori informazioni, vedere [Connect-MsolService](https://docs.microsoft.com/powershell/module/msonline/connect-msolservice?view=azureadps-1.0&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="5328a-125">For more information, see [Connect-MsolService](https://docs.microsoft.com/powershell/module/msonline/connect-msolservice?view=azureadps-1.0&preserve-view=true).</span></span>

<span data-ttu-id="5328a-126">**Accesso completo**</span><span class="sxs-lookup"><span data-stu-id="5328a-126">**Full access**</span></span> <br>
<span data-ttu-id="5328a-127">Gli utenti con accesso completo possono accedere, visualizzare tutte le informazioni di sistema e risolvere gli avvisi, inviare file per l'analisi approfondita e scaricare il pacchetto di onboarding.</span><span class="sxs-lookup"><span data-stu-id="5328a-127">Users with full access can log in, view all system information and resolve alerts, submit files for deep analysis, and download the onboarding package.</span></span>
<span data-ttu-id="5328a-128">L'assegnazione dei diritti di accesso completi richiede l'aggiunta degli utenti ai ruoli predefiniti "Amministratore della sicurezza" o "Amministratore globale" di AAD.</span><span class="sxs-lookup"><span data-stu-id="5328a-128">Assigning full access rights requires adding the users to the "Security Administrator" or "Global Administrator" AAD built-in roles.</span></span>

<span data-ttu-id="5328a-129">**Accesso in sola lettura**</span><span class="sxs-lookup"><span data-stu-id="5328a-129">**Read-only access**</span></span> <br>
<span data-ttu-id="5328a-130">Gli utenti con accesso in sola lettura possono accedere, visualizzare tutti gli avvisi e le informazioni correlate.</span><span class="sxs-lookup"><span data-stu-id="5328a-130">Users with read-only access can log in, view all alerts, and related information.</span></span>
<span data-ttu-id="5328a-131">Non saranno in grado di modificare gli stati di avviso, inviare file per l'analisi approfondita o eseguire operazioni di modifica dello stato.</span><span class="sxs-lookup"><span data-stu-id="5328a-131">They will not be able to change alert states, submit files for deep analysis or perform any state changing operations.</span></span>
<span data-ttu-id="5328a-132">L'assegnazione dei diritti di accesso di sola lettura richiede l'aggiunta degli utenti al ruolo predefinito "Lettore di sicurezza" di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="5328a-132">Assigning read-only access rights requires adding the users to the "Security Reader" Azure AD built-in role.</span></span>

<span data-ttu-id="5328a-133">Per assegnare ruoli di sicurezza, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="5328a-133">Use the following steps to assign security roles:</span></span>

- <span data-ttu-id="5328a-134">Per **l'accesso in** lettura e scrittura, assegnare gli utenti al ruolo di amministratore della sicurezza utilizzando il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="5328a-134">For **read and write** access, assign users to the security administrator role by using the following command:</span></span>

  ```PowerShell
  Add-MsolRoleMember -RoleName "Security Administrator" -RoleMemberEmailAddress "secadmin@Contoso.onmicrosoft.com"
  ```
  
- <span data-ttu-id="5328a-135">Per **l'accesso in sola** lettura, assegnare gli utenti al ruolo lettore di sicurezza utilizzando il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="5328a-135">For **read-only** access, assign users to the security reader role by using the following command:</span></span>

  ```PowerShell
  Add-MsolRoleMember -RoleName "Security Reader" -RoleMemberEmailAddress "reader@Contoso.onmicrosoft.com"
  ```

<span data-ttu-id="5328a-136">Per ulteriori informazioni, vedere [Aggiungere o rimuovere membri del gruppo con Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal)</span><span class="sxs-lookup"><span data-stu-id="5328a-136">For more information, see [Add or remove group members using Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal).</span></span>

## <a name="assign-user-access-using-the-azure-portal"></a><span data-ttu-id="5328a-137">Assegnare l'accesso utente tramite il portale di Azure</span><span class="sxs-lookup"><span data-stu-id="5328a-137">Assign user access using the Azure portal</span></span>

<span data-ttu-id="5328a-138">Per ulteriori informazioni, vedere [Assegnare ruoli di amministratore e non amministratore agli utenti con Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)</span><span class="sxs-lookup"><span data-stu-id="5328a-138">For more information, see [Assign administrator and non-administrator roles to users with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).</span></span>

## <a name="related-topic"></a><span data-ttu-id="5328a-139">Argomento correlato</span><span class="sxs-lookup"><span data-stu-id="5328a-139">Related topic</span></span>

- [<span data-ttu-id="5328a-140">Gestire l'accesso al portale tramite RBAC</span><span class="sxs-lookup"><span data-stu-id="5328a-140">Manage portal access using RBAC</span></span>](rbac.md)