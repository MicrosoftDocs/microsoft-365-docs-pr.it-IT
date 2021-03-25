---
title: Individuazione proxy statico di Microsoft Defender ATP per Linux
ms.reviewer: ''
description: Descrive come configurare Microsoft Defender ATP per l'individuazione di proxy statici.
keywords: microsoft, defender, atp, linux, installazione, proxy
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
ms.openlocfilehash: 841e5d5169469edb804514458760c5f52e66edaa
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51065717"
---
# <a name="configure-microsoft-defender-for-endpoint-for-linux-for-static-proxy-discovery"></a><span data-ttu-id="0693a-104">Configurare Microsoft Defender per Endpoint per Linux per l'individuazione di proxy statici</span><span class="sxs-lookup"><span data-stu-id="0693a-104">Configure Microsoft Defender for Endpoint for Linux for static proxy discovery</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="0693a-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="0693a-105">**Applies to:**</span></span>
- [<span data-ttu-id="0693a-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="0693a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="0693a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0693a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="0693a-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="0693a-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="0693a-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="0693a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="0693a-110">Microsoft Defender ATP può individuare un server proxy utilizzando la ```HTTPS_PROXY``` variabile di ambiente.</span><span class="sxs-lookup"><span data-stu-id="0693a-110">Microsoft Defender ATP can discover a proxy server using the ```HTTPS_PROXY``` environment variable.</span></span> <span data-ttu-id="0693a-111">Questa impostazione deve essere **configurata sia al** momento dell'installazione che dopo l'installazione del prodotto.</span><span class="sxs-lookup"><span data-stu-id="0693a-111">This setting must be configured **both** at installation time and after the product has been installed.</span></span>

## <a name="installation-time-configuration"></a><span data-ttu-id="0693a-112">Configurazione del tempo di installazione</span><span class="sxs-lookup"><span data-stu-id="0693a-112">Installation time configuration</span></span>

<span data-ttu-id="0693a-113">Durante l'installazione, ```HTTPS_PROXY``` la variabile di ambiente deve essere passata a Gestione pacchetti.</span><span class="sxs-lookup"><span data-stu-id="0693a-113">During installation, the ```HTTPS_PROXY``` environment variable must be passed to the package manager.</span></span> <span data-ttu-id="0693a-114">Gestione pacchetti può leggere questa variabile in uno dei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="0693a-114">The package manager can read this variable in any of the following ways:</span></span>

- <span data-ttu-id="0693a-115">La ```HTTPS_PROXY``` variabile è definita nella riga ```/etc/environment``` seguente:</span><span class="sxs-lookup"><span data-stu-id="0693a-115">The ```HTTPS_PROXY``` variable is defined in ```/etc/environment``` with the following line:</span></span>

    ```bash
    HTTPS_PROXY="http://proxy.server:port/"
    ```

- <span data-ttu-id="0693a-116">La variabile è definita nella configurazione globale `HTTPS_PROXY` di Gestione pacchetti.</span><span class="sxs-lookup"><span data-stu-id="0693a-116">The `HTTPS_PROXY` variable is defined in the package manager global configuration.</span></span> <span data-ttu-id="0693a-117">Ad esempio, in Ubuntu 18.04, è possibile aggiungere la riga seguente a `/etc/apt/apt.conf.d/proxy.conf` :</span><span class="sxs-lookup"><span data-stu-id="0693a-117">For example, in Ubuntu 18.04, you can add the following line to `/etc/apt/apt.conf.d/proxy.conf`:</span></span>
  
    ```bash
    Acquire::https::Proxy "http://proxy.server:port/";
    ```

    > [!CAUTION]
    > <span data-ttu-id="0693a-118">Si noti che i due metodi precedenti potrebbero definire il proxy da utilizzare per altre applicazioni nel sistema.</span><span class="sxs-lookup"><span data-stu-id="0693a-118">Note that above two methods could define the proxy to use for other applications on your system.</span></span> <span data-ttu-id="0693a-119">Utilizzare questo metodo con cautela o solo se si tratta di una configurazione generalmente globale.</span><span class="sxs-lookup"><span data-stu-id="0693a-119">Use this method with caution, or only if this is meant to be a generally global configuration.</span></span>
  
- <span data-ttu-id="0693a-120">La `HTTPS_PROXY` variabile viene anteposta ai comandi di installazione o disinstallazione.</span><span class="sxs-lookup"><span data-stu-id="0693a-120">The `HTTPS_PROXY` variable is prepended to the installation or uninstallation commands.</span></span> <span data-ttu-id="0693a-121">Ad esempio, con gestione pacchetti APT, anteporre la variabile come segue durante l'installazione di Microsoft Defender per Endpoint:</span><span class="sxs-lookup"><span data-stu-id="0693a-121">For example, with the APT package manager, prepend the variable as follows when installing Microsoft Defender for Endpoint:</span></span> 

    ```bash  
    HTTPS_PROXY="http://proxy.server:port/" apt install mdatp
    ```

    > [!NOTE]
    > <span data-ttu-id="0693a-122">Non aggiungere sudo tra la definizione della variabile di ambiente e apt, altrimenti la variabile non verrà propagata.</span><span class="sxs-lookup"><span data-stu-id="0693a-122">Do not add sudo between the environment variable definition and apt, otherwise the variable will not be propagated.</span></span>

<span data-ttu-id="0693a-123">La `HTTPS_PROXY` variabile di ambiente può essere definita in modo analogo durante la disinstallazione.</span><span class="sxs-lookup"><span data-stu-id="0693a-123">The `HTTPS_PROXY` environment variable may similarly be defined during uninstallation.</span></span>

<span data-ttu-id="0693a-124">Si noti che l'installazione e la disinstallazione non avranno necessariamente esito negativo se è necessario un proxy ma non è configurato.</span><span class="sxs-lookup"><span data-stu-id="0693a-124">Note that installation and uninstallation will not necessarily fail if a proxy is required but not configured.</span></span> <span data-ttu-id="0693a-125">Tuttavia, la telemetria non verrà inviata e l'operazione potrebbe richiedere molto più tempo a causa dei timeout di rete.</span><span class="sxs-lookup"><span data-stu-id="0693a-125">However, telemetry will not be submitted, and the operation could take much longer due to network timeouts.</span></span>

## <a name="post-installation-configuration"></a><span data-ttu-id="0693a-126">Configurazione post-installazione</span><span class="sxs-lookup"><span data-stu-id="0693a-126">Post installation configuration</span></span>
  
<span data-ttu-id="0693a-127">Dopo l'installazione, `HTTPS_PROXY` la variabile di ambiente deve essere definita nel file del servizio Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="0693a-127">After installation, the `HTTPS_PROXY` environment variable must be defined in the Defender for Endpoint service file.</span></span> <span data-ttu-id="0693a-128">A tale scopo, apri `/lib/systemd/system/mdatp.service` in un editor di testo durante l'esecuzione come utente radice.</span><span class="sxs-lookup"><span data-stu-id="0693a-128">To do this, open `/lib/systemd/system/mdatp.service` in a text editor while running as the root user.</span></span> <span data-ttu-id="0693a-129">È quindi possibile propagare la variabile al servizio in uno dei due modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="0693a-129">You can then propagate the variable to the service in one of two ways:</span></span>

- <span data-ttu-id="0693a-130">Rimuovere il commento dalla riga `#Environment="HTTPS_PROXY=http://address:port"` e specificare l'indirizzo proxy statico.</span><span class="sxs-lookup"><span data-stu-id="0693a-130">Uncomment the line `#Environment="HTTPS_PROXY=http://address:port"` and specify your static proxy address.</span></span>

- <span data-ttu-id="0693a-131">Aggiungere una riga `EnvironmentFile=/path/to/env/file` .</span><span class="sxs-lookup"><span data-stu-id="0693a-131">Add a line `EnvironmentFile=/path/to/env/file`.</span></span> <span data-ttu-id="0693a-132">Questo percorso può puntare a o a un file personalizzato, uno dei quali `/etc/environment` deve aggiungere la riga seguente:</span><span class="sxs-lookup"><span data-stu-id="0693a-132">This path can point to `/etc/environment` or a custom file, either of which needs to add the following line:</span></span>
  
    ```bash
    HTTPS_PROXY="http://proxy.server:port/"
    ```

<span data-ttu-id="0693a-133">Dopo aver modificato il `mdatp.service` file, salvarlo e chiuderlo.</span><span class="sxs-lookup"><span data-stu-id="0693a-133">After modifying the `mdatp.service` file, save and close it.</span></span> <span data-ttu-id="0693a-134">Riavviare il servizio in modo che le modifiche possano essere applicate.</span><span class="sxs-lookup"><span data-stu-id="0693a-134">Restart the service so the changes can be applied.</span></span> <span data-ttu-id="0693a-135">In Ubuntu, questo implica due comandi:</span><span class="sxs-lookup"><span data-stu-id="0693a-135">In Ubuntu, this involves two commands:</span></span>  

```bash
systemctl daemon-reload; systemctl restart mdatp
```