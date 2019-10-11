---
title: Creazione di rapporti e traccia dei messaggi in Exchange Online Protection
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: f40253f2-50a1-426e-9979-be74ba74cb61
description: Microsoft (EOP) Exchange Online Protection offre diversi rapporti che consentono di determinare lo stato generale e l'integrità dell'organizzazione. Sono inoltre disponibili strumenti per la risoluzione dei problemi relativi a eventi specifici, ad esempio il mancato recapito di un messaggio ai destinatari desiderati, e report di controllo per assicurare il rispetto dei requisiti di conformità. Nella tabella seguente vengono descritti i report e gli strumenti per la risoluzione dei problemi disponibili per gli amministratori di EOP.
ms.openlocfilehash: 81b4ce3d22fbf33dc2f22a4b0a73a3459b1874ee
ms.sourcegitcommit: cbf117a4cd92a907115c9f10752f3c557361e586
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/10/2019
ms.locfileid: "37441413"
---
# <a name="reporting-and-message-trace-in-exchange-online-protection"></a><span data-ttu-id="1c1c6-105">Creazione di rapporti e traccia dei messaggi in Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="1c1c6-105">Reporting and message trace in Exchange Online Protection</span></span>

<span data-ttu-id="1c1c6-106">Microsoft (EOP) Exchange Online Protection offre diversi rapporti che consentono di determinare lo stato generale e l'integrità dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1c1c6-106">Microsoft Exchange Online Protection (EOP) offers many different reports that can help you determine the overall status and health of your organization.</span></span> <span data-ttu-id="1c1c6-107">Sono inoltre disponibili strumenti per la risoluzione dei problemi relativi a eventi specifici, ad esempio il mancato recapito di un messaggio ai destinatari desiderati, e report di controllo per assicurare il rispetto dei requisiti di conformità.</span><span class="sxs-lookup"><span data-stu-id="1c1c6-107">There are also tools to help you troubleshoot specific events (such as a message not arriving to its intended recipients), and auditing reports to aid with compliance requirements.</span></span>

## <a name="usage-reports"></a><span data-ttu-id="1c1c6-108">Report sull'uso</span><span class="sxs-lookup"><span data-stu-id="1c1c6-108">Usage reports</span></span>

<span data-ttu-id="1c1c6-109">**Attività gruppi di office 365**: consente di visualizzare informazioni sul numero di gruppi di Office 365 creati e utilizzati.</span><span class="sxs-lookup"><span data-stu-id="1c1c6-109">**Office 365 groups activity**: View information about the number of Office 365 groups that are created and used.</span></span>

<span data-ttu-id="1c1c6-110">**Attività di posta elettronica**: consente di visualizzare informazioni sul numero di messaggi inviati, ricevuti e letti nell'intera organizzazione e per utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="1c1c6-110">**Email activity**: View information about the number of messages sent, received and read in your whole organization, and by specific users.</span></span>

<span data-ttu-id="1c1c6-111">**Utilizzo delle app di posta elettronica**: consente di visualizzare le informazioni sulle app di posta elettronica utilizzate.</span><span class="sxs-lookup"><span data-stu-id="1c1c6-111">**Email app usage**: View information about the email apps that are used.</span></span> <span data-ttu-id="1c1c6-112">Questi dati includono il numero totale di connessioni per ogni applicazione e le versioni di Outlook con cui si stabilisce la connessione.</span><span class="sxs-lookup"><span data-stu-id="1c1c6-112">This include the total number of connections for each app, and the versions of Outlook that are connecting.</span></span>

<span data-ttu-id="1c1c6-113">**Utilizzo delle cassette postali**: consente di visualizzare informazioni sull'archiviazione utilizzata, sul consumo di quote, sul numero di elementi e sull'ultima attività (invio o lettura) per le cassette postali.</span><span class="sxs-lookup"><span data-stu-id="1c1c6-113">**Mailbox usage**: View information about storage used, quota consumption, item count, and last activity (send or read activity) for mailboxes.</span></span>

<span data-ttu-id="1c1c6-114">Per ulteriori informazioni, vedere le risorse seguenti:</span><span class="sxs-lookup"><span data-stu-id="1c1c6-114">See the following resources for more information:</span></span>

- [<span data-ttu-id="1c1c6-115">Rapporti di Office 365 nell'interfaccia di amministrazione-gruppi di Office 365</span><span class="sxs-lookup"><span data-stu-id="1c1c6-115">Office 365 Reports in the admin center - Office 365 groups</span></span>](https://go.microsoft.com/fwlink/p/?linkid=861610)

- [<span data-ttu-id="1c1c6-116">Report di Office 365 nell'interfaccia di amministrazione - Attività di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="1c1c6-116">Office 365 Reports in the Admin Center - Email activity</span></span>](https://go.microsoft.com/fwlink/p/?linkid=859706)

- [<span data-ttu-id="1c1c6-117">Report di Office 365 nell'interfaccia di amministrazione - Utilizzo delle applicazioni di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="1c1c6-117">Office 365 Reports in the Admin Center - Email apps usage</span></span>](https://go.microsoft.com/fwlink/p/?linkid=859707)

- [<span data-ttu-id="1c1c6-118">Report di Office 365 nell'interfaccia di amministrazione - Utilizzo delle cassette postali</span><span class="sxs-lookup"><span data-stu-id="1c1c6-118">Office 365 Reports in the Admin Center - Mailbox usage</span></span>](https://go.microsoft.com/fwlink/p/?linkid=859708)

## <a name="security--compliance-reports-in-the-microsoft-365-admin-center"></a><span data-ttu-id="1c1c6-119">Rapporti di conformità & di sicurezza nell'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1c1c6-119">Security & compliance reports in the Microsoft 365 admin center</span></span>

<span data-ttu-id="1c1c6-120">Questi report avanzati forniscono un'esperienza di report interattiva per gli amministratori di EOP, che include informazioni di riepilogo e la possibilità di eseguire il drill-down per ulteriori dettagli.</span><span class="sxs-lookup"><span data-stu-id="1c1c6-120">These enhanced reports provide an interactive reporting experience for EOP admins, which includes summary information, and the ability to drill down for more details.</span></span>

<span data-ttu-id="1c1c6-121">**Advanced Threat Protection (ATP)**: visualizzare informazioni sui collegamenti sicuri e sugli allegati sicuri che fanno parte di ATP.</span><span class="sxs-lookup"><span data-stu-id="1c1c6-121">**Advanced Threat Protection (ATP)**: View information about safe links and safe attachments that are part of ATP.</span></span>

<span data-ttu-id="1c1c6-122">**EOP**: consente di visualizzare informazioni su rilevamenti di malware, posta contraffatta, rilevamenti di posta indesiderata e flusso di posta da e verso l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1c1c6-122">**EOP**: View information about malware detections, spoofed mail, spam detections, and mail flow to and from your organization.</span></span>

[<span data-ttu-id="1c1c6-123">Visualizzare i report per Advanced Threat Protection e Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="1c1c6-123">View reports for Advanced Threat Protection and Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/p/?linkid=852409)

## <a name="custom-reports-using-microsoft-graph"></a><span data-ttu-id="1c1c6-124">Report personalizzati tramite Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="1c1c6-124">Custom reports using Microsoft Graph</span></span>

<span data-ttu-id="1c1c6-125">Creare report a livello di programmazione che sono disponibili nell'interfaccia di amministrazione di Microsoft 365 tramite Microsoft Graph vedere gli argomenti secondari di utilizzo dei [report sull'utilizzo di Office 365 in Microsoft Graph](https://go.microsoft.com/fwlink/p/?linkid=865135)</span><span class="sxs-lookup"><span data-stu-id="1c1c6-125">Programmatically create reports that are available in the Microsoft 365 admin center by using Microsoft Graph  See the subtopics of [Working with Office 365 usage reports in Microsoft Graph](https://go.microsoft.com/fwlink/p/?linkid=865135)</span></span>

## <a name="custom-reports-using-reporting-web-services"></a><span data-ttu-id="1c1c6-126">Rapporti personalizzati tramite servizi Web Reporting</span><span class="sxs-lookup"><span data-stu-id="1c1c6-126">Custom reports using reporting web services</span></span>

<span data-ttu-id="1c1c6-127">Creare report a livello di programmazione dai cmdlet di report di Exchange Online Protection PowerShell disponibili utilizzando il filtro delle query REST/ODATA2.</span><span class="sxs-lookup"><span data-stu-id="1c1c6-127">Programmatically create reports from the available Exchange Online Protection PowerShell reporting cmdlets by using REST/ODATA2 query filtering.</span></span>

<span data-ttu-id="1c1c6-128">Vedere [servizi Web di Reporting di Office 365](https://go.microsoft.com/fwlink/p/?LinkId=279926)</span><span class="sxs-lookup"><span data-stu-id="1c1c6-128">See [Office 365 Reporting Web Services](https://go.microsoft.com/fwlink/p/?LinkId=279926)</span></span>

## <a name="message-trace"></a><span data-ttu-id="1c1c6-129">Traccia dei messaggi</span><span class="sxs-lookup"><span data-stu-id="1c1c6-129">Message trace</span></span>

<span data-ttu-id="1c1c6-130">Consente di seguire il percorso dei messaggi all'interno di EOP.</span><span class="sxs-lookup"><span data-stu-id="1c1c6-130">Follows email messages as they travel through EOP.</span></span> <span data-ttu-id="1c1c6-131">È possibile stabilire se un messaggio di posta elettronica è stato ricevuto, rifiutato, ritardato o recapitato dal servizio.</span><span class="sxs-lookup"><span data-stu-id="1c1c6-131">You can determine if an email message was received, rejected, deferred, or delivered by the service.</span></span> <span data-ttu-id="1c1c6-132">Mostra inoltre quali azioni sono state eseguite sul messaggio prima del raggiungimento dello stato finale.</span><span class="sxs-lookup"><span data-stu-id="1c1c6-132">It also shows what actions were taken on the message before it reached its final status.</span></span>

<span data-ttu-id="1c1c6-133">È possibile utilizzare queste informazioni per rispondere in modo efficiente alle domande dell'utente, risolvere i problemi relativi al flusso di posta, convalidare le modifiche apportate ai criteri e ridurre la necessità di contattare il supporto tecnico per assistenza.</span><span class="sxs-lookup"><span data-stu-id="1c1c6-133">You can use this information to efficiently answer your user's questions, troubleshoot mail flow issues, validate policy changes, and alleviates the need to contact technical support for assistance.</span></span>

<span data-ttu-id="1c1c6-134">Vedere [traccia di un messaggio di posta elettronica](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/trace-an-email-message)</span><span class="sxs-lookup"><span data-stu-id="1c1c6-134">See [Trace an email message](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/trace-an-email-message)</span></span>

## <a name="audit-logging"></a><span data-ttu-id="1c1c6-135">Registrazione di controllo</span><span class="sxs-lookup"><span data-stu-id="1c1c6-135">Audit logging</span></span>

<span data-ttu-id="1c1c6-136">Consente di tenere traccia di modifiche specifiche apportate all'organizzazione dagli amministratori.</span><span class="sxs-lookup"><span data-stu-id="1c1c6-136">Tracks specific changes made by admins to your organization.</span></span> <span data-ttu-id="1c1c6-137">Questi report consentono di risolvere problemi di configurazione o individuare la causa di problemi relativi alla sicurezza o alla conformità.</span><span class="sxs-lookup"><span data-stu-id="1c1c6-137">These reports can help you troubleshoot configuration issues or find the cause of security or compliance-related problems.</span></span> <span data-ttu-id="1c1c6-138">Vedere [rapporti di controllo in EOP](auditing-reports-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="1c1c6-138">See [Auditing reports in EOP](auditing-reports-in-eop.md).</span></span>

## <a name="reporting-and-message-trace-data-availability-and-latency"></a><span data-ttu-id="1c1c6-139">Rapporti e latenza e disponibilità dei dati dei messaggi</span><span class="sxs-lookup"><span data-stu-id="1c1c6-139">Reporting and message trace data availability and latency</span></span>

<span data-ttu-id="1c1c6-140">La tabella seguente descrive quando in EOP le funzionalità di creazione rapporti e dati di traccia dei messaggi sono disponibili e per quanto tempo.</span><span class="sxs-lookup"><span data-stu-id="1c1c6-140">The following table describes when EOP reporting and message trace data is available and for how long.</span></span>

||||
|:-----|:-----|:-----|
|<span data-ttu-id="1c1c6-141">**Tipo di rapporto**</span><span class="sxs-lookup"><span data-stu-id="1c1c6-141">**Report type**</span></span>|<span data-ttu-id="1c1c6-142">**Dati disponibili per (periodo passato)**</span><span class="sxs-lookup"><span data-stu-id="1c1c6-142">**Data available for (look back period)**</span></span>|<span data-ttu-id="1c1c6-143">**Latenza**</span><span class="sxs-lookup"><span data-stu-id="1c1c6-143">**Latency**</span></span>|
|<span data-ttu-id="1c1c6-144">Rapporti di riepilogo sulla protezione della posta</span><span class="sxs-lookup"><span data-stu-id="1c1c6-144">Mail protection summary reports</span></span>|<span data-ttu-id="1c1c6-145">90 giorni</span><span class="sxs-lookup"><span data-stu-id="1c1c6-145">90 days</span></span>|<span data-ttu-id="1c1c6-p106">L'aggregazione dei dati dei messaggi è quasi completa entro 24-48 ore. Alcune modifiche aggregate incrementali minori possono verificarsi in un periodo massimo di 5 giorni.</span><span class="sxs-lookup"><span data-stu-id="1c1c6-p106">Message data aggregation is mostly complete within 24-48 hours. Some minor incremental aggregated changes may occur for up to 5 days.</span></span>|
|<span data-ttu-id="1c1c6-148">Rapporti dettagliati sulla protezione della posta</span><span class="sxs-lookup"><span data-stu-id="1c1c6-148">Mail protection detail reports</span></span>|<span data-ttu-id="1c1c6-149">90 giorni</span><span class="sxs-lookup"><span data-stu-id="1c1c6-149">90 days</span></span>|<span data-ttu-id="1c1c6-p107">Per dati dettagliati creati da meno di 7 giorni, i dati devono essere visualizzati entro 24 ore ma potrebbero non essere completi fino a 48 ore. Alcune modifiche incrementali minori possono verificarsi in un periodo massimo di 5 giorni.</span><span class="sxs-lookup"><span data-stu-id="1c1c6-p107">For detail data that's less than 7 days old, data should appear within 24 hours but may not be complete until 48 hours. Some minor incremental changes may occur for up to 5 days.</span></span> <br/><br/> <span data-ttu-id="1c1c6-152">Per visualizzare rapporti dettagliati per messaggi creati da più di 7 giorni, i risultati potrebbero richiedere alcune ore.</span><span class="sxs-lookup"><span data-stu-id="1c1c6-152">To view detail reports for messages that are greater than 7 days old, results may take up to a few hours.</span></span>|
|<span data-ttu-id="1c1c6-153">Dati di traccia dei messaggi</span><span class="sxs-lookup"><span data-stu-id="1c1c6-153">Message trace data</span></span>|<span data-ttu-id="1c1c6-154">90 giorni</span><span class="sxs-lookup"><span data-stu-id="1c1c6-154">90 days</span></span>|<span data-ttu-id="1c1c6-155">Quando si esegue la traccia dei messaggi per i messaggi creati da meno di 7 giorni, i messaggi devono essere visualizzati entro un periodo compreso tra 5 e 30 minuti.</span><span class="sxs-lookup"><span data-stu-id="1c1c6-155">When you run a message trace for messages that are less than 7 days old, the messages should appear within 5-30 minutes.</span></span><br/><br/> <span data-ttu-id="1c1c6-156">Quando si esegua la traccia dei messaggi per messaggi creati da più di 7 giorni, i risultati potrebbero richiedere alcune ore.</span><span class="sxs-lookup"><span data-stu-id="1c1c6-156">When you run a message trace for messages that are greater than 7 days old, results may take up to a few hours.</span></span>|

> [!NOTE]
> <span data-ttu-id="1c1c6-157">La disponibilità e la latenza dei dati sono le stesse se richieste tramite l'interfaccia di amministrazione di Microsoft 365 o Remote PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1c1c6-157">Data availability and latency is the same whether requested via the Microsoft 365 admin center or remote PowerShell.</span></span>
