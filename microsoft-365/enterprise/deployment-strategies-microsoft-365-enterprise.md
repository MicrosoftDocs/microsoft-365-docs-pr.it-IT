---
title: Strategie di distribuzione dell'infrastruttura di base di Microsoft 365 Enterprise
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 01/23/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Informazioni su alcuni modi in cui è possibile distribuire le fasi dell'infrastruttura di base di Microsoft 365 Enterprise.
ms.openlocfilehash: fb4cf301f1e450cd5db9b392c0ca2d8e3767242a
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32289558"
---
# <a name="microsoft-365-enterprise-foundation-infrastructure-deployment-strategies"></a>Strategie di distribuzione dell'infrastruttura di base di Microsoft 365 Enterprise

Per distribuire le fasi dell'[infrastruttura di base](deploy-foundation-infrastructure.md) di Microsoft 365 Enterprise e implementarne le capacità, il software e i servizi agli utenti, è possibile scegliere tra numerose opzioni. Per iniziare a gestire i progetti di questa attività, che può essere lunga e complessa a seconda delle dimensioni dell'organizzazione e dell'infrastruttura esistente, prendere in considerazione le strategie di distribuzione seguenti:

- Distribuzione seriale
- Distribuzione in parallelo con implementazione utente senza sovrapposizione
- Distribuzione in parallelo con implementazione utente con sovrapposizione
- Infrastruttura predisposta in precedenza e implementazione della configurazione end-to-end

Usare queste strategie come suggerimenti su come gestire l'intero progetto e comprendere più rapidamente i vantaggi offerti da Microsoft 365 Enterprise per l'azienda.

>[!Note]
>Questo articolo contiene ipotesi e semplificazioni per descrivere in modo coerente le strategie di distribuzione. Queste strategie sono generalizzate, di conseguenza non implicano tempistiche specifiche, né possono essere considerate valide per qualsiasi situazione e organizzazione.
>

## <a name="elements-of-it-project-management-for-typical-enterprise-organizations"></a>Elementi della gestione dei progetti IT per organizzazioni aziendali standard

L'infrastruttura IT include i servizi back-end e l'implementazione di funzionalità nuove o migliorate oppure di software installato per gli utenti finali. I reparti IT distribuiscono in genere gli elementi di un'infrastruttura IT in modo sistematico. Un approccio per la corretta distribuzione di un elemento dell'infrastruttura IT prevede:

- Un'implementazione pilota 

  Include la configurazione e l'implementazione dell'infrastruttura iniziale per un set pilota di utenti, l'esecuzione di test e le successive modifiche alla configurazione dell'infrastruttura.

- Un'implementazione utente

  Include l'implementazione nel resto dell'organizzazione in base ad aree geografiche, reparti, gruppi o altri tipi di propagazione sistematica della configurazione o del software.

Il set di utenti nell'implementazione pilota non è uguale a quello dell'implementazione utente.

Per illustrare queste definizioni, in questo articolo si usano le immagini seguenti: 

![](./media/deployment-strategies-microsoft-365-enterprise/definitions.png) 

L'ombreggiatura nell'immagine relativa all'implementazione utente indica la percentuale di implementazione (da 0% a 100%) nell'organizzazione usando un approccio strutturato o metodico, ad esempio per gruppi, reparti o aree geografiche.

## <a name="deployment-strategies"></a>Strategie di distribuzione

Prendere in considerazione le strategie di distribuzione seguenti:

- Distribuzione seriale
- Distribuzione in parallelo con implementazione utente senza sovrapposizione
- Distribuzione in parallelo con implementazione utente con sovrapposizione
- Infrastruttura predisposta in precedenza e implementazione della configurazione end-to-end

### <a name="serial-deployment"></a>Distribuzione seriale

Con una distribuzione seriale si implementa completamente una fase, ovvero si consente alla fase di completare la distribuzione per tutti gli utenti, prima di passare a quella successiva. Ecco alcuni dei motivi per cui è consigliabile eseguire la distribuzione in questo modo:

- Riduzione dei rischi
- Vincoli relativi alla gestione delle risorse
- Cicli di finanziamento del reparto IT
- Dipendenze delle tecnologie IT
- Gestione delle modifiche aziendali e riluttanza degli utenti finali

Questo diagramma di Gantt mostra una distribuzione seriale semplificata delle fasi 2-6 dell'infrastruttura di base per Microsoft 365 Enterprise.

![](./media/deployment-strategies-microsoft-365-enterprise/serial.png) 
 
Per semplificare la discussione e l'esempio, si presuppone che ogni fase e ogni segmento di distribuzione all'interno di ogni fase richieda lo stesso tempo.

>[!Note]
>Fase 1: la connessione dell'infrastruttura di base di Microsoft 365 Enterprise è una fase di competenza esclusiva del reparto IT. Gli utenti possono usufruire dei vantaggi di una connettività ottimizzata alle risorse cloud di Microsoft, ma non sono obbligati a farlo.
>

Esperienza utente pilota semplificata di esempio:

- A dicembre si deve usare lo smartphone personale per la MFA. (Identity)
- A marzo si installa Windows 10 Enterprise nel desktop Windows 8.1. (Windows 10 Enterprise)
- A giugno si installa Office 365 ProPlus, in sostituzione di Office 2013. (Office 365 ProPlus)
- A settembre si applicano i criteri di accesso condizionale e alle app e di registrazione dei dispositivi. (Gestione dispositivi mobili)
- A dicembre si installa il client Azure Information Protection e si impara ad applicare etichette ai documenti. (Information Protection)

Ne risulta una cadenza di 90 giorni tra due implementazioni pilota.

Esperienza utente finale semplificata di esempio:

- A gennaio si deve usare lo smartphone personale per la MFA. (Identity)
- Ad aprile si installa Windows 10 Enterprise nel desktop Windows 8.1. (Windows 10 Enterprise)
- A luglio si installa Office 365 ProPlus, in sostituzione di Office 2013. (Office 365 ProPlus)
- A ottobre si applicano i criteri di accesso condizionale e alle app e di registrazione dei dispositivi. (Gestione dispositivi mobili)
- A gennaio dell'anno successivo si installa il client Azure Information Protection e si impara ad applicare etichette ai documenti. (Information Protection)

Ne risulta una cadenza di 90 giorni tra due implementazioni utente.

Lo svantaggio di questa strategia di distribuzione è che la distribuzione completa dell'infrastruttura di base di Microsoft 365 Enterprise può richiedere molto tempo.

### <a name="parallel-deployment-with-non-overlapping-user-rollout-parallel-1"></a>Distribuzione in parallelo con implementazione utente senza sovrapposizione (in parallelo 1)

Per questa strategia di distribuzione si avvia l'implementazione pilota della fase successiva durante l'ultima parte dell'implementazione utente della fase corrente. Ecco la distribuzione delle fasi 2-6 quando l'implementazione pilota viene avviata quando l'implementazione utente della fase precedente sta per terminare.

Ecco un confronto semplificato tra le strategie di distribuzione seriale e in parallelo.

![](./media/deployment-strategies-microsoft-365-enterprise/parallel1.png) 
 
Il risultato finale è che l'implementazione utente per la fase corrente viene completata in tutta l'organizzazione prima dell'avvio di quella successiva. Gli utenti che non sono inclusi nelle implementazioni pilota non devono gestire le implementazioni di più fasi contemporaneamente, ma le implementazioni pilota vengano eseguite in parallelo con quelle utente.

Esperienza utente pilota semplificata di esempio: 

- A dicembre si deve usare lo smartphone personale per la MFA. (Identity)
- A febbraio si installa Windows 10 Enterprise nel desktop Windows 8.1. (Windows 10 Enterprise)
- Ad aprile si installa Office 365 ProPlus, in sostituzione di Office 2013. (Office 365 ProPlus)
- A giugno si applicano i criteri di accesso condizionale e alle app e di registrazione dei dispositivi. (Gestione dispositivi mobili)
- Ad agosto si installa il client Azure Information Protection e si impara ad applicare etichette ai documenti. (Information Protection)

Ne risulta una cadenza di 60 giorni tra due implementazioni pilota.

Esperienza utente finale semplificata di esempio:

- A gennaio si deve usare lo smartphone personale per la MFA. (Identity)
- A marzo si installa Windows 10 Enterprise nel desktop Windows 8.1. (Windows 10 Enterprise)
- A maggio si installa Office 365 ProPlus, in sostituzione di Office 2013. (Office 365 ProPlus)
- A luglio si applicano i criteri di accesso condizionale e alle app e di registrazione dei dispositivi. (Gestione dispositivi mobili)
- A settembre si installa il client Azure Information Protection e si impara ad applicare etichette ai documenti. (Information Protection)

Ne risulta una cadenza di 60 giorni tra due implementazioni utente.

Il vantaggio di questa strategia di distribuzione è che può richiedere meno tempo per distribuire completamente l'infrastruttura di base di Microsoft 365 Enterprise, senza che il reparto IT e gli utenti debbano gestire più implementazioni contemporaneamente.

### <a name="parallel-deployment-with-overlapping-user-rollout-parallel-2"></a>Distribuzione in parallelo con implementazione utente con sovrapposizione (in parallelo 2)

Per questa strategia di distribuzione si avviano:

- L'implementazione pilota della fase successiva durante l'ultima parte dell'implementazione utente della fase corrente.
- L'implementazione utente della fase successiva durante l'implementazione utente della fase corrente in modo che nessun utente debba gestire l'implementazione di più fasi contemporaneamente. Questa operazione presuppone che ogni fase dell'infrastruttura di base venga implementata nello stesso modo, tramite aree geografiche, reparti o altri criteri.

Ecco un confronto semplificato tra le diverse strategie di distribuzione.

![](./media/deployment-strategies-microsoft-365-enterprise/parallel2.png) 

Il risultato finale è il seguente:

- Le implementazioni pilota passano da una fase all'altra senza pause.
- L'implementazione utente per una fase inizia prima del completamento dell'implementazione utente della fase precedente, ma nessun singolo utente implementa più di una fase alla volta.

Esperienza utente pilota semplificata di esempio: 

- A dicembre si deve usare lo smartphone personale per la MFA. (Identity)
- A gennaio si installa Windows 10 Enterprise nel desktop Windows 8.1. (Windows 10 Enterprise)
- A febbraio si installa Office 365 ProPlus, in sostituzione di Office 2013. (Office 365 ProPlus)
- A marzo si applicano i criteri di accesso condizionale e alle app e di registrazione dei dispositivi. (Gestione dispositivi mobili)
- Ad aprile si installa il client Azure Information Protection e si impara ad applicare etichette ai documenti. (Information Protection)

Ne risulta una cadenza di 30 giorni tra due implementazioni pilota.

Esperienza utente finale semplificata di esempio:

- A gennaio si deve usare lo smartphone personale per la MFA. (Identity)
- A febbraio si installa Windows 10 Enterprise nel desktop Windows 8.1. (Windows 10 Enterprise)
- A marzo si installa Office 365 ProPlus, in sostituzione di Office 2013. (Office 365 ProPlus)
- Ad aprile si applicano i criteri di accesso condizionale e alle app e di registrazione dei dispositivi. (Gestione dispositivi mobili)
- A maggio si installa il client Azure Information Protection e si impara ad applicare etichette ai documenti. (Information Protection)

Ne risulta una cadenza di 30 giorni tra due implementazioni utente.

Il vantaggio di questa strategia di distribuzione è che può richiedere ancor meno tempo per la distribuzione completa dell'infrastruttura di base di Microsoft 365 Enterprise, e anche in questo caso senza che gli utenti debbano gestire più implementazioni contemporaneamente. Non è però prevista una pausa per gli utenti tra una fase e l'altra.

### <a name="up-front-infrastructure-and-rollout-of-end-to-end-configuration"></a>Infrastruttura predisposta in precedenza e implementazione della configurazione end-to-end

Per le organizzazioni di dimensioni inferiori che possono comprimere le fasi 2-6 in un unico segmento di distribuzione, la distribuzione risultante è simile alla seguente:
 
![](./media/deployment-strategies-microsoft-365-enterprise/up-front.png) 

Il reparto IT configura l'infrastruttura per le fasi 2-6, quindi esegue l'implementazione per gli utenti pilota per verificare la funzionalità end-to-end. Ad esempio, gli utenti pilota ottengono contemporaneamente tutte le funzionalità seguenti:

- MFA e altre funzionalità per la gestione delle identità (Identity)
- Windows 10 Enterprise in dispositivi Windows (Windows 10 Enterprise)
- Office 365 ProPlus per la famiglia di prodotti Office (Office 365 ProPlus)
- Criteri di accesso condizionale e alle app (Gestione dispositivi mobili)
- Installazione del client Azure Information Protection e training su come applicare etichette ai documenti (Information Protection)

Al termine dell'implementazione pilota, viene avviata l'implementazione utente in cui ogni utente ottiene contemporaneamente tutte le funzionalità.

## <a name="next-step"></a>Passaggio successivo

Avviare la distribuzione di Microsoft 365 Enterprise con l'[infrastruttura di base](deploy-foundation-infrastructure.md).
