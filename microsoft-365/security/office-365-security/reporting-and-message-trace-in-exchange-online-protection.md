---
title: Creazione di report e traccia messaggio
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: f40253f2-50a1-426e-9979-be74ba74cb61
ms.custom:
- seo-marvel-apr2020
description: In questo articolo vengono riportati i report e gli strumenti per la risoluzione dei problemi disponibili per gli amministratori di Microsoft Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1307fa1431a4fdd46c9ab070a2986a015891568f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918679"
---
# <a name="reporting-and-message-trace-in-eop"></a><span data-ttu-id="5f1ec-103">Creazione di report e traccia dei messaggi in EOP</span><span class="sxs-lookup"><span data-stu-id="5f1ec-103">Reporting and message trace in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="5f1ec-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="5f1ec-104">**Applies to**</span></span>
- [<span data-ttu-id="5f1ec-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="5f1ec-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="5f1ec-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="5f1ec-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="5f1ec-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5f1ec-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="5f1ec-108">Nelle organizzazioni di Microsoft 365 con cassette postali in Exchange Online o in organizzazioni autonome di Exchange Online Protection (EOP) senza cassette postali di Exchange Online, EOP offre molti report diversi che consentono di determinare lo stato generale e l'integrità dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5f1ec-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP offers many different reports that can help you determine the overall status and health of your organization.</span></span> <span data-ttu-id="5f1ec-109">Sono inoltre disponibili strumenti per la risoluzione dei problemi relativi a eventi specifici, ad esempio il mancato recapito di un messaggio ai destinatari desiderati, e report di controllo per assicurare il rispetto dei requisiti di conformità.</span><span class="sxs-lookup"><span data-stu-id="5f1ec-109">There are also tools to help you troubleshoot specific events (such as a message not arriving to its intended recipients), and auditing reports to aid with compliance requirements.</span></span>

## <a name="usage-reports"></a><span data-ttu-id="5f1ec-110">Report sull'uso</span><span class="sxs-lookup"><span data-stu-id="5f1ec-110">Usage reports</span></span>

<span data-ttu-id="5f1ec-111">**Attività dei gruppi di Microsoft 365**: consente di visualizzare informazioni sul numero di gruppi di Microsoft 365 creati e utilizzati.</span><span class="sxs-lookup"><span data-stu-id="5f1ec-111">**Microsoft 365 groups activity**: View information about the number of Microsoft 365 groups that are created and used.</span></span>

<span data-ttu-id="5f1ec-112">**Attività di posta** elettronica : consente di visualizzare informazioni sul numero di messaggi inviati, ricevuti e letti nell'intera organizzazione e da utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="5f1ec-112">**Email activity**: View information about the number of messages sent, received and read in your whole organization, and by specific users.</span></span>

<span data-ttu-id="5f1ec-113">**Utilizzo dell'app di** posta elettronica : consente di visualizzare informazioni sulle app di posta elettronica usate.</span><span class="sxs-lookup"><span data-stu-id="5f1ec-113">**Email app usage**: View information about the email apps that are used.</span></span> <span data-ttu-id="5f1ec-114">Questi dati includono il numero totale di connessioni per ogni applicazione e le versioni di Outlook con cui si stabilisce la connessione.</span><span class="sxs-lookup"><span data-stu-id="5f1ec-114">This include the total number of connections for each app, and the versions of Outlook that are connecting.</span></span>

<span data-ttu-id="5f1ec-115">**Utilizzo delle cassette** postali: consente di visualizzare informazioni sull'archiviazione utilizzata, sul consumo di quote, sul conteggio degli elementi e sull'ultima attività (attività di invio o lettura) per le cassette postali.</span><span class="sxs-lookup"><span data-stu-id="5f1ec-115">**Mailbox usage**: View information about storage used, quota consumption, item count, and last activity (send or read activity) for mailboxes.</span></span>

<span data-ttu-id="5f1ec-116">Per ulteriori informazioni, vedere le risorse seguenti:</span><span class="sxs-lookup"><span data-stu-id="5f1ec-116">See the following resources for more information:</span></span>

- [<span data-ttu-id="5f1ec-117">Report di Microsoft 365 nell'interfaccia di amministrazione - Gruppi di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5f1ec-117">Microsoft 365 Reports in the admin center - Microsoft 365 groups</span></span>](../../admin/activity-reports/office-365-groups.md)

- [<span data-ttu-id="5f1ec-118">Report di Microsoft 365 nell'interfaccia di amministrazione - Attività di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="5f1ec-118">Microsoft 365 Reports in the admin center - Email activity</span></span>](../../admin/activity-reports/email-activity.md)

- [<span data-ttu-id="5f1ec-119">Report di Microsoft 365 nell'interfaccia di amministrazione - Utilizzo delle app di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="5f1ec-119">Microsoft 365 Reports in the admin center - Email apps usage</span></span>](../../admin/activity-reports/email-apps-usage.md)

- [<span data-ttu-id="5f1ec-120">Report di Microsoft 365 nell'interfaccia di amministrazione - Utilizzo delle cassette postali</span><span class="sxs-lookup"><span data-stu-id="5f1ec-120">Microsoft 365 Reports in the admin center - Mailbox usage</span></span>](../../admin/activity-reports/mailbox-usage.md)

## <a name="security--compliance-reports-in-the-microsoft-365-admin-center"></a><span data-ttu-id="5f1ec-121">Report di & sicurezza nell'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5f1ec-121">Security & compliance reports in the Microsoft 365 admin center</span></span>

<span data-ttu-id="5f1ec-122">Questi report migliorati offrono un'esperienza di creazione di report interattiva per gli amministratori di EOP, che include informazioni di riepilogo e la possibilità di eseguire il drill-down per ulteriori dettagli.</span><span class="sxs-lookup"><span data-stu-id="5f1ec-122">These enhanced reports provide an interactive reporting experience for EOP admins, which includes summary information, and the ability to drill down for more details.</span></span>

<span data-ttu-id="5f1ec-123">**Defender for Office 365**: Visualizzare informazioni su Collegamenti sicuri e allegati sicuri che fanno parte di Microsoft Defender per Office 365.</span><span class="sxs-lookup"><span data-stu-id="5f1ec-123">**Defender for Office 365**: View information about Safe Links and Safe Attachments that are part of Microsoft Defender for Office 365.</span></span>

<span data-ttu-id="5f1ec-124">**EOP:** consente di visualizzare informazioni sui rilevamenti di malware, posta contraffatta, rilevamenti di posta indesiderata e flusso di posta da e verso l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5f1ec-124">**EOP**: View information about malware detections, spoofed mail, spam detections, and mail flow to and from your organization.</span></span>

[<span data-ttu-id="5f1ec-125">Visualizzare i report per Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="5f1ec-125">View reports for Defender for Office 365</span></span>](view-reports-for-atp.md)

## <a name="custom-reports-using-microsoft-graph"></a><span data-ttu-id="5f1ec-126">Report personalizzati con Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="5f1ec-126">Custom reports using Microsoft Graph</span></span>

<span data-ttu-id="5f1ec-127">Creare report disponibili nell'interfaccia di amministrazione a livello di programmazione tramite Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="5f1ec-127">Programmatically create reports that are available in the admin center by using Microsoft Graph.</span></span> <span data-ttu-id="5f1ec-128">Per ulteriori informazioni, vedere [Overview of Microsoft Graph](/graph/overview) e Working with Office [365 usage reports in Microsoft Graph](/graph/api/resources/report).</span><span class="sxs-lookup"><span data-stu-id="5f1ec-128">For more information, see [Overview of Microsoft Graph](/graph/overview) and [Working with Office 365 usage reports in Microsoft Graph](/graph/api/resources/report).</span></span>

## <a name="message-trace"></a><span data-ttu-id="5f1ec-129">Traccia dei messaggi</span><span class="sxs-lookup"><span data-stu-id="5f1ec-129">Message trace</span></span>

<span data-ttu-id="5f1ec-130">Consente di seguire il percorso dei messaggi all'interno di EOP.</span><span class="sxs-lookup"><span data-stu-id="5f1ec-130">Follows email messages as they travel through EOP.</span></span> <span data-ttu-id="5f1ec-131">È possibile stabilire se un messaggio di posta elettronica è stato ricevuto, rifiutato, ritardato o recapitato dal servizio.</span><span class="sxs-lookup"><span data-stu-id="5f1ec-131">You can determine if an email message was received, rejected, deferred, or delivered by the service.</span></span> <span data-ttu-id="5f1ec-132">Mostra inoltre quali azioni sono state eseguite sul messaggio prima del raggiungimento dello stato finale.</span><span class="sxs-lookup"><span data-stu-id="5f1ec-132">It also shows what actions were taken on the message before it reached its final status.</span></span>

<span data-ttu-id="5f1ec-133">È possibile utilizzare queste informazioni per rispondere in modo efficiente alle domande dell'utente, risolvere i problemi relativi al flusso di posta, convalidare le modifiche apportate ai criteri e ridurre la necessità di contattare il supporto tecnico per assistenza.</span><span class="sxs-lookup"><span data-stu-id="5f1ec-133">You can use this information to efficiently answer your user's questions, troubleshoot mail flow issues, validate policy changes, and alleviates the need to contact technical support for assistance.</span></span>

<span data-ttu-id="5f1ec-134">Vedere [Traccia messaggio nel Centro sicurezza & conformità](message-trace-scc.md).</span><span class="sxs-lookup"><span data-stu-id="5f1ec-134">See [Message trace in the Security & Compliance Center](message-trace-scc.md).</span></span>

## <a name="audit-logging"></a><span data-ttu-id="5f1ec-135">Registrazione di controllo</span><span class="sxs-lookup"><span data-stu-id="5f1ec-135">Audit logging</span></span>

<span data-ttu-id="5f1ec-136">Consente di tenere traccia di modifiche specifiche apportate all'organizzazione dagli amministratori.</span><span class="sxs-lookup"><span data-stu-id="5f1ec-136">Tracks specific changes made by admins to your organization.</span></span> <span data-ttu-id="5f1ec-137">Questi report consentono di risolvere problemi di configurazione o individuare la causa di problemi relativi alla sicurezza o alla conformità.</span><span class="sxs-lookup"><span data-stu-id="5f1ec-137">These reports can help you troubleshoot configuration issues or find the cause of security or compliance-related problems.</span></span> <span data-ttu-id="5f1ec-138">Vedere [Report di controllo in EOP](auditing-reports-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="5f1ec-138">See [Auditing reports in EOP](auditing-reports-in-eop.md).</span></span>

## <a name="reporting-and-message-trace-data-availability-and-latency"></a><span data-ttu-id="5f1ec-139">Rapporti e latenza e disponibilità dei dati dei messaggi</span><span class="sxs-lookup"><span data-stu-id="5f1ec-139">Reporting and message trace data availability and latency</span></span>

<span data-ttu-id="5f1ec-140">La tabella seguente descrive quando in EOP le funzionalità di creazione rapporti e dati di traccia dei messaggi sono disponibili e per quanto tempo.</span><span class="sxs-lookup"><span data-stu-id="5f1ec-140">The following table describes when EOP reporting and message trace data is available and for how long.</span></span>

****

|<span data-ttu-id="5f1ec-141">Tipo di rapporto</span><span class="sxs-lookup"><span data-stu-id="5f1ec-141">Report type</span></span>|<span data-ttu-id="5f1ec-142">Dati disponibili per (periodo passato)</span><span class="sxs-lookup"><span data-stu-id="5f1ec-142">Data available for (look back period)</span></span>|<span data-ttu-id="5f1ec-143">Latenza</span><span class="sxs-lookup"><span data-stu-id="5f1ec-143">Latency</span></span>|
|---|---|---|
|<span data-ttu-id="5f1ec-144">Rapporti riepilogati sulla protezione della posta</span><span class="sxs-lookup"><span data-stu-id="5f1ec-144">Mail protection summary reports</span></span>|<span data-ttu-id="5f1ec-145">90 giorni</span><span class="sxs-lookup"><span data-stu-id="5f1ec-145">90 days</span></span>|<span data-ttu-id="5f1ec-p106">L'aggregazione dei dati dei messaggi è quasi completa entro 24-48 ore. Alcune modifiche aggregate incrementali minori possono verificarsi in un periodo massimo di 5 giorni.</span><span class="sxs-lookup"><span data-stu-id="5f1ec-p106">Message data aggregation is mostly complete within 24-48 hours. Some minor incremental aggregated changes may occur for up to 5 days.</span></span>|
|<span data-ttu-id="5f1ec-148">Rapporti dettagliati sulla protezione della posta</span><span class="sxs-lookup"><span data-stu-id="5f1ec-148">Mail protection detail reports</span></span>|<span data-ttu-id="5f1ec-149">90 giorni</span><span class="sxs-lookup"><span data-stu-id="5f1ec-149">90 days</span></span>|<span data-ttu-id="5f1ec-p107">Per dati dettagliati creati da meno di 7 giorni, i dati devono essere visualizzati entro 24 ore ma potrebbero non essere completi fino a 48 ore. Alcune modifiche incrementali minori possono verificarsi in un periodo massimo di 5 giorni.</span><span class="sxs-lookup"><span data-stu-id="5f1ec-p107">For detail data that's less than 7 days old, data should appear within 24 hours but may not be complete until 48 hours. Some minor incremental changes may occur for up to 5 days.</span></span> <p> <span data-ttu-id="5f1ec-152">Per visualizzare rapporti dettagliati per messaggi creati da più di 7 giorni, i risultati potrebbero richiedere alcune ore.</span><span class="sxs-lookup"><span data-stu-id="5f1ec-152">To view detail reports for messages that are greater than 7 days old, results may take up to a few hours.</span></span>|
|<span data-ttu-id="5f1ec-153">Dati di traccia dei messaggi</span><span class="sxs-lookup"><span data-stu-id="5f1ec-153">Message trace data</span></span>|<span data-ttu-id="5f1ec-154">90 giorni</span><span class="sxs-lookup"><span data-stu-id="5f1ec-154">90 days</span></span>|<span data-ttu-id="5f1ec-155">Quando si esegue la traccia dei messaggi per i messaggi creati da meno di 7 giorni, i messaggi devono essere visualizzati entro un periodo compreso tra 5 e 30 minuti.</span><span class="sxs-lookup"><span data-stu-id="5f1ec-155">When you run a message trace for messages that are less than 7 days old, the messages should appear within 5-30 minutes.</span></span><p> <span data-ttu-id="5f1ec-156">Quando si esegua la traccia dei messaggi per messaggi creati da più di 7 giorni, i risultati potrebbero richiedere alcune ore.</span><span class="sxs-lookup"><span data-stu-id="5f1ec-156">When you run a message trace for messages that are greater than 7 days old, results may take up to a few hours.</span></span>|
|

> [!NOTE]
> <span data-ttu-id="5f1ec-157">La disponibilità e la latenza dei dati sono le stesse richieste tramite l'interfaccia di amministrazione o PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="5f1ec-157">Data availability and latency is the same whether requested via the admin center or remote PowerShell.</span></span>