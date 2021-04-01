---
title: Risolvere i problemi di connettività cloud per Microsoft Defender per Endpoint per Mac
description: Questo argomento descrive come risolvere i problemi di connettività cloud per Microsoft Defender per Endpoint per Mac
keywords: microsoft, defender, atp, mac, installazione, distribuire, disinstallazione, intune, jamf, macos, catalina, mojave, high sierra
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-lsaldanha
author: lovina-saldanha
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: e522495fa86b5a71faa9f25cc863c29cc5d124c0
ms.sourcegitcommit: 7b8104015a76e02bc215e1cf08069979c70650ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "51476686"
---
# <a name="troubleshoot-cloud-connectivity-issues-for-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="abfc5-104">Risolvere i problemi di connettività cloud per Microsoft Defender per Endpoint per Mac</span><span class="sxs-lookup"><span data-stu-id="abfc5-104">Troubleshoot cloud connectivity issues for Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="abfc5-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="abfc5-105">**Applies to:**</span></span>
- [<span data-ttu-id="abfc5-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="abfc5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="abfc5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="abfc5-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="abfc5-108">**Piattaforma** macOS</span><span class="sxs-lookup"><span data-stu-id="abfc5-108">**Platform** macOS</span></span>

<span data-ttu-id="abfc5-109">Questo argomento descrive come risolvere i problemi di connettività cloud per Microsoft Defender per Endpoint per Mac.</span><span class="sxs-lookup"><span data-stu-id="abfc5-109">This topic describes how to Troubleshoot cloud connectivity issues for Microsoft Defender for Endpoint for Mac.</span></span>

## <a name="run-the-connectivity-test"></a><span data-ttu-id="abfc5-110">Eseguire il test di connettività</span><span class="sxs-lookup"><span data-stu-id="abfc5-110">Run the connectivity test</span></span>
<span data-ttu-id="abfc5-111">Per verificare se Defender per Endpoint per Mac può comunicare con il cloud con le impostazioni di rete correnti, esegui un test di connettività dalla riga di comando:</span><span class="sxs-lookup"><span data-stu-id="abfc5-111">To test if Defender for Endpoint for Mac can communicate to the cloud with the current network settings, run a connectivity test from the command line:</span></span>

```Bash
mdatp connectivity test
```

<span data-ttu-id="abfc5-112">output previsto:</span><span class="sxs-lookup"><span data-stu-id="abfc5-112">expected output:</span></span>
```Bash
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

<span data-ttu-id="abfc5-113">Se il test di connettività ha esito negativo, verificare se il dispositivo dispone dell'accesso a Internet e se uno qualsiasi [degli endpoint](microsoft-defender-endpoint-mac.md#network-connections) richiesti dal prodotto è bloccato da un proxy o da un firewall.</span><span class="sxs-lookup"><span data-stu-id="abfc5-113">If the connectivity test fails, check if the device has Internet access and if [any of the endpoints required by the product](microsoft-defender-endpoint-mac.md#network-connections) are blocked by a proxy or firewall.</span></span>

<span data-ttu-id="abfc5-114">Gli errori con errore di arricciatura 35 o 60 indicano il rifiuto dell'aggiunta del certificato, che indica un potenziale problema con l'ispezione SSL o HTTPS.</span><span class="sxs-lookup"><span data-stu-id="abfc5-114">Failures with curl error 35 or 60 indicate certificate pinning rejection, which indicates a potential issue with SSL or HTTPS inspection.</span></span> <span data-ttu-id="abfc5-115">Vedi le istruzioni seguenti relative alla configurazione dell'ispezione SSL.</span><span class="sxs-lookup"><span data-stu-id="abfc5-115">See instructions below regarding SSL inspection configuration.</span></span>

## <a name="troubleshooting-steps-for-environments-without-proxy-or-with-proxy-autoconfig-pac-or-with-web-proxy-autodiscovery-protocol-wpad"></a><span data-ttu-id="abfc5-116">Procedura di risoluzione dei problemi per gli ambienti senza proxy o con proxy autoconfig (PAC) o con WPAD (Web Proxy Autodiscovery Protocol)</span><span class="sxs-lookup"><span data-stu-id="abfc5-116">Troubleshooting steps for environments without proxy or with Proxy autoconfig (PAC) or with Web Proxy Autodiscovery Protocol (WPAD)</span></span>
<span data-ttu-id="abfc5-117">Utilizzare la procedura seguente per verificare che una connessione non sia bloccata in un ambiente senza proxy o con proxy autoconfig (PAC) o con WPAD (Web Proxy Autodiscovery Protocol).</span><span class="sxs-lookup"><span data-stu-id="abfc5-117">Use the following procedure to test that a connection is not blocked in an environment without a proxy or with Proxy autoconfig (PAC) or with Web Proxy Autodiscovery Protocol (WPAD).</span></span>

<span data-ttu-id="abfc5-118">Se un proxy o un firewall blocca il traffico anonimo, assicurati che il traffico anonimo sia consentito negli URL elencati in precedenza.</span><span class="sxs-lookup"><span data-stu-id="abfc5-118">If a proxy or firewall is blocking anonymous traffic, make sure that anonymous traffic is permitted in the previously listed URLs.</span></span>

> [!WARNING]
> <span data-ttu-id="abfc5-119">I proxy autenticati non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="abfc5-119">Authenticated proxies are not supported.</span></span> <span data-ttu-id="abfc5-120">Assicurati che vengano usati solo PAC, WPAD o un proxy statico.</span><span class="sxs-lookup"><span data-stu-id="abfc5-120">Ensure that only PAC, WPAD, or a static proxy is being used.</span></span> <span data-ttu-id="abfc5-121">Anche l'ispezione e l'intercettazione dei proxy SSL non sono supportati per motivi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="abfc5-121">SSL inspection and intercepting proxies are also not supported for security reasons.</span></span> <span data-ttu-id="abfc5-122">Configura un'eccezione per l'ispezione SSL e il server proxy per passare direttamente i dati da Microsoft Defender per Endpoint per Mac agli URL rilevanti senza intercettazione.</span><span class="sxs-lookup"><span data-stu-id="abfc5-122">Configure an exception for SSL inspection and your proxy server to directly pass through data from Microsoft Defender for Endpoint for Mac to the relevant URLs without interception.</span></span> <span data-ttu-id="abfc5-123">L'aggiunta del certificato di intercettazione all'archivio globale non consentirà l'intercettazione.</span><span class="sxs-lookup"><span data-stu-id="abfc5-123">Adding your interception certificate to the global store will not allow for interception.</span></span>
<span data-ttu-id="abfc5-124">Per verificare che una connessione non sia bloccata: in un browser come Microsoft Edge per Mac o Safari aprire https://x.cp.wd.microsoft.com/api/report e https://cdn.x.cp.wd.microsoft.com/ping .</span><span class="sxs-lookup"><span data-stu-id="abfc5-124">To test that a connection is not blocked: In a browser such as Microsoft Edge for Mac or Safari open https://x.cp.wd.microsoft.com/api/report and https://cdn.x.cp.wd.microsoft.com/ping.</span></span>

<span data-ttu-id="abfc5-125">Facoltativamente, in Terminale eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="abfc5-125">Optionally, in Terminal, run the following command:</span></span>

```Bash
curl -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping' 
```

<span data-ttu-id="abfc5-126">L'output di questo comando deve essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="abfc5-126">The output from this command should be similar to:</span></span>
```bash
OK https://x.cp.wd.microsoft.com/api/report
OK https://cdn.x.cp.wd.microsoft.com/ping
```
