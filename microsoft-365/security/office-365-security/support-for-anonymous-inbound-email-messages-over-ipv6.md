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
ms.openlocfilehash: be226bf9814b0fcfadaaeb5b4bdda0ff133dd0c8
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202150"
---
# <a name="add-support-for-anonymous-inbound-email-over-ipv6-in-microsoft-365"></a>Aggiungere il supporto per la posta elettronica in ingresso anonima su IPv6 in Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Microsoft 365 organizzazioni con cassette postali di Exchange Online e organizzazioni autonome di Exchange Online Protection (EOP) senza cassette postali di Exchange Online supportano la posta elettronica in ingresso anonima su IPv6. Il server di posta elettronica IPv6 di origine deve soddisfare entrambi i requisiti seguenti:

- L'indirizzo IPv6 di origine deve disporre di un record PTR (Reverse DNS Lookup) valido che consenta alla destinazione di trovare il nome di dominio dall'indirizzo IPv6.

- Il mittente deve superare la verifica SPF (definita in [RFC 7208](https://tools.ietf.org/html/rfc7208)) oppure la [verifica DKIM](http://dkim.org/) (definita in [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).

Prima che l'organizzazione possa ricevere messaggi di posta elettronica in ingresso anonimi su IPv6, un amministratore deve contattare il supporto tecnico Microsoft e richiederlo. Per istruzioni su come aprire una richiesta di supporto, vedere [contattare il supporto per i prodotti aziendali-Guida](../../admin/contact-support-for-business-products.md)per gli amministratori.

Dopo l'attivazione del supporto dei messaggi IPv6 in ingresso anonimo nell'organizzazione, il messaggio passerà attraverso il normale filtro dei messaggi fornito dal servizio.

## <a name="troubleshooting"></a>Risoluzione dei problemi

- Se il server di posta elettronica di origine non dispone di un record di ricerca DNS inverso IPv6, i messaggi verranno rifiutati con l'errore seguente:

  > 450 il servizio 4.7.25 non è disponibile, l'invio dell'indirizzo IPv6 [2a01:111: F200:2004:: 240] deve avere un record DNS inverso.

- Se il mittente non supera la convalida SPF o DKIM, i messaggi verranno rifiutati con l'errore seguente:

  > 450 servizio 4.7.26 non disponibile, il messaggio inviato su IPv6 [2a01:111: F200:2004:: 240] deve passare sia SPF sia la convalida DKIM.

- Se si tenta di ricevere messaggi IPv6 anonimi prima di essere stati scelti, il messaggio verrà rifiutato con il seguente errore:

  > 550 5.2.1 servizio non disponibile, [contoso.com] non accetta la posta elettronica su IPv6.

## <a name="related-topics"></a>Argomenti correlati

[Supporto per la convalida di messaggi firmati con DKIM](support-for-validation-of-dkim-signed-messages.md)
