---
title: Supporto per la convalida delle chiavi di dominio identificate messaggi di posta elettronica (DKIM) firmati
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a4c95148-a00c-4d12-85ed-88520b547d97
ms.collection:
- M365-security-compliance
description: Informazioni sulla convalida dei messaggi firmati di DKIM in Exchange Online Protection ed Exchange Online
ms.openlocfilehash: 91a01f89bb633a38d27ddd3f2945b8707643d7e9
ms.sourcegitcommit: 89097fb648987567b9493b9d94c85c5990562874
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/13/2021
ms.locfileid: "49845060"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a><span data-ttu-id="dee1e-103">Supporto per la convalida di messaggi firmati con DKIM</span><span class="sxs-lookup"><span data-stu-id="dee1e-103">Support for validation of DKIM signed messages</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="dee1e-104">Exchange Online Protection (EOP) ed Exchange Online supportano entrambi la convalida in ingresso dei messaggi di posta elettronica ([DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)) identificati dai tasti di dominio.</span><span class="sxs-lookup"><span data-stu-id="dee1e-104">Exchange Online Protection (EOP) and Exchange Online both support inbound validation of Domain Keys Identified Mail ([DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)) messages.</span></span>

<span data-ttu-id="dee1e-105">DKIM verifica che un messaggio di posta elettronica non sia stato *falsificato* da un altro utente e che sia stato inviato dal dominio *da cui proviene* .</span><span class="sxs-lookup"><span data-stu-id="dee1e-105">DKIM validates that an email message wasn't *spoofed* by someone else, and was sent from the domain it *says* it came from.</span></span> <span data-ttu-id="dee1e-106">Collega un messaggio di posta elettronica all'organizzazione che l'ha inviata.</span><span class="sxs-lookup"><span data-stu-id="dee1e-106">It ties an email message to the organization that sent it.</span></span> <span data-ttu-id="dee1e-107">La verifica di DKIM viene utilizzata automaticamente per tutti i messaggi inviati con IPv6.</span><span class="sxs-lookup"><span data-stu-id="dee1e-107">DKIM verification is used automatically for all messages sent with IPv6.</span></span> <span data-ttu-id="dee1e-108">Microsoft 365 supporta anche DKIM quando la posta viene inviata tramite IPv4.</span><span class="sxs-lookup"><span data-stu-id="dee1e-108">Microsoft 365 also supports DKIM when mail is sent over IPv4.</span></span> <span data-ttu-id="dee1e-109">Per ulteriori informazioni sul supporto di IPv6, vedere [Supporto per messaggi di posta elettronica in ingresso anonimi su IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md).</span><span class="sxs-lookup"><span data-stu-id="dee1e-109">(For more information about IPv6 support, see [Support for anonymous inbound email messages over IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md).)</span></span>

<span data-ttu-id="dee1e-110">DKIM convalida un messaggio con firma digitale che viene visualizzato nell'intestazione DKIM-Signature delle intestazioni del messaggio.</span><span class="sxs-lookup"><span data-stu-id="dee1e-110">DKIM validates a digitally signed message that appears in the DKIM-Signature header of the message headers.</span></span> <span data-ttu-id="dee1e-111">I risultati di una convalida DKIM-Signature vengono contrassegnati nell'intestazione Authentication-Results.</span><span class="sxs-lookup"><span data-stu-id="dee1e-111">The results of a DKIM-Signature validation are stamped in the Authentication-Results header.</span></span> <span data-ttu-id="dee1e-112">Il testo dell'intestazione del messaggio è simile al seguente (dove contoso.com è il mittente):</span><span class="sxs-lookup"><span data-stu-id="dee1e-112">The message header text appears similar to the following (where contoso.com is the sender):</span></span>

 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`

> [!NOTE]
> <span data-ttu-id="dee1e-113">Per ulteriori informazioni sull'intestazione Authentication-Results, vedere RFC 7001 ([Message Header Field per indicare lo stato di autenticazione dei messaggi](https://www.rfc-editor.org/rfc/rfc7001.txt).</span><span class="sxs-lookup"><span data-stu-id="dee1e-113">For more information about the Authentication-Results header, see RFC 7001 ([Message Header Field for Indicating Message Authentication Status](https://www.rfc-editor.org/rfc/rfc7001.txt).</span></span> <span data-ttu-id="dee1e-114">L'implementazione di DKIM di Microsoft è conforme a questa RFC.</span><span class="sxs-lookup"><span data-stu-id="dee1e-114">Microsoft's DKIM implementation conforms with this RFC.</span></span>

<span data-ttu-id="dee1e-115">Gli amministratori possono creare [regole del flusso di posta](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) di Exchange (note anche come regole di trasporto) sui risultati della convalida di DKIM.</span><span class="sxs-lookup"><span data-stu-id="dee1e-115">Admins can create Exchange [mail flow rules](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) on the results of DKIM validation.</span></span> <span data-ttu-id="dee1e-116">Queste regole del flusso di posta consentiranno agli amministratori di filtrare o instradare i messaggi in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="dee1e-116">These mail flow rules will allow admins to filter or route messages as needed.</span></span>
