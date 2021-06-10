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
ms.openlocfilehash: cf8e74a6886d7086da062d6258e3e1e1a1cbd730
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861720"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-access-control"></a><span data-ttu-id="7dafc-104">Microsoft Defender for Endpoint Device Control Removable Archiviazione Access Control</span><span class="sxs-lookup"><span data-stu-id="7dafc-104">Microsoft Defender for Endpoint Device Control Removable Storage Access Control</span></span>

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="7dafc-105">Microsoft Defender for Endpoint Device Control Removable Archiviazione Access Control consente di eseguire l'attività seguente:</span><span class="sxs-lookup"><span data-stu-id="7dafc-105">Microsoft Defender for Endpoint Device Control Removable Storage Access Control enables you to do the following task:</span></span>
- <span data-ttu-id="7dafc-106">controllo, consentendo o impedendo l'accesso in lettura, scrittura o esecuzione all'archiviazione rimovibile con o senza esclusione</span><span class="sxs-lookup"><span data-stu-id="7dafc-106">auditing, allowing or preventing the read, write or execute access to removable storage with or without exclusion</span></span>

|<span data-ttu-id="7dafc-107">Privilegio</span><span class="sxs-lookup"><span data-stu-id="7dafc-107">Privilege</span></span> |<span data-ttu-id="7dafc-108">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="7dafc-108">Permission</span></span>  |
|---------|---------|
|<span data-ttu-id="7dafc-109">Access</span><span class="sxs-lookup"><span data-stu-id="7dafc-109">Access</span></span>    |  <span data-ttu-id="7dafc-110">Lettura, scrittura ed esecuzione</span><span class="sxs-lookup"><span data-stu-id="7dafc-110">Read, Write, Execute</span></span>       |
|<span data-ttu-id="7dafc-111">Modalità azione</span><span class="sxs-lookup"><span data-stu-id="7dafc-111">Action Mode</span></span>    |    <span data-ttu-id="7dafc-112">Controllo, Consenti, Impedisci</span><span class="sxs-lookup"><span data-stu-id="7dafc-112">Audit, Allow, Prevent</span></span>     |
|<span data-ttu-id="7dafc-113">Supporto CSP</span><span class="sxs-lookup"><span data-stu-id="7dafc-113">CSP Support</span></span>   |   <span data-ttu-id="7dafc-114">Sì</span><span class="sxs-lookup"><span data-stu-id="7dafc-114">Yes</span></span>      |
|<span data-ttu-id="7dafc-115">Supporto oggetti Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="7dafc-115">GPO Support</span></span>    |   <span data-ttu-id="7dafc-116">Sì</span><span class="sxs-lookup"><span data-stu-id="7dafc-116">Yes</span></span>      |
|<span data-ttu-id="7dafc-117">Supporto basato sull'utente</span><span class="sxs-lookup"><span data-stu-id="7dafc-117">User-based Support</span></span>     |   <span data-ttu-id="7dafc-118">Sì</span><span class="sxs-lookup"><span data-stu-id="7dafc-118">Yes</span></span>      |
|<span data-ttu-id="7dafc-119">Supporto basato su computer</span><span class="sxs-lookup"><span data-stu-id="7dafc-119">Machine-based Support</span></span>    |    <span data-ttu-id="7dafc-120">Sì</span><span class="sxs-lookup"><span data-stu-id="7dafc-120">Yes</span></span>     |

## <a name="prepare-your-endpoints"></a><span data-ttu-id="7dafc-121">Preparare gli endpoint</span><span class="sxs-lookup"><span data-stu-id="7dafc-121">Prepare your endpoints</span></span>

<span data-ttu-id="7dafc-122">Distribuire Il controllo di accesso Archiviazione rimovibili nei dispositivi Windows 10 con antimalware Client versione **4.18.2103.3 o successiva.**</span><span class="sxs-lookup"><span data-stu-id="7dafc-122">Deploy Removable Storage Access Control on Windows 10 devices that have Anti-malware Client Version **4.18.2103.3 or later**.</span></span>
1. <span data-ttu-id="7dafc-123">**4.18.2104 o** versione successiva : Aggiungere SerialNumberId, VID_PID, supporto dell'oggetto Criteri di gruppo basato su filepath, ComputerSid</span><span class="sxs-lookup"><span data-stu-id="7dafc-123">**4.18.2104 or later**: Add SerialNumberId, VID_PID, filepath-based GPO support, ComputerSid</span></span>

2. <span data-ttu-id="7dafc-124">**4.18.2105 o** versione successiva : Aggiungere il supporto dei caratteri jolly per HardwareId/DeviceId/InstancePathId/FriendlyNameId/SerialNumberId, la combinazione di un utente specifico in un computer specifico, SSD rimovibile (un SSD SanDisk Extreme)/supporto USB Attached SCSI (UAS)</span><span class="sxs-lookup"><span data-stu-id="7dafc-124">**4.18.2105 or later**: Add Wildcard support for HardwareId/DeviceId/InstancePathId/FriendlyNameId/SerialNumberId, the combination of specific user on specific machine, removeable SSD (a SanDisk Extreme SSD)/USB Attached SCSI (UAS) support</span></span>

:::image type="content" source="images/powershell.png" alt-text="Interfaccia di PowerShell":::

   > [!NOTE]
   > <span data-ttu-id="7dafc-126">Nessuno dei Sicurezza di Windows deve essere attivo, è possibile eseguire Removable Archiviazione Access Control indipendentemente Sicurezza di Windows stato.</span><span class="sxs-lookup"><span data-stu-id="7dafc-126">None of Windows Security components need to be active, you can run Removable Storage Access Control independent of Windows Security status.</span></span>

## <a name="policy-properties"></a><span data-ttu-id="7dafc-127">Proprietà dei criteri</span><span class="sxs-lookup"><span data-stu-id="7dafc-127">Policy properties</span></span>


<span data-ttu-id="7dafc-128">È possibile utilizzare le proprietà seguenti per creare un gruppo di archiviazione rimovibile:</span><span class="sxs-lookup"><span data-stu-id="7dafc-128">You can use the following properties to create a removable storage group:</span></span>

<span data-ttu-id="7dafc-129">**Nome proprietà: ID gruppo**</span><span class="sxs-lookup"><span data-stu-id="7dafc-129">**Property name: Group Id**</span></span>

1. <span data-ttu-id="7dafc-130">Descrizione: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), un ID univoco, rappresenta il gruppo e verrà utilizzato nel criterio.</span><span class="sxs-lookup"><span data-stu-id="7dafc-130">Description: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), a unique ID, represents the group and will be used in the policy.</span></span>

<span data-ttu-id="7dafc-131">**Nome proprietà: DescriptorIdList**</span><span class="sxs-lookup"><span data-stu-id="7dafc-131">**Property name: DescriptorIdList**</span></span>

1. <span data-ttu-id="7dafc-132">Descrizione: elenca le proprietà del dispositivo che vuoi usare per coprire il gruppo.</span><span class="sxs-lookup"><span data-stu-id="7dafc-132">Description: List the device properties you want to use to cover in the group.</span></span>
<span data-ttu-id="7dafc-133">Elenca le proprietà del dispositivo che vuoi usare per coprire il gruppo.</span><span class="sxs-lookup"><span data-stu-id="7dafc-133">List the device properties you want to use to cover in the group.</span></span>
<span data-ttu-id="7dafc-134">Per ogni proprietà del dispositivo, vedi **la sezione Proprietà dispositivo** sopra riportata per ulteriori dettagli.</span><span class="sxs-lookup"><span data-stu-id="7dafc-134">For each device property, see **Device Properties** section above for more detail.</span></span>

1. <span data-ttu-id="7dafc-135">Opzioni:</span><span class="sxs-lookup"><span data-stu-id="7dafc-135">Options:</span></span>
    - <span data-ttu-id="7dafc-136">ID primario</span><span class="sxs-lookup"><span data-stu-id="7dafc-136">Primary ID</span></span>
        - <span data-ttu-id="7dafc-137">RemovableMediaDevices</span><span class="sxs-lookup"><span data-stu-id="7dafc-137">RemovableMediaDevices</span></span>
        - <span data-ttu-id="7dafc-138">CdRomDevices</span><span class="sxs-lookup"><span data-stu-id="7dafc-138">CdRomDevices</span></span>
    - <span data-ttu-id="7dafc-139">DeviceId</span><span class="sxs-lookup"><span data-stu-id="7dafc-139">DeviceId</span></span>
    - <span data-ttu-id="7dafc-140">HardwareId</span><span class="sxs-lookup"><span data-stu-id="7dafc-140">HardwareId</span></span>
    - <span data-ttu-id="7dafc-141">InstancePathId: InstancePathId è una stringa che identifica in modo univoco il dispositivo nel sistema, ad esempio USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0.</span><span class="sxs-lookup"><span data-stu-id="7dafc-141">InstancePathId: InstancePathId is a string that uniquely identifies the device in the system, for example, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0.</span></span> <span data-ttu-id="7dafc-142">Il numero alla fine (ad esempio **&0)** rappresenta lo slot disponibile e può cambiare da dispositivo a dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7dafc-142">The number at the end (for example **&0**) represents the available slot and may change from device to device.</span></span> <span data-ttu-id="7dafc-143">Per ottenere risultati ottimali, utilizzare un carattere jolly alla fine.</span><span class="sxs-lookup"><span data-stu-id="7dafc-143">For best results, use a wildcard at the end.</span></span> <span data-ttu-id="7dafc-144">Ad esempio, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611\*</span><span class="sxs-lookup"><span data-stu-id="7dafc-144">For example, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611\*</span></span>
    - <span data-ttu-id="7dafc-145">FriendlyNameId</span><span class="sxs-lookup"><span data-stu-id="7dafc-145">FriendlyNameId</span></span>
    - <span data-ttu-id="7dafc-146">SerialNumberId</span><span class="sxs-lookup"><span data-stu-id="7dafc-146">SerialNumberId</span></span>
    - <span data-ttu-id="7dafc-147">VID</span><span class="sxs-lookup"><span data-stu-id="7dafc-147">VID</span></span>
    - <span data-ttu-id="7dafc-148">PID</span><span class="sxs-lookup"><span data-stu-id="7dafc-148">PID</span></span>
    - <span data-ttu-id="7dafc-149">VID_PID</span><span class="sxs-lookup"><span data-stu-id="7dafc-149">VID_PID</span></span>
        - <span data-ttu-id="7dafc-150">0751_55E0: corrisponde a questa coppia VID/PID esatta</span><span class="sxs-lookup"><span data-stu-id="7dafc-150">0751_55E0: match this exact VID/PID pair</span></span>
        - <span data-ttu-id="7dafc-151">_55E0: corrisponde a qualsiasi supporto con PID=55E0</span><span class="sxs-lookup"><span data-stu-id="7dafc-151">_55E0: match any media with PID=55E0</span></span>
        - <span data-ttu-id="7dafc-152">0751_: corrisponde a qualsiasi supporto con VID=0751</span><span class="sxs-lookup"><span data-stu-id="7dafc-152">0751_: match any media with VID=0751</span></span>
        
<span data-ttu-id="7dafc-153">**Nome proprietà: MatchType**</span><span class="sxs-lookup"><span data-stu-id="7dafc-153">**Property name: MatchType**</span></span> 

1. <span data-ttu-id="7dafc-154">Descrizione: quando in DescriptorIDList vengono utilizzate più proprietà del dispositivo, MatchType definisce la relazione.</span><span class="sxs-lookup"><span data-stu-id="7dafc-154">Description: When there are multiple device properties being used in the DescriptorIDList, MatchType defines the relationship.</span></span>

1. <span data-ttu-id="7dafc-155">Opzioni:</span><span class="sxs-lookup"><span data-stu-id="7dafc-155">Options:</span></span>
    - <span data-ttu-id="7dafc-156">MatchAll: tutti gli attributi in DescriptorIdList saranno **relazione And.** Ad esempio, se l'amministratore inserisce DeviceID e InstancePathID per ogni USB connesso, il sistema controllera' se l'USB soddisfa entrambi i valori.</span><span class="sxs-lookup"><span data-stu-id="7dafc-156">MatchAll: Any attributes under the DescriptorIdList will be **And** relationship; for example, if administrator puts DeviceID and InstancePathID, for every connected USB, system will check to see whether the USB meets both values.</span></span>

    - <span data-ttu-id="7dafc-157">MatchAny: gli attributi sotto DescriptorIdList saranno **relazione Or.** Ad esempio, se l'amministratore inserisce DeviceID e InstancePathID, per ogni USB connessa, il sistema farà l'imposizione purché l'USB abbia un **valore DeviceID** o **InstanceID** identico.</span><span class="sxs-lookup"><span data-stu-id="7dafc-157">MatchAny: The attributes under the DescriptorIdList will be **Or** relationship; for example, if administrator puts DeviceID and InstancePathID, for every connected USB, system will do the enforcement as long as the USB has either an identical **DeviceID** or **InstanceID** value.</span></span>



<span data-ttu-id="7dafc-158">Di seguito sono riportate le proprietà dei criteri di controllo di accesso:</span><span class="sxs-lookup"><span data-stu-id="7dafc-158">Following are the access control policy properties:</span></span>

<span data-ttu-id="7dafc-159">**Nome proprietà: PolicyRuleId**</span><span class="sxs-lookup"><span data-stu-id="7dafc-159">**Property name: PolicyRuleId**</span></span>

1. <span data-ttu-id="7dafc-160">Descrizione: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), un ID univoco, rappresenta il criterio e verrà utilizzato nei report e nella risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="7dafc-160">Description: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), a unique ID, represents the policy and will be used in the reporting and troubleshooting.</span></span>

<span data-ttu-id="7dafc-161">**Nome proprietà: IncludedIdList**</span><span class="sxs-lookup"><span data-stu-id="7dafc-161">**Property name: IncludedIdList**</span></span>

1. <span data-ttu-id="7dafc-162">Descrizione: i gruppi a cui verrà applicato il criterio.</span><span class="sxs-lookup"><span data-stu-id="7dafc-162">Description: The group(s) that the policy will be applied to.</span></span> <span data-ttu-id="7dafc-163">Se vengono aggiunti più gruppi, il criterio verrà applicato a tutti i supporti di tutti i gruppi.</span><span class="sxs-lookup"><span data-stu-id="7dafc-163">If multiple groups are added, the policy will be applied to any media in all those groups.</span></span>

1. <span data-ttu-id="7dafc-164">Opzioni: l'ID gruppo/GUID deve essere utilizzato in questa istanza.</span><span class="sxs-lookup"><span data-stu-id="7dafc-164">Options: The Group ID/GUID must be used at this instance.</span></span>

<span data-ttu-id="7dafc-165">Nell'esempio seguente viene illustrato l'utilizzo di GroupID:</span><span class="sxs-lookup"><span data-stu-id="7dafc-165">The following example shows the usage of GroupID:</span></span>

`<IncludedIdList> <GroupId>{EAA4CCE5-F6C9-4760-8BAD-FDCC76A2ACA1}</GroupId> </IncludedIdList>`

<span data-ttu-id="7dafc-166">**Nome proprietà: ExcludedIDList**</span><span class="sxs-lookup"><span data-stu-id="7dafc-166">**Property name: ExcludedIDList**</span></span>

1. <span data-ttu-id="7dafc-167">Descrizione: i gruppi a cui non verrà applicato il criterio.</span><span class="sxs-lookup"><span data-stu-id="7dafc-167">Description: The group(s) that the policy will not be applied to.</span></span>
1. <span data-ttu-id="7dafc-168">Opzioni: l'ID gruppo/GUID deve essere utilizzato in questa istanza.</span><span class="sxs-lookup"><span data-stu-id="7dafc-168">Options: The Group ID/GUID must be used at this instance.</span></span>

<span data-ttu-id="7dafc-169">**Nome proprietà: Id voce**</span><span class="sxs-lookup"><span data-stu-id="7dafc-169">**Property name: Entry Id**</span></span>

1. <span data-ttu-id="7dafc-170">Descrizione: Un oggetto PolicyRule può avere più voci. ogni voce con un GUID univoco indica a Device Control una restrizione.</span><span class="sxs-lookup"><span data-stu-id="7dafc-170">Description: One PolicyRule can have multiple entries; each entry with a unique GUID tells Device Control one restriction.</span></span>

<span data-ttu-id="7dafc-171">**Nome proprietà: Type**</span><span class="sxs-lookup"><span data-stu-id="7dafc-171">**Property name: Type**</span></span>

1. <span data-ttu-id="7dafc-172">Descrizione: definisce l'azione per i gruppi di archiviazione rimovibili in IncludedIDList.</span><span class="sxs-lookup"><span data-stu-id="7dafc-172">Description: Defines the action for the removable storage groups in IncludedIDList.</span></span>
    - <span data-ttu-id="7dafc-173">Imposizione: Consenti o Nega</span><span class="sxs-lookup"><span data-stu-id="7dafc-173">Enforcement: Allow or Deny</span></span>
    - <span data-ttu-id="7dafc-174">Controllo: AuditAllowed o AuditDenied</span><span class="sxs-lookup"><span data-stu-id="7dafc-174">Audit: AuditAllowed or AuditDenied</span></span> 
1. <span data-ttu-id="7dafc-175">Opzioni:</span><span class="sxs-lookup"><span data-stu-id="7dafc-175">Options:</span></span>
    - <span data-ttu-id="7dafc-176">Consenti</span><span class="sxs-lookup"><span data-stu-id="7dafc-176">Allow</span></span>
    - <span data-ttu-id="7dafc-177">Nega</span><span class="sxs-lookup"><span data-stu-id="7dafc-177">Deny</span></span>
    - <span data-ttu-id="7dafc-178">AuditAllowed: definisce la notifica e l'evento quando è consentito l'accesso</span><span class="sxs-lookup"><span data-stu-id="7dafc-178">AuditAllowed: Defines notification and event when access is allowed</span></span>
    - <span data-ttu-id="7dafc-179">AuditDenied: definisce la notifica e l'evento quando l'accesso viene negato. deve collaborare con **la voce** Deny.</span><span class="sxs-lookup"><span data-stu-id="7dafc-179">AuditDenied: Defines notification and event when access is denied; has to work together with **Deny** entry.</span></span>

<span data-ttu-id="7dafc-180">Quando sono presenti tipi di conflitto per lo stesso supporto, il sistema applierà il primo nel criterio.</span><span class="sxs-lookup"><span data-stu-id="7dafc-180">When there are conflict types for the same media, the system will apply the first one in the policy.</span></span> <span data-ttu-id="7dafc-181">Un esempio di tipo di conflitto è **Allow** e **Deny.**</span><span class="sxs-lookup"><span data-stu-id="7dafc-181">An example of a conflict type is **Allow** and **Deny**.</span></span>

<span data-ttu-id="7dafc-182">**Nome proprietà: Sid**</span><span class="sxs-lookup"><span data-stu-id="7dafc-182">**Property name: Sid**</span></span>

1. <span data-ttu-id="7dafc-183">Descrizione: definisce se applicare questo criterio a un utente o a un gruppo di utenti specifico. una voce può avere al massimo un Sid e una voce senza sid significa applicare il criterio sul computer.</span><span class="sxs-lookup"><span data-stu-id="7dafc-183">Description: Defines whether apply this policy over specific user or user group; one entry can have maximum one Sid and an entry without any Sid means applying the policy over the machine.</span></span>

<span data-ttu-id="7dafc-184">**Nome proprietà: ComputerSid**</span><span class="sxs-lookup"><span data-stu-id="7dafc-184">**Property name: ComputerSid**</span></span>

1. <span data-ttu-id="7dafc-185">Descrizione: definisce se applicare questo criterio a un computer o a un gruppo di computer specifico. una voce può avere al massimo un ComputerSid e una voce senza ComputerSid significa applicare il criterio sul computer.</span><span class="sxs-lookup"><span data-stu-id="7dafc-185">Description: Defines whether apply this policy over specific machine or machine group; one entry can have maximum one ComputerSid and an entry without any ComputerSid means applying the policy over the machine.</span></span> <span data-ttu-id="7dafc-186">Se si desidera applicare una voce a un utente specifico e a un computer specifico, aggiungere sia Sid che ComputerSid nella stessa voce.</span><span class="sxs-lookup"><span data-stu-id="7dafc-186">If you want to apply an Entry to a specific user and specific machine, add both Sid and ComputerSid into the same Entry.</span></span>

<span data-ttu-id="7dafc-187">**Nome proprietà: Opzioni**</span><span class="sxs-lookup"><span data-stu-id="7dafc-187">**Property name: Options**</span></span>

1. <span data-ttu-id="7dafc-188">Descrizione: definisce se visualizzare o meno la notifica.</span><span class="sxs-lookup"><span data-stu-id="7dafc-188">Description: Defines whether to display notification or not.</span></span>

   :::image type="content" source="images/device-status.png" alt-text="Schermata in cui è possibile visualizzare lo stato del dispositivo":::

1. <span data-ttu-id="7dafc-190">Opzioni: 0-4.</span><span class="sxs-lookup"><span data-stu-id="7dafc-190">Options: 0-4.</span></span> <span data-ttu-id="7dafc-191">Quando è selezionata l'opzione Digitazione Consenti o Nega:</span><span class="sxs-lookup"><span data-stu-id="7dafc-191">When Type Allow or Deny is selected:</span></span>

   - <span data-ttu-id="7dafc-192">0: nothing</span><span class="sxs-lookup"><span data-stu-id="7dafc-192">0: nothing</span></span>
   - <span data-ttu-id="7dafc-193">4: **disabilitare AuditAllowed** **e AuditDenied** per questa voce.</span><span class="sxs-lookup"><span data-stu-id="7dafc-193">4: disable **AuditAllowed** and **AuditDenied** for this Entry.</span></span> <span data-ttu-id="7dafc-194">Anche se **block** si verifica e **l'impostazione AuditDenied** è configurata, il sistema non mostrerà la notifica.</span><span class="sxs-lookup"><span data-stu-id="7dafc-194">Even if **Block** happens and the **AuditDenied** is setting configured, the system will not show notification.</span></span>

   <span data-ttu-id="7dafc-195">Quando è **selezionato Il tipo AuditAllowed** **o AuditDenied:**</span><span class="sxs-lookup"><span data-stu-id="7dafc-195">When Type **AuditAllowed** or **AuditDenied** is selected:</span></span>

   - <span data-ttu-id="7dafc-196">0: nothing</span><span class="sxs-lookup"><span data-stu-id="7dafc-196">0: nothing</span></span>
   - <span data-ttu-id="7dafc-197">1: mostra notifica</span><span class="sxs-lookup"><span data-stu-id="7dafc-197">1: show notification</span></span>
   - <span data-ttu-id="7dafc-198">2: invia evento</span><span class="sxs-lookup"><span data-stu-id="7dafc-198">2: send event</span></span>
   - <span data-ttu-id="7dafc-199">3: mostra evento di notifica e invio</span><span class="sxs-lookup"><span data-stu-id="7dafc-199">3: show notification and send event</span></span>

<span data-ttu-id="7dafc-200">**Nome proprietà: AccessMask**</span><span class="sxs-lookup"><span data-stu-id="7dafc-200">**Property name: AccessMask**</span></span>

1. <span data-ttu-id="7dafc-201">Descrizione: definisce l'accesso.</span><span class="sxs-lookup"><span data-stu-id="7dafc-201">Description: Defines the access.</span></span>

1. <span data-ttu-id="7dafc-202">Opzioni: 1-7:</span><span class="sxs-lookup"><span data-stu-id="7dafc-202">Options: 1-7:</span></span>
    - <span data-ttu-id="7dafc-203">1: Lettura</span><span class="sxs-lookup"><span data-stu-id="7dafc-203">1: Read</span></span>
    - <span data-ttu-id="7dafc-204">2: Scrittura</span><span class="sxs-lookup"><span data-stu-id="7dafc-204">2: Write</span></span>
    - <span data-ttu-id="7dafc-205">3: Lettura e scrittura</span><span class="sxs-lookup"><span data-stu-id="7dafc-205">3: Read and Write</span></span>
    - <span data-ttu-id="7dafc-206">4: Eseguire</span><span class="sxs-lookup"><span data-stu-id="7dafc-206">4: Execute</span></span>
    - <span data-ttu-id="7dafc-207">5: Lettura ed esecuzione</span><span class="sxs-lookup"><span data-stu-id="7dafc-207">5: Read and Execute</span></span>
    - <span data-ttu-id="7dafc-208">6: Scrittura ed esecuzione</span><span class="sxs-lookup"><span data-stu-id="7dafc-208">6: Write and Execute</span></span>
    - <span data-ttu-id="7dafc-209">7: Lettura ed scrittura ed esecuzione</span><span class="sxs-lookup"><span data-stu-id="7dafc-209">7: Read and Write and Execute</span></span>

## <a name="common-removable-storage-access-control-scenarios"></a><span data-ttu-id="7dafc-210">Scenari comuni di controllo di Archiviazione rimovibili</span><span class="sxs-lookup"><span data-stu-id="7dafc-210">Common Removable Storage Access Control scenarios</span></span>

<span data-ttu-id="7dafc-211">Per acquisire familiarità con Microsoft Defender for Endpoint Removable Archiviazione Access Control, abbiamo creato alcuni scenari comuni da seguire.</span><span class="sxs-lookup"><span data-stu-id="7dafc-211">To help familiarize you with Microsoft Defender for Endpoint Removable Storage Access Control, we have put together some common scenarios for you to follow.</span></span>

### <a name="scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs"></a><span data-ttu-id="7dafc-212">Scenario 1: Impedire l'accesso in scrittura ed esecuzione a tutti gli USB approvati specifici, ma consentirne l'esecuzione</span><span class="sxs-lookup"><span data-stu-id="7dafc-212">Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs</span></span>

1. <span data-ttu-id="7dafc-213">Creare gruppi</span><span class="sxs-lookup"><span data-stu-id="7dafc-213">Create groups</span></span>
    1. <span data-ttu-id="7dafc-214">Gruppo 1: qualsiasi archivio rimovibile e CD/DVD.</span><span class="sxs-lookup"><span data-stu-id="7dafc-214">Group 1: Any removable storage and CD/DVD.</span></span> <span data-ttu-id="7dafc-215">Un esempio di archiviazione rimovibile e CD/DVD è il gruppo **9b28fae8-72f7-4267-a1a5-685f747a7146 nell'esempio** [Any Removable Archiviazione and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span><span class="sxs-lookup"><span data-stu-id="7dafc-215">An example of a removable storage and CD/DVD is: Group **9b28fae8-72f7-4267-a1a5-685f747a7146** in the sample [Any Removable Storage and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="7dafc-216">Gruppo 2: USB approvati in base alle proprietà del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7dafc-216">Group 2: Approved USBs based on device properties.</span></span> <span data-ttu-id="7dafc-217">Un esempio per questo caso di utilizzo è: ID istanza - Gruppo **65fa649a-a111-4912-9294-fb6337a25038** nel file di esempio [approved usbs Group.xml.](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)</span><span class="sxs-lookup"><span data-stu-id="7dafc-217">An example for this use case is: Instance ID – Group **65fa649a-a111-4912-9294-fb6337a25038** in the sample [Approved USBs Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7dafc-218">È necessario sostituire `&` con `&amp;` nel valore.</span><span class="sxs-lookup"><span data-stu-id="7dafc-218">You have to replace `&` with `&amp;` in the value.</span></span>

2. <span data-ttu-id="7dafc-219">Creazione di un criterio</span><span class="sxs-lookup"><span data-stu-id="7dafc-219">Create policy</span></span>
    1. <span data-ttu-id="7dafc-220">Criterio 1: bloccare l'accesso in scrittura ed esecuzione, ma consentire gli USB approvati.</span><span class="sxs-lookup"><span data-stu-id="7dafc-220">Policy 1: Block Write and Execute Access but allow approved USBs.</span></span> <span data-ttu-id="7dafc-221">Un esempio per questo caso d'uso è: PolicyRule **c544a991-5786-4402-949e-a032cb790d0e** nell'esempio [Scenario 1 Block Write and Execute Access but allow approved USBs .xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span><span class="sxs-lookup"><span data-stu-id="7dafc-221">An example for this use case is: PolicyRule **c544a991-5786-4402-949e-a032cb790d0e** in the sample [Scenario 1 Block Write and Execute Access but allow approved USBs .xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="7dafc-222">Criterio 2: controlla l'accesso in scrittura ed esecuzione agli USB consentiti.</span><span class="sxs-lookup"><span data-stu-id="7dafc-222">Policy 2: Audit Write and Execute access to allowed USBs.</span></span> <span data-ttu-id="7dafc-223">Un esempio per questo caso di utilizzo è: PolicyRule **36ae1037-a639-4cff-946b-b36c53089a4c** nell'esempio [Scenario 1 Audit Write and Execute access to approved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span><span class="sxs-lookup"><span data-stu-id="7dafc-223">An example for this use case is: PolicyRule **36ae1037-a639-4cff-946b-b36c53089a4c** in the sample [Scenario 1 Audit Write and Execute access to approved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

### <a name="scenario-2-audit-write-and-execute-access-to-all-but-block-specific-unapproved-usbs"></a><span data-ttu-id="7dafc-224">Scenario 2: controllare l'accesso in scrittura ed esecuzione a tutti gli USB non approvati specifici, ma bloccarlo</span><span class="sxs-lookup"><span data-stu-id="7dafc-224">Scenario 2: Audit Write and Execute access to all but block specific unapproved USBs</span></span>

1. <span data-ttu-id="7dafc-225">Creare gruppi</span><span class="sxs-lookup"><span data-stu-id="7dafc-225">Create groups</span></span>
    1. <span data-ttu-id="7dafc-226">Gruppo 1: qualsiasi archivio rimovibile e CD/DVD.</span><span class="sxs-lookup"><span data-stu-id="7dafc-226">Group 1: Any removable storage and CD/DVD.</span></span> <span data-ttu-id="7dafc-227">Un esempio di questo caso di utilizzo è il gruppo **9b28fae8-72f7-4267-a1a5-685f747a7146 nell'esempio** [Any Removable Archiviazione and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span><span class="sxs-lookup"><span data-stu-id="7dafc-227">An example for this use case is: Group **9b28fae8-72f7-4267-a1a5-685f747a7146** in the sample [Any Removable Storage and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="7dafc-228">Gruppo 2: USB non approvati in base alle proprietà del dispositivo, ad esempio ID fornitore/ID prodotto, Nome descrittivo - Gruppo **65fa649a-a111-4912-9294-fb6337a25038** nel file di esempio [USBs non approvate Group.xml.](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)</span><span class="sxs-lookup"><span data-stu-id="7dafc-228">Group 2: Unapproved USBs based on device properties, for example, Vendor ID / Product ID, Friendly Name – Group **65fa649a-a111-4912-9294-fb6337a25038** in the sample [Unapproved USBs Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="7dafc-229">È necessario sostituire `&` con `&amp;` nel valore.</span><span class="sxs-lookup"><span data-stu-id="7dafc-229">You have to replace `&` with `&amp;` in the value.</span></span>

2. <span data-ttu-id="7dafc-230">Creazione di un criterio</span><span class="sxs-lookup"><span data-stu-id="7dafc-230">Create policy</span></span>
    1. <span data-ttu-id="7dafc-231">Criterio 1: Bloccare l'accesso in scrittura ed esecuzione a tutti gli USB non approvati specifici.</span><span class="sxs-lookup"><span data-stu-id="7dafc-231">Policy 1: Block Write and Execute access to all but block specific unapproved USBs.</span></span> <span data-ttu-id="7dafc-232">Un esempio di questo caso di utilizzo è: PolicyRule **23b8e437-66ac-4b32-b3d7-24044637fc98 nell'esempio** [Scenario 2 Audit Write and Execute access to all but block specific unapproved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span><span class="sxs-lookup"><span data-stu-id="7dafc-232">An example of this use case is: PolicyRule **23b8e437-66ac-4b32-b3d7-24044637fc98** in the sample [Scenario 2 Audit Write and Execute access to all but block specific unapproved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="7dafc-233">Criterio 2: controllare l'accesso in scrittura ed esecuzione ad altri utenti.</span><span class="sxs-lookup"><span data-stu-id="7dafc-233">Policy 2: Audit Write and Execute access to others.</span></span> <span data-ttu-id="7dafc-234">Un esempio di questo caso di utilizzo è: PolicyRule **b58ab853-9a6f-405c-a194-740e69422b48 nell'esempio** [Scenario 2 Audit Write and Execute access to others.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span><span class="sxs-lookup"><span data-stu-id="7dafc-234">An example of this use case is: PolicyRule **b58ab853-9a6f-405c-a194-740e69422b48** in the sample [Scenario 2 Audit Write and Execute access to others.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

## <a name="deploying-and-managing-policy-via-group-policy"></a><span data-ttu-id="7dafc-235">Distribuzione e gestione dei criteri tramite Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="7dafc-235">Deploying and managing policy via Group Policy</span></span>

<span data-ttu-id="7dafc-236">La funzionalità Controllo di Archiviazione rimovibili consente di applicare i criteri tramite Criteri di gruppo a un utente o a un dispositivo o a entrambi.</span><span class="sxs-lookup"><span data-stu-id="7dafc-236">The Removable Storage Access Control feature enables you to apply policy via Group Policy to either user or device, or both.</span></span>

### <a name="licensing"></a><span data-ttu-id="7dafc-237">Licenze</span><span class="sxs-lookup"><span data-stu-id="7dafc-237">Licensing</span></span>

<span data-ttu-id="7dafc-238">Prima di iniziare a utilizzare Removable Archiviazione Access Control, è necessario confermare [l'Microsoft 365 abbonamento.](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2)</span><span class="sxs-lookup"><span data-stu-id="7dafc-238">Before you get started with Removable Storage Access Control, you must confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2).</span></span> <span data-ttu-id="7dafc-239">Per accedere a Removable Archiviazione Access Control, è necessario disporre di Microsoft 365 E3 o Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="7dafc-239">To access and use Removable Storage Access Control, you must have Microsoft 365 E3 or Microsoft 365 E5.</span></span>

### <a name="deploying-policy-via-group-policy"></a><span data-ttu-id="7dafc-240">Distribuzione dei criteri tramite Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="7dafc-240">Deploying policy via Group Policy</span></span>

1. <span data-ttu-id="7dafc-241">Combina tutti i gruppi `<Groups>` `</Groups>` all'interno di un unico file XML.</span><span class="sxs-lookup"><span data-stu-id="7dafc-241">Combine all groups within `<Groups>` `</Groups>` into one xml file.</span></span> 

    <span data-ttu-id="7dafc-242">Nell'immagine seguente viene illustrato l'esempio dello [scenario 1: Impedire](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)l'accesso in scrittura ed esecuzione a tutti gli USB approvati specifici.</span><span class="sxs-lookup"><span data-stu-id="7dafc-242">The following image illustrates the example of [Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs).</span></span>
    
    :::image type="content" source="images/prevent-write-access-allow-usb.png" alt-text="Schermata che mostra le impostazioni di configurazione che consentono specifici USB approvati nei dispositivi":::
    
2. <span data-ttu-id="7dafc-244">Combina tutte le regole `<PolicyRules>` `</PolicyRules>` all'interno di un unico file XML.</span><span class="sxs-lookup"><span data-stu-id="7dafc-244">Combine all rules within `<PolicyRules>` `</PolicyRules>` into one xml file.</span></span> 

    <span data-ttu-id="7dafc-245">Se si desidera limitare un utente specifico, utilizzare la proprietà SID nell'oggetto Entry.</span><span class="sxs-lookup"><span data-stu-id="7dafc-245">If you want to restrict a specific user, then use SID property into the Entry.</span></span> <span data-ttu-id="7dafc-246">Se non è presente alcun SID nella voce del criterio, la voce verrà applicata a tutti gli utenti dell'istanza di accesso per il computer.</span><span class="sxs-lookup"><span data-stu-id="7dafc-246">If there is no SID in the policy Entry, the Entry will be applied to everyone login instance for the machine.</span></span>
    
    <span data-ttu-id="7dafc-247">Nell'immagine seguente viene illustrato l'utilizzo della proprietà SID e un esempio dello [scenario 1:](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)Impedire l'accesso in scrittura ed esecuzione a tutti gli USB approvati specifici.</span><span class="sxs-lookup"><span data-stu-id="7dafc-247">The following image illustrates the usage of SID property, and an example of [Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs).</span></span>
    
    :::image type="content" source="images/usage-sid-property.png" alt-text="Schermata che visualizza un codice che indica l'utilizzo dell'attributo della proprietà SID":::

3. <span data-ttu-id="7dafc-249">Salvare sia i file XML delle regole che dei gruppi nella cartella della condivisione di rete e inserire il percorso della cartella della condivisione di rete nell'impostazione di Criteri di gruppo: Configurazione computer -> Modelli amministrativi **-> Windows Componenti -> Antivirus Microsoft Defender -> Controllo dispositivi: "Definire** i gruppi di criteri di controllo dei dispositivi" e "Definire le regole dei criteri di controllo dei dispositivi".</span><span class="sxs-lookup"><span data-stu-id="7dafc-249">Save both rule and group XML files on network share folder and put network share folder path into the Group Policy setting: **Computer Configuration -> Administrative Templates -> Windows Components -> Microsoft Defender Antivirus -> Device Control: ‘Define device control policy groups’ and ‘Define device control policy rules’**.</span></span>

    - <span data-ttu-id="7dafc-250">Il computer di destinazione deve essere in grado di accedere alla condivisione di rete per disporre del criterio.</span><span class="sxs-lookup"><span data-stu-id="7dafc-250">The target machine must be able to access the network share to have the policy.</span></span> <span data-ttu-id="7dafc-251">Tuttavia, una volta letto il criterio, la connessione di condivisione di rete non è più necessaria, anche dopo il riavvio del computer.</span><span class="sxs-lookup"><span data-stu-id="7dafc-251">However, once the policy is read, the network share connection is no longer required, even after machine reboot.</span></span>

    :::image type="content" source="images/device-control.png" alt-text="Schermata Controllo dispositivo":::

## <a name="deploying-and-managing-policy-via-intune-oma-uri"></a><span data-ttu-id="7dafc-253">Distribuzione e gestione dei criteri tramite URI OMA di Intune</span><span class="sxs-lookup"><span data-stu-id="7dafc-253">Deploying and managing policy via Intune OMA-URI</span></span>

<span data-ttu-id="7dafc-254">La funzionalità Controllo di Archiviazione rimovibili consente di applicare i criteri tramite URI OMA a un utente o a un dispositivo o a entrambi.</span><span class="sxs-lookup"><span data-stu-id="7dafc-254">The Removable Storage Access Control feature enables you to apply policy via OMA-URI to either user or device, or both.</span></span>

### <a name="licensing"></a><span data-ttu-id="7dafc-255">Licenze</span><span class="sxs-lookup"><span data-stu-id="7dafc-255">Licensing</span></span>

<span data-ttu-id="7dafc-256">Prima di iniziare a utilizzare Removable Archiviazione Access Control, è necessario confermare [l'Microsoft 365 abbonamento.](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2)</span><span class="sxs-lookup"><span data-stu-id="7dafc-256">Before you get started with Removable Storage Access Control, you  must confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2).</span></span> <span data-ttu-id="7dafc-257">Per accedere a Removable Archiviazione Access Control, è necessario disporre di Microsoft 365 E3 o Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="7dafc-257">To access and use Removable Storage Access Control, you must have Microsoft 365 E3 or Microsoft 365 E5.</span></span>

### <a name="permission"></a><span data-ttu-id="7dafc-258">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="7dafc-258">Permission</span></span>

<span data-ttu-id="7dafc-259">Per la distribuzione dei criteri in Intune, l'account deve disporre delle autorizzazioni per creare, modificare, aggiornare o eliminare i profili di configurazione dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="7dafc-259">For policy deployment in Intune, the account must have permissions to create, edit, update, or delete device configuration profiles.</span></span> <span data-ttu-id="7dafc-260">È possibile creare ruoli personalizzati o utilizzare uno qualsiasi dei ruoli predefiniti con queste autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="7dafc-260">You can create custom roles or use any of the built-in roles with these permissions.</span></span>

- <span data-ttu-id="7dafc-261">Ruolo Gestione criteri e profili</span><span class="sxs-lookup"><span data-stu-id="7dafc-261">Policy and profile Manager role</span></span>
- <span data-ttu-id="7dafc-262">Ruolo personalizzato con autorizzazioni Create/Edit/Update/Read/Delete/View Reports attivate per i profili di configurazione dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="7dafc-262">Custom role with Create/Edit/Update/Read/Delete/View Reports permissions turned on for Device Configuration profiles</span></span>
- <span data-ttu-id="7dafc-263">Amministratore globale</span><span class="sxs-lookup"><span data-stu-id="7dafc-263">Global administrator</span></span>

### <a name="deploying-policy-via-oma-uri"></a><span data-ttu-id="7dafc-264">Distribuzione dei criteri tramite URI OMA</span><span class="sxs-lookup"><span data-stu-id="7dafc-264">Deploying policy via OMA-URI</span></span>

<span data-ttu-id="7dafc-265">**Microsoft Endpoint Manager di amministrazione ( https://endpoint.microsoft.com/) -> Devices -> Configuration profiles -> Create profile -> Platform: Windows 10 and later & Profile: Custom**</span><span class="sxs-lookup"><span data-stu-id="7dafc-265">**Microsoft Endpoint Manager admin center (https://endpoint.microsoft.com/) -> Devices -> Configuration profiles -> Create profile -> Platform: Windows 10 and later & Profile: Custom**</span></span>

1. <span data-ttu-id="7dafc-266">Per ogni gruppo, crea una regola URI OMA:</span><span class="sxs-lookup"><span data-stu-id="7dafc-266">For each Group, create an OMA-URI rule:</span></span>
    - <span data-ttu-id="7dafc-267">OMA-URI: </span><span class="sxs-lookup"><span data-stu-id="7dafc-267">OMA-URI:</span></span>

      <span data-ttu-id="7dafc-268">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b **GroupGUID**%7d/GroupData</span><span class="sxs-lookup"><span data-stu-id="7dafc-268">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b **GroupGUID**%7d/GroupData</span></span>

      <span data-ttu-id="7dafc-269">Ad esempio, per qualsiasi gruppo di archiviazione rimovibile e **CD/DVD** nell'esempio, il collegamento deve essere:</span><span class="sxs-lookup"><span data-stu-id="7dafc-269">For example, for **any removable storage and CD/DVD** group in the sample, the link must be:</span></span>

      <span data-ttu-id="7dafc-270">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b9b28fae8-72f7-4267-a1a5-685f747a7146%7d/GroupData</span><span class="sxs-lookup"><span data-stu-id="7dafc-270">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b9b28fae8-72f7-4267-a1a5-685f747a7146%7d/GroupData</span></span>

    - <span data-ttu-id="7dafc-271">Tipo di dati: String (file XML)</span><span class="sxs-lookup"><span data-stu-id="7dafc-271">Data Type: String (XML file)</span></span>
    
      :::image type="content" source="images/xml-data-type-string.png" alt-text="File XML per il tipo di dati STRING":::

2. <span data-ttu-id="7dafc-273">Per ogni criterio, crea anche un URI OMA:</span><span class="sxs-lookup"><span data-stu-id="7dafc-273">For each policy, also create an OMA-URI:</span></span>

    - <span data-ttu-id="7dafc-274">OMA-URI: </span><span class="sxs-lookup"><span data-stu-id="7dafc-274">OMA-URI:</span></span>

      <span data-ttu-id="7dafc-275">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bFA6BE102-0784-4A2A-B010-A0BEBEBF68E1%7d/RuleData</span><span class="sxs-lookup"><span data-stu-id="7dafc-275">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bFA6BE102-0784-4A2A-B010-A0BEBEBF68E1%7d/RuleData</span></span>

      <span data-ttu-id="7dafc-276">Ad esempio, per la regola Blocca scrittura ed esecuzione accesso ma consenti le **usbs** approvate nell'esempio, il collegamento deve essere:</span><span class="sxs-lookup"><span data-stu-id="7dafc-276">For example, for the **Block Write and Execute Access but allow approved USBs** rule in the sample, the link must be:</span></span> 

      <span data-ttu-id="7dafc-277">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bc544a991-5786-4402-949e-a032cb790d0e%7d/RuleData.</span><span class="sxs-lookup"><span data-stu-id="7dafc-277">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bc544a991-5786-4402-949e-a032cb790d0e%7d/RuleData.</span></span>

    - <span data-ttu-id="7dafc-278">Tipo di dati: String (file XML)</span><span class="sxs-lookup"><span data-stu-id="7dafc-278">Data Type: String (XML file)</span></span>

      :::image type="content" source="images/xml-data-type-string-2.png" lightbox="images/xml-data-type-string-2.png" alt-text="Visualizzazione del file XML per il tipo di dati STRING":::

## <a name="deploying-and-managing-policy-by-using-intune-user-interface"></a><span data-ttu-id="7dafc-280">Distribuzione e gestione dei criteri tramite l'interfaccia utente di Intune</span><span class="sxs-lookup"><span data-stu-id="7dafc-280">Deploying and managing policy by using Intune user interface</span></span>

<span data-ttu-id="7dafc-281">Questa funzionalità (nell'interfaccia di amministrazione di Microsoft Endpoint Manager ( > https://endpoint.microsoft.com/) Devices > Configuration profiles > Create profile > Platform: Windows 10 and later & Profile: Device Control) non è ancora disponibile.</span><span class="sxs-lookup"><span data-stu-id="7dafc-281">This capability (in Microsoft Endpoint Manager admin center (https://endpoint.microsoft.com/) > Devices > Configuration profiles > Create profile > Platform: Windows 10 and later & Profile: Device Control) is not yet available.</span></span> 

## <a name="view-device-control-removable-storage-access-control-data-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="7dafc-282">Visualizzare i dati di controllo Archiviazione di accesso rimovibili in Microsoft Defender per Endpoint</span><span class="sxs-lookup"><span data-stu-id="7dafc-282">View Device Control Removable Storage Access Control data in Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="7dafc-283">Il portale Microsoft 365 sicurezza mostra l'archiviazione rimovibile bloccata dal Controllo dispositivo Rimovibile Archiviazione Access Control.</span><span class="sxs-lookup"><span data-stu-id="7dafc-283">The Microsoft 365 security portal shows removable storage blocked by the Device Control Removable Storage Access Control.</span></span> <span data-ttu-id="7dafc-284">Per accedere alla Microsoft 365 sicurezza, è necessario disporre dell'abbonamento seguente:</span><span class="sxs-lookup"><span data-stu-id="7dafc-284">To access the Microsoft 365 security, you must have the following subscription:</span></span>

- <span data-ttu-id="7dafc-285">Microsoft 365 per la creazione di report E5</span><span class="sxs-lookup"><span data-stu-id="7dafc-285">Microsoft 365 for E5 reporting</span></span>

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
