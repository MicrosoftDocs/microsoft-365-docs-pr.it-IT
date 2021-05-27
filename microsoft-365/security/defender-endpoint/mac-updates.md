---
title: Distribuire gli aggiornamenti per Microsoft Defender per Endpoint su Mac
description: Controlla gli aggiornamenti per Microsoft Defender per Endpoint su Mac in ambienti aziendali.
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, aggiornamenti, distribuire
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
ms.openlocfilehash: e08781455888595d57bd8a9e6f792796ea1853cd
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2021
ms.locfileid: "52684208"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-on-macos"></a>Distribuire gli aggiornamenti per Microsoft Defender per Endpoint in macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**

- [Microsoft Defender per endpoint su macOS](microsoft-defender-endpoint-mac.md)
- [Microsoft Defender ATP](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Microsoft pubblica regolarmente aggiornamenti software per migliorare le prestazioni, la sicurezza e offrire nuove funzionalità.

Per aggiornare Microsoft Defender for Endpoint in macOS, viene utilizzato un programma denominato Microsoft AutoUpdate (MAU). Per impostazione predefinita, MAU controlla automaticamente la disponibilità di aggiornamenti ogni giorno, ma puoi modificarli in settimana, mensile o manualmente.

![Schermata MAU](images/MDATP-34-MAU.png)

Se decidi di distribuire gli aggiornamenti usando gli strumenti di distribuzione del software, devi configurare MAU per controllare manualmente la disponibilità di aggiornamenti software. Puoi distribuire le preferenze per configurare come e quando MAU controlla la disponibilità di aggiornamenti per i Mac nell'organizzazione.

## <a name="use-msupdate"></a>Utilizzare msupdate

MAU include uno strumento da riga di comando, denominato *msupdate,* progettato per gli amministratori IT in modo che abbia un controllo più preciso sulla modalità di applicazione degli aggiornamenti. Le istruzioni per l'utilizzo di questo strumento sono disponibili in [Aggiornamento Office per Mac tramite msupdate](https://docs.microsoft.com/deployoffice/mac/update-office-for-mac-using-msupdate).

In MAU, l'identificatore dell'applicazione per Microsoft Defender per Endpoint in macOS è *WDAV00*. Per scaricare e installare gli aggiornamenti più recenti per Microsoft Defender for Endpoint in macOS, eseguire il comando seguente da una finestra del terminale:

```
./msupdate --install --apps wdav00
```

## <a name="set-preferences-for-microsoft-autoupdate"></a>Impostare le preferenze per Microsoft AutoUpdate

Questa sezione descrive le preferenze più comuni che possono essere usate per configurare MAU. Queste impostazioni possono essere distribuite come profilo di configurazione tramite la console di gestione utilizzata dall'organizzazione. Un esempio di profilo di configurazione è illustrato nelle sezioni seguenti.

### <a name="set-the-channel-name"></a>Impostare il nome del canale

Il canale determina il tipo e la frequenza degli aggiornamenti offerti tramite MAU. I dispositivi in `Beta` possono provare nuove funzionalità prima dei dispositivi in e `Preview` `Current` . 

Il `Current` canale contiene la versione più stabile del prodotto.

>[!IMPORTANT]
> Prima di Microsoft AutoUpdate versione 4.29, i canali avevano nomi diversi: 
> 
> - `Beta` è stato `InsiderFast` denominato (Insider Fast)
> - `Preview` è stato `External` denominato (Insider Slow)
> - `Current` è stato denominato `Production`

>[!TIP]
>Per visualizzare in anteprima le nuove funzionalità e fornire feedback anticipato, è consigliabile configurare alcuni dispositivi dell'organizzazione in `Beta` o `Preview` .

|Sezione|Valore|
|:--|:--|
| **Dominio** | `com.microsoft.autoupdate2` |
| **Chiave** | ChannelName |
| **Data type** | Stringa |
| **Valori possibili** | Beta <br/> Anteprima <br/> Current |
|||

>[!WARNING]
>Questa impostazione modifica il canale per tutte le applicazioni aggiornate tramite Microsoft AutoUpdate. Per modificare il canale solo per Microsoft Defender for Endpoint in macOS, esegui il comando seguente dopo la sostituzione `[channel-name]` con il canale desiderato:
> ```bash
> defaults write com.microsoft.autoupdate2 Applications -dict-add "/Applications/Microsoft Defender ATP.app" " { 'Application ID' = 'WDAV00' ; 'App Domain' = 'com.microsoft.wdav' ; LCID = 1033 ; ChannelName = '[channel-name]' ; }"
> ```

### <a name="set-update-check-frequency"></a>Impostare la frequenza di controllo degli aggiornamenti

Modificare la frequenza di ricerca degli aggiornamenti da parte di MAU.

|Sezione|Valore|
|:--|:--|
| **Dominio** | `com.microsoft.autoupdate2` |
| **Chiave** | UpdateCheckFrequency |
| **Data type** | Numero intero |
| **Valore predefinito** | 720 (minuti) |
| **Commento** | Questo valore è impostato in minuti. |


### <a name="change-how-mau-interacts-with-updates"></a>Modificare il modo in cui MAU interagisce con gli aggiornamenti

Modificare la modalità di ricerca degli aggiornamenti da parte di MAU.

|Sezione|Valore|
|:--|:--|
| **Dominio** | `com.microsoft.autoupdate2` |
| **Chiave** | HowToCheck |
| **Data type** | Stringa |
| **Valori possibili** | Manuale <br/> AutomaticCheck <br/> AutomaticDownload |
| **Commento** |  Nota che AutomaticDownload farà un download e l'installazione invisibile all'utente, se possibile. |


### <a name="change-whether-the-check-for-updates-button-is-enabled"></a>Modificare se il pulsante "Controlla aggiornamenti" è abilitato

Modificare se gli utenti locali potranno fare clic sull'opzione "Controlla aggiornamenti" nell'interfaccia utente di Microsoft AutoUpdate.

|Sezione|Valore|
|:--|:--|
| **Dominio** | `com.microsoft.autoupdate2` |
| **Chiave** | EnableCheckForUpdatesButton |
| **Data type** | Booleano |
| **Valori possibili** | True (impostazione predefinita) <br/> Falso |


### <a name="disable-insider-checkbox"></a>Casella di controllo Disattiva Insider

Impostare su true per rendere "Partecipa al programma Insider Office insider..." casella di controllo non disponibile/ disattivata per gli utenti.

|Sezione|Valore|
|:--|:--|
| **Dominio** | `com.microsoft.autoupdate2` |
| **Chiave** | DisableInsiderCheckbox |
| **Data type** | Booleano |
| **Valori possibili** | False (impostazione predefinita) <br/> Vero |


### <a name="limit-the-telemetry-that-is-sent-from-mau"></a>Limitare la telemetria inviata da MAU

Impostare su false per inviare dati heartbeat minimi, nessun utilizzo dell'applicazione e nessun dettaglio dell'ambiente.

|Sezione|Valore|
|:--|:--|
| **Dominio** | `com.microsoft.autoupdate2` |
| **Chiave** | SendAllTelemetryEnabled |
| **Data type** | Booleano |
| **Valori possibili** | True (impostazione predefinita) <br/> Falso |


## <a name="example-configuration-profile"></a>Profilo di configurazione di esempio

Viene utilizzato il profilo di configurazione seguente per:
- Posizionare il dispositivo nel canale Di produzione
- Scaricare e installare automaticamente gli aggiornamenti
- Abilitare il pulsante "Controlla aggiornamenti" nell'interfaccia utente
- Consenti agli utenti nel dispositivo di registrarsi nei canali Insider


>[!WARNING]
>La configurazione seguente è una configurazione di esempio e non deve essere utilizzata in produzione senza un'adeguata revisione delle impostazioni e la personalizzazione delle configurazioni.

>[!TIP]
>Per visualizzare in anteprima le nuove funzionalità e fornire feedback anticipato, è consigliabile configurare alcuni dispositivi dell'organizzazione in `Beta` o `Preview` .

### <a name="jamf"></a>JAMF

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>ChannelName</key>
    <string>Production</string>
    <key>HowToCheck</key>
    <string>AutomaticDownload</string>
    <key>EnableCheckForUpdatesButton</key>
    <true/>
    <key>DisableInsiderCheckbox</key>
    <false/>
    <key>SendAllTelemetryEnabled</key>
    <true/>
</dict>
</plist>
```

### <a name="intune"></a>Intune

```XML
<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1">
    <dict>
        <key>PayloadUUID</key>
        <string>B762FF60-6ACB-4A72-9E72-459D00C936F3</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>com.microsoft.autoupdate2</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft AutoUpdate settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft AutoUpdate configuration settings</string>
        <key>PayloadVersion</key>
        <integer>1</integer>
        <key>PayloadEnabled</key>
        <true/>
        <key>PayloadRemovalDisallowed</key>
        <true/>
        <key>PayloadScope</key>
        <string>System</string>
        <key>PayloadContent</key>
        <array>
            <dict>
            <key>PayloadUUID</key>
            <string>5A6F350A-CC2C-440B-A074-68E3F34EBAE9</string>
            <key>PayloadType</key>
            <string>com.microsoft.autoupdate2</string>
            <key>PayloadOrganization</key>
            <string>Microsoft</string>
            <key>PayloadIdentifier</key>
            <string>com.microsoft.autoupdate2</string>
            <key>PayloadDisplayName</key>
            <string>Microsoft AutoUpdate configuration settings</string>
            <key>PayloadDescription</key>
            <string/>
            <key>PayloadVersion</key>
            <integer>1</integer>
            <key>PayloadEnabled</key>
            <true/>
            <key>ChannelName</key>
            <string>Production</string>
            <key>HowToCheck</key>
            <string>AutomaticDownload</string>
            <key>EnableCheckForUpdatesButton</key>
            <true/>
            <key>DisableInsiderCheckbox</key>
            <false/>
            <key>SendAllTelemetryEnabled</key>
            <true/>
            </dict>
        </array>
    </dict>
</plist>
```

Per configurare MAU, è possibile distribuire questo profilo di configurazione dallo strumento di gestione utilizzato dall'organizzazione:
- Da JAMF carica questo profilo di configurazione e imposta dominio di preferenza *su com.microsoft.autoupdate2*.
- Da Intune carica questo profilo di configurazione e imposta il nome del profilo di configurazione personalizzato *su com.microsoft.autoupdate2*.

## <a name="resources"></a>Risorse

- [riferimento msupdate](https://docs.microsoft.com/deployoffice/mac/update-office-for-mac-using-msupdate)
