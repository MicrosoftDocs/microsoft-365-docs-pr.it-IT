---
title: Aggiungere il supporto per i messaggi di posta elettronica in ingresso anonimi su IPv6
f1.keywords:
- NOCSH
author: chrisda
ms.author: chrisda
manager: chrisda
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b68df621-0a5f-4824-8abc-41e0c4fd1398
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: L'amministratore può imparare a configurare il supporto per la posta elettronica in ingresso anonima da origini IPv6 in Exchange Online ed Exchange Online Protection.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 63c9434fbd1f69c0cbd3145717b712857eb17e28
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290274"
---
# <a name="add-support-for-anonymous-inbound-email-over-ipv6-in-microsoft-365"></a><span data-ttu-id="4e03e-103">Aggiungere il supporto per la posta elettronica in ingresso anonima su IPv6 in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4e03e-103">Add support for anonymous inbound email over IPv6 in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="4e03e-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="4e03e-104">**Applies to**</span></span>
- [<span data-ttu-id="4e03e-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="4e03e-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="4e03e-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="4e03e-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="4e03e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4e03e-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="4e03e-108">Le organizzazioni di Microsoft 365 con cassette postali di Exchange Online e organizzazioni Exchange Online Protection (EOP) autonome senza cassette postali di Exchange Online supportano la posta elettronica in ingresso anonima su IPv6.</span><span class="sxs-lookup"><span data-stu-id="4e03e-108">Microsoft 365 organizations with Exchange Online mailboxes and standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes support anonymous inbound email over IPv6.</span></span> <span data-ttu-id="4e03e-109">Il server di posta elettronica IPv6 di origine deve soddisfare entrambi i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="4e03e-109">The source IPv6 email server must meet both of the following requirements:</span></span>

- <span data-ttu-id="4e03e-110">L'indirizzo IPv6 di origine deve disporre di un record di ricerca DNS inversa (PTR) valido che consenta alla destinazione di trovare il nome di dominio dall'indirizzo IPv6.</span><span class="sxs-lookup"><span data-stu-id="4e03e-110">The source IPv6 address must have a valid reverse DNS lookup (PTR) record that allows the destination to find the domain name from the IPv6 address.</span></span>

- <span data-ttu-id="4e03e-111">Il mittente deve superare la verifica SPF (definita in [RFC 7208](https://tools.ietf.org/html/rfc7208)) oppure la [verifica DKIM](http://dkim.org/) (definita in [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).</span><span class="sxs-lookup"><span data-stu-id="4e03e-111">The sender must pass either SPF verification (defined in [RFC 7208](https://tools.ietf.org/html/rfc7208)) or [DKIM verification](http://dkim.org/) (defined in [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).</span></span>

<span data-ttu-id="4e03e-112">Prima che l'organizzazione possa ricevere messaggi di posta elettronica in ingresso anonimi su IPv6, un amministratore deve contattare il supporto tecnico Microsoft e richiederlo.</span><span class="sxs-lookup"><span data-stu-id="4e03e-112">Before your organization can receive anonymous inbound email over IPv6, an admin needs to contact Microsoft support and ask for it.</span></span> <span data-ttu-id="4e03e-113">Per istruzioni su come aprire una richiesta di supporto, vedere Contattare il supporto per i prodotti [per le aziende - Guida per gli amministratori.](../../admin/contact-support-for-business-products.md)</span><span class="sxs-lookup"><span data-stu-id="4e03e-113">For instructions about how to open a support request, see [Contact support for business products - Admin Help](../../admin/contact-support-for-business-products.md).</span></span>

<span data-ttu-id="4e03e-114">Dopo aver abilitato il supporto dei messaggi IPv6 in ingresso anonimi nell'organizzazione, il messaggio verrà inviato tramite il normale filtro messaggi fornito dal servizio.</span><span class="sxs-lookup"><span data-stu-id="4e03e-114">After anonymous inbound IPv6 message support is enabled in your organization, the message will go through the normal message filtering that's provided by the service.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="4e03e-115">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="4e03e-115">Troubleshooting</span></span>

- <span data-ttu-id="4e03e-116">Se il server di posta elettronica di origine non dispone di un record di ricerca DNS inverso IPv6, i messaggi verranno rifiutati con l'errore seguente:</span><span class="sxs-lookup"><span data-stu-id="4e03e-116">If the source email server doesn't have an IPv6 reverse DNS lookup record, the messages will be rejected with the following error:</span></span>

  > <span data-ttu-id="4e03e-117">450 4.7.25 Service unavailable, sending IPv6 address [2a01:111:f200:2004::240] must have reverse DNS record.</span><span class="sxs-lookup"><span data-stu-id="4e03e-117">450 4.7.25 Service unavailable, sending IPv6 address [2a01:111:f200:2004::240] must have reverse DNS record.</span></span>

- <span data-ttu-id="4e03e-118">Se il mittente non supera la convalida SPF o DKIM, i messaggi verranno rifiutati con il seguente errore:</span><span class="sxs-lookup"><span data-stu-id="4e03e-118">If the sender doesn't pass SPF or DKIM validation, the messages will be rejected with the following error:</span></span>

  > <span data-ttu-id="4e03e-119">450 4.7.26 Servizio non disponibile, messaggio inviato tramite IPv6 [2a01:111:f200:2004::240] deve superare la convalida SPF o DKIM.</span><span class="sxs-lookup"><span data-stu-id="4e03e-119">450 4.7.26 Service unavailable, message sent over IPv6 [2a01:111:f200:2004::240] must pass either SPF or DKIM validation.</span></span>

- <span data-ttu-id="4e03e-120">Se si tenta di ricevere messaggi IPv6 anonimi prima di acconsentire esplicitamente, il messaggio verrà rifiutato con il seguente errore:</span><span class="sxs-lookup"><span data-stu-id="4e03e-120">If you try to receive anonymous IPv6 messages before you've opted in, the message will be rejected with the following error:</span></span>

  > <span data-ttu-id="4e03e-121">550 5.2.1 Servizio non disponibile, [contoso.com] non accetta la posta elettronica su IPv6.</span><span class="sxs-lookup"><span data-stu-id="4e03e-121">550 5.2.1 Service unavailable, [contoso.com] does not accept email over IPv6.</span></span>

## <a name="related-topics"></a><span data-ttu-id="4e03e-122">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="4e03e-122">Related topics</span></span>

[<span data-ttu-id="4e03e-123">Supporto per la convalida di messaggi firmati con DKIM</span><span class="sxs-lookup"><span data-stu-id="4e03e-123">Support for validation of DKIM signed messages</span></span>](support-for-validation-of-dkim-signed-messages.md)
