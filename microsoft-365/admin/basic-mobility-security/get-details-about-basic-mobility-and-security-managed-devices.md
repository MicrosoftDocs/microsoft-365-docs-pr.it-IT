---
title: Ottenere informazioni dettagliate sui dispositivi gestiti di sicurezza e mobilità di base
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
description: Utilizzare Windows PowerShell per ottenere informazioni dettagliate sui dispositivi mobili e di sicurezza di base nell'organizzazione.
ms.openlocfilehash: 7b041e54d512291163616d3b61973cef989cec5c
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2020
ms.locfileid: "47336927"
---
# <a name="get-details-about-basic-mobility-and-security-managed-devices"></a><span data-ttu-id="270d6-103">Ottenere informazioni dettagliate sui dispositivi gestiti di sicurezza e mobilità di base</span><span class="sxs-lookup"><span data-stu-id="270d6-103">Get details about Basic Mobility and Security managed devices</span></span>

<span data-ttu-id="270d6-104">In questo articolo viene illustrato come utilizzare Windows PowerShell per ottenere informazioni dettagliate sui dispositivi dell'organizzazione che sono stati configurati per la sicurezza e la mobilità di base.</span><span class="sxs-lookup"><span data-stu-id="270d6-104">This article shows you how to use Windows PowerShell to get details about the devices in your organization that you set up for Basic Mobility and Security.</span></span>

<span data-ttu-id="270d6-105">Di seguito viene illustrata una ripartizione per i dettagli del dispositivo disponibili.</span><span class="sxs-lookup"><span data-stu-id="270d6-105">Here's a breakdown for the device details available to you.</span></span>

|<span data-ttu-id="270d6-106">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="270d6-106">**Detail**</span></span>|<span data-ttu-id="270d6-107">**Cosa cercare in PowerShell**</span><span class="sxs-lookup"><span data-stu-id="270d6-107">**What to look for in PowerShell**</span></span>|
|:----------------|:------------------------------------------------------------------------------|
|<span data-ttu-id="270d6-108">Il dispositivo è registrato in mobilità e sicurezza di base.</span><span class="sxs-lookup"><span data-stu-id="270d6-108">Device is enrolled in Basic Mobility and Security.</span></span> <span data-ttu-id="270d6-109">Per altre informazioni, vedere [registrazione del dispositivo mobile tramite la sicurezza e la mobilità di base](enroll-your-mobile-device-using-basic-mobility-and-security.md)</span><span class="sxs-lookup"><span data-stu-id="270d6-109">For more info, see [Enroll your mobile device using Basic Mobility and Security](enroll-your-mobile-device-using-basic-mobility-and-security.md)</span></span>|<span data-ttu-id="270d6-110">Il valore del parametro *Managed*   è:</span><span class="sxs-lookup"><span data-stu-id="270d6-110">The value of the *isManaged* parameter is:</span></span><br/><span data-ttu-id="270d6-111">**True**= il dispositivo è registrato.</span><span class="sxs-lookup"><span data-stu-id="270d6-111">**True**= device is enrolled.</span></span><br/><span data-ttu-id="270d6-112">**False**= il dispositivo non è registrato.</span><span class="sxs-lookup"><span data-stu-id="270d6-112">**False**= device is not enrolled.</span></span> |
|<span data-ttu-id="270d6-113">Il dispositivo è conforme ai criteri di sicurezza del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="270d6-113">Device is compliant with your device security policies.</span></span> <span data-ttu-id="270d6-114">Per altre informazioni, vedere [creare criteri di sicurezza dei dispositivi](create-device-security-policies-in-basic-mmobility-and-security.md)</span><span class="sxs-lookup"><span data-stu-id="270d6-114">For more info, see [Create device security policies](create-device-security-policies-in-basic-mmobility-and-security.md)</span></span>|<span data-ttu-id="270d6-115">Il valore del parametro *isCompliant*   è:</span><span class="sxs-lookup"><span data-stu-id="270d6-115">The value of the *isCompliant* parameter is:</span></span><br/><span data-ttu-id="270d6-116">**Vero**   = il dispositivo è conforme ai criteri.</span><span class="sxs-lookup"><span data-stu-id="270d6-116">**True** = device is compliant with policies.</span></span><br/><span data-ttu-id="270d6-117">Valore **false**   = il dispositivo non è conforme ai criteri.</span><span class="sxs-lookup"><span data-stu-id="270d6-117">**False** = device is not compliant with policies.</span></span>|

:::image type="content" source="../../media/basic-mobility-security/bms-7-powershell-parameters.png" alt-text="Parametri di base per la mobilità e la sicurezza di PowerShell":::

>[!NOTE]
><span data-ttu-id="270d6-119">I comandi e gli script di questo articolo restituiscono anche informazioni dettagliate su tutti i dispositivi gestiti da [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune).</span><span class="sxs-lookup"><span data-stu-id="270d6-119">The commands and scripts in this article also return details about any devices managed by [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="270d6-120">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="270d6-120">Before you begin</span></span>

<span data-ttu-id="270d6-121">Per eseguire i comandi e gli script descritti in questo articolo, è necessario impostare alcuni aspetti.</span><span class="sxs-lookup"><span data-stu-id="270d6-121">There are a few things you need to set up to run the commands and scripts described in this article.</span></span>

### <a name="step-1-download-and-install-the-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="270d6-122">Passaggio 1: scaricare e installare il modulo di Azure Active Directory per Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="270d6-122">Step 1: Download and install the Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="270d6-123">Per altre informazioni su questi passaggi, vedere [Connect to Microsoft 365 with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="270d6-123">For more info on these steps, see [Connect to Microsoft 365 with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell).</span></span>

1. <span data-ttu-id="270d6-124">Accedere a [Assistente per l'accesso ai Microsoft Online Services per professionisti IT RTWl](https://www.microsoft.com/download/details.aspx?id=41950)   e selezionare  **download per l'assistente per l'accesso ai Microsoft Online Services**.</span><span class="sxs-lookup"><span data-stu-id="270d6-124">Go to [Microsoft Online Services Sign-In Assistant for IT Professionals RTWl](https://www.microsoft.com/download/details.aspx?id=41950) and select  **Download for Microsoft Online Services Sign-in Assistant**.</span></span>   

2. <span data-ttu-id="270d6-125">Installare il Modulo di Microsoft Azure Active Directory per Windows PowerShell con la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="270d6-125">Install the Microsoft Azure Active Directory Module for Windows PowerShell with these steps:</span></span>   

    1. <span data-ttu-id="270d6-126">Aprire un prompt di comandi di PowerShell a livello di amministratore.</span><span class="sxs-lookup"><span data-stu-id="270d6-126">Open an administrator-level PowerShell command prompt.</span></span>  

    2. <span data-ttu-id="270d6-127">Eseguire il comando Install-Module MSOnline.</span><span class="sxs-lookup"><span data-stu-id="270d6-127">Run the Install-Module MSOnline command.</span></span>
    
    3. <span data-ttu-id="270d6-128">Se viene richiesto di installare il provider NuGet, digitare Y e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="270d6-128">If prompted to install the NuGet provider, type Y and press ENTER.</span></span>   

    4. <span data-ttu-id="270d6-129">Se viene richiesto di installare il modulo da PSGallery, digitare Y e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="270d6-129">If prompted to install the module from PSGallery, type Y and press ENTER.</span></span>   

    5. <span data-ttu-id="270d6-130">Dopo l'installazione, chiudere la finestra di comando di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="270d6-130">After installation, close the PowerShell command window.</span></span>
    
### <a name="step-2-connect-to-your-microsoft-365-subscription"></a><span data-ttu-id="270d6-131">Passaggio 2: connettersi alla sottoscrizione Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="270d6-131">Step 2: Connect to your Microsoft 365 subscription</span></span>

1. <span data-ttu-id="270d6-132">Nel modulo Windows Azure Active Directory per Windows PowerShell, eseguire il comando riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="270d6-132">In the Windows Azure Active Directory Module for Windows PowerShell, run the following command.</span></span>  

    <span data-ttu-id="270d6-133">$UserCredential = Get-Credential</span><span class="sxs-lookup"><span data-stu-id="270d6-133">$UserCredential = Get-Credential</span></span>

2. <span data-ttu-id="270d6-134">Nella finestra di dialogo richiesta credenziali di Windows PowerShell, digitare il nome utente e la password per l'account di amministratore globale di Microsoft 365, quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="270d6-134">In the Windows PowerShell Credential Request dialog box, type the user name and password for your Microsoft 365 global admin account, and then select **OK**.</span></span>
    
3. <span data-ttu-id="270d6-135">Eseguire il comando riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="270d6-135">Run the following command.</span></span>
    
    <span data-ttu-id="270d6-136">Connect-MsolService-Credential $UserCredential</span><span class="sxs-lookup"><span data-stu-id="270d6-136">Connect-MsolService -Credential $UserCredential</span></span>

### <a name="step-3-make-sure-youre-able-to-run-powershell-scripts"></a><span data-ttu-id="270d6-137">Passaggio 3: verificare di essere in grado di eseguire gli script di PowerShell</span><span class="sxs-lookup"><span data-stu-id="270d6-137">Step 3: Make sure you’re able to run PowerShell scripts</span></span>

>[!NOTE]
><span data-ttu-id="270d6-138">È possibile ignorare questo passaggio se si è già configurati per l'esecuzione di script di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="270d6-138">You can skip this step if you’re already set up to run PowerShell scripts.</span></span>

<span data-ttu-id="270d6-139">Per eseguire lo script Get-MsolUserDeviceComplianceStatus.ps1, è necessario abilitare l'esecuzione degli script di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="270d6-139">To run the Get-MsolUserDeviceComplianceStatus.ps1 script, you need to enable the running of PowerShell scripts.</span></span>

1. <span data-ttu-id="270d6-140">Dal desktop di Windows, selezionare **Avvia**e quindi digitare Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="270d6-140">From your Windows Desktop, select **Start**, and then type Windows PowerShell.</span></span> <span data-ttu-id="270d6-141">Fare clic con il pulsante destro del mouse su Windows PowerShell e quindi scegliere **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="270d6-141">Right-click Windows PowerShell, and then select **Run as administrator**.</span></span>

2. <span data-ttu-id="270d6-142">Eseguire il comando riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="270d6-142">Run the following command.</span></span>
    
    <span data-ttu-id="270d6-143">Set-ExecutionPolicy RemoteSigned</span><span class="sxs-lookup"><span data-stu-id="270d6-143">Set-ExecutionPolicy  RemoteSigned</span></span>

3. <span data-ttu-id="270d6-144">Quando richiesto, digitare Y e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="270d6-144">When prompted, type Y and then press Enter.</span></span>
    
<span data-ttu-id="270d6-145">**Eseguire il cmdlet Get-MsolDevice per visualizzare i dettagli di tutti i dispositivi nell'organizzazione**</span><span class="sxs-lookup"><span data-stu-id="270d6-145">**Run the Get-MsolDevice cmdlet to display details for all devices in your organization**</span></span>

1. <span data-ttu-id="270d6-146">Aprire il modulo Microsoft Azure Active Directory per Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="270d6-146">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>  

2. <span data-ttu-id="270d6-147">Eseguire il comando riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="270d6-147">Run the following command.</span></span>
    
    <span data-ttu-id="270d6-148">Get-MsolDevice-all-ReturnRegisteredOwners | Where-Object {$ _. RegisteredOwners. Count-gt 0}</span><span class="sxs-lookup"><span data-stu-id="270d6-148">Get-MsolDevice -All -ReturnRegisteredOwners | Where-Object {$_.RegisteredOwners.Count -gt 0}</span></span>

<span data-ttu-id="270d6-149">Per ulteriori esempi, vedere  [Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=841721).</span><span class="sxs-lookup"><span data-stu-id="270d6-149">For more examples, see  [Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=841721).</span></span>

## <a name="run-a-script-to-get-device-details"></a><span data-ttu-id="270d6-150">Eseguire uno script per ottenere i dettagli del dispositivo</span><span class="sxs-lookup"><span data-stu-id="270d6-150">Run a script to get device details</span></span>

<span data-ttu-id="270d6-151">In primo luogo, salvare lo script nel computer.</span><span class="sxs-lookup"><span data-stu-id="270d6-151">First, save the script to your computer.</span></span>

1. <span data-ttu-id="270d6-152">Copiare e incollare il testo seguente nel blocco note.</span><span class="sxs-lookup"><span data-stu-id="270d6-152">Copy and paste the following text into Notepad.</span></span>  

2.  <span data-ttu-id="270d6-153">param</span><span class="sxs-lookup"><span data-stu-id="270d6-153">param (</span></span>
    

3.  <span data-ttu-id="270d6-154">[PSObject []] $users = @ (),</span><span class="sxs-lookup"><span data-stu-id="270d6-154">[PSObject[]]$users = @(),</span></span>
    

4.  <span data-ttu-id="270d6-155">[Switch] $export,</span><span class="sxs-lookup"><span data-stu-id="270d6-155">[Switch]$export,</span></span>
    

5.  <span data-ttu-id="270d6-156">[String] $exportFileName = "UserDeviceComplianceStatus_" + (Get-Date-Format "yyMMdd_HHMMss") + ". csv",</span><span class="sxs-lookup"><span data-stu-id="270d6-156">[String]$exportFileName = "UserDeviceComplianceStatus_" + (Get-Date -Format "yyMMdd_HHMMss") + ".csv",</span></span>
    

6.  <span data-ttu-id="270d6-157">[String] $exportPath = [Environment]:: GetFolderPath ("desktop")</span><span class="sxs-lookup"><span data-stu-id="270d6-157">[String]$exportPath = [Environment]::GetFolderPath("Desktop")</span></span>
    

7.  <span data-ttu-id="270d6-158">)</span><span class="sxs-lookup"><span data-stu-id="270d6-158">)</span></span>
    

9.  <span data-ttu-id="270d6-159">[System. Collections. IDictionary] $script: schema = @ {</span><span class="sxs-lookup"><span data-stu-id="270d6-159">[System.Collections.IDictionary]$script:schema = @{</span></span>
    

11.  <span data-ttu-id="270d6-160">DeviceId =''</span><span class="sxs-lookup"><span data-stu-id="270d6-160">DeviceId = ''</span></span>
    

12.  <span data-ttu-id="270d6-161">DeviceOSType =''</span><span class="sxs-lookup"><span data-stu-id="270d6-161">DeviceOSType = ''</span></span>
    

13.  <span data-ttu-id="270d6-162">DeviceOSVersion =''</span><span class="sxs-lookup"><span data-stu-id="270d6-162">DeviceOSVersion = ''</span></span>
    

14.  <span data-ttu-id="270d6-163">DeviceTrustLevel =''</span><span class="sxs-lookup"><span data-stu-id="270d6-163">DeviceTrustLevel = ''</span></span>
    

15.  <span data-ttu-id="270d6-164">DisplayName =''</span><span class="sxs-lookup"><span data-stu-id="270d6-164">DisplayName = ''</span></span>
    

16.  <span data-ttu-id="270d6-165">IsCompliant =''</span><span class="sxs-lookup"><span data-stu-id="270d6-165">IsCompliant = ''</span></span>
    

17.  <span data-ttu-id="270d6-166">Managed =''</span><span class="sxs-lookup"><span data-stu-id="270d6-166">IsManaged = ''</span></span>
    

18.  <span data-ttu-id="270d6-167">ApproximateLastLogonTimestamp =''</span><span class="sxs-lookup"><span data-stu-id="270d6-167">ApproximateLastLogonTimestamp = ''</span></span>
    

19.  <span data-ttu-id="270d6-168">DeviceObjectId =''</span><span class="sxs-lookup"><span data-stu-id="270d6-168">DeviceObjectId = ''</span></span>
    

20.  <span data-ttu-id="270d6-169">RegisteredOwnerUpn =''</span><span class="sxs-lookup"><span data-stu-id="270d6-169">RegisteredOwnerUpn = ''</span></span>
    

21.  <span data-ttu-id="270d6-170">RegisteredOwnerObjectId =''</span><span class="sxs-lookup"><span data-stu-id="270d6-170">RegisteredOwnerObjectId = ''</span></span>
    

22.  <span data-ttu-id="270d6-171">RegisteredOwnerDisplayName =''</span><span class="sxs-lookup"><span data-stu-id="270d6-171">RegisteredOwnerDisplayName = ''</span></span>
    

23.  <span data-ttu-id="270d6-172">}</span><span class="sxs-lookup"><span data-stu-id="270d6-172">}</span></span>
    

25.  <span data-ttu-id="270d6-173">funzione createResultObject</span><span class="sxs-lookup"><span data-stu-id="270d6-173">function createResultObject</span></span>
    

26.  <span data-ttu-id="270d6-174">{</span><span class="sxs-lookup"><span data-stu-id="270d6-174">{</span></span>
    

28.  <span data-ttu-id="270d6-175">[PSObject] $resultObject = New-Object-TypeName PSObject-Property $script: schema</span><span class="sxs-lookup"><span data-stu-id="270d6-175">[PSObject]$resultObject = New-Object -TypeName PSObject -Property $script:schema</span></span>
    

30.  <span data-ttu-id="270d6-176">$resultObject di ritorno</span><span class="sxs-lookup"><span data-stu-id="270d6-176">return $resultObject</span></span>
    

31.  <span data-ttu-id="270d6-177">}</span><span class="sxs-lookup"><span data-stu-id="270d6-177">}</span></span>
    

33.  <span data-ttu-id="270d6-178">Se ($users. Count-EQ 0)</span><span class="sxs-lookup"><span data-stu-id="270d6-178">If ($users.Count -eq 0)</span></span>
    

34.  <span data-ttu-id="270d6-179">{</span><span class="sxs-lookup"><span data-stu-id="270d6-179">{</span></span>
    

35.  <span data-ttu-id="270d6-180">$users = Get-MsolUser</span><span class="sxs-lookup"><span data-stu-id="270d6-180">$users = Get-MsolUser</span></span>
    

36.  <span data-ttu-id="270d6-181">}</span><span class="sxs-lookup"><span data-stu-id="270d6-181">}</span></span>
    

38.  <span data-ttu-id="270d6-182">[PSObject []] $result = foreach ($u in $users)</span><span class="sxs-lookup"><span data-stu-id="270d6-182">[PSObject[]]$result = foreach ($u in $users)</span></span>
    

39.  <span data-ttu-id="270d6-183">{</span><span class="sxs-lookup"><span data-stu-id="270d6-183">{</span></span>
    

41.  <span data-ttu-id="270d6-184">[PSObject] $devices = Get-msoldevice-RegisteredOwnerUpn $u. UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="270d6-184">[PSObject]$devices = get-msoldevice -RegisteredOwnerUpn $u.UserPrincipalName</span></span>
    

42.  <span data-ttu-id="270d6-185">foreach ($d in $devices)</span><span class="sxs-lookup"><span data-stu-id="270d6-185">foreach ($d in $devices)</span></span>
    

43.  <span data-ttu-id="270d6-186">{</span><span class="sxs-lookup"><span data-stu-id="270d6-186">{</span></span>
    

44.  <span data-ttu-id="270d6-187">[PSObject] $deviceResult = createResultObject</span><span class="sxs-lookup"><span data-stu-id="270d6-187">[PSObject]$deviceResult = createResultObject</span></span>
    

45.  <span data-ttu-id="270d6-188">$deviceResult. DeviceId = $d. DeviceId</span><span class="sxs-lookup"><span data-stu-id="270d6-188">$deviceResult.DeviceId = $d.DeviceId</span></span>
    

46.  <span data-ttu-id="270d6-189">$deviceResult. DeviceOSType = $d. DeviceOSType</span><span class="sxs-lookup"><span data-stu-id="270d6-189">$deviceResult.DeviceOSType = $d.DeviceOSType</span></span>
    

47.  <span data-ttu-id="270d6-190">$deviceResult. DeviceOSVersion = $d. DeviceOSVersion</span><span class="sxs-lookup"><span data-stu-id="270d6-190">$deviceResult.DeviceOSVersion = $d.DeviceOSVersion</span></span>
    

48.  <span data-ttu-id="270d6-191">$deviceResult. DeviceTrustLevel = $d. DeviceTrustLevel</span><span class="sxs-lookup"><span data-stu-id="270d6-191">$deviceResult.DeviceTrustLevel = $d.DeviceTrustLevel</span></span>
    

49.  <span data-ttu-id="270d6-192">$deviceResult. DisplayName = $d. DisplayName</span><span class="sxs-lookup"><span data-stu-id="270d6-192">$deviceResult.DisplayName = $d.DisplayName</span></span>
    

50.  <span data-ttu-id="270d6-193">$deviceResult. IsCompliant = $d. GraphDeviceObject. IsCompliant</span><span class="sxs-lookup"><span data-stu-id="270d6-193">$deviceResult.IsCompliant = $d.GraphDeviceObject.IsCompliant</span></span>
    

51.  <span data-ttu-id="270d6-194">$deviceResult. Managed = $d. GraphDeviceObject. Managed</span><span class="sxs-lookup"><span data-stu-id="270d6-194">$deviceResult.IsManaged = $d.GraphDeviceObject.IsManaged</span></span>
    

52.  <span data-ttu-id="270d6-195">$deviceResult. DeviceObjectId = $d. ObjectId</span><span class="sxs-lookup"><span data-stu-id="270d6-195">$deviceResult.DeviceObjectId = $d.ObjectId</span></span>
    

53.  <span data-ttu-id="270d6-196">$deviceResult. RegisteredOwnerUpn = $u. UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="270d6-196">$deviceResult.RegisteredOwnerUpn = $u.UserPrincipalName</span></span>
    

54.  <span data-ttu-id="270d6-197">$deviceResult. RegisteredOwnerObjectId = $u. ObjectId</span><span class="sxs-lookup"><span data-stu-id="270d6-197">$deviceResult.RegisteredOwnerObjectId = $u.ObjectId</span></span>
    

55.  <span data-ttu-id="270d6-198">$deviceResult. RegisteredOwnerDisplayName = $u. DisplayName</span><span class="sxs-lookup"><span data-stu-id="270d6-198">$deviceResult.RegisteredOwnerDisplayName = $u.DisplayName</span></span>
    

56.  <span data-ttu-id="270d6-199">$deviceResult. ApproximateLastLogonTimestamp = $d. ApproximateLastLogonTimestamp</span><span class="sxs-lookup"><span data-stu-id="270d6-199">$deviceResult.ApproximateLastLogonTimestamp = $d.ApproximateLastLogonTimestamp</span></span>
    

58.  <span data-ttu-id="270d6-200">$deviceResult</span><span class="sxs-lookup"><span data-stu-id="270d6-200">$deviceResult</span></span>
    

59.  <span data-ttu-id="270d6-201">}</span><span class="sxs-lookup"><span data-stu-id="270d6-201">}</span></span>
    

61.  <span data-ttu-id="270d6-202">}</span><span class="sxs-lookup"><span data-stu-id="270d6-202">}</span></span>
    

63.  <span data-ttu-id="270d6-203">If ($export)</span><span class="sxs-lookup"><span data-stu-id="270d6-203">If ($export)</span></span>
    

64.  <span data-ttu-id="270d6-204">{</span><span class="sxs-lookup"><span data-stu-id="270d6-204">{</span></span>
    

65.  <span data-ttu-id="270d6-205">$result | Export-CSV-Path ($exportPath + " \" + $ExportFileName)-NoTypeInformation</span><span class="sxs-lookup"><span data-stu-id="270d6-205">$result | Export-Csv -path ($exportPath + "\" + $exportFileName) -NoTypeInformation</span></span>
    

66.  <span data-ttu-id="270d6-206">}</span><span class="sxs-lookup"><span data-stu-id="270d6-206">}</span></span>
    

67.  <span data-ttu-id="270d6-207">Altro</span><span class="sxs-lookup"><span data-stu-id="270d6-207">Else</span></span>
    

68.  <span data-ttu-id="270d6-208">{</span><span class="sxs-lookup"><span data-stu-id="270d6-208">{</span></span>
    

69.  <span data-ttu-id="270d6-209">$result</span><span class="sxs-lookup"><span data-stu-id="270d6-209">$result</span></span>
    

70.  <span data-ttu-id="270d6-210">}</span><span class="sxs-lookup"><span data-stu-id="270d6-210">}</span></span>
    

71.  <span data-ttu-id="270d6-211">Salvarlo come file di script di Windows PowerShell utilizzando l'estensione ps1 del file. ad esempio, Get-MsolUserDeviceComplianceStatus.ps1.</span><span class="sxs-lookup"><span data-stu-id="270d6-211">Save it as a Windows PowerShell script file by using the file extension .ps1; for example, Get-MsolUserDeviceComplianceStatus.ps1.</span></span>   

## <a name="run-the-script-to-get-device-information-for-a-single-user-account"></a><span data-ttu-id="270d6-212">Eseguire lo script per ottenere informazioni sul dispositivo per un singolo account utente</span><span class="sxs-lookup"><span data-stu-id="270d6-212">Run the script to get device information for a single user account</span></span>

1. <span data-ttu-id="270d6-213">Aprire il modulo Microsoft Azure Active Directory per Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="270d6-213">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>
    
2. <span data-ttu-id="270d6-214">Passare alla cartella in cui è stato salvato lo script.</span><span class="sxs-lookup"><span data-stu-id="270d6-214">Go to the folder where you saved the script.</span></span> <span data-ttu-id="270d6-215">Ad esempio, se è stato salvato in C:\PS-Scripts, eseguire il comando riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="270d6-215">For example, if you saved it to C:\PS-Scripts, run the following command.</span></span>
    
    <span data-ttu-id="270d6-216">C:\PS-Scripts CD</span><span class="sxs-lookup"><span data-stu-id="270d6-216">cd C:\PS-Scripts</span></span>

3. <span data-ttu-id="270d6-217">Eseguire il seguente comando per identificare l'utente per il quale si desidera ottenere i dettagli del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="270d6-217">Run the following command to identify the user you want to get device details for.</span></span> <span data-ttu-id="270d6-218">In questo esempio vengono recuperati i dettagli per bar@example.com.</span><span class="sxs-lookup"><span data-stu-id="270d6-218">This example gets details for bar@example.com.</span></span>
    
    <span data-ttu-id="270d6-219">$u = Get-MsolUser-UserPrincipalName bar@example.com</span><span class="sxs-lookup"><span data-stu-id="270d6-219">$u = Get-MsolUser -UserPrincipalName bar@example.com</span></span>

4. <span data-ttu-id="270d6-220">Per avviare lo script, eseguire il comando riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="270d6-220">Run the following command to initiate the script.</span></span>

    <span data-ttu-id="270d6-221">.\Get-MsolUserDeviceComplianceStatus.ps1-$u utente-Export</span><span class="sxs-lookup"><span data-stu-id="270d6-221">.\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export</span></span>

<span data-ttu-id="270d6-222">Le informazioni vengono esportate nel desktop di Windows come file CSV.</span><span class="sxs-lookup"><span data-stu-id="270d6-222">The information is exported to your Windows Desktop as a CSV file.</span></span> <span data-ttu-id="270d6-223">È possibile utilizzare parametri aggiuntivi per specificare il nome e il percorso del file CSV.</span><span class="sxs-lookup"><span data-stu-id="270d6-223">You can use additional parameters to specify the file name and path of the CSV.</span></span>

## <a name="run-the-script-to-get-device-information-for-a-group-of-users"></a><span data-ttu-id="270d6-224">Eseguire lo script per ottenere informazioni sul dispositivo per un gruppo di utenti</span><span class="sxs-lookup"><span data-stu-id="270d6-224">Run the script to get device information for a group of users</span></span>

1. <span data-ttu-id="270d6-225">Aprire il modulo Microsoft Azure Active Directory per Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="270d6-225">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>
    
2. <span data-ttu-id="270d6-226">Passare alla cartella in cui è stato salvato lo script.</span><span class="sxs-lookup"><span data-stu-id="270d6-226">Go to the folder where you saved the script.</span></span> <span data-ttu-id="270d6-227">Ad esempio, se è stato salvato in C:\PS-Scripts, eseguire il comando riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="270d6-227">For example, if you saved it to C:\PS-Scripts, run the following command.</span></span>   

    <span data-ttu-id="270d6-228">C:\PS-Scripts CD</span><span class="sxs-lookup"><span data-stu-id="270d6-228">cd C:\PS-Scripts</span></span>

3. <span data-ttu-id="270d6-229">Eseguire il seguente comando per identificare il gruppo per cui si desidera ottenere i dettagli del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="270d6-229">Run the following command to identify the group you want to get device details for.</span></span> <span data-ttu-id="270d6-230">In questo esempio vengono recuperati i dettagli per gli utenti del gruppo FinanceStaff.</span><span class="sxs-lookup"><span data-stu-id="270d6-230">This example gets details for users in the FinanceStaff group.</span></span> 

    <span data-ttu-id="270d6-231">$u = get-MsolGroupMember-SearchString "FinanceStaff" | % {Get-MsolUser-ObjectId $ _. ObjectId</span><span class="sxs-lookup"><span data-stu-id="270d6-231">$u = Get-MsolGroupMember -SearchString "FinanceStaff" | % { Get-MsolUser -ObjectId $_.ObjectId }</span></span>

4. <span data-ttu-id="270d6-232">Per avviare lo script, eseguire il comando riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="270d6-232">Run the following command to initiate the script.</span></span>   

    <span data-ttu-id="270d6-233">.\Get-MsolUserDeviceComplianceStatus.ps1-$u utente-Export</span><span class="sxs-lookup"><span data-stu-id="270d6-233">.\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export</span></span>

<span data-ttu-id="270d6-234">Le informazioni vengono esportate nel desktop di Windows come file CSV.</span><span class="sxs-lookup"><span data-stu-id="270d6-234">The information is exported to your Windows Desktop as a CSV file.</span></span> <span data-ttu-id="270d6-235">È possibile utilizzare parametri aggiuntivi per specificare il nome e il percorso del file CSV.</span><span class="sxs-lookup"><span data-stu-id="270d6-235">You can use additional parameters to specify the file name and path of the CSV.</span></span>

## <a name="related-topics"></a><span data-ttu-id="270d6-236">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="270d6-236">Related topics</span></span>

[<span data-ttu-id="270d6-237">Microsoft Connect è stato ritirato</span><span class="sxs-lookup"><span data-stu-id="270d6-237">Microsoft Connect Has Been Retired</span></span>](https://docs.microsoft.com/collaborate/connect-redirect)

[<span data-ttu-id="270d6-238">Panoramica della sicurezza e della mobilità di base</span><span class="sxs-lookup"><span data-stu-id="270d6-238">Overview of Basic Mobility and Security</span></span>](overview-of-basic-mobility-and-security-for-microsoft-365.md)

[<span data-ttu-id="270d6-239">Get-MsolDevice</span><span class="sxs-lookup"><span data-stu-id="270d6-239">Get-MsolDevice</span></span>](https://go.microsoft.com/fwlink/?linkid=841721)