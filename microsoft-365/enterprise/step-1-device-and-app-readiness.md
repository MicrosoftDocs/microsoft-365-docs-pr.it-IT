---
title: 'Passaggio 1: preparazione di dispositivi e app'
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
description: Informazioni su come valutare la conformità di dispositivi e app nell'ambiente.
ms.openlocfilehash: a9fa85ea37de06399aa2264b09c61e588edc2107
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868927"
---
# <a name="step-1-device-and-app-readiness"></a>Passaggio 1: preparazione di dispositivi e app

Iniziare il progetto di distribuzione desktop con un inventario dei dispositivi e delle app, con l'assegnazione delle priorità, con l'esecuzione di test sui dispositivi e sulle app cui è stata assegnata la priorità, quindi con la correzione di quanto necessario per prepararsi alla distribuzione.

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
>La preparazione di dispositivi e app rappresenta il primo passaggio del processo di distribuzione consigliato e copre gli aspetti olistici della compatibilità tra applicazione e hardware. Per vedere il processo di distribuzione della versione desktop completa, visitare il [Centro di distribuzione desktop moderno](https://aka.ms/HowToShift).
>

In passato, l'ostacolo principale per l'aggiornamento dei computer desktop degli utenti era la compatibilità di hardware e applicazioni. Finalmente, passando a Windows 10 e Office 365 ProPlus, praticamente ogni applicazione creata negli ultimi 10 anni sarà compatibile con Windows 10 e qualsiasi componente aggiuntivo COM e macro VBA utilizzato dall'organizzazione nelle versioni precedenti di Office (fino a Office 2010) continuerà a essere compatibile nelle versioni più recenti di Office, senza nessuna modifica.

Premesso ciò, a seconda delle dimensioni e della longevità dell'organizzazione, la verifica della compatibilità di hardware e applicazioni rimane comunque un passaggio iniziale fondamentale nel nostro processo di distribuzione a 8 fasi consigliato.

In questo articolo vengono fornite delle indicazioni per guidare gli utenti dalla prima fase (Preparazione di dispositivi e app) usando il nuovo strumento Preparazione aggiornamenti di Windows Analytics, una soluzione basata sul cloud intelligente disponibile con la licenza Windows.

Se al momento Windows Analytics non è configurato per l'ambiente o se si desidera iscriversi per una prova, accedere alla [pagina di Windows Analytics](http://www.aka.ms/windowsanalytics) e iniziare.

## <a name="recommended-tool-windows-analytics-upgrade-readiness"></a>Strumento consigliato: Preparazione aggiornamenti di Windows Analytics

Preparazione aggiornamenti di Windows Analytics offre numerosi vantaggi rispetto ai sistemi di gestione di desktop tradizionali ed è lo strumento che consigliamo. È senza agente, guida l'utente nelle operazioni che devono essere effettuate e sfrutta le informazioni sulla compatibilità di driver e applicazioni raccolte durante l'aggiornamento di centinaia di milioni di PC utente, per fornire una valutazione dettagliata individuando i problemi relativi alla compatibilità che potrebbero impedire l'aggiornamento, con collegamenti alle correzioni consigliate note di Microsoft.

Per configurare Preparazione aggiornamenti di Window Analytics, prima di tutto è necessario configurare un abbonamento ad Azure e includervi un'area di lavoro di Azure Log Analytics. Una volta che il servizio Preparazione aggiornamenti di Windows Analytics è in esecuzione, è possibile registrare qualsiasi dispositivo Windows 7 SP1 o versioni successive connesso a Internet tramite le impostazioni di Criteri di gruppo. È semplicissimo. Non ci sono agenti da distribuire e il flusso di lavoro visivo di Preparazione aggiornamenti di Windows Analytics guida l'utente dalla distribuzione pilota alla distribuzione di produzione. Se si desidera, è possibile esportare i dati da Preparazione aggiornamenti di Windows Analytics agli strumenti di distribuzione software come System Center Configuration Manager, per raggiungere direttamente i PC e creare raccolte non appena diventano disponibili per la distribuzione.

## <a name="device-and-app-readiness-process"></a>Processo di preparazione di dispositivi e app

Il processo di preparazione di dispositivi e app è costituito dai quattro passaggi descritti di seguito: 1. Inventario, 2. Assegnazione della priorità, 3. Test, 4. Correzione.

### <a name="1-inventory"></a>1\. Inventario

Il servizio Preparazione aggiornamenti di Windows Analytics si avvale di un processo senza agente per effettuare un inventario dei computer, delle applicazioni e dei componenti aggiuntivi di Office tra i vari desktop in uso.

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-3.png)

Inoltre, fornisce dei report sui siti Internet più visitati, sulle app e sui percorsi Intranet per aiutare l'utente con la fase di test della compatibilità successiva.

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-4.png)

### <a name="2-prioritize"></a>2\. Assegnazione delle priorità

Una volta effettuato l'inventario, Preparazione aggiornamenti di Windows Analytics consente di identificare e classificare in ordine di priorità l'hardware e le app più comuni utilizzati nell'organizzazione, oltre a indicare su cosa concentrarsi per sbloccare il maggior numero possibile di PC per la distribuzione,

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-5.png)

fornendo anche delle indicazioni che aiutino l'utente a valutare se siano necessari degli aggiornamenti per risolvere i problemi durante il passaggio successivo: il test.

### <a name="3-testing"></a>3\. Test

Si noterà che la maggior parte delle applicazioni, dei driver e dei componenti aggiuntivi di cui viene effettuato l'inventario funziona com'è. Per gli elementi di cui Preparazione aggiornamenti di Windows Analytics rileva problemi, vengono fornite informazioni note, come dove trovare gli aggiornamenti delle versioni per risolvere i problemi relativi alla compatibilità. Anziché spendere tempo e risorse nella risoluzione di problemi complessi di dispositivi meno recenti e applicazioni non fondamentali e con una distribuzione limitata, è possibile concentrarsi sulla collaborazione con gli utenti per ritirare e sostituire tali elementi.

È possibile utilizzare Preparazione aggiornamenti di Windows Analytics anche per valutare i problemi di compatibilità basati sul browser, identificando siti Web e app Web a cui gli utenti continuano ad accedere con controlli ActiveX, oggetti browser helper, VBScript o altre tecnologie legacy non supportate dal browser Microsoft Edge. Gli utenti dovranno continuare a usare Internet Explorer 11 per questi siti ed è possibile aggiungerli all'[elenco di siti con modalità Enterprise](https://docs.microsoft.com/it-IT/microsoft-edge/deploy/emie-to-improve-compatibility) con Enterprise Mode Site List Manager.

Inoltre, per facilitare il passaggio a Office 365 ProPlus, è consigliabile usare [Readiness Toolkit for Office](https://docs.microsoft.com/it-IT/deployoffice/use-the-readiness-toolkit-to-assess-application-compatibility-for-office-365-pro) per testare la compatibilità dei componenti aggiuntivi e delle macro Microsoft Visual Basic for Applications (VBA).

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-6.png)

### <a name="4-remediation"></a>4\. Correzione

La fase finale della preparazione di dispositivi e app consiste nella "correzione". Sarà necessario raccogliere i pacchetti driver e software obbligatori che verranno usati per sostituire o aggiornare le versioni precedenti nell'ambito del processo di distribuzione.

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-7.png)

Man mano che vengono esaminati problemi, un numero sempre maggiore di PC diventa "pronto per la distribuzione". Ciò significa che sia i driver che le app sui PC vengono considerati compatibili con la versione di Windows 10 che si intende utilizzare per la distribuzione.

## <a name="continued-use-of-telemetry-tools"></a>Uso continuo degli strumenti di telemetria

Preparazione aggiornamenti di Windows Analytics non è solo uno strumento che consente di passare a Windows 10 e Office 365 ProPlus. Una volta installato Windows 10 e Office 365 nei computer desktop, è possibile usarlo per gestire la distribuzione e gli aggiornamenti delle funzionalità semestrali per avere sempre le ultime versioni a disposizione.

## <a name="next-step"></a>Passaggio successivo 

## <a name="step-2-directory-and-network-readinesshttpsakamsmdd2"></a>[Passaggio 2: conformità directory e rete](https://aka.ms/mdd2)