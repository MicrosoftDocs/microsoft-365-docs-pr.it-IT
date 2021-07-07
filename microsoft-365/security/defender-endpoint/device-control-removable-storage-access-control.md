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
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-access-control"></a>Microsoft Defender for Endpoint Device Control Removable Archiviazione Access Control

[!INCLUDE [Prerelease](../includes/prerelease.md)]

Microsoft Defender for Endpoint Device Control Removable Archiviazione Access Control consente di eseguire l'attività seguente:

- controllo, consentendo o impedendo l'accesso in lettura, scrittura o esecuzione all'archiviazione rimovibile con o senza esclusione

|Privilegio |Autorizzazione  |
|---------|---------|
|Access    |  Lettura, scrittura ed esecuzione       |
|Modalità azione    |    Controllo, Consenti, Impedisci     |
|Supporto CSP   |   Sì      |
|Supporto oggetti Criteri di gruppo    |   Sì      |
|Supporto basato sull'utente     |   Sì      |
|Supporto basato su computer    |    Sì     |

## <a name="prepare-your-endpoints"></a>Preparare gli endpoint

Distribuire Il controllo di accesso Archiviazione rimovibili nei dispositivi Windows 10 con client antimalware **versione 4.18.2103.3 o successiva.**

- **4.18.2104 o** versione successiva : Aggiungere SerialNumberId, VID_PID, supporto dell'oggetto Criteri di gruppo basato su filepath, ComputerSid

- **4.18.2105 o** versione successiva : Aggiungere il supporto dei caratteri jolly per HardwareId/DeviceId/InstancePathId/FriendlyNameId/SerialNumberId, la combinazione di un utente specifico in un computer specifico, SSD rimovibile (un SSD SanDisk Extreme)/supporto USB Attached SCSI (UAS)

- **4.18.2107** o versione successiva : Aggiungere il supporto di Windows Portable Device (WPD) (per dispositivi mobili, ad esempio tablet)

:::image type="content" source="images/powershell.png" alt-text="Interfaccia di PowerShell":::

> [!NOTE]
> Nessuno dei Sicurezza di Windows deve essere attivo, è possibile eseguire Removable Archiviazione Access Control indipendentemente Sicurezza di Windows stato.

## <a name="policy-properties"></a>Proprietà dei criteri

È possibile utilizzare le proprietà seguenti per creare un gruppo di archiviazione rimovibile:

**Nome proprietà: ID gruppo**

1. Descrizione: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), un ID univoco, rappresenta il gruppo e verrà utilizzato nel criterio.

**Nome proprietà: DescriptorIdList**

2. Descrizione: elenca le proprietà del dispositivo che vuoi usare per coprire il gruppo.
Per ogni proprietà del dispositivo, vedi **la sezione Proprietà dispositivo** sopra riportata per ulteriori dettagli.

3. Opzioni:
    - PrimaryId
        - RemovableMediaDevices
        - CdRomDevices
        - WpdDevices
    - DeviceId
    - HardwareId
    - InstancePathId: InstancePathId è una stringa che identifica in modo univoco il dispositivo nel sistema, ad esempio USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0. Il numero alla fine (ad esempio **&0)** rappresenta lo slot disponibile e può cambiare da dispositivo a dispositivo. Per ottenere risultati ottimali, utilizzare un carattere jolly alla fine. Ad esempio, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611*
    - FriendlyNameId
    - SerialNumberId
    - VID
    - PID
    - VID_PID
        - 0751_55E0: corrisponde a questa coppia VID/PID esatta
        - _55E0: corrisponde a qualsiasi supporto con PID=55E0
        - 0751_: corrisponde a qualsiasi supporto con VID=0751
        
**Nome proprietà: MatchType** 

1. Descrizione: quando in DescriptorIDList vengono utilizzate più proprietà del dispositivo, MatchType definisce la relazione.

2. Opzioni:

    - MatchAll: tutti gli attributi in DescriptorIdList saranno **relazione And.** Ad esempio, se l'amministratore inserisce DeviceID e InstancePathID per ogni USB connesso, il sistema controllera' se l'USB soddisfa entrambi i valori.
    - MatchAny: gli attributi sotto DescriptorIdList saranno **relazione Or.** Ad esempio, se l'amministratore inserisce DeviceID e InstancePathID, per ogni USB connessa, il sistema farà l'imposizione purché l'USB abbia un **valore DeviceID** o **InstanceID** identico.

Di seguito sono riportate le proprietà dei criteri di controllo di accesso:

**Nome proprietà: PolicyRuleId**

1. Descrizione: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), un ID univoco, rappresenta il criterio e verrà utilizzato nei report e nella risoluzione dei problemi.

**Nome proprietà: IncludedIdList**

1. Descrizione: i gruppi a cui verrà applicato il criterio. Se vengono aggiunti più gruppi, il criterio verrà applicato a tutti i supporti di tutti i gruppi.

2. Opzioni: l'ID gruppo/GUID deve essere utilizzato in questa istanza.

Nell'esempio seguente viene illustrato l'utilizzo di GroupID:

`<IncludedIdList> <GroupId>{EAA4CCE5-F6C9-4760-8BAD-FDCC76A2ACA1}</GroupId> </IncludedIdList>`

**Nome proprietà: ExcludedIDList**

Descrizione: i gruppi a cui non verrà applicato il criterio.

Opzioni: l'ID gruppo/GUID deve essere utilizzato in questa istanza.

**Nome proprietà: Id voce**

1. Descrizione: Un oggetto PolicyRule può avere più voci. ogni voce con un GUID univoco indica a Device Control una restrizione.

**Nome proprietà: Type**

1. Descrizione: definisce l'azione per i gruppi di archiviazione rimovibili in IncludedIDList.
    - Imposizione: Consenti o Nega
    - Controllo: AuditAllowed o AuditDenied 

2. Opzioni:

    - Consenti
    - Nega
    - AuditAllowed: definisce la notifica e l'evento quando è consentito l'accesso
    - AuditDenied: definisce la notifica e l'evento quando l'accesso viene negato. deve collaborare con **la voce** Deny.

Quando sono presenti tipi di conflitto per lo stesso supporto, il sistema applierà il primo nel criterio. Un esempio di tipo di conflitto è **Allow** e **Deny.**

**Nome proprietà: Sid**

Descrizione: il Sid del computer locale o il Sid dell'oggetto AD, definisce se applicare questo criterio a un utente o a un gruppo di utenti specifico. una voce può avere un massimo di un Sid e una voce senza sid significa applicare il criterio sul computer.

**Nome proprietà: ComputerSid**

Descrizione: il Sid del computer locale o il Sid dell'oggetto AD, definisce se applicare questo criterio a un computer o a un gruppo di computer specifico; una voce può avere un massimo di un ComputerSid e una voce senza ComputerSid significa applicare il criterio sul computer. Se si desidera applicare una voce a un utente specifico e a un computer specifico, aggiungere sia Sid che ComputerSid nella stessa voce.

**Nome proprietà: Opzioni**

Descrizione: definisce se visualizzare o meno la notifica.

   :::image type="content" source="images/device-status.png" alt-text="Schermata in cui è possibile visualizzare lo stato del dispositivo":::

Opzioni: 0-4. Quando è selezionata l'opzione Digitazione Consenti o Nega:

   - 0: nothing
   - 4: **disabilitare AuditAllowed** **e AuditDenied** per questa voce. Anche se **block** si verifica e **l'impostazione AuditDenied** è configurata, il sistema non mostrerà la notifica.

   Quando è **selezionato Il tipo AuditAllowed** **o AuditDenied:**

   - 0: nothing
   - 1: mostra notifica
   - 2: invia evento
   - 3: mostra evento di notifica e invio

**Nome proprietà: AccessMask**

Descrizione: definisce l'accesso.

Opzioni 1-7:
  - 1: Lettura
  - 2: Scrittura
  - 3: Lettura e scrittura
  - 4: Eseguire
  - 5: Lettura ed esecuzione
  - 6: Scrittura ed esecuzione
  - 7: Lettura ed scrittura ed esecuzione

## <a name="common-removable-storage-access-control-scenarios"></a>Scenari comuni di controllo di Archiviazione rimovibili

Per acquisire familiarità con Microsoft Defender for Endpoint Removable Archiviazione Access Control, abbiamo creato alcuni scenari comuni da seguire.

### <a name="scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs"></a>Scenario 1: Impedire l'accesso in scrittura ed esecuzione a tutti gli USB approvati specifici, ma consentirne l'esecuzione

1. Creare gruppi

    1. Gruppo 1: qualsiasi archivio rimovibile e CD/DVD. Un esempio di archiviazione rimovibile e CD/DVD è il gruppo **9b28fae8-72f7-4267-a1a5-685f747a7146 nell'esempio** [Any Removable Archiviazione and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.
    
    2. Gruppo 2: USB approvati in base alle proprietà del dispositivo. Un esempio per questo caso di utilizzo è: ID istanza - Gruppo **65fa649a-a111-4912-9294-fb6337a25038** nel file di esempio [approved usbs Group.xml.](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)

    > [!NOTE]
    > È necessario sostituire `&` con `&amp;` nel valore.

2. Creazione di un criterio

    1. Criterio 1: bloccare l'accesso in scrittura ed esecuzione, ma consentire gli USB approvati. Un esempio per questo caso d'uso è: PolicyRule **c544a991-5786-4402-949e-a032cb790d0e** nell'esempio [Scenario 1 Block Write and Execute Access but allow approved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.
    
    2. Criterio 2: controlla l'accesso in scrittura ed esecuzione agli USB consentiti. Un esempio per questo caso di utilizzo è: PolicyRule **36ae1037-a639-4cff-946b-b36c53089a4c** nell'esempio [Scenario 1 Audit Write and Execute access to approved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.

### <a name="scenario-2-audit-write-and-execute-access-to-all-but-block-specific-unapproved-usbs"></a>Scenario 2: controllare l'accesso in scrittura ed esecuzione a tutti gli USB non approvati specifici, ma bloccarlo

1. Creare gruppi

    1. Gruppo 1: qualsiasi archivio rimovibile e CD/DVD. Un esempio di questo caso di utilizzo è il gruppo **9b28fae8-72f7-4267-a1a5-685f747a7146 nell'esempio** [Any Removable Archiviazione and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.
    
    2. Gruppo 2: USB non approvati in base alle proprietà del dispositivo, ad esempio ID fornitore/ID prodotto, Nome descrittivo - Gruppo **65fa649a-a111-4912-9294-fb6337a25038** nel file di esempio [USBs non approvate Group.xml.](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) 

    > [!NOTE]
    > È necessario sostituire `&` con `&amp;` nel valore.

2. Creazione di un criterio

    1. Criterio 1: Bloccare l'accesso in scrittura ed esecuzione a tutti gli USB non approvati specifici. Un esempio di questo caso di utilizzo è: PolicyRule **23b8e437-66ac-4b32-b3d7-24044637fc98 nell'esempio** [Scenario 2 Audit Write and Execute access to all but block specific unapproved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.
    
    2. Criterio 2: controllare l'accesso in scrittura ed esecuzione ad altri utenti. Un esempio di questo caso di utilizzo è: PolicyRule **b58ab853-9a6f-405c-a194-740e69422b48 nell'esempio** [Scenario 2 Audit Write and Execute access to others.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.

## <a name="deploying-and-managing-policy-via-group-policy"></a>Distribuzione e gestione dei criteri tramite Criteri di gruppo

La funzionalità Controllo di Archiviazione rimovibili consente di applicare i criteri tramite Criteri di gruppo a un utente o a un dispositivo o a entrambi.

### <a name="licensing"></a>Licenze

Prima di iniziare a utilizzare Removable Archiviazione Access Control, è necessario confermare [l'Microsoft 365 abbonamento.](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2) Per accedere a Removable Archiviazione Access Control, è necessario disporre di Microsoft 365 E3 o Microsoft 365 E5.

### <a name="deploying-policy-via-group-policy"></a>Distribuzione dei criteri tramite Criteri di gruppo

1. Combina tutti i gruppi `<Groups>` `</Groups>` all'interno di un unico file XML. 

    Nell'immagine seguente viene illustrato l'esempio dello [scenario 1: Impedire](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)l'accesso in scrittura ed esecuzione a tutti gli USB approvati specifici.
    
    :::image type="content" source="images/prevent-write-access-allow-usb.png" alt-text="Schermata che mostra le impostazioni di configurazione che consentono specifici USB approvati nei dispositivi":::
    
2. Combina tutte le regole `<PolicyRules>` `</PolicyRules>` all'interno di un unico file XML. 

    Se si desidera limitare un utente specifico, utilizzare la proprietà SID nell'oggetto Entry. Se non è presente alcun SID nella voce del criterio, la voce verrà applicata a tutti gli utenti dell'istanza di accesso per il computer.
    
    Nell'immagine seguente viene illustrato l'utilizzo della proprietà SID e un esempio dello [scenario 1:](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)Impedire l'accesso in scrittura ed esecuzione a tutti gli USB approvati specifici.
    
    :::image type="content" source="images/usage-sid-property.png" alt-text="Schermata che visualizza un codice che indica l'utilizzo dell'attributo della proprietà SID":::

3. Salvare sia i file XML delle regole che dei gruppi nella cartella della condivisione di rete e inserire il percorso della cartella della condivisione di rete nell'impostazione di Criteri di gruppo: Configurazione computer -> Modelli amministrativi **-> Windows Componenti -> Antivirus Microsoft Defender -> Controllo dispositivi: "Definire** i gruppi di criteri di controllo dei dispositivi" e "Definire le regole dei criteri di controllo dei dispositivi".

    - Il computer di destinazione deve essere in grado di accedere alla condivisione di rete per disporre del criterio. Tuttavia, una volta letto il criterio, la connessione di condivisione di rete non è più necessaria, anche dopo il riavvio del computer.

    :::image type="content" source="images/device-control.png" alt-text="Schermata Controllo dispositivo":::

## <a name="deploying-and-managing-policy-via-intune-oma-uri"></a>Distribuzione e gestione dei criteri tramite URI OMA di Intune

La funzionalità Controllo di Archiviazione rimovibili consente di applicare i criteri tramite URI OMA a un utente o a un dispositivo o a entrambi.

### <a name="licensing"></a>Licenze

Prima di iniziare a utilizzare Removable Archiviazione Access Control, è necessario confermare [l'Microsoft 365 abbonamento.](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2) Per accedere a Removable Archiviazione Access Control, è necessario disporre di Microsoft 365 E3 o Microsoft 365 E5.

### <a name="permission"></a>Autorizzazione

Per la distribuzione dei criteri in Intune, l'account deve disporre delle autorizzazioni per creare, modificare, aggiornare o eliminare i profili di configurazione dei dispositivi. È possibile creare ruoli personalizzati o utilizzare uno qualsiasi dei ruoli predefiniti con queste autorizzazioni.

- Ruolo Gestione criteri e profili
- Ruolo personalizzato con autorizzazioni Create/Edit/Update/Read/Delete/View Reports attivate per i profili di configurazione dei dispositivi
- Amministratore globale

### <a name="deploying-policy-via-oma-uri"></a>Distribuzione dei criteri tramite URI OMA

**Microsoft Endpoint Manager di amministrazione ( https://endpoint.microsoft.com/) -> Devices -> Configuration profiles -> Create profile -> Platform: Windows 10 and later & Profile: Custom**

1. Per ogni gruppo, crea una regola URI OMA:
    - OMA-URI: 

      ./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b **GroupGUID**%7d/GroupData

      Ad esempio, per qualsiasi gruppo di archiviazione rimovibile e **CD/DVD** nell'esempio, il collegamento deve essere:

      ./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b9b28fae8-72f7-4267-a1a5-685f747a7146%7d/GroupData

    - Tipo di dati: String (file XML)
    
      :::image type="content" source="images/xml-data-type-string.png" alt-text="File XML per il tipo di dati STRING":::

2. Per ogni criterio, crea anche un URI OMA:

    - OMA-URI: 

      ./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bFA6BE102-0784-4A2A-B010-A0BEBEBF68E1%7d/RuleData

      Ad esempio, per la regola Blocca scrittura ed esecuzione accesso ma consenti le **usbs** approvate nell'esempio, il collegamento deve essere: 

      ./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bc544a991-5786-4402-949e-a032cb790d0e%7d/RuleData.

    - Tipo di dati: String (file XML)

      :::image type="content" source="images/xml-data-type-string-2.png" lightbox="images/xml-data-type-string-2.png" alt-text="Visualizzazione del file XML per il tipo di dati STRING":::

## <a name="deploying-and-managing-policy-by-using-intune-user-interface"></a>Distribuzione e gestione dei criteri tramite l'interfaccia utente di Intune

Questa funzionalità (nell'interfaccia di amministrazione di Microsoft Endpoint Manager ( > https://endpoint.microsoft.com/) Devices > Configuration profiles > Create profile > Platform: Windows 10 and later & Profile: Device Control) non è ancora disponibile. 

## <a name="view-device-control-removable-storage-access-control-data-in-microsoft-defender-for-endpoint"></a>Visualizzare i dati di controllo Archiviazione di accesso rimovibili in Microsoft Defender per Endpoint

Il portale Microsoft 365 sicurezza mostra l'archiviazione rimovibile bloccata dal Controllo dispositivo Rimovibile Archiviazione Access Control. Per accedere alla Microsoft 365 sicurezza, è necessario disporre dell'abbonamento seguente:

- Microsoft 365 per la creazione di report E5

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

## <a name="frequently-asked-questions"></a>Domande frequenti

**Qual è la limitazione del supporto di archiviazione rimovibile per il numero massimo di USB?**

È stato convalidato un gruppo USB con 100.000 supporti, fino a 7 MB. Il criterio funziona sia in Intune che negli oggetti Criteri di gruppo senza problemi di prestazioni.

**Perché il criterio non funziona?**

Il motivo più comune è che non esiste una versione [client antimalware necessaria.](/microsoft-365/security/defender-endpoint/device-control-removable-storage-access-control#prepare-your-endpoints)

Un altro motivo potrebbe essere che il file XML non è formattato correttamente, ad esempio, non utilizzando la formattazione markdown corretta per il carattere "&" nel file XML oppure l'editor di testo potrebbe aggiungere un indicatore dell'ordine dei byte (BOM) 0xEF 0xBB 0xBF all'inizio dei file che causa il non funzionamento dell'analisi XML. Una soluzione semplice consiste nel scaricare il [file di](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) esempio (selezionare **Raw** e quindi **Salva con** nome ) e quindi aggiornare.

Se è presente un valore e il criterio viene gestito tramite Criteri di gruppo, verificare se il dispositivo client può accedere al percorso XML dei criteri.

**Come è possibile sapere quale computer utilizza una versione client antimalware non aggiornata nell'organizzazione?**

È possibile utilizzare la query seguente per ottenere la versione del client antimalware nel portale Microsoft 365 sicurezza:
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
