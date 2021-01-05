---
title: Monitorare e rispondere agli incidenti sulla privacy dei dati nell'organizzazione
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 01/04/2021
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
ms.custom: ''
description: Utilizzare i criteri di controllo e di avviso e le richieste del soggetto dei dati per monitorare e rispondere agli incidenti dei dati personali.
ms.openlocfilehash: 3ae0f2a6528f6188500c7cee7732c6447013eaa6
ms.sourcegitcommit: ae646779d84e993cf80b1207e76b856a21be5790
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/04/2021
ms.locfileid: "49749588"
---
# <a name="monitor-and-respond-to-data-privacy-incidents-in-your-organization"></a><span data-ttu-id="a6d83-103">Monitorare e rispondere agli incidenti sulla privacy dei dati nell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="a6d83-103">Monitor and respond to data privacy incidents in your organization</span></span>

<span data-ttu-id="a6d83-104">Sono disponibili funzionalità di Microsoft 365 che consentono di monitorare, indagare e rispondere agli incidenti sulla privacy dei dati nell'organizzazione durante la operazionalizzare delle funzionalità correlate.</span><span class="sxs-lookup"><span data-stu-id="a6d83-104">Microsoft 365 features are available to help you monitor, investigate, and respond to data privacy incidents in your organization as you operationalize related capabilities.</span></span> <span data-ttu-id="a6d83-105">L'utilizzo di processi, procedure e altre documentazioni per ognuna di queste operazioni può anche essere importante per dimostrare la conformità agli organismi di regolamentazione.</span><span class="sxs-lookup"><span data-stu-id="a6d83-105">Having processes, procedures, and other documentation for each of these may also be important to demonstrate compliance to regulatory bodies.</span></span>

<span data-ttu-id="a6d83-106">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="a6d83-106">These include:</span></span> 

- <span data-ttu-id="a6d83-107">Criteri di controllo e avviso</span><span class="sxs-lookup"><span data-stu-id="a6d83-107">Auditing and alert policies</span></span>
- <span data-ttu-id="a6d83-108">Richieste del soggetto dei dati (inclusa la ricerca di contenuto e eDiscovery)</span><span class="sxs-lookup"><span data-stu-id="a6d83-108">Data subject requests (including content search and eDiscovery)</span></span>
- <span data-ttu-id="a6d83-109">Ulteriori strumenti e report di analisi</span><span class="sxs-lookup"><span data-stu-id="a6d83-109">Additional investigative tools and reporting</span></span>

## <a name="data-privacy-regulations-impacting-the-use-of-monitoring-and-response-tools"></a><span data-ttu-id="a6d83-110">Normative sulla privacy dei dati che influiscono sull'utilizzo degli strumenti di monitoraggio e risposta</span><span class="sxs-lookup"><span data-stu-id="a6d83-110">Data privacy regulations impacting the use of monitoring and response tools</span></span>

<span data-ttu-id="a6d83-111">Ecco un elenco di esempi di regolamenti sulla privacy dei dati che possono riguardare i controlli di governance delle informazioni:</span><span class="sxs-lookup"><span data-stu-id="a6d83-111">Here is a sample listing of data privacy regulations that may relate to information governance controls:</span></span>

- <span data-ttu-id="a6d83-112">LGPD articolo 46</span><span class="sxs-lookup"><span data-stu-id="a6d83-112">LGPD Article 46</span></span>
- <span data-ttu-id="a6d83-113">LGPD articolo 48</span><span class="sxs-lookup"><span data-stu-id="a6d83-113">LGPD Article 48</span></span>
- <span data-ttu-id="a6d83-114">Articolo di GDPR (5) (1) (f)</span><span class="sxs-lookup"><span data-stu-id="a6d83-114">GDPR Article (5)(1)(f)</span></span>
- <span data-ttu-id="a6d83-115">Articolo di GDPR (15) (1) (e)</span><span class="sxs-lookup"><span data-stu-id="a6d83-115">GDPR Article (15)(1)(e)</span></span>
- <span data-ttu-id="a6d83-116">HIPAA-HITECH (45 C.F.R.</span><span class="sxs-lookup"><span data-stu-id="a6d83-116">HIPAA-HITECH (45 C.F.R.</span></span> <span data-ttu-id="a6d83-117">164.308 (a) (1) (II) (D))</span><span class="sxs-lookup"><span data-stu-id="a6d83-117">164.308(a)(1)(ii)(D))</span></span>
- <span data-ttu-id="a6d83-118">HIPAA-HITECH (45 C.F.R.</span><span class="sxs-lookup"><span data-stu-id="a6d83-118">HIPAA-HITECH (45 C.F.R.</span></span> <span data-ttu-id="a6d83-119">164.308(a)(6)(ii)</span><span class="sxs-lookup"><span data-stu-id="a6d83-119">164.308(a)(6)(ii)</span></span>
- <span data-ttu-id="a6d83-120">HIPAA-HITECH (45 C.F.R.</span><span class="sxs-lookup"><span data-stu-id="a6d83-120">HIPAA-HITECH (45 C.F.R.</span></span> <span data-ttu-id="a6d83-121">164.312 (b))</span><span class="sxs-lookup"><span data-stu-id="a6d83-121">164.312(b))</span></span>
- <span data-ttu-id="a6d83-122">CCPA (1798.105 (c))</span><span class="sxs-lookup"><span data-stu-id="a6d83-122">CCPA (1798.105(c))</span></span>

<span data-ttu-id="a6d83-123">Per ulteriori informazioni, vedere [valutare i rischi per la privacy dei dati e identificare informazioni riservate](information-protection-deploy-assess.md).</span><span class="sxs-lookup"><span data-stu-id="a6d83-123">For more information, see [Assess data privacy risks and identify sensitive information](information-protection-deploy-assess.md).</span></span>

<span data-ttu-id="a6d83-124">Le normative sulla privacy dei dati richiedono generalmente le seguenti operazioni per il monitoraggio e la risposta:</span><span class="sxs-lookup"><span data-stu-id="a6d83-124">The data privacy regulations generally call for the following for monitoring and response:</span></span>

- <span data-ttu-id="a6d83-125">Controllo, avviso e Reporting per attività relative all'archiviazione, alla condivisione e all'elaborazione dei dati personali</span><span class="sxs-lookup"><span data-stu-id="a6d83-125">Auditing, alerting, and reporting for activities related to the storage, sharing and processing of personal data</span></span>
- <span data-ttu-id="a6d83-126">La capacità di rispondere a una richiesta del soggetto dei dati (DSR) e, in alcuni casi, di eseguire indagini e altre misure amministrative per conformarsi a tali richieste.</span><span class="sxs-lookup"><span data-stu-id="a6d83-126">The ability to respond to a data subject request (DSR) and in some cases, perform investigative and other administrative measures to comply with such requests.</span></span>

<span data-ttu-id="a6d83-127">L'organizzazione può anche eseguire attività di monitoraggio e risposta per altri scopi, ad esempio altre esigenze di conformità o per motivi aziendali.</span><span class="sxs-lookup"><span data-stu-id="a6d83-127">Your organization may also wish to perform monitoring and response activities for other purposes, such as other compliance needs or for business reasons.</span></span> <span data-ttu-id="a6d83-128">La definizione del sistema di monitoraggio e di risposta per la privacy dei dati deve essere svolta come parte del monitoraggio e della pianificazione di risposta, implementazione e gestione generali.</span><span class="sxs-lookup"><span data-stu-id="a6d83-128">Establishing your monitoring and response scheme for data privacy should be done as part of overall monitoring and response planning, implementation, and management.</span></span>

<span data-ttu-id="a6d83-129">Per iniziare a utilizzare uno schema di monitoraggio e risposta in Microsoft 365 per le normative sulla privacy dei dati, in questo articolo sono elencate le funzionalità utili di Microsoft 365 per rispondere a domande quali:</span><span class="sxs-lookup"><span data-stu-id="a6d83-129">To help you get started with a monitoring and response scheme in Microsoft 365 for data privacy regulations, this article lists useful capabilities in Microsoft 365 to answer questions such as:</span></span> 

- <span data-ttu-id="a6d83-130">Che tipo di monitoraggio giornaliero, di analisi e di creazione di report sono disponibili per i diversi tipi di dati e le origini?</span><span class="sxs-lookup"><span data-stu-id="a6d83-130">What sort of day-to-day monitoring, investigative and reporting techniques are available for the different data types and sources?</span></span>
- <span data-ttu-id="a6d83-131">Quali sono i meccanismi necessari per gestire le richieste degli interessati (richieste DSR) e le azioni correttive, ad esempio Anonymization, redazione ed eliminazione.</span><span class="sxs-lookup"><span data-stu-id="a6d83-131">What mechanisms will be needed to handle data subject requests (DSRs) and any remedial actions, such as anonymization, redaction, and deletion.</span></span>

## <a name="auditing-and-alert-policies-in-the-security-and-compliance-center"></a><span data-ttu-id="a6d83-132">Criteri di controllo e di avviso nel centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="a6d83-132">Auditing and Alert Policies in the Security and Compliance Center</span></span>

<span data-ttu-id="a6d83-133">Vedere questi articoli per la configurazione del controllo, del controllo avanzato e dei criteri di avviso:</span><span class="sxs-lookup"><span data-stu-id="a6d83-133">See these articles for setting up auditing, advanced auditing, and alert policies:</span></span>

- [<span data-ttu-id="a6d83-134">Controllo unificato</span><span class="sxs-lookup"><span data-stu-id="a6d83-134">Unified auditing</span></span>](../compliance/search-the-audit-log-in-security-and-compliance.md)
- [<span data-ttu-id="a6d83-135">Controllo delle cassette postali</span><span class="sxs-lookup"><span data-stu-id="a6d83-135">Mailbox auditing</span></span>](../compliance/enable-mailbox-auditing.md)
- [<span data-ttu-id="a6d83-136">Controllo avanzato</span><span class="sxs-lookup"><span data-stu-id="a6d83-136">Advanced audit</span></span>](../compliance/advanced-audit.md)
- [<span data-ttu-id="a6d83-137">Criteri di avviso</span><span class="sxs-lookup"><span data-stu-id="a6d83-137">Alert policies</span></span>](../compliance/alert-policies.md)

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a><span data-ttu-id="a6d83-138">Richieste del soggetto dei dati per GDPR e CCPA</span><span class="sxs-lookup"><span data-stu-id="a6d83-138">Data subject requests for the GDPR and CCPA</span></span>

<span data-ttu-id="a6d83-139">Per informazioni su come rispondere a un DSR in Microsoft 365, vedere [richieste degli interessati per GDPR e CCPA](../compliance/gdpr-dsr-office365.md) .</span><span class="sxs-lookup"><span data-stu-id="a6d83-139">See [Data Subject Requests for the GDPR and CCPA](../compliance/gdpr-dsr-office365.md) for information on responding to a DSR in Microsoft 365.</span></span>

## <a name="manage-deleted-users-in-microsoft-stream"></a><span data-ttu-id="a6d83-140">Gestire gli utenti eliminati in Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="a6d83-140">Manage deleted users in Microsoft Stream</span></span>

<span data-ttu-id="a6d83-141">Per Microsoft Stream, quando un utente viene eliminato da Azure Active Directory (Azure AD), se il relativo nome è stato associato a un video del flusso postato prima di quel momento, l'indirizzo di posta elettronica rimane associato al video.</span><span class="sxs-lookup"><span data-stu-id="a6d83-141">For Microsoft Stream, when a user is deleted from Azure Active Directory (Azure AD), if their name was associated with a posted Stream video prior to that point, their email address remains associated with the video.</span></span> <span data-ttu-id="a6d83-142">Per rimuoverlo, vedere [gestire gli utenti eliminati da Microsoft Stream](https://docs.microsoft.com/stream/managing-deleted-users) .</span><span class="sxs-lookup"><span data-stu-id="a6d83-142">See [Manage deleted users from Microsoft Stream](https://docs.microsoft.com/stream/managing-deleted-users) to remove it.</span></span>

## <a name="insider-risk-management-as-an-investigative-tool"></a><span data-ttu-id="a6d83-143">Gestione dei rischi insider come strumento investigativo</span><span class="sxs-lookup"><span data-stu-id="a6d83-143">Insider risk management as an investigative tool</span></span>

<span data-ttu-id="a6d83-144">La [gestione dei rischi insider in microsoft 365](../compliance/insider-risk-management.md) è una funzionalità dell'interfaccia di amministrazione della conformità Microsoft che consente di ridurre al minimo i rischi interni, consentendo di rilevare, indagare ed eseguire azioni sulle attività a rischio nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a6d83-144">[Insider risk management in Microsoft 365](../compliance/insider-risk-management.md) is a feature of the Microsoft Compliance admin center to help you minimize internal risk by enabling you to detect, investigate, and take action on risky activities in your organization.</span></span>
