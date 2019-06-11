---
title: 'Passaggio 1: preparazione di dispositivi e app'
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 05/20/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Informazioni su come valutare la conformità di dispositivi e app nell'ambiente.
ms.openlocfilehash: f45b4c4b38cd2108c706eb6465e9b5ba241e252f
ms.sourcegitcommit: 7e806db3d44ec223754efe1e9613b2c7117c4788
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2019
ms.locfileid: "34814637"
---
# <a name="step-1-device-and-app-readiness"></a>Passaggio 1: preparazione di dispositivi e app

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-1.png)

<table>
<thead>
<td><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-3.png" alt="Step 1" height="130" width="130" /></td>
<td><p><strong>Passaggio 1: preparazione di dispositivi e app</strong></p>
<p>Iniziare il progetto di distribuzione desktop con un inventario dei dispositivi e delle app, con l'assegnazione delle priorità, con l'esecuzione di test sui dispositivi e sulle app cui è stata assegnata la priorità, quindi con la correzione di quanto necessario per prepararsi alla distribuzione.</p></td>
<td><a href="https://aka.ms/ddev1" target="_blank"><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-14.png" alt="Step 1" height="120" width="213" /></a></td>
</thead>
</table>

>[!NOTE]
>La preparazione di dispositivi e app rappresenta il primo passaggio del processo di distribuzione consigliato e copre gli aspetti olistici della compatibilità di applicazioni e componenti hardware. Per vedere il processo di distribuzione desktop completo, visitare il [Centro distribuzione desktop](https://aka.ms/HowToShift).
>

In passato, l'ostacolo principale per l'aggiornamento dei computer desktop degli utenti era la compatibilità di hardware e applicazioni. Finalmente, passando a Windows 10 e Office 365 ProPlus, praticamente ogni applicazione creata negli ultimi 10 anni sarà compatibile con Windows 10 e qualsiasi componente aggiuntivo COM e macro VBA utilizzato dall'organizzazione nelle versioni precedenti di Office (fino a Office 2010) continuerà a essere compatibile nelle versioni più recenti di Office, senza nessuna modifica.

Premesso ciò, a seconda delle dimensioni e della longevità dell'organizzazione, la verifica della compatibilità di hardware e applicazioni rimane comunque un passaggio iniziale fondamentale nel nostro processo di distribuzione a 8 fasi consigliato.

In questo articolo viene illustrata la prima fase, Preparazione di dispositivi e app, usando strumenti di valutazione dello stato di preparazione Microsoft come Preparazione aggiornamenti di Windows Analytics, una soluzione nuova e intelligente basata sul cloud disponibile con la licenza di Windows.

## <a name="windows-10-compatibility-scan"></a>Analisi della compatibilità di Windows 10

Prima di distribuire Windows 10, Microsoft consiglia di controllare l'idoneità dei dispositivi esistenti che eseguono Windows 7 o 8/8.1. Il supporto di installazione di Windows 10 supporta un'opzione della riga di comando per setup.exe, che consente di controllare solo la compatibilità senza eseguire l'aggiornamento. ScanOnly può essere eseguito come file batch con script o integrati in una sequenza di attività di System Center Configuration Manager. È possibile eseguire ScanOnly direttamente dalla rete, in modo che il supporto di installazione di Windows 10 non venga scaricato nel dispositivo locale. Al termine dell'operazione ScanOnly, i risultati vengono restituiti tramite codici di uscita nei file di log generati da Setup.exe.   

Una riga di comando ScanOnly di esempio che completa l'analisi di compatibilità in modo invisibile all'utente avrà un aspetto simile al seguente:

    Setup.EXE /Auto Upgrade /Quiet /NoReboot /Compat ScanOnly

Per altre informazioni su ScanOnly e altre opzioni della riga di comando di Windows, vedere [Opzioni della riga di comando per l'installazione di Windows](https://aka.ms/setupswitches).

## <a name="recommended-tool-windows-analytics-upgrade-readiness"></a>Strumento consigliato: Preparazione aggiornamenti di Windows Analytics

Preparazione aggiornamenti di Windows Analytics offre numerosi vantaggi rispetto ai sistemi di gestione desktop tradizionali ed è lo strumento consigliato. È senza agente e guida l'utente nelle operazioni da eseguire sfruttando le informazioni sulla compatibilità di driver e applicazioni raccolte durante l'aggiornamento di centinaia di milioni di PC. Queste informazioni forniscono una valutazione dettagliata, identificando i problemi di compatibilità che potrebbero impedire l'aggiornamento, con collegamenti alle correzioni consigliate note di Microsoft.

Per configurare Preparazione aggiornamenti di Window Analytics, prima di tutto è necessario configurare una sottoscrizione di Azure e includervi un'area di lavoro di Azure Log Analytics. Una volta che il servizio Preparazione aggiornamenti di Windows Analytics è in esecuzione, è possibile registrare qualsiasi dispositivo Windows 7 SP1 o versioni successive connesso a Internet tramite le impostazioni di Criteri di gruppo. È semplicissimo. Non ci sono agenti da distribuire e il flusso di lavoro visivo di Preparazione aggiornamenti di Windows Analytics guida l'utente dalla distribuzione pilota alla distribuzione di produzione. Volendo, è possibile esportare i dati da Preparazione aggiornamenti di Windows Analytics a strumenti per la distribuzione del software come System Center Configuration Manager, per raggiungere direttamente i PC e creare raccolte non appena sono pronti per la distribuzione.

Se al momento Windows Analytics non è configurato per l'ambiente o se si desidera iscriversi per una prova, accedere alla [pagina di Windows Analytics](http://www.aka.ms/windowsanalytics) e iniziare.

## <a name="device-and-app-readiness-process"></a>Processo di preparazione di dispositivi e app

Il processo di preparazione di dispositivi e app è costituito da quattro passaggi: 1. Inventario, 2 Assegnazione della priorità, 3. Test, 4. Correzione. Di seguito vengono esaminati in dettaglio.

### <a name="1-inventory"></a>1\. Inventario

Il servizio Preparazione aggiornamenti di Windows Analytics si avvale di un processo senza agente per effettuare un inventario dei computer, delle applicazioni e dei componenti aggiuntivi di Office tra i vari desktop in uso.

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-3.png)

Inoltre, fornisce report sui siti Internet più visitati, sulle app e sui percorsi Intranet, per semplificare la successiva fase di test della compatibilità.

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-4.png)

### <a name="2-prioritize"></a>2\. Assegnazione della priorità

Una volta eseguito l'inventario, Preparazione aggiornamenti di Windows Analytics consente di identificare e classificare in ordine di priorità l'hardware e le app più comuni usati nell'organizzazione, oltre a indicare su cosa concentrarsi per sbloccare il maggior numero possibile di PC per la distribuzione.

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-5.png)

Fornisce inoltre indicazioni utili per valutare se siano necessari aggiornamenti per risolvere i problemi durante il passaggio successivo: il test.

### <a name="3-testing"></a>3\. Test

Si noterà che la maggior parte delle applicazioni, dei driver e dei componenti aggiuntivi sottoposti a inventario funzionerà così com'è. Per gli elementi in cui Preparazione aggiornamenti di Windows Analytics rileva problemi, vengono fornite informazioni note, come dove trovare gli aggiornamenti delle versioni per risolvere i problemi di compatibilità. Anziché dedicare tempo e risorse alla risoluzione di problemi complessi in dispositivi meno recenti e applicazioni non fondamentali e con una distribuzione limitata, è possibile concentrarsi sulla collaborazione con gli utenti per ritirare e sostituire tali elementi.

È possibile utilizzare Preparazione aggiornamenti di Windows Analytics anche per valutare i problemi di compatibilità basati sul browser, identificando siti Web e app Web a cui gli utenti continuano ad accedere con controlli ActiveX, oggetti browser helper, VBScript o altre tecnologie legacy non supportate dal browser Microsoft Edge. Gli utenti dovranno continuare a usare Internet Explorer 11 per questi siti ed è possibile aggiungerli all'[elenco di siti con modalità Enterprise](https://docs.microsoft.com/it-IT/microsoft-edge/deploy/emie-to-improve-compatibility) con Enterprise Mode Site List Manager.

Inoltre, per facilitare il passaggio a Office 365 ProPlus, è consigliabile usare [Readiness Toolkit for Office](https://docs.microsoft.com/it-IT/deployoffice/use-the-readiness-toolkit-to-assess-application-compatibility-for-office-365-pro) per testare la compatibilità dei componenti aggiuntivi e delle macro Microsoft Visual Basic for Applications (VBA).

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-6.png)

### <a name="4-remediation"></a>4\. Correzione

La fase finale della preparazione di dispositivi e app è quella di correzione. Sarà necessario raccogliere i pacchetti driver e software necessari che verranno usati per sostituire o aggiornare le versioni precedenti nell'ambito del processo di distribuzione.

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-7.png)

Man mano che vengono esaminati problemi, un numero sempre maggiore di PC diventa "pronto per la distribuzione". Ciò significa che sia i driver che le app sui PC vengono considerati compatibili con la versione di Windows 10 che si intende utilizzare per la distribuzione.

### <a name="configuration-manager-software-inventory-for-application-prioritization"></a>Inventario software di Configuration Manager per la definizione della priorità delle applicazioni

L'inventario software di Configuration Manager è un'alternativa all'uso di soluzioni di analisi basate sul cloud per valutare lo stato di preparazione di dispositivi e app. È possibile tenere traccia del numero di installazioni ed eseguire il drill-down in computer specifici per definire più facilmente le priorità per il test e la convalida della compatibilità, oltre che impostare pacchetti di applicazioni come compatibili con Windows 10 tramite le impostazioni del pacchetto. Anche se questa opzione non offre la possibilità di confrontare le informazioni di compatibilità note con i servizi di analisi di Microsoft, può rappresentare una soluzione efficace per un set ridotto di applicazioni con priorità per il testing manuale. 

Per altre informazioni, vedere [Introduzione all'inventario software in System Center Configuration Manager](https://docs.microsoft.com/it-IT/sccm/core/clients/manage/inventory/introduction-to-software-inventory) e come configurare i requisiti della piattaforma nei pacchetti applicazioni in [Pacchetti e programmi di System Center Configuration Manager](https://docs.microsoft.com/it-IT/sccm/apps/deploy-use/packages-and-programs).


## <a name="desktop-app-assure"></a>Desktop App Assure

Un altro strumento utile per valutare la compatibilità delle app di Windows 10 e Office 365 ProPlus è il programma [Desktop App Assure](https://aka.ms/desktopappassure), disponibile in FastTrack Center. Tramite Desktop App Assure, in caso di problemi validi di compatibilità delle applicazioni sarà possibile collaborare gratuitamente con un tecnico Microsoft per risolvere l'incompatibilità.

## <a name="continued-use-of-diagnostic-data-tools"></a>Uso continuativo di strumenti per i dati di diagnostica

Preparazione aggiornamenti di Windows Analytics non è solo uno strumento che consente di passare a Windows 10 e Office 365 ProPlus. Una volta installato Windows 10 e Office 365 nei computer desktop, è possibile usarlo per gestire la distribuzione e gli aggiornamenti delle funzionalità semestrali per avere sempre le ultime versioni a disposizione.

## <a name="next-step"></a>Passaggio successivo 

## <a name="step-2-directory-and-network-readinesshttpsakamsmdd2"></a>[Passaggio 2: conformità directory e rete](https://aka.ms/mdd2)