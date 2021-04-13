---
title: Raccogliere dati di diagnostica di Microsoft Defender Antivirus
description: Usare uno strumento per raccogliere dati per risolvere i problemi di Microsoft Defender Antivirus
keywords: risolvere i problemi, errore, correggere, conformità degli aggiornamenti, oms, monitorare, report, Microsoft Defender av, oggetto Criteri di gruppo, impostazione, dati di diagnostica
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/29/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 3b7c07bace86a2a4651e5c951c6e0b7d954f0982
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690478"
---
# <a name="collect-microsoft-defender-av-diagnostic-data"></a><span data-ttu-id="a3b83-104">Raccogliere i dati di diagnostica di Microsoft Defender AV</span><span class="sxs-lookup"><span data-stu-id="a3b83-104">Collect Microsoft Defender AV diagnostic data</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a3b83-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="a3b83-105">**Applies to:**</span></span>

- [<span data-ttu-id="a3b83-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="a3b83-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="a3b83-107">Questo articolo descrive come raccogliere dati di diagnostica che possono essere usati dai team di supporto e progettazione Microsoft per risolvere i problemi che potrebbero verificarsi quando si usa Microsoft Defender AV.</span><span class="sxs-lookup"><span data-stu-id="a3b83-107">This article describes how to collect diagnostic data that can be used by Microsoft support and engineering teams to help troubleshoot issues you might encounter when using the Microsoft Defender AV.</span></span>

> [!NOTE]
> <span data-ttu-id="a3b83-108">Come parte del processo di indagine o di risposta, puoi raccogliere un pacchetto di indagine da un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a3b83-108">As part of the investigation or response process, you can collect an investigation package from a device.</span></span> <span data-ttu-id="a3b83-109">Ecco come: Raccogliere [il pacchetto di indagine dai dispositivi](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices).</span><span class="sxs-lookup"><span data-stu-id="a3b83-109">Here's how: [Collect investigation package from devices](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices).</span></span>

<span data-ttu-id="a3b83-110">In almeno due dispositivi in cui si verifica lo stesso problema, ottenere il file di diagnostica CAB seguendo la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="a3b83-110">On at least two devices that are experiencing the same issue, obtain the .cab diagnostic file by taking the following steps:</span></span>

1. <span data-ttu-id="a3b83-111">Aprire una versione a livello di amministratore del prompt dei comandi come segue:</span><span class="sxs-lookup"><span data-stu-id="a3b83-111">Open an administrator-level version of the command prompt as follows:</span></span>

    <span data-ttu-id="a3b83-112">a.</span><span class="sxs-lookup"><span data-stu-id="a3b83-112">a.</span></span> <span data-ttu-id="a3b83-113">Apri il menu **Start.**</span><span class="sxs-lookup"><span data-stu-id="a3b83-113">Open the **Start** menu.</span></span>

    <span data-ttu-id="a3b83-114">b.</span><span class="sxs-lookup"><span data-stu-id="a3b83-114">b.</span></span> <span data-ttu-id="a3b83-115">Digitare **cmd**.</span><span class="sxs-lookup"><span data-stu-id="a3b83-115">Type **cmd**.</span></span> <span data-ttu-id="a3b83-116">Fare clic con il pulsante **destro del mouse su Prompt** dei comandi e scegliere Esegui come **amministratore.**</span><span class="sxs-lookup"><span data-stu-id="a3b83-116">Right-click on **Command Prompt** and click **Run as administrator**.</span></span>

    <span data-ttu-id="a3b83-117">c.</span><span class="sxs-lookup"><span data-stu-id="a3b83-117">c.</span></span> <span data-ttu-id="a3b83-118">Immettere le credenziali di amministratore o approvare il prompt.</span><span class="sxs-lookup"><span data-stu-id="a3b83-118">Enter administrator credentials or approve the prompt.</span></span>

2. <span data-ttu-id="a3b83-119">Passare alla directory di Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="a3b83-119">Navigate to the Microsoft Defender directory.</span></span> <span data-ttu-id="a3b83-120">Per impostazione predefinita, è `C:\Program Files\Windows Defender` .</span><span class="sxs-lookup"><span data-stu-id="a3b83-120">By default, this is `C:\Program Files\Windows Defender`.</span></span>

> [!NOTE]
> <span data-ttu-id="a3b83-121">Se si esegue una versione [aggiornata di Microsoft Defender Platform,](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform)eseguire dal percorso `MpCmdRun` seguente: `C:\ProgramData\Microsoft\Windows Defender\Platform\<version>` .</span><span class="sxs-lookup"><span data-stu-id="a3b83-121">If you're running an [updated Microsoft Defender Platform version](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform), please run `MpCmdRun` from the following location: `C:\ProgramData\Microsoft\Windows Defender\Platform\<version>`.</span></span>

3. <span data-ttu-id="a3b83-122">Digitare il comando seguente e quindi premere **INVIO**</span><span class="sxs-lookup"><span data-stu-id="a3b83-122">Type the following command, and then press **Enter**</span></span>  

    ```Dos
    mpcmdrun.exe -GetFiles
    ```
  
4. <span data-ttu-id="a3b83-123">Verrà generato un file CAB contenente diversi log di diagnostica.</span><span class="sxs-lookup"><span data-stu-id="a3b83-123">A .cab file will be generated that contains various diagnostic logs.</span></span> <span data-ttu-id="a3b83-124">Il percorso del file verrà specificato nell'output nel prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="a3b83-124">The location of the file will be specified in the output in the command prompt.</span></span> <span data-ttu-id="a3b83-125">Per impostazione predefinita, il percorso è `C:\ProgramData\Microsoft\Microsoft Defender\Support\MpSupportFiles.cab` .</span><span class="sxs-lookup"><span data-stu-id="a3b83-125">By default, the location is `C:\ProgramData\Microsoft\Microsoft Defender\Support\MpSupportFiles.cab`.</span></span>

> [!NOTE]
> <span data-ttu-id="a3b83-126">Per reindirizzare il file CAB a un percorso diverso o a una condivisione UNC, utilizzare il comando seguente: `mpcmdrun.exe -GetFiles -SupportLogLocation <path>`</span><span class="sxs-lookup"><span data-stu-id="a3b83-126">To redirect the cab file to a a different path or UNC share, use the following command: `mpcmdrun.exe -GetFiles -SupportLogLocation <path>`</span></span>  <br/><span data-ttu-id="a3b83-127">Per ulteriori informazioni, vedere [Reindirizzare i dati di diagnostica a una condivisione UNC.](#redirect-diagnostic-data-to-a-unc-share)</span><span class="sxs-lookup"><span data-stu-id="a3b83-127">For more information, see [Redirect diagnostic data to a UNC share](#redirect-diagnostic-data-to-a-unc-share).</span></span>

5. <span data-ttu-id="a3b83-128">Copiare questi file CAB in un percorso accessibile dal supporto Tecnico Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a3b83-128">Copy these .cab files to a location that can be accessed by Microsoft support.</span></span> <span data-ttu-id="a3b83-129">Un esempio potrebbe essere una cartella di OneDrive protetta da password che puoi condividere con microsoft.</span><span class="sxs-lookup"><span data-stu-id="a3b83-129">An example could be a password-protected OneDrive folder that you can share with us.</span></span>

> [!NOTE]
><span data-ttu-id="a3b83-130">In caso di problemi con la conformità degli aggiornamenti, inviare un messaggio di posta elettronica utilizzando il modello di posta elettronica Supporto conformità aggiornamenti <a href="mailto:ucsupport@microsoft.com?subject=WDAV assessment issue&body=I%20am%20encountering%20the%20following%20issue%20when%20using%20Windows%20Defender%20AV%20in%20Update%20Compliance%3a%20%0d%0aI%20have%20provided%20at%20least%202%20support%20.cab%20files%20at%20the%20following%20location%3a%20%3Caccessible%20share%2c%20including%20access%20details%20such%20as%20password%3E%0d%0aMy%20OMS%20workspace%20ID%20is%3a%20%0d%0aPlease%20contact%20me%20at%3a">e</a>compilare il modello con le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a3b83-130">If you have a problem with Update compliance, send an email using the <a href="mailto:ucsupport@microsoft.com?subject=WDAV assessment issue&body=I%20am%20encountering%20the%20following%20issue%20when%20using%20Windows%20Defender%20AV%20in%20Update%20Compliance%3a%20%0d%0aI%20have%20provided%20at%20least%202%20support%20.cab%20files%20at%20the%20following%20location%3a%20%3Caccessible%20share%2c%20including%20access%20details%20such%20as%20password%3E%0d%0aMy%20OMS%20workspace%20ID%20is%3a%20%0d%0aPlease%20contact%20me%20at%3a">Update Compliance support email template</a>, and fill out the template with the following information:</span></span>
>```
> I am encountering the following issue when using Microsoft Defender Antivirus in Update Compliance:
> I have provided at least 2 support .cab files at the following location:  
> <accessible share, including access details such as password>
>
>    My OMS workspace ID is:
>
>    Please contact me at:

## <a name="redirect-diagnostic-data-to-a-unc-share"></a><span data-ttu-id="a3b83-131">Reindirizzare i dati di diagnostica a una condivisione UNC</span><span class="sxs-lookup"><span data-stu-id="a3b83-131">Redirect diagnostic data to a UNC share</span></span>
<span data-ttu-id="a3b83-132">Per raccogliere dati di diagnostica in un archivio centrale, è possibile specificare il parametro SupportLogLocation.</span><span class="sxs-lookup"><span data-stu-id="a3b83-132">To collect diagnostic data on a central repository, you can specify the SupportLogLocation parameter.</span></span>

```Dos
mpcmdrun.exe -GetFiles -SupportLogLocation <path>
```

<span data-ttu-id="a3b83-133">Copia i dati di diagnostica nel percorso specificato.</span><span class="sxs-lookup"><span data-stu-id="a3b83-133">Copies the diagnostic data to the specified path.</span></span> <span data-ttu-id="a3b83-134">Se il percorso non viene specificato, i dati di diagnostica verranno copiati nel percorso specificato nella configurazione del percorso del registro di supporto.</span><span class="sxs-lookup"><span data-stu-id="a3b83-134">If the path is not specified, the diagnostic data will be copied to the location specified in the Support Log Location Configuration.</span></span>

<span data-ttu-id="a3b83-135">Quando si utilizza il parametro SupportLogLocation, nel percorso di destinazione verrà creata una struttura di cartelle simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="a3b83-135">When the SupportLogLocation parameter is used, a folder structure like as follows will be created in the destination path:</span></span>

```Dos
<path>\<MMDD>\MpSupport-<hostname>-<HHMM>.cab
```

| <span data-ttu-id="a3b83-136">Campo</span><span class="sxs-lookup"><span data-stu-id="a3b83-136">field</span></span>  | <span data-ttu-id="a3b83-137">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a3b83-137">Description</span></span>   |
|:----|:----|
| <span data-ttu-id="a3b83-138">path</span><span class="sxs-lookup"><span data-stu-id="a3b83-138">path</span></span> | <span data-ttu-id="a3b83-139">Percorso specificato nella riga di comando o recuperato dalla configurazione</span><span class="sxs-lookup"><span data-stu-id="a3b83-139">The path as specified on the command line or retrieved from configuration</span></span>
| <span data-ttu-id="a3b83-140">MMDD</span><span class="sxs-lookup"><span data-stu-id="a3b83-140">MMDD</span></span> | <span data-ttu-id="a3b83-141">Mese e giorno in cui sono stati raccolti i dati di diagnostica (ad esempio, 0530)</span><span class="sxs-lookup"><span data-stu-id="a3b83-141">Month and day when the diagnostic data was collected (for example, 0530)</span></span>
| <span data-ttu-id="a3b83-142">hostname</span><span class="sxs-lookup"><span data-stu-id="a3b83-142">hostname</span></span> | <span data-ttu-id="a3b83-143">Nome host del dispositivo in cui sono stati raccolti i dati di diagnostica</span><span class="sxs-lookup"><span data-stu-id="a3b83-143">The hostname of the device on which the diagnostic data was collected</span></span>
| <span data-ttu-id="a3b83-144">HHMM</span><span class="sxs-lookup"><span data-stu-id="a3b83-144">HHMM</span></span> | <span data-ttu-id="a3b83-145">Ore e minuti in cui sono stati raccolti i dati di diagnostica (ad esempio, 1422)</span><span class="sxs-lookup"><span data-stu-id="a3b83-145">Hours and minutes when the diagnostic data was collected (for example, 1422)</span></span>

> [!NOTE]
> <span data-ttu-id="a3b83-146">Quando si usa una condivisione file, assicurarsi che l'account usato per raccogliere il pacchetto di diagnostica abbia accesso in scrittura alla condivisione.</span><span class="sxs-lookup"><span data-stu-id="a3b83-146">When using a file share please make sure that account used to collect the diagnostic package has write access to the share.</span></span>  

## <a name="specify-location-where-diagnostic-data-is-created"></a><span data-ttu-id="a3b83-147">Specificare la posizione in cui vengono creati i dati di diagnostica</span><span class="sxs-lookup"><span data-stu-id="a3b83-147">Specify location where diagnostic data is created</span></span>

<span data-ttu-id="a3b83-148">È inoltre possibile specificare la posizione in cui verrà creato il file CAB di diagnostica utilizzando un oggetto Criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="a3b83-148">You can also specify where the diagnostic .cab file will be created using a Group Policy Object (GPO).</span></span> 

1. <span data-ttu-id="a3b83-149">Aprire l'Editor Criteri di gruppo locali e trovare l'oggetto Criteri di gruppo SupportLogLocation all'indirizzo: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\SupportLogLocation`</span><span class="sxs-lookup"><span data-stu-id="a3b83-149">Open the Local Group Policy Editor and find the SupportLogLocation GPO at: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\SupportLogLocation`</span></span>
   
1. <span data-ttu-id="a3b83-150">Selezionare **Definisci il percorso della directory per copiare i file di registro di supporto.**</span><span class="sxs-lookup"><span data-stu-id="a3b83-150">Select **Define the directory path to copy support log files**.</span></span>

    ![Screenshot dell'editor Criteri di gruppo locali](images/GPO1-SupportLogLocationDefender.png)  
        
     ![Screenshot of define path for log files setting](images/GPO2-SupportLogLocationGPPage.png)  
3. <span data-ttu-id="a3b83-153">All'interno dell'editor dei criteri, selezionare **Abilitato.**</span><span class="sxs-lookup"><span data-stu-id="a3b83-153">Inside the policy editor, select **Enabled**.</span></span>
       
4. <span data-ttu-id="a3b83-154">Specificare il percorso della directory in cui copiare i file di registro di supporto nel **campo** Opzioni.</span><span class="sxs-lookup"><span data-stu-id="a3b83-154">Specify the directory path where you want to copy the support log files in the **Options** field.</span></span>
     <span data-ttu-id="a3b83-155">![Screenshot of Enabled directory path custom setting](images/GPO3-SupportLogLocationGPPageEnabledExample.png)</span><span class="sxs-lookup"><span data-stu-id="a3b83-155">![Screenshot of Enabled directory path custom setting](images/GPO3-SupportLogLocationGPPageEnabledExample.png)</span></span> 
5. <span data-ttu-id="a3b83-156">Selezionare **OK** o **Applica**.</span><span class="sxs-lookup"><span data-stu-id="a3b83-156">Select **OK** or **Apply**.</span></span>

## <a name="see-also"></a><span data-ttu-id="a3b83-157">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a3b83-157">See also</span></span>

- [<span data-ttu-id="a3b83-158">Risolvere i problemi relativi ai report di Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="a3b83-158">Troubleshoot Microsoft Defender Antivirus reporting</span></span>](troubleshoot-reporting.md)