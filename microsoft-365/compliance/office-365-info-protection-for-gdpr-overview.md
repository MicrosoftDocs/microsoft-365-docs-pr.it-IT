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
# <a name="overview-of-office-365-information-protection-for-gdpr"></a><span data-ttu-id="d9537-104">Panoramica di Office 365 Information Protection per RGPD
</span><span class="sxs-lookup"><span data-stu-id="d9537-104">Overview of Office 365 Information Protection for GDPR</span></span>

<span data-ttu-id="d9537-p102">Questa soluzione mostra come proteggere i dati riservati archiviati nei servizi di Office 365. Include suggerimenti prescrittivi per individuare, classificare, proteggere e monitorare i dati personali. Questa soluzione utilizza l'RGPD come esempio, ma è possibile applicare lo stesso processo per raggiungere la conformità con molti altri regolamenti.</span><span class="sxs-lookup"><span data-stu-id="d9537-p102">This solution demonstrates how to protect sensitive data that is stored in Office 365 services. It includes prescriptive recommendations for discovering, classifying, protecting, and monitoring personal data. This solution uses General Data Protection Regulation (GDPR) as an example, but you can apply the same process to achieve compliance with many other regulations.</span></span>

<span data-ttu-id="d9537-p103">L'RGPD regola la raccolta, l'archiviazione, l'elaborazione e la condivisione dei dati personali. I dati personali sono definiti in modo molto ampio nell'RGPD, come qualsiasi dato relativo a una persona fisica identificata o identificabile residente nell'Unione Europea.</span><span class="sxs-lookup"><span data-stu-id="d9537-p103">GDPR regulates the collection, storage, processing, and sharing of personal data. Personal data is defined very broadly under the GDPR as any data that relates to an identified or identifiable natural person that is a resident of the European Union (EU).</span></span>

<span data-ttu-id="d9537-110">Articolo 4 - Definizioni</span><span class="sxs-lookup"><span data-stu-id="d9537-110">Article 4 – Definitions</span></span>

> <span data-ttu-id="d9537-111">con "dati personali" si intende qualsiasi informazione relativa a una persona fisica identificata o identificabile ("soggetto dei dati"); una persona fisica identificabile è una persona che può essere identificata, direttamente o indirettamente, in particolare in riferimento a un identificatore come un nome, un numero di identificazione, dati sulla posizione, un identificatore online o a uno o più fattori specifici per l'identità fisica, psicologica, genetica, mentale, economica, culturale o sociale della persona fisica;</span><span class="sxs-lookup"><span data-stu-id="d9537-111">‘personal data’ means any information relating to an identified or identifiable natural person (‘data subject’); an identifiable natural person is one who can be identified, directly or indirectly, in particular by reference to an identifier such as a name, an identification number, location data, an online identifier or to one or more factors specific to the physical, physiological, genetic, mental, economic, cultural or social identity of that natural person;</span></span>

<span data-ttu-id="d9537-p104">Questa soluzione vuole aiutare le organizzazioni a individuare e proteggere i dati personali in Office 365 che potrebbero essere soggetti all'RGPD. Non offre o rappresenta una conferma della conformità all'RGPD. Le organizzazioni sono tenute a verificare autonomamente la conformità all'RGPD mediante i propri esperti legali e di conformità o avvalendosi di professionisti esterni specializzati in conformità.
</span><span class="sxs-lookup"><span data-stu-id="d9537-p104">This solution is intended to help organizations discover and protect personal data in Office 365 that might be subject to the GDPR. It is not offered as a GDPR compliance attestation. Organizations are responsible for ensuring their own GDPR compliance and are advised to consult their legal and compliance teams or to seek guidance and advice from third parties that specialize in compliance.</span></span>

<span data-ttu-id="d9537-115">[GDPR Assessment](https://www.microsoft.com/cyberassessment/en/gdpr/uso365?ls=Email&mkt_tok=eyJpIjoiTTJFeE5USXlOR1EwTWpJMiIsInQiOiJQTmdCYWR5NTlOd3JLWHZlb2NzNldKclQ4ZVBzVmhGeUhoUlFcL1pvSDIyXC9Ka05iTUR1aGpxT0YxQ0FUeGNDOUlkbWZLM1U4SUZWZmEyaGF6XC9ueUxkTHJzZnB3VDRMZlhPdkR4MzRLWkF5ckRNdWwxUkgzXC9yRU8yNkttSHhTb3VpZjNyVlJrNm9TTVZRYU5HR240a0FRPT0ifQ%3D%3D) è uno strumento rapido, online di autovalutazione che consente alle autorizzazioni di verificare gratuitamente il proprio livello di preparazione alla conformità con l'RGPD.</span><span class="sxs-lookup"><span data-stu-id="d9537-115">GDPR Assessment is a quick, online self-evaluation tool available at no cost to help your organization review its overall level of readiness to comply with the GDPR ().</span></span>

## <a name="assess-and-manage-your-compliance-risk"></a><span data-ttu-id="d9537-116">Verificare e gestire il rischio di conformità</span><span class="sxs-lookup"><span data-stu-id="d9537-116">Assess and manage your compliance risk</span></span>

<span data-ttu-id="d9537-p105">Il primo passo per la conformità RGPD consiste nel valutare se tale regolamento è applicabile all'organizzazione e, in tal caso, in quale misura. L'analisi include la comprensione dei dati elaborati dall'organizzazione e dove questi si trovano.</span><span class="sxs-lookup"><span data-stu-id="d9537-p105">The first step towards GDPR compliance is to assess whether the GDPR applies to your organization, and, if so, to what extent. This analysis includes understanding the data your organization processes and where it resides.</span></span>

### <a name="step-1--use-compliance-score-to-view-the-regulation-requirements-and-track-your-progress"></a><span data-ttu-id="d9537-119">Fase 1 - Usare il punteggio di conformità per verificare i requisiti normativi e tenere traccia dello stato di avanzamento</span><span class="sxs-lookup"><span data-stu-id="d9537-119">Step 1 — Use Compliance Manager to view the regulation requirements and track your progress</span></span>

<span data-ttu-id="d9537-120">Il punteggio di conformità offre strumenti per tenere traccia, implementare e gestire i controlli per consentire all'organizzazione di raggiungere la conformità con diversi standard, tra cui GDPR.</span><span class="sxs-lookup"><span data-stu-id="d9537-120">Compliance Manager provides tools to track, implement, and manage the auditing controls to help your organization reach compliance against various standards, including GDPR.</span></span>

![Usare il punteggio di conformità e Compliance Manager per verificare i requisiti normativi e tenere traccia dello stato di avanzamento](Media/Overview-image1.png)

<span data-ttu-id="d9537-122">Per ulteriori informazioni, vedere [punteggio di conformità](compliance-score.md).</span><span class="sxs-lookup"><span data-stu-id="d9537-122">For more information, see the [Understanding the Compliance Score](compliance-score.md) section.</span></span>

### <a name="step-2--use-content-search-and-sensitive-information-types-to-find-personal-data"></a><span data-ttu-id="d9537-123">Fase 2 - Usare Ricerca contenuto e le tipologie di informazioni sensibili per trovare i dati personali
</span><span class="sxs-lookup"><span data-stu-id="d9537-123">Step 2 — Use Content Search and sensitive information types to find personal data</span></span> 

<span data-ttu-id="d9537-p106">Individuare i dati personali nel proprio ambiente soggetti all'RGPD. Usare Ricerca contenuto insieme alle tipologie di informazioni sensibili per:
</span><span class="sxs-lookup"><span data-stu-id="d9537-p106">Discover personal data in your environment that is subject to the GDPR. Use Content Search together with sensitive information types to:</span></span>

- <span data-ttu-id="d9537-126">Trovare e indicare dove si trovano i dati personali.</span><span class="sxs-lookup"><span data-stu-id="d9537-126">Find and report on where personal data resides.</span></span>

- <span data-ttu-id="d9537-127">Ottimizzare i tipi di dati riservati e altre query per trovare tutti i dati personali nel proprio ambiente.</span><span class="sxs-lookup"><span data-stu-id="d9537-127">Optimize sensitive data types and other queries to find all personal data in your environment.</span></span>

![<span data-ttu-id="d9537-128"> Usare Ricerca contenuto e le tipologie di informazioni sensibili per trovare i dati personali
</span><span class="sxs-lookup"><span data-stu-id="d9537-128">Use Content Search and sensitive info types to find personal data</span></span>](Media/Overview-image2.png)

<span data-ttu-id="d9537-p107">Le tipologie di informazioni sensibili permettono di riconoscere in modo automatico informazioni specifiche come i numeri di previdenza sociale e di carta di credito. Questo articolo include una serie di tipologie da usare come punto di partenza. Molte altre tipologie di informazioni sensibili saranno presto disponibili per i dati personali nei paesi dell'Unione Europea.
</span><span class="sxs-lookup"><span data-stu-id="d9537-p107">Sensitive information types define how the automated process recognizes specific information types such as health service numbers and credit card numbers. This article includes a set you can use as a starting point. Many more sensitive information types are coming soon for personal data in EU countries.</span></span>

<span data-ttu-id="d9537-132">Per ulteriori informazioni, vedere [Cercare e trovare i dati personali](search-for-and-find-personal-data.md).</span><span class="sxs-lookup"><span data-stu-id="d9537-132">For more information, see [Search for and find personal data](search-for-and-find-personal-data.md).</span></span> 

## <a name="classify-protect-and-monitor-personal-data-in-office-365-and-other-saas-apps"></a><span data-ttu-id="d9537-133">Classificare, proteggere e monitorare i dati personali in Office 365 e altre applicazioni SaaS</span><span class="sxs-lookup"><span data-stu-id="d9537-133">Classify, protect, and monitor personal data in Office 365 and other SaaS apps</span></span>

<span data-ttu-id="d9537-134">Alcune funzionalità utilizzate per la protezione delle informazioni in Office 365 possono anche essere usate per proteggere i dati riservati nelle altre applicazioni SaaS.</span><span class="sxs-lookup"><span data-stu-id="d9537-134">Some of the capabilities used for information protection in Office 365 can also be used to protect sensitive data in other SaaS applications.</span></span>

![Classificare, proteggere e monitorare i dati personali](Media/Overview-image3.png)

<span data-ttu-id="d9537-136">L'illustrazione seguente viene descritta ulteriormente nella sezione (dalla fase 3 alla fase 5).
</span><span class="sxs-lookup"><span data-stu-id="d9537-136">This illustration is described by the rest this section (steps 3-5).</span></span>

### <a name="step-3--decide-if-you-want-to-use-labels-in-addition-to-sensitive-information-types"></a><span data-ttu-id="d9537-137">Fase 3 - Decidere se usare anche le etichette, oltre alle tipologie di informazioni sensibili
</span><span class="sxs-lookup"><span data-stu-id="d9537-137">Step 3 — Decide if you want to use labels in addition to sensitive information types</span></span>

<span data-ttu-id="d9537-p108">Le tipologie di informazioni sensibili permettono di classificare i dati. Vedere [Definire uno schema di classificazione per i dati personali](architect-a-classification-schema-for-personal-data.md), per decidere se usare anche le etichette. Per applicare le etichette, vedere [Applicare le etichette ai dati personali in Office 365](apply-labels-to-personal-data-in-office-365.md).
</span><span class="sxs-lookup"><span data-stu-id="d9537-p108">Sensitive information types are a form of classification. See [Architect a classification schema for personal data](architect-a-classification-schema-for-personal-data.md), to decide if you also want to implement labels. To apply labels, see [Apply labels to personal data in Office 365](apply-labels-to-personal-data-in-office-365.md).</span></span>

<span data-ttu-id="d9537-p109">La figura mostra l'uso delle etichette e delle tipologie di informazioni sensibili in Office 365. Prossimamente sarà possibile utilizzarli anche con Cloud App Security per trovare i dati sensibili nelle altre applicazioni SaaS, ad esempio Box e Salesforce.
</span><span class="sxs-lookup"><span data-stu-id="d9537-p109">In the illustration, sensitive information types and labels work across Office 365. Coming soon, you can use these with Cloud App Security to find sensitive data in other SaaS apps, such as Box and Salesforce.</span></span>

### <a name="step-4--protect-personal-data-in-office-365"></a><span data-ttu-id="d9537-143">Fase 4 - Proteggere i dati personali in Office 365
</span><span class="sxs-lookup"><span data-stu-id="d9537-143">Step 4 — Protect personal data in Office 365</span></span> 

<span data-ttu-id="d9537-p110">La protezione dei dati personali inizia con la prevenzione della perdita dei dati di Office 365. Esistono molte altre funzionalità consigliate per proteggere l'accesso ai dati personali, tra cui Crittografia dei messaggi di Office 365 per la posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="d9537-p110">Protection for personal data starts with Office 365 data loss prevention. There are several other capabilities recommended for protecting access to personal data, including Office 365 Message Encryption for email.</span></span>

<span data-ttu-id="d9537-146">Queste protezioni possono essere applicate a set di dati specifici:</span><span class="sxs-lookup"><span data-stu-id="d9537-146">These protections can be targeted to specific data sets:</span></span>

- <span data-ttu-id="d9537-147">Autorizzazioni a livello di sito e raccolta</span><span class="sxs-lookup"><span data-stu-id="d9537-147">Site and library-level permissions</span></span>

- <span data-ttu-id="d9537-148">Criteri di condivisione esterna a livello di sito</span><span class="sxs-lookup"><span data-stu-id="d9537-148">Site-level external sharing policies</span></span>

- <span data-ttu-id="d9537-149">Criteri di accesso ai dispositivi a livello di sito
</span><span class="sxs-lookup"><span data-stu-id="d9537-149">Site-level device access policies</span></span>

<span data-ttu-id="d9537-150">La protezione per l'accesso a Office 365 e altri servizi cloud include:</span><span class="sxs-lookup"><span data-stu-id="d9537-150">Protection for access to Office 365 and other cloud services include:</span></span>

- <span data-ttu-id="d9537-151">Protezione dell'accesso a identità e dispositivi in Enterprise Mobility + Security (EMS)</span><span class="sxs-lookup"><span data-stu-id="d9537-151">Identity and device access protection in Enterprise Mobility + Security (EMS)</span></span>

- <span data-ttu-id="d9537-152">Gestione accessi con privilegi</span><span class="sxs-lookup"><span data-stu-id="d9537-152">Privileged access management</span></span>

- <span data-ttu-id="d9537-153">Funzionalità di sicurezza di Windows 10</span><span class="sxs-lookup"><span data-stu-id="d9537-153">Windows 10 security capabilities</span></span>

<span data-ttu-id="d9537-154">Per ulteriori informazioni sull'applicazione della protezione, vedere [Applicare la protezione ai dati personali di Office 365](apply-protection-to-personal-data-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="d9537-154">For more information about applying proteciton, see [Apply protection to personal data in Office 365](apply-protection-to-personal-data-in-office-365.md).</span></span>

### <a name="step-5--monitor-for-leaks-of-personal-data"></a><span data-ttu-id="d9537-155">Fase 5 - Monitorare la perdita di dati personali
</span><span class="sxs-lookup"><span data-stu-id="d9537-155">Step 5 — Monitor for leaks of personal data</span></span>

<span data-ttu-id="d9537-p111">I report sulla prevenzione della perdita dei dati di Office 365 forniscono il livello maggiore di dettaglio per il monitoraggio dei dati riservati. È possibile configurare avvisi automatici e analizzare violazioni utilizzando il log di controllo di Office 365. Cloud App Security estende la capacità di trovare e monitorare i dati riservati ad altri provider SaaS. Per ulteriori informazioni su questi strumenti, vedere [Monitorare le violazioni dei dati personali](/security/office-365-security/monitor-for-leaks-of-personal-data.md).</span><span class="sxs-lookup"><span data-stu-id="d9537-p111">Office 365 data loss prevention reports provide the greatest level of detail for monitoring sensitive data. You can setup automated alerts and investigate breaches by using the Office 365 audit log. Cloud App Security extends the ability to find and monitor sensitive data to other SaaS providers. For more information on these tools, see [Monitor for breaches of personal data](/security/office-365-security/monitor-for-leaks-of-personal-data.md).</span></span>
