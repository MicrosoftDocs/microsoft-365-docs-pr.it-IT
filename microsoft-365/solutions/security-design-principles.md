---
title: Pianificazione delle risorse di Microsoft 365 Enterprise - Architettura della cybersecurity
description: Informazioni su come superare le sfide relative alla sicurezza nell'architettura Microsoft Enterprise di Kozeta Garrett, Cybersecurity Architect di Microsoft.
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
- M365solutions
ms.custom: seo-marvel-jun2020
f1.keywords: NOCSH
ms.openlocfilehash: 7b84094fecc1ddbd58bcdfca808df6585958a6dc
ms.sourcegitcommit: ddfb4f3e34deb733e8625e845e4dfd1fcc066ceb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/06/2021
ms.locfileid: "49771932"
---
# <a name="security-hurdles-you-can-sail-overone-architects-viewpoint"></a>Ostacoli alla sicurezza che è possibile sorreggiare: il punto di vista di un architetto

In questo articolo [Kozeta Garrett,](https://www.linkedin.com/in/kozeta-garrett-53013a6/)Cybersecurity Architect di Microsoft, descrive le principali sfide per la sicurezza che incontra nelle organizzazioni aziendali e consiglia gli approcci per affrontare questi ostacoli.

## <a name="about-the-author"></a>Informazioni sull'autore

![Kozeta Garrett photo](../media/solutions-architecture-center/kozeta-garrett-security.jpg)

Nel mio ruolo di Cloud Security Architect, ho collaborato con più organizzazioni per fornire indicazioni strategiche e tecniche incentrate sulla progettazione e l'implementazione dell'architettura di sicurezza per i clienti che esercitino la migrazione a Microsoft 365 e Azure, sviluppando soluzioni di sicurezza aziendali e contribuendo a trasformare l'architettura e la cultura della sicurezza per la resilienza aziendale. La mia esperienza include il rilevamento e la risposta a eventi imprevisti, l'analisi del malware, il test di penetrazione e la raccomandazione di miglioramenti alla sicurezza e alla difesa IT. Sono molto abilissimo a guidare le trasformazioni che comportano la sicurezza come elemento di supporto per l'azienda, inclusi gli sforzi di modernizzazione.

È stato molto soddisfacente vedere come le organizzazioni che hanno adottato una mentalità di modernizzazione della sicurezza negli ultimi due anni siano in una posizione ideale che consente loro di continuare a operare in remoto in modo sicuro, nonostante la recente situazione coVID-19. Purtroppo, queste circostanze sono servite anche come una chiamata di riattivazione per alcuni clienti, che non erano pronti per questa esigenza immediata. Molte organizzazioni si stanno rendendo conto di doversi modernizzare rapidamente, ritirare i debiti accumulati per la sicurezza IT e migliorare la loro sicurezza durante la notte in modo da poter operare in queste circostanze estremamente insolite.

La buona notizia è che Microsoft ha curato alcune grandi risorse per aiutare le organizzazioni a migliorare rapidamente il loro livello di sicurezza. Oltre a queste risorse, vorrei condividere le principali sfide che ho riscontrato con i clienti ogni giorno, con l'intuito di poter affrontare questi ostacoli.

Attualmente vivo nella California settentrionale, vicino alla capitale del nostro paese, Washington DC. Mi piace molto ogni forma di attività ed esercizio all'aperto, come la corsa, la gita in cyclette, l'attività fisica e l'attività fisica. Per contrastare questi eventi, mi piace anche la cucina, il buongustaio e i viaggi.

## <a name="partner-with-the-security-team-from-the-start-of-cloud-adoption"></a>Collaborare con il team di sicurezza dall'inizio dell'adozione del cloud

Per iniziare, non posso sottolineare quanto sia importante che i team dell'organizzazione si coordinano fin dall'inizio. I team di sicurezza devono essere adottati come partner critici nelle fasi iniziali dell'adozione e della progettazione del cloud. Ciò significa ottenere l'onboarding dei team di sicurezza per l'adozione del cloud, non solo per le funzionalità aggiunte all'azienda (ad esempio, un'ottima esperienza utente da dispositivi mobili sicuri, applicazioni con funzionalità complete o la creazione di valore per i dati aziendali oltre le applicazioni di posta elettronica e produttività con funzionalità limitate), ma anche per sfruttare le funzionalità di archiviazione, IA e analisi di elaborazione che consentono di risolvere nuove e vecchie sfide per la sicurezza. I team di sicurezza devono essere inclusi nella gestione di tutti gli aspetti di questo cambiamento, incluse le persone (cultura), i processi (formazione) e la tecnologia per avere successo. Significa anche investire nella modernizzazione e nel miglioramento continuo del Security Operations Center (SOC). Collaborare per allineare la strategia di sicurezza alla strategia aziendale e alle tendenze dell'ambiente per garantire che la trasformazione digitale sia eseguita in modo sicuro. Quando questa operazione viene eseguita in modo adeguato, le organizzazioni sviluppano la capacità di adattarsi più velocemente alle modifiche, incluse le modifiche all'azienda, all'IT e alla sicurezza.

Il punto in cui i clienti si inciampano maggiormente negli ostacoli è quando non esiste una vera partnership tra le operazioni e i team SOC. Anche se il team operativo è sotto pressione e ha l'incarico di rispettare scadenze rigide per l'adozione del cloud, i team di sicurezza non sono sempre inclusi nelle prime fasi del processo di revisione e pianificazione di una strategia di sicurezza completa. Ciò implica l'integrazione di componenti cloud e componenti diversi in modalità in-prem. Questa mancanza di partnership si fa ancora più difficile per i diversi team che sembrano lavorare in silos per implementare controlli per i propri componenti specifici, determinando una maggiore complessità di implementazione, risoluzione dei problemi e integrazione.

I clienti che scavalcano questi ostacoli hanno buone relazioni tra i team di gestione delle operazioni e della governance e i team di gestione della sicurezza e dei rischi per il ripristino della strategia di sicurezza e dei requisiti per la protezione dei carichi di lavoro cloud ibridi. Si concentrano sugli obiettivi e i risultati di sicurezza definitivi, ovvero la protezione dei dati e la disponibilità di sistemi e servizi in conformità ai requisiti di governance, rischi e conformità della sicurezza informatica. Queste organizzazioni sviluppano relazioni iniziali tra il team operativo e di governance e SOC, che è fondamentale per l'approccio di progettazione della sicurezza e massimizza il valore dei propri investimenti.

## <a name="build-a-modern-identity-based-security-perimeter"></a>Creare un perimetro di sicurezza moderno (basato sull'identità)

Successivamente, adottare un approccio di architettura Zero Trust. Questo inizia con la creazione di un perimetro di sicurezza moderno basato sull'identità. Progettare l'architettura di sicurezza in cui ogni tentativo di accesso, in modalità in ambiente o cloud, viene considerato come non attendibile fino a quando non viene verificato: "non considerare mai attendibile, verificare sempre". Questo approccio di progettazione non solo aumenta la sicurezza e la produttività, ma consente anche agli utenti di lavorare ovunque con qualsiasi tipo di dispositivo. I sofisticati controlli cloud inclusi in Microsoft 365 consentono di proteggere le identità degli utenti controllando l'accesso alle risorse preziose in base al livello di rischio degli utenti.

Per una configurazione consigliata, vedere [Configurazioni di identità e accesso ai dispositivi.](../security/office-365-security/microsoft-365-policies-configurations.md)

## <a name="transition-security-controls-to-the-cloud"></a>Eseguire la transizione dei controlli di sicurezza al cloud

Molti team di sicurezza usano ancora le procedure consigliate per la sicurezza tradizionali create per un ambiente locale, tra cui la gestione di una "sicurezza perimetrale di rete" e il tentativo di "forzare" gli strumenti e i controlli di sicurezza locali per le soluzioni cloud. Questi controlli non sono stati progettati per il cloud, sono inefficaci e impediscono l'adozione di funzionalità cloud moderne. I processi e gli strumenti che funzionano per un approccio alla sicurezza perimetrale di rete si sono rivelati inefficienti, ostruttivi per le funzionalità cloud e non consentono di sfruttare le funzionalità di sicurezza moderne e automatizzate.

Per risolvere questo problema, è possibile passare dalle strategie di difesa alla protezione gestita dal cloud, all'analisi e alla correzione automatizzate, al test automatico della penna, a Defender per Office 365 e all'analisi degli incidenti. I clienti che utilizzano soluzioni di gestione dei dispositivi moderne hanno implementato la gestione automatizzata, l'applicazione di patch standardizzata, l'antivirus, l'applicazione dei criteri e la protezione delle applicazioni in tutti i dispositivi (smartphone, personal computer, portatile o tablet). Ciò elimina la necessità di una VPN, Microsoft System Center Configuration Manager (SCCM) e criteri di gruppo di Active Directory. Questo, in combinazione con i criteri di accesso condizionale, offre un controllo e una visibilità potenti, nonché un accesso semplificato alle risorse indipendentemente dalla posizione da cui operano gli utenti.

## <a name="strive-for-best-together-security-tools"></a>Cercare strumenti di sicurezza "migliori insieme"

Un altro ostacolo che i clienti sorrendono è l'approccio migliore agli strumenti di sicurezza. L'applicazione continua di più livelli di soluzioni di punta per soddisfare le esigenze di sicurezza emergenti causa la scomposizione della sicurezza aziendale. Anche con le migliori intenzioni, gli strumenti nella maggior parte degli ambienti non si integrano perché diventano troppo costosi e complessi. Ciò, a sua volta, crea lacune nella visibilità, in quanto esistono più avvisi da saperne di più di quanto il team possa gestire. Anche la riqualificazione del team SecOps su nuovi strumenti diventa una sfida costante.

L'approccio "semplice è migliore" funziona anche per la sicurezza. Invece di scegliere gli strumenti migliori, è possibile aggirare questo ostacolo adottando una strategia "migliore insieme" con strumenti che funzionano insieme per impostazione predefinita. Le funzionalità di sicurezza Microsoft proteggono l'intera organizzazione con una protezione integrata dalle minacce che si estende su applicazioni, utenti e cloud. L'integrazione consente a un'organizzazione di essere più resiliente e ridurre i rischi, includendo gli utenti malintenzionati all'ingresso e la correzione rapida degli attacchi.

## <a name="balance-security-with-functionality"></a>Bilanciare la sicurezza con le funzionalità

Poiché provengono da un lungo background e da un'esperienza di cybersecurity, tendono a preferire iniziare con la configurazione più sicura e a consentire alle organizzazioni di rilassare le configurazioni di sicurezza in base alle proprie esigenze operative e di sicurezza. Tuttavia, questo può arrivare a un prezzo elevato di funzionalità perse e di scarsa esperienza utente. Come hanno appreso molte organizzazioni, se la sicurezza è troppo difficile per gli utenti, troveranno un modo per aggirare l'utente, incluso l'uso di servizi cloud non gestiti. Per quanto sia difficile da accettare, mi sono reso conto che il delicato equilibrio funzionalità-sicurezza deve essere raggiunto.

Le organizzazioni che si rendono conto che gli utenti fanno tutto il necessario per ottenere il loro lavoro riconoscono che la "sfida Shadow IT" non vale la pena combattere. Riconoscono che i dipendenti IT sono i principali autori del reato quando si tratta di shadow IT e l'uso di applicazioni SaaS non approvate per il proprio lavoro. Hanno spostato la loro strategia per incoraggiarne l'uso (anziché eliminare) e concentrarsi sulla mitigazione dell'esposizione ai rischi che potrebbe creare. I team di sicurezza di queste organizzazioni non insistono sul fatto che tutto venga bloccato, registrato e inviato tramite un proxy inverso o una VPN. Piuttosto, questi team di sicurezza raddoppiano gli sforzi per proteggere i dati importanti e sensibili dall'esposizione alle parti sbagliate o alle app dannose. Lavorano per proteggere l'integrità dei dati. Stanno facendo uso completo di funzionalità di protezione delle informazioni cloud più avanzate, tra cui crittografia, autenticazione a più fattori sicura, rischi e conformità automatizzati e funzionalità cloud App Security Broker (CASB) consentendo e incoraggiando anche la condivisione protetta tra più piattaforme. Stanno trasformando l'IT shadow in creatività, produttività e collaborazione ispiranti, che consentono all'azienda di rimanere all'avanguardia.

## <a name="adopt-a-methodical-approach"></a>Adottare un approccio metodico

La maggior parte delle sfide che ho riscontrato nell'implementazione della sicurezza cloud in organizzazioni diverse, indipendentemente dal settore, sono state molto simili. Prima di tutto, mentre è disponibile una grande documentazione su funzionalità e funzionalità specifiche, esiste un livello di confusione a livello di organizzazione su cosa si applica a loro, dove le funzionalità di sicurezza si sovrappongono e come devono essere integrate. Esiste inoltre un livello di incertezza sulle funzionalità di sicurezza preconfigurato e che richiedono la configurazione da parte dell'organizzazione. Inoltre, i team SOC purtroppo non hanno avuto l'esposizione completa, la formazione o l'allocazione del budget necessaria per prepararsi alla rapida adozione del cloud e alla trasformazione digitale già in corso nelle loro organizzazioni.

Per eliminare questi ostacoli, Microsoft ha curato diverse risorse progettate per aiutare l'utente a adottare un approccio metodico alla strategia e all'implementazione della sicurezza.

|Risorsa   |Ulteriori informazioni  |
|---------|---------|
|[Principali attività per i team di sicurezza per supportare il lavoro da casa](../security/top-security-tasks-for-remote-work.md)      | Se improvvisamente si supporta una forza lavoro a casa, questo articolo consente di aumentare rapidamente la sicurezza. Include le principali attività consigliate in base al piano di gestione delle licenze.    |
|[Responsabili delle decisioni relative alla sicurezza per le aziende di Microsoft 365](../security/Microsoft-365-security-for-bdm.md)    | Quando si ha tempo per un piano più completo, questo articolo include suggerimenti che si estendono su Microsoft 365, in ordine di priorità in base alla superficie di attacco. Viene fornito anche con un foglio di calcolo che puoi usare per ordinare licenze e aree (ad esempio identità, protezione dalle minacce e monitoraggio).  |
|[Consigli sull'architettura di sicurezza Microsoft](https://docs.microsoft.com/security/compass/compass)    | Se si è un architetto della sicurezza, assicurarsi di vedere i consigli sulla sicurezza organizzati in base alla disciplina, incluse le operazioni di identità, rete e sicurezza.   |
|[Suggerimenti per Microsoft Security Operations](https://docs.microsoft.com/security/compass/security-operations-videos-and-decks)|Informazioni sui consigli di Microsoft per la configurazione e l'esecuzione di un Centro operativo per la sicurezza (SOC) |
|[Workshop di formazione del Chief Information Security Officer (CISO)](https://docs.microsoft.com/security/ciso-workshop/ciso-workshop)   | Se non si ha di nuovo la sicurezza cloud, non perdere questa serie di video.        |
|[docs.security.com/security](https://docs.microsoft.com/security/)    | Linee guida tecniche di Microsoft per la strategia e l'architettura di sicurezza.        |
| | |

Tutte queste risorse sono progettate per essere utilizzate come punto di partenza e adattate alle esigenze dell'organizzazione.
