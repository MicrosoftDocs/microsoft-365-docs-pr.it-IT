---
title: Payment Card Industry (PCI) Data Security Standard (DSS)
description: Azure, SharePoint Online e OneDrive for Business sono conformi a Payment Card Industry Data Security Standards Level 1 versione 3.2.
keywords: Microsoft 365, conformità, offerte
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
ms.openlocfilehash: 7c87b758798c2676ca627f738d8d48c97161b4d1
ms.sourcegitcommit: eb0f255baff1f2856621cbc64a3f34a04be37be3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2019
ms.locfileid: "39859506"
---
# <a name="payment-card-industry-pci-data-security-standard-dss"></a>Payment Card Industry (PCI) Data Security Standard (DSS)

## <a name="pci-dss-overview"></a>Panoramica PCI DSS

Il Payment Card Industry (PCI) Data Security Standards (DSS) è uno standard di sicurezza delle informazioni globale progettato per prevenire le frodi attraverso un maggiore controllo dei dati delle carte di credito. Le organizzazioni di tutte le dimensioni devono seguire gli standard PCI DSS se accettano le carte di pagamento dei cinque principali brand, ovvero Visa, MasterCard, American Express, Discover e Japan Credit Bureau (JCB). L'adeguamento allo standard PCI DSS è richiesto a tutte le organizzazioni che archiviano, elaborano o trasmettono dati di pagamento e dei titolari di carte di credito.

## <a name="microsoft-and-pci-dss"></a>Microsoft e PCI DSS

Microsoft ha completato una valutazione annuale PCI DSS attraverso un Qualified Security Assessor (QSA) approvato. Gli autori hanno analizzato gli ambienti Microsoft Azure, Microsoft OneDrive for Business e Microsoft SharePoint Online che includono validazione delle infrastrutture, sviluppo, operazioni, gestione, supporto e servizi inclusi. Lo standard PCI DSS definisce quattro livelli di adeguamento in base al volume di transazioni. Azure, OneDrive for Business e SharePoint Online hanno ottenuto la certificazione di adeguamento a PCI DSS versione 3.2 al livello di provider di servizi 1 (il maggior volume di transazioni, ovvero oltre 6 milioni all'anno).

I risultati della valutazione sono riportati in un Attestato di adeguamento (AoC, Attestation on Compliance), consultabile dai clienti, e in un Rapporto di adeguamento (RoC, Report on Compliance) rilasciati dal QSA. Il periodo di validità dell'adeguamento ha inizio dopo il superamento del controllo e dopo aver ricevuto l'AoC dal QSA e termina dopo un anno a partire dalla data della firma dell'Attestato di adeguamento. 

I clienti che intendono sviluppare un ambiente per i titolari di carte di credito o un servizio di elaborazione carte possono utilizzare queste convalide in molte delle porzioni sottostanti, riducendo così lo sforzo e i costi associati di ottenere la loro certificazione PCI DSS.

È importante capire che lo stato di adeguamento allo standard PCI DSS di Azure, OneDrive for Business e SharePoint Online non si traduce automaticamente in una certificazione PCI DSS per i servizi che i clienti creano o ospitano su queste piattaforme. I clienti sono responsabili di ottenere l'adeguamento ai requisiti PCI DSS.

## <a name="microsoft-in-scope-cloud-services"></a>Servizi cloud Microsoft inclusi

- [Azure e Azure per enti pubblici](https://aka.ms/AzureCompliance)
- Cloud App Security
- Servizio cloud Flow, indipendente o incluso in un piano o in una famiglia di prodotti con marchio Office 365 o Dynamics 365
- Graph
- Intune
- Servizio cloud PowerApps, autonomo o incluso in un piano o in una famiglia di prodotti con marchio Office 365 o Dynamics 365
- Servizio cloud Power BI, autonomo o incluso in un piano o in una famiglia di prodotti con marchio Office 365
- Ricerca in OneDrive for Business e SharePoint Online (solo Stati Uniti)

## <a name="audit-reports-and-certificates"></a>Controlli, report e certificati

- [Attestato di adeguamento PCI DSS di Azure](https://aka.ms/azure-pci)
- [Attestato di adeguamento PCI DSS di OneDrive for Business e SharePoint Online](https://aka.ms/spo-pci)

## <a name="get-your-pci-dss-solution-running-on-azure"></a>Ottenere una soluzione PCI DSS su Azure

Creare e implementare una soluzione PCI DSS nel cloud in maniera ancora più rapida con i Modelli Blueprint PCI DSS per sicurezza e conformità di Azure. Architettura di riferimento, guide per l'implementazione, mappe di controllo dell'implementazione, scritti automatizzati e molto altro. [Iniziare a usare il Modello Blueprint PCI DSS di Azure](https://aka.ms/pciblueprint)

## <a name="frequently-asked-questions"></a>Domande frequenti

**Perché sulla copertina dell'Attestato di adeguamento (AoC) è indicato "giugno 2018"?**

La data giugno 2018 sulla copertina si riferisce a quando il modello AoC è stato pubblicato. Fare riferimento alla Sezione 2 per la data della valutazione.

**Perché ci sono più Attestati di adeguamento di Azure?**

Il pacchetto Attestato di adeguamento di Azure dispone di Attestati di adeguamento che corrispondono al cloud di Azure Public, Azure Germania e Azure per gli enti pubblici. I clienti dovrebbero usare l'attestato di adeguamento corrispondente al proprio ambiente Azure.  

**Qual è la relazione tra PA DSS e PCI DSS?**

Il Payment Application Data Security Standard (PA DSS) è un set di requisiti adeguato a PCI DSS che sostituisce le Payment Application Best Practices di Visa e riunisce tutti i requisiti di adeguamento delle altre principali società emittenti di carte di pagamento. Il PA DSS aiuta i fornitori di software a sviluppare applicazioni di terze parti per archiviare, elaborare o trasmettere i dati di pagamento dei titolari di carta nell'ambito di un processo di saldo o autorizzazione di carte. I venditori al dettaglio devono usare applicazioni certificate PA DSS per l'adeguamento allo standard PCI DSS. PA DSS non si applica ad Azure.

**Cosa si intende per acquirente e Azure se ne serve?**

Un acquirente è una banca o un'altra entità che elabora le transazioni in carta di pagamento. Azure non offre l'elaborazione delle carte di pagamento come servizio, pertanto non si serve di un acquirente.

**A quali organizzazioni e commercianti si applica PCI DSS?**

PCI DSS si applica a qualsiasi azienda, a prescindere dalle dimensioni o dal numero di transazioni, che accetta, trasmette o archivia dati dei titolari di carte. Ciò significa che se un qualsiasi cliente effettua un pagamento all'azienda usando una carta di credito o debito, si applicano i requisiti PCI DSS. Le aziende vengono convalidate a uno dei quattro livelli in base al volume di transazioni totale su un periodo di 12 mesi. Il livello 1 riguarda le aziende che elaborano oltre 6 milioni di transazioni all'anno, il livello 2 da 1 milione a 6 milioni, il livello 3 da 20.000 a 1 milione e il livello 4 fino a 20.000 transazioni.

**Qual è la fase iniziale del percorso di adeguamento PCI DSS di un'organizzazione per una soluzione distribuita in Azure?**

Le informazioni rilasciate dal PCI Security Standards Council sono molto utili per scoprire di più su specifici requisiti di adeguamento. Il consiglio pubblica la [PCI DSS Quick Reference Guide](https://www.pcisecuritystandards.org/documents/PCISSC%20QRG%20August%202014%20-print.pdf) per i commercianti e le altre figure coinvolte nell'elaborazione del pagamento tramite carte. La guida spiega come lo standard PCI DSS contribuisce alla protezione dell'ambiente in cui avvengono le transazioni con carta di credito e come applicarlo.

L'adeguamento implica diversi fattori, inclusa la valutazione dei sistemi e dei processi non ospitati in Azure. I singoli requisiti variano in base a quali servizi di Azure vengono usati e come vengono impiegati nell'ambito della soluzione.

**Esistono piani per OneDrive for Business e SharePoint Online per essere conformi a PCI DSS al fuori degli Stati Uniti?**

Al momento, OneDrive for Business e SharePoint Online sono conformi a PCI DSS solo negli Stati Uniti. Microsoft valuterà requisiti e tempistiche per le aree fuori gli Stati Uniti e fornirà aggiornamenti quando e se altre regioni vengono aggiunge alla guida di orientamento.

**Cosa includono OneDrive for Business e SharePoint Online?**

Attualmente, solo i file e i documenti caricati su OneDrive for Business e SharePoint Online saranno conformi a PCI DSS.

## <a name="resources"></a>Risorse

- [PCI Security Standards Council](https://www.pcisecuritystandards.org/)
- [PCI Data Security Standard](https://www.pcisecuritystandards.org/documents/PCI_DSS_v3-1.pdf)
- [Azure PCI DSS 3.2.1 Responsibility Matrix](https://aka.ms/pciresponsibilitymatrix)
- [PCI DSS Quick Reference Guide](https://www.pcisecuritystandards.org/documents/PCISSC%20QRG%20August%202014%20-print.pdf)
- [Conformità nel Centro protezione Microsoft](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a>Scaricare il documento di informazioni di base sull'offerta

È necessario il documento di informazioni di base sull'offerta? Scarica il [PDF](https://download.microsoft.com/download/3/7/7/377F1BBC-37D5-4677-AB4A-7C01D089CA67/PCI-DSS-Compliance.pdf).
