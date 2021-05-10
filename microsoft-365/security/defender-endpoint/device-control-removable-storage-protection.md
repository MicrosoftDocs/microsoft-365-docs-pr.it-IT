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
ms.openlocfilehash: ec5cfa78852d65db808c4e853f90f5639df25d6f
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/10/2021
ms.locfileid: "52300207"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-protection"></a>Microsoft Defender per Endpoint Device Control Removable Archiviazione Protection

[!INCLUDE [Prerelease](../includes/prerelease.md)]

Microsoft Defender for Endpoint Device Control Removable Archiviazione Protection impedisce a utenti o computer o a entrambi di utilizzare supporti di archiviazione rimovibili non autorizzati.

**Microsoft Defender per Endpoint Removable Archiviazione Protection**


|Criteri  |Funzionalità |Descrizione  |
|---------|---------|---------|
|Installazione dispositivo    |  Impedisci l'installazione con o senza esclusione - Consenti dispositivi specifici in base a diverse proprietà; per altre informazioni, vedi la sezione [Proprietà del dispositivo](#device-properties) di seguito.        |    Funziona nel computer: gli utenti diversi che a questo accederanno saranno limitati dallo stesso criterio. Per informazioni, vedi Come controllare i dispositivi USB e altri supporti [rimovibili con Microsoft Defender for Endpoint.](control-usb-devices-using-intune.md)     |
|Controllo di accesso all'archiviazione rimovibile      | (1) Controllare l'accesso in lettura o scrittura o esecuzione all'archiviazione rimovibile in base a diverse proprietà del dispositivo, con o senza eccezione. Per altre informazioni, vedi la sezione [Proprietà dispositivo](#device-properties) di seguito. (2) Impedire l'accesso in lettura o scrittura o in esecuzione con o senza esclusione - Consentire dispositivi specifici in base a diverse proprietà del dispositivo; per altre informazioni sulle proprietà del dispositivo, vedi la sezione [Proprietà dispositivo](#device-properties) di seguito.     |     Funziona su computer o utenti o su entrambi: consente solo a utenti specifici che eseguono l'accesso in lettura/scrittura/esecuzione a uno specifico spazio di archiviazione rimovibile in un computer specifico; per la funzionalità in Windows, vedere [Removable storage Access Control](device-control-removable-storage-access-control.md); per le funzionalità in Mac, vedi [Controllo dispositivo per macOS.](mac-device-control-overview.md)     |
|Endpoint DLP Archivi rimovibili      |    Controlla o avvisa o impedisci a un utente di copiare un elemento o informazioni su supporti rimovibili o su un dispositivo USB.     |  Per ulteriori informazioni, vedere [Microsoft Endpoint DLP](/compliance/endpoint-dlp-learn-about.md).       |
|BitLocker    |     Bloccare i dati che devono essere scritti in unità rimovibili che non sono BitLocker protette: bloccare l'accesso alle unità rimovibili a meno che non siano state crittografate in un computer di proprietà dell'organizzazione.    |   Per ulteriori informazioni, vedere BitLocker – [Removable Drive Impostazioni](/mem/intune/protect/endpoint-security-disk-encryption-profile-settings#bitlocker---removable-drive-settings.md).      |

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
