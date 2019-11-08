---
title: Supporto per messaggi di posta elettronica in ingresso anonimi su IPv6
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b68df621-0a5f-4824-8abc-41e0c4fd1398
ms.collection:
- M365-security-compliance
description: Informazioni su come configurare il supporto per i messaggi anonimi provenienti da origini IPv6 per Exchange Online Protection ed Exchange Online.
ms.openlocfilehash: c29c1fa450ca2a2e213930c4f4a394aaf462e31d
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2019
ms.locfileid: "38031991"
---
# <a name="support-for-anonymous-inbound-email-messages-over-ipv6"></a>Supporto per i messaggi di posta elettronica in ingresso anonimi su IPv6

Exchange Online Protection (EOP) ed Exchange Online supportano la ricezione di messaggi di posta elettronica in ingresso anonimi sulle comunicazioni IPv6 da mittenti che non inviano messaggi su TLS (Transport Layer Security). È possibile scegliere di ricevere i messaggi tramite IPv6 richiedendo questa funzionalità dal supporto tecnico Microsoft aprendo l'interfaccia di amministrazione di Microsoft 365 in [https://admin.microsoft.com/adminportal/home](https://admin.microsoft.com/adminportal/home), facendo clic su **supporto**e quindi su **nuova richiesta di servizio**. Se non si sceglie di utilizzare IPv6, si continuerà a ricevere messaggi su IPv4.
  
I mittenti che trasmettono messaggi al servizio su IPv6 devono rispettare i seguenti due requisiti:
  
1. L'indirizzo IPv6 di invio deve avere un record PTR valido ([record DNS inverso](https://en.wikipedia.org/wiki/Reverse_DNS_lookup) dell'indirizzo IPv6 di invio). 
    
2. Il mittente deve superare la verifica SPF (definita in [RFC 7208](https://tools.ietf.org/html/rfc7208)) oppure la [verifica DKIM](https://dkim.org/) (definita in [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).
    
Il rispetto di tali requisiti è obbligatorio e non dipende dalla configurazione utilizzata prima di scegliere IPv6. Se entrambi i requisiti sono soddisfatti, il messaggio passerà attraverso il normale filtro dei messaggi di posta elettronica fornito dal servizio. Se uno dei due requisiti non è soddisfatto, il messaggio sarà rifiutato con una delle seguenti risposte 450:
  
-  `450 4.7.25 Service unavailable, sending IPv6 address [2a01:111:f200:2004::240] must have reverse DNS record.`
    
-  `450 4.7.26 Service unavailable, message sent over IPv6 [2a01:111:f200:2004::240] must pass either SPF or DKIM validation.`
    
Se non si è scelto di ricevere messaggi su IPv6 e il mittente tenta di forzare un messaggio su IPv6 collegandosi manualmente al server di posta, il messaggio sarà rifiutato con una risposta 550 simile alla seguente:
  
 `550 5.2.1 Service unavailable, [contoso.com] does not accept email over IPv6.`
  
## <a name="for-more-information"></a>Ulteriori informazioni

[Supporto per la convalida di messaggi firmati con DKIM](support-for-validation-of-dkim-signed-messages.md)
  

