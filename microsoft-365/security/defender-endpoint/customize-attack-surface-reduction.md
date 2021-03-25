---
title: Personalizzare le regole di riduzione della superficie di attacco
description: Impostare singolarmente le regole nelle modalità di controllo, blocco o disabilitata e aggiungere file e cartelle che devono essere esclusi dalle regole di riduzione della superficie di attacco
keywords: Riduzione della superficie di attacco, fianchi, sistema di prevenzione delle intrusioni host, regole di protezione, anti-exploit, antiexploit, exploit, prevenzione delle infezioni, personalizzare, configurare, escludere
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: levinec
ms.author: ellevin
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 99a88a869c8a79f79cbc3a16fc73bf556416c51a
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163298"
---
# <a name="customize-attack-surface-reduction-rules"></a>Personalizzare le regole di riduzione della superficie di attacco

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**
- [Microsoft Defender ATP](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

> [!IMPORTANT]
> Alcune informazioni fanno riferimento alle caratteristiche del prodotto prima del rilascio, e possono essere modificate sostanzialmente prima della distribuzione al pubblico. Microsoft non fornisce alcuna garanzia, esplicita o implicita, in relazione alle informazioni contenute in questo documento.

[Le regole di riduzione della superficie](enable-attack-surface-reduction.md) di attacco consentono di evitare comportamenti software spesso utilizzati in modo improprio per compromettere il dispositivo o la rete. Ad esempio, un utente malintenzionato potrebbe tentare di eseguire uno script non firmato da un'unità USB oppure fare in modo che una macro in un documento di Office eserciti chiamate direttamente all'API Win32. Le regole di riduzione della superficie di attacco possono vincolare questi tipi di comportamenti rischiosi e migliorare la posizione difensiva dell'organizzazione.

Informazioni su come personalizzare le [](#exclude-files-and-folders) regole di riduzione [](#customize-the-notification) della superficie di attacco escludendo file e cartelle o aggiungendo testo personalizzato all'avviso di notifica visualizzato nel computer di un utente.

Puoi impostare regole di riduzione della superficie di attacco per i dispositivi che eseguono una delle seguenti edizioni e versioni di Windows:
- Windows 10 Pro, [versione 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) o successiva
- Windows 10 Enterprise, [versione 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) o successiva
- Windows Server, [versione 1803 (Canale semestraale)](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) o versione successiva
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19) Puoi usare i provider di servizi di configurazione (CSP) di Criteri di gruppo, PowerShell e Gestione dispositivi mobili (MDM) per configurare queste impostazioni.

## <a name="exclude-files-and-folders"></a>Escludere file e cartelle

È possibile scegliere di escludere file e cartelle dalla valutazione da parte delle regole di riduzione della superficie di attacco. Una volta escluso, l'esecuzione del file non verrà bloccata anche se una regola di riduzione della superficie di attacco rileva che il file contiene comportamenti dannosi.

> [!WARNING]
> Ciò potrebbe potenzialmente consentire l'esecuzione di file non sicuri e infettare i dispositivi. L'esclusione di file o cartelle può ridurre notevolmente la protezione fornita dalle regole di riduzione della superficie di attacco. L'esecuzione dei file che sarebbero stati bloccati da una regola sarà consentita e non verrà registrato alcun report o evento.

Un'esclusione si applica a tutte le regole che consentono le esclusioni. È possibile specificare un singolo file, un percorso di cartella o il nome di dominio completo per una risorsa. Tuttavia, non è possibile limitare un'esclusione a una regola specifica.

Un'esclusione viene applicata solo all'avvio dell'applicazione o del servizio escluso. Ad esempio, se si aggiunge un'esclusione per un servizio di aggiornamento già in esecuzione, il servizio di aggiornamento continuerà a attivare eventi finché il servizio non viene arrestato e riavviato.

La riduzione della superficie di attacco supporta variabili di ambiente e caratteri jolly. Per informazioni sull'utilizzo dei caratteri jolly, vedere Utilizzare i caratteri jolly nel nome file e nel percorso della cartella o negli elenchi di esclusione [delle estensioni.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)
Se si verificano problemi con le regole che rilevano file che ritieni non debbano essere rilevati, usa la modalità di controllo [per testare la regola.](evaluate-attack-surface-reduction.md)

Descrizione delle regole | GUID
-|-|-
Impedire a tutte le applicazioni di Office di creare processi figlio | D4F940AB-401B-4EFC-AADC-AD5F3C50688A
Bloccare l'esecuzione di script potenzialmente offuscati | 5BEB7EFE-FD9A-4556-801D-275E5FFC04CC
Bloccare le chiamate API Win32 dalla macro di Office | 92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B
Impedire alle applicazioni di Office di creare contenuto eseguibile | 3B576869-A4EC-4529-8536-B80A7769E899
Impedire alle applicazioni di Office di inserire codice in altri processi | 75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84
Impedire a JavaScript o VBScript di avviare il contenuto eseguibile scaricato | D3E037E1-3EB8-44C8-A917-57927947596D
Bloccare il contenuto eseguibile dal client di posta elettronica e dalla webmail | BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550
Bloccare l'esecuzione dei file eseguibili a meno che non soddisfino criteri di prevalenza, età o elenco attendibile | 01443614-cd74-433a-b99e-2ecdc07bfc25
Usare la protezione avanzata contro ransomware | c1db55ab-c21a-4637-bb3f-a12568109d35
Bloccare il furto delle credenziali dal sottosistema dell'autorità di sicurezza locale di Windows (lsass.exe) | 9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2
Bloccare le creazioni di processi originate dai comandi PSExec e WMI | d1e49aac-8f56-4280-b9ba-993a6d77406c
Bloccare i processi non attendibili e non firmati eseguiti da USB | b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4
Impedire alle applicazioni di comunicazione di Office di creare processi figlio | 26190899-1602-49e8-8b27-eb1d0a1ce869
Impedire ad Adobe Reader di creare processi figlio | 7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c
Bloccare la persistenza tramite la sottoscrizione di eventi WMI | e6db77e5-3df2-4cf1-b95a-636979351e5b

Per informazioni [dettagliate su](attack-surface-reduction.md) ogni regola, vedere l'argomento relativo alla riduzione della superficie di attacco.

### <a name="use-group-policy-to-exclude-files-and-folders"></a>Utilizzare Criteri di gruppo per escludere file e cartelle

1. Nel computer di gestione di Criteri di gruppo aprire Console Gestione Criteri di [gruppo,](https://technet.microsoft.com/library/cc731212.aspx)fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.

2. **Nell'Editor Gestione Criteri di gruppo** passare a Configurazione computer **e** fare clic su **Modelli amministrativi.**

3. Espandi l'albero fino ai **componenti di Windows** Microsoft Defender Antivirus Windows Defender riduzione della superficie di attacco  >    >  di Exploit **Guard.**  >  

4. Fai doppio clic **sull'impostazione Escludi** file e percorsi dalle regole di riduzione della superficie di attacco e imposta l'opzione su **Abilitato.** Selezionare **Mostra** e immettere ogni file o cartella nella **colonna Nome** valore. Immettere **0** nella **colonna Valore** per ogni elemento.

> [!WARNING]
> Non utilizzare le virgolette perché non sono supportate per la colonna **Nome valore** o **Valore.**

### <a name="use-powershell-to-exclude-files-and-folders"></a>Utilizzare PowerShell per escludere file e cartelle

1. Digitare **powershell** nel menu Start, fare clic con il pulsante destro del mouse Windows PowerShell **e** selezionare Esegui come **amministratore**
2. Immettere il cmdlet seguente:

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionOnlyExclusions "<fully qualified path or resource>"
    ```

Continuare a utilizzare `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` per aggiungere altre cartelle all'elenco.

> [!IMPORTANT]
> Usa `Add-MpPreference` per aggiungere o aggiungere app all'elenco. `Set-MpPreference`L'utilizzo del cmdlet sovrascriverà l'elenco esistente.

### <a name="use-mdm-csps-to-exclude-files-and-folders"></a>Usare CSP MDM per escludere file e cartelle

Usa il provider di servizi di configurazione [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) per aggiungere esclusioni.

## <a name="customize-the-notification"></a>Personalizzare la notifica

Puoi personalizzare la notifica per l'attivazione di una regola e bloccare un'app o un file. Vedi [l'articolo Sicurezza di Windows.](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center#customize-notifications-from-the-windows-defender-security-center)

## <a name="related-topics"></a>Argomenti correlati

* [Ridurre le superfici di attacco con le regole di riduzione della superficie di attacco](attack-surface-reduction.md)
* [Abilitare le regole di riduzione della superficie di attacco](enable-attack-surface-reduction.md)
* [Valutare le regole di riduzione della superficie di attacco](evaluate-attack-surface-reduction.md)
* [Domande frequenti sulla riduzione della superficie di attacco](attack-surface-reduction.md)
