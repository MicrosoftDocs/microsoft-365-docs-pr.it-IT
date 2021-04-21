---
title: Microsoft Defender per Endpoint su Mac
ms.reviewer: ''
description: Scopri come installare, configurare, aggiornare e usare Microsoft Defender per Endpoint su Mac.
keywords: microsoft, defender, atp, mac, installazione, distribuire, disinstallazione, intune, jamf, macos, big sur, catalina, mojave, mde per mac
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
ms.openlocfilehash: 705b1fffbc38282441f66e0dc411cf09699cb3f9
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903767"
---
# <a name="microsoft-defender-for-endpoint-on-mac"></a><span data-ttu-id="c5e2d-104">Microsoft Defender per Endpoint su Mac</span><span class="sxs-lookup"><span data-stu-id="c5e2d-104">Microsoft Defender for Endpoint on Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c5e2d-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="c5e2d-105">**Applies to:**</span></span>
- [<span data-ttu-id="c5e2d-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="c5e2d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c5e2d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c5e2d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="c5e2d-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="c5e2d-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c5e2d-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="c5e2d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="c5e2d-110">Questo argomento descrive come installare, configurare, aggiornare e usare Defender per Endpoint su Mac.</span><span class="sxs-lookup"><span data-stu-id="c5e2d-110">This topic describes how to install, configure, update, and use Defender for Endpoint on Mac.</span></span>

> [!CAUTION]
> <span data-ttu-id="c5e2d-111">L'esecuzione di altri prodotti di protezione degli endpoint di terze parti insieme a Microsoft Defender per Endpoint su Mac può causare problemi di prestazioni ed effetti collaterali imprevedibili.</span><span class="sxs-lookup"><span data-stu-id="c5e2d-111">Running other third-party endpoint protection products alongside Microsoft Defender for Endpoint on Mac is likely to lead to performance problems and unpredictable side effects.</span></span> <span data-ttu-id="c5e2d-112">Se la protezione degli endpoint non Microsoft è un requisito assoluto nell'ambiente, puoi comunque sfruttare in modo sicuro la funzionalità Defender for Endpoint on Mac EDR dopo aver configurato la funzionalità antivirus per l'esecuzione in [modalità passiva.](mac-preferences.md#enable--disable-passive-mode)</span><span class="sxs-lookup"><span data-stu-id="c5e2d-112">If non-Microsoft endpoint protection is an absolute requirement in your environment, you can still safely take advantage of Defender for Endpoint on Mac EDR functionality after configuring the antivirus functionality to run in [Passive mode](mac-preferences.md#enable--disable-passive-mode).</span></span>

## <a name="whats-new-in-the-latest-release"></a><span data-ttu-id="c5e2d-113">Novità della versione più recente</span><span class="sxs-lookup"><span data-stu-id="c5e2d-113">What’s new in the latest release</span></span>

[<span data-ttu-id="c5e2d-114">Novità di Microsoft Defender per Endpoint</span><span class="sxs-lookup"><span data-stu-id="c5e2d-114">What's new in Microsoft Defender for Endpoint</span></span>](whats-new-in-microsoft-defender-atp.md)

[<span data-ttu-id="c5e2d-115">Novità di Microsoft Defender per Endpoint su Mac</span><span class="sxs-lookup"><span data-stu-id="c5e2d-115">What's new in Microsoft Defender for Endpoint on Mac</span></span>](mac-whatsnew.md)

> [!TIP]
> <span data-ttu-id="c5e2d-116">Se hai commenti e suggerimenti che vuoi condividere, invialo aprendo Microsoft Defender per Endpoint sul Mac nel dispositivo e accedendo alla guida Invia  >  **feedback.**</span><span class="sxs-lookup"><span data-stu-id="c5e2d-116">If you have any feedback that you would like to share, submit it by opening Microsoft Defender for Endpoint on Mac on your device and navigating to **Help** > **Send feedback**.</span></span>

<span data-ttu-id="c5e2d-117">Per ottenere le funzionalità più recenti, incluse le funzionalità di anteprima (ad esempio il rilevamento degli endpoint e la risposta per i dispositivi Mac), configura il dispositivo macOS che esegue Microsoft Defender for Endpoint come dispositivo "Insider".</span><span class="sxs-lookup"><span data-stu-id="c5e2d-117">To get the latest features, including preview capabilities (such as endpoint detection and response for your Mac devices), configure your macOS device running Microsoft Defender for Endpoint to be an "Insider" device.</span></span>

## <a name="how-to-install-microsoft-defender-for-endpoint-on-mac"></a><span data-ttu-id="c5e2d-118">Come installare Microsoft Defender per Endpoint su Mac</span><span class="sxs-lookup"><span data-stu-id="c5e2d-118">How to install Microsoft Defender for Endpoint on Mac</span></span>

### <a name="prerequisites"></a><span data-ttu-id="c5e2d-119">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="c5e2d-119">Prerequisites</span></span>

- <span data-ttu-id="c5e2d-120">Una sottoscrizione defender per endpoint e l'accesso al portale di Microsoft Defender Security Center</span><span class="sxs-lookup"><span data-stu-id="c5e2d-120">A Defender for Endpoint subscription and access to the Microsoft Defender Security Center portal</span></span>
- <span data-ttu-id="c5e2d-121">Esperienza a livello di principiante nello scripting macOS e BASH</span><span class="sxs-lookup"><span data-stu-id="c5e2d-121">Beginner-level experience in macOS and BASH scripting</span></span>
- <span data-ttu-id="c5e2d-122">Privilegi amministrativi nel dispositivo (in caso di distribuzione manuale)</span><span class="sxs-lookup"><span data-stu-id="c5e2d-122">Administrative privileges on the device (in case of manual deployment)</span></span>

### <a name="installation-instructions"></a><span data-ttu-id="c5e2d-123">Istruzioni di installazione</span><span class="sxs-lookup"><span data-stu-id="c5e2d-123">Installation instructions</span></span>

<span data-ttu-id="c5e2d-124">Esistono diversi metodi e strumenti di distribuzione che puoi usare per installare e configurare Defender per Endpoint su Mac.</span><span class="sxs-lookup"><span data-stu-id="c5e2d-124">There are several methods and deployment tools that you can use to install and configure Defender for Endpoint on Mac.</span></span>

- <span data-ttu-id="c5e2d-125">Strumenti di gestione di terze parti:</span><span class="sxs-lookup"><span data-stu-id="c5e2d-125">Third-party management tools:</span></span>
    - [<span data-ttu-id="c5e2d-126">Distribuzione basata su Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="c5e2d-126">Microsoft Intune-based deployment</span></span>](mac-install-with-intune.md)
    - [<span data-ttu-id="c5e2d-127">Distribuzione basata su JAMF</span><span class="sxs-lookup"><span data-stu-id="c5e2d-127">JAMF-based deployment</span></span>](mac-install-with-jamf.md)
    - [<span data-ttu-id="c5e2d-128">Altri prodotti MDM</span><span class="sxs-lookup"><span data-stu-id="c5e2d-128">Other MDM products</span></span>](mac-install-with-other-mdm.md)

- <span data-ttu-id="c5e2d-129">Strumento da riga di comando:</span><span class="sxs-lookup"><span data-stu-id="c5e2d-129">Command-line tool:</span></span>
    - [<span data-ttu-id="c5e2d-130">Distribuzione manuale</span><span class="sxs-lookup"><span data-stu-id="c5e2d-130">Manual deployment</span></span>](mac-install-manually.md)

### <a name="system-requirements"></a><span data-ttu-id="c5e2d-131">Requisiti di sistema</span><span class="sxs-lookup"><span data-stu-id="c5e2d-131">System requirements</span></span>

<span data-ttu-id="c5e2d-132">Sono supportate le tre versioni principali più recenti di macOS.</span><span class="sxs-lookup"><span data-stu-id="c5e2d-132">The three most recent major releases of macOS are supported.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c5e2d-133">In macOS 11 (Big Sur), Microsoft Defender for Endpoint richiede profili di configurazione aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="c5e2d-133">On macOS 11 (Big Sur), Microsoft Defender for Endpoint requires additional configuration profiles.</span></span> <span data-ttu-id="c5e2d-134">Se sei un cliente esistente che esegue l'aggiornamento da versioni precedenti di macOS, assicurati di distribuire i profili di configurazione aggiuntivi elencati in Nuovi profili di configurazione per macOS Catalina e versioni [più recenti di macOS.](mac-sysext-policies.md)</span><span class="sxs-lookup"><span data-stu-id="c5e2d-134">If you are an existing customer upgrading from earlier versions of macOS, make sure to deploy the additional configuration profiles listed on [New configuration profiles for macOS Catalina and newer versions of macOS](mac-sysext-policies.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c5e2d-135">Il supporto per macOS 10.13 (High Sierra) è stato interrotto a partire dal 15 febbraio 2021.</span><span class="sxs-lookup"><span data-stu-id="c5e2d-135">Support for macOS 10.13 (High Sierra) has been discontinued as of February 15th, 2021.</span></span>

- <span data-ttu-id="c5e2d-136">11 (Big Sur), 10.15 (Catalina), 10.14 (Mojave)</span><span class="sxs-lookup"><span data-stu-id="c5e2d-136">11 (Big Sur), 10.15 (Catalina), 10.14 (Mojave)</span></span>
- <span data-ttu-id="c5e2d-137">Spazio su disco: 1 GB</span><span class="sxs-lookup"><span data-stu-id="c5e2d-137">Disk space: 1GB</span></span>

<span data-ttu-id="c5e2d-138">Le versioni beta di macOS non sono supportate.</span><span class="sxs-lookup"><span data-stu-id="c5e2d-138">Beta versions of macOS are not supported.</span></span>

<span data-ttu-id="c5e2d-139">I dispositivi macOS con processori M1 non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="c5e2d-139">macOS devices with M1 processors are not supported.</span></span>

<span data-ttu-id="c5e2d-140">Dopo aver abilitato il servizio, potrebbe essere necessario configurare la rete o il firewall per consentire le connessioni in uscita tra il servizio e gli endpoint.</span><span class="sxs-lookup"><span data-stu-id="c5e2d-140">After you've enabled the service, you may need to configure your network or firewall to allow outbound connections between it and your endpoints.</span></span>

### <a name="licensing-requirements"></a><span data-ttu-id="c5e2d-141">Requisiti per la licenza</span><span class="sxs-lookup"><span data-stu-id="c5e2d-141">Licensing requirements</span></span>

<span data-ttu-id="c5e2d-142">Microsoft Defender per Endpoint su Mac richiede una delle seguenti offerte per contratti multilicenza Microsoft:</span><span class="sxs-lookup"><span data-stu-id="c5e2d-142">Microsoft Defender for Endpoint on Mac requires one of the following Microsoft Volume Licensing offers:</span></span>

- <span data-ttu-id="c5e2d-143">Microsoft 365 E5 (M365 E5)</span><span class="sxs-lookup"><span data-stu-id="c5e2d-143">Microsoft 365 E5 (M365 E5)</span></span>
- <span data-ttu-id="c5e2d-144">Microsoft 365 E5 Security</span><span class="sxs-lookup"><span data-stu-id="c5e2d-144">Microsoft 365 E5 Security</span></span>
- <span data-ttu-id="c5e2d-145">Microsoft 365 A5 (M365 A5)</span><span class="sxs-lookup"><span data-stu-id="c5e2d-145">Microsoft 365 A5 (M365 A5)</span></span>

> [!NOTE]
> <span data-ttu-id="c5e2d-146">Gli utenti con licenza idonea possono usare Microsoft Defender per Endpoint su un massimo di cinque dispositivi simultanei.</span><span class="sxs-lookup"><span data-stu-id="c5e2d-146">Eligible licensed users may use Microsoft Defender for Endpoint on up to five concurrent devices.</span></span>
> <span data-ttu-id="c5e2d-147">Microsoft Defender for Endpoint è disponibile anche per l'acquisto da un provider di soluzioni cloud (CSP).</span><span class="sxs-lookup"><span data-stu-id="c5e2d-147">Microsoft Defender for Endpoint is also available for purchase from a Cloud Solution Provider (CSP).</span></span> <span data-ttu-id="c5e2d-148">Quando viene acquistato tramite un CSP, non richiede offerte di contratti multilicenza Microsoft elencate.</span><span class="sxs-lookup"><span data-stu-id="c5e2d-148">When purchased via a CSP, it does not require Microsoft Volume Licensing offers listed.</span></span>

### <a name="network-connections"></a><span data-ttu-id="c5e2d-149">Connessioni di rete</span><span class="sxs-lookup"><span data-stu-id="c5e2d-149">Network connections</span></span>

<span data-ttu-id="c5e2d-150">Nel seguente foglio di calcolo scaricabile sono elencati i servizi e gli URL associati a cui la rete deve essere in grado di connettersi.</span><span class="sxs-lookup"><span data-stu-id="c5e2d-150">The following downloadable spreadsheet lists the services and their associated URLs that your network must be able to connect to.</span></span> <span data-ttu-id="c5e2d-151">È consigliabile verificare che non siano presenti regole di filtro di rete o firewall che negherebbero l'accesso *a* questi URL oppure potrebbe essere necessario creare una regola di autorizzazione specifica per tali URL.</span><span class="sxs-lookup"><span data-stu-id="c5e2d-151">You should ensure that there are no firewall or network filtering rules that would deny access to these URLs, or you may need to create an *allow* rule specifically for them.</span></span>



|<span data-ttu-id="c5e2d-152">**Foglio di calcolo dell'elenco dei domini**</span><span class="sxs-lookup"><span data-stu-id="c5e2d-152">**Spreadsheet of domains list**</span></span>|<span data-ttu-id="c5e2d-153">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="c5e2d-153">**Description**</span></span>|
|:-----|:-----|
|![Immagine di scorrimento per il foglio di calcolo degli URL di Microsoft Defender for Endpoint](images/mdatp-urls.png)<br/>  | <span data-ttu-id="c5e2d-155">Foglio di calcolo di record DNS specifici per le posizioni dei servizi, le posizioni geografiche e il sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="c5e2d-155">Spreadsheet of specific DNS records for service locations, geographic locations, and OS.</span></span> <br><br><span data-ttu-id="c5e2d-156">Scaricare il foglio di calcolo qui: [mdatp-urls.xlsx](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx).</span><span class="sxs-lookup"><span data-stu-id="c5e2d-156">Download the spreadsheet here: [mdatp-urls.xlsx](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx).</span></span>

<span data-ttu-id="c5e2d-157">Microsoft Defender for Endpoint può individuare un server proxy utilizzando i metodi di individuazione seguenti:</span><span class="sxs-lookup"><span data-stu-id="c5e2d-157">Microsoft Defender for Endpoint can discover a proxy server by using the following discovery methods:</span></span>
- <span data-ttu-id="c5e2d-158">Configurazione automatica proxy (PAC)</span><span class="sxs-lookup"><span data-stu-id="c5e2d-158">Proxy autoconfig (PAC)</span></span>
- <span data-ttu-id="c5e2d-159">WPAD (Web Proxy Autodiscovery Protocol)</span><span class="sxs-lookup"><span data-stu-id="c5e2d-159">Web Proxy Autodiscovery Protocol (WPAD)</span></span>
- <span data-ttu-id="c5e2d-160">Configurazione manuale del proxy statico</span><span class="sxs-lookup"><span data-stu-id="c5e2d-160">Manual static proxy configuration</span></span>

<span data-ttu-id="c5e2d-161">Se un proxy o un firewall blocca il traffico anonimo, assicurati che il traffico anonimo sia consentito negli URL elencati in precedenza.</span><span class="sxs-lookup"><span data-stu-id="c5e2d-161">If a proxy or firewall is blocking anonymous traffic, make sure that anonymous traffic is permitted in the previously listed URLs.</span></span>

> [!WARNING]
> <span data-ttu-id="c5e2d-162">I proxy autenticati non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="c5e2d-162">Authenticated proxies are not supported.</span></span> <span data-ttu-id="c5e2d-163">Assicurati che vengano usati solo PAC, WPAD o un proxy statico.</span><span class="sxs-lookup"><span data-stu-id="c5e2d-163">Ensure that only PAC, WPAD, or a static proxy is being used.</span></span>
>
> <span data-ttu-id="c5e2d-164">Anche l'ispezione e l'intercettazione dei proxy SSL non sono supportati per motivi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="c5e2d-164">SSL inspection and intercepting proxies are also not supported for security reasons.</span></span> <span data-ttu-id="c5e2d-165">Configura un'eccezione per l'ispezione SSL e il server proxy per passare direttamente i dati da Microsoft Defender per Endpoint su macOS agli URL rilevanti senza intercettazione.</span><span class="sxs-lookup"><span data-stu-id="c5e2d-165">Configure an exception for SSL inspection and your proxy server to directly pass through data from Microsoft Defender for Endpoint on macOS to the relevant URLs without interception.</span></span> <span data-ttu-id="c5e2d-166">L'aggiunta del certificato di intercettazione all'archivio globale non consentirà l'intercettazione.</span><span class="sxs-lookup"><span data-stu-id="c5e2d-166">Adding your interception certificate to the global store will not allow for interception.</span></span>

<span data-ttu-id="c5e2d-167">Per verificare che una connessione non sia bloccata, aprire [https://x.cp.wd.microsoft.com/api/report](https://x.cp.wd.microsoft.com/api/report) e [https://cdn.x.cp.wd.microsoft.com/ping](https://cdn.x.cp.wd.microsoft.com/ping) in un browser.</span><span class="sxs-lookup"><span data-stu-id="c5e2d-167">To test that a connection is not blocked, open [https://x.cp.wd.microsoft.com/api/report](https://x.cp.wd.microsoft.com/api/report) and [https://cdn.x.cp.wd.microsoft.com/ping](https://cdn.x.cp.wd.microsoft.com/ping) in a browser.</span></span>

<span data-ttu-id="c5e2d-168">Se si preferisce la riga di comando, è anche possibile controllare la connessione eseguendo il comando seguente in Terminale:</span><span class="sxs-lookup"><span data-stu-id="c5e2d-168">If you prefer the command line, you can also check the connection by running the following command in Terminal:</span></span>

```bash
curl -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

<span data-ttu-id="c5e2d-169">L'output di questo comando deve essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="c5e2d-169">The output from this command should be similar to the following:</span></span>

 `OK https://x.cp.wd.microsoft.com/api/report`

 `OK https://cdn.x.cp.wd.microsoft.com/ping`

> [!CAUTION]
> <span data-ttu-id="c5e2d-170">È consigliabile mantenere [la protezione dell'integrità del](https://support.apple.com/en-us/HT204899) sistema (SIP) abilitata nei dispositivi client.</span><span class="sxs-lookup"><span data-stu-id="c5e2d-170">We recommend that you keep [System Integrity Protection](https://support.apple.com/en-us/HT204899) (SIP) enabled on client devices.</span></span> <span data-ttu-id="c5e2d-171">SIP è una funzionalità di sicurezza macOS incorporata che impedisce la manomissione di basso livello del sistema operativo ed è abilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="c5e2d-171">SIP is a built-in macOS security feature that prevents low-level tampering with the OS, and is enabled by default.</span></span>

<span data-ttu-id="c5e2d-172">Dopo l'installazione di Microsoft Defender for Endpoint, è possibile convalidare la connettività eseguendo il comando seguente in Terminal:</span><span class="sxs-lookup"><span data-stu-id="c5e2d-172">Once Microsoft Defender for Endpoint is installed, connectivity can be validated by running the following command in Terminal:</span></span>
```bash
mdatp connectivity test
```

## <a name="how-to-update-microsoft-defender-for-endpoint-on-mac"></a><span data-ttu-id="c5e2d-173">Come aggiornare Microsoft Defender per Endpoint su Mac</span><span class="sxs-lookup"><span data-stu-id="c5e2d-173">How to update Microsoft Defender for Endpoint on Mac</span></span>

<span data-ttu-id="c5e2d-174">Microsoft pubblica regolarmente aggiornamenti software per migliorare le prestazioni, la sicurezza e offrire nuove funzionalità.</span><span class="sxs-lookup"><span data-stu-id="c5e2d-174">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span> <span data-ttu-id="c5e2d-175">Per aggiornare Microsoft Defender per Endpoint su Mac, viene utilizzato un programma denominato Microsoft AutoUpdate (MAU).</span><span class="sxs-lookup"><span data-stu-id="c5e2d-175">To update Microsoft Defender for Endpoint on Mac, a program named Microsoft AutoUpdate (MAU) is used.</span></span> <span data-ttu-id="c5e2d-176">Per altre informazioni, vedi [Distribuire gli aggiornamenti per Microsoft Defender per Endpoint su Mac.](mac-updates.md)</span><span class="sxs-lookup"><span data-stu-id="c5e2d-176">To learn more, see [Deploy updates for Microsoft Defender for Endpoint on Mac](mac-updates.md).</span></span>

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-mac"></a><span data-ttu-id="c5e2d-177">Come configurare Microsoft Defender per Endpoint su Mac</span><span class="sxs-lookup"><span data-stu-id="c5e2d-177">How to configure Microsoft Defender for Endpoint on Mac</span></span>

<span data-ttu-id="c5e2d-178">Le indicazioni su come configurare il prodotto in ambienti aziendali sono disponibili in Impostare le preferenze [per Microsoft Defender per Endpoint su Mac.](mac-preferences.md)</span><span class="sxs-lookup"><span data-stu-id="c5e2d-178">Guidance for how to configure the product in enterprise environments is available in [Set preferences for Microsoft Defender for Endpoint on Mac](mac-preferences.md).</span></span>

## <a name="macos-kernel-and-system-extensions"></a><span data-ttu-id="c5e2d-179">Estensioni del kernel e del sistema macOS</span><span class="sxs-lookup"><span data-stu-id="c5e2d-179">macOS kernel and system extensions</span></span>

<span data-ttu-id="c5e2d-180">In linea con l'evoluzione di macOS, stiamo preparando un aggiornamento di Microsoft Defender per Endpoint su Mac che sfrutta le estensioni di sistema anziché le estensioni del kernel.</span><span class="sxs-lookup"><span data-stu-id="c5e2d-180">In alignment with macOS evolution, we are preparing a Microsoft Defender for Endpoint on Mac update that leverages system extensions instead of kernel extensions.</span></span> <span data-ttu-id="c5e2d-181">Per informazioni dettagliate, vedi [Novità di Microsoft Defender per Endpoint su Mac.](mac-whatsnew.md)</span><span class="sxs-lookup"><span data-stu-id="c5e2d-181">For relevant details, see [What's new in Microsoft Defender for Endpoint on Mac](mac-whatsnew.md).</span></span>

## <a name="resources"></a><span data-ttu-id="c5e2d-182">Risorse</span><span class="sxs-lookup"><span data-stu-id="c5e2d-182">Resources</span></span>

- <span data-ttu-id="c5e2d-183">Per altre informazioni sulla registrazione, la disinstallazione o altri argomenti, vedi [Risorse per Microsoft Defender per Endpoint su Mac.](mac-resources.md)</span><span class="sxs-lookup"><span data-stu-id="c5e2d-183">For more information about logging, uninstalling, or other topics, see [Resources for Microsoft Defender for Endpoint on Mac](mac-resources.md).</span></span>

- <span data-ttu-id="c5e2d-184">[Privacy per Microsoft Defender per Endpoint su Mac](mac-privacy.md).</span><span class="sxs-lookup"><span data-stu-id="c5e2d-184">[Privacy for Microsoft Defender for Endpoint on Mac](mac-privacy.md).</span></span>
