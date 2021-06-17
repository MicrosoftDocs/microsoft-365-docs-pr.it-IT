---
title: Personalizzare regole per la riduzione della superficie di attacco
description: Impostare singolarmente le regole nelle modalità di controllo, blocco o disabilitata e aggiungere file e cartelle che devono essere esclusi dalle regole di riduzione della superficie di attacco
keywords: Riduzione della superficie di attacco, fianchi, sistema di prevenzione delle intrusioni host, regole di protezione, anti-exploit, antiexploit, exploit, prevenzione delle infezioni, personalizzare, configurare, escludere
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 6b9814180df2cad2553c4565ebb65891b5cf9bf5
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985421"
---
# <a name="customize-attack-surface-reduction-rules"></a>Personalizzare regole per la riduzione della superficie di attacco

**Si applica a:**

- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

> [!IMPORTANT]
> Alcune informazioni fanno riferimento alle caratteristiche del prodotto prima del rilascio, e possono essere modificate sostanzialmente prima della distribuzione al pubblico. Microsoft non fornisce alcuna garanzia, esplicita o implicita, in relazione alle informazioni contenute in questo documento.

[Le regole di riduzione della superficie](enable-attack-surface-reduction.md) di attacco consentono di evitare comportamenti software spesso utilizzati in modo improprio per compromettere il dispositivo o la rete. Ad esempio, un utente malintenzionato potrebbe tentare di eseguire uno script non firmato da un'unità USB o avere una macro in un documento Office effettuare chiamate direttamente all'API Win32. Le regole di riduzione della superficie di attacco possono vincolare questi tipi di comportamenti rischiosi e migliorare la posizione difensiva dell'organizzazione.

Informazioni su come personalizzare le [](#exclude-files-and-folders) regole di riduzione [](#customize-the-notification) della superficie di attacco escludendo file e cartelle o aggiungendo testo personalizzato all'avviso di notifica visualizzato nel computer di un utente.

Puoi impostare regole di riduzione della superficie di attacco per i dispositivi che eseguono una delle seguenti edizioni e versioni di Windows:

- Windows 10 Pro versione [1709](/windows/whats-new/whats-new-windows-10-version-1709) o successiva
- Windows 10 Enterprise versione [1709](/windows/whats-new/whats-new-windows-10-version-1709) o successiva
- Windows Server, [versione 1803 (Canale semestraale)](/windows-server/get-started/whats-new-in-windows-server-1803) o versione successiva
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19) Puoi usare i provider di servizi di configurazione (CSP) di Criteri di gruppo, PowerShell e Gestione dispositivi mobili (MDM) per configurare queste impostazioni.

## <a name="exclude-files-and-folders"></a>Escludere file e cartelle

È possibile scegliere di escludere file e cartelle dalla valutazione da parte delle regole di riduzione della superficie di attacco. Se escluso, l'esecuzione del file non verrà bloccata anche se una regola di riduzione della superficie di attacco rileva che il file contiene comportamenti dannosi.

Ad esempio, considera la regola ransomware:

La regola ransomware è progettata per aiutare i clienti aziendali a ridurre i rischi di attacchi ransomware garantendo al contempo la continuità aziendale. Per impostazione predefinita, gli errori delle regole ransomware a livello di cautela e protezione da file che non hanno ancora raggiunto una reputazione e un'attendibilità sufficienti. Per rievolgimento, la regola ransomware si attiva solo sui file che non hanno acquisito una reputazione e una diffusione abbastanza positivi, in base alle metriche di utilizzo di milioni di clienti. In genere, i blocchi vengono risolti automaticamente, perché i valori di "reputazione e attendibilità" di ogni file vengono aggiornati in modo incrementale con l'aumento dell'utilizzo non problematico.

Nei casi in cui i blocchi non vengono risolti automaticamente in modo appropriato, i clienti _possono,_ a proprio rischio, utilizzare il meccanismo self-service o una funzionalità "elenco consenti" basata su Indicatore di compromissione (IOC) per sbloccare i file stessi.  

> [!WARNING]
> L'esclusione o lo sblocco di file o cartelle potrebbe potenzialmente consentire l'esecuzione di file non sicuri e infettare i dispositivi. L'esclusione di file o cartelle può ridurre in modo grave la protezione fornita dalle regole di riduzione delle superficie di attacco. L'esecuzione dei file che sarebbero stati bloccati da una regola sarà consentita e non verrà registrato alcun report o evento.

Un'esclusione si applica a tutte le regole che consentono le esclusioni. È possibile specificare un singolo file, un percorso di cartella o il nome di dominio completo per una risorsa. Tuttavia, non è possibile limitare un'esclusione a una regola specifica.

Un'esclusione viene applicata solo all'avvio dell'applicazione o del servizio escluso. Ad esempio, se si aggiunge un'esclusione per un servizio di aggiornamento già in esecuzione, il servizio di aggiornamento continuerà a attivare eventi finché il servizio non viene arrestato e riavviato.

La riduzione della superficie di attacco supporta variabili di ambiente e caratteri jolly. Per informazioni sull'utilizzo dei caratteri jolly, vedere Utilizzare i caratteri jolly nel nome file e nel percorso della cartella o negli elenchi di esclusione [delle estensioni.](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)
Se si verificano problemi con le regole che rilevano file che ritieni non debbano essere rilevati, usa la modalità di controllo [per testare la regola.](evaluate-attack-surface-reduction.md)

| Descrizione delle regole | GUID |
|:----|:----|
| Impedire a Office applicazioni di creare processi figlio | `D4F940AB-401B-4EFC-AADC-AD5F3C50688A` |
| Bloccare l'esecuzione di script potenzialmente offuscati | `5BEB7EFE-FD9A-4556-801D-275E5FFC04CC` |
| Bloccare le chiamate API Win32 da Office macro | `92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B` |
| Impedire Office applicazioni di creare contenuto eseguibile | `3B576869-A4EC-4529-8536-B80A7769E899` |
| Bloccare Office applicazioni dall'inserimento di codice in altri processi | `75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84` |
| Impedire a JavaScript o VBScript di avviare il contenuto eseguibile scaricato | `D3E037E1-3EB8-44C8-A917-57927947596D` |
| Bloccare il contenuto eseguibile dal client di posta elettronica e dalla webmail | `BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550` |
| Bloccare l'esecuzione dei file eseguibili a meno che non soddisfino criteri di prevalenza, età o elenco attendibile | `01443614-cd74-433a-b99e-2ecdc07bfc25` |
| Usare la protezione avanzata contro ransomware | `c1db55ab-c21a-4637-bb3f-a12568109d35` |
| Bloccare il furto delle credenziali dal sottosistema Windows autorità di sicurezza locale (lsass.exe) | `9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2` |
| Bloccare le creazioni di processi originate dai comandi PSExec e WMI | `d1e49aac-8f56-4280-b9ba-993a6d77406c` |
| Bloccare i processi non attendibili e non firmati eseguiti da USB | `b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4` |
| Impedire Office applicazioni di comunicazione di creare processi figlio | `26190899-1602-49e8-8b27-eb1d0a1ce869` |
| Impedire ad Adobe Reader di creare processi figlio | `7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c` |
| Bloccare la persistenza tramite la sottoscrizione di eventi WMI | `e6db77e5-3df2-4cf1-b95a-636979351e5b` |

Per informazioni [dettagliate su](attack-surface-reduction.md) ogni regola, vedere l'argomento relativo alla riduzione della superficie di attacco.

### <a name="use-group-policy-to-exclude-files-and-folders"></a>Utilizzare Criteri di gruppo per escludere file e cartelle

1. Nel computer di gestione dei Criteri di gruppo aprire la [Console Gestione Criteri di gruppo](https://technet.microsoft.com/library/cc731212.aspx), fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo da configurare e scegliere **Modifica**.

2. **Nell'Editor Gestione Criteri di gruppo** passare a Configurazione computer **e** fare clic su **Modelli amministrativi.**

3. Espandi l'albero per Windows **componenti Antivirus Microsoft Defender** Windows Defender riduzione della superficie di attacco di  >    >  **Exploit Guard.**  >  

4. Fai doppio clic **sull'impostazione Escludi** file e percorsi dalle regole di riduzione della superficie di attacco e imposta l'opzione su **Abilitato.** Selezionare **Mostra** e immettere ogni file o cartella nella **colonna Nome** valore. Immettere **0** nella **colonna Valore** per ogni elemento.

> [!WARNING]
> Non utilizzare le virgolette perché non sono supportate per la colonna **Nome valore** o **Valore.**

### <a name="use-powershell-to-exclude-files-and-folders"></a>Utilizzare PowerShell per escludere file e cartelle

1. Digitare **powershell** nella menu Start, fare clic con il pulsante destro **del mouse** Windows PowerShell e selezionare Esegui come **amministratore**
2. Immettere il cmdlet seguente:

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionOnlyExclusions "<fully qualified path or resource>"
    ```

Continuare a utilizzare `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` per aggiungere altre cartelle all'elenco.

> [!IMPORTANT]
> Usa `Add-MpPreference` per aggiungere o aggiungere app all'elenco. `Set-MpPreference`L'utilizzo del cmdlet sovrascriverà l'elenco esistente.

### <a name="use-mdm-csps-to-exclude-files-and-folders"></a>Usare CSP MDM per escludere file e cartelle

Usa il provider di servizi di configurazione [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) per aggiungere esclusioni.

## <a name="customize-the-notification"></a>Personalizzare la notifica

Puoi personalizzare la notifica per l'attivazione di una regola e bloccare un'app o un file. Vedi [l'Sicurezza di Windows](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center#customize-notifications-from-the-windows-defender-security-center) articolo.

## <a name="related-topics"></a>Argomenti correlati

- [Ridurre le superfici di attacco con le regole di riduzione della superficie di attacco](attack-surface-reduction.md)
- [Abilitare regole per la riduzione della superficie di attacco](enable-attack-surface-reduction.md)
- [Valutare le regole per la riduzione della superficie di attacco](evaluate-attack-surface-reduction.md)
- [Domande frequenti per la riduzione della superficie di attacco](attack-surface-reduction.md)
