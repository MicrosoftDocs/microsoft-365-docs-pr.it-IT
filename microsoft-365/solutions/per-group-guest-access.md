---
title: Impedire che gli utenti guest vengano aggiunti a un gruppo specifico
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
description: Informazioni su come impedire che gli utenti guest vengano aggiunti a un gruppo specifico
ms.openlocfilehash: 91c7560186fb0b954075e9ff9c997b34121951cd
ms.sourcegitcommit: cdf2b8dad7db9e16afd339abaaa5397faf11807c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/21/2020
ms.locfileid: "48651351"
---
# <a name="prevent-guest-users-from-being-added-to-a-specific-microsoft-365-group-or-microsoft-teams-team"></a>Impedire che gli utenti guest vengano aggiunti a un gruppo Microsoft 365 o a un team di Microsoft Teams

Se si desidera consentire agli utenti di accedere alla maggior parte dei gruppi e ai team, ma si desidera impedire l'accesso guest, è possibile bloccare l'accesso guest per singoli gruppi e team. Bloccando l'accesso Guest a un team, è possibile bloccare l'accesso Guest al gruppo associato. In questo modo si impedisce l'aggiunta di nuovi ospiti, ma non vengono rimossi gli ospiti già presenti nel gruppo o nel team.

Se si utilizzano le etichette di riservatezza nell'organizzazione, è consigliabile utilizzarle per controllare l'accesso guest per ogni singolo gruppo. Per informazioni su come eseguire questa operazione, [utilizzare le etichette di riservatezza per proteggere il contenuto in Microsoft teams, microsoft 365 Groups e SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites). Questo è l'approccio consigliato.

## <a name="change-group-settings-using-microsoft-powershell"></a>Modificare le impostazioni di gruppo mediante Microsoft PowerShell

È inoltre possibile impedire l'aggiunta di nuovi ospiti ai singoli gruppi tramite PowerShell.

È necessario utilizzare la versione di anteprima di [Azure Active Directory PowerShell per Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (Module Name **AzureADPreview**) per modificare l'impostazione di accesso Guest a livello di gruppo:

- Se non è ancora stata installata una versione del modulo PowerShell di Azure AD, vedere [installare il modulo Azure AD](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview&preserve-view=true) e seguire le istruzioni per installare la versione di anteprima pubblica.

- Se è installata la versione 2.0 disponibile a livello generale del modulo PowerShell di Azure AD (AzureAD), è necessario disinstallarlo eseguendo `Uninstall-Module AzureAD` nella sessione di PowerShell e quindi installare la versione di anteprima eseguendo `Install-Module AzureADPreview`.

- Se è già stata installata la versione Preview, eseguire `Install-Module AzureADPreview` per verificare che sia la versione più recente di questo modulo.

> [!NOTE]
> È necessario disporre dei diritti di amministratore globale per eseguire questi comandi. 

Eseguire lo script seguente, modificando */<GroupName/>* il nome del gruppo in cui si desidera bloccare l'accesso guest.

```PowerShell
$GroupName = "<GroupName>"

Connect-AzureAD

$template = Get-AzureADDirectorySettingTemplate | ? {$_.displayname -eq "group.unified.guest"}
$settingsCopy = $template.CreateDirectorySetting()
$settingsCopy["AllowToAddGuests"]=$False
$groupID= (Get-AzureADGroup -SearchString $GroupName).ObjectId
New-AzureADObjectSetting -TargetType Groups -TargetObjectId $groupID -DirectorySetting $settingsCopy
```

Per verificare le impostazioni, eseguire il comando seguente:

```PowerShell
Get-AzureADObjectSetting -TargetObjectId $groupID -TargetType Groups | fl Values
```

La verifica è simile alla seguente:
    
![Schermata della finestra di PowerShell che indica che l'accesso al gruppo Guest è stato impostato su false.](../media/09ebfb4f-859f-44c3-a29e-63a59fd6ef87.png)
  
## <a name="allow-or-block-guest-access-based-on-their-domain"></a>Consenti o blocca l'accesso guest in base al dominio

È possibile autorizzare o bloccare utenti guest che utilizzano uno specifico dominio. Ad esempio, se la propria azienda (contoso) ha una partnership con un'altra azienda (Fabrikam), è possibile aggiungere Fabrikam all'elenco Consenti in modo che gli utenti possano aggiungerli ai propri gruppi.

Per ulteriori informazioni, vedere [Consenti o blocca gli inviti agli utenti B2B provenienti da organizzazioni specifiche](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).

## <a name="add-guests-to-the-global-address-list"></a>Aggiungere gli ospiti all'elenco indirizzi globale

Per impostazione predefinita, gli utenti non sono visibili nell'elenco indirizzi globale di Exchange. Utilizzare la procedura riportata di seguito per rendere visibile un ospite nell'elenco indirizzi globale.

Individuare l'ObjectID dell'utente Guest eseguendo:

```PowerShell
Get-AzureADUser -Filter "userType eq 'Guest'"
```

Eseguire quindi il comando seguente utilizzando i valori corretti per ObjectID, DATENAME, cognome, DisplayName e TelephoneNumber.

```PowerShell
Set-AzureADUser -ObjectId cfcbd1a0-ed18-4210-9b9d-cf0ba93cf6b2 -ShowInAddressList $true -GivenName 'Megan' -Surname 'Bowen' -DisplayName 'Megan Bowen' -TelephoneNumber '555-555-5555'
```

## <a name="related-articles"></a>Articoli correlati

[Gestire l'appartenenza ai gruppi nell'interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/create-groups/add-or-remove-members-from-groups)
  
[Recensioni di Azure Active Directory Access](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)
