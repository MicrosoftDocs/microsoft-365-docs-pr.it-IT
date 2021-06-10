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
ms.custom: seo-marvel-apr2020
description: Utilizzare i report DLP in Office 365 per visualizzare il numero di corrispondenze, sostituzioni o falsi positivi dei criteri DLP e vedere se stanno andando verso l'alto o verso il basso nel tempo.
ms.openlocfilehash: 742f0ef0334e714c7f31cbc2f97559993454f6b7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928390"
---
# <a name="view-the-reports-for-data-loss-prevention"></a><span data-ttu-id="fc109-103">Visualizzare i report di prevenzione della perdita di dati</span><span class="sxs-lookup"><span data-stu-id="fc109-103">View the reports for data loss prevention</span></span>

<span data-ttu-id="fc109-104">Dopo aver creato i criteri di prevenzione della perdita dei dati (DLP), è necessario verificare che funzionino come previsto e per mantenere la conformità.</span><span class="sxs-lookup"><span data-stu-id="fc109-104">After you create your data loss prevention (DLP) policies, you'll want to verify that they're working as you intended and helping you to stay compliant.</span></span> <span data-ttu-id="fc109-105">Con i report DLP nel Centro &amp; sicurezza e conformità, è possibile visualizzare rapidamente:</span><span class="sxs-lookup"><span data-stu-id="fc109-105">With the DLP reports in the Security &amp; Compliance Center, you can quickly view:</span></span>
  
- <span data-ttu-id="fc109-106">**Corrispondenze dei criteri DLP** Questo report mostra il conteggio delle corrispondenze dei criteri DLP nel tempo.</span><span class="sxs-lookup"><span data-stu-id="fc109-106">**DLP policy matches** This report shows the count of DLP policy matches over time.</span></span> <span data-ttu-id="fc109-107">È possibile filtrare i report per data, percorso, criterio o azione.</span><span class="sxs-lookup"><span data-stu-id="fc109-107">You can filter the report by date, location, policy, or action.</span></span> <span data-ttu-id="fc109-108">È possibile usare questo report per:</span><span class="sxs-lookup"><span data-stu-id="fc109-108">You can use this report to:</span></span> 
    
  - <span data-ttu-id="fc109-109">Ottimizzare o perfezionare i criteri di prevenzione della perdita dei dati durante la loro esecuzione in modalità test.</span><span class="sxs-lookup"><span data-stu-id="fc109-109">Tune or refine your DLP policies as you run them in test mode.</span></span> <span data-ttu-id="fc109-110">È possibile visualizzare la regola specifica per la quale è stata trovata una corrispondenza al contenuto.</span><span class="sxs-lookup"><span data-stu-id="fc109-110">You can view the specific rule that matched the content.</span></span>
    
  - <span data-ttu-id="fc109-111">Concentrare l'attenzione su intervalli di tempo specifici e comprendere i motivi di eventuali impennate e tendenze.</span><span class="sxs-lookup"><span data-stu-id="fc109-111">Focus on specific time periods and understand the reasons for spikes and trends.</span></span>
    
  - <span data-ttu-id="fc109-112">Individuare i processi aziendali che violano i criteri DLP dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="fc109-112">Discover business processes that violate your organization's DLP policies.</span></span>
    
  - <span data-ttu-id="fc109-113">Comprendere ogni impatto aziendale dei criteri di prevenzione della perdita dei dati visualizzando quali azioni sono state applicate al contenuto.</span><span class="sxs-lookup"><span data-stu-id="fc109-113">Understand any business impact of the DLP policies by seeing what actions are being applied to content.</span></span>
    
  - <span data-ttu-id="fc109-114">Verificare la conformità con uno specifico criterio DLP mostrando le eventuali corrispondenze per tale criterio.</span><span class="sxs-lookup"><span data-stu-id="fc109-114">Verify compliance with a specific DLP policy by showing any matches for that policy.</span></span>
    
  - <span data-ttu-id="fc109-115">Visualizzare un elenco degli utenti principali e ripetere gli utenti che contribuiscono agli incidenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="fc109-115">View a list of top users and repeat users who are contributing to incidents in your organization.</span></span>
    
  - <span data-ttu-id="fc109-116">Visualizzare un elenco dei principali tipi di informazioni riservate nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="fc109-116">View a list of the top types of sensitive information in your organization.</span></span>
    
- <span data-ttu-id="fc109-117">**Eventi imprevisti DLP** Questo report mostra anche le corrispondenze dei criteri nel tempo, come il rapporto corrispondenze dei criteri.</span><span class="sxs-lookup"><span data-stu-id="fc109-117">**DLP incidents** This report also shows policy matches over time, like the policy matches report.</span></span> <span data-ttu-id="fc109-118">Tuttavia, il rapporto corrispondenze dei criteri mostra le corrispondenze a livello di regola. Ad esempio, se un messaggio di posta elettronica corrisponde a tre regole diverse, il rapporto corrisponde ai criteri mostra tre voci diverse.</span><span class="sxs-lookup"><span data-stu-id="fc109-118">However, the policy matches report shows matches at a rule level; for example, if an email matched three different rules, the policy matches report shows three different line items.</span></span> <span data-ttu-id="fc109-119">Al contrario, il report degli eventi imprevisti mostra le corrispondenze a livello di elemento. Ad esempio, se un messaggio di posta elettronica corrisponde a tre regole diverse, il rapporto eventi imprevisti mostra una singola riga per tale elemento di contenuto.</span><span class="sxs-lookup"><span data-stu-id="fc109-119">By contrast, the incidents report shows matches at an item level; for example, if an email matched three different rules, the incidents report shows a single line item for that piece of content.</span></span> 
    
  <span data-ttu-id="fc109-120">Poiché i conteggi dei report vengono aggregati in modo diverso, il rapporto corrispondenze dei criteri è migliore per identificare le corrispondenze con regole specifiche e ottimizzare i criteri DLP.</span><span class="sxs-lookup"><span data-stu-id="fc109-120">Because the report counts are aggregated differently, the policy matches report is better for identifying matches with specific rules and fine tuning DLP policies.</span></span> <span data-ttu-id="fc109-121">Il report relativo agli incidenti è più utile per identificare i tipi di contenuto specifici che risultano essere problematici per i propri criteri di prevenzione della perdita dei dati.</span><span class="sxs-lookup"><span data-stu-id="fc109-121">The incidents report is better for identifying specific pieces of content that are problematic for your DLP policies.</span></span>
    
- <span data-ttu-id="fc109-122">**Falsi positivi e sostituzioni DLP** Se il criterio DLP consente agli utenti di ignorarlo o segnalare un falso positivo, questo report mostra un conteggio di tali istanze nel tempo.</span><span class="sxs-lookup"><span data-stu-id="fc109-122">**DLP false positives and overrides** If your DLP policy allows users to override it or report a false positive, this report shows a count of such instances over time.</span></span> <span data-ttu-id="fc109-123">È possibile filtrare i report per data, percorso o criterio.</span><span class="sxs-lookup"><span data-stu-id="fc109-123">You can filter the report by date, location, or policy.</span></span> <span data-ttu-id="fc109-124">È possibile usare questo report per:</span><span class="sxs-lookup"><span data-stu-id="fc109-124">You can use this report to:</span></span> 
    
  - <span data-ttu-id="fc109-125">Ottimizzare o perfezionare i criteri di prevenzione della perdita dei dati rilevando i criteri che causano un numero elevato di falsi positivi.</span><span class="sxs-lookup"><span data-stu-id="fc109-125">Tune or refine your DLP policies by seeing which policies incur a high number of false positives.</span></span>
    
  - <span data-ttu-id="fc109-126">Visualizzare le giustificazioni inviate dagli utenti quando risolvono un suggerimento per i criteri ignorando il criterio.</span><span class="sxs-lookup"><span data-stu-id="fc109-126">View the justifications submitted by users when they resolve a policy tip by overriding the policy.</span></span>
    
  - <span data-ttu-id="fc109-127">Scoprire dove i criteri di prevenzione della perdita dei dati sono in conflitto con processi aziendali validi incorrendo in un numero elevato di override degli utenti.</span><span class="sxs-lookup"><span data-stu-id="fc109-127">Discover where DLP policies conflict with valid business processes by incurring a high number of user overrides.</span></span>
    
<span data-ttu-id="fc109-128">Tutti i report di prevenzione della perdita dei dati possono mostrare i dati relativi a un periodo di tempo di quattro mesi precedenti.</span><span class="sxs-lookup"><span data-stu-id="fc109-128">All DLP reports can show data from the most recent four-month time period.</span></span> <span data-ttu-id="fc109-129">I dati più recenti possono richiedere fino a 24 ore per essere visualizzati nei report.</span><span class="sxs-lookup"><span data-stu-id="fc109-129">The most recent data can take up to 24 hours to appear in the reports.</span></span>
  
<span data-ttu-id="fc109-130">Questi report sono disponibili nel dashboard dei report del Centro sicurezza e &amp; \>  \> **conformità.**</span><span class="sxs-lookup"><span data-stu-id="fc109-130">You can find these reports in the Security &amp; Compliance Center \> **Reports** \> **Dashboard**.</span></span>
  
![Report corrispondenze criteri DLP](../media/117d20c9-d379-403f-ad68-1f5cd6c4e5cf.png)
  
## <a name="view-the-justification-submitted-by-a-user-for-an-override"></a><span data-ttu-id="fc109-132">Visualizzare la giustificazione inviata da un utente per una sostituzione</span><span class="sxs-lookup"><span data-stu-id="fc109-132">View the justification submitted by a user for an override</span></span>

<span data-ttu-id="fc109-133">Se i criteri di prevenzione della perdita dei dati dell'organizzazione consentono agli utenti di ignorarli, è possibile utilizzare il report sui criteri falsi positivi e ignorati per visualizzare il testo inviato dagli utenti nei suggerimenti per i criteri.</span><span class="sxs-lookup"><span data-stu-id="fc109-133">If your DLP policy allows users to override it, you can use the false positive and override report to view the text submitted by users in the policy tip.</span></span>
  
![Campo Giustificazione nei dettagli del report dlp falso positivo e sostituzione](../media/e11e3126-026d-4e77-a16d-74a0686d1fa3.png)
  
## <a name="take-action-on-insights-and-recommendations"></a><span data-ttu-id="fc109-135">Eseguire azioni su informazioni dettagliate e suggerimenti</span><span class="sxs-lookup"><span data-stu-id="fc109-135">Take action on insights and recommendations</span></span>

<span data-ttu-id="fc109-136">I report possono mostrare informazioni dettagliate e suggerimenti in cui è possibile fare clic sull'icona di avviso rossa per visualizzare i dettagli sui potenziali problemi e intraprendere possibili azioni correttive.</span><span class="sxs-lookup"><span data-stu-id="fc109-136">Reports can show insights and recommendations where you can click the red warning icon to see details about potential issues and take possible remedial action.</span></span>
  
![Fare clic su un'icona informazioni dettagliate per visualizzare i dettagli e le azioni da eseguire](../media/51782036-7299-4960-8175-75c2b1637159.png)
  
## <a name="permissions-for-dlp-reports"></a><span data-ttu-id="fc109-138">Autorizzazioni per i report DLP</span><span class="sxs-lookup"><span data-stu-id="fc109-138">Permissions for DLP reports</span></span>

<span data-ttu-id="fc109-139">Per visualizzare i report DLP nel Centro sicurezza & conformità, è necessario disporre delle autorizzazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="fc109-139">To view DLP reports in the Security & Compliance Center, you have to be assigned the:</span></span>

- <span data-ttu-id="fc109-140">**Ruolo Lettore** di sicurezza nell'Exchange di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="fc109-140">**Security Reader** role in the Exchange admin center.</span></span> <span data-ttu-id="fc109-141">Per impostazione predefinita, questo ruolo viene assegnato ai gruppi di ruoli Gestione organizzazione e Lettore sicurezza nell'Exchange di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="fc109-141">By default, this role is assigned to the Organization Management and Security Reader role groups in the Exchange admin center.</span></span>

- <span data-ttu-id="fc109-142">**Ruolo Gestione conformità DLP di sola** visualizzazione nel Centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="fc109-142">**View-Only DLP Compliance Management** role in the Security & Compliance Center.</span></span> <span data-ttu-id="fc109-143">Per impostazione predefinita, questo ruolo viene assegnato ai gruppi di ruoli Amministratore conformità, Gestione organizzazione, Amministratore sicurezza e Lettore sicurezza nel Centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="fc109-143">By default, this role is assigned to the Compliance Administrator, Organization Management, Security Administrator, and Security Reader role groups in the Security & Compliance Center.</span></span>

- <span data-ttu-id="fc109-144">**Ruolo Destinatari di sola** visualizzazione nell'Exchange di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="fc109-144">**View-Only Recipients** role in the Exchange admin center.</span></span> <span data-ttu-id="fc109-145">Per impostazione predefinita, questo ruolo viene assegnato ai gruppi di ruoli Gestione conformità, Gestione organizzazione e Gestione organizzazione View-Only nell'interfaccia Exchange di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="fc109-145">By default, this role is assigned to the Compliance Management, Organization Management, and View-Only Organization Management role groups in the Exchange admin center.</span></span>

## <a name="find-the-cmdlets-for-the-dlp-reports"></a><span data-ttu-id="fc109-146">Trovare i cmdlet per i report DLP</span><span class="sxs-lookup"><span data-stu-id="fc109-146">Find the cmdlets for the DLP reports</span></span>

<span data-ttu-id="fc109-147">Per usare la maggior parte dei cmdlet per il Centro sicurezza e conformità, è necessario:</span><span class="sxs-lookup"><span data-stu-id="fc109-147">To use most of the cmdlets for the Security &amp; Compliance Center, you need to:</span></span>
  
1. [<span data-ttu-id="fc109-148">Connessione al Centro sicurezza &amp; e conformità tramite PowerShell remoto</span><span class="sxs-lookup"><span data-stu-id="fc109-148">Connect to the Security &amp; Compliance Center using remote PowerShell</span></span>](/powershell/exchange/connect-to-scc-powershell&amp;clcid=0x409)
    
2. <span data-ttu-id="fc109-149">Utilizzare uno di questi [cmdlet del Centro sicurezza e &amp; conformità](/powershell/exchange/exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="fc109-149">Use any of these [Security &amp; Compliance Center cmdlets](/powershell/exchange/exchange-online-powershell)</span></span>
    
<span data-ttu-id="fc109-150">I report dei criteri di prevenzione della perdita dei dati devono tuttavia estrarre i dati da Office 365, incluso Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="fc109-150">However, DLP reports need pull data from across Office 365, including Exchange Online.</span></span> <span data-ttu-id="fc109-151">Per questo motivo, i cmdlet per i report DLP sono disponibili in Exchange Online PowerShell, non in PowerShell del Centro &amp; sicurezza e conformità.</span><span class="sxs-lookup"><span data-stu-id="fc109-151">For this reason, the cmdlets for the DLP reports are available in Exchange Online Powershell—not in Security &amp; Compliance Center Powershell.</span></span> <span data-ttu-id="fc109-152">Per usare i cmdlet per i report dei criteri di prevenzione della perdita dei dati, è quindi necessario:</span><span class="sxs-lookup"><span data-stu-id="fc109-152">Therefore, to use the cmdlets for the DLP reports, you need to:</span></span>
  
1. [<span data-ttu-id="fc109-153">Connettersi a Exchange Online tramite la sessione remota di PowerShell</span><span class="sxs-lookup"><span data-stu-id="fc109-153">Connect to Exchange Online using remote PowerShell</span></span>](/powershell/exchange/connect-to-exchange-online-powershell)
    
2. <span data-ttu-id="fc109-154">Usare uno di questi cmdlet per i report dei criteri di prevenzione della perdita dei dati:</span><span class="sxs-lookup"><span data-stu-id="fc109-154">Use any of these cmdlets for the DLP reports:</span></span>
    
      - [<span data-ttu-id="fc109-155">Get-DlpDetectionsReport</span><span class="sxs-lookup"><span data-stu-id="fc109-155">Get-DlpDetectionsReport</span></span>](/powershell/module/exchange/get-dlpdetectionsreport)
    
      - [<span data-ttu-id="fc109-156">Get-DlpDetailReport</span><span class="sxs-lookup"><span data-stu-id="fc109-156">Get-DlpDetailReport</span></span>](/powershell/module/exchange/get-dlpdetailreport)
