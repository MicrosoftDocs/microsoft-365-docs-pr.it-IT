---
title: Introduzione ai criteri di prevenzione della perdita dei dati predefiniti
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
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
ms.custom:
- seo-marvel-apr2020
description: Informazioni su come utilizzare il report per affinare i criteri di prevenzione della perdita dei dati predefiniti dell'organizzazione.
ms.openlocfilehash: 98f2a95d66860695034fa958969d1c195e9d58be
ms.sourcegitcommit: 8c698d1a0c41baf5f35d07b0d765b4a5ead593d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/13/2021
ms.locfileid: "53408961"
---
# <a name="get-started-with-the-default-dlp-policy"></a><span data-ttu-id="0d4ce-103">Introduzione ai criteri di prevenzione della perdita dei dati predefiniti</span><span class="sxs-lookup"><span data-stu-id="0d4ce-103">Get started with the default DLP policy</span></span>

<span data-ttu-id="0d4ce-104">Prima di creare il primo criterio di prevenzione della perdita dei dati (DLP), DLP contribuisce a proteggere le informazioni riservate con un criterio predefinito.</span><span class="sxs-lookup"><span data-stu-id="0d4ce-104">Before you even create your first data loss prevention (DLP) policy, DLP is helping to protect your sensitive information with a default policy.</span></span> <span data-ttu-id="0d4ce-105">Questo criterio predefinito e il relativo suggerimento (mostrato di seguito) consentono di proteggere i contenuti sensibili inviando una notifica quando i messaggi di posta elettronica o i documenti contenenti un numero di carta di credito sono stati condivisi con un utente esterno all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="0d4ce-105">This default policy and its recommendation (shown below) help keep your sensitive content secure by notifying you when email or documents containing a credit card number were shared with someone outside your organization.</span></span> <span data-ttu-id="0d4ce-106">Questo suggerimento verrà visualizzato nella **home** page del Centro &amp; sicurezza e conformità.</span><span class="sxs-lookup"><span data-stu-id="0d4ce-106">You'll see this recommendation on the **Home** page of the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="0d4ce-107">Puoi usare questo widget per visualizzare rapidamente quando e quanti dati sensibili sono stati condivisi e quindi perfezionare il criterio DLP predefinito con uno o due clic.</span><span class="sxs-lookup"><span data-stu-id="0d4ce-107">You can use this widget to quickly view when and how much sensitive information was shared, and then refine the default DLP policy in just a click or two.</span></span> <span data-ttu-id="0d4ce-108">È inoltre possibile modificare il criterio DLP predefinito in qualsiasi momento perché è completamente personalizzabile.</span><span class="sxs-lookup"><span data-stu-id="0d4ce-108">You can also edit the default DLP policy at any time because it's fully customizable.</span></span> <span data-ttu-id="0d4ce-109">Tieni presente che se non vedi il suggerimento in un primo momento, prova a fare clic **su +Altro** nella parte inferiore della **sezione Consigliato per te.**</span><span class="sxs-lookup"><span data-stu-id="0d4ce-109">Note that if you don't see the recommendation at first, try clicking **+More** at the bottom of the **Recommended for you** section.</span></span> 
  
![Widget denominato Proteggere ulteriormente il contenuto condiviso](../media/2bae6dbc-cc92-4f35-b54c-c36e60226b5b.png)
  
## <a name="view-the-report-and-refine-the-default-dlp-policy"></a><span data-ttu-id="0d4ce-111">Visualizzare il report e perfezionare il criterio DLP predefinito</span><span class="sxs-lookup"><span data-stu-id="0d4ce-111">View the report and refine the default DLP policy</span></span>

<span data-ttu-id="0d4ce-112">Quando il widget mostra che gli utenti hanno condiviso informazioni riservate con persone esterne all'organizzazione, scegliere **Affina** criterio DLP nella parte inferiore.</span><span class="sxs-lookup"><span data-stu-id="0d4ce-112">When the widget shows you that users have shared sensitive information with people outside your organization, choose **Refine DLP policy** at the bottom.</span></span> 
  
<span data-ttu-id="0d4ce-113">Il report dettagliato mostra quando e quanti contenuti contenenti numeri di carta di credito sono stati condivisi negli ultimi 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="0d4ce-113">The detailed report shows you when and how much content containing credit card numbers was shared in the past 30 days.</span></span> <span data-ttu-id="0d4ce-114">Tieni presente che le corrispondenze delle regole possono richiedere fino a 48 ore per essere mostrate nel widget.</span><span class="sxs-lookup"><span data-stu-id="0d4ce-114">Note that rule matches can take up to 48 hours to show up in the widget.</span></span>
  
<span data-ttu-id="0d4ce-115">Per proteggere le informazioni riservate, il criterio DLP predefinito:</span><span class="sxs-lookup"><span data-stu-id="0d4ce-115">To help protect the sensitive information, the default DLP policy:</span></span>
  
- <span data-ttu-id="0d4ce-116">Rileva quando il contenuto in Exchange, SharePoint e OneDrive che contiene almeno un numero di carta di credito viene condiviso con persone esterne all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="0d4ce-116">Detects when content in Exchange, SharePoint, and OneDrive that contains at least one credit card number is shared with people outside your organization.</span></span>
    
- <span data-ttu-id="0d4ce-117">Mostra un suggerimento per i criteri e invia una notifica tramite posta elettronica agli utenti quando tentano di condividere queste informazioni riservate con persone esterne all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="0d4ce-117">Shows a policy tip and sends an email notification to users when they attempt to share this sensitive information with people outside your organization.</span></span> <span data-ttu-id="0d4ce-118">Per ulteriori informazioni su queste opzioni, vedere [Send email notifications and show policy tips for DLP policies.](use-notifications-and-policy-tips.md)</span><span class="sxs-lookup"><span data-stu-id="0d4ce-118">For more information on these options, see [Send email notifications and show policy tips for DLP policies](use-notifications-and-policy-tips.md).</span></span>
    
- <span data-ttu-id="0d4ce-119">Genera report dettagliati sulle attività in modo da poter tenere traccia di elementi come chi ha condiviso il contenuto con persone esterne all'organizzazione e quando lo ha fatto.</span><span class="sxs-lookup"><span data-stu-id="0d4ce-119">Generates detailed activity reports so that you can track things like who shared the content with people outside your organization and when they did it.</span></span> <span data-ttu-id="0d4ce-120">È possibile utilizzare i report [DLP e](view-the-dlp-reports.md) i [dati del registro di](search-the-audit-log-in-security-and-compliance.md) controllo (dove **DLP**  =  **attività**) per visualizzare queste informazioni.</span><span class="sxs-lookup"><span data-stu-id="0d4ce-120">You can use the [DLP reports](view-the-dlp-reports.md) and [audit log data](search-the-audit-log-in-security-and-compliance.md) (where **Activity** = **DLP**) to see this information.</span></span>
    
<span data-ttu-id="0d4ce-121">Per affinare rapidamente il criterio DLP predefinito, è possibile scegliere di farlo:</span><span class="sxs-lookup"><span data-stu-id="0d4ce-121">To quickly refine the default DLP policy, you can choose to have it:</span></span>
  
- <span data-ttu-id="0d4ce-122">Inviare un messaggio di posta elettronica di segnalazione degli eventi imprevisti quando gli utenti condividono queste informazioni riservate con persone esterne all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="0d4ce-122">Send you an incident report email when users share this sensitive information with people outside your organization.</span></span>
    
- <span data-ttu-id="0d4ce-123">Aggiungere altri utenti al rapporto operazioni non consentite tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="0d4ce-123">Add other users to the email incident report.</span></span>
    
- <span data-ttu-id="0d4ce-124">Blocca l'accesso al contenuto contenente le informazioni riservate, ma consenti all'utente di eseguire l'override e condividere o inviare, se necessario.</span><span class="sxs-lookup"><span data-stu-id="0d4ce-124">Block access to the content containing the sensitive information, but allow the user to override and share or send if they need to.</span></span>
    
<span data-ttu-id="0d4ce-125">Per ulteriori informazioni sui report degli eventi imprevisti o sulla limitazione dell'accesso, vedere [Informazioni di riferimento sulla prevenzione della perdita di dati.](data-loss-prevention-policies.md)</span><span class="sxs-lookup"><span data-stu-id="0d4ce-125">For more information on incident reports or restricting access, see [Data loss prevention reference](data-loss-prevention-policies.md).</span></span>
  
<span data-ttu-id="0d4ce-126">Se si desidera modificare queste opzioni in un secondo momento, è possibile modificare il criterio DLP predefinito in qualsiasi momento- vedere la sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="0d4ce-126">If you want to change these options later, you can edit the default DLP policy at any time - see the next section.</span></span>
  
![Impostazioni per il widget denominato Proteggere ulteriormente il contenuto condiviso](../media/dad30a84-2715-4c0a-a5c5-44d85492363e.png)
  
## <a name="edit-the-default-dlp-policy"></a><span data-ttu-id="0d4ce-128">Modificare il criterio DLP predefinito</span><span class="sxs-lookup"><span data-stu-id="0d4ce-128">Edit the default DLP policy</span></span>

<span data-ttu-id="0d4ce-129">Questo criterio è denominato **Criterio DLP predefinito** e viene visualizzato in Prevenzione della **perdita** dei dati nella **pagina** Criteri del Centro sicurezza &amp; e conformità.</span><span class="sxs-lookup"><span data-stu-id="0d4ce-129">This policy is named **Default DLP policy** and appears under **Data loss prevention** on the **Policy** page of the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="0d4ce-130">Questo criterio è completamente personalizzabile, come qualsiasi criterio DLP creato da zero.</span><span class="sxs-lookup"><span data-stu-id="0d4ce-130">This policy is fully customizable, the same as any DLP policy that you create yourself from scratch.</span></span> <span data-ttu-id="0d4ce-131">Puoi anche disattivare o eliminare il criterio, in modo che gli utenti non ricevano più suggerimenti per i criteri o notifiche tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="0d4ce-131">You can also turn off or delete the policy, so that your users no longer receive policy tips or email notifications.</span></span>
  
![Criterio DLP denominato Criterio DLP predefinito](../media/260731e8-4d57-4c98-abec-07b052ec48d5.png)
  
## <a name="when-the-widget-does-and-does-not-appear"></a><span data-ttu-id="0d4ce-133">Quando il widget viene visualizzato e non viene visualizzato</span><span class="sxs-lookup"><span data-stu-id="0d4ce-133">When the widget does and does not appear</span></span>

<span data-ttu-id="0d4ce-134">Il widget denominato **Protezione ulteriore contenuto condiviso** viene visualizzato nella sezione Consigliato per **l'utente** della **home** page del Centro sicurezza &amp; e conformità.</span><span class="sxs-lookup"><span data-stu-id="0d4ce-134">The widget named **Further protect shared content** appears in the **Recommended for you** section of the **Home** page of the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="0d4ce-135">Questo widget viene visualizzato solo quando:</span><span class="sxs-lookup"><span data-stu-id="0d4ce-135">This widget appears only when:</span></span>
  
- <span data-ttu-id="0d4ce-136">Non esistono criteri di prevenzione della perdita di dati nel Centro sicurezza e conformità &amp; o nell Exchange intervanza di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="0d4ce-136">There are no data loss prevention policies in the Security &amp; Compliance Center or Exchange admin center.</span></span> <span data-ttu-id="0d4ce-137">Questo widget ha lo scopo di aiutarti a iniziare a usare DLP, in modo che non venga visualizzato se hai già criteri DLP.</span><span class="sxs-lookup"><span data-stu-id="0d4ce-137">This widget is intended to help you get started with DLP, so it doesn't appear if you already have DLP policies.</span></span>
    
- <span data-ttu-id="0d4ce-138">Il contenuto contenente almeno una carta di credito è stato condiviso con un utente esterno all'organizzazione negli ultimi 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="0d4ce-138">Content containing least one credit card has been shared with someone outside your organization in the past 30 days.</span></span>
    
<span data-ttu-id="0d4ce-139">Tieni presente che le corrispondenze delle regole possono richiedere fino a 48 ore per essere disponibili per il widget, quindi dopo aver rilevato le informazioni riservate condivise esternamente, potrebbero essere necessarie fino a due giorni per la visualizzazione del suggerimento.</span><span class="sxs-lookup"><span data-stu-id="0d4ce-139">Note that rule matches can take up to 48 hours to be available to the widget, so after sensitive information shared externally is detected, it may take up to two days for the recommendation to appear.</span></span>
  
<span data-ttu-id="0d4ce-140">Infine, dopo aver utilizzato il widget per affinare il criterio DLP predefinito, il widget scompare dalla **home** page.</span><span class="sxs-lookup"><span data-stu-id="0d4ce-140">Finally, after you use the widget to refine the default DLP policy, the widget disappears from the **Home** page.</span></span> 
  

