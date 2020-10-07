---
title: Bloccare gli utenti Guest da un gruppo specifico
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
description: Bloccare gli utenti Guest da un gruppo specifico
ms.openlocfilehash: 17e5f8f9ab4107a12a0607dca3795d54b7be012c
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377307"
---
# <a name="block-guest-users-from-a-specific-microsoft-365-group-or-microsoft-teams-team"></a><span data-ttu-id="33594-103">Bloccare gli utenti Guest da uno specifico gruppo di Microsoft 365 o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="33594-103">Block guest users from a specific Microsoft 365 group or Microsoft Teams team</span></span>

<span data-ttu-id="33594-104">Se si desidera consentire agli utenti di accedere alla maggior parte dei gruppi e ai team, ma si desidera impedire l'accesso guest, è possibile bloccare l'accesso guest per singoli gruppi e team.</span><span class="sxs-lookup"><span data-stu-id="33594-104">If you want to allow guest access to most groups and teams, but have some where you want to prevent guest access, you can block guest access for individual groups and teams.</span></span> <span data-ttu-id="33594-105">Bloccando l'accesso Guest a un team, è possibile bloccare l'accesso Guest al gruppo associato.</span><span class="sxs-lookup"><span data-stu-id="33594-105">(Blocking guest access to a team is done by blocking guest access to the associated group.)</span></span>

<span data-ttu-id="33594-106">Se si utilizzano le etichette di riservatezza nell'organizzazione, è consigliabile utilizzarle per controllare l'accesso guest per ogni singolo gruppo.</span><span class="sxs-lookup"><span data-stu-id="33594-106">If you use sensitivity labels in your organization, we recommend using them to control guest access on a per-group basis.</span></span> <span data-ttu-id="33594-107">Per informazioni su come eseguire questa operazione, [utilizzare le etichette di riservatezza per proteggere il contenuto in Microsoft teams, microsoft 365 Groups e SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span><span class="sxs-lookup"><span data-stu-id="33594-107">For information about how to do this, [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span> <span data-ttu-id="33594-108">Questo è l'approccio consigliato.</span><span class="sxs-lookup"><span data-stu-id="33594-108">This is the recommended approach.</span></span>

<span data-ttu-id="33594-109">È inoltre possibile bloccare l'accesso Guest ai singoli gruppi tramite Microsoft PowerShell.</span><span class="sxs-lookup"><span data-stu-id="33594-109">You can also block guest access to individual groups by using Microsoft PowerShell.</span></span>

<span data-ttu-id="33594-110">È necessario utilizzare la versione di anteprima di [Azure Active Directory PowerShell per Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (Module Name **AzureADPreview**) per modificare l'impostazione di accesso Guest a livello di gruppo:</span><span class="sxs-lookup"><span data-stu-id="33594-110">You must use the preview version of [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:</span></span>

- <span data-ttu-id="33594-111">Se non è ancora stata installata una versione del modulo PowerShell di Azure AD, vedere [installare il modulo Azure AD](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview&preserve-view=true) e seguire le istruzioni per installare la versione di anteprima pubblica.</span><span class="sxs-lookup"><span data-stu-id="33594-111">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview&preserve-view=true) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="33594-112">Se è installata la versione 2.0 disponibile a livello generale del modulo PowerShell di Azure AD (AzureAD), è necessario disinstallarlo eseguendo `Uninstall-Module AzureAD` nella sessione di PowerShell e quindi installare la versione di anteprima eseguendo `Install-Module AzureADPreview`.</span><span class="sxs-lookup"><span data-stu-id="33594-112">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="33594-113">Se è già stata installata la versione Preview, eseguire `Install-Module AzureADPreview` per verificare che sia la versione più recente di questo modulo.</span><span class="sxs-lookup"><span data-stu-id="33594-113">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>

> [!NOTE]
> <span data-ttu-id="33594-114">È necessario disporre dei diritti di amministratore globale per eseguire questi comandi.</span><span class="sxs-lookup"><span data-stu-id="33594-114">You must have global admin rights to run these commands.</span></span> 

<span data-ttu-id="33594-115">Eseguire lo script seguente, modificando */<GroupName/>* il nome del gruppo in cui si desidera bloccare l'accesso guest.</span><span class="sxs-lookup"><span data-stu-id="33594-115">Run the following script, changing */<GroupName/>* to the name of the group where you want to block guest access.</span></span>

```PowerShell
$GroupName = "<GroupName>"

Connect-AzureAD

$template = Get-AzureADDirectorySettingTemplate | ? {$_.displayname -eq "group.unified.guest"}
$settingsCopy = $template.CreateDirectorySetting()
$settingsCopy["AllowToAddGuests"]=$False
$groupID= (Get-AzureADGroup -SearchString $GroupName).ObjectId
New-AzureADObjectSetting -TargetType Groups -TargetObjectId $groupID -DirectorySetting $settingsCopy
```

<span data-ttu-id="33594-116">Per verificare le impostazioni, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="33594-116">To verify your settings, run this command:</span></span>

```PowerShell
Get-AzureADObjectSetting -TargetObjectId $groupID -TargetType Groups | fl Values
```

<span data-ttu-id="33594-117">La verifica è simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="33594-117">The verification looks like this:</span></span>
    
![Schermata della finestra di PowerShell che indica che l'accesso al gruppo Guest è stato impostato su false.](../media/09ebfb4f-859f-44c3-a29e-63a59fd6ef87.png)
  
## <a name="allow-or-block-guest-access-based-on-their-domain"></a><span data-ttu-id="33594-119">Consenti o blocca l'accesso guest in base al dominio</span><span class="sxs-lookup"><span data-stu-id="33594-119">Allow or block guest access based on their domain</span></span>

<span data-ttu-id="33594-120">È possibile autorizzare o bloccare utenti guest che utilizzano uno specifico dominio.</span><span class="sxs-lookup"><span data-stu-id="33594-120">You can allow or block guest users who are using a specific domain.</span></span> <span data-ttu-id="33594-121">Ad esempio, se la propria azienda (contoso) ha una partnership con un'altra azienda (Fabrikam), è possibile aggiungere Fabrikam all'elenco Consenti in modo che gli utenti possano aggiungerli ai propri gruppi.</span><span class="sxs-lookup"><span data-stu-id="33594-121">For example, if your business (Contoso) has a partnership with another business (Fabrikam), you can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span>

<span data-ttu-id="33594-122">Per ulteriori informazioni, vedere [Consenti o blocca gli inviti agli utenti B2B provenienti da organizzazioni specifiche](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span><span class="sxs-lookup"><span data-stu-id="33594-122">For more information, see [Allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span></span>

## <a name="add-guests-to-the-global-address-list"></a><span data-ttu-id="33594-123">Aggiungere gli ospiti all'elenco indirizzi globale</span><span class="sxs-lookup"><span data-stu-id="33594-123">Add guests to the global address list</span></span>

<span data-ttu-id="33594-124">Per impostazione predefinita, gli utenti non sono visibili nell'elenco indirizzi globale di Exchange.</span><span class="sxs-lookup"><span data-stu-id="33594-124">By default, guests aren't visible in the Exchange Global Address List.</span></span> <span data-ttu-id="33594-125">Utilizzare la procedura riportata di seguito per rendere visibile un ospite nell'elenco indirizzi globale.</span><span class="sxs-lookup"><span data-stu-id="33594-125">Use the steps listed below to make a guest visible in the global address list.</span></span>

<span data-ttu-id="33594-126">Individuare l'ObjectID dell'utente Guest eseguendo:</span><span class="sxs-lookup"><span data-stu-id="33594-126">Find the guest user's ObjectID by running:</span></span>

```PowerShell
Get-AzureADUser -Filter "userType eq 'Guest'"
```

<span data-ttu-id="33594-127">Eseguire quindi il comando seguente utilizzando i valori corretti per ObjectID, DATENAME, cognome, DisplayName e TelephoneNumber.</span><span class="sxs-lookup"><span data-stu-id="33594-127">Then run the following using the appropriate values for ObjectID, GivenName, Surname, DisplayName, and TelephoneNumber.</span></span>

```PowerShell
Set-AzureADUser -ObjectId cfcbd1a0-ed18-4210-9b9d-cf0ba93cf6b2 -ShowInAddressList $true -GivenName 'Megan' -Surname 'Bowen' -DisplayName 'Megan Bowen' -TelephoneNumber '555-555-5555'
```

## <a name="related-articles"></a><span data-ttu-id="33594-128">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="33594-128">Related articles</span></span>

[<span data-ttu-id="33594-129">Gestire l'appartenenza ai gruppi nell'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="33594-129">Manage Group membership in the Microsoft 365 admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/create-groups/add-or-remove-members-from-groups)
  
[<span data-ttu-id="33594-130">Recensioni di Azure Active Directory Access</span><span class="sxs-lookup"><span data-stu-id="33594-130">Azure Active Directory access reviews</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[<span data-ttu-id="33594-131">Set-AzureADUser</span><span class="sxs-lookup"><span data-stu-id="33594-131">Set-AzureADUser</span></span>](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)