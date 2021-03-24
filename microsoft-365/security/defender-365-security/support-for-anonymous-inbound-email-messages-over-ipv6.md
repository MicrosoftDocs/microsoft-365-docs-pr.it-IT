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
ms.openlocfilehash: df06891401802d212cbfdb55085662901f5546e9
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51061909"
---
# <a name="add-support-for-anonymous-inbound-email-over-ipv6-in-microsoft-365"></a>Aggiungere il supporto per la posta elettronica in ingresso anonima su IPv6 in Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Le organizzazioni di Microsoft 365 con cassette postali di Exchange Online e organizzazioni autonome di Exchange Online Protection (EOP) senza cassette postali di Exchange Online supportano la posta elettronica in ingresso anonima su IPv6. Il server di posta elettronica IPv6 di origine deve soddisfare entrambi i requisiti seguenti:

- L'indirizzo IPv6 di origine deve avere un record PTR (Reverse DNS Lookup) valido che consenta alla destinazione di trovare il nome di dominio dall'indirizzo IPv6.

- Il mittente deve superare la verifica SPF (definita in [RFC 7208](https://tools.ietf.org/html/rfc7208)) oppure la [verifica DKIM](http://dkim.org/) (definita in [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).

Prima che l'organizzazione possa ricevere messaggi di posta elettronica in ingresso anonimi tramite IPv6, un amministratore deve contattare il supporto Tecnico Microsoft e richiederlo. Per istruzioni su come aprire una richiesta di supporto, vedere Contattare il supporto per i prodotti [aziendali - Guida per gli amministratori.](../../admin/contact-support-for-business-products.md)

Dopo aver abilitato il supporto dei messaggi IPv6 in ingresso anonimi nell'organizzazione, il messaggio passa attraverso il normale filtro messaggi fornito dal servizio.

## <a name="troubleshooting"></a>Risoluzione dei problemi

- Se il server di posta elettronica di origine non dispone di un record di ricerca DNS inverso IPv6, i messaggi verranno rifiutati con l'errore seguente:

  > 450 4.7.25 Service unavailable, sending IPv6 address [2a01:111:f200:2004::240] must have reverse DNS record.

- Se il mittente non supera la convalida SPF o DKIM, i messaggi verranno rifiutati con l'errore seguente:

  > 450 4.7.26 Servizio non disponibile, messaggio inviato tramite IPv6 [2a01:111:f200:2004::240] deve superare la convalida SPF o DKIM.

- Se si tenta di ricevere messaggi IPv6 anonimi prima di aver acconsentito esplicitamente, il messaggio verrà rifiutato con l'errore seguente:

  > 550 5.2.1 Servizio non disponibile, [contoso.com] non accetta la posta elettronica tramite IPv6.

## <a name="related-topics"></a>Argomenti correlati

[Supporto per la convalida di messaggi firmati con DKIM](support-for-validation-of-dkim-signed-messages.md)
