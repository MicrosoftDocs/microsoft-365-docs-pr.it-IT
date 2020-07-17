---
title: Visualizzazioni della campagna in ATP
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
ms.openlocfilehash: fe443c43fa5cea8ec6e3e1c0bc5ee5307b5c28f6
ms.sourcegitcommit: 9ee1261c405f82b49c62390a25dfdea23340d644
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/06/2020
ms.locfileid: "45039483"
---
# <a name="campaign-views-in-atp"></a><span data-ttu-id="003d5-103">Visualizzazioni della campagna in ATP</span><span class="sxs-lookup"><span data-stu-id="003d5-103">Campaign Views in ATP</span></span>

<span data-ttu-id="003d5-104">La visualizzazione della campagna è una funzionalità di Advanced Threat Protection (ATP) nel centro sicurezza & Compliance che identifica e categorizza gli attacchi di phishing nel servizio.</span><span class="sxs-lookup"><span data-stu-id="003d5-104">Campaign Views is a feature in Advanced Threat Protection (ATP) in the Security & Compliance Center that identifies and categorizes phishing attacks in the service.</span></span> <span data-ttu-id="003d5-105">Visualizzazione campagne consente di:</span><span class="sxs-lookup"><span data-stu-id="003d5-105">Campaign Views can help you to:</span></span>

- <span data-ttu-id="003d5-106">Analizzare e rispondere in modo efficiente agli attacchi di phishing.</span><span class="sxs-lookup"><span data-stu-id="003d5-106">Efficiently investigate and respond to phishing attacks.</span></span>

- <span data-ttu-id="003d5-107">Comprendere meglio la portata dell'attacco.</span><span class="sxs-lookup"><span data-stu-id="003d5-107">Better understand the scope of the attack.</span></span>

- <span data-ttu-id="003d5-108">Visualizzare i dettagli dell'attacco.</span><span class="sxs-lookup"><span data-stu-id="003d5-108">Show value to decision makers.</span></span>

<span data-ttu-id="003d5-109">Visualizzazione campagne fornisce una visione d'insieme di un attacco in maniera più rapida e completa rispetto a un processo manuale.</span><span class="sxs-lookup"><span data-stu-id="003d5-109">Campaign Views lets you see the big picture of an attack faster and more complete than any human.</span></span>

## <a name="what-is-a-campaign"></a><span data-ttu-id="003d5-110">Cos'è una campagna?</span><span class="sxs-lookup"><span data-stu-id="003d5-110">What is a campaign?</span></span>

<span data-ttu-id="003d5-111">Una campagna è un attacco coordinato perpetrato tramite posta elettronica contro una o più organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="003d5-111">A campaign is a coordinated email attack against one or many organizations.</span></span> <span data-ttu-id="003d5-112">Gli attacchi tramite posta elettronica che rubano le credenziali e i dati aziendali rappresentano un settore importante e redditizio.</span><span class="sxs-lookup"><span data-stu-id="003d5-112">Email attacks that steal credentials and company data are a big and lucrative industry.</span></span> <span data-ttu-id="003d5-113">Man mano che le tecnologie aumentano nel tentativo di arrestare gli attacchi, gli aggressori modificano i propri metodi nel tentativo di garantire il successo continuativo.</span><span class="sxs-lookup"><span data-stu-id="003d5-113">As technologies increase in an effort to stop attacks, attackers modify their methods in an effort to ensure continued success.</span></span>

<span data-ttu-id="003d5-114">Microsoft sfrutta la vasta quantità di dati antiphishing, di protezione dalla posta indesiderata e antimalware in tutto il servizio per facilitare l'identificazione delle campagne.</span><span class="sxs-lookup"><span data-stu-id="003d5-114">Microsoft leverages the vast amounts of anti-phishing, anti-spam, and anti-malware data across the entire service to help identify campaigns.</span></span> <span data-ttu-id="003d5-115">Vengono analizzate e classificate le informazioni sull'attacco in base a diversi fattori.</span><span class="sxs-lookup"><span data-stu-id="003d5-115">We analyze and classify the attack information according to several factors.</span></span> <span data-ttu-id="003d5-116">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="003d5-116">For example:</span></span>

- <span data-ttu-id="003d5-117">**Origine attacco**: gli indirizzi IP di origine e i domini di posta elettronica del mittente.</span><span class="sxs-lookup"><span data-stu-id="003d5-117">**Attack source**: The source IP addresses and sender email domains.</span></span>

- <span data-ttu-id="003d5-118">**Proprietà del messaggio di attacco**: contenuto, stile e tono dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="003d5-118">**Attack message properties**: The content, style, and tone of the messages.</span></span>

- <span data-ttu-id="003d5-119">**Destinatari dell'attacco**: domini dei destinatari, funzione aziendale dei destinatari (amministratori, dirigenti e così via), tipi di azienda (grandi, piccole, pubbliche, private e così via) e settori.</span><span class="sxs-lookup"><span data-stu-id="003d5-119">**Attack recipients**: Recipient domains, recipient job functions (admins, executives, etc.), company types (large, small, public, private, etc.), and industries.</span></span>

- <span data-ttu-id="003d5-120">**Payload di attacco**: collegamenti dannosi, allegati o altri payload nei messaggi.</span><span class="sxs-lookup"><span data-stu-id="003d5-120">**Attack payload**: Malicious links, attachments, or other payloads in the messages.</span></span>

<span data-ttu-id="003d5-121">Una campagna potrebbe essere di breve durata, o potrebbe interferire tra diversi giorni, settimane o mesi con periodi attivi e inattivi.</span><span class="sxs-lookup"><span data-stu-id="003d5-121">A campaign might be short-lived, or could span several days, weeks, or months with active and inactive periods.</span></span> <span data-ttu-id="003d5-122">Una campagna potrebbe essere avviata con l'organizzazione specifica oppure l'organizzazione potrebbe far parte di una campagna più estesa tra più società.</span><span class="sxs-lookup"><span data-stu-id="003d5-122">A campaign might be launched against your specific organization, or your organization might be part of a larger campaign across multiple companies.</span></span>

## <a name="campaign-views-the-security--compliance-center"></a><span data-ttu-id="003d5-123">Visualizzazione della campagna il Centro sicurezza & Compliance</span><span class="sxs-lookup"><span data-stu-id="003d5-123">Campaign Views the Security & Compliance Center</span></span>

<span data-ttu-id="003d5-124">Le visualizzazioni della campagna sono disponibili nel [Centro sicurezza & conformità](https://protection.office.com) nelle campagne di **gestione delle minacce** \> **Campaigns**o direttamente su <https://protection.office.com/campaigns> .</span><span class="sxs-lookup"><span data-stu-id="003d5-124">Campaign Views is available in the [Security & Compliance Center](https://protection.office.com) at **Threat management** \> **Campaigns**, or directly at <https://protection.office.com/campaigns>.</span></span>

![Panoramica della campagna nel Centro sicurezza e conformità](../../media/campaigns-overview.png)

<span data-ttu-id="003d5-126">È inoltre possibile accedere alle visualizzazioni della campagna da:</span><span class="sxs-lookup"><span data-stu-id="003d5-126">You can also get to Campaign Views from:</span></span>

- <span data-ttu-id="003d5-127">**Gestione delle minacce** \> **Gestione risorse** \> **Visualizzazione** \> **Campagne**</span><span class="sxs-lookup"><span data-stu-id="003d5-127">**Threat management** \> **Explorer** \> **View** \> **Campaigns**</span></span>

- <span data-ttu-id="003d5-128">**Gestione delle minacce** \> **Gestione risorse** \> **Visualizzazione** \> **Tutti i messaggi di posta elettronica** \> Scheda **campagna**</span><span class="sxs-lookup"><span data-stu-id="003d5-128">**Threat management** \> **Explorer** \> **View** \> **All email** \> **Campaign** tab</span></span>

- <span data-ttu-id="003d5-129">**Gestione delle minacce** \> **Gestione risorse** \> **Visualizzazione** \> **Phishing** \> Scheda **campagna**</span><span class="sxs-lookup"><span data-stu-id="003d5-129">**Threat management** \> **Explorer** \> **View** \> **Phish** \> **Campaign** tab</span></span>

- <span data-ttu-id="003d5-130">**Gestione delle minacce** \> **Gestione risorse** \> **Visualizzazione** \> **Malware** \> Scheda **campagna**</span><span class="sxs-lookup"><span data-stu-id="003d5-130">**Threat management** \> **Explorer** \> **View** \> **Malware** \> **Campaign** tab</span></span>

<span data-ttu-id="003d5-131">Per accedere alle visualizzazioni della campagna, è necessario essere membri dei gruppi di ruoli **Gestione organizzazione**, **amministratore sicurezza**o **lettore di sicurezza** nel centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="003d5-131">To access Campaign Views, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Reader** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="003d5-132">Per altre informazioni, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="003d5-132">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="campaigns-overview"></a><span data-ttu-id="003d5-133">Panoramica delle campagne</span><span class="sxs-lookup"><span data-stu-id="003d5-133">Campaigns overview</span></span>

<span data-ttu-id="003d5-134">La pagina Panoramica Visualizza informazioni su tutte le campagne.</span><span class="sxs-lookup"><span data-stu-id="003d5-134">The overview page shows information about all campaigns.</span></span>

<span data-ttu-id="003d5-135">Nella scheda **campagna** predefinita, l'area **tipo di campagna** Visualizza un grafico a barre che indica il numero di destinatari al giorno.</span><span class="sxs-lookup"><span data-stu-id="003d5-135">On the default **Campaign** tab, the **Campaign type** area shows a bar graph that shows the number of recipients per day.</span></span> <span data-ttu-id="003d5-136">Per impostazione predefinita, nel grafico vengono visualizzati i dati di **phishing** e di **malware** .</span><span class="sxs-lookup"><span data-stu-id="003d5-136">By default, the graph shows both **Phish** and **Malware** data.</span></span>

> [!TIP]
> <span data-ttu-id="003d5-137">Se non vengono visualizzati dati sulla campagna, provare a modificare l'intervallo di date o i [filtri](#filters-and-settings).</span><span class="sxs-lookup"><span data-stu-id="003d5-137">If you don't see any campaign data, try changing the date range or [filters](#filters-and-settings).</span></span>

<span data-ttu-id="003d5-138">La parte restante della pagina Panoramica Visualizza le informazioni seguenti nella scheda **campagna** :</span><span class="sxs-lookup"><span data-stu-id="003d5-138">The rest of the overview page shows the following information on the **Campaign** tab:</span></span>

- <span data-ttu-id="003d5-139">**Nome**</span><span class="sxs-lookup"><span data-stu-id="003d5-139">**Name**</span></span>

- <span data-ttu-id="003d5-140">**Esempio di oggetto**: oggetto di uno dei messaggi della campagna.</span><span class="sxs-lookup"><span data-stu-id="003d5-140">**Sample subject**: The subject line of one of the messages in the campaign.</span></span> <span data-ttu-id="003d5-141">Tenere presente che tutti i messaggi nella campagna non avranno necessariamente lo stesso oggetto.</span><span class="sxs-lookup"><span data-stu-id="003d5-141">Note that all messages in the campaign will not necessarily have the same subject.</span></span>

- <span data-ttu-id="003d5-142">**Targeted**: la percentuale calcolata da: (il numero di destinatari della campagna nell'organizzazione)/(il numero totale di destinatari nella campagna tra tutte le organizzazioni del servizio).</span><span class="sxs-lookup"><span data-stu-id="003d5-142">**Targeted**: The percentage as calculated by: (the number of campaign recipients in your organization) / (the total number of recipients in the campaign across all organizations in the service).</span></span> <span data-ttu-id="003d5-143">Questo valore indica la misura in cui la campagna viene specificatamente indirizzata all'organizzazione (un valore superiore) e indirizzata ad altre organizzazioni del servizio (un valore più basso).</span><span class="sxs-lookup"><span data-stu-id="003d5-143">This value indicates the degree to which the campaign is specifically directed at your organization (a higher value) vs. directed at other organizations in the service (a lower value).</span></span>

- <span data-ttu-id="003d5-144">**Type**: questo valore è **phishing** o **malware**.</span><span class="sxs-lookup"><span data-stu-id="003d5-144">**Type**: This value is either **Phish** or **Malware**.</span></span>

- <span data-ttu-id="003d5-145">**Sottotipo**: questo valore contiene maggiori dettagli sulla campagna.</span><span class="sxs-lookup"><span data-stu-id="003d5-145">**Subtype**: This value contains more details about the campaign.</span></span> <span data-ttu-id="003d5-146">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="003d5-146">For example:</span></span>

  - <span data-ttu-id="003d5-147">**Phishing**: se disponibile, il marchio che viene phishing da questa campagna.</span><span class="sxs-lookup"><span data-stu-id="003d5-147">**Phish**: Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="003d5-148">Ad esempio,,,, `Microsoft` `365` `Unknown` `Outlook` o `DocuSign` .</span><span class="sxs-lookup"><span data-stu-id="003d5-148">For example, `Microsoft`, `365`, `Unknown`, `Outlook`, or `DocuSign`.</span></span>

  - <span data-ttu-id="003d5-149">**Malware**: ad esempio, `HTML/PHISH` o `HTML/<MalwareFamilyName>` .</span><span class="sxs-lookup"><span data-stu-id="003d5-149">**Malware**: For example, `HTML/PHISH` or `HTML/<MalwareFamilyName>`.</span></span>

<span data-ttu-id="003d5-150">Se disponibile, il marchio che viene phishing da questa campagna.</span><span class="sxs-lookup"><span data-stu-id="003d5-150">Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="003d5-151">Quando il rilevamento è guidato dalla tecnologia ATP, il prefisso **ATP-** viene aggiunto al valore del sottotipo.</span><span class="sxs-lookup"><span data-stu-id="003d5-151">When the detection is driven by ATP technology, the prefix **ATP-** is added to the subtype value.</span></span>

- <span data-ttu-id="003d5-152">**Destinatari**: il numero di utenti oggetti dell'attacco della campagna.</span><span class="sxs-lookup"><span data-stu-id="003d5-152">**Recipients**: The number of users that were targeted by this campaign.</span></span>

- <span data-ttu-id="003d5-153">**Posta in arrivo**: il numero di utenti che hanno ricevuto messaggi da questa campagna nella posta in arrivo (non recapitati nella cartella posta indesiderata).</span><span class="sxs-lookup"><span data-stu-id="003d5-153">**Inboxed**: The number of users that received messages from this campaign in their Inbox (not delivered to their Junk Email folder).</span></span>

- <span data-ttu-id="003d5-154">**Fare clic**su: numero di utenti che hanno fatto clic sull'URL o che hanno aperto l'allegato nel messaggio di phishing.</span><span class="sxs-lookup"><span data-stu-id="003d5-154">**Clicked**: The number of users that clicked on the URL or opened the attachment in the phishing message.</span></span>

- <span data-ttu-id="003d5-155">**Fare clic su rate**: la percentuale calcolata da "**fare clic su**  /  **posta in arrivo**".</span><span class="sxs-lookup"><span data-stu-id="003d5-155">**Click rate**: The percentage as calculated by "**Clicked** / **Inboxed**".</span></span> <span data-ttu-id="003d5-156">Questo valore è un indicatore dell'efficacia della campagna e indica se i destinatari sono stati in grado di identificare il messaggio come phishing ed evitare di fare clic sull'URL del payload.</span><span class="sxs-lookup"><span data-stu-id="003d5-156">This value is an indicator of the effectiveness of the campaign, and whether the recipients were able to identify the message as phishing and avoid clicking on the payload URL.</span></span>

  <span data-ttu-id="003d5-157">Si noti che questo valore non viene utilizzato nelle campagne antimalware.</span><span class="sxs-lookup"><span data-stu-id="003d5-157">Note that this value isn't used in malware campaigns.</span></span>

- <span data-ttu-id="003d5-158">**Visitato**: numero di utenti effettivamente apportati al sito Web payload.</span><span class="sxs-lookup"><span data-stu-id="003d5-158">**Visited**: How many users actually made it through to the payload website.</span></span> <span data-ttu-id="003d5-159">Se sono presenti valori **cliccati** , ma i collegamenti sicuri impediscono l'accesso al sito Web, questo valore sarà zero.</span><span class="sxs-lookup"><span data-stu-id="003d5-159">If there are **Clicked** values, but Safe Links blocked access to the website, this value will be zero.</span></span>

<span data-ttu-id="003d5-160">La scheda **origine campagna** Visualizza le origini dei messaggi in una mappa del mondo.</span><span class="sxs-lookup"><span data-stu-id="003d5-160">The **Campaign origin** tab shows the message sources on a map of the world.</span></span>

### <a name="filters-and-settings"></a><span data-ttu-id="003d5-161">Filtri e impostazioni</span><span class="sxs-lookup"><span data-stu-id="003d5-161">Filters and settings</span></span>

<span data-ttu-id="003d5-162">Nella parte superiore della pagina visualizzazioni campagna sono disponibili diverse impostazioni di filtro e query che consentono di individuare e isolare campagne specifiche.</span><span class="sxs-lookup"><span data-stu-id="003d5-162">At the top of the Campaign Views page, there are several filter and query settings to help you find and isolate specific campaigns.</span></span>

![Filtri per la campagna](../../media/campaign-filters-and-settings.png)

<span data-ttu-id="003d5-164">La maggior parte dei filtri di base che è possibile eseguire è la data/ora di inizio e la data/ora di fine.</span><span class="sxs-lookup"><span data-stu-id="003d5-164">The most basic filtering that you can do is the start date/time and the end date/time.</span></span>

<span data-ttu-id="003d5-165">Per filtrare ulteriormente la visualizzazione, è possibile eseguire una singola proprietà con un filtro a più valori facendo clic sul pulsante **tipo di campagna** , effettuando la selezione e quindi facendo clic su **Aggiorna**.</span><span class="sxs-lookup"><span data-stu-id="003d5-165">To further filter the view, you can do single property with multiple values filtering by clicking the **Campaign type** button, making your selection, and then clicking **Refresh**.</span></span>

<span data-ttu-id="003d5-166">Le proprietà della campagna disponibili sono descritte nell'elenco seguente:</span><span class="sxs-lookup"><span data-stu-id="003d5-166">The available campaign properties are described in the following list:</span></span>

- <span data-ttu-id="003d5-167">Base</span><span class="sxs-lookup"><span data-stu-id="003d5-167">Basic</span></span>

  - <span data-ttu-id="003d5-168">**Tipo di campagna**: selezionare **malware** o **phishing**.</span><span class="sxs-lookup"><span data-stu-id="003d5-168">**Campaign type**: Select **Malware** or **Phish**.</span></span> <span data-ttu-id="003d5-169">La cancellazione delle selezioni ha lo stesso risultato della selezione di entrambi.</span><span class="sxs-lookup"><span data-stu-id="003d5-169">Clearing the selections has the same result as selecting both.</span></span>
  - <span data-ttu-id="003d5-170">**Nome della campagna**</span><span class="sxs-lookup"><span data-stu-id="003d5-170">**Campaign name**</span></span>
  - <span data-ttu-id="003d5-171">**Sottotipo di campagna**</span><span class="sxs-lookup"><span data-stu-id="003d5-171">**Campaign subtype**</span></span>
  - <span data-ttu-id="003d5-172">**Mittente**</span><span class="sxs-lookup"><span data-stu-id="003d5-172">**Sender**</span></span>
  - <span data-ttu-id="003d5-173">**Destinatari**</span><span class="sxs-lookup"><span data-stu-id="003d5-173">**Recipients**</span></span>
  - <span data-ttu-id="003d5-174">**Dominio mittente**</span><span class="sxs-lookup"><span data-stu-id="003d5-174">**Sender domain**</span></span>
  - <span data-ttu-id="003d5-175">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="003d5-175">**Subject**</span></span>
  - <span data-ttu-id="003d5-176">**Nome file allegato**</span><span class="sxs-lookup"><span data-stu-id="003d5-176">**Attachment filename**</span></span>
  - <span data-ttu-id="003d5-177">**Famiglia di malware**</span><span class="sxs-lookup"><span data-stu-id="003d5-177">**Malware family**</span></span>
  - <span data-ttu-id="003d5-178">**Azione per il recapito**</span><span class="sxs-lookup"><span data-stu-id="003d5-178">**Delivery action**</span></span>
  - <span data-ttu-id="003d5-179">**Tecnologia di rilevamento**</span><span class="sxs-lookup"><span data-stu-id="003d5-179">**Detection technology**</span></span>
  - <span data-ttu-id="003d5-180">**Categorie**</span><span class="sxs-lookup"><span data-stu-id="003d5-180">**Tags**</span></span>
  - <span data-ttu-id="003d5-181">**Sostituzioni del sistema**</span><span class="sxs-lookup"><span data-stu-id="003d5-181">**System overrides**</span></span>

- <span data-ttu-id="003d5-182">Impostazioni avanzate</span><span class="sxs-lookup"><span data-stu-id="003d5-182">Advanced</span></span>

  - <span data-ttu-id="003d5-183">**ID messaggio Internet**: disponibile nel campo di intestazione **Message-ID** nell'intestazione del messaggio.</span><span class="sxs-lookup"><span data-stu-id="003d5-183">**Internet message ID**: Available in the **Message-ID** header field in the message header.</span></span> <span data-ttu-id="003d5-184">Un valore di esempio è `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (si notino le parentesi angolari).</span><span class="sxs-lookup"><span data-stu-id="003d5-184">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
  
  - <span data-ttu-id="003d5-185">**ID messaggio di rete**: valore GUID disponibile nel campo di intestazione **X-MS-Exchange-Organization-network-Message-ID** nell'intestazione del messaggio.</span><span class="sxs-lookup"><span data-stu-id="003d5-185">**Network message ID**: A GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header field in the message header.</span></span>
  
  - <span data-ttu-id="003d5-186">**Indirizzo IP mittente**</span><span class="sxs-lookup"><span data-stu-id="003d5-186">**Sender IP**</span></span>
  
  - <span data-ttu-id="003d5-187">**Attachment SHA256**: per trovare il valore hash SHA256 di un file in Windows, eseguire il comando seguente in un prompt dei comandi: `certutil.exe -hashfile "<Path>\<Filename>" SHA256` .</span><span class="sxs-lookup"><span data-stu-id="003d5-187">**Attachment SHA256**: To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt: `certutil.exe -hashfile "<Path>\<Filename>" SHA256`.</span></span>
  
  - <span data-ttu-id="003d5-188">**ID cluster**</span><span class="sxs-lookup"><span data-stu-id="003d5-188">**Cluster ID**</span></span>
  
  - <span data-ttu-id="003d5-189">**ID criteri di avviso**</span><span class="sxs-lookup"><span data-stu-id="003d5-189">**Alert Policy ID**</span></span>

- <span data-ttu-id="003d5-190">URL</span><span class="sxs-lookup"><span data-stu-id="003d5-190">URLs</span></span>

  - <span data-ttu-id="003d5-191">**Dominio URL**</span><span class="sxs-lookup"><span data-stu-id="003d5-191">**URL domain**</span></span>
  - <span data-ttu-id="003d5-192">**Dominio e percorso URL**</span><span class="sxs-lookup"><span data-stu-id="003d5-192">**URL domain and path**</span></span>
  - <span data-ttu-id="003d5-193">**URL**</span><span class="sxs-lookup"><span data-stu-id="003d5-193">**URL**</span></span>
  - <span data-ttu-id="003d5-194">**Percorso URL**</span><span class="sxs-lookup"><span data-stu-id="003d5-194">**URL path**</span></span>
  - <span data-ttu-id="003d5-195">**Fare clic su verdetto**</span><span class="sxs-lookup"><span data-stu-id="003d5-195">**Click verdict**</span></span>

<span data-ttu-id="003d5-196">Per un filtro più avanzato, tra cui il filtro in base a più proprietà, è possibile fare clic sul pulsante **filtro avanzato** per creare una query.</span><span class="sxs-lookup"><span data-stu-id="003d5-196">For more advanced filtering, including filtering by multiple properties, you can click the **Advanced filter** button to build a query.</span></span> <span data-ttu-id="003d5-197">Sono disponibili le stesse proprietà della campagna, ma con i miglioramenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="003d5-197">The same campaign properties are available, but with the following enhancements:</span></span>

- <span data-ttu-id="003d5-198">È possibile fare clic su **Aggiungi condizione** per selezionare più condizioni.</span><span class="sxs-lookup"><span data-stu-id="003d5-198">You can click **Add a condition** to select multiple conditions.</span></span>
- <span data-ttu-id="003d5-199">È possibile scegliere l'operatore **and** o **or** tra le condizioni.</span><span class="sxs-lookup"><span data-stu-id="003d5-199">You can choose the **And** or **Or** operator between conditions.</span></span>
- <span data-ttu-id="003d5-200">È possibile selezionare l'elemento del **gruppo** di condizioni nella parte inferiore dell'elenco delle condizioni per formare condizioni composte complesse.</span><span class="sxs-lookup"><span data-stu-id="003d5-200">You can select the **Condition group** item at the bottom of the conditions list to form complex compound conditions.</span></span>

<span data-ttu-id="003d5-201">Al termine, fare clic sul pulsante **query** .</span><span class="sxs-lookup"><span data-stu-id="003d5-201">When you're finished, click the **Query** button.</span></span>

<span data-ttu-id="003d5-202">Dopo aver creato un filtro di base o avanzato, è possibile salvarlo tramite **Save Query** or **Save query As**.</span><span class="sxs-lookup"><span data-stu-id="003d5-202">After you create a basic or advanced filter, you can save it by using **Save query** or **Save query as**.</span></span> <span data-ttu-id="003d5-203">Successivamente, quando si torna alla visualizzazione della campagna, è possibile caricare un filtro salvato facendo clic su **Impostazioni query salvate**.</span><span class="sxs-lookup"><span data-stu-id="003d5-203">Later, when you return to Campaign Views, you can load a saved filter by clicking **Saved query settings**.</span></span>

<span data-ttu-id="003d5-204">Per esportare il grafico o l'elenco delle campagne, fare clic su **Esporta** e selezionare **Esporta dati grafico** o **Esporta campagna**.</span><span class="sxs-lookup"><span data-stu-id="003d5-204">To export the graph or the list of campaigns, click **Export** and select **Export chart data** or **Export campaign list**.</span></span>

<span data-ttu-id="003d5-205">Se si dispone di un abbonamento a Microsoft Defender ATP, è possibile fare clic su **WDATP** per connettere o disconnettere le informazioni sulle campagne con Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="003d5-205">If you have a Microsoft Defender ATP subscription, you can click **WDATP** to connect or disconnect the campaigns information with Microsoft Defender ATP.</span></span> <span data-ttu-id="003d5-206">Per ulteriori informazioni, vedere [integrazione di Office 365 ATP con Microsoft Defender ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/integrate-office-365-ti-with-wdatp).</span><span class="sxs-lookup"><span data-stu-id="003d5-206">For more information, see [Integrate Office 365 ATP with Microsoft Defender ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/integrate-office-365-ti-with-wdatp).</span></span>

## <a name="campaign-details"></a><span data-ttu-id="003d5-207">Dettagli campagna</span><span class="sxs-lookup"><span data-stu-id="003d5-207">Campaign details</span></span>

<span data-ttu-id="003d5-208">Quando si fa clic sul nome di una campagna, i dettagli della campagna vengono visualizzati in un riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="003d5-208">When you click on the name of a campaign, the campaign details appear in a flyout.</span></span>

### <a name="campaign-information"></a><span data-ttu-id="003d5-209">Informazioni sulla campagna</span><span class="sxs-lookup"><span data-stu-id="003d5-209">Campaign information</span></span>

<span data-ttu-id="003d5-210">Nella parte superiore della visualizzazione dettagli campagna sono disponibili le informazioni sulla campagna seguenti:</span><span class="sxs-lookup"><span data-stu-id="003d5-210">At the top of the campaign details view, the following campaign information is available:</span></span>

- <span data-ttu-id="003d5-211">**ID**: l'identificatore della campagna univoco.</span><span class="sxs-lookup"><span data-stu-id="003d5-211">**ID**: The unique campaign identifier.</span></span>

- <span data-ttu-id="003d5-212">**Started** and **ended**: la data di inizio e la data di fine della campagna.</span><span class="sxs-lookup"><span data-stu-id="003d5-212">**Started** and **Ended**: The start date and end date of the campaign.</span></span> <span data-ttu-id="003d5-213">Si noti che queste date potrebbero essere estese oltre le date di filtro selezionate nella pagina panoramica.</span><span class="sxs-lookup"><span data-stu-id="003d5-213">Note that these dates might extend further than your filter dates that you selected on the overview page.</span></span>

- <span data-ttu-id="003d5-214">**Impatto**: in questa sezione sono contenuti i dati seguenti per il filtro intervallo di date selezionato (o che si seleziona nella sequenza temporale):</span><span class="sxs-lookup"><span data-stu-id="003d5-214">**Impact**: This section contains the following data for the date range filter you selected (or that you select in the timeline):</span></span>
  
  - <span data-ttu-id="003d5-215">Numero totale di destinatari.</span><span class="sxs-lookup"><span data-stu-id="003d5-215">The total number of recipients.</span></span>
  - <span data-ttu-id="003d5-216">Il numero di messaggi che sono stati "ricevuti" (ovvero recapitati nella posta in arrivo, non nella cartella posta indesiderata).</span><span class="sxs-lookup"><span data-stu-id="003d5-216">The number of messages that were "Inboxed" (that is, delivered to the Inbox, not to the Junk Email folder).</span></span>
  - <span data-ttu-id="003d5-217">Il numero di utenti che hanno fatto clic sul payload URL nel messaggio di phishing.</span><span class="sxs-lookup"><span data-stu-id="003d5-217">How many users clicked on the URL payload in the phishing message.</span></span>
  - <span data-ttu-id="003d5-218">Howe molti utenti hanno visitato l'URL.</span><span class="sxs-lookup"><span data-stu-id="003d5-218">Howe many users visited the URL.</span></span>

- <span data-ttu-id="003d5-219">**Targeted**: la percentuale calcolata da: (il numero di destinatari della campagna nell'organizzazione)/(il numero totale di destinatari nella campagna tra tutte le organizzazioni del servizio).</span><span class="sxs-lookup"><span data-stu-id="003d5-219">**Targeted**: The percentage as calculated by: (the number of campaign recipients in your organization) / (the total number of recipients in the campaign across all organizations in the service).</span></span> <span data-ttu-id="003d5-220">Si noti che questo valore viene calcolato per tutta la durata della campagna e non modifica le date del filtro.</span><span class="sxs-lookup"><span data-stu-id="003d5-220">Note that this value is calculated over the entire lifetime of the campaign, and doesn't change the filter dates.</span></span>

- <span data-ttu-id="003d5-221">Una cronologia interattiva delle attività della campagna: la sequenza temporale Visualizza le attività per l'intera durata della campagna.</span><span class="sxs-lookup"><span data-stu-id="003d5-221">An interactive timeline of campaign activity: The timeline shows activity over the entire lifetime of the campaign.</span></span> <span data-ttu-id="003d5-222">Per impostazione predefinita, l'area ombreggiata include il filtro dell'intervallo di date selezionato nella panoramica.</span><span class="sxs-lookup"><span data-stu-id="003d5-222">By default, the shaded area includes the date range filter that you selected in the overview.</span></span> <span data-ttu-id="003d5-223">È possibile fare clic e trascinare per selezionare un punto iniziale e un punto finale specifici, <u>che modificheranno i dati visualizzati nell'area di **impatto** e nel resto della pagina come descritto nelle sezioni successive</u>.</span><span class="sxs-lookup"><span data-stu-id="003d5-223">You can click and drag to select a specific start point and end point, <u>which will change the data that's displayed in **Impact** area, and on the rest of the page as described in the next sections</u>.</span></span>

<span data-ttu-id="003d5-224">Nella barra del titolo, è possibile fare clic sull'icona **download campagna** write-up per scaricare la campagna ![ per scaricare ](../../media/download-campaign-write-up-button.png) i dettagli della campagna in un documento di Word (per impostazione predefinita, denominato CampaignReport.docx).</span><span class="sxs-lookup"><span data-stu-id="003d5-224">In the title bar, you can click the **Download campaign write-up** button ![Download campaign write-up icon](../../media/download-campaign-write-up-button.png) to download the campaign details to a Word document (by default, named CampaignReport.docx).</span></span> <span data-ttu-id="003d5-225">Tenere presente che questo documento contiene informazioni dettagliate sull'intero ciclo di vita della campagna (non solo le date di filtro selezionate).</span><span class="sxs-lookup"><span data-stu-id="003d5-225">Note that this document contains details over the entire lifetime of the campaign (not just the filter dates you selected).</span></span>

![Informazioni sulla campagna](../../media/campaign-details-campaign-info.png)

### <a name="campaign-flow"></a><span data-ttu-id="003d5-227">Flusso della campagna</span><span class="sxs-lookup"><span data-stu-id="003d5-227">Campaign flow</span></span>

<span data-ttu-id="003d5-228">Al centro della visualizzazione dettagli campagna, i dettagli importanti sulla campagna sono presentati nella sezione **flusso** in un diagramma di flusso orizzontale (noto come diagramma di _Sankey_ ).</span><span class="sxs-lookup"><span data-stu-id="003d5-228">In the middle of the campaign details view, important details about the campaign are presented in the **Flow** section in a horizontal flow diagram (known as a _Sankey_ diagram).</span></span> <span data-ttu-id="003d5-229">Questi dettagli aiuteranno a comprendere gli elementi della campagna e il potenziale impatto sull'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="003d5-229">These details will help you to understand the elements of the campaign and the potential impact in your organization.</span></span>

> [!TIP]
> <span data-ttu-id="003d5-230">Le informazioni visualizzate nel diagramma di **flusso** sono controllate dall'intervallo di date ombreggiato nella sequenza temporale, come descritto nella sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="003d5-230">The information that's displayed in the **Flow** diagram is controlled by the shaded date range in the timeline as described in the previous section.</span></span>

![Dettagli della campagna che non contengono clic sull'URL da parte dell'utente](../../media/campaign-details-no-recipient-actions.png)

<span data-ttu-id="003d5-232">Se si passa il mouse su una fascia orizzontale nel diagramma, viene visualizzato il numero di messaggi correlati (ad esempio i messaggi provenienti da un determinato IP di origine, i messaggi provenienti dall'IP di origine con il dominio del mittente specificato e così via).</span><span class="sxs-lookup"><span data-stu-id="003d5-232">If you hover over a horizontal band in the diagram, you'll see the number of related messages (for example, messages from a particular source IP, messages from the source IP using the specified sender domain, etc.).</span></span>

<span data-ttu-id="003d5-233">Il diagramma include le seguenti informazioni:</span><span class="sxs-lookup"><span data-stu-id="003d5-233">The diagram contains the following information:</span></span>

- <span data-ttu-id="003d5-234">**Indirizzi IP mittenti**</span><span class="sxs-lookup"><span data-stu-id="003d5-234">**Sender IPs**</span></span>

- <span data-ttu-id="003d5-235">**Domini mittenti**</span><span class="sxs-lookup"><span data-stu-id="003d5-235">**Sender domains**</span></span>

- <span data-ttu-id="003d5-236">**Verdetti del filtro**: questi valori sono correlati ai verdetti di filtraggio della posta indesiderata e phishing disponibili come descritto nelle intestazioni dei messaggi di protezione dalla [posta indesiderata](anti-spam-message-headers.md).</span><span class="sxs-lookup"><span data-stu-id="003d5-236">**Filter verdicts**: These values are related to the available phishing and spam filtering verdicts as described in [Anti-spam message headers](anti-spam-message-headers.md).</span></span> <span data-ttu-id="003d5-237">I valori disponibili sono descritti nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="003d5-237">The available values are described in the following table:</span></span>

  ||||
  |---|---|---|
  |<span data-ttu-id="003d5-238">**Valore**</span><span class="sxs-lookup"><span data-stu-id="003d5-238">**Value**</span></span>|<span data-ttu-id="003d5-239">**Verdetto del filtro posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="003d5-239">**Spam filter verdict**</span></span>|<span data-ttu-id="003d5-240">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="003d5-240">**Description**</span></span>|
  |<span data-ttu-id="003d5-241">**Consentiti**</span><span class="sxs-lookup"><span data-stu-id="003d5-241">**Allowed**</span></span>|`SFV:SKN` <br/><br/> `SFV:SKI`|<span data-ttu-id="003d5-242">Il messaggio è stato contrassegnato come non indesiderato e/o il filtro saltato prima di essere valutato tramite il filtro posta indesiderata, ad esempio tramite una regola del flusso di posta, nota anche come regola di trasporto.</span><span class="sxs-lookup"><span data-stu-id="003d5-242">The message was marked as not spam and/or skipped filtering before being evaluated by spam filtering (for example, by a mail flow rule, also known as a transport rule).</span></span><br/><br/><span data-ttu-id="003d5-243">Il messaggio ha ignorato il filtro per la posta indesiderata per altri motivi (ad esempio, il mittente e il destinatario sono presenti nella stessa organizzazione).</span><span class="sxs-lookup"><span data-stu-id="003d5-243">The message skipped spam filtering for other reasons (for example, the sender and recipient appear to be in the same organization).</span></span>|
  |<span data-ttu-id="003d5-244">**Bloccati**</span><span class="sxs-lookup"><span data-stu-id="003d5-244">**Blocked**</span></span>|`SFV:SKS`|<span data-ttu-id="003d5-245">Il messaggio è stato contrassegnato come posta indesiderata prima di essere valutato tramite il filtro posta indesiderata, ad esempio tramite una regola del flusso di posta.</span><span class="sxs-lookup"><span data-stu-id="003d5-245">The message was marked as spam before being evaluated by spam filtering (for example, by a mail flow rule).</span></span>|
  |<span data-ttu-id="003d5-246">**Rilevato**</span><span class="sxs-lookup"><span data-stu-id="003d5-246">**Detected**</span></span>|`SFV:SPM`|<span data-ttu-id="003d5-247">Il messaggio è stato contrassegnato come posta indesiderata dal filtro posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="003d5-247">The message was marked as spam by spam filtering.</span></span>|
  |<span data-ttu-id="003d5-248">**Non rilevato**</span><span class="sxs-lookup"><span data-stu-id="003d5-248">**Not Detected**</span></span>|`SFV:NSPM`|<span data-ttu-id="003d5-249">Il messaggio è stato contrassegnato come non indesiderato dal filtro posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="003d5-249">The message was marked as not spam by spam filtering.</span></span>|
  |<span data-ttu-id="003d5-250">**Rilasciato**</span><span class="sxs-lookup"><span data-stu-id="003d5-250">**Released**</span></span>|`SFV:SKQ`|<span data-ttu-id="003d5-251">Il messaggio ha ignorato il filtro della posta indesiderata perché è stato rilasciato dalla quarantena.</span><span class="sxs-lookup"><span data-stu-id="003d5-251">The message skipped spam filtering because it was released from quarantine.</span></span>|
  |<span data-ttu-id="003d5-252">**Consenti tenant**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="003d5-252">**Tenant Allow**<sup>\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="003d5-253">Il messaggio ha ignorato il filtro della posta indesiderata a causa delle impostazioni dei criteri di protezione dalla posta indesiderata (ad esempio, il mittente è nell'elenco dei mittenti consentito o nel dominio consentito).</span><span class="sxs-lookup"><span data-stu-id="003d5-253">The message skipped spam filtering due to anti-spam policy settings (for example, the sender was in the allowed sender list or allowed domain list).</span></span>|
  |<span data-ttu-id="003d5-254">**Blocco tenant**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="003d5-254">**Tenant Block**<sup>\*\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="003d5-255">Il messaggio è stato bloccato dal filtro posta indesiderata a causa delle impostazioni dei criteri di protezione da posta indesiderata (ad esempio, il mittente è nell'elenco dei mittenti consentiti o nel dominio consentito).</span><span class="sxs-lookup"><span data-stu-id="003d5-255">The message was blocked by spam filtering due to anti-spam policy settings (for example, the sender was in the allowed sender list or allowed domain list).</span></span>|
  |<span data-ttu-id="003d5-256">**Consenti utente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="003d5-256">**User Allow**<sup>\*</sup></span></span>|`SFV:SFE`|<span data-ttu-id="003d5-257">Il messaggio ha ignorato il filtro della posta indesiderata perché il mittente si trovava nell'elenco Mittenti attendibili di un utente in Outlook.</span><span class="sxs-lookup"><span data-stu-id="003d5-257">The message skipped spam filtering because the sender was in a user's Safe Senders list in Outlook.</span></span>|
  |<span data-ttu-id="003d5-258">**Blocco utenti**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="003d5-258">**User Block**<sup>\*\*</sup></span></span>|`SFV:BLK`|<span data-ttu-id="003d5-259">Il messaggio è stato bloccato dal filtro posta indesiderata perché il mittente si trovava nell'elenco Mittenti bloccati di un utente in Outlook.</span><span class="sxs-lookup"><span data-stu-id="003d5-259">The message was blocked by spam filtering because the sender was in a user's Blocked Senders list in Outlook.</span></span>|
  |<span data-ttu-id="003d5-260">**ZAP**</span><span class="sxs-lookup"><span data-stu-id="003d5-260">**ZAP**</span></span>|<span data-ttu-id="003d5-261">n/d</span><span class="sxs-lookup"><span data-stu-id="003d5-261">n/a</span></span>|<span data-ttu-id="003d5-262">[Zero-hour auto Purge (ZAP)](zero-hour-auto-purge.md) ha eseguito un'azione sul messaggio recapitato in base alle impostazioni dei criteri di protezione da posta indesiderata (spostati nella cartella posta indesiderata o in quarantena).</span><span class="sxs-lookup"><span data-stu-id="003d5-262">[Zero-hour auto purge (ZAP)](zero-hour-auto-purge.md) took action on the delivered message according to your anti-spam policy settings (moved to the Junk Email folder or Quarantined).</span></span>|
  |

  <span data-ttu-id="003d5-263"><sup>\*</sup>Esaminare i criteri di protezione da posta indesiderata, poiché il servizio potrebbe essere stato bloccato.</span><span class="sxs-lookup"><span data-stu-id="003d5-263"><sup>\*</sup> Review your anti-spam policies, because the allowed message would have likely been blocked by the service.</span></span>

  <span data-ttu-id="003d5-264"><sup>\*\*</sup>Esaminare i criteri di protezione da posta indesiderata, poiché tali messaggi devono essere messi in quarantena, non recapitati.</span><span class="sxs-lookup"><span data-stu-id="003d5-264"><sup>\*\*</sup> Review your anti-spam policies, because these messages should be quarantined, not delivered.</span></span>

- <span data-ttu-id="003d5-265">**Posizioni di recapito**: è consigliabile esaminare i messaggi che sono stati effettivamente recapitati ai destinatari (nella cartella posta in arrivo o posta indesiderata), anche se gli utenti non hanno fatto clic sull'URL del payload nel messaggio.</span><span class="sxs-lookup"><span data-stu-id="003d5-265">**Delivery locations**: You'll likely want to investigate messages that were actually delivered to recipients (either to the Inbox or the Junk Email folder), even if users didn't click on the payload URL in the message.</span></span> <span data-ttu-id="003d5-266">È inoltre possibile rimuovere i messaggi in quarantena dalla quarantena.</span><span class="sxs-lookup"><span data-stu-id="003d5-266">You can also remove the quarantined messages from quarantine.</span></span> <span data-ttu-id="003d5-267">Per ulteriori informazioni, vedere [messaggi di posta elettronica in quarantena in EOP](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="003d5-267">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

  - <span data-ttu-id="003d5-268">**Cartella eliminata**</span><span class="sxs-lookup"><span data-stu-id="003d5-268">**Deleted folder**</span></span>
  - <span data-ttu-id="003d5-269">**Interrotte**</span><span class="sxs-lookup"><span data-stu-id="003d5-269">**Dropped**</span></span>
  - <span data-ttu-id="003d5-270">**External**: il destinatario si trova nell'organizzazione di posta elettronica locale in ambienti ibridi.</span><span class="sxs-lookup"><span data-stu-id="003d5-270">**External**: The recipient is located in your on-premises email organization in hybrid environments.</span></span>
  - <span data-ttu-id="003d5-271">**Operazione non riuscita**</span><span class="sxs-lookup"><span data-stu-id="003d5-271">**Failed**</span></span>
  - <span data-ttu-id="003d5-272">**Inoltrato**</span><span class="sxs-lookup"><span data-stu-id="003d5-272">**Forwarded**</span></span>
  - <span data-ttu-id="003d5-273">**Posta in arrivo**</span><span class="sxs-lookup"><span data-stu-id="003d5-273">**Inbox**</span></span>
  - <span data-ttu-id="003d5-274">**Posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="003d5-274">**Junk folder**</span></span>
  - <span data-ttu-id="003d5-275">**Quarantena**</span><span class="sxs-lookup"><span data-stu-id="003d5-275">**Quarantine**</span></span>
  - <span data-ttu-id="003d5-276">**Unknown**</span><span class="sxs-lookup"><span data-stu-id="003d5-276">**Unknown**</span></span>

- <span data-ttu-id="003d5-277">**Clic URL**: sono descritti nella sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="003d5-277">**URL clicks**: These are described in the next section.</span></span>

> [!NOTE]
> <span data-ttu-id="003d5-278">In tutti i layer che contengono più di 10 elementi vengono visualizzati i primi 10 elementi, mentre quelli restanti sono raggruppati in **altri**.</span><span class="sxs-lookup"><span data-stu-id="003d5-278">In all layers that contain more than 10 items, the top 10 items are shown, while the rest are bundled together in **Others**.</span></span>

#### <a name="url-clicks"></a><span data-ttu-id="003d5-279">Clic URL</span><span class="sxs-lookup"><span data-stu-id="003d5-279">URL clicks</span></span>

<span data-ttu-id="003d5-280">Quando un messaggio di phishing viene recapitato a un destinatario (nella cartella posta in arrivo o posta indesiderata), è sempre possibile che l'utente clicchi sull'URL del payload.</span><span class="sxs-lookup"><span data-stu-id="003d5-280">When a phishing message is delivered to a recipient (to the Inbox or the Junk Email folder), there's always a chance that the user will click on the payload URL.</span></span> <span data-ttu-id="003d5-281">Non fare clic sull'URL in un messaggio recapitato è una piccola misura di esito positivo, ma è necessario determinare il motivo per cui il messaggio di phishing è stato recapitato alla propria cassetta postale in primo luogo.</span><span class="sxs-lookup"><span data-stu-id="003d5-281">Not clicking on the URL in a delivered message is a small measure of success, but you need to determine why the phishing message was delivered to their mailbox in the first place.</span></span>

<span data-ttu-id="003d5-282">Se un utente ha fatto clic sull'URL payload nel messaggio di phishing, le azioni vengono visualizzate nell'area **clic URL** del diagramma nella visualizzazione dettagli campagna.</span><span class="sxs-lookup"><span data-stu-id="003d5-282">If a user clicked on the payload URL in the phishing message, the actions are displayed in the **URL clicks** area of the diagram in the campaign details view.</span></span>

- <span data-ttu-id="003d5-283">**Consentiti**</span><span class="sxs-lookup"><span data-stu-id="003d5-283">**Allowed**</span></span>

- <span data-ttu-id="003d5-284">**BlockPage**: il destinatario ha fatto clic sull'URL payload, ma l'accesso al sito Web dannoso è stato bloccato dai criteri dei [collegamenti sicuri ATP](atp-safe-links.md) nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="003d5-284">**BlockPage**: The recipient clicked on the payload URL, but their access to the malicious website was blocked by the [ATP Safe Links](atp-safe-links.md) policies in your organization.</span></span>

- <span data-ttu-id="003d5-285">**BlockPageOverride**: il destinatario ha fatto clic sull'URL del payload nel messaggio, i collegamenti sicuri di ATP hanno provato a arrestarli, ma sono stati autorizzati a eseguire l'override del blocco.</span><span class="sxs-lookup"><span data-stu-id="003d5-285">**BlockPageOverride**: The recipient clicked on the payload URL in the message, ATP Safe Links tried to stop them, but they were allowed to override the block.</span></span> <span data-ttu-id="003d5-286">È necessario esaminare i criteri per i [collegamenti sicuri](set-up-atp-safe-links-policies.md) per capire perché gli utenti possono ignorare il verdetto dei collegamenti sicuri e continuare con il sito Web dannoso.</span><span class="sxs-lookup"><span data-stu-id="003d5-286">You need to investigate your [Safe Links policies](set-up-atp-safe-links-policies.md) to see why users are allowed to override the Safe Links verdict and continue to the malicious website.</span></span>

- <span data-ttu-id="003d5-287">**PendingDetonationPage**: gli allegati sicuri di ATP è in fase di apertura dell'URL di payload in un ambiente computer virtuale e di vedere cosa accade.</span><span class="sxs-lookup"><span data-stu-id="003d5-287">**PendingDetonationPage**: ATP Safe Attachments is in the process of opening the payload URL in a virtual computer environment, and seeing what happens.</span></span>

- <span data-ttu-id="003d5-288">**PendingDetonationPageOverride**: al destinatario è stato consentito di ignorare il processo di detonazione del payload e di aprire l'URL senza attendere i risultati.</span><span class="sxs-lookup"><span data-stu-id="003d5-288">**PendingDetonationPageOverride**: The recipient was allowed to override the payload detonation process and open the URL without waiting for the results.</span></span>

### <a name="tabs"></a><span data-ttu-id="003d5-289">Schede</span><span class="sxs-lookup"><span data-stu-id="003d5-289">Tabs</span></span>

<span data-ttu-id="003d5-290">Le schede nella visualizzazione dettagli campagna consentono di analizzare ulteriormente la campagna.</span><span class="sxs-lookup"><span data-stu-id="003d5-290">The tabs in the campaign details view allow you to further investigate the campaign.</span></span>

> [!TIP]
> <span data-ttu-id="003d5-291">Le informazioni visualizzate nelle schede sono controllate dall'intervallo di date ombreggiato nella sequenza temporale, come descritto nella sezione [informazioni sulla campagna](#campaign-information) .</span><span class="sxs-lookup"><span data-stu-id="003d5-291">The information that's displayed on the tabs is controlled by the shaded date range in the timeline as described in [Campaign information](#campaign-information) section.</span></span>

- <span data-ttu-id="003d5-292">**Clic URL**: se gli utenti non hanno fatto clic sull'URL payload nel messaggio di phishing, questa sezione sarà vuota.</span><span class="sxs-lookup"><span data-stu-id="003d5-292">**URL clicks**: If users didn't click on the payload URL in the phishing message, this section will be blank.</span></span> <span data-ttu-id="003d5-293">Se un utente è stato in grado di fare clic sull'URL, verranno inseriti i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="003d5-293">If a user was able to click on the URL, the following values will be populated:</span></span>

  - <span data-ttu-id="003d5-294">**Utente:**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="003d5-294">**User**<sup>\*</sup></span></span>
  - <span data-ttu-id="003d5-295">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="003d5-295">**URL**<sup>\*</sup></span></span>
  - <span data-ttu-id="003d5-296">**Fare clic su tempo**</span><span class="sxs-lookup"><span data-stu-id="003d5-296">**Click time**</span></span>
  - <span data-ttu-id="003d5-297">**Fare clic su verdetto**</span><span class="sxs-lookup"><span data-stu-id="003d5-297">**Click verdict**</span></span>

- <span data-ttu-id="003d5-298">**Indirizzi IP mittenti**</span><span class="sxs-lookup"><span data-stu-id="003d5-298">**Sender IPs**</span></span>

  - <span data-ttu-id="003d5-299">**Indirizzo IP mittente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="003d5-299">**Sender IP**<sup>\*</sup></span></span>
  - <span data-ttu-id="003d5-300">**Conteggio totale**</span><span class="sxs-lookup"><span data-stu-id="003d5-300">**Total count**</span></span>
  - <span data-ttu-id="003d5-301">**Posta in arrivo**</span><span class="sxs-lookup"><span data-stu-id="003d5-301">**Inboxed**</span></span>
  - <span data-ttu-id="003d5-302">**Non ricevuti**</span><span class="sxs-lookup"><span data-stu-id="003d5-302">**Not Inboxed**</span></span>
  - <span data-ttu-id="003d5-303">**SPF superato**: il mittente è stato autenticato da [Sender Policy Framework (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md).</span><span class="sxs-lookup"><span data-stu-id="003d5-303">**SPF passed**: The sender was authenticated by the [Sender Policy Framework (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span> <span data-ttu-id="003d5-304">Un mittente che non supera la convalida SPF indica che il mittente non è autenticato o che il messaggio è spoofing di un mittente legittimo.</span><span class="sxs-lookup"><span data-stu-id="003d5-304">A sender that does not pass SPF validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="003d5-305">**Mittenti**</span><span class="sxs-lookup"><span data-stu-id="003d5-305">**Senders**</span></span>

  - <span data-ttu-id="003d5-306">**Sender**: questo è l'indirizzo effettivo del mittente nel comando SMTP mail from, che non è necessariamente l'indirizzo di posta elettronica da: che gli utenti visualizzano nei client di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="003d5-306">**Sender**: This is the actual sender address in the SMTP MAIL FROM command, which is not necessarily the From: email address that users see in their email clients.</span></span>
  - <span data-ttu-id="003d5-307">**Conteggio totale**</span><span class="sxs-lookup"><span data-stu-id="003d5-307">**Total count**</span></span>
  - <span data-ttu-id="003d5-308">**Posta in arrivo**</span><span class="sxs-lookup"><span data-stu-id="003d5-308">**Inboxed**</span></span>
  - <span data-ttu-id="003d5-309">**Non ricevuti**</span><span class="sxs-lookup"><span data-stu-id="003d5-309">**Not Inboxed**</span></span>
  - <span data-ttu-id="003d5-310">**DKIM superato**: il mittente è stato autenticato da [Key Domain identificated mail (DKIM)](support-for-validation-of-dkim-signed-messages.md).</span><span class="sxs-lookup"><span data-stu-id="003d5-310">**DKIM passed**: The sender was authenticated by [Domain Keys Identified Mail (DKIM)](support-for-validation-of-dkim-signed-messages.md).</span></span> <span data-ttu-id="003d5-311">Un mittente che non supera la convalida di DKIM indica che il mittente non è autenticato o che il messaggio è spoofing di un mittente legittimo.</span><span class="sxs-lookup"><span data-stu-id="003d5-311">A sender that does not pass DKIM validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>
  - <span data-ttu-id="003d5-312">**DMARC superato**: il mittente è stato autenticato da [autenticazione dei messaggi basata sul dominio, Reporting e conformità (DMARC)](use-dmarc-to-validate-email.md).</span><span class="sxs-lookup"><span data-stu-id="003d5-312">**DMARC passed**: The sender was authenticated by [Domain-based Message Authentication, Reporting, and Conformance (DMARC)](use-dmarc-to-validate-email.md).</span></span> <span data-ttu-id="003d5-313">Un mittente che non supera la convalida di DMARC indica che il mittente non è autenticato o che il messaggio è spoofing di un mittente legittimo.</span><span class="sxs-lookup"><span data-stu-id="003d5-313">A sender that does not pass DMARC validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="003d5-314">**Allegati**</span><span class="sxs-lookup"><span data-stu-id="003d5-314">**Attachments**</span></span>

  - <span data-ttu-id="003d5-315">**Filename**</span><span class="sxs-lookup"><span data-stu-id="003d5-315">**Filename**</span></span>
  - <span data-ttu-id="003d5-316">**SHA256**</span><span class="sxs-lookup"><span data-stu-id="003d5-316">**SHA256**</span></span>
  - <span data-ttu-id="003d5-317">**Famiglia di malware**</span><span class="sxs-lookup"><span data-stu-id="003d5-317">**Malware family**</span></span>
  - <span data-ttu-id="003d5-318">**Conteggio totale**</span><span class="sxs-lookup"><span data-stu-id="003d5-318">**Total count**</span></span>

- <span data-ttu-id="003d5-319">**URL**</span><span class="sxs-lookup"><span data-stu-id="003d5-319">**URL**</span></span>

  - <span data-ttu-id="003d5-320">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="003d5-320">**URL**<sup>\*</sup></span></span>
  - <span data-ttu-id="003d5-321">**Conteggio totale**</span><span class="sxs-lookup"><span data-stu-id="003d5-321">**Total Count**</span></span>

<span data-ttu-id="003d5-322"><sup>\*</sup> Se si fa clic su questo valore, viene aperto un nuovo riquadro a comparsa che contiene altri dettagli sulla voce specificata (utente, URL e così via) nella parte superiore della visualizzazione dei dettagli della campagna.</span><span class="sxs-lookup"><span data-stu-id="003d5-322"><sup>\*</sup> Clicking on this value opens a new flyout that contains more details about the specified item (user, URL, etc.) on top of the campaign details view.</span></span> <span data-ttu-id="003d5-323">Per tornare alla visualizzazione dei dettagli della campagna, fare clic su **Chiudi** nel nuovo riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="003d5-323">To return to the campaign details view, click **Done** in the new flyout.</span></span>

### <a name="buttons"></a><span data-ttu-id="003d5-324">Pulsanti</span><span class="sxs-lookup"><span data-stu-id="003d5-324">Buttons</span></span>

<span data-ttu-id="003d5-325">I pulsanti nella visualizzazione dei dettagli della campagna consentono di usare la potenza di Esplora minacce per approfondire la campagna.</span><span class="sxs-lookup"><span data-stu-id="003d5-325">The buttons in the campaign details view allow you to use the power of Threat Explorer to further investigate the campaign.</span></span>

- <span data-ttu-id="003d5-326">**Esplora minacce**: apre una nuova scheda di ricerca in Esplora minacce usando il valore **ID campagna** come filtro di ricerca.</span><span class="sxs-lookup"><span data-stu-id="003d5-326">**Explore campaign**: Opens a new Threat Explorer search tab using the **Campaign ID** value as the search filter.</span></span>

- <span data-ttu-id="003d5-327">**Esplorare i messaggi in arrivo**: apre una nuova scheda di ricerca di Esplora minacce utilizzando l' **ID della campagna** e il **percorso di recapito: posta in arrivo** come filtro di ricerca.</span><span class="sxs-lookup"><span data-stu-id="003d5-327">**Explore Inboxed messages**: Opens a new Threat Explorer search tab using the **Campaign ID** and **Delivery location: Inbox** as the search filter.</span></span>
