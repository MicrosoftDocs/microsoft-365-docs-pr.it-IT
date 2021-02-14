---
title: Assegnare licenze di Microsoft 365 agli account utente
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
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
description: Descrive come assegnare licenze di Microsoft 365 agli account utente singolarmente o in base all'appartenenza ai gruppi.
ms.openlocfilehash: a2eed7b3597dcc2531834456a9b05f5aa1b07a23
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326508"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts"></a><span data-ttu-id="765d7-103">Assegnare licenze di Microsoft 365 agli account utente</span><span class="sxs-lookup"><span data-stu-id="765d7-103">Assign Microsoft 365 licenses to user accounts</span></span>

<span data-ttu-id="765d7-104">*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.</span><span class="sxs-lookup"><span data-stu-id="765d7-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="765d7-105">Per il modello di identità solo cloud, è possibile assegnare licenze di Microsoft 365 agli account utente durante la creazione, a seconda di come vengono creati.</span><span class="sxs-lookup"><span data-stu-id="765d7-105">For the cloud-only identity model, you can assign Microsoft 365 licenses to user accounts as they are created, depending on how you create them.</span></span>

<span data-ttu-id="765d7-106">Per il modello di identità ibrido, quando gli account utente di Servizi di dominio Active Directory vengono sincronizzati per la prima volta, non viene loro assegnata automaticamente una posizione o una licenza di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="765d7-106">For the hybrid identity model, when Active Directory Domain Services (AD DS) user accounts are synchronized for the first time, they are not automatically assigned a location or a Microsoft 365 license.</span></span> <span data-ttu-id="765d7-107">**È necessario configurare ogni account utente con una posizione utente prima o insieme all'assegnazione di una licenza.**</span><span class="sxs-lookup"><span data-stu-id="765d7-107">**You must configure each user account with a user location prior to or along with assigning a license.**</span></span>

<span data-ttu-id="765d7-108">In entrambi i casi, è necessario assegnare una licenza agli account utente in modo che gli utenti possano accedere ai servizi di Microsoft 365, ad esempio posta elettronica e Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="765d7-108">In either case, you must assign a license to user accounts so your users can access Microsoft 365 services, such as email and Microsoft Teams.</span></span>

<span data-ttu-id="765d7-109">È possibile assegnare licenze agli account utente singolarmente o automaticamente tramite l'appartenenza ai gruppi.</span><span class="sxs-lookup"><span data-stu-id="765d7-109">You can assign licenses to user accounts either individually or automatically through group membership.</span></span>

<span data-ttu-id="765d7-110">Per assegnare licenze di Microsoft 365 a singoli account utente, è possibile utilizzare:</span><span class="sxs-lookup"><span data-stu-id="765d7-110">To assign Microsoft 365 licenses to individual user accounts, you can use:</span></span>

- [<span data-ttu-id="765d7-111">L'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="765d7-111">The Microsoft 365 admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)
- [<span data-ttu-id="765d7-112">PowerShell</span><span class="sxs-lookup"><span data-stu-id="765d7-112">PowerShell</span></span>](assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)
- <span data-ttu-id="765d7-113">Interfaccia di amministrazione di Azure AD</span><span class="sxs-lookup"><span data-stu-id="765d7-113">The Azure AD admin center</span></span>

## <a name="group-based-licensing"></a><span data-ttu-id="765d7-114">Licenze basate sui gruppi</span><span class="sxs-lookup"><span data-stu-id="765d7-114">Group-based licensing</span></span>

<span data-ttu-id="765d7-115">Puoi configurare i gruppi di sicurezza in Azure AD per assegnare automaticamente le licenze da un set di sottoscrizioni a tutti i membri del gruppo.</span><span class="sxs-lookup"><span data-stu-id="765d7-115">You can configure security groups in Azure AD to automatically assign licenses from a set of subscriptions to all the members of the group.</span></span> <span data-ttu-id="765d7-116">Questa operazione è denominata *licenze basate sui gruppi*.</span><span class="sxs-lookup"><span data-stu-id="765d7-116">This is known as *group-based licensing*.</span></span> <span data-ttu-id="765d7-117">Se un account utente viene aggiunto o rimosso dal gruppo, le licenze per gli abbonamenti del gruppo verranno automaticamente assegnate o rimosse dall'account utente.</span><span class="sxs-lookup"><span data-stu-id="765d7-117">If a user account is added to or removed from the group, the licenses for the group's subscriptions will be automatically assigned or unassigned from the user account.</span></span>

<span data-ttu-id="765d7-118">Assicurarsi di avere a disposizione abbastanza licenze per tutti i membri del gruppo.</span><span class="sxs-lookup"><span data-stu-id="765d7-118">Make sure you have enough licenses for all the group members.</span></span> <span data-ttu-id="765d7-119">Se le licenze a disposizione terminano, i nuovi utenti non potranno ottenerne una finché non ne saranno di nuovo disponibili.</span><span class="sxs-lookup"><span data-stu-id="765d7-119">If you run out of licenses, new users won't be assigned licenses until licenses become available.</span></span>

>[!Note]
><span data-ttu-id="765d7-120">Non è necessario configurare l'assegnazione delle licenze basate su gruppo per i gruppi contenenti account Azure business to business (B2B).</span><span class="sxs-lookup"><span data-stu-id="765d7-120">You should not configure group-based licensing for groups that contain Azure business to business (B2B) accounts.</span></span>
>

<span data-ttu-id="765d7-121">Per altre informazioni, vedi licenze [basate su gruppo in Azure AD.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)</span><span class="sxs-lookup"><span data-stu-id="765d7-121">For more informaion, see [group-based licensing in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal).</span></span>

## <a name="next-steps"></a><span data-ttu-id="765d7-122">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="765d7-122">Next steps</span></span>

<span data-ttu-id="765d7-123">Con il set appropriato di account utente a cui sono state assegnate licenze, è ora possibile:</span><span class="sxs-lookup"><span data-stu-id="765d7-123">With the appropriate set of user accounts that have been assigned licenses, you are now ready to:</span></span>

- [<span data-ttu-id="765d7-124">Implementare la sicurezza</span><span class="sxs-lookup"><span data-stu-id="765d7-124">Implement security</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap)
- [<span data-ttu-id="765d7-125">Distribuire software client, ad esempio Microsoft 365 Apps</span><span class="sxs-lookup"><span data-stu-id="765d7-125">Deploy client software, such as Microsoft 365 Apps</span></span>](https://docs.microsoft.com/DeployOffice/deployment-guide-microsoft-365-apps)
- [<span data-ttu-id="765d7-126">Configurare la gestione dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="765d7-126">Set up device management</span></span>](device-management-roadmap-microsoft-365.md)
- [<span data-ttu-id="765d7-127">Configurare servizi e applicazioni</span><span class="sxs-lookup"><span data-stu-id="765d7-127">Configure services and applications</span></span>](configure-services-and-applications.md)
