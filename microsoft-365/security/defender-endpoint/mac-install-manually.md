---
title: Distribuzione manuale per Microsoft Defender for Endpoint per macOS
description: Installare Manualmente Microsoft Defender per Endpoint per macOS dalla riga di comando.
keywords: microsoft, defender, atp, mac, installazione, distribuire, disinstallazione, intune, jamf, macos, catalina, mojave, high sierra
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
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
ms.technology: mde
ms.openlocfilehash: 044a3d48dc350a5663a27ab3c16c2da7a5e3f3f1
ms.sourcegitcommit: a965c498e6b3890877f895d5197898b306092813
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/26/2021
ms.locfileid: "51379443"
---
# <a name="manual-deployment-for-microsoft-defender-for-endpoint-for-macos"></a><span data-ttu-id="a9fab-104">Distribuzione manuale per Microsoft Defender for Endpoint per macOS</span><span class="sxs-lookup"><span data-stu-id="a9fab-104">Manual deployment for Microsoft Defender for Endpoint for macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a9fab-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="a9fab-105">**Applies to:**</span></span>
- [<span data-ttu-id="a9fab-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="a9fab-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a9fab-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a9fab-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="a9fab-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="a9fab-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a9fab-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="a9fab-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="a9fab-110">Questo argomento descrive come distribuire Manualmente Microsoft Defender for Endpoint per macOS.</span><span class="sxs-lookup"><span data-stu-id="a9fab-110">This topic describes how to deploy Microsoft Defender for Endpoint for macOS manually.</span></span> <span data-ttu-id="a9fab-111">Una distribuzione corretta richiede il completamento di tutti i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="a9fab-111">A successful deployment requires the completion of all of the following steps:</span></span>
- [<span data-ttu-id="a9fab-112">Scaricare i pacchetti di installazione e onboarding</span><span class="sxs-lookup"><span data-stu-id="a9fab-112">Download installation and onboarding packages</span></span>](#download-installation-and-onboarding-packages)
- [<span data-ttu-id="a9fab-113">Installazione dell'applicazione (macOS 10.15 e versioni precedenti)</span><span class="sxs-lookup"><span data-stu-id="a9fab-113">Application installation (macOS 10.15 and older versions)</span></span>](#application-installation-macos-1015-and-older-versions)
- [<span data-ttu-id="a9fab-114">Installazione dell'applicazione (macOS 11 e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="a9fab-114">Application installation (macOS 11 and newer versions)</span></span>](#application-installation-macos-11-and-newer-versions)
- [<span data-ttu-id="a9fab-115">Configurazione client</span><span class="sxs-lookup"><span data-stu-id="a9fab-115">Client configuration</span></span>](#client-configuration)

## <a name="prerequisites-and-system-requirements"></a><span data-ttu-id="a9fab-116">Prerequisiti e requisiti di sistema</span><span class="sxs-lookup"><span data-stu-id="a9fab-116">Prerequisites and system requirements</span></span>

<span data-ttu-id="a9fab-117">Prima di iniziare, vedi la pagina principale di [Microsoft Defender per Endpoint per macOS](microsoft-defender-endpoint-mac.md) per una descrizione dei prerequisiti e dei requisiti di sistema per la versione software corrente.</span><span class="sxs-lookup"><span data-stu-id="a9fab-117">Before you get started, see [the main Microsoft Defender for Endpoint for macOS page](microsoft-defender-endpoint-mac.md) for a description of prerequisites and system requirements for the current software version.</span></span>

## <a name="download-installation-and-onboarding-packages"></a><span data-ttu-id="a9fab-118">Scaricare i pacchetti di installazione e onboarding</span><span class="sxs-lookup"><span data-stu-id="a9fab-118">Download installation and onboarding packages</span></span>

<span data-ttu-id="a9fab-119">Scaricare i pacchetti di installazione e onboarding da Microsoft Defender Security Center:</span><span class="sxs-lookup"><span data-stu-id="a9fab-119">Download the installation and onboarding packages from Microsoft Defender Security Center:</span></span>

1. <span data-ttu-id="a9fab-120">In Microsoft Defender Security Center, vai a **Impostazioni > Gestione dispositivi > onboarding**.</span><span class="sxs-lookup"><span data-stu-id="a9fab-120">In Microsoft Defender Security Center, go to **Settings > Device Management > Onboarding**.</span></span>
2. <span data-ttu-id="a9fab-121">Nella sezione 1 della pagina imposta il sistema operativo su **macOS** e il metodo di distribuzione su **Script locale.**</span><span class="sxs-lookup"><span data-stu-id="a9fab-121">In Section 1 of the page, set operating system to **macOS** and Deployment method to **Local script**.</span></span>
3. <span data-ttu-id="a9fab-122">Nella sezione 2 della pagina seleziona **Scarica pacchetto di installazione.**</span><span class="sxs-lookup"><span data-stu-id="a9fab-122">In Section 2 of the page, select **Download installation package**.</span></span> <span data-ttu-id="a9fab-123">Salvarlo come wdav.pkg in una directory locale.</span><span class="sxs-lookup"><span data-stu-id="a9fab-123">Save it as wdav.pkg to a local directory.</span></span>
4. <span data-ttu-id="a9fab-124">Nella sezione 2 della pagina seleziona **Scarica pacchetto di onboarding.**</span><span class="sxs-lookup"><span data-stu-id="a9fab-124">In Section 2 of the page, select **Download onboarding package**.</span></span> <span data-ttu-id="a9fab-125">Salvarlo come WindowsDefenderATPOnboardingPackage.zip nella stessa directory.</span><span class="sxs-lookup"><span data-stu-id="a9fab-125">Save it as WindowsDefenderATPOnboardingPackage.zip to the same directory.</span></span>

    ![Screenshot di Microsoft Defender Security Center](images/atp-portal-onboarding-page.png)

5. <span data-ttu-id="a9fab-127">Da un prompt dei comandi, verificare di disporre dei due file.</span><span class="sxs-lookup"><span data-stu-id="a9fab-127">From a command prompt, verify that you have the two files.</span></span>
    
## <a name="application-installation-macos-1015-and-older-versions"></a><span data-ttu-id="a9fab-128">Installazione dell'applicazione (macOS 10.15 e versioni precedenti)</span><span class="sxs-lookup"><span data-stu-id="a9fab-128">Application installation (macOS 10.15 and older versions)</span></span>

<span data-ttu-id="a9fab-129">Per completare questo processo, devi disporre dei privilegi di amministratore nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a9fab-129">To complete this process, you must have admin privileges on the device.</span></span>

1. <span data-ttu-id="a9fab-130">Passa al file wdav.pkg scaricato nel Finder e aprilo.</span><span class="sxs-lookup"><span data-stu-id="a9fab-130">Navigate to the downloaded wdav.pkg in Finder and open it.</span></span>

    ![Screenshot1 per l'installazione dell'app](images/mdatp-28-appinstall.png)

2. <span data-ttu-id="a9fab-132">Selezionare **Continua**, accettare le condizioni di licenza e immettere la password quando richiesto.</span><span class="sxs-lookup"><span data-stu-id="a9fab-132">Select **Continue**, agree with the License terms, and enter the password when prompted.</span></span>

    ![Screenshot2 per l'installazione dell'app](images/mdatp-29-appinstalllogin.png)

   > [!IMPORTANT]
   > <span data-ttu-id="a9fab-134">Ti verrà richiesto di consentire l'installazione di un driver di Microsoft ("Estensione di sistema bloccata" o "L'installazione è in attesa" o entrambe.</span><span class="sxs-lookup"><span data-stu-id="a9fab-134">You will be prompted to allow a driver from Microsoft to be installed (either "System Extension Blocked" or "Installation is on hold" or both.</span></span> <span data-ttu-id="a9fab-135">Il driver deve essere autorizzato a essere installato.</span><span class="sxs-lookup"><span data-stu-id="a9fab-135">The driver must be allowed to be installed.</span></span>

   ![Screenshot3 per l'installazione dell'app](images/mdatp-30-systemextension.png)

3. <span data-ttu-id="a9fab-137">Seleziona **Apri preferenze di sicurezza** o Apri preferenze di sistema > Sicurezza & **Privacy.**</span><span class="sxs-lookup"><span data-stu-id="a9fab-137">Select **Open Security Preferences** or **Open System Preferences > Security & Privacy**.</span></span> <span data-ttu-id="a9fab-138">Selezionare **Consenti**:</span><span class="sxs-lookup"><span data-stu-id="a9fab-138">Select **Allow**:</span></span>

    ![Screenshot della finestra Sicurezza e privacy](images/mdatp-31-securityprivacysettings.png)

   <span data-ttu-id="a9fab-140">L'installazione procede.</span><span class="sxs-lookup"><span data-stu-id="a9fab-140">The installation proceeds.</span></span>

   > [!CAUTION]
   > <span data-ttu-id="a9fab-141">Se non si seleziona **Consenti,** l'installazione procederà dopo 5 minuti.</span><span class="sxs-lookup"><span data-stu-id="a9fab-141">If you don't select **Allow**, the installation will proceed after 5 minutes.</span></span> <span data-ttu-id="a9fab-142">Microsoft Defender for Endpoint verrà caricato, ma alcune funzionalità, ad esempio la protezione in tempo reale, verranno disabilitate.</span><span class="sxs-lookup"><span data-stu-id="a9fab-142">Microsoft Defender for Endpoint will be loaded, but some features, such as real-time protection, will be disabled.</span></span> <span data-ttu-id="a9fab-143">Per informazioni su come risolvere [questo problema,](mac-support-kext.md) vedi Risolvere i problemi relativi alle estensioni del kernel.</span><span class="sxs-lookup"><span data-stu-id="a9fab-143">See [Troubleshoot kernel extension issues](mac-support-kext.md) for information on how to resolve this.</span></span>

> [!NOTE]
> <span data-ttu-id="a9fab-144">macOS potrebbe richiedere di riavviare il dispositivo alla prima installazione di Microsoft Defender per Endpoint.</span><span class="sxs-lookup"><span data-stu-id="a9fab-144">macOS may request to reboot the device upon the first installation of Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="a9fab-145">La protezione in tempo reale non sarà disponibile fino al riavvio del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a9fab-145">Real-time protection will not be available until the device is rebooted.</span></span>

## <a name="application-installation-macos-11-and-newer-versions"></a><span data-ttu-id="a9fab-146">Installazione dell'applicazione (macOS 11 e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="a9fab-146">Application installation (macOS 11 and newer versions)</span></span>

<span data-ttu-id="a9fab-147">Per completare questo processo, devi disporre dei privilegi di amministratore nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a9fab-147">To complete this process, you must have admin privileges on the device.</span></span>

1. <span data-ttu-id="a9fab-148">Passa al file wdav.pkg scaricato nel Finder e aprilo.</span><span class="sxs-lookup"><span data-stu-id="a9fab-148">Navigate to the downloaded wdav.pkg in Finder and open it.</span></span>

    ![Screenshot4 per l'installazione dell'app](images/big-sur-install-1.png)

2. <span data-ttu-id="a9fab-150">Selezionare **Continua**, accettare le condizioni di licenza e immettere la password quando richiesto.</span><span class="sxs-lookup"><span data-stu-id="a9fab-150">Select **Continue**, agree with the License terms, and enter the password when prompted.</span></span>

3. <span data-ttu-id="a9fab-151">Al termine del processo di installazione, verrà promosso per approvare le estensioni di sistema utilizzate dal prodotto.</span><span class="sxs-lookup"><span data-stu-id="a9fab-151">At the end of the installation process, you'll be promoted to approve the system extensions used by the product.</span></span> <span data-ttu-id="a9fab-152">Selezionare **Apri preferenze di sicurezza.**</span><span class="sxs-lookup"><span data-stu-id="a9fab-152">Select **Open Security Preferences**.</span></span>

    ![Approvazione dell'estensione di sistema](images/big-sur-install-2.png)

4. <span data-ttu-id="a9fab-154">Nella finestra **Sicurezza & Privacy** seleziona **Consenti.**</span><span class="sxs-lookup"><span data-stu-id="a9fab-154">From the **Security & Privacy** window, select **Allow**.</span></span>

    ![Preferenze di sicurezza delle estensioni di sistema1](images/big-sur-install-3.png)

5. <span data-ttu-id="a9fab-156">Ripeti i passaggi 3 & 4 per tutte le estensioni di sistema distribuite con Microsoft Defender per Endpoint per Mac.</span><span class="sxs-lookup"><span data-stu-id="a9fab-156">Repeat steps 3 & 4 for all system extensions distributed with Microsoft Defender for Endpoint for Mac.</span></span>

6. <span data-ttu-id="a9fab-157">Come parte delle funzionalità di rilevamento e risposta degli endpoint, Microsoft Defender per Endpoint per Mac esamina il traffico socket e segnala queste informazioni al portale di Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="a9fab-157">As part of the Endpoint Detection and Response capabilities, Microsoft Defender for Endpoint for Mac inspects socket traffic and reports this information to the Microsoft Defender Security Center portal.</span></span> <span data-ttu-id="a9fab-158">Quando viene richiesto di concedere a Microsoft Defender le autorizzazioni per Endpoint per filtrare il traffico di rete, selezionare **Consenti**.</span><span class="sxs-lookup"><span data-stu-id="a9fab-158">When prompted to grant Microsoft Defender for Endpoint permissions to filter network traffic, select **Allow**.</span></span>

    ![Preferenze di sicurezza delle estensioni di sistema2](images/big-sur-install-4.png)

7. <span data-ttu-id="a9fab-160">Aprire **Preferenze di** sistema Sicurezza & Privacy e passare alla scheda Privacy. Concedere l'autorizzazione Accesso completo al disco a Microsoft Defender  >   **ATP** e  Microsoft Defender **ATP Endpoint Security Extension**. </span><span class="sxs-lookup"><span data-stu-id="a9fab-160">Open **System Preferences** > **Security & Privacy** and navigate to the **Privacy** tab. Grant **Full Disk Access** permission to **Microsoft Defender ATP** and **Microsoft Defender ATP Endpoint Security Extension**.</span></span>

    ![Accesso completo al disco](images/big-sur-install-5.png)

## <a name="client-configuration"></a><span data-ttu-id="a9fab-162">Configurazione client</span><span class="sxs-lookup"><span data-stu-id="a9fab-162">Client configuration</span></span>

1. <span data-ttu-id="a9fab-163">Copia wdav.pkg e MicrosoftDefenderATPOnboardingMacOs.py nel dispositivo in cui distribuisci Microsoft Defender per Endpoint per macOS.</span><span class="sxs-lookup"><span data-stu-id="a9fab-163">Copy wdav.pkg and MicrosoftDefenderATPOnboardingMacOs.py to the device where you deploy Microsoft Defender for Endpoint for macOS.</span></span>

    <span data-ttu-id="a9fab-164">Il dispositivo client non è associato a orgId.</span><span class="sxs-lookup"><span data-stu-id="a9fab-164">The client device isn't associated with orgId.</span></span> <span data-ttu-id="a9fab-165">Si noti che *l'attributo orgId* è vuoto.</span><span class="sxs-lookup"><span data-stu-id="a9fab-165">Note that the *orgId* attribute is blank.</span></span>

    ```bash
    mdatp health --field org_id
    ```

2. <span data-ttu-id="a9fab-166">Eseguire lo script Python per installare il file di configurazione:</span><span class="sxs-lookup"><span data-stu-id="a9fab-166">Run the Python script to install the configuration file:</span></span>

    ```bash
    /usr/bin/python MicrosoftDefenderATPOnboardingMacOs.py
    ```

3. <span data-ttu-id="a9fab-167">Verifica che il dispositivo sia ora associato all'organizzazione e segnala un *orgId valido:*</span><span class="sxs-lookup"><span data-stu-id="a9fab-167">Verify that the device is now associated with your organization and reports a valid *orgId*:</span></span>

    ```bash
    mdatp health --field org_id
    ```

<span data-ttu-id="a9fab-168">Dopo l'installazione, vedrai l'icona di Microsoft Defender nella barra di stato di macOS nell'angolo in alto a destra.</span><span class="sxs-lookup"><span data-stu-id="a9fab-168">After installation, you'll see the Microsoft Defender icon in the macOS status bar in the top-right corner.</span></span>

   ![Icona di Microsoft Defender nella schermata della barra di stato](images/mdatp-icon-bar.png)
   

## <a name="how-to-allow-full-disk-access"></a><span data-ttu-id="a9fab-170">Come consentire l'accesso completo al disco</span><span class="sxs-lookup"><span data-stu-id="a9fab-170">How to Allow Full Disk Access</span></span>

> [!CAUTION]
> <span data-ttu-id="a9fab-171">macOS 10.15 (Catalina) contiene nuovi miglioramenti alla sicurezza e alla privacy.</span><span class="sxs-lookup"><span data-stu-id="a9fab-171">macOS 10.15 (Catalina) contains new security and privacy enhancements.</span></span> <span data-ttu-id="a9fab-172">A partire da questa versione, per impostazione predefinita, le applicazioni non sono in grado di accedere a determinate posizioni sul disco (ad esempio Documenti, Download, Desktop e così via) senza il consenso esplicito.</span><span class="sxs-lookup"><span data-stu-id="a9fab-172">Beginning with this version, by default, applications are not able to access certain locations on disk (such as Documents, Downloads, Desktop, etc.) without explicit consent.</span></span> <span data-ttu-id="a9fab-173">In assenza di questo consenso, Microsoft Defender for Endpoint non è in grado di proteggere completamente il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a9fab-173">In the absence of this consent, Microsoft Defender for Endpoint is not able to fully protect your device.</span></span>

<span data-ttu-id="a9fab-174">Per concedere il consenso, aprire Preferenze di sistema -> Sicurezza & Privacy -> Privacy -> Accesso completo al disco.</span><span class="sxs-lookup"><span data-stu-id="a9fab-174">To grant consent, open System Preferences -> Security & Privacy -> Privacy -> Full Disk Access.</span></span> <span data-ttu-id="a9fab-175">Fare clic sull'icona di blocco per apportare modifiche nella parte inferiore della finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="a9fab-175">Click the lock icon to make changes (bottom of the dialog box).</span></span> <span data-ttu-id="a9fab-176">Seleziona Microsoft Defender per Endpoint.</span><span class="sxs-lookup"><span data-stu-id="a9fab-176">Select Microsoft Defender for Endpoint.</span></span>

## <a name="logging-installation-issues"></a><span data-ttu-id="a9fab-177">Registrazione dei problemi di installazione</span><span class="sxs-lookup"><span data-stu-id="a9fab-177">Logging installation issues</span></span>

<span data-ttu-id="a9fab-178">Per [ulteriori informazioni su](mac-resources.md#logging-installation-issues) come trovare il registro generato automaticamente creato dal programma di installazione quando si verifica un errore, vedere Registrazione dei problemi di installazione.</span><span class="sxs-lookup"><span data-stu-id="a9fab-178">See [Logging installation issues](mac-resources.md#logging-installation-issues) for more information on how to find the automatically generated log that is created by the installer when an error occurs.</span></span>

## <a name="uninstallation"></a><span data-ttu-id="a9fab-179">Disinstallazione</span><span class="sxs-lookup"><span data-stu-id="a9fab-179">Uninstallation</span></span>

<span data-ttu-id="a9fab-180">Vedi [Disinstallazione](mac-resources.md#uninstalling) per informazioni dettagliate su come rimuovere Microsoft Defender per Endpoint per macOS dai dispositivi client.</span><span class="sxs-lookup"><span data-stu-id="a9fab-180">See [Uninstalling](mac-resources.md#uninstalling) for details on how to remove Microsoft Defender for Endpoint for macOS from client devices.</span></span>
