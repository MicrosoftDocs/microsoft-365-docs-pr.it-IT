---
title: Gestire l'accesso guest nei gruppi di Microsoft 365
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
ms.assetid: 9de497a9-2f5c-43d6-ae18-767f2e6fe6e0
description: Informazioni su come aggiungere gli ospiti a un gruppo di Microsoft 365, visualizzare gli utenti guest e utilizzare PowerShell per controllare l'accesso guest.
ms.openlocfilehash: 0322bd269f1c5637627461d136b40f6af4fc9540
ms.sourcegitcommit: 4512f54ba80d869d4c04e8f9bd897d1878280852
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "44854247"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a>Gestire l'accesso guest nei gruppi di Microsoft 365

Per impostazione predefinita, l'accesso guest per i gruppi di Microsoft 365 è attivato per l'organizzazione. Gli amministratori possono controllare se consentire l'accesso Guest ai gruppi per l'intera organizzazione o per i singoli gruppi.

Quando è attivata, i membri del gruppo possono invitare gli utenti Guest a un gruppo di Microsoft 365 tramite Outlook sul Web. Gli inviti vengono inviati al proprietario del gruppo per l'approvazione.

Una volta approvato, l'utente ospite viene aggiunto alla directory e al gruppo.

> [!Note]
> Le reti aziendali di Yammer che si trovano in modalità nativa o l' [eu Geo](https://go.microsoft.com/fwlink/?linkid=2107357) non supportano gli utenti della rete.
> I gruppi di Yammer connessi a Microsoft 365 non supportano attualmente l'accesso guest, ma è possibile creare gruppi esterni non connessi nella rete Yammer. Per istruzioni, vedere [creare e gestire gruppi esterni in Yammer](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-external-groups) .

L'accesso guest nei gruppi è spesso utilizzato come parte di uno scenario più ampio che include SharePoint o teams. Tali servizi dispongono di impostazioni di condivisione Guest. Per istruzioni complete su come configurare la condivisione Guest tra gruppi, SharePoint e team, vedere:

- [Collaborare con gli utenti guest a un sito](../../solutions/collaborate-in-site.md)
- [Collaborare con gli utenti guest in un team](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a>Gestione degli accessi ai gruppi

Se si desidera abilitare o disabilitare l'accesso guest nei gruppi, è possibile farlo nell'interfaccia di amministrazione di Microsoft 365.

1. Nell'interfaccia di amministrazione, andare a **Mostra tutte** le impostazioni \> **Settings** \> **org** impostazioni e nella scheda **Servizi** , selezionare **Microsoft 365 gruppi**.
  
2. Nella pagina **Microsoft 365 groups** , scegliere se si desidera consentire agli utenti esterni all'organizzazione di accedere alle risorse del gruppo o consentire ai proprietari di gruppi di aggiungere persone esterne all'organizzazione.

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a>Aggiungere gli utenti a un gruppo di Microsoft 365 dall'interfaccia di amministrazione

Se l'ospite è già presente nella directory, è possibile aggiungerli ai gruppi dall'interfaccia di amministrazione di Microsoft 365.
  
1. Nell'interfaccia di amministrazione, andare alla pagina **gruppi**  >  **Groups** .
  
2. Fare clic sul gruppo a cui si desidera aggiungere l'ospite e selezionare **Visualizza tutti e Gestisci membri** nella scheda **membri** . 
  
4. Selezionare **Aggiungi membri**e scegliere il nome del Guest che si desidera aggiungere.
    
5. Selezionare **Salva**.

Se si desidera aggiungere direttamente un guest alla directory, è possibile [aggiungere gli utenti di collaborazione B2B di Azure Active Directory nel portale di Azure](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).

Se si desidera modificare le informazioni di un ospite, è possibile [aggiungere o aggiornare le informazioni del profilo di un utente utilizzando Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).
  
## <a name="block-guest-users-from-a-specific-group"></a>Bloccare gli utenti Guest da un gruppo specifico

Se si desidera consentire l'accesso guest alla maggior parte dei gruppi, ma si desidera impedire l'accesso guest, è possibile bloccare l'accesso guest per i singoli gruppi tramite Microsoft PowerShell.

È necessario utilizzare la versione di anteprima di [Azure Active Directory PowerShell per Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (Module Name **AzureADPreview**) per modificare l'impostazione di accesso Guest a livello di gruppo:

- Se non è ancora stata installata una versione del modulo PowerShell di Azure AD, vedere [installare il modulo Azure AD](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) e seguire le istruzioni per installare la versione di anteprima pubblica.

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
    
![Schermata della finestra di PowerShell che indica che l'accesso al gruppo Guest è stato impostato su false.](../../media/09ebfb4f-859f-44c3-a29e-63a59fd6ef87.png)
  
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

[Gestire l'appartenenza ai gruppi nell'interfaccia di amministrazione di Microsoft 365](add-or-remove-members-from-groups.md)
  
[Recensioni di Azure Active Directory Access](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)
