---
title: Impedire l'aggiunta di utenti guest a un gruppo specifico
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
ms.openlocfilehash: 8bee26bf5ec323536ca1ac6f25ce96927634cee7
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2020
ms.locfileid: "49660049"
---
# <a name="prevent-guests-from-being-added-to-a-specific-microsoft-365-group-or-microsoft-teams-team"></a>Impedire l'aggiunta di utenti guest a un gruppo di Microsoft 365 o a un team di Microsoft Teams specifico

Se si desidera consentire l'accesso guest alla maggior parte dei gruppi e dei team, ma alcuni si desidera impedire l'accesso guest, è possibile bloccare l'accesso guest per singoli gruppi e team. Il blocco dell'accesso guest a un team viene eseguito bloccando l'accesso guest al gruppo associato. In questo modo si impedisce l'aggiunta di nuovi utenti guest, ma non gli utenti guest già presenti nel gruppo o nel team.

Se si usano etichette di riservatezza nell'organizzazione, è consigliabile usarle per controllare l'accesso guest per ogni gruppo. Per informazioni su come eseguire questa operazione, usare le etichette di riservatezza per proteggere il contenuto in Microsoft Teams, gruppi di [Microsoft 365 e siti di SharePoint.](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites) Questo è l'approccio consigliato.

## <a name="change-group-settings-using-microsoft-powershell"></a>Modificare le impostazioni di gruppo con Microsoft PowerShell

È inoltre possibile impedire l'aggiunta di nuovi utenti guest a singoli gruppi tramite PowerShell. Tenere presente che il sito di SharePoint associato al team dispone [di controlli di condivisione guest separati.](https://docs.microsoft.com/sharepoint/change-external-sharing-site)

È necessario utilizzare la versione di anteprima di [Azure Active Directory PowerShell per Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (nome modulo **AzureADPreview**) per modificare l'impostazione di accesso guest a livello di gruppo:

- Se non è ancora stata installata una versione del modulo PowerShell di Azure AD, vedere [installare il modulo Azure AD](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview&preserve-view=true) e seguire le istruzioni per installare la versione di anteprima pubblica.

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
    
![Screenshot of PowerShell window showing that guest group access has been set to false.](../media/09ebfb4f-859f-44c3-a29e-63a59fd6ef87.png)
  
## <a name="allow-or-block-guest-access-based-on-their-domain"></a>Consentire o bloccare l'accesso guest in base al dominio

È possibile consentire o bloccare gli utenti guest che utilizzano un dominio specifico. Ad esempio, se l'azienda (Contoso) ha una relazione con un'altra azienda (Fabrikam), è possibile aggiungere Fabrikam all'elenco Consenti in modo che gli utenti possano aggiungere tali utenti guest ai propri gruppi.

Per ulteriori informazioni, vedere Consentire o bloccare gli inviti a utenti [B2B di organizzazioni specifiche.](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)

## <a name="add-guests-to-the-global-address-list"></a>Aggiungere utenti guest all'elenco indirizzi globale

Per impostazione predefinita, gli utenti guest non sono visibili nell'elenco indirizzi globale di Exchange. Utilizzare i passaggi elencati di seguito per rendere visibile un guest nell'elenco indirizzi globale.

Trovare l'ObjectID del guest eseguendo:

```PowerShell
Get-AzureADUser -Filter "userType eq 'Guest'"
```

Eseguire quindi le operazioni seguenti utilizzando i valori appropriati per ObjectID, GivenName, Surname, DisplayName e TelephoneNumber.

```PowerShell
Set-AzureADUser -ObjectId cfcbd1a0-ed18-4210-9b9d-cf0ba93cf6b2 -ShowInAddressList $true -GivenName 'Megan' -Surname 'Bowen' -DisplayName 'Megan Bowen' -TelephoneNumber '555-555-5555'
```

## <a name="related-topics"></a>Argomenti correlati

[Procedura dettagliata per la pianificazione della governance della collaborazione](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Creare il piano di governance della collaborazione](collaboration-governance-first.md)

[Gestire l'appartenenza ai gruppi nell'interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/create-groups/add-or-remove-members-from-groups)
  
[Verifiche di accesso di Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)
