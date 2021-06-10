---
title: Visualizzazioni in Esplora minacce e rilevamenti in tempo reale
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 05/15/2020
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Informazioni su come usare Esplora minacce e il report sui rilevamenti in tempo reale per analizzare e rispondere alle minacce nel Centro sicurezza & conformità.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 78c03b45063f4bc34b47ab003bcf00d2befab886
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206422"
---
# <a name="views-in-threat-explorer-and-real-time-detections"></a><span data-ttu-id="dfcfa-103">Visualizzazioni in Esplora minacce e rilevamenti in tempo reale</span><span class="sxs-lookup"><span data-stu-id="dfcfa-103">Views in Threat Explorer and real-time detections</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="dfcfa-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="dfcfa-104">**Applies to**</span></span>
- [<span data-ttu-id="dfcfa-105">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="dfcfa-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="dfcfa-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="dfcfa-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)


![Esplora minacce](../../media/ThreatExplorerFirstOpened.png)

<span data-ttu-id="dfcfa-108">[Threat Explorer](threat-explorer.md) (e il report sui rilevamenti in tempo reale) è uno strumento potente e quasi in tempo reale per aiutare i team delle operazioni di sicurezza ad analizzare e rispondere alle minacce nel Centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="dfcfa-108">[Threat Explorer](threat-explorer.md) (and the real-time detections report) is a powerful, near real-time tool to help Security Operations teams investigate and respond to threats in the Security & Compliance Center.</span></span> <span data-ttu-id="dfcfa-109">Explorer (e il report sui rilevamenti in tempo reale) visualizza informazioni su malware e virus sospetti nella posta elettronica e nei file in Office 365, oltre ad altre minacce e rischi per la sicurezza per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="dfcfa-109">Explorer (and the real-time detections report) displays information about suspected malware and phish in email and files in Office 365, as well as other security threats and risks to your organization.</span></span>

- <span data-ttu-id="dfcfa-110">Se hai [Microsoft Defender per Office 365](defender-for-office-365.md) Piano 2, hai Explorer.</span><span class="sxs-lookup"><span data-stu-id="dfcfa-110">If you have [Microsoft Defender for Office 365](defender-for-office-365.md) Plan 2, then you have Explorer.</span></span>
- <span data-ttu-id="dfcfa-111">Se hai Microsoft Defender per Office 365 Piano 1, hai rilevamenti in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="dfcfa-111">If you have Microsoft Defender for Office 365 Plan 1, then you have real-time detections.</span></span>

<span data-ttu-id="dfcfa-112">Quando apri Explorer per la prima volta (o il report dei rilevamenti in tempo reale), la visualizzazione predefinita mostra i rilevamenti di malware tramite posta elettronica negli ultimi 7 giorni.</span><span class="sxs-lookup"><span data-stu-id="dfcfa-112">When you first open Explorer (or the real-time detections report), the default view shows email malware detections for the past 7 days.</span></span> <span data-ttu-id="dfcfa-113">Questo report può anche mostrare Microsoft Defender per Office 365, ad esempio URL dannosi rilevati da Collegamenti sicuri [e](safe-links.md)file dannosi rilevati da [Allegati sicuri.](safe-attachments.md)</span><span class="sxs-lookup"><span data-stu-id="dfcfa-113">This report can also show Microsoft Defender for Office 365 detections, such as malicious URLs detected by [Safe Links](safe-links.md), and malicious files detected by [Safe Attachments](safe-attachments.md).</span></span> <span data-ttu-id="dfcfa-114">Questo report può essere modificato per visualizzare i dati degli ultimi 30 giorni (con un abbonamento a pagamento di Microsoft Defender Office 365 P2).</span><span class="sxs-lookup"><span data-stu-id="dfcfa-114">This report can be modified to show data for the past 30 days (with a Microsoft Defender for Office 365 P2 paid subscription).</span></span> <span data-ttu-id="dfcfa-115">Le sottoscrizioni di valutazione includeranno solo i dati degli ultimi sette giorni.</span><span class="sxs-lookup"><span data-stu-id="dfcfa-115">Trial subscriptions will include data for the past seven days only.</span></span>

****

|<span data-ttu-id="dfcfa-116">Abbonamento</span><span class="sxs-lookup"><span data-stu-id="dfcfa-116">Subscription</span></span>|<span data-ttu-id="dfcfa-117">Utilità</span><span class="sxs-lookup"><span data-stu-id="dfcfa-117">Utility</span></span>|<span data-ttu-id="dfcfa-118">Giorni di dati</span><span class="sxs-lookup"><span data-stu-id="dfcfa-118">Days of Data</span></span>|
|---|---|---|
|<span data-ttu-id="dfcfa-119">Microsoft Defender per la Office 365 P1</span><span class="sxs-lookup"><span data-stu-id="dfcfa-119">Microsoft Defender for Office 365 P1 trial</span></span>|<span data-ttu-id="dfcfa-120">Rilevamenti in tempo reale</span><span class="sxs-lookup"><span data-stu-id="dfcfa-120">Real-time detections</span></span>|<span data-ttu-id="dfcfa-121">7 </span><span class="sxs-lookup"><span data-stu-id="dfcfa-121">7</span></span>|
|<span data-ttu-id="dfcfa-122">Microsoft Defender per Office 365 P1 a pagamento</span><span class="sxs-lookup"><span data-stu-id="dfcfa-122">Microsoft Defender for Office 365 P1 paid</span></span>|<span data-ttu-id="dfcfa-123">Rilevamenti in tempo reale</span><span class="sxs-lookup"><span data-stu-id="dfcfa-123">Real-time detections</span></span>|<span data-ttu-id="dfcfa-124">30</span><span class="sxs-lookup"><span data-stu-id="dfcfa-124">30</span></span>|
|<span data-ttu-id="dfcfa-125">Microsoft Defender for Office 365 P1 paid testing Defender for Office 365 P2 trial</span><span class="sxs-lookup"><span data-stu-id="dfcfa-125">Microsoft Defender for Office 365 P1 paid testing Defender for Office 365 P2 trial</span></span>|<span data-ttu-id="dfcfa-126">Esplora minacce</span><span class="sxs-lookup"><span data-stu-id="dfcfa-126">Threat Explorer</span></span>|<span data-ttu-id="dfcfa-127">7 </span><span class="sxs-lookup"><span data-stu-id="dfcfa-127">7</span></span>|
|<span data-ttu-id="dfcfa-128">Microsoft Defender for Office 365 P2 trial</span><span class="sxs-lookup"><span data-stu-id="dfcfa-128">Microsoft Defender for Office 365 P2 trial</span></span>|<span data-ttu-id="dfcfa-129">Esplora minacce</span><span class="sxs-lookup"><span data-stu-id="dfcfa-129">Threat Explorer</span></span>|<span data-ttu-id="dfcfa-130">7 </span><span class="sxs-lookup"><span data-stu-id="dfcfa-130">7</span></span>|
|<span data-ttu-id="dfcfa-131">Microsoft Defender per Office 365 P2 a pagamento</span><span class="sxs-lookup"><span data-stu-id="dfcfa-131">Microsoft Defender for Office 365 P2 paid</span></span>|<span data-ttu-id="dfcfa-132">Esplora minacce</span><span class="sxs-lookup"><span data-stu-id="dfcfa-132">Threat Explorer</span></span>|<span data-ttu-id="dfcfa-133">30</span><span class="sxs-lookup"><span data-stu-id="dfcfa-133">30</span></span>|
|

> [!NOTE]
> <span data-ttu-id="dfcfa-134">Presto estenderemo il limite di conservazione e ricerca dei dati di Explorer (e rilevamento in tempo reale) per i tenant di prova da 7 a 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="dfcfa-134">We will soon be extending the Explorer (and Real-time detections) data retention and search limit for trial tenants from 7 to 30 days.</span></span> <span data-ttu-id="dfcfa-135">Questa modifica viene monitorata nell'ambito dell'articolo della roadmap n. 70544 ed è attualmente in fase di implementazione.</span><span class="sxs-lookup"><span data-stu-id="dfcfa-135">This change is being tracked as part of roadmap item no. 70544, and is currently in a roll-out phase.</span></span>

<span data-ttu-id="dfcfa-136">Utilizzare **il** menu Visualizza per modificare le informazioni visualizzate.</span><span class="sxs-lookup"><span data-stu-id="dfcfa-136">Use the **View** menu to change what information is displayed.</span></span> <span data-ttu-id="dfcfa-137">Le descrizioni comandi consentono di determinare la visualizzazione da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="dfcfa-137">Tooltips help you determine which view to use.</span></span>

![Menu Visualizzazione Esplora minacce](../../media/ThreatExplorerViewMenu.png)

<span data-ttu-id="dfcfa-139">Dopo aver selezionato una visualizzazione, è possibile applicare filtri e configurare le query per eseguire ulteriori analisi.</span><span class="sxs-lookup"><span data-stu-id="dfcfa-139">Once you have selected a view, you can apply filters and set up queries to conduct further analysis.</span></span> <span data-ttu-id="dfcfa-140">Le sezioni seguenti forniscono una breve panoramica delle varie visualizzazioni disponibili in Esplora risorse (o rilevamenti in tempo reale).</span><span class="sxs-lookup"><span data-stu-id="dfcfa-140">The following sections provide a brief overview of the various views available in Explorer (or real-time detections).</span></span>

## <a name="email--malware"></a><span data-ttu-id="dfcfa-141">Malware > posta elettronica</span><span class="sxs-lookup"><span data-stu-id="dfcfa-141">Email > Malware</span></span>

<span data-ttu-id="dfcfa-142">Per visualizzare questo report, in Esplora risorse (o rilevamenti in tempo reale), scegliere **Visualizza** \> **malware per posta** \> **elettronica.**</span><span class="sxs-lookup"><span data-stu-id="dfcfa-142">To view this report, in Explorer (or real-time detections), choose **View** \> **Email** \> **Malware**.</span></span> <span data-ttu-id="dfcfa-143">Questa visualizzazione mostra informazioni sui messaggi di posta elettronica identificati come contenenti malware.</span><span class="sxs-lookup"><span data-stu-id="dfcfa-143">This view shows information about email messages that were identified as containing malware.</span></span>

![Visualizzare i dati sulla posta elettronica identificata come malware](../../media/ExplorerEmailMalwareMenu.png)

<span data-ttu-id="dfcfa-145">Fare **clic su Mittente** per aprire l'elenco delle opzioni di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="dfcfa-145">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="dfcfa-146">Utilizzare questo elenco per visualizzare i dati in base al mittente, ai destinatari, al dominio del mittente, all'oggetto, alla tecnologia di rilevamento, allo stato di protezione e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="dfcfa-146">Use this list to view data by sender, recipients, sender domain, subject, detection technology, protection status, and more.</span></span>

<span data-ttu-id="dfcfa-147">Ad esempio, per vedere quali azioni sono state eseguite sui messaggi di posta elettronica rilevati, scegliere **Stato protezione** nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="dfcfa-147">For example, to see what actions were taken on detected email messages, choose **Protection status** in the list.</span></span> <span data-ttu-id="dfcfa-148">Selezionare un'opzione e quindi fare clic sul pulsante Aggiorna per applicare il filtro al report.</span><span class="sxs-lookup"><span data-stu-id="dfcfa-148">Select an option, and then click the Refresh button to apply that filter to your report.</span></span>

![Opzioni di Stato di Threat Protection per Threat Explorer](../../media/ThreatExplorerProtectionStatusOptions.png)

<span data-ttu-id="dfcfa-150">Sotto il grafico, visualizzare ulteriori dettagli su messaggi specifici.</span><span class="sxs-lookup"><span data-stu-id="dfcfa-150">Below the chart, view more details about specific messages.</span></span> <span data-ttu-id="dfcfa-151">Quando si seleziona un elemento nell'elenco, viene visualizzato un riquadro a comparsa in cui sono disponibili ulteriori informazioni sull'elemento selezionato.</span><span class="sxs-lookup"><span data-stu-id="dfcfa-151">When you select an item in the list, a fly-out pane opens, where you can learn more about the item you selected.</span></span>

![Esplora minacce con riquadro a comparsa aperto](../../media/ThreatExplorerMalwareItemSelectedFlyout.png)

## <a name="email--phish"></a><span data-ttu-id="dfcfa-153">Email > Phish</span><span class="sxs-lookup"><span data-stu-id="dfcfa-153">Email > Phish</span></span>

<span data-ttu-id="dfcfa-154">Per visualizzare questo report, in Esplora risorse (o rilevamenti in tempo reale), scegliere **Visualizza** \> **e-mail** \> **Phish.**</span><span class="sxs-lookup"><span data-stu-id="dfcfa-154">To view this report, in Explorer (or real-time detections), choose **View** \> **Email** \> **Phish**.</span></span> <span data-ttu-id="dfcfa-155">Questa visualizzazione mostra i messaggi di posta elettronica identificati come tentativi di phishing.</span><span class="sxs-lookup"><span data-stu-id="dfcfa-155">This view shows email messages identified as phishing attempts.</span></span>

![Visualizzare i dati sulla posta elettronica identificata come tentativi di phishing](../../media/ThreatExplorerEmailPhish.png)

<span data-ttu-id="dfcfa-157">Fare **clic su Mittente** per aprire l'elenco delle opzioni di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="dfcfa-157">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="dfcfa-158">Utilizzare questo elenco per visualizzare i dati per mittente, destinatari, dominio mittente, IP mittente, dominio URL, fare clic su verdetto e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="dfcfa-158">Use this list to view data by sender, recipients, sender domain, sender IP, URL domain, click verdict, and more.</span></span>

<span data-ttu-id="dfcfa-159">Ad esempio, per sapere quali azioni sono state eseguite quando gli utenti hanno fatto clic su URL identificati come tentativi di phishing, scegliere Fare clic su **Verdetto** nell'elenco, selezionare una o più opzioni e quindi fare clic sul pulsante Aggiorna.</span><span class="sxs-lookup"><span data-stu-id="dfcfa-159">For example, to see what actions were taken when people clicked on URLs that were identified as phishing attempts, choose **Click verdict** in the list, select one or more options, and then click the Refresh button.</span></span>

![Fare clic su Opzioni verdetto per il report Phish](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)

<span data-ttu-id="dfcfa-161">Sotto il grafico, visualizza altri dettagli su messaggi specifici, clic su URL, URL e origine della posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="dfcfa-161">Below the chart, view more details about specific messages, URL clicks, URLs, and email origin.</span></span>

![URL rilevati come phish nei messaggi di posta elettronica](../../media/ThreatExplorerEmailPhishURLs.png)

<span data-ttu-id="dfcfa-163">Quando si seleziona un elemento nell'elenco, ad esempio un URL rilevato, viene visualizzato un riquadro a comparsa, in cui è possibile ottenere ulteriori informazioni sull'elemento selezionato.</span><span class="sxs-lookup"><span data-stu-id="dfcfa-163">When you select an item in the list, such as a URL that was detected, a fly-out pane opens, where you can learn more about the item you selected.</span></span>

![Dettagli su un URL rilevato](../../media/ThreatExplorerEmailPhishURLDetails.png)

## <a name="email--submissions"></a><span data-ttu-id="dfcfa-165">Invii > posta elettronica</span><span class="sxs-lookup"><span data-stu-id="dfcfa-165">Email > Submissions</span></span>

<span data-ttu-id="dfcfa-166">Per visualizzare questo report, in Esplora risorse (o rilevamenti in tempo reale), scegliere **Visualizza** \>  \> **invii di posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="dfcfa-166">To view this report, in Explorer (or real-time detections), choose **View** \> **Email** \> **Submissions**.</span></span> <span data-ttu-id="dfcfa-167">Questa visualizzazione mostra la posta elettronica segnalata dagli utenti come posta indesiderata, non indesiderata o phishing.</span><span class="sxs-lookup"><span data-stu-id="dfcfa-167">This view shows email that users have reported as junk, not junk, or phishing email.</span></span>

![Messaggi di posta elettronica segnalati dagli utenti](../../media/ThreatExplorerEmailUserReportedViewOptions.png)

<span data-ttu-id="dfcfa-169">Fare **clic su Mittente** per aprire l'elenco delle opzioni di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="dfcfa-169">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="dfcfa-170">Utilizzare questo elenco per visualizzare le informazioni per mittente, destinatari, tipo di report (la determinazione dell'utente che il messaggio di posta elettronica è stato indesiderato, non indesiderato o phish) e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="dfcfa-170">Use this list to view information by sender, recipients, report type (the user's determination that the email was junk, not junk, or phish), and more.</span></span>

<span data-ttu-id="dfcfa-171">Ad esempio, per visualizzare le informazioni sui messaggi di posta elettronica segnalati come tentativi di phishing, fare clic su **Tipo** di rapporto mittente, selezionare Phish e quindi fare \> clic sul pulsante Aggiorna. </span><span class="sxs-lookup"><span data-stu-id="dfcfa-171">For example, to view information about email messages that were reported as phishing attempts, click **Sender** \> **Report type**, select **Phish**, and then click the Refresh button.</span></span>

![Phish selezionato per il filtro Tipo di report](../../media/ThreatExplorerEmailUserReportedPhishSelected.png)

<span data-ttu-id="dfcfa-173">Sotto il grafico, visualizzare ulteriori dettagli su messaggi di posta elettronica specifici, ad esempio la riga dell'oggetto, l'indirizzo IP del mittente, l'utente che ha segnalato il messaggio come posta indesiderata, non indesiderata o phish e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="dfcfa-173">Below the chart, view more details about specific email messages, such as subject line, the sender's IP address, the user that reported the message as junk, not junk, or phish, and more.</span></span>

![Messaggi segnalati come tentativi di phishing](../../media/ThreatExplorerEmailPhishUserReportedPhishDetails.png)

<span data-ttu-id="dfcfa-175">Selezionare un elemento nell'elenco per visualizzare ulteriori dettagli.</span><span class="sxs-lookup"><span data-stu-id="dfcfa-175">Select an item in the list to view additional details.</span></span>

## <a name="email--all-email"></a><span data-ttu-id="dfcfa-176">Posta elettronica > Tutti i messaggi di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="dfcfa-176">Email > All email</span></span>

<span data-ttu-id="dfcfa-177">Per visualizzare questo report, in Esplora risorse scegliere **Visualizza** \> **posta elettronica** tutti i \> **messaggi.**</span><span class="sxs-lookup"><span data-stu-id="dfcfa-177">To view this report, in Explorer, choose **View** \> **Email** \> **All mail**.</span></span> <span data-ttu-id="dfcfa-178">Questa visualizzazione mostra una visualizzazione dettagliata dell'attività di posta elettronica, inclusa la posta elettronica identificata come dannosa a causa di phishing o malware, nonché tutta la posta non dannosa (posta elettronica normale, posta indesiderata e posta in blocco).</span><span class="sxs-lookup"><span data-stu-id="dfcfa-178">This views shows an all-up view of email activity, including email identified as malicious due to phishing or malware, as well all non-malicious mail (normal email, spam, and bulk mail).</span></span>

> [!NOTE]
> <span data-ttu-id="dfcfa-179">Se viene visualizzato un errore che legge troppi dati da **visualizzare,** aggiungere un filtro e, se necessario, restringere l'intervallo di date visualizzato.</span><span class="sxs-lookup"><span data-stu-id="dfcfa-179">If you get an error that reads **Too much data to display**, add a filter and, if necessary, narrow the date range you're viewing.</span></span>

<span data-ttu-id="dfcfa-180">Per applicare un filtro, scegliere **Mittente,** selezionare un elemento nell'elenco e quindi fare clic sul pulsante Aggiorna.</span><span class="sxs-lookup"><span data-stu-id="dfcfa-180">To apply a filter, choose **Sender**, select an item in the list, and then click the Refresh button.</span></span> <span data-ttu-id="dfcfa-181">In questo esempio, abbiamo usato **la tecnologia di rilevamento** come filtro (sono disponibili diverse opzioni).</span><span class="sxs-lookup"><span data-stu-id="dfcfa-181">In our example, we used **Detection technology** as a filter (there are several options available).</span></span> <span data-ttu-id="dfcfa-182">Visualizzare le informazioni in base al mittente, al dominio del mittente, ai destinatari, all'oggetto, al nome del file dell'allegato, alla famiglia di malware, allo stato di protezione (azioni intraprese dalle funzionalità e dai criteri di protezione dalle minacce in Office 365), alla tecnologia di rilevamento (come è stato rilevato il malware) e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="dfcfa-182">View information by sender, sender's domain, recipients, subject, attachment filename, malware family, protection status (actions taken by your threat protection features and policies in Office 365), detection technology (how the malware was detected), and more.</span></span>

![Visualizzare i dati sulla posta elettronica rilevata dalla tecnologia di rilevamento](../../media/0c032eb3-6021-4174-9f06-ff8f30c245ca.png)

<span data-ttu-id="dfcfa-184">Sotto il grafico, visualizzare ulteriori dettagli su messaggi di posta elettronica specifici, ad esempio riga dell'oggetto, destinatario, mittente, stato e così via.</span><span class="sxs-lookup"><span data-stu-id="dfcfa-184">Below the chart, view more details about specific email messages, such as subject line, recipient, sender, status, and so on.</span></span>

## <a name="content--malware"></a><span data-ttu-id="dfcfa-185">Malware > contenuto</span><span class="sxs-lookup"><span data-stu-id="dfcfa-185">Content > Malware</span></span>

<span data-ttu-id="dfcfa-186">Per visualizzare questo report, in Esplora risorse (o rilevamenti in tempo reale), scegliere **Visualizza** \> **malware contenuto.** \> </span><span class="sxs-lookup"><span data-stu-id="dfcfa-186">To view this report, in Explorer (or real-time detections), choose **View** \> **Content** \> **Malware**.</span></span> <span data-ttu-id="dfcfa-187">Questa visualizzazione mostra i file identificati come dannosi da [Microsoft Defender per Office 365 in SharePoint Online, OneDrive for Business e Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="dfcfa-187">This view shows files that were identified as malicious by [Microsoft Defender for Office 365 in SharePoint Online, OneDrive for Business, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="dfcfa-188">Visualizzare le informazioni per famiglia di malware, tecnologia di rilevamento (come è stato rilevato il malware) e carico di lavoro (OneDrive, SharePoint o Teams).</span><span class="sxs-lookup"><span data-stu-id="dfcfa-188">View information by malware family, detection technology (how the malware was detected), and workload (OneDrive, SharePoint, or Teams).</span></span>

![Visualizzare i dati sul malware rilevato](../../media/d11dc568-b091-4159-b261-df13d76b520b.png)

<span data-ttu-id="dfcfa-190">Sotto il grafico, visualizzare ulteriori dettagli su file specifici, ad esempio nome file allegato, carico di lavoro, dimensioni del file, chi ha modificato il file e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="dfcfa-190">Below the chart, view more details about specific files, such as attachment filename, workload, file size, who last modified the file, and more.</span></span>

## <a name="click-to-filter-capabilities"></a><span data-ttu-id="dfcfa-191">Funzionalità di filtro a clic</span><span class="sxs-lookup"><span data-stu-id="dfcfa-191">Click-to-filter capabilities</span></span>

<span data-ttu-id="dfcfa-192">Con Explorer (e rilevamenti in tempo reale), puoi applicare un filtro in un clic.</span><span class="sxs-lookup"><span data-stu-id="dfcfa-192">With Explorer (and real-time detections), you can apply a filter in a click.</span></span> <span data-ttu-id="dfcfa-193">Fare clic su un elemento nella legenda e tale elemento diventa un filtro per il report.</span><span class="sxs-lookup"><span data-stu-id="dfcfa-193">Click an item in the legend, and that item becomes a filter for the report.</span></span> <span data-ttu-id="dfcfa-194">Si supponga, ad esempio, di guardare la visualizzazione Malware in Esplora risorse:</span><span class="sxs-lookup"><span data-stu-id="dfcfa-194">For example, suppose we are looking at the Malware view in Explorer:</span></span>

![Vai a Esplora gestione \> delle minacce](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

<span data-ttu-id="dfcfa-196">Se **si fa clic su Detonazione ATP** in questo grafico, verrà restituita una visualizzazione simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="dfcfa-196">Clicking **ATP Detonation** in this chart results in a view like this:</span></span>

![Explorer filtrato per visualizzare solo Defender per Office 365 risultati detonazione](../../media/7241d7dd-27bc-467d-9db8-6e806c49df14.png)

<span data-ttu-id="dfcfa-198">In questa visualizzazione vengono ora cercati i dati per i file che sono stati detonati da [Allegati sicuri](safe-attachments.md).</span><span class="sxs-lookup"><span data-stu-id="dfcfa-198">In this view, we are now looking at data for files that were detonated by [Safe Attachments](safe-attachments.md).</span></span> <span data-ttu-id="dfcfa-199">Sotto il grafico, è possibile visualizzare i dettagli relativi a messaggi di posta elettronica specifici con allegati rilevati dagli allegati sicuri.</span><span class="sxs-lookup"><span data-stu-id="dfcfa-199">Below the chart, we can see details about specific email messages that had attachments that were detected by Safe Attachments.</span></span>

![Dettagli specifici sui messaggi di posta elettronica con allegati rilevati](../../media/c91fb05c-d1d4-4085-acc6-f7008a415c2a.png)

<span data-ttu-id="dfcfa-201">La selezione di una o più voci attiva il **menu** Azioni, che offre diverse opzioni tra cui scegliere per gli elementi selezionati.</span><span class="sxs-lookup"><span data-stu-id="dfcfa-201">Selecting one or more items activates the **Actions** menu, which offers several choices from which to choose for the selected item(s).</span></span>

![La selezione di un elemento attiva il menu Azioni](../../media/95f127a4-1b2a-4a76-88b9-096e3ba27d1b.png)

<span data-ttu-id="dfcfa-203">La possibilità di filtrare in un clic e passare a dettagli specifici può risparmiare molto tempo nell'analisi delle minacce.</span><span class="sxs-lookup"><span data-stu-id="dfcfa-203">The ability to filter in a click and navigate to specific details can save you a lot of time in investigating threats.</span></span>

## <a name="queries-and-filters"></a><span data-ttu-id="dfcfa-204">Query e filtri</span><span class="sxs-lookup"><span data-stu-id="dfcfa-204">Queries and filters</span></span>

<span data-ttu-id="dfcfa-205">Explorer (oltre al report sui rilevamenti in tempo reale) include diversi filtri potenti e funzionalità di query che consentono di analizzare i dettagli, ad esempio gli utenti di destinazione principali, le principali famiglie di malware, la tecnologia di rilevamento e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="dfcfa-205">Explorer (as well as the real-time detections report) has several powerful filters and querying capabilities that enable you to drill into details, such as top targeted users, top malware families, detection technology and more.</span></span> <span data-ttu-id="dfcfa-206">Ogni tipo di report offre diversi modi per visualizzare ed esplorare i dati.</span><span class="sxs-lookup"><span data-stu-id="dfcfa-206">Each kind of report offers a variety of ways to view and explore data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dfcfa-207">Non utilizzare caratteri jolly, ad esempio un asterisco o un punto interrogativo, nella barra delle query per Esplora risorse (o rilevamenti in tempo reale).</span><span class="sxs-lookup"><span data-stu-id="dfcfa-207">Do not use wildcard characters, such as an asterisk or a question mark, in the query bar for Explorer (or real-time detections).</span></span> <span data-ttu-id="dfcfa-208">Quando si esegue una ricerca nel campo **Oggetto** per i messaggi di posta elettronica, Explorer (o rilevamenti in tempo reale) esegue una corrispondenza parziale e restituisce risultati simili a una ricerca con caratteri jolly.</span><span class="sxs-lookup"><span data-stu-id="dfcfa-208">When you search on the **Subject field** for email messages, Explorer (or real-time detections) will perform partial matching and yield results similar to a wildcard search.</span></span>
