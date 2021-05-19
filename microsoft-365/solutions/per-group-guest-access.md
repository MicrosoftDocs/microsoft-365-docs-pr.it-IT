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
recommendations: false
description: Informazioni su come impedire l'aggiunta di utenti guest a un gruppo specifico
ms.openlocfilehash: 1db2055f3e546c05905dbf4c854333387112f06e
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538928"
---
# <a name="prevent-guests-from-being-added-to-a-specific-microsoft-365-group-or-microsoft-teams-team"></a>Impedire l'aggiunta di guest a un gruppo Microsoft 365 o a un team Microsoft Teams utenti

Se si desidera consentire l'accesso guest alla maggior parte dei gruppi e dei team, ma si desidera impedire l'accesso guest, è possibile bloccare l'accesso guest per singoli gruppi e team. Il blocco dell'accesso guest a un team viene eseguito bloccando l'accesso guest al gruppo associato. Ciò impedisce l'aggiunta di nuovi guest, ma non rimuove gli utenti guest già presenti nel gruppo o nel team.

Se si utilizzano etichette di riservatezza nell'organizzazione, è consigliabile usarle per controllare l'accesso guest per ogni gruppo. Per informazioni su come eseguire questa operazione, utilizzare le etichette di riservatezza per proteggere il contenuto [in Microsoft Teams, Microsoft 365](../compliance/sensitivity-labels-teams-groups-sites.md)gruppi e SharePoint siti. Questo è l'approccio consigliato.

## <a name="change-group-settings-using-microsoft-powershell"></a>Modificare le impostazioni dei gruppi con Microsoft PowerShell

È inoltre possibile impedire l'aggiunta di nuovi guest a singoli gruppi tramite PowerShell. Tenere presente che il sito del team SharePoint dispone [di controlli di condivisione guest separati.](/sharepoint/change-external-sharing-site)

È necessario utilizzare la versione di anteprima di [Azure Active Directory PowerShell per Graph](/powershell/azure/active-directory/install-adv2) (nome modulo **AzureADPreview**) per modificare l'impostazione di accesso guest a livello di gruppo:

- Se non è ancora stata installata una versione del modulo PowerShell di Azure AD, vedere [installare il modulo Azure AD](/powershell/azure/active-directory/install-adv2?preserve-view=true&view=azureadps-2.0-preview) e seguire le istruzioni per installare la versione di anteprima pubblica.

- Se è installata la versione 2.0 disponibile a livello generale del modulo PowerShell di Azure AD (AzureAD), è necessario disinstallarlo eseguendo `Uninstall-Module AzureAD` nella sessione di PowerShell e quindi installare la versione di anteprima eseguendo `Install-Module AzureADPreview`.

- Se è già stata installata la versione Preview, eseguire `Install-Module AzureADPreview` per verificare che sia la versione più recente di questo modulo.

> [!NOTE]
> Per eseguire questi comandi, è necessario disporre dei diritti di amministratore globale. 

Eseguire lo script seguente, modificando il nome del gruppo in cui */<GroupName/>* si desidera bloccare l'accesso guest.

```PowerShell
$GroupName = "<GroupName>"

Connect-AzureAD

$template = Get-AzureADDirectorySettingTemplate | ? {$_.displayname -eq "group.unified.guest"}
$settingsCopy = $template.CreateDirectorySetting()
$settingsCopy["AllowToAddGuests"]=$False
$groupID= (Get-AzureADGroup -SearchString $GroupName).ObjectId
New-AzureADObjectSetting -TargetType Groups -TargetObjectId $groupID -DirectorySetting $settingsCopy
```

Per verificare le impostazioni, eseguire questo comando:

```PowerShell
Get-AzureADObjectSetting -TargetObjectId $groupID -TargetType Groups | fl Values
```

La verifica è simile alla seguente:
    
![Screenshot della finestra di PowerShell che mostra che l'accesso al gruppo guest è stato impostato su false.](../media/09ebfb4f-859f-44c3-a29e-63a59fd6ef87.png)
  
## <a name="allow-or-block-guest-access-based-on-their-domain"></a>Consentire o bloccare l'accesso guest in base al proprio dominio

È possibile consentire o bloccare gli utenti guest che utilizzano un dominio specifico. Ad esempio, se l'azienda (Contoso) ha una partnership con un'altra azienda (Fabrikam), è possibile aggiungere Fabrikam all'elenco Consenti in modo che gli utenti possano aggiungere tali utenti guest ai propri gruppi.

Per ulteriori informazioni, vedere [Allow or block invitations to B2B users from specific organizations](/azure/active-directory/b2b/allow-deny-list).

## <a name="add-guests-to-the-global-address-list"></a>Aggiungere utenti guest all'elenco indirizzi globale

Per impostazione predefinita, gli utenti guest non sono visibili nell'Exchange indirizzi globale. Seguire i passaggi elencati di seguito per rendere visibile un guest nell'elenco indirizzi globale.

Trovare l'ObjectID del guest eseguendo:

```PowerShell
Get-AzureADUser -Filter "userType eq 'Guest'"
```

Eseguire quindi le operazioni seguenti utilizzando i valori appropriati per ObjectID, GivenName, Surname, DisplayName e TelephoneNumber.

```PowerShell
Set-AzureADUser -ObjectId cfcbd1a0-ed18-4210-9b9d-cf0ba93cf6b2 -ShowInAddressList $true -GivenName 'Megan' -Surname 'Bowen' -DisplayName 'Megan Bowen' -TelephoneNumber '555-555-5555'
```

## <a name="related-topics"></a>Argomenti correlati

[Pianificazione dettagliata della governance della collaborazione](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Creare il piano di governance della collaborazione](collaboration-governance-first.md)

[Gestire l'appartenenza ai gruppi nell'Microsoft 365 di amministrazione](../admin/create-groups/add-or-remove-members-from-groups.md)
  
[Azure Active Directory di accesso](/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[Set-AzureADUser](/powershell/module/azuread/set-azureaduser)