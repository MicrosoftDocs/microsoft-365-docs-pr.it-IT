---
title: Livello di probabilità di posta indesiderata
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori possono ottenere informazioni sul livello di probabilità di posta indesiderata applicato ai messaggi in Exchange Online Protection (EOP).
ms.openlocfilehash: fbd892b0171cee71f516d7ca3b26b91da664af79
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202234"
---
# <a name="spam-confidence-level-scl-in-eop"></a><span data-ttu-id="9c1e8-103">Livello di probabilità di posta indesiderata (SCL) in EOP</span><span class="sxs-lookup"><span data-stu-id="9c1e8-103">Spam confidence level (SCL) in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="9c1e8-104">In Microsoft 365 organizzazioni con cassette postali in Exchange Online o in organizzazioni Exchange Online Protection (EOP) senza cassette postali di Exchange Online, i messaggi in ingresso passano attraverso il filtro posta indesiderata in EOP e vengono assegnati un punteggio di posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="9c1e8-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound messages go through spam filtering in EOP and are assigned a spam score.</span></span> <span data-ttu-id="9c1e8-105">Tale punteggio viene mappato a un singolo livello di probabilità di posta indesiderata (SCL) aggiunto al messaggio in un X-header.</span><span class="sxs-lookup"><span data-stu-id="9c1e8-105">That score is mapped to an individual spam confidence level (SCL) that's added to the message in an X-header.</span></span> <span data-ttu-id="9c1e8-106">Un livello SCL superiore indica che un messaggio è più probabile che sia posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="9c1e8-106">A higher SCL indicates a message is more likely to be spam.</span></span> <span data-ttu-id="9c1e8-107">EOP esegue un'azione sul messaggio in base al livello SCL.</span><span class="sxs-lookup"><span data-stu-id="9c1e8-107">EOP takes action on the message based on the SCL.</span></span>

<span data-ttu-id="9c1e8-108">La modalità SCL e le azioni predefinite eseguite nei messaggi sono descritte nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="9c1e8-108">What the SCL means and the default actions that are taken on messages are described in the following table.</span></span> <span data-ttu-id="9c1e8-109">Per ulteriori informazioni sulle azioni che è possibile eseguire sui messaggi in base al verdetto del filtro della posta indesiderata, vedere [Configure anti-spam Policies in EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="9c1e8-109">For more information about actions you can take on messages based on the spam filtering verdict, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

****

|<span data-ttu-id="9c1e8-110">SCL</span><span class="sxs-lookup"><span data-stu-id="9c1e8-110">SCL</span></span>|<span data-ttu-id="9c1e8-111">Definizione</span><span class="sxs-lookup"><span data-stu-id="9c1e8-111">Definition</span></span>|<span data-ttu-id="9c1e8-112">Azione predefinita</span><span class="sxs-lookup"><span data-stu-id="9c1e8-112">Default action</span></span>|
|:---:|---|---|
|<span data-ttu-id="9c1e8-113">-1</span><span class="sxs-lookup"><span data-stu-id="9c1e8-113">-1</span></span>|<span data-ttu-id="9c1e8-114">Il messaggio ha ignorato il filtro della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="9c1e8-114">The message skipped spam filtering.</span></span> <span data-ttu-id="9c1e8-115">Ad esempio, il messaggio è proveniente da un mittente sicuro, è stato inviato a un destinatario sicuro oppure è da un server di origine posta elettronica nell'elenco indirizzi IP consentiti.</span><span class="sxs-lookup"><span data-stu-id="9c1e8-115">For example, the message is from a safe sender, was sent to a safe recipient, or is from an email source server on the IP Allow List.</span></span> <span data-ttu-id="9c1e8-116">Per ulteriori informazioni, vedere [creare elenchi di mittenti attendibili in EOP](create-safe-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="9c1e8-116">For more information, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>|<span data-ttu-id="9c1e8-117">Recapito del messaggio nella Posta in arrivo del destinatario.</span><span class="sxs-lookup"><span data-stu-id="9c1e8-117">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="9c1e8-118">0, 1</span><span class="sxs-lookup"><span data-stu-id="9c1e8-118">0, 1</span></span>|<span data-ttu-id="9c1e8-119">Filtro posta indesiderata determinato il messaggio non era posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="9c1e8-119">Spam filtering determined the message was not spam.</span></span>|<span data-ttu-id="9c1e8-120">Recapito del messaggio nella Posta in arrivo del destinatario.</span><span class="sxs-lookup"><span data-stu-id="9c1e8-120">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="9c1e8-121">5, 6</span><span class="sxs-lookup"><span data-stu-id="9c1e8-121">5, 6</span></span>|<span data-ttu-id="9c1e8-122">Filtro posta indesiderata contrassegnata come **posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="9c1e8-122">Spam filtering marked the message as **Spam**</span></span>|<span data-ttu-id="9c1e8-123">Recapito del messaggio nella cartella Posta indesiderata del destinatario</span><span class="sxs-lookup"><span data-stu-id="9c1e8-123">Deliver the message to the recipients' Junk Email folder.</span></span>|
|<span data-ttu-id="9c1e8-124">9 </span><span class="sxs-lookup"><span data-stu-id="9c1e8-124">9</span></span>|<span data-ttu-id="9c1e8-125">Filtro posta indesiderata contrassegnata come **posta indesiderata con elevata sicurezza**</span><span class="sxs-lookup"><span data-stu-id="9c1e8-125">Spam filtering marked the message as **High confidence spam**</span></span>|<span data-ttu-id="9c1e8-126">Recapito del messaggio nella cartella Posta indesiderata del destinatario</span><span class="sxs-lookup"><span data-stu-id="9c1e8-126">Deliver the message to the recipients' Junk Email folder.</span></span>|
|

<span data-ttu-id="9c1e8-127">Si noterà che SCL 2, 3, 4, 7 e 8 non vengono utilizzati dal filtro per la posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="9c1e8-127">You'll notice that SCL 2, 3, 4, 7, and 8 aren't used by spam filtering.</span></span>

<span data-ttu-id="9c1e8-128">È possibile utilizzare le regole del flusso di posta (note anche come regole di trasporto) per contrassegnare il livello SCL nei messaggi.</span><span class="sxs-lookup"><span data-stu-id="9c1e8-128">You can use mail flow rules (also known as transport rules) to stamp the SCL on messages.</span></span> <span data-ttu-id="9c1e8-129">Se si utilizza una regola del flusso di posta per impostare SCL, i valori 5 o 6 attivano l'azione del filtro posta indesiderata per la **posta indesiderata**e i valori 7, 8 o 9 attivano l'azione del filtro posta indesiderata per la posta indesiderata **elevata**.</span><span class="sxs-lookup"><span data-stu-id="9c1e8-129">If you use a mail flow rule to set the SCL, the values 5 or 6 trigger the spam filtering action for **Spam**, and the values 7, 8, or 9 trigger the spam filtering action for **High confidence spam**.</span></span> <span data-ttu-id="9c1e8-130">Per ulteriori informazioni, vedere [Use Mail Flow Rules to impostare il livello di probabilità di posta indesiderata (SCL) nei messaggi](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span><span class="sxs-lookup"><span data-stu-id="9c1e8-130">For more information, see [Use mail flow rules to set the spam confidence level (SCL) in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span></span>

<span data-ttu-id="9c1e8-131">Analogamente a SCL, il livello di reclamo in blocco (BCL) identifica la posta elettronica di massa non valida (nota anche come _posta grigia_).</span><span class="sxs-lookup"><span data-stu-id="9c1e8-131">Similar to the SCL, the bulk complaint level (BCL) identifies bad bulk email (also known as _gray mail_).</span></span> <span data-ttu-id="9c1e8-132">Più il BCL è elevato, maggiore è la probabilità che un messaggio di posta elettronica in blocco generi reclami, ed è quindi più probabile che si tratti di posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="9c1e8-132">A higher BCL indicates a bulk mail message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="9c1e8-133">È possibile configurare la soglia BCL nei criteri di protezione da posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="9c1e8-133">You configure the BCL threshold in anti-spam policies.</span></span> <span data-ttu-id="9c1e8-134">Per ulteriori informazioni, vedere [configurare i criteri di protezione dalla posta indesiderata in EOP](configure-your-spam-filter-policies.md), [livello di reclamo in blocco (BCL) in EOP)](bulk-complaint-level-values.md)e [Qual è la differenza tra posta elettronica indesiderata e posta elettronica in blocco?](what-s-the-difference-between-junk-email-and-bulk-email.md).</span><span class="sxs-lookup"><span data-stu-id="9c1e8-134">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md), [Bulk complaint level (BCL) in EOP)](bulk-complaint-level-values.md), and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md).</span></span>

|<!-- -->|
|---|
|<span data-ttu-id="9c1e8-135">![L'icona breve per LinkedIn Learning ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Microsoft 365?**</span><span class="sxs-lookup"><span data-stu-id="9c1e8-135">![The short icon for LinkedIn Learning](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Microsoft 365?**</span></span> <span data-ttu-id="9c1e8-136">Scopri i corsi video gratuiti per **Microsoft 365 Admins e professionisti it**, offerti da LinkedIn Learning.</span><span class="sxs-lookup"><span data-stu-id="9c1e8-136">Discover free video courses for **Microsoft 365 admins and IT pros**, brought to you by LinkedIn Learning.</span></span>|
