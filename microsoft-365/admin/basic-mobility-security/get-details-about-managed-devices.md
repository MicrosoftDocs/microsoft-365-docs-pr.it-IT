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
# <a name="get-details-about-basic-mobility-and-security-managed-devices"></a><span data-ttu-id="432dc-103">Informazioni dettagliate sui dispositivi gestiti di base per dispositivi mobili e sicurezza</span><span class="sxs-lookup"><span data-stu-id="432dc-103">Get details about Basic Mobility and Security managed devices</span></span>

<span data-ttu-id="432dc-104">Questo articolo illustra come usare Windows PowerShell per ottenere informazioni dettagliate sui dispositivi dell'organizzazione che hai configurato per Dispositivi mobili e sicurezza di base.</span><span class="sxs-lookup"><span data-stu-id="432dc-104">This article shows you how to use Windows PowerShell to get details about the devices in your organization that you set up for Basic Mobility and Security.</span></span>

<span data-ttu-id="432dc-105">Ecco una scomposizione per i dettagli del dispositivo disponibili.</span><span class="sxs-lookup"><span data-stu-id="432dc-105">Here's a breakdown for the device details available to you.</span></span>

|<span data-ttu-id="432dc-106">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="432dc-106">**Detail**</span></span>|<span data-ttu-id="432dc-107">**Cosa cercare in PowerShell**</span><span class="sxs-lookup"><span data-stu-id="432dc-107">**What to look for in PowerShell**</span></span>|
|:----------------|:------------------------------------------------------------------------------|
|<span data-ttu-id="432dc-108">Il dispositivo è registrato in Dispositivi mobili e sicurezza di base.</span><span class="sxs-lookup"><span data-stu-id="432dc-108">Device is enrolled in Basic Mobility and Security.</span></span> <span data-ttu-id="432dc-109">Per altre info, vedi [Registrare il dispositivo mobile con Dispositivi mobili e sicurezza di base](enroll-your-mobile-device.md)</span><span class="sxs-lookup"><span data-stu-id="432dc-109">For more info, see [Enroll your mobile device using Basic Mobility and Security](enroll-your-mobile-device.md)</span></span>|<span data-ttu-id="432dc-110">Il valore del *parametro isManaged*   è:</span><span class="sxs-lookup"><span data-stu-id="432dc-110">The value of the *isManaged* parameter is:</span></span><br/><span data-ttu-id="432dc-111">**True**= il dispositivo è registrato.</span><span class="sxs-lookup"><span data-stu-id="432dc-111">**True**= device is enrolled.</span></span><br/><span data-ttu-id="432dc-112">**False**= il dispositivo non è registrato.</span><span class="sxs-lookup"><span data-stu-id="432dc-112">**False**= device is not enrolled.</span></span> |
|<span data-ttu-id="432dc-113">Il dispositivo è conforme ai criteri di sicurezza del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="432dc-113">Device is compliant with your device security policies.</span></span> <span data-ttu-id="432dc-114">Per altre info, vedi [Creare criteri di sicurezza dei dispositivi](create-device-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="432dc-114">For more info, see [Create device security policies](create-device-security-policies.md)</span></span>|<span data-ttu-id="432dc-115">Il valore del *parametro isCompliant*   è:</span><span class="sxs-lookup"><span data-stu-id="432dc-115">The value of the *isCompliant* parameter is:</span></span><br/><span data-ttu-id="432dc-116">**True**   = il dispositivo è conforme ai criteri.</span><span class="sxs-lookup"><span data-stu-id="432dc-116">**True** = device is compliant with policies.</span></span><br/><span data-ttu-id="432dc-117">**False**   = il dispositivo non è conforme ai criteri.</span><span class="sxs-lookup"><span data-stu-id="432dc-117">**False** = device is not compliant with policies.</span></span>|

:::image type="content" source="../../media/basic-mobility-security/bms-7-powershell-parameters.png" alt-text="Parametri di Base di PowerShell per dispositivi mobili e sicurezza":::

> [!NOTE]
> <span data-ttu-id="432dc-119">I comandi e gli script in questo articolo restituiscono inoltre informazioni dettagliate su tutti i dispositivi gestiti da [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune).</span><span class="sxs-lookup"><span data-stu-id="432dc-119">The commands and scripts in this article also return details about any devices managed by [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="432dc-120">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="432dc-120">Before you begin</span></span>

<span data-ttu-id="432dc-121">È necessario configurare alcuni elementi per eseguire i comandi e gli script descritti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="432dc-121">There are a few things you need to set up to run the commands and scripts described in this article.</span></span>

### <a name="step-1-download-and-install-the-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="432dc-122">Passaggio 1: Scaricare e installare il modulo Azure Active Directory per Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="432dc-122">Step 1: Download and install the Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="432dc-123">Per altre info su questi passaggi, [vedi Connessione per Microsoft 365 con PowerShell.](/office365/enterprise/powershell/connect-to-office-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="432dc-123">For more info on these steps, see [Connect to Microsoft 365 with PowerShell](/office365/enterprise/powershell/connect-to-office-365-powershell).</span></span>

1. <span data-ttu-id="432dc-124">Vai a [Microsoft Online Services Sign-In Assistant for IT Professionals RTWl](https://download.microsoft.com/download/7/1/E/71EF1D05-A42C-4A1F-8162-96494B5E615C/msoidcli_32bit.msi)e seleziona Download per Microsoft Online Services Assistente per    **l'accesso**.</span><span class="sxs-lookup"><span data-stu-id="432dc-124">Go to [Microsoft Online Services Sign-In Assistant for IT Professionals RTWl](https://download.microsoft.com/download/7/1/E/71EF1D05-A42C-4A1F-8162-96494B5E615C/msoidcli_32bit.msi) and select  **Download for Microsoft Online Services Sign-in Assistant**.</span></span>

2. <span data-ttu-id="432dc-125">Installare il Modulo di Microsoft Azure Active Directory per Windows PowerShell con la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="432dc-125">Install the Microsoft Azure Active Directory Module for Windows PowerShell with these steps:</span></span>

    1. <span data-ttu-id="432dc-126">Aprire un prompt dei comandi di PowerShell a livello di amministratore.</span><span class="sxs-lookup"><span data-stu-id="432dc-126">Open an administrator-level PowerShell command prompt.</span></span>

    2. <span data-ttu-id="432dc-127">Eseguire il comando `Install-Module MSOnline`.</span><span class="sxs-lookup"><span data-stu-id="432dc-127">Run the `Install-Module MSOnline` command.</span></span>

    3. <span data-ttu-id="432dc-128">Se viene richiesto di installare il provider NuGet, digitare Y e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="432dc-128">If prompted to install the NuGet provider, type Y and press ENTER.</span></span>

    4. <span data-ttu-id="432dc-129">Se viene richiesto di installare il modulo da PSGallery, digitare Y e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="432dc-129">If prompted to install the module from PSGallery, type Y and press ENTER.</span></span>

    5. <span data-ttu-id="432dc-130">Dopo l'installazione, chiudere la finestra di comando di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="432dc-130">After installation, close the PowerShell command window.</span></span>

### <a name="step-2-connect-to-your-microsoft-365-subscription"></a><span data-ttu-id="432dc-131">Passaggio 2: Connessione'abbonamento Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="432dc-131">Step 2: Connect to your Microsoft 365 subscription</span></span>

1. <span data-ttu-id="432dc-132">Nel modulo Windows Azure Active Directory per Windows PowerShell, eseguire il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="432dc-132">In the Windows Azure Active Directory Module for Windows PowerShell, run the following command.</span></span>

   ```powershell
   $UserCredential = Get-Credential
   ```

2. <span data-ttu-id="432dc-133">Nella finestra Windows PowerShell richiesta credenziali digitare il nome utente e la password per l'account Microsoft 365 amministratore globale e quindi selezionare **OK.**</span><span class="sxs-lookup"><span data-stu-id="432dc-133">In the Windows PowerShell Credential Request dialog box, type the user name and password for your Microsoft 365 global admin account, and then select **OK**.</span></span>

3. <span data-ttu-id="432dc-134">Esegui il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="432dc-134">Run the following command.</span></span>

   ```powershell
   Connect-MsolService -Credential $UserCredential
   ```

### <a name="step-3-make-sure-youre-able-to-run-powershell-scripts"></a><span data-ttu-id="432dc-135">Passaggio 3: verificare di essere in grado di eseguire script di PowerShell</span><span class="sxs-lookup"><span data-stu-id="432dc-135">Step 3: Make sure you’re able to run PowerShell scripts</span></span>

> [!NOTE]
> <span data-ttu-id="432dc-136">È possibile ignorare questo passaggio se si è già configurato per l'esecuzione di script di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="432dc-136">You can skip this step if you’re already set up to run PowerShell scripts.</span></span>

<span data-ttu-id="432dc-137">Per eseguire lo script Get-MsolUserDeviceComplianceStatus.ps1, è necessario abilitare l'esecuzione degli script di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="432dc-137">To run the Get-MsolUserDeviceComplianceStatus.ps1 script, you need to enable the running of PowerShell scripts.</span></span>

1. <span data-ttu-id="432dc-138">Dal desktop Windows, selezionare **Start** e quindi digitare Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="432dc-138">From your Windows Desktop, select **Start**, and then type Windows PowerShell.</span></span> <span data-ttu-id="432dc-139">Fare clic con il Windows PowerShell e quindi scegliere **Esegui come amministratore.**</span><span class="sxs-lookup"><span data-stu-id="432dc-139">Right-click Windows PowerShell, and then select **Run as administrator**.</span></span>

2. <span data-ttu-id="432dc-140">Esegui il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="432dc-140">Run the following command.</span></span>

   ```powershell
   Set-ExecutionPolicy  RemoteSigned
   ```

3. <span data-ttu-id="432dc-141">Quando richiesto, digitare Y e quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="432dc-141">When prompted, type Y and then press Enter.</span></span>

#### <a name="run-the-get-msoldevice-cmdlet-to-display-details-for-all-devices-in-your-organization"></a><span data-ttu-id="432dc-142">Eseguire il cmdlet Get-MsolDevice per visualizzare i dettagli per tutti i dispositivi dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="432dc-142">Run the Get-MsolDevice cmdlet to display details for all devices in your organization</span></span>

1. <span data-ttu-id="432dc-143">Aprire il modulo Microsoft Azure Active Directory per Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="432dc-143">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>

2. <span data-ttu-id="432dc-144">Esegui il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="432dc-144">Run the following command.</span></span>

   ```powershell
   Get-MsolDevice -All -ReturnRegisteredOwners | Where-Object {$_.RegisteredOwners.Count -gt 0}
   ```

<span data-ttu-id="432dc-145">Per altri esempi, vedi  [Get-MsolDevice.](https://go.microsoft.com/fwlink/?linkid=2157939)</span><span class="sxs-lookup"><span data-stu-id="432dc-145">For more examples, see  [Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=2157939).</span></span>

## <a name="run-a-script-to-get-device-details"></a><span data-ttu-id="432dc-146">Eseguire uno script per ottenere i dettagli del dispositivo</span><span class="sxs-lookup"><span data-stu-id="432dc-146">Run a script to get device details</span></span>

<span data-ttu-id="432dc-147">Salvare innanzitutto lo script nel computer.</span><span class="sxs-lookup"><span data-stu-id="432dc-147">First, save the script to your computer.</span></span>

1. <span data-ttu-id="432dc-148">Copiare e incollare il testo seguente Blocco note.</span><span class="sxs-lookup"><span data-stu-id="432dc-148">Copy and paste the following text into Notepad.</span></span>

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

2. <span data-ttu-id="432dc-149">Salvarlo come file Windows PowerShell script utilizzando l'estensione .ps1; ad esempio, Get-MsolUserDeviceComplianceStatus.ps1.</span><span class="sxs-lookup"><span data-stu-id="432dc-149">Save it as a Windows PowerShell script file by using the file extension .ps1; for example, Get-MsolUserDeviceComplianceStatus.ps1.</span></span>

## <a name="run-the-script-to-get-device-information-for-a-single-user-account"></a><span data-ttu-id="432dc-150">Eseguire lo script per ottenere informazioni sul dispositivo per un singolo account utente</span><span class="sxs-lookup"><span data-stu-id="432dc-150">Run the script to get device information for a single user account</span></span>

1. <span data-ttu-id="432dc-151">Aprire il modulo Microsoft Azure Active Directory per Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="432dc-151">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>

2. <span data-ttu-id="432dc-152">Passare alla cartella in cui è stato salvato lo script.</span><span class="sxs-lookup"><span data-stu-id="432dc-152">Go to the folder where you saved the script.</span></span> <span data-ttu-id="432dc-153">Ad esempio, se è stato salvato in C:\PS-Scripts, eseguire il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="432dc-153">For example, if you saved it to C:\PS-Scripts, run the following command.</span></span>

   ```powershell
   cd C:\PS-Scripts
   ```

3. <span data-ttu-id="432dc-154">Eseguire il comando seguente per identificare l'utente per cui si desidera ottenere i dettagli del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="432dc-154">Run the following command to identify the user you want to get device details for.</span></span> <span data-ttu-id="432dc-155">In questo esempio vengono fornite informazioni dettagliate bar@example.com.</span><span class="sxs-lookup"><span data-stu-id="432dc-155">This example gets details for bar@example.com.</span></span>

   ```powershell
   $u = Get-MsolUser -UserPrincipalName bar@example.com
   ```

4. <span data-ttu-id="432dc-156">Eseguire il comando seguente per avviare lo script.</span><span class="sxs-lookup"><span data-stu-id="432dc-156">Run the following command to initiate the script.</span></span>

   ```powershell
   .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export
   ```

<span data-ttu-id="432dc-157">Le informazioni vengono esportate nel Windows Desktop come file CSV.</span><span class="sxs-lookup"><span data-stu-id="432dc-157">The information is exported to your Windows Desktop as a CSV file.</span></span> <span data-ttu-id="432dc-158">È possibile utilizzare parametri aggiuntivi per specificare il nome file e il percorso del file CSV.</span><span class="sxs-lookup"><span data-stu-id="432dc-158">You can use additional parameters to specify the file name and path of the CSV.</span></span>

## <a name="run-the-script-to-get-device-information-for-a-group-of-users"></a><span data-ttu-id="432dc-159">Eseguire lo script per ottenere informazioni sul dispositivo per un gruppo di utenti</span><span class="sxs-lookup"><span data-stu-id="432dc-159">Run the script to get device information for a group of users</span></span>

1. <span data-ttu-id="432dc-160">Aprire il modulo Microsoft Azure Active Directory per Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="432dc-160">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>

2. <span data-ttu-id="432dc-161">Passare alla cartella in cui è stato salvato lo script.</span><span class="sxs-lookup"><span data-stu-id="432dc-161">Go to the folder where you saved the script.</span></span> <span data-ttu-id="432dc-162">Ad esempio, se è stato salvato in C:\PS-Scripts, eseguire il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="432dc-162">For example, if you saved it to C:\PS-Scripts, run the following command.</span></span>

   ```powershell
   cd C:\PS-Scripts
   ```

3. <span data-ttu-id="432dc-163">Esegui il comando seguente per identificare il gruppo per cui vuoi ottenere i dettagli del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="432dc-163">Run the following command to identify the group you want to get device details for.</span></span> <span data-ttu-id="432dc-164">In questo esempio vengono recuperate informazioni dettagliate per gli utenti del gruppo FinanceStaff.</span><span class="sxs-lookup"><span data-stu-id="432dc-164">This example gets details for users in the FinanceStaff group.</span></span>

   ```powershell
   $u = Get-MsolGroupMember -SearchString "FinanceStaff" | % { Get-MsolUser -ObjectId $_.ObjectId }
   ```

4. <span data-ttu-id="432dc-165">Eseguire il comando seguente per avviare lo script.</span><span class="sxs-lookup"><span data-stu-id="432dc-165">Run the following command to initiate the script.</span></span>

   ```powershell
   .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export
   ```

<span data-ttu-id="432dc-166">Le informazioni vengono esportate nel Windows Desktop come file CSV.</span><span class="sxs-lookup"><span data-stu-id="432dc-166">The information is exported to your Windows Desktop as a CSV file.</span></span> <span data-ttu-id="432dc-167">È possibile utilizzare parametri aggiuntivi per specificare il nome file e il percorso del file CSV.</span><span class="sxs-lookup"><span data-stu-id="432dc-167">You can use additional parameters to specify the file name and path of the CSV.</span></span>

## <a name="related-topics"></a><span data-ttu-id="432dc-168">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="432dc-168">Related topics</span></span>

[<span data-ttu-id="432dc-169">Microsoft Connessione è stato ritirato</span><span class="sxs-lookup"><span data-stu-id="432dc-169">Microsoft Connect Has Been Retired</span></span>](/collaborate/connect-redirect)

[<span data-ttu-id="432dc-170">Panoramica Basic Mobility + Security</span><span class="sxs-lookup"><span data-stu-id="432dc-170">Overview of Basic Mobility and Security</span></span>](overview.md)

[<span data-ttu-id="432dc-171">Get-MsolDevice</span><span class="sxs-lookup"><span data-stu-id="432dc-171">Get-MsolDevice</span></span>](https://go.microsoft.com/fwlink/?linkid=2157939)
