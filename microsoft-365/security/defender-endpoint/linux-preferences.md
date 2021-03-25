---
title: Impostare le preferenze per Microsoft Defender ATP per Linux
ms.reviewer: ''
description: Descrive come configurare Microsoft Defender ATP per Linux nelle aziende.
keywords: microsoft, defender, atp, linux, installazione, distribuire, disinstallazione, pupazzo, ansible, linux, redhat, ubuntu, debian, sles, suse, centos
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
ms.openlocfilehash: 5206de55523c6f5a24fa85f29d48620b38be5bfa
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064557"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="92931-104">Impostare le preferenze per Microsoft Defender per Endpoint per Linux</span><span class="sxs-lookup"><span data-stu-id="92931-104">Set preferences for Microsoft Defender for Endpoint for Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="92931-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="92931-105">**Applies to:**</span></span>
- [<span data-ttu-id="92931-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="92931-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="92931-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="92931-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="92931-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="92931-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="92931-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="92931-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

>[!IMPORTANT]
><span data-ttu-id="92931-110">Questo argomento contiene istruzioni su come impostare le preferenze per Defender per Endpoint per Linux in ambienti aziendali.</span><span class="sxs-lookup"><span data-stu-id="92931-110">This topic contains instructions for how to set preferences for Defender for Endpoint for Linux in enterprise environments.</span></span> <span data-ttu-id="92931-111">Se si desidera configurare il prodotto in un dispositivo dalla riga di comando, vedere [Resources](linux-resources.md#configure-from-the-command-line).</span><span class="sxs-lookup"><span data-stu-id="92931-111">If you are interested in configuring the product on a device from the command-line, see [Resources](linux-resources.md#configure-from-the-command-line).</span></span>

<span data-ttu-id="92931-112">In ambienti aziendali, Defender per Endpoint per Linux può essere gestito tramite un profilo di configurazione.</span><span class="sxs-lookup"><span data-stu-id="92931-112">In enterprise environments, Defender for Endpoint for Linux can be managed through a configuration profile.</span></span> <span data-ttu-id="92931-113">Questo profilo viene distribuito dallo strumento di gestione scelto.</span><span class="sxs-lookup"><span data-stu-id="92931-113">This profile is deployed from the management tool of your choice.</span></span> <span data-ttu-id="92931-114">Le preferenze gestite dall'organizzazione hanno la precedenza su quelle impostate localmente nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="92931-114">Preferences managed by the enterprise take precedence over the ones set locally on the device.</span></span> <span data-ttu-id="92931-115">In altre parole, gli utenti dell'organizzazione non sono in grado di modificare le preferenze impostate tramite questo profilo di configurazione.</span><span class="sxs-lookup"><span data-stu-id="92931-115">In other words, users in your enterprise are not able to change preferences that are set through this configuration profile.</span></span>

<span data-ttu-id="92931-116">Questo articolo descrive la struttura di questo profilo (incluso un profilo consigliato che puoi usare per iniziare) e le istruzioni su come distribuire il profilo.</span><span class="sxs-lookup"><span data-stu-id="92931-116">This article describes the structure of this profile (including a recommended profile that you can use to get started) and instructions on how to deploy the profile.</span></span>

## <a name="configuration-profile-structure"></a><span data-ttu-id="92931-117">Struttura del profilo di configurazione</span><span class="sxs-lookup"><span data-stu-id="92931-117">Configuration profile structure</span></span>

<span data-ttu-id="92931-118">Il profilo di configurazione è un file JSON costituito da voci identificate da una chiave (che indica il nome della preferenza), seguita da un valore, che dipende dalla natura della preferenza.</span><span class="sxs-lookup"><span data-stu-id="92931-118">The configuration profile is a .json file that consists of entries identified by a key (which denotes the name of the preference), followed by a value, which depends on the nature of the preference.</span></span> <span data-ttu-id="92931-119">I valori possono essere semplici, ad esempio un valore numerico o complessi, ad esempio un elenco nidificato di preferenze.</span><span class="sxs-lookup"><span data-stu-id="92931-119">Values can be simple, such as a numerical value, or complex, such as a nested list of preferences.</span></span>

<span data-ttu-id="92931-120">In genere, si utilizza uno strumento di gestione della configurazione per eseguire il push di un file con il nome ```mdatp_managed.json``` nel percorso ```/etc/opt/microsoft/mdatp/managed/``` .</span><span class="sxs-lookup"><span data-stu-id="92931-120">Typically, you would use a configuration management tool to push a file with the name ```mdatp_managed.json``` at the location ```/etc/opt/microsoft/mdatp/managed/```.</span></span>

<span data-ttu-id="92931-121">Il livello superiore del profilo di configurazione include le preferenze e le voci a livello di prodotto per le sottoaree del prodotto, che vengono illustrate in modo più dettagliato nelle sezioni successive.</span><span class="sxs-lookup"><span data-stu-id="92931-121">The top level of the configuration profile includes product-wide preferences and entries for subareas of the product, which are explained in more detail in the next sections.</span></span>

### <a name="antivirus-engine-preferences"></a><span data-ttu-id="92931-122">Preferenze del motore antivirus</span><span class="sxs-lookup"><span data-stu-id="92931-122">Antivirus engine preferences</span></span>

<span data-ttu-id="92931-123">La *sezione antivirusEngine* del profilo di configurazione viene utilizzata per gestire le preferenze del componente antivirus del prodotto.</span><span class="sxs-lookup"><span data-stu-id="92931-123">The *antivirusEngine* section of the configuration profile is used to manage the preferences of the antivirus component of the product.</span></span>

|||
|:---|:---|
| <span data-ttu-id="92931-124">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="92931-124">**Key**</span></span> | <span data-ttu-id="92931-125">antivirusEngine</span><span class="sxs-lookup"><span data-stu-id="92931-125">antivirusEngine</span></span> |
| <span data-ttu-id="92931-126">**Data type**</span><span class="sxs-lookup"><span data-stu-id="92931-126">**Data type**</span></span> | <span data-ttu-id="92931-127">Dizionario (preferenza annidata)</span><span class="sxs-lookup"><span data-stu-id="92931-127">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="92931-128">**Comments**</span><span class="sxs-lookup"><span data-stu-id="92931-128">**Comments**</span></span> | <span data-ttu-id="92931-129">Per una descrizione del contenuto del dizionario, vedi le sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="92931-129">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-real-time-protection"></a><span data-ttu-id="92931-130">Abilitare/disabilitare la protezione in tempo reale</span><span class="sxs-lookup"><span data-stu-id="92931-130">Enable / disable real-time protection</span></span>

<span data-ttu-id="92931-131">Determina se la protezione in tempo reale (analizza i file quando vi si accede) è abilitata o meno.</span><span class="sxs-lookup"><span data-stu-id="92931-131">Determines whether real-time protection (scan files as they are accessed) is enabled or not.</span></span>

|||
|:---|:---|
| <span data-ttu-id="92931-132">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="92931-132">**Key**</span></span> | <span data-ttu-id="92931-133">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="92931-133">enableRealTimeProtection</span></span> |
| <span data-ttu-id="92931-134">**Data type**</span><span class="sxs-lookup"><span data-stu-id="92931-134">**Data type**</span></span> | <span data-ttu-id="92931-135">Booleano</span><span class="sxs-lookup"><span data-stu-id="92931-135">Boolean</span></span> |
| <span data-ttu-id="92931-136">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="92931-136">**Possible values**</span></span> | <span data-ttu-id="92931-137">true (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="92931-137">true (default)</span></span> <br/> <span data-ttu-id="92931-138">false</span><span class="sxs-lookup"><span data-stu-id="92931-138">false</span></span> |

#### <a name="enable--disable-passive-mode"></a><span data-ttu-id="92931-139">Abilitare/disabilitare la modalità passiva</span><span class="sxs-lookup"><span data-stu-id="92931-139">Enable / disable passive mode</span></span>

<span data-ttu-id="92931-140">Determina se il motore antivirus viene eseguito in modalità passiva o meno.</span><span class="sxs-lookup"><span data-stu-id="92931-140">Determines whether the antivirus engine runs in passive mode or not.</span></span> <span data-ttu-id="92931-141">In modalità passiva:</span><span class="sxs-lookup"><span data-stu-id="92931-141">In passive mode:</span></span>
- <span data-ttu-id="92931-142">La protezione in tempo reale è disattivata.</span><span class="sxs-lookup"><span data-stu-id="92931-142">Real-time protection is turned off.</span></span>
- <span data-ttu-id="92931-143">L'analisi su richiesta è attivata.</span><span class="sxs-lookup"><span data-stu-id="92931-143">On-demand scanning is turned on.</span></span>
- <span data-ttu-id="92931-144">La correzione automatica delle minacce è disattivata.</span><span class="sxs-lookup"><span data-stu-id="92931-144">Automatic threat remediation is turned off.</span></span>
- <span data-ttu-id="92931-145">Gli aggiornamenti delle funzionalità di intelligence per la sicurezza sono attivati.</span><span class="sxs-lookup"><span data-stu-id="92931-145">Security intelligence updates are turned on.</span></span>
- <span data-ttu-id="92931-146">L'icona del menu Stato è nascosta.</span><span class="sxs-lookup"><span data-stu-id="92931-146">Status menu icon is hidden.</span></span>

|||
|:---|:---|
| <span data-ttu-id="92931-147">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="92931-147">**Key**</span></span> | <span data-ttu-id="92931-148">passiveMode</span><span class="sxs-lookup"><span data-stu-id="92931-148">passiveMode</span></span> |
| <span data-ttu-id="92931-149">**Data type**</span><span class="sxs-lookup"><span data-stu-id="92931-149">**Data type**</span></span> | <span data-ttu-id="92931-150">Booleano</span><span class="sxs-lookup"><span data-stu-id="92931-150">Boolean</span></span> |
| <span data-ttu-id="92931-151">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="92931-151">**Possible values**</span></span> | <span data-ttu-id="92931-152">false (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="92931-152">false (default)</span></span> <br/> <span data-ttu-id="92931-153">true</span><span class="sxs-lookup"><span data-stu-id="92931-153">true</span></span> |
| <span data-ttu-id="92931-154">**Comments**</span><span class="sxs-lookup"><span data-stu-id="92931-154">**Comments**</span></span> | <span data-ttu-id="92931-155">Disponibile in Defender per Endpoint versione 100.67.60 o successiva.</span><span class="sxs-lookup"><span data-stu-id="92931-155">Available in Defender for Endpoint version 100.67.60 or higher.</span></span> |

#### <a name="exclusion-merge-policy"></a><span data-ttu-id="92931-156">Criteri di unione esclusioni</span><span class="sxs-lookup"><span data-stu-id="92931-156">Exclusion merge policy</span></span>

<span data-ttu-id="92931-157">Specifica i criteri di unione per le esclusioni.</span><span class="sxs-lookup"><span data-stu-id="92931-157">Specifies the merge policy for exclusions.</span></span> <span data-ttu-id="92931-158">Può essere una combinazione di esclusioni definite dall'amministratore e definite dall'utente ( ) o solo esclusioni definite `merge` dall'amministratore ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="92931-158">It can be a combination of administrator-defined and user-defined exclusions (`merge`) or only administrator-defined exclusions (`admin_only`).</span></span> <span data-ttu-id="92931-159">Questa impostazione può essere utilizzata per impedire agli utenti locali di definire le proprie esclusioni.</span><span class="sxs-lookup"><span data-stu-id="92931-159">This setting can be used to restrict local users from defining their own exclusions.</span></span>

|||
|:---|:---|
| <span data-ttu-id="92931-160">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="92931-160">**Key**</span></span> | <span data-ttu-id="92931-161">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="92931-161">exclusionsMergePolicy</span></span> |
| <span data-ttu-id="92931-162">**Data type**</span><span class="sxs-lookup"><span data-stu-id="92931-162">**Data type**</span></span> | <span data-ttu-id="92931-163">Stringa</span><span class="sxs-lookup"><span data-stu-id="92931-163">String</span></span> |
| <span data-ttu-id="92931-164">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="92931-164">**Possible values**</span></span> | <span data-ttu-id="92931-165">merge (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="92931-165">merge (default)</span></span> <br/> <span data-ttu-id="92931-166">admin_only</span><span class="sxs-lookup"><span data-stu-id="92931-166">admin_only</span></span> |
| <span data-ttu-id="92931-167">**Comments**</span><span class="sxs-lookup"><span data-stu-id="92931-167">**Comments**</span></span> | <span data-ttu-id="92931-168">Disponibile in Defender per Endpoint versione 100.83.73 o successiva.</span><span class="sxs-lookup"><span data-stu-id="92931-168">Available in Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="scan-exclusions"></a><span data-ttu-id="92931-169">Esclusioni analisi</span><span class="sxs-lookup"><span data-stu-id="92931-169">Scan exclusions</span></span>

<span data-ttu-id="92931-170">Entità escluse dall'analisi.</span><span class="sxs-lookup"><span data-stu-id="92931-170">Entities that have been excluded from the scan.</span></span> <span data-ttu-id="92931-171">Le esclusioni possono essere specificate da percorsi completi, estensioni o nomi di file.</span><span class="sxs-lookup"><span data-stu-id="92931-171">Exclusions can be specified by full paths, extensions, or file names.</span></span>

|||
|:---|:---|
| <span data-ttu-id="92931-172">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="92931-172">**Key**</span></span> | <span data-ttu-id="92931-173">esclusioni</span><span class="sxs-lookup"><span data-stu-id="92931-173">exclusions</span></span> |
| <span data-ttu-id="92931-174">**Data type**</span><span class="sxs-lookup"><span data-stu-id="92931-174">**Data type**</span></span> | <span data-ttu-id="92931-175">Dizionario (preferenza annidata)</span><span class="sxs-lookup"><span data-stu-id="92931-175">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="92931-176">**Comments**</span><span class="sxs-lookup"><span data-stu-id="92931-176">**Comments**</span></span> | <span data-ttu-id="92931-177">Per una descrizione del contenuto del dizionario, vedi le sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="92931-177">See the following sections for a description of the dictionary contents.</span></span> |

<span data-ttu-id="92931-178">**Tipo di esclusione**</span><span class="sxs-lookup"><span data-stu-id="92931-178">**Type of exclusion**</span></span>

<span data-ttu-id="92931-179">Specifica il tipo di contenuto escluso dall'analisi.</span><span class="sxs-lookup"><span data-stu-id="92931-179">Specifies the type of content excluded from the scan.</span></span>

|||
|:---|:---|
| <span data-ttu-id="92931-180">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="92931-180">**Key**</span></span> | <span data-ttu-id="92931-181">$type</span><span class="sxs-lookup"><span data-stu-id="92931-181">$type</span></span> |
| <span data-ttu-id="92931-182">**Data type**</span><span class="sxs-lookup"><span data-stu-id="92931-182">**Data type**</span></span> | <span data-ttu-id="92931-183">Stringa</span><span class="sxs-lookup"><span data-stu-id="92931-183">String</span></span> |
| <span data-ttu-id="92931-184">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="92931-184">**Possible values**</span></span> | <span data-ttu-id="92931-185">excludedPath</span><span class="sxs-lookup"><span data-stu-id="92931-185">excludedPath</span></span> <br/> <span data-ttu-id="92931-186">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="92931-186">excludedFileExtension</span></span> <br/> <span data-ttu-id="92931-187">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="92931-187">excludedFileName</span></span> |

<span data-ttu-id="92931-188">**Percorso del contenuto escluso**</span><span class="sxs-lookup"><span data-stu-id="92931-188">**Path to excluded content**</span></span>

<span data-ttu-id="92931-189">Utilizzato per escludere il contenuto dall'analisi in base al percorso completo del file.</span><span class="sxs-lookup"><span data-stu-id="92931-189">Used to exclude content from the scan by full file path.</span></span>

|||
|:---|:---|
| <span data-ttu-id="92931-190">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="92931-190">**Key**</span></span> | <span data-ttu-id="92931-191">path</span><span class="sxs-lookup"><span data-stu-id="92931-191">path</span></span> |
| <span data-ttu-id="92931-192">**Data type**</span><span class="sxs-lookup"><span data-stu-id="92931-192">**Data type**</span></span> | <span data-ttu-id="92931-193">Stringa</span><span class="sxs-lookup"><span data-stu-id="92931-193">String</span></span> |
| <span data-ttu-id="92931-194">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="92931-194">**Possible values**</span></span> | <span data-ttu-id="92931-195">percorsi validi</span><span class="sxs-lookup"><span data-stu-id="92931-195">valid paths</span></span> |
| <span data-ttu-id="92931-196">**Comments**</span><span class="sxs-lookup"><span data-stu-id="92931-196">**Comments**</span></span> | <span data-ttu-id="92931-197">Applicabile solo se *$type* *è excludedPath*</span><span class="sxs-lookup"><span data-stu-id="92931-197">Applicable only if *$type* is *excludedPath*</span></span> |

<span data-ttu-id="92931-198">**Tipo di percorso (file/directory)**</span><span class="sxs-lookup"><span data-stu-id="92931-198">**Path type (file / directory)**</span></span>

<span data-ttu-id="92931-199">Indica se la proprietà *path* fa riferimento a un file o a una directory.</span><span class="sxs-lookup"><span data-stu-id="92931-199">Indicates if the *path* property refers to a file or directory.</span></span> 

|||
|:---|:---|
| <span data-ttu-id="92931-200">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="92931-200">**Key**</span></span> | <span data-ttu-id="92931-201">isDirectory</span><span class="sxs-lookup"><span data-stu-id="92931-201">isDirectory</span></span> |
| <span data-ttu-id="92931-202">**Data type**</span><span class="sxs-lookup"><span data-stu-id="92931-202">**Data type**</span></span> | <span data-ttu-id="92931-203">Booleano</span><span class="sxs-lookup"><span data-stu-id="92931-203">Boolean</span></span> |
| <span data-ttu-id="92931-204">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="92931-204">**Possible values**</span></span> | <span data-ttu-id="92931-205">false (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="92931-205">false (default)</span></span> <br/> <span data-ttu-id="92931-206">true</span><span class="sxs-lookup"><span data-stu-id="92931-206">true</span></span> |
| <span data-ttu-id="92931-207">**Comments**</span><span class="sxs-lookup"><span data-stu-id="92931-207">**Comments**</span></span> | <span data-ttu-id="92931-208">Applicabile solo se *$type* *è excludedPath*</span><span class="sxs-lookup"><span data-stu-id="92931-208">Applicable only if *$type* is *excludedPath*</span></span> |

<span data-ttu-id="92931-209">**Estensione di file esclusa dall'analisi**</span><span class="sxs-lookup"><span data-stu-id="92931-209">**File extension excluded from the scan**</span></span>

<span data-ttu-id="92931-210">Usato per escludere il contenuto dall'analisi per estensione di file.</span><span class="sxs-lookup"><span data-stu-id="92931-210">Used to exclude content from the scan by file extension.</span></span>

|||
|:---|:---|
| <span data-ttu-id="92931-211">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="92931-211">**Key**</span></span> | <span data-ttu-id="92931-212">extension</span><span class="sxs-lookup"><span data-stu-id="92931-212">extension</span></span> |
| <span data-ttu-id="92931-213">**Data type**</span><span class="sxs-lookup"><span data-stu-id="92931-213">**Data type**</span></span> | <span data-ttu-id="92931-214">Stringa</span><span class="sxs-lookup"><span data-stu-id="92931-214">String</span></span> |
| <span data-ttu-id="92931-215">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="92931-215">**Possible values**</span></span> | <span data-ttu-id="92931-216">estensioni di file valide</span><span class="sxs-lookup"><span data-stu-id="92931-216">valid file extensions</span></span> |
| <span data-ttu-id="92931-217">**Comments**</span><span class="sxs-lookup"><span data-stu-id="92931-217">**Comments**</span></span> | <span data-ttu-id="92931-218">Applicabile solo se *$type* *è excludedFileExtension*</span><span class="sxs-lookup"><span data-stu-id="92931-218">Applicable only if *$type* is *excludedFileExtension*</span></span> |

<span data-ttu-id="92931-219">**Processo escluso dall'analisi**</span><span class="sxs-lookup"><span data-stu-id="92931-219">**Process excluded from the scan**</span></span>

<span data-ttu-id="92931-220">Specifica un processo per il quale tutte le attività di file vengono escluse dall'analisi.</span><span class="sxs-lookup"><span data-stu-id="92931-220">Specifies a process for which all file activity is excluded from scanning.</span></span> <span data-ttu-id="92931-221">Il processo può essere specificato in base al nome (ad esempio, `cat` ) o al percorso completo (ad esempio, `/bin/cat` ).</span><span class="sxs-lookup"><span data-stu-id="92931-221">The process can be specified either by its name (for example, `cat`) or full path (for example, `/bin/cat`).</span></span>

|||
|:---|:---|
| <span data-ttu-id="92931-222">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="92931-222">**Key**</span></span> | <span data-ttu-id="92931-223">name</span><span class="sxs-lookup"><span data-stu-id="92931-223">name</span></span> |
| <span data-ttu-id="92931-224">**Data type**</span><span class="sxs-lookup"><span data-stu-id="92931-224">**Data type**</span></span> | <span data-ttu-id="92931-225">Stringa</span><span class="sxs-lookup"><span data-stu-id="92931-225">String</span></span> |
| <span data-ttu-id="92931-226">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="92931-226">**Possible values**</span></span> | <span data-ttu-id="92931-227">qualsiasi stringa</span><span class="sxs-lookup"><span data-stu-id="92931-227">any string</span></span> |
| <span data-ttu-id="92931-228">**Comments**</span><span class="sxs-lookup"><span data-stu-id="92931-228">**Comments**</span></span> | <span data-ttu-id="92931-229">Applicabile solo se *$type* *è excludedFileName*</span><span class="sxs-lookup"><span data-stu-id="92931-229">Applicable only if *$type* is *excludedFileName*</span></span> |

#### <a name="allowed-threats"></a><span data-ttu-id="92931-230">Minacce consentite</span><span class="sxs-lookup"><span data-stu-id="92931-230">Allowed threats</span></span>

<span data-ttu-id="92931-231">Elenco delle minacce (identificate dal nome) che non sono bloccate dal prodotto e che possono essere eseguite.</span><span class="sxs-lookup"><span data-stu-id="92931-231">List of threats (identified by their name) that are not blocked by the product and are instead allowed to run.</span></span>

|||
|:---|:---|
| <span data-ttu-id="92931-232">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="92931-232">**Key**</span></span> | <span data-ttu-id="92931-233">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="92931-233">allowedThreats</span></span> |
| <span data-ttu-id="92931-234">**Data type**</span><span class="sxs-lookup"><span data-stu-id="92931-234">**Data type**</span></span> | <span data-ttu-id="92931-235">Matrice di stringhe</span><span class="sxs-lookup"><span data-stu-id="92931-235">Array of strings</span></span> |

#### <a name="disallowed-threat-actions"></a><span data-ttu-id="92931-236">Azioni di minaccia non consentite</span><span class="sxs-lookup"><span data-stu-id="92931-236">Disallowed threat actions</span></span>

<span data-ttu-id="92931-237">Limita le azioni che l'utente locale di un dispositivo può intraprendere quando vengono rilevate minacce.</span><span class="sxs-lookup"><span data-stu-id="92931-237">Restricts the actions that the local user of a device can take when threats are detected.</span></span> <span data-ttu-id="92931-238">Le azioni incluse in questo elenco non vengono visualizzate nell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="92931-238">The actions included in this list are not displayed in the user interface.</span></span>

|||
|:---|:---|
| <span data-ttu-id="92931-239">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="92931-239">**Key**</span></span> | <span data-ttu-id="92931-240">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="92931-240">disallowedThreatActions</span></span> |
| <span data-ttu-id="92931-241">**Data type**</span><span class="sxs-lookup"><span data-stu-id="92931-241">**Data type**</span></span> | <span data-ttu-id="92931-242">Matrice di stringhe</span><span class="sxs-lookup"><span data-stu-id="92931-242">Array of strings</span></span> |
| <span data-ttu-id="92931-243">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="92931-243">**Possible values**</span></span> | <span data-ttu-id="92931-244">allow (impedisce agli utenti di consentire minacce)</span><span class="sxs-lookup"><span data-stu-id="92931-244">allow (restricts users from allowing threats)</span></span> <br/> <span data-ttu-id="92931-245">restore (impedisce agli utenti di ripristinare le minacce dalla quarantena)</span><span class="sxs-lookup"><span data-stu-id="92931-245">restore (restricts users from restoring threats from the quarantine)</span></span> |
| <span data-ttu-id="92931-246">**Comments**</span><span class="sxs-lookup"><span data-stu-id="92931-246">**Comments**</span></span> | <span data-ttu-id="92931-247">Disponibile in Defender per Endpoint versione 100.83.73 o successiva.</span><span class="sxs-lookup"><span data-stu-id="92931-247">Available in Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="threat-type-settings"></a><span data-ttu-id="92931-248">Impostazioni del tipo di minaccia</span><span class="sxs-lookup"><span data-stu-id="92931-248">Threat type settings</span></span>

<span data-ttu-id="92931-249">La *preferenza threatTypeSettings* nel motore antivirus viene utilizzata per controllare la modalità di gestione di determinati tipi di minacce da parte del prodotto.</span><span class="sxs-lookup"><span data-stu-id="92931-249">The *threatTypeSettings* preference in the antivirus engine is used to control how certain threat types are handled by the product.</span></span>

|||
|:---|:---|
| <span data-ttu-id="92931-250">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="92931-250">**Key**</span></span> | <span data-ttu-id="92931-251">threatTypeSettings</span><span class="sxs-lookup"><span data-stu-id="92931-251">threatTypeSettings</span></span> |
| <span data-ttu-id="92931-252">**Data type**</span><span class="sxs-lookup"><span data-stu-id="92931-252">**Data type**</span></span> | <span data-ttu-id="92931-253">Dizionario (preferenza annidata)</span><span class="sxs-lookup"><span data-stu-id="92931-253">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="92931-254">**Comments**</span><span class="sxs-lookup"><span data-stu-id="92931-254">**Comments**</span></span> | <span data-ttu-id="92931-255">Per una descrizione del contenuto del dizionario, vedi le sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="92931-255">See the following sections for a description of the dictionary contents.</span></span> |

<span data-ttu-id="92931-256">**Tipo di minaccia**</span><span class="sxs-lookup"><span data-stu-id="92931-256">**Threat type**</span></span>

<span data-ttu-id="92931-257">Tipo di minaccia per cui è configurato il comportamento.</span><span class="sxs-lookup"><span data-stu-id="92931-257">Type of threat for which the behavior is configured.</span></span>

|||
|:---|:---|
| <span data-ttu-id="92931-258">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="92931-258">**Key**</span></span> | <span data-ttu-id="92931-259">chiave</span><span class="sxs-lookup"><span data-stu-id="92931-259">key</span></span> |
| <span data-ttu-id="92931-260">**Data type**</span><span class="sxs-lookup"><span data-stu-id="92931-260">**Data type**</span></span> | <span data-ttu-id="92931-261">Stringa</span><span class="sxs-lookup"><span data-stu-id="92931-261">String</span></span> |
| <span data-ttu-id="92931-262">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="92931-262">**Possible values**</span></span> | <span data-ttu-id="92931-263">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="92931-263">potentially_unwanted_application</span></span> <br/> <span data-ttu-id="92931-264">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="92931-264">archive_bomb</span></span> |

<span data-ttu-id="92931-265">**Procedura da seguire**</span><span class="sxs-lookup"><span data-stu-id="92931-265">**Action to take**</span></span>

<span data-ttu-id="92931-266">Azione da intraprendere quando si verifica una minaccia del tipo specificato nella sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="92931-266">Action to take when coming across a threat of the type specified in the preceding section.</span></span> <span data-ttu-id="92931-267">Può essere:</span><span class="sxs-lookup"><span data-stu-id="92931-267">Can be:</span></span>

- <span data-ttu-id="92931-268">**Controllo:** il dispositivo non è protetto da questo tipo di minaccia, ma viene registrata una voce relativa alla minaccia.</span><span class="sxs-lookup"><span data-stu-id="92931-268">**Audit**: The device is not protected against this type of threat, but an entry about the threat is logged.</span></span>
- <span data-ttu-id="92931-269">**Blocca**: il dispositivo è protetto da questo tipo di minaccia e si viene informati nella console di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="92931-269">**Block**: The device is protected against this type of threat and you are notified in the security console.</span></span>
- <span data-ttu-id="92931-270">**Disattivato:** il dispositivo non è protetto da questo tipo di minaccia e non viene registrato nulla.</span><span class="sxs-lookup"><span data-stu-id="92931-270">**Off**: The device is not protected against this type of threat and nothing is logged.</span></span>

|||
|:---|:---|
| <span data-ttu-id="92931-271">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="92931-271">**Key**</span></span> | <span data-ttu-id="92931-272">valore</span><span class="sxs-lookup"><span data-stu-id="92931-272">value</span></span> |
| <span data-ttu-id="92931-273">**Data type**</span><span class="sxs-lookup"><span data-stu-id="92931-273">**Data type**</span></span> | <span data-ttu-id="92931-274">Stringa</span><span class="sxs-lookup"><span data-stu-id="92931-274">String</span></span> |
| <span data-ttu-id="92931-275">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="92931-275">**Possible values**</span></span> | <span data-ttu-id="92931-276">audit (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="92931-276">audit (default)</span></span> <br/> <span data-ttu-id="92931-277">blocco</span><span class="sxs-lookup"><span data-stu-id="92931-277">block</span></span> <br/> <span data-ttu-id="92931-278">off</span><span class="sxs-lookup"><span data-stu-id="92931-278">off</span></span> |

#### <a name="threat-type-settings-merge-policy"></a><span data-ttu-id="92931-279">Criteri di unione delle impostazioni del tipo di minaccia</span><span class="sxs-lookup"><span data-stu-id="92931-279">Threat type settings merge policy</span></span>

<span data-ttu-id="92931-280">Specifica il criterio di unione per le impostazioni del tipo di minaccia.</span><span class="sxs-lookup"><span data-stu-id="92931-280">Specifies the merge policy for threat type settings.</span></span> <span data-ttu-id="92931-281">Può essere una combinazione di impostazioni definite dall'amministratore e definite dall'utente ( ) o solo impostazioni definite `merge` dall'amministratore ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="92931-281">This can be a combination of administrator-defined and user-defined settings (`merge`) or only administrator-defined settings (`admin_only`).</span></span> <span data-ttu-id="92931-282">Questa impostazione può essere usata per impedire agli utenti locali di definire le proprie impostazioni per diversi tipi di minacce.</span><span class="sxs-lookup"><span data-stu-id="92931-282">This setting can be used to restrict local users from defining their own settings for different threat types.</span></span>

|||
|:---|:---|
| <span data-ttu-id="92931-283">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="92931-283">**Key**</span></span> | <span data-ttu-id="92931-284">threatTypeSettingsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="92931-284">threatTypeSettingsMergePolicy</span></span> |
| <span data-ttu-id="92931-285">**Data type**</span><span class="sxs-lookup"><span data-stu-id="92931-285">**Data type**</span></span> | <span data-ttu-id="92931-286">Stringa</span><span class="sxs-lookup"><span data-stu-id="92931-286">String</span></span> |
| <span data-ttu-id="92931-287">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="92931-287">**Possible values**</span></span> | <span data-ttu-id="92931-288">merge (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="92931-288">merge (default)</span></span> <br/> <span data-ttu-id="92931-289">admin_only</span><span class="sxs-lookup"><span data-stu-id="92931-289">admin_only</span></span> |
| <span data-ttu-id="92931-290">**Comments**</span><span class="sxs-lookup"><span data-stu-id="92931-290">**Comments**</span></span> | <span data-ttu-id="92931-291">Disponibile in Defender per Endpoint versione 100.83.73 o successiva.</span><span class="sxs-lookup"><span data-stu-id="92931-291">Available in Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="antivirus-scan-history-retention-in-days"></a><span data-ttu-id="92931-292">Conservazione cronologia analisi antivirus (in giorni)</span><span class="sxs-lookup"><span data-stu-id="92931-292">Antivirus scan history retention (in days)</span></span>

<span data-ttu-id="92931-293">Specifica il numero di giorni in cui i risultati vengono conservati nella cronologia dell'analisi nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="92931-293">Specify the number of days that results are retained in the scan history on the device.</span></span> <span data-ttu-id="92931-294">I risultati dell'analisi precedente vengono rimossi dalla cronologia.</span><span class="sxs-lookup"><span data-stu-id="92931-294">Old scan results are removed from the history.</span></span> <span data-ttu-id="92931-295">Vecchi file in quarantena che vengono rimossi anche dal disco.</span><span class="sxs-lookup"><span data-stu-id="92931-295">Old quarantined files that are also removed from the disk.</span></span>

|||
|:---|:---|
| <span data-ttu-id="92931-296">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="92931-296">**Key**</span></span> | <span data-ttu-id="92931-297">scanResultsRetentionDays</span><span class="sxs-lookup"><span data-stu-id="92931-297">scanResultsRetentionDays</span></span> |
| <span data-ttu-id="92931-298">**Data type**</span><span class="sxs-lookup"><span data-stu-id="92931-298">**Data type**</span></span> | <span data-ttu-id="92931-299">Stringa</span><span class="sxs-lookup"><span data-stu-id="92931-299">String</span></span> |
| <span data-ttu-id="92931-300">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="92931-300">**Possible values**</span></span> | <span data-ttu-id="92931-301">90 (impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="92931-301">90 (default).</span></span> <span data-ttu-id="92931-302">I valori consentiti sono da 1 giorno a 180 giorni.</span><span class="sxs-lookup"><span data-stu-id="92931-302">Allowed values are from 1 day to 180 days.</span></span> |
| <span data-ttu-id="92931-303">**Comments**</span><span class="sxs-lookup"><span data-stu-id="92931-303">**Comments**</span></span> | <span data-ttu-id="92931-304">Disponibile in Defender per Endpoint versione 101.04.76 o successiva.</span><span class="sxs-lookup"><span data-stu-id="92931-304">Available in Defender for Endpoint version 101.04.76 or higher.</span></span> |

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a><span data-ttu-id="92931-305">Numero massimo di elementi nella cronologia dell'analisi antivirus</span><span class="sxs-lookup"><span data-stu-id="92931-305">Maximum number of items in the antivirus scan history</span></span>

<span data-ttu-id="92931-306">Specificare il numero massimo di voci da mantenere nella cronologia di analisi.</span><span class="sxs-lookup"><span data-stu-id="92931-306">Specify the maximum number of entries to keep in the scan history.</span></span> <span data-ttu-id="92931-307">Le voci includono tutte le analisi su richiesta eseguite in passato e tutti i rilevamenti antivirus.</span><span class="sxs-lookup"><span data-stu-id="92931-307">Entries include all on-demand scans performed in the past and all antivirus detections.</span></span>

|||
|:---|:---|
| <span data-ttu-id="92931-308">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="92931-308">**Key**</span></span> | <span data-ttu-id="92931-309">scanHistoryMaximumItems</span><span class="sxs-lookup"><span data-stu-id="92931-309">scanHistoryMaximumItems</span></span> |
| <span data-ttu-id="92931-310">**Data type**</span><span class="sxs-lookup"><span data-stu-id="92931-310">**Data type**</span></span> | <span data-ttu-id="92931-311">Stringa</span><span class="sxs-lookup"><span data-stu-id="92931-311">String</span></span> |
| <span data-ttu-id="92931-312">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="92931-312">**Possible values**</span></span> | <span data-ttu-id="92931-313">10000 (impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="92931-313">10000 (default).</span></span> <span data-ttu-id="92931-314">I valori consentiti sono da 5.000 elementi a 15.000 elementi.</span><span class="sxs-lookup"><span data-stu-id="92931-314">Allowed values are from 5000 items to 15000 items.</span></span> |
| <span data-ttu-id="92931-315">**Comments**</span><span class="sxs-lookup"><span data-stu-id="92931-315">**Comments**</span></span> | <span data-ttu-id="92931-316">Disponibile in Defender per Endpoint versione 101.04.76 o successiva.</span><span class="sxs-lookup"><span data-stu-id="92931-316">Available in Defender for Endpoint version 101.04.76 or higher.</span></span> |

### <a name="cloud-delivered-protection-preferences"></a><span data-ttu-id="92931-317">Preferenze di protezione per il cloud</span><span class="sxs-lookup"><span data-stu-id="92931-317">Cloud-delivered protection preferences</span></span>

<span data-ttu-id="92931-318">La *voce cloudService* nel profilo di configurazione viene utilizzata per configurare la funzionalità di protezione basata sul cloud del prodotto.</span><span class="sxs-lookup"><span data-stu-id="92931-318">The *cloudService* entry in the configuration profile is used to configure the cloud-driven protection feature of the product.</span></span>

|||
|:---|:---|
| <span data-ttu-id="92931-319">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="92931-319">**Key**</span></span> | <span data-ttu-id="92931-320">cloudService</span><span class="sxs-lookup"><span data-stu-id="92931-320">cloudService</span></span> |
| <span data-ttu-id="92931-321">**Data type**</span><span class="sxs-lookup"><span data-stu-id="92931-321">**Data type**</span></span> | <span data-ttu-id="92931-322">Dizionario (preferenza annidata)</span><span class="sxs-lookup"><span data-stu-id="92931-322">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="92931-323">**Comments**</span><span class="sxs-lookup"><span data-stu-id="92931-323">**Comments**</span></span> | <span data-ttu-id="92931-324">Per una descrizione del contenuto del dizionario, vedi le sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="92931-324">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-cloud-delivered-protection"></a><span data-ttu-id="92931-325">Abilitare/disabilitare la protezione recapitata nel cloud</span><span class="sxs-lookup"><span data-stu-id="92931-325">Enable / disable cloud delivered protection</span></span>

<span data-ttu-id="92931-326">Determina se la protezione consegnata dal cloud è abilitata o meno nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="92931-326">Determines whether cloud-delivered protection is enabled on the device or not.</span></span> <span data-ttu-id="92931-327">Per migliorare la sicurezza dei servizi, è consigliabile mantenere attivata questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="92931-327">To improve the security of your services, we recommend keeping this feature turned on.</span></span>

|||
|:---|:---|
| <span data-ttu-id="92931-328">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="92931-328">**Key**</span></span> | <span data-ttu-id="92931-329">abilitati</span><span class="sxs-lookup"><span data-stu-id="92931-329">enabled</span></span> |
| <span data-ttu-id="92931-330">**Data type**</span><span class="sxs-lookup"><span data-stu-id="92931-330">**Data type**</span></span> | <span data-ttu-id="92931-331">Booleano</span><span class="sxs-lookup"><span data-stu-id="92931-331">Boolean</span></span> |
| <span data-ttu-id="92931-332">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="92931-332">**Possible values**</span></span> | <span data-ttu-id="92931-333">true (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="92931-333">true (default)</span></span> <br/> <span data-ttu-id="92931-334">false</span><span class="sxs-lookup"><span data-stu-id="92931-334">false</span></span> |

#### <a name="diagnostic-collection-level"></a><span data-ttu-id="92931-335">Livello raccolta diagnostica</span><span class="sxs-lookup"><span data-stu-id="92931-335">Diagnostic collection level</span></span>

<span data-ttu-id="92931-336">I dati di diagnostica vengono usati per mantenere Defender per Endpoint sicuro e aggiornato, rilevare, diagnosticare e risolvere i problemi e apportare miglioramenti al prodotto.</span><span class="sxs-lookup"><span data-stu-id="92931-336">Diagnostic data is used to keep Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span> <span data-ttu-id="92931-337">Questa impostazione determina il livello di diagnostica inviato dal prodotto a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="92931-337">This setting determines the level of diagnostics sent by the product to Microsoft.</span></span>

|||
|:---|:---|
| <span data-ttu-id="92931-338">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="92931-338">**Key**</span></span> | <span data-ttu-id="92931-339">diagnosticLevel</span><span class="sxs-lookup"><span data-stu-id="92931-339">diagnosticLevel</span></span> |
| <span data-ttu-id="92931-340">**Data type**</span><span class="sxs-lookup"><span data-stu-id="92931-340">**Data type**</span></span> | <span data-ttu-id="92931-341">Stringa</span><span class="sxs-lookup"><span data-stu-id="92931-341">String</span></span> |
| <span data-ttu-id="92931-342">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="92931-342">**Possible values**</span></span> | <span data-ttu-id="92931-343">facoltativo (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="92931-343">optional (default)</span></span> <br/> <span data-ttu-id="92931-344">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="92931-344">required</span></span> |

#### <a name="enable--disable-automatic-sample-submissions"></a><span data-ttu-id="92931-345">Abilitare/disabilitare gli invii di esempio automatici</span><span class="sxs-lookup"><span data-stu-id="92931-345">Enable / disable automatic sample submissions</span></span>

<span data-ttu-id="92931-346">Determina se i campioni sospetti (che potrebbero contenere minacce) vengono inviati a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="92931-346">Determines whether suspicious samples (that are likely to contain threats) are sent to Microsoft.</span></span> <span data-ttu-id="92931-347">Esistono tre livelli per controllare l'invio di campioni:</span><span class="sxs-lookup"><span data-stu-id="92931-347">There are three levels for controlling sample submission:</span></span>

- <span data-ttu-id="92931-348">**Nessuno:** nessun campione sospetto viene inviato a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="92931-348">**None**: no suspicious samples are submitted to Microsoft.</span></span>
- <span data-ttu-id="92931-349">**Sicuro:** solo i campioni sospetti che non contengono informazioni personali vengono inviati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="92931-349">**Safe**: only suspicious samples that do not contain personally identifiable information (PII) are submitted automatically.</span></span> <span data-ttu-id="92931-350">Questo è il valore predefinito per questa impostazione.</span><span class="sxs-lookup"><span data-stu-id="92931-350">This is the default value for this setting.</span></span>
- <span data-ttu-id="92931-351">**All**: tutti i campioni sospetti vengono inviati a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="92931-351">**All**: all suspicious samples are submitted to Microsoft.</span></span>

|||
|:---|:---|
| <span data-ttu-id="92931-352">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="92931-352">**Key**</span></span> | <span data-ttu-id="92931-353">automaticSampleSubmissionConsent</span><span class="sxs-lookup"><span data-stu-id="92931-353">automaticSampleSubmissionConsent</span></span> |
| <span data-ttu-id="92931-354">**Data type**</span><span class="sxs-lookup"><span data-stu-id="92931-354">**Data type**</span></span> | <span data-ttu-id="92931-355">Stringa</span><span class="sxs-lookup"><span data-stu-id="92931-355">String</span></span> |
| <span data-ttu-id="92931-356">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="92931-356">**Possible values**</span></span> | <span data-ttu-id="92931-357">nessuno</span><span class="sxs-lookup"><span data-stu-id="92931-357">none</span></span> <br/> <span data-ttu-id="92931-358">safe (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="92931-358">safe (default)</span></span> <br/> <span data-ttu-id="92931-359">all</span><span class="sxs-lookup"><span data-stu-id="92931-359">all</span></span> |

#### <a name="enable--disable-automatic-security-intelligence-updates"></a><span data-ttu-id="92931-360">Abilitare/disabilitare gli aggiornamenti automatici delle funzionalità di intelligence per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="92931-360">Enable / disable automatic security intelligence updates</span></span>

<span data-ttu-id="92931-361">Determina se gli aggiornamenti delle funzionalità di intelligence per la sicurezza vengono installati automaticamente:</span><span class="sxs-lookup"><span data-stu-id="92931-361">Determines whether security intelligence updates are installed automatically:</span></span>

|||
|:---|:---|
| <span data-ttu-id="92931-362">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="92931-362">**Key**</span></span> | <span data-ttu-id="92931-363">automaticDefinitionUpdateEnabled</span><span class="sxs-lookup"><span data-stu-id="92931-363">automaticDefinitionUpdateEnabled</span></span> |
| <span data-ttu-id="92931-364">**Data type**</span><span class="sxs-lookup"><span data-stu-id="92931-364">**Data type**</span></span> | <span data-ttu-id="92931-365">Booleano</span><span class="sxs-lookup"><span data-stu-id="92931-365">Boolean</span></span> |
| <span data-ttu-id="92931-366">**Valori possibili**</span><span class="sxs-lookup"><span data-stu-id="92931-366">**Possible values**</span></span> | <span data-ttu-id="92931-367">true (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="92931-367">true (default)</span></span> <br/> <span data-ttu-id="92931-368">false</span><span class="sxs-lookup"><span data-stu-id="92931-368">false</span></span> |

## <a name="recommended-configuration-profile"></a><span data-ttu-id="92931-369">Profilo di configurazione consigliato</span><span class="sxs-lookup"><span data-stu-id="92931-369">Recommended configuration profile</span></span>

<span data-ttu-id="92931-370">Per iniziare, ti consigliamo di usare il profilo di configurazione seguente per la tua azienda per sfruttare tutte le funzionalità di protezione fornite da Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="92931-370">To get started, we recommend the following configuration profile for your enterprise to take advantage of all protection features that Defender for Endpoint provides.</span></span>

<span data-ttu-id="92931-371">Il profilo di configurazione seguente:</span><span class="sxs-lookup"><span data-stu-id="92931-371">The following configuration profile will:</span></span>

- <span data-ttu-id="92931-372">Abilitare la protezione in tempo reale (RTP)</span><span class="sxs-lookup"><span data-stu-id="92931-372">Enable real-time protection (RTP)</span></span>
- <span data-ttu-id="92931-373">Specificare la modalità di gestione dei seguenti tipi di minacce:</span><span class="sxs-lookup"><span data-stu-id="92931-373">Specify how the following threat types are handled:</span></span>
  - <span data-ttu-id="92931-374">**Le applicazioni potenzialmente indesiderate sono** bloccate</span><span class="sxs-lookup"><span data-stu-id="92931-374">**Potentially unwanted applications (PUA)** are blocked</span></span>
  - <span data-ttu-id="92931-375">**Le bombe di** archiviazione (file con una velocità di compressione elevata) vengono verificate nei log del prodotto</span><span class="sxs-lookup"><span data-stu-id="92931-375">**Archive bombs** (file with a high compression rate) are audited to the product logs</span></span>
- <span data-ttu-id="92931-376">Abilitare gli aggiornamenti automatici delle funzionalità di intelligence per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="92931-376">Enable automatic security intelligence updates</span></span>
- <span data-ttu-id="92931-377">Abilitare la protezione basata sul cloud</span><span class="sxs-lookup"><span data-stu-id="92931-377">Enable cloud-delivered protection</span></span>
- <span data-ttu-id="92931-378">Abilitare l'invio automatico di esempi a `safe` livello</span><span class="sxs-lookup"><span data-stu-id="92931-378">Enable automatic sample submission at `safe` level</span></span>

### <a name="sample-profile"></a><span data-ttu-id="92931-379">Profilo di esempio</span><span class="sxs-lookup"><span data-stu-id="92931-379">Sample profile</span></span>

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
      "enabled":true
   }
}
```

## <a name="full-configuration-profile-example"></a><span data-ttu-id="92931-380">Esempio di profilo di configurazione completo</span><span class="sxs-lookup"><span data-stu-id="92931-380">Full configuration profile example</span></span>

<span data-ttu-id="92931-381">Il profilo di configurazione seguente contiene voci per tutte le impostazioni descritte in questo documento e può essere utilizzato per scenari più avanzati in cui si desidera un maggiore controllo sul prodotto.</span><span class="sxs-lookup"><span data-stu-id="92931-381">The following configuration profile contains entries for all settings described in this document and can be used for more advanced scenarios where you want more control over the product.</span></span>

### <a name="full-profile"></a><span data-ttu-id="92931-382">Profilo completo</span><span class="sxs-lookup"><span data-stu-id="92931-382">Full profile</span></span>

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
            "path":"/home"
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
      "automaticDefinitionUpdateEnabled":true
   }
}
```

## <a name="configuration-profile-validation"></a><span data-ttu-id="92931-383">Convalida del profilo di configurazione</span><span class="sxs-lookup"><span data-stu-id="92931-383">Configuration profile validation</span></span>

<span data-ttu-id="92931-384">Il profilo di configurazione deve essere un file in formato JSON valido.</span><span class="sxs-lookup"><span data-stu-id="92931-384">The configuration profile must be a valid JSON-formatted file.</span></span> <span data-ttu-id="92931-385">Per verificarlo, è possibile utilizzare diversi strumenti.</span><span class="sxs-lookup"><span data-stu-id="92931-385">There are a number of tools that can be used to verify this.</span></span> <span data-ttu-id="92931-386">Ad esempio, se hai `python` installato nel dispositivo:</span><span class="sxs-lookup"><span data-stu-id="92931-386">For example, if you have `python` installed on your device:</span></span>

```bash
python -m json.tool mdatp_managed.json
```

<span data-ttu-id="92931-387">Se json è ben formato, il comando precedente lo restituisce al terminale e restituisce un codice di uscita di `0` .</span><span class="sxs-lookup"><span data-stu-id="92931-387">If the JSON is well-formed, the above command outputs it back to the Terminal and returns an exit code of `0`.</span></span> <span data-ttu-id="92931-388">In caso contrario, viene visualizzato un errore che descrive il problema e il comando restituisce un codice di uscita di `1` .</span><span class="sxs-lookup"><span data-stu-id="92931-388">Otherwise, an error that describes the issue is displayed and the command returns an exit code of `1`.</span></span>

## <a name="configuration-profile-deployment"></a><span data-ttu-id="92931-389">Distribuzione dei profili di configurazione</span><span class="sxs-lookup"><span data-stu-id="92931-389">Configuration profile deployment</span></span>

<span data-ttu-id="92931-390">Dopo aver creato il profilo di configurazione per l'organizzazione, è possibile distribuirlo tramite lo strumento di gestione utilizzato dall'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="92931-390">Once you've built the configuration profile for your enterprise, you can deploy it through the management tool that your enterprise is using.</span></span> <span data-ttu-id="92931-391">Defender for Endpoint per Linux legge la configurazione gestita dal file */etc/opt/microsoft/mdatp/managed/mdatp_managed.json.*</span><span class="sxs-lookup"><span data-stu-id="92931-391">Defender for Endpoint for Linux reads the managed configuration from the */etc/opt/microsoft/mdatp/managed/mdatp_managed.json* file.</span></span>