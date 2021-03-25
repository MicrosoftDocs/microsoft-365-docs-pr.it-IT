---
title: Microsoft Defender ATP per Mac - Estensioni di sistema (anteprima)
description: Questo articolo contiene istruzioni per provare la funzionalità delle estensioni di sistema di Microsoft Defender ATP per Mac. Questa funzionalità è attualmente in anteprima pubblica.
keywords: microsoft, defender, atp, mac, kernel, sistema, estensioni, catalina
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: security
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ROBOTS: noindex,nofollow
ms.technology: mde
ms.openlocfilehash: 6becdd995d70c0b8193e8df097c9256dc38c72a2
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185898"
---
# <a name="microsoft-defender-for-endpoint-for-mac---system-extensions-public-preview"></a><span data-ttu-id="f1b6a-105">Microsoft Defender per Endpoint per Mac - anteprima pubblica delle estensioni di sistema)</span><span class="sxs-lookup"><span data-stu-id="f1b6a-105">Microsoft Defender for Endpoint for Mac - system extensions public preview)</span></span>

<span data-ttu-id="f1b6a-106">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="f1b6a-106">**Applies to:**</span></span>
- [<span data-ttu-id="f1b6a-107">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="f1b6a-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f1b6a-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f1b6a-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f1b6a-109">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="f1b6a-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f1b6a-110">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="f1b6a-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="f1b6a-111">In linea con l'evoluzione di macOS, stiamo preparando un aggiornamento defender per Endpoint per Mac che sfrutta le estensioni di sistema anziché le estensioni del kernel.</span><span class="sxs-lookup"><span data-stu-id="f1b6a-111">In alignment with macOS evolution, we are preparing a Defender for Endpoint for Mac update that leverages system extensions instead of kernel extensions.</span></span> <span data-ttu-id="f1b6a-112">Questo aggiornamento si applica solo a macOS Catalina (10.15.4) e alle versioni successive di macOS.</span><span class="sxs-lookup"><span data-stu-id="f1b6a-112">This update will only apply to macOS Catalina (10.15.4) and later versions of macOS.</span></span>

<span data-ttu-id="f1b6a-113">Questa funzionalità è attualmente in anteprima pubblica.</span><span class="sxs-lookup"><span data-stu-id="f1b6a-113">This functionality is currently in public preview.</span></span> <span data-ttu-id="f1b6a-114">Questo articolo descrive come abilitare questa funzionalità nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f1b6a-114">This article describes how to enable this functionality on your device.</span></span> <span data-ttu-id="f1b6a-115">Puoi provare questa funzionalità localmente nel tuo dispositivo o configurarla in remoto tramite uno strumento di gestione.</span><span class="sxs-lookup"><span data-stu-id="f1b6a-115">You can try out this feature locally on your own device or configure it remotely through a management tool.</span></span>

<span data-ttu-id="f1b6a-116">Questi passaggi presuppongono che Defender for Endpoint sia già in esecuzione nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f1b6a-116">These steps assume you already have Defender for Endpoint running on your device.</span></span> <span data-ttu-id="f1b6a-117">Per ulteriori informazioni, vedere [questa pagina](microsoft-defender-endpoint-mac.md).</span><span class="sxs-lookup"><span data-stu-id="f1b6a-117">For more information, see [this page](microsoft-defender-endpoint-mac.md).</span></span>

## <a name="known-issues"></a><span data-ttu-id="f1b6a-118">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="f1b6a-118">Known issues</span></span>

- <span data-ttu-id="f1b6a-119">Abbiamo ricevuto segnalazioni dell'estensione di rete che interferisce con l'estensione Kerberos SSO apple.</span><span class="sxs-lookup"><span data-stu-id="f1b6a-119">We’ve received reports of the network extension interfering with the Apple SSO Kerberos extension.</span></span>
- <span data-ttu-id="f1b6a-120">La versione corrente del prodotto installa ancora un'estensione del kernel.</span><span class="sxs-lookup"><span data-stu-id="f1b6a-120">The current version of the product still installs a kernel extension.</span></span> <span data-ttu-id="f1b6a-121">L'estensione del kernel viene usata solo come meccanismo di fallback e verrà rimossa prima che questa funzionalità raggiunga l'anteprima pubblica.</span><span class="sxs-lookup"><span data-stu-id="f1b6a-121">The kernel extension is only used as a fallback mechanism and will be removed before this feature reaches public preview.</span></span>
- <span data-ttu-id="f1b6a-122">Stiamo ancora lavorando a una versione del prodotto che distribuisce e funziona correttamente su macOS 11 Big Sur.</span><span class="sxs-lookup"><span data-stu-id="f1b6a-122">We're still working on a product version that deploys and functions properly on macOS 11 Big Sur.</span></span>

## <a name="deployment-prerequisites"></a><span data-ttu-id="f1b6a-123">Prerequisiti di distribuzione</span><span class="sxs-lookup"><span data-stu-id="f1b6a-123">Deployment prerequisites</span></span>

- <span data-ttu-id="f1b6a-124">Versione minima del sistema operativo macOS: **10.15.4**</span><span class="sxs-lookup"><span data-stu-id="f1b6a-124">Minimum macOS operating system version: **10.15.4**</span></span>
- <span data-ttu-id="f1b6a-125">Versione minima del prodotto: **101.03.73**</span><span class="sxs-lookup"><span data-stu-id="f1b6a-125">Minimum product version: **101.03.73**</span></span>
- <span data-ttu-id="f1b6a-126">Il dispositivo deve essere nel **canale di aggiornamento rapido Insider.**</span><span class="sxs-lookup"><span data-stu-id="f1b6a-126">Your device must be in the **Insider Fast update channel**.</span></span> <span data-ttu-id="f1b6a-127">È possibile controllare il canale di aggiornamento utilizzando il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="f1b6a-127">You can check the update channel by using the following command:</span></span>

  ```bash
  mdatp health --field release_ring
  ```

  <span data-ttu-id="f1b6a-128">Se il dispositivo non è già nel canale di aggiornamento Insider Fast, esegui il comando seguente dal Terminale.</span><span class="sxs-lookup"><span data-stu-id="f1b6a-128">If your device isn't already in the Insider Fast update channel, execute the following command from the Terminal.</span></span> <span data-ttu-id="f1b6a-129">L'aggiornamento del canale ha effetto al successivo avvio del prodotto (quando viene installato il successivo aggiornamento del prodotto o quando il dispositivo viene riavviato).</span><span class="sxs-lookup"><span data-stu-id="f1b6a-129">The channel update takes effect the next time the product starts (when the next product update is installed, or when the device is rebooted).</span></span>

  ```bash
  defaults write com.microsoft.autoupdate2 ChannelName -string Beta
  ```

  <span data-ttu-id="f1b6a-130">In alternativa, se si è in un ambiente gestito (JAMF o Intune), è possibile configurare il canale di aggiornamento in remoto.</span><span class="sxs-lookup"><span data-stu-id="f1b6a-130">Alternatively, if you're in a managed environment (JAMF or Intune), you can configure the update channel remotely.</span></span> <span data-ttu-id="f1b6a-131">Per altre informazioni, vedi [Distribuire gli aggiornamenti per Microsoft Defender ATP per Mac: Impostare il nome del canale.](mac-updates.md#set-the-channel-name)</span><span class="sxs-lookup"><span data-stu-id="f1b6a-131">For more information, see [Deploy updates for Microsoft Defender ATP for Mac: Set the channel name](mac-updates.md#set-the-channel-name).</span></span>

## <a name="deployment-steps"></a><span data-ttu-id="f1b6a-132">Fasi di distribuzione</span><span class="sxs-lookup"><span data-stu-id="f1b6a-132">Deployment steps</span></span>

<span data-ttu-id="f1b6a-133">Seguire i passaggi di distribuzione corrispondenti all'ambiente e al metodo preferito per provare questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="f1b6a-133">Follow the deployment steps that correspond to your environment and your preferred method of trying out this feature.</span></span>

### <a name="manual-deployment"></a><span data-ttu-id="f1b6a-134">Distribuzione manuale</span><span class="sxs-lookup"><span data-stu-id="f1b6a-134">Manual deployment</span></span>

#### <a name="approve-the-system-extensions-and-enable-the-network-extension"></a><span data-ttu-id="f1b6a-135">Approvare le estensioni di sistema e abilitare l'estensione di rete</span><span class="sxs-lookup"><span data-stu-id="f1b6a-135">Approve the system extensions and enable the network extension</span></span>

1. <span data-ttu-id="f1b6a-136">Dopo aver soddisfatto tutti i prerequisiti di distribuzione, riavvia il dispositivo per avviare il processo di approvazione e attivazione dell'estensione di sistema.</span><span class="sxs-lookup"><span data-stu-id="f1b6a-136">After all deployment prerequisites are met, restart your device to launch the system extension approval and activation process.</span></span>

   <span data-ttu-id="f1b6a-137">Vedrai una serie di istruzioni di sistema per approvare le estensioni di sistema di Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="f1b6a-137">You'll see a series of system prompts to approve the Defender for Endpoint system extensions.</span></span> <span data-ttu-id="f1b6a-138">Devi **approvare tutti** i prompt della serie, perché macOS richiede un'approvazione esplicita per ogni estensione che Defender per Endpoint per Mac installa nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f1b6a-138">You must approve **all** prompts from the series, because macOS requires an explicit approval for each extension that Defender for Endpoint for Mac installs on the device.</span></span>
   
   <span data-ttu-id="f1b6a-139">Per ogni approvazione, seleziona **Apri preferenze di sicurezza** e quindi seleziona **Consenti** per consentire l'esecuzione dell'estensione di sistema.</span><span class="sxs-lookup"><span data-stu-id="f1b6a-139">For each approval, select **Open Security Preferences** and then select **Allow** to allow the system extension to run.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="f1b6a-140">È necessario chiudere e riaprire la finestra Sicurezza & preferenze di sistema  >  **tra** le approvazioni successive.</span><span class="sxs-lookup"><span data-stu-id="f1b6a-140">You must close and reopen the **System Preferences** > **Security & Privacy** window between subsequent approvals.</span></span> <span data-ttu-id="f1b6a-141">In caso contrario, macOS non visualizza l'approvazione successiva.</span><span class="sxs-lookup"><span data-stu-id="f1b6a-141">Otherwise, macOS will not display the next approval.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="f1b6a-142">C'è un timeout di un minuto prima che il prodotto torni all'estensione del kernel.</span><span class="sxs-lookup"><span data-stu-id="f1b6a-142">There is a one-minute timeout before the product falls back to the kernel extension.</span></span> <span data-ttu-id="f1b6a-143">In questo modo si garantisce che il dispositivo sia protetto.</span><span class="sxs-lookup"><span data-stu-id="f1b6a-143">This ensures that the device is protected.</span></span>
   >
   > <span data-ttu-id="f1b6a-144">Se è trascorso più di un minuto, riavviare il daemon riavviando il dispositivo o utilizzando per attivare di nuovo il flusso `sudo killall -9 wdavdaemon` di approvazione.</span><span class="sxs-lookup"><span data-stu-id="f1b6a-144">If more than one minute elapses, restart the daemon by rebooting the device or by using `sudo killall -9 wdavdaemon` to trigger the approval flow again.</span></span>

   ![Popup approvazione dell'estensione di sistema](images/mac-system-extension-approval.png)

   ![Finestra di approvazione dell'estensione di sistema](images/mac-system-extension-pref.png)

1. <span data-ttu-id="f1b6a-147">Dopo l'approvazione delle estensioni di sistema, macOS richiede un'approvazione per consentire il filtro del traffico di rete.</span><span class="sxs-lookup"><span data-stu-id="f1b6a-147">After the system extensions are approved, macOS prompts for an approval to allow network traffic to be filtered.</span></span> <span data-ttu-id="f1b6a-148">Fare clic **su Consenti**.</span><span class="sxs-lookup"><span data-stu-id="f1b6a-148">Click **Allow**.</span></span>

   ![Popup approvazione estensione di rete](images/mac-system-extension-filter.png)

#### <a name="grant-full-disk-access-to-the-endpoint-security-system-extension"></a><span data-ttu-id="f1b6a-150">Concedere l'accesso completo al disco all'estensione di sistema endpoint Security</span><span class="sxs-lookup"><span data-stu-id="f1b6a-150">Grant Full Disk Access to the Endpoint Security system extension</span></span>

<span data-ttu-id="f1b6a-151">Apri la **scheda Preferenze di** sistema Sicurezza & Privacy privacy e concedi Accesso completo al  >    >   **disco** all'estensione microsoft Defender **Endpoint Security.**</span><span class="sxs-lookup"><span data-stu-id="f1b6a-151">Open the **System Preferences** > **Security & Privacy** > **Privacy** tab and grant **Full Disk Access** to the **Microsoft Defender Endpoint Security Extension**.</span></span>

![Accesso completo al disco per l'estensione di sistema endpoint Security](images/mac-system-extension-fda.png)

#### <a name="reboot-your-device"></a><span data-ttu-id="f1b6a-153">Riavviare il dispositivo</span><span class="sxs-lookup"><span data-stu-id="f1b6a-153">Reboot your device</span></span>

<span data-ttu-id="f1b6a-154">Per l'applicazione delle modifiche, devi riavviare il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f1b6a-154">In order for the changes to take effect, you must reboot your device.</span></span>

#### <a name="verify-that-the-system-extensions-are-running"></a><span data-ttu-id="f1b6a-155">Verificare che le estensioni di sistema siano in esecuzione</span><span class="sxs-lookup"><span data-stu-id="f1b6a-155">Verify that the system extensions are running</span></span>

<span data-ttu-id="f1b6a-156">Dal terminale, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="f1b6a-156">From the Terminal, run the following command:</span></span>

```bash
mdatp health --field real_time_protection_subsystem
```

<span data-ttu-id="f1b6a-157">L'output `endpoint_security_extension` del terminale indica che il prodotto utilizza la funzionalità delle estensioni di sistema.</span><span class="sxs-lookup"><span data-stu-id="f1b6a-157">Terminal output `endpoint_security_extension` indicates the product is using the system extensions functionality.</span></span>

### <a name="managed-deployment"></a><span data-ttu-id="f1b6a-158">Distribuzione gestita</span><span class="sxs-lookup"><span data-stu-id="f1b6a-158">Managed deployment</span></span>

<span data-ttu-id="f1b6a-159">Fai riferimento a Nuovi profili di configurazione per macOS Catalina e alle versioni più recenti di [macOS: JAMF](mac-sysext-policies.md#jamf) per i nuovi profili di configurazione che devi distribuire per questa nuova funzionalità.</span><span class="sxs-lookup"><span data-stu-id="f1b6a-159">Refer to [New configuration profiles for macOS Catalina and newer versions of macOS: JAMF](mac-sysext-policies.md#jamf) for the new configuration profiles you must deploy for this new feature.</span></span>

<span data-ttu-id="f1b6a-160">Oltre a questi profili, assicurati di configurare i dispositivi di destinazione per il canale di aggiornamento veloce Insider, come descritto in [Prerequisiti per la distribuzione](#deployment-prerequisites).</span><span class="sxs-lookup"><span data-stu-id="f1b6a-160">In addition to those profiles, make sure to configure the target devices to be in the Insider Fast update channel, as described in [Deployment prerequisites](#deployment-prerequisites).</span></span>

<span data-ttu-id="f1b6a-161">In un dispositivo in cui vengono soddisfatti tutti i prerequisiti e sono stati distribuiti i nuovi profili di configurazione, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="f1b6a-161">On a device where all prerequisites are met and the new configuration profiles have been deployed, run the following command:</span></span>

```bash
$ mdatp health --field real_time_protection_subsystem
```

<span data-ttu-id="f1b6a-162">Se questo comando stampa `endpoint_security_extension` , il prodotto utilizza la funzionalità delle estensioni di sistema.</span><span class="sxs-lookup"><span data-stu-id="f1b6a-162">If this command prints `endpoint_security_extension`, the product is using the system extensions functionality.</span></span>

## <a name="validate-basic-scenarios"></a><span data-ttu-id="f1b6a-163">Convalidare gli scenari di base</span><span class="sxs-lookup"><span data-stu-id="f1b6a-163">Validate basic scenarios</span></span>

1. <span data-ttu-id="f1b6a-164">Testare il rilevamento EICAR (European Institute for Computer Antivirus Research).</span><span class="sxs-lookup"><span data-stu-id="f1b6a-164">Test European Institute for Computer Antivirus Research (EICAR) detection.</span></span> <span data-ttu-id="f1b6a-165">Da una finestra del terminale, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="f1b6a-165">From a Terminal window, run the following command:</span></span>

   ```bash
   curl -o eicar.txt https://secure.eicar.org/eicar.com.txt
   ```

   <span data-ttu-id="f1b6a-166">Verificare che il file EICAR sia in quarantena.</span><span class="sxs-lookup"><span data-stu-id="f1b6a-166">Verify that the EICAR file is quarantined.</span></span> <span data-ttu-id="f1b6a-167">È possibile verificare lo stato del file nella pagina Cronologia protezione nell'interfaccia utente o da una riga di comando utilizzando il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="f1b6a-167">You can verify the file's status on the Protection History page in the user interface, or from a command line by using the following command:</span></span>

    ```bash
    mdatp threat list
    ```

2. <span data-ttu-id="f1b6a-168">Testare lo scenario di rilevamento e risposta degli endpoint (EDR).</span><span class="sxs-lookup"><span data-stu-id="f1b6a-168">Test the Endpoint Detection and Response (EDR) DIY scenario.</span></span> <span data-ttu-id="f1b6a-169">Da una finestra del terminale, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="f1b6a-169">From a terminal window, run the following command:</span></span>

   ```bash
   curl -o "MDATP MacOS DIY.zip" https://aka.ms/mdatpmacosdiy
   ```

   <span data-ttu-id="f1b6a-170">Verificare che nel portale della pagina del computer per gli scenari EICAR ed EDR FAI-da-ti sia stato visualizzato due avvisi.</span><span class="sxs-lookup"><span data-stu-id="f1b6a-170">Validate that two alerts popped up in the portal on the machine page for EICAR and EDR DIY scenarios.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="f1b6a-171">Domande frequenti</span><span class="sxs-lookup"><span data-stu-id="f1b6a-171">Frequently asked questions</span></span>

- <span data-ttu-id="f1b6a-172">D: Perché viene ancora visualizzato `kernel_extension` quando si esegue `mdatp health --field real_time_protection_subsystem` ?</span><span class="sxs-lookup"><span data-stu-id="f1b6a-172">Q: Why am I still seeing `kernel_extension` when I run `mdatp health --field real_time_protection_subsystem`?</span></span>

    <span data-ttu-id="f1b6a-173">A: Fare riferimento alla sezione [Prerequisiti di](#deployment-prerequisites) distribuzione e verificare che tutti i prerequisiti siano soddisfatti.</span><span class="sxs-lookup"><span data-stu-id="f1b6a-173">A: Refer back to the [Deployment prerequisites](#deployment-prerequisites) section and double-check that all prerequisites are met.</span></span> <span data-ttu-id="f1b6a-174">Se tutti i prerequisiti sono soddisfatti, riavvia il dispositivo e controlla di nuovo.</span><span class="sxs-lookup"><span data-stu-id="f1b6a-174">If all prerequisites are met, restart your device and check again.</span></span>

- <span data-ttu-id="f1b6a-175">D: Quando sarà supportato macOS 11 Big Sur?</span><span class="sxs-lookup"><span data-stu-id="f1b6a-175">Q: When will macOS 11 Big Sur be supported?</span></span>

    <span data-ttu-id="f1b6a-176">A: Stiamo lavorando attivamente per aggiungere il supporto per macOS 11.</span><span class="sxs-lookup"><span data-stu-id="f1b6a-176">A: We are actively working on adding support for macOS 11.</span></span> <span data-ttu-id="f1b6a-177">Verranno poste ulteriori informazioni nella [pagina Novità.](mac-whatsnew.md)</span><span class="sxs-lookup"><span data-stu-id="f1b6a-177">We will post more information to the [What's new](mac-whatsnew.md) page.</span></span>
