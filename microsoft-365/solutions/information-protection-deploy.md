---
title: Distribuire la protezione delle informazioni per le normative sulla privacy dei dati con Microsoft 365
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- M365solutions
ms.custom: ''
description: Configurare l'infrastruttura di sicurezza e di servizio per proteggere le informazioni e attenersi alle normative sulla privacy dei dati.
ms.openlocfilehash: 35ccfb21accd969c2a2cbdddde9a4ec1c7eeed64
ms.sourcegitcommit: b03a7ad0a80f8b839f40b8d396ab3a049491a12f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2020
ms.locfileid: "44695110"
---
# <a name="deploy-information-protection-for-data-privacy-regulations-with-microsoft-365"></a><span data-ttu-id="49845-103">Distribuire la protezione delle informazioni per le normative sulla privacy dei dati con Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="49845-103">Deploy information protection for data privacy regulations with Microsoft 365</span></span>

<span data-ttu-id="49845-104">Questa soluzione fornisce indicazioni su come pianificare e proteggere i dati personali archiviati nei servizi Microsoft 365 e potenzialmente soggetti alle normative sulla privacy dei dati, come il regolamento generale sulla protezione dei dati (GDPR) dell'Unione europea.</span><span class="sxs-lookup"><span data-stu-id="49845-104">This solution provides guidance on how to plan for and protect personal data that is stored in Microsoft 365 services and potentially subject to data privacy regulations such as the European Union's General Data Protection Regulation (GDPR).</span></span> <span data-ttu-id="49845-105">Questa soluzione è incentrata sulle funzionalità di Microsoft Information Protection and Compliance, sul punteggio di conformità di Microsoft e sugli strumenti di valutazione che consentono di conoscere i dati.</span><span class="sxs-lookup"><span data-stu-id="49845-105">This solution focuses on applicable Microsoft information protection and compliance features, Microsoft Compliance Score, and assessment tools to help you know your data.</span></span> 
 
<span data-ttu-id="49845-106">Sono inoltre disponibili ulteriori informazioni sull'utilizzo dei controlli Microsoft Identity, Device e Threat Protection per le esigenze relative alla privacy dei dati, nonché sugli strumenti per l'individuazione e la risposta degli incidenti di dati.</span><span class="sxs-lookup"><span data-stu-id="49845-106">Additional information is also provided on the use of Microsoft identity, device, and threat protection controls for your data privacy needs, as well as data incident discovery and response tools.</span></span> 

## <a name="organization-of-this-guidance-material"></a><span data-ttu-id="49845-107">Organizzazione di questo materiale di orientamento</span><span class="sxs-lookup"><span data-stu-id="49845-107">Organization of this guidance material</span></span>

<span data-ttu-id="49845-108">Per facilitare la comprensione degli strumenti di Microsoft 365 disponibili per identificare, gestire, controllare e monitorare i dati personali soggetti a una o più normative relative alla privacy, queste linee guida sono organizzate in sezioni.</span><span class="sxs-lookup"><span data-stu-id="49845-108">To help you understand the Microsoft 365 tools available to identify, manage, control, and monitor personal data subject to one or more privacy-related regulations, this guidance is organized into sections.</span></span>
 
![Distribuire protezione delle informazioni per le normative sulla privacy dei dati](../media/information-protection-deploy/information-protection-deploy-grid.png)

<span data-ttu-id="49845-110">Ognuna di queste sezioni corrisponde a un articolo distinto della soluzione.</span><span class="sxs-lookup"><span data-stu-id="49845-110">Each of these sections correspond to a separate article in this solution.</span></span>

>[!Note]
><span data-ttu-id="49845-111">Se si ha già familiarità con gli obblighi relativi alla privacy dei dati e si esegue in base a un piano esistente, potrebbe essere necessario concentrarsi sulle indicazioni di prevenzione, protezione, conservazione e analisi.</span><span class="sxs-lookup"><span data-stu-id="49845-111">If you are already familiar with your data privacy obligations and are executing against an existing plan, you may want to focus on the Prevent, Protect, Retain, and Investigate guidance.</span></span>

>[!Important]
><span data-ttu-id="49845-112">Seguendo queste indicazioni non sarà necessariamente conforme a qualsiasi normativa sulla privacy dei dati, in particolare considerando il numero di passaggi necessari che non rientrano nel contesto delle caratteristiche.</span><span class="sxs-lookup"><span data-stu-id="49845-112">Following this guidance will not necessarily make you compliant with any data privacy regulation, especially considering the number of steps required that are outside the context of the features.</span></span> <span data-ttu-id="49845-113">L'utente è responsabile per garantire la conformità e per consultare i propri team legali e di conformità o per richiedere indicazioni e consigli da terze parti specializzate in conformità.</span><span class="sxs-lookup"><span data-stu-id="49845-113">You are responsible for ensuring your compliance and to consult your legal and compliance teams or to seek guidance and advice from third parties that specialize in compliance.</span></span>
>

## <a name="plan-assess-data-privacy-risks-and-identify-sensitive-items"></a><span data-ttu-id="49845-114">Pianificare: valutare i rischi per la privacy dei dati e identificare gli elementi sensibili</span><span class="sxs-lookup"><span data-stu-id="49845-114">Plan: Assess data privacy risks and identify sensitive items</span></span> 

<span data-ttu-id="49845-115">Valutare le normative sulla privacy dei dati e i rischi a cui l'organizzazione è soggetta è un primo passo importante da intraprendere prima di iniziare a implementare i miglioramenti, compresi quelli ottenibili tramite la configurazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="49845-115">Assessing data privacy regulations and risks that your organization is subject to is a key first step to take before starting to implement improvements, including those achievable through Microsoft 365 configuration.</span></span> <span data-ttu-id="49845-116">Ciò può includere una valutazione generale della conformità o l'identificazione di particolari tipi di informazioni sensibili che sono soggetti ai controlli normativi che l'organizzazione deve soddisfare, nonché la loro occorrenza nell'ambiente Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="49845-116">This may include an overall readiness assessment or identification of particular sensitive information types that are subject to regulatory controls your organization needs to comply with, as well as the occurrence of them in your Microsoft 365 environment.</span></span>

<span data-ttu-id="49845-117">Per ulteriori informazioni, vedere [valutare i rischi per la privacy dei dati e identificare gli elementi sensibili](information-protection-deploy-assess.md).</span><span class="sxs-lookup"><span data-stu-id="49845-117">For more information, see [Assess data privacy risks and identify sensitive items](information-protection-deploy-assess.md).</span></span>

## <a name="track-use-compliance-score-and-compliance-manager"></a><span data-ttu-id="49845-118">Track: utilizzare la conformità score e Compliance Manager</span><span class="sxs-lookup"><span data-stu-id="49845-118">Track: Use Compliance Score and Compliance Manager</span></span> 

<span data-ttu-id="49845-119">Score compliance e Compliance Manager offrono un set integrato di strumenti disponibili nell'interfaccia di amministrazione di Microsoft 365 compliance e nel portale di gestione dei servizi.</span><span class="sxs-lookup"><span data-stu-id="49845-119">Compliance Score and Compliance Manager provide an integrated set of tools available in the Microsoft 365 Compliance admin center and Services Trust Portal.</span></span> <span data-ttu-id="49845-120">Insieme, questi strumenti offrono una capacità integrata di monitorare e gestire le azioni di miglioramento complessive, nonché quelle relative a più normative sulla privacy dei dati a cui sono soggetti.</span><span class="sxs-lookup"><span data-stu-id="49845-120">Together, these tools provide you with a built-in ability to track and manage improvement actions overall as well as those related to multiple data privacy regulations to which you are subjected.</span></span>

<span data-ttu-id="49845-121">Gli strumenti consentono inoltre di utilizzare modelli di valutazione specifici per ogni regola, in cui è possibile tenere presenti gli elementi di azione per ogni modello di valutazione selezionato, nonché visualizzare controlli normativi specifici e correlarli a azioni specifiche.</span><span class="sxs-lookup"><span data-stu-id="49845-121">The tools also allow you to leverage built in assessment templates specific to each regulation, where you can track action items for each assessment template selected, as well as view specific regulatory controls, and relate them to specific actions.</span></span>

<span data-ttu-id="49845-122">Per ulteriori informazioni, vedere [use Compliance score and Compliance Manager to Manage Improvement actions](information-protection-deploy-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="49845-122">For more information, see [Use Compliance Score and Compliance Manager to manage improvement actions](information-protection-deploy-compliance.md).</span></span>

## <a name="prevent-use-identity-device-and-threat-protection-for-data-privacy-regulation"></a><span data-ttu-id="49845-123">Impedisci: utilizzare l'identità, il dispositivo e la protezione dalle minacce per la normativa sulla privacy dei dati</span><span class="sxs-lookup"><span data-stu-id="49845-123">Prevent: Use identity, device, and threat protection for data privacy regulation</span></span>

<span data-ttu-id="49845-124">Microsoft 365 fornisce una serie di funzionalità di protezione delle minacce e delle identità che è possibile utilizzare per conformarsi alla conformità alle normative sulla privacy dei dati.</span><span class="sxs-lookup"><span data-stu-id="49845-124">Microsoft 365 provides a number of identity, device, and threat protection capabilities that you can use to help comply with data privacy regulatory compliance.</span></span> 

<span data-ttu-id="49845-125">Per ulteriori informazioni, vedere [use Identity, Device, and Threat Protection for data privacy Regulation](information-protection-deploy-identity-device-threat.md).</span><span class="sxs-lookup"><span data-stu-id="49845-125">For more information, see [Use identity, device, and threat protection for data privacy regulation](information-protection-deploy-identity-device-threat.md).</span></span>

<span data-ttu-id="49845-126">Questo articolo descrive brevemente cosa richiedono generalmente le normative sulla privacy dei dati in queste aree e fornisce un elenco delle soluzioni Microsoft 365 correlate, con collegamenti a ulteriori informazioni che consentono di soddisfare i requisiti di implementazione.</span><span class="sxs-lookup"><span data-stu-id="49845-126">This article briefly describes what the data privacy regulations generally call for in these areas and provides a listing of related Microsoft 365 solutions, with links to more information to help you address any implementation requirements.</span></span> 

## <a name="protect-information-subject-to-data-privacy-regulation"></a><span data-ttu-id="49845-127">Proteggere le informazioni soggette alla normativa sulla privacy dei dati</span><span class="sxs-lookup"><span data-stu-id="49845-127">Protect information subject to data privacy regulation</span></span>

<span data-ttu-id="49845-128">Le normative sulla privacy dei dati prevedono una serie di controlli di protezione delle informazioni personali che possono essere utilizzati nel proprio ambiente, tra cui oltre 40 proteggere i controlli delle informazioni in tutte le quattro normative sulla privacy dei dati nel nostro set di GDPR, California Consumer Protection Act (CCPA), HIPAA-HITECH (United States Health Care Act) e Brasile Data Protection Act (LGPD)</span><span class="sxs-lookup"><span data-stu-id="49845-128">Data privacy regulations dictate a number of personal information protection controls that can be employed in your environment, including more than forty Protect Information controls across just the four data privacy regulations in our sample set of GDPR, California Consumer Protection Act (CCPA), HIPAA-HITECH (United States health care privacy act), and the Brazil Data Protection Act (LGPD).</span></span>

<span data-ttu-id="49845-129">Per ulteriori informazioni, vedere [Protect Information subject to data privacy Regulation nell'organizzazione](information-protection-deploy-protect-information.md).</span><span class="sxs-lookup"><span data-stu-id="49845-129">For more information, see [Protect information subject to data privacy regulation in your organization](information-protection-deploy-protect-information.md).</span></span>

<span data-ttu-id="49845-130">In questo articolo vengono illustrati i principali schemi di controllo che è possibile utilizzare per soddisfare le esigenze di protezione delle informazioni per la privacy dei dati nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="49845-130">This article lays out the main control schemes that can be used for addressing information protection needs for data privacy in your organization.</span></span>

## <a name="retain-govern-information-subject-to-data-privacy-regulation"></a><span data-ttu-id="49845-131">Mantieni: regola le informazioni soggette alla normativa sulla privacy dei dati</span><span class="sxs-lookup"><span data-stu-id="49845-131">Retain: Govern information subject to data privacy regulation</span></span>

<span data-ttu-id="49845-132">Le normative sulla privacy dei dati richiedono controlli per la governance delle informazioni personali che possono essere utilizzati nel proprio ambiente, tra cui oltre ventiquattro controlli nelle quattro normative sulla privacy dei dati nel nostro set di esempi di GDPR, CCPA, HIPAA-HITECH e LGPD.</span><span class="sxs-lookup"><span data-stu-id="49845-132">Data privacy regulations call for personal information governance controls that can be employed in your environment, including more than twenty-four controls across the four data privacy regulations in our sample set of GDPR, CCPA, HIPAA-HITECH, and LGPD.</span></span>

<span data-ttu-id="49845-133">Per ulteriori informazioni, vedere [govern Information subject to data privacy Regulation nell'organizzazione](information-protection-deploy-govern.md).</span><span class="sxs-lookup"><span data-stu-id="49845-133">For more information, see [Govern information subject to data privacy regulation in your organization](information-protection-deploy-govern.md).</span></span>

<span data-ttu-id="49845-134">Anche se le normative sulla privacy dei dati possono essere vaghe per quanto riguarda la governance delle informazioni &mdash; , come la conservazione, l'eliminazione e l'archiviazione mirate &mdash; in questo articolo vengono illustrati gli schemi di controllo principali che è possibile utilizzare per la privacy dei dati nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="49845-134">While the data privacy regulations can be vague regarding information governance&mdash;such as purposeful retention, deletion and archiving&mdash;this article lays out the primary control schemes that you can use address information governance needs for data privacy in your organization.</span></span>

## <a name="investigate-monitor-and-respond-subject-to-data-privacy-regulation"></a><span data-ttu-id="49845-135">Esaminare: monitorare e rispondere alla normativa sulla privacy dei dati</span><span class="sxs-lookup"><span data-stu-id="49845-135">Investigate: Monitor and respond subject to data privacy regulation</span></span>

<span data-ttu-id="49845-136">Sono disponibili funzionalità di Microsoft 365 che consentono di monitorare, esaminare e rispondere agli incidenti sulla privacy dei dati nell'organizzazione durante la operazionalizzare delle funzionalità correlate.</span><span class="sxs-lookup"><span data-stu-id="49845-136">There are Microsoft 365 features available to help you monitor, investigate, and respond to data privacy incidents in your organization as you operationalize related capabilities.</span></span> 

<span data-ttu-id="49845-137">L'utilizzo di processi, procedure e altre documentazioni per ognuna di queste operazioni può essere importante per dimostrare la conformità agli organismi di regolamentazione.</span><span class="sxs-lookup"><span data-stu-id="49845-137">Having processes, procedures, and other documentation for each of these can be important to demonstrate compliance to regulatory bodies.</span></span>

<span data-ttu-id="49845-138">Per ulteriori informazioni, vedere [monitorare e rispondere agli incidenti sulla privacy dei dati nell'organizzazione](information-protection-deploy-monitor-respond.md).</span><span class="sxs-lookup"><span data-stu-id="49845-138">For more information, see [Monitor and respond to data privacy incidents in your organization](information-protection-deploy-monitor-respond.md).</span></span>
