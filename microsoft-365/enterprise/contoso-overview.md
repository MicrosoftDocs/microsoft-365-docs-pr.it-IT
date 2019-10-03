---
title: Panoramica di Contoso Corporation
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Informazioni sulla società Contoso Corporation e sulla struttura a livelli dei suoi uffici nel mondo.
ms.openlocfilehash: ad2b3cce0e40161199513616a07ecd0a83a3e1b1
ms.sourcegitcommit: c6eab4a9f1b70e7ff0db6b2a1128a4db2591cbaf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/02/2019
ms.locfileid: "37369557"
---
# <a name="overview-of-the-contoso-corporation"></a>Panoramica di Contoso Corporation

**Riepilogo:** Informazioni sulla società Contoso Corporation e sulla struttura a livelli dei suoi uffici nel mondo.

![Contoso Corporation](./media/contoso-overview/contoso-icon.png)

Contoso Corporation è un’organizzazione multinazionale con sede a Parigi, in Francia. È un’azienda conglomerata di produzione, vendita e supporto con oltre 100.000 prodotti.

## <a name="contoso-around-the-world"></a>Contoso nel mondo

Nella figura 1 viene mostrata la sede di Parigi e gli uffici secondari e gli hub regionali nei vari continenti.

![Uffici di Contoso in tutto il mondo](./media/contoso-overview/contoso-overview-fig1.png)

**Figura 1: Uffici di Contoso in tutto il mondo**
 
Gli uffici di Contoso di tutto il mondo seguono una struttura a tre livelli.

- Sede centrale

  La sede di Contoso Corporation è un grande campus aziendale alla periferia di Parigi con decine di edifici per le strutture di amministrazione, ingegneria e produzione. Tutti i datacenter di Contoso e la presenza Internet sono ospitati nella sede di Parigi.

  La sede ha 25.000 dipendenti.

- Hub regionali

  Gli hub regionali servono una specifica area geografica del mondo con il 60% delle vendite e staff di supporto. Ogni hub regionale è connesso alla sede centrale di Parigi con un collegamento WAN con larghezza di banda elevata.

  Ogni hub regionale ha una media di 2.000 dipendenti.

- Filiali

  Gli uffici secondari ospitano l’80% del personale addetto alle vendite e al supporto tecnico e forniscono una presenza sul posto per i clienti di Contoso nelle città principali o nelle aree geografiche secondarie. Ogni ufficio secondario è collegato a un hub regionale con un collegamento WAN ad elevata larghezza di banda.

  Ogni filiale ha una media di 250 dipendenti.

Il 25% dei dipendenti di Contoso è esclusivamente mobile, con una percentuale maggiore di dipendenti solo mobile negli hub regionali e negli uffici secondari. Fornire un supporto migliore ai dipendenti che operano solo da dispositivi mobili è un obiettivo aziendale importante per Contoso.

## <a name="design-considerations-for-microsoft-365-enterprise"></a>Considerazioni sulla progettazione di Microsoft 365 Enterprise

Gli architetti IT di Contoso hanno identificato i requisiti e le considerazioni di progettazione seguenti per la distribuzione di Microsoft 365 Enterprise: 

- Più aree geografiche con requisiti di conformità alle normative locali
- Un datacenter intranet centrale nella sede centrale e server di applicazioni locali che ospitano applicazioni line of business interne
- Un’infrastruttura System Center Configuration Manager esistente
- Una combinazione di dispositivi informatici client, tra cui Windows, Mac e Linux
- Una combinazione di dispositivi mobili personali e di proprietà dell’azienda, tra cui smartphone e tablet iOS (iPhone e iPad) e Android
- Molti dipendenti remoti e che operano da dispositivi mobili
- Molti partner commerciali
- Una grande quantità di informazioni personali e dei clienti
- Una grande quantità di proprietà intellettuale di alto valore, sotto forma di specifiche di progettazione per i prodotti e di segreti commerciali

## <a name="next-step"></a>Passaggio successivo

[Informazioni](contoso-infra-needs.md) sull'infrastruttura IT locale di Contoso Corporation e su come sono state gestite le sue esigenze aziendali con Microsoft 365 Enterprise.

## <a name="see-also"></a>Vedere anche

[Guida all'implementazione](deploy-microsoft-365-enterprise.md)

[Guide dei laboratori di testing](m365-enterprise-test-lab-guides.md)



