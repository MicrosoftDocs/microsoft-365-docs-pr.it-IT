---
title: Aggiungere o rimuovere un amministratore geo
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.collection: SPO_Content
localization_priority: Normal
f1.keywords:
- NOCSH
description: È necessario configurare gli amministratori separati per ogni posizione geografica? Informazioni su come aggiungere o rimuovere un amministratore di posizione geografica in Microsoft 365 Multi-Geo.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9a3d916bfec2c53850f923fb5322298e9ff440ca
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691529"
---
# <a name="add-or-remove-a-geo-administrator-in-microsoft-365-multi-geo"></a><span data-ttu-id="d5750-104">Aggiungere o rimuovere un amministratore di posizione geografica in Microsoft 365 Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="d5750-104">Add or remove a geo administrator in Microsoft 365 Multi-Geo</span></span>

<span data-ttu-id="d5750-105">È possibile configurare amministratori separati per ogni posizione geografica disponibili nel tenant.</span><span class="sxs-lookup"><span data-stu-id="d5750-105">You can configure separate administrators for each geo location that you have in your tenant.</span></span> <span data-ttu-id="d5750-106">Questi amministratori avranno accesso alle impostazioni SharePoint Online e OneDrive specifiche per la posizione geografica.</span><span class="sxs-lookup"><span data-stu-id="d5750-106">These administrators will have access to the SharePoint Online and OneDrive settings that are specific to their geo location.</span></span>

<span data-ttu-id="d5750-107">Alcuni servizi, ad esempio l'archivio termini, sono gestiti dalla posizione centrale e replicati nelle posizioni satellitari.</span><span class="sxs-lookup"><span data-stu-id="d5750-107">Some services - such as the term store - are administered from the central location and replicated to satellite locations.</span></span> <span data-ttu-id="d5750-108">L’amministratore geografico della sede centrale può accedere a questi criteri, mentre gli amministratori geografici per località satellitari non possono.</span><span class="sxs-lookup"><span data-stu-id="d5750-108">The geo admin for the central location has access to these, whereas geo admins for satellite locations don't.</span></span>

<span data-ttu-id="d5750-109">Gli amministratori globali e di SharePoint Online continuano ad avere accesso alle impostazioni nella posizione centrale e in tutte le località satellitari.</span><span class="sxs-lookup"><span data-stu-id="d5750-109">Global administrators and SharePoint Online administrators continue to have access to settings in the central location and all satellite locations.</span></span>

## <a name="configuring-geo-administrators"></a><span data-ttu-id="d5750-110">Configurazione gli amministratori geografici</span><span class="sxs-lookup"><span data-stu-id="d5750-110">Configuring geo administrators</span></span>

<span data-ttu-id="d5750-111">Per configurare gli amministratori geografici è necessario il modulo di PowerShell per SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="d5750-111">Configuring geo admins requires SharePoint Online PowerShell module.</span></span>

<span data-ttu-id="d5750-112">Utilizzare [Connect-SPOService](https://docs.microsoft.com/powershell/module/sharepoint-online/Connect-SPOService) per connettersi all'interfaccia di amministrazione della posizione geografica in cui si vuole aggiungere l'amministratore geografico. (Ad esempio Connect-SPOService  https://ContosoEUR-admin.sharepoint.com.)</span><span class="sxs-lookup"><span data-stu-id="d5750-112">Use [Connect-SPOService](https://docs.microsoft.com/powershell/module/sharepoint-online/Connect-SPOService) to connect to the admin center of the geo location where you want to add the geo admin. (For example, Connect-SPOService  https://ContosoEUR-admin.sharepoint.com.)</span></span>

<span data-ttu-id="d5750-113">Per visualizzare gli amministratori geografici esistenti in una posizione, eseguire `Get-SPOGeoAdministrator`</span><span class="sxs-lookup"><span data-stu-id="d5750-113">To view the existing geo admins of a location, run `Get-SPOGeoAdministrator`</span></span>

### <a name="adding-a-user-as-a-geo-admin"></a><span data-ttu-id="d5750-114">Aggiunta di un utente come amministratore geografico</span><span class="sxs-lookup"><span data-stu-id="d5750-114">Adding a user as a geo admin</span></span>

<span data-ttu-id="d5750-115">Per aggiungere un utente come amministratore geografico, eseguire `Add-SPOGeoAdministrator -UserPrincipalName <UPN>`</span><span class="sxs-lookup"><span data-stu-id="d5750-115">To add a user as a geo admin, run `Add-SPOGeoAdministrator -UserPrincipalName <UPN>`</span></span>

<span data-ttu-id="d5750-116">Per rimuovere un utente da amministratore geografico di una posizione, eseguire  `Remove-SPOGeoAdministrator -UserPrincipalName <UPN>`</span><span class="sxs-lookup"><span data-stu-id="d5750-116">To remove a user as a Geo Admin of a location, run  `Remove-SPOGeoAdministrator -UserPrincipalName <UPN>`</span></span>

### <a name="adding-a-group-as-a-geo-admin"></a><span data-ttu-id="d5750-117">Aggiunta di un gruppo come amministratore geografico</span><span class="sxs-lookup"><span data-stu-id="d5750-117">Adding a group as a geo admin</span></span>

<span data-ttu-id="d5750-118">È possibile aggiungere un gruppo di sicurezza o un gruppo di sicurezza abilitato alla posta elettronica come amministratore di posizione geografica. I gruppi di distribuzione e i gruppi di Microsoft 365 non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="d5750-118">You can add a security group or a mail-enabled security group as a geo admin. (Distribution groups and Microsoft 365 Groups are not supported.)</span></span>

<span data-ttu-id="d5750-119">Per aggiungere un gruppo come amministratore geografico, eseguire `Add-SPOGeoAdministrator -GroupAlias <alias>`</span><span class="sxs-lookup"><span data-stu-id="d5750-119">To add a group as a geo administrator, run `Add-SPOGeoAdministrator -GroupAlias <alias>`</span></span>

<span data-ttu-id="d5750-120">Per rimuovere un gruppo da amministratore geografico, eseguire `Remove-SPOGeoAdministrator -GroupAlias <alias>`</span><span class="sxs-lookup"><span data-stu-id="d5750-120">To remove a group as a geo administrator, run `Remove-SPOGeoAdministrator -GroupAlias <alias>`</span></span>

<span data-ttu-id="d5750-121">Si noti che non tutti i gruppi di sicurezza un alias di gruppo.</span><span class="sxs-lookup"><span data-stu-id="d5750-121">Note that not all security groups have a group alias.</span></span> <span data-ttu-id="d5750-122">Per aggiungere un gruppo di sicurezza che non dispone di un alias, eseguire [Get-MsolGroup](https://docs.microsoft.com/powershell/module/msonline/get-msolgroup) per recuperare un elenco dei gruppi, trovare il valore del proprio gruppo di sicurezza e quindi eseguire:</span><span class="sxs-lookup"><span data-stu-id="d5750-122">If you want to add a security group that does not have an alias, run [Get-MsolGroup](https://docs.microsoft.com/powershell/module/msonline/get-msolgroup) to retrieve a list of groups, find your security group's ObjectID, and then run:</span></span>

`Add-SPOGeoAdministrator -ObjectID <ObjectID>`

<span data-ttu-id="d5750-123">Per rimuovere un gruppo usando il valore di ObjectID, eseguire `Remove-SPOGeoAdministrator -ObjectID <ObjectID>`</span><span class="sxs-lookup"><span data-stu-id="d5750-123">To remove a group by using the ObjectID, run `Remove-SPOGeoAdministrator -ObjectID <ObjectID>`</span></span>

## <a name="related-topics"></a><span data-ttu-id="d5750-124">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="d5750-124">Related topics</span></span>

[<span data-ttu-id="d5750-125">Add-SPOGeoAdministrator</span><span class="sxs-lookup"><span data-stu-id="d5750-125">Add-SPOGeoAdministrator</span></span>](https://docs.microsoft.com/powershell/module/sharepoint-online/add-spogeoadministrator)

[<span data-ttu-id="d5750-126">Get-SPOGeoAdministrator</span><span class="sxs-lookup"><span data-stu-id="d5750-126">Get-SPOGeoAdministrator</span></span>](https://docs.microsoft.com/powershell/module/sharepoint-online/get-spogeoadministrator)

[<span data-ttu-id="d5750-127">Remove-SPOGeoAdministrator</span><span class="sxs-lookup"><span data-stu-id="d5750-127">Remove-SPOGeoAdministrator</span></span>](https://docs.microsoft.com/powershell/module/sharepoint-online/remove-spogeoadministrator)

[<span data-ttu-id="d5750-128">Impostare un alias (MailNickName) per un gruppo di sicurezza</span><span class="sxs-lookup"><span data-stu-id="d5750-128">Set an alias (MailNickName) for a security group</span></span>](https://docs.microsoft.com/powershell/module/azuread/set-azureadgroup)