---
title: Visualizzare i report di prevenzione della perdita di dati
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 6/7/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
description: Con i report DLP in Office 365, è possibile visualizzare rapidamente il numero di corrispondenze di criteri DLP, sostituzioni o falsi positivi. controllare se si sta facendo una tendenza verso l'alto o verso il basso nel tempo; filtrare il report in modi diversi; e visualizzare ulteriori dettagli selezionando un punto su una linea del grafico.
ms.openlocfilehash: c00047680f684e3845c4383face09c2cee579721
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42068759"
---
# <a name="view-the-reports-for-data-loss-prevention"></a><span data-ttu-id="bcd17-103">Visualizzare i report di prevenzione della perdita di dati</span><span class="sxs-lookup"><span data-stu-id="bcd17-103">View the reports for data loss prevention</span></span>

<span data-ttu-id="bcd17-104">Dopo aver creato i criteri di prevenzione della perdita di dati (DLP), è necessario verificare che funzionino come previsto e che vi aiuti a rimanere conformi.</span><span class="sxs-lookup"><span data-stu-id="bcd17-104">After you create your data loss prevention (DLP) policies, you'll want to verify that they're working as you intended and helping you to stay compliant.</span></span> <span data-ttu-id="bcd17-105">Con i report DLP nel centro sicurezza &amp; e conformità di Office 365, è possibile visualizzare rapidamente:</span><span class="sxs-lookup"><span data-stu-id="bcd17-105">With the DLP reports in the Office 365 Security &amp; Compliance Center, you can quickly view:</span></span>
  
- <span data-ttu-id="bcd17-106">**Corrispondenze di criteri DLP** Questo rapporto Visualizza il numero di corrispondenze di criteri DLP nel tempo.</span><span class="sxs-lookup"><span data-stu-id="bcd17-106">**DLP policy matches** This report shows the count of DLP policy matches over time.</span></span> <span data-ttu-id="bcd17-107">È possibile filtrare il report per data, percorso, criterio o azione.</span><span class="sxs-lookup"><span data-stu-id="bcd17-107">You can filter the report by date, location, policy, or action.</span></span> <span data-ttu-id="bcd17-108">È possibile utilizzare questo report per:</span><span class="sxs-lookup"><span data-stu-id="bcd17-108">You can use this report to:</span></span> 
    
  - <span data-ttu-id="bcd17-109">Ottimizzare o affinare i criteri DLP quando vengono eseguiti in modalità test.</span><span class="sxs-lookup"><span data-stu-id="bcd17-109">Tune or refine your DLP policies as you run them in test mode.</span></span> <span data-ttu-id="bcd17-110">È possibile visualizzare la regola specifica corrispondente al contenuto.</span><span class="sxs-lookup"><span data-stu-id="bcd17-110">You can view the specific rule that matched the content.</span></span>
    
  - <span data-ttu-id="bcd17-111">Concentrare l'attenzione su intervalli di tempo specifici e comprendere i motivi di eventuali impennate e tendenze.</span><span class="sxs-lookup"><span data-stu-id="bcd17-111">Focus on specific time periods and understand the reasons for spikes and trends.</span></span>
    
  - <span data-ttu-id="bcd17-112">Individuare i processi aziendali che violano i criteri DLP dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="bcd17-112">Discover business processes that violate your organization's DLP policies.</span></span>
    
  - <span data-ttu-id="bcd17-113">Comprendere qualsiasi impatto aziendale dei criteri DLP vedendo quali azioni vengono applicate al contenuto.</span><span class="sxs-lookup"><span data-stu-id="bcd17-113">Understand any business impact of the DLP policies by seeing what actions are being applied to content.</span></span>
    
  - <span data-ttu-id="bcd17-114">Verificare la conformità con uno specifico criterio DLP mostrando le eventuali corrispondenze per tale criterio.</span><span class="sxs-lookup"><span data-stu-id="bcd17-114">Verify compliance with a specific DLP policy by showing any matches for that policy.</span></span>
    
  - <span data-ttu-id="bcd17-115">Consente di visualizzare un elenco di utenti principali e di ripetere gli utenti che contribuiscono a incidenti nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="bcd17-115">View a list of top users and repeat users who are contributing to incidents in your organization.</span></span>
    
  - <span data-ttu-id="bcd17-116">Visualizzare un elenco dei tipi principali di informazioni riservate nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="bcd17-116">View a list of the top types of sensitive information in your organization.</span></span>
    
- <span data-ttu-id="bcd17-117">**Incidenti DLP** Questo rapporto Visualizza anche le corrispondenze di criteri nel tempo, come il rapporto criteri di corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="bcd17-117">**DLP incidents** This report also shows policy matches over time, like the policy matches report.</span></span> <span data-ttu-id="bcd17-118">Tuttavia, il rapporto dei criteri corrisponde alle corrispondenze a livello di regola; ad esempio, se un messaggio di posta elettronica corrisponde a tre regole diverse, il rapporto criteri corrisponde a tre diversi elementi pubblicitari.</span><span class="sxs-lookup"><span data-stu-id="bcd17-118">However, the policy matches report shows matches at a rule level; for example, if an email matched three different rules, the policy matches report shows three different line items.</span></span> <span data-ttu-id="bcd17-119">Al contrario, il rapporto sugli incidenti Visualizza le corrispondenze a livello di elemento. ad esempio, se un messaggio di posta elettronica corrisponde a tre regole diverse, il rapporto eventi non consentiti Visualizza un singolo elemento di riga per il contenuto.</span><span class="sxs-lookup"><span data-stu-id="bcd17-119">By contrast, the incidents report shows matches at an item level; for example, if an email matched three different rules, the incidents report shows a single line item for that piece of content.</span></span> 
    
  <span data-ttu-id="bcd17-120">Poiché i conteggi dei rapporti vengono aggregati in modo diverso, il rapporto criteri di ricerca è migliore per identificare le corrispondenze con regole specifiche e criteri DLP di ottimizzazione.</span><span class="sxs-lookup"><span data-stu-id="bcd17-120">Because the report counts are aggregated differently, the policy matches report is better for identifying matches with specific rules and fine tuning DLP policies.</span></span> <span data-ttu-id="bcd17-121">Il rapporto sugli incidenti è migliore per identificare parti di contenuto specifiche che sono problematiche per i criteri DLP.</span><span class="sxs-lookup"><span data-stu-id="bcd17-121">The incidents report is better for identifying specific pieces of content that are problematic for your DLP policies.</span></span>
    
- <span data-ttu-id="bcd17-122">**False positive e sostituzioni DLP** Se il criterio DLP consente agli utenti di eseguire l'override o di segnalare un falso positivo, questo rapporto Visualizza il numero di istanze nel tempo.</span><span class="sxs-lookup"><span data-stu-id="bcd17-122">**DLP false positives and overrides** If your DLP policy allows users to override it or report a false positive, this report shows a count of such instances over time.</span></span> <span data-ttu-id="bcd17-123">È possibile filtrare il report per data, percorso o criterio.</span><span class="sxs-lookup"><span data-stu-id="bcd17-123">You can filter the report by date, location, or policy.</span></span> <span data-ttu-id="bcd17-124">È possibile utilizzare questo report per:</span><span class="sxs-lookup"><span data-stu-id="bcd17-124">You can use this report to:</span></span> 
    
  - <span data-ttu-id="bcd17-125">Ottimizzare o affinare i criteri DLP vedendo quali criteri incorrono in un numero elevato di falsi positivi.</span><span class="sxs-lookup"><span data-stu-id="bcd17-125">Tune or refine your DLP policies by seeing which policies incur a high number of false positives.</span></span>
    
  - <span data-ttu-id="bcd17-126">Visualizzare le giustificazioni inviate dagli utenti quando si risolve un suggerimento per i criteri eseguendo l'override del criterio.</span><span class="sxs-lookup"><span data-stu-id="bcd17-126">View the justifications submitted by users when they resolve a policy tip by overriding the policy.</span></span>
    
  - <span data-ttu-id="bcd17-127">Individuare la posizione in cui i criteri DLP sono in conflitto con processi aziendali validi incorrendo in un numero elevato di sostituzioni degli utenti.</span><span class="sxs-lookup"><span data-stu-id="bcd17-127">Discover where DLP policies conflict with valid business processes by incurring a high number of user overrides.</span></span>
    
<span data-ttu-id="bcd17-128">Tutti i report DLP sono in grado di visualizzare i dati del periodo di quattro mesi più recente.</span><span class="sxs-lookup"><span data-stu-id="bcd17-128">All DLP reports can show data from the most recent four-month time period.</span></span> <span data-ttu-id="bcd17-129">I dati più recenti possono richiedere fino a 24 ore per essere visualizzati nei rapporti.</span><span class="sxs-lookup"><span data-stu-id="bcd17-129">The most recent data can take up to 24 hours to appear in the reports.</span></span>
  
<span data-ttu-id="bcd17-130">Questi rapporti sono disponibili &amp; nel **Dashboard**dei **report** \> del centro \> sicurezza e conformità.</span><span class="sxs-lookup"><span data-stu-id="bcd17-130">You can find these reports in the Security &amp; Compliance Center \> **Reports** \> **Dashboard**.</span></span>
  
![Rapporto delle corrispondenze dei criteri DLP](../media/117d20c9-d379-403f-ad68-1f5cd6c4e5cf.png)
  
## <a name="view-the-justification-submitted-by-a-user-for-an-override"></a><span data-ttu-id="bcd17-132">Visualizzare la giustificazione inviata da un utente per una sostituzione</span><span class="sxs-lookup"><span data-stu-id="bcd17-132">View the justification submitted by a user for an override</span></span>

<span data-ttu-id="bcd17-133">Se il criterio DLP consente agli utenti di sostituirlo, è possibile utilizzare il rapporto false positive e Sostituisci per visualizzare il testo inviato dagli utenti nel suggerimento per i criteri.</span><span class="sxs-lookup"><span data-stu-id="bcd17-133">If your DLP policy allows users to override it, you can use the false positive and override report to view the text submitted by users in the policy tip.</span></span>
  
![Campo giustificazione nei dettagli del rapporto di sostituzione e false](../media/e11e3126-026d-4e77-a16d-74a0686d1fa3.png)
  
## <a name="take-action-on-insights-and-recommendations"></a><span data-ttu-id="bcd17-135">Intervenire su informazioni e suggerimenti</span><span class="sxs-lookup"><span data-stu-id="bcd17-135">Take action on insights and recommendations</span></span>

<span data-ttu-id="bcd17-136">I report possono mostrare spunti e suggerimenti in cui è possibile fare clic sull'icona di avviso rossa per visualizzare i dettagli relativi a potenziali problemi e intraprendere possibili interventi correttivi.</span><span class="sxs-lookup"><span data-stu-id="bcd17-136">Reports can show insights and recommendations where you can click the red warning icon to see details about potential issues and take possible remedial action.</span></span>
  
![Fare clic su un'icona Insights per visualizzare i dettagli e le azioni da intraprendere](../media/51782036-7299-4960-8175-75c2b1637159.png)
  
## <a name="permissions-for-dlp-reports"></a><span data-ttu-id="bcd17-138">Autorizzazioni per i report DLP</span><span class="sxs-lookup"><span data-stu-id="bcd17-138">Permissions for DLP reports</span></span>

<span data-ttu-id="bcd17-139">Per visualizzare i report DLP nel centro sicurezza & Compliance, è necessario assegnare il seguente:</span><span class="sxs-lookup"><span data-stu-id="bcd17-139">To view DLP reports in the Security & Compliance Center, you have to be assigned the:</span></span>

- <span data-ttu-id="bcd17-140">Ruolo **lettore di sicurezza** nell'interfaccia di amministrazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="bcd17-140">**Security Reader** role in the Exchange admin center.</span></span> <span data-ttu-id="bcd17-141">Per impostazione predefinita, questo ruolo viene assegnato ai gruppi di ruoli Gestione organizzazione e lettore di sicurezza nell'interfaccia di amministrazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="bcd17-141">By default, this role is assigned to the Organization Management and Security Reader role groups in the Exchange admin center.</span></span>

- <span data-ttu-id="bcd17-142">Ruolo di **gestione della conformità DLP di sola visualizzazione** nel centro sicurezza & Compliance.</span><span class="sxs-lookup"><span data-stu-id="bcd17-142">**View-Only DLP Compliance Management** role in the Security & Compliance Center.</span></span> <span data-ttu-id="bcd17-143">Per impostazione predefinita, questo ruolo viene assegnato ai gruppi di ruoli amministratore di conformità, Gestione organizzazione, amministratore della sicurezza e lettore di sicurezza nel centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="bcd17-143">By default, this role is assigned to the Compliance Administrator, Organization Management, Security Administrator, and Security Reader role groups in the Security & Compliance Center.</span></span>

- <span data-ttu-id="bcd17-144">Ruolo **destinatari di sola visualizzazione** nell'interfaccia di amministrazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="bcd17-144">**View-Only Recipients** role in the Exchange admin center.</span></span> <span data-ttu-id="bcd17-145">Per impostazione predefinita, questo ruolo viene assegnato ai gruppi di ruoli Gestione conformità, Gestione organizzazione e organizzazione di sola visualizzazione nell'interfaccia di amministrazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="bcd17-145">By default, this role is assigned to the Compliance Management, Organization Management, and View-Only Organization Management role groups in the Exchange admin center.</span></span>

## <a name="find-the-cmdlets-for-the-dlp-reports"></a><span data-ttu-id="bcd17-146">Individuare i cmdlet per i report DLP</span><span class="sxs-lookup"><span data-stu-id="bcd17-146">Find the cmdlets for the DLP reports</span></span>

<span data-ttu-id="bcd17-147">Per usare la maggior parte dei cmdlet per il Centro sicurezza e conformità, è necessario:</span><span class="sxs-lookup"><span data-stu-id="bcd17-147">To use most of the cmdlets for the Security &amp; Compliance Center, you need to:</span></span>
  
1. <span data-ttu-id="bcd17-148">[Connettersi al Centro sicurezza e conformità di Office 365 utilizzando la sessione remota di PowerShell](https://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409).</span><span class="sxs-lookup"><span data-stu-id="bcd17-148">[Connect to the Office 365 Security &amp; Compliance Center using remote PowerShell](https://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409)</span></span>
    
2. <span data-ttu-id="bcd17-149">Utilizzare uno di questi [cmdlet del centro &amp; sicurezza e conformità di Office 365](https://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)</span><span class="sxs-lookup"><span data-stu-id="bcd17-149">Use any of these [Office 365 Security &amp; Compliance Center cmdlets](https://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)</span></span>
    
<span data-ttu-id="bcd17-150">I report dei criteri di prevenzione della perdita dei dati devono tuttavia estrarre i dati da Office 365, incluso Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="bcd17-150">However, DLP reports need pull data from across Office 365, including Exchange Online.</span></span> <span data-ttu-id="bcd17-151">Per questo motivo, i cmdlet per i report DLP sono disponibili in PowerShell di Exchange Online, non in PowerShell &amp; per il Centro sicurezza e conformità.</span><span class="sxs-lookup"><span data-stu-id="bcd17-151">For this reason, the cmdlets for the DLP reports are available in Exchange Online Powershell—not in Security &amp; Compliance Center Powershell.</span></span> <span data-ttu-id="bcd17-152">Per usare i cmdlet per i report dei criteri di prevenzione della perdita dei dati, è quindi necessario:</span><span class="sxs-lookup"><span data-stu-id="bcd17-152">Therefore, to use the cmdlets for the DLP reports, you need to:</span></span>
  
1. [<span data-ttu-id="bcd17-153">Connettersi a Exchange Online tramite la sessione remota di PowerShell</span><span class="sxs-lookup"><span data-stu-id="bcd17-153">Connect to Exchange Online using remote PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkID=799773&amp;clcid=0x409)
    
2. <span data-ttu-id="bcd17-154">Usare uno di questi cmdlet per i report dei criteri di prevenzione della perdita dei dati:</span><span class="sxs-lookup"><span data-stu-id="bcd17-154">Use any of these cmdlets for the DLP reports:</span></span>
    
      - [<span data-ttu-id="bcd17-155">Get-DlpDetectionsReport</span><span class="sxs-lookup"><span data-stu-id="bcd17-155">Get-DlpDetectionsReport</span></span>](https://go.microsoft.com/fwlink/?LinkID=799774&amp;clcid=0x409)
    
      - [<span data-ttu-id="bcd17-156">Get-DlpDetailReport</span><span class="sxs-lookup"><span data-stu-id="bcd17-156">Get-DlpDetailReport</span></span>](https://go.microsoft.com/fwlink/?LinkID=799775&amp;clcid=0x409)
    

