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
description: Informazioni su come gestire gli account utente, le licenze e i gruppi di Microsoft 365 con PowerShell.
ms.openlocfilehash: 0c6ca6a4165b616097405a9de178c254aa489a3c
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2020
ms.locfileid: "47429987"
---
# <a name="manage-microsoft-365-user-accounts-licenses-and-groups-with-powershell"></a><span data-ttu-id="e8535-103">Gestire gli account utente, le licenze e i gruppi di Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="e8535-103">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>

<span data-ttu-id="e8535-104">*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="e8535-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="e8535-105">Gli amministratori di Microsoft 365 devono gestire gli account utente, le licenze e i gruppi.</span><span class="sxs-lookup"><span data-stu-id="e8535-105">Microsoft 365 administrators need to manage user accounts, licenses, and groups.</span></span> <span data-ttu-id="e8535-106">Anche se è possibile eseguire la maggior parte di queste attività nell'interfaccia di amministrazione di Microsoft 365, alcune sono più semplici in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e8535-106">Although you can do most of these tasks in the Microsoft 365 admin center, some are easier in PowerShell.</span></span>

<span data-ttu-id="e8535-107">Per ulteriori informazioni, vedere gli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="e8535-107">For more information, see the following articles.</span></span>

## <a name="user-accounts"></a><span data-ttu-id="e8535-108">Account utente</span><span class="sxs-lookup"><span data-stu-id="e8535-108">User accounts</span></span>

- [<span data-ttu-id="e8535-109">Creare account utente</span><span class="sxs-lookup"><span data-stu-id="e8535-109">Create user accounts</span></span>](create-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="e8535-110">Visualizzare account utente</span><span class="sxs-lookup"><span data-stu-id="e8535-110">View user accounts</span></span>](view-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="e8535-111">Configurare le proprietà degli account utente</span><span class="sxs-lookup"><span data-stu-id="e8535-111">Configure user account properties</span></span>](configure-user-account-properties-with-microsoft-365-powershell.md)
- [<span data-ttu-id="e8535-112">Assegnare ruoli agli account utente</span><span class="sxs-lookup"><span data-stu-id="e8535-112">Assign roles to user accounts</span></span>](assign-roles-to-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="e8535-113">Eliminare e ripristinare account utente</span><span class="sxs-lookup"><span data-stu-id="e8535-113">Delete and restore user accounts</span></span>](delete-and-restore-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="e8535-114">Bloccare account utente</span><span class="sxs-lookup"><span data-stu-id="e8535-114">Block user accounts</span></span>](block-user-accounts-with-microsoft-365-powershell.md)

## <a name="licenses-and-services"></a><span data-ttu-id="e8535-115">Licenze e servizi</span><span class="sxs-lookup"><span data-stu-id="e8535-115">Licenses and services</span></span>
- [<span data-ttu-id="e8535-116">Visualizzare le licenze e i servizi</span><span class="sxs-lookup"><span data-stu-id="e8535-116">View licenses and services</span></span>](view-licenses-and-services-with-microsoft-365-powershell.md)
- [<span data-ttu-id="e8535-117">Visualizzare gli utenti con licenza e senza licenza</span><span class="sxs-lookup"><span data-stu-id="e8535-117">View licensed and unlicensed users</span></span>](view-licensed-and-unlicensed-users-with-microsoft-365-powershell.md)
- <span data-ttu-id="e8535-118">[Assegnare licenze agli account utente](assign-licenses-to-user-accounts-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="e8535-118">[Assign licenses to user accounts](assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)</span></span>
- [<span data-ttu-id="e8535-119">Visualizzare la licenza dell'account e i dettagli di servizio</span><span class="sxs-lookup"><span data-stu-id="e8535-119">View account license and service details</span></span>](view-account-license-and-service-details-with-microsoft-365-powershell.md)
- [<span data-ttu-id="e8535-120">Disabilitare l'accesso ai servizi</span><span class="sxs-lookup"><span data-stu-id="e8535-120">Disable access to services</span></span>](disable-access-to-services-with-microsoft-365-powershell.md)
  - [<span data-ttu-id="e8535-121">Disabilitare l'accesso a Sway</span><span class="sxs-lookup"><span data-stu-id="e8535-121">Disable access to Sway</span></span>](disable-access-to-sway-with-microsoft-365-powershell.md)
  - [<span data-ttu-id="e8535-122">Disabilitare l'accesso ai servizi durante l'assegnazione di licenze utente</span><span class="sxs-lookup"><span data-stu-id="e8535-122">Disable access to services while assigning user licenses</span></span>](disable-access-to-services-while-assigning-user-licenses.md)
- [<span data-ttu-id="e8535-123">Rimuovere licenze dagli account utente</span><span class="sxs-lookup"><span data-stu-id="e8535-123">Remove licenses from user accounts</span></span>](remove-licenses-from-user-accounts-with-microsoft-365-powershell.md)

## <a name="groups"></a><span data-ttu-id="e8535-124">Gruppi</span><span class="sxs-lookup"><span data-stu-id="e8535-124">Groups</span></span>
- [<span data-ttu-id="e8535-125">Gestire l'appartenenza ai gruppi</span><span class="sxs-lookup"><span data-stu-id="e8535-125">Maintain group membership</span></span>](maintain-group-membership-with-microsoft-365-powershell.md)
- [<span data-ttu-id="e8535-126">Gestire i gruppi di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e8535-126">Manage Microsoft 365 groups</span></span>](manage-microsoft-365-groups-with-powershell.md)
