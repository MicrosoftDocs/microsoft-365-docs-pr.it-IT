---
title: Supporto per la convalida dei messaggi firmati DKIM (Domain Keys Identified Mail)
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a4c95148-a00c-4d12-85ed-88520b547d97
ms.collection:
- M365-security-compliance
description: Informazioni sulla convalida dei messaggi firmati DKIM in Exchange Online Protection ed Exchange Online
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 111bf169d60e386dc48ef086bbe631b8760201a6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916527"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a><span data-ttu-id="8dff8-103">Supporto per la convalida di messaggi firmati con DKIM</span><span class="sxs-lookup"><span data-stu-id="8dff8-103">Support for validation of DKIM signed messages</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="8dff8-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="8dff8-104">**Applies to**</span></span>
- [<span data-ttu-id="8dff8-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="8dff8-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="8dff8-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="8dff8-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="8dff8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8dff8-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="8dff8-108">Exchange Online Protection (EOP) ed Exchange Online supportano entrambi la convalida in ingresso dei messaggi[DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)(Domain Keys Identified Mail).</span><span class="sxs-lookup"><span data-stu-id="8dff8-108">Exchange Online Protection (EOP) and Exchange Online both support inbound validation of Domain Keys Identified Mail ([DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)) messages.</span></span>

<span data-ttu-id="8dff8-109">DKIM convalida che un messaggio di posta elettronica non è stato *falsificato* da un altro utente ed è stato inviato dal dominio da cui è stato specificato. </span><span class="sxs-lookup"><span data-stu-id="8dff8-109">DKIM validates that an email message wasn't *spoofed* by someone else, and was sent from the domain it *says* it came from.</span></span> <span data-ttu-id="8dff8-110">Viene quindi inviato un messaggio di posta elettronica all'organizzazione che lo ha inviato.</span><span class="sxs-lookup"><span data-stu-id="8dff8-110">It ties an email message to the organization that sent it.</span></span> <span data-ttu-id="8dff8-111">La verifica DKIM viene utilizzata automaticamente per tutti i messaggi inviati con IPv6.</span><span class="sxs-lookup"><span data-stu-id="8dff8-111">DKIM verification is used automatically for all messages sent with IPv6.</span></span> <span data-ttu-id="8dff8-112">Microsoft 365 supporta inoltre DKIM quando la posta viene inviata tramite IPv4.</span><span class="sxs-lookup"><span data-stu-id="8dff8-112">Microsoft 365 also supports DKIM when mail is sent over IPv4.</span></span> <span data-ttu-id="8dff8-113">Per ulteriori informazioni sul supporto di IPv6, vedere [Supporto per messaggi di posta elettronica in ingresso anonimi su IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md).</span><span class="sxs-lookup"><span data-stu-id="8dff8-113">(For more information about IPv6 support, see [Support for anonymous inbound email messages over IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md).)</span></span>

<span data-ttu-id="8dff8-114">DKIM convalida un messaggio con firma digitale che viene visualizzato nellDKIM-Signature delle intestazioni del messaggio.</span><span class="sxs-lookup"><span data-stu-id="8dff8-114">DKIM validates a digitally signed message that appears in the DKIM-Signature header of the message headers.</span></span> <span data-ttu-id="8dff8-115">I risultati di una DKIM-Signature convalida vengono contrassegnati nell'intestazione Authentication-Results.</span><span class="sxs-lookup"><span data-stu-id="8dff8-115">The results of a DKIM-Signature validation are stamped in the Authentication-Results header.</span></span> <span data-ttu-id="8dff8-116">Il testo dell'intestazione del messaggio è simile al seguente (dove contoso.com è il mittente):</span><span class="sxs-lookup"><span data-stu-id="8dff8-116">The message header text appears similar to the following (where contoso.com is the sender):</span></span>

 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`

> [!NOTE]
> <span data-ttu-id="8dff8-117">Per ulteriori informazioni sull'intestazione Authentication-Results messaggio, vedere RFC 7001 ([Message Header Field for Indicating Message Authentication Status](https://www.rfc-editor.org/rfc/rfc7001.txt)).</span><span class="sxs-lookup"><span data-stu-id="8dff8-117">For more information about the Authentication-Results header, see RFC 7001 ([Message Header Field for Indicating Message Authentication Status](https://www.rfc-editor.org/rfc/rfc7001.txt).</span></span> <span data-ttu-id="8dff8-118">L'implementazione DKIM di Microsoft è conforme a questa RFC.</span><span class="sxs-lookup"><span data-stu-id="8dff8-118">Microsoft's DKIM implementation conforms with this RFC.</span></span>

<span data-ttu-id="8dff8-119">Gli amministratori possono creare regole del flusso [di posta](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) di Exchange (note anche come regole di trasporto) sui risultati della convalida DKIM.</span><span class="sxs-lookup"><span data-stu-id="8dff8-119">Admins can create Exchange [mail flow rules](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) on the results of DKIM validation.</span></span> <span data-ttu-id="8dff8-120">Queste regole del flusso di posta consentiranno agli amministratori di filtrare o instradare i messaggi in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="8dff8-120">These mail flow rules will allow admins to filter or route messages as needed.</span></span>