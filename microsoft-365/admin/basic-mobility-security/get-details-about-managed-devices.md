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
ms.openlocfilehash: d34263ee215c568834034f2735bb69d9cef9ac6d
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430211"
---
# <a name="get-details-about-basic-mobility-and-security-managed-devices"></a>Ottenere informazioni dettagliate sui dispositivi gestiti di sicurezza e mobilità di base

In questo articolo viene illustrato come utilizzare Windows PowerShell per ottenere informazioni dettagliate sui dispositivi dell'organizzazione che sono stati configurati per la sicurezza e la mobilità di base.

Di seguito viene illustrata una ripartizione per i dettagli del dispositivo disponibili.

|**Dettagli**|**Cosa cercare in PowerShell**|
|:----------------|:------------------------------------------------------------------------------|
|Il dispositivo è registrato in mobilità e sicurezza di base. Per altre informazioni, vedere [registrazione del dispositivo mobile tramite la sicurezza e la mobilità di base](enroll-your-mobile-device.md)|Il valore del parametro *Managed*   è:<br/>**True**= il dispositivo è registrato.<br/>**False**= il dispositivo non è registrato. |
|Il dispositivo è conforme ai criteri di sicurezza del dispositivo. Per altre informazioni, vedere [creare criteri di sicurezza dei dispositivi](create-device-security-policies.md)|Il valore del parametro *isCompliant*   è:<br/>**Vero**   = il dispositivo è conforme ai criteri.<br/>Valore **false**   = il dispositivo non è conforme ai criteri.|

:::image type="content" source="../../media/basic-mobility-security/bms-7-powershell-parameters.png" alt-text="Parametri di base per la mobilità e la sicurezza di PowerShell":::

>[!NOTE]
>I comandi e gli script di questo articolo restituiscono anche informazioni dettagliate su tutti i dispositivi gestiti da [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune).

## <a name="before-you-begin"></a>Informazioni preliminari

Per eseguire i comandi e gli script descritti in questo articolo, è necessario impostare alcuni aspetti.

### <a name="step-1-download-and-install-the-azure-active-directory-module-for-windows-powershell"></a>Passaggio 1: scaricare e installare il modulo di Azure Active Directory per Windows PowerShell

Per altre informazioni su questi passaggi, vedere [Connect to Microsoft 365 with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell).

1. Accedere a [Assistente per l'accesso ai Microsoft Online Services per professionisti IT RTWl](https://www.microsoft.com/download/details.aspx?id=41950)   e selezionare  **download per l'assistente per l'accesso ai Microsoft Online Services**.   

2. Installare il Modulo di Microsoft Azure Active Directory per Windows PowerShell con la procedura seguente:   

    1. Aprire un prompt di comandi di PowerShell a livello di amministratore.  

    2. Eseguire il comando Install-Module MSOnline.
    
    3. Se viene richiesto di installare il provider NuGet, digitare Y e premere INVIO.   

    4. Se viene richiesto di installare il modulo da PSGallery, digitare Y e premere INVIO.   

    5. Dopo l'installazione, chiudere la finestra di comando di PowerShell.
    
### <a name="step-2-connect-to-your-microsoft-365-subscription"></a>Passaggio 2: connettersi alla sottoscrizione Microsoft 365

1. Nel modulo Windows Azure Active Directory per Windows PowerShell, eseguire il comando riportato di seguito.  

    $UserCredential = Get-Credential

2. Nella finestra di dialogo richiesta credenziali di Windows PowerShell, digitare il nome utente e la password per l'account di amministratore globale di Microsoft 365, quindi selezionare **OK**.
    
3. Eseguire il comando riportato di seguito.
    
    Connect-MsolService-Credential $UserCredential

### <a name="step-3-make-sure-youre-able-to-run-powershell-scripts"></a>Passaggio 3: verificare di essere in grado di eseguire gli script di PowerShell

>[!NOTE]
>È possibile ignorare questo passaggio se si è già configurati per l'esecuzione di script di PowerShell.

Per eseguire lo script Get-MsolUserDeviceComplianceStatus.ps1, è necessario abilitare l'esecuzione degli script di PowerShell.

1. Dal desktop di Windows, selezionare **Avvia**e quindi digitare Windows PowerShell. Fare clic con il pulsante destro del mouse su Windows PowerShell e quindi scegliere **Esegui come amministratore**.

2. Eseguire il comando riportato di seguito.
    
    Set-ExecutionPolicy RemoteSigned

3. Quando richiesto, digitare Y e premere INVIO.
    
**Eseguire il cmdlet Get-MsolDevice per visualizzare i dettagli di tutti i dispositivi nell'organizzazione**

1. Aprire il modulo Microsoft Azure Active Directory per Windows PowerShell.  

2. Eseguire il comando riportato di seguito.
    
    Get-MsolDevice-all-ReturnRegisteredOwners | Where-Object {$ _. RegisteredOwners. Count-gt 0}

Per ulteriori esempi, vedere  [Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=841721).

## <a name="run-a-script-to-get-device-details"></a>Eseguire uno script per ottenere i dettagli del dispositivo

In primo luogo, salvare lo script nel computer.

1. Copiare e incollare il testo seguente nel blocco note.  

2.  param
    

3.  [PSObject []] $users = @ (),
    

4.  [Switch] $export,
    

5.  [String] $exportFileName = "UserDeviceComplianceStatus_" + (Get-Date-Format "yyMMdd_HHMMss") + ". csv",
    

6.  [String] $exportPath = [Environment]:: GetFolderPath ("desktop")
    

7.  )
    

9.  [System. Collections. IDictionary] $script: schema = @ {
    

11.  DeviceId =''
    

12.  DeviceOSType =''
    

13.  DeviceOSVersion =''
    

14.  DeviceTrustLevel =''
    

15.  DisplayName =''
    

16.  IsCompliant =''
    

17.  Managed =''
    

18.  ApproximateLastLogonTimestamp =''
    

19.  DeviceObjectId =''
    

20.  RegisteredOwnerUpn =''
    

21.  RegisteredOwnerObjectId =''
    

22.  RegisteredOwnerDisplayName =''
    

23.  }
    

25.  funzione createResultObject
    

26.  {
    

28.  [PSObject] $resultObject = New-Object-TypeName PSObject-Property $script: schema
    

30.  $resultObject di ritorno
    

31.  }
    

33.  Se ($users. Count-EQ 0)
    

34.  {
    

35.  $users = Get-MsolUser
    

36.  }
    

38.  [PSObject []] $result = foreach ($u in $users)
    

39.  {
    

41.  [PSObject] $devices = Get-msoldevice-RegisteredOwnerUpn $u. UserPrincipalName
    

42.  foreach ($d in $devices)
    

43.  {
    

44.  [PSObject] $deviceResult = createResultObject
    

45.  $deviceResult. DeviceId = $d. DeviceId
    

46.  $deviceResult. DeviceOSType = $d. DeviceOSType
    

47.  $deviceResult. DeviceOSVersion = $d. DeviceOSVersion
    

48.  $deviceResult. DeviceTrustLevel = $d. DeviceTrustLevel
    

49.  $deviceResult. DisplayName = $d. DisplayName
    

50.  $deviceResult. IsCompliant = $d. GraphDeviceObject. IsCompliant
    

51.  $deviceResult. Managed = $d. GraphDeviceObject. Managed
    

52.  $deviceResult. DeviceObjectId = $d. ObjectId
    

53.  $deviceResult. RegisteredOwnerUpn = $u. UserPrincipalName
    

54.  $deviceResult. RegisteredOwnerObjectId = $u. ObjectId
    

55.  $deviceResult. RegisteredOwnerDisplayName = $u. DisplayName
    

56.  $deviceResult. ApproximateLastLogonTimestamp = $d. ApproximateLastLogonTimestamp
    

58.  $deviceResult
    

59.  }
    

61.  }
    

63.  If ($export)
    

64.  {
    

65.  $result | Export-CSV-Path ($exportPath + " \" + $ExportFileName)-NoTypeInformation
    

66.  }
    

67.  Altro
    

68.  {
    

69.  $result
    

70.  }
    

71.  Salvarlo come file di script di Windows PowerShell utilizzando l'estensione ps1 del file. ad esempio, Get-MsolUserDeviceComplianceStatus.ps1.   

## <a name="run-the-script-to-get-device-information-for-a-single-user-account"></a>Eseguire lo script per ottenere informazioni sul dispositivo per un singolo account utente

1. Aprire il modulo Microsoft Azure Active Directory per Windows PowerShell.
    
2. Passare alla cartella in cui è stato salvato lo script. Ad esempio, se è stato salvato in C:\PS-Scripts, eseguire il comando riportato di seguito.
    
    C:\PS-Scripts CD

3. Eseguire il seguente comando per identificare l'utente per il quale si desidera ottenere i dettagli del dispositivo. In questo esempio vengono recuperati i dettagli per bar@example.com.
    
    $u = Get-MsolUser-UserPrincipalName bar@example.com

4. Per avviare lo script, eseguire il comando riportato di seguito.

    .\Get-MsolUserDeviceComplianceStatus.ps1-$u utente-Export

Le informazioni vengono esportate nel desktop di Windows come file CSV. È possibile utilizzare parametri aggiuntivi per specificare il nome e il percorso del file CSV.

## <a name="run-the-script-to-get-device-information-for-a-group-of-users"></a>Eseguire lo script per ottenere informazioni sul dispositivo per un gruppo di utenti

1. Aprire il modulo Microsoft Azure Active Directory per Windows PowerShell.
    
2. Passare alla cartella in cui è stato salvato lo script. Ad esempio, se è stato salvato in C:\PS-Scripts, eseguire il comando riportato di seguito.   

    C:\PS-Scripts CD

3. Eseguire il seguente comando per identificare il gruppo per cui si desidera ottenere i dettagli del dispositivo. In questo esempio vengono recuperati i dettagli per gli utenti del gruppo FinanceStaff. 

    $u = get-MsolGroupMember-SearchString "FinanceStaff" | % {Get-MsolUser-ObjectId $ _. ObjectId

4. Per avviare lo script, eseguire il comando riportato di seguito.   

    .\Get-MsolUserDeviceComplianceStatus.ps1-$u utente-Export

Le informazioni vengono esportate nel desktop di Windows come file CSV. È possibile utilizzare parametri aggiuntivi per specificare il nome e il percorso del file CSV.

## <a name="related-topics"></a>Argomenti correlati

[Microsoft Connect è stato ritirato](https://docs.microsoft.com/collaborate/connect-redirect)

[Panoramica della sicurezza e della mobilità di base](overview.md)

[Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=841721)