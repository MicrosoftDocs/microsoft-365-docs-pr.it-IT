---
title: Informazioni dettagliate sui dispositivi gestiti di base per dispositivi mobili e sicurezza
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: Usa Windows PowerShell per ottenere informazioni dettagliate sui dispositivi mobili e di sicurezza di base nell'organizzazione.
ms.openlocfilehash: 2edee1b08f137d3e4f977b4d6800c1b0fc0e0473
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228172"
---
# <a name="get-details-about-basic-mobility-and-security-managed-devices"></a>Informazioni dettagliate sui dispositivi gestiti di base per dispositivi mobili e sicurezza

Questo articolo illustra come usare Windows PowerShell per ottenere informazioni dettagliate sui dispositivi dell'organizzazione che hai configurato per Dispositivi mobili e sicurezza di base.

Ecco una scomposizione per i dettagli del dispositivo disponibili.

|**Dettagli**|**Cosa cercare in PowerShell**|
|:----------------|:------------------------------------------------------------------------------|
|Il dispositivo è registrato in Dispositivi mobili e sicurezza di base. Per altre info, vedi [Registrare il dispositivo mobile con Dispositivi mobili e sicurezza di base](enroll-your-mobile-device.md)|Il valore del *parametro isManaged*   è:<br/>**True**= il dispositivo è registrato.<br/>**False**= il dispositivo non è registrato. |
|Il dispositivo è conforme ai criteri di sicurezza del dispositivo. Per altre info, vedi [Creare criteri di sicurezza dei dispositivi](create-device-security-policies.md)|Il valore del *parametro isCompliant*   è:<br/>**True**   = il dispositivo è conforme ai criteri.<br/>**False**   = il dispositivo non è conforme ai criteri.|

:::image type="content" source="../../media/basic-mobility-security/bms-7-powershell-parameters.png" alt-text="Parametri di Base di PowerShell per dispositivi mobili e sicurezza":::

> [!NOTE]
> I comandi e gli script in questo articolo restituiscono inoltre informazioni dettagliate su tutti i dispositivi gestiti da [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune).

## <a name="before-you-begin"></a>Prima di iniziare

È necessario configurare alcuni elementi per eseguire i comandi e gli script descritti in questo articolo.

### <a name="step-1-download-and-install-the-azure-active-directory-module-for-windows-powershell"></a>Passaggio 1: Scaricare e installare il modulo Azure Active Directory per Windows PowerShell

Per altre info su questi passaggi, [vedi Connessione per Microsoft 365 con PowerShell.](/office365/enterprise/powershell/connect-to-office-365-powershell)

1. Vai a [Microsoft Online Services Sign-In Assistant for IT Professionals RTWl](https://download.microsoft.com/download/7/1/E/71EF1D05-A42C-4A1F-8162-96494B5E615C/msoidcli_32bit.msi)e seleziona Download per Microsoft Online Services Assistente per    **l'accesso**.

2. Installare il Modulo di Microsoft Azure Active Directory per Windows PowerShell con la procedura seguente:

    1. Aprire un prompt dei comandi di PowerShell a livello di amministratore.

    2. Eseguire il comando `Install-Module MSOnline`.

    3. Se viene richiesto di installare il provider NuGet, digitare Y e premere INVIO.

    4. Se viene richiesto di installare il modulo da PSGallery, digitare Y e premere INVIO.

    5. Dopo l'installazione, chiudere la finestra di comando di PowerShell.

### <a name="step-2-connect-to-your-microsoft-365-subscription"></a>Passaggio 2: Connessione'abbonamento Microsoft 365

1. Nel modulo Windows Azure Active Directory per Windows PowerShell, eseguire il comando seguente.

   ```powershell
   $UserCredential = Get-Credential
   ```

2. Nella finestra Windows PowerShell richiesta credenziali digitare il nome utente e la password per l'account Microsoft 365 amministratore globale e quindi selezionare **OK.**

3. Esegui il comando seguente:

   ```powershell
   Connect-MsolService -Credential $UserCredential
   ```

### <a name="step-3-make-sure-youre-able-to-run-powershell-scripts"></a>Passaggio 3: verificare di essere in grado di eseguire script di PowerShell

> [!NOTE]
> È possibile ignorare questo passaggio se si è già configurato per l'esecuzione di script di PowerShell.

Per eseguire lo script Get-MsolUserDeviceComplianceStatus.ps1, è necessario abilitare l'esecuzione degli script di PowerShell.

1. Dal desktop Windows, selezionare **Start** e quindi digitare Windows PowerShell. Fare clic con il Windows PowerShell e quindi scegliere **Esegui come amministratore.**

2. Esegui il comando seguente:

   ```powershell
   Set-ExecutionPolicy  RemoteSigned
   ```

3. Quando richiesto, digitare Y e quindi premere INVIO.

#### <a name="run-the-get-msoldevice-cmdlet-to-display-details-for-all-devices-in-your-organization"></a>Eseguire il cmdlet Get-MsolDevice per visualizzare i dettagli per tutti i dispositivi dell'organizzazione

1. Aprire il modulo Microsoft Azure Active Directory per Windows PowerShell.

2. Esegui il comando seguente:

   ```powershell
   Get-MsolDevice -All -ReturnRegisteredOwners | Where-Object {$_.RegisteredOwners.Count -gt 0}
   ```

Per altri esempi, vedi  [Get-MsolDevice.](https://go.microsoft.com/fwlink/?linkid=2157939)

## <a name="run-a-script-to-get-device-details"></a>Eseguire uno script per ottenere i dettagli del dispositivo

Salvare innanzitutto lo script nel computer.

1. Copiare e incollare il testo seguente Blocco note.

   ```powershell
   param (
   [PSObject[]]$users = @(),
   [Switch]$export,
   [String]$exportFileName = "UserDeviceComplianceStatus_" + (Get-Date -Format "yyMMdd_HHMMss") + ".csv",
   [String]$exportPath = [Environment]::GetFolderPath("Desktop")
   )
   [System.Collections.IDictionary]$script:schema = @{
   DeviceId = ''
   DeviceOSType = ''
   DeviceOSVersion = ''
   DeviceTrustLevel = ''
   DisplayName = ''
   IsCompliant = ''
   IsManaged = ''
   ApproximateLastLogonTimestamp = ''
   DeviceObjectId = ''
   RegisteredOwnerUpn = ''
   RegisteredOwnerObjectId = ''
   RegisteredOwnerDisplayName = ''
   }
   function createResultObject
   {
   [PSObject]$resultObject = New-Object -TypeName PSObject -Property $script:schema
   return $resultObject
   }
   If ($users.Count -eq 0)
   {
   $users = Get-MsolUser
   }
   [PSObject[]]$result = foreach ($u in $users)
   {
   [PSObject]$devices = get-msoldevice -RegisteredOwnerUpn $u.UserPrincipalName
   foreach ($d in $devices)
   {
   [PSObject]$deviceResult = createResultObject
   $deviceResult.DeviceId = $d.DeviceId
   $deviceResult.DeviceOSType = $d.DeviceOSType
   $deviceResult.DeviceOSVersion = $d.DeviceOSVersion
   $deviceResult.DeviceTrustLevel = $d.DeviceTrustLevel
   $deviceResult.DisplayName = $d.DisplayName
   $deviceResult.IsCompliant = $d.GraphDeviceObject.IsCompliant
   $deviceResult.IsManaged = $d.GraphDeviceObject.IsManaged
   $deviceResult.DeviceObjectId = $d.ObjectId
   $deviceResult.RegisteredOwnerUpn = $u.UserPrincipalName
   $deviceResult.RegisteredOwnerObjectId = $u.ObjectId
   $deviceResult.RegisteredOwnerDisplayName = $u.DisplayName
   $deviceResult.ApproximateLastLogonTimestamp = $d.ApproximateLastLogonTimestamp
   $deviceResult
   }
   }
   If ($export)
   {
   $result | Export-Csv -path ($exportPath + "\" + $exportFileName) -NoTypeInformation
   }
   Else
   {
   $result
   }
   ```

2. Salvarlo come file Windows PowerShell script utilizzando l'estensione .ps1; ad esempio, Get-MsolUserDeviceComplianceStatus.ps1.

## <a name="run-the-script-to-get-device-information-for-a-single-user-account"></a>Eseguire lo script per ottenere informazioni sul dispositivo per un singolo account utente

1. Aprire il modulo Microsoft Azure Active Directory per Windows PowerShell.

2. Passare alla cartella in cui è stato salvato lo script. Ad esempio, se è stato salvato in C:\PS-Scripts, eseguire il comando seguente.

   ```powershell
   cd C:\PS-Scripts
   ```

3. Eseguire il comando seguente per identificare l'utente per cui si desidera ottenere i dettagli del dispositivo. In questo esempio vengono fornite informazioni dettagliate bar@example.com.

   ```powershell
   $u = Get-MsolUser -UserPrincipalName bar@example.com
   ```

4. Eseguire il comando seguente per avviare lo script.

   ```powershell
   .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export
   ```

Le informazioni vengono esportate nel Windows Desktop come file CSV. È possibile utilizzare parametri aggiuntivi per specificare il nome file e il percorso del file CSV.

## <a name="run-the-script-to-get-device-information-for-a-group-of-users"></a>Eseguire lo script per ottenere informazioni sul dispositivo per un gruppo di utenti

1. Aprire il modulo Microsoft Azure Active Directory per Windows PowerShell.

2. Passare alla cartella in cui è stato salvato lo script. Ad esempio, se è stato salvato in C:\PS-Scripts, eseguire il comando seguente.

   ```powershell
   cd C:\PS-Scripts
   ```

3. Esegui il comando seguente per identificare il gruppo per cui vuoi ottenere i dettagli del dispositivo. In questo esempio vengono recuperate informazioni dettagliate per gli utenti del gruppo FinanceStaff.

   ```powershell
   $u = Get-MsolGroupMember -SearchString "FinanceStaff" | % { Get-MsolUser -ObjectId $_.ObjectId }
   ```

4. Eseguire il comando seguente per avviare lo script.

   ```powershell
   .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export
   ```

Le informazioni vengono esportate nel Windows Desktop come file CSV. È possibile utilizzare parametri aggiuntivi per specificare il nome file e il percorso del file CSV.

## <a name="related-topics"></a>Argomenti correlati

[Microsoft Connessione è stato ritirato](/collaborate/connect-redirect)

[Panoramica Basic Mobility + Security](overview.md)

[Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=2157939)
