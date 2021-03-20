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
ms.openlocfilehash: 92fcd6f39ffff97d7a4ecd2a69626ece54b481b2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904253"
---
# <a name="get-details-about-basic-mobility-and-security-managed-devices"></a><span data-ttu-id="4d765-103">Informazioni dettagliate sui dispositivi gestiti di base per dispositivi mobili e sicurezza</span><span class="sxs-lookup"><span data-stu-id="4d765-103">Get details about Basic Mobility and Security managed devices</span></span>

<span data-ttu-id="4d765-104">Questo articolo illustra come usare Windows PowerShell per ottenere informazioni dettagliate sui dispositivi dell'organizzazione che hai configurato per Dispositivi mobili e sicurezza di base.</span><span class="sxs-lookup"><span data-stu-id="4d765-104">This article shows you how to use Windows PowerShell to get details about the devices in your organization that you set up for Basic Mobility and Security.</span></span>

<span data-ttu-id="4d765-105">Ecco una scomposizione per i dettagli del dispositivo disponibili.</span><span class="sxs-lookup"><span data-stu-id="4d765-105">Here's a breakdown for the device details available to you.</span></span>

|<span data-ttu-id="4d765-106">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="4d765-106">**Detail**</span></span>|<span data-ttu-id="4d765-107">**Cosa cercare in PowerShell**</span><span class="sxs-lookup"><span data-stu-id="4d765-107">**What to look for in PowerShell**</span></span>|
|:----------------|:------------------------------------------------------------------------------|
|<span data-ttu-id="4d765-108">Il dispositivo è registrato in Dispositivi mobili e sicurezza di base.</span><span class="sxs-lookup"><span data-stu-id="4d765-108">Device is enrolled in Basic Mobility and Security.</span></span> <span data-ttu-id="4d765-109">Per altre info, vedi [Registrare il dispositivo mobile con Dispositivi mobili e sicurezza di base](enroll-your-mobile-device.md)</span><span class="sxs-lookup"><span data-stu-id="4d765-109">For more info, see [Enroll your mobile device using Basic Mobility and Security](enroll-your-mobile-device.md)</span></span>|<span data-ttu-id="4d765-110">Il valore del *parametro isManaged*   è:</span><span class="sxs-lookup"><span data-stu-id="4d765-110">The value of the *isManaged* parameter is:</span></span><br/><span data-ttu-id="4d765-111">**True**= il dispositivo è registrato.</span><span class="sxs-lookup"><span data-stu-id="4d765-111">**True**= device is enrolled.</span></span><br/><span data-ttu-id="4d765-112">**False**= il dispositivo non è registrato.</span><span class="sxs-lookup"><span data-stu-id="4d765-112">**False**= device is not enrolled.</span></span> |
|<span data-ttu-id="4d765-113">Il dispositivo è conforme ai criteri di sicurezza del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4d765-113">Device is compliant with your device security policies.</span></span> <span data-ttu-id="4d765-114">Per altre info, vedi [Creare criteri di sicurezza dei dispositivi](create-device-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="4d765-114">For more info, see [Create device security policies](create-device-security-policies.md)</span></span>|<span data-ttu-id="4d765-115">Il valore del *parametro isCompliant*   è:</span><span class="sxs-lookup"><span data-stu-id="4d765-115">The value of the *isCompliant* parameter is:</span></span><br/><span data-ttu-id="4d765-116">**True**   = il dispositivo è conforme ai criteri.</span><span class="sxs-lookup"><span data-stu-id="4d765-116">**True** = device is compliant with policies.</span></span><br/><span data-ttu-id="4d765-117">**False**   = il dispositivo non è conforme ai criteri.</span><span class="sxs-lookup"><span data-stu-id="4d765-117">**False** = device is not compliant with policies.</span></span>|

:::image type="content" source="../../media/basic-mobility-security/bms-7-powershell-parameters.png" alt-text="Parametri di Base di PowerShell per dispositivi mobili e sicurezza":::

>[!NOTE]
><span data-ttu-id="4d765-119">I comandi e gli script in questo articolo restituiscono inoltre informazioni dettagliate sui dispositivi gestiti da [Microsoft Intune.](https://www.microsoft.com/cloud-platform/microsoft-intune)</span><span class="sxs-lookup"><span data-stu-id="4d765-119">The commands and scripts in this article also return details about any devices managed by [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="4d765-120">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="4d765-120">Before you begin</span></span>

<span data-ttu-id="4d765-121">È necessario configurare alcuni elementi per eseguire i comandi e gli script descritti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="4d765-121">There are a few things you need to set up to run the commands and scripts described in this article.</span></span>

### <a name="step-1-download-and-install-the-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="4d765-122">Passaggio 1: Scaricare e installare il modulo di Azure Active Directory per Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4d765-122">Step 1: Download and install the Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="4d765-123">Per altre info su questi passaggi, vedi [Connettersi a Microsoft 365 con PowerShell.](/office365/enterprise/powershell/connect-to-office-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="4d765-123">For more info on these steps, see [Connect to Microsoft 365 with PowerShell](/office365/enterprise/powershell/connect-to-office-365-powershell).</span></span>

1. <span data-ttu-id="4d765-124">Vai a [Microsoft Online Services Sign-In Assistant for IT Professionals RTWl](https://www.microsoft.com/download/details.aspx?id=41950)e seleziona Download per Microsoft Online Services Assistente per    **l'accesso**.</span><span class="sxs-lookup"><span data-stu-id="4d765-124">Go to [Microsoft Online Services Sign-In Assistant for IT Professionals RTWl](https://www.microsoft.com/download/details.aspx?id=41950) and select  **Download for Microsoft Online Services Sign-in Assistant**.</span></span>

2. <span data-ttu-id="4d765-125">Installare il Modulo di Microsoft Azure Active Directory per Windows PowerShell con la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="4d765-125">Install the Microsoft Azure Active Directory Module for Windows PowerShell with these steps:</span></span>

    1. <span data-ttu-id="4d765-126">Aprire un prompt dei comandi di PowerShell a livello di amministratore.</span><span class="sxs-lookup"><span data-stu-id="4d765-126">Open an administrator-level PowerShell command prompt.</span></span>  

    2. <span data-ttu-id="4d765-127">Eseguire il comando Install-Module MSOnline.</span><span class="sxs-lookup"><span data-stu-id="4d765-127">Run the Install-Module MSOnline command.</span></span>

    3. <span data-ttu-id="4d765-128">Se viene richiesto di installare il provider NuGet, digitare Y e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="4d765-128">If prompted to install the NuGet provider, type Y and press ENTER.</span></span>

    4. <span data-ttu-id="4d765-129">Se viene richiesto di installare il modulo da PSGallery, digitare Y e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="4d765-129">If prompted to install the module from PSGallery, type Y and press ENTER.</span></span>

    5. <span data-ttu-id="4d765-130">Dopo l'installazione, chiudere la finestra di comando di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4d765-130">After installation, close the PowerShell command window.</span></span>

### <a name="step-2-connect-to-your-microsoft-365-subscription"></a><span data-ttu-id="4d765-131">Passaggio 2: connettersi all'abbonamento a Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4d765-131">Step 2: Connect to your Microsoft 365 subscription</span></span>

1. <span data-ttu-id="4d765-132">Nel modulo Windows Azure Active Directory per Windows PowerShell, eseguire il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="4d765-132">In the Windows Azure Active Directory Module for Windows PowerShell, run the following command.</span></span>  

    <span data-ttu-id="4d765-133">$UserCredential = Get-Credential</span><span class="sxs-lookup"><span data-stu-id="4d765-133">$UserCredential = Get-Credential</span></span>

2. <span data-ttu-id="4d765-134">Nella finestra Windows PowerShell richiesta credenziali digitare il nome utente e la password per l'account di amministratore globale di Microsoft 365 e quindi selezionare **OK.**</span><span class="sxs-lookup"><span data-stu-id="4d765-134">In the Windows PowerShell Credential Request dialog box, type the user name and password for your Microsoft 365 global admin account, and then select **OK**.</span></span>

3. <span data-ttu-id="4d765-135">Eseguire il comando riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="4d765-135">Run the following command.</span></span>

    <span data-ttu-id="4d765-136">Connect-MsolService -Credential $UserCredential</span><span class="sxs-lookup"><span data-stu-id="4d765-136">Connect-MsolService -Credential $UserCredential</span></span>

### <a name="step-3-make-sure-youre-able-to-run-powershell-scripts"></a><span data-ttu-id="4d765-137">Passaggio 3: verificare di essere in grado di eseguire script di PowerShell</span><span class="sxs-lookup"><span data-stu-id="4d765-137">Step 3: Make sure you’re able to run PowerShell scripts</span></span>

>[!NOTE]
><span data-ttu-id="4d765-138">È possibile ignorare questo passaggio se si è già configurato per l'esecuzione di script di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4d765-138">You can skip this step if you’re already set up to run PowerShell scripts.</span></span>

<span data-ttu-id="4d765-139">Per eseguire lo script Get-MsolUserDeviceComplianceStatus.ps1, è necessario abilitare l'esecuzione degli script di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4d765-139">To run the Get-MsolUserDeviceComplianceStatus.ps1 script, you need to enable the running of PowerShell scripts.</span></span>

1. <span data-ttu-id="4d765-140">Da Desktop di Windows seleziona **Start** e quindi digita Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4d765-140">From your Windows Desktop, select **Start**, and then type Windows PowerShell.</span></span> <span data-ttu-id="4d765-141">Fare clic con il Windows PowerShell e quindi scegliere **Esegui come amministratore.**</span><span class="sxs-lookup"><span data-stu-id="4d765-141">Right-click Windows PowerShell, and then select **Run as administrator**.</span></span>

2. <span data-ttu-id="4d765-142">Eseguire il comando riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="4d765-142">Run the following command.</span></span>

    <span data-ttu-id="4d765-143">Set-ExecutionPolicy RemoteSigned</span><span class="sxs-lookup"><span data-stu-id="4d765-143">Set-ExecutionPolicy  RemoteSigned</span></span>

3. <span data-ttu-id="4d765-144">Quando richiesto, digitare Y e quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="4d765-144">When prompted, type Y and then press Enter.</span></span>

<span data-ttu-id="4d765-145">**Eseguire il cmdlet Get-MsolDevice per visualizzare i dettagli per tutti i dispositivi dell'organizzazione**</span><span class="sxs-lookup"><span data-stu-id="4d765-145">**Run the Get-MsolDevice cmdlet to display details for all devices in your organization**</span></span>

1. <span data-ttu-id="4d765-146">Aprire il modulo Microsoft Azure Active Directory per Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4d765-146">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>  

2. <span data-ttu-id="4d765-147">Eseguire il comando riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="4d765-147">Run the following command.</span></span>

    <span data-ttu-id="4d765-148">Get-MsolDevice -All -ReturnRegisteredOwners | Where-Object {$_. RegisteredOwners.Count -gt 0}</span><span class="sxs-lookup"><span data-stu-id="4d765-148">Get-MsolDevice -All -ReturnRegisteredOwners | Where-Object {$_.RegisteredOwners.Count -gt 0}</span></span>

<span data-ttu-id="4d765-149">Per altri esempi, vedi  [Get-MsolDevice.](https://go.microsoft.com/fwlink/?linkid=2157939)</span><span class="sxs-lookup"><span data-stu-id="4d765-149">For more examples, see  [Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=2157939).</span></span>

## <a name="run-a-script-to-get-device-details"></a><span data-ttu-id="4d765-150">Eseguire uno script per ottenere i dettagli del dispositivo</span><span class="sxs-lookup"><span data-stu-id="4d765-150">Run a script to get device details</span></span>

<span data-ttu-id="4d765-151">Salvare innanzitutto lo script nel computer.</span><span class="sxs-lookup"><span data-stu-id="4d765-151">First, save the script to your computer.</span></span>

1. <span data-ttu-id="4d765-152">Copiare e incollare il testo seguente nel Blocco note.</span><span class="sxs-lookup"><span data-stu-id="4d765-152">Copy and paste the following text into Notepad.</span></span>  

2.  <span data-ttu-id="4d765-153">param (</span><span class="sxs-lookup"><span data-stu-id="4d765-153">param (</span></span>

3.  <span data-ttu-id="4d765-154">[PSObject[]]$users = @(),</span><span class="sxs-lookup"><span data-stu-id="4d765-154">[PSObject[]]$users = @(),</span></span>

4.  <span data-ttu-id="4d765-155">[Switch]$export,</span><span class="sxs-lookup"><span data-stu-id="4d765-155">[Switch]$export,</span></span>

5.  <span data-ttu-id="4d765-156">[String]$exportFileName = "UserDeviceComplianceStatus_" + (Get-Date -Format "yyMMdd_HHMMss") + ".csv",</span><span class="sxs-lookup"><span data-stu-id="4d765-156">[String]$exportFileName = "UserDeviceComplianceStatus_" + (Get-Date -Format "yyMMdd_HHMMss") + ".csv",</span></span>

6.  <span data-ttu-id="4d765-157">[String]$exportPath = [Environment]::GetFolderPath("Desktop")</span><span class="sxs-lookup"><span data-stu-id="4d765-157">[String]$exportPath = [Environment]::GetFolderPath("Desktop")</span></span>

7.  <span data-ttu-id="4d765-158">)</span><span class="sxs-lookup"><span data-stu-id="4d765-158">)</span></span>

9.  <span data-ttu-id="4d765-159">[System.Collections.IDictionary]$script:schema = @{</span><span class="sxs-lookup"><span data-stu-id="4d765-159">[System.Collections.IDictionary]$script:schema = @{</span></span>

11.  <span data-ttu-id="4d765-160">DeviceId = ''</span><span class="sxs-lookup"><span data-stu-id="4d765-160">DeviceId = ''</span></span>

12.  <span data-ttu-id="4d765-161">DeviceOSType = ''</span><span class="sxs-lookup"><span data-stu-id="4d765-161">DeviceOSType = ''</span></span>

13.  <span data-ttu-id="4d765-162">DeviceOSVersion = ''</span><span class="sxs-lookup"><span data-stu-id="4d765-162">DeviceOSVersion = ''</span></span>

14.  <span data-ttu-id="4d765-163">DeviceTrustLevel = ''</span><span class="sxs-lookup"><span data-stu-id="4d765-163">DeviceTrustLevel = ''</span></span>

15.  <span data-ttu-id="4d765-164">DisplayName = ''</span><span class="sxs-lookup"><span data-stu-id="4d765-164">DisplayName = ''</span></span>

16.  <span data-ttu-id="4d765-165">IsCompliant = ''</span><span class="sxs-lookup"><span data-stu-id="4d765-165">IsCompliant = ''</span></span>

17.  <span data-ttu-id="4d765-166">IsManaged = ''</span><span class="sxs-lookup"><span data-stu-id="4d765-166">IsManaged = ''</span></span>

18.  <span data-ttu-id="4d765-167">ApproximateLastLogonTimestamp = ''</span><span class="sxs-lookup"><span data-stu-id="4d765-167">ApproximateLastLogonTimestamp = ''</span></span>

19.  <span data-ttu-id="4d765-168">DeviceObjectId = ''</span><span class="sxs-lookup"><span data-stu-id="4d765-168">DeviceObjectId = ''</span></span>

20.  <span data-ttu-id="4d765-169">RegisteredOwnerUpn = ''</span><span class="sxs-lookup"><span data-stu-id="4d765-169">RegisteredOwnerUpn = ''</span></span>

21.  <span data-ttu-id="4d765-170">RegisteredOwnerObjectId = ''</span><span class="sxs-lookup"><span data-stu-id="4d765-170">RegisteredOwnerObjectId = ''</span></span>
    

22.  <span data-ttu-id="4d765-171">RegisteredOwnerDisplayName = ''</span><span class="sxs-lookup"><span data-stu-id="4d765-171">RegisteredOwnerDisplayName = ''</span></span>
    

23.  <span data-ttu-id="4d765-172">}</span><span class="sxs-lookup"><span data-stu-id="4d765-172">}</span></span>
    

25.  <span data-ttu-id="4d765-173">funzione createResultObject</span><span class="sxs-lookup"><span data-stu-id="4d765-173">function createResultObject</span></span>
    

26.  <span data-ttu-id="4d765-174">{</span><span class="sxs-lookup"><span data-stu-id="4d765-174">{</span></span>
    

28.  <span data-ttu-id="4d765-175">[PSObject]$resultObject = New-Object -TypeName PSObject -Property $script:schema</span><span class="sxs-lookup"><span data-stu-id="4d765-175">[PSObject]$resultObject = New-Object -TypeName PSObject -Property $script:schema</span></span>
    

30.  <span data-ttu-id="4d765-176">return $resultObject</span><span class="sxs-lookup"><span data-stu-id="4d765-176">return $resultObject</span></span>
    

31.  <span data-ttu-id="4d765-177">}</span><span class="sxs-lookup"><span data-stu-id="4d765-177">}</span></span>
    

33.  <span data-ttu-id="4d765-178">Se ($users. Count -eq 0)</span><span class="sxs-lookup"><span data-stu-id="4d765-178">If ($users.Count -eq 0)</span></span>
    

34.  <span data-ttu-id="4d765-179">{</span><span class="sxs-lookup"><span data-stu-id="4d765-179">{</span></span>
    

35.  <span data-ttu-id="4d765-180">$users = Get-MsolUser</span><span class="sxs-lookup"><span data-stu-id="4d765-180">$users = Get-MsolUser</span></span>
    

36.  <span data-ttu-id="4d765-181">}</span><span class="sxs-lookup"><span data-stu-id="4d765-181">}</span></span>
    

38.  <span data-ttu-id="4d765-182">[PSObject[]]$result = foreach ($u in $users)</span><span class="sxs-lookup"><span data-stu-id="4d765-182">[PSObject[]]$result = foreach ($u in $users)</span></span>
    

39.  <span data-ttu-id="4d765-183">{</span><span class="sxs-lookup"><span data-stu-id="4d765-183">{</span></span>
    

41.  <span data-ttu-id="4d765-184">[PSObject]$devices = get-msoldevice -RegisteredOwnerUpn $u.UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="4d765-184">[PSObject]$devices = get-msoldevice -RegisteredOwnerUpn $u.UserPrincipalName</span></span>
    

42.  <span data-ttu-id="4d765-185">foreach ($d in $devices)</span><span class="sxs-lookup"><span data-stu-id="4d765-185">foreach ($d in $devices)</span></span>
    

43.  <span data-ttu-id="4d765-186">{</span><span class="sxs-lookup"><span data-stu-id="4d765-186">{</span></span>
    

44.  <span data-ttu-id="4d765-187">[PSObject]$deviceResult = createResultObject</span><span class="sxs-lookup"><span data-stu-id="4d765-187">[PSObject]$deviceResult = createResultObject</span></span>
    

45.  <span data-ttu-id="4d765-188">$deviceResult.DeviceId = $d.DeviceId</span><span class="sxs-lookup"><span data-stu-id="4d765-188">$deviceResult.DeviceId = $d.DeviceId</span></span>
    

46.  <span data-ttu-id="4d765-189">$deviceResult.DeviceOSType = $d.DeviceOSType</span><span class="sxs-lookup"><span data-stu-id="4d765-189">$deviceResult.DeviceOSType = $d.DeviceOSType</span></span>
    

47.  <span data-ttu-id="4d765-190">$deviceResult.DeviceOSVersion = $d.DeviceOSVersion</span><span class="sxs-lookup"><span data-stu-id="4d765-190">$deviceResult.DeviceOSVersion = $d.DeviceOSVersion</span></span>
    

48.  <span data-ttu-id="4d765-191">$deviceResult.DeviceTrustLevel = $d.DeviceTrustLevel</span><span class="sxs-lookup"><span data-stu-id="4d765-191">$deviceResult.DeviceTrustLevel = $d.DeviceTrustLevel</span></span>
    

49.  <span data-ttu-id="4d765-192">$deviceResult.DisplayName = $d.DisplayName</span><span class="sxs-lookup"><span data-stu-id="4d765-192">$deviceResult.DisplayName = $d.DisplayName</span></span>
    

50.  <span data-ttu-id="4d765-193">$deviceResult.IsCompliant = $d.GraphDeviceObject.IsCompliant</span><span class="sxs-lookup"><span data-stu-id="4d765-193">$deviceResult.IsCompliant = $d.GraphDeviceObject.IsCompliant</span></span>
    

51.  <span data-ttu-id="4d765-194">$deviceResult.IsManaged = $d.GraphDeviceObject.IsManaged</span><span class="sxs-lookup"><span data-stu-id="4d765-194">$deviceResult.IsManaged = $d.GraphDeviceObject.IsManaged</span></span>
    

52.  <span data-ttu-id="4d765-195">$deviceResult.DeviceObjectId = $d.ObjectId</span><span class="sxs-lookup"><span data-stu-id="4d765-195">$deviceResult.DeviceObjectId = $d.ObjectId</span></span>
    

53.  <span data-ttu-id="4d765-196">$deviceResult.RegisteredOwnerUpn = $u.UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="4d765-196">$deviceResult.RegisteredOwnerUpn = $u.UserPrincipalName</span></span>
    

54.  <span data-ttu-id="4d765-197">$deviceResult.RegisteredOwnerObjectId = $u.ObjectId</span><span class="sxs-lookup"><span data-stu-id="4d765-197">$deviceResult.RegisteredOwnerObjectId = $u.ObjectId</span></span>
    

55.  <span data-ttu-id="4d765-198">$deviceResult.RegisteredOwnerDisplayName = $u.DisplayName</span><span class="sxs-lookup"><span data-stu-id="4d765-198">$deviceResult.RegisteredOwnerDisplayName = $u.DisplayName</span></span>
    

56.  <span data-ttu-id="4d765-199">$deviceResult.ApproximateLastLogonTimestamp = $d.ApproximateLastLogonTimestamp</span><span class="sxs-lookup"><span data-stu-id="4d765-199">$deviceResult.ApproximateLastLogonTimestamp = $d.ApproximateLastLogonTimestamp</span></span>
    

58.  <span data-ttu-id="4d765-200">$deviceResult</span><span class="sxs-lookup"><span data-stu-id="4d765-200">$deviceResult</span></span>
    

59.  <span data-ttu-id="4d765-201">}</span><span class="sxs-lookup"><span data-stu-id="4d765-201">}</span></span>
    

61.  <span data-ttu-id="4d765-202">}</span><span class="sxs-lookup"><span data-stu-id="4d765-202">}</span></span>
    

63.  <span data-ttu-id="4d765-203">If ($export)</span><span class="sxs-lookup"><span data-stu-id="4d765-203">If ($export)</span></span>
    

64.  <span data-ttu-id="4d765-204">{</span><span class="sxs-lookup"><span data-stu-id="4d765-204">{</span></span>
    

65.  <span data-ttu-id="4d765-205">$result | Export-Csv -path ($exportPath + " \" + $exportFileName) -NoTypeInformation</span><span class="sxs-lookup"><span data-stu-id="4d765-205">$result | Export-Csv -path ($exportPath + "\" + $exportFileName) -NoTypeInformation</span></span>
    

66.  <span data-ttu-id="4d765-206">}</span><span class="sxs-lookup"><span data-stu-id="4d765-206">}</span></span>
    

67.  <span data-ttu-id="4d765-207">Else</span><span class="sxs-lookup"><span data-stu-id="4d765-207">Else</span></span>
    

68.  <span data-ttu-id="4d765-208">{</span><span class="sxs-lookup"><span data-stu-id="4d765-208">{</span></span>
    

69.  <span data-ttu-id="4d765-209">$result</span><span class="sxs-lookup"><span data-stu-id="4d765-209">$result</span></span>
    

70.  <span data-ttu-id="4d765-210">}</span><span class="sxs-lookup"><span data-stu-id="4d765-210">}</span></span>
    

71.  <span data-ttu-id="4d765-211">Salvarlo come file Windows PowerShell script utilizzando l'estensione ps1; ad esempio, Get-MsolUserDeviceComplianceStatus.ps1.</span><span class="sxs-lookup"><span data-stu-id="4d765-211">Save it as a Windows PowerShell script file by using the file extension .ps1; for example, Get-MsolUserDeviceComplianceStatus.ps1.</span></span>   

## <a name="run-the-script-to-get-device-information-for-a-single-user-account"></a><span data-ttu-id="4d765-212">Eseguire lo script per ottenere informazioni sul dispositivo per un singolo account utente</span><span class="sxs-lookup"><span data-stu-id="4d765-212">Run the script to get device information for a single user account</span></span>

1. <span data-ttu-id="4d765-213">Aprire il modulo Microsoft Azure Active Directory per Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4d765-213">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>
    
2. <span data-ttu-id="4d765-214">Passare alla cartella in cui è stato salvato lo script.</span><span class="sxs-lookup"><span data-stu-id="4d765-214">Go to the folder where you saved the script.</span></span> <span data-ttu-id="4d765-215">Ad esempio, se è stato salvato in C:\PS-Scripts, eseguire il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="4d765-215">For example, if you saved it to C:\PS-Scripts, run the following command.</span></span>
    
    <span data-ttu-id="4d765-216">cd C:\PS-Scripts</span><span class="sxs-lookup"><span data-stu-id="4d765-216">cd C:\PS-Scripts</span></span>

3. <span data-ttu-id="4d765-217">Eseguire il comando seguente per identificare l'utente per cui si desidera ottenere i dettagli del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4d765-217">Run the following command to identify the user you want to get device details for.</span></span> <span data-ttu-id="4d765-218">In questo esempio vengono fornite informazioni dettagliate bar@example.com.</span><span class="sxs-lookup"><span data-stu-id="4d765-218">This example gets details for bar@example.com.</span></span>
    
    <span data-ttu-id="4d765-219">$u = Get-MsolUser -UserPrincipalName bar@example.com</span><span class="sxs-lookup"><span data-stu-id="4d765-219">$u = Get-MsolUser -UserPrincipalName bar@example.com</span></span>

4. <span data-ttu-id="4d765-220">Eseguire il comando seguente per avviare lo script.</span><span class="sxs-lookup"><span data-stu-id="4d765-220">Run the following command to initiate the script.</span></span>

    <span data-ttu-id="4d765-221">.\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export</span><span class="sxs-lookup"><span data-stu-id="4d765-221">.\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export</span></span>

<span data-ttu-id="4d765-222">Le informazioni vengono esportate nel desktop di Windows come file CSV.</span><span class="sxs-lookup"><span data-stu-id="4d765-222">The information is exported to your Windows Desktop as a CSV file.</span></span> <span data-ttu-id="4d765-223">È possibile utilizzare parametri aggiuntivi per specificare il nome file e il percorso del file CSV.</span><span class="sxs-lookup"><span data-stu-id="4d765-223">You can use additional parameters to specify the file name and path of the CSV.</span></span>

## <a name="run-the-script-to-get-device-information-for-a-group-of-users"></a><span data-ttu-id="4d765-224">Eseguire lo script per ottenere informazioni sul dispositivo per un gruppo di utenti</span><span class="sxs-lookup"><span data-stu-id="4d765-224">Run the script to get device information for a group of users</span></span>

1. <span data-ttu-id="4d765-225">Aprire il modulo Microsoft Azure Active Directory per Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4d765-225">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>
    
2. <span data-ttu-id="4d765-226">Passare alla cartella in cui è stato salvato lo script.</span><span class="sxs-lookup"><span data-stu-id="4d765-226">Go to the folder where you saved the script.</span></span> <span data-ttu-id="4d765-227">Ad esempio, se è stato salvato in C:\PS-Scripts, eseguire il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="4d765-227">For example, if you saved it to C:\PS-Scripts, run the following command.</span></span>   

    <span data-ttu-id="4d765-228">cd C:\PS-Scripts</span><span class="sxs-lookup"><span data-stu-id="4d765-228">cd C:\PS-Scripts</span></span>

3. <span data-ttu-id="4d765-229">Esegui il comando seguente per identificare il gruppo per cui vuoi ottenere i dettagli del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4d765-229">Run the following command to identify the group you want to get device details for.</span></span> <span data-ttu-id="4d765-230">In questo esempio vengono recuperate informazioni dettagliate per gli utenti del gruppo FinanceStaff.</span><span class="sxs-lookup"><span data-stu-id="4d765-230">This example gets details for users in the FinanceStaff group.</span></span> 

    <span data-ttu-id="4d765-231">$u = Get-MsolGroupMember -SearchString "FinanceStaff" | % { Get-MsolUser -ObjectId $_. ObjectId }</span><span class="sxs-lookup"><span data-stu-id="4d765-231">$u = Get-MsolGroupMember -SearchString "FinanceStaff" | % { Get-MsolUser -ObjectId $_.ObjectId }</span></span>

4. <span data-ttu-id="4d765-232">Eseguire il comando seguente per avviare lo script.</span><span class="sxs-lookup"><span data-stu-id="4d765-232">Run the following command to initiate the script.</span></span>

    <span data-ttu-id="4d765-233">.\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export</span><span class="sxs-lookup"><span data-stu-id="4d765-233">.\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export</span></span>

<span data-ttu-id="4d765-234">Le informazioni vengono esportate nel desktop di Windows come file CSV.</span><span class="sxs-lookup"><span data-stu-id="4d765-234">The information is exported to your Windows Desktop as a CSV file.</span></span> <span data-ttu-id="4d765-235">È possibile utilizzare parametri aggiuntivi per specificare il nome file e il percorso del file CSV.</span><span class="sxs-lookup"><span data-stu-id="4d765-235">You can use additional parameters to specify the file name and path of the CSV.</span></span>

## <a name="related-topics"></a><span data-ttu-id="4d765-236">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="4d765-236">Related topics</span></span>

[<span data-ttu-id="4d765-237">Microsoft Connect è stato ritirato</span><span class="sxs-lookup"><span data-stu-id="4d765-237">Microsoft Connect Has Been Retired</span></span>](/collaborate/connect-redirect)

[<span data-ttu-id="4d765-238">Panoramica Basic Mobility + Security</span><span class="sxs-lookup"><span data-stu-id="4d765-238">Overview of Basic Mobility and Security</span></span>](overview.md)

[<span data-ttu-id="4d765-239">Get-MsolDevice</span><span class="sxs-lookup"><span data-stu-id="4d765-239">Get-MsolDevice</span></span>](https://go.microsoft.com/fwlink/?linkid=2157939)