---
title: Gestire gli account utente, le licenze e i gruppi di Microsoft 365 con PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/13/2020
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
description: Informazioni su come gestire gli account utente, le licenze e i gruppi di Microsoft 365 con PowerShell.
ms.openlocfilehash: ec60fcfe3c3d2c0e26cb2cca6a56741067d154c0
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/14/2020
ms.locfileid: "49073126"
---
# <a name="manage-microsoft-365-user-accounts-licenses-and-groups-with-powershell"></a><span data-ttu-id="8b411-103">Gestire gli account utente, le licenze e i gruppi di Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="8b411-103">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>

<span data-ttu-id="8b411-104">*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="8b411-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="8b411-105">Gli amministratori di Microsoft 365 devono gestire gli account utente, le licenze e i gruppi.</span><span class="sxs-lookup"><span data-stu-id="8b411-105">Microsoft 365 administrators need to manage user accounts, licenses, and groups.</span></span> <span data-ttu-id="8b411-106">Anche se è possibile eseguire la maggior parte di queste attività nell'interfaccia di amministrazione di Microsoft 365, alcune sono più semplici in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8b411-106">Although you can do most of these tasks in the Microsoft 365 admin center, some are easier in PowerShell.</span></span>

<span data-ttu-id="8b411-107">Per ulteriori informazioni, vedere gli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="8b411-107">For more information, see the following articles.</span></span>

## <a name="user-accounts"></a><span data-ttu-id="8b411-108">Account utente</span><span class="sxs-lookup"><span data-stu-id="8b411-108">User accounts</span></span>

- [<span data-ttu-id="8b411-109">Creare account utente</span><span class="sxs-lookup"><span data-stu-id="8b411-109">Create user accounts</span></span>](create-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="8b411-110">Visualizzare account utente</span><span class="sxs-lookup"><span data-stu-id="8b411-110">View user accounts</span></span>](view-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="8b411-111">Configurare le proprietà degli account utente</span><span class="sxs-lookup"><span data-stu-id="8b411-111">Configure user account properties</span></span>](configure-user-account-properties-with-microsoft-365-powershell.md)
- [<span data-ttu-id="8b411-112">Assegnare ruoli agli account utente</span><span class="sxs-lookup"><span data-stu-id="8b411-112">Assign roles to user accounts</span></span>](assign-roles-to-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="8b411-113">Eliminare e ripristinare account utente</span><span class="sxs-lookup"><span data-stu-id="8b411-113">Delete and restore user accounts</span></span>](delete-and-restore-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="8b411-114">Bloccare account utente</span><span class="sxs-lookup"><span data-stu-id="8b411-114">Block user accounts</span></span>](block-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="8b411-115">Password</span><span class="sxs-lookup"><span data-stu-id="8b411-115">Passwords</span></span>](manage-passwords-with-microsoft-365-powershell.md)

## <a name="licenses-and-services"></a><span data-ttu-id="8b411-116">Licenze e servizi</span><span class="sxs-lookup"><span data-stu-id="8b411-116">Licenses and services</span></span>
- [<span data-ttu-id="8b411-117">Visualizzare le licenze e i servizi</span><span class="sxs-lookup"><span data-stu-id="8b411-117">View licenses and services</span></span>](view-licenses-and-services-with-microsoft-365-powershell.md)
- [<span data-ttu-id="8b411-118">Visualizzare gli utenti con licenza e senza licenza</span><span class="sxs-lookup"><span data-stu-id="8b411-118">View licensed and unlicensed users</span></span>](view-licensed-and-unlicensed-users-with-microsoft-365-powershell.md)
- <span data-ttu-id="8b411-119">[Assegnare licenze agli account utente](assign-licenses-to-user-accounts-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="8b411-119">[Assign licenses to user accounts](assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)</span></span>
- [<span data-ttu-id="8b411-120">Visualizzare la licenza dell'account e i dettagli di servizio</span><span class="sxs-lookup"><span data-stu-id="8b411-120">View account license and service details</span></span>](view-account-license-and-service-details-with-microsoft-365-powershell.md)
- [<span data-ttu-id="8b411-121">Disabilitare l'accesso ai servizi</span><span class="sxs-lookup"><span data-stu-id="8b411-121">Disable access to services</span></span>](disable-access-to-services-with-microsoft-365-powershell.md)
  - [<span data-ttu-id="8b411-122">Disabilitare l'accesso a Sway</span><span class="sxs-lookup"><span data-stu-id="8b411-122">Disable access to Sway</span></span>](disable-access-to-sway-with-microsoft-365-powershell.md)
  - [<span data-ttu-id="8b411-123">Disabilitare l'accesso ai servizi durante l'assegnazione di licenze utente</span><span class="sxs-lookup"><span data-stu-id="8b411-123">Disable access to services while assigning user licenses</span></span>](disable-access-to-services-while-assigning-user-licenses.md)
- [<span data-ttu-id="8b411-124">Rimuovere licenze dagli account utente</span><span class="sxs-lookup"><span data-stu-id="8b411-124">Remove licenses from user accounts</span></span>](remove-licenses-from-user-accounts-with-microsoft-365-powershell.md)

## <a name="groups"></a><span data-ttu-id="8b411-125">Gruppi</span><span class="sxs-lookup"><span data-stu-id="8b411-125">Groups</span></span>
- [<span data-ttu-id="8b411-126">Gestire l'appartenenza ai gruppi</span><span class="sxs-lookup"><span data-stu-id="8b411-126">Maintain group membership</span></span>](maintain-group-membership-with-microsoft-365-powershell.md)
- [<span data-ttu-id="8b411-127">Gestire i gruppi di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8b411-127">Manage Microsoft 365 groups</span></span>](manage-microsoft-365-groups-with-powershell.md)
