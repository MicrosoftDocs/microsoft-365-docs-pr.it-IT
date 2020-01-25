---
title: 'Codice di condotta in materia di controllo della sicurezza informatica ISO/IEC 27017:2015 '
description: I servizi cloud di Microsoft hanno implementato questo Codice di condotta in materia di controllo della sicurezza informatica.
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
titleSuffix: Microsoft Compliance
ms.openlocfilehash: 758e7d0f3e82afa6cfd4b90501bd84080d8f6303
ms.sourcegitcommit: 3dca80f268006658a0b721aa4f6df1224c7964dc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2020
ms.locfileid: "41260014"
---
# <a name="isoiec-270172015-code-of-practice-for-information-security-controls"></a><span data-ttu-id="27f24-104">Codice di condotta in materia di controllo della sicurezza informatica ISO/IEC 27017:2015 </span><span class="sxs-lookup"><span data-stu-id="27f24-104">ISO/IEC 27017:2015 Code of Practice for Information Security Controls</span></span>

## <a name="iso-iec-27017-overview"></a><span data-ttu-id="27f24-105">Panoramica ISO-IEC 27017</span><span class="sxs-lookup"><span data-stu-id="27f24-105">ISO-IEC 27017 Overview</span></span>

<span data-ttu-id="27f24-106">Il Codice di condotta ISO/IEC 27017:2015 è stato progettato come un riferimento per la selezione dei controlli di sicurezza delle informazioni dei servizi cloud quando si implementa un sistema di gestione della sicurezza delle informazioni cloud computing basato su ISO/IEC 27002:2013.</span><span class="sxs-lookup"><span data-stu-id="27f24-106">The ISO/IEC 27017:2015 code of practice is designed for organizations to use as a reference for selecting cloud services information security controls when implementing a cloud computing information security management system based on ISO/IEC 27002:2013.</span></span> <span data-ttu-id="27f24-107">Può anche essere usato dai provider di servizi cloud come documento guida per l'implementazione dei controlli di protezione comunemente accettati.</span><span class="sxs-lookup"><span data-stu-id="27f24-107">It can also be used by cloud service providers as a guidance document for implementing commonly accepted protection controls.</span></span>

<span data-ttu-id="27f24-108">Questo standard internazionale fornisce indicazioni aggiuntive sull'implementazione specifiche del cloud basate su ISO/IEC 27002 e controlli aggiuntivi per attenuare i rischi per la sicurezza delle informazioni facendo riferimento alle clausole 5-18 in ISO/IEC 27002: 2013 per controlli, indicazioni sull'implementazione e altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="27f24-108">This international standard provides additional cloud-specific implementation guidance based on ISO/IEC 27002, and provides additional controls to address cloud-specific information security threats and risks referring to clauses 5–18 in ISO/IEC 27002: 2013 for controls, implementation guidance, and other information.</span></span> <span data-ttu-id="27f24-109">In modo specifico, questo standard fornisce indicazioni su 37 controlli in ISO/IEC 27002 e include sette nuovi controlli che non sono duplicati in ISO/IEC 27002.</span><span class="sxs-lookup"><span data-stu-id="27f24-109">Specifically, this standard provides guidance on 37 controls in ISO/IEC 27002, and it also features seven new controls that are not duplicated in ISO/IEC 27002.</span></span> <span data-ttu-id="27f24-110">Questi nuovi controlli riguardano le aeree importanti elencate di seguito:</span><span class="sxs-lookup"><span data-stu-id="27f24-110">These new controls address the following important areas:</span></span>

- <span data-ttu-id="27f24-111">Responsabilità e ruoli condivisi nell'ambiente di cloud computing</span><span class="sxs-lookup"><span data-stu-id="27f24-111">Shared roles and responsibilities within a cloud computing environment</span></span>
- <span data-ttu-id="27f24-112">Rimozione e restituzione degli asset dei clienti dei servizi cloud alla rescissione del contratto</span><span class="sxs-lookup"><span data-stu-id="27f24-112">Removal and return of cloud service customer assets upon contract termination</span></span>
- <span data-ttu-id="27f24-113">Protezione e separazione dell'ambiente virtuale di un cliente da quello di altri clienti</span><span class="sxs-lookup"><span data-stu-id="27f24-113">Protection and separation of a customer’s virtual environment from that of other customers</span></span>
- <span data-ttu-id="27f24-114">Requisiti di hardening delle macchine virtuali per soddisfare esigenze di business</span><span class="sxs-lookup"><span data-stu-id="27f24-114">Virtual machine hardening requirements to meet business needs</span></span>
- <span data-ttu-id="27f24-115">Procedure per operazioni amministrative di un ambiente di cloud computing</span><span class="sxs-lookup"><span data-stu-id="27f24-115">Procedures for administrative operations of a cloud computing environment</span></span>
- <span data-ttu-id="27f24-116">Monitoraggio di attività rilevanti da parte dei clienti in un ambiente di cloud computing</span><span class="sxs-lookup"><span data-stu-id="27f24-116">Enabling customers to monitor relevant activities within a cloud computing environment</span></span>
- <span data-ttu-id="27f24-117">Allineamento della gestione della sicurezza per reti virtuali e fisiche</span><span class="sxs-lookup"><span data-stu-id="27f24-117">Alignment of security management for virtual and physical networks</span></span>

## <a name="microsoft-and-isoiec-27017"></a><span data-ttu-id="27f24-118">Microsoft e ISO/IEC 27017</span><span class="sxs-lookup"><span data-stu-id="27f24-118">Microsoft and ISO/IEC 27017</span></span>

<span data-ttu-id="27f24-119">ISO/IEC 27017 è unico nel fornire indicazioni tanto ai provider di servizi cloud quanto ai clienti di servizi cloud.</span><span class="sxs-lookup"><span data-stu-id="27f24-119">ISO/IEC 27017 is unique in providing guidance for both cloud service providers and cloud service customers.</span></span> <span data-ttu-id="27f24-120">Fornisce inoltre ai clienti di servizi cloud informazioni pratiche su ciò che devono aspettarsi dai provider.</span><span class="sxs-lookup"><span data-stu-id="27f24-120">It also provides cloud service customers with practical information on what they should expect from cloud service providers.</span></span> <span data-ttu-id="27f24-121">I clienti possono trarre vantaggio direttamente da ISO/IEC 27017 assicurandosi che comprendano le responsabilità condivise nel cloud.</span><span class="sxs-lookup"><span data-stu-id="27f24-121">Customers can benefit directly from ISO/IEC 27017 by ensuring they understand the shared responsibilities in the cloud.</span></span>

<span data-ttu-id="27f24-122">Per informazioni sui vantaggi di ISO/IEC 27017 in Microsoft Cloud: [scaricare ISO/IEC 27017: Codice di comportamento in materia di controllo della sicurezza informatica ](https://aka.ms/iso27017-backgrounder)</span><span class="sxs-lookup"><span data-stu-id="27f24-122">Learn about the benefits of ISO/IEC 27017 on the Microsoft Cloud: [Download the ISO/IEC 27017: Code of Practice for Information Security Controls](https://aka.ms/iso27017-backgrounder)</span></span>

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="27f24-123">Servizi cloud Microsoft inclusi nell'ambito</span><span class="sxs-lookup"><span data-stu-id="27f24-123">Microsoft in-scope cloud services</span></span>

- [<span data-ttu-id="27f24-124">Azure, Azure per enti pubblici e Azure Germania</span><span class="sxs-lookup"><span data-stu-id="27f24-124">Azure, Azure Government, and Azure Germany</span></span>](https://aka.ms/AzureCompliance)
- <span data-ttu-id="27f24-125">Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="27f24-125">Cloud App Security</span></span>
- [<span data-ttu-id="27f24-126">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="27f24-126">Dynamics 365</span></span>](https://aka.ms/d365-compliance-list)
- <span data-ttu-id="27f24-127">Genomica</span><span class="sxs-lookup"><span data-stu-id="27f24-127">Genomics</span></span>
- <span data-ttu-id="27f24-128">Graph</span><span class="sxs-lookup"><span data-stu-id="27f24-128">Graph</span></span>
- <span data-ttu-id="27f24-129">Intune</span><span class="sxs-lookup"><span data-stu-id="27f24-129">Intune</span></span>
- <span data-ttu-id="27f24-130">Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="27f24-130">Microsoft Managed Desktop</span></span>
- <span data-ttu-id="27f24-131">Servizio cloud Microsoft Flow, autonomo o incluso in un piano o in una famiglia di prodotti Office 365 o Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="27f24-131">Microsoft Flow cloud service either as a standalone service or as included in an Office 365 or Dynamics 365 branded plan or suite</span></span>
- <span data-ttu-id="27f24-132">Office 365, Office 365 U.S. Government, Office 365 U.S. Government Defense e Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="27f24-132">Office 365, Office 365 U.S. Government, Office 365 U.S. Government Defense, and Office 365 Germany</span></span>
- <span data-ttu-id="27f24-133">Servizio cloud PowerApps, autonomo o incluso in un piano o in una famiglia di prodotti con marchio Office 365 o Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="27f24-133">PowerApps cloud service either as a standalone service or as included in an Office 365 or Dynamics 365 branded plan or suite</span></span>
- <span data-ttu-id="27f24-134">Servizio cloud Power BI, autonomo o incluso in un piano o in una famiglia di prodotti con marchio Office 365</span><span class="sxs-lookup"><span data-stu-id="27f24-134">Power BI cloud service either as a standalone service or as included in an Office 365 branded plan or suite</span></span>
- <span data-ttu-id="27f24-135">Vedere un [elenco dettagliato](https://go.microsoft.com/fwlink/p/?linkid=2077751) dei servizi inclusi in Office 365</span><span class="sxs-lookup"><span data-stu-id="27f24-135">See a [detailed list](https://go.microsoft.com/fwlink/p/?linkid=2077751) of covered services in Office 365</span></span>

## <a name="audits-reports-and-certificates"></a><span data-ttu-id="27f24-136">Controlli, report e certificati</span><span class="sxs-lookup"><span data-stu-id="27f24-136">Audits, reports, and certificates</span></span>

<span data-ttu-id="27f24-137">I servizi cloud Microsoft vengono controllati una volta all'anno per verificare l'adeguamento al Codice di comportamento ISO/IEC 27017:2015 come parte del processo di certificazione per ISO/IEC 27001:2013.</span><span class="sxs-lookup"><span data-stu-id="27f24-137">Microsoft cloud services are audited once a year for the ISO/IEC 27017:2015 code of practice as part of the certification process for ISO/IEC 27001:2013.</span></span>

- [<span data-ttu-id="27f24-138">Certificato ISO 27017 di Azure</span><span class="sxs-lookup"><span data-stu-id="27f24-138">Azure ISO 27017 Certificate</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2078005)
- [<span data-ttu-id="27f24-139">Report di valutazione ISO 27017 per Azure</span><span class="sxs-lookup"><span data-stu-id="27f24-139">Azure ISO 27017 Assessment report</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2078010)
- [<span data-ttu-id="27f24-140">Dichiarazione di applicabilità di Azure ISO 27017</span><span class="sxs-lookup"><span data-stu-id="27f24-140">Azure ISO 27017 Statement of Applicability</span></span>](https://aka.ms/AzureISO27017StatementofApplicability)
- [<span data-ttu-id="27f24-141">Report di valutazione di controllo ISO 27001, 27018 e 27017 per Office 365</span><span class="sxs-lookup"><span data-stu-id="27f24-141">Office 365 ISO 27001, 27018, and 27017 Audit Assessment Report</span></span>](https://aka.ms/o365isoreport)

## <a name="frequently-asked-questions"></a><span data-ttu-id="27f24-142">Domande frequenti</span><span class="sxs-lookup"><span data-stu-id="27f24-142">Frequently asked questions</span></span>

<span data-ttu-id="27f24-143">A chi si applica lo standard?</span><span class="sxs-lookup"><span data-stu-id="27f24-143">To whom does the standard apply?</span></span>

<span data-ttu-id="27f24-144">Questo codice di comportamento fornisce controlli e indicazioni sull'implementazione tanto ai provider di servizi cloud quanto ai clienti di servizi cloud.</span><span class="sxs-lookup"><span data-stu-id="27f24-144">This code of practice provides controls and implementation guidance for both cloud service providers and cloud service customers.</span></span> <span data-ttu-id="27f24-145">È strutturato in un formato simile a ISO/IEC 27002:2013.</span><span class="sxs-lookup"><span data-stu-id="27f24-145">It is structured in a format similar to ISO/IEC 27002:2013.</span></span>

<span data-ttu-id="27f24-146">**Dove è possibile consultare le informazioni sull'adeguamento di Microsoft per ISO/IEC 27017:2015?**</span><span class="sxs-lookup"><span data-stu-id="27f24-146">**Where can I view Microsoft’s compliance information for ISO/IEC 27017:2015?**</span></span>

<span data-ttu-id="27f24-147">Si può scaricare il [certificato ISO/IEC 27017:2015](https://aka.ms/azureiso27017) per Azure, Intune e Power BI.</span><span class="sxs-lookup"><span data-stu-id="27f24-147">You can download the [ISO/IEC 27017:2015 certificate](https://aka.ms/azureiso27017) for Azure, Intune, and Power BI.</span></span>

<span data-ttu-id="27f24-148">**Posso usare la conformità ISO/IEC 27017 dei servizi Microsoft nella procedura di certificazione della mia organizzazione?**</span><span class="sxs-lookup"><span data-stu-id="27f24-148">**Can I use the ISO/IEC 27017 compliance of Microsoft services in my organization’s certification process?**</span></span>

<span data-ttu-id="27f24-149">Sì.</span><span class="sxs-lookup"><span data-stu-id="27f24-149">Yes.</span></span> <span data-ttu-id="27f24-150">Se l' azienda desidera una certificazione per le implementazioni distribuite su qualsiasi servizio enterprise cloud Microsoft, è possibile utilizzare le certificazioni rilevanti di Microsoft nella valutazione dell'adeguamento.</span><span class="sxs-lookup"><span data-stu-id="27f24-150">If your business is seeking certification for implementations deployed on any Microsoft in-scope enterprise cloud services, you can use Microsoft’s relevant certifications in your compliance assessment.</span></span> <span data-ttu-id="27f24-151">Tuttavia, si ha la responsabilità di affidare l'incarico a un perito affinché valuti la propria implementazione in termini di conformità e per i controlli e i processi all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="27f24-151">However, you are responsible for engaging an assessor to evaluate your implementation for compliance, and for the controls and processes within your own organization.</span></span>

<span data-ttu-id="27f24-152">**Come si possono ottenere copie dei report di controllo applicabili?**</span><span class="sxs-lookup"><span data-stu-id="27f24-152">**How can I get copies of the applicable audit reports?**</span></span>

<span data-ttu-id="27f24-153">Il [portale di attendibilità dei servizi](https://aka.ms/stphelp) fornisce report di controllo indipendenti e di terze parti e altra documentazione correlata.</span><span class="sxs-lookup"><span data-stu-id="27f24-153">The [Service Trust Portal](https://aka.ms/stphelp) provides independent, third-party audit reports and other related documentation.</span></span> <span data-ttu-id="27f24-154">È possibile usare il portale per scaricare e rivedere questa documentazione come supporto per i requisiti normativi.</span><span class="sxs-lookup"><span data-stu-id="27f24-154">You can use the portal to download and review this documentation for assistance with your own regulatory requirements.</span></span>

## <a name="resources"></a><span data-ttu-id="27f24-155">Risorse</span><span class="sxs-lookup"><span data-stu-id="27f24-155">Resources</span></span>

- [<span data-ttu-id="27f24-156">Codice di comportamento ISO/IEC 27017:2015</span><span class="sxs-lookup"><span data-stu-id="27f24-156">ISO/IEC 27017:2015 code of practice</span></span>](https://www.iso.org/iso/iso_catalogue/catalogue_tc/catalogue_detail.htm?csnumber=43757)
- [<span data-ttu-id="27f24-157">Condizioni di Microsoft Online Services</span><span class="sxs-lookup"><span data-stu-id="27f24-157">Microsoft Online Services Terms</span></span>](https://aka.ms/Online-Services-Terms)
- [<span data-ttu-id="27f24-158">Conformità nel Centro di protezione Microsoft</span><span class="sxs-lookup"><span data-stu-id="27f24-158">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a><span data-ttu-id="27f24-159">Scarica il documento di informazioni di base sulla soluzione</span><span class="sxs-lookup"><span data-stu-id="27f24-159">Download the offering backgrounder</span></span>

<span data-ttu-id="27f24-160">Ti serve il documento di informazioni di base sulla soluzione?</span><span class="sxs-lookup"><span data-stu-id="27f24-160">Do you need the backgrounder document for this offering?</span></span> <span data-ttu-id="27f24-161">Scarica il [PDF](https://download.microsoft.com/download/7/7/9/7799D02B-A97A-48E0-A057-C19DD543BB24/ISO-IEC-27017_backgrounder.pdf).</span><span class="sxs-lookup"><span data-stu-id="27f24-161">Download the [PDF](https://download.microsoft.com/download/7/7/9/7799D02B-A97A-48E0-A057-C19DD543BB24/ISO-IEC-27017_backgrounder.pdf).</span></span>
