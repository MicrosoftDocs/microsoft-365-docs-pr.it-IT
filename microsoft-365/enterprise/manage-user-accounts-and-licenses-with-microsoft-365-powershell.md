---
title: Gestire gli account utente, le licenze e i gruppi di Microsoft 365 con PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- PowerShell
- Ent_Office_Other
- seo-marvel-apr2020
ms.assetid: 26b9ff81-93b0-4251-beaf-3c9f1d7c80c8
description: In questo articolo vengono fornite informazioni su come gestire gli account utente, le licenze e i gruppi di Microsoft 365 con PowerShell.
ms.openlocfilehash: a262cbb62cd457e3a22550af2f773551cf67bb43
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46696108"
---
# <a name="manage-microsoft-365-user-accounts-licenses-and-groups-with-powershell"></a><span data-ttu-id="614cb-103">Gestire gli account utente, le licenze e i gruppi di Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="614cb-103">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>

<span data-ttu-id="614cb-104">*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="614cb-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="614cb-105">Una delle attività principali di qualsiasi amministratore di Microsoft 365 è la gestione degli account utente, delle licenze e dei gruppi.</span><span class="sxs-lookup"><span data-stu-id="614cb-105">One of the primary tasks of any Microsoft 365 administrator is managing user accounts, licenses, and groups.</span></span> <span data-ttu-id="614cb-106">Anche se è possibile eseguire la maggior parte degli aspetti di queste attività nell'interfaccia di amministrazione di Microsoft 365, altre attività sono molto più rapide e facili con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="614cb-106">Although you can accomplish most aspects of these tasks in the Microsoft 365 admin center, other tasks are much quicker and easier with PowerShell.</span></span> 

<span data-ttu-id="614cb-107">Per ulteriori informazioni, vedere questi argomenti.</span><span class="sxs-lookup"><span data-stu-id="614cb-107">For more information, see these topics.</span></span>

## <a name="user-accounts"></a><span data-ttu-id="614cb-108">Account utente</span><span class="sxs-lookup"><span data-stu-id="614cb-108">User accounts</span></span>

- [<span data-ttu-id="614cb-109">Creare account utente</span><span class="sxs-lookup"><span data-stu-id="614cb-109">Create user accounts</span></span>](create-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="614cb-110">Visualizzare account utente</span><span class="sxs-lookup"><span data-stu-id="614cb-110">View user accounts</span></span>](view-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="614cb-111">Configurare le proprietà degli account utente</span><span class="sxs-lookup"><span data-stu-id="614cb-111">Configure user account properties</span></span>](configure-user-account-properties-with-microsoft-365-powershell.md)
- [<span data-ttu-id="614cb-112">Assegnare ruoli agli account utente</span><span class="sxs-lookup"><span data-stu-id="614cb-112">Assign roles to user accounts</span></span>](assign-roles-to-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="614cb-113">Eliminare e ripristinare account utente</span><span class="sxs-lookup"><span data-stu-id="614cb-113">Delete and restore user accounts</span></span>](delete-and-restore-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="614cb-114">Bloccare account utente</span><span class="sxs-lookup"><span data-stu-id="614cb-114">Block user accounts</span></span>](block-user-accounts-with-microsoft-365-powershell.md)

## <a name="licenses-and-services"></a><span data-ttu-id="614cb-115">Licenze e servizi</span><span class="sxs-lookup"><span data-stu-id="614cb-115">Licenses and services</span></span>
- [<span data-ttu-id="614cb-116">Visualizzare le licenze e i servizi</span><span class="sxs-lookup"><span data-stu-id="614cb-116">View licenses and services</span></span>](view-licenses-and-services-with-microsoft-365-powershell.md)
- [<span data-ttu-id="614cb-117">Visualizzare gli utenti con licenza e senza licenza</span><span class="sxs-lookup"><span data-stu-id="614cb-117">View licensed and unlicensed users</span></span>](view-licensed-and-unlicensed-users-with-microsoft-365-powershell.md)
- <span data-ttu-id="614cb-118">[Assegnare licenze agli account utente](assign-licenses-to-user-accounts-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="614cb-118">[Assign licenses to user accounts](assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)</span></span>
- [<span data-ttu-id="614cb-119">Visualizzare la licenza dell'account e i dettagli di servizio</span><span class="sxs-lookup"><span data-stu-id="614cb-119">View account license and service details</span></span>](view-account-license-and-service-details-with-microsoft-365-powershell.md)
- [<span data-ttu-id="614cb-120">Disabilitare l'accesso ai servizi</span><span class="sxs-lookup"><span data-stu-id="614cb-120">Disable access to services</span></span>](disable-access-to-services-with-microsoft-365-powershell.md)
  - [<span data-ttu-id="614cb-121">Disabilitare l'accesso a Sway</span><span class="sxs-lookup"><span data-stu-id="614cb-121">Disable access to Sway</span></span>](disable-access-to-sway-with-microsoft-365-powershell.md)
  - [<span data-ttu-id="614cb-122">Disabilitare l'accesso ai servizi durante l'assegnazione di licenze utente</span><span class="sxs-lookup"><span data-stu-id="614cb-122">Disable access to services while assigning user licenses</span></span>](disable-access-to-services-while-assigning-user-licenses.md)
- [<span data-ttu-id="614cb-123">Rimuovere licenze dagli account utente</span><span class="sxs-lookup"><span data-stu-id="614cb-123">Remove licenses from user accounts</span></span>](remove-licenses-from-user-accounts-with-microsoft-365-powershell.md)

## <a name="groups"></a><span data-ttu-id="614cb-124">Gruppi</span><span class="sxs-lookup"><span data-stu-id="614cb-124">Groups</span></span>
- [<span data-ttu-id="614cb-125">Gestire l'appartenenza ai gruppi</span><span class="sxs-lookup"><span data-stu-id="614cb-125">Maintain group membership</span></span>](maintain-group-membership-with-microsoft-365-powershell.md)
- [<span data-ttu-id="614cb-126">Gestire i gruppi di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="614cb-126">Manage Microsoft 365 groups</span></span>](manage-microsoft-365-groups-with-powershell.md)

