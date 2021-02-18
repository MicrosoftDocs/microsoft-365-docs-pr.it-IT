---
title: Supporto per la convalida dei messaggi firmati DKIM (Domain Keys Identified Mail)
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a4c95148-a00c-4d12-85ed-88520b547d97
ms.collection:
- M365-security-compliance
description: Informazioni sulla convalida dei messaggi firmati DKIM in Exchange Online Protection ed Exchange Online
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9da41cc7918b36e1aa6a4a8cc48aea6cd2a865c6
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290262"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a>Supporto per la convalida di messaggi firmati con DKIM

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Exchange Online Protection (EOP) ed Exchange Online supportano entrambi la convalida in ingresso dei messaggi[DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)(Domain Keys Identified Mail).

DKIM convalida che un messaggio di posta elettronica non è stato *falsificato* da un altro utente e che è stato inviato dal dominio da cui è stato dichiarato.  Consente di inviare un messaggio di posta elettronica all'organizzazione che lo ha inviato. La verifica DKIM viene utilizzata automaticamente per tutti i messaggi inviati con IPv6. Microsoft 365 supporta anche DKIM quando la posta viene inviata tramite IPv4. Per ulteriori informazioni sul supporto di IPv6, vedere [Supporto per messaggi di posta elettronica in ingresso anonimi su IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md).

DKIM convalida un messaggio con firma digitale che viene visualizzato nellDKIM-Signature delle intestazioni del messaggio. I risultati di una DKIM-Signature convalida vengono contrassegnati nell'intestazione Authentication-Results controllo. Il testo dell'intestazione del messaggio è simile al seguente (dove contoso.com è il mittente):

 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`

> [!NOTE]
> Per ulteriori informazioni sull'intestazione Authentication-Results messaggio, vedere RFC 7001 ([Message Header Field for Indicating Message Authentication Status](https://www.rfc-editor.org/rfc/rfc7001.txt)). L'implementazione DKIM di Microsoft è conforme a questa RFC.

Gli amministratori possono creare regole del flusso [di posta](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) di Exchange (note anche come regole di trasporto) sui risultati della convalida DKIM. Queste regole del flusso di posta consentiranno agli amministratori di filtrare o instradare i messaggi in base alle esigenze.
