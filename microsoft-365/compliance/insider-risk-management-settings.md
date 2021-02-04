---
title: Impostazioni di gestione dei rischi Insider
description: Informazioni sulle impostazioni di gestione dei rischi Insider in Microsoft 365
keywords: Microsoft 365, gestione dei rischi Insider, gestione dei rischi, conformità
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
ms.openlocfilehash: ba851a7ad6243b9b3b6bc69432bd2b3036d6b269
ms.sourcegitcommit: c0cfb9b354db56fdd329aec2a89a9b2cf160c4b0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2021
ms.locfileid: "50094767"
---
# <a name="get-started-with-insider-risk-management-settings"></a>Introduzione alle impostazioni di gestione dei rischi Insider

Le impostazioni di gestione dei rischi Insider si applicano a tutti i criteri di gestione dei rischi Insider, indipendentemente dal modello scelto durante la creazione di un criterio. Le impostazioni vengono configurate usando il **controllo delle** impostazioni dei rischi Insider che si trova nella parte superiore di tutte le schede di gestione dei rischi Insider. Queste impostazioni controllano i componenti dei criteri per le aree seguenti:

- Privacy
- Indicatori
- Sequenze temporali dei criteri
- Rilevamenti intelligenti
- Esportare avvisi (anteprima)
- Gruppi di utenti con priorità (anteprima)
- Asset fisici con priorità (anteprima)
- Flussi di Power Automate (anteprima)
- Microsoft Teams (anteprima)

Prima di iniziare e creare criteri di gestione dei rischi Insider, è importante comprendere queste impostazioni e scegliere i livelli di impostazione migliori per le esigenze di conformità per l'organizzazione.

## <a name="privacy"></a>Privacy

La protezione della privacy degli utenti che hanno corrispondenze ai criteri è importante e può contribuire a promuovere l'obiettività nell'analisi e nell'analisi dei dati per gli avvisi di rischio Insider. Per gli utenti con una corrispondenza ai criteri di rischio Insider, è possibile scegliere una delle impostazioni seguenti:

- **Mostra versioni anonime** dei nomi utente: i nomi degli utenti sono anonimi per impedire ad amministratori, investigatori di dati e revisori di vedere chi è associato agli avvisi dei criteri. Ad esempio, un utente "Grace Grace" apparirebbe con uno pseudonimo casuale, ad esempio "AnonIS8-988" in tutte le aree dell'esperienza di gestione dei rischi insider. La scelta di questa impostazione consente di anonimizzare tutti gli utenti con corrispondenze dei criteri correnti e precedenti e si applica a tutti i criteri. Le informazioni del profilo utente nell'avviso per i rischi Insider e i dettagli del caso non saranno disponibili quando si sceglie questa opzione. Tuttavia, i nomi utente vengono visualizzati quando si aggiungono nuovi utenti ai criteri esistenti o quando si assegnano utenti a nuovi criteri. Se si sceglie di disattivare questa impostazione, verranno visualizzati i nomi utente per tutti gli utenti che hanno corrispondenze ai criteri correnti o precedenti.
- **Non mostrare versioni anonime** dei nomi utente: i nomi utente vengono visualizzati per tutte le corrispondenze dei criteri correnti e precedenti per avvisi e casi. Le informazioni del profilo utente (nome, titolo, alias e organizzazione o reparto) vengono visualizzate per l'utente per tutti gli avvisi e i casi di gestione dei rischi Insider.

![Impostazioni di privacy per la gestione dei rischi Insider](../media/insider-risk-settings-privacy.png)

## <a name="indicators"></a>Indicatori

I modelli di criteri di rischio Insider definiscono il tipo di attività di rischio che si desidera rilevare e analizzare. Ogni modello di criteri è basato su indicatori specifici che corrispondono a trigger e attività di rischio specifici. Tutti gli indicatori sono disabilitati per impostazione predefinita ed è necessario selezionare uno o più indicatori di criteri prima di configurare un criterio di gestione dei rischi Insider.

Gli avvisi vengono attivati dai criteri quando gli utenti eseguono attività correlate agli indicatori dei criteri che soddisfano una soglia obbligatoria. La gestione dei rischi Insider utilizza due tipi di indicatori:

- **Attivazione di eventi:** eventi che determinano se un utente è attivo per un criterio di gestione dei rischi Insider. Se un utente viene aggiunto a un criterio di gestione dei rischi Insider non dispone di un evento di attivazione, l'attività dell'utente non viene valutata dal criterio. Ad esempio, l'utente A viene  aggiunto a un criterio creato dal furto di dati allontanando il modello di criteri degli utenti e il criterio e il connettore risorse umane di Microsoft 365 sono configurati correttamente. Fino a quando l'utente A non ha una data di terminazione riportata dal connettore hr, le attività dell'utente A non vengono valutate da questo criterio di gestione dei rischi Insider per il rischio. Un altro esempio di evento di attivazione è se un utente ha un *avviso* di criteri DLP di gravità elevata quando si utilizzano i criteri di *perdita di* dati.
- **Indicatori dei criteri:** indicatori inclusi nei criteri di gestione dei rischi Insider utilizzati per determinare un punteggio di rischio per un utente nell'ambito. Questi indicatori di criteri vengono attivati solo dopo che si verifica un evento di attivazione per un utente. Alcuni esempi di indicatori dei criteri sono quando un utente copia i dati nei servizi di archiviazione cloud personali o nei dispositivi di archiviazione portatili oppure se un utente condivide file e cartelle interni con parti esterne non autorizzate.

Gli indicatori dei criteri vengono segmentati nelle aree seguenti. È possibile scegliere gli indicatori per attivare e personalizzare i limiti degli eventi degli indicatori per ogni livello di indicatore quando si crea un criterio di rischio Insider:

- **Indicatori di Office:** includono gli indicatori dei criteri per i siti di SharePoint, Teams e la messaggistica di posta elettronica.
- **Indicatori di dispositivo:** includono indicatori di criteri per attività come la condivisione di file in rete o con dispositivi. Gli indicatori includono attività che coinvolgono Microsoft Office file, . File CSV e . File PDF. Se si seleziona **Indicatori dispositivo,** l'attività viene elaborata solo per i dispositivi con Windows 10 Build 1809 o versione successiva. Per altre informazioni sulla configurazione dei dispositivi per l'integrazione con il rischio Insider, vedi la seguente sezione Abilitare gli indicatori di dispositivo [e l'onboarding dei dispositivi.](insider-risk-management-settings.md#OnboardDevices)
- **Indicatore di violazione dei** criteri di sicurezza: sono inclusi gli indicatori di Microsoft Defender per endpoint correlati all'installazione di software non approvata o dannosa o che ignorano i controlli di sicurezza. Per ricevere avvisi nella gestione dei rischi Insider, devi avere una licenza di Defender for Endpoint attiva e l'integrazione dei rischi Insider abilitata. Per altre informazioni sulla configurazione di Defender per Endpoint per l'integrazione della gestione dei rischi Insider, vedi [Configurare le funzionalità avanzate in Microsoft Defender for Endpoint.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-features\#share-endpoint-alerts-with-microsoft-compliance-center)
- **Punteggi del punteggio di rischio**: includono l'aumento del punteggio di rischio per attività insolite o violazioni dei criteri passate. L'abilitazione dei punteggi di rischio aumenta i punteggi di rischio e la probabilità di avvisi per questi tipi di attività. I punteggi di rischio possono essere selezionati solo se sono selezionati uno o più indicatori.

![Impostazioni degli indicatori di gestione dei rischi Insider](../media/insider-risk-settings-indicators.png)

In alcuni casi, è possibile limitare gli indicatori dei criteri di rischio Insider applicati ai criteri di rischio Insider nell'organizzazione. È possibile disattivare gli indicatori dei criteri per aree specifiche disabilitandoli da tutti i criteri di rischio Insider. Non è possibile modificare gli eventi di attivazione per i modelli di criteri di rischio Insider.

Per definire gli indicatori dei criteri di rischio Insider abilitati in tutti i criteri di rischio **Insider,** passare a Indicatori di impostazioni dei rischi Insider e selezionare uno o  >   più indicatori di criteri. Gli indicatori selezionati nella pagina Impostazioni indicatori non possono essere configurati singolarmente durante la creazione o la modifica di un criterio di rischio Insider nella procedura guidata dei criteri.

>[!NOTE]
>La visualizzazione dei nuovi utenti aggiunti manualmente nel dashboard degli utenti potrebbe richiedere diverse **ore.** La visualizzazione delle attività per i 90 giorni precedenti per questi utenti può richiedere fino a 24 ore. Per visualizzare le attività per gli utenti aggiunti manualmente, selezionare l'utente nel **dashboard** Utenti e aprire la **scheda Attività** utente nel riquadro dei dettagli.

### <a name="enable-device-indicators-and-onboard-devices"></a>Abilitare gli indicatori di dispositivo e i dispositivi di onboard
<a name="OnboardDevices"> </a>

Per abilitare il monitoraggio delle attività di rischio nei dispositivi e includere indicatori dei criteri per queste attività, i dispositivi devono soddisfare i requisiti seguenti ed è necessario completare i passaggi di onboarding seguenti.

#### <a name="step-1-prepare-your-endpoints"></a>Passaggio 1: Preparare gli endpoint

Assicurati che i dispositivi Windows 10 che si prevede di segnalare nella gestione dei rischi Insider soddisfino questi requisiti.

1. Deve eseguire Windows 10 x64 build 1809 o versione successiva e deve aver installato l'aggiornamento di [Windows 10 (OS Build 17763.1075)](https://support.microsoft.com/help/4537818/windows-10-update-kb4537818) dal 20 febbraio 2020.
2. Tutti i dispositivi devono essere [aggiunti ad Azure Active Directory (AAD)](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join) o aggiunto ad Azure AD ibrido.
3. Installare il browser Microsoft Chromium Edge nel dispositivo endpoint per monitorare le azioni per l'attività di caricamento nel cloud. Vedere [Scaricare il nuovo Microsoft Edge basato su Chromium](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium).

#### <a name="step-2-onboarding-devices"></a>Passaggio 2: Onboarding dei dispositivi
<a name="OnboardStep2"> </a>

Devi abilitare il monitoraggio dei dispositivi e l'onboarder degli endpoint prima di poter monitorare le attività di gestione dei rischi Insider in un dispositivo. Entrambe le azioni vengono eseguite nel portale Conformità Microsoft 365.

Quando vuoi eseguire l'onboarded dei dispositivi che non sono stati ancora onboarded, scaricherai lo script appropriato e distribuirai come descritto nei passaggi seguenti.

Se i dispositivi sono già presenti in [Microsoft Defender per endpoint](https://docs.microsoft.com/windows/security/threat-protection/), verranno visualizzati nell'elenco dei dispositivi gestiti. Segui [il passaggio 3: se i dispositivi sono stati onboarded in Microsoft Defender per Endpoint](insider-risk-management-settings.md#OnboardStep3) nella sezione successiva.

In questo scenario di distribuzione eseguirai l'onboarded dei dispositivi che non sono stati ancora onboarded e vuoi semplicemente monitorare le attività di rischio Insider nei dispositivi Windows 10.

1. Aprire il [Centro conformità Microsoft](https://compliance.microsoft.com).
2. Aprire la pagina delle impostazioni del Centro conformità e scegliere **Onboarding di dispositivi**.

   > [!NOTE]
   > Anche se in genere sono necessari circa 60 secondi perché l'onboarding dei dispositivi sia abilitato, attendere fino a 30 minuti prima di contattare il supporto tecnico Microsoft.

3. Scegliere **Gestione dispositivi** per aprire l'elenco **Dispositivi**. L'elenco sarà vuoto finché non si caricano dispositivi.
4. Scegliere **Onboarding** per avviare il processo di onboarding.
5. Scegli la modalità di distribuzione in questi altri dispositivi nell'elenco Dei metodi **di** distribuzione e quindi scarica **il pacchetto.**
6. Seguire le procedure appropriate in [Strumenti e metodi di onboarding per i dispositivi Windows 10](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints). Questo collegamento porta a una pagina di destinazione in cui è possibile accedere alle procedure di Microsoft Defender per endpoint che corrispondono al pacchetto di distribuzione selezionato nel passaggio 5:
    - Onboarding di dispositivi Windows 10 con Criteri di gruppo
    - Onboarding di dispositivi Windows 10 con Microsoft Endpoint Configuration Manager
    - Onboarding di dispositivi Windows 10 con gli strumenti di Gestione dispositivi mobili
    - Onboarding di dispositivi Windows 10 con uno script locale
    - Onboarding di dispositivi VDI (Virtual Desktop Infrastructure) non persistenti.

Una volta completata l'operazione e l'onboarded dell'endpoint, dovrebbe essere visibile nell'elenco dei dispositivi e l'endpoint inizierà a segnalare i log delle attività di controllo alla gestione dei rischi Insider.

> [!NOTE]
> Questa esperienza richiede la licenza. Se non si ha la licenza necessaria, i dati non saranno visibili o accessibili.

#### <a name="step-3-if-you-have-devices-onboarded-into-microsoft-defender-for-endpoint"></a>Passaggio 3: se i dispositivi sono stati onboarded in Microsoft Defender per Endpoint
<a name="OnboardStep3"> </a>

Se Microsoft Defender for Endpoint è già distribuito e sono presenti report degli endpoint, tutti questi endpoint verranno visualizzati nell'elenco dei dispositivi gestiti. Puoi continuare a eseguire l'onboarding di nuovi dispositivi nella gestione dei rischi Insider per espandere la copertura usando la sezione [Passaggio 2: Onboarding dei dispositivi.](insider-risk-management-settings.md#OnboardStep2)

1. Aprire il [Centro conformità Microsoft](https://compliance.microsoft.com).
2. Aprire la pagina delle impostazioni del Centro conformità e scegliere **Abilita monitoraggio dispositivi**.
3. Scegliere **Gestione dispositivi** per aprire l'elenco **Dispositivi**. Dovrebbe essere visualizzato l'elenco dei dispositivi che già inviano report a Microsoft Defender per endpoint.
4. Scegli **Onboarding** se devi eseguire l'onboarding di più dispositivi.
5. Scegli il modo in cui vuoi eseguire la distribuzione in questi altri dispositivi nell'elenco **Dei** metodi di distribuzione e quindi scarica **il pacchetto.**
6. Seguire le procedure appropriate in [Strumenti e metodi di onboarding per i dispositivi Windows 10](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints). Questo collegamento porta a una pagina di destinazione in cui è possibile accedere alle procedure di Microsoft Defender per endpoint che corrispondono al pacchetto di distribuzione selezionato nel passaggio 5:
    - Onboarding di dispositivi Windows 10 con Criteri di gruppo
    - Onboarding di dispositivi Windows 10 con Microsoft Endpoint Configuration Manager
    - Onboarding di dispositivi Windows 10 con gli strumenti di Gestione dispositivi mobili
    - Onboarding di dispositivi Windows 10 con uno script locale
    - Onboarding di dispositivi VDI (Virtual Desktop Infrastructure) non persistenti.

Una volta completata l'operazione e l'onboarded dell'endpoint, dovrebbe essere visibile nella tabella Dispositivi e l'endpoint inizierà a segnalare i log delle attività di controllo alla gestione dei rischi Insider. 

> [!NOTE]
>Questa esperienza richiede la licenza. Se non si ha la licenza necessaria, i dati non saranno visibili o accessibili.

### <a name="indicator-level-settings-preview"></a>Impostazioni del livello dell'indicatore (anteprima)

Quando si crea un criterio nella procedura guidata dei criteri, è possibile configurare il modo in cui il numero giornaliero di eventi di rischio deve influenzare il punteggio di rischio per gli avvisi di rischio Insider. Queste impostazioni degli indicatori consentono di controllare il modo in cui il numero di occorrenze di eventi di rischio nell'organizzazione deve influire sul punteggio di rischio e, di conseguenza, sulla gravità dell'avviso associata per questi eventi. Se si preferisce, è anche possibile scegliere di mantenere i livelli di soglia degli eventi predefiniti consigliati da Microsoft per tutti gli indicatori abilitati.

Ad esempio, si decide di abilitare gli indicatori di SharePoint nelle impostazioni dei criteri di rischio Insider  e di impostare soglie personalizzate per gli eventi di SharePoint quando si configurano gli indicatori per un nuovo criterio di perdita di dati di rischio Insider. Durante la procedura guidata dei criteri di rischio Insider, è possibile configurare tre diversi livelli di evento giornalieri per ogni indicatore di SharePoint per influenzare il punteggio di rischio per gli avvisi associati a questi eventi.

![Impostazioni degli indicatori personalizzati per la gestione dei rischi Insider](../media/insider-risk-custom-indicators.png)

Per il primo livello di evento giornaliero, impostare la soglia su *10* o più eventi al giorno per un impatto inferiore sul punteggio di rischio per gli eventi, *20* o più eventi al giorno per un impatto medio sul punteggio di rischio per gli eventi e *30* o più eventi al giorno un impatto maggiore sul punteggio di rischio per gli eventi. Queste impostazioni in effetti significano:

- Se sono presenti da 1 a 9 eventi di SharePoint che si verificano dopo l'attivazione dell'evento, i punteggi di rischio hanno un impatto minimo e tendono a non generare un avviso.
- Se sono presenti 10-19 eventi di SharePoint che si verificano dopo un evento di attivazione, il punteggio di rischio è intrinsecamente inferiore e i livelli di gravità degli avvisi tendono a essere a un livello basso.
- Se sono presenti 20-29 eventi di SharePoint che si verificano dopo un'attivazione, il punteggio di rischio è intrinsecamente superiore e i livelli di gravità degli avvisi tendono a essere a un livello medio.
- Se sono presenti 30 o più eventi di SharePoint che si verificano dopo un'attivazione, il punteggio di rischio è intrinsecamente superiore e i livelli di gravità degli avvisi tendono a essere di alto livello.

## <a name="policy-timeframes"></a>Tempistiche dei criteri

I tempi dei criteri consentono di definire i periodi di revisione passati e futuri che vengono attivati dopo le corrispondenze dei criteri in base a eventi e attività per i modelli di criteri di gestione dei rischi Insider. A seconda del modello di criterio scelto, sono disponibili i seguenti tempi per i criteri:

- **Finestra di attivazione:** disponibile per  tutti i modelli di criteri, la finestra attivazione è il numero di giorni definito per l'attivazione della finestra dopo **un** evento di attivazione. La finestra viene attivata da 1 a 30 giorni dopo che si verifica un evento di attivazione per qualsiasi utente assegnato al criterio. Ad esempio, hai configurato un criterio di gestione dei rischi Insider e impostato la finestra *di attivazione* su 30 giorni. Sono trascorsi diversi mesi dalla configurazione del criterio e si verifica un evento di attivazione per uno degli utenti inclusi nel criterio. L'evento di attivazione attiva la *finestra di* attivazione e il criterio è attivo per tale utente per 30 giorni dopo l'evento di attivazione.
- **Rilevamento delle attività passate:** disponibile  per tutti i modelli di criteri, il rilevamento delle attività passate è il numero definito di giorni in cui la finestra viene attivata **prima** di un evento di attivazione. La finestra viene attivata per 0-180 giorni prima che si verifichi un evento di attivazione per qualsiasi utente assegnato al criterio. Ad esempio, hai configurato un criterio di gestione dei rischi Insider e impostato il *rilevamento delle attività passate* su 90 giorni. Sono trascorsi diversi mesi dalla configurazione del criterio e si verifica un evento di attivazione per uno degli utenti inclusi nel criterio. L'evento di attivazione  attiva il rilevamento delle attività passate e il criterio raccoglie le attività storici per quell'utente per 90 giorni prima dell'evento di attivazione.

![Impostazioni dell'intervallo di tempo per la gestione dei rischi Insider](../media/insider-risk-settings-timeframes.png)

## <a name="intelligent-detections"></a>Rilevamenti intelligenti

Le impostazioni di rilevamento intelligenti consentono di perfezionare il modo in cui i rilevamenti di attività rischiose vengono elaborati per gli avvisi. In alcune circostanze, potrebbe essere necessario definire i tipi di file da ignorare oppure applicare un livello di rilevamento per i file per definire una barra minima per gli avvisi. Usa queste impostazioni per controllare il volume complessivo degli avvisi, le esclusioni dei tipi di file e i limiti del volume di file.

### <a name="anomaly-detections"></a>Rilevamenti di anomalie

I rilevamenti anomali includono le impostazioni per le esclusioni dei tipi di file e i limiti del volume dei file.

- **Esclusioni dei tipi di** file: per escludere tipi di file specifici da tutti i criteri di gestione dei rischi Insider, immettere le estensioni dei tipi di file separate da virgole. Ad esempio, per escludere determinati tipi di file musicali dalle corrispondenze dei criteri, è possibile immettere *aac,mp3,wav,wma* nel campo **Esclusioni di tipi di** file. I file con queste estensioni verranno ignorati da tutti i criteri di gestione dei rischi Insider.
- **Limite di limitazione del volume di** file: per definire un livello minimo di file prima che gli avvisi attività siano riportati nei criteri di rischio Insider, immettere il numero di file. Ad esempio, immettere "10" se non si desidera generare avvisi di rischio Insider quando un utente scarica 10 file o meno, anche se i criteri considerano questa attività un'anomalia.

### <a name="alert-volume"></a>Volume avviso

Alle attività degli utenti rilevate dai criteri di rischio Insider viene assegnato un punteggio di rischio specifico, che a sua volta determina la gravità dell'avviso (bassa, media, alta). Per impostazione predefinita, verrà generata una determinata quantità di avvisi di gravità bassa, media e alta, ma è possibile aumentare o ridurre il volume in base alle proprie esigenze. Per modificare il volume di avvisi per tutti i criteri di gestione dei rischi Insider, scegliere una delle impostazioni seguenti:

- **Meno avvisi:** verranno visualizzati tutti gli avvisi di gravità elevata, meno avvisi di gravità media e nessun avviso di gravità bassa. Questo livello di impostazione significa che potresti perdere alcuni veri positivi.
- **Volume predefinito:** verranno visualizzati tutti gli avvisi di gravità elevata e una quantità bilanciata di avvisi di gravità media e bassa.
- **Altri avvisi:** verranno visualizzati tutti gli avvisi di gravità media e alta e gli avvisi di gravità più bassa. Questo livello di impostazione potrebbe comportare più falsi positivi.

### <a name="microsoft-defender-for-endpoint-preview"></a>Microsoft Defender for Endpoint (anteprima)

[Microsoft Defender for Endpoint è](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) una piattaforma di sicurezza degli endpoint aziendale progettata per aiutare le reti aziendali a prevenire, rilevare, analizzare e rispondere alle minacce avanzate. Per una migliore visibilità della violazione della sicurezza nell'organizzazione, puoi importare e filtrare gli avvisi di Defender per gli endpoint per le attività usate nei criteri creati dai modelli di criteri di violazione della sicurezza per la gestione dei rischi insider.

A seconda dei tipi di segnali che ti interessano, puoi scegliere di importare gli avvisi per la gestione dei rischi Insider in base allo stato di valutazione degli avvisi di Defender for Endpoint. È possibile definire uno o più degli stati di triage degli avvisi seguenti nelle impostazioni globali da importare:

- Unknown
- Nuova
- In corso
- Risolti

Gli avvisi di Defender per Endpoint vengono importati ogni giorno. A seconda dello stato di triage scelto, potresti visualizzare più attività utente per lo stesso avviso in cui lo stato della triage cambia in Defender per Endpoint.

Ad esempio, se si seleziona *Nuovo,* *In* corso e Risolto per questa impostazione, quando viene generato un avviso di Microsoft Defender per endpoint e lo stato è *Nuovo,* viene importata un'attività di avviso iniziale per l'utente a rischio Insider.  Quando lo stato della valutazione di Defender per endpoint cambia *in In corso,* viene importata una seconda attività per questo avviso per l'utente a rischio Insider. Quando lo stato finale di  valutazione di Defender per endpoint è risolto, viene importata una terza attività per questo avviso per l'utente a rischio Insider. Questa funzionalità consente agli investigatori di seguire l'avanzamento degli avvisi di Defender for Endpoint e di scegliere il livello di visibilità richiesto dall'indagine.

>[!IMPORTANT]
>Dovrai configurare Microsoft Defender per Endpoint nell'organizzazione e abilitare Defender per Endpoint per l'integrazione della gestione dei rischi Insider in Defender Security Center per importare gli avvisi di violazione della sicurezza. Per altre informazioni sulla configurazione di Defender per Endpoint per l'integrazione della gestione dei rischi Insider, vedi [Configurare le funzionalità avanzate in Defender per Endpoint.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-features\#share-endpoint-alerts-with-microsoft-compliance-center)

### <a name="domains-preview"></a>Domini (anteprima)

Le impostazioni del dominio consentono di definire i livelli di rischio per le comunicazioni a domini specifici. Queste comunicazioni includono la condivisione di file, i messaggi di posta elettronica o il download di contenuto. Specificando i domini in queste impostazioni, è possibile aumentare o ridurre il punteggio di rischio per l'attività che avviene con questi domini. Ad esempio, per specificare contoso.com e sales.wingtiptoys.com domini consentiti, immettere "contoso.com sales.wingtiptoys.com" nel **campo Domini** consentiti.

Per ognuna delle impostazioni di dominio seguenti, è possibile immettere fino a 500 domini:

- **Domini non consentiti:** Specificando i domini non consentiti, l'attività che avviene con questi domini avrà *punteggi di rischio* più elevati.
- **Domini consentiti:** Specificando i domini consentiti nelle impostazioni, l'attività  che avviene con questi domini avrà punteggi di rischio più bassi e verrà trattata in modo analogo al modo in cui viene trattata l'attività interna dell'organizzazione. Ad esempio, le attività di posta elettronica in questi domini vengono analizzate in modo analogo a come viene analizzata l'attività di posta elettronica interna.
- **Domini di terze parti:** I domini di terze parti sono domini utilizzati per scopi aziendali nell'organizzazione e i contenuti sensibili possono essere archiviati in queste posizioni. Specificando un dominio di terze parti, è possibile ricevere avvisi per qualsiasi attività rischiosa in questi domini.

## <a name="export-alerts-preview"></a>Esportare avvisi (anteprima)

Le informazioni sugli avvisi per la gestione dei rischi Insider possono essere esportate nei servizi siem (Security Information and Event Management) tramite lo [schema dell'API Office 365 Management Activity.](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#security-and-compliance-alerts-schema) È possibile utilizzare le API office 365 Management Activity per esportare le informazioni sugli avvisi in altre applicazioni che l'organizzazione può usare per gestire o aggregare le informazioni sui rischi Insider.

Per usare le API per esaminare le informazioni sugli avvisi per i rischi Insider:

1. Abilitare il supporto dell'API Office 365 Management Activity **nell'esportazione delle** impostazioni di gestione dei  >  **rischi**  >  **Insider.** Per impostazione predefinita, questa impostazione è disabilitata per l'organizzazione di Microsoft 365.
2. Filtrare le attività di controllo comuni di Office 365 *in base a SecurityComplianceAlerts.*
3. Filtra *SecurityComplianceAlerts in* base alla *categoria InsiderRiskManagement.*

![Impostazioni di avviso per l'esportazione della gestione dei rischi Insider](../media/insider-risk-settings-export.png)

Le informazioni sugli avvisi contengono informazioni dello schema degli avvisi di sicurezza e conformità e dello schema comune dell'API di gestione di Office 365.

I campi e i valori seguenti vengono esportati per gli avvisi di gestione dei rischi Insider per lo schema di avviso sicurezza & conformità:

| **Parametro alert** | **Descrizione** |
|:------------------|:----------------|
| AlertType | Il tipo di avviso è *Personalizzato.*  |
| AlertId | GUID dell'avviso. Gli avvisi per la gestione dei rischi Insider sono modificabili. Quando cambia lo stato dell'avviso, viene generato un nuovo registro con lo stesso AlertID. Questo AlertID può essere usato per correlare gli aggiornamenti per un avviso. |
| Categoria | La categoria dell'avviso è *InsiderRiskManagement.* Questa categoria può essere usata per distinguere questi avvisi da altri avvisi di sicurezza & conformità. |
| Commenti | Commenti predefiniti per l'avviso. I valori *sono Nuovo avviso* (registrato quando viene creato un avviso) e *Avviso* aggiornato (registrato quando è presente un aggiornamento di un avviso). Utilizzare AlertID per correlare gli aggiornamenti per un avviso. |
| Dati | I dati per l'avviso includono l'ID utente univoco, il nome dell'entità utente e la data e l'ora (UTC) quando l'utente è stato attivato in un criterio. |
| Nome | Nome del criterio per i criteri di gestione dei rischi Insider che hanno generato l'avviso. |
| PolicyId | GUID del criterio di gestione dei rischi Insider che ha attivato l'avviso. |
| Gravità | Gravità dell'avviso. I valori *sono High,* *Medium* o *Low.* |
| Origine | Origine dell'avviso. Il valore è *Office 365 Security & Compliance.* |
| Stato | Stato dell'avviso. I valori *sono Active* (*Needs Review* in insider risk), *Investigating* (*Confirmed* in insider risk), *Resolved* (*Resolved* in insider risk), Dismissed ( *Dismissed* in insider risk). |
| Version | Versione dello schema degli avvisi di sicurezza e conformità. |

I campi e i valori seguenti vengono esportati per gli avvisi di gestione dei rischi Insider per lo schema comune [dell'API office 365 Management Activity.](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema)

- UserId
- Id
- RecordType
- CreationTime
- Operazione
- OrganizationId
- UserType
- UserKey

## <a name="priority-user-groups-preview"></a>Gruppi di utenti con priorità (anteprima)

Gli utenti dell'organizzazione possono avere livelli di rischio diversi a seconda della posizione, del livello di accesso alle informazioni riservate o della cronologia dei rischi. Assegnare priorità all'esame e al punteggio delle attività di questi utenti può aiutare a avvisare l'utente in caso di potenziali rischi che potrebbero avere conseguenze più elevate per l'organizzazione. I gruppi di utenti prioritari nella gestione dei rischi Insider consentono di definire gli utenti dell'organizzazione che necessitano di un'ispezione più stretta e di un punteggio dei rischi più sensibile. Insieme alle  violazioni dei criteri di  sicurezza da parte degli utenti con priorità e alle perdite di dati in base ai modelli di criteri degli utenti con priorità, gli utenti aggiunti a un gruppo di utenti con priorità hanno una maggiore probabilità di avvisi di rischio Insider e avvisi con livelli di gravità più elevati.

![Impostazioni del gruppo di utenti con priorità di gestione dei rischi Insider](../media/insider-risk-settings-priority-users.png)

Ad esempio, è necessario proteggersi da perdite di dati per un progetto estremamente riservato in cui gli utenti hanno accesso alle informazioni riservate. Si sceglie di creare *un gruppo di* utenti *con* priorità Utenti di progetto riservati per gli utenti dell'organizzazione che lavorano a questo progetto. Utilizzando la procedura  guidata dei criteri e il modello di criteri Perdita di dati per utenti con priorità, è possibile creare un nuovo criterio e assegnare il gruppo utenti con priorità Utenti di *Project* riservati al criterio. Le attività esaminate dai criteri per i membri del gruppo di utenti con priorità Utenti di *progetto* riservati sono più sensibili ai rischi e le attività di questi utenti avranno maggiori probabilità di generare un avviso e di ricevere avvisi con livelli di gravità più elevati.

### <a name="create-a-priority-user-group"></a>Creare un gruppo di utenti con priorità

Per creare un nuovo gruppo di utenti con priorità, si useranno i controlli di impostazione nella soluzione di gestione dei rischi **Insider** nel Centro conformità Microsoft 365. Per creare un gruppo di utenti con priorità, è necessario essere membri del gruppo di ruoli *Insider Risk Management* o Insider Risk Management *Admin.*

Completare la procedura seguente per creare un gruppo di utenti con priorità:

1. Nel Centro [conformità Microsoft 365](https://compliance.microsoft.com)passare a Gestione dei **rischi Insider e** selezionare le impostazioni dei rischi **Insider.**
2. Selezionare la **scheda Gruppi di utenti con** priorità
3. Nella scheda **Gruppi di utenti con priorità** selezionare Crea gruppo di utenti con priorità **per** avviare la creazione guidata del gruppo.
4. Nella pagina **Definisci gruppo** compilare i campi seguenti:
    - **Nome (obbligatorio):** immettere un nome descrittivo per il gruppo di utenti con priorità. Non è possibile modificare il nome del gruppo di utenti con priorità dopo aver completato la procedura guidata.
    - **Descrizione (facoltativo):** immettere una descrizione per il gruppo di utenti con priorità.
5. Selezionare **Avanti** per continuare.
6. Nella **pagina** Scegli membri  selezionare Scegliere i membri da cercare e selezionare gli account  utente abilitati alla posta elettronica inclusi nel gruppo oppure selezionare la casella di controllo Seleziona tutti per aggiungere tutti gli utenti dell'organizzazione al gruppo. Selezionare **Aggiungi** per continuare **o** Annulla per chiudere senza aggiungere utenti al gruppo.
7. Selezionare **Avanti** per continuare.
8. Nella pagina **Revisione** esaminare le impostazioni scelte per il gruppo di utenti con priorità. Selezionare **Modifica** per modificare uno qualsiasi dei valori del gruppo oppure selezionare **Invia** per creare e attivare il gruppo di utenti con priorità.
9. Nella pagina di conferma, selezionare **Fine per** uscire dalla procedura guidata.

### <a name="update-a-priority-user-group"></a>Aggiornare un gruppo di utenti con priorità

Per aggiornare un gruppo di utenti con priorità esistente, si utilizzerà l'impostazione dei controlli nella soluzione di gestione dei rischi **Insider** nel Centro conformità Microsoft 365. Per aggiornare un gruppo di utenti con priorità, è necessario essere membri del gruppo di ruoli *Insider Risk Management* o Insider Risk Management *Admin.*

Completare la procedura seguente per modificare un gruppo di utenti con priorità:

1. Nel Centro [conformità Microsoft 365](https://compliance.microsoft.com)passare a Gestione dei **rischi Insider e** selezionare le impostazioni dei rischi **Insider.**
2. Selezionare la **scheda Gruppi di utenti con** priorità
3. Selezionare il gruppo di utenti con priorità che si desidera modificare e selezionare **Modifica gruppo.**
4. Nella pagina **Definisci gruppo** aggiornare il campo Descrizione, se necessario. Non è possibile aggiornare il nome del gruppo di utenti con priorità. Selezionare **Avanti** per continuare.
5. Nella pagina **Scegli membri** aggiungere nuovi membri al gruppo utilizzando il **controllo Scegli** membri. Per rimuovere un utente dal gruppo, selezionare la "X" accanto all'utente che si desidera rimuovere. Selezionare **Avanti** per continuare.
6. Nella pagina **Revisione** esaminare le impostazioni di aggiornamento scelte per il gruppo di utenti con priorità. Selezionare **Modifica** per modificare uno qualsiasi dei valori del gruppo oppure selezionare **Invia** per aggiornare il gruppo di utenti con priorità.
7. Nella pagina di conferma, selezionare **Fine per** uscire dalla procedura guidata.

### <a name="delete-a-priority-user-group"></a>Eliminare un gruppo di utenti con priorità

Per eliminare un gruppo di utenti con priorità esistente, si utilizzerà l'impostazione dei controlli nella soluzione di gestione dei rischi **Insider** nel Centro conformità Microsoft 365. Per eliminare un gruppo di utenti con priorità, è necessario essere membri del gruppo di ruoli *Insider Risk Management* o Insider Risk Management *Admin.*

>[!IMPORTANT]
>L'eliminazione di un gruppo di utenti con priorità lo rimuoverà da qualsiasi criterio attivo a cui è assegnato. Se si elimina un gruppo di utenti con priorità assegnato a un criterio attivo, il criterio non conterrà alcun utente nell'ambito e sarà effettivamente inattivo e non creerà avvisi.

Completare la procedura seguente per eliminare un gruppo di utenti con priorità:

1. Nel Centro [conformità Microsoft 365](https://compliance.microsoft.com)passare a Gestione dei **rischi Insider e** selezionare le impostazioni dei rischi **Insider.**
2. Selezionare la **scheda Gruppi di utenti con** priorità
3. Selezionare il gruppo di utenti con priorità che si desidera modificare e scegliere **Elimina** dal menu dashboard.
4. Nella finestra **di dialogo** Elimina selezionare **Sì** per eliminare il gruppo di utenti con priorità oppure **scegliere Annulla** per tornare al dashboard.

## <a name="priority-physical-assets-preview"></a>Asset fisici con priorità (anteprima)

L'identificazione dell'accesso alle risorse fisiche prioritarie e la correlazione dell'attività di accesso agli eventi utente è un componente importante dell'infrastruttura di conformità. Queste risorse fisiche rappresentano posizioni prioritarie nell'organizzazione, ad esempio edifici aziendali, data center o sale server. Le attività a rischio Insider possono essere associate agli utenti che lavorano in orari insoliti, che tentano di accedere a queste aree sensibili o sicure non autorizzate e alle richieste di accesso ad aree di alto livello senza necessità legittime.

Con le risorse fisiche con priorità abilitate e il connettore dati di [badging](import-physical-badging-data.md) fisico configurato, la gestione dei rischi Insider integra i segnali provenienti dai sistemi di controllo fisico e accesso con altre attività di rischio degli utenti. Esaminando i modelli di comportamento nei sistemi di accesso fisico e correlando queste attività con altri eventi di rischio Insider, la gestione dei rischi Insider può aiutare gli investigatori e gli analisti della conformità a prendere decisioni di risposta più informate per gli avvisi. L'accesso alle risorse fisiche prioritarie viene ottenuto e identificato in approfondimenti in modo diverso dall'accesso alle risorse non prioritarie.

Ad esempio, l'organizzazione dispone di un sistema di badging per gli utenti che monitora e approva l'accesso fisico alle normali aree di lavoro e di progetto sensibili. Sono disponibili diversi utenti che lavorano a un progetto sensibile e questi utenti tornerà in altre aree dell'organizzazione al termine del progetto. Quando il progetto sensibile si avvicina al completamento, è necessario assicurarsi che il lavoro del progetto rimanga riservato e che l'accesso alle aree del progetto sia strettamente controllato.

Si sceglie di abilitare il connettore dati di badging fisico in Microsoft 365 per importare le informazioni di accesso dal sistema di badging fisico e specificare le risorse fisiche prioritarie nella gestione dei rischi insider. Importando le informazioni dal sistema di badging e correlando le informazioni di accesso fisico ad altre attività di rischio identificate nella gestione dei rischi insider, si nota che uno degli utenti del progetto accede agli uffici del progetto dopo il normale orario di lavoro ed esporta grandi quantità di dati in un servizio di archiviazione cloud personale dalla normale area di lavoro. Questa attività di accesso fisico associata all'attività online può puntare a possibili furti di dati e gli investigatori e gli analisti di conformità possono intraprendere le azioni appropriate come determinato dalle circostanze per questo utente.

### <a name="configure-priority-physical-assets"></a>Configurare asset fisici con priorità

Per configurare gli asset fisici con priorità, è necessario configurare il connettore di badging fisico e usare i controlli delle impostazioni nella soluzione di gestione dei rischi **Insider** nel Centro conformità Microsoft 365. Per configurare le risorse fisiche con priorità, è necessario essere membri del gruppo di ruoli *Insider Risk Management* o Insider Risk Management *Admin.*

Completare la procedura seguente per configurare le risorse fisiche con priorità:

1. Seguire i passaggi di configurazione per la gestione dei rischi Insider [nell'articolo Introduzione alla gestione dei rischi Insider.](insider-risk-management-configure.md) Nel passaggio 3, assicurarsi di configurare il connettore di badging fisico.

    >[!IMPORTANT]
    >Per consentire ai criteri di gestione dei rischi Insider di usare e correlare i dati del segnale relativi agli utenti in uscita e terminati con i dati degli eventi dalle piattaforme di accesso e controllo fisico, è necessario configurare anche il connettore risorse umane di Microsoft 365. Se si abilita il connettore di badging fisico senza abilitare il connettore risorse umane di Microsoft 365, i criteri di gestione dei rischi Insider eelaborare gli eventi solo per le attività di accesso fisico per gli utenti dell'organizzazione.

2. Nel Centro [conformità Microsoft 365,](https://compliance.microsoft.com)accedere a Gestione dei rischi **Insider** e selezionare Le impostazioni dei rischi **Insider** Priorità  >  **risorse fisiche.**
3. Nella pagina **Asset** fisici con priorità è possibile aggiungere manualmente gli ID risorsa fisica che si desidera monitorare per gli eventi delle risorse importati dal connettore di badging fisico oppure importare un . File CSV di tutti gli ID risorsa fisica importati dal connettore di badging fisico: a) Per aggiungere manualmente gli ID delle risorse fisiche, scegliere Aggiungi asset fisici con **priorità,** immettere un ID risorsa fisica, quindi selezionare **Aggiungi**. Immettere altri ID risorsa fisica e quindi selezionare Aggiungi asset **fisici con** priorità per salvare tutti gli asset immessi.
    b) Per aggiungere un elenco di ID risorsa fisica da un file . Csv file, choose **Import priority physical assets**. Nella finestra di dialogo esplora file selezionare il file . Csv file che si desidera importare, quindi selezionare **Apri.** ID degli asset fisici dall'oggetto . I file CSV vengono aggiunti all'elenco.
4. Passare alla scheda **Indicatori di** criteri in Impostazioni.
5. Nella pagina **Indicatori di criteri** passare alla sezione **Indicatori** di accesso fisico e selezionare la casella di controllo Accesso fisico dopo la chiusura o l'accesso non riuscito **all'asset sensibile.**
6. Selezionare **Salva** per configurare e uscire.

### <a name="delete-a-priority-physical-asset"></a>Eliminare un asset fisico con priorità

Per eliminare un asset fisico con priorità esistente, si useranno i controlli di impostazione nella soluzione di gestione dei rischi Insider nel Centro conformità Microsoft 365. Per eliminare un asset fisico con priorità, è necessario essere membri del gruppo di ruoli Insider Risk Management o Insider Risk Management Admin.

>[!IMPORTANT]
>L'eliminazione di un asset fisico con priorità rimuove l'esame da qualsiasi criterio attivo in cui era incluso in precedenza. Gli avvisi generati dalle attività associate all'asset fisico con priorità non vengono eliminati.

Completare la procedura seguente per eliminare un asset fisico con priorità:

1. Nel Centro [conformità Microsoft 365,](https://compliance.microsoft.com)accedere a Gestione dei rischi **Insider** e selezionare Le impostazioni dei rischi **Insider** Priorità  >  **risorse fisiche.**
2. Nella pagina **Priorità risorse fisiche** selezionare l'asset che si desidera eliminare.
3. Scegliere **Elimina** dal menu azione per eliminare l'asset.

## <a name="power-automate-flows-preview"></a>Flussi di Power Automate (anteprima)

[Microsoft Power Automate è](https://docs.microsoft.com/power-automate/getting-started) un servizio di flusso di lavoro che automatizza le azioni tra applicazioni e servizi. Utilizzando i flussi dei modelli o creati manualmente, è possibile automatizzare le attività comuni associate a tali applicazioni e servizi. Quando si abilita Power Automate flows per la gestione dei rischi Insider, è possibile automatizzare le attività importanti per i casi e gli utenti. È possibile configurare i flussi di Power Automate per recuperare informazioni su utenti, avvisi e casi e condividere queste informazioni con le parti interessate e altre applicazioni, nonché automatizzare le azioni nella gestione dei rischi Insider, ad esempio la pubblicazione di note sul caso. I flussi di Power Automate sono applicabili ai casi e a qualsiasi utente nell'ambito di un criterio.

I clienti con abbonamenti a Microsoft 365 che includono la gestione dei rischi Insider non necessitano di ulteriori licenze di Power Automate per usare i modelli di Power Automate per la gestione dei rischi Insider consigliati. Questi modelli possono essere personalizzati per supportare l'organizzazione e coprire gli scenari principali di gestione dei rischi Insider. Se si sceglie di usare le funzionalità avanzate di Power Automate in questi modelli, creare un modello personalizzato usando il connettore di conformità di Microsoft 365 o usare i modelli di Power Automate per altre aree di conformità in Microsoft 365, potrebbe essere necessario disporre di più licenze di Power Automate.

I modelli power automate seguenti vengono forniti ai clienti per supportare l'automazione dei processi per gli utenti e i casi di gestione dei rischi Insider:

- Informare gli utenti quando vengono aggiunti a un criterio di rischio **Insider:** questo modello è per le organizzazioni con criteri interni, privacy o requisiti normativi che gli utenti devono ricevere una notifica quando sono soggetti a criteri di gestione dei rischi Insider. Quando questo flusso viene configurato e selezionato per un utente nella pagina degli utenti, agli utenti e ai relativi responsabili viene inviato un messaggio di posta elettronica quando l'utente viene aggiunto a un criterio di gestione dei rischi Insider. Questo modello supporta inoltre l'aggiornamento di un elenco di SharePoint ospitato in un sito di SharePoint per tenere traccia dei dettagli del messaggio di notifica, ad esempio data/ora e destinatario del messaggio. Se hai scelto di anonimizzare gli utenti **nelle** impostazioni di privacy, i flussi creati da questo modello non funzioneranno come previsto in modo da mantenere la privacy degli utenti. Power Automate flows using this template are available on the **Users dashboard.**
- Richiedere informazioni alle risorse umane o aziendali su un utente in un caso di rischio **Insider:** quando agiscono su un caso, gli analisti e gli investigatori del rischio Insider potrebbero dover consultare le risorse umane o altri stakeholder per comprendere il contesto delle attività del caso. Quando questo flusso viene configurato e selezionato per un caso, gli analisti e gli investigatori inviano un messaggio di posta elettronica agli stakeholder delle risorse umane e aziendali configurati per questo flusso. A ogni destinatario viene inviato un messaggio con opzioni di risposta preconfigurato o personalizzabile. Quando i destinatari selezionano un'opzione di risposta, la risposta viene registrata come nota del caso e include informazioni su destinatario e data/ora. Se hai scelto di anonimizzare gli utenti **nelle** impostazioni di privacy, i flussi creati da questo modello non funzioneranno come previsto in modo da mantenere la privacy degli utenti. Power Automate flows using this template are available on the **Cases dashboard.**
- **Informare il responsabile quando un utente** ha un avviso per i rischi Insider: alcune organizzazioni potrebbero avere la necessità di ricevere una notifica di gestione immediata quando un utente ha un avviso per la gestione dei rischi Insider. Quando questo flusso è configurato e selezionato, al responsabile del caso all'utente viene inviato un messaggio di posta elettronica con le seguenti informazioni su tutti gli avvisi caso:
    - Criteri applicabili per l'avviso
    - Data/ora dell'avviso
    - Livello di gravità dell'avviso

    Il flusso aggiorna automaticamente le note sul caso che il messaggio è stato inviato e che il flusso è stato attivato. Se hai scelto di anonimizzare gli utenti **nelle** impostazioni di privacy, i flussi creati da questo modello non funzioneranno come previsto in modo da mantenere la privacy degli utenti. Power Automate flows using this template are available on the **Cases dashboard.**

- **Aggiungere un promemoria** del calendario per seguire un caso di rischio Insider: questo modello consente agli investigatori e agli analisti del rischio di aggiungere promemoria del calendario per i casi al calendario di Outlook di Office 365. Questo flusso elimina la necessità per gli utenti di uscire o uscire dal flusso di lavoro di gestione dei rischi Insider durante l'elaborazione dei casi e la valutazione degli avvisi. Quando questo flusso è configurato e selezionato, viene aggiunto un promemoria al calendario di Outlook di Office 365 per l'utente che esegue il flusso. Power Automate flows using this template are available on the **Cases dashboard.**
- Creare un record per i casi di rischio **Insider in ServiceNow:** questo modello è per le organizzazioni che desiderano utilizzare la soluzione ServiceNow per tenere traccia dei casi di gestione dei rischi Insider.  In un caso, gli analisti e gli investigatori del rischio Insider possono creare un record per il caso in ServiceNow. È possibile personalizzare questo modello per popolare i campi selezionati in ServiceNow in base alle esigenze dell'organizzazione. Power Automate flows using this template are available on the **Cases dashboard.** Per ulteriori informazioni sui campi ServiceNow disponibili, vedere l'articolo di [riferimento su ServiceNow Connector.](/connectors/service-now/)

### <a name="create-a-power-automate-flow-from-insider-risk-management-template"></a>Creare un flusso power automate da un modello di gestione dei rischi Insider

Per creare un flusso power automate da un modello di gestione dei rischi Insider consigliato, si useranno i controlli delle impostazioni nella soluzione di gestione dei  rischi **Insider** nel Centro conformità Microsoft 365 o l'opzione Gestisci flussi di **Power Automate** dal **controllo Automate** quando si lavora direttamente nei **dashboard** casi o utenti.

Per creare un flusso power automate nell'area delle impostazioni, è necessario essere membri del gruppo di ruoli *Insider Risk Management* o Insider Risk Management *Admin.* Per creare un flusso di Power Automate con l'opzione Gestisci flussi di **Power Automate,** è necessario essere membri di almeno un gruppo di ruoli di gestione dei rischi Insider.

Completare la procedura seguente per creare un flusso power automate da un modello di gestione dei rischi Insider consigliato:

1. Nel Centro [conformità Microsoft 365,](https://compliance.microsoft.com/)accedere a Gestione dei rischi **Insider** e selezionare le impostazioni dei rischi **Insider**  >  **Power Automate flows.** È inoltre possibile accedere dalle pagine **Dei casi** o **dei dashboard** degli utenti scegliendo **Automatizza**  >  **la gestione dei flussi di Power Automate.**
2. Nella pagina **Flussi di Power Automate** seleziona un modello consigliato dai modelli di gestione dei rischi **Insider** che potresti avere come nella pagina.
3. Il flusso elenca le connessioni incorporate necessarie per il flusso e noterà se gli stati della connessione sono disponibili. Se necessario, aggiornare tutte le connessioni non visualizzate come disponibili. Selezionare **Continua.**
4. Per impostazione predefinita, i flussi consigliati sono preconfigurato con i campi consigliati per la gestione dei rischi Insider e i campi dati del servizio Microsoft 365 necessari per completare l'attività assegnata per il flusso. Se necessario, personalizzare i componenti del flusso utilizzando il **controllo** Mostra opzioni avanzate e configurando le proprietà disponibili per il componente di flusso.
5. Se necessario, aggiungere eventuali altri passaggi al flusso selezionando il **pulsante Nuovo** passaggio. Nella maggior parte dei casi, questa operazione non dovrebbe essere necessaria per i modelli predefiniti consigliati.
6. Selezionare **Salva bozza** per salvare il flusso per ulteriori configurazioni oppure **selezionare Salva** per completare la configurazione per il flusso.
7. Selezionare **Chiudi** per tornare alla **pagina del flusso di Power Automate.** Il nuovo modello verrà elencato  come flusso nelle schede Flussi utente ed è automaticamente disponibile dal controllo a discesa **Automate** quando si lavora con i casi di gestione dei rischi Insider per l'utente che crea il flusso.

>[!IMPORTANT]
>Se altri utenti dell'organizzazione devono accedere al flusso, il flusso deve essere condiviso.

### <a name="create-a-custom-power-automate-flow-for-insider-risk-management"></a>Creare un flusso power automate personalizzato per la gestione dei rischi Insider

Alcuni processi e flussi di lavoro per l'organizzazione potrebbero essere al di fuori dei modelli di flusso di gestione dei rischi Insider consigliati e potrebbe essere necessario creare flussi personalizzati di Power Automate per le aree di gestione dei rischi Insider. I flussi di Power Automate sono flessibili e supportano una personalizzazione estesa, ma è necessario eseguire alcuni passaggi per l'integrazione con le funzionalità di gestione dei rischi Insider.

Completare la procedura seguente per creare un modello power automate personalizzato per la gestione dei rischi insider:

1. Controllare la licenza del flusso di **Power Automate:** per creare flussi Power Automate personalizzati che usano trigger di gestione dei rischi Insider, è necessaria una licenza di Power Automate. I modelli di flusso di gestione dei rischi Insider consigliati non richiedono licenze aggiuntive e sono inclusi come parte della licenza di gestione dei rischi Insider.
2. **Creare un flusso automatizzato:** creare un flusso che esegua una o più attività dopo essere stato attivato da un evento di gestione dei rischi Insider. Per informazioni dettagliate su come creare un flusso automatizzato, vedere [Creare un flusso in Power Automate.](https://docs.microsoft.com/power-automate/get-started-logic-flow)
3. Selezionare il connettore di conformità di **Microsoft 365:** cercare e selezionare il connettore di conformità di Microsoft 365. Questo connettore consente trigger e azioni di gestione dei rischi Insider. Per ulteriori informazioni sui connettori, vedere l'articolo di panoramica [di riferimento sui connettori.](https://docs.microsoft.com/connectors/connector-reference/)
4. **Scegliere i trigger di gestione dei rischi** Insider per il flusso: la gestione dei rischi Insider ha due trigger disponibili per i flussi personalizzati di Power Automate:
    - **Per un caso di gestione dei rischi Insider** selezionato: i flussi con questo trigger possono essere selezionati dalla pagina dashboard dei casi di gestione dei rischi Insider.
    - **Per un utente di gestione dei rischi Insider** selezionato: i flussi con questo trigger possono essere selezionati dalla pagina dashboard Utenti di gestione dei rischi Insider.
5. Scegliere le azioni di gestione dei rischi Insider per il flusso: è possibile scegliere tra diverse azioni per la gestione dei rischi Insider da includere nel flusso personalizzato:
    - Ottenere un avviso per la gestione dei rischi Insider
    - Ottenere un caso di gestione dei rischi Insider
    - Ottenere un utente per la gestione dei rischi Insider
    - Ottenere avvisi per la gestione dei rischi Insider per un caso
    - Aggiungere una nota sul caso di gestione dei rischi Insider

### <a name="share-a-power-automate-flow"></a>Condividere un flusso power automate

Per impostazione predefinita, i flussi di Power Automate creati da un utente sono disponibili solo per tale utente. Per consentire ad altri utenti di gestione dei rischi Insider di accedere e utilizzare un flusso, il flusso deve essere condiviso dall'autore del flusso. Per condividere un flusso, si useranno i controlli delle impostazioni nella soluzione di gestione dei rischi **Insider** nel Centro conformità Microsoft 365 o nell'opzione Gestisci flussi di **Power Automate** dal controllo Automate quando si lavora direttamente nelle pagine del **dashboard** Casi o Utenti.  Dopo aver condiviso un flusso, tutti gli utenti con cui è stato condiviso  possono accedere al flusso nell'elenco a discesa **Automate** control nei dashboard del caso **e dell'utente.**

Per condividere un flusso di Power Automate nell'area delle impostazioni, è necessario essere membri del gruppo di ruoli *Insider Risk Management* o Insider Risk Management *Admin.* Per condividere un flusso di Power Automate con l'opzione Gestisci flussi di **Power Automate,** è necessario essere membri di almeno un gruppo di ruoli di gestione dei rischi Insider.

Completare la procedura seguente per condividere un flusso di Power Automate:

1. Nel Centro [conformità Microsoft 365,](htttps://compliance.microsoft.com)accedere a Gestione dei rischi **Insider** e selezionare le impostazioni dei rischi **Insider**  >  **Power Automate flows.** È inoltre possibile accedere dalle pagine **Dei casi** o **dei dashboard** degli utenti scegliendo **Automatizza**  >  **la gestione dei flussi di Power Automate.**
2. Nella pagina **Flussi di Power Automate** selezionare la **scheda Flussi del** team o **Flussi del** team.
3. Selezionare il flusso da condividere, quindi scegliere **Condividi** dal menu delle opzioni del flusso.
4. Nella pagina di condivisione del flusso immettere il nome dell'utente o del gruppo che si desidera aggiungere come proprietario del flusso.
5. Nella finestra **di dialogo Connessione** utilizzata selezionare **OK** per confermare che l'utente o il gruppo aggiunto avrà accesso completo al flusso.

### <a name="edit-a-power-automate-flow"></a>Modificare un flusso di Power Automate

Per modificare un flusso, si useranno i controlli delle impostazioni nella soluzione di gestione dei rischi **Insider** nel  Centro conformità Microsoft 365 o nell'opzione Gestisci flussi di Power Automate dal controllo **Automate** quando si lavora direttamente nei **dashboard** dei casi o degli utenti. 

Per modificare un flusso di Power Automate nell'area delle impostazioni, è necessario essere membri del gruppo di ruoli *Insider Risk Management* o Insider Risk Management *Admin.* Per modificare un flusso di Power Automate con l'opzione Gestisci flussi di **Power Automate,** è necessario essere membri di almeno un gruppo di ruoli di gestione dei rischi Insider.

Completare la procedura seguente per modificare un flusso di Power Automate:

1. Nel Centro [conformità Microsoft 365,](htttps://compliance.microsoft.com)accedere a Gestione dei rischi **Insider** e selezionare le impostazioni dei rischi **Insider**  >  **Power Automate flows.** È inoltre possibile accedere dalle pagine **Dei casi** o **dei dashboard** degli utenti scegliendo **Automatizza**  >  **la gestione dei flussi di Power Automate.**
2. Nella pagina **Flussi di Power Automate** selezionare un flusso da modificare e scegliere **Modifica** dal menu di controllo del flusso.
3. Selezionare i **puntini di sospensione**  >  **Impostazioni** per modificare l'impostazione di un componente di flusso o i puntini di sospensione  >  **Elimina** per eliminare un componente di flusso.
4. Selezionare **Salva** e quindi **Chiudi per** completare la modifica del flusso.

### <a name="delete-a-power-automate-flow"></a>Eliminare un flusso di Power Automate

Per eliminare un flusso, si useranno i controlli delle impostazioni nella soluzione di gestione dei rischi **Insider** nel  Centro conformità Microsoft 365 o nell'opzione Gestisci flussi di Power Automate dal controllo **Automate** quando si lavora direttamente nei **dashboard** casi o utenti.  Quando un flusso viene eliminato, viene rimosso come opzione per tutti gli utenti.

Per eliminare un flusso di Power Automate nell'area delle impostazioni, è necessario essere membri del gruppo di ruoli *Insider Risk Management* o Insider Risk Management *Admin.* Per eliminare un flusso di Power Automate con l'opzione Gestisci flussi di **Power Automate,** è necessario essere membri di almeno un gruppo di ruoli di gestione dei rischi Insider.

Completare la procedura seguente per eliminare un flusso di Power Automate:

1. Nel Centro [conformità Microsoft 365,](htttps://compliance.microsoft.com)accedere a Gestione dei rischi **Insider** e selezionare le impostazioni dei rischi **Insider**  >  **Power Automate flows.** È inoltre possibile accedere dalle pagine **Dei casi** o **dei dashboard** degli utenti scegliendo **Automatizza**  >  **la gestione dei flussi di Power Automate.**
2. Nella pagina **Flussi di Power Automate** selezionare un flusso da eliminare e scegliere **Elimina** dal menu di controllo del flusso.
3. Nella finestra di dialogo di conferma dell'eliminazione, selezionare **Elimina** per rimuovere il flusso oppure **scegliere Annulla** per uscire dall'azione di eliminazione.

## <a name="microsoft-teams-preview"></a>Microsoft Teams (anteprima)

Gli analisti e gli investigatori della conformità possono usare facilmente Microsoft Teams per la collaborazione sui casi di gestione dei rischi insider. Possono coordinarsi e comunicare con altre parti interessate in Microsoft Teams per:

- Coordinare ed esaminare le attività di risposta per i casi nei canali privati di Teams
- Condividere e archiviare in modo sicuro file ed elementi di prova correlati a singoli casi
- Tenere traccia e rivedere le attività di risposta da parte di analisti e investigatori

Dopo aver abilitato Microsoft Teams per la gestione dei rischi Insider, viene creato un team di Microsoft Teams dedicato ogni volta che viene confermato un avviso e viene creato un caso. Per impostazione predefinita, il team include automaticamente tutti i membri dei gruppi di ruoli Insider *Risk Management,* *Insider Risk Management Analysts* e *Insider Risk Management Investigators* (fino a 100 utenti iniziali). È possibile aggiungere altri collaboratori dell'organizzazione al team dopo che è stato creato e in base alle esigenze. Per i casi esistenti creati prima di abilitare Microsoft Teams, gli analisti e gli investigatori possono scegliere di creare un nuovo team di Microsoft Teams quando lavorano in un caso, se necessario.  Dopo aver risolto il caso associato nella gestione dei rischi Insider, il team viene automaticamente archiviato (spostato in nascosto e di sola lettura).

Per altre informazioni su come usare team e canali in Microsoft Teams, vedere Panoramica dei team e dei [canali in Microsoft Teams.](https://docs.microsoft.com/MicrosoftTeams/teams-channels-overview)

L'abilitazione del supporto di Microsoft Teams per i casi è facile e veloce da configurare. Per abilitare Microsoft Teams per la gestione dei rischi Insider, eseguire la procedura seguente:

1. Nel Centro [conformità Microsoft 365,](htttps://compliance.microsoft.com)accedere alle impostazioni dei rischi **Insider per** la gestione dei  >  **rischi Insider.**
2. Selezionare la **scheda Microsoft Teams.**
3. Abilitare l'integrazione di Microsoft Teams per la gestione dei rischi Insider.
4. Selezionare **Salva** per configurare e uscire.

### <a name="create-a-microsoft-teams-team-for-existing-cases"></a>Creare un team di Microsoft Teams per i casi esistenti

Se si abilita il supporto di Microsoft Teams per la gestione dei rischi Insider dopo aver creato casi esistenti, sarà necessario creare manualmente un team per ogni caso in base alle esigenze. Dopo aver abilitato il supporto di Microsoft Teams nelle impostazioni di gestione dei rischi Insider, i nuovi casi creeranno automaticamente un nuovo team di Microsoft Teams.

Gli utenti devono disporre dell'autorizzazione per creare gruppi di Microsoft 365 nell'organizzazione per creare un team di Microsoft Teams da un caso. Per ulteriori informazioni sulla gestione delle autorizzazioni per i gruppi di Microsoft 365, vedere Gestire chi può creare gruppi di [Microsoft 365.](https://docs.microsoft.com/microsoft-365/solutions/manage-creation-of-groups)

Per creare un team per un caso, si userà il controllo Crea team Microsoft quando si lavora direttamente in un caso esistente. Completare la procedura seguente per creare un nuovo team:

1. Nel Centro [conformità Microsoft 365](htttps://compliance.microsoft.com)passare a Casi di gestione dei rischi **Insider** e selezionare un  >   caso esistente.
2. Scegliere Crea Microsoft Team dal menu **dell'azione del caso.**
3. Nel campo **Nome team** immettere un nome per il nuovo team di Microsoft Teams.
4. Selezionare **Crea team Microsoft** e quindi chiudi. 

A seconda del numero di utenti assegnati ai gruppi di ruoli di gestione dei rischi Insider, potrebbero essere necessario 15 minuti prima che tutti gli investigatori e gli analisti siano aggiunti al team di Microsoft Teams per un caso.
