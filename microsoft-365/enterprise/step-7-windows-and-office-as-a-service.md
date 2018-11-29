---
title: 'Passaggio 7: Windows e Office come servizio'
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 09/14/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Informazioni su come preparare Windows e Office come servizio nel proprio ambiente.
ms.openlocfilehash: 5c3eb54e07b1cc5492a6d938e97286283fc47ca7
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868673"
---
# <a name="step-7-windows-and-office-as-a-service"></a>Passaggio 7: Windows e Office come servizio

Preparazione per gli aggiornamenti canale semestrali con nuove funzionalità e capacità in Windows 10 e Office 365 ProPlus e per gli aggiornamenti corrispondenti agli strumenti di gestione con System Center Configuration Manager Current Branch.

![](media/step-7-windows-and-office-as-a-service-media/step-7-windows-and-office-as-a-service-media-1.png)

<table>
<thead>
<td><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-10.png" alt="Step 7" height="144" width="144" /></td>
<td><p><strong>Passaggio 7: preparazione per Windows e Office as a Service</strong></p>
<p>Windows 10 e Office 365 ProPlus aggiungono continuamente nuove funzionalità per continuare a offrire esperienze utente e protezione con le ultime novità. Ottenere informazioni su come restare al passo con gli aggiornamenti mensili e semestrali, su come funziona il nuovo modello di manutenzione e sugli strumenti e opzioni disponibili.</p></td>
<td><a href="https://aka.ms/ddev7" target="_blank"><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-20.png" alt="Step 7" height="130" width="231" /></a></td>
</thead>
</table>

>[!NOTE]
>Windows and Office as a Service è il settimo passaggio del nostro processo di distribuzione consigliato che copre la pianificazione della preparazione agli aggiornamenti semestrali delle funzionalità. Per vedere il processo di distribuzione per la versione desktop completa, visitare [Centro distribuzione desktop moderno](https://aka.ms/HowToShift).
>

Sia Windows 10 che Office 365 ProPlus introducono nuove opzioni di assistenza, modelli di supporto e tempistiche di aggiornamento. Queste modifiche semplificano il processo per rimanere aggiornati sulle ultime funzionalità. Insieme a questi aggiornamenti ci sono nuove opzioni di configurazione per abilitare piani di assistenza che soddisfano le esigenze dell'utente.

[Aiutare i clienti nel passaggio a un desktop moderno](https://www.microsoft.com/it-IT/microsoft-365/blog/2018/09/06/helping-customers-shift-to-a-modern-desktop/)

## <a name="update-types"></a>Tipi di aggiornamento

Gli aggiornamenti si dividono in due categorie principali, aggiornamenti delle funzionalità e aggiornamenti qualitativi e di sicurezza che contengono correzioni di errori, sicurezza cumulativa e affidabilità. In termini di cadenza, sia Windows che Office offrono un canale semestrale che offre nuove funzionalità due volte all'anno intorno a marzo e settembre, mentre gli aggiornamenti qualitativi e di sicurezza si verificano mensilmente. Inoltre, solo per le app di Office 365, vengono forniti aggiornamenti canale mensili che sono completamente supportati e contengono sia nuove funzionalità che aggiornamenti qualitativi.

Chi è abituato a un ciclo più lungo tra il sistema operativo desktop e gli aggiornamenti delle app, potrebbe chiedere:

  - Gli aggiornamenti saranno compatibili?

  - Gli utenti devono ricevere un'altra formazione?

  - E quali sono i rischi?

Per rispondere a queste domande e spiegare il motivo dell'offerta più frequente di nuove funzionalità, di seguito vengono presentati alcuni dei vantaggi di questo approccio

### <a name="feature-update-benefits"></a>Vantaggi dell'aggiornamento delle funzionalità

In primo luogo, Microsoft si è allontanata dal modello del passato che introduceva enormi ondate di cambiamento ogni tre anni, fino alle odierne modifiche incrementali più piccole con aggiornamenti delle funzionalità due volte all'anno. Perché? La rapida evoluzione della tecnologia ma anche delle minacce alla sicurezza, conferma la protezione dell'esperienza utente come argomento di grande attualità. Alcuni degli aggiornamenti relativi alla sicurezza, ad esempio, non possono essere forniti solo dagli aggiornamenti di sicurezza mensili o dai file di firma antivirus; possono essere piattaforme a basso livello, come la sicurezza basata sulla virtualizzazione.

[Guida rapida di Windows as a Service](https://docs.microsoft.com/it-IT/windows/deployment/update/waas-quick-start)

[Ridurre le minacce con le funzionalità di sicurezza di Windows 10](https://docs.microsoft.com/it-IT/windows/security/threat-protection/overview-of-threat-mitigations-in-windows-10%20%20)

### <a name="cumulative-update-model-benefits"></a>Vantaggi del modello di aggiornamento cumulativo

Gli aggiornamenti qualitativi e di sicurezza offerti come pacchetto di aggiornamento cumulativo risolvono molti dei problemi del passato. Un tempo era possibile scegliere anche tra una dozzina di aggiornamenti o più ogni mese sia per Windows che per Office. Ovviamente, questa situazione determinava set di matrici quasi impossibili da supportare. Inoltre, se si installa una versione di Windows o Office rilasciata già da un anno o più, potrebbero essere necessarie ore o talvolta giorni per applicare tutti gli aggiornamenti offerti dal rilascio di questa versione.

Con il modello cumulativo, l'utente rimane aggiornato all'ultimo aggiornamento, riducendo così il numero di aggiornamenti mensili che è necessario distribuire. Ogni aggiornamento si basa sugli aggiornamenti dei mesi precedenti e contiene tutte le correzioni necessarie per rimanere aggiornati. Gli aggiornamenti cumulativi sono particolarmente utili quando i PC non vengono utilizzati per diversi mesi, poiché restano in memoria in attesa di essere riassegnati a un altro utente.

[Panoramica di Windows as a Service](https://docs.microsoft.com/it-IT/windows/deployment/update/waas-overview)

### <a name="expanded-validation-of-updates"></a>Convalida estesa degli aggiornamenti

Un altro vantaggio è che, prima di distribuire gli aggiornamenti per un'ampia distribuzione, vengono rilasciate build tramite programmi Insider per [Office](https://products.office.com/en-us/office-insider?tab=Windows-Desktop) e [Windows](https://insider.windows.com/it-IT/) e ciò consente di raccogliere telemetria e feedback prima di rilasciare gli aggiornamenti su larga scala. Attualmente i programmi Insider sono aperti a tutti in modo da poter comprendere in anticipo gli aggiornamenti. Non appena vengono rilasciati aggiornamenti, si riceve telemetria da milioni di configurazioni, pertanto al momento dell'implementazione degli aggiornamenti, la qualità è intrinsecamente più prevedibile

INOLTRE, poiché le build di Office 365 ProPlus Insider riflettono gli aggiornamenti canale mensili, se si utilizza il canale semestrale per Office per fornire aggiornamenti delle funzionalità due volte all'anno in linea con Windows, è possibile convalidare tali build in anticipo utilizzando anche le versioni canale mirate semestrali.

### <a name="supporting-management-tools"></a>Strumenti di gestione di supporto

Al fine di rendere la distribuzione degli aggiornamenti ideale per l'utente, System Center Configuration Manager Current Branch viene aggiornato frequentemente per supportare l'implementazione degli aggiornamenti su Windows e Office e qualsiasi nuova funzionalità.

[Distribuire gli aggiornamenti di Windows 10 con System Center Configuration Manager](https://docs.microsoft.com/it-IT/windows/deployment/update/waas-manage-updates-configuration-manager)

[Gestire Office 365 ProPlus con Configuration Manager](https://docs.microsoft.com/it-IT/sccm/sum/deploy-use/manage-office-365-proplus-updates)

## <a name="phased-deployment-of-updates"></a>Distribuzione a fasi degli aggiornamenti

A questo punto si può procedere sulla spiegazione di come verranno implementati gli aggiornamenti. Per qualsiasi versione, si consigliano almeno tre fasi di distribuzione per l'IT: convalida, distribuzione pilota e distribuzione della produzione estesa. Una volta installato Windows 10 e Office 365 ProPlus, l'utente si avvarrà di manutenzione mensile per rimanere aggiornato con gli aggiornamenti critici di sicurezza e qualitativi, per poi passare alla manutenzione semestrale per le nuove funzionalità.

### <a name="monthly-updating"></a>Aggiornamento mensile

Il modello di servizio è progettato in modo da poter scegliere di limitare l'implementazione delle nuove funzionalità a due volte l'anno e, se necessario, è possibile anche saltare un aggiornamento semestrale e continuare a ricevere aggiornamenti qualitativi e sicurezza. Come accennato, la natura cumulativa degli aggiornamenti mensili comporta che ciascuno aumenterà di dimensioni ogni mese.

#### <a name="express-updates"></a>Express Updates

Usando una tecnologia chiamata "Express Updates" in Windows e Binary Delta Compression in Office, p possibile ridurre significativamente le dimensioni del download. In entrambi gli approcci, i motori di aggiornamento confrontano ciò che è sul PC e trovano solo i differenziali necessari per aggiornare ciò che è presente.

[Aggiornamenti qualitativi di Windows 10 illustrati e fine degli aggiornamenti delta](https://techcommunity.microsoft.com/t5/Windows-IT-Pro-Blog/Windows-10-quality-updates-explained-amp-the-end-of-delta/ba-p/214426)

Windows Update for Business e Windows Server Update Services hanno supportato gli Express Updates per un lungo periodo, tuttavia ora è stato esteso il supporto a System Center Configuration Manager in modo che possa utilizzare anche gli Express Updates.

![](media/step-7-windows-and-office-as-a-service-media/step-7-windows-and-office-as-a-service-media-3.png)

#### <a name="binary-delta-compression"></a>Binary Delta Compression

Binary Delta Compression in Office viene utilizzato solo se si esegue l'aggiornamento dalla versione più recente di Office 365 ProPlus, pertanto per utilizzare questo approccio è necessario aggiornare la build precedente e non è possibile saltare gli aggiornamenti.

I canali di aggiornamento di Windows e Office possono essere gestiti tramite Configuration Manager utilizzando il processo di approvazione e individuazione standard. Inoltre, è possibile utilizzare le impostazioni dei criteri in Office e Windows per applicare i canali di aggiornamento utilizzati e le relative impostazioni.

### <a name="semi-annual-updates"></a>Aggiornamenti semestrali

Quindi queste sono le considerazioni sugli aggiornamenti mensili. Ora si può passare agli aggiornamenti semestrali più grandi.

Come descritto nella sezione relativa alla preparazione di dispositivi e applicazioni, sarà necessario prepararsi per questi aggiornamenti più grandi utilizzando gli stessi strumenti di preparazione configurati nel Passaggio 1 del grafico circolare del processo di distribuzione.

Per quanto riguarda gli strumenti, è possibile utilizzare le impostazioni dei criteri con Windows Update for Business, la gestione degli aggiornamenti software tramite System Center Configuration Manager, Windows Server Update Services (WSUS) o i criteri di aggiornamento impostati da Microsoft Intune. Se si è preoccupati della larghezza di banda della rete, vedere il Passaggio 2: conformità di directory e rete per informazioni sulle opzioni per ridurre il traffico di rete tramite ottimizzazione recapito e altre tecnologie di memorizzazione nella cache peer-to-peer.

![](media/step-7-windows-and-office-as-a-service-media/step-7-windows-and-office-as-a-service-media-4.png)

[Canale semestrale per Windows](https://docs.microsoft.com/it-IT/windows/deployment/update/waas-overview#semi-annual-channel)

[Canale semestrale per Office 365 ProPlus](https://docs.microsoft.com/it-IT/DeployOffice/overview-of-update-channels-for-office-365-proplus#BKMK_SAC)

#### <a name="upgrade-task-sequences"></a>Sequenze di attività di aggiornamento

L'installazione degli aggiornamenti di funzionalità più grandi tramite routine di gestione degli aggiornamenti software standard è un'opzione supportata, ma molte organizzazioni sceglieranno di utilizzare una sequenza di attività di aggiornamento con System Center Configuration Manager o Microsoft Deployment Toolkit.

Una sequenza di attività consente di creare controlli personalizzati o attività PRIMA dell'installazione dell'aggiornamento delle funzionalità e consente di eseguire attività personalizzate DOPO che l'installazione dell'aggiornamento è stata completata. Le attività di post-aggiornamento potrebbero includere servizi di sospensione temporanea se necessario durante l'aggiornamento, installazione sostituzione di driver, aggiornamenti di applicazioni o barra delle applicazioni e impostazioni Start personalizzate di Windows 10.

![](media/step-7-windows-and-office-as-a-service-media/step-7-windows-and-office-as-a-service-media-5.png)

Se l'utente usa già le sequenze di attività per migrare i computer Windows 7 su Windows 10 e conosce bene questi strumenti, ne avrà il massimo controllo. Anche se è possibile utilizzare una singola sequenza di attività per l'intero aggiornamento, è abbastanza comune che le organizzazioni utilizzino due sequenze di attività. Una sequenza di attività per accertarsi che i PC siano pronti per l'aggiornamento, che precede in modo silenzioso tutti i file di installazione richiesti sui computer di destinazione e uno per eseguire l'aggiornamento effettivo. Questo approccio garantisce un impatto minimo sulla produttività dell'utente.

[Creare una sequenza di attività per aggiornare un sistema operativo in Configuration Manager](https://docs.microsoft.com/it-IT/sccm/osd/deploy-use/create-a-task-sequence-to-upgrade-an-operating-system)

#### <a name="semi-annual-channel-support-for-feature-updates"></a>Supporto canale semestrale per l'aggiornamento delle funzionalità

[Come annunciato nel settembre 2018](https://www.microsoft.com/it-IT/microsoft-365/blog/2018/09/06/helping-customers-shift-to-a-modern-desktop/), per il supporto di sequenza temporale per gli aggiornamenti canale semestrali verrà utilizzato il modello seguente.

  - Tutti gli aggiornamenti delle funzionalità attualmente supportati di Windows 10 Enterprise ed Education, a partire dalla versione 1607, saranno supportati per 30 mesi dalla data di rilascio originale.

  - Tutti gli aggiornamenti di funzionalità futuri, a partire da 1809, con assegnazione settembre saranno supportati per 30 mesi dalla data di rilascio.

  - Gli aggiornamenti delle funzionalità future con assegnazione marzo e a partire da 1903 continueranno a essere supportati per 18 mesi dalla data di rilascio.

  - Gli aggiornamenti semestrali di Office 365 ProPlus continuano a essere supportati per 18 mesi

#### <a name="additional-setup-automation-options-outside-of-task-sequences"></a>Ulteriori opzioni di automazione della configurazione al di fuori delle sequenze di attività

Se non si utilizzano le sequenze di attività di aggiornamento, ora è possibile eseguire azioni personalizzate o applicare file del driver durante gli aggiornamenti delle funzioni nella fase di pre-installazione (prima che l'installazione esegua i controlli di compatibilità) o nella fase di pre-commit (prima che l'aggiornamento venga applicato).

[Novità in Windows 10, versione 1803](https://docs.microsoft.com/it-IT/windows/whats-new/whats-new-windows-10-version-1803%23windows-setup)

## <a name="next-step"></a>Passaggio successivo 

## <a name="step-8-user-communications-and-traininghttpsakamsmdd8"></a>[Passaggio 8: formazione e comunicazioni utente](https://aka.ms/mdd8)

## <a name="previous-step"></a>Passaggio precedente 

## <a name="step-6-os-deployment-and-feature-updateshttpsakamsmdd6"></a>[Passaggio 6: distribuzione del sistema operativo e aggiornamenti delle funzionalità](https://aka.ms/mdd6)