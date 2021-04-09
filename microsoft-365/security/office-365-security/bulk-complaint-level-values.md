---
title: Valori del livello di reclamo in blocco
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
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: Gli amministratori possono ottenere informazioni sui valori BCL (Bulk Complaint Level) utilizzati in Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 08924a7db0a5c4588ed70bc41e4caf46afb35b53
ms.sourcegitcommit: a46532bb422ee51331f478ff50cc5444586bf6a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2021
ms.locfileid: "51650255"
---
# <a name="bulk-complaint-level-bcl-in-eop"></a><span data-ttu-id="342dc-103">Livello di reclamo in blocco (BCL) in EOP</span><span class="sxs-lookup"><span data-stu-id="342dc-103">Bulk complaint level (BCL) in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="342dc-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="342dc-104">**Applies to**</span></span>
- [<span data-ttu-id="342dc-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="342dc-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="342dc-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="342dc-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="342dc-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="342dc-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="342dc-108">Nelle organizzazioni di Microsoft 365 con cassette postali in Exchange Online o in organizzazioni autonome di Exchange Online Protection (EOP) senza cassette postali di Exchange Online, EOP assegna un livello di reclamo in blocco (BCL) ai messaggi in ingresso dai mailer in blocco.</span><span class="sxs-lookup"><span data-stu-id="342dc-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP assigns a bulk complaint level (BCL) to inbound messages from bulk mailers.</span></span> <span data-ttu-id="342dc-109">Il livello di probabilità di posta indesiderata viene aggiunto al messaggio in un X-header ed è simile al livello di probabilità di posta indesiderata [(SCL)](spam-confidence-levels.md) utilizzato per identificare i messaggi come posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="342dc-109">The BCL is added to the message in an X-header and is similar to the [spam confidence level (SCL)](spam-confidence-levels.md) that's used to identify messages as spam.</span></span> <span data-ttu-id="342dc-110">Un livello di probabilità di posta indesiderata più elevato indica che un messaggio in blocco è più probabile che generi reclami (ed è quindi più probabile che sia posta indesiderata).</span><span class="sxs-lookup"><span data-stu-id="342dc-110">A higher BCL indicates a bulk message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="342dc-111">Microsoft usa sia origini interne che di terze parti per identificare la posta in blocco e determinare il BCL appropriato.</span><span class="sxs-lookup"><span data-stu-id="342dc-111">Microsoft uses both internal and third party sources to identify bulk mail and determine the appropriate BCL.</span></span>

<span data-ttu-id="342dc-112">I mailer in blocco variano in base ai modelli di invio, alla creazione di contenuto e alle procedure di acquisizione dei destinatari.</span><span class="sxs-lookup"><span data-stu-id="342dc-112">Bulk mailers vary in their sending patterns, content creation, and recipient acquisition practices.</span></span> <span data-ttu-id="342dc-113">I mailer in blocco inviano ai propri sottoscrittori i messaggi desiderati con contenuto pertinente.</span><span class="sxs-lookup"><span data-stu-id="342dc-113">Good bulk mailers send desired messages with relevant content to their subscribers.</span></span> <span data-ttu-id="342dc-114">Questi messaggi generano pochi reclami da parte dei destinatari.</span><span class="sxs-lookup"><span data-stu-id="342dc-114">These messages generate few complaints from recipients.</span></span> <span data-ttu-id="342dc-115">Altri mailer in blocco inviano messaggi indesiderati che assomigliano molto alla posta indesiderata e generano molti reclami da parte dei destinatari.</span><span class="sxs-lookup"><span data-stu-id="342dc-115">Other bulk mailers send unsolicited messages that closely resemble spam and generate many complaints from recipients.</span></span> <span data-ttu-id="342dc-116">I messaggi provenienti da un mailer in blocco sono noti come posta in blocco o posta grigia.</span><span class="sxs-lookup"><span data-stu-id="342dc-116">Messages from a bulk mailer are known as bulk mail or gray mail.</span></span>

 <span data-ttu-id="342dc-117">Il filtro della  posta indesiderata contrassegna i messaggi come posta elettronica in blocco in base alla soglia BCL (il valore predefinito o un valore specificato) ed eseguire l'azione specificata sul messaggio (l'azione predefinita è recapitare il messaggio nella cartella Posta indesiderata del destinatario).</span><span class="sxs-lookup"><span data-stu-id="342dc-117">Spam filtering marks messages as **Bulk email** based on the BCL threshold (the default value or a value you specify) and takes the specified action on the message (the default action is deliver the message to the recipient's Junk Email folder).</span></span> <span data-ttu-id="342dc-118">Per ulteriori informazioni, vedere [Configure anti-spam policies](configure-your-spam-filter-policies.md) e [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span><span class="sxs-lookup"><span data-stu-id="342dc-118">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md) and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span></span>

<span data-ttu-id="342dc-119">Le soglie BCL sono descritte nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="342dc-119">The BCL thresholds are described in the following table.</span></span>

****

|<span data-ttu-id="342dc-120">BCL</span><span class="sxs-lookup"><span data-stu-id="342dc-120">BCL</span></span>|<span data-ttu-id="342dc-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="342dc-121">Description</span></span>|
|:---:|---|
|<span data-ttu-id="342dc-122">0</span><span class="sxs-lookup"><span data-stu-id="342dc-122">0</span></span>|<span data-ttu-id="342dc-123">Il messaggio non viene inviato da un mittente in blocco.</span><span class="sxs-lookup"><span data-stu-id="342dc-123">The message isn't from a bulk sender.</span></span>|
|<span data-ttu-id="342dc-124">1, 2, 3</span><span class="sxs-lookup"><span data-stu-id="342dc-124">1, 2, 3</span></span>|<span data-ttu-id="342dc-125">Il messaggio viene inviato da un mittente in blocco che genera pochi reclami.</span><span class="sxs-lookup"><span data-stu-id="342dc-125">The message is from a bulk sender that generates few complaints.</span></span>|
|<span data-ttu-id="342dc-126">4, 5, 6, 7<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="342dc-126">4, 5, 6, 7<sup>\*</sup></span></span>|<span data-ttu-id="342dc-127">Il messaggio viene inviato da un mittente in blocco che genera un numero misto di reclami.</span><span class="sxs-lookup"><span data-stu-id="342dc-127">The message is from a bulk sender that generates a mixed number of complaints.</span></span>|
|<span data-ttu-id="342dc-128">8, 9</span><span class="sxs-lookup"><span data-stu-id="342dc-128">8, 9</span></span>|<span data-ttu-id="342dc-129">Il messaggio viene inviato da un mittente in blocco che genera un numero elevato di reclami.</span><span class="sxs-lookup"><span data-stu-id="342dc-129">The message is from a bulk sender that generates a high number of complaints.</span></span>|
|

<span data-ttu-id="342dc-130"><sup>\*</sup> Si tratta del valore di soglia predefinito utilizzato nei criteri di protezione da posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="342dc-130"><sup>\*</sup> This is the default threshold value that's used in anti-spam policies.</span></span>
