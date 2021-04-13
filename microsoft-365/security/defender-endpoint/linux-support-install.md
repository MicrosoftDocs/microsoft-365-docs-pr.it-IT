---
title: Risolvere i problemi di installazione per Microsoft Defender ATP per Linux
ms.reviewer: ''
description: Risolvere i problemi di installazione per Microsoft Defender ATP per Linux
keywords: microsoft, defender, atp, linux, installazione
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
ms.openlocfilehash: 347528def6929dde200249cd9710f7ce33484c7f
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688814"
---
# <a name="troubleshoot-installation-issues-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="cf7cd-104">Risolvere i problemi di installazione per Microsoft Defender per Endpoint su Linux</span><span class="sxs-lookup"><span data-stu-id="cf7cd-104">Troubleshoot installation issues for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="cf7cd-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="cf7cd-105">**Applies to:**</span></span>
- [<span data-ttu-id="cf7cd-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="cf7cd-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="cf7cd-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cf7cd-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="cf7cd-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="cf7cd-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="cf7cd-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="cf7cd-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="verify-if-installation-succeeded"></a><span data-ttu-id="cf7cd-110">Verificare se l'installazione è riuscita</span><span class="sxs-lookup"><span data-stu-id="cf7cd-110">Verify if installation succeeded</span></span>

<span data-ttu-id="cf7cd-111">Un errore durante l'installazione può causare o meno un messaggio di errore significativo da parte di Gestione pacchetti.</span><span class="sxs-lookup"><span data-stu-id="cf7cd-111">An error in installation may or may not result in a meaningful error message by the package manager.</span></span> <span data-ttu-id="cf7cd-112">Per verificare se l'installazione è riuscita, ottenere e controllare i registri di installazione utilizzando:</span><span class="sxs-lookup"><span data-stu-id="cf7cd-112">To verify if the installation succeeded, obtain and check the installation logs using:</span></span>

 ```bash
 sudo journalctl | grep 'microsoft-mdatp'  > installation.log
```

```bash
 grep 'postinstall end' installation.log
```

```Output
 microsoft-mdatp-installer[102243]: postinstall end [2020-03-26 07:04:43OURCE +0000] 102216
 ```

<span data-ttu-id="cf7cd-113">Un output del comando precedente con data e ora di installazione corrette indica l'esito positivo.</span><span class="sxs-lookup"><span data-stu-id="cf7cd-113">An output from the previous command with correct date and time of installation indicates success.</span></span>

<span data-ttu-id="cf7cd-114">Controlla anche la [configurazione client per](linux-install-manually.md#client-configuration) verificare l'integrità del prodotto e rilevare il file di testo EICAR.</span><span class="sxs-lookup"><span data-stu-id="cf7cd-114">Also check the [Client configuration](linux-install-manually.md#client-configuration) to verify the health of the product and detect the EICAR text file.</span></span>

## <a name="make-sure-you-have-the-correct-package"></a><span data-ttu-id="cf7cd-115">Assicurati di avere il pacchetto corretto</span><span class="sxs-lookup"><span data-stu-id="cf7cd-115">Make sure you have the correct package</span></span>

<span data-ttu-id="cf7cd-116">Tenere presente che il pacchetto che si sta installando corrisponde alla distribuzione host e alla versione.</span><span class="sxs-lookup"><span data-stu-id="cf7cd-116">Please mind that the package you are installing is matching the host distribution and version.</span></span>

| <span data-ttu-id="cf7cd-117">pacchetto</span><span class="sxs-lookup"><span data-stu-id="cf7cd-117">package</span></span>                       | <span data-ttu-id="cf7cd-118">distribuzione</span><span class="sxs-lookup"><span data-stu-id="cf7cd-118">distribution</span></span>                             |
|-------------------------------|------------------------------------------|
| <span data-ttu-id="cf7cd-119">mdatp-rhel8. Linux.x86_64.rpm</span><span class="sxs-lookup"><span data-stu-id="cf7cd-119">mdatp-rhel8.Linux.x86_64.rpm</span></span>  | <span data-ttu-id="cf7cd-120">Oracle, RHEL e CentOS 8.x</span><span class="sxs-lookup"><span data-stu-id="cf7cd-120">Oracle, RHEL and CentOS 8.x</span></span>              |
| <span data-ttu-id="cf7cd-121">mdatp-sles12. Linux.x86_64.rpm</span><span class="sxs-lookup"><span data-stu-id="cf7cd-121">mdatp-sles12.Linux.x86_64.rpm</span></span> | <span data-ttu-id="cf7cd-122">SuSE Linux Enterprise Server 12.x</span><span class="sxs-lookup"><span data-stu-id="cf7cd-122">SuSE Linux Enterprise Server 12.x</span></span>        |
| <span data-ttu-id="cf7cd-123">mdatp-sles15. Linux.x86_64.rpm</span><span class="sxs-lookup"><span data-stu-id="cf7cd-123">mdatp-sles15.Linux.x86_64.rpm</span></span> | <span data-ttu-id="cf7cd-124">SuSE Linux Enterprise Server 15.x</span><span class="sxs-lookup"><span data-stu-id="cf7cd-124">SuSE Linux Enterprise Server 15.x</span></span>        |
| <span data-ttu-id="cf7cd-125">mdatp. Linux.x86_64.rpm</span><span class="sxs-lookup"><span data-stu-id="cf7cd-125">mdatp.Linux.x86_64.rpm</span></span>        | <span data-ttu-id="cf7cd-126">Oracle, RHEL e CentOS 7.x</span><span class="sxs-lookup"><span data-stu-id="cf7cd-126">Oracle, RHEL and CentOS 7.x</span></span>              |
| <span data-ttu-id="cf7cd-127">mdatp. Linux.x86_64.deb</span><span class="sxs-lookup"><span data-stu-id="cf7cd-127">mdatp.Linux.x86_64.deb</span></span>        | <span data-ttu-id="cf7cd-128">Debian e Ubuntu 16.04, 18.04 e 20.04</span><span class="sxs-lookup"><span data-stu-id="cf7cd-128">Debian and Ubuntu 16.04, 18.04 and 20.04</span></span> |

<span data-ttu-id="cf7cd-129">Per [la distribuzione](linux-install-manually.md)manuale, verificare che sia stata scelta la versione e la distribuzione corrette.</span><span class="sxs-lookup"><span data-stu-id="cf7cd-129">For [manual deployment](linux-install-manually.md), make sure the correct distro and version had been chosen.</span></span>

## <a name="installation-failed"></a><span data-ttu-id="cf7cd-130">Installazione non riuscita</span><span class="sxs-lookup"><span data-stu-id="cf7cd-130">Installation failed</span></span>

<span data-ttu-id="cf7cd-131">Verificare se il servizio mdatp è in esecuzione:</span><span class="sxs-lookup"><span data-stu-id="cf7cd-131">Check if the mdatp service is running:</span></span>

```bash
systemctl status mdatp
```
```Output
 ● mdatp.service - Microsoft Defender for Endpoint
   Loaded: loaded (/lib/systemd/system/mdatp.service; enabled; vendor preset: enabled)
   Active: active (running) since Thu 2020-03-26 10:37:30 IST; 23h ago
 Main PID: 1966 (wdavdaemon)
    Tasks: 105 (limit: 4915)
   CGroup: /system.slice/mdatp.service
           ├─1966 /opt/microsoft/mdatp/sbin/wdavdaemon
           ├─1967 /opt/microsoft/mdatp/sbin/wdavdaemon
           └─1968 /opt/microsoft/mdatp/sbin/wdavdaemon
 ```

## <a name="steps-to-troubleshoot-if-mdatp-service-isnt-running"></a><span data-ttu-id="cf7cd-132">Procedura per la risoluzione dei problemi se il servizio mdatp non è in esecuzione</span><span class="sxs-lookup"><span data-stu-id="cf7cd-132">Steps to troubleshoot if mdatp service isn't running</span></span>

1. <span data-ttu-id="cf7cd-133">Verificare se l'utente "mdatp" esiste:</span><span class="sxs-lookup"><span data-stu-id="cf7cd-133">Check if "mdatp" user exists:</span></span>

    ```bash
    id "mdatp"
    ```

    <span data-ttu-id="cf7cd-134">Se non è disponibile alcun output, eseguire</span><span class="sxs-lookup"><span data-stu-id="cf7cd-134">If there’s no output, run</span></span>

    ```bash
    sudo useradd --system --no-create-home --user-group --shell /usr/sbin/nologin mdatp
    ```

2. <span data-ttu-id="cf7cd-135">Prova ad abilitare e riavviare il servizio usando:</span><span class="sxs-lookup"><span data-stu-id="cf7cd-135">Try enabling and restarting the service using:</span></span>

    ```bash
    sudo systemctl enable mdatp
    ```

    ```bash
    sudo systemctl restart mdatp
    ```

3. <span data-ttu-id="cf7cd-136">Se mdatp.service non viene trovato durante l'esecuzione del comando precedente, eseguire:</span><span class="sxs-lookup"><span data-stu-id="cf7cd-136">If mdatp.service isn't found upon running the previous command, run:</span></span>

    ```bash
    sudo cp /opt/microsoft/mdatp/conf/mdatp.service <systemd_path>
    ```

    <span data-ttu-id="cf7cd-137">dove ```<systemd_path>``` è per le ```/lib/systemd/system``` distribuzioni di Ubuntu e Debian e ```/usr/lib/systemd/system``` per Rhel, CentOS, Oracle e SLES.</span><span class="sxs-lookup"><span data-stu-id="cf7cd-137">where ```<systemd_path>``` is ```/lib/systemd/system``` for Ubuntu and Debian distributions and ```/usr/lib/systemd/system``` for Rhel, CentOS, Oracle and SLES.</span></span>
   <span data-ttu-id="cf7cd-138">Eseguire di nuovo il passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="cf7cd-138">Then rerun step 2.</span></span>

4. <span data-ttu-id="cf7cd-139">Se i passaggi precedenti non funzionano, controlla se SELinux è installato e in modalità di applicazione.</span><span class="sxs-lookup"><span data-stu-id="cf7cd-139">If the above steps don’t work, check if SELinux is installed and in enforcing mode.</span></span> <span data-ttu-id="cf7cd-140">In tal caso, prova a impostarlo sulla modalità permissiva (preferibilmente) o disabilitata.</span><span class="sxs-lookup"><span data-stu-id="cf7cd-140">If so, try setting it to permissive (preferably) or disabled mode.</span></span> <span data-ttu-id="cf7cd-141">Può essere fatto impostando il parametro `SELINUX` su "permissive" o "disabled" nel `/etc/selinux/config` file, seguito dal riavvio.</span><span class="sxs-lookup"><span data-stu-id="cf7cd-141">It can be done by setting the parameter `SELINUX` to "permissive" or "disabled" in `/etc/selinux/config` file, followed by reboot.</span></span> <span data-ttu-id="cf7cd-142">Controlla la pagina man-of-selinux per altri dettagli.</span><span class="sxs-lookup"><span data-stu-id="cf7cd-142">Check the man-page of selinux for more details.</span></span>
<span data-ttu-id="cf7cd-143">Provare a riavviare il servizio mdatp utilizzando il passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="cf7cd-143">Now try restarting the mdatp service using step 2.</span></span> <span data-ttu-id="cf7cd-144">Ripristinare immediatamente la modifica della configurazione per motivi di sicurezza dopo averli provati e aver riavviato.</span><span class="sxs-lookup"><span data-stu-id="cf7cd-144">Revert the configuration change immediately though for security reasons after trying it and reboot.</span></span>

5. <span data-ttu-id="cf7cd-145">Se `/opt` la directory è un collegamento simbolico, crea un binding mount per `/opt/microsoft` .</span><span class="sxs-lookup"><span data-stu-id="cf7cd-145">If `/opt` directory is a symbolic link, create a bind mount for `/opt/microsoft`.</span></span>

6. <span data-ttu-id="cf7cd-146">Verificare che il daemon abbia l'autorizzazione eseguibile.</span><span class="sxs-lookup"><span data-stu-id="cf7cd-146">Ensure that the daemon has executable permission.</span></span>

    ```bash
    ls -l /opt/microsoft/mdatp/sbin/wdavdaemon
    ```

    ```Output
    -rwxr-xr-x 2 root root 15502160 Mar  3 04:47 /opt/microsoft/mdatp/sbin/wdavdaemon
    ```

    <span data-ttu-id="cf7cd-147">Se il daemon non dispone di autorizzazioni eseguibili, rendilo eseguibile usando:</span><span class="sxs-lookup"><span data-stu-id="cf7cd-147">If the daemon doesn't have executable permissions, make it executable using:</span></span>

    ```bash
    sudo chmod 0755 /opt/microsoft/mdatp/sbin/wdavdaemon
    ```

    <span data-ttu-id="cf7cd-148">e riprovare a eseguire il passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="cf7cd-148">and retry running step 2.</span></span>

7. <span data-ttu-id="cf7cd-149">Assicurati che il file system contenente wdavdaemon non sia montato con "noexec".</span><span class="sxs-lookup"><span data-stu-id="cf7cd-149">Ensure that the file system containing wdavdaemon isn't mounted with "noexec".</span></span>

## <a name="if-mdatp-service-is-running-but-eicar-text-file-detection-doesnt-work"></a><span data-ttu-id="cf7cd-150">Se il servizio mdatp è in esecuzione, ma il rilevamento dei file di testo EICAR non funziona</span><span class="sxs-lookup"><span data-stu-id="cf7cd-150">If mdatp service is running, but EICAR text file detection doesn't work</span></span>

1. <span data-ttu-id="cf7cd-151">Controllare il tipo di file system usando:</span><span class="sxs-lookup"><span data-stu-id="cf7cd-151">Check the file system type using:</span></span>

    ```bash
    findmnt -T <path_of_EICAR_file>
    ```

    <span data-ttu-id="cf7cd-152">I file system attualmente supportati per le attività di accesso sono elencati [qui.](microsoft-defender-endpoint-linux.md#system-requirements)</span><span class="sxs-lookup"><span data-stu-id="cf7cd-152">Currently supported file systems for on-access activity are listed [here](microsoft-defender-endpoint-linux.md#system-requirements).</span></span> <span data-ttu-id="cf7cd-153">I file esterni a questi file system non verranno analizzati.</span><span class="sxs-lookup"><span data-stu-id="cf7cd-153">Any files outside these file systems won't be scanned.</span></span>

## <a name="command-line-tool-mdatp-isnt-working"></a><span data-ttu-id="cf7cd-154">Lo strumento da riga di comando "mdatp" non funziona</span><span class="sxs-lookup"><span data-stu-id="cf7cd-154">Command-line tool “mdatp” isn't working</span></span>

1. <span data-ttu-id="cf7cd-155">Se l'esecuzione dello strumento da riga di comando `mdatp` restituisce un `command not found` errore, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="cf7cd-155">If running the command-line tool `mdatp` gives an error `command not found`, run the following command:</span></span>

    ```bash
    sudo ln -sf /opt/microsoft/mdatp/sbin/wdavdaemonclient /usr/bin/mdatp
    ```

    <span data-ttu-id="cf7cd-156">e riprovare.</span><span class="sxs-lookup"><span data-stu-id="cf7cd-156">and try again.</span></span>

    <span data-ttu-id="cf7cd-157">Se nessuno dei passaggi precedenti è utile, raccogliere i log di diagnostica:</span><span class="sxs-lookup"><span data-stu-id="cf7cd-157">If none of the above steps help, collect the diagnostic logs:</span></span>

    ```bash
    sudo mdatp diagnostic create
    ```

    ```Output
    Diagnostic file created: <path to file>
    ```

    <span data-ttu-id="cf7cd-158">Il percorso di un file ZIP contenente i registri verrà visualizzato come output.</span><span class="sxs-lookup"><span data-stu-id="cf7cd-158">Path to a zip file that contains the logs will be displayed as an output.</span></span> <span data-ttu-id="cf7cd-159">Contattare il supporto tecnico con questi log.</span><span class="sxs-lookup"><span data-stu-id="cf7cd-159">Reach out to our customer support with these logs.</span></span>
