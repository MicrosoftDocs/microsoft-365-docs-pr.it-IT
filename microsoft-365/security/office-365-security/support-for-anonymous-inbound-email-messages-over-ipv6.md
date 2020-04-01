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
# <a name="add-support-for-anonymous-inbound-email-over-ipv6-in-office-365"></a>Aggiungere il supporto per la posta elettronica in ingresso anonima su IPv6 in Office 365

Le organizzazioni di Office 365 con cassette postali di Exchange Online e organizzazioni autonome di Exchange Online Protection (EOP) senza cassette postali di Exchange Online supportano la posta elettronica in ingresso anonima su IPv6 Il server di posta elettronica IPv6 di origine deve soddisfare entrambi i requisiti seguenti:

- L'indirizzo IPv6 di origine deve disporre di un record PTR (Reverse DNS Lookup) valido che consenta alla destinazione di trovare il nome di dominio dall'indirizzo IPv6.

- Il mittente deve superare la verifica SPF (definita in [RFC 7208](https://tools.ietf.org/html/rfc7208)) oppure la [verifica DKIM](https://dkim.org/) (definita in [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).

Prima che l'organizzazione possa ricevere messaggi di posta elettronica in ingresso anonimi su IPv6, un amministratore deve contattare il supporto tecnico Microsoft e richiederlo:

1. Aprire l'interfaccia di amministrazione di Microsoft <https://admin.microsoft.com/adminportal/home> 365 in e fare clic su **Guida** (?).

2. Nella casella di ricerca, ad esempio, "richiedere messaggi di posta elettronica IPv6 in ingresso" e quindi premere INVIO, digitare una **Descrizione del riquadro a comparsa.**

3. Nella parte inferiore della pagina, fare clic su supporto per i **contatti**.

4. Nella pagina del **supporto dei contatti** che viene visualizzata, compilare e verificare le informazioni (scorrere verso il basso se necessario) e quindi fare clic su **contattami**.

Dopo l'attivazione del supporto dei messaggi IPv6 in ingresso anonimo nell'organizzazione, il messaggio passerà attraverso il normale filtro dei messaggi fornito dal servizio.

## <a name="troubleshooting"></a>Risoluzione dei problemi

- Se il server di posta elettronica di origine non dispone di un record di ricerca DNS inverso IPv6, i messaggi verranno rifiutati con l'errore seguente:

  > 450 il servizio 4.7.25 non è disponibile, l'invio dell'indirizzo IPv6 [2a01:111: F200:2004:: 240] deve avere un record DNS inverso.

- Se il mittente non supera la convalida SPF o DKIM, i messaggi verranno rifiutati con l'errore seguente:

  > 450 servizio 4.7.26 non disponibile, il messaggio inviato su IPv6 [2a01:111: F200:2004:: 240] deve passare sia SPF sia la convalida DKIM.

- Se si tenta di ricevere messaggi IPv6 anonimi prima di essere stati scelti, il messaggio verrà rifiutato con il seguente errore:

  > 550 5.2.1 servizio non disponibile, [contoso.com] non accetta la posta elettronica su IPv6.

## <a name="for-more-information"></a>Ulteriori informazioni

[Supporto per la convalida di messaggi firmati con DKIM](support-for-validation-of-dkim-signed-messages.md)
