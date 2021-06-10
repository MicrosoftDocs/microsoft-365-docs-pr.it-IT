---
title: Application Guard per Office 365 per gli amministratori
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
description: Ottieni le ultime novità nell'isolamento basato su hardware. Impedire attacchi attuali ed emergenti, come exploit o collegamenti dannosi, di compromettere la produttività dei dipendenti e la sicurezza aziendale.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d0fa6ad884c6b21457c8359cf82e32e4b8c100ba
ms.sourcegitcommit: 7ebed5810480d7c49f8ca03207b5ea84993d253f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "51488312"
---
# <a name="application-guard-for-office-for-admins"></a>Application Guard per Office per gli amministratori

**Si applica a:** Word, Excel e PowerPoint per Microsoft 365, Windows 10 Enterprise

Microsoft Defender Application Guard per Office (Application Guard per Office) consente di impedire ai file non attendibili di accedere alle risorse attendibili, proteggendo l'azienda da attacchi nuovi ed emergenti. Questo articolo illustra agli amministratori la configurazione dei dispositivi per un'anteprima di Application Guard per Office. Fornisce informazioni sui requisiti di sistema e sui passaggi di installazione per abilitare Application Guard Office in un dispositivo.

## <a name="prerequisites"></a>Prerequisiti

### <a name="minimum-hardware-requirements"></a>Requisiti hardware minimi

* **CPU**: 64 bit, 4 core (fisici o virtuali), estensioni di virtualizzazione (Intel VT-x OR AMD-V), Core i5 equivalente o superiore consigliato
* **Memoria fisica**: 8 GB di RAM
* **Disco rigido**: 10 GB di spazio libero nell'unità di sistema (SSD consigliato)

### <a name="minimum-software-requirements"></a>Requisiti software minimi

* **Windows 10**: Windows 10 Enterprise, Client Build versione 2004 (20H1) build 19041 o successiva
* **Office**: Office Canale corrente e Canale Enterprise mensile, build versione 2011 16.0.13530.10000 o successiva. Sono supportate sia le versioni a 32 bit che a 64 bit Office.
* **Pacchetto di aggiornamento**: Windows 10 di sicurezza mensile [cumulativo KB4571756](https://support.microsoft.com/help/4571756/windows-10-update-KB4571756)

Per i requisiti di sistema dettagliati, vedere [Requisiti di sistema per Microsoft Defender Application Guard](/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard). Inoltre, fare riferimento alle guide del produttore del computer su come abilitare la tecnologia di virtualizzazione.
Per altre informazioni sui Office di aggiornamento, vedi [Panoramica dei canali di aggiornamento per Microsoft 365](/deployoffice/overview-update-channels).

### <a name="licensing-requirements"></a>Requisiti di licenza

* Microsoft 365 E5 o Microsoft 365 E5 Security

## <a name="deploy-application-guard-for-office"></a>Distribuire Application Guard per Office

### <a name="enable-application-guard-for-office"></a>Abilitare Application Guard per Office

1. Scaricare e installare Windows 10 **aggiornamenti cumulativi della sicurezza mensili KB4571756**.

2. Selezionare **Microsoft Defender Application Guard** in Windows funzionalità e selezionare **OK.** L'abilitazione della funzionalità Application Guard richiederà il riavvio del sistema. Puoi scegliere di riavviare subito o dopo il passaggio 3.

   ![Windows Finestra di dialogo Funzionalità che mostra il gruppo di disponibilità](../../media/ag03-deploy.png)

   La funzionalità può essere abilitata anche eseguendo il seguente comando di PowerShell come amministratore:

   ```powershell
   Enable-WindowsOptionalFeature -online -FeatureName Windows-Defender-ApplicationGuard
   ```

3. Cercare Microsoft Defender Application Guard **in modalità gestita**, criteri di gruppo in Configurazione computer Modelli amministrativi Windows componenti **\\ \\ \\ Microsoft Defender Application Guard**. Attivare questo criterio impostando il valore in Opzioni su **2** o **3** e quindi selezionando **OK** o **Applica.**

   ![Attivare Il gruppo di disponibilità in modalità gestita](../../media/ag04-deploy.png)

   È invece possibile impostare il criterio CSP corrispondente:

   > URI OMA: **./Device/Vendor/MSFT/WindowsDefenderApplicationGuard/Impostazioni/AllowWindowsDefenderApplicationGuard** <br> Tipo di dati: **Integer** <br> Valore: **2**

4. Riavviare il sistema.

### <a name="set-diagnostics--feedback-to-send-full-data"></a>Impostare il feedback & diagnostica per inviare dati completi

> [!NOTE]
> Questa operazione non è necessaria, tuttavia, la configurazione dei dati di diagnostica facoltativi consente di diagnosticare i problemi segnalati.

Questo passaggio garantisce che i dati necessari per identificare e risolvere i problemi raggiungano Microsoft. Segui questi passaggi per abilitare la diagnostica nel dispositivo Windows dispositivo:

1. Apri **Impostazioni** dal menu Start.

   ![Menu Start](../../media/ag05-diagnostic.png)

2. In **Windows Impostazioni** selezionare **Privacy.**

   ![Windows Impostazioni menu](../../media/ag06-diagnostic.png)

3. In Privacy seleziona **Diagnostica & feedback** e seleziona Dati di diagnostica **facoltativi.**

   ![Menu Diagnostica e feedback](../../media/ag07a-diagnostic.png)

Per ulteriori informazioni sulla configurazione Windows di diagnostica, vedere [Configuring Windows diagnostic data in your organization](/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enterprise-management).

### <a name="confirm-that-application-guard-for-office-is-enabled-and-working"></a>Verificare che Application Guard per Office sia abilitato e funzionante

Prima di verificare che Application Guard per Office sia abilitato, avvia Word, Excel o PowerPoint in un dispositivo in cui sono stati distribuiti i criteri. Assicurati che Office sia attivato. Potrebbe essere necessario utilizzare l'identità aziendale per attivare prima Office prodotto.

Per verificare che Application Guard per Office sia abilitato, avviare Word, Excel o PowerPoint e quindi aprire un documento non attendibile. Ad esempio, è possibile aprire un documento scaricato da Internet o un allegato di posta elettronica da un utente esterno all'organizzazione.

Quando apri per la prima volta un file non attendibile, potresti visualizzare una Office iniziale come nell'esempio seguente. Potrebbe essere visualizzato per un certo tempo mentre Application Guard per Office è in fase di attivazione e il file viene aperto. Le successive aperture di file non attendibili dovrebbero essere più veloci.

![app Office iniziale](../../media/ag08-confirm.png)

All'apertura, il file dovrebbe visualizzare alcuni indicatori visivi che il file è stato aperto all'interno di Application Guard per Office:

* Callout sulla barra multifunzione

  ![File doc che mostra una piccola nota di App Guard](../../media/ag09-confirm.png)

* Icona dell'applicazione con uno scudo sulla barra delle applicazioni

  ![Icona nella barra delle applicazioni](../../media/ag12-limitations.png)

## <a name="configure-application-guard-for-office"></a>Configurare Application Guard per Office

Office supporta i criteri seguenti per consentire di configurare le funzionalità di Application Guard per Office. Questi criteri possono essere configurati tramite Criteri di gruppo o tramite il [servizio Office criteri cloud.](/DeployOffice/overview-office-cloud-policy-service)
Vedere la configurazione impostata dall'amministratore esaminando le impostazioni di Criteri di gruppo in Configurazione utente Modelli amministrativi **\\ Microsoft Office \\ 2016 \\ Security Impostazioni Trust Center Application \\ \\ Guard**.


> [!NOTE]
> La configurazione di questi criteri può disabilitare alcune funzionalità per i file aperti in Application Guard per Office.

|Criterio|Descrizione|
|---|---|
|Non usare Application Guard per Office|Se si abilita questo criterio, Word, Excel e PowerPoint utilizzerà il contenitore di isolamento Visualizzazione protetta anziché Application Guard per Office. Questo criterio può essere usato per disabilitare temporaneamente Application Guard per Office quando si verificano problemi a lasciarlo abilitato per Microsoft Edge.|
|Configurare Application Guard per la pre-Office contenitore|Questo criterio determina se Application Guard per Office contenitore, per l'isolamento di file non attendibili, è pre-creato per migliorare le prestazioni di run-time. Se abiliti questa impostazione, puoi specificare il numero di giorni per continuare la pre-creazione di un contenitore o consentire al Office euristico predefinito di pre-creare il contenitore.
|Non consentire copia/incolla per Office documenti aperti in Application Guard per Office|L'abilitazione di questo criterio impedirà a un utente di copiare e incollare il contenuto di un documento aperto in Application Guard per Office a un documento aperto all'esterno di esso.|
|Disabilitare l'accelerazione hardware in Application Guard per Office|Questo criterio controlla se Application Guard per Office l'accelerazione hardware per il rendering della grafica. Se abiliti questa impostazione, Application Guard per Office usa il rendering basato su software (CPU) e non carica driver di grafica di terze parti né interagisce con alcun hardware grafico connesso.
|Disabilitare la protezione dei tipi di file non supportati in Application Guard per Office|Questo criterio controlla se Application Guard per Office blocca l'apertura di tipi di file non supportati o se abilita il reindirizzamento a Visualizzazione protetta.
|Disattivare l'accesso a fotocamera e microfono per i documenti aperti in Application Guard per Office|L'abilitazione di questo criterio Office l'accesso alla fotocamera e al microfono all'interno di Application Guard per Office.|
|Limitare la stampa dai documenti aperti in Application Guard per Office|L'abilitazione di questo criterio limiterà le stampanti su cui un utente può stampare da un file aperto in Application Guard per Office. Ad esempio, è possibile utilizzare questo criterio per limitare gli utenti alla stampa solo in FORMATO PDF.|
|Impedire agli utenti di rimuovere Application Guard per Office protezione dei file|L'abilitazione di questo criterio rimuoverà l'opzione (nell'esperienza dell'applicazione Office) per disabilitare Application Guard per la protezione Office o per aprire un file all'esterno di Application Guard per Office. <p> **Nota:** Gli utenti possono comunque ignorare questo criterio rimuovendo manualmente la proprietà Mark-of-the-Web dal file o spostando un documento in un percorso attendibile.|
|

> [!NOTE]
> I criteri seguenti richiederanno all'utente di disconnettersi e accedere di nuovo per Windows per avere effetto:
>
> * Disabilitare la copia/incolla per i documenti aperti in Application Guard per Office
> * Limitare la stampa per i documenti aperti in Application Guard per Office
> * Disattivare l'accesso a fotocamera e microfono ai documenti aperti in Application Guard per Office

## <a name="submit-feedback"></a>Inviare commenti e suggerimenti

### <a name="submit-feedback-via-feedback-hub"></a>Inviare commenti e suggerimenti tramite Hub di Feedback

Se riscontri problemi durante l'avvio di Application Guard per Office, sei invitato a inviare il tuo feedback tramite Hub di Feedback:

1. Apri **l'app Hub di Feedback** e accedi.

2. Se viene visualizzata una finestra di dialogo di errore durante l'avvio di Application Guard, selezionare Segnala a **Microsoft** nella finestra di dialogo di errore per avviare un nuovo invio di feedback. In caso contrario, <https://aka.ms/mdagoffice-fb> passare a selezionare la categoria corretta per Application Guard, quindi selezionare **+ &nbsp; Aggiungi nuovo feedback** in alto a destra.

3. Immetti un riepilogo nella **casella Riepiloga il tuo feedback** se non è già compilato automaticamente.

4. Immettere una descrizione dettagliata del problema riscontrato e i passaggi da eseguire nella casella Spiega **in** dettaglio, quindi selezionare **Avanti.**

5. Selezionare la bolla accanto a **Problema**. Assicurati che la categoria selezionata sia **Sicurezza e privacy Microsoft Defender Application Guard - \> Office**, quindi seleziona **Avanti**.

6. Seleziona **Nuovo feedback,** quindi **Avanti.**

7. Raccogliere le tracce sul problema:

   1. Espandi il **riquadro Ricrea il problema.**

   2. Se il problema si verifica durante l'esecuzione di Application Guard, aprire un'istanza di Application Guard. L'apertura di un'istanza consente di raccogliere ulteriori tracce dal contenitore di Application Guard.

   3. Seleziona **Avvia registrazione** e attendi che il riquadro smetta di ruotare e pronuncia *Interrompi registrazione.*

   4. Riprodurre completamente il problema con Application Guard. La riproduzione può includere il tentativo di avviare un'istanza di Application Guard e di attendere finché non ha esito negativo o di riprodurre un problema in un'istanza di Application Guard in esecuzione.

   5. Seleziona il riquadro **Interrompi** registrazione.

   6. Mantenere aperte tutte le istanze di Application Guard in esecuzione, anche per alcuni minuti dopo l'invio, in modo che sia possibile raccogliere anche la diagnostica dei contenitori.

8. Allega eventuali screenshot o file rilevanti correlati al problema.

9. Selezionare **Invia**.

### <a name="submit-feedback-via-office-customer-voice"></a>Inviare feedback tramite Office Customer Voice

È inoltre possibile inviare feedback da Office se il problema si verifica quando Office documenti vengono aperti in Application Guard. Fai riferimento al [manuale Office Insider per](https://insider.office.com/handbook) inviare commenti e suggerimenti.

## <a name="integration-with-microsoft-defender-for-endpoint-and-microsoft-defender-for-office-365"></a>Integrazione con Microsoft Defender per Endpoint e Microsoft Defender per Office 365

Application Guard per Office è integrato con Microsoft Defender for Endpoint per fornire il monitoraggio e l'avviso in caso di attività dannose che si verificano nell'ambiente isolato.

[Documenti sicuri in Microsoft E365 E5](/microsoft-365/security/office-365-security/safe-docs) è una funzionalità che usa Microsoft Defender for Endpoint per analizzare i documenti aperti in Application Guard per Office. Per un ulteriore livello di protezione, gli utenti non possono lasciare Application Guard per Office finché non vengono determinati i risultati dell'analisi.

Microsoft Defender for Endpoint è una piattaforma di sicurezza progettata per aiutare le reti aziendali a prevenire, rilevare, analizzare e rispondere alle minacce avanzate. Per altri dettagli su questa piattaforma, vedi [Microsoft Defender for Endpoint.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp) Per altre informazioni sull'onboarding dei dispositivi per questa piattaforma, vedi [Eseguire l'onboarding](/windows/security/threat-protection/microsoft-defender-atp/onboard-configure)dei dispositivi nel servizio Microsoft Defender for Endpoint.

Puoi anche configurare Microsoft Defender per Office 365 per l'utilizzo con Defender per Endpoint. Per altre info, fai riferimento a [Integrate Defender for Office 365 con Microsoft Defender for Endpoint.](integrate-office-365-ti-with-mde.md)

## <a name="limitations-and-considerations"></a>Limitazioni e considerazioni

* Application Guard per Office è una modalità protetta che isola i documenti non attendibili in modo che non possano accedere alle risorse aziendali attendibili, a una intranet, all'identità dell'utente e ai file arbitrari nel computer. Di conseguenza, se un utente tenta di accedere a una funzionalità che ha una dipendenza da tale accesso, ad esempio l'inserimento di un'immagine da un file locale su disco, l'accesso avrà esito negativo e genererà un prompt come nell'esempio seguente. Per consentire a un documento non attendibile di accedere a risorse attendibili, gli utenti devono rimuovere la protezione di Application Guard dal documento.

  ![Finestra di dialogo che consente di mantenere al sicuro questa funzionalità non è disponibile](../../media/ag10-limitations.png)

  > [!NOTE]
  > Consigliare agli utenti di rimuovere la protezione solo se considera attendibile il file e la relativa origine o da dove proveniva.

* Il contenuto attivo in documenti come macro e ActiveX è disabilitato in Application Guard per Office. Gli utenti devono rimuovere la protezione di Application Guard per abilitare il contenuto attivo.

* I file non attendibili da condivisioni di rete o file condivisi da OneDrive, OneDrive for Business o SharePoint Online da un'organizzazione diversa vengono aperti in sola lettura in Application Guard. Gli utenti possono salvare una copia locale di tali file per continuare a lavorare nel contenitore o rimuovere la protezione per lavorare direttamente con il file originale.

* I file protetti da Information Rights Management (IRM) sono bloccati per impostazione predefinita. Se gli utenti desiderano aprire tali file in Visualizzazione protetta, un amministratore deve configurare le impostazioni dei criteri per i tipi di file non supportati per l'organizzazione.

* Tutte le personalizzazioni Office applicazioni in Application Guard per Office non vengono mantenute dopo che un utente si è connesso di nuovo o dopo il riavvio del dispositivo.

* Solo gli strumenti di accessibilità che usano il framework UIA possono offrire un'esperienza accessibile per i file aperti in Application Guard per Office.

* La connettività di rete è necessaria per il primo avvio di Application Guard dopo l'installazione. La connettività è necessaria per application guard per convalidare la licenza.

* Nella sezione info del documento, la *proprietà Last Modified By* può visualizzare **WDAGUtilityAccount** come utente. WDAGUtilityAccount è l'utente anonimo configurato in Application Guard. L'identità dell'utente desktop non viene condivisa all'interno del contenitore di Application Guard.

## <a name="performance-optimizations-for-application-guard-for-office"></a>Ottimizzazioni delle prestazioni per Application Guard per Office

In questa sezione viene fornita una panoramica delle ottimizzazioni delle prestazioni usate in Application Guard per Office. Queste informazioni possono aiutare gli amministratori a diagnosticare i report degli utenti relativi alle prestazioni del Office o del sistema generale quando Application Guard è abilitato.

Application Guard usa un contenitore virtualizzato per isolare i documenti non attendibili dal sistema. Il processo di creazione di un contenitore e la configurazione del contenitore di Application Guard per l'apertura di documenti Office presenta un sovraccarico delle prestazioni che potrebbe influire negativamente sull'esperienza utente quando gli utenti aprono un documento non attendibile.

Per fornire agli utenti l'esperienza di apertura dei file prevista, Application Guard usa la logica per pre-creare un contenitore quando in un sistema viene soddisfatta l'euristica seguente: un utente ha aperto un file in Visualizzazione protetta o Application Guard negli ultimi 28 giorni.

Quando viene soddisfatta questa euristica, Office crea un contenitore di Application Guard per l'utente dopo l'accesso a Windows. Mentre questa operazione di pre-creazione è in corso, le prestazioni del sistema potrebbero rallentare, ma l'effetto si risolve non appena l'operazione viene completata.

> [!NOTE]
> I suggerimenti necessari per l'euristica per pre-creare il contenitore vengono generati da Office applicazioni quando un utente li usa. Se un utente installa Office in un nuovo sistema in cui Application Guard è abilitato, Office non creerà il contenitore prima della prima apertura di un documento non attendibile nel sistema. L'utente osserverà che questo primo file richiede più tempo per l'apertura in Application Guard.

## <a name="known-issues"></a>Problemi noti

* La selezione di collegamenti Web ( `http` o ) non consente di aprire il `https` browser.
* Al momento non è possibile incollare il contenuto o le immagini IN FORMATO RTF Office documenti aperti con Application Guard.
* L'impostazione predefinita per i criteri di protezione dei tipi di file non supportati è bloccare l'apertura di tipi di file non attendibili di Information Rights Management (IRM), CSV o HTML.
* Gli aggiornamenti a .NET potrebbero causare un errore di apertura dei file in Application Guard. Come soluzione alternativa, gli utenti possono riavviare il dispositivo quando si verificano questo errore. Per ulteriori informazioni sul problema, vedere [Receiving an error message when attempting to open Windows Defender Application Guard or Windows Sandbox](https://support.microsoft.com/help/4575917/receiving-an-error-message-when-attempting-to-open-windows-defender-ap).
