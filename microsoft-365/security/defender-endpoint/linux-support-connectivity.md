---
title: Risolvere i problemi di connettività cloud per Microsoft Defender per Endpoint su Linux
ms.reviewer: ''
description: Risolvere i problemi di connettività cloud per Microsoft Defender per Endpoint su Linux
keywords: microsoft, defender, atp, linux, cloud, connettività, comunicazione
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 985e4c39c60600da892c010b6ee26e9c98bb0611
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903167"
---
# <a name="troubleshoot-cloud-connectivity-issues-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="f9499-104">Risolvere i problemi di connettività cloud per Microsoft Defender per Endpoint su Linux</span><span class="sxs-lookup"><span data-stu-id="f9499-104">Troubleshoot cloud connectivity issues for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f9499-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="f9499-105">**Applies to:**</span></span>
- [<span data-ttu-id="f9499-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="f9499-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f9499-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f9499-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f9499-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="f9499-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="f9499-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="f9499-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="run-the-connectivity-test"></a><span data-ttu-id="f9499-110">Eseguire il test di connettività</span><span class="sxs-lookup"><span data-stu-id="f9499-110">Run the connectivity test</span></span>

<span data-ttu-id="f9499-111">Per verificare se Defender per Endpoint per Linux può comunicare con il cloud con le impostazioni di rete correnti, eseguire un test di connettività dalla riga di comando:</span><span class="sxs-lookup"><span data-stu-id="f9499-111">To test if Defender for Endpoint for Linux can communicate to the cloud with the current network settings, run a connectivity test from the command line:</span></span>

```bash
mdatp connectivity test
```

<span data-ttu-id="f9499-112">output previsto:</span><span class="sxs-lookup"><span data-stu-id="f9499-112">expected output:</span></span>

```output
Testing connection with https://cdn.x.cp.wd.microsoft.com/ping ... [OK]
Testing connection with https://eu-cdn.x.cp.wd.microsoft.com/ping ... [OK]
Testing connection with https://wu-cdn.x.cp.wd.microsoft.com/ping ... [OK]
Testing connection with https://x.cp.wd.microsoft.com/api/report ... [OK]
Testing connection with https://winatp-gw-cus.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-eus.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-weu.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-neu.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-ukw.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-uks.microsoft.com/test ... [OK]
Testing connection with https://eu-v20.events.data.microsoft.com/ping ... [OK]
Testing connection with https://us-v20.events.data.microsoft.com/ping ... [OK]
Testing connection with https://uk-v20.events.data.microsoft.com/ping ... [OK]
Testing connection with https://v20.events.data.microsoft.com/ping ... [OK]
```

<span data-ttu-id="f9499-113">Se il test di connettività ha esito negativo, verificare se il dispositivo dispone dell'accesso a Internet e se uno qualsiasi [degli endpoint](microsoft-defender-endpoint-linux.md#network-connections) richiesti dal prodotto è bloccato da un proxy o da un firewall.</span><span class="sxs-lookup"><span data-stu-id="f9499-113">If the connectivity test fails, check if the device has Internet access and if [any of the endpoints required by the product](microsoft-defender-endpoint-linux.md#network-connections) are blocked by a proxy or firewall.</span></span>

<span data-ttu-id="f9499-114">Errori con errore di arricciatura 35 o 60, indicare il rifiuto dell'aggiunta del certificato.</span><span class="sxs-lookup"><span data-stu-id="f9499-114">Failures with curl error 35 or 60, indicate certificate pinning rejection.</span></span> <span data-ttu-id="f9499-115">Verificare se la connessione è sotto controllo SSL o HTTPS.</span><span class="sxs-lookup"><span data-stu-id="f9499-115">Please check if the connection is under SSL or HTTPS inspection.</span></span> <span data-ttu-id="f9499-116">In tal caso, aggiungi Microsoft Defender for Endpoint all'elenco consenti.</span><span class="sxs-lookup"><span data-stu-id="f9499-116">If so, add Microsoft Defender for Endpoint to the allow list.</span></span>

## <a name="troubleshooting-steps-for-environments-without-proxy-or-with-transparent-proxy"></a><span data-ttu-id="f9499-117">Procedura di risoluzione dei problemi per gli ambienti senza proxy o con proxy trasparente</span><span class="sxs-lookup"><span data-stu-id="f9499-117">Troubleshooting steps for environments without proxy or with transparent proxy</span></span>

<span data-ttu-id="f9499-118">Per verificare che una connessione non sia bloccata in un ambiente senza un proxy o con un proxy trasparente, eseguire il comando seguente nel terminale:</span><span class="sxs-lookup"><span data-stu-id="f9499-118">To test that a connection is not blocked in an environment without a proxy or with a transparent proxy, run the following command in the terminal:</span></span>

```bash
curl -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

<span data-ttu-id="f9499-119">L'output di questo comando deve essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="f9499-119">The output from this command should be similar to:</span></span>

```Output
OK https://x.cp.wd.microsoft.com/api/report
OK https://cdn.x.cp.wd.microsoft.com/ping
```

## <a name="troubleshooting-steps-for-environments-with-static-proxy"></a><span data-ttu-id="f9499-120">Procedura di risoluzione dei problemi per gli ambienti con proxy statico</span><span class="sxs-lookup"><span data-stu-id="f9499-120">Troubleshooting steps for environments with static proxy</span></span>

> [!WARNING]
> <span data-ttu-id="f9499-121">PAC, WPAD e proxy autenticati non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="f9499-121">PAC, WPAD, and authenticated proxies are not supported.</span></span> <span data-ttu-id="f9499-122">Verificare che sia in uso solo un proxy statico o trasparente.</span><span class="sxs-lookup"><span data-stu-id="f9499-122">Ensure that only a static proxy or transparent proxy is being used.</span></span>
>
> <span data-ttu-id="f9499-123">Anche l'ispezione e l'intercettazione dei proxy SSL non sono supportati per motivi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="f9499-123">SSL inspection and intercepting proxies are also not supported for security reasons.</span></span> <span data-ttu-id="f9499-124">Configura un'eccezione per l'ispezione SSL e il server proxy per passare direttamente i dati da Defender per Endpoint per Linux agli URL rilevanti senza intercettazione.</span><span class="sxs-lookup"><span data-stu-id="f9499-124">Configure an exception for SSL inspection and your proxy server to directly pass through data from Defender for Endpoint for Linux to the relevant URLs without interception.</span></span> <span data-ttu-id="f9499-125">L'aggiunta del certificato di intercettazione all'archivio globale non consentirà l'intercettazione.</span><span class="sxs-lookup"><span data-stu-id="f9499-125">Adding your interception certificate to the global store will not allow for interception.</span></span>

<span data-ttu-id="f9499-126">Se è necessario un proxy statico, aggiungi un parametro proxy al comando precedente, dove `proxy_address:port` corrisponde all'indirizzo proxy e alla porta:</span><span class="sxs-lookup"><span data-stu-id="f9499-126">If a static proxy is required, add a proxy parameter to the above command, where `proxy_address:port` correspond to the proxy address and port:</span></span>

```bash
curl -x http://proxy_address:port -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

<span data-ttu-id="f9499-127">Assicurati di usare lo stesso indirizzo proxy e la stessa porta configurati nel `/lib/system/system/mdatp.service` file.</span><span class="sxs-lookup"><span data-stu-id="f9499-127">Ensure that you use the same proxy address and port as configured in the `/lib/system/system/mdatp.service` file.</span></span> <span data-ttu-id="f9499-128">Controlla la configurazione del proxy se sono presenti errori dai comandi precedenti.</span><span class="sxs-lookup"><span data-stu-id="f9499-128">Check your proxy configuration if there are errors from the above commands.</span></span>

> [!WARNING]
> <span data-ttu-id="f9499-129">Il proxy statico non può essere configurato tramite una variabile di ambiente a `HTTPS_PROXY` livello di sistema.</span><span class="sxs-lookup"><span data-stu-id="f9499-129">The static proxy cannot be configured through a system-wide `HTTPS_PROXY` environment variable.</span></span> <span data-ttu-id="f9499-130">Assicurati invece che `HTTPS_PROXY` sia impostato correttamente nel `/lib/system/system/mdatp.service` file.</span><span class="sxs-lookup"><span data-stu-id="f9499-130">Instead, ensure that `HTTPS_PROXY` is properly set in the `/lib/system/system/mdatp.service` file.</span></span>

<span data-ttu-id="f9499-131">Per utilizzare un proxy statico, è `mdatp.service` necessario modificare il file.</span><span class="sxs-lookup"><span data-stu-id="f9499-131">To use a static proxy, the `mdatp.service` file must be modified.</span></span> <span data-ttu-id="f9499-132">Assicurarsi che `#` l'interlinea venga rimossa per rimuovere il commento dalla riga seguente `/lib/systemd/system/mdatp.service` da :</span><span class="sxs-lookup"><span data-stu-id="f9499-132">Ensure the leading `#` is removed to uncomment the following line from `/lib/systemd/system/mdatp.service`:</span></span>

```bash
#Environment="HTTPS_PROXY=http://address:port"
```

<span data-ttu-id="f9499-133">Assicurarsi inoltre che sia stato inserito l'indirizzo proxy statico corretto per sostituire `address:port` .</span><span class="sxs-lookup"><span data-stu-id="f9499-133">Also ensure that the correct static proxy address is filled in to replace `address:port`.</span></span>

<span data-ttu-id="f9499-134">Se questo file è corretto, prova a eseguire il comando seguente nel terminale per ricaricare Defender per Endpoint per Linux e propagare l'impostazione:</span><span class="sxs-lookup"><span data-stu-id="f9499-134">If this file is correct, try running the following command in the terminal to reload Defender for Endpoint for Linux and propagate the setting:</span></span>

```bash
sudo systemctl daemon-reload; sudo systemctl restart mdatp
```

<span data-ttu-id="f9499-135">In caso di esito positivo, tentare un altro test di connettività dalla riga di comando:</span><span class="sxs-lookup"><span data-stu-id="f9499-135">Upon success, attempt another connectivity test from the command line:</span></span>

```bash
mdatp connectivity test
```

<span data-ttu-id="f9499-136">Se il problema persiste, contattare il supporto tecnico.</span><span class="sxs-lookup"><span data-stu-id="f9499-136">If the problem persists, contact customer support.</span></span>

## <a name="resources"></a><span data-ttu-id="f9499-137">Risorse</span><span class="sxs-lookup"><span data-stu-id="f9499-137">Resources</span></span>

- <span data-ttu-id="f9499-138">Per ulteriori informazioni su come configurare il prodotto per l'utilizzo di un proxy statico, vedere [Configure Microsoft Defender for Endpoint for static proxy discovery](linux-static-proxy-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="f9499-138">For more information about how to configure the product to use a static proxy, see [Configure Microsoft Defender for Endpoint for static proxy discovery](linux-static-proxy-configuration.md).</span></span>
