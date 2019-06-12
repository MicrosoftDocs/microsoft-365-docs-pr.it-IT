---
title: Registrare i dispositivi in Microsoft Managed Desktop
description: Registrare i dispositivi da soli in modo che possano essere gestiti da Microsoft Managed Desktop
ms.prod: w10
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: f1e61cfc7fd1d6d597efbfa2480155e06a3d3eb7
ms.sourcegitcommit: d6fcd57a0689abbe4ab47489034f52e327f4e5f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/11/2019
ms.locfileid: "34857299"
---
# <a name="register-devices-in-microsoft-managed-desktop"></a><span data-ttu-id="54215-103">Registrare i dispositivi in Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="54215-103">Register devices in Microsoft Managed Desktop</span></span>

>[!NOTE]
><span data-ttu-id="54215-104">In questo argomento vengono illustrati i passaggi da eseguire per la registrazione dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="54215-104">This topic describes the steps for you to register devices on your own.</span></span> <span data-ttu-id="54215-105">Il processo per i partner è documentato nei [dispositivi di registrazione in Microsoft Managed Desktop for partners](register-devices-partner.md).</span><span class="sxs-lookup"><span data-stu-id="54215-105">The process for Partners is documented in [Register devices in Microsoft Managed Desktop for Partners](register-devices-partner.md).</span></span>

<span data-ttu-id="54215-106">Microsoft Managed Desktop è in grado di lavorare con dispositivi nuovi di zecca oppure è possibile riutilizzare i dispositivi che potrebbero essere già presenti (il che richiede che vengano ristampati).</span><span class="sxs-lookup"><span data-stu-id="54215-106">Microsoft Managed Desktop can work with brand-new devices or you can re-use devices you might already have (which will require that you re-image them).</span></span> <span data-ttu-id="54215-107">È possibile registrare i dispositivi tramite Microsoft Managed Desktop sul portale di Azure o ottenere flessibilità utilizzando un'API.</span><span class="sxs-lookup"><span data-stu-id="54215-107">You can register devices by using Microsoft Managed Desktop on the Azure Portal or gain flexibility by using an API.</span></span>

## <a name="prepare-to-register-devices"></a><span data-ttu-id="54215-108">Preparare la registrazione di dispositivi</span><span class="sxs-lookup"><span data-stu-id="54215-108">Prepare to register devices</span></span>

<span data-ttu-id="54215-109">Se non sono già stati ottenuti i dispositivi che si desidera utilizzare, controllare i [dispositivi Microsoft Managed Desktop](../service-description/device-list.md) e collaborare con un partner dispositivo per procurarsi dispositivi supportati.</span><span class="sxs-lookup"><span data-stu-id="54215-109">If you haven't already obtained the devices you want to use, check [Microsoft Managed Desktop devices](../service-description/device-list.md) and work with a device partner to procure supported devices.</span></span>

<span data-ttu-id="54215-110">Se si lavora con dispositivi completamente nuovi o si riutilizzano quelli esistenti, per registrarli con Microsoft Managed Desktop, è necessario preparare un **file CSV (delimitato da virgole)**.</span><span class="sxs-lookup"><span data-stu-id="54215-110">Whether you're working with completely new devices or re-using existing ones, to register them with Microsoft Managed Desktop, you'll need to prepare a **comma-delimited (CSV) file**.</span></span> <span data-ttu-id="54215-111">Questo file deve includere le informazioni seguenti per ogni dispositivo:</span><span class="sxs-lookup"><span data-stu-id="54215-111">This file should include the following information for each device:</span></span>

>[!NOTE]
><span data-ttu-id="54215-112">Questo formato è solo per la registrazione in modalità self-service.</span><span class="sxs-lookup"><span data-stu-id="54215-112">This format is for self-service registration only.</span></span> <span data-ttu-id="54215-113">Il formato dei partner dovrebbe essere utilizzato è documentato nei [dispositivi di registrazione in Microsoft Managed Desktop for partners](register-devices-partner.md).</span><span class="sxs-lookup"><span data-stu-id="54215-113">The format Partners should use is documented in [Register devices in Microsoft Managed Desktop for Partners](register-devices-partner.md).</span></span>

<span data-ttu-id="54215-114">Questi valori vengono utilizzati per scopi di visualizzazione e non è necessario corrispondere esattamente alle proprietà del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="54215-114">These values are used for display purposes, and don't need to match properties from the device exactly.</span></span>
- <span data-ttu-id="54215-115">Produttore del dispositivo (ad esempio: SpiralOrbit)</span><span class="sxs-lookup"><span data-stu-id="54215-115">Device manufacturer (example: SpiralOrbit)</span></span> 
- <span data-ttu-id="54215-116">Modello di dispositivo (ad esempio: ContosoABC)</span><span class="sxs-lookup"><span data-stu-id="54215-116">Device model (example: ContosoABC)</span></span>
- <span data-ttu-id="54215-117">Numero di serie del dispositivo</span><span class="sxs-lookup"><span data-stu-id="54215-117">Device serial number</span></span>

<span data-ttu-id="54215-118">L'hash hardware deve essere una corrispondenza esatta.</span><span class="sxs-lookup"><span data-stu-id="54215-118">The hardware hash must be an exact match.</span></span>
- <span data-ttu-id="54215-119">Hash hardware</span><span class="sxs-lookup"><span data-stu-id="54215-119">Hardware hash</span></span>

<span data-ttu-id="54215-120">Per ottenere l'hash hardware, è possibile richiedere assistenza all'OEM o al partner oppure eseguire la procedura seguente per ogni dispositivo:</span><span class="sxs-lookup"><span data-stu-id="54215-120">To obtain the hardware hash you can ask for help from your OEM or Partner, or follow these steps for each device:</span></span>

1.  <span data-ttu-id="54215-121">Aprire un prompt di PowerShell con diritti amministrativi.</span><span class="sxs-lookup"><span data-stu-id="54215-121">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="54215-122">Correre`Install-Script -Name Get-MMDRegistrationInfo`</span><span class="sxs-lookup"><span data-stu-id="54215-122">Run `Install-Script -Name Get-MMDRegistrationInfo`</span></span>
3.  <span data-ttu-id="54215-123">Correre`powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="54215-123">Run `powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span></span>


<span data-ttu-id="54215-124">In alternativa, è possibile eseguire questa procedura in un dispositivo nuovo di zecca (prima di passare per la prima volta tramite OOBE):</span><span class="sxs-lookup"><span data-stu-id="54215-124">Alternately, you can follow these steps on a brand-new device (before going through OOBE for the first time):</span></span>

1. <span data-ttu-id="54215-125">In un altro dispositivo, inserire un'unità USB.</span><span class="sxs-lookup"><span data-stu-id="54215-125">On a different device, insert a USB drive.</span></span>
2. <span data-ttu-id="54215-126">Aprire un prompt di PowerShell con diritti amministrativi.</span><span class="sxs-lookup"><span data-stu-id="54215-126">Open a PowerShell prompt with administrative rights.</span></span>
3. <span data-ttu-id="54215-127">Correre`Save-Script -Name Get-MMDRegistrationInfo -Path <pathToUsb>`</span><span class="sxs-lookup"><span data-stu-id="54215-127">Run `Save-Script -Name Get-MMDRegistrationInfo -Path <pathToUsb>`</span></span>
4. <span data-ttu-id="54215-128">Attivare il dispositivo di destinazione, ma non avviare l'esperienza di installazione.</span><span class="sxs-lookup"><span data-stu-id="54215-128">Turn on the target device, but do not start the setup experience.</span></span> <span data-ttu-id="54215-129">Se si avvia accidentalmente l'esperienza di installazione, sarà necessario reimpostare o ricreare il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="54215-129">If you accidentally start the setup experience, you'll have to reset or reimage the device.</span></span>
5. <span data-ttu-id="54215-130">Inserire l'unità USB e quindi premere MAIUSC + F10.</span><span class="sxs-lookup"><span data-stu-id="54215-130">Insert the USB drive, and then press SHIFT + F10.</span></span>
6. <span data-ttu-id="54215-131">Aprire un prompt di PowerShell con diritti amministrativi e quindi eseguirlo `cd <pathToUsb>`.</span><span class="sxs-lookup"><span data-stu-id="54215-131">Open a PowerShell prompt with administrative rights, and then run `cd <pathToUsb>`.</span></span>
7. <span data-ttu-id="54215-132">Correre`Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span><span class="sxs-lookup"><span data-stu-id="54215-132">Run `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span></span>
8. <span data-ttu-id="54215-133">Correre`.\Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="54215-133">Run `.\Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span></span>
3. <span data-ttu-id="54215-134">Rimuovere l'unità USB e quindi arrestare il dispositivo eseguendo`shutdown -s -t 0`</span><span class="sxs-lookup"><span data-stu-id="54215-134">Remove the USB drive, and then shut down the device by running `shutdown -s -t 0`</span></span>

>[!IMPORTANT]
><span data-ttu-id="54215-135">Non accendere nuovamente il dispositivo di destinazione fino a quando non si è completata la registrazione.</span><span class="sxs-lookup"><span data-stu-id="54215-135">Do not power on the target device again until you've completed registration for it.</span></span> 

>[!NOTE]
><span data-ttu-id="54215-136">Per comodità, è possibile scaricare un [modello](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-partner.xlsx) per questo file CSV.</span><span class="sxs-lookup"><span data-stu-id="54215-136">For your convenience, you can download a [template](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-partner.xlsx) for this CSV file.</span></span>

<span data-ttu-id="54215-137">Il file deve includere le **intestazioni di colonna** identiche a quelle del campione (produttore, modello e così via), ma i propri dati per le altre righe.</span><span class="sxs-lookup"><span data-stu-id="54215-137">Your file needs to include the **exact same column headings** as the sample one (Manufacturer, Model, etc.), but your own data for the other rows.</span></span> <span data-ttu-id="54215-138">Se si utilizza il modello, aprirlo in uno strumento di modifica del testo, ad esempio Blocco note, e considerare di lasciare tutti i dati solo nella riga 1, immettendo solo i dati nelle righe 2 e seguenti.</span><span class="sxs-lookup"><span data-stu-id="54215-138">If you use the template, open it in a text editing tool such as Notepad, and consider leaving all the data in row 1 alone, only entering data in rows 2 and below.</span></span> 
    
  ```
 Manufacturer,Model,Serial Number,Hardware Hash
  SpiralOrbit,ContosoABC,000000000000,dGhpc2RldmljZWlzYW5tbWRkZXZpY2U
  
  
  ```

>[!NOTE]
><span data-ttu-id="54215-139">Se si dimentica di modificare i dati di esempio, la registrazione avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="54215-139">If you forget to change any of the sample data, registration will fail.</span></span>   


## <a name="register-devices-by-using-the-azure-portal"></a><span data-ttu-id="54215-140">Registrare i dispositivi tramite il portale di Azure</span><span class="sxs-lookup"><span data-stu-id="54215-140">Register devices by using the Azure Portal</span></span>

<span data-ttu-id="54215-141">Dal portale Microsoft Managed Desktop [Azure](https://aka.ms/mmdportal)selezionare **dispositivi** nel riquadro di spostamento a sinistra.</span><span class="sxs-lookup"><span data-stu-id="54215-141">From the Microsoft Managed Desktop [Azure Portal](https://aka.ms/mmdportal), select **Devices** in the left navigation pane.</span></span> <span data-ttu-id="54215-142">Selezionare **+ registra dispositivi**; verrà aperto il volo:</span><span class="sxs-lookup"><span data-stu-id="54215-142">Select **+ Register devices**; the fly-in opens:</span></span>

<span data-ttu-id="54215-143">[![Fly-in dopo aver selezionato i dispositivi di registrazione](images/register-devices-flyin-sterile.png)](images/register-devices-flyin-sterile.png)</span><span class="sxs-lookup"><span data-stu-id="54215-143">[![Fly-in after selecting Register devices](images/register-devices-flyin-sterile.png)](images/register-devices-flyin-sterile.png)</span></span>


[//]: # (Purtroppo questo non è vero. È possibile rimuovere questa nota, lasciandola adesso fino a quando non avremo la possibilità di chattare.)

<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


<span data-ttu-id="54215-145">Eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="54215-145">Follow these steps:</span></span>

1. <span data-ttu-id="54215-146">In **caricamento file**, specificare un percorso per il file CSV creato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="54215-146">In **File upload**, provide a path to the CSV file you created previously.</span></span>
2. <span data-ttu-id="54215-147">Facoltativamente, è possibile aggiungere un **ID ordine** o un **ID acquisto** per i propri scopi di verifica.</span><span class="sxs-lookup"><span data-stu-id="54215-147">Optionally, you can add an **Order ID** or **Purchase ID** for your own tracking purposes.</span></span> <span data-ttu-id="54215-148">Non sono presenti requisiti di formato per questi valori.</span><span class="sxs-lookup"><span data-stu-id="54215-148">There are no format requirements for these values.</span></span>
3. <span data-ttu-id="54215-149">Selezionare **registra dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="54215-149">Select **Register devices**.</span></span> <span data-ttu-id="54215-150">Il sistema aggiungerà i dispositivi all'elenco di dispositivi sul Blade dei **dispositivi**, contrassegnati come **registrazione in sospeso**.</span><span class="sxs-lookup"><span data-stu-id="54215-150">The system will add the devices to your list of devices on the **Devices blade**, marked as **Registration Pending**.</span></span> <span data-ttu-id="54215-151">La registrazione richiede in genere meno di 10 minuti e, quando il dispositivo verrà visualizzato come **pronto per il significato dell'utente** , è pronto e in attesa che l'utente finale inizi a utilizzare.</span><span class="sxs-lookup"><span data-stu-id="54215-151">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for an end-user to start using.</span></span>


<span data-ttu-id="54215-152">È possibile monitorare lo stato di registrazione dei dispositivi nella pagina principale di **Microsoft Managed Desktop-Devices** .</span><span class="sxs-lookup"><span data-stu-id="54215-152">You can monitor the progress of device registration on the main **Microsoft Managed Desktop - Devices** page.</span></span> <span data-ttu-id="54215-153">Gli stati possibili segnalati includono:</span><span class="sxs-lookup"><span data-stu-id="54215-153">Possible states reported there include:</span></span>

| <span data-ttu-id="54215-154">Stato</span><span class="sxs-lookup"><span data-stu-id="54215-154">State</span></span> | <span data-ttu-id="54215-155">Descrizione</span><span class="sxs-lookup"><span data-stu-id="54215-155">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="54215-156">Registrazione in sospeso</span><span class="sxs-lookup"><span data-stu-id="54215-156">Registration pending</span></span> | <span data-ttu-id="54215-157">La registrazione non è ancora stata completata.</span><span class="sxs-lookup"><span data-stu-id="54215-157">Registration is not done yet.</span></span> <span data-ttu-id="54215-158">Controllare in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="54215-158">Check back later.</span></span> |
| <span data-ttu-id="54215-159">Registrazione non riuscita</span><span class="sxs-lookup"><span data-stu-id="54215-159">Registration failed</span></span> | <span data-ttu-id="54215-160">La registrazione non è stata completata.</span><span class="sxs-lookup"><span data-stu-id="54215-160">Registration could not be completed.</span></span> <span data-ttu-id="54215-161">Per ulteriori informazioni, fare riferimento a [risoluzione dei problemi](register-devices-self.md#troubleshooting) .</span><span class="sxs-lookup"><span data-stu-id="54215-161">Refer to [Troubleshooting](register-devices-self.md#troubleshooting) for more information.</span></span> |
| <span data-ttu-id="54215-162">Pronto per l'utente</span><span class="sxs-lookup"><span data-stu-id="54215-162">Ready for user</span></span> | <span data-ttu-id="54215-163">La registrazione ha avuto esito positivo e il dispositivo è ora pronto per essere recapitato all'utente finale.</span><span class="sxs-lookup"><span data-stu-id="54215-163">Registration succeeded and the device is now ready to be delivered to the end user.</span></span> <span data-ttu-id="54215-164">Microsoft Managed Desktop li guiderà per la prima volta, quindi non è necessario eseguire ulteriori preparativi.</span><span class="sxs-lookup"><span data-stu-id="54215-164">Microsoft Managed Desktop will guide them through first time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="54215-165">Attivo</span><span class="sxs-lookup"><span data-stu-id="54215-165">Active</span></span> | <span data-ttu-id="54215-166">Il dispositivo è stato recapitato all'utente finale ed è stato registrato con il tenant.</span><span class="sxs-lookup"><span data-stu-id="54215-166">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="54215-167">Questo indica anche che stanno usando regolarmente il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="54215-167">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="54215-168">Inattivo</span><span class="sxs-lookup"><span data-stu-id="54215-168">Inactive</span></span> | <span data-ttu-id="54215-169">Il dispositivo è stato recapitato all'utente finale ed è stato registrato con il tenant.</span><span class="sxs-lookup"><span data-stu-id="54215-169">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="54215-170">Tuttavia, non hanno utilizzato il dispositivo di recente (negli ultimi 7 giorni).</span><span class="sxs-lookup"><span data-stu-id="54215-170">However, they have not used the device recently (in the last 7 days).</span></span>  | 


## <a name="register-devices-by-using-an-api"></a><span data-ttu-id="54215-171">Registrare i dispositivi tramite un'API</span><span class="sxs-lookup"><span data-stu-id="54215-171">Register devices by using an API</span></span>

<span data-ttu-id="54215-172">È disponibile un'API REST per consentire una maggiore flessibilità e ripetibilità con frequenti registrazioni di dispositivi separate.</span><span class="sxs-lookup"><span data-stu-id="54215-172">A REST API is available to allow you greater flexibility and repeatability with frequent separate device registrations.</span></span> <span data-ttu-id="54215-173">Al momento, per utilizzare l'API, chiedere assistenza al contatto Microsoft per partecipare a un'anteprima di questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="54215-173">Currently, to use the API, ask for help from your Microsoft contact to join a preview of this capability.</span></span>



## <a name="troubleshooting"></a><span data-ttu-id="54215-174">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="54215-174">Troubleshooting</span></span>

| <span data-ttu-id="54215-175">Messaggio di errore</span><span class="sxs-lookup"><span data-stu-id="54215-175">Error message</span></span> | <span data-ttu-id="54215-176">Dettagli</span><span class="sxs-lookup"><span data-stu-id="54215-176">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="54215-177">Dispositivo non trovato</span><span class="sxs-lookup"><span data-stu-id="54215-177">Device not found</span></span> | <span data-ttu-id="54215-178">Non è stato possibile registrare il dispositivo perché non è stata trovata una corrispondenza per il produttore, il modello o il numero di serie specificato.</span><span class="sxs-lookup"><span data-stu-id="54215-178">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="54215-179">Confermare questi valori con il fornitore del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="54215-179">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="54215-180">Dispositivo non trovato</span><span class="sxs-lookup"><span data-stu-id="54215-180">Device not found</span></span> | <span data-ttu-id="54215-181">Non è stato possibile annullare la registrazione di questo dispositivo perché non esiste nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="54215-181">We couldn’t de-register this device because it does not exist in your organization.</span></span> <span data-ttu-id="54215-182">Non sono necessarie ulteriori azioni.</span><span class="sxs-lookup"><span data-stu-id="54215-182">No further action required.</span></span> |
| <span data-ttu-id="54215-183">Hash hardware non valido</span><span class="sxs-lookup"><span data-stu-id="54215-183">Hardware hash not valid</span></span> | <span data-ttu-id="54215-184">L'hash hardware fornito per il dispositivo non è stato formattato correttamente.</span><span class="sxs-lookup"><span data-stu-id="54215-184">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="54215-185">Fare doppio check sull'hash hardware e quindi inviare di nuovo.</span><span class="sxs-lookup"><span data-stu-id="54215-185">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="54215-186">Dispositivo già registrato</span><span class="sxs-lookup"><span data-stu-id="54215-186">Device already registered</span></span> | <span data-ttu-id="54215-187">Questo dispositivo è già registrato nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="54215-187">This device is already registered to your organization.</span></span> <span data-ttu-id="54215-188">Non sono necessarie ulteriori azioni.</span><span class="sxs-lookup"><span data-stu-id="54215-188">No further action required.</span></span> |
| <span data-ttu-id="54215-189">Dispositivo rivendicato da un'altra organizzazione</span><span class="sxs-lookup"><span data-stu-id="54215-189">Device claimed by another organization</span></span> | <span data-ttu-id="54215-190">Questo dispositivo è già stato rivendicato da un'altra organizzazione.</span><span class="sxs-lookup"><span data-stu-id="54215-190">This device has already been claimed by another organization.</span></span> <span data-ttu-id="54215-191">Controllare con il fornitore del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="54215-191">Check with your device supplier.</span></span> |
| <span data-ttu-id="54215-192">Errore imprevisto</span><span class="sxs-lookup"><span data-stu-id="54215-192">Unexpected error</span></span> | <span data-ttu-id="54215-193">La richiesta non è stata elaborata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="54215-193">Your request could not be automatically processed.</span></span> <span data-ttu-id="54215-194">Contattare il supporto tecnico e fornire l'ID richiesta:<requestId></span><span class="sxs-lookup"><span data-stu-id="54215-194">Contact Support and provide the Request ID: <requestId></span></span> |




