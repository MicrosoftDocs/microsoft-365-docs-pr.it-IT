---
title: Valori di livello di reclamo in blocco
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
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: Gli amministratori possono ottenere informazioni sui valori del livello di conformità di massa (BCL) utilizzati in Exchange Online Protection (EOP).
ms.openlocfilehash: 53d0ae5fb23fb68ef970a07b2b5d8c4220775de7
ms.sourcegitcommit: 61ef32f802a1fb6d1e3a3aa005764ead32a7951e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/30/2020
ms.locfileid: "48318217"
---
# <a name="bulk-complaint-level-bcl-in-eop"></a><span data-ttu-id="0d148-103">Livello di reclamo in blocco (BCL) in EOP</span><span class="sxs-lookup"><span data-stu-id="0d148-103">Bulk complaint level (BCL) in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="0d148-104">In Microsoft 365 organizzazioni con cassette postali in Exchange Online o in organizzazioni di Exchange Online Protection (EOP) senza cassette postali di Exchange Online, EOP assegna un livello di conformità alla massa (BCL, bulk compliant Level) ai messaggi in ingresso provenienti da Mailer in blocco.</span><span class="sxs-lookup"><span data-stu-id="0d148-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP assigns a bulk compliant level (BCL) to inbound messages from bulk mailers.</span></span> <span data-ttu-id="0d148-105">La BCL viene aggiunta al messaggio in un X-header ed è simile al livello di [probabilità di posta indesiderata (SCL)](spam-confidence-levels.md) utilizzato per identificare i messaggi come posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="0d148-105">The BCL is added to the message in an X-header and is similar to the [spam confidence level (SCL)](spam-confidence-levels.md) that's used to identify messages as spam.</span></span> <span data-ttu-id="0d148-106">Una BCL superiore indica che è più probabile che un messaggio in blocco generi reclami (ed è pertanto più probabile che sia posta indesiderata).</span><span class="sxs-lookup"><span data-stu-id="0d148-106">A higher BCL indicates a bulk message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="0d148-107">Microsoft utilizza le origini sia interne che di terze parti per identificare la posta in blocco e determinare la BCL appropriata.</span><span class="sxs-lookup"><span data-stu-id="0d148-107">Microsoft uses both internal and third party sources to identify bulk mail and determine the appropriate BCL.</span></span>

<span data-ttu-id="0d148-108">I messaggi di posta elettronica in blocco variano nei modelli di invio, nella creazione di contenuto e nelle procedure di acquisizione dei destinatari.</span><span class="sxs-lookup"><span data-stu-id="0d148-108">Bulk mailers vary in their sending patterns, content creation, and recipient acquisition practices.</span></span> <span data-ttu-id="0d148-109">I messaggi di posta elettronica in blocco ottimali inviano il contenuto desiderato ai propri abbonati.</span><span class="sxs-lookup"><span data-stu-id="0d148-109">Good bulk mailers send desired messages with relevant content to their subscribers.</span></span> <span data-ttu-id="0d148-110">Questi messaggi generano alcuni reclami dai destinatari.</span><span class="sxs-lookup"><span data-stu-id="0d148-110">These messages generate few complaints from recipients.</span></span> <span data-ttu-id="0d148-111">Altri messaggi di posta elettronica in blocco inviano messaggio non richiesti che assomigliano molto alla posta indesiderata e generano numerosi reclami dai destinatari.</span><span class="sxs-lookup"><span data-stu-id="0d148-111">Other bulk mailers send unsolicited messages that closely resemble spam and generate many complaints from recipients.</span></span> <span data-ttu-id="0d148-112">I messaggi provenienti da un mailer di posta in blocco sono noti come posta in blocco o posta grigia.</span><span class="sxs-lookup"><span data-stu-id="0d148-112">Messages from a bulk mailer are known as bulk mail or gray mail.</span></span>

 <span data-ttu-id="0d148-113">Il filtro posta indesiderata consente di contrassegnare i messaggi come **posta elettronica in blocco** in base alla soglia BCL (valore predefinito o valore specificato) e di eseguire l'azione specificata sul messaggio (l'azione predefinita è recapitare il messaggio alla cartella posta indesiderata del destinatario).</span><span class="sxs-lookup"><span data-stu-id="0d148-113">Spam filtering marks messages as **Bulk email** based on the BCL threshold (the default value or a value you specify) and takes the specified action on the message (the default action is deliver the message to the recipient's Junk Email folder).</span></span> <span data-ttu-id="0d148-114">Per ulteriori informazioni, vedere Configurare i criteri di protezione dalla posta [indesiderata](configure-your-spam-filter-policies.md) e [Qual è la differenza tra posta elettronica indesiderata e posta elettronica in blocco?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span><span class="sxs-lookup"><span data-stu-id="0d148-114">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md) and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span></span>

<span data-ttu-id="0d148-115">Le soglie BCL sono descritte nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="0d148-115">The BCL thresholds are described in the following table.</span></span>

****

|<span data-ttu-id="0d148-116">BCL</span><span class="sxs-lookup"><span data-stu-id="0d148-116">BCL</span></span>|<span data-ttu-id="0d148-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0d148-117">Description</span></span>|
|:---:|---|
|<span data-ttu-id="0d148-118">0</span><span class="sxs-lookup"><span data-stu-id="0d148-118">0</span></span>|<span data-ttu-id="0d148-119">Il messaggio non viene da un mittente in blocco.</span><span class="sxs-lookup"><span data-stu-id="0d148-119">The message isn't from a bulk sender.</span></span>|
|<span data-ttu-id="0d148-120">1, 2, 3</span><span class="sxs-lookup"><span data-stu-id="0d148-120">1, 2, 3</span></span>|<span data-ttu-id="0d148-121">Il messaggio è proveniente da un mittente in blocco che genera alcuni reclami.</span><span class="sxs-lookup"><span data-stu-id="0d148-121">The message is from a bulk sender that generates few complaints.</span></span>|
|<span data-ttu-id="0d148-122">4, 5, 6, 7<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0d148-122">4, 5, 6, 7<sup>\*</sup></span></span>|<span data-ttu-id="0d148-123">Il messaggio è proveniente da un mittente in blocco che genera un numero misto di denunce.</span><span class="sxs-lookup"><span data-stu-id="0d148-123">The message is from a bulk sender that generates a mixed number of complaints.</span></span>|
|<span data-ttu-id="0d148-124">8, 9</span><span class="sxs-lookup"><span data-stu-id="0d148-124">8, 9</span></span>|<span data-ttu-id="0d148-125">Il messaggio è proveniente da un mittente in blocco che genera un numero elevato di denunce.</span><span class="sxs-lookup"><span data-stu-id="0d148-125">The message is from a bulk sender that generates a high number of complaints.</span></span>|
|

<span data-ttu-id="0d148-126"><sup>\*</sup> Si tratta del valore di soglia predefinito utilizzato nei criteri di protezione da posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="0d148-126"><sup>\*</sup> This is the default threshold value that's used in anti-spam policies.</span></span>
