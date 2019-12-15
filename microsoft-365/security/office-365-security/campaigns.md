---
title: Visualizzazione campagne in Office 365 ATP
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: mcostea
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Informazioni su Visualizzazione campagne in Office 365 Advanced Threat Protection.
ms.openlocfilehash: 2d43b73a613ad6399a151a6bda39f236c7c913e8
ms.sourcegitcommit: b65c80051e53d9be223f4769f4d42a39f5a07735
ms.translationtype: MT + HT Review
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2019
ms.locfileid: "39962761"
---
# <a name="campaign-views-in-office-365-atp"></a><span data-ttu-id="0bf6b-103">Visualizzazione campagne in Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="0bf6b-103">Campaign Views in Office 365 ATP</span></span>

> [!NOTE]
> <span data-ttu-id="0bf6b-104">Le funzionalità qui descritte sono attualmente in anteprima e soggette a modifiche.</span><span class="sxs-lookup"><span data-stu-id="0bf6b-104">The features described in this topic are currently in preview, and are subject to change.</span></span>

<span data-ttu-id="0bf6b-105">Visualizzazione campagne è una funzionalità di Advanced Threat Protection (ATP) nel Centro sicurezza e conformità di Office 365 che identifica e categorizza gli attacchi di phishing nel servizio.</span><span class="sxs-lookup"><span data-stu-id="0bf6b-105">Campaign Views is a feature in Advanced Threat Protection (ATP) in the Office 365 Security & Compliance Center that identifies and categorizes phishing attacks in the service.</span></span> <span data-ttu-id="0bf6b-106">Visualizzazione campagne consente di:</span><span class="sxs-lookup"><span data-stu-id="0bf6b-106">Campaign Views can help you to:</span></span>

- <span data-ttu-id="0bf6b-107">Analizzare e rispondere in modo efficiente agli attacchi di phishing.</span><span class="sxs-lookup"><span data-stu-id="0bf6b-107">Efficiently investigate and respond to phishing attacks.</span></span>

- <span data-ttu-id="0bf6b-108">Comprendere meglio la portata dell'attacco.</span><span class="sxs-lookup"><span data-stu-id="0bf6b-108">Better understand the scope of the attack.</span></span>

- <span data-ttu-id="0bf6b-109">Visualizzare i dettagli dell'attacco.</span><span class="sxs-lookup"><span data-stu-id="0bf6b-109">Show value to decision makers.</span></span>

<span data-ttu-id="0bf6b-110">Visualizzazione campagne fornisce una visione d'insieme di un attacco in maniera più rapida e completa rispetto a un processo manuale.</span><span class="sxs-lookup"><span data-stu-id="0bf6b-110">Campaign Views lets you see the big picture of an attack faster and more complete than any human.</span></span>

## <a name="what-is-a-campaign"></a><span data-ttu-id="0bf6b-111">Cos'è una campagna?</span><span class="sxs-lookup"><span data-stu-id="0bf6b-111">What is a DSR?</span></span>

<span data-ttu-id="0bf6b-112">Una campagna è un attacco coordinato perpetrato tramite posta elettronica contro una o più organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="0bf6b-112">A campaign is a coordinated email attack against one or many organizations.</span></span> <span data-ttu-id="0bf6b-113">I messaggi di posta elettronica per rubare credenziali e dati aziendali sono diventati un business lucrativo.</span><span class="sxs-lookup"><span data-stu-id="0bf6b-113">Today, email attacks that steal credentials and company data are a big and lucrative business.</span></span> <span data-ttu-id="0bf6b-114">Con l'aumentare delle tecnologie impiegate per arrestare le minacce informatiche, gli attacchi informatici sono diventati così sofisticati da modificare i metodi impiegati per garantire il proprio successo.</span><span class="sxs-lookup"><span data-stu-id="0bf6b-114">As technologies increase in an effort to stop attacks, attackers are sophisticated enough to modify their methods in an effort to ensure continued success.</span></span>

<span data-ttu-id="0bf6b-115">Microsoft sfrutta le enormi quantità di dati anti-phishing, della posta indesiderata, anti-malware e dall'esperienza nell'intero servizio Office 365 per identificare campagne di scala mondiale.</span><span class="sxs-lookup"><span data-stu-id="0bf6b-115">Microsoft leverages the vast amounts of anti-phishing, anti-spam, and anti-malware data and experience across the entire Office 365 service world-wide to identify campaigns.</span></span> <span data-ttu-id="0bf6b-116">Le informazioni relative all'attacco sono analizzate e classificate in base a diversi fattori.</span><span class="sxs-lookup"><span data-stu-id="0bf6b-116">The attack information is analyzed and classified according to several factors.</span></span> <span data-ttu-id="0bf6b-117">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="0bf6b-117">For example:</span></span>

- <span data-ttu-id="0bf6b-118">**Origine dell'attacco**: indirizzi IP origine e domini di posta elettronica del mittente.</span><span class="sxs-lookup"><span data-stu-id="0bf6b-118">**Attack source**: Source IP addresses and sender email domains.</span></span>

- <span data-ttu-id="0bf6b-119">**Caratteristiche del messaggio di attacco**: il contenuto, lo stile e il tono dei messaggi di attacco.</span><span class="sxs-lookup"><span data-stu-id="0bf6b-119">**Attack message properties**: The content, style, and tone of the attack messages.</span></span>

- <span data-ttu-id="0bf6b-120">**Destinatari dell'attacco**: domini dei destinatari, funzione aziendale dei destinatari (amministratori, dirigenti e così via), tipi di azienda (grandi, piccole, pubbliche, private e così via) e settori.</span><span class="sxs-lookup"><span data-stu-id="0bf6b-120">**Attack recipients**: Recipient domains, recipient job functions (admins, executives, etc.), company types (large, small, public, private, etc.), and industries.</span></span>

- <span data-ttu-id="0bf6b-121">**Attacco payload**: collegamenti, allegati o altri payload dannosi.</span><span class="sxs-lookup"><span data-stu-id="0bf6b-121">**Attack payload**: Malicious links, attachments, or other payloads.</span></span>

## <a name="campaign-views-the-office-365-security--compliance-center"></a><span data-ttu-id="0bf6b-122">Visualizzazione campagne del Centro sicurezza e conformità di Office 365</span><span class="sxs-lookup"><span data-stu-id="0bf6b-122">Reports in the Office 365 Security & Compliance Center</span></span>

<span data-ttu-id="0bf6b-123">Visualizzazione campagne è disponibile nel [Centro sicurezza e conformità](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center) nelle seguenti posizioni:</span><span class="sxs-lookup"><span data-stu-id="0bf6b-123">Campaign Views is available in the [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center) at the following locations:</span></span>

- <span data-ttu-id="0bf6b-124">**Gestione delle minacce** \> **Esplora** \> **Visualizzazione** \> **Phishing** \> **Campagna in primo piano (anteprima)**</span><span class="sxs-lookup"><span data-stu-id="0bf6b-124">**Threat management** \> **Explorer** \> **View** \> **Phish** \> **Top campaign (Preview)**</span></span>

- <span data-ttu-id="0bf6b-125">**Gestione delle minacce** \> **Esplora** \> **Visualizzazione** \> **Tutti i messaggi di posta elettronica** \> **Campagna in primo piano (anteprima)**</span><span class="sxs-lookup"><span data-stu-id="0bf6b-125">**Threat management** \> **Explorer** \> **View** \> **All email** \> **Top campaign (Preview)**</span></span>

![Panoramica della campagna nel Centro sicurezza e conformità](../media/campaigns-overview.png)

> [!TIP]
> <span data-ttu-id="0bf6b-127">Attualmente l'unico filtro disponibile è l'intervallo di date.</span><span class="sxs-lookup"><span data-stu-id="0bf6b-127">Currently, the only filtering that's available is the date range.</span></span> <span data-ttu-id="0bf6b-128">Se i dati della campagna non sono visibili, provare a modificare l'intervallo di date.</span><span class="sxs-lookup"><span data-stu-id="0bf6b-128">If you don't see any campaign data, try changing the date range.</span></span>

<span data-ttu-id="0bf6b-129">La pagina di panoramica visualizza le seguenti informazioni sulla campagna:</span><span class="sxs-lookup"><span data-stu-id="0bf6b-129">The overview page shows the following information about the campaign:</span></span>

- <span data-ttu-id="0bf6b-130">**Nome**</span><span class="sxs-lookup"><span data-stu-id="0bf6b-130">**Name**</span></span>

- <span data-ttu-id="0bf6b-131">**Esempio di oggetto**: oggetto di uno dei messaggi della campagna.</span><span class="sxs-lookup"><span data-stu-id="0bf6b-131">**Sample subject**: The subject line of one of the messages in the campaign.</span></span> <span data-ttu-id="0bf6b-132">Si noti che _non tutti_ i messaggi della campagna avranno necessariamente lo stesso oggetto.</span><span class="sxs-lookup"><span data-stu-id="0bf6b-132">Note that _all_ the messages in the campaign will not necessarily have this same subject line.</span></span>

- <span data-ttu-id="0bf6b-133">**Tipo**: al momento questo valore sarà sempre **Phishing**.</span><span class="sxs-lookup"><span data-stu-id="0bf6b-133">**Type**: Currently, this value will always be **Phish**.</span></span>

- <span data-ttu-id="0bf6b-134">**Sottotipo**: se disponibile, il marchio oggetto dell'attacco di phishing dalla campagna.</span><span class="sxs-lookup"><span data-stu-id="0bf6b-134">**Subtype**: Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="0bf6b-135">Quando la minaccia viene rilevata grazie alla tecnologia ATP, al valore sottotipo viene aggiunto **ATP**.</span><span class="sxs-lookup"><span data-stu-id="0bf6b-135">When the detection is driven by ATP technology, the prefix **ATP-** is added to the subtype value.</span></span>

- <span data-ttu-id="0bf6b-136">**Destinatari**: il numero di utenti oggetti dell'attacco della campagna.</span><span class="sxs-lookup"><span data-stu-id="0bf6b-136">**Recipients**: The number of users that were targeted by this campaign.</span></span>

- <span data-ttu-id="0bf6b-137">**Recapitato**: il numero di utenti che hanno ricevuto i messaggi della campagna nella loro posta in arrivo.</span><span class="sxs-lookup"><span data-stu-id="0bf6b-137">**Delivered**: The number of users that received messages from this campaign into their Inbox.</span></span>

- <span data-ttu-id="0bf6b-138">**ID**: identificatore univoco della campagna.</span><span class="sxs-lookup"><span data-stu-id="0bf6b-138">**ID**: A unique identifier for the campaign.</span></span>

<span data-ttu-id="0bf6b-139">Quando si fa clic sul nome di una campagna, i dettagli della campagna sono visualizzati in un riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="0bf6b-139">When you click on the name of a campaign, the campaign details appears in a flyout.</span></span>

## <a name="campaign-details"></a><span data-ttu-id="0bf6b-140">Dettagli campagna</span><span class="sxs-lookup"><span data-stu-id="0bf6b-140">Campaign details</span></span>

<span data-ttu-id="0bf6b-141">Nella visualizzazione dei dettagli della campagna sono disponibili numerose informazioni:</span><span class="sxs-lookup"><span data-stu-id="0bf6b-141">In the campaign details view, a lot of information is available about the campaign:</span></span>

- <span data-ttu-id="0bf6b-142">Informazioni sulla campagna:</span><span class="sxs-lookup"><span data-stu-id="0bf6b-142">Campaign information:</span></span>

  - <span data-ttu-id="0bf6b-143">**ID**: l'identificatore univoco della campagna, identico a quello della schermata panoramica.</span><span class="sxs-lookup"><span data-stu-id="0bf6b-143">**ID**: The same unique identifier of the campaign from the overview screen.</span></span>

  - <span data-ttu-id="0bf6b-144">**Iniziata** e **Terminata**: l'intervallo di date scelto come filtro.</span><span class="sxs-lookup"><span data-stu-id="0bf6b-144">**Started** and **Ended**: the date range filter you selected.</span></span>

  - <span data-ttu-id="0bf6b-145">**Impatto**: il numero di messaggi inviati nell'intervallo di date selezionato, il numero di messaggi ricevuti (recapitati nella posta in arrivo) e il numero di utenti che hanno fatto clic sull'URL del payload nel messaggio di phishing.</span><span class="sxs-lookup"><span data-stu-id="0bf6b-145">**Impact**: the number of messages sent in the date range you selected, how many were "inboxed" (that is, delivered to the Inbox), and how many users clicked on the URL payload in the phishing message.</span></span>

  - <span data-ttu-id="0bf6b-146">Una sequenza temporale delle attività delle campagne: quando è iniziata e terminata la campagna e il volume di messaggi nel corso del tempo.</span><span class="sxs-lookup"><span data-stu-id="0bf6b-146">A timeline of campaign activity: When the campaign started and ended, and the volume of messages over time.</span></span>

### <a name="campaign-flow"></a><span data-ttu-id="0bf6b-147">Flusso della campagna</span><span class="sxs-lookup"><span data-stu-id="0bf6b-147">Campaign flow</span></span>

<span data-ttu-id="0bf6b-148">I dettagli importanti sulla campagna sono presentati in un diagramma di flusso orizzontale (noto come diagramma di _Sankey_) nella sezione **Flusso**.</span><span class="sxs-lookup"><span data-stu-id="0bf6b-148">Important details about the campaign are presented in a horizontal flow diagram (known as a _Sankey_ diagram) in the **Flow** section.</span></span> <span data-ttu-id="0bf6b-149">Questi dettagli aiuteranno a comprendere gli elementi della campagna e il potenziale impatto sull'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="0bf6b-149">These details will help you to understand the elements of the campaign and the potential impact in your organization.</span></span>

![Dettagli della campagna che non contengono clic sull'URL da parte dell'utente](../media/campaign-details-no-recipient-actions.png)

<span data-ttu-id="0bf6b-151">Se si passa il mouse su una fascia orizzontale nel diagramma, viene visualizzato il numero di messaggi correlati (ad esempio i messaggi provenienti da un determinato IP di origine, i messaggi provenienti dall'IP di origine con il dominio del mittente specificato e così via).</span><span class="sxs-lookup"><span data-stu-id="0bf6b-151">If you hover over a horizontal band in the diagram, you'll see the number of related messages (for example, messages from a particular source IP, messages from the source IP using the specified sender domain, etc.).</span></span>

<span data-ttu-id="0bf6b-152">Il diagramma include le seguenti informazioni:</span><span class="sxs-lookup"><span data-stu-id="0bf6b-152">The entry contains the following information:</span></span>

- <span data-ttu-id="0bf6b-153">**Indirizzi IP mittenti**</span><span class="sxs-lookup"><span data-stu-id="0bf6b-153">**Sender IPs**</span></span>

- <span data-ttu-id="0bf6b-154">**Domini mittenti**</span><span class="sxs-lookup"><span data-stu-id="0bf6b-154">**Sender domains**</span></span>

- <span data-ttu-id="0bf6b-155">**Filtra risultati**: i valori qui riportati riguardano i risultati del filtro anti-phishing e della posta indesiderata disponibili come descritto in [Intestazioni dei messaggi di posta indesiderata](anti-spam-message-headers.md).</span><span class="sxs-lookup"><span data-stu-id="0bf6b-155">**Filter verdicts**: The values here are related to the available anti-phishing and anti-spam filter verdicts as described in [Anti-spam message headers](anti-spam-message-headers.md).</span></span> <span data-ttu-id="0bf6b-156">Molto interessanti sono i valori **Autorizza tenant**, ossia un'impostazione di configurazione nell'organizzazione che ha autorizzato il recapito di un messaggio che sarebbe altrimenti stato bloccato dal servizio (ad esempio un dominio nell'elenco di mittenti consentiti).</span><span class="sxs-lookup"><span data-stu-id="0bf6b-156">Of great interest here are the values **Tenant Allow**, which means a configured setting in the organization allowed a message through that would have been otherwise blocked by the service (for example, a domain in the Allowed Senders list).</span></span>

  - <span data-ttu-id="0bf6b-157">**Blocca tenant**: questo valore si riferisce a un'opzione nell'organizzazione (ad esempio una voce di dominio nell'[Elenco mittenti bloccati](create-block-sender-lists-in-office-365.md)) che ha rilevato il messaggio e ha determinato dove è stato recapitato.</span><span class="sxs-lookup"><span data-stu-id="0bf6b-157">**Tenant Block**: This value indicates that a setting in your organization (for example, a domain entry in the [Blocked Senders list](create-block-sender-lists-in-office-365.md)) both detected the message and determined where it was delivered.</span></span> <span data-ttu-id="0bf6b-158">Per i messaggi non messi in quarantena, esaminare le impostazioni dei mittenti bloccati per determinare il motivo per cui il messaggio è stato recapitato.</span><span class="sxs-lookup"><span data-stu-id="0bf6b-158">For messages that weren't quarantined, review your blocked senders settings to determine why the message was delivered.</span></span>

  - <span data-ttu-id="0bf6b-159">**Rilevato**</span><span class="sxs-lookup"><span data-stu-id="0bf6b-159">**Detected**</span></span>

  - <span data-ttu-id="0bf6b-160">**Tenant autorizzato**</span><span class="sxs-lookup"><span data-stu-id="0bf6b-160">**Tenant Allow**</span></span>

- <span data-ttu-id="0bf6b-161">**Posizioni di recapito**: è consigliabile esaminare i messaggi che sono stati effettivamente recapitati ai destinatari (nella cartella posta in arrivo o posta indesiderata), anche se gli utenti non hanno fatto clic sull'URL del payload nel messaggio.</span><span class="sxs-lookup"><span data-stu-id="0bf6b-161">**Delivery locations**: You'll likely want to investigate messages that were actually delivered to recipients (either to the Inbox or the Junk Email folder), even if users didn't click on the payload URL in the message.</span></span> <span data-ttu-id="0bf6b-162">È anche possibile rimuovere i messaggi messi in quarantena da [Messaggi di posta elettronica in quarantena in Office 365](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="0bf6b-162">You can also remove the quarantined messages from [Quarantine email messages in Office 365](quarantine-email-messages.md).</span></span>

  - <span data-ttu-id="0bf6b-163">**Posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="0bf6b-163">**The Junk E-Mail folder.**</span></span>

  - <span data-ttu-id="0bf6b-164">**Quarantena**</span><span class="sxs-lookup"><span data-stu-id="0bf6b-164">**Quarantine**</span></span>

  - <span data-ttu-id="0bf6b-165">**Posta in arrivo**</span><span class="sxs-lookup"><span data-stu-id="0bf6b-165">**Inbox**</span></span>

#### <a name="url-clicks"></a><span data-ttu-id="0bf6b-166">Clic URL</span><span class="sxs-lookup"><span data-stu-id="0bf6b-166">URL clicks</span></span>

<span data-ttu-id="0bf6b-167">È possibile che i messaggi recapitati nella cartella di posta in arrivo o nella posta indesiderata del destinatario vengano gestiti dall'utente (ossia che l'utente clicchi sull'URL dannoso nel messaggio).</span><span class="sxs-lookup"><span data-stu-id="0bf6b-167">There's always the chance that messages delivered to the recipient's Inbox or Junk Email folder can be acted upon by the user (that is, user will click on the malicious URL in the message).</span></span> <span data-ttu-id="0bf6b-168">Se questo non avviene, si tratta solo di una piccola percentuale di successo, anche se è certamente necessario determinare il motivo per cui il messaggio è stato recapitato nella casella di posta.</span><span class="sxs-lookup"><span data-stu-id="0bf6b-168">If they haven't, that's a small measure of success, although you certainly need to determine why the harmful message was delivered to their mailbox in the first place.</span></span>

<span data-ttu-id="0bf6b-169">Se un utente ha fatto clic sull'URL dannoso, le azioni vengono visualizzate nella sezione **Clic URL** del diagramma.</span><span class="sxs-lookup"><span data-stu-id="0bf6b-169">If a user has clicked on the malicious URL, the actions are displayed in the **URL clicks** area of the diagram.</span></span>

![Dettagli della campagna che contengono clic sull'URL](../media/campaign-details-with-recipient-actions.png)

- <span data-ttu-id="0bf6b-171">**Blocco di collegamenti sicuri**: questo valore indica che il destinatario ha fatto clic sull'URL di payload nel messaggio, ma è stato bloccato dai criteri [Collegamenti sicuri ATP](atp-safe-links.md) all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="0bf6b-171">**Safe Links Block**: This value indicates the recipient clicked on the payload URL in the message, but it was blocked by the [ATP Safe Links](atp-safe-links.md) policies in your organization.</span></span>

- <span data-ttu-id="0bf6b-172">**Blocco collegamenti sicuri ignorato**: questo valore indica anche che il destinatario ha fatto clic sull'URL di payload nel messaggio e che i collegamenti sicuri ATP hanno tentato di fermarlo ma gli utenti sono stati autorizzati a ignorare il blocco.</span><span class="sxs-lookup"><span data-stu-id="0bf6b-172">**Safe Links Block Override**: This value also indicates the recipient clicked on the payload URL in the message, ATP Safe Links tried to stop them, but they were allowed to override the block.</span></span> <span data-ttu-id="0bf6b-173">È necessario analizzare i [criteri dei collegamenti sicuri](set-up-atp-safe-links-policies.md) per capire perché agli utenti è consentito ignorare la valutazione dei collegamenti sicuri e quindi fare clic su URL dannosi.</span><span class="sxs-lookup"><span data-stu-id="0bf6b-173">You need to investigate your [Safe Links policies](set-up-atp-safe-links-policies.md) to see why users are allowed to override the Safe Links verdict and click on malicious URLs.</span></span>

### <a name="tabs"></a><span data-ttu-id="0bf6b-174">Schede</span><span class="sxs-lookup"><span data-stu-id="0bf6b-174">Tabs</span></span>

<span data-ttu-id="0bf6b-175">Nella visualizzazione dei dettagli della campagna sono disponibili diverse schede che consentono di esaminare la campagna in maniera più approfondita.</span><span class="sxs-lookup"><span data-stu-id="0bf6b-175">There are several tabs in the campaign details view that allow you to further investigate the campaign.</span></span>

- <span data-ttu-id="0bf6b-176">**Clic URL**: se non è stato fatto clic sull'URL del payload nel messaggio di phishing, questa sezione sarà vuota.</span><span class="sxs-lookup"><span data-stu-id="0bf6b-176">**URL Clicks**: If the payload URL in the phishing message wasn't clicked, this section will be blank.</span></span> <span data-ttu-id="0bf6b-177">Se un utente ha potuto fare clic sull'URL,</span><span class="sxs-lookup"><span data-stu-id="0bf6b-177">If a user was able to click on the URL, you</span></span>

  - <span data-ttu-id="0bf6b-178">**Utente:**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0bf6b-178">User</span></span>

  - <span data-ttu-id="0bf6b-179">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0bf6b-179">URL</span></span>

  - <span data-ttu-id="0bf6b-180">**Ora clic**</span><span class="sxs-lookup"><span data-stu-id="0bf6b-180">**Click Time**</span></span>

  - <span data-ttu-id="0bf6b-181">**Azione clic**</span><span class="sxs-lookup"><span data-stu-id="0bf6b-181">Click **Action**.</span></span>

- <span data-ttu-id="0bf6b-182">**Indirizzi IP mittenti**</span><span class="sxs-lookup"><span data-stu-id="0bf6b-182">**Sender IPs**</span></span>

  - <span data-ttu-id="0bf6b-183">**Indirizzo IP mittente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0bf6b-183">**Sender IP**<sup>\*</sup></span></span>

  - <span data-ttu-id="0bf6b-184">**Conteggio totale**</span><span class="sxs-lookup"><span data-stu-id="0bf6b-184">**Total Count**</span></span>

  - <span data-ttu-id="0bf6b-185">**Conteggio messaggi in posta in arrivo**</span><span class="sxs-lookup"><span data-stu-id="0bf6b-185">**Inboxed Count**</span></span>

  - <span data-ttu-id="0bf6b-186">**Conteggio bloccati**</span><span class="sxs-lookup"><span data-stu-id="0bf6b-186">**Blocked Count**</span></span>

  - <span data-ttu-id="0bf6b-187">**SPF superato**</span><span class="sxs-lookup"><span data-stu-id="0bf6b-187">**SPF Passed**</span></span>

- <span data-ttu-id="0bf6b-188">**Mittenti**</span><span class="sxs-lookup"><span data-stu-id="0bf6b-188">**Senders**</span></span>

  - <span data-ttu-id="0bf6b-189">**Mittente**</span><span class="sxs-lookup"><span data-stu-id="0bf6b-189">**Sender**</span></span>

  - <span data-ttu-id="0bf6b-190">**Conteggio totale**</span><span class="sxs-lookup"><span data-stu-id="0bf6b-190">**Total Count**</span></span>

  - <span data-ttu-id="0bf6b-191">**Conteggio messaggi in posta in arrivo**</span><span class="sxs-lookup"><span data-stu-id="0bf6b-191">**Inboxed Count**</span></span>

  - <span data-ttu-id="0bf6b-192">**Conteggio bloccati**</span><span class="sxs-lookup"><span data-stu-id="0bf6b-192">**Blocked Count**</span></span>

  - <span data-ttu-id="0bf6b-193">**DKIM superato**</span><span class="sxs-lookup"><span data-stu-id="0bf6b-193">**DKIM Passed**</span></span>

  - <span data-ttu-id="0bf6b-194">**DMARC superato**</span><span class="sxs-lookup"><span data-stu-id="0bf6b-194">**DMARC Passed**</span></span>

- <span data-ttu-id="0bf6b-195">**Payload**</span><span class="sxs-lookup"><span data-stu-id="0bf6b-195">**Payloads**</span></span>

  - <span data-ttu-id="0bf6b-196">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0bf6b-196">URL</span></span>

  - <span data-ttu-id="0bf6b-197">**Conteggio totale**</span><span class="sxs-lookup"><span data-stu-id="0bf6b-197">**Total Count**</span></span>

<span data-ttu-id="0bf6b-198"><sup>\*</sup> Se si fa clic su questo valore, viene aperto un nuovo riquadro a comparsa che contiene altri dettagli sulla voce specificata (utente, URL e così via) nella parte superiore della visualizzazione dei dettagli della campagna.</span><span class="sxs-lookup"><span data-stu-id="0bf6b-198"><sup>\*</sup> Clicking on this value opens a new flyout that contains more details about the specified item (user, URL, etc.) on top of the campaign details view.</span></span> <span data-ttu-id="0bf6b-199">Per tornare alla visualizzazione dei dettagli della campagna, fare clic su **Chiudi** nel nuovo riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="0bf6b-199">To return to the campaign details view, click **Done** in the new flyout.</span></span>

### <a name="buttons"></a><span data-ttu-id="0bf6b-200">Pulsanti</span><span class="sxs-lookup"><span data-stu-id="0bf6b-200">Buttons</span></span>

<span data-ttu-id="0bf6b-201">I pulsanti nella visualizzazione dei dettagli della campagna consentono di usare la potenza di Esplora minacce per approfondire la campagna.</span><span class="sxs-lookup"><span data-stu-id="0bf6b-201">The buttons in the campaign details view allow you to use the power of Threat Explorer to further investigate the campaign.</span></span>

- <span data-ttu-id="0bf6b-202">**Esplora minacce**: apre una nuova scheda di ricerca in Esplora minacce usando il valore **ID campagna** come filtro di ricerca.</span><span class="sxs-lookup"><span data-stu-id="0bf6b-202">**Explore campaign**: Opens a new Threat Explorer search tab using the **Campaign ID** value as the search filter.</span></span>

- <span data-ttu-id="0bf6b-203">**Esplora minacce in posta in arrivo**: apre una nuova scheda di ricerca in Esplora minacce usando **ID campagna** e **Posizione di recapito: posta in arrivo** come filtro di ricerca.</span><span class="sxs-lookup"><span data-stu-id="0bf6b-203">**Explore Inbox messages**: Opens a new Threat Explorer search tab using the **Campaign ID** and **Delivery location: Inbox** as the search filter.</span></span>
