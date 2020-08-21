---
title: Aggiungere il supporto per i messaggi di posta elettronica in ingresso anonimi su IPv6
f1.keywords:
- NOCSH
author: chrisda
ms.author: chrisda
manager: chrisda
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b68df621-0a5f-4824-8abc-41e0c4fd1398
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: L'amministratore può imparare a configurare il supporto per la posta elettronica in ingresso anonima dalle origini IPv6 in Exchange Online e Exchange Online Protection.
ms.openlocfilehash: 7384c1044cc02ec20079dc03068c2ca99e68d2c2
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826778"
---
# <a name="add-support-for-anonymous-inbound-email-over-ipv6-in-microsoft-365"></a><span data-ttu-id="20149-103">Aggiungere il supporto per la posta elettronica in ingresso anonima su IPv6 in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="20149-103">Add support for anonymous inbound email over IPv6 in Microsoft 365</span></span>

<span data-ttu-id="20149-104">Microsoft 365 organizzazioni con cassette postali di Exchange Online e organizzazioni autonome di Exchange Online Protection (EOP) senza cassette postali di Exchange Online supportano la posta elettronica in ingresso anonima su IPv6.</span><span class="sxs-lookup"><span data-stu-id="20149-104">Microsoft 365 organizations with Exchange Online mailboxes and standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes support anonymous inbound email over IPv6.</span></span> <span data-ttu-id="20149-105">Il server di posta elettronica IPv6 di origine deve soddisfare entrambi i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="20149-105">The source IPv6 email server must meet both of the following requirements:</span></span>

- <span data-ttu-id="20149-106">L'indirizzo IPv6 di origine deve disporre di un record PTR (Reverse DNS Lookup) valido che consenta alla destinazione di trovare il nome di dominio dall'indirizzo IPv6.</span><span class="sxs-lookup"><span data-stu-id="20149-106">The source IPv6 address must have a valid reverse DNS lookup (PTR) record that allows the destination to find the domain name from the IPv6 address.</span></span>

- <span data-ttu-id="20149-107">Il mittente deve superare la verifica SPF (definita in [RFC 7208](https://tools.ietf.org/html/rfc7208)) oppure la [verifica DKIM](https://dkim.org/) (definita in [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).</span><span class="sxs-lookup"><span data-stu-id="20149-107">The sender must pass either SPF verification (defined in [RFC 7208](https://tools.ietf.org/html/rfc7208)) or [DKIM verification](https://dkim.org/) (defined in [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).</span></span>

<span data-ttu-id="20149-108">Prima che l'organizzazione possa ricevere messaggi di posta elettronica in ingresso anonimi su IPv6, un amministratore deve contattare il supporto tecnico Microsoft e richiederlo.</span><span class="sxs-lookup"><span data-stu-id="20149-108">Before your organization can receive anonymous inbound email over IPv6, an admin needs to contact Microsoft support and ask for it.</span></span> <span data-ttu-id="20149-109">Per istruzioni su come aprire una richiesta di supporto, vedere [contattare il supporto per i prodotti aziendali-Guida](../../admin/contact-support-for-business-products.md)per gli amministratori.</span><span class="sxs-lookup"><span data-stu-id="20149-109">For instructions about how to open a support request, see [Contact support for business products - Admin Help](../../admin/contact-support-for-business-products.md).</span></span>

<span data-ttu-id="20149-110">Dopo l'attivazione del supporto dei messaggi IPv6 in ingresso anonimo nell'organizzazione, il messaggio passerà attraverso il normale filtro dei messaggi fornito dal servizio.</span><span class="sxs-lookup"><span data-stu-id="20149-110">After anonymous inbound IPv6 message support is enabled in your organization, the message will go through the normal message filtering that's provided by the service.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="20149-111">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="20149-111">Troubleshooting</span></span>

- <span data-ttu-id="20149-112">Se il server di posta elettronica di origine non dispone di un record di ricerca DNS inverso IPv6, i messaggi verranno rifiutati con l'errore seguente:</span><span class="sxs-lookup"><span data-stu-id="20149-112">If the source email server doesn't have an IPv6 reverse DNS lookup record, the messages will be rejected with the following error:</span></span>

  > <span data-ttu-id="20149-113">450 il servizio 4.7.25 non è disponibile, l'invio dell'indirizzo IPv6 [2a01:111: F200:2004:: 240] deve avere un record DNS inverso.</span><span class="sxs-lookup"><span data-stu-id="20149-113">450 4.7.25 Service unavailable, sending IPv6 address [2a01:111:f200:2004::240] must have reverse DNS record.</span></span>

- <span data-ttu-id="20149-114">Se il mittente non supera la convalida SPF o DKIM, i messaggi verranno rifiutati con l'errore seguente:</span><span class="sxs-lookup"><span data-stu-id="20149-114">If the sender doesn't pass SPF or DKIM validation, the messages will be rejected with the following error:</span></span>

  > <span data-ttu-id="20149-115">450 servizio 4.7.26 non disponibile, il messaggio inviato su IPv6 [2a01:111: F200:2004:: 240] deve passare sia SPF sia la convalida DKIM.</span><span class="sxs-lookup"><span data-stu-id="20149-115">450 4.7.26 Service unavailable, message sent over IPv6 [2a01:111:f200:2004::240] must pass either SPF or DKIM validation.</span></span>

- <span data-ttu-id="20149-116">Se si tenta di ricevere messaggi IPv6 anonimi prima di essere stati scelti, il messaggio verrà rifiutato con il seguente errore:</span><span class="sxs-lookup"><span data-stu-id="20149-116">If you try to receive anonymous IPv6 messages before you've opted in, the message will be rejected with the following error:</span></span>

  > <span data-ttu-id="20149-117">550 5.2.1 servizio non disponibile, [contoso.com] non accetta la posta elettronica su IPv6.</span><span class="sxs-lookup"><span data-stu-id="20149-117">550 5.2.1 Service unavailable, [contoso.com] does not accept email over IPv6.</span></span>

## <a name="related-topics"></a><span data-ttu-id="20149-118">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="20149-118">Related topics</span></span>

[<span data-ttu-id="20149-119">Supporto per la convalida di messaggi firmati con DKIM</span><span class="sxs-lookup"><span data-stu-id="20149-119">Support for validation of DKIM signed messages</span></span>](support-for-validation-of-dkim-signed-messages.md)