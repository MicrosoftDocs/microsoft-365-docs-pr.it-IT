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
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-protection"></a>Microsoft Defender per Endpoint Device Control Removable Archiviazione Protection

[!INCLUDE [Prerelease](../includes/prerelease.md)]

Microsoft Defender for Endpoint Device Control Removable Archiviazione Protection impedisce a utenti o computer o a entrambi di utilizzare supporti di archiviazione rimovibili non autorizzati.

## <a name="protection-policies"></a>Criteri di protezione

### <a name="device-installation"></a>Installazione del dispositivo

**Funzionalità:** impedisci l'installazione con o senza esclusione in base a diverse proprietà del dispositivo.

**Descrizione**
- Applicato a livello di computer: lo stesso criterio si applica a qualsiasi utente connesso.
- Supporta MEM e GPO.
- Supportato '[Proprietà dispositivo](#device-properties)' come elencato.
- Per altre informazioni su Windows, vedi Come controllare i dispositivi USB e altri supporti [rimovibili con Microsoft Defender for Endpoint.](control-usb-devices-using-intune.md)

**Piattaforma supportata** - Windows 10

**Descrizione**
- Applicato a livello di computer: lo stesso criterio si applica a qualsiasi utente connesso
- Per informazioni specifiche su macOS, vedi [Controllo dispositivo per macOS.](mac-device-control-overview.md)
 
**Piattaforma supportata** - macOS Catalina 10.15.4+ (con le estensioni di sistema abilitate)

### <a name="removable-storage-access-control"></a>Controllo di accesso all'archiviazione rimovibile

**Funzionalità**
- *Controllo* Accesso in lettura o scrittura o esecuzione all'archiviazione rimovibile in base a diverse proprietà del dispositivo, con o senza esclusione.
- *Impedisci* Accesso in lettura o scrittura o in esecuzione con o senza esclusione: consentire un dispositivo specifico in base a diverse proprietà del dispositivo.

**Descrizione**
- Applicato a un computer o a un utente o a entrambi: consente solo a utenti specifici che eseguono l'accesso in lettura/scrittura/esecuzione a uno specifico spazio di archiviazione rimovibile in un computer specifico.
- Supporta l'URI OMA e l'oggetto Criteri di gruppo MEM.
- Supportato '[Proprietà dispositivo](#device-properties)' come elencato.
- Per la funzionalità in Windows, vedere [Removable storage Access Control](device-control-removable-storage-access-control.md).

**Piattaforma supportata** - Windows 10

**Descrizione**
- Applicato a livello di computer: lo stesso criterio si applica a qualsiasi utente connesso.
- Per informazioni specifiche su macOS, vedi [Controllo dispositivo per macOS.](mac-device-control-overview.md)
 
**Piattaforma supportata** - macOS Catalina 10.15.4+ (con le estensioni di sistema abilitate)

### <a name="windows-portable-device-access-control"></a>Windows Controllo di accesso dei dispositivi portatili

**Funzionalità** : nega l'accesso in lettura o scrittura [Windows qualsiasi](/windows-hardware/drivers/portable/)dispositivo portatile, ad esempio Tablet, iPhone.

**Descrizione**
- Applicato a un computer o a un utente o a entrambi.
- Supporta l'URI OMA e l'oggetto Criteri di gruppo MEM.

**Piattaforma supportata** - Windows 10

### <a name="endpoint-dlp-removable-storage"></a>Endpoint DLP Archivi rimovibili

**Funzionalità:** controlla o avvisa o impedisci a un utente di copiare un elemento o informazioni in un supporto rimovibile o in un dispositivo USB.

**Descrizione-** Per ulteriori informazioni su Windows, vedere Informazioni sulla prevenzione della perdita di dati Microsoft 365 [endpoint.](../../compliance/endpoint-dlp-learn-about.md)

**Piattaforma supportata** - Windows 10

### <a name="bitlocker"></a>BitLocker 

**Funzionalità**
- Bloccare i dati da scrivere in unità rimovibili non BitLocker protette.
- Bloccare l'accesso alle unità rimovibili a meno che non siano state crittografate in un computer di proprietà dell'organizzazione
 
**Descrizione** - Per ulteriori informazioni su Windows, [vedere BitLocker – Removable Drive Impostazioni](/mem/intune/protect/endpoint-security-disk-encryption-profile-settings).

**Piattaforma supportata** - Windows 10

## <a name="device-properties"></a>Proprietà del dispositivo

Microsoft Defender for Endpoint Device Control Removable Archiviazione Protection consente di limitare l'accesso all'archiviazione rimovibile in base alle proprietà descritte nella tabella seguente:


|Nome proprietà  |Criteri applicabili  |Si applica ai sistemi operativi  |Descrizione  |
|---------|---------|---------|---------|
|Classe Device    |     [Come controllare i dispositivi USB e altri supporti rimovibili con Microsoft Defender for Endpoint](control-usb-devices-using-intune.md)     |   Windows      |  Per informazioni sui formati dell'ID dispositivo, vedi [classe di configurazione del dispositivo.](/windows-hardware/drivers/install/system-defined-device-setup-classes-available-to-vendors) **Nota:** l'installazione dei dispositivi può essere applicata a qualsiasi dispositivo, non solo all'archiviazione rimovibile.       |
|ID primario   |     Controllo di accesso all'archiviazione rimovibile    |   Windows      |      L'ID primario include l'archiviazione rimovibile e il CD/DVD.   |
|ID dispositivo     |  [Come controllare i dispositivi USB e altri supporti rimovibili con Microsoft Defender for Endpoint;](control-usb-devices-using-intune.md) Controllo di accesso all'archiviazione rimovibile       |      Windows   |    Per informazioni sui formati id dispositivo, vedere [Identificatori USB standard,](/windows-hardware/drivers/install/standard-usb-identifiers)ad esempio USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07      |
|Hardware ID     |     [Come controllare i dispositivi USB e altri supporti rimovibili con Microsoft Defender for Endpoint;](control-usb-devices-using-intune.md) Controllo di accesso all'archiviazione rimovibile    |     Windows    |    Stringa che identifica il dispositivo nel sistema, ad esempio USBSTOR\DiskGeneric_Flash_Disk______8.07; **Nota:** l'ID hardware non è univoco. dispositivi diversi possono condividere lo stesso valore.|
|ID istanza    | Installazione del dispositivo; Controllo di accesso all'archiviazione rimovibile     |     Windows    |   Una stringa identifica in modo univoco il dispositivo nel sistema, ad esempio USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0      |
|Nome descrittivo     |     Controllo di accesso all'archiviazione rimovibile    |   Windows      |    Stringa collegata al dispositivo, ad esempio Dispositivo USB generico flash disk     |
|ID fornitore/ID prodotto     |  Controllo di accesso all'archiviazione rimovibile       |   Windows Mac      |     ID fornitore è il codice fornitore a quattro cifre che il comitato USB assegna al fornitore. ID prodotto è il codice prodotto a quattro cifre che il fornitore assegna al dispositivo. Supportare il carattere jolly.    |
|Serial NumberId     |     Controllo di accesso all'archiviazione rimovibile    |      Windows Mac   |     Ad esempio, <SerialNumberId>002324B534BCB431B000058A</SerialNumberId>    |

## <a name="related-topic"></a>Argomento correlato

- [Microsoft Defender for Endpoint Device Control Removable Archiviazione Access Control](device-control-removable-storage-access-control.md)

