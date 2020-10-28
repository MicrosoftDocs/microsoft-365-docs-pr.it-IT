---
title: Dispositivi di bordo di Windows 10 con Configuration Manager
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Utilizzare Configuration Manager per distribuire il pacchetto di configurazione nei dispositivi in modo che siano onboarded al servizio.
ms.openlocfilehash: ea1b0cba10dc3e7120192e0c0ee87e2e354f1cc2
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769479"
---
# <a name="onboard-windows-10-devices-using-configuration-manager"></a>Dispositivi di bordo di Windows 10 con Configuration Manager

**Si applica a:**

- [Prevenzione della perdita di dati (DLP) di Microsoft 365 endpoint](/microsoft-365/compliance/endpoint-dlp-learn-about)
- System Center Configuration Manager 2012 R2

### <a name="onboard-devices-using-system-center-configuration-manager"></a>Dispositivi di bordo tramite System Center Configuration Manager

1. Aprire il file con estensione zip del pacchetto di configurazione di Configuration Manager ( *DeviceComplianceOnboardingPackage.zip* ) scaricato dalla procedura guidata di onboarding dei servizi. È anche possibile ottenere il pacchetto dal [centro conformità Microsoft](https://compliance.microsoft.com/).

2. Nel riquadro di spostamento selezionare impostazioni onboarding del dispositivo di **configurazione**  >  **Device Onboarding**  >  **Onboarding** .

3. Nel campo **metodo di distribuzione** selezionare **Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602** .
 
4. Selezionare **Download package** e salvare il file con estensione zip.

5. Estrarre il contenuto del file con estensione zip in una posizione condivisa e di sola lettura a cui è possibile accedere gli amministratori di rete che distribuiscono il pacchetto. È necessario disporre di un file denominato *DeviceComplianceOnboardingScript. cmd* .

6. Distribuire il pacchetto attenendosi alla procedura descritta nell'articolo [packages and programmes in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\)) .

7. Scegliere un insieme di dispositivi predefinito per la distribuzione del pacchetto.

> [!NOTE]
> Microsoft 365 endpoint la prevenzione della perdita dei dati non supporta l'onboarding durante la fase [di out-of-Box Experience (OOBE)](https://answers.microsoft.com/en-us/windows/wiki/windows_10/how-to-complete-the-windows-10-out-of-box/47e3f943-f000-45e3-8c5c-9d85a1a0cf87) . Assicurarsi che gli utenti completino OOBE dopo l'esecuzione dell'installazione o dell'aggiornamento di Windows.

>[!TIP]
> Dopo aver eseguito l'onboarding del dispositivo, è possibile scegliere di eseguire un test di rilevamento per verificare che un dispositivo sia correttamente onboarded to the Service. Per ulteriori informazioni, vedere [eseguire un test di rilevamento su un dispositivo ATP Microsoft Defender appena integrato](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test).
>
> Si noti che è possibile creare una regola di rilevamento su un'applicazione di Configuration Manager per controllare continuamente se un dispositivo è stato onboarded. Un'applicazione è un tipo di oggetto diverso rispetto a un pacchetto e a un programma.
> Se un dispositivo non è ancora stato onboarded (a causa del completamento di OOBE in sospeso o di qualsiasi altro motivo), Configuration Manager ritenterà di onboard il dispositivo finché la regola non rileverà la modifica dello stato.
> 
> Questo comportamento può essere ottenuto creando una regola di rilevamento che controlla se il valore del registro di sistema "OnboardingState" (di tipo REG_DWORD) = 1.
> Questo valore del registro di sistema si trova in "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status".
Per ulteriori informazioni, vedere [Configure Detection Methods in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682159\(v=technet.10\)#step-4-configure-detection-methods-to-indicate-the-presence-of-the-deployment-type).

### <a name="configure-sample-collection-settings"></a>Configurare le impostazioni di raccolta di esempio

Per ogni dispositivo, è possibile impostare un valore di configurazione per indicare se è possibile raccogliere campioni dal dispositivo quando viene effettuata una richiesta tramite Microsoft Defender Security Center per inviare un file per un'analisi approfondita.

>[!NOTE]
>Queste impostazioni di configurazione vengono in genere eseguite tramite Configuration Manager. 

È possibile impostare una regola di conformità per l'elemento di configurazione in Configuration Manager per modificare l'impostazione di condivisione di esempio in un dispositivo.

Questa regola deve essere un *elemento di configurazione* della regola di conformità che consente di impostare il valore di una chiave del registro di sistema nei dispositivi di destinazione per assicurarsi che siano reclami.

La configurazione viene impostata tramite la seguente voce della chiave del registro di sistema:

```
Path: “HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection”
Name: "AllowSampleCollection"
Value: 0 or 1
```
Dove:<br>
Il tipo di chiave è una D-WORD. <br>
I valori possibili sono:
- 0-non consente la condivisione di campioni da questo dispositivo
- 1-consente la condivisione di tutti i tipi di file da questo dispositivo

Il valore predefinito nel caso in cui la chiave del registro di sistema non esiste è 1.

Per ulteriori informazioni sulla conformità di System Center Configuration Manager, vedere [Introduction to Compliance Settings in System center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\)).


## <a name="other-recommended-configuration-settings"></a>Altre impostazioni di configurazione consigliate
Dopo aver eseguito il servizio di onboarding per i dispositivi, è importante sfruttare le funzionalità di protezione delle minacce incluse, consentendo loro di utilizzare le seguenti impostazioni di configurazione consigliate.

### <a name="device-collection-configuration"></a>Configurazione raccolta dispositivi
Se si utilizza endpoint Configuration Manager, versione 2002 o successiva, è possibile scegliere di ampliare la distribuzione per includere server o client di livello più basso.


### <a name="next-generation-protection-configuration"></a>Configurazione di protezione di prossima generazione

Sono consigliate le impostazioni di configurazione seguenti:

**Analisi**

- Analizzare i dispositivi di archiviazione rimovibili come unità USB: Sì

**Protezione in tempo reale**

- Abilitare il monitoraggio comportamentale: Sì
- Abilitare la protezione da applicazioni potenzialmente indesiderate al download e prima dell'installazione: Sì

**Servizio di protezione cloud**

- Tipo di appartenenza del servizio protezione cloud: appartenenza avanzata

**Riduzione della superficie di attacco** Configurare tutte le regole disponibili da controllare.

>[!NOTE]
> Il blocco di queste attività può interrompere i processi aziendali legittimi. L'approccio migliore consiste nell'impostare tutto per il controllo, identificare quelli che possono essere attivati e quindi abilitare tali impostazioni sugli endpoint che non dispongono di rilevamenti falsi positivi.

**Protezione di rete**

Prima di abilitare la protezione di rete in modalità di controllo o di blocco, verificare di aver installato l'aggiornamento della piattaforma antimalware, che può essere ottenuto dalla [pagina di supporto](https://support.microsoft.com/en-us/help/4560203/windows-defender-anti-malware-platform-binaries-are-missing).


**Accesso alla cartella controllata**

Abilitare la funzionalità in modalità di controllo per almeno 30 giorni. Dopo questo periodo, esaminare i rilevamenti e creare un elenco di applicazioni che possono essere scritte in directory protette.

Per ulteriori informazioni, vedere [valutare l'accesso alla cartella controllata](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/evaluate-controlled-folder-access).


## <a name="offboard-devices-using-configuration-manager"></a>Dispositivi di trasferisce tramite Configuration Manager

Per motivi di sicurezza, il pacchetto utilizzato per i dispositivi di trasferisce scadrà 30 giorni dopo la data in cui è stato scaricato. I pacchetti di Offboarding scaduti inviati a un dispositivo verranno rifiutati. Quando si scarica un pacchetto di Offboarding, viene inviata una notifica alla data di scadenza dei pacchetti e verrà incluso anche il nome del pacchetto.

> [!NOTE]
> I criteri di onboarding e offboarding non devono essere distribuiti contemporaneamente nello stesso dispositivo, altrimenti ciò provocherà collisioni imprevedibili.

### <a name="offboard-devices-using-microsoft-endpoint-configuration-manager-current-branch"></a>Dispositivi di trasferisce che utilizzano la filiale corrente di Microsoft endpoint Configuration Manager

Se si utilizza la succursale corrente di Microsoft endpoint Configuration Manager, vedere [creare un file di configurazione di Offboarding](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#create-an-offboarding-configuration-file).

### <a name="offboard-devices-using-system-center-2012-r2-configuration-manager"></a>Dispositivi di trasferisce che utilizzano System Center 2012 R2 Configuration Manager

1. Ottenere il pacchetto offboarding dal [centro conformità Microsoft](https://compliance.microsoft.com/):

2. Nel riquadro di spostamento, selezionare **Impostazioni**  >   **onboarding del dispositivo** >  **offboarding** .

3. Selezionare Windows 10 come sistema operativo.

4. Nel campo **metodo di distribuzione** selezionare **Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602** .
    
5. Selezionare **Download package** e salvare il file con estensione zip.

6. Estrarre il contenuto del file con estensione zip in una posizione condivisa e di sola lettura a cui è possibile accedere gli amministratori di rete che distribuiscono il pacchetto. È necessario disporre di un file denominato *DeviceComplianceOffboardingScript_valid_until_YYYY-mm-dd. cmd* .

7. Distribuire il pacchetto attenendosi alla procedura descritta nell'articolo [packages and programmes in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\)) .

8. Scegliere un insieme di dispositivi predefinito per la distribuzione del pacchetto.

> [!IMPORTANT]
> Offboarding fa in modo che il dispositivo smetta di inviare i dati del sensore al portale, ma i dati del dispositivo, incluso il riferimento agli avvisi che ha avuto, verranno conservati per un massimo di 6 mesi.


## <a name="monitor-device-configuration"></a>Monitorare la configurazione del dispositivo

Se si utilizza la succursale corrente di Microsoft endpoint Configuration Manager, utilizzare il Dashboard Microsoft Defender ATP incorporato nella console di Configuration Manager. Per ulteriori informazioni, vedere [Microsoft Defender Advanced Threat Protection-monitor](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#monitor).

Se si utilizza System Center 2012 R2 Configuration Manager, il monitoraggio è costituito da due parti:

1. La conferma del pacchetto di configurazione è stata distribuita correttamente ed è in esecuzione (o è stata eseguita correttamente) sui dispositivi della rete.

2. Verifica che i dispositivi siano compatibili con il servizio di prevenzione della perdita di dati di Microsoft 365 endpoint (questo garantisce che il dispositivo possa completare il processo di onboarding e possa continuare a segnalare i dati al servizio).

### <a name="confirm-the-configuration-package-has-been-correctly-deployed"></a>Confermare che il pacchetto di configurazione è stato distribuito correttamente

1. Nella console di Configuration Manager, fare clic su **monitoraggio** nella parte inferiore del riquadro di spostamento.

2. Selezionare **Panoramica** e quindi **distribuzioni** .

3. Selezionare la distribuzione con il nome del pacchetto.

4. Esaminare gli indicatori di stato in **statistiche di completamento** e stato del **contenuto** .

    Se sono presenti distribuzioni non riuscite (dispositivi con **errori** , **requisiti non soddisfatti** o **Stati non riusciti** ), potrebbe essere necessario risolvere i problemi relativi ai dispositivi. Per ulteriori informazioni, vedere [risolvere i problemi relativi all'onboarding di Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding).

    ![Configuration Manager che mostra la distribuzione completata senza errori](../media/sccm-deployment.png)

### <a name="check-that-the-devices-are-compliant-with-the-microsoft-365-endpoint-data-loss-prevention-service"></a>Verificare che i dispositivi siano compatibili con il servizio di prevenzione della perdita di dati di Microsoft 365 endpoint

È possibile impostare una regola di conformità per l'elemento di configurazione in System Center 2012 R2 Configuration Manager per monitorare la distribuzione.

> [!NOTE]
> Questa procedura e la voce del registro di sistema si applicano all'endpoint DLP e alla protezione avanzata dalle minacce.

Questa regola deve essere un elemento di configurazione di una regola di conformità *non correttivo* che monitora il valore di una chiave del registro di sistema nei dispositivi di destinazione.

Monitorare la voce della chiave del registro di sistema seguente:
```
Path: “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status”
Name: “OnboardingState”
Value: “1”
```
Per ulteriori informazioni, vedere [Introduzione alle impostazioni di conformità in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\)).

## <a name="related-topics"></a>Argomenti correlati
- [Dispositivi di bordo di Windows 10 con criteri di gruppo](dlp-configure-endpoints-gp.md)
- [Dispositivi di bordo di Windows 10 con strumenti di gestione dei dispositivi mobili](dlp-configure-endpoints-mdm.md)
- [Dispositivi di bordo di Windows 10 con uno script locale](dlp-configure-endpoints-script.md)
- [Dispositivi VDI (Virtual Desktop Infrastructure) non permanenti di bordo](dlp-configure-endpoints-vdi.md)
- [Eseguire un test di rilevamento su un dispositivo ATP Microsoft Defender appena integrato](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [Risolvere i problemi di onboarding di Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
