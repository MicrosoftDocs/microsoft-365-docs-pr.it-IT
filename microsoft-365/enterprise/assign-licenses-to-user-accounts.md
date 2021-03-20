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
description: Descrive come assegnare licenze di Microsoft 365 agli account utente, singolarmente o in base all'appartenenza ai gruppi.
ms.openlocfilehash: 6bba3cd767787f450840c5cae6c30f2be21bed1b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905441"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts"></a><span data-ttu-id="8573e-103">Assegnare licenze di Microsoft 365 agli account utente</span><span class="sxs-lookup"><span data-stu-id="8573e-103">Assign Microsoft 365 licenses to user accounts</span></span>

<span data-ttu-id="8573e-104">*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="8573e-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="8573e-105">Per il modello di identità solo cloud, è possibile assegnare licenze di Microsoft 365 agli account utente durante la creazione, a seconda di come vengono create.</span><span class="sxs-lookup"><span data-stu-id="8573e-105">For the cloud-only identity model, you can assign Microsoft 365 licenses to user accounts as they are created, depending on how you create them.</span></span>

<span data-ttu-id="8573e-106">Per il modello di identità ibrido, quando gli account utente di Servizi di dominio Active Directory vengono sincronizzati per la prima volta, non viene loro assegnata automaticamente una posizione o una licenza di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8573e-106">For the hybrid identity model, when Active Directory Domain Services (AD DS) user accounts are synchronized for the first time, they are not automatically assigned a location or a Microsoft 365 license.</span></span> <span data-ttu-id="8573e-107">**È necessario configurare ogni account utente con una posizione utente prima o insieme all'assegnazione di una licenza.**</span><span class="sxs-lookup"><span data-stu-id="8573e-107">**You must configure each user account with a user location prior to or along with assigning a license.**</span></span>

<span data-ttu-id="8573e-108">In entrambi i casi, è necessario assegnare una licenza agli account utente in modo che gli utenti possano accedere ai servizi di Microsoft 365, ad esempio posta elettronica e Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8573e-108">In either case, you must assign a license to user accounts so your users can access Microsoft 365 services, such as email and Microsoft Teams.</span></span>

<span data-ttu-id="8573e-109">È possibile assegnare licenze agli account utente singolarmente o automaticamente tramite l'appartenenza ai gruppi.</span><span class="sxs-lookup"><span data-stu-id="8573e-109">You can assign licenses to user accounts either individually or automatically through group membership.</span></span>

<span data-ttu-id="8573e-110">Per assegnare licenze di Microsoft 365 a singoli account utente, è possibile utilizzare:</span><span class="sxs-lookup"><span data-stu-id="8573e-110">To assign Microsoft 365 licenses to individual user accounts, you can use:</span></span>

- [<span data-ttu-id="8573e-111">L'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8573e-111">The Microsoft 365 admin center</span></span>](../admin/manage/assign-licenses-to-users.md)
- [<span data-ttu-id="8573e-112">PowerShell</span><span class="sxs-lookup"><span data-stu-id="8573e-112">PowerShell</span></span>](assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)
- <span data-ttu-id="8573e-113">Interfaccia di amministrazione di Azure AD</span><span class="sxs-lookup"><span data-stu-id="8573e-113">The Azure AD admin center</span></span>

## <a name="group-based-licensing"></a><span data-ttu-id="8573e-114">Licenze basate sui gruppi</span><span class="sxs-lookup"><span data-stu-id="8573e-114">Group-based licensing</span></span>

<span data-ttu-id="8573e-115">È possibile configurare i gruppi di sicurezza in Azure AD per assegnare automaticamente le licenze da un set di sottoscrizioni a tutti i membri del gruppo.</span><span class="sxs-lookup"><span data-stu-id="8573e-115">You can configure security groups in Azure AD to automatically assign licenses from a set of subscriptions to all the members of the group.</span></span> <span data-ttu-id="8573e-116">Questa operazione è denominata *licenze basate sui gruppi*.</span><span class="sxs-lookup"><span data-stu-id="8573e-116">This is known as *group-based licensing*.</span></span> <span data-ttu-id="8573e-117">Se un account utente viene aggiunto o rimosso dal gruppo, le licenze per gli abbonamenti del gruppo verranno automaticamente assegnate o rimosse dall'account utente.</span><span class="sxs-lookup"><span data-stu-id="8573e-117">If a user account is added to or removed from the group, the licenses for the group's subscriptions will be automatically assigned or unassigned from the user account.</span></span>

<span data-ttu-id="8573e-118">Assicurarsi di avere a disposizione abbastanza licenze per tutti i membri del gruppo.</span><span class="sxs-lookup"><span data-stu-id="8573e-118">Make sure you have enough licenses for all the group members.</span></span> <span data-ttu-id="8573e-119">Se le licenze a disposizione terminano, i nuovi utenti non potranno ottenerne una finché non ne saranno di nuovo disponibili.</span><span class="sxs-lookup"><span data-stu-id="8573e-119">If you run out of licenses, new users won't be assigned licenses until licenses become available.</span></span>

>[!Note]
><span data-ttu-id="8573e-120">Non è necessario configurare l'assegnazione delle licenze basate su gruppo per i gruppi contenenti account Azure business to business (B2B).</span><span class="sxs-lookup"><span data-stu-id="8573e-120">You should not configure group-based licensing for groups that contain Azure business to business (B2B) accounts.</span></span>
>

<span data-ttu-id="8573e-121">Per altre informazioni, vedi Licenze [basate su gruppo in Azure AD.](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)</span><span class="sxs-lookup"><span data-stu-id="8573e-121">For more informaion, see [group-based licensing in Azure AD](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal).</span></span>

## <a name="next-steps"></a><span data-ttu-id="8573e-122">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="8573e-122">Next steps</span></span>

<span data-ttu-id="8573e-123">Con il set appropriato di account utente a cui sono state assegnate licenze, è ora possibile:</span><span class="sxs-lookup"><span data-stu-id="8573e-123">With the appropriate set of user accounts that have been assigned licenses, you are now ready to:</span></span>

- [<span data-ttu-id="8573e-124">Implementare la sicurezza</span><span class="sxs-lookup"><span data-stu-id="8573e-124">Implement security</span></span>](../security/office-365-security/security-roadmap.md)
- [<span data-ttu-id="8573e-125">Distribuire software client, ad esempio Microsoft 365 Apps</span><span class="sxs-lookup"><span data-stu-id="8573e-125">Deploy client software, such as Microsoft 365 Apps</span></span>](/DeployOffice/deployment-guide-microsoft-365-apps)
- [<span data-ttu-id="8573e-126">Configurare la gestione dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="8573e-126">Set up device management</span></span>](device-management-roadmap-microsoft-365.md)
- [<span data-ttu-id="8573e-127">Configurare servizi e applicazioni</span><span class="sxs-lookup"><span data-stu-id="8573e-127">Configure services and applications</span></span>](configure-services-and-applications.md)