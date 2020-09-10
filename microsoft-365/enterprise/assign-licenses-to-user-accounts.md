---
title: Assegnare le licenze Microsoft 365 agli account utente
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/03/2019
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365p_AddUsersWithDirSync
- O365M_AddUsersWithDirSync
- O365E_HRCSetupAADConnectAboutLM617031
- O365E_AddUsersWithDirSync
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOP150
- MOE150
- MBS150
ms.assetid: 01920974-9e6f-4331-a370-13aea4e82b3e
description: Descrive come assegnare le licenze Microsoft 365 agli account utente, individualmente o in base all'appartenenza ai gruppi.
ms.openlocfilehash: e132a8c2d65c401899624b9d255050385f2cb721
ms.sourcegitcommit: 74ef7179887eedc696c975a82c865b2d4b3808fd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/09/2020
ms.locfileid: "47417099"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts"></a><span data-ttu-id="a1a7e-103">Assegnare le licenze Microsoft 365 agli account utente</span><span class="sxs-lookup"><span data-stu-id="a1a7e-103">Assign Microsoft 365 licenses to user accounts</span></span>

<span data-ttu-id="a1a7e-104">*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="a1a7e-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="a1a7e-105">Per il modello di identità solo cloud, è possibile assegnare le licenze Microsoft 365 agli account utente quando vengono creati, a seconda della modalità di creazione.</span><span class="sxs-lookup"><span data-stu-id="a1a7e-105">For the cloud-only identity model, you can assign Microsoft 365 licenses to user accounts as they are created, depending on how you create them.</span></span>

<span data-ttu-id="a1a7e-106">Per il modello di identità ibrida, quando gli account utente di servizi di dominio Active Directory (AD DS) vengono sincronizzati per la prima volta, non viene assegnata automaticamente una licenza Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a1a7e-106">For the hybrid identity model, when Active Directory Domain Services (AD DS) user accounts are synchronized for the first time, they are not automatically assigned a Microsoft 365 license.</span></span> <span data-ttu-id="a1a7e-107">Prima di tutto, è necessario configurare ogni account utente con un percorso utente.</span><span class="sxs-lookup"><span data-stu-id="a1a7e-107">You must first configure each user account with a user location.</span></span>

<span data-ttu-id="a1a7e-108">In entrambi i casi, è necessario assegnare una licenza agli account utente in modo che gli utenti possano accedere ai servizi Microsoft 365, ad esempio la posta elettronica e Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="a1a7e-108">In either case, you must assign a license to user accounts so your users can access Microsoft 365 services, such as email and Microsoft Teams.</span></span>

<span data-ttu-id="a1a7e-109">È possibile assegnare le licenze agli account utente singolarmente o automaticamente tramite l'appartenenza al gruppo.</span><span class="sxs-lookup"><span data-stu-id="a1a7e-109">You can assign licenses to user accounts either individually or automatically through group membership.</span></span>

<span data-ttu-id="a1a7e-110">Per assegnare le licenze Microsoft 365 ai singoli account utente, è possibile utilizzare:</span><span class="sxs-lookup"><span data-stu-id="a1a7e-110">To assign Microsoft 365 licenses to individual user accounts, you can use:</span></span>

- [<span data-ttu-id="a1a7e-111">L'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a1a7e-111">The Microsoft 365 admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)
- [<span data-ttu-id="a1a7e-112">PowerShell per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a1a7e-112">PowerShell for Microsoft 365</span></span>](assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)

<span data-ttu-id="a1a7e-113">Per l'assegnazione di licenze automatiche, vedere [Group-based Licensing in Azure ad](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="a1a7e-113">For automatic license assignment, see [group-based licensing in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal).</span></span>

## <a name="next-steps"></a><span data-ttu-id="a1a7e-114">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="a1a7e-114">Next steps</span></span>

<span data-ttu-id="a1a7e-115">Con l'intero set di account utente a cui sono state assegnate le licenze, ora è possibile eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a1a7e-115">With the full set of user accounts that have been assigned licenses, you are now ready to:</span></span>

- [<span data-ttu-id="a1a7e-116">Implementare la sicurezza</span><span class="sxs-lookup"><span data-stu-id="a1a7e-116">Implement security</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap)
- [<span data-ttu-id="a1a7e-117">Distribuire il software client, ad esempio le app Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a1a7e-117">Deploy client software, such as Microsoft 365 Apps</span></span>](https://docs.microsoft.com/DeployOffice/deployment-guide-microsoft-365-apps)
- [<span data-ttu-id="a1a7e-118">Configurare la sicurezza e la mobilità di base in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a1a7e-118">Set up Basic Mobility and Security in Microsoft 365</span></span>](https://support.microsoft.com/office/set-up-basic-mobility-and-security-dd892318-bc44-4eb1-af00-9db5430be3cd)
- [<span data-ttu-id="a1a7e-119">Configurare servizi e applicazioni</span><span class="sxs-lookup"><span data-stu-id="a1a7e-119">Configure services and applications</span></span>](configure-services-and-applications.md)
