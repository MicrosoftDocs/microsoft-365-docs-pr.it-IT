---
title: Impostare le preferenze per Microsoft Defender per Endpoint per Mac
description: Configurare Microsoft Defender per Endpoint per Mac nelle organizzazioni aziendali.
keywords: microsoft, defender, atp, mac, gestione, preferenze, enterprise, intune, jamf, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: d2bea469031e2c5932e859fbad7d442ebe4d34ed
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2021
ms.locfileid: "51860924"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="1c923-104">Impostare le preferenze per Microsoft Defender per Endpoint in macOS</span><span class="sxs-lookup"><span data-stu-id="1c923-104">Set preferences for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="1c923-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="1c923-105">**Applies to:**</span></span>

- [<span data-ttu-id="1c923-106">Microsoft Defender per endpoint su macOS</span><span class="sxs-lookup"><span data-stu-id="1c923-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)

>[!IMPORTANT]
><span data-ttu-id="1c923-107">Questo articolo contiene istruzioni su come impostare le preferenze per Microsoft Defender per Endpoint in macOS nelle organizzazioni aziendali.</span><span class="sxs-lookup"><span data-stu-id="1c923-107">This article contains instructions for how to set preferences for Microsoft Defender for Endpoint on macOS in enterprise organizations.</span></span> <span data-ttu-id="1c923-108">Per configurare Microsoft Defender per Endpoint in macOS tramite l'interfaccia della riga di comando, vedi [Risorse](mac-resources.md#configuring-from-the-command-line).</span><span class="sxs-lookup"><span data-stu-id="1c923-108">To configure Microsoft Defender for Endpoint on macOS using the command-line interface, see [Resources](mac-resources.md#configuring-from-the-command-line).</span></span>

## <a name="summary"></a><span data-ttu-id="1c923-109">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="1c923-109">Summary</span></span>

<span data-ttu-id="1c923-110">Nelle organizzazioni aziendali, Microsoft Defender for Endpoint in macOS può essere gestito tramite un profilo di configurazione distribuito utilizzando uno dei diversi strumenti di gestione.</span><span class="sxs-lookup"><span data-stu-id="1c923-110">In enterprise organizations, Microsoft Defender for Endpoint on macOS can be managed through a configuration profile that is deployed by using one of several management tools.</span></span> <span data-ttu-id="1c923-111">Le preferenze gestite dal team delle operazioni di sicurezza hanno la precedenza sulle preferenze impostate localmente nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1c923-111">Preferences that are managed by your security operations team take precedence over preferences that are set locally on the device.</span></span> <span data-ttu-id="1c923-112">La modifica delle preferenze impostate tramite il profilo di configurazione richiede privilegi inoltrati e non è disponibile per gli utenti senza autorizzazioni amministrative.</span><span class="sxs-lookup"><span data-stu-id="1c923-112">Changing the preferences that are set through the configuration profile requires escalated privileges and is not available for users without administrative permissions.</span></span>

<span data-ttu-id="1c923-113">Questo articolo descrive la struttura del profilo di configurazione, include un profilo consigliato che puoi usare per iniziare e fornisce istruzioni su come distribuire il profilo.</span><span class="sxs-lookup"><span data-stu-id="1c923-113">This article describes the structure of the configuration profile, includes a recommended profile that you can use to get started, and provides instructions on how to deploy the profile.</span></span>

## <a name="configuration-profile-structure"></a><span data-ttu-id="1c923-114">Struttura del profilo di configurazione</span><span class="sxs-lookup"><span data-stu-id="1c923-114">Configuration profile structure</span></span>

<span data-ttu-id="1c923-115">Il profilo di configurazione è un file *plist* costituito da voci identificate da una chiave (che indica il nome della preferenza), seguita da un valore, che dipende dalla natura della preferenza.</span><span class="sxs-lookup"><span data-stu-id="1c923-115">The configuration profile is a *.plist* file that consists of entries identified by a key (which denotes the name of the preference), followed by a value, which depends on the nature of the preference.</span></span> <span data-ttu-id="1c923-116">I valori possono essere semplici (ad esempio un valore numerico) o complessi, ad esempio un elenco nidificato di preferenze.</span><span class="sxs-lookup"><span data-stu-id="1c923-116">Values can either be simple (such as a numerical value) or complex, such as a nested list of preferences.</span></span>

>[!CAUTION]
><span data-ttu-id="1c923-117">Il layout del profilo di configurazione dipende dalla console di gestione in uso.</span><span class="sxs-lookup"><span data-stu-id="1c923-117">The layout of the configuration profile depends on the management console that you are using.</span></span> <span data-ttu-id="1c923-118">Le sezioni seguenti contengono esempi di profili di configurazione per JAMF e Intune.</span><span class="sxs-lookup"><span data-stu-id="1c923-118">The following sections contain examples of configuration profiles for JAMF and Intune.</span></span>

<span data-ttu-id="1c923-119">Il livello superiore del profilo di configurazione include le preferenze e le voci a livello di prodotto per le sottoaree di Microsoft Defender per Endpoint, che vengono illustrate in modo più dettagliato nelle sezioni successive.</span><span class="sxs-lookup"><span data-stu-id="1c923-119">The top level of the configuration profile includes product-wide preferences and entries for subareas of Microsoft Defender for Endpoint, which are explained in more detail in the next sections.</span></span>

### <a name="antivirus-engine-preferences"></a><span data-ttu-id="1c923-120">Preferenze del motore antivirus</span><span class="sxs-lookup"><span data-stu-id="1c923-120">Antivirus engine preferences</span></span>

<span data-ttu-id="1c923-121">La *sezione antivirusEngine* del profilo di configurazione viene usata per gestire le preferenze del componente antivirus di Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="1c923-121">The *antivirusEngine* section of the configuration profile is used to manage the preferences of the antivirus component of Microsoft Defender for Endpoint.</span></span>

|<span data-ttu-id="1c923-122">Sezione</span><span class="sxs-lookup"><span data-stu-id="1c923-122">Section</span></span>|<span data-ttu-id="1c923-123">Valore</span><span class="sxs-lookup"><span data-stu-id="1c923-123">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1c923-124">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="1c923-124">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1c923-125">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1c923-125">**Key**</span></span> | <span data-ttu-id="1c923-126">antivirusEngine</span><span class="sxs-lookup"><span data-stu-id="1c923-126">antivirusEngine</span></span> |
| <span data-ttu-id="1c923-127">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1c923-127">**Data type**</span></span> | <span data-ttu-id="1c923-128">Dizionario (preferenza annidata)</span><span class="sxs-lookup"><span data-stu-id="1c923-128">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="1c923-129">**Comments**</span><span class="sxs-lookup"><span data-stu-id="1c923-129">**Comments**</span></span> | <span data-ttu-id="1c923-130">Per una descrizione del contenuto del dizionario, vedi le sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="1c923-130">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-real-time-protection"></a><span data-ttu-id="1c923-131">Abilitare/disabilitare la protezione in tempo reale</span><span class="sxs-lookup"><span data-stu-id="1c923-131">Enable / disable real-time protection</span></span>

<span data-ttu-id="1c923-132">Specificare se abilitare la protezione in tempo reale, che analizza i file man a cui si accede.</span><span class="sxs-lookup"><span data-stu-id="1c923-132">Specify whether to enable real-time protection, which scans files as they are accessed.</span></span>

|<span data-ttu-id="1c923-133">Sezione</span><span class="sxs-lookup"><span data-stu-id="1c923-133">Section</span></span>|<span data-ttu-id="1c923-134">Valore</span><span class="sxs-lookup"><span data-stu-id="1c923-134">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1c923-135">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="1c923-135">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1c923-136">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1c923-136">**Key**</span></span> | <span data-ttu-id="1c923-137">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="1c923-137">enableRealTimeProtection</span></span> |
| <span data-ttu-id="1c923-138">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1c923-138">**Data type**</span></span> | <span data-ttu-id="1c923-139">Booleano</span><span class="sxs-lookup"><span data-stu-id="1c923-139">Boolean</span></span> |
| <span data-ttu-id="1c923-140">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="1c923-140">**Possible values**</span></span> | <span data-ttu-id="1c923-141">true (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="1c923-141">true (default)</span></span> <br/> <span data-ttu-id="1c923-142">false</span><span class="sxs-lookup"><span data-stu-id="1c923-142">false</span></span> |

#### <a name="enable--disable-passive-mode"></a><span data-ttu-id="1c923-143">Abilitare/disabilitare la modalità passiva</span><span class="sxs-lookup"><span data-stu-id="1c923-143">Enable / disable passive mode</span></span>

<span data-ttu-id="1c923-144">Specificare se il motore antivirus viene eseguito in modalità passiva.</span><span class="sxs-lookup"><span data-stu-id="1c923-144">Specify whether the antivirus engine runs in passive mode.</span></span> <span data-ttu-id="1c923-145">La modalità passiva ha le implicazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1c923-145">Passive mode has the following implications:</span></span> 
- <span data-ttu-id="1c923-146">La protezione in tempo reale è disattivata</span><span class="sxs-lookup"><span data-stu-id="1c923-146">Real-time protection is turned off</span></span>
- <span data-ttu-id="1c923-147">L'analisi su richiesta è attivata</span><span class="sxs-lookup"><span data-stu-id="1c923-147">On-demand scanning is turned on</span></span>
- <span data-ttu-id="1c923-148">La correzione automatica delle minacce è disattivata</span><span class="sxs-lookup"><span data-stu-id="1c923-148">Automatic threat remediation is turned off</span></span>
- <span data-ttu-id="1c923-149">Gli aggiornamenti delle funzionalità di intelligence per la sicurezza sono attivati</span><span class="sxs-lookup"><span data-stu-id="1c923-149">Security intelligence updates are turned on</span></span>
- <span data-ttu-id="1c923-150">L'icona del menu Stato è nascosta</span><span class="sxs-lookup"><span data-stu-id="1c923-150">Status menu icon is hidden</span></span>

|<span data-ttu-id="1c923-151">Sezione</span><span class="sxs-lookup"><span data-stu-id="1c923-151">Section</span></span>|<span data-ttu-id="1c923-152">Valore</span><span class="sxs-lookup"><span data-stu-id="1c923-152">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1c923-153">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="1c923-153">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1c923-154">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1c923-154">**Key**</span></span> | <span data-ttu-id="1c923-155">passiveMode</span><span class="sxs-lookup"><span data-stu-id="1c923-155">passiveMode</span></span> |
| <span data-ttu-id="1c923-156">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1c923-156">**Data type**</span></span> | <span data-ttu-id="1c923-157">Booleano</span><span class="sxs-lookup"><span data-stu-id="1c923-157">Boolean</span></span> |
| <span data-ttu-id="1c923-158">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="1c923-158">**Possible values**</span></span> | <span data-ttu-id="1c923-159">false (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="1c923-159">false (default)</span></span> <br/> <span data-ttu-id="1c923-160">true</span><span class="sxs-lookup"><span data-stu-id="1c923-160">true</span></span> |
| <span data-ttu-id="1c923-161">**Comments**</span><span class="sxs-lookup"><span data-stu-id="1c923-161">**Comments**</span></span> | <span data-ttu-id="1c923-162">Disponibile in Microsoft Defender per Endpoint versione 100.67.60 o successiva.</span><span class="sxs-lookup"><span data-stu-id="1c923-162">Available in Microsoft Defender for Endpoint version 100.67.60 or higher.</span></span> |

#### <a name="exclusion-merge-policy"></a><span data-ttu-id="1c923-163">Criteri di unione esclusioni</span><span class="sxs-lookup"><span data-stu-id="1c923-163">Exclusion merge policy</span></span>

<span data-ttu-id="1c923-164">Specificare i criteri di unione per le esclusioni.</span><span class="sxs-lookup"><span data-stu-id="1c923-164">Specify the merge policy for exclusions.</span></span> <span data-ttu-id="1c923-165">Può trattarsi di una combinazione di esclusioni definite dall'amministratore e definite dall'utente ( ) o solo di esclusioni definite `merge` dall'amministratore ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="1c923-165">This can be a combination of administrator-defined and user-defined exclusions (`merge`) or only administrator-defined exclusions (`admin_only`).</span></span> <span data-ttu-id="1c923-166">Questa impostazione può essere utilizzata per impedire agli utenti locali di definire le proprie esclusioni.</span><span class="sxs-lookup"><span data-stu-id="1c923-166">This setting can be used to restrict local users from defining their own exclusions.</span></span>

|<span data-ttu-id="1c923-167">Sezione</span><span class="sxs-lookup"><span data-stu-id="1c923-167">Section</span></span>|<span data-ttu-id="1c923-168">Valore</span><span class="sxs-lookup"><span data-stu-id="1c923-168">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1c923-169">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="1c923-169">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1c923-170">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1c923-170">**Key**</span></span> | <span data-ttu-id="1c923-171">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="1c923-171">exclusionsMergePolicy</span></span> |
| <span data-ttu-id="1c923-172">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1c923-172">**Data type**</span></span> | <span data-ttu-id="1c923-173">Stringa</span><span class="sxs-lookup"><span data-stu-id="1c923-173">String</span></span> |
| <span data-ttu-id="1c923-174">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="1c923-174">**Possible values**</span></span> | <span data-ttu-id="1c923-175">merge (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="1c923-175">merge (default)</span></span> <br/> <span data-ttu-id="1c923-176">admin_only</span><span class="sxs-lookup"><span data-stu-id="1c923-176">admin_only</span></span> |
| <span data-ttu-id="1c923-177">**Comments**</span><span class="sxs-lookup"><span data-stu-id="1c923-177">**Comments**</span></span> | <span data-ttu-id="1c923-178">Disponibile in Microsoft Defender per Endpoint versione 100.83.73 o successiva.</span><span class="sxs-lookup"><span data-stu-id="1c923-178">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="scan-exclusions"></a><span data-ttu-id="1c923-179">Esclusioni analisi</span><span class="sxs-lookup"><span data-stu-id="1c923-179">Scan exclusions</span></span>

<span data-ttu-id="1c923-180">Specificare le entità escluse dall'analisi.</span><span class="sxs-lookup"><span data-stu-id="1c923-180">Specify entities excluded from being scanned.</span></span> <span data-ttu-id="1c923-181">Le esclusioni possono essere specificate da percorsi completi, estensioni o nomi di file.</span><span class="sxs-lookup"><span data-stu-id="1c923-181">Exclusions can be specified by full paths, extensions, or file names.</span></span>

|<span data-ttu-id="1c923-182">Sezione</span><span class="sxs-lookup"><span data-stu-id="1c923-182">Section</span></span>|<span data-ttu-id="1c923-183">Valore</span><span class="sxs-lookup"><span data-stu-id="1c923-183">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1c923-184">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="1c923-184">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1c923-185">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1c923-185">**Key**</span></span> | <span data-ttu-id="1c923-186">esclusioni</span><span class="sxs-lookup"><span data-stu-id="1c923-186">exclusions</span></span> |
| <span data-ttu-id="1c923-187">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1c923-187">**Data type**</span></span> | <span data-ttu-id="1c923-188">Dizionario (preferenza annidata)</span><span class="sxs-lookup"><span data-stu-id="1c923-188">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="1c923-189">**Comments**</span><span class="sxs-lookup"><span data-stu-id="1c923-189">**Comments**</span></span> | <span data-ttu-id="1c923-190">Per una descrizione del contenuto del dizionario, vedi le sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="1c923-190">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="type-of-exclusion"></a><span data-ttu-id="1c923-191">Tipo di esclusione</span><span class="sxs-lookup"><span data-stu-id="1c923-191">Type of exclusion</span></span>

<span data-ttu-id="1c923-192">Specificare il contenuto escluso dall'analisi in base al tipo.</span><span class="sxs-lookup"><span data-stu-id="1c923-192">Specify content excluded from being scanned by type.</span></span>

|<span data-ttu-id="1c923-193">Sezione</span><span class="sxs-lookup"><span data-stu-id="1c923-193">Section</span></span>|<span data-ttu-id="1c923-194">Valore</span><span class="sxs-lookup"><span data-stu-id="1c923-194">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1c923-195">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="1c923-195">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1c923-196">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1c923-196">**Key**</span></span> | <span data-ttu-id="1c923-197">$type</span><span class="sxs-lookup"><span data-stu-id="1c923-197">$type</span></span> |
| <span data-ttu-id="1c923-198">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1c923-198">**Data type**</span></span> | <span data-ttu-id="1c923-199">Stringa</span><span class="sxs-lookup"><span data-stu-id="1c923-199">String</span></span> |
| <span data-ttu-id="1c923-200">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="1c923-200">**Possible values**</span></span> | <span data-ttu-id="1c923-201">excludedPath</span><span class="sxs-lookup"><span data-stu-id="1c923-201">excludedPath</span></span> <br/> <span data-ttu-id="1c923-202">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="1c923-202">excludedFileExtension</span></span> <br/> <span data-ttu-id="1c923-203">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="1c923-203">excludedFileName</span></span> |

##### <a name="path-to-excluded-content"></a><span data-ttu-id="1c923-204">Percorso del contenuto escluso</span><span class="sxs-lookup"><span data-stu-id="1c923-204">Path to excluded content</span></span>

<span data-ttu-id="1c923-205">Specificare il contenuto escluso dall'analisi tramite il percorso completo del file.</span><span class="sxs-lookup"><span data-stu-id="1c923-205">Specify content excluded from being scanned by full file path.</span></span>

|<span data-ttu-id="1c923-206">Sezione</span><span class="sxs-lookup"><span data-stu-id="1c923-206">Section</span></span>|<span data-ttu-id="1c923-207">Valore</span><span class="sxs-lookup"><span data-stu-id="1c923-207">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1c923-208">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="1c923-208">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1c923-209">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1c923-209">**Key**</span></span> | <span data-ttu-id="1c923-210">path</span><span class="sxs-lookup"><span data-stu-id="1c923-210">path</span></span> |
| <span data-ttu-id="1c923-211">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1c923-211">**Data type**</span></span> | <span data-ttu-id="1c923-212">Stringa</span><span class="sxs-lookup"><span data-stu-id="1c923-212">String</span></span> |
| <span data-ttu-id="1c923-213">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="1c923-213">**Possible values**</span></span> | <span data-ttu-id="1c923-214">percorsi validi</span><span class="sxs-lookup"><span data-stu-id="1c923-214">valid paths</span></span> |
| <span data-ttu-id="1c923-215">**Comments**</span><span class="sxs-lookup"><span data-stu-id="1c923-215">**Comments**</span></span> | <span data-ttu-id="1c923-216">Applicabile solo se *$type* *è excludedPath*</span><span class="sxs-lookup"><span data-stu-id="1c923-216">Applicable only if *$type* is *excludedPath*</span></span> |

##### <a name="path-type-file--directory"></a><span data-ttu-id="1c923-217">Tipo di percorso (file/directory)</span><span class="sxs-lookup"><span data-stu-id="1c923-217">Path type (file / directory)</span></span>

<span data-ttu-id="1c923-218">Indicare se la *proprietà path* fa riferimento a un file o a una directory.</span><span class="sxs-lookup"><span data-stu-id="1c923-218">Indicate if the *path* property refers to a file or directory.</span></span> 

|<span data-ttu-id="1c923-219">Sezione</span><span class="sxs-lookup"><span data-stu-id="1c923-219">Section</span></span>|<span data-ttu-id="1c923-220">Valore</span><span class="sxs-lookup"><span data-stu-id="1c923-220">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1c923-221">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="1c923-221">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1c923-222">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1c923-222">**Key**</span></span> | <span data-ttu-id="1c923-223">isDirectory</span><span class="sxs-lookup"><span data-stu-id="1c923-223">isDirectory</span></span> |
| <span data-ttu-id="1c923-224">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1c923-224">**Data type**</span></span> | <span data-ttu-id="1c923-225">Booleano</span><span class="sxs-lookup"><span data-stu-id="1c923-225">Boolean</span></span> |
| <span data-ttu-id="1c923-226">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="1c923-226">**Possible values**</span></span> | <span data-ttu-id="1c923-227">false (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="1c923-227">false (default)</span></span> <br/> <span data-ttu-id="1c923-228">true</span><span class="sxs-lookup"><span data-stu-id="1c923-228">true</span></span> |
| <span data-ttu-id="1c923-229">**Comments**</span><span class="sxs-lookup"><span data-stu-id="1c923-229">**Comments**</span></span> | <span data-ttu-id="1c923-230">Applicabile solo se *$type* *è excludedPath*</span><span class="sxs-lookup"><span data-stu-id="1c923-230">Applicable only if *$type* is *excludedPath*</span></span> |

##### <a name="file-extension-excluded-from-the-scan"></a><span data-ttu-id="1c923-231">Estensione di file esclusa dall'analisi</span><span class="sxs-lookup"><span data-stu-id="1c923-231">File extension excluded from the scan</span></span>

<span data-ttu-id="1c923-232">Specificare il contenuto escluso dall'analisi per estensione di file.</span><span class="sxs-lookup"><span data-stu-id="1c923-232">Specify content excluded from being scanned by file extension.</span></span>

|<span data-ttu-id="1c923-233">Sezione</span><span class="sxs-lookup"><span data-stu-id="1c923-233">Section</span></span>|<span data-ttu-id="1c923-234">Valore</span><span class="sxs-lookup"><span data-stu-id="1c923-234">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1c923-235">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="1c923-235">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1c923-236">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1c923-236">**Key**</span></span> | <span data-ttu-id="1c923-237">extension</span><span class="sxs-lookup"><span data-stu-id="1c923-237">extension</span></span> |
| <span data-ttu-id="1c923-238">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1c923-238">**Data type**</span></span> | <span data-ttu-id="1c923-239">Stringa</span><span class="sxs-lookup"><span data-stu-id="1c923-239">String</span></span> |
| <span data-ttu-id="1c923-240">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="1c923-240">**Possible values**</span></span> | <span data-ttu-id="1c923-241">estensioni di file valide</span><span class="sxs-lookup"><span data-stu-id="1c923-241">valid file extensions</span></span> |
| <span data-ttu-id="1c923-242">**Comments**</span><span class="sxs-lookup"><span data-stu-id="1c923-242">**Comments**</span></span> | <span data-ttu-id="1c923-243">Applicabile solo se *$type* *è excludedFileExtension*</span><span class="sxs-lookup"><span data-stu-id="1c923-243">Applicable only if *$type* is *excludedFileExtension*</span></span> |

##### <a name="process-excluded-from-the-scan"></a><span data-ttu-id="1c923-244">Processo escluso dall'analisi</span><span class="sxs-lookup"><span data-stu-id="1c923-244">Process excluded from the scan</span></span>

<span data-ttu-id="1c923-245">Specificare un processo per il quale tutte le attività dei file vengono escluse dall'analisi.</span><span class="sxs-lookup"><span data-stu-id="1c923-245">Specify a process for which all file activity is excluded from scanning.</span></span> <span data-ttu-id="1c923-246">Il processo può essere specificato in base al nome (ad esempio) o al `cat` percorso completo (ad `/bin/cat` esempio).</span><span class="sxs-lookup"><span data-stu-id="1c923-246">The process can be specified either by its name (e.g. `cat`) or full path (e.g. `/bin/cat`).</span></span>

|<span data-ttu-id="1c923-247">Sezione</span><span class="sxs-lookup"><span data-stu-id="1c923-247">Section</span></span>|<span data-ttu-id="1c923-248">Valore</span><span class="sxs-lookup"><span data-stu-id="1c923-248">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1c923-249">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="1c923-249">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1c923-250">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1c923-250">**Key**</span></span> | <span data-ttu-id="1c923-251">name</span><span class="sxs-lookup"><span data-stu-id="1c923-251">name</span></span> |
| <span data-ttu-id="1c923-252">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1c923-252">**Data type**</span></span> | <span data-ttu-id="1c923-253">Stringa</span><span class="sxs-lookup"><span data-stu-id="1c923-253">String</span></span> |
| <span data-ttu-id="1c923-254">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="1c923-254">**Possible values**</span></span> | <span data-ttu-id="1c923-255">qualsiasi stringa</span><span class="sxs-lookup"><span data-stu-id="1c923-255">any string</span></span> |
| <span data-ttu-id="1c923-256">**Comments**</span><span class="sxs-lookup"><span data-stu-id="1c923-256">**Comments**</span></span> | <span data-ttu-id="1c923-257">Applicabile solo se *$type* *è excludedFileName*</span><span class="sxs-lookup"><span data-stu-id="1c923-257">Applicable only if *$type* is *excludedFileName*</span></span> |

#### <a name="allowed-threats"></a><span data-ttu-id="1c923-258">Minacce consentite</span><span class="sxs-lookup"><span data-stu-id="1c923-258">Allowed threats</span></span>

<span data-ttu-id="1c923-259">Specifica le minacce in base al nome che non sono bloccate da Defender per Endpoint per Mac.</span><span class="sxs-lookup"><span data-stu-id="1c923-259">Specify threats by name that are not blocked by Defender for Endpoint for Mac.</span></span> <span data-ttu-id="1c923-260">L'esecuzione di queste minacce sarà consentita.</span><span class="sxs-lookup"><span data-stu-id="1c923-260">These threats will be allowed to run.</span></span>

|<span data-ttu-id="1c923-261">Sezione</span><span class="sxs-lookup"><span data-stu-id="1c923-261">Section</span></span>|<span data-ttu-id="1c923-262">Valore</span><span class="sxs-lookup"><span data-stu-id="1c923-262">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1c923-263">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="1c923-263">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1c923-264">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1c923-264">**Key**</span></span> | <span data-ttu-id="1c923-265">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="1c923-265">allowedThreats</span></span> |
| <span data-ttu-id="1c923-266">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1c923-266">**Data type**</span></span> | <span data-ttu-id="1c923-267">Matrice di stringhe</span><span class="sxs-lookup"><span data-stu-id="1c923-267">Array of strings</span></span> |

#### <a name="disallowed-threat-actions"></a><span data-ttu-id="1c923-268">Azioni di minaccia non consentite</span><span class="sxs-lookup"><span data-stu-id="1c923-268">Disallowed threat actions</span></span>

<span data-ttu-id="1c923-269">Limita le azioni che l'utente locale di un dispositivo può intraprendere quando vengono rilevate minacce.</span><span class="sxs-lookup"><span data-stu-id="1c923-269">Restricts the actions that the local user of a device can take when threats are detected.</span></span> <span data-ttu-id="1c923-270">Le azioni incluse in questo elenco non vengono visualizzate nell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="1c923-270">The actions included in this list are not displayed in the user interface.</span></span>

|<span data-ttu-id="1c923-271">Sezione</span><span class="sxs-lookup"><span data-stu-id="1c923-271">Section</span></span>|<span data-ttu-id="1c923-272">Valore</span><span class="sxs-lookup"><span data-stu-id="1c923-272">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1c923-273">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="1c923-273">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1c923-274">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1c923-274">**Key**</span></span> | <span data-ttu-id="1c923-275">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="1c923-275">disallowedThreatActions</span></span> |
| <span data-ttu-id="1c923-276">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1c923-276">**Data type**</span></span> | <span data-ttu-id="1c923-277">Matrice di stringhe</span><span class="sxs-lookup"><span data-stu-id="1c923-277">Array of strings</span></span> |
| <span data-ttu-id="1c923-278">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="1c923-278">**Possible values**</span></span> | <span data-ttu-id="1c923-279">allow (impedisce agli utenti di consentire minacce)</span><span class="sxs-lookup"><span data-stu-id="1c923-279">allow (restricts users from allowing threats)</span></span> <br/> <span data-ttu-id="1c923-280">restore (impedisce agli utenti di ripristinare le minacce dalla quarantena)</span><span class="sxs-lookup"><span data-stu-id="1c923-280">restore (restricts users from restoring threats from the quarantine)</span></span> |
| <span data-ttu-id="1c923-281">**Comments**</span><span class="sxs-lookup"><span data-stu-id="1c923-281">**Comments**</span></span> | <span data-ttu-id="1c923-282">Disponibile in Microsoft Defender per Endpoint versione 100.83.73 o successiva.</span><span class="sxs-lookup"><span data-stu-id="1c923-282">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="threat-type-settings"></a><span data-ttu-id="1c923-283">Impostazioni del tipo di minaccia</span><span class="sxs-lookup"><span data-stu-id="1c923-283">Threat type settings</span></span>

<span data-ttu-id="1c923-284">Specifica come vengono gestiti determinati tipi di minacce da Microsoft Defender per Endpoint in macOS.</span><span class="sxs-lookup"><span data-stu-id="1c923-284">Specify how certain threat types are handled by Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="1c923-285">Sezione</span><span class="sxs-lookup"><span data-stu-id="1c923-285">Section</span></span>|<span data-ttu-id="1c923-286">Valore</span><span class="sxs-lookup"><span data-stu-id="1c923-286">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1c923-287">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="1c923-287">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1c923-288">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1c923-288">**Key**</span></span> | <span data-ttu-id="1c923-289">threatTypeSettings</span><span class="sxs-lookup"><span data-stu-id="1c923-289">threatTypeSettings</span></span> |
| <span data-ttu-id="1c923-290">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1c923-290">**Data type**</span></span> | <span data-ttu-id="1c923-291">Dizionario (preferenza annidata)</span><span class="sxs-lookup"><span data-stu-id="1c923-291">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="1c923-292">**Comments**</span><span class="sxs-lookup"><span data-stu-id="1c923-292">**Comments**</span></span> | <span data-ttu-id="1c923-293">Per una descrizione del contenuto del dizionario, vedi le sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="1c923-293">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="threat-type"></a><span data-ttu-id="1c923-294">Tipo di minaccia</span><span class="sxs-lookup"><span data-stu-id="1c923-294">Threat type</span></span>

<span data-ttu-id="1c923-295">Specificare i tipi di minaccia.</span><span class="sxs-lookup"><span data-stu-id="1c923-295">Specify threat types.</span></span>

|<span data-ttu-id="1c923-296">Sezione</span><span class="sxs-lookup"><span data-stu-id="1c923-296">Section</span></span>|<span data-ttu-id="1c923-297">Valore</span><span class="sxs-lookup"><span data-stu-id="1c923-297">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1c923-298">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="1c923-298">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1c923-299">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1c923-299">**Key**</span></span> | <span data-ttu-id="1c923-300">chiave</span><span class="sxs-lookup"><span data-stu-id="1c923-300">key</span></span> |
| <span data-ttu-id="1c923-301">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1c923-301">**Data type**</span></span> | <span data-ttu-id="1c923-302">Stringa</span><span class="sxs-lookup"><span data-stu-id="1c923-302">String</span></span> |
| <span data-ttu-id="1c923-303">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="1c923-303">**Possible values**</span></span> | <span data-ttu-id="1c923-304">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="1c923-304">potentially_unwanted_application</span></span> <br/> <span data-ttu-id="1c923-305">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="1c923-305">archive_bomb</span></span> |

##### <a name="action-to-take"></a><span data-ttu-id="1c923-306">Procedura da seguire</span><span class="sxs-lookup"><span data-stu-id="1c923-306">Action to take</span></span>

<span data-ttu-id="1c923-307">Specificare l'azione da eseguire quando viene rilevata una minaccia del tipo specificato nella sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="1c923-307">Specify what action to take when a threat of the type specified in the preceding section is detected.</span></span> <span data-ttu-id="1c923-308">Scegliere una delle seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="1c923-308">Choose from the following options:</span></span>

- <span data-ttu-id="1c923-309">**Controllo**: il dispositivo non è protetto da questo tipo di minaccia, ma viene registrata una voce relativa alla minaccia.</span><span class="sxs-lookup"><span data-stu-id="1c923-309">**Audit**: your device is not protected against this type of threat, but an entry about the threat is logged.</span></span>
- <span data-ttu-id="1c923-310">**Blocca**: il dispositivo è protetto da questo tipo di minaccia e si viene informati nell'interfaccia utente e nella console di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="1c923-310">**Block**: your device is protected against this type of threat and you are notified in the user interface and the security console.</span></span>
- <span data-ttu-id="1c923-311">**Disattivato:** il dispositivo non è protetto da questo tipo di minaccia e non viene registrato nulla.</span><span class="sxs-lookup"><span data-stu-id="1c923-311">**Off**: your device is not protected against this type of threat and nothing is logged.</span></span>

|<span data-ttu-id="1c923-312">Sezione</span><span class="sxs-lookup"><span data-stu-id="1c923-312">Section</span></span>|<span data-ttu-id="1c923-313">Valore</span><span class="sxs-lookup"><span data-stu-id="1c923-313">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1c923-314">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="1c923-314">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1c923-315">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1c923-315">**Key**</span></span> | <span data-ttu-id="1c923-316">valore</span><span class="sxs-lookup"><span data-stu-id="1c923-316">value</span></span> |
| <span data-ttu-id="1c923-317">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1c923-317">**Data type**</span></span> | <span data-ttu-id="1c923-318">Stringa</span><span class="sxs-lookup"><span data-stu-id="1c923-318">String</span></span> |
| <span data-ttu-id="1c923-319">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="1c923-319">**Possible values**</span></span> | <span data-ttu-id="1c923-320">audit (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="1c923-320">audit (default)</span></span> <br/> <span data-ttu-id="1c923-321">blocco</span><span class="sxs-lookup"><span data-stu-id="1c923-321">block</span></span> <br/> <span data-ttu-id="1c923-322">off</span><span class="sxs-lookup"><span data-stu-id="1c923-322">off</span></span> |

#### <a name="threat-type-settings-merge-policy"></a><span data-ttu-id="1c923-323">Criteri di unione delle impostazioni del tipo di minaccia</span><span class="sxs-lookup"><span data-stu-id="1c923-323">Threat type settings merge policy</span></span>

<span data-ttu-id="1c923-324">Specificare i criteri di unione per le impostazioni del tipo di minaccia.</span><span class="sxs-lookup"><span data-stu-id="1c923-324">Specify the merge policy for threat type settings.</span></span> <span data-ttu-id="1c923-325">Può essere una combinazione di impostazioni definite dall'amministratore e definite dall'utente ( ) o solo impostazioni definite `merge` dall'amministratore ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="1c923-325">This can be a combination of administrator-defined and user-defined settings (`merge`) or only administrator-defined settings (`admin_only`).</span></span> <span data-ttu-id="1c923-326">Questa impostazione può essere usata per impedire agli utenti locali di definire le proprie impostazioni per diversi tipi di minacce.</span><span class="sxs-lookup"><span data-stu-id="1c923-326">This setting can be used to restrict local users from defining their own settings for different threat types.</span></span>

|<span data-ttu-id="1c923-327">Sezione</span><span class="sxs-lookup"><span data-stu-id="1c923-327">Section</span></span>|<span data-ttu-id="1c923-328">Valore</span><span class="sxs-lookup"><span data-stu-id="1c923-328">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1c923-329">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="1c923-329">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1c923-330">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1c923-330">**Key**</span></span> | <span data-ttu-id="1c923-331">threatTypeSettingsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="1c923-331">threatTypeSettingsMergePolicy</span></span> |
| <span data-ttu-id="1c923-332">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1c923-332">**Data type**</span></span> | <span data-ttu-id="1c923-333">Stringa</span><span class="sxs-lookup"><span data-stu-id="1c923-333">String</span></span> |
| <span data-ttu-id="1c923-334">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="1c923-334">**Possible values**</span></span> | <span data-ttu-id="1c923-335">merge (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="1c923-335">merge (default)</span></span> <br/> <span data-ttu-id="1c923-336">admin_only</span><span class="sxs-lookup"><span data-stu-id="1c923-336">admin_only</span></span> |
| <span data-ttu-id="1c923-337">**Comments**</span><span class="sxs-lookup"><span data-stu-id="1c923-337">**Comments**</span></span> | <span data-ttu-id="1c923-338">Disponibile in Microsoft Defender per Endpoint versione 100.83.73 o successiva.</span><span class="sxs-lookup"><span data-stu-id="1c923-338">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="antivirus-scan-history-retention-in-days"></a><span data-ttu-id="1c923-339">Conservazione cronologia analisi antivirus (in giorni)</span><span class="sxs-lookup"><span data-stu-id="1c923-339">Antivirus scan history retention (in days)</span></span>

<span data-ttu-id="1c923-340">Specifica il numero di giorni in cui i risultati vengono conservati nella cronologia dell'analisi nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1c923-340">Specify the number of days that results are retained in the scan history on the device.</span></span> <span data-ttu-id="1c923-341">I risultati dell'analisi precedente vengono rimossi dalla cronologia.</span><span class="sxs-lookup"><span data-stu-id="1c923-341">Old scan results are removed from the history.</span></span> <span data-ttu-id="1c923-342">Vecchi file in quarantena che vengono rimossi anche dal disco.</span><span class="sxs-lookup"><span data-stu-id="1c923-342">Old quarantined files that are also removed from the disk.</span></span>

|<span data-ttu-id="1c923-343">Sezione</span><span class="sxs-lookup"><span data-stu-id="1c923-343">Section</span></span>|<span data-ttu-id="1c923-344">Valore</span><span class="sxs-lookup"><span data-stu-id="1c923-344">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1c923-345">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="1c923-345">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1c923-346">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1c923-346">**Key**</span></span> | <span data-ttu-id="1c923-347">scanResultsRetentionDays</span><span class="sxs-lookup"><span data-stu-id="1c923-347">scanResultsRetentionDays</span></span> |
| <span data-ttu-id="1c923-348">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1c923-348">**Data type**</span></span> | <span data-ttu-id="1c923-349">Stringa</span><span class="sxs-lookup"><span data-stu-id="1c923-349">String</span></span> |
| <span data-ttu-id="1c923-350">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="1c923-350">**Possible values**</span></span> | <span data-ttu-id="1c923-351">90 (impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="1c923-351">90 (default).</span></span> <span data-ttu-id="1c923-352">I valori consentiti sono da 1 giorno a 180 giorni.</span><span class="sxs-lookup"><span data-stu-id="1c923-352">Allowed values are from 1 day to 180 days.</span></span> |
| <span data-ttu-id="1c923-353">**Comments**</span><span class="sxs-lookup"><span data-stu-id="1c923-353">**Comments**</span></span> | <span data-ttu-id="1c923-354">Disponibile in Microsoft Defender per Endpoint versione 101.07.23 o successiva.</span><span class="sxs-lookup"><span data-stu-id="1c923-354">Available in Microsoft Defender for Endpoint version 101.07.23 or higher.</span></span> |

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a><span data-ttu-id="1c923-355">Numero massimo di elementi nella cronologia dell'analisi antivirus</span><span class="sxs-lookup"><span data-stu-id="1c923-355">Maximum number of items in the antivirus scan history</span></span>

<span data-ttu-id="1c923-356">Specificare il numero massimo di voci da mantenere nella cronologia di analisi.</span><span class="sxs-lookup"><span data-stu-id="1c923-356">Specify the maximum number of entries to keep in the scan history.</span></span> <span data-ttu-id="1c923-357">Le voci includono tutte le analisi su richiesta eseguite in passato e tutti i rilevamenti antivirus.</span><span class="sxs-lookup"><span data-stu-id="1c923-357">Entries include all on-demand scans performed in the past and all antivirus detections.</span></span>

|<span data-ttu-id="1c923-358">Sezione</span><span class="sxs-lookup"><span data-stu-id="1c923-358">Section</span></span>|<span data-ttu-id="1c923-359">Valore</span><span class="sxs-lookup"><span data-stu-id="1c923-359">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1c923-360">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="1c923-360">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1c923-361">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1c923-361">**Key**</span></span> | <span data-ttu-id="1c923-362">scanHistoryMaximumItems</span><span class="sxs-lookup"><span data-stu-id="1c923-362">scanHistoryMaximumItems</span></span> |
| <span data-ttu-id="1c923-363">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1c923-363">**Data type**</span></span> | <span data-ttu-id="1c923-364">Stringa</span><span class="sxs-lookup"><span data-stu-id="1c923-364">String</span></span> |
| <span data-ttu-id="1c923-365">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="1c923-365">**Possible values**</span></span> | <span data-ttu-id="1c923-366">10000 (impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="1c923-366">10000 (default).</span></span> <span data-ttu-id="1c923-367">I valori consentiti sono da 5.000 elementi a 15.000 elementi.</span><span class="sxs-lookup"><span data-stu-id="1c923-367">Allowed values are from 5000 items to 15000 items.</span></span> |
| <span data-ttu-id="1c923-368">**Comments**</span><span class="sxs-lookup"><span data-stu-id="1c923-368">**Comments**</span></span> | <span data-ttu-id="1c923-369">Disponibile in Microsoft Defender per Endpoint versione 101.07.23 o successiva.</span><span class="sxs-lookup"><span data-stu-id="1c923-369">Available in Microsoft Defender for Endpoint version 101.07.23 or higher.</span></span> |

### <a name="cloud-delivered-protection-preferences"></a><span data-ttu-id="1c923-370">Preferenze di protezione per il cloud</span><span class="sxs-lookup"><span data-stu-id="1c923-370">Cloud-delivered protection preferences</span></span>

<span data-ttu-id="1c923-371">Configurare le funzionalità di protezione basata sul cloud di Microsoft Defender per Endpoint in macOS.</span><span class="sxs-lookup"><span data-stu-id="1c923-371">Configure the cloud-driven protection features of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="1c923-372">Sezione</span><span class="sxs-lookup"><span data-stu-id="1c923-372">Section</span></span>|<span data-ttu-id="1c923-373">Valore</span><span class="sxs-lookup"><span data-stu-id="1c923-373">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1c923-374">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="1c923-374">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1c923-375">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1c923-375">**Key**</span></span> | <span data-ttu-id="1c923-376">cloudService</span><span class="sxs-lookup"><span data-stu-id="1c923-376">cloudService</span></span> |
| <span data-ttu-id="1c923-377">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1c923-377">**Data type**</span></span> | <span data-ttu-id="1c923-378">Dizionario (preferenza annidata)</span><span class="sxs-lookup"><span data-stu-id="1c923-378">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="1c923-379">**Comments**</span><span class="sxs-lookup"><span data-stu-id="1c923-379">**Comments**</span></span> | <span data-ttu-id="1c923-380">Per una descrizione del contenuto del dizionario, vedi le sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="1c923-380">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-cloud-delivered-protection"></a><span data-ttu-id="1c923-381">Abilitare/disabilitare la protezione recapitata nel cloud</span><span class="sxs-lookup"><span data-stu-id="1c923-381">Enable / disable cloud-delivered protection</span></span>

<span data-ttu-id="1c923-382">Specificare se abilitare o meno la protezione recapitata nel cloud.</span><span class="sxs-lookup"><span data-stu-id="1c923-382">Specify whether to enable cloud-delivered protection the device or not.</span></span> <span data-ttu-id="1c923-383">Per migliorare la sicurezza dei servizi, è consigliabile mantenere attivata questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="1c923-383">To improve the security of your services, we recommend keeping this feature turned on.</span></span>

|<span data-ttu-id="1c923-384">Sezione</span><span class="sxs-lookup"><span data-stu-id="1c923-384">Section</span></span>|<span data-ttu-id="1c923-385">Valore</span><span class="sxs-lookup"><span data-stu-id="1c923-385">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1c923-386">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="1c923-386">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1c923-387">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1c923-387">**Key**</span></span> | <span data-ttu-id="1c923-388">abilitati</span><span class="sxs-lookup"><span data-stu-id="1c923-388">enabled</span></span> |
| <span data-ttu-id="1c923-389">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1c923-389">**Data type**</span></span> | <span data-ttu-id="1c923-390">Booleano</span><span class="sxs-lookup"><span data-stu-id="1c923-390">Boolean</span></span> |
| <span data-ttu-id="1c923-391">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="1c923-391">**Possible values**</span></span> | <span data-ttu-id="1c923-392">true (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="1c923-392">true (default)</span></span> <br/> <span data-ttu-id="1c923-393">false</span><span class="sxs-lookup"><span data-stu-id="1c923-393">false</span></span> |

#### <a name="diagnostic-collection-level"></a><span data-ttu-id="1c923-394">Livello raccolta diagnostica</span><span class="sxs-lookup"><span data-stu-id="1c923-394">Diagnostic collection level</span></span>

<span data-ttu-id="1c923-395">I dati di diagnostica vengono usati per mantenere Microsoft Defender for Endpoint sicuro e aggiornato, rilevare, diagnosticare e risolvere i problemi e apportare miglioramenti al prodotto.</span><span class="sxs-lookup"><span data-stu-id="1c923-395">Diagnostic data is used to keep Microsoft Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span> <span data-ttu-id="1c923-396">Questa impostazione determina il livello di diagnostica inviato da Microsoft Defender per Endpoint a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1c923-396">This setting determines the level of diagnostics sent by Microsoft Defender for Endpoint to Microsoft.</span></span>

|<span data-ttu-id="1c923-397">Sezione</span><span class="sxs-lookup"><span data-stu-id="1c923-397">Section</span></span>|<span data-ttu-id="1c923-398">Valore</span><span class="sxs-lookup"><span data-stu-id="1c923-398">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1c923-399">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="1c923-399">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1c923-400">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1c923-400">**Key**</span></span> | <span data-ttu-id="1c923-401">diagnosticLevel</span><span class="sxs-lookup"><span data-stu-id="1c923-401">diagnosticLevel</span></span> |
| <span data-ttu-id="1c923-402">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1c923-402">**Data type**</span></span> | <span data-ttu-id="1c923-403">Stringa</span><span class="sxs-lookup"><span data-stu-id="1c923-403">String</span></span> |
| <span data-ttu-id="1c923-404">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="1c923-404">**Possible values**</span></span> | <span data-ttu-id="1c923-405">facoltativo (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="1c923-405">optional (default)</span></span> <br/> <span data-ttu-id="1c923-406">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="1c923-406">required</span></span> |

#### <a name="enable--disable-automatic-sample-submissions"></a><span data-ttu-id="1c923-407">Abilitare/disabilitare gli invii di esempio automatici</span><span class="sxs-lookup"><span data-stu-id="1c923-407">Enable / disable automatic sample submissions</span></span>

<span data-ttu-id="1c923-408">Determina se i campioni sospetti (che potrebbero contenere minacce) vengono inviati a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1c923-408">Determines whether suspicious samples (that are likely to contain threats) are sent to Microsoft.</span></span> <span data-ttu-id="1c923-409">Viene richiesto se è probabile che il file inviato contenga informazioni personali.</span><span class="sxs-lookup"><span data-stu-id="1c923-409">You are prompted if the submitted file is likely to contain personal information.</span></span>

|<span data-ttu-id="1c923-410">Sezione</span><span class="sxs-lookup"><span data-stu-id="1c923-410">Section</span></span>|<span data-ttu-id="1c923-411">Valore</span><span class="sxs-lookup"><span data-stu-id="1c923-411">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1c923-412">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="1c923-412">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1c923-413">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1c923-413">**Key**</span></span> | <span data-ttu-id="1c923-414">automaticSampleSubmission</span><span class="sxs-lookup"><span data-stu-id="1c923-414">automaticSampleSubmission</span></span> |
| <span data-ttu-id="1c923-415">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1c923-415">**Data type**</span></span> | <span data-ttu-id="1c923-416">Booleano</span><span class="sxs-lookup"><span data-stu-id="1c923-416">Boolean</span></span> |
| <span data-ttu-id="1c923-417">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="1c923-417">**Possible values**</span></span> | <span data-ttu-id="1c923-418">true (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="1c923-418">true (default)</span></span> <br/> <span data-ttu-id="1c923-419">false</span><span class="sxs-lookup"><span data-stu-id="1c923-419">false</span></span> |

#### <a name="enable--disable-automatic-security-intelligence-updates"></a><span data-ttu-id="1c923-420">Abilitare/disabilitare gli aggiornamenti automatici delle funzionalità di intelligence per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="1c923-420">Enable / disable automatic security intelligence updates</span></span>

<span data-ttu-id="1c923-421">Determina se gli aggiornamenti delle funzionalità di intelligence per la sicurezza vengono installati automaticamente:</span><span class="sxs-lookup"><span data-stu-id="1c923-421">Determines whether security intelligence updates are installed automatically:</span></span>

|<span data-ttu-id="1c923-422">Sezione</span><span class="sxs-lookup"><span data-stu-id="1c923-422">Section</span></span>|<span data-ttu-id="1c923-423">Valore</span><span class="sxs-lookup"><span data-stu-id="1c923-423">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1c923-424">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1c923-424">**Key**</span></span> | <span data-ttu-id="1c923-425">automaticDefinitionUpdateEnabled</span><span class="sxs-lookup"><span data-stu-id="1c923-425">automaticDefinitionUpdateEnabled</span></span> |
| <span data-ttu-id="1c923-426">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1c923-426">**Data type**</span></span> | <span data-ttu-id="1c923-427">Booleano</span><span class="sxs-lookup"><span data-stu-id="1c923-427">Boolean</span></span> |
| <span data-ttu-id="1c923-428">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="1c923-428">**Possible values**</span></span> | <span data-ttu-id="1c923-429">true (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="1c923-429">true (default)</span></span> <br/> <span data-ttu-id="1c923-430">false</span><span class="sxs-lookup"><span data-stu-id="1c923-430">false</span></span> |

### <a name="user-interface-preferences"></a><span data-ttu-id="1c923-431">Preferenze dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="1c923-431">User interface preferences</span></span>

<span data-ttu-id="1c923-432">Gestire le preferenze per l'interfaccia utente di Microsoft Defender per Endpoint in macOS.</span><span class="sxs-lookup"><span data-stu-id="1c923-432">Manage the preferences for the user interface of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="1c923-433">Sezione</span><span class="sxs-lookup"><span data-stu-id="1c923-433">Section</span></span>|<span data-ttu-id="1c923-434">Valore</span><span class="sxs-lookup"><span data-stu-id="1c923-434">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1c923-435">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="1c923-435">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1c923-436">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1c923-436">**Key**</span></span> | <span data-ttu-id="1c923-437">userInterface</span><span class="sxs-lookup"><span data-stu-id="1c923-437">userInterface</span></span> |
| <span data-ttu-id="1c923-438">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1c923-438">**Data type**</span></span> | <span data-ttu-id="1c923-439">Dizionario (preferenza annidata)</span><span class="sxs-lookup"><span data-stu-id="1c923-439">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="1c923-440">**Comments**</span><span class="sxs-lookup"><span data-stu-id="1c923-440">**Comments**</span></span> | <span data-ttu-id="1c923-441">Per una descrizione del contenuto del dizionario, vedi le sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="1c923-441">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="show--hide-status-menu-icon"></a><span data-ttu-id="1c923-442">Mostra/nascondi icona del menu di stato</span><span class="sxs-lookup"><span data-stu-id="1c923-442">Show / hide status menu icon</span></span>

<span data-ttu-id="1c923-443">Specifica se mostrare o nascondere l'icona del menu di stato nell'angolo in alto a destra dello schermo.</span><span class="sxs-lookup"><span data-stu-id="1c923-443">Specify whether to show or hide the status menu icon in the top-right corner of the screen.</span></span>

|<span data-ttu-id="1c923-444">Sezione</span><span class="sxs-lookup"><span data-stu-id="1c923-444">Section</span></span>|<span data-ttu-id="1c923-445">Valore</span><span class="sxs-lookup"><span data-stu-id="1c923-445">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1c923-446">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="1c923-446">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1c923-447">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1c923-447">**Key**</span></span> | <span data-ttu-id="1c923-448">hideStatusMenuIcon</span><span class="sxs-lookup"><span data-stu-id="1c923-448">hideStatusMenuIcon</span></span> |
| <span data-ttu-id="1c923-449">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1c923-449">**Data type**</span></span> | <span data-ttu-id="1c923-450">Booleano</span><span class="sxs-lookup"><span data-stu-id="1c923-450">Boolean</span></span> |
| <span data-ttu-id="1c923-451">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="1c923-451">**Possible values**</span></span> | <span data-ttu-id="1c923-452">false (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="1c923-452">false (default)</span></span> <br/> <span data-ttu-id="1c923-453">true</span><span class="sxs-lookup"><span data-stu-id="1c923-453">true</span></span> |

#### <a name="show--hide-option-to-send-feedback"></a><span data-ttu-id="1c923-454">Opzione Mostra/Nascondi per inviare commenti e suggerimenti</span><span class="sxs-lookup"><span data-stu-id="1c923-454">Show / hide option to send feedback</span></span>

<span data-ttu-id="1c923-455">Specificare se gli utenti possono inviare commenti e suggerimenti a Microsoft andando a `Help`  >  `Send Feedback` .</span><span class="sxs-lookup"><span data-stu-id="1c923-455">Specify whether users can submit feedback to Microsoft by going to `Help` > `Send Feedback`.</span></span>

|<span data-ttu-id="1c923-456">Sezione</span><span class="sxs-lookup"><span data-stu-id="1c923-456">Section</span></span>|<span data-ttu-id="1c923-457">Valore</span><span class="sxs-lookup"><span data-stu-id="1c923-457">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1c923-458">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="1c923-458">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1c923-459">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1c923-459">**Key**</span></span> | <span data-ttu-id="1c923-460">userInitiatedFeedback</span><span class="sxs-lookup"><span data-stu-id="1c923-460">userInitiatedFeedback</span></span> |
| <span data-ttu-id="1c923-461">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1c923-461">**Data type**</span></span> | <span data-ttu-id="1c923-462">Stringa</span><span class="sxs-lookup"><span data-stu-id="1c923-462">String</span></span> |
| <span data-ttu-id="1c923-463">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="1c923-463">**Possible values**</span></span> | <span data-ttu-id="1c923-464">enabled (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="1c923-464">enabled (default)</span></span> <br/> <span data-ttu-id="1c923-465">disabilitati</span><span class="sxs-lookup"><span data-stu-id="1c923-465">disabled</span></span> |
| <span data-ttu-id="1c923-466">**Comments**</span><span class="sxs-lookup"><span data-stu-id="1c923-466">**Comments**</span></span> | <span data-ttu-id="1c923-467">Disponibile in Microsoft Defender per Endpoint versione 101.19.61 o successiva.</span><span class="sxs-lookup"><span data-stu-id="1c923-467">Available in Microsoft Defender for Endpoint version 101.19.61 or higher.</span></span> |

### <a name="endpoint-detection-and-response-preferences"></a><span data-ttu-id="1c923-468">Preferenze di risposta e rilevamento degli endpoint</span><span class="sxs-lookup"><span data-stu-id="1c923-468">Endpoint detection and response preferences</span></span>

<span data-ttu-id="1c923-469">Gestire le preferenze del componente di rilevamento e risposta degli endpoint (EDR) di Microsoft Defender per Endpoint in macOS.</span><span class="sxs-lookup"><span data-stu-id="1c923-469">Manage the preferences of the endpoint detection and response (EDR) component of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="1c923-470">Sezione</span><span class="sxs-lookup"><span data-stu-id="1c923-470">Section</span></span>|<span data-ttu-id="1c923-471">Valore</span><span class="sxs-lookup"><span data-stu-id="1c923-471">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1c923-472">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="1c923-472">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1c923-473">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1c923-473">**Key**</span></span> | <span data-ttu-id="1c923-474">edr</span><span class="sxs-lookup"><span data-stu-id="1c923-474">edr</span></span> |
| <span data-ttu-id="1c923-475">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1c923-475">**Data type**</span></span> | <span data-ttu-id="1c923-476">Dizionario (preferenza annidata)</span><span class="sxs-lookup"><span data-stu-id="1c923-476">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="1c923-477">**Comments**</span><span class="sxs-lookup"><span data-stu-id="1c923-477">**Comments**</span></span> | <span data-ttu-id="1c923-478">Per una descrizione del contenuto del dizionario, vedi le sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="1c923-478">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="device-tags"></a><span data-ttu-id="1c923-479">Tag dispositivo</span><span class="sxs-lookup"><span data-stu-id="1c923-479">Device tags</span></span>

<span data-ttu-id="1c923-480">Specificare un nome di tag e il relativo valore.</span><span class="sxs-lookup"><span data-stu-id="1c923-480">Specify a tag name and its value.</span></span> 

- <span data-ttu-id="1c923-481">Il tag GROUP contrassegna il dispositivo con il valore specificato.</span><span class="sxs-lookup"><span data-stu-id="1c923-481">The GROUP tag, tags the device with the specified value.</span></span> <span data-ttu-id="1c923-482">Il tag si riflette nel portale nella pagina del dispositivo e può essere usato per filtrare e raggruppare i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="1c923-482">The tag is reflected in the portal under the device page and can be used for filtering and grouping devices.</span></span>

|<span data-ttu-id="1c923-483">Sezione</span><span class="sxs-lookup"><span data-stu-id="1c923-483">Section</span></span>|<span data-ttu-id="1c923-484">Valore</span><span class="sxs-lookup"><span data-stu-id="1c923-484">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1c923-485">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="1c923-485">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1c923-486">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1c923-486">**Key**</span></span> | <span data-ttu-id="1c923-487">tag</span><span class="sxs-lookup"><span data-stu-id="1c923-487">tags</span></span> |
| <span data-ttu-id="1c923-488">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1c923-488">**Data type**</span></span> | <span data-ttu-id="1c923-489">Dizionario (preferenza annidata)</span><span class="sxs-lookup"><span data-stu-id="1c923-489">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="1c923-490">**Comments**</span><span class="sxs-lookup"><span data-stu-id="1c923-490">**Comments**</span></span> | <span data-ttu-id="1c923-491">Per una descrizione del contenuto del dizionario, vedi le sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="1c923-491">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="type-of-tag"></a><span data-ttu-id="1c923-492">Tipo di tag</span><span class="sxs-lookup"><span data-stu-id="1c923-492">Type of tag</span></span>

<span data-ttu-id="1c923-493">Specifica il tipo di tag</span><span class="sxs-lookup"><span data-stu-id="1c923-493">Specifies the type of tag</span></span>

|<span data-ttu-id="1c923-494">Sezione</span><span class="sxs-lookup"><span data-stu-id="1c923-494">Section</span></span>|<span data-ttu-id="1c923-495">Valore</span><span class="sxs-lookup"><span data-stu-id="1c923-495">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1c923-496">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="1c923-496">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1c923-497">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1c923-497">**Key**</span></span> | <span data-ttu-id="1c923-498">chiave</span><span class="sxs-lookup"><span data-stu-id="1c923-498">key</span></span> |
| <span data-ttu-id="1c923-499">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1c923-499">**Data type**</span></span> | <span data-ttu-id="1c923-500">Stringa</span><span class="sxs-lookup"><span data-stu-id="1c923-500">String</span></span> |
| <span data-ttu-id="1c923-501">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="1c923-501">**Possible values**</span></span> | `GROUP` |

##### <a name="value-of-tag"></a><span data-ttu-id="1c923-502">Valore del tag</span><span class="sxs-lookup"><span data-stu-id="1c923-502">Value of tag</span></span>

<span data-ttu-id="1c923-503">Specifica il valore del tag</span><span class="sxs-lookup"><span data-stu-id="1c923-503">Specifies the value of tag</span></span>

|<span data-ttu-id="1c923-504">Sezione</span><span class="sxs-lookup"><span data-stu-id="1c923-504">Section</span></span>|<span data-ttu-id="1c923-505">Valore</span><span class="sxs-lookup"><span data-stu-id="1c923-505">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1c923-506">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="1c923-506">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1c923-507">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="1c923-507">**Key**</span></span> | <span data-ttu-id="1c923-508">valore</span><span class="sxs-lookup"><span data-stu-id="1c923-508">value</span></span> |
| <span data-ttu-id="1c923-509">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1c923-509">**Data type**</span></span> | <span data-ttu-id="1c923-510">Stringa</span><span class="sxs-lookup"><span data-stu-id="1c923-510">String</span></span> |
| <span data-ttu-id="1c923-511">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="1c923-511">**Possible values**</span></span> | <span data-ttu-id="1c923-512">qualsiasi stringa</span><span class="sxs-lookup"><span data-stu-id="1c923-512">any string</span></span> |

> [!IMPORTANT]  
> - <span data-ttu-id="1c923-513">È possibile impostare un solo valore per ogni tipo di tag.</span><span class="sxs-lookup"><span data-stu-id="1c923-513">Only one value per tag type can be set.</span></span>
> - <span data-ttu-id="1c923-514">Il tipo di tag è univoco e non deve essere ripetuto nello stesso profilo di configurazione.</span><span class="sxs-lookup"><span data-stu-id="1c923-514">Type of tags are unique, and should not be repeated in the same configuration profile.</span></span>

## <a name="recommended-configuration-profile"></a><span data-ttu-id="1c923-515">Profilo di configurazione consigliato</span><span class="sxs-lookup"><span data-stu-id="1c923-515">Recommended configuration profile</span></span>

<span data-ttu-id="1c923-516">Per iniziare, ti consigliamo la configurazione seguente per l'azienda per sfruttare tutte le funzionalità di protezione fornite da Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="1c923-516">To get started, we recommend the following configuration for your enterprise to take advantage of all protection features that Microsoft Defender for Endpoint provides.</span></span>

<span data-ttu-id="1c923-517">Il profilo di configurazione seguente (o, nel caso di JAMF, un elenco di proprietà che potrebbe essere caricato nel profilo di configurazione delle impostazioni personalizzate) sarà:</span><span class="sxs-lookup"><span data-stu-id="1c923-517">The following configuration profile (or, in case of JAMF, a property list that could be uploaded into the custom settings configuration profile) will:</span></span>
- <span data-ttu-id="1c923-518">Abilitare la protezione in tempo reale (RTP)</span><span class="sxs-lookup"><span data-stu-id="1c923-518">Enable real-time protection (RTP)</span></span>
- <span data-ttu-id="1c923-519">Specificare la modalità di gestione dei seguenti tipi di minacce:</span><span class="sxs-lookup"><span data-stu-id="1c923-519">Specify how the following threat types are handled:</span></span>
  - <span data-ttu-id="1c923-520">**Le applicazioni potenzialmente indesiderate sono** bloccate</span><span class="sxs-lookup"><span data-stu-id="1c923-520">**Potentially unwanted applications (PUA)** are blocked</span></span>
  - <span data-ttu-id="1c923-521">**Le bombe di** archiviazione (file con una velocità di compressione elevata) vengono verificate in Microsoft Defender per i log degli endpoint</span><span class="sxs-lookup"><span data-stu-id="1c923-521">**Archive bombs** (file with a high compression rate) are audited to Microsoft Defender for Endpoint logs</span></span>
- <span data-ttu-id="1c923-522">Abilitare gli aggiornamenti automatici delle funzionalità di intelligence per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="1c923-522">Enable automatic security intelligence updates</span></span>
- <span data-ttu-id="1c923-523">Abilitare la protezione basata sul cloud</span><span class="sxs-lookup"><span data-stu-id="1c923-523">Enable cloud-delivered protection</span></span>
- <span data-ttu-id="1c923-524">Abilitare l'invio automatico di esempi</span><span class="sxs-lookup"><span data-stu-id="1c923-524">Enable automatic sample submission</span></span>

### <a name="property-list-for-jamf-configuration-profile"></a><span data-ttu-id="1c923-525">Elenco delle proprietà per il profilo di configurazione JAMF</span><span class="sxs-lookup"><span data-stu-id="1c923-525">Property list for JAMF configuration profile</span></span>

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

### <a name="intune-profile"></a><span data-ttu-id="1c923-526">Profilo intune</span><span class="sxs-lookup"><span data-stu-id="1c923-526">Intune profile</span></span>

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

## <a name="full-configuration-profile-example"></a><span data-ttu-id="1c923-527">Esempio di profilo di configurazione completo</span><span class="sxs-lookup"><span data-stu-id="1c923-527">Full configuration profile example</span></span>

<span data-ttu-id="1c923-528">I modelli seguenti contengono voci per tutte le impostazioni descritte in questo documento e possono essere usati per scenari più avanzati in cui si desidera un maggiore controllo su Microsoft Defender for Endpoint in macOS.</span><span class="sxs-lookup"><span data-stu-id="1c923-528">The following templates contain entries for all settings described in this document and can be used for more advanced scenarios where you want more control over Microsoft Defender for Endpoint on macOS.</span></span>

### <a name="property-list-for-jamf-configuration-profile"></a><span data-ttu-id="1c923-529">Elenco delle proprietà per il profilo di configurazione JAMF</span><span class="sxs-lookup"><span data-stu-id="1c923-529">Property list for JAMF configuration profile</span></span>

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

### <a name="intune-profile"></a><span data-ttu-id="1c923-530">Profilo intune</span><span class="sxs-lookup"><span data-stu-id="1c923-530">Intune profile</span></span>

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

## <a name="property-list-validation"></a><span data-ttu-id="1c923-531">Convalida elenco proprietà</span><span class="sxs-lookup"><span data-stu-id="1c923-531">Property list validation</span></span>

<span data-ttu-id="1c923-532">L'elenco delle proprietà deve essere un file *plist* valido.</span><span class="sxs-lookup"><span data-stu-id="1c923-532">The property list must be a valid *.plist* file.</span></span> <span data-ttu-id="1c923-533">Questa operazione può essere verificata eseguendo:</span><span class="sxs-lookup"><span data-stu-id="1c923-533">This can be checked by executing:</span></span>

```bash
plutil -lint com.microsoft.wdav.plist
```
```Output
com.microsoft.wdav.plist: OK
```

<span data-ttu-id="1c923-534">Se il file è ben formato, il comando precedente restituisce un `OK` codice di uscita di `0` .</span><span class="sxs-lookup"><span data-stu-id="1c923-534">If the file is well-formed, the above command outputs `OK` and returns an exit code of `0`.</span></span> <span data-ttu-id="1c923-535">In caso contrario, viene visualizzato un errore che descrive il problema e il comando restituisce un codice di uscita di `1` .</span><span class="sxs-lookup"><span data-stu-id="1c923-535">Otherwise, an error that describes the issue is displayed and the command returns an exit code of `1`.</span></span>

## <a name="configuration-profile-deployment"></a><span data-ttu-id="1c923-536">Distribuzione dei profili di configurazione</span><span class="sxs-lookup"><span data-stu-id="1c923-536">Configuration profile deployment</span></span>

<span data-ttu-id="1c923-537">Dopo aver creato il profilo di configurazione per l'organizzazione, è possibile distribuirlo tramite la console di gestione in uso.</span><span class="sxs-lookup"><span data-stu-id="1c923-537">Once you've built the configuration profile for your enterprise, you can deploy it through the management console that your enterprise is using.</span></span> <span data-ttu-id="1c923-538">Le sezioni seguenti forniscono istruzioni su come distribuire questo profilo usando JAMF e Intune.</span><span class="sxs-lookup"><span data-stu-id="1c923-538">The following sections provide instructions on how to deploy this profile using JAMF and Intune.</span></span>

### <a name="jamf-deployment"></a><span data-ttu-id="1c923-539">Distribuzione JAMF</span><span class="sxs-lookup"><span data-stu-id="1c923-539">JAMF deployment</span></span>

<span data-ttu-id="1c923-540">Dalla console JAMF apri **Profili** di configurazione computer, passa al profilo di configurazione che vuoi usare, quindi  >  seleziona **Impostazioni personalizzate.**</span><span class="sxs-lookup"><span data-stu-id="1c923-540">From the JAMF console, open **Computers** > **Configuration Profiles**, navigate to the configuration profile you'd like to use, then select **Custom Settings**.</span></span> <span data-ttu-id="1c923-541">Crea una voce con `com.microsoft.wdav` come dominio di preferenza e carica il file *plist* prodotto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="1c923-541">Create an entry with `com.microsoft.wdav` as the preference domain and upload the *.plist* produced earlier.</span></span>

>[!CAUTION]
><span data-ttu-id="1c923-542">È necessario immettere il dominio di preferenza corretto ( ); in caso contrario, le preferenze non verranno `com.microsoft.wdav` riconosciute da Microsoft Defender per Endpoint.</span><span class="sxs-lookup"><span data-stu-id="1c923-542">You must enter the correct preference domain (`com.microsoft.wdav`); otherwise, the preferences will not be recognized by Microsoft Defender for Endpoint.</span></span>

### <a name="intune-deployment"></a><span data-ttu-id="1c923-543">Distribuzione di Intune</span><span class="sxs-lookup"><span data-stu-id="1c923-543">Intune deployment</span></span>

1. <span data-ttu-id="1c923-544">Aprire **Gestisci**  >  **configurazione dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="1c923-544">Open **Manage** > **Device configuration**.</span></span> <span data-ttu-id="1c923-545">Selezionare **Gestisci**  >  **profili**  >  **Crea profilo**.</span><span class="sxs-lookup"><span data-stu-id="1c923-545">Select **Manage** > **Profiles** > **Create Profile**.</span></span>

2. <span data-ttu-id="1c923-546">Scegliere un nome per il profilo.</span><span class="sxs-lookup"><span data-stu-id="1c923-546">Choose a name for the profile.</span></span> <span data-ttu-id="1c923-547">Modificare **Platform=macOS** in **Profile type=Custom**.</span><span class="sxs-lookup"><span data-stu-id="1c923-547">Change **Platform=macOS** to **Profile type=Custom**.</span></span> <span data-ttu-id="1c923-548">Selezionare Configura.</span><span class="sxs-lookup"><span data-stu-id="1c923-548">Select Configure.</span></span>

3. <span data-ttu-id="1c923-549">Salvare il file plist prodotto in precedenza come `com.microsoft.wdav.xml` .</span><span class="sxs-lookup"><span data-stu-id="1c923-549">Save the .plist produced earlier as `com.microsoft.wdav.xml`.</span></span>

4. <span data-ttu-id="1c923-550">Immettere `com.microsoft.wdav` come nome del profilo di configurazione **personalizzato**.</span><span class="sxs-lookup"><span data-stu-id="1c923-550">Enter `com.microsoft.wdav` as the **custom configuration profile name**.</span></span>

5. <span data-ttu-id="1c923-551">Apri il profilo di configurazione e carica il `com.microsoft.wdav.xml` file.</span><span class="sxs-lookup"><span data-stu-id="1c923-551">Open the configuration profile and upload the `com.microsoft.wdav.xml` file.</span></span> <span data-ttu-id="1c923-552">Questo file è stato creato nel passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="1c923-552">(This file was created in step 3.)</span></span>

6. <span data-ttu-id="1c923-553">Seleziona **OK**.</span><span class="sxs-lookup"><span data-stu-id="1c923-553">Select **OK**.</span></span>

7. <span data-ttu-id="1c923-554">Selezionare **Gestisci**  >  **assegnazioni**.</span><span class="sxs-lookup"><span data-stu-id="1c923-554">Select **Manage** > **Assignments**.</span></span> <span data-ttu-id="1c923-555">Nella scheda **Includi** seleziona **Assegna a tutti gli utenti & Tutti i dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="1c923-555">In the **Include** tab, select **Assign to All Users & All devices**.</span></span>

>[!CAUTION]
><span data-ttu-id="1c923-556">È necessario immettere il nome del profilo di configurazione personalizzato corretto. in caso contrario, queste preferenze non verranno riconosciute da Microsoft Defender per Endpoint.</span><span class="sxs-lookup"><span data-stu-id="1c923-556">You must enter the correct custom configuration profile name; otherwise, these preferences will not be recognized by Microsoft Defender for Endpoint.</span></span>

## <a name="resources"></a><span data-ttu-id="1c923-557">Risorse</span><span class="sxs-lookup"><span data-stu-id="1c923-557">Resources</span></span>

- [<span data-ttu-id="1c923-558">Informazioni di riferimento sui profili di configurazione (documentazione per sviluppatori Apple)</span><span class="sxs-lookup"><span data-stu-id="1c923-558">Configuration Profile Reference (Apple developer documentation)</span></span>](https://developer.apple.com/business/documentation/Configuration-Profile-Reference.pdf)
