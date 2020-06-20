---
title: Securities and Exchange Commission (SEC) Rule 17a-4 (f) Stati Uniti
description: Una società di valutazione indipendente ha convalidato che Azure e Office 365 possono aiutare le aziende finanziarie a soddisfare i requisiti di conservazione e di archiviazione non modificabili della regola SEC 17a-4 (f).
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
ms.openlocfilehash: 89456de1ec4ef170d85d7bd9c6b210d8bdb39f28
ms.sourcegitcommit: 51e47ca4b355436a2ad3deb154060eb1927428e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2020
ms.locfileid: "44773727"
---
# <a name="securities-and-exchange-commission-sec-rule-17a-4f-united-states"></a>Securities and Exchange Commission (SEC) Rule 17a-4 (f) Stati Uniti

## <a name="microsoft-and-sec-rule-17a-4f"></a>Regola Microsoft e SEC 17a-4 (f)

La [US Securities and Exchange Commission (sec)](https://www.sec.gov/) è un'agenzia indipendente del governo federale degli Stati Uniti e del soprintendente primario e regolatore dei mercati di titoli statunitensi. Esercita l'autorità di applicazione sulle leggi sui titoli federali, propone nuove regole di titoli e supervisiona la regolamentazione del mercato del settore dei titoli.

La SEC definisce i requisiti rigorosi ed espliciti per le entità regolamentate che scelgono di conservare libri e record su supporti di archiviazione elettronici. Ha stabilito [17 cfr 240.17 a-3](https://www.govinfo.gov/app/details/CFR-2012-title17-vol3/CFR-2012-title17-vol3-sec240-17a-3) e [17 cfr 240.17 a-4](https://www.ecfr.gov/cgi-bin/text-idx?mc=true&node=pt17.4.240&rgn=div5#se17.4.240_117a_64) per regolamentare archiviazione, compresi i periodi di conservazione, per i commercianti di titoli broker-dealers. Successivamente, il SEC ha [modificato](https://www.sec.gov/rules/interp/34-47806.htm) 17 cfr 240.17 a-4 comma (f), emettendo due rilasci interpretativi espressamente per consentire la conservazione di libri e record su supporti di archiviazione elettronici, purché siano soddisfatte determinate condizioni.

Un sistema di archiviazione elettronico soddisfa tali condizioni se impedisce l'alterazione o la cancellazione dei record per il periodo di conservazione richiesto. I periodi di conservazione variano da tre a sei anni in base ai tipi di record, con accesso immediato incaricato per i primi due anni. Inoltre, una delle versioni interpretative richiede che il sistema di archiviazione sia in grado di conservare i record oltre il periodo di conservazione stabilito dalla SEC per essere conformi a comparizioni, blocco legale o altri requisiti di questo tipo.

## <a name="microsoft-and-sec-rule-17a-4f"></a>Regola Microsoft e SEC 17a-4 (f)

I clienti dei servizi finanziari, che rappresentano una delle industrie più fortemente regolamentate del mondo, sono soggetti a disposizioni complesse come la conservazione delle transazioni finanziarie e la comunicazione correlata in uno stato non cancellabile e non modificabile. Tra le più prescrittivo è la regola 17a-4 (f) della Commissione statunitense per la sicurezza e lo scambio (SEC), che prevede requisiti severi per le entità regolamentate che scelgono di conservare libri e record su supporti di archiviazione elettronici. I record archiviati devono essere antimanomissioni senza la possibilità di modificarli o eliminarli fino al termine del periodo di conservazione definito.

Lo spazio di archiviazione BLOB Microsoft Azure immutabile con il blocco dei criteri e Microsoft Office 365 con blocco di conservazione può aiutare gli istituti finanziari a soddisfare i requisiti di archiviazione immutabili della regola SEC 17a-4 (f).

Per valutare Azure e Office 365 compliance with SEC Rule 17a-4 (f), Microsoft ha mantenuto una società di valutazione indipendente specializzata in Records Management and information governance, Cohasset Associates. Nel rapporto risultante per:

- **Azure**: [SEC 17a-4 (f) valutazione della conformità: Microsoft Azure Storage](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=19b08fd4-d276-43e8-9461-715981d0ea20&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_GRC_Assessment_Reports), Cohasset ha convalidato che l' [archiviazione BLOB immutabile di Azure](https://docs.microsoft.com/azure/storage/blobs/storage-blob-immutable-storage) con l'opzione di blocco dei criteri, quando viene utilizzata per mantenere i BLOB basati sul tempo in un formato non cancellabile e non riscrivibile (Worm), soddisfa i requisiti di archiviazione immutabili della regola sec. Ogni BLOB (record) è protetto dall'essere modificato, sovrascritto o eliminato fino a quando non è scaduto il periodo di conservazione obbligatorio e sono state rilasciate eventuali esenzioni legali associate. I provider di software e i partner che dispongono di carichi di lavoro sensibili possono ora basarsi sull'archiviazione BLOB immutabile di Azure come soluzione cloud di onestop-Shop per la conservazione dei record e l'archiviazione immutabile. Gli istituti finanziari possono ora creare le proprie applicazioni approfittando di queste funzionalità pur rimanendo conformi.
- **Office 365**: [utilizzare Exchange Online per conformarsi a SEC 17a-4](https://docs.microsoft.com/office365/securitycompliance/use-exchange-online-to-comply-with-sec-rule-17a-4), Cohasset ha convalidato [che Office 365 con conservazione Lock](retention-policies.md) include funzionalità di archiviazione che consentono ai clienti regolamentati, inclusi i broker-dealer, di archiviare i dati in modo da aiutarli a conformarsi ai requisiti sec per la conservazione dei record. I criteri di conservazione in Office 365 consentono di mantenere una vasta gamma di dati, tra cui la posta elettronica, la segreteria telefonica, i documenti condivisi, i messaggi istantanei e i dati di terze parti. In particolare, l'archiviazione in Office 365 consente ai clienti di impostare criteri di conservazione dei messaggi globali o granulari per archiviare i dati per un periodo definito e oltre in un formato non riscrivibile e non cancellabile.

## <a name="microsoft-in-scope-cloud-services"></a>Servizi cloud Microsoft inclusi nell'ambito

- [Azure](https://gallery.technet.microsoft.com/Overview-of-Azure-c1be3942)
- [Office 365](https://aka.ms/Office365ComplianceOfferings)

## <a name="audits-reports-and-certificates"></a>Controlli, report e certificati

### <a name="azure--sec-rule-17"></a>& di Azure secondo la regola 17

[SEC 17a-4 (f) & CFTC 1,31 (c-d) valutazione della conformità dello spazio di archiviazione di Azure](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=19b08fd4-d276-43e8-9461-715981d0ea20&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_GRC_Assessment_Reports)

### <a name="office-365--sec-rule-17"></a>Office 365 & SEC regola 17

[SEC 17a-4 (f) valutazione di conformità: Microsoft Security & Compliance Center with Exchange Online](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=9fa8349d-a0c9-47d9-93ad-472aa0fa44ec&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

## <a name="how-to-implement"></a>Come eseguire l'implementazione

### <a name="financial-services-regulation"></a>Regolamentazione dei servizi finanziari

Mappa di conformità dei principali principi di regolamentazione degli Stati Uniti per cloud computing e Microsoft Online Services. [Altre informazioni](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=5b483567-00b0-4d86-96ae-ee887dadb61c&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_Compliance_Guides)

### <a name="risk-assessment--compliance-guide"></a>Guida alla conformità alla valutazione dei rischi &

Creare un modello di governance per la valutazione dei rischi per i servizi cloud Microsoft e la notifica del regolatore. [Altre informazioni](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

### <a name="financial-use-cases"></a>Casi di utilizzo finanziario

Utilizzare le anteprime dei casi, le esercitazioni e altre risorse per creare soluzioni di Azure per i servizi finanziari. [Altre informazioni](https://docs.microsoft.com/azure/industry/financial/)

## <a name="resources"></a>Risorse

- [Archiviazione in Microsoft Office 365, conservazione dei dati e regola 17a-4](https://www.microsoft.com/microsoft-365/blog/2015/11/10/office-365-exchange-online-archiving-now-meets-sec-rule-17a-4-requirements/)
- [Conformità servizi finanziari Microsoft](https://download.microsoft.com/download/6/4/7/64707E3E-6D3E-45D0-8207-A0EA3201B4A6/Microsoft%20Cloud%20-%20Financial%20Services%20Compliance%20Program%20\(Print\).pdf)
- [Programma di conformità Microsoft Business Cloud Services e servizi finanziari](https://servicetrust.microsoft.com/viewpage/financialservicesoverview)
- [Azure Financial Services Compliance Program](https://azure.microsoft.com/resources/videos/azurecon-2015-financial-services-compliance-in-azure/)
- [Strumento di valutazione del rischio cloud di Azure per i servizi finanziari](https://servicetrust.microsoft.com/ViewPage/FFIECBlueprint?command=Download&downloadType=Document&downloadId=079a1973-711a-428f-9312-9ddd290cff7b&docTab=c726d5c0-2d1e-11e8-a485-57140ec19669_PaaS)
- [Criteri di conservazione di Microsoft Office 365](https://docs.microsoft.com/office365/securitycompliance/retention-policies)
- [Blog sui servizi finanziari di Microsoft](https://techcommunity.microsoft.com/t5/Financial-Services-Blog/bg-p/FinancialServicesBlog)
- [Conformità nel Centro protezione Microsoft](https://www.microsoft.com/trust-center/compliance/compliance-overview)
