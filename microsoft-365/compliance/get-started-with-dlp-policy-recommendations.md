---
title: Introduzione alle raccomandazioni per i criteri di prevenzione della perdita dei dati
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 8/7/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Normal
description: Questa raccomandazione basata su Insight aiuta l'organizzazione a mantenere i contenuti riservati sicuri quando viene archiviato e condiviso in Office 365 informando quando si verifica una possibile lacuna nella copertura dei criteri DLP. Questo suggerimento viene visualizzato nella Home page del Centro sicurezza &amp; e conformità, se i documenti contengono uno dei primi cinque tipi più comuni di informazioni riservate ma non sono protetti da un criterio DLP.
ms.openlocfilehash: 3bbdbd230e9ae28136bcd89df46f0e9c10cb80fb
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41596353"
---
# <a name="get-started-with-dlp-policy-recommendations"></a><span data-ttu-id="85559-104">Introduzione alle raccomandazioni per i criteri di prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="85559-104">Get started with DLP policy recommendations</span></span>

<span data-ttu-id="85559-105">Questa raccomandazione basata su Insight aiuta l'organizzazione a mantenere i contenuti riservati sicuri quando viene archiviato e condiviso in Office 365 informando quando si verifica una possibile lacuna nella copertura dei criteri DLP.</span><span class="sxs-lookup"><span data-stu-id="85559-105">This insight-driven recommendation helps your organization keep sensitive content secure when it's stored and shared in Office 365 by informing you when there's a possible gap in your DLP policy coverage.</span></span> <span data-ttu-id="85559-106">Questo suggerimento viene visualizzato nella **Home** page del Centro sicurezza &amp; e conformità, se i documenti contengono uno dei primi cinque tipi più comuni di informazioni riservate, ma non sono protetti da un criterio di prevenzione della perdita di dati (DLP).</span><span class="sxs-lookup"><span data-stu-id="85559-106">You'll see this recommendation on the **Home** page of the Security &amp; Compliance Center, if your documents contain any of the top-five most common types of sensitive information but aren't protected by a data loss prevention (DLP) policy.</span></span> 
  
<span data-ttu-id="85559-107">È possibile utilizzare questo widget per creare rapidamente un criterio DLP personalizzato con un solo clic o due e, dopo aver creato questo criterio DLP, è completamente personalizzabile.</span><span class="sxs-lookup"><span data-stu-id="85559-107">You can use this widget to quickly create a customized DLP policy in just a click or two, and after you create this DLP policy, it's fully customizable.</span></span> <span data-ttu-id="85559-108">Si noti che, se la raccomandazione non viene visualizzata all'inizio, provare a fare clic su **+ altro** nella parte inferiore della sezione **consigliata per l'utente** .</span><span class="sxs-lookup"><span data-stu-id="85559-108">Note that if you don't see the recommendation at first, try clicking **+More** at the bottom of the **Recommended for you** section.</span></span> 
  
![Widget denominato informazioni riservate non protette](media/91bc04d2-6eff-4294-8b73-b2d56d26ffc4.png)
  
## <a name="create-the-recommended-dlp-policy"></a><span data-ttu-id="85559-110">Creare il criterio DLP consigliato</span><span class="sxs-lookup"><span data-stu-id="85559-110">Create the recommended DLP policy</span></span>

<span data-ttu-id="85559-111">Quando il widget Visualizza informazioni riservate non protette, scegliere **inizia** in basso per creare rapidamente un criterio DLP.</span><span class="sxs-lookup"><span data-stu-id="85559-111">When the widget shows you unprotected sensitive information, choose **Get started** at the bottom to quickly create a DLP policy.</span></span> 
  
<span data-ttu-id="85559-112">Per proteggere le informazioni riservate, questo criterio DLP:</span><span class="sxs-lookup"><span data-stu-id="85559-112">To help protect the sensitive information, this DLP policy:</span></span>
  
- <span data-ttu-id="85559-113">Rileva quando il contenuto in Exchange, SharePoint e OneDrive che contiene uno dei tipi non protetti di informazioni riservate viene condiviso con persone esterne all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="85559-113">Detects when content in Exchange, SharePoint, and OneDrive that contains one of the unprotected types of sensitive information is shared with people outside your organization.</span></span>
    
- <span data-ttu-id="85559-114">Genera report di attività dettagliati in modo che sia possibile tenere conto di elementi quali la condivisione dei contenuti con persone esterne all'organizzazione e quando sono state eseguite.</span><span class="sxs-lookup"><span data-stu-id="85559-114">Generates detailed activity reports so that you can track things like who shared the content with people outside your organization and when they did it.</span></span> <span data-ttu-id="85559-115">È possibile utilizzare i [report DLP](view-the-dlp-reports.md) e i [dati del log di controllo](search-the-audit-log-in-security-and-compliance.md) (dove **attività** = **DLP**) per visualizzare queste informazioni.</span><span class="sxs-lookup"><span data-stu-id="85559-115">You can use the [DLP reports](view-the-dlp-reports.md) and [audit log data](search-the-audit-log-in-security-and-compliance.md) (where **Activity** = **DLP**) to see this information.</span></span>
    
<span data-ttu-id="85559-116">È inoltre possibile scegliere di disporre del criterio DLP:</span><span class="sxs-lookup"><span data-stu-id="85559-116">You can also choose to have the DLP policy:</span></span>
  
- <span data-ttu-id="85559-117">Inviare un messaggio di posta indesiderata quando gli utenti condividono molte delle informazioni riservate con persone esterne all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="85559-117">Send you an incident report email when users share a lot of this sensitive information with people outside your organization.</span></span>
    
- <span data-ttu-id="85559-118">Aggiungere altri utenti al rapporto sugli incidenti di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="85559-118">Add other users to the email incident report.</span></span>
    
- <span data-ttu-id="85559-119">Mostrare un suggerimento per i criteri e inviare una notifica tramite posta elettronica agli utenti quando tentano di condividere queste informazioni riservate con persone esterne all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="85559-119">Show a policy tip and send an email notification to users when they attempt to share this sensitive information with people outside your organization.</span></span> <span data-ttu-id="85559-120">Per ulteriori informazioni su queste opzioni, vedere [inviare notifiche tramite posta elettronica e Mostra suggerimenti per i criteri DLP](use-notifications-and-policy-tips.md).</span><span class="sxs-lookup"><span data-stu-id="85559-120">For more information on these options, see [Send email notifications and show policy tips for DLP policies](use-notifications-and-policy-tips.md).</span></span>
    
<span data-ttu-id="85559-121">Se si desidera modificare queste opzioni in un secondo momento, è possibile modificare il criterio DLP dopo che è stato creato.</span><span class="sxs-lookup"><span data-stu-id="85559-121">If you want to change these options later, you can edit the DLP policy after it's created.</span></span> <span data-ttu-id="85559-122">Ad esempio, è possibile rendere il criterio più restrittivo persino bloccando la condivisione di contenuti che contengono informazioni riservate in primo luogo, vedere la sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="85559-122">For example, you can make the policy more restrictive by even blocking people from sharing content that contains sensitive information in the first place - see the next section.</span></span>
  
![Impostazioni del widget denominate informazioni riservate non protette](media/b6106cbd-1bed-4582-aaef-b678de470c9b.png)
  
## <a name="edit-the-recommended-dlp-policy"></a><span data-ttu-id="85559-124">Modificare il criterio DLP consigliato</span><span class="sxs-lookup"><span data-stu-id="85559-124">Edit the recommended DLP policy</span></span>

<span data-ttu-id="85559-125">Dopo aver utilizzato il widget per creare un criterio DLP, il criterio viene visualizzato in **prevenzione della perdita di dati** nella pagina **criteri** del &amp; Centro sicurezza e conformità.</span><span class="sxs-lookup"><span data-stu-id="85559-125">After you use the widget to create a DLP policy, the policy appears under **Data loss prevention** on the **Policy** page of the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="85559-126">Per impostazione predefinita, il criterio è denominato **criterio consigliato dal sistema per la condivisione di informazioni riservate**.</span><span class="sxs-lookup"><span data-stu-id="85559-126">By default, the policy is named **System Recommended Policy for Sharing Sensitive Information**.</span></span> <span data-ttu-id="85559-127">Questo criterio è completamente personalizzabile, lo stesso di qualsiasi criterio DLP creato da zero.</span><span class="sxs-lookup"><span data-stu-id="85559-127">This policy is fully customizable, the same as any DLP policy that you create yourself from scratch.</span></span> <span data-ttu-id="85559-128">Ad esempio, se si è deciso di non abilitare i rapporti sugli incidenti e i suggerimenti per i criteri quando è stato utilizzato il widget, è sempre possibile modificare il criterio e attivarle in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="85559-128">For example, if you decided not to turn on incident reports and policy tips when you used the widget, you can always edit the policy and turn on those options at any time.</span></span>
  
![Criteri consigliati per la condivisione di informazioni riservate](media/2fc49f25-ec25-4433-add4-d60f73888f13.png)
  
## <a name="when-the-widget-does-and-does-not-appear"></a><span data-ttu-id="85559-130">Quando il widget fa e non viene visualizzato</span><span class="sxs-lookup"><span data-stu-id="85559-130">When the widget does and does not appear</span></span>

<span data-ttu-id="85559-131">Il widget denominato **informazioni riservate non protette** viene visualizzato nella sezione **consigliata** della **Home** page del Centro sicurezza &amp; e conformità.</span><span class="sxs-lookup"><span data-stu-id="85559-131">The widget named **Unprotected Sensitive Information** appears in the **Recommended for you** section of the **Home** page of the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="85559-132">Questo widget viene visualizzato solo quando:</span><span class="sxs-lookup"><span data-stu-id="85559-132">This widget appears only when:</span></span>
  
- <span data-ttu-id="85559-133">I nuovi documenti contenenti uno dei cinque tipi più comuni di informazioni riservate sono stati rilevati in SharePoint o OneDrive negli ultimi 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="85559-133">New documents containing any of the five most common types of sensitive information are detected in SharePoint or OneDrive over the past 30 days.</span></span>
    
- <span data-ttu-id="85559-134">Le informazioni riservate non sono già protette da un criterio DLP esistente.</span><span class="sxs-lookup"><span data-stu-id="85559-134">That sensitive information is not already protected by an existing DLP policy.</span></span>
    
<span data-ttu-id="85559-135">A differenza dei criteri DLP che analizzano costantemente i dati, questa raccomandazione consente di analizzare gli spazi vuoti nella copertura del criterio DLP all'incirca ogni 48 ore, quindi dopo che è stato caricato il nuovo contenuto, potrebbero essere necessari fino a due giorni prima che venga visualizzata la raccomandazione.</span><span class="sxs-lookup"><span data-stu-id="85559-135">Unlike DLP policies that are constantly scanning your data, this recommendation scans for gaps in your DLP policy coverage roughly every 48 hours, so after new content is uploaded, it may take up to two days for the recommendation to appear.</span></span>
  
<span data-ttu-id="85559-136">Infine, dopo aver utilizzato il widget per creare un criterio DLP consigliato, il widget scompare dalla **Home** page.</span><span class="sxs-lookup"><span data-stu-id="85559-136">Finally, after you use the widget to create a recommended DLP policy, the widget disappears from the **Home** page.</span></span> 
  

