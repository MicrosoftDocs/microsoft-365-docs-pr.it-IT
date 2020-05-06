---
title: Valori dei livelli di reclamo in blocco (BCL)
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 8/23/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: Informazioni sui valori del livello di conformità in blocco (BCL, bulk Compliance Level) in Office 365.
ms.openlocfilehash: 82c006f05ce3d37ff23ca1e522b653bd26efeed8
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035569"
---
# <a name="bulk-complaint-level-bcl-in-office-365"></a><span data-ttu-id="e036f-103">Livello di reclamo in blocco (BCL) in Office 365</span><span class="sxs-lookup"><span data-stu-id="e036f-103">Bulk complaint level (BCL) in Office 365</span></span>

<span data-ttu-id="e036f-104">I messaggi di posta elettronica in blocco variano nei modelli di invio, nella creazione di contenuto e nelle procedure di acquisizione dei destinatari.</span><span class="sxs-lookup"><span data-stu-id="e036f-104">Bulk mailers vary in their sending patterns, content creation, and recipient acquisition practices.</span></span> <span data-ttu-id="e036f-105">Alcuni sono buoni mailer che inviano i messaggi desiderati con contenuti rilevanti ai propri abbonati.</span><span class="sxs-lookup"><span data-stu-id="e036f-105">Some are good bulk mailers that send desired messages with relevant content to their subscribers.</span></span> <span data-ttu-id="e036f-106">Questi messaggi generano alcuni reclami dai destinatari.</span><span class="sxs-lookup"><span data-stu-id="e036f-106">These messages generate few complaints from recipients.</span></span> <span data-ttu-id="e036f-107">Altri messaggi di posta elettronica in blocco inviano messaggio non richiesti che assomigliano molto alla posta indesiderata e generano numerosi reclami dai destinatari.</span><span class="sxs-lookup"><span data-stu-id="e036f-107">Other bulk mailers send unsolicited messages that closely resemble spam and generate many complaints from recipients.</span></span> <span data-ttu-id="e036f-108">I messaggi provenienti da un mailer di posta in blocco sono noti come posta in blocco o posta grigia.</span><span class="sxs-lookup"><span data-stu-id="e036f-108">Messages from a bulk mailer is known as bulk mail or gray mail.</span></span>

<span data-ttu-id="e036f-109">Per distinguere i messaggi provenienti da diversi tipi di posta in blocco, la posta elettronica in ingresso proveniente da messaggi di posta in blocco (Exchange Online o standalone Exchange Online Protection (EOP) senza le cassette postali di Exchange Online) viene assegnata a un livello di reclamo in blocco (BCL) aggiunto al messaggio in un X-header.</span><span class="sxs-lookup"><span data-stu-id="e036f-109">To distinguish messages from different types of bulk mailers, inbound email from bulk mailers (Exchange Online or standalone Exchange Online Protection (EOP) without Exchange Online mailboxes) is assigned a bulk complaint level (BCL) that's added to the message in an X-header.</span></span> <span data-ttu-id="e036f-110">La BCL è simile al [livello di probabilità di posta indesiderata (SCL)](spam-confidence-levels.md) utilizzato per identificare i messaggi come posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="e036f-110">The BCL is similar to the [spam confidence level (SCL)](spam-confidence-levels.md) that's used to identify messages as spam.</span></span> <span data-ttu-id="e036f-111">Una BCL superiore indica che è più probabile che un messaggio in blocco generi reclami (ed è pertanto più probabile che sia posta indesiderata).</span><span class="sxs-lookup"><span data-stu-id="e036f-111">A higher BCL indicates a bulk message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="e036f-112">Microsoft utilizza le origini sia interne che di terze parti per identificare la posta in blocco e determinare la BCL appropriata.</span><span class="sxs-lookup"><span data-stu-id="e036f-112">Microsoft uses both internal and third party sources to identify bulk mail and determine the appropriate BCL.</span></span>

 <span data-ttu-id="e036f-113">Il filtro posta indesiderata consente di contrassegnare i messaggi come **posta elettronica in blocco** in base alla soglia BCL (valore predefinito o valore specificato) e di eseguire l'azione specificata sul messaggio (l'azione predefinita è recapitare il messaggio alla cartella posta indesiderata del destinatario).</span><span class="sxs-lookup"><span data-stu-id="e036f-113">Spam filtering marks messages as **Bulk email** based on the BCL threshold (the default value or a value you specify) and takes the specified action on the message (the default action is deliver the message to the recipient's Junk Email folder).</span></span> <span data-ttu-id="e036f-114">Per ulteriori informazioni, vedere Configurare i criteri di protezione dalla posta [indesiderata](configure-your-spam-filter-policies.md) e [Qual è la differenza tra posta elettronica indesiderata e posta elettronica in blocco?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span><span class="sxs-lookup"><span data-stu-id="e036f-114">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md) and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span></span>

<span data-ttu-id="e036f-115">Le soglie BCL sono descritte nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="e036f-115">The BCL thresholds are described in the following table.</span></span>

|||
|:---:|---|
|<span data-ttu-id="e036f-116">**BCL**</span><span class="sxs-lookup"><span data-stu-id="e036f-116">**BCL**</span></span>|<span data-ttu-id="e036f-117">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="e036f-117">**Description**</span></span>|
|<span data-ttu-id="e036f-118">0</span><span class="sxs-lookup"><span data-stu-id="e036f-118">0</span></span>|<span data-ttu-id="e036f-119">Il messaggio non viene da un mittente in blocco.</span><span class="sxs-lookup"><span data-stu-id="e036f-119">The message isn't from a bulk sender.</span></span>|
|<span data-ttu-id="e036f-120">1, 2, 3</span><span class="sxs-lookup"><span data-stu-id="e036f-120">1, 2, 3</span></span>|<span data-ttu-id="e036f-121">Il messaggio è proveniente da un mittente in blocco che genera alcuni reclami.</span><span class="sxs-lookup"><span data-stu-id="e036f-121">The message is from a bulk sender that generates few complaints.</span></span>|
|<span data-ttu-id="e036f-122">4, 5, 6, 7</span><span class="sxs-lookup"><span data-stu-id="e036f-122">4, 5, 6, 7</span></span>|<span data-ttu-id="e036f-123">Il messaggio è proveniente da un mittente in blocco che genera un numero misto di denunce.</span><span class="sxs-lookup"><span data-stu-id="e036f-123">The message is from a bulk sender that generates a mixed number of complaints.</span></span>|
|<span data-ttu-id="e036f-124">8, 9</span><span class="sxs-lookup"><span data-stu-id="e036f-124">8, 9</span></span>|<span data-ttu-id="e036f-125">Il messaggio è proveniente da un mittente in blocco che genera un numero elevato di denunce.</span><span class="sxs-lookup"><span data-stu-id="e036f-125">The message is from a bulk sender that generates a high number of complaints.</span></span>|
|
