---
title: Visualizzazione campagne in Office 365 ATP
f1.keywords:
- NOCSH
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
ms.openlocfilehash: 350f4f9007bf6f09836080af65802a9757532dcc
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42083545"
---
# <a name="campaign-views-in-office-365-atp"></a><span data-ttu-id="c1b5b-103">Visualizzazione campagne in Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="c1b5b-103">Campaign Views in Office 365 ATP</span></span>

<span data-ttu-id="c1b5b-104">Visualizzazione campagne è una funzionalità di Advanced Threat Protection (ATP) nel Centro sicurezza e conformità di Office 365 che identifica e categorizza gli attacchi di phishing nel servizio.</span><span class="sxs-lookup"><span data-stu-id="c1b5b-104">Campaign Views is a feature in Advanced Threat Protection (ATP) in the Office 365 Security & Compliance Center that identifies and categorizes phishing attacks in the service.</span></span> <span data-ttu-id="c1b5b-105">Visualizzazione campagne consente di:</span><span class="sxs-lookup"><span data-stu-id="c1b5b-105">Campaign Views can help you to:</span></span>

- <span data-ttu-id="c1b5b-106">Analizzare e rispondere in modo efficiente agli attacchi di phishing.</span><span class="sxs-lookup"><span data-stu-id="c1b5b-106">Efficiently investigate and respond to phishing attacks.</span></span>

- <span data-ttu-id="c1b5b-107">Comprendere meglio la portata dell'attacco.</span><span class="sxs-lookup"><span data-stu-id="c1b5b-107">Better understand the scope of the attack.</span></span>

- <span data-ttu-id="c1b5b-108">Visualizzare i dettagli dell'attacco.</span><span class="sxs-lookup"><span data-stu-id="c1b5b-108">Show value to decision makers.</span></span>

<span data-ttu-id="c1b5b-109">Visualizzazione campagne fornisce una visione d'insieme di un attacco in maniera più rapida e completa rispetto a un processo manuale.</span><span class="sxs-lookup"><span data-stu-id="c1b5b-109">Campaign Views lets you see the big picture of an attack faster and more complete than any human.</span></span>

## <a name="what-is-a-campaign"></a><span data-ttu-id="c1b5b-110">Cos'è una campagna?</span><span class="sxs-lookup"><span data-stu-id="c1b5b-110">What is a campaign?</span></span>

<span data-ttu-id="c1b5b-111">Una campagna è un attacco coordinato perpetrato tramite posta elettronica contro una o più organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="c1b5b-111">A campaign is a coordinated email attack against one or many organizations.</span></span> <span data-ttu-id="c1b5b-112">Gli attacchi tramite posta elettronica che rubano le credenziali e i dati aziendali rappresentano un settore importante e redditizio.</span><span class="sxs-lookup"><span data-stu-id="c1b5b-112">Email attacks that steal credentials and company data are a big and lucrative industry.</span></span> <span data-ttu-id="c1b5b-113">Man mano che le tecnologie aumentano nel tentativo di arrestare gli attacchi, gli aggressori modificano i propri metodi nel tentativo di garantire il successo continuativo.</span><span class="sxs-lookup"><span data-stu-id="c1b5b-113">As technologies increase in an effort to stop attacks, attackers modify their methods in an effort to ensure continued success.</span></span>

<span data-ttu-id="c1b5b-114">Microsoft utilizza la vasta gamma di dati anti-phishing, antispam e antimalware in tutto il servizio Office 365 per facilitare l'identificazione delle campagne.</span><span class="sxs-lookup"><span data-stu-id="c1b5b-114">Microsoft leverages the vast amounts of anti-phishing, anti-spam, and anti-malware data across the entire Office 365 service to help identify campaigns.</span></span> <span data-ttu-id="c1b5b-115">Vengono analizzate e classificate le informazioni sull'attacco in base a diversi fattori.</span><span class="sxs-lookup"><span data-stu-id="c1b5b-115">We analyze and classify the attack information according to several factors.</span></span> <span data-ttu-id="c1b5b-116">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="c1b5b-116">For example:</span></span>

- <span data-ttu-id="c1b5b-117">**Origine dell'attacco**: indirizzi IP origine e domini di posta elettronica del mittente.</span><span class="sxs-lookup"><span data-stu-id="c1b5b-117">**Attack source**: Source IP addresses and sender email domains.</span></span>

- <span data-ttu-id="c1b5b-118">**Caratteristiche del messaggio di attacco**: il contenuto, lo stile e il tono dei messaggi di attacco.</span><span class="sxs-lookup"><span data-stu-id="c1b5b-118">**Attack message properties**: The content, style, and tone of the attack messages.</span></span>

- <span data-ttu-id="c1b5b-119">**Destinatari dell'attacco**: domini dei destinatari, funzione aziendale dei destinatari (amministratori, dirigenti e così via), tipi di azienda (grandi, piccole, pubbliche, private e così via) e settori.</span><span class="sxs-lookup"><span data-stu-id="c1b5b-119">**Attack recipients**: Recipient domains, recipient job functions (admins, executives, etc.), company types (large, small, public, private, etc.), and industries.</span></span>

- <span data-ttu-id="c1b5b-120">**Attacco payload**: collegamenti malevoli, allegati o altri payload nei messaggi di attacco.</span><span class="sxs-lookup"><span data-stu-id="c1b5b-120">**Attack payload**: Malicious links, attachments, or other payloads in the attack messages.</span></span>

<span data-ttu-id="c1b5b-121">Una campagna potrebbe essere di breve durata, o potrebbe interferire tra diversi giorni, settimane o mesi con periodi attivi e inattivi.</span><span class="sxs-lookup"><span data-stu-id="c1b5b-121">A campaign might be short-lived, or could span several days, weeks, or months with active and inactive periods.</span></span> <span data-ttu-id="c1b5b-122">Una campagna potrebbe essere avviata con l'organizzazione specifica oppure l'organizzazione potrebbe far parte di una campagna più estesa tra più società.</span><span class="sxs-lookup"><span data-stu-id="c1b5b-122">A campaign might be launched against your specific organization, or your organization might be part of a larger campaign across multiple companies.</span></span>

## <a name="campaign-views-the-office-365-security--compliance-center"></a><span data-ttu-id="c1b5b-123">Visualizzazione campagne del Centro sicurezza e conformità di Office 365</span><span class="sxs-lookup"><span data-stu-id="c1b5b-123">Campaign Views the Office 365 Security & Compliance Center</span></span>

<span data-ttu-id="c1b5b-124">Le visualizzazioni campagna sono disponibili nel [Centro sicurezza & conformità](https://protection.office.com) nelle \*\*\*\* \> **campagne**di gestione delle minacce.</span><span class="sxs-lookup"><span data-stu-id="c1b5b-124">Campaign Views is available in the [Security & Compliance Center](https://protection.office.com) at **Threat management** \> **Campaigns**.</span></span>

![Panoramica della campagna nel Centro sicurezza e conformità](../../media/campaigns-overview.png)

<span data-ttu-id="c1b5b-126">È inoltre possibile accedere alla visualizzazione campagne da:</span><span class="sxs-lookup"><span data-stu-id="c1b5b-126">You can also get to Campaigns View from:</span></span>

- <span data-ttu-id="c1b5b-127">**Campagne** di \*\*\*\* \> \*\*\*\* visualizzazione \> di **gestione delle minacce** \></span><span class="sxs-lookup"><span data-stu-id="c1b5b-127">**Threat management** \> **Explorer** \> **View** \> **Campaigns**</span></span>

- <span data-ttu-id="c1b5b-128">**Gestione delle** \> minacce **Esplora** \> \*\*\*\* \*\*\*\* \> \*\*\*\* tutte le campagne di posta elettronica \></span><span class="sxs-lookup"><span data-stu-id="c1b5b-128">**Threat management** \> **Explorer** \> **View** \> **All email** \> **Campaign**</span></span>

> [!TIP]
> <span data-ttu-id="c1b5b-129">Se i dati della campagna non sono visibili, provare a modificare l'intervallo di date.</span><span class="sxs-lookup"><span data-stu-id="c1b5b-129">If you don't see any campaign data, try changing the date range.</span></span>

<span data-ttu-id="c1b5b-130">La pagina di panoramica visualizza le seguenti informazioni sulla campagna:</span><span class="sxs-lookup"><span data-stu-id="c1b5b-130">The overview page shows the following information about the campaign:</span></span>

- <span data-ttu-id="c1b5b-131">**Nome**</span><span class="sxs-lookup"><span data-stu-id="c1b5b-131">**Name**</span></span>

- <span data-ttu-id="c1b5b-132">**Esempio di oggetto**: oggetto di uno dei messaggi della campagna.</span><span class="sxs-lookup"><span data-stu-id="c1b5b-132">**Sample subject**: The subject line of one of the messages in the campaign.</span></span> <span data-ttu-id="c1b5b-133">Tenere presente che tutti i messaggi nella campagna non avranno necessariamente lo stesso oggetto.</span><span class="sxs-lookup"><span data-stu-id="c1b5b-133">Note that all messages in the campaign will not necessarily have the same subject.</span></span>

- <span data-ttu-id="c1b5b-134">**Tipo**: attualmente, questo valore è sempre **phishing**.</span><span class="sxs-lookup"><span data-stu-id="c1b5b-134">**Type**: Currently, this value is always **Phish**.</span></span>

- <span data-ttu-id="c1b5b-135">**Sottotipo**: se disponibile, il marchio oggetto dell'attacco di phishing dalla campagna.</span><span class="sxs-lookup"><span data-stu-id="c1b5b-135">**Subtype**: Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="c1b5b-136">Quando il rilevamento è guidato dalla tecnologia ATP, il prefisso **ATP-** viene aggiunto al valore del sottotipo.</span><span class="sxs-lookup"><span data-stu-id="c1b5b-136">When the detection is driven by ATP technology, the prefix **ATP-** is added to the subtype value.</span></span>

- <span data-ttu-id="c1b5b-137">**Destinatari**: il numero di utenti oggetti dell'attacco della campagna.</span><span class="sxs-lookup"><span data-stu-id="c1b5b-137">**Recipients**: The number of users that were targeted by this campaign.</span></span>

- <span data-ttu-id="c1b5b-138">**Posta in arrivo**: il numero di utenti che hanno ricevuto messaggi da questa campagna nella cartella posta in arrivo (non recapitati alla posta indesiderata).</span><span class="sxs-lookup"><span data-stu-id="c1b5b-138">**Inboxed**: The number of users that received messages from this campaign in their Inbox (not delivered to Junk).</span></span>

- <span data-ttu-id="c1b5b-139">**Fare clic**su: il numero di utenti che hanno fatto clic sull'URL nel messaggio di phishing.</span><span class="sxs-lookup"><span data-stu-id="c1b5b-139">**Clicked**: The number of users that clicked on the URL in the phishing message.</span></span>

- <span data-ttu-id="c1b5b-140">**Fare clic su rate**: la percentuale calcolata da "**fare clic su** / **posta in arrivo**".</span><span class="sxs-lookup"><span data-stu-id="c1b5b-140">**Click Rate**: The percentage as calculated by "**Clicked** / **Inboxed**".</span></span> <span data-ttu-id="c1b5b-141">Questo valore è un indicatore dell'efficacia della campagna e indica se i destinatari sono stati in grado di identificare il messaggio come phishing ed evitare di fare clic sull'URL del payload.</span><span class="sxs-lookup"><span data-stu-id="c1b5b-141">This value is an indicator of the effectiveness of the campaign, and whether the recipients were able to identify the message as phishing and avoid clicking on the payload URL.</span></span>

- <span data-ttu-id="c1b5b-142">**Visitato**: numero di utenti effettivamente apportati al sito Web payload.</span><span class="sxs-lookup"><span data-stu-id="c1b5b-142">**Visited**: How many users actually made it through to the payload website.</span></span> <span data-ttu-id="c1b5b-143">Se sono presenti valori **cliccati** , ma i collegamenti sicuri impediscono l'accesso al sito Web, questo valore sarà zero.</span><span class="sxs-lookup"><span data-stu-id="c1b5b-143">If there are **Clicked** values, but Safe Links blocked access to the website, this value will be zero.</span></span>

<span data-ttu-id="c1b5b-144">Quando si fa clic sul nome di una campagna, i dettagli della campagna sono visualizzati in un riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="c1b5b-144">When you click on the name of a campaign, the campaign details appears in a flyout.</span></span>

## <a name="campaign-details"></a><span data-ttu-id="c1b5b-145">Dettagli campagna</span><span class="sxs-lookup"><span data-stu-id="c1b5b-145">Campaign details</span></span>

<span data-ttu-id="c1b5b-146">Nella visualizzazione dei dettagli della campagna sono disponibili numerose informazioni:</span><span class="sxs-lookup"><span data-stu-id="c1b5b-146">In the campaign details view, a lot of information is available about the campaign:</span></span>

- <span data-ttu-id="c1b5b-147">Informazioni sulla campagna:</span><span class="sxs-lookup"><span data-stu-id="c1b5b-147">Campaign information:</span></span>

  - <span data-ttu-id="c1b5b-148">**ID**: l'identificatore della campagna univoco.</span><span class="sxs-lookup"><span data-stu-id="c1b5b-148">**ID**: The unique campaign identifier.</span></span>

  - <span data-ttu-id="c1b5b-149">**Iniziata** e **Terminata**: l'intervallo di date scelto come filtro.</span><span class="sxs-lookup"><span data-stu-id="c1b5b-149">**Started** and **Ended**: the date range filter you selected.</span></span>

  - <span data-ttu-id="c1b5b-150">**Impatto**: i dati seguenti per il filtro intervallo di date selezionato:</span><span class="sxs-lookup"><span data-stu-id="c1b5b-150">**Impact**: The following data for the date range filter you selected:</span></span>
  
    - <span data-ttu-id="c1b5b-151">Numero totale di destinatari.</span><span class="sxs-lookup"><span data-stu-id="c1b5b-151">The total number of recipients.</span></span>

    - <span data-ttu-id="c1b5b-152">Il numero di messaggi che sono stati "ricevuti" (ovvero, recapitati nella posta in arrivo, non per la posta indesiderata).</span><span class="sxs-lookup"><span data-stu-id="c1b5b-152">The number of messages that were "Inboxed" (that is, delivered to the Inbox, not to Junk).</span></span>

    - <span data-ttu-id="c1b5b-153">Il numero di utenti che hanno fatto clic sul payload URL nel messaggio di phishing.</span><span class="sxs-lookup"><span data-stu-id="c1b5b-153">How many users clicked on the URL payload in the phishing message.</span></span>

    - <span data-ttu-id="c1b5b-154">Howe molti utenti hanno visitato l'URL.</span><span class="sxs-lookup"><span data-stu-id="c1b5b-154">Howe many users visited the URL.</span></span>

  - <span data-ttu-id="c1b5b-155">Una sequenza temporale delle attività delle campagne: quando è iniziata e terminata la campagna e il volume di messaggi nel corso del tempo.</span><span class="sxs-lookup"><span data-stu-id="c1b5b-155">A timeline of campaign activity: When the campaign started and ended, and the volume of messages over time.</span></span>

### <a name="campaign-flow"></a><span data-ttu-id="c1b5b-156">Flusso della campagna</span><span class="sxs-lookup"><span data-stu-id="c1b5b-156">Campaign flow</span></span>

<span data-ttu-id="c1b5b-157">I dettagli importanti sulla campagna sono presentati in un diagramma di flusso orizzontale (noto come diagramma di _Sankey_) nella sezione **Flusso**.</span><span class="sxs-lookup"><span data-stu-id="c1b5b-157">Important details about the campaign are presented in a horizontal flow diagram (known as a _Sankey_ diagram) in the **Flow** section.</span></span> <span data-ttu-id="c1b5b-158">Questi dettagli aiuteranno a comprendere gli elementi della campagna e il potenziale impatto sull'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c1b5b-158">These details will help you to understand the elements of the campaign and the potential impact in your organization.</span></span>

![Dettagli della campagna che non contengono clic sull'URL da parte dell'utente](../../media/campaign-details-no-recipient-actions.png)

<span data-ttu-id="c1b5b-160">Se si passa il mouse su una fascia orizzontale nel diagramma, viene visualizzato il numero di messaggi correlati (ad esempio i messaggi provenienti da un determinato IP di origine, i messaggi provenienti dall'IP di origine con il dominio del mittente specificato e così via).</span><span class="sxs-lookup"><span data-stu-id="c1b5b-160">If you hover over a horizontal band in the diagram, you'll see the number of related messages (for example, messages from a particular source IP, messages from the source IP using the specified sender domain, etc.).</span></span>

<span data-ttu-id="c1b5b-161">Il diagramma include le seguenti informazioni:</span><span class="sxs-lookup"><span data-stu-id="c1b5b-161">The diagram contains the following information:</span></span>

- <span data-ttu-id="c1b5b-162">**Indirizzi IP mittenti**</span><span class="sxs-lookup"><span data-stu-id="c1b5b-162">**Sender IPs**</span></span>

- <span data-ttu-id="c1b5b-163">**Domini mittenti**</span><span class="sxs-lookup"><span data-stu-id="c1b5b-163">**Sender domains**</span></span>

- <span data-ttu-id="c1b5b-164">**Filtra risultati**: i valori qui riportati riguardano i risultati del filtro anti-phishing e della posta indesiderata disponibili come descritto in [Intestazioni dei messaggi di posta indesiderata](anti-spam-message-headers.md).</span><span class="sxs-lookup"><span data-stu-id="c1b5b-164">**Filter verdicts**: The values here are related to the available anti-phishing and anti-spam filter verdicts as described in [Anti-spam message headers](anti-spam-message-headers.md).</span></span> <span data-ttu-id="c1b5b-165">I valori disponibili sono descritti nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="c1b5b-165">The available values are described in the following table:</span></span>

  |<span data-ttu-id="c1b5b-166">Valore</span><span class="sxs-lookup"><span data-stu-id="c1b5b-166">Value</span></span>|<span data-ttu-id="c1b5b-167">Verdetto del filtro posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="c1b5b-167">Spam filter verdict</span></span>|<span data-ttu-id="c1b5b-168">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c1b5b-168">Description</span></span>|
  |:-----|:-----|:-----|
  | <span data-ttu-id="c1b5b-169">**Consentiti**</span><span class="sxs-lookup"><span data-stu-id="c1b5b-169">**Allowed**</span></span>|`SFV:SKN` <br/><br/> `SFV:SKI`|<span data-ttu-id="c1b5b-170">Il messaggio è stato contrassegnato come non indesiderato e/o filtro saltato prima di essere valutato dal filtro di posta indesiderata, ad esempio tramite una regola del flusso di posta, nota anche come regola di trasporto.</span><span class="sxs-lookup"><span data-stu-id="c1b5b-170">The message was marked as not spam and/or skipped filtering before being evaluated by the spam filter (for example, by a mail flow rule, also known as a transport rule).</span></span><br/><br/><span data-ttu-id="c1b5b-171">Il messaggio ha ignorato il filtro per la posta indesiderata per altri motivi (ad esempio, il mittente e il destinatario sono presenti nella stessa organizzazione).</span><span class="sxs-lookup"><span data-stu-id="c1b5b-171">The message skipped spam filtering for other reasons (for example, the sender and recipient appear to be in the same organization).</span></span>|
  |<span data-ttu-id="c1b5b-172">**Bloccati**</span><span class="sxs-lookup"><span data-stu-id="c1b5b-172">**Blocked**</span></span>|`SFV:SKS`|<span data-ttu-id="c1b5b-173">Il messaggio è stato contrassegnato come posta indesiderata prima di essere valutato dal filtro di posta indesiderata, ad esempio da una regola del flusso di posta.</span><span class="sxs-lookup"><span data-stu-id="c1b5b-173">The message was marked as spam before being evaluated by the spam filter (for example, by a mail flow rule).</span></span>|
  |<span data-ttu-id="c1b5b-174">**Rilevato**</span><span class="sxs-lookup"><span data-stu-id="c1b5b-174">**Detected**</span></span>|`SFV:SPM`|<span data-ttu-id="c1b5b-175">Il messaggio è stato contrassegnato come posta indesiderata dal filtro posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="c1b5b-175">The message was marked as spam by the spam filter.</span></span>|
  |<span data-ttu-id="c1b5b-176">**Non rilevato**</span><span class="sxs-lookup"><span data-stu-id="c1b5b-176">**Not Detected**</span></span>|`SFV:NSPM`|<span data-ttu-id="c1b5b-177">Il messaggio è stato contrassegnato come non indesiderato dal filtro posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="c1b5b-177">The message was marked as not spam by the spam filter.</span></span>|
  |<span data-ttu-id="c1b5b-178">**Rilasciato**</span><span class="sxs-lookup"><span data-stu-id="c1b5b-178">**Released**</span></span>|`SFV:SKQ`|<span data-ttu-id="c1b5b-179">Il messaggio ha ignorato il filtro della posta indesiderata perché è stato rilasciato dalla quarantena.</span><span class="sxs-lookup"><span data-stu-id="c1b5b-179">The message skipped spam filtering because it was released from quarantine.</span></span>|
  |<span data-ttu-id="c1b5b-180">**Consenti tenant**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c1b5b-180">**Tenant Allow**<sup>\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="c1b5b-181">Il messaggio ha ignorato il filtro della posta indesiderata a causa della configurazione dei criteri di filtro posta indesiderata (ad esempio, il mittente o il dominio è nell'elenco dei **Mittenti consentiti** )</span><span class="sxs-lookup"><span data-stu-id="c1b5b-181">The message skipped spam filtering due to the spam filter policy configuration (for example, the sender or domain was in hte **Sender allow** list).</span></span>|
  |<span data-ttu-id="c1b5b-182">**Blocco tenant**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="c1b5b-182">**Tenant Block**<sup>\*\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="c1b5b-183">Il messaggio è stato bloccato dal filtro posta indesiderata a causa della configurazione dei criteri di filtro della posta indesiderata (ad esempio, il mittente o il dominio è nell'elenco dei **Mittenti bloccati** ).</span><span class="sxs-lookup"><span data-stu-id="c1b5b-183">The message was blocked by spam filtering due to the spam filter policy configuration (for example, the sender or domain was in the **Sender block** list).</span></span>|
  |<span data-ttu-id="c1b5b-184">**Consenti utente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c1b5b-184">**User Allow**<sup>\*</sup></span></span>|`SFV:SFE`|<span data-ttu-id="c1b5b-185">Il messaggio ha ignorato il filtro della posta indesiderata perché il mittente si trovava nell'elenco Mittenti attendibili di un utente in Outlook.</span><span class="sxs-lookup"><span data-stu-id="c1b5b-185">The message skipped spam filtering because the sender was in a user's Safe Senders list in Outlook.</span></span>|
  |<span data-ttu-id="c1b5b-186">**Blocco utenti**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="c1b5b-186">**User Block**<sup>\*\*</sup></span></span>|`SFV:BLK`|<span data-ttu-id="c1b5b-187">Il messaggio è stato bloccato dal filtro posta indesiderata perché il mittente si trovava nell'elenco Mittenti bloccati di un utente in Outlook.</span><span class="sxs-lookup"><span data-stu-id="c1b5b-187">The message was blocked by spam filtering because the sender was in a user's Blocked Senders list in Outlook.</span></span>|
  |<span data-ttu-id="c1b5b-188">**ZAP**</span><span class="sxs-lookup"><span data-stu-id="c1b5b-188">**ZAP**</span></span>|<span data-ttu-id="c1b5b-189">n/d</span><span class="sxs-lookup"><span data-stu-id="c1b5b-189">n/a</span></span>|<span data-ttu-id="c1b5b-190">[Zero-hour auto Purge (ZAP)](zero-hour-auto-purge.md) ha eseguito un'azione sul messaggio recapitato in base alla configurazione dei criteri di filtro posta indesiderata (spostata nella cartella posta indesiderata o in quarantena).</span><span class="sxs-lookup"><span data-stu-id="c1b5b-190">[Zero-hour auto purge (ZAP)](zero-hour-auto-purge.md) took action on the delivered message according to your spam filter policy configuration (moved to the Junk Email folder or Quarantined).</span></span>|

  <span data-ttu-id="c1b5b-191"><sup>\*</sup>Esaminare le impostazioni di configurazione dei criteri di filtro della posta indesiderata, in quanto il servizio potrebbe essere stato bloccato.</span><span class="sxs-lookup"><span data-stu-id="c1b5b-191"><sup>\*</sup> Review your spam filter policy configuration settings, because the allowed message would have likely been blocked by the service.</span></span>

  <span data-ttu-id="c1b5b-192"><sup>\*\*</sup>Esaminare le impostazioni di configurazione dei criteri di filtro della posta indesiderata, poiché tali messaggi devono essere messi in quarantena</span><span class="sxs-lookup"><span data-stu-id="c1b5b-192"><sup>\*\*</sup> Review your spam filter policy configuration settings, because these messages should be quarantined, not delivered.</span></span>

- <span data-ttu-id="c1b5b-193">**Posizioni di recapito**: è consigliabile esaminare i messaggi che sono stati effettivamente recapitati ai destinatari (nella cartella posta in arrivo o posta indesiderata), anche se gli utenti non hanno fatto clic sull'URL del payload nel messaggio.</span><span class="sxs-lookup"><span data-stu-id="c1b5b-193">**Delivery locations**: You'll likely want to investigate messages that were actually delivered to recipients (either to the Inbox or the Junk Email folder), even if users didn't click on the payload URL in the message.</span></span> <span data-ttu-id="c1b5b-194">È inoltre possibile rimuovere i messaggi in quarantena dalla quarantena.</span><span class="sxs-lookup"><span data-stu-id="c1b5b-194">You can also remove the quarantined messages from quarantine.</span></span> <span data-ttu-id="c1b5b-195">For more information, see [Quarantine email messages in Office 365](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="c1b5b-195">For more information, see [Quarantine email messages in Office 365](quarantine-email-messages.md).</span></span>

  - <span data-ttu-id="c1b5b-196">**Cartella eliminata**</span><span class="sxs-lookup"><span data-stu-id="c1b5b-196">**Deleted folder**</span></span>

  - <span data-ttu-id="c1b5b-197">**Interrotte**</span><span class="sxs-lookup"><span data-stu-id="c1b5b-197">**Dropped**</span></span>

  - <span data-ttu-id="c1b5b-198">**External**: il destinatario si trova nell'organizzazione di posta elettronica locale.</span><span class="sxs-lookup"><span data-stu-id="c1b5b-198">**External**: The recipient is located in your on-premises email organization.</span></span>

  - <span data-ttu-id="c1b5b-199">**Operazione non riuscita**</span><span class="sxs-lookup"><span data-stu-id="c1b5b-199">**Failed**</span></span>

  - <span data-ttu-id="c1b5b-200">**Inoltrato**</span><span class="sxs-lookup"><span data-stu-id="c1b5b-200">**Forwarded**</span></span>

  - <span data-ttu-id="c1b5b-201">**Posta in arrivo**</span><span class="sxs-lookup"><span data-stu-id="c1b5b-201">**Inbox**</span></span>

  - <span data-ttu-id="c1b5b-202">**Posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="c1b5b-202">**Junk folder**</span></span>

  - <span data-ttu-id="c1b5b-203">**Quarantena**</span><span class="sxs-lookup"><span data-stu-id="c1b5b-203">**Quarantine**</span></span>

  - <span data-ttu-id="c1b5b-204">**Unknown**</span><span class="sxs-lookup"><span data-stu-id="c1b5b-204">**Unknown**</span></span>

> [!NOTE]
> <span data-ttu-id="c1b5b-205">In tutti i layer che contengono più di 10 elementi vengono visualizzati i primi 10 elementi, mentre quelli restanti sono raggruppati in **altri**.</span><span class="sxs-lookup"><span data-stu-id="c1b5b-205">In all layers that contain more than 10 items, the top 10 items are shown, while the rest are bundled together in **Others**.</span></span>

#### <a name="url-clicks"></a><span data-ttu-id="c1b5b-206">Clic URL</span><span class="sxs-lookup"><span data-stu-id="c1b5b-206">URL clicks</span></span>

<span data-ttu-id="c1b5b-207">Quando un messaggio di phishing viene recapitato a un destinatario (nella cartella posta in arrivo o posta indesiderata), è sempre possibile che l'utente clicchi sull'URL del payload.</span><span class="sxs-lookup"><span data-stu-id="c1b5b-207">When a phishing message is delivered to a recipient (to the Inbox or the Junk Email folder), there's always a chance that the user will click on the payload URL.</span></span> <span data-ttu-id="c1b5b-208">Non fare clic sull'URL in un messaggio recapitato è una piccola misura di esito positivo, ma è necessario determinare il motivo per cui il messaggio di phishing è stato recapitato alla propria cassetta postale in primo luogo.</span><span class="sxs-lookup"><span data-stu-id="c1b5b-208">Not clicking on the URL in a delivered message is a small measure of success, but you need to determine why the phishing message was delivered to their mailbox in the first place.</span></span>

<span data-ttu-id="c1b5b-209">Se un utente ha fatto clic sull'URL payload nel messaggio di phishing, le azioni vengono visualizzate nell'area **clic URL** del diagramma nella visualizzazione dettagli campagna.</span><span class="sxs-lookup"><span data-stu-id="c1b5b-209">If a user clicked on the payload URL in the phishing message, the actions are displayed in the **URL clicks** area of the diagram in the campaign details view.</span></span>

- <span data-ttu-id="c1b5b-210">**Consentiti**</span><span class="sxs-lookup"><span data-stu-id="c1b5b-210">**Allowed**</span></span>

- <span data-ttu-id="c1b5b-211">**BlockPage**: il destinatario ha fatto clic sull'URL payload, ma l'accesso al sito Web dannoso è stato bloccato dai criteri dei [collegamenti sicuri ATP](atp-safe-links.md) nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c1b5b-211">**BlockPage**: The recipient clicked on the payload URL, but their access to the malicious website was blocked by the [ATP Safe Links](atp-safe-links.md) policies in your organization.</span></span>

- <span data-ttu-id="c1b5b-212">**BlockPageOverride**: il destinatario ha fatto clic sull'URL del payload nel messaggio, i collegamenti sicuri di ATP hanno provato a arrestarli, ma sono stati autorizzati a eseguire l'override del blocco.</span><span class="sxs-lookup"><span data-stu-id="c1b5b-212">**BlockPageOverride**: The recipient clicked on the payload URL in the message, ATP Safe Links tried to stop them, but they were allowed to override the block.</span></span> <span data-ttu-id="c1b5b-213">È necessario esaminare i criteri per i [collegamenti sicuri](set-up-atp-safe-links-policies.md) per capire perché gli utenti possono ignorare il verdetto dei collegamenti sicuri e continuare con il sito Web dannoso.</span><span class="sxs-lookup"><span data-stu-id="c1b5b-213">You need to investigate your [Safe Links policies](set-up-atp-safe-links-policies.md) to see why users are allowed to override the Safe Links verdict and continue to the malicious website.</span></span>

- <span data-ttu-id="c1b5b-214">**PendingDetonationPage**: gli allegati sicuri di ATP è in fase di apertura dell'URL di payload in un ambiente computer virtuale e di vedere cosa accade.</span><span class="sxs-lookup"><span data-stu-id="c1b5b-214">**PendingDetonationPage**: ATP Safe Attachments is in the process of opening the payload URL in a virtual computer environment, and seeing what happens.</span></span>

- <span data-ttu-id="c1b5b-215">**PendingDetonationPageOverride**: al destinatario è stato consentito di ignorare il processo di detonazione del payload e di aprire l'URL senza attendere i risultati.</span><span class="sxs-lookup"><span data-stu-id="c1b5b-215">**PendingDetonationPageOverride**: The recipient was allowed to override the payload detonation process and open the URL without waiting for the results.</span></span>

### <a name="tabs"></a><span data-ttu-id="c1b5b-216">Schede</span><span class="sxs-lookup"><span data-stu-id="c1b5b-216">Tabs</span></span>

<span data-ttu-id="c1b5b-217">Nella visualizzazione dei dettagli della campagna sono disponibili diverse schede che consentono di esaminare la campagna in maniera più approfondita.</span><span class="sxs-lookup"><span data-stu-id="c1b5b-217">There are several tabs in the campaign details view that allow you to further investigate the campaign.</span></span>

- <span data-ttu-id="c1b5b-218">**Clic URL**: se gli utenti non hanno fatto clic sull'URL payload nel messaggio di phishing, questa sezione sarà vuota.</span><span class="sxs-lookup"><span data-stu-id="c1b5b-218">**URL Clicks**: If users didn't click on the payload URL in the phishing message, this section will be blank.</span></span> <span data-ttu-id="c1b5b-219">Se un utente è stato in grado di fare clic sull'URL, verranno inseriti i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="c1b5b-219">If a user was able to click on the URL, the following values will be populated:</span></span>

  - <span data-ttu-id="c1b5b-220">**Utente:**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c1b5b-220">**User**<sup>\*</sup></span></span>

  - <span data-ttu-id="c1b5b-221">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c1b5b-221">**URL**<sup>\*</sup></span></span>

  - <span data-ttu-id="c1b5b-222">**Ora clic**</span><span class="sxs-lookup"><span data-stu-id="c1b5b-222">**Click Time**</span></span>

  - <span data-ttu-id="c1b5b-223">**Azione clic**</span><span class="sxs-lookup"><span data-stu-id="c1b5b-223">**Click Action**</span></span>

- <span data-ttu-id="c1b5b-224">**Indirizzi IP mittenti**</span><span class="sxs-lookup"><span data-stu-id="c1b5b-224">**Sender IPs**</span></span>

  - <span data-ttu-id="c1b5b-225">**Indirizzo IP mittente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c1b5b-225">**Sender IP**<sup>\*</sup></span></span>

  - <span data-ttu-id="c1b5b-226">**Conteggio totale**</span><span class="sxs-lookup"><span data-stu-id="c1b5b-226">**Total Count**</span></span>

  - <span data-ttu-id="c1b5b-227">**Conteggio messaggi in posta in arrivo**</span><span class="sxs-lookup"><span data-stu-id="c1b5b-227">**Inboxed Count**</span></span>

  - <span data-ttu-id="c1b5b-228">**Conteggio bloccati**</span><span class="sxs-lookup"><span data-stu-id="c1b5b-228">**Blocked Count**</span></span>

  - <span data-ttu-id="c1b5b-229">**SPF superato**: il mittente è stato autenticato da [Sender Policy Framework (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md).</span><span class="sxs-lookup"><span data-stu-id="c1b5b-229">**SPF Passed**: The sender was authenticated by the [Sender Policy Framework (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span> <span data-ttu-id="c1b5b-230">Un mittente che non supera la convalida SPF indica che il mittente non è autenticato o che il messaggio è spoofing di un mittente legittimo.</span><span class="sxs-lookup"><span data-stu-id="c1b5b-230">A sender that does not pass SPF validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="c1b5b-231">**Mittenti**</span><span class="sxs-lookup"><span data-stu-id="c1b5b-231">**Senders**</span></span>

  - <span data-ttu-id="c1b5b-232">**Sender**: questo è l'indirizzo effettivo del mittente nel comando SMTP mail from, che non è necessariamente l'indirizzo di posta elettronica da: che gli utenti visualizzano nei client di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="c1b5b-232">**Sender**: This is the actual sender address in the SMTP MAIL FROM command, which is not necessarily the From: email address that users see in their email clients.</span></span>

  - <span data-ttu-id="c1b5b-233">**Conteggio totale**</span><span class="sxs-lookup"><span data-stu-id="c1b5b-233">**Total Count**</span></span>

  - <span data-ttu-id="c1b5b-234">**Posta in arrivo**</span><span class="sxs-lookup"><span data-stu-id="c1b5b-234">**Inboxed**</span></span>

  - <span data-ttu-id="c1b5b-235">**Non ricevuti**</span><span class="sxs-lookup"><span data-stu-id="c1b5b-235">**Not Inboxed**</span></span>

  - <span data-ttu-id="c1b5b-236">**DKIM superato**: il mittente è stato autenticato da [Key Domain identificated mail (DKIM)](support-for-validation-of-dkim-signed-messages.md).</span><span class="sxs-lookup"><span data-stu-id="c1b5b-236">**DKIM Passed**: The sender was authenticated by [Domain Keys Identified Mail (DKIM)](support-for-validation-of-dkim-signed-messages.md).</span></span> <span data-ttu-id="c1b5b-237">Un mittente che non supera la convalida di DKIM indica che il mittente non è autenticato o che il messaggio è spoofing di un mittente legittimo.</span><span class="sxs-lookup"><span data-stu-id="c1b5b-237">A sender that does not pass DKIM validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>

  - <span data-ttu-id="c1b5b-238">**DMARC superato**: il mittente è stato autenticato da [autenticazione dei messaggi basata sul dominio, Reporting e conformità (DMARC)](use-dmarc-to-validate-email.md).</span><span class="sxs-lookup"><span data-stu-id="c1b5b-238">**DMARC Passed**: The sender was authenticated by [Domain-based Message Authentication, Reporting, and Conformance (DMARC)](use-dmarc-to-validate-email.md).</span></span> <span data-ttu-id="c1b5b-239">Un mittente che non supera la convalida di DMARC indica che il mittente non è autenticato o che il messaggio è spoofing di un mittente legittimo.</span><span class="sxs-lookup"><span data-stu-id="c1b5b-239">A sender that does not pass DMARC validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="c1b5b-240">**Payload**</span><span class="sxs-lookup"><span data-stu-id="c1b5b-240">**Payloads**</span></span>

  - <span data-ttu-id="c1b5b-241">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c1b5b-241">**URL**<sup>\*</sup></span></span>

  - <span data-ttu-id="c1b5b-242">**Conteggio totale**</span><span class="sxs-lookup"><span data-stu-id="c1b5b-242">**Total Count**</span></span>

<span data-ttu-id="c1b5b-243"><sup>\*</sup> Se si fa clic su questo valore, viene aperto un nuovo riquadro a comparsa che contiene altri dettagli sulla voce specificata (utente, URL e così via) nella parte superiore della visualizzazione dei dettagli della campagna.</span><span class="sxs-lookup"><span data-stu-id="c1b5b-243"><sup>\*</sup> Clicking on this value opens a new flyout that contains more details about the specified item (user, URL, etc.) on top of the campaign details view.</span></span> <span data-ttu-id="c1b5b-244">Per tornare alla visualizzazione dei dettagli della campagna, fare clic su **Chiudi** nel nuovo riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="c1b5b-244">To return to the campaign details view, click **Done** in the new flyout.</span></span>

### <a name="buttons"></a><span data-ttu-id="c1b5b-245">Pulsanti</span><span class="sxs-lookup"><span data-stu-id="c1b5b-245">Buttons</span></span>

<span data-ttu-id="c1b5b-246">I pulsanti nella visualizzazione dei dettagli della campagna consentono di usare la potenza di Esplora minacce per approfondire la campagna.</span><span class="sxs-lookup"><span data-stu-id="c1b5b-246">The buttons in the campaign details view allow you to use the power of Threat Explorer to further investigate the campaign.</span></span>

- <span data-ttu-id="c1b5b-247">**Esplora minacce**: apre una nuova scheda di ricerca in Esplora minacce usando il valore **ID campagna** come filtro di ricerca.</span><span class="sxs-lookup"><span data-stu-id="c1b5b-247">**Explore campaign**: Opens a new Threat Explorer search tab using the **Campaign ID** value as the search filter.</span></span>

- <span data-ttu-id="c1b5b-248">**Esplorare i messaggi in arrivo**: apre una nuova scheda di ricerca di Esplora minacce utilizzando l' **ID della campagna** e il **percorso di recapito: posta in arrivo** come filtro di ricerca.</span><span class="sxs-lookup"><span data-stu-id="c1b5b-248">**Explore Inboxed messages**: Opens a new Threat Explorer search tab using the **Campaign ID** and **Delivery location: Inbox** as the search filter.</span></span>
