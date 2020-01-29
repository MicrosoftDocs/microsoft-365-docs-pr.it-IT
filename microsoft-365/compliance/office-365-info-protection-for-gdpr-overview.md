---
title: >
  Panoramica di Office 365 Information Protection per RGPD
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 2/7/2018
audience: ITPro
ms.topic: overview
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- GDPR
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: Panoramica di Office 365 Information Protection per GDPR. Informazioni su come individuare, classificare, proteggere e monitorare i dati personali.
ms.openlocfilehash: d4e84e6a3fc1020f3eecda6eb72e3d02a9f66555
ms.sourcegitcommit: 03a83ff76c8162b850c4c552759c49f2a4750574
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2020
ms.locfileid: "41558503"
---
# <a name="overview-of-office-365-information-protection-for-gdpr"></a>Panoramica di Office 365 Information Protection per RGPD


Questa soluzione mostra come proteggere i dati riservati archiviati nei servizi di Office 365. Include suggerimenti prescrittivi per individuare, classificare, proteggere e monitorare i dati personali. Questa soluzione utilizza l'RGPD come esempio, ma è possibile applicare lo stesso processo per raggiungere la conformità con molti altri regolamenti.

L'RGPD regola la raccolta, l'archiviazione, l'elaborazione e la condivisione dei dati personali. I dati personali sono definiti in modo molto ampio nell'RGPD, come qualsiasi dato relativo a una persona fisica identificata o identificabile residente nell'Unione Europea.

Articolo 4 - Definizioni

> con "dati personali" si intende qualsiasi informazione relativa a una persona fisica identificata o identificabile ("soggetto dei dati"); una persona fisica identificabile è una persona che può essere identificata, direttamente o indirettamente, in particolare in riferimento a un identificatore come un nome, un numero di identificazione, dati sulla posizione, un identificatore online o a uno o più fattori specifici per l'identità fisica, psicologica, genetica, mentale, economica, culturale o sociale della persona fisica;

Questa soluzione vuole aiutare le organizzazioni a individuare e proteggere i dati personali in Office 365 che potrebbero essere soggetti all'RGPD. Non offre o rappresenta una conferma della conformità all'RGPD. Le organizzazioni sono tenute a verificare autonomamente la conformità all'RGPD mediante i propri esperti legali e di conformità o avvalendosi di professionisti esterni specializzati in conformità.


[GDPR Assessment](https://www.microsoft.com/cyberassessment/en/gdpr/uso365?ls=Email&mkt_tok=eyJpIjoiTTJFeE5USXlOR1EwTWpJMiIsInQiOiJQTmdCYWR5NTlOd3JLWHZlb2NzNldKclQ4ZVBzVmhGeUhoUlFcL1pvSDIyXC9Ka05iTUR1aGpxT0YxQ0FUeGNDOUlkbWZLM1U4SUZWZmEyaGF6XC9ueUxkTHJzZnB3VDRMZlhPdkR4MzRLWkF5ckRNdWwxUkgzXC9yRU8yNkttSHhTb3VpZjNyVlJrNm9TTVZRYU5HR240a0FRPT0ifQ%3D%3D) è uno strumento rapido, online di autovalutazione che consente alle autorizzazioni di verificare gratuitamente il proprio livello di preparazione alla conformità con l'RGPD.

## <a name="assess-and-manage-your-compliance-risk"></a>Verificare e gestire il rischio di conformità

Il primo passo per la conformità RGPD consiste nel valutare se tale regolamento è applicabile all'organizzazione e, in tal caso, in quale misura. L'analisi include la comprensione dei dati elaborati dall'organizzazione e dove questi si trovano.

### <a name="step-1--use-compliance-score-to-view-the-regulation-requirements-and-track-your-progress"></a>Fase 1 - Usare il punteggio di conformità per verificare i requisiti normativi e tenere traccia dello stato di avanzamento

Il punteggio di conformità offre strumenti per tenere traccia, implementare e gestire i controlli per consentire all'organizzazione di raggiungere la conformità con diversi standard, tra cui GDPR.

![Usare il punteggio di conformità e Compliance Manager per verificare i requisiti normativi e tenere traccia dello stato di avanzamento](Media/Overview-image1.png)

Per ulteriori informazioni, vedere [punteggio di conformità](compliance-score.md).

### <a name="step-2--use-content-search-and-sensitive-information-types-to-find-personal-data"></a>Fase 2 - Usare Ricerca contenuto e le tipologie di informazioni sensibili per trovare i dati personali
 

Individuare i dati personali nel proprio ambiente soggetti all'RGPD. Usare Ricerca contenuto insieme alle tipologie di informazioni sensibili per:


- Trovare e indicare dove si trovano i dati personali.

- Ottimizzare i tipi di dati riservati e altre query per trovare tutti i dati personali nel proprio ambiente.

![ Usare Ricerca contenuto e le tipologie di informazioni sensibili per trovare i dati personali
](Media/Overview-image2.png)

Le tipologie di informazioni sensibili permettono di riconoscere in modo automatico informazioni specifiche come i numeri di previdenza sociale e di carta di credito. Questo articolo include una serie di tipologie da usare come punto di partenza. Molte altre tipologie di informazioni sensibili saranno presto disponibili per i dati personali nei paesi dell'Unione Europea.


Per ulteriori informazioni, vedere [Cercare e trovare i dati personali](search-for-and-find-personal-data.md). 

## <a name="classify-protect-and-monitor-personal-data-in-office-365-and-other-saas-apps"></a>Classificare, proteggere e monitorare i dati personali in Office 365 e altre applicazioni SaaS

Alcune funzionalità utilizzate per la protezione delle informazioni in Office 365 possono anche essere usate per proteggere i dati riservati nelle altre applicazioni SaaS.

![Classificare, proteggere e monitorare i dati personali](Media/Overview-image3.png)

L'illustrazione seguente viene descritta ulteriormente nella sezione (dalla fase 3 alla fase 5).


### <a name="step-3--decide-if-you-want-to-use-labels-in-addition-to-sensitive-information-types"></a>Fase 3 - Decidere se usare anche le etichette, oltre alle tipologie di informazioni sensibili


Le tipologie di informazioni sensibili permettono di classificare i dati. Vedere [Definire uno schema di classificazione per i dati personali](architect-a-classification-schema-for-personal-data.md), per decidere se usare anche le etichette. Per applicare le etichette, vedere [Applicare le etichette ai dati personali in Office 365](apply-labels-to-personal-data-in-office-365.md).


La figura mostra l'uso delle etichette e delle tipologie di informazioni sensibili in Office 365. Prossimamente sarà possibile utilizzarli anche con Cloud App Security per trovare i dati sensibili nelle altre applicazioni SaaS, ad esempio Box e Salesforce.


### <a name="step-4--protect-personal-data-in-office-365"></a>Fase 4 - Proteggere i dati personali in Office 365
 

La protezione dei dati personali inizia con la prevenzione della perdita dei dati di Office 365. Esistono molte altre funzionalità consigliate per proteggere l'accesso ai dati personali, tra cui Crittografia dei messaggi di Office 365 per la posta elettronica.

Queste protezioni possono essere applicate a set di dati specifici:

- Autorizzazioni a livello di sito e raccolta

- Criteri di condivisione esterna a livello di sito

- Criteri di accesso ai dispositivi a livello di sito


La protezione per l'accesso a Office 365 e altri servizi cloud include:

- Protezione dell'accesso a identità e dispositivi in Enterprise Mobility + Security (EMS)

- Gestione accessi con privilegi

- Funzionalità di sicurezza di Windows 10

Per ulteriori informazioni sull'applicazione della protezione, vedere [Applicare la protezione ai dati personali di Office 365](apply-protection-to-personal-data-in-office-365.md).

### <a name="step-5--monitor-for-leaks-of-personal-data"></a>Fase 5 - Monitorare la perdita di dati personali


I report sulla prevenzione della perdita dei dati di Office 365 forniscono il livello maggiore di dettaglio per il monitoraggio dei dati riservati. È possibile configurare avvisi automatici e analizzare violazioni utilizzando il log di controllo di Office 365. Cloud App Security estende la capacità di trovare e monitorare i dati riservati ad altri provider SaaS. Per ulteriori informazioni su questi strumenti, vedere [Monitorare le violazioni dei dati personali](/security/office-365-security/monitor-for-leaks-of-personal-data.md).
