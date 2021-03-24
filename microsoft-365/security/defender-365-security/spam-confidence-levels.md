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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori possono conoscere il livello di probabilità di posta indesiderata (SCL) applicato ai messaggi in Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 951bbcb5fcbcc7b7916ee1c34c4ab489d54b6667
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064458"
---
# <a name="spam-confidence-level-scl-in-eop"></a><span data-ttu-id="286a7-103">Livello di probabilità di posta indesiderata (SCL) in EOP</span><span class="sxs-lookup"><span data-stu-id="286a7-103">Spam confidence level (SCL) in EOP</span></span>

<span data-ttu-id="286a7-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="286a7-104">**Applies to**</span></span>
- [<span data-ttu-id="286a7-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="286a7-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="286a7-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="286a7-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="286a7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="286a7-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="286a7-108">Nelle organizzazioni di Microsoft 365 con cassette postali in Exchange Online o in organizzazioni autonome di Exchange Online Protection (EOP) senza cassette postali di Exchange Online, i messaggi in ingresso passano attraverso il filtro della posta indesiderata in EOP e vengono assegnati un punteggio di posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="286a7-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound messages go through spam filtering in EOP and are assigned a spam score.</span></span> <span data-ttu-id="286a7-109">Tale punteggio viene mappato a un singolo livello di probabilità di posta indesiderata (SCL) che viene aggiunto al messaggio in un X-header.</span><span class="sxs-lookup"><span data-stu-id="286a7-109">That score is mapped to an individual spam confidence level (SCL) that's added to the message in an X-header.</span></span> <span data-ttu-id="286a7-110">Un livello di probabilità di posta indesiderata più alto indica che è più probabile che un messaggio sia posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="286a7-110">A higher SCL indicates a message is more likely to be spam.</span></span> <span data-ttu-id="286a7-111">EOP adotta un'azione sul messaggio in base al SCL.</span><span class="sxs-lookup"><span data-stu-id="286a7-111">EOP takes action on the message based on the SCL.</span></span>

<span data-ttu-id="286a7-112">Il significato del livello di probabilità di posta elettronica (SCL) e le azioni predefinite eseguite sui messaggi sono descritti nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="286a7-112">What the SCL means and the default actions that are taken on messages are described in the following table.</span></span> <span data-ttu-id="286a7-113">Per ulteriori informazioni sulle azioni che è possibile eseguire sui messaggi in base al verdetto del filtro posta indesiderata, vedere [Configure anti-spam policies in EOP.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="286a7-113">For more information about actions you can take on messages based on the spam filtering verdict, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

****

|<span data-ttu-id="286a7-114">SCL</span><span class="sxs-lookup"><span data-stu-id="286a7-114">SCL</span></span>|<span data-ttu-id="286a7-115">Definizione</span><span class="sxs-lookup"><span data-stu-id="286a7-115">Definition</span></span>|<span data-ttu-id="286a7-116">Azione predefinita</span><span class="sxs-lookup"><span data-stu-id="286a7-116">Default action</span></span>|
|:---:|---|---|
|<span data-ttu-id="286a7-117">-1</span><span class="sxs-lookup"><span data-stu-id="286a7-117">-1</span></span>|<span data-ttu-id="286a7-118">Il messaggio ha ignorato il filtro posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="286a7-118">The message skipped spam filtering.</span></span> <span data-ttu-id="286a7-119">Ad esempio, il messaggio viene inviato da un mittente sicuro, è stato inviato a un destinatario sicuro o da un server di origine della posta elettronica nell'elenco indirizzi IP consentiti.</span><span class="sxs-lookup"><span data-stu-id="286a7-119">For example, the message is from a safe sender, was sent to a safe recipient, or is from an email source server on the IP Allow List.</span></span> <span data-ttu-id="286a7-120">Per ulteriori informazioni, vedere [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="286a7-120">For more information, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>|<span data-ttu-id="286a7-121">Recapito del messaggio nella Posta in arrivo del destinatario.</span><span class="sxs-lookup"><span data-stu-id="286a7-121">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="286a7-122">0, 1</span><span class="sxs-lookup"><span data-stu-id="286a7-122">0, 1</span></span>|<span data-ttu-id="286a7-123">Il filtro posta indesiderata ha determinato che il messaggio non era posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="286a7-123">Spam filtering determined the message was not spam.</span></span>|<span data-ttu-id="286a7-124">Recapito del messaggio nella Posta in arrivo del destinatario.</span><span class="sxs-lookup"><span data-stu-id="286a7-124">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="286a7-125">5, 6</span><span class="sxs-lookup"><span data-stu-id="286a7-125">5, 6</span></span>|<span data-ttu-id="286a7-126">Il filtro posta indesiderata ha contrassegnato il messaggio come **Posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="286a7-126">Spam filtering marked the message as **Spam**</span></span>|<span data-ttu-id="286a7-127">Recapito del messaggio nella cartella Posta indesiderata del destinatario</span><span class="sxs-lookup"><span data-stu-id="286a7-127">Deliver the message to the recipients' Junk Email folder.</span></span>|
|<span data-ttu-id="286a7-128">9 </span><span class="sxs-lookup"><span data-stu-id="286a7-128">9</span></span>|<span data-ttu-id="286a7-129">Il filtro posta indesiderata ha contrassegnato il messaggio come **posta indesiderata ad alta probabilità**</span><span class="sxs-lookup"><span data-stu-id="286a7-129">Spam filtering marked the message as **High confidence spam**</span></span>|<span data-ttu-id="286a7-130">Recapito del messaggio nella cartella Posta indesiderata del destinatario</span><span class="sxs-lookup"><span data-stu-id="286a7-130">Deliver the message to the recipients' Junk Email folder.</span></span>|
|

<span data-ttu-id="286a7-131">Si noterà che SCL 2, 3, 4, 7 e 8 non vengono utilizzati dal filtro posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="286a7-131">You'll notice that SCL 2, 3, 4, 7, and 8 aren't used by spam filtering.</span></span>

<span data-ttu-id="286a7-132">È possibile utilizzare le regole del flusso di posta (note anche come regole di trasporto) per impostare il livello di probabilità di posta indesiderata sui messaggi.</span><span class="sxs-lookup"><span data-stu-id="286a7-132">You can use mail flow rules (also known as transport rules) to stamp the SCL on messages.</span></span> <span data-ttu-id="286a7-133">Se si utilizza una regola del flusso di posta per impostare il livello di probabilità di posta indesiderata, i valori 5 o 6 attivano l'azione di filtro della posta indesiderata per Posta indesiderata e i valori 7, 8 o 9 attivano l'azione di filtro della posta indesiderata per Posta indesiderata alta **confidenza.**</span><span class="sxs-lookup"><span data-stu-id="286a7-133">If you use a mail flow rule to set the SCL, the values 5 or 6 trigger the spam filtering action for **Spam**, and the values 7, 8, or 9 trigger the spam filtering action for **High confidence spam**.</span></span> <span data-ttu-id="286a7-134">Per ulteriori informazioni, vedere [Use mail flow rules to set the spam confidence level (SCL) in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span><span class="sxs-lookup"><span data-stu-id="286a7-134">For more information, see [Use mail flow rules to set the spam confidence level (SCL) in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span></span>

<span data-ttu-id="286a7-135">Analogamente al livello di probabilità di posta indesiderata, il livello di reclamo in blocco (BCL) identifica la posta elettronica in blocco non erta (nota anche come _posta grigia)._</span><span class="sxs-lookup"><span data-stu-id="286a7-135">Similar to the SCL, the bulk complaint level (BCL) identifies bad bulk email (also known as _gray mail_).</span></span> <span data-ttu-id="286a7-136">Più il BCL è elevato, maggiore è la probabilità che un messaggio di posta elettronica in blocco generi reclami, ed è quindi più probabile che si tratti di posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="286a7-136">A higher BCL indicates a bulk mail message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="286a7-137">Configurare la soglia BCL nei criteri di protezione da posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="286a7-137">You configure the BCL threshold in anti-spam policies.</span></span> <span data-ttu-id="286a7-138">Per ulteriori informazioni, vedere [Configure anti-spam policies in EOP,](configure-your-spam-filter-policies.md) [Bulk complaint level (BCL) in EOP)](bulk-complaint-level-values.md)e Qual è la differenza tra posta indesiderata e posta [elettronica in blocco?](what-s-the-difference-between-junk-email-and-bulk-email.md).</span><span class="sxs-lookup"><span data-stu-id="286a7-138">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md), [Bulk complaint level (BCL) in EOP)](bulk-complaint-level-values.md), and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md).</span></span>

****

<span data-ttu-id="286a7-139">![L'icona breve per LinkedIn Learning ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Microsoft 365?**</span><span class="sxs-lookup"><span data-stu-id="286a7-139">![The short icon for LinkedIn Learning](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Microsoft 365?**</span></span> <span data-ttu-id="286a7-140">Scopri i corsi video gratuiti per amministratori di **Microsoft 365** e professionisti IT, che sono stati portati da LinkedIn Learning.</span><span class="sxs-lookup"><span data-stu-id="286a7-140">Discover free video courses for **Microsoft 365 admins and IT pros**, brought to you by LinkedIn Learning.</span></span>
