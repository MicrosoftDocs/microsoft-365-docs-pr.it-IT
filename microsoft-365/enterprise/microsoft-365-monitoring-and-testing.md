---
title: Microsoft 365 monitoraggio e testing del tenant perimetrale
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: In questo articolo, informazioni su come Microsoft monitora e verifica continuamente i confini dei tenant per Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: cd0aa3f88de3a8e22ef67283b20ecfae9959cb05
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690918"
---
# <a name="monitoring-and-testing-tenant-boundaries"></a>Monitoraggio e verifica dei limiti del tenant

Microsoft monitora continuamente e verifica in modo esplicito le debolezze e le vulnerabilità dei confini dei tenant, tra cui il monitoraggio per intrusioni, tentativi di violazione delle autorizzazioni e la mancanza di risorse. È inoltre possibile utilizzare più sistemi interni per monitorare continuamente l'utilizzo inappropriato delle risorse, che, se rilevato, attiva la limitazione integrata.

Microsoft 365 dispone di sistemi di monitoraggio interni che monitorano continuamente per qualsiasi errore e instradano il ripristino automatico quando viene rilevato un errore. I sistemi Microsoft 365 analizzano le deviazioni del comportamento del servizio e avviano processi di autoguarigione incorporati nel sistema. Microsoft 365 utilizza anche il monitoraggio esterno in cui il monitoraggio viene eseguito da più posizioni sia da servizi di terze parti attendibili (per la verifica indipendente di SLA) sia dai propri Data Center per generare avvisi. Per la diagnostica, sono presenti numerose funzionalità di registrazione, controllo e tracciabilità. La tracciabilità e il monitoraggio granulari consentono di isolare i problemi ed eseguire un'analisi delle cause radice rapida ed efficace.

Anche se Microsoft 365 ha azioni di ripristino automatizzate laddove possibile, gli ingegneri di Microsoft on-call sono disponibili 24x7 per analizzare tutte le escalation di sicurezza di gravità 1 e le recensioni post-mortem di ogni incidente di servizio contribuiscono all'apprendimento e al miglioramento continuo. Questo team include ingegneri del supporto tecnico, sviluppatori di prodotti, Program Manager, Product Manager e Senior Leadership. I professionisti di chiamata forniscono un backup tempestivo e spesso possono automatizzare le azioni di ripristino, in modo che la prossima volta che si verifica un evento possa essere risanata.

Microsoft esegue un'accurata revisione post-incidente ogni volta che si verifica un incidente di sicurezza di Microsoft 365 indipendentemente dall'entità dell'impatto. Una revisione post-incidente è costituita da un'analisi di ciò che è accaduto, da come è stato risposto e da come prevenire incidenti simili in futuro. Per la trasparenza e la responsabilità, si condivide la revisione post-incidente per eventuali incidenti di servizio importanti con clienti interessati. Per informazioni specifiche, vedere [Office 365 Security Incident Management](https://aka.ms/Office365SIM).

## <a name="assume-breach-methodology"></a>Assumere una metodologia di violazione

In base all'analisi dettagliata dei trend di sicurezza, Microsoft sostiene ed evidenzia la necessità di ulteriori investimenti in processi e tecnologie di sicurezza reattivi che si concentrano sul rilevamento e la risposta alle minacce emergenti, anziché solo alla prevenzione di tali minacce. A causa delle modifiche apportate al panorama delle minacce e all'analisi approfondita, Microsoft ha affinato la propria strategia di sicurezza oltre a impedire violazioni della sicurezza più attrezzate per gestire le violazioni quando si verificano – una strategia che considera gli eventi di sicurezza importanti non come una questione di se, ma quando.

Anche se le procedure di [violazione delle violazioni](https://www.microsoft.com/TrustCenter/Security/default.aspx) di Microsoft sono state eseguite da molti anni, molti clienti non sono a conoscenza del lavoro svolto dietro le quinte per indurire il cloud Microsoft. Presumere che la violazione sia una mentalità che guida gli investimenti di sicurezza, le decisioni di progettazione e le procedure di sicurezza operative. Se si presuppone che la violazione venga consentita, le relazioni tra le applicazioni, i servizi, le identità e le reti vengono considerate come insicure e già compromesse dall'interno e dall'esterno. Anche se la strategia di violazione del presupposto non è stata sostenuta da una violazione effettiva di qualsiasi servizio Microsoft Enterprise o cloud, è stato riconosciuto che molte organizzazioni, in tutto il settore, sono state violate nonostante tutti i tentativi di impedirlo. Se si impedisce che le violazioni siano una parte fondamentale delle operazioni di qualsiasi organizzazione, tali procedure devono essere continuamente verificate e potenziate per affrontare efficacemente gli avversari moderni e le minacce persistenti avanzate. Affinché qualsiasi organizzazione debba prepararsi per una violazione, deve innanzitutto creare e gestire procedure di risposta di sicurezza robuste, ripetibili e accuratamente testate.

Sebbene impediscano la violazione dei processi di sicurezza, ad esempio la modellazione delle minacce, le revisioni del codice e i test di sicurezza, sono molto utili nell'ambito del ciclo di vita [dello sviluppo della sicurezza](https://www.microsoft.com/securityengineering/sdl/), si presuppone che la violazione fornisca numerosi vantaggi che consentono di tenere conto della sicurezza complessiva esercitando e misurando le funzionalità reattive in caso

Microsoft ha deciso di eseguire questa operazione mediante esercizi di guerra in corso e test di penetrazione del sito dal vivo dei piani di risposta alla sicurezza con l'obiettivo di migliorare la capacità di rilevamento e di risposta. Microsoft simula regolarmente le violazioni del mondo reale, esegue il monitoraggio della sicurezza continua e pratica la gestione degli incidenti di sicurezza per convalidare e migliorare la sicurezza di Microsoft 365, Azure e altri servizi cloud Microsoft.

Microsoft esegue la propria strategia di sicurezza di violazione con due gruppi di base:
- Team rossi (utenti malintenzionati)
- Squadre blu (difensori)

Microsoft Azure e Microsoft 365 staff sono separati da Team rossi e squadre blu a tempo pieno.

Denominato "[red teaming](https://go.microsoft.com/fwlink/?linkid=518599)", l'approccio consiste nel testare i sistemi e le operazioni di Azure e Microsoft 365 utilizzando la stessa tattica, le tecniche e le procedure degli avversari reali, rispetto all'infrastruttura di produzione in tempo reale, senza la prescienza dei team di ingegneri o operativi. In questo modo vengono verificate le funzionalità di rilevamento e risposta della sicurezza di Microsoft, che consentono di identificare vulnerabilità di produzione, errori di configurazione, presupposti non validi e altri problemi di sicurezza in maniera controllata. Ogni violazione della squadra rossa è seguita da una divulgazione completa tra entrambe le squadre per identificare gli spazi vuoti, i risultati degli indirizzi e migliorare la risposta alla violazione.

**Nota**: nessun dato dei clienti viene deliberatamente mirato durante il testing del teaming o la penetrazione del sito Live. I test riguardano Microsoft 365 e l'infrastruttura e le piattaforme di Azure, nonché i tenant, le applicazioni e i dati di Microsoft. I tenant, le applicazioni e i contenuti dei clienti ospitati in Microsoft 365 o Azure non vengono mai mirati.

## <a name="red-teams"></a>Team rossi

La squadra rossa è un gruppo di personale a tempo pieno all'interno di Microsoft che si concentra sulla violazione dell'infrastruttura di Microsoft, della piattaforma e dei tenant e applicazioni di Microsoft. Essi sono l'avversario dedicato (un gruppo di hacker etici) che eseguono attacchi mirati e persistenti nei confronti dei servizi online (infrastruttura Microsoft, piattaforme e applicazioni, ma non le applicazioni o il contenuto dei clienti finali).

Il ruolo della squadra rossa è quello di attaccare e penetrare gli ambienti usando gli stessi passaggi di un avversario:
 
![Fasi di violazione](../media/office-365-isolation-breach-stages.png)

Tra le altre funzioni, i team rossi tentano di violare i limiti di isolamento dei tenant per individuare eventuali errori o lacune nel nostro progetto di isolamento.

## <a name="blue-teams"></a>Team blu

Il team blu è costituito da un set dedicato di risponditori o membri di sicurezza provenienti da tutte le organizzazioni di risposta, ingegneria e operazioni per gli incidenti di sicurezza. Indipendentemente dal loro make-up, sono indipendenti e operano separatamente dal team rosso. Il team blu segue i processi di sicurezza stabiliti e utilizza gli strumenti e le tecnologie più recenti per rilevare e rispondere agli attacchi e alla penetrazione. Proprio come gli attacchi del mondo reale, la squadra blu non sa quando o come si verificherà l'attacco del team rosso o quali metodi possono essere utilizzati. Il lavoro, se si tratta di un attacco di squadra rossa o di un assalto effettivo, consiste nel rilevare e rispondere a tutti gli incidenti di sicurezza. Per questo motivo, il team blu è continuamente in chiamata e deve reagire alle violazioni della squadra rossa nello stesso modo in cui si riferiscono a qualsiasi altra violazione.

Quando un avversario, ad esempio una squadra rossa, ha violato un ambiente, il team blu deve:

- Raccogliere le evidenze lasciate dall'avversario
- Rilevare la prova come indicazione del compromesso
- Avvisare il team di ingegneri e operativi appropriato
- Triage gli avvisi per determinare se garantiscono ulteriori indagini
- Raccogliere il contesto dall'ambiente per l'ambito della violazione
- Creare un piano di correzione per contenere o rimuovere l'avversario
- Eseguire il piano di correzione e riprendersi dalla violazione

Questi passaggi formano la risposta degli incidenti di sicurezza che corre parallela all'avversario, come illustrato di seguito:
 
![Fasi di risposta alla violazione](../media/office-365-isolation-breach-response-stages.png)

Le violazioni della squadra rossa consentono di esercitare la capacità del team blu di rilevare e rispondere agli attacchi del mondo reale end-to-end. La cosa più importante è che consente la risposta agli incidenti di sicurezza praticata prima di una vera e propria violazione. Inoltre, a causa delle violazioni della squadra rossa, la squadra blu migliora la loro consapevolezza situazionale che può essere utile quando si tratta di violazioni future (se dal team rosso o da un altro avversario). Nel corso del processo di rilevamento e di risposta, il team blu produce informazioni sull'azione e acquisisce visibilità nelle condizioni effettive degli ambienti in cui si sta tentando di difendere. Questa operazione viene eseguita spesso tramite l'analisi dei dati e la scientifica, eseguite dal team blu, quando rispondono agli attacchi dei team rossi e definendo indicatori di minaccia, ad esempio indicatori di compromesso. Analogamente a come la squadra rossa identifica gli spazi vuoti nella storia della sicurezza, i team blu identificano le lacune nella loro capacità di rilevare e rispondere. Inoltre, dal momento che il modello Red teams affronta gli attacchi del mondo reale, la squadra blu può essere valutata in modo accurato sulle loro capacità, o impossibilità, per gestire gli avversari decisi e persistenti. Infine, le violazioni alla squadra rossa misurano sia la preparazione che l'impatto della nostra risposta alla violazione.
