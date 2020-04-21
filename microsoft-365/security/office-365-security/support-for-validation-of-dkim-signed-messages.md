---
title: Supporto per la convalida di messaggi firmati con DKIM
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
ms.openlocfilehash: 1abe517ed7922b60abb3a78436ed61b4d0b3ed55
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631206"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a>Supporto per la convalida di messaggi firmati con DKIM

Exchange Online Protection (EOP) ed Exchange Online supportano la convalida in ingresso di messaggi Domain Keys Identified Mail ([DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)). DKIM è un metodo per confermare che il messaggio è stato inviato dal dominio di origine dichiarato e che non è stato soggetto a spoofing da parte di altri. Collega una messaggio di posta elettronica all'organizzazione che lo ha inviato. La verifica DKIM viene utilizzata automaticamente per tutti i messaggi inviati tramite comunicazioni IPv6. Microsoft 365 ora supporta anche DKIM quando la posta viene inviata tramite IPv4. Per ulteriori informazioni sul supporto di IPv6, vedere [Supporto per messaggi di posta elettronica in ingresso anonimi su IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md).

DKIM convalida un messaggio con firma digitale visualizzato nell'intestazione DKIM-Signature nelle intestazioni del messaggio. I risultati di una convalida DKIM-Signature vengono inseriti nell'intestazione Authentication-Results, che è conforme a RFC 7001 ([Message Header Field for Indicating Message Authentication Status](https://www.rfc-editor.org/rfc/rfc7001.txt)). Il testo dell'intestazione del messaggio è simile al seguente (dove contoso.com è il mittente):

 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`

Gli amministratori possono creare [regole del flusso di posta](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) di Exchange (note anche come regole di trasporto) sui risultati di una convalida DKIM per filtrare o instradare i messaggi in base alle esigenze.
