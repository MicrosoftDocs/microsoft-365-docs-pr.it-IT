---
title: Impostare le preferenze per Microsoft Defender per Endpoint su Mac
description: Configurare MMicrosoft Defender per Endpoint su Mac nelle organizzazioni aziendali.
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, gestione, preferenze, enterprise, intune, jamf, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: b706cb8dbd43d545768c1c573021b5ef401e3c09
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2021
ms.locfileid: "52346403"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="1dbfc-104">Impostare le preferenze per Microsoft Defender per Endpoint in macOS</span><span class="sxs-lookup"><span data-stu-id="1dbfc-104">Set preferences for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1dbfc-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-105">**Applies to:**</span></span>

- [<span data-ttu-id="1dbfc-106">Microsoft Defender per endpoint su macOS</span><span class="sxs-lookup"><span data-stu-id="1dbfc-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)

>[!IMPORTANT]
><span data-ttu-id="1dbfc-107">Questo articolo contiene istruzioni su come impostare le preferenze per Microsoft Defender per Endpoint in macOS nelle organizzazioni aziendali.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-107">This article contains instructions for how to set preferences for Microsoft Defender for Endpoint on macOS in enterprise organizations.</span></span> <span data-ttu-id="1dbfc-108">Per configurare Microsoft Defender per Endpoint in macOS tramite l'interfaccia della riga di comando, vedi [Risorse](mac-resources.md#configuring-from-the-command-line).</span><span class="sxs-lookup"><span data-stu-id="1dbfc-108">To configure Microsoft Defender for Endpoint on macOS using the command-line interface, see [Resources](mac-resources.md#configuring-from-the-command-line).</span></span>

## <a name="summary"></a><span data-ttu-id="1dbfc-109">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="1dbfc-109">Summary</span></span>

<span data-ttu-id="1dbfc-110">Nelle organizzazioni aziendali, Microsoft Defender for Endpoint in macOS può essere gestito tramite un profilo di configurazione distribuito utilizzando uno dei diversi strumenti di gestione.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-110">In enterprise organizations, Microsoft Defender for Endpoint on macOS can be managed through a configuration profile that is deployed by using one of several management tools.</span></span> <span data-ttu-id="1dbfc-111">Le preferenze gestite dal team delle operazioni di sicurezza hanno la precedenza sulle preferenze impostate localmente nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-111">Preferences that are managed by your security operations team take precedence over preferences that are set locally on the device.</span></span> <span data-ttu-id="1dbfc-112">La modifica delle preferenze impostate tramite il profilo di configurazione richiede privilegi inoltrati e non è disponibile per gli utenti senza autorizzazioni amministrative.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-112">Changing the preferences that are set through the configuration profile requires escalated privileges and is not available for users without administrative permissions.</span></span>

<span data-ttu-id="1dbfc-113">Questo articolo descrive la struttura del profilo di configurazione, include un profilo consigliato che puoi usare per iniziare e fornisce istruzioni su come distribuire il profilo.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-113">This article describes the structure of the configuration profile, includes a recommended profile that you can use to get started, and provides instructions on how to deploy the profile.</span></span>

## <a name="configuration-profile-structure"></a><span data-ttu-id="1dbfc-114">Struttura del profilo di configurazione</span><span class="sxs-lookup"><span data-stu-id="1dbfc-114">Configuration profile structure</span></span>

<span data-ttu-id="1dbfc-115">Il profilo di configurazione è un file *plist* costituito da voci identificate da una chiave (che indica il nome della preferenza), seguita da un valore, che dipende dalla natura della preferenza.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-115">The configuration profile is a *.plist* file that consists of entries identified by a key (which denotes the name of the preference), followed by a value, which depends on the nature of the preference.</span></span> <span data-ttu-id="1dbfc-116">I valori possono essere semplici (ad esempio un valore numerico) o complessi, ad esempio un elenco nidificato di preferenze.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-116">Values can either be simple (such as a numerical value) or complex, such as a nested list of preferences.</span></span>

>[!CAUTION]
><span data-ttu-id="1dbfc-117">Il layout del profilo di configurazione dipende dalla console di gestione in uso.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-117">The layout of the configuration profile depends on the management console that you are using.</span></span> <span data-ttu-id="1dbfc-118">Le sezioni seguenti contengono esempi di profili di configurazione per JAMF e Intune.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-118">The following sections contain examples of configuration profiles for JAMF and Intune.</span></span>

<span data-ttu-id="1dbfc-119">Il livello superiore del profilo di configurazione include le preferenze e le voci a livello di prodotto per le sottoaree di Microsoft Defender per Endpoint, che vengono illustrate in modo più dettagliato nelle sezioni successive.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-119">The top level of the configuration profile includes product-wide preferences and entries for subareas of Microsoft Defender for Endpoint, which are explained in more detail in the next sections.</span></span>

### <a name="antivirus-engine-preferences"></a><span data-ttu-id="1dbfc-120">Preferenze del motore antivirus</span><span class="sxs-lookup"><span data-stu-id="1dbfc-120">Antivirus engine preferences</span></span>

<span data-ttu-id="1dbfc-121">La *sezione antivirusEngine* del profilo di configurazione viene usata per gestire le preferenze del componente antivirus di Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-121">The *antivirusEngine* section of the configuration profile is used to manage the preferences of the antivirus component of Microsoft Defender for Endpoint.</span></span>

|<span data-ttu-id="1dbfc-122">Sezione</span><span class="sxs-lookup"><span data-stu-id="1dbfc-122">Section</span></span>|<span data-ttu-id="1dbfc-123">Valore</span><span class="sxs-lookup"><span data-stu-id="1dbfc-123">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1dbfc-124">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-124">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1dbfc-125">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-125">**Key**</span></span> | <span data-ttu-id="1dbfc-126">antivirusEngine</span><span class="sxs-lookup"><span data-stu-id="1dbfc-126">antivirusEngine</span></span> |
| <span data-ttu-id="1dbfc-127">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-127">**Data type**</span></span> | <span data-ttu-id="1dbfc-128">Dizionario (preferenza annidata)</span><span class="sxs-lookup"><span data-stu-id="1dbfc-128">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="1dbfc-129">**Comments**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-129">**Comments**</span></span> | <span data-ttu-id="1dbfc-130">Per una descrizione del contenuto del dizionario, vedi le sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-130">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-real-time-protection"></a><span data-ttu-id="1dbfc-131">Abilitare/disabilitare la protezione in tempo reale</span><span class="sxs-lookup"><span data-stu-id="1dbfc-131">Enable / disable real-time protection</span></span>

<span data-ttu-id="1dbfc-132">Specificare se abilitare la protezione in tempo reale, che analizza i file man a cui si accede.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-132">Specify whether to enable real-time protection, which scans files as they are accessed.</span></span>

|<span data-ttu-id="1dbfc-133">Sezione</span><span class="sxs-lookup"><span data-stu-id="1dbfc-133">Section</span></span>|<span data-ttu-id="1dbfc-134">Valore</span><span class="sxs-lookup"><span data-stu-id="1dbfc-134">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1dbfc-135">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-135">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1dbfc-136">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-136">**Key**</span></span> | <span data-ttu-id="1dbfc-137">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="1dbfc-137">enableRealTimeProtection</span></span> |
| <span data-ttu-id="1dbfc-138">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-138">**Data type**</span></span> | <span data-ttu-id="1dbfc-139">Booleano</span><span class="sxs-lookup"><span data-stu-id="1dbfc-139">Boolean</span></span> |
| <span data-ttu-id="1dbfc-140">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-140">**Possible values**</span></span> | <span data-ttu-id="1dbfc-141">true (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="1dbfc-141">true (default)</span></span> <br/> <span data-ttu-id="1dbfc-142">false</span><span class="sxs-lookup"><span data-stu-id="1dbfc-142">false</span></span> |

#### <a name="enable--disable-passive-mode"></a><span data-ttu-id="1dbfc-143">Abilitare/disabilitare la modalità passiva</span><span class="sxs-lookup"><span data-stu-id="1dbfc-143">Enable / disable passive mode</span></span>

<span data-ttu-id="1dbfc-144">Specificare se il motore antivirus viene eseguito in modalità passiva.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-144">Specify whether the antivirus engine runs in passive mode.</span></span> <span data-ttu-id="1dbfc-145">La modalità passiva ha le implicazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1dbfc-145">Passive mode has the following implications:</span></span> 
- <span data-ttu-id="1dbfc-146">La protezione in tempo reale è disattivata</span><span class="sxs-lookup"><span data-stu-id="1dbfc-146">Real-time protection is turned off</span></span>
- <span data-ttu-id="1dbfc-147">L'analisi su richiesta è attivata</span><span class="sxs-lookup"><span data-stu-id="1dbfc-147">On-demand scanning is turned on</span></span>
- <span data-ttu-id="1dbfc-148">La correzione automatica delle minacce è disattivata</span><span class="sxs-lookup"><span data-stu-id="1dbfc-148">Automatic threat remediation is turned off</span></span>
- <span data-ttu-id="1dbfc-149">Gli aggiornamenti delle funzionalità di intelligence per la sicurezza sono attivati</span><span class="sxs-lookup"><span data-stu-id="1dbfc-149">Security intelligence updates are turned on</span></span>
- <span data-ttu-id="1dbfc-150">L'icona del menu Stato è nascosta</span><span class="sxs-lookup"><span data-stu-id="1dbfc-150">Status menu icon is hidden</span></span>

|<span data-ttu-id="1dbfc-151">Sezione</span><span class="sxs-lookup"><span data-stu-id="1dbfc-151">Section</span></span>|<span data-ttu-id="1dbfc-152">Valore</span><span class="sxs-lookup"><span data-stu-id="1dbfc-152">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1dbfc-153">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-153">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1dbfc-154">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-154">**Key**</span></span> | <span data-ttu-id="1dbfc-155">passiveMode</span><span class="sxs-lookup"><span data-stu-id="1dbfc-155">passiveMode</span></span> |
| <span data-ttu-id="1dbfc-156">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-156">**Data type**</span></span> | <span data-ttu-id="1dbfc-157">Booleano</span><span class="sxs-lookup"><span data-stu-id="1dbfc-157">Boolean</span></span> |
| <span data-ttu-id="1dbfc-158">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-158">**Possible values**</span></span> | <span data-ttu-id="1dbfc-159">false (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="1dbfc-159">false (default)</span></span> <br/> <span data-ttu-id="1dbfc-160">true</span><span class="sxs-lookup"><span data-stu-id="1dbfc-160">true</span></span> |
| <span data-ttu-id="1dbfc-161">**Comments**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-161">**Comments**</span></span> | <span data-ttu-id="1dbfc-162">Disponibile in Microsoft Defender per Endpoint versione 100.67.60 o successiva.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-162">Available in Microsoft Defender for Endpoint version 100.67.60 or higher.</span></span> |

#### <a name="exclusion-merge-policy"></a><span data-ttu-id="1dbfc-163">Criteri di unione esclusioni</span><span class="sxs-lookup"><span data-stu-id="1dbfc-163">Exclusion merge policy</span></span>

<span data-ttu-id="1dbfc-164">Specificare i criteri di unione per le esclusioni.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-164">Specify the merge policy for exclusions.</span></span> <span data-ttu-id="1dbfc-165">Può trattarsi di una combinazione di esclusioni definite dall'amministratore e definite dall'utente ( ) o solo di esclusioni definite `merge` dall'amministratore ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="1dbfc-165">This can be a combination of administrator-defined and user-defined exclusions (`merge`) or only administrator-defined exclusions (`admin_only`).</span></span> <span data-ttu-id="1dbfc-166">Questa impostazione può essere utilizzata per impedire agli utenti locali di definire le proprie esclusioni.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-166">This setting can be used to restrict local users from defining their own exclusions.</span></span>

|<span data-ttu-id="1dbfc-167">Sezione</span><span class="sxs-lookup"><span data-stu-id="1dbfc-167">Section</span></span>|<span data-ttu-id="1dbfc-168">Valore</span><span class="sxs-lookup"><span data-stu-id="1dbfc-168">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1dbfc-169">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-169">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1dbfc-170">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-170">**Key**</span></span> | <span data-ttu-id="1dbfc-171">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="1dbfc-171">exclusionsMergePolicy</span></span> |
| <span data-ttu-id="1dbfc-172">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-172">**Data type**</span></span> | <span data-ttu-id="1dbfc-173">Stringa</span><span class="sxs-lookup"><span data-stu-id="1dbfc-173">String</span></span> |
| <span data-ttu-id="1dbfc-174">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-174">**Possible values**</span></span> | <span data-ttu-id="1dbfc-175">merge (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="1dbfc-175">merge (default)</span></span> <br/> <span data-ttu-id="1dbfc-176">admin_only</span><span class="sxs-lookup"><span data-stu-id="1dbfc-176">admin_only</span></span> |
| <span data-ttu-id="1dbfc-177">**Comments**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-177">**Comments**</span></span> | <span data-ttu-id="1dbfc-178">Disponibile in Microsoft Defender per Endpoint versione 100.83.73 o successiva.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-178">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="scan-exclusions"></a><span data-ttu-id="1dbfc-179">Esclusioni analisi</span><span class="sxs-lookup"><span data-stu-id="1dbfc-179">Scan exclusions</span></span>

<span data-ttu-id="1dbfc-180">Specificare le entità escluse dall'analisi.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-180">Specify entities excluded from being scanned.</span></span> <span data-ttu-id="1dbfc-181">Le esclusioni possono essere specificate da percorsi completi, estensioni o nomi di file.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-181">Exclusions can be specified by full paths, extensions, or file names.</span></span>
<span data-ttu-id="1dbfc-182">Le esclusioni vengono specificate come matrice di elementi, l'amministratore può specificare il numero di elementi necessario, in qualsiasi ordine.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-182">(Exclusions are specified as an array of items, administrator can specify as many elements as necessary, in any order.)</span></span>

|<span data-ttu-id="1dbfc-183">Sezione</span><span class="sxs-lookup"><span data-stu-id="1dbfc-183">Section</span></span>|<span data-ttu-id="1dbfc-184">Valore</span><span class="sxs-lookup"><span data-stu-id="1dbfc-184">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1dbfc-185">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-185">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1dbfc-186">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-186">**Key**</span></span> | <span data-ttu-id="1dbfc-187">esclusioni</span><span class="sxs-lookup"><span data-stu-id="1dbfc-187">exclusions</span></span> |
| <span data-ttu-id="1dbfc-188">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-188">**Data type**</span></span> | <span data-ttu-id="1dbfc-189">Dizionario (preferenza annidata)</span><span class="sxs-lookup"><span data-stu-id="1dbfc-189">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="1dbfc-190">**Comments**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-190">**Comments**</span></span> | <span data-ttu-id="1dbfc-191">Per una descrizione del contenuto del dizionario, vedi le sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-191">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="type-of-exclusion"></a><span data-ttu-id="1dbfc-192">Tipo di esclusione</span><span class="sxs-lookup"><span data-stu-id="1dbfc-192">Type of exclusion</span></span>

<span data-ttu-id="1dbfc-193">Specificare il contenuto escluso dall'analisi in base al tipo.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-193">Specify content excluded from being scanned by type.</span></span>

|<span data-ttu-id="1dbfc-194">Sezione</span><span class="sxs-lookup"><span data-stu-id="1dbfc-194">Section</span></span>|<span data-ttu-id="1dbfc-195">Valore</span><span class="sxs-lookup"><span data-stu-id="1dbfc-195">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1dbfc-196">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-196">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1dbfc-197">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-197">**Key**</span></span> | <span data-ttu-id="1dbfc-198">$type</span><span class="sxs-lookup"><span data-stu-id="1dbfc-198">$type</span></span> |
| <span data-ttu-id="1dbfc-199">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-199">**Data type**</span></span> | <span data-ttu-id="1dbfc-200">Stringa</span><span class="sxs-lookup"><span data-stu-id="1dbfc-200">String</span></span> |
| <span data-ttu-id="1dbfc-201">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-201">**Possible values**</span></span> | <span data-ttu-id="1dbfc-202">excludedPath</span><span class="sxs-lookup"><span data-stu-id="1dbfc-202">excludedPath</span></span> <br/> <span data-ttu-id="1dbfc-203">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="1dbfc-203">excludedFileExtension</span></span> <br/> <span data-ttu-id="1dbfc-204">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="1dbfc-204">excludedFileName</span></span> |

##### <a name="path-to-excluded-content"></a><span data-ttu-id="1dbfc-205">Percorso del contenuto escluso</span><span class="sxs-lookup"><span data-stu-id="1dbfc-205">Path to excluded content</span></span>

<span data-ttu-id="1dbfc-206">Specificare il contenuto escluso dall'analisi tramite il percorso completo del file.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-206">Specify content excluded from being scanned by full file path.</span></span>

|<span data-ttu-id="1dbfc-207">Sezione</span><span class="sxs-lookup"><span data-stu-id="1dbfc-207">Section</span></span>|<span data-ttu-id="1dbfc-208">Valore</span><span class="sxs-lookup"><span data-stu-id="1dbfc-208">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1dbfc-209">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-209">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1dbfc-210">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-210">**Key**</span></span> | <span data-ttu-id="1dbfc-211">path</span><span class="sxs-lookup"><span data-stu-id="1dbfc-211">path</span></span> |
| <span data-ttu-id="1dbfc-212">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-212">**Data type**</span></span> | <span data-ttu-id="1dbfc-213">Stringa</span><span class="sxs-lookup"><span data-stu-id="1dbfc-213">String</span></span> |
| <span data-ttu-id="1dbfc-214">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-214">**Possible values**</span></span> | <span data-ttu-id="1dbfc-215">percorsi validi</span><span class="sxs-lookup"><span data-stu-id="1dbfc-215">valid paths</span></span> |
| <span data-ttu-id="1dbfc-216">**Comments**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-216">**Comments**</span></span> | <span data-ttu-id="1dbfc-217">Applicabile solo se *$type* *è excludedPath*</span><span class="sxs-lookup"><span data-stu-id="1dbfc-217">Applicable only if *$type* is *excludedPath*</span></span> |

## <a name="supported-exclusion-types"></a><span data-ttu-id="1dbfc-218">Tipi di esclusione supportati</span><span class="sxs-lookup"><span data-stu-id="1dbfc-218">Supported exclusion types</span></span>

<span data-ttu-id="1dbfc-219">La tabella seguente mostra i tipi di esclusione supportati da Defender per Endpoint su Mac.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-219">The follow table shows the exclusion types supported by Defender for Endpoint on Mac.</span></span>

<span data-ttu-id="1dbfc-220">Esclusione</span><span class="sxs-lookup"><span data-stu-id="1dbfc-220">Exclusion</span></span> | <span data-ttu-id="1dbfc-221">Definizione</span><span class="sxs-lookup"><span data-stu-id="1dbfc-221">Definition</span></span> | <span data-ttu-id="1dbfc-222">Esempi</span><span class="sxs-lookup"><span data-stu-id="1dbfc-222">Examples</span></span>
---|---|---
<span data-ttu-id="1dbfc-223">Estensione del file</span><span class="sxs-lookup"><span data-stu-id="1dbfc-223">File extension</span></span> | <span data-ttu-id="1dbfc-224">Tutti i file con estensione, ovunque nel dispositivo</span><span class="sxs-lookup"><span data-stu-id="1dbfc-224">All files with the extension, anywhere on the device</span></span> | `.test`
<span data-ttu-id="1dbfc-225">File</span><span class="sxs-lookup"><span data-stu-id="1dbfc-225">File</span></span> | <span data-ttu-id="1dbfc-226">Un file specifico identificato dal percorso completo</span><span class="sxs-lookup"><span data-stu-id="1dbfc-226">A specific file identified by the full path</span></span> | `/var/log/test.log`<br/>`/var/log/*.log`<br/>`/var/log/install.?.log`
<span data-ttu-id="1dbfc-227">Cartella</span><span class="sxs-lookup"><span data-stu-id="1dbfc-227">Folder</span></span> | <span data-ttu-id="1dbfc-228">Tutti i file nella cartella specificata (in modo ricorsivo)</span><span class="sxs-lookup"><span data-stu-id="1dbfc-228">All files under the specified folder (recursively)</span></span> | `/var/log/`<br/>`/var/*/`
<span data-ttu-id="1dbfc-229">Processo</span><span class="sxs-lookup"><span data-stu-id="1dbfc-229">Process</span></span> | <span data-ttu-id="1dbfc-230">Un processo specifico (specificato dal percorso completo o dal nome del file) e tutti i file aperti da esso</span><span class="sxs-lookup"><span data-stu-id="1dbfc-230">A specific process (specified either by the full path or file name) and all files opened by it</span></span> | `/bin/cat`<br/>`cat`<br/>`c?t`

> [!IMPORTANT]
> <span data-ttu-id="1dbfc-231">I percorsi precedenti devono essere collegamenti rigidi, non collegamenti simbolici, per essere esclusi correttamente.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-231">The paths above must be hard links, not symbolic links, in order to be successfully excluded.</span></span> <span data-ttu-id="1dbfc-232">È possibile verificare se un percorso è un collegamento simbolico eseguendo `file <path-name>` .</span><span class="sxs-lookup"><span data-stu-id="1dbfc-232">You can check if a path is a symbolic link by running `file <path-name>`.</span></span>

<span data-ttu-id="1dbfc-233">Le esclusioni di file, cartelle e processi supportano i caratteri jolly seguenti:</span><span class="sxs-lookup"><span data-stu-id="1dbfc-233">File, folder, and process exclusions support the following wildcards:</span></span>

<span data-ttu-id="1dbfc-234">Carattere jolly</span><span class="sxs-lookup"><span data-stu-id="1dbfc-234">Wildcard</span></span> | <span data-ttu-id="1dbfc-235">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1dbfc-235">Description</span></span> | <span data-ttu-id="1dbfc-236">Esempio</span><span class="sxs-lookup"><span data-stu-id="1dbfc-236">Example</span></span> | <span data-ttu-id="1dbfc-237">Corrispondenze</span><span class="sxs-lookup"><span data-stu-id="1dbfc-237">Matches</span></span> | <span data-ttu-id="1dbfc-238">Non corrisponde</span><span class="sxs-lookup"><span data-stu-id="1dbfc-238">Does not match</span></span>
---|---|---|---|---
\* |    <span data-ttu-id="1dbfc-239">Corrisponde a qualsiasi numero di caratteri compresi nessuno (si noti che quando questo carattere jolly viene utilizzato all'interno di un percorso sostituirà una sola cartella)</span><span class="sxs-lookup"><span data-stu-id="1dbfc-239">Matches any number of any characters including none (note that when this wildcard is used inside a path it will substitute only one folder)</span></span> | `/var/\*/\*.log` | `/var/log/system.log` | `/var/log/nested/system.log`
<span data-ttu-id="1dbfc-240">?</span><span class="sxs-lookup"><span data-stu-id="1dbfc-240">?</span></span> | <span data-ttu-id="1dbfc-241">Corrisponde a qualsiasi carattere singolo</span><span class="sxs-lookup"><span data-stu-id="1dbfc-241">Matches any single character</span></span> | `file?.log` | `file1.log`<br/>`file2.log` | `file123.log`

##### <a name="path-type-file--directory"></a><span data-ttu-id="1dbfc-242">Tipo di percorso (file/directory)</span><span class="sxs-lookup"><span data-stu-id="1dbfc-242">Path type (file / directory)</span></span>

<span data-ttu-id="1dbfc-243">Indicare se la *proprietà path* fa riferimento a un file o a una directory.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-243">Indicate if the *path* property refers to a file or directory.</span></span> 

|<span data-ttu-id="1dbfc-244">Sezione</span><span class="sxs-lookup"><span data-stu-id="1dbfc-244">Section</span></span>|<span data-ttu-id="1dbfc-245">Valore</span><span class="sxs-lookup"><span data-stu-id="1dbfc-245">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1dbfc-246">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-246">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1dbfc-247">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-247">**Key**</span></span> | <span data-ttu-id="1dbfc-248">isDirectory</span><span class="sxs-lookup"><span data-stu-id="1dbfc-248">isDirectory</span></span> |
| <span data-ttu-id="1dbfc-249">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-249">**Data type**</span></span> | <span data-ttu-id="1dbfc-250">Booleano</span><span class="sxs-lookup"><span data-stu-id="1dbfc-250">Boolean</span></span> |
| <span data-ttu-id="1dbfc-251">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-251">**Possible values**</span></span> | <span data-ttu-id="1dbfc-252">false (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="1dbfc-252">false (default)</span></span> <br/> <span data-ttu-id="1dbfc-253">true</span><span class="sxs-lookup"><span data-stu-id="1dbfc-253">true</span></span> |
| <span data-ttu-id="1dbfc-254">**Comments**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-254">**Comments**</span></span> | <span data-ttu-id="1dbfc-255">Applicabile solo se *$type* *è excludedPath*</span><span class="sxs-lookup"><span data-stu-id="1dbfc-255">Applicable only if *$type* is *excludedPath*</span></span> |

##### <a name="file-extension-excluded-from-the-scan"></a><span data-ttu-id="1dbfc-256">Estensione di file esclusa dall'analisi</span><span class="sxs-lookup"><span data-stu-id="1dbfc-256">File extension excluded from the scan</span></span>

<span data-ttu-id="1dbfc-257">Specificare il contenuto escluso dall'analisi per estensione di file.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-257">Specify content excluded from being scanned by file extension.</span></span>

|<span data-ttu-id="1dbfc-258">Sezione</span><span class="sxs-lookup"><span data-stu-id="1dbfc-258">Section</span></span>|<span data-ttu-id="1dbfc-259">Valore</span><span class="sxs-lookup"><span data-stu-id="1dbfc-259">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1dbfc-260">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-260">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1dbfc-261">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-261">**Key**</span></span> | <span data-ttu-id="1dbfc-262">extension</span><span class="sxs-lookup"><span data-stu-id="1dbfc-262">extension</span></span> |
| <span data-ttu-id="1dbfc-263">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-263">**Data type**</span></span> | <span data-ttu-id="1dbfc-264">Stringa</span><span class="sxs-lookup"><span data-stu-id="1dbfc-264">String</span></span> |
| <span data-ttu-id="1dbfc-265">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-265">**Possible values**</span></span> | <span data-ttu-id="1dbfc-266">estensioni di file valide</span><span class="sxs-lookup"><span data-stu-id="1dbfc-266">valid file extensions</span></span> |
| <span data-ttu-id="1dbfc-267">**Comments**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-267">**Comments**</span></span> | <span data-ttu-id="1dbfc-268">Applicabile solo se *$type* *è excludedFileExtension*</span><span class="sxs-lookup"><span data-stu-id="1dbfc-268">Applicable only if *$type* is *excludedFileExtension*</span></span> |

##### <a name="process-excluded-from-the-scan"></a><span data-ttu-id="1dbfc-269">Processo escluso dall'analisi</span><span class="sxs-lookup"><span data-stu-id="1dbfc-269">Process excluded from the scan</span></span>

<span data-ttu-id="1dbfc-270">Specificare un processo per il quale tutte le attività dei file vengono escluse dall'analisi.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-270">Specify a process for which all file activity is excluded from scanning.</span></span> <span data-ttu-id="1dbfc-271">Il processo può essere specificato in base al nome (ad esempio) o al `cat` percorso completo (ad `/bin/cat` esempio).</span><span class="sxs-lookup"><span data-stu-id="1dbfc-271">The process can be specified either by its name (e.g. `cat`) or full path (e.g. `/bin/cat`).</span></span>

|<span data-ttu-id="1dbfc-272">Sezione</span><span class="sxs-lookup"><span data-stu-id="1dbfc-272">Section</span></span>|<span data-ttu-id="1dbfc-273">Valore</span><span class="sxs-lookup"><span data-stu-id="1dbfc-273">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1dbfc-274">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-274">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1dbfc-275">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-275">**Key**</span></span> | <span data-ttu-id="1dbfc-276">name</span><span class="sxs-lookup"><span data-stu-id="1dbfc-276">name</span></span> |
| <span data-ttu-id="1dbfc-277">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-277">**Data type**</span></span> | <span data-ttu-id="1dbfc-278">Stringa</span><span class="sxs-lookup"><span data-stu-id="1dbfc-278">String</span></span> |
| <span data-ttu-id="1dbfc-279">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-279">**Possible values**</span></span> | <span data-ttu-id="1dbfc-280">qualsiasi stringa</span><span class="sxs-lookup"><span data-stu-id="1dbfc-280">any string</span></span> |
| <span data-ttu-id="1dbfc-281">**Comments**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-281">**Comments**</span></span> | <span data-ttu-id="1dbfc-282">Applicabile solo se *$type* *è excludedFileName*</span><span class="sxs-lookup"><span data-stu-id="1dbfc-282">Applicable only if *$type* is *excludedFileName*</span></span> |

#### <a name="allowed-threats"></a><span data-ttu-id="1dbfc-283">Minacce consentite</span><span class="sxs-lookup"><span data-stu-id="1dbfc-283">Allowed threats</span></span>

<span data-ttu-id="1dbfc-284">Specifica le minacce in base al nome che non sono bloccate da Defender per Endpoint su Mac.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-284">Specify threats by name that are not blocked by Defender for Endpoint on Mac.</span></span> <span data-ttu-id="1dbfc-285">L'esecuzione di queste minacce sarà consentita.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-285">These threats will be allowed to run.</span></span>

|<span data-ttu-id="1dbfc-286">Sezione</span><span class="sxs-lookup"><span data-stu-id="1dbfc-286">Section</span></span>|<span data-ttu-id="1dbfc-287">Valore</span><span class="sxs-lookup"><span data-stu-id="1dbfc-287">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1dbfc-288">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-288">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1dbfc-289">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-289">**Key**</span></span> | <span data-ttu-id="1dbfc-290">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="1dbfc-290">allowedThreats</span></span> |
| <span data-ttu-id="1dbfc-291">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-291">**Data type**</span></span> | <span data-ttu-id="1dbfc-292">Matrice di stringhe</span><span class="sxs-lookup"><span data-stu-id="1dbfc-292">Array of strings</span></span> |

#### <a name="disallowed-threat-actions"></a><span data-ttu-id="1dbfc-293">Azioni di minaccia non consentite</span><span class="sxs-lookup"><span data-stu-id="1dbfc-293">Disallowed threat actions</span></span>

<span data-ttu-id="1dbfc-294">Limita le azioni che l'utente locale di un dispositivo può intraprendere quando vengono rilevate minacce.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-294">Restricts the actions that the local user of a device can take when threats are detected.</span></span> <span data-ttu-id="1dbfc-295">Le azioni incluse in questo elenco non vengono visualizzate nell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-295">The actions included in this list are not displayed in the user interface.</span></span>

|<span data-ttu-id="1dbfc-296">Sezione</span><span class="sxs-lookup"><span data-stu-id="1dbfc-296">Section</span></span>|<span data-ttu-id="1dbfc-297">Valore</span><span class="sxs-lookup"><span data-stu-id="1dbfc-297">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1dbfc-298">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-298">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1dbfc-299">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-299">**Key**</span></span> | <span data-ttu-id="1dbfc-300">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="1dbfc-300">disallowedThreatActions</span></span> |
| <span data-ttu-id="1dbfc-301">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-301">**Data type**</span></span> | <span data-ttu-id="1dbfc-302">Matrice di stringhe</span><span class="sxs-lookup"><span data-stu-id="1dbfc-302">Array of strings</span></span> |
| <span data-ttu-id="1dbfc-303">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-303">**Possible values**</span></span> | <span data-ttu-id="1dbfc-304">allow (impedisce agli utenti di consentire minacce)</span><span class="sxs-lookup"><span data-stu-id="1dbfc-304">allow (restricts users from allowing threats)</span></span> <br/> <span data-ttu-id="1dbfc-305">restore (impedisce agli utenti di ripristinare le minacce dalla quarantena)</span><span class="sxs-lookup"><span data-stu-id="1dbfc-305">restore (restricts users from restoring threats from the quarantine)</span></span> |
| <span data-ttu-id="1dbfc-306">**Comments**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-306">**Comments**</span></span> | <span data-ttu-id="1dbfc-307">Disponibile in Microsoft Defender per Endpoint versione 100.83.73 o successiva.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-307">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="threat-type-settings"></a><span data-ttu-id="1dbfc-308">Impostazioni del tipo di minaccia</span><span class="sxs-lookup"><span data-stu-id="1dbfc-308">Threat type settings</span></span>

<span data-ttu-id="1dbfc-309">Specifica come vengono gestiti determinati tipi di minacce da Microsoft Defender per Endpoint in macOS.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-309">Specify how certain threat types are handled by Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="1dbfc-310">Sezione</span><span class="sxs-lookup"><span data-stu-id="1dbfc-310">Section</span></span>|<span data-ttu-id="1dbfc-311">Valore</span><span class="sxs-lookup"><span data-stu-id="1dbfc-311">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1dbfc-312">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-312">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1dbfc-313">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-313">**Key**</span></span> | <span data-ttu-id="1dbfc-314">threatTypeSettings</span><span class="sxs-lookup"><span data-stu-id="1dbfc-314">threatTypeSettings</span></span> |
| <span data-ttu-id="1dbfc-315">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-315">**Data type**</span></span> | <span data-ttu-id="1dbfc-316">Dizionario (preferenza annidata)</span><span class="sxs-lookup"><span data-stu-id="1dbfc-316">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="1dbfc-317">**Comments**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-317">**Comments**</span></span> | <span data-ttu-id="1dbfc-318">Per una descrizione del contenuto del dizionario, vedi le sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-318">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="threat-type"></a><span data-ttu-id="1dbfc-319">Tipo di minaccia</span><span class="sxs-lookup"><span data-stu-id="1dbfc-319">Threat type</span></span>

<span data-ttu-id="1dbfc-320">Specificare i tipi di minaccia.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-320">Specify threat types.</span></span>

|<span data-ttu-id="1dbfc-321">Sezione</span><span class="sxs-lookup"><span data-stu-id="1dbfc-321">Section</span></span>|<span data-ttu-id="1dbfc-322">Valore</span><span class="sxs-lookup"><span data-stu-id="1dbfc-322">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1dbfc-323">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-323">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1dbfc-324">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-324">**Key**</span></span> | <span data-ttu-id="1dbfc-325">chiave</span><span class="sxs-lookup"><span data-stu-id="1dbfc-325">key</span></span> |
| <span data-ttu-id="1dbfc-326">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-326">**Data type**</span></span> | <span data-ttu-id="1dbfc-327">Stringa</span><span class="sxs-lookup"><span data-stu-id="1dbfc-327">String</span></span> |
| <span data-ttu-id="1dbfc-328">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-328">**Possible values**</span></span> | <span data-ttu-id="1dbfc-329">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="1dbfc-329">potentially_unwanted_application</span></span> <br/> <span data-ttu-id="1dbfc-330">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="1dbfc-330">archive_bomb</span></span> |

##### <a name="action-to-take"></a><span data-ttu-id="1dbfc-331">Procedura da seguire</span><span class="sxs-lookup"><span data-stu-id="1dbfc-331">Action to take</span></span>

<span data-ttu-id="1dbfc-332">Specificare l'azione da eseguire quando viene rilevata una minaccia del tipo specificato nella sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-332">Specify what action to take when a threat of the type specified in the preceding section is detected.</span></span> <span data-ttu-id="1dbfc-333">Scegliere una delle seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="1dbfc-333">Choose from the following options:</span></span>

- <span data-ttu-id="1dbfc-334">**Controllo**: il dispositivo non è protetto da questo tipo di minaccia, ma viene registrata una voce relativa alla minaccia.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-334">**Audit**: your device is not protected against this type of threat, but an entry about the threat is logged.</span></span>
- <span data-ttu-id="1dbfc-335">**Blocca**: il dispositivo è protetto da questo tipo di minaccia e si viene informati nell'interfaccia utente e nella console di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-335">**Block**: your device is protected against this type of threat and you are notified in the user interface and the security console.</span></span>
- <span data-ttu-id="1dbfc-336">**Disattivato:** il dispositivo non è protetto da questo tipo di minaccia e non viene registrato nulla.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-336">**Off**: your device is not protected against this type of threat and nothing is logged.</span></span>

|<span data-ttu-id="1dbfc-337">Sezione</span><span class="sxs-lookup"><span data-stu-id="1dbfc-337">Section</span></span>|<span data-ttu-id="1dbfc-338">Valore</span><span class="sxs-lookup"><span data-stu-id="1dbfc-338">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1dbfc-339">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-339">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1dbfc-340">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-340">**Key**</span></span> | <span data-ttu-id="1dbfc-341">valore</span><span class="sxs-lookup"><span data-stu-id="1dbfc-341">value</span></span> |
| <span data-ttu-id="1dbfc-342">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-342">**Data type**</span></span> | <span data-ttu-id="1dbfc-343">Stringa</span><span class="sxs-lookup"><span data-stu-id="1dbfc-343">String</span></span> |
| <span data-ttu-id="1dbfc-344">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-344">**Possible values**</span></span> | <span data-ttu-id="1dbfc-345">audit (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="1dbfc-345">audit (default)</span></span> <br/> <span data-ttu-id="1dbfc-346">blocco</span><span class="sxs-lookup"><span data-stu-id="1dbfc-346">block</span></span> <br/> <span data-ttu-id="1dbfc-347">off</span><span class="sxs-lookup"><span data-stu-id="1dbfc-347">off</span></span> |

#### <a name="threat-type-settings-merge-policy"></a><span data-ttu-id="1dbfc-348">Criteri di unione delle impostazioni del tipo di minaccia</span><span class="sxs-lookup"><span data-stu-id="1dbfc-348">Threat type settings merge policy</span></span>

<span data-ttu-id="1dbfc-349">Specificare i criteri di unione per le impostazioni del tipo di minaccia.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-349">Specify the merge policy for threat type settings.</span></span> <span data-ttu-id="1dbfc-350">Può essere una combinazione di impostazioni definite dall'amministratore e definite dall'utente ( ) o solo impostazioni definite `merge` dall'amministratore ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="1dbfc-350">This can be a combination of administrator-defined and user-defined settings (`merge`) or only administrator-defined settings (`admin_only`).</span></span> <span data-ttu-id="1dbfc-351">Questa impostazione può essere usata per impedire agli utenti locali di definire le proprie impostazioni per diversi tipi di minacce.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-351">This setting can be used to restrict local users from defining their own settings for different threat types.</span></span>

|<span data-ttu-id="1dbfc-352">Sezione</span><span class="sxs-lookup"><span data-stu-id="1dbfc-352">Section</span></span>|<span data-ttu-id="1dbfc-353">Valore</span><span class="sxs-lookup"><span data-stu-id="1dbfc-353">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1dbfc-354">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-354">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1dbfc-355">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-355">**Key**</span></span> | <span data-ttu-id="1dbfc-356">threatTypeSettingsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="1dbfc-356">threatTypeSettingsMergePolicy</span></span> |
| <span data-ttu-id="1dbfc-357">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-357">**Data type**</span></span> | <span data-ttu-id="1dbfc-358">Stringa</span><span class="sxs-lookup"><span data-stu-id="1dbfc-358">String</span></span> |
| <span data-ttu-id="1dbfc-359">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-359">**Possible values**</span></span> | <span data-ttu-id="1dbfc-360">merge (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="1dbfc-360">merge (default)</span></span> <br/> <span data-ttu-id="1dbfc-361">admin_only</span><span class="sxs-lookup"><span data-stu-id="1dbfc-361">admin_only</span></span> |
| <span data-ttu-id="1dbfc-362">**Comments**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-362">**Comments**</span></span> | <span data-ttu-id="1dbfc-363">Disponibile in Microsoft Defender per Endpoint versione 100.83.73 o successiva.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-363">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="antivirus-scan-history-retention-in-days"></a><span data-ttu-id="1dbfc-364">Conservazione cronologia analisi antivirus (in giorni)</span><span class="sxs-lookup"><span data-stu-id="1dbfc-364">Antivirus scan history retention (in days)</span></span>

<span data-ttu-id="1dbfc-365">Specifica il numero di giorni in cui i risultati vengono conservati nella cronologia dell'analisi nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-365">Specify the number of days that results are retained in the scan history on the device.</span></span> <span data-ttu-id="1dbfc-366">I risultati dell'analisi precedente vengono rimossi dalla cronologia.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-366">Old scan results are removed from the history.</span></span> <span data-ttu-id="1dbfc-367">Vecchi file in quarantena che vengono rimossi anche dal disco.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-367">Old quarantined files that are also removed from the disk.</span></span>

|<span data-ttu-id="1dbfc-368">Sezione</span><span class="sxs-lookup"><span data-stu-id="1dbfc-368">Section</span></span>|<span data-ttu-id="1dbfc-369">Valore</span><span class="sxs-lookup"><span data-stu-id="1dbfc-369">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1dbfc-370">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-370">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1dbfc-371">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-371">**Key**</span></span> | <span data-ttu-id="1dbfc-372">scanResultsRetentionDays</span><span class="sxs-lookup"><span data-stu-id="1dbfc-372">scanResultsRetentionDays</span></span> |
| <span data-ttu-id="1dbfc-373">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-373">**Data type**</span></span> | <span data-ttu-id="1dbfc-374">Stringa</span><span class="sxs-lookup"><span data-stu-id="1dbfc-374">String</span></span> |
| <span data-ttu-id="1dbfc-375">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-375">**Possible values**</span></span> | <span data-ttu-id="1dbfc-376">90 (impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="1dbfc-376">90 (default).</span></span> <span data-ttu-id="1dbfc-377">I valori consentiti sono da 1 giorno a 180 giorni.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-377">Allowed values are from 1 day to 180 days.</span></span> |
| <span data-ttu-id="1dbfc-378">**Comments**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-378">**Comments**</span></span> | <span data-ttu-id="1dbfc-379">Disponibile in Microsoft Defender per Endpoint versione 101.07.23 o successiva.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-379">Available in Microsoft Defender for Endpoint version 101.07.23 or higher.</span></span> |

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a><span data-ttu-id="1dbfc-380">Numero massimo di elementi nella cronologia dell'analisi antivirus</span><span class="sxs-lookup"><span data-stu-id="1dbfc-380">Maximum number of items in the antivirus scan history</span></span>

<span data-ttu-id="1dbfc-381">Specificare il numero massimo di voci da mantenere nella cronologia di analisi.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-381">Specify the maximum number of entries to keep in the scan history.</span></span> <span data-ttu-id="1dbfc-382">Le voci includono tutte le analisi su richiesta eseguite in passato e tutti i rilevamenti antivirus.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-382">Entries include all on-demand scans performed in the past and all antivirus detections.</span></span>

|<span data-ttu-id="1dbfc-383">Sezione</span><span class="sxs-lookup"><span data-stu-id="1dbfc-383">Section</span></span>|<span data-ttu-id="1dbfc-384">Valore</span><span class="sxs-lookup"><span data-stu-id="1dbfc-384">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1dbfc-385">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-385">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1dbfc-386">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-386">**Key**</span></span> | <span data-ttu-id="1dbfc-387">scanHistoryMaximumItems</span><span class="sxs-lookup"><span data-stu-id="1dbfc-387">scanHistoryMaximumItems</span></span> |
| <span data-ttu-id="1dbfc-388">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-388">**Data type**</span></span> | <span data-ttu-id="1dbfc-389">Stringa</span><span class="sxs-lookup"><span data-stu-id="1dbfc-389">String</span></span> |
| <span data-ttu-id="1dbfc-390">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-390">**Possible values**</span></span> | <span data-ttu-id="1dbfc-391">10000 (impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="1dbfc-391">10000 (default).</span></span> <span data-ttu-id="1dbfc-392">I valori consentiti sono da 5.000 elementi a 15.000 elementi.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-392">Allowed values are from 5000 items to 15000 items.</span></span> |
| <span data-ttu-id="1dbfc-393">**Comments**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-393">**Comments**</span></span> | <span data-ttu-id="1dbfc-394">Disponibile in Microsoft Defender per Endpoint versione 101.07.23 o successiva.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-394">Available in Microsoft Defender for Endpoint version 101.07.23 or higher.</span></span> |

### <a name="cloud-delivered-protection-preferences"></a><span data-ttu-id="1dbfc-395">Preferenze di protezione per il cloud</span><span class="sxs-lookup"><span data-stu-id="1dbfc-395">Cloud-delivered protection preferences</span></span>

<span data-ttu-id="1dbfc-396">Configurare le funzionalità di protezione basata sul cloud di Microsoft Defender per Endpoint in macOS.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-396">Configure the cloud-driven protection features of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="1dbfc-397">Sezione</span><span class="sxs-lookup"><span data-stu-id="1dbfc-397">Section</span></span>|<span data-ttu-id="1dbfc-398">Valore</span><span class="sxs-lookup"><span data-stu-id="1dbfc-398">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1dbfc-399">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-399">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1dbfc-400">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-400">**Key**</span></span> | <span data-ttu-id="1dbfc-401">cloudService</span><span class="sxs-lookup"><span data-stu-id="1dbfc-401">cloudService</span></span> |
| <span data-ttu-id="1dbfc-402">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-402">**Data type**</span></span> | <span data-ttu-id="1dbfc-403">Dizionario (preferenza annidata)</span><span class="sxs-lookup"><span data-stu-id="1dbfc-403">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="1dbfc-404">**Comments**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-404">**Comments**</span></span> | <span data-ttu-id="1dbfc-405">Per una descrizione del contenuto del dizionario, vedi le sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-405">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-cloud-delivered-protection"></a><span data-ttu-id="1dbfc-406">Abilitare/disabilitare la protezione recapitata nel cloud</span><span class="sxs-lookup"><span data-stu-id="1dbfc-406">Enable / disable cloud-delivered protection</span></span>

<span data-ttu-id="1dbfc-407">Specificare se abilitare o meno la protezione recapitata nel cloud.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-407">Specify whether to enable cloud-delivered protection the device or not.</span></span> <span data-ttu-id="1dbfc-408">Per migliorare la sicurezza dei servizi, è consigliabile mantenere attivata questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-408">To improve the security of your services, we recommend keeping this feature turned on.</span></span>

|<span data-ttu-id="1dbfc-409">Sezione</span><span class="sxs-lookup"><span data-stu-id="1dbfc-409">Section</span></span>|<span data-ttu-id="1dbfc-410">Valore</span><span class="sxs-lookup"><span data-stu-id="1dbfc-410">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1dbfc-411">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-411">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1dbfc-412">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-412">**Key**</span></span> | <span data-ttu-id="1dbfc-413">abilitati</span><span class="sxs-lookup"><span data-stu-id="1dbfc-413">enabled</span></span> |
| <span data-ttu-id="1dbfc-414">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-414">**Data type**</span></span> | <span data-ttu-id="1dbfc-415">Booleano</span><span class="sxs-lookup"><span data-stu-id="1dbfc-415">Boolean</span></span> |
| <span data-ttu-id="1dbfc-416">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-416">**Possible values**</span></span> | <span data-ttu-id="1dbfc-417">true (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="1dbfc-417">true (default)</span></span> <br/> <span data-ttu-id="1dbfc-418">false</span><span class="sxs-lookup"><span data-stu-id="1dbfc-418">false</span></span> |

#### <a name="diagnostic-collection-level"></a><span data-ttu-id="1dbfc-419">Livello raccolta diagnostica</span><span class="sxs-lookup"><span data-stu-id="1dbfc-419">Diagnostic collection level</span></span>

<span data-ttu-id="1dbfc-420">I dati di diagnostica vengono usati per mantenere Microsoft Defender for Endpoint sicuro e aggiornato, rilevare, diagnosticare e risolvere i problemi e apportare miglioramenti al prodotto.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-420">Diagnostic data is used to keep Microsoft Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span> <span data-ttu-id="1dbfc-421">Questa impostazione determina il livello di diagnostica inviato da Microsoft Defender per Endpoint a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-421">This setting determines the level of diagnostics sent by Microsoft Defender for Endpoint to Microsoft.</span></span>

|<span data-ttu-id="1dbfc-422">Sezione</span><span class="sxs-lookup"><span data-stu-id="1dbfc-422">Section</span></span>|<span data-ttu-id="1dbfc-423">Valore</span><span class="sxs-lookup"><span data-stu-id="1dbfc-423">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1dbfc-424">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-424">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1dbfc-425">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-425">**Key**</span></span> | <span data-ttu-id="1dbfc-426">diagnosticLevel</span><span class="sxs-lookup"><span data-stu-id="1dbfc-426">diagnosticLevel</span></span> |
| <span data-ttu-id="1dbfc-427">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-427">**Data type**</span></span> | <span data-ttu-id="1dbfc-428">Stringa</span><span class="sxs-lookup"><span data-stu-id="1dbfc-428">String</span></span> |
| <span data-ttu-id="1dbfc-429">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-429">**Possible values**</span></span> | <span data-ttu-id="1dbfc-430">facoltativo (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="1dbfc-430">optional (default)</span></span> <br/> <span data-ttu-id="1dbfc-431">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="1dbfc-431">required</span></span> |

#### <a name="enable--disable-automatic-sample-submissions"></a><span data-ttu-id="1dbfc-432">Abilitare/disabilitare gli invii di esempio automatici</span><span class="sxs-lookup"><span data-stu-id="1dbfc-432">Enable / disable automatic sample submissions</span></span>

<span data-ttu-id="1dbfc-433">Determina se i campioni sospetti (che potrebbero contenere minacce) vengono inviati a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-433">Determines whether suspicious samples (that are likely to contain threats) are sent to Microsoft.</span></span> <span data-ttu-id="1dbfc-434">Viene richiesto se è probabile che il file inviato contenga informazioni personali.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-434">You are prompted if the submitted file is likely to contain personal information.</span></span>

|<span data-ttu-id="1dbfc-435">Sezione</span><span class="sxs-lookup"><span data-stu-id="1dbfc-435">Section</span></span>|<span data-ttu-id="1dbfc-436">Valore</span><span class="sxs-lookup"><span data-stu-id="1dbfc-436">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1dbfc-437">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-437">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1dbfc-438">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-438">**Key**</span></span> | <span data-ttu-id="1dbfc-439">automaticSampleSubmission</span><span class="sxs-lookup"><span data-stu-id="1dbfc-439">automaticSampleSubmission</span></span> |
| <span data-ttu-id="1dbfc-440">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-440">**Data type**</span></span> | <span data-ttu-id="1dbfc-441">Booleano</span><span class="sxs-lookup"><span data-stu-id="1dbfc-441">Boolean</span></span> |
| <span data-ttu-id="1dbfc-442">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-442">**Possible values**</span></span> | <span data-ttu-id="1dbfc-443">true (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="1dbfc-443">true (default)</span></span> <br/> <span data-ttu-id="1dbfc-444">false</span><span class="sxs-lookup"><span data-stu-id="1dbfc-444">false</span></span> |

#### <a name="enable--disable-automatic-security-intelligence-updates"></a><span data-ttu-id="1dbfc-445">Abilitare/disabilitare gli aggiornamenti automatici delle funzionalità di intelligence per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="1dbfc-445">Enable / disable automatic security intelligence updates</span></span>

<span data-ttu-id="1dbfc-446">Determina se gli aggiornamenti delle funzionalità di intelligence per la sicurezza vengono installati automaticamente:</span><span class="sxs-lookup"><span data-stu-id="1dbfc-446">Determines whether security intelligence updates are installed automatically:</span></span>

|<span data-ttu-id="1dbfc-447">Sezione</span><span class="sxs-lookup"><span data-stu-id="1dbfc-447">Section</span></span>|<span data-ttu-id="1dbfc-448">Valore</span><span class="sxs-lookup"><span data-stu-id="1dbfc-448">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1dbfc-449">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-449">**Key**</span></span> | <span data-ttu-id="1dbfc-450">automaticDefinitionUpdateEnabled</span><span class="sxs-lookup"><span data-stu-id="1dbfc-450">automaticDefinitionUpdateEnabled</span></span> |
| <span data-ttu-id="1dbfc-451">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-451">**Data type**</span></span> | <span data-ttu-id="1dbfc-452">Booleano</span><span class="sxs-lookup"><span data-stu-id="1dbfc-452">Boolean</span></span> |
| <span data-ttu-id="1dbfc-453">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-453">**Possible values**</span></span> | <span data-ttu-id="1dbfc-454">true (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="1dbfc-454">true (default)</span></span> <br/> <span data-ttu-id="1dbfc-455">false</span><span class="sxs-lookup"><span data-stu-id="1dbfc-455">false</span></span> |

### <a name="user-interface-preferences"></a><span data-ttu-id="1dbfc-456">Preferenze dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="1dbfc-456">User interface preferences</span></span>

<span data-ttu-id="1dbfc-457">Gestire le preferenze per l'interfaccia utente di Microsoft Defender per Endpoint in macOS.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-457">Manage the preferences for the user interface of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="1dbfc-458">Sezione</span><span class="sxs-lookup"><span data-stu-id="1dbfc-458">Section</span></span>|<span data-ttu-id="1dbfc-459">Valore</span><span class="sxs-lookup"><span data-stu-id="1dbfc-459">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1dbfc-460">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-460">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1dbfc-461">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-461">**Key**</span></span> | <span data-ttu-id="1dbfc-462">userInterface</span><span class="sxs-lookup"><span data-stu-id="1dbfc-462">userInterface</span></span> |
| <span data-ttu-id="1dbfc-463">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-463">**Data type**</span></span> | <span data-ttu-id="1dbfc-464">Dizionario (preferenza annidata)</span><span class="sxs-lookup"><span data-stu-id="1dbfc-464">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="1dbfc-465">**Comments**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-465">**Comments**</span></span> | <span data-ttu-id="1dbfc-466">Per una descrizione del contenuto del dizionario, vedi le sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-466">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="show--hide-status-menu-icon"></a><span data-ttu-id="1dbfc-467">Mostra/nascondi icona del menu di stato</span><span class="sxs-lookup"><span data-stu-id="1dbfc-467">Show / hide status menu icon</span></span>

<span data-ttu-id="1dbfc-468">Specifica se mostrare o nascondere l'icona del menu di stato nell'angolo in alto a destra dello schermo.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-468">Specify whether to show or hide the status menu icon in the top-right corner of the screen.</span></span>

|<span data-ttu-id="1dbfc-469">Sezione</span><span class="sxs-lookup"><span data-stu-id="1dbfc-469">Section</span></span>|<span data-ttu-id="1dbfc-470">Valore</span><span class="sxs-lookup"><span data-stu-id="1dbfc-470">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1dbfc-471">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-471">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1dbfc-472">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-472">**Key**</span></span> | <span data-ttu-id="1dbfc-473">hideStatusMenuIcon</span><span class="sxs-lookup"><span data-stu-id="1dbfc-473">hideStatusMenuIcon</span></span> |
| <span data-ttu-id="1dbfc-474">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-474">**Data type**</span></span> | <span data-ttu-id="1dbfc-475">Booleano</span><span class="sxs-lookup"><span data-stu-id="1dbfc-475">Boolean</span></span> |
| <span data-ttu-id="1dbfc-476">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-476">**Possible values**</span></span> | <span data-ttu-id="1dbfc-477">false (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="1dbfc-477">false (default)</span></span> <br/> <span data-ttu-id="1dbfc-478">true</span><span class="sxs-lookup"><span data-stu-id="1dbfc-478">true</span></span> |

#### <a name="show--hide-option-to-send-feedback"></a><span data-ttu-id="1dbfc-479">Opzione Mostra/Nascondi per inviare commenti e suggerimenti</span><span class="sxs-lookup"><span data-stu-id="1dbfc-479">Show / hide option to send feedback</span></span>

<span data-ttu-id="1dbfc-480">Specificare se gli utenti possono inviare commenti e suggerimenti a Microsoft andando a `Help`  >  `Send Feedback` .</span><span class="sxs-lookup"><span data-stu-id="1dbfc-480">Specify whether users can submit feedback to Microsoft by going to `Help` > `Send Feedback`.</span></span>

|<span data-ttu-id="1dbfc-481">Sezione</span><span class="sxs-lookup"><span data-stu-id="1dbfc-481">Section</span></span>|<span data-ttu-id="1dbfc-482">Valore</span><span class="sxs-lookup"><span data-stu-id="1dbfc-482">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1dbfc-483">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-483">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1dbfc-484">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-484">**Key**</span></span> | <span data-ttu-id="1dbfc-485">userInitiatedFeedback</span><span class="sxs-lookup"><span data-stu-id="1dbfc-485">userInitiatedFeedback</span></span> |
| <span data-ttu-id="1dbfc-486">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-486">**Data type**</span></span> | <span data-ttu-id="1dbfc-487">Stringa</span><span class="sxs-lookup"><span data-stu-id="1dbfc-487">String</span></span> |
| <span data-ttu-id="1dbfc-488">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-488">**Possible values**</span></span> | <span data-ttu-id="1dbfc-489">enabled (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="1dbfc-489">enabled (default)</span></span> <br/> <span data-ttu-id="1dbfc-490">disabilitati</span><span class="sxs-lookup"><span data-stu-id="1dbfc-490">disabled</span></span> |
| <span data-ttu-id="1dbfc-491">**Comments**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-491">**Comments**</span></span> | <span data-ttu-id="1dbfc-492">Disponibile in Microsoft Defender per Endpoint versione 101.19.61 o successiva.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-492">Available in Microsoft Defender for Endpoint version 101.19.61 or higher.</span></span> |

### <a name="endpoint-detection-and-response-preferences"></a><span data-ttu-id="1dbfc-493">Preferenze di risposta e rilevamento degli endpoint</span><span class="sxs-lookup"><span data-stu-id="1dbfc-493">Endpoint detection and response preferences</span></span>

<span data-ttu-id="1dbfc-494">Gestisci le preferenze del componente di rilevamento e risposta degli endpoint (EDR) di Microsoft Defender per Endpoint in macOS.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-494">Manage the preferences of the endpoint detection and response (EDR) component of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="1dbfc-495">Sezione</span><span class="sxs-lookup"><span data-stu-id="1dbfc-495">Section</span></span>|<span data-ttu-id="1dbfc-496">Valore</span><span class="sxs-lookup"><span data-stu-id="1dbfc-496">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1dbfc-497">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-497">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1dbfc-498">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-498">**Key**</span></span> | <span data-ttu-id="1dbfc-499">edr</span><span class="sxs-lookup"><span data-stu-id="1dbfc-499">edr</span></span> |
| <span data-ttu-id="1dbfc-500">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-500">**Data type**</span></span> | <span data-ttu-id="1dbfc-501">Dizionario (preferenza annidata)</span><span class="sxs-lookup"><span data-stu-id="1dbfc-501">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="1dbfc-502">**Comments**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-502">**Comments**</span></span> | <span data-ttu-id="1dbfc-503">Per una descrizione del contenuto del dizionario, vedi le sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-503">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="device-tags"></a><span data-ttu-id="1dbfc-504">Tag dispositivo</span><span class="sxs-lookup"><span data-stu-id="1dbfc-504">Device tags</span></span>

<span data-ttu-id="1dbfc-505">Specificare un nome di tag e il relativo valore.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-505">Specify a tag name and its value.</span></span> 

- <span data-ttu-id="1dbfc-506">Il tag GROUP contrassegna il dispositivo con il valore specificato.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-506">The GROUP tag, tags the device with the specified value.</span></span> <span data-ttu-id="1dbfc-507">Il tag si riflette nel portale nella pagina del dispositivo e può essere usato per filtrare e raggruppare i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-507">The tag is reflected in the portal under the device page and can be used for filtering and grouping devices.</span></span>

|<span data-ttu-id="1dbfc-508">Sezione</span><span class="sxs-lookup"><span data-stu-id="1dbfc-508">Section</span></span>|<span data-ttu-id="1dbfc-509">Valore</span><span class="sxs-lookup"><span data-stu-id="1dbfc-509">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1dbfc-510">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-510">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1dbfc-511">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-511">**Key**</span></span> | <span data-ttu-id="1dbfc-512">tag</span><span class="sxs-lookup"><span data-stu-id="1dbfc-512">tags</span></span> |
| <span data-ttu-id="1dbfc-513">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-513">**Data type**</span></span> | <span data-ttu-id="1dbfc-514">Dizionario (preferenza annidata)</span><span class="sxs-lookup"><span data-stu-id="1dbfc-514">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="1dbfc-515">**Comments**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-515">**Comments**</span></span> | <span data-ttu-id="1dbfc-516">Per una descrizione del contenuto del dizionario, vedi le sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-516">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="type-of-tag"></a><span data-ttu-id="1dbfc-517">Tipo di tag</span><span class="sxs-lookup"><span data-stu-id="1dbfc-517">Type of tag</span></span>

<span data-ttu-id="1dbfc-518">Specifica il tipo di tag</span><span class="sxs-lookup"><span data-stu-id="1dbfc-518">Specifies the type of tag</span></span>

|<span data-ttu-id="1dbfc-519">Sezione</span><span class="sxs-lookup"><span data-stu-id="1dbfc-519">Section</span></span>|<span data-ttu-id="1dbfc-520">Valore</span><span class="sxs-lookup"><span data-stu-id="1dbfc-520">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1dbfc-521">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-521">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1dbfc-522">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-522">**Key**</span></span> | <span data-ttu-id="1dbfc-523">chiave</span><span class="sxs-lookup"><span data-stu-id="1dbfc-523">key</span></span> |
| <span data-ttu-id="1dbfc-524">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-524">**Data type**</span></span> | <span data-ttu-id="1dbfc-525">Stringa</span><span class="sxs-lookup"><span data-stu-id="1dbfc-525">String</span></span> |
| <span data-ttu-id="1dbfc-526">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-526">**Possible values**</span></span> | `GROUP` |

##### <a name="value-of-tag"></a><span data-ttu-id="1dbfc-527">Valore del tag</span><span class="sxs-lookup"><span data-stu-id="1dbfc-527">Value of tag</span></span>

<span data-ttu-id="1dbfc-528">Specifica il valore del tag</span><span class="sxs-lookup"><span data-stu-id="1dbfc-528">Specifies the value of tag</span></span>

|<span data-ttu-id="1dbfc-529">Sezione</span><span class="sxs-lookup"><span data-stu-id="1dbfc-529">Section</span></span>|<span data-ttu-id="1dbfc-530">Valore</span><span class="sxs-lookup"><span data-stu-id="1dbfc-530">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1dbfc-531">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-531">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1dbfc-532">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-532">**Key**</span></span> | <span data-ttu-id="1dbfc-533">valore</span><span class="sxs-lookup"><span data-stu-id="1dbfc-533">value</span></span> |
| <span data-ttu-id="1dbfc-534">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-534">**Data type**</span></span> | <span data-ttu-id="1dbfc-535">Stringa</span><span class="sxs-lookup"><span data-stu-id="1dbfc-535">String</span></span> |
| <span data-ttu-id="1dbfc-536">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="1dbfc-536">**Possible values**</span></span> | <span data-ttu-id="1dbfc-537">qualsiasi stringa</span><span class="sxs-lookup"><span data-stu-id="1dbfc-537">any string</span></span> |

> [!IMPORTANT]  
> - <span data-ttu-id="1dbfc-538">È possibile impostare un solo valore per ogni tipo di tag.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-538">Only one value per tag type can be set.</span></span>
> - <span data-ttu-id="1dbfc-539">Il tipo di tag è univoco e non deve essere ripetuto nello stesso profilo di configurazione.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-539">Type of tags are unique, and should not be repeated in the same configuration profile.</span></span>

## <a name="recommended-configuration-profile"></a><span data-ttu-id="1dbfc-540">Profilo di configurazione consigliato</span><span class="sxs-lookup"><span data-stu-id="1dbfc-540">Recommended configuration profile</span></span>

<span data-ttu-id="1dbfc-541">Per iniziare, ti consigliamo la configurazione seguente per l'azienda per sfruttare tutte le funzionalità di protezione fornite da Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-541">To get started, we recommend the following configuration for your enterprise to take advantage of all protection features that Microsoft Defender for Endpoint provides.</span></span>

<span data-ttu-id="1dbfc-542">Il profilo di configurazione seguente (o, nel caso di JAMF, un elenco di proprietà che potrebbe essere caricato nel profilo di configurazione delle impostazioni personalizzate) sarà:</span><span class="sxs-lookup"><span data-stu-id="1dbfc-542">The following configuration profile (or, in case of JAMF, a property list that could be uploaded into the custom settings configuration profile) will:</span></span>
- <span data-ttu-id="1dbfc-543">Abilitare la protezione in tempo reale (RTP)</span><span class="sxs-lookup"><span data-stu-id="1dbfc-543">Enable real-time protection (RTP)</span></span>
- <span data-ttu-id="1dbfc-544">Specificare la modalità di gestione dei seguenti tipi di minacce:</span><span class="sxs-lookup"><span data-stu-id="1dbfc-544">Specify how the following threat types are handled:</span></span>
  - <span data-ttu-id="1dbfc-545">**Le applicazioni potenzialmente indesiderate sono** bloccate</span><span class="sxs-lookup"><span data-stu-id="1dbfc-545">**Potentially unwanted applications (PUA)** are blocked</span></span>
  - <span data-ttu-id="1dbfc-546">**Le bombe di** archiviazione (file con una velocità di compressione elevata) vengono verificate in Microsoft Defender per i log degli endpoint</span><span class="sxs-lookup"><span data-stu-id="1dbfc-546">**Archive bombs** (file with a high compression rate) are audited to Microsoft Defender for Endpoint logs</span></span>
- <span data-ttu-id="1dbfc-547">Abilitare gli aggiornamenti automatici delle funzionalità di intelligence per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="1dbfc-547">Enable automatic security intelligence updates</span></span>
- <span data-ttu-id="1dbfc-548">Abilitare la protezione fornita dal cloud</span><span class="sxs-lookup"><span data-stu-id="1dbfc-548">Enable cloud-delivered protection</span></span>
- <span data-ttu-id="1dbfc-549">Abilitare l'invio automatico di esempi</span><span class="sxs-lookup"><span data-stu-id="1dbfc-549">Enable automatic sample submission</span></span>

### <a name="property-list-for-jamf-configuration-profile"></a><span data-ttu-id="1dbfc-550">Elenco delle proprietà per il profilo di configurazione JAMF</span><span class="sxs-lookup"><span data-stu-id="1dbfc-550">Property list for JAMF configuration profile</span></span>

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>antivirusEngine</key>
    <dict>
        <key>enableRealTimeProtection</key>
        <true/>
        <key>threatTypeSettings</key>
        <array>
            <dict>
                <key>key</key>
                <string>potentially_unwanted_application</string>
                <key>value</key>
                <string>block</string>
            </dict>
            <dict>
                <key>key</key>
                <string>archive_bomb</string>
                <key>value</key>
                <string>audit</string>
            </dict>
        </array>
    </dict>
    <key>cloudService</key>
    <dict>
        <key>enabled</key>
        <true/>
        <key>automaticSampleSubmission</key>
        <true/>
        <key>automaticDefinitionUpdateEnabled</key>
        <true/>
    </dict>
</dict>
</plist>
```

### <a name="intune-profile"></a><span data-ttu-id="1dbfc-551">Profilo intune</span><span class="sxs-lookup"><span data-stu-id="1dbfc-551">Intune profile</span></span>

```XML
<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1">
    <dict>
        <key>PayloadUUID</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>com.microsoft.wdav</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft Defender for Endpoint settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft Defender for Endpoint configuration settings</string>
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
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadType</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadOrganization</key>
                <string>Microsoft</string>
                <key>PayloadIdentifier</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadDisplayName</key>
                <string>Microsoft Defender for Endpoint configuration settings</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
                <key>antivirusEngine</key>
                <dict>
                    <key>enableRealTimeProtection</key>
                    <true/>
                    <key>threatTypeSettings</key>
                    <array>
                        <dict>
                            <key>key</key>
                            <string>potentially_unwanted_application</string>
                            <key>value</key>
                            <string>block</string>
                        </dict>
                        <dict>
                            <key>key</key>
                            <string>archive_bomb</string>
                            <key>value</key>
                            <string>audit</string>
                        </dict>
                    </array>
                </dict>
                <key>cloudService</key>
                <dict>
                    <key>enabled</key>
                    <true/>
                    <key>automaticSampleSubmission</key>
                    <true/>
                    <key>automaticDefinitionUpdateEnabled</key>
                    <true/>
                </dict>
            </dict>
        </array>
    </dict>
</plist>
```

## <a name="full-configuration-profile-example"></a><span data-ttu-id="1dbfc-552">Esempio di profilo di configurazione completo</span><span class="sxs-lookup"><span data-stu-id="1dbfc-552">Full configuration profile example</span></span>

<span data-ttu-id="1dbfc-553">I modelli seguenti contengono voci per tutte le impostazioni descritte in questo documento e possono essere usati per scenari più avanzati in cui si desidera un maggiore controllo su Microsoft Defender for Endpoint in macOS.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-553">The following templates contain entries for all settings described in this document and can be used for more advanced scenarios where you want more control over Microsoft Defender for Endpoint on macOS.</span></span>

### <a name="property-list-for-jamf-configuration-profile"></a><span data-ttu-id="1dbfc-554">Elenco delle proprietà per il profilo di configurazione JAMF</span><span class="sxs-lookup"><span data-stu-id="1dbfc-554">Property list for JAMF configuration profile</span></span>

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>antivirusEngine</key>
    <dict>
        <key>enableRealTimeProtection</key>
        <true/>
        <key>passiveMode</key>
        <false/>
        <key>exclusions</key>
        <array>
            <dict>
                <key>$type</key>
                <string>excludedPath</string>
                <key>isDirectory</key>
                <false/>
                <key>path</key>
                <string>/var/log/system.log</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedPath</string>
                <key>isDirectory</key>
                <true/>
                <key>path</key>
                <string>/home</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedPath</string>
                <key>isDirectory</key>
                <true/>
                <key>path</key>
                <string>/Users/*/git</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedFileExtension</string>
                <key>extension</key>
                <string>pdf</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedFileName</string>
                <key>name</key>
                <string>cat</string>
            </dict>
        </array>
        <key>exclusionsMergePolicy</key>
        <string>merge</string>
        <key>allowedThreats</key>
        <array>
            <string>EICAR-Test-File (not a virus)</string>
        </array>
        <key>disallowedThreatActions</key>
        <array>
            <string>allow</string>
            <string>restore</string>
        </array>
        <key>threatTypeSettings</key>
        <array>
            <dict>
                <key>key</key>
                <string>potentially_unwanted_application</string>
                <key>value</key>
                <string>block</string>
            </dict>
            <dict>
                <key>key</key>
                <string>archive_bomb</string>
                <key>value</key>
                <string>audit</string>
            </dict>
        </array>
        <key>threatTypeSettingsMergePolicy</key>
        <string>merge</string>
    </dict>
    <key>cloudService</key>
    <dict>
        <key>enabled</key>
        <true/>
        <key>diagnosticLevel</key>
        <string>optional</string>
        <key>automaticSampleSubmission</key>
        <true/>
        <key>automaticDefinitionUpdateEnabled</key>
        <true/>
    </dict>
    <key>edr</key>
    <dict>
        <key>tags</key>
        <array>
            <dict>
                <key>key</key>
                <string>GROUP</string>
                <key>value</key>
                <string>ExampleTag</string>
            </dict>
        </array>
    </dict>
    <key>userInterface</key>
    <dict>
        <key>hideStatusMenuIcon</key>
        <false/>
        <key>userInitiatedFeedback</key>
        <string>enabled</string>
    </dict>
</dict>
</plist>
```

### <a name="intune-profile"></a><span data-ttu-id="1dbfc-555">Profilo intune</span><span class="sxs-lookup"><span data-stu-id="1dbfc-555">Intune profile</span></span>

```XML
        <key>PayloadUUID</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft Defender for Endpoint settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft Defender for Endpoint configuration settings</string>
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
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadType</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadOrganization</key>
                <string>Microsoft</string>
                <key>PayloadIdentifier</key>
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadDisplayName</key>
                <string>Microsoft Defender for Endpoint configuration settings</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
                <key>antivirusEngine</key>
                <dict>
                    <key>enableRealTimeProtection</key>
                    <true/>
                    <key>passiveMode</key>
                    <false/>
                    <key>exclusions</key>
                    <array>
                        <dict>
                            <key>$type</key>
                            <string>excludedPath</string>
                            <key>isDirectory</key>
                            <false/>
                            <key>path</key>
                            <string>/var/log/system.log</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedPath</string>
                            <key>isDirectory</key>
                            <true/>
                            <key>path</key>
                            <string>/home</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedPath</string>
                            <key>isDirectory</key>
                            <true/>
                            <key>path</key>
                            <string>/Users/*/git</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedFileExtension</string>
                            <key>extension</key>
                            <string>pdf</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedFileName</string>
                            <key>name</key>
                            <string>cat</string>
                        </dict>
                    </array>
                    <key>exclusionsMergePolicy</key>
                    <string>merge</string>
                    <key>allowedThreats</key>
                    <array>
                        <string>EICAR-Test-File (not a virus)</string>
                    </array>
                    <key>disallowedThreatActions</key>
                    <array>
                        <string>allow</string>
                        <string>restore</string>
                    </array>
                    <key>threatTypeSettings</key>
                    <array>
                        <dict>
                            <key>key</key>
                            <string>potentially_unwanted_application</string>
                            <key>value</key>
                            <string>block</string>
                        </dict>
                        <dict>
                            <key>key</key>
                            <string>archive_bomb</string>
                            <key>value</key>
                            <string>audit</string>
                        </dict>
                    </array>
                    <key>threatTypeSettingsMergePolicy</key>
                    <string>merge</string>
                </dict>
                <key>cloudService</key>
                <dict>
                    <key>enabled</key>
                    <true/>
                    <key>diagnosticLevel</key>
                    <string>optional</string>
                    <key>automaticSampleSubmission</key>
                    <true/>
                    <key>automaticDefinitionUpdateEnabled</key>
                    <true/>
                </dict>
                <key>edr</key>
                <dict>
                    <key>tags</key>
                    <array>
                        <dict>
                            <key>key</key>
                            <string>GROUP</string>
                            <key>value</key>
                            <string>ExampleTag</string>
                        </dict>
                    </array>
                </dict>
                <key>userInterface</key>
                <dict>
                    <key>hideStatusMenuIcon</key>
                    <false/>
                    <key>userInitiatedFeedback</key>
                    <string>enabled</string>
                </dict>
            </dict>
        </array>
```

## <a name="property-list-validation"></a><span data-ttu-id="1dbfc-556">Convalida elenco proprietà</span><span class="sxs-lookup"><span data-stu-id="1dbfc-556">Property list validation</span></span>

<span data-ttu-id="1dbfc-557">L'elenco delle proprietà deve essere un file *plist* valido.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-557">The property list must be a valid *.plist* file.</span></span> <span data-ttu-id="1dbfc-558">Questa operazione può essere verificata eseguendo:</span><span class="sxs-lookup"><span data-stu-id="1dbfc-558">This can be checked by executing:</span></span>

```bash
plutil -lint com.microsoft.wdav.plist
```
```Output
com.microsoft.wdav.plist: OK
```

<span data-ttu-id="1dbfc-559">Se il file è ben formato, il comando precedente restituisce un `OK` codice di uscita di `0` .</span><span class="sxs-lookup"><span data-stu-id="1dbfc-559">If the file is well-formed, the above command outputs `OK` and returns an exit code of `0`.</span></span> <span data-ttu-id="1dbfc-560">In caso contrario, viene visualizzato un errore che descrive il problema e il comando restituisce un codice di uscita di `1` .</span><span class="sxs-lookup"><span data-stu-id="1dbfc-560">Otherwise, an error that describes the issue is displayed and the command returns an exit code of `1`.</span></span>

## <a name="configuration-profile-deployment"></a><span data-ttu-id="1dbfc-561">Distribuzione dei profili di configurazione</span><span class="sxs-lookup"><span data-stu-id="1dbfc-561">Configuration profile deployment</span></span>

<span data-ttu-id="1dbfc-562">Dopo aver creato il profilo di configurazione per l'organizzazione, è possibile distribuirlo tramite la console di gestione in uso.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-562">Once you've built the configuration profile for your enterprise, you can deploy it through the management console that your enterprise is using.</span></span> <span data-ttu-id="1dbfc-563">Le sezioni seguenti forniscono istruzioni su come distribuire questo profilo usando JAMF e Intune.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-563">The following sections provide instructions on how to deploy this profile using JAMF and Intune.</span></span>

### <a name="jamf-deployment"></a><span data-ttu-id="1dbfc-564">Distribuzione JAMF</span><span class="sxs-lookup"><span data-stu-id="1dbfc-564">JAMF deployment</span></span>

<span data-ttu-id="1dbfc-565">Dalla console JAMF, aprire **Profili** di configurazione computer, passare al profilo di configurazione che si desidera utilizzare, quindi  >  selezionare **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-565">From the JAMF console, open **Computers** > **Configuration Profiles**, navigate to the configuration profile you'd like to use, then select **Custom Settings**.</span></span> <span data-ttu-id="1dbfc-566">Crea una voce con `com.microsoft.wdav` come dominio di preferenza e carica il file *plist* prodotto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-566">Create an entry with `com.microsoft.wdav` as the preference domain and upload the *.plist* produced earlier.</span></span>

>[!CAUTION]
><span data-ttu-id="1dbfc-567">È necessario immettere il dominio di preferenza corretto ( ); in caso contrario, le preferenze non verranno `com.microsoft.wdav` riconosciute da Microsoft Defender per Endpoint.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-567">You must enter the correct preference domain (`com.microsoft.wdav`); otherwise, the preferences will not be recognized by Microsoft Defender for Endpoint.</span></span>

### <a name="intune-deployment"></a><span data-ttu-id="1dbfc-568">Distribuzione di Intune</span><span class="sxs-lookup"><span data-stu-id="1dbfc-568">Intune deployment</span></span>

1. <span data-ttu-id="1dbfc-569">Aprire **Gestisci**  >  **configurazione dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-569">Open **Manage** > **Device configuration**.</span></span> <span data-ttu-id="1dbfc-570">Selezionare **Gestisci**  >  **profili**  >  **Crea profilo**.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-570">Select **Manage** > **Profiles** > **Create Profile**.</span></span>

2. <span data-ttu-id="1dbfc-571">Scegliere un nome per il profilo.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-571">Choose a name for the profile.</span></span> <span data-ttu-id="1dbfc-572">Modificare **Platform=macOS** in **Profile type=Custom**.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-572">Change **Platform=macOS** to **Profile type=Custom**.</span></span> <span data-ttu-id="1dbfc-573">Selezionare Configura.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-573">Select Configure.</span></span>

3. <span data-ttu-id="1dbfc-574">Salvare il file plist prodotto in precedenza come `com.microsoft.wdav.xml` .</span><span class="sxs-lookup"><span data-stu-id="1dbfc-574">Save the .plist produced earlier as `com.microsoft.wdav.xml`.</span></span>

4. <span data-ttu-id="1dbfc-575">Immettere `com.microsoft.wdav` come nome del profilo di configurazione **personalizzato**.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-575">Enter `com.microsoft.wdav` as the **custom configuration profile name**.</span></span>

5. <span data-ttu-id="1dbfc-576">Apri il profilo di configurazione e carica il `com.microsoft.wdav.xml` file.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-576">Open the configuration profile and upload the `com.microsoft.wdav.xml` file.</span></span> <span data-ttu-id="1dbfc-577">Questo file è stato creato nel passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-577">(This file was created in step 3.)</span></span>

6. <span data-ttu-id="1dbfc-578">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-578">Select **OK**.</span></span>

7. <span data-ttu-id="1dbfc-579">Selezionare **Gestisci**  >  **assegnazioni**.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-579">Select **Manage** > **Assignments**.</span></span> <span data-ttu-id="1dbfc-580">Nella scheda **Includi** seleziona **Assegna a tutti gli utenti & Tutti i dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-580">In the **Include** tab, select **Assign to All Users & All devices**.</span></span>

>[!CAUTION]
><span data-ttu-id="1dbfc-581">È necessario immettere il nome del profilo di configurazione personalizzato corretto. in caso contrario, queste preferenze non verranno riconosciute da Microsoft Defender per Endpoint.</span><span class="sxs-lookup"><span data-stu-id="1dbfc-581">You must enter the correct custom configuration profile name; otherwise, these preferences will not be recognized by Microsoft Defender for Endpoint.</span></span>

## <a name="resources"></a><span data-ttu-id="1dbfc-582">Risorse</span><span class="sxs-lookup"><span data-stu-id="1dbfc-582">Resources</span></span>

- [<span data-ttu-id="1dbfc-583">Informazioni di riferimento sui profili di configurazione (documentazione per sviluppatori Apple)</span><span class="sxs-lookup"><span data-stu-id="1dbfc-583">Configuration Profile Reference (Apple developer documentation)</span></span>](https://developer.apple.com/business/documentation/Configuration-Profile-Reference.pdf)
