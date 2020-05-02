---
title: Ostacoli alla sicurezza in cui è possibile navigare, ovvero il punto di vista di un architetto
description: Descrizione.
ms.author: bcarter
author: brendacarter
manager: bcarter
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.custom:
- M365solutions
f1.keywords: NOCSH
ms.openlocfilehash: bb9a9d046ed51690f5f7cab5b94e65c3c2e62f11
ms.sourcegitcommit: 101084f9c81616342d78493232d8f13f5ffa4ddf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/01/2020
ms.locfileid: "44003050"
---
# <a name="security-hurdles-you-can-sail-over--one-architects-viewpoint"></a>Ostacoli alla sicurezza in cui è possibile navigare, ovvero il punto di vista di un architetto

In questo articolo, [kozeta Garrett](https://www.linkedin.com/in/kozeta-garrett-53013a6/), architetto Cybersecurity presso Microsoft, descrive le principali sfide alla sicurezza incontrate nelle organizzazioni aziendali e consiglia gli approcci per la navigazione su questi ostacoli. 

## <a name="about-the-author"></a>Informazioni sull'autore

![Foto di kozeta Garrett](../media/solutions-architecture-center/kozeta-garrett-security.jpg) 

Nel mio ruolo di architetto della sicurezza cloud, ho collaborato con più organizzazioni per fornire consulenza strategica e tecnica concentrandosi sulla progettazione e sull'implementazione dell'architettura di sicurezza per i clienti che eseguono la migrazione a Microsoft 365 e Azure, allo sviluppo di soluzioni di sicurezza aziendale e alla trasformazione dell'architettura di sicurezza e delle impostazioni cultura per la resilienza aziendale. My Experience include il rilevamento degli incidenti e la risposta, l'analisi del malware, il test di penetrazione e la raccomandazione di miglioramenti alla sicurezza IT e alla posizione difensiva. Sono molto appassionato di trasformazioni leader che determinano la sicurezza come Enabler per l'azienda, compresi gli sforzi di modernizzazione.

È stato più soddisfacente vedere in che modo le organizzazioni che hanno adottato una mentalità di modernizzazione della sicurezza negli ultimi due anni sono in una posizione ottima che consente loro di continuare a operare in remoto in modo sicuro, nonostante la recente situazione di COVID-19. Purtroppo, queste circostanze sono servite anche come campanello d'invocazione per alcuni clienti, che non sono pronti per questo immediato bisogno. Molte organizzazioni si stanno rendendo conto che devono modernizzarsi rapidamente, ritirare il debito di sicurezza IT accumulato e migliorare la loro posizione di sicurezza durante la notte in modo che possano funzionare in queste circostanze estremamente insolite.

La buona notizia è che Microsoft ha curato alcune risorse ottimali per aiutare le organizzazioni a dilagare rapidamente verso l'alto la loro posizione di sicurezza. Oltre a queste risorse, vorrei condividere le principali sfide che ho incontrato quotidianamente con i clienti nella speranza di poter navigare su questi ostacoli.

Attualmente vivo in Northern Virginia, vicino alla capitale del nostro paese, Washington DC. Mi piace quasi ogni forma di attività all'aria aperta e l'esercizio fisico, come l'esecuzione, mountain bike, escursionismo e nuoto. Per contrastare questi mi piace cucinare tanto, cibo gourmet e viaggi. 


## <a name="partner-with-the-security-team-from-the-start-of-cloud-adoption"></a>Collaborare con il team di sicurezza fin dall'inizio del Cloud Adoption

Per iniziare, non è possibile sottolineare quanto sia importante per i team dell'organizzazione coordinarsi fin dall'inizio. I team di sicurezza devono essere accettati come partner critici nelle fasi iniziali di adozione e progettazione del cloud. Questo significa che i team di sicurezza devono salire a bordo per Champion Cloud Adoption, non solo per le funzionalità aggiuntive per l'azienda (ad esempio, una grande esperienza utente da dispositivi mobili sicuri, applicazioni complete o la creazione di valore sui dati aziendali oltre alla funzionalità limitata di posta elettronica e produttività), ma anche per sfruttare le funzionalità di archiviazione, AI e analisi del calcolo che consentono di risolvere nuove e I team di sicurezza devono essere inclusi nella gestione di tutti gli aspetti di questo spostamento, tra cui le persone (cultura), i processi (formazione) e la tecnologia per avere esito positivo. Significa anche investire nella modernizzazione e nel miglioramento continuo del SOC (Security Operations Center). Collaborare per allineare la strategia di sicurezza con la strategia aziendale e le tendenze dell'ambiente per garantire che la trasformazione digitale venga fatta in modo sicuro. Una volta completata questa operazione, le organizzazioni sviluppano la capacità di adattarsi più rapidamente alle modifiche, incluse le modifiche apportate all'azienda, all'IT e alla sicurezza. 

La maggior parte dei casi in cui è possibile visualizzare i clienti supera gli ostacoli quando non esiste una vera e propria partnership tra le operazioni e i team SOC. Mentre il team delle operazioni viene sottoposto a pressioni e impone scadenze ravvicinate per l'adozione del cloud, i team di sicurezza non sono sempre inclusi all'inizio del processo per la revisione e la pianificazione di una strategia di sicurezza completa. Questo implica l'integrazione di diversi componenti cloud e componenti in-Prem. Questa mancanza di partnership è stata ulteriormente rimandata a diverse squadre che sembrano funzionare in silos per implementare i controlli per i componenti specifici, causando l'aggiunta di complessità di implementazione, risoluzione dei problemi e integrazione.

I clienti che si occupano di tali ostacoli dispongono di una buona partnership tra le operazioni e la governance e i team di gestione della sicurezza e dei rischi per rinnovare la strategia di sicurezza e i requisiti per la protezione dei carichi di lavoro cloud ibridi. Si concentrano sul laser sugli obiettivi e sui risultati di sicurezza definitivi, ovvero la protezione dei dati e la disponibilità di sistemi e servizi in conformità con i requisiti di governance, rischio e conformità di Cybersecurity. Queste organizzazioni sviluppano partnership precoci tra le operazioni e il team di governance e SOC che sono fondamentali per l'approccio di progettazione della sicurezza e massimizzano il valore dei loro investimenti. 

## <a name="build-a-modern-identity-based-security-perimeter"></a>Creare un perimetro di sicurezza moderno (basato su identità)

Adottare quindi un approccio di architettura con zero attendibilità. Questo inizia con la creazione di un perimetro di sicurezza moderno basato sull'identità. Progettare l'architettura di sicurezza in cui ogni tentativo di accesso, sia su-Prem o cloud, viene considerato non attendibile finché non viene verificato, ovvero "mai attendibilità, verifica sempre". Questo approccio di progettazione non solo aumenta la sicurezza e la produttività, ma consente anche agli utenti di lavorare ovunque con qualsiasi tipo di dispositivo. I controlli cloud sofisticati inclusi in Microsoft 365 consentono di proteggere le identità degli utenti e di controllare l'accesso alle risorse importanti in base al livello di rischio dell'utente.

Per una configurazione consigliata, vedere [configurazioni di accesso a identità e dispositivi](../enterprise/microsoft-365-policies-configurations.md). 

## <a name="transition-security-controls-to-the-cloud"></a>Transizione dei controlli di sicurezza nel cloud

Molti team di sicurezza utilizzano ancora le procedure consigliate per la sicurezza tradizionali create per un mondo tutto in locale, incluso il mantenimento di una "sicurezza del perimetro di rete" e il tentativo di "forzare" gli strumenti e i controlli di sicurezza su Cloud Solutions. Tali controlli non sono stati creati per il cloud, sono inefficaci e impediscono l'adozione di funzionalità cloud moderne. I processi e gli strumenti che funzionano per un approccio di sicurezza del perimetro di rete hanno dimostrato di essere inefficienti, ostruttivi nelle funzionalità del cloud e non consentono di sfruttare le funzionalità di sicurezza moderne e automatizzate.

È possibile navigare su questo ostacolo spostando le strategie di difesa per la protezione gestita dal cloud, l'analisi automatizzata e la risoluzione dei problemi, il testing automatico della penna, la protezione avanzata dalle minacce e l'indagine sugli incidenti. I clienti che utilizzano moderne soluzioni di gestione dei dispositivi hanno implementato la gestione automatizzata, il patching standardizzato, l'antivirus, l'applicazione dei criteri e la protezione delle applicazioni su tutti i dispositivi (se si tratta di smartphone, personal computer, laptop o tablet). In questo modo viene eliminata la necessità di una VPN, di Microsoft System Center Configuration Manager (SCCM) e di criteri di gruppo di Active Directory. Questo, insieme ai criteri di accesso condizionale, fornisce un controllo e una visibilità potenti, nonché un accesso semplificato alle risorse indipendentemente dal luogo in cui operano gli utenti.

## <a name="strive-for-best-together-security-tools"></a>Cercare gli strumenti di sicurezza ' migliori insieme '

Un altro ostacolo che vede i clienti inciampare è l'adozione di un approccio "migliore di razza" agli strumenti di sicurezza. Continuamente la sovrapposizione delle soluzioni di punti "Best of Breed" per risolvere i requisiti di sicurezza emergenti causa la ripartizione della sicurezza aziendale. Anche con le migliori intenzioni, gli strumenti nella maggior parte degli ambienti non vengono integrati perché diventano troppo costosi e complessi. Questo, a sua incirca, crea spazi di visibilità perché sono presenti più avvisi per la valutazione rispetto al team che è in grado di gestire. La riqualificazione del team di secops su nuovi strumenti diventa anche una sfida costante.

L'approccio ' Simple is better ' funziona anche per la sicurezza. Invece di seguire gli strumenti "Best of Breed", è possibile navigare su questo ostacolo adottando una strategia "migliore insieme" con strumenti che interagiscono per impostazione predefinita. Le funzionalità di sicurezza di Microsoft proteggono l'intera organizzazione con una protezione integrata delle minacce che si estende su applicazioni, utenti e cloud. L'integrazione consente a un'organizzazione di essere più resiliente e di ridurre i rischi contenendo gli aggressori all'ingresso e di correggere rapidamente gli attacchi.

## <a name="balance-security-with-functionality"></a>Bilanciamento della sicurezza con la funzionalità

Poiché provengo da un background e da un'esperienza di Cybersecurity lunghi, preferirei iniziare con la configurazione più sicura fuori dalla finestra e consentire alle organizzazioni di distendere le configurazioni di sicurezza in base alle proprie esigenze operative e di sicurezza. Tuttavia, questo può avere un prezzo molto alto di funzionalità perse e un'esperienza utente insufficiente. Come molte organizzazioni hanno imparato, se la sicurezza è troppo difficile per gli utenti, troveranno un modo per aggirare l'ambiente, anche utilizzando servizi cloud non gestiti. Per quanto sia difficile per me accettare, sono venuto a rendersi conto che la delicata funzionalità-bilanciamento della sicurezza deve essere raggiunto.

Le organizzazioni che realizzano gli utenti faranno tutto il possibile per far sì che il proprio lavoro riconosca che la battaglia "Shadow IT" non è degna di essere combattuta. Essi riconoscono che i dipendenti IT sono i maggiori trasgressori quando si tratta di Shadow IT e l'utilizzo di applicazioni SaaS non approvate per il loro processo. Hanno spostato la strategia per incoraggiarne l'utilizzo (invece di sopprimere) e concentrarsi sulla riduzione dell'esposizione ai rischi che potrebbe creare. I team di sicurezza di queste organizzazioni non insistono sul fatto che tutto venga bloccato, registrato e inviato tramite un proxy inverso o una VPN. Piuttosto, queste squadre di sicurezza raddoppiano gli sforzi per proteggere i dati importanti e sensibili dall'esporre alle parti errate o alle app dannose. Essi lavorano per proteggere l'integrità dei dati. Sono in grado di utilizzare in modo completo le funzionalità di protezione delle informazioni di cloud più avanzate, tra cui la crittografia, la sicurezza dell'autenticazione a più fattori, il rischio e la conformità automatizzati e le funzionalità di CASB (cloud app Security Broker), consentendo e persino incoraggiando la condivisione protetta su più piattaforme. Essi stanno trasformando Shadow IT in Inspiring Creativity, Productivity, and Collaboration che consente ai propri business di rimanere in vantaggio competitivo.


## <a name="adopt-a-methodical-approach"></a>Adottare un approccio metodico 

La maggior parte delle sfide che ho sperimentato con l'implementazione della sicurezza cloud in organizzazioni diverse, indipendentemente dall'industria, sono state molto simili. Prima di tutto, sebbene vi sia una grande quantità di documentazione su caratteristiche e funzionalità specifiche, vi è un livello di confusione a livello di organizzazione in merito a ciò che si applica, in cui si sovrappongono le funzionalità di sicurezza e in che modo le funzionalità devono essere integrate. È inoltre presente un livello di incertezza su quali funzionalità di sicurezza vengono preconfigurate fuori dalla casella e che richiedono la configurazione da parte dell'organizzazione. Inoltre, i team SOC purtroppo non hanno avuto l'esposizione completa, la formazione o la dotazione preventiva necessaria per preparare la rapida adozione del cloud e la trasformazione digitale che le loro organizzazioni sono già in corso.

Per risolvere questi ostacoli, Microsoft ha curato diverse risorse progettate per semplificare l'adozione di un approccio metodico alla strategia di sicurezza e all'implementazione. 


|Risorsa   |Ulteriori informazioni  |
|---------|---------|
|[Attività principali per i team di sicurezza che supportano l'utilizzo da casa](../security/top-security-tasks-for-remote-work.md)      | Se si trova all'improvviso il supporto di una forza lavoro per la maggior parte della casa, questo articolo consente di velocizzare rapidamente la sicurezza. Include attività consigliate superiori in base al piano di gestione delle licenze.    |
|[Microsoft 365 Security for business decisions makers](../security/Microsoft-365-security-for-bdm.md)    | Quando si ha tempo per un piano più completo, in questo articolo sono inclusi i suggerimenti relativi a Microsoft 365, in base alla priorità della superficie di attacco. Viene fornito anche con un foglio di calcolo che è possibile utilizzare per ordinare le licenze e l'area (ad esempio, identità, protezione dalle minacce e monitoraggio).  |
|[Consigli sull'architettura di sicurezza Microsoft](https://docs.microsoft.com/security/compass/compass)    | Se si è un architetto della sicurezza, vedere consigli sulla sicurezza organizzati dalla disciplina, incluse le operazioni di identità, di rete e di sicurezza.   |
|[Consigli sulle operazioni di sicurezza Microsoft](https://docs.microsoft.com/security/compass/security-operations-videos-and-decks)|Informazioni sui suggerimenti Microsoft per l'installazione e l'esecuzione di un centro operazioni di sicurezza (SOC, Security Operations Center) |
|[Formazione workshop Chief Information Security Officer (OICOL)](https://docs.microsoft.com/security/ciso-workshop/ciso-workshop)   | Se si è nuovi alla sicurezza cloud, non perdere questa serie di video.        |
|[docs.security.com/security](https://docs.microsoft.com/security/)    | Linee guida tecniche di Microsoft per la strategia di sicurezza e l'architettura.        |
| | |

Tutte queste risorse sono progettate per essere utilizzate come punto di partenza e adattate alle esigenze della propria organizzazione. 

