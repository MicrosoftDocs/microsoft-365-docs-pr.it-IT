---
title: Microsoft Defender for Endpoint Device Control Removable Archiviazione Access Control
description: Informazioni dettagliate su Microsoft Defender for Endpoint
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
ms.openlocfilehash: fba74990d8e4465f957acda83e66e1dc43a317e8
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841187"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-access-control"></a><span data-ttu-id="3fe93-104">Microsoft Defender for Endpoint Device Control Removable Archiviazione Access Control</span><span class="sxs-lookup"><span data-stu-id="3fe93-104">Microsoft Defender for Endpoint Device Control Removable Storage Access Control</span></span>

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="3fe93-105">Microsoft Defender for Endpoint Device Control Removable Archiviazione Access Control consente di eseguire l'attività seguente:</span><span class="sxs-lookup"><span data-stu-id="3fe93-105">Microsoft Defender for Endpoint Device Control Removable Storage Access Control enables you to do the following task:</span></span>
- <span data-ttu-id="3fe93-106">controllo, consentendo o impedendo l'accesso in lettura, scrittura o esecuzione all'archiviazione rimovibile con o senza esclusione</span><span class="sxs-lookup"><span data-stu-id="3fe93-106">auditing, allowing or preventing the read, write or execute access to removable storage with or without exclusion</span></span>

|<span data-ttu-id="3fe93-107">Privilegio</span><span class="sxs-lookup"><span data-stu-id="3fe93-107">Privilege</span></span> |<span data-ttu-id="3fe93-108">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="3fe93-108">Permission</span></span>  |
|---------|---------|
|<span data-ttu-id="3fe93-109">Access</span><span class="sxs-lookup"><span data-stu-id="3fe93-109">Access</span></span>    |  <span data-ttu-id="3fe93-110">Lettura, scrittura ed esecuzione</span><span class="sxs-lookup"><span data-stu-id="3fe93-110">Read, Write, Execute</span></span>       |
|<span data-ttu-id="3fe93-111">Modalità azione</span><span class="sxs-lookup"><span data-stu-id="3fe93-111">Action Mode</span></span>    |    <span data-ttu-id="3fe93-112">Controllo, Consenti, Impedisci</span><span class="sxs-lookup"><span data-stu-id="3fe93-112">Audit, Allow, Prevent</span></span>     |
|<span data-ttu-id="3fe93-113">Supporto CSP</span><span class="sxs-lookup"><span data-stu-id="3fe93-113">CSP Support</span></span>   |   <span data-ttu-id="3fe93-114">Sì</span><span class="sxs-lookup"><span data-stu-id="3fe93-114">Yes</span></span>      |
|<span data-ttu-id="3fe93-115">Supporto oggetti Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="3fe93-115">GPO Support</span></span>    |   <span data-ttu-id="3fe93-116">Sì</span><span class="sxs-lookup"><span data-stu-id="3fe93-116">Yes</span></span>      |
|<span data-ttu-id="3fe93-117">Supporto basato sull'utente</span><span class="sxs-lookup"><span data-stu-id="3fe93-117">User-based Support</span></span>     |   <span data-ttu-id="3fe93-118">Sì</span><span class="sxs-lookup"><span data-stu-id="3fe93-118">Yes</span></span>      |
|<span data-ttu-id="3fe93-119">Supporto basato su computer</span><span class="sxs-lookup"><span data-stu-id="3fe93-119">Machine-based Support</span></span>    |    <span data-ttu-id="3fe93-120">Sì</span><span class="sxs-lookup"><span data-stu-id="3fe93-120">Yes</span></span>     |

## <a name="prepare-your-endpoints"></a><span data-ttu-id="3fe93-121">Preparare gli endpoint</span><span class="sxs-lookup"><span data-stu-id="3fe93-121">Prepare your endpoints</span></span>

<span data-ttu-id="3fe93-122">Distribuire Il controllo di accesso Archiviazione rimovibili nei dispositivi Windows 10 con antimalware Client versione **4.18.2103.3 o successiva.**</span><span class="sxs-lookup"><span data-stu-id="3fe93-122">Deploy Removable Storage Access Control on Windows 10 devices that have Anti-malware Client Version **4.18.2103.3 or later**.</span></span>
1. <span data-ttu-id="3fe93-123">**4.18.2104 o** versione successiva : Aggiungere SerialNumberId, VID_PID, supporto degli oggetti Criteri di gruppo basati su filepath</span><span class="sxs-lookup"><span data-stu-id="3fe93-123">**4.18.2104 or later**: Add SerialNumberId, VID_PID, filepath-based GPO support</span></span>

2. <span data-ttu-id="3fe93-124">**4.18.2105 o** versione successiva : Aggiungere il supporto dei caratteri jolly per HardwareId/DeviceId/InstancePathId/FriendlyNameId/SerialNumberId, la combinazione di un utente specifico in un computer specifico, SSD rimovibile (un SSD SanDisk Extreme)/supporto USB Attached SCSI (UAS)</span><span class="sxs-lookup"><span data-stu-id="3fe93-124">**4.18.2105 or later**: Add Wildcard support for HardwareId/DeviceId/InstancePathId/FriendlyNameId/SerialNumberId, the combination of specific user on specific machine, removeable SSD (a SanDisk Extreme SSD)/USB Attached SCSI (UAS) support</span></span>

:::image type="content" source="images/powershell.png" alt-text="Interfaccia di PowerShell":::

## <a name="policy-properties"></a><span data-ttu-id="3fe93-126">Proprietà dei criteri</span><span class="sxs-lookup"><span data-stu-id="3fe93-126">Policy properties</span></span>

<span data-ttu-id="3fe93-127">È possibile utilizzare le proprietà seguenti per creare un gruppo di archiviazione rimovibile:</span><span class="sxs-lookup"><span data-stu-id="3fe93-127">You can use the following properties to create a removable storage group:</span></span>

<span data-ttu-id="3fe93-128">**Nome proprietà: ID gruppo**</span><span class="sxs-lookup"><span data-stu-id="3fe93-128">**Property name: Group ID**</span></span>

1. <span data-ttu-id="3fe93-129">Descrizione: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), un ID univoco, rappresenta il gruppo e verrà utilizzato nel criterio.</span><span class="sxs-lookup"><span data-stu-id="3fe93-129">Description: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), a unique ID, represents the group and will be used in the policy.</span></span>

<span data-ttu-id="3fe93-130">**Nome proprietà: DescriptorIdList**</span><span class="sxs-lookup"><span data-stu-id="3fe93-130">**Property name: DescriptorIdList**</span></span>

1. <span data-ttu-id="3fe93-131">Descrizione: elenca le proprietà del dispositivo che vuoi usare per coprire il gruppo.</span><span class="sxs-lookup"><span data-stu-id="3fe93-131">Description: List the device properties you want to use to cover in the group.</span></span>
<span data-ttu-id="3fe93-132">Elenca le proprietà del dispositivo che vuoi usare per coprire il gruppo.</span><span class="sxs-lookup"><span data-stu-id="3fe93-132">List the device properties you want to use to cover in the group.</span></span>
<span data-ttu-id="3fe93-133">Per ogni proprietà del dispositivo, vedi **la sezione Proprietà dispositivo** sopra riportata per ulteriori dettagli.</span><span class="sxs-lookup"><span data-stu-id="3fe93-133">For each device property, see **Device Properties** section above for more detail.</span></span>

1. <span data-ttu-id="3fe93-134">Opzioni:</span><span class="sxs-lookup"><span data-stu-id="3fe93-134">Options:</span></span>
    - <span data-ttu-id="3fe93-135">ID primario</span><span class="sxs-lookup"><span data-stu-id="3fe93-135">Primary ID</span></span>
        - <span data-ttu-id="3fe93-136">RemovableMediaDevices</span><span class="sxs-lookup"><span data-stu-id="3fe93-136">RemovableMediaDevices</span></span>
        - <span data-ttu-id="3fe93-137">CdRomDevices</span><span class="sxs-lookup"><span data-stu-id="3fe93-137">CdRomDevices</span></span>
    - <span data-ttu-id="3fe93-138">DeviceId</span><span class="sxs-lookup"><span data-stu-id="3fe93-138">DeviceId</span></span>
    - <span data-ttu-id="3fe93-139">HardwareId</span><span class="sxs-lookup"><span data-stu-id="3fe93-139">HardwareId</span></span>
    - <span data-ttu-id="3fe93-140">InstancePathId: InstancePathId è una stringa che identifica in modo univoco il dispositivo nel sistema, ad esempio USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0.</span><span class="sxs-lookup"><span data-stu-id="3fe93-140">InstancePathId: InstancePathId is a string that uniquely identifies the device in the system, for example, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0.</span></span> <span data-ttu-id="3fe93-141">Il numero alla fine (ad esempio **&0)** rappresenta lo slot disponibile e può cambiare da dispositivo a dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3fe93-141">The number at the end (for example **&0**) represents the available slot and may change from device to device.</span></span> <span data-ttu-id="3fe93-142">Per ottenere risultati ottimali, utilizzare un carattere jolly alla fine.</span><span class="sxs-lookup"><span data-stu-id="3fe93-142">For best results, use a wildcard at the end.</span></span> <span data-ttu-id="3fe93-143">Ad esempio, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611\*</span><span class="sxs-lookup"><span data-stu-id="3fe93-143">For example, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611\*</span></span>
    - <span data-ttu-id="3fe93-144">FriendlyNameId</span><span class="sxs-lookup"><span data-stu-id="3fe93-144">FriendlyNameId</span></span>
    - <span data-ttu-id="3fe93-145">SerialNumberId</span><span class="sxs-lookup"><span data-stu-id="3fe93-145">SerialNumberId</span></span>
    - <span data-ttu-id="3fe93-146">VID</span><span class="sxs-lookup"><span data-stu-id="3fe93-146">VID</span></span>
    - <span data-ttu-id="3fe93-147">PID</span><span class="sxs-lookup"><span data-stu-id="3fe93-147">PID</span></span>
    - <span data-ttu-id="3fe93-148">VID_PID</span><span class="sxs-lookup"><span data-stu-id="3fe93-148">VID_PID</span></span>
        - <span data-ttu-id="3fe93-149">0751_55E0: corrisponde a questa coppia VID/PID esatta</span><span class="sxs-lookup"><span data-stu-id="3fe93-149">0751_55E0: match this exact VID/PID pair</span></span>
        - <span data-ttu-id="3fe93-150">_55E0: corrisponde a qualsiasi supporto con PID=55E0</span><span class="sxs-lookup"><span data-stu-id="3fe93-150">_55E0: match any media with PID=55E0</span></span>
        - <span data-ttu-id="3fe93-151">0751_: corrisponde a qualsiasi supporto con VID=0751</span><span class="sxs-lookup"><span data-stu-id="3fe93-151">0751_: match any media with VID=0751</span></span>
        
<span data-ttu-id="3fe93-152">**Nome proprietà: MatchType**</span><span class="sxs-lookup"><span data-stu-id="3fe93-152">**Property name: MatchType**</span></span> 

1. <span data-ttu-id="3fe93-153">Descrizione: quando in DescriptorIDList vengono utilizzate più proprietà del dispositivo, MatchType definisce la relazione.</span><span class="sxs-lookup"><span data-stu-id="3fe93-153">Description: When there are multiple device properties being used in the DescriptorIDList, MatchType defines the relationship.</span></span>

1. <span data-ttu-id="3fe93-154">Opzioni:</span><span class="sxs-lookup"><span data-stu-id="3fe93-154">Options:</span></span>
    - <span data-ttu-id="3fe93-155">MatchAll: tutti gli attributi in DescriptorIdList saranno **relazione And.** Ad esempio, se l'amministratore inserisce DeviceID e InstancePathID per ogni USB connesso, il sistema controllera' se l'USB soddisfa entrambi i valori.</span><span class="sxs-lookup"><span data-stu-id="3fe93-155">MatchAll: Any attributes under the DescriptorIdList will be **And** relationship; for example, if administrator puts DeviceID and InstancePathID, for every connected USB, system will check to see whether the USB meets both values.</span></span>

    - <span data-ttu-id="3fe93-156">MatchAny: gli attributi sotto DescriptorIdList saranno **relazione Or.** Ad esempio, se l'amministratore inserisce DeviceID e InstancePathID, per ogni USB connessa, il sistema farà l'imposizione purché l'USB abbia un **valore DeviceID** o **InstanceID** identico.</span><span class="sxs-lookup"><span data-stu-id="3fe93-156">MatchAny: The attributes under the DescriptorIdList will be **Or** relationship; for example, if administrator puts DeviceID and InstancePathID, for every connected USB, system will do the enforcement as long as the USB has either an identical **DeviceID** or **InstanceID** value.</span></span>

<span data-ttu-id="3fe93-157">Di seguito sono riportate le proprietà dei criteri di controllo di accesso:</span><span class="sxs-lookup"><span data-stu-id="3fe93-157">Following are the access control policy properties:</span></span>

<span data-ttu-id="3fe93-158">**Nome proprietà: PolicyRuleId**</span><span class="sxs-lookup"><span data-stu-id="3fe93-158">**Property name: PolicyRuleId**</span></span>

1. <span data-ttu-id="3fe93-159">Descrizione: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), un ID univoco, rappresenta il criterio e verrà utilizzato nei report e nella risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="3fe93-159">Description: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), a unique ID, represents the policy and will be used in the reporting and troubleshooting.</span></span>

<span data-ttu-id="3fe93-160">**Nome proprietà: IncludedIdList**</span><span class="sxs-lookup"><span data-stu-id="3fe93-160">**Property name: IncludedIdList**</span></span>

1. <span data-ttu-id="3fe93-161">Descrizione: i gruppi a cui verrà applicato il criterio.</span><span class="sxs-lookup"><span data-stu-id="3fe93-161">Description: The group(s) that the policy will be applied to.</span></span> <span data-ttu-id="3fe93-162">Se vengono aggiunti più gruppi, il criterio verrà applicato a tutti i supporti di tutti i gruppi.</span><span class="sxs-lookup"><span data-stu-id="3fe93-162">If multiple groups are added, the policy will be applied to any media in all those groups.</span></span>

1. <span data-ttu-id="3fe93-163">Opzioni: l'ID gruppo/GUID deve essere utilizzato in questa istanza.</span><span class="sxs-lookup"><span data-stu-id="3fe93-163">Options: The Group ID/GUID must be used at this instance.</span></span>

<span data-ttu-id="3fe93-164">Nell'esempio seguente viene illustrato l'utilizzo di GroupID:</span><span class="sxs-lookup"><span data-stu-id="3fe93-164">The following example shows the usage of GroupID:</span></span>

`<IncludedIdList> <GroupId>{EAA4CCE5-F6C9-4760-8BAD-FDCC76A2ACA1}</GroupId> </IncludedIdList>`

<span data-ttu-id="3fe93-165">**Nome proprietà: ExcludedIDList**</span><span class="sxs-lookup"><span data-stu-id="3fe93-165">**Property name: ExcludedIDList**</span></span>

1. <span data-ttu-id="3fe93-166">Descrizione: i gruppi a cui non verrà applicato il criterio.</span><span class="sxs-lookup"><span data-stu-id="3fe93-166">Description: The group(s) that the policy will not be applied to.</span></span>
1. <span data-ttu-id="3fe93-167">Opzioni: l'ID gruppo/GUID deve essere utilizzato in questa istanza.</span><span class="sxs-lookup"><span data-stu-id="3fe93-167">Options: The Group ID/GUID must be used at this instance.</span></span>

<span data-ttu-id="3fe93-168">**Nome proprietà: ID voce**</span><span class="sxs-lookup"><span data-stu-id="3fe93-168">**Property name: Entry ID**</span></span>

1. <span data-ttu-id="3fe93-169">Descrizione: Un oggetto PolicyRule può avere più voci. ogni voce con un GUID univoco indica a Device Control una restrizione.</span><span class="sxs-lookup"><span data-stu-id="3fe93-169">Description: One PolicyRule can have multiple entries; each entry with a unique GUID tells Device Control one restriction.</span></span>

<span data-ttu-id="3fe93-170">**Nome proprietà: Type**</span><span class="sxs-lookup"><span data-stu-id="3fe93-170">**Property name: Type**</span></span>

1. <span data-ttu-id="3fe93-171">Descrizione: definisce l'azione per i gruppi di archiviazione rimovibili in IncludedIDList.</span><span class="sxs-lookup"><span data-stu-id="3fe93-171">Description: Defines the action for the removable storage groups in IncludedIDList.</span></span>
    - <span data-ttu-id="3fe93-172">Imposizione: Consenti o Nega</span><span class="sxs-lookup"><span data-stu-id="3fe93-172">Enforcement: Allow or Deny</span></span>
    - <span data-ttu-id="3fe93-173">Controllo: AuditAllowed o AuditDenied</span><span class="sxs-lookup"><span data-stu-id="3fe93-173">Audit: AuditAllowed or AuditDenied</span></span> 
1. <span data-ttu-id="3fe93-174">Opzioni:</span><span class="sxs-lookup"><span data-stu-id="3fe93-174">Options:</span></span>
    - <span data-ttu-id="3fe93-175">Consenti</span><span class="sxs-lookup"><span data-stu-id="3fe93-175">Allow</span></span>
    - <span data-ttu-id="3fe93-176">Nega</span><span class="sxs-lookup"><span data-stu-id="3fe93-176">Deny</span></span>
    - <span data-ttu-id="3fe93-177">AuditAllowed: definisce la notifica e l'evento quando è consentito l'accesso</span><span class="sxs-lookup"><span data-stu-id="3fe93-177">AuditAllowed: Defines notification and event when access is allowed</span></span>
    - <span data-ttu-id="3fe93-178">AuditDenied: definisce la notifica e l'evento quando l'accesso viene negato. deve collaborare con **la voce** Deny.</span><span class="sxs-lookup"><span data-stu-id="3fe93-178">AuditDenied: Defines notification and event when access is denied; has to work together with **Deny** entry.</span></span>

<span data-ttu-id="3fe93-179">Quando sono presenti tipi di conflitto per lo stesso supporto, il sistema applierà il primo nel criterio.</span><span class="sxs-lookup"><span data-stu-id="3fe93-179">When there are conflict types for the same media, the system will apply the first one in the policy.</span></span> <span data-ttu-id="3fe93-180">Un esempio di tipo di conflitto è **Allow** e **Deny.**</span><span class="sxs-lookup"><span data-stu-id="3fe93-180">An example of a conflict type is **Allow** and **Deny**.</span></span>

<span data-ttu-id="3fe93-181">**Nome proprietà: Opzioni**</span><span class="sxs-lookup"><span data-stu-id="3fe93-181">**Property name: Options**</span></span>

1. <span data-ttu-id="3fe93-182">Descrizione: definisce se visualizzare o meno la notifica.</span><span class="sxs-lookup"><span data-stu-id="3fe93-182">Description: Defines whether to display notification or not.</span></span>

   :::image type="content" source="images/device-status.png" alt-text="Schermata in cui è possibile visualizzare lo stato del dispositivo":::

1. <span data-ttu-id="3fe93-184">Opzioni: 0-4.</span><span class="sxs-lookup"><span data-stu-id="3fe93-184">Options: 0-4.</span></span> <span data-ttu-id="3fe93-185">Quando è selezionata l'opzione Digitazione Consenti o Nega:</span><span class="sxs-lookup"><span data-stu-id="3fe93-185">When Type Allow or Deny is selected:</span></span>

   - <span data-ttu-id="3fe93-186">0: nothing</span><span class="sxs-lookup"><span data-stu-id="3fe93-186">0: nothing</span></span>
   - <span data-ttu-id="3fe93-187">4: **disabilitare AuditAllowed** **e AuditDenied** per questa voce.</span><span class="sxs-lookup"><span data-stu-id="3fe93-187">4: disable **AuditAllowed** and **AuditDenied** for this Entry.</span></span> <span data-ttu-id="3fe93-188">Anche se **block** si verifica e **l'impostazione AuditDenied** è configurata, il sistema non mostrerà la notifica.</span><span class="sxs-lookup"><span data-stu-id="3fe93-188">Even if **Block** happens and the **AuditDenied** is setting configured, the system will not show notification.</span></span>

   <span data-ttu-id="3fe93-189">Quando è **selezionato Il tipo AuditAllowed** **o AuditDenied:**</span><span class="sxs-lookup"><span data-stu-id="3fe93-189">When Type **AuditAllowed** or **AuditDenied** is selected:</span></span>

   - <span data-ttu-id="3fe93-190">0: nothing</span><span class="sxs-lookup"><span data-stu-id="3fe93-190">0: nothing</span></span>
   - <span data-ttu-id="3fe93-191">1: mostra notifica</span><span class="sxs-lookup"><span data-stu-id="3fe93-191">1: show notification</span></span>
   - <span data-ttu-id="3fe93-192">2: invia evento</span><span class="sxs-lookup"><span data-stu-id="3fe93-192">2: send event</span></span>
   - <span data-ttu-id="3fe93-193">3: mostra evento di notifica e invio</span><span class="sxs-lookup"><span data-stu-id="3fe93-193">3: show notification and send event</span></span>

<span data-ttu-id="3fe93-194">**Nome proprietà: AccessMask**</span><span class="sxs-lookup"><span data-stu-id="3fe93-194">**Property name: AccessMask**</span></span>

1. <span data-ttu-id="3fe93-195">Descrizione: definisce l'accesso.</span><span class="sxs-lookup"><span data-stu-id="3fe93-195">Description: Defines the access.</span></span>

1. <span data-ttu-id="3fe93-196">Opzioni: 1-7:</span><span class="sxs-lookup"><span data-stu-id="3fe93-196">Options: 1-7:</span></span>
    - <span data-ttu-id="3fe93-197">1: Lettura</span><span class="sxs-lookup"><span data-stu-id="3fe93-197">1: Read</span></span>
    - <span data-ttu-id="3fe93-198">2: Scrittura</span><span class="sxs-lookup"><span data-stu-id="3fe93-198">2: Write</span></span>
    - <span data-ttu-id="3fe93-199">3: Lettura e scrittura</span><span class="sxs-lookup"><span data-stu-id="3fe93-199">3: Read and Write</span></span>
    - <span data-ttu-id="3fe93-200">4: Eseguire</span><span class="sxs-lookup"><span data-stu-id="3fe93-200">4: Execute</span></span>
    - <span data-ttu-id="3fe93-201">5: Lettura ed esecuzione</span><span class="sxs-lookup"><span data-stu-id="3fe93-201">5: Read and Execute</span></span>
    - <span data-ttu-id="3fe93-202">6: Scrittura ed esecuzione</span><span class="sxs-lookup"><span data-stu-id="3fe93-202">6: Write and Execute</span></span>
    - <span data-ttu-id="3fe93-203">7: Lettura ed scrittura ed esecuzione</span><span class="sxs-lookup"><span data-stu-id="3fe93-203">7: Read and Write and Execute</span></span>

## <a name="common-removable-storage-access-control-scenarios"></a><span data-ttu-id="3fe93-204">Scenari comuni di controllo di Archiviazione rimovibili</span><span class="sxs-lookup"><span data-stu-id="3fe93-204">Common Removable Storage Access Control scenarios</span></span>

<span data-ttu-id="3fe93-205">Per acquisire familiarità con Microsoft Defender for Endpoint Removable Archiviazione Access Control, abbiamo creato alcuni scenari comuni da seguire.</span><span class="sxs-lookup"><span data-stu-id="3fe93-205">To help familiarize you with Microsoft Defender for Endpoint Removable Storage Access Control, we have put together some common scenarios for you to follow.</span></span>

### <a name="scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs"></a><span data-ttu-id="3fe93-206">Scenario 1: Impedire l'accesso in scrittura ed esecuzione a tutti gli USB approvati specifici, ma consentirne l'esecuzione</span><span class="sxs-lookup"><span data-stu-id="3fe93-206">Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs</span></span>

1. <span data-ttu-id="3fe93-207">Creare gruppi</span><span class="sxs-lookup"><span data-stu-id="3fe93-207">Create groups</span></span>
    1. <span data-ttu-id="3fe93-208">Gruppo 1: qualsiasi archivio rimovibile e CD/DVD.</span><span class="sxs-lookup"><span data-stu-id="3fe93-208">Group 1: Any removable storage and CD/DVD.</span></span> <span data-ttu-id="3fe93-209">Un esempio di archiviazione rimovibile e CD/DVD è il gruppo **9b28fae8-72f7-4267-a1a5-685f747a7146 nell'esempio** [Any Removable Archiviazione and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span><span class="sxs-lookup"><span data-stu-id="3fe93-209">An example of a removable storage and CD/DVD is: Group **9b28fae8-72f7-4267-a1a5-685f747a7146** in the sample [Any Removable Storage and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="3fe93-210">Gruppo 2: USB approvati in base alle proprietà del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3fe93-210">Group 2: Approved USBs based on device properties.</span></span> <span data-ttu-id="3fe93-211">Un esempio per questo caso di utilizzo è: ID istanza - Gruppo **65fa649a-a111-4912-9294-fb6337a25038** nel file di esempio [approved usbs Group.xml.](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)</span><span class="sxs-lookup"><span data-stu-id="3fe93-211">An example for this use case is: Instance ID – Group **65fa649a-a111-4912-9294-fb6337a25038** in the sample [Approved USBs Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3fe93-212">È necessario sostituire `&` con `&amp;` nel valore.</span><span class="sxs-lookup"><span data-stu-id="3fe93-212">You have to replace `&` with `&amp;` in the value.</span></span>

2. <span data-ttu-id="3fe93-213">Creazione di un criterio</span><span class="sxs-lookup"><span data-stu-id="3fe93-213">Create policy</span></span>
    1. <span data-ttu-id="3fe93-214">Criterio 1: bloccare l'accesso in scrittura ed esecuzione, ma consentire gli USB approvati.</span><span class="sxs-lookup"><span data-stu-id="3fe93-214">Policy 1: Block Write and Execute Access but allow approved USBs.</span></span> <span data-ttu-id="3fe93-215">Un esempio per questo caso d'uso è: PolicyRule **c544a991-5786-4402-949e-a032cb790d0e** nell'esempio [Scenario 1 Block Write and Execute Access but allow approved USBs .xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span><span class="sxs-lookup"><span data-stu-id="3fe93-215">An example for this use case is: PolicyRule **c544a991-5786-4402-949e-a032cb790d0e** in the sample [Scenario 1 Block Write and Execute Access but allow approved USBs .xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="3fe93-216">Criterio 2: controlla l'accesso in scrittura ed esecuzione agli USB consentiti.</span><span class="sxs-lookup"><span data-stu-id="3fe93-216">Policy 2: Audit Write and Execute access to allowed USBs.</span></span> <span data-ttu-id="3fe93-217">Un esempio per questo caso di utilizzo è: PolicyRule **36ae1037-a639-4cff-946b-b36c53089a4c** nell'esempio [Scenario 1 Audit Write and Execute access to approved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span><span class="sxs-lookup"><span data-stu-id="3fe93-217">An example for this use case is: PolicyRule **36ae1037-a639-4cff-946b-b36c53089a4c** in the sample [Scenario 1 Audit Write and Execute access to approved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

### <a name="scenario-2-audit-write-and-execute-access-to-all-but-block-specific-unapproved-usbs"></a><span data-ttu-id="3fe93-218">Scenario 2: controllare l'accesso in scrittura ed esecuzione a tutti gli USB non approvati specifici, ma bloccarlo</span><span class="sxs-lookup"><span data-stu-id="3fe93-218">Scenario 2: Audit Write and Execute access to all but block specific unapproved USBs</span></span>

1. <span data-ttu-id="3fe93-219">Creare gruppi</span><span class="sxs-lookup"><span data-stu-id="3fe93-219">Create groups</span></span>
    1. <span data-ttu-id="3fe93-220">Gruppo 1: qualsiasi archivio rimovibile e CD/DVD.</span><span class="sxs-lookup"><span data-stu-id="3fe93-220">Group 1: Any removable storage and CD/DVD.</span></span> <span data-ttu-id="3fe93-221">Un esempio di questo caso di utilizzo è il gruppo **9b28fae8-72f7-4267-a1a5-685f747a7146 nell'esempio** [Any Removable Archiviazione and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span><span class="sxs-lookup"><span data-stu-id="3fe93-221">An example for this use case is: Group **9b28fae8-72f7-4267-a1a5-685f747a7146** in the sample [Any Removable Storage and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="3fe93-222">Gruppo 2: USB non approvati in base alle proprietà del dispositivo, ad esempio ID fornitore/ID prodotto, Nome descrittivo - Gruppo **65fa649a-a111-4912-9294-fb6337a25038** nel file di esempio [USBs non approvate Group.xml.](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)</span><span class="sxs-lookup"><span data-stu-id="3fe93-222">Group 2: Unapproved USBs based on device properties, for example, Vendor ID / Product ID, Friendly Name – Group **65fa649a-a111-4912-9294-fb6337a25038** in the sample [Unapproved USBs Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="3fe93-223">È necessario sostituire `&` con `&amp;` nel valore.</span><span class="sxs-lookup"><span data-stu-id="3fe93-223">You have to replace `&` with `&amp;` in the value.</span></span>

2. <span data-ttu-id="3fe93-224">Creazione di un criterio</span><span class="sxs-lookup"><span data-stu-id="3fe93-224">Create policy</span></span>
    1. <span data-ttu-id="3fe93-225">Criterio 1: Bloccare l'accesso in scrittura ed esecuzione a tutti gli USB non approvati specifici.</span><span class="sxs-lookup"><span data-stu-id="3fe93-225">Policy 1: Block Write and Execute access to all but block specific unapproved USBs.</span></span> <span data-ttu-id="3fe93-226">Un esempio di questo caso di utilizzo è: PolicyRule **23b8e437-66ac-4b32-b3d7-24044637fc98 nell'esempio** [Scenario 2 Audit Write and Execute access to all but block specific unapproved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span><span class="sxs-lookup"><span data-stu-id="3fe93-226">An example of this use case is: PolicyRule **23b8e437-66ac-4b32-b3d7-24044637fc98** in the sample [Scenario 2 Audit Write and Execute access to all but block specific unapproved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="3fe93-227">Criterio 2: controllare l'accesso in scrittura ed esecuzione ad altri utenti.</span><span class="sxs-lookup"><span data-stu-id="3fe93-227">Policy 2: Audit Write and Execute access to others.</span></span> <span data-ttu-id="3fe93-228">Un esempio di questo caso di utilizzo è: PolicyRule **b58ab853-9a6f-405c-a194-740e69422b48 nell'esempio** [Scenario 2 Audit Write and Execute access to others.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span><span class="sxs-lookup"><span data-stu-id="3fe93-228">An example of this use case is: PolicyRule **b58ab853-9a6f-405c-a194-740e69422b48** in the sample [Scenario 2 Audit Write and Execute access to others.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

## <a name="deploying-and-managing-policy-via-group-policy"></a><span data-ttu-id="3fe93-229">Distribuzione e gestione dei criteri tramite Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="3fe93-229">Deploying and managing policy via Group Policy</span></span>

<span data-ttu-id="3fe93-230">La funzionalità Controllo di Archiviazione rimovibili consente di applicare i criteri tramite Criteri di gruppo a un utente o a un dispositivo o a entrambi.</span><span class="sxs-lookup"><span data-stu-id="3fe93-230">The Removable Storage Access Control feature enables you to apply policy via Group Policy to either user or device, or both.</span></span>

### <a name="licensing"></a><span data-ttu-id="3fe93-231">Licenze</span><span class="sxs-lookup"><span data-stu-id="3fe93-231">Licensing</span></span>

<span data-ttu-id="3fe93-232">Prima di iniziare a utilizzare Removable Archiviazione Access Control, è necessario confermare [l'Microsoft 365 abbonamento.](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2)</span><span class="sxs-lookup"><span data-stu-id="3fe93-232">Before you get started with Removable Storage Access Control, you must confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2).</span></span> <span data-ttu-id="3fe93-233">Per accedere a Removable Archiviazione Access Control, è necessario disporre di Microsoft 365 E3 o Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="3fe93-233">To access and use Removable Storage Access Control, you must have Microsoft 365 E3 or Microsoft 365 E5.</span></span>

### <a name="deploying-policy-via-group-policy"></a><span data-ttu-id="3fe93-234">Distribuzione dei criteri tramite Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="3fe93-234">Deploying policy via Group Policy</span></span>

1. <span data-ttu-id="3fe93-235">Combina tutti i gruppi `<Groups>` `</Groups>` all'interno di un unico file XML.</span><span class="sxs-lookup"><span data-stu-id="3fe93-235">Combine all groups within `<Groups>` `</Groups>` into one xml file.</span></span> 

    <span data-ttu-id="3fe93-236">Nell'immagine seguente viene illustrato l'esempio dello [scenario 1: Impedire](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)l'accesso in scrittura ed esecuzione a tutti gli USB approvati specifici.</span><span class="sxs-lookup"><span data-stu-id="3fe93-236">The following image illustrates the example of [Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs).</span></span>
    
    :::image type="content" source="images/prevent-write-access-allow-usb.png" alt-text="Schermata che mostra le impostazioni di configurazione che consentono specifici USB approvati nei dispositivi":::
    
2. <span data-ttu-id="3fe93-238">Combina tutte le regole `<PolicyRules>` `</PolicyRules>` all'interno di un unico file XML.</span><span class="sxs-lookup"><span data-stu-id="3fe93-238">Combine all rules within `<PolicyRules>` `</PolicyRules>` into one xml file.</span></span> 

    <span data-ttu-id="3fe93-239">Se si desidera limitare un utente specifico, utilizzare la proprietà SID nell'oggetto Entry.</span><span class="sxs-lookup"><span data-stu-id="3fe93-239">If you want to restrict a specific user, then use SID property into the Entry.</span></span> <span data-ttu-id="3fe93-240">Se non è presente alcun SID nella voce del criterio, la voce verrà applicata a tutti gli utenti dell'istanza di accesso per il computer.</span><span class="sxs-lookup"><span data-stu-id="3fe93-240">If there is no SID in the policy Entry, the Entry will be applied to everyone login instance for the machine.</span></span>
    
    <span data-ttu-id="3fe93-241">Nell'immagine seguente viene illustrato l'utilizzo della proprietà SID e un esempio dello [scenario 1:](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)Impedire l'accesso in scrittura ed esecuzione a tutti gli USB approvati specifici.</span><span class="sxs-lookup"><span data-stu-id="3fe93-241">The following image illustrates the usage of SID property, and an example of [Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs).</span></span>
    
    :::image type="content" source="images/usage-sid-property.png" alt-text="Schermata che visualizza un codice che indica l'utilizzo dell'attributo della proprietà SID":::

3. <span data-ttu-id="3fe93-243">Salvare sia i file XML delle regole che dei gruppi nella cartella della condivisione di rete e inserire il percorso della cartella della condivisione di rete nell'impostazione di Criteri di gruppo: Configurazione computer -> Modelli amministrativi **-> Windows Componenti -> Antivirus Microsoft Defender -> Controllo dispositivi: "Definire** i gruppi di criteri di controllo dei dispositivi" e "Definire le regole dei criteri di controllo dei dispositivi".</span><span class="sxs-lookup"><span data-stu-id="3fe93-243">Save both rule and group XML files on network share folder and put network share folder path into the Group Policy setting: **Computer Configuration -> Administrative Templates -> Windows Components -> Microsoft Defender Antivirus -> Device Control: ‘Define device control policy groups’ and ‘Define device control policy rules’**.</span></span>

    - <span data-ttu-id="3fe93-244">Il computer di destinazione deve essere in grado di accedere alla condivisione di rete per disporre del criterio.</span><span class="sxs-lookup"><span data-stu-id="3fe93-244">The target machine must be able to access the network share to have the policy.</span></span> <span data-ttu-id="3fe93-245">Tuttavia, una volta letto il criterio, la connessione di condivisione di rete non è più necessaria, anche dopo il riavvio del computer.</span><span class="sxs-lookup"><span data-stu-id="3fe93-245">However, once the policy is read, the network share connection is no longer required, even after machine reboot.</span></span>

    :::image type="content" source="images/device-control.png" alt-text="Schermata Controllo dispositivo":::

## <a name="deploying-and-managing-policy-via-intune-oma-uri"></a><span data-ttu-id="3fe93-247">Distribuzione e gestione dei criteri tramite URI OMA di Intune</span><span class="sxs-lookup"><span data-stu-id="3fe93-247">Deploying and managing policy via Intune OMA-URI</span></span>

<span data-ttu-id="3fe93-248">La funzionalità Controllo di Archiviazione rimovibili consente di applicare i criteri tramite URI OMA a un utente o a un dispositivo o a entrambi.</span><span class="sxs-lookup"><span data-stu-id="3fe93-248">The Removable Storage Access Control feature enables you to apply policy via OMA-URI to either user or device, or both.</span></span>

### <a name="licensing"></a><span data-ttu-id="3fe93-249">Licenze</span><span class="sxs-lookup"><span data-stu-id="3fe93-249">Licensing</span></span>

<span data-ttu-id="3fe93-250">Prima di iniziare a utilizzare Removable Archiviazione Access Control, è necessario confermare [l'Microsoft 365 abbonamento.](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2)</span><span class="sxs-lookup"><span data-stu-id="3fe93-250">Before you get started with Removable Storage Access Control, you  must confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2).</span></span> <span data-ttu-id="3fe93-251">Per accedere a Removable Archiviazione Access Control, è necessario disporre di Microsoft 365 E3 o Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="3fe93-251">To access and use Removable Storage Access Control, you must have Microsoft 365 E3 or Microsoft 365 E5.</span></span>

### <a name="permission"></a><span data-ttu-id="3fe93-252">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="3fe93-252">Permission</span></span>

<span data-ttu-id="3fe93-253">Per la distribuzione dei criteri in Intune, l'account deve disporre delle autorizzazioni per creare, modificare, aggiornare o eliminare i profili di configurazione dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="3fe93-253">For policy deployment in Intune, the account must have permissions to create, edit, update, or delete device configuration profiles.</span></span> <span data-ttu-id="3fe93-254">È possibile creare ruoli personalizzati o utilizzare uno qualsiasi dei ruoli predefiniti con queste autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="3fe93-254">You can create custom roles or use any of the built-in roles with these permissions.</span></span>

- <span data-ttu-id="3fe93-255">Ruolo Gestione criteri e profili</span><span class="sxs-lookup"><span data-stu-id="3fe93-255">Policy and profile Manager role</span></span>
- <span data-ttu-id="3fe93-256">Ruolo personalizzato con autorizzazioni Create/Edit/Update/Read/Delete/View Reports attivate per i profili di configurazione dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="3fe93-256">Custom role with Create/Edit/Update/Read/Delete/View Reports permissions turned on for Device Configuration profiles</span></span>
- <span data-ttu-id="3fe93-257">Amministratore globale</span><span class="sxs-lookup"><span data-stu-id="3fe93-257">Global administrator</span></span>

### <a name="deploying-policy-via-oma-uri"></a><span data-ttu-id="3fe93-258">Distribuzione dei criteri tramite URI OMA</span><span class="sxs-lookup"><span data-stu-id="3fe93-258">Deploying policy via OMA-URI</span></span>

<span data-ttu-id="3fe93-259">**Microsoft Endpoint Manager di amministrazione ( https://endpoint.microsoft.com/) -> Devices -> Configuration profiles -> Create profile -> Platform: Windows 10 and later & Profile: Custom**</span><span class="sxs-lookup"><span data-stu-id="3fe93-259">**Microsoft Endpoint Manager admin center (https://endpoint.microsoft.com/) -> Devices -> Configuration profiles -> Create profile -> Platform: Windows 10 and later & Profile: Custom**</span></span>

1. <span data-ttu-id="3fe93-260">Per ogni gruppo, crea una regola URI OMA:</span><span class="sxs-lookup"><span data-stu-id="3fe93-260">For each Group, create an OMA-URI rule:</span></span>
    - <span data-ttu-id="3fe93-261">OMA-URI: </span><span class="sxs-lookup"><span data-stu-id="3fe93-261">OMA-URI:</span></span>

      <span data-ttu-id="3fe93-262">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b **GroupGUID**%7d/GroupData</span><span class="sxs-lookup"><span data-stu-id="3fe93-262">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b **GroupGUID**%7d/GroupData</span></span>

      <span data-ttu-id="3fe93-263">Ad esempio, per qualsiasi gruppo di archiviazione rimovibile e **CD/DVD** nell'esempio, il collegamento deve essere:</span><span class="sxs-lookup"><span data-stu-id="3fe93-263">For example, for **any removable storage and CD/DVD** group in the sample, the link must be:</span></span>

      <span data-ttu-id="3fe93-264">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b9b28fae8-72f7-4267-a1a5-685f747a7146%7d/GroupData</span><span class="sxs-lookup"><span data-stu-id="3fe93-264">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b9b28fae8-72f7-4267-a1a5-685f747a7146%7d/GroupData</span></span>

    - <span data-ttu-id="3fe93-265">Tipo di dati: String (file XML)</span><span class="sxs-lookup"><span data-stu-id="3fe93-265">Data Type: String (XML file)</span></span>
    
      :::image type="content" source="images/xml-data-type-string.png" alt-text="File XML per il tipo di dati STRING":::

2. <span data-ttu-id="3fe93-267">Per ogni criterio, crea anche un URI OMA:</span><span class="sxs-lookup"><span data-stu-id="3fe93-267">For each policy, also create an OMA-URI:</span></span>

    - <span data-ttu-id="3fe93-268">OMA-URI: </span><span class="sxs-lookup"><span data-stu-id="3fe93-268">OMA-URI:</span></span>

      <span data-ttu-id="3fe93-269">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bFA6BE102-0784-4A2A-B010-A0BEBEBF68E1%7d/RuleData</span><span class="sxs-lookup"><span data-stu-id="3fe93-269">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bFA6BE102-0784-4A2A-B010-A0BEBEBF68E1%7d/RuleData</span></span>

      <span data-ttu-id="3fe93-270">Ad esempio, per la regola Blocca scrittura ed esecuzione accesso ma consenti le **usbs** approvate nell'esempio, il collegamento deve essere:</span><span class="sxs-lookup"><span data-stu-id="3fe93-270">For example, for the **Block Write and Execute Access but allow approved USBs** rule in the sample, the link must be:</span></span> 

      <span data-ttu-id="3fe93-271">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bc544a991-5786-4402-949e-a032cb790d0e%7d/RuleData.</span><span class="sxs-lookup"><span data-stu-id="3fe93-271">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bc544a991-5786-4402-949e-a032cb790d0e%7d/RuleData.</span></span>

    - <span data-ttu-id="3fe93-272">Tipo di dati: String (file XML)</span><span class="sxs-lookup"><span data-stu-id="3fe93-272">Data Type: String (XML file)</span></span>

      :::image type="content" source="images/xml-data-type-string-2.png" lightbox="images/xml-data-type-string-2.png" alt-text="Visualizzazione del file XML per il tipo di dati STRING":::

## <a name="deploying-and-managing-policy-by-using-intune-user-interface"></a><span data-ttu-id="3fe93-274">Distribuzione e gestione dei criteri tramite l'interfaccia utente di Intune</span><span class="sxs-lookup"><span data-stu-id="3fe93-274">Deploying and managing policy by using Intune user interface</span></span>

<span data-ttu-id="3fe93-275">Questa funzionalità (nell'interfaccia di amministrazione di Microsoft Endpoint Manager ( > https://endpoint.microsoft.com/) Devices > Configuration profiles > Create profile > Platform: Windows 10 and later & Profile: Device Control) non è ancora disponibile.</span><span class="sxs-lookup"><span data-stu-id="3fe93-275">This capability (in Microsoft Endpoint Manager admin center (https://endpoint.microsoft.com/) > Devices > Configuration profiles > Create profile > Platform: Windows 10 and later & Profile: Device Control) is not yet available.</span></span> 

## <a name="view-device-control-removable-storage-access-control-data-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="3fe93-276">Visualizzare i dati di controllo Archiviazione di accesso rimovibili in Microsoft Defender per Endpoint</span><span class="sxs-lookup"><span data-stu-id="3fe93-276">View Device Control Removable Storage Access Control data in Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="3fe93-277">Il portale Microsoft 365 sicurezza mostra l'archiviazione rimovibile bloccata dal Controllo dispositivo Rimovibile Archiviazione Access Control.</span><span class="sxs-lookup"><span data-stu-id="3fe93-277">The Microsoft 365 security portal shows removable storage blocked by the Device Control Removable Storage Access Control.</span></span> <span data-ttu-id="3fe93-278">Per accedere alla Microsoft 365 sicurezza, è necessario disporre dell'abbonamento seguente:</span><span class="sxs-lookup"><span data-stu-id="3fe93-278">To access the Microsoft 365 security, you must have the following subscription:</span></span>

- <span data-ttu-id="3fe93-279">Microsoft 365 per la creazione di report E5</span><span class="sxs-lookup"><span data-stu-id="3fe93-279">Microsoft 365 for E5 reporting</span></span>

```kusto
//events triggered by RemovableStoragePolicyTriggered
DeviceEvents
| where ActionType == &quot;RemovableStoragePolicyTriggered&quot; 
| extend parsed=parse_json(AdditionalFields) 
| extend RemovableStorageAccess = tostring(parsed.RemovableStorageAccess)  
| extend RemovableStoragePolicyVerdict = tostring(parsed.RemovableStoragePolicyVerdict)  
| extend MediaBusType = tostring(parsed.BusType)  
| extend MediaClassGuid = tostring(parsed.ClassGuid)
| extend MediaClassName = tostring(parsed.ClassName)
| extend MediaDeviceId = tostring(parsed.DeviceId) 
| extend MediaInstanceId = tostring(parsed.DeviceInstanceId) 
| extend MediaName = tostring(parsed.MediaName) 
| extend RemovableStoragePolicy = tostring(parsed.RemovableStoragePolicy)  
| extend MediaProductId = tostring(parsed.ProductId)  
| extend MediaVendorId = tostring(parsed.VendorId)  
| extend MediaSerialNumber = tostring(parsed.SerialNumber)  
| extend MediaVolume = tostring(parsed.Volume)  
| project Timestamp, DeviceId, DeviceName, ActionType, RemovableStorageAccess, RemovableStoragePolicyVerdict, MediaBusType, MediaClassGuid, MediaClassName, MediaDeviceId, MediaInstanceId, MediaName, RemovableStoragePolicy, MediaProductId, MediaVendorId, MediaSerialNumber, MediaVolume 
| order by Timestamp desc
```

:::image type="content" source="images/block-removable-storage.png" alt-text="Schermata che illustra il blocco dell'archiviazione rimovibile":::
