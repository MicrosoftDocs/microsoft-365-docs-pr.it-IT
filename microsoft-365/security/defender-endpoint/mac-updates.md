---
title: Distribuire gli aggiornamenti per Microsoft Defender ATP per Mac
description: Controllare gli aggiornamenti per Microsoft Defender ATP per Mac in ambienti aziendali.
keywords: microsoft, defender, atp, mac, aggiornamenti, distribuire
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
ms.openlocfilehash: 3321c1bd181b89c53e2618fc20fa7f733a20cfc1
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689054"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="20e26-104">Distribuire gli aggiornamenti per Microsoft Defender per Endpoint in macOS</span><span class="sxs-lookup"><span data-stu-id="20e26-104">Deploy updates for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="20e26-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="20e26-105">**Applies to:**</span></span>

- [<span data-ttu-id="20e26-106">Microsoft Defender per Endpoint in macOS</span><span class="sxs-lookup"><span data-stu-id="20e26-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="20e26-107">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="20e26-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="20e26-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="20e26-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="20e26-109">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="20e26-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="20e26-110">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="20e26-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="20e26-111">Microsoft pubblica regolarmente aggiornamenti software per migliorare le prestazioni, la sicurezza e offrire nuove funzionalità.</span><span class="sxs-lookup"><span data-stu-id="20e26-111">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span>

<span data-ttu-id="20e26-112">Per aggiornare Microsoft Defender for Endpoint in macOS, viene utilizzato un programma denominato Microsoft AutoUpdate (MAU).</span><span class="sxs-lookup"><span data-stu-id="20e26-112">To update Microsoft Defender for Endpoint on macOS, a program named Microsoft AutoUpdate (MAU) is used.</span></span> <span data-ttu-id="20e26-113">Per impostazione predefinita, MAU controlla automaticamente la disponibilità di aggiornamenti ogni giorno, ma puoi modificarli in settimana, mensile o manualmente.</span><span class="sxs-lookup"><span data-stu-id="20e26-113">By default, MAU automatically checks for updates daily, but you can change that to weekly, monthly, or manually.</span></span>

![Schermata MAU](images/MDATP-34-MAU.png)

<span data-ttu-id="20e26-115">Se decidi di distribuire gli aggiornamenti usando gli strumenti di distribuzione del software, devi configurare MAU per controllare manualmente la disponibilità di aggiornamenti software.</span><span class="sxs-lookup"><span data-stu-id="20e26-115">If you decide to deploy updates by using your software distribution tools, you should configure MAU to manually check for software updates.</span></span> <span data-ttu-id="20e26-116">Puoi distribuire le preferenze per configurare come e quando MAU controlla la disponibilità di aggiornamenti per i Mac nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="20e26-116">You can deploy preferences to configure how and when MAU checks for updates for the Macs in your organization.</span></span>

## <a name="use-msupdate"></a><span data-ttu-id="20e26-117">Utilizzare msupdate</span><span class="sxs-lookup"><span data-stu-id="20e26-117">Use msupdate</span></span>

<span data-ttu-id="20e26-118">MAU include uno strumento da riga di comando, denominato *msupdate,* progettato per gli amministratori IT in modo che abbia un controllo più preciso sulla modalità di applicazione degli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="20e26-118">MAU includes a command-line tool, called *msupdate*, that is designed for IT administrators so that they have more precise control over when updates are applied.</span></span> <span data-ttu-id="20e26-119">Le istruzioni per l'utilizzo di questo strumento sono disponibili in [Update Office for Mac by using msupdate](https://docs.microsoft.com/deployoffice/mac/update-office-for-mac-using-msupdate).</span><span class="sxs-lookup"><span data-stu-id="20e26-119">Instructions for how to use this tool can be found in [Update Office for Mac by using msupdate](https://docs.microsoft.com/deployoffice/mac/update-office-for-mac-using-msupdate).</span></span>

<span data-ttu-id="20e26-120">In MAU, l'identificatore dell'applicazione per Microsoft Defender per Endpoint in macOS è *WDAV00*.</span><span class="sxs-lookup"><span data-stu-id="20e26-120">In MAU, the application identifier for Microsoft Defender for Endpoint on macOS is *WDAV00*.</span></span> <span data-ttu-id="20e26-121">Per scaricare e installare gli aggiornamenti più recenti per Microsoft Defender for Endpoint in macOS, eseguire il comando seguente da una finestra del terminale:</span><span class="sxs-lookup"><span data-stu-id="20e26-121">To download and install the latest updates for Microsoft Defender for Endpoint on macOS, execute the following command from a Terminal window:</span></span>

```
./msupdate --install --apps wdav00
```

## <a name="set-preferences-for-microsoft-autoupdate"></a><span data-ttu-id="20e26-122">Impostare le preferenze per Microsoft AutoUpdate</span><span class="sxs-lookup"><span data-stu-id="20e26-122">Set preferences for Microsoft AutoUpdate</span></span>

<span data-ttu-id="20e26-123">Questa sezione descrive le preferenze più comuni che possono essere usate per configurare MAU.</span><span class="sxs-lookup"><span data-stu-id="20e26-123">This section describes the most common preferences that can be used to configure MAU.</span></span> <span data-ttu-id="20e26-124">Queste impostazioni possono essere distribuite come profilo di configurazione tramite la console di gestione utilizzata dall'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="20e26-124">These settings can be deployed as a configuration profile through the management console that your enterprise is using.</span></span> <span data-ttu-id="20e26-125">Un esempio di profilo di configurazione è illustrato nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="20e26-125">An example of a configuration profile is shown in the following sections.</span></span>

### <a name="set-the-channel-name"></a><span data-ttu-id="20e26-126">Impostare il nome del canale</span><span class="sxs-lookup"><span data-stu-id="20e26-126">Set the channel name</span></span>

<span data-ttu-id="20e26-127">Il canale determina il tipo e la frequenza degli aggiornamenti offerti tramite MAU.</span><span class="sxs-lookup"><span data-stu-id="20e26-127">The channel determines the type and frequency of updates that are offered through MAU.</span></span> <span data-ttu-id="20e26-128">I dispositivi in `Beta` possono provare nuove funzionalità prima dei dispositivi in e `Preview` `Current` .</span><span class="sxs-lookup"><span data-stu-id="20e26-128">Devices in `Beta` can try out new features before devices in `Preview` and `Current`.</span></span> 

<span data-ttu-id="20e26-129">Il `Current` canale contiene la versione più stabile del prodotto.</span><span class="sxs-lookup"><span data-stu-id="20e26-129">The `Current` channel contains the most stable version of the product.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="20e26-130">Prima di Microsoft AutoUpdate versione 4.29, i canali avevano nomi diversi:</span><span class="sxs-lookup"><span data-stu-id="20e26-130">Prior to Microsoft AutoUpdate version 4.29, channels had different names:</span></span> 
> 
> - <span data-ttu-id="20e26-131">`Beta` è stato `InsiderFast` denominato (Insider Fast)</span><span class="sxs-lookup"><span data-stu-id="20e26-131">`Beta` was named `InsiderFast` (Insider Fast)</span></span>
> - <span data-ttu-id="20e26-132">`Preview` è stato `External` denominato (Insider Slow)</span><span class="sxs-lookup"><span data-stu-id="20e26-132">`Preview` was named `External` (Insider Slow)</span></span>
> - <span data-ttu-id="20e26-133">`Current` è stato denominato `Production`</span><span class="sxs-lookup"><span data-stu-id="20e26-133">`Current` was named `Production`</span></span>

>[!TIP]
><span data-ttu-id="20e26-134">Per visualizzare in anteprima le nuove funzionalità e fornire feedback anticipato, è consigliabile configurare alcuni dispositivi dell'organizzazione in `Beta` o `Preview` .</span><span class="sxs-lookup"><span data-stu-id="20e26-134">In order to preview new features and provide early feedback, it is recommended that you configure some devices in your enterprise to `Beta` or `Preview`.</span></span>

|<span data-ttu-id="20e26-135">Sezione</span><span class="sxs-lookup"><span data-stu-id="20e26-135">Section</span></span>|<span data-ttu-id="20e26-136">Valore</span><span class="sxs-lookup"><span data-stu-id="20e26-136">Value</span></span>|
|:--|:--|
| <span data-ttu-id="20e26-137">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="20e26-137">**Domain**</span></span> | <span data-ttu-id="20e26-138">com.microsoft.autoupdate2</span><span class="sxs-lookup"><span data-stu-id="20e26-138">com.microsoft.autoupdate2</span></span> |
| <span data-ttu-id="20e26-139">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="20e26-139">**Key**</span></span> | <span data-ttu-id="20e26-140">ChannelName</span><span class="sxs-lookup"><span data-stu-id="20e26-140">ChannelName</span></span> |
| <span data-ttu-id="20e26-141">**Data type**</span><span class="sxs-lookup"><span data-stu-id="20e26-141">**Data type**</span></span> | <span data-ttu-id="20e26-142">Stringa</span><span class="sxs-lookup"><span data-stu-id="20e26-142">String</span></span> |
| <span data-ttu-id="20e26-143">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="20e26-143">**Possible values**</span></span> | <span data-ttu-id="20e26-144">Beta</span><span class="sxs-lookup"><span data-stu-id="20e26-144">Beta</span></span> <br/> <span data-ttu-id="20e26-145">Anteprima</span><span class="sxs-lookup"><span data-stu-id="20e26-145">Preview</span></span> <br/> <span data-ttu-id="20e26-146">Current</span><span class="sxs-lookup"><span data-stu-id="20e26-146">Current</span></span> |
|||

>[!WARNING]
><span data-ttu-id="20e26-147">Questa impostazione modifica il canale per tutte le applicazioni aggiornate tramite Microsoft AutoUpdate.</span><span class="sxs-lookup"><span data-stu-id="20e26-147">This setting changes the channel for all applications that are updated through Microsoft AutoUpdate.</span></span> <span data-ttu-id="20e26-148">Per modificare il canale solo per Microsoft Defender for Endpoint in macOS, esegui il comando seguente dopo la sostituzione `[channel-name]` con il canale desiderato:</span><span class="sxs-lookup"><span data-stu-id="20e26-148">To change the channel only for Microsoft Defender for Endpoint on macOS, execute the following command after replacing `[channel-name]` with the desired channel:</span></span>
> ```bash
> defaults write com.microsoft.autoupdate2 Applications -dict-add "/Applications/Microsoft Defender ATP.app" " { 'Application ID' = 'WDAV00' ; 'App Domain' = 'com.microsoft.wdav' ; LCID = 1033 ; ChannelName = '[channel-name]' ; }"
> ```

### <a name="set-update-check-frequency"></a><span data-ttu-id="20e26-149">Impostare la frequenza di controllo degli aggiornamenti</span><span class="sxs-lookup"><span data-stu-id="20e26-149">Set update check frequency</span></span>

<span data-ttu-id="20e26-150">Modificare la frequenza di ricerca degli aggiornamenti da parte di MAU.</span><span class="sxs-lookup"><span data-stu-id="20e26-150">Change how often MAU searches for updates.</span></span>

|<span data-ttu-id="20e26-151">Sezione</span><span class="sxs-lookup"><span data-stu-id="20e26-151">Section</span></span>|<span data-ttu-id="20e26-152">Valore</span><span class="sxs-lookup"><span data-stu-id="20e26-152">Value</span></span>|
|:--|:--|
| <span data-ttu-id="20e26-153">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="20e26-153">**Domain**</span></span> | <span data-ttu-id="20e26-154">com.microsoft.autoupdate2</span><span class="sxs-lookup"><span data-stu-id="20e26-154">com.microsoft.autoupdate2</span></span> |
| <span data-ttu-id="20e26-155">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="20e26-155">**Key**</span></span> | <span data-ttu-id="20e26-156">UpdateCheckFrequency</span><span class="sxs-lookup"><span data-stu-id="20e26-156">UpdateCheckFrequency</span></span> |
| <span data-ttu-id="20e26-157">**Data type**</span><span class="sxs-lookup"><span data-stu-id="20e26-157">**Data type**</span></span> | <span data-ttu-id="20e26-158">Numero intero</span><span class="sxs-lookup"><span data-stu-id="20e26-158">Integer</span></span> |
| <span data-ttu-id="20e26-159">**Valore predefinito**</span><span class="sxs-lookup"><span data-stu-id="20e26-159">**Default value**</span></span> | <span data-ttu-id="20e26-160">720 (minuti)</span><span class="sxs-lookup"><span data-stu-id="20e26-160">720 (minutes)</span></span> |
| <span data-ttu-id="20e26-161">**Commento**</span><span class="sxs-lookup"><span data-stu-id="20e26-161">**Comment**</span></span> | <span data-ttu-id="20e26-162">Questo valore è impostato in minuti.</span><span class="sxs-lookup"><span data-stu-id="20e26-162">This value is set in minutes.</span></span> |


### <a name="change-how-mau-interacts-with-updates"></a><span data-ttu-id="20e26-163">Modificare il modo in cui MAU interagisce con gli aggiornamenti</span><span class="sxs-lookup"><span data-stu-id="20e26-163">Change how MAU interacts with updates</span></span>

<span data-ttu-id="20e26-164">Modificare la modalità di ricerca degli aggiornamenti da parte di MAU.</span><span class="sxs-lookup"><span data-stu-id="20e26-164">Change how MAU searches for updates.</span></span>

|<span data-ttu-id="20e26-165">Sezione</span><span class="sxs-lookup"><span data-stu-id="20e26-165">Section</span></span>|<span data-ttu-id="20e26-166">Valore</span><span class="sxs-lookup"><span data-stu-id="20e26-166">Value</span></span>|
|:--|:--|
| <span data-ttu-id="20e26-167">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="20e26-167">**Domain**</span></span> | <span data-ttu-id="20e26-168">com.microsoft.autoupdate2</span><span class="sxs-lookup"><span data-stu-id="20e26-168">com.microsoft.autoupdate2</span></span> |
| <span data-ttu-id="20e26-169">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="20e26-169">**Key**</span></span> | <span data-ttu-id="20e26-170">HowToCheck</span><span class="sxs-lookup"><span data-stu-id="20e26-170">HowToCheck</span></span> |
| <span data-ttu-id="20e26-171">**Data type**</span><span class="sxs-lookup"><span data-stu-id="20e26-171">**Data type**</span></span> | <span data-ttu-id="20e26-172">Stringa</span><span class="sxs-lookup"><span data-stu-id="20e26-172">String</span></span> |
| <span data-ttu-id="20e26-173">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="20e26-173">**Possible values**</span></span> | <span data-ttu-id="20e26-174">Manuale</span><span class="sxs-lookup"><span data-stu-id="20e26-174">Manual</span></span> <br/> <span data-ttu-id="20e26-175">AutomaticCheck</span><span class="sxs-lookup"><span data-stu-id="20e26-175">AutomaticCheck</span></span> <br/> <span data-ttu-id="20e26-176">AutomaticDownload</span><span class="sxs-lookup"><span data-stu-id="20e26-176">AutomaticDownload</span></span> |
| <span data-ttu-id="20e26-177">**Commento**</span><span class="sxs-lookup"><span data-stu-id="20e26-177">**Comment**</span></span> |  <span data-ttu-id="20e26-178">Nota che AutomaticDownload farà un download e l'installazione invisibile all'utente, se possibile.</span><span class="sxs-lookup"><span data-stu-id="20e26-178">Note that AutomaticDownload will do a download and install silently if possible.</span></span> |


### <a name="change-whether-the-check-for-updates-button-is-enabled"></a><span data-ttu-id="20e26-179">Modificare se il pulsante "Controlla aggiornamenti" è abilitato</span><span class="sxs-lookup"><span data-stu-id="20e26-179">Change whether the "Check for Updates" button is enabled</span></span>

<span data-ttu-id="20e26-180">Modificare se gli utenti locali potranno fare clic sull'opzione "Controlla aggiornamenti" nell'interfaccia utente di Microsoft AutoUpdate.</span><span class="sxs-lookup"><span data-stu-id="20e26-180">Change whether local users will be able to click the "Check for Updates" option in the Microsoft AutoUpdate user interface.</span></span>

|<span data-ttu-id="20e26-181">Sezione</span><span class="sxs-lookup"><span data-stu-id="20e26-181">Section</span></span>|<span data-ttu-id="20e26-182">Valore</span><span class="sxs-lookup"><span data-stu-id="20e26-182">Value</span></span>|
|:--|:--|
| <span data-ttu-id="20e26-183">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="20e26-183">**Domain**</span></span> | <span data-ttu-id="20e26-184">com.microsoft.autoupdate2</span><span class="sxs-lookup"><span data-stu-id="20e26-184">com.microsoft.autoupdate2</span></span> |
| <span data-ttu-id="20e26-185">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="20e26-185">**Key**</span></span> | <span data-ttu-id="20e26-186">EnableCheckForUpdatesButton</span><span class="sxs-lookup"><span data-stu-id="20e26-186">EnableCheckForUpdatesButton</span></span> |
| <span data-ttu-id="20e26-187">**Data type**</span><span class="sxs-lookup"><span data-stu-id="20e26-187">**Data type**</span></span> | <span data-ttu-id="20e26-188">Booleano</span><span class="sxs-lookup"><span data-stu-id="20e26-188">Boolean</span></span> |
| <span data-ttu-id="20e26-189">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="20e26-189">**Possible values**</span></span> | <span data-ttu-id="20e26-190">True (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="20e26-190">True (default)</span></span> <br/> <span data-ttu-id="20e26-191">False</span><span class="sxs-lookup"><span data-stu-id="20e26-191">False</span></span> |


### <a name="disable-insider-checkbox"></a><span data-ttu-id="20e26-192">Casella di controllo Disattiva Insider</span><span class="sxs-lookup"><span data-stu-id="20e26-192">Disable Insider checkbox</span></span>

<span data-ttu-id="20e26-193">Impostare su true per rendere "Partecipa al programma Office Insider..." casella di controllo non disponibile/ disattivata per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="20e26-193">Set to true to make the "Join the Office Insider Program..." checkbox unavailable / greyed out to users.</span></span>

|<span data-ttu-id="20e26-194">Sezione</span><span class="sxs-lookup"><span data-stu-id="20e26-194">Section</span></span>|<span data-ttu-id="20e26-195">Valore</span><span class="sxs-lookup"><span data-stu-id="20e26-195">Value</span></span>|
|:--|:--|
| <span data-ttu-id="20e26-196">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="20e26-196">**Domain**</span></span> | <span data-ttu-id="20e26-197">com.microsoft.autoupdate2</span><span class="sxs-lookup"><span data-stu-id="20e26-197">com.microsoft.autoupdate2</span></span> |
| <span data-ttu-id="20e26-198">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="20e26-198">**Key**</span></span> | <span data-ttu-id="20e26-199">DisableInsiderCheckbox</span><span class="sxs-lookup"><span data-stu-id="20e26-199">DisableInsiderCheckbox</span></span> |
| <span data-ttu-id="20e26-200">**Data type**</span><span class="sxs-lookup"><span data-stu-id="20e26-200">**Data type**</span></span> | <span data-ttu-id="20e26-201">Booleano</span><span class="sxs-lookup"><span data-stu-id="20e26-201">Boolean</span></span> |
| <span data-ttu-id="20e26-202">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="20e26-202">**Possible values**</span></span> | <span data-ttu-id="20e26-203">False (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="20e26-203">False (default)</span></span> <br/> <span data-ttu-id="20e26-204">Vero</span><span class="sxs-lookup"><span data-stu-id="20e26-204">True</span></span> |


### <a name="limit-the-telemetry-that-is-sent-from-mau"></a><span data-ttu-id="20e26-205">Limitare la telemetria inviata da MAU</span><span class="sxs-lookup"><span data-stu-id="20e26-205">Limit the telemetry that is sent from MAU</span></span>

<span data-ttu-id="20e26-206">Impostare su false per inviare dati heartbeat minimi, nessun utilizzo dell'applicazione e nessun dettaglio dell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="20e26-206">Set to false to send minimal heartbeat data, no application usage, and no environment details.</span></span>

|<span data-ttu-id="20e26-207">Sezione</span><span class="sxs-lookup"><span data-stu-id="20e26-207">Section</span></span>|<span data-ttu-id="20e26-208">Valore</span><span class="sxs-lookup"><span data-stu-id="20e26-208">Value</span></span>|
|:--|:--|
| <span data-ttu-id="20e26-209">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="20e26-209">**Domain**</span></span> | <span data-ttu-id="20e26-210">com.microsoft.autoupdate2</span><span class="sxs-lookup"><span data-stu-id="20e26-210">com.microsoft.autoupdate2</span></span> |
| <span data-ttu-id="20e26-211">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="20e26-211">**Key**</span></span> | <span data-ttu-id="20e26-212">SendAllTelemetryEnabled</span><span class="sxs-lookup"><span data-stu-id="20e26-212">SendAllTelemetryEnabled</span></span> |
| <span data-ttu-id="20e26-213">**Data type**</span><span class="sxs-lookup"><span data-stu-id="20e26-213">**Data type**</span></span> | <span data-ttu-id="20e26-214">Booleano</span><span class="sxs-lookup"><span data-stu-id="20e26-214">Boolean</span></span> |
| <span data-ttu-id="20e26-215">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="20e26-215">**Possible values**</span></span> | <span data-ttu-id="20e26-216">True (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="20e26-216">True (default)</span></span> <br/> <span data-ttu-id="20e26-217">False</span><span class="sxs-lookup"><span data-stu-id="20e26-217">False</span></span> |


## <a name="example-configuration-profile"></a><span data-ttu-id="20e26-218">Profilo di configurazione di esempio</span><span class="sxs-lookup"><span data-stu-id="20e26-218">Example configuration profile</span></span>

<span data-ttu-id="20e26-219">Viene utilizzato il profilo di configurazione seguente per:</span><span class="sxs-lookup"><span data-stu-id="20e26-219">The following configuration profile is used to:</span></span>
- <span data-ttu-id="20e26-220">Posizionare il dispositivo nel canale Beta</span><span class="sxs-lookup"><span data-stu-id="20e26-220">Place the device in the Beta channel</span></span>
- <span data-ttu-id="20e26-221">Scaricare e installare automaticamente gli aggiornamenti</span><span class="sxs-lookup"><span data-stu-id="20e26-221">Automatically download and install updates</span></span>
- <span data-ttu-id="20e26-222">Abilitare il pulsante "Controlla aggiornamenti" nell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="20e26-222">Enable the "Check for updates" button in the user interface</span></span>
- <span data-ttu-id="20e26-223">Consenti agli utenti nel dispositivo di registrarsi nei canali Insider</span><span class="sxs-lookup"><span data-stu-id="20e26-223">Allow users on the device to enroll into the Insider channels</span></span>

### <a name="jamf"></a><span data-ttu-id="20e26-224">JAMF</span><span class="sxs-lookup"><span data-stu-id="20e26-224">JAMF</span></span>

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>ChannelName</key>
    <string>Beta</string>
    <key>HowToCheck</key>
    <string>AutomaticDownload</string>
    <key>EnableCheckForUpdatesButton</key>
    <true/>
    <key>DisableInsiderCheckbox</key>
    <false/>
    <key>SendAllTelemetryEnabled</key>
    <true/>
</dict>
</plist>
```

### <a name="intune"></a><span data-ttu-id="20e26-225">Intune</span><span class="sxs-lookup"><span data-stu-id="20e26-225">Intune</span></span>

```XML
<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1">
    <dict>
        <key>PayloadUUID</key>
        <string>B762FF60-6ACB-4A72-9E72-459D00C936F3</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>com.microsoft.autoupdate2</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft AutoUpdate settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft AutoUpdate configuration settings</string>
        <key>PayloadVersion</key>
        <integer>1</integer>
        <key>PayloadEnabled</key>
        <true/>
        <key>PayloadRemovalDisallowed</key>
        <true/>
        <key>PayloadScope</key>
        <string>System</string>
        <key>PayloadContent</key>
        <array>
            <dict>
            <key>PayloadUUID</key>
            <string>5A6F350A-CC2C-440B-A074-68E3F34EBAE9</string>
            <key>PayloadType</key>
            <string>com.microsoft.autoupdate2</string>
            <key>PayloadOrganization</key>
            <string>Microsoft</string>
            <key>PayloadIdentifier</key>
            <string>com.microsoft.autoupdate2</string>
            <key>PayloadDisplayName</key>
            <string>Microsoft AutoUpdate configuration settings</string>
            <key>PayloadDescription</key>
            <string/>
            <key>PayloadVersion</key>
            <integer>1</integer>
            <key>PayloadEnabled</key>
            <true/>
            <key>ChannelName</key>
            <string>Beta</string>
            <key>HowToCheck</key>
            <string>AutomaticDownload</string>
            <key>EnableCheckForUpdatesButton</key>
            <true/>
            <key>DisableInsiderCheckbox</key>
            <false/>
            <key>SendAllTelemetryEnabled</key>
            <true/>
            </dict>
        </array>
    </dict>
</plist>
```

<span data-ttu-id="20e26-226">Per configurare MAU, è possibile distribuire questo profilo di configurazione dallo strumento di gestione utilizzato dall'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="20e26-226">To configure MAU, you can deploy this configuration profile from the management tool that your enterprise is using:</span></span>
- <span data-ttu-id="20e26-227">Da JAMF carica questo profilo di configurazione e imposta dominio di preferenza *su com.microsoft.autoupdate2*.</span><span class="sxs-lookup"><span data-stu-id="20e26-227">From JAMF, upload this configuration profile and set the Preference Domain to *com.microsoft.autoupdate2*.</span></span>
- <span data-ttu-id="20e26-228">Da Intune carica questo profilo di configurazione e imposta il nome del profilo di configurazione personalizzato *su com.microsoft.autoupdate2*.</span><span class="sxs-lookup"><span data-stu-id="20e26-228">From Intune, upload this configuration profile and set the custom configuration profile name to *com.microsoft.autoupdate2*.</span></span>

## <a name="resources"></a><span data-ttu-id="20e26-229">Risorse</span><span class="sxs-lookup"><span data-stu-id="20e26-229">Resources</span></span>

- [<span data-ttu-id="20e26-230">riferimento msupdate</span><span class="sxs-lookup"><span data-stu-id="20e26-230">msupdate reference</span></span>](https://docs.microsoft.com/deployoffice/mac/update-office-for-mac-using-msupdate)
