---
title: Impedire l'aggiunta di guest a un gruppo specifico
ms.reviewer: arvaradh
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Informazioni su come impedire l'aggiunta di utenti guest a un gruppo specifico
ms.openlocfilehash: 572746a666586920ad85dafddbd78997940490d7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907941"
---
# <a name="prevent-guests-from-being-added-to-a-specific-microsoft-365-group-or-microsoft-teams-team"></a><span data-ttu-id="3f45e-103">Impedire l'aggiunta di utenti guest a uno specifico gruppo di Microsoft 365 o team di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3f45e-103">Prevent guests from being added to a specific Microsoft 365 group or Microsoft Teams team</span></span>

<span data-ttu-id="3f45e-104">Se si desidera consentire l'accesso guest alla maggior parte dei gruppi e dei team, ma si desidera impedire l'accesso guest, è possibile bloccare l'accesso guest per singoli gruppi e team.</span><span class="sxs-lookup"><span data-stu-id="3f45e-104">If you want to allow guest access to most groups and teams, but have some where you want to prevent guest access, you can block guest access for individual groups and teams.</span></span> <span data-ttu-id="3f45e-105">Il blocco dell'accesso guest a un team viene eseguito bloccando l'accesso guest al gruppo associato. Ciò impedisce l'aggiunta di nuovi guest, ma non rimuove gli utenti guest già presenti nel gruppo o nel team.</span><span class="sxs-lookup"><span data-stu-id="3f45e-105">(Blocking guest access to a team is done by blocking guest access to the associated group.) This prevents new guests from being added but does not remove guests that are already in the group or team.</span></span>

<span data-ttu-id="3f45e-106">Se si utilizzano etichette di riservatezza nell'organizzazione, è consigliabile usarle per controllare l'accesso guest per ogni gruppo.</span><span class="sxs-lookup"><span data-stu-id="3f45e-106">If you use sensitivity labels in your organization, we recommend using them to control guest access on a per-group basis.</span></span> <span data-ttu-id="3f45e-107">Per informazioni su come eseguire questa operazione, utilizzare etichette di riservatezza per proteggere il contenuto in Microsoft Teams, gruppi di [Microsoft 365 e siti di SharePoint.](../compliance/sensitivity-labels-teams-groups-sites.md)</span><span class="sxs-lookup"><span data-stu-id="3f45e-107">For information about how to do this, [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](../compliance/sensitivity-labels-teams-groups-sites.md).</span></span> <span data-ttu-id="3f45e-108">Questo è l'approccio consigliato.</span><span class="sxs-lookup"><span data-stu-id="3f45e-108">This is the recommended approach.</span></span>

## <a name="change-group-settings-using-microsoft-powershell"></a><span data-ttu-id="3f45e-109">Modificare le impostazioni dei gruppi con Microsoft PowerShell</span><span class="sxs-lookup"><span data-stu-id="3f45e-109">Change group settings using Microsoft PowerShell</span></span>

<span data-ttu-id="3f45e-110">È inoltre possibile impedire l'aggiunta di nuovi guest a singoli gruppi tramite PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3f45e-110">You can also prevent the addition of new guests to individual groups by using PowerShell.</span></span> <span data-ttu-id="3f45e-111">Tenere presente che il sito di SharePoint associato al team dispone [di controlli di condivisione guest separati.](/sharepoint/change-external-sharing-site)</span><span class="sxs-lookup"><span data-stu-id="3f45e-111">(Remember that the team's associated SharePoint site has [separate guest sharing controls](/sharepoint/change-external-sharing-site).)</span></span>

<span data-ttu-id="3f45e-112">È necessario utilizzare la versione di anteprima di [Azure Active Directory PowerShell per Graph](/powershell/azure/active-directory/install-adv2) (nome modulo **AzureADPreview**) per modificare l'impostazione di accesso guest a livello di gruppo:</span><span class="sxs-lookup"><span data-stu-id="3f45e-112">You must use the preview version of [Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:</span></span>

- <span data-ttu-id="3f45e-113">Se non è ancora stata installata una versione del modulo PowerShell di Azure AD, vedere [installare il modulo Azure AD](/powershell/azure/active-directory/install-adv2?preserve-view=true&view=azureadps-2.0-preview) e seguire le istruzioni per installare la versione di anteprima pubblica.</span><span class="sxs-lookup"><span data-stu-id="3f45e-113">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](/powershell/azure/active-directory/install-adv2?preserve-view=true&view=azureadps-2.0-preview) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="3f45e-114">Se è installata la versione 2.0 disponibile a livello generale del modulo PowerShell di Azure AD (AzureAD), è necessario disinstallarlo eseguendo `Uninstall-Module AzureAD` nella sessione di PowerShell e quindi installare la versione di anteprima eseguendo `Install-Module AzureADPreview`.</span><span class="sxs-lookup"><span data-stu-id="3f45e-114">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="3f45e-115">Se è già stata installata la versione Preview, eseguire `Install-Module AzureADPreview` per verificare che sia la versione più recente di questo modulo.</span><span class="sxs-lookup"><span data-stu-id="3f45e-115">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>

> [!NOTE]
> <span data-ttu-id="3f45e-116">Per eseguire questi comandi, è necessario disporre dei diritti di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="3f45e-116">You must have global admin rights to run these commands.</span></span> 

<span data-ttu-id="3f45e-117">Eseguire lo script seguente, modificando il nome del gruppo in cui */<GroupName/>* si desidera bloccare l'accesso guest.</span><span class="sxs-lookup"><span data-stu-id="3f45e-117">Run the following script, changing */<GroupName/>* to the name of the group where you want to block guest access.</span></span>

```PowerShell
$GroupName = "<GroupName>"

Connect-AzureAD

$template = Get-AzureADDirectorySettingTemplate | ? {$_.displayname -eq "group.unified.guest"}
$settingsCopy = $template.CreateDirectorySetting()
$settingsCopy["AllowToAddGuests"]=$False
$groupID= (Get-AzureADGroup -SearchString $GroupName).ObjectId
New-AzureADObjectSetting -TargetType Groups -TargetObjectId $groupID -DirectorySetting $settingsCopy
```

<span data-ttu-id="3f45e-118">Per verificare le impostazioni, eseguire questo comando:</span><span class="sxs-lookup"><span data-stu-id="3f45e-118">To verify your settings, run this command:</span></span>

```PowerShell
Get-AzureADObjectSetting -TargetObjectId $groupID -TargetType Groups | fl Values
```

<span data-ttu-id="3f45e-119">La verifica è simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="3f45e-119">The verification looks like this:</span></span>
    
![Screenshot della finestra di PowerShell che mostra che l'accesso al gruppo guest è stato impostato su false.](../media/09ebfb4f-859f-44c3-a29e-63a59fd6ef87.png)
  
## <a name="allow-or-block-guest-access-based-on-their-domain"></a><span data-ttu-id="3f45e-121">Consentire o bloccare l'accesso guest in base al proprio dominio</span><span class="sxs-lookup"><span data-stu-id="3f45e-121">Allow or block guest access based on their domain</span></span>

<span data-ttu-id="3f45e-122">È possibile consentire o bloccare gli utenti guest che utilizzano un dominio specifico.</span><span class="sxs-lookup"><span data-stu-id="3f45e-122">You can allow or block guests who are using a specific domain.</span></span> <span data-ttu-id="3f45e-123">Ad esempio, se l'azienda (Contoso) ha una partnership con un'altra azienda (Fabrikam), è possibile aggiungere Fabrikam all'elenco Consenti in modo che gli utenti possano aggiungere tali utenti guest ai propri gruppi.</span><span class="sxs-lookup"><span data-stu-id="3f45e-123">For example, if your business (Contoso) has a partnership with another business (Fabrikam), you can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span>

<span data-ttu-id="3f45e-124">Per ulteriori informazioni, vedere [Allow or block invitations to B2B users from specific organizations](/azure/active-directory/b2b/allow-deny-list).</span><span class="sxs-lookup"><span data-stu-id="3f45e-124">For more information, see [Allow or block invitations to B2B users from specific organizations](/azure/active-directory/b2b/allow-deny-list).</span></span>

## <a name="add-guests-to-the-global-address-list"></a><span data-ttu-id="3f45e-125">Aggiungere utenti guest all'elenco indirizzi globale</span><span class="sxs-lookup"><span data-stu-id="3f45e-125">Add guests to the global address list</span></span>

<span data-ttu-id="3f45e-126">Per impostazione predefinita, gli utenti guest non sono visibili nell'elenco indirizzi globale di Exchange.</span><span class="sxs-lookup"><span data-stu-id="3f45e-126">By default, guests aren't visible in the Exchange Global Address List.</span></span> <span data-ttu-id="3f45e-127">Seguire i passaggi elencati di seguito per rendere visibile un guest nell'elenco indirizzi globale.</span><span class="sxs-lookup"><span data-stu-id="3f45e-127">Use the steps listed below to make a guest visible in the global address list.</span></span>

<span data-ttu-id="3f45e-128">Trovare l'ObjectID del guest eseguendo:</span><span class="sxs-lookup"><span data-stu-id="3f45e-128">Find the guest's ObjectID by running:</span></span>

```PowerShell
Get-AzureADUser -Filter "userType eq 'Guest'"
```

<span data-ttu-id="3f45e-129">Eseguire quindi le operazioni seguenti utilizzando i valori appropriati per ObjectID, GivenName, Surname, DisplayName e TelephoneNumber.</span><span class="sxs-lookup"><span data-stu-id="3f45e-129">Then run the following using the appropriate values for ObjectID, GivenName, Surname, DisplayName, and TelephoneNumber.</span></span>

```PowerShell
Set-AzureADUser -ObjectId cfcbd1a0-ed18-4210-9b9d-cf0ba93cf6b2 -ShowInAddressList $true -GivenName 'Megan' -Surname 'Bowen' -DisplayName 'Megan Bowen' -TelephoneNumber '555-555-5555'
```

## <a name="related-topics"></a><span data-ttu-id="3f45e-130">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="3f45e-130">Related topics</span></span>

[<span data-ttu-id="3f45e-131">Pianificazione dettagliata della governance della collaborazione</span><span class="sxs-lookup"><span data-stu-id="3f45e-131">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="3f45e-132">Creare il piano di governance della collaborazione</span><span class="sxs-lookup"><span data-stu-id="3f45e-132">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="3f45e-133">Gestire l'appartenenza ai gruppi nell'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3f45e-133">Manage Group membership in the Microsoft 365 admin center</span></span>](../admin/create-groups/add-or-remove-members-from-groups.md)
  
[<span data-ttu-id="3f45e-134">Verifiche di accesso ad Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="3f45e-134">Azure Active Directory access reviews</span></span>](/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[<span data-ttu-id="3f45e-135">Set-AzureADUser</span><span class="sxs-lookup"><span data-stu-id="3f45e-135">Set-AzureADUser</span></span>](/powershell/module/azuread/set-azureaduser)