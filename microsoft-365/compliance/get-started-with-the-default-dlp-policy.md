---
title: Introduzione ai criteri di prevenzione della perdita dei dati predefiniti
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 8/10/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: e0ada764-6422-4b44-9472-513bed04837b
ms.collection:
- M365-security-compliance
description: Prima di creare anche il primo criterio di prevenzione della perdita di dati (DLP), DLP contribuisce a proteggere le informazioni riservate con un criterio predefinito. Questo criterio predefinito e il relativo suggerimento (illustrato di seguito) consentono di mantenere la sicurezza del contenuto riservato notificando quando la posta elettronica o i documenti contenenti un numero di carta di credito sono stati condivisi con un utente esterno all'organizzazione.
ms.openlocfilehash: d24848e5956a6e8927307d3102f4ce31f1187bfd
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637830"
---
# <a name="get-started-with-the-default-dlp-policy"></a><span data-ttu-id="4c858-104">Introduzione ai criteri di prevenzione della perdita dei dati predefiniti</span><span class="sxs-lookup"><span data-stu-id="4c858-104">Get started with the default DLP policy</span></span>

<span data-ttu-id="4c858-105">Prima di creare anche il primo criterio di prevenzione della perdita di dati (DLP), DLP contribuisce a proteggere le informazioni riservate con un criterio predefinito.</span><span class="sxs-lookup"><span data-stu-id="4c858-105">Before you even create your first data loss prevention (DLP) policy, DLP is helping to protect your sensitive information with a default policy.</span></span> <span data-ttu-id="4c858-106">Questo criterio predefinito e il relativo suggerimento (illustrato di seguito) consentono di mantenere la sicurezza del contenuto riservato notificando quando la posta elettronica o i documenti contenenti un numero di carta di credito sono stati condivisi con un utente esterno all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4c858-106">This default policy and its recommendation (shown below) help keep your sensitive content secure by notifying you when email or documents containing a credit card number were shared with someone outside your organization.</span></span> <span data-ttu-id="4c858-107">Questo suggerimento viene visualizzato nella **Home** page del Centro sicurezza &amp; e conformità.</span><span class="sxs-lookup"><span data-stu-id="4c858-107">You'll see this recommendation on the **Home** page of the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="4c858-108">È possibile utilizzare questo widget per visualizzare rapidamente la condivisione e la quantità di informazioni riservate, quindi affinare il criterio DLP predefinito in un solo clic o due.</span><span class="sxs-lookup"><span data-stu-id="4c858-108">You can use this widget to quickly view when and how much sensitive information was shared, and then refine the default DLP policy in just a click or two.</span></span> <span data-ttu-id="4c858-109">È inoltre possibile modificare il criterio DLP predefinito in qualsiasi momento perché è completamente personalizzabile.</span><span class="sxs-lookup"><span data-stu-id="4c858-109">You can also edit the default DLP policy at any time because it's fully customizable.</span></span> <span data-ttu-id="4c858-110">Si noti che, se la raccomandazione non viene visualizzata all'inizio, provare a fare clic su **+ altro** nella parte inferiore della sezione **consigliata per l'utente** .</span><span class="sxs-lookup"><span data-stu-id="4c858-110">Note that if you don't see the recommendation at first, try clicking **+More** at the bottom of the **Recommended for you** section.</span></span> 
  
![Widget denominato ulteriore protezione del contenuto condiviso](../media/2bae6dbc-cc92-4f35-b54c-c36e60226b5b.png)
  
## <a name="view-the-report-and-refine-the-default-dlp-policy"></a><span data-ttu-id="4c858-112">Visualizzazione del report e affinamento del criterio DLP predefinito</span><span class="sxs-lookup"><span data-stu-id="4c858-112">View the report and refine the default DLP policy</span></span>

<span data-ttu-id="4c858-113">Quando il widget indica che gli utenti hanno condiviso informazioni riservate con persone esterne all'organizzazione, scegliere **affina i criteri DLP** nella parte inferiore.</span><span class="sxs-lookup"><span data-stu-id="4c858-113">When the widget shows you that users have shared sensitive information with people outside your organization, choose **Refine DLP policy** at the bottom.</span></span> 
  
<span data-ttu-id="4c858-114">Il rapporto dettagliato indica quando e quanto contenuto contenente i numeri di carta di credito è stato condiviso negli ultimi 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="4c858-114">The detailed report shows you when and how much content containing credit card numbers was shared in the past 30 days.</span></span> <span data-ttu-id="4c858-115">Si noti che le corrispondenze delle regole possono richiedere fino a 48 ore per essere visualizzate nel widget.</span><span class="sxs-lookup"><span data-stu-id="4c858-115">Note that rule matches can take up to 48 hours to show up in the widget.</span></span>
  
<span data-ttu-id="4c858-116">Per proteggere le informazioni riservate, il criterio DLP predefinito:</span><span class="sxs-lookup"><span data-stu-id="4c858-116">To help protect the sensitive information, the default DLP policy:</span></span>
  
- <span data-ttu-id="4c858-117">Rileva quando il contenuto in Exchange, SharePoint e OneDrive che contiene almeno un numero di carta di credito viene condiviso con persone esterne all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4c858-117">Detects when content in Exchange, SharePoint, and OneDrive that contains at least one credit card number is shared with people outside your organization.</span></span>
    
- <span data-ttu-id="4c858-118">Visualizza un suggerimento per i criteri e invia una notifica tramite posta elettronica agli utenti quando tentano di condividere queste informazioni riservate con persone esterne all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4c858-118">Shows a policy tip and sends an email notification to users when they attempt to share this sensitive information with people outside your organization.</span></span> <span data-ttu-id="4c858-119">Per ulteriori informazioni su queste opzioni, vedere [inviare notifiche tramite posta elettronica e Mostra suggerimenti per i criteri DLP](use-notifications-and-policy-tips.md).</span><span class="sxs-lookup"><span data-stu-id="4c858-119">For more information on these options, see [Send email notifications and show policy tips for DLP policies](use-notifications-and-policy-tips.md).</span></span>
    
- <span data-ttu-id="4c858-120">Genera report di attività dettagliati in modo che sia possibile tenere conto di elementi quali la condivisione dei contenuti con persone esterne all'organizzazione e quando sono state eseguite.</span><span class="sxs-lookup"><span data-stu-id="4c858-120">Generates detailed activity reports so that you can track things like who shared the content with people outside your organization and when they did it.</span></span> <span data-ttu-id="4c858-121">È possibile utilizzare i [report DLP](view-the-dlp-reports.md) e i [dati del log di controllo](search-the-audit-log-in-security-and-compliance.md) (dove **attività** = **DLP**) per visualizzare queste informazioni.</span><span class="sxs-lookup"><span data-stu-id="4c858-121">You can use the [DLP reports](view-the-dlp-reports.md) and [audit log data](search-the-audit-log-in-security-and-compliance.md) (where **Activity** = **DLP**) to see this information.</span></span>
    
<span data-ttu-id="4c858-122">Per affinare rapidamente il criterio DLP predefinito, è possibile sceglierlo:</span><span class="sxs-lookup"><span data-stu-id="4c858-122">To quickly refine the default DLP policy, you can choose to have it:</span></span>
  
- <span data-ttu-id="4c858-123">Inviare un messaggio di posta indesiderata quando gli utenti condividono queste informazioni riservate con persone esterne all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4c858-123">Send you an incident report email when users share this sensitive information with people outside your organization.</span></span>
    
- <span data-ttu-id="4c858-124">Aggiungere altri utenti al rapporto sugli incidenti di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="4c858-124">Add other users to the email incident report.</span></span>
    
- <span data-ttu-id="4c858-125">Blocca l'accesso al contenuto contenente le informazioni riservate, ma Consenti all'utente di eseguire l'override e la condivisione o l'invio, se necessario.</span><span class="sxs-lookup"><span data-stu-id="4c858-125">Block access to the content containing the sensitive information, but allow the user to override and share or send if they need to.</span></span>
    
<span data-ttu-id="4c858-126">Per ulteriori informazioni sui rapporti sugli incidenti o la limitazione dell'accesso, vedere [Panoramica dei criteri di prevenzione della perdita di dati](data-loss-prevention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="4c858-126">For more information on incident reports or restricting access, see [Overview of data loss prevention policies](data-loss-prevention-policies.md).</span></span>
  
<span data-ttu-id="4c858-127">Se si desidera modificare queste opzioni in un secondo momento, è possibile modificare il criterio DLP predefinito in qualsiasi ora, vedere la sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="4c858-127">If you want to change these options later, you can edit the default DLP policy at any time - see the next section.</span></span>
  
![Impostazioni per widget denominato ulteriore protezione del contenuto condiviso](../media/dad30a84-2715-4c0a-a5c5-44d85492363e.png)
  
## <a name="edit-the-default-dlp-policy"></a><span data-ttu-id="4c858-129">Modificare il criterio DLP predefinito</span><span class="sxs-lookup"><span data-stu-id="4c858-129">Edit the default DLP policy</span></span>

<span data-ttu-id="4c858-130">Questo criterio è denominato **criterio DLP predefinito** e viene visualizzato in **prevenzione della perdita di dati** nella pagina **criteri** del &amp; Centro sicurezza e conformità.</span><span class="sxs-lookup"><span data-stu-id="4c858-130">This policy is named **Default DLP policy** and appears under **Data loss prevention** on the **Policy** page of the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="4c858-131">Questo criterio è completamente personalizzabile, lo stesso di qualsiasi criterio DLP creato da zero.</span><span class="sxs-lookup"><span data-stu-id="4c858-131">This policy is fully customizable, the same as any DLP policy that you create yourself from scratch.</span></span> <span data-ttu-id="4c858-132">È anche possibile disattivare o eliminare il criterio, in modo che gli utenti non ricevano più suggerimenti per i criteri o notifiche tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="4c858-132">You can also turn off or delete the policy, so that your users no longer receive policy tips or email notifications.</span></span>
  
![Criterio DLP denominato criterio DLP predefinito](../media/260731e8-4d57-4c98-abec-07b052ec48d5.png)
  
## <a name="when-the-widget-does-and-does-not-appear"></a><span data-ttu-id="4c858-134">Quando il widget fa e non viene visualizzato</span><span class="sxs-lookup"><span data-stu-id="4c858-134">When the widget does and does not appear</span></span>

<span data-ttu-id="4c858-135">Il widget denominato **ulteriore protezione contenuto condiviso** viene visualizzato nella sezione **consigliata per l'utente** della **Home** page del centro &amp; sicurezza e conformità.</span><span class="sxs-lookup"><span data-stu-id="4c858-135">The widget named **Further protect shared content** appears in the **Recommended for you** section of the **Home** page of the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="4c858-136">Questo widget viene visualizzato solo quando:</span><span class="sxs-lookup"><span data-stu-id="4c858-136">This widget appears only when:</span></span>
  
- <span data-ttu-id="4c858-137">Non esistono criteri di prevenzione della perdita di dati nel &amp; Centro sicurezza o nell'interfaccia di amministrazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="4c858-137">There are no data loss prevention policies in the Security &amp; Compliance Center or Exchange admin center.</span></span> <span data-ttu-id="4c858-138">Questo widget ha lo scopo di iniziare a utilizzare DLP, in modo che non venga visualizzato se si dispone già di criteri DLP.</span><span class="sxs-lookup"><span data-stu-id="4c858-138">This widget is intended to help you get started with DLP, so it doesn't appear if you already have DLP policies.</span></span>
    
- <span data-ttu-id="4c858-139">I contenuti contenenti almeno una carta di credito sono stati condivisi con un utente esterno all'organizzazione negli ultimi 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="4c858-139">Content containing least one credit card has been shared with someone outside your organization in the past 30 days.</span></span>
    
<span data-ttu-id="4c858-140">Si noti che le corrispondenze delle regole possono richiedere fino a 48 ore per essere disponibili per il widget, quindi dopo che le informazioni riservate condivise esternamente vengono rilevate, potrebbero essere necessari fino a due giorni affinché venga visualizzata la raccomandazione.</span><span class="sxs-lookup"><span data-stu-id="4c858-140">Note that rule matches can take up to 48 hours to be available to the widget, so after sensitive information shared externally is detected, it may take up to two days for the recommendation to appear.</span></span>
  
<span data-ttu-id="4c858-141">Infine, dopo aver utilizzato il widget per affinare il criterio DLP predefinito, il widget scompare dalla **Home** page.</span><span class="sxs-lookup"><span data-stu-id="4c858-141">Finally, after you use the widget to refine the default DLP policy, the widget disappears from the **Home** page.</span></span> 
  

