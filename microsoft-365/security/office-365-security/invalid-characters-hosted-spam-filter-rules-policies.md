---
title: Evitare caratteri non validi nelle regole di filtro della posta indesiderata e nel criterio del filtro della posta indesiderata
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 09/24/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Viene fornita assistenza per gli amministratori che dispongono di caratteri non validi nella configurazione di protezione da posta indesiderata e vengono eseguiti in &amp; problemi quando si tenta di utilizzare il Centro sicurezza e conformità.
ms.openlocfilehash: 96d81c17c33c5ecf6e7b88ebe5676336b963cb4e
ms.sourcegitcommit: 550ea6f093ec35182e7c65a2811e9bfb07ec7d01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2019
ms.locfileid: "38039105"
---
# <a name="avoid-invalid-characters-in-your-spam-filter-rules-and-spam-filter-policy"></a>Evitare caratteri non validi nelle regole del filtro posta indesiderata e nei criteri di filtro della posta 

In precedenza, gli amministratori di Office 365 impostare e configurare le regole di filtro della posta indesiderata e i criteri di filtro della posta indesiderata tramite l'interfaccia di amministrazione di Exchange. A questo punto, è possibile &amp; utilizzare il Centro sicurezza e conformità per gestire la configurazione della protezione da posta indesiderata. I caratteri seguenti sono supportati nell'interfaccia di amministrazione di Exchange, ma non sono supportati per &amp; l'utilizzo nel centro sicurezza e conformità.  

**Caratteri non validi:**
  
```\ % & * + / = ? { } | < > ( ) ; : , [ ] "```

Se le regole del filtro di posta indesiderata o il criterio di filtro della posta indesiderata contiene uno dei caratteri non validi, è possibile che si verifichi uno o tutti questi problemi:
- Potrebbe essere Impossibile trovare il criterio o le regole nel centro sicurezza &amp; e conformità.
- È possibile che si verifichino errori durante il tentativo di ottenere le regole o il criterio utilizzando Windows PowerShell.
- Potrebbe risultare che il criterio o le impostazioni non vengano eseguite o eseguite come previsto.

## <a name="remove-the-invalid-characters-from-the-spam-filter-policy-and-rules"></a>Rimuovere i caratteri non validi dai criteri e dalle regole del filtro della posta indesiderata

Dopo aver identificato i criteri e le regole che contengono caratteri non validi, è possibile modificare i nomi utilizzando i cmdlet di Windows PowerShell. 

1. [Connettersi a Exchange Online tramite Remote PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).
    
2. Per modificare il nome del criterio di filtro della posta indesiderata, eseguire il cmdlet Set-HostedContentFilterPolicy come indicato di seguito:
    
    ```powershell
    Set-HostedContentFilterPolicy -Identity "Old policy name" -Name "New policy name"
    ```  

3. Per modificare il nome di una regola di filtro per la posta indesiderata, eseguire il cmdlet Set-HostedContentFilterRule come indicato di seguito:
    
    ```powershell
    Set-HostedContentFilterRule -Identity "Old rule name" -Name "New rule name"
    ```  

  
 ## <a name="for-more-information"></a>Ulteriori informazioni

[Gestione delle minacce nel centro &amp; sicurezza e conformità](protect-against-threats.md)
  
[Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterpolicy?view=exchange-ps)

[Set-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterrule?view=exchange-ps)
