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
ms.openlocfilehash: f13734392e4975738a0d60d38e618595b5175667
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934562"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="20bb2-104">Impostare le preferenze per Microsoft Defender per Endpoint in macOS</span><span class="sxs-lookup"><span data-stu-id="20bb2-104">Set preferences for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="20bb2-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="20bb2-105">**Applies to:**</span></span>

- [<span data-ttu-id="20bb2-106">Microsoft Defender per endpoint su macOS</span><span class="sxs-lookup"><span data-stu-id="20bb2-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)

>[!IMPORTANT]
><span data-ttu-id="20bb2-107">Questo articolo contiene istruzioni su come impostare le preferenze per Microsoft Defender per Endpoint in macOS nelle organizzazioni aziendali.</span><span class="sxs-lookup"><span data-stu-id="20bb2-107">This article contains instructions for how to set preferences for Microsoft Defender for Endpoint on macOS in enterprise organizations.</span></span> <span data-ttu-id="20bb2-108">Per configurare Microsoft Defender per Endpoint in macOS tramite l'interfaccia della riga di comando, vedi [Risorse](mac-resources.md#configuring-from-the-command-line).</span><span class="sxs-lookup"><span data-stu-id="20bb2-108">To configure Microsoft Defender for Endpoint on macOS using the command-line interface, see [Resources](mac-resources.md#configuring-from-the-command-line).</span></span>

## <a name="summary"></a><span data-ttu-id="20bb2-109">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="20bb2-109">Summary</span></span>

<span data-ttu-id="20bb2-110">Nelle organizzazioni aziendali, Microsoft Defender for Endpoint in macOS può essere gestito tramite un profilo di configurazione distribuito utilizzando uno dei diversi strumenti di gestione.</span><span class="sxs-lookup"><span data-stu-id="20bb2-110">In enterprise organizations, Microsoft Defender for Endpoint on macOS can be managed through a configuration profile that is deployed by using one of several management tools.</span></span> <span data-ttu-id="20bb2-111">Le preferenze gestite dal team delle operazioni di sicurezza hanno la precedenza sulle preferenze impostate localmente nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="20bb2-111">Preferences that are managed by your security operations team take precedence over preferences that are set locally on the device.</span></span> <span data-ttu-id="20bb2-112">La modifica delle preferenze impostate tramite il profilo di configurazione richiede privilegi inoltrati e non è disponibile per gli utenti senza autorizzazioni amministrative.</span><span class="sxs-lookup"><span data-stu-id="20bb2-112">Changing the preferences that are set through the configuration profile requires escalated privileges and is not available for users without administrative permissions.</span></span>

<span data-ttu-id="20bb2-113">Questo articolo descrive la struttura del profilo di configurazione, include un profilo consigliato che puoi usare per iniziare e fornisce istruzioni su come distribuire il profilo.</span><span class="sxs-lookup"><span data-stu-id="20bb2-113">This article describes the structure of the configuration profile, includes a recommended profile that you can use to get started, and provides instructions on how to deploy the profile.</span></span>

## <a name="configuration-profile-structure"></a><span data-ttu-id="20bb2-114">Struttura del profilo di configurazione</span><span class="sxs-lookup"><span data-stu-id="20bb2-114">Configuration profile structure</span></span>

<span data-ttu-id="20bb2-115">Il profilo di configurazione è un file *plist* costituito da voci identificate da una chiave (che indica il nome della preferenza), seguita da un valore, che dipende dalla natura della preferenza.</span><span class="sxs-lookup"><span data-stu-id="20bb2-115">The configuration profile is a *.plist* file that consists of entries identified by a key (which denotes the name of the preference), followed by a value, which depends on the nature of the preference.</span></span> <span data-ttu-id="20bb2-116">I valori possono essere semplici (ad esempio un valore numerico) o complessi, ad esempio un elenco nidificato di preferenze.</span><span class="sxs-lookup"><span data-stu-id="20bb2-116">Values can either be simple (such as a numerical value) or complex, such as a nested list of preferences.</span></span>

>[!CAUTION]
><span data-ttu-id="20bb2-117">Il layout del profilo di configurazione dipende dalla console di gestione in uso.</span><span class="sxs-lookup"><span data-stu-id="20bb2-117">The layout of the configuration profile depends on the management console that you are using.</span></span> <span data-ttu-id="20bb2-118">Le sezioni seguenti contengono esempi di profili di configurazione per JAMF e Intune.</span><span class="sxs-lookup"><span data-stu-id="20bb2-118">The following sections contain examples of configuration profiles for JAMF and Intune.</span></span>

<span data-ttu-id="20bb2-119">Il livello superiore del profilo di configurazione include le preferenze e le voci a livello di prodotto per le sottoaree di Microsoft Defender per Endpoint, che vengono illustrate in modo più dettagliato nelle sezioni successive.</span><span class="sxs-lookup"><span data-stu-id="20bb2-119">The top level of the configuration profile includes product-wide preferences and entries for subareas of Microsoft Defender for Endpoint, which are explained in more detail in the next sections.</span></span>

### <a name="antivirus-engine-preferences"></a><span data-ttu-id="20bb2-120">Preferenze del motore antivirus</span><span class="sxs-lookup"><span data-stu-id="20bb2-120">Antivirus engine preferences</span></span>

<span data-ttu-id="20bb2-121">La *sezione antivirusEngine* del profilo di configurazione viene usata per gestire le preferenze del componente antivirus di Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="20bb2-121">The *antivirusEngine* section of the configuration profile is used to manage the preferences of the antivirus component of Microsoft Defender for Endpoint.</span></span>

|<span data-ttu-id="20bb2-122">Sezione</span><span class="sxs-lookup"><span data-stu-id="20bb2-122">Section</span></span>|<span data-ttu-id="20bb2-123">Valore</span><span class="sxs-lookup"><span data-stu-id="20bb2-123">Value</span></span>|
|:---|:---|
| <span data-ttu-id="20bb2-124">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="20bb2-124">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="20bb2-125">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="20bb2-125">**Key**</span></span> | <span data-ttu-id="20bb2-126">antivirusEngine</span><span class="sxs-lookup"><span data-stu-id="20bb2-126">antivirusEngine</span></span> |
| <span data-ttu-id="20bb2-127">**Data type**</span><span class="sxs-lookup"><span data-stu-id="20bb2-127">**Data type**</span></span> | <span data-ttu-id="20bb2-128">Dizionario (preferenza annidata)</span><span class="sxs-lookup"><span data-stu-id="20bb2-128">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="20bb2-129">**Comments**</span><span class="sxs-lookup"><span data-stu-id="20bb2-129">**Comments**</span></span> | <span data-ttu-id="20bb2-130">Per una descrizione del contenuto del dizionario, vedi le sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="20bb2-130">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-real-time-protection"></a><span data-ttu-id="20bb2-131">Abilitare/disabilitare la protezione in tempo reale</span><span class="sxs-lookup"><span data-stu-id="20bb2-131">Enable / disable real-time protection</span></span>

<span data-ttu-id="20bb2-132">Specificare se abilitare la protezione in tempo reale, che analizza i file man a cui si accede.</span><span class="sxs-lookup"><span data-stu-id="20bb2-132">Specify whether to enable real-time protection, which scans files as they are accessed.</span></span>

|<span data-ttu-id="20bb2-133">Sezione</span><span class="sxs-lookup"><span data-stu-id="20bb2-133">Section</span></span>|<span data-ttu-id="20bb2-134">Valore</span><span class="sxs-lookup"><span data-stu-id="20bb2-134">Value</span></span>|
|:---|:---|
| <span data-ttu-id="20bb2-135">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="20bb2-135">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="20bb2-136">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="20bb2-136">**Key**</span></span> | <span data-ttu-id="20bb2-137">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="20bb2-137">enableRealTimeProtection</span></span> |
| <span data-ttu-id="20bb2-138">**Data type**</span><span class="sxs-lookup"><span data-stu-id="20bb2-138">**Data type**</span></span> | <span data-ttu-id="20bb2-139">Booleano</span><span class="sxs-lookup"><span data-stu-id="20bb2-139">Boolean</span></span> |
| <span data-ttu-id="20bb2-140">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="20bb2-140">**Possible values**</span></span> | <span data-ttu-id="20bb2-141">true (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="20bb2-141">true (default)</span></span> <br/> <span data-ttu-id="20bb2-142">false</span><span class="sxs-lookup"><span data-stu-id="20bb2-142">false</span></span> |

#### <a name="enable--disable-passive-mode"></a><span data-ttu-id="20bb2-143">Abilitare/disabilitare la modalità passiva</span><span class="sxs-lookup"><span data-stu-id="20bb2-143">Enable / disable passive mode</span></span>

<span data-ttu-id="20bb2-144">Specificare se il motore antivirus viene eseguito in modalità passiva.</span><span class="sxs-lookup"><span data-stu-id="20bb2-144">Specify whether the antivirus engine runs in passive mode.</span></span> <span data-ttu-id="20bb2-145">La modalità passiva ha le implicazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="20bb2-145">Passive mode has the following implications:</span></span> 
- <span data-ttu-id="20bb2-146">La protezione in tempo reale è disattivata</span><span class="sxs-lookup"><span data-stu-id="20bb2-146">Real-time protection is turned off</span></span>
- <span data-ttu-id="20bb2-147">L'analisi su richiesta è attivata</span><span class="sxs-lookup"><span data-stu-id="20bb2-147">On-demand scanning is turned on</span></span>
- <span data-ttu-id="20bb2-148">La correzione automatica delle minacce è disattivata</span><span class="sxs-lookup"><span data-stu-id="20bb2-148">Automatic threat remediation is turned off</span></span>
- <span data-ttu-id="20bb2-149">Gli aggiornamenti delle funzionalità di intelligence per la sicurezza sono attivati</span><span class="sxs-lookup"><span data-stu-id="20bb2-149">Security intelligence updates are turned on</span></span>
- <span data-ttu-id="20bb2-150">L'icona del menu Stato è nascosta</span><span class="sxs-lookup"><span data-stu-id="20bb2-150">Status menu icon is hidden</span></span>

|<span data-ttu-id="20bb2-151">Sezione</span><span class="sxs-lookup"><span data-stu-id="20bb2-151">Section</span></span>|<span data-ttu-id="20bb2-152">Valore</span><span class="sxs-lookup"><span data-stu-id="20bb2-152">Value</span></span>|
|:---|:---|
| <span data-ttu-id="20bb2-153">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="20bb2-153">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="20bb2-154">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="20bb2-154">**Key**</span></span> | <span data-ttu-id="20bb2-155">passiveMode</span><span class="sxs-lookup"><span data-stu-id="20bb2-155">passiveMode</span></span> |
| <span data-ttu-id="20bb2-156">**Data type**</span><span class="sxs-lookup"><span data-stu-id="20bb2-156">**Data type**</span></span> | <span data-ttu-id="20bb2-157">Booleano</span><span class="sxs-lookup"><span data-stu-id="20bb2-157">Boolean</span></span> |
| <span data-ttu-id="20bb2-158">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="20bb2-158">**Possible values**</span></span> | <span data-ttu-id="20bb2-159">false (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="20bb2-159">false (default)</span></span> <br/> <span data-ttu-id="20bb2-160">true</span><span class="sxs-lookup"><span data-stu-id="20bb2-160">true</span></span> |
| <span data-ttu-id="20bb2-161">**Comments**</span><span class="sxs-lookup"><span data-stu-id="20bb2-161">**Comments**</span></span> | <span data-ttu-id="20bb2-162">Disponibile in Microsoft Defender per Endpoint versione 100.67.60 o successiva.</span><span class="sxs-lookup"><span data-stu-id="20bb2-162">Available in Microsoft Defender for Endpoint version 100.67.60 or higher.</span></span> |

#### <a name="exclusion-merge-policy"></a><span data-ttu-id="20bb2-163">Criteri di unione esclusioni</span><span class="sxs-lookup"><span data-stu-id="20bb2-163">Exclusion merge policy</span></span>

<span data-ttu-id="20bb2-164">Specificare i criteri di unione per le esclusioni.</span><span class="sxs-lookup"><span data-stu-id="20bb2-164">Specify the merge policy for exclusions.</span></span> <span data-ttu-id="20bb2-165">Può trattarsi di una combinazione di esclusioni definite dall'amministratore e definite dall'utente ( ) o solo di esclusioni definite `merge` dall'amministratore ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="20bb2-165">This can be a combination of administrator-defined and user-defined exclusions (`merge`) or only administrator-defined exclusions (`admin_only`).</span></span> <span data-ttu-id="20bb2-166">Questa impostazione può essere utilizzata per impedire agli utenti locali di definire le proprie esclusioni.</span><span class="sxs-lookup"><span data-stu-id="20bb2-166">This setting can be used to restrict local users from defining their own exclusions.</span></span>

|<span data-ttu-id="20bb2-167">Sezione</span><span class="sxs-lookup"><span data-stu-id="20bb2-167">Section</span></span>|<span data-ttu-id="20bb2-168">Valore</span><span class="sxs-lookup"><span data-stu-id="20bb2-168">Value</span></span>|
|:---|:---|
| <span data-ttu-id="20bb2-169">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="20bb2-169">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="20bb2-170">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="20bb2-170">**Key**</span></span> | <span data-ttu-id="20bb2-171">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="20bb2-171">exclusionsMergePolicy</span></span> |
| <span data-ttu-id="20bb2-172">**Data type**</span><span class="sxs-lookup"><span data-stu-id="20bb2-172">**Data type**</span></span> | <span data-ttu-id="20bb2-173">Stringa</span><span class="sxs-lookup"><span data-stu-id="20bb2-173">String</span></span> |
| <span data-ttu-id="20bb2-174">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="20bb2-174">**Possible values**</span></span> | <span data-ttu-id="20bb2-175">merge (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="20bb2-175">merge (default)</span></span> <br/> <span data-ttu-id="20bb2-176">admin_only</span><span class="sxs-lookup"><span data-stu-id="20bb2-176">admin_only</span></span> |
| <span data-ttu-id="20bb2-177">**Comments**</span><span class="sxs-lookup"><span data-stu-id="20bb2-177">**Comments**</span></span> | <span data-ttu-id="20bb2-178">Disponibile in Microsoft Defender per Endpoint versione 100.83.73 o successiva.</span><span class="sxs-lookup"><span data-stu-id="20bb2-178">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="scan-exclusions"></a><span data-ttu-id="20bb2-179">Esclusioni analisi</span><span class="sxs-lookup"><span data-stu-id="20bb2-179">Scan exclusions</span></span>

<span data-ttu-id="20bb2-180">Specificare le entità escluse dall'analisi.</span><span class="sxs-lookup"><span data-stu-id="20bb2-180">Specify entities excluded from being scanned.</span></span> <span data-ttu-id="20bb2-181">Le esclusioni possono essere specificate da percorsi completi, estensioni o nomi di file.</span><span class="sxs-lookup"><span data-stu-id="20bb2-181">Exclusions can be specified by full paths, extensions, or file names.</span></span>

|<span data-ttu-id="20bb2-182">Sezione</span><span class="sxs-lookup"><span data-stu-id="20bb2-182">Section</span></span>|<span data-ttu-id="20bb2-183">Valore</span><span class="sxs-lookup"><span data-stu-id="20bb2-183">Value</span></span>|
|:---|:---|
| <span data-ttu-id="20bb2-184">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="20bb2-184">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="20bb2-185">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="20bb2-185">**Key**</span></span> | <span data-ttu-id="20bb2-186">esclusioni</span><span class="sxs-lookup"><span data-stu-id="20bb2-186">exclusions</span></span> |
| <span data-ttu-id="20bb2-187">**Data type**</span><span class="sxs-lookup"><span data-stu-id="20bb2-187">**Data type**</span></span> | <span data-ttu-id="20bb2-188">Dizionario (preferenza annidata)</span><span class="sxs-lookup"><span data-stu-id="20bb2-188">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="20bb2-189">**Comments**</span><span class="sxs-lookup"><span data-stu-id="20bb2-189">**Comments**</span></span> | <span data-ttu-id="20bb2-190">Per una descrizione del contenuto del dizionario, vedi le sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="20bb2-190">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="type-of-exclusion"></a><span data-ttu-id="20bb2-191">Tipo di esclusione</span><span class="sxs-lookup"><span data-stu-id="20bb2-191">Type of exclusion</span></span>

<span data-ttu-id="20bb2-192">Specificare il contenuto escluso dall'analisi in base al tipo.</span><span class="sxs-lookup"><span data-stu-id="20bb2-192">Specify content excluded from being scanned by type.</span></span>

|<span data-ttu-id="20bb2-193">Sezione</span><span class="sxs-lookup"><span data-stu-id="20bb2-193">Section</span></span>|<span data-ttu-id="20bb2-194">Valore</span><span class="sxs-lookup"><span data-stu-id="20bb2-194">Value</span></span>|
|:---|:---|
| <span data-ttu-id="20bb2-195">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="20bb2-195">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="20bb2-196">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="20bb2-196">**Key**</span></span> | <span data-ttu-id="20bb2-197">$type</span><span class="sxs-lookup"><span data-stu-id="20bb2-197">$type</span></span> |
| <span data-ttu-id="20bb2-198">**Data type**</span><span class="sxs-lookup"><span data-stu-id="20bb2-198">**Data type**</span></span> | <span data-ttu-id="20bb2-199">Stringa</span><span class="sxs-lookup"><span data-stu-id="20bb2-199">String</span></span> |
| <span data-ttu-id="20bb2-200">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="20bb2-200">**Possible values**</span></span> | <span data-ttu-id="20bb2-201">excludedPath</span><span class="sxs-lookup"><span data-stu-id="20bb2-201">excludedPath</span></span> <br/> <span data-ttu-id="20bb2-202">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="20bb2-202">excludedFileExtension</span></span> <br/> <span data-ttu-id="20bb2-203">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="20bb2-203">excludedFileName</span></span> |

##### <a name="path-to-excluded-content"></a><span data-ttu-id="20bb2-204">Percorso del contenuto escluso</span><span class="sxs-lookup"><span data-stu-id="20bb2-204">Path to excluded content</span></span>

<span data-ttu-id="20bb2-205">Specificare il contenuto escluso dall'analisi tramite il percorso completo del file.</span><span class="sxs-lookup"><span data-stu-id="20bb2-205">Specify content excluded from being scanned by full file path.</span></span>

|<span data-ttu-id="20bb2-206">Sezione</span><span class="sxs-lookup"><span data-stu-id="20bb2-206">Section</span></span>|<span data-ttu-id="20bb2-207">Valore</span><span class="sxs-lookup"><span data-stu-id="20bb2-207">Value</span></span>|
|:---|:---|
| <span data-ttu-id="20bb2-208">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="20bb2-208">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="20bb2-209">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="20bb2-209">**Key**</span></span> | <span data-ttu-id="20bb2-210">path</span><span class="sxs-lookup"><span data-stu-id="20bb2-210">path</span></span> |
| <span data-ttu-id="20bb2-211">**Data type**</span><span class="sxs-lookup"><span data-stu-id="20bb2-211">**Data type**</span></span> | <span data-ttu-id="20bb2-212">Stringa</span><span class="sxs-lookup"><span data-stu-id="20bb2-212">String</span></span> |
| <span data-ttu-id="20bb2-213">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="20bb2-213">**Possible values**</span></span> | <span data-ttu-id="20bb2-214">percorsi validi</span><span class="sxs-lookup"><span data-stu-id="20bb2-214">valid paths</span></span> |
| <span data-ttu-id="20bb2-215">**Comments**</span><span class="sxs-lookup"><span data-stu-id="20bb2-215">**Comments**</span></span> | <span data-ttu-id="20bb2-216">Applicabile solo se *$type* *è excludedPath*</span><span class="sxs-lookup"><span data-stu-id="20bb2-216">Applicable only if *$type* is *excludedPath*</span></span> |

##### <a name="path-type-file--directory"></a><span data-ttu-id="20bb2-217">Tipo di percorso (file/directory)</span><span class="sxs-lookup"><span data-stu-id="20bb2-217">Path type (file / directory)</span></span>

<span data-ttu-id="20bb2-218">Indicare se la *proprietà path* fa riferimento a un file o a una directory.</span><span class="sxs-lookup"><span data-stu-id="20bb2-218">Indicate if the *path* property refers to a file or directory.</span></span> 

|<span data-ttu-id="20bb2-219">Sezione</span><span class="sxs-lookup"><span data-stu-id="20bb2-219">Section</span></span>|<span data-ttu-id="20bb2-220">Valore</span><span class="sxs-lookup"><span data-stu-id="20bb2-220">Value</span></span>|
|:---|:---|
| <span data-ttu-id="20bb2-221">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="20bb2-221">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="20bb2-222">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="20bb2-222">**Key**</span></span> | <span data-ttu-id="20bb2-223">isDirectory</span><span class="sxs-lookup"><span data-stu-id="20bb2-223">isDirectory</span></span> |
| <span data-ttu-id="20bb2-224">**Data type**</span><span class="sxs-lookup"><span data-stu-id="20bb2-224">**Data type**</span></span> | <span data-ttu-id="20bb2-225">Booleano</span><span class="sxs-lookup"><span data-stu-id="20bb2-225">Boolean</span></span> |
| <span data-ttu-id="20bb2-226">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="20bb2-226">**Possible values**</span></span> | <span data-ttu-id="20bb2-227">false (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="20bb2-227">false (default)</span></span> <br/> <span data-ttu-id="20bb2-228">true</span><span class="sxs-lookup"><span data-stu-id="20bb2-228">true</span></span> |
| <span data-ttu-id="20bb2-229">**Comments**</span><span class="sxs-lookup"><span data-stu-id="20bb2-229">**Comments**</span></span> | <span data-ttu-id="20bb2-230">Applicabile solo se *$type* *è excludedPath*</span><span class="sxs-lookup"><span data-stu-id="20bb2-230">Applicable only if *$type* is *excludedPath*</span></span> |

##### <a name="file-extension-excluded-from-the-scan"></a><span data-ttu-id="20bb2-231">Estensione di file esclusa dall'analisi</span><span class="sxs-lookup"><span data-stu-id="20bb2-231">File extension excluded from the scan</span></span>

<span data-ttu-id="20bb2-232">Specificare il contenuto escluso dall'analisi per estensione di file.</span><span class="sxs-lookup"><span data-stu-id="20bb2-232">Specify content excluded from being scanned by file extension.</span></span>

|<span data-ttu-id="20bb2-233">Sezione</span><span class="sxs-lookup"><span data-stu-id="20bb2-233">Section</span></span>|<span data-ttu-id="20bb2-234">Valore</span><span class="sxs-lookup"><span data-stu-id="20bb2-234">Value</span></span>|
|:---|:---|
| <span data-ttu-id="20bb2-235">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="20bb2-235">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="20bb2-236">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="20bb2-236">**Key**</span></span> | <span data-ttu-id="20bb2-237">extension</span><span class="sxs-lookup"><span data-stu-id="20bb2-237">extension</span></span> |
| <span data-ttu-id="20bb2-238">**Data type**</span><span class="sxs-lookup"><span data-stu-id="20bb2-238">**Data type**</span></span> | <span data-ttu-id="20bb2-239">Stringa</span><span class="sxs-lookup"><span data-stu-id="20bb2-239">String</span></span> |
| <span data-ttu-id="20bb2-240">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="20bb2-240">**Possible values**</span></span> | <span data-ttu-id="20bb2-241">estensioni di file valide</span><span class="sxs-lookup"><span data-stu-id="20bb2-241">valid file extensions</span></span> |
| <span data-ttu-id="20bb2-242">**Comments**</span><span class="sxs-lookup"><span data-stu-id="20bb2-242">**Comments**</span></span> | <span data-ttu-id="20bb2-243">Applicabile solo se *$type* *è excludedFileExtension*</span><span class="sxs-lookup"><span data-stu-id="20bb2-243">Applicable only if *$type* is *excludedFileExtension*</span></span> |

##### <a name="process-excluded-from-the-scan"></a><span data-ttu-id="20bb2-244">Processo escluso dall'analisi</span><span class="sxs-lookup"><span data-stu-id="20bb2-244">Process excluded from the scan</span></span>

<span data-ttu-id="20bb2-245">Specificare un processo per il quale tutte le attività dei file vengono escluse dall'analisi.</span><span class="sxs-lookup"><span data-stu-id="20bb2-245">Specify a process for which all file activity is excluded from scanning.</span></span> <span data-ttu-id="20bb2-246">Il processo può essere specificato in base al nome (ad esempio) o al `cat` percorso completo (ad `/bin/cat` esempio).</span><span class="sxs-lookup"><span data-stu-id="20bb2-246">The process can be specified either by its name (e.g. `cat`) or full path (e.g. `/bin/cat`).</span></span>

|<span data-ttu-id="20bb2-247">Sezione</span><span class="sxs-lookup"><span data-stu-id="20bb2-247">Section</span></span>|<span data-ttu-id="20bb2-248">Valore</span><span class="sxs-lookup"><span data-stu-id="20bb2-248">Value</span></span>|
|:---|:---|
| <span data-ttu-id="20bb2-249">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="20bb2-249">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="20bb2-250">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="20bb2-250">**Key**</span></span> | <span data-ttu-id="20bb2-251">name</span><span class="sxs-lookup"><span data-stu-id="20bb2-251">name</span></span> |
| <span data-ttu-id="20bb2-252">**Data type**</span><span class="sxs-lookup"><span data-stu-id="20bb2-252">**Data type**</span></span> | <span data-ttu-id="20bb2-253">Stringa</span><span class="sxs-lookup"><span data-stu-id="20bb2-253">String</span></span> |
| <span data-ttu-id="20bb2-254">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="20bb2-254">**Possible values**</span></span> | <span data-ttu-id="20bb2-255">qualsiasi stringa</span><span class="sxs-lookup"><span data-stu-id="20bb2-255">any string</span></span> |
| <span data-ttu-id="20bb2-256">**Comments**</span><span class="sxs-lookup"><span data-stu-id="20bb2-256">**Comments**</span></span> | <span data-ttu-id="20bb2-257">Applicabile solo se *$type* *è excludedFileName*</span><span class="sxs-lookup"><span data-stu-id="20bb2-257">Applicable only if *$type* is *excludedFileName*</span></span> |

#### <a name="allowed-threats"></a><span data-ttu-id="20bb2-258">Minacce consentite</span><span class="sxs-lookup"><span data-stu-id="20bb2-258">Allowed threats</span></span>

<span data-ttu-id="20bb2-259">Specifica le minacce in base al nome che non sono bloccate da Defender per Endpoint su Mac.</span><span class="sxs-lookup"><span data-stu-id="20bb2-259">Specify threats by name that are not blocked by Defender for Endpoint on Mac.</span></span> <span data-ttu-id="20bb2-260">L'esecuzione di queste minacce sarà consentita.</span><span class="sxs-lookup"><span data-stu-id="20bb2-260">These threats will be allowed to run.</span></span>

|<span data-ttu-id="20bb2-261">Sezione</span><span class="sxs-lookup"><span data-stu-id="20bb2-261">Section</span></span>|<span data-ttu-id="20bb2-262">Valore</span><span class="sxs-lookup"><span data-stu-id="20bb2-262">Value</span></span>|
|:---|:---|
| <span data-ttu-id="20bb2-263">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="20bb2-263">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="20bb2-264">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="20bb2-264">**Key**</span></span> | <span data-ttu-id="20bb2-265">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="20bb2-265">allowedThreats</span></span> |
| <span data-ttu-id="20bb2-266">**Data type**</span><span class="sxs-lookup"><span data-stu-id="20bb2-266">**Data type**</span></span> | <span data-ttu-id="20bb2-267">Matrice di stringhe</span><span class="sxs-lookup"><span data-stu-id="20bb2-267">Array of strings</span></span> |

#### <a name="disallowed-threat-actions"></a><span data-ttu-id="20bb2-268">Azioni di minaccia non consentite</span><span class="sxs-lookup"><span data-stu-id="20bb2-268">Disallowed threat actions</span></span>

<span data-ttu-id="20bb2-269">Limita le azioni che l'utente locale di un dispositivo può intraprendere quando vengono rilevate minacce.</span><span class="sxs-lookup"><span data-stu-id="20bb2-269">Restricts the actions that the local user of a device can take when threats are detected.</span></span> <span data-ttu-id="20bb2-270">Le azioni incluse in questo elenco non vengono visualizzate nell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="20bb2-270">The actions included in this list are not displayed in the user interface.</span></span>

|<span data-ttu-id="20bb2-271">Sezione</span><span class="sxs-lookup"><span data-stu-id="20bb2-271">Section</span></span>|<span data-ttu-id="20bb2-272">Valore</span><span class="sxs-lookup"><span data-stu-id="20bb2-272">Value</span></span>|
|:---|:---|
| <span data-ttu-id="20bb2-273">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="20bb2-273">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="20bb2-274">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="20bb2-274">**Key**</span></span> | <span data-ttu-id="20bb2-275">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="20bb2-275">disallowedThreatActions</span></span> |
| <span data-ttu-id="20bb2-276">**Data type**</span><span class="sxs-lookup"><span data-stu-id="20bb2-276">**Data type**</span></span> | <span data-ttu-id="20bb2-277">Matrice di stringhe</span><span class="sxs-lookup"><span data-stu-id="20bb2-277">Array of strings</span></span> |
| <span data-ttu-id="20bb2-278">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="20bb2-278">**Possible values**</span></span> | <span data-ttu-id="20bb2-279">allow (impedisce agli utenti di consentire minacce)</span><span class="sxs-lookup"><span data-stu-id="20bb2-279">allow (restricts users from allowing threats)</span></span> <br/> <span data-ttu-id="20bb2-280">restore (impedisce agli utenti di ripristinare le minacce dalla quarantena)</span><span class="sxs-lookup"><span data-stu-id="20bb2-280">restore (restricts users from restoring threats from the quarantine)</span></span> |
| <span data-ttu-id="20bb2-281">**Comments**</span><span class="sxs-lookup"><span data-stu-id="20bb2-281">**Comments**</span></span> | <span data-ttu-id="20bb2-282">Disponibile in Microsoft Defender per Endpoint versione 100.83.73 o successiva.</span><span class="sxs-lookup"><span data-stu-id="20bb2-282">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="threat-type-settings"></a><span data-ttu-id="20bb2-283">Impostazioni del tipo di minaccia</span><span class="sxs-lookup"><span data-stu-id="20bb2-283">Threat type settings</span></span>

<span data-ttu-id="20bb2-284">Specifica come vengono gestiti determinati tipi di minacce da Microsoft Defender per Endpoint in macOS.</span><span class="sxs-lookup"><span data-stu-id="20bb2-284">Specify how certain threat types are handled by Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="20bb2-285">Sezione</span><span class="sxs-lookup"><span data-stu-id="20bb2-285">Section</span></span>|<span data-ttu-id="20bb2-286">Valore</span><span class="sxs-lookup"><span data-stu-id="20bb2-286">Value</span></span>|
|:---|:---|
| <span data-ttu-id="20bb2-287">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="20bb2-287">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="20bb2-288">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="20bb2-288">**Key**</span></span> | <span data-ttu-id="20bb2-289">threatTypeSettings</span><span class="sxs-lookup"><span data-stu-id="20bb2-289">threatTypeSettings</span></span> |
| <span data-ttu-id="20bb2-290">**Data type**</span><span class="sxs-lookup"><span data-stu-id="20bb2-290">**Data type**</span></span> | <span data-ttu-id="20bb2-291">Dizionario (preferenza annidata)</span><span class="sxs-lookup"><span data-stu-id="20bb2-291">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="20bb2-292">**Comments**</span><span class="sxs-lookup"><span data-stu-id="20bb2-292">**Comments**</span></span> | <span data-ttu-id="20bb2-293">Per una descrizione del contenuto del dizionario, vedi le sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="20bb2-293">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="threat-type"></a><span data-ttu-id="20bb2-294">Tipo di minaccia</span><span class="sxs-lookup"><span data-stu-id="20bb2-294">Threat type</span></span>

<span data-ttu-id="20bb2-295">Specificare i tipi di minaccia.</span><span class="sxs-lookup"><span data-stu-id="20bb2-295">Specify threat types.</span></span>

|<span data-ttu-id="20bb2-296">Sezione</span><span class="sxs-lookup"><span data-stu-id="20bb2-296">Section</span></span>|<span data-ttu-id="20bb2-297">Valore</span><span class="sxs-lookup"><span data-stu-id="20bb2-297">Value</span></span>|
|:---|:---|
| <span data-ttu-id="20bb2-298">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="20bb2-298">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="20bb2-299">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="20bb2-299">**Key**</span></span> | <span data-ttu-id="20bb2-300">chiave</span><span class="sxs-lookup"><span data-stu-id="20bb2-300">key</span></span> |
| <span data-ttu-id="20bb2-301">**Data type**</span><span class="sxs-lookup"><span data-stu-id="20bb2-301">**Data type**</span></span> | <span data-ttu-id="20bb2-302">Stringa</span><span class="sxs-lookup"><span data-stu-id="20bb2-302">String</span></span> |
| <span data-ttu-id="20bb2-303">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="20bb2-303">**Possible values**</span></span> | <span data-ttu-id="20bb2-304">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="20bb2-304">potentially_unwanted_application</span></span> <br/> <span data-ttu-id="20bb2-305">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="20bb2-305">archive_bomb</span></span> |

##### <a name="action-to-take"></a><span data-ttu-id="20bb2-306">Procedura da seguire</span><span class="sxs-lookup"><span data-stu-id="20bb2-306">Action to take</span></span>

<span data-ttu-id="20bb2-307">Specificare l'azione da eseguire quando viene rilevata una minaccia del tipo specificato nella sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="20bb2-307">Specify what action to take when a threat of the type specified in the preceding section is detected.</span></span> <span data-ttu-id="20bb2-308">Scegliere una delle seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="20bb2-308">Choose from the following options:</span></span>

- <span data-ttu-id="20bb2-309">**Controllo**: il dispositivo non è protetto da questo tipo di minaccia, ma viene registrata una voce relativa alla minaccia.</span><span class="sxs-lookup"><span data-stu-id="20bb2-309">**Audit**: your device is not protected against this type of threat, but an entry about the threat is logged.</span></span>
- <span data-ttu-id="20bb2-310">**Blocca**: il dispositivo è protetto da questo tipo di minaccia e si viene informati nell'interfaccia utente e nella console di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="20bb2-310">**Block**: your device is protected against this type of threat and you are notified in the user interface and the security console.</span></span>
- <span data-ttu-id="20bb2-311">**Disattivato:** il dispositivo non è protetto da questo tipo di minaccia e non viene registrato nulla.</span><span class="sxs-lookup"><span data-stu-id="20bb2-311">**Off**: your device is not protected against this type of threat and nothing is logged.</span></span>

|<span data-ttu-id="20bb2-312">Sezione</span><span class="sxs-lookup"><span data-stu-id="20bb2-312">Section</span></span>|<span data-ttu-id="20bb2-313">Valore</span><span class="sxs-lookup"><span data-stu-id="20bb2-313">Value</span></span>|
|:---|:---|
| <span data-ttu-id="20bb2-314">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="20bb2-314">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="20bb2-315">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="20bb2-315">**Key**</span></span> | <span data-ttu-id="20bb2-316">valore</span><span class="sxs-lookup"><span data-stu-id="20bb2-316">value</span></span> |
| <span data-ttu-id="20bb2-317">**Data type**</span><span class="sxs-lookup"><span data-stu-id="20bb2-317">**Data type**</span></span> | <span data-ttu-id="20bb2-318">Stringa</span><span class="sxs-lookup"><span data-stu-id="20bb2-318">String</span></span> |
| <span data-ttu-id="20bb2-319">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="20bb2-319">**Possible values**</span></span> | <span data-ttu-id="20bb2-320">audit (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="20bb2-320">audit (default)</span></span> <br/> <span data-ttu-id="20bb2-321">blocco</span><span class="sxs-lookup"><span data-stu-id="20bb2-321">block</span></span> <br/> <span data-ttu-id="20bb2-322">off</span><span class="sxs-lookup"><span data-stu-id="20bb2-322">off</span></span> |

#### <a name="threat-type-settings-merge-policy"></a><span data-ttu-id="20bb2-323">Criteri di unione delle impostazioni del tipo di minaccia</span><span class="sxs-lookup"><span data-stu-id="20bb2-323">Threat type settings merge policy</span></span>

<span data-ttu-id="20bb2-324">Specificare i criteri di unione per le impostazioni del tipo di minaccia.</span><span class="sxs-lookup"><span data-stu-id="20bb2-324">Specify the merge policy for threat type settings.</span></span> <span data-ttu-id="20bb2-325">Può essere una combinazione di impostazioni definite dall'amministratore e definite dall'utente ( ) o solo impostazioni definite `merge` dall'amministratore ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="20bb2-325">This can be a combination of administrator-defined and user-defined settings (`merge`) or only administrator-defined settings (`admin_only`).</span></span> <span data-ttu-id="20bb2-326">Questa impostazione può essere usata per impedire agli utenti locali di definire le proprie impostazioni per diversi tipi di minacce.</span><span class="sxs-lookup"><span data-stu-id="20bb2-326">This setting can be used to restrict local users from defining their own settings for different threat types.</span></span>

|<span data-ttu-id="20bb2-327">Sezione</span><span class="sxs-lookup"><span data-stu-id="20bb2-327">Section</span></span>|<span data-ttu-id="20bb2-328">Valore</span><span class="sxs-lookup"><span data-stu-id="20bb2-328">Value</span></span>|
|:---|:---|
| <span data-ttu-id="20bb2-329">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="20bb2-329">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="20bb2-330">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="20bb2-330">**Key**</span></span> | <span data-ttu-id="20bb2-331">threatTypeSettingsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="20bb2-331">threatTypeSettingsMergePolicy</span></span> |
| <span data-ttu-id="20bb2-332">**Data type**</span><span class="sxs-lookup"><span data-stu-id="20bb2-332">**Data type**</span></span> | <span data-ttu-id="20bb2-333">Stringa</span><span class="sxs-lookup"><span data-stu-id="20bb2-333">String</span></span> |
| <span data-ttu-id="20bb2-334">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="20bb2-334">**Possible values**</span></span> | <span data-ttu-id="20bb2-335">merge (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="20bb2-335">merge (default)</span></span> <br/> <span data-ttu-id="20bb2-336">admin_only</span><span class="sxs-lookup"><span data-stu-id="20bb2-336">admin_only</span></span> |
| <span data-ttu-id="20bb2-337">**Comments**</span><span class="sxs-lookup"><span data-stu-id="20bb2-337">**Comments**</span></span> | <span data-ttu-id="20bb2-338">Disponibile in Microsoft Defender per Endpoint versione 100.83.73 o successiva.</span><span class="sxs-lookup"><span data-stu-id="20bb2-338">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="antivirus-scan-history-retention-in-days"></a><span data-ttu-id="20bb2-339">Conservazione cronologia analisi antivirus (in giorni)</span><span class="sxs-lookup"><span data-stu-id="20bb2-339">Antivirus scan history retention (in days)</span></span>

<span data-ttu-id="20bb2-340">Specifica il numero di giorni in cui i risultati vengono conservati nella cronologia dell'analisi nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="20bb2-340">Specify the number of days that results are retained in the scan history on the device.</span></span> <span data-ttu-id="20bb2-341">I risultati dell'analisi precedente vengono rimossi dalla cronologia.</span><span class="sxs-lookup"><span data-stu-id="20bb2-341">Old scan results are removed from the history.</span></span> <span data-ttu-id="20bb2-342">Vecchi file in quarantena che vengono rimossi anche dal disco.</span><span class="sxs-lookup"><span data-stu-id="20bb2-342">Old quarantined files that are also removed from the disk.</span></span>

|<span data-ttu-id="20bb2-343">Sezione</span><span class="sxs-lookup"><span data-stu-id="20bb2-343">Section</span></span>|<span data-ttu-id="20bb2-344">Valore</span><span class="sxs-lookup"><span data-stu-id="20bb2-344">Value</span></span>|
|:---|:---|
| <span data-ttu-id="20bb2-345">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="20bb2-345">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="20bb2-346">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="20bb2-346">**Key**</span></span> | <span data-ttu-id="20bb2-347">scanResultsRetentionDays</span><span class="sxs-lookup"><span data-stu-id="20bb2-347">scanResultsRetentionDays</span></span> |
| <span data-ttu-id="20bb2-348">**Data type**</span><span class="sxs-lookup"><span data-stu-id="20bb2-348">**Data type**</span></span> | <span data-ttu-id="20bb2-349">Stringa</span><span class="sxs-lookup"><span data-stu-id="20bb2-349">String</span></span> |
| <span data-ttu-id="20bb2-350">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="20bb2-350">**Possible values**</span></span> | <span data-ttu-id="20bb2-351">90 (impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="20bb2-351">90 (default).</span></span> <span data-ttu-id="20bb2-352">I valori consentiti sono da 1 giorno a 180 giorni.</span><span class="sxs-lookup"><span data-stu-id="20bb2-352">Allowed values are from 1 day to 180 days.</span></span> |
| <span data-ttu-id="20bb2-353">**Comments**</span><span class="sxs-lookup"><span data-stu-id="20bb2-353">**Comments**</span></span> | <span data-ttu-id="20bb2-354">Disponibile in Microsoft Defender per Endpoint versione 101.07.23 o successiva.</span><span class="sxs-lookup"><span data-stu-id="20bb2-354">Available in Microsoft Defender for Endpoint version 101.07.23 or higher.</span></span> |

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a><span data-ttu-id="20bb2-355">Numero massimo di elementi nella cronologia dell'analisi antivirus</span><span class="sxs-lookup"><span data-stu-id="20bb2-355">Maximum number of items in the antivirus scan history</span></span>

<span data-ttu-id="20bb2-356">Specificare il numero massimo di voci da mantenere nella cronologia di analisi.</span><span class="sxs-lookup"><span data-stu-id="20bb2-356">Specify the maximum number of entries to keep in the scan history.</span></span> <span data-ttu-id="20bb2-357">Le voci includono tutte le analisi su richiesta eseguite in passato e tutti i rilevamenti antivirus.</span><span class="sxs-lookup"><span data-stu-id="20bb2-357">Entries include all on-demand scans performed in the past and all antivirus detections.</span></span>

|<span data-ttu-id="20bb2-358">Sezione</span><span class="sxs-lookup"><span data-stu-id="20bb2-358">Section</span></span>|<span data-ttu-id="20bb2-359">Valore</span><span class="sxs-lookup"><span data-stu-id="20bb2-359">Value</span></span>|
|:---|:---|
| <span data-ttu-id="20bb2-360">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="20bb2-360">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="20bb2-361">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="20bb2-361">**Key**</span></span> | <span data-ttu-id="20bb2-362">scanHistoryMaximumItems</span><span class="sxs-lookup"><span data-stu-id="20bb2-362">scanHistoryMaximumItems</span></span> |
| <span data-ttu-id="20bb2-363">**Data type**</span><span class="sxs-lookup"><span data-stu-id="20bb2-363">**Data type**</span></span> | <span data-ttu-id="20bb2-364">Stringa</span><span class="sxs-lookup"><span data-stu-id="20bb2-364">String</span></span> |
| <span data-ttu-id="20bb2-365">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="20bb2-365">**Possible values**</span></span> | <span data-ttu-id="20bb2-366">10000 (impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="20bb2-366">10000 (default).</span></span> <span data-ttu-id="20bb2-367">I valori consentiti sono da 5.000 elementi a 15.000 elementi.</span><span class="sxs-lookup"><span data-stu-id="20bb2-367">Allowed values are from 5000 items to 15000 items.</span></span> |
| <span data-ttu-id="20bb2-368">**Comments**</span><span class="sxs-lookup"><span data-stu-id="20bb2-368">**Comments**</span></span> | <span data-ttu-id="20bb2-369">Disponibile in Microsoft Defender per Endpoint versione 101.07.23 o successiva.</span><span class="sxs-lookup"><span data-stu-id="20bb2-369">Available in Microsoft Defender for Endpoint version 101.07.23 or higher.</span></span> |

### <a name="cloud-delivered-protection-preferences"></a><span data-ttu-id="20bb2-370">Preferenze di protezione per il cloud</span><span class="sxs-lookup"><span data-stu-id="20bb2-370">Cloud-delivered protection preferences</span></span>

<span data-ttu-id="20bb2-371">Configurare le funzionalità di protezione basata sul cloud di Microsoft Defender per Endpoint in macOS.</span><span class="sxs-lookup"><span data-stu-id="20bb2-371">Configure the cloud-driven protection features of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="20bb2-372">Sezione</span><span class="sxs-lookup"><span data-stu-id="20bb2-372">Section</span></span>|<span data-ttu-id="20bb2-373">Valore</span><span class="sxs-lookup"><span data-stu-id="20bb2-373">Value</span></span>|
|:---|:---|
| <span data-ttu-id="20bb2-374">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="20bb2-374">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="20bb2-375">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="20bb2-375">**Key**</span></span> | <span data-ttu-id="20bb2-376">cloudService</span><span class="sxs-lookup"><span data-stu-id="20bb2-376">cloudService</span></span> |
| <span data-ttu-id="20bb2-377">**Data type**</span><span class="sxs-lookup"><span data-stu-id="20bb2-377">**Data type**</span></span> | <span data-ttu-id="20bb2-378">Dizionario (preferenza annidata)</span><span class="sxs-lookup"><span data-stu-id="20bb2-378">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="20bb2-379">**Comments**</span><span class="sxs-lookup"><span data-stu-id="20bb2-379">**Comments**</span></span> | <span data-ttu-id="20bb2-380">Per una descrizione del contenuto del dizionario, vedi le sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="20bb2-380">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-cloud-delivered-protection"></a><span data-ttu-id="20bb2-381">Abilitare/disabilitare la protezione recapitata nel cloud</span><span class="sxs-lookup"><span data-stu-id="20bb2-381">Enable / disable cloud-delivered protection</span></span>

<span data-ttu-id="20bb2-382">Specificare se abilitare o meno la protezione recapitata nel cloud.</span><span class="sxs-lookup"><span data-stu-id="20bb2-382">Specify whether to enable cloud-delivered protection the device or not.</span></span> <span data-ttu-id="20bb2-383">Per migliorare la sicurezza dei servizi, è consigliabile mantenere attivata questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="20bb2-383">To improve the security of your services, we recommend keeping this feature turned on.</span></span>

|<span data-ttu-id="20bb2-384">Sezione</span><span class="sxs-lookup"><span data-stu-id="20bb2-384">Section</span></span>|<span data-ttu-id="20bb2-385">Valore</span><span class="sxs-lookup"><span data-stu-id="20bb2-385">Value</span></span>|
|:---|:---|
| <span data-ttu-id="20bb2-386">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="20bb2-386">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="20bb2-387">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="20bb2-387">**Key**</span></span> | <span data-ttu-id="20bb2-388">abilitati</span><span class="sxs-lookup"><span data-stu-id="20bb2-388">enabled</span></span> |
| <span data-ttu-id="20bb2-389">**Data type**</span><span class="sxs-lookup"><span data-stu-id="20bb2-389">**Data type**</span></span> | <span data-ttu-id="20bb2-390">Booleano</span><span class="sxs-lookup"><span data-stu-id="20bb2-390">Boolean</span></span> |
| <span data-ttu-id="20bb2-391">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="20bb2-391">**Possible values**</span></span> | <span data-ttu-id="20bb2-392">true (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="20bb2-392">true (default)</span></span> <br/> <span data-ttu-id="20bb2-393">false</span><span class="sxs-lookup"><span data-stu-id="20bb2-393">false</span></span> |

#### <a name="diagnostic-collection-level"></a><span data-ttu-id="20bb2-394">Livello raccolta diagnostica</span><span class="sxs-lookup"><span data-stu-id="20bb2-394">Diagnostic collection level</span></span>

<span data-ttu-id="20bb2-395">I dati di diagnostica vengono usati per mantenere Microsoft Defender for Endpoint sicuro e aggiornato, rilevare, diagnosticare e risolvere i problemi e apportare miglioramenti al prodotto.</span><span class="sxs-lookup"><span data-stu-id="20bb2-395">Diagnostic data is used to keep Microsoft Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span> <span data-ttu-id="20bb2-396">Questa impostazione determina il livello di diagnostica inviato da Microsoft Defender per Endpoint a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="20bb2-396">This setting determines the level of diagnostics sent by Microsoft Defender for Endpoint to Microsoft.</span></span>

|<span data-ttu-id="20bb2-397">Sezione</span><span class="sxs-lookup"><span data-stu-id="20bb2-397">Section</span></span>|<span data-ttu-id="20bb2-398">Valore</span><span class="sxs-lookup"><span data-stu-id="20bb2-398">Value</span></span>|
|:---|:---|
| <span data-ttu-id="20bb2-399">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="20bb2-399">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="20bb2-400">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="20bb2-400">**Key**</span></span> | <span data-ttu-id="20bb2-401">diagnosticLevel</span><span class="sxs-lookup"><span data-stu-id="20bb2-401">diagnosticLevel</span></span> |
| <span data-ttu-id="20bb2-402">**Data type**</span><span class="sxs-lookup"><span data-stu-id="20bb2-402">**Data type**</span></span> | <span data-ttu-id="20bb2-403">Stringa</span><span class="sxs-lookup"><span data-stu-id="20bb2-403">String</span></span> |
| <span data-ttu-id="20bb2-404">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="20bb2-404">**Possible values**</span></span> | <span data-ttu-id="20bb2-405">facoltativo (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="20bb2-405">optional (default)</span></span> <br/> <span data-ttu-id="20bb2-406">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="20bb2-406">required</span></span> |

#### <a name="enable--disable-automatic-sample-submissions"></a><span data-ttu-id="20bb2-407">Abilitare/disabilitare gli invii di esempio automatici</span><span class="sxs-lookup"><span data-stu-id="20bb2-407">Enable / disable automatic sample submissions</span></span>

<span data-ttu-id="20bb2-408">Determina se i campioni sospetti (che potrebbero contenere minacce) vengono inviati a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="20bb2-408">Determines whether suspicious samples (that are likely to contain threats) are sent to Microsoft.</span></span> <span data-ttu-id="20bb2-409">Viene richiesto se è probabile che il file inviato contenga informazioni personali.</span><span class="sxs-lookup"><span data-stu-id="20bb2-409">You are prompted if the submitted file is likely to contain personal information.</span></span>

|<span data-ttu-id="20bb2-410">Sezione</span><span class="sxs-lookup"><span data-stu-id="20bb2-410">Section</span></span>|<span data-ttu-id="20bb2-411">Valore</span><span class="sxs-lookup"><span data-stu-id="20bb2-411">Value</span></span>|
|:---|:---|
| <span data-ttu-id="20bb2-412">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="20bb2-412">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="20bb2-413">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="20bb2-413">**Key**</span></span> | <span data-ttu-id="20bb2-414">automaticSampleSubmission</span><span class="sxs-lookup"><span data-stu-id="20bb2-414">automaticSampleSubmission</span></span> |
| <span data-ttu-id="20bb2-415">**Data type**</span><span class="sxs-lookup"><span data-stu-id="20bb2-415">**Data type**</span></span> | <span data-ttu-id="20bb2-416">Booleano</span><span class="sxs-lookup"><span data-stu-id="20bb2-416">Boolean</span></span> |
| <span data-ttu-id="20bb2-417">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="20bb2-417">**Possible values**</span></span> | <span data-ttu-id="20bb2-418">true (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="20bb2-418">true (default)</span></span> <br/> <span data-ttu-id="20bb2-419">false</span><span class="sxs-lookup"><span data-stu-id="20bb2-419">false</span></span> |

#### <a name="enable--disable-automatic-security-intelligence-updates"></a><span data-ttu-id="20bb2-420">Abilitare/disabilitare gli aggiornamenti automatici delle funzionalità di intelligence per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="20bb2-420">Enable / disable automatic security intelligence updates</span></span>

<span data-ttu-id="20bb2-421">Determina se gli aggiornamenti delle funzionalità di intelligence per la sicurezza vengono installati automaticamente:</span><span class="sxs-lookup"><span data-stu-id="20bb2-421">Determines whether security intelligence updates are installed automatically:</span></span>

|<span data-ttu-id="20bb2-422">Sezione</span><span class="sxs-lookup"><span data-stu-id="20bb2-422">Section</span></span>|<span data-ttu-id="20bb2-423">Valore</span><span class="sxs-lookup"><span data-stu-id="20bb2-423">Value</span></span>|
|:---|:---|
| <span data-ttu-id="20bb2-424">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="20bb2-424">**Key**</span></span> | <span data-ttu-id="20bb2-425">automaticDefinitionUpdateEnabled</span><span class="sxs-lookup"><span data-stu-id="20bb2-425">automaticDefinitionUpdateEnabled</span></span> |
| <span data-ttu-id="20bb2-426">**Data type**</span><span class="sxs-lookup"><span data-stu-id="20bb2-426">**Data type**</span></span> | <span data-ttu-id="20bb2-427">Booleano</span><span class="sxs-lookup"><span data-stu-id="20bb2-427">Boolean</span></span> |
| <span data-ttu-id="20bb2-428">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="20bb2-428">**Possible values**</span></span> | <span data-ttu-id="20bb2-429">true (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="20bb2-429">true (default)</span></span> <br/> <span data-ttu-id="20bb2-430">false</span><span class="sxs-lookup"><span data-stu-id="20bb2-430">false</span></span> |

### <a name="user-interface-preferences"></a><span data-ttu-id="20bb2-431">Preferenze dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="20bb2-431">User interface preferences</span></span>

<span data-ttu-id="20bb2-432">Gestire le preferenze per l'interfaccia utente di Microsoft Defender per Endpoint in macOS.</span><span class="sxs-lookup"><span data-stu-id="20bb2-432">Manage the preferences for the user interface of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="20bb2-433">Sezione</span><span class="sxs-lookup"><span data-stu-id="20bb2-433">Section</span></span>|<span data-ttu-id="20bb2-434">Valore</span><span class="sxs-lookup"><span data-stu-id="20bb2-434">Value</span></span>|
|:---|:---|
| <span data-ttu-id="20bb2-435">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="20bb2-435">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="20bb2-436">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="20bb2-436">**Key**</span></span> | <span data-ttu-id="20bb2-437">userInterface</span><span class="sxs-lookup"><span data-stu-id="20bb2-437">userInterface</span></span> |
| <span data-ttu-id="20bb2-438">**Data type**</span><span class="sxs-lookup"><span data-stu-id="20bb2-438">**Data type**</span></span> | <span data-ttu-id="20bb2-439">Dizionario (preferenza annidata)</span><span class="sxs-lookup"><span data-stu-id="20bb2-439">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="20bb2-440">**Comments**</span><span class="sxs-lookup"><span data-stu-id="20bb2-440">**Comments**</span></span> | <span data-ttu-id="20bb2-441">Per una descrizione del contenuto del dizionario, vedi le sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="20bb2-441">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="show--hide-status-menu-icon"></a><span data-ttu-id="20bb2-442">Mostra/nascondi icona del menu di stato</span><span class="sxs-lookup"><span data-stu-id="20bb2-442">Show / hide status menu icon</span></span>

<span data-ttu-id="20bb2-443">Specifica se mostrare o nascondere l'icona del menu di stato nell'angolo in alto a destra dello schermo.</span><span class="sxs-lookup"><span data-stu-id="20bb2-443">Specify whether to show or hide the status menu icon in the top-right corner of the screen.</span></span>

|<span data-ttu-id="20bb2-444">Sezione</span><span class="sxs-lookup"><span data-stu-id="20bb2-444">Section</span></span>|<span data-ttu-id="20bb2-445">Valore</span><span class="sxs-lookup"><span data-stu-id="20bb2-445">Value</span></span>|
|:---|:---|
| <span data-ttu-id="20bb2-446">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="20bb2-446">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="20bb2-447">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="20bb2-447">**Key**</span></span> | <span data-ttu-id="20bb2-448">hideStatusMenuIcon</span><span class="sxs-lookup"><span data-stu-id="20bb2-448">hideStatusMenuIcon</span></span> |
| <span data-ttu-id="20bb2-449">**Data type**</span><span class="sxs-lookup"><span data-stu-id="20bb2-449">**Data type**</span></span> | <span data-ttu-id="20bb2-450">Booleano</span><span class="sxs-lookup"><span data-stu-id="20bb2-450">Boolean</span></span> |
| <span data-ttu-id="20bb2-451">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="20bb2-451">**Possible values**</span></span> | <span data-ttu-id="20bb2-452">false (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="20bb2-452">false (default)</span></span> <br/> <span data-ttu-id="20bb2-453">true</span><span class="sxs-lookup"><span data-stu-id="20bb2-453">true</span></span> |

#### <a name="show--hide-option-to-send-feedback"></a><span data-ttu-id="20bb2-454">Opzione Mostra/Nascondi per inviare commenti e suggerimenti</span><span class="sxs-lookup"><span data-stu-id="20bb2-454">Show / hide option to send feedback</span></span>

<span data-ttu-id="20bb2-455">Specificare se gli utenti possono inviare commenti e suggerimenti a Microsoft andando a `Help`  >  `Send Feedback` .</span><span class="sxs-lookup"><span data-stu-id="20bb2-455">Specify whether users can submit feedback to Microsoft by going to `Help` > `Send Feedback`.</span></span>

|<span data-ttu-id="20bb2-456">Sezione</span><span class="sxs-lookup"><span data-stu-id="20bb2-456">Section</span></span>|<span data-ttu-id="20bb2-457">Valore</span><span class="sxs-lookup"><span data-stu-id="20bb2-457">Value</span></span>|
|:---|:---|
| <span data-ttu-id="20bb2-458">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="20bb2-458">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="20bb2-459">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="20bb2-459">**Key**</span></span> | <span data-ttu-id="20bb2-460">userInitiatedFeedback</span><span class="sxs-lookup"><span data-stu-id="20bb2-460">userInitiatedFeedback</span></span> |
| <span data-ttu-id="20bb2-461">**Data type**</span><span class="sxs-lookup"><span data-stu-id="20bb2-461">**Data type**</span></span> | <span data-ttu-id="20bb2-462">Stringa</span><span class="sxs-lookup"><span data-stu-id="20bb2-462">String</span></span> |
| <span data-ttu-id="20bb2-463">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="20bb2-463">**Possible values**</span></span> | <span data-ttu-id="20bb2-464">enabled (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="20bb2-464">enabled (default)</span></span> <br/> <span data-ttu-id="20bb2-465">disabilitati</span><span class="sxs-lookup"><span data-stu-id="20bb2-465">disabled</span></span> |
| <span data-ttu-id="20bb2-466">**Comments**</span><span class="sxs-lookup"><span data-stu-id="20bb2-466">**Comments**</span></span> | <span data-ttu-id="20bb2-467">Disponibile in Microsoft Defender per Endpoint versione 101.19.61 o successiva.</span><span class="sxs-lookup"><span data-stu-id="20bb2-467">Available in Microsoft Defender for Endpoint version 101.19.61 or higher.</span></span> |

### <a name="endpoint-detection-and-response-preferences"></a><span data-ttu-id="20bb2-468">Preferenze di risposta e rilevamento degli endpoint</span><span class="sxs-lookup"><span data-stu-id="20bb2-468">Endpoint detection and response preferences</span></span>

<span data-ttu-id="20bb2-469">Gestire le preferenze del componente di rilevamento e risposta degli endpoint (EDR) di Microsoft Defender per Endpoint in macOS.</span><span class="sxs-lookup"><span data-stu-id="20bb2-469">Manage the preferences of the endpoint detection and response (EDR) component of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="20bb2-470">Sezione</span><span class="sxs-lookup"><span data-stu-id="20bb2-470">Section</span></span>|<span data-ttu-id="20bb2-471">Valore</span><span class="sxs-lookup"><span data-stu-id="20bb2-471">Value</span></span>|
|:---|:---|
| <span data-ttu-id="20bb2-472">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="20bb2-472">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="20bb2-473">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="20bb2-473">**Key**</span></span> | <span data-ttu-id="20bb2-474">edr</span><span class="sxs-lookup"><span data-stu-id="20bb2-474">edr</span></span> |
| <span data-ttu-id="20bb2-475">**Data type**</span><span class="sxs-lookup"><span data-stu-id="20bb2-475">**Data type**</span></span> | <span data-ttu-id="20bb2-476">Dizionario (preferenza annidata)</span><span class="sxs-lookup"><span data-stu-id="20bb2-476">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="20bb2-477">**Comments**</span><span class="sxs-lookup"><span data-stu-id="20bb2-477">**Comments**</span></span> | <span data-ttu-id="20bb2-478">Per una descrizione del contenuto del dizionario, vedi le sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="20bb2-478">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="device-tags"></a><span data-ttu-id="20bb2-479">Tag dispositivo</span><span class="sxs-lookup"><span data-stu-id="20bb2-479">Device tags</span></span>

<span data-ttu-id="20bb2-480">Specificare un nome di tag e il relativo valore.</span><span class="sxs-lookup"><span data-stu-id="20bb2-480">Specify a tag name and its value.</span></span> 

- <span data-ttu-id="20bb2-481">Il tag GROUP contrassegna il dispositivo con il valore specificato.</span><span class="sxs-lookup"><span data-stu-id="20bb2-481">The GROUP tag, tags the device with the specified value.</span></span> <span data-ttu-id="20bb2-482">Il tag si riflette nel portale nella pagina del dispositivo e può essere usato per filtrare e raggruppare i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="20bb2-482">The tag is reflected in the portal under the device page and can be used for filtering and grouping devices.</span></span>

|<span data-ttu-id="20bb2-483">Sezione</span><span class="sxs-lookup"><span data-stu-id="20bb2-483">Section</span></span>|<span data-ttu-id="20bb2-484">Valore</span><span class="sxs-lookup"><span data-stu-id="20bb2-484">Value</span></span>|
|:---|:---|
| <span data-ttu-id="20bb2-485">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="20bb2-485">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="20bb2-486">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="20bb2-486">**Key**</span></span> | <span data-ttu-id="20bb2-487">tag</span><span class="sxs-lookup"><span data-stu-id="20bb2-487">tags</span></span> |
| <span data-ttu-id="20bb2-488">**Data type**</span><span class="sxs-lookup"><span data-stu-id="20bb2-488">**Data type**</span></span> | <span data-ttu-id="20bb2-489">Dizionario (preferenza annidata)</span><span class="sxs-lookup"><span data-stu-id="20bb2-489">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="20bb2-490">**Comments**</span><span class="sxs-lookup"><span data-stu-id="20bb2-490">**Comments**</span></span> | <span data-ttu-id="20bb2-491">Per una descrizione del contenuto del dizionario, vedi le sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="20bb2-491">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="type-of-tag"></a><span data-ttu-id="20bb2-492">Tipo di tag</span><span class="sxs-lookup"><span data-stu-id="20bb2-492">Type of tag</span></span>

<span data-ttu-id="20bb2-493">Specifica il tipo di tag</span><span class="sxs-lookup"><span data-stu-id="20bb2-493">Specifies the type of tag</span></span>

|<span data-ttu-id="20bb2-494">Sezione</span><span class="sxs-lookup"><span data-stu-id="20bb2-494">Section</span></span>|<span data-ttu-id="20bb2-495">Valore</span><span class="sxs-lookup"><span data-stu-id="20bb2-495">Value</span></span>|
|:---|:---|
| <span data-ttu-id="20bb2-496">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="20bb2-496">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="20bb2-497">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="20bb2-497">**Key**</span></span> | <span data-ttu-id="20bb2-498">chiave</span><span class="sxs-lookup"><span data-stu-id="20bb2-498">key</span></span> |
| <span data-ttu-id="20bb2-499">**Data type**</span><span class="sxs-lookup"><span data-stu-id="20bb2-499">**Data type**</span></span> | <span data-ttu-id="20bb2-500">Stringa</span><span class="sxs-lookup"><span data-stu-id="20bb2-500">String</span></span> |
| <span data-ttu-id="20bb2-501">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="20bb2-501">**Possible values**</span></span> | `GROUP` |

##### <a name="value-of-tag"></a><span data-ttu-id="20bb2-502">Valore del tag</span><span class="sxs-lookup"><span data-stu-id="20bb2-502">Value of tag</span></span>

<span data-ttu-id="20bb2-503">Specifica il valore del tag</span><span class="sxs-lookup"><span data-stu-id="20bb2-503">Specifies the value of tag</span></span>

|<span data-ttu-id="20bb2-504">Sezione</span><span class="sxs-lookup"><span data-stu-id="20bb2-504">Section</span></span>|<span data-ttu-id="20bb2-505">Valore</span><span class="sxs-lookup"><span data-stu-id="20bb2-505">Value</span></span>|
|:---|:---|
| <span data-ttu-id="20bb2-506">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="20bb2-506">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="20bb2-507">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="20bb2-507">**Key**</span></span> | <span data-ttu-id="20bb2-508">valore</span><span class="sxs-lookup"><span data-stu-id="20bb2-508">value</span></span> |
| <span data-ttu-id="20bb2-509">**Data type**</span><span class="sxs-lookup"><span data-stu-id="20bb2-509">**Data type**</span></span> | <span data-ttu-id="20bb2-510">Stringa</span><span class="sxs-lookup"><span data-stu-id="20bb2-510">String</span></span> |
| <span data-ttu-id="20bb2-511">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="20bb2-511">**Possible values**</span></span> | <span data-ttu-id="20bb2-512">qualsiasi stringa</span><span class="sxs-lookup"><span data-stu-id="20bb2-512">any string</span></span> |

> [!IMPORTANT]  
> - <span data-ttu-id="20bb2-513">È possibile impostare un solo valore per ogni tipo di tag.</span><span class="sxs-lookup"><span data-stu-id="20bb2-513">Only one value per tag type can be set.</span></span>
> - <span data-ttu-id="20bb2-514">Il tipo di tag è univoco e non deve essere ripetuto nello stesso profilo di configurazione.</span><span class="sxs-lookup"><span data-stu-id="20bb2-514">Type of tags are unique, and should not be repeated in the same configuration profile.</span></span>

## <a name="recommended-configuration-profile"></a><span data-ttu-id="20bb2-515">Profilo di configurazione consigliato</span><span class="sxs-lookup"><span data-stu-id="20bb2-515">Recommended configuration profile</span></span>

<span data-ttu-id="20bb2-516">Per iniziare, ti consigliamo la configurazione seguente per l'azienda per sfruttare tutte le funzionalità di protezione fornite da Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="20bb2-516">To get started, we recommend the following configuration for your enterprise to take advantage of all protection features that Microsoft Defender for Endpoint provides.</span></span>

<span data-ttu-id="20bb2-517">Il profilo di configurazione seguente (o, nel caso di JAMF, un elenco di proprietà che potrebbe essere caricato nel profilo di configurazione delle impostazioni personalizzate) sarà:</span><span class="sxs-lookup"><span data-stu-id="20bb2-517">The following configuration profile (or, in case of JAMF, a property list that could be uploaded into the custom settings configuration profile) will:</span></span>
- <span data-ttu-id="20bb2-518">Abilitare la protezione in tempo reale (RTP)</span><span class="sxs-lookup"><span data-stu-id="20bb2-518">Enable real-time protection (RTP)</span></span>
- <span data-ttu-id="20bb2-519">Specificare la modalità di gestione dei seguenti tipi di minacce:</span><span class="sxs-lookup"><span data-stu-id="20bb2-519">Specify how the following threat types are handled:</span></span>
  - <span data-ttu-id="20bb2-520">**Le applicazioni potenzialmente indesiderate sono** bloccate</span><span class="sxs-lookup"><span data-stu-id="20bb2-520">**Potentially unwanted applications (PUA)** are blocked</span></span>
  - <span data-ttu-id="20bb2-521">**Le bombe di** archiviazione (file con una velocità di compressione elevata) vengono verificate in Microsoft Defender per i log degli endpoint</span><span class="sxs-lookup"><span data-stu-id="20bb2-521">**Archive bombs** (file with a high compression rate) are audited to Microsoft Defender for Endpoint logs</span></span>
- <span data-ttu-id="20bb2-522">Abilitare gli aggiornamenti automatici delle funzionalità di intelligence per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="20bb2-522">Enable automatic security intelligence updates</span></span>
- <span data-ttu-id="20bb2-523">Abilitare la protezione basata sul cloud</span><span class="sxs-lookup"><span data-stu-id="20bb2-523">Enable cloud-delivered protection</span></span>
- <span data-ttu-id="20bb2-524">Abilitare l'invio automatico di esempi</span><span class="sxs-lookup"><span data-stu-id="20bb2-524">Enable automatic sample submission</span></span>

### <a name="property-list-for-jamf-configuration-profile"></a><span data-ttu-id="20bb2-525">Elenco delle proprietà per il profilo di configurazione JAMF</span><span class="sxs-lookup"><span data-stu-id="20bb2-525">Property list for JAMF configuration profile</span></span>

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

### <a name="intune-profile"></a><span data-ttu-id="20bb2-526">Profilo intune</span><span class="sxs-lookup"><span data-stu-id="20bb2-526">Intune profile</span></span>

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

## <a name="full-configuration-profile-example"></a><span data-ttu-id="20bb2-527">Esempio di profilo di configurazione completo</span><span class="sxs-lookup"><span data-stu-id="20bb2-527">Full configuration profile example</span></span>

<span data-ttu-id="20bb2-528">I modelli seguenti contengono voci per tutte le impostazioni descritte in questo documento e possono essere usati per scenari più avanzati in cui si desidera un maggiore controllo su Microsoft Defender for Endpoint in macOS.</span><span class="sxs-lookup"><span data-stu-id="20bb2-528">The following templates contain entries for all settings described in this document and can be used for more advanced scenarios where you want more control over Microsoft Defender for Endpoint on macOS.</span></span>

### <a name="property-list-for-jamf-configuration-profile"></a><span data-ttu-id="20bb2-529">Elenco delle proprietà per il profilo di configurazione JAMF</span><span class="sxs-lookup"><span data-stu-id="20bb2-529">Property list for JAMF configuration profile</span></span>

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

### <a name="intune-profile"></a><span data-ttu-id="20bb2-530">Profilo intune</span><span class="sxs-lookup"><span data-stu-id="20bb2-530">Intune profile</span></span>

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

## <a name="property-list-validation"></a><span data-ttu-id="20bb2-531">Convalida elenco proprietà</span><span class="sxs-lookup"><span data-stu-id="20bb2-531">Property list validation</span></span>

<span data-ttu-id="20bb2-532">L'elenco delle proprietà deve essere un file *plist* valido.</span><span class="sxs-lookup"><span data-stu-id="20bb2-532">The property list must be a valid *.plist* file.</span></span> <span data-ttu-id="20bb2-533">Questa operazione può essere verificata eseguendo:</span><span class="sxs-lookup"><span data-stu-id="20bb2-533">This can be checked by executing:</span></span>

```bash
plutil -lint com.microsoft.wdav.plist
```
```Output
com.microsoft.wdav.plist: OK
```

<span data-ttu-id="20bb2-534">Se il file è ben formato, il comando precedente restituisce un `OK` codice di uscita di `0` .</span><span class="sxs-lookup"><span data-stu-id="20bb2-534">If the file is well-formed, the above command outputs `OK` and returns an exit code of `0`.</span></span> <span data-ttu-id="20bb2-535">In caso contrario, viene visualizzato un errore che descrive il problema e il comando restituisce un codice di uscita di `1` .</span><span class="sxs-lookup"><span data-stu-id="20bb2-535">Otherwise, an error that describes the issue is displayed and the command returns an exit code of `1`.</span></span>

## <a name="configuration-profile-deployment"></a><span data-ttu-id="20bb2-536">Distribuzione dei profili di configurazione</span><span class="sxs-lookup"><span data-stu-id="20bb2-536">Configuration profile deployment</span></span>

<span data-ttu-id="20bb2-537">Dopo aver creato il profilo di configurazione per l'organizzazione, è possibile distribuirlo tramite la console di gestione in uso.</span><span class="sxs-lookup"><span data-stu-id="20bb2-537">Once you've built the configuration profile for your enterprise, you can deploy it through the management console that your enterprise is using.</span></span> <span data-ttu-id="20bb2-538">Le sezioni seguenti forniscono istruzioni su come distribuire questo profilo usando JAMF e Intune.</span><span class="sxs-lookup"><span data-stu-id="20bb2-538">The following sections provide instructions on how to deploy this profile using JAMF and Intune.</span></span>

### <a name="jamf-deployment"></a><span data-ttu-id="20bb2-539">Distribuzione JAMF</span><span class="sxs-lookup"><span data-stu-id="20bb2-539">JAMF deployment</span></span>

<span data-ttu-id="20bb2-540">Dalla console JAMF apri **Profili** di configurazione computer, passa al profilo di configurazione che vuoi usare, quindi  >  seleziona **Impostazioni personalizzate.**</span><span class="sxs-lookup"><span data-stu-id="20bb2-540">From the JAMF console, open **Computers** > **Configuration Profiles**, navigate to the configuration profile you'd like to use, then select **Custom Settings**.</span></span> <span data-ttu-id="20bb2-541">Crea una voce con `com.microsoft.wdav` come dominio di preferenza e carica il file *plist* prodotto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="20bb2-541">Create an entry with `com.microsoft.wdav` as the preference domain and upload the *.plist* produced earlier.</span></span>

>[!CAUTION]
><span data-ttu-id="20bb2-542">È necessario immettere il dominio di preferenza corretto ( ); in caso contrario, le preferenze non verranno `com.microsoft.wdav` riconosciute da Microsoft Defender per Endpoint.</span><span class="sxs-lookup"><span data-stu-id="20bb2-542">You must enter the correct preference domain (`com.microsoft.wdav`); otherwise, the preferences will not be recognized by Microsoft Defender for Endpoint.</span></span>

### <a name="intune-deployment"></a><span data-ttu-id="20bb2-543">Distribuzione di Intune</span><span class="sxs-lookup"><span data-stu-id="20bb2-543">Intune deployment</span></span>

1. <span data-ttu-id="20bb2-544">Aprire **Gestisci**  >  **configurazione dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="20bb2-544">Open **Manage** > **Device configuration**.</span></span> <span data-ttu-id="20bb2-545">Selezionare **Gestisci**  >  **profili**  >  **Crea profilo**.</span><span class="sxs-lookup"><span data-stu-id="20bb2-545">Select **Manage** > **Profiles** > **Create Profile**.</span></span>

2. <span data-ttu-id="20bb2-546">Scegliere un nome per il profilo.</span><span class="sxs-lookup"><span data-stu-id="20bb2-546">Choose a name for the profile.</span></span> <span data-ttu-id="20bb2-547">Modificare **Platform=macOS** in **Profile type=Custom**.</span><span class="sxs-lookup"><span data-stu-id="20bb2-547">Change **Platform=macOS** to **Profile type=Custom**.</span></span> <span data-ttu-id="20bb2-548">Selezionare Configura.</span><span class="sxs-lookup"><span data-stu-id="20bb2-548">Select Configure.</span></span>

3. <span data-ttu-id="20bb2-549">Salvare il file plist prodotto in precedenza come `com.microsoft.wdav.xml` .</span><span class="sxs-lookup"><span data-stu-id="20bb2-549">Save the .plist produced earlier as `com.microsoft.wdav.xml`.</span></span>

4. <span data-ttu-id="20bb2-550">Immettere `com.microsoft.wdav` come nome del profilo di configurazione **personalizzato**.</span><span class="sxs-lookup"><span data-stu-id="20bb2-550">Enter `com.microsoft.wdav` as the **custom configuration profile name**.</span></span>

5. <span data-ttu-id="20bb2-551">Apri il profilo di configurazione e carica il `com.microsoft.wdav.xml` file.</span><span class="sxs-lookup"><span data-stu-id="20bb2-551">Open the configuration profile and upload the `com.microsoft.wdav.xml` file.</span></span> <span data-ttu-id="20bb2-552">Questo file è stato creato nel passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="20bb2-552">(This file was created in step 3.)</span></span>

6. <span data-ttu-id="20bb2-553">Seleziona **OK**.</span><span class="sxs-lookup"><span data-stu-id="20bb2-553">Select **OK**.</span></span>

7. <span data-ttu-id="20bb2-554">Selezionare **Gestisci**  >  **assegnazioni**.</span><span class="sxs-lookup"><span data-stu-id="20bb2-554">Select **Manage** > **Assignments**.</span></span> <span data-ttu-id="20bb2-555">Nella scheda **Includi** seleziona **Assegna a tutti gli utenti & Tutti i dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="20bb2-555">In the **Include** tab, select **Assign to All Users & All devices**.</span></span>

>[!CAUTION]
><span data-ttu-id="20bb2-556">È necessario immettere il nome del profilo di configurazione personalizzato corretto. in caso contrario, queste preferenze non verranno riconosciute da Microsoft Defender per Endpoint.</span><span class="sxs-lookup"><span data-stu-id="20bb2-556">You must enter the correct custom configuration profile name; otherwise, these preferences will not be recognized by Microsoft Defender for Endpoint.</span></span>

## <a name="resources"></a><span data-ttu-id="20bb2-557">Risorse</span><span class="sxs-lookup"><span data-stu-id="20bb2-557">Resources</span></span>

- [<span data-ttu-id="20bb2-558">Informazioni di riferimento sui profili di configurazione (documentazione per sviluppatori Apple)</span><span class="sxs-lookup"><span data-stu-id="20bb2-558">Configuration Profile Reference (Apple developer documentation)</span></span>](https://developer.apple.com/business/documentation/Configuration-Profile-Reference.pdf)
