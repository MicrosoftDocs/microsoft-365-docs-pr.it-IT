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
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 0b0f7c5a4a75fdc80509dbc02a43d28f7c93fd7c
ms.sourcegitcommit: 53aebd492a4b998805c70c8e06a2cfa5d453905c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2021
ms.locfileid: "53327048"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-access-control"></a><span data-ttu-id="74d35-104">Microsoft Defender for Endpoint Device Control Removable Archiviazione Access Control</span><span class="sxs-lookup"><span data-stu-id="74d35-104">Microsoft Defender for Endpoint Device Control Removable Storage Access Control</span></span>

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="74d35-105">Microsoft Defender for Endpoint Device Control Removable Archiviazione Access Control consente di eseguire l'attività seguente:</span><span class="sxs-lookup"><span data-stu-id="74d35-105">Microsoft Defender for Endpoint Device Control Removable Storage Access Control enables you to do the following task:</span></span>

- <span data-ttu-id="74d35-106">controllo, consentendo o impedendo l'accesso in lettura, scrittura o esecuzione all'archiviazione rimovibile con o senza esclusione</span><span class="sxs-lookup"><span data-stu-id="74d35-106">auditing, allowing or preventing the read, write or execute access to removable storage with or without exclusion</span></span>

|<span data-ttu-id="74d35-107">Privilegio</span><span class="sxs-lookup"><span data-stu-id="74d35-107">Privilege</span></span> |<span data-ttu-id="74d35-108">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="74d35-108">Permission</span></span>  |
|---------|---------|
|<span data-ttu-id="74d35-109">Access</span><span class="sxs-lookup"><span data-stu-id="74d35-109">Access</span></span>    |  <span data-ttu-id="74d35-110">Lettura, scrittura ed esecuzione</span><span class="sxs-lookup"><span data-stu-id="74d35-110">Read, Write, Execute</span></span>       |
|<span data-ttu-id="74d35-111">Modalità azione</span><span class="sxs-lookup"><span data-stu-id="74d35-111">Action Mode</span></span>    |    <span data-ttu-id="74d35-112">Controllo, Consenti, Impedisci</span><span class="sxs-lookup"><span data-stu-id="74d35-112">Audit, Allow, Prevent</span></span>     |
|<span data-ttu-id="74d35-113">Supporto CSP</span><span class="sxs-lookup"><span data-stu-id="74d35-113">CSP Support</span></span>   |   <span data-ttu-id="74d35-114">Sì</span><span class="sxs-lookup"><span data-stu-id="74d35-114">Yes</span></span>      |
|<span data-ttu-id="74d35-115">Supporto oggetti Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="74d35-115">GPO Support</span></span>    |   <span data-ttu-id="74d35-116">Sì</span><span class="sxs-lookup"><span data-stu-id="74d35-116">Yes</span></span>      |
|<span data-ttu-id="74d35-117">Supporto basato sull'utente</span><span class="sxs-lookup"><span data-stu-id="74d35-117">User-based Support</span></span>     |   <span data-ttu-id="74d35-118">Sì</span><span class="sxs-lookup"><span data-stu-id="74d35-118">Yes</span></span>      |
|<span data-ttu-id="74d35-119">Supporto basato su computer</span><span class="sxs-lookup"><span data-stu-id="74d35-119">Machine-based Support</span></span>    |    <span data-ttu-id="74d35-120">Sì</span><span class="sxs-lookup"><span data-stu-id="74d35-120">Yes</span></span>     |

## <a name="prepare-your-endpoints"></a><span data-ttu-id="74d35-121">Preparare gli endpoint</span><span class="sxs-lookup"><span data-stu-id="74d35-121">Prepare your endpoints</span></span>

<span data-ttu-id="74d35-122">Distribuire Il controllo di accesso Archiviazione rimovibili nei dispositivi Windows 10 con client antimalware **versione 4.18.2103.3 o successiva.**</span><span class="sxs-lookup"><span data-stu-id="74d35-122">Deploy Removable Storage Access Control on Windows 10 devices that have antimalware client version **4.18.2103.3 or later**.</span></span>

- <span data-ttu-id="74d35-123">**4.18.2104 o** versione successiva : Aggiungere SerialNumberId, VID_PID, supporto dell'oggetto Criteri di gruppo basato su filepath, ComputerSid</span><span class="sxs-lookup"><span data-stu-id="74d35-123">**4.18.2104 or later**: Add SerialNumberId, VID_PID, filepath-based GPO support, ComputerSid</span></span>

- <span data-ttu-id="74d35-124">**4.18.2105 o** versione successiva : Aggiungere il supporto dei caratteri jolly per HardwareId/DeviceId/InstancePathId/FriendlyNameId/SerialNumberId, la combinazione di un utente specifico in un computer specifico, SSD rimovibile (un SSD SanDisk Extreme)/supporto USB Attached SCSI (UAS)</span><span class="sxs-lookup"><span data-stu-id="74d35-124">**4.18.2105 or later**: Add Wildcard support for HardwareId/DeviceId/InstancePathId/FriendlyNameId/SerialNumberId, the combination of specific user on specific machine, removeable SSD (a SanDisk Extreme SSD)/USB Attached SCSI (UAS) support</span></span>

- <span data-ttu-id="74d35-125">**4.18.2107** o versione successiva : Aggiungere il supporto di Windows Portable Device (WPD) (per dispositivi mobili, ad esempio tablet)</span><span class="sxs-lookup"><span data-stu-id="74d35-125">**4.18.2107 or later**: Add Windows Portable Device (WPD) support (for mobile devices, such as tablets)</span></span>

:::image type="content" source="images/powershell.png" alt-text="Interfaccia di PowerShell":::

> [!NOTE]
> <span data-ttu-id="74d35-127">Nessuno dei Sicurezza di Windows deve essere attivo, è possibile eseguire Removable Archiviazione Access Control indipendentemente Sicurezza di Windows stato.</span><span class="sxs-lookup"><span data-stu-id="74d35-127">None of Windows Security components need to be active, you can run Removable Storage Access Control independent of Windows Security status.</span></span>

## <a name="policy-properties"></a><span data-ttu-id="74d35-128">Proprietà dei criteri</span><span class="sxs-lookup"><span data-stu-id="74d35-128">Policy properties</span></span>

<span data-ttu-id="74d35-129">È possibile utilizzare le proprietà seguenti per creare un gruppo di archiviazione rimovibile:</span><span class="sxs-lookup"><span data-stu-id="74d35-129">You can use the following properties to create a removable storage group:</span></span>

<span data-ttu-id="74d35-130">**Nome proprietà: ID gruppo**</span><span class="sxs-lookup"><span data-stu-id="74d35-130">**Property name: Group Id**</span></span>

1. <span data-ttu-id="74d35-131">Descrizione: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), un ID univoco, rappresenta il gruppo e verrà utilizzato nel criterio.</span><span class="sxs-lookup"><span data-stu-id="74d35-131">Description: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), a unique ID, represents the group and will be used in the policy.</span></span>

<span data-ttu-id="74d35-132">**Nome proprietà: DescriptorIdList**</span><span class="sxs-lookup"><span data-stu-id="74d35-132">**Property name: DescriptorIdList**</span></span>

2. <span data-ttu-id="74d35-133">Descrizione: elenca le proprietà del dispositivo che vuoi usare per coprire il gruppo.</span><span class="sxs-lookup"><span data-stu-id="74d35-133">Description: List the device properties you want to use to cover in the group.</span></span>
<span data-ttu-id="74d35-134">Per ogni proprietà del dispositivo, vedi **la sezione Proprietà dispositivo** sopra riportata per ulteriori dettagli.</span><span class="sxs-lookup"><span data-stu-id="74d35-134">For each device property, see **Device Properties** section above for more detail.</span></span>

3. <span data-ttu-id="74d35-135">Opzioni:</span><span class="sxs-lookup"><span data-stu-id="74d35-135">Options:</span></span>
    - <span data-ttu-id="74d35-136">PrimaryId</span><span class="sxs-lookup"><span data-stu-id="74d35-136">PrimaryId</span></span>
        - <span data-ttu-id="74d35-137">RemovableMediaDevices</span><span class="sxs-lookup"><span data-stu-id="74d35-137">RemovableMediaDevices</span></span>
        - <span data-ttu-id="74d35-138">CdRomDevices</span><span class="sxs-lookup"><span data-stu-id="74d35-138">CdRomDevices</span></span>
        - <span data-ttu-id="74d35-139">WpdDevices</span><span class="sxs-lookup"><span data-stu-id="74d35-139">WpdDevices</span></span>
    - <span data-ttu-id="74d35-140">DeviceId</span><span class="sxs-lookup"><span data-stu-id="74d35-140">DeviceId</span></span>
    - <span data-ttu-id="74d35-141">HardwareId</span><span class="sxs-lookup"><span data-stu-id="74d35-141">HardwareId</span></span>
    - <span data-ttu-id="74d35-142">InstancePathId: InstancePathId è una stringa che identifica in modo univoco il dispositivo nel sistema, ad esempio USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0.</span><span class="sxs-lookup"><span data-stu-id="74d35-142">InstancePathId: InstancePathId is a string that uniquely identifies the device in the system, for example, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0.</span></span> <span data-ttu-id="74d35-143">Il numero alla fine (ad esempio **&0)** rappresenta lo slot disponibile e può cambiare da dispositivo a dispositivo.</span><span class="sxs-lookup"><span data-stu-id="74d35-143">The number at the end (for example **&0**) represents the available slot and may change from device to device.</span></span> <span data-ttu-id="74d35-144">Per ottenere risultati ottimali, utilizzare un carattere jolly alla fine.</span><span class="sxs-lookup"><span data-stu-id="74d35-144">For best results, use a wildcard at the end.</span></span> <span data-ttu-id="74d35-145">Ad esempio, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611\*</span><span class="sxs-lookup"><span data-stu-id="74d35-145">For example, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611\*</span></span>
    - <span data-ttu-id="74d35-146">FriendlyNameId</span><span class="sxs-lookup"><span data-stu-id="74d35-146">FriendlyNameId</span></span>
    - <span data-ttu-id="74d35-147">SerialNumberId</span><span class="sxs-lookup"><span data-stu-id="74d35-147">SerialNumberId</span></span>
    - <span data-ttu-id="74d35-148">VID</span><span class="sxs-lookup"><span data-stu-id="74d35-148">VID</span></span>
    - <span data-ttu-id="74d35-149">PID</span><span class="sxs-lookup"><span data-stu-id="74d35-149">PID</span></span>
    - <span data-ttu-id="74d35-150">VID_PID</span><span class="sxs-lookup"><span data-stu-id="74d35-150">VID_PID</span></span>
        - <span data-ttu-id="74d35-151">0751_55E0: corrisponde a questa coppia VID/PID esatta</span><span class="sxs-lookup"><span data-stu-id="74d35-151">0751_55E0: match this exact VID/PID pair</span></span>
        - <span data-ttu-id="74d35-152">_55E0: corrisponde a qualsiasi supporto con PID=55E0</span><span class="sxs-lookup"><span data-stu-id="74d35-152">_55E0: match any media with PID=55E0</span></span>
        - <span data-ttu-id="74d35-153">0751_: corrisponde a qualsiasi supporto con VID=0751</span><span class="sxs-lookup"><span data-stu-id="74d35-153">0751_: match any media with VID=0751</span></span>
        
<span data-ttu-id="74d35-154">**Nome proprietà: MatchType**</span><span class="sxs-lookup"><span data-stu-id="74d35-154">**Property name: MatchType**</span></span> 

1. <span data-ttu-id="74d35-155">Descrizione: quando in DescriptorIDList vengono utilizzate più proprietà del dispositivo, MatchType definisce la relazione.</span><span class="sxs-lookup"><span data-stu-id="74d35-155">Description: When there are multiple device properties being used in the DescriptorIDList, MatchType defines the relationship.</span></span>

2. <span data-ttu-id="74d35-156">Opzioni:</span><span class="sxs-lookup"><span data-stu-id="74d35-156">Options:</span></span>

    - <span data-ttu-id="74d35-157">MatchAll: tutti gli attributi in DescriptorIdList saranno **relazione And.** Ad esempio, se l'amministratore inserisce DeviceID e InstancePathID per ogni USB connesso, il sistema controllera' se l'USB soddisfa entrambi i valori.</span><span class="sxs-lookup"><span data-stu-id="74d35-157">MatchAll: Any attributes under the DescriptorIdList will be **And** relationship; for example, if administrator puts DeviceID and InstancePathID, for every connected USB, system will check to see whether the USB meets both values.</span></span>
    - <span data-ttu-id="74d35-158">MatchAny: gli attributi sotto DescriptorIdList saranno **relazione Or.** Ad esempio, se l'amministratore inserisce DeviceID e InstancePathID, per ogni USB connessa, il sistema farà l'imposizione purché l'USB abbia un **valore DeviceID** o **InstanceID** identico.</span><span class="sxs-lookup"><span data-stu-id="74d35-158">MatchAny: The attributes under the DescriptorIdList will be **Or** relationship; for example, if administrator puts DeviceID and InstancePathID, for every connected USB, system will do the enforcement as long as the USB has either an identical **DeviceID** or **InstanceID** value.</span></span>

<span data-ttu-id="74d35-159">Di seguito sono riportate le proprietà dei criteri di controllo di accesso:</span><span class="sxs-lookup"><span data-stu-id="74d35-159">Following are the access control policy properties:</span></span>

<span data-ttu-id="74d35-160">**Nome proprietà: PolicyRuleId**</span><span class="sxs-lookup"><span data-stu-id="74d35-160">**Property name: PolicyRuleId**</span></span>

1. <span data-ttu-id="74d35-161">Descrizione: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), un ID univoco, rappresenta il criterio e verrà utilizzato nei report e nella risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="74d35-161">Description: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), a unique ID, represents the policy and will be used in the reporting and troubleshooting.</span></span>

<span data-ttu-id="74d35-162">**Nome proprietà: IncludedIdList**</span><span class="sxs-lookup"><span data-stu-id="74d35-162">**Property name: IncludedIdList**</span></span>

1. <span data-ttu-id="74d35-163">Descrizione: i gruppi a cui verrà applicato il criterio.</span><span class="sxs-lookup"><span data-stu-id="74d35-163">Description: The group(s) that the policy will be applied to.</span></span> <span data-ttu-id="74d35-164">Se vengono aggiunti più gruppi, il criterio verrà applicato a tutti i supporti di tutti i gruppi.</span><span class="sxs-lookup"><span data-stu-id="74d35-164">If multiple groups are added, the policy will be applied to any media in all those groups.</span></span>

2. <span data-ttu-id="74d35-165">Opzioni: l'ID gruppo/GUID deve essere utilizzato in questa istanza.</span><span class="sxs-lookup"><span data-stu-id="74d35-165">Options: The Group ID/GUID must be used at this instance.</span></span>

<span data-ttu-id="74d35-166">Nell'esempio seguente viene illustrato l'utilizzo di GroupID:</span><span class="sxs-lookup"><span data-stu-id="74d35-166">The following example shows the usage of GroupID:</span></span>

`<IncludedIdList> <GroupId>{EAA4CCE5-F6C9-4760-8BAD-FDCC76A2ACA1}</GroupId> </IncludedIdList>`

<span data-ttu-id="74d35-167">**Nome proprietà: ExcludedIDList**</span><span class="sxs-lookup"><span data-stu-id="74d35-167">**Property name: ExcludedIDList**</span></span>

<span data-ttu-id="74d35-168">Descrizione: i gruppi a cui non verrà applicato il criterio.</span><span class="sxs-lookup"><span data-stu-id="74d35-168">Description: The group(s) that the policy will not be applied to.</span></span>

<span data-ttu-id="74d35-169">Opzioni: l'ID gruppo/GUID deve essere utilizzato in questa istanza.</span><span class="sxs-lookup"><span data-stu-id="74d35-169">Options: The Group ID/GUID must be used at this instance.</span></span>

<span data-ttu-id="74d35-170">**Nome proprietà: Id voce**</span><span class="sxs-lookup"><span data-stu-id="74d35-170">**Property name: Entry Id**</span></span>

1. <span data-ttu-id="74d35-171">Descrizione: Un oggetto PolicyRule può avere più voci. ogni voce con un GUID univoco indica a Device Control una restrizione.</span><span class="sxs-lookup"><span data-stu-id="74d35-171">Description: One PolicyRule can have multiple entries; each entry with a unique GUID tells Device Control one restriction.</span></span>

<span data-ttu-id="74d35-172">**Nome proprietà: Type**</span><span class="sxs-lookup"><span data-stu-id="74d35-172">**Property name: Type**</span></span>

1. <span data-ttu-id="74d35-173">Descrizione: definisce l'azione per i gruppi di archiviazione rimovibili in IncludedIDList.</span><span class="sxs-lookup"><span data-stu-id="74d35-173">Description: Defines the action for the removable storage groups in IncludedIDList.</span></span>
    - <span data-ttu-id="74d35-174">Imposizione: Consenti o Nega</span><span class="sxs-lookup"><span data-stu-id="74d35-174">Enforcement: Allow or Deny</span></span>
    - <span data-ttu-id="74d35-175">Controllo: AuditAllowed o AuditDenied</span><span class="sxs-lookup"><span data-stu-id="74d35-175">Audit: AuditAllowed or AuditDenied</span></span> 

2. <span data-ttu-id="74d35-176">Opzioni:</span><span class="sxs-lookup"><span data-stu-id="74d35-176">Options:</span></span>

    - <span data-ttu-id="74d35-177">Consenti</span><span class="sxs-lookup"><span data-stu-id="74d35-177">Allow</span></span>
    - <span data-ttu-id="74d35-178">Nega</span><span class="sxs-lookup"><span data-stu-id="74d35-178">Deny</span></span>
    - <span data-ttu-id="74d35-179">AuditAllowed: definisce la notifica e l'evento quando è consentito l'accesso</span><span class="sxs-lookup"><span data-stu-id="74d35-179">AuditAllowed: Defines notification and event when access is allowed</span></span>
    - <span data-ttu-id="74d35-180">AuditDenied: definisce la notifica e l'evento quando l'accesso viene negato. deve collaborare con **la voce** Deny.</span><span class="sxs-lookup"><span data-stu-id="74d35-180">AuditDenied: Defines notification and event when access is denied; has to work together with **Deny** entry.</span></span>

<span data-ttu-id="74d35-181">Quando sono presenti tipi di conflitto per lo stesso supporto, il sistema applierà il primo nel criterio.</span><span class="sxs-lookup"><span data-stu-id="74d35-181">When there are conflict types for the same media, the system will apply the first one in the policy.</span></span> <span data-ttu-id="74d35-182">Un esempio di tipo di conflitto è **Allow** e **Deny.**</span><span class="sxs-lookup"><span data-stu-id="74d35-182">An example of a conflict type is **Allow** and **Deny**.</span></span>

<span data-ttu-id="74d35-183">**Nome proprietà: Sid**</span><span class="sxs-lookup"><span data-stu-id="74d35-183">**Property name: Sid**</span></span>

<span data-ttu-id="74d35-184">Descrizione: il Sid del computer locale o il Sid dell'oggetto AD, definisce se applicare questo criterio a un utente o a un gruppo di utenti specifico. una voce può avere un massimo di un Sid e una voce senza sid significa applicare il criterio sul computer.</span><span class="sxs-lookup"><span data-stu-id="74d35-184">Description: Local computer Sid or the Sid of the AD object, defines whether to apply this policy over a specific user or user group; one entry can have a maximum of one Sid and an entry without any Sid means applying the policy over the machine.</span></span>

<span data-ttu-id="74d35-185">**Nome proprietà: ComputerSid**</span><span class="sxs-lookup"><span data-stu-id="74d35-185">**Property name: ComputerSid**</span></span>

<span data-ttu-id="74d35-186">Descrizione: il Sid del computer locale o il Sid dell'oggetto AD, definisce se applicare questo criterio a un computer o a un gruppo di computer specifico; una voce può avere un massimo di un ComputerSid e una voce senza ComputerSid significa applicare il criterio sul computer.</span><span class="sxs-lookup"><span data-stu-id="74d35-186">Description: Local computer Sid or the Sid of the AD object, defines whether to apply this policy over a specific machine or machine group; one entry can have a maximum of one ComputerSid and an entry without any ComputerSid means applying the policy over the machine.</span></span> <span data-ttu-id="74d35-187">Se si desidera applicare una voce a un utente specifico e a un computer specifico, aggiungere sia Sid che ComputerSid nella stessa voce.</span><span class="sxs-lookup"><span data-stu-id="74d35-187">If you want to apply an Entry to a specific user and specific machine, add both Sid and ComputerSid into the same Entry.</span></span>

<span data-ttu-id="74d35-188">**Nome proprietà: Opzioni**</span><span class="sxs-lookup"><span data-stu-id="74d35-188">**Property name: Options**</span></span>

<span data-ttu-id="74d35-189">Descrizione: definisce se visualizzare o meno la notifica.</span><span class="sxs-lookup"><span data-stu-id="74d35-189">Description: Defines whether to display notification or not.</span></span>

   :::image type="content" source="images/device-status.png" alt-text="Schermata in cui è possibile visualizzare lo stato del dispositivo":::

<span data-ttu-id="74d35-191">Opzioni: 0-4.</span><span class="sxs-lookup"><span data-stu-id="74d35-191">Options: 0-4.</span></span> <span data-ttu-id="74d35-192">Quando è selezionata l'opzione Digitazione Consenti o Nega:</span><span class="sxs-lookup"><span data-stu-id="74d35-192">When Type Allow or Deny is selected:</span></span>

   - <span data-ttu-id="74d35-193">0: nothing</span><span class="sxs-lookup"><span data-stu-id="74d35-193">0: nothing</span></span>
   - <span data-ttu-id="74d35-194">4: **disabilitare AuditAllowed** **e AuditDenied** per questa voce.</span><span class="sxs-lookup"><span data-stu-id="74d35-194">4: disable **AuditAllowed** and **AuditDenied** for this Entry.</span></span> <span data-ttu-id="74d35-195">Anche se **block** si verifica e **l'impostazione AuditDenied** è configurata, il sistema non mostrerà la notifica.</span><span class="sxs-lookup"><span data-stu-id="74d35-195">Even if **Block** happens and the **AuditDenied** is setting configured, the system will not show notification.</span></span>

   <span data-ttu-id="74d35-196">Quando è **selezionato Il tipo AuditAllowed** **o AuditDenied:**</span><span class="sxs-lookup"><span data-stu-id="74d35-196">When Type **AuditAllowed** or **AuditDenied** is selected:</span></span>

   - <span data-ttu-id="74d35-197">0: nothing</span><span class="sxs-lookup"><span data-stu-id="74d35-197">0: nothing</span></span>
   - <span data-ttu-id="74d35-198">1: mostra notifica</span><span class="sxs-lookup"><span data-stu-id="74d35-198">1: show notification</span></span>
   - <span data-ttu-id="74d35-199">2: invia evento</span><span class="sxs-lookup"><span data-stu-id="74d35-199">2: send event</span></span>
   - <span data-ttu-id="74d35-200">3: mostra evento di notifica e invio</span><span class="sxs-lookup"><span data-stu-id="74d35-200">3: show notification and send event</span></span>

<span data-ttu-id="74d35-201">**Nome proprietà: AccessMask**</span><span class="sxs-lookup"><span data-stu-id="74d35-201">**Property name: AccessMask**</span></span>

<span data-ttu-id="74d35-202">Descrizione: definisce l'accesso.</span><span class="sxs-lookup"><span data-stu-id="74d35-202">Description: Defines the access.</span></span>

<span data-ttu-id="74d35-203">Opzioni 1-7:</span><span class="sxs-lookup"><span data-stu-id="74d35-203">Options 1-7:</span></span>
  - <span data-ttu-id="74d35-204">1: Lettura</span><span class="sxs-lookup"><span data-stu-id="74d35-204">1: Read</span></span>
  - <span data-ttu-id="74d35-205">2: Scrittura</span><span class="sxs-lookup"><span data-stu-id="74d35-205">2: Write</span></span>
  - <span data-ttu-id="74d35-206">3: Lettura e scrittura</span><span class="sxs-lookup"><span data-stu-id="74d35-206">3: Read and Write</span></span>
  - <span data-ttu-id="74d35-207">4: Eseguire</span><span class="sxs-lookup"><span data-stu-id="74d35-207">4: Execute</span></span>
  - <span data-ttu-id="74d35-208">5: Lettura ed esecuzione</span><span class="sxs-lookup"><span data-stu-id="74d35-208">5: Read and Execute</span></span>
  - <span data-ttu-id="74d35-209">6: Scrittura ed esecuzione</span><span class="sxs-lookup"><span data-stu-id="74d35-209">6: Write and Execute</span></span>
  - <span data-ttu-id="74d35-210">7: Lettura ed scrittura ed esecuzione</span><span class="sxs-lookup"><span data-stu-id="74d35-210">7: Read and Write and Execute</span></span>

## <a name="common-removable-storage-access-control-scenarios"></a><span data-ttu-id="74d35-211">Scenari comuni di controllo di Archiviazione rimovibili</span><span class="sxs-lookup"><span data-stu-id="74d35-211">Common Removable Storage Access Control scenarios</span></span>

<span data-ttu-id="74d35-212">Per acquisire familiarità con Microsoft Defender for Endpoint Removable Archiviazione Access Control, abbiamo creato alcuni scenari comuni da seguire.</span><span class="sxs-lookup"><span data-stu-id="74d35-212">To help familiarize you with Microsoft Defender for Endpoint Removable Storage Access Control, we have put together some common scenarios for you to follow.</span></span>

### <a name="scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs"></a><span data-ttu-id="74d35-213">Scenario 1: Impedire l'accesso in scrittura ed esecuzione a tutti gli USB approvati specifici, ma consentirne l'esecuzione</span><span class="sxs-lookup"><span data-stu-id="74d35-213">Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs</span></span>

1. <span data-ttu-id="74d35-214">Creare gruppi</span><span class="sxs-lookup"><span data-stu-id="74d35-214">Create groups</span></span>

    1. <span data-ttu-id="74d35-215">Gruppo 1: qualsiasi archivio rimovibile e CD/DVD.</span><span class="sxs-lookup"><span data-stu-id="74d35-215">Group 1: Any removable storage and CD/DVD.</span></span> <span data-ttu-id="74d35-216">Un esempio di archiviazione rimovibile e CD/DVD è il gruppo **9b28fae8-72f7-4267-a1a5-685f747a7146 nell'esempio** [Any Removable Archiviazione and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span><span class="sxs-lookup"><span data-stu-id="74d35-216">An example of a removable storage and CD/DVD is: Group **9b28fae8-72f7-4267-a1a5-685f747a7146** in the sample [Any Removable Storage and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="74d35-217">Gruppo 2: USB approvati in base alle proprietà del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="74d35-217">Group 2: Approved USBs based on device properties.</span></span> <span data-ttu-id="74d35-218">Un esempio per questo caso di utilizzo è: ID istanza - Gruppo **65fa649a-a111-4912-9294-fb6337a25038** nel file di esempio [approved usbs Group.xml.](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)</span><span class="sxs-lookup"><span data-stu-id="74d35-218">An example for this use case is: Instance ID – Group **65fa649a-a111-4912-9294-fb6337a25038** in the sample [Approved USBs Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

    > [!NOTE]
    > <span data-ttu-id="74d35-219">È necessario sostituire `&` con `&amp;` nel valore.</span><span class="sxs-lookup"><span data-stu-id="74d35-219">You have to replace `&` with `&amp;` in the value.</span></span>

2. <span data-ttu-id="74d35-220">Creazione di un criterio</span><span class="sxs-lookup"><span data-stu-id="74d35-220">Create policy</span></span>

    1. <span data-ttu-id="74d35-221">Criterio 1: bloccare l'accesso in scrittura ed esecuzione, ma consentire gli USB approvati.</span><span class="sxs-lookup"><span data-stu-id="74d35-221">Policy 1: Block Write and Execute Access but allow approved USBs.</span></span> <span data-ttu-id="74d35-222">Un esempio per questo caso d'uso è: PolicyRule **c544a991-5786-4402-949e-a032cb790d0e** nell'esempio [Scenario 1 Block Write and Execute Access but allow approved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span><span class="sxs-lookup"><span data-stu-id="74d35-222">An example for this use case is: PolicyRule **c544a991-5786-4402-949e-a032cb790d0e** in the sample [Scenario 1 Block Write and Execute Access but allow approved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="74d35-223">Criterio 2: controlla l'accesso in scrittura ed esecuzione agli USB consentiti.</span><span class="sxs-lookup"><span data-stu-id="74d35-223">Policy 2: Audit Write and Execute access to allowed USBs.</span></span> <span data-ttu-id="74d35-224">Un esempio per questo caso di utilizzo è: PolicyRule **36ae1037-a639-4cff-946b-b36c53089a4c** nell'esempio [Scenario 1 Audit Write and Execute access to approved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span><span class="sxs-lookup"><span data-stu-id="74d35-224">An example for this use case is: PolicyRule **36ae1037-a639-4cff-946b-b36c53089a4c** in the sample [Scenario 1 Audit Write and Execute access to approved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

### <a name="scenario-2-audit-write-and-execute-access-to-all-but-block-specific-unapproved-usbs"></a><span data-ttu-id="74d35-225">Scenario 2: controllare l'accesso in scrittura ed esecuzione a tutti gli USB non approvati specifici, ma bloccarlo</span><span class="sxs-lookup"><span data-stu-id="74d35-225">Scenario 2: Audit Write and Execute access to all but block specific unapproved USBs</span></span>

1. <span data-ttu-id="74d35-226">Creare gruppi</span><span class="sxs-lookup"><span data-stu-id="74d35-226">Create groups</span></span>

    1. <span data-ttu-id="74d35-227">Gruppo 1: qualsiasi archivio rimovibile e CD/DVD.</span><span class="sxs-lookup"><span data-stu-id="74d35-227">Group 1: Any removable storage and CD/DVD.</span></span> <span data-ttu-id="74d35-228">Un esempio di questo caso di utilizzo è il gruppo **9b28fae8-72f7-4267-a1a5-685f747a7146 nell'esempio** [Any Removable Archiviazione and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span><span class="sxs-lookup"><span data-stu-id="74d35-228">An example for this use case is: Group **9b28fae8-72f7-4267-a1a5-685f747a7146** in the sample [Any Removable Storage and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="74d35-229">Gruppo 2: USB non approvati in base alle proprietà del dispositivo, ad esempio ID fornitore/ID prodotto, Nome descrittivo - Gruppo **65fa649a-a111-4912-9294-fb6337a25038** nel file di esempio [USBs non approvate Group.xml.](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)</span><span class="sxs-lookup"><span data-stu-id="74d35-229">Group 2: Unapproved USBs based on device properties, for example, Vendor ID / Product ID, Friendly Name – Group **65fa649a-a111-4912-9294-fb6337a25038** in the sample [Unapproved USBs Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="74d35-230">È necessario sostituire `&` con `&amp;` nel valore.</span><span class="sxs-lookup"><span data-stu-id="74d35-230">You have to replace `&` with `&amp;` in the value.</span></span>

2. <span data-ttu-id="74d35-231">Creazione di un criterio</span><span class="sxs-lookup"><span data-stu-id="74d35-231">Create policy</span></span>

    1. <span data-ttu-id="74d35-232">Criterio 1: Bloccare l'accesso in scrittura ed esecuzione a tutti gli USB non approvati specifici.</span><span class="sxs-lookup"><span data-stu-id="74d35-232">Policy 1: Block Write and Execute access to all but block specific unapproved USBs.</span></span> <span data-ttu-id="74d35-233">Un esempio di questo caso di utilizzo è: PolicyRule **23b8e437-66ac-4b32-b3d7-24044637fc98 nell'esempio** [Scenario 2 Audit Write and Execute access to all but block specific unapproved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span><span class="sxs-lookup"><span data-stu-id="74d35-233">An example of this use case is: PolicyRule **23b8e437-66ac-4b32-b3d7-24044637fc98** in the sample [Scenario 2 Audit Write and Execute access to all but block specific unapproved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="74d35-234">Criterio 2: controllare l'accesso in scrittura ed esecuzione ad altri utenti.</span><span class="sxs-lookup"><span data-stu-id="74d35-234">Policy 2: Audit Write and Execute access to others.</span></span> <span data-ttu-id="74d35-235">Un esempio di questo caso di utilizzo è: PolicyRule **b58ab853-9a6f-405c-a194-740e69422b48 nell'esempio** [Scenario 2 Audit Write and Execute access to others.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span><span class="sxs-lookup"><span data-stu-id="74d35-235">An example of this use case is: PolicyRule **b58ab853-9a6f-405c-a194-740e69422b48** in the sample [Scenario 2 Audit Write and Execute access to others.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

## <a name="deploying-and-managing-policy-via-group-policy"></a><span data-ttu-id="74d35-236">Distribuzione e gestione dei criteri tramite Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="74d35-236">Deploying and managing policy via Group Policy</span></span>

<span data-ttu-id="74d35-237">La funzionalità Controllo di Archiviazione rimovibili consente di applicare i criteri tramite Criteri di gruppo a un utente o a un dispositivo o a entrambi.</span><span class="sxs-lookup"><span data-stu-id="74d35-237">The Removable Storage Access Control feature enables you to apply policy via Group Policy to either user or device, or both.</span></span>

### <a name="licensing"></a><span data-ttu-id="74d35-238">Licenze</span><span class="sxs-lookup"><span data-stu-id="74d35-238">Licensing</span></span>

<span data-ttu-id="74d35-239">Prima di iniziare a utilizzare Removable Archiviazione Access Control, è necessario confermare [l'Microsoft 365 abbonamento.](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2)</span><span class="sxs-lookup"><span data-stu-id="74d35-239">Before you get started with Removable Storage Access Control, you must confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2).</span></span> <span data-ttu-id="74d35-240">Per accedere a Removable Archiviazione Access Control, è necessario disporre di Microsoft 365 E3 o Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="74d35-240">To access and use Removable Storage Access Control, you must have Microsoft 365 E3 or Microsoft 365 E5.</span></span>

### <a name="deploying-policy-via-group-policy"></a><span data-ttu-id="74d35-241">Distribuzione dei criteri tramite Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="74d35-241">Deploying policy via Group Policy</span></span>

1. <span data-ttu-id="74d35-242">Combina tutti i gruppi `<Groups>` `</Groups>` all'interno di un unico file XML.</span><span class="sxs-lookup"><span data-stu-id="74d35-242">Combine all groups within `<Groups>` `</Groups>` into one xml file.</span></span> 

    <span data-ttu-id="74d35-243">Nell'immagine seguente viene illustrato l'esempio dello [scenario 1: Impedire](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)l'accesso in scrittura ed esecuzione a tutti gli USB approvati specifici.</span><span class="sxs-lookup"><span data-stu-id="74d35-243">The following image illustrates the example of [Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs).</span></span>
    
    :::image type="content" source="images/prevent-write-access-allow-usb.png" alt-text="Schermata che mostra le impostazioni di configurazione che consentono specifici USB approvati nei dispositivi":::
    
2. <span data-ttu-id="74d35-245">Combina tutte le regole `<PolicyRules>` `</PolicyRules>` all'interno di un unico file XML.</span><span class="sxs-lookup"><span data-stu-id="74d35-245">Combine all rules within `<PolicyRules>` `</PolicyRules>` into one xml file.</span></span> 

    <span data-ttu-id="74d35-246">Se si desidera limitare un utente specifico, utilizzare la proprietà SID nell'oggetto Entry.</span><span class="sxs-lookup"><span data-stu-id="74d35-246">If you want to restrict a specific user, then use SID property into the Entry.</span></span> <span data-ttu-id="74d35-247">Se non è presente alcun SID nella voce del criterio, la voce verrà applicata a tutti gli utenti dell'istanza di accesso per il computer.</span><span class="sxs-lookup"><span data-stu-id="74d35-247">If there is no SID in the policy Entry, the Entry will be applied to everyone login instance for the machine.</span></span>
    
    <span data-ttu-id="74d35-248">Nell'immagine seguente viene illustrato l'utilizzo della proprietà SID e un esempio dello [scenario 1:](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)Impedire l'accesso in scrittura ed esecuzione a tutti gli USB approvati specifici.</span><span class="sxs-lookup"><span data-stu-id="74d35-248">The following image illustrates the usage of SID property, and an example of [Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs).</span></span>
    
    :::image type="content" source="images/usage-sid-property.png" alt-text="Schermata che visualizza un codice che indica l'utilizzo dell'attributo della proprietà SID":::

3. <span data-ttu-id="74d35-250">Salvare sia i file XML delle regole che dei gruppi nella cartella della condivisione di rete e inserire il percorso della cartella della condivisione di rete nell'impostazione di Criteri di gruppo: Configurazione computer -> Modelli amministrativi **-> Windows Componenti -> Antivirus Microsoft Defender -> Controllo dispositivi: "Definire** i gruppi di criteri di controllo dei dispositivi" e "Definire le regole dei criteri di controllo dei dispositivi".</span><span class="sxs-lookup"><span data-stu-id="74d35-250">Save both rule and group XML files on network share folder and put network share folder path into the Group Policy setting: **Computer Configuration -> Administrative Templates -> Windows Components -> Microsoft Defender Antivirus -> Device Control: ‘Define device control policy groups’ and ‘Define device control policy rules’**.</span></span>

    - <span data-ttu-id="74d35-251">Il computer di destinazione deve essere in grado di accedere alla condivisione di rete per disporre del criterio.</span><span class="sxs-lookup"><span data-stu-id="74d35-251">The target machine must be able to access the network share to have the policy.</span></span> <span data-ttu-id="74d35-252">Tuttavia, una volta letto il criterio, la connessione di condivisione di rete non è più necessaria, anche dopo il riavvio del computer.</span><span class="sxs-lookup"><span data-stu-id="74d35-252">However, once the policy is read, the network share connection is no longer required, even after machine reboot.</span></span>

    :::image type="content" source="images/device-control.png" alt-text="Schermata Controllo dispositivo":::

## <a name="deploying-and-managing-policy-via-intune-oma-uri"></a><span data-ttu-id="74d35-254">Distribuzione e gestione dei criteri tramite URI OMA di Intune</span><span class="sxs-lookup"><span data-stu-id="74d35-254">Deploying and managing policy via Intune OMA-URI</span></span>

<span data-ttu-id="74d35-255">La funzionalità Controllo di Archiviazione rimovibili consente di applicare i criteri tramite URI OMA a un utente o a un dispositivo o a entrambi.</span><span class="sxs-lookup"><span data-stu-id="74d35-255">The Removable Storage Access Control feature enables you to apply policy via OMA-URI to either user or device, or both.</span></span>

### <a name="licensing"></a><span data-ttu-id="74d35-256">Licenze</span><span class="sxs-lookup"><span data-stu-id="74d35-256">Licensing</span></span>

<span data-ttu-id="74d35-257">Prima di iniziare a utilizzare Removable Archiviazione Access Control, è necessario confermare [l'Microsoft 365 abbonamento.](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2)</span><span class="sxs-lookup"><span data-stu-id="74d35-257">Before you get started with Removable Storage Access Control, you  must confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2).</span></span> <span data-ttu-id="74d35-258">Per accedere a Removable Archiviazione Access Control, è necessario disporre di Microsoft 365 E3 o Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="74d35-258">To access and use Removable Storage Access Control, you must have Microsoft 365 E3 or Microsoft 365 E5.</span></span>

### <a name="permission"></a><span data-ttu-id="74d35-259">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="74d35-259">Permission</span></span>

<span data-ttu-id="74d35-260">Per la distribuzione dei criteri in Intune, l'account deve disporre delle autorizzazioni per creare, modificare, aggiornare o eliminare i profili di configurazione dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="74d35-260">For policy deployment in Intune, the account must have permissions to create, edit, update, or delete device configuration profiles.</span></span> <span data-ttu-id="74d35-261">È possibile creare ruoli personalizzati o utilizzare uno qualsiasi dei ruoli predefiniti con queste autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="74d35-261">You can create custom roles or use any of the built-in roles with these permissions.</span></span>

- <span data-ttu-id="74d35-262">Ruolo Gestione criteri e profili</span><span class="sxs-lookup"><span data-stu-id="74d35-262">Policy and profile Manager role</span></span>
- <span data-ttu-id="74d35-263">Ruolo personalizzato con autorizzazioni Create/Edit/Update/Read/Delete/View Reports attivate per i profili di configurazione dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="74d35-263">Custom role with Create/Edit/Update/Read/Delete/View Reports permissions turned on for Device Configuration profiles</span></span>
- <span data-ttu-id="74d35-264">Amministratore globale</span><span class="sxs-lookup"><span data-stu-id="74d35-264">Global administrator</span></span>

### <a name="deploying-policy-via-oma-uri"></a><span data-ttu-id="74d35-265">Distribuzione dei criteri tramite URI OMA</span><span class="sxs-lookup"><span data-stu-id="74d35-265">Deploying policy via OMA-URI</span></span>

<span data-ttu-id="74d35-266">**Microsoft Endpoint Manager di amministrazione ( https://endpoint.microsoft.com/) -> Devices -> Configuration profiles -> Create profile -> Platform: Windows 10 and later & Profile: Custom**</span><span class="sxs-lookup"><span data-stu-id="74d35-266">**Microsoft Endpoint Manager admin center (https://endpoint.microsoft.com/) -> Devices -> Configuration profiles -> Create profile -> Platform: Windows 10 and later & Profile: Custom**</span></span>

1. <span data-ttu-id="74d35-267">Per ogni gruppo, crea una regola URI OMA:</span><span class="sxs-lookup"><span data-stu-id="74d35-267">For each Group, create an OMA-URI rule:</span></span>
    - <span data-ttu-id="74d35-268">OMA-URI: </span><span class="sxs-lookup"><span data-stu-id="74d35-268">OMA-URI:</span></span>

      <span data-ttu-id="74d35-269">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b **GroupGUID**%7d/GroupData</span><span class="sxs-lookup"><span data-stu-id="74d35-269">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b **GroupGUID**%7d/GroupData</span></span>

      <span data-ttu-id="74d35-270">Ad esempio, per qualsiasi gruppo di archiviazione rimovibile e **CD/DVD** nell'esempio, il collegamento deve essere:</span><span class="sxs-lookup"><span data-stu-id="74d35-270">For example, for **any removable storage and CD/DVD** group in the sample, the link must be:</span></span>

      <span data-ttu-id="74d35-271">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b9b28fae8-72f7-4267-a1a5-685f747a7146%7d/GroupData</span><span class="sxs-lookup"><span data-stu-id="74d35-271">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b9b28fae8-72f7-4267-a1a5-685f747a7146%7d/GroupData</span></span>

    - <span data-ttu-id="74d35-272">Tipo di dati: String (file XML)</span><span class="sxs-lookup"><span data-stu-id="74d35-272">Data Type: String (XML file)</span></span>
    
      :::image type="content" source="images/xml-data-type-string.png" alt-text="File XML per il tipo di dati STRING":::

2. <span data-ttu-id="74d35-274">Per ogni criterio, crea anche un URI OMA:</span><span class="sxs-lookup"><span data-stu-id="74d35-274">For each policy, also create an OMA-URI:</span></span>

    - <span data-ttu-id="74d35-275">OMA-URI: </span><span class="sxs-lookup"><span data-stu-id="74d35-275">OMA-URI:</span></span>

      <span data-ttu-id="74d35-276">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bFA6BE102-0784-4A2A-B010-A0BEBEBF68E1%7d/RuleData</span><span class="sxs-lookup"><span data-stu-id="74d35-276">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bFA6BE102-0784-4A2A-B010-A0BEBEBF68E1%7d/RuleData</span></span>

      <span data-ttu-id="74d35-277">Ad esempio, per la regola Blocca scrittura ed esecuzione accesso ma consenti le **usbs** approvate nell'esempio, il collegamento deve essere:</span><span class="sxs-lookup"><span data-stu-id="74d35-277">For example, for the **Block Write and Execute Access but allow approved USBs** rule in the sample, the link must be:</span></span> 

      <span data-ttu-id="74d35-278">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bc544a991-5786-4402-949e-a032cb790d0e%7d/RuleData.</span><span class="sxs-lookup"><span data-stu-id="74d35-278">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bc544a991-5786-4402-949e-a032cb790d0e%7d/RuleData.</span></span>

    - <span data-ttu-id="74d35-279">Tipo di dati: String (file XML)</span><span class="sxs-lookup"><span data-stu-id="74d35-279">Data Type: String (XML file)</span></span>

      :::image type="content" source="images/xml-data-type-string-2.png" lightbox="images/xml-data-type-string-2.png" alt-text="Visualizzazione del file XML per il tipo di dati STRING":::

## <a name="deploying-and-managing-policy-by-using-intune-user-interface"></a><span data-ttu-id="74d35-281">Distribuzione e gestione dei criteri tramite l'interfaccia utente di Intune</span><span class="sxs-lookup"><span data-stu-id="74d35-281">Deploying and managing policy by using Intune user interface</span></span>

<span data-ttu-id="74d35-282">Questa funzionalità (nell'interfaccia di amministrazione di Microsoft Endpoint Manager ( > https://endpoint.microsoft.com/) Devices > Configuration profiles > Create profile > Platform: Windows 10 and later & Profile: Device Control) non è ancora disponibile.</span><span class="sxs-lookup"><span data-stu-id="74d35-282">This capability (in Microsoft Endpoint Manager admin center (https://endpoint.microsoft.com/) > Devices > Configuration profiles > Create profile > Platform: Windows 10 and later & Profile: Device Control) is not yet available.</span></span> 

## <a name="view-device-control-removable-storage-access-control-data-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="74d35-283">Visualizzare i dati di controllo Archiviazione di accesso rimovibili in Microsoft Defender per Endpoint</span><span class="sxs-lookup"><span data-stu-id="74d35-283">View Device Control Removable Storage Access Control data in Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="74d35-284">Il portale Microsoft 365 sicurezza mostra l'archiviazione rimovibile bloccata dal Controllo dispositivo Rimovibile Archiviazione Access Control.</span><span class="sxs-lookup"><span data-stu-id="74d35-284">The Microsoft 365 security portal shows removable storage blocked by the Device Control Removable Storage Access Control.</span></span> <span data-ttu-id="74d35-285">Per accedere alla Microsoft 365 sicurezza, è necessario disporre dell'abbonamento seguente:</span><span class="sxs-lookup"><span data-stu-id="74d35-285">To access the Microsoft 365 security, you must have the following subscription:</span></span>

- <span data-ttu-id="74d35-286">Microsoft 365 per la creazione di report E5</span><span class="sxs-lookup"><span data-stu-id="74d35-286">Microsoft 365 for E5 reporting</span></span>

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

## <a name="frequently-asked-questions"></a><span data-ttu-id="74d35-288">Domande frequenti</span><span class="sxs-lookup"><span data-stu-id="74d35-288">Frequently asked questions</span></span>

<span data-ttu-id="74d35-289">**Qual è la limitazione del supporto di archiviazione rimovibile per il numero massimo di USB?**</span><span class="sxs-lookup"><span data-stu-id="74d35-289">**What is the removable storage media limitation for the maximum number of USBs?**</span></span>

<span data-ttu-id="74d35-290">È stato convalidato un gruppo USB con 100.000 supporti, fino a 7 MB.</span><span class="sxs-lookup"><span data-stu-id="74d35-290">We have validated one USB group with 100,000 media - up to 7 MB in size.</span></span> <span data-ttu-id="74d35-291">Il criterio funziona sia in Intune che negli oggetti Criteri di gruppo senza problemi di prestazioni.</span><span class="sxs-lookup"><span data-stu-id="74d35-291">The policy works in both Intune and GPO without performance issues.</span></span>

<span data-ttu-id="74d35-292">**Perché il criterio non funziona?**</span><span class="sxs-lookup"><span data-stu-id="74d35-292">**Why does the policy not work?**</span></span>

<span data-ttu-id="74d35-293">Il motivo più comune è che non esiste una versione [client antimalware necessaria.](/microsoft-365/security/defender-endpoint/device-control-removable-storage-access-control#prepare-your-endpoints)</span><span class="sxs-lookup"><span data-stu-id="74d35-293">The most common reason is there is no required [antimalware client version](/microsoft-365/security/defender-endpoint/device-control-removable-storage-access-control#prepare-your-endpoints).</span></span>

<span data-ttu-id="74d35-294">Un altro motivo potrebbe essere che il file XML non è formattato correttamente, ad esempio, non utilizzando la formattazione markdown corretta per il carattere "&" nel file XML oppure l'editor di testo potrebbe aggiungere un indicatore dell'ordine dei byte (BOM) 0xEF 0xBB 0xBF all'inizio dei file che causa il non funzionamento dell'analisi XML.</span><span class="sxs-lookup"><span data-stu-id="74d35-294">Another reason could be that the XML file is not correctly formatted, for example, not using the correct markdown formatting for the "&" character in the XML file, or the text editor might add a byte order mark (BOM) 0xEF 0xBB 0xBF at the beginning of the files which causes the XML parsing not to work.</span></span> <span data-ttu-id="74d35-295">Una soluzione semplice consiste nel scaricare il [file di](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) esempio (selezionare **Raw** e quindi **Salva con** nome ) e quindi aggiornare.</span><span class="sxs-lookup"><span data-stu-id="74d35-295">One simple solution is to download the [sample file](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) (select **Raw** and then **Save as**) and then update.</span></span>

<span data-ttu-id="74d35-296">Se è presente un valore e il criterio viene gestito tramite Criteri di gruppo, verificare se il dispositivo client può accedere al percorso XML dei criteri.</span><span class="sxs-lookup"><span data-stu-id="74d35-296">If there is a value and the policy is managed via Group Policy, check whether the client device can access the policy XML path.</span></span>

<span data-ttu-id="74d35-297">**Come è possibile sapere quale computer utilizza una versione client antimalware non aggiornata nell'organizzazione?**</span><span class="sxs-lookup"><span data-stu-id="74d35-297">**How can I know which machine is using out of date antimalware client version in the organization?**</span></span>

<span data-ttu-id="74d35-298">È possibile utilizzare la query seguente per ottenere la versione del client antimalware nel portale Microsoft 365 sicurezza:</span><span class="sxs-lookup"><span data-stu-id="74d35-298">You can use following query to get antimalware client version on the Microsoft 365 security portal:</span></span>
```kusto
//check the antimalware client version
DeviceFileEvents
| where FileName == "MsMpEng.exe"
| where FolderPath contains @"C:\ProgramData\Microsoft\Windows Defender\Platform\"
| extend PlatformVersion=tostring(split(FolderPath, "\\", 5))
//| project DeviceName, PlatformVersion // check which machine is using legacy platformVersion
| summarize dcount(DeviceName) by PlatformVersion // check how many machines are using which platformVersion
| order by PlatformVersion desc
```
