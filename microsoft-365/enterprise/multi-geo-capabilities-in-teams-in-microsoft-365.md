---
title: Funzionalità multi-geografiche in Microsoft Teams
ms.reviewer: daro
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: ''
ms.collection:
- Strat_SP_gtc
- SPO_Content
- m365solution-scenario
- m365solution-spintranet
localization_priority: Normal
description: Informazioni su come Teams con Microsoft 365 Multi-Geo.
ms.openlocfilehash: 7da2032e1106d03178eccf3bcfb4f37fc63780d7
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/15/2021
ms.locfileid: "53453526"
---
# <a name="multi-geo-capabilities-in-microsoft-teams"></a><span data-ttu-id="376e5-103">Funzionalità multi-geografiche in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="376e5-103">Multi-Geo capabilities in Microsoft Teams</span></span>

<span data-ttu-id="376e5-104">Le funzionalità Multi-Geo in Teams consentono Teams i dati della chat da archiviare in una posizione geografica specificata.</span><span class="sxs-lookup"><span data-stu-id="376e5-104">Multi-Geo capabilities in Teams enables Teams chat data to be stored at rest in a specified geo location.</span></span> <span data-ttu-id="376e5-105">I dati di chat sono costituiti da messaggi di chat, inclusi messaggi privati, messaggi di canale e immagini utilizzati nelle chat.</span><span class="sxs-lookup"><span data-stu-id="376e5-105">Chat data consists of chat messages, including private messages, channel messages, and images used in chats.</span></span>

<span data-ttu-id="376e5-106">Teams utilizza il file PDL (Preferred Data Location) per utenti e gruppi per determinare dove archiviare i dati.</span><span class="sxs-lookup"><span data-stu-id="376e5-106">Teams uses the Preferred Data Location (PDL) for users and groups to determine where to store data.</span></span> <span data-ttu-id="376e5-107">Se la PDL non è impostata o non è valida, i dati vengono archiviati nella posizione centrale del tenant.</span><span class="sxs-lookup"><span data-stu-id="376e5-107">If the PDL is not set or is invalid, data is stored in the tenant's central location.</span></span>

## <a name="user-chat"></a><span data-ttu-id="376e5-108">Chat utente</span><span class="sxs-lookup"><span data-stu-id="376e5-108">User chat</span></span>

<span data-ttu-id="376e5-109">La chat utente include messaggi di riunione uno-a-uno, uno-a-molti e privati.</span><span class="sxs-lookup"><span data-stu-id="376e5-109">User chat includes one-to-one, one-to-many, and private meeting messages.</span></span>

<span data-ttu-id="376e5-110">Quando viene creato un nuovo utente, Teams legge il file PDL dell'utente e archivia tutti i dati della chat in tale posizione geografica.</span><span class="sxs-lookup"><span data-stu-id="376e5-110">When a new user is created, Teams reads the user's PDL and stores all their chat data in that geo location.</span></span>

<span data-ttu-id="376e5-111">Per gli utenti esistenti, se un amministratore aggiunge o modifica il file PDL per un utente, i dati della chat dell'utente vengono aggiunti a una coda di migrazione per essere spostati nella posizione geografica specificata.</span><span class="sxs-lookup"><span data-stu-id="376e5-111">For existing users, if an administrator adds or modifies the PDL for a user, that user's chat data is added to a migration queue to be moved to the specified geo location.</span></span>

<span data-ttu-id="376e5-112">La posizione di archiviazione per una chat uno-a-uno o uno-a-molti si basa sul file PDL della persona che ha creato la chat.</span><span class="sxs-lookup"><span data-stu-id="376e5-112">The storage location for a one-to-one or one-to-many chat is based on the PDL of the person who created the chat.</span></span> <span data-ttu-id="376e5-113">Se il PDL dell'utente viene modificato, la chat verrà migrata nella nuova posizione geografica.</span><span class="sxs-lookup"><span data-stu-id="376e5-113">If that user's PDL is changed, the chat will be migrated to the new geo location.</span></span> <span data-ttu-id="376e5-114">La posizione di archiviazione per una chat di riunione si basa sul PDL dell'organizzatore della riunione.</span><span class="sxs-lookup"><span data-stu-id="376e5-114">The storage location for a meeting chat is based on the PDL of the meeting organizer.</span></span>

<span data-ttu-id="376e5-115">Per trovare la posizione corrente dei dati Teams utente, connettersi a [Teams PowerShell](/powershell/module/teams/connect-microsoftteams) ed eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="376e5-115">To find the current location of a user's Teams data, [connect to Teams PowerShell](/powershell/module/teams/connect-microsoftteams) and run the following command:</span></span>

```PowerShell
Get-MultiGeoRegion -EntityType User -EntityId <UPN>
```

## <a name="channel-messages"></a><span data-ttu-id="376e5-116">Messaggi di canale</span><span class="sxs-lookup"><span data-stu-id="376e5-116">Channel messages</span></span>

<span data-ttu-id="376e5-117">Ogni Microsoft 365 ha una posizione dati preferita (PDL, Preferred Data Location) che indica la posizione geografica in cui devono essere archiviati i dati correlati.</span><span class="sxs-lookup"><span data-stu-id="376e5-117">Each Microsoft 365 group has a Preferred Data Location (PDL) which denotes the geo location where related data is to be stored.</span></span> <span data-ttu-id="376e5-118">Teams il file PDL per il gruppo associato a ogni team per determinare dove archiviare i dati di messaggistica del canale per tale team.</span><span class="sxs-lookup"><span data-stu-id="376e5-118">Teams uses the PDL for the group associated with each team to determine where to store channel messaging data for that team.</span></span> <span data-ttu-id="376e5-119">Sono inclusi i canali privati e le chat che si verificano all'interno di una riunione di canale.</span><span class="sxs-lookup"><span data-stu-id="376e5-119">This includes private channels as well as chat that occurs within a channel meeting.</span></span>

<span data-ttu-id="376e5-120">Quando un utente crea un nuovo team, il PDL dell'utente determina quale file PDL viene assegnato al Microsoft 365 gruppo.</span><span class="sxs-lookup"><span data-stu-id="376e5-120">When a user creates a new team, that user's PDL determines what PDL is assigned to the Microsoft 365 group.</span></span> <span data-ttu-id="376e5-121">Il file PDL del gruppo determina dove vengono archiviati i dati del team.</span><span class="sxs-lookup"><span data-stu-id="376e5-121">The group PDL determines where that team's data is stored.</span></span> <span data-ttu-id="376e5-122">Se il PDL dell'utente in un secondo momento cambia, il PDL del gruppo non viene modificato.</span><span class="sxs-lookup"><span data-stu-id="376e5-122">If that user's PDL later changes, the group's PDL is not changed.</span></span>

<span data-ttu-id="376e5-123">Per i team esistenti, se un amministratore aggiunge o modifica il file PDL per il gruppo di Microsoft 365 che contiene un team, i dati di messaggistica del canale del team vengono aggiunti a una coda di migrazione per essere spostati nella posizione geografica specificata.</span><span class="sxs-lookup"><span data-stu-id="376e5-123">For existing teams, if an administrator adds or modifies the PDL for the Microsoft 365 group that backs a team, that team's channel messaging data is added to a migration queue to be moved to the specified geo location.</span></span>

<span data-ttu-id="376e5-124">La modifica del file PDL del gruppo Microsoft 365 coda dei dati Teams eseguire la migrazione nel percorso scelto.</span><span class="sxs-lookup"><span data-stu-id="376e5-124">Changing the PDL of the Microsoft 365 group queues the Teams data to migrate to the chosen location.</span></span> <span data-ttu-id="376e5-125">Tuttavia, non viene eseguita automaticamente la migrazione del SharePoint o dei file associati al gruppo.</span><span class="sxs-lookup"><span data-stu-id="376e5-125">However, this does not migrate the SharePoint site or files associated with the Group automatically.</span></span> <span data-ttu-id="376e5-126">È necessario spostare il sito separatamente seguendo le procedure descritte in [Move a SharePoint site to a different geo location.](/microsoft-365/enterprise/move-sharepoint-between-geo-locations)</span><span class="sxs-lookup"><span data-stu-id="376e5-126">You must move the site separately by following the procedures in [Move a SharePoint site to a different geo location](/microsoft-365/enterprise/move-sharepoint-between-geo-locations).</span></span> <span data-ttu-id="376e5-127">Assicurati di eseguire entrambi i passaggi per evitare Teams dati e SharePoint per un gruppo in posizioni diverse.</span><span class="sxs-lookup"><span data-stu-id="376e5-127">Be sure to do both steps to avoid Teams data and SharePoint data for one group in different locations.</span></span>

<span data-ttu-id="376e5-128">Per trovare la posizione corrente dei dati di un team, connettersi a [Teams PowerShell](/powershell/module/teams/connect-microsoftteams) ed eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="376e5-128">To find the current location of a team's data, [connect to Teams PowerShell](/powershell/module/teams/connect-microsoftteams) and run the following command:</span></span>

```PowerShell
Get-MultiGeoRegion -EntityType Group -EntityId <GroupObjectId>
```

## <a name="user-experience"></a><span data-ttu-id="376e5-129">Esperienza utente</span><span class="sxs-lookup"><span data-stu-id="376e5-129">User Experience</span></span>

<span data-ttu-id="376e5-130">Teams Multi-Geo è facile per l'utente finale.</span><span class="sxs-lookup"><span data-stu-id="376e5-130">Teams Multi-Geo is seamless to the end user.</span></span> <span data-ttu-id="376e5-131">Dopo aver modificato il file PDL di un utente o di un gruppo, i rispettivi dati verranno accodato per la migrazione e la migrazione verrà eseguita automaticamente senza alcun impatto sull'utente o sul client Teams anche se sono attivi durante la migrazione.</span><span class="sxs-lookup"><span data-stu-id="376e5-131">Once you change the PDL of a user or a group, the respective data will queue for migration and the migration will occur automatically with no impact to the user or their Teams client even if they are active while the migration occurs.</span></span>

## <a name="see-also"></a><span data-ttu-id="376e5-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="376e5-132">See also</span></span>

[<span data-ttu-id="376e5-133">Configurazione del tenant di Microsoft 365 Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="376e5-133">Microsoft 365 Multi-Geo tenant configuration</span></span>](/microsoft-365/enterprise/multi-geo-tenant-configuration)

[<span data-ttu-id="376e5-134">Amministrare un ambiente multi-geo</span><span class="sxs-lookup"><span data-stu-id="376e5-134">Administering a multi-geo environment</span></span>](administering-a-multi-geo-environment.md)

[<span data-ttu-id="376e5-135">Amministrazione delle cassette postali di Exchange Online in un ambiente multi-geo</span><span class="sxs-lookup"><span data-stu-id="376e5-135">Administering Exchange Online mailboxes in a multi-geo environment</span></span>](administering-exchange-online-multi-geo.md)
