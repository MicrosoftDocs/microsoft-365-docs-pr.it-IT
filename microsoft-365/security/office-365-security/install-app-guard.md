---
title: Application Guard per Office 365 per amministratori
keywords: application guard, protezione, isolamento, contenitore isolato, isolamento hardware
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Ottenere la versione più recente dell'isolamento basato su hardware. Impedire attacchi attuali ed emergenti, come exploit o collegamenti dannosi, di compromettere la produttività dei dipendenti e la sicurezza aziendale.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: cf02f6776eb68537486b49c4fe45e8f88eeb38c6
ms.sourcegitcommit: c0cfb9b354db56fdd329aec2a89a9b2cf160c4b0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2021
ms.locfileid: "50094880"
---
# <a name="application-guard-for-office-for-admins"></a>Application Guard per Office per amministratori

**Si applica a:** Word, Excel e PowerPoint per Microsoft 365, Windows 10 Enterprise

Microsoft Defender Application Guard per Office (Application Guard per Office) consente di impedire ai file non attendibili di accedere alle risorse attendibili, proteggendo l'azienda dagli attacchi nuovi ed emergenti. Questo articolo illustra agli amministratori come configurare i dispositivi per un'anteprima di Application Guard per Office. Fornisce informazioni sui requisiti di sistema e sui passaggi di installazione per abilitare Application Guard per Office in un dispositivo.

## <a name="prerequisites"></a>Prerequisiti

### <a name="minimum-hardware-requirements"></a>Requisiti hardware minimi

* **CPU**: 64 bit, 4 core (fisici o virtuali), estensioni di virtualizzazione (Intel VT-x OR AMD-V), Core i5 equivalenti o superiori consigliati
* **Memoria fisica**: 8 GB di RAM
* **Disco rigido:** 10 GB di spazio libero nell'unità di sistema (SSD consigliato)

### <a name="minimum-software-requirements"></a>Requisiti software minimi

* **Windows 10**: Windows 10 Enterprise Edition, Client Build versione 2004 (20H1) build 19041 o successiva
* **Office**: Office Current Channel Build versione 2011 16.0.13530.10000 o successiva. Sono supportate entrambe le versioni a 32 bit e a 64 bit di Office.
* **Pacchetto di aggiornamento:** aggiornamento cumulativo della sicurezza mensile per Windows 10 [KB4571756](https://support.microsoft.com/help/4571756/windows-10-update-KB4571756)

Per i requisiti di sistema dettagliati, fare riferimento [ai requisiti di sistema per Microsoft Defender Application Guard.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard) Per ulteriori informazioni sui canali di aggiornamento di Office, vedere [Panoramica dei canali di aggiornamento per Microsoft 365.](https://docs.microsoft.com/deployoffice/overview-update-channels)

### <a name="licensing-requirements"></a>Requisiti per la licenza

* Microsoft 365 E5 o Microsoft 365 E5 Security

## <a name="deploy-application-guard-for-office"></a>Distribuire Application Guard per Office

### <a name="enable-application-guard-for-office"></a>Abilitare Application Guard per Office

1. Scaricare e installare gli aggiornamenti cumulativi per la sicurezza **mensili di Windows 10 KB4571756.**

2. Seleziona **Microsoft Defender Application Guard** in Funzionalità di Windows e seleziona **OK.** L'abilitazione della funzionalità Application Guard richiederà un riavvio del sistema. È possibile scegliere di riavviare subito o dopo il passaggio 3.

   ![Finestra di dialogo Funzionalità di Windows che mostra Il gruppo di disponibilità](../../media/ag03-deploy.png)

   La funzionalità può essere abilitata anche eseguendo il comando di PowerShell seguente come amministratore:

   ```powershell
   Enable-WindowsOptionalFeature -online -FeatureName Windows-Defender-ApplicationGuard
   ```

3. Cercare **Microsoft Defender Application Guard in modalità gestita**, un criterio di gruppo in Modelli amministrativi di Configurazione computer Componenti di Windows Microsoft Defender Application **\\ \\ \\ Guard.** Attivare questo criterio impostando il valore in Opzioni su **2** o **3** e quindi selezionando **OK** o **Applica.**

   ![Attivare Il gruppo di disponibilità in modalità gestita](../../media/ag04-deploy.png)

   Puoi invece impostare il criterio CSP corrispondente:

   > URI OMA: **./Device/Vendor/MSFT/WindowsDefenderApplicationGuard/Settings/AllowWindowsDefenderApplicationGuard** <br> Tipo di dati: **Integer** <br> Valore: **2**

4. Riavviare il sistema.

### <a name="set-diagnostics--feedback-to-send-full-data"></a>Impostare il feedback & diagnostica per inviare dati completi

Questo passaggio garantisce che i dati necessari per identificare e risolvere i problemi raggiungano Microsoft. Segui questi passaggi per abilitare la diagnostica nel dispositivo Windows:

1. Apri **Impostazioni** dal menu Start.

   ![Menu Start](../../media/ag05-diagnostic.png)

2. In **Impostazioni di Windows** seleziona **Privacy.**

   ![Menu Impostazioni di Windows](../../media/ag06-diagnostic.png)

3. In Privacy, selezionare **Diagnostica & feedback** e selezionare Dati di diagnostica **facoltativi.**

   ![Menu Diagnostica e feedback](../../media/ag07a-diagnostic.png)

Per ulteriori informazioni sulla configurazione delle impostazioni di diagnostica di Windows, vedere [Configurazione dei dati di diagnostica di Windows nell'organizzazione.](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enterprise-management)

### <a name="confirm-that-application-guard-for-office-is-enabled-and-working"></a>Verificare che Application Guard per Office sia abilitato e funzionante

Prima di confermare che Application Guard per Office è abilitato, avviare Word, Excel o PowerPoint in un dispositivo in cui sono stati distribuiti i criteri. Verificare che Office sia attivato. Potrebbe essere necessario utilizzare l'identità aziendale per attivare prima il prodotto Office.

Per verificare che Application Guard per Office sia abilitato, avviare Word, Excel o PowerPoint e quindi aprire un documento non attendibile. Ad esempio, è possibile aprire un documento scaricato da Internet o un allegato di posta elettronica da un utente esterno all'organizzazione.

Quando si apre per la prima volta un file non attendibile, è possibile che venga visualizzata una schermata iniziale di Office come nell'esempio seguente. Potrebbe essere visualizzato per un certo periodo di tempo durante l'attivazione di Application Guard per Office e l'apertura del file. Le successive aperture di file non attendibili dovrebbero essere più veloci.

![Schermata iniziale dell'app di Office](../../media/ag08-confirm.png)

All'apertura, il file dovrebbe visualizzare alcuni indicatori visivi che il file è stato aperto all'interno di Application Guard per Office:

* Callout sulla barra multifunzione

  ![File doc che mostra una piccola nota di App Guard](../../media/ag09-confirm.png)

* Icona dell'applicazione con uno scudo sulla barra delle applicazioni

  ![Icona nella barra delle applicazioni](../../media/ag12-limitations.png)

## <a name="configure-application-guard-for-office"></a>Configurare Application Guard per Office

Office supporta i criteri seguenti per consentire di configurare le funzionalità di Application Guard per Office. Questi criteri possono essere configurati tramite Criteri di gruppo o tramite il servizio criteri cloud di Office.

> [!NOTE]
> La configurazione di questi criteri può disabilitare alcune funzionalità per i file aperti in Application Guard per Office.

|Criteri|Descrizione|
|---|---|
|Non usare Application Guard per Office|L'abilitazione di questo criterio impone a Word, Excel e PowerPoint di utilizzare il contenitore di isolamento Visualizzazione protetta anziché Application Guard per Office. Questo criterio può essere usato per disabilitare temporaneamente Application Guard per Office quando si verificano problemi nel lasciarlo abilitato per Microsoft Edge.|
|Configurare Application Guard per la pre-creazione di contenitori di Office|Questo criterio determina se il contenitore di Application Guard per Office, per l'isolamento dei file non attendibili, è pre-creato per migliorare le prestazioni di run-time. Se si abilita questa impostazione, è possibile specificare il numero di giorni per continuare la pre-creazione di un contenitore o consentire all'euristica predefinita di Office di pre-creare il contenitore.
|Non consentire la copia/incolla per i documenti di Office aperti in Application Guard per Office|L'abilitazione di questo criterio impedisce a un utente di copiare e incollare il contenuto di un documento aperto in Application Guard per Office in un documento aperto all'esterno di esso.|
|Disabilitare l'accelerazione hardware in Application Guard per Office|Questo criterio controlla se Application Guard per Office usa l'accelerazione hardware per il rendering della grafica. Se abiliti questa impostazione, Application Guard per Office usa il rendering basato su software (CPU) e non carica driver grafici di terze parti né interagisce con alcun hardware grafico connesso.
|Disabilitare la protezione dei tipi di file non supportati in Application Guard per Office|Questo criterio controlla se Application Guard per Office blocca l'apertura di tipi di file non supportati o se abilita il reindirizzamento a Visualizzazione protetta.
|Disattivare l'accesso a fotocamera e microfono per i documenti aperti in Application Guard per Office|L'abilitazione di questo criterio rimuove l'accesso di Office alla fotocamera e al microfono all'interno di Application Guard per Office.|
|Limitare la stampa dai documenti aperti in Application Guard per Office|L'abilitazione di questo criterio limiterà le stampanti su cui un utente può stampare da un file aperto in Application Guard per Office. Ad esempio, è possibile utilizzare questo criterio per limitare gli utenti alla stampa solo in formato PDF.|
|Impedire agli utenti di rimuovere Application Guard per la protezione di Office nei file|L'abilitazione di questo criterio rimuove l'opzione (nell'esperienza delle applicazioni di Office) per disabilitare Application Guard per la protezione di Office o per aprire un file all'esterno di Application Guard per Office. <p> **Nota:** Gli utenti possono comunque ignorare questo criterio rimuovendo manualmente la proprietà Mark-of-the-Web dal file o spostando un documento in un percorso attendibile.|
|

> [!NOTE]
> I criteri seguenti richiedono all'utente di disconnettersi e accedere di nuovo a Windows per avere effetto:
>
> * Disabilitare copia/incolla per i documenti aperti in Application Guard per Office
> * Limitare la stampa per i documenti aperti in Application Guard per Office
> * Disattivare l'accesso a fotocamera e microfono ai documenti aperti in Application Guard per Office

## <a name="submit-feedback"></a>Inviare commenti e suggerimenti

### <a name="submit-feedback-via-feedback-hub"></a>Inviare feedback tramite Hub di Feedback

Se si verificano problemi durante l'avvio di Application Guard per Office, si consiglia di inviare il proprio feedback tramite Hub di Feedback:

1. Apri **l'app Hub di Feedback** e accedi.

2. Se viene visualizzata una finestra di dialogo di errore durante l'avvio di Application Guard, seleziona Segnala a **Microsoft** nella finestra di dialogo di errore per avviare un nuovo invio di feedback. In caso contrario, <https://aka.ms/mdagoffice-fb> passa a selezionare la categoria corretta per Application Guard, quindi seleziona **+ &nbsp; Aggiungi nuovo feedback** in alto a destra.

3. Immetti un riepilogo nella **casella Riepiloga il feedback,** se non è già compilato automaticamente.

4. Immettere una descrizione dettagliata del problema riscontrato e i passaggi da eseguire nella casella Spiega **in** maggiore dettaglio, quindi selezionare **Avanti.**

5. Selezionare la finestra accanto a **Problema.** Verificare che la categoria selezionata sia **Sicurezza e privacy di Microsoft Defender Application Guard – \> Office,** quindi selezionare **Avanti.**

6. Selezionare **Nuovo feedback,** quindi **Avanti.**

7. Raccogliere le tracce sul problema:

   1. Espandi il **riquadro Ricrea il problema.**

   2. Se il problema che stai riscontrando si verifica mentre Application Guard è in esecuzione, apri un'istanza di Application Guard. L'apertura di un'istanza consente di raccogliere ulteriori tracce all'interno del contenitore di Application Guard.

   3. Seleziona **Avvia registrazione** e attendi che il riquadro smetta di ruotare e pronuncia *"Interrompi registrazione".*

   4. Riprodurre completamente il problema con Application Guard. La riproduzione può includere il tentativo di avviare un'istanza di Application Guard in attesa di un errore o la riproduzione di un problema in un'istanza di Application Guard in esecuzione.

   5. Seleziona il riquadro **Interrompi** registrazione.

   6. Mantieni aperte tutte le istanze di Application Guard in esecuzione, anche per alcuni minuti dopo l'invio, in modo che sia possibile raccogliere anche la diagnostica del contenitore.

8. Allega eventuali screenshot o file rilevanti correlati al problema.

9. Selezionare **Invia**.

### <a name="submit-feedback-via-office-customer-voice"></a>Inviare commenti e suggerimenti tramite Office Customer Voice

È anche possibile inviare commenti e suggerimenti da Office se il problema si verifica quando i documenti di Office vengono aperti in Application Guard. Fare riferimento al [Manuale office Insider per](https://insider.office.com/handbook) inviare commenti e suggerimenti.

## <a name="integration-with-microsoft-defender-for-endpoint-and-microsoft-defender-for-office-365"></a>Integrazione con Microsoft Defender per Endpoint e Microsoft Defender per Office 365

Application Guard per Office è integrato con Microsoft Defender for Endpoint per fornire il monitoraggio e l'avviso in caso di attività dannose che si verificano nell'ambiente isolato.

Microsoft Defender for Endpoint è una piattaforma di sicurezza progettata per aiutare le reti aziendali a prevenire, rilevare, analizzare e rispondere alle minacce avanzate. Per altri dettagli su questa piattaforma, vedi [Microsoft Defender per Endpoint.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp) Per altre informazioni sull'onboarding dei dispositivi in questa piattaforma, vedi [Eseguire l'onboarding](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/onboard-configure)dei dispositivi nel servizio Microsoft Defender for Endpoint.

È anche possibile configurare Microsoft Defender per Office 365 per l'utilizzo con Defender per Endpoint. Per altre info, fai riferimento a [Integrate Defender per Office 365 con Microsoft Defender for Endpoint.](integrate-office-365-ti-with-wdatp.md)

## <a name="limitations-and-considerations"></a>Limitazioni e considerazioni

* Application Guard per Office è una modalità con restrizioni che isola i documenti non attendibili in modo che non possano accedere alle risorse aziendali attendibili, a una Intranet, all'identità dell'utente e ai file arbitrari nel computer. Di conseguenza, se un utente tenta di accedere a una caratteristica che dipende da tale accesso, ad esempio l'inserimento di un'immagine da un file locale su disco, l'accesso avrà esito negativo e genererà un prompt come nell'esempio seguente. Per consentire a un documento non attendibile di accedere alle risorse attendibili, gli utenti devono rimuovere la protezione di Application Guard dal documento.

  ![Finestra di dialogo che consente di mantenere al sicuro questa funzionalità non è disponibile](../../media/ag10-limitations.png)

  > [!NOTE]
  > Consigliare agli utenti di rimuovere la protezione solo se considera attendibile il file e la relativa origine o da dove proveniva.

* I contenuti attivi in documenti come macro e ActiveX sono disabilitati in Application Guard per Office. Gli utenti devono rimuovere la protezione di Application Guard per abilitare il contenuto attivo.

* I file non attendibili provenienti da condivisioni di rete o da file condivisi da OneDrive, OneDrive for Business o SharePoint Online da un'organizzazione diversa vengono aperti in sola lettura in Application Guard. Gli utenti possono salvare una copia locale di tali file per continuare a lavorare nel contenitore o rimuovere la protezione per lavorare direttamente con il file originale.

* I file protetti da Information Rights Management (IRM) sono bloccati per impostazione predefinita. Se gli utenti desiderano aprire tali file in Visualizzazione protetta, un amministratore deve configurare le impostazioni dei criteri per i tipi di file non supportati per l'organizzazione.

* Qualsiasi personalizzazione delle applicazioni di Office in Application Guard per Office non verrà mantenuta dopo che un utente si è connesso di nuovo o dopo il riavvio del dispositivo.

* Solo gli strumenti di accessibilità che usano il framework uia possono offrire un'esperienza accessibile per i file aperti in Application Guard per Office.

* La connettività di rete è necessaria per il primo avvio di Application Guard dopo l'installazione. La connettività è necessaria per application guard per convalidare la licenza.

* Nella sezione info del documento, la proprietà *Last Modified By* può visualizzare **WDAGUtilityAccount** come utente. WDAGUtilityAccount è l'utente anonimo configurato in Application Guard. L'identità dell'utente desktop non viene condivisa all'interno del contenitore di Application Guard.

## <a name="performance-optimizations-for-application-guard-for-office"></a>Ottimizzazioni delle prestazioni per Application Guard per Office

Questa sezione fornisce una panoramica delle ottimizzazioni delle prestazioni usate in Application Guard per Office. Queste informazioni possono aiutare gli amministratori a diagnosticare i report degli utenti relativi alle prestazioni di Office o del sistema generale quando Application Guard è abilitato.

Application Guard usa un contenitore virtualizzato per isolare i documenti non attendibili dal sistema. Il processo di creazione di un contenitore e configurazione del contenitore di Application Guard per l'apertura dei documenti di Office presenta un sovraccarico delle prestazioni che potrebbe influire negativamente sull'esperienza utente quando gli utenti aprono un documento non attendibile.

Per fornire agli utenti l'esperienza di apertura file prevista, Application Guard usa la logica per pre-creare un contenitore quando in un sistema viene soddisfatta l'euristica seguente: un utente ha aperto un file in Visualizzazione protetta o In Application Guard negli ultimi 28 giorni.

Quando questa euristica viene soddisfatta, Office pre-crea un contenitore di Application Guard per l'utente dopo l'accesso a Windows. Mentre questa operazione di pre-creazione è in corso, le prestazioni del sistema potrebbero rallentare, ma l'effetto verrà risolto non appena l'operazione verrà completata.

> [!NOTE]
> I suggerimenti necessari per la pre-creazione del contenitore da parte dell'euristica vengono generati dalle applicazioni di Office quando vengono utilizzati dall'utente. Se un utente installa Office in un nuovo sistema in cui Application Guard è abilitato, Office non creerà il contenitore prima della prima apertura di un documento non attendibile nel sistema. L'utente osserverà che l'apertura di questo primo file richiede più tempo in Application Guard.

## <a name="known-issues"></a>Problemi noti

* Se si `http` selezionano collegamenti Web ( o ) non si apre il `https` browser.
* L'incollamento di contenuto RTF (Rich Text Format) o di immagini nei documenti di Office aperti con Application Guard non è attualmente supportato.
* Gli aggiornamenti a .NET causano l'errore di apertura dei file in Application Guard. Come soluzione alternativa, gli utenti possono riavviare il dispositivo quando si verificano questo errore. Per altre informazioni sul problema, vedere La ricezione di un messaggio di errore quando si tenta di aprire [Windows Defender Application Guard o Sandbox di Windows.](https://support.microsoft.com/help/4575917/receiving-an-error-message-when-attempting-to-open-windows-defender-ap)
