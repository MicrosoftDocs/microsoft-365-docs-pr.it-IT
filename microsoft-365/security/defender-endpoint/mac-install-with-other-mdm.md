---
title: Distribuzione con un sistema mdm (Mobile Device Management) diverso per Microsoft Defender ATP per Mac
description: Installare Microsoft Defender ATP per Mac in altre soluzioni di gestione.
keywords: microsoft, defender, atp, mac, installazione, distribuire, macos, catalina, mojave, high sierra
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: mavel
author: maximvelichko
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: e3a20f0a356a32eddc05b3792c0c04c23197a7b0
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185696"
---
# <a name="deployment-with-a-different-mobile-device-management-mdm-system-for-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="0e038-104">Distribuzione con un sistema mdm (Mobile Device Management) diverso per Microsoft Defender per Endpoint per Mac</span><span class="sxs-lookup"><span data-stu-id="0e038-104">Deployment with a different Mobile Device Management (MDM) system for Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="0e038-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="0e038-105">**Applies to:**</span></span>
- [<span data-ttu-id="0e038-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="0e038-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="0e038-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0e038-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="0e038-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="0e038-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="0e038-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="0e038-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)
 
## <a name="prerequisites-and-system-requirements"></a><span data-ttu-id="0e038-110">Prerequisiti e requisiti di sistema</span><span class="sxs-lookup"><span data-stu-id="0e038-110">Prerequisites and system requirements</span></span>

<span data-ttu-id="0e038-111">Prima di iniziare, vedi la pagina principale di [Microsoft Defender per Endpoint per Mac](microsoft-defender-endpoint-mac.md) per una descrizione dei prerequisiti e dei requisiti di sistema per la versione software corrente.</span><span class="sxs-lookup"><span data-stu-id="0e038-111">Before you get started, see [the main Microsoft Defender for Endpoint for Mac page](microsoft-defender-endpoint-mac.md) for a description of prerequisites and system requirements for the current software version.</span></span>

## <a name="approach"></a><span data-ttu-id="0e038-112">Approccio</span><span class="sxs-lookup"><span data-stu-id="0e038-112">Approach</span></span>

> [!CAUTION]
> <span data-ttu-id="0e038-113">Attualmente, Microsoft supporta solo Intune e JAMF per la distribuzione e la gestione di Microsoft Defender per Endpoint per Mac.</span><span class="sxs-lookup"><span data-stu-id="0e038-113">Currently, Microsoft oficially supports only Intune and JAMF for the deployment and management of Microsoft Defender for Endpoint for Mac.</span></span> <span data-ttu-id="0e038-114">Microsoft non fa alcuna garanzia, espressa o implicita, rispetto alle informazioni fornite di seguito.</span><span class="sxs-lookup"><span data-stu-id="0e038-114">Microsoft makes no warranties, express or implied, with respect to the information provided below.</span></span>

<span data-ttu-id="0e038-115">Se l'organizzazione usa una soluzione di gestione dei dispositivi mobili (MDM) non ufficialmente supportata, ciò non significa che non sei in grado di distribuire o eseguire Microsoft Defender per Endpoint per Mac.</span><span class="sxs-lookup"><span data-stu-id="0e038-115">If your organization uses a Mobile Device Management (MDM) solution that is not officially supported, this does not mean you are unable to deploy or run Microsoft Defender for Endpoint for Mac.</span></span>

<span data-ttu-id="0e038-116">Microsoft Defender per Endpoint per Mac non dipende da funzionalità specifiche del fornitore.</span><span class="sxs-lookup"><span data-stu-id="0e038-116">Microsoft Defender for Endpoint for Mac does not depend on any vendor-specific features.</span></span> <span data-ttu-id="0e038-117">Può essere usato con qualsiasi soluzione MDM che supporti le funzionalità seguenti:</span><span class="sxs-lookup"><span data-stu-id="0e038-117">It can be used with any MDM solution that supports the following features:</span></span>

- <span data-ttu-id="0e038-118">Distribuisci un file pkg macOS nei dispositivi gestiti.</span><span class="sxs-lookup"><span data-stu-id="0e038-118">Deploy a macOS .pkg to managed devices.</span></span>
- <span data-ttu-id="0e038-119">Distribuire i profili di configurazione del sistema macOS nei dispositivi gestiti.</span><span class="sxs-lookup"><span data-stu-id="0e038-119">Deploy macOS system configuration profiles to managed devices.</span></span>
- <span data-ttu-id="0e038-120">Eseguire uno strumento o uno script arbitrario configurato dall'amministratore nei dispositivi gestiti.</span><span class="sxs-lookup"><span data-stu-id="0e038-120">Run an arbitrary admin-configured tool/script on managed devices.</span></span>

<span data-ttu-id="0e038-121">La maggior parte delle soluzioni MDM moderne include queste funzionalità, tuttavia, possono chiamarle in modo diverso.</span><span class="sxs-lookup"><span data-stu-id="0e038-121">Most modern MDM solutions include these features, however, they may call them differently.</span></span>

<span data-ttu-id="0e038-122">Puoi tuttavia distribuire Defender senza l'ultimo requisito dell'elenco precedente:</span><span class="sxs-lookup"><span data-stu-id="0e038-122">You can deploy Defender without the last requirement from the preceding list, however:</span></span>

- <span data-ttu-id="0e038-123">Non sarà possibile raccogliere lo stato in modo centralizzato</span><span class="sxs-lookup"><span data-stu-id="0e038-123">You will not be able to collect status in a centralized way</span></span>
- <span data-ttu-id="0e038-124">Se decidi di disinstallare Defender, dovrai accedere al dispositivo client in locale come amministratore</span><span class="sxs-lookup"><span data-stu-id="0e038-124">If you decide to uninstall Defender, you will need to log on to the client device locally as an administrator</span></span>

## <a name="deployment"></a><span data-ttu-id="0e038-125">Distribuzione</span><span class="sxs-lookup"><span data-stu-id="0e038-125">Deployment</span></span>

<span data-ttu-id="0e038-126">La maggior parte delle soluzioni MDM usa lo stesso modello per la gestione dei dispositivi macOS, con una terminologia simile.</span><span class="sxs-lookup"><span data-stu-id="0e038-126">Most MDM solutions use the same model for managing macOS devices, with similar terminology.</span></span> <span data-ttu-id="0e038-127">Usa [la distribuzione basata su JAMF](mac-install-with-jamf.md) come modello.</span><span class="sxs-lookup"><span data-stu-id="0e038-127">Use [JAMF-based deployment](mac-install-with-jamf.md) as a template.</span></span>

### <a name="package"></a><span data-ttu-id="0e038-128">Pacchetto</span><span class="sxs-lookup"><span data-stu-id="0e038-128">Package</span></span>

<span data-ttu-id="0e038-129">Configurare la distribuzione di [un pacchetto dell'applicazione necessario](mac-install-with-jamf.md), con il pacchetto di installazione (wdav.pkg) scaricato da Microsoft Defender Security [Center.](mac-install-with-jamf.md)</span><span class="sxs-lookup"><span data-stu-id="0e038-129">Configure deployment of a [required application package](mac-install-with-jamf.md), with the installation package (wdav.pkg) downloaded from [Microsoft Defender Security Center](mac-install-with-jamf.md).</span></span>

<span data-ttu-id="0e038-130">Per distribuire il pacchetto nell'organizzazione, usa le istruzioni associate alla soluzione MDM.</span><span class="sxs-lookup"><span data-stu-id="0e038-130">In order to deploy the package to your enterprise, use the instructions associated with your MDM solution.</span></span>

### <a name="license-settings"></a><span data-ttu-id="0e038-131">Impostazioni delle licenze</span><span class="sxs-lookup"><span data-stu-id="0e038-131">License settings</span></span>

<span data-ttu-id="0e038-132">Configurare un [profilo di configurazione del sistema](mac-install-with-jamf.md).</span><span class="sxs-lookup"><span data-stu-id="0e038-132">Set up [a system configuration profile](mac-install-with-jamf.md).</span></span> <span data-ttu-id="0e038-133">La soluzione MDM potrebbe chiamarla come "Profilo impostazioni personalizzate", poiché Microsoft Defender per Endpoint per Mac non fa parte di macOS.</span><span class="sxs-lookup"><span data-stu-id="0e038-133">Your MDM solution may call it something like "Custom Settings Profile", as Microsoft Defender for Endpoint for Mac is not part of macOS.</span></span>

<span data-ttu-id="0e038-134">Usa l'elenco delle proprietà jamf/WindowsDefenderATPOnboarding.plist, che può essere estratto da un pacchetto di onboarding scaricato da [Microsoft Defender Security Center.](mac-install-with-jamf.md)</span><span class="sxs-lookup"><span data-stu-id="0e038-134">Use the property list, jamf/WindowsDefenderATPOnboarding.plist, which can be extracted from an onboarding package downloaded from [Microsoft Defender Security Center](mac-install-with-jamf.md).</span></span>
<span data-ttu-id="0e038-135">Il sistema potrebbe supportare un elenco di proprietà arbitrario in formato XML.</span><span class="sxs-lookup"><span data-stu-id="0e038-135">Your system may support an arbitrary property list in XML format.</span></span> <span data-ttu-id="0e038-136">Puoi caricare il file jamf/WindowsDefenderATPOnboarding.plist così come è in questo caso.</span><span class="sxs-lookup"><span data-stu-id="0e038-136">You can upload the jamf/WindowsDefenderATPOnboarding.plist file as-is in that case.</span></span>
<span data-ttu-id="0e038-137">In alternativa, potrebbe essere necessario convertire prima l'elenco delle proprietà in un formato diverso.</span><span class="sxs-lookup"><span data-stu-id="0e038-137">Alternatively, it may require you to convert the property list to a different format first.</span></span>

<span data-ttu-id="0e038-138">In genere, il profilo personalizzato ha un ID, un nome o un attributo di dominio.</span><span class="sxs-lookup"><span data-stu-id="0e038-138">Typically, your custom profile has an ID, name, or domain attribute.</span></span> <span data-ttu-id="0e038-139">È necessario utilizzare esattamente "com.microsoft.wdav.atp" per questo valore.</span><span class="sxs-lookup"><span data-stu-id="0e038-139">You must use exactly "com.microsoft.wdav.atp" for this value.</span></span>
<span data-ttu-id="0e038-140">MDM lo usa per distribuire il file di impostazioni in **/Library/Managed Preferences/com.microsoft.wdav.atp.plist** in un dispositivo client e Defender usa questo file per caricare le informazioni di onboarding.</span><span class="sxs-lookup"><span data-stu-id="0e038-140">MDM uses it to deploy the settings file to **/Library/Managed Preferences/com.microsoft.wdav.atp.plist** on a client device, and Defender uses this file for loading the onboarding information.</span></span>

### <a name="kernel-extension-policy"></a><span data-ttu-id="0e038-141">Criteri di estensione kernel</span><span class="sxs-lookup"><span data-stu-id="0e038-141">Kernel extension policy</span></span>

<span data-ttu-id="0e038-142">Configurare un criterio di estensione KEXT o kernel.</span><span class="sxs-lookup"><span data-stu-id="0e038-142">Set up a KEXT or kernel extension policy.</span></span> <span data-ttu-id="0e038-143">Usa l'identificatore del team **UBF8T346G9** per consentire le estensioni del kernel fornite da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0e038-143">Use team identifier **UBF8T346G9** to allow kernel extensions provided by Microsoft.</span></span>

### <a name="system-extension-policy"></a><span data-ttu-id="0e038-144">Criteri di estensione di sistema</span><span class="sxs-lookup"><span data-stu-id="0e038-144">System extension policy</span></span>

<span data-ttu-id="0e038-145">Configurare un criterio di estensione di sistema.</span><span class="sxs-lookup"><span data-stu-id="0e038-145">Set up a system extension policy.</span></span> <span data-ttu-id="0e038-146">Usa l'identificatore del team **UBF8T346G9** e approva gli identificatori bundle seguenti:</span><span class="sxs-lookup"><span data-stu-id="0e038-146">Use team identifier **UBF8T346G9** and approve the following bundle identifiers:</span></span>

- <span data-ttu-id="0e038-147">com.microsoft.wdav.epsext</span><span class="sxs-lookup"><span data-stu-id="0e038-147">com.microsoft.wdav.epsext</span></span>
- <span data-ttu-id="0e038-148">com.microsoft.wdav.netext</span><span class="sxs-lookup"><span data-stu-id="0e038-148">com.microsoft.wdav.netext</span></span>

### <a name="full-disk-access-policy"></a><span data-ttu-id="0e038-149">Criteri di accesso completo al disco</span><span class="sxs-lookup"><span data-stu-id="0e038-149">Full disk access policy</span></span>

<span data-ttu-id="0e038-150">Concedere l'accesso completo al disco ai componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="0e038-150">Grant Full Disk Access to the following components:</span></span>

- <span data-ttu-id="0e038-151">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="0e038-151">Microsoft Defender for Endpoint</span></span>
    - <span data-ttu-id="0e038-152">Identificatore: `com.microsoft.wdav`</span><span class="sxs-lookup"><span data-stu-id="0e038-152">Identifier: `com.microsoft.wdav`</span></span>
    - <span data-ttu-id="0e038-153">Tipo di identificatore: ID bundle</span><span class="sxs-lookup"><span data-stu-id="0e038-153">Identifier Type: Bundle ID</span></span>
    - <span data-ttu-id="0e038-154">Requisiti del codice: `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="0e038-154">Code Requirement: `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>

- <span data-ttu-id="0e038-155">Estensione microsoft Defender for Endpoint Security</span><span class="sxs-lookup"><span data-stu-id="0e038-155">Microsoft Defender for Endpoint Security Extension</span></span>
    - <span data-ttu-id="0e038-156">Identificatore: `com.microsoft.wdav.epsext`</span><span class="sxs-lookup"><span data-stu-id="0e038-156">Identifier: `com.microsoft.wdav.epsext`</span></span>
    - <span data-ttu-id="0e038-157">Tipo di identificatore: ID bundle</span><span class="sxs-lookup"><span data-stu-id="0e038-157">Identifier Type: Bundle ID</span></span>
    - <span data-ttu-id="0e038-158">Requisiti del codice: `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="0e038-158">Code Requirement: `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>

### <a name="network-extension-policy"></a><span data-ttu-id="0e038-159">Criteri di estensione di rete</span><span class="sxs-lookup"><span data-stu-id="0e038-159">Network extension policy</span></span>

<span data-ttu-id="0e038-160">Come parte delle funzionalità di rilevamento e risposta degli endpoint, Microsoft Defender per Endpoint per Mac esamina il traffico socket e segnala queste informazioni al portale di Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="0e038-160">As part of the Endpoint Detection and Response capabilities, Microsoft Defender for Endpoint for Mac inspects socket traffic and reports this information to the Microsoft Defender Security Center portal.</span></span> <span data-ttu-id="0e038-161">Il criterio seguente consente all'estensione di rete di eseguire questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="0e038-161">The following policy allows the network extension to perform this functionality.</span></span>

- <span data-ttu-id="0e038-162">Tipo di filtro: Plug-in</span><span class="sxs-lookup"><span data-stu-id="0e038-162">Filter type: Plugin</span></span>
- <span data-ttu-id="0e038-163">Identificatore bundle plug-in: `com.microsoft.wdav`</span><span class="sxs-lookup"><span data-stu-id="0e038-163">Plugin bundle identifier: `com.microsoft.wdav`</span></span>
- <span data-ttu-id="0e038-164">Identificatore bundle del provider di dati di filtro: `com.microsoft.wdav.netext`</span><span class="sxs-lookup"><span data-stu-id="0e038-164">Filter data provider bundle identifier: `com.microsoft.wdav.netext`</span></span>
- <span data-ttu-id="0e038-165">Requisito designato dal provider di dati di filtro: `identifier "com.microsoft.wdav.tunnelext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="0e038-165">Filter data provider designated requirement: `identifier "com.microsoft.wdav.tunnelext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>
- <span data-ttu-id="0e038-166">Socket di filtro: `true`</span><span class="sxs-lookup"><span data-stu-id="0e038-166">Filter sockets: `true`</span></span>

## <a name="check-installation-status"></a><span data-ttu-id="0e038-167">Controllare lo stato di installazione</span><span class="sxs-lookup"><span data-stu-id="0e038-167">Check installation status</span></span>

<span data-ttu-id="0e038-168">Eseguire [Microsoft Defender for Endpoint](mac-install-with-jamf.md) in un dispositivo client per controllare lo stato di onboarding.</span><span class="sxs-lookup"><span data-stu-id="0e038-168">Run [Microsoft Defender for Endpoint](mac-install-with-jamf.md) on a client device to check the onboarding status.</span></span>
