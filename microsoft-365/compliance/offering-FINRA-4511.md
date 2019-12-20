---
title: Autorità di regolamentazione del settore finanziario (FINRA) regola 4511 (c) Stati Uniti
description: Una società di valutazione indipendente ha convalidato che Azure e Office 365 può aiutare le aziende finanziarie a rispettare la regola FINRA 4511 Records conservazione e i requisiti di archiviazione immutabili.
keywords: Microsoft 365, conformità, offerte
localization_priority: None
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
titleSuffix: Microsoft Compliance
ms.openlocfilehash: 1ef6f3c9e8f6a5b3aaef40b4d0aa8eaac1c3572c
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2019
ms.locfileid: "40805009"
---
# <a name="financial-industry-regulatory-authority-finra-rule-4511c-united-states"></a>Autorità di regolamentazione del settore finanziario (FINRA) regola 4511 (c) Stati Uniti

## <a name="about-finra-rule-4511"></a>Informazioni su FINRA regola 4511

La [Financial Industry Regulatory Authority (FINRA)](https://www.finra.org/#/) è il più grande organismo indipendente che disciplina le aziende di titoli con la supervisione di oltre 4.500 società di brokeraggio negli Stati Uniti. È stato autorizzato dal Congresso degli Stati Uniti "per proteggere gli investitori dell'America facendo in modo che l'industria del broker-dealer operi in maniera equa e onesta".

Nel 2011, la Commissione per la sicurezza e lo scambio degli Stati Uniti (SEC) ha approvato l'adozione da parte di FINRA delle regole del SEC che disciplinano la conservazione di libri e record su supporti di archiviazione elettronici. La [regola 4511 (c) di FINRA](https://www.finra.org/sites/default/files/NoticeDocument/p123548.pdf) specifica che "tutti i libri e i record richiesti in base alle regole di FINRA devono essere conservati in un formato e un supporto conformi a Sea (Securities Exchange Act) Rule 17a-4".

Inoltre, la regola 4511 (c) di FINRA richiede che le aziende mantengano per un periodo di almeno sei anni i libri e i record per i quali non esiste un periodo di conservazione specificato in FINRA applicabile o in base alle regole del mare. In effetti, se i registri e i record appartengono a un account, il periodo di conservazione deve essere di sei anni dopo la chiusura dell'account. In caso contrario, il periodo di conservazione è di sei anni dopo la creazione di tali libri e record.

## <a name="microsoft-and-finra-rule-4511c"></a>Microsoft and FINRA Rule 4511 (c)

I clienti dei servizi finanziari, che rappresentano una delle industrie più fortemente regolamentate del mondo, sono soggetti a disposizioni complesse come la conservazione delle transazioni finanziarie e la comunicazione correlata in uno stato non cancellabile e non modificabile. Tra di essi vi è la regola 4511 dell'autorità di regolamentazione del settore finanziario (FINRA), che prevede requisiti severi per le entità regolamentate che scelgono di conservare i libri e i record sui supporti di archiviazione elettronici. I record archiviati devono essere antimanomissioni senza la possibilità di modificarli o eliminarli fino al termine del periodo di conservazione definito.

Lo spazio di archiviazione BLOB Microsoft Azure immutabile con il blocco dei criteri e Microsoft Office 365 con blocco di conservazione può aiutare gli istituti finanziari a soddisfare i requisiti di archiviazione immutabili della regola 4511 (c) di FINRA.

## <a name="microsoft-azure"></a>Microsoft Azure

Per valutare la conformità di Azure con la regola 4511 (c) di FINRA, Microsoft ha mantenuto una società di valutazione indipendente specializzata in Records Management and information governance, Cohasset Associates. Il report risultante, [SEC 17a-4 (f) & CFTC 1,31 (c-d) valutazione della conformità: Microsoft Azure Storage](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=19b08fd4-d276-43e8-9461-715981d0ea20&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_GRC_Assessment_Reports), include la conformità di Azure con la regola FINRA 4511 (c), che rinvia al formato e ai requisiti multimediali della regola SEC 17a-4 (f).

Cohasset ha convalidato che l' [archiviazione BLOB immutabile in Azure](https://docs.microsoft.com/azure/storage/blobs/storage-blob-immutable-storage) con l'opzione di blocco dei criteri, se utilizzata per mantenere i BLOB basati sul tempo in un formato non cancellabile e non riscrivibile (Worm), soddisfa i requisiti di archiviazione di FINRA rilevanti. Ogni BLOB (record) è protetto dall'essere modificato, sovrascritto o eliminato fino a quando non è scaduto il periodo di conservazione obbligatorio e sono state rilasciate eventuali esenzioni legali associate.

I provider di software e i partner che dispongono di carichi di lavoro sensibili possono ora basarsi sull'archiviazione BLOB immutabile di Azure come soluzione cloud One-Stop Shop per la conservazione dei record e l'archiviazione immutabile. Gli istituti finanziari possono ora creare le proprie applicazioni approfittando di queste funzionalità pur rimanendo conformi.

## <a name="microsoft-office-365"></a>Microsoft Office 365

Per valutare Office 365 compliance with FINRA Rule 4511 (c), Microsoft ha mantenuto uno studio legale leader indipendente specializzato in questioni normative, Covington & Burling, LLP. Nel report risultante, archiving in Microsoft Office 365, data retention e Rule 17a-4 Compliance, Covington ha convalidato che [Office 365 con Preservation Lock](https://docs.microsoft.com/office365/securitycompliance/retention-policies#locking-a-retention-policy) include funzionalità di archiviazione che consentono ai clienti regolamentati, inclusi i broker-dealer, di archiviare i dati in modo che li consentano di soddisfare i requisiti di FINRA per la conservazione dei record.

L'archiviazione in Office 365 consente di mantenere una vasta gamma di dati, tra cui la posta elettronica, la segreteria telefonica, i documenti condivisi, i messaggi istantanei e i dati di terze parti. In particolare, l'archiviazione in Office 365 consente ai clienti di impostare i criteri di conservazione dei messaggi globali o granulari per archiviare i dati per un periodo definito e oltre in un formato non riscrivibile e non cancellabile.

## <a name="microsoft-in-scope-cloud-services"></a>Servizi cloud Microsoft inclusi nell'ambito

- [Azure](https://gallery.technet.microsoft.com/Overview-of-Azure-c1be3942)
- [Office 365](https://aka.ms/Office365ComplianceOfferings)

## <a name="audits-reports-and-certificates"></a>Controlli, report e certificati

### <a name="azure--finra-rule-4511c"></a>Azure & regola di FINRA 4511 (c)

[SEC 17a-4 (f) & CFTC 1,31 (c-d) valutazione della conformità dello spazio di archiviazione di Azure](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=19b08fd4-d276-43e8-9461-715981d0ea20&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_GRC_Assessment_Reports)

### <a name="office-365--finra-rule-4511c"></a>Office 365 & regola di FINRA 4511 (c)

[Archiviazione in Office 365, data retention e SEC Rule 17a-4 Compliance](https://www.microsoft.com/microsoft-365/blog/2015/11/10/office-365-exchange-online-archiving-now-meets-sec-rule-17a-4-requirements/)

## <a name="how-to-implement"></a>Come eseguire l'implementazione

- **Regolamento sui servizi finanziari**: mappa di conformità dei principali principi di regolamentazione degli Stati Uniti per il cloud computing e i Microsoft Online Services. [Altre informazioni](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=5b483567-00b0-4d86-96ae-ee887dadb61c&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_Compliance_Guides)
- **Guida alla conformità e alla valutazione dei rischi**: creare un modello di governance per la valutazione dei rischi dei servizi cloud Microsoft e la notifica all'organismo di regolamentazione. [Altre informazioni](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)
- **Casi di utilizzo nel settore finanziario**: panoramiche di casi, esercitazioni e altre risorse per creare soluzioni con Azure per i servizi finanziari. [Altre informazioni](https://docs.microsoft.com/azure/industry/financial/)

## <a name="resources"></a>Risorse

- [Financial Services Compliance Program di Microsoft](https://download.microsoft.com/download/6/4/7/64707E3E-6D3E-45D0-8207-A0EA3201B4A6/Microsoft%20Cloud%20-%20Financial%20Services%20Compliance%20Program%20\(Print\).pdf)
- [Servizi cloud e servizi finanziari di Microsoft per le aziende](https://servicetrust.microsoft.com/viewpage/financialservicesoverview)
- [Financial Services Compliance Program di Azure](https://azure.microsoft.com/resources/videos/azurecon-2015-financial-services-compliance-in-azure/)
- [Strumento di valutazione del rischio cloud di Azure per i servizi finanziari](https://servicetrust.microsoft.com/ViewPage/FFIECBlueprint?command=Download&downloadType=Document&downloadId=079a1973-711a-428f-9312-9ddd290cff7b&docTab=c726d5c0-2d1e-11e8-a485-57140ec19669_PaaS)
- [Criteri di conservazione di Microsoft Office 365](https://docs.microsoft.com/office365/securitycompliance/retention-policies)
- [Blog sui servizi finanziari di Microsoft](https://techcommunity.microsoft.com/t5/Financial-Services-Blog/bg-p/FinancialServicesBlog)
- [Conformità nel Centro di protezione Microsoft](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a>Scaricare il documento di informazioni di base sull'offerta

È necessario il documento di informazioni di base sull'offerta? Scarica il [PDF](https://download.microsoft.com/download/6/B/2/6B20520B-E264-4B58-9EE2-DD6C87D9E254/FINRA-Compliance.pdf).
