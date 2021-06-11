---
title: Microsoft Defender per Endpoint Device Control Removable Archiviazione Protection
description: Comprendere le "funzionalità che consentono di impedire a utenti o computer o a entrambi di utilizzare supporti di archiviazione rimovibili non autorizzati
keywords: supporti di archiviazione rimovibili
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-smandalika
author: v-smandalika
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: c9b97c2157ba8090628af23b2ab54cf38f04d8c6
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538388"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-protection"></a><span data-ttu-id="f3cbd-104">Microsoft Defender per Endpoint Device Control Removable Archiviazione Protection</span><span class="sxs-lookup"><span data-stu-id="f3cbd-104">Microsoft Defender for Endpoint Device Control Removable Storage Protection</span></span>

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="f3cbd-105">Microsoft Defender for Endpoint Device Control Removable Archiviazione Protection impedisce a utenti o computer o a entrambi di utilizzare supporti di archiviazione rimovibili non autorizzati.</span><span class="sxs-lookup"><span data-stu-id="f3cbd-105">Microsoft Defender for Endpoint Device Control Removable Storage Protection prevents user or machine or both from using unauthorized removable storage media.</span></span>

## <a name="protection-policies"></a><span data-ttu-id="f3cbd-106">Criteri di protezione</span><span class="sxs-lookup"><span data-stu-id="f3cbd-106">Protection policies</span></span>

### <a name="device-installation"></a><span data-ttu-id="f3cbd-107">Installazione del dispositivo</span><span class="sxs-lookup"><span data-stu-id="f3cbd-107">Device installation</span></span>

<span data-ttu-id="f3cbd-108">**Funzionalità:** impedisci l'installazione con o senza esclusione in base a diverse proprietà del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f3cbd-108">**Capabilities** - Prevent installation with or without exclusion based on various device properties.</span></span>

<span data-ttu-id="f3cbd-109">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="f3cbd-109">**Description**</span></span>
- <span data-ttu-id="f3cbd-110">Applicato a livello di computer: lo stesso criterio si applica a qualsiasi utente connesso.</span><span class="sxs-lookup"><span data-stu-id="f3cbd-110">Applied at machine level: the same policy applies for any logged on user.</span></span>
- <span data-ttu-id="f3cbd-111">Supporta MEM e GPO.</span><span class="sxs-lookup"><span data-stu-id="f3cbd-111">Supports MEM and GPO.</span></span>
- <span data-ttu-id="f3cbd-112">Supportato '[Proprietà dispositivo](#device-properties)' come elencato.</span><span class="sxs-lookup"><span data-stu-id="f3cbd-112">Supported  ‘[Device Properties](#device-properties)’ as listed.</span></span>
- <span data-ttu-id="f3cbd-113">Per altre informazioni su Windows, vedi Come controllare i dispositivi USB e altri supporti [rimovibili con Microsoft Defender for Endpoint.](control-usb-devices-using-intune.md)</span><span class="sxs-lookup"><span data-stu-id="f3cbd-113">For more information on Windows, see [How to control USB devices and other removable media using Microsoft Defender for Endpoint](control-usb-devices-using-intune.md).</span></span>

<span data-ttu-id="f3cbd-114">**Piattaforma supportata** - Windows 10</span><span class="sxs-lookup"><span data-stu-id="f3cbd-114">**Supported Platform** - Windows 10</span></span>

<span data-ttu-id="f3cbd-115">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="f3cbd-115">**Description**</span></span>
- <span data-ttu-id="f3cbd-116">Applicato a livello di computer: lo stesso criterio si applica a qualsiasi utente connesso</span><span class="sxs-lookup"><span data-stu-id="f3cbd-116">Applied at machine level: the same policy applies for any logged on user</span></span>
- <span data-ttu-id="f3cbd-117">Per informazioni specifiche su macOS, vedi [Controllo dispositivo per macOS.](mac-device-control-overview.md)</span><span class="sxs-lookup"><span data-stu-id="f3cbd-117">For macOS specific information, see [Device control for macOS](mac-device-control-overview.md).</span></span>
 
<span data-ttu-id="f3cbd-118">**Piattaforma supportata** - macOS Catalina 10.15.4+ (con le estensioni di sistema abilitate)</span><span class="sxs-lookup"><span data-stu-id="f3cbd-118">**Supported platform** - macOS Catalina 10.15.4+ (with system extensions enabled)</span></span>

### <a name="removable-storage-access-control"></a><span data-ttu-id="f3cbd-119">Controllo di accesso all'archiviazione rimovibile</span><span class="sxs-lookup"><span data-stu-id="f3cbd-119">Removable storage Access Control</span></span>

<span data-ttu-id="f3cbd-120">**Funzionalità**</span><span class="sxs-lookup"><span data-stu-id="f3cbd-120">**Capabilities**</span></span>
- <span data-ttu-id="f3cbd-121">*Controllo* Accesso in lettura o scrittura o esecuzione all'archiviazione rimovibile in base a diverse proprietà del dispositivo, con o senza esclusione.</span><span class="sxs-lookup"><span data-stu-id="f3cbd-121">*Audit* Read or Write or Execute access to removable storage based on various device properties, with or without an exclusion.</span></span>
- <span data-ttu-id="f3cbd-122">*Impedisci* Accesso in lettura o scrittura o in esecuzione con o senza esclusione: consentire un dispositivo specifico in base a diverse proprietà del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f3cbd-122">*Prevent* Read or Write or Execute access with or without an exclusion - Allow specific device based on various device properties.</span></span>

<span data-ttu-id="f3cbd-123">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="f3cbd-123">**Description**</span></span>
- <span data-ttu-id="f3cbd-124">Applicato a un computer o a un utente o a entrambi: consente solo a utenti specifici che eseguono l'accesso in lettura/scrittura/esecuzione a uno specifico spazio di archiviazione rimovibile in un computer specifico.</span><span class="sxs-lookup"><span data-stu-id="f3cbd-124">Applied at either machine or user or both – only allow specific people performing Read/Write/Execute access to specific removable storage on specific machine.</span></span>
- <span data-ttu-id="f3cbd-125">Supporta l'URI OMA e l'oggetto Criteri di gruppo MEM.</span><span class="sxs-lookup"><span data-stu-id="f3cbd-125">Support MEM OMA-URI and GPO.</span></span>
- <span data-ttu-id="f3cbd-126">Supportato '[Proprietà dispositivo](#device-properties)' come elencato.</span><span class="sxs-lookup"><span data-stu-id="f3cbd-126">Supported  ‘[Device Properties](#device-properties)’ as listed.</span></span>
- <span data-ttu-id="f3cbd-127">Per la funzionalità in Windows, vedere [Removable storage Access Control](device-control-removable-storage-access-control.md).</span><span class="sxs-lookup"><span data-stu-id="f3cbd-127">For feature in Windows, see [Removable storage Access Control](device-control-removable-storage-access-control.md).</span></span>

<span data-ttu-id="f3cbd-128">**Piattaforma supportata** - Windows 10</span><span class="sxs-lookup"><span data-stu-id="f3cbd-128">**Supported Platform** - Windows 10</span></span>

<span data-ttu-id="f3cbd-129">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="f3cbd-129">**Description**</span></span>
- <span data-ttu-id="f3cbd-130">Applicato a livello di computer: lo stesso criterio si applica a qualsiasi utente connesso.</span><span class="sxs-lookup"><span data-stu-id="f3cbd-130">Applied at machine level: the same policy applies for any logged on user.</span></span>
- <span data-ttu-id="f3cbd-131">Per informazioni specifiche su macOS, vedi [Controllo dispositivo per macOS.](mac-device-control-overview.md)</span><span class="sxs-lookup"><span data-stu-id="f3cbd-131">For macOS specific information, see [Device control for macOS](mac-device-control-overview.md).</span></span>
 
<span data-ttu-id="f3cbd-132">**Piattaforma supportata** - macOS Catalina 10.15.4+ (con le estensioni di sistema abilitate)</span><span class="sxs-lookup"><span data-stu-id="f3cbd-132">**Supported platform** - macOS Catalina 10.15.4+ (with system extensions enabled)</span></span>

### <a name="windows-portable-device-access-control"></a><span data-ttu-id="f3cbd-133">Windows Controllo di accesso dei dispositivi portatili</span><span class="sxs-lookup"><span data-stu-id="f3cbd-133">Windows Portable Device Access Control</span></span>

<span data-ttu-id="f3cbd-134">**Funzionalità** : nega l'accesso in lettura o scrittura [Windows qualsiasi](/windows-hardware/drivers/portable/)dispositivo portatile, ad esempio Tablet, iPhone.</span><span class="sxs-lookup"><span data-stu-id="f3cbd-134">**Capabilities** - Deny Read or Write access to any [Windows Portable Device](/windows-hardware/drivers/portable/), for example: Tablet, iPhone.</span></span>

<span data-ttu-id="f3cbd-135">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="f3cbd-135">**Description**</span></span>
- <span data-ttu-id="f3cbd-136">Applicato a un computer o a un utente o a entrambi.</span><span class="sxs-lookup"><span data-stu-id="f3cbd-136">Applied at either machine or user or both.</span></span>
- <span data-ttu-id="f3cbd-137">Supporta l'URI OMA e l'oggetto Criteri di gruppo MEM.</span><span class="sxs-lookup"><span data-stu-id="f3cbd-137">Support MEM OMA-URI and GPO.</span></span>

<span data-ttu-id="f3cbd-138">**Piattaforma supportata** - Windows 10</span><span class="sxs-lookup"><span data-stu-id="f3cbd-138">**Supported Platform** - Windows 10</span></span>

### <a name="endpoint-dlp-removable-storage"></a><span data-ttu-id="f3cbd-139">Endpoint DLP Archivi rimovibili</span><span class="sxs-lookup"><span data-stu-id="f3cbd-139">Endpoint DLP Removable storage</span></span>

<span data-ttu-id="f3cbd-140">**Funzionalità:** controlla o avvisa o impedisci a un utente di copiare un elemento o informazioni in un supporto rimovibile o in un dispositivo USB.</span><span class="sxs-lookup"><span data-stu-id="f3cbd-140">**Capabilities** - Audit or Warn or Prevent a user from copying an item or information to removable media or USB device.</span></span>

<span data-ttu-id="f3cbd-141">**Descrizione-** Per ulteriori informazioni su Windows, vedere Informazioni sulla prevenzione della perdita di dati Microsoft 365 [endpoint.](../../compliance/endpoint-dlp-learn-about.md)</span><span class="sxs-lookup"><span data-stu-id="f3cbd-141">**Description** - For more information on Windows, see [Learn about Microsoft 365 Endpoint data loss prevention](../../compliance/endpoint-dlp-learn-about.md).</span></span>

<span data-ttu-id="f3cbd-142">**Piattaforma supportata** - Windows 10</span><span class="sxs-lookup"><span data-stu-id="f3cbd-142">**Supported Platform** - Windows 10</span></span>

### <a name="bitlocker"></a><span data-ttu-id="f3cbd-143">BitLocker</span><span class="sxs-lookup"><span data-stu-id="f3cbd-143">BitLocker</span></span> 

<span data-ttu-id="f3cbd-144">**Funzionalità**</span><span class="sxs-lookup"><span data-stu-id="f3cbd-144">**Capabilities**</span></span>
- <span data-ttu-id="f3cbd-145">Bloccare i dati da scrivere in unità rimovibili non BitLocker protette.</span><span class="sxs-lookup"><span data-stu-id="f3cbd-145">Block data to be written to removable drives that aren't BitLocker protected.</span></span>
- <span data-ttu-id="f3cbd-146">Bloccare l'accesso alle unità rimovibili a meno che non siano state crittografate in un computer di proprietà dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="f3cbd-146">Block access to removable drives unless they were encrypted on a computer owned by your organization</span></span>
 
<span data-ttu-id="f3cbd-147">**Descrizione** - Per ulteriori informazioni su Windows, [vedere BitLocker – Removable Drive Impostazioni](/mem/intune/protect/endpoint-security-disk-encryption-profile-settings).</span><span class="sxs-lookup"><span data-stu-id="f3cbd-147">**Description** - For more information on Windows, see [BitLocker – Removable Drive Settings](/mem/intune/protect/endpoint-security-disk-encryption-profile-settings).</span></span>

<span data-ttu-id="f3cbd-148">**Piattaforma supportata** - Windows 10</span><span class="sxs-lookup"><span data-stu-id="f3cbd-148">**Supported Platform** - Windows 10</span></span>

## <a name="device-properties"></a><span data-ttu-id="f3cbd-149">Proprietà del dispositivo</span><span class="sxs-lookup"><span data-stu-id="f3cbd-149">Device properties</span></span>

<span data-ttu-id="f3cbd-150">Microsoft Defender for Endpoint Device Control Removable Archiviazione Protection consente di limitare l'accesso all'archiviazione rimovibile in base alle proprietà descritte nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="f3cbd-150">Microsoft Defender for Endpoint Device Control Removable Storage Protection allows you to restrict the removable storage access based on the properties described in the table below:</span></span>


|<span data-ttu-id="f3cbd-151">Nome proprietà</span><span class="sxs-lookup"><span data-stu-id="f3cbd-151">Property Name</span></span>  |<span data-ttu-id="f3cbd-152">Criteri applicabili</span><span class="sxs-lookup"><span data-stu-id="f3cbd-152">Applicable Policies</span></span>  |<span data-ttu-id="f3cbd-153">Si applica ai sistemi operativi</span><span class="sxs-lookup"><span data-stu-id="f3cbd-153">Applies to Operating Systems</span></span>  |<span data-ttu-id="f3cbd-154">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f3cbd-154">Description</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="f3cbd-155">Classe Device</span><span class="sxs-lookup"><span data-stu-id="f3cbd-155">Device Class</span></span>    |     [<span data-ttu-id="f3cbd-156">Come controllare i dispositivi USB e altri supporti rimovibili con Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f3cbd-156">How to control USB devices and other removable media using Microsoft Defender for Endpoint</span></span>](control-usb-devices-using-intune.md)     |   <span data-ttu-id="f3cbd-157">Windows</span><span class="sxs-lookup"><span data-stu-id="f3cbd-157">Windows</span></span>      |  <span data-ttu-id="f3cbd-158">Per informazioni sui formati dell'ID dispositivo, vedi [classe di configurazione del dispositivo.](/windows-hardware/drivers/install/system-defined-device-setup-classes-available-to-vendors)</span><span class="sxs-lookup"><span data-stu-id="f3cbd-158">For information about Device ID formats, see [device setup class](/windows-hardware/drivers/install/system-defined-device-setup-classes-available-to-vendors).</span></span> <span data-ttu-id="f3cbd-159">**Nota:** l'installazione dei dispositivi può essere applicata a qualsiasi dispositivo, non solo all'archiviazione rimovibile.</span><span class="sxs-lookup"><span data-stu-id="f3cbd-159">**Note**: Device Installation can be applied to any devices, not only Removable storage.</span></span>       |
|<span data-ttu-id="f3cbd-160">ID primario</span><span class="sxs-lookup"><span data-stu-id="f3cbd-160">Primary ID</span></span>   |     <span data-ttu-id="f3cbd-161">Controllo di accesso all'archiviazione rimovibile</span><span class="sxs-lookup"><span data-stu-id="f3cbd-161">Removable storage Access Control</span></span>    |   <span data-ttu-id="f3cbd-162">Windows</span><span class="sxs-lookup"><span data-stu-id="f3cbd-162">Windows</span></span>      |      <span data-ttu-id="f3cbd-163">L'ID primario include l'archiviazione rimovibile e il CD/DVD.</span><span class="sxs-lookup"><span data-stu-id="f3cbd-163">The Primary ID includes removable storage and CD/DVD.</span></span>   |
|<span data-ttu-id="f3cbd-164">ID dispositivo</span><span class="sxs-lookup"><span data-stu-id="f3cbd-164">Device ID</span></span>     |  <span data-ttu-id="f3cbd-165">[Come controllare i dispositivi USB e altri supporti rimovibili con Microsoft Defender for Endpoint;](control-usb-devices-using-intune.md) Controllo di accesso all'archiviazione rimovibile</span><span class="sxs-lookup"><span data-stu-id="f3cbd-165">[How to control USB devices and other removable media using Microsoft Defender for Endpoint](control-usb-devices-using-intune.md); Removable storage Access Control</span></span>       |      <span data-ttu-id="f3cbd-166">Windows</span><span class="sxs-lookup"><span data-stu-id="f3cbd-166">Windows</span></span>   |    <span data-ttu-id="f3cbd-167">Per informazioni sui formati id dispositivo, vedere [Identificatori USB standard,](/windows-hardware/drivers/install/standard-usb-identifiers)ad esempio USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07</span><span class="sxs-lookup"><span data-stu-id="f3cbd-167">For information about Device ID formats, see [Standard USB Identifiers](/windows-hardware/drivers/install/standard-usb-identifiers), for example, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07</span></span>      |
|<span data-ttu-id="f3cbd-168">Hardware ID</span><span class="sxs-lookup"><span data-stu-id="f3cbd-168">Hardware ID</span></span>     |     <span data-ttu-id="f3cbd-169">[Come controllare i dispositivi USB e altri supporti rimovibili con Microsoft Defender for Endpoint;](control-usb-devices-using-intune.md) Controllo di accesso all'archiviazione rimovibile</span><span class="sxs-lookup"><span data-stu-id="f3cbd-169">[How to control USB devices and other removable media using Microsoft Defender for Endpoint](control-usb-devices-using-intune.md); Removable storage Access Control</span></span>    |     <span data-ttu-id="f3cbd-170">Windows</span><span class="sxs-lookup"><span data-stu-id="f3cbd-170">Windows</span></span>    |    <span data-ttu-id="f3cbd-171">Stringa che identifica il dispositivo nel sistema, ad esempio USBSTOR\DiskGeneric_Flash_Disk______8.07; **Nota:** l'ID hardware non è univoco. dispositivi diversi possono condividere lo stesso valore.</span><span class="sxs-lookup"><span data-stu-id="f3cbd-171">A string identified the device in the system, for example, USBSTOR\DiskGeneric_Flash_Disk______8.07; **Note**: Hardware ID is not unique; different devices may share same value.</span></span>|
|<span data-ttu-id="f3cbd-172">ID istanza</span><span class="sxs-lookup"><span data-stu-id="f3cbd-172">Instance ID</span></span>    | <span data-ttu-id="f3cbd-173">Installazione del dispositivo; Controllo di accesso all'archiviazione rimovibile</span><span class="sxs-lookup"><span data-stu-id="f3cbd-173">Device Installation; Removable storage Access Control</span></span>     |     <span data-ttu-id="f3cbd-174">Windows</span><span class="sxs-lookup"><span data-stu-id="f3cbd-174">Windows</span></span>    |   <span data-ttu-id="f3cbd-175">Una stringa identifica in modo univoco il dispositivo nel sistema, ad esempio USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0</span><span class="sxs-lookup"><span data-stu-id="f3cbd-175">A string uniquely identifies the device in the system, for example, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0</span></span>      |
|<span data-ttu-id="f3cbd-176">Nome descrittivo</span><span class="sxs-lookup"><span data-stu-id="f3cbd-176">Friendly Name</span></span>     |     <span data-ttu-id="f3cbd-177">Controllo di accesso all'archiviazione rimovibile</span><span class="sxs-lookup"><span data-stu-id="f3cbd-177">Removable storage Access Control</span></span>    |   <span data-ttu-id="f3cbd-178">Windows</span><span class="sxs-lookup"><span data-stu-id="f3cbd-178">Windows</span></span>      |    <span data-ttu-id="f3cbd-179">Stringa collegata al dispositivo, ad esempio Dispositivo USB generico flash disk</span><span class="sxs-lookup"><span data-stu-id="f3cbd-179">A string attached to the device, for example, Generic Flash Disk USB Device</span></span>     |
|<span data-ttu-id="f3cbd-180">ID fornitore/ID prodotto</span><span class="sxs-lookup"><span data-stu-id="f3cbd-180">Vendor ID / Product ID</span></span>     |  <span data-ttu-id="f3cbd-181">Controllo di accesso all'archiviazione rimovibile</span><span class="sxs-lookup"><span data-stu-id="f3cbd-181">Removable storage Access Control</span></span>       |   <span data-ttu-id="f3cbd-182">Windows Mac</span><span class="sxs-lookup"><span data-stu-id="f3cbd-182">Windows Mac</span></span>      |     <span data-ttu-id="f3cbd-183">ID fornitore è il codice fornitore a quattro cifre che il comitato USB assegna al fornitore.</span><span class="sxs-lookup"><span data-stu-id="f3cbd-183">Vendor ID is the four-digit vendor code that the USB committee assigns to the vendor.</span></span> <span data-ttu-id="f3cbd-184">ID prodotto è il codice prodotto a quattro cifre che il fornitore assegna al dispositivo. Supportare il carattere jolly.</span><span class="sxs-lookup"><span data-stu-id="f3cbd-184">Product ID is the four-digit product code that the vendor assigns to the device; Support wildcard.</span></span>    |
|<span data-ttu-id="f3cbd-185">Serial NumberId</span><span class="sxs-lookup"><span data-stu-id="f3cbd-185">Serial NumberId</span></span>     |     <span data-ttu-id="f3cbd-186">Controllo di accesso all'archiviazione rimovibile</span><span class="sxs-lookup"><span data-stu-id="f3cbd-186">Removable storage Access Control</span></span>    |      <span data-ttu-id="f3cbd-187">Windows Mac</span><span class="sxs-lookup"><span data-stu-id="f3cbd-187">Windows Mac</span></span>   |     <span data-ttu-id="f3cbd-188">Ad esempio, <SerialNumberId>002324B534BCB431B000058A</SerialNumberId></span><span class="sxs-lookup"><span data-stu-id="f3cbd-188">For example, <SerialNumberId>002324B534BCB431B000058A</SerialNumberId></span></span>    |

## <a name="related-topic"></a><span data-ttu-id="f3cbd-189">Argomento correlato</span><span class="sxs-lookup"><span data-stu-id="f3cbd-189">Related topic</span></span>

- [<span data-ttu-id="f3cbd-190">Microsoft Defender for Endpoint Device Control Removable Archiviazione Access Control</span><span class="sxs-lookup"><span data-stu-id="f3cbd-190">Microsoft Defender for Endpoint Device Control Removable Storage Access Control</span></span>](device-control-removable-storage-access-control.md)

