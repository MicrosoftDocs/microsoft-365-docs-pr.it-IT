---
title: Visualizzare i report per Office 365 Advanced Threat Protection
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 05/21/2019
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
description: Informazioni su come trovare e utilizzare i report per Office 365 Advanced Threat Protection nel centro &amp; sicurezza e conformità.
ms.openlocfilehash: 9ad177e96184913be61e098a1aafa294a123199b
ms.sourcegitcommit: ba223b4fd069fc6fd09c2a2e34c770a18bc7b2a2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2019
ms.locfileid: "39866408"
---
# <a name="view-reports-for-office-365-advanced-threat-protection"></a><span data-ttu-id="998eb-103">Visualizzare i report per Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="998eb-103">View reports for Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="998eb-104">Se l'organizzazione dispone di [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) ed è necessario disporre delle [autorizzazioni necessarie](#what-permissions-are-needed-to-view-the-atp-reports), è possibile utilizzare diversi rapporti ATP nel &amp; Centro sicurezza e conformità.</span><span class="sxs-lookup"><span data-stu-id="998eb-104">If your organization has [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) and you have the [necessary permissions](#what-permissions-are-needed-to-view-the-atp-reports), you can use several ATP reports in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="998eb-105">(Andare al \*\*\*\* \> **Dashboard**di report).</span><span class="sxs-lookup"><span data-stu-id="998eb-105">(Go to **Reports** \> **Dashboard**.)</span></span>
  
![Il dashboard &amp; del Centro sicurezza e conformità consente di individuare la modalità di funzionamento di Advanced Threat Protection](../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)
  
<span data-ttu-id="998eb-107">I report ATP includono quanto segue:</span><span class="sxs-lookup"><span data-stu-id="998eb-107">ATP reports include the following:</span></span>
- [<span data-ttu-id="998eb-108">Report dello stato di protezione dalle minacce</span><span class="sxs-lookup"><span data-stu-id="998eb-108">Threat Protection Status report</span></span>](#threat-protection-status-report)
- [<span data-ttu-id="998eb-109">Report dei tipi di file di ATP</span><span class="sxs-lookup"><span data-stu-id="998eb-109">ATP File Types report</span></span>](#atp-file-types-report)
- [<span data-ttu-id="998eb-110">Report della gestione dei messaggi di ATP</span><span class="sxs-lookup"><span data-stu-id="998eb-110">ATP Message Disposition report</span></span>](#atp-message-disposition-report)
- <span data-ttu-id="998eb-111">[rilevamenti o esploratori in tempo reale](threat-explorer.md) (a seconda che si disponga di Office 365 ATP piano 1 o 2)</span><span class="sxs-lookup"><span data-stu-id="998eb-111">either [real-time detections or Explorer](threat-explorer.md) (depending on whether you have Office 365 ATP Plan 1 or 2)</span></span>
- <span data-ttu-id="998eb-112">... [e altro ancora](#additional-reports-to-view).</span><span class="sxs-lookup"><span data-stu-id="998eb-112">... [and more](#additional-reports-to-view).</span></span> 

<span data-ttu-id="998eb-113">Leggere questo articolo per ottenere una panoramica dei rapporti ATP e su come usarli.</span><span class="sxs-lookup"><span data-stu-id="998eb-113">Read this article to get an overview of ATP reports and how to use them.</span></span>
  
## <a name="threat-protection-status-report"></a><span data-ttu-id="998eb-114">Report dello stato di protezione dalle minacce</span><span class="sxs-lookup"><span data-stu-id="998eb-114">Threat Protection Status report</span></span>

<span data-ttu-id="998eb-115">Il rapporto **sullo stato della protezione dalle minacce** è una singola visualizzazione che raggruppa informazioni su contenuto dannoso e messaggi di posta elettronica dannosi rilevati e bloccati da [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) e [Office 365 ATP](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="998eb-115">The **Threat Protection Status** report is a single view that brings together information about malicious content and malicious email detected and blocked by [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) and [Office 365 ATP](office-365-atp.md).</span></span> <span data-ttu-id="998eb-116">Questo report è utile per la visualizzazione di rilevamenti nel tempo (fino a 90 giorni) e consente agli amministratori della sicurezza di identificare le tendenze o determinare se i criteri devono essere adattati.</span><span class="sxs-lookup"><span data-stu-id="998eb-116">This report is useful for viewing detections over time (up to 90 days), and it enables security administrators to identify trends or determine whether policies need adjustments.</span></span> 

<span data-ttu-id="998eb-117">Il rapporto sullo stato di protezione di minacce fornisce un numero aggregato di messaggi di posta elettronica univoci con contenuti dannosi, ad esempio i file o gli indirizzi del sito Web (URL) bloccati dal motore antimalware, da [zero-hour auto Purge (ZAP)](zero-hour-auto-purge.md)e dalle caratteristiche ATP come i [collegamenti sicuri](atp-safe-links.md)di ATP, gli [allegati sicuri di ATP](atp-safe-attachments.md)e le [funzionalità di anti-phishing ATP](atp-anti-phishing.md).</span><span class="sxs-lookup"><span data-stu-id="998eb-117">The Threat Protection Status report provides an aggregated count of unique email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and ATP features like [ATP Safe Links](atp-safe-links.md), [ATP Safe Attachments](atp-safe-attachments.md), and [ATP anti-phishing capabilities](atp-anti-phishing.md).</span></span> 

> [!NOTE]
> <span data-ttu-id="998eb-118">Un rapporto sullo stato della protezione dalle minacce è disponibile per i clienti che dispongono di [Office 365 ATP](office-365-atp.md) o [Exchange Online Protection](exchange-online-protection-eop.md) (EOP); Tuttavia, le informazioni visualizzate nel rapporto sullo stato di protezione di minacce per i clienti ATP probabilmente conterranno dati diversi da quelli che potrebbero essere visualizzati dai clienti di EOP.</span><span class="sxs-lookup"><span data-stu-id="998eb-118">A Threat Protection Status report is available to customers who have either [Office 365 ATP](office-365-atp.md) or [Exchange Online Protection](exchange-online-protection-eop.md) (EOP); however, the information that is displayed in the Threat Protection Status report for ATP customers will likely contain different data than what EOP customers might see.</span></span> <span data-ttu-id="998eb-119">Ad esempio, il rapporto sullo stato della protezione dalle minacce per i clienti ATP conterrà informazioni sui [file dannosi rilevati in SharePoint Online, OneDrive o Microsoft teams](atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="998eb-119">For example, the Threat Protection Status report for ATP customers will contain information about [malicious files detected in SharePoint Online, OneDrive, or Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span> <span data-ttu-id="998eb-120">Tali informazioni sono specifiche di ATP, quindi i clienti che hanno EOP ma non ATP non vedranno tali dettagli nella loro relazione sullo stato di protezione dalle minacce.</span><span class="sxs-lookup"><span data-stu-id="998eb-120">Such information is specific to ATP, so customers who have EOP but not ATP will not see those details in their Threat Protection Status report.</span></span>
  
<span data-ttu-id="998eb-121">Per visualizzare il rapporto sullo stato di protezione dalle minacce, nel [Centro sicurezza &amp; e conformità](https://protection.office.com), accedere a **segnala** \> \*\*\*\* \> **lo stato di protezione delle minacce**del dashboard.</span><span class="sxs-lookup"><span data-stu-id="998eb-121">To view the Threat Protection Status report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Threat Protection Status**.</span></span>
  
![Rapporto sullo stato di protezione ATP con minacce](../media/6bdd41eb-62e0-423b-9fd4-d1d5baf0cbd5.png)
  
<span data-ttu-id="998eb-123">Per ottenere lo stato dettagliato per un giorno, posizionare il puntatore del mouse sul grafico.</span><span class="sxs-lookup"><span data-stu-id="998eb-123">To get detailed status for a day, hover over the graph.</span></span>
  
![Dati sullo stato della protezione da ATP per un giorno](../media/d5c2c6ad-c002-4985-a032-c866e46fdea8.png)
  
<span data-ttu-id="998eb-125">Per impostazione predefinita, il rapporto sullo stato della protezione dalle minacce Visualizza i dati negli ultimi sette giorni.</span><span class="sxs-lookup"><span data-stu-id="998eb-125">By default, the Threat Protection Status report shows data for the past seven days.</span></span> <span data-ttu-id="998eb-126">Tuttavia, è possibile scegliere **filtri** e modificare l'intervallo di date per visualizzare i dati fino a 90 giorni.</span><span class="sxs-lookup"><span data-stu-id="998eb-126">However, you can choose **Filters** and change the date range to view data for up to 90 days.</span></span> <span data-ttu-id="998eb-127">Se si utilizza un abbonamento di valutazione, potrebbe essere limitato a 30 giorni di dati.</span><span class="sxs-lookup"><span data-stu-id="998eb-127">(If you are using a trial subscription, you might be limited to 30 days' of data.)</span></span>
  
![Filtri di stato di protezione da minacce ATP](../media/4f703369-642b-402b-9758-b9c828283410.png)
  
<span data-ttu-id="998eb-129">È inoltre possibile utilizzare il menu **Visualizza dati in base** a per modificare le informazioni visualizzate nel report.</span><span class="sxs-lookup"><span data-stu-id="998eb-129">You can also use the **View data by** menu to change what information is displayed in the report.</span></span> 
  
![Opzioni di visualizzazione per il rapporto sullo stato della protezione da ATP](../media/4959bf8c-d192-4542-b00b-184e101e7513.png)
  
## <a name="atp-file-types-report"></a><span data-ttu-id="998eb-131">Report dei tipi di file di ATP</span><span class="sxs-lookup"><span data-stu-id="998eb-131">ATP File Types report</span></span>

<span data-ttu-id="998eb-132">Il rapporto **tipi di file ATP** Visualizza il tipo di file rilevati come dannosi dagli [allegati sicuri di ATP](atp-safe-attachments.md).</span><span class="sxs-lookup"><span data-stu-id="998eb-132">The **ATP File Types** report shows you the type of files detected as malicious by [ATP Safe Attachments](atp-safe-attachments.md).</span></span>
  
<span data-ttu-id="998eb-133">Per visualizzare questo report, nel [Centro sicurezza &amp; e conformità](https://protection.office.com), accedere a **Reports** \> **Dashboard** \> **ATP types**.</span><span class="sxs-lookup"><span data-stu-id="998eb-133">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **ATP File Types**.</span></span>
  
![Report dei tipi di file di ATP](../media/6e3f5d33-79aa-4b2d-938c-6ef135d9e54c.png)
  
<span data-ttu-id="998eb-135">Quando si posiziona il puntatore del mouse su un determinato giorno, è possibile visualizzare la ripartizione dei tipi di file dannosi rilevati dagli [allegati sicuri ATP](atp-safe-attachments.md) e dalla [protezione anti-malware antispamming &amp; in Office 365](anti-spam-and-anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="998eb-135">When you hover over a particular day, you can see the breakdown of types of malicious files that were detected by [ATP Safe Attachments](atp-safe-attachments.md) and [anti-spam &amp; anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md).</span></span>
  
![I tipi di file ATP riportano i dati per un giorno](../media/10d18428-699a-41d2-a73e-be3a8214ada1.png)
  
## <a name="atp-message-disposition-report"></a><span data-ttu-id="998eb-137">Report della gestione dei messaggi di ATP</span><span class="sxs-lookup"><span data-stu-id="998eb-137">ATP Message Disposition report</span></span>

<span data-ttu-id="998eb-138">Il rapporto di **disposizione dei messaggi ATP** indica le azioni eseguite per i messaggi di posta elettronica rilevati come contenuti dannosi.</span><span class="sxs-lookup"><span data-stu-id="998eb-138">The **ATP Message Disposition** report shows you the actions that were taken for email messages that were detected as having malicious content.</span></span> 
  
<span data-ttu-id="998eb-139">Per visualizzare questo report, nel [Centro sicurezza &amp; e conformità](https://protection.office.com), accedere a **disposizione dei messaggi**per il **Dashboard** \> dei **report** \> ATP.</span><span class="sxs-lookup"><span data-stu-id="998eb-139">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **ATP Message Disposition**.</span></span>
  
![Rapporto di disposizione del messaggio ATP](../media/b0ff65c4-53d3-496d-bafa-8937a5eb69e5.png)
  
<span data-ttu-id="998eb-141">Quando si posiziona il puntatore del mouse su una barra del grafico, è possibile vedere quali azioni sono state eseguite per il messaggio di posta elettronica rilevato per quel giorno.</span><span class="sxs-lookup"><span data-stu-id="998eb-141">When you hover over a bar in the chart, you can see what actions were taken for detected email for that day.</span></span>
  
![Dati del rapporto disposizione dei messaggi ATP per un giorno](../media/68d2beb8-4b30-48c4-8ba6-5e8ab88ae456.png)
  
## <a name="additional-reports-to-view"></a><span data-ttu-id="998eb-143">Report aggiuntivi da visualizzare</span><span class="sxs-lookup"><span data-stu-id="998eb-143">Additional reports to view</span></span>

<span data-ttu-id="998eb-144">Oltre ai report ATP descritti in questo articolo, sono disponibili diversi altri report, come descritto nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="998eb-144">In addition to the ATP reports described in this article, several other reports are available, as described in the following table:</span></span>

|<span data-ttu-id="998eb-145">Report (s)</span><span class="sxs-lookup"><span data-stu-id="998eb-145">Report(s)</span></span>  |<span data-ttu-id="998eb-146">Dettagli</span><span class="sxs-lookup"><span data-stu-id="998eb-146">Details</span></span>  |
|---------|---------|
|<span data-ttu-id="998eb-147">**Esploratori** o **rilevamenti in tempo reale** (i clienti di Office 365 trifosfato di adenosina piano 2 hanno esploratori; I clienti di Office 365 ATP Plan 1 dispongono di rilevamenti in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="998eb-147">**Explorer** or **real-time detections** (Office 365 ATP Plan 2 customers have Explorer; Office 365 ATP Plan 1 customers have real-time detections.)</span></span>| [<span data-ttu-id="998eb-148">Esplora minacce (e rilevamenti in tempo reale)</span><span class="sxs-lookup"><span data-stu-id="998eb-148">Threat Explorer (and real-time detections)</span></span>](threat-explorer.md)       |
|<span data-ttu-id="998eb-149">Report di **protezione della posta elettronica**, ad esempio un report mittenti e destinatari principali, un report di posta indesiderata e un report di rilevamenti di spam.</span><span class="sxs-lookup"><span data-stu-id="998eb-149">**Email security reports**, such as a Top Senders and Recipients report, a Spoof Mail report, and a Spam Detections report.</span></span> | [<span data-ttu-id="998eb-150">Visualizzare i report sulla sicurezza della posta &amp; elettronica nel centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="998eb-150">View email security reports in the Security &amp; Compliance Center</span></span>](../../compliance/view-email-security-reports.md)        |
|<span data-ttu-id="998eb-151">**Traccia URL collegamenti sicuri ATP** (questo è un report generato tramite PowerShell). Questo rapporto illustra i risultati delle azioni di collegamenti sicuri ATP negli ultimi sette (7) giorni.</span><span class="sxs-lookup"><span data-stu-id="998eb-151">**ATP Safe Links URL trace** (This is a report you generate by using PowerShell.) This report shows the results of ATP Safe Links actions over the past seven (7) days.</span></span> |[<span data-ttu-id="998eb-152">Informazioni di riferimento sui cmdlet Get-UrlTrace</span><span class="sxs-lookup"><span data-stu-id="998eb-152">Get-UrlTrace cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-urltrace) |
|<span data-ttu-id="998eb-153">**Risultati di EOP e ATP** (si tratta di un report personalizzato generato tramite PowerShell).</span><span class="sxs-lookup"><span data-stu-id="998eb-153">**EOP and ATP results** (This is a custom report you generate by using PowerShell).</span></span> <span data-ttu-id="998eb-154">Questo report contiene informazioni, ad esempio dominio, data, tipo di evento, direzione, azione e numero di messaggi.</span><span class="sxs-lookup"><span data-stu-id="998eb-154">This report contains information, such as Domain, Date, Event Type, Direction, Action, and Message Count.</span></span>  | [<span data-ttu-id="998eb-155">Informazioni di riferimento sui cmdlet Get-MailTrafficATPReport</span><span class="sxs-lookup"><span data-stu-id="998eb-155">Get-MailTrafficATPReport cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-mailtrafficatpreport) |
|<span data-ttu-id="998eb-156">**Rilevamenti di EOP e ATP** (è un report personalizzato che viene generato tramite PowerShell).</span><span class="sxs-lookup"><span data-stu-id="998eb-156">**EOP and ATP detections** (This is a custom report you generate by using PowerShell).</span></span> <span data-ttu-id="998eb-157">Questo report contiene informazioni dettagliate su file o URL dannosi, tentativi di phishing, rappresentazione e altre potenziali minacce nei messaggi di posta elettronica o nei file.</span><span class="sxs-lookup"><span data-stu-id="998eb-157">This report contains details about malicious files or URLs, phishing attempts, impersonation, and other potential threats in email or files.</span></span>   | [<span data-ttu-id="998eb-158">Informazioni di riferimento sui cmdlet Get-MailDetailATPReport</span><span class="sxs-lookup"><span data-stu-id="998eb-158">Get-MailDetailATPReport cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-maildetailatpreport)        |

  
## <a name="what-permissions-are-needed-to-view-the-atp-reports"></a><span data-ttu-id="998eb-159">Quali autorizzazioni sono necessarie per visualizzare i report ATP?</span><span class="sxs-lookup"><span data-stu-id="998eb-159">What permissions are needed to view the ATP reports?</span></span>

<span data-ttu-id="998eb-160">Per visualizzare e utilizzare i rapporti descritti in questo articolo, **è necessario disporre di un ruolo appropriato assegnato per il Centro sicurezza &amp; e l'interfaccia di amministrazione di Exchange**.</span><span class="sxs-lookup"><span data-stu-id="998eb-160">In order to view and use the reports described in this article, **you must have an appropriate role assigned for both the Security &amp; Compliance Center and the Exchange admin center**.</span></span>

- <span data-ttu-id="998eb-161">Per il centro &amp; sicurezza e conformità, è necessario che sia assegnato uno dei ruoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="998eb-161">For the Security &amp; Compliance Center, you must have one of the following roles assigned:</span></span>
    - <span data-ttu-id="998eb-162">Gestione organizzazione</span><span class="sxs-lookup"><span data-stu-id="998eb-162">Organization Management</span></span>
    - <span data-ttu-id="998eb-163">Amministratore della sicurezza (è possibile assegnarlo nell'interfaccia di amministrazione di Azure Active[https://aad.portal.azure.com](https://aad.portal.azure.com)directory ())</span><span class="sxs-lookup"><span data-stu-id="998eb-163">Security Administrator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
    - <span data-ttu-id="998eb-164">Lettore di sicurezza</span><span class="sxs-lookup"><span data-stu-id="998eb-164">Security Reader</span></span>

- <span data-ttu-id="998eb-165">Per Exchange Online, è necessario che sia assegnato uno dei ruoli seguenti nell'interfaccia di amministrazione di Exchange ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) o con i cmdlet di PowerShell (vedere [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)):</span><span class="sxs-lookup"><span data-stu-id="998eb-165">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) or with PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)):</span></span>
    - <span data-ttu-id="998eb-166">Gestione organizzazione</span><span class="sxs-lookup"><span data-stu-id="998eb-166">Organization Management</span></span>
    - <span data-ttu-id="998eb-167">Gestione organizzazione in sola visualizzazione</span><span class="sxs-lookup"><span data-stu-id="998eb-167">View-only Organization Management</span></span>
    - <span data-ttu-id="998eb-168">Ruolo Destinatari di sola lettura</span><span class="sxs-lookup"><span data-stu-id="998eb-168">View-Only Recipients role</span></span>
    - <span data-ttu-id="998eb-169">Gestione della conformità</span><span class="sxs-lookup"><span data-stu-id="998eb-169">Compliance Management</span></span>

<span data-ttu-id="998eb-170">Per altre informazioni, vedere le risorse seguenti:</span><span class="sxs-lookup"><span data-stu-id="998eb-170">To learn more, see the following resources:</span></span>

- [<span data-ttu-id="998eb-171">Permissions in the Office 365 Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="998eb-171">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)

- [<span data-ttu-id="998eb-172">Autorizzazioni funzionalità in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="998eb-172">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)
   
## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="998eb-173">Cosa succede se i rapporti non mostrano dati?</span><span class="sxs-lookup"><span data-stu-id="998eb-173">What if the reports aren't showing data?</span></span>

<span data-ttu-id="998eb-174">Se i dati non vengono visualizzati nei rapporti ATP, verificare che i criteri siano configurati correttamente.</span><span class="sxs-lookup"><span data-stu-id="998eb-174">If you are not seeing data in your ATP reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="998eb-175">L'organizzazione deve disporre di [criteri dei collegamenti sicuri ATP](set-up-atp-safe-links-policies.md) e di criteri per gli [allegati sicuri ATP](set-up-atp-safe-attachments-policies.md) definiti in modo che la protezione da ATP sia sul posto.</span><span class="sxs-lookup"><span data-stu-id="998eb-175">Your organization must have [ATP Safe Links policies](set-up-atp-safe-links-policies.md) and [ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) defined in order for ATP protection to be in place.</span></span> <span data-ttu-id="998eb-176">Vedere anche [protezione da posta indesiderata e anti-malware in Office 365](anti-spam-and-anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="998eb-176">Also see [Anti-spam and anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="998eb-177">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="998eb-177">Related topics</span></span>

[<span data-ttu-id="998eb-178">Report e informazioni dettagliate nel centro sicurezza &amp; e conformità di Office 365</span><span class="sxs-lookup"><span data-stu-id="998eb-178">Reports and insights in the Office 365 Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="998eb-179">Creare una pianificazione per un report nel centro sicurezza &amp; e conformità</span><span class="sxs-lookup"><span data-stu-id="998eb-179">Create a schedule for a report in the Security &amp; Compliance Center</span></span>](create-a-schedule-for-a-report.md)
  
[<span data-ttu-id="998eb-180">Configurare e scaricare un report personalizzato nel centro sicurezza &amp; e conformità</span><span class="sxs-lookup"><span data-stu-id="998eb-180">Set up and download a custom report in the Security &amp; Compliance Center</span></span>](set-up-and-download-a-custom-report.md)
  

