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
ms.openlocfilehash: 99f507ad381ee21ba91753716439180fafe37c24
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51066306"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="e1476-104">Distribuire gli aggiornamenti per Microsoft Defender per Endpoint per Mac</span><span class="sxs-lookup"><span data-stu-id="e1476-104">Deploy updates for Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="e1476-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="e1476-105">**Applies to:**</span></span>

- [<span data-ttu-id="e1476-106">Microsoft Defender per Endpoint per Mac</span><span class="sxs-lookup"><span data-stu-id="e1476-106">Microsoft Defender for Endpoint for Mac</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="e1476-107">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="e1476-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e1476-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e1476-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="e1476-109">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="e1476-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e1476-110">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="e1476-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="e1476-111">Microsoft pubblica regolarmente aggiornamenti software per migliorare le prestazioni, la sicurezza e offrire nuove funzionalità.</span><span class="sxs-lookup"><span data-stu-id="e1476-111">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span>

<span data-ttu-id="e1476-112">Per aggiornare Microsoft Defender per Endpoint per Mac, viene utilizzato un programma denominato Microsoft AutoUpdate (MAU).</span><span class="sxs-lookup"><span data-stu-id="e1476-112">To update Microsoft Defender for Endpoint for Mac, a program named Microsoft AutoUpdate (MAU) is used.</span></span> <span data-ttu-id="e1476-113">Per impostazione predefinita, MAU controlla automaticamente la disponibilità di aggiornamenti ogni giorno, ma puoi modificarli in settimana, mensile o manualmente.</span><span class="sxs-lookup"><span data-stu-id="e1476-113">By default, MAU automatically checks for updates daily, but you can change that to weekly, monthly, or manually.</span></span>

![Schermata MAU](images/MDATP-34-MAU.png)

<span data-ttu-id="e1476-115">Se decidi di distribuire gli aggiornamenti usando gli strumenti di distribuzione del software, devi configurare MAU per controllare manualmente la disponibilità di aggiornamenti software.</span><span class="sxs-lookup"><span data-stu-id="e1476-115">If you decide to deploy updates by using your software distribution tools, you should configure MAU to manually check for software updates.</span></span> <span data-ttu-id="e1476-116">Puoi distribuire le preferenze per configurare come e quando MAU controlla la disponibilità di aggiornamenti per i Mac nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e1476-116">You can deploy preferences to configure how and when MAU checks for updates for the Macs in your organization.</span></span>

## <a name="use-msupdate"></a><span data-ttu-id="e1476-117">Utilizzare msupdate</span><span class="sxs-lookup"><span data-stu-id="e1476-117">Use msupdate</span></span>

<span data-ttu-id="e1476-118">MAU include uno strumento da riga di comando, denominato *msupdate,* progettato per gli amministratori IT in modo che abbia un controllo più preciso sulla modalità di applicazione degli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="e1476-118">MAU includes a command-line tool, called *msupdate*, that is designed for IT administrators so that they have more precise control over when updates are applied.</span></span> <span data-ttu-id="e1476-119">Le istruzioni per l'utilizzo di questo strumento sono disponibili in [Update Office for Mac by using msupdate](https://docs.microsoft.com/deployoffice/mac/update-office-for-mac-using-msupdate).</span><span class="sxs-lookup"><span data-stu-id="e1476-119">Instructions for how to use this tool can be found in [Update Office for Mac by using msupdate](https://docs.microsoft.com/deployoffice/mac/update-office-for-mac-using-msupdate).</span></span>

<span data-ttu-id="e1476-120">In MAU, l'identificatore dell'applicazione per Microsoft Defender per Endpoint per Mac è *WDAV00.*</span><span class="sxs-lookup"><span data-stu-id="e1476-120">In MAU, the application identifier for Microsoft Defender for Endpoint for Mac is *WDAV00*.</span></span> <span data-ttu-id="e1476-121">Per scaricare e installare gli aggiornamenti più recenti per Microsoft Defender per Endpoint per Mac, eseguire il comando seguente da una finestra del terminale:</span><span class="sxs-lookup"><span data-stu-id="e1476-121">To download and install the latest updates for Microsoft Defender for Endpoint for Mac, execute the following command from a Terminal window:</span></span>

```
./msupdate --install --apps wdav00
```

## <a name="set-preferences-for-microsoft-autoupdate"></a><span data-ttu-id="e1476-122">Impostare le preferenze per Microsoft AutoUpdate</span><span class="sxs-lookup"><span data-stu-id="e1476-122">Set preferences for Microsoft AutoUpdate</span></span>

<span data-ttu-id="e1476-123">Questa sezione descrive le preferenze più comuni che possono essere usate per configurare MAU.</span><span class="sxs-lookup"><span data-stu-id="e1476-123">This section describes the most common preferences that can be used to configure MAU.</span></span> <span data-ttu-id="e1476-124">Queste impostazioni possono essere distribuite come profilo di configurazione tramite la console di gestione utilizzata dall'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e1476-124">These settings can be deployed as a configuration profile through the management console that your enterprise is using.</span></span> <span data-ttu-id="e1476-125">Un esempio di profilo di configurazione è illustrato nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="e1476-125">An example of a configuration profile is shown in the following sections.</span></span>

### <a name="set-the-channel-name"></a><span data-ttu-id="e1476-126">Impostare il nome del canale</span><span class="sxs-lookup"><span data-stu-id="e1476-126">Set the channel name</span></span>

<span data-ttu-id="e1476-127">Il canale determina il tipo e la frequenza degli aggiornamenti offerti tramite MAU.</span><span class="sxs-lookup"><span data-stu-id="e1476-127">The channel determines the type and frequency of updates that are offered through MAU.</span></span> <span data-ttu-id="e1476-128">I dispositivi in `Beta` possono provare nuove funzionalità prima dei dispositivi in e `Preview` `Current` .</span><span class="sxs-lookup"><span data-stu-id="e1476-128">Devices in `Beta` can try out new features before devices in `Preview` and `Current`.</span></span> 

<span data-ttu-id="e1476-129">Il `Current` canale contiene la versione più stabile del prodotto.</span><span class="sxs-lookup"><span data-stu-id="e1476-129">The `Current` channel contains the most stable version of the product.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="e1476-130">Prima di Microsoft AutoUpdate versione 4.29, i canali avevano nomi diversi:</span><span class="sxs-lookup"><span data-stu-id="e1476-130">Prior to Microsoft AutoUpdate version 4.29, channels had different names:</span></span> 
> 
> - <span data-ttu-id="e1476-131">`Beta` è stato `InsiderFast` denominato (Insider Fast)</span><span class="sxs-lookup"><span data-stu-id="e1476-131">`Beta` was named `InsiderFast` (Insider Fast)</span></span>
> - <span data-ttu-id="e1476-132">`Preview` è stato `External` denominato (Insider Slow)</span><span class="sxs-lookup"><span data-stu-id="e1476-132">`Preview` was named `External` (Insider Slow)</span></span>
> - <span data-ttu-id="e1476-133">`Current` è stato denominato `Production`</span><span class="sxs-lookup"><span data-stu-id="e1476-133">`Current` was named `Production`</span></span>

>[!TIP]
><span data-ttu-id="e1476-134">Per visualizzare in anteprima le nuove funzionalità e fornire feedback anticipato, è consigliabile configurare alcuni dispositivi dell'organizzazione in `Beta` o `Preview` .</span><span class="sxs-lookup"><span data-stu-id="e1476-134">In order to preview new features and provide early feedback, it is recommended that you configure some devices in your enterprise to `Beta` or `Preview`.</span></span>

|||
|:--|:--|
| <span data-ttu-id="e1476-135">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="e1476-135">**Domain**</span></span> | <span data-ttu-id="e1476-136">com.microsoft.autoupdate2</span><span class="sxs-lookup"><span data-stu-id="e1476-136">com.microsoft.autoupdate2</span></span> |
| <span data-ttu-id="e1476-137">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="e1476-137">**Key**</span></span> | <span data-ttu-id="e1476-138">ChannelName</span><span class="sxs-lookup"><span data-stu-id="e1476-138">ChannelName</span></span> |
| <span data-ttu-id="e1476-139">**Data type**</span><span class="sxs-lookup"><span data-stu-id="e1476-139">**Data type**</span></span> | <span data-ttu-id="e1476-140">Stringa</span><span class="sxs-lookup"><span data-stu-id="e1476-140">String</span></span> |
| <span data-ttu-id="e1476-141">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="e1476-141">**Possible values**</span></span> | <span data-ttu-id="e1476-142">Beta</span><span class="sxs-lookup"><span data-stu-id="e1476-142">Beta</span></span> <br/> <span data-ttu-id="e1476-143">Anteprima</span><span class="sxs-lookup"><span data-stu-id="e1476-143">Preview</span></span> <br/> <span data-ttu-id="e1476-144">Current</span><span class="sxs-lookup"><span data-stu-id="e1476-144">Current</span></span> |
|||

>[!WARNING]
><span data-ttu-id="e1476-145">Questa impostazione modifica il canale per tutte le applicazioni aggiornate tramite Microsoft AutoUpdate.</span><span class="sxs-lookup"><span data-stu-id="e1476-145">This setting changes the channel for all applications that are updated through Microsoft AutoUpdate.</span></span> <span data-ttu-id="e1476-146">Per modificare il canale solo per Microsoft Defender per Endpoint per Mac, esegui il comando seguente dopo la sostituzione `[channel-name]` con il canale desiderato:</span><span class="sxs-lookup"><span data-stu-id="e1476-146">To change the channel only for Microsoft Defender for Endpoint for Mac, execute the following command after replacing `[channel-name]` with the desired channel:</span></span>
> ```bash
> defaults write com.microsoft.autoupdate2 Applications -dict-add "/Applications/Microsoft Defender ATP.app" " { 'Application ID' = 'WDAV00' ; 'App Domain' = 'com.microsoft.wdav' ; LCID = 1033 ; ChannelName = '[channel-name]' ; }"
> ```

### <a name="set-update-check-frequency"></a><span data-ttu-id="e1476-147">Impostare la frequenza di controllo degli aggiornamenti</span><span class="sxs-lookup"><span data-stu-id="e1476-147">Set update check frequency</span></span>

<span data-ttu-id="e1476-148">Modificare la frequenza di ricerca degli aggiornamenti da parte di MAU.</span><span class="sxs-lookup"><span data-stu-id="e1476-148">Change how often MAU searches for updates.</span></span>

|||
|:--|:--|
| <span data-ttu-id="e1476-149">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="e1476-149">**Domain**</span></span> | <span data-ttu-id="e1476-150">com.microsoft.autoupdate2</span><span class="sxs-lookup"><span data-stu-id="e1476-150">com.microsoft.autoupdate2</span></span> |
| <span data-ttu-id="e1476-151">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="e1476-151">**Key**</span></span> | <span data-ttu-id="e1476-152">UpdateCheckFrequency</span><span class="sxs-lookup"><span data-stu-id="e1476-152">UpdateCheckFrequency</span></span> |
| <span data-ttu-id="e1476-153">**Data type**</span><span class="sxs-lookup"><span data-stu-id="e1476-153">**Data type**</span></span> | <span data-ttu-id="e1476-154">Numero intero</span><span class="sxs-lookup"><span data-stu-id="e1476-154">Integer</span></span> |
| <span data-ttu-id="e1476-155">**Valore predefinito**</span><span class="sxs-lookup"><span data-stu-id="e1476-155">**Default value**</span></span> | <span data-ttu-id="e1476-156">720 (minuti)</span><span class="sxs-lookup"><span data-stu-id="e1476-156">720 (minutes)</span></span> |
| <span data-ttu-id="e1476-157">**Commento**</span><span class="sxs-lookup"><span data-stu-id="e1476-157">**Comment**</span></span> | <span data-ttu-id="e1476-158">Questo valore è impostato in minuti.</span><span class="sxs-lookup"><span data-stu-id="e1476-158">This value is set in minutes.</span></span> |
|||

### <a name="change-how-mau-interacts-with-updates"></a><span data-ttu-id="e1476-159">Modificare il modo in cui MAU interagisce con gli aggiornamenti</span><span class="sxs-lookup"><span data-stu-id="e1476-159">Change how MAU interacts with updates</span></span>

<span data-ttu-id="e1476-160">Modificare la modalità di ricerca degli aggiornamenti da parte di MAU.</span><span class="sxs-lookup"><span data-stu-id="e1476-160">Change how MAU searches for updates.</span></span>

|||
|:--|:--|
| <span data-ttu-id="e1476-161">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="e1476-161">**Domain**</span></span> | <span data-ttu-id="e1476-162">com.microsoft.autoupdate2</span><span class="sxs-lookup"><span data-stu-id="e1476-162">com.microsoft.autoupdate2</span></span> |
| <span data-ttu-id="e1476-163">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="e1476-163">**Key**</span></span> | <span data-ttu-id="e1476-164">HowToCheck</span><span class="sxs-lookup"><span data-stu-id="e1476-164">HowToCheck</span></span> |
| <span data-ttu-id="e1476-165">**Data type**</span><span class="sxs-lookup"><span data-stu-id="e1476-165">**Data type**</span></span> | <span data-ttu-id="e1476-166">Stringa</span><span class="sxs-lookup"><span data-stu-id="e1476-166">String</span></span> |
| <span data-ttu-id="e1476-167">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="e1476-167">**Possible values**</span></span> | <span data-ttu-id="e1476-168">Manuale</span><span class="sxs-lookup"><span data-stu-id="e1476-168">Manual</span></span> <br/> <span data-ttu-id="e1476-169">AutomaticCheck</span><span class="sxs-lookup"><span data-stu-id="e1476-169">AutomaticCheck</span></span> <br/> <span data-ttu-id="e1476-170">AutomaticDownload</span><span class="sxs-lookup"><span data-stu-id="e1476-170">AutomaticDownload</span></span> |
| <span data-ttu-id="e1476-171">**Commento**</span><span class="sxs-lookup"><span data-stu-id="e1476-171">**Comment**</span></span> |  <span data-ttu-id="e1476-172">Nota che AutomaticDownload farà un download e l'installazione invisibile all'utente, se possibile.</span><span class="sxs-lookup"><span data-stu-id="e1476-172">Note that AutomaticDownload will do a download and install silently if possible.</span></span> |
|||

### <a name="change-whether-the-check-for-updates-button-is-enabled"></a><span data-ttu-id="e1476-173">Modificare se il pulsante "Controlla aggiornamenti" è abilitato</span><span class="sxs-lookup"><span data-stu-id="e1476-173">Change whether the "Check for Updates" button is enabled</span></span>

<span data-ttu-id="e1476-174">Modificare se gli utenti locali potranno fare clic sull'opzione "Controlla aggiornamenti" nell'interfaccia utente di Microsoft AutoUpdate.</span><span class="sxs-lookup"><span data-stu-id="e1476-174">Change whether local users will be able to click the "Check for Updates" option in the Microsoft AutoUpdate user interface.</span></span>

|||
|:--|:--|
| <span data-ttu-id="e1476-175">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="e1476-175">**Domain**</span></span> | <span data-ttu-id="e1476-176">com.microsoft.autoupdate2</span><span class="sxs-lookup"><span data-stu-id="e1476-176">com.microsoft.autoupdate2</span></span> |
| <span data-ttu-id="e1476-177">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="e1476-177">**Key**</span></span> | <span data-ttu-id="e1476-178">EnableCheckForUpdatesButton</span><span class="sxs-lookup"><span data-stu-id="e1476-178">EnableCheckForUpdatesButton</span></span> |
| <span data-ttu-id="e1476-179">**Data type**</span><span class="sxs-lookup"><span data-stu-id="e1476-179">**Data type**</span></span> | <span data-ttu-id="e1476-180">Booleano</span><span class="sxs-lookup"><span data-stu-id="e1476-180">Boolean</span></span> |
| <span data-ttu-id="e1476-181">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="e1476-181">**Possible values**</span></span> | <span data-ttu-id="e1476-182">True (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="e1476-182">True (default)</span></span> <br/> <span data-ttu-id="e1476-183">False</span><span class="sxs-lookup"><span data-stu-id="e1476-183">False</span></span> |
|||

### <a name="disable-insider-checkbox"></a><span data-ttu-id="e1476-184">Casella di controllo Disattiva Insider</span><span class="sxs-lookup"><span data-stu-id="e1476-184">Disable Insider checkbox</span></span>

<span data-ttu-id="e1476-185">Impostare su true per rendere "Partecipa al programma Office Insider..." casella di controllo non disponibile/ disattivata per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="e1476-185">Set to true to make the "Join the Office Insider Program..." checkbox unavailable / greyed out to users.</span></span>

|||
|:--|:--|
| <span data-ttu-id="e1476-186">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="e1476-186">**Domain**</span></span> | <span data-ttu-id="e1476-187">com.microsoft.autoupdate2</span><span class="sxs-lookup"><span data-stu-id="e1476-187">com.microsoft.autoupdate2</span></span> |
| <span data-ttu-id="e1476-188">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="e1476-188">**Key**</span></span> | <span data-ttu-id="e1476-189">DisableInsiderCheckbox</span><span class="sxs-lookup"><span data-stu-id="e1476-189">DisableInsiderCheckbox</span></span> |
| <span data-ttu-id="e1476-190">**Data type**</span><span class="sxs-lookup"><span data-stu-id="e1476-190">**Data type**</span></span> | <span data-ttu-id="e1476-191">Booleano</span><span class="sxs-lookup"><span data-stu-id="e1476-191">Boolean</span></span> |
| <span data-ttu-id="e1476-192">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="e1476-192">**Possible values**</span></span> | <span data-ttu-id="e1476-193">False (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="e1476-193">False (default)</span></span> <br/> <span data-ttu-id="e1476-194">Vero</span><span class="sxs-lookup"><span data-stu-id="e1476-194">True</span></span> |
|||

### <a name="limit-the-telemetry-that-is-sent-from-mau"></a><span data-ttu-id="e1476-195">Limitare la telemetria inviata da MAU</span><span class="sxs-lookup"><span data-stu-id="e1476-195">Limit the telemetry that is sent from MAU</span></span>

<span data-ttu-id="e1476-196">Impostare su false per inviare dati heartbeat minimi, nessun utilizzo dell'applicazione e nessun dettaglio dell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="e1476-196">Set to false to send minimal heartbeat data, no application usage, and no environment details.</span></span>

|||
|:--|:--|
| <span data-ttu-id="e1476-197">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="e1476-197">**Domain**</span></span> | <span data-ttu-id="e1476-198">com.microsoft.autoupdate2</span><span class="sxs-lookup"><span data-stu-id="e1476-198">com.microsoft.autoupdate2</span></span> |
| <span data-ttu-id="e1476-199">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="e1476-199">**Key**</span></span> | <span data-ttu-id="e1476-200">SendAllTelemetryEnabled</span><span class="sxs-lookup"><span data-stu-id="e1476-200">SendAllTelemetryEnabled</span></span> |
| <span data-ttu-id="e1476-201">**Data type**</span><span class="sxs-lookup"><span data-stu-id="e1476-201">**Data type**</span></span> | <span data-ttu-id="e1476-202">Booleano</span><span class="sxs-lookup"><span data-stu-id="e1476-202">Boolean</span></span> |
| <span data-ttu-id="e1476-203">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="e1476-203">**Possible values**</span></span> | <span data-ttu-id="e1476-204">True (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="e1476-204">True (default)</span></span> <br/> <span data-ttu-id="e1476-205">False</span><span class="sxs-lookup"><span data-stu-id="e1476-205">False</span></span> |
|||

## <a name="example-configuration-profile"></a><span data-ttu-id="e1476-206">Profilo di configurazione di esempio</span><span class="sxs-lookup"><span data-stu-id="e1476-206">Example configuration profile</span></span>

<span data-ttu-id="e1476-207">Viene utilizzato il profilo di configurazione seguente per:</span><span class="sxs-lookup"><span data-stu-id="e1476-207">The following configuration profile is used to:</span></span>
- <span data-ttu-id="e1476-208">Posizionare il dispositivo nel canale Beta</span><span class="sxs-lookup"><span data-stu-id="e1476-208">Place the device in the Beta channel</span></span>
- <span data-ttu-id="e1476-209">Scaricare e installare automaticamente gli aggiornamenti</span><span class="sxs-lookup"><span data-stu-id="e1476-209">Automatically download and install updates</span></span>
- <span data-ttu-id="e1476-210">Abilitare il pulsante "Controlla aggiornamenti" nell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="e1476-210">Enable the "Check for updates" button in the user interface</span></span>
- <span data-ttu-id="e1476-211">Consenti agli utenti nel dispositivo di registrarsi nei canali Insider</span><span class="sxs-lookup"><span data-stu-id="e1476-211">Allow users on the device to enroll into the Insider channels</span></span>

### <a name="jamf"></a><span data-ttu-id="e1476-212">JAMF</span><span class="sxs-lookup"><span data-stu-id="e1476-212">JAMF</span></span>

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

### <a name="intune"></a><span data-ttu-id="e1476-213">Intune</span><span class="sxs-lookup"><span data-stu-id="e1476-213">Intune</span></span>

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

<span data-ttu-id="e1476-214">Per configurare MAU, è possibile distribuire questo profilo di configurazione dallo strumento di gestione utilizzato dall'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="e1476-214">To configure MAU, you can deploy this configuration profile from the management tool that your enterprise is using:</span></span>
- <span data-ttu-id="e1476-215">Da JAMF carica questo profilo di configurazione e imposta dominio di preferenza *su com.microsoft.autoupdate2*.</span><span class="sxs-lookup"><span data-stu-id="e1476-215">From JAMF, upload this configuration profile and set the Preference Domain to *com.microsoft.autoupdate2*.</span></span>
- <span data-ttu-id="e1476-216">Da Intune carica questo profilo di configurazione e imposta il nome del profilo di configurazione personalizzato *su com.microsoft.autoupdate2*.</span><span class="sxs-lookup"><span data-stu-id="e1476-216">From Intune, upload this configuration profile and set the custom configuration profile name to *com.microsoft.autoupdate2*.</span></span>

## <a name="resources"></a><span data-ttu-id="e1476-217">Risorse</span><span class="sxs-lookup"><span data-stu-id="e1476-217">Resources</span></span>

- [<span data-ttu-id="e1476-218">riferimento msupdate</span><span class="sxs-lookup"><span data-stu-id="e1476-218">msupdate reference</span></span>](https://docs.microsoft.com/deployoffice/mac/update-office-for-mac-using-msupdate)
