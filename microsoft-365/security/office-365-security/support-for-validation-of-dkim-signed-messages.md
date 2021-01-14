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
# <a name="support-for-validation-of-dkim-signed-messages"></a>Supporto per la convalida di messaggi firmati con DKIM

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

Exchange Online Protection (EOP) ed Exchange Online supportano entrambi la convalida in ingresso dei messaggi di posta elettronica ([DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)) identificati dai tasti di dominio.

DKIM verifica che un messaggio di posta elettronica non sia stato *falsificato* da un altro utente e che sia stato inviato dal dominio *da cui proviene* . Collega un messaggio di posta elettronica all'organizzazione che l'ha inviata. La verifica di DKIM viene utilizzata automaticamente per tutti i messaggi inviati con IPv6. Microsoft 365 supporta anche DKIM quando la posta viene inviata tramite IPv4. Per ulteriori informazioni sul supporto di IPv6, vedere [Supporto per messaggi di posta elettronica in ingresso anonimi su IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md).

DKIM convalida un messaggio con firma digitale che viene visualizzato nell'intestazione DKIM-Signature delle intestazioni del messaggio. I risultati di una convalida DKIM-Signature vengono contrassegnati nell'intestazione Authentication-Results. Il testo dell'intestazione del messaggio è simile al seguente (dove contoso.com è il mittente):

 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`

> [!NOTE]
> Per ulteriori informazioni sull'intestazione Authentication-Results, vedere RFC 7001 ([Message Header Field per indicare lo stato di autenticazione dei messaggi](https://www.rfc-editor.org/rfc/rfc7001.txt). L'implementazione di DKIM di Microsoft è conforme a questa RFC.

Gli amministratori possono creare [regole del flusso di posta](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) di Exchange (note anche come regole di trasporto) sui risultati della convalida di DKIM. Queste regole del flusso di posta consentiranno agli amministratori di filtrare o instradare i messaggi in base alle esigenze.
