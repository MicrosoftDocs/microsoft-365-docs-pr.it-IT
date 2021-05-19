---
title: Gestire chi può creare gruppi in Microsoft 365
f1.keywords: NOCSH
ms.author: mikeplum
ms.reviewer: arvaradh
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 4c46c8cb-17d0-44b5-9776-005fced8e618
recommendations: false
description: Informazioni su come controllare quali utenti possono creare Microsoft 365 gruppi.
ms.openlocfilehash: 19a106d255708f4b1df8f798219ea7ea778bbef3
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52539180"
---
# <a name="manage-who-can-create-microsoft-365-groups"></a>Gestire chi può creare gruppi in Microsoft 365

Per impostazione predefinita, tutti gli utenti possono creare Microsoft 365 gruppi. Questo è l'approccio consigliato perché consente agli utenti di iniziare a collaborare senza richiedere assistenza da parte dell'IT.

Se l'azienda richiede di limitare gli utenti che possono creare gruppi, è possibile limitare la creazione di un gruppo Microsoft 365 ai membri di un Microsoft 365 o di un gruppo di sicurezza specifico.

Se si è preoccupati per la creazione di team o gruppi non conformi agli standard aziendali, è consigliabile richiedere agli utenti di completare un corso di formazione e quindi aggiungerli al gruppo di utenti consentiti.

Quando si limitano gli utenti autorizzati a creare un gruppo, questo influisce su tutti i servizi che si basano sui gruppi per l'accesso, tra cui:

- Outlook
- SharePoint
- Yammer
- Microsoft Teams
- Microsoft Stream
- Planner
- Power BI (classico)
- Project per il Web / Roadmap

I passaggi descritti in questo articolo non impediscono ai membri di determinati ruoli di creare gruppi. Office 365 Gli amministratori globali possono creare gruppi tramite l'interfaccia Microsoft 365, Planner, Exchange e SharePoint Online. Altri ruoli possono creare gruppi con mezzi limitati, elencati di seguito.

- Exchange Amministratore: Exchange di amministrazione, Azure AD
- Supporto del livello partner 1: Microsoft 365 di amministrazione, Exchange di amministrazione, Azure AD
- Supporto di livello partner 2: Microsoft 365 di amministrazione, Exchange di amministrazione, Azure AD
- Writer di directory: Azure AD
- SharePoint Amministratore: SharePoint di amministrazione, Azure AD
- Teams Amministratore del servizio: Teams di amministrazione, Azure AD
- Amministratore utente: Microsoft 365 di amministrazione, Azure AD

Se si è membri di uno di questi ruoli, è possibile creare Microsoft 365 gruppi per gli utenti con restrizioni e quindi assegnare l'utente come proprietario del gruppo.

## <a name="licensing-requirements"></a>Requisiti di licenza

Per gestire chi crea i gruppi, le persone seguenti hanno bisogno di licenze di Azure AD Premium o licenze EDU di base di Azure AD assegnate:

- L'amministratore che configura queste impostazioni di creazione del gruppo
- Membri del gruppo a cui è consentito creare gruppi

> [!NOTE]
> Vedi [Assegnare o rimuovere licenze nel portale Azure Active Directory per](/azure/active-directory/fundamentals/license-users-groups) ulteriori dettagli su come assegnare licenze di Azure.

Le persone seguenti non hanno bisogno di licenze EDU di Azure AD Premium e basic EDU di Azure AD assegnate:

- Persone che sono membri Microsoft 365 gruppi e che non hanno la possibilità di creare altri gruppi.

## <a name="step-1-create-a-group-for-users-who-need-to-create-microsoft-365-groups"></a>Passaggio 1: Creare un gruppo per gli utenti che devono creare Microsoft 365 gruppi

È possibile utilizzare un solo gruppo dell'organizzazione per controllare chi è in grado di creare gruppi. Tuttavia, è possibile annidare altri gruppi come membri di questo gruppo.

Gli amministratori dei ruoli sopra elencati non devono essere membri di questo gruppo: mantengono la possibilità di creare gruppi.

1. Nell'interfaccia di amministrazione passare alla [pagina Gruppi](https://admin.microsoft.com/adminportal/home#/groups).

2. Fare clic **su Aggiungi gruppo**.

3. Scegliere il tipo di gruppo desiderato. Ricordare il nome del gruppo. Questo nome sarà necessario in un secondo momento.

4. Completare la configurazione del gruppo, aggiungere persone o altri gruppi che si desidera possano creare gruppi nell'organizzazione.

Per istruzioni dettagliate, vedere [Create, edit, or delete a security group in the Microsoft 365 admin center](../admin/email/create-edit-or-delete-a-security-group.md).

## <a name="step-2-run-powershell-commands"></a>Passaggio 2: Eseguire i comandi di PowerShell

È necessario utilizzare la versione di anteprima di [Azure Active Directory PowerShell per Graph (AzureAD) (nome](/powershell/azure/active-directory/install-adv2) modulo **AzureADPreview**) per modificare l'impostazione di accesso guest a livello di gruppo:

- Se non è ancora stata installata una versione del modulo PowerShell di Azure AD, vedere [installare il modulo Azure AD](/powershell/azure/active-directory/install-adv2?preserve-view=true&view=azureadps-2.0-preview) e seguire le istruzioni per installare la versione di anteprima pubblica.

- Se è installata la versione 2.0 disponibile a livello generale del modulo PowerShell di Azure AD (AzureAD), è necessario disinstallarlo eseguendo `Uninstall-Module AzureAD` nella sessione di PowerShell e quindi installare la versione di anteprima eseguendo `Install-Module AzureADPreview`.

- Se è già stata installata la versione Preview, eseguire `Install-Module AzureADPreview` per verificare che sia la versione più recente di questo modulo.

Copiare lo script seguente in un editor di testo, ad esempio Blocco note o il Windows PowerShell [ISE](/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).

Sostituire *\<GroupName\>* con il nome del gruppo creato. Ad esempio:

`$GroupName = "Group Creators"`

Salvare il file come GroupCreators.ps1.

Nella finestra di PowerShell passare al percorso in cui è stato salvato il file (digitare "CD <FileLocation> ").

Eseguire lo script digitando:

`.\GroupCreators.ps1`

e [accedere con l'account amministratore](../enterprise/connect-to-microsoft-365-powershell.md#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) quando richiesto.

```PowerShell
$GroupName = "<GroupName>"
$AllowGroupCreation = $False

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
  $settingsCopy["GroupCreationAllowedGroupId"] = (Get-AzureADGroup -SearchString $GroupName).objectid
}
 else {
$settingsCopy["GroupCreationAllowedGroupId"] = $GroupName
}
Set-AzureADDirectorySetting -Id $settingsObjectID -DirectorySetting $settingsCopy

(Get-AzureADDirectorySetting -Id $settingsObjectID).Values
```

L'ultima riga dello script visualizza le impostazioni aggiornate:

![Screenshot dell'output dello script di PowerShell.](../media/952cd982-5139-4080-9add-24bafca0830c.png)

Se in futuro si desidera modificare il gruppo utilizzato, è possibile eseguire di nuovo lo script con il nome del nuovo gruppo.

Se si desidera disattivare la restrizione di creazione del gruppo e consentire nuovamente a tutti gli utenti di creare gruppi, impostare $GroupName su "" e $AllowGroupCreation su "True" ed eseguire di nuovo lo script.

## <a name="step-3-verify-that-it-works"></a>Passaggio 3: Verificare il funzionamento del comando

L'applicazione delle modifiche può richiedere 30 minuti o più. È possibile verificare le nuove impostazioni eseguendo le operazioni seguenti:

1. Accedi a Microsoft 365 con un account utente di un utente che NON dovrebbe avere la possibilità di creare gruppi. Ciò significa che non sono membri del gruppo creato o di un amministratore.

2. Seleziona il **riquadro Planner.**

3. In Planner seleziona **Nuovo piano nel** riquadro di spostamento sinistro per creare un piano.

4. Dovrebbe essere visualizzato un messaggio che indica che la creazione del piano e del gruppo è disabilitata.

Ripetere la stessa procedura con un membro del gruppo.

> [!NOTE]
> Se i membri del gruppo non sono in grado di creare gruppi, verificare che non siano bloccati tramite il criterio OWA [cassetta postale](/powershell/module/exchange/set-owamailboxpolicy).

## <a name="related-topics"></a>Argomenti correlati

[Pianificazione dettagliata della governance della collaborazione](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Creare il piano di governance della collaborazione](collaboration-governance-first.md)

[Guida introduttiva a PowerShell di Office 365](../enterprise/getting-started-with-microsoft-365-powershell.md)

[Configurare la gestione dei gruppi in modalità self-service in Azure Active Directory](/azure/active-directory/users-groups-roles/groups-self-service-management)

[Set-ExecutionPolicy](/powershell/module/microsoft.powershell.security/set-executionpolicy)

[Azure Active Directory cmdlet per la configurazione delle impostazioni di gruppo](/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
