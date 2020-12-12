---
title: Impedire agli utenti di essere aggiunti a un gruppo specifico
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
description: Informazioni su come impedire agli utenti di essere aggiunti a un gruppo specifico
ms.openlocfilehash: 8bee26bf5ec323536ca1ac6f25ce96927634cee7
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2020
ms.locfileid: "49660049"
---
# <a name="prevent-guests-from-being-added-to-a-specific-microsoft-365-group-or-microsoft-teams-team"></a><span data-ttu-id="a40e0-103">Impedire agli utenti di essere aggiunti a un gruppo Microsoft 365 o a un team di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a40e0-103">Prevent guests from being added to a specific Microsoft 365 group or Microsoft Teams team</span></span>

<span data-ttu-id="a40e0-104">Se si desidera consentire agli utenti di accedere alla maggior parte dei gruppi e ai team, ma si desidera impedire l'accesso guest, è possibile bloccare l'accesso guest per singoli gruppi e team.</span><span class="sxs-lookup"><span data-stu-id="a40e0-104">If you want to allow guest access to most groups and teams, but have some where you want to prevent guest access, you can block guest access for individual groups and teams.</span></span> <span data-ttu-id="a40e0-105">Bloccando l'accesso Guest a un team, è possibile bloccare l'accesso Guest al gruppo associato. In questo modo si impedisce l'aggiunta di nuovi ospiti, ma non vengono rimossi gli ospiti già presenti nel gruppo o nel team.</span><span class="sxs-lookup"><span data-stu-id="a40e0-105">(Blocking guest access to a team is done by blocking guest access to the associated group.) This prevents new guests from being added but does not remove guests that are already in the group or team.</span></span>

<span data-ttu-id="a40e0-106">Se si utilizzano le etichette di riservatezza nell'organizzazione, è consigliabile utilizzarle per controllare l'accesso guest per ogni singolo gruppo.</span><span class="sxs-lookup"><span data-stu-id="a40e0-106">If you use sensitivity labels in your organization, we recommend using them to control guest access on a per-group basis.</span></span> <span data-ttu-id="a40e0-107">Per informazioni su come eseguire questa operazione, [utilizzare le etichette di riservatezza per proteggere il contenuto in Microsoft teams, microsoft 365 Groups e SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span><span class="sxs-lookup"><span data-stu-id="a40e0-107">For information about how to do this, [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span> <span data-ttu-id="a40e0-108">Questo è l'approccio consigliato.</span><span class="sxs-lookup"><span data-stu-id="a40e0-108">This is the recommended approach.</span></span>

## <a name="change-group-settings-using-microsoft-powershell"></a><span data-ttu-id="a40e0-109">Modificare le impostazioni di gruppo mediante Microsoft PowerShell</span><span class="sxs-lookup"><span data-stu-id="a40e0-109">Change group settings using Microsoft PowerShell</span></span>

<span data-ttu-id="a40e0-110">È inoltre possibile impedire l'aggiunta di nuovi ospiti ai singoli gruppi tramite PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a40e0-110">You can also prevent the addition of new guests to individual groups by using PowerShell.</span></span> <span data-ttu-id="a40e0-111">Tenere presente che il sito di SharePoint associato del team ha [controlli di condivisione Guest distinti](https://docs.microsoft.com/sharepoint/change-external-sharing-site).</span><span class="sxs-lookup"><span data-stu-id="a40e0-111">(Remember that the team's associated SharePoint site has [separate guest sharing controls](https://docs.microsoft.com/sharepoint/change-external-sharing-site).)</span></span>

<span data-ttu-id="a40e0-112">È necessario utilizzare la versione di anteprima di [Azure Active Directory PowerShell per Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (Module Name **AzureADPreview**) per modificare l'impostazione di accesso Guest a livello di gruppo:</span><span class="sxs-lookup"><span data-stu-id="a40e0-112">You must use the preview version of [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:</span></span>

- <span data-ttu-id="a40e0-113">Se non è ancora stata installata una versione del modulo PowerShell di Azure AD, vedere [installare il modulo Azure AD](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview&preserve-view=true) e seguire le istruzioni per installare la versione di anteprima pubblica.</span><span class="sxs-lookup"><span data-stu-id="a40e0-113">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview&preserve-view=true) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="a40e0-114">Se è installata la versione 2.0 disponibile a livello generale del modulo PowerShell di Azure AD (AzureAD), è necessario disinstallarlo eseguendo `Uninstall-Module AzureAD` nella sessione di PowerShell e quindi installare la versione di anteprima eseguendo `Install-Module AzureADPreview`.</span><span class="sxs-lookup"><span data-stu-id="a40e0-114">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="a40e0-115">Se è già stata installata la versione Preview, eseguire `Install-Module AzureADPreview` per verificare che sia la versione più recente di questo modulo.</span><span class="sxs-lookup"><span data-stu-id="a40e0-115">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>

> [!NOTE]
> <span data-ttu-id="a40e0-116">È necessario disporre dei diritti di amministratore globale per eseguire questi comandi.</span><span class="sxs-lookup"><span data-stu-id="a40e0-116">You must have global admin rights to run these commands.</span></span> 

<span data-ttu-id="a40e0-117">Eseguire lo script seguente, modificando */<GroupName/>* il nome del gruppo in cui si desidera bloccare l'accesso guest.</span><span class="sxs-lookup"><span data-stu-id="a40e0-117">Run the following script, changing */<GroupName/>* to the name of the group where you want to block guest access.</span></span>

```PowerShell
$GroupName = "<GroupName>"

Connect-AzureAD

$template = Get-AzureADDirectorySettingTemplate | ? {$_.displayname -eq "group.unified.guest"}
$settingsCopy = $template.CreateDirectorySetting()
$settingsCopy["AllowToAddGuests"]=$False
$groupID= (Get-AzureADGroup -SearchString $GroupName).ObjectId
New-AzureADObjectSetting -TargetType Groups -TargetObjectId $groupID -DirectorySetting $settingsCopy
```

<span data-ttu-id="a40e0-118">Per verificare le impostazioni, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="a40e0-118">To verify your settings, run this command:</span></span>

```PowerShell
Get-AzureADObjectSetting -TargetObjectId $groupID -TargetType Groups | fl Values
```

<span data-ttu-id="a40e0-119">La verifica è simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="a40e0-119">The verification looks like this:</span></span>
    
![Schermata della finestra di PowerShell che indica che l'accesso al gruppo Guest è stato impostato su false.](../media/09ebfb4f-859f-44c3-a29e-63a59fd6ef87.png)
  
## <a name="allow-or-block-guest-access-based-on-their-domain"></a><span data-ttu-id="a40e0-121">Consenti o blocca l'accesso guest in base al dominio</span><span class="sxs-lookup"><span data-stu-id="a40e0-121">Allow or block guest access based on their domain</span></span>

<span data-ttu-id="a40e0-122">È possibile consentire o bloccare gli utenti che utilizzano un dominio specifico.</span><span class="sxs-lookup"><span data-stu-id="a40e0-122">You can allow or block guests who are using a specific domain.</span></span> <span data-ttu-id="a40e0-123">Ad esempio, se la propria azienda (contoso) ha una partnership con un'altra azienda (Fabrikam), è possibile aggiungere Fabrikam all'elenco Consenti in modo che gli utenti possano aggiungerli ai propri gruppi.</span><span class="sxs-lookup"><span data-stu-id="a40e0-123">For example, if your business (Contoso) has a partnership with another business (Fabrikam), you can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span>

<span data-ttu-id="a40e0-124">Per ulteriori informazioni, vedere [Consenti o blocca gli inviti agli utenti B2B provenienti da organizzazioni specifiche](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span><span class="sxs-lookup"><span data-stu-id="a40e0-124">For more information, see [Allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span></span>

## <a name="add-guests-to-the-global-address-list"></a><span data-ttu-id="a40e0-125">Aggiungere gli ospiti all'elenco indirizzi globale</span><span class="sxs-lookup"><span data-stu-id="a40e0-125">Add guests to the global address list</span></span>

<span data-ttu-id="a40e0-126">Per impostazione predefinita, gli utenti non sono visibili nell'elenco indirizzi globale di Exchange.</span><span class="sxs-lookup"><span data-stu-id="a40e0-126">By default, guests aren't visible in the Exchange Global Address List.</span></span> <span data-ttu-id="a40e0-127">Utilizzare la procedura riportata di seguito per rendere visibile un ospite nell'elenco indirizzi globale.</span><span class="sxs-lookup"><span data-stu-id="a40e0-127">Use the steps listed below to make a guest visible in the global address list.</span></span>

<span data-ttu-id="a40e0-128">Individuare l'ObjectID dell'ospite eseguendo le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a40e0-128">Find the guest's ObjectID by running:</span></span>

```PowerShell
Get-AzureADUser -Filter "userType eq 'Guest'"
```

<span data-ttu-id="a40e0-129">Eseguire quindi il comando seguente utilizzando i valori corretti per ObjectID, DATENAME, cognome, DisplayName e TelephoneNumber.</span><span class="sxs-lookup"><span data-stu-id="a40e0-129">Then run the following using the appropriate values for ObjectID, GivenName, Surname, DisplayName, and TelephoneNumber.</span></span>

```PowerShell
Set-AzureADUser -ObjectId cfcbd1a0-ed18-4210-9b9d-cf0ba93cf6b2 -ShowInAddressList $true -GivenName 'Megan' -Surname 'Bowen' -DisplayName 'Megan Bowen' -TelephoneNumber '555-555-5555'
```

## <a name="related-topics"></a><span data-ttu-id="a40e0-130">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="a40e0-130">Related topics</span></span>

[<span data-ttu-id="a40e0-131">Pianificazione della governance della collaborazione</span><span class="sxs-lookup"><span data-stu-id="a40e0-131">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="a40e0-132">Creare il piano di governance di collaborazione</span><span class="sxs-lookup"><span data-stu-id="a40e0-132">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="a40e0-133">Gestire l'appartenenza ai gruppi nell'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a40e0-133">Manage Group membership in the Microsoft 365 admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/create-groups/add-or-remove-members-from-groups)
  
[<span data-ttu-id="a40e0-134">Recensioni di Azure Active Directory Access</span><span class="sxs-lookup"><span data-stu-id="a40e0-134">Azure Active Directory access reviews</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[<span data-ttu-id="a40e0-135">Set-AzureADUser</span><span class="sxs-lookup"><span data-stu-id="a40e0-135">Set-AzureADUser</span></span>](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)
