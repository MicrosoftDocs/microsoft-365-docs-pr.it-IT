---
title: Securities and Exchange Commission-regolamentazione dei sistemi Compliance and Integrity (SCI)
description: Le regole di fantascienza si applicano alle entità di fantascienza, che includono organizzazioni di autoregolamentazione (OAD) come scambiatori di stock e opzioni, agenzie di compensazione registrate e sistemi di negoziazione alternativi (ATS).
keywords: Microsoft 365, conformità, offerte
localization_priority: None
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
titleSuffix: Microsoft Compliance
ms.openlocfilehash: 962524f29b72d46500869f4f0059959a2b77ff3e
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601863"
---
# <a name="securities-and-exchange-commission-regulation-systems-compliance-and-integrity-sci"></a>Securities and Exchange Commission: regolamentazione dei sistemi Compliance and Integrity (SCI)

## <a name="about-regulation-sci"></a>Informazioni su Regulation SCI

La US Securities and Exchange Commission (SEC) è un'agenzia indipendente del governo federale degli Stati Uniti e del soprintendente primario e regolatore dei mercati di titoli statunitensi. Esercita l'autorità di applicazione sulle leggi sui titoli federali, propone nuove regole di titoli e supervisiona la regolamentazione del mercato del settore dei titoli.

Nel novembre 2014, la SEC ha adottato [Regulation Systems Compliance and Integrity (sci)](https://www.sec.gov/rules/final/2014/34-73639.pdf) (e forma sci per la segnalazione degli eventi di fantascienza) per rafforzare l'infrastruttura tecnologica nei mercati dei titoli statunitensi. Il regolamento ha lo scopo di ridurre la frequenza delle interruzioni del sistema, migliorare la resilienza quando si verificano tali incidenti e aumentare la svista SEC della tecnologia del mercato dei titoli e l'applicazione delle sue normative.

Le regole di fantascienza si applicano alle entità di fantascienza, che includono organizzazioni di autoregolamentazione (OAD) come scambiatori di stock e opzioni, agenzie di compensazione registrate e sistemi di negoziazione alternativi (ATS). Le regole regolano principalmente i sistemi che supportano direttamente le funzioni principali del mercato dei titoli: negoziazione, liquidazione e liquidazione, routing degli ordini, dati di mercato, regolamentazione del mercato e sorveglianza del mercato.

## <a name="microsoft-and-sec-regulation-sci"></a>Microsoft e SEC Regulation SCI

La US Securities and Exchange Commission (SEC) ha adottato il regolamento SCI per rafforzare l'infrastruttura tecnologica delle organizzazioni finanziarie che operano e supportano i mercati dei titoli degli Stati Uniti. Sotto la svista SEC, i suoi requisiti sono stati studiati per garantire che questi sistemi siano a disponibilità elevata, resilienza forte e bassa latenza (elevato volume di messaggi con scarso ritardo).

Per aiutare i clienti dei servizi finanziari degli Stati Uniti a essere conformi al presente regolamento, Microsoft ha pubblicato la [Guida all'implementazione di Microsoft Azure sec Regulation Systems Compliance and Integrity cloud](https://servicetrust.microsoft.com/ViewPage/TrustDocumentsV3?command=Download&downloadType=Document&downloadId=a69ce0c1-7b7e-44e9-9143-867241e6b2f9&tab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913&docTab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913_FAQ_and_White_Papers). Le indicazioni contenute in questo documento:

- Viene fornita una panoramica delle funzionalità di Azure complessive che supportano una forte resilienza, la disponibilità elevata e una bassa latenza.
- Consente di chiarire quali aree di controllo e aspetti normativi indirizzi di Azure. Questo mapping punto per punto di funzionalità e servizi di Azure ai requisiti di fantascienza misura la conformità di Azure rispetto al Framework normativo. Consente inoltre ai clienti di comprendere dove è possibile spostare le responsabilità di sicurezza in Azure che erano completamente proprietarie quando operavano in locale. Queste funzionalità sono configurate dalle promesse di Microsoft nei contratti di SLA di Azure.
- Specifica ogni requisito di SIC di regolamentazione che è responsabile del cliente per l'indirizzo e offre documentazione e servizi di Azure per aiutarli a rispondere a queste responsabilità.

Questo documento fornisce un'accurata lista di controllo delle aree critiche di regolamentazione di fantascienza. Questo elenco di controllo consente alle organizzazioni finanziarie di comprendere in che modo è possibile adottare Azure per garantire ai propri regolatori, clienti e dirigenti la conformità con i requisiti normativi applicabili.

## <a name="microsoft-in-scope-cloud-services"></a>Servizi cloud Microsoft inclusi nell'ambito

- [Azure](https://aka.ms/AzureCompliance)

## <a name="how-to-implement"></a>Come implementare

- [Guida all'implementazione di sci di regolamentazione](https://servicetrust.microsoft.com/ViewPage/TrustDocumentsV3?command=Download&downloadType=Document&downloadId=a69ce0c1-7b7e-44e9-9143-867241e6b2f9&tab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913&docTab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913_FAQ_and_White_Papers): esegue il mapping delle funzionalità di Azure rispetto alla normativa e dettaglia la responsabilità condivisa per la conformità.
- [Progettazione di applicazioni di Azure affidabili](https://docs.microsoft.com/azure/architecture/resiliency/): breve panoramica del modo in cui creare l'affidabilità in ogni passaggio della progettazione delle applicazioni di Azure.
- [Progettazione di applicazioni a disponibilità elevata](https://docs.microsoft.com/azure/storage/common/storage-designing-ha-apps-with-ragrs): in che modo gli sviluppatori possono contribuire a garantire che le applicazioni di archiviazione di Azure siano estremamente disponibili.
- [Valutazione dei rischi e guida alla conformità](https://aka.ms/RiskGovernanceGuide): per creare un modello di governance per la valutazione dei rischi dei servizi cloud Microsoft e la notifica all'autorità competente.

## <a name="frequently-asked-questions"></a>Domande frequenti

**Cosa significa la responsabilità condivisa quando si utilizza la tecnologia cloud?**

Poiché gli ambienti di elaborazione passano dai data center locali a quelli nel cloud, la responsabilità della sicurezza si sposta anche, ovvero il provider di servizi cloud (CSP) e il cliente ora condividono questa responsabilità. Per ogni applicazione e soluzione, la quantità di responsabilità spetta al cliente e la quantità di informazioni sul provider dipende dal modello di Azure distribuito da un cliente, ovvero IaaS, SaaS o PaaS. Il cliente è tenuto a capire in che misura essi siano responsabili dell'implementazione dei controlli di sicurezza richiesti. Tuttavia, Microsoft fornisce indicazioni che consentono ai clienti di esplorare la dinamica complessa. Per ulteriori informazioni, leggere [responsabilità condivise per il cloud computing](https://gallery.technet.microsoft.com/Shared-Responsibilities-81d0ff91).

**Quali istituzioni finanziarie possono usufruire di Azure per contribuire a soddisfare i requisiti di SCI regolamentare?**

Le organizzazioni finanziarie o le entità di fantascienza che sono soggette a questo regolamento possono distribuire Azure. La SEC dice che la sua regolamentazione si applica a' Self-Regulatory Organizations (OAD), compresi gli scambi di opzioni e stock, agenzie di compensazione registrate, FINRA, e la MSRB, sistemi alternativi di negoziazione (ATS), che gli stock di nanometri commerciali e non-SMN superiori a quelli specificati soglie dei volumi, disseminatori di dati di mercato consolidati (piano Processor) e di alcune agenzie di compensazione esenti.

## <a name="resources"></a>Risorse

- [SEC risposte alle domande più frequenti relative alla normativa SCI](https://www.sec.gov/divisions/marketreg/regulation-sci-faq.shtml)
- [Continuità aziendale e ripristino di emergenza (BCDR): aree con accoppiamento Azure](https://docs.microsoft.com/azure/best-practices-availability-paired-regions)
- [Mappa di conformità dei principi di regolamentazione del cloud computing e di Microsoft Online Services](https://aka.ms/FinServ-Guide-US)
- [Cloud Financial Services Compliance Program di Microsoft](https://aka.ms/FSCP-Print)
- [Conformità dei servizi finanziari in Azure](https://aka.ms/FinServ-Compliance-Azure)
- [Servizi finanziari Microsoft](https://aka.ms/FinServ-Compliance)
- [Regola di Microsoft e SEC 17a-4](offering-SEC-17a-4.md)
- [Conformità in Microsoft Trust Center](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a>Scarica il documento di informazioni di base sulla soluzione

Ti serve il documento di informazioni di base sulla soluzione? Scarica il [PDF](https://download.microsoft.com/download/8/1/a/81aa04eb-3c1f-4c1a-ba7d-9d30032acc52/SEC_Reg_SCI-Compliance.pdf).