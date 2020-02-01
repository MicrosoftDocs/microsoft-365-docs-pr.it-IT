---
title: Normative per l'esportazione degli Stati Uniti (EAR)
description: I servizi cloud Microsoft consentono ai clienti soggetti alle normative sull'esportazione degli Stati Uniti (EAR) di soddisfare i requisiti di conformità e di gestire i rischi per il controllo dell'esportazione.
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
ms.openlocfilehash: 1adf0bab35c921dd416028747b0309e5ad5f3055
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601963"
---
# <a name="us-export-administration-regulations-ear"></a>Normative per l'esportazione degli Stati Uniti (EAR)

## <a name="about-the-ear"></a>Informazioni sull'EAR

Il dipartimento del commercio degli Stati Uniti applica le normative sull'Export Administration (EAR) tramite l' [ufficio di presidenza dell'industria e della sicurezza (bis)](https://www.bis.doc.gov/). L'EAR gestisce in generale e impone controlli sull'esportazione e la riesportazione della maggior parte delle merci commerciali, del software e della tecnologia, inclusi gli elementi "a duplice utilizzo" che possono essere utilizzati sia a fini commerciali che militari e a determinati elementi di difesa.

Le linee guida BIS contengano che, quando i dati o il software vengono caricati nel cloud o trasferiti tra i nodi utente, il cliente, non il provider di servizi cloud, è l'"esportatore" che ha la responsabilità di garantire che i trasferimenti di, l'archiviazione e l'accesso a tali dati o software è conforme all'EAR.

[Secondo la BRI](https://www.bis.doc.gov/index.php/documents/regulation-docs/412-part-734-scope-of-the-export-administration-regulations/file), l' *esportazione* si riferisce al trasferimento di dati tecnici o tecnologici protetti a una destinazione straniera o alla sua liberazione a una persona straniera negli Stati Uniti (noto anche come *esportazione considerata*). L'EAR regola ampiamente:

- Esportazioni dagli Stati Uniti.
- Riesportazioni o ritrasferimenti di elementi di origine americana e di alcuni elementi di origine estera con più di una parte *de minimis* del contenuto di origine USA.
- Trasferimenti o divulgazioni a persone provenienti da altri paesi.

Gli elementi soggetti all'EAR sono disponibili nell'elenco di controllo del commercio (Lepanto) in cui a ciascun elemento è assegnato un [numero di classificazione di controllo di esportazione univoco (ECCN)](https://www.bis.doc.gov/index.php/licensing/commerce-control-list-classification/export-control-classification-number-eccn). Gli elementi non elencati nel nome utente sono designati come EAR99 e la maggior parte dei prodotti commerciali di EAR99 non richiede l'esportazione di una licenza. Tuttavia, a seconda della destinazione, dell'utente finale o dell'utilizzo finale dell'elemento, anche un elemento di EAR99 potrebbe richiedere una licenza di esportazione BIS.

La [regola finale](https://www.federalregister.gov/documents/2016/06/03/2016-12734/revisions-to-definitions-in-the-export-administration-regulations), pubblicata nel giugno 2016, ha chiarito che i requisiti per le licenze ear non si applicano anche alla trasmissione e all'archiviazione di dati tecnici e software non classificati se sono stati crittografati end-to-end con i moduli di crittografia FIPS 140-2 convalidati e non sono stati memorizzati intenzionalmente in un paese sottoposto a embargo militare o nella Federazione Russa.

## <a name="microsoft-and-the-ear"></a>Microsoft e l'EAR

Le tecnologie, i prodotti e i servizi Microsoft sono soggetti alle normative sull'amministrazione dell'esportazione degli Stati Uniti (EAR). Anche se non vi è alcuna certificazione di conformità per EAR, Microsoft Azure, Microsoft Azure Government e Microsoft Office 365 Government (ambienti di GCCHigh e DoD) offrono caratteristiche e strumenti importanti per aiutare i clienti idonei a sottoporsi all'EAR Manage Export controllare i rischi e soddisfare i requisiti di conformità.

Il dipartimento del commercio statunitense, che applica l'EAR, ha ritenuto che i clienti, non i provider di servizi cloud, come Microsoft, siano considerati esportatori dei propri dati del cliente. Anche se la maggior parte dei dati del cliente non è considerata "tecnologia" o "dati tecnici" soggetti ai controlli di esportazione EAR, i servizi cloud Microsoft in-scope sono strutturati in modo da consentire ai clienti di gestire e ridurre significativamente i rischi potenziali per il controllo delle esportazioni. Microsoft generalmente, ma non solo, raccomanda l'utilizzo dei servizi cloud governativi per i clienti idonei. Con una pianificazione appropriata, i clienti possono utilizzare gli strumenti seguenti e le proprie procedure interne per garantire la conformità completa ai controlli di esportazione degli Stati Uniti.

- **Controlli sul percorso dei dati**. I clienti hanno visibilità in cui vengono archiviati i dati e l'accesso a strumenti robusti per limitarne l'archiviazione. Possono quindi garantire che i propri dati siano archiviati negli Stati Uniti e ridurre al minimo il trasferimento di dati tecnici o tecnologici controllati al di fuori degli Stati Uniti. Inoltre, i dati dei clienti non vengono archiviati in una posizione non conforme, coerentemente ai divieti AURICOLARi in cui i dati sono "archiviati intenzionalmente": nessun Data Center di Azure si trova in uno dei 25 paesi di D:5 del gruppo o nella Federazione Russa.
- **Crittografia end-to-end**. Approfittando del porto sicuro per la crittografia end-to-end per i percorsi di archiviazione fisica specificati nell'EAR, i servizi cloud di Microsoft in-scope offrono funzionalità di crittografia che consentono di proteggere i rischi per il controllo delle esportazioni. Offrono inoltre ai clienti una [vasta gamma di opzioni per la crittografia dei dati](https://aka.ms/Azure-Encryption-Overview) in transito e a riposo e la flessibilità di scegliere tra le opzioni di crittografia.
- **Strumenti e protocolli che impediscono l'esportazione ritenuta non autorizzata**. L'utilizzo della crittografia contribuisce anche alla protezione da una potenziale esportazione ritenuta (o considerata riesportazione) sotto l'EAR, perché anche se un utente non statunitense ha accesso ai dati crittografati, non viene rilevato nulla se non sono in grado di leggere o comprendere i dati mentre sono crittografati. Pertanto, non vi è alcuna "liberazione" dei dati controllati.

## <a name="microsoft-in-scope-cloud-services"></a>Servizi cloud Microsoft inclusi nell'ambito

- [Azure e Azure per enti pubblici](https://aka.ms/AzureCompliance)
- [Amministrazione di Office 365 (GCC-High e DoD)](https://aka.ms/Office-365-Export-Controls)
- Intune

## <a name="how-to-implement"></a>Come eseguire l'implementazione

Panoramica dei controlli di esportazione degli Stati Uniti e indicazioni per i clienti che valutano gli obblighi derivanti dall'EAR.

- [Azure](https://aka.ms/Azure-Export-Controls)
- [Office 365](https://aka.ms/Office-365-Export-Controls)

## <a name="frequently-asked-questions"></a>Domande frequenti

**Cosa è necessario fare per conformarsi ai controlli Export quando si utilizzano i servizi cloud Microsoft?**

Sotto l'orecchio, quando i dati vengono caricati su un server cloud, ad esempio il cloud Microsoft, il cliente che possiede i dati, non il provider di servizi cloud, è considerato l'esportatore. Per questo motivo, il proprietario dei dati, ovvero il cliente Microsoft, deve valutare attentamente in che modo l'utilizzo del cloud Microsoft può implicare l'esportazione dei controlli e determinare se i dati da utilizzare o archiviarli potrebbero essere soggetti a controlli EAR e, in caso affermativo, quali controlli si applicano. Ulteriori informazioni sul modo in cui [Azure](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=c24c11f2-2cd4-444a-9160-19762855ad3a&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers) e [Office 365](https://query.prod.cms.rt.microsoft.com/cms/api/am/binary/RE1s5kI) Cloud Services possono aiutare i clienti a garantire la conformità completa ai controlli di esportazione degli Stati Uniti.

**Le tecnologie, i prodotti e i servizi Microsoft sono soggetti all'EAR?**

La maggior parte delle tecnologie, dei prodotti e dei servizi Microsoft:

- Non sono soggetti all'EAR e quindi non sono presenti nell'elenco di controllo di commercio e non dispongono di ECCN;
- O sono EAR99 o 5D992 mercato di massa-idoneo per l'autoclassificazione da parte di Microsoft e può essere esportato in paesi non sottoposto a embargo senza una licenza come nessuna licenza obbligatoria (NLR).

Detto questo, alcuni prodotti Microsoft sono stati assegnati a un ECCN che può o meno richiedere una licenza. Consultare l'EAR o il consulente legale per determinare il tipo di licenza appropriato e i paesi idonei ai fini dell'esportazione.

**Qual è la differenza tra l'EAR and International Traffic in Arms Regulations (ITAR)?**

I controlli primari degli Stati Uniti per l'esportazione con l'applicazione più ampia sono EAR, amministrati dal dipartimento del commercio statunitense. L'EAR è applicabile agli elementi a doppio utilizzo che dispongono sia di applicazioni commerciali che militari e ad elementi con applicazioni puramente commerciali.

Gli Stati Uniti dispongono anche di regolamenti di controllo di esportazione distinti e più specializzati, come ITAR, che disciplina gli elementi e la tecnologia più sensibili. Amministrati dal dipartimento di stato americano, impongono controlli sull'esportazione, l'importazione temporanea, la riesportazione e il trasferimento di molti elementi militari, difensivi e di intelligence (noti anche come "articoli di difesa"), compresi i dati tecnici correlati.

## <a name="resources"></a>Risorse

- [Esportazione di prodotti Microsoft: Panoramica](https://www.microsoft.com/exporting/overview.aspx)
- [Esportazione di prodotti Microsoft: domande frequenti](https://www.microsoft.com/exporting/faq.aspx)
- [Esportazione di prodotti Microsoft: ricerca prodotti](https://www.microsoft.com/exporting/exporting-information.aspx)
- [Restrizioni all'esportazione per la crittografia](https://docs.microsoft.com/windows/uwp/security/export-restrictions-on-cryptography)
- [Microsoft e FIPS 140-2](offering-fips-140-2.md)
- [Microsoft e ITAR](offering-itar.md)
- [Conformità in Microsoft Trust Center](https://www.microsoft.com/trust-center/compliance/compliance-overview)
