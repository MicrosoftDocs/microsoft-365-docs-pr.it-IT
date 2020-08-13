---
title: Creazione di report e traccia messaggio
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: f40253f2-50a1-426e-9979-be74ba74cb61
ms.custom:
- seo-marvel-apr2020
description: In questo articolo vengono fornite informazioni sui report e gli strumenti per la risoluzione dei problemi disponibili per gli amministratori di Microsoft Exchange Online Protection (EOP).
ms.openlocfilehash: ddf8c021681bb600548b134d678d1e0fb0f29d0c
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2020
ms.locfileid: "46652802"
---
# <a name="reporting-and-message-trace-in-eop"></a><span data-ttu-id="a8a87-103">Creazione di report e traccia dei messaggi in EOP</span><span class="sxs-lookup"><span data-stu-id="a8a87-103">Reporting and message trace in EOP</span></span>

<span data-ttu-id="a8a87-104">In Microsoft 365 organizzazioni con cassette postali in Exchange Online o standalone Exchange Online Protection (EOP) organizzazioni senza cassette postali di Exchange Online, EOP offre numerosi rapporti diversi che consentono di determinare lo stato generale e l'integrità dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a8a87-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP offers many different reports that can help you determine the overall status and health of your organization.</span></span> <span data-ttu-id="a8a87-105">Sono inoltre disponibili strumenti per la risoluzione dei problemi relativi a eventi specifici, ad esempio il mancato recapito di un messaggio ai destinatari desiderati, e report di controllo per assicurare il rispetto dei requisiti di conformità.</span><span class="sxs-lookup"><span data-stu-id="a8a87-105">There are also tools to help you troubleshoot specific events (such as a message not arriving to its intended recipients), and auditing reports to aid with compliance requirements.</span></span>

## <a name="usage-reports"></a><span data-ttu-id="a8a87-106">Report sull'uso</span><span class="sxs-lookup"><span data-stu-id="a8a87-106">Usage reports</span></span>

<span data-ttu-id="a8a87-107">**Attività gruppi microsoft 365**: consente di visualizzare informazioni sul numero di gruppi di Microsoft 365 creati e utilizzati.</span><span class="sxs-lookup"><span data-stu-id="a8a87-107">**Microsoft 365 groups activity**: View information about the number of Microsoft 365 groups that are created and used.</span></span>

<span data-ttu-id="a8a87-108">**Attività di posta elettronica**: consente di visualizzare informazioni sul numero di messaggi inviati, ricevuti e letti nell'intera organizzazione e per utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="a8a87-108">**Email activity**: View information about the number of messages sent, received and read in your whole organization, and by specific users.</span></span>

<span data-ttu-id="a8a87-109">**Utilizzo delle app di posta elettronica**: consente di visualizzare le informazioni sulle app di posta elettronica utilizzate.</span><span class="sxs-lookup"><span data-stu-id="a8a87-109">**Email app usage**: View information about the email apps that are used.</span></span> <span data-ttu-id="a8a87-110">Questi dati includono il numero totale di connessioni per ogni applicazione e le versioni di Outlook con cui si stabilisce la connessione.</span><span class="sxs-lookup"><span data-stu-id="a8a87-110">This include the total number of connections for each app, and the versions of Outlook that are connecting.</span></span>

<span data-ttu-id="a8a87-111">**Utilizzo delle cassette postali**: consente di visualizzare informazioni sull'archiviazione utilizzata, sul consumo di quote, sul numero di elementi e sull'ultima attività (invio o lettura) per le cassette postali.</span><span class="sxs-lookup"><span data-stu-id="a8a87-111">**Mailbox usage**: View information about storage used, quota consumption, item count, and last activity (send or read activity) for mailboxes.</span></span>

<span data-ttu-id="a8a87-112">Per ulteriori informazioni, vedere le risorse seguenti:</span><span class="sxs-lookup"><span data-stu-id="a8a87-112">See the following resources for more information:</span></span>

- [<span data-ttu-id="a8a87-113">Report di Microsoft 365 nell'interfaccia di amministrazione-gruppi Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a8a87-113">Microsoft 365 Reports in the admin center - Microsoft 365 groups</span></span>](https://docs.microsoft.com/microsoft-365/admin/activity-reports/office-365-groups)

- [<span data-ttu-id="a8a87-114">Rapporti Microsoft 365 nell'interfaccia di amministrazione-attività di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="a8a87-114">Microsoft 365 Reports in the admin center - Email activity</span></span>](https://docs.microsoft.com/microsoft-365/admin/activity-reports/email-activity)

- [<span data-ttu-id="a8a87-115">Report di Microsoft 365 nell'interfaccia di amministrazione-utilizzo delle app di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="a8a87-115">Microsoft 365 Reports in the admin center - Email apps usage</span></span>](https://docs.microsoft.com/microsoft-365/admin/activity-reports/email-apps-usage)

- [<span data-ttu-id="a8a87-116">Report di Microsoft 365 nell'interfaccia di amministrazione-utilizzo delle cassette postali</span><span class="sxs-lookup"><span data-stu-id="a8a87-116">Microsoft 365 Reports in the admin center - Mailbox usage</span></span>](https://docs.microsoft.com/microsoft-365/admin/activity-reports/mailbox-usage)

## <a name="security--compliance-reports-in-the-microsoft-365-admin-center"></a><span data-ttu-id="a8a87-117">Rapporti di conformità & di sicurezza nell'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a8a87-117">Security & compliance reports in the Microsoft 365 admin center</span></span>

<span data-ttu-id="a8a87-118">Questi report avanzati forniscono un'esperienza di report interattiva per gli amministratori di EOP, che include informazioni di riepilogo e la possibilità di eseguire il drill-down per ulteriori dettagli.</span><span class="sxs-lookup"><span data-stu-id="a8a87-118">These enhanced reports provide an interactive reporting experience for EOP admins, which includes summary information, and the ability to drill down for more details.</span></span>

<span data-ttu-id="a8a87-119">**Advanced Threat Protection (ATP)**: visualizzare informazioni sui collegamenti sicuri e sugli allegati sicuri che fanno parte di ATP.</span><span class="sxs-lookup"><span data-stu-id="a8a87-119">**Advanced Threat Protection (ATP)**: View information about safe links and safe attachments that are part of ATP.</span></span>

<span data-ttu-id="a8a87-120">**EOP**: consente di visualizzare informazioni su rilevamenti di malware, posta contraffatta, rilevamenti di posta indesiderata e flusso di posta da e verso l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a8a87-120">**EOP**: View information about malware detections, spoofed mail, spam detections, and mail flow to and from your organization.</span></span>

[<span data-ttu-id="a8a87-121">Visualizzare i report per Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="a8a87-121">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)

## <a name="custom-reports-using-microsoft-graph"></a><span data-ttu-id="a8a87-122">Report personalizzati tramite Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="a8a87-122">Custom reports using Microsoft Graph</span></span>

<span data-ttu-id="a8a87-123">Creare report a livello di programmazione che sono disponibili nell'interfaccia di amministrazione tramite Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="a8a87-123">Programmatically create reports that are available in the admin center by using Microsoft Graph.</span></span> <span data-ttu-id="a8a87-124">Per ulteriori informazioni, vedere [Panoramica di Microsoft Graph](https://docs.microsoft.com/graph/overview) e utilizzo dei [report sull'utilizzo di Office 365 in Microsoft Graph](https://docs.microsoft.com/graph/api/resources/report).</span><span class="sxs-lookup"><span data-stu-id="a8a87-124">For more information, see [Overview of Microsoft Graph](https://docs.microsoft.com/graph/overview) and [Working with Office 365 usage reports in Microsoft Graph](https://docs.microsoft.com/graph/api/resources/report).</span></span>

## <a name="message-trace"></a><span data-ttu-id="a8a87-125">Traccia dei messaggi</span><span class="sxs-lookup"><span data-stu-id="a8a87-125">Message trace</span></span>

<span data-ttu-id="a8a87-126">Consente di seguire il percorso dei messaggi all'interno di EOP.</span><span class="sxs-lookup"><span data-stu-id="a8a87-126">Follows email messages as they travel through EOP.</span></span> <span data-ttu-id="a8a87-127">È possibile stabilire se un messaggio di posta elettronica è stato ricevuto, rifiutato, ritardato o recapitato dal servizio.</span><span class="sxs-lookup"><span data-stu-id="a8a87-127">You can determine if an email message was received, rejected, deferred, or delivered by the service.</span></span> <span data-ttu-id="a8a87-128">Mostra inoltre quali azioni sono state eseguite sul messaggio prima del raggiungimento dello stato finale.</span><span class="sxs-lookup"><span data-stu-id="a8a87-128">It also shows what actions were taken on the message before it reached its final status.</span></span>

<span data-ttu-id="a8a87-129">È possibile utilizzare queste informazioni per rispondere in modo efficiente alle domande dell'utente, risolvere i problemi relativi al flusso di posta, convalidare le modifiche apportate ai criteri e ridurre la necessità di contattare il supporto tecnico per assistenza.</span><span class="sxs-lookup"><span data-stu-id="a8a87-129">You can use this information to efficiently answer your user's questions, troubleshoot mail flow issues, validate policy changes, and alleviates the need to contact technical support for assistance.</span></span>

<span data-ttu-id="a8a87-130">Vedere [Message Trace in the Security & Compliance Center](message-trace-scc.md).</span><span class="sxs-lookup"><span data-stu-id="a8a87-130">See [Message trace in the Security & Compliance Center](message-trace-scc.md).</span></span>

## <a name="audit-logging"></a><span data-ttu-id="a8a87-131">Registrazione di controllo</span><span class="sxs-lookup"><span data-stu-id="a8a87-131">Audit logging</span></span>

<span data-ttu-id="a8a87-132">Consente di tenere traccia di modifiche specifiche apportate all'organizzazione dagli amministratori.</span><span class="sxs-lookup"><span data-stu-id="a8a87-132">Tracks specific changes made by admins to your organization.</span></span> <span data-ttu-id="a8a87-133">Questi report consentono di risolvere problemi di configurazione o individuare la causa di problemi relativi alla sicurezza o alla conformità.</span><span class="sxs-lookup"><span data-stu-id="a8a87-133">These reports can help you troubleshoot configuration issues or find the cause of security or compliance-related problems.</span></span> <span data-ttu-id="a8a87-134">Vedere [rapporti di controllo in EOP](auditing-reports-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="a8a87-134">See [Auditing reports in EOP](auditing-reports-in-eop.md).</span></span>

## <a name="reporting-and-message-trace-data-availability-and-latency"></a><span data-ttu-id="a8a87-135">Rapporti e latenza e disponibilità dei dati dei messaggi</span><span class="sxs-lookup"><span data-stu-id="a8a87-135">Reporting and message trace data availability and latency</span></span>

<span data-ttu-id="a8a87-136">La tabella seguente descrive quando in EOP le funzionalità di creazione rapporti e dati di traccia dei messaggi sono disponibili e per quanto tempo.</span><span class="sxs-lookup"><span data-stu-id="a8a87-136">The following table describes when EOP reporting and message trace data is available and for how long.</span></span>

****

|<span data-ttu-id="a8a87-137">Tipo di rapporto</span><span class="sxs-lookup"><span data-stu-id="a8a87-137">Report type</span></span>|<span data-ttu-id="a8a87-138">Dati disponibili per (periodo passato)</span><span class="sxs-lookup"><span data-stu-id="a8a87-138">Data available for (look back period)</span></span>|<span data-ttu-id="a8a87-139">Latenza</span><span class="sxs-lookup"><span data-stu-id="a8a87-139">Latency</span></span>|
|---|---|---|
|<span data-ttu-id="a8a87-140">Rapporti di riepilogo sulla protezione della posta</span><span class="sxs-lookup"><span data-stu-id="a8a87-140">Mail protection summary reports</span></span>|<span data-ttu-id="a8a87-141">90 giorni</span><span class="sxs-lookup"><span data-stu-id="a8a87-141">90 days</span></span>|<span data-ttu-id="a8a87-p106">L'aggregazione dei dati dei messaggi è quasi completa entro 24-48 ore. Alcune modifiche aggregate incrementali minori possono verificarsi in un periodo massimo di 5 giorni.</span><span class="sxs-lookup"><span data-stu-id="a8a87-p106">Message data aggregation is mostly complete within 24-48 hours. Some minor incremental aggregated changes may occur for up to 5 days.</span></span>|
|<span data-ttu-id="a8a87-144">Rapporti dettagliati sulla protezione della posta</span><span class="sxs-lookup"><span data-stu-id="a8a87-144">Mail protection detail reports</span></span>|<span data-ttu-id="a8a87-145">90 giorni</span><span class="sxs-lookup"><span data-stu-id="a8a87-145">90 days</span></span>|<span data-ttu-id="a8a87-p107">Per dati dettagliati creati da meno di 7 giorni, i dati devono essere visualizzati entro 24 ore ma potrebbero non essere completi fino a 48 ore. Alcune modifiche incrementali minori possono verificarsi in un periodo massimo di 5 giorni.</span><span class="sxs-lookup"><span data-stu-id="a8a87-p107">For detail data that's less than 7 days old, data should appear within 24 hours but may not be complete until 48 hours. Some minor incremental changes may occur for up to 5 days.</span></span> <br/><br/> <span data-ttu-id="a8a87-148">Per visualizzare rapporti dettagliati per messaggi creati da più di 7 giorni, i risultati potrebbero richiedere alcune ore.</span><span class="sxs-lookup"><span data-stu-id="a8a87-148">To view detail reports for messages that are greater than 7 days old, results may take up to a few hours.</span></span>|
|<span data-ttu-id="a8a87-149">Dati di traccia dei messaggi</span><span class="sxs-lookup"><span data-stu-id="a8a87-149">Message trace data</span></span>|<span data-ttu-id="a8a87-150">90 giorni</span><span class="sxs-lookup"><span data-stu-id="a8a87-150">90 days</span></span>|<span data-ttu-id="a8a87-151">Quando si esegue la traccia dei messaggi per i messaggi creati da meno di 7 giorni, i messaggi devono essere visualizzati entro un periodo compreso tra 5 e 30 minuti.</span><span class="sxs-lookup"><span data-stu-id="a8a87-151">When you run a message trace for messages that are less than 7 days old, the messages should appear within 5-30 minutes.</span></span><br/><br/> <span data-ttu-id="a8a87-152">Quando si esegua la traccia dei messaggi per messaggi creati da più di 7 giorni, i risultati potrebbero richiedere alcune ore.</span><span class="sxs-lookup"><span data-stu-id="a8a87-152">When you run a message trace for messages that are greater than 7 days old, results may take up to a few hours.</span></span>|
|

> [!NOTE]
> <span data-ttu-id="a8a87-153">La disponibilità e la latenza dei dati sono le stesse se richieste tramite l'interfaccia di amministrazione o Remote PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a8a87-153">Data availability and latency is the same whether requested via the admin center or remote PowerShell.</span></span>
