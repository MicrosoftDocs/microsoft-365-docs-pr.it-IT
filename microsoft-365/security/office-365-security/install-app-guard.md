---
title: Applicazione di protezione per Office 365 per gli amministratori
keywords: applicazione, protezione, isolamento, contenitore isolato, isolamento hardware
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
description: Ottenere la versione più recente dell'isolamento basato sull'hardware. Impedire attacchi correnti ed emergenti come exploit o collegamenti dannosi dall'interrompere la produttività dei dipendenti e la sicurezza dell'organizzazione.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9a9c9270f61661982108da518d1bf24d2a717b6a
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029727"
---
# <a name="application-guard-for-office-for-admins"></a>Protezione dell'applicazione per Office per gli amministratori

**Si applica a:** Word, Excel e PowerPoint per Microsoft 365, Windows 10 Enterprise

Microsoft Defender Application Guard for Office (Application Guard for Office) consente di evitare che i file non attendibili accedano a risorse attendibili, mantenendo l'organizzazione sicura da attacchi nuovi ed emergenti. In questo articolo vengono illustrati gli amministratori tramite la configurazione dei dispositivi per un'anteprima di Application Guard per Office. Fornisce informazioni sui requisiti di sistema e sui passaggi di installazione per abilitare la protezione delle applicazioni per Office in un dispositivo.

## <a name="prerequisites"></a>Prerequisiti

### <a name="minimum-hardware-requirements"></a>Requisiti hardware minimi

* **CPU**: 64 bit, 4 core (fisico o virtuale), estensioni di virtualizzazione (Intel VT-x o AMD-V), Core i5 equivalente o superiore consigliato
* **Memoria fisica**: 8 GB di RAM
* **Disco rigido**: 10 GB di spazio libero nell'unità di sistema (consigliato da SSD)

### <a name="minimum-software-requirements"></a>Requisiti software minimi

* **Windows 10**: Windows 10 Enterprise Edition, generazione Client versione 2004 (20H1) Build 19041 o versioni successive
* **Office**: versione corrente di Office Channel Build 2011 16.0.13530.10000 o versioni successive
* **Pacchetto di aggiornamento**: aggiornamento della sicurezza cumulativo di Windows 10 [KB4571756](https://support.microsoft.com/help/4571756/windows-10-update-KB4571756)

Per informazioni dettagliate sui requisiti di sistema, vedere [requisiti di sistema per Microsoft Defender Application Guard](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard). Per ulteriori informazioni sui canali di aggiornamento di Office, vedere [Overview of Update channels for Microsoft 365](https://docs.microsoft.com/deployoffice/overview-update-channels).

### <a name="licensing-requirements"></a>Requisiti per la licenza

* Sicurezza di Microsoft 365 E5 o Microsoft 365 E5

## <a name="deploy-application-guard-for-office"></a>Distribuire applicazione di protezione per Office

### <a name="enable-application-guard-for-office"></a>Abilitare la protezione dell'applicazione per Office

1. Scaricare e installare **gli aggiornamenti di sicurezza cumulativi mensili di Windows 10 KB4571756**.

2. Selezionare **Protezione applicazione Microsoft Defender** in funzionalità di Windows e quindi fare clic su **OK**. L'abilitazione della funzionalità di protezione dell'applicazione richiederà un riavvio del sistema. È possibile scegliere di riavviare subito o dopo il passaggio 3.

   ![Finestra di dialogo funzionalità di Windows che mostra AG](../../media/ag03-deploy.png)

   La funzionalità può anche essere abilitata eseguendo il seguente comando di PowerShell come amministratore:

   ```powershell
   Enable-WindowsOptionalFeature -online -FeatureName Windows-Defender-ApplicationGuard
   ```

3. Search for **Microsoft Defender Application Guard in modalità gestita**, un criterio di gruppo in **Configurazione computer \\ modelli amministrativi di \\ Windows Components \\ Microsoft Defender Application Guard**. Attiva questo criterio impostando il valore in opzioni come **2** o **3**, quindi selezionando **OK** o **applica**.

   ![Attivazione di AG in modalità gestita](../../media/ag04-deploy.png)

   È invece possibile impostare il criterio CSP corrispondente:

   > OMA-URI: **./Device/vendor/MSFT/WindowsDefenderApplicationGuard/Settings/AllowWindowsDefenderApplicationGuard** <br> Tipo di dati: **intero** <br> Valore: **2**

4. Riavviare il sistema.

### <a name="set-diagnostics--feedback-to-send-full-data"></a>Set Diagnostics & feedback to Send Full data

Questo passaggio garantisce che i dati necessari per identificare e correggere i problemi raggiungano Microsoft. Seguire questa procedura per abilitare la diagnostica nel dispositivo Windows:

1. Aprire **Impostazioni** dal menu Start.

   ![Menu Start](../../media/ag05-diagnostic.png)

2. Nelle **impostazioni di Windows**, selezionare **privacy**.

   ![Menu impostazioni di Windows](../../media/ag06-diagnostic.png)

3. In privacy, selezionare **diagnostica & Commenti** e selezionare **dati diagnostici facoltativi**.

   ![Menu diagnostica e commenti e suggerimenti](../../media/ag07a-diagnostic.png)

Per ulteriori informazioni sulla configurazione delle impostazioni di diagnostica di Windows, fare riferimento a [configurazione dei dati di diagnostica di Windows nell'organizzazione](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enterprise-management).

### <a name="confirm-that-application-guard-for-office-is-enabled-and-working"></a>Verificare che Application Guard per Office sia abilitato e funzionante

Prima di confermare l'abilitazione di protezione dell'applicazione per Office, avviare Word, Excel o PowerPoint in un dispositivo in cui sono stati distribuiti i criteri. Verificare che Office sia attivato. Potrebbe essere necessario utilizzare l'identità del lavoro per attivare prima il prodotto Office.

Per verificare che Application Guard per Office sia abilitato, avviare Word, Excel o PowerPoint e quindi aprire un documento non attendibile. Ad esempio, è possibile aprire un documento che è stato scaricato da Internet o da un allegato di posta elettronica da un utente esterno all'organizzazione.

Quando si apre per la prima volta un file non attendibile, è possibile che venga visualizzata una schermata iniziale di Office come l'esempio seguente. Potrebbe essere visualizzato per un certo periodo di tempo mentre la protezione dell'applicazione per Office è in fase di attivazione e il file viene aperto. Le aperture successive dei file non attendibili dovrebbero essere più veloci.

![Schermata iniziale dell'app di Office](../../media/ag08-confirm.png)

Al momento dell'apertura, il file deve visualizzare alcuni indicatori visivi che il file è stato aperto all'interno dell'applicazione di protezione per Office:

* Un callout nella barra multifunzione

  ![File doc che mostra le piccole note di protezione delle app](../../media/ag09-confirm.png)

* L'icona dell'applicazione con una schermatura nella barra delle applicazioni

  ![Icona nella barra delle applicazioni](../../media/ag12-limitations.png)

## <a name="configure-application-guard-for-office"></a>Configurare la protezione dell'applicazione per Office

Office supporta i criteri seguenti per consentire di configurare le funzionalità di protezione delle applicazioni per Office. Questi criteri possono essere configurati mediante criteri di gruppo o tramite il servizio criteri cloud di Office.

> [!NOTE]
> La configurazione di questi criteri può disabilitare alcune funzionalità per i file aperti in Application Guard per Office.

|Criteri|Descrizione|
|---|---|
|Non utilizzare Application Guard per Office|L'abilitazione di questo criterio costringerà Word, Excel e PowerPoint a utilizzare il contenitore di isolamento della visualizzazione protetta anziché la protezione dell'applicazione per Office. Questo criterio può essere utilizzato per disabilitare temporaneamente la funzionalità di protezione delle applicazioni per Office quando si verificano problemi di abilitazione per Microsoft Edge.|
|Configurare la protezione dell'applicazione per la precreazione del contenitore di Office|Questo criterio determina se la protezione dell'applicazione per il contenitore di Office, per l'isolamento di file non attendibili, viene creata in precedenza per migliorare le prestazioni di run-time. Se si abilita questa impostazione, è possibile specificare il numero di giorni per continuare la creazione di un contenitore o consentire all'euristica incorporata di Office di creare il contenitore.
|Non consentire la copia/incolla per i documenti di Office aperti in Application Guard per Office|L'abilitazione di questo criterio impedirà a un utente di copiare e incollare il contenuto di un documento aperto in Application Guard for Office a un documento aperto all'esterno di esso.|
|Disabilitare l'accelerazione hardware nell'applicazione di protezione per Office|Questo criterio determina se Application Guard per Office utilizza l'accelerazione hardware per eseguire il rendering della grafica. Se si abilita questa impostazione, Application Guard per Office utilizza il rendering basato su software (CPU) e non caricherà alcun driver di grafica di terze parti o interagirà con qualsiasi hardware grafico connesso.
|Disabilitare la protezione dei tipi di file non supportati in Application Guard per Office|Questo criterio determina se Application Guard per Office bloccherà i tipi di file non supportati dall'apertura o se consentirà il reindirizzamento alla visualizzazione protetta.
|Disattivare l'accesso alla videocamera e al microfono per i documenti aperti in Application Guard per Office|L'abilitazione di questo criterio consente di rimuovere l'accesso di Office alla videocamera e al microfono all'interno dell'applicazione di protezione per Office.|
|Limitare la stampa ai documenti aperti in Application Guard per Office|L'abilitazione di questo criterio consentirà di limitare le stampanti che un utente può stampare da un file aperto in Application Guard for Office. Ad esempio, è possibile utilizzare questo criterio per limitare gli utenti a stampare solo in formato PDF.|
|Impedire agli utenti di rimuovere l'applicazione di protezione per Office Protection nei file|L'abilitazione di questo criterio consente di rimuovere l'opzione (nell'ambito dell'applicazione di Office) per disabilitare l'applicazione di protezione per Office Protection o per aprire un file all'esterno dell'applicazione di protezione per Office. <p> **Nota:** Gli utenti possono comunque ignorare questo criterio rimuovendo manualmente la proprietà Mark-of-the-Web dal file o spostando un documento in un percorso attendibile.|
|

> [!NOTE]
> I criteri seguenti richiederanno all'utente di disconnettersi e accedere di nuovo a Windows per rendere effettive le operazioni riportate di seguito:
>
> * Disattiva copia/incolla per i documenti aperti in applicazione di protezione per Office
> * Limitare la stampa per i documenti aperti in Application Guard per Office
> * Disattivare l'accesso videocamera e MIC ai documenti aperti in Application Guard per Office

## <a name="submit-feedback"></a>Inviare commenti e suggerimenti

### <a name="submit-feedback-via-feedback-hub"></a>Inviare commenti e suggerimenti tramite hub commenti e suggerimenti

Se si verificano problemi durante l'avvio dell'applicazione di protezione per Office, è consigliabile inviare commenti e suggerimenti tramite l'hub dei commenti e suggerimenti:

1. Aprire l' **app dell'hub dei commenti** e accedi.

2. Se si riceve una finestra di dialogo di errore durante l'avvio dell'applicazione, selezionare **segnala a Microsoft** nella finestra di dialogo di errore per avviare un nuovo invio di commenti e suggerimenti. In caso contrario, passare a <https://aka.ms/mdagoffice-fb> per selezionare la categoria corretta per la protezione dell'applicazione, quindi selezionare **+ &nbsp; Aggiungi nuovo feedback** vicino all'angolo in alto a destra.

3. Se non è già stato compilato, immettere un riepilogo nella casella **riepiloga i commenti e suggerimenti** .

4. Immettere una descrizione dettagliata del problema che si è verificato e quali passaggi sono stati apportati nella casella **spiega in altre** informazioni, quindi selezionare **Avanti**.

5. Selezionare la bolla accanto a **problema**. Verificare che la categoria selezionata sia **sicurezza e privacy \> Microsoft Defender Application Guard – Office**, quindi selezionare **Avanti**.

6. Selezionare **nuovo feedback**, quindi **Avanti**.

7. Raccogliere le tracce sul problema:

   1. Espandere la sezione **ricrea il mio problema** .

   2. Se il problema riscontrato si verifica durante l'esecuzione della protezione dell'applicazione, aprire un'istanza di guardia dell'applicazione. L'apertura di un'istanza consente di raccogliere ulteriori tracce dall'interno del contenitore di protezione dell'applicazione.

   3. Seleziona **Avvia registrazione** e attendi che il riquadro smetta di girare e di' *Interrompi registrazione*.

   4. Riprodurre completamente il problema con la protezione dell'applicazione. La riproduzione potrebbe includere il tentativo di avviare un'istanza di protezione dell'applicazione e l'attesa fino a quando non ha esito negativo oppure di riprodurre un problema in un'istanza in esecuzione di protezione dell'applicazione.

   5. Selezionare il riquadro **Interrompi registrazione** .

   6. Tenere aperte tutte le istanze di protezione delle applicazioni in esecuzione, anche per alcuni minuti dopo l'invio, in modo che sia possibile raccogliere anche la diagnostica dei contenitori.

8. Collegare gli screenshot o i file rilevanti relativi al problema.

9. Selezionare **Invia**.

### <a name="submit-feedback-via-office-customer-voice"></a>Inviare commenti e suggerimenti tramite la voce del cliente di Office

È anche possibile inviare commenti e suggerimenti da Office se il problema si verifica quando i documenti di Office vengono aperti nel servizio di protezione dell'applicazione. Fare riferimento a [Office Insider Handbook](https://insider.office.com/handbook) per l'invio di commenti e suggerimenti.

## <a name="integration-with-microsoft-defender-for-endpoint-and-microsoft-defender-for-office-365"></a>Integrazione con Microsoft Defender per endpoint e Microsoft Defender per Office 365

Applicazione di protezione per Office è integrata con Microsoft Defender per endpoint per fornire il monitoraggio e l'avviso di attività dannose che si verifica nell'ambiente isolato.

Microsoft Defender for endpoint è una piattaforma di sicurezza progettata per aiutare le reti aziendali a impedire, rilevare, indagare e rispondere a minacce avanzate. Per ulteriori informazioni su questa piattaforma, vedere [Microsoft Defender for endpoint](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp). Per ulteriori informazioni sui dispositivi di onboarding su questa piattaforma, vedere [dispositivi di bordo per il servizio Microsoft Defender per endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/onboard-configure).

È inoltre possibile configurare Microsoft Defender per Office 365 per l'utilizzo con Defender per endpoint. Per ulteriori informazioni, fare riferimento a [integrazione di Defender per Office 365 con Microsoft Defender per endpoint](integrate-office-365-ti-with-wdatp.md).

## <a name="limitations-and-considerations"></a>Limitazioni e considerazioni

* Applicazione di protezione per Office è una modalità limitata che isola i documenti non attendibili in modo che non possano accedere alle risorse aziendali attendibili, a una rete Intranet, all'identità dell'utente e ai file arbitrari nel computer. Di conseguenza, se un utente tenta di accedere a una funzionalità che ha una dipendenza da tale accesso, ad esempio inserendo un'immagine da un file locale su disco, l'accesso avrà esito negativo e verrà generato un prompt come l'esempio seguente. Per consentire a un documento non attendibile di accedere a risorse attendibili, gli utenti devono rimuovere la protezione delle applicazioni dal documento.

  ![La finestra di dialogo che indica che consente di mantenere la sicurezza, questa funzionalità non è disponibile](../../media/ag10-limitations.png)

  > [!NOTE]
  > Consigliare agli utenti di rimuovere la protezione solo se si considera attendibile il file e la sua origine o da dove proviene.

* Il contenuto attivo in documenti come macro e controlli ActiveX è disabilitato in applicazione di protezione per Office. Gli utenti devono rimuovere la protezione delle applicazioni per abilitare il contenuto attivo.

* File non attendibili provenienti da condivisioni di rete o file condivisi da OneDrive, OneDrive for business o SharePoint Online da un'organizzazione diversa aperta come di sola lettura in applicazione di protezione. Gli utenti possono salvare una copia locale di tali file per continuare a lavorare nel contenitore o rimuovere la protezione per funzionare direttamente con il file originale.

* I file protetti da Information Rights Management (IRM) sono bloccati per impostazione predefinita. Se gli utenti desiderano aprire tali file in visualizzazione protetta, un amministratore deve configurare le impostazioni dei criteri per i tipi di file non supportati per l'organizzazione.

* Tutte le personalizzazioni per le applicazioni di Office in Application Guard for Office non verranno mantenute dopo che un utente ha eseguito l'accesso e non ha eseguito l'accesso o dopo il riavvio del dispositivo.

* Solo gli strumenti di accessibilità che utilizzano il Framework UIA possono fornire un'esperienza accessibile per i file aperti in Application Guard for Office.

* La connettività di rete è necessaria per il primo avvio della protezione dell'applicazione dopo l'installazione. La connettività è necessaria affinché la protezione dell'applicazione convalidi la licenza.

* Nella sezione info del documento, la proprietà *Last modified by* può visualizzare **WDAGUtilityAccount** come utente. WDAGUtilityAccount è l'utente anonimo configurato in Application Guard. L'identità dell'utente desktop non è condivisa all'interno del contenitore di protezione dell'applicazione.

## <a name="performance-optimizations-for-application-guard-for-office"></a>Ottimizzazioni delle prestazioni per l'applicazione di protezione per Office

In questa sezione viene fornita una panoramica delle ottimizzazioni delle prestazioni utilizzate in Application Guard for Office. Queste informazioni consentono agli amministratori di diagnosticare i rapporti degli utenti relativi alle prestazioni di Office o del sistema generale quando l'applicazione di protezione è abilitata.

Application Guard utilizza un contenitore virtualizzato per isolare i documenti non attendibili dal sistema. Il processo di creazione di un contenitore e l'impostazione del contenitore di protezione dell'applicazione per aprire i documenti di Office ha un sovraccarico delle prestazioni che potrebbe influire negativamente sull'esperienza utente quando gli utenti aprono un documento non attendibile.

Per fornire agli utenti l'esperienza di apertura dei file prevista, Application Guard utilizza la logica per creare un contenitore quando viene soddisfatta l'euristica seguente in un sistema: un utente ha aperto un file in visualizzazione protetta o applicazione di protezione negli ultimi 28 giorni.

Quando viene soddisfatta questa euristica, Office crea un contenitore di protezione dell'applicazione per l'utente dopo l'accesso a Windows. Durante l'esecuzione di questa operazione di precreazione, è possibile che il sistema verifichi prestazioni lente, ma l'effetto si risolverà non appena l'operazione viene completata.

> [!NOTE]
> I suggerimenti necessari affinché l'euristica precrei il contenitore vengono generati dalle applicazioni di Office come un utente li utilizza. Se un utente installa Office in un nuovo sistema in cui è abilitata la funzionalità di protezione dell'applicazione, Office non creerà la precreazione del contenitore fino alla prima volta che un utente apre un documento non attendibile nel sistema. L'utente osserverà che questo primo file richiede più tempo per l'apertura nella protezione dell'applicazione.

## <a name="known-issues"></a>Problemi noti

* Se si seleziona collegamenti Web ( `http` o `https` ) non si apre il browser.
* L'incollamento di contenuto in formato RTF (Rich Text Format) o di immagini nei documenti di Office aperti con applicazione di protezione non è supportato in questo momento.
* Gli aggiornamenti a .NET causano la mancata apertura dei file nella protezione dell'applicazione. Come soluzione alternativa, gli utenti possono riavviare il dispositivo quando si incontrano in questo errore. Per ulteriori informazioni sul problema, vedere [ricezione di un messaggio di errore quando si tenta di aprire Windows Defender Application Guard o Windows sandbox](https://support.microsoft.com/help/4575917/receiving-an-error-message-when-attempting-to-open-windows-defender-ap).
