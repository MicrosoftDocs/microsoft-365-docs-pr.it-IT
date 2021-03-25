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
ms.openlocfilehash: 8695e25000390cf6c5d58adf63db1984c873d75b
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206462"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a>Supporto per la convalida di messaggi firmati con DKIM

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Online Protection (EOP) ed Exchange Online supportano entrambi la convalida in ingresso dei messaggi[DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)(Domain Keys Identified Mail).

DKIM convalida che un messaggio di posta elettronica non è stato *falsificato* da un altro utente ed è stato inviato dal dominio da cui è stato specificato.  Viene quindi inviato un messaggio di posta elettronica all'organizzazione che lo ha inviato. La verifica DKIM viene utilizzata automaticamente per tutti i messaggi inviati con IPv6. Microsoft 365 supporta inoltre DKIM quando la posta viene inviata tramite IPv4. Per ulteriori informazioni sul supporto di IPv6, vedere [Supporto per messaggi di posta elettronica in ingresso anonimi su IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md).

DKIM convalida un messaggio con firma digitale che viene visualizzato nellDKIM-Signature delle intestazioni del messaggio. I risultati di una DKIM-Signature convalida vengono contrassegnati nell'intestazione Authentication-Results. Il testo dell'intestazione del messaggio è simile al seguente (dove contoso.com è il mittente):

 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`

> [!NOTE]
> Per ulteriori informazioni sull'intestazione Authentication-Results messaggio, vedere RFC 7001 ([Message Header Field for Indicating Message Authentication Status](https://www.rfc-editor.org/rfc/rfc7001.txt)). L'implementazione DKIM di Microsoft è conforme a questa RFC.

Gli amministratori possono creare regole del flusso [di posta](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) di Exchange (note anche come regole di trasporto) sui risultati della convalida DKIM. Queste regole del flusso di posta consentiranno agli amministratori di filtrare o instradare i messaggi in base alle esigenze.