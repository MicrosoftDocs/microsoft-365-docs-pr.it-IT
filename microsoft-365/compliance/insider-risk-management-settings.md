---
title: Impostazioni di gestione dei rischi Insider
description: Informazioni sulle impostazioni di gestione dei rischi insider in Microsoft 365
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
ms.openlocfilehash: 7592b92b74173e77e7937151ba88c23163363fde
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624694"
---
# <a name="get-started-with-insider-risk-management-settings"></a>Introduzione alle impostazioni di gestione dei rischi insider

Le impostazioni di gestione dei rischi insider si applicano a tutti i criteri di gestione dei rischi insider, indipendentemente dal modello scelto durante la creazione di un criterio. Le impostazioni vengono configurate usando il controllo **Impostazioni rischi dei dipendenti** posto nella parte superiore di tutte le schede per la gestione dei rischi Insider. Queste impostazioni controllano i componenti dei criteri per le aree seguenti:

- Privacy
- Indicatori
- Sequenze temporali dei criteri
- Rilevamenti intelligenti
- Esportare avvisi (anteprima)
- Gruppi di utenti con priorità (anteprima)
- Asset fisici prioritari (anteprima)
- Power Automate flussi (anteprima)
- Microsoft Teams (anteprima)
- Analisi (anteprima)

Prima di iniziare e creare criteri di gestione dei rischi insider, è importante comprendere queste impostazioni e scegliere i livelli di impostazione migliori per le esigenze di conformità per l'organizzazione.

## <a name="privacy"></a>Privacy

È fondamentale proteggere la privacy degli utenti che rientrano nei criteri, ciò può contribuire a promuovere l'oggettività nell'analisi dei dati e nelle revisioni dell'analisi per gli avvisi di rischio Insider. Per gli utenti con criteri di rischio insider, è possibile scegliere una delle impostazioni seguenti:

- **Show anonymized versions of usernames**: I nomi degli utenti sono anonimi per impedire ad amministratori, investigatori e revisori di vedere chi è associato agli avvisi dei criteri. Ad esempio, un utente "Grace Taylor" comparirebbe con uno pseudonimo casuale come "AnonIS8-988" in tutte le aree dell'esperienza di gestione dei rischi Insider. Quando si sceglie questa impostazione, vengono resi anonimi tutti gli utenti con corrispondenze con i criteri correnti e precedenti e si applica a tutti i criteri. Le informazioni del profilo utente nell'avviso per i rischi insider e nei dettagli del caso non saranno disponibili quando si sceglie questa opzione. Tuttavia, i nomi utente vengono visualizzati quando si aggiungono nuovi utenti ai criteri esistenti o quando si assegnano utenti a nuovi criteri. Se si sceglie di disattivare questa impostazione, verranno visualizzati i nomi utente per tutti gli utenti con corrispondenze di criteri correnti o precedenti.
- **Non mostrare versioni anonime** dei nomi utente: i nomi utente vengono visualizzati per tutte le corrispondenze dei criteri correnti e precedenti per avvisi e casi. Le informazioni del profilo utente (nome, titolo, alias e organizzazione o reparto) vengono visualizzate per l'utente per tutti gli avvisi e i casi di gestione dei rischi insider.

![Impostazioni di privacy per la gestione dei rischi insider](../media/insider-risk-settings-privacy.png)

## <a name="indicators"></a>Indicatori

I modelli di criteri di rischio Insider definiscono il tipo di attività di rischio che si desidera rilevare e analizzare. Ogni modello di criteri si basa su indicatori specifici che corrispondono a trigger e attività di rischio specifici. Tutti gli indicatori sono disabilitati per impostazione predefinita ed è necessario selezionare uno o più indicatori dei criteri prima di configurare un criterio di gestione dei rischi insider.

Gli avvisi vengono attivati dai criteri quando gli utenti eseguono attività correlate agli indicatori dei criteri che soddisfano una soglia necessaria. La gestione dei rischi insider utilizza due tipi di indicatori:

- **Triggering events**: Eventi che determinano se un utente è attivo in un criterio di gestione dei rischi insider. Se un utente viene aggiunto a un criterio di gestione dei rischi insider non dispone di un evento di attivazione, l'attività dell'utente non viene valutata dal criterio. Ad esempio, l'utente A viene  aggiunto a un criterio creato dal furto di dati allontanando il modello di criteri degli utenti e il criterio e Microsoft 365 connettore HR sono configurati correttamente. Finché l'utente A non ha una data di terminazione segnalata dal connettore HR, le attività dell'utente A non vengono valutate da questo criterio di gestione dei rischi insider per i rischi. Un altro esempio di evento di attivazione è se un utente ha un *avviso* di criteri DLP di gravità elevata quando si utilizzano i criteri di *perdita di* dati.
- **Indicatori dei criteri**: Indicatori inclusi nei criteri di gestione dei rischi insider utilizzati per determinare un punteggio di rischio per un utente nell'ambito. Questi indicatori di criteri vengono attivati solo dopo che si verifica un evento di attivazione per un utente. Alcuni esempi di indicatori dei criteri sono quando un utente copia i dati nei servizi di archiviazione cloud personali o nei dispositivi di archiviazione portatili, se un account utente viene rimosso da Azure Active Directory o se un utente condivide file e cartelle interni con parti esterne non autorizzate.

Gli indicatori dei criteri sono suddivisi nelle aree seguenti. Puoi scegliere gli indicatori per attivare e personalizzare i limiti degli eventi degli indicatori per ogni livello di indicatore quando crei un criterio di rischio insider:

- **Office:** includono indicatori dei criteri per i siti SharePoint, Microsoft Teams messaggi di posta elettronica.
- **Indicatori di dispositivo:** includono indicatori dei criteri per attività come la condivisione di file in rete o con dispositivi. Gli indicatori includono attività che coinvolgono tutti i tipi di file, escludendo l'attività di file eseguibile (.exe) e di libreria di collegamento dinamico (.dll). Se si **seleziona** Indicatori di dispositivo , l'attività viene elaborata solo per i dispositivi con Windows 10 Build 1809 o versione successiva ed è necessario prima eseguire l'onboardboard dei dispositivi nel Centro conformità. Per altre informazioni sulla configurazione dei dispositivi per l'integrazione con i rischi insider, vedi la sezione Seguente Abilitare gli indicatori di dispositivo e i dispositivi [di onboarding](insider-risk-management-settings.md#OnboardDevices) in questo articolo.
- **Indicatore di violazione dei criteri** di sicurezza (anteprima): sono inclusi gli indicatori di Microsoft Defender for Endpoint correlati all'installazione di software non approvato o dannoso o all'esclusione dei controlli di sicurezza. Per ricevere avvisi nella gestione dei rischi insider, devi avere una licenza di Defender for Endpoint attiva e l'integrazione dei rischi insider abilitata. Per altre informazioni sulla configurazione di Defender per Endpoint per l'integrazione della gestione dei rischi insider, vedi [Configurare le funzionalità avanzate in Microsoft Defender for Endpoint.](/windows/security/threat-protection/microsoft-defender-atp/advanced-features\#share-endpoint-alerts-with-microsoft-compliance-center)
- **Indicatori di accesso fisico (anteprima):** includono indicatori dei criteri per l'accesso fisico agli asset sensibili. Ad esempio, i tentativi di accesso a un'area con restrizioni nei log di sistema di badging fisico possono essere condivisi con i criteri di gestione dei rischi insider. Per ricevere questi tipi di avvisi nella gestione dei rischi insider, è necessario che gli asset fisici con priorità siano abilitati nella gestione dei rischi insider e che sia configurato il connettore dati di [badging](import-physical-badging-data.md) fisico. Per ulteriori informazioni sulla configurazione dell'accesso fisico, vedere la sezione [Priorità di accesso fisico](#priority-physical-assets-preview) in questo articolo.
- **Microsoft Cloud App Security (anteprima):** sono inclusi gli indicatori dei criteri degli avvisi condivisi Cloud App Security. Il rilevamento delle anomalie abilitato automaticamente in Cloud App Security avvia immediatamente il rilevamento e la raccolta dei risultati, individuando numerose anomalie comportamentali tra gli utenti e i computer e i dispositivi connessi alla rete. Per includere queste attività negli avvisi dei criteri di gestione dei rischi insider, selezionare uno o più indicatori in questa sezione. Per altre informazioni sull'analisi Cloud App Security e il rilevamento di anomalie, vedi Ottenere l'analisi comportamentale e [il rilevamento di anomalie.](/cloud-app-security/anomaly-detection-policy)
- **Ripetitori del punteggio di rischio**: includono l'aumento del punteggio di rischio per attività insolite o violazioni dei criteri precedenti. L'abilitazione dei ripetitori del punteggio di rischio aumenta i punteggi di rischio e la probabilità di avvisi per questi tipi di attività. Per le attività insolite, i punteggi vengono aumentati se l'attività rilevata si discosta dal comportamento tipico dell'utente. Ad esempio, un aumento significativo dei download giornalieri di file. L'attività insolita viene presentata come un aumento percentuale (ad esempio, "100% rispetto all'attività normale") e inciderà in modo diverso sul punteggio di rischio a seconda dell'attività. Per gli utenti con violazioni dei criteri precedenti, i punteggi vengono aumentati se un utente ha risolto più di un caso in precedenza come violazione dei criteri confermata. I ripetitori del punteggio di rischio possono essere selezionati solo se sono selezionati uno o più indicatori.

In alcuni casi, è possibile limitare gli indicatori dei criteri di rischio insider applicati ai criteri di rischio insider nell'organizzazione. Puoi disattivare gli indicatori dei criteri per aree specifiche disabilitandoli da tutti i criteri di rischio insider. Gli eventi di attivazione non possono essere modificati per i modelli di criteri di rischio insider.

Per definire gli indicatori dei criteri di rischio insider abilitati in tutti i criteri di rischio insider, passare a **Impostazioni di** rischio Insider Indicatori e selezionare uno o più indicatori di  >   criteri. Gli indicatori selezionati nella pagina Impostazioni indicatori non possono essere configurati singolarmente durante la creazione o la modifica di un criterio di rischio insider nella procedura guidata dei criteri.

>[!NOTE]
>La visualizzazione dei nuovi utenti aggiunti manualmente nel dashboard Utenti può richiedere **diverse ore.** La visualizzazione delle attività dei 90 giorni precedenti per questi utenti può richiedere fino a 24 ore. Per visualizzare le attività per gli utenti aggiunti manualmente, selezionare l'utente nel **dashboard** Utenti e aprire la **scheda Attività** utente nel riquadro dei dettagli.

### <a name="enable-device-indicators-and-onboard-devices"></a>Abilitare gli indicatori di dispositivo e i dispositivi di onboard
<a name="OnboardDevices"> </a>

Per abilitare il monitoraggio delle attività di rischio nei dispositivi e includere indicatori dei criteri per queste attività, i dispositivi devono soddisfare i requisiti seguenti ed è necessario completare la procedura di onboarding seguente.

#### <a name="step-1-prepare-your-endpoints"></a>Passaggio 1: Preparare gli endpoint

Assicurati che i dispositivi Windows 10 che si prevede di segnalare nella gestione dei rischi insider soddisfino questi requisiti.

1. Deve eseguire Windows 10 x64 build 1809 o versione successiva e deve aver installato l'aggiornamento [di Windows 10 (OS Build 17763.1075)](https://support.microsoft.com/help/4537818/windows-10-update-kb4537818) dal 20 febbraio 2020.
2. L'account utente utilizzato per accedere al Windows 10 deve essere un account AAD (Active Azure Active Directory). Il Windows 10 può essere [AAD,](/azure/active-directory/devices/concept-azure-ad-join)AAD ibrido o aggiunto ad Active Directory o registrato AAD.
3. Installare il browser Microsoft Chromium Edge nel dispositivo endpoint per monitorare le azioni per l'attività di caricamento cloud. Vedere [Scaricare il nuovo Microsoft Edge basato su Chromium](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium).

#### <a name="step-2-onboarding-devices"></a>Passaggio 2: Onboarding dei dispositivi
<a name="OnboardStep2"> </a>

Devi abilitare il monitoraggio dei dispositivi e l'onboardboard degli endpoint prima di poter monitorare le attività di gestione dei rischi insider in un dispositivo. Entrambe le azioni vengono eseguite nel portale Microsoft 365 conformità.

Quando vuoi eseguire l'onboarded dei dispositivi che non sono ancora stati onboarded, scaricherai lo script appropriato e distribuirai come descritto nei passaggi seguenti.

Se i dispositivi sono già presenti in [Microsoft Defender per endpoint](/windows/security/threat-protection/), verranno visualizzati nell'elenco dei dispositivi gestiti. Segui [passaggio 3: se hai dispositivi onboarded in Microsoft Defender for Endpoint](insider-risk-management-settings.md#OnboardStep3) nella sezione successiva.

In questo scenario di distribuzione, eseguirai l'onboarded dei dispositivi che non sono stati ancora onboarded e vuoi solo monitorare le attività di rischio insider nei dispositivi Windows 10 insider.

1. Aprire il [Centro conformità Microsoft](https://compliance.microsoft.com).
2. Aprire la pagina delle impostazioni del Centro conformità e scegliere **Onboarding di dispositivi**.

   > [!NOTE]
   > Anche se in genere sono necessari circa 60 secondi perché l'onboarding dei dispositivi sia abilitato, attendere fino a 30 minuti prima di contattare il supporto tecnico Microsoft.

3. Scegliere **Gestione dispositivi** per aprire l'elenco **Dispositivi**. L'elenco sarà vuoto finché non si caricano dispositivi.
4. Scegliere **Onboarding** per avviare il processo di onboarding.
5. Scegli la modalità di distribuzione in questi altri dispositivi nell'elenco **Metodo di** distribuzione e quindi scarica **il pacchetto.**
6. Seguire le procedure appropriate in [Strumenti e metodi di onboarding per i dispositivi Windows 10](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints). Questo collegamento porta a una pagina di destinazione in cui è possibile accedere alle procedure di Microsoft Defender per endpoint che corrispondono al pacchetto di distribuzione selezionato nel passaggio 5:
    - Onboarding di dispositivi Windows 10 con Criteri di gruppo
    - Onboarding di dispositivi Windows 10 con Microsoft Endpoint Configuration Manager
    - Onboarding di dispositivi Windows 10 con gli strumenti di Gestione dispositivi mobili
    - Onboarding di dispositivi Windows 10 con uno script locale
    - Onboarding di dispositivi VDI (Virtual Desktop Infrastructure) non persistenti.

Dopo aver eseguito l'onboarded dell'endpoint, dovrebbe essere visibile nell'elenco dei dispositivi e l'endpoint inizierà a segnalare i log delle attività di controllo alla gestione dei rischi insider.

> [!NOTE]
> Questa esperienza richiede la licenza. Se non si ha la licenza necessaria, i dati non saranno visibili o accessibili.

#### <a name="step-3-if-you-have-devices-onboarded-into-microsoft-defender-for-endpoint"></a>Passaggio 3: se i dispositivi sono stati onboarded in Microsoft Defender for Endpoint
<a name="OnboardStep3"> </a>

Se Microsoft Defender for Endpoint è già distribuito e sono presenti report degli endpoint, tutti questi endpoint verranno visualizzati nell'elenco dei dispositivi gestiti. Puoi continuare a eseguire l'onboarding di nuovi dispositivi nella gestione dei rischi insider per espandere la copertura usando la sezione [Passaggio 2: onboarding dei](insider-risk-management-settings.md#OnboardStep2) dispositivi.

1. Aprire il [Centro conformità Microsoft](https://compliance.microsoft.com).
2. Aprire la pagina delle impostazioni del Centro conformità e scegliere **Abilita monitoraggio dispositivi**.
3. Scegliere **Gestione dispositivi** per aprire l'elenco **Dispositivi**. Dovrebbe essere visualizzato l'elenco dei dispositivi che stanno già segnalando in Microsoft Defender per Endpoint.
4. Scegli **Onboarding** se devi eseguire l'onboarding di più dispositivi.
5. Scegli la modalità di distribuzione in questi altri dispositivi nell'elenco **Metodo di** distribuzione e quindi **scarica pacchetto.**
6. Seguire le procedure appropriate in [Strumenti e metodi di onboarding per i dispositivi Windows 10](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints). Questo collegamento porta a una pagina di destinazione in cui è possibile accedere alle procedure di Microsoft Defender per endpoint che corrispondono al pacchetto di distribuzione selezionato nel passaggio 5:
    - Onboarding di dispositivi Windows 10 con Criteri di gruppo
    - Onboarding di dispositivi Windows 10 con Microsoft Endpoint Configuration Manager
    - Onboarding di dispositivi Windows 10 con gli strumenti di Gestione dispositivi mobili
    - Onboarding di dispositivi Windows 10 con uno script locale
    - Onboarding di dispositivi VDI (Virtual Desktop Infrastructure) non persistenti.

Dopo aver eseguito l'onboarded dell'endpoint, dovrebbe essere visibile nella tabella Dispositivi e l'endpoint inizierà a segnalare i log delle attività di controllo alla gestione dei rischi insider. 

> [!NOTE]
>Questa esperienza richiede la licenza. Se non si ha la licenza necessaria, i dati non saranno visibili o accessibili.

### <a name="indicator-level-settings-preview"></a>Impostazioni livello indicatore (anteprima)

Quando si crea un criterio nella procedura guidata dei criteri, è possibile configurare il modo in cui il numero giornaliero di eventi di rischio deve influenzare il punteggio di rischio per gli avvisi di rischio insider. Queste impostazioni degli indicatori consentono di controllare il modo in cui il numero di occorrenze di eventi di rischio nell'organizzazione deve influire sul punteggio di rischio e quindi sulla gravità dell'avviso associata per questi eventi. Se preferisci, puoi anche scegliere di mantenere i livelli di soglia degli eventi predefiniti consigliati da Microsoft per tutti gli indicatori abilitati.

Ad esempio, si decide di abilitare gli indicatori di SharePoint nelle impostazioni dei criteri di rischio insider e di  impostare soglie personalizzate per gli eventi di SharePoint durante la configurazione degli indicatori per un nuovo criterio di fuga di dati insider. Durante la procedura guidata dei criteri di rischio insider, si configurano tre diversi livelli di eventi giornalieri per ogni indicatore di SharePoint per influenzare il punteggio di rischio per gli avvisi associati a questi eventi.

![Impostazioni degli indicatori personalizzati per la gestione dei rischi insider](../media/insider-risk-custom-indicators.png)

Per il primo livello di evento giornaliero, si imposta la soglia su *10* o più eventi al giorno per un impatto minore sul punteggio di rischio per gli eventi, *su 20* o più eventi al giorno per un impatto medio sul punteggio di rischio per gli eventi e *su 30* o più eventi al giorno un impatto maggiore sul punteggio di rischio per gli eventi. Queste impostazioni in modo efficace significano:

- Se sono presenti da 1 a 9 eventi SharePoint che si verificano dopo l'attivazione dell'evento, i punteggi di rischio hanno un impatto minimo e tendono a non generare un avviso.
- Se sono presenti 10-19 eventi SharePoint che si verificano dopo un evento di attivazione, il punteggio di rischio è intrinsecamente inferiore e i livelli di gravità degli avvisi tendono a essere a un livello basso.
- Se sono presenti 20-29 eventi SharePoint che si verificano dopo un trigger, il punteggio di rischio è intrinsecamente superiore e i livelli di gravità degli avvisi tendono a essere di livello medio.
- Se sono presenti 30 o più eventi SharePoint che si verificano dopo un'attivazione, il punteggio di rischio è intrinsecamente superiore e i livelli di gravità degli avvisi tendono a essere di alto livello.

## <a name="policy-timeframes"></a>Timeframe dei criteri

I timeframe dei criteri consentono di definire periodi di revisione passati e futuri, i quali sono attivati dopo le corrispondenze ai criteri, in base a eventi e attività relativi ai modelli di criteri di gestione dei rischi Insider. A seconda del modello di criteri scelto, sono disponibili i seguenti tempi per i criteri:

- **Finestra di** attivazione: disponibile per  tutti i modelli di criteri, la finestra Attivazione è il numero definito di giorni che la finestra viene attivata dopo **un** evento di attivazione. La finestra viene attivata da 1 a 30 giorni dopo che si verifica un evento di attivazione per qualsiasi utente assegnato al criterio. Ad esempio, hai configurato un criterio di gestione dei rischi insider e hai impostato la *finestra di attivazione* su 30 giorni. Sono trascorsi diversi mesi dalla configurazione del criterio e si verifica un evento di attivazione per uno degli utenti inclusi nel criterio. L'evento di attivazione attiva la *finestra di* attivazione e il criterio è attivo per tale utente per 30 giorni dopo l'evento di attivazione.
- **Rilevamento attività passate**: Disponibile per  tutti i modelli di criteri, il rilevamento delle attività passate è il numero definito di giorni in cui la finestra viene attivata **prima** di un evento di attivazione. La finestra viene attivata da 0 a 180 giorni prima che si verifichi un evento di attivazione per qualsiasi utente assegnato al criterio. Ad esempio, hai configurato un criterio di gestione dei rischi insider e hai impostato *il rilevamento delle* attività passate su 90 giorni. Sono trascorsi diversi mesi dalla configurazione del criterio e si verifica un evento di attivazione per uno degli utenti inclusi nel criterio. L'evento di attivazione  attiva il rilevamento delle attività passate e il criterio raccoglie le attività storiche per tale utente per 90 giorni prima dell'evento di attivazione.

![Impostazioni dell'intervallo di tempo per la gestione dei rischi Insider](../media/insider-risk-settings-timeframes.png)

## <a name="intelligent-detections"></a>Rilevamenti intelligenti

Le impostazioni di rilevamento intelligente consentono di perfezionare il modo in cui i rilevamenti di attività rischiose vengono elaborati per gli avvisi. In alcuni casi, potrebbe essere necessario definire i tipi di file da ignorare oppure applicare un livello di rilevamento per i file per definire una barra minima per gli avvisi. Usa queste impostazioni per controllare il volume complessivo degli avvisi, le esclusioni dei tipi di file e i limiti del volume di file.

### <a name="file-type-exclusions"></a>Esclusioni di tipi di file

Per escludere tipi di file specifici da tutti i criteri di gestione dei rischi insider, immettere le estensioni dei tipi di file separate da virgole. Ad esempio, per escludere determinati tipi di file musicali dalle corrispondenze ai criteri, è possibile immettere aac,mp3,wav,wma nel campo **Esclusioni file**. I file con queste estensioni verranno ignorati da tutti i criteri di gestione dei rischi insider.

### <a name="threshold-for-unusual-file-activity"></a>Soglia per attività insolite nei file

Per definire un livello minimo di file prima che gli avvisi attività siano riportati nei criteri di rischio insider, immettere il numero di file. Ad esempio, immettere "10" se non si desidera generare avvisi di rischio insider quando un utente scarica 10 file o meno, anche se i criteri considerano questa attività insolita.

### <a name="alert-volume"></a>Volume avviso

Alle attività degli utenti rilevate dai criteri di rischio insider viene assegnato un punteggio di rischio specifico, che a sua volta determina la gravità dell'avviso (bassa, media, alta). Per impostazione predefinita, verrà generata una determinata quantità di avvisi di gravità bassa, media e alta, ma è possibile aumentare o ridurre il volume in base alle proprie esigenze. Per modificare il volume di avvisi per tutti i criteri di gestione dei rischi insider, scegliere una delle impostazioni seguenti:

- **Meno avvisi:** verranno visualizzati tutti gli avvisi di gravità elevata, meno avvisi di gravità media e nessun avviso di gravità bassa. Questo livello di impostazione significa che potresti perdere alcuni veri positivi.
- **Volume predefinito:** verranno visualizzati tutti gli avvisi di gravità elevata e una quantità bilanciata di avvisi di gravità media e bassa.
- **Altri avvisi:** verranno visualizzati tutti gli avvisi di gravità medio e alto e la maggior parte degli avvisi di gravità bassa. Questo livello di impostazione potrebbe causare più falsi positivi.

### <a name="microsoft-defender-for-endpoint-preview"></a>Microsoft Defender for Endpoint (anteprima)

[Microsoft Defender for Endpoint è](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) una piattaforma di sicurezza degli endpoint aziendale progettata per aiutare le reti aziendali a prevenire, rilevare, analizzare e rispondere alle minacce avanzate. Per avere una migliore visibilità delle violazioni della sicurezza nell'organizzazione, puoi importare e filtrare Defender per gli avvisi endpoint per le attività utilizzate nei criteri creati dai modelli di criteri di violazione della sicurezza per la gestione dei rischi insider.

A seconda dei tipi di segnali che ti interessano, puoi scegliere di importare gli avvisi nella gestione dei rischi insider in base allo stato di valutazione degli avvisi defender per endpoint. È possibile definire uno o più degli stati di triage degli avvisi seguenti nelle impostazioni globali da importare:

- Unknown
- New
- In corso
- Risolti

Gli avvisi di Defender per Endpoint vengono importati ogni giorno. A seconda dello stato di triage scelto, potresti visualizzare più attività utente per lo stesso avviso in cui lo stato della triage cambia in Defender for Endpoint.

Ad esempio, se si seleziona *Nuovo,* *In* corso e Risolto per questa impostazione, quando viene generato un avviso di Microsoft Defender per endpoint e lo stato è *Nuovo*, viene importata un'attività di avviso iniziale per l'utente a rischio insider.  Quando lo stato di valutazione di Defender for Endpoint viene modificato *in In* corso, viene importata una seconda attività per questo avviso per l'utente a rischio insider. Quando lo stato finale di valutazione defender per endpoint è impostato su *Risolto,* viene importata una terza attività per questo avviso per l'utente a rischio insider. Questa funzionalità consente agli investigatori di seguire la progressione degli avvisi di Defender for Endpoint e di scegliere il livello di visibilità richiesto dall'indagine.

>[!IMPORTANT]
>Per importare gli avvisi di violazione della sicurezza è necessario configurare Microsoft Defender for endpoint nell'organizzazione e abilitarlo per l'integrazione della gestione dei rischi Insider in Defender Security Center. Per altre informazioni sulla configurazione di Defender per Endpoint per l'integrazione della gestione dei rischi Insider, vedere [Configurare le funzionalità avanzate in Defender per endpoint](/windows/security/threat-protection/microsoft-defender-atp/advanced-features\#share-endpoint-alerts-with-microsoft-compliance-center).

### <a name="domains-preview"></a>Domini (anteprima)

Le impostazioni del dominio consentono di definire i livelli di rischio per le attività in domini specifici. Queste attività includono la condivisione di file, l'invio di messaggi di posta elettronica, il download o il caricamento di contenuto. Specificando i domini in queste impostazioni, è possibile aumentare o ridurre il punteggio di rischio per l'attività che si svolge con questi domini.

Utilizzare Aggiungi dominio per definire un dominio per ognuna delle impostazioni di dominio. È inoltre possibile utilizzare i caratteri jolly per soddisfare le varianti dei domini radice o dei sottodomini. Ad esempio, per specificare sales.wingtiptoys.com e support.wingtiptoys.com, utilizzare la voce con caratteri jolly '*.wingtiptoys.com' per associare questi sottodomini (e qualsiasi altro sottodominio allo stesso livello). Per specificare sottodomini a più livelli per un dominio radice, è necessario selezionare la casella di controllo Includi **sottodomini** a più livelli.

Per ognuna delle seguenti impostazioni di dominio, è possibile immettere fino a 500 domini:

- **Domini non consentiti:** Se si specificano domini non consentiti, l'attività che si svolge con questi domini avrà *punteggi di* rischio più elevati. Alcuni esempi sono le attività che implicano la condivisione di contenuto con qualcuno (ad esempio l'invio di posta elettronica a un utente con un indirizzo gmail.com) e quando gli utenti scaricano contenuto in un dispositivo da uno di questi domini non consentiti.
- **Domini consentiti:** Alcune attività correlate ai domini consentiti verranno ignorate dai criteri e non genereranno avvisi. Queste attività includono:

    - Posta elettronica inviata a domini esterni
    - File, cartelle, siti condivisi con domini esterni
    - File caricati in domini esterni (con Microsoft Edge browser)

    Specificando i domini consentiti nelle impostazioni, questa attività con questi domini viene trattata in modo analogo a come viene trattata l'attività interna dell'organizzazione. Ad esempio, i domini aggiunti qui e mappano le attività possono implicare la condivisione di contenuto con un utente esterno all'organizzazione (ad esempio l'invio di posta elettronica a un utente con un indirizzo gmail.com).

- **Domini di terze parti:** Se l'organizzazione usa domini di terze parti per scopi aziendali (ad esempio l'archiviazione cloud), includerli qui in modo da poter ricevere avvisi per le attività correlate all'indicatore di dispositivo Utilizzare un browser per scaricare contenuto da un sito di terze *parti.*

## <a name="export-alerts-preview"></a>Esportare avvisi (anteprima)

Le informazioni sugli avvisi per la gestione dei rischi insider sono esportabili nei servizi siem (Security Information and Event Management) tramite lo [schema dell'API](/office/office-365-management-api/office-365-management-activity-api-schema#security-and-compliance-alerts-schema)Office 365 Management Activity . Puoi usare le API di Office 365 Management Activity per esportare le informazioni sugli avvisi in altre applicazioni che l'organizzazione può usare per gestire o aggregare le informazioni sui rischi insider.

Per usare le API per esaminare le informazioni sugli avvisi per i rischi insider:

1. Abilita il Office 365 API di gestione delle attività di gestione in **Insider risk management**  >  **Impostazioni**  >  **Export alerts**. Per impostazione predefinita, questa impostazione è disabilitata per l'Microsoft 365 organizzazione.
2. Filtrare le attività Office 365 controllo in base *a SecurityComplianceAlerts.*
3. Filtra *SecurityComplianceAlerts in* base alla *categoria InsiderRiskManagement.*

![Impostazioni di avviso per l'esportazione della gestione dei rischi Insider](../media/insider-risk-settings-export.png)

Le informazioni sugli avvisi contengono informazioni dello schema degli avvisi di sicurezza e conformità e dello schema comune dell'API di gestione Office 365 sicurezza.

I campi e i valori seguenti vengono esportati per gli avvisi di gestione dei rischi insider per lo schema di avviso sicurezza & conformità:

| **Parametro Alert** | **Descrizione** |
|:------------------|:----------------|
| AlertType | Il tipo dell'avviso è *Personalizzato.*  |
| AlertId | GUID dell'avviso. Gli avvisi per la gestione dei rischi insider sono modificabili. Quando lo stato dell'avviso cambia, viene generato un nuovo registro con lo stesso AlertID. Questo AlertID può essere usato per correlare gli aggiornamenti per un avviso. |
| Categoria | La categoria dell'avviso è *InsiderRiskManagement.* Questa categoria può essere usata per distinguere questi avvisi da altri avvisi di sicurezza & conformità. |
| Commenti | Commenti predefiniti per l'avviso. I valori *sono Nuovo avviso* (registrato quando viene creato un avviso) e Avviso *aggiornato* (registrato quando è presente un aggiornamento di un avviso). Utilizzare AlertID per correlare gli aggiornamenti per un avviso. |
| Dati | I dati dell'avviso includono l'ID utente univoco, il nome dell'entità utente e la data e l'ora (UTC) quando l'utente è stato attivato in un criterio. |
| Nome | Nome dei criteri per i criteri di gestione dei rischi insider che hanno generato l'avviso. |
| PolicyId | GUID del criterio di gestione dei rischi insider che ha attivato l'avviso. |
| Gravità | Gravità dell'avviso. I valori *sono High,* *Medium* o *Low.* |
| Origine | Origine dell'avviso. Il valore è *Office 365 Sicurezza & Conformità*. |
| Stato | Stato dell'avviso. I valori *sono Active* (*Needs Review* in insider risk), *Investigating* (*Confirmed* in insider risk), *Resolved* (*Resolved* in insider risk), *Dismissed* (*Dismissed* in insider risk). |
| Version | Versione dello schema di avviso di sicurezza e conformità. |

I campi e i valori seguenti vengono esportati per gli avvisi di gestione dei rischi insider per lo schema comune dell'API Office 365 [management.](/office/office-365-management-api/office-365-management-activity-api-schema#common-schema)

- UserId
- Id
- RecordType
- CreationTime
- Operazione
- OrganizationId
- UserType
- UserKey

## <a name="priority-user-groups-preview"></a>Gruppi di utenti con priorità (anteprima)

Gli utenti dell'organizzazione possono avere livelli di rischio diversi a seconda della posizione, del livello di accesso alle informazioni riservate o della cronologia dei rischi. L'assegnazione delle priorità all'esame e al punteggio delle attività di questi utenti può aiutare a avvisare l'utente in caso di potenziali rischi che potrebbero avere conseguenze più elevate per l'organizzazione. I gruppi di utenti con priorità nella gestione dei rischi insider consentono di definire gli utenti dell'organizzazione che necessitano di un'ispezione più stretta e di un punteggio di rischio più sensibile. Insieme alle  violazioni dei criteri di  sicurezza da parte degli utenti con priorità e alle perdite di dati da parte dei modelli di criteri degli utenti con priorità, gli utenti aggiunti a un gruppo di utenti con priorità hanno una maggiore probabilità di avvisi di rischio insider e avvisi con livelli di gravità più elevati.

![Impostazioni del gruppo di utenti con priorità di gestione dei rischi Insider](../media/insider-risk-settings-priority-users.png)

Ad esempio, è necessario proteggere da perdite di dati per un progetto estremamente riservato in cui gli utenti hanno accesso alle informazioni riservate. Si sceglie di creare *un gruppo di Project* *utenti* con priorità Riservato per gli utenti dell'organizzazione che lavorano a questo progetto. Utilizzando la procedura  guidata dei criteri e il modello di criteri Perdite di dati per utenti con priorità, è possibile creare un nuovo criterio e assegnare il gruppo *utenti* con priorità Utenti Project riservato al criterio. Le attività esaminate dal criterio per i membri del gruppo di utenti con priorità Project Riservato gli utenti sono più sensibili ai rischi e le attività di questi utenti saranno più propense *a* generare un avviso e a ricevere avvisi con livelli di gravità più elevati.

### <a name="create-a-priority-user-group"></a>Creare un gruppo di utenti con priorità

Per creare un nuovo gruppo di utenti con priorità, si utilizzerà l'impostazione dei controlli nella soluzione di gestione dei rischi **Insider** nel Centro Microsoft 365 conformità. Per creare un gruppo di utenti con priorità, è necessario essere membri del gruppo di ruoli *Insider Risk Management* o Insider Risk Management *Admin.*

Completare la procedura seguente per creare un gruppo di utenti con priorità:

1. Nel Centro [Microsoft 365 conformità,](https://compliance.microsoft.com)passare a Gestione dei rischi **Insider** e selezionare Impostazioni **rischio Insider.**
2. Selezionare la **scheda Priorità gruppi di** utenti
3. Nella scheda **Gruppi di utenti con priorità** selezionare Crea gruppo di utenti con priorità **per** avviare la creazione guidata del gruppo.
4. Nella pagina **Definisci gruppo** completare i campi seguenti:
    - **Nome (obbligatorio):** immettere un nome descrittivo per il gruppo di utenti con priorità. Non è possibile modificare il nome del gruppo di utenti con priorità dopo aver completato la procedura guidata.
    - **Descrizione (facoltativo):** immettere una descrizione per il gruppo di utenti con priorità.
5. Selezionare **Avanti** per continuare.
6. Nella pagina **Scegli** membri  selezionare Scegliere i membri da cercare e selezionare gli account  utente abilitati alla posta elettronica inclusi nel gruppo oppure selezionare la casella di controllo Seleziona tutto per aggiungere al gruppo tutti gli utenti dell'organizzazione. Selezionare **Aggiungi** per continuare o **Annulla** per chiudere senza aggiungere utenti al gruppo.
7. Selezionare **Avanti** per continuare.
8. Nella pagina **Revisione** esaminare le impostazioni scelte per il gruppo di utenti con priorità. Selezionare **Modifica** per modificare uno qualsiasi dei valori del gruppo oppure selezionare **Invia** per creare e attivare il gruppo di utenti con priorità.
9. Nella pagina di conferma, selezionare **Fatto per** uscire dalla procedura guidata.

### <a name="update-a-priority-user-group"></a>Aggiornare un gruppo di utenti con priorità

Per aggiornare un gruppo di utenti con priorità esistente, si utilizzerà l'impostazione dei controlli nella soluzione di gestione dei rischi **Insider** nel Centro Microsoft 365 conformità. Per aggiornare un gruppo di utenti con priorità, è necessario essere membri del gruppo di ruoli *Insider Risk Management* o Insider Risk Management *Admin.*

Completare la procedura seguente per modificare un gruppo di utenti con priorità:

1. Nel Centro [Microsoft 365 conformità,](https://compliance.microsoft.com)passare a Gestione dei rischi **Insider** e selezionare Impostazioni **rischio Insider.**
2. Selezionare la **scheda Priorità gruppi di** utenti
3. Selezionare il gruppo di utenti con priorità che si desidera modificare e selezionare **Modifica gruppo.**
4. Nella pagina **Definisci gruppo** aggiornare il campo Descrizione, se necessario. Non è possibile aggiornare il nome del gruppo di utenti con priorità. Selezionare **Avanti** per continuare.
5. Nella pagina **Scegli membri** aggiungere nuovi membri al gruppo utilizzando il **controllo Scegli** membri. Per rimuovere un utente dal gruppo, selezionare la "X" accanto all'utente che si desidera rimuovere. Selezionare **Avanti** per continuare.
6. Nella pagina **Revisione** esaminare le impostazioni di aggiornamento scelte per il gruppo di utenti con priorità. Selezionare **Modifica** per modificare uno qualsiasi dei valori del gruppo o selezionare **Invia** per aggiornare il gruppo di utenti con priorità.
7. Nella pagina di conferma, selezionare **Fatto per** uscire dalla procedura guidata.

### <a name="delete-a-priority-user-group"></a>Eliminare un gruppo di utenti con priorità

Per eliminare un gruppo di utenti con priorità esistente, si utilizzerà l'impostazione dei controlli nella soluzione di gestione dei rischi **Insider** nel Centro Microsoft 365 conformità. Per eliminare un gruppo di utenti con priorità, è necessario essere membri del gruppo di ruoli *Insider Risk Management* o Insider Risk Management *Admin.*

>[!IMPORTANT]
>L'eliminazione di un gruppo di utenti con priorità lo rimuoverà da qualsiasi criterio attivo a cui è assegnato. Se si elimina un gruppo di utenti con priorità assegnato a un criterio attivo, il criterio non conterrà utenti nell'ambito e sarà effettivamente inattivo e non creerà avvisi.

Completare la procedura seguente per eliminare un gruppo di utenti con priorità:

1. Nel Centro [Microsoft 365 conformità,](https://compliance.microsoft.com)passare a Gestione dei rischi **Insider** e selezionare Impostazioni **rischio Insider.**
2. Selezionare la **scheda Priorità gruppi di** utenti
3. Selezionare il gruppo di utenti con priorità che si desidera modificare e scegliere **Elimina** dal menu dashboard.
4. Nella finestra **di dialogo** Elimina selezionare **Sì** per eliminare il gruppo di utenti con priorità oppure **scegliere Annulla** per tornare al dashboard.

## <a name="priority-physical-assets-preview"></a>Asset fisici prioritari (anteprima)

Identificare l'accesso alle risorse fisiche prioritarie e correlare l'attività di accesso agli eventi utente è un componente importante dell'infrastruttura di conformità. Questi asset fisici rappresentano posizioni prioritarie nell'organizzazione, ad esempio edifici aziendali, data center o sale server. Le attività a rischio insider possono essere associate agli utenti che lavorano in orari insoliti, tentando di accedere a queste aree sensibili o sicure non autorizzate e alle richieste di accesso ad aree di alto livello senza esigenze legittime.

Con gli asset fisici con priorità abilitati e il connettore dati di [badging](import-physical-badging-data.md) fisico configurato, la gestione dei rischi insider integra i segnali dei sistemi di controllo e accesso fisici con altre attività di rischio degli utenti. Esaminando i modelli di comportamento nei sistemi di accesso fisico e correlando queste attività con altri eventi di rischio insider, la gestione dei rischi insider può aiutare gli investigatori e gli analisti di conformità a prendere decisioni di risposta più informate per gli avvisi. L'accesso alle risorse fisiche prioritarie viene ottenuto e identificato nelle informazioni dettagliate in modo diverso dall'accesso alle risorse non prioritarie.

Ad esempio, l'organizzazione ha un sistema di badging per gli utenti che monitora e approva l'accesso fisico alle normali aree di lavoro e ai progetti sensibili. Sono disponibili diversi utenti che lavorano a un progetto sensibile e questi utenti tornano in altre aree dell'organizzazione al termine del progetto. Quando il progetto riservato si avvicina al completamento, si desidera assicurarsi che il lavoro del progetto rimanga riservato e che l'accesso alle aree del progetto sia strettamente controllato.

Si sceglie di abilitare il connettore dati di badging fisico in Microsoft 365 importare le informazioni di accesso dal sistema fisico di badging e specificare asset fisici di priorità nella gestione dei rischi insider. Importando le informazioni dal sistema di badging e correlando le informazioni di accesso fisico con altre attività di rischio identificate nella gestione dei rischi insider, si nota che uno degli utenti del progetto accede agli uffici del progetto dopo il normale orario di lavoro ed esporta anche grandi quantità di dati in un servizio di archiviazione cloud personale dalla normale area di lavoro. Questa attività di accesso fisico associata all'attività online può puntare a possibili furti di dati e gli investigatori e gli analisti di conformità possono intraprendere le azioni appropriate come determinato dalle circostanze per questo utente.

![Asset fisici con priorità di gestione dei rischi insider](../media/insider-risk-settings-priority-assets.png)

### <a name="configure-priority-physical-assets"></a>Configurare asset fisici con priorità

Per configurare gli asset fisici con priorità, si configurerà il connettore di badging fisico e si useranno i controlli delle impostazioni nella soluzione di gestione dei rischi **Insider** nel Centro Microsoft 365 conformità. Per configurare gli asset fisici con priorità, è necessario essere membri del gruppo di ruoli *Insider Risk Management* o Insider Risk Management *Admin*.

Completare la procedura seguente per configurare gli asset fisici con priorità:

1. Seguire i passaggi di configurazione per la gestione dei rischi insider [nell'articolo Introduzione alla gestione dei rischi](insider-risk-management-configure.md) insider. Nel passaggio 3, assicurarsi di configurare il connettore di badging fisico.

    >[!IMPORTANT]
    >Per consentire ai criteri di gestione dei rischi insider di usare e correlare i dati del segnale relativi agli utenti in uscita e terminati con i dati degli eventi dalle piattaforme di controllo fisico e di accesso, è inoltre necessario configurare il connettore hr Microsoft 365. Se si abilita il connettore di badging fisico senza abilitare il connettore hr di Microsoft 365, i criteri di gestione dei rischi insider e processeranno solo gli eventi per le attività di accesso fisico per gli utenti dell'organizzazione.

2. Nel Centro [Microsoft 365 conformità,](https://compliance.microsoft.com)passare a Gestione dei rischi **Insider** e selezionare Impostazioni **rischio Insider** Priorità asset  >  **fisici.**
3. Nella  pagina Asset fisici di priorità è possibile aggiungere manualmente gli ID risorsa fisica che si desidera monitorare per gli eventi degli asset importati dal connettore di badging fisico oppure importare un file .csv di tutti gli ID delle risorse fisiche importati dal connettore di protezione fisica: a) Per aggiungere manualmente gli ID delle risorse fisiche, scegliere Aggiungi asset fisici di **priorità,** immettere un ID risorsa fisica, quindi selezionare **Aggiungi**. Immetti altri ID risorsa fisica e quindi seleziona Aggiungi asset fisici **di priorità** per salvare tutti gli asset immessi.
    b) Per aggiungere un elenco di ID risorsa fisica da un file .csv, scegliere Importa asset fisici **con priorità**. Nella finestra di dialogo Esplora file seleziona .csv file che vuoi importare, quindi seleziona **Apri.** Gli ID risorsa fisica dei file .csv vengono aggiunti all'elenco.
4. Passare alla **scheda Indicatori dei** criteri in Impostazioni.
5. Nella pagina **Indicatori criteri** passare alla sezione **Indicatori** di accesso fisico e selezionare la casella di controllo Accesso fisico dopo la chiusura o l'accesso non riuscito **all'asset sensibile.**
6. Selezionare **Salva** per configurare ed uscire.

### <a name="delete-a-priority-physical-asset"></a>Eliminare un asset fisico con priorità

Per eliminare un asset fisico con priorità esistente, si utilizzerà l'impostazione dei controlli nella soluzione di gestione dei rischi Insider nel Centro Microsoft 365 conformità. Per eliminare un asset fisico con priorità, è necessario essere membri del gruppo di ruoli Insider Risk Management o Insider Risk Management Admin.

>[!IMPORTANT]
>L'eliminazione di un asset fisico di priorità lo rimuove dall'esame da qualsiasi criterio attivo in cui era incluso in precedenza. Gli avvisi generati dalle attività associate all'asset fisico con priorità non vengono eliminati.

Completare la procedura seguente per eliminare un asset fisico con priorità:

1. Nel Centro [Microsoft 365 conformità,](https://compliance.microsoft.com)passare a Gestione dei rischi **Insider** e selezionare Impostazioni **rischio Insider** Priorità asset  >  **fisici.**
2. Nella pagina **Priorità risorse fisiche** selezionare l'asset che si desidera eliminare.
3. Scegliere **Elimina** dal menu azione per eliminare la risorsa.

## <a name="power-automate-flows-preview"></a>Power Automate flussi (anteprima)

[Microsoft Power Automate](/power-automate/getting-started) è un servizio di flusso di lavoro che automatizza le azioni tra applicazioni e servizi. Utilizzando i flussi dei modelli o creati manualmente, è possibile automatizzare le attività comuni associate a tali applicazioni e servizi. Quando si abilitano Power Automate per la gestione dei rischi insider, è possibile automatizzare attività importanti per casi e utenti. È possibile configurare i flussi di Power Automate per recuperare le informazioni su utenti, avvisi e casi e condividere queste informazioni con le parti interessate e altre applicazioni, nonché automatizzare le azioni nella gestione dei rischi insider, ad esempio la pubblicazione di note sul caso. Power Automate flussi di lavoro sono applicabili ai casi e a qualsiasi utente nell'ambito di un criterio.

I clienti con Microsoft 365 che includono la gestione dei rischi insider non necessitano di licenze Power Automate aggiuntive per usare i modelli di gestione dei rischi insider Power Automate insider consigliati. Questi modelli possono essere personalizzati per supportare l'organizzazione e coprire gli scenari di gestione dei rischi insider di base. Se si sceglie di utilizzare le funzionalità di Power Automate premium in questi modelli, creare un modello personalizzato utilizzando il connettore di conformità di Microsoft 365 o utilizzare modelli Power Automate per altre aree di conformità in Microsoft 365, potrebbero essere necessarie altre licenze Power Automate.

I modelli di Power Automate seguenti vengono forniti ai clienti per supportare l'automazione dei processi per gli utenti e i casi di gestione dei rischi insider:

- **Informare** gli utenti quando vengono aggiunti a un criterio di rischio Insider: questo modello è per le organizzazioni con criteri interni, privacy o requisiti normativi che gli utenti devono ricevere una notifica quando sono soggetti a criteri di gestione dei rischi insider. Quando questo flusso viene configurato e selezionato per un utente nella pagina degli utenti, agli utenti e ai relativi responsabili viene inviato un messaggio di posta elettronica quando l'utente viene aggiunto a un criterio di gestione dei rischi insider. Questo modello supporta anche l'aggiornamento di un SharePoint di posta elettronica ospitato in un sito di SharePoint per tenere traccia dei dettagli del messaggio di notifica, ad esempio data/ora e destinatario del messaggio. Se si è scelto di anonimizzare gli utenti in **Impostazioni** privacy, i flussi creati da questo modello non funzioneranno come previsto in modo che la privacy degli utenti sia mantenuta. Power Automate flussi che usano questo modello sono disponibili nel **dashboard Utenti.**
- **Richiedere** informazioni alle risorse umane o aziendali su un utente in un caso di rischio insider: quando agiscono su un caso, gli analisti e gli investigatori del rischio insider potrebbero dover consultare le risorse umane o altri stakeholder per comprendere il contesto delle attività del caso. Quando questo flusso è configurato e selezionato per un caso, analisti e investigatori inviano un messaggio di posta elettronica alle risorse umane e agli stakeholder aziendali configurati per questo flusso. A ogni destinatario viene inviato un messaggio con opzioni di risposta preconfigurato o personalizzabile. Quando i destinatari selezionano un'opzione di risposta, la risposta viene registrata come nota del caso e include informazioni su destinatario e data/ora. Se si è scelto di anonimizzare gli utenti in **Impostazioni** privacy, i flussi creati da questo modello non funzioneranno come previsto in modo che la privacy degli utenti sia mantenuta. Power Automate flussi di lavoro che usano questo modello sono disponibili nel **dashboard Casi.**
- **Notificare al responsabile quando un utente** ha un avviso per i rischi insider: alcune organizzazioni potrebbero dover ricevere una notifica di gestione immediata quando un utente ha un avviso per la gestione dei rischi insider. Quando questo flusso è configurato e selezionato, al responsabile del caso all'utente viene inviato un messaggio di posta elettronica con le informazioni seguenti su tutti gli avvisi caso:
    - Criteri applicabili per l'avviso
    - Data/ora dell'avviso
    - Livello di gravità dell'avviso

    Il flusso aggiorna automaticamente le note del caso che il messaggio è stato inviato e che il flusso è stato attivato. Se si è scelto di anonimizzare gli utenti in **Impostazioni** privacy, i flussi creati da questo modello non funzioneranno come previsto in modo che la privacy degli utenti sia mantenuta. Power Automate flussi di lavoro che usano questo modello sono disponibili nel **dashboard Casi.**
- Creare record per i casi di rischio insider **in ServiceNow**: questo modello è per le organizzazioni che desiderano utilizzare la soluzione ServiceNow per tenere traccia dei casi di gestione dei rischi insider.  In un caso, gli analisti e gli investigatori del rischio insider possono creare un record per il caso in ServiceNow. È possibile personalizzare questo modello per popolare i campi selezionati in ServiceNow in base alle esigenze dell'organizzazione. Power Automate flussi di lavoro che usano questo modello sono disponibili nel **dashboard Casi.** Per ulteriori informazioni sui campi ServiceNow disponibili, vedere l'articolo di [riferimento serviceNow Connector.](/connectors/service-now/)

### <a name="create-a-power-automate-flow-from-insider-risk-management-template"></a>Creare un flusso di Power Automate dal modello di gestione dei rischi insider

Per creare un flusso di Power Automate da un modello di gestione dei rischi insider consigliato, si useranno i controlli delle impostazioni nella soluzione di gestione dei rischi  **Insider** nel Centro conformità Microsoft 365 o nell'opzione Gestisci flussi **di Power Automate** dal controllo **Automate** quando si lavora direttamente nei dashboard Casi o **Utenti.**

Per creare un flusso Power Automate nell'area delle impostazioni, è necessario essere membri del gruppo di ruoli *Insider Risk Management* o Insider Risk Management *Admin.* Per creare un flusso Power Automate  con l'opzione Gestisci flussi di Power Automate, è necessario essere membri di almeno un gruppo di ruoli di gestione dei rischi insider.

Completare i passaggi seguenti per creare un flusso Power Automate da un modello di gestione dei rischi insider consigliato:

1. Nel Centro [Microsoft 365 conformità,](https://compliance.microsoft.com/)passare a Gestione dei rischi **Insider** e selezionare Impostazioni **rischio Insider** Power Automate  >  **flussi.** È inoltre possibile accedere dalle **pagine dei** **dashboard** Casi o Utenti scegliendo **Automatizza** gestione Power Automate  >  **flussi.**
2. Nella pagina **Power Automate flussi** di lavoro selezionare un modello consigliato nella sezione Modelli di gestione dei rischi **insider** che potrebbero piacerti nella pagina.
3. Il flusso elenca le connessioni incorporate necessarie per il flusso e noterà se gli stati della connessione sono disponibili. Se necessario, aggiornare tutte le connessioni che non vengono visualizzate come disponibili. Selezionare **Continua.**
4. Per impostazione predefinita, i flussi consigliati sono preconfigurato con i campi di dati del servizio di Microsoft 365 e insider consigliati necessari per completare l'attività assegnata per il flusso. Se necessario, personalizzare i componenti del flusso utilizzando il **controllo Mostra** opzioni avanzate e configurando le proprietà disponibili per il componente di flusso.
5. Se necessario, aggiungere altri passaggi al flusso selezionando il **pulsante Nuovo** passaggio. Nella maggior parte dei casi, questa operazione non deve essere necessaria per i modelli predefiniti consigliati.
6. Selezionare **Salva bozza** per salvare il flusso per ulteriori configurazioni oppure **selezionare Salva** per completare la configurazione per il flusso.
7. Selezionare **Chiudi** per tornare alla pagina **Power Automate flusso** di lavoro. Il nuovo modello verrà elencato  come flusso nelle schede Flussi di lavoro ed è automaticamente disponibile dal controllo a discesa **Automate** quando si lavora con i casi di gestione dei rischi insider per l'utente che crea il flusso.

>[!IMPORTANT]
>Se altri utenti dell'organizzazione devono accedere al flusso, il flusso deve essere condiviso.

![Gestione dei rischi insider consente di automatizzare i flussi](../media/insider-risk-settings-power-automate-flows.png)

### <a name="create-a-custom-power-automate-flow-for-insider-risk-management"></a>Creare un flusso di Power Automate personalizzato per la gestione dei rischi insider

Alcuni processi e Power Automate flussi di lavoro per l'organizzazione potrebbero essere al di fuori dei modelli di flusso di gestione dei rischi insider consigliati e potrebbe essere necessario creare flussi di lavoro personalizzati per le aree di gestione dei rischi insider. Power Automate flussi di lavoro sono flessibili e supportano una personalizzazione estesa, ma è necessario eseguire alcuni passaggi per l'integrazione con le funzionalità di gestione dei rischi insider.

Completare la procedura seguente per creare un modello di Power Automate personalizzato per la gestione dei rischi insider:

1. **Controllare la licenza Power Automate** flusso di lavoro: per creare flussi di Power Automate personalizzati che usano trigger di gestione dei rischi insider, è necessaria una licenza Power Automate interna. I modelli di flusso di gestione dei rischi insider consigliati non richiedono licenze aggiuntive e sono inclusi come parte della licenza di gestione dei rischi insider.
2. **Creare un flusso automatizzato:** creare un flusso che esegua una o più attività dopo che è stato attivato da un evento di gestione dei rischi insider. Per informazioni dettagliate su come creare un flusso automatizzato, vedere [Create a flow in Power Automate](/power-automate/get-started-logic-flow).
3. **Selezionare il Microsoft 365 di conformità**: Cercare e selezionare il Microsoft 365 di conformità. Questo connettore consente azioni e trigger di gestione dei rischi insider. Per ulteriori informazioni sui connettori, vedere [l'articolo panoramica di riferimento sui](/connectors/connector-reference/) connettori.
4. **Scegliere i trigger di gestione dei rischi** insider per il flusso: la gestione dei rischi insider ha due trigger disponibili per i flussi Power Automate personalizzati:
    - **Per un caso di gestione dei rischi insider selezionato:** i flussi con questo trigger possono essere selezionati dalla pagina dashboard Dei casi di gestione dei rischi insider.
    - **Per un utente selezionato per la gestione dei rischi** insider: i flussi con questo trigger possono essere selezionati dalla pagina Dashboard utenti per la gestione dei rischi insider.
5. Scegliere le azioni di gestione dei rischi insider per il flusso: è possibile scegliere tra diverse azioni per la gestione dei rischi insider da includere nel flusso personalizzato:
    - Ottenere un avviso per la gestione dei rischi insider
    - Ottenere un caso di gestione dei rischi insider
    - Ottenere un utente insider per la gestione dei rischi
    - Ottenere avvisi per la gestione dei rischi insider per un caso
    - Aggiungere una nota sul caso di gestione dei rischi insider

### <a name="share-a-power-automate-flow"></a>Condividere un Power Automate flusso

Per impostazione predefinita, Power Automate flussi creati da un utente sono disponibili solo per tale utente. Per consentire ad altri utenti di gestione dei rischi insider di accedere e usare un flusso, il flusso deve essere condiviso dall'autore del flusso. Per condividere un flusso, si useranno i controlli delle impostazioni nella soluzione di gestione dei rischi **Insider** nel Centro conformità Microsoft 365 o  nell'opzione Gestisci flussi di **Power Automate** dal controllo Automate quando si lavora direttamente nelle pagine del **dashboard** Casi o Utenti. Dopo aver condiviso un flusso, tutti gli utenti con cui è stato condiviso  possono accedere al flusso nell'elenco a discesa **Automatizza** controllo nei dashboard del caso **e dell'utente.**

Per condividere un flusso Power Automate nell'area delle impostazioni, è necessario essere membri del gruppo di ruoli *Insider Risk Management* o Insider Risk Management *Admin.* Per condividere un flusso Power Automate con l'opzione **Gestisci** flussi Power Automate, è necessario essere membri di almeno un gruppo di ruoli di gestione dei rischi insider.

Completare la procedura seguente per condividere un Power Automate flusso:

1. Nel Centro [Microsoft 365 conformità,](https://compliance.microsoft.com)passare a Gestione dei rischi **Insider** e selezionare Impostazioni **rischio Insider** Power Automate  >  **flussi.** È inoltre possibile accedere dalle **pagine dei** **dashboard** Casi o Utenti scegliendo **Automatizza** gestione Power Automate  >  **flussi.**
2. Nella pagina **Power Automate flussi** di lavoro selezionare la scheda **Flussi del** team o Flussi **del** team.
3. Seleziona il flusso da condividere, quindi scegli **Condividi** dal menu delle opzioni del flusso.
4. Nella pagina di condivisione del flusso immettere il nome dell'utente o del gruppo che si desidera aggiungere come proprietario del flusso.
5. Nella finestra **di dialogo Connessione** utilizzata selezionare **OK** per confermare che l'utente o il gruppo aggiunto avrà accesso completo al flusso.

### <a name="edit-a-power-automate-flow"></a>Modificare un Power Automate flusso

Per modificare un flusso, verranno utilizzati i controlli delle impostazioni nella soluzione di gestione dei rischi **Insider** nel Centro conformità Microsoft 365 o  nell'opzione Gestisci flussi di **Power Automate** dal controllo **Automate** quando si lavora direttamente nei **dashboard** Casi o Utenti.

Per modificare un flusso Power Automate nell'area delle impostazioni, è necessario essere membri del gruppo di ruoli *Insider Risk Management* o Insider Risk Management *Admin.* Per modificare un flusso Power Automate  con l'opzione Gestisci Power Automate flussi di lavoro, è necessario essere membri di almeno un gruppo di ruoli di gestione dei rischi insider.

Completare la procedura seguente per modificare un Power Automate flusso:

1. Nel Centro [Microsoft 365 conformità,](https://compliance.microsoft.com)passare a Gestione dei rischi **Insider** e selezionare Impostazioni **rischio Insider** Power Automate  >  **flussi.** È inoltre possibile accedere dalle **pagine dei** **dashboard** Casi o Utenti scegliendo **Automatizza** gestione Power Automate  >  **flussi.**
2. Nella pagina **Power Automate flussi** selezionare un flusso da modificare e scegliere **Modifica** dal menu controllo di flusso.
3. Selezionare i **puntini di sospensione Impostazioni** modificare l'impostazione di un componente di flusso o i puntini di sospensione  >     >  **Elimina** per eliminare un componente di flusso.
4. Selezionare **Salva** e quindi **Chiudi per** completare la modifica del flusso.

### <a name="delete-a-power-automate-flow"></a>Eliminare un Power Automate flusso

Per eliminare un flusso, si useranno i controlli delle impostazioni nella soluzione di gestione dei rischi **Insider** nel Centro conformità di Microsoft 365  o nell'opzione Gestisci flussi di **Power Automate** dal controllo **Automate** quando si lavora direttamente nei **dashboard** Casi o Utenti. Quando un flusso viene eliminato, viene rimosso come opzione per tutti gli utenti.

Per eliminare un Power Automate nell'area delle impostazioni, è necessario essere membri del gruppo di ruoli *Insider Risk Management* o Insider Risk Management *Admin.* Per eliminare un flusso Power Automate con l'opzione **Gestisci** Power Automate flussi di lavoro, è necessario essere membri di almeno un gruppo di ruoli di gestione dei rischi insider.

Completare la procedura seguente per eliminare un Power Automate flusso:

1. Nel Centro [Microsoft 365 conformità,](https://compliance.microsoft.com)passare a Gestione dei rischi **Insider** e selezionare Impostazioni **rischio Insider** Power Automate  >  **flussi.** È inoltre possibile accedere dalle **pagine dei** **dashboard** Casi o Utenti scegliendo **Automatizza** gestione Power Automate  >  **flussi.**
2. Nella pagina **Power Automate flussi** selezionare un flusso da eliminare e scegliere **Elimina** dal menu controllo di flusso.
3. Nella finestra di dialogo di conferma dell'eliminazione, selezionare **Elimina** per rimuovere il flusso oppure **scegliere Annulla** per uscire dall'azione di eliminazione.

## <a name="microsoft-teams-preview"></a>Microsoft Teams (anteprima)

Gli analisti e gli investigatori della conformità possono facilmente usare Microsoft Teams per la collaborazione su casi di gestione dei rischi insider. Possono coordinarsi e comunicare con altri stakeholder in Microsoft Teams per:

- Coordinare ed esaminare le attività di risposta per i casi in canali Teams privati
- Condividere e archiviare in modo sicuro file ed elementi di prova relativi a singoli casi
- Tenere traccia e rivedere le attività di risposta da parte di analisti e investigatori

Dopo Microsoft Teams per la gestione dei rischi insider, viene creato un team Microsoft Teams dedicato ogni volta che viene confermato un avviso e viene creato un caso. Per impostazione predefinita, il team include automaticamente tutti i membri dei gruppi di ruoli *Insider Risk Management,* *Insider Risk Management Analysts* e *Insider Risk Management Investigators* (fino a 100 utenti iniziali). È possibile aggiungere altri collaboratori dell'organizzazione al team dopo la creazione e in base alle esigenze. Per i casi esistenti creati prima di Microsoft Teams, analisti e investigatori possono scegliere di creare un nuovo team di Microsoft Teams quando lavorano in un caso, se necessario.  Dopo aver risolto il caso associato nella gestione dei rischi insider, il team viene automaticamente archiviato (spostato in nascosto e di sola lettura).

Per ulteriori informazioni su come usare team e canali in Microsoft Teams, vedere [Overview of teams and channels in Microsoft Teams](/MicrosoftTeams/teams-channels-overview).

L'abilitazione Microsoft Teams supporto per i casi è facile e veloce da configurare. Per abilitare la Microsoft Teams per la gestione dei rischi insider, completare i passaggi seguenti:

1. Nel Centro [Microsoft 365 conformità,](https://compliance.microsoft.com)passare a **Gestione** dei rischi Insider Impostazioni dei  >  **rischi Insider.**
2. Selezionare la **Microsoft Teams.**
3. Abilitare Microsoft Teams per la gestione dei rischi insider.
4. Selezionare **Salva** per configurare ed uscire.

![Gestione dei rischi insider Microsoft Teams](../media/insider-risk-settings-teams.png)

### <a name="create-a-microsoft-teams-team-for-existing-cases"></a>Creare un Microsoft Teams team per i casi esistenti

Se abiliti Microsoft Teams per la gestione dei rischi insider dopo aver già avuto casi esistenti, dovrai creare manualmente un team per ogni caso in base alle esigenze. Dopo aver abilitato Microsoft Teams supporto nelle impostazioni di gestione dei rischi insider, i nuovi casi creeranno automaticamente un nuovo team Microsoft Teams sicurezza.

Gli utenti hanno bisogno dell'autorizzazione per creare Microsoft 365 gruppi nell'organizzazione per creare un team Microsoft Teams da un caso. Per ulteriori informazioni sulla gestione delle autorizzazioni per Microsoft 365, vedere [Manage who can create Microsoft 365 Groups](../solutions/manage-creation-of-groups.md).

Per creare un team per un caso, userai il controllo Crea team Microsoft quando lavori direttamente in un caso esistente. Completare la procedura seguente per creare un nuovo team:

1. Nel Centro [Microsoft 365 conformità,](https://compliance.microsoft.com)passare a **Casi di** gestione dei rischi Insider e selezionare un caso  >   esistente.
2. Scegliere Crea Microsoft Team dal menu **azione del caso.**
3. Nel campo **Nome team** immettere un nome per il nuovo team Microsoft Teams team.
4. Seleziona **Crea team Microsoft** e quindi seleziona **Chiudi.**

A seconda del numero di utenti assegnati ai gruppi di ruoli di gestione dei rischi insider, potrebbero essere necessario 15 minuti per aggiungere tutti gli investigatori e gli analisti al team di Microsoft Teams per un caso.

## <a name="analytics-preview"></a>Analisi (anteprima)

L'analisi del rischio Insider consente di condurre una valutazione dei potenziali rischi insider nell'organizzazione senza configurare criteri di rischio Insider. Questa valutazione può aiutare l'organizzazione a identificare le potenziali aree con rischio utente più elevato e a determinare il tipo e l'ambito dei criteri di gestione dei rischi Insider che può essere opportuno configurare. Le analisi analitiche offrono i vantaggi seguenti per l'organizzazione:

- Facile da configurare: per iniziare a usare le analisi analitiche, è possibile selezionare Esegui analisi quando richiesto dal suggerimento di analisi o passare > Impostazioni rischio Insider e abilitare l'analisi.
- Requisiti minimi per la privacy: i risultati dell'analisi e le informazioni dettagliate vengono restituiti come attività degli utenti anonimi, i singoli nomi utente non sono identificabili dai revisori.
- Comprendere i potenziali rischi tramite informazioni approfondite consolidate: i risultati dell'analisi consentono di identificare rapidamente le potenziali aree di rischio per gli utenti e i criteri più utili per attenuare questi rischi.

Guarda il [video Insider Risk Management Analytics](https://www.youtube.com/watch?v=5c0P5MCXNXk) per comprendere in che modo l'analisi può contribuire ad accelerare l'identificazione dei potenziali rischi insider e ad agire rapidamente.

L'analisi analizza gli eventi di attività di rischio da diverse origini per identificare informazioni dettagliate sulle potenziali aree di rischio. A seconda della configurazione corrente, l'analisi cerca le attività di rischio idonee nelle aree seguenti:

- **Microsoft 365 log di** controllo : inclusa in tutte le analisi, questa è l'origine principale per identificare la maggior parte delle attività potenzialmente rischiose.
- **Exchange Online**: inclusa in tutte le analisi, l'attività Exchange Online consente di identificare le attività in cui i dati negli allegati vengono inseriti tramite posta elettronica a contatti o servizi esterni.
- **Azure Active Directory**: inclusa in tutte le analisi, la cronologia Azure Active Directory consente di identificare le attività rischiose associate agli utenti con account utente eliminati.
- **Microsoft 365 connettore** dati HR : se configurato, gli eventi del connettore HR consentono di identificare le attività rischiose associate agli utenti con date di chiusura imminenti o di dimissioni imminenti.

Le informazioni analitiche delle analisi si basano sugli stessi segnali di attività di rischio usati dai criteri di gestione dei rischi insider e sui risultati dei report in base alle attività degli utenti singoli e sequenziali. Tuttavia, il punteggio di rischio per l'analisi si basa su un massimo di 30 giorni di attività, mentre i criteri di rischio insider usano l'attività quotidiana per ottenere informazioni dettagliate. Quando abiliti ed esegui l'analisi per la prima volta nell'organizzazione, vedrai i risultati dell'analisi per un giorno. Se si lascia abilitata l'analisi, verranno visualizzati i risultati di ogni analisi giornaliera aggiunta ai report di analisi per un intervallo massimo dei 30 giorni di attività precedenti.

### <a name="enable-analytics-and-start-your-scan"></a>Abilitare l'analisi e avviare l'analisi

Per abilitare l'analisi dei rischi insider, è necessario essere membri del gruppo di ruoli Insider Risk Management, Insider Risk Management Admin o Microsoft 365 Global admin.
Completare la procedura seguente per abilitare l'analisi dei rischi insider:

1. Nel Centro [Microsoft 365 conformità](https://compliance.microsoft.com)passare a Gestione dei **rischi Insider.**
2. Selezionare **Esegui analisi** nella scheda Analisi per i rischi insider **nella** scheda Panoramica della gestione dei rischi **insider.** In questo modo viene attivata l'analisi dell'analisi per l'organizzazione. Puoi anche attivare l'analisi nell'organizzazione accedendo a Impostazioni dei rischi **Insider** Analisi e abilitando  >   **l'analisi dell'attività** utente del tenant per identificare potenziali rischi insider.
3. Nel riquadro **Dei dettagli di** Analisi selezionare Esegui **analisi** per avviare l'analisi per l'organizzazione. I risultati dell'analisi analitica possono richiedere fino a 24 ore prima che i dati analitici siano disponibili come report per la revisione.

![Impostazioni di analisi per la gestione dei rischi Insider](../media/insider-risk-settings-analytics-enable.png)

### <a name="viewing-analytics-insights-and-creating-new-policies"></a>Visualizzazione delle informazioni analitiche e creazione di nuovi criteri

Al termine della prima analisi analitica per l'organizzazione, è possibile visualizzare le informazioni dettagliate e i suggerimenti per le attività potenzialmente rischiose da parte degli utenti. Le analisi giornaliere continueranno a meno che non si dissegni l'analisi per l'organizzazione. Per visualizzare i potenziali rischi per l'organizzazione, passare alla scheda **Panoramica** e selezionare **Visualizza** risultati nella scheda Analisi dei rischi **Insider (anteprima).** Se l'analisi dell'organizzazione non è stata completata, verrà visualizzato un messaggio che indica che l'analisi è ancora attiva.

![Scheda pronta per il report di analisi dei rischi insider](../media/insider-risk-analytics-ready-card.png)

Per le analisi completate, vengono visualizzati i potenziali rischi individuati nell'organizzazione e informazioni dettagliate e suggerimenti per affrontare tali rischi. I rischi identificati e le informazioni dettagliate specifiche sono inclusi nei report raggruppati per area, il numero totale di utenti con rischi identificati, la percentuale di questi utenti con attività potenzialmente rischiose e un criterio di rischio insider consigliato per contribuire a mitigare questi rischi. I report includono:

- **Informazioni dettagliate sulle** perdite di dati : Attività per tutti gli utenti che possono includere la sovrascrittura accidentale di informazioni esterne all'organizzazione o perdite di dati da parte di utenti con intenti dannosi.
- **Informazioni** dettagliate sul furto di dati : attività per utenti in partenza o utenti con account Azure Active Directory eliminati che possono includere la condivisione rischiosa di informazioni esterne all'organizzazione o il furto di dati da parte di utenti con intenti dannosi.
- **Principali informazioni dettagliate sull'esfiltrazione**: attività di tutti gli utenti che possono includere la condivisione di dati all'esterno dell'organizzazione.

![Report di panoramica dell'analisi della gestione dei rischi Insider](../media/insider-risk-analytics-overview.png)

Per visualizzare ulteriori informazioni per una panoramica, selezionare **Visualizza dettagli** per visualizzare il riquadro dei dettagli per le informazioni dettagliate. Il riquadro dei dettagli include i risultati completi delle  informazioni dettagliate, un suggerimento per i criteri di rischio insider e il pulsante Crea criterio per aiutarti rapidamente a creare i criteri consigliati. La selezione di Crea criterio consente di accedere alla procedura guidata dei criteri e di selezionare automaticamente il modello di criteri consigliato correlato alle informazioni dettagliate. Ad esempio, se le  informazioni analitiche  sono relative all'attività di perdita di dati, il modello di criteri Perdite di dati generali verrà pre-selezionato nella procedura guidata per i criteri.

![Report dei dettagli dell'analisi della gestione dei rischi insider](../media/insider-risk-analytics-details.png)

### <a name="turn-off-analytics"></a>Disattivare l'analisi

Per disattivare l'analisi dei rischi insider, è necessario essere membri del gruppo di ruoli Insider *Risk Management,* *Insider Risk Management Admin* o Microsoft 365 global *admin.* Dopo aver disabilitato l'analisi, i report analitici rimangono statici e non verranno aggiornati per i nuovi rischi.

Completare la procedura seguente per disattivare l'analisi dei rischi insider:

1. Nel Centro [Microsoft 365 conformità](https://compliance.microsoft.com)passare a Gestione dei **rischi Insider.**
2. Seleziona **La pagina Analisi delle impostazioni dei rischi**  >  **Insider.**
3. Nella pagina **Analisi** disattivare Analizza **l'attività** utente del tenant per identificare potenziali rischi insider.