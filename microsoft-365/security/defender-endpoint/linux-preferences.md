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
ms.openlocfilehash: 29505a6e975fdfa2283efe3391c615e40e678164
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2021
ms.locfileid: "52346379"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="c6caf-104">Impostare le preferenze per Microsoft Defender per Endpoint su Linux</span><span class="sxs-lookup"><span data-stu-id="c6caf-104">Set preferences for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="c6caf-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="c6caf-105">**Applies to:**</span></span>
- [<span data-ttu-id="c6caf-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="c6caf-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c6caf-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c6caf-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="c6caf-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="c6caf-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c6caf-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="c6caf-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

>[!IMPORTANT]
><span data-ttu-id="c6caf-110">Questo argomento contiene istruzioni su come impostare le preferenze per Defender per Endpoint in Linux in ambienti aziendali.</span><span class="sxs-lookup"><span data-stu-id="c6caf-110">This topic contains instructions for how to set preferences for Defender for Endpoint on Linux in enterprise environments.</span></span> <span data-ttu-id="c6caf-111">Se si desidera configurare il prodotto in un dispositivo dalla riga di comando, vedere [Resources](linux-resources.md#configure-from-the-command-line).</span><span class="sxs-lookup"><span data-stu-id="c6caf-111">If you are interested in configuring the product on a device from the command-line, see [Resources](linux-resources.md#configure-from-the-command-line).</span></span>

<span data-ttu-id="c6caf-112">In ambienti aziendali, Defender per Endpoint su Linux può essere gestito tramite un profilo di configurazione.</span><span class="sxs-lookup"><span data-stu-id="c6caf-112">In enterprise environments, Defender for Endpoint on Linux can be managed through a configuration profile.</span></span> <span data-ttu-id="c6caf-113">Questo profilo viene distribuito dallo strumento di gestione scelto.</span><span class="sxs-lookup"><span data-stu-id="c6caf-113">This profile is deployed from the management tool of your choice.</span></span> <span data-ttu-id="c6caf-114">Le preferenze gestite dall'organizzazione hanno la precedenza su quelle impostate localmente nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c6caf-114">Preferences managed by the enterprise take precedence over the ones set locally on the device.</span></span> <span data-ttu-id="c6caf-115">In altre parole, gli utenti dell'organizzazione non sono in grado di modificare le preferenze impostate tramite questo profilo di configurazione.</span><span class="sxs-lookup"><span data-stu-id="c6caf-115">In other words, users in your enterprise are not able to change preferences that are set through this configuration profile.</span></span>

<span data-ttu-id="c6caf-116">Questo articolo descrive la struttura di questo profilo (incluso un profilo consigliato che puoi usare per iniziare) e le istruzioni su come distribuire il profilo.</span><span class="sxs-lookup"><span data-stu-id="c6caf-116">This article describes the structure of this profile (including a recommended profile that you can use to get started) and instructions on how to deploy the profile.</span></span>

## <a name="configuration-profile-structure"></a><span data-ttu-id="c6caf-117">Struttura del profilo di configurazione</span><span class="sxs-lookup"><span data-stu-id="c6caf-117">Configuration profile structure</span></span>

<span data-ttu-id="c6caf-118">Il profilo di configurazione è un file JSON costituito da voci identificate da una chiave (che indica il nome della preferenza), seguita da un valore, che dipende dalla natura della preferenza.</span><span class="sxs-lookup"><span data-stu-id="c6caf-118">The configuration profile is a .json file that consists of entries identified by a key (which denotes the name of the preference), followed by a value, which depends on the nature of the preference.</span></span> <span data-ttu-id="c6caf-119">I valori possono essere semplici, ad esempio un valore numerico o complessi, ad esempio un elenco nidificato di preferenze.</span><span class="sxs-lookup"><span data-stu-id="c6caf-119">Values can be simple, such as a numerical value, or complex, such as a nested list of preferences.</span></span>

<span data-ttu-id="c6caf-120">In genere, si utilizza uno strumento di gestione della configurazione per eseguire il push di un file con il nome ```mdatp_managed.json``` nel percorso ```/etc/opt/microsoft/mdatp/managed/``` .</span><span class="sxs-lookup"><span data-stu-id="c6caf-120">Typically, you would use a configuration management tool to push a file with the name ```mdatp_managed.json``` at the location ```/etc/opt/microsoft/mdatp/managed/```.</span></span>

<span data-ttu-id="c6caf-121">Il livello superiore del profilo di configurazione include le preferenze e le voci a livello di prodotto per le sottoaree del prodotto, che vengono illustrate in modo più dettagliato nelle sezioni successive.</span><span class="sxs-lookup"><span data-stu-id="c6caf-121">The top level of the configuration profile includes product-wide preferences and entries for subareas of the product, which are explained in more detail in the next sections.</span></span>

### <a name="antivirus-engine-preferences"></a><span data-ttu-id="c6caf-122">Preferenze del motore antivirus</span><span class="sxs-lookup"><span data-stu-id="c6caf-122">Antivirus engine preferences</span></span>

<span data-ttu-id="c6caf-123">La *sezione antivirusEngine* del profilo di configurazione viene utilizzata per gestire le preferenze del componente antivirus del prodotto.</span><span class="sxs-lookup"><span data-stu-id="c6caf-123">The *antivirusEngine* section of the configuration profile is used to manage the preferences of the antivirus component of the product.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c6caf-124">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="c6caf-124">**Key**</span></span> | <span data-ttu-id="c6caf-125">antivirusEngine</span><span class="sxs-lookup"><span data-stu-id="c6caf-125">antivirusEngine</span></span> |
| <span data-ttu-id="c6caf-126">**Data type**</span><span class="sxs-lookup"><span data-stu-id="c6caf-126">**Data type**</span></span> | <span data-ttu-id="c6caf-127">Dizionario (preferenza annidata)</span><span class="sxs-lookup"><span data-stu-id="c6caf-127">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="c6caf-128">**Comments**</span><span class="sxs-lookup"><span data-stu-id="c6caf-128">**Comments**</span></span> | <span data-ttu-id="c6caf-129">Per una descrizione del contenuto del dizionario, vedi le sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="c6caf-129">See the following sections for a description of the dictionary contents.</span></span> |
|||

#### <a name="enable--disable-real-time-protection"></a><span data-ttu-id="c6caf-130">Abilitare/disabilitare la protezione in tempo reale</span><span class="sxs-lookup"><span data-stu-id="c6caf-130">Enable / disable real-time protection</span></span>

<span data-ttu-id="c6caf-131">Determina se la protezione in tempo reale (analizza i file quando vi si accede) è abilitata o meno.</span><span class="sxs-lookup"><span data-stu-id="c6caf-131">Determines whether real-time protection (scan files as they are accessed) is enabled or not.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c6caf-132">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="c6caf-132">**Key**</span></span> | <span data-ttu-id="c6caf-133">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="c6caf-133">enableRealTimeProtection</span></span> |
| <span data-ttu-id="c6caf-134">**Data type**</span><span class="sxs-lookup"><span data-stu-id="c6caf-134">**Data type**</span></span> | <span data-ttu-id="c6caf-135">Booleano</span><span class="sxs-lookup"><span data-stu-id="c6caf-135">Boolean</span></span> |
| <span data-ttu-id="c6caf-136">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="c6caf-136">**Possible values**</span></span> | <span data-ttu-id="c6caf-137">true (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="c6caf-137">true (default)</span></span> <br/> <span data-ttu-id="c6caf-138">false</span><span class="sxs-lookup"><span data-stu-id="c6caf-138">false</span></span> |
|||

#### <a name="enable--disable-passive-mode"></a><span data-ttu-id="c6caf-139">Abilitare/disabilitare la modalità passiva</span><span class="sxs-lookup"><span data-stu-id="c6caf-139">Enable / disable passive mode</span></span>

<span data-ttu-id="c6caf-140">Determina se il motore antivirus viene eseguito in modalità passiva o meno.</span><span class="sxs-lookup"><span data-stu-id="c6caf-140">Determines whether the antivirus engine runs in passive mode or not.</span></span> <span data-ttu-id="c6caf-141">In modalità passiva:</span><span class="sxs-lookup"><span data-stu-id="c6caf-141">In passive mode:</span></span>
- <span data-ttu-id="c6caf-142">La protezione in tempo reale è disattivata.</span><span class="sxs-lookup"><span data-stu-id="c6caf-142">Real-time protection is turned off.</span></span>
- <span data-ttu-id="c6caf-143">L'analisi su richiesta è attivata.</span><span class="sxs-lookup"><span data-stu-id="c6caf-143">On-demand scanning is turned on.</span></span>
- <span data-ttu-id="c6caf-144">La correzione automatica delle minacce è disattivata.</span><span class="sxs-lookup"><span data-stu-id="c6caf-144">Automatic threat remediation is turned off.</span></span>
- <span data-ttu-id="c6caf-145">Gli aggiornamenti delle funzionalità di intelligence per la sicurezza sono attivati.</span><span class="sxs-lookup"><span data-stu-id="c6caf-145">Security intelligence updates are turned on.</span></span>
- <span data-ttu-id="c6caf-146">L'icona del menu Stato è nascosta.</span><span class="sxs-lookup"><span data-stu-id="c6caf-146">Status menu icon is hidden.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c6caf-147">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="c6caf-147">**Key**</span></span> | <span data-ttu-id="c6caf-148">passiveMode</span><span class="sxs-lookup"><span data-stu-id="c6caf-148">passiveMode</span></span> |
| <span data-ttu-id="c6caf-149">**Data type**</span><span class="sxs-lookup"><span data-stu-id="c6caf-149">**Data type**</span></span> | <span data-ttu-id="c6caf-150">Booleano</span><span class="sxs-lookup"><span data-stu-id="c6caf-150">Boolean</span></span> |
| <span data-ttu-id="c6caf-151">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="c6caf-151">**Possible values**</span></span> | <span data-ttu-id="c6caf-152">false (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="c6caf-152">false (default)</span></span> <br/> <span data-ttu-id="c6caf-153">true</span><span class="sxs-lookup"><span data-stu-id="c6caf-153">true</span></span> |
| <span data-ttu-id="c6caf-154">**Comments**</span><span class="sxs-lookup"><span data-stu-id="c6caf-154">**Comments**</span></span> | <span data-ttu-id="c6caf-155">Disponibile in Defender per Endpoint versione 100.67.60 o successiva.</span><span class="sxs-lookup"><span data-stu-id="c6caf-155">Available in Defender for Endpoint version 100.67.60 or higher.</span></span> |
|||

#### <a name="exclusion-merge-policy"></a><span data-ttu-id="c6caf-156">Criteri di unione esclusioni</span><span class="sxs-lookup"><span data-stu-id="c6caf-156">Exclusion merge policy</span></span>

<span data-ttu-id="c6caf-157">Specifica i criteri di unione per le esclusioni.</span><span class="sxs-lookup"><span data-stu-id="c6caf-157">Specifies the merge policy for exclusions.</span></span> <span data-ttu-id="c6caf-158">Può essere una combinazione di esclusioni definite dall'amministratore e definite dall'utente ( ) o solo esclusioni definite `merge` dall'amministratore ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="c6caf-158">It can be a combination of administrator-defined and user-defined exclusions (`merge`) or only administrator-defined exclusions (`admin_only`).</span></span> <span data-ttu-id="c6caf-159">Questa impostazione può essere utilizzata per impedire agli utenti locali di definire le proprie esclusioni.</span><span class="sxs-lookup"><span data-stu-id="c6caf-159">This setting can be used to restrict local users from defining their own exclusions.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c6caf-160">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="c6caf-160">**Key**</span></span> | <span data-ttu-id="c6caf-161">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="c6caf-161">exclusionsMergePolicy</span></span> |
| <span data-ttu-id="c6caf-162">**Data type**</span><span class="sxs-lookup"><span data-stu-id="c6caf-162">**Data type**</span></span> | <span data-ttu-id="c6caf-163">Stringa</span><span class="sxs-lookup"><span data-stu-id="c6caf-163">String</span></span> |
| <span data-ttu-id="c6caf-164">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="c6caf-164">**Possible values**</span></span> | <span data-ttu-id="c6caf-165">merge (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="c6caf-165">merge (default)</span></span> <br/> <span data-ttu-id="c6caf-166">admin_only</span><span class="sxs-lookup"><span data-stu-id="c6caf-166">admin_only</span></span> |
| <span data-ttu-id="c6caf-167">**Comments**</span><span class="sxs-lookup"><span data-stu-id="c6caf-167">**Comments**</span></span> | <span data-ttu-id="c6caf-168">Disponibile in Defender per Endpoint versione 100.83.73 o successiva.</span><span class="sxs-lookup"><span data-stu-id="c6caf-168">Available in Defender for Endpoint version 100.83.73 or higher.</span></span> |
|||

#### <a name="scan-exclusions"></a><span data-ttu-id="c6caf-169">Esclusioni analisi</span><span class="sxs-lookup"><span data-stu-id="c6caf-169">Scan exclusions</span></span>

<span data-ttu-id="c6caf-170">Entità escluse dall'analisi.</span><span class="sxs-lookup"><span data-stu-id="c6caf-170">Entities that have been excluded from the scan.</span></span> <span data-ttu-id="c6caf-171">Le esclusioni possono essere specificate da percorsi completi, estensioni o nomi di file.</span><span class="sxs-lookup"><span data-stu-id="c6caf-171">Exclusions can be specified by full paths, extensions, or file names.</span></span>
<span data-ttu-id="c6caf-172">Le esclusioni vengono specificate come matrice di elementi, l'amministratore può specificare il numero di elementi necessario, in qualsiasi ordine.</span><span class="sxs-lookup"><span data-stu-id="c6caf-172">(Exclusions are specified as an array of items, administrator can specify as many elements as necessary, in any order.)</span></span>

|||
|:---|:---|
| <span data-ttu-id="c6caf-173">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="c6caf-173">**Key**</span></span> | <span data-ttu-id="c6caf-174">esclusioni</span><span class="sxs-lookup"><span data-stu-id="c6caf-174">exclusions</span></span> |
| <span data-ttu-id="c6caf-175">**Data type**</span><span class="sxs-lookup"><span data-stu-id="c6caf-175">**Data type**</span></span> | <span data-ttu-id="c6caf-176">Dizionario (preferenza annidata)</span><span class="sxs-lookup"><span data-stu-id="c6caf-176">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="c6caf-177">**Comments**</span><span class="sxs-lookup"><span data-stu-id="c6caf-177">**Comments**</span></span> | <span data-ttu-id="c6caf-178">Per una descrizione del contenuto del dizionario, vedi le sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="c6caf-178">See the following sections for a description of the dictionary contents.</span></span> |
|||

<span data-ttu-id="c6caf-179">**Tipo di esclusione**</span><span class="sxs-lookup"><span data-stu-id="c6caf-179">**Type of exclusion**</span></span>

<span data-ttu-id="c6caf-180">Specifica il tipo di contenuto escluso dall'analisi.</span><span class="sxs-lookup"><span data-stu-id="c6caf-180">Specifies the type of content excluded from the scan.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c6caf-181">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="c6caf-181">**Key**</span></span> | <span data-ttu-id="c6caf-182">$type</span><span class="sxs-lookup"><span data-stu-id="c6caf-182">$type</span></span> |
| <span data-ttu-id="c6caf-183">**Data type**</span><span class="sxs-lookup"><span data-stu-id="c6caf-183">**Data type**</span></span> | <span data-ttu-id="c6caf-184">Stringa</span><span class="sxs-lookup"><span data-stu-id="c6caf-184">String</span></span> |
| <span data-ttu-id="c6caf-185">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="c6caf-185">**Possible values**</span></span> | <span data-ttu-id="c6caf-186">excludedPath</span><span class="sxs-lookup"><span data-stu-id="c6caf-186">excludedPath</span></span> <br/> <span data-ttu-id="c6caf-187">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="c6caf-187">excludedFileExtension</span></span> <br/> <span data-ttu-id="c6caf-188">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="c6caf-188">excludedFileName</span></span> |
|||

<span data-ttu-id="c6caf-189">**Percorso del contenuto escluso**</span><span class="sxs-lookup"><span data-stu-id="c6caf-189">**Path to excluded content**</span></span>

<span data-ttu-id="c6caf-190">Utilizzato per escludere il contenuto dall'analisi in base al percorso completo del file.</span><span class="sxs-lookup"><span data-stu-id="c6caf-190">Used to exclude content from the scan by full file path.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c6caf-191">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="c6caf-191">**Key**</span></span> | <span data-ttu-id="c6caf-192">path</span><span class="sxs-lookup"><span data-stu-id="c6caf-192">path</span></span> |
| <span data-ttu-id="c6caf-193">**Data type**</span><span class="sxs-lookup"><span data-stu-id="c6caf-193">**Data type**</span></span> | <span data-ttu-id="c6caf-194">Stringa</span><span class="sxs-lookup"><span data-stu-id="c6caf-194">String</span></span> |
| <span data-ttu-id="c6caf-195">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="c6caf-195">**Possible values**</span></span> | <span data-ttu-id="c6caf-196">percorsi validi</span><span class="sxs-lookup"><span data-stu-id="c6caf-196">valid paths</span></span> |
| <span data-ttu-id="c6caf-197">**Comments**</span><span class="sxs-lookup"><span data-stu-id="c6caf-197">**Comments**</span></span> | <span data-ttu-id="c6caf-198">Applicabile solo se *$type* *è excludedPath*</span><span class="sxs-lookup"><span data-stu-id="c6caf-198">Applicable only if *$type* is *excludedPath*</span></span> |
|||

<span data-ttu-id="c6caf-199">**Tipo di percorso (file/directory)**</span><span class="sxs-lookup"><span data-stu-id="c6caf-199">**Path type (file / directory)**</span></span>

<span data-ttu-id="c6caf-200">Indica se la proprietà *path* fa riferimento a un file o a una directory.</span><span class="sxs-lookup"><span data-stu-id="c6caf-200">Indicates if the *path* property refers to a file or directory.</span></span> 

|||
|:---|:---|
| <span data-ttu-id="c6caf-201">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="c6caf-201">**Key**</span></span> | <span data-ttu-id="c6caf-202">isDirectory</span><span class="sxs-lookup"><span data-stu-id="c6caf-202">isDirectory</span></span> |
| <span data-ttu-id="c6caf-203">**Data type**</span><span class="sxs-lookup"><span data-stu-id="c6caf-203">**Data type**</span></span> | <span data-ttu-id="c6caf-204">Booleano</span><span class="sxs-lookup"><span data-stu-id="c6caf-204">Boolean</span></span> |
| <span data-ttu-id="c6caf-205">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="c6caf-205">**Possible values**</span></span> | <span data-ttu-id="c6caf-206">false (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="c6caf-206">false (default)</span></span> <br/> <span data-ttu-id="c6caf-207">true</span><span class="sxs-lookup"><span data-stu-id="c6caf-207">true</span></span> |
| <span data-ttu-id="c6caf-208">**Comments**</span><span class="sxs-lookup"><span data-stu-id="c6caf-208">**Comments**</span></span> | <span data-ttu-id="c6caf-209">Applicabile solo se *$type* *è excludedPath*</span><span class="sxs-lookup"><span data-stu-id="c6caf-209">Applicable only if *$type* is *excludedPath*</span></span> |
|||

<span data-ttu-id="c6caf-210">**Estensione di file esclusa dall'analisi**</span><span class="sxs-lookup"><span data-stu-id="c6caf-210">**File extension excluded from the scan**</span></span>

<span data-ttu-id="c6caf-211">Usato per escludere il contenuto dall'analisi per estensione di file.</span><span class="sxs-lookup"><span data-stu-id="c6caf-211">Used to exclude content from the scan by file extension.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c6caf-212">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="c6caf-212">**Key**</span></span> | <span data-ttu-id="c6caf-213">extension</span><span class="sxs-lookup"><span data-stu-id="c6caf-213">extension</span></span> |
| <span data-ttu-id="c6caf-214">**Data type**</span><span class="sxs-lookup"><span data-stu-id="c6caf-214">**Data type**</span></span> | <span data-ttu-id="c6caf-215">Stringa</span><span class="sxs-lookup"><span data-stu-id="c6caf-215">String</span></span> |
| <span data-ttu-id="c6caf-216">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="c6caf-216">**Possible values**</span></span> | <span data-ttu-id="c6caf-217">estensioni di file valide</span><span class="sxs-lookup"><span data-stu-id="c6caf-217">valid file extensions</span></span> |
| <span data-ttu-id="c6caf-218">**Comments**</span><span class="sxs-lookup"><span data-stu-id="c6caf-218">**Comments**</span></span> | <span data-ttu-id="c6caf-219">Applicabile solo se *$type* *è excludedFileExtension*</span><span class="sxs-lookup"><span data-stu-id="c6caf-219">Applicable only if *$type* is *excludedFileExtension*</span></span> |
|||

<span data-ttu-id="c6caf-220">**Processo escluso dall'analisi**</span><span class="sxs-lookup"><span data-stu-id="c6caf-220">**Process excluded from the scan**</span></span>

<span data-ttu-id="c6caf-221">Specifica un processo per il quale tutte le attività di file vengono escluse dall'analisi.</span><span class="sxs-lookup"><span data-stu-id="c6caf-221">Specifies a process for which all file activity is excluded from scanning.</span></span> <span data-ttu-id="c6caf-222">Il processo può essere specificato in base al nome (ad esempio, `cat` ) o al percorso completo (ad esempio, `/bin/cat` ).</span><span class="sxs-lookup"><span data-stu-id="c6caf-222">The process can be specified either by its name (for example, `cat`) or full path (for example, `/bin/cat`).</span></span>

|||
|:---|:---|
| <span data-ttu-id="c6caf-223">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="c6caf-223">**Key**</span></span> | <span data-ttu-id="c6caf-224">name</span><span class="sxs-lookup"><span data-stu-id="c6caf-224">name</span></span> |
| <span data-ttu-id="c6caf-225">**Data type**</span><span class="sxs-lookup"><span data-stu-id="c6caf-225">**Data type**</span></span> | <span data-ttu-id="c6caf-226">Stringa</span><span class="sxs-lookup"><span data-stu-id="c6caf-226">String</span></span> |
| <span data-ttu-id="c6caf-227">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="c6caf-227">**Possible values**</span></span> | <span data-ttu-id="c6caf-228">qualsiasi stringa</span><span class="sxs-lookup"><span data-stu-id="c6caf-228">any string</span></span> |
| <span data-ttu-id="c6caf-229">**Comments**</span><span class="sxs-lookup"><span data-stu-id="c6caf-229">**Comments**</span></span> | <span data-ttu-id="c6caf-230">Applicabile solo se *$type* *è excludedFileName*</span><span class="sxs-lookup"><span data-stu-id="c6caf-230">Applicable only if *$type* is *excludedFileName*</span></span> |
|||

#### <a name="allowed-threats"></a><span data-ttu-id="c6caf-231">Minacce consentite</span><span class="sxs-lookup"><span data-stu-id="c6caf-231">Allowed threats</span></span>

<span data-ttu-id="c6caf-232">Elenco delle minacce (identificate dal nome) che non sono bloccate dal prodotto e che possono essere eseguite.</span><span class="sxs-lookup"><span data-stu-id="c6caf-232">List of threats (identified by their name) that are not blocked by the product and are instead allowed to run.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c6caf-233">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="c6caf-233">**Key**</span></span> | <span data-ttu-id="c6caf-234">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="c6caf-234">allowedThreats</span></span> |
| <span data-ttu-id="c6caf-235">**Data type**</span><span class="sxs-lookup"><span data-stu-id="c6caf-235">**Data type**</span></span> | <span data-ttu-id="c6caf-236">Matrice di stringhe</span><span class="sxs-lookup"><span data-stu-id="c6caf-236">Array of strings</span></span> |
|||

#### <a name="disallowed-threat-actions"></a><span data-ttu-id="c6caf-237">Azioni di minaccia non consentite</span><span class="sxs-lookup"><span data-stu-id="c6caf-237">Disallowed threat actions</span></span>

<span data-ttu-id="c6caf-238">Limita le azioni che l'utente locale di un dispositivo può intraprendere quando vengono rilevate minacce.</span><span class="sxs-lookup"><span data-stu-id="c6caf-238">Restricts the actions that the local user of a device can take when threats are detected.</span></span> <span data-ttu-id="c6caf-239">Le azioni incluse in questo elenco non vengono visualizzate nell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="c6caf-239">The actions included in this list are not displayed in the user interface.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c6caf-240">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="c6caf-240">**Key**</span></span> | <span data-ttu-id="c6caf-241">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="c6caf-241">disallowedThreatActions</span></span> |
| <span data-ttu-id="c6caf-242">**Data type**</span><span class="sxs-lookup"><span data-stu-id="c6caf-242">**Data type**</span></span> | <span data-ttu-id="c6caf-243">Matrice di stringhe</span><span class="sxs-lookup"><span data-stu-id="c6caf-243">Array of strings</span></span> |
| <span data-ttu-id="c6caf-244">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="c6caf-244">**Possible values**</span></span> | <span data-ttu-id="c6caf-245">allow (impedisce agli utenti di consentire minacce)</span><span class="sxs-lookup"><span data-stu-id="c6caf-245">allow (restricts users from allowing threats)</span></span> <br/> <span data-ttu-id="c6caf-246">restore (impedisce agli utenti di ripristinare le minacce dalla quarantena)</span><span class="sxs-lookup"><span data-stu-id="c6caf-246">restore (restricts users from restoring threats from the quarantine)</span></span> |
| <span data-ttu-id="c6caf-247">**Comments**</span><span class="sxs-lookup"><span data-stu-id="c6caf-247">**Comments**</span></span> | <span data-ttu-id="c6caf-248">Disponibile in Defender per Endpoint versione 100.83.73 o successiva.</span><span class="sxs-lookup"><span data-stu-id="c6caf-248">Available in Defender for Endpoint version 100.83.73 or higher.</span></span> |
|||

#### <a name="threat-type-settings"></a><span data-ttu-id="c6caf-249">Impostazioni del tipo di minaccia</span><span class="sxs-lookup"><span data-stu-id="c6caf-249">Threat type settings</span></span>

<span data-ttu-id="c6caf-250">La *preferenza threatTypeSettings* nel motore antivirus viene utilizzata per controllare la modalità di gestione di determinati tipi di minacce da parte del prodotto.</span><span class="sxs-lookup"><span data-stu-id="c6caf-250">The *threatTypeSettings* preference in the antivirus engine is used to control how certain threat types are handled by the product.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c6caf-251">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="c6caf-251">**Key**</span></span> | <span data-ttu-id="c6caf-252">threatTypeSettings</span><span class="sxs-lookup"><span data-stu-id="c6caf-252">threatTypeSettings</span></span> |
| <span data-ttu-id="c6caf-253">**Data type**</span><span class="sxs-lookup"><span data-stu-id="c6caf-253">**Data type**</span></span> | <span data-ttu-id="c6caf-254">Dizionario (preferenza annidata)</span><span class="sxs-lookup"><span data-stu-id="c6caf-254">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="c6caf-255">**Comments**</span><span class="sxs-lookup"><span data-stu-id="c6caf-255">**Comments**</span></span> | <span data-ttu-id="c6caf-256">Per una descrizione del contenuto del dizionario, vedi le sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="c6caf-256">See the following sections for a description of the dictionary contents.</span></span> |
|||

<span data-ttu-id="c6caf-257">**Tipo di minaccia**</span><span class="sxs-lookup"><span data-stu-id="c6caf-257">**Threat type**</span></span>

<span data-ttu-id="c6caf-258">Tipo di minaccia per cui è configurato il comportamento.</span><span class="sxs-lookup"><span data-stu-id="c6caf-258">Type of threat for which the behavior is configured.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c6caf-259">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="c6caf-259">**Key**</span></span> | <span data-ttu-id="c6caf-260">chiave</span><span class="sxs-lookup"><span data-stu-id="c6caf-260">key</span></span> |
| <span data-ttu-id="c6caf-261">**Data type**</span><span class="sxs-lookup"><span data-stu-id="c6caf-261">**Data type**</span></span> | <span data-ttu-id="c6caf-262">Stringa</span><span class="sxs-lookup"><span data-stu-id="c6caf-262">String</span></span> |
| <span data-ttu-id="c6caf-263">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="c6caf-263">**Possible values**</span></span> | <span data-ttu-id="c6caf-264">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="c6caf-264">potentially_unwanted_application</span></span> <br/> <span data-ttu-id="c6caf-265">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="c6caf-265">archive_bomb</span></span> |
|||

<span data-ttu-id="c6caf-266">**Procedura da seguire**</span><span class="sxs-lookup"><span data-stu-id="c6caf-266">**Action to take**</span></span>

<span data-ttu-id="c6caf-267">Azione da intraprendere quando si verifica una minaccia del tipo specificato nella sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="c6caf-267">Action to take when coming across a threat of the type specified in the preceding section.</span></span> <span data-ttu-id="c6caf-268">Può essere:</span><span class="sxs-lookup"><span data-stu-id="c6caf-268">Can be:</span></span>

- <span data-ttu-id="c6caf-269">**Controllo:** il dispositivo non è protetto da questo tipo di minaccia, ma viene registrata una voce relativa alla minaccia.</span><span class="sxs-lookup"><span data-stu-id="c6caf-269">**Audit**: The device is not protected against this type of threat, but an entry about the threat is logged.</span></span>
- <span data-ttu-id="c6caf-270">**Blocca**: il dispositivo è protetto da questo tipo di minaccia e si viene informati nella console di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="c6caf-270">**Block**: The device is protected against this type of threat and you are notified in the security console.</span></span>
- <span data-ttu-id="c6caf-271">**Disattivato:** il dispositivo non è protetto da questo tipo di minaccia e non viene registrato nulla.</span><span class="sxs-lookup"><span data-stu-id="c6caf-271">**Off**: The device is not protected against this type of threat and nothing is logged.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c6caf-272">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="c6caf-272">**Key**</span></span> | <span data-ttu-id="c6caf-273">valore</span><span class="sxs-lookup"><span data-stu-id="c6caf-273">value</span></span> |
| <span data-ttu-id="c6caf-274">**Data type**</span><span class="sxs-lookup"><span data-stu-id="c6caf-274">**Data type**</span></span> | <span data-ttu-id="c6caf-275">Stringa</span><span class="sxs-lookup"><span data-stu-id="c6caf-275">String</span></span> |
| <span data-ttu-id="c6caf-276">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="c6caf-276">**Possible values**</span></span> | <span data-ttu-id="c6caf-277">audit (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="c6caf-277">audit (default)</span></span> <br/> <span data-ttu-id="c6caf-278">blocco</span><span class="sxs-lookup"><span data-stu-id="c6caf-278">block</span></span> <br/> <span data-ttu-id="c6caf-279">off</span><span class="sxs-lookup"><span data-stu-id="c6caf-279">off</span></span> |
|||

#### <a name="threat-type-settings-merge-policy"></a><span data-ttu-id="c6caf-280">Criteri di unione delle impostazioni del tipo di minaccia</span><span class="sxs-lookup"><span data-stu-id="c6caf-280">Threat type settings merge policy</span></span>

<span data-ttu-id="c6caf-281">Specifica il criterio di unione per le impostazioni del tipo di minaccia.</span><span class="sxs-lookup"><span data-stu-id="c6caf-281">Specifies the merge policy for threat type settings.</span></span> <span data-ttu-id="c6caf-282">Può essere una combinazione di impostazioni definite dall'amministratore e definite dall'utente ( ) o solo impostazioni definite `merge` dall'amministratore ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="c6caf-282">This can be a combination of administrator-defined and user-defined settings (`merge`) or only administrator-defined settings (`admin_only`).</span></span> <span data-ttu-id="c6caf-283">Questa impostazione può essere usata per impedire agli utenti locali di definire le proprie impostazioni per diversi tipi di minacce.</span><span class="sxs-lookup"><span data-stu-id="c6caf-283">This setting can be used to restrict local users from defining their own settings for different threat types.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c6caf-284">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="c6caf-284">**Key**</span></span> | <span data-ttu-id="c6caf-285">threatTypeSettingsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="c6caf-285">threatTypeSettingsMergePolicy</span></span> |
| <span data-ttu-id="c6caf-286">**Data type**</span><span class="sxs-lookup"><span data-stu-id="c6caf-286">**Data type**</span></span> | <span data-ttu-id="c6caf-287">Stringa</span><span class="sxs-lookup"><span data-stu-id="c6caf-287">String</span></span> |
| <span data-ttu-id="c6caf-288">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="c6caf-288">**Possible values**</span></span> | <span data-ttu-id="c6caf-289">merge (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="c6caf-289">merge (default)</span></span> <br/> <span data-ttu-id="c6caf-290">admin_only</span><span class="sxs-lookup"><span data-stu-id="c6caf-290">admin_only</span></span> |
| <span data-ttu-id="c6caf-291">**Comments**</span><span class="sxs-lookup"><span data-stu-id="c6caf-291">**Comments**</span></span> | <span data-ttu-id="c6caf-292">Disponibile in Defender per Endpoint versione 100.83.73 o successiva.</span><span class="sxs-lookup"><span data-stu-id="c6caf-292">Available in Defender for Endpoint version 100.83.73 or higher.</span></span> |
|||

#### <a name="antivirus-scan-history-retention-in-days"></a><span data-ttu-id="c6caf-293">Conservazione cronologia analisi antivirus (in giorni)</span><span class="sxs-lookup"><span data-stu-id="c6caf-293">Antivirus scan history retention (in days)</span></span>

<span data-ttu-id="c6caf-294">Specifica il numero di giorni in cui i risultati vengono conservati nella cronologia dell'analisi nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c6caf-294">Specify the number of days that results are retained in the scan history on the device.</span></span> <span data-ttu-id="c6caf-295">I risultati dell'analisi precedente vengono rimossi dalla cronologia.</span><span class="sxs-lookup"><span data-stu-id="c6caf-295">Old scan results are removed from the history.</span></span> <span data-ttu-id="c6caf-296">Vecchi file in quarantena che vengono rimossi anche dal disco.</span><span class="sxs-lookup"><span data-stu-id="c6caf-296">Old quarantined files that are also removed from the disk.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c6caf-297">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="c6caf-297">**Key**</span></span> | <span data-ttu-id="c6caf-298">scanResultsRetentionDays</span><span class="sxs-lookup"><span data-stu-id="c6caf-298">scanResultsRetentionDays</span></span> |
| <span data-ttu-id="c6caf-299">**Data type**</span><span class="sxs-lookup"><span data-stu-id="c6caf-299">**Data type**</span></span> | <span data-ttu-id="c6caf-300">Stringa</span><span class="sxs-lookup"><span data-stu-id="c6caf-300">String</span></span> |
| <span data-ttu-id="c6caf-301">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="c6caf-301">**Possible values**</span></span> | <span data-ttu-id="c6caf-302">90 (impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="c6caf-302">90 (default).</span></span> <span data-ttu-id="c6caf-303">I valori consentiti sono da 1 giorno a 180 giorni.</span><span class="sxs-lookup"><span data-stu-id="c6caf-303">Allowed values are from 1 day to 180 days.</span></span> |
| <span data-ttu-id="c6caf-304">**Comments**</span><span class="sxs-lookup"><span data-stu-id="c6caf-304">**Comments**</span></span> | <span data-ttu-id="c6caf-305">Disponibile in Defender per Endpoint versione 101.04.76 o successiva.</span><span class="sxs-lookup"><span data-stu-id="c6caf-305">Available in Defender for Endpoint version 101.04.76 or higher.</span></span> |
|||

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a><span data-ttu-id="c6caf-306">Numero massimo di elementi nella cronologia dell'analisi antivirus</span><span class="sxs-lookup"><span data-stu-id="c6caf-306">Maximum number of items in the antivirus scan history</span></span>

<span data-ttu-id="c6caf-307">Specificare il numero massimo di voci da mantenere nella cronologia di analisi.</span><span class="sxs-lookup"><span data-stu-id="c6caf-307">Specify the maximum number of entries to keep in the scan history.</span></span> <span data-ttu-id="c6caf-308">Le voci includono tutte le analisi su richiesta eseguite in passato e tutti i rilevamenti antivirus.</span><span class="sxs-lookup"><span data-stu-id="c6caf-308">Entries include all on-demand scans performed in the past and all antivirus detections.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c6caf-309">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="c6caf-309">**Key**</span></span> | <span data-ttu-id="c6caf-310">scanHistoryMaximumItems</span><span class="sxs-lookup"><span data-stu-id="c6caf-310">scanHistoryMaximumItems</span></span> |
| <span data-ttu-id="c6caf-311">**Data type**</span><span class="sxs-lookup"><span data-stu-id="c6caf-311">**Data type**</span></span> | <span data-ttu-id="c6caf-312">Stringa</span><span class="sxs-lookup"><span data-stu-id="c6caf-312">String</span></span> |
| <span data-ttu-id="c6caf-313">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="c6caf-313">**Possible values**</span></span> | <span data-ttu-id="c6caf-314">10000 (impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="c6caf-314">10000 (default).</span></span> <span data-ttu-id="c6caf-315">I valori consentiti sono da 5.000 elementi a 15.000 elementi.</span><span class="sxs-lookup"><span data-stu-id="c6caf-315">Allowed values are from 5000 items to 15000 items.</span></span> |
| <span data-ttu-id="c6caf-316">**Comments**</span><span class="sxs-lookup"><span data-stu-id="c6caf-316">**Comments**</span></span> | <span data-ttu-id="c6caf-317">Disponibile in Defender per Endpoint versione 101.04.76 o successiva.</span><span class="sxs-lookup"><span data-stu-id="c6caf-317">Available in Defender for Endpoint version 101.04.76 or higher.</span></span> |
|||

### <a name="cloud-delivered-protection-preferences"></a><span data-ttu-id="c6caf-318">Preferenze di protezione per il cloud</span><span class="sxs-lookup"><span data-stu-id="c6caf-318">Cloud-delivered protection preferences</span></span>

<span data-ttu-id="c6caf-319">La *voce cloudService* nel profilo di configurazione viene utilizzata per configurare la funzionalità di protezione basata sul cloud del prodotto.</span><span class="sxs-lookup"><span data-stu-id="c6caf-319">The *cloudService* entry in the configuration profile is used to configure the cloud-driven protection feature of the product.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c6caf-320">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="c6caf-320">**Key**</span></span> | <span data-ttu-id="c6caf-321">cloudService</span><span class="sxs-lookup"><span data-stu-id="c6caf-321">cloudService</span></span> |
| <span data-ttu-id="c6caf-322">**Data type**</span><span class="sxs-lookup"><span data-stu-id="c6caf-322">**Data type**</span></span> | <span data-ttu-id="c6caf-323">Dizionario (preferenza annidata)</span><span class="sxs-lookup"><span data-stu-id="c6caf-323">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="c6caf-324">**Comments**</span><span class="sxs-lookup"><span data-stu-id="c6caf-324">**Comments**</span></span> | <span data-ttu-id="c6caf-325">Per una descrizione del contenuto del dizionario, vedi le sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="c6caf-325">See the following sections for a description of the dictionary contents.</span></span> |
|||

#### <a name="enable--disable-cloud-delivered-protection"></a><span data-ttu-id="c6caf-326">Abilitare/disabilitare la protezione recapitata nel cloud</span><span class="sxs-lookup"><span data-stu-id="c6caf-326">Enable / disable cloud delivered protection</span></span>

<span data-ttu-id="c6caf-327">Determina se la protezione consegnata dal cloud è abilitata o meno nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c6caf-327">Determines whether cloud-delivered protection is enabled on the device or not.</span></span> <span data-ttu-id="c6caf-328">Per migliorare la sicurezza dei servizi, è consigliabile mantenere attivata questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="c6caf-328">To improve the security of your services, we recommend keeping this feature turned on.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c6caf-329">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="c6caf-329">**Key**</span></span> | <span data-ttu-id="c6caf-330">abilitati</span><span class="sxs-lookup"><span data-stu-id="c6caf-330">enabled</span></span> |
| <span data-ttu-id="c6caf-331">**Data type**</span><span class="sxs-lookup"><span data-stu-id="c6caf-331">**Data type**</span></span> | <span data-ttu-id="c6caf-332">Booleano</span><span class="sxs-lookup"><span data-stu-id="c6caf-332">Boolean</span></span> |
| <span data-ttu-id="c6caf-333">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="c6caf-333">**Possible values**</span></span> | <span data-ttu-id="c6caf-334">true (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="c6caf-334">true (default)</span></span> <br/> <span data-ttu-id="c6caf-335">false</span><span class="sxs-lookup"><span data-stu-id="c6caf-335">false</span></span> |
|||

#### <a name="diagnostic-collection-level"></a><span data-ttu-id="c6caf-336">Livello raccolta diagnostica</span><span class="sxs-lookup"><span data-stu-id="c6caf-336">Diagnostic collection level</span></span>

<span data-ttu-id="c6caf-337">I dati di diagnostica vengono usati per mantenere Defender per Endpoint sicuro e aggiornato, rilevare, diagnosticare e risolvere i problemi e apportare miglioramenti al prodotto.</span><span class="sxs-lookup"><span data-stu-id="c6caf-337">Diagnostic data is used to keep Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span> <span data-ttu-id="c6caf-338">Questa impostazione determina il livello di diagnostica inviato dal prodotto a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c6caf-338">This setting determines the level of diagnostics sent by the product to Microsoft.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c6caf-339">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="c6caf-339">**Key**</span></span> | <span data-ttu-id="c6caf-340">diagnosticLevel</span><span class="sxs-lookup"><span data-stu-id="c6caf-340">diagnosticLevel</span></span> |
| <span data-ttu-id="c6caf-341">**Data type**</span><span class="sxs-lookup"><span data-stu-id="c6caf-341">**Data type**</span></span> | <span data-ttu-id="c6caf-342">Stringa</span><span class="sxs-lookup"><span data-stu-id="c6caf-342">String</span></span> |
| <span data-ttu-id="c6caf-343">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="c6caf-343">**Possible values**</span></span> | <span data-ttu-id="c6caf-344">facoltativo (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="c6caf-344">optional (default)</span></span> <br/> <span data-ttu-id="c6caf-345">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="c6caf-345">required</span></span> |
|||

#### <a name="enable--disable-automatic-sample-submissions"></a><span data-ttu-id="c6caf-346">Abilitare/disabilitare gli invii di esempio automatici</span><span class="sxs-lookup"><span data-stu-id="c6caf-346">Enable / disable automatic sample submissions</span></span>

<span data-ttu-id="c6caf-347">Determina se i campioni sospetti (che potrebbero contenere minacce) vengono inviati a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c6caf-347">Determines whether suspicious samples (that are likely to contain threats) are sent to Microsoft.</span></span> <span data-ttu-id="c6caf-348">Esistono tre livelli per controllare l'invio di campioni:</span><span class="sxs-lookup"><span data-stu-id="c6caf-348">There are three levels for controlling sample submission:</span></span>

- <span data-ttu-id="c6caf-349">**Nessuno:** nessun campione sospetto viene inviato a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c6caf-349">**None**: no suspicious samples are submitted to Microsoft.</span></span>
- <span data-ttu-id="c6caf-350">**Sicuro:** solo i campioni sospetti che non contengono informazioni personali vengono inviati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="c6caf-350">**Safe**: only suspicious samples that do not contain personally identifiable information (PII) are submitted automatically.</span></span> <span data-ttu-id="c6caf-351">Questo è il valore predefinito per questa impostazione.</span><span class="sxs-lookup"><span data-stu-id="c6caf-351">This is the default value for this setting.</span></span>
- <span data-ttu-id="c6caf-352">**All**: tutti i campioni sospetti vengono inviati a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c6caf-352">**All**: all suspicious samples are submitted to Microsoft.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c6caf-353">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="c6caf-353">**Key**</span></span> | <span data-ttu-id="c6caf-354">automaticSampleSubmissionConsent</span><span class="sxs-lookup"><span data-stu-id="c6caf-354">automaticSampleSubmissionConsent</span></span> |
| <span data-ttu-id="c6caf-355">**Data type**</span><span class="sxs-lookup"><span data-stu-id="c6caf-355">**Data type**</span></span> | <span data-ttu-id="c6caf-356">Stringa</span><span class="sxs-lookup"><span data-stu-id="c6caf-356">String</span></span> |
| <span data-ttu-id="c6caf-357">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="c6caf-357">**Possible values**</span></span> | <span data-ttu-id="c6caf-358">nessuno</span><span class="sxs-lookup"><span data-stu-id="c6caf-358">none</span></span> <br/> <span data-ttu-id="c6caf-359">safe (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="c6caf-359">safe (default)</span></span> <br/> <span data-ttu-id="c6caf-360">all</span><span class="sxs-lookup"><span data-stu-id="c6caf-360">all</span></span> |
|||

#### <a name="enable--disable-automatic-security-intelligence-updates"></a><span data-ttu-id="c6caf-361">Abilitare/disabilitare gli aggiornamenti automatici delle funzionalità di intelligence per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="c6caf-361">Enable / disable automatic security intelligence updates</span></span>

<span data-ttu-id="c6caf-362">Determina se gli aggiornamenti delle funzionalità di intelligence per la sicurezza vengono installati automaticamente:</span><span class="sxs-lookup"><span data-stu-id="c6caf-362">Determines whether security intelligence updates are installed automatically:</span></span>

|||
|:---|:---|
| <span data-ttu-id="c6caf-363">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="c6caf-363">**Key**</span></span> | <span data-ttu-id="c6caf-364">automaticDefinitionUpdateEnabled</span><span class="sxs-lookup"><span data-stu-id="c6caf-364">automaticDefinitionUpdateEnabled</span></span> |
| <span data-ttu-id="c6caf-365">**Data type**</span><span class="sxs-lookup"><span data-stu-id="c6caf-365">**Data type**</span></span> | <span data-ttu-id="c6caf-366">Booleano</span><span class="sxs-lookup"><span data-stu-id="c6caf-366">Boolean</span></span> |
| <span data-ttu-id="c6caf-367">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="c6caf-367">**Possible values**</span></span> | <span data-ttu-id="c6caf-368">true (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="c6caf-368">true (default)</span></span> <br/> <span data-ttu-id="c6caf-369">false</span><span class="sxs-lookup"><span data-stu-id="c6caf-369">false</span></span> |
|||

## <a name="recommended-configuration-profile"></a><span data-ttu-id="c6caf-370">Profilo di configurazione consigliato</span><span class="sxs-lookup"><span data-stu-id="c6caf-370">Recommended configuration profile</span></span>

<span data-ttu-id="c6caf-371">Per iniziare, ti consigliamo di usare il profilo di configurazione seguente per la tua azienda per sfruttare tutte le funzionalità di protezione fornite da Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="c6caf-371">To get started, we recommend the following configuration profile for your enterprise to take advantage of all protection features that Defender for Endpoint provides.</span></span>

<span data-ttu-id="c6caf-372">Il profilo di configurazione seguente:</span><span class="sxs-lookup"><span data-stu-id="c6caf-372">The following configuration profile will:</span></span>

- <span data-ttu-id="c6caf-373">Abilitare la protezione in tempo reale (RTP)</span><span class="sxs-lookup"><span data-stu-id="c6caf-373">Enable real-time protection (RTP)</span></span>
- <span data-ttu-id="c6caf-374">Specificare la modalità di gestione dei seguenti tipi di minacce:</span><span class="sxs-lookup"><span data-stu-id="c6caf-374">Specify how the following threat types are handled:</span></span>
  - <span data-ttu-id="c6caf-375">**Le applicazioni potenzialmente indesiderate sono** bloccate</span><span class="sxs-lookup"><span data-stu-id="c6caf-375">**Potentially unwanted applications (PUA)** are blocked</span></span>
  - <span data-ttu-id="c6caf-376">**Le bombe di** archiviazione (file con una velocità di compressione elevata) vengono verificate nei log del prodotto</span><span class="sxs-lookup"><span data-stu-id="c6caf-376">**Archive bombs** (file with a high compression rate) are audited to the product logs</span></span>
- <span data-ttu-id="c6caf-377">Abilitare gli aggiornamenti automatici delle funzionalità di intelligence per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="c6caf-377">Enable automatic security intelligence updates</span></span>
- <span data-ttu-id="c6caf-378">Abilitare la protezione fornita dal cloud</span><span class="sxs-lookup"><span data-stu-id="c6caf-378">Enable cloud-delivered protection</span></span>
- <span data-ttu-id="c6caf-379">Abilitare l'invio automatico di esempi a `safe` livello</span><span class="sxs-lookup"><span data-stu-id="c6caf-379">Enable automatic sample submission at `safe` level</span></span>

### <a name="sample-profile"></a><span data-ttu-id="c6caf-380">Profilo di esempio</span><span class="sxs-lookup"><span data-stu-id="c6caf-380">Sample profile</span></span>

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

## <a name="full-configuration-profile-example"></a><span data-ttu-id="c6caf-381">Esempio di profilo di configurazione completo</span><span class="sxs-lookup"><span data-stu-id="c6caf-381">Full configuration profile example</span></span>

<span data-ttu-id="c6caf-382">Il profilo di configurazione seguente contiene voci per tutte le impostazioni descritte in questo documento e può essere utilizzato per scenari più avanzati in cui si desidera un maggiore controllo sul prodotto.</span><span class="sxs-lookup"><span data-stu-id="c6caf-382">The following configuration profile contains entries for all settings described in this document and can be used for more advanced scenarios where you want more control over the product.</span></span>

### <a name="full-profile"></a><span data-ttu-id="c6caf-383">Profilo completo</span><span class="sxs-lookup"><span data-stu-id="c6caf-383">Full profile</span></span>

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
            "extension":"pdf"
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

## <a name="configuration-profile-validation"></a><span data-ttu-id="c6caf-384">Convalida del profilo di configurazione</span><span class="sxs-lookup"><span data-stu-id="c6caf-384">Configuration profile validation</span></span>

<span data-ttu-id="c6caf-385">Il profilo di configurazione deve essere un file in formato JSON valido.</span><span class="sxs-lookup"><span data-stu-id="c6caf-385">The configuration profile must be a valid JSON-formatted file.</span></span> <span data-ttu-id="c6caf-386">Per verificarlo, è possibile utilizzare diversi strumenti.</span><span class="sxs-lookup"><span data-stu-id="c6caf-386">There are a number of tools that can be used to verify this.</span></span> <span data-ttu-id="c6caf-387">Ad esempio, se hai `python` installato nel dispositivo:</span><span class="sxs-lookup"><span data-stu-id="c6caf-387">For example, if you have `python` installed on your device:</span></span>

```bash
python -m json.tool mdatp_managed.json
```

<span data-ttu-id="c6caf-388">Se json è ben formato, il comando precedente lo restituisce al terminale e restituisce un codice di uscita di `0` .</span><span class="sxs-lookup"><span data-stu-id="c6caf-388">If the JSON is well-formed, the above command outputs it back to the Terminal and returns an exit code of `0`.</span></span> <span data-ttu-id="c6caf-389">In caso contrario, viene visualizzato un errore che descrive il problema e il comando restituisce un codice di uscita di `1` .</span><span class="sxs-lookup"><span data-stu-id="c6caf-389">Otherwise, an error that describes the issue is displayed and the command returns an exit code of `1`.</span></span>

## <a name="verifying-that-the-mdatp_managedjson-file-is-working-as-expected"></a><span data-ttu-id="c6caf-390">Verifica del funzionamento mdatp_managed.jsfile nel modo previsto</span><span class="sxs-lookup"><span data-stu-id="c6caf-390">Verifying that the mdatp_managed.json file is working as expected</span></span>
<span data-ttu-id="c6caf-391">Per verificare che /etc/opt/microsoft/mdatp/managed/mdatp_managed.jsfunzioni correttamente, dovrebbe essere visualizzato "[gestito]" accanto a queste impostazioni:</span><span class="sxs-lookup"><span data-stu-id="c6caf-391">To verify that your /etc/opt/microsoft/mdatp/managed/mdatp_managed.json is working properly, you should see "[managed]" next to these settings:</span></span>  
- <span data-ttu-id="c6caf-392">cloud_enabled</span><span class="sxs-lookup"><span data-stu-id="c6caf-392">cloud_enabled</span></span>
- <span data-ttu-id="c6caf-393">cloud_automatic_sample_submission_consent</span><span class="sxs-lookup"><span data-stu-id="c6caf-393">cloud_automatic_sample_submission_consent</span></span>
- <span data-ttu-id="c6caf-394">passice_mode_enabled</span><span class="sxs-lookup"><span data-stu-id="c6caf-394">passice_mode_enabled</span></span>
- <span data-ttu-id="c6caf-395">real_time_protection_enabled</span><span class="sxs-lookup"><span data-stu-id="c6caf-395">real_time_protection_enabled</span></span>
- <span data-ttu-id="c6caf-396">automatic_definition_update_enabled</span><span class="sxs-lookup"><span data-stu-id="c6caf-396">automatic_definition_update_enabled</span></span>

> [!NOTE]
> <span data-ttu-id="c6caf-397">Per lmdatp_managed.jsè attivo, non è necessario riavviare il wdavdaemon.</span><span class="sxs-lookup"><span data-stu-id="c6caf-397">For the mdatp_managed.json to take effect, no restart of the wdavdaemon is required.</span></span>

## <a name="configuration-profile-deployment"></a><span data-ttu-id="c6caf-398">Distribuzione dei profili di configurazione</span><span class="sxs-lookup"><span data-stu-id="c6caf-398">Configuration profile deployment</span></span>

<span data-ttu-id="c6caf-399">Dopo aver creato il profilo di configurazione per l'organizzazione, è possibile distribuirlo tramite lo strumento di gestione utilizzato dall'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c6caf-399">Once you've built the configuration profile for your enterprise, you can deploy it through the management tool that your enterprise is using.</span></span> <span data-ttu-id="c6caf-400">Defender per Endpoint su Linux legge la configurazione gestita dal file */etc/opt/microsoft/mdatp/managed/mdatp_managed.json.*</span><span class="sxs-lookup"><span data-stu-id="c6caf-400">Defender for Endpoint on Linux reads the managed configuration from the */etc/opt/microsoft/mdatp/managed/mdatp_managed.json* file.</span></span>
