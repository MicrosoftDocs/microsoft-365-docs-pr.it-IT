---
title: Valori di livello di reclamo in blocco, messaggi di posta in blocco, livelli di BCL, come funziona BCL, valutazioni BCL, antispam, intestazione antispam, filtro posta in blocco, Interrompi posta in blocco
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
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
description: Informazioni sui valori di reclamo in blocco di livello (BCL) in Office 365.
ms.openlocfilehash: 6f9314a5b96dbd641e461dfb564ed8605372a949
ms.sourcegitcommit: b0396171d24c6298b809b43bb109d3afed4de5b8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/10/2019
ms.locfileid: "37451098"
---
# <a name="bulk-complaint-level-values"></a><span data-ttu-id="afeaa-103">Valori di livello di reclamo in blocco</span><span class="sxs-lookup"><span data-stu-id="afeaa-103">Bulk Complaint Level values</span></span>

<span data-ttu-id="afeaa-104">I messaggi di posta elettronica in blocco variano nei modelli di invio, nella creazione di contenuto e nelle procedure di acquisizione dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="afeaa-104">Bulk mailers vary in their sending patterns, content creation, and list acquisition practices.</span></span> <span data-ttu-id="afeaa-105">Alcuni sono buoni mailer che inviano messaggi desiderati con contenuto pertinente ai propri abbonati.</span><span class="sxs-lookup"><span data-stu-id="afeaa-105">Some are good bulk mailers that send wanted messages with relevant content to their subscribers.</span></span> <span data-ttu-id="afeaa-106">Questi messaggi generano alcuni reclami dai destinatari.</span><span class="sxs-lookup"><span data-stu-id="afeaa-106">These messages generate few complaints from recipients.</span></span> <span data-ttu-id="afeaa-107">Altri messaggi di posta elettronica in blocco inviano messaggio non richiesti che assomigliano molto alla posta indesiderata e generano numerosi reclami dai destinatari.</span><span class="sxs-lookup"><span data-stu-id="afeaa-107">Other bulk mailers send unsolicited messages that closely resemble spam and generate many complaints from recipients.</span></span>

<span data-ttu-id="afeaa-108">Per distinguere questi tipi di messaggi di posta elettronica in blocco, viene assegnato un punteggio di livello di reclamo in blocco da parte di un messaggio di posta elettronica in blocco.</span><span class="sxs-lookup"><span data-stu-id="afeaa-108">To distinguish these types of bulk mailers, messages from bulk mailers are assigned a Bulk Complaint Level (BCL) rating.</span></span> <span data-ttu-id="afeaa-109">Le valutazioni BCL variano da 1 a 9 a seconda di quanto è probabile che il mailer di posta in blocco debba generare reclami.</span><span class="sxs-lookup"><span data-stu-id="afeaa-109">BCL ratings range from 1 to 9 depending on how likely the bulk mailer is to generate complaints.</span></span> <span data-ttu-id="afeaa-110">Un mittente che ha un punteggio di BCL 9 può generare molti reclami dai destinatari, mentre non è probabile che un punteggio di BCL 3 generi molti reclami.</span><span class="sxs-lookup"><span data-stu-id="afeaa-110">A sender that has a rating of BCL 9 is likely to generate many complaints from recipients, whereas a rating of BCL 3 is unlikely to generate many complaints.</span></span> <span data-ttu-id="afeaa-111">Microsoft utilizza origini sia interne che di terze parti per identificare la posta in blocco e determinare la BCL appropriata.</span><span class="sxs-lookup"><span data-stu-id="afeaa-111">Microsoft uses both internal and third-party sources to identify bulk mail and determine the appropriate BCL.</span></span> <span data-ttu-id="afeaa-112">Per ulteriori informazioni su questa intestazione del messaggio, vedere intestazioni dei messaggi di protezione da [posta indesiderata](anti-spam-message-headers.md).</span><span class="sxs-lookup"><span data-stu-id="afeaa-112">For more information about this message header, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>

<span data-ttu-id="afeaa-113">Poiché un mailer di posta in blocco con una valutazione pari a 9 rischia di generare reclami, la BCL predefinita è 7.</span><span class="sxs-lookup"><span data-stu-id="afeaa-113">Since a bulk mailer with a rating of 9 is likely to generate complaints, the default BCL is 7.</span></span> <span data-ttu-id="afeaa-114">Questo significa che i messaggi di posta in blocco verranno accettati fino a quando il livello di reclamo di 7 e la posta non verranno accettati successivamente.</span><span class="sxs-lookup"><span data-stu-id="afeaa-114">This means that bulk mails will be accepted until the complaint level of 7 and mail won't be accepted thereafter.</span></span> <span data-ttu-id="afeaa-115">Minore è la classificazione, minore è l'accettazione della posta in blocco.</span><span class="sxs-lookup"><span data-stu-id="afeaa-115">The lower the rating, the less bulk mail is accepted.</span></span> <span data-ttu-id="afeaa-116">Se gli utenti sono e il loro lavoro è sensibile alla posta in blocco e la BCL è impostata su 4, non verrà accettata la posta in blocco con una BCL superiore a 4.</span><span class="sxs-lookup"><span data-stu-id="afeaa-116">If your users are, and their work is, sensitive to bulk mail, and your BCL is set to 4, then no bulk mail with a higher BCL than 4 will be accepted.</span></span>

<span data-ttu-id="afeaa-117">È possibile utilizzare i valori BCL per impostare il livello di filtro di massa desiderato per l'organizzazione, attenendosi alla procedura descritta in [Configure Your Spam Filter Policies](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="afeaa-117">You can use BCL values to set the desired level of bulk filtering your organization requires by following the steps in [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="afeaa-118">Nella tabella seguente vengono descritti i valori BCL attualmente in uso.</span><span class="sxs-lookup"><span data-stu-id="afeaa-118">The following table describes the BCL values that are currently in use.</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="afeaa-119">**Valore BCL**</span><span class="sxs-lookup"><span data-stu-id="afeaa-119">**BCL Value**</span></span>|<span data-ttu-id="afeaa-120">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="afeaa-120">**Description**</span></span>|
|<span data-ttu-id="afeaa-121">0</span><span class="sxs-lookup"><span data-stu-id="afeaa-121">0</span></span>|<span data-ttu-id="afeaa-122">Il messaggio non viene da un mittente in blocco.</span><span class="sxs-lookup"><span data-stu-id="afeaa-122">The message isn't from a bulk sender.</span></span>|
|<span data-ttu-id="afeaa-123">1, 2, 3</span><span class="sxs-lookup"><span data-stu-id="afeaa-123">1, 2, 3</span></span>|<span data-ttu-id="afeaa-124">Il messaggio è proveniente da un mittente in blocco che genera alcuni reclami.</span><span class="sxs-lookup"><span data-stu-id="afeaa-124">The message is from a bulk sender that generates few complaints.</span></span>|
|<span data-ttu-id="afeaa-125">4, 5, 6, 7</span><span class="sxs-lookup"><span data-stu-id="afeaa-125">4, 5, 6, 7</span></span>|<span data-ttu-id="afeaa-126">Il messaggio è proveniente da un mittente in blocco che genera un numero misto di denunce.</span><span class="sxs-lookup"><span data-stu-id="afeaa-126">The message is from a bulk sender that generates a mixed number of complaints.</span></span>|
|<span data-ttu-id="afeaa-127">8, 9</span><span class="sxs-lookup"><span data-stu-id="afeaa-127">8, 9</span></span>|<span data-ttu-id="afeaa-128">Il messaggio è proveniente da un mittente in blocco che genera un numero elevato di denunce</span><span class="sxs-lookup"><span data-stu-id="afeaa-128">The message is from a bulk sender that generates a high number of complaints</span></span>|
