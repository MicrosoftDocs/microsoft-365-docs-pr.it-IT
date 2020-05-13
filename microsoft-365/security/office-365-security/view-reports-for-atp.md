---
title: Visualizzare i report per Advanced Threat Protection
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection:
- M365-security-compliance
description: Trovare e utilizzare i report per Office 365 Advanced Threat Protection nel centro sicurezza e &amp; conformità.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: af5844cf05d14e34059a26291d2034187439ec56
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208490"
---
# <a name="view-reports-for-office-365-advanced-threat-protection"></a><span data-ttu-id="5d4d6-103">Visualizzare i report per Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="5d4d6-103">View reports for Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="5d4d6-104">Se l'organizzazione dispone di [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) ed è necessario disporre delle [autorizzazioni necessarie](#what-permissions-are-needed-to-view-the-atp-reports), è possibile utilizzare diversi rapporti ATP nel &amp; Centro sicurezza e conformità.</span><span class="sxs-lookup"><span data-stu-id="5d4d6-104">If your organization has [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) and you have the [necessary permissions](#what-permissions-are-needed-to-view-the-atp-reports), you can use several ATP reports in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="5d4d6-105">(Andare a **report** \> **Dashboard**.</span><span class="sxs-lookup"><span data-stu-id="5d4d6-105">(Go to **Reports** \> **Dashboard**.)</span></span>

![Il dashboard del Centro sicurezza e conformità consente di individuare la modalità di &amp; funzionamento di Advanced Threat Protection](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

<span data-ttu-id="5d4d6-107">I report ATP includono quanto segue:</span><span class="sxs-lookup"><span data-stu-id="5d4d6-107">ATP reports include the following:</span></span>

- [<span data-ttu-id="5d4d6-108">Report dello stato di protezione dalle minacce</span><span class="sxs-lookup"><span data-stu-id="5d4d6-108">Threat Protection Status report</span></span>](#threat-protection-status-report)
- [<span data-ttu-id="5d4d6-109">Report dei tipi di file di ATP</span><span class="sxs-lookup"><span data-stu-id="5d4d6-109">ATP File Types report</span></span>](#atp-file-types-report)
- [<span data-ttu-id="5d4d6-110">Report della gestione dei messaggi di ATP</span><span class="sxs-lookup"><span data-stu-id="5d4d6-110">ATP Message Disposition report</span></span>](#atp-message-disposition-report)
- <span data-ttu-id="5d4d6-111">[rilevamenti o esploratori in tempo reale](threat-explorer.md) (a seconda che si disponga di Office 365 ATP piano 1 o 2)</span><span class="sxs-lookup"><span data-stu-id="5d4d6-111">either [real-time detections or Explorer](threat-explorer.md) (depending on whether you have Office 365 ATP Plan 1 or 2)</span></span>
- <span data-ttu-id="5d4d6-112">... [e altro ancora](#additional-reports-to-view).</span><span class="sxs-lookup"><span data-stu-id="5d4d6-112">... [and more](#additional-reports-to-view).</span></span>

<span data-ttu-id="5d4d6-113">Leggere questo articolo per ottenere una panoramica dei rapporti ATP e su come usarli.</span><span class="sxs-lookup"><span data-stu-id="5d4d6-113">Read this article to get an overview of ATP reports and how to use them.</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="5d4d6-114">Report dello stato di protezione dalle minacce</span><span class="sxs-lookup"><span data-stu-id="5d4d6-114">Threat Protection Status report</span></span>

<span data-ttu-id="5d4d6-115">Il rapporto **sullo stato della protezione dalle minacce** è una singola visualizzazione che raggruppa informazioni su contenuto dannoso e messaggi di posta elettronica dannosi rilevati e bloccati da [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) e [Office 365 ATP](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="5d4d6-115">The **Threat Protection Status** report is a single view that brings together information about malicious content and malicious email detected and blocked by [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) and [Office 365 ATP](office-365-atp.md).</span></span> <span data-ttu-id="5d4d6-116">Questo report è utile per la visualizzazione di rilevamenti nel tempo (fino a 90 giorni) e consente agli amministratori della sicurezza di identificare le tendenze o determinare se i criteri devono essere adattati.</span><span class="sxs-lookup"><span data-stu-id="5d4d6-116">This report is useful for viewing detections over time (up to 90 days), and it enables security administrators to identify trends or determine whether policies need adjustments.</span></span>

<span data-ttu-id="5d4d6-117">Il rapporto fornisce un numero aggregato di messaggi di posta elettronica univoci con contenuti dannosi, ad esempio i file o gli indirizzi del sito Web (URL) bloccati dal motore antimalware, da [zero-hour auto Purge (ZAP)](zero-hour-auto-purge.md)e dalle caratteristiche ATP come i [collegamenti sicuri](atp-safe-links.md)di ATP, gli [allegati sicuri di ATP](atp-safe-attachments.md)e il servizio [antiphishing ATP](set-up-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="5d4d6-117">The report provides an aggregated count of unique email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and ATP features like [ATP Safe Links](atp-safe-links.md), [ATP Safe Attachments](atp-safe-attachments.md), and [ATP anti-phishing](set-up-anti-phishing-policies.md).</span></span>

<span data-ttu-id="5d4d6-118">I filtri e i guasti delle informazioni consentono la categorizzazione più granulare delle informazioni contenute nel rapporto.</span><span class="sxs-lookup"><span data-stu-id="5d4d6-118">Filters and breakdowns of the information allow for more granular categorizations of the information in this report.</span></span> <span data-ttu-id="5d4d6-119">In particolare, è presente un menu ' Break Down by ' incluso per la **posta elettronica** \> **phishing** e le visualizzazioni malware per la **posta elettronica** \> **Malware views**.</span><span class="sxs-lookup"><span data-stu-id="5d4d6-119">Specifically, there is a 'break down by' menu included for **Email** \> **Phish** and **Email** \> **Malware views**.</span></span> <span data-ttu-id="5d4d6-120">I dati verranno suddivisi in:</span><span class="sxs-lookup"><span data-stu-id="5d4d6-120">It will break down the data into:</span></span>

|||
|---|---|
|<span data-ttu-id="5d4d6-121">In base al tipo di rilevamento</span><span class="sxs-lookup"><span data-stu-id="5d4d6-121">By detection type</span></span>|<span data-ttu-id="5d4d6-122">Quali criteri hanno consentito di intercettare tali minacce?</span><span class="sxs-lookup"><span data-stu-id="5d4d6-122">What policy helped catch these threats?</span></span>|
|<span data-ttu-id="5d4d6-123">Tramite la tecnologia di rilevamento</span><span class="sxs-lookup"><span data-stu-id="5d4d6-123">By detection technology</span></span>|<span data-ttu-id="5d4d6-124">La tecnologia Microsoft sottostante ha rilevato la minaccia?</span><span class="sxs-lookup"><span data-stu-id="5d4d6-124">What underlying Microsoft technology caught the threat?</span></span>|
|<span data-ttu-id="5d4d6-125">In base allo stato di recapito</span><span class="sxs-lookup"><span data-stu-id="5d4d6-125">By delivery status</span></span>|<span data-ttu-id="5d4d6-126">Che cosa è successo ai messaggi di posta elettronica rilevati come minacce?</span><span class="sxs-lookup"><span data-stu-id="5d4d6-126">What happened to the email messages detected as threats?</span></span>|
|

> [!TIP]
> <span data-ttu-id="5d4d6-127">Sia la > di posta elettronica phishing | Le visualizzazioni di malware presentano guasti granulari per le tecnologie di rilevamento mostrate, con categorie come la *reputazione dei file generati da ATP*, la *detonazione dei file*, la *detonazione degli URL*, l' *anti-spoofing: errore DMARC*, ad esempio, utili per individuare esattamente quale caratteristica ha portato la propria organizzazione a rilevare le minacce.</span><span class="sxs-lookup"><span data-stu-id="5d4d6-127">Both the Email > Phish | Malware views have granular breakdowns for the detection technologies shown, with categories like *ATP-generated file reputation*, *File detonation*, *URL detonation*, *Anti-spoof: DMARC failure*, for example, helpful in pinpointing exactly which feature led your organization to catch threats.</span></span>

![Elenco a discesa rapporto sullo stato di protezione dalle minacce che mostra ' scomposizione per '.](../../media/tp-threatProtectStatRpt-BreakDownBy.png)

<span data-ttu-id="5d4d6-129">Queste visualizzazioni offrono l'opzione per l'esportazione, tramite un clic sul pulsante (in phishing di **posta elettronica** \> **Phish**, malware per **posta** elettronica \> **Malware**e visualizzazioni **Content** \> **malware** contenuto).</span><span class="sxs-lookup"><span data-stu-id="5d4d6-129">These views give you the option to export, via a button click (in **Email** \> **Phish**, **Email** \> **Malware**, and **Content** \> **Malware** views).</span></span> <span data-ttu-id="5d4d6-130">I dati aggregati esportati nel computer possono essere aperti in Excel.</span><span class="sxs-lookup"><span data-stu-id="5d4d6-130">The aggregated data exported to your computer can be opened in Excel.</span></span>

![In questo elemento grafico viene illustrato come scegliere Esporta come opzione dal menu della visualizzazione malware, a destra tra la pianificazione e il rapporto di richiesta.](../../media/tp-threatProtectStatRpt-BreakDownByExport.png)

<span data-ttu-id="5d4d6-132">**Nota**: il numero massimo di voci che possono essere esportate per **phishing** e **malware** è inferiore a 10000.</span><span class="sxs-lookup"><span data-stu-id="5d4d6-132">**Note**: The maximum number of entries that can be exported for **Phish** and **Malware** is just under 10000.</span></span> <span data-ttu-id="5d4d6-133">Se si esporta una visualizzazione, vengono esportate solo le voci 10000 più recenti.</span><span class="sxs-lookup"><span data-stu-id="5d4d6-133">If you export a view, only the most recent 10000 entries are exported.</span></span>

<span data-ttu-id="5d4d6-134">Le visualizzazioni panoramica e messaggi di posta elettronica visualizzano le informazioni entro le ore successive all'elaborazione anziché entro 24 ore (demand re.</span><span class="sxs-lookup"><span data-stu-id="5d4d6-134">The Overview and Emails views will display information within hours of processing rather than in 24 hours (demand re.</span></span> <span data-ttu-id="5d4d6-135">velocità maggiore qui è stato un segnale chiaro)!</span><span class="sxs-lookup"><span data-stu-id="5d4d6-135">increased speeds here has been a clear signal)!</span></span>

> [!NOTE]
> <span data-ttu-id="5d4d6-136">Un rapporto sullo stato della protezione dalle minacce è disponibile per i clienti che dispongono di [Office 365 ATP](office-365-atp.md) o [Exchange Online Protection](exchange-online-protection-overview.md)(EOP); Tuttavia, le informazioni visualizzate nel rapporto sullo stato di protezione di minacce per i clienti ATP probabilmente conterranno dati diversi da quelli che potrebbero essere visualizzati dai clienti di EOP.</span><span class="sxs-lookup"><span data-stu-id="5d4d6-136">A Threat Protection Status report is available to customers who have either [Office 365 ATP](office-365-atp.md) or [Exchange Online Protection](exchange-online-protection-overview.md)) (EOP); however, the information that is displayed in the Threat Protection Status report for ATP customers will likely contain different data than what EOP customers might see.</span></span> <span data-ttu-id="5d4d6-137">Ad esempio, il rapporto sullo stato della protezione dalle minacce per i clienti ATP conterrà informazioni sui [file dannosi rilevati in SharePoint Online, OneDrive o Microsoft teams](atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="5d4d6-137">For example, the Threat Protection Status report for ATP customers will contain information about [malicious files detected in SharePoint Online, OneDrive, or Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span> <span data-ttu-id="5d4d6-138">Tali informazioni sono specifiche di ATP, quindi i clienti che hanno EOP ma non ATP non vedranno tali dettagli nella loro relazione sullo stato di protezione dalle minacce.</span><span class="sxs-lookup"><span data-stu-id="5d4d6-138">Such information is specific to ATP, so customers who have EOP but not ATP will not see those details in their Threat Protection Status report.</span></span>

<span data-ttu-id="5d4d6-139">Per visualizzare il rapporto sullo stato di protezione dalle minacce, nel [ &amp; Centro sicurezza e conformità](https://protection.office.com), accedere a **segnala** \> **Dashboard** \> **lo stato di protezione delle minacce**del dashboard.</span><span class="sxs-lookup"><span data-stu-id="5d4d6-139">To view the Threat Protection Status report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Threat Protection Status**.</span></span>

![Rapporto sullo stato di protezione ATP con minacce](../../media/6bdd41eb-62e0-423b-9fd4-d1d5baf0cbd5.png)

<span data-ttu-id="5d4d6-141">Per ottenere lo stato dettagliato per un giorno, posizionare il puntatore del mouse sul grafico.</span><span class="sxs-lookup"><span data-stu-id="5d4d6-141">To get detailed status for a day, hover over the graph.</span></span>

![Dati sullo stato della protezione da ATP per un giorno](../../media/d5c2c6ad-c002-4985-a032-c866e46fdea8.png)

<span data-ttu-id="5d4d6-143">Per impostazione predefinita, il rapporto sullo stato della protezione dalle minacce Visualizza i dati negli ultimi sette giorni.</span><span class="sxs-lookup"><span data-stu-id="5d4d6-143">By default, the Threat Protection Status report shows data for the past seven days.</span></span> <span data-ttu-id="5d4d6-144">Tuttavia, è possibile scegliere **filtri** e modificare l'intervallo di date per visualizzare i dati fino a 90 giorni.</span><span class="sxs-lookup"><span data-stu-id="5d4d6-144">However, you can choose **Filters** and change the date range to view data for up to 90 days.</span></span> <span data-ttu-id="5d4d6-145">Se si utilizza un abbonamento di valutazione, potrebbe essere limitato a 30 giorni di dati.</span><span class="sxs-lookup"><span data-stu-id="5d4d6-145">(If you are using a trial subscription, you might be limited to 30 days' of data.)</span></span>

![Filtri di stato di protezione da minacce ATP](../../media/4f703369-642b-402b-9758-b9c828283410.png)

<span data-ttu-id="5d4d6-147">È inoltre possibile utilizzare il menu **Visualizza dati in base** a per modificare le informazioni visualizzate nel report.</span><span class="sxs-lookup"><span data-stu-id="5d4d6-147">You can also use the **View data by** menu to change what information is displayed in the report.</span></span>

![Opzioni di visualizzazione per il rapporto sullo stato della protezione da ATP](../../media/4959bf8c-d192-4542-b00b-184e101e7513.png)

## <a name="url-protection-status-report"></a><span data-ttu-id="5d4d6-149">Rapporto sullo stato di protezione URL</span><span class="sxs-lookup"><span data-stu-id="5d4d6-149">URL Protection Status report</span></span>

<span data-ttu-id="5d4d6-150">Questo rapporto è basato sui dati raccolti e sui rischi rilevati, per clic (mentre la maggior parte dei rapporti correlati alla minaccia di posta elettronica sono per i dati del messaggio).</span><span class="sxs-lookup"><span data-stu-id="5d4d6-150">This report is based data collected, and threats detected, per click (whereas most other email threat related reports are per message data).</span></span> <span data-ttu-id="5d4d6-151">Questo report è stato creato per mostrare minacce provenienti da collegamenti ipertestuali nei messaggi di posta elettronica e nei documenti, per clic.</span><span class="sxs-lookup"><span data-stu-id="5d4d6-151">This report is designed to show threats that come from hyperlinks in email messages and documents, per click.</span></span> <span data-ttu-id="5d4d6-152">Sono disponibili due visualizzazioni:</span><span class="sxs-lookup"><span data-stu-id="5d4d6-152">There are two views:</span></span>

|||
|---|---|
|<span data-ttu-id="5d4d6-153">Azione di protezione dell'URL fare clic su</span><span class="sxs-lookup"><span data-stu-id="5d4d6-153">URL click protection action</span></span>|<span data-ttu-id="5d4d6-154">Vedere il numero di URL bloccati, bloccati ma ignorati con un clic da un utente, ignorati con un clic da un utente e consentiti.</span><span class="sxs-lookup"><span data-stu-id="5d4d6-154">See the number of URLs blocked, blocked but overridden with a click-through by a user, overridden with a click-through by a user, and allowed.</span></span>|
|<span data-ttu-id="5d4d6-155">URL fare clic su applicazione</span><span class="sxs-lookup"><span data-stu-id="5d4d6-155">URL click by application</span></span>|<span data-ttu-id="5d4d6-156">Vedere l'applicazione da cui è stato fatto clic sull'URL.</span><span class="sxs-lookup"><span data-stu-id="5d4d6-156">See the application from which the URL was clicked.</span></span>|
|

<span data-ttu-id="5d4d6-157">Nella tabella Details, è possibile visualizzare ulteriori informazioni su informazioni sui tempi e sugli utenti di clic.</span><span class="sxs-lookup"><span data-stu-id="5d4d6-157">In the details table, you'll be able to see more information regarding click time and user information.</span></span> <span data-ttu-id="5d4d6-158">Infine, tenere presente che il rapporto sullo stato di protezione URL Mostra la caratteristica protezione dalla funzionalità collegamenti sicuri ATP, quindi solo i clienti che hanno abilitato i collegamenti sicuri di ATP vedranno i dati riportati in questo report.</span><span class="sxs-lookup"><span data-stu-id="5d4d6-158">Finally, keep in mind the URL Protection Status report shows the protection from ATP Safe Links feature, so only customers who have enabled ATP Safe Links will see data reflected on this report.</span></span>

> [!NOTE]
> <span data-ttu-id="5d4d6-159">Si tratta di un *report di tendenza di protezione*, in cui i dati rappresentano le tendenze di un DataSet più grande.</span><span class="sxs-lookup"><span data-stu-id="5d4d6-159">This is a *protection trend report*, meaning data represents trends in a larger dataset.</span></span> <span data-ttu-id="5d4d6-160">Di conseguenza, i dati nella visualizzazione aggregata non sono disponibili in tempo reale qui, ma i dati nella visualizzazione tabella dettagli sono, pertanto è possibile che si verifichi una leggera discrepanza tra le due visualizzazioni.</span><span class="sxs-lookup"><span data-stu-id="5d4d6-160">As a result, the data in the aggregate view is not available in real time here, but the data in the details table view is, so you may see a slight discrepancy between the two views.</span></span>

## <a name="atp-file-types-report"></a><span data-ttu-id="5d4d6-161">Report dei tipi di file di ATP</span><span class="sxs-lookup"><span data-stu-id="5d4d6-161">ATP File Types report</span></span>

<span data-ttu-id="5d4d6-162">Il rapporto **tipi di file ATP** Visualizza il tipo di file rilevati come dannosi dagli [allegati sicuri di ATP](atp-safe-attachments.md).</span><span class="sxs-lookup"><span data-stu-id="5d4d6-162">The **ATP File Types** report shows you the type of files detected as malicious by [ATP Safe Attachments](atp-safe-attachments.md).</span></span>

<span data-ttu-id="5d4d6-163">Per visualizzare questo report, nel [Centro sicurezza e &amp; conformità](https://protection.office.com), accedere a **Reports** \> **Dashboard** \> **ATP types**.</span><span class="sxs-lookup"><span data-stu-id="5d4d6-163">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **ATP File Types**.</span></span>

![Report dei tipi di file di ATP](../../media/6e3f5d33-79aa-4b2d-938c-6ef135d9e54c.png)
  
<span data-ttu-id="5d4d6-165">Quando si posiziona il puntatore del mouse su un determinato giorno, è possibile visualizzare la ripartizione dei tipi di file dannosi rilevati dagli [allegati sicuri ATP](atp-safe-attachments.md) e dalla [ &amp; protezione anti-malware antispamming](anti-spam-and-anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="5d4d6-165">When you hover over a particular day, you can see the breakdown of types of malicious files that were detected by [ATP Safe Attachments](atp-safe-attachments.md) and [anti-spam &amp; anti-malware protection](anti-spam-and-anti-malware-protection.md).</span></span>
  
![I tipi di file ATP riportano i dati per un giorno](../../media/10d18428-699a-41d2-a73e-be3a8214ada1.png)

## <a name="atp-message-disposition-report"></a><span data-ttu-id="5d4d6-167">Report della gestione dei messaggi di ATP</span><span class="sxs-lookup"><span data-stu-id="5d4d6-167">ATP Message Disposition report</span></span>

<span data-ttu-id="5d4d6-168">Il rapporto di **disposizione dei messaggi ATP** indica le azioni eseguite per i messaggi di posta elettronica rilevati come contenuti dannosi.</span><span class="sxs-lookup"><span data-stu-id="5d4d6-168">The **ATP Message Disposition** report shows you the actions that were taken for email messages that were detected as having malicious content.</span></span>

<span data-ttu-id="5d4d6-169">Per visualizzare questo report, nel [Centro sicurezza e &amp; conformità](https://protection.office.com), accedere a disposizione dei messaggi per il dashboard dei **report** \> **Dashboard** \> **ATP**.</span><span class="sxs-lookup"><span data-stu-id="5d4d6-169">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **ATP Message Disposition**.</span></span>

![Rapporto di disposizione del messaggio ATP](../../media/b0ff65c4-53d3-496d-bafa-8937a5eb69e5.png)

<span data-ttu-id="5d4d6-171">Quando si posiziona il puntatore del mouse su una barra del grafico, è possibile vedere quali azioni sono state eseguite per il messaggio di posta elettronica rilevato per quel giorno.</span><span class="sxs-lookup"><span data-stu-id="5d4d6-171">When you hover over a bar in the chart, you can see what actions were taken for detected email for that day.</span></span>

![Dati del rapporto disposizione dei messaggi ATP per un giorno](../../media/68d2beb8-4b30-48c4-8ba6-5e8ab88ae456.png)

## <a name="additional-reports-to-view"></a><span data-ttu-id="5d4d6-173">Report aggiuntivi da visualizzare</span><span class="sxs-lookup"><span data-stu-id="5d4d6-173">Additional reports to view</span></span>

<span data-ttu-id="5d4d6-174">Oltre ai report ATP descritti in questo articolo, sono disponibili diversi altri report, come descritto nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="5d4d6-174">In addition to the ATP reports described in this article, several other reports are available, as described in the following table:</span></span>

|||
|---|---|
|<span data-ttu-id="5d4d6-175">**Report (s)**</span><span class="sxs-lookup"><span data-stu-id="5d4d6-175">**Report(s)**</span></span>|<span data-ttu-id="5d4d6-176">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="5d4d6-176">**Details**</span></span>|
|<span data-ttu-id="5d4d6-177">**Esploratori** o **rilevamenti in tempo reale**: (i clienti di Office 365 trifosfato di adenosina piano 2 hanno Esplora risorse; I clienti di Office 365 ATP Plan 1 dispongono di rilevamenti in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="5d4d6-177">**Explorer** or **real-time detections**: (Office 365 ATP Plan 2 customers have Explorer; Office 365 ATP Plan 1 customers have real-time detections.)</span></span>|[<span data-ttu-id="5d4d6-178">Esplora minacce (e rilevamenti in tempo reale)</span><span class="sxs-lookup"><span data-stu-id="5d4d6-178">Threat Explorer (and real-time detections)</span></span>](threat-explorer.md)|
|<span data-ttu-id="5d4d6-179">Report di **protezione della posta elettronica**, ad esempio un report mittenti e destinatari principali, un report di posta indesiderata e un report di rilevamenti di spam.</span><span class="sxs-lookup"><span data-stu-id="5d4d6-179">**Email security reports**, such as a Top Senders and Recipients report, a Spoof Mail report, and a Spam Detections report.</span></span>|[<span data-ttu-id="5d4d6-180">Visualizzare i report sulla sicurezza della posta elettronica nel centro sicurezza e &amp; conformità</span><span class="sxs-lookup"><span data-stu-id="5d4d6-180">View email security reports in the Security &amp; Compliance Center</span></span>](view-email-security-reports.md)|
|<span data-ttu-id="5d4d6-181">**Traccia URL collegamenti sicuri ATP**: (si tratta di un report generato tramite PowerShell). Questo rapporto illustra i risultati delle azioni di collegamenti sicuri ATP negli ultimi sette (7) giorni.</span><span class="sxs-lookup"><span data-stu-id="5d4d6-181">**ATP Safe Links URL trace**: (This is a report you generate by using PowerShell.) This report shows the results of ATP Safe Links actions over the past seven (7) days.</span></span>|[<span data-ttu-id="5d4d6-182">Informazioni di riferimento sui cmdlet Get-UrlTrace</span><span class="sxs-lookup"><span data-stu-id="5d4d6-182">Get-UrlTrace cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-urltrace)|
|<span data-ttu-id="5d4d6-183">**Risultati di EOP e ATP**: (questo è un report personalizzato che viene generato tramite PowerShell).</span><span class="sxs-lookup"><span data-stu-id="5d4d6-183">**EOP and ATP results**: (This is a custom report you generate by using PowerShell).</span></span> <span data-ttu-id="5d4d6-184">Questo report contiene informazioni, ad esempio dominio, data, tipo di evento, direzione, azione e numero di messaggi.</span><span class="sxs-lookup"><span data-stu-id="5d4d6-184">This report contains information, such as Domain, Date, Event Type, Direction, Action, and Message Count.</span></span>|[<span data-ttu-id="5d4d6-185">Informazioni di riferimento sui cmdlet Get-MailTrafficATPReport</span><span class="sxs-lookup"><span data-stu-id="5d4d6-185">Get-MailTrafficATPReport cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-mailtrafficatpreport)|
|<span data-ttu-id="5d4d6-186">**Rilevamenti di EOP e ATP**: (questo è un report personalizzato che viene generato tramite PowerShell).</span><span class="sxs-lookup"><span data-stu-id="5d4d6-186">**EOP and ATP detections**: (This is a custom report you generate by using PowerShell).</span></span> <span data-ttu-id="5d4d6-187">Questo report contiene informazioni dettagliate su file o URL dannosi, tentativi di phishing, rappresentazione e altre potenziali minacce nei messaggi di posta elettronica o nei file.</span><span class="sxs-lookup"><span data-stu-id="5d4d6-187">This report contains details about malicious files or URLs, phishing attempts, impersonation, and other potential threats in email or files.</span></span>|[<span data-ttu-id="5d4d6-188">Informazioni di riferimento sui cmdlet Get-MailDetailATPReport</span><span class="sxs-lookup"><span data-stu-id="5d4d6-188">Get-MailDetailATPReport cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-maildetailatpreport)|
|

## <a name="what-permissions-are-needed-to-view-the-atp-reports"></a><span data-ttu-id="5d4d6-189">Quali autorizzazioni sono necessarie per visualizzare i report ATP?</span><span class="sxs-lookup"><span data-stu-id="5d4d6-189">What permissions are needed to view the ATP reports?</span></span>

<span data-ttu-id="5d4d6-190">Per visualizzare e utilizzare i rapporti descritti in questo articolo, **è necessario disporre di un ruolo appropriato assegnato per il &amp; Centro sicurezza e l'interfaccia di amministrazione di Exchange**.</span><span class="sxs-lookup"><span data-stu-id="5d4d6-190">In order to view and use the reports described in this article, **you must have an appropriate role assigned for both the Security &amp; Compliance Center and the Exchange admin center**.</span></span>

- <span data-ttu-id="5d4d6-191">Per il &amp; Centro sicurezza e conformità, è necessario che sia assegnato uno dei ruoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="5d4d6-191">For the Security &amp; Compliance Center, you must have one of the following roles assigned:</span></span>

  - <span data-ttu-id="5d4d6-192">Gestione organizzazione</span><span class="sxs-lookup"><span data-stu-id="5d4d6-192">Organization Management</span></span>
  - <span data-ttu-id="5d4d6-193">Amministratore della sicurezza (è possibile assegnarlo nell'interfaccia di amministrazione di Azure Active Directory ( [https://aad.portal.azure.com](https://aad.portal.azure.com) ))</span><span class="sxs-lookup"><span data-stu-id="5d4d6-193">Security Administrator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
  - <span data-ttu-id="5d4d6-194">Operatore di sicurezza (che può essere assegnato nell'interfaccia di amministrazione di Azure Active Directory ( [https://aad.portal.azure.com](https://aad.portal.azure.com) ))</span><span class="sxs-lookup"><span data-stu-id="5d4d6-194">Security Operator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
  - <span data-ttu-id="5d4d6-195">Ruolo con autorizzazioni di lettura per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="5d4d6-195">Security Reader</span></span>

- <span data-ttu-id="5d4d6-196">Per Exchange Online, è necessario che sia assegnato uno dei ruoli seguenti nell'interfaccia di amministrazione di Exchange ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) ) o con i cmdlet di PowerShell (vedere [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)):</span><span class="sxs-lookup"><span data-stu-id="5d4d6-196">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) or with PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)):</span></span>

  - <span data-ttu-id="5d4d6-197">Gestione organizzazione</span><span class="sxs-lookup"><span data-stu-id="5d4d6-197">Organization Management</span></span>
  - <span data-ttu-id="5d4d6-198">Gestione organizzazione in sola visualizzazione</span><span class="sxs-lookup"><span data-stu-id="5d4d6-198">View-only Organization Management</span></span>
  - <span data-ttu-id="5d4d6-199">Ruolo Destinatari di sola lettura</span><span class="sxs-lookup"><span data-stu-id="5d4d6-199">View-Only Recipients role</span></span>
  - <span data-ttu-id="5d4d6-200">Gestione della conformità</span><span class="sxs-lookup"><span data-stu-id="5d4d6-200">Compliance Management</span></span>

<span data-ttu-id="5d4d6-201">Per altre informazioni, vedere le risorse seguenti:</span><span class="sxs-lookup"><span data-stu-id="5d4d6-201">To learn more, see the following resources:</span></span>

- [<span data-ttu-id="5d4d6-202">Autorizzazioni nel centro sicurezza e &amp; conformità</span><span class="sxs-lookup"><span data-stu-id="5d4d6-202">Permissions in the Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)

- [<span data-ttu-id="5d4d6-203">Autorizzazioni funzionalità in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="5d4d6-203">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="5d4d6-204">Cosa succede se i rapporti non mostrano dati?</span><span class="sxs-lookup"><span data-stu-id="5d4d6-204">What if the reports aren't showing data?</span></span>

<span data-ttu-id="5d4d6-205">Se i dati non vengono visualizzati nei rapporti ATP, verificare che i criteri siano configurati correttamente.</span><span class="sxs-lookup"><span data-stu-id="5d4d6-205">If you are not seeing data in your ATP reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="5d4d6-206">L'organizzazione deve disporre di [criteri dei collegamenti sicuri ATP](set-up-atp-safe-links-policies.md) e di criteri per gli [allegati sicuri ATP](set-up-atp-safe-attachments-policies.md) definiti in modo che la protezione da ATP sia sul posto.</span><span class="sxs-lookup"><span data-stu-id="5d4d6-206">Your organization must have [ATP Safe Links policies](set-up-atp-safe-links-policies.md) and [ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) defined in order for ATP protection to be in place.</span></span> <span data-ttu-id="5d4d6-207">Vedere anche [protezione da posta indesiderata e anti-malware in Office 365](anti-spam-and-anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="5d4d6-207">Also see [Anti-spam and anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="5d4d6-208">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="5d4d6-208">Related topics</span></span>

[<span data-ttu-id="5d4d6-209">Report e informazioni dettagliate nel centro sicurezza e &amp; conformità</span><span class="sxs-lookup"><span data-stu-id="5d4d6-209">Reports and insights in the Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="5d4d6-210">Creare una pianificazione per un report nel centro sicurezza e &amp; conformità</span><span class="sxs-lookup"><span data-stu-id="5d4d6-210">Create a schedule for a report in the Security &amp; Compliance Center</span></span>](create-a-schedule-for-a-report.md)

[<span data-ttu-id="5d4d6-211">Configurare e scaricare un report personalizzato nel centro sicurezza e &amp; conformità</span><span class="sxs-lookup"><span data-stu-id="5d4d6-211">Set up and download a custom report in the Security &amp; Compliance Center</span></span>](set-up-and-download-a-custom-report.md)

[<span data-ttu-id="5d4d6-212">Autorizzazioni ruolo (Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="5d4d6-212">Role permissions (Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
