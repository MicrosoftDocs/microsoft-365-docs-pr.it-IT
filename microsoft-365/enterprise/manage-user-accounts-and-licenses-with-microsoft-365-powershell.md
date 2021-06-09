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
description: Informazioni su come gestire Microsoft 365 utenti, licenze e gruppi con PowerShell.
ms.openlocfilehash: d3745b9365c67615efe32881408d1a717b8dbbed
ms.sourcegitcommit: bdf65d48b20f0f428162c39ee997accfa84f4e5d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/20/2020
ms.locfileid: "49371537"
---
# <a name="manage-microsoft-365-user-accounts-licenses-and-groups-with-powershell"></a><span data-ttu-id="cd144-103">Gestire gli account utente, le licenze e i gruppi di Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="cd144-103">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>

<span data-ttu-id="cd144-104">*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.</span><span class="sxs-lookup"><span data-stu-id="cd144-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="cd144-105">Microsoft 365 amministratori devono gestire account utente, licenze e gruppi.</span><span class="sxs-lookup"><span data-stu-id="cd144-105">Microsoft 365 administrators need to manage user accounts, licenses, and groups.</span></span> <span data-ttu-id="cd144-106">Sebbene sia possibile eseguire la maggior parte di queste attività nell'Microsoft 365 di amministrazione, alcune sono più semplici in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cd144-106">Although you can do most of these tasks in the Microsoft 365 admin center, some are easier in PowerShell.</span></span>

<span data-ttu-id="cd144-107">Per ulteriori informazioni, vedere gli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="cd144-107">For more information, see the following articles.</span></span>

## <a name="user-accounts"></a><span data-ttu-id="cd144-108">Account utente</span><span class="sxs-lookup"><span data-stu-id="cd144-108">User accounts</span></span>

- [<span data-ttu-id="cd144-109">Creare account utente</span><span class="sxs-lookup"><span data-stu-id="cd144-109">Create user accounts</span></span>](create-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="cd144-110">Visualizzare account utente</span><span class="sxs-lookup"><span data-stu-id="cd144-110">View user accounts</span></span>](view-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="cd144-111">Configurare le proprietà degli account utente</span><span class="sxs-lookup"><span data-stu-id="cd144-111">Configure user account properties</span></span>](configure-user-account-properties-with-microsoft-365-powershell.md)
- [<span data-ttu-id="cd144-112">Assegnare ruoli agli account utente</span><span class="sxs-lookup"><span data-stu-id="cd144-112">Assign roles to user accounts</span></span>](assign-roles-to-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="cd144-113">Eliminare e ripristinare account utente</span><span class="sxs-lookup"><span data-stu-id="cd144-113">Delete and restore user accounts</span></span>](delete-and-restore-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="cd144-114">Bloccare account utente</span><span class="sxs-lookup"><span data-stu-id="cd144-114">Block user accounts</span></span>](block-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="cd144-115">Password</span><span class="sxs-lookup"><span data-stu-id="cd144-115">Passwords</span></span>](manage-passwords-with-microsoft-365-powershell.md)

## <a name="licenses-and-services"></a><span data-ttu-id="cd144-116">Licenze e servizi</span><span class="sxs-lookup"><span data-stu-id="cd144-116">Licenses and services</span></span>
- [<span data-ttu-id="cd144-117">Visualizzare le licenze e i servizi</span><span class="sxs-lookup"><span data-stu-id="cd144-117">View licenses and services</span></span>](view-licenses-and-services-with-microsoft-365-powershell.md)
- [<span data-ttu-id="cd144-118">Visualizzare gli utenti con licenza e senza licenza</span><span class="sxs-lookup"><span data-stu-id="cd144-118">View licensed and unlicensed users</span></span>](view-licensed-and-unlicensed-users-with-microsoft-365-powershell.md)
- <span data-ttu-id="cd144-119">[Assegnare licenze agli account utente](assign-licenses-to-user-accounts-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="cd144-119">[Assign licenses to user accounts](assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)</span></span>
- [<span data-ttu-id="cd144-120">Visualizzare la licenza dell'account e i dettagli di servizio</span><span class="sxs-lookup"><span data-stu-id="cd144-120">View account license and service details</span></span>](view-account-license-and-service-details-with-microsoft-365-powershell.md)
- [<span data-ttu-id="cd144-121">Disabilitare l'accesso ai servizi</span><span class="sxs-lookup"><span data-stu-id="cd144-121">Disable access to services</span></span>](disable-access-to-services-with-microsoft-365-powershell.md)
  - [<span data-ttu-id="cd144-122">Disabilitare l'accesso a Sway</span><span class="sxs-lookup"><span data-stu-id="cd144-122">Disable access to Sway</span></span>](disable-access-to-sway-with-microsoft-365-powershell.md)
  - [<span data-ttu-id="cd144-123">Disabilitare l'accesso ai servizi durante l'assegnazione di licenze utente</span><span class="sxs-lookup"><span data-stu-id="cd144-123">Disable access to services while assigning user licenses</span></span>](disable-access-to-services-while-assigning-user-licenses.md)
- [<span data-ttu-id="cd144-124">Rimuovere licenze dagli account utente</span><span class="sxs-lookup"><span data-stu-id="cd144-124">Remove licenses from user accounts</span></span>](remove-licenses-from-user-accounts-with-microsoft-365-powershell.md)

## <a name="groups"></a><span data-ttu-id="cd144-125">Gruppi</span><span class="sxs-lookup"><span data-stu-id="cd144-125">Groups</span></span>
- [<span data-ttu-id="cd144-126">Gestire i gruppi di sicurezza</span><span class="sxs-lookup"><span data-stu-id="cd144-126">Manage security groups</span></span>](manage-security-groups-with-microsoft-365-powershell.md)
- [<span data-ttu-id="cd144-127">Mantenere l’appartenenza ai gruppi di sicurezza</span><span class="sxs-lookup"><span data-stu-id="cd144-127">Maintain security group membership</span></span>](maintain-group-membership-with-microsoft-365-powershell.md)
- [<span data-ttu-id="cd144-128">Gestire i gruppi di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cd144-128">Manage Microsoft 365 groups</span></span>](manage-microsoft-365-groups-with-powershell.md)
