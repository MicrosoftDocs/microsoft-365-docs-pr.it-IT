---
title: Procedura dettagliata-spoofing Intelligence Insight
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 59a3ecaf-15ed-483b-b824-d98961d88bdd
ms.collection:
- M365-security-compliance
description: Gli amministratori possono sapere come funziona l'Insight di intelligence di spoofing. Possono determinare rapidamente quali mittenti stanno inviando messaggi di posta elettronica nelle loro organizzazioni da domini che non superano i controlli di autenticazione della posta elettronica (SPF, DKIM o DMARC).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6f5ebd0fd42d17354eeb1e03c946ac5446c3667c
ms.sourcegitcommit: d81c7cea85af6ad5fef81d3c930514a51464368c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/04/2020
ms.locfileid: "49572742"
---
# <a name="walkthrough---spoof-intelligence-insight-in-microsoft-defender-for-office-365"></a><span data-ttu-id="4dd74-104">Procedura dettagliata-spoofing Intelligence Insight in Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="4dd74-104">Walkthrough - Spoof intelligence insight in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="4dd74-105">In Microsoft 365 organizzazioni con difensore per Office 365, è possibile utilizzare la funzionalità di Insight Intelligence per determinare rapidamente quali mittenti stanno inviando legalmente la posta elettronica non autenticata (messaggi provenienti da domini che non superano i controlli SPF, DKIM o DMARC).</span><span class="sxs-lookup"><span data-stu-id="4dd74-105">In Microsoft 365 organizations with Defender for Office 365, you can use the Spoof intelligence insight to quickly determine which senders are legitimately sending you unauthenticated email (messages from domains that don't pass SPF, DKIM, or DMARC checks).</span></span>

<span data-ttu-id="4dd74-106">Consentendo ai mittenti noti di inviare messaggi falsificati da posizioni note, è possibile ridurre i falsi positivi (un buon messaggio di posta elettronica contrassegnato come cattivo).</span><span class="sxs-lookup"><span data-stu-id="4dd74-106">By allowing known senders to send spoofed messages from known locations, you can reduce false positives (good email marked as bad).</span></span> <span data-ttu-id="4dd74-107">Monitorando i mittenti autorizzati falsificati, è possibile fornire un ulteriore livello di sicurezza per impedire l'arrivo di messaggi non sicuri nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4dd74-107">By monitoring the allowed spoofed senders, you provide an additional layer of security to prevent unsafe messages from arriving in your organization.</span></span>

<span data-ttu-id="4dd74-108">Per ulteriori informazioni sui report e sulle intuizioni, vedere [Reports and Insights in the Security & Compliance Center](reports-and-insights-in-security-and-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="4dd74-108">For more information about reports and insights, see [Reports and insights in the Security & Compliance Center](reports-and-insights-in-security-and-compliance.md).</span></span>

<span data-ttu-id="4dd74-109">Questa procedura dettagliata è una delle numerose per il Centro sicurezza & Compliance.</span><span class="sxs-lookup"><span data-stu-id="4dd74-109">This walkthrough is one of several for the Security & Compliance Center.</span></span> <span data-ttu-id="4dd74-110">Per informazioni sull'esplorazione di report e approfondimenti, vedere le procedure dettagliate nella sezione [argomenti correlati](#related-topics) .</span><span class="sxs-lookup"><span data-stu-id="4dd74-110">To about navigating reports and insights, see the walkthroughs in the [Related topics](#related-topics) section.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="4dd74-111">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="4dd74-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="4dd74-112">Aprire il Centro sicurezza e conformità in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="4dd74-112">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="4dd74-113">Per accedere direttamente alla pagina del **dashboard di sicurezza** , utilizzare <https://protection.office.com/searchandinvestigation/dashboard> .</span><span class="sxs-lookup"><span data-stu-id="4dd74-113">To go directly to the **Security dashboard** page, use <https://protection.office.com/searchandinvestigation/dashboard>.</span></span>

  <span data-ttu-id="4dd74-114">È possibile visualizzare l'Insight di intelligence di spoofing da più di un dashboard nel centro sicurezza & Compliance.</span><span class="sxs-lookup"><span data-stu-id="4dd74-114">You can view the Spoof intelligence insight from more than one dashboard in the Security & Compliance Center.</span></span> <span data-ttu-id="4dd74-115">Indipendentemente dal dashboard che si sta esaminando, l'Insight fornisce gli stessi dettagli e consente di eseguire rapidamente le stesse attività.</span><span class="sxs-lookup"><span data-stu-id="4dd74-115">Regardless of which dashboard you're looking at, the insight provides the same details and allows you to quickly perform the same tasks.</span></span>

- <span data-ttu-id="4dd74-116">Prima di poter eseguire le procedure descritte in questo articolo, è necessario disporre delle autorizzazioni per il Centro sicurezza & Compliance:</span><span class="sxs-lookup"><span data-stu-id="4dd74-116">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="4dd74-117">**Gestione organizzazione**</span><span class="sxs-lookup"><span data-stu-id="4dd74-117">**Organization Management**</span></span>
  - <span data-ttu-id="4dd74-118">**Amministratore della sicurezza**</span><span class="sxs-lookup"><span data-stu-id="4dd74-118">**Security Administrator**</span></span>
  - <span data-ttu-id="4dd74-119">**Lettore di sicurezza**</span><span class="sxs-lookup"><span data-stu-id="4dd74-119">**Security Reader**</span></span>
  - <span data-ttu-id="4dd74-120">**Ruolo con autorizzazioni di lettura globali**</span><span class="sxs-lookup"><span data-stu-id="4dd74-120">**Global Reader**</span></span>

  <span data-ttu-id="4dd74-121">**Nota**: l'aggiunta di utenti al ruolo di Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft 365 fornisce agli utenti le autorizzazioni necessarie nel centro sicurezza & Compliance _e_ le autorizzazioni per altre caratteristiche in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4dd74-121">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="4dd74-122">Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="4dd74-122">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>

- <span data-ttu-id="4dd74-123">È possibile abilitare e disabilitare l'intelligence spoof nei criteri di anti-phishing in Microsoft Defender per Office 365.</span><span class="sxs-lookup"><span data-stu-id="4dd74-123">You enable and disable spoof intelligence in anti-phishing policies in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="4dd74-124">Per ulteriori informazioni, vedere [Configure anti-phishing Policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="4dd74-124">For more information, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

- <span data-ttu-id="4dd74-125">Per utilizzare l'intelligence spoof per monitorare e gestire i mittenti che inviano messaggi non autenticati, vedere [Configure Spoofing Intelligence in Microsoft 365](learn-about-spoof-intelligence.md).</span><span class="sxs-lookup"><span data-stu-id="4dd74-125">To use spoof intelligence to monitor and manage senders who are sending you unauthenticated messages, see [Configure spoof intelligence in Microsoft 365](learn-about-spoof-intelligence.md).</span></span>

## <a name="open-the-spoof-intelligence-insight-in-the-security--compliance-center"></a><span data-ttu-id="4dd74-126">Aprire lo spoofing Intelligence Insight nel centro sicurezza & Compliance</span><span class="sxs-lookup"><span data-stu-id="4dd74-126">Open the spoof intelligence insight in the Security & Compliance Center</span></span>

1. <span data-ttu-id="4dd74-127">Nel centro sicurezza & conformità, accedere a **Threat Management** \> **Dashboard.**</span><span class="sxs-lookup"><span data-stu-id="4dd74-127">In the Security & Compliance Center, go to **Threat Management** \> **Dashboard.**</span></span>

2. <span data-ttu-id="4dd74-128">Nella riga **Insights** cercare uno degli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="4dd74-128">In the **Insights** row, look for one of the following items:</span></span>

   - <span data-ttu-id="4dd74-129">L' **intelligenza spoof è abilitata**: l'Insight è denominato **domini falsificati che non hanno eseguito l'autenticazione degli ultimi 30 giorni**.</span><span class="sxs-lookup"><span data-stu-id="4dd74-129">**Spoof intelligence is enabled**: The insight is named **Spoofed domains that failed authentication of the past 30 days**.</span></span> <span data-ttu-id="4dd74-130">non vengono intraprese azioni in modalità test sul messaggio.</span><span class="sxs-lookup"><span data-stu-id="4dd74-130">This is the default.</span></span>
   - <span data-ttu-id="4dd74-131">L' **intelligenza contraffatta è disattivata**: l'Insight nel nome **Abilita la protezione spoof** e facendo clic su di essa è possibile abilitare l'intelligence spoof.</span><span class="sxs-lookup"><span data-stu-id="4dd74-131">**Spoof intelligence is disabled**: The insight in named **Enable Spoof Protection**, and clicking on it allows you to enable spoof intelligence.</span></span>

3. <span data-ttu-id="4dd74-132">L'Insight sul dashboard Visualizza informazioni di questo tipo:</span><span class="sxs-lookup"><span data-stu-id="4dd74-132">The insight on the dashboard shows you information like this:</span></span>

   ![Schermata di Insight Intelligence spoofing](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   <span data-ttu-id="4dd74-134">Questa intuizione ha due modalità:</span><span class="sxs-lookup"><span data-stu-id="4dd74-134">This insight has two modes:</span></span>

   - <span data-ttu-id="4dd74-135">**Modalità Insight**: se l'intelligence spoof è abilitata, l'Insight Visualizza il numero di messaggi che sono stati influenzati dalle funzionalità di intelligence spoof negli ultimi 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="4dd74-135">**Insight mode**: If spoof intelligence is enabled, the insight shows you how many messages were impacted by our spoof intelligence capabilities over the past 30 days.</span></span>

   - <span data-ttu-id="4dd74-136">**Cosa succede se la modalità**: se l'intelligence di spoofing è disabilitata, l'Insight Visualizza il numero *di messaggi che* sono stati influenzati dalle funzionalità di intelligence spoof negli ultimi 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="4dd74-136">**What if mode**: If spoof intelligence is disabled, then the insight shows you how many messages *would* have been impacted by our spoof intelligence capabilities over the past 30 days.</span></span>

   <span data-ttu-id="4dd74-137">In entrambi i casi, i domini falsificati visualizzati nell'Insight sono separati in due categorie: **coppie di domini sospetti** e **coppie di domini non sospetti**.</span><span class="sxs-lookup"><span data-stu-id="4dd74-137">Either way, the spoofed domains displayed in the insight are separated into two categories: **Suspicious domain pairs** and **Non-suspicious domain pairs**.</span></span> <span data-ttu-id="4dd74-138">Queste categorie sono ulteriormente suddivise in tre diversi bucket che è possibile esaminare.</span><span class="sxs-lookup"><span data-stu-id="4dd74-138">These categories are further subdivided into three different buckets for you to review.</span></span>

   <span data-ttu-id="4dd74-139">Una **coppia di domini** è una combinazione dell'indirizzo mittente e dell'infrastruttura di invio:</span><span class="sxs-lookup"><span data-stu-id="4dd74-139">A **domain pair** is a combination of the From address and the sending infrastructure:</span></span>

   - <span data-ttu-id="4dd74-140">L'indirizzo da è l'indirizzo di posta elettronica del mittente visualizzato nella casella da nei client di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="4dd74-140">The From address is the sender's email address that's displayed in the From box in email clients.</span></span> <span data-ttu-id="4dd74-141">Questo indirizzo è noto anche come `5322.From` indirizzo.</span><span class="sxs-lookup"><span data-stu-id="4dd74-141">This address is also known as the `5322.From` address.</span></span>

   - <span data-ttu-id="4dd74-142">L'infrastruttura di invio, o mittente, è il dominio dell'organizzazione del servizio di ricerca DNS inverso (record PTR) dell'indirizzo IP di invio.</span><span class="sxs-lookup"><span data-stu-id="4dd74-142">The sending infrastructure, or sender, is the organizational domain of the reverse DNS lookup (PTR record) of the sending IP address.</span></span> <span data-ttu-id="4dd74-143">Se l'indirizzo IP di invio non ha un record PTR, il mittente viene identificato dall'IP di invio con la subnet mask 255.255.255.0 nella notazione CIDR (/24).</span><span class="sxs-lookup"><span data-stu-id="4dd74-143">If the sending IP address has no PTR record, then the sender is identified by the sending IP with the 255.255.255.0 subnet mask in CIDR notation (/24).</span></span> <span data-ttu-id="4dd74-144">Ad esempio, se l'indirizzo IP è 192.168.100.100, l'indirizzo IP completo del mittente è 192.168.100.100/24.</span><span class="sxs-lookup"><span data-stu-id="4dd74-144">For example, if the IP address is 192.168.100.100 then the complete IP address of the sender is 192.168.100.100/24.</span></span>

   <span data-ttu-id="4dd74-145">Le **coppie di domini sospetti** includono:</span><span class="sxs-lookup"><span data-stu-id="4dd74-145">**Suspicious domain pairs** include:</span></span>

   - <span data-ttu-id="4dd74-146">**Spoof ad alta confidenza**: sulla base dei modelli di invio storico e del Punteggio di reputazione dei domini, è estremamente sicuro che i domini siano spoofing e che i messaggi provenienti da questi domini abbiano maggiori probabilità di essere dannosi.</span><span class="sxs-lookup"><span data-stu-id="4dd74-146">**High-confidence spoof**: Based on the historical sending patterns and the reputation score of the domains, we're highly confident that the domains are spoofing, and messages from these domains are more likely to be malicious.</span></span>

   - <span data-ttu-id="4dd74-147">**Falsificazione della confidenza moderata**: in base ai modelli di invio cronologici e al Punteggio di reputazione dei domini, si è certi che i domini siano spoofing e che i messaggi inviati da questi domini siano legittimi.</span><span class="sxs-lookup"><span data-stu-id="4dd74-147">**Moderate confidence spoof**: Based on historical sending patterns and the reputation score of the domains, we're moderately confident that the domains are spoofing, and that messages sent from these domains are legitimate.</span></span> <span data-ttu-id="4dd74-148">I falsi positivi sono più probabili in questa categoria rispetto alla falsificazione con attendibilità elevata.</span><span class="sxs-lookup"><span data-stu-id="4dd74-148">False positives are more likely in this category than high-confidence spoof.</span></span>

   - <span data-ttu-id="4dd74-149">**Coppie di domini non sospetti** (include **Rescued spoof**): il dominio non è riuscito l'autenticazione esplicita della posta elettronica controlla [SPF](how-office-365-uses-spf-to-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md)e [DMARC](use-dmarc-to-validate-email.md)).</span><span class="sxs-lookup"><span data-stu-id="4dd74-149">**Non-suspicious domain pairs** (includes **rescued spoof**): The domain failed explicit email authentication checks [SPF](how-office-365-uses-spf-to-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md), and [DMARC](use-dmarc-to-validate-email.md)).</span></span> <span data-ttu-id="4dd74-150">Tuttavia, il dominio ha superato i controlli di autenticazione della posta elettronica impliciti ([autenticazione composita](email-validation-and-authentication.md#composite-authentication)).</span><span class="sxs-lookup"><span data-stu-id="4dd74-150">However, the domain passed our implicit email authentication checks ([composite authentication](email-validation-and-authentication.md#composite-authentication)).</span></span> <span data-ttu-id="4dd74-151">Di conseguenza, non è stata eseguita alcuna azione antispoofing sul messaggio.</span><span class="sxs-lookup"><span data-stu-id="4dd74-151">As a result, no anti-spoofing action was taken on the message.</span></span>

### <a name="view-detailed-information-about-suspicious-domain-pairs-from-the-spoof-intelligence-insight"></a><span data-ttu-id="4dd74-152">Visualizzare informazioni dettagliate sulle coppie di domini sospetti da spoofing Intelligence Insight</span><span class="sxs-lookup"><span data-stu-id="4dd74-152">View detailed information about suspicious domain pairs from the spoof intelligence insight</span></span>

1. <span data-ttu-id="4dd74-153">Nell'Insight Intelligence spoofing, fare clic su una qualsiasi delle coppie di domini (alto, moderato o salvato).</span><span class="sxs-lookup"><span data-stu-id="4dd74-153">On the Spoof intelligence insight, click any of the domain pairs (high, moderate, or rescued).</span></span>

   <span data-ttu-id="4dd74-154">Viene visualizzata la pagina di **Insight Intelligence spoof** .</span><span class="sxs-lookup"><span data-stu-id="4dd74-154">The **Spoof Intelligence insight** page appears.</span></span> <span data-ttu-id="4dd74-155">Nella pagina viene visualizzato un elenco di mittenti che inviano messaggi di posta elettronica non autenticati nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4dd74-155">The page shows you a list of senders who are sending unauthenticated email into your organization.</span></span>

   <span data-ttu-id="4dd74-156">Queste informazioni consentono di determinare se i messaggi falsificati sono autorizzati o se è necessario intraprendere ulteriori azioni.</span><span class="sxs-lookup"><span data-stu-id="4dd74-156">This information helps you determine whether spoofed messages are authorized, or if you need to take further action.</span></span>

   <span data-ttu-id="4dd74-157">È possibile ordinare le informazioni in base al numero di messaggi, alla data in cui è stata rilevata l'ultima volta la parodia e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="4dd74-157">You can sort the information by message count, the date the spoof was last detected, and more.</span></span>

2. <span data-ttu-id="4dd74-158">Selezionare un elemento nella tabella per aprire un riquadro dei dettagli che contiene informazioni complete sulla coppia di domini.</span><span class="sxs-lookup"><span data-stu-id="4dd74-158">Select an item in the table to open a details pane that contains rich information about the domain pair.</span></span> <span data-ttu-id="4dd74-159">Le informazioni includono:</span><span class="sxs-lookup"><span data-stu-id="4dd74-159">The information includes:</span></span>
   - <span data-ttu-id="4dd74-160">Perché questo è stato rilevato.</span><span class="sxs-lookup"><span data-stu-id="4dd74-160">Why we caught this.</span></span>
   - <span data-ttu-id="4dd74-161">Cosa devi fare.</span><span class="sxs-lookup"><span data-stu-id="4dd74-161">What you need to do.</span></span>
   - <span data-ttu-id="4dd74-162">Riepilogo di un dominio.</span><span class="sxs-lookup"><span data-stu-id="4dd74-162">A domain summary.</span></span>
   - <span data-ttu-id="4dd74-163">Dati WhoIs sul mittente.</span><span class="sxs-lookup"><span data-stu-id="4dd74-163">WhoIs data about the sender.</span></span>
   - <span data-ttu-id="4dd74-164">Messaggi simili che sono stati visualizzati nel tenant dallo stesso mittente.</span><span class="sxs-lookup"><span data-stu-id="4dd74-164">Similar messages we have seen in your tenant from the same sender.</span></span>

   <span data-ttu-id="4dd74-165">Da qui, è anche possibile scegliere di aggiungere o rimuovere la coppia di dominio dall'elenco dei mittenti attendibili di **AllowedToSpoof** .</span><span class="sxs-lookup"><span data-stu-id="4dd74-165">From here, you can also choose to add or remove the domain pair from the **AllowedToSpoof** safe sender list.</span></span>

   ![Schermata di un dominio nel riquadro dei dettagli dell'analisi di intelligence di spoofing](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

### <a name="add-or-remove-a-domain-from-the-allowedtospoof-list"></a><span data-ttu-id="4dd74-167">Aggiungere o rimuovere un dominio dall'elenco AllowedToSpoof</span><span class="sxs-lookup"><span data-stu-id="4dd74-167">Add or remove a domain from the AllowedToSpoof list</span></span>

<span data-ttu-id="4dd74-168">È possibile aggiungere o rimuovere un dominio dall'elenco AllowedToSpoof (Safe sender) nel riquadro dei dettagli dell'Insight di intelligence di spoofing per la coppia di dominio.</span><span class="sxs-lookup"><span data-stu-id="4dd74-168">You add or remove a domain from the AllowedToSpoof (safe sender) list in the details pane of the spoof intelligence insight for the domain pair.</span></span> <span data-ttu-id="4dd74-169">È sufficiente impostare l'interruttore di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="4dd74-169">Simply set the toggle accordingly.</span></span>

<span data-ttu-id="4dd74-170">La possibilità di una coppia di domini consente solo la combinazione del dominio contraffatto *e* dell'infrastruttura di invio.</span><span class="sxs-lookup"><span data-stu-id="4dd74-170">Allowing a domain pair only allows the combination of the spoofed domain *and* the sending infrastructure.</span></span> <span data-ttu-id="4dd74-171">Non consente la posta elettronica dal dominio contraffatto da qualsiasi origine, né consente la posta elettronica dall'infrastruttura di invio per qualsiasi dominio.</span><span class="sxs-lookup"><span data-stu-id="4dd74-171">It does not allow email from the spoofed domain from any source, nor does it allow email from the sending infrastructure for any domain.</span></span>

<span data-ttu-id="4dd74-172">Ad esempio, è possibile consentire alla coppia di domini seguente di inviare messaggi falsificati all'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="4dd74-172">For example, you allow the following domain pair to send spoofed messages into your organization:</span></span>

- <span data-ttu-id="4dd74-173">*Dominio contraffatto*: Gmail.com "</span><span class="sxs-lookup"><span data-stu-id="4dd74-173">*Spoofed Domain*: gmail.com"</span></span>
- <span data-ttu-id="4dd74-174">*Infrastruttura di invio* `tms.mx.com` :</span><span class="sxs-lookup"><span data-stu-id="4dd74-174">*Sending Infrastructure* `tms.mx.com`:</span></span>

<span data-ttu-id="4dd74-175">Solo il messaggio di posta elettronica da tale coppia di dominio sarà autorizzato allo spoofing.</span><span class="sxs-lookup"><span data-stu-id="4dd74-175">Only email from that domain pair will be allowed to spoof.</span></span> <span data-ttu-id="4dd74-176">Gli altri mittenti che tentano di falsificare gmail.com non sono consentiti.</span><span class="sxs-lookup"><span data-stu-id="4dd74-176">Other senders attempting to spoof gmail.com aren't allowed.</span></span> <span data-ttu-id="4dd74-177">I messaggi in altri domini di tms.mx.com vengono controllati da spoofing Intelligence.</span><span class="sxs-lookup"><span data-stu-id="4dd74-177">Messages in other domains from tms.mx.com are checked by spoof intelligence.</span></span>

## <a name="related-topics"></a><span data-ttu-id="4dd74-178">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="4dd74-178">Related topics</span></span>

[<span data-ttu-id="4dd74-179">Protezione anti-spoofing in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4dd74-179">Anti-spoofing protection in Microsoft 365</span></span>](anti-spoofing-protection.md)
