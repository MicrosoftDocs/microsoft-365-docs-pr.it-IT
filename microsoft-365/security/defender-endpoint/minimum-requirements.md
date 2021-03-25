---
title: Requisiti minimi per Microsoft Defender per Endpoint
description: Comprendere i requisiti di licenza e i requisiti per l'onboarding dei dispositivi nel servizio
keywords: requisiti minimi, licenze, tabella di confronto
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: c6afa48fcee80c0b8fb7ed0563264932566b6321
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185792"
---
# <a name="minimum-requirements-for-microsoft-defender-for-endpoint"></a>Requisiti minimi per Microsoft Defender per Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


Esistono alcuni requisiti minimi per l'onboarding dei dispositivi nel servizio. Informazioni sulle licenze, i requisiti hardware e software e altre impostazioni di configurazione per eseguire l'onboardment dei dispositivi nel servizio.

> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-minreqs-abovefoldlink)

> [!TIP]
> - Informazioni sui miglioramenti più recenti in Defender for Endpoint: [Defender for Endpoint Tech Community.](https://techcommunity.microsoft.com/t5/Windows-Defender-Advanced-Threat/ct-p/WindowsDefenderAdvanced)
> - Defender for Endpoint ha dimostrato le funzionalità di ottica e rilevamento leader del settore nella recente valutazione MITRE. Read: [Insights from the MITRE ATT&CK-based evaluation](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).

## <a name="licensing-requirements"></a>Requisiti per la licenza
Microsoft Defender for Endpoint richiede una delle seguenti offerte di contratti multilicenza Microsoft:

- Windows 10 Enterprise E5
- Windows 10 Education A5
- Microsoft 365 E5 (M365 E5) che include Windows 10 Enterprise E5
- Microsoft 365 A5 (M365 A5)
- Microsoft 365 E5 Security
- Microsoft 365 A5 Security
- Microsoft Defender per endpoint

> [!NOTE]
> Gli utenti con licenza idonea possono usare Microsoft Defender per Endpoint su un massimo di cinque dispositivi simultanei.
> Microsoft Defender for Endpoint è disponibile anche per l'acquisto da un provider di soluzioni cloud (CSP).

Microsoft Defender for Endpoint per i server richiede una delle opzioni di licenza seguenti:

- [Centro sicurezza di Azure con Azure Defender abilitato](https://docs.microsoft.com/azure/security-center/security-center-pricing)
- Microsoft Defender for Endpoint for Server (uno per server coperto)

> [!NOTE]
> I clienti possono acquisire licenze server (una per server OSE)) per Microsoft Defender for Endpoint for Servers se hanno un minimo combinato di 50 licenze per una o più delle licenze utente seguenti:
>
> * Microsoft Defender per endpoint
> * Windows E5/A5
> * Microsoft 365 E5/A5
> * Microsoft 365 E5/A5 Security

Per informazioni dettagliate sulle licenze, vedere il sito [condizioni](https://www.microsoft.com/licensing/terms/) del prodotto e collaborare con il team dell'account per ulteriori informazioni sui termini e le condizioni.

Per altre informazioni sulla matrice di funzionalità nelle edizioni di Windows 10, vedi [Confrontare le edizioni di Windows 10.](https://www.microsoft.com/windowsforbusiness/compare)

Per una tabella di confronto dettagliata del confronto delle edizioni commerciali di Windows 10, vedi il [PDF di confronto.](https://wfbdevicemanagementprod.blob.core.windows.net/windowsforbusiness/Windows10_CommercialEdition_Comparison.pdf)

## <a name="browser-requirements"></a>Requisiti per il browser
L'accesso a Defender for Endpoint viene eseguito tramite un browser, che supporta i browser seguenti:

- Microsoft Edge
- Internet Explorer versione 11
- Google Chrome

> [!NOTE]
> Mentre altri browser potrebbero funzionare, i browser menzionati sono quelli supportati.


## <a name="hardware-and-software-requirements"></a>Requisiti hardware e software

### <a name="supported-windows-versions"></a>Versioni di Windows supportate
- Windows 7 SP1 Enterprise ([Richiede ESU per il supporto](https://docs.microsoft.com/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq). )
- Windows 7 SP1 Pro ([Richiede ESU per il supporto](https://docs.microsoft.com/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq). )
- Windows 8.1 Enterprise
- Windows 8.1 Pro
- Windows 10 Enterprise
- [Windows 10 Enterprise LTSC](https://docs.microsoft.com/windows/whats-new/ltsc/)
- Windows 10 Education
- Windows 10 Pro
- Windows 10 Pro Education
- Windows Server
  - Windows Server 2008 R2 SP1
  - Windows Server 2012 R2
  - Windows Server 2016
  - Windows Server, versione 1803 o successiva
  - Windows Server 2019
- Desktop virtuale Windows

I dispositivi nella rete devono eseguire una di queste edizioni.

I requisiti hardware per Defender per Endpoint nei dispositivi sono gli stessi per le edizioni supportate.

> [!NOTE]
> I computer che eseguono versioni per dispositivi mobili di Windows (ad esempio Windows CE e Windows 10 Mobile) non sono supportati.
>
> Le macchine virtuali che eseguono Windows 10 Enterprise 2016 LTSB potrebbero riscontrare problemi di prestazioni se eseguite su piattaforme di virtualizzazione non Microsoft.
>
> Per gli ambienti virtuali, ti consigliamo di usare Windows 10 Enterprise LTSC 2019 o versione successiva.


### <a name="other-supported-operating-systems"></a>Altri sistemi operativi supportati
- Android
- Linux
- macOS

> [!NOTE]
> Per il funzionamento dell'integrazione, dovrai conoscere esattamente le distribuzioni Linux e le versioni di Android e macOS compatibili con Defender for Endpoint.



### <a name="network-and-data-storage-and-configuration-requirements"></a>Requisiti di archiviazione e configurazione di rete e dati
Quando esegui l'onboarding guidato per la prima volta, devi scegliere dove archiviare le informazioni relative a Microsoft Defender for Endpoint: nell'Unione Europea, nel Regno Unito o nel datacenter degli Stati Uniti.

> [!NOTE]
> - Non è possibile modificare il percorso di archiviazione dei dati dopo la prima installazione.
> - Per altre [informazioni su dove](data-storage-privacy.md) e come Microsoft archivia i dati, consulta Microsoft Defender per l'archiviazione e la privacy dei dati degli endpoint.


### <a name="diagnostic-data-settings"></a>Impostazioni dei dati di diagnostica

> [!NOTE]
> Microsoft Defender for Endpoint non richiede alcun livello di diagnostica specifico purché sia abilitato.

Verificare che il servizio dati di diagnostica sia abilitato in tutti i dispositivi dell'organizzazione.
Per impostazione predefinita, questo servizio è abilitato. È consigliabile verificare che i dati dei sensori siano da essi.

Usa la riga di comando per controllare il tipo di avvio del servizio dati di diagnostica **di Windows 10:**

1. Apri un prompt della riga di comando con privilegi elevati nel dispositivo:

   1.  Passare a **Start** e digitare **cmd**.

   1.  Fare clic con il pulsante destro del mouse su **Prompt dei comandi** e scegliere **Esegui come amministratore**.

2. Immettere il comando seguente e premere **INVIO**:

   ```console
   sc qc diagtrack
   ```

   Se il servizio è abilitato, il risultato dovrebbe essere simile allo screenshot seguente:

   ![Risultato del comando sc query per diagtrack](images/windefatp-sc-qc-diagtrack.png)


Dovrai impostare l'avvio automatico del servizio se il START_TYPE **non** è impostato su **AUTO_START**.


**Usa la riga di comando per impostare il servizio dati di diagnostica di Windows 10 per l'avvio automatico:**

1.  Aprire un prompt della riga di comando con privilegi elevati nell'endpoint:

    1. Passare a **Start** e digitare **cmd**.

    1. Fare clic con il pulsante destro del mouse su **Prompt dei comandi** e scegliere **Esegui come amministratore**.

2.  Immettere il comando seguente e premere **INVIO**:

    ```console
    sc config diagtrack start=auto
    ```

3.  Viene visualizzato un messaggio di esito positivo. Verificare la modifica immettendo il comando seguente e premere **INVIO:**

    ```console
    sc qc diagtrack
    ```


#### <a name="internet-connectivity"></a>Connessione Internet
La connettività Internet nei dispositivi è necessaria direttamente o tramite proxy.

Il sensore Defender for Endpoint può utilizzare una larghezza di banda media giornaliera di 5 MB per comunicare con il servizio cloud Defender for Endpoint e segnalare i dati informatici. Le attività una-off come i caricamenti di file e la raccolta di pacchetti di analisi non sono incluse in questa larghezza di banda media giornaliera.

Per ulteriori informazioni sulle impostazioni di configurazione del proxy aggiuntive, vedere [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md).

Prima di eseguire l'onboard di dispositivi, è necessario che il servizio dati di diagnostica sia abilitato. Il servizio è abilitato per impostazione predefinita in Windows 10.


## <a name="microsoft-defender-antivirus-configuration-requirement"></a>Requisiti di configurazione di Microsoft Defender Antivirus
L'agente Defender for Endpoint dipende dalla capacità di Microsoft Defender Antivirus di analizzare i file e fornire informazioni su di essi.

Configura gli aggiornamenti di Security Intelligence nel Defender per i dispositivi endpoint indipendentemente dal fatto che Microsoft Defender Antivirus sia l'antimalware attivo o meno. Per altre informazioni, vedi [Gestire gli aggiornamenti di Microsoft Defender Antivirus e applicare le linee di base.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus)

Quando Microsoft Defender Antivirus non è l'antimalware attivo nell'organizzazione e usi il servizio Defender for Endpoint, Microsoft Defender Antivirus passa alla modalità passiva.

Se l'organizzazione ha disattivato Microsoft Defender Antivirus tramite criteri di gruppo o altri metodi, i dispositivi che sono stati onboarded devono essere esclusi da questo criterio di gruppo.

Se si stanno onboarding server e Microsoft Defender Antivirus non è l'antimalware attivo nei server, Microsoft Defender Antivirus dovrà essere configurato per passare alla modalità passiva o disinstallato. La configurazione dipende dalla versione del server. Per ulteriori informazioni, vedere [Compatibilità con Microsoft Defender Antivirus.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus-compatibility.md)

> [!NOTE]
> I criteri di gruppo normali non si applicano a Protezione da manomissione e le modifiche alle impostazioni di Microsoft Defender Antivirus verranno ignorate quando Protezione da manomissione è impostata su Protezione da manomissione.


## <a name="microsoft-defender-antivirus-early-launch-antimalware-elam-driver-is-enabled"></a>Il driver Microsoft Defender Antivirus Early Launch Antimalware (ELAM) è abilitato
Se si esegue Microsoft Defender Antivirus come prodotto antimalware principale nei dispositivi, l'onboard dell'agente Defender for Endpoint verrà eseguito correttamente.

Se stai eseguendo un client antimalware di terze parti e usi soluzioni di gestione dei dispositivi mobili o Microsoft Endpoint Manager (current branch), dovrai assicurarti che il driver ELAM di Microsoft Defender Antivirus sia abilitato. Per altre informazioni, vedi [Verificare che Microsoft Defender Antivirus non sia disabilitato dai criteri.](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)


## <a name="related-topics"></a>Argomenti correlati
- [Configurare Microsoft Defender per la distribuzione degli endpoint](production-deployment.md)
- [Dispositivi onboard](onboard-configure.md)
