---
title: Pianificazione delle risorse di Microsoft 365 Enterprise - Architettura di cybersecurity
description: Informazioni su come superare le sfide di sicurezza nell'architettura Microsoft Enterprise da Kozeta Garrett, Cybersecurity Architect di Microsoft.
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
ms.openlocfilehash: 7cd9098766024093a0b9fa2d6e95131bf13d09df
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51052483"
---
# <a name="security-hurdles-you-can-sail-overone-architects-viewpoint"></a>Ostacoli di sicurezza su cui è possibile navigare: il punto di vista di un architetto

In questo [articolo, Kozeta Garrett,](https://www.linkedin.com/in/kozeta-garrett-53013a6/)Cybersecurity Architect di Microsoft, descrive le principali sfide alla sicurezza che incontra nelle organizzazioni aziendali e consiglia gli approcci per affrontare questi ostacoli.

## <a name="about-the-author"></a>Informazioni sull'autore

![Kozeta Garrett photo](../media/solutions-architecture-center/kozeta-garrett-security.jpg)

Nel mio ruolo di Cloud Security Architect, ho lavorato con più organizzazioni per fornire indicazioni strategiche e tecniche incentrate sulla progettazione e l'implementazione dell'architettura di sicurezza per i clienti che migrano a Microsoft 365 e Azure, sviluppando soluzioni di sicurezza aziendali e contribuendo a trasformare l'architettura di sicurezza e la cultura per la resilienza aziendale. La mia esperienza include il rilevamento e la risposta degli incidenti, l'analisi del malware, i test di penetrazione e la raccomandazione di miglioramenti alla sicurezza IT e alla postura di difesa. Sono molto abilissimo a guidare le trasformazioni che comportano la sicurezza come un abilitazione per l'azienda, inclusi gli sforzi di modernizzazione.

È stato molto soddisfacente vedere come le organizzazioni che hanno adottato una mentalità di modernizzazione della sicurezza negli ultimi due anni siano in una posizione ideale che consente loro di continuare a operare in remoto in modo sicuro, nonostante la recente situazione COVID-19. Purtroppo, queste circostanze sono servite anche come una sveglia per alcuni clienti, che non erano pronti per questa necessità immediata. Molte organizzazioni si stanno rendendo conto che devono modernizzare rapidamente, ritirare il debito di sicurezza IT accumulato e migliorare la loro posizione di sicurezza durante la notte in modo che possano operare in queste circostanze estremamente insolite.

La buona notizia è che Microsoft ha curato alcune grandi risorse per aiutare le organizzazioni a migliorare rapidamente la loro sicurezza. Oltre a queste risorse, vorrei condividere le principali sfide che ho incontrato quotidianamente con i clienti nella speranza di poter navigare su questi ostacoli.

Attualmente vivo nella Virginia settentrionale, vicino alla capitale del nostro paese, Washington DC. Amo quasi ogni forma di attività all'aperto e di esercizio fisico, come la corsa, la corsa in bicicletta, l'attività a piedi e il nuoto. Per contrastare questi problemi, mi piace tanto la cucina, il cibo da buongustaio e i viaggi.

## <a name="partner-with-the-security-team-from-the-start-of-cloud-adoption"></a>Collaborare con il team di sicurezza fin dall'inizio dell'adozione del cloud

Per iniziare, non posso sottolineare abbastanza quanto sia importante per i team dell'organizzazione coordinarsi fin dall'inizio. I team di sicurezza devono essere adottati come partner critici nelle prime fasi dell'adozione e della progettazione del cloud. Ciò significa far eseguire l'onboarding dei team di sicurezza per difendere l'adozione del cloud, non solo per le funzionalità aggiunte all'azienda (ad esempio, un'esperienza utente ottimale da dispositivi mobili sicuri, applicazioni con funzionalità complete o la creazione di valore sui dati aziendali oltre le applicazioni di posta elettronica e produttività a funzionalità limitate), ma anche per sfruttare le funzionalità di archiviazione, IA e analisi di calcolo che consentono di risolvere le nuove e vecchie sfide di sicurezza. I team di sicurezza devono essere inclusi nella gestione di tutti gli aspetti di questo cambiamento, incluse le persone (cultura), i processi (formazione) e la tecnologia per avere successo. Significa anche investire nella modernizzazione e nel miglioramento continuo del Security Operations Center (SOC). Collaborare per allineare la strategia di sicurezza alla strategia aziendale e alle tendenze dell'ambiente per garantire che la trasformazione digitale sia eseguita in modo sicuro. Quando questa operazione viene eseguita in modo adeguato, le organizzazioni sviluppano la capacità di adattarsi più rapidamente alle modifiche, incluse le modifiche apportate all'azienda, all'IT e alla sicurezza.

Dove vedo i clienti che inciampano di più negli ostacoli è quando non c'è una vera partnership tra le operazioni e i team SOC. Mentre il team operativo è sotto pressione e ha il compito di rispettare scadenze rigide per adottare il cloud, i team di sicurezza non sono sempre inclusi nelle prime fasi del processo per rivedere e pianificare una strategia di sicurezza completa. Ciò implica l'integrazione di diversi componenti cloud e componenti in ambiente prem. Questa mancanza di partnership si aggiunge a team diversi che sembrano lavorare in silos per implementare controlli per i propri componenti specifici, determinando una maggiore complessità di implementazione, risoluzione dei problemi e integrazione.

I clienti che navigano su questi ostacoli hanno buone partnership tra i team operations e governance e i team di gestione della sicurezza e dei rischi per modificare la strategia di sicurezza e i requisiti per la protezione dei carichi di lavoro cloud ibridi. Si concentrano sugli obiettivi e i risultati di sicurezza più importanti, ovvero la protezione dei dati e la disponibilità di sistemi e servizi in conformità ai requisiti di governance, rischi e conformità della sicurezza informatica. Queste organizzazioni sviluppano partnership iniziali tra il team operations e governance e SOC, che è fondamentale per l'approccio alla progettazione della sicurezza e massimizza il valore dei propri investimenti.

## <a name="build-a-modern-identity-based-security-perimeter"></a>Creare un perimetro di sicurezza moderno (basato sull'identità)

Successivamente, adottare un approccio all'architettura Zero Trust. Questo inizia con la creazione di un perimetro di sicurezza moderno basato sull'identità. Progettare l'architettura di sicurezza in cui ogni tentativo di accesso, sia sul posto che nel cloud, viene considerato non attendibile finché non viene verificato: "Non considerare mai attendibile, verifica sempre". Questo approccio di progettazione non solo aumenta la sicurezza e la produttività, ma consente anche agli utenti di lavorare ovunque con qualsiasi tipo di dispositivo. I sofisticati controlli cloud inclusi in Microsoft 365 consentono di proteggere le identità degli utenti controllando l'accesso a risorse preziose in base al livello di rischio degli utenti.

Per una configurazione consigliata, vedere [Configurazioni di identità e accesso ai dispositivi](../security/defender-365-security/microsoft-365-policies-configurations.md).

## <a name="transition-security-controls-to-the-cloud"></a>Transizione dei controlli di sicurezza nel cloud

Molti team di sicurezza utilizzano ancora le procedure consigliate di sicurezza tradizionali create per un mondo tutto locale, tra cui la gestione di una "sicurezza perimetrale di rete" e il tentativo di "forzare" gli strumenti e i controlli di sicurezza locali per le soluzioni cloud. Tali controlli non sono stati progettati per il cloud, sono inefficaci e ostacolano l'adozione di funzionalità cloud moderne. I processi e gli strumenti che funzionano per un approccio alla sicurezza perimetrale di rete si sono dimostrati inefficienti, ostruttivi alle funzionalità cloud e non consentono di sfruttare le funzionalità di sicurezza moderne e automatizzate.

È possibile risolvere questo ostacolo spostando le strategie di difesa in protezione gestita dal cloud, analisi e correzione automatizzate, test automatizzati della penna, Defender per Office 365 e analisi degli incidenti. I clienti che utilizzano soluzioni di gestione dei dispositivi moderne hanno implementato la gestione automatizzata, l'applicazione di patch standardizzata, l'antivirus, l'applicazione dei criteri e la protezione delle applicazioni in tutti i dispositivi (smartphone, personal computer, laptop o tablet). In questo modo si elimina la necessità di una VPN, Microsoft System Center Configuration Manager (SCCM) e criteri di gruppo di Active Directory. Questo, insieme ai criteri di accesso condizionale, offre un controllo e una visibilità potenti, nonché un accesso semplificato alle risorse indipendentemente dalla posizione da cui operano gli utenti.

## <a name="strive-for-best-together-security-tools"></a>Cercare strumenti di sicurezza "migliori insieme"

Un altro ostacolo che vedo i clienti inciampare è l'approccio "best of breed" agli strumenti di sicurezza. L'applicazione continua di soluzioni di punta "best of breed" per soddisfare le esigenze di sicurezza emergenti fa sì che la sicurezza aziendale si interrompa. Anche con le migliori intenzioni, gli strumenti nella maggior parte degli ambienti non vengono integrati perché diventa troppo costoso e complesso. Questo, a sua volta, crea lacune di visibilità in quanto esistono più avvisi per la triage di quanto il team possa gestire. Anche la riqualificazione del team SecOps su nuovi strumenti diventa una sfida costante.

L'approccio "semplice è migliore" funziona anche per la sicurezza. Invece di scegliere gli strumenti "migliori della generazione", è possibile aggirare questo ostacolo adottando una strategia "migliore insieme" con strumenti che funzionano insieme per impostazione predefinita. Le funzionalità di sicurezza Microsoft proteggono l'intera organizzazione con una protezione dalle minacce integrata che si estende su applicazioni, utenti e cloud. L'integrazione consente a un'organizzazione di essere più resiliente e ridurre i rischi, con la possibilità di contenere gli utenti malintenzionati all'ingresso e di correggere rapidamente gli attacchi.

## <a name="balance-security-with-functionality"></a>Bilanciare la sicurezza con le funzionalità

Poiché provengono da un lungo background ed esperienza di cybersecurity, tendo a preferire iniziare con la configurazione più sicura e consentendo alle organizzazioni di rilassare le configurazioni di sicurezza in base alle loro esigenze operative e di sicurezza. Tuttavia, questo può avere un prezzo elevato per la perdita di funzionalità e la scarsa esperienza utente. Come molte organizzazioni hanno appreso, se la sicurezza è troppo difficile per gli utenti, troveranno un modo per aggirare l'utente, incluso l'utilizzo di servizi cloud non gestiti. Per quanto sia difficile da accettare, mi sono reso conto che il delicato equilibrio funzionalità-sicurezza deve essere raggiunto.

Le organizzazioni che si rendono conto che gli utenti fanno tutto il necessario per ottenere il loro lavoro riconoscono che la "shadow it battle" non vale la pena combattere. Riconoscono che i dipendenti IT sono i principali trasgressori per quanto riguarda l'IT shadow e l'uso di applicazioni SaaS non approvate per il proprio lavoro. Hanno spostato la loro strategia per incoraggiarne l'uso (invece di sopprimere) e concentrarsi sulla mitigazione dell'esposizione ai rischi che potrebbe creare. I team di sicurezza di queste organizzazioni non insistono sul fatto che tutto venga bloccato, registrato e inviato tramite un proxy inverso o una VPN. Piuttosto, questi team di sicurezza raddoppiano gli sforzi per proteggere i dati importanti e sensibili dall'esposizione a parti sbagliate o app dannose. Funzionano per proteggere l'integrità dei dati. Stanno facendo uso completo di funzionalità di protezione delle informazioni cloud più avanzate, tra cui crittografia, autenticazione a più fattori sicura, rischi e conformità automatizzati e funzionalità casB (Cloud App Security Broker), consentendo e incoraggiando anche la condivisione protetta tra più piattaforme. Stanno trasformando l'IT shadow in una creatività, una produttività e una collaborazione stimolanti, che consente all'azienda di rimanere all'avanguardia.

## <a name="adopt-a-methodical-approach"></a>Adottare un approccio metodico

La maggior parte delle sfide che ho riscontrato nell'implementazione della sicurezza cloud in organizzazioni diverse, indipendentemente dal settore, sono state molto simili. Prima di tutto, sebbene sia disponibile una grande documentazione su funzionalità e funzionalità specifiche, esiste un livello di confusione a livello di organizzazione su cosa si applica a loro, dove si sovrappongono le funzionalità di sicurezza e su come devono essere integrate le funzionalità. Esiste anche un livello di incertezza sulle funzionalità di sicurezza preconfigurato e che richiedono la configurazione da parte dell'organizzazione. Inoltre, i team SOC purtroppo non hanno avuto l'esposizione completa, la formazione o l'allocazione del budget necessaria per preparare la rapida adozione del cloud e la trasformazione digitale già in corso.

Per aiutarti a eliminare questi ostacoli, Microsoft ha curato diverse risorse progettate per aiutarti a adottare un approccio metodico alla strategia e all'implementazione della sicurezza.

|Risorsa   |Ulteriori informazioni  |
|---------|---------|
|[Principali attività per i team di sicurezza per supportare il lavoro da casa](../security/top-security-tasks-for-remote-work.md)      | Se ti trovi improvvisamente a supportare una forza lavoro per lo più a casa, questo articolo ti aiuta a migliorare rapidamente la sicurezza. Include le principali attività consigliate in base al piano di gestione delle licenze.    |
|[Microsoft 365 Security for Business Decisions Makers](../security/Microsoft-365-security-for-bdm.md)    | Quando si ha tempo per un piano più completo, questo articolo include suggerimenti che si estendono su Microsoft 365, in base alla priorità in base alla superficie di attacco. Viene fornito anche con un foglio di calcolo che puoi usare per ordinare le licenze e l'area (ad esempio identità, protezione dalle minacce e monitoraggio).  |
|[Consigli sull'architettura di sicurezza Microsoft](/security/compass/compass)    | Se si è un architetto della sicurezza, assicurarsi di vedere i consigli sulla sicurezza organizzati in base alla disciplina, incluse le operazioni di identità, rete e sicurezza.   |
|[Suggerimenti per Microsoft Security Operations](/security/compass/security-operations-videos-and-decks)|Informazioni sui suggerimenti di Microsoft per la configurazione e l'esecuzione di un Centro operativo per la sicurezza (SOC) |
|[Formazione del Chief Information Security Officer (CISO)](/security/ciso-workshop/ciso-workshop)   | Se non si ha di nuovo a che fare con la sicurezza cloud, non perdere questa serie di video.        |
|[docs.security.com/security](/security/)    | Linee guida tecniche di Microsoft per la strategia e l'architettura di sicurezza.        |
| | |

Tutte queste risorse sono progettate per essere utilizzate come punto di partenza e adattate alle esigenze dell'organizzazione.