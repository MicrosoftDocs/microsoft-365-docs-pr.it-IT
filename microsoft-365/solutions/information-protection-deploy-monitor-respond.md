---
title: Monitorare e rispondere agli incidenti di privacy dei dati nell'organizzazione
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
description: Usa i criteri di controllo e di avviso e le richieste dell'oggetto dei dati per monitorare e rispondere a eventi imprevisti relativi ai dati personali.
ms.openlocfilehash: 4070cd772d243bcfba33bfb164fd05e1f0911b3b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928425"
---
# <a name="monitor-and-respond-to-data-privacy-incidents-in-your-organization"></a><span data-ttu-id="c430f-103">Monitorare e rispondere agli incidenti di privacy dei dati nell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="c430f-103">Monitor and respond to data privacy incidents in your organization</span></span>

<span data-ttu-id="c430f-104">Microsoft 365 sono disponibili funzionalità che consentono di monitorare, analizzare e rispondere agli incidenti relativi alla privacy dei dati nell'organizzazione durante l'operatività delle funzionalità correlate.</span><span class="sxs-lookup"><span data-stu-id="c430f-104">Microsoft 365 features are available to help you monitor, investigate, and respond to data privacy incidents in your organization as you operationalize related capabilities.</span></span> <span data-ttu-id="c430f-105">La presenza di processi, procedure e altra documentazione per ognuno di questi elementi può essere importante anche per dimostrare la conformità agli organismi normativi.</span><span class="sxs-lookup"><span data-stu-id="c430f-105">Having processes, procedures, and other documentation for each of these may also be important to demonstrate compliance to regulatory bodies.</span></span>

<span data-ttu-id="c430f-106">Questi includono:</span><span class="sxs-lookup"><span data-stu-id="c430f-106">These include:</span></span> 

- <span data-ttu-id="c430f-107">Criteri di controllo e avviso</span><span class="sxs-lookup"><span data-stu-id="c430f-107">Auditing and alert policies</span></span>
- <span data-ttu-id="c430f-108">Richieste dell'oggetto dei dati (tra cui ricerca contenuto ed eDiscovery)</span><span class="sxs-lookup"><span data-stu-id="c430f-108">Data subject requests (including content search and eDiscovery)</span></span>
- <span data-ttu-id="c430f-109">Strumenti di indagine e report aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="c430f-109">Additional investigative tools and reporting</span></span>

## <a name="data-privacy-regulations-impacting-the-use-of-monitoring-and-response-tools"></a><span data-ttu-id="c430f-110">Normative sulla privacy dei dati che influiscono sull'uso di strumenti di monitoraggio e risposta</span><span class="sxs-lookup"><span data-stu-id="c430f-110">Data privacy regulations impacting the use of monitoring and response tools</span></span>

<span data-ttu-id="c430f-111">Ecco un elenco di esempio delle normative sulla privacy dei dati che possono riguardare i controlli di governance delle informazioni:</span><span class="sxs-lookup"><span data-stu-id="c430f-111">Here is a sample listing of data privacy regulations that may relate to information governance controls:</span></span>

- <span data-ttu-id="c430f-112">Articolo LGPD 46</span><span class="sxs-lookup"><span data-stu-id="c430f-112">LGPD Article 46</span></span>
- <span data-ttu-id="c430f-113">LGPD Articolo 48</span><span class="sxs-lookup"><span data-stu-id="c430f-113">LGPD Article 48</span></span>
- <span data-ttu-id="c430f-114">Articolo GDPR (5)(1)(f)</span><span class="sxs-lookup"><span data-stu-id="c430f-114">GDPR Article (5)(1)(f)</span></span>
- <span data-ttu-id="c430f-115">Articolo GDPR (15)(1)(e)</span><span class="sxs-lookup"><span data-stu-id="c430f-115">GDPR Article (15)(1)(e)</span></span>
- <span data-ttu-id="c430f-116">HIPAA-HITECH (45 C.F.R.</span><span class="sxs-lookup"><span data-stu-id="c430f-116">HIPAA-HITECH (45 C.F.R.</span></span> <span data-ttu-id="c430f-117">164.308(a)(1)(ii)(D))</span><span class="sxs-lookup"><span data-stu-id="c430f-117">164.308(a)(1)(ii)(D))</span></span>
- <span data-ttu-id="c430f-118">HIPAA-HITECH (45 C.F.R.</span><span class="sxs-lookup"><span data-stu-id="c430f-118">HIPAA-HITECH (45 C.F.R.</span></span> <span data-ttu-id="c430f-119">164.308(a)(6)(ii)</span><span class="sxs-lookup"><span data-stu-id="c430f-119">164.308(a)(6)(ii)</span></span>
- <span data-ttu-id="c430f-120">HIPAA-HITECH (45 C.F.R.</span><span class="sxs-lookup"><span data-stu-id="c430f-120">HIPAA-HITECH (45 C.F.R.</span></span> <span data-ttu-id="c430f-121">164.312(b))</span><span class="sxs-lookup"><span data-stu-id="c430f-121">164.312(b))</span></span>
- <span data-ttu-id="c430f-122">CCPA (1798.105(c))</span><span class="sxs-lookup"><span data-stu-id="c430f-122">CCPA (1798.105(c))</span></span>

<span data-ttu-id="c430f-123">Per ulteriori informazioni, vedere [Valutare i rischi per la privacy dei dati e identificare le informazioni riservate.](information-protection-deploy-assess.md)</span><span class="sxs-lookup"><span data-stu-id="c430f-123">For more information, see [Assess data privacy risks and identify sensitive information](information-protection-deploy-assess.md).</span></span>

<span data-ttu-id="c430f-124">Le normative sulla privacy dei dati in genere prescindono quanto segue per il monitoraggio e la risposta:</span><span class="sxs-lookup"><span data-stu-id="c430f-124">The data privacy regulations generally call for the following for monitoring and response:</span></span>

- <span data-ttu-id="c430f-125">Controllo, avviso e creazione di report per le attività relative all'archiviazione, alla condivisione e all'elaborazione dei dati personali</span><span class="sxs-lookup"><span data-stu-id="c430f-125">Auditing, alerting, and reporting for activities related to the storage, sharing and processing of personal data</span></span>
- <span data-ttu-id="c430f-126">La possibilità di rispondere a una richiesta dell'oggetto dei dati (DSR) e, in alcuni casi, eseguire misure di indagine e altre misure amministrative per conformarsi a tali richieste.</span><span class="sxs-lookup"><span data-stu-id="c430f-126">The ability to respond to a data subject request (DSR) and in some cases, perform investigative and other administrative measures to comply with such requests.</span></span>

<span data-ttu-id="c430f-127">L'organizzazione può anche desiderare di eseguire attività di monitoraggio e risposta per altri scopi, ad esempio per altre esigenze di conformità o per motivi aziendali.</span><span class="sxs-lookup"><span data-stu-id="c430f-127">Your organization may also wish to perform monitoring and response activities for other purposes, such as other compliance needs or for business reasons.</span></span> <span data-ttu-id="c430f-128">La definizione dello schema di monitoraggio e risposta per la privacy dei dati deve essere eseguita nell'ambito del monitoraggio generale e della pianificazione, implementazione e gestione delle risposte.</span><span class="sxs-lookup"><span data-stu-id="c430f-128">Establishing your monitoring and response scheme for data privacy should be done as part of overall monitoring and response planning, implementation, and management.</span></span>

<span data-ttu-id="c430f-129">Per iniziare a usare uno schema di monitoraggio e risposta in Microsoft 365 per le normative sulla privacy dei dati, in questo articolo sono elencate le funzionalità utili in Microsoft 365 per rispondere a domande quali:</span><span class="sxs-lookup"><span data-stu-id="c430f-129">To help you get started with a monitoring and response scheme in Microsoft 365 for data privacy regulations, this article lists useful capabilities in Microsoft 365 to answer questions such as:</span></span> 

- <span data-ttu-id="c430f-130">Che tipo di tecniche quotidiane di monitoraggio, indagine e segnalazione sono disponibili per i diversi tipi di dati e origini?</span><span class="sxs-lookup"><span data-stu-id="c430f-130">What sort of day-to-day monitoring, investigative and reporting techniques are available for the different data types and sources?</span></span>
- <span data-ttu-id="c430f-131">Quali meccanismi saranno necessari per gestire le richieste dell'oggetto dei dati (DSR) ed eventuali azioni correttive, ad esempio l'anonimizzazione, la redazione e l'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="c430f-131">What mechanisms will be needed to handle data subject requests (DSRs) and any remedial actions, such as anonymization, redaction, and deletion.</span></span>

## <a name="auditing-and-alert-policies-in-the-security-and-compliance-center"></a><span data-ttu-id="c430f-132">Criteri di controllo e avviso nel Centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="c430f-132">Auditing and Alert Policies in the Security and Compliance Center</span></span>

<span data-ttu-id="c430f-133">Vedere questi articoli per configurare il controllo, il controllo avanzato e i criteri di avviso:</span><span class="sxs-lookup"><span data-stu-id="c430f-133">See these articles for setting up auditing, advanced auditing, and alert policies:</span></span>

- [<span data-ttu-id="c430f-134">Controllo unificato</span><span class="sxs-lookup"><span data-stu-id="c430f-134">Unified auditing</span></span>](../compliance/search-the-audit-log-in-security-and-compliance.md)
- [<span data-ttu-id="c430f-135">Controllo delle cassette postali</span><span class="sxs-lookup"><span data-stu-id="c430f-135">Mailbox auditing</span></span>](../compliance/enable-mailbox-auditing.md)
- [<span data-ttu-id="c430f-136">Controllo avanzato</span><span class="sxs-lookup"><span data-stu-id="c430f-136">Advanced audit</span></span>](../compliance/advanced-audit.md)
- [<span data-ttu-id="c430f-137">Criteri di avviso</span><span class="sxs-lookup"><span data-stu-id="c430f-137">Alert policies</span></span>](../compliance/alert-policies.md)

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a><span data-ttu-id="c430f-138">Richieste degli soggetti dei dati per il GDPR e il CCPA</span><span class="sxs-lookup"><span data-stu-id="c430f-138">Data subject requests for the GDPR and CCPA</span></span>

<span data-ttu-id="c430f-139">Per informazioni sulla risposta a una richiesta DSR in Microsoft 365, vedere Richieste dell'soggetto dei dati per il GDPR e [il CCPA.](/compliance/regulatory/gdpr-dsr-Office365)</span><span class="sxs-lookup"><span data-stu-id="c430f-139">See [Data Subject Requests for the GDPR and CCPA](/compliance/regulatory/gdpr-dsr-Office365) for information on responding to a DSR in Microsoft 365.</span></span>

## <a name="manage-deleted-users-in-microsoft-stream"></a><span data-ttu-id="c430f-140">Gestire gli utenti eliminati in Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="c430f-140">Manage deleted users in Microsoft Stream</span></span>

<span data-ttu-id="c430f-141">Per Microsoft Stream, quando un utente viene eliminato da Azure Active Directory (Azure AD), se il nome è stato associato a un video stream pubblicato prima di tale punto, l'indirizzo di posta elettronica rimane associato al video.</span><span class="sxs-lookup"><span data-stu-id="c430f-141">For Microsoft Stream, when a user is deleted from Azure Active Directory (Azure AD), if their name was associated with a posted Stream video prior to that point, their email address remains associated with the video.</span></span> <span data-ttu-id="c430f-142">Vedi [Gestire gli utenti eliminati da Microsoft Stream](/stream/managing-deleted-users) per rimuoverlo.</span><span class="sxs-lookup"><span data-stu-id="c430f-142">See [Manage deleted users from Microsoft Stream](/stream/managing-deleted-users) to remove it.</span></span>

## <a name="insider-risk-management-as-an-investigative-tool"></a><span data-ttu-id="c430f-143">Gestione dei rischi insider come strumento di indagine</span><span class="sxs-lookup"><span data-stu-id="c430f-143">Insider risk management as an investigative tool</span></span>

<span data-ttu-id="c430f-144">[La gestione dei](../compliance/insider-risk-management.md) rischi insider in Microsoft 365 è una funzionalità dell'interfaccia di amministrazione di Conformità Microsoft che consente di ridurre al minimo i rischi interni consentendo di rilevare, analizzare e intervenire sulle attività rischiose nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c430f-144">[Insider risk management in Microsoft 365](../compliance/insider-risk-management.md) is a feature of the Microsoft Compliance admin center to help you minimize internal risk by enabling you to detect, investigate, and take action on risky activities in your organization.</span></span>