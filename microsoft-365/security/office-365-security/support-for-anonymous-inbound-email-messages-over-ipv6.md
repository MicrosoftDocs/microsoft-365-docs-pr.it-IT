---
title: Aggiungere il supporto per la posta elettronica in ingresso anonima su IPv6
f1.keywords:
- NOCSH
author: chrisda
ms.author: chrisda
manager: chrisda
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b68df621-0a5f-4824-8abc-41e0c4fd1398
ms.collection:
- M365-security-compliance
description: L'amministratore può imparare a configurare il supporto per la posta elettronica in ingresso anonima dalle origini IPv6 in Exchange Online e Exchange Online Protection.
ms.openlocfilehash: 67e839249d41381be22bbccf6b09d1616c387c66
ms.sourcegitcommit: 748bc3484b7ccbd65b558f495b6fa42196c3c571
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2020
ms.locfileid: "43083642"
---
# <a name="add-support-for-anonymous-inbound-email-over-ipv6-in-office-365"></a><span data-ttu-id="91f89-103">Aggiungere il supporto per la posta elettronica in ingresso anonima su IPv6 in Office 365</span><span class="sxs-lookup"><span data-stu-id="91f89-103">Add support for anonymous inbound email over IPv6 in Office 365</span></span>

<span data-ttu-id="91f89-104">Le organizzazioni di Office 365 con cassette postali di Exchange Online e organizzazioni autonome di Exchange Online Protection (EOP) senza cassette postali di Exchange Online supportano la posta elettronica in ingresso anonima su IPv6</span><span class="sxs-lookup"><span data-stu-id="91f89-104">Office 365 organizations with Exchange Online mailboxes and standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes support anonymous inbound email over IPv6.</span></span> <span data-ttu-id="91f89-105">Il server di posta elettronica IPv6 di origine deve soddisfare entrambi i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="91f89-105">The source IPv6 email server must meet both of the following requirements:</span></span>

- <span data-ttu-id="91f89-106">L'indirizzo IPv6 di origine deve disporre di un record PTR (Reverse DNS Lookup) valido che consenta alla destinazione di trovare il nome di dominio dall'indirizzo IPv6.</span><span class="sxs-lookup"><span data-stu-id="91f89-106">The source IPv6 address must have a valid reverse DNS lookup (PTR) record that allows the destination to find the domain name from the IPv6 address.</span></span>

- <span data-ttu-id="91f89-107">Il mittente deve superare la verifica SPF (definita in [RFC 7208](https://tools.ietf.org/html/rfc7208)) oppure la [verifica DKIM](https://dkim.org/) (definita in [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).</span><span class="sxs-lookup"><span data-stu-id="91f89-107">The sender must pass either SPF verification (defined in [RFC 7208](https://tools.ietf.org/html/rfc7208)) or [DKIM verification](https://dkim.org/) (defined in [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).</span></span>

<span data-ttu-id="91f89-108">Prima che l'organizzazione possa ricevere messaggi di posta elettronica in ingresso anonimi su IPv6, un amministratore deve contattare il supporto tecnico Microsoft e richiederlo:</span><span class="sxs-lookup"><span data-stu-id="91f89-108">Before your organization can receive anonymous inbound email over IPv6, an admin needs to contact Microsoft support and ask for it:</span></span>

1. <span data-ttu-id="91f89-109">Aprire l'interfaccia di amministrazione di Microsoft <https://admin.microsoft.com/adminportal/home> 365 in e fare clic su **Guida** (?).</span><span class="sxs-lookup"><span data-stu-id="91f89-109">Open the Microsoft 365 admin center at <https://admin.microsoft.com/adminportal/home> and click **Help** (?).</span></span>

2. <span data-ttu-id="91f89-110">Nella casella di ricerca, ad esempio, "richiedere messaggi di posta elettronica IPv6 in ingresso" e quindi premere INVIO, digitare una **Descrizione del riquadro a comparsa.**</span><span class="sxs-lookup"><span data-stu-id="91f89-110">In the **Need help?** flyout that appears, type something descriptive in the search box (for example, "request anonymous inbound IPv6 email"), and then press ENTER.</span></span>

3. <span data-ttu-id="91f89-111">Nella parte inferiore della pagina, fare clic su supporto per i **contatti**.</span><span class="sxs-lookup"><span data-stu-id="91f89-111">At the bottom of the page, click **Contact support**.</span></span>

4. <span data-ttu-id="91f89-112">Nella pagina del **supporto dei contatti** che viene visualizzata, compilare e verificare le informazioni (scorrere verso il basso se necessario) e quindi fare clic su **contattami**.</span><span class="sxs-lookup"><span data-stu-id="91f89-112">In the **Contact support** page that appears, fill out and verify the information (scroll down as necessary), and then click **Contact me**.</span></span>

<span data-ttu-id="91f89-113">Dopo l'attivazione del supporto dei messaggi IPv6 in ingresso anonimo nell'organizzazione, il messaggio passerà attraverso il normale filtro dei messaggi fornito dal servizio.</span><span class="sxs-lookup"><span data-stu-id="91f89-113">After anonymous inbound IPv6 message support is enabled in your organization, the message will go through the normal message filtering that's provided by the service.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="91f89-114">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="91f89-114">Troubleshooting</span></span>

- <span data-ttu-id="91f89-115">Se il server di posta elettronica di origine non dispone di un record di ricerca DNS inverso IPv6, i messaggi verranno rifiutati con l'errore seguente:</span><span class="sxs-lookup"><span data-stu-id="91f89-115">If the source email server doesn't have an IPv6 reverse DNS lookup record, the messages will be rejected with the following error:</span></span>

  > <span data-ttu-id="91f89-116">450 il servizio 4.7.25 non è disponibile, l'invio dell'indirizzo IPv6 [2a01:111: F200:2004:: 240] deve avere un record DNS inverso.</span><span class="sxs-lookup"><span data-stu-id="91f89-116">450 4.7.25 Service unavailable, sending IPv6 address [2a01:111:f200:2004::240] must have reverse DNS record.</span></span>

- <span data-ttu-id="91f89-117">Se il mittente non supera la convalida SPF o DKIM, i messaggi verranno rifiutati con l'errore seguente:</span><span class="sxs-lookup"><span data-stu-id="91f89-117">If the sender doesn't pass SPF or DKIM validation, the messages will be rejected with the following error:</span></span>

  > <span data-ttu-id="91f89-118">450 servizio 4.7.26 non disponibile, il messaggio inviato su IPv6 [2a01:111: F200:2004:: 240] deve passare sia SPF sia la convalida DKIM.</span><span class="sxs-lookup"><span data-stu-id="91f89-118">450 4.7.26 Service unavailable, message sent over IPv6 [2a01:111:f200:2004::240] must pass either SPF or DKIM validation.</span></span>

- <span data-ttu-id="91f89-119">Se si tenta di ricevere messaggi IPv6 anonimi prima di essere stati scelti, il messaggio verrà rifiutato con il seguente errore:</span><span class="sxs-lookup"><span data-stu-id="91f89-119">If you try to receive anonymous IPv6 messages before you've opted in, the message will be rejected with the following error:</span></span>

  > <span data-ttu-id="91f89-120">550 5.2.1 servizio non disponibile, [contoso.com] non accetta la posta elettronica su IPv6.</span><span class="sxs-lookup"><span data-stu-id="91f89-120">550 5.2.1 Service unavailable, [contoso.com] does not accept email over IPv6.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="91f89-121">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="91f89-121">For more information</span></span>

[<span data-ttu-id="91f89-122">Supporto per la convalida di messaggi firmati con DKIM</span><span class="sxs-lookup"><span data-stu-id="91f89-122">Support for validation of DKIM signed messages</span></span>](support-for-validation-of-dkim-signed-messages.md)
