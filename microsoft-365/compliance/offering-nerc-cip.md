---
title: North American Electric Reliability Corporation (NERC)
description: Azure e Azure per enti pubblici sono idonei per gli enti registrati che distribuiscono certi carichi di lavoro nel cloud seguendo i CIP standard NERC.
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
ms.openlocfilehash: f4394a66242a981ab179b07f45e82132f68968d7
ms.sourcegitcommit: 888b9355ef7b933c55ca6c18639c12426ff3fbde
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2020
ms.locfileid: "48305356"
---
# <a name="north-american-electric-reliability-corporation-nerc"></a>North American Electric Reliability Corporation (NERC)

## <a name="about-the-nerc"></a>Informazioni sulla NERC

La [North America Electric Reliability Corporation](https://www.nerc.com/) (NERC) è un'ente di certificazione no profit che ha l'obiettivo di garantire l'affidabilità del sistema elettrico nordamericano. La NERC è soggetta alla supervisione da parte della Federal Energy Regulatory Commission (FERC) statunitense e di autorità governative canadesi. Nel 2006, in accordo a quanto stabilito dall'Energy Policy Act del 2005 (US Public Law 109-58), tale commissione ha designato la NERC come Electric Reliability Organization (ERO), dandole così carattere di ufficialità. La NERC si occupa dello sviluppo e applicazione di criteri di affidabilità noti come [Critical Infrastructure Protection (CIP) standard](https://www.nerc.com/pa/Stand/Pages/CIPStandards.aspx), ovvero per la protezione di infrastrutture fondamentali.

## <a name="microsoft-and-the-nerc-cip-standard"></a>Microsoft e i CIP standard NERC

La North America Electric Reliability Corporation (NERC) è un'ente di certificazione no profit che ha l'obiettivo di garantire l'affidabilità del sistema di produzione di energia elettrica nordamericano. La NERC è soggetta alla supervisione da parte della Federal Energy Regulatory Commission (FERC) statunitense e di autorità governative canadesi. Nel 2006, in accordo a quanto stabilito dall'Energy Policy Act del 2005 (US Public Law 109-58), tale commissione ha designato la NERC come Electric Reliability Organization (ERO), dandole così carattere di ufficialità. La NERC si occupa dello sviluppo e applicazione di criteri di affidabilità noti come [Critical Infrastructure Protection (CIP) standard](https://www.nerc.com/pa/Stand/Pages/CIPStandards.aspx), ovvero per la protezione di infrastrutture fondamentali.

Ciascun proprietario, operatore e utente del sistema di produzione di energia elettrica deve [conformarsi ai CIP standard NERC](https://www.nerc.com/pa/comp/Pages/default.aspx). È richiesto che tali entità si registrino alla NERC. I provider di servizi cloud e terze parti fornitrici non sono soggetti ai CIP standard NERC, tuttavia sono previsti certi obiettivi da tenere in considerazione qualora le [entità registrate](https://www.nerc.com/pa/comp/Pages/Registration.aspx) si avvalgano di fornitori per le loro operazioni nell'ambito del sistema di produzione di elettricità (BES, Bulk Electric System). I clienti Microsoft che gestiscono sistemi BES sono totalmente responsabili del rispetto dei CIP standard NERC da parte della propria organizzazione. Né Microsoft Azure né Microsoft Azure per enti pubblici costituiscono un BES o un BES Cyber Asset.

Come indicato dalla NERC nell'attuale corpus dei [CIP standard](https://www.nerc.com/pa/Stand/Reliability%20Standards%20Complete%20Set/RSCompleteSet.pdf) e del [glossario dei termini](https://www.nerc.com/pa/Stand/Glossary%20of%20Terms/Glossary_of_Terms.pdf) NERC, i BES Cyber Asset eseguono funzioni di monitoraggio o controllo del BES in tempo reale, influenzando l'affidabilità del funzionamento del BES stesso entro 15 minuti da una loro eventuale compromissione. Per ospitare nel cloud computing i BES Cyber Asset e i Protected Cyber Asset in modo adeguato, le attuali definizioni fornite dai CIP standard NERC [hanno bisogno di essere riviste](https://www.nerc.com/pa/Stand/Pages/Project%202016-02%20Modifications%20to%20CIP%20Standards.aspx). Tuttavia, esistono molti carichi di lavoro che trattano dati relativi ai CIP, ma che non rientrano nell'ambito della regola dei 15 minuti; per esempio, la vasta categoria BCSI (BES Cyber System Information).

Azure e Azure per enti pubblici sono idonei per quelle entità registrate che distribuiscono certi carichi di lavoro seguendo i CIP standard NERC, inclusi i carichi di lavoro BCSI. Microsoft rende disponibili i seguenti documenti a tutte le entità registrate, interessate alla distribuzione di dati e carichi di lavoro in Azure o Azure per enti pubblici nel rispetto degli obblighi di conformità ai CIP standard NERC:

- Il white paper [CIP standard NERC e cloud computing](https://aka.ms/AzureNERC), che include considerazioni in materia di conformità a tali requisiti basandosi su controlli effettuati da terzi e applicabili ai provider di servizi cloud, come ad esempio gli audit di FedRAMP. Il documento tratta del controllo dei precedenti per le risorse impegnate in operazioni relative al cloud, rispondendo alle più domande comuni in materia di isolamento logico e multi-tenancy, di interesse per le entità registrate. Vi trova spazio anche un paragone fra la sicurezza per la distribuzione locale piuttosto che cloud.
- La [Guida all'implementazione cloud per controlli NERC](https://aka.ms/AzureNERCGuide) è un documento orientativo che fornisce la verifica del mapping tra i requisiti dei CIP standard NERC correnti e il set di controllo [NIST SP 800-53 Rev 4](https://nvd.nist.gov/800-53/Rev4), che costituisce la base di analisi per FedRAMP. È stato concepito come una guida tecnica pratica per avvicinare le entità registrate ai requisiti di conformità CIP NERC per le risorse distribuite nel cloud. Il documento contiene i fogli di lavoro precompilati [Reliability Standard Audit Worksheets (RSAWs)](https://www.nerc.com/pa/comp/Pages/Reliability-Standard-Audit-Worksheets-\(RSAWs\).aspx) per le verifiche di affidabilità, i quali spiegano l'approccio di Azure nel controllo dei requisiti CIP NERC, fornendo inoltre alle entità registrate indicazioni su come utilizzare i servizi di Azure per implementare i controlli di cui devono occuparsi.

La divisione ERO Enterprise della NERC [ha rilasciato](https://www.nerc.com/pa/comp/guidance/Pages/default.aspx) una [guida pratica](https://www.nerc.com/pa/comp/guidance/CMEPPracticeGuidesDL/ERO%20Enterprise%20CMEP%20Practice%20Guide%20_%20BCSI%20-%20v0.2%20CLEAN.pdf) al CMEP (Compliance Monitoring and Enforcement Program), il programma di monitoraggio e applicazione della conformità, in modo da fornire al proprio personale indicazioni utili alla valutazione del processo di autorizzazione di un'entità registrata per l'accesso alle posizioni di archiviazione di BCSI designate e per eventuali controlli di accesso implementati dalla stessa. Inoltre, la NERC ha esaminato i dettagli dell'implementazione del controllo di Azure e le prove di controllo di FedRAMP relative agli standard CIP-004-6 e CIP-011-2 applicabili a BCSI. Considerando la guida pratica rilasciata dall'ERO e la revisione dei controlli di FedRAMP con la finalità di garantire che le entità registrate criptino i dati, non risultano necessarie ulteriori indicazioni o chiarimenti circa la distribuzione nel cloud dei carichi di lavoro BCSI e di carichi associati. Tuttavia, in ultima analisi, le entità registrate sono responsabili della propria conformità ai CIP standard NERC sulla base dei fatti e circostanze a loro noti. Si invitano le entità registrate a esaminare la [Guida all'implementazione cloud per controlli NERC](https://aka.ms/AzureNERCGuide), per assistenza nella documentazione dei propri processi e prove volti ad autorizzare l'accesso elettronico alle posizioni di archiviazione BCSI, inclusa la gestione della chiave usata per la crittografia di BCSI in Azure e Azure per enti pubblici.

## <a name="microsoft-in-scope-cloud-services"></a>Servizi cloud Microsoft inclusi nell'ambito

- [Azure e Azure per enti pubblici](https://aka.ms/AzureCompliance)

## <a name="audits-reports-and-certificates"></a>Controlli, report e certificati

Microsoft è tenuta a ricertificare i suoi servizi cloud ogni anno per mantenere le proprie autorizzazioni P-ATO e ATO. A tal fine, Microsoft deve monitorare e valutare costantemente i propri controlli di sicurezza e dimostrare il mantenimento della conformità.

- [Autorizzazioni dei servizi cloud Microsoft](https://marketplace.fedramp.gov/?sort=productName&productNameSearch=azure#/product/azure-government)
- [Report Microsoft sui controlli di FedRAMP](https://aka.ms/MicrosoftFedRAMPAuditDocuments)

## <a name="how-to-implement"></a>Come eseguire l'implementazione

### <a name="nerc-cip-standards-and-cloud-computing"></a>CIP standard NERC e cloud computing

Tratta della conformità delle entità registrate considerando l'adozione di sistemi cloud per i carichi di lavoro soggetti ai CIP standard NERC.

[Ulteriori informazioni](https://aka.ms/AzureNERC)

### <a name="cloud-implementation-guide-for-nerc-audits"></a>Guida all'implementazione cloud per controlli NERC

Indicazioni tecniche per aiutare le entità registrate con i controlli NERC sulle risorse distribuite in Azure o Azure per enti pubblici. 

[Ulteriori informazioni](https://aka.ms/AzureNERCGuide)

## <a name="frequently-asked-questions"></a>Domande frequenti

**Su chi ricade la responsabilità del rispetto dei CIP standard NERC?**

Ciascun proprietario, operatore e utente del sistema di produzione di energia elettrica deve [conformarsi ai CIP standard NERC](https://www.nerc.com/pa/comp/Pages/default.aspx). È richiesto che tali entità si registrino alla NERC. I provider di servizi cloud e terze parti fornitrici non sono soggetti ai CIP standard NERC, tuttavia sono previsti certi obiettivi da tenere in considerazione qualora le [entità registrate](https://www.nerc.com/pa/comp/Pages/Registration.aspx) si avvalgano di fornitori per le loro operazioni nell'ambito del sistema di produzione di elettricità (BES, Bulk Electric System). I clienti Microsoft che gestiscono sistemi BES sono totalmente responsabili del rispetto dei CIP standard NERC da parte della propria organizzazione. Né Azure né Azure per enti pubblici costituiscono un BES o un BES Cyber Asset.

Per valutare l'idoneità di Azure e Azure per enti pubblici a trattare i dati e i carichi di lavoro soggetti ai CIP standard NERC, si invita le entità registrate a consultare i propri responsabili della conformità e i revisori della NERC. Si invita inoltre a leggere la [Guida all'implementazione cloud per controlli NERC](https://aka.ms/AzureNERCGuide), per assistenza nella documentazione dei propri processi e delle prove per le risorse distribuite nel cloud.

**Quali carichi di lavoro possono distribuire su Azure e Azure per enti pubblici le entità registrate?**

I [CIP standard](https://www.nerc.com/pa/Stand/Reliability%20Standards%20Complete%20Set/RSCompleteSet.pdf) NERC e il [glossario dei termini](https://www.nerc.com/pa/Stand/Glossary%20of%20Terms/Glossary_of_Terms.pdf) afferma che i BES Cyber Asset eseguono funzioni di monitoraggio o controllo del BES in tempo reale e che, nel caso di una loro compromissione, nel giro di 15 minuti vanno a influenzare l'affidabilità del funzionamento del BES stesso. Per ospitare nel cloud computing i BES Cyber Asset e i Protected Cyber Asset in modo adeguato, le attuali definizioni fornite dai CIP standard NERC [hanno bisogno di essere riviste](https://www.nerc.com/pa/Stand/Pages/Project%202016-02%20Modifications%20to%20CIP%20Standards.aspx). Tuttavia, esistono molti carichi di lavoro che trattano dati relativi ai CIP, ma che non rientrano nell'ambito della regola dei 15 minuti; per esempio, la vasta categoria BCSI (BES Cyber System Information).

La divisione ERO Enterprise della NERC [ha rilasciato](https://www.nerc.com/pa/comp/guidance/Pages/default.aspx) una [guida pratica](https://www.nerc.com/pa/comp/guidance/CMEPPracticeGuidesDL/ERO%20Enterprise%20CMEP%20Practice%20Guide%20_%20BCSI%20-%20v0.2%20CLEAN.pdf) al CMEP (Compliance Monitoring and Enforcement Program), il programma di monitoraggio e applicazione della conformità, in modo da fornire al proprio personale indicazioni utili alla valutazione del processo di autorizzazione di un'entità registrata per l'accesso alle posizioni di archiviazione di BCSI designate e per eventuali controlli di accesso implementati dalla stessa. Inoltre, la NERC ha esaminato i dettagli dell'implementazione del controllo di Azure e le prove di controllo di FedRAMP relative agli standard CIP-004-6 e CIP-011-2 applicabili a BCSI. Considerando la guida pratica rilasciata dall'ERO e la revisione dei controlli di FedRAMP con la finalità di garantire che le entità registrate criptino i dati, non risultano necessarie ulteriori indicazioni o chiarimenti per la distribuzione nel cloud dei carichi di lavoro BCSI e dei carichi associati. Tuttavia, in ultima analisi, le entità registrate sono responsabili della propria conformità ai CIP standard NERC sulla base dei fatti e circostanze a loro noti.

## <a name="use-microsoft-compliance-manager-to-assess-your-risk"></a>Usare Microsoft Compliance Manager per valutare i rischi

[Microsoft Compliance Manager](compliance-manager.md) è una funzionalità nel [Centro conformità Microsoft 365](microsoft-365-compliance-center.md) utile per comprendere lo stato di conformità dell'organizzazione e intraprendere azioni per ridurre i rischi. Compliance Manager offre un modello premium per creare una valutazione per questa normativa. Individuare il modello nella pagina **modelli di valutazioni** in Compliance Manager. Informazioni su come [creare valutazioni in Compliance Manager](compliance-manager-assessments.md).

## <a name="resources"></a>Risorse

- [Guida alla conformità NERC](https://www.nerc.com/pa/comp/guidance/)
- [NERC: Gestione dei rischi della catena di fornitura per la cybersecurity](https://www.nerc.com/pa/Stand/Pages/CIP0131RI.aspx)
- [Conformità NERC e sua applicazione](https://www.nerc.com/pa/comp/Pages/default.aspx)
- [Organizzazione e certificazione NERC](https://www.nerc.com/pa/comp/Pages/Registration.aspx)
- [Microsoft e FedRAMP](offering-fedramp.md)
- [Attestazione](offering-csa-star-attestation.md) e [certificazione](offering-csa-star-certification.md) di Microsoft e CSA
- [Microsoft e i report SOC 2](offering-soc.md)
- [Conformità nel Centro di protezione Microsoft](https://www.microsoft.com/trust-center/compliance/compliance-overview)
