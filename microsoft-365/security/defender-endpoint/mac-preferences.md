---
title: Impostare le preferenze per Microsoft Defender ATP per Mac
description: Configurare Microsoft Defender ATP per Mac nelle organizzazioni aziendali.
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
ms.openlocfilehash: 578830d44a9a69c3ccafd78ceaf59ddfe100e43f
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068893"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="9f427-104">Impostare le preferenze per Microsoft Defender per Endpoint per Mac</span><span class="sxs-lookup"><span data-stu-id="9f427-104">Set preferences for Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="9f427-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="9f427-105">**Applies to:**</span></span>

- [<span data-ttu-id="9f427-106">Microsoft Defender per Endpoint per Mac</span><span class="sxs-lookup"><span data-stu-id="9f427-106">Microsoft Defender for Endpoint for Mac</span></span>](microsoft-defender-endpoint-mac.md)

>[!IMPORTANT]
><span data-ttu-id="9f427-107">Questo articolo contiene istruzioni su come impostare le preferenze per Microsoft Defender per Endpoint per Mac nelle organizzazioni aziendali.</span><span class="sxs-lookup"><span data-stu-id="9f427-107">This article contains instructions for how to set preferences for Microsoft Defender for Endpoint for Mac in enterprise organizations.</span></span> <span data-ttu-id="9f427-108">Per configurare Microsoft Defender per Endpoint per Mac usando l'interfaccia della riga di comando, vedi [Risorse](mac-resources.md#configuring-from-the-command-line).</span><span class="sxs-lookup"><span data-stu-id="9f427-108">To configure Microsoft Defender for Endpoint for Mac using the command-line interface, see [Resources](mac-resources.md#configuring-from-the-command-line).</span></span>

## <a name="summary"></a><span data-ttu-id="9f427-109">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="9f427-109">Summary</span></span>

<span data-ttu-id="9f427-110">Nelle organizzazioni aziendali, Microsoft Defender per Endpoint per Mac può essere gestito tramite un profilo di configurazione distribuito utilizzando uno dei diversi strumenti di gestione.</span><span class="sxs-lookup"><span data-stu-id="9f427-110">In enterprise organizations, Microsoft Defender for Endpoint for Mac can be managed through a configuration profile that is deployed by using one of several management tools.</span></span> <span data-ttu-id="9f427-111">Le preferenze gestite dal team delle operazioni di sicurezza hanno la precedenza sulle preferenze impostate localmente nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9f427-111">Preferences that are managed by your security operations team take precedence over preferences that are set locally on the device.</span></span> <span data-ttu-id="9f427-112">La modifica delle preferenze impostate tramite il profilo di configurazione richiede privilegi inoltrati e non è disponibile per gli utenti senza autorizzazioni amministrative.</span><span class="sxs-lookup"><span data-stu-id="9f427-112">Changing the preferences that are set through the configuration profile requires escalated privileges and is not available for users without administrative permissions.</span></span>

<span data-ttu-id="9f427-113">Questo articolo descrive la struttura del profilo di configurazione, include un profilo consigliato che puoi usare per iniziare e fornisce istruzioni su come distribuire il profilo.</span><span class="sxs-lookup"><span data-stu-id="9f427-113">This article describes the structure of the configuration profile, includes a recommended profile that you can use to get started, and provides instructions on how to deploy the profile.</span></span>

## <a name="configuration-profile-structure"></a><span data-ttu-id="9f427-114">Struttura del profilo di configurazione</span><span class="sxs-lookup"><span data-stu-id="9f427-114">Configuration profile structure</span></span>

<span data-ttu-id="9f427-115">Il profilo di configurazione è un file *plist* costituito da voci identificate da una chiave (che indica il nome della preferenza), seguita da un valore, che dipende dalla natura della preferenza.</span><span class="sxs-lookup"><span data-stu-id="9f427-115">The configuration profile is a *.plist* file that consists of entries identified by a key (which denotes the name of the preference), followed by a value, which depends on the nature of the preference.</span></span> <span data-ttu-id="9f427-116">I valori possono essere semplici (ad esempio un valore numerico) o complessi, ad esempio un elenco nidificato di preferenze.</span><span class="sxs-lookup"><span data-stu-id="9f427-116">Values can either be simple (such as a numerical value) or complex, such as a nested list of preferences.</span></span>

>[!CAUTION]
><span data-ttu-id="9f427-117">Il layout del profilo di configurazione dipende dalla console di gestione in uso.</span><span class="sxs-lookup"><span data-stu-id="9f427-117">The layout of the configuration profile depends on the management console that you are using.</span></span> <span data-ttu-id="9f427-118">Le sezioni seguenti contengono esempi di profili di configurazione per JAMF e Intune.</span><span class="sxs-lookup"><span data-stu-id="9f427-118">The following sections contain examples of configuration profiles for JAMF and Intune.</span></span>

<span data-ttu-id="9f427-119">Il livello superiore del profilo di configurazione include le preferenze e le voci a livello di prodotto per le sottoaree di Microsoft Defender per Endpoint, che vengono illustrate in modo più dettagliato nelle sezioni successive.</span><span class="sxs-lookup"><span data-stu-id="9f427-119">The top level of the configuration profile includes product-wide preferences and entries for subareas of Microsoft Defender for Endpoint, which are explained in more detail in the next sections.</span></span>

### <a name="antivirus-engine-preferences"></a><span data-ttu-id="9f427-120">Preferenze del motore antivirus</span><span class="sxs-lookup"><span data-stu-id="9f427-120">Antivirus engine preferences</span></span>

<span data-ttu-id="9f427-121">La *sezione antivirusEngine* del profilo di configurazione viene usata per gestire le preferenze del componente antivirus di Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="9f427-121">The *antivirusEngine* section of the configuration profile is used to manage the preferences of the antivirus component of Microsoft Defender for Endpoint.</span></span>

|||
|:---|:---|
| <span data-ttu-id="9f427-122">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="9f427-122">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9f427-123">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="9f427-123">**Key**</span></span> | <span data-ttu-id="9f427-124">antivirusEngine</span><span class="sxs-lookup"><span data-stu-id="9f427-124">antivirusEngine</span></span> |
| <span data-ttu-id="9f427-125">**Data type**</span><span class="sxs-lookup"><span data-stu-id="9f427-125">**Data type**</span></span> | <span data-ttu-id="9f427-126">Dizionario (preferenza annidata)</span><span class="sxs-lookup"><span data-stu-id="9f427-126">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="9f427-127">**Comments**</span><span class="sxs-lookup"><span data-stu-id="9f427-127">**Comments**</span></span> | <span data-ttu-id="9f427-128">Per una descrizione del contenuto del dizionario, vedi le sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="9f427-128">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-real-time-protection"></a><span data-ttu-id="9f427-129">Abilitare/disabilitare la protezione in tempo reale</span><span class="sxs-lookup"><span data-stu-id="9f427-129">Enable / disable real-time protection</span></span>

<span data-ttu-id="9f427-130">Specificare se abilitare la protezione in tempo reale, che analizza i file man a cui si accede.</span><span class="sxs-lookup"><span data-stu-id="9f427-130">Specify whether to enable real-time protection, which scans files as they are accessed.</span></span>

|||
|:---|:---|
| <span data-ttu-id="9f427-131">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="9f427-131">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9f427-132">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="9f427-132">**Key**</span></span> | <span data-ttu-id="9f427-133">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="9f427-133">enableRealTimeProtection</span></span> |
| <span data-ttu-id="9f427-134">**Data type**</span><span class="sxs-lookup"><span data-stu-id="9f427-134">**Data type**</span></span> | <span data-ttu-id="9f427-135">Booleano</span><span class="sxs-lookup"><span data-stu-id="9f427-135">Boolean</span></span> |
| <span data-ttu-id="9f427-136">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="9f427-136">**Possible values**</span></span> | <span data-ttu-id="9f427-137">true (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="9f427-137">true (default)</span></span> <br/> <span data-ttu-id="9f427-138">false</span><span class="sxs-lookup"><span data-stu-id="9f427-138">false</span></span> |

#### <a name="enable--disable-passive-mode"></a><span data-ttu-id="9f427-139">Abilitare/disabilitare la modalità passiva</span><span class="sxs-lookup"><span data-stu-id="9f427-139">Enable / disable passive mode</span></span>

<span data-ttu-id="9f427-140">Specificare se il motore antivirus viene eseguito in modalità passiva.</span><span class="sxs-lookup"><span data-stu-id="9f427-140">Specify whether the antivirus engine runs in passive mode.</span></span> <span data-ttu-id="9f427-141">La modalità passiva ha le implicazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9f427-141">Passive mode has the following implications:</span></span> 
- <span data-ttu-id="9f427-142">La protezione in tempo reale è disattivata</span><span class="sxs-lookup"><span data-stu-id="9f427-142">Real-time protection is turned off</span></span>
- <span data-ttu-id="9f427-143">L'analisi su richiesta è attivata</span><span class="sxs-lookup"><span data-stu-id="9f427-143">On-demand scanning is turned on</span></span>
- <span data-ttu-id="9f427-144">La correzione automatica delle minacce è disattivata</span><span class="sxs-lookup"><span data-stu-id="9f427-144">Automatic threat remediation is turned off</span></span>
- <span data-ttu-id="9f427-145">Gli aggiornamenti delle funzionalità di intelligence per la sicurezza sono attivati</span><span class="sxs-lookup"><span data-stu-id="9f427-145">Security intelligence updates are turned on</span></span>
- <span data-ttu-id="9f427-146">L'icona del menu Stato è nascosta</span><span class="sxs-lookup"><span data-stu-id="9f427-146">Status menu icon is hidden</span></span>

|||
|:---|:---|
| <span data-ttu-id="9f427-147">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="9f427-147">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9f427-148">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="9f427-148">**Key**</span></span> | <span data-ttu-id="9f427-149">passiveMode</span><span class="sxs-lookup"><span data-stu-id="9f427-149">passiveMode</span></span> |
| <span data-ttu-id="9f427-150">**Data type**</span><span class="sxs-lookup"><span data-stu-id="9f427-150">**Data type**</span></span> | <span data-ttu-id="9f427-151">Booleano</span><span class="sxs-lookup"><span data-stu-id="9f427-151">Boolean</span></span> |
| <span data-ttu-id="9f427-152">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="9f427-152">**Possible values**</span></span> | <span data-ttu-id="9f427-153">false (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="9f427-153">false (default)</span></span> <br/> <span data-ttu-id="9f427-154">true</span><span class="sxs-lookup"><span data-stu-id="9f427-154">true</span></span> |
| <span data-ttu-id="9f427-155">**Comments**</span><span class="sxs-lookup"><span data-stu-id="9f427-155">**Comments**</span></span> | <span data-ttu-id="9f427-156">Disponibile in Microsoft Defender per Endpoint versione 100.67.60 o successiva.</span><span class="sxs-lookup"><span data-stu-id="9f427-156">Available in Microsoft Defender for Endpoint version 100.67.60 or higher.</span></span> |

#### <a name="exclusion-merge-policy"></a><span data-ttu-id="9f427-157">Criteri di unione esclusioni</span><span class="sxs-lookup"><span data-stu-id="9f427-157">Exclusion merge policy</span></span>

<span data-ttu-id="9f427-158">Specificare i criteri di unione per le esclusioni.</span><span class="sxs-lookup"><span data-stu-id="9f427-158">Specify the merge policy for exclusions.</span></span> <span data-ttu-id="9f427-159">Può trattarsi di una combinazione di esclusioni definite dall'amministratore e definite dall'utente ( ) o solo di esclusioni definite `merge` dall'amministratore ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="9f427-159">This can be a combination of administrator-defined and user-defined exclusions (`merge`) or only administrator-defined exclusions (`admin_only`).</span></span> <span data-ttu-id="9f427-160">Questa impostazione può essere utilizzata per impedire agli utenti locali di definire le proprie esclusioni.</span><span class="sxs-lookup"><span data-stu-id="9f427-160">This setting can be used to restrict local users from defining their own exclusions.</span></span>

|||
|:---|:---|
| <span data-ttu-id="9f427-161">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="9f427-161">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9f427-162">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="9f427-162">**Key**</span></span> | <span data-ttu-id="9f427-163">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="9f427-163">exclusionsMergePolicy</span></span> |
| <span data-ttu-id="9f427-164">**Data type**</span><span class="sxs-lookup"><span data-stu-id="9f427-164">**Data type**</span></span> | <span data-ttu-id="9f427-165">Stringa</span><span class="sxs-lookup"><span data-stu-id="9f427-165">String</span></span> |
| <span data-ttu-id="9f427-166">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="9f427-166">**Possible values**</span></span> | <span data-ttu-id="9f427-167">merge (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="9f427-167">merge (default)</span></span> <br/> <span data-ttu-id="9f427-168">admin_only</span><span class="sxs-lookup"><span data-stu-id="9f427-168">admin_only</span></span> |
| <span data-ttu-id="9f427-169">**Comments**</span><span class="sxs-lookup"><span data-stu-id="9f427-169">**Comments**</span></span> | <span data-ttu-id="9f427-170">Disponibile in Microsoft Defender per Endpoint versione 100.83.73 o successiva.</span><span class="sxs-lookup"><span data-stu-id="9f427-170">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="scan-exclusions"></a><span data-ttu-id="9f427-171">Esclusioni analisi</span><span class="sxs-lookup"><span data-stu-id="9f427-171">Scan exclusions</span></span>

<span data-ttu-id="9f427-172">Specificare le entità escluse dall'analisi.</span><span class="sxs-lookup"><span data-stu-id="9f427-172">Specify entities excluded from being scanned.</span></span> <span data-ttu-id="9f427-173">Le esclusioni possono essere specificate da percorsi completi, estensioni o nomi di file.</span><span class="sxs-lookup"><span data-stu-id="9f427-173">Exclusions can be specified by full paths, extensions, or file names.</span></span>

|||
|:---|:---|
| <span data-ttu-id="9f427-174">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="9f427-174">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9f427-175">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="9f427-175">**Key**</span></span> | <span data-ttu-id="9f427-176">esclusioni</span><span class="sxs-lookup"><span data-stu-id="9f427-176">exclusions</span></span> |
| <span data-ttu-id="9f427-177">**Data type**</span><span class="sxs-lookup"><span data-stu-id="9f427-177">**Data type**</span></span> | <span data-ttu-id="9f427-178">Dizionario (preferenza annidata)</span><span class="sxs-lookup"><span data-stu-id="9f427-178">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="9f427-179">**Comments**</span><span class="sxs-lookup"><span data-stu-id="9f427-179">**Comments**</span></span> | <span data-ttu-id="9f427-180">Per una descrizione del contenuto del dizionario, vedi le sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="9f427-180">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="type-of-exclusion"></a><span data-ttu-id="9f427-181">Tipo di esclusione</span><span class="sxs-lookup"><span data-stu-id="9f427-181">Type of exclusion</span></span>

<span data-ttu-id="9f427-182">Specificare il contenuto escluso dall'analisi in base al tipo.</span><span class="sxs-lookup"><span data-stu-id="9f427-182">Specify content excluded from being scanned by type.</span></span>

|||
|:---|:---|
| <span data-ttu-id="9f427-183">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="9f427-183">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9f427-184">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="9f427-184">**Key**</span></span> | <span data-ttu-id="9f427-185">$type</span><span class="sxs-lookup"><span data-stu-id="9f427-185">$type</span></span> |
| <span data-ttu-id="9f427-186">**Data type**</span><span class="sxs-lookup"><span data-stu-id="9f427-186">**Data type**</span></span> | <span data-ttu-id="9f427-187">Stringa</span><span class="sxs-lookup"><span data-stu-id="9f427-187">String</span></span> |
| <span data-ttu-id="9f427-188">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="9f427-188">**Possible values**</span></span> | <span data-ttu-id="9f427-189">excludedPath</span><span class="sxs-lookup"><span data-stu-id="9f427-189">excludedPath</span></span> <br/> <span data-ttu-id="9f427-190">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="9f427-190">excludedFileExtension</span></span> <br/> <span data-ttu-id="9f427-191">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="9f427-191">excludedFileName</span></span> |

##### <a name="path-to-excluded-content"></a><span data-ttu-id="9f427-192">Percorso del contenuto escluso</span><span class="sxs-lookup"><span data-stu-id="9f427-192">Path to excluded content</span></span>

<span data-ttu-id="9f427-193">Specificare il contenuto escluso dall'analisi tramite il percorso completo del file.</span><span class="sxs-lookup"><span data-stu-id="9f427-193">Specify content excluded from being scanned by full file path.</span></span>

|||
|:---|:---|
| <span data-ttu-id="9f427-194">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="9f427-194">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9f427-195">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="9f427-195">**Key**</span></span> | <span data-ttu-id="9f427-196">path</span><span class="sxs-lookup"><span data-stu-id="9f427-196">path</span></span> |
| <span data-ttu-id="9f427-197">**Data type**</span><span class="sxs-lookup"><span data-stu-id="9f427-197">**Data type**</span></span> | <span data-ttu-id="9f427-198">Stringa</span><span class="sxs-lookup"><span data-stu-id="9f427-198">String</span></span> |
| <span data-ttu-id="9f427-199">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="9f427-199">**Possible values**</span></span> | <span data-ttu-id="9f427-200">percorsi validi</span><span class="sxs-lookup"><span data-stu-id="9f427-200">valid paths</span></span> |
| <span data-ttu-id="9f427-201">**Comments**</span><span class="sxs-lookup"><span data-stu-id="9f427-201">**Comments**</span></span> | <span data-ttu-id="9f427-202">Applicabile solo se *$type* *è excludedPath*</span><span class="sxs-lookup"><span data-stu-id="9f427-202">Applicable only if *$type* is *excludedPath*</span></span> |

##### <a name="path-type-file--directory"></a><span data-ttu-id="9f427-203">Tipo di percorso (file/directory)</span><span class="sxs-lookup"><span data-stu-id="9f427-203">Path type (file / directory)</span></span>

<span data-ttu-id="9f427-204">Indicare se la *proprietà path* fa riferimento a un file o a una directory.</span><span class="sxs-lookup"><span data-stu-id="9f427-204">Indicate if the *path* property refers to a file or directory.</span></span> 

|||
|:---|:---|
| <span data-ttu-id="9f427-205">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="9f427-205">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9f427-206">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="9f427-206">**Key**</span></span> | <span data-ttu-id="9f427-207">isDirectory</span><span class="sxs-lookup"><span data-stu-id="9f427-207">isDirectory</span></span> |
| <span data-ttu-id="9f427-208">**Data type**</span><span class="sxs-lookup"><span data-stu-id="9f427-208">**Data type**</span></span> | <span data-ttu-id="9f427-209">Booleano</span><span class="sxs-lookup"><span data-stu-id="9f427-209">Boolean</span></span> |
| <span data-ttu-id="9f427-210">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="9f427-210">**Possible values**</span></span> | <span data-ttu-id="9f427-211">false (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="9f427-211">false (default)</span></span> <br/> <span data-ttu-id="9f427-212">true</span><span class="sxs-lookup"><span data-stu-id="9f427-212">true</span></span> |
| <span data-ttu-id="9f427-213">**Comments**</span><span class="sxs-lookup"><span data-stu-id="9f427-213">**Comments**</span></span> | <span data-ttu-id="9f427-214">Applicabile solo se *$type* *è excludedPath*</span><span class="sxs-lookup"><span data-stu-id="9f427-214">Applicable only if *$type* is *excludedPath*</span></span> |

##### <a name="file-extension-excluded-from-the-scan"></a><span data-ttu-id="9f427-215">Estensione di file esclusa dall'analisi</span><span class="sxs-lookup"><span data-stu-id="9f427-215">File extension excluded from the scan</span></span>

<span data-ttu-id="9f427-216">Specificare il contenuto escluso dall'analisi per estensione di file.</span><span class="sxs-lookup"><span data-stu-id="9f427-216">Specify content excluded from being scanned by file extension.</span></span>

|||
|:---|:---|
| <span data-ttu-id="9f427-217">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="9f427-217">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9f427-218">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="9f427-218">**Key**</span></span> | <span data-ttu-id="9f427-219">extension</span><span class="sxs-lookup"><span data-stu-id="9f427-219">extension</span></span> |
| <span data-ttu-id="9f427-220">**Data type**</span><span class="sxs-lookup"><span data-stu-id="9f427-220">**Data type**</span></span> | <span data-ttu-id="9f427-221">Stringa</span><span class="sxs-lookup"><span data-stu-id="9f427-221">String</span></span> |
| <span data-ttu-id="9f427-222">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="9f427-222">**Possible values**</span></span> | <span data-ttu-id="9f427-223">estensioni di file valide</span><span class="sxs-lookup"><span data-stu-id="9f427-223">valid file extensions</span></span> |
| <span data-ttu-id="9f427-224">**Comments**</span><span class="sxs-lookup"><span data-stu-id="9f427-224">**Comments**</span></span> | <span data-ttu-id="9f427-225">Applicabile solo se *$type* *è excludedFileExtension*</span><span class="sxs-lookup"><span data-stu-id="9f427-225">Applicable only if *$type* is *excludedFileExtension*</span></span> |

##### <a name="process-excluded-from-the-scan"></a><span data-ttu-id="9f427-226">Processo escluso dall'analisi</span><span class="sxs-lookup"><span data-stu-id="9f427-226">Process excluded from the scan</span></span>

<span data-ttu-id="9f427-227">Specificare un processo per il quale tutte le attività dei file vengono escluse dall'analisi.</span><span class="sxs-lookup"><span data-stu-id="9f427-227">Specify a process for which all file activity is excluded from scanning.</span></span> <span data-ttu-id="9f427-228">Il processo può essere specificato in base al nome (ad esempio) o al `cat` percorso completo (ad `/bin/cat` esempio).</span><span class="sxs-lookup"><span data-stu-id="9f427-228">The process can be specified either by its name (e.g. `cat`) or full path (e.g. `/bin/cat`).</span></span>

|||
|:---|:---|
| <span data-ttu-id="9f427-229">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="9f427-229">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9f427-230">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="9f427-230">**Key**</span></span> | <span data-ttu-id="9f427-231">name</span><span class="sxs-lookup"><span data-stu-id="9f427-231">name</span></span> |
| <span data-ttu-id="9f427-232">**Data type**</span><span class="sxs-lookup"><span data-stu-id="9f427-232">**Data type**</span></span> | <span data-ttu-id="9f427-233">Stringa</span><span class="sxs-lookup"><span data-stu-id="9f427-233">String</span></span> |
| <span data-ttu-id="9f427-234">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="9f427-234">**Possible values**</span></span> | <span data-ttu-id="9f427-235">qualsiasi stringa</span><span class="sxs-lookup"><span data-stu-id="9f427-235">any string</span></span> |
| <span data-ttu-id="9f427-236">**Comments**</span><span class="sxs-lookup"><span data-stu-id="9f427-236">**Comments**</span></span> | <span data-ttu-id="9f427-237">Applicabile solo se *$type* *è excludedFileName*</span><span class="sxs-lookup"><span data-stu-id="9f427-237">Applicable only if *$type* is *excludedFileName*</span></span> |

#### <a name="allowed-threats"></a><span data-ttu-id="9f427-238">Minacce consentite</span><span class="sxs-lookup"><span data-stu-id="9f427-238">Allowed threats</span></span>

<span data-ttu-id="9f427-239">Specifica le minacce in base al nome che non sono bloccate da Defender per Endpoint per Mac.</span><span class="sxs-lookup"><span data-stu-id="9f427-239">Specify threats by name that are not blocked by Defender for Endpoint for Mac.</span></span> <span data-ttu-id="9f427-240">L'esecuzione di queste minacce sarà consentita.</span><span class="sxs-lookup"><span data-stu-id="9f427-240">These threats will be allowed to run.</span></span>

|||
|:---|:---|
| <span data-ttu-id="9f427-241">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="9f427-241">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9f427-242">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="9f427-242">**Key**</span></span> | <span data-ttu-id="9f427-243">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="9f427-243">allowedThreats</span></span> |
| <span data-ttu-id="9f427-244">**Data type**</span><span class="sxs-lookup"><span data-stu-id="9f427-244">**Data type**</span></span> | <span data-ttu-id="9f427-245">Matrice di stringhe</span><span class="sxs-lookup"><span data-stu-id="9f427-245">Array of strings</span></span> |

#### <a name="disallowed-threat-actions"></a><span data-ttu-id="9f427-246">Azioni di minaccia non consentite</span><span class="sxs-lookup"><span data-stu-id="9f427-246">Disallowed threat actions</span></span>

<span data-ttu-id="9f427-247">Limita le azioni che l'utente locale di un dispositivo può intraprendere quando vengono rilevate minacce.</span><span class="sxs-lookup"><span data-stu-id="9f427-247">Restricts the actions that the local user of a device can take when threats are detected.</span></span> <span data-ttu-id="9f427-248">Le azioni incluse in questo elenco non vengono visualizzate nell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="9f427-248">The actions included in this list are not displayed in the user interface.</span></span>

|||
|:---|:---|
| <span data-ttu-id="9f427-249">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="9f427-249">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9f427-250">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="9f427-250">**Key**</span></span> | <span data-ttu-id="9f427-251">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="9f427-251">disallowedThreatActions</span></span> |
| <span data-ttu-id="9f427-252">**Data type**</span><span class="sxs-lookup"><span data-stu-id="9f427-252">**Data type**</span></span> | <span data-ttu-id="9f427-253">Matrice di stringhe</span><span class="sxs-lookup"><span data-stu-id="9f427-253">Array of strings</span></span> |
| <span data-ttu-id="9f427-254">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="9f427-254">**Possible values**</span></span> | <span data-ttu-id="9f427-255">allow (impedisce agli utenti di consentire minacce)</span><span class="sxs-lookup"><span data-stu-id="9f427-255">allow (restricts users from allowing threats)</span></span> <br/> <span data-ttu-id="9f427-256">restore (impedisce agli utenti di ripristinare le minacce dalla quarantena)</span><span class="sxs-lookup"><span data-stu-id="9f427-256">restore (restricts users from restoring threats from the quarantine)</span></span> |
| <span data-ttu-id="9f427-257">**Comments**</span><span class="sxs-lookup"><span data-stu-id="9f427-257">**Comments**</span></span> | <span data-ttu-id="9f427-258">Disponibile in Microsoft Defender per Endpoint versione 100.83.73 o successiva.</span><span class="sxs-lookup"><span data-stu-id="9f427-258">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="threat-type-settings"></a><span data-ttu-id="9f427-259">Impostazioni del tipo di minaccia</span><span class="sxs-lookup"><span data-stu-id="9f427-259">Threat type settings</span></span>

<span data-ttu-id="9f427-260">Specifica come vengono gestiti determinati tipi di minacce da Microsoft Defender per Endpoint per Mac.</span><span class="sxs-lookup"><span data-stu-id="9f427-260">Specify how certain threat types are handled by Microsoft Defender for Endpoint for Mac.</span></span>

|||
|:---|:---|
| <span data-ttu-id="9f427-261">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="9f427-261">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9f427-262">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="9f427-262">**Key**</span></span> | <span data-ttu-id="9f427-263">threatTypeSettings</span><span class="sxs-lookup"><span data-stu-id="9f427-263">threatTypeSettings</span></span> |
| <span data-ttu-id="9f427-264">**Data type**</span><span class="sxs-lookup"><span data-stu-id="9f427-264">**Data type**</span></span> | <span data-ttu-id="9f427-265">Dizionario (preferenza annidata)</span><span class="sxs-lookup"><span data-stu-id="9f427-265">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="9f427-266">**Comments**</span><span class="sxs-lookup"><span data-stu-id="9f427-266">**Comments**</span></span> | <span data-ttu-id="9f427-267">Per una descrizione del contenuto del dizionario, vedi le sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="9f427-267">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="threat-type"></a><span data-ttu-id="9f427-268">Tipo di minaccia</span><span class="sxs-lookup"><span data-stu-id="9f427-268">Threat type</span></span>

<span data-ttu-id="9f427-269">Specificare i tipi di minaccia.</span><span class="sxs-lookup"><span data-stu-id="9f427-269">Specify threat types.</span></span>

|||
|:---|:---|
| <span data-ttu-id="9f427-270">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="9f427-270">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9f427-271">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="9f427-271">**Key**</span></span> | <span data-ttu-id="9f427-272">chiave</span><span class="sxs-lookup"><span data-stu-id="9f427-272">key</span></span> |
| <span data-ttu-id="9f427-273">**Data type**</span><span class="sxs-lookup"><span data-stu-id="9f427-273">**Data type**</span></span> | <span data-ttu-id="9f427-274">Stringa</span><span class="sxs-lookup"><span data-stu-id="9f427-274">String</span></span> |
| <span data-ttu-id="9f427-275">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="9f427-275">**Possible values**</span></span> | <span data-ttu-id="9f427-276">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="9f427-276">potentially_unwanted_application</span></span> <br/> <span data-ttu-id="9f427-277">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="9f427-277">archive_bomb</span></span> |

##### <a name="action-to-take"></a><span data-ttu-id="9f427-278">Procedura da seguire</span><span class="sxs-lookup"><span data-stu-id="9f427-278">Action to take</span></span>

<span data-ttu-id="9f427-279">Specificare l'azione da eseguire quando viene rilevata una minaccia del tipo specificato nella sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="9f427-279">Specify what action to take when a threat of the type specified in the preceding section is detected.</span></span> <span data-ttu-id="9f427-280">Scegliere una delle seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="9f427-280">Choose from the following options:</span></span>

- <span data-ttu-id="9f427-281">**Controllo**: il dispositivo non è protetto da questo tipo di minaccia, ma viene registrata una voce relativa alla minaccia.</span><span class="sxs-lookup"><span data-stu-id="9f427-281">**Audit**: your device is not protected against this type of threat, but an entry about the threat is logged.</span></span>
- <span data-ttu-id="9f427-282">**Blocca**: il dispositivo è protetto da questo tipo di minaccia e si viene informati nell'interfaccia utente e nella console di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="9f427-282">**Block**: your device is protected against this type of threat and you are notified in the user interface and the security console.</span></span>
- <span data-ttu-id="9f427-283">**Disattivato:** il dispositivo non è protetto da questo tipo di minaccia e non viene registrato nulla.</span><span class="sxs-lookup"><span data-stu-id="9f427-283">**Off**: your device is not protected against this type of threat and nothing is logged.</span></span>

|||
|:---|:---|
| <span data-ttu-id="9f427-284">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="9f427-284">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9f427-285">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="9f427-285">**Key**</span></span> | <span data-ttu-id="9f427-286">valore</span><span class="sxs-lookup"><span data-stu-id="9f427-286">value</span></span> |
| <span data-ttu-id="9f427-287">**Data type**</span><span class="sxs-lookup"><span data-stu-id="9f427-287">**Data type**</span></span> | <span data-ttu-id="9f427-288">Stringa</span><span class="sxs-lookup"><span data-stu-id="9f427-288">String</span></span> |
| <span data-ttu-id="9f427-289">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="9f427-289">**Possible values**</span></span> | <span data-ttu-id="9f427-290">audit (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="9f427-290">audit (default)</span></span> <br/> <span data-ttu-id="9f427-291">blocco</span><span class="sxs-lookup"><span data-stu-id="9f427-291">block</span></span> <br/> <span data-ttu-id="9f427-292">off</span><span class="sxs-lookup"><span data-stu-id="9f427-292">off</span></span> |

#### <a name="threat-type-settings-merge-policy"></a><span data-ttu-id="9f427-293">Criteri di unione delle impostazioni del tipo di minaccia</span><span class="sxs-lookup"><span data-stu-id="9f427-293">Threat type settings merge policy</span></span>

<span data-ttu-id="9f427-294">Specificare i criteri di unione per le impostazioni del tipo di minaccia.</span><span class="sxs-lookup"><span data-stu-id="9f427-294">Specify the merge policy for threat type settings.</span></span> <span data-ttu-id="9f427-295">Può essere una combinazione di impostazioni definite dall'amministratore e definite dall'utente ( ) o solo impostazioni definite `merge` dall'amministratore ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="9f427-295">This can be a combination of administrator-defined and user-defined settings (`merge`) or only administrator-defined settings (`admin_only`).</span></span> <span data-ttu-id="9f427-296">Questa impostazione può essere usata per impedire agli utenti locali di definire le proprie impostazioni per diversi tipi di minacce.</span><span class="sxs-lookup"><span data-stu-id="9f427-296">This setting can be used to restrict local users from defining their own settings for different threat types.</span></span>

|||
|:---|:---|
| <span data-ttu-id="9f427-297">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="9f427-297">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9f427-298">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="9f427-298">**Key**</span></span> | <span data-ttu-id="9f427-299">threatTypeSettingsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="9f427-299">threatTypeSettingsMergePolicy</span></span> |
| <span data-ttu-id="9f427-300">**Data type**</span><span class="sxs-lookup"><span data-stu-id="9f427-300">**Data type**</span></span> | <span data-ttu-id="9f427-301">Stringa</span><span class="sxs-lookup"><span data-stu-id="9f427-301">String</span></span> |
| <span data-ttu-id="9f427-302">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="9f427-302">**Possible values**</span></span> | <span data-ttu-id="9f427-303">merge (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="9f427-303">merge (default)</span></span> <br/> <span data-ttu-id="9f427-304">admin_only</span><span class="sxs-lookup"><span data-stu-id="9f427-304">admin_only</span></span> |
| <span data-ttu-id="9f427-305">**Comments**</span><span class="sxs-lookup"><span data-stu-id="9f427-305">**Comments**</span></span> | <span data-ttu-id="9f427-306">Disponibile in Microsoft Defender per Endpoint versione 100.83.73 o successiva.</span><span class="sxs-lookup"><span data-stu-id="9f427-306">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="antivirus-scan-history-retention-in-days"></a><span data-ttu-id="9f427-307">Conservazione cronologia analisi antivirus (in giorni)</span><span class="sxs-lookup"><span data-stu-id="9f427-307">Antivirus scan history retention (in days)</span></span>

<span data-ttu-id="9f427-308">Specifica il numero di giorni in cui i risultati vengono conservati nella cronologia dell'analisi nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9f427-308">Specify the number of days that results are retained in the scan history on the device.</span></span> <span data-ttu-id="9f427-309">I risultati dell'analisi precedente vengono rimossi dalla cronologia.</span><span class="sxs-lookup"><span data-stu-id="9f427-309">Old scan results are removed from the history.</span></span> <span data-ttu-id="9f427-310">Vecchi file in quarantena che vengono rimossi anche dal disco.</span><span class="sxs-lookup"><span data-stu-id="9f427-310">Old quarantined files that are also removed from the disk.</span></span>

|||
|:---|:---|
| <span data-ttu-id="9f427-311">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="9f427-311">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9f427-312">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="9f427-312">**Key**</span></span> | <span data-ttu-id="9f427-313">scanResultsRetentionDays</span><span class="sxs-lookup"><span data-stu-id="9f427-313">scanResultsRetentionDays</span></span> |
| <span data-ttu-id="9f427-314">**Data type**</span><span class="sxs-lookup"><span data-stu-id="9f427-314">**Data type**</span></span> | <span data-ttu-id="9f427-315">Stringa</span><span class="sxs-lookup"><span data-stu-id="9f427-315">String</span></span> |
| <span data-ttu-id="9f427-316">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="9f427-316">**Possible values**</span></span> | <span data-ttu-id="9f427-317">90 (impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="9f427-317">90 (default).</span></span> <span data-ttu-id="9f427-318">I valori consentiti sono da 1 giorno a 180 giorni.</span><span class="sxs-lookup"><span data-stu-id="9f427-318">Allowed values are from 1 day to 180 days.</span></span> |
| <span data-ttu-id="9f427-319">**Comments**</span><span class="sxs-lookup"><span data-stu-id="9f427-319">**Comments**</span></span> | <span data-ttu-id="9f427-320">Disponibile in Microsoft Defender per Endpoint versione 101.07.23 o successiva.</span><span class="sxs-lookup"><span data-stu-id="9f427-320">Available in Microsoft Defender for Endpoint version 101.07.23 or higher.</span></span> |

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a><span data-ttu-id="9f427-321">Numero massimo di elementi nella cronologia dell'analisi antivirus</span><span class="sxs-lookup"><span data-stu-id="9f427-321">Maximum number of items in the antivirus scan history</span></span>

<span data-ttu-id="9f427-322">Specificare il numero massimo di voci da mantenere nella cronologia di analisi.</span><span class="sxs-lookup"><span data-stu-id="9f427-322">Specify the maximum number of entries to keep in the scan history.</span></span> <span data-ttu-id="9f427-323">Le voci includono tutte le analisi su richiesta eseguite in passato e tutti i rilevamenti antivirus.</span><span class="sxs-lookup"><span data-stu-id="9f427-323">Entries include all on-demand scans performed in the past and all antivirus detections.</span></span>

|||
|:---|:---|
| <span data-ttu-id="9f427-324">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="9f427-324">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9f427-325">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="9f427-325">**Key**</span></span> | <span data-ttu-id="9f427-326">scanHistoryMaximumItems</span><span class="sxs-lookup"><span data-stu-id="9f427-326">scanHistoryMaximumItems</span></span> |
| <span data-ttu-id="9f427-327">**Data type**</span><span class="sxs-lookup"><span data-stu-id="9f427-327">**Data type**</span></span> | <span data-ttu-id="9f427-328">Stringa</span><span class="sxs-lookup"><span data-stu-id="9f427-328">String</span></span> |
| <span data-ttu-id="9f427-329">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="9f427-329">**Possible values**</span></span> | <span data-ttu-id="9f427-330">10000 (impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="9f427-330">10000 (default).</span></span> <span data-ttu-id="9f427-331">I valori consentiti sono da 5.000 elementi a 15.000 elementi.</span><span class="sxs-lookup"><span data-stu-id="9f427-331">Allowed values are from 5000 items to 15000 items.</span></span> |
| <span data-ttu-id="9f427-332">**Comments**</span><span class="sxs-lookup"><span data-stu-id="9f427-332">**Comments**</span></span> | <span data-ttu-id="9f427-333">Disponibile in Microsoft Defender per Endpoint versione 101.07.23 o successiva.</span><span class="sxs-lookup"><span data-stu-id="9f427-333">Available in Microsoft Defender for Endpoint version 101.07.23 or higher.</span></span> |

### <a name="cloud-delivered-protection-preferences"></a><span data-ttu-id="9f427-334">Preferenze di protezione per il cloud</span><span class="sxs-lookup"><span data-stu-id="9f427-334">Cloud-delivered protection preferences</span></span>

<span data-ttu-id="9f427-335">Configurare le funzionalità di protezione basata sul cloud di Microsoft Defender per Endpoint per Mac.</span><span class="sxs-lookup"><span data-stu-id="9f427-335">Configure the cloud-driven protection features of Microsoft Defender for Endpoint for Mac.</span></span>

|||
|:---|:---|
| <span data-ttu-id="9f427-336">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="9f427-336">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9f427-337">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="9f427-337">**Key**</span></span> | <span data-ttu-id="9f427-338">cloudService</span><span class="sxs-lookup"><span data-stu-id="9f427-338">cloudService</span></span> |
| <span data-ttu-id="9f427-339">**Data type**</span><span class="sxs-lookup"><span data-stu-id="9f427-339">**Data type**</span></span> | <span data-ttu-id="9f427-340">Dizionario (preferenza annidata)</span><span class="sxs-lookup"><span data-stu-id="9f427-340">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="9f427-341">**Comments**</span><span class="sxs-lookup"><span data-stu-id="9f427-341">**Comments**</span></span> | <span data-ttu-id="9f427-342">Per una descrizione del contenuto del dizionario, vedi le sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="9f427-342">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-cloud-delivered-protection"></a><span data-ttu-id="9f427-343">Abilitare/disabilitare la protezione recapitata nel cloud</span><span class="sxs-lookup"><span data-stu-id="9f427-343">Enable / disable cloud-delivered protection</span></span>

<span data-ttu-id="9f427-344">Specificare se abilitare o meno la protezione recapitata nel cloud.</span><span class="sxs-lookup"><span data-stu-id="9f427-344">Specify whether to enable cloud-delivered protection the device or not.</span></span> <span data-ttu-id="9f427-345">Per migliorare la sicurezza dei servizi, è consigliabile mantenere attivata questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="9f427-345">To improve the security of your services, we recommend keeping this feature turned on.</span></span>

|||
|:---|:---|
| <span data-ttu-id="9f427-346">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="9f427-346">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9f427-347">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="9f427-347">**Key**</span></span> | <span data-ttu-id="9f427-348">abilitati</span><span class="sxs-lookup"><span data-stu-id="9f427-348">enabled</span></span> |
| <span data-ttu-id="9f427-349">**Data type**</span><span class="sxs-lookup"><span data-stu-id="9f427-349">**Data type**</span></span> | <span data-ttu-id="9f427-350">Booleano</span><span class="sxs-lookup"><span data-stu-id="9f427-350">Boolean</span></span> |
| <span data-ttu-id="9f427-351">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="9f427-351">**Possible values**</span></span> | <span data-ttu-id="9f427-352">true (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="9f427-352">true (default)</span></span> <br/> <span data-ttu-id="9f427-353">false</span><span class="sxs-lookup"><span data-stu-id="9f427-353">false</span></span> |

#### <a name="diagnostic-collection-level"></a><span data-ttu-id="9f427-354">Livello raccolta diagnostica</span><span class="sxs-lookup"><span data-stu-id="9f427-354">Diagnostic collection level</span></span>

<span data-ttu-id="9f427-355">I dati di diagnostica vengono usati per mantenere Microsoft Defender for Endpoint sicuro e aggiornato, rilevare, diagnosticare e risolvere i problemi e apportare miglioramenti al prodotto.</span><span class="sxs-lookup"><span data-stu-id="9f427-355">Diagnostic data is used to keep Microsoft Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span> <span data-ttu-id="9f427-356">Questa impostazione determina il livello di diagnostica inviato da Microsoft Defender per Endpoint a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9f427-356">This setting determines the level of diagnostics sent by Microsoft Defender for Endpoint to Microsoft.</span></span>

|||
|:---|:---|
| <span data-ttu-id="9f427-357">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="9f427-357">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9f427-358">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="9f427-358">**Key**</span></span> | <span data-ttu-id="9f427-359">diagnosticLevel</span><span class="sxs-lookup"><span data-stu-id="9f427-359">diagnosticLevel</span></span> |
| <span data-ttu-id="9f427-360">**Data type**</span><span class="sxs-lookup"><span data-stu-id="9f427-360">**Data type**</span></span> | <span data-ttu-id="9f427-361">Stringa</span><span class="sxs-lookup"><span data-stu-id="9f427-361">String</span></span> |
| <span data-ttu-id="9f427-362">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="9f427-362">**Possible values**</span></span> | <span data-ttu-id="9f427-363">facoltativo (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="9f427-363">optional (default)</span></span> <br/> <span data-ttu-id="9f427-364">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="9f427-364">required</span></span> |

#### <a name="enable--disable-automatic-sample-submissions"></a><span data-ttu-id="9f427-365">Abilitare/disabilitare gli invii di esempio automatici</span><span class="sxs-lookup"><span data-stu-id="9f427-365">Enable / disable automatic sample submissions</span></span>

<span data-ttu-id="9f427-366">Determina se i campioni sospetti (che potrebbero contenere minacce) vengono inviati a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9f427-366">Determines whether suspicious samples (that are likely to contain threats) are sent to Microsoft.</span></span> <span data-ttu-id="9f427-367">Viene richiesto se è probabile che il file inviato contenga informazioni personali.</span><span class="sxs-lookup"><span data-stu-id="9f427-367">You are prompted if the submitted file is likely to contain personal information.</span></span>

|||
|:---|:---|
| <span data-ttu-id="9f427-368">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="9f427-368">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9f427-369">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="9f427-369">**Key**</span></span> | <span data-ttu-id="9f427-370">automaticSampleSubmission</span><span class="sxs-lookup"><span data-stu-id="9f427-370">automaticSampleSubmission</span></span> |
| <span data-ttu-id="9f427-371">**Data type**</span><span class="sxs-lookup"><span data-stu-id="9f427-371">**Data type**</span></span> | <span data-ttu-id="9f427-372">Booleano</span><span class="sxs-lookup"><span data-stu-id="9f427-372">Boolean</span></span> |
| <span data-ttu-id="9f427-373">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="9f427-373">**Possible values**</span></span> | <span data-ttu-id="9f427-374">true (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="9f427-374">true (default)</span></span> <br/> <span data-ttu-id="9f427-375">false</span><span class="sxs-lookup"><span data-stu-id="9f427-375">false</span></span> |

#### <a name="enable--disable-automatic-security-intelligence-updates"></a><span data-ttu-id="9f427-376">Abilitare/disabilitare gli aggiornamenti automatici delle funzionalità di intelligence per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="9f427-376">Enable / disable automatic security intelligence updates</span></span>

<span data-ttu-id="9f427-377">Determina se gli aggiornamenti delle funzionalità di intelligence per la sicurezza vengono installati automaticamente:</span><span class="sxs-lookup"><span data-stu-id="9f427-377">Determines whether security intelligence updates are installed automatically:</span></span>

|||
|:---|:---|
| <span data-ttu-id="9f427-378">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="9f427-378">**Key**</span></span> | <span data-ttu-id="9f427-379">automaticDefinitionUpdateEnabled</span><span class="sxs-lookup"><span data-stu-id="9f427-379">automaticDefinitionUpdateEnabled</span></span> |
| <span data-ttu-id="9f427-380">**Data type**</span><span class="sxs-lookup"><span data-stu-id="9f427-380">**Data type**</span></span> | <span data-ttu-id="9f427-381">Booleano</span><span class="sxs-lookup"><span data-stu-id="9f427-381">Boolean</span></span> |
| <span data-ttu-id="9f427-382">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="9f427-382">**Possible values**</span></span> | <span data-ttu-id="9f427-383">true (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="9f427-383">true (default)</span></span> <br/> <span data-ttu-id="9f427-384">false</span><span class="sxs-lookup"><span data-stu-id="9f427-384">false</span></span> |

### <a name="user-interface-preferences"></a><span data-ttu-id="9f427-385">Preferenze dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="9f427-385">User interface preferences</span></span>

<span data-ttu-id="9f427-386">Gestisci le preferenze per l'interfaccia utente di Microsoft Defender per Endpoint per Mac.</span><span class="sxs-lookup"><span data-stu-id="9f427-386">Manage the preferences for the user interface of Microsoft Defender for Endpoint for Mac.</span></span>

|||
|:---|:---|
| <span data-ttu-id="9f427-387">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="9f427-387">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9f427-388">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="9f427-388">**Key**</span></span> | <span data-ttu-id="9f427-389">userInterface</span><span class="sxs-lookup"><span data-stu-id="9f427-389">userInterface</span></span> |
| <span data-ttu-id="9f427-390">**Data type**</span><span class="sxs-lookup"><span data-stu-id="9f427-390">**Data type**</span></span> | <span data-ttu-id="9f427-391">Dizionario (preferenza annidata)</span><span class="sxs-lookup"><span data-stu-id="9f427-391">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="9f427-392">**Comments**</span><span class="sxs-lookup"><span data-stu-id="9f427-392">**Comments**</span></span> | <span data-ttu-id="9f427-393">Per una descrizione del contenuto del dizionario, vedi le sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="9f427-393">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="show--hide-status-menu-icon"></a><span data-ttu-id="9f427-394">Mostra/nascondi icona del menu di stato</span><span class="sxs-lookup"><span data-stu-id="9f427-394">Show / hide status menu icon</span></span>

<span data-ttu-id="9f427-395">Specifica se mostrare o nascondere l'icona del menu di stato nell'angolo in alto a destra dello schermo.</span><span class="sxs-lookup"><span data-stu-id="9f427-395">Specify whether to show or hide the status menu icon in the top-right corner of the screen.</span></span>

|||
|:---|:---|
| <span data-ttu-id="9f427-396">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="9f427-396">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9f427-397">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="9f427-397">**Key**</span></span> | <span data-ttu-id="9f427-398">hideStatusMenuIcon</span><span class="sxs-lookup"><span data-stu-id="9f427-398">hideStatusMenuIcon</span></span> |
| <span data-ttu-id="9f427-399">**Data type**</span><span class="sxs-lookup"><span data-stu-id="9f427-399">**Data type**</span></span> | <span data-ttu-id="9f427-400">Booleano</span><span class="sxs-lookup"><span data-stu-id="9f427-400">Boolean</span></span> |
| <span data-ttu-id="9f427-401">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="9f427-401">**Possible values**</span></span> | <span data-ttu-id="9f427-402">false (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="9f427-402">false (default)</span></span> <br/> <span data-ttu-id="9f427-403">true</span><span class="sxs-lookup"><span data-stu-id="9f427-403">true</span></span> |

#### <a name="show--hide-option-to-send-feedback"></a><span data-ttu-id="9f427-404">Opzione Mostra/Nascondi per inviare commenti e suggerimenti</span><span class="sxs-lookup"><span data-stu-id="9f427-404">Show / hide option to send feedback</span></span>

<span data-ttu-id="9f427-405">Specificare se gli utenti possono inviare commenti e suggerimenti a Microsoft andando a `Help`  >  `Send Feedback` .</span><span class="sxs-lookup"><span data-stu-id="9f427-405">Specify whether users can submit feedback to Microsoft by going to `Help` > `Send Feedback`.</span></span>

|||
|:---|:---|
| <span data-ttu-id="9f427-406">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="9f427-406">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9f427-407">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="9f427-407">**Key**</span></span> | <span data-ttu-id="9f427-408">userInitiatedFeedback</span><span class="sxs-lookup"><span data-stu-id="9f427-408">userInitiatedFeedback</span></span> |
| <span data-ttu-id="9f427-409">**Data type**</span><span class="sxs-lookup"><span data-stu-id="9f427-409">**Data type**</span></span> | <span data-ttu-id="9f427-410">Stringa</span><span class="sxs-lookup"><span data-stu-id="9f427-410">String</span></span> |
| <span data-ttu-id="9f427-411">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="9f427-411">**Possible values**</span></span> | <span data-ttu-id="9f427-412">enabled (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="9f427-412">enabled (default)</span></span> <br/> <span data-ttu-id="9f427-413">disabilitati</span><span class="sxs-lookup"><span data-stu-id="9f427-413">disabled</span></span> |
| <span data-ttu-id="9f427-414">**Comments**</span><span class="sxs-lookup"><span data-stu-id="9f427-414">**Comments**</span></span> | <span data-ttu-id="9f427-415">Disponibile in Microsoft Defender per Endpoint versione 101.19.61 o successiva.</span><span class="sxs-lookup"><span data-stu-id="9f427-415">Available in Microsoft Defender for Endpoint version 101.19.61 or higher.</span></span> |

### <a name="endpoint-detection-and-response-preferences"></a><span data-ttu-id="9f427-416">Preferenze di risposta e rilevamento degli endpoint</span><span class="sxs-lookup"><span data-stu-id="9f427-416">Endpoint detection and response preferences</span></span>

<span data-ttu-id="9f427-417">Gestire le preferenze del componente di rilevamento e risposta degli endpoint (EDR) di Microsoft Defender per Endpoint per Mac.</span><span class="sxs-lookup"><span data-stu-id="9f427-417">Manage the preferences of the endpoint detection and response (EDR) component of Microsoft Defender for Endpoint for Mac.</span></span>

|||
|:---|:---|
| <span data-ttu-id="9f427-418">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="9f427-418">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9f427-419">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="9f427-419">**Key**</span></span> | <span data-ttu-id="9f427-420">edr</span><span class="sxs-lookup"><span data-stu-id="9f427-420">edr</span></span> |
| <span data-ttu-id="9f427-421">**Data type**</span><span class="sxs-lookup"><span data-stu-id="9f427-421">**Data type**</span></span> | <span data-ttu-id="9f427-422">Dizionario (preferenza annidata)</span><span class="sxs-lookup"><span data-stu-id="9f427-422">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="9f427-423">**Comments**</span><span class="sxs-lookup"><span data-stu-id="9f427-423">**Comments**</span></span> | <span data-ttu-id="9f427-424">Per una descrizione del contenuto del dizionario, vedi le sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="9f427-424">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="device-tags"></a><span data-ttu-id="9f427-425">Tag dispositivo</span><span class="sxs-lookup"><span data-stu-id="9f427-425">Device tags</span></span>

<span data-ttu-id="9f427-426">Specificare un nome di tag e il relativo valore.</span><span class="sxs-lookup"><span data-stu-id="9f427-426">Specify a tag name and its value.</span></span> 

- <span data-ttu-id="9f427-427">Il tag GROUP contrassegna il dispositivo con il valore specificato.</span><span class="sxs-lookup"><span data-stu-id="9f427-427">The GROUP tag, tags the device with the specified value.</span></span> <span data-ttu-id="9f427-428">Il tag si riflette nel portale nella pagina del dispositivo e può essere usato per filtrare e raggruppare i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="9f427-428">The tag is reflected in the portal under the device page and can be used for filtering and grouping devices.</span></span>

|||
|:---|:---|
| <span data-ttu-id="9f427-429">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="9f427-429">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9f427-430">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="9f427-430">**Key**</span></span> | <span data-ttu-id="9f427-431">tag</span><span class="sxs-lookup"><span data-stu-id="9f427-431">tags</span></span> |
| <span data-ttu-id="9f427-432">**Data type**</span><span class="sxs-lookup"><span data-stu-id="9f427-432">**Data type**</span></span> | <span data-ttu-id="9f427-433">Dizionario (preferenza annidata)</span><span class="sxs-lookup"><span data-stu-id="9f427-433">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="9f427-434">**Comments**</span><span class="sxs-lookup"><span data-stu-id="9f427-434">**Comments**</span></span> | <span data-ttu-id="9f427-435">Per una descrizione del contenuto del dizionario, vedi le sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="9f427-435">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="type-of-tag"></a><span data-ttu-id="9f427-436">Tipo di tag</span><span class="sxs-lookup"><span data-stu-id="9f427-436">Type of tag</span></span>

<span data-ttu-id="9f427-437">Specifica il tipo di tag</span><span class="sxs-lookup"><span data-stu-id="9f427-437">Specifies the type of tag</span></span>

|||
|:---|:---|
| <span data-ttu-id="9f427-438">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="9f427-438">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9f427-439">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="9f427-439">**Key**</span></span> | <span data-ttu-id="9f427-440">chiave</span><span class="sxs-lookup"><span data-stu-id="9f427-440">key</span></span> |
| <span data-ttu-id="9f427-441">**Data type**</span><span class="sxs-lookup"><span data-stu-id="9f427-441">**Data type**</span></span> | <span data-ttu-id="9f427-442">Stringa</span><span class="sxs-lookup"><span data-stu-id="9f427-442">String</span></span> |
| <span data-ttu-id="9f427-443">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="9f427-443">**Possible values**</span></span> | `GROUP` |

##### <a name="value-of-tag"></a><span data-ttu-id="9f427-444">Valore del tag</span><span class="sxs-lookup"><span data-stu-id="9f427-444">Value of tag</span></span>

<span data-ttu-id="9f427-445">Specifica il valore del tag</span><span class="sxs-lookup"><span data-stu-id="9f427-445">Specifies the value of tag</span></span>

|||
|:---|:---|
| <span data-ttu-id="9f427-446">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="9f427-446">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9f427-447">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="9f427-447">**Key**</span></span> | <span data-ttu-id="9f427-448">valore</span><span class="sxs-lookup"><span data-stu-id="9f427-448">value</span></span> |
| <span data-ttu-id="9f427-449">**Data type**</span><span class="sxs-lookup"><span data-stu-id="9f427-449">**Data type**</span></span> | <span data-ttu-id="9f427-450">Stringa</span><span class="sxs-lookup"><span data-stu-id="9f427-450">String</span></span> |
| <span data-ttu-id="9f427-451">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="9f427-451">**Possible values**</span></span> | <span data-ttu-id="9f427-452">qualsiasi stringa</span><span class="sxs-lookup"><span data-stu-id="9f427-452">any string</span></span> |

> [!IMPORTANT]  
> - <span data-ttu-id="9f427-453">È possibile impostare un solo valore per ogni tipo di tag.</span><span class="sxs-lookup"><span data-stu-id="9f427-453">Only one value per tag type can be set.</span></span>
> - <span data-ttu-id="9f427-454">Il tipo di tag è univoco e non deve essere ripetuto nello stesso profilo di configurazione.</span><span class="sxs-lookup"><span data-stu-id="9f427-454">Type of tags are unique, and should not be repeated in the same configuration profile.</span></span>

## <a name="recommended-configuration-profile"></a><span data-ttu-id="9f427-455">Profilo di configurazione consigliato</span><span class="sxs-lookup"><span data-stu-id="9f427-455">Recommended configuration profile</span></span>

<span data-ttu-id="9f427-456">Per iniziare, ti consigliamo la configurazione seguente per l'azienda per sfruttare tutte le funzionalità di protezione fornite da Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="9f427-456">To get started, we recommend the following configuration for your enterprise to take advantage of all protection features that Microsoft Defender for Endpoint provides.</span></span>

<span data-ttu-id="9f427-457">Il profilo di configurazione seguente (o, nel caso di JAMF, un elenco di proprietà che potrebbe essere caricato nel profilo di configurazione delle impostazioni personalizzate) sarà:</span><span class="sxs-lookup"><span data-stu-id="9f427-457">The following configuration profile (or, in case of JAMF, a property list that could be uploaded into the custom settings configuration profile) will:</span></span>
- <span data-ttu-id="9f427-458">Abilitare la protezione in tempo reale (RTP)</span><span class="sxs-lookup"><span data-stu-id="9f427-458">Enable real-time protection (RTP)</span></span>
- <span data-ttu-id="9f427-459">Specificare la modalità di gestione dei seguenti tipi di minacce:</span><span class="sxs-lookup"><span data-stu-id="9f427-459">Specify how the following threat types are handled:</span></span>
  - <span data-ttu-id="9f427-460">**Le applicazioni potenzialmente indesiderate sono** bloccate</span><span class="sxs-lookup"><span data-stu-id="9f427-460">**Potentially unwanted applications (PUA)** are blocked</span></span>
  - <span data-ttu-id="9f427-461">**Le bombe di** archiviazione (file con una velocità di compressione elevata) vengono verificate in Microsoft Defender per i log degli endpoint</span><span class="sxs-lookup"><span data-stu-id="9f427-461">**Archive bombs** (file with a high compression rate) are audited to Microsoft Defender for Endpoint logs</span></span>
- <span data-ttu-id="9f427-462">Abilitare gli aggiornamenti automatici delle funzionalità di intelligence per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="9f427-462">Enable automatic security intelligence updates</span></span>
- <span data-ttu-id="9f427-463">Abilitare la protezione basata sul cloud</span><span class="sxs-lookup"><span data-stu-id="9f427-463">Enable cloud-delivered protection</span></span>
- <span data-ttu-id="9f427-464">Abilitare l'invio automatico di esempi</span><span class="sxs-lookup"><span data-stu-id="9f427-464">Enable automatic sample submission</span></span>

### <a name="property-list-for-jamf-configuration-profile"></a><span data-ttu-id="9f427-465">Elenco delle proprietà per il profilo di configurazione JAMF</span><span class="sxs-lookup"><span data-stu-id="9f427-465">Property list for JAMF configuration profile</span></span>

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

### <a name="intune-profile"></a><span data-ttu-id="9f427-466">Profilo intune</span><span class="sxs-lookup"><span data-stu-id="9f427-466">Intune profile</span></span>

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

## <a name="full-configuration-profile-example"></a><span data-ttu-id="9f427-467">Esempio di profilo di configurazione completo</span><span class="sxs-lookup"><span data-stu-id="9f427-467">Full configuration profile example</span></span>

<span data-ttu-id="9f427-468">I modelli seguenti contengono voci per tutte le impostazioni descritte in questo documento e possono essere usati per scenari più avanzati in cui si desidera un maggiore controllo su Microsoft Defender per Endpoint per Mac.</span><span class="sxs-lookup"><span data-stu-id="9f427-468">The following templates contain entries for all settings described in this document and can be used for more advanced scenarios where you want more control over Microsoft Defender for Endpoint for Mac.</span></span>

### <a name="property-list-for-jamf-configuration-profile"></a><span data-ttu-id="9f427-469">Elenco delle proprietà per il profilo di configurazione JAMF</span><span class="sxs-lookup"><span data-stu-id="9f427-469">Property list for JAMF configuration profile</span></span>

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

### <a name="intune-profile"></a><span data-ttu-id="9f427-470">Profilo intune</span><span class="sxs-lookup"><span data-stu-id="9f427-470">Intune profile</span></span>

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

## <a name="property-list-validation"></a><span data-ttu-id="9f427-471">Convalida elenco proprietà</span><span class="sxs-lookup"><span data-stu-id="9f427-471">Property list validation</span></span>

<span data-ttu-id="9f427-472">L'elenco delle proprietà deve essere un file *plist* valido.</span><span class="sxs-lookup"><span data-stu-id="9f427-472">The property list must be a valid *.plist* file.</span></span> <span data-ttu-id="9f427-473">Questa operazione può essere verificata eseguendo:</span><span class="sxs-lookup"><span data-stu-id="9f427-473">This can be checked by executing:</span></span>

```bash
plutil -lint com.microsoft.wdav.plist
```
```Output
com.microsoft.wdav.plist: OK
```

<span data-ttu-id="9f427-474">Se il file è ben formato, il comando precedente restituisce un `OK` codice di uscita di `0` .</span><span class="sxs-lookup"><span data-stu-id="9f427-474">If the file is well-formed, the above command outputs `OK` and returns an exit code of `0`.</span></span> <span data-ttu-id="9f427-475">In caso contrario, viene visualizzato un errore che descrive il problema e il comando restituisce un codice di uscita di `1` .</span><span class="sxs-lookup"><span data-stu-id="9f427-475">Otherwise, an error that describes the issue is displayed and the command returns an exit code of `1`.</span></span>

## <a name="configuration-profile-deployment"></a><span data-ttu-id="9f427-476">Distribuzione dei profili di configurazione</span><span class="sxs-lookup"><span data-stu-id="9f427-476">Configuration profile deployment</span></span>

<span data-ttu-id="9f427-477">Dopo aver creato il profilo di configurazione per l'organizzazione, è possibile distribuirlo tramite la console di gestione in uso.</span><span class="sxs-lookup"><span data-stu-id="9f427-477">Once you've built the configuration profile for your enterprise, you can deploy it through the management console that your enterprise is using.</span></span> <span data-ttu-id="9f427-478">Le sezioni seguenti forniscono istruzioni su come distribuire questo profilo usando JAMF e Intune.</span><span class="sxs-lookup"><span data-stu-id="9f427-478">The following sections provide instructions on how to deploy this profile using JAMF and Intune.</span></span>

### <a name="jamf-deployment"></a><span data-ttu-id="9f427-479">Distribuzione JAMF</span><span class="sxs-lookup"><span data-stu-id="9f427-479">JAMF deployment</span></span>

<span data-ttu-id="9f427-480">Dalla console JAMF apri **Profili** di configurazione computer, passa al profilo di configurazione che vuoi usare, quindi  >  seleziona **Impostazioni personalizzate.**</span><span class="sxs-lookup"><span data-stu-id="9f427-480">From the JAMF console, open **Computers** > **Configuration Profiles**, navigate to the configuration profile you'd like to use, then select **Custom Settings**.</span></span> <span data-ttu-id="9f427-481">Crea una voce con `com.microsoft.wdav` come dominio di preferenza e carica il file *plist* prodotto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="9f427-481">Create an entry with `com.microsoft.wdav` as the preference domain and upload the *.plist* produced earlier.</span></span>

>[!CAUTION]
><span data-ttu-id="9f427-482">È necessario immettere il dominio di preferenza corretto ( ); in caso contrario, le preferenze non verranno `com.microsoft.wdav` riconosciute da Microsoft Defender per Endpoint.</span><span class="sxs-lookup"><span data-stu-id="9f427-482">You must enter the correct preference domain (`com.microsoft.wdav`); otherwise, the preferences will not be recognized by Microsoft Defender for Endpoint.</span></span>

### <a name="intune-deployment"></a><span data-ttu-id="9f427-483">Distribuzione di Intune</span><span class="sxs-lookup"><span data-stu-id="9f427-483">Intune deployment</span></span>

1. <span data-ttu-id="9f427-484">Aprire **Gestisci**  >  **configurazione dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="9f427-484">Open **Manage** > **Device configuration**.</span></span> <span data-ttu-id="9f427-485">Selezionare **Gestisci**  >  **profili**  >  **Crea profilo**.</span><span class="sxs-lookup"><span data-stu-id="9f427-485">Select **Manage** > **Profiles** > **Create Profile**.</span></span>

2. <span data-ttu-id="9f427-486">Scegliere un nome per il profilo.</span><span class="sxs-lookup"><span data-stu-id="9f427-486">Choose a name for the profile.</span></span> <span data-ttu-id="9f427-487">Modificare **Platform=macOS** in **Profile type=Custom**.</span><span class="sxs-lookup"><span data-stu-id="9f427-487">Change **Platform=macOS** to **Profile type=Custom**.</span></span> <span data-ttu-id="9f427-488">Selezionare Configura.</span><span class="sxs-lookup"><span data-stu-id="9f427-488">Select Configure.</span></span>

3. <span data-ttu-id="9f427-489">Salvare il file plist prodotto in precedenza come `com.microsoft.wdav.xml` .</span><span class="sxs-lookup"><span data-stu-id="9f427-489">Save the .plist produced earlier as `com.microsoft.wdav.xml`.</span></span>

4. <span data-ttu-id="9f427-490">Immettere `com.microsoft.wdav` come nome del profilo di configurazione **personalizzato**.</span><span class="sxs-lookup"><span data-stu-id="9f427-490">Enter `com.microsoft.wdav` as the **custom configuration profile name**.</span></span>

5. <span data-ttu-id="9f427-491">Apri il profilo di configurazione e carica il `com.microsoft.wdav.xml` file.</span><span class="sxs-lookup"><span data-stu-id="9f427-491">Open the configuration profile and upload the `com.microsoft.wdav.xml` file.</span></span> <span data-ttu-id="9f427-492">Questo file è stato creato nel passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="9f427-492">(This file was created in step 3.)</span></span>

6. <span data-ttu-id="9f427-493">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="9f427-493">Select **OK**.</span></span>

7. <span data-ttu-id="9f427-494">Selezionare **Gestisci**  >  **assegnazioni**.</span><span class="sxs-lookup"><span data-stu-id="9f427-494">Select **Manage** > **Assignments**.</span></span> <span data-ttu-id="9f427-495">Nella scheda **Includi** seleziona **Assegna a tutti gli utenti & Tutti i dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="9f427-495">In the **Include** tab, select **Assign to All Users & All devices**.</span></span>

>[!CAUTION]
><span data-ttu-id="9f427-496">È necessario immettere il nome del profilo di configurazione personalizzato corretto. in caso contrario, queste preferenze non verranno riconosciute da Microsoft Defender per Endpoint.</span><span class="sxs-lookup"><span data-stu-id="9f427-496">You must enter the correct custom configuration profile name; otherwise, these preferences will not be recognized by Microsoft Defender for Endpoint.</span></span>

## <a name="resources"></a><span data-ttu-id="9f427-497">Risorse</span><span class="sxs-lookup"><span data-stu-id="9f427-497">Resources</span></span>

- [<span data-ttu-id="9f427-498">Informazioni di riferimento sui profili di configurazione (documentazione per sviluppatori Apple)</span><span class="sxs-lookup"><span data-stu-id="9f427-498">Configuration Profile Reference (Apple developer documentation)</span></span>](https://developer.apple.com/business/documentation/Configuration-Profile-Reference.pdf)
