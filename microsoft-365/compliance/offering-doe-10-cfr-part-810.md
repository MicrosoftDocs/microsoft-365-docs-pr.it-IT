---
title: US DoE 10 CFR parte 810
description: I clienti soggetti ai requisiti di controllo di esportazione di DoE 10 CFR Part 810 possono utilizzare Azure Government.
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
ms.openlocfilehash: b34babe60781858b85a3c76280c2126094442851
ms.sourcegitcommit: 7f307b4f583b602f11f69adae46d7f3bf6982c65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2020
ms.locfileid: "44066439"
---
# <a name="us-doe-10-cfr-part-810"></a>US DoE 10 CFR parte 810

## <a name="microsoft-and-doe-10-cfr-part-810"></a>Microsoft e DoE 10 CFR parte 810

Microsoft Azure Government può contribuire al supporto dei clienti soggetti ai requisiti di controllo dell'esportazione del dipartimento di energia degli Stati Uniti (DoE) 10 CFR parte 810 mediante due autorizzazioni:

- FedRAMP High provvisorio authorization to operate (P-ATO) emesso dall'organo di autorizzazione comune (JAB)
- Le autorizzazioni di livello 4 e 5 provvisorie del dipartimento della difesa (DoD) Defense Information Systems Agency

FedRAMP offre una linea di base appropriata per garantire che Azure Government offra infrastruttura di base e tecnologie di virtualizzazione e servizi quali calcolo, archiviazione e networking che sono stati creati con severi controlli NIST. Queste informazioni consentono di soddisfare i requisiti di separazione dei dati del cliente e consentono di abilitare connessioni sicure agli ambienti locali dei clienti.

Inoltre, Azure Government è un cloud della community del governo degli Stati Uniti che è fisicamente separato dal cloud di Azure. Fornisce garanzie aggiuntive relative ai requisiti specifici di screening del background da parte del governo degli Stati Uniti, compresi controlli specifici che limitano l'accesso alle informazioni e ai sistemi per i cittadini degli Stati Uniti tra il personale di Azure Operations.

## <a name="microsoft-in-scope-cloud-services"></a>Servizi cloud Microsoft inclusi

- [Amministrazione di Azure](https://aka.ms/AzureCompliance)
- Intune

## <a name="how-to-implement"></a>Come eseguire l'implementazione

- [Standard CIP di NERC & cloud computing](https://aka.ms/AzureNERC): indicazioni per le utilità elettriche e le entità registrate per la distribuzione di carichi di lavoro su Azure o Azure Government.

## <a name="about-doe-10-cfr-part-810"></a>Informazioni su DoE 10 CFR parte 810

La normativa sul controllo delle esportazioni del dipartimento di energia (DoE) del reparto statunitense [10 cfr parte 810](https://www.govinfo.gov/content/pkg/FR-2015-02-23/pdf/2015-03479.pdf) disciplina l'esportazione di tecnologie e assistenza nucleare non classificate. Aiuta a garantire che le tecnologie nucleari esportate dagli Stati Uniti vengano utilizzate solo per scopi pacifici. La parte riveduta 810 (regola finale) ha avuto effetto nel marzo 2015 ed è amministrata dall' [amministrazione nazionale per la sicurezza nucleare](https://www.energy.gov/nnsa/national-nuclear-security-administration). La sezione 810,6 indica che è necessaria una specifica autorizzazione DoE per entrambe le condizioni di assistenza e di trasferimento di tecnologie nucleari sensibili che sono "generalmente autorizzate", nonché quelle che richiedono un'autorizzazione specifica (ad esempio, per l'assistenza che coinvolge tecnologie nucleari sensibili come l'arricchimento e la produzione di acqua pesante).

## <a name="frequently-asked-questions"></a>Domande frequenti

**Le normative 10 CFR parte 110 della Commissione di regolamentazione nucleare degli Stati Uniti si applicano al governo di Azure?**

No. La [US Nuclear Regulatory Commission](https://www.nrc.gov/) (NRC) regola l' [esportazione e l'importazione](https://www.nrc.gov/about-nrc/ip/export-import.html) di impianti nucleari, apparecchiature e materiali correlati al di sotto di [10 cfr parte 110](https://www.nrc.gov/reading-rm/doc-collections/cfr/part110/). L'NRC non regola la tecnologia nucleare e l'assistenza relativa a questi elementi che rientrano nella giurisdizione DoE. Pertanto, le normative NRC 10 CFR Part 110 non si applicano a Azure Government.

**Come è possibile fornire la prova che conformi alla DoE 10 CFR parte 810?**

Se l'organizzazione sta distribuendo dati in Azure Government, è possibile fare affidamento sul sistema di amministrazione di Azure FedRAMP High P-ATO come prova che si sta gestendo i dati in modo appropriato. Tuttavia, si è responsabili di ottenere l'autorizzazione DoE dei propri sistemi, incluso l'utilizzo dei servizi cloud.

**Quali sono le mie responsabilità per la classificazione dei dati distribuiti in Azure Government?**

I clienti che distribuiscono dati in Azure government sono responsabili del proprio processo di classificazione della sicurezza. Per i dati dei clienti soggetti ai controlli di esportazione DoE, il sistema di classificazione è aumentato dai controlli di informazioni nucleari controllati non classificati (UCNI) stabiliti dalla sezione 148 del [US Atomic Energy Act](https://www.epa.gov/laws-regulations/summary-atomic-energy-act).

## <a name="resources"></a>Risorse

- [Servizi cloud di Azure e controlli di esportazione degli Stati Uniti](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=c24c11f2-2cd4-444a-9160-19762855ad3a&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)
- [Microsoft e FedRAMP](offering-fedramp.md)
- [Microsoft e DoD](offering-dod-disa-l2-l4-l5.md)
- [Cloud Microsoft per enti pubblici](https://www.microsoft.com/enterprise/government)
- [Conformità nel Centro protezione di Microsoft](https://www.microsoft.com/trust-center/compliance/compliance-overview)
