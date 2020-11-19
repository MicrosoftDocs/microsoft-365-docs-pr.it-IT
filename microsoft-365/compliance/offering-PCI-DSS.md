---
title: Payment Card Industry (PCI) Data Security Standard (DSS)
description: Azure, SharePoint Online e OneDrive for Business sono conformi a Payment Card Industry Data Security Standards Level 1 versione 3.2.
keywords: Microsoft 365, conformità, offerte
localization_priority: Priority
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 57164e08128080f90cb3985b3a3f887521f4c3d5
ms.sourcegitcommit: 0402d3275632fceda9137b6abc3ce48c8020172a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/17/2020
ms.locfileid: "49126599"
---
# <a name="payment-card-industry-pci-data-security-standard-dss"></a>Payment Card Industry (PCI) Data Security Standard (DSS)

## <a name="pci-dss-overview"></a>Panoramica PCI DSS

Il Payment Card Industry (PCI) Data Security Standards (DSS) è uno standard di sicurezza delle informazioni globale progettato per prevenire le frodi attraverso un maggiore controllo dei dati delle carte di credito. Tutte le organizzazioni, indipendentemente dalle loro dimensioni, devono aderire agli standard PCI DSS se accettano le carte di pagamento dei cinque principali istituti ovvero Visa, MasterCard, American Express, Discover e Japan Credit Bureau (JCB). L'adozione dello standard PCI DSS è obbligatoria per tutte le organizzazioni che archiviano, elaborano o trasmettono dati di pagamento e dei titolari di carte di credito.

## <a name="microsoft-and-pci-dss"></a>Microsoft e PCI DSS

Microsoft ha incaricato un Qualified Security Assessor (QSA) approvato di condurre una valutazione PCI DSS annuale. I revisori hanno valutato gli ambienti Microsoft Azure, Microsoft OneDrive for Business e Microsoft SharePoint Online comprese le infrastrutture, l’ambiente di sviluppo e operativo, la gestione, il supporto e i servizi applicabili. Lo standard PCI DSS definisce quattro livelli di conformità secondo il volume di transazioni. Azure, OneDrive for Business e SharePoint Online hanno ottenuto la certificazione di conformità a PCI DSS versione 3.2 al livello 1 dei provider di servizi (il volume più alto di transazioni, ovvero oltre 6 milioni all'anno).

I risultati della valutazione sono riportati in un Attestato di conformità (AoC, Attestation on Compliance), consultabile dai clienti, e in un Report di conformità (RoC, Report on Compliance) rilasciati dal QSA. Il periodo di validità della conformità inizia dopo il superamento del controllo e dopo aver ricevuto l'AoC dal QSA e termina dopo un anno a partire dalla data della firma dell'Attestato di conformità. 

I clienti che intendono sviluppare un ambiente per i titolari di carte di credito o un servizio di elaborazione carte possono sfruttare questi attestati anche per molte delle porzioni sottostanti e ridurre così le attività e i costi necessari per ottenere la loro certificazione PCI DSS.

È importante capire che lo stato di conformità allo standard PCI DSS di Azure, OneDrive for Business e SharePoint Online non si traduce automaticamente in una certificazione PCI DSS per i servizi che i clienti creano o ospitano su queste piattaforme. Il rispetto dei requisiti PCI DSS è responsabilità dei clienti.

## <a name="microsoft-in-scope-cloud-services"></a>Servizi cloud Microsoft associati

- [Azure e Azure per enti pubblici](https://azure.microsoft.com/global-infrastructure/government/)
- Microsoft Cloud App Security
- Servizio cloud Flow, indipendente o incluso in un piano o in una famiglia di prodotti Office 365 o Dynamics 365
- Microsoft Graph
- Intune
- [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- Servizio cloud PowerApps come servizio autonomo o incluso in un piano o in una famiglia di prodotti con marchio Office 365 o Dynamics 365
- Servizio cloud Power BI, autonomo o incluso in un piano o in una famiglia di prodotti Office 365
- Ricerca in OneDrive for Business e SharePoint Online (solo Stati Uniti)

## <a name="audit-reports-and-certificates"></a>Controlli, report e certificati

- [Attestato di conformità PCI DSS di Azure](https://aka.ms/azure-pci)
- [Attestato di conformità PCI DSS di OneDrive for Business e SharePoint Online](https://aka.ms/spo-pci)

## <a name="get-your-pci-dss-solution-running-on-azure"></a>Creare una soluzione PCI DSS per Azure

Per creare e implementare una soluzione PCI DSS nel cloud in maniera ancora più rapida è possibile usare i progetti di sicurezza e conformità di Azure per PCI DSS. Architettura di riferimento, guide per l'implementazione, mappe di controllo dell'implementazione, script automatizzati e molto altro. [Iniziare a usare il modello di progetto PCI DSS di Azure](https://aka.ms/pciblueprint).

## <a name="frequently-asked-questions"></a>Domande frequenti

**Perché la data riportata sulla prima pagina dell'Attestato di conformità adeguamento (AoC) è “giugno 2018”?**

La data giugno 2018 riportata sulla prima pagina dell’attestato si riferisce a quando il modello AoC è stato pubblicato. Fare riferimento alla Sezione 2 per la data della valutazione.

**Perché ci sono vari Attestati di conformità di Azure?**

Il pacchetto Attestati di conformità di Azure comprende gli attestati per il cloud di Azure Public, Azure Germania e Azure per gli enti pubblici. I clienti dovrebbero usare l'attestato di conformità corrispondente al proprio ambiente Azure.  

**Qual è la relazione tra PA DSS e PCI DSS?**

Il Payment Application Data Security Standard (PA DSS) è un insieme di requisiti conformi a PCI DSS che sostituisce le Payment Application Best Practices di Visa e riunisce tutti i requisiti di conformità degli altri principali istituti emittenti delle carte. Il PA DSS aiuta i fornitori di software a sviluppare applicazioni di terze parti per archiviare, elaborare o trasmettere i dati di pagamento dei titolari delle carte per l’autorizzazione o il saldo di una transazione. I venditori al dettaglio devono usare applicazioni certificate PA DSS per la conformità allo standard PCI DSS. PA DSS non si applica ad Azure.

**Cosa si intende per acquirente? Azure usa un acquirente?**

Un acquirente è una banca o un altro istituto finanziario che elabora le transazioni con carta di pagamento. Azure non offre l'elaborazione delle carte di pagamento come servizio, pertanto non si serve di un acquirente.

**A quali organizzazioni ed esercenti si applica PCI DSS?**

PCI DSS si applica a qualsiasi azienda, a prescindere dalle dimensioni o dal numero di transazioni elaborate, che accetta, trasmette o archivia i dati dei titolari di carte. Ciò significa che se un cliente effettua un pagamento all'azienda usando una carta di credito o debito, si applicano i requisiti PCI DSS. Le aziende vengono valutate rispetto ai quattro livelli disponibili in base al volume di transazioni totale elaborate in un periodo di 12 mesi. Il livello 1 è per le aziende che elaborano oltre 6 milioni di transazioni all'anno, il livello 2 da 1 milione a 6 milioni, il livello 3 da 20.000 a 1 milione e il livello 4 fino a 20.000 transazioni.

**Come inizio il processo di adeguamento a PCI DSS della mia organizzazione per una soluzione in un ambiente Azure?**

Le pubblicazioni del PCI Security Standards Council offrono informazioni molto utili sui requisiti di conformità. L’organizzazione pubblica la [Guida di riferimento rapida PCI DSS](https://www.pcisecuritystandards.org/documents/PCISSC%20QRG%20August%202014%20-print.pdf) per gli esercenti e gli altri istituti che elaborano i pagamenti con le carte. La guida spiega come lo standard PCI DSS contribuisce a proteggere l'ambiente in cui avvengono le transazioni con carta di credito e come applicarlo.

Il processo di adeguamento implica diversi elementi, tra cui la valutazione dei sistemi e dei processi non ospitati in Azure. I singoli requisiti dipendono dai servizi di Azure usati e da come vengono impiegati nell'ambito della soluzione.

**OneDrive for Business e SharePoint Online saranno conformi a PCI DSS al fuori degli Stati Uniti?**

Al momento, OneDrive for Business e SharePoint Online sono conformi a PCI DSS solo negli Stati Uniti. Microsoft valuterà i requisiti e le tempistiche per le altre aree geografiche e informerà i clienti se il processo di adozione di PCI DSS interesserà altre aree geografiche.

**Cosa includono OneDrive for Business e SharePoint Online?**

Al momento, solo i file e i documenti caricati su OneDrive for Business e SharePoint Online saranno conformi a PCI DSS.

## <a name="use-microsoft-compliance-manager-to-assess-your-risk"></a>Usare Microsoft Compliance Manager per valutare i rischi

[Microsoft Compliance Manager](compliance-manager.md) è una funzionalità del [Centro conformità Microsoft 365](microsoft-365-compliance-center.md) utile per comprendere lo stato di conformità dell'organizzazione e adottare misure per ridurre i rischi. Compliance Manager offre un modello premium per creare una valutazione per questa normativa. È possibile trovare il modello nella pagina dei **modelli di valutazione** in Compliance Manager. Informazioni su come [creare valutazioni in Compliance Manager](compliance-manager-assessments.md).

## <a name="resources"></a>Risorse

- [PCI Security Standards Council](https://www.pcisecuritystandards.org/)
- [PCI Data Security Standard](https://www.pcisecuritystandards.org/documents/PCI_DSS_v3-1.pdf)
- [Azure PCI DSS 3.2.1 Blueprint](https://docs.microsoft.com/azure/governance/blueprints/samples/pci-dss-3.2.1/)
- [PCI DSS Quick Reference Guide](https://www.pcisecuritystandards.org/documents/PCISSC%20QRG%20August%202014%20-print.pdf)
- [Conformità nel Centro protezione Microsoft](https://www.microsoft.com/trust-center/compliance/compliance-overview)
