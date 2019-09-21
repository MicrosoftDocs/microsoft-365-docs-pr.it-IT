---
title: Supporto per la convalida di messaggi firmati con DKIM
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
ms.openlocfilehash: 75c104af4b3e6126bac37024de2c7f6ab337a028
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37084838"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a>Supporto per la convalida di messaggi firmati con DKIM

Exchange Online Protection (EOP) ed Exchange Online supportano la convalida in ingresso di messaggi Domain Keys Identified Mail ([DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)). DKIM è un metodo per confermare che il messaggio è stato inviato dal dominio di origine dichiarato e che non è stato soggetto a spoofing da parte di altri. Collega una messaggio di posta elettronica all'organizzazione che lo ha inviato. La verifica DKIM viene utilizzata automaticamente per tutti i messaggi inviati tramite comunicazioni IPv6. Office 365 supporta ora anche DKIM quando la posta viene inviata tramite IPv4. Per ulteriori informazioni sul supporto di IPv6, vedere [Supporto per messaggi di posta elettronica in ingresso anonimi su IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md).
  
DKIM convalida un messaggio con firma digitale visualizzato nell'intestazione DKIM-Signature nelle intestazioni del messaggio. I risultati di una convalida DKIM-Signature vengono inseriti nell'intestazione Authentication-Results, che è conforme a RFC 7001 ([Message Header Field for Indicating Message Authentication Status](https://www.rfc-editor.org/rfc/rfc7001.txt)). Il testo dell'intestazione del messaggio è simile al seguente (dove contoso.com è il mittente):
  
 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`
  
Gli amministratori possono creare [regole del flusso di posta](http://technet.microsoft.com/library/743bd525-0ca2-426d-b76c-b4a052bc8886.aspx) di Exchange (note anche come regole di trasporto) sui risultati di una convalida DKIM per filtrare o instradare i messaggi in base alle esigenze. 
  

