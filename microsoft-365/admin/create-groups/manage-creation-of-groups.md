---
title: Gestire gli utenti autorizzati a creare gruppi
f1.keywords: NOCSH
ms.author: mikeplum
ms.reviewer: arvaradh
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
- BCS160
- MSP160
- MST160
- MET150
- MOE150
ms.assetid: 4c46c8cb-17d0-44b5-9776-005fced8e618
description: Informazioni su come controllare quali utenti possono creare gruppi di Microsoft 365.
ms.openlocfilehash: b64e7ac96c5a0e38583d00f8a61bd47c5304cf45
ms.sourcegitcommit: 589f78fc0f39aff9109959ded48d146cc32fc3c5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44761675"
---
# <a name="manage-who-can-create-groups"></a>Gestire gli utenti autorizzati a creare gruppi

  
Poiché è così semplice per gli utenti creare gruppi di Microsoft 365, non si è sommersi dalle richieste di crearle per conto di altre persone. Tuttavia, a seconda dei requisiti aziendali, può essere opportuno controllare chi è autorizzato a creare gruppi.
  
In questo articolo viene illustrato come disabilitare la possibilità di creare gruppi in tutti i servizi di Microsoft 365 che utilizzano i gruppi, tra cui:
  
- Outlook
    
- SharePoint
    
- Yammer
    
- Microsoft Teams

- Microsoft Stream

- Planner
    
- PowerBI

- Progetto per il Web e la Guida di orientamento
    
È possibile limitare la creazione di un gruppo di Microsoft 365 ai membri di un gruppo di sicurezza specifico. Per configurarlo, è necessario utilizzare Windows PowerShell. In questo articolo vengono illustrati i passaggi necessari.
  
La procedura descritta in questo articolo non impedirà ai membri di determinati ruoli di creare gruppi. Gli amministratori globali possono creare gruppi tramite qualsiasi mezzo, ad esempio Microsoft 365 Admin Center, planner, teams, Exchange e SharePoint Online. Altri ruoli possono creare gruppi tramite mezzi limitati, elencati di seguito.
        
  - Amministratore di Exchange: interfaccia di amministrazione di Exchange, Azure AD
    
  - Supporto di partner Tier 1: interfaccia di amministrazione di Microsoft 365, interfaccia di amministrazione di Exchange, Azure AD
    
  - Supporto di partner Tier 2: interfaccia di amministrazione di Microsoft 365, interfaccia di amministrazione di Exchange, Azure AD
    
  - Scrittori di directory: Azure AD

  - Amministratore di SharePoint: interfaccia di amministrazione di SharePoint, Azure AD
  
  - Amministratore del servizio teams: interfaccia di amministrazione di teams, Azure AD
  
  - Amministratore Gestione utenti: interfaccia di amministrazione di Microsoft 365, Yammer, Azure AD
     
Se si è membri di uno di questi ruoli, è possibile creare gruppi Microsoft 365 per gli utenti con restrizioni e quindi assegnare l'utente come proprietario del gruppo. Gli utenti che dispongono di questo ruolo sono in grado di creare gruppi connessi in Yammer, indipendentemente dalle impostazioni di PowerShell che potrebbero impedire la creazione.

## <a name="licensing-requirements"></a>Requisiti per la licenza

Per gestire gli utenti che creano gruppi, le seguenti persone devono avere licenze Azure AD Premium o licenze di Azure AD Basic EDU ad essi assegnate:

- L'amministratore che configura queste impostazioni per la creazione di un gruppo
- I membri del gruppo di sicurezza a cui è consentito creare i gruppi

> [!NOTE]
> Per ulteriori informazioni su come assegnare le licenze di Azure, vedere [assegnare o rimuovere licenze nel portale di Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups) .

Gli utenti seguenti non hanno la necessità di assegnare loro le licenze Azure ad Premium o Azure AD Basic EDU:

- Utenti che sono membri di gruppi di Microsoft 365 e che non hanno la possibilità di creare altri gruppi.

## <a name="step-1-create-a-security-group-for-users-who-need-to-create-microsoft-365-groups"></a>Passaggio 1: creare un gruppo di sicurezza per gli utenti che hanno la necessità di creare gruppi di Microsoft 365

È possibile utilizzare un solo gruppo di sicurezza nell'organizzazione per controllare chi è in grado di creare gruppi. Tuttavia, è possibile annidare altri gruppi di sicurezza come membri del gruppo. Ad esempio, il gruppo denominato Consenti creazione gruppi è il gruppo di sicurezza designato e i gruppi Utenti di Microsoft Planner e Utenti di Exchange Online sono membri di questo gruppo.

Gli amministratori nei ruoli sopra elencati non devono necessariamente essere membri di questo gruppo: mantengono la possibilità di creare gruppi.

> [!IMPORTANT]
> Assicurarsi di utilizzare un **gruppo di sicurezza** per limitare gli utenti autorizzati a creare gruppi. Se si tenta di utilizzare un gruppo di Microsoft 365, i membri non saranno in grado di creare un gruppo da SharePoint perché verifica la ricerca di un gruppo di sicurezza. 
    
1. Nell'interfaccia di amministrazione, andare alla pagina **gruppi** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> .

2. Fare clic su **Aggiungi gruppo**.

3. Scegliere **sicurezza** come tipo di gruppo. Ricordare il nome del gruppo. Questo nome sarà necessario in un secondo momento.
  
4. Completare la configurazione del gruppo di sicurezza, aggiungendo persone o altri gruppi di sicurezza che si desidera siano in grado di creare gruppi nell'organizzazione.
    
Per istruzioni dettagliate, vedere [creare, modificare o eliminare un gruppo di sicurezza nell'interfaccia di amministrazione di Microsoft 365](../email/create-edit-or-delete-a-security-group.md).
 
## <a name="step-2-run-powershell-commands"></a>Passaggio 2: Eseguire i comandi di PowerShell

Per modificare l'impostazione di accesso Guest a livello di gruppo, è necessario utilizzare la versione di anteprima di [Azure Active Directory PowerShell per Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (Module Name **AzureADPreview**):

- Se non è ancora stata installata una versione del modulo PowerShell di Azure AD, vedere [installare il modulo Azure AD](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) e seguire le istruzioni per installare la versione di anteprima pubblica.

- Se è installata la versione 2.0 disponibile a livello generale del modulo PowerShell di Azure AD (AzureAD), è necessario disinstallarlo eseguendo `Uninstall-Module AzureAD` nella sessione di PowerShell e quindi installare la versione di anteprima eseguendo `Install-Module AzureADPreview`.

- Se è già stata installata la versione Preview, eseguire `Install-Module AzureADPreview` per verificare che sia la versione più recente di questo modulo.



Copiare lo script riportato di seguito in un editor di testo, ad esempio Blocco note, o [Windows PowerShell ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).

Sostituire *\<SecurityGroupName\>* con il nome del gruppo di sicurezza creato. Ad esempio:

`$GroupName = "Group Creators"`

Salvare il file come GroupCreators.ps1. 

Nella finestra di PowerShell, passare al percorso in cui è stato salvato il file (digitare "CD <FileLocation> ").

Eseguire lo script digitando:

`.\GroupCreators.ps1`

e [Accedi con l'account di amministratore](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#step-2-connect-to-azure-ad-for-your-office-365-subscription) quando richiesto.

```PowerShell
$GroupName = "<SecurityGroupName>"
$AllowGroupCreation = "False"

Connect-AzureAD

$settingsObjectID = (Get-AzureADDirectorySetting | Where-object -Property Displayname -Value "Group.Unified" -EQ).id
if(!$settingsObjectID)
{
      $template = Get-AzureADDirectorySettingTemplate | Where-object {$_.displayname -eq "group.unified"}
    $settingsCopy = $template.CreateDirectorySetting()
    New-AzureADDirectorySetting -DirectorySetting $settingsCopy
    $settingsObjectID = (Get-AzureADDirectorySetting | Where-object -Property Displayname -Value "Group.Unified" -EQ).id
}

$settingsCopy = Get-AzureADDirectorySetting -Id $settingsObjectID
$settingsCopy["EnableGroupCreation"] = $AllowGroupCreation

if($GroupName)
{
    $settingsCopy["GroupCreationAllowedGroupId"] = (Get-AzureADGroup -Filter "DisplayName eq '$GroupName'").objectId
}
 else {
$settingsCopy["GroupCreationAllowedGroupId"] = $GroupName
}
Set-AzureADDirectorySetting -Id $settingsObjectID -DirectorySetting $settingsCopy

(Get-AzureADDirectorySetting -Id $settingsObjectID).Values
```

L'ultima riga dello script visualizzerà le impostazioni aggiornate:

![This is what your settings will look like when you're done.](../../media/952cd982-5139-4080-9add-24bafca0830c.png)

Se in futuro si desidera modificare il gruppo di sicurezza utilizzato, è possibile rieseguire lo script con il nome del nuovo gruppo di sicurezza.

Se si desidera disattivare la restrizione per la creazione di un gruppo e consentire nuovamente a tutti gli utenti di creare gruppi, impostare $GroupName su "" e $AllowGroupCreation su "true" ed eseguire di nuovo lo script.
    
## <a name="step-3-verify-that-it-works"></a>Passaggio 3: Verificare il funzionamento del comando

Per rendere effettive le modifiche possono essere necessari 30 minuti o più. È possibile verificare le nuove impostazioni eseguendo le operazioni seguenti:

1. Accedere con un account utente di utenti che non devono avere la possibilità di creare gruppi. Ovvero, non sono membri del gruppo di sicurezza creato o di un amministratore.
    
2. Selezionare il riquadro **pianificatore** . 
    
3. In pianificazione selezionare **nuovo piano** nella barra di spostamento a sinistra per creare un piano. 
  
4. Si dovrebbe ottenere un messaggio che prevede che la creazione di piani e gruppi sia disattivata.

Provare di nuovo la stessa procedura con un membro del gruppo di sicurezza.

> [!NOTE]
> Se i membri del gruppo di sicurezza non sono in grado di creare gruppi, verificare che non siano bloccati tramite il [criterio cassetta postale OWA](https://go.microsoft.com/fwlink/?linkid=852135).
    
## <a name="related-articles"></a>Articoli correlati

[Guida introduttiva a PowerShell di Office 365](https://go.microsoft.com/fwlink/p/?LinkId=808033)

[Configurare la gestione dei gruppi in modalità self-service in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-self-service-management)

[Set-ExecutionPolicy](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)

[Cmdlet di Azure Active Directory per la configurazione delle impostazioni di gruppo](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
