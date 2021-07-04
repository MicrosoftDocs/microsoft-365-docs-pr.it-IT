---
title: Impostare le preferenze per Microsoft Defender per Endpoint su Linux
ms.reviewer: ''
description: Descrive come configurare Microsoft Defender per Endpoint su Linux nelle aziende.
keywords: microsoft, defender, Microsoft Defender for Endpoint, linux, installazione, distribuire, disinstallazione, pupazzo, ansible, linux, redhat, ubuntu, debian, sles, suse, centos
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
ms.openlocfilehash: 7998e878ad03fdfb64c314dc8b7234ece46164ce
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289494"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="1b2c9-104">Impostare le preferenze per Microsoft Defender per Endpoint su Linux</span><span class="sxs-lookup"><span data-stu-id="1b2c9-104">Set preferences for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="1b2c9-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-105">**Applies to:**</span></span>
- [<span data-ttu-id="1b2c9-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="1b2c9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1b2c9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1b2c9-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="1b2c9-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="1b2c9-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="1b2c9-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="1b2c9-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

> [!IMPORTANT]
> <span data-ttu-id="1b2c9-110">Questo argomento contiene istruzioni su come impostare le preferenze per Defender per Endpoint in Linux in ambienti aziendali.</span><span class="sxs-lookup"><span data-stu-id="1b2c9-110">This topic contains instructions for how to set preferences for Defender for Endpoint on Linux in enterprise environments.</span></span> <span data-ttu-id="1b2c9-111">Se si desidera configurare il prodotto in un dispositivo dalla riga di comando, vedere [Resources](linux-resources.md#configure-from-the-command-line).</span><span class="sxs-lookup"><span data-stu-id="1b2c9-111">If you are interested in configuring the product on a device from the command-line, see [Resources](linux-resources.md#configure-from-the-command-line).</span></span>

<span data-ttu-id="1b2c9-112">In ambienti aziendali, Defender per Endpoint su Linux può essere gestito tramite un profilo di configurazione.</span><span class="sxs-lookup"><span data-stu-id="1b2c9-112">In enterprise environments, Defender for Endpoint on Linux can be managed through a configuration profile.</span></span> <span data-ttu-id="1b2c9-113">Questo profilo viene distribuito dallo strumento di gestione scelto.</span><span class="sxs-lookup"><span data-stu-id="1b2c9-113">This profile is deployed from the management tool of your choice.</span></span> <span data-ttu-id="1b2c9-114">Le preferenze gestite dall'organizzazione hanno la precedenza su quelle impostate localmente nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1b2c9-114">Preferences managed by the enterprise take precedence over the ones set locally on the device.</span></span> <span data-ttu-id="1b2c9-115">In altre parole, gli utenti dell'organizzazione non sono in grado di modificare le preferenze impostate tramite questo profilo di configurazione.</span><span class="sxs-lookup"><span data-stu-id="1b2c9-115">In other words, users in your enterprise are not able to change preferences that are set through this configuration profile.</span></span>

<span data-ttu-id="1b2c9-116">Questo articolo descrive la struttura di questo profilo (incluso un profilo consigliato che puoi usare per iniziare) e le istruzioni su come distribuire il profilo.</span><span class="sxs-lookup"><span data-stu-id="1b2c9-116">This article describes the structure of this profile (including a recommended profile that you can use to get started) and instructions on how to deploy the profile.</span></span>

## <a name="configuration-profile-structure"></a><span data-ttu-id="1b2c9-117">Struttura del profilo di configurazione</span><span class="sxs-lookup"><span data-stu-id="1b2c9-117">Configuration profile structure</span></span>

<span data-ttu-id="1b2c9-118">Il profilo di configurazione è un file JSON costituito da voci identificate da una chiave (che indica il nome della preferenza), seguita da un valore, che dipende dalla natura della preferenza.</span><span class="sxs-lookup"><span data-stu-id="1b2c9-118">The configuration profile is a .json file that consists of entries identified by a key (which denotes the name of the preference), followed by a value, which depends on the nature of the preference.</span></span> <span data-ttu-id="1b2c9-119">I valori possono essere semplici, ad esempio un valore numerico o complessi, ad esempio un elenco nidificato di preferenze.</span><span class="sxs-lookup"><span data-stu-id="1b2c9-119">Values can be simple, such as a numerical value, or complex, such as a nested list of preferences.</span></span>

<span data-ttu-id="1b2c9-120">In genere, si utilizza uno strumento di gestione della configurazione per eseguire il push di un file con il nome ```mdatp_managed.json``` nel percorso ```/etc/opt/microsoft/mdatp/managed/``` .</span><span class="sxs-lookup"><span data-stu-id="1b2c9-120">Typically, you would use a configuration management tool to push a file with the name ```mdatp_managed.json``` at the location ```/etc/opt/microsoft/mdatp/managed/```.</span></span>

<span data-ttu-id="1b2c9-121">Il livello superiore del profilo di configurazione include le preferenze e le voci a livello di prodotto per le sottoaree del prodotto, che vengono illustrate in modo più dettagliato nelle sezioni successive.</span><span class="sxs-lookup"><span data-stu-id="1b2c9-121">The top level of the configuration profile includes product-wide preferences and entries for subareas of the product, which are explained in more detail in the next sections.</span></span>

### <a name="antivirus-engine-preferences"></a><span data-ttu-id="1b2c9-122">Preferenze del motore antivirus</span><span class="sxs-lookup"><span data-stu-id="1b2c9-122">Antivirus engine preferences</span></span>

<span data-ttu-id="1b2c9-123">La *sezione antivirusEngine* del profilo di configurazione viene utilizzata per gestire le preferenze del componente antivirus del prodotto.</span><span class="sxs-lookup"><span data-stu-id="1b2c9-123">The *antivirusEngine* section of the configuration profile is used to manage the preferences of the antivirus component of the product.</span></span>

<br>

****

|<span data-ttu-id="1b2c9-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1b2c9-124">Description</span></span>|<span data-ttu-id="1b2c9-125">Valore</span><span class="sxs-lookup"><span data-stu-id="1b2c9-125">Value</span></span>|
|---|---|
|<span data-ttu-id="1b2c9-126">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-126">**Key**</span></span>|<span data-ttu-id="1b2c9-127">antivirusEngine</span><span class="sxs-lookup"><span data-stu-id="1b2c9-127">antivirusEngine</span></span>|
|<span data-ttu-id="1b2c9-128">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-128">**Data type**</span></span>|<span data-ttu-id="1b2c9-129">Dizionario (preferenza annidata)</span><span class="sxs-lookup"><span data-stu-id="1b2c9-129">Dictionary (nested preference)</span></span>|
|<span data-ttu-id="1b2c9-130">**Comments**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-130">**Comments**</span></span>|<span data-ttu-id="1b2c9-131">Per una descrizione del contenuto del dizionario, vedi le sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="1b2c9-131">See the following sections for a description of the dictionary contents.</span></span>|
|

#### <a name="enable--disable-real-time-protection"></a><span data-ttu-id="1b2c9-132">Abilitare/disabilitare la protezione in tempo reale</span><span class="sxs-lookup"><span data-stu-id="1b2c9-132">Enable / disable real-time protection</span></span>

<span data-ttu-id="1b2c9-133">Determina se la protezione in tempo reale (analizza i file quando vi si accede) è abilitata o meno.</span><span class="sxs-lookup"><span data-stu-id="1b2c9-133">Determines whether real-time protection (scan files as they are accessed) is enabled or not.</span></span>

<br>

****

|<span data-ttu-id="1b2c9-134">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1b2c9-134">Description</span></span>|<span data-ttu-id="1b2c9-135">Valore</span><span class="sxs-lookup"><span data-stu-id="1b2c9-135">Value</span></span>|
|---|---|
|<span data-ttu-id="1b2c9-136">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-136">**Key**</span></span>|<span data-ttu-id="1b2c9-137">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="1b2c9-137">enableRealTimeProtection</span></span>|
|<span data-ttu-id="1b2c9-138">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-138">**Data type**</span></span>|<span data-ttu-id="1b2c9-139">Booleano</span><span class="sxs-lookup"><span data-stu-id="1b2c9-139">Boolean</span></span>|
|<span data-ttu-id="1b2c9-140">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-140">**Possible values**</span></span>|<span data-ttu-id="1b2c9-141">true (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="1b2c9-141">true (default)</span></span> <p> <span data-ttu-id="1b2c9-142">false</span><span class="sxs-lookup"><span data-stu-id="1b2c9-142">false</span></span>|
|

#### <a name="enable--disable-passive-mode"></a><span data-ttu-id="1b2c9-143">Abilitare/disabilitare la modalità passiva</span><span class="sxs-lookup"><span data-stu-id="1b2c9-143">Enable / disable passive mode</span></span>

<span data-ttu-id="1b2c9-144">Determina se il motore antivirus viene eseguito in modalità passiva o meno.</span><span class="sxs-lookup"><span data-stu-id="1b2c9-144">Determines whether the antivirus engine runs in passive mode or not.</span></span> <span data-ttu-id="1b2c9-145">In modalità passiva:</span><span class="sxs-lookup"><span data-stu-id="1b2c9-145">In passive mode:</span></span>

- <span data-ttu-id="1b2c9-146">La protezione in tempo reale è disattivata.</span><span class="sxs-lookup"><span data-stu-id="1b2c9-146">Real-time protection is turned off.</span></span>
- <span data-ttu-id="1b2c9-147">L'analisi su richiesta è attivata.</span><span class="sxs-lookup"><span data-stu-id="1b2c9-147">On-demand scanning is turned on.</span></span>
- <span data-ttu-id="1b2c9-148">La correzione automatica delle minacce è disattivata.</span><span class="sxs-lookup"><span data-stu-id="1b2c9-148">Automatic threat remediation is turned off.</span></span>
- <span data-ttu-id="1b2c9-149">Gli aggiornamenti delle funzionalità di intelligence per la sicurezza sono attivati.</span><span class="sxs-lookup"><span data-stu-id="1b2c9-149">Security intelligence updates are turned on.</span></span>
- <span data-ttu-id="1b2c9-150">L'icona del menu Stato è nascosta.</span><span class="sxs-lookup"><span data-stu-id="1b2c9-150">Status menu icon is hidden.</span></span>

<br>

****

|<span data-ttu-id="1b2c9-151">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1b2c9-151">Description</span></span>|<span data-ttu-id="1b2c9-152">Valore</span><span class="sxs-lookup"><span data-stu-id="1b2c9-152">Value</span></span>|
|---|---|
|<span data-ttu-id="1b2c9-153">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-153">**Key**</span></span>|<span data-ttu-id="1b2c9-154">passiveMode</span><span class="sxs-lookup"><span data-stu-id="1b2c9-154">passiveMode</span></span>|
|<span data-ttu-id="1b2c9-155">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-155">**Data type**</span></span>|<span data-ttu-id="1b2c9-156">Booleano</span><span class="sxs-lookup"><span data-stu-id="1b2c9-156">Boolean</span></span>|
|<span data-ttu-id="1b2c9-157">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-157">**Possible values**</span></span>|<span data-ttu-id="1b2c9-158">false (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="1b2c9-158">false (default)</span></span> <p> <span data-ttu-id="1b2c9-159">true</span><span class="sxs-lookup"><span data-stu-id="1b2c9-159">true</span></span>|
|<span data-ttu-id="1b2c9-160">**Comments**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-160">**Comments**</span></span>|<span data-ttu-id="1b2c9-161">Disponibile in Defender per Endpoint versione 100.67.60 o successiva.</span><span class="sxs-lookup"><span data-stu-id="1b2c9-161">Available in Defender for Endpoint version 100.67.60 or higher.</span></span>|
|

#### <a name="exclusion-merge-policy"></a><span data-ttu-id="1b2c9-162">Criteri di unione esclusioni</span><span class="sxs-lookup"><span data-stu-id="1b2c9-162">Exclusion merge policy</span></span>

<span data-ttu-id="1b2c9-163">Specifica i criteri di unione per le esclusioni.</span><span class="sxs-lookup"><span data-stu-id="1b2c9-163">Specifies the merge policy for exclusions.</span></span> <span data-ttu-id="1b2c9-164">Può essere una combinazione di esclusioni definite dall'amministratore e definite dall'utente ( ) o solo esclusioni definite `merge` dall'amministratore ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="1b2c9-164">It can be a combination of administrator-defined and user-defined exclusions (`merge`) or only administrator-defined exclusions (`admin_only`).</span></span> <span data-ttu-id="1b2c9-165">Questa impostazione può essere utilizzata per impedire agli utenti locali di definire le proprie esclusioni.</span><span class="sxs-lookup"><span data-stu-id="1b2c9-165">This setting can be used to restrict local users from defining their own exclusions.</span></span>

<br>

****

|<span data-ttu-id="1b2c9-166">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1b2c9-166">Description</span></span>|<span data-ttu-id="1b2c9-167">Valore</span><span class="sxs-lookup"><span data-stu-id="1b2c9-167">Value</span></span>|
|---|---|
|<span data-ttu-id="1b2c9-168">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-168">**Key**</span></span>|<span data-ttu-id="1b2c9-169">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="1b2c9-169">exclusionsMergePolicy</span></span>|
|<span data-ttu-id="1b2c9-170">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-170">**Data type**</span></span>|<span data-ttu-id="1b2c9-171">Stringa</span><span class="sxs-lookup"><span data-stu-id="1b2c9-171">String</span></span>|
|<span data-ttu-id="1b2c9-172">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-172">**Possible values**</span></span>|<span data-ttu-id="1b2c9-173">merge (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="1b2c9-173">merge (default)</span></span> <p> <span data-ttu-id="1b2c9-174">admin_only</span><span class="sxs-lookup"><span data-stu-id="1b2c9-174">admin_only</span></span>|
|<span data-ttu-id="1b2c9-175">**Comments**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-175">**Comments**</span></span>|<span data-ttu-id="1b2c9-176">Disponibile in Defender per Endpoint versione 100.83.73 o successiva.</span><span class="sxs-lookup"><span data-stu-id="1b2c9-176">Available in Defender for Endpoint version 100.83.73 or higher.</span></span>|
|

#### <a name="scan-exclusions"></a><span data-ttu-id="1b2c9-177">Esclusioni analisi</span><span class="sxs-lookup"><span data-stu-id="1b2c9-177">Scan exclusions</span></span>

<span data-ttu-id="1b2c9-178">Entità escluse dall'analisi.</span><span class="sxs-lookup"><span data-stu-id="1b2c9-178">Entities that have been excluded from the scan.</span></span> <span data-ttu-id="1b2c9-179">Le esclusioni possono essere specificate da percorsi completi, estensioni o nomi di file.</span><span class="sxs-lookup"><span data-stu-id="1b2c9-179">Exclusions can be specified by full paths, extensions, or file names.</span></span>
<span data-ttu-id="1b2c9-180">Le esclusioni vengono specificate come matrice di elementi, l'amministratore può specificare il numero di elementi necessario, in qualsiasi ordine.</span><span class="sxs-lookup"><span data-stu-id="1b2c9-180">(Exclusions are specified as an array of items, administrator can specify as many elements as necessary, in any order.)</span></span>

<br>

****

|<span data-ttu-id="1b2c9-181">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1b2c9-181">Description</span></span>|<span data-ttu-id="1b2c9-182">Valore</span><span class="sxs-lookup"><span data-stu-id="1b2c9-182">Value</span></span>|
|---|---|
|<span data-ttu-id="1b2c9-183">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-183">**Key**</span></span>|<span data-ttu-id="1b2c9-184">esclusioni</span><span class="sxs-lookup"><span data-stu-id="1b2c9-184">exclusions</span></span>|
|<span data-ttu-id="1b2c9-185">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-185">**Data type**</span></span>|<span data-ttu-id="1b2c9-186">Dizionario (preferenza annidata)</span><span class="sxs-lookup"><span data-stu-id="1b2c9-186">Dictionary (nested preference)</span></span>|
|<span data-ttu-id="1b2c9-187">**Comments**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-187">**Comments**</span></span>|<span data-ttu-id="1b2c9-188">Per una descrizione del contenuto del dizionario, vedi le sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="1b2c9-188">See the following sections for a description of the dictionary contents.</span></span>|
|

##### <a name="type-of-exclusion"></a><span data-ttu-id="1b2c9-189">Tipo di esclusione</span><span class="sxs-lookup"><span data-stu-id="1b2c9-189">Type of exclusion</span></span>

<span data-ttu-id="1b2c9-190">Specifica il tipo di contenuto escluso dall'analisi.</span><span class="sxs-lookup"><span data-stu-id="1b2c9-190">Specifies the type of content excluded from the scan.</span></span>

<br>

****

|<span data-ttu-id="1b2c9-191">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1b2c9-191">Description</span></span>|<span data-ttu-id="1b2c9-192">Valore</span><span class="sxs-lookup"><span data-stu-id="1b2c9-192">Value</span></span>|
|---|---|
|<span data-ttu-id="1b2c9-193">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-193">**Key**</span></span>|<span data-ttu-id="1b2c9-194">$type</span><span class="sxs-lookup"><span data-stu-id="1b2c9-194">$type</span></span>|
|<span data-ttu-id="1b2c9-195">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-195">**Data type**</span></span>|<span data-ttu-id="1b2c9-196">Stringa</span><span class="sxs-lookup"><span data-stu-id="1b2c9-196">String</span></span>|
|<span data-ttu-id="1b2c9-197">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-197">**Possible values**</span></span>|<span data-ttu-id="1b2c9-198">excludedPath</span><span class="sxs-lookup"><span data-stu-id="1b2c9-198">excludedPath</span></span> <p> <span data-ttu-id="1b2c9-199">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="1b2c9-199">excludedFileExtension</span></span> <p> <span data-ttu-id="1b2c9-200">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="1b2c9-200">excludedFileName</span></span>|
|

##### <a name="path-to-excluded-content"></a><span data-ttu-id="1b2c9-201">Percorso del contenuto escluso</span><span class="sxs-lookup"><span data-stu-id="1b2c9-201">Path to excluded content</span></span>

<span data-ttu-id="1b2c9-202">Utilizzato per escludere il contenuto dall'analisi in base al percorso completo del file.</span><span class="sxs-lookup"><span data-stu-id="1b2c9-202">Used to exclude content from the scan by full file path.</span></span>

<br>

****

|<span data-ttu-id="1b2c9-203">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1b2c9-203">Description</span></span>|<span data-ttu-id="1b2c9-204">Valore</span><span class="sxs-lookup"><span data-stu-id="1b2c9-204">Value</span></span>|
|---|---|
|<span data-ttu-id="1b2c9-205">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-205">**Key**</span></span>|<span data-ttu-id="1b2c9-206">path</span><span class="sxs-lookup"><span data-stu-id="1b2c9-206">path</span></span>|
|<span data-ttu-id="1b2c9-207">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-207">**Data type**</span></span>|<span data-ttu-id="1b2c9-208">Stringa</span><span class="sxs-lookup"><span data-stu-id="1b2c9-208">String</span></span>|
|<span data-ttu-id="1b2c9-209">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-209">**Possible values**</span></span>|<span data-ttu-id="1b2c9-210">percorsi validi</span><span class="sxs-lookup"><span data-stu-id="1b2c9-210">valid paths</span></span>|
|<span data-ttu-id="1b2c9-211">**Comments**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-211">**Comments**</span></span>|<span data-ttu-id="1b2c9-212">Applicabile solo se *$type* *è excludedPath*</span><span class="sxs-lookup"><span data-stu-id="1b2c9-212">Applicable only if *$type* is *excludedPath*</span></span>|
|

##### <a name="path-type-file--directory"></a><span data-ttu-id="1b2c9-213">Tipo di percorso (file/directory)</span><span class="sxs-lookup"><span data-stu-id="1b2c9-213">Path type (file / directory)</span></span>

<span data-ttu-id="1b2c9-214">Indica se la proprietà *path* fa riferimento a un file o a una directory.</span><span class="sxs-lookup"><span data-stu-id="1b2c9-214">Indicates if the *path* property refers to a file or directory.</span></span>

<br>

****

|<span data-ttu-id="1b2c9-215">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1b2c9-215">Description</span></span>|<span data-ttu-id="1b2c9-216">Valore</span><span class="sxs-lookup"><span data-stu-id="1b2c9-216">Value</span></span>|
|---|---|
|<span data-ttu-id="1b2c9-217">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-217">**Key**</span></span>|<span data-ttu-id="1b2c9-218">isDirectory</span><span class="sxs-lookup"><span data-stu-id="1b2c9-218">isDirectory</span></span>|
|<span data-ttu-id="1b2c9-219">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-219">**Data type**</span></span>|<span data-ttu-id="1b2c9-220">Booleano</span><span class="sxs-lookup"><span data-stu-id="1b2c9-220">Boolean</span></span>|
|<span data-ttu-id="1b2c9-221">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-221">**Possible values**</span></span>|<span data-ttu-id="1b2c9-222">false (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="1b2c9-222">false (default)</span></span> <p> <span data-ttu-id="1b2c9-223">true</span><span class="sxs-lookup"><span data-stu-id="1b2c9-223">true</span></span>|
|<span data-ttu-id="1b2c9-224">**Comments**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-224">**Comments**</span></span>|<span data-ttu-id="1b2c9-225">Applicabile solo se *$type* *è excludedPath*</span><span class="sxs-lookup"><span data-stu-id="1b2c9-225">Applicable only if *$type* is *excludedPath*</span></span>|
|

##### <a name="file-extension-excluded-from-the-scan"></a><span data-ttu-id="1b2c9-226">Estensione di file esclusa dall'analisi</span><span class="sxs-lookup"><span data-stu-id="1b2c9-226">File extension excluded from the scan</span></span>

<span data-ttu-id="1b2c9-227">Usato per escludere il contenuto dall'analisi per estensione di file.</span><span class="sxs-lookup"><span data-stu-id="1b2c9-227">Used to exclude content from the scan by file extension.</span></span>

<br>

****

|<span data-ttu-id="1b2c9-228">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1b2c9-228">Description</span></span>|<span data-ttu-id="1b2c9-229">Valore</span><span class="sxs-lookup"><span data-stu-id="1b2c9-229">Value</span></span>|
|---|---|
|<span data-ttu-id="1b2c9-230">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-230">**Key**</span></span>|<span data-ttu-id="1b2c9-231">extension</span><span class="sxs-lookup"><span data-stu-id="1b2c9-231">extension</span></span>|
|<span data-ttu-id="1b2c9-232">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-232">**Data type**</span></span>|<span data-ttu-id="1b2c9-233">Stringa</span><span class="sxs-lookup"><span data-stu-id="1b2c9-233">String</span></span>|
|<span data-ttu-id="1b2c9-234">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-234">**Possible values**</span></span>|<span data-ttu-id="1b2c9-235">estensioni di file valide</span><span class="sxs-lookup"><span data-stu-id="1b2c9-235">valid file extensions</span></span>|
|<span data-ttu-id="1b2c9-236">**Comments**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-236">**Comments**</span></span>|<span data-ttu-id="1b2c9-237">Applicabile solo se *$type* *è excludedFileExtension*</span><span class="sxs-lookup"><span data-stu-id="1b2c9-237">Applicable only if *$type* is *excludedFileExtension*</span></span>|
|

##### <a name="process-excluded-from-the-scan"></a><span data-ttu-id="1b2c9-238">Processo escluso dall'analisi\*</span><span class="sxs-lookup"><span data-stu-id="1b2c9-238">Process excluded from the scan\*</span></span>

<span data-ttu-id="1b2c9-239">Specifica un processo per il quale tutte le attività di file vengono escluse dall'analisi.</span><span class="sxs-lookup"><span data-stu-id="1b2c9-239">Specifies a process for which all file activity is excluded from scanning.</span></span> <span data-ttu-id="1b2c9-240">Il processo può essere specificato in base al nome (ad esempio, `cat` ) o al percorso completo (ad esempio, `/bin/cat` ).</span><span class="sxs-lookup"><span data-stu-id="1b2c9-240">The process can be specified either by its name (for example, `cat`) or full path (for example, `/bin/cat`).</span></span>

<br>

****

|<span data-ttu-id="1b2c9-241">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1b2c9-241">Description</span></span>|<span data-ttu-id="1b2c9-242">Valore</span><span class="sxs-lookup"><span data-stu-id="1b2c9-242">Value</span></span>|
|---|---|
|<span data-ttu-id="1b2c9-243">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-243">**Key**</span></span>|<span data-ttu-id="1b2c9-244">name</span><span class="sxs-lookup"><span data-stu-id="1b2c9-244">name</span></span>|
|<span data-ttu-id="1b2c9-245">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-245">**Data type**</span></span>|<span data-ttu-id="1b2c9-246">Stringa</span><span class="sxs-lookup"><span data-stu-id="1b2c9-246">String</span></span>|
|<span data-ttu-id="1b2c9-247">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-247">**Possible values**</span></span>|<span data-ttu-id="1b2c9-248">qualsiasi stringa</span><span class="sxs-lookup"><span data-stu-id="1b2c9-248">any string</span></span>|
|<span data-ttu-id="1b2c9-249">**Comments**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-249">**Comments**</span></span>|<span data-ttu-id="1b2c9-250">Applicabile solo se *$type* *è excludedFileName*</span><span class="sxs-lookup"><span data-stu-id="1b2c9-250">Applicable only if *$type* is *excludedFileName*</span></span>|
|

#### <a name="allowed-threats"></a><span data-ttu-id="1b2c9-251">Minacce consentite</span><span class="sxs-lookup"><span data-stu-id="1b2c9-251">Allowed threats</span></span>

<span data-ttu-id="1b2c9-252">Elenco delle minacce (identificate dal nome) che non sono bloccate dal prodotto e che possono essere eseguite.</span><span class="sxs-lookup"><span data-stu-id="1b2c9-252">List of threats (identified by their name) that are not blocked by the product and are instead allowed to run.</span></span>

<br>

****

|<span data-ttu-id="1b2c9-253">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1b2c9-253">Description</span></span>|<span data-ttu-id="1b2c9-254">Valore</span><span class="sxs-lookup"><span data-stu-id="1b2c9-254">Value</span></span>|
|---|---|
|<span data-ttu-id="1b2c9-255">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-255">**Key**</span></span>|<span data-ttu-id="1b2c9-256">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="1b2c9-256">allowedThreats</span></span>|
|<span data-ttu-id="1b2c9-257">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-257">**Data type**</span></span>|<span data-ttu-id="1b2c9-258">Matrice di stringhe</span><span class="sxs-lookup"><span data-stu-id="1b2c9-258">Array of strings</span></span>|
|

#### <a name="disallowed-threat-actions"></a><span data-ttu-id="1b2c9-259">Azioni di minaccia non consentite</span><span class="sxs-lookup"><span data-stu-id="1b2c9-259">Disallowed threat actions</span></span>

<span data-ttu-id="1b2c9-260">Limita le azioni che l'utente locale di un dispositivo può intraprendere quando vengono rilevate minacce.</span><span class="sxs-lookup"><span data-stu-id="1b2c9-260">Restricts the actions that the local user of a device can take when threats are detected.</span></span> <span data-ttu-id="1b2c9-261">Le azioni incluse in questo elenco non vengono visualizzate nell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="1b2c9-261">The actions included in this list are not displayed in the user interface.</span></span>

<br>

****

|<span data-ttu-id="1b2c9-262">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1b2c9-262">Description</span></span>|<span data-ttu-id="1b2c9-263">Valore</span><span class="sxs-lookup"><span data-stu-id="1b2c9-263">Value</span></span>|
|---|---|
|<span data-ttu-id="1b2c9-264">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-264">**Key**</span></span>|<span data-ttu-id="1b2c9-265">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="1b2c9-265">disallowedThreatActions</span></span>|
|<span data-ttu-id="1b2c9-266">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-266">**Data type**</span></span>|<span data-ttu-id="1b2c9-267">Matrice di stringhe</span><span class="sxs-lookup"><span data-stu-id="1b2c9-267">Array of strings</span></span>|
|<span data-ttu-id="1b2c9-268">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-268">**Possible values**</span></span>|<span data-ttu-id="1b2c9-269">allow (impedisce agli utenti di consentire minacce)</span><span class="sxs-lookup"><span data-stu-id="1b2c9-269">allow (restricts users from allowing threats)</span></span> <p> <span data-ttu-id="1b2c9-270">restore (impedisce agli utenti di ripristinare le minacce dalla quarantena)</span><span class="sxs-lookup"><span data-stu-id="1b2c9-270">restore (restricts users from restoring threats from the quarantine)</span></span>|
|<span data-ttu-id="1b2c9-271">**Comments**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-271">**Comments**</span></span>|<span data-ttu-id="1b2c9-272">Disponibile in Defender per Endpoint versione 100.83.73 o successiva.</span><span class="sxs-lookup"><span data-stu-id="1b2c9-272">Available in Defender for Endpoint version 100.83.73 or higher.</span></span>|
|

#### <a name="threat-type-settings"></a><span data-ttu-id="1b2c9-273">Impostazioni del tipo di minaccia</span><span class="sxs-lookup"><span data-stu-id="1b2c9-273">Threat type settings</span></span>

<span data-ttu-id="1b2c9-274">La *preferenza threatTypeSettings* nel motore antivirus viene utilizzata per controllare la modalità di gestione di determinati tipi di minacce da parte del prodotto.</span><span class="sxs-lookup"><span data-stu-id="1b2c9-274">The *threatTypeSettings* preference in the antivirus engine is used to control how certain threat types are handled by the product.</span></span>

<br>

****

|<span data-ttu-id="1b2c9-275">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1b2c9-275">Description</span></span>|<span data-ttu-id="1b2c9-276">Valore</span><span class="sxs-lookup"><span data-stu-id="1b2c9-276">Value</span></span>|
|---|---|
|<span data-ttu-id="1b2c9-277">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-277">**Key**</span></span>|<span data-ttu-id="1b2c9-278">threatTypeSettings</span><span class="sxs-lookup"><span data-stu-id="1b2c9-278">threatTypeSettings</span></span>|
|<span data-ttu-id="1b2c9-279">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-279">**Data type**</span></span>|<span data-ttu-id="1b2c9-280">Dizionario (preferenza annidata)</span><span class="sxs-lookup"><span data-stu-id="1b2c9-280">Dictionary (nested preference)</span></span>|
|<span data-ttu-id="1b2c9-281">**Comments**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-281">**Comments**</span></span>|<span data-ttu-id="1b2c9-282">Per una descrizione del contenuto del dizionario, vedi le sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="1b2c9-282">See the following sections for a description of the dictionary contents.</span></span>|
|

##### <a name="threat-type"></a><span data-ttu-id="1b2c9-283">Tipo di minaccia</span><span class="sxs-lookup"><span data-stu-id="1b2c9-283">Threat type</span></span>

<span data-ttu-id="1b2c9-284">Tipo di minaccia per cui è configurato il comportamento.</span><span class="sxs-lookup"><span data-stu-id="1b2c9-284">Type of threat for which the behavior is configured.</span></span>

<br>

****

|<span data-ttu-id="1b2c9-285">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1b2c9-285">Description</span></span>|<span data-ttu-id="1b2c9-286">Valore</span><span class="sxs-lookup"><span data-stu-id="1b2c9-286">Value</span></span>|
|---|---|
|<span data-ttu-id="1b2c9-287">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-287">**Key**</span></span>|<span data-ttu-id="1b2c9-288">chiave</span><span class="sxs-lookup"><span data-stu-id="1b2c9-288">key</span></span>|
|<span data-ttu-id="1b2c9-289">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-289">**Data type**</span></span>|<span data-ttu-id="1b2c9-290">Stringa</span><span class="sxs-lookup"><span data-stu-id="1b2c9-290">String</span></span>|
|<span data-ttu-id="1b2c9-291">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-291">**Possible values**</span></span>|<span data-ttu-id="1b2c9-292">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="1b2c9-292">potentially_unwanted_application</span></span> <p> <span data-ttu-id="1b2c9-293">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="1b2c9-293">archive_bomb</span></span>|
|

##### <a name="action-to-take"></a><span data-ttu-id="1b2c9-294">Procedura da seguire</span><span class="sxs-lookup"><span data-stu-id="1b2c9-294">Action to take</span></span>

<span data-ttu-id="1b2c9-295">Azione da intraprendere quando si verifica una minaccia del tipo specificato nella sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="1b2c9-295">Action to take when coming across a threat of the type specified in the preceding section.</span></span> <span data-ttu-id="1b2c9-296">Può essere:</span><span class="sxs-lookup"><span data-stu-id="1b2c9-296">Can be:</span></span>

- <span data-ttu-id="1b2c9-297">**Controllo:** il dispositivo non è protetto da questo tipo di minaccia, ma viene registrata una voce relativa alla minaccia.</span><span class="sxs-lookup"><span data-stu-id="1b2c9-297">**Audit**: The device is not protected against this type of threat, but an entry about the threat is logged.</span></span>
- <span data-ttu-id="1b2c9-298">**Blocca**: il dispositivo è protetto da questo tipo di minaccia e si viene informati nella console di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="1b2c9-298">**Block**: The device is protected against this type of threat and you are notified in the security console.</span></span>
- <span data-ttu-id="1b2c9-299">**Disattivato:** il dispositivo non è protetto da questo tipo di minaccia e non viene registrato nulla.</span><span class="sxs-lookup"><span data-stu-id="1b2c9-299">**Off**: The device is not protected against this type of threat and nothing is logged.</span></span>

<br>

****

|<span data-ttu-id="1b2c9-300">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1b2c9-300">Description</span></span>|<span data-ttu-id="1b2c9-301">Valore</span><span class="sxs-lookup"><span data-stu-id="1b2c9-301">Value</span></span>|
|---|---|
|<span data-ttu-id="1b2c9-302">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-302">**Key**</span></span>|<span data-ttu-id="1b2c9-303">valore</span><span class="sxs-lookup"><span data-stu-id="1b2c9-303">value</span></span>|
|<span data-ttu-id="1b2c9-304">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-304">**Data type**</span></span>|<span data-ttu-id="1b2c9-305">Stringa</span><span class="sxs-lookup"><span data-stu-id="1b2c9-305">String</span></span>|
|<span data-ttu-id="1b2c9-306">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-306">**Possible values**</span></span>|<span data-ttu-id="1b2c9-307">audit (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="1b2c9-307">audit (default)</span></span> <p> <span data-ttu-id="1b2c9-308">blocco</span><span class="sxs-lookup"><span data-stu-id="1b2c9-308">block</span></span> <p> <span data-ttu-id="1b2c9-309">off</span><span class="sxs-lookup"><span data-stu-id="1b2c9-309">off</span></span>|
|

#### <a name="threat-type-settings-merge-policy"></a><span data-ttu-id="1b2c9-310">Criteri di unione delle impostazioni del tipo di minaccia</span><span class="sxs-lookup"><span data-stu-id="1b2c9-310">Threat type settings merge policy</span></span>

<span data-ttu-id="1b2c9-311">Specifica il criterio di unione per le impostazioni del tipo di minaccia.</span><span class="sxs-lookup"><span data-stu-id="1b2c9-311">Specifies the merge policy for threat type settings.</span></span> <span data-ttu-id="1b2c9-312">Può essere una combinazione di impostazioni definite dall'amministratore e definite dall'utente ( ) o solo impostazioni definite `merge` dall'amministratore ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="1b2c9-312">This can be a combination of administrator-defined and user-defined settings (`merge`) or only administrator-defined settings (`admin_only`).</span></span> <span data-ttu-id="1b2c9-313">Questa impostazione può essere usata per impedire agli utenti locali di definire le proprie impostazioni per diversi tipi di minacce.</span><span class="sxs-lookup"><span data-stu-id="1b2c9-313">This setting can be used to restrict local users from defining their own settings for different threat types.</span></span>

<br>

****

|<span data-ttu-id="1b2c9-314">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1b2c9-314">Description</span></span>|<span data-ttu-id="1b2c9-315">Valore</span><span class="sxs-lookup"><span data-stu-id="1b2c9-315">Value</span></span>|
|---|---|
|<span data-ttu-id="1b2c9-316">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-316">**Key**</span></span>|<span data-ttu-id="1b2c9-317">threatTypeSettingsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="1b2c9-317">threatTypeSettingsMergePolicy</span></span>|
|<span data-ttu-id="1b2c9-318">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-318">**Data type**</span></span>|<span data-ttu-id="1b2c9-319">Stringa</span><span class="sxs-lookup"><span data-stu-id="1b2c9-319">String</span></span>|
|<span data-ttu-id="1b2c9-320">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-320">**Possible values**</span></span>|<span data-ttu-id="1b2c9-321">merge (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="1b2c9-321">merge (default)</span></span> <p> <span data-ttu-id="1b2c9-322">admin_only</span><span class="sxs-lookup"><span data-stu-id="1b2c9-322">admin_only</span></span>|
|<span data-ttu-id="1b2c9-323">**Comments**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-323">**Comments**</span></span>|<span data-ttu-id="1b2c9-324">Disponibile in Defender per Endpoint versione 100.83.73 o successiva.</span><span class="sxs-lookup"><span data-stu-id="1b2c9-324">Available in Defender for Endpoint version 100.83.73 or higher.</span></span>|
|

#### <a name="antivirus-scan-history-retention-in-days"></a><span data-ttu-id="1b2c9-325">Conservazione cronologia analisi antivirus (in giorni)</span><span class="sxs-lookup"><span data-stu-id="1b2c9-325">Antivirus scan history retention (in days)</span></span>

<span data-ttu-id="1b2c9-326">Specifica il numero di giorni in cui i risultati vengono conservati nella cronologia dell'analisi nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1b2c9-326">Specify the number of days that results are retained in the scan history on the device.</span></span> <span data-ttu-id="1b2c9-327">I risultati dell'analisi precedente vengono rimossi dalla cronologia.</span><span class="sxs-lookup"><span data-stu-id="1b2c9-327">Old scan results are removed from the history.</span></span> <span data-ttu-id="1b2c9-328">Vecchi file in quarantena che vengono rimossi anche dal disco.</span><span class="sxs-lookup"><span data-stu-id="1b2c9-328">Old quarantined files that are also removed from the disk.</span></span>

<br>

****

|<span data-ttu-id="1b2c9-329">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1b2c9-329">Description</span></span>|<span data-ttu-id="1b2c9-330">Valore</span><span class="sxs-lookup"><span data-stu-id="1b2c9-330">Value</span></span>|
|---|---|
|<span data-ttu-id="1b2c9-331">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-331">**Key**</span></span>|<span data-ttu-id="1b2c9-332">scanResultsRetentionDays</span><span class="sxs-lookup"><span data-stu-id="1b2c9-332">scanResultsRetentionDays</span></span>|
|<span data-ttu-id="1b2c9-333">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-333">**Data type**</span></span>|<span data-ttu-id="1b2c9-334">Stringa</span><span class="sxs-lookup"><span data-stu-id="1b2c9-334">String</span></span>|
|<span data-ttu-id="1b2c9-335">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-335">**Possible values**</span></span>|<span data-ttu-id="1b2c9-336">90 (impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="1b2c9-336">90 (default).</span></span> <span data-ttu-id="1b2c9-337">I valori consentiti sono da 1 giorno a 180 giorni.</span><span class="sxs-lookup"><span data-stu-id="1b2c9-337">Allowed values are from 1 day to 180 days.</span></span>|
|<span data-ttu-id="1b2c9-338">**Comments**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-338">**Comments**</span></span>|<span data-ttu-id="1b2c9-339">Disponibile in Defender per Endpoint versione 101.04.76 o successiva.</span><span class="sxs-lookup"><span data-stu-id="1b2c9-339">Available in Defender for Endpoint version 101.04.76 or higher.</span></span>|
|

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a><span data-ttu-id="1b2c9-340">Numero massimo di elementi nella cronologia dell'analisi antivirus</span><span class="sxs-lookup"><span data-stu-id="1b2c9-340">Maximum number of items in the antivirus scan history</span></span>

<span data-ttu-id="1b2c9-341">Specificare il numero massimo di voci da mantenere nella cronologia di analisi.</span><span class="sxs-lookup"><span data-stu-id="1b2c9-341">Specify the maximum number of entries to keep in the scan history.</span></span> <span data-ttu-id="1b2c9-342">Le voci includono tutte le analisi su richiesta eseguite in passato e tutti i rilevamenti antivirus.</span><span class="sxs-lookup"><span data-stu-id="1b2c9-342">Entries include all on-demand scans performed in the past and all antivirus detections.</span></span>

<br>

****

|<span data-ttu-id="1b2c9-343">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1b2c9-343">Description</span></span>|<span data-ttu-id="1b2c9-344">Valore</span><span class="sxs-lookup"><span data-stu-id="1b2c9-344">Value</span></span>|
|---|---|
|<span data-ttu-id="1b2c9-345">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-345">**Key**</span></span>|<span data-ttu-id="1b2c9-346">scanHistoryMaximumItems</span><span class="sxs-lookup"><span data-stu-id="1b2c9-346">scanHistoryMaximumItems</span></span>|
|<span data-ttu-id="1b2c9-347">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-347">**Data type**</span></span>|<span data-ttu-id="1b2c9-348">Stringa</span><span class="sxs-lookup"><span data-stu-id="1b2c9-348">String</span></span>|
|<span data-ttu-id="1b2c9-349">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-349">**Possible values**</span></span>|<span data-ttu-id="1b2c9-350">10000 (impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="1b2c9-350">10000 (default).</span></span> <span data-ttu-id="1b2c9-351">I valori consentiti sono da 5.000 elementi a 15.000 elementi.</span><span class="sxs-lookup"><span data-stu-id="1b2c9-351">Allowed values are from 5000 items to 15000 items.</span></span>|
|<span data-ttu-id="1b2c9-352">**Comments**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-352">**Comments**</span></span>|<span data-ttu-id="1b2c9-353">Disponibile in Defender per Endpoint versione 101.04.76 o successiva.</span><span class="sxs-lookup"><span data-stu-id="1b2c9-353">Available in Defender for Endpoint version 101.04.76 or higher.</span></span>|
|

### <a name="cloud-delivered-protection-preferences"></a><span data-ttu-id="1b2c9-354">Preferenze di protezione per il cloud</span><span class="sxs-lookup"><span data-stu-id="1b2c9-354">Cloud-delivered protection preferences</span></span>

<span data-ttu-id="1b2c9-355">La *voce cloudService* nel profilo di configurazione viene utilizzata per configurare la funzionalità di protezione basata sul cloud del prodotto.</span><span class="sxs-lookup"><span data-stu-id="1b2c9-355">The *cloudService* entry in the configuration profile is used to configure the cloud-driven protection feature of the product.</span></span>

<br>

****

|<span data-ttu-id="1b2c9-356">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1b2c9-356">Description</span></span>|<span data-ttu-id="1b2c9-357">Valore</span><span class="sxs-lookup"><span data-stu-id="1b2c9-357">Value</span></span>|
|---|---|
|<span data-ttu-id="1b2c9-358">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-358">**Key**</span></span>|<span data-ttu-id="1b2c9-359">cloudService</span><span class="sxs-lookup"><span data-stu-id="1b2c9-359">cloudService</span></span>|
|<span data-ttu-id="1b2c9-360">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-360">**Data type**</span></span>|<span data-ttu-id="1b2c9-361">Dizionario (preferenza annidata)</span><span class="sxs-lookup"><span data-stu-id="1b2c9-361">Dictionary (nested preference)</span></span>|
|<span data-ttu-id="1b2c9-362">**Comments**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-362">**Comments**</span></span>|<span data-ttu-id="1b2c9-363">Per una descrizione del contenuto del dizionario, vedi le sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="1b2c9-363">See the following sections for a description of the dictionary contents.</span></span>|
|

#### <a name="enable--disable-cloud-delivered-protection"></a><span data-ttu-id="1b2c9-364">Abilitare/disabilitare la protezione recapitata nel cloud</span><span class="sxs-lookup"><span data-stu-id="1b2c9-364">Enable / disable cloud delivered protection</span></span>

<span data-ttu-id="1b2c9-365">Determina se la protezione consegnata dal cloud è abilitata o meno nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1b2c9-365">Determines whether cloud-delivered protection is enabled on the device or not.</span></span> <span data-ttu-id="1b2c9-366">Per migliorare la sicurezza dei servizi, è consigliabile mantenere attivata questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="1b2c9-366">To improve the security of your services, we recommend keeping this feature turned on.</span></span>

<br>

****

|<span data-ttu-id="1b2c9-367">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1b2c9-367">Description</span></span>|<span data-ttu-id="1b2c9-368">Valore</span><span class="sxs-lookup"><span data-stu-id="1b2c9-368">Value</span></span>|
|---|---|
|<span data-ttu-id="1b2c9-369">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-369">**Key**</span></span>|<span data-ttu-id="1b2c9-370">abilitati</span><span class="sxs-lookup"><span data-stu-id="1b2c9-370">enabled</span></span>|
|<span data-ttu-id="1b2c9-371">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-371">**Data type**</span></span>|<span data-ttu-id="1b2c9-372">Booleano</span><span class="sxs-lookup"><span data-stu-id="1b2c9-372">Boolean</span></span>|
|<span data-ttu-id="1b2c9-373">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-373">**Possible values**</span></span>|<span data-ttu-id="1b2c9-374">true (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="1b2c9-374">true (default)</span></span> <p> <span data-ttu-id="1b2c9-375">false</span><span class="sxs-lookup"><span data-stu-id="1b2c9-375">false</span></span>|
|

#### <a name="diagnostic-collection-level"></a><span data-ttu-id="1b2c9-376">Livello raccolta diagnostica</span><span class="sxs-lookup"><span data-stu-id="1b2c9-376">Diagnostic collection level</span></span>

<span data-ttu-id="1b2c9-377">I dati di diagnostica vengono usati per mantenere Defender per Endpoint sicuro e aggiornato, rilevare, diagnosticare e risolvere i problemi e apportare miglioramenti al prodotto.</span><span class="sxs-lookup"><span data-stu-id="1b2c9-377">Diagnostic data is used to keep Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span> <span data-ttu-id="1b2c9-378">Questa impostazione determina il livello di diagnostica inviato dal prodotto a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1b2c9-378">This setting determines the level of diagnostics sent by the product to Microsoft.</span></span>

<br>

****

|<span data-ttu-id="1b2c9-379">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1b2c9-379">Description</span></span>|<span data-ttu-id="1b2c9-380">Valore</span><span class="sxs-lookup"><span data-stu-id="1b2c9-380">Value</span></span>|
|---|---|
|<span data-ttu-id="1b2c9-381">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-381">**Key**</span></span>|<span data-ttu-id="1b2c9-382">diagnosticLevel</span><span class="sxs-lookup"><span data-stu-id="1b2c9-382">diagnosticLevel</span></span>|
|<span data-ttu-id="1b2c9-383">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-383">**Data type**</span></span>|<span data-ttu-id="1b2c9-384">Stringa</span><span class="sxs-lookup"><span data-stu-id="1b2c9-384">String</span></span>|
|<span data-ttu-id="1b2c9-385">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-385">**Possible values**</span></span>|<span data-ttu-id="1b2c9-386">facoltativo (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="1b2c9-386">optional (default)</span></span> <p> <span data-ttu-id="1b2c9-387">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="1b2c9-387">required</span></span>|
|

#### <a name="enable--disable-automatic-sample-submissions"></a><span data-ttu-id="1b2c9-388">Abilitare/disabilitare gli invii di esempio automatici</span><span class="sxs-lookup"><span data-stu-id="1b2c9-388">Enable / disable automatic sample submissions</span></span>

<span data-ttu-id="1b2c9-389">Determina se i campioni sospetti (che potrebbero contenere minacce) vengono inviati a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1b2c9-389">Determines whether suspicious samples (that are likely to contain threats) are sent to Microsoft.</span></span> <span data-ttu-id="1b2c9-390">Esistono tre livelli per controllare l'invio di campioni:</span><span class="sxs-lookup"><span data-stu-id="1b2c9-390">There are three levels for controlling sample submission:</span></span>

- <span data-ttu-id="1b2c9-391">**Nessuno:** nessun campione sospetto viene inviato a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1b2c9-391">**None**: no suspicious samples are submitted to Microsoft.</span></span>
- <span data-ttu-id="1b2c9-392">**Cassaforte**: solo i campioni sospetti che non contengono informazioni personali vengono inviati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="1b2c9-392">**Safe**: only suspicious samples that do not contain personally identifiable information (PII) are submitted automatically.</span></span> <span data-ttu-id="1b2c9-393">Questo è il valore predefinito per questa impostazione.</span><span class="sxs-lookup"><span data-stu-id="1b2c9-393">This is the default value for this setting.</span></span>
- <span data-ttu-id="1b2c9-394">**All**: tutti i campioni sospetti vengono inviati a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1b2c9-394">**All**: all suspicious samples are submitted to Microsoft.</span></span>

<br>

****

|<span data-ttu-id="1b2c9-395">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1b2c9-395">Description</span></span>|<span data-ttu-id="1b2c9-396">Valore</span><span class="sxs-lookup"><span data-stu-id="1b2c9-396">Value</span></span>|
|---|---|
|<span data-ttu-id="1b2c9-397">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-397">**Key**</span></span>|<span data-ttu-id="1b2c9-398">automaticSampleSubmissionConsent</span><span class="sxs-lookup"><span data-stu-id="1b2c9-398">automaticSampleSubmissionConsent</span></span>|
|<span data-ttu-id="1b2c9-399">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-399">**Data type**</span></span>|<span data-ttu-id="1b2c9-400">Stringa</span><span class="sxs-lookup"><span data-stu-id="1b2c9-400">String</span></span>|
|<span data-ttu-id="1b2c9-401">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-401">**Possible values**</span></span>|<span data-ttu-id="1b2c9-402">nessuno</span><span class="sxs-lookup"><span data-stu-id="1b2c9-402">none</span></span> <p> <span data-ttu-id="1b2c9-403">safe (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="1b2c9-403">safe (default)</span></span> <p> <span data-ttu-id="1b2c9-404">all</span><span class="sxs-lookup"><span data-stu-id="1b2c9-404">all</span></span>|
|

#### <a name="enable--disable-automatic-security-intelligence-updates"></a><span data-ttu-id="1b2c9-405">Abilitare/disabilitare gli aggiornamenti automatici delle funzionalità di intelligence per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="1b2c9-405">Enable / disable automatic security intelligence updates</span></span>

<span data-ttu-id="1b2c9-406">Determina se gli aggiornamenti delle funzionalità di intelligence per la sicurezza vengono installati automaticamente:</span><span class="sxs-lookup"><span data-stu-id="1b2c9-406">Determines whether security intelligence updates are installed automatically:</span></span>

<br>

****

|<span data-ttu-id="1b2c9-407">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1b2c9-407">Description</span></span>|<span data-ttu-id="1b2c9-408">Valore</span><span class="sxs-lookup"><span data-stu-id="1b2c9-408">Value</span></span>|
|---|---|
|<span data-ttu-id="1b2c9-409">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-409">**Key**</span></span>|<span data-ttu-id="1b2c9-410">automaticDefinitionUpdateEnabled</span><span class="sxs-lookup"><span data-stu-id="1b2c9-410">automaticDefinitionUpdateEnabled</span></span>|
|<span data-ttu-id="1b2c9-411">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-411">**Data type**</span></span>|<span data-ttu-id="1b2c9-412">Booleano</span><span class="sxs-lookup"><span data-stu-id="1b2c9-412">Boolean</span></span>|
|<span data-ttu-id="1b2c9-413">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="1b2c9-413">**Possible values**</span></span>|<span data-ttu-id="1b2c9-414">true (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="1b2c9-414">true (default)</span></span> <p> <span data-ttu-id="1b2c9-415">false</span><span class="sxs-lookup"><span data-stu-id="1b2c9-415">false</span></span>|
|

## <a name="recommended-configuration-profile"></a><span data-ttu-id="1b2c9-416">Profilo di configurazione consigliato</span><span class="sxs-lookup"><span data-stu-id="1b2c9-416">Recommended configuration profile</span></span>

<span data-ttu-id="1b2c9-417">Per iniziare, ti consigliamo di usare il profilo di configurazione seguente per la tua azienda per sfruttare tutte le funzionalità di protezione fornite da Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="1b2c9-417">To get started, we recommend the following configuration profile for your enterprise to take advantage of all protection features that Defender for Endpoint provides.</span></span>

<span data-ttu-id="1b2c9-418">Il profilo di configurazione seguente:</span><span class="sxs-lookup"><span data-stu-id="1b2c9-418">The following configuration profile will:</span></span>

- <span data-ttu-id="1b2c9-419">Abilitare la protezione in tempo reale (RTP)</span><span class="sxs-lookup"><span data-stu-id="1b2c9-419">Enable real-time protection (RTP)</span></span>
- <span data-ttu-id="1b2c9-420">Specificare la modalità di gestione dei seguenti tipi di minacce:</span><span class="sxs-lookup"><span data-stu-id="1b2c9-420">Specify how the following threat types are handled:</span></span>
  - <span data-ttu-id="1b2c9-421">**Le applicazioni potenzialmente indesiderate sono** bloccate</span><span class="sxs-lookup"><span data-stu-id="1b2c9-421">**Potentially unwanted applications (PUA)** are blocked</span></span>
  - <span data-ttu-id="1b2c9-422">**Le bombe di** archiviazione (file con una velocità di compressione elevata) vengono verificate nei log del prodotto</span><span class="sxs-lookup"><span data-stu-id="1b2c9-422">**Archive bombs** (file with a high compression rate) are audited to the product logs</span></span>
- <span data-ttu-id="1b2c9-423">Abilitare gli aggiornamenti automatici delle funzionalità di intelligence per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="1b2c9-423">Enable automatic security intelligence updates</span></span>
- <span data-ttu-id="1b2c9-424">Abilitare la protezione fornita dal cloud</span><span class="sxs-lookup"><span data-stu-id="1b2c9-424">Enable cloud-delivered protection</span></span>
- <span data-ttu-id="1b2c9-425">Abilitare l'invio automatico di esempi a `safe` livello</span><span class="sxs-lookup"><span data-stu-id="1b2c9-425">Enable automatic sample submission at `safe` level</span></span>

### <a name="sample-profile"></a><span data-ttu-id="1b2c9-426">Profilo di esempio</span><span class="sxs-lookup"><span data-stu-id="1b2c9-426">Sample profile</span></span>

```JSON
{
   "antivirusEngine":{
      "enableRealTimeProtection":true,
      "threatTypeSettings":[
         {
            "key":"potentially_unwanted_application",
            "value":"block"
         },
         {
            "key":"archive_bomb",
            "value":"audit"
         }
      ]
   },
   "cloudService":{
      "automaticDefinitionUpdateEnabled":true,
      "automaticSampleSubmissionConsent":"safe",
      "enabled":true,
      "proxy":"http://proxy.server:port/"
   }
}
```

## <a name="full-configuration-profile-example"></a><span data-ttu-id="1b2c9-427">Esempio di profilo di configurazione completo</span><span class="sxs-lookup"><span data-stu-id="1b2c9-427">Full configuration profile example</span></span>

<span data-ttu-id="1b2c9-428">Il profilo di configurazione seguente contiene voci per tutte le impostazioni descritte in questo documento e può essere utilizzato per scenari più avanzati in cui si desidera un maggiore controllo sul prodotto.</span><span class="sxs-lookup"><span data-stu-id="1b2c9-428">The following configuration profile contains entries for all settings described in this document and can be used for more advanced scenarios where you want more control over the product.</span></span>

### <a name="full-profile"></a><span data-ttu-id="1b2c9-429">Profilo completo</span><span class="sxs-lookup"><span data-stu-id="1b2c9-429">Full profile</span></span>

```JSON
{
   "antivirusEngine":{
      "enableRealTimeProtection":true,
      "passiveMode":false,
      "exclusionsMergePolicy":"merge",
      "exclusions":[
         {
            "$type":"excludedPath",
            "isDirectory":false,
            "path":"/var/log/system.log"
         },
         {
            "$type":"excludedPath",
            "isDirectory":true,
            "path":"/run"
         },
         {
            "$type":"excludedPath",
            "isDirectory":true,
            "path":"/home/*/git"
         },
         {
            "$type":"excludedFileExtension",
            "extension":".pdf"
         },
         {
            "$type":"excludedFileName",
            "name":"cat"
         }
      ],
      "allowedThreats":[
         "EICAR-Test-File (not a virus)"
      ],
      "disallowedThreatActions":[
         "allow",
         "restore"
      ],
      "threatTypeSettingsMergePolicy":"merge",
      "threatTypeSettings":[
         {
            "key":"potentially_unwanted_application",
            "value":"block"
         },
         {
            "key":"archive_bomb",
            "value":"audit"
         }
      ]
   },
   "cloudService":{
      "enabled":true,
      "diagnosticLevel":"optional",
      "automaticSampleSubmissionConsent":"safe",
      "automaticDefinitionUpdateEnabled":true,
      "proxy": "http://proxy.server:port/"
   }
}
```

## <a name="configuration-profile-validation"></a><span data-ttu-id="1b2c9-430">Convalida del profilo di configurazione</span><span class="sxs-lookup"><span data-stu-id="1b2c9-430">Configuration profile validation</span></span>

<span data-ttu-id="1b2c9-431">Il profilo di configurazione deve essere un file in formato JSON valido.</span><span class="sxs-lookup"><span data-stu-id="1b2c9-431">The configuration profile must be a valid JSON-formatted file.</span></span> <span data-ttu-id="1b2c9-432">Per verificarlo, è possibile utilizzare diversi strumenti.</span><span class="sxs-lookup"><span data-stu-id="1b2c9-432">There are a number of tools that can be used to verify this.</span></span> <span data-ttu-id="1b2c9-433">Ad esempio, se hai `python` installato nel dispositivo:</span><span class="sxs-lookup"><span data-stu-id="1b2c9-433">For example, if you have `python` installed on your device:</span></span>

```bash
python -m json.tool mdatp_managed.json
```

<span data-ttu-id="1b2c9-434">Se json è ben formato, il comando precedente lo restituisce al terminale e restituisce un codice di uscita di `0` .</span><span class="sxs-lookup"><span data-stu-id="1b2c9-434">If the JSON is well-formed, the above command outputs it back to the Terminal and returns an exit code of `0`.</span></span> <span data-ttu-id="1b2c9-435">In caso contrario, viene visualizzato un errore che descrive il problema e il comando restituisce un codice di uscita di `1` .</span><span class="sxs-lookup"><span data-stu-id="1b2c9-435">Otherwise, an error that describes the issue is displayed and the command returns an exit code of `1`.</span></span>

## <a name="verifying-that-the-mdatp_managedjson-file-is-working-as-expected"></a><span data-ttu-id="1b2c9-436">Verifica del funzionamento mdatp_managed.jsfile nel modo previsto</span><span class="sxs-lookup"><span data-stu-id="1b2c9-436">Verifying that the mdatp_managed.json file is working as expected</span></span>

<span data-ttu-id="1b2c9-437">Per verificare che /etc/opt/microsoft/mdatp/managed/mdatp_managed.jsfunzioni correttamente, dovrebbe essere visualizzato "[gestito]" accanto a queste impostazioni:</span><span class="sxs-lookup"><span data-stu-id="1b2c9-437">To verify that your /etc/opt/microsoft/mdatp/managed/mdatp_managed.json is working properly, you should see "[managed]" next to these settings:</span></span>

- <span data-ttu-id="1b2c9-438">cloud_enabled</span><span class="sxs-lookup"><span data-stu-id="1b2c9-438">cloud_enabled</span></span>
- <span data-ttu-id="1b2c9-439">cloud_automatic_sample_submission_consent</span><span class="sxs-lookup"><span data-stu-id="1b2c9-439">cloud_automatic_sample_submission_consent</span></span>
- <span data-ttu-id="1b2c9-440">passive_mode_enabled</span><span class="sxs-lookup"><span data-stu-id="1b2c9-440">passive_mode_enabled</span></span>
- <span data-ttu-id="1b2c9-441">real_time_protection_enabled</span><span class="sxs-lookup"><span data-stu-id="1b2c9-441">real_time_protection_enabled</span></span>
- <span data-ttu-id="1b2c9-442">automatic_definition_update_enabled</span><span class="sxs-lookup"><span data-stu-id="1b2c9-442">automatic_definition_update_enabled</span></span>

> [!NOTE]
> <span data-ttu-id="1b2c9-443">Per lmdatp_managed.jsè attivo, non è necessario riavviare il wdavdaemon.</span><span class="sxs-lookup"><span data-stu-id="1b2c9-443">For the mdatp_managed.json to take effect, no restart of the wdavdaemon is required.</span></span>

## <a name="configuration-profile-deployment"></a><span data-ttu-id="1b2c9-444">Distribuzione dei profili di configurazione</span><span class="sxs-lookup"><span data-stu-id="1b2c9-444">Configuration profile deployment</span></span>

<span data-ttu-id="1b2c9-445">Dopo aver creato il profilo di configurazione per l'organizzazione, è possibile distribuirlo tramite lo strumento di gestione utilizzato dall'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1b2c9-445">Once you've built the configuration profile for your enterprise, you can deploy it through the management tool that your enterprise is using.</span></span> <span data-ttu-id="1b2c9-446">Defender per Endpoint su Linux legge la configurazione gestita dal file */etc/opt/microsoft/mdatp/managed/mdatp_managed.json.*</span><span class="sxs-lookup"><span data-stu-id="1b2c9-446">Defender for Endpoint on Linux reads the managed configuration from the */etc/opt/microsoft/mdatp/managed/mdatp_managed.json* file.</span></span>
