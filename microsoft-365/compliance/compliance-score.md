---
title: Punteggio di conformità Microsoft
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Il Punteggio di conformità di Microsoft aiuta le organizzazioni a semplificare e automatizzare le valutazioni dei rischi e suggerisce azioni consigliate per aiutare a gestire i rischi.
ms.openlocfilehash: 507ff021095dfc0b18cffb6db313009c22ad2693
ms.sourcegitcommit: eb3c7f473e8fe62624f52c9bb38dcd6a96fa58a3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "44046274"
---
# <a name="microsoft-compliance-score-preview"></a>Punteggio di conformità Microsoft (anteprima)

Il [Punteggio di conformità di Microsoft](https://compliance.microsoft.com/compliancescore) contribuisce a semplificare il modo in cui gestire la conformità e ridurre i rischi di conformità tramite un'esperienza facile da usare. Il Punteggio di conformità è disponibile per l'anteprima pubblica nel [centro conformità di Microsoft 365](microsoft-365-compliance-center.md).

**In questo articolo:** Leggere questo articolo per comprendere quale punteggio di conformità è e come configurarlo per l'organizzazione.

Informazioni **sugli aggiornamenti:** Sono stati pubblicati diversi aggiornamenti nella versione di aprile 2020. Visitare le [Note](compliance-score-release-notes.md) sulla versione del Punteggio di conformità per visualizzare i problemi nuovi e noti con la versione di anteprima del Punteggio di conformità.

## <a name="what-is-compliance-score"></a>Che cos'è il Punteggio di conformità

Microsoft Compliance Score è una funzionalità di anteprima del centro conformità di Microsoft 365 che consente di comprendere la posizione di conformità dell'organizzazione. Calcola un punteggio basato sui rischi misurando lo stato di avanzamento del processo di completamento delle azioni che consentono di ridurre i rischi per la protezione dei dati e gli standard normativi.

È possibile utilizzare il Punteggio di conformità come strumento per monitorare tutte le valutazioni dei rischi. Offre funzionalità di flusso di lavoro che consentono di completare efficacemente le valutazioni dei rischi tramite uno strumento comune.

Se attualmente si utilizza [Compliance Manager](compliance-manager-overview.md), si noterà che il Punteggio di conformità è ora una funzionalità autonoma con una progettazione più semplice e più facile da usare per gestire più facilmente la conformità. 

La pagina principale del Punteggio di conformità è il dashboard personalizzato. Mostra il tuo punteggio corrente, ti aiuta a vedere cosa ha bisogno di attenzioni e ti guida alle azioni per migliorare il tuo punteggio. Il dashboard del Punteggio di conformità avrà l'aspetto seguente:

![Punteggio di conformità-dashboard](../media/compliance-score-dashboard.png "Dashboard del Punteggio di conformità")

### <a name="simplified-compliance-management"></a>Gestione della conformità semplificata

Il Punteggio di conformità consente di semplificare la gestione della conformità fornendo:

- **Valutazioni continue**: consente di analizzare automaticamente gli ambienti Microsoft 365 per rilevare e monitorare l'efficacia dei controlli di protezione dei dati nel sistema
- **Azioni consigliate**: fornisce consigli e istruzioni dettagliate su come implementare i controlli per massimizzare il Punteggio
-  **Mapping di controllo incorporato**: consente di rimanere aggiornati con il paesaggio di conformità in evoluzione fornendo un Framework di controllo comune incorporato.

> [!IMPORTANT]
> I consigli di Compliance Manager e Punteggio di conformità non devono essere interpretati come una garanzia di conformità. Spetta a te valutare e convalidare l'efficacia dei controlli del cliente per il tuo ambiente normativo. Questi servizi sono attualmente in anteprima e sono soggetti ai termini e alle condizioni nelle condizioni dei [servizi online](https://go.microsoft.com/fwlink/?linkid=2108910). Vedere anche [linee guida per la gestione delle licenze di Microsoft 365 per sicurezza e conformità](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).

## <a name="relationship-to-compliance-manager"></a>Relazione con Compliance Manager

Considerare la conformità score come versione semplificata di Compliance Manager. Mentre i due esistono come strumenti distinti ma integrati, il Punteggio di conformità rende più facile monitorare la postura di conformità globale e adottare misure per migliorarla.

Punteggio di conformità condivide lo stesso backend con Compliance Manager, quindi qualsiasi dato che potrebbe essere già presente in Compliance Manager mostrerà il Punteggio di conformità.

Alcune funzionalità rimangono solo in Compliance Manager durante l'anteprima pubblica, ad esempio la gestione delle valutazioni e la creazione di modelli. Si consiglia di iniziare tutte le attività di gestione della conformità in Score Compliance. Quando si accede a funzioni gestite da Compliance Manager, si verrà guidati a tale strumento. Per questo motivo, alcuni di questi documenti indirizzano gli argomenti di Compliance Manager.

Ulteriori informazioni sulla relazione tra Score compliance e Compliance Manager nelle [Note sulla versione del Punteggio di conformità](compliance-score-release-notes.md).

## <a name="understanding-your-score"></a>Informazioni sul Punteggio

Punteggio di conformità fornisce un punteggio iniziale basato sulla linea di base per la protezione dei dati di Microsoft 365. Questa baseline è un set di controlli che include norme e standard di settore comuni. Anche se questo punteggio è un buon punto di partenza per valutare la postura di conformità, il Punteggio di conformità diventa più potente dopo aver aggiunto valutazioni più rilevanti per la propria organizzazione.

Ad esempio, se l'organizzazione appartiene al settore dei servizi finanziari, potrebbe essere necessario aggiungere la valutazione di FFIEC. Se l'organizzazione appartiene all'industria del settore sanitario, è possibile aggiungere la valutazione HIPAA/HITECH. Informazioni su come [aggiungere valutazioni in Compliance Manager](working-with-compliance-manager.md#assessments).

Per ulteriori informazioni [, vedere Calcolo del Punteggio di conformità e monitoraggio continuo](compliance-score-methodology.md).


## <a name="key-components-controls-assessments-templates-groups"></a>Componenti principali: controlli, valutazioni, modelli, gruppi

Il Punteggio di conformità utilizza diversi componenti per facilitare la gestione delle attività di conformità. Quando si utilizza il Punteggio di conformità per assegnare, testare e monitorare le attività di conformità, è utile avere una conoscenza di base dei componenti principali: controlli, valutazioni, modelli e gruppi.

### <a name="controls"></a>Controlli

Un controllo definisce come valutare e gestire la configurazione del sistema, il processo organizzativo e gli utenti responsabili della riunione di un requisito specifico di un criterio di regolamentazione, standard o interno.

Il Punteggio di conformità tiene traccia di due tipi di controlli:

1. **Controlli gestiti da Microsoft**: controlli per i servizi cloud Microsoft, che Microsoft è responsabile dell'implementazione
2. **Controlli gestiti dal cliente**: controlli gestiti dall'organizzazione, che sono responsabili dell'implementazione
 
### <a name="assessments"></a>Valutazioni

Una valutazione è una valutazione di un modello che avvia il processo di punteggio per la propria organizzazione. Le valutazioni raggruppano le azioni necessarie per soddisfare i requisiti di una norma, di una normativa o di una legge. Ad esempio, si può avere una valutazione che, quando si completano tutte le azioni all'interno di esso, porta le impostazioni di Office 365 in linea con i requisiti ISO 27001.

Punteggio di conformità fornisce alla propria organizzazione una valutazione iniziale basata sulla linea di base per la protezione dei dati di Microsoft 365. Tale valutazione è una raccomandazione per la riduzione dei rischi di protezione e conformità dei dati (ulteriori[informazioni](compliance-score-methodology.md#initial-score-based-on-microsoft-365-data-protection-baseline)).

Le valutazioni hanno diversi componenti:

- **Servizi nell'ambito**: l'insieme specifico di servizi Microsoft applicabile alla valutazione
- **Controlli gestiti da Microsoft**: controlli che Microsoft ha implementato e testato
- **Controlli gestiti dal cliente**: controlli da gestire
- **Punteggio di valutazione**: la percentuale dei punti ottenuti completando le azioni all'interno di tale valutazione

> [!NOTE]
> Punteggio di conformità consente di visualizzare le valutazioni e la modalità di factoring nel punteggio generale. Tuttavia, durante l'anteprima pubblica si verrà indirizzati a Compliance Manager per gestire le proprie valutazioni.

Visualizzare istruzioni dettagliate per la [gestione delle valutazioni in Compliance Manager](working-with-compliance-manager.md#assessments).

### <a name="templates"></a>Modelli

Il Punteggio di conformità fornisce modelli preconfigurati per le valutazioni. È inoltre possibile personalizzare un modello preconfigurato aggiungendo controlli e azioni personalizzati. Ad esempio, è possibile creare un modello per il controllo del processo aziendale oppure un modello per uno standard di protezione dei dati o di conformità regionale non incluso in uno dei modelli già configurati. Introducendo i propri modelli in Score Compliance, è possibile monitorare non solo le valutazioni cloud di Microsoft, ma anche eventuali altre valutazioni dei rischi nell'ambito della propria organizzazione.

I modelli preconfigurati per il Punteggio di conformità sono:

1. [Legge generale sulla protezione dei dati (LGPD) in Brasile](https://go.microsoft.com/fwlink/?linkid=2115387)
2. [California Consumer Privacy Act (CCPA)](https://go.microsoft.com/fwlink/?linkid=2108871) (anteprima)
3. [Matrice dei controlli cloud di Cloud Security Alliance (CSA) (CCM) 3.0.1](https://go.microsoft.com/fwlink/?linkid=2109076)
4. [GDPR Unione europea](https://go.microsoft.com/fwlink/?linkid=2108870)
5. [Opuscolo sulla sicurezza delle istituzioni finanziarie federali (FFIEC)](https://go.microsoft.com/fwlink/?linkid=2109077)
6. [FedRAMP moderato](https://go.microsoft.com/fwlink/?linkid=2108869)
7. [HIPAA](https://go.microsoft.com/fwlink/?linkid=2109078) / [Hitech](https://go.microsoft.com/fwlink/?linkid=2109079) HIPAA
8. [IRAP](https://go.microsoft.com/fwlink/?linkid=2113709) / ISM (anteprima) del[governo australiano](https://go.microsoft.com/fwlink/?linkid=2113024) di IRAP
9. [ISO 27001:2013](https://go.microsoft.com/fwlink/?linkid=2109073)
10. [ISO 27018:2014](https://go.microsoft.com/fwlink/?linkid=2109074)
11. [ISO 27701:2019](https://go.microsoft.com/fwlink/?linkid=2113025)
12. [Linea di base per la protezione dei dati di Microsoft 365](compliance-score-methodology.md#initial-score-based-on-microsoft-365-data-protection-baseline)
13. [NIST 800-53 Rev. 4](https://go.microsoft.com/fwlink/?linkid=2109075)
14. [NIST 800-171](https://go.microsoft.com/fwlink/?linkid=2108867)
15. [NIST Cybersecurity Framework (CSF)](https://go.microsoft.com/fwlink/?linkid=2108868)
16. [SOC 1](https://go.microsoft.com/fwlink/?linkid=2115184)
17. [SOC 2](https://go.microsoft.com/fwlink/?linkid=2115184)

Visualizzare [istruzioni dettagliate per la creazione di modelli](working-with-compliance-manager.md#templates), che si verifica in Compliance Manager.

### <a name="groups"></a>Gruppi

I gruppi consentono di organizzare valutazioni in modo logico. Ad esempio, è possibile scegliere di raggruppare le valutazioni per anno, standard di conformità, servizi, team all'interno dell'organizzazione o in qualche altro modo.

Quando due diverse valutazioni nello stesso gruppo condividono azioni gestite dal cliente, gli aggiornamenti apportati ai dettagli dell'implementazione, al testing e allo stato dell'azione in una valutazione verranno sincronizzati automaticamente alla stessa azione in qualsiasi altra valutazione del gruppo. La sincronizzazione delle azioni in questo modo consente di unificare le azioni di miglioramento assegnate all'interno del gruppo e di ridurre il lavoro di duplicazione.

Informazioni su come [creare i gruppi in Compliance Manager](working-with-compliance-manager.md#groups). Dopo aver creato i gruppi, è possibile [filtrare il dashboard del Punteggio di conformità](compliance-score-setup.md#filtering-your-dashboard-view) per visualizzare il Punteggio di uno o più gruppi.

## <a name="next-step-begin-setup"></a>Passaggio successivo: avviare l'installazione

Informazioni su come eseguire l'accesso, impostare le autorizzazioni e configurare gli aggiornamenti e le visualizzazioni del dashboard all' [installazione del Punteggio di conformità](compliance-score-setup.md).
