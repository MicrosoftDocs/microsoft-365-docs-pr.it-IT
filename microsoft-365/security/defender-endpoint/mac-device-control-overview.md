---
title: Controllo dispositivo per macOS
description: Scopri come configurare Microsoft Defender per Endpoint su Mac per ridurre le minacce da archivi rimovibili, ad esempio dispositivi USB.
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, dispositivo, controllo, usb, rimovibile, supporto
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: security
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
ms.openlocfilehash: 682f59729e06c63818491ad7540528d574380c8b
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2021
ms.locfileid: "52877837"
---
# <a name="device-control-for-macos"></a>Controllo dispositivo per macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="requirements"></a>Requisiti

Il controllo del dispositivo per macOS presenta i prerequisiti seguenti:

>[!div class="checklist"]
> - Diritto di Microsoft Defender for Endpoint (può essere di prova)
> - Versione minima del sistema operativo: macOS 10.15.4 o versione successiva
> - Versione minima del prodotto: 101.24.59
> - Il dispositivo deve essere in esecuzione con estensioni di sistema (questa è l'impostazione predefinita in macOS 11 Big Sur). 
> 
>   Puoi verificare se il dispositivo è in esecuzione su estensioni di sistema eseguendo il comando seguente e verifica che sia in `endpoint_security_extension` stampa nella console: 
> 
>   ```bash
>   mdatp health --field real_time_protection_subsystem 
>   ```
> - Il dispositivo deve essere nel `Beta` canale di aggiornamento Microsoft AutoUpdate (denominato in `InsiderFast` precedenza). Per altre informazioni, vedi [Distribuire gli aggiornamenti per Microsoft Defender per Endpoint su Mac.](mac-updates.md)
> 
>   Puoi controllare il canale di aggiornamento usando il comando seguente: 
> 
>    ```bash
>    mdatp health --field release_ring 
>    ```
>
>    Se il comando precedente non stampa o `Beta` , eseguire il comando seguente dal `InsiderFast` terminale. L'aggiornamento del canale ha effetto al successivo avvio del prodotto (quando viene installato il successivo aggiornamento del prodotto o quando il dispositivo viene riavviato). 
> 
>    ```bash
>    defaults write com.microsoft.autoupdate2 ChannelName -string Beta
>    ```
>
>    In alternativa, se si è in un ambiente gestito (JAMF o Intune), è possibile configurare il canale di aggiornamento in remoto. Per altre informazioni, vedi [Distribuire gli aggiornamenti per Microsoft Defender per Endpoint su Mac.](mac-updates.md) 

## <a name="device-control-policy"></a>Criteri di controllo dei dispositivi

Per configurare il controllo dei dispositivi per macOS, devi creare un criterio che descriva le restrizioni che vuoi applicare all'interno dell'organizzazione.

Il criterio di controllo dei dispositivi è incluso nel profilo di configurazione usato per configurare tutte le altre impostazioni del prodotto. Per ulteriori informazioni, vedere [Struttura del profilo di configurazione.](mac-preferences.md#configuration-profile-structure)

All'interno del profilo di configurazione, i criteri di controllo dei dispositivi sono definiti nella sezione seguente:

|Sezione|Valore|
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Chiave** | deviceControl |
| **Data type** | Dizionario (preferenza annidata) |
| **Comments** | Per una descrizione del contenuto del dizionario, vedi le sezioni seguenti. |

I criteri di controllo del dispositivo possono essere usati per:

- [Personalizzare la destinazione dell'URL per le notifiche generate dal controllo del dispositivo](#customize-url-target-for-notifications-raised-by-device-control)
- [Consentire o bloccare i dispositivi rimovibili](#allow-or-block-removable-devices)

### <a name="customize-url-target-for-notifications-raised-by-device-control"></a>Personalizzare la destinazione dell'URL per le notifiche generate dal controllo del dispositivo

Quando il criterio di controllo del dispositivo che hai applicato a un dispositivo (ad esempio, l'accesso a un dispositivo multimediale rimovibile è limitato), viene visualizzata una notifica per l'utente.

![Notifica di controllo del dispositivo](images/mac-device-control-notification.png)

Quando gli utenti finali selezionano questa notifica, viene aperta una pagina Web nel browser predefinito. È possibile configurare l'URL aperto quando gli utenti finali selezionano la notifica.

|Sezione|Valore|
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Chiave** | navigationTarget |
| **Data type** | Stringa |
| **Comments** | Se non è definito, il prodotto utilizza un URL predefinito che punta a una pagina generica che spiega l'azione eseguita dal prodotto. |

### <a name="allow-or-block-removable-devices"></a>Consentire o bloccare i dispositivi rimovibili

La sezione supporti rimovibili del criterio di controllo del dispositivo viene utilizzata per limitare l'accesso ai supporti rimovibili. 

> [!NOTE]
> I seguenti tipi di supporti rimovibili sono attualmente supportati e possono essere inclusi nel criterio: dispositivi di archiviazione USB.

|Sezione|Valore|
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Chiave** | removableMediaPolicy |
| **Data type** | Dizionario (preferenza annidata) |
| **Comments** | Per una descrizione del contenuto del dizionario, vedi le sezioni seguenti. |

Questa sezione del criterio è gerarchica, consentendo la massima flessibilità e coprendo un'ampia gamma di casi d'uso. Al livello principale sono i fornitori, identificati da un ID fornitore. Per ogni fornitore sono presenti prodotti identificati da un ID prodotto. Infine, per ogni prodotto sono presenti numeri di serie che denotano dispositivi specifici.

```
|-- policy top level 
    |-- vendor 1 
        |-- product 1 
            |-- serial number 1 
            ...
            |-- serial number N 
        ...
        |-- product N 
    ...
    |-- vendor N
```

Per informazioni su come trovare gli identificatori di dispositivo, vedi [Cercare gli identificatori di dispositivo.](#look-up-device-identifiers)

Il criterio viene valutato dalla voce più specifica a quella più generale. Ciò significa che, quando un dispositivo è collegato, il prodotto tenta di trovare la corrispondenza più specifica nel criterio per ogni dispositivo multimediale rimovibile e di applicare le autorizzazioni a tale livello. Se non è presente alcuna corrispondenza, viene applicata la corrispondenza migliore successiva, fino all'autorizzazione specificata al livello superiore, che è l'impostazione predefinita quando un dispositivo non corrisponde ad alcuna altra voce nel criterio.

#### <a name="policy-enforcement-level"></a>Livello di imposizione dei criteri

Nella sezione Supporti rimovibili è disponibile un'opzione per impostare il livello di imposizione, che può assumere uno dei valori seguenti:

- `audit` - Con questo livello di imposizione, se l'accesso a un dispositivo è limitato, viene visualizzata una notifica all'utente, ma il dispositivo può comunque essere usato. Questo livello di imposizione può essere utile per valutare l'efficacia di un criterio.
- `block` - In questo livello di imposizione, le operazioni che l'utente può eseguire sul dispositivo sono limitate a quanto definito nel criterio. Inoltre, viene generata una notifica all'utente. 

|Sezione|Valore|
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Chiave** | enforcementLevel |
| **Data type** | Stringa |
| **Valori possibili** | audit (impostazione predefinita) <br/> blocco |

#### <a name="default-permission-level"></a>Livello di autorizzazione predefinito

Al livello superiore della sezione supporti rimovibili, è possibile configurare il livello di autorizzazione predefinito per i dispositivi che non corrispondono ad altri elementi del criterio.

Questa impostazione può essere impostata su:

- `none` - Nessuna operazione può essere eseguita sul dispositivo
- Combinazione dei valori seguenti:
    - `read` - Le operazioni di lettura sono consentite nel dispositivo
    - `write` - Le operazioni di scrittura sono consentite nel dispositivo
    - `execute` - Le operazioni di esecuzione sono consentite nel dispositivo

> [!NOTE]
> Se `none` è presente nel livello di autorizzazione, qualsiasi altra autorizzazione ( , o ) verrà `read` `write` `execute` ignorata.

> [!NOTE]
> `execute`L'autorizzazione si riferisce solo all'esecuzione di file binari Mach-O. Non include l'esecuzione di script o altri tipi di payload.

|Sezione|Valore|
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Chiave** | autorizzazione |
| **Data type** | Matrice di stringhe |
| **Valori possibili** | nessuno <br/> lettura <br/> scrittura <br/> execute |

#### <a name="restrict-removable-media-by-vendor-product-and-serial-number"></a>Limitare i supporti rimovibili in base al fornitore, al prodotto e al numero di serie

Come descritto in [Consentire o bloccare](#allow-or-block-removable-devices)i dispositivi rimovibili, i supporti rimovibili come i dispositivi USB possono essere identificati dall'ID fornitore, dall'ID prodotto e dal numero di serie.

Al livello superiore del criterio di supporto rimovibile, è possibile definire restrizioni più granulari a livello di fornitore. 

Il dizionario contiene una o più voci, con ogni `vendors` voce identificata dall'ID fornitore.

|Sezione|Valore|
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Chiave** | fornitori |
| **Data type** | Dizionario (preferenza annidata) |

Per ogni fornitore, puoi specificare il livello di autorizzazione desiderato per i dispositivi di tale fornitore.

|Sezione|Valore|
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Chiave** | autorizzazione |
| **Data type** | Matrice di stringhe |
| **Valori possibili** | Uguale al [livello di autorizzazione predefinito](#default-permission-level) |

È inoltre possibile specificare facoltativamente il set di prodotti appartenenti al fornitore per il quale sono definite autorizzazioni più granulari. Il dizionario contiene una o più voci, con ogni `products` voce identificata dall'ID prodotto. 

|Sezione|Valore|
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Chiave** | prodotti |
| **Data type** | Dizionario (preferenza annidata) |

Per ogni prodotto, è possibile specificare il livello di autorizzazione desiderato per tale prodotto.

|Sezione|Valore|
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Chiave** | autorizzazione |
| **Data type** | Matrice di stringhe |
| **Valori possibili** | Uguale al [livello di autorizzazione predefinito](#default-permission-level) |

È inoltre possibile specificare un set facoltativo di numeri di serie per i quali sono definite autorizzazioni più granulari.

Il dizionario contiene una o più voci, con ogni `serialNumbers` voce identificata dal numero di serie.

|Sezione|Valore|
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Chiave** | serialNumbers |
| **Data type** | Dizionario (preferenza annidata) |

Per ogni numero di serie, è possibile specificare il livello di autorizzazione desiderato.

|Sezione|Valore|
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Chiave** | autorizzazione |
| **Data type** | Matrice di stringhe |
| **Valori possibili** | Uguale al [livello di autorizzazione predefinito](#default-permission-level) |

#### <a name="example-device-control-policy"></a>Criteri di controllo dei dispositivi di esempio

L'esempio seguente mostra come tutti i concetti precedenti possono essere combinati in un criterio di controllo del dispositivo. Nell'esempio seguente si noti la natura gerarchica del criterio di supporto rimovibile.

```xml
<?xml version="1.0" encoding="UTF-8"?> 
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"> 
<plist version="1.0"> 
<dict> 
    <key>deviceControl</key> 
    <dict> 
        <key>navigationTarget</key> 
        <string>[custom URL for notifications]</string> 
        <key>removableMediaPolicy</key> 
        <dict> 
            <key>enforcementLevel</key> 
            <string>[enforcement level]</string> <!-- audit / block --> 
            <key>permission</key> 
            <array> 
                <string>[permission]</string> <!-- none / read / write / execute --> 
                <!-- other permissions -->
            </array> 
            <key>vendors</key> 
            <dict> 
                <key>[vendor id]</key> 
                <dict>
                    <key>permission</key> 
                    <array> 
                        <string>[permission]</string> <!-- none / read / write / execute --> 
                        <!-- other permissions -->
                    </array> 
                    <key>products</key> 
                    <dict> 
                        <key>[product id]</key> 
                        <dict> 
                            <key>permission</key> 
                            <array> 
                                <string>[permission]</string> <!-- none / read / write / execute --> 
                                <!-- other permissions -->
                            </array> 
                            <key>serialNumbers</key> 
                            <dict> 
                                <key>[serial-number]</key> 
                                <array> 
                                    <string>[permission]</string> <!-- none / read / write / execute --> 
                                    <!-- other permissions -->
                                </array> 
                                <!-- other serial numbers --> 
                            </dict> 
                        </dict> 
                        <!-- other products --> 
                    </dict> 
                </dict> 
                <!-- other vendors --> 
            </dict> 
        </dict> 
    </dict> 
</dict> 
</plist> 
```

Abbiamo incluso altri esempi di criteri di controllo dei dispositivi nei documenti seguenti:

- [Esempi di criteri di controllo dei dispositivi per Intune](mac-device-control-intune.md)
- [Esempi di criteri di controllo dei dispositivi per JAMF](mac-device-control-jamf.md)

#### <a name="look-up-device-identifiers"></a>Cercare identificatori di dispositivo

Per trovare l'ID fornitore, l'ID prodotto e il numero di serie di un dispositivo USB:

1. Accedi a un dispositivo Mac.
1. Collega il dispositivo USB per il quale vuoi cercare gli identificatori.
1. Nel menu di primo livello di macOS seleziona **Informazioni su questo Mac.**

    ![Informazioni su questo Mac](images/mac-device-control-lookup-1.png)

1. Selezionare **Report di sistema**.

    ![Rapporto di sistema](images/mac-device-control-lookup-2.png)

1. Nella colonna sinistra seleziona **USB.**

    ![Visualizzazione di tutti i dispositivi USB](images/mac-device-control-lookup-3.png)

1. In **Albero dispositivi USB** passa al dispositivo USB collegato.

    ![Dettagli di un dispositivo USB](images/mac-device-control-lookup-4.png)

1. Vengono visualizzati l'ID fornitore, l'ID prodotto e il numero di serie. Quando si aggiungono l'ID fornitore e l'ID prodotto al criterio del supporto rimovibile, è necessario aggiungere la parte solo dopo `0x` . Ad esempio, nell'immagine seguente, l'ID fornitore è `1000` e l'ID prodotto è `090c` .

#### <a name="discover-usb-devices-in-your-organization"></a>Individuare i dispositivi USB nell'organizzazione

Puoi visualizzare gli eventi di montaggio, smontamento e modifica del volume provenienti da dispositivi USB in Microsoft Defender for Endpoint advanced hunting. Questi eventi possono essere utili per identificare attività di utilizzo sospette o eseguire indagini interne.

```
DeviceEvents 
    | where ActionType == "UsbDriveMounted" or ActionType == "UsbDriveUnmounted" or ActionType == "UsbDriveDriveLetterChanged"
    | where DeviceId == "<device ID>"
```

## <a name="device-control-policy-deployment"></a>Distribuzione dei criteri di controllo dei dispositivi

Il criterio di controllo del dispositivo deve essere incluso accanto alle altre impostazioni del prodotto, come descritto in Impostare le preferenze per [Microsoft Defender per Endpoint in macOS.](mac-preferences.md)

Questo profilo può essere distribuito usando le istruzioni elencate in [Distribuzione del profilo di configurazione](mac-preferences.md#configuration-profile-deployment).

## <a name="troubleshooting-tips"></a>Suggerimenti per la risoluzione dei problemi

Dopo aver eseguito il push del profilo di configurazione tramite Intune o JAMF, puoi verificare se è stato raccolto correttamente dal prodotto eseguendo il comando seguente dal terminale:

```bash
mdatp device-control removable-media policy list
```

Questo comando stamperà nell'output standard il criterio di controllo del dispositivo utilizzato dal prodotto. In caso di stampa, assicurati che (a) il profilo di configurazione sia stato effettivamente inserito nel dispositivo dalla console di gestione e (b) sia un criterio di controllo del dispositivo valido, come descritto `Policy is empty` in questo documento.

In un dispositivo in cui il criterio è stato recapitato correttamente e in cui sono presenti uno o più dispositivi collegati, puoi eseguire il comando seguente per elencare tutti i dispositivi e le autorizzazioni effettive applicate.

```bash
mdatp device-control removable-media devices list
```

Esempio di output:

```Output
.Device(s)
|-o Name: Untitled 1, Permission ["read", "execute"]
| |-o Vendor: General "fff0"
| |-o Product: USB Flash Disk "1000"
| |-o Serial number: "04ZSSMHI2O7WBVOA"
| |-o Mount point: "/Volumes/TESTUSB"
```

Nell'esempio precedente, è collegato un solo dispositivo multimediale rimovibile e dispone di autorizzazioni e, in base ai criteri di controllo del dispositivo recapitati `read` `execute` al dispositivo.

## <a name="related-topics"></a>Argomenti correlati

- [Esempi di criteri di controllo dei dispositivi per Intune](mac-device-control-intune.md)
- [Esempi di criteri di controllo dei dispositivi per JAMF](mac-device-control-jamf.md)
